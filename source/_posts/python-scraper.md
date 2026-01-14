---
title: python-scraper
date: 2026-01-12 12:00:15
tags:
- scraper
categories: 
- python
---

# 1. python如何访问互联网？

python通过 urllib(url + lib) 去访问互联网

url 格式和组成部分

{% asset_img url.png %}

![](C:\Users\Lenovo\AppData\Roaming\marktext\images\2026-01-12-12-09-38-image.png)

urllib 是一个包

### 1.1 requests：HTTP请求库，发送请求获取响应数据

**使用步骤**：1. 导入模块

2. 发送 get 请求，获取响应

3. 从响应中获取数据

{% asset_img request.png %}

![](C:\Users\Lenovo\AppData\Roaming\marktext\images\2026-01-12-13-39-37-image.png)

```python
response.text：#响应体 str 类型
response.encoding：#二进制转换字符使用的编码
response.content：#响应体 bytes 类型
response.content.decode：#硬编码为 utf-8 的字符串
```

```python
urllib.request：#阅读并打开目标url
urllib.request.Request()：#返回访问目标 url 的对象
response = urllib.request.urlopen(url,data)：#访问目标 url 地址中指定的 data 的内容，发送 post 请求（get：从服务器请求获得数据 post：向制动服务器提交被处理的数据）
response.geturl()：#返回对象的 url 地址
response.info()：#得到 http message 的对象
response.getcode()：#得到访问该目标 url 地址的状态码
reponse.read()：#返回 html 格式的内容
decode("utf-8")：#硬编码为 utf-8 的格式
urllib.parse：#解析目标 url
urllib.robotparser：#解析 robot.txt 文件
```

### 1.2 修改herder

- 通过 Request 的 headers参数修改

- 通过 Request.add_header() 方法修改

### 1.3 代理

步骤：1. 参数是一个字典{'类型'：'代理ip：端口号'}

```python
proxy_support = urllib.request.ProxyHandler({})
```

2. 定制、创建一个 opener

```python
opener = urllib.request.build_opener(proxy_support)
```

3. 安装 opener

```python
urllib.request.install_opener(opener)
```

### 1.4 requests 进阶

结合 Cookies 和 Session 的实战用法，处理登录、保持会话的核心技巧：

1. Session：requests.Session()，相当于一个”持久化的浏览器窗口“，会自动保存请求过程中产生的 Cookies，后续请求无需手动传递。

2. Cookies：服务器给客户端的”身份凭证“，Session 会自动维护这个凭证，避免重复手动设置。

简短示例代码如下：

```python
import requests
session = requests.Session()
session.headers = {"User-Agent":""}
login_data = {
    "account":"aaa",
    "passward":"123456"
}
session.post(url,data = login_data)
```

也可手动将浏览器的 Cookies 复制到 Session中，但 Cookies 易失效，需频繁更新

# 2. Beautiful Soup

Beautiful Soup是一个可以从 HTML 或 XML文件中提取数据的 Python 库

要安装两个库：bs4 和 lxml

```python
#1. 导入模块
from bs4 import BeautifulSoup
#2. 创建BeautifulSoup 对象
soup = BeautifulSoup("<html>data</html>",'lxml')#’lxml‘：解决警告问题，创建BeautifulSoup对象时，指定解析器
```

### 2.1 BeautifulSoup对象的 find 方法

**find 方法的作用**：搜索文档树

```python
find(self,name = None,attrs = {},recursive = True,text = None,**kwargs)
```

**参数**：

- name：标签名

- attrs：属性字典

- recursive：是否递归循环查找

- text：根据文本内容查找

**返回**：

    查找到的第一个元素对象

```python
title = soup.find('title')#查找 title 标签的内容
a  = soup.findall('a')#查找 a 标签下的所有内容
link1 = soup.find(id = 'link1')#通过命名参数查找 id 为 link1 的标签
link2 = soup.find(attrs = {'id':'link1'})#使用attrs 来指定属性字典，进行查找（通用）
text = soup.find(text = 'Elaie')#根据文本内容进行查找，代码返回 Elsie（不常用）
```

**Tag 对象常见属性**

- name：获取标签名称

- attrs：获取标签所有属性的键和值

- text：获取标签的文本字符串

```python
print(a.text#打印 a 标签下的文本内容
print(a.attrs)#打印 a 标签下的所有属性
```

# 3. 正则表达式

正则表达式是一种字符串匹配的模式，从某个字符串中提取符合某种条件的子串。

{% asset_img re.png %}

. 匹配除换行符以外的其他字符

![](C:\Users\Lenovo\AppData\Roaming\marktext\images\2026-01-13-14-25-35-image.png)

### 3.1 r 原串

正则中使用 r 原始字符串，可以忽略转移符号带来的影响，即待匹配的字符串中有多少个”\“，r 原串正则中就添加多少个”\“

### 3.2 re.search()方法

```python
re.search(pattern,string，flags=0)
```

**作用**：扫描整个字符串，返回一个匹配的对象

**参数**：

- pattern：正则表达式

