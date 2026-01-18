---
title: python-HTML5
date: 2026-01-14 16:57:38
tags:
- Front-End
categories:
- python
---

# 1. 什么是 HTML？

超文本标记语言，是一种用来告知浏览器如何组织页面的标记语言。

### 1.1 知识点：

1. 标记也成为标签（元素）

2. 大小写都可，建议小写

3. HTML 由一系列的标签组成

简单地说，学习 HTML 就是学习标签

### 1.2 标签语法：

```html
<h1>标题内容</h1>
```

### 1.3 标签组成：

1. 符号：标签用<>尖括号表示

2. 组成：开始标签、结束标签和内容

3. 别称：标签也称为元素

标签分类：大部分都是双标签，少数单标签

例如：

```html
<hr>
```

水平线,放在文本后则为换行 

# 2. HTML 文档

### 2.1 文档类型

```html
<!DOCTYPE html>
```

HTML5 的文档类型声明，他告诉浏览器当前页是使用 HTML5 规范编写的

### 2.2 html 元素

<html> 元素。这个元素包裹了页面中的所有内容，有时被称为根元素，在 HTML 中：

- lang：声明网页的主要语言，帮助浏览器、搜索引擎等正确处理页面内容

- en：代表英语，即页面的主要语言为英语

- zh-CN：代表中文

- ```html
  <head>
  ```

头部元素。包含文档的元（meta）数据，主要保存供机器处理的信息，而非人类可读信息。

- ```html
  <meta charset="UTF-8">h=device-width,initial-scale=1.0">
  ```

表示该文档的字符集设置为 UTF-8

- ```html
  <meta name="viewport" content="widt 
  ```

开发者能确保网页在移动设备上以最佳状态呈现，提升用户浏览体验

- ```html
  <title>Document</title>
  ```

设置页面标题，即出现在该页面加载的浏览器标签中的内容

- ```html
  <body>
  
  </body>
  ```

包含所有显示在页面上的内容，包含文本、图片、视频等

# 3. HTML 的标签和段落

### 3.1 标签的关系

- 嵌套关系

```html
<head></head>
<body></body>
```

- 父子关系

```html
<head>
    <title></title>
</head>
```

### 3.2 标题的标签

语法：

```html
<h1>这是h1标题</h1>
<h2>这是h2标题</h2>
<h3>这是h3标题</h3>
<h4>这是h4标题</h4>
<h5>这是h5标题</h5>
<h6>这是h6标题</h6 >
```

在现有的六个标题层次中，除非觉得有必要否则应该争取每页使用不超过三个

### 3.3 段落标签

HTML 元素表示文本的一个段落

语法：

```html
<p>里面是段落文本</p>
```

每行只显示一个，文字显示不会自动换行，段落的相关样式用 CSS 设置。

### 3.4 强调与重要性标签

```html
<strong>加粗</strong>
<em>倾斜</em>
<ins>下划线</ins>
<del>删除线</del>
```

### 3.5 注释标签

```html
<!--这里是注释内容-->
```

快捷键：ctrl + /

特点：1. 注释内容不会显示在网页上

2. 可以跨越多行

3. 常用于代码说明、临时禁用代码或给其他开发者留言

# 4. 块级元素和内联元素

**块级元素**：1. 块级元素独占一行

2. 它可以嵌套其他元素

3. 常见的比如p、h、div等

**内联元素**：1. 可以一行放多个，太长与文本一起使用

2. 不能嵌套块级元素，可以嵌套其他内联元素

3. 常见的比如 strong、em、a等

**注意事项**：

1. 段落 p 标签里面不要放其他块级元素

2. 段落里面放文字相关，比如内联元素

3. 但是元素分类不是一直不可更改的，CSS 可以通过 display 改变他们的显示模式

# 5. HTML 中的图片

### 5.1 图片的属性

1. 属性采取键值对形式

2. 属性之间没有必要的先后顺序

3. 但是属性之间必须有空格分隔

语法：

```html
<img src="" alt="">
<img src="pig.jpg" alt="这是佩奇">
```

src 属性：只想插入到页面的图像地址

alt 属性：备选文本，用于在图片无法显示或者因为网速慢情况下显示的文字

**注意**：图片与 HTML 文件放在一起。若图片较多，可将图片存放到文件夹下。

HTML 这么找到图片？

1. 同一目录：直接使用文件名即可（./ 表示当前文件夹）

2. 下级子目录：使用目录名/文件名

3. 上级目录：使用 ../ 返回上一级

### 5.2 其他属性

一般情况下，宽度和高度只修改一个，剩下的等比例缩放

width：设置图片的宽度（建议 CSS 修改）

height：设置图片的高度

title：图像标题。鼠标悬停现实的文本

