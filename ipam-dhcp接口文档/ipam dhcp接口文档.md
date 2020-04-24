## ipam dhcp接口文档



## 全局设置：

- 所有的变量类型都是字符串或整数
- 接口暂定，联调时候继续优化。



### 1 子网管理

#### 1.1 添加ipv4子网

| 功能     | 描述                                                         |
| -------- | ------------------------------------------------------------ |
| 接口功能 | 添加ipv4子网                                                 |
| 接口地址 | /apis/linkingthing.com/example/v1/restsubnetv4s              |
| 请求方式 | POST                                                         |
| 请求参数 | subnet, string, 子网地址                                     |
|          | name, 类型 string,子网地址                                   |
|          | gateway, 类型 string, 网关地址                               |
| 请求示例 | curl http://10.0.0.101:8081/apis/linkingthing.com/example/v1/restsubnetv4s -X POST -d '{"subnet":"10.0.1.0/24", "name":"name2", "validLifetime":"3600","gateway":"192.168.1.1","dnsServer":"1.1.1.1"}' |



| 参数名称 | 是否必填 | 数据类型 | 备注           |
| -------- | -------- | -------- | -------------- |
| name     | 是       | string   | 要更新节点的id |
|          |          |          |                |
|          |          |          |                |
|          |          |          |                |

- 请求示例

​    "gateway": "192.168.1.1",

​	"total": "",//地址数量
​	"usage": ""//子网地址使用率

​      "dnsServer": "2.2.2.3",//域名服务器

​      "dhcpEnable": 0,//是否开启dhcp

​      "dnsEnable": 0,//是否开启dns

​      "zoneName": "",//区域名称

​      "viewId": "", //视图id

​      "note": "" //备注

- 返回数据示例

{
	"embedded": {
		"id": "541122915319513089",  //新创建的子网的资源id
		"type": "restsubnetv4",
		"links": {
			"collection": "/apis/linkingthing/dhcp/v1/restsubnetv4s",
			"remove": "/apis/linkingthing/dhcp/v1/restsubnetv4s/541122915319513089",
			"restpools": "/apis/linkingthing/dhcp/v1/restsubnetv4s/541122915319513089/restpools",
			"restreservations": "/apis/linkingthing/dhcp/v1/restsubnetv4s/541122915319513089/restreservations",
			"self": "/apis/linkingthing/dhcp/v1/restsubnetv4s/541122915319513089",
			"update": "/apis/linkingthing/dhcp/v1/restsubnetv4s/541122915319513089"
		},
		"creationTimestamp": "2020-03-26T07:33:28Z",//创建时间
		"deletionTimestamp": null
	},
	"name": "name35", //子网名称
	"subnet": "192.168.1.35/24", //子网地址
	"subnet_id": "541122915319513089",  //新创建的子网的资源id
	"validLifetime": "35", //有效生命时长
	"Reservations": null,
	"Pools": null,

​    "gateway": "192.168.1.1",

​	"total": "",//地址数量
​	"usage": ""//子网地址使用率

​      "dnsServer": "2.2.2.3",//域名服务器

​      "dhcpEnable": 1,//是否开启dhcp  默认开启dhcp

​      "dnsEnable": 0,//是否开启dns

​      "zoneName": "",//区域名称

​      "viewId": "", //视图id

​      "note": "" //备注

}



#### 1.2 列出ipv4子网

| 功能     | 描述                                                         |
| -------- | ------------------------------------------------------------ |
| 接口功能 | 列出当前所有的ipv4子网                                       |
| 接口地址 | /apis/linkingthing.com/example/v1/restsubnetv4s              |
| 请求方式 | GET                                                          |
| 请求参数 | 无                                                           |
|          |                                                              |
| 请求示例 | curl http://10.0.0.101:8081/apis/linkingthing.com/example/v1/restsubnetv4s -X GET |



- 返回数据示例

{
	"type": "collection",
	"resourceType": "restsubnetv4",
	"links": {
		"self": "/apis/linkingthing/dhcp/v1/restsubnetv4s"
	},
	"data": [{
		"embedded": {
			"id": "540635706462830593",
			"type": "restsubnetv4",
			"links": {
				"collection": "/apis/linkingthing/dhcp/v1/restsubnetv4s",
				"remove": "/apis/linkingthing/dhcp/v1/restsubnetv4s/540635706462830593",
				"restpools": "/apis/linkingthing/dhcp/v1/restsubnetv4s/540635706462830593/restpools",
				"restreservations": "/apis/linkingthing/dhcp/v1/restsubnetv4s/540635706462830593/restreservations",
				"self": "/apis/linkingthing/dhcp/v1/restsubnetv4s/540635706462830593",
				"update": "/apis/linkingthing/dhcp/v1/restsubnetv4s/540635706462830593"
			},
			"creationTimestamp": null,
			"deletionTimestamp": null
		},
		"name": "name2",//子网名字
		"subnet": "192.168.1.2/24",//子网地址
		"subnet_id": "540635706462830593",//子网id
		"validLifetime": "",
		"Reservations": null,
		"Pools": null,
		"total": "0",//子网的ip总数
		"usage": "0.0"//子网的ip利用率

​	},{
​		"embedded": {
​			"id": "541122915319513089",
​			"type": "restsubnetv4",
​			"links": {
​				"collection": "/apis/linkingthing/dhcp/v1/restsubnetv4s",
​				"remove": "/apis/linkingthing/dhcp/v1/restsubnetv4s/541122915319513089",
​				"restpools": "/apis/linkingthing/dhcp/v1/restsubnetv4s/541122915319513089/restpools",
​				"restreservations": "/apis/linkingthing/dhcp/v1/restsubnetv4s/541122915319513089/restreservations",
​				"self": "/apis/linkingthing/dhcp/v1/restsubnetv4s/541122915319513089",
​				"update": "/apis/linkingthing/dhcp/v1/restsubnetv4s/541122915319513089"
​			},
​			"creationTimestamp": null,
​			"deletionTimestamp": null
​		},
​		"name": "name35",
​		"subnet": "192.168.1.35/24",
​		"subnet_id": "541122915319513089",
​		"validLifetime": "35",
​		"Reservations": null,
​		"Pools": null,
​		"total": "0",
​		"usage": "0.00",

​      "dnsServer": "2.2.2.3",//域名服务器

​      "dhcpEnable": 0,//是否开启dhcp

​      "dnsEnable": 0,//是否开启dns

​      "zoneName": "",//区域名称

​      "viewId": "", //视图id

​      "note": "" //备注

​	}]
}



#### 1.2.2 获取一个ipv4子网的信息

| 功能     | 描述                                                         |
| -------- | ------------------------------------------------------------ |
| 接口功能 | 获取一个ipv4子网的信息                                       |
| 接口地址 | /apis/linkingthing.com/example/v1/restsubnetv4s/:subnetv4Id  |
| 请求方式 | GET                                                          |
| 请求参数 | 无                                                           |
|          |                                                              |
| 请求示例 | curl http://10.0.0.101:8081/apis/linkingthing.com/example/v1/restsubnetv4s/547130458575503361 -X GET |



- 返回数据示例

{  "embedded": {

​    "id": "547130458575503361",

​    "type": "restsubnetv4",

​    "links": {

​      "collection": "/apis/linkingthing/dhcp/v1/restsubnetv4s",

​      "remove": "/apis/linkingthing/dhcp/v1/restsubnetv4s/547130458575503361",

​      "restpools": "/apis/linkingthing/dhcp/v1/restsubnetv4s/547130458575503361/restpools",

​      "restreservations": "/apis/linkingthing/dhcp/v1/restsubnetv4s/547130458575503361/restreservations",

​      "self": "/apis/linkingthing/dhcp/v1/restsubnetv4s/547130458575503361",

​      "update": "/apis/linkingthing/dhcp/v1/restsubnetv4s/547130458575503361"

​    },

​    "creationTimestamp": "2020-04-16T12:49:25Z",

​    "deletionTimestamp": null

  },

  "name": "name2",

  "subnet": "10.0.2.0/24",

  "subnet_id": "547130458575503361",

  "validLifetime": "3600",

  "Reservations": null,

  "Pools": null,

  "total": "",

  "usage": "",

  "gateway": "192.168.2.1",

  "dnsServer": "1.1.1.1",

  "dhcpEnable": 0,

  "dnsEnable": 0,

  "zoneName": "",

  "viewId": "",

  "note": ""

}



#### 1.3 修改ipv4子网

| 功能     | 描述                                                         |
| -------- | ------------------------------------------------------------ |
| 接口功能 | 修改ipv4子网信息                                             |
| 接口地址 | /apis/linkingthing.com/example/v1/restsubnetv4s/:subnetv4Id  |
| 请求方式 | POST                                                         |
| 请求示例 | curl http://10.0.0.101:8081/apis/linkingthing.com/example/v1/restsubnetv4s/541122915319513089 -X PUT -d '{"subnet":"192.168.1.35/24", "name":"name352", "zoneName":"zone01","viewId":"12","dhcpEnable":1,"dnsEnable":1,"note":"notessss"}' |
|          |                                                              |

| 参数名称   | 是否必填 | 数据类型 | 备注                            |
| ---------- | -------- | -------- | ------------------------------- |
| zoneName   | 是       | string   | 区域名                |
| viewId     | 是       | string   | view ID                |
| dhcpEnable | 是       | int      | 开启dhcp  1开启 0关闭           |
| dnsEnable  | 是       | int      | 开启dns  1开启 0关闭 |
| note      | 是       | string   | 备注                            |
| gateway | 否 | string | 网关 |
| dnsServer | 否 | string | 域名服务器 |



- 返回数据示例

{
	"embedded": {
		"id": "541122915319513089",
		"type": "restsubnetv4",
		"links": {
			"collection": "/apis/linkingthing/dhcp/v1/restsubnetv4s",
			"remove": "/apis/linkingthing/dhcp/v1/restsubnetv4s/541122915319513089",
			"restpools": "/apis/linkingthing/dhcp/v1/restsubnetv4s/541122915319513089/restpools",
			"restreservations": "/apis/linkingthing/dhcp/v1/restsubnetv4s/541122915319513089/restreservations",
			"self": "/apis/linkingthing/dhcp/v1/restsubnetv4s/541122915319513089",
			"update": "/apis/linkingthing/dhcp/v1/restsubnetv4s/541122915319513089"
		},
		"creationTimestamp": null,
		"deletionTimestamp": null
	},
	"name": "name352",
	"subnet": "192.168.1.35/24",
	"subnet_id": "541122915319513089",
	"validLifetime": "352",
	"Reservations": null,
	"Pools": null,
	"total": "",
	"usage": ""

  "gateway": "1.1.1.1",

  "dnsServer": "2.2.2.2",

  "dhcpEnable": 1,

  "dnsEnable": 0,

  "zoneName": "",

  "viewId": "",

  "note": "notessss"

}

#### 1.4 删除ipv4子网

| 功能     | 描述                                                         |
| -------- | ------------------------------------------------------------ |
| 接口功能 | 删除ipv4子网                                                 |
| 接口地址 | /apis/linkingthing.com/example/v1/restsubnetv4s/:subnetv4Id  |
| 请求方式 | DELETE                                                       |
| 请求参数 | 无                                                           |
| 请求示例 | curl http://10.0.0.101:8081/apis/linkingthing.com/example/v1/restsubnetv4s/541122915319513089 -X DELETE |
|          |                                                              |

- 返回数据示例

默认成功。如果失败会返回如下信息：

