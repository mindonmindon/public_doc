# mttt api

## 1. 图稿列表

get	/api/v1/image

query:

| 参数名      | 值   | 注释        |
| ----------- | ---- | ----------- |
| category_id |      | 分类id      |
| page        |      | 分页 第几页 |

reponse:

```json5
{
  // 0-成功， 非0-失败
  "code": 0,
  "message": "",
  "data": {
    "list": [
      {
        // id
        "pid": "39e65899ef784840ad887a3361303b1d",
        // 分类id
        "category_id": "39e65899ef784840ad887a3361303b1d",
        // 图稿类型, 1-mftt类型 2-lltt类型
        "load_type": 2,
        // 真彩图预览地址
        "preview": "https://xxx.xxx/xxxx.png",
        // 线稿图预览地址
        "gray_preview": "https://xxx.xxx/xxxx.png",
        // 客户端支持最小版本
        "support_version": 1.0,
        // 是否推荐，0-否 1-是
        "is_recommend": 1,
        // 是否新上的图，0-否 1-是
        "is_new": 1
      }
    ],
    "page": 1,
    "size": 5,
    "total": 1
  }
}
```

PS:

1. load_type不同时， 图标在原图位置配置文件 json文件结构不同, 1-mftt类型 2-lltt类型
2. 图标在原图位置的原点不同， mftt-原图中心点， lltt-原图左上角
3. mftt类型时，无背景图地址，背景图为精灵图第一张， lltt有背景图
4. mftt无真彩图预览地址， lltt有真彩图预览地址



## 2. 图稿详情

get	/api/v1/image/<图稿pid>

reponse:

```json5
{
  // 0-成功， 非0-失败
  "code": 0,
  "message": "",
  "data": {
    "pid": "39e65899ef784840ad887a3361303b1d",
    // 分类id
    "category_id": "39e65899ef784840ad887a3361303b1d",
    // 图稿类型, 1-mftt类型 2-lltt类型
    "load_type": 2,
    // 预览真彩图地址
    "preview": "https://xxx.xxx/xxxx.png",
    // 预览线稿图地址
    "gray_preview": "https://xxx.xxx/xxxx.png",
    // 精灵图地址
    "sprite": "https://xxx.xxx/xxxx.png",
    // 精灵图plist地址
    "sprite_plist": "https://xxx.xxx/xxxx.plist",
    // 图标在原图位置配置文件 json文件
    "position": "https://xxx.xxx/xxxx.json",
    // 背景图地址 。1-mftt类型时，无背景图地址，背景图为精灵图第一张
    "background": "https://xxx.xxx/xxxx.png",
    // 客户端支持最小版本
    "support_version": 1.0,
    // 是否推荐 0-否 1-是
    "is_recommend": 1,
    // 是否新上的图
    "is_new": 1
  }
}
```

PS:

1. load_type不同时， 图标在原图位置配置文件 json文件结构不同, 1-mftt类型 2-lltt类型

2. 图标在原图位置的原点不同， mftt-原图中心点， lltt-原图左上角

3. mftt类型时，无背景图地址，背景图为精灵图第一张， lltt有背景图

4. mftt无真彩图预览地址， lltt有真彩图预览地址

   


# 3. 图稿分类列表

get	/api/v1/imageCategory

reponse:

```json5
{
  // 0-成功， 非0-失败
  "code": 0,
  "message": "",
  "data": {
    "list": [
      {
        // id
        "pid": "39e65899ef784840ad887a3361303b1d",
        // 分类名称
        "name": "二次元",
        // 权重
        "sort": "100",
        // 客户端支持最小版本
        "support_version": 1.0
      },
      {
        "pid": "8e44d7d14466450eb59e49265a8bdaa2",
        "name": "Q萌",
        "sort": "88",
        "support_version": 1.0
      }
    ]
  }
}
```

