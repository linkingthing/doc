# 所有接口

| 序号 | 方法   | 接口                                                         | 表单                                                         | 菜单                                   |描述|
| ---- | ------ | ------------------------------------------------------------ | ------------------------------------------------------------ | -------------------------------------- |----|
| 1.    | GET    | /apis/linkingthing.com/example/v1/acls                       | 无                                                           | 访问控制列表                           |
| 2.    | POST   | /apis/linkingthing.com/example/v1/acls                       | {"name":"acl1231_01",   "IP":["10.0.0.11","10.0.0.12","10.0.0.13"]} | 访问控制列表                           |
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
| 22   | GET    | /apis/linkingthing.com/example/v1/forwards                   | 无                                                           | 转发管理->默认转发                           |
| 23   | PUT    | /apis/linkingthing.com/example/v1/forwards/forward       | {"type":"only", "ip":["10.0.0.19","10.0.0.22"]}              | 转发管理->默认转发                           |
| 24   | DELETE | /apis/linkingthing.com/example/v1/forwards/forward       | 无                                                           | 转发管理->默认转发                           |
| 25   | GET    | /apis/linkingthing.com/example/v1/views                      | 无                                                           | 转发管理->区转发|视图获取|                               |
| 26   | GET    | /apis/linkingthing.com/example/v1/views/:view_id/zones       | 无                                                           | 转发管理->区转发           |区获取
| 27   | POST   | /apis/linkingthing.com/example/v1/views/:view_id/zones/:zone_id?action=forward       | {"oper":"GET"}       | 转发管理->区转发           |服务器地址列表和转发方式获取|
| 28   | POST   | /apis/linkingthing.com/example/v1/views/:view_id/zones/:zone_id?action=forward       | {"oper":"MOD","type":"only","ips":["10.0.0.19", "10.0.0.22"]}      | 转发管理->区转发           |服务器地址列表和转发方式修改,type固定为first或者only
| 29   | POST   | /apis/linkingthing.com/example/v1/views/:view_id/zones/:zone_id?action=forward       | {"oper":"DEL"}       | 转发管理->区转发           |服务器地址列表和转发方式删除
| 30   | GET    | /apis/linkingthing.com/example/v1/views/:view_id/redirections | 无                                                           | 权威管理->配置管理->视图->区->资源记录 |
| 31   | POST   | /apis/linkingthing.com/example/v1/views/:view_id/redirections | {"name":"www.baidu.com","ttl":200,"datatype":"A","redirecttype":"rpc","value":"10.0.0.1"}                                 | 权威管理->重定向 |新建
| 32   | GET    | /apis/linkingthing.com/example/v1/views/:view_id/redirections/:redirection_id | 无                                                           | 权威管理->重定向 |查询一条记录
| 33   | PUT    | /apis/linkingthing.com/example/v1/views/:view_id/redirections/:redirection_id | 同POST                                                        | 权威管理->重定向 |修改一条记录
| 34   | DELETE | /apis/linkingthing.com/example/v1/views/:view_id/redirections/:redirection_id | 无                                                           | 权威管理->重定向 |删除一条记录
| 35   | GET    | /apis/linkingthing.com/example/v1/defaultdns64s | 无                                                           | 递归管理->默认4A地址合成|查询
| 36   | POST   | /apis/linkingthing.com/example/v1/defaultdns64s | {"prefix":"24oe:eeff::/96","clientacl":"514208360416477185","aaddress":"516547807624527873"}                                 | 递归管理->默认4A地址合成 |新建
| 37   | GET    | /apis/linkingthing.com/example/v1/defaultdns64s/:defaultdns64_id | 无                                                           | 递归管理->默认4A地址合成 |查询一条记录
| 38   | PUT    | /apis/linkingthing.com/example/v1/defaultdns64s/:defaultdns64_id | 同POST                                                        | 递归管理->默认4A地址合成 |修改一条记录
| 39   | DELETE | /apis/linkingthing.com/example/v1/defaultdns64s/:defaultdns64_id | 无                                                           | 递归管理->默认4A地址合成 |删除一条记录
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

# 接口详细描述
## 1. 区转发
### 1.1. 视图展示
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

### 1.2. 区信息获取  
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

|请求内容|http://10.0.0.19:8081/apis/linkingthing.com/example/v1/views/516794447518629889/zones|
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

### 1.3. 服务器地址,转发方式信息获取  
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

### 1.4. 服务器地址,转发方式信息修改  
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

### 1.5. 服务器地址,转发方式信息删除
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