{
	"code": "ServerError",
	"status": 500,
	"type": "error",
	"message": "unknown subnetv4 with ID 541120201920839681, record not found"
}



#### 1.5 拆分ipv4子网



| 功能     | 描述                                                         |
| -------- | ------------------------------------------------------------ |
| 接口功能 | 拆分ipv4子网                                                 |
| 接口地址 | /apis/linkingthing.com/example/v1/restsubnetv4s/:subnetv4Id?action=mergesplit |
| 请求方式 | POST                                                         |
| 请求参数 | oper, string, ="split"; mask, string, 掩码长度               |
| 请求示例 | curl http://10.0.0.101:8081/apis/linkingthing.com/example/v1/restsubnetv4s/541122915319513089?action=mergesplit -X POST -d '{"oper":"split","mask":"29"}' |
|          |                                                              |

- 返回数据示例

字段和新建ipv4子网的一致

{
	"embedded": {
		"id": "542483914175676417",
		"creationTimestamp": "2020-03-31T02:55:52Z",//创建时间
		"deletionTimestamp": null
	},
	"name": "192.168.1.240/29",//name原型没有输入，暂时和subnet一致
	"subnet": "192.168.1.240/29",//新的子网
	"subnet_id": "542483914175676417",
	"validLifetime": "0",
	"Reservations": null,
	"Pools": null,
	"total": "",
	"usage": ""
}, {
	"embedded": {
		"id": "542483917507723265",
		"creationTimestamp": "2020-03-31T02:55:53Z",
		"deletionTimestamp": null
	},
	"name": "192.168.1.248/29",
	"subnet": "192.168.1.248/29",
	"subnet_id": "542483917507723265",
	"validLifetime": "0",
	"Reservations": null,
	"Pools": null,
	"total": "",
	"usage": ""
}



#### 1.6 合并ipv4子网



| 功能     | 描述                                                         |
| -------- | ------------------------------------------------------------ |
| 接口功能 | 合并ipv4子网。传入几个子网id，如果不能合并服务器会提示错误。如果能合并，将删除这几个子网，创建一个新的子网 |
| 接口地址 | /apis/linkingthing.com/example/v1/restsubnetv4s?action=mergesplit |
| 请求方式 | POST                                                         |
| 请求参数 | oper, string, ="split" 操作,都是split                        |
|          | ips, string, 逗号分隔的子网id                                |
|          | 示例："ips":"542475213327138817,542475209988800513"          |
| 请求示例 | curl http://10.0.0.101:8081/apis/linkingthing.com/example/v1/restsubnetv4s?action=mergesplit -X POST -d '{"oper":"merge","ips":"542475213327138817,542475209988800513"}' |
|          |                                                              |

- 返回数据示例

  - 正确返回创建后的子网详情

    {

    "embedded": {

  ​    "id": "542875861930442753",

  ​    "creationTimestamp": "2020-04-01T12:09:25Z",

  ​    "deletionTimestamp": null

    },

    "name": "10.0.6.0/24",

    "subnet": "10.0.6.0/24",

    "subnet_id": "542875861930442753",

    "validLifetime": "0",

    "Reservations": null,

    "Pools": null,

    "total": "",

    "usage": ""

  }

  

  - 如果不能合并，返回错误信息

{"code":"ServerError","status":500,"type":"error","message":"错误, 无法合并子网"}



#### 1.7 添加ipv6子网

| 功能     | 描述                                                         |
| -------- | ------------------------------------------------------------ |
| 接口功能 | 新建ipv6子网                                                 |
| 接口地址 | /apis/linkingthing.com/example/v1/restsubnetv6s              |
| 请求方式 | POST                                                         |
| 请求参数 | subnet, string, 子网地址                                     |
|          | name, 类型 string,子网地址                                   |
|          | ipv6没有网关参数                                             |
| 请求示例 | curl http://10.0.0.101:8081/apis/linkingthing.com/example/v1/restsubnetv6s -X POST -d '{"subnet":"fe80:10::/64", "name":"name2", "validLifetime":"3600"}' |

- 返回数据示例

{

  "type": "collection",

  "resourceType": "restsubnetv6",

  "links": {

​    "self": "/apis/linkingthing.com/example/v1/restsubnetv6s"

  },

  "data": [

​    {

​      "embedded": {

​        "id": "546737206723346433",

​        "type": "restsubnetv6",

​        "links": {

​          "collection": "/apis/linkingthing.com/example/v1/restsubnetv6s",

​          "self": "/apis/linkingthing.com/example/v1/restsubnetv6s/546737206723346433"

​        },

​        "creationTimestamp": null,

​        "deletionTimestamp": null

​      },

​      "subnet": "fe80:3::/64",

​      "subnet_id": "",

​      "validLifetime": "11",

​      "Reservations": null,

​      "Pools": null,

​      "total": "",

​      "usage": ""

​    },

​    {

​      "embedded": {

​        "id": "546740223223005185",

​        "type": "restsubnetv6",

​        "links": {

​          "collection": "/apis/linkingthing.com/example/v1/restsubnetv6s",

​          "self": "/apis/linkingthing.com/example/v1/restsubnetv6s/546740223223005185"

​        },

​        "creationTimestamp": null,

​        "deletionTimestamp": null

​      },

​      "subnet": "fe80:4::/64",

​      "subnet_id": "",

​      "validLifetime": "14",

​      "Reservations": null,

​      "Pools": null,

​      "total": "",

​      "usage": ""

​    }

  ]

}





#### 1.8 列出ipv6子网

| 功能     | 描述                                                         |
| -------- | ------------------------------------------------------------ |
| 接口功能 | 列出当前所有的ipv6子网                                       |
| 接口地址 | /apis/linkingthing.com/example/v1/restsubnetv6s              |
| 请求方式 | POST                                                         |
| 请求参数 | 无                                                           |
|          |                                                              |
| 请求示例 | curl http://10.0.0.101:8081/apis/linkingthing.com/example/v1/restsubnetv6s -X GET |



{

  "type": "collection",

  "resourceType": "restsubnetv6",

  "links": {

​    "self": "/apis/linkingthing.com/example/v1/restsubnetv6s"

  },

  "data": [

​    {

​      "embedded": {

​        "id": "546737206723346433",

​        "type": "restsubnetv6",

​        "links": {

​          "collection": "/apis/linkingthing.com/example/v1/restsubnetv6s",

​          "remove": "/apis/linkingthing.com/example/v1/restsubnetv6s/546737206723346433",

​          "restpoolv6s": "/apis/linkingthing.com/example/v1/restsubnetv6s/546737206723346433/restpoolv6s",

​          "self": "/apis/linkingthing.com/example/v1/restsubnetv6s/546737206723346433",

​          "update": "/apis/linkingthing.com/example/v1/restsubnetv6s/546737206723346433"

​        },

​        "creationTimestamp": null,

​        "deletionTimestamp": null

​      },

​      "subnet": "fe80:3::/64",

​      "subnet_id": "",

​      "validLifetime": "11",

​      "Reservations": null,

​      "Pools": null,

​      "total": "",

​      "usage": ""

​    },

​    {

​      "embedded": {

​        "id": "546740223223005185",

​        "type": "restsubnetv6",

​        "links": {

​          "collection": "/apis/linkingthing.com/example/v1/restsubnetv6s",

​          "remove": "/apis/linkingthing.com/example/v1/restsubnetv6s/546740223223005185",

​          "restpoolv6s": "/apis/linkingthing.com/example/v1/restsubnetv6s/546740223223005185/restpoolv6s",

​          "self": "/apis/linkingthing.com/example/v1/restsubnetv6s/546740223223005185",

​          "update": "/apis/linkingthing.com/example/v1/restsubnetv6s/546740223223005185"

​        },

​        "creationTimestamp": null,

​        "deletionTimestamp": null

​      },

​      "subnet": "fe80:4::/64",

​      "subnet_id": "",

​      "validLifetime": "14",

​      "Reservations": null,

​      "Pools": null,

​      "total": "",

​      "usage": ""

​    }

  ]

}





#### 1.9 修改ipv6子网

| 功能     | 描述                                                         |
| -------- | ------------------------------------------------------------ |
| 接口功能 | 修改ipv6子网                                                 |
| 接口地址 | /apis/linkingthing.com/example/v1/restsubnetv6s/:subnetv6Id  |
| 请求方式 | POST                                                         |
| 请求参数 | 与添加ipv6子网相同                                           |
| 请求示例 | curl http://10.0.0.101:8081/apis/linkingthing.com/example/v1/restsubnetv6s/541122915319513089 -X PUT -d '{"subnet":"fe80:10::/64", "name":"name4", "validLifetime":"3602"}' |
|          |                                                              |

- 返回数据示例

{

  "embedded": {

​    "id": "547095958587572225",

​    "type": "restsubnetv6",

​    "links": {

​      "collection": "/apis/linkingthing.com/example/v1/restsubnetv6s",

​      "remove": "/apis/linkingthing.com/example/v1/restsubnetv6s/547095958587572225",

​      "restpoolv6s": "/apis/linkingthing.com/example/v1/restsubnetv6s/547095958587572225/restpoolv6s",

​      "self": "/apis/linkingthing.com/example/v1/restsubnetv6s/547095958587572225",

​      "update": "/apis/linkingthing.com/example/v1/restsubnetv6s/547095958587572225"

​    },

​    "creationTimestamp": null,

​    "deletionTimestamp": null

  },

  "name": "name4",

  "subnet": "fe80:10::/64",

  "subnet_id": "547095958587572225",

  "validLifetime": "3602",

  "Reservations": null,

  "Pools": null,

  "total": "",

  "usage": ""

}

#### 1.10 删除ipv6子网

| 功能     | 描述                                                         |
| -------- | ------------------------------------------------------------ |
| 接口功能 | 删除ipv6子网                                                 |
| 接口地址 | /apis/linkingthing.com/example/v1/restsubnetv6s/:subnetv6Id  |
| 请求方式 | DELETE                                                       |
| 请求参数 | 无                                                           |
| 请求示例 | curl http://10.0.0.101:8081/apis/linkingthing.com/example/v1/restsubnetv4s/541122915319513089 -X DELETE |
|          |                                                              |

- 返回数据示例

默认成功。如果失败会返回如下信息：

{
	"code": "ServerError",
	"status": 500,
	"type": "error",
	"message": "unknown subnetv4 with ID 541120201920839681, record not found"
}



#### 1.11 列出ipv4和ipv6子网

| 功能     | 描述                                                         |
| -------- | ------------------------------------------------------------ |
| 接口功能 | 列出当前所有的ipv4和ipv6子网                                 |
| 接口地址 | /apis/linkingthing.com/example/v1/restsubnetv46s             |
| 请求方式 | POST                                                         |
| 请求参数 | 无                                                           |
|          |                                                              |
| 请求示例 | curl http://10.0.0.101:8081/apis/linkingthing.com/example/v1/restsubnetv46s -X GET |



- 返回数据示例

