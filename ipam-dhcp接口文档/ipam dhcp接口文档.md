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



### 2规划地址展示
- 接口信息  

|接口描述|获取视图信息|
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

界面元素|响应参数位置|参数类型|参数值举例|
- | -|-|-|
保留地址|reserved|string|"172.16.86.206"|
动态地址|dynamic|string|"172.16.86.3"|
固定地址|stable|string|"172.16.86.1"|
手动地址|manual|string|"172.16.86.210"|
已分配地址|lease|string|"172.16.86.103"|
### 3地址扫描

- 接口信息  

|接口描述|获取视图信息|
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

界面元素|响应参数位置|参数类型|参数值举例|
- | -|-|-|
冲突地址|collision|string|"172.16.86.254"|
僵尸地址|dead|string|"172.16.86.102"|



### 4 地址池管理

#### 4.1 添加ipv4地址池

| 功能     | 描述                                                         |
| -------- | ------------------------------------------------------------ |
| 接口功能 | 获取top域名和top ip                                          |
| 接口地址 | /apis/linkingthing.com/example/v1/subnetv4s/:subnetv4Id/restpools |
| 请求方式 | POST                                                         |
| 请求参数 | begin-address, string, 地址池开始地址                        |
|          | end-address, string, 地址池结束地址                          |
|          | valid-lifetime, string, 默认租赁时间                         |
|          | max-valid-lifetime, string, 最大租赁时间                     |
| 请求示例 | curl http://10.0.0.101:8081/apis/linkingthing.com/example/v1/restsubnetv4s/541134712457986049/restpools -X POST -d '{"begin-address": "10.0.7.61", "end-address": "10.0.7.63","valid-lifetime":2324,"max-valid-lifetime":232324}' |

- 返回数据示例

{
	"embedded": {
		"id": "541181942501539841", //新建的地址池的id
		"type": "restpool",
		"links": {
			"collection": "/apis/linkingthing/dhcp/v1/restsubnetv4s/541177423683059713/restpools",
			"remove": "/apis/linkingthing/dhcp/v1/restsubnetv4s/541177423683059713/restpools/541181942501539841",
			"self": "/apis/linkingthing/dhcp/v1/restsubnetv4s/541177423683059713/restpools/541181942501539841",
			"update": "/apis/linkingthing/dhcp/v1/restsubnetv4s/541177423683059713/restpools/541181942501539841"
		},
		"creationTimestamp": "2020-03-26T20:33:42+08:00",
		"deletionTimestamp": null
	},
	"subnetv4_id": "", //暂时无用
	"option-data": null, //option数组，后期补充
	"begin-address": "10.0.7.61", //开始地址
	"end-address": "10.0.7.63" //结束地址

"max-valid-lifetime":232324, //最大租赁时间

"valid-lifetime":2324 //默认租赁时间

}



#### 4.2 列出ipv4 pool

#### 

| 功能     | 描述                                                         |
| -------- | ------------------------------------------------------------ |
| 接口功能 | 列出一个子网下的所有地址池                                   |
| 接口地址 | /apis/linkingthing.com/example/v1/subnetv4s/:subnetv4Id/restpools |
| 请求方式 | GET                                                          |
| 请求参数 | begin-address, string, 地址池开始地址                        |
|          |                                                              |
| 请求示例 | curl http://10.0.0.101:8081/apis/linkingthing.com/example/v1/restsubnetv4s/541134712457986049/restpools -X GET |

- 返回数据示例

