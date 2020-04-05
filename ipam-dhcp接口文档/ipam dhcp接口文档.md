## ipam dhcp接口文档



## 全局设置：

- 所有的变量类型都是字符串或整数
- 接口暂定，联调时候继续优化。



### 1 子网管理

#### 1.1 添加ipv4子网

| 功能     | 描述                                                         |
| -------- | ------------------------------------------------------------ |
| 接口功能 | 获取top域名和top ip                                          |
| 接口地址 | /apis/linkingthing.com/example/v1/restsubnetv4s              |
| 请求方式 | POST                                                         |
| 请求参数 | subnet, string, 子网地址                                     |
|          | name, 类型 string,子网地址                                   |
|          | gateway, 类型 string, 网关地址 //暂时不生效，后期补充        |
| 请求示例 | curl http://10.0.0.101:8081/apis/linkingthing.com/example/v1/restsubnetv4s -X POST -d '{"subnet":"10.0.1.0/24", "name":"name2", "validLifetime":"3600"}' |

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
	"total": "",//地址数量
	"usage": ""//子网地址使用率
}



#### 1.2 列出ipv4子网

| 功能     | 描述                                                         |
| -------- | ------------------------------------------------------------ |
| 接口功能 | 列出当前所有的子网                                           |
| 接口地址 | /apis/linkingthing.com/example/v1/restsubnetv4s              |
| 请求方式 | POST                                                         |
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
​		"usage": "0.00"
​	}]
}

#### 1.3 修改ipv4子网

| 功能     | 描述                                                         |
| -------- | ------------------------------------------------------------ |
| 接口功能 | 修改ipv4子网信息                                             |
| 接口地址 | /apis/linkingthing.com/example/v1/restsubnetv4s/:subnetv4Id  |
| 请求方式 | POST                                                         |
| 请求参数 | 无                                                           |
| 请求示例 | curl http://10.0.0.101:8081/apis/linkingthing.com/example/v1/restsubnetv4s/541122915319513089 -X PUT -d '{"subnet":"192.168.1.35/24", "name":"name352", "validLifeTime":"352"}' |
|          |                                                              |

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

}

#### 1.4 删除ipv4子网

| 功能     | 描述                                                         |
| -------- | ------------------------------------------------------------ |
| 接口功能 | 删除ipv4子网                                                 |
| 接口地址 | /apis/linkingthing.com/example/v1/restsubnetv4s/:subnetv4Id  |
| 请求方式 | POST                                                         |
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



### 2规划地址展示
- 接口信息  

|接口描述|获取规划地址信息|
|-|-|
|请求地址|/apis/linkingthing.com/example/v1/dividedaddresses/:dividedaddress_id
|请求方式|HTTP/1.1 GET|
|返回格式|JSON|

- 请求参数意义

|参数名称|是否必填|数据类型|备注|
| - |-|-|-|
|dividedaddress_id|是|整型|子网id|

- 请求示例

|请求内容|http://10.0.0.19:8081/apis/linkingthing.com/example/v1/dividedaddresses/1|
|-|-|
|响应内容|如下引用|