{
	"type": "collection",
	"resourceType": "restsubnetv4",
	"links": {
		"self": "/apis/linkingthing/dhcp/v1/restsubnetv4s"
	},
	"data": [{
		"embedded": {
			"id": "540635706462830593",
			"type": "restsubnetv4",
			"links": {
				"collection": "/apis/linkingthing/dhcp/v1/restsubnetv4s",
				"remove": "/apis/linkingthing/dhcp/v1/restsubnetv4s/540635706462830593",
				"restpools": "/apis/linkingthing/dhcp/v1/restsubnetv4s/540635706462830593/restpools",
				"restreservations": "/apis/linkingthing/dhcp/v1/restsubnetv4s/540635706462830593/restreservations",
				"self": "/apis/linkingthing/dhcp/v1/restsubnetv4s/540635706462830593",
				"update": "/apis/linkingthing/dhcp/v1/restsubnetv4s/540635706462830593"
			},
			"creationTimestamp": null,
			"deletionTimestamp": null
		},
		"name": "name2",//子网名字
		"subnet": "192.168.1.2/24",//子网地址
		"subnet_id": "540635706462830593",//子网id
		"validLifetime": "",
		"Reservations": null,
		"Pools": null,
		"total": "0",//子网的ip总数
		"usage": "0.0"//子网的ip利用率

​	},{
​		"embedded": {
​			"id": "541122915319513089",
​			"type": "restsubnetv4",
​			"links": {
​				"collection": "/apis/linkingthing/dhcp/v1/restsubnetv4s",
​				"remove": "/apis/linkingthing/dhcp/v1/restsubnetv4s/541122915319513089",
​				"restpools": "/apis/linkingthing/dhcp/v1/restsubnetv4s/541122915319513089/restpools",
​				"restreservations": "/apis/linkingthing/dhcp/v1/restsubnetv4s/541122915319513089/restreservations",
​				"self": "/apis/linkingthing/dhcp/v1/restsubnetv4s/541122915319513089",
​				"update": "/apis/linkingthing/dhcp/v1/restsubnetv4s/541122915319513089"
​			},
​			"creationTimestamp": null,
​			"deletionTimestamp": null
​		},
​		"name": "name35",
​		"subnet": "192.168.1.35/24",
​		"subnet_id": "541122915319513089",
​		"validLifetime": "35",
​		"Reservations": null,
​		"Pools": null,
​		"total": "0",
​		"usage": "0.00"
​	}]
}





### 2 IP地址展示
## 2.1展示所有IP地址
- 接口信息  

|接口描述|获取规划地址信息|
|-|-|
|请求地址|/apis/linkingthing.com/example/v1/restsubnetv4s/:restsubnetv4_id/ipaddresses
|请求方式|HTTP/1.1 GET|
|返回格式|JSON|

- 请求参数意义

|参数名称|是否必填|数据类型|备注|
| - |-|-|-|
|restsubnetv4_id|是|整型|子网id|

- 请求示例

|请求内容|http://10.0.0.19:8081/apis/linkingthing.com/example/v1/restsubnetv4s/1/ipaddresses|
|-|-|
|响应内容|如下引用|

```
{
	"type": "collection",
	"resourceType": "ipaddress",
	"links": {
		"self": "/apis/linkingthing.com/example/v1/restsubnetv4s/1/ipaddresses"
	},
	"data": [{
		"id": "549281636718051329",
		"type": "ipaddress",
		"links": {
			"collection": "/apis/linkingthing.com/example/v1/restsubnetv4s/1/ipaddresses",
			"update": "/apis/linkingthing.com/example/v1/restsubnetv4s/1/ipaddresses/549281636718051329"
		},
		"creationTimestamp": null,
		"deletionTimestamp": null,
		"ip": "172.16.86.126",
		"macaddress": "",
		"macvender": "",
		"AddressType": "dynamic",
		"opersystem": "",
		"netbiosname": "",
		"hostname": "",
		"interfaceid": "",
		"scantime": 0,
		"lastalivetime": 0,
		"fingerprint": "",
		"leasestarttime": 0,
		"leaseendtime": 0,
		"devicetypeflag": false,
		"devicetype": "",
		"businessflag": false,
		"business": "",
		"chargepersonflag": false,
		"chargeperson": "",
		"telflag": false,
		"tel": "",
		"departmentflag": false,
		"department": "",
		"positionflag": false,
		"position": ""
	}, {
		"id": "549281636731355137",
		"type": "ipaddress",
		"links": {
			"collection": "/apis/linkingthing.com/example/v1/restsubnetv4s/1/ipaddresses",
			"update": "/apis/linkingthing.com/example/v1/restsubnetv4s/1/ipaddresses/549281636731355137"
		},
		"creationTimestamp": null,
		"deletionTimestamp": null,
		"ip": "172.16.86.21",
		"macaddress": "",
		"macvender": "",
		"AddressType": "dynamic",
		"opersystem": "",
		"netbiosname": "",
		"hostname": "",
		"interfaceid": "",
		"scantime": 0,
		"lastalivetime": 0,
		"fingerprint": "",
		"leasestarttime": 0,
		"leaseendtime": 0,
		"devicetypeflag": false,
		"devicetype": "",
		"businessflag": false,
		"business": "",
		"chargepersonflag": false,
		"chargeperson": "",
		"telflag": false,
		"tel": "",
		"departmentflag": false,
		"department": "",
		"positionflag": false,
		"position": ""
	}, ...
	 {
		"id": "549281639184367617",
		"type": "ipaddress",
		"links": {
			"collection": "/apis/linkingthing.com/example/v1/restsubnetv4s/1/ipaddresses",
			"update": "/apis/linkingthing.com/example/v1/restsubnetv4s/1/ipaddresses/549281639184367617"
		},
		"creationTimestamp": null,
		"deletionTimestamp": null,
		"ip": "172.16.86.149",
		"macaddress": "",
		"macvender": "",
		"AddressType": "dynamic",
		"opersystem": "",
		"netbiosname": "",
		"hostname": "",
		"interfaceid": "",
		"scantime": 0,
		"lastalivetime": 0,
		"fingerprint": "",
		"leasestarttime": 0,
		"leaseendtime": 0,
		"devicetypeflag": false,
		"devicetype": "",
		"businessflag": false,
		"business": "",
		"chargepersonflag": false,
		"chargeperson": "",
		"telflag": false,
		"tel": "",
		"departmentflag": false,
		"department": "",
		"positionflag": false,
		"position": ""
	}]
}
```

|响应参数|意义|参数类型|参数值举例|
|- | -|-|-|
|id|唯一标识|string|"547145299625639937"|
|ip|ip地址|string|"172.16.86.206"|
|macaddress|MAC地址|string|"1:1:1:1:1:1"|
|macvender|MAC厂商|string|"华为"|
|AddressType|地址类型|string|"dynamic"|
|opersystem|操作系统|string|"Linux"|
|netbiosname|netbios检测出来的名字|string|"host01"|
|hostname|主机名|string|"dynamic"|
|interfaceid|交换机端口|string|"12"|
|scantime|扫描时间|int|1587043291|
|lastalivetime|最近活跃时间|int|1587043291|
|fingerprint|指纹|string|""|
|leasestarttime|租约开始时间|int|1587043291|
|leaseendtime|租约结束时间|int|1587093291"|
|devicetypeflag|设备类型的启用标志位|bool|true|
|devicetype|设备类型|string|"printer"|

|AddressType序号|意义|值||
|- | -|-|-|
|1|保留地址|reserved|string|"172.16.86.206"|
|2|动态地址|dynamic|string|"172.16.86.3"|
|3|固定地址|stable|string|"172.16.86.1"|
|4|手动地址|manual|string|"172.16.86.210"|
|5|已分配地址|lease|string|"172.16.86.103"|
|6|未使用地址|unused|string|"172.16.86.203"|

### 2.2 IP地址设置
- 接口信息  

|接口描述|设置IP地址属性|
|-|-|
|请求地址|/apis/linkingthing.com/example/v1/restsubnetv4s/:restsubnetv4_id/ipaddresses/:ipaddress_id
|请求报文体|JSON报文|
|请求方式|HTTP/1.1 PUT|
|返回格式|JSON|

- 请求报文如下
```
{
	"type": "dividedaddress",
	"ip": "172.16.86.29",
	"macaddress": "1:1:1:1:1:1",
	"macvender": "",
	"AddressType": "dynamic",
	"opersystem": "",
	"netbiosname": "",
	"hostname": "huangwlv1",
	"interfaceid": "",
	"scantime": 0,
	"lastalivetime": 0,
	"fingerprint": "",
	"leasestarttime": 0,
	"leaseendtime": 0,
	"devicetypeflag": true,
	"devicetype": "printer",
	"businessflag": false,
	"business": "",
	"chargepersonflag": false,
	"chargeperson": "",
	"telflag": false,
	"tel": "",
	"departmentflag": false,
	"department": "",
	"positionflag": false,
	"position": ""
}
```

- 请求参数意义

|参数名称|是否必填|数据类型|备注|
| - |-|-|-|
|subnetid|是|整型|子网id|

- 请求示例

|请求内容|http://10.0.0.19:8081/apis/linkingthing.com/example/v1/restsubnetv4s/1/ipaddresses/549281639174864897|
|-|-|
|请求内容|如下引用|
```
{
	"type": "ipaddress",
	"ip": "172.16.86.29",
	"macaddress": "1:1:1:1:1:1",
	"macvender": "",
	"AddressType": "dynamic",
	"opersystem": "",
	"netbiosname": "",
	"hostname": "huangwlv1",
	"interfaceid": "",
	"scantime": 0,
	"lastalivetime": 0,
	"fingerprint": "",
	"leasestarttime": 0,
	"leaseendtime": 0,
	"devicetypeflag": true,
	"devicetype": "printer",
	"businessflag": false,
	"business": "",
	"chargepersonflag": false,
	"chargeperson": "",
	"telflag": false,
	"tel": "",
	"departmentflag": false,
	"department": "",
	"positionflag": false,
	"position": ""
}
```

|-|-|
|响应内容|如下引用|

```
{
	"id": "549281639174864897",
	"type": "ipaddress",
	"links": {
		"collection": "/apis/linkingthing.com/example/v1/restsubnetv4s/1/ipaddresses",
		"ipattrappends": "/apis/linkingthing.com/example/v1/restsubnetv4s/1/ipaddresses/549281639174864897/ipattrappends",
		"update": "/apis/linkingthing.com/example/v1/restsubnetv4s/1/ipaddresses/549281639174864897"
	},
	"creationTimestamp": null,
	"deletionTimestamp": null,
	"ip": "172.16.86.29",
	"macaddress": "1:1:1:1:1:1",
	"macvender": "",
	"AddressType": "dynamic",
	"opersystem": "",
	"netbiosname": "",
	"hostname": "huangwlv1",
	"interfaceid": "",
	"scantime": 0,
	"lastalivetime": 0,
	"fingerprint": "",
	"leasestarttime": 0,
	"leaseendtime": 0,
	"devicetypeflag": true,
	"devicetype": "printer",
	"businessflag": false,
	"business": "",
	"chargepersonflag": false,
	"chargeperson": "",
	"telflag": false,
	"tel": "",
	"departmentflag": false,
	"department": "",
	"positionflag": false,
	"position": ""
}
```

### 2.3 IP地址扩展属性设置
- 接口信息  

|接口描述|获取规划地址信息|
|-|-|
|请求地址|/apis/linkingthing.com/example/v1/restsubnetv4s/:restsubnetv4_id/ipaddresses/:ipaddress_id/ipattrappends/ipattrappend
|请求报文体|JSON报文|
|请求方式|HTTP/1.1 PUT|
|返回格式|JSON|

- 请求报文如下
```
{"DeviceTypeFlag":true,"BusinessFlag":false,"ChargePersonFlag":false,"TelFlag":false,"DepartmentFlag":false,"PositionFlag":false}
```

- 请求参数意义

|参数名称|是否必填|数据类型|备注|
| - |-|-|-|
|dividedaddress_id|是|整型|单条IP信息记录的id,来自于2.1|

- 请求示例

