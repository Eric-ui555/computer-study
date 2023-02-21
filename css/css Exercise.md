[CSS 代码测试 - W3schools 在线教程](https://www.w3schools.cn/css/exercise.asp)

### CSS 选择器

1、将所有 < p > 元素的颜色更改为“红色”。

```css
p {
  color: red;
}
```

2、将 id="para1" 元素的颜色更改为“红色”。

```css
#para1 {
  color: red;
}
```

3、将具有“colortext”类的所有元素的颜色更改为“红色”。

```css
.colortext {
  color: red;
}
```

4、将所有 < p > 和 < h1 > 元素的颜色更改为“红色”。 将选择器分组以最小化代码。

```css
h1, p {
  color: red;
}
```

### CSS 如何使用

1、添加带有 URL 的外部样式表：“mystyle.css”。

```html
<link rel="stylesheet" href="mystyle.css">
```

2、使用内部样式表为页面设置 "background-color: linen"。

```css
body {
  background-color: linen;
}
```

3、使用内联样式为页面设置 "background-color: linen"。

```html
<body style="background-color: linen">

< h1 >This is a Heading</h1>
< p >This is a paragraph.</p>
< p >This is another paragraph.</p>

</body>
```

### CSS 背景颜色

1、将页面的背景颜色设置为“linen”，将 < h1 > 的背景颜色设置为“lightblue”。

```
body {
  background-color: linen;
}
h1 {
  background-color: lightblue;
}
```

2、将“paper.gif”设置为页面的背景图像。

```css
body {
  background-image: url("paper.gif");
}
```

3、将“gradient_bg_vertical.png”设置为页面的背景图片，仅垂直重复。

```css
body {
  background-image: url("gradient_bg_vertical.png");
  background-repeat: repeat-y;
}
```

4、指定背景图像应在右上角显示一次。

```css
body {
  background-image: url("img_tree.png");
  background-repeat: no-repeat;
  background-position: top right;
}
```

5、使用简写背景属性将背景图像设置为 `"img_tree.png"`，在右上角显示一次。

```css
body {
  background: url("img_tree.png") no-repeat top right;
}
```

### CSS 边框

1、为 < p > 设置“4px”、“点”边框。

```css
p {
  border-style: dotted;
  border-width: 4px;
}
```

2、将 < p > 的边框颜色设置为“红色”。

```css
p {
  border-style: dotted;
  border-width: 4px;
  border-color: red;
}
```

3、更改 3 个边框属性，使它们只显示顶部的边框。

```css
p {
  border-top-style: dotted;
  border-top-width: 4px;
  border-top-color: red;
}
```

4、使用边框属性：将 p 的边框设置为“10px”、“solid”和“green”。

```css
p {
  border: 10px solid green;
}
```

CSS 外边距

1、将 < h1 > 的左边距设置为“20px”。

```css
h1 {
  background-color: lightblue;
  margin-left: 20px;
}
```

2、将 < h1 > 的所有边距设置为“25px”。

```css
h1 {
  background-color: lightblue;
  margin:25px;
}
```

3、使用 margin 属性将 < h1 > 的上下边距设置为“50px”，将左右边距设置为“25px”。

```css
h1 {
  background-color: lightblue;
  margin: 50px 25px;
}
```

4、使用 margin 属性居中对齐 < h1 > 元素。

```css
h1 {
  background-color: lightblue;
  width: 300px;
  margin: auto;
}
```

### CSS 内边距

1、将 < p > 的顶部填充设置为“30px”。

```css
p {
  background-color: lightblue;
  padding-top: 30px;
}
```

2、将 < p > 的所有填充设置为“50px”。

```css
p {
  background-color: lightblue;
  padding: 50px;
}
```

3、使用 padding 属性将 < p > 的顶部和底部填充设置为“25px”，将左右填充设置为“50px”。

```css
p {
  background-color: lightblue;
  padding: 25px 50px;
}
```

### CSS 高度和宽度

1、将 < h1 > 的高度设置为“100px”。

```css
h1 {
  background-color: lightblue;
  height: 100px;
}
```

2、将 < h1 > 的宽度设置为“50%”。

```css
h1 {
  background-color: lightblue;
  width: 50%;
}
```

### CSS 盒子模型

1、将 div 的宽度设置为“200px”。

```css
div {
  background-color: lightblue;
  width: 200px;
}
```

2、将 div 的内边距设置为“25px”。

```css
div {
  background-color: lightblue;
  width: 200px;
  padding: 25px;
}
```

3、将 div 的边框设置为“25px solid navy”。

```css
div {
  background-color: lightblue;
  width: 200px;
  padding: 25px;
  border: 25px solid navy;
}
```

4、将 div 的边距设置为“25px”。

```css
div {
  background-color: lightblue;
  width: 200px;
  padding: 25px;
  border: 25px solid navy;
  margin: 25px;
}
```

### CSS 轮廓

1、为 < p > 设置“solid”、“5px”轮廓。

```css
p {
  outline-style: solid;
  outline-width: 5px;
}
```

2、将 < p > 的轮廓颜色设置为“绿色”。

```css
p {
  outline-style: solid;
  outline-width: 4px;
  outline-color: green;
}
```

3、使用 outline 属性：将 p 的轮廓设置为“red”、“dotted”和“10px”。

```css
p {
  outline: red dotted 10px;
}
```

### CSS 文本

> [CSS 文本 (w3schools.cn)](https://www.w3schools.cn/css/css_text.asp)

1、将页面的文本颜色设置为“红色”，将 < h1 > 的文本颜色设置为“蓝色”。

```css
body {
  color: red;
}

h1 {
  color: blue;
}
```

2、居中对齐 < h1 > 元素。

```css
h1 {
  text-align: center;
}
```

3、从链接中删除下划线。

```css
a {
	text-decoration: none;通常用于从链接上删除下划线：
}

< p ><a href="css_text.asp">CSS text tutorial</a></p>
```

4、将 < h1 > 中的文本设置为大写字母，将 < p > 中的文本设置为首字母大写。

```css
h1 {
  text-transform: uppercase;
}
p {
  text-transform: capitalize;
}
h2 {
  text-transform: lowercase;
}
```

5、将 < p > 元素的第一行缩进 20px。

```css
p {
  text-indent: 20px;
}
```

### CSS 字体

1、将页面的字体系列设置为“Courier New”，将 < h1 > 的字体系列设置为“Verdana”。

```css
body {
  font-family: "Courier New";
}

h1 {
  font-family: Verdana;
}
```

2、将 < p > 元素显示为斜体文本。

```css
p {
  font-style: italic;
}
```

3、将页面的字体大小设置为 "20px"，将 < h1 > 的字体大小设置为 "3em"。

```css
body {
  font-size: 20px;
}

h1 {
  font-size: 3em;
}
```

4、将 < p > 元素显示为“粗体”文本。

```css
p {
  font-weight: bold;
}
```

5、使用字体属性：将 < p > 设置为 "italic"、"20px" 和 "Verdana"。

```css
p {
  font: italic 20px Verdana;
}
```

### CSS 链接

1、将链接的颜色设置为“绿色”。

```css
a {
  color: green;
}

< p ><a href="https://www.w3schools.com">W3Schools.com</a></p>
```

2、将未访问链接的颜色设置为“红色”，将已访问链接的颜色设置为“蓝色”。

```css
/* unvisited link */
a:link {
  color: red;
}

/* visited link */
a:visited {
  color: blue;
}

/* mouse over link */
a:hover {
  color: black;
}

/* selected link */
a:active {
  color: green;
}

< p ><a href="https://www.w3schools.com">W3Schools.com</a></p>
```

3、删除已访问和未访问链接的下划线，并为悬停和活动链接状态指定 "underline"。

```css
/* unvisited link */
a:link {
  text-decoration: none;
}

/* visited link */
a:visited {
  text-decoration: none;
}

/* mouse over link */
a:hover {
  text-decoration: underline;
}

/* selected link */
a:active {
  text-decoration: underline;
}
```

4、将已访问和未访问链接的背景颜色设置为 "lightblue"，将悬停和活动链接状态的背景颜色设置为 "yellow"。

```css
/* unvisited link */
a:link {
  background-color: lightblue;
}

/* visited link */
a:visited {
  background-color: lightblue;
}

/* mouse over link */
a:hover {
  background-color: yellow;
}

/* selected link */
a:active {
  background-color: yellow;
}
```

### CSS 列表

1、将无序列表的列表样式设置为“方形”，将列表样式设置为 有序列表到“大写罗马”。

```css
ul {
  list-style-type: square;
}

ol {
  list-style-type: upper-roman;
}
```

2、将图像“sqpurple.gif”设置为无序列表的列表项标记。

```css
ul {
  list-style-image: url('sqpurple.gif');
}
```

3、使用 list-style 属性：将无序列表标记设置为 "img_marker.png"，备用样式为 "circle"，并在内容流中显示标记。

```css
ul {
  list-style: circle inside url('img_marker.png');
}
```

4、从列表项中删除项目符号/标记。

```css
ul {
  list-style-type: none;
}
```

### CSS 表格

1、将表格、th 和 td 元素的边框设置为“2px solid green”。

```css
table, th, td {
  border: 2px solid green;
}
```

2、将表格边框折叠成一个边框。

```css
table {
  border-collapse: collapse;
}
table, td, th {
  border: 1px solid black;
}
```

3、将表格的宽度设置为“100%”。

```css
table {
  width: 100%;
}
table, td, th {
  border: 1px solid black;
}
```

4、将 <td> 元素中的文本对齐方式设置为 "right"。

```css
table, td, th {
  border: 1px solid black;
}
td {
  text-align: right;
}
```

5、将 <th> 元素中的填充设置为 "15px"。

```css
table, td, th {
  border: 1px solid black;
}
th {
  padding: 15px;
}
```

6、将 <th> 元素的背景颜色设置为 "lightblue"。

```css
table, td, th {
  border: 1px solid black;
}
th {
  background-color: lightblue;
}
```

### CSS 显示和可见

> [CSS 布局 - display 属性 (w3schools.cn)](https://www.w3schools.cn/css/css_display_visibility.asp)

1、隐藏 < h1 > 元素。 它仍应占用与以前相同的空间。

```css
h1 {
  visibility: hidden;
}
```

2、隐藏 < h1 > 元素。 它应该**不**占用任何空间。

```css
h1 {
  display: none;
}
```

3、将列表项显示为内联元素。

```css
li {
  display: inline;
}
```

4、将 <strong> 元素显示为块元素。

```css
strong {
  display:block;
}
```

### CSS 定位

1、相对于窗口/框架边缘，将 < h1 > 元素定位为始终距顶部 50 像素，距右侧 50 像素。

```css
h1 {
  position: fixed;
  top: 50px;
  right: 50px;
  color: red;
}
```

2、将 < h1 > 元素相对于其正常位置向左 20 像素，向下 30 像素。

```css
h1 {
  position: relative;
  top: 30px;
  left: -20px;
  color: red;
}
```

3、相对于 HTML 页面，将 < h1 > 元素定位在距离左侧 50 像素和距离顶部 100 像素的位置。

```css
h1 {
  position: absolute;
  top: 100px;
  left: 50px;
  color: red;
}
```

4、将 <img> 元素放在文本后面。

```css
img {
  position: absolute;
  left: 0px;
  top: 0px;
  z-index: -1;
}
```

5、将具有“topleft”类的元素定位在距其容器左侧 30px 和距顶部 15px 的位置。

```html
<!DOCTYPE html>
<html>
<head>
<style>
.container {
  position: relative;
}

.topleft {
  position: absolute;
  left: 30px;
  top: 15px;
  font-size: 18px;
}

img {
  width: 100%;
  height: auto;
  opacity: 0.3;
}
</style>
</head>
<body>

<div class="container">
  <img src="img_5terre.jpg" alt="Cinque Terre" width="1000" height="300">
  <div class="topleft">Top Left</div>
</div>

</body>
</html>
```

### CSS 溢出

overflow 属性可设置以下值：

- visible - 默认。溢出没有被剪裁。内容在元素框外渲染
- hidden - 溢出被剪裁，其余内容将不可见
- scroll - 溢出被剪裁，同时添加滚动条以查看其余内容
- auto - 与 scroll 类似，但仅在必要时添加滚动条

1、将滚动条添加到 < div > 元素。

```css
div {
  background-color: #eee;
  width: 200px;
  height: 70px;
  border: 1px dotted black;
}
```

2、指定 < div > 元素中溢出的文本不可见，即使滚动也不可见。

```css
div {
  background-color: lightblue;
  width: 200px;
  height: 200px;
  overflow: hidden;
}
```

3、向 < div > 添加水平滚动条。

```css
div {
  background-color: #eee;
  width: 150px;
  height: 70px;
  border: 1px dotted black;
  white-space: nowrap;
  overflow-x: scroll;
}
```

### CSS 垂直和水平对齐

1、使用边距将 < div > 元素居中对齐。

```css
div {
  margin-left: auto;
  margin-right: auto;
  width: 300px;
  background-color: #b0e0e6;
}
```

2、使用绝对定位将 < div > 元素一直定位到右侧。

```css
div {
  position: absolute;
  right: 0px;
  width: 300px;
  background-color: #b0e0e6;
}
```

### CSS 组合器

> CSS 中有四种不同的组合器：
>
> - 后代选择器 (空格)
> - 子选择器 (>)
> - 相邻兄弟选择器 (+)
> - 通用兄弟选择器 (~)

1、将作为 < div > 元素的后代的所有 < p > 元素的颜色更改为“红色”。

```css
div p {
  color: red;
}
```

2、将作为 < div > 元素的直接子元素的所有 < p > 元素的颜色更改为“红色”。

```css
div > p {
  color: red;
}
```

3、将 < p > 元素的颜色更改为“红色”，这些元素是 <div> 元素的相邻（紧随其后）兄弟。

```css
div + p{
	color:red;
}
```

4、将作为 < div > 元素的兄弟元素的 < p > 元素的颜色更改为“红色”。

```css
div ~ p {
  color: red;
}
```

### CSS 伪类

1、将已访问和未访问链接的背景颜色设置为 "lightblue"，将悬停和活动链接状态的背景颜色设置为 "yellow"。

```css
/* unvisited link */
a {
  background-color: lightblue;
}

/* visited link */
a {
  background-color: lightblue;
}

/* mouse over link */
a {
  background-color: yellow;
}

/* selected link */
a {
  background-color: yellow;
}
```

2、当用户将鼠标悬停在具有“highlight”类的 p 元素上时，将背景颜色更改为 "lightblue"。

```css
p.highlight:hover{
	background-color:lightblue;
}
```

3、将作为任何元素的第一个子元素的 < p > 元素的背景颜色设置为 "lightblue"。

```css
p:first-child {
  background-color: lightblue;
}
```

4、将处于焦点（单击或活动）的 < input > 元素的背景颜色设置为 "lightblue"。

```css
input:focus {
  background-color: lightblue;
}
```

### CSS 伪元素

CSS 伪元素用于设置元素指定部分的样式。比如：

- 设置元素的首字母、首行的样式
- 在元素的内容之前或之后插入内容

1、将 < p > 元素的第一行的文本颜色设置为红色。

```css
p::first-line {
  color: red;
}
```

2、对于 < p > 元素的第一个字母，将文本颜色设置为 "red"，将文本大小设置为 "xx-large"。

```css
p::first-letter {
  color: red;
  font-size: xx-large;
}
```

3、使用 ::before 和 ::after 伪元素在 < p > 元素之前和之后插入图像 "smiley.gif"。

```css
p::before{
  content: url(smiley.gif);
}
p::after{
  content: url(smiley.gif);
}
```

### CSS 透明度

1、将 < img > 元素的透明度/不透明度设置为 "0.4"。

```css
img {
  opacity: 0.4;
}
```

2、当用户将鼠标指针悬停在 < img > 元素上时，移除它的透明度/不透明度。

```css
img {
  opacity: 0.4;
}
img:hover {
  opacity: 1.0;
}
```

### CSS 属性选择器

1、对于具有 "target" 属性的元素，将背景颜色设置为 "lightblue"。

```css
a[target] {
  background-color: lightblue;
}

<a href="http://www.disney.com" target="_blank">disney.com</a>
<a href="http://www.wikipedia.org" target="_top">wikipedia.org</a>
```

2、对于具有以下属性的元素，将背景颜色设置为 "lightblue" : target="_blank"

```css
a[target="_blank"] {
  background-color: lightblue;
}
<a href="http://www.disney.com" target="_blank">disney.com</a>
<a href="http://www.wikipedia.org" target="_top">wikipedia.org</a>
```

3、在具有 "title" 属性且包含单词 "red" 的元素周围设置一个颜色为 "red" 的边框。

```css
[title~="red"] {
  border: 5px solid red;
}

<img src="klematis_small.jpg" title="two red flowers" width="107" height="90">
<img src="klematis2_small.jpg" title="purple flower" width="107" height="80">
<img src="klematis3_small.jpg" title="red flower" width="116" height="90">
<img src="klematis4_small.jpg" title="two white flowers" width="120" height="90">
```

4、在具有以 "red" 开头的 "title" 属性的元素周围设置颜色为 "red" 的边框。

```css
[title^="red"] {
  border: 5px solid red;
}
<img src="klematis_small.jpg" title="two red flowers" width="107" height="90">
<img src="klematis2_small.jpg" title="purple flower" width="107" height="80">
<img src="klematis3_small.jpg" title="red flower" width="116" height="90">
<img src="klematis4_small.jpg" title="two white flowers" width="120" height="90">
```

5、在具有 "title" 属性以单词 "flower" 结尾（不是花**s**）的元素周围设置一个颜色为 "red" 的边框。

```css
[title$="flower"] {
  border: 5px solid red;
}
<img src="klematis_small.jpg" title="two red flowers" width="107" height="90">
<img src="klematis2_small.jpg" title="purple flower" width="107" height="80">
<img src="klematis3_small.jpg" title="red flower" width="116" height="90">
<img src="klematis4_small.jpg" title="two white flowers" width="120" height="90">
```

6、设置一个颜色为 "red" 的边框，围绕具有包含值 "flow" 的 "title" 属性的元素。

```css
[title*="flow"] {
  border: 5px solid red;
}
<img src="klematis_small.jpg" title="two red flowers" width="107" height="90">
<img src="klematis2_small.jpg" title="purple flower" width="107" height="80">
<img src="klematis3_small.jpg" title="red flower" width="116" height="90">
<img src="klematis4_small.jpg" title="two white flowers" width="120" height="90">
```

### CSS 圆角

1、给 <div> 元素圆角（使用速记属性和值 "25px"）。

```css
div {
  border-radius: 25px;
  background: #73AD21;
  padding: 20px; 
  width: 200px;  
}
```

2、在左下角给 <div> 元素一个圆角（25px 半径

```css
div {
  border-bottom-left-radius: 25px;
  background: #73AD21;
  padding: 20px; 
  width: 200px;  
}
```

### CSS 边框图像

1、使用图像 "border.png" 给 < div > 元素一个图像边框。 将图像切成 30px 并重复。

```css
div { 
  border: 10px solid transparent;
  border-image: url(border.png) 30 round;
}
```

2、使用图像 "border.png" 给 < div > 元素一个图像边框。 将图像切成 30 像素并拉伸。

```css
div { 
  border: 10px solid transparent;
  border-image: url(border.png) 30 stretch;
}
```

### CSS 多重背景

1、将第二个背景图像 ("img_flwr.gif") 添加到 < body > 元素。 确保 "img_flwr.gif" 显示在当前背景图像的顶部。

```css
body {
  background-image: url(img_flwr.gif), url(paper.gif);
}
```

2、将背景图片的大小改为：宽100px，高80px。

```css
body {
  background: url(img_flwr.gif);
  background-size: 100px 80px;
  background-repeat: no-repeat;
}
```

3、更改背景图像的大小，使其始终适合整个页面。

```css
html { 
  background: url(img_flower.jpg) no-repeat center center fixed;
  background-size: cover;
}

body { 
  color: white; 
}
```

4、指定背景图像位置应从内容框的左上角开始。

```css
div { 
  border: 10px solid black;
  padding: 35px;
  background: url(img_flwr.gif);
  background-repeat: no-repeat;
  background-origin: content-box;
}
```

5、指定背景的 "painting area" 应位于填充的外边缘。

```css
div { 
  border: 10px dotted black;
  padding: 35px;
  background: lightblue;
  background-clip: padding-box;
}
```

### CSS 颜色

1、通过使用 RGBA 颜色而不是 RGB，将 < h1 > 元素的背景颜色的不透明度设置为 "0.3"。

```css
h1 {
   background-color: rgb(0,255,0);
}
->
h1 {
  background-color: rgba(0,255,0,0.3);
}
```

2、将以下 **HSL** 颜色设置为 < h1 > 元素的背景：将**色相**设置为红色 (0)，将**饱和度**设置为 100%，将**亮度**设置为 50%。

```css
h1 {
  background-color: hsl(0,100%,50%);
}
```

3、通过使用 HSLA 颜色而不是 HSL 将 < h1 > 元素的背景颜色的不透明度设置为 "0.3"。

```css
h1 {
  background-color: hsla(0,100%,50%,0.3);
}
```

4、将 < h1 > 元素的透明度/不透明度设置为 "0.4"。

```css
h1 {
  background-color: red;
  opacity: 0.4;
}
```

### CSS 渐变

1、为 < div > 元素设置一个线性渐变背景，从上到下，从 "white" 过渡到 "green"。

```css
div {
  background-image: linear-gradient(white, green);
}
```

2、为 < div > 元素设置一个线性渐变背景，从左上角到右下角，从 "white" 过渡到 "green"。

```css
div {
  background-image: linear-gradient(to bottom right, white, green);
}
```

3、为 < div > 元素设置线性渐变背景，以 70 度角，从 "white" 过渡到 "green"。

```css
div {
  background-image: linear-gradient(70deg, white, green);
}
```

4、为 < div > 元素设置一个线性渐变背景，从上到下，从 "white" 过渡到 "red" 到 "blue" 到 "green"。

```css
div {
  background-image: linear-gradient(white, red, blue, green);
}
```

5、为 < div > 元素设置一个线性渐变背景，从上到下，从 "rgba(0,255,0,0.2)" 过渡到 "rgba(0,255,0,1)"。

```css
div {
  background-image: linear-gradient(rgba(0,255,0,0.2), rgba(0,255,0,1));
}
```

6、为 < div > 元素设置径向渐变背景，从 "white" 过渡到 "green"。

```css
div {
  background-image: radial-gradient(white, green);
}
```

7、为 < div > 元素设置径向渐变背景，圆形，从 "white" 过渡到 "green"。

```css
div {
  background-image: radial-gradient(circle, white, green);
}
```

### CSS 阴影效果

1、为 < h1 > 元素设置 "2px" 水平和 "2px" 垂直的文本阴影。

```css
h1 {
  text-shadow: 2px 2px;
}
```

2、将文字阴影的颜色改为"green"，并设置"5px"模糊半径。

```css
h1 {
  text-shadow: 2px 2px 5px green;
}
```

3、向 < h1 > 元素添加一个新阴影（不要删除当前阴影）：无水平或垂直阴影、10px 模糊和红色。

```css
h1 {
  text-shadow: 2px 2px 5px green, 0 0 10px red;
}
```

4、为 < div > 元素设置 "10px" 水平和 "10px" 垂直的框阴影。

```css
div {
  box-shadow: 10px 10px;
}

<div style="background-color: lightblue; width: 350px; padding: 15px;">
< h1 >This is a Heading</h1>
< p >This is a paragraph.</p>
< p >This is another paragraph.</p>
</div>
```

5、将框阴影的颜色更改为 "grey"，并设置 "5px" 模糊。

```css
div {
  box-shadow: 10px 10px 5px grey;
}
```

CSS 文本效果

1、指定 < p > 元素的溢出内容应使用省略号 (...)

```css
p {
  white-space: nowrap; 
  width: 200px; 
  border: 1px solid #000000;
  overflow: hidden;
  text-overflow: ellipsis;  //省略号
}
```

2、指定 < p > 元素中的文本应该换行，即使它需要在单词中间拆分。

```css
p {
  width: 150px; 
  border: 1px solid #000000;
  word-wrap: break-word;
}
```

3、指定 < p > 元素中的文本可以在任意两个字母之间中断。

```css
p {
  width: 150px; 
  border: 1px solid #000000;
  word-break: break-all;
}
```

### CSS Web字体

1、添加名称为 "sansation" 和 URL 为"sansation_light.woff" 的 Web 字体。

```css
@font-face {
  font-family: sansation;
  src: url(sansation_light.woff);
}

body {
  font-family: sansation;
}
```

2、为 "sansation" 字体的粗体字符添加另一个 @font-face 规则。 使用 URL "sansation_bold.woff"。

```css
@font-face {
  font-family: sansation;
  src: url(sansation_light.woff);
}

@font-face {
  font-family: sansation;
  src: url(sansation_bold.woff);
  font-weight: bold;
}

body {
  font-family: sansation;
}
```

### CSS 2D转换

1、使用 transform 属性，将 < div > 元素向右移动 100px，向下移动 200px。

```css
div {
  width: 100px;
  height: 100px;
  background-color: lightblue;
  border: 1px solid black;
  transform: translate(100px,200px);
}
```

2、使用 transform 属性，将 < div > 元素旋转 45 度。

```css
div {
  width: 100px;
  height: 100px;
  margin: 50px;
  background-color: lightblue;
  border: 1px solid black;
  transform: rotate(45deg);
}
```

3、使用 transform 属性，将 < div > 的大小更改为宽度的一半，但高度增加一倍。

```css
div {
  width: 100px;
  height: 100px;
  margin: 50px;
  background-color: lightblue;
  border: 1px solid black;
  transform: scale(0.5,2);
}
```

4、使用 transform 属性，将 < div > 元素沿 X 轴倾斜 20 度，沿 Y 轴倾斜 30 度。

```css
div {
  width: 100px;
  height: 100px;
  margin: 50px;
  background-color: lightblue;
  border: 1px solid black;
  transform: skew(20deg, 30deg);
}
```

### CSS 3D转换

1、使用 transform 属性，将 < div > 元素绕其 X 轴旋转 150 度。

```css
div {
  width: 100px;
  height: 100px;
  background-color: lightblue;
  border: 1px solid black;
  transform: rotateX(150deg);
}
```

2、使用 transform 属性，将 < div > 元素围绕其 Y 轴旋转 120 度。

```css
div {
  width: 100px;
  height: 100px;
  background-color: lightblue;
  border: 1px solid black;
  transform: rotateY(120deg);
}
```

3、使用 transform 属性，将 < div > 元素围绕其 Z 轴旋转 90 度。

```css
div {
  width: 100px;
  height: 100px;
  background-color: lightblue;
  border: 1px solid black;
  transform: rotateZ(90deg);
}
```

### CSS 过渡

> [CSS 代码测试 - W3schools 在线教程](https://www.w3schools.cn/css/exercise.asp?filename=exercise_css3_transitions1)

1、为 < div > 元素的宽度变化添加 2 秒的过渡效果。

```css
div {
  width: 100px;
  height: 100px;
  background: red;
  transition: width 2s;
}

div:hover {
  width: 300px;
}
```

2、指定 < div > 元素的过渡应具有 "ease-in-out" 速度曲线。

```css
div {
  width: 100px;
  height: 100px;
  background: red;
  transition: width 2s;
  transition-timing-function: ease-in-out;
}

div:hover {
  width: 300px;
}
```

3、指定 < div > 元素的转换在开始之前应该有 "0.5" 秒的延迟。

```css
div {
  width: 100px;
  height: 100px;
  background: red;
  transition: width 2s;
}

div:hover {
  width: 300px;
}
```

4、为背景添加 2 秒的过渡效果，并变换 < div > 元素的变化。

```css
div {
  width: 100px;
  height: 100px;
  background: red;
  transition: background 2s, transform 2s;
}

div:hover {
  background: blue;
  transform: rotate(180deg);
}
```

5、使用过渡速记属性，指定 < div > 元素的宽度更改应具有：
"2" second duration, "ease-in-out" speed curve, and a "0.5" second delay before starting.

```css
div {
  width: 100px;
  height: 100px;
  background: red;
  transition: width 2s ease-in-out 0.5s;
}

div:hover {
  width: 400px;
}
```

### CSS 动画

> [CSS3 动画 (w3schools.cn)](https://www.w3schools.cn/css/css3_animations.asp)

1、为 < div > 元素添加一个 2 秒的动画，将颜色从红色变为蓝色。 调用动画 “示例”

```css
div {
  width: 100px;
  height: 100px;
  background-color: red;
  animation-name: example;
  animation-duration: 2s;
}

@keyframes example {
  from {background-color: red;}
  to {background-color: blue;}
}
```

2、将以下 5 个步骤添加到动画“示例”中 （使用 0%、25%、50%、 75% 和 100%）：

1. 0% - Set background color to "red", left position to "0px", top position to: "0px"
2. 25% - Set background color to "blue", left position to "0px", top position to: "200px"
3. 50% - Set background color to "green", left position to "200px", top position to: "200px"
4. 75% - Set background color to "yellow", left position to "200px", top position to: "0px"
5. 100% - Set background color to "red", left position to "0px", top position to: "0px"

```css
div {
  width: 100px;
  height: 100px;
  position: relative;
  background-color: red;
  animation-name: example;
  animation-duration: 4s;
}

@keyframes example {
  0%   {background-color: red; left:0px; top:0px;}
  25%  {background-color: blue; left:0px; top:200px;}
  50%  {background-color: green; left:200px; top:200px;}
  75%  {background-color: yellow; left:200px; top:0px;}
  100% {background-color: red; left:0px; top:0px;}
}
```

3、指定 < div > 元素的动画在开始之前应该有 "1" 秒的延迟。

```css
div {
  width: 100px;
  height: 100px;
  position: relative;
  background-color: red;
  animation-name: example;
  animation-duration: 2s;
}

@keyframes example {
  0%   {background-color: red; left:0px;}
  50%  {background-color: yellow; left:200px;}
  100% {background-color: red; left:0px;}
}
```

4、指定 < div > 元素的动画应该永远继续循环。

```css
div {
  width: 100px;
  height: 100px;
  position: relative;
  background-color: red;
  animation-name: example;
  animation-duration: 2s;
  animation-iteration-count: infinite;  // 重要
}

@keyframes example {
  0%   {background-color: red; left:0px;}
  50%  {background-color: yellow; left:200px;}
  100% {background-color: red; left:0px;}
}
```

5、指定 < div > 元素的动画应在向前和向后运行之间交替。

```css
div {
  width: 100px;
  height: 100px;
  position: relative;
  background-color: red;
  animation-name: example;
  animation-duration: 4s;
  animation-iteration-count: infinite;  
}

@keyframes example {
  0%   {background-color: red; left:0px; top:0px;}
  25%  {background-color: blue; left:0px; top:200px;}
  50%  {background-color: green; left:200px; top:200px;}
  75%  {background-color: yellow; left:200px; top:0px;}
  100% {background-color: red; left:0px; top:0px;}
}
```

6、指定 < div > 元素的动画应具有 "ease-in-out" 速度曲线。

```css
div {
  width: 100px;
  height: 100px;
  position: relative;
  background-color: red;
  animation-name: example;
  animation-duration: 4s;
  animation-timing-function: ease-in-out;
}

@keyframes example {
  0%   {background-color: red; left:0px;}
  50%  {background-color: yellow; left:200px;}
  100% {background-color: red; left:0px;}
}
```