##  2. 重定向
###  2.1 视图展示
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
		"rpzsize": 2,
		"redirectsize": 0
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
		"rpzsize": 0,
		"redirectsize": 0
	}]
}
```
界面元素|响应参数位置|参数类型|参数值举例|
- | -|-|-|
视图|{"data":[{"name": "view1231_01"}]}|string|view1231_01|
重定向配置数量|{"data":[{"rpzsize":2}]}|int|2|
NXDOMAIN重定向配置数量|{"data":[{"redirectsize":2}]}|int|2|

###  2.2 第二页查询
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
		"redirecttype": "rpc",
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
		"redirecttype": "rpc",
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
重定向方式|{"data":[{"redirecttype": "rpc"}]}|string|rpc|重定向方式有两种,界面显示"直接重定向"和"NXDOMAIN重定向,前者后台数据用rpz表示,后者用redirect表示|

###  2.3 第二页新建
- 接口信息  

|接口描述|新建一条记录|
|-|-|
|请求地址|/apis/linkingthing.com/example/v1/views/:view_id/redirections|
|请求方式|HTTP/1.1 POST|
|表单内容|{"name":"www.baidu.com","ttl":200,"datatype":"A","redirecttype":"rpc","value":"10.0.0.1"}|
|返回格式|JSON|

- 请求参数意义

|参数名称|是否必填|数据类型|备注|
| - |-|-|-|
|name|是|string|域名|
|ttl|是|string|TTL|
|datatype|是|string|只能填A\|AAAA\|CNAME,其他后续补充|
|redirecttype|是|string|只能填rpc或者redirect|
|value|是|string|ipv4地址或者ipv6地址|

- 请求示例

|请求内容|http://10.0.0.19:8081/apis/linkingthing.com/example/v1/views/516794447518629889/redirections|
|-|-|
|表单内容|{"name":"www.baidu.com","ttl":200,"datatype":"A","redirecttype":"rpc","value":"10.0.0.1"}|
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
		"redirecttype": "rpc",
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
		"redirecttype": "rpc",
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
重定向方式|{"data":[{"redirecttype": "rpc"}]}|string|rpc|

###  2.4 第二页删除
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

###  2.5 第二页修改
- 接口信息  

|接口描述|新建一条记录|
|-|-|
|请求地址|/apis/linkingthing.com/example/v1/views/:view_id/redirections/:redirection_id|
|请求方式|HTTP/1.1 PUT|
|表单内容|{"name":"www.baidu.com","datatype":"AAAA","value":"1.2.3.4","ttl":10,"redirecttype":"rpc"}|
|返回格式|JSON|

- 请求参数意义

|参数名称|是否必填|数据类型|备注|
| - |-|-|-|
|name|是|string|域名|
|ttl|是|string|TTL|
|datatype|是|string|只能填A\|AAAA\|CNAME,其他后续补充|
|redirecttype|是|string|只能填rpc或者redirect|
|value|是|string|ipv4地址或者ipv6地址|

- 请求示例

|请求内容|http://10.0.0.19:8081/apis/linkingthing.com/example/v1/views/516794447518629889/redirections/519590500841455617|
|-|-|
|表单内容|{"name":"www.baidu.com","datatype":"AAAA","value":"1.2.3.4","ttl":10,"redirecttype":"rpc"}|
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
	"redirecttype": "rpc",
	"value": "1.2.3.4"
}
```
界面元素|响应参数位置|参数类型|参数值举例|
- | -|-|-|
域名|{"data":[{"name": "www.baidu.com"}]}|string|www.baidu.com|
TTL|{"data":[{"ttl": 10}]}|int|10|
记录类型|{"data":[{"datatype": "AAAAA"}]}|string|AAAA|
记录值|{"data":[{"value": "1.2.3.4"}]}|string|1.2.3.4|
重定向方式|{"data":[{"redirecttype": "rpc"}]}|string|rpc|

##  3. 递归管理->默认4A地址合成
###  3.1 页面展示
- 接口信息  

|接口描述|获取视图信息|
|-|-|
|请求地址|/apis/linkingthing.com/example/v1/defaultdns64s|
|请求方式|HTTP/1.1 GET|
|返回格式|JSON|

- 请求参数意义

|参数名称|是否必填|数据类型|备注|
| - |-|-|-|
|无|

- 请求示例

|请求内容|http://10.0.0.19:8081/apis/linkingthing.com/example/v1/defaultdns64s|
|-|-|
|响应内容|如下引用|

```
{
	"type": "collection",
	"resourceType": "defaultdns64",
	"links": {
		"self": "/apis/linkingthing.com/example/v1/defaultdns64s"
	},
	"data": [{
		"id": "526425621228912641",
		"type": "defaultdns64",
		"links": {
			"collection": "/apis/linkingthing.com/example/v1/defaultdns64s",
			"remove": "/apis/linkingthing.com/example/v1/defaultdns64s/526425621228912641",
			"self": "/apis/linkingthing.com/example/v1/defaultdns64s/526425621228912641",
			"update": "/apis/linkingthing.com/example/v1/defaultdns64s/526425621228912641"
		},
		"creationTimestamp": null,
		"prefix": "24oe:eeff::/96",
		"clientacl": "514208360416477185",
		"clientaclname": "acl_0114_1",
		"aaddress": "516547807624527873",
		"addressname": "acl_0114_3"
	}]
}
```
界面元素|响应参数位置|参数类型|参数值举例|
- | -|-|-|
前缀|{"data":[{"prefix": "24oe:eeff::/96"}]}|string|view1231_01|
客户IP地址|{"data":[{"whitename": "hwl_1230_07"}]}|string|hwl_1230_07|
客户IP黑名单|{"data":[{"blackname": "hwl_1230_02"}]}|string|hwl_1230_02|
目标IPv4地址|{"data":[{"addressname": "hwl_1230_03"}]}|string|hwl_1230_03|