|请求内容|http://10.0.0.19:8081/apis/linkingthing.com/example/v1/restsubnetv4s/1/ipaddresses/549281638181011457/ipattrappends/ipattrappend|
|-|-|
|请求内容|如下引用|
```
{
	"DeviceTypeFlag": true,
	"BusinessFlag": true,
	"ChargePersonFlag": true,
	"TelFlag": true,
	"DepartmentFlag": true,
	"PositionFlag": true
}
```

|-|-|
|响应内容|如下引用|

```
{
	"id": "ipattrappend",
	"type": "ipattrappend",
	"links": {
		"self": "/apis/linkingthing.com/example/v1/restsubnetv4s/1/ipaddresses/549281638181011457/ipattrappends/ipattrappend",
		"update": "/apis/linkingthing.com/example/v1/restsubnetv4s/1/ipaddresses/549281638181011457/ipattrappends/ipattrappend"
	},
	"creationTimestamp": null,
	"deletionTimestamp": null,
	"DeviceTypeFlag": true,
	"BusinessFlag": true,
	"ChargePersonFlag": true,
	"TelFlag": true,
	"DepartmentFlag": true,
	"PositionFlag": true
}
```

### 2.4 IP地址扩展属性查询
- 接口信息  

|接口描述|获取规划地址信息|
|-|-|
|请求地址|/apis/linkingthing.com/example/v1/ipattrappends/:dividedaddress_id
|请求报文体|无|
|请求方式|HTTP/1.1 GET|
|返回格式|JSON|


- 请求参数意义

|参数名称|是否必填|数据类型|备注|
| - |-|-|-|
|dividedaddress_id|是|整型|单条IP信息记录的id,来自于2.1|

- 请求示例

|请求内容|http://10.0.0.19:8081/apis/linkingthing.com/example/v1/restsubnetv4s/1/ipaddresses/549281638181011457/ipattrappends/ipattrappend|
|-|-|
|请求内容|如下引用|

|-|-|
|响应内容|如下引用|

```
{
	"id": "549281638181011457",
	"type": "ipattrappend",
	"links": {
		"self": "/apis/linkingthing.com/example/v1/restsubnetv4s/1/ipaddresses/549281638181011457/ipattrappends/549281638181011457",
		"update": "/apis/linkingthing.com/example/v1/restsubnetv4s/1/ipaddresses/549281638181011457/ipattrappends/549281638181011457"
	},
	"creationTimestamp": null,
	"deletionTimestamp": null,
	"DeviceTypeFlag": true,
	"BusinessFlag": true,
	"ChargePersonFlag": true,
	"TelFlag": true,
	"DepartmentFlag": true,
	"PositionFlag": true
}
```

#### 2.5 转固定

| 功能     | 描述                                                         |
| -------- | ------------------------------------------------------------ |
| 接口功能 | 添加option                                                   |
| 接口地址 | /apis/linkingthing.com/example/v1/dividedaddresses/:id?action=change |
| 请求方式 | POST                                                         |
| 请求参数 | oper, string, 转换为什么类型 "tostable"(转固定)或"toresv"(转保留) |
|          | data, json字符串, {"macaddress":"xx","ipaddress":"1.1.2.2","subnetv4Id":"542826129599365121","hwAddress":"00:01:02:03:04:05"} |
|          | macaddress, string, 转固定的时候加上                         |
|          | ipaddress, string, ip地址                                    |
|          | subnetv4Id, string, 本ip地址所属的ipv4子网的id               |
|          | hwAddress, string, 转固定地址时，如果类型是硬件地址，要加此项 |
|          |                                                              |
|          | 示例：保留地址的几种配置情况，每一项可以作为一个固定或保留地址<br />"reservations": [<br/>    {<br/>        "hw-address": "aa:bb:cc:dd:ee:ff",<br/>        "hostname": "hw-host-dynamic" <br/>    },{<br/>        "hw-address": "01:02:03:04:05:06",<br/>        "hostname": "hw-host-fixed",<br/>        "ip-address": "192.0.1.77"<br/>    },{<br/>        "client-id":"01:11:22:33:44:55:66",<br/>        "hostname": "client-id-host" <br/>    }<br/>] |
| 请求示例 | curl http://10.0.0.101:8081/apis/linkingthing.com/example/v1/dividedaddresses/544515252269514753?action=change -X POST -d '{<br/>    "oper": "tostable",<br/>    "data": {<br/>       "ipaddress": "1.1.2.7",<br/>        "subnetv4Id": "544515252269514753",<br/>        "hwAddress": "00:01:02:03:04:17"<br/>    }<br/>}' |

- 请求参数意义

| 参数名称 |            | 是否必填 | 数据类型 | 备注                            |
| -------- | ---------- | -------- | -------- | ------------------------------- |
| oper     |            | 是       | 字符串   | 必须是tostable                  |
| data     |            | 是       | 数组     |                                 |
|          | subnetv4Id | 是       | 整型     | 子网id                          |
|          | ipaddress  | 否       | 字符串   | ip地址                          |
|          | hostname   | 否       | 字符串   | 主机名                          |
|          |            |          |          | ipadderss和hostname至少要有一个 |
|          | hwAddress  | 否       | 字符串   | 硬件地址                        |
|          | clientId   | 否       | 字符串   | 客户端id                        |
|          |            |          |          | hwAddress和clientId有且只有一个 |
|          |            |          |          |                                 |



- 返回数据示例

无。默认成功



#### 2.3 转保留

#### 

| 功能     | 描述                                                         |
| -------- | ------------------------------------------------------------ |
| 接口功能 | 把一个地址转为保留地址                                       |
| 接口地址 | /apis/linkingthing.com/example/v1/dividedaddresses/:id?action=change |
| 请求方式 | POST                                                         |
| 请求参数 | oper, string, 转换为什么类型 "tostable"(转固定)或"toresv"(转保留) |
|          | data, json字符串, {"duid":"123456","hostname":"duid-host","subnetv4Id":"542826129599365121"} |
|          |                                                              |
|          |                                                              |
|          |                                                              |
|          |                                                              |
|          | 示例：保留地址的几种配置情况，每一项可以作为一个固定或保留地址<br />"reservations": [<br/>    {<br/>        "hw-address": "aa:bb:cc:dd:ee:ff",<br/>        "hostname": "hw-host-dynamic" <br/>    },{<br/>        "hw-address": "01:02:03:04:05:06",<br/>        "hostname": "hw-host-fixed",<br/>        "ip-address": "192.0.1.77"<br/>    },{<br/>        "duid":"01:02:03:04:05",<br/>        "hostname": "duid-host" <br/>    },{<br/>        "circuit-id": "'charter950'", <br/>        "hostname": "circuit-id-host"<br/>    },{<br/>        "client-id":"01:11:22:33:44:55:66",<br/>        "hostname": "client-id-host" <br/>    }<br/>] |
| 请求示例 | curl http://10.0.0.101:8081/apis/linkingthing.com/example/v1/dividedaddresses/544515252269514753?action=change -X POST -d '{<br/>    "oper": "toresv",<br/>    "data": {<br/>        "ipaddress": "1.1.2.7",<br/>        "subnetv4Id": "547643604375863297",<br/>        "hwAddress": "00:01:02:03:04:17"<br/>    }<br/>}' |

- 请求参数意义

  | 参数名称 |            | 是否必填 | 数据类型 | 备注                             |
  | -------- | ---------- | -------- | -------- | -------------------------------- |
  | oper     |            | 是       | 字符串   | 必须是tostable                   |
  | data     |            | 是       | 数组     |                                  |
  |          | subnetv4Id | 是       | 整型     | 子网id                           |
  |          | hostname   | 是       | 字符串   | 主机名                           |
  |          |            |          |          | ipadderss和hostname至少要有一个  |
  |          | duid       | 否       | 字符串   | 设备唯一id                       |
  |          | circuitId  | 否       | 字符串   | 物理线路的id，转保留地址的参数   |
  |          |            |          |          | hwAddress和circuitId有且只有一个 |
  |          |            |          |          |                                  |

  

- 返回数据示例

无。默认成功



### 3地址扫描

- 接口信息  

|接口描述|获取扫描地址信息|
|-|-|
|请求地址|/apis/linkingthing.com/example/v1/scanaddresses/:scanaddress_id
|请求方式|HTTP/1.1 GET|
|返回格式|JSON|

- 请求参数意义

|参数名称|是否必填|数据类型|备注|
| - |-|-|-|
|scanaddress_id|是|整型|子网id|

- 请求示例

|请求内容|http://10.0.0.19:8081/apis/linkingthing.com/example/v1/scanaddresses/1|
|-|-|
|响应内容|如下引用|

```
{
	"id": "1",
	"type": "scanaddress",
	"links": {
		"self": "/apis/linkingthing.com/example/v1/scanaddresses/1"
	},
	"creationTimestamp": null,
	"deletionTimestamp": null,
	"data": {
		"172.16.86.1": {
			"macaddress": "",
			"macvender": "",
			"AddressType": "collision",
			"opersystem": "",
			"netbiosname": "",
			"hostname": "",
			"interfaceid": "",
			"scaninterfaceid": "",
			"fingerprint": "",
			"leasestarttime": 0,
			"leaseendtime": 0
		},
		"172.16.86.102": {
			"macaddress": "",
			"macvender": "",
			"AddressType": "dead",
			"opersystem": "",
			"netbiosname": "",
			"hostname": "",
			"interfaceid": "",
			"scaninterfaceid": "",
			"fingerprint": "",
			"leasestarttime": 0,
			"leaseendtime": 0
		},
		"172.16.86.12": {
			"macaddress": "",
			"macvender": "",
			"AddressType": "dead",
			"opersystem": "",
			"netbiosname": "",
			"hostname": "",
			"interfaceid": "",
			"scaninterfaceid": "",
			"fingerprint": "",
			"leasestarttime": 0,
			"leaseendtime": 0
		},
		"172.16.86.254": {
			"macaddress": "",
			"macvender": "",
			"AddressType": "collision",
			"opersystem": "",
			"netbiosname": "",
			"hostname": "",
			"interfaceid": "",
			"scaninterfaceid": "",
			"fingerprint": "",
			"leasestarttime": 0,
			"leaseendtime": 0
		}
	}
}
```

|界面元素|响应参数位置|参数类型|参数值举例|
|- | -|-|-|
|冲突地址|collision|string|"172.16.86.254"|
|僵尸地址|dead|string|"172.16.86.102"|



### 4 地址池管理

#### 4.1 添加ipv4地址池

| 功能     | 描述                                                         |
| -------- | ------------------------------------------------------------ |
| 接口功能 | 获取top域名和top ip                                          |
| 接口地址 | /apis/linkingthing.com/example/v1/restsubnetv4s/:subnetv4Id/restpools |
| 请求方式 | POST                                                         |
| 请求参数 | begin-address, string, 地址池开始地址                        |
|          | end-address, string, 地址池结束地址                          |
|          | valid-lifetime, string, 默认租赁时间                         |
|          | max-valid-lifetime, string, 最大租赁时间                     |
|          | gateway, string, 网关                                        |
|          | dnsServer, string, 域名服务器                                |
| 请求示例 | curl http://10.0.0.101:8081/apis/linkingthing.com/example/v1/restsubnetv4s/541134712457986049/restpools -X POST -d '{"beginAddress": "10.0.4.71",<br/>    "endAddress": "10.0.4.73",<br/>    "validLifetime": "2324",<br/>    "maxValidLifetime": "232324",<br/>    "gateway":"1.1.1.3",<br/>    "dnsServer":"2.2.2.3"}' |

- 返回数据示例