### 5.3 常见的图片格式

1. jpeg / jpg：有损压缩技术，放大缩小会变得牧户或有锯齿  **适用场景**：摄影照片、网页图片（非透明背景）。

2. png：无损压缩，支持透明度  **适用场景**：LOGO、网页图形、需要透明度的图像

3. gif：支持动画，最多256色（索引色）。支持简单动画和透明背景  **适用场景**：简单动画、表情包、低色彩图形。

4. webp：Google开发的现代格式。支持有损 / 无损压缩、透明度和动画。  **适用场景**：网页优化（替代 jpeg / png / gif）。

5. avif：基于 AV1 视频编码，支持高压缩率和 HDR。压缩效率由于 webp。  **适用场景**：未来网页优化、需高性能压缩的场景（B站、京东等）

网页优化：优先 Webp / AVIF，备选 JPEG / PNG。

透明图像：PNG（静态）或 Webp（动态）。

动画：Webp / GIF（简单动画）。

其他格式：如 SVG、HEIC等

# 6. 视频和音频

### 6.1 视频标签

```html
<video src=""></video>
<video src="video.mp4" controls width="300"></video>
```

src 属性：只想要插入到页面的视频地址

controls：显示浏览器自带播放控件

width / height 属性：设置视频的宽度和高度

#### 6.1.1视频标签其他属性：

autoplay：自动播放（需设置静音）

loop：循环播放

muted：静音

poster：预览图像，即视频封面

#### 6.1.2 视频标签兼容性写法：

```html
<video controls>
    <source src="video.mp4" type="video/mp4">
    <source src="video.ogg" type="video/ogg">
    <source src="video.webm" type="video/webm">
    <p>您的浏览器不支持 HTML 5 Video 标签，请升级浏览器</p>
</video>
```

1. 将 src 属性放在几个单独的 source 元素当中，这些元素分别指向各自的资源 。

2. 浏览器会检查 source 元素，并且播放第一个与其自身相匹配的媒体。

3. 每个 source 元素都含有 type 属性，浏览器也会通过检查这个属性来迅速的跳过那些不支持的格式，若没有添加 type 属性，浏览器会尝试加载每一个文件，知道找到一个能正确播放的格式，但这样会消耗大量的时间和资源。

### 6.2 音频标签

```html
<audio src="audio.mp3" autoplay></audio>
<audio autoplay>
    <source src="audio.mp3" type="audio/mp3">
    <p>您的浏览器不支持 HTML 5 Video 标签，请升级浏览器</p>
</audio>
```

**注意**：音频标签浏览器不让自动播放

# 7. 超链接

### 7.1 语法：

```html
<a href=""></a>
<a href="https://www.deepseek.com/">DeepSeek官网</a>
```

href 属性：也成为超文本引用或目标，他将包含一个网址来创建一个基本链接。（连接可以除了自身之外的其他元素，比如文字、标题、图片、视频等。

内部链接：去往网站内部的链接

### 7.2 其他属性

title属性：鼠标悬停提示的文字

target属性：打开页面的方式：_self 当前窗口打开（默认）；_blank 新窗口打开

### 7.3 创建超链接

1. 空链接：在 HTML中，空链接通常指的是没有实际指向目标的超链接，符号是 #

2. 下载链接：如果是 exe 或者压缩包点击是下载

3. 邮件链接：需用关键词mailto:

例如：

```html
<a href="mailto:123456@163.com">给我发邮件</a>
```

### 7.4 锚点链接

#### 7.4.1 跳转链接

1. 定义锚点目标：使用 id 属性创建锚点目标，比如：

```html
<h2 id="1">第一部分</h2>
```

2. 创建跳转链接：使用 # 标记锚点目标，比如：

```html
<a href="#1">跳转到第一部分</a>
```

#### 7.4.2 页面滑动效果

在 <head> 标签中添加以下代码（CSS）

```css
<head>
    <style>
        html{
        scroll-behavior:smooth;
    }
    </style>
</head>
```

# 8. 布局标签

1. 网站结构标签：网页的外观大概包括：页眉、导航栏、著内容、侧边栏、页脚等

2. 无语义标签：没有合适语义标签时，在进行一些布局时候可以选择：div 和 span 标签

3. 列表标签：HTML 列表是网页内容组织的重要元素，可以让显示的内容国家整齐有序

### 8.1 网站结构标签

| 标签（双标签） | 作用             |
|:------- | -------------- |
| head    | 网页页眉（头部）       |
| main    | 网页内容，每个页面只能有一个 |
| nav     | 导航栏            |
| article | 文章相关           |
| section | 分块             |
| aside   | 侧边栏            |
| footer  | 页面页脚（底部）       |

**注意**：以上标签受浏览器兼容性影响，PC 端根据公司需求，移动端放心使用

