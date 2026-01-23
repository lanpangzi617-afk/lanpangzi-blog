---
title: python-CSS
date: 2026-01-20 14:19:25
tags:
- Front-End
categories:
- python
---

# 1. CSS 简介

CSS 是用来控制网页在浏览器中的显示外观的语言。

- 样式美化：文本样式、背景、边框等

- 布局与定位：元素排列、响应式设计

- 动画交互：伪类、过度、动画

### 1.1 CSS 分类：

1. 内嵌样式表（行内样式表）：样式写到标签内部，可以控制当前标签的样式，特殊情况使用。

```html
<p style="color:red;font-size:14px;">文字内容</p>
```

2. 内部样式表：写到 head 标签中，脱离结构，可以控制当前页面的所有标签，较为常用。

3. 外部样式表：单独新建一个 CSS 文件，完全脱离结构，可以控制整个网站的所有标签，**最常用**。

```html
<link rel="stylesheet" href="./css/index.css">
```

# 2. CSS 选择器

CSS 选择器：选择 HTML 元素的方式

CSS 属性：采取键值对形式。属性名：属性值;

### 2.1 选择器分类

1. 基础选择器

2. 关系选择器

3. 分组选择器

4. 伪类和伪元素

5. 属性选择器

### 2.2 基础选择器

基础选择器指的是由单个选择器组成，常见的有：

1. 类型选择器

```css
p {
    color: gold;
}
```

类选择器选择某个类型的元素，也称为标签选择器

2. 类选择器

```css
.box {
    color: gold;
}
```

类选择器选择某 1 个元素或者多个元素

在 HTML 中可用 class=""

语法：

{% asset_img result1.png %}

![](C:\Users\Lenovo\AppData\Roaming\marktext\images\2026-01-20-14-59-38-image.png)

```html
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  <style>
    .pink {
      color: pink;
    }

    .sub-nav {
      font-size: 20px;
    }
  </style>
</head>

<body>
  <div class="pink sub-nav">粉色</div>

</body>
```

{% asset_img result2.png %}

![](C:\Users\Lenovo\AppData\Roaming\marktext\images\2026-01-20-15-06-33-image.png)

3. id 选择器

```css
#box {
    color: gold;
}
```

跟 class 类似

| 类选择器                   | id 选择器                       |
| ---------------------- | ---------------------------- |
| 语法：以 . 开头，后跟类名（如 .nav） | 语法：以#开头，后跟 id 名（如 #header）   |
| 作用：选择 class 属性的一个或多个元素 | 作用：选择特定 id 属性的唯一元素           |
| 特点：可用使用多次              | 特点：统一页面中，id 值必须唯一（不能重复）      |
| 类似：身份证的名字，可用使用多次       | 类似：身份证的编号，唯一，只能用一次           |
| 场景：后期修改样式基本都是类选择器      | 场景：后期主要是配合 JavaScript 添加交互效果 |

4. 通配符选择器

```css
* {
    color: gold;
}
```

通配符选择器可用选择 HTML 中所有的标签，进行样式修改。

特殊情况下通过是佩服清除所有元素的默认边距和填充，统一不同浏览器的默认样式。

```css
* {
   /* 清除所有元素的外边框 */
    margin: 0;
    /* 清除所有元素的内边框 */
    padding: 0;
    /* 让块级的盒子水平居中展示 */
    margin:0 auto;
    bod-sizing: border-box;
}
```

### 2.3 关系选择器

关系选择器是通过位置关系来选择目标元素（标签），可以更精准选择某些元素。常见的有：

