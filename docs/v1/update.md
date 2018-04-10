# 应用升级

## 检查更新

```
GET /device/update
```

#### 请求参数

| 名称 | 类型 | 说明 | 必填 | 例子 |
| -- | -- | -- | -- | -- |
| version | string | APP当前版本号 | 是 | 1.0.0 |

#### 返回值说明

| 名称 | 类型 | 说明 | 例子 |
| -- | -- | -- | -- |
| need_upgrade | boolean | 是否需要更新 | true |
| version | string | 最新版本 | "1.0.1" |
| url | string | 下载地址 | true |
| task_id | integer | 兼容性字段 | 1 |

#### 请求例子

```
GET /device/update?version=1.0.0
```

#### 响应例子

```json
{
    "need_upgrade": true,
    "version": "1.0.1",
    "url": "https://www.abc.com/update.apk",
    "task_id": 1
}
```

## 升级结果提交

```
POST /device/update_result
```

#### 请求参数说明

请求Body应为JSON字符串

| 名称 | 类型 | 说明 | 必填 | 例子 |
| -- | -- | -- | -- | -- |
| result | integer | 升级结果。0表示成功，1表示失败 | 是 | 0 |
| desc | string | 详细信息，提供用于Debug的信息 | 否 | 'success' |
| from | string | 升级前版本 | 否 | '1.0.0' |
| to | string | 升级后版本 | 是 | '1.0.1' |
| task_id | integer | 兼容性字段 | 否 | 1 |

#### 请求例子

```json
{
    "result": 0,
    "desc": "success",
    "from": "1.0.0",
    "to": "1.0.1",
    "task_id": 1
}
```

#### 响应例子

成功状态码

```
201 Created
```