### 8.2 无语义标签

1. **div 标签**

特点：

- 块级元素：默认独占一行，前后会自动换行

- 通常用于布局结构，作为其他元素的容器

- 可以包含其他块级或行内元素

- 默认没有语义
2. **span 标签**

特点：

- 行内元素：不会换行，仅包裹内容的一部分

- 用于对文本或行内元素的局部样式或操作

- 默认没有语义
3. **块级元素与行内元素的区别**：

| 特性       | 块级元素                      | 行内元素                        |
| -------- | ------------------------- | --------------------------- |
| **默认显示** | 独占一行，自动换行                 | 与其他元素在同一行，不换行               |
| **嵌套规则** | 可嵌套块级元素和行内元素              | 只能嵌套行内元素，不能嵌套块级元素           |
| **常见标签** | div p h1-h6 ul li section | span a strong em img（特殊行内块） |

### 8.3 列表标签

1. 无序列表 ul：顺序无关紧要的列表

2. 有序列表 ol：顺序有关紧要的列表

3. 描述列表 dl：标记一组项目及相关描述

#### 8.3.1 无序列表

无序列表在我们布局中非常常用，常用于一些整齐对齐的木块中使用。

例如：

{% asset_img bullet_list.png %}

![](C:\Users\Lenovo\AppData\Roaming\marktext\images\2026-01-17-15-44-01-image.png)

```html
<ul>
    <li>小米</li>
    <li>小米14</li>
</ul>
```

{% asset_img result1.png %}

![](C:\Users\Lenovo\AppData\Roaming\marktext\images\2026-01-17-16-00-18-image.png)

ul：

- 定义列表的容器

- 只能包含 li>元素

li：

- 定义列表的选项

- 里面可以放其他 html 元素

#### 8.3.2 有序列表

有序列表在布局中使用较少，实际开发即使有顺序，一般用其他替代。

```html
<ol>
    <li>小米</li>
    <li>小米14</li>
  </ol>
```

{% asset_img result2.png %}

![](C:\Users\Lenovo\AppData\Roaming\marktext\images\2026-01-17-16-05-42-image.png)

#### 8.3.3 描述列表

描述列表在布局中主要是在页面底部，例如：

{% asset_img result3.png %}

![](C:\Users\Lenovo\AppData\Roaming\marktext\images\2026-01-17-16-10-00-image.png)

```html
<dl>
    <dt>关于小米</dt>
    <dd>了解小米</dd>
    <dd>加入小米</dd>
    <dd>投资者关系</dd>
    <dd>ESG与可持续发展</dd>
    <dd>廉洁举报</dd>
</dl>
```

{% asset_img result4.png %}

![](C:\Users\Lenovo\AppData\Roaming\marktext\images\2026-01-17-16-29-28-image.png)

dl：

- 定义列表的容器

- 只能包含 dt 和  dd 元素

dt：

- 定义被描述的术语

- 通常显示为左对齐或加粗

- 一个 dt 可以对应多个 dd

dd：

- 包含术语的定义或描述

- 通常显示为缩进形式

- 可以包含段落、图片、链接等其他 HTML 元素

# 9. 表格标签

**作用**：以结构化方式展示行列数据，使信息清晰、易读且便于对比。

网页场景：主要用于数据展示或者后台管理系统的信息展示

| 标签    | 作用     |
| ----- | ------ |
| table | 表格容器标签 |
| tr    | 行标签    |
| td    | 单元格标签  |
| th    | 表头单元格  |

{% asset_img result5.png %}

![](C:\Users\Lenovo\AppData\Roaming\marktext\images\2026-01-17-16-35-38-image.png)

**注意**：美化表格是 CSS 的工作

```html
<table>
    <tr>
      <th>姓名</th>
      <th>年龄</th>
      <th>成绩</th>
    </tr>
    <tr>
      <td>张三</td>
      <td>18</td>
      <td>98</td>
    </tr>
    <tr>
      <td>李四</td>
      <td>19</td>
      <td>99</td>
    </tr>
  </table>
```

{% asset_img result6.png %}

![](C:\Users\Lenovo\AppData\Roaming\marktext\images\2026-01-17-16-45-52-image.png)

### 9.1 表格结构标签

增强表格语义，让表格结构噶恩加清晰

| 标签    | 作用        |
| ----- | --------- |
| thead | 定义表格的头部区域 |
| tbody | 定义表格的主要内容 |
| tfoot | 定义表格的底部区域 |

```html
 <table>
    <thead>
      <tr>
        <th>姓名</th>
        <th>年龄</th>
        <th>成绩</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>张三</td>
        <td>18</td>
        <td>98</td>
      </tr>
      <tr>
        <td>李四</td>
        <td>19</td>
        <td>99</td>
      </tr>
    </tbody>
  </table>
```

