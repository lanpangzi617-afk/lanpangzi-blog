---
title: python_basic_knowledge
date: 2025-12-20 19:51:21
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
   
   - 添加数据
     
     1. append(),只能添加一个参数
     
     2. extend([]),添加多个参数
     
     3. insert(num,data),在指定位置插入数据
   
   . 删除元素
   
   1. remove()
   
   2. del 语句,例如：del list[1]
   
   3. pop(),默认去除列表中最后一个元素，并返回该元素；同时也可以删除某元素对应的索引，例如：list.pop(1)
   
   . 切片（slice）
   
   1. list[start:stop],默认从第一位元素和最后一位元素获取

2. 元组 tuple
   
   - 不可改变，给元组赋值后面必须带一个逗号，才能被程序识别为元组；当需要给元组加一个元素，可利用切片进行拼接完成。
