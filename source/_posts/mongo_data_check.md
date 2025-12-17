# 一、概述

MongoDB 本身不定义结构，项目中必须使用 pydantic 来定义 Mongo 数据。

即：Mongo 负责存数据 —>pydantic 负责定义数据结构

# 二、定义ObjectId类型：

mongoDB原始数据：

'{% asset_img 屏幕截图 2025-12-17 163524.png %}'

![](C:\Users\Lenovo\AppData\Roaming\marktext\images\2025-12-17-16-02-19-e78f669731658ede6b843a250450a2e.png)

_id 类型特殊（ObjectId），pydantic 不认识ObjectId，故FastAPI无法校验路径参数

因此我们需要定义 ObjectId 类型_：

![](C:\Users\Lenovo\AppData\Roaming\marktext\images\2025-12-17-16-09-39-image.png)

# 三、定义 MongoDB 数据

![](C:\Users\Lenovo\AppData\Roaming\marktext\images\2025-12-17-16-13-38-image.png)
