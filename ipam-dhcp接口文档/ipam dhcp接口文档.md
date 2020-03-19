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




