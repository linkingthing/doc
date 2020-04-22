|操作方法|URL|接口功能|备注|
|-|-|-|-|
|GET |/apis/linkingthing.com/example/v1/checkcodes/checkcode|获取校验码||
|POST |/apis/linkingthing.com/example/v1/users?action=login|用户登录||
|POST |/apis/linkingthing.com/example/v1/checkcodes/checkcode?action=checkvalue|校验码校验||
|PUT |/apis/linkingthing.com/example/v1/users?action=changepwd|用户密码修改||
|POST |/apis/linkingthing.com/example/v1/users?action=logout|用户退出登录||
|GET |/apis/linkingthing.com/example/v1/nodes?querytype=querystat|节点的cpu内存磁盘利用率|节点管理-服务器信息的三个饼图|
|GET |/apis/linkingthing.com/example/v1/nodes?querytype=queryrange|获取某段时间的cpu内存磁盘利用率|节点管理-controller服务器的三个历史折线图 (cpu内存硬盘)|
|GET |/apis/linkingthing.com/example/v1/nodes?querytype=queryserver|列出节点的状态|节点管理-拓扑图和服务器列表页面|
|GET |/apis/linkingthing.com/example/v1/nodes?querytype=querydns|节点管理模块，展示dns模块的统计数据|top域名、解析类型等|
|GET |/apis/linkingthing.com/example/v1/nodes?querytype=querydhcp|节点管理模块，dhcp模块的统计数据|dhcp报文统计、利用率、lease统计|
|GET |/apis/linkingthing.com/example/v1/resolveStatuses|DNS解析状态查询||
|GET |/apis/linkingthing.com/example/v1/memhits|DNS缓存命中率查询||
|POST |/apis/linkingthing.com/example/v1/networks?action=checkipv6prefix|IP地址规划IPv6地址校验||
|POST |/apis/linkingthing.com/example/v1/networks|IP地址规划新建一个网络||
|DELETE |/apis/linkingthing.com/example/v1/networks/:network_id|IP地址规划删除一个网络||
|GET |/apis/linkingthing.com/example/v1/networks/:network_id|IP地址规划获取一个网络||
|PUT |/apis/linkingthing.com/example/v1/networks/:network_id|IP地址规划修改一个网络||
|GET |/apis/linkingthing.com/example/v1/subnets/:subnet_id/ipaddresses|获取所有的子网下的IP地址|包含属性|
|POST |/apis/linkingthing.com/example/v1/subnets/:subnet_id?action=split|子网拆分||
|PUT |/apis/linkingthing.com/example/v1/subnets/:subnet_id/ipaddresses/:ipaddress_id|修改子网下某个ip的属性||
|PUT |/apis/linkingthing.com/example/v1/subnets/:subnet_id/ipaddresses/:ipaddress_id/ipattrappends/ipattrappend|修改子网下某个ip下的扩展属性||
|POST |/apis/linkingthing.com/example/v1/subnets/:subnet_id/ipaddresses/:ipaddress_id?action=change&ope=tostable|子网下某个ip转固定||
|POST |/apis/linkingthing.com/example/v1/subnets/:subnet_id/ipaddresses/:ipaddress_id?action=change&ope=toresv|子网下某个ip转保留||