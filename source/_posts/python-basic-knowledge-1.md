---
title: python_basic_knowledge
date: 2025-12-21 00:43:49
categories:
  - python
tags:
  - basic
---

# 三元表达式

例如：

```python
id = x if x < y else y
```

意思是如果 x < y 则把 x 赋值给 id ，否则就把 y 赋值给 id。

# 断言

assert 这个关键字被称为断言，当 assert 后面的条件为假时，a 程序会自动崩溃并抛出 AssertionError 的异常。

例如：

```python
assert 3 > 4
```

此时程序就会抛出 AssertionError 异常

# range()

```python
range([statrt], stop[, step])
```

用中括号括起来的两个参数是可选的，step = 1 表示第三个参数的值默认为 1，range 作用是生成一个从 start 参数的值开始到 stop-1 参数的值结束的数字序列。

# 数组

1. 列表 list
   - 添加数据
     1. append(),只能添加一个参数
     2. extend([]),添加多个参数
     3. insert(num,data),在指定位置插入数据
   - 删除元素
     1. remove()
     2. del 语句,例如：del list[1]
     3. pop(),默认去除列表中最后一个元素，并返回该元素；同时也可以删除某元素对应的索引，例如：list.pop(1)
   - 切片（slice）
     1. list[start:stop],默认从第一位元素和最后一位元素获取
2. 元组 tuple
   - 不可改变，给元组赋值后面必须带一个逗号，才能被程序识别为元组；当需要给元组加一个元素，可利用切片进行拼接完成。

# 字符串

格式化 format()：

```python
"{0:.1f}{1}".format(25.687,"GB")
```

返回 25.7GB

# 序列

1. list() 将可迭代对象转换为列表

2. tuple() 将一个可迭代对象转换为元组

3. max() 返回序列或参数集合的最大值

4. sum(iterable[,start = 0]) 返回序列 iterable 和可选参数 start 的总和

5. sorted() 默认从小到大排序

6. enumerate() 将对象转换为元组

7. zip() 将两个对象转换为元组

   例如：a = [1,2,3,4,5,6]

   b = [3,4,5]

   zip(a,b)

   输出为：[(1,3),(2,4),(3,5)]

# 收集参数（可变参数）

在参数前加一个 ”\*“ 的符号

例如：def test(\*params exp):

print(len(params),exp)