{
	"embedded": {
		"id": "542842026496000001",//新建的地址池的id
		"type": "restpool",
		"links": {
			"collection": "/apis/linkingthing/dhcp/v1/restsubnetv4s/542826129599365121/restpools",
			"remove": "/apis/linkingthing/dhcp/v1/restsubnetv4s/542826129599365121/restpools/542842026496000001",
			"self": "/apis/linkingthing/dhcp/v1/restsubnetv4s/542826129599365121/restpools/542842026496000001",
			"update": "/apis/linkingthing/dhcp/v1/restsubnetv4s/542826129599365121/restpools/542842026496000001"
		},
		"creationTimestamp": "2020-04-01T17:17:19+08:00",
		"deletionTimestamp": null
	},
	"subnetv4Id": "547131748367302657",//地址池所在的子网id
	"option-data": null,//option数组，后期补充
	"beginAddress": "101.10.1.41",//开始地址
	"endAddress": "101.10.1.43",//结束地址

  "total": 0,

  "usage": 0,

  "addressType": "",

  "poolName": "",

  "gateway": "1.1.1.1",//网关

  "dnsServer": "2.2.2.2",//域名服务器

​	"maxValidLifetime": "232324",//最大租赁时间
​	"validLifetime": "2324"//默认租赁时间
}



#### 4.2 列出ipv4 pool

#### 

| 功能     | 描述                                                         |
| -------- | ------------------------------------------------------------ |
| 接口功能 | 列出一个子网下的所有地址池                                   |
| 接口地址 | /apis/linkingthing.com/example/v1/restsubnetv4s/:subnetv4Id/restpools |
| 请求方式 | GET                                                          |
|          |                                                              |
| 请求示例 | curl http://10.0.0.101:8081/apis/linkingthing.com/example/v1/restsubnetv4s/541134712457986049/restpools -X GET |

- 请求参数意义

| 参数名称 | 是否必填 | 数据类型 | 备注 |
| -------- | -------- | -------- | ---- |
| 无       |          |          |      |
|          |          |          |      |

- 返回参数意义

| 参数名称          | 是否必填 | 数据类型 | 备注         |
| ----------------- | -------- | -------- | ------------ |
| poolName          | s        | 字符串   | IP地址       |
| total             | 是       | 整数     | 地址总量     |
| addressType       | 是       | 字符串   | 类型         |
| creationTimestamp | 是       | 字符串   | 创建时间     |
| usage             | 是       | 浮点数   | DHCP使用率   |
| validLifetime     | 是       | 整数     | 默认租赁时间 |
| maxValidLifetime  | 是       | 整数     | 最大租赁时间 |
| gateway           | 是       | 字符串   | 路由服务器   |
| dnsServer         | 是       | 字符串   | 域名服务器   |



- 返回数据示例

{
	"type": "collection",
	"resourceType": "restpool",
	"links": {
		"self": "/apis/linkingthing/dhcp/v1/restsubnetv4s/542826129599365121/restpools"
	},
	"data": [{
		"embedded": {
			"id": "542841629383655425",
			"type": "restpool",
			"links": {
				"collection": "/apis/linkingthing/dhcp/v1/restsubnetv4s/542826129599365121/restpools",
				"remove": "/apis/linkingthing/dhcp/v1/restsubnetv4s/542826129599365121/restpools/542841629383655425",
				"self": "/apis/linkingthing/dhcp/v1/restsubnetv4s/542826129599365121/restpools/542841629383655425",
				"update": "/apis/linkingthing/dhcp/v1/restsubnetv4s/542826129599365121/restpools/542841629383655425"
			},
			"creationTimestamp": "2020-04-01T09:15:18Z",
			"deletionTimestamp": null
		},
		"subnetv4Id": "",
		"optionData": null,
		"beginAddress": "101.10.1.31",
		"endAddress": "101.10.1.33",
		"total": 2,
		"usage": 15.32,
		"addressType": "resv",
		"poolName": "101.10.1.31-101.10.1.33"
	}, {
		"embedded": {
			"id": "542842026496000001",
			"type": "restpool",
			"links": {
				"collection": "/apis/linkingthing/dhcp/v1/restsubnetv4s/542826129599365121/restpools",
				"remove": "/apis/linkingthing/dhcp/v1/restsubnetv4s/542826129599365121/restpools/542842026496000001",
				"self": "/apis/linkingthing/dhcp/v1/restsubnetv4s/542826129599365121/restpools/542842026496000001",
				"update": "/apis/linkingthing/dhcp/v1/restsubnetv4s/542826129599365121/restpools/542842026496000001"
			},
			"creationTimestamp": "2020-04-01T09:17:19Z",
			"deletionTimestamp": null
		},
	
		"optionData": null,
		"beginAddress": "101.10.1.41",
		"endAddress": "101.10.1.43",
		"total": 2,
		"usage": 15.32,
		"addressType": "resv",
		"poolName": "101.10.1.41-101.10.1.43"

​      "subnetv4Id": "547131748367302657",

​      "maxValidLifetime": 232324,

​      "validLifetime": 2324,

​      "gateway": "1.1.1.1",

​      "dnsServer": "2.2.2.2"

​	}]
}

#### 4.3 get ipv4 pool



| 功能     | 描述                                                         |
| -------- | ------------------------------------------------------------ |
| 接口功能 | 获取子网下的一个地址池的信息                                 |
| 接口地址 | /apis/linkingthing.com/example/v1/restsubnetv4s/:subnetv4Id/restpools/:poolId |
| 请求方式 | PUT                                                          |
| 请求参数 |                                                              |
|          |                                                              |
| 请求示例 | curl http://10.0.0.101:8081/apis/linkingthing.com/example/v1/restsubnetv4s/541134712457986049/restpools/541703561156001793 -X GET |

- 返回数据示例

  {

  "embedded": {

​    "id": "547372652815679489",

​    "type": "restpool",

​    "links": {

​      "collection": "/apis/linkingthing/dhcp/v1/restsubnetv4s/547131748367302657/restpools",

​      "remove": "/apis/linkingthing/dhcp/v1/restsubnetv4s/547131748367302657/restpools/547372652815679489",

​      "self": "/apis/linkingthing/dhcp/v1/restsubnetv4s/547131748367302657/restpools/547372652815679489",

​      "update": "/apis/linkingthing/dhcp/v1/restsubnetv4s/547131748367302657/restpools/547372652815679489"

​    },

​    "creationTimestamp": "2020-04-17T09:21:16Z",

​    "deletionTimestamp": null

  },

  "subnetv4Id": "547131748367302657",

  "optionData": null,

  "beginAddress": "10.0.4.71",

  "endAddress": "10.0.4.73",

  "total": 3,

  "usage": 0,

  "addressType": "resv",

  "poolName": "10.0.4.71-10.0.4.73",

  "gateway": "1.1.1.1",//网关

  "dnsServer": "2.2.2.2"//域名服务器

}



#### 4.4 修改ipv4 pool



| 功能     | 描述                                                         |
| -------- | ------------------------------------------------------------ |
| 接口功能 | 修改子网下的一个地址池                                       |
| 接口地址 | /apis/linkingthing.com/example/v1/restsubnetv4s/:subnetv4Id/restpools/:poolId |
| 请求方式 | PUT                                                          |
| 请求参数 | beginAddress, string, 地址池开始地址                         |
|          | endAddress, string, 地址池结束地址                           |
|          | validLifetime, string, 默认租赁时间                          |
|          | maxValidLifetime, string, 最大租赁时间                       |
|          | gateway,string,默认网关（应该在子网页面）                    |
|          | dnsServer, string, 域名服务器(应该在子网页面)                |
| 请求示例 | curl http://10.0.0.101:8081/apis/linkingthing.com/example/v1/restsubnetv4s/541134712457986049/restpools/541703561156001793 -X PUT -d '{"beginAddress":"101.10.1.41","endAddress":"101.10.1.43","validLifetime":"23","maxValidLifetime":"3601"}' |

- 返回数据示例

  {
  	"embedded": {
  		"id": "542842026496000001",
  		"type": "restpool",
  		"links": {
  			"collection": "/apis/linkingthing/dhcp/v1/restsubnetv4s/542826129599365121/restpools",
  			"remove": "/apis/linkingthing/dhcp/v1/restsubnetv4s/542826129599365121/restpools/542842026496000001",
  			"self": "/apis/linkingthing/dhcp/v1/restsubnetv4s/542826129599365121/restpools/542842026496000001",
  			"update": "/apis/linkingthing/dhcp/v1/restsubnetv4s/542826129599365121/restpools/542842026496000001"
  		},
  		"creationTimestamp": null,
  		"deletionTimestamp": null
  	},
    "subnetv4Id": "547131748367302657",
  
    "optionData": null,
  
	  "beginAddress": "10.0.4.71",
  
  "endAddress": "10.0.4.73",
  
    "maxValidLifetime": "232324",
  
    "validLifetime": "2324",
  
    "total": 0,
  
    "usage": 0,
  
    "addressType": "",
  
    "poolName": "",
  
    "gateway": "1.1.1.5",
  
    "dnsServer": "2.2.2.5"
  
  }


#### 4.5 删除 ipv4 pool



| 功能     | 描述                                                         |
| -------- | ------------------------------------------------------------ |
| 接口功能 | 删除子网下的一个地址池                                       |
| 接口地址 | /apis/linkingthing.com/example/v1/restsubnetv4s/:subnetv4Id/restpools/:poolId |
| 请求方式 | DELETE                                                       |
| 请求参数 | 无                                                           |
|          |                                                              |
| 请求示例 | curl http://10.0.0.101:8081/apis/linkingthing.com/example/v1/restsubnetv4s/541134712457986049/restpools/541709948222537729  -X DELETE |

- 返回数据示例

  正常没有返回

  如果出错，返回：

  {"code":"ServerError","status":500,"type":"error","message":"unknown subnetv4pool with ID 541059362827632641, record not found"}

#### 4.6 添加ipv6地址池

| 功能     | 描述                                                         |
| -------- | ------------------------------------------------------------ |
| 接口功能 | 获取top域名和top ip                                          |
| 接口地址 | /apis/linkingthing.com/example/v1/restsubnetv6s/:subnetv6Id/restpoolv6s |
| 请求方式 | POST                                                         |
| 请求参数 | begin-address, string, 地址池开始地址                        |
|          | end-address, string, 地址池结束地址                          |
|          |                                                              |
|          |                                                              |
| 请求示例 | curl http://10.0.0.101:8081/apis/linkingthing.com/example/v1/restsubnetv6s/541134712457986049/restpoolv6s -X POST -d '{<br/>    "beginAddress": "fe80:4::2",<br/>    "endAddress": "fe80:4::3"<br/>}' |

- 返回数据示例

{
	"embedded": {
		"id": "542842026496000001",//新建的地址池的id
		"type": "restpool",
		"links": {
			"collection": "/apis/linkingthing/dhcp/v1/restsubnetv4s/542826129599365121/restpools",
			"remove": "/apis/linkingthing/dhcp/v1/restsubnetv4s/542826129599365121/restpools/542842026496000001",
			"self": "/apis/linkingthing/dhcp/v1/restsubnetv4s/542826129599365121/restpools/542842026496000001",
			"update": "/apis/linkingthing/dhcp/v1/restsubnetv4s/542826129599365121/restpools/542842026496000001"
		},
		"creationTimestamp": "2020-04-01T17:17:19+08:00",
		"deletionTimestamp": null
	},
	"subnetv4_id": "",//暂时无用
	"option-data": null,//option数组，后期补充
	"beginAddress": "101.10.1.41",//开始地址
	"endAddress": "101.10.1.43",//结束地址
	"maxValidLifetime": 232324,//最大租赁时间
	"validLifetime": 2324//默认租赁时间
}



