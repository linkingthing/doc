|操作方法|URL|接口功能|备注|
|-|-|-|-|
|GET |/apis/linkingthing.com/example/v1/checkcodes/checkcode|获取校验码||
|POST |/apis/linkingthing.com/example/v1/users?action=login|用户登录||
|POST |/apis/linkingthing.com/example/v1/checkcodes/checkcode?action=checkvalue|校验码校验||
|PUT |/apis/linkingthing.com/example/v1/users?action=changepwd|用户密码修改||
|POST |/apis/linkingthing.com/example/v1/users?action=logout|用户退出登录||
|GET |/apis/linkingthing.com/example/v1/nodes?querytype=querystat|||
|GET |/apis/linkingthing.com/example/v1/nodes?querytype=queryrange|||
|GET |/apis/linkingthing.com/example/v1/nodes?querytype=queryserver|||
|GET |/apis/linkingthing.com/example/v1/nodes?querytype=querydns|||
|GET |/apis/linkingthing.com/example/v1/nodes?querytype=querydhcp|||
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