```
{
	"id": "1",
	"type": "dividedaddress",
	"links": {
		"self": "/apis/linkingthing.com/example/v1/dividedaddresses/1"
	},
	"creationTimestamp": null,
	"deletionTimestamp": null,
	"data": {
		"172.16.86.1": {
			"macaddress": "",
			"macvender": "",
			"AddressType": "stable",
			"opersystem": "",
			"netbiosname": "",
			"hostname": "",
			"interfaceid": "",
			"scaninterfaceid": "",
			"fingerprint": "",
			"leasestarttime": 0,
			"leaseendtime": 0
		},
		"172.16.86.10": {
			"macaddress": "",
			"macvender": "",
			"AddressType": "dynamic",
			"opersystem": "",
			"netbiosname": "",
			"hostname": "",
			"interfaceid": "",
			"scaninterfaceid": "",
			"fingerprint": "",
			"leasestarttime": 0,
			"leaseendtime": 0
		},
		"172.16.86.100": {
			"macaddress": "",
			"macvender": "",
			"AddressType": "lease",
			"opersystem": "",
			"netbiosname": "",
			"hostname": "",
			"interfaceid": "",
			"scaninterfaceid": "",
			"fingerprint": "",
			"leasestarttime": 0,
			"leaseendtime": 0
		},
		"172.16.86.101": {
			"macaddress": "",
			"macvender": "",
			"AddressType": "lease",
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
			"AddressType": "lease",
			"opersystem": "",
			"netbiosname": "",
			"hostname": "",
			"interfaceid": "",
			"scaninterfaceid": "",
			"fingerprint": "",
			"leasestarttime": 0,
			"leaseendtime": 0
		},
...
		"172.16.86.202": {
			"macaddress": "",
			"macvender": "",
			"AddressType": "unused",
			"opersystem": "",
			"netbiosname": "",
			"hostname": "",
			"interfaceid": "",
			"scaninterfaceid": "",
			"fingerprint": "",
			"leasestarttime": 0,
			"leaseendtime": 0
		},
		"172.16.86.203": {
			"macaddress": "",
			"macvender": "",
			"AddressType": "unused",
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
|保留地址|reserved|string|"172.16.86.206"|
|动态地址|dynamic|string|"172.16.86.3"|
|固定地址|stable|string|"172.16.86.1"|
|手动地址|manual|string|"172.16.86.210"|
|已分配地址|lease|string|"172.16.86.103"|
|未使用地址|unused|string|"172.16.86.203"|
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
| 请求示例 | curl http://10.0.0.101:8081/apis/linkingthing.com/example/v1/restsubnetv4s/541134712457986049/restpools -X POST -d '{"beginAddress": "10.0.7.61", "endAddress": "10.0.7.63","validLifetime":2324,"maxValidLifetime":232324}' |

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



#### 4.2 列出ipv4 pool

#### 

| 功能     | 描述                                                         |
| -------- | ------------------------------------------------------------ |
| 接口功能 | 列出一个子网下的所有地址池                                   |
| 接口地址 | /apis/linkingthing.com/example/v1/restsubnetv4s/:subnetv4Id/restpools |
| 请求方式 | GET                                                          |
| 请求参数 | begin-address, string, 地址池开始地址                        |
|          |                                                              |
| 请求示例 | curl http://10.0.0.101:8081/apis/linkingthing.com/example/v1/restsubnetv4s/541134712457986049/restpools -X GET |

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
			"creationTimestamp": null,
			"deletionTimestamp": null
		},
		"subnetv4Id": "",
		"option-data": null,
		"beginAddress": "101.10.1.31",
		"endAddress": "101.10.1.33"
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
			"creationTimestamp": null,
			"deletionTimestamp": null
		},	

​    "subnetv4Id": "",//暂时无用
​	"optionData": null,//option数组，后期补充
​	"beginAddress": "101.10.1.41",//开始地址
​	"endAddress": "101.10.1.43",//结束地址
​	"maxValidLifetime": 232324,//最大租赁时间
​	"validLifetime": 2324//默认租赁时间
​	}]
}



#### 4.3 修改ipv4 pool



| 功能     | 描述                                                         |
| -------- | ------------------------------------------------------------ |
| 接口功能 | 修改子网下的一个地址池                                       |
| 接口地址 | /apis/linkingthing.com/example/v1/restsubnetv4s/:subnetv4Id/restpools/:poolId |
| 请求方式 | PUT                                                          |
| 请求参数 | beginAddress, string, 地址池开始地址                         |
|          | endAddress, string, 地址池结束地址                           |
|          | validLifetime, int, 默认租赁时间                             |
|          | maxValidLifetime, int, 最大租赁时间                          |
| 请求示例 | curl http://10.0.0.101:8081/apis/linkingthing.com/example/v1/restsubnetv4s/541134712457986049/restpools/541703561156001793 -X PUT -d '{"beginAddress":"101.10.1.41","endAddress":"101.10.1.43","validLifetime":23,"maxValidLifetime":3601}' |

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
  	"subnetv4Id": "",
  	"optionData": null,
  	"beginAddress": "101.10.1.41",
  	"endAddress": "101.10.1.43",
	"maxValidLifetime": 3601,
  	"validLifetime": 23
}
  


#### 4.4 删除 ipv4 pool



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
{"prefix":"240e:1120::/30"}
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
	"name": "all",
	"subnet": "240e:1122::/32",
	"nodecode": 0,

	"depth": 0,
	"usedfor": "zone",
	"nodes": [{
		"name": "test1",
		"nodecode": 0,
		"subtreebitnum": 3,
		"usedfor": "business1",
		"nodes": [{
			"name": "test11",
			"nodecode": 0
		}, {
			"name": "test12",
			"nodecode": 1
		}, {
			"name": "test13",
			"nodecode": 2
		}]
	}, {
		"name": "test2",
		"nodecode": 1,

		"usedfor": "business2",
		"nodes": [{
			"name": "test21",
			"nodecode": 0
		}, {
			"name": "test22",
			"nodecode": 1
		}, {
			"name": "test23",
			"nodecode": 2
		}]
	}, {
		"name": "test3",
		"nodecode": 2,

		"usedfor": "business3",
		"nodes": [{
			"name": "test31",
			"nodecode": 0
		}, {
			"name": "test32",
			"nodecode": 1
		}, {
			"name": "test33",
			"nodecode": 2
		}]
	}]
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
	"name": "all",
	"subnet": "240e:1122::/32",
	"nodecode": 0,

	"depth": 0,
	"usedfor": "zone",
	"nodes": [{
		"name": "test1",
		"nodecode": 0,
		"subtreebitnum": 3,
		"usedfor": "business1",
		"nodes": [{
			"name": "test11",
			"nodecode": 0
		}, {
			"name": "test12",
			"nodecode": 1
		}, {
			"name": "test13",
			"nodecode": 2
		}]
	}, {
		"name": "test2",
		"nodecode": 1,

		"usedfor": "business2",
		"nodes": [{
			"name": "test21",
			"nodecode": 0
		}, {
			"name": "test22",
			"nodecode": 1
		}, {
			"name": "test23",
			"nodecode": 2
		}]
	}, {
		"name": "test3",
		"nodecode": 2,

		"usedfor": "business3",
		"nodes": [{
			"name": "test31",
			"nodecode": 0
		}, {
			"name": "test32",
			"nodecode": 1
		}, {
			"name": "test33",
			"nodecode": 2
		}]
	}]
}
```
|-|-|
|响应内容|如下引用|

