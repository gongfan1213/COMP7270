以下是课件内容的完整中文翻译：

---

**第1章 网页开发入门**

**课程教师**：刘进伟博士、张策博士、姜金田先生

**学习目标**
- 能够使用标记语言创建HTML页面
- 能够使用CSS为HTML页面添加样式

**什么是HTML？**
- HTML代表超文本标记语言（Hyper Text Markup Language）。
- 它是一种标记语言，而不是编程语言。
- 注意，标记语言是一种对文本进行注释的系统，使其与文本本身有所区分。

**标签、元素和属性**
- 标签的名称出现在尖括号之间，例如<tag_name>。
- 这是一个开始标签，结束标签的名称前面有一个正斜杠，即</tag_name>。
- 一对开始和结束标签之间的标记内容称为元素。
- 示例：<tag_name>标记内容</tag_name>

**标签、元素和属性**
- 允许嵌套元素
- 示例：
- 元素可以具有属性，这些属性出现在开始标签内，由一个或多个键值对组成，格式为attribute_name="attribute_value"或attribute_name='attribute_value'

**示例**
```html
<html>
<head>
<title> 这是一个起始页面 </title>
</head>
<body>
<h1 style="text-align:center"> 这是一个起始页面 </h1> 点击 <a href="http://www.comp.hkbu.edu.hk"> 这里 </a> 访问香港浸会大学计算机系 <br>
</body>
</html>
```

**HTML链接**
- 几乎所有网页中都有链接。
- 链接允许用户通过点击从一个页面跳转到另一个页面。
- 在HTML中，链接使用<a>标签指定。
- href属性指定目标地址，可以是：
  - 另一个文档，和/或
  - 由id指定的另一个元素

**HTML链接**
- 示例：
- 在HTML文档中创建一个命名的div：
  ```html
  <div id="cp3"> 第3章 </div>
  ```
- 在同一文档中创建指向“第3章”的链接：
  ```html
  <a href="#cp3"> 跳转到第3章 </a>
  ```
- 或者，从另一个页面创建指向“第3章”的链接：
  ```html
  <a href="anchor1.html#cp3"> 跳转到第3章 </a>
  ```

**示例**
```html
<!DOCTYPE html> <!-- anchor1.html -->
<html>
<head>
<title>锚点示例1</title>
</head>
<body>
<h1>锚点示例1：链接到同一文档</h1>
<p><a href="#cp3">跳转到第3章</a></p>
<p><a href="anchor2.html">跳转到锚点示例2</a></p>
<h2>第1章</h2>
<h2>第2章</h2>
<h2><a id="cp3">第3章</a></h2>
</body>
</html>
<!DOCTYPE html> <!-- anchor2.html -->
<html>
<head>
<title>锚点示例2</title>
</head>
<body>
<h1>锚点示例2：链接到另一个文档</h1>
<a href="anchor1.html#cp3">跳转到锚点示例1的第3章</a>
</body>
</html>
```

**HTML表格**
- 表格使用<table>标签定义。
- 表格通过<tr>标签划分为行。
- 每行通过<td>标签划分为数据单元格。
- <td>标签可以包含文本、链接、图像、列表、表单、其他表格等。
- <th>标签表示表格标题，其中的文本元素会以加粗和居中的方式显示。

**示例**
```html
<!DOCTYPE html>
<html>
<head>
<title>乘法表</title>
<style>
table, th, td {
border: 1px solid black;
}
</style>
</head>
<body>
<h1>5x5乘法表</h1>
<table style="width:50%">
<tr><td></td><th>1</th><th>2</th><th>3</th><th>4</th><th>5</th></tr>
<tr><th>1</th><td>1</td><td>2</td><td>3</td><td>4</td><td>5</td></tr>
<tr><th>2</th><td>2</td><td>4</td><td>6</td><td>8</td><td>10</td></tr>
<tr><th>3</th><td>3</td><td>6</td><td>9</td><td>12</td><td>15</td></tr>
<tr><th>4</th><td>4</td><td>8</td><td>12</td><td>16</td><td>20</td></tr>
<tr><th>5</th><td>5</td><td>10</td><td>15</td><td>20</td><td>25</td></tr>
</table>
</body>
</html>
```

**HTML列表**
- 无序列表
  - 使用<ul>标签定义
  - 每个列表项以<li>标签开始
- 有序列表
  - 使用<ol>标签定义
  - 每个列表项以<li>标签开始
- 列表可以嵌套

**示例**
```html
<!DOCTYPE html>
<html>
<head>
<title>HTML列表</title>
</head>
<body>
<ul>
<li>项目1</li>
<li>项目2：嵌套有序列表
<ol>
<li>嵌套项目1</li>
<li>嵌套项目2</li>
</ol>
</li>
<li>项目3</li>
</ul>
</body>
</html>
```

**什么是CSS？**
- CSS代表层叠样式表（Cascading Style Sheets）
- 样式定义了如何显示HTML元素