1. **后代选择器(最重要）**

```css
.box p {
    color:pink;
}
```

说明：选择 div 标签里面的 p 元素，中间空格隔开；父级 div 作用是限定，子元素 p 修改样式。

选择某个元素的后代元素（不限层级，包括子元素、孙元素等）

2. 子代选择器

```css
.box>p {
    color:pink;
}
```

子代选择器只选择”亲儿子“

3. 邻接兄弟选择器

```css
h2+p {
    color:red;
}
```

选中紧跟在 h2 后面的第一个 p 元素

4. 通用兄弟选择器

```css
h2~p {
    color:blue;
}
```

选中紧跟在 h2 后面的所有 p 元素

### 2.4 分组选择器

是将不同的选择器组合在一起，使用逗号分隔，也称为并集选择器。

使用场景：多个元素具备相同样式

语法：

```css
div,
span {
    color:pink;
}
```

### 2.5 伪类和伪元素选择器

选择元素的特定状态或结构位置，符号是冒号（：）

1. **状态伪类**：根据用户交互或状态变化选择。比如：鼠标经过链接、表单获得焦点等。
   
       **1.1 链接伪类**
   
       链接伪类用于根据**链接的不同状态**（如为访问、悬停、点击等）为其添加样式。从而提升用户体验和界面交互性。
   
   | 链接伪类      | 作用                 |
   | --------- | ------------------ |
   | a:link    | 未访问链接的默认样式         |
   | a:visited | 已访问链接的样式           |
   | a:hover   | 鼠标悬停在链接上时的反馈       |
   | a:active  | 链接被点击时的瞬时状态（按下到松开） |

        伪类顺序规划（LVHA 顺序）—>a:link->a:visited->a:hover->a:active

```html
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>fifth</title>
  <link rel="stylesheet" href="./fifth.css">
</head>

<body>
  <a href="https://www.doubao.com" target="_blank">豆包一下</a>
</body>
```

```css
a:link {
  color: #000;
}

a:visited {
  color: antiquewhite;
}

a:hover {
  color: red;
}

a:active {
  color: blue;
}        
```

{% asset_img ressult4.png %}   

![](C:\Users\Lenovo\AppData\Roaming\marktext\images\2026-01-21-14-16-15-image.png)  

        **1.2 用户行为伪类**

        用户以某种方式和文档交互的时候应用，这些用户行为伪类，又是叫做伪类

使用场景：

- 鼠标经过元素的时候，修改样式。

- 表单获得焦点的时候

| 动态伪类   | 作用          |
| ------ | ----------- |
| :hover | 鼠标经过元素      |
| :focus | 获得焦点的元素（表单） |

```css
.box:hover {
    color:pink;
}
```

2. **结构伪类**：根据元素的位置选择。比如：第 5 个第 10 个元素、选择前 3 个元素等。

| 结构伪类          | 作用               |
| ------------- | ---------------- |
| :first-child  | 一组兄弟元素中的第一个元素    |
| :last-child   | 一组兄弟元素中的最后一个元素   |
| :nth-child(n) | 一组兄弟元素列表中第 n 个元素 |

```css
.ul li:first-child {
    color:red;
}
```

n 的取值可以是：

- 数字。从 1 开始

- 关键字。odd 奇数，even 偶数

- 公式。:nth-child(3n) 3的倍数：第3 6 9...个元素

                  :nth-child(n+2) 第 2 个以及以后的元素

                   :nth-child(-n+3) 前面 3 个元素

**注意**：公式的 n 取值从 **0** 开始计算  

3. **表单伪类**：针对表单元素的状态，比如：表单禁用、选中复选框等。

| 表单伪类      | 作用          |
| --------- | ----------- |
| :disabled | 表单禁用        |
| :checked  | 选中状态，单选复选按钮 |

```css
button:disabled{
    /* 透明度，嚷着按钮透明 0-1 */
    opacity:.4;
}
```

4. **伪元素选择器**：选中元素的特定部分（使用双冒号::）

使用场景：

1. 让表单里面的 placeholder 文字便颜色

2. 做更多的修饰效果

| 伪元素选择器         | 作用                       |
| -------------- | ------------------------ |
| ::first-line   | 选择首行                     |
| ::first-letter | 首字母                      |
| ::placeholder  | 选择 input 或者 textarea 占位符 |
| ::before       | 元素内插入伪元素，作为第一个元素         |
| ::after        | 元素内插入伪元素，作为最后一个元素        |

```css
div::before {
    content:"开始";
    color:red;
} 
div::after {
    content:"结束";
    color:red;
} 
```

{% asset_img ressult5.png %}

![](C:\Users\Lenovo\AppData\Roaming\marktext\images\2026-01-21-14-52-27-image.png)

注意：

- before 和 after 是插入伪元素，特性类似内联元素

- content 属性是必须的，没有内容空引号即可

- 后期非常常用，比如小图标、各种装饰效果等
5. **属性选择器**：根据元素的属性特征来精准定位元素，从而实现更灵活的样式控制

使用场景：

1. 表单样式控制

2. 图标字体控制

3. 图表化语言适配等

| 属性选择器   | 作用                 |
| ------- | ------------------ |
| [属性]    | 匹配包含指定属性的元素        |
| [属性=值]  | 匹配属性值等于指定值的元素      |
| [属性^=值] | 匹配属性值以指定字符串开头的元素   |
| [属性$=值] | 匹配属性值以指定字符串结尾的元素   |
| [属性*=值] | 匹配属性值任意位置包含指定子串的元素 |

```css
a[class] {
  color: red;
}
```

```html
<a href="#" class="shux">属性</a>
```

{% asset_img ressult6.png %}

![](C:\Users\Lenovo\AppData\Roaming\marktext\images\2026-01-21-15-08-38-image.png)

# 3. CSS 文本样式

CSS 文本样式用于控制网页中文字的外观。包括字体、颜色、对齐、间距等，主要分为两大类：

1. 字体样式：比如使用哪种字体，字体大小、字体粗体、斜体等等

2. 文本布局：比如文本对齐、行高、字间距、首行缩进等等

**注意**：文字无法直接通过 CSS 来更改样式，必须要用适合的标签来包裹它们，**本质是修改标签样式**，里面的文字跟随样式变化。

### 3.1 字体样式

| 字体样式            | 说明     |
| --------------- | ------ |
| color           | 设置字体颜色 |
| font-family     | 字体族    |
| font-size       | 字体大小   |
| font-style      | 字体风格   |
| font-weigh      | 字体粗体   |
| text-decoration | 字体装饰   |

#### 3.1.1 color-字体颜色

1. 关键字

这些颜色通常不会在生产环境的网站中使用，主要学习使用。
比如：red、green、blue、pink等。
例如：p { color: pink;}

2. 十六进制

这个是开发**最常用**的。实际开发中，我们从设计稿直接复制即可。

比如：红色 #FF0000 或者 #F00

例如：p { color: #f00; }

3. rgb格式

rgb() 函数接受三个参数，分别表示颜色的红、绿和蓝。 也是设计稿复制的

比如：红色 rgb(255,0,0)

例如：p { color: rgb(255,0,0) }

另有：rgba(255,0,0, 0.3) 文字透明，最后一个数值取值 0~1。

0完全透明 1 完全不透明

#### 3.1.2 font-family 字体族

给定一个有**先后顺序**的，有字体名或者字体族名组成的列表来为选定的元素设置字体。

```css
body {font-family:Arial,Helvetica,sans-serif;}
```

属性值用逗号隔开。浏览器会选择列表中第一个该计算机上有安装的字体。网页建议开发使用无衬线字体。

#### 3.1.3 font-size 字体大小

font-size 可以设置字体大小：像素 px

CSS 像素（CSS Pixel） 是 CSS 中用于定义长度、尺寸的单位（简写为 px）**绝对单位**

不同浏览器默认字体大小不一样，谷歌默认16px，建议给 body 标签统一指定大小，做到浏览器统一

```css
body {
    font-size:16px;
}
```

#### 3.1.4 font-style 字体风格

font-style 用来打开和关闭文本 italic (斜体) 。
属性值：

- normal:  将文本设置为普通字体 (将存在的斜体关闭)

- italic:  如果当前字体的斜体版本可用，那么文本设置为斜体版本

**最常见**：让 em 或 i 标签取消默认倾斜

#### 3.1.5 font-weight 字体粗体

font-weight 设置文字的粗体大小

使用场景：

1. 很多标题是不要加粗的，此时可以用 CSS 取消加粗。

2. 部分大批量文字可以利用CSS加粗。

属性值：

- normal: 正常粗细

- bold: 加粗 

其他值受属性影响基本不用。

数字属性值：（**常用**）

- 400: 正常粗细

- 700: 加粗

取值范围100~900 之间，常用就是400和700

#### 3.1.6 text-decoration 字体装饰

设置 / 取消字体上的文本装饰。

使用场景：

1. 最常见设置链接下划线，比如取消下划线等

2. 特殊情况添加删除线

属性值：

- none：取消文本装饰

- underline：下划线

- overline：上划线

- line-through：穿过文本的线

### 3.2 文本布局

| 字体样式           | 说明     |
| -------------- | ------ |
| text-align     | 文本对齐   |
| text-indent    | 首行缩进   |
| letter-spacing | 文本字符间距 |
| line-height    | 行高     |

#### 3.2.1 text-align 文本对齐

控制文本在它所在的块级盒子内**如何水平对齐**

适用场景：

1. 文本/图片在盒子水平对齐。

2. 文章文字两端对齐

属性值：

- left：文本左对齐（默认）

- right：文本右对齐

- center：文本对平居中对齐

- justify：自动改变字间距，两端对齐

#### 3.2.2 text-indent 文本缩进

设置**块级元素**中文本行前面空格（**缩进**）的长度

适用场景：

1. 段落首行缩进2个字的效果。

2. logo隐藏文字效果（在笔记后面）。 

属性值：数字：常见单位是em，相对单位，**本元素的文字大小**；1em 等于当前元素的字体大小，如果当前元素没有大小，则按照父元素文字大小。与 px 一样，1 em = 16 px

#### 3.2.3 letter-spacing 字间距

用于设置文本字符的间距

使用场景：调整字与字之间距离，用户体验更好

属性值：数字，单位 px

#### 3.2.4 line-height 行高

设置文本每行之间的高

使用场景：

1. 设置多行文本之间的上下间距

2. 让单行文本垂直居中

属性值：

- 数字 px

- 数字不带单位（当前字体大小的倍数）1.5 = 16 * 1.5 px

{% asset_img result3.png %}

![](C:\Users\Lenovo\AppData\Roaming\marktext\images\2026-01-20-18-18-59-image.png)

# 4. font 简写

font 简写属性在一个声明中设置多个字体属性

使用场景：给整个页面设置相关字体样式

语法：

```html
font:font-style font-weight font-size/line-height font-family
```

有严格的书写顺序，其中 font-size 和 font-family 是必须写的，其他可以省略，默认显示

# 5. CSS 继承性

子元素自动继承父元素的某些 CSS 样式属性

- 主要继承跟文字相关的样式属性，比如字体、颜色、文本对齐等

- 但是子元素定义自己的样式，会优先自己的样式

- 能继承大部分与文字相关的

# 6. CSS 优先级

优先级由选择器的权重决定，权重高的规则覆盖权重低的规则。浏览器通过优先级来判断哪些属性值与一个元素最为相关。优先级是基于不同种类**选择器**组成的**匹配规则**。
原则：

1. 优先级相等的时候，CSS 中**最后**的那个声明的样式将会被应用到元素上。（层叠遵循就近原则）
2. 其余判断那个选择器**权重**高，优先执行那个样式。
3. 权重是4位一组，是分开的层级，不能进位。

| 选择器类型       | 示例                    | 权重值          | 优先级说明               |
| ----------- | --------------------- | ------------ | ------------------- |
| !important  | color:red !important  | 无限大          | 强制覆盖所有规则（慎用）        |
| 内联样式        | div style="color:red" | (1,0,0,0)    | 行内样式权重最高(1，0，0，0)   |
| ID 选择器      | #myid                 | (0,1,0,0)    | 每个 ID 增加 0,1,0,0    |
| 类 / 属性 / 伪类 | .class, [type="text"] | (0, 0, 1, 0) | 每个类/属性/伪类增加 0,0,1,0 |
| 类型（标签）/伪元素  | div, ::after          | (0, 0, 0, 1) | 每个标签/伪元素增加 0,0,0,1  |
| 通配符/继承      | *, 继承的样式              | (0, 0, 0, 0) | 通配符和继承权重最低          |

# 7. 盒子模型

所有的元素都被一个个的“盒子”包围着，在 CSS 中，一般分为**区块盒子**和**行内盒子**。

**区块盒子（block）**：

1. 盒子会产生换行

2. width 和 height 属性可以发挥作用

3. 不设置宽度则默认是父元素空间的 100%

4. 内边距、外边距和边框会撑大元素

5. 常见的比如：div、p、h、ul、table等

**行内盒子（inline）**：

1. 盒子不会产生换行

2. width 和 height 属性将不起作用

3. 垂直方向的内边距、外边距不起效果

4. 水平方向的内边距、外边距会有效果

5. 常见的比如：span、em、a、strong等

### 7.1 盒子模型组成

CSS 盒子模型整体上适用于区块盒子，包含盒子内容、内边距、外边距、边框四部分

1. 盒子内容：显示内容的区域，由内容或者指定宽度高度来决定内容大小

2. 内边距 padding：内容距离边框之间的距离

3. 边框 border：边框盒子包住内容和内边距

4. 外边距 margin：更改盒子与其他元素值阿金的距离

#### 7.1.1 边框

**属性值**：

border：边框粗细 边框样式 边框颜色；

- 边框有三部分属性值组成，之间必须**空格**隔开

- 三部分属性值**没有先后顺序**

| 边框样式   | 描述   | 视觉效果     |
| ------ | ---- | -------- |
| dotted | 点状边框 | 圆点组成的虚线  |
| dashed | 虚线边框 | 短横线组成的虚线 |
| solid  | 实线边框 | 单一线条     |

若遇到需设置四个边框不同样式的情况，可根据方位名词：top、bottom、left、right

1. border-top：1px solid pink；

2. border-botton：1px solid pink；

3. border-left：1px solid pink；

4. border-right：1px solid pink；

**圆角边框**：border-radius：数字或百分比

```css
.button {
    border-radius: 10px;
}
```

实现：

- 胶囊圆角：长方形设置圆角为宽度的一半；

- 圆形：正方形设置圆角为高度一半或者50%

若需对四个角分别设置样式，可：

| 圆角写法                               | 作用                          |
| ---------------------------------- | --------------------------- |
| border-radius：10px;                |                             |
| border-radius:10px 20px;           | 左上 右下是10px；右上 左下是20px       |
| border-radius:10px 20px 30px;      | 左上是10px；右上左下是20px；右下30px    |
| border-radius:10px 20px 30px 40px; | 左上10px；右下20px；右下30px；左下40px |

border-radius：顺时针记忆（左上角 右上角 右下角 左下角）

#### 7.1.2 内边距

内边距（padding）多个值用空格隔开，顺时针记忆

| 内边距写法                        | 作用                      |
| ---------------------------- | ----------------------- |
| padding:10px;                | 上下左右 4 个内边距都是 10px      |
| padding：10px 20px;           | 上下内边距是10px，左右内边距是20px   |
| padding:10px 20px 30px;      | 上是10px，左右是20px，下是30px   |
| padding:10px 20px 30px 40px; | 上10px，右20px，下30px，左40px |

单边设置：根据方位名词：top、bottom、left、right（与边框设置一样）

#### 7.1.3 外边距

外边距是盒子周围一圈看不到的空间，它会把其他元素推离盒子。

| 外边距写法                       | 作用                      |
| --------------------------- | ----------------------- |
| margin:10px;                | 上下左右 4 个外边距都是 10px      |
| margin:10px 20px 30px 40px; | 上下外边距是10px，左右外边距是20px   |
| margin:10px 20px 30px 40px; | 上是10px，左右是20px，下是30px   |
| margin:10px 20px 30px 40px; | 上10px，右20px，下30px，左40px |

单边设置：根据方位名词：top、bottom、left、right（与边框设置一样）

**注意**：

1. 行内元素左右外边距生效，上下外边距无效

2. 行内元素设置宽度和高度也无效

区块元素可以利用 margin 实现**水平居中**

- 块级盒子**必须有宽度**

- 只需要设置**左右外边距为 auto** 即可

**外边距塌陷**：区块元素上下外边距会出现塌陷情况：

1. 嵌套关系（父子）的区块元素

2. 给子盒子设置上下外边距会让父盒子塌陷移动

解决方案：

1. 给父盒子添加上边框。（父盒子本身有边框则不会出现问题）

2. 给父盒子添加上内边距。（同理）

3. 给父盒子添加：overflow:hidden;（同理）

### 7.2 盒子模型-尺寸计算

在 CSS 盒子模型的默认定义里，除了宽度和高度增加盒子大小之外，padding 和 border 都会让盒子变大。

例如：

{% asset_img result7.png %}

![](C:\Users\Lenovo\AppData\Roaming\marktext\images\2026-01-22-16-00-55-image.png)

**解决方法**：box-sizing 用于定义元素的盒子模型计算方式，控制元素的 width 和 height 是否包含 padding 和 border

语法：box-sizing:属性值; 如：box-sizing:border-box;

| 属性值         | 描述                                                                                |
| ----------- | --------------------------------------------------------------------------------- |
| content-box | 默认值。元素的 width 和 height 仅包含内容区域，不包含 padding 和 border。<br/>理解：width = 内容的宽度         |
| border-box  | 元素的 width 和 height 包含内容、padding 和 border。<br/>理解：width = border + padding + 内容的宽度 |

### 7.3 盒子背景

用于设置元素背景相关属性，包括背景颜色、背景图片、背景位置、背景重复方式等

| 属性                    | 作用         | 常用值                                    | 示例代码                          |
| --------------------- | ---------- | -------------------------------------- | ----------------------------- |
| background-color      | 设置元素背景颜色   | 颜色名称、十六进制、RGB、透明度                      | background-color:#f0f0f0;     |
| background-image      | 设置背景图片     | url（image.jpg）                         | background-image:url(bg.png); |
| background-repeat     | 控制背景图片是否重复 | repeat(默认)、no-repeat、repeat-x、repeat-y | background-repeat:no-repeat;  |
| background-position   | 定位背景图片位置   | x y（如center top，或者px、%单位）              | background-position:center;   |
| background-size       | 调整背景图片尺寸   | 默认 auto、cover（覆盖）、contain（包含）或者跟 px、%  | background-size:cover;        |
| background-attachment | 背景是否随页面滚动  | scroll（默认）、fixed（固定，针对于当前视口）           | background-attachment:fixed;  |

**背景复合写法**：

background:颜色 图片 重复 固定  位置/尺寸;（与顺序无关）

### 7.4 背景渐变

在 CSS 中，可以通过 linear-gradient（线性渐变）和 radial-gradient（径向渐变）为元素添加渐变背景

| 属性 / 方法                              | 描述            | 示例代码                                                                                                                     |
| ------------------------------------ | ------------- | ------------------------------------------------------------------------------------------------------------------------ |
| linear-gradient(方向，颜色1 位置，颜色2 位置...) | 线性渐变（方向可控）    | background：linear-gradient(to right，#ff6b6b,#4ecdc4)<br/>background-image：linear-gradient(90deg，#ff6b6b 30%,#4ecdc4 70%) |
| radial-gradient(形状，颜色1，颜色2...)       | 径向渐变（形状和位置可控） | radial-gradient（circle,#ff9a9e,#fad0c4)                                                                                  |

**线性渐变**：

1. 方向。可以是方位名词，也可以是 deg（角度）

2. 位置。色标的位置，可选填。

**文字背景线性渐变**：

background:linear-gradient(to right,pink,red); 设置背景渐变

-webkit-background-clip:text; 兼容性写法，照顾谷歌老版本浏览器 -webkit-

background-clip:text; 文字范围裁剪背景

-webkit-text-fill-color:transparent; 文本填充颜色设置为透明

### 7.5 盒子阴影

CSS box-shadow 属性用于在元素的框架上添加阴影效果，盒子添加阴影，效果更立体，鼠标经过元素显示阴影，更加突出元素。

语法：

box-shadow:X轴偏移量 Y轴偏移量 模糊半径 扩散半径 颜色;

1. 多个属性用空格隔开

2. X轴偏移量和Y轴偏移量是必须要写的，奇语可省略采取默认值

3. 默认是外阴影，如果改为内阴影要写 inset

```css
.nav li {
    box-shadow:0 15px 30px rgba(0,0,0,.1)
}
```

### 7.6 过渡

过渡效果用于在元素的属性值发生变化时，平滑地过渡（而不是瞬间切换）

**使用场景**：

1. 鼠标经过图片放大

2. 表单获得焦点，输入框变宽

**语法**：

transition：过度属性 过渡时间

1. 属性值中间空格隔开

2. 过渡属性如果都要变化可以写 all

3. 过渡时间单位是秒s，比如0.2s等

**注意**：过渡写到盒子上，谁做过渡给谁加

### 7.7 样式初始化

浏览器对 HTML 元素有默认样式（如 margin、padding、font-size）。

**初始化的核心目的**：

1. 统一浏览器默认样式，消除差异

2. 减少后续开发中的冗余代码

3. 提高代码可维护性

### 7.8 单行文本溢出显示省略号

```css
/* 溢出隐藏 */
overflow:hidden;
/* 文本溢出显示省略号 */
text-overflow:ellipsis;
/* 强制文字一行显示，不换行 */
white-space:nowrap;
```

### 7.9 多行文字溢出显示省略号

```css
/* 旧版弹性盒子布局 */
display:-webkit-box;
/* 文本垂直排列 */
-webkit-box-orient:vertical;
/* 限制显示行数 */
-webkit-line-clamp:3;
/* 隐藏溢出内容 */
overflow:hidden;
/* 文本溢出显示省略号 */
text-overflow:ellipsis;
```

**注意**：盒子的高度需要与限制显示文本的高度一致才能正确显示省略号

# 8. 字体图标

字体图标是一种以字体形式嵌入网页的技术，允许开发者像使用文字一样通过 CSS 控制图标的样式（如颜色、大小、阴影等）

字体图标要么设计师提供，要么去字体库下载

| 图标库             | 特点                         | 官网链接                    |
| --------------- | -------------------------- | ----------------------- |
| Font Awesome    | 图标最全，支持免费版和 pro 付费版        | fontawesome.com         |
| Bootstrap Icons | Bootstrap 生态内图标，简单易用       | icons.getbootstrap.com  |
| icomoon         | IcoMoon 最早推出了第一个自定义图标字体生成器 | icomoon.io              |
| iconfont        | 阿里字体库，包含淘宝图标库和阿里妈妈图标库（免费）  | http://www.iconfont.cn/ |

**使用步骤**：

1. 下载字体图标文件：去官网或者设计师准备字体图标文件，保存到项目目录下。

2. 引入html文件中：根据提供的压缩包，引入CSS文件（link方式）

3. 使用字体图标：一般情况下，我们通过标签调用类名选择对应字体图标。根据实际需求，调整字体样式，比如颜色、大小、位置等

# 9. 精灵图

CSS 精灵图（CSS Sprites）是将多个小图标或图像合并到**一张大图中**，通过调整 **background-position** 属性来显示特定部分的图像技术。

**优势**：

1. 减少 HTTP 请求：多个小图标合并为一张图片，只需一次请求。

2. 提升性能：减少网络开销，尤其适合移动端或低带宽场景。

3. 统一管理：方便维护图标集，避免文件分散。

**使用场景**：

1. 导航菜单图标

2. 按钮操作图标

3. 复杂彩色小图标更适合精灵图

**注意**：通过合理使用 CSS 精灵图，可以有效优化网页性能。对于复杂场景（如高清屏适配），建议结合 SVG 或字体图标使用。

原理：

1. 给盒子添加背景图片

2. 通过背景定位（background-position）移动位置对齐

3. 注意网页坐标不同。

# 10. CSS布局

CSS 布局是网页设计的核心技术之一，用于控制元素在页面中的排列方式

1. normal：正常布局

2. display：模式转换布局

3. flexbox：弹性布局

4. grid：网格布局

5. position：定位布局

6. column：多列布局

### 10.1 display 转换

display 属性允许我们更改默认的显示方式

1. display:block; 转换为区块元素（常用）

2. display:inline; 转换为行内元素（罕见）

3. display:inline-block; 转换为行内块元素（较少）

### 10.2 浮动(被放弃的布局方式)

浮动（float）可以让元素脱离文档流，向左或享有浮动，直到碰到父容器边缘或其他浮动元素

| 属性值   | 作用      | 示例           |
| ----- | ------- | ------------ |
| left  | 左侧浮动    | float:left;  |
| right | 右侧浮动    | float:right; |
| none  | 默认值，不浮动 | float:none;  |

**浮动带来的影响**：

1. 父盒子没有高度。（很多情况下不能给父亲指定高度）

2. 子元素浮动。

3. 影响其他盒子布局。

**解决**：清除浮动，也可理解为闭合浮动，就是让浮动的元素尽量控制在父盒子内，不要影响其他盒子。

**清除浮动主要有四种方式**：

1. 额外标签法：在浮动元素的最后面，新增一个块级标签。添加属性：clear:both;

2. 单伪元素清除浮动：父元素添加伪元素。

3. 双伪元素清除浮动：父元素添加双伪元素。

4. overflow 清除浮动：父元素添加 overflow:hidden;。

### 10.3 弹性盒子（主流）

Flexbox 是 CSS 弹性盒子布局模块（Flexible Box Layout Module）的缩写，可以快速实现元素的对齐、分布和空间分配。

**弹性盒子核心**：

1. 父控子（亲父子）
   
   - 父盒子控制子盒子如何排列布局
   
   - 父盒子称为容器，子盒子成为项目

2. 主轴和交叉轴（侧轴）
   
   - 主轴默认水平方向，交叉轴默认垂直方向（可以更改）

**容器（父盒子）属性**：

| 属性              | 作用                                         | 示例                                       |
| --------------- | ------------------------------------------ | ---------------------------------------- |
| display         | 定义元素为 Flex 容器                              | .container{display:flex;}                |
| flex-direction  | 定义主轴方向（项目排列方向）                             | .container{flex-direction:row;}          |
| flex-wrap       | 控制是否换行                                     | .container{flex-wrap:wrap;}              |
| justify-content | 定义主轴上的对齐方式（整体分布）                           | .container{justify-content:center;}      |
| align-items     | 定义交叉轴上的对齐方式（单行时整体对齐                        | .container{align-items:center;}          |
| align-content   | 定义多行是交叉轴上的对齐方式（仅当 flex-wrap:wrap 且内容换行时生效） | .container{align-content:space-between;} |

**项目（子盒子）属性**：

| 属性          | 作用                                    | 示例                        |
| ----------- | ------------------------------------- | ------------------------- |
| order       | 定义项目的排列顺序（默认0，数值越小越靠前）                | .item{order:-1;}          |
| flex-grow   | 定义项目的放大比例（默认0，即不放大）                   | .item{flex-grow:1;}       |
| flex-shrink | 定义项目的缩小比例（默认1，空间不足时等比缩小）              | {flex-shrink:0;}          |
| flex-basis  | 定义项目在主轴方向上的初始大小（优先级高于 width / height） | .item{flex-basis:200px;}  |
| flex        | flex-grow flex-shrink flex-basis 的简写  | .item{flex:1;}            |
| align-self  | 覆盖容器的 align-items，单独定义某个项目的交叉轴对齐方式    | .item{align-self:center;} |

容器（父盒子）设置 **display:flex**; 可以让子盒子按照主轴方式排列

- 如果子元素有大小，则按照给定大小来显示。

- 如果子元素没有大小，则拉伸充满父容器。

- 若子元素总宽度超过容器宽度，默认会压缩子元素。

**大部分情况下**，父容器设置 display:flex，子元素设定大小

#### 10.3.1 **justify-content 定义主轴上的对齐方式**

| 属性值           | 效果       | 示例                   |
| ------------- | -------- | -------------------- |
| flex-start    | 左对齐（默认）  | 子元素靠左排列              |
| flex-end      | 右对齐      | 子元素靠右排列              |
| center        | 居中对齐     | 子元素居中                |
| space-between | 两端对齐     | 首个子元素放置于七点，末尾元素放置于终点 |
| space-around  | 项目两端间隔相等 | 每个子元素周围分配相同的空间       |
| space-evenly  | 项目间隔均匀分布 | 每个子元素之间的间隔相等         |

{% asset_img result8.png %}

![](C:\Users\Lenovo\AppData\Roaming\marktext\images\2026-01-23-18-28-35-image.png)

#### 10.3.2 align-items 定义交叉轴上的对齐方式（单行时整体对齐）

| 属性值        | 作用描述                    |
| ---------- | ----------------------- |
| flex-start | 项目在交叉轴起点对齐（默认）          |
| flex-end   | 项目在交叉轴终点对齐              |
| center     | 项目在交叉轴居中对齐              |
| stretch    | 项目拉伸填充整个容器高度（需子项目无固定高度） |

{% asset_img result9.png %}

![](C:\Users\Lenovo\AppData\Roaming\marktext\images\2026-01-23-18-38-35-image.png)

#### 10.3.3 flex-direction定义主轴方向（改变主轴方向）

| 属性值            | 描述                   | 示例效果                  | 代码示例                                       |
| -------------- | -------------------- | --------------------- | ------------------------------------------ |
| row            | 默认值。子元素沿水平主轴（从左到右）排列 | A B C（横向排列）           | .container{flex-direction:row;}            |
| row-reverse    | 子元素沿水平主轴反向排列（从右到左）   | C B A（反向横向排列）         | .container{flex-direction:reverse;}        |
| column         | 子元素沿垂直主轴（从上到下）排列     | A<br/>B<br/>C（纵向排列）   | .container{flex-direction:column;}         |
| column-reverse | 子元素沿垂直主轴反向排列（从下到上）   | C<br/>B<br/>A（反向纵向排列） | .container{flex-direction:column-reverse;} |
