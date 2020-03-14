## vmware虚拟机列表与功能

| dell ip  | ip地址         | vm-name         | 功能                                   | 负责人 |
| -------- | -------------- | --------------- | -------------------------------------- | ------ |
| 10.0.0.2 |                |                 |                                        |        |
|          | 10.0.0.55      |                 | 节点管理接口、 cockroach db、kafka服务 | 谢全朝 |
|          | 10.0.0.58      | windows 7 x64   | windows7                               | 谢全朝 |
|          | 10.0.0.24      | centos7-clone01 | prometheus docker                      | 谢全朝 |
|          | 10.0.0.69      | centos7-clone08 | elasticsearch, kibana                  | 谢全朝 |
|          | 192.168.13.131 | centos10        | kea的客户端                            | 谢全朝 |
|          | 192.168.13.128 | centos7-clone02 | kea的客户端2                           | 谢全朝 |
|          | 192.168.13.132 | centos11        | 新的kea服务器                          | 谢全朝 |
|          |                |                 |                                        |        |



| 序号 | 主机名称         | IP         | 是否虚拟机 | 用途               | 角色       |
| ---- | ---------------- | ---------- | ---------- | ------------------ | ---------- |
| 1    | 01DevelopMachine | 10.0.0.7   | 否         | 开发人员           |            |
| 2    | 03DevelopMachine | 10.0.0.110 | 否         | 测试人员           |            |
| 3    | huangwlv1        | 10.0.0.19  | 是         | huagnwanlong       |            |
| 4    | huangwlv2        | 10.0.0.20  | 是         | huagnwanlong       |            |
| 5    | webserver        | 10.0.0.21  | 是         | huagnwanlong       |            |
|      |                  |            |            |                    |            |
|      |                  | 10.0.0.31  | 否         | 整体测试(测试组用) |            |
|      |                  | 10.0.0.32  | 是         | 整体测试(测试组用) | controller |
|      |                  | 10.0.0.34  | 是         | 整体测试(测试组用) | controller |
|      |                  | 10.0.0.35  | 是         | 整体测试(测试组用) | dns        |
|      |                  | 10.0.0.36  | 是         | 整体测试(测试组用) | dns        |
|      |                  | 10.0.0.37  | 是         | 整体测试(测试组用) | dhcp       |
|      |                  | 10.0.0.38  | 是         | 整体测试(测试组用) | dhcp       |





19服务器的端口和服务列表

| 服务器ip  | 端口号 | 进程       | 备注                  |
| --------- | ------ | ---------- | --------------------- |
| 10.0.0.19 | 8001   | dnsagent   | dns exporter          |
| 10.0.0.19 | 8888   | dnsagent   | dns client (grpc)     |
| 10.0.0.19 | 9100   | dnsagent   | metrics to prometheus |
| 10.0.0.19 | 8081   | controller |                       |
| 10.0.0.19 | 26257  | cockroach  | 数据库                |
|           | 9092   | kafka      |                       |
|           | 2181   | zookeeper  |                       |



[root@huangwlv1 dnsagent]# netstat -natp | grep LIST
tcp        0      0 127.0.0.1:8080          0.0.0.0:*               LISTEN      10386/cockroach
tcp        0      0 127.0.0.1:26257         0.0.0.0:*               LISTEN      10386/cockroach
tcp        0      0 10.0.0.19:53            0.0.0.0:*               LISTEN      21784/named
tcp        0      0 10.0.0.11:53            0.0.0.0:*               LISTEN      21784/named
tcp        0      0 127.0.0.1:53            0.0.0.0:*               LISTEN      21784/named
tcp        0      0 127.0.0.1:953           0.0.0.0:*               LISTEN      21784/named

tcp6       0      0 :::53                   :::*                    LISTEN      21784/named

tcp6       0      0 :::39123                :::*                    LISTEN      13397/java
tcp6       0      0 :::37379                :::*                    LISTEN      14446/java
tcp6       0      0 :::9092                 :::*                    LISTEN      14446/java
tcp6       0      0 :::2181                 :::*                    LISTEN      13397/java

**//controller**

tcp6       0      0 :::8081                 :::*                    LISTEN      14824/./controller

**// dnsagent**
tcp        0      0 127.0.0.1:8888          0.0.0.0:*               LISTEN      24114/./dnsagent
tcp6       0      0 :::9100                 :::*                    LISTEN      24114/./dnsagent
tcp6       0      0 :::8001                 :::*                    LISTEN      24114/./dnsagent



**//55上启动gorest**

[root@localhost dnsagent]# netstat -natp | grep LIST | grep gorest
tcp        0      0 0.0.0.0:3333            0.0.0.0:*               LISTEN      83350/./gorest
tcp6       0      0 :::1234                 :::*                    LISTEN      83350/./gorest



ip-55

- 启动zookeeper和kafka

cd /root/kafka

nohup bin/zookeeper-server-start.sh -daemon config/zookeeper.properties &

nohup bin/kafka-server-start.sh config/server.properties >kafka-start.log &

todo问题 logs占用存储空间有些大 定期删除

- 启动websocket监听（dhcp方式）

cd /root/go1.13.4/src/github.com/linkingthing/ddi/cmd/dhcpv4agent

~~nohup ./dhcpv4agent &~~



- 查看当前服务器监听的端口

[root@ip-55 dhcpv4agent]# netstat -natp | grep LIST
tcp        0      0 0.0.0.0:22              0.0.0.0:*               LISTEN      6437/sshd
tcp        0      0 10.0.0.55:8888          0.0.0.0:*               LISTEN      7956/./dhcpv4agent
tcp6       0      0 :::3306                 :::*                    LISTEN      6499/mysqld
tcp6       0      0 :::9100                 :::*                    LISTEN      6438/node_exporter
tcp6       0      0 :::22                   :::*                    LISTEN      6437/sshd
tcp6       0      0 :::34306                :::*                    LISTEN      7600/java
tcp6       0      0 :::36642                :::*                    LISTEN      7244/java
tcp6       0      0 :::9092                 :::*                    LISTEN      7600/java
tcp6       0      0 :::2181                 :::*                    LISTEN      7244/java





31机器的kea配置

[root@localhost kea]# vim kea-dhcp4.conf
[root@localhost kea]# pwd
/usr/local/etc/kea

  "lease-database": {

​    // Memfile is the simplest and easiest backend to use. It's a in-memory

​    // C++ database that stores its state in CSV file.

​    \#"type": "memfile",

​    "type": "mysql",

​    "name": "kea",

​    "user":"kea",

​    "password":"Xieqc./323",

​    "host":"localhost",

​    "port":3306

​    //"lfc-interval": 2603600

  },

select * from lease4;