**CSS及其优势**
- HTML最初用于定义文档内容。
- CSS定义样式和格式：
  - 可以为任何元素一次性指定显示细节。
  - 样式可以保存在外部.css文件中。
  - 可以通过一个文件更改所有页面的呈现方式。

**CSS放在哪里？**
- 外部样式表
  - 样式应用于多个页面，每个页面必须在头部（head）部分使用<link>标签链接
- 内部样式表
  - 对于具有唯一样式的单个文档，使用<style>标签指定
- 内联样式
  - 使用style属性的样式标签

**CSS链接方式**
- CSS的插入方式：
  - 外部
  - 内部
  - 内联

**示例**
```html
<html>
<head>
<link rel="stylesheet" href="external.css">
<style>
p { color:#ff0033; }
</style>
</head>
<body>
<p style="color:#ff0033;"> 一些文本。 </p>
</body>
</html>
```

**CSS语法**
- 两个主要部分：选择器 {声明}
  - 选择器
    - 指定要样式的HTML元素。
    - 多个选择器用逗号分隔。
  - 声明
    - 每个声明由属性和值组成。
    - 多个声明用分号分隔。
    - 注释用/*和*/括起来。

**选择器匹配**
- 按元素名称选择所有元素 p {...}
- 按类名选择所有元素 .marked {...}
- 按id选择元素 #color {...}
- 指定所有元素 * {...}

**选择器匹配**
- 一些CSS属性
  - background-color：指定要使用的背景颜色。
  - color：指定文本颜色。
  - text-align：指定元素中文本的水平对齐方式
  - text-transform：控制文本的大小写
  - text-decoration：指定添加的装饰

**CSS属性**
- 一些CSS属性，续
  - font-family：指定元素的字体。
  - font-weight：设置文本中字符的粗细。
  - font-style：指定文本的字体样式。
  - font-size：设置字体大小。

**示例**
```css
body {
background-color: black; color: white; font-family: times, arial, serif;
}
h1 {
text-align: center; text-transform: uppercase; text-decoration: underline;
}
h2 {
font-weight: bold; font-style: oblique;
}
```

**CSS盒模型**
- 所有HTML元素都可以被视为盒子。

**CSS盒模型**
- 外边距（Margin）：清除边框周围的区域。外边距没有背景颜色，是完全透明的。
- 边框（Border）：围绕内边距和内容的边框。边框受盒子背景颜色的影响。
- 内边距（Padding）：清除内容周围的区域。内边距受盒子背景颜色的影响。
- 内容（Content）：盒子的内容，文本和图像出现的地方。

**CSS盒模型**
- 外边距、内边距示例
  - all_four margin: 0px;
  - top_and_bottom right_and_left padding: 2px 10px;
  - top right_and_left bottom padding: 2px 10px 5px;
  - top right bottom left padding: 2px 10px 5px 15px;

**CSS盒模型**
- 边框
  - border-width, border-style, border-color
  - 边框样式的部分值
    - none, dotted, dashed, solid, double
  - 示例
    - border: 5px solid gray;

**示例**
```html
<!DOCTYPE html>
<html>
<head>
<title>CSS盒模型</title>
<style>
.ex {
width: 220px; padding: 2px 10px 5px; border: 5px solid gray; margin: 0px;
}
</style>
</head>
<body>
<img src="http://via.placeholder.com/250x100/dec.png" width="250" height="100" /> <br>
<div class="ex">
上面的图像宽度为250px。<br>该元素的总宽度也是250px。
</div>
</body>
</html>
```

**CSS object-fit**
- object-fit属性指定替换元素的内容应如何适应由其高度和宽度确定的盒子。

**浮动元素**
- 浮动元素可以被推到左边或右边，允许其他元素围绕它排列。
- 元素如何浮动
  - 元素水平浮动。
  - 浮动元素将尽可能地向左或向右移动。

**HTML的块级元素和内联元素**
- HTML元素可以是块级元素或内联元素。
- 块级元素是一个占据整个可用宽度的元素，并且在其前后都有换行符。
  - 示例：<h1>、<p>、<div>
- 内联元素只占据必要的宽度，并且不会强制换行。
  - 示例：<span>、<a>、<img>

**显示属性**
- 使用CSS的display属性可以将内联元素更改为块级元素，反之亦然。
- 示例：
  - 要隐藏一个元素，可以将其CSS display属性设置为none

**示例**
```html
<!DOCTYPE html>
<html>
<head>
<title>CSS display示例</title>
</head>
<body>
<p>文本中的<span>内联span</span>。</p>
<p>文本中的<span style="display:block">块级span</span>。</p>
<ul>
<li>块级项目1</li>
<li style="display:inline">内联项目2</li>
<li style="display:inline">内联项目3</li>
<li style="display:none">隐藏项目4</li>
<li>块级项目5</li>
</ul>
</body>
</html>
```
