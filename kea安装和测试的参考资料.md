### 安装和测试的参考资料

https://www.jianshu.com/p/b333c4271939

#### 下载kea github源码

#### 安装必要的软件

yum install gcc gcc-c++ openssl-devel mariadb-devel libtool automake autoconf -y

#### 依赖的软件

1. yum install -y boost boost-devel

2. yum install -y log4cplus log4cplus-devel 如果没有yum 源 本地下载log4cplus.tar.xz xz -d file.xz tar xf file.tar

3. 依赖的软件的备注 log4cplus C++ logging library(https://sourceforge.net/p/log4cplus/wiki/Home/).

   Boost system library (https://www.boost.org/).

   To store lease information in a PostgreSQL database, Kea requires PostgreSQL headers and libraries.

   As of the 1.5.0 release, Kea provides a NETCONF interface with the kea-netconf agent.

## kea manual

https://kea.readthedocs.io/en/latest/arm/intro.html

### ch3 install kea

```
首先安装postgresql
 
 
 yum -y install postgresql11-server postgresql11
 
$ yum list postgres*
$ yum install -y postgresql postgresql-devel postgresql-server

yum install -y postgresql11 postgresql11-devel postgresql11-server


查看kea源文件目录的INSTALL文件。需要生成configure文件
$ autoreconf --install
$ ./configure --with-pgsql=/usr/bin/pg_config 

./configure --with-pgsql=/usr/pgsql-11/bin/pg_config --enable-shell --with-log4cplus --with-mysql 

./configure --with-pgsql=/usr/bin/pg_config --enable-shell --with-log4cplus --with-mysql --enable-perfdhcp
    

$ make -j4
$ make install

查看postgresql的安装地址
$rpm -qal|grep postgres
```

$ postgresql-setup initdb Initializing database ... OK

```
# 启动pgsql
$ systemctl start postgresql

# 登录postgresql
$ sudo -u postgres psql postgres

# create user
CREATE DATABASE
postgres=# CREATE USER psql WITH     PASSWORD 'psql323';
CREATE ROLE
postgres=# GRANT ALL PRIVILEGES ON DATABASE kea TO psql;
GRANT
postgres=#
```

### ch4 kea db 管理

```
kea-admin command backend
    kommand: 
        db-init
        db-version
        db-upgrade
        lease-dump

    backend:
        memfile
        mysql
        pgsql
        cgq
    

# kea 数据库创建后，init表
$ kea-admin db-init pgsql -u postgres -p postgres -n kea
```

### ch5 kea配置

#### 5.2 CB configuration backend

从多个db控制和获取配置。只有mysql支持

### ch6 用keactrl管理kea

keactrl是个shell脚本，用来控制各种kea server的startup, shutdown和reconfiguration. the Kea servers (kea-dhcp4, kea-dhcp6, kea-dhcp-ddns, kea-ctrl-agent, and kea-netconf).

6.2 命令行选项

### ch7 kea control agent

#### 7.1 overview

```
CA是个daemon，暴露了restful 控制接口来管理kea servers  
从http接受控制命令，转发到对应的server或自己处理，依据是service参数，命令的细节和结构在[management api](https://kea.readthedocs.io/en/latest/arm/ctrl-channel.html#ctrl-channel)
```

#### 7.2 配置

```
"Control-agent":
    "control-sockets": {
        dhcp4, dhcp6,d2
    "hooks-libraries": [
    "loggers": [ {
        "name": "kea-ctrl-agent",
        "severity": "INFO"
    } ]
```

#### 7.3 安全连接

apache2或nginx作为反向代理，运行ssl

```
# For URLs such as https://kea.example.org/kea, forward the
# requests to http://127.0.0.1:8080.
location /kea {
    proxy_pass http://127.0.0.1:8080;
}
```

#### 7.4 运行CA

```
$ ./kea-ctrl-agent -c /usr/local/etc/kea/kea-ctrl-agent.conf
```

#### 7.5 连接CA

### ch8 dhcpv4 server

#### 8.1 start/stop

```
keactrl 
    -c file
    -d
    -p server-port
    -P client-port
    -t config-file
    -v
    -V
    -W kea configuration report
```

Since the DHCPv4 server opens privileged ports, it requires root access. This daemon must be run as root.

#### 8.2 dhcpv4 服务器配置

{

```
# DHCPv4 configuration starts on the next line
```

"Dhcp4": {

```
# First we set up global values
"valid-lifetime": 4000,
"renew-timer": 1000,
"rebind-timer": 2000,

# Next we set up the interfaces to be used by the server.
"interfaces-config": {
    "interfaces": [ "eth0" ]
},

# And we specify the type of lease database
"lease-database": {
    "type": "memfile",
    "persist": true,
    "name": "/var/lib/kea/dhcp4.leases"
},

# Finally, we list the subnets from which we will be leasing addresses.
"subnet4": [
    {
        "subnet": "192.0.2.0/24",
        "pools": [
            {
                 "pool": "192.0.2.1 - 192.0.2.200"
            }
        ]
    }
]
# DHCPv4 configuration ends with the next line
```

}

}

## ch8

### 8.2 sanity checks in dhcpv4

数据保持一致性 配置scope叫sanity-checks,目前只有一个参数是lease-checks 每个子网有一个subnet-id的值，lease数据表有一列是subnet_id 然而，如果配置被修改，一个lease可能有一个subnet-id 但是没有对应的subnet来匹配这个id

```
"Dhcp4": { "sanity-checks": {
    "lease-checks": "fix-del" 
    },
}
```

#### 8.9 management api for dhcpv4 server

## ch15

### 15.9

#### 15.9.1 subnet-id参数

在过去的版本，保留地址属于一个特定的子网，kea1.5.0之后，保留地址能被全局设置，也就是不局限于任何子网。

### ch17 management api

2020-01-13

安装kea perfdhcp

找不到aclocal 需要安装libtool

yum install -y libtool

$ autoreconf -f -i

$./configure

insert into lease4 (address, hwaddr, client_id, valid_lifetime, expire, subnet_id, fqdn_fwd, fqdn_rev, state) values (167772266, '\x000c290501ab', '3', 3600, '2019-11-15 06:22:55-03', 1, 'f', 'f', 2);

insert into lease4 (address, hwaddr, client_id, valid_lifetime, expire, subnet_id, fqdn_fwd, fqdn_rev, state) values (167772269, '0x000c290501ab', '3', 3600, '2019-11-15 06:22:55-03', 1, 'f', 'f', 2); insert into lease4 (address, hwaddr, client_id, valid_lifetime, expire, subnet_id, fqdn_fwd, fqdn_rev, state) values (167772269, '0x000c290501ab', '3', 3600, '2019-11-15 06:22:55-03', 1, 'f', 'f', 2);

kea-admin lease-init -h 10.0.0.23 mysql -u root -p Xieqc./2002 -n kea

grant all privileges on *.* to 'root'@'%' identified by 'Xieqc./2002' with grant option; flush privileges;

### install mysqld

$ systemctl start mysqld

// 查找root的默认密码 $ grep root /var/log/mysqld.log 2020-01-13T10:02:45.873375Z 1 [Note] A temporary password is generated for root@localhost: ;c<wNKyB!0eH

//reset password

mysql> ALTER USER 'root'@'localhost' IDENTIFIED BY 'Xieqc./2002'; mysql> flush privileges;

//初始化db

$ kea-admin db-init mysql -u root -p Xieqc./2002 -n kea

//修改kea配置文件，重启dhcp服务

$ keactrl reload -s dhcp6

//允许root远程访问

GRANT ALL PRIVILEGES ON *.* TO 'root'@'%' IDENTIFIED BY 'Xieqc./2002' WITH GRANT OPTION;

flush privileges;