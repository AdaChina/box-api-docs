# 播放列表

## 获取播放素材

```
GET /playlist
```

#### 返回值说明

| 名称 | 类型 | 说明 | 例子 |
| -- | -- | -- | -- |
| type | string | 素材类型 | image |
| url | string | 素材地址 | a.com/b.png |
| duration | integer | 图片停留时长/视频时长（秒） | 180 |

#### 响应例子

```json
[
    {
        "type": "image",
        "url": "https://abc.com/1.png",
        "duration": 20
    },
    {
        "type": "video",
        "url": "https://abc.com/2.mp4",
        "duration": 132
    }
]
```
