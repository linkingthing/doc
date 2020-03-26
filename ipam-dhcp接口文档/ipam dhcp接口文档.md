## ipam dhcp接口文档



## 全局设置：

- 所有的变量类型都是字符串或整数
- 接口暂定，联调时候继续优化。



### 1 子网管理

#### 1.1 添加子网

| 功能     | 描述                                                         |
| -------- | ------------------------------------------------------------ |
| 接口功能 | 获取top域名和top ip                                          |
| 接口地址 | /apis/linkingthing.com/example/v1/subnetv4s                  |
| 请求方式 | POST                                                         |
| 请求参数 | 无                                                           |
|          | name, 类型 string                                            |
|          | gateway, 类型 string //暂时不生效，后期补充                  |
| 请求示例 | curl http://10.0.0.101:8081/apis/linkingthing.com/example/v1/subnetv4s -X POST -d '{"subnet":"10.0.1.0/24", "name":"name2"}' |

- 返回数据示例

{
	"embedded": {
		"id": "538928061063856129",  //新创建的子网的资源id
		"type": "subnetv4",
		"links": {
			"collection": "/apis/linkingthing/dhcp/v1/subnetv4s",
			"remove": "/apis/linkingthing/dhcp/v1/subnetv4s/538928061063856129",
			"restreservations": "/apis/linkingthing/dhcp/v1/subnetv4s/538928061063856129/restreservations",
			"self": "/apis/linkingthing/dhcp/v1/subnetv4s/538928061063856129",
			"update": "/apis/linkingthing/dhcp/v1/subnetv4s/538928061063856129"
		},
		"creationTimestamp": "2020-03-18T21:29:52+08:00",
		"deletionTimestamp": null
	},
	"name": "name8", //子网名称
	"subnet": "10.0.8.0/24", //子网地址
	"subnet_id": "538928061063856129",
	"validLifeTime": "", //暂时忽略
	"Reservations": null,
	"Pools": null
}



#### 1.2 列出子网

| 功能     | 描述                                                         |
| -------- | ------------------------------------------------------------ |
| 接口功能 | 列出当前所有的子网                                           |
| 接口地址 | /apis/linkingthing/dhcp/v1/subnetv4s                         |
| 请求方式 | POST                                                         |
| 请求参数 | 无                                                           |
|          |                                                              |
| 请求示例 | curl http://10.0.0.101:8081/apis/linkingthing.com/example/v1/subnetv4s -X GET |

- 返回数据示例

{
	"type": "collection",
	"resourceType": "subnetv4",
	"links": {
		"self": "/apis/linkingthing/dhcp/v1/subnetv4s"
	},
	"data": [{
		"embedded": {
			"id": "538926576168599553",//子网id
			"type": "subnetv4",
			"links": {
				"collection": "/apis/linkingthing/dhcp/v1/subnetv4s",
				"remove": "/apis/linkingthing/dhcp/v1/subnetv4s/538926576168599553",
				"restreservations": "/apis/linkingthing/dhcp/v1/subnetv4s/538926576168599553/restreservations",
				"self": "/apis/linkingthing/dhcp/v1/subnetv4s/538926576168599553",
				"update": "/apis/linkingthing/dhcp/v1/subnetv4s/538926576168599553"
			},
			"creationTimestamp": null,
			"deletionTimestamp": null
		},
		"subnet": "10.0.7.0/24", //子网地址
		"subnet_id": "538926576168599553", //子网id
		"validLifeTime": "",
		"Reservations": null,
		"Pools": null
	}, {
		"embedded": {
			"id": "538928061063856129",
			"type": "subnetv4",
			"links": {
				"collection": "/apis/linkingthing/dhcp/v1/subnetv4s",
				"remove": "/apis/linkingthing/dhcp/v1/subnetv4s/538928061063856129",
				"restreservations": "/apis/linkingthing/dhcp/v1/subnetv4s/538928061063856129/restreservations",
				"self": "/apis/linkingthing/dhcp/v1/subnetv4s/538928061063856129",
				"update": "/apis/linkingthing/dhcp/v1/subnetv4s/538928061063856129"
			},
			"creationTimestamp": null,
			"deletionTimestamp": null
		},
		"subnet": "10.0.8.0/24",
		"subnet_id": "538928061063856129",
		"validLifeTime": "",
		"Reservations": null,
		"Pools": null
	}]
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