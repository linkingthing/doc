# dhcp模块接口文档



# 所有接口

| 模块   | 序号 | 方法   | 接口                                                         | 表单 | 菜单 | 描述                         |
| ------ | ---- | ------ | ------------------------------------------------------------ | ---- | ---- | ---------------------------- |
| v4子网 |      |        |                                                              |      |      |                              |
|        | 1.1  | GET    | apis/linkingthing/dhcp/v1/subnetv4s                          | 无   |      | 获取dhcpv4的子网列表         |
|        | 1.2  | POST   | apis/linkingthing/dhcp/v1/subnetv4s                          |      |      | 新建dhcpv4子网               |
|        | 1.3  | GET    | apis/linkingthing/dhcp/v1/subnetv4s/:id                      |      |      | 获得dhcpv4子网的详情         |
|        | 1.4  | PUT    | apis/linkingthing/dhcp/v1/subnetv4s/:id                      |      |      | 修改dhcpv4子网               |
|        | 1.5  | delete | apis/linkingthing/dhcp/v1/subnetv4s/:id                      |      |      | 删除dhcpv4子网               |
|        |      |        |                                                              |      |      |                              |
|        | 1.6  | GET    | /apis/linkingthing/dhcp/v1/subnetv4s/:id/restreservations    |      |      | 列出某个子网下的所有保留地址 |
|        | 1.7  | POST   | /apis/linkingthing/dhcp/v1/subnetv4s/:id/restreservations    |      |      | 新增v4保留地址               |
|        | 1.8  | GET    | /apis/linkingthing/dhcp/v1/subnetv4s/:id/restreservations/:id |      |      | 获取v4保留地址的详情         |
|        | 1.9  | POST   | /apis/linkingthing/dhcp/v1/subnetv4s/:id/restreservations/:id |      |      | 修改v4保留地址               |
|        | 1.10 | DELETE | /apis/linkingthing/dhcp/v1/subnetv4s/:id/restreservations/:id |      |      | 删除v4保留地址               |
|        |      |        |                                                              |      |      |                              |
|        | 1.11 | GET    | /apis/linkingthing/dhcp/v1/subnetv4s/:id/pools               |      |      | 列出某个子网下的所有地址池   |
|        | 1.12 | POST   | /apis/linkingthing/dhcp/v1/subnetv4s/:id/pools               |      |      | 新增v4地址池                 |
|        | 1.13 | GET    | /apis/linkingthing/dhcp/v1/subnetv4s/:id/pools/:id           |      |      | 获取v4保留地址的详情         |
|        | 1.14 | PUT    | /apis/linkingthing/dhcp/v1/subnetv4s/:id/pools/:id           |      |      | 修改v4地址池                 |
|        | 1.15 | DELETE | /apis/linkingthing/dhcp/v1/subnetv4s/:id/pools/:id           |      |      | 删除v4保留地址               |
| v6子网 |      |        |                                                              |      |      |                              |
|        | 1.1  | GET    | apis/linkingthing/dhcp/v1/subnetv6s                          | 无   |      | 获取dhcpv6的子网列表         |
|        |      |        |                                                              |      |      |                              |

## 一、dhcpv4

### 1.1 列出dhcpv4子网列表

- 接口信息  

| 接口描述 | 列出dhcpv4子网列表                  |
| -------- | ----------------------------------- |
| 请求地址 | apis/linkingthing/dhcp/v1/subnetv4s |
| 请求方式 | HTTP/1.1 GET                        |
| 返回格式 | JSON                                |

- 请求参数意义

| 参数名称 | 是否必填 | 数据类型 | 备注 |
| -------- | -------- | -------- | ---- |
|          |          |          |      |

- 请求示例

| 请求内容 | http://10.0.0.15:1234/apis/linkingthing/dhcp/v1/subnetv4s |
| -------- | --------------------------------------------------------- |
| 响应内容 | 如下引用                                                  |

```
{
	"type": "collection",
	"resourceType": "subnetv4",
	"links": {
		"self": "/apis/linkingthing/dhcp/v1/subnetv4s"
	},
	"data": [{
		"type": "subnetv4",
		"links": {
			"collection": "/apis/linkingthing/dhcp/v1/subnetv4s"
		},
		"creationTimestamp": null,
		"subnet": "222",
		"validLifeTime": "23"
	}, {
		"type": "subnetv4",
		"links": {
			"collection": "/apis/linkingthing/dhcp/v1/subnetv4s"
		},
		"creationTimestamp": null,
		"subnet": "222",
		"validLifeTime": "233"
	}]
}
```

| 界面元素 | 响应参数位置 | 参数类型 | 参数值举例 |      |
| -------- | ------------ | -------- | ---------- | ---- |
|          |              |          |            |      |
|          |              |          |            |      |



### 1.2 新建dhcpv4子网

- 接口信息  

