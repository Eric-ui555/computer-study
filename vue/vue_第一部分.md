## 一、vue基础

### 1.1 webpack

概念：webpack是前端项目工程化的具体解决方案

主要功能：提供了友好的前端模块化开发支持，以及代码压缩混淆、处理浏览器端JavaScript的兼容性、性能优化等强大的功能

+ 新建项目空白目录，并运行 `npm init –y` 命令，初始化包管理配置文件 package.json，
+ 新建 src 源代码目录，新建 src -> index.html 首页和 src -> index.js 脚本文件

+ 初始化首页基本的结构
+ 运行 npm install jquery –S 命令，安装 jQuery
+ 通过 ES6 模块化的方式导入 jQuery，实现列表隔行变色效果

> 1、在项目中安装webpack

```
在终端运行如下命令，安装webpack相关的两个包
npm install webpack@5.42.1 webpack-cli@4.7.2 -D

-S是--save的简写
-D是--save-dev的简写
```

> 2、在项目中配置webpack

+ 在项目根目录中，创建名为webpack.config.js的webpack配置文件，并初始化如下的配置

```js
module.exports ={
    // mode 用来指定构建模式，可选值有，development和production
    mode: "development"
}
```

+ 在package.json的scripts节点下，新增dev脚本如下

![image-20220811180228687](E:\savefile\typora\image\image-20220811180228687.png)

+ 在终端运行`npm run dev`命令，启动webpack进行项目的打包构建

> 3、 mode 的可选值

mode 节点的可选值有两个，分别是：

+ **development**：开发环境
  + 不会对打包生成的文件进行代码压缩和性能优化
  + **打包速度快**，适合在**开发阶段**使用

+ **production**：生产环境
  + 会对打包生成的文件进行代码压缩和性能优化
  + **打包速度很慢**，仅适合在**项目发布阶段**使用

### 1.2 HTML