test(1,23,"abc",exp = 8)
```

3,8

建议：若在可变参数后有一个其他参数，需给此参数赋一个默认值

# global 关键字

在函数内使用 global 关键字，使之成为全局变量。

# 内嵌函数

内嵌函数只能在函数内被调用

# 匿名函数

lambda：创建匿名函数

lambda 参数列表：表达式

filter：过滤器，过滤 true 的内容

map：映射，将序列的每一个元素作为函数的参数进行运算加工，直到所有可迭代的序列完成加工并返回加工后的元素构成的新序列

例如：list(map(lambda x:x\*2,range(10)))

[0,2,4,6,8,10,12,14,16,18]

# 递归

函数必须返回

# 字典-工厂函数（类型）

{}：键值对，可用 dict 表示

可直接对”键“赋值完成字典参数的添加

keys()：访问字典的键

values()：访问字典的值

items()：访问字典的项

get()方法：访问字典的项

clear()：清空字典

copy()：浅拷贝，对应的地址不一样

pop()：给出键对应的值，原字典的的键值对被去除

popitem()：按优先级给出键值对

update()：通过字典去更新另一个字典

# 集合

{}：如何创建一个集合：

1.直接将一堆元素用花括号括起来

2.使用 set()工厂函数

例如： 

```python
set = set([1,2,3,4,4])
print(set)
```

[1,2,3,4]#自动去重

add()：添加元素

frozenset()：表示不可变集合，即不可添加

# 打开文件

{% asset_img open_file.png 这是图片描述 %}

![](E:\lanpangzi-blog\source_posts\python-basic-knowledge-1\open_file.png)

# OS 模块

一些常用方法：

mkdir：在当前目录下创建单个文件

例如：os.mkdir("E:\\\A")

remove(path)：删除文件

rmdir(path)：删除空的文件夹

rename(old,new)：将 old 重命名为 new

# pickle 模块

使用 dump() 方法将列表、字典保存到文件中

load() 读取文件

# 处理异常的方法

{% asset_img try_except.png  %}

![](E:\lanpangzi-blog\source_posts\python-basic-knowledge-1\try_except.png)

raise \*\* 抛出异常

{% asset_img raise.png 这是图片描述 %}

![](E:\lanpangzi-blog\source_posts\python-basic-knowledge-1\raise.png)

# EasyGui

EasyGui 是 python 的一个轻量级 GUI 库，所有交互通过弹窗实现，不需要写回调函数、布局管理等复杂代码，非常适合快速制作小型交互工具或脚本的人机交互界面。

常见的几种功能：

消息框：msgbox

{% asset_img msgbox.png %}

![](C:\Users\Lenovo\AppData\Roaming\marktext\images\2026-01-08-18-11-49-image.png)

输入框：enterbox

{% asset_img enterbox.png %}

![](C:\Users\Lenovo\AppData\Roaming\marktext\images\2026-01-08-18-12-35-image.png)

选择框：choicebox

{% asset_img choicebox.png %}

![](C:\Users\Lenovo\AppData\Roaming\marktext\images\2026-01-08-18-13-24-image.png)

按钮框：buttonbox

{% asset_img buttonbox.png %}

![](C:\Users\Lenovo\AppData\Roaming\marktext\images\2026-01-08-18-13-48-image.png)

文件选择框：fileopenbox

{% asset_img fileropenbox.png %}

![](C:\Users\Lenovo\AppData\Roaming\marktext\images\2026-01-08-18-14-12-image.png)

# 类和对象

**类（Class）**：是创建对象的“模板”，定义了对象的属性和方法

**对象（Object）**：是类的实例

对象 = 属性 + 方法

**封装**：将对象的属性和方法“包裹”起来，之对外暴露必要的接口（方法），避免外部直接修改属性导致错误。

{% asset_img capsulation.png %}

![](C:\Users\Lenovo\AppData\Roaming\marktext\images\2026-01-08-18-30-45-image.png)

**继承**：让一个类（子类/派生类）继承另一个类（父类/基类）的属性和方法，子类可以复用父类的代码，也可以扩展自己的功能。

{% asset_img inherit.png %}

![](C:\Users\Lenovo\AppData\Roaming\marktext\images\2026-01-08-18-34-45-image.png)

若子类需在父类属性 / 方法的基础上添加属性 / 方法，需先调用父类的属性 / 方法。例如：super().\*\*()

{% asset_img super.png %}

![](C:\Users\Lenovo\AppData\Roaming\marktext\images\2026-01-08-19-11-01-image.png)

**多态**：同一种方法名，在不同的子类中有不同的实现，调用时根据对象的类型自动执行对应的方法，实现“一个接口，多种形态”。

{% asset_img polymorphic.png %}

![](C:\Users\Lenovo\AppData\Roaming\marktext\images\2026-01-08-18-39-04-image.png)

**self**：类中实例方法的第一个参数，指向当前类创建的具体对象（实例）本身。

\***\*init\_**(self)\*\*：python 类的初始化方法，用来初始化对象的属性，不返回实例。

\***\*new**(self,)\*\*:返回实例对象

**公有（Public）**：默认的属性 / 方法，类的内部、外部、子类都能直接访问。

**私有（Private）**：属性 / 方法以\_\_开头，仅能在类的内部直接访问。

# 类，类对象和实例对象

{% asset_img class.png %}

![](C:\Users\Lenovo\AppData\Roaming\marktext\images\2026-01-08-19-21-08-image.png)

若属性与方法名相同，属性会覆盖掉方法

{% asset_img same.png %}

![](C:\Users\Lenovo\AppData\Roaming\marktext\images\2026-01-08-19-24-19-image.png)

# 工厂函数（内置函数）

{% asset_img factory.png %}

![](C:\Users\Lenovo\AppData\Roaming\marktext\images\2026-01-09-16-09-20-image.png)

`**__str__()`**：给**用户\*\*看的，追求可读性、简洁易懂；

`__repr__()`：给**开发者**看的，追求精确性、能还原对象（“所见即所得”）。

{% asset_img str_repr %}

![](C:\Users\Lenovo\AppData\Roaming\marktext\images\2026-01-09-17-02-56-image.png)

**eq\_**():

{% asset_img eq.png %}

![](C:\Users\Lenovo\AppData\Roaming\marktext\images\2026-01-09-18-48-19-image.png)\_\_

# 属性访问

{% asset_img attribute.png %}

![](C:\Users\Lenovo\AppData\Roaming\marktext\images\2026-01-09-18-00-54-image.png)

# 内置函数

if **name** =="**main**“：表示直接运行该文件，生产环境通常不用，但本地调试非常常见

包（package)：一个文件夹内用于存放相关的模块，在该文件夹中必须创建一个"**init**.py"的模块文件，内容可谓空
