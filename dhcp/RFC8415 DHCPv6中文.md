# RFC8415 DHCPv6中文



## 相关的RFC整理

RFC3315 上一个版本的DHCPv6
RFC3633 DHCPv6相关的IPv6前缀选项
RFC3736 无状态DHCPv6
RFC4193 本地唯一IPv6单播地址 Unique Local IPv6 Unicast Addresses https://tools.ietf.org/html/rfc4193
RFC4242 DHCPv6的信息刷新时间选项
RFC4291 IPv6寻址结构
  	中文 https://wenku.baidu.com/view/f7d0d2896529647d272852db.html

RFC4861 ndp IPv6  https://tools.ietf.org/html/rfc4861 
RFC4862 IPv6 Stateless Address Autoconfiguration SLAAC
​	中文翻译 https://wenku.baidu.com/view/496e6701cc17552707220890.html?sxts=1577177364416

RFC4941  EUI-64  IPv6隐私扩展
RFC6355 uuid 
RFC6879 ipv6企业网络重新编号环境，思考和方法
RFC7083 当DHCPv6服务不可用时防止客户端高频请求的一种机制
RFC7084 The DHCP requirements and network architecture for Customer Edge Routers
RFC7283 中继代理对未知类型消息的处理
RFC7500 操作模型的交互过程
RFC7550 多种有状态的DHCPv6选项
RFC7844 Anonymity Profiles for DHCP Clients
RFC8200 IPv6标准

本文档更新了多个RFC，3315 3633 3736 4242 7083 7283 7550等

## Ch1 介绍

DHCPv6的基本操作提供了对与服务器连接在相同链路的客户端的配置。中继代理功能用来为连接在不同链路的客户端和服务器之间提供通信功能。

DHCPv6能向一个设备提供服务器分配的地址和其他配置信息，这些信息保存在数据包的option中。DHCPv6也能用来扩展新的option来提供本文未定义的其他配置信息。

DHCPv6也提供前缀代理机制(最初定义在RFC3633)，通过这个机制，一个代理路由器能向请求路由器发送前缀信息(定义在RFC7084)。

DHCP也能用来指提供其他配置选项(不提供IPv6地址和前缀)，这意味着服务器不需要跟踪任何状态，因此，这种模式被称为“无状态DHCPv6”。

### 1.1 本文与过去的DHCPv6标准的关系

过去的几个RFC都被本文更新了，偶尔参考下就好。具体RFC编号在本文开始部分

### 1.2 与DHCPv4的关系

历史的DHCPv4的RFC有RFC2131和RFC2132，本文不描述DHCPv4与DHCPv6的整合。RFC3315建议未来的DHCPv6应该扩展能够携带IPv4的地址和配置信息。然而，现在的IETF的一致意见是向节点传递IPv4的配置信息时应该用DHCPv4而不是DHCPv6。在纯IPv6的网络，RFC7341描述了一个传输机制可以通过DHCPv6协议来传递DHCPv4消息
DHCPv4和DHCPv6的配置的合并不在本文的范围。RFC4477讨论了一起运行DHCPv4和DHCPv6服务时遇到的一些问题和可能的策略。然而RFC4477有些过时了，可以参考一下。

## 2 

本文也利用内部概念













