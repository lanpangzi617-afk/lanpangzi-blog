---
title: mongodb_valid
date: 2025-12-17 17:38:02
tags:
---

# 一、概述

MongoDB 本身不定义结构，项目中必须使用 pydantic 来定义 Mongo 数据。

即：Mongo 负责存数据 —>pydantic 负责定义数据结构

# 二、定义 ObjectId 类型：

mongoDB 原始数据：

![](C:\Users\Lenovo\AppData\Roaming\marktext\images\2025-12-17-16-02-19-e78f669731658ede6b843a250450a2e.png)

\_id 类型特殊（ObjectId），pydantic 不认识 ObjectId，故 FastAPI 无法校验路径参数

因此我们需要定义 ObjectId 类型\_：

![](C:\Users\Lenovo\AppData\Roaming\marktext\images\2025-12-17-16-09-39-image.png)

# 三、定义 MongoDB 数据

![](C:\Users\Lenovo\AppData\Roaming\marktext\images\2025-12-17-16-13-38-image.png)

# 方式 1：使用 Hexo 标签（推荐）

`{% asset_img 微信图片_20251218100151.jpg 这是图片描述 %}`

# 方式 2：使用相对路径

`![图片描述](lanpangzi_blog/source/_post/images/mongoDB原始数据.jpg)`

# 方式 3：带链接的图片

`{% asset_link example.jpg 点击下载图片 %}`

{% asset_img wallhaven.png 这是图片描述 %}
