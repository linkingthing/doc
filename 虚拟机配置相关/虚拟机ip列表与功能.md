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









