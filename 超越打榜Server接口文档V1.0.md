# 超越打榜Server接口文档V1.0
1. 接口请求格式规范

> 服务侧提供Restful格式的https接口，请求和返回的统一使用json格式，utf-8编码，示例：
* `url:https:chaoyuedabang.com/hello`
* 
```
request:{
"key1":"value1",
"key2":"value2"
}
```
* 
```
response:{
"returnCode":"0",
"returnDesc":"success"
}
```
2. API接口
* get
* post
1. 用户登陆
```
request:
| 字段名   | 类型   | 是否可选（M为必选O为可选）   | 描述   | 
|:----|:----|:----|:----|
| userName   | String(64)   | M   | 用户登陆账号   | 
| password   | String(64)   | M   | 用户登陆密码   | 
| ifAdmin   | boolean   | O   | 是否为管理员登陆   | 

response:
| 字段名 | 类型 | 是否可选（M为必选O为可选） | 描述 | 
|
| returnCode | String(16) | M | 返回码，返回码代表的信息看第三章 | 
| returnDesc | String(64) | M | 返回描述 | 
| accessToken | String(256) | M | 用户登陆Token，客户端保存并在，需要登陆后操作的接口请求中携带此token，使用RSA256签名加密 | 
```

2. 管理员添加渠道信息
3. 应答码
```
returnCode的值对应的成功或失败原因如下图所示
| 0   | 成功   | 
|:----|:----|
| 1   | 参数错误   | 
| 2   | 不分情况的服务侧内部错误   | 
| 3   | 第三方接口错误   | 
|    |    | 
|    |    | 
```