- string：从那个字符串中查找

- flags：匹配模式

**返回**：返回 string 中与 pattern 匹配的 Match对象

### 3.3 re.findall()方法

```python
re.findall(pattern,string,flags=0)
```

**作用**：扫描整个 string 字符串，返回所有与 pattern 匹配的列表

**参数**：

- pattern：正则表达式

- string：从那个字符串中查找

- flags：匹配模式

**返回**：返回 string 中与 pattern 匹配的结果列表

**特点**：

- 若正则表达式中没有()，则返回与整个正则表达式匹配的列表

- 若正则表达式中有(),则返回()中匹配的内容列表，小括号两边的东西是负责确定提取数据所在位置。

### 3.4 常用的 flags 取值

1. re.IGNORECASE（re.I）：忽略大小写匹配（比如 `a` 能匹配 `A`，`Z` 能匹配 `z`）

2. re.MULTILINE（re.M）：多行模式（让 `^` 匹配每行开头，`$` 匹配每行结尾，而非整个字符串的开头 / 结尾）

3. re.DOTALL（re.S）：让 `.` 匹配包括换行符 `\n` 在内的所有字符（默认 `.` 不匹配 `\n`）

4. re.VERBOSE（re.X）：忽略正则中的空格和注释（方便写复杂正则时排版）

# 4. json 模块

1. json.loads()：json 字符串转换为 python 类型数据

2. json.load(file)：json 格式的文件对象转换为 python 类型数据

3. json.dumps(obj)：python 类型数据转换为 json 字符串

4. json.dump(obj,file)：python 类型数据转换为 json 格式的文件对象

obj：python 类型对象

ensure_ascii=False：不显示 ASCII 码

# 5. XPath 解析

XPath（XML Path Language）是一种用在 XML/HTML 文档中定位节点（标签/属性/文本）的语言。

### 5.1 XPath 核心语法

{% asset_img XPath.png %}

![](C:\Users\Lenovo\AppData\Roaming\marktext\images\2026-01-13-16-32-32-image.png)

若在某个元素的循环下，./ 表示当前这个元素

### 5.2 步骤

```python
from lxml import etree
import request
response = request.get(url)
html_str = response.text
tree =etree.HTML(html_str)#解析 HTML
result = tree.xpath()#使用XPth提取数据
```

# 6. 多线程

首先区分线程和进程的关系：进程是资源单位，每一个进程至少要有一个线程

核心方法：

- Thread(target = **，args = **)：创建线程对象，target 指定执行函数，args 传参（元组格式）

- start()：启动线程（真正开启线程执行，而非直接调用 run()）

- join()：阻塞主线程，等待该线程执行完毕（不加则主线程先结束）

- is_alive()：判断线程是否还在运行（返回 True / False）

若需要创建大量线程（比如爬取 100 个网页），用 ThreadPoolExecutor 线程池更高效（自动管理线程数量，避免资源耗尽）

```python
from concurrent.futures import ThreadPoolExecutor
import  time
def crawl(url):
    print(f"开始爬取{url}")
    time.sleep(1)
    return f"{url}爬取完成"
if __name__ == "__main__":
    urls = [f"https://example.com/{i} for i in range (5)]
    with ThreadPoolExecutor(max_workers = 3) as executor:
        results = executor.map(crawl,urls)
        results = executor.submit(crewl,urls) #第二种执行方法
    for res in results:
        print(res)
```

# 7. 异步协程

异步协程（Async Coroutine）是处理高并发 IO 任务（比如爬虫，接口调用）的高效方式。

- async：定义携程函数（异步函数）

- await：暂停协程，等待异步任务完成（仅能在协程函数内使用）

- asyncio：python 内置的异步核心模式，管理协程的运行、调度。

```python
import asyncio
import aiohttp #异步 http 库（替代requests
import time
async def crawl(url):
    async with aiohttp.ClientSession() as session:
        async with session.get(url) as response:
            await asyncio.sleep(1)
            return f"{url}爬取完成"

async def main():
    urls = [f"https://example.com{i} for i in range (5)]
    tasks = [asyncio.create_task(crawl(url) for url in urls]
    results = await asyncio.gather(*tasks)#批量等待多个任务完成，返回结果列表
    for res in results:
        print(res)

if __name__ =="__main__":
    start = time.time()
    asyncio.run(main)
    print(f"异步总耗时：{time.time() - start:.2f}秒) 
```

- 直接调用协程函数不会执行，只会返回一个协程对象，需通过 async.create_task() 封装为任务，或 await 执行。

- await：只能在协程函数内使用，只能跟可等待对象（协程、任务、Future），不能跟普通函数，作用是“暂停当前协程，等待后面的异步任务完成，期间事件循环可以执行其他任务”。

- 异步代码中，不能用同步的 IO 操作（比如：requests.get()、time.sleep()）否则会阻塞整个时间循环；替代方案：aiohttp 替代 requests，asyncio.sleep() 替代 time.sleep()。

- 事件循环重复运行：一个程序中 asyncio.run() 只能调用一次（主入口），多次调用会报错。