#### 4.7 列出ipv6 pool

#### 

| 功能     | 描述                                                         |
| -------- | ------------------------------------------------------------ |
| 接口功能 | 列出一个子网下的所有地址池                                   |
| 接口地址 | /apis/linkingthing.com/example/v1/restsubnetv6s/:subnetv6Id/restpoolv6s |
| 请求方式 | GET                                                          |
|          |                                                              |
| 请求示例 | curl http://10.0.0.101:8081/apis/linkingthing.com/example/v1/restsubnetv6s/541134712457986049/restpoolv6s -X GET |

- 请求参数意义

| 参数名称 | 是否必填 | 数据类型 | 备注 |
| -------- | -------- | -------- | ---- |
| 无       |          |          |      |
|          |          |          |      |

- 返回参数意义

| 参数名称          | 是否必填 | 数据类型 | 备注       |
| ----------------- | -------- | -------- | ---------- |
| poolName          | 是       | 字符串   | IP地址     |
| total             | 是       | 整数     | 地址总量   |
| addressType       | 是       | 字符串   | 类型       |
| creationTimestamp | 是       | 字符串   | 创建时间   |
| usage             | s        | 浮点数   | DHCP使用率 |



- 返回数据示例

{

  "type": "collection",

  "resourceType": "restpoolv6",

  "links": {

​    "self": "/apis/linkingthing.com/example/v1/restsubnetv6s/546740223223005185/restpoolv6s"

  },

  "data": [

​    {

​      "embedded": {

​        "id": "547074725928599553",

​        "type": "restpoolv6",

​        "links": {

​          "collection": "/apis/linkingthing.com/example/v1/restsubnetv6s/546740223223005185/restpoolv6s",

​          "remove": "/apis/linkingthing.com/example/v1/restsubnetv6s/546740223223005185/restpoolv6s/547074725928599553",

​          "self": "/apis/linkingthing.com/example/v1/restsubnetv6s/546740223223005185/restpoolv6s/547074725928599553",

​          "update": "/apis/linkingthing.com/example/v1/restsubnetv6s/546740223223005185/restpoolv6s/547074725928599553"

​        },

​        "creationTimestamp": "2020-04-16T08:05:56Z",

​        "deletionTimestamp": null

​      },

​      "subnetv6Id": "",

​      "optionData": null,

​      "beginAddress": "fe80:4::15",

​      "endAddress": "fe80:4::16",

​      "total": 1,

​      "usage": 15.32,

​      "addressType": "resv",

​      "poolName": "fe80:4::15-fe80:4::16"

​    },

​    {

​      "embedded": {

​        "id": "547074764241993729",

​        "type": "restpoolv6",

​        "links": {

​          "collection": "/apis/linkingthing.com/example/v1/restsubnetv6s/546740223223005185/restpoolv6s",

​          "remove": "/apis/linkingthing.com/example/v1/restsubnetv6s/546740223223005185/restpoolv6s/547074764241993729",

​          "self": "/apis/linkingthing.com/example/v1/restsubnetv6s/546740223223005185/restpoolv6s/547074764241993729",

​          "update": "/apis/linkingthing.com/example/v1/restsubnetv6s/546740223223005185/restpoolv6s/547074764241993729"

​        },

​        "creationTimestamp": "2020-04-16T08:06:08Z",

​        "deletionTimestamp": null

​      },

​      "subnetv6Id": "",

​      "optionData": null,

​      "beginAddress": "fe80:4::2",

​      "endAddress": "fe80:4::3",

​      "total": 1,

​      "usage": 15.32,

​      "addressType": "resv",

​      "poolName": "fe80:4::2-fe80:4::3"

​    }

  ]

}

#### 4.8 修改ipv6 pool



| 功能     | 描述                                                         |
| -------- | ------------------------------------------------------------ |
| 接口功能 | 修改ipv6地址池                                               |
| 接口地址 | /apis/linkingthing.com/example/v1/restsubnetv6s/:subnetv6Id/restpoolv6s/:poolId |
| 请求方式 | PUT                                                          |
| 请求参数 | beginAddress, string, 地址池开始地址                         |
|          | endAddress, string, 地址池结束地址                           |
|          |                                                              |
|          |                                                              |
| 请求示例 | curl http://10.0.0.101:8081/apis/linkingthing.com/example/v1/restsubnetv6s/541134712457986049/restpoolv6s/541703561156001793 -X PUT -d '{<br/>    "beginAddress": "fe80:4::22",<br/>    "endAddress": "fe80:4::23"<br/>}' |

- 返回数据示例

  {
  
    "embedded": {
  
  ​    "id": "547097969365057537",
  
  ​    "type": "restpoolv6",
  
  ​    "links": {
  
  ​      "collection": "/apis/linkingthing.com/example/v1/restsubnetv6s/546740223223005185/restpoolv6s",
  
  ​      "remove": "/apis/linkingthing.com/example/v1/restsubnetv6s/546740223223005185/restpoolv6s/547097969365057537",
  
  ​      "self": "/apis/linkingthing.com/example/v1/restsubnetv6s/546740223223005185/restpoolv6s/547097969365057537",
  
  ​      "update": "/apis/linkingthing.com/example/v1/restsubnetv6s/546740223223005185/restpoolv6s/547097969365057537"
  
  ​    },
  
  ​    "creationTimestamp": null,
  
  ​    "deletionTimestamp": null
  
    },
  
    "subnetv6Id": "",
  
    "optionData": null,
  
    "beginAddress": "fe80:4::22",
  
    "endAddress": "fe80:4::23",
  
    "total": 0,
  
    "usage": 0,
  
    "addressType": "",
  
    "poolName": ""
  
  }


#### 4.9 删除 ipv6 pool



| 功能     | 描述                                                         |
| -------- | ------------------------------------------------------------ |
| 接口功能 | 删除子网下的一个地址池                                       |
| 接口地址 | /apis/linkingthing.com/example/v1/restsubnetv6s/:subnetv6Id/restpoolv6s/:poolId |
| 请求方式 | DELETE                                                       |
| 请求参数 | 无                                                           |
|          |                                                              |
| 请求示例 | curl http://10.0.0.101:8081/apis/linkingthing.com/example/v1/restsubnetv4s/541134712457986049/restpools/541709948222537729  -X DELETE |

- 返回数据示例

  正常没有返回

  如果出错，返回：

  {"code":"ServerError","status":500,"type":"error","message":"unknown subnetv4pool with ID 541059362827632641, record not found"}



### 5 Option管理

#### 5.1 添加option

| 功能     | 描述                                                         |
| -------- | ------------------------------------------------------------ |
| 接口功能 | 添加option                                                   |
| 接口地址 | /apis/linkingthing.com/example/v1/restoptionnames            |
| 请求方式 | POST                                                         |
| 请求参数 | optionVer, string, option的版本 "v4"或"v6"                   |
|          | optionId, int, option序号                                    |
|          | optionName, string, option名称                               |
|          | optionType, string, option类型                               |
| 请求示例 | curl http://10.0.0.101:8081/apis/linkingthing.com/example/v1/restoptionnames -X POST -d '{"optionVer":"v6","optionId":3,"optionName":"name03","optionType":"integer"}' |

- 返回数据示例

{

  "embedded": {

​    "id": "543347579624587265", //id

​    "type": "restoptionname",

​    "links": {

​      "collection": "/apis/linkingthing.com/example/v1/restoptionnames",

​      "remove": "/apis/linkingthing.com/example/v1/restoptionnames/543347579624587265",

​      "update": "/apis/linkingthing.com/example/v1/restoptionnames/543347579624587265"

​    },

​    "creationTimestamp": "2020-04-03T12:08:42+08:00",

​    "deletionTimestamp": null

  },

  "optionVer": "v6", //与请求参数相同

  "optionId": 3,//与请求参数相同

  "optionName": "name03",//与请求参数相同

  "optionType": "integer"//与请求参数相同

}



#### 5.2 option配置页面 (统计信息)

| 功能     | 描述                                                         |
| -------- | ------------------------------------------------------------ |
| 接口功能 | option配置                                                   |
| 接口地址 | /apis/linkingthing.com/example/v1/restoptionnames?action=list |
| 请求方式 | POST                                                         |
| 请求参数 | action, string, 只有一个值 "list"                            |
|          |                                                              |
| 请求示例 | curl http://10.0.0.101:8081/apis/linkingthing.com/example/v1/restoptionnames -X POST -d '{"oper":"list"}' |

- 返回数据示例

{
	"status": "200",//默认成功，是200
	"message": "ok",//暂时无用
	"data": [{
		"optionNotes": "",//备注
		"optionNum": 5,//数量
		"optionName": "DHCP",//名称
		"optionType": "IPv4"//类型
	}, {
		"optionNotes": "",
		"optionNum": 5,
		"optionName": "DHCP",
		"optionType": "IPv4"
	}]
}



#### 5.3 option列表

| 功能     | 描述                                                         |
| -------- | ------------------------------------------------------------ |
| 接口功能 | option列表                                                   |
| 接口地址 | /apis/linkingthing.com/example/v1/restoptionnames            |
| 请求方式 | GET                                                          |
| 请求参数 | 无                                                           |
|          |                                                              |
| 请求示例 | curl http://10.0.0.101:8081/apis/linkingthing.com/example/v1/restoptionnames -X GET |

- 返回数据示例

{

  "type": "collection",

  "resourceType": "restoptionname",

  "links": {

​    "self": "/apis/linkingthing.com/example/v1/restoptionnames"

  },

  "data": [

​    {

​      "embedded": {

​        "id": "543347579624587265",

​        "type": "restoptionname",

​        "links": {

​          "collection": "/apis/linkingthing.com/example/v1/restoptionnames",

​          "remove": "/apis/linkingthing.com/example/v1/restoptionnames/543347579624587265",

​          "update": "/apis/linkingthing.com/example/v1/restoptionnames/543347579624587265"

​        },

​        "creationTimestamp": "2020-04-03T04:08:42Z",

​        "deletionTimestamp": null

​      },

​      "optionVer": "v6",

​      "optionId": 3,

​      "optionName": "name03",

​      "optionType": "integer"

​    },

​    {

​      "embedded": {

​        "id": "543351159456595969",

​        "type": "restoptionname",

​        "links": {

​          "collection": "/apis/linkingthing.com/example/v1/restoptionnames",

​          "remove": "/apis/linkingthing.com/example/v1/restoptionnames/543351159456595969",

​          "update": "/apis/linkingthing.com/example/v1/restoptionnames/543351159456595969"

​        },

​        "creationTimestamp": "2020-04-03T04:26:54Z",

​        "deletionTimestamp": null

​      },

​      "optionVer": "v4",//与5.1请求参数相同

​      "optionId": 2,//与5.1请求参数相同

​      "optionName": "name02",//与5.1请求参数相同

​      "optionType": "integer"//与5.1请求参数相同

​    }

  ]

}



#### 5.4 option编辑

| 功能     | 描述                                                         |
| -------- | ------------------------------------------------------------ |
| 接口功能 | option编辑                                                   |
| 接口地址 | /apis/linkingthing.com/example/v1/restoptionnames/:id        |
| 请求方式 | PUT                                                          |
| 请求参数 | optionVer, string, option的版本 "v4"或"v6"                   |
|          | optionId, int, option序号                                    |
|          | optionName, string, option名称                               |
|          | optionType, string, option类型                               |
| 请求示例 | curl http://10.0.0.101:8081/apis/linkingthing.com/example/v1/restoptionnames/543135023926870017 -X PUT -d '{"optionVer":"v6","optionId":4,"optionName":"name04","optionType":"integer"}' |