速查列表[HTML 速查列表 | 菜鸟教程 (runoob.com)](https://www.runoob.com/html/html-quicklist.html)

#### 1.2.1元素

```html
<head> 定义了文档的信息
<title> 标签定义了不同文档的标题
<base> 定义了页面链接标签的默认链接地址
<link> 标签定义了文档与外部资源之间的关系，通常用于链接到样式表
<meta> 定义了HTML文档的元数据
<style> 标签定义了HTML文档的样式文件引用地址
<script>标签用于加载脚本文件
```

+ 文本格式化

```html
<b>: 定义粗体文字
<em>: 定义着重文字
<i>: 定义斜体字
<small>: 定义小号字
<strong>: 定义加重语气
<sub>: 定义下标字
<sup>: 定义上标字
<ins>: 定义插入字
<del>: 定义删除字
```

+ 图像

```html
<!-- 图片 -->
<img src="../img/woman.jpg" width="200" height="400">
<!-- 音频 -->
<audio src="../img/郑智化 - 游戏人间.mp3" controls></audio>
<!-- 视频 -->
<video src="../img/薛之谦-迟迟(标清).mp4" controls width="400" height="400"></video>
```

+ 超链接

```html
<a href="https://www.baidu.com" target="_blank">百度一下，你就知道</a>
```

+ 列表

```html
<!-- 有序列表 -->
<!-- type设置列表标签 -->
<ol>
    <li>coffee</li>
    <li>tea</li>
</ol>
<br>
<!-- 无序列表 -->
<ul>
	<li>coffee</li>	
    <li>tea</li>
</ul>
```

+ 表格

```html
<!-- 表格 -->
<!-----------------------------------------
table:
    border:规定表格边框的宽度
    cellspacing: 规定单元格之间的留白
tr: 定义行
	align: 定义表格行的内容对齐方式
th: 定义表头单元格
td: 定义单元格
	rowspan:规定单元格可横跨的行数
	colpan:规定单元格可横跨的列数
----------------------------------------->
<table border="1" cellspacing="0" width="500">
    <tr height="50">
        <th>编号</th>
        <th>姓名</th>
        <th>职位</th>
        <th>地址</th>
    </tr>
    <tr align="center" height="50">
        <td>01</td>
        <td>张三</td>
        <td colspan="2">老板</td>
        <!-- <td>北京</td> -->
    </tr>
</table>
```

+ 布局

```html
<div> 定义一个HTML文档中的一个区域部分，经常与CSS一起使用，用来布局网络</div>
<span> 用于组合行内元素 </span>
```

+ 表单

```html
<!-------------------------------------------------
创建表单：<form> 标签
    action:制定和表单暑假提交的url
    	* 表单项数据要想被提交，则必须指定其name属性
    method:指定表单提交的方式
    	get:默认值
    		* 请求参数会拼接在URL后面
    		* url的长度有限制 4KB
    	post
    		* 请求参数会在http请求协议的请求体中
    		* 请求参数无限制的
------------------------------------------------->
<input>: 表单项，通过type属性控制输入形式
<select>: 定义下拉列表，<option>定义列表项
<textarea>: 文本域
<!-----------------------------------------------
输入类型 type
文本域：<input type="text"> 
密码字段：<input type="password">
单选按钮：<input type="radio">
复选框：<input type="checkbox">
提交按钮：<input type="submit"> 
文件上传按钮：<input type="file"> 
重置按钮：<input type="reset"> 
点击按钮：<input type="button"> 
------------------------------------------------>
    <from action="#"> 
            姓名：<input type="text"><br>
            密码：<input type="password"><br>
            性别：
                <input type="radio" name="gender" value="1">男
                <input type="radio" name="gender" value="2">女<br>
            爱好：
                <input type="checkbox" name="hobby" value="1">电影
                <input type="checkbox" name="hobby" value="2">游戏
                <input type="checkbox" name="hobby" value="3">睡觉
                <br><hr><br>
            上传头像: 
                <input type="file">
            <br><hr><br>
            个人描述：
                <textarea></textarea>
            <br><hr><br>
            <input type="reset" name="reset">
            <input type="submit" name="submit">
        </from>
```

+ 框架：在同一个浏览器窗口中显示不止一个页面

```html
<!-- iframe语法: -->
<iframe src="URL"></iframe>
<!-- height 和 width 属性用来定义iframe标签的高度与宽度-->
<!-- frameborder 属性用于定义iframe表示是否显示边框。-->
```

#### 1.2.2 属性

+ class: 为html元素定义一个或多个类名（classname）(类名从样式文件引入)
+ id: 定义元素的唯一id
+ style:  规定元素的行内样式（inline style）
+ title: 描述了元素的额外信息 (作为工具条使用)

### 1.3 CSS

#### 1.3.1 CSS导入方式

CSS (Cascading Style Sheets) 用于渲染HTML元素标签的样式

CSS 可以通过以下方式添加到HTML中:

- 内联样式：在HTML元素中使用"style"**属性**

```html
<div style="color:red">hello,css</div>
```

- 内部样式表：在HTML文档头部 <head> 区域使用<style> **元素** 来包含CSS

```html
<style>
    div{
        color: blue;
    }
</style>
```

- 外部样式表：使用外部 CSS **文件**

```html
<link href="../css/1.css" rel="stylesheet">

css文件
p{
    color: green;
}
```

#### 1.3.2 CSS 选择器

+ 元素选择器

```html
元素名称{color:red;}
---------------------------
div{color:red;}
```

+ id选择器

```html
#id属性值{color:red;}
---------------------------
#name{color:red;}

<div id="name">hello css2</div>
```

+ 类选择器class

```html
.class属性值{color:red;}
---------------------------
.cls{color:red;}

<div class="cls">hello css3</div>
```

#### 1.3.3 CSS属性

[如何添加 CSS (w3school.com.cn)](https://www.w3school.com.cn/css/css_shiyong.asp)

### 1.4 JavaScript

JavaScript是一门跨平台、面向对象的脚本语言，来控制网页行为，是网页能够交互

#### 1.4.1 JavaScript引入方式

+ 内部脚本

```javascript
<script>alert("hello")</script> 
```

+ 外部脚本

```javascript
<script src="../js/demo.js"></script>

demo.js
alert("helloworld")
```

#### 1.4.2 JavaScript基础语法

+ 书写语法

  +  区分大小写

  + 每行结尾的分号可有可无

  + 注释

    + 单行注释：//注释内容和
    + 多行注释：/* 注释内容 */

  + 大括号表示代码块

    ```
    if(count == 3){
    	alert(count);
    } 
    ```

+ 输出语句

  + 使用window.alert()写入井号狂

  + 使用document.write()写入HTML输出

  + 使用console.log()写入浏览器控制台

    ```
    window.alert("hello,js");
    document.write("hello,js");
    console.log("hello,js")
    ```

+ 变量

  + var关键字来声明变量，全局变量，可以重复定义
  + javascript是一门弱类型语言，变量可以存放不同类型的值
  + 变量名需要遵循的规则
    + 组成字符可以是任何字母、数字、下划线或美元符号$
    + 数字不能开头
    + 建议使用驼峰命名
  + let只在当前代码块中有效，且不允许重复定义
  + const声明一个只读的常量，一旦声明就不能改变

+ 数据类型

  + 原始类型

    + number：数字（整数、小数、NaN(Not a Number)）
    + string：字符、字符串、单双引号皆可
    + boolean：布尔
    + null：对象为空
    + undefined：当声明的变量未初始化时，该变量的默认值时undefined

  + 引用类型

  + 使用**typeof运算符**可以获取数据类型

    ```
    alert(typeof age)
    ```

+ 运算符

  + ```html
    ==：会进行类型转换
    1、判断类型是否一样，如果不一样，则进行类型转换
    2、再去比较其值
    ---------------------------------------------
    ===:全等于，不会进行类型转换
    1、判断类型是否一样，如果不一样，则直接返回false
    2、再去比较其值
    ---------------------------------------------
    类型转换：
    * 其他类型转为number
    	1、string: 按照字符串的字面值，转为数据，如果字面值不是数字，则转为NaN，一般使用parseInt
    	2、boolean: true为1，false为0
    * 其他类型转为boolean
    	1、number: 0和NaN转为false,其他转为true
    	2、string: 空字符串转为false，其他的字符串转为true
    	3、null: 转为false
    	4、undefined: 转为false
    ```

+ 流程控制语句

  + 和java一样

+ 函数

  + function关键词来定义函数

    ```html
    function functionName(参数1, 参数2){
    	要执行的代码
    }
    ---------------------------------------
    var functionName = function(参数1, 参数2){
    	要执行的代码
    }
    ---------------------------------------
    形式参数不需要类型
    返回值也不需要定义类型，可以在函数内部直接使用return返回即可
    ```

#### 1.4.3 JavaScript常用对象

1、Array

+ JavaScript Array对象用于定义数组


```
---定义---
var 变量名 = new Array(元素列表)  //方式一
var 变量名 = [元素列表]  //方式二
---访问---
arr[索引] = 值
```

+ 特点：JavaScript数组相当于java中的集合，**变长变类型**

+ 方法
  + push：添加元素
  + splice：删除元素

2、String

```
---定义---
var 变量名 = new String(s)  //方式一
var 变量名 = s  //方式二
---属性---
length: 字符串的长度
---方法---
charAt(): 返回在指定位置的字符
indexOf(): 检索字符串
```

3、自定义对象

```
var 对象名称 = {
	属性名称1: 属性值1,
	属性名称1: 属性值1,
	...
	函数名称: function(形参列表){}
	...
}
```

#### 1.4.4 BOM

+ Browser Object Model 浏览器对象模型
+ JavaScript 将浏览器的各个组成部分封装为对象
+ 组成：
+ Windows：浏览器窗口对象

  + 获取：直接使用window，其中window.可省略

```js
alert(): 显示带有一段消息和一个确认按钮的警告框
confirm(): 显示带有一段消息以及确认按钮和取消按钮的对话框
---------定时器---------------
setInterval(function, 毫秒值): 在一定的时间间隔后执行一个function, 循环执行
setTimeout(function, 毫秒值): 在一定的时间间隔后执行一个function, 只执行一次
```

+ Navigator：浏览器对象
+ Screen：屏幕对象
+ History：历史记录对象

  + 获取：

```js
window.history.方法();
history.方法();
-------------------------
back(): 加载history列表中的一个url
forward():加载history列表中的下一个url
```

+ Location：地址栏对象

  

```js
window.location.方法();
location.方法();
-------------------------
href: 设置或返回完整的URL 
```

#### 1.4.5 DOM

+ Document Object Model 文档对象模型
+ 将标记语言的各个组成部分封装为对象
  + Document：整个文档对象
  + Element：元素对象
  + Attribute：属性对象
  + Text：文本对象
  + Comment：注释对象 

1、获取Element

+ Element：元素对象
+ 获取：使用Document对象的方法来获取
  + getElementById：根据id属性值获取，返回一个Element对象
  + getElementsByTagName：根据标签名称获取，返回一个Element对象数组
  + getElementsByName：根据name属性值获取，返回一个Element对象数组
  + getElementsByClassName：根据class属性值获取，返回一个Element对象数组

#### 1.4.6 事件监听???

事件：HTML事件是发生在HTML元素上的“事情”，比如：

+ 按钮被点击
+ 鼠标移动到元素之上
+ 按下键盘按键

事件监听：JavaScript可以在事件被侦测到时执行代码

事件绑定有两种方式：

+ 方式一：通过HTML标签中的事件属性进行绑定

```js
<input type="button" onclick='on()'>
function on(){
	alert("我被点击了");
}
```

+ 方式二：通过DOM元素属性绑定

```js
<input type="button" id="btn">

document.getElementById("btn").onclick = function(){
    alert("我被点击了")
}
```

#### 1.4.7 表单验证

#### 1.4.8 正则表达式

### 1.5 vue的指令与过滤器

#### 1.5.1 指令

指令是vue为开发者提供的**模板语法**，用于辅助开发者渲染页面的基本结构

按照用途划分

+ 内容渲染指令
+ 属性绑定指令
+ 事件绑定指令
+ 双向绑定指令
+ 条件渲染指令
+ 列表渲染指令

#### 1.5.2 内容渲染指令

> 内容渲染指令用来赋值开发者渲染DOM元素的文本内容
>

+ **v-text**：会覆盖元素内部原有的内容；

+ **{{  }}**插值表达式：在实际开发中用的最多，只是内容的占位符，不会覆盖原有的内容；

+ **v-html**：可以把带有标签的字符串，渲染成真正的HTML内容。

```vue
<div id="app">
	<p v-text = "username"> </p>
    <p>性别：{{gender}}</p>
    <p v-html = "info"></p>
</div>
info:'<h4 style="color:red; font-weight:bold;">欢迎大家来学习</h4>'
```

#### 1.5.3 属性绑定指令

> 注意：差值表达式{{ }}只能用在元素的**内容节点**中，不能用在元素的属性节点中
>

+ v-bind：为元素属性动态绑定属性值

+ 在 vue 中，可以使用 `v-bind` 指令，为元素的属性动态绑定值；

+ v-bind简写是英文的`：`

在使用 v-bind 属性绑定期间，如果绑定内容需要进行动态拼接，则字符串外面应该包裹单引号，例如：

```vue
<div :title="'box'+ index">这是一个div</div>
```

#### 1.5.4 事件绑定指令

1、**v-on：绑定事件，可简写为@**

+ methods的作用：定义事件的处理函数

2、语法格式

```html
<button @click="add"></button>

methods:{
	add(){
	 	//如果在方法中要修改data中的数据，可以通过this访问到
		this.count += 1;
	}
}
```

+ 在绑定事件处理函数的时候，可以使用 `()` 来传参

3、$event的应用场景：如果默认的事件对象e被覆盖了，则可以手动传递一个

```vue
<button @click="add(3, $event)"></button>

methods:{
	add(n, e){
	 	//如果在方法中要修改data中的数据，可以通过this访问到
		this.count += n;
	}
}
```

4、事件修饰符

+ 在事件处理函数中调用 `event.preventDefault()` 或 `event.stopPropagation()` 是非常常见的需求。
+ vue提供了事件修饰符的概念，来辅助程序员更方便的对事件的出发进行控制

| 事件修饰符 | 说明                                                  |
| ---------- | ----------------------------------------------------- |
| .prevent   | 阻止默认行为(例如，组织a链接的跳转、组织表单的提交等) |
| .stop      | 阻止事件冒泡                                          |
| .capture   | 以捕获模式触发当前的事件处理函数                      |
| .once      | 绑定的事件只触发1次                                   |
| .self      | 只有在event.target是当前元素自身时触发事件处理函数    |

5、按键修饰符

```html
<input type="text" @keyup.esc="clearInput">

clearInput(e) {
    console.info("触发了clearInput方法");
    e.target.value="";
}
```

#### **1.5.6** 双向数据绑定指令

+ 在不操作DOM的情况下，快速获取表单数据 
+ v-model
+ v-model指令的专用修饰符

| 修饰符  | 作用                           | 实例                          |
| ------- | ------------------------------ | ----------------------------- |
| .number | 自动将用户的输入值转为数值类型 | <input v-model.number="age"/> |
| .trim   | 自动过滤用户输入的首位空白字符 | <input v-model.trim="msg"/>   |
| .lazy   | 在“change”时而非“input”时更新  | <input v-model.lazy="msg"/>   |

```html
<input type="text" v-model.number="h1">+<input type="text" v-model.number="h2">=<span>{{n1+n2}}</span>
```

#### 1.5.7 条件渲染指令

条件渲染指令用来复制开发者按需控制DOM的显示与隐藏

+ v-if
+ v-show

```html
<p v-if="flag">这是v-if渲染的指令</p>
<p v-show="flag">这是v-show渲染的指令</p>

flag:true
```

1、v-show的原理是：动态为元素添加或移除 `display: none`样式来实现元素的显示和隐藏

+ 如果要频繁的切换元素的显示状态，用v-show性能会更好

2、v-if的原理是：每次动态创建或移除元素，实现元素的显示和隐藏

+ 如果刚进入页面的时候，某些元素不需要被展示，而且后期这个元素很可能也不需要被显示出来，此时v-if性能更好

v-else必须和v-if配合使用

```html
<div v-if="score === 'A'">优秀</div>
<div v-else-if="score === 'B'">良好</div>
<div v-else-if="score === 'C'">及格</div>
<div v-else>差</div>
```

#### 1.5.8 列表渲染指令

列表渲染指令v-for，用来辅助开发者基于一个数组来循环渲染一个列表结构。v-for指令需要使用item in items形式的特殊语法。其中：

+ items是待循环的数组
+ item是被循环的每一项

```html
<ul>
	<li v-for="item in list">姓名是：{{item.name}}</li>
</ul>
```

v-for指令还支持一个可选的第二个参数，即当前项的索引，语法格式为(item, index) in items，

注意：v-for中的item和index都是形参，可以改变

```html
<table class="table table-bordered table-center table-hover table-striped">
    <thead>
        <th>索引</th>
        <th>ID</th>
        <th>姓名</th>
    </thead>
    <tbody>
        <tr v-for="(item,index) in list">
            <td>{{index}}</td>
            <td>{{item.id}}</td>
            <td>{{item.name}}</td>
        </tr>
    </tbody>
</table>
```

key值的注意事项

+ key的值只能是字符串或数字类型
+ key的值必须据唯一性
+ 建议把数据项id属性的值作为key的值
+ 使用index的值当作key的值没有任何意义（索引不具有唯一指向性）
+ 建议使用v-for指令时一定要制定key的值

#### 1.5.9 过滤器（vue2）

+ 过滤器Filters是vue为开发者提供的功能，常用于**文本的格式化**，用途：**插值表达式和v-bind属性绑定**

+ 过滤器应该被添加在JavaScript表达式的尾部，由“`管道符|`”进行调用

```html
<div id="app">
    <div>message:{{ message | capi }}</div>
</div>
<script>
    const vm = new Vue({
        el:'#app',
        data:{
            message:'hello, vue.js!'
        },
        // 过滤器函数，必须被定义到filters节点之下
        // 过滤器本质上是函数
        filters:{
            // 注意过滤器函数形参中的val,永远都是"管道符 | "前面的那个值
            capi(val){
                // 字符串由charAt方法，这个方法接受索引值，表示从字符串中把索引对应的字符，给取出来
                // console.log(val);
                const first = val.charAt(0).toUpperCase()
                // 字符串的slice方法，可以截取字符串，从指定索引往后截取
                const other = val.slice(1)
                // 强调；过滤器中一定要有一个返回值
                return first+other;
            }
        }

    })
</script>
```

+ 私有过滤器
+ 全局过滤器 
+ 在filters节点下定义的过滤器，成为”私有过滤器“，因为它只能在当前vm实例所控制的el区域内使用。如果希望在多个vue实例之间共享过滤器，可以如下定义：

```vue
// 使用Vue.filter()定义全局过滤器
Vue.filter('capi',function(str){
    const first = str.charAt(0).toUpperCase()
    const other = str.slice(1)
    return first;
})
```

+ 可连续调用多个过滤器

#### 1.5.10 侦听器

1、方法格式的侦听器

缺点1：无法在更进入页面的时候，自动触发

缺点2：如果侦听的是一个对象，如果对象中的属性发生了变化，不会发生变化

2、对象格式的侦听器

好处1：可以通过immediate选项，让侦听器自动触发

好处2：可以通过deep选项，让侦听器深度监听对象中每个属性的变化！！！

```vue
watch: {
    // 方法格式的侦听器
    username(newVal, oldVal){
    	console.log("新值："+newVal,"旧值："+ oldVal);
    },
    // 对象格式的侦听器
    username: {
        // 侦听器的处理函数
        handler(newVal, oldVal){
        	console.log("新值："+newVal,"旧值："+ oldVal);
        },
    	// immediate的作用是控制侦听器是否默认自动触发一次
    	immediate: true
	}
}
```

#### 1.5.11 计算属性???

+ ES6模板字符串

特点

+ 定义的时候要被定义成方法
+ 在使用计算属性的时候，当普通的属性使用即可

好处

+ 实现了代码的复用
+ 只要计算属性中依赖的数据源发生了变化，计算属性会重新开始求值！

```html
// 所有的计算属性，都要定义在computed节点下
// 计算属性在定义的时候，要定义成"方法格式"
computed: {
    // rgb作为一个计算属性，被定义成方法格式
    // 最终在这个方法中要返回一个生成好的rgb(x,x,x)的字符串
    rgb(){
    	return `rgb(${this.r},${this.g},${this.b})`
    }
}
```

## 二、深入组件

### 2.1 axios

> axios是一个专注于网络请求的库

[起步 | Axios 中文文档 | Axios 中文网 (axios-http.cn)](https://www.axios-http.cn/docs/intro)

#### 2.1.1 get请求

```js
axios({
    // 请求方式
    methods: 'GET',
    // 请求的地址
    url: 'http://localhost:8080/teachers',
    // URL中的查询参数
    params: {},
    // 请求体参数
    data: {}
}).then(function(result){
    console.log(result);
})
```

#### 2.1.2 post请求

```js
document.querySelector('#btnPost').addEventListener('click', async function () {
    // 如果调用某个方法的返回值是 Promise 实例，则前面可以添加 await！
    // await 只能用在被 async “修饰”的方法中
    const { data: res } = await axios({
        method: 'POST', 
        url: 'http://www.liulongbin.top:3006/api/post',
        data: {
            name: 'zs',
            age: 20
        }
    })

    console.log(res)
})
```

#### 2.1.3 直接使用get和post请求

```js
<button id="postInfo">发起post请求</button>
<button id="getInfo">发起get请求</button>
<script>
    document.querySelector('#postInfo').addEventListener('click', async function(){
    url = "http://localhost:8080/teachers"
    const { data:res } = await axios.post(url, {
        // 请求体数据
        // id : 1, name:'王栋', type:'语文', appraise:'优秀'
    })
    console.log(res)
})
document.querySelector('#getInfo').addEventListener('click', async function(){
    url = "http://localhost:8080/teachers"
    const { data:res } = await axios.get(url, {params: { id:1 }})
    console.log(res)
})
```

### 2.2 vue组件

#### 2.2.1 vue-cli安装

+ 简化了介于webpack创建工程化的Vue项目的过程

+ 在终端下运行如下的命令，创建指定名称的项目：

```bash
vue create 项目的名称
```

![image-20220815170216439](E:\savefile\typora\image\image-20220815170216439.png)

![image-20220815170632263](E:\savefile\typora\image\image-20220815170632263.png)

![image-20220815170712421](E:\savefile\typora\image\image-20220815170712421.png)

![image-20220815170744427](E:\savefile\typora\image\image-20220815170744427.png)

![image-20220815171053344](E:\savefile\typora\image\image-20220815171053344.png)

![image-20220815171506721](E:\savefile\typora\image\image-20220815171506721.png)

vue 项目中 src 目录的构成：

```js
assets 文件夹：存放项目中用到的静态资源文件，例如：css 样式表、图片资源
components 文件夹：程序员封装的、可复用的组件，都要放到 components 目录下
main.js 是项目的入口文件。整个项目的运行，要先执行 main.js
App.vue 是项目的根组件。
```

vue项目的运行流程：通过main.js把App.vue渲染到index.html的指定区域中

其中

+ App.vue 是项目的根组件，用来编写待渲染的模板结构
+ index.html 中需要预留一个el区域
+ main.js 把App.vue 渲染到了index.html所预留的区域中

组件化开发

+ 根据封装的思想，把页面上可重用的UI结构封装为组件，从而方面项目的开发和维护

vue组件的三个组成部分

+ template -> 组件的模板结构
+ script -> 组件的Javascript行为
+ style -> 组件的样式

#### 2.2.2 vue组件的关系

在使用时表示

> 1、注册私有子组件

+ 使用import语法导入需要的组件

```js
import Left from '@/components/Left.vue'
```

+ 使用components节点注册组件

```js
export default{
	components:{
		Left
	}
}
```

+ 以标签形式使用刚才的组件

```vue
<div class='box'>
	<Left></Left>
</div>
```

> 2、注册全局组件

+ 在vue项目的main.js入口文件中，通过Vue.component()方法，可以注册全局组件

```js
// 导入需要全局注册的组件 
import Count from '@/components/Count.vue'

// 参数1: 字符串格式, 表示组件的注册名称
// 参数2: 需要被全局注册的那个组件
Vue.component('MyCount',Count);
```

> 3、组件的props

+ props是组件的自定义属性，在封装通用组件的时候，合理地使用props可以极大地提高组件的复用性

```js
export default {
    // props是自定义属性，允许使用者通过自定义属性，为当前组件指定初始值
    // 自定义属性的名字，是封装者自定义的(只要名称合法即可)
    // props 中的数据，可以直接在模板结构中使用
    // props 的值是只读的
    props:['init'],
    data(){}
}
```

+ vue规定：组件中封装的自定义属性是指只读的，陈鼓学院不能直接修改props的值，否则会直接报错

![image-20220819172013652](E:\savefile\typora\image\image-20220819172013652.png)

+ props的default默认值

+ 在声明自定义属性时，可以通过default来定义属性的默认值。

```js
export default {
	props:{
        init: {
            // 用 default 属性来定义默认值
            default: 0,
            // init 的值类型必须是 Number 数字
            type: Number,
            // 必选项校验
            required: true
        }
    }
}
```

> 4、组件之间的样式冲突问题
>

默认情况下，写在.vue组件中的样式会全局生效，因此很容易造成**多个组件之间的样式冲突问题**

导致组件之间样式冲突的根本原因是：

+ 单页面应用程序中，所有组件的DOM结构，都是基于唯一的index.html页面进行呈现的
+ 每个组件中的样式，都会影响整个index.html页面中的DOM元素

#### 2.2.3 组件的生命周期???

生命周期是指一个组件从**创建运行到销毁**的整个阶段，**强调的是一个时间段**

**生命周期函数**：是由vue框架提供的内置函数，会伴随着组件的生命周期，**自动按次序执行**

### 2.3 路由

#### 2.3.1 基础知识

路由：Hash地址与组件之间的对应关系

前端路由的工作方式

+ 用户点击了页面上的路由链接
+ 导致了URL地址栏中的Hash值发生了变化
+ 前端路由监听了到Hash地址的变化
+ 前端路由把当前**Hash地址对应的组件**渲染到浏览器中

<img src="E:\savefile\typora\image\image-20220820105055626.png" alt="image-20220820105055626" style="zoom:80%;" />

#### 2.3.2 vue-router插件的基本用法

vue.js官方给出的路由解决方案，只能结合vue项目进行使用

1、在控制台中安装 vue-router 包

```
npm i vue-router@3.5.2 -S
```

2、创建路由模块

在src源代码目录下，新建router/index.js路由模块

```js
// 1、导入 Vue 和 VueRouter 的包
import Vue from "vue";
import VueRouter from "vue-router";

// 2、调用 Vue.use() 函数，把 VueRouter 安装为 Vue 的插件
Vue.use(VueRouter)

// 3、创建路由的实例对象
const router = new VueRouter()

// 4、向外共享路由的实例对象
export default router 
```

3、导入并挂在路由模块（在main.js中加入）

```js
import router from '@/router/index.js'

new Vue({
  render: h => h(App),

  // router: 路由的实例对象
  router,
}).$mount('#app')
```

4、声明路由链接和占位符

在 src/App.vue 组件中，使用 vue-router 提供的 <router-link>和<router-view>声明路由链接和占位符

```vue
<template>
    <div class="app-container">
        <h2>App2组件</h2>
        <router-link to="/home">首页</router-link>
        <router-link to="/movie">电影</router-link>
        <router-link to="/about">关于</router-link>
        <hr />
        <router-view></router-view>
    </div>
</template>
```

5、声明路由的匹配规则

在 src/router/index.js 路由模块中，通过 routes 数组声明路由的匹配规则。

```js
// 1、导入 Vue 和 VueRouter 的包
import Vue from "vue";
import VueRouter from "vue-router";
import home from '@/components/Home.vue'
import movie from '@/components/Movie.vue'
import about from '@/components/About.vue'

// 2、调用 Vue.use() 函数，把 VueRouter 安装为 Vue 的插件
// Vue.use() 函数的作用，就是来安装插件的
Vue.use(VueRouter)

// 3、创建路由的实例对象
const router = new VueRouter({
    // routes是一个数组，作用：定义“Hash地址”与组件之间的对应关系
    routes:[
        // 重定向路由规则
        {path:'/',redirect:'/home'},
        // 路由规则
        {path:'/home',component:home},
        // 需求：在movie组件中，希望根据id的值，展示对应电影的详细信息
        // 可以为路由规则开启 props 传参，从而方面的拿到动态参数的值
        {path:'/movie',component:movie}
    ],
})
```

一些概念：

+ 路由重定向：用户在访问地址 A 的时候，强制用户跳转到地址 C ，从而展示特定的组件页面。 通过路由规则的 redirect 属性，指定一个新的路由地址，可以很方便地设置路由的重定向：
+ 嵌套路由：通过路由实现组件的嵌套展示，叫做嵌套路由。
+ 声明子路由链接和子路由占位符。在 About.vue 组件中，声明 tab1 和 tab2 的子路由链接以及子路由占位符，在 src/router/index.js 路由模块中，导入需要的组件，并使用 children 属性声明子路由规则

``` js
// 1、导入 Vue 和 VueRouter 的包
import Vue from "vue";
import VueRouter from "vue-router";
import home from '@/components/Home.vue'
import movie from '@/components/Movie.vue'
import about from '@/components/About.vue'
import Tab1 from '@/components/tabs/Tab1.vue'
import Tab2 from '@/components/tabs/Tab2.vue'
import main from '@/components/Main.vue'
import login from '@/components/Login.vue'

// 2、调用 Vue.use() 函数，把 VueRouter 安装为 Vue 的插件
// Vue.use() 函数的作用，就是来安装插件的
Vue.use(VueRouter)

// 3、创建路由的实例对象
const router = new VueRouter({
    // routes是一个数组，作用：定义“Hash地址”与组件之间的对应关系
    routes:[
        // 重定向路由规则
        {path:'/',redirect:'/home'},
        // 路由规则
        {path:'/home',component:home},
        // 需求：在movie组件中，希望根据id的值，展示对应电影的详细信息
        // 可以为路由规则开启 props 传参，从而方面的拿到动态参数的值
        {path:'/movie/:mid',component:movie, props:true},
        {
            path:'/about',
            component: about,
            // redirect: '/about/tab1',
            children: [
                // 子路由规则
                // 通过children属性，嵌套使用子路由规则
                // 默认子路由：如果children数组中，某个路由规则的path值为空字符串，则这条路由规则，叫做“默认子路由”
                {path:'',component:Tab1},
                {path:'tab2',component:Tab2},
            ]
        },
        {path:'/login',component:login},
        {path:'/main',component:main}
    ],
})
```

### 2.4 动态组件

动态组件指的是动态切换组件的显示与隐藏

vue 提供了一个内置的组件，专门用来实现动态组件的渲染

```vue
// 1、导入需要使用的.vue组件
import Left from '@/components/Left.vue'
import Right from './components/Right.vue';

data(){
    return{
        // 当前要渲染的组件的名称 
        comName: 'Left',
    }
},

<!-- 通过is属性，动态指定要渲染的组件 -->
<!-- 1、component 标签是 vue 内置的，作用：组件的占位符 -->
<!-- 2、is属性的值，表示要渲染的组件的名字 -->
<!-- 3、is属性的值，应该是组件在 components 节点下的注册名称 -->
<component :is="comName"></component>
```

使用 **keep-alive** 保持状态：默认情况下，切换动态组件时无法保持组件的状态。此时可以使用 vue 内置的组件保持动态组件的状态。

```vue
<!-- keep-alive可以把内部的组件进行缓存，而不是销毁组件 -->
<!-- 在使用 keep-alive 的时候，可以通过 include 指定那些组件需要被缓存 -->
<!-- 或者，通过 exclude 属性指定那些组件不需要被缓存，但是不要同时使用 include 和 exclude 这两个属性 -->
<keep-alive include="Left,Right" exclude="">
    <component :is="comName"></component>
</keep-alive>
```

+ 当组件被缓存时，会自动触发组件的 deactivated 生命周期函数;

+ 当组件被激活时，会自动触发组件的 activated 生命周期函数;

```vue
created(){
	console.log("Left组件被创建了....")
},
destroyed(){
	console.log("Left组件被销毁了....")
},
<!-- 只有在keep-alive组件中和才会被使用 -->
activated(){
	console.log("Left组件被激活了：activated")
},
deactivated(){
	console.log("Left组件被缓存了：deactivated")
}
```

### 2.5 Vue生命周期

vue 生命周期指的是vue实例从创建到销毁的过程，即指从创建、初始化数据、编译模板、挂在DOM到渲染、更新到渲染、销毁等一系列过程，他主要分为八个阶段：创建前后、载入前后、更新前后、销毁前、销毁后以及一些特殊场景的生命周期。

| 生命周期      | 描述                               |
| ------------- | ---------------------------------- |
| beforeCreate  | 组件实例被创建之前                 |
| created       | 组件实例已经完全创建               |
| beforeMount   | 组件挂载之前                       |
| mounted       | 组件挂载到实例上去之后             |
| beforeUpdate  | 组件数据发生变化，更新之前         |
| updated       | 数据更新之后                       |
| beforeDestory | 组件实例销毁之前                   |
| destroyed     | 组件实例销毁之后                   |
| activated     | keep-alive 缓存的组件激活时        |
| deactivated   | keep-alive 缓存的组件停用时调用    |
| errorCaptured | 捕获一个来自子孙组件的错误时被调用 |

![组件生命周期图示](vue.assets/lifecycle.16e4c08e.png)

## 三、外部组件

### 3.1 echarts

```
// 导包
npm install echarts --save
// 全局引入
import * as echarts from "echarts";
Vue.prototype.$echarts = echarts;
```

1、legend：图例样式

```js
legend:{
    left:'center',
        textStyle:{
            color:'white',
        }
},
```

2、tooltip：背景框

```js
tooltip: {
    show: true,
        trigger: 'axis', // 鼠标悬浮会有竖线
        axisPointer: {
            type: 'cross'
         }
},
```

3、xAxis、yAxis

```js
// x轴文字的配置
axisLabel: { 
    show: true,
        textStyle: {
            color: "rgba(219,225,255,1)",
        }
},

// 去除图中的横线和竖线
splitLine:{
   show:false
}
```

4、toolbox：工具箱

```js
toolbox: { // 工具箱
    show: true,
        feature: {
            dataZoom: {
                yAxisIndex: 'none'
            },
                dataView: {
                    readOnly: false
                },
                    magicType: {
                        type: ['bar', 'line']
                    },
                        restore: {}
        }
},
```