```
{
	"id": "544045009172070401",
	"name": "all",
	"subnet": "240e:1122::/32",
	"nodecode": 0,
	"subtreebitnum": 4,
	"depth": 0,
	"usedfor": "zone",
	"nodes": [{
		"id": "544045009197826049",
		"name": "test1",
		"subnet": "240e:1122::/36",
		"nodecode": 0,
		"subtreebitnum": 4,
		"depth": 1,
		"usedfor": "business1",
		"nodes": [{
			"id": "544045009220960257",
			"name": "test11",
			"subnet": "240e:1122::/40",
			"nodecode": 0,
			"subtreebitnum": 1,
			"depth": 2,
			"usedfor": "",
			"nodes": null
		}, {
			"id": "544045009226498049",
			"name": "test12",
			"subnet": "240e:1122:2::/40",
			"nodecode": 1,
			"subtreebitnum": 1,
			"depth": 2,
			"usedfor": "",
			"nodes": null
		}, {
			"id": "544045009232789505",
			"name": "test13",
			"subnet": "240e:1122:4::/40",
			"nodecode": 2,
			"subtreebitnum": 1,
			"depth": 2,
			"usedfor": "",
			"nodes": null
		}]
	}, {
		"id": "544045009238622209",
		"name": "test2",
		"subnet": "240e:1122:2000::/36",
		"nodecode": 1,
		"subtreebitnum": 4,
		"depth": 1,
		"usedfor": "business2",
		"nodes": [{
			"id": "544045009259724801",
			"name": "test21",
			"subnet": "240e:1122:2000::/40",
			"nodecode": 0,
			"subtreebitnum": 1,
			"depth": 2,
			"usedfor": "",
			"nodes": null
		}, {
			"id": "544045009265164289",
			"name": "test22",
			"subnet": "240e:1122:2002::/40",
			"nodecode": 1,
			"subtreebitnum": 1,
			"depth": 2,
			"usedfor": "",
			"nodes": null
		}, {
			"id": "544045009270800385",
			"name": "test23",
			"subnet": "240e:1122:2004::/40",
			"nodecode": 2,
			"subtreebitnum": 1,
			"depth": 2,
			"usedfor": "",
			"nodes": null
		}]
	}, {
		"id": "544045009276305409",
		"name": "test3",
		"subnet": "240e:1122:4000::/36",
		"nodecode": 2,
		"subtreebitnum": 4,
		"depth": 1,
		"usedfor": "business3",
		"nodes": [{
			"id": "544045009297997825",
			"name": "test31",
			"subnet": "240e:1122:4000::/40",
			"nodecode": 0,
			"subtreebitnum": 1,
			"depth": 2,
			"usedfor": "",
			"nodes": null
		}, {
			"id": "544045009303633921",
			"name": "test32",
			"subnet": "240e:1122:4002::/40",
			"nodecode": 1,
			"subtreebitnum": 1,
			"depth": 2,
			"usedfor": "",
			"nodes": null
		}, {
			"id": "544045009308745729",
			"name": "test33",
			"subnet": "240e:1122:4004::/40",
			"nodecode": 2,
			"subtreebitnum": 1,
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
|请求报文体内容|{"id":"543723971361406977"}|
|-|-|
|响应内容|如下|
```
{
	"id": "543990284628230145",
	"name": "test3",
	"subnet": "240e:1122:8000::/35",
	"nodecode": 2,
	"subtreebitnum": 3,
	"depth": 1,
	"usedfor": "business3",
	"nodes": [{
		"id": "543990284650020865",
		"name": "test31",
		"subnet": "240e:1122:8000::/38",
		"nodecode": 0,
		"subtreebitnum": 0,
		"depth": 2,
		"usedfor": "",
		"nodes": null
	}, {
		"id": "543990284655230977",
		"name": "test32",
		"subnet": "240e:1122:8800::/38",
		"nodecode": 1,
		"subtreebitnum": 0,
		"depth": 2,
		"usedfor": "",
		"nodes": null
	}, {
		"id": "543990284660539393",
		"name": "test33",
		"subnet": "240e:1122:9000::/38",
		"nodecode": 2,
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

|接口描述|新增子节点|
|-|-|
|请求地址|/apis/linkingthing.com/example/v1/updatesubtree
|请求方式|HTTP/1.1 POST|
|请求报文体|无|
|返回格式|JSON|

|参数名称|是否必填|数据类型|备注|
| - |-|-|-|
|id|是|string|要查询节点的id|

- 请求示例

|请求内容|http://10.0.0.19:8081/apis/linkingthing.com/example/v1/updatesubtree|
|请求报文体内容|如下|
```
{
	"id": "544045009172070401",
	"name": "all",
	"subnet": "240e:1122::/32",
	"nodecode": 0,
	"depth": 0,
	"usedfor": "zone",
	"nodes": [{
		"name": "test1",
		"nodecode": 0,
		"usedfor": "business1",
		"nodes": [{
			"name": "test11",
			"nodecode": 0
		}, {
			"name": "test12",
			"nodecode": 1
		}, {
			"name": "test13",
			"nodecode": 2
		}]
	}, {
		"name": "test2",
		"nodecode": 1,
		"usedfor": "business2",
		"nodes": [{
			"name": "test21",
			"nodecode": 0
		}, {
			"name": "test22",
			"nodecode": 1
		}, {
			"name": "test23",
			"nodecode": 2
		}]
	}, {
		"name": "test3",
		"nodecode": 2,
		"usedfor": "business3",
		"nodes": [{
			"name": "test31",
			"nodecode": 0
		}, {
			"name": "test32",
			"nodecode": 1
		}, {
			"name": "test33",
			"nodecode": 2
		}]
	}]
}
```

|-|-|
|响应内容|如下|
```
{
	"id": "544045504174358529",
	"name": "all",
	"subnet": "240e:1122::/32",
	"nodecode": 0,
	"subtreebitnum": 3,
	"depth": 0,
	"usedfor": "zone",
	"nodes": [{
		"id": "544045504191168513",
		"name": "test1",
		"subnet": "240e:1122::/35",
		"nodecode": 0,
		"subtreebitnum": 3,
		"depth": 1,
		"usedfor": "business1",
		"nodes": [{
			"id": "544045504209190913",
			"name": "test11",
			"subnet": "240e:1122::/38",
			"nodecode": 0,
			"subtreebitnum": 0,
			"depth": 2,
			"usedfor": "",
			"nodes": null
		}, {
			"id": "544045504213450753",
			"name": "test12",
			"subnet": "240e:1122:800::/38",
			"nodecode": 1,
			"subtreebitnum": 0,
			"depth": 2,
			"usedfor": "",
			"nodes": null
		}, {
			"id": "544045504217120769",
			"name": "test13",
			"subnet": "240e:1122:1000::/38",
			"nodecode": 2,
			"subtreebitnum": 0,
			"depth": 2,
			"usedfor": "",
			"nodes": null
		}]
	}, {
		"id": "544045504221511681",
		"name": "test2",
		"subnet": "240e:1122:4000::/35",
		"nodecode": 1,
		"subtreebitnum": 3,
		"depth": 1,
		"usedfor": "business2",
		"nodes": [{
			"id": "544045504236191745",
			"name": "test21",
			"subnet": "240e:1122:4000::/38",
			"nodecode": 0,
			"subtreebitnum": 0,
			"depth": 2,
			"usedfor": "",
			"nodes": null
		}, {
			"id": "544045504239960065",
			"name": "test22",
			"subnet": "240e:1122:4800::/38",
			"nodecode": 1,
			"subtreebitnum": 0,
			"depth": 2,
			"usedfor": "",
			"nodes": null
		}, {
			"id": "544045504243924993",
			"name": "test23",
			"subnet": "240e:1122:5000::/38",
			"nodecode": 2,
			"subtreebitnum": 0,
			"depth": 2,
			"usedfor": "",
			"nodes": null
		}]
	}, {
		"id": "544045504247562241",
		"name": "test3",
		"subnet": "240e:1122:8000::/35",
		"nodecode": 2,
		"subtreebitnum": 3,
		"depth": 1,
		"usedfor": "business3",
		"nodes": [{
			"id": "544045504264404993",
			"name": "test31",
			"subnet": "240e:1122:8000::/38",
			"nodecode": 0,
			"subtreebitnum": 0,
			"depth": 2,
			"usedfor": "",
			"nodes": null
		}, {
			"id": "544045504268402689",
			"name": "test32",
			"subnet": "240e:1122:8800::/38",
			"nodecode": 1,
			"subtreebitnum": 0,
			"depth": 2,
			"usedfor": "",
			"nodes": null
		}, {
			"id": "544045504272564225",
			"name": "test33",
			"subnet": "240e:1122:9000::/38",
			"nodecode": 2,
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
|nodes|节点树|{"nodes": [{}]}||
|id|节点ID,更新后全部会改变|{"id":[{"id": "543736063566249985"}]}|string|"543736063566249985"|
|name|节点名称|{"name": "busi3"]}|string|"busi3"|
|subnet|子网|{"subnet": "240e:1122:1002::/41"]}|string|"240e:1122:1002::/41"|
|nodecode|节点值编码|{"id":[{"id": "543736063566249985"}]}|string|"543736063566249985"|
|subtreebitnum|下一级节点位个数|{"subtreebitnum": 0}|string|"0"|
|depth|当前节点深度|{"depth": 2}|string|2|
|usedfor|下一级节点的意义|{"usedfor": "busi"}|string|"busi"|
