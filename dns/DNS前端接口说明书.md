# 接口总览

| 序号 | 方法   | 接口                                                         | 表单                                                         | 菜单                                   |描述|
| ---- | ------ | ------------------------------------------------------------ | ------------------------------------------------------------ | -------------------------------------- |----|
| 1.    | GET    | /apis/linkingthing.com/example/v1/acls                       | 无                                                           | 访问控制列表                           |
| 2.    | POST   | /apis/linkingthing.com/example/v1/acls                       | {"name":"acl112","list":[{"name":"a1","aclid":"547697602773778433","type":"acl"},{"name":"10.0.0.1","aclid":"1","type":"ip"}]} | 访问控制列表                           |
| 3    | GET    | /apis/linkingthing.com/example/v1/acls/:acl_id               | 无                                                           | 访问控制列表                           |
| 4    | PUT    | /apis/linkingthing.com/example/v1/acls/:acl_id               | 同POST                                                       | 访问控制列表                           |
| 5    | DELETE | /apis/linkingthing.com/example/v1/acls/:acl_id               | 无                                                           | 访问控制列表                           |
| 6    | GET    | /apis/linkingthing.com/example/v1/views                      | 无                                                           | 视图管理                               |
| 7    | POST   | /apis/linkingthing.com/example/v1/views                      | {"name":"view1231_01",   "priority":1,   "aclids":["516763968540311553","516557026014625793","516554717453811713"], "isused":1} | 视图管理                               |
| 8    | GET    | /apis/linkingthing.com/example/v1/views/:view_id             | 无                                                           | 视图管理                               |
| 9    | PUT    | /apis/linkingthing.com/example/v1/views/:view_id             | 同POST                                                        | 视图管理                               |
| 10   | DELETE | /apis/linkingthing.com/example/v1/views/:view_id             | 无                                                           | 视图管理                               |
| 11   | GET    | /apis/linkingthing.com/example/v1/views/:view_id/zones       | 无                                                           | 权威管理->配置管理->视图->区           |
| 12   | POST   | /apis/linkingthing.com/example/v1/views/:view_id/zones       | {"name":"zone1231_01", "isused":1}       | 权威管理->配置管理->视图->区           |
| 13   | GET    | /apis/linkingthing.com/example/v1/views/:view_id/zones/:zone_id | 无                                                           | 权威管理->配置管理->视图->区           |
| 14   | DELETE | /apis/linkingthing.com/example/v1/views/:view_id/zones/:zone_id | 无                                                           | 权威管理->配置管理->视图->区           |
| 15   | GET    | /apis/linkingthing.com/example/v1/views/:view_id/zones/:zone_id/rrs | 无                                                           | 权威管理->配置管理->视图->区->资源记录 |
| 16   | POST   | /apis/linkingthing.com/example/v1/views/:view_id/zones/:zone_id/rrs | {"name":"www","ttl":300,"type":"A","value":"10.0.0.41","isused":1}                                 | 权威管理->配置管理->视图->区->资源记录 |
| 17   | GET    | /apis/linkingthing.com/example/v1/views/:view_id/zones/:zone_id/rrs/:rr_id | 无                                                           | 权威管理->配置管理->视图->区->资源记录 |
| 18   | PUT    | /apis/linkingthing.com/example/v1/views/:view_id/zones/:zone_id/rrs/:rr_id | 同POST                                                        | 权威管理->配置管理->视图->区->资源记录 |
| 19   | DELETE | /apis/linkingthing.com/example/v1/views/:view_id/zones/:zone_id/rrs/:rr_id | 无                                                           | 权威管理->配置管理->视图->区->资源记录 |
| 20   | GET    | /public/*filepath                                            | 无                                                           | 静态资源路径                           |
| 21   | HEAD   | /public/*filepath                                            | 无                                                           | 静态资源路径                           |
| 25   | GET    | /apis/linkingthing.com/example/v1/views                      | 无                                                           | 转发管理->区转发|视图获取|                               |
| 26   | GET    | /apis/linkingthing.com/example/v1/views/:view_id/zones       | 无                                                           | 转发管理->区转发           |区获取
| 27   | POST   | /apis/linkingthing.com/example/v1/views/:view_id/zones/:zone_id?action=forward       | {"oper":"GET"}       | 转发管理->区转发           |服务器地址列表和转发方式获取|
| 28   | POST   | /apis/linkingthing.com/example/v1/views/:view_id/zones/:zone_id?action=forward       | {"oper":"MOD","type":"only","ips":["10.0.0.19", "10.0.0.22"]}      | 转发管理->区转发           |服务器地址列表和转发方式修改,type固定为first或者only
| 29   | POST   | /apis/linkingthing.com/example/v1/views/:view_id/zones/:zone_id?action=forward       | {"oper":"DEL"}       | 转发管理->区转发           |服务器地址列表和转发方式删除
| 30   | GET    | /apis/linkingthing.com/example/v1/views/:view_id/redirections | 无                                                           | 权威管理->配置管理->视图->区->资源记录 |
| 31   | POST   | /apis/linkingthing.com/example/v1/views/:view_id/redirections | {"name":"www.baidu.com","ttl":200,"datatype":"A","redirecttype":"localzone","value":"10.0.0.1"}                                 | 权威管理->重定向 |新建
| 32   | GET    | /apis/linkingthing.com/example/v1/views/:view_id/redirections/:redirection_id | 无                                                           | 权威管理->重定向 |查询一条记录
| 33   | PUT    | /apis/linkingthing.com/example/v1/views/:view_id/redirections/:redirection_id | 同POST                                                        | 权威管理->重定向 |修改一条记录
| 34   | DELETE | /apis/linkingthing.com/example/v1/views/:view_id/redirections/:redirection_id | 无                                                           | 权威管理->重定向 |删除一条记录
| 40   | GET    | /apis/linkingthing.com/example/v1/views/:view_id/dns64s | 无                                                           | 递归管理->4A地址合成|查询
| 41   | POST   | /apis/linkingthing.com/example/v1/views/:view_id/dns64s | {"prefix":"24oe:eeff::/96","clientacl":"514208360416477185", "aaddress":"516547807624527873"}                                 | 递归管理->4A地址合成 |新建
| 42   | GET    | /apis/linkingthing.com/example/v1/views/:view_id/dns64s/:dns64_id | 无                                                           | 递归管理->4A地址合成 |查询一条记录
| 43   | PUT    | /apis/linkingthing.com/example/v1/views/:view_id/dns64s/:dns64_id | 同POST                                                        | 递归管理->4A地址合成 |修改一条记录
| 44   | DELETE | /apis/linkingthing.com/example/v1/views/:view_id/dns64s/:dns64_id | 无                                                           | 递归管理->4A地址合成 |删除一条记录
| 45   | GET    | /apis/linkingthing.com/example/v1/ipblackholes | 无                                                           | 安全管理->地址黑名单|查询
| 46   | POST   | /apis/linkingthing.com/example/v1/ipblackholes | {"aclids":["514208360416477185","516547798340304897","516547807624527873"]}                                 | 安全管理->地址黑名单 |新建
| 47   | GET    | /apis/linkingthing.com/example/v1/ipblackholes/:ipblackhole_id | 无                                                           | 安全管理->地址黑名单 |查询一条记录
| 48   | PUT    | /apis/linkingthing.com/example/v1/ipblackholes/:ipblackhole_id | 同POST                                                        | 安全管理->地址黑名单 |修改一条记录
| 49   | DELETE | /apis/linkingthing.com/example/v1/ipblackholes/:ipblackhole_id | 无                                                           | 安全管理->地址黑名单 |删除一条记录
| 50   | GET    | /apis/linkingthing.com/example/v1/recursiveconcurrents | 无                                                           | 安全管理->并发控制|查询
| 51   | PUT    | /apis/linkingthing.com/example/v1/recursiveconcurrents/con | 同POST                                                        | 安全管理->并发控制 |修改一条记录
| 52   | GET    | /apis/linkingthing.com/example/v1/getcheckimage | 无                                                           | 登录界面=>校验码获取 |获取一条校验码图片
| 53   | GET    | /apis/linkingthing.com/example/v1/checkvalue?CheckValueToken=1581910764145&CheckValue=BYtP | 无                                                        | 登录界面=>输入校验码进行校验 |输入的校验码正确是否校验
| 54   | POST   | /apis/linkingthing.com/example/v1/login | {"username":"admin","password":"admin"}   报文头需要携带content-type: application/json;               | 登录界面=>登录校验 |登录认证，认证成功响应报文会返回token，其他接口登陆时报文头需要携带token，格式：Authorization: Bearer [token]
| 55   | GET    | /apis/linkingthing.com/example/v1/sortlists/1 | 无                 | 权威管理=>资源优先级设置 |查询
| 56   | POST   | /apis/linkingthing.com/example/v1/sortlists | {"aclids":["acl01","acl02","acl03"...]}                 | 权威管理=>资源优先级设置 |新建,设置的acl可以有多个,每个acl下面至少有一个ip或者ip段,最多两个ip或者ip段.
| 57   | PUT   | /apis/linkingthing.com/example/v1/sortlists/1 | {"aclids":["acl01","acl02","acl03"...]}                 | 权威管理=>资源优先级设置 |修改优先级设置里面的acl顺序和个数.
| 58   | DELETE   | /apis/linkingthing.com/example/v1/sortlists/1 |                  | 权威管理=>资源优先级设置 |删除整个优先级设置

# 接口详细描述

## 1. 控制列表查询
### 1.1. 获取所有ACL
- 接口信息  

|接口描述|获取视图信息|
|-|-|
|请求地址|/apis/linkingthing.com/example/v1/acls|
|请求方式|HTTP/1.1 GET|
|返回格式|JSON|

- 请求参数意义

|参数名称|是否必填|数据类型|备注|
| - |-|-|-|
|无|

- 请求示例

|请求内容|http://10.0.0.19:8081/apis/linkingthing.com/example/v1/acls|
|-|-|
|响应内容|如下引用|

```
{
	"type": "collection",
	"resourceType": "acl",
	"links": {
		"self": "/apis/linkingthing.com/example/v1/acls"
	},
	"data": [{
		"id": "1",
		"type": "acl",
		"links": {
			"collection": "/apis/linkingthing.com/example/v1/acls",
			"remove": "/apis/linkingthing.com/example/v1/acls/1",
			"self": "/apis/linkingthing.com/example/v1/acls/1",
			"update": "/apis/linkingthing.com/example/v1/acls/1"
		},
		"creationTimestamp": "2020-04-18T12:53:04Z",
		"deletionTimestamp": null,
		"name": "any",
		"list": null
	}, {
		"id": "2",
		"type": "acl",
		"links": {
			"collection": "/apis/linkingthing.com/example/v1/acls",
			"remove": "/apis/linkingthing.com/example/v1/acls/2",
			"self": "/apis/linkingthing.com/example/v1/acls/2",
			"update": "/apis/linkingthing.com/example/v1/acls/2"
		},
		"creationTimestamp": "2020-04-18T12:53:04Z",
		"deletionTimestamp": null,
		"name": "none",
		"list": null
	}, {
		"id": "548260628901855233",
		"type": "acl",
		"links": {
			"collection": "/apis/linkingthing.com/example/v1/acls",
			"remove": "/apis/linkingthing.com/example/v1/acls/548260628901855233",
			"self": "/apis/linkingthing.com/example/v1/acls/548260628901855233",
			"update": "/apis/linkingthing.com/example/v1/acls/548260628901855233"
		},
		"creationTimestamp": "2020-04-20T12:37:45Z",
		"deletionTimestamp": null,
		"name": "acl112",
		"list": null
	}, {
		"id": "548407788097142785",
		"type": "acl",
		"links": {
			"collection": "/apis/linkingthing.com/example/v1/acls",
			"remove": "/apis/linkingthing.com/example/v1/acls/548407788097142785",
			"self": "/apis/linkingthing.com/example/v1/acls/548407788097142785",
			"update": "/apis/linkingthing.com/example/v1/acls/548407788097142785"
		},
		"creationTimestamp": "2020-04-21T01:06:15Z",
		"deletionTimestamp": null,
		"name": "a22",
		"list": [{
			"name": "20.20.20.2",
			"aclid": "1",
			"type": "ip"
		}, {
			"name": "a1",
			"aclid": "547697602773778433",
			"type": "acl"
		}, {
			"name": "a2",
			"aclid": "548216738318483457",
			"type": "acl"
		}]
	}]
}
```
|JSON元素|表示意义|参数类型|参数值举例|
|- | -|-|-|
|{"name": "a22"}|acl名称|string|a22|
|"list":[]|表示嵌套的acl列表|数组|list|
|"type"|表示嵌套元素的类型,acl表示name内容为acl名称,ip表示name填充的是ip|string|a2|
|aclid|当type="acl"时有意义,表示acl的id|string|"548216738318483457"|

### 1.2. 获取一个ACL
- 接口信息  

|接口描述|获取视图信息|
|-|-|
|请求地址|/apis/linkingthing.com/example/v1/acls/:acl_id|
|请求方式|HTTP/1.1 GET|
|返回格式|JSON|

- 请求参数意义

|参数名称|是否必填|数据类型|备注|
| - |-|-|-|
|无|

- 请求示例

|请求内容|http://10.0.0.19:8081/apis/linkingthing.com/example/v1/acls/548407788097142785|
|-|-|
|响应内容|如下引用|

```
{
	"id": "548407788097142785",
	"type": "acl",
	"links": {
		"collection": "/apis/linkingthing.com/example/v1/acls",
		"remove": "/apis/linkingthing.com/example/v1/acls/548407788097142785",
		"self": "/apis/linkingthing.com/example/v1/acls/548407788097142785",
		"update": "/apis/linkingthing.com/example/v1/acls/548407788097142785"
	},
	"creationTimestamp": "2020-04-21T01:06:15Z",
	"deletionTimestamp": null,
	"name": "a22",
	"list": [{
		"name": "20.20.20.2",
		"aclid": "1",
		"type": "ip"
	}, {
		"name": "a1",
		"aclid": "547697602773778433",
		"type": "acl"
	}, {
		"name": "a2",
		"aclid": "548216738318483457",
		"type": "acl"
	}]
}
```
|JSON元素|表示意义|参数类型|参数值举例|
|- | -|-|-|
|{"name": "a22"}|acl名称|string|a22|
|list中的name|表示创建的元素的名称,当type为acl时,name为嵌套的acl名称,当type为ip时,name为ip|string|"20.20.20.2"/"a1"|
|"list":[]|表示嵌套的acl列表|数组|list|
|"type"|表示嵌套元素的类型,acl表示name内容为acl名称,ip表示name填充的是ip|string|a2|
|aclid|当type="acl"时有意义,表示acl的id|string|"548216738318483457"|

### 1.3. 新建ACL
- 接口信息  

|接口描述|获取视图信息|
|-|-|
|请求地址|/apis/linkingthing.com/example/v1/acls|
|请求方式|HTTP/1.1 POST|
|请求格式|{"name":"acl112","list":[{"name":"a1","aclid":"547697602773778433","type":"acl"},{"name":"10.0.0.1","aclid":"1","type":"ip"}]}|
|返回格式|JSON|

- 请求参数意义

|参数名称|是否必填|数据类型|备注|
| - |-|-|-|
|第一个name|是|string|表示创建的acl的名称|
|list中的name|是|string|表示创建的元素的名称,当type为acl时,name填充选择的嵌套的acl名称|
|list中的name|是|string|表示创建的元素的名称,当type为ip时,name填充客户输入的ip值|
|list中的type|是|string|表示嵌套的元素的类型,只有acl和ip两种|

- 请求示例

|请求内容|http://10.0.0.19:8081/apis/linkingthing.com/example/v1/acls|
|-|-|
|请求报文体|{"name":"acl112","list":[{"name":"a1","aclid":"547697602773778433","type":"acl"},{"name":"10.0.0.1","aclid":"1","type":"ip"}]}|
|响应内容|如下引用|

```
{
	"id": "548260628901855233",
	"type": "acl",
	"links": {
		"collection": "/apis/linkingthing.com/example/v1/acls",
		"remove": "/apis/linkingthing.com/example/v1/acls/548260628901855233",
		"self": "/apis/linkingthing.com/example/v1/acls/548260628901855233",
		"update": "/apis/linkingthing.com/example/v1/acls/548260628901855233"
	},
	"creationTimestamp": "2020-04-20T12:37:45Z",
	"deletionTimestamp": null,
	"name": "acl112",
	"list": [{
		"name": "a1",
		"aclid": "547697602773778433",
		"type": "acl"
	}, {
		"name": "10.0.0.1",
		"aclid": "1",
		"type": "ip"
	}]
}
```
|JSON元素|表示意义|参数类型|参数值举例|
|- | -|-|-|
|{"name": "acl112"}|acl名称|string|acl112|
|list中的{"name": "a1"}|嵌套的acl名称|string|a1|
|"list":[]|表示嵌套的acl列表|数组|list|
|"type"|表示嵌套元素的类型,acl表示name内容为acl名称,ip表示name填充的是ip|string|a1|
|aclid|当type="acl"时有意义,表示acl的id|string|"547697602773778433"|

### 1.4. 修改ACL
- 接口信息  

|接口描述|获取视图信息|
|-|-|
|请求地址|/apis/linkingthing.com/example/v1/acls/:acl_id|
|请求方式|HTTP/1.1 POST|
|请求格式|{"name":"acl112","list":[{"name":"10.0.0.21","aclid":"1","type":"ip"},{"name":"a2","aclid":"548216738318483457","type":"acl"}]}|
|返回格式|JSON|

- 请求参数意义

|参数名称|是否必填|数据类型|备注|
| - |-|-|-|
|第一个name|是|string|表示创建的acl的名称|
|list中的name|是|string|表示创建的元素的名称,当type为acl时,name填充选择的嵌套的acl名称|
|list中的name|是|string|表示创建的元素的名称,当type为ip时,name填充客户输入的ip值|
|list中的type|是|string|表示嵌套的元素的类型,只有acl和ip两种|

- 请求示例

|请求内容|http://10.0.0.19:8081/apis/linkingthing.com/example/v1/acls/548260628901855233|
|-|-|
|请求报文体|{"name":"acl112","list":[{"name":"a1","aclid":"547697602773778433","type":"acl"},{"name":"10.0.0.1","aclid":"1","type":"ip"}]}|
|响应内容|如下引用|

```
{
	"id": "548260628901855233",
	"type": "acl",
	"links": {
		"collection": "/apis/linkingthing.com/example/v1/acls",
		"remove": "/apis/linkingthing.com/example/v1/acls/548260628901855233",
		"self": "/apis/linkingthing.com/example/v1/acls/548260628901855233",
		"update": "/apis/linkingthing.com/example/v1/acls/548260628901855233"
	},
	"creationTimestamp": null,
	"deletionTimestamp": null,
	"name": "acl112",
	"list": [{
		"name": "10.0.0.21",
		"aclid": "1",
		"type": "ip"
	}, {
		"name": "a2",
		"aclid": "548216738318483457",
		"type": "acl"
	}]
}
```
|JSON元素|表示意义|参数类型|参数值举例|
|- | -|-|-|
|{"name": "acl112"}|acl名称|string|acl112|
|list中的{"name": "a1"}|嵌套的acl名称|string|a1|
|"list":[]|表示嵌套的acl列表|数组|list|
|"type"|表示嵌套元素的类型,acl表示name内容为acl名称,ip表示name填充的是ip|string|a1|
|aclid|当type="acl"时有意义,表示acl的id|string|"547697602773778433"|

### 1.5. 删除ACL
- 接口信息  

|接口描述|获取视图信息|
|-|-|
|请求地址|/apis/linkingthing.com/example/v1/acls|
|请求方式|HTTP/1.1 POST|
|请求格式|{"name":"acl112","list":[{"name":"a1","aclid":"547697602773778433","type":"acl"},{"name":"10.0.0.1","aclid":"1","type":"ip"}]}|
|返回格式|JSON|

- 请求参数意义

|参数名称|是否必填|数据类型|备注|
| - |-|-|-|
|第一个name|是|string|表示创建的acl的名称|
|list中的name|是|string|表示创建的元素的名称,当type为acl时,name填充选择的嵌套的acl名称|
|list中的name|是|string|表示创建的元素的名称,当type为ip时,name填充客户输入的ip值|
|list中的type|是|string|表示嵌套的元素的类型,只有acl和ip两种|

- 请求示例

|请求内容|http://10.0.0.19:8081/apis/linkingthing.com/example/v1/acls|
|-|-|
|请求报文体|{"name":"acl112","list":[{"name":"a1","aclid":"547697602773778433","type":"acl"},{"name":"10.0.0.1","aclid":"1","type":"ip"}]}|
|响应内容|如下引用|

```
{
	"id": "548260628901855233",
	"type": "acl",
	"links": {
		"collection": "/apis/linkingthing.com/example/v1/acls",
		"remove": "/apis/linkingthing.com/example/v1/acls/548260628901855233",
		"self": "/apis/linkingthing.com/example/v1/acls/548260628901855233",
		"update": "/apis/linkingthing.com/example/v1/acls/548260628901855233"
	},
	"creationTimestamp": "2020-04-20T12:37:45Z",
	"deletionTimestamp": null,
	"name": "acl112",
	"list": [{
		"name": "a1",
		"aclid": "547697602773778433",
		"type": "acl"
	}, {
		"name": "10.0.0.1",
		"aclid": "1",
		"type": "ip"
	}]
}
```
|JSON元素|表示意义|参数类型|参数值举例|
|- | -|-|-|
|{"name": "acl112"}|acl名称|string|acl112|
|list中的{"name": "a1"}|嵌套的acl名称|string|a1|
|"list":[]|表示嵌套的acl列表|数组|list|
|"type"|表示嵌套元素的类型,acl表示name内容为acl名称,ip表示name填充的是ip|string|a1|
|aclid|当type="acl"时有意义,表示acl的id|string|"547697602773778433"|

-------------
## 2. 视图
### 2.1. 获取所有视图
- 接口信息  

|接口描述|获取视图信息|
|-|-|
|请求地址|/apis/linkingthing.com/example/v1/views|
|请求方式|HTTP/1.1 GET|
|返回格式|JSON|

- 请求参数意义

|参数名称|是否必填|数据类型|备注|
| - |-|-|-|
|无|

- 请求示例

|请求内容|http://10.0.0.19:8081/apis/linkingthing.com/example/v1/views|
|-|-|
|响应内容|如下引用|

```
{
	"type": "collection",
	"resourceType": "view",
	"links": {
		"self": "/apis/linkingthing.com/example/v1/views"
	},
	"data": [{
		"id": "548541154561130497",
		"type": "view",
		"links": {
			"collection": "/apis/linkingthing.com/example/v1/views",
			"dns64s": "/apis/linkingthing.com/example/v1/views/548541154561130497/dns64s",
			"redirections": "/apis/linkingthing.com/example/v1/views/548541154561130497/redirections",
			"remove": "/apis/linkingthing.com/example/v1/views/548541154561130497",
			"self": "/apis/linkingthing.com/example/v1/views/548541154561130497",
			"update": "/apis/linkingthing.com/example/v1/views/548541154561130497",
			"zones": "/apis/linkingthing.com/example/v1/views/548541154561130497/zones"
		},
		"creationTimestamp": "2020-04-21T12:24:35Z",
		"deletionTimestamp": null,
		"name": "view02",
		"priority": 1,
		"aclids": ["547697602773778433"],
		"acls": [{
			"id": "547697602773778433",
			"creationTimestamp": null,
			"deletionTimestamp": null,
			"name": "a1",
			"list": null
		}],
		"zonesize": 0,
		"localzonesize": 0,
		"nxdomainsize": 0,
		"dns64size": 0
	}, {
		"id": "547697640614494209",
		"type": "view",
		"links": {
			"collection": "/apis/linkingthing.com/example/v1/views",
			"dns64s": "/apis/linkingthing.com/example/v1/views/547697640614494209/dns64s",
			"redirections": "/apis/linkingthing.com/example/v1/views/547697640614494209/redirections",
			"remove": "/apis/linkingthing.com/example/v1/views/547697640614494209",
			"self": "/apis/linkingthing.com/example/v1/views/547697640614494209",
			"update": "/apis/linkingthing.com/example/v1/views/547697640614494209",
			"zones": "/apis/linkingthing.com/example/v1/views/547697640614494209/zones"
		},
		"creationTimestamp": "2020-04-18T12:54:15Z",
		"deletionTimestamp": null,
		"name": "v1",
		"priority": 2,
		"aclids": ["547697602773778433"],
		"acls": [{
			"id": "547697602773778433",
			"creationTimestamp": null,
			"deletionTimestamp": null,
			"name": "a1",
			"list": null
		}],
		"zonesize": 1,
		"localzonesize": 1,
		"nxdomainsize": 0,
		"dns64size": 0
	}, {
		"id": "1000000",
		"type": "view",
		"links": {
			"collection": "/apis/linkingthing.com/example/v1/views",
			"dns64s": "/apis/linkingthing.com/example/v1/views/1000000/dns64s",
			"redirections": "/apis/linkingthing.com/example/v1/views/1000000/redirections",
			"remove": "/apis/linkingthing.com/example/v1/views/1000000",
			"self": "/apis/linkingthing.com/example/v1/views/1000000",
			"update": "/apis/linkingthing.com/example/v1/views/1000000",
			"zones": "/apis/linkingthing.com/example/v1/views/1000000/zones"
		},
		"creationTimestamp": "2020-04-18T12:53:04Z",
		"deletionTimestamp": null,
		"name": "default",
		"priority": 3,
		"aclids": ["1"],
		"acls": [{
			"id": "1",
			"creationTimestamp": null,
			"deletionTimestamp": null,
			"name": "any",
			"list": null
		}],
		"zonesize": 0,
		"localzonesize": 0,
		"nxdomainsize": 0,
		"dns64size": 0
	}]
}
```
|JSON元素|表示意义|参数类型|参数值举例|
|- | -|-|-|
|{"name"}|视图名称|string|v1|
|"priority"]|表示视图的优先级别|int|1|
|"aclids"|表示选中的acl的id|string|"547697602773778433"|
|"acls"|所有的acl内容|acl对象数组||
|"zonesize"|区的个数|int|0|
|"localzonesize"|localzone的个数|int|0|
|"nxdomainsize"|nxdomain的个数|int|0|
|"dns64size"|dns64的个数|int|0|

### 2.2. 获取一个视图
- 接口信息  

|接口描述|获取视图信息|
|-|-|
|请求地址|/apis/linkingthing.com/example/v1/views/:view_id|
|请求方式|HTTP/1.1 GET|
|返回格式|JSON|

- 请求参数意义

|参数名称|是否必填|数据类型|备注|
| - |-|-|-|
|无|

- 请求示例

|请求内容|http://10.0.0.19:8081/apis/linkingthing.com/example/v1/views/547697640614494209|
|-|-|
|响应内容|如下引用|

```
{
	"id": "547697640614494209",
	"type": "view",
	"links": {
		"collection": "/apis/linkingthing.com/example/v1/views",
		"dns64s": "/apis/linkingthing.com/example/v1/views/547697640614494209/dns64s",
		"redirections": "/apis/linkingthing.com/example/v1/views/547697640614494209/redirections",
		"remove": "/apis/linkingthing.com/example/v1/views/547697640614494209",
		"self": "/apis/linkingthing.com/example/v1/views/547697640614494209",
		"update": "/apis/linkingthing.com/example/v1/views/547697640614494209",
		"zones": "/apis/linkingthing.com/example/v1/views/547697640614494209/zones"
	},
	"creationTimestamp": "2020-04-18T12:54:15Z",
	"deletionTimestamp": null,
	"name": "v1",
	"priority": 2,
	"aclids": ["547697602773778433"],
	"acls": [{
		"id": "547697602773778433",
		"creationTimestamp": null,
		"deletionTimestamp": null,
		"name": "a1",
		"list": null
	}],
	"zonesize": 1,
	"localzone": 1,
	"nxdomainsize": 0,
	"dns64size": 0
}
```
|JSON元素|表示意义|参数类型|参数值举例|
|- | -|-|-|
|{"name"}|视图名称|string|v1|
|"priority"]|表示视图的优先级别|int|1|
|"aclids"|表示选中的acl的id|string|"547697602773778433"|
|"acls"|所有的acl内容|acl对象数组||
|"zonesize"|区的个数|int|0|
|"localzonesize"|localzone的个数|int|0|
|"nxdomainsize"|nxdomain的个数|int|0|
|"dns64size"|dns64的个数|int|0|

### 2.3. 新建一个视图
- 接口信息  

|接口描述|新建一个视图|
|-|-|
|请求地址|/apis/linkingthing.com/example/v1/views|
|请求方式|HTTP/1.1 POST|
|请求格式|{"name":"view01","aclids":["548216738318483457"],"priority":1}|
|返回格式|JSON|

- 请求参数意义

|参数名称|是否必填|数据类型|备注|
| - |-|-|-|
|name|是|string|表示创建的视图的名称|
|aclids|是|数组|视图包含的acl|
|priority|是|int|视图的优先级别|


- 请求示例

|请求内容|http://10.0.0.19:8081/apis/linkingthing.com/example/v1/views|
|-|-|
|请求报文体|{"name":"view01","aclids":["548216738318483457"],"priority":1}|
|响应内容|如下引用|

```
{
	"id": "548545868657393665",
	"type": "view",
	"links": {
		"collection": "/apis/linkingthing.com/example/v1/views",
		"dns64s": "/apis/linkingthing.com/example/v1/views/548545868657393665/dns64s",
		"redirections": "/apis/linkingthing.com/example/v1/views/548545868657393665/redirections",
		"remove": "/apis/linkingthing.com/example/v1/views/548545868657393665",
		"self": "/apis/linkingthing.com/example/v1/views/548545868657393665",
		"update": "/apis/linkingthing.com/example/v1/views/548545868657393665",
		"zones": "/apis/linkingthing.com/example/v1/views/548545868657393665/zones"
	},
	"creationTimestamp": "2020-04-21T12:48:34Z",
	"deletionTimestamp": null,
	"name": "view01",
	"priority": 1,
	"aclids": ["548216738318483457"],
	"acls": null,
	"zonesize": 0,
	"localzone": 0,
	"nxdomainsize": 0,
	"dns64size": 0
}
```
|JSON元素|表示意义|参数类型|参数值举例|
|- | -|-|-|
|{"name"}|视图名称|string|v1|
|"priority"]|表示视图的优先级别|int|1|
|"aclids"|表示选中的acl的id|string|"547697602773778433"|
|"acls"|所有的acl内容|acl对象数组||
|"zonesize"|区的个数|int|0|
|"localzonesize"|localzone的个数|int|0|
|"nxdomainsize"|nxdomain的个数|int|0|
|"dns64size"|dns64的个数|int|0|

### 2.4. 修改视图
- 接口信息  

|接口描述|修改视图信息|
|-|-|
|请求地址|/apis/linkingthing.com/example/v1/views/:view_id|
|请求方式|HTTP/1.1 PUT|
|请求格式|{"name":"view02","aclids":["548216738318483457"],"priority":1}|
|返回格式|JSON|

- 请求参数意义

|参数名称|是否必填|数据类型|备注|
| - |-|-|-|
|第一个name|是|string|表示创建的acl的名称|
|name|是|string|视图的名称|
|aclids|是|string数组|表示使用的acl的id列表|
|priority|是|int|表示优先级|

- 请求示例

|请求内容|http://10.0.0.19:8081/apis/linkingthing.com/example/v1/views/548541154561130497|
|-|-|
|请求报文体|{"name":"view02","aclids":["548216738318483457"],"priority":1}|
|响应内容|如下引用|

```
{
	"id": "548541154561130497",
	"type": "view",
	"links": {
		"collection": "/apis/linkingthing.com/example/v1/views",
		"dns64s": "/apis/linkingthing.com/example/v1/views/548541154561130497/dns64s",
		"redirections": "/apis/linkingthing.com/example/v1/views/548541154561130497/redirections",
		"remove": "/apis/linkingthing.com/example/v1/views/548541154561130497",
		"self": "/apis/linkingthing.com/example/v1/views/548541154561130497",
		"update": "/apis/linkingthing.com/example/v1/views/548541154561130497",
		"zones": "/apis/linkingthing.com/example/v1/views/548541154561130497/zones"
	},
	"creationTimestamp": null,
	"deletionTimestamp": null,
	"name": "view02",
	"priority": 1,
	"aclids": ["548216738318483457"],
	"acls": null,
	"zonesize": 0,
	"localzonesize": 0,
	"nxdomainsize": 0,
	"dns64size": 0
}
```
|JSON元素|表示意义|参数类型|参数值举例|
|- | -|-|-|
|{"name"}|视图名称|string|view02|
|"priority"]|表示视图的优先级别|int|1|
|"aclids"|表示选中的acl的id|string|"548216738318483457"|
|"acls"|所有的acl内容|acl对象数组||
|"zonesize"|区的个数|int|0|
|"localzonesize"|localzone的个数|int|0|
|"nxdomainsize"|nxdomain的个数|int|0|
|"dns64size"|dns64的个数|int|0|

### 2.5. 删除视图
- 接口信息  

|接口描述|获取视图信息|
|-|-|
|请求地址|/apis/linkingthing.com/example/v1/views/:view_id|
|请求方式|HTTP/1.1 DELETE|
|请求报文|无|
|返回格式|JSON|

- 请求示例

|请求内容|http://10.0.0.19:8081/apis/linkingthing.com/example/v1/views/547697640614494209|
|-|-|
|响应内容|无|
-----------

## 3. 区
### 3.1. 获取所有区
- 接口信息  

|接口描述|获取视图信息|
|-|-|
|请求地址|/apis/linkingthing.com/example/v1/views/:view_id/zones|
|请求方式|HTTP/1.1 GET|
|返回格式|JSON|

- 请求参数意义

|参数名称|是否必填|数据类型|备注|
| - |-|-|-|
|无|

- 请求示例

|请求内容|http://10.0.0.19:8081/apis/linkingthing.com/example/v1/views/548545868657393665/zones|
|-|-|
|响应内容|如下引用|

```
{
	"type": "collection",
	"resourceType": "zone",
	"links": {
		"self": "/apis/linkingthing.com/example/v1/views/548545868657393665/zones"
	},
	"data": [{
		"id": "548697389362741249",
		"type": "zone",
		"links": {
			"collection": "/apis/linkingthing.com/example/v1/views/548545868657393665/zones",
			"remove": "/apis/linkingthing.com/example/v1/views/548545868657393665/zones/548697389362741249",
			"rrs": "/apis/linkingthing.com/example/v1/views/548545868657393665/zones/548697389362741249/rrs",
			"self": "/apis/linkingthing.com/example/v1/views/548545868657393665/zones/548697389362741249"
		},
		"creationTimestamp": "2020-04-22T01:39:14Z",
		"deletionTimestamp": null,
		"name": "baidu.com",
		"zonetype": "",
		"rrsize": 0,
		"forwardsize": 0
	}]
}
```
|JSON元素|表示意义|参数类型|参数值举例|
|- | -|-|-|
|{"name"}|区名称|string|baidu.com|
|"zonetype"]|表示区的类型,有master和forward两种,权威区使用master|string|master|
|"rrsize"|表示区下面资源的个数|int|0|
|"forwardsize"|forward区下转发服务器的个数|int|0|

### 3.2. 获取一个区
- 接口信息  

|接口描述|获取视图信息|
|-|-|
|请求地址|/apis/linkingthing.com/example/v1/views/:view_id/zones/:zone_id|
|请求方式|HTTP/1.1 GET|
|返回格式|JSON|

- 请求参数意义

|参数名称|是否必填|数据类型|备注|
| - |-|-|-|
|无|

- 请求示例

|请求内容|http://10.0.0.19:8081/apis/linkingthing.com/example/v1/views/548545868657393665/zones/548697389362741249|
|-|-|
|响应内容|如下引用|

```
{
	"id": "548697389362741249",
	"type": "zone",
	"links": {
		"collection": "/apis/linkingthing.com/example/v1/views/548545868657393665/zones",
		"remove": "/apis/linkingthing.com/example/v1/views/548545868657393665/zones/548697389362741249",
		"rrs": "/apis/linkingthing.com/example/v1/views/548545868657393665/zones/548697389362741249/rrs",
		"self": "/apis/linkingthing.com/example/v1/views/548545868657393665/zones/548697389362741249"
	},
	"creationTimestamp": "2020-04-22T01:39:14Z",
	"deletionTimestamp": null,
	"name": "baidu.com",
	"zonetype": "",
	"rrsize": 0,
	"forwardsize": 0
}
```
|JSON元素|表示意义|参数类型|参数值举例|
|- | -|-|-|
|{"name"}|区名称|string|baidu.com|
|"zonetype"]|表示区的类型,有master和forward两种,权威区使用master|string|master|
|"rrsize"|表示区下面资源的个数|int|0|
|"forwardsize"|forward区下转发服务器的个数|int|0|

### 3.3. 新建一个区
- 接口信息  

|接口描述|新建一个视图|
|-|-|
|请求地址|/apis/linkingthing.com/example/v1/views/:view_id/zones|
|请求方式|HTTP/1.1 POST|
|请求格式|{"name":"baidu.com","zonetype":"master"}|
|返回格式|JSON|

- 请求参数意义

|参数名称|是否必填|数据类型|备注|
| - |-|-|-|
|name|是|string|表示创建的区的名称|
|zonetype|是|字符串|表示区的类型,权威的区使用master|


- 请求示例

|请求内容|http://10.0.0.19:8081/apis/linkingthing.com/example/v1/views/548545868657393665/zones|
|-|-|
|请求报文体|{"name":"baidu.com","zonetype":"master"}|
|响应内容|如下引用|

```
{
	"id": "548697389362741249",
	"type": "zone",
	"links": {
		"collection": "/apis/linkingthing.com/example/v1/views/548545868657393665/zones",
		"remove": "/apis/linkingthing.com/example/v1/views/548545868657393665/zones/548697389362741249",
		"rrs": "/apis/linkingthing.com/example/v1/views/548545868657393665/zones/548697389362741249/rrs",
		"self": "/apis/linkingthing.com/example/v1/views/548545868657393665/zones/548697389362741249"
	},
	"creationTimestamp": "2020-04-22T01:39:14Z",
	"deletionTimestamp": null,
	"name": "baidu.com",
	"zonetype": "master",
	"rrsize": 0,
	"forwardsize": 0
}
```
|JSON元素|表示意义|参数类型|参数值举例|
|- | -|-|-|
|{"name"}|区名称|string|baidu.com|
|"zonetype"]|表示区的类型,有master和forward两种,权威区使用master|string|master|
|"rrsize"|表示区下面资源的个数|int|0|
|"forwardsize"|forward区下转发服务器的个数|int|0|


### 3.4. 删除区
- 接口信息  

|接口描述|获取视图信息|
|-|-|
|请求地址|/apis/linkingthing.com/example/v1/views/:view_id/zones/:zone_id|
|请求方式|HTTP/1.1 DELETE|
|请求报文|无|
|返回格式|JSON|

- 请求示例

|请求内容|http://10.0.0.19:8081/apis/linkingthing.com/example/v1/views/548545868657393665/zones/548697389362741249|
|-|-|
|响应内容|无|
-------

## 4. 资源记录
### 4.1. 获取所有资源记录
- 接口信息  

|接口描述|获取视图信息|
|-|-|
|请求地址|/apis/linkingthing.com/example/v1/views/:view_id/zones/:zone_id/rrs|
|请求方式|HTTP/1.1 GET|
|返回格式|JSON|

- 请求参数意义

|参数名称|是否必填|数据类型|备注|
| - |-|-|-|
|无|

- 请求示例

|请求内容|http://10.0.0.19:8081/apis/linkingthing.com/example/v1/views/548545868657393665/zones/548700984546033665/rrs|
|-|-|
|响应内容|如下引用|

```
{
	"type": "collection",
	"resourceType": "rr",
	"links": {
		"self": "/apis/linkingthing.com/example/v1/views/548545868657393665/zones/548700984546033665/rrs"
	},
	"data": [{
		"id": "548701306110836737",
		"links": {
			"collection": "/apis/linkingthing.com/example/v1/views/548545868657393665/zones/548700984546033665/rrs",
			"remove": "/apis/linkingthing.com/example/v1/views/548545868657393665/zones/548700984546033665/rrs/548701306110836737",
			"self": "/apis/linkingthing.com/example/v1/views/548545868657393665/zones/548700984546033665/rrs/548701306110836737",
			"update": "/apis/linkingthing.com/example/v1/views/548545868657393665/zones/548700984546033665/rrs/548701306110836737"
		},
		"creationTimestamp": "2020-04-22T01:59:09Z",
		"deletionTimestamp": null,
		"name": "mail",
		"type": "A",
		"ttl": 200,
		"value": "10.0.0.12"
	}, {
		"id": "548706012618620929",
		"links": {
			"collection": "/apis/linkingthing.com/example/v1/views/548545868657393665/zones/548700984546033665/rrs",
			"remove": "/apis/linkingthing.com/example/v1/views/548545868657393665/zones/548700984546033665/rrs/548706012618620929",
			"self": "/apis/linkingthing.com/example/v1/views/548545868657393665/zones/548700984546033665/rrs/548706012618620929",
			"update": "/apis/linkingthing.com/example/v1/views/548545868657393665/zones/548700984546033665/rrs/548706012618620929"
		},
		"creationTimestamp": "2020-04-22T02:23:06Z",
		"deletionTimestamp": null,
		"name": "mail",
		"type": "AAAA",
		"ttl": 200,
		"value": "240e:1122::1"
	}]
}
```
|JSON元素|表示意义|参数类型|参数值举例|
|- | -|-|-|
|name|是|string|表示创建的资源在区前是所有的标签名称,可以是多级,*或者@.*表示通配,@表示区本身|
|type|是|string|资源的类型,有A,AAAA,cname|
|ttl|是|int|资源的可缓存时间|
|value|是|string|资源的对应的值|

### 4.2. 获取一个rr
- 接口信息  

|接口描述|获取视图信息|
|-|-|
|请求地址|/apis/linkingthing.com/example/v1/views/:view_id/zones/:zone_id/rrs/:rr_id|
|请求方式|HTTP/1.1 GET|
|返回格式|JSON|

- 请求参数意义

|参数名称|是否必填|数据类型|备注|
| - |-|-|-|
|无|

- 请求示例

|请求内容|http://10.0.0.19:8081/apis/linkingthing.com/example/v1/views/548545868657393665/zones/548700984546033665/rrs/548706012618620929|
|-|-|
|响应内容|如下引用|

```
{
	"id": "548706012618620929",
	"links": {
		"collection": "/apis/linkingthing.com/example/v1/views/548545868657393665/zones/548700984546033665/rrs",
		"remove": "/apis/linkingthing.com/example/v1/views/548545868657393665/zones/548700984546033665/rrs/548706012618620929",
		"self": "/apis/linkingthing.com/example/v1/views/548545868657393665/zones/548700984546033665/rrs/548706012618620929",
		"update": "/apis/linkingthing.com/example/v1/views/548545868657393665/zones/548700984546033665/rrs/548706012618620929"
	},
	"creationTimestamp": "2020-04-22T02:23:06Z",
	"deletionTimestamp": null,
	"name": "mail",
	"type": "AAAA",
	"ttl": 200,
	"value": "240e:1122::1"
}
```
|JSON元素|表示意义|参数类型|参数值举例|
|- | -|-|-|
|name|是|string|表示创建的资源在区前是所有的标签名称,可以是多级,*或者@.*表示通配,@表示区本身|
|type|是|string|资源的类型,有A,AAAA,cname|
|ttl|是|int|资源的可缓存时间|
|value|是|string|资源的对应的值|

### 4.3. 新建一个rr
- 接口信息  

|接口描述|新建一个视图|
|-|-|
|请求地址|/apis/linkingthing.com/example/v1/views/:view_id/zones/:zone_id/rrs|
|请求方式|HTTP/1.1 POST|
|请求格式|{"name":"mail","type":"A","value":"10.0.0.12","ttl":200}|
|返回格式|JSON|

- 请求参数意义

|参数名称|是否必填|数据类型|备注|
| - |-|-|-|
|name|是|string|表示创建的资源在区前是所有的标签名称,可以是多级,*或者@.*表示通配,@表示区本身|
|type|是|string|资源的类型,有A,AAAA,cname|
|ttl|是|int|资源的可缓存时间|
|value|是|string|资源的对应的值|


- 请求示例

|请求内容|http://10.0.0.19:8081/apis/linkingthing.com/example/v1/views/548545868657393665/zones/548700984546033665/rrs|
|-|-|
|请求报文体|{"name":"mail","type":"AAAA","value":"240e:1122::1","ttl":200}|
|响应内容|如下引用|

```
{
	"id": "548706012618620929",
	"links": {
		"collection": "/apis/linkingthing.com/example/v1/views/548545868657393665/zones/548700984546033665/rrs",
		"remove": "/apis/linkingthing.com/example/v1/views/548545868657393665/zones/548700984546033665/rrs/548706012618620929",
		"self": "/apis/linkingthing.com/example/v1/views/548545868657393665/zones/548700984546033665/rrs/548706012618620929",
		"update": "/apis/linkingthing.com/example/v1/views/548545868657393665/zones/548700984546033665/rrs/548706012618620929"
	},
	"creationTimestamp": "2020-04-22T02:23:06Z",
	"deletionTimestamp": null,
	"name": "mail",
	"type": "AAAA",
	"ttl": 200,
	"value": "240e:1122::1"
}
```
|JSON元素|表示意义|参数类型|参数值举例|
|- | -|-|-|
|name|是|string|表示创建的资源在区前是所有的标签名称,可以是多级,*或者@.*表示通配,@表示区本身|
|type|是|string|资源的类型,有A,AAAA,cname|
|ttl|是|int|资源的可缓存时间|
|value|是|string|资源的对应的值|

### 4.4. 修改rr
- 接口信息  

|接口描述|修改视图信息|
|-|-|
|请求地址|/apis/linkingthing.com/example/v1/views/:view_id/zones/:zone_id/rrs/:rr_id|
|请求方式|HTTP/1.1 PUT|
|请求格式|{"name":"view02","aclids":["548216738318483457"],"priority":1}|
|返回格式|JSON|

- 请求参数意义

|参数名称|是否必填|数据类型|备注|
| - |-|-|-|
|name|是|string|表示创建的资源在区前是所有的标签名称,可以是多级,*或者@.*表示通配,@表示区本身|
|type|是|string|资源的类型,有A,AAAA,cname|
|ttl|是|int|资源的可缓存时间|
|value|是|string|资源的对应的值|

- 请求示例

|请求内容|http://10.0.0.19:8081/apis/linkingthing.com/example/v1/views/548545868657393665/zones/548700984546033665/rrs/548701306110836737|
|-|-|
|请求报文体|{"name":"mail","type":"A","value":"10.0.0.13","ttl":200}|
|响应内容|如下引用|

```
{
	"id": "548701306110836737",
	"links": {
		"collection": "/apis/linkingthing.com/example/v1/views/548545868657393665/zones/548700984546033665/rrs",
		"remove": "/apis/linkingthing.com/example/v1/views/548545868657393665/zones/548700984546033665/rrs/548701306110836737",
		"self": "/apis/linkingthing.com/example/v1/views/548545868657393665/zones/548700984546033665/rrs/548701306110836737",
		"update": "/apis/linkingthing.com/example/v1/views/548545868657393665/zones/548700984546033665/rrs/548701306110836737"
	},
	"creationTimestamp": "2020-04-22T01:59:09Z",
	"deletionTimestamp": null,
	"name": "mail",
	"type": "A",
	"ttl": 200,
	"value": "10.0.0.13"
}
```
|JSON元素|表示意义|参数类型|参数值举例|
|- | -|-|-|
|name|是|string|表示创建的资源在区前是所有的标签名称,可以是多级,*或者@.*表示通配,@表示区本身|
|type|是|string|资源的类型,有A,AAAA,cname|
|ttl|是|int|资源的可缓存时间|
|value|是|string|资源的对应的值|

### 4.5. 删除rr
- 接口信息  

|接口描述|获取视图信息|
|-|-|
|请求地址|/apis/linkingthing.com/example/v1/views/:view_id/zones/:zone_id/rrs/:rr_id|
|请求方式|HTTP/1.1 DELETE|
|请求报文|无|
|返回格式|JSON|

- 请求示例

|请求内容|http://10.0.0.19:8081/apis/linkingthing.com/example/v1/views/548545868657393665/zones/548700984546033665/rrs/548706012618620929|
|-|-|
|响应内容|无|

-------

## 5. 区转发
### 5.1. 视图展示
- 接口信息  

|接口描述|获取视图信息|
|-|-|
|请求地址|/apis/linkingthing.com/example/v1/views|
|请求方式|HTTP/1.1 GET|
|返回格式|JSON|

- 请求参数意义

|参数名称|是否必填|数据类型|备注|
| - |-|-|-|
|无|

- 请求示例

|请求内容|http://10.0.0.19:8081/apis/linkingthing.com/example/v1/views|
|-|-|
|响应内容|如下引用|

```
{
    "type": "collection",
    "resourceType": "view",
    "links": {
        "self": "/apis/linkingthing.com/example/v1/views"
    },
    "data": [
        {
            "id": "516794447518629889",
            "type": "view",
            "links": {
                "collection": "/apis/linkingthing.com/example/v1/views",
                "remove": "/apis/linkingthing.com/example/v1/views/516794447518629889",
                "self": "/apis/linkingthing.com/example/v1/views/516794447518629889",
                "update": "/apis/linkingthing.com/example/v1/views/516794447518629889",
                "zones": "/apis/linkingthing.com/example/v1/views/516794447518629889/zones"
            },
            "creationTimestamp": "2019-12-31T09:12:29Z",
            "name": "view1231_01",
            "priority": 6,
            "isused": 0,
            "aclids": [
                "514208360416477185",
                "516547798340304897"
            ],
            "acls": [
                {
                    "id": "514208360416477185",
                    "creationTimestamp": null,
                    "name": "hwl_1230_07",
                    "IP": null
                },
                {
                    "id": "516547798340304897",
                    "creationTimestamp": null,
                    "name": "hwl_1230_02",
                    "IP": null
                }
            ],
            "zonesize": 2
        }
    ]
}
```
界面元素|响应参数位置|参数类型|参数值举例|
- | -|-|-|
视图|{"data":[{"name": "view1231_01"}]}|string|view1231_01|
域名数量|{"data":[{"zonesize":2}]}|int|2|

### 5.2. 区信息获取  
- 接口信息  

|接口描述|获取视图信息|
|-|-|
|请求地址|/apis/linkingthing.com/example/v1/views/:view_id/zones?zonetype=forward|
|请求方式|HTTP/1.1 GET|
|返回格式|JSON|

- 请求参数意义

|参数名称|是否必填|数据类型|备注|
| - |-|-|-|
|无|

- 请求示例

|请求内容|http://10.0.0.19:8081/apis/linkingthing.com/example/v1/views/516794447518629889/zones?zonetype=forward|
|-|-|
|响应内容|如下引用|

```
{
	"type": "collection",
	"resourceType": "zone",
	"links": {
		"self": "/apis/linkingthing.com/example/v1/views/516794447518629889/zones"
	},
	"data": [{
		"id": "517359608067588097",
		"type": "zone",
		"links": {
			"collection": "/apis/linkingthing.com/example/v1/views/516794447518629889/zones",
			"remove": "/apis/linkingthing.com/example/v1/views/516794447518629889/zones/517359608067588097",
			"rrs": "/apis/linkingthing.com/example/v1/views/516794447518629889/zones/517359608067588097/rrs",
			"self": "/apis/linkingthing.com/example/v1/views/516794447518629889/zones/517359608067588097"
		},
		"creationTimestamp": null,
		"name": "zone1231_01",
		"isused": 0,
		"forwardsize": 0
	}, {
		"id": "517359681792376833",
		"type": "zone",
		"links": {
			"collection": "/apis/linkingthing.com/example/v1/views/516794447518629889/zones",
			"remove": "/apis/linkingthing.com/example/v1/views/516794447518629889/zones/517359681792376833",
			"rrs": "/apis/linkingthing.com/example/v1/views/516794447518629889/zones/517359681792376833/rrs",
			"self": "/apis/linkingthing.com/example/v1/views/516794447518629889/zones/517359681792376833"
		},
		"creationTimestamp": null,
		"name": "zone1231_02",
		"isused": 0,
		"forwardsize": 2
	}]
}
```
界面元素|响应参数位置|参数类型|参数值举例|
- | -|-|-|
区|{"data":[{"name": "zone1231_01"}]}|string|zone1231_01|
域名数量|{"data":[{forwardsize":2}]}|int|2|

### 5.3. 转发的区信息创建  
- 接口信息  

|接口描述|获取视图信息|
|-|-|
|请求地址|/apis/linkingthing.com/example/v1/views/:view_id/zones|
|请求方式|HTTP/1.1 POST|
|请求报文体|{"name":"qq.com","zonetype":"forward"}|
|返回格式|JSON|

- 请求参数意义

|参数名称|是否必填|数据类型|备注|
| - |-|-|-|
|name|是|string|区的名称|
|zonetype|是|string|必需填forward,表示转发类型的区|

- 请求示例

|请求内容|http://10.0.0.19:8081/apis/linkingthing.com/example/v1/views/542481403128414209/zones|
|-|-|
|请求报文体|{"name":"qq.com","zonetype":"forward"}|
|响应内容|如下引用|

```
{
	"id": "546733543530168321",
	"type": "zone",
	"links": {
		"collection": "/apis/linkingthing.com/example/v1/views/542481403128414209/zones",
		"remove": "/apis/linkingthing.com/example/v1/views/542481403128414209/zones/546733543530168321",
		"rrs": "/apis/linkingthing.com/example/v1/views/542481403128414209/zones/546733543530168321/rrs",
		"self": "/apis/linkingthing.com/example/v1/views/542481403128414209/zones/546733543530168321"
	},
	"creationTimestamp": "2020-04-15T03:10:36Z",
	"deletionTimestamp": null,
	"name": "qq.com",
	"zonetype": "forward",
	"rrsize": 0,
	"forwardsize": 0
}
```
界面元素|响应参数位置|参数类型|参数值举例|
- | -|-|-|
域名|{{"name": "qq.com"}}|string|qq.com|
转发地址数量|{{"rrsize":0}}|int|0|

### 5.4. 转发的区信息删除  
- 接口信息  

|接口描述|获取视图信息|
|-|-|
|请求地址|/apis/linkingthing.com/example/v1/views/:view_id/zones/:zone_id|
|请求方式|HTTP/1.1 DELETE|
|返回格式|JSON|

- 请求参数意义

|参数名称|是否必填|数据类型|备注|
| - |-|-|-|
|name|是|string|区的名称|
|zonetype|是|string|必需填forward,表示转发类型的区|

- 请求示例

|请求内容|http://10.0.0.19:8081/apis/linkingthing.com/example/v1/views/542481403128414209/zones|
|-|-|
|请求报文体|{"name":"qq.com","zonetype":"forward"}|
|响应内容|无|

界面元素|响应参数位置|参数类型|参数值举例|
- | -|-|-|
域名|{{"name": "qq.com"}}|string|qq.com|
转发地址数量|{{"rrsize":0}}|int|0|

### 5.5. 服务器地址,转发方式信息获取  
- 接口信息  

|接口描述|获取视图信息|
|-|-|
|请求地址|/apis/linkingthing.com/example/v1/views/:view_id/zones/:zone_id?action=forward|
|请求方式|HTTP/1.1 POST|
|表单内容|{"oper":"GET"}|
|返回格式||

- 请求参数意义

|参数名称|是否必填|数据类型|备注|
| - |-|-|-|
|oper|是|string|表示操作类型,GET表示获取|

- 请求示例

|请求内容|http://10.0.0.19:8081/apis/linkingthing.com/example/v1/views/516794447518629889/zones/517359608067588097?action=forward|
|-|-|
|表单内容|{"oper":"GET"}|
|响应内容|如下引用|

```
{"id":"0","creationTimestamp":null,"oper":"","type":"","ips":null}
或者
{"id":"519038924372606977","creationTimestamp":null,"oper":"","type":"only","ips":["10.0.0.19","10.0.0.22"]}
```
界面元素|响应参数位置|参数类型|参数值举例|
- | -|-|-|
服务器地址列表|{"ips":["10.0.0.19","10.0.0.22"]}|string|10.0.0.19,10.0.0.22|
转发方式|{"type":"only"}|string|only|

### 5.6. 服务器地址,转发方式信息修改  
- 接口信息  

|接口描述|获取视图信息|
|-|-|
|请求地址|/apis/linkingthing.com/example/v1/views/:view_id/zones/:zone_id?action=forward|
|请求方式|HTTP/1.1 POST|
|表单内容|{"oper":"MOD","type":"only","ips":["10.0.0.19", "10.0.0.22"]}|
|返回格式||

- 请求参数意义

|参数名称|是否必填|数据类型|备注|
| - |-|-|-|
|oper|是|string|表示操作类型,MOD表示修改|
|type|是|string|表示转发类型,只有only或者first|
|ips|是|string数组|表示服务器地址列表,可以是ipv4也可以是ipv6地址|

- 请求示例

|请求内容|http://10.0.0.19:8081/apis/linkingthing.com/example/v1/views/516794447518629889/zones/517359608067588097?action=forward|
|-|-|
|表单内容|{"oper":"MOD","type":"only","ips":["10.0.0.19", "10.0.0.22"]}|
|响应内容|如下引用|

```
{"creationTimestamp":null,"oper":"MOD","type":"only","ips":["10.0.0.19","10.0.0.22"]}
```
界面元素|响应参数位置|参数类型|参数值举例|
- | -|-|-|
服务器地址列表|{"ips":["10.0.0.19","10.0.0.22"]}|string|10.0.0.19,10.0.0.22|
转发方式|{"type":"only"}|string|only|

### 5.7. 服务器地址,转发方式信息删除
- 接口信息  

|接口描述|获取视图信息|
|-|-|
|请求地址|/apis/linkingthing.com/example/v1/views/:view_id/zones/:zone_id?action=forward|
|请求方式|HTTP/1.1 POST|
|表单内容|{"oper":"DEL"}|
|返回格式||

- 请求参数意义

|参数名称|是否必填|数据类型|备注|
| - |-|-|-|
|oper|是|string|表示操作类型,DEL表示删除|

- 请求示例

|请求内容|http://10.0.0.19:8081/apis/linkingthing.com/example/v1/views/516794447518629889/zones/517359608067588097?action=forward|
|-|-|
|表单内容|{"oper":"DEL"}|
|响应内容|如下引用|

```
"del success!"
```
界面元素|响应参数位置|参数类型|参数值举例|
- | -|-|-|
无|||

##  6. 重定向
###  6.1 视图展示
- 接口信息  

|接口描述|获取视图信息|
|-|-|
|请求地址|/apis/linkingthing.com/example/v1/views|
|请求方式|HTTP/1.1 GET|
|返回格式|JSON|

- 请求参数意义

|参数名称|是否必填|数据类型|备注|
| - |-|-|-|
|无|

- 请求示例

|请求内容|http://10.0.0.19:8081/apis/linkingthing.com/example/v1/views|
|-|-|
|响应内容|如下引用|

```
{
	"type": "collection",
	"resourceType": "view",
	"links": {
		"self": "/apis/linkingthing.com/example/v1/views"
	},
	"data": [{
		"id": "516794447518629889",
		"type": "view",
		"links": {
			"collection": "/apis/linkingthing.com/example/v1/views",
			"redirections": "/apis/linkingthing.com/example/v1/views/516794447518629889/redirections",
			"remove": "/apis/linkingthing.com/example/v1/views/516794447518629889",
			"self": "/apis/linkingthing.com/example/v1/views/516794447518629889",
			"update": "/apis/linkingthing.com/example/v1/views/516794447518629889",
			"zones": "/apis/linkingthing.com/example/v1/views/516794447518629889/zones"
		},
		"creationTimestamp": "2019-12-31T09:12:29Z",
		"name": "view1231_01",
		"priority": 8,
		"isused": 0,
		"aclids": ["514208360416477185", "516547798340304897"],
		"acls": [{
			"id": "514208360416477185",
			"creationTimestamp": null,
			"name": "hwl_1230_07",
			"IP": null
		}, {
			"id": "516547798340304897",
			"creationTimestamp": null,
			"name": "hwl_1230_02",
			"IP": null
		}],
		"zonesize": 2,
		"localzonesize": 2,
		"nxdomainsize": 0
	}, {
		"id": "517374817670234113",
		"type": "view",
		"links": {
			"collection": "/apis/linkingthing.com/example/v1/views",
			"redirections": "/apis/linkingthing.com/example/v1/views/517374817670234113/redirections",
			"remove": "/apis/linkingthing.com/example/v1/views/517374817670234113",
			"self": "/apis/linkingthing.com/example/v1/views/517374817670234113",
			"update": "/apis/linkingthing.com/example/v1/views/517374817670234113",
			"zones": "/apis/linkingthing.com/example/v1/views/517374817670234113/zones"
		},
		"creationTimestamp": "2020-01-02T10:24:24Z",
		"name": "view_internal",
		"priority": 7,
		"isused": 0,
		"aclids": ["514208360416477185"],
		"acls": [{
			"id": "514208360416477185",
			"creationTimestamp": null,
			"name": "hwl_1230_07",
			"IP": null
		}],
		"zonesize": 0,
		"localzonesize": 0,
		"nxdomainsize": 0
	}]
}
```
界面元素|响应参数位置|参数类型|参数值举例|
- | -|-|-|
视图|{"data":[{"name": "view1231_01"}]}|string|view1231_01|
重定向配置数量|{"data":[{"localzonesize":2}]}|int|2|
NXDOMAIN重定向配置数量|{"data":[{"nxdomainsize":2}]}|int|2|

###  6.2 第二页查询
- 接口信息  

|接口描述|获取页面信息|
|-|-|
|请求地址|/apis/linkingthing.com/example/v1/views/:view_id/redirections|
|请求方式|HTTP/1.1 GET|
|返回格式|JSON|

- 请求参数意义

|参数名称|是否必填|数据类型|备注|
| - |-|-|-|
|无|

- 请求示例

|请求内容|http://10.0.0.19:8081/apis/linkingthing.com/example/v1/views/516794447518629889/redirections|
|-|-|
|响应内容|如下引用|

```
{
	"type": "collection",
	"resourceType": "redirection",
	"links": {
		"self": "/apis/linkingthing.com/example/v1/views/516794447518629889/redirections"
	},
	"data": [{
		"id": "519383672805851137",
		"type": "redirection",
		"links": {
			"collection": "/apis/linkingthing.com/example/v1/views/516794447518629889/redirections",
			"remove": "/apis/linkingthing.com/example/v1/views/516794447518629889/redirections/519383672805851137",
			"self": "/apis/linkingthing.com/example/v1/views/516794447518629889/redirections/519383672805851137",
			"update": "/apis/linkingthing.com/example/v1/views/516794447518629889/redirections/519383672805851137"
		},
		"creationTimestamp": null,
		"name": "www.baidu.com",
		"ttl": 200,
		"datatype": "A",
		"redirecttype": "localzone",
		"value": "10.0.0.1"
	}, {
		"id": "519384560842113025",
		"type": "redirection",
		"links": {
			"collection": "/apis/linkingthing.com/example/v1/views/516794447518629889/redirections",
			"remove": "/apis/linkingthing.com/example/v1/views/516794447518629889/redirections/519384560842113025",
			"self": "/apis/linkingthing.com/example/v1/views/516794447518629889/redirections/519384560842113025",
			"update": "/apis/linkingthing.com/example/v1/views/516794447518629889/redirections/519384560842113025"
		},
		"creationTimestamp": null,
		"name": "www.baidu.com",
		"ttl": 200,
		"datatype": "A",
		"redirecttype": "localzone",
		"value": "10.0.0.1"
	}]
}
```
界面元素|响应参数位置|参数类型|参数值举例|说明|
- | -|-|-|-|
域名|{"data":[{"name": "www.baidu.com"}]}|string|www.baidu.com|
TTL|{"data":[{"ttl": 200}]}|int|200|
记录类型|{"data":[{"datatype": "A"}]}|string|A|
记录值|{"data":[{"value": "10.0.0.1"}]}|string|10.0.0.1|
重定向方式|{"data":[{"redirecttype": "localzone"}]}|string|localzone|重定向方式有两种,为localzone和redirect|

###  6.3 第二页新建
- 接口信息  

|接口描述|新建一条记录|
|-|-|
|请求地址|/apis/linkingthing.com/example/v1/views/:view_id/redirections|
|请求方式|HTTP/1.1 POST|
|表单内容|{"name":"www.baidu.com","ttl":200,"datatype":"A","redirecttype":"localzone","value":"10.0.0.1"}|
|返回格式|JSON|

- 请求参数意义

|参数名称|是否必填|数据类型|备注|
| - |-|-|-|
|name|是|string|域名|
|ttl|是|string|TTL|
|datatype|是|string|只能填A\|AAAA\|CNAME,其他后续补充|
|redirecttype|是|string|只能填localzone或者redirect|
|value|是|string|ipv4地址或者ipv6地址|

- 请求示例

|请求内容|http://10.0.0.19:8081/apis/linkingthing.com/example/v1/views/516794447518629889/redirections|
|-|-|
|表单内容|{"name":"www.baidu.com","ttl":200,"datatype":"A","redirecttype":"localzone","value":"10.0.0.1"}|
|响应内容|如下引用|

```
{
	"type": "collection",
	"resourceType": "redirection",
	"links": {
		"self": "/apis/linkingthing.com/example/v1/views/516794447518629889/redirections"
	},
	"data": [{
		"id": "519384560842113025",
		"type": "redirection",
		"links": {
			"collection": "/apis/linkingthing.com/example/v1/views/516794447518629889/redirections",
			"remove": "/apis/linkingthing.com/example/v1/views/516794447518629889/redirections/519384560842113025",
			"self": "/apis/linkingthing.com/example/v1/views/516794447518629889/redirections/519384560842113025",
			"update": "/apis/linkingthing.com/example/v1/views/516794447518629889/redirections/519384560842113025"
		},
		"creationTimestamp": null,
		"name": "www.baidu.com",
		"ttl": 200,
		"datatype": "A",
		"redirecttype": "localzone",
		"value": "10.0.0.1"
	}, {
		"id": "519590500841455617",
		"type": "redirection",
		"links": {
			"collection": "/apis/linkingthing.com/example/v1/views/516794447518629889/redirections",
			"remove": "/apis/linkingthing.com/example/v1/views/516794447518629889/redirections/519590500841455617",
			"self": "/apis/linkingthing.com/example/v1/views/516794447518629889/redirections/519590500841455617",
			"update": "/apis/linkingthing.com/example/v1/views/516794447518629889/redirections/519590500841455617"
		},
		"creationTimestamp": null,
		"name": "ff77",
		"ttl": 10,
		"datatype": "AAAA",
		"redirecttype": "localzone",
		"value": "1.2.3.4"
	}]
}
```
界面元素|响应参数位置|参数类型|参数值举例|
- | -|-|-|
域名|{"data":[{"name": "www.baidu.com"}]}|string|www.baidu.com|
TTL|{"data":[{"ttl": 200}]}|int|200|
记录类型|{"data":[{"datatype": "A"}]}|string|A|
记录值|{"data":[{"value": "10.0.0.1"}]}|string|10.0.0.1|
重定向方式|{"data":[{"redirecttype": "localzone"}]}|string|localzone|

###  6.4 第二页删除
- 接口信息  

|接口描述|删除一条记录|
|-|-|
|请求地址|/apis/linkingthing.com/example/v1/views/:view_id/redirections/:redirection_id|
|请求方式|HTTP/1.1 DELETE|
|返回格式|JSON|

- 请求参数意义

|参数名称|是否必填|数据类型|备注|
| - |-|-|-|
|无|


- 请求示例

|请求内容|http://10.0.0.19:8081/apis/linkingthing.com/example/v1/views/516794447518629889/redirections/519383672805851137|
|-|-|
|响应内容|无|

界面元素|响应参数位置|参数类型|参数值举例|
- | -|-|-|
无|

###  6.5 第二页修改
- 接口信息  

|接口描述|新建一条记录|
|-|-|
|请求地址|/apis/linkingthing.com/example/v1/views/:view_id/redirections/:redirection_id|
|请求方式|HTTP/1.1 PUT|
|表单内容|{"name":"www.baidu.com","datatype":"AAAA","value":"1.2.3.4","ttl":10,"redirecttype":"localzone"}|
|返回格式|JSON|

- 请求参数意义

|参数名称|是否必填|数据类型|备注|
| - |-|-|-|
|name|是|string|域名|
|ttl|是|string|TTL|
|datatype|是|string|只能填A\|AAAA\|CNAME,其他后续补充|
|redirecttype|是|string|只能填localzone或者nxdomain|
|value|是|string|ipv4地址或者ipv6地址|

- 请求示例

|请求内容|http://10.0.0.19:8081/apis/linkingthing.com/example/v1/views/516794447518629889/redirections/519590500841455617|
|-|-|
|表单内容|{"name":"www.baidu.com","datatype":"AAAA","value":"1.2.3.4","ttl":10,"redirecttype":"localzone"}|
|响应内容|如下引用|

```
{
	"id": "519590500841455617",
	"type": "redirection",
	"links": {
		"collection": "/apis/linkingthing.com/example/v1/views/516794447518629889/redirections",
		"remove": "/apis/linkingthing.com/example/v1/views/516794447518629889/redirections/519590500841455617",
		"self": "/apis/linkingthing.com/example/v1/views/516794447518629889/redirections/519590500841455617",
		"update": "/apis/linkingthing.com/example/v1/views/516794447518629889/redirections/519590500841455617"
	},
	"creationTimestamp": null,
	"name": "www.baidu.com",
	"ttl": 10,
	"datatype": "AAAA",
	"redirecttype": "localzone",
	"value": "1.2.3.4"
}
```
界面元素|响应参数位置|参数类型|参数值举例|
- | -|-|-|
域名|{"data":[{"name": "www.baidu.com"}]}|string|www.baidu.com|
TTL|{"data":[{"ttl": 10}]}|int|10|
记录类型|{"data":[{"datatype": "AAAAA"}]}|string|AAAA|
记录值|{"data":[{"value": "1.2.3.4"}]}|string|1.2.3.4|
重定向方式|{"data":[{"redirecttype": "localzone"}]}|string|localzone|


##  7. 递归管理->4A地址合成
###  7.1 视图展示
- 接口信息  

|接口描述|获取视图信息|
|-|-|
|请求地址|/apis/linkingthing.com/example/v1/views|
|请求方式|HTTP/1.1 GET|
|返回格式|JSON|

- 请求参数意义

|参数名称|是否必填|数据类型|备注|
| - |-|-|-|
|无|

- 请求示例

|请求内容|http://10.0.0.19:8081/apis/linkingthing.com/example/v1/views|
|-|-|
|响应内容|如下引用|

```
{
	"type": "collection",
	"resourceType": "view",
	"links": {
		"self": "/apis/linkingthing.com/example/v1/views"
	},
	"data": [{
		"id": "1",
		"type": "view",
		"links": {
			"collection": "/apis/linkingthing.com/example/v1/views",
			"dns64s": "/apis/linkingthing.com/example/v1/views/1/dns64s",
			"redirections": "/apis/linkingthing.com/example/v1/views/1/redirections",
			"remove": "/apis/linkingthing.com/example/v1/views/1",
			"self": "/apis/linkingthing.com/example/v1/views/1",
			"update": "/apis/linkingthing.com/example/v1/views/1",
			"zones": "/apis/linkingthing.com/example/v1/views/1/zones"
		},
		"creationTimestamp": "2020-01-13T03:15:30Z",
		"name": "default",
		"priority": 9,
		"isused": 1,
		"aclids": ["1"],
		"acls": [{
			"id": "1",
			"creationTimestamp": null,
			"name": "any",
			"IP": null
		}],
		"zonesize": 0,
		"localzonesize": 0,
		"nxdomainsize": 0,
		"dns64size": 0
	}, {
		"id": "516794447518629889",
		"type": "view",
		"links": {
			"collection": "/apis/linkingthing.com/example/v1/views",
			"dns64s": "/apis/linkingthing.com/example/v1/views/516794447518629889/dns64s",
			"redirections": "/apis/linkingthing.com/example/v1/views/516794447518629889/redirections",
			"remove": "/apis/linkingthing.com/example/v1/views/516794447518629889",
			"self": "/apis/linkingthing.com/example/v1/views/516794447518629889",
			"update": "/apis/linkingthing.com/example/v1/views/516794447518629889",
			"zones": "/apis/linkingthing.com/example/v1/views/516794447518629889/zones"
		},
		"creationTimestamp": "2019-12-31T09:12:29Z",
		"name": "view1231_01",
		"priority": 8,
		"isused": 0,
		"aclids": ["514208360416477185", "516547798340304897"],
		"acls": [{
			"id": "514208360416477185",
			"creationTimestamp": null,
			"name": "hwl_1230_07",
			"IP": null
		}, {
			"id": "516547798340304897",
			"creationTimestamp": null,
			"name": "hwl_1230_02",
			"IP": null
		}],
		"zonesize": 2,
		"localzonesize": 2,
		"nxdomainsize": 1,
		"dns64size": 0
	}]
}
```
界面元素|响应参数位置|参数类型|参数值举例|
- | -|-|-|
视图|{"data":[{"name": "view1231_01"}]}|string|view1231_01|
规则数量|{"data":[{"dns64size":0}]}|int|0|

###  7.2 第二页页面展示
- 接口信息  

|接口描述|获取信息|
|-|-|
|请求地址|/apis/linkingthing.com/example/v1/views/:view_id/dns64s|
|请求方式|HTTP/1.1 GET|
|返回格式|JSON|

- 请求参数意义

|参数名称|是否必填|数据类型|备注|
| - |-|-|-|
|无|

- 请求示例

|请求内容|http://10.0.0.19:8081/apis/linkingthing.com/example/v1/views/516794447518629889/dns64s|
|-|-|
|响应内容|如下引用|

```
{
	"type": "collection",
	"resourceType": "dns64",
	"links": {
		"self": "/apis/linkingthing.com/example/v1/views/516794447518629889/dns64s"
	},
	"data": [{
		"id": "526432953968230401",
		"type": "dns64",
		"links": {
			"collection": "/apis/linkingthing.com/example/v1/views/516794447518629889/dns64s",
			"remove": "/apis/linkingthing.com/example/v1/views/516794447518629889/dns64s/526432953968230401",
			"self": "/apis/linkingthing.com/example/v1/views/516794447518629889/dns64s/526432953968230401",
			"update": "/apis/linkingthing.com/example/v1/views/516794447518629889/dns64s/526432953968230401"
		},
		"creationTimestamp": null,
		"prefix": "24oe:bbaa::/96",
		"clientacl": "514208360416477185",
		"clientaclname": "acl_0114_1",
		"aaddress": "516547807624527873",
		"addressname": "acl_0114_3"
	}, {
		"id": "526433620144848897",
		"type": "dns64",
		"links": {
			"collection": "/apis/linkingthing.com/example/v1/views/516794447518629889/dns64s",
			"remove": "/apis/linkingthing.com/example/v1/views/516794447518629889/dns64s/526433620144848897",
			"self": "/apis/linkingthing.com/example/v1/views/516794447518629889/dns64s/526433620144848897",
			"update": "/apis/linkingthing.com/example/v1/views/516794447518629889/dns64s/526433620144848897"
		},
		"creationTimestamp": null,
		"prefix": "24oe:ccaa::/96",
		"clientacl": "516547819132321793",
		"clientaclname": "acl_0114_4",
		"aaddress": "526353410404548609",
		"addressname": "btest001"
	}]
}
```
界面元素|响应参数位置|参数类型|参数值举例|
- | -|-|-|
前缀|{"data":[{"prefix": "24oe:eeff::/96"}]}|string|view1231_01|
客户IP地址|{"data":[{"whitename": "hwl_1230_07"}]}|string|hwl_1230_07|
客户IP黑名单|{"data":[{"blackname": "hwl_1230_02"}]}|string|hwl_1230_02|
目标IPv4地址|{"data":[{"addressname": "hwl_1230_03"}]}|string|hwl_1230_03|

###  7.3 第二页新建
- 接口信息  

|接口描述|新建一条记录|
|-|-|
|请求地址|/apis/linkingthing.com/example/v1/views/:view_id/dns64s|
|请求方式|HTTP/1.1 POST|
|表单内容|{"prefix":"24oe:bbaa::/96","clientacl":"514208360416477185","aaddress":"516547807624527873"}|
|返回格式|JSON|

- 请求参数意义

|参数名称|是否必填|数据类型|备注|
| - |-|-|-|
|prefix|是|string|前缀|
|clientacl|是|string|客户IP地址,来自于ACL的ID|
|aaddress|是|string|目标IPv4地址,来自于ACL的ID|

  - 依赖接口,ACL的ID获取接口
|接口描述|获取所有ACL记录|
|-|-|
|请求地址|/apis/linkingthing.com/example/v1/acls|
|请求方式|HTTP/1.1 GET|
|表单内容|无|
|返回格式|JSON,如下|
	
	````
	{
		"type": "collection",
		"resourceType": "acl",
		"links": {
			"self": "/apis/linkingthing.com/example/v1/acls"
		},
		"data": [{
			"id": "514208360416477185",
			"type": "acl",
			"links": {
				"collection": "/apis/linkingthing.com/example/v1/acls",
				"remove": "/apis/linkingthing.com/example/v1/acls/514208360416477185",
				"self": "/apis/linkingthing.com/example/v1/acls/514208360416477185",
				"update": "/apis/linkingthing.com/example/v1/acls/514208360416477185"
			},
			"creationTimestamp": "2019-12-22T05:58:58Z",
			"name": "hwl_1230_07",
			"IP": ["10.0.0.11", "10.0.0.12", "10.0.0.13"]
		}, {
			"id": "516547798340304897",
			"type": "acl",
			"links": {
				"collection": "/apis/linkingthing.com/example/v1/acls",
				"remove": "/apis/linkingthing.com/example/v1/acls/516547798340304897",
				"self": "/apis/linkingthing.com/example/v1/acls/516547798340304897",
				"update": "/apis/linkingthing.com/example/v1/acls/516547798340304897"
			},
			"creationTimestamp": "2019-12-30T12:17:57Z",
			"name": "hwl_1230_02",
			"IP": ["10.0.0.11", "10.0.0.12", "10.0.0.13"]
		}, {
			"id": "516547807624527873",
			"type": "acl",
			"links": {
				"collection": "/apis/linkingthing.com/example/v1/acls",
				"remove": "/apis/linkingthing.com/example/v1/acls/516547807624527873",
				"self": "/apis/linkingthing.com/example/v1/acls/516547807624527873",
				"update": "/apis/linkingthing.com/example/v1/acls/516547807624527873"
			},
			"creationTimestamp": "2019-12-30T12:18:00Z",
			"name": "hwl_1230_03",
			"IP": ["10.0.0.11", "10.0.0.12", "10.0.0.13"]
		}]
	}
	````

  - ACL的ID取值来自于{"data":[{"id": "516547807624527873"}]}

- 请求示例

|请求内容|http://10.0.0.19:8081/apis/linkingthing.com/example/v1/views/516794447518629889/dns64s|
|-|-|
|表单内容|{"prefix":"24oe:bbaa::/96","clientacl":"514208360416477185","aaddress":"516547807624527873"}|
|响应内容|如下引用|

```
{
	"id": "526432953968230401",
	"type": "dns64",
	"links": {
		"collection": "/apis/linkingthing.com/example/v1/views/516794447518629889/dns64s",
		"remove": "/apis/linkingthing.com/example/v1/views/516794447518629889/dns64s/526432953968230401",
		"self": "/apis/linkingthing.com/example/v1/views/516794447518629889/dns64s/526432953968230401",
		"update": "/apis/linkingthing.com/example/v1/views/516794447518629889/dns64s/526432953968230401"
	},
	"creationTimestamp": "2020-02-03T10:16:28Z",
	"prefix": "24oe:bbaa::/96",
	"clientacl": "514208360416477185",
	"clientaclname": "",
	"aaddress": "516547807624527873",
	"addressname": ""
}
```

###  7.4 第二页删除
- 接口信息  

|接口描述|删除一条记录|
|-|-|
|请求地址|/apis/linkingthing.com/example/v1/views/:view_id/dns64s/:dns64_id|
|请求方式|HTTP/1.1 DELETE|
|返回格式|JSON|

- 请求参数意义

|参数名称|是否必填|数据类型|备注|
| - |-|-|-|
|无|


- 请求示例

|请求内容|http://10.0.0.19:8081/apis/linkingthing.com/example/v1/views/516794447518629889/dns64s/520418989060194305|
|-|-|
|响应内容|无|

界面元素|响应参数位置|参数类型|参数值举例|
- | -|-|-|
无|

###  7.5 第二页修改
- 接口信息  

|接口描述|新建一条记录|
|-|-|
|请求地址|	/apis/linkingthing.com/example/v1/views/:view_id/dns64s/:dns64_id|
|请求方式|HTTP/1.1 PUT|
|表单内容|{"prefix":"24oe:cbba::/96","clientacl":"516547819132321793","aaddress":"526353410404548609"}|
|返回格式|JSON|

- 请求参数意义

|参数名称|是否必填|数据类型|备注|
| - |-|-|-|
|prefix|是|string|前缀|
|clientacl|是|string|客户IP地址,来自于ACL的ID|
|aaddress|是|string|目标IPv4地址,来自于ACL的ID|

- 请求示例

|请求内容|http://10.0.0.19:8081/apis/linkingthing.com/example/v1/views/516794447518629889/dns64s/526433620144848897|
|-|-|
|表单内容|{"prefix":"24oe:cbba::/96","clientacl":"516547819132321793","aaddress":"526353410404548609"}|
|响应内容|如下引用|

```
{
	"id": "526433620144848897",
	"type": "dns64",
	"links": {
		"collection": "/apis/linkingthing.com/example/v1/views/516794447518629889/dns64s",
		"remove": "/apis/linkingthing.com/example/v1/views/516794447518629889/dns64s/526433620144848897",
		"self": "/apis/linkingthing.com/example/v1/views/516794447518629889/dns64s/526433620144848897",
		"update": "/apis/linkingthing.com/example/v1/views/516794447518629889/dns64s/526433620144848897"
	},
	"creationTimestamp": null,
	"prefix": "24oe:cbba::/96",
	"clientacl": "516547819132321793",
	"clientaclname": "",
	"aaddress": "526353410404548609",
	"addressname": ""
}
```

##  8. 安全管理->地址黑名单
###  8.1 页面展示
- 接口信息  

|接口描述|获取信息|
|-|-|
|请求地址|/apis/linkingthing.com/example/v1/ipblackholes|
|请求方式|HTTP/1.1 GET|
|返回格式|JSON|

- 请求参数意义

|参数名称|是否必填|数据类型|备注|
| - |-|-|-|
|无|

- 请求示例

|请求内容|http://10.0.0.19:8081/apis/linkingthing.com/example/v1/ipblackholes|
|-|-|
|响应内容|如下引用|

```
{
	"type": "collection",
	"resourceType": "ipblackhole",
	"links": {
		"self": "/apis/linkingthing.com/example/v1/ipblackholes"
	},
	"data": [{
		"id": "516547819132321793",
		"type": "ipblackhole",
		"links": {
			"collection": "/apis/linkingthing.com/example/v1/ipblackholes",
			"remove": "/apis/linkingthing.com/example/v1/ipblackholes/516547819132321793",
			"self": "/apis/linkingthing.com/example/v1/ipblackholes/516547819132321793",
			"update": "/apis/linkingthing.com/example/v1/ipblackholes/516547819132321793"
		},
		"creationTimestamp": null,
		"aclid": "516547807624527873",
		"name": "hwl_0114_3"
	}, {
		"id": "516547845042929665",
		"type": "ipblackhole",
		"links": {
			"collection": "/apis/linkingthing.com/example/v1/ipblackholes",
			"remove": "/apis/linkingthing.com/example/v1/ipblackholes/516547845042929665",
			"self": "/apis/linkingthing.com/example/v1/ipblackholes/516547845042929665",
			"update": "/apis/linkingthing.com/example/v1/ipblackholes/516547845042929665"
		},
		"creationTimestamp": null,
		"aclid": "516547872703512577",
		"name": "hwl_1230_078"
	}]
}
```
界面元素|响应参数位置|参数类型|参数值举例|
- | -|-|-|
访问控制列表|{"data":[{"name":"any"}]}|string|any|

###  8.2 新建
- 接口信息  

|接口描述|新建一条记录|
|-|-|
|请求地址|/apis/linkingthing.com/example/v1/ipblackholes|
|请求方式|HTTP/1.1 POST|
|表单内容|{"aclid":"516547845042929665"}|
|返回格式|JSON|

- 请求参数意义

|参数名称|是否必填|数据类型|备注|
| - |-|-|-|
|aclids|是|string数组|客户IP黑名单,来自于ACL的ID|

  - 依赖接口,ACL的ID获取接口

|接口描述|获取所有ACL记录|
|-|-|
|请求地址|/apis/linkingthing.com/example/v1/acls|
|请求方式|HTTP/1.1 GET|
|表单内容|无|
|返回格式|JSON,如下|
	
````
	{
		"type": "collection",
		"resourceType": "acl",
		"links": {
			"self": "/apis/linkingthing.com/example/v1/acls"
		},
		"data": [{
			"id": "514208360416477185",
			"type": "acl",
			"links": {
				"collection": "/apis/linkingthing.com/example/v1/acls",
				"remove": "/apis/linkingthing.com/example/v1/acls/514208360416477185",
				"self": "/apis/linkingthing.com/example/v1/acls/514208360416477185",
				"update": "/apis/linkingthing.com/example/v1/acls/514208360416477185"
			},
			"creationTimestamp": "2019-12-22T05:58:58Z",
			"name": "hwl_1230_07",
			"IP": ["10.0.0.11", "10.0.0.12", "10.0.0.13"]
		}, {
			"id": "516547798340304897",
			"type": "acl",
			"links": {
				"collection": "/apis/linkingthing.com/example/v1/acls",
				"remove": "/apis/linkingthing.com/example/v1/acls/516547798340304897",
				"self": "/apis/linkingthing.com/example/v1/acls/516547798340304897",
				"update": "/apis/linkingthing.com/example/v1/acls/516547798340304897"
			},
			"creationTimestamp": "2019-12-30T12:17:57Z",
			"name": "hwl_1230_02",
			"IP": ["10.0.0.11", "10.0.0.12", "10.0.0.13"]
		}, {
			"id": "516547807624527873",
			"type": "acl",
			"links": {
				"collection": "/apis/linkingthing.com/example/v1/acls",
				"remove": "/apis/linkingthing.com/example/v1/acls/516547807624527873",
				"self": "/apis/linkingthing.com/example/v1/acls/516547807624527873",
				"update": "/apis/linkingthing.com/example/v1/acls/516547807624527873"
			},
			"creationTimestamp": "2019-12-30T12:18:00Z",
			"name": "hwl_1230_03",
			"IP": ["10.0.0.11", "10.0.0.12", "10.0.0.13"]
		}]
	}
````

  - ACL的ID取值来自于{"data":[{"id": "516547807624527873"}]}

- 请求示例

|请求内容|http://10.0.0.19:8081/apis/linkingthing.com/example/v1/ipblackholes|
|-|-|
|表单内容|{"aclid":"516547845042929665"}|
|响应内容|如下引用|

```
{
	"id": "521006795219009537",
	"type": "ipblackhole",
	"links": {
		"collection": "/apis/linkingthing.com/example/v1/ipblackholes",
		"remove": "/apis/linkingthing.com/example/v1/ipblackholes/521006795219009537",
		"self": "/apis/linkingthing.com/example/v1/ipblackholes/521006795219009537",
		"update": "/apis/linkingthing.com/example/v1/ipblackholes/521006795219009537"
	},
	"creationTimestamp": "2020-01-15T14:17:35+08:00",
	"aclid": "516547845042929665",
	"name": ""
}
```

###  8.3 删除
- 接口信息  

|接口描述|删除一条记录|
|-|-|
|请求地址|/apis/linkingthing.com/example/v1/ipblackholes/:ipblackhole_id|
|请求方式|HTTP/1.1 DELETE|
|返回格式|JSON|

- 请求参数意义

|参数名称|是否必填|数据类型|备注|
| - |-|-|-|
|无|


- 请求示例

|请求内容|http://10.0.0.19:8081/apis/linkingthing.com/example/v1/ipblackholes/516547845042929665|
|-|-|
|响应内容|无|

界面元素|响应参数位置|参数类型|参数值举例|
- | -|-|-|
无|

###  8.4 修改
- 接口信息  

|接口描述|修改一条记录|
|-|-|
|请求地址|/apis/linkingthing.com/example/v1/ipblackholes/:ipblackhole_id|
|请求方式|HTTP/1.1 PUT|
|表单内容|{"aclid":"516547872703512577"}|
|返回格式|JSON|

- 请求参数意义

|参数名称|是否必填|数据类型|备注|
| - |-|-|-|
|aclids|是|string数组|客户IP黑名单,来自于ACL的ID|

- 请求示例

|请求内容|http://10.0.0.19:8081/apis/linkingthing.com/example/v1/ipblackholes/520729840016523265|
|-|-|
|表单内容|{"aclid":"516547872703512577"}|
|响应内容|如下引用|

```
{
	"id": "516547845042929665",
	"type": "ipblackhole",
	"links": {
		"collection": "/apis/linkingthing.com/example/v1/ipblackholes",
		"remove": "/apis/linkingthing.com/example/v1/ipblackholes/516547845042929665",
		"self": "/apis/linkingthing.com/example/v1/ipblackholes/516547845042929665",
		"update": "/apis/linkingthing.com/example/v1/ipblackholes/516547845042929665"
	},
	"creationTimestamp": null,
	"aclid": "516547872703512577",
	"name": ""
}
```

##  9. 安全管理->并发控制
###  9.1 页面展示
- 接口信息  

|接口描述|获取信息|
|-|-|
|请求地址|/apis/linkingthing.com/example/v1/recursiveconcurrents|
|请求方式|HTTP/1.1 GET|
|返回格式|JSON|

- 请求参数意义

|参数名称|是否必填|数据类型|备注|
| - |-|-|-|
|无|

- 请求示例

|请求内容|http://10.0.0.19:8081/apis/linkingthing.com/example/v1/recursiveconcurrents|
|-|-|
|响应内容|如下引用|

```
{
	"type": "collection",
	"resourceType": "recursiveconcurrent",
	"links": {
		"self": "/apis/linkingthing.com/example/v1/recursiveconcurrents"
	},
	"data": [{
		"type": "recursiveconcurrent",
		"links": {
			"collection": "/apis/linkingthing.com/example/v1/recursiveconcurrents",
			"update": "/apis/linkingthing.com/example/v1/recursiveconcurrents"
		},
		"creationTimestamp": null,
		"recursiveClients": 1000,
		"fetchesPerZone": 0
	}]
}
```
界面元素|响应参数位置|参数类型|参数值举例|
- | -|-|-|
递归并发数|{"data":[{"recursiveClients":1000}]}|int|1000|
单一域递归并发数|{"data":[{"fetchesPerZone":0}]}|int|0|

###  9.2 修改
- 接口信息  

|接口描述|修改一条记录|
|-|-|
|请求地址|/apis/linkingthing.com/example/v1/recursiveconcurrents/con|
|请求方式|HTTP/1.1 PUT|
|表单内容|{"recursiveClients":2000,"fetchesPerZone":1000}|
|返回格式|JSON|

- 请求参数意义

|参数名称|是否必填|数据类型|备注|
| - |-|-|-|
|recursiveClients|是|int|递归并发数|
|fetchesPerZone|是|int|单一域递归并发数|

- 请求示例

|请求内容|http://10.0.0.19:8081/apis/linkingthing.com/example/v1/recursiveconcurrents/con|
|-|-|
|表单内容|{"recursiveClients":2000,"fetchesPerZone":1000}|
|响应内容|如下引用|

```
{
	"id": "con",
	"type": "recursiveconcurrent",
	"links": {
		"collection": "/apis/linkingthing.com/example/v1/recursiveconcurrents",
		"update": "/apis/linkingthing.com/example/v1/recursiveconcurrents/con"
	},
	"creationTimestamp": null,
	"recursiveClients": 2000,
	"fetchesPerZone": 1000
}
```

## 10. 校验码
### 10.1. 校验码图片展示
- 接口信息  

|接口描述|获取视图信息|
|-|-|
|请求地址|/apis/linkingthing.com/example/v1/getcheckimage|
|请求方式|HTTP/1.1 GET|
|返回格式|jpeg图片|

- 请求参数意义

|参数名称|是否必填|数据类型|备注|
| - |-|-|-|
|无|

- 请求示例

|请求内容|http://10.0.0.19:8081/apis/linkingthing.com/example/v1/getcheckimage|
|-|-|
|响应内容|图片，报文头如下带有一个时间戳|
|响应报文头的Checkvaluetoken: 1581910764145|1581910764145用于下次校验码校验时携带的token|

```
HTTP/1.1 200 OK
Checkvaluetoken: 1581910764145
Test: test
Date: Mon, 17 Feb 2020 03:39:24 GMT
Content-Type: image/jpeg
Connection: close
Content-Length: 13894
```


### 10.2. 校验码校验  
- 接口信息  

|接口描述|校验码校验|
|-|-|
|请求地址|/apis/linkingthing.com/example/v1/checkvalue?CheckValueToken=1581910764145&CheckValue=BYtP|
|请求方式|HTTP/1.1 GET|
|返回格式|text|

- 请求参数意义

|参数名称|是否必填|数据类型|备注|
| - |-|-|-|
|CheckValueToken|是|字符串|获取校验码图片时的时间戳token|
|CheckValue|是|字符串|图片中的值，不区分大小写|

- 请求示例

|请求内容|http://10.0.0.19:8081/apis/linkingthing.com/example/v1/checkvalue?CheckValueToken=1581910764145&CheckValue=BYtP|
|-|-|
|响应内容|check value success!|

## 11.界面登陆 
### 11.1 界面登陆  
- 接口信息  

|接口描述|获取视图信息|
|-|-|
|请求地址|/apis/linkingthing.com/example/v1/login|
|请求方式|HTTP/1.1 POST|
|表单内容|{"username":"admin","password":"admin"}|
|返回格式||

- 请求参数意义

|参数名称|是否必填|数据类型|备注|
| - |-|-|-|
|username|是|string|用户账号|
|password|是|string|账号密码|

- 请求示例

|请求内容|http://10.0.0.19:8081/apis/linkingthing.com/example/v1/login|
|-|-|
|表单内容|{"username":"admin","password":"admin"}|
|响应内容|如下引用|

```
{
	"code": 200,
	"expire": "2020-02-17T13:14:44+08:00",
	"token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJleHAiOjE1ODE5MTY0ODQsImlkIjoiYWRtaW4iLCJvcmlnX2lhdCI6MTU4MTkxMjg4NH0.9XEGOsDE5l8Z4YsHU58SKtL_GMXo5Wuuv4tNMZCWN-I"
}
```
- 报文体参数意义

|参数名称|数据类型|备注|
| - |-|-|-|
|expire|string|令牌超时时间|
|token|string|用户唯一标识串|

## 12.修改密码 
### 12.1 修改密码  
- 接口信息  

|接口描述|获取视图信息|
|-|-|
|请求地址|/apis/linkingthing.com/example/v1/changepwd|
|请求方式|HTTP/1.1 POST|
|表单内容|{"username":"admin","password":"admin"}|
|返回格式||

- 请求参数意义

|参数名称|是否必填|数据类型|备注|
| - |-|-|-|
|username|是|string|用户账号|
|password|是|string|账号密码|

- 请求示例

|请求内容|http://10.0.0.19:8081/apis/linkingthing.com/example/v1/changepwd|
|-|-|
|表单内容|{"username":"admin","password":"admin"}|
|成功响应内容|"change password success!"|

```
HTTP/1.1 200 OK
Content-Type: text/plain; charset=utf-8
Date: Tue, 18 Feb 2020 11:01:03 GMT
Content-Length: 24

change password success!
```
## 13.响应资源排序
### 13.1 响应资源排序查询
- 接口信息  

|接口描述|获取响应资源排序信息|
|-|-|
|请求地址| 	/apis/linkingthing.com/example/v1/sortlists/1|
|请求方式|HTTP/1.1 GET|
|表单内容|无|
|返回格式|JSON报文|

- 请求参数意义

|参数名称|是否必填|数据类型|备注|
| - |-|-|-|
|无|


- 请求示例

|请求内容|http://10.0.0.19:8081/apis/linkingthing.com/example/v1/sortlists/1|
|-|-|
|表单内容|无|
|成功响应内容|报文如下|

```
{
	"id": "1",
	"type": "sortlist",
	"links": {
		"remove": "/apis/linkingthing.com/example/v1/sortlists/1",
		"self": "/apis/linkingthing.com/example/v1/sortlists/1",
		"update": "/apis/linkingthing.com/example/v1/sortlists/1"
	},
	"creationTimestamp": null,
	"aclids": ["533775428170809345", "533130520387452929", "1"],
	"acls": [{
		"id": "533775428170809345",
		"creationTimestamp": null,
		"name": "aclsortlist",
		"IP": null
	}, {
		"id": "533130520387452929",
		"creationTimestamp": null,
		"name": "sortlistsecond",
		"IP": null
	}, {
		"id": "1",
		"creationTimestamp": null,
		"name": "any",
		"IP": null
	}]
}
```
- 报文体参数意义

|参数名称|数据类型|备注|
| - |-|-|-|
|aclids|string数组|acl的id|
|acls|acl数组|acl的对象数组,其中name用来界面展示|

###  13.2 新建
- 接口信息  

|接口描述|新建一条记录|
|-|-|
|请求地址| 	/apis/linkingthing.com/example/v1/sortlists|
|请求方式|HTTP/1.1 POST|
|表单内容|{"aclids":["533775428170809345","533130520387452929"]|
|返回格式|JSON|

- 请求参数意义

|参数名称|是否必填|数据类型|备注|
| - |-|-|-|
|aclids|是|string|aclid数组|

- 请求示例

|请求内容|http://10.0.0.19:8081/apis/linkingthing.com/example/v1/sortlists|
|-|-|
|表单内容|{"aclids":["533775428170809345","533130520387452929"]}|
|响应内容|如下引用|

```
{
	"id": "1",
	"type": "sortlist",
	"links": {
		"remove": "/apis/linkingthing.com/example/v1/sortlists/1",
		"self": "/apis/linkingthing.com/example/v1/sortlists/1",
		"update": "/apis/linkingthing.com/example/v1/sortlists/1"
	},
	"creationTimestamp": "2020-03-02T00:26:22+08:00",
	"aclids": ["533775428170809345", "533130520387452929"]
}
```

###  13.3 删除
- 接口信息  

|接口描述|删除一条记录|
|-|-|
|请求地址| 	/apis/linkingthing.com/example/v1/sortlists/1|
|请求方式|HTTP/1.1 DELETE|
|返回格式|JSON|

- 请求参数意义

|参数名称|是否必填|数据类型|备注|
| - |-|-|-|
|无|


- 请求示例

|请求内容|http://10.0.0.19:8081/apis/linkingthing.com/example/v1/sortlists/1|
|-|-|
|响应内容|无|

界面元素|响应参数位置|参数类型|参数值举例|
- | -|-|-|
无|

###  13.4 修改
- 接口信息  

|接口描述|新建一条记录|
|-|-|
|请求地址|/apis/linkingthing.com/example/v1/sortlists/1|
|请求方式|HTTP/1.1 PUT|
|表单内容|{"aclids":["533775428170809345","533130520387452929","1"]}|
|返回格式|JSON|

- 请求参数意义

|参数名称|是否必填|数据类型|备注|
| - |-|-|-|
|aclids|是|string|aclid数组|

- 请求示例

|请求内容|http://10.0.0.19:8081/apis/linkingthing.com/example/v1/sortlists/1|
|-|-|
|表单内容|{"aclids":["533775428170809345","533130520387452929","1"]}|
|响应内容|如下引用|

```
{
	"id": "1",
	"type": "sortlist",
	"links": {
		"remove": "/apis/linkingthing.com/example/v1/sortlists/1",
		"self": "/apis/linkingthing.com/example/v1/sortlists/1",
		"update": "/apis/linkingthing.com/example/v1/sortlists/1"
	},
	"creationTimestamp": null,
	"aclids": ["533775428170809345", "533130520387452929", "1"]
}
```