- 返回数据示例

{

  "embedded": {

​    "id": "543351159456595969",

​    "type": "restoptionname",

​    "links": {

​      "collection": "/apis/linkingthing.com/example/v1/restoptionnames",

​      "remove": "/apis/linkingthing.com/example/v1/restoptionnames/543351159456595969",

​      "update": "/apis/linkingthing.com/example/v1/restoptionnames/543351159456595969"

​    },

​    "creationTimestamp": null,

​    "deletionTimestamp": null

  },

  "optionVer": "v4",

  "optionId": 1,

  "optionName": "name01",

  "optionType": "integer"

}



#### 5.5 option删除

| 功能     | 描述                                                         |
| -------- | ------------------------------------------------------------ |
| 接口功能 | option删除                                                   |
| 接口地址 | /apis/linkingthing.com/example/v1/restoptionnames/:id        |
| 请求方式 | DELETE                                                       |
| 请求参数 | 无                                                           |
|          |                                                              |
| 请求示例 | curl http://10.0.0.101:8081/apis/linkingthing.com/example/v1/restoptionnames/543135023926870017 -X DELETE |

- 返回数据示例

成功没有任何返回

失败返回各种错误

{"code":"ServerError","status":500,"type":"error","message":"unknown OptionName with ID 543135023926870017, record not found"}

### 6地址规划
#### 6.1 前缀地址校验

- 接口信息

|接口描述|前缀地址校验|
|-|-|
|请求地址|/apis/linkingthing.com/example/v1/checkipv6prefix
|请求方式|HTTP/1.1 POST|
|请求报文体|JSON|
|返回格式|JSON|

- 请求参数意义
请求报文体如下
```
{"prefix":"240e:1122::/30"}
```

|参数名称|是否必填|数据类型|备注|
| - |-|-|-|
|prefix|是|string|ipv6前缀字符串|

- 请求示例

|请求内容|http://10.0.0.19:8081/apis/linkingthing.com/example/v1/checkipv6prefix|
|请求报文体内容|{"prefix":"240e:1122::/30"}|
|-|-|
|响应内容|如下引用|

```
{"prefix":"240e:1120::/30","binary":"00100100000011100001000100100000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000"}
```

|元素|响应参数位置|参数类型|参数值举例|
|- | -|-|-|
|纠正后的ipv6前缀字符串|{"prefix":"240e:1120::/30"}|string|"240e:1120::/30"|

#### 6.2 新增子节点
- 接口信息

|接口描述|新增子节点|
|-|-|
|请求地址|/apis/linkingthing.com/example/v1/createsubtree
|请求方式|HTTP/1.1 POST|
|请求报文体|JSON|
|返回格式|JSON|

- 请求参数意义
请求报文体如下
```
{
    "name":"all",
    "beginsubnet":"240e:1122::/32",
    "endsubnet":"240e:1122::/32",
    "beginnodecode":0,
    "endnodecode":0,
    "depth":0,
    "usedfor":"zone",
    "nodes":[
        {
            "name":"test1",
            "beginnodecode":0,
            "endnodecode":1,
            "usedfor":"business1",
            "nodes":[
                {
                    "name":"test11",
                    "beginnodecode":0,
                    "endnodecode":0
                },
                {
                    "name":"test12",
                    "beginnodecode":1,
                    "endnodecode":1
                },
                {
                    "name":"test13",
                    "beginnodecode":2,
                    "endnodecode":2
                }
            ]
        },
        {
            "name":"test2",
            "beginnodecode":2,
            "endnodecode":3,
            "usedfor":"business2",
            "nodes":[
                {
                    "name":"test21",
                    "beginnodecode":0,
                    "endnodecode":0
                },
                {
                    "name":"test22",
                    "beginnodecode":1,
                    "endnodecode":1
                },
                {
                    "name":"test23",
                    "beginnodecode":2,
                    "endnodecode":2
                }
            ]
        },
        {
            "name":"test3",
            "beginnodecode":4,
            "endnodecode":5,
            "usedfor":"business3",
            "nodes":[
                {
                    "name":"test31",
                    "beginnodecode":0,
                    "endnodecode":0
                },
                {
                    "name":"test32",
                    "beginnodecode":1,
                    "endnodecode":1
                },
                {
                    "name":"test33",
                    "beginnodecode":2,
                    "endnodecode":2
                }
            ]
        }
    ]
}
```

|参数名称|是否必填|数据类型|备注|
| - |-|-|-|
|subnet|是|string|当前节点ipv6子网|
|usedfor|是|string|新开子树节点意义|
|subtreebitnum|是|int|申请使用的bit位数,可有可无,没有的时候表示系统自动生成该值,有值则校验合法后会使用该值,不合法会使用系统自动生成.|
|depth|是|int|新开子树节点深度(头节点深度为0)|
|nodes|是|nodes|子节点数组|
|nodecode|是|string|子节点编码值,可以为不连续的值.|
|NodeName|是|string|子节点名称|

- 请求示例

|请求内容|http://10.0.0.19:8081/apis/linkingthing.com/example/v1/createsubtree|
|请求报文体内容|如下|
```
{
    "name":"all",
    "beginsubnet":"240e:1122::/32",
    "endsubnet":"240e:1122::/32",
    "beginnodecode":0,
    "endnodecode":0,
    "depth":0,
    "usedfor":"zone",
    "nodes":[
        {
            "name":"test1",
            "beginnodecode":0,
            "endnodecode":1,
            "usedfor":"business1",
            "nodes":[
                {
                    "name":"test11",
                    "beginnodecode":0,
                    "endnodecode":0
                },
                {
                    "name":"test12",
                    "beginnodecode":1,
                    "endnodecode":1
                },
                {
                    "name":"test13",
                    "beginnodecode":2,
                    "endnodecode":2
                }
            ]
        },
        {
            "name":"test2",
            "beginnodecode":2,
            "endnodecode":3,
            "usedfor":"business2",
            "nodes":[
                {
                    "name":"test21",
                    "beginnodecode":0,
                    "endnodecode":0
                },
                {
                    "name":"test22",
                    "beginnodecode":1,
                    "endnodecode":1
                },
                {
                    "name":"test23",
                    "beginnodecode":2,
                    "endnodecode":2
                }
            ]
        },
        {
            "name":"test3",
            "beginnodecode":4,
            "endnodecode":5,
            "usedfor":"business3",
            "nodes":[
                {
                    "name":"test31",
                    "beginnodecode":0,
                    "endnodecode":0
                },
                {
                    "name":"test32",
                    "beginnodecode":1,
                    "endnodecode":1
                },
                {
                    "name":"test33",
                    "beginnodecode":2,
                    "endnodecode":2
                }
            ]
        }
    ]
}
```
|-|-|
|响应内容|如下引用|

```
{
	"id": "545170931893010433",
	"name": "all",
	"beginsubnet": "240e:1122::/32",
	"endsubnet": "240e:1122::/32",
	"beginnodecode": 0,
	"endnodecode": 0,
	"subtreebitnum": 3,
	"depth": 0,
	"usedfor": "zone",
	"nodes": [{
		"id": "545170931908280321",
		"name": "test1",
		"beginsubnet": "240e:1122::/35",
		"endsubnet": "240e:1122:2000::/35",
		"beginnodecode": 0,
		"endnodecode": 1,
		"subtreebitnum": 3,
		"depth": 1,
		"usedfor": "business1",
		"nodes": [{
			"id": "545170931918962689",
			"name": "test11",
			"beginsubnet": "240e:1122::/37",
			"endsubnet": "240e:1122::/37",
			"beginnodecode": 0,
			"endnodecode": 0,
			"subtreebitnum": 0,
			"depth": 2,
			"usedfor": "",
			"nodes": null
		}, {
			"id": "545170931925188609",
			"name": "test12",
			"beginsubnet": "240e:1122:800::/37",
			"endsubnet": "240e:1122:800::/37",
			"beginnodecode": 1,
			"endnodecode": 1,
			"subtreebitnum": 0,
			"depth": 2,
			"usedfor": "",
			"nodes": null
		}, {
			"id": "545170931931250689",
			"name": "test13",
			"beginsubnet": "240e:1122:1000::/37",
			"endsubnet": "240e:1122:1000::/37",
			"beginnodecode": 2,
			"endnodecode": 2,
			"subtreebitnum": 0,
			"depth": 2,
			"usedfor": "",
			"nodes": null
		}]
	}, {
		"id": "545170931937476609",
		"name": "test2",
		"beginsubnet": "240e:1122:4000::/35",
		"endsubnet": "240e:1122:6000::/35",
		"beginnodecode": 2,
		"endnodecode": 3,
		"subtreebitnum": 3,
		"depth": 1,
		"usedfor": "business2",
		"nodes": [{
			"id": "545170931946684417",
			"name": "test21",
			"beginsubnet": "240e:1122:4000::/37",
			"endsubnet": "240e:1122:4000::/37",
			"beginnodecode": 0,
			"endnodecode": 0,
			"subtreebitnum": 0,
			"depth": 2,
			"usedfor": "",
			"nodes": null
		}, {
			"id": "545170931951730689",
			"name": "test22",
			"beginsubnet": "240e:1122:4800::/37",
			"endsubnet": "240e:1122:4800::/37",
			"beginnodecode": 1,
			"endnodecode": 1,
			"subtreebitnum": 0,
			"depth": 2,
			"usedfor": "",
			"nodes": null
		}, {
			"id": "545170931957497857",
			"name": "test23",
			"beginsubnet": "240e:1122:5000::/37",
			"endsubnet": "240e:1122:5000::/37",
			"beginnodecode": 2,
			"endnodecode": 2,
			"subtreebitnum": 0,
			"depth": 2,
			"usedfor": "",
			"nodes": null
		}]
	}, {
		"id": "545170931962937345",
		"name": "test3",
		"beginsubnet": "240e:1122:8000::/35",
		"endsubnet": "240e:1122:a000::/35",
		"beginnodecode": 4,
		"endnodecode": 5,
		"subtreebitnum": 3,
		"depth": 1,
		"usedfor": "business3",
		"nodes": [{
			"id": "545170931974078465",
			"name": "test31",
			"beginsubnet": "240e:1122:8000::/37",
			"endsubnet": "240e:1122:8000::/37",
			"beginnodecode": 0,
			"endnodecode": 0,
			"subtreebitnum": 0,
			"depth": 2,
			"usedfor": "",
			"nodes": null
		}, {
			"id": "545170931980271617",
			"name": "test32",
			"beginsubnet": "240e:1122:8800::/37",
			"endsubnet": "240e:1122:8800::/37",
			"beginnodecode": 1,
			"endnodecode": 1,
			"subtreebitnum": 0,
			"depth": 2,
			"usedfor": "",
			"nodes": null
		}, {
			"id": "545170931985874945",
			"name": "test33",
			"beginsubnet": "240e:1122:9000::/37",
			"endsubnet": "240e:1122:9000::/37",
			"beginnodecode": 2,
			"endnodecode": 2,
			"subtreebitnum": 0,
			"depth": 2,
			"usedfor": "",
			"nodes": null
		}]
	}]
}
```

|响应元素|元素意义|响应参数位置|参数类型|参数值举例|
|- |- | -|-|-|
|parentid|父节点编码|{"parentid": "543686093389955073"}|string|"543686093389955073"|
|nodes|子节点编码|{"nodes":[{"id":"543686093397360641"}]}|string|"172.16.86.102"|

