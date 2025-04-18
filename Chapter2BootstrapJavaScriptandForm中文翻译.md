以下是课件内容的完整中文翻译：

---

**COMP7980 – 动态网页与移动编程  
COMP7270 – 网页与移动编程**

**第 2 章 Bootstrap、JavaScript 和表单**

**课程教师**：麻时钞博士、张策博士、姜锦田先生

---

**公告**

- 对上节课字体过小表示歉意。
- 将调整屏幕分辨率，并使用 Zoom 分享屏幕。
  - Zoom 链接：[https://hkbu.zoom.us/j/99775423344?pwd=8Wi6pJIZ29TDkzj0X4XnnbTTlEMjAj.1](https://hkbu.zoom.us/j/99775423344?pwd=8Wi6pJIZ29TDkzj0X4XnnbTTlEMjAj.1)
- 选择 Mac OS。
- 账户名：guest
- 账户密码：

---

**公告**

**教师变更**

- **张策博士 (Dr. ZHANG Ce)**  
  - 邮箱：cezhang@comp.hkbu.edu.hk  
  - 办公室：RRS 727  
  - 电话：3411-5979

- **姜锦田先生 (Mr. JIANG Jintian)**  
  - 邮箱：jintian-jiang@comp.hkbu.edu.hk  
  - 办公室：RRS 637  
  - 电话：3411-6454

- **麻时钞博士 (Dr. MA Shichao)**  
  - 邮箱：shichaoma@comp.hkbu.edu.hk  
  - 办公室：DLB 804  
  - 电话：3411-7599

---

**议程**

- 使用 Bootstrap 进行响应式网页设计
- 客户端 JavaScript
- HTML 表单元素

---

**响应式网页设计**

- 响应式网页设计（Responsive Web Design, RWD）是一种网页设计理念，旨在为各种设备提供最佳的浏览和交互体验。

---

**为什么需要 RWD？**

- 随着移动流量占比超过互联网总流量的一半，响应式设计变得越发重要。
- 这一趋势如此普遍，以至于谷歌开始提升移动端友好的网站在移动设备搜索中的排名。
- 这实际上对那些不支持移动设备的网站造成了不利影响。

---

**Bootstrap**

- Bootstrap 是一个流行的前端框架，提供了一系列预先设计好的 HTML、CSS 和 JavaScript 组件。它旨在简化响应式和移动端优先的网页及应用程序的开发过程。
- Bootstrap 提供了网格系统、CSS 样式以及一系列可直接使用的组件，例如导航栏、按钮、表单、模态框等。这些组件设计为易于定制和响应式，能够自动适应不同的屏幕尺寸和设备。

---

**浏览器的响应式模式**

- **Safari**

---

**浏览器的响应式模式**

- **Chrome**
  - 点击设备工具栏
    1. 鼠标右键，选择 `检查` 按钮。
    2. 找到 `设备工具栏`，点击它。

---

**Bootstrap 网格系统**

- Bootstrap 提供了一个响应式网格系统，帮助创建灵活且响应式的布局。该网格系统基于 12 列布局，允许开发人员轻松地在不同屏幕尺寸上组织和结构化内容。
- 网格类：Bootstrap 提供了定义网格系统中列的布局和行为的 CSS 类。您可以将这些类分配给 HTML 元素，以指定它们在不同屏幕尺寸下的行为。最常用的网格类是 col-xs-*、col-sm-*、col-md-* 和 col-lg-*，其中 * 表示元素应跨越的列数。

---

**断点**

---

**Bootstrap 网格系统**

- 响应式行为：Bootstrap 的网格系统本质上是响应式的。通过应用适当的网格类，您可以控制元素在屏幕尺寸变化时的堆叠或重新排列方式。例如，您可以指定一个元素在大屏幕上占据两列（col-lg-2），但在超小屏幕上占据整个宽度（col-12）。
- 嵌套与偏移：Bootstrap 允许您将列嵌套在其他列中，从而实现更复杂和嵌套的布局。您还可以使用偏移类在列之间创建间距或偏移它们在网格中的位置。

---

**为较小屏幕定义的列宽也会被较大屏幕继承，除非明确覆盖。**

- 在平板电脑或桌面设备上查看时
- 在手机上表现为常规块级元素

```html
<div class="container text-center">
<div class="row"> <div class="col-md-8">.col-md-8</div> <div class="col-6 col-md-4">.col-6 .col-md-4</div> </div>
<div class="row"> <div class="col-6 col-md-4">.col-6 .col-md-4</div> <div class="col-6 col-md-4">.col-6 .col-md-4</div> <div class="col-6 col-md-4">.col-6 .col-md-4</div> </div>
<div class="row"> <div class="col-6">.col-6</div> <div class="col-6">.col-6</div> </div> </div>
```

---

**Bootstrap 网格系统**

- 在前面的例子中，`container` 类创建了一个网格系统的响应式容器。`row` 类表示网格中的一行，而 `col-*-*` 类定义了列。
- 在 Bootstrap 5 中，不指定列宽的 `col` 类是一个简写类，表示等宽列。

```html
<div class="row">
<div class="col card">
Card 1
</div> <div class="col card">
Card 2
</div> <div class="col card">
Card 3
</div> <div class="col card">
Card 4
</div>
</div>
```

---

**嵌套**

- 列可以相互嵌套，以创建更复杂的布局。
- 这允许您将一列细分为多个子列，每个子列都有自己的宽度和内容排列方式。

```html
<div class="container text-center"> <div class="row"> <div class="col-sm-3"> Level 1: .col-sm-3 </div> <div class="col-sm-9"> <div class="row"> <div class="col-8 col-sm-6"> Level 2: .col-8 .col-sm-6 </div> <div class="col-4 col-sm-6"> Level 2: .col-4 .col-sm-6 </div> </div> </div> </div> </div>
```

---

**Bootstrap**

- 响应式 CSS：Bootstrap 包含了启用元素响应式行为的 CSS 类和工具。它允许您根据屏幕尺寸显示或隐藏内容，调整内边距和外边距，以及控制元素的可见性。

```html
<div class="d-none d-md-block">
此元素在小屏幕上隐藏，但在中等及以上屏幕尺寸上可见。
</div>
<div class="d-sm-none">
此元素在小屏幕上隐藏，但在中等及以上屏幕尺寸上可见。
</div>
<div class="d-lg-none d-xl-block">
此元素在大屏幕上隐藏，但在超大屏幕上可见。
</div>
```

**外边距与内边距**

- 间距单位 = 1rem
- = 字体大小
- = 默认值 16px

```html
<div class="container my-4">
<!-- 内容 -->
</div>
```

---

**更多关于 Bootstrap**

- 预设计的组件：Bootstrap 提供了一系列在网页开发中常用的预设计 UI 组件，例如导航菜单、按钮、表单、卡片、轮播图等。这些组件具有默认样式和响应式行为，便于创建一致且美观的界面。
- JavaScript 插件：Bootstrap 包含了一系列 JavaScript 插件，为组件添加交互性和增强功能。这些插件提供了下拉菜单、模态框、工具提示、轮播图等功能，无需您从头编写复杂的 JavaScript 代码。

---

**客户端脚本编写与 JavaScript**

- JavaScript 的设计目的是为 HTML 页面添加交互性。
- 注意，JavaScript 和 Java 是两种在概念和设计上完全不同的语言！
- 我们使用 JavaScript 来定义网页的行为。

---

**响应事件**

- 当某些事件发生时执行，例如页面加载完成或用户点击 HTML 元素。
- 例如：`onchange`、`onclick` 等。
- 读取和写入 HTML 元素
- 读取并更改 HTML 元素的内容。

```javascript
function teamSelected(team) {
var superheroElem = document.getElementById("superhero"); superheroElem.options.length = 0;
}
```

**JavaScript 能做什么？**

---

**在 DOM 树中访问 HTML 元素**

- 获取具有指定 ID 的元素。
- 当网页加载时，浏览器会创建该页面的文档对象模型（DOM 树）。
- 要访问 DOM 树中任意节点（）的父元素，使用：

```javascript
elem
document.getElementById("superhero")
elem.parentNode
```

---

**读取和写入 HTML 元素**

- 为特定 ID 元素分配新的类名：
- 编辑特定 ID 元素的样式属性：
- 修改内部 HTML：

```javascript
document.getElementById("myid").classList.add("active");
document.getElementById("myid").style.display = "none";
document.getElementById("myid").innerHTML = "内部内容";
```

---

**querySelector 与 querySelectorAll**

- 这些方法返回与指定 CSS 选择器匹配的元素。

```javascript
document.querySelector('td');
document.querySelector('#id2');
document.querySelectorAll('.sundays');
document.querySelectorAll('ol[start="5"]');
```

---

**querySelector 与 querySelectorAll**

- 文档方法 querySelector() 返回文档中第一个匹配指定选择器或选择器组的元素。如果未找到匹配项，则返回 null。
- 文档方法 querySelectorAll() 返回文档中匹配指定选择器或选择器组的所有元素的集合。

---

**数组**

- 数组用于按特定顺序存储和管理一系列元素。
- 在 JavaScript 中，数组允许您将多个值组合在单个名称下，并使用数字索引访问这些值。
- 在 `person` 对象的上下文中，`avengers` 是一个数组属性，您可以通过索引符号 `avengers[index]` 访问数组中的特定元素。索引表示元素在数组中的位置，从 0 开始表示第一个元素。

```javascript
const avengers = ['Iron Man', 'Captain America', 'Thor', 'Hulk', 'Black Widow', 'Hawkeye'];
```

---

**for…of**

- 可以使用 `for...of` 循环遍历数组的所有元素。

```javascript
for (var avenger of avengers) {
console.log(avenger);
}
// Iron Man Captain America Thor Hulk Black Widow Hawkeye
```

---

**HTML 表单元素**

- 输入元素：`<input>` 元素用于创建文本框、复选框、单选按钮等。它允许用户输入数据。`type` 属性决定了输入元素的具体类型。
- 类型属性：`<input>` 元素的 `type` 属性指定要显示的输入控件类型。常见值包括用于文本框的 `text`、用于密码框的 `password`、用于数字输入的 `number`、用于复选框的 `checkbox` 和用于单选按钮的 `radio`。
- 选择元素：`<select>` 元素创建下拉菜单或列表框。它允许用户从预定义的列表中选择选项。`<select>` 元素内的 `<option>` 元素表示可用的选择项。

---

**HTML 表单元素**

- 客户端验证：HTML5 提供了客户端验证功能，可在提交表单之前验证表单输入。
- 必填属性：`required` 属性用于标记输入字段为必填项。将其应用于输入元素时，它确保用户在提交表单之前必须在该字段中输入值。
- 为数字字段指定有效范围，使用 `max` 和 `min`。

---

**HTML 表单元素**

- 禁用属性：`disabled` 属性禁用输入元素，防止用户与其交互。
- 按钮元素：`<button>` 元素创建可点击的按钮。
- `type` 属性指定按钮的行为。
  - `type="submit"` 用于创建提交按钮，触发表单提交。
