## BaseUrl: 139.9.211.248:8040
## 用户相关
### 用户登陆
url :     /index/dologin?username=#{username}&password=#{password}
请求方法:  get

RequestBody:

|参数名|参数类型|是否必填|备注|
|-----|-----|-----|-----|
|username|string|是|用户名:默认admin|
|password|string|是|用户密码:默认123456|

ResponseBody:
```json
{
    "message": "Ok",
    "code": 200,
    "data": {
        "user": {
            "userId": "admin",
            "userName": "admin",
            "userPassword": "123456",
            "userPhone": null,
            "userEmail": null,
            "userRemark": null
        }
    }
}
```
### 用户注册
url :     /UserController/addUser
请求方法:  post

RequestBody:

|参数名|参数类型|是否必填|备注|
|-----|-----|-----|-----|
|userName|string|是|用户名|
|userPassoword|string|是|用户密码|
|userPhone|string|是|手机号|
|userEmail|string|是|邮箱|
|userRemark|string|否|备注|

ResponseBody:
```json
{
    "message": "Ok",
    "code": 200,
    "data": {
        "user": {
            "userId": "324010869689670173470127425348768",
            "userName": "zhangsan",
            "userPassword": "123456",
            "userPhone": "123456",
            "userEmail": "546725246@qq.com",
            "userRemark": ""
        }
    }
}
```

### 修改用户
url :     /UserController/updateUser
请求方法:  put

RequestBody:

|参数名|参数类型|是否必填|备注|
|-----|-----|-----|-----|
|userId|string|是|用户ID|
|userName|string|是|用户名|
|userPassoword|string|是|用户密码|
|userPhone|string|是|手机号|
|userEmail|string|是|邮箱|
|userRemark|string|否|备注|

ResponseBody:
```json
{
    "message": "Ok",
    "code": 200,
    "data": {
        "user": {
            "userId": "324010869689670173470127425348768",
            "userName": "zhangsan",
            "userPassword": "123456",
            "userPhone": "123456",
            "userEmail": "546725246@qq.com",
            "userRemark": ""
        }
    }
}
```

## 节点相关

### 添加用户节点
url: /UserNodeController/addUserNode
请求方法: post

RequestBody:

|参数名|参数类型|是否必填|备注|
|-----|-----|-----|-----|
|userId|string|是|用户ID|
|nodeNumber|string|是|节点编号|
|nodeName|string|是|节点名称|
|nodeMac|string|是|节点地址|
|nodeHeartBeat|string|是|心跳包，默认为1|
|nodeDb|string|是|增益放大倍数，默认为1|
|nodeMiddleHz|string|是|中值频率，默认为00|
|nodeDb2|string|是|2路信号增益放大倍数，默认为1|
|nodeMiddleHz2|string|是|2路信号中值频率，默认为00|
|analysisId|string|是|分析序列号，默认为1|
|nodeRemark|string|否|节点备注信息|


ResponseBody:
```
{
    "message": "Ok",
    "code": 200,
    "data": {}
}
```

### 删除用户节点

url: /UserNodeController/deleteUserNode?userId=#{userId}&nodeId=#{nodeId}
请求方法：delete

ResponseBody:
```
{
    "message": "Ok",
    "code": 200,
    "data": {}
}
```

### 修改用户节点
url: /UserNodeController/updateUserNode
请求方法: put

RequestBody:

|参数名|参数类型|是否必填|备注|
|-----|-----|-----|-----|
|nodeId|string|是|节点Id|
|nodeNumber|string|是|节点编号|
|nodeName|string|是|节点名称|
|nodeMac|string|是|节点地址|
|nodeHeartBeat|string|是|心跳包，默认为1|
|nodeDb|string|是|增益放大倍数，默认为1|
|nodeMiddleHz|string|是|中值频率，默认为00|
|nodeDb2|string|是|2路信号增益放大倍数，默认为1|
|nodeMiddleHz2|string|是|2路信号中值频率，默认为00|
|analysisId|string|是|分析序列号，默认为1|
|nodeRemark|string|否|节点备注信息|


ResponseBody:
```
{
    "message": "Ok",
    "code": 200,
    "data": {}
}
```

### 查询用户节点
url: /UserNodeController/getUserNode?userId=#{userId}
请求方法: get


ResponseBody:
```
{
    "message": "Ok",
    "code": 200,
    "data": {
        "nodes": [
            {
                "nodeId": "612841076180541734182459943747570007",
                "nodeNumber": "2号节点",
                "nodeName": "1号节点",
                "nodeLastCommandId": "1",
                "nodeCommandId": "1",
                "nodeStateId": "612841076180541734182459943747570007",
                "nodeRemark": "123",
                "analysisId": "1",
                "nodeMac": "0007",
                "nodeMiddleHz": "00",
                "nodeDb": "332",
                "nodeMiddleHz2": null,
                "nodeDb2": null,
                "nodeLastMac": null,
                "nodeHeartBeat": "1",
                "receive": false
            }
        ]
    }
}
```

## 数据分析

### 新建一次分析

url: /analysisController/analysis
请求方法: post

RequestBody:

|参数名|参数类型|是否必填|备注|
|-----|-----|-----|-----|
|userId|string|是|用户ID|
|analysisName|string|是|分析描述|
|analysisRemark|string|是|分析备注|
|nodeId|string[]|是|节点ID列表|

ResponseBody:
```
{
    "message": "Ok",
    "code": 200,
    "data": {}
}
```

### 查询全部分析

url: /analysisController/analysis?userId=#{userId}
请求方法: get

ResponseBody:
```
{
    "message": "Ok",
    "code": 200,
    "data": {
        "analysisList": [
            {
                "analysisId": "134040503430573173481601784302730",
                "analysisDescribe": "无数",
                "analysisRemark": "haha",
                "userId": "admin",
                "analysisCreateTime": 1578885021000
            },
            {
                "analysisId": "145261988552352173477682116675517",
                "analysisDescribe": "无数",
                "analysisRemark": "haha",
                "userId": "admin",
                "analysisCreateTime": 1578896242000
            },
            {
                "analysisId": "6063538699153800173495521454588247",
                "analysisDescribe": "A0",
                "analysisRemark": "校验",
                "userId": "admin",
                "analysisCreateTime": 1574318714000
            }
        ]
    }
}
```

### 删除一次分析
url: /analysisController/analysis?analysisId=#{analysisId}
请求方法:delete


ResponseBody:
```
{
    "message": "Ok",
    "code": 200,
    "data": {}
}
```

### 查询一次分析下的全部节点
url: /analysisNodeController/analysisNode?analysisId=134040503430573173481601784302730
请求方法:get

ResponseBody:
```
{
    "message": "Ok",
    "code": 200,
    "data": {
        "nodeList": [
            {
                "nodeId": "612841076180541734182459943747570007",
                "nodeNumber": "2号节点",
                "nodeName": "1号节点",
                "nodeLastCommandId": "1",
                "nodeCommandId": "1",
                "nodeStateId": "612841076180541734182459943747570007",
                "nodeRemark": "123",
                "analysisId": "145261988552352173477682116675517",
                "nodeMac": "0007",
                "nodeMiddleHz": "00",
                "nodeDb": "332",
                "nodeMiddleHz2": null,
                "nodeDb2": null,
                "nodeLastMac": null,
                "nodeHeartBeat": "1",
                "receive": false
            }
        ]
    }
}
```