###  3.2 第二页新建
- 接口信息  

|接口描述|新建一条记录|
|-|-|
|请求地址|/apis/linkingthing.com/example/v1/defaultdns64s|
|请求方式|HTTP/1.1 POST|
|表单内容|{"prefix":"24oe:eeff::/96","clientacl":"514208360416477185","aaddress":"516547807624527873"}|
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

|请求内容|http://10.0.0.19:8081/apis/linkingthing.com/example/v1/defaultdns64s|
|-|-|
|表单内容|{"prefix":"24oe:eeff::/96","clientacl":"514208360416477185","aaddress":"516547807624527873"}|
|响应内容|如下引用|

```
{
	"id": "526425621228912641",
	"type": "defaultdns64",
	"links": {
		"collection": "/apis/linkingthing.com/example/v1/defaultdns64s",
		"remove": "/apis/linkingthing.com/example/v1/defaultdns64s/526425621228912641",
		"self": "/apis/linkingthing.com/example/v1/defaultdns64s/526425621228912641",
		"update": "/apis/linkingthing.com/example/v1/defaultdns64s/526425621228912641"
	},
	"creationTimestamp": "2020-02-03T17:39:10+08:00",
	"prefix": "24oe:eeff::/96",
	"clientacl": "514208360416477185",
	"clientaclname": "",
	"aaddress": "516547807624527873",
	"addressname": ""
}
```

###  3.3 第二页删除
- 接口信息  

|接口描述|删除一条记录|
|-|-|
|请求地址|/apis/linkingthing.com/example/v1/defaultdns64s/:defaultdns64_id|
|请求方式|HTTP/1.1 DELETE|
|返回格式|JSON|

- 请求参数意义

|参数名称|是否必填|数据类型|备注|
| - |-|-|-|
|无|


- 请求示例

|请求内容|http://10.0.0.19:8081/apis/linkingthing.com/example/v1/defaultdns64s/519873083128807425|
|-|-|
|响应内容|无|

界面元素|响应参数位置|参数类型|参数值举例|
- | -|-|-|
无|

###  3.4 第二页修改
- 接口信息  

|接口描述|新建一条记录|
|-|-|
|请求地址|/apis/linkingthing.com/example/v1/defaultdns64s/:defaultdns64_id|
|请求方式|HTTP/1.1 PUT|
|表单内容|{"prefix":"24oe:eeff::/96","clientacl":"514208360416477185","aaddress":"516547872703512577"}|
|返回格式|JSON|

- 请求参数意义

|参数名称|是否必填|数据类型|备注|
| - |-|-|-|
|prefix|是|string|前缀|
|clientacl|是|string|客户IP地址,来自于ACL的ID|
|aaddress|是|string|目标IPv4地址,来自于ACL的ID|

- 请求示例

|请求内容|http://10.0.0.19:8081/apis/linkingthing.com/example/v1/defaultdns64s/526425621228912641|
|-|-|
|表单内容|{"prefix":"24oe:eeff::/96","clientacl":"514208360416477185","aaddress":"516547872703512577"}|
|响应内容|如下引用|

```
{
	"id": "526425621228912641",
	"type": "defaultdns64",
	"links": {
		"collection": "/apis/linkingthing.com/example/v1/defaultdns64s",
		"remove": "/apis/linkingthing.com/example/v1/defaultdns64s/526425621228912641",
		"self": "/apis/linkingthing.com/example/v1/defaultdns64s/526425621228912641",
		"update": "/apis/linkingthing.com/example/v1/defaultdns64s/526425621228912641"
	},
	"creationTimestamp": null,
	"prefix": "24oe:eeff::/96",
	"clientacl": "514208360416477185",
	"clientaclname": "",
	"aaddress": "516547872703512577",
	"addressname": ""
}
```

##  4. 递归管理->4A地址合成
###  4.1 视图展示
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
		"rpzsize": 0,
		"redirectsize": 0,
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
		"rpzsize": 2,
		"redirectsize": 1,
		"dns64size": 0
	}]
}
```
界面元素|响应参数位置|参数类型|参数值举例|
- | -|-|-|
视图|{"data":[{"name": "view1231_01"}]}|string|view1231_01|
规则数量|{"data":[{"dns64size":0}]}|int|0|

###  4.2 第二页页面展示
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

###  4.3 第二页新建
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

###  4.4 第二页删除
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

###  4.5 第二页修改
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

##  5. 安全管理->地址黑名单
###  5.1 页面展示
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

###  5.2 新建
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

###  5.4 删除
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

###  5.5 修改
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

##  6. 安全管理->并发控制
###  6.1 页面展示
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

###  6.2 修改
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