#### 6.3删除子树节点

- 接口信息

|接口描述|新增子节点|
|-|-|
|请求地址|/apis/linkingthing.com/example/v1/deletesubtree
|请求方式|HTTP/1.1 DELETE|
|请求报文体|JSON|
|返回格式|JSON|

- 请求参数意义
请求报文体如下
```
{
	"id": "543687537509335041"
}
```

|参数名称|是否必填|数据类型|备注|
| - |-|-|-|
|id|是|string|要删除节点的id|


- 请求示例

|请求内容|http://10.0.0.19:8081/apis/linkingthing.com/example/v1/deletesubtree|
|请求报文体内容|如下|
```
{"id":"543723971361406977"}
```
|-|-|
|响应内容|无|

#### 6.4 查询子树节点

- 接口信息

|接口描述|新增子节点|
|-|-|
|请求地址|/apis/linkingthing.com/example/v1/getsubtree?id=543736063566249985
|请求方式|HTTP/1.1 GET|
|请求报文体|无|
|返回格式|JSON|

|参数名称|是否必填|数据类型|备注|
| - |-|-|-|
|id|是|string|要查询节点的id|

- 请求示例

|请求内容|http://10.0.0.19:8081/apis/linkingthing.com/example/v1/getsubtree?id=543736063566249985|
|-|-|
|响应内容|如下|

```
{
	"id": "545298304795344897",
	"name": "test1",
	"beginsubnet": "240e:1122::/35",
	"endsubnet": "240e:1122:2000::/35",
	"beginnodecode": 0,
	"endnodecode": 1,
	"subtreebitnum": 3,
	"depth": 1,
	"usedfor": "business1",
	"nodes": [{
		"id": "545298304801603585",
		"name": "test11",
		"beginsubnet": "240e:1122::/37",
		"endsubnet": "240e:1122::/37",
		"beginnodecode": 0,
		"endnodecode": 0,
		"subtreebitnum": 0,
		"depth": 2,
		"usedfor": "",
		"nodes": null
	}, {
		"id": "545298304805896193",
		"name": "test12",
		"beginsubnet": "240e:1122:800::/37",
		"endsubnet": "240e:1122:800::/37",
		"beginnodecode": 1,
		"endnodecode": 1,
		"subtreebitnum": 0,
		"depth": 2,
		"usedfor": "",
		"nodes": null
	}, {
		"id": "545298304809926657",
		"name": "test13",
		"beginsubnet": "240e:1122:1000::/37",
		"endsubnet": "240e:1122:1000::/37",
		"beginnodecode": 2,
		"endnodecode": 2,
		"subtreebitnum": 0,
		"depth": 2,
		"usedfor": "",
		"nodes": null
	}, {
		"id": "545298304814252033",
		"name": "剩余资源",
		"beginsubnet": "240e:1122::/37",
		"endsubnet": "240e:1122::/37",
		"beginnodecode": 0,
		"endnodecode": 0,
		"subtreebitnum": 0,
		"depth": 2,
		"usedfor": "",
		"nodes": null
	}]
}
```

|响应元素|元素意义|响应参数位置|参数类型|参数值举例|
|- |- | -|-|-|
|nodes|节点树|{"nodes": [{}]}||
|id|节点ID|{"id":[{"id": "543736063566249985"}]}|string|"543736063566249985"|
|name|节点名称|{"name": "busi3"]}|string|"busi3"|
|subnet|子网|{"subnet": "240e:1122:1002::/41"]}|string|"240e:1122:1002::/41"|
|nodecode|节点值编码|{"id":[{"id": "543736063566249985"}]}|string|"543736063566249985"|
|subtreebitnum|下一级节点位个数|{"subtreebitnum": 0}|string|"0"|
|depth|当前节点深度|{"depth": 2}|string|2|
|usedfor|下一级节点的意义|{"usedfor": "busi"}|string|"busi"|

#### 6.5 更新子树节点

- 接口信息

|接口描述|更新子节点|
|-|-|
|请求地址|/apis/linkingthing.com/example/v1/updatesubtree
|请求方式|HTTP/1.1 POST|
|请求报文体|无|
|返回格式|JSON|

|参数名称|是否必填|数据类型|备注|
| - |-|-|-|
|id|是|string|要更新节点的id|

- 请求示例

|请求内容|http://10.0.0.19:8081/apis/linkingthing.com/example/v1/updatesubtree|
|请求报文体内容|如下|
```
{
   "id": "545172711584989185",
    "name":"all",
    "beginsubnet":"240e:1122::/32",
    "endsubnet":"240e:1122::/32",
    "beginnodecode":0,
    "endnodecode":0,
    "depth":0,
    "usedfor":"zone",
    "nodes":[
        {
            "name":"test1",
            "beginnodecode":0,
            "endnodecode":1,
            "usedfor":"business1",
            "nodes":[
                {
                    "name":"test11",
                    "beginnodecode":0,
                    "endnodecode":0
                },
                {
                    "name":"test12",
                    "beginnodecode":1,
                    "endnodecode":1
                },
                {
                    "name":"test13",
                    "beginnodecode":2,
                    "endnodecode":2
                }
            ]
        },
        {
            "name":"test2",
            "beginnodecode":2,
            "endnodecode":3,
            "usedfor":"business2",
            "nodes":[
                {
                    "name":"test21",
                    "beginnodecode":0,
                    "endnodecode":0
                },
                {
                    "name":"test22",
                    "beginnodecode":1,
                    "endnodecode":1
                },
                {
                    "name":"test23",
                    "beginnodecode":2,
                    "endnodecode":2
                }
            ]
        },
        {
            "name":"test3",
            "beginnodecode":4,
            "endnodecode":5,
            "usedfor":"business3",
            "nodes":[
                {
                    "name":"test31",
                    "beginnodecode":0,
                    "endnodecode":0
                },
                {
                    "name":"test32",
                    "beginnodecode":1,
                    "endnodecode":1
                },
                {
                    "name":"test33",
                    "beginnodecode":2,
                    "endnodecode":2
                }
            ]
        }
    ]
}
```

|-|-|
|响应内容|如下|
```
{
    "id":"545295223778344961",
    "name":"all",
    "beginsubnet":"240e:1122::/32",
    "endsubnet":"240e:1122::/32",
    "beginnodecode":0,
    "endnodecode":0,
    "subtreebitnum":3,
    "depth":0,
    "usedfor":"zone",
    "nodes":[
        {
            "id":"545295223787978753",
            "name":"test1",
            "beginsubnet":"240e:1122::/35",
            "endsubnet":"240e:1122:2000::/35",
            "beginnodecode":0,
            "endnodecode":1,
            "subtreebitnum":3,
            "depth":1,
            "usedfor":"business1",
            "nodes":[
                {
                    "id":"545295223795613697",
                    "name":"test11",
                    "beginsubnet":"240e:1122::/37",
                    "endsubnet":"240e:1122::/37",
                    "beginnodecode":0,
                    "endnodecode":0,
                    "subtreebitnum":0,
                    "depth":2,
                    "usedfor":"",
                    "nodes":null
                },
                {
                    "id":"545295223799578625",
                    "name":"test12",
                    "beginsubnet":"240e:1122:800::/37",
                    "endsubnet":"240e:1122:800::/37",
                    "beginnodecode":1,
                    "endnodecode":1,
                    "subtreebitnum":0,
                    "depth":2,
                    "usedfor":"",
                    "nodes":null
                },
                {
                    "id":"545295223805247489",
                    "name":"test13",
                    "beginsubnet":"240e:1122:1000::/37",
                    "endsubnet":"240e:1122:1000::/37",
                    "beginnodecode":2,
                    "endnodecode":2,
                    "subtreebitnum":0,
                    "depth":2,
                    "usedfor":"",
                    "nodes":null
                }
            ]
        },
        {
            "id":"545295223809900545",
            "name":"test2",
            "beginsubnet":"240e:1122:4000::/35",
            "endsubnet":"240e:1122:6000::/35",
            "beginnodecode":2,
            "endnodecode":3,
            "subtreebitnum":3,
            "depth":1,
            "usedfor":"business2",
            "nodes":[
                {
                    "id":"545295223818420225",
                    "name":"test21",
                    "beginsubnet":"240e:1122:4000::/37",
                    "endsubnet":"240e:1122:4000::/37",
                    "beginnodecode":0,
                    "endnodecode":0,
                    "subtreebitnum":0,
                    "depth":2,
                    "usedfor":"",
                    "nodes":null
                },
                {
                    "id":"545295223822778369",
                    "name":"test22",
                    "beginsubnet":"240e:1122:4800::/37",
                    "endsubnet":"240e:1122:4800::/37",
                    "beginnodecode":1,
                    "endnodecode":1,
                    "subtreebitnum":0,
                    "depth":2,
                    "usedfor":"",
                    "nodes":null
                },
                {
                    "id":"545295223827169281",
                    "name":"test23",
                    "beginsubnet":"240e:1122:5000::/37",
                    "endsubnet":"240e:1122:5000::/37",
                    "beginnodecode":2,
                    "endnodecode":2,
                    "subtreebitnum":0,
                    "depth":2,
                    "usedfor":"",
                    "nodes":null
                }
            ]
        },
        {
            "id":"545295223831494657",
            "name":"test3",
            "beginsubnet":"240e:1122:8000::/35",
            "endsubnet":"240e:1122:a000::/35",
            "beginnodecode":4,
            "endnodecode":5,
            "subtreebitnum":3,
            "depth":1,
            "usedfor":"business3",
            "nodes":[
                {
                    "id":"545295223840047105",
                    "name":"test31",
                    "beginsubnet":"240e:1122:8000::/37",
                    "endsubnet":"240e:1122:8000::/37",
                    "beginnodecode":0,
                    "endnodecode":0,
                    "subtreebitnum":0,
                    "depth":2,
                    "usedfor":"",
                    "nodes":null
                },
                {
                    "id":"545295223844864001",
                    "name":"test32",
                    "beginsubnet":"240e:1122:8800::/37",
                    "endsubnet":"240e:1122:8800::/37",
                    "beginnodecode":1,
                    "endnodecode":1,
                    "subtreebitnum":0,
                    "depth":2,
                    "usedfor":"",
                    "nodes":null
                },
                {
                    "id":"545295223849091073",
                    "name":"test33",
                    "beginsubnet":"240e:1122:9000::/37",
                    "endsubnet":"240e:1122:9000::/37",
                    "beginnodecode":2,
                    "endnodecode":2,
                    "subtreebitnum":0,
                    "depth":2,
                    "usedfor":"",
                    "nodes":null
                }
            ]
        }
    ]
}
```
|响应元素|元素意义|响应参数位置|参数类型|参数值举例|
|- |- | -|-|-|
|nodes|节点树|{"nodes": [{}]}||
|id|节点ID,更新后全部会改变|{"id":[{"id": "543736063566249985"}]}|string|"543736063566249985"|
|name|节点名称|{"name": "busi3"]}|string|"busi3"|
|subnet|子网|{"subnet": "240e:1122:1002::/41"]}|string|"240e:1122:1002::/41"|
|nodecode|节点值编码|{"id":[{"id": "543736063566249985"}]}|string|"543736063566249985"|
|subtreebitnum|下一级节点位个数|{"subtreebitnum": 0}|string|"0"|
|depth|当前节点深度|{"depth": 2}|string|2|
|usedfor|下一级节点的意义|{"usedfor": "busi"}|string|"busi"|
