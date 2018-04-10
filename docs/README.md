# 艾道校宣API文档

## 当前可用版本
```
V1
```

## API Endpoint
测试环境:
```
TBD
```
生产环境:
```
TBD
```

## 请求规范
### Header
#### 身份验证

客户端访问API时，需要使用```序列号```和```设备Key```进行Base64编码

```
echo -n "serial:key" | base64
```
身份验证部分格式如下：
```
Authorization: Basic QUMyNzU2Mjk1NTcwOjU3YTIwYWJkYTE5MzFhMTc1NzE0NGQwYQ==
```

#### API版本号

客户端请求时，需指定请求的API版本号

如请求V1版本:

```
Accept: application/vnd.ada-box.v1+json
```

#### 应用版本号

客户端请求时，需要发送当前应用版本号

```
AdaCampus-App-Version: 1.0.0
```

#### 守护进程版本号

客户端请求时，需要发送当前应用版本号

```
AdaCampus-Watcher-Version: 1.2.5
```

#### 传递表单

如需传递表单，Header需要加上Content-Type

```
Content-Type: application/json
```

## 错误信息

如请求出现错误时，将会返回标准HTTP状态码以及应用错误码

[详细应用错误码](errorcode.md)

```
401 Unauthorized
```

```json
{
    "error_code": 1003,
    "message": "未提供认证Header"
}
```
