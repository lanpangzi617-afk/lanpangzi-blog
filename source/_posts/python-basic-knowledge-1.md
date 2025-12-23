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