![](C:\Users\Lenovo\AppData\Roaming\marktext\images\2026-01-17-16-55-52-image.png)

### 9.2 合并单元格

表格开发中很少使用合并，因为会导致表格难以维护，且可能影响响应式适配（尤其在移动端）。如果有特殊情况，可以借助 AI。

原理：

1. 确定是跨行（rowspan）还是跨列合并（colspan）

2. 找到目标单元格（左上原则），写合并数量

3. 删除多余单元格

# 10. 表单

收集用户输入数据，并将数据提交到后端进行处理。

例如：

{% asset_img result7.png %}

![](C:\Users\Lenovo\AppData\Roaming\marktext\images\2026-01-17-17-05-34-image.png)

**场景**：

- 用户登录 / 注册

- 搜索框

- 联系表单

- 问卷调查

- 订单支付

- 文件上传...

**表单的核心标签组成**：

1. 表单容器：form：定义表单的容器，包裹所有表单控件。默认包含 action 属性

2. 表单控件：包含 input 通用输入控件、textarea 多行文本输入框、select 下拉选择框、button自定义按钮等

3. 辅助标签：label 关联输入控件的文本标签，提升可访问性（点击标签可聚焦输入框），更好的提高表单的用户体验

### 10.1 表单容器

form 标签

作用：定义表单的容器，包裹所有表单控件

```html
<form action=""></form>
```

action 属性定义了提交表单时，应该把所有收集的数据发送给谁（URL）取处理

### 10.2 表单控件

#### 10.2.1 input 表单

通用输入控件，包含输入框、单选框、复选框等

1. 单选框

```html
<input type="text">
```

| type属性   | 说明    |
| -------- | ----- |
| text     | 单行文本框 |
| password | 密码框   |
| radio    | 单选框   |
| checkbox | 复选框   |
| file     | 文件域   |

| 其他属性         | 说明                                                     |
| ------------ | ------------------------------------------------------ |
| placeholder  | 提示信息                                                   |
| name         | 元素的名称                                                  |
| maxlength    | 允许的最大字符数                                               |
| accesskey    | 使用元素获得焦点的快捷键                                           |
| autocomplete | 用于控制表单的自动填充行为，帮助浏览器决定是否根据用户历史输入自动填充字段值<br/>取值 on / off |

2. 单选框和复选框

| type属性值  | 说明  |
| -------- | --- |
| radio    | 单选框 |
| checkbox | 复选框 |

| 其他属性    | 说明       |
| ------- | -------- |
| name    | 表单名称实现分组 |
| value   | 表单值      |
| checked | 是否默认选中   |

3. 文件域 file

| 其他属性    | 说明                    |
| ------- | --------------------- |
| mutiple | 允许选择多个文件              |
| accept  | 规定选择的文件类型，多个类型之间用逗号分割 |

#### 10.2.2 textarea 表单：多行文本输入框

textarea：是一个多行纯文本编辑控件，适用于允许用户输入大量自由格式文本的场景，例如评论或反馈表单

```html
      <li>
        留言：<textarea name="msg" placeholder="请输入留言" rows="5" cols="15"></textarea>
      </li>
```

{% asset_img reslut8.png %}

![](C:\Users\Lenovo\AppData\Roaming\marktext\images\2026-01-18-23-31-06-image.png)

| 常见属性        | 说明             |
| ----------- | -------------- |
| name        | 表单名称           |
| placeholder | 提示信息           |
| rows        | 文本行数，正整数，默认为 2 |
| cols        | 文本列数，正整数，默认 20 |

文本与 textarea 利用 CSS设定样式，比如宽高边框等

#### 10.2.3 select 下拉表单：下拉选择框

select：表示一个提供选项菜单的控件

select 元素是容器，option 是每一个选项标签，每个选项要跟一个值，要想默认选中一个选项，可以添加 selected 属性

因为 select 很难修改为好看的效果，大部分下拉列表可以跳过其他标签模拟实现

```html
      <li>
        地区：<select name="city">
          <option value="广东">广东</option>
          <option value="上海" selected>上海</option>
          <option value="北京">北京</option>
        </select>
      </li>
```

{% asset_img reslut9.png %}

![](C:\Users\Lenovo\AppData\Roaming\marktext\images\2026-01-18-23-33-22-image.png)

#### 10.2.4 button 按钮：自定义按钮

button：定义一个按钮，元素内部可以放置内容，比如文本或图像

语法：

```html
<button>登录</button>
```

disabled属性：可以禁用按钮，无法点击

![](C:\Users\Lenovo\AppData\Roaming\marktext\images\2026-01-18-23-34-30-image.png)