| 接口描述 | 新建dhcpv4子网                      |
| -------- | ----------------------------------- |
| 请求地址 | apis/linkingthing/dhcp/v1/subnetv4s |
| 请求方式 | HTTP/1.1 POST                       |
| 返回格式 | JSON                                |

- 请求参数意义

| 参数名称      | 是否必填 | 数据类型 | 备注            |
| ------------- | -------- | -------- | --------------- |
| subnet        | 是       | string   | 名称            |
| validLifeTime | 否       | string   | valid-life-time |

- 请求示例

| 请求内容 | http://10.0.0.15:1234/apis/linkingthing/dhcp/v1/subnetv4s |
| -------- | --------------------------------------------------------- |
| 响应内容 | 如下引用                                                  |

```
{
	"embedded": {
		"id": "cde",
		"type": "subnetv4",
		"links": {
			"collection": "/apis/linkingthing/dhcp/v1/subnetv4s",
			"remove": "/apis/linkingthing/dhcp/v1/subnetv4s/cde",
			"restreservations": "/apis/linkingthing/dhcp/v1/subnetv4s/cde/restreservations",
			"self": "/apis/linkingthing/dhcp/v1/subnetv4s/cde",
			"update": "/apis/linkingthing/dhcp/v1/subnetv4s/cde"
		},
		"creationTimestamp": "2020-02-14T16:51:46+08:00"
	},
	"subnet": "cde",
	"validLifeTime": "",
	"Reservations": null,
	"Pools": null
}
```

| 界面元素 | 响应参数位置 | 参数类型 | 参数值举例 |      |
| -------- | ------------ | -------- | ---------- | ---- |
|          |              |          |            |      |
|          |              |          |            |      |

### 1.3 获取dhcpv4子网详情

- 接口信息  

| 接口描述 | 获取dhcpv4子网详情                      |
| -------- | --------------------------------------- |
| 请求地址 | apis/linkingthing/dhcp/v1/subnetv4s/:id |
| 请求方式 | HTTP/1.1 GET                            |
| 返回格式 | JSON                                    |

- 请求参数意义

| 参数名称 | 是否必填 | 数据类型 | 备注 |
| -------- | -------- | -------- | ---- |
| id       | 是       |          |      |

- 请求示例

| 请求内容 |          |
| -------- | -------- |
| 响应内容 | 如下引用 |

```

```

| 界面元素 | 响应参数位置 | 参数类型 | 参数值举例 |      |
| -------- | ------------ | -------- | ---------- | ---- |
|          |              |          |            |      |
|          |              |          |            |      |





### 1.4 修改dhcpv4子网

- 接口信息  

| 接口描述 | 新建dhcpv4子网                      |
| -------- | ----------------------------------- |
| 请求地址 | apis/linkingthing/dhcp/v1/subnetv4s |
| 请求方式 | HTTP/1.1 POST                       |
| 返回格式 | JSON                                |

- 请求参数意义

| 参数名称 | 是否必填 | 数据类型 | 备注 |
| -------- | -------- | -------- | ---- |
| 无       |          |          |      |

- 请求示例

| 请求内容 |          |
| -------- | -------- |
| 响应内容 | 如下引用 |

```

```

| 界面元素 | 响应参数位置 | 参数类型 | 参数值举例 |      |
| -------- | ------------ | -------- | ---------- | ---- |
|          |              |          |            |      |
|          |              |          |            |      |



## 二、dhcpv6

### 2.1 列出dhcpv6子网列表

- 接口信息  

| 接口描述 | 列出dhcpv4子网列表                  |
| -------- | ----------------------------------- |
| 请求地址 | apis/linkingthing/dhcp/v1/subnetv6s |
| 请求方式 | HTTP/1.1 GET                        |
| 返回格式 | JSON                                |

- 请求参数意义

| 参数名称 | 是否必填 | 数据类型 | 备注 |
| -------- | -------- | -------- | ---- |
|          |          |          |      |

- 请求示例

| 请求内容 | http://10.0.0.15:1234/apis/linkingthing/dhcp/v1/subnetv6s |
| -------- | --------------------------------------------------------- |
| 响应内容 | 如下引用                                                  |

```
{
	"type": "collection",
	"resourceType": "subnetv4",
	"links": {
		"self": "/apis/linkingthing/dhcp/v1/subnetv4s"
	},
	"data": [{
		"type": "subnetv4",
		"links": {
			"collection": "/apis/linkingthing/dhcp/v1/subnetv4s"
		},
		"creationTimestamp": null,
		"subnet": "222",
		"validLifeTime": "23"
	}, {
		"type": "subnetv4",
		"links": {
			"collection": "/apis/linkingthing/dhcp/v1/subnetv4s"
		},
		"creationTimestamp": null,
		"subnet": "222",
		"validLifeTime": "233"
	}]
}
```

| 界面元素 | 响应参数位置 | 参数类型 | 参数值举例 |      |
| -------- | ------------ | -------- | ---------- | ---- |
|          |              |          |            |      |
|          |              |          |            |      |

