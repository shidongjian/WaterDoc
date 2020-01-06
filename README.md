## BaseUrl: 139.9.211.248:8040
## 用户相关
### 用户登陆
url :     /index/dologin
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
