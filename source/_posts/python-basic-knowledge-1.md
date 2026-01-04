---
title: python_basic_knowledge
date: 2025-12-21 00:43:49
tags:
---

# 三元表达式

例如：id = x if x < y else y

意思是如果 x < y 则把 x 赋值给 id ，否则就把 y 赋值给 id。

# 断言

assert 这个关键字被称为断言，当assert 后面的条件为假时，a程序会自动崩溃并抛出AssertionError的异常。

例如：assert 3 > 4

此时程序就会抛出 AssertionError 异常

# range()

range([statrt], stop[, step])

用中括号括起来的两个参数是可选的，step = 1 表示第三个参数的值默认为 1，range 作用是生成一个从start 参数的值开始到 stop-1 参数的值结束的数字序列。

# 数组

1. 列表 list
   * 添加数据
     1. append(),只能添加一个参数
     2. extend([]),添加多个参数
     3. insert(num,data),在指定位置插入数据
   * 删除元素
     1. remove()
     2. del 语句,例如：del list[1]
     3. pop(),默认去除列表中最后一个元素，并返回该元素；同时也可以删除某元素对应的索引，例如：list.pop(1)
   * 切片（slice）
     1. list[start:stop],默认从第一位元素和最后一位元素获取
2. 元组 tuple
   * 不可改变，给元组赋值后面必须带一个逗号，才能被程序识别为元组；当需要给元组加一个元素，可利用切片进行拼接完成。

# 字符串

格式化 format()：

"{0:.1f}{1}".format(25.687,"GB")

返回25.7GB

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

在参数前加一个 ”*“ 的符号

例如：def test(*params exp):

                print(len(params),exp)

test(1,23,"abc",exp = 8)

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

例如：list(map(lambda x:x*2,range(10)))

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

2.使用set()工厂函数

例如： set = set([1,2,3,4,4])

print(set)

[1,2,3,4]#自动去重

add()：添加元素

frozenset()：表示不可变集合，即不可添加 

# 打开文件

{% asset_img open_file.png 这是图片描述 %}

# OS模块

一些常用方法：

mkdir：在当前目录下创建单个文件

例如：os.mkdir("E:\\\A")

remove(path)：删除文件

rmdir(path)：删除空的文件夹

rename(old,new)：将 old 重命名为 new

# pickle模块

使用 dump() 方法将列表、字典保存到文件中

load() 读取文件

# 处理异常的方法

{% asset_img try_except.png 这是图片描述 %}

raise ** 抛出异常

{% asset_img raise.png 这是图片描述 %}