{
	"type": "collection",
	"resourceType": "restpool",
	"links": {
		"self": "/apis/linkingthing/dhcp/v1/restsubnetv4s/541177423683059713/restpools"
	},
	"data": [{
		"embedded": {
			"id": "541177599701876737",
			"type": "restpool",
			"links": {
				"collection": "/apis/linkingthing/dhcp/v1/restsubnetv4s/541177423683059713/restpools",
				"remove": "/apis/linkingthing/dhcp/v1/restsubnetv4s/541177423683059713/restpools/541177599701876737",
				"self": "/apis/linkingthing/dhcp/v1/restsubnetv4s/541177423683059713/restpools/541177599701876737",
				"update": "/apis/linkingthing/dhcp/v1/restsubnetv4s/541177423683059713/restpools/541177599701876737"
			},
			"creationTimestamp": null,
			"deletionTimestamp": null
		},
		"subnetv4_id": "",
		"option-data": null,
		"begin-address": "10.0.7.31",
		"end-address": "10.0.7.33"
	}, {
		"embedded": {
			"id": "541180482764046337",
			"type": "restpool",
			"links": {
				"collection": "/apis/linkingthing/dhcp/v1/restsubnetv4s/541177423683059713/restpools",
				"remove": "/apis/linkingthing/dhcp/v1/restsubnetv4s/541177423683059713/restpools/541180482764046337",
				"self": "/apis/linkingthing/dhcp/v1/restsubnetv4s/541177423683059713/restpools/541180482764046337",
				"update": "/apis/linkingthing/dhcp/v1/restsubnetv4s/541177423683059713/restpools/541180482764046337"
			},
			"creationTimestamp": null,
			"deletionTimestamp": null
		},
		"subnetv4_id": "",
		"option-data": null,
		"begin-address": "10.0.7.31",
		"end-address": "10.0.7.33"
	}, {
		"embedded": {
			"id": "541180985772277761",
			"type": "restpool",
			"links": {
				"collection": "/apis/linkingthing/dhcp/v1/restsubnetv4s/541177423683059713/restpools",
				"remove": "/apis/linkingthing/dhcp/v1/restsubnetv4s/541177423683059713/restpools/541180985772277761",
				"self": "/apis/linkingthing/dhcp/v1/restsubnetv4s/541177423683059713/restpools/541180985772277761",
				"update": "/apis/linkingthing/dhcp/v1/restsubnetv4s/541177423683059713/restpools/541180985772277761"
			},
			"creationTimestamp": null,
			"deletionTimestamp": null
		},
		"subnetv4_id": "",
		"option-data": null,
		"begin-address": "10.0.7.35",
		"end-address": "10.0.7.43"
	}, {
		"embedded": {
			"id": "541181152339394561",
			"type": "restpool",
			"links": {
				"collection": "/apis/linkingthing/dhcp/v1/restsubnetv4s/541177423683059713/restpools",
				"remove": "/apis/linkingthing/dhcp/v1/restsubnetv4s/541177423683059713/restpools/541181152339394561",
				"self": "/apis/linkingthing/dhcp/v1/restsubnetv4s/541177423683059713/restpools/541181152339394561",
				"update": "/apis/linkingthing/dhcp/v1/restsubnetv4s/541177423683059713/restpools/541181152339394561"
			},
			"creationTimestamp": null,
			"deletionTimestamp": null
		},
		"subnetv4_id": "",
		"option-data": null,
		"begin-address": "10.0.7.51",
		"end-address": "10.0.7.53"
	}, {
		"embedded": {
			"id": "541181942501539841",
			"type": "restpool",
			"links": {
				"collection": "/apis/linkingthing/dhcp/v1/restsubnetv4s/541177423683059713/restpools",
				"remove": "/apis/linkingthing/dhcp/v1/restsubnetv4s/541177423683059713/restpools/541181942501539841",
				"self": "/apis/linkingthing/dhcp/v1/restsubnetv4s/541177423683059713/restpools/541181942501539841",
				"update": "/apis/linkingthing/dhcp/v1/restsubnetv4s/541177423683059713/restpools/541181942501539841"
			},
			"creationTimestamp": null,
			"deletionTimestamp": null
		},
		"subnetv4_id": "",
		"option-data": null,
		"begin-address": "10.0.7.61",
		"end-address": "10.0.7.63"
	}]
}



#### 4.3 修改ipv4 pool



| 功能     | 描述                                                         |
| -------- | ------------------------------------------------------------ |
| 接口功能 | 修改子网下的一个地址池                                       |
| 接口地址 | /apis/linkingthing.com/example/v1/subnetv4s/:subnetv4Id/restpools/:poolId |
| 请求方式 | PUT                                                          |
| 请求参数 | begin-address, string, 地址池开始地址                        |
|          | end-address, string, 地址池结束地址                          |
|          | valid-lifetime, string, 默认租赁时间                         |
|          | max-valid-lifetime, string, 最大租赁时间                     |
| 请求示例 | curl http://10.0.0.101:8081/apis/linkingthing.com/example/v1/restsubnetv4s/541134712457986049/restpools/541703561156001793 -X PUT -d '{"begin-address": "10.0.6.20","end-address": "10.0.6.27","valid-lifetime":2325,"max-valid-lifetime":232325}' |

- 返回数据示例

  {
  	"embedded": {
  		"id": "541181942501539841",
  		"type": "restpool",
  		"links": {
  			"collection": "/apis/linkingthing/dhcp/v1/restsubnetv4s/540777754924679169/restpools",
  			"remove": "/apis/linkingthing/dhcp/v1/restsubnetv4s/540777754924679169/restpools/541181942501539841",
  			"self": "/apis/linkingthing/dhcp/v1/restsubnetv4s/540777754924679169/restpools/541181942501539841",
  			"update": "/apis/linkingthing/dhcp/v1/restsubnetv4s/540777754924679169/restpools/541181942501539841"
  		},
  		"creationTimestamp": null,
  		"deletionTimestamp": null
  	},
  	"subnetv4_id": "11",
  	"option-data": null,
  	"begin-address": "10.0.7.61",
  	"end-address": "10.0.7.66",

  "max-valid-lifetime":232325,

  "valid-lifetime":2325

  }

  

#### 4.4 删除 ipv4 pool



| 功能     | 描述                                                         |
| -------- | ------------------------------------------------------------ |
| 接口功能 | 删除子网下的一个地址池                                       |
| 接口地址 | /apis/linkingthing.com/example/v1/subnetv4s/:subnetv4Id/restpools/:poolId |
| 请求方式 | DELETE                                                       |
| 请求参数 | 无                                                           |
|          |                                                              |
| 请求示例 | curl http://10.0.0.101:8081/apis/linkingthing.com/example/v1/restsubnetv4s/541134712457986049/restpools/541709948222537729  -X DELETE |

- 返回数据示例

  正常没有返回

  如果出错，返回：

  {"code":"ServerError","status":500,"type":"error","message":"unknown subnetv4pool with ID 541059362827632641, record not found"}





