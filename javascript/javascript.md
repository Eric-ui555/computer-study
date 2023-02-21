# JavaScript

## 1、JS基础

## 2、ES6

[ECMAScript 6 入门 - 《阮一峰 ECMAScript 6 (ES6) 标准入门教程 第三版》 - 书栈网 · BookStack](https://www.bookstack.cn/read/es6-3rd/sidebar.md)

### 关键字

> let

let:ES6中新增的用于声明变量的关键字

let声明的变量**只在所处于的块级有效**

```javascript
if (true) { 
     let a = 10;
 }
 console.log(a) // a is not defined
```

注意：使用let关键字声明的变量才具有块级作用域，使用var声明的变量不具备块级作用域特性。

> const

作用：声明常量，常量就是值（内存地址）不能变化的量。

+ 具有**块级作用域**
+ **声明常量时必须赋值**
+ 常量赋值后，值不能更改

> let、const、var的区别

1. 使用 var 声明的变量，其作用域为该语句所在的函数内，且存在变量提升现象。

2. 使用 let 声明的变量，其作用域为该语句所在的代码块内，不存在变量提升。

3. 使用 const 声明的是常量，在后面出现的代码中不能再修改该常量的值。

| **var**      | **let**        | **const**      |
| ------------ | -------------- | -------------- |
| 函数级作用域 | 块级作用域     | 块级作用域     |
| 变量提升     | 不存在变量提升 | 不存在变量提升 |
| 值可更改     | 值可更改       | 值不可更改     |

### 解构赋值

ES6中允许从数组中提取值，按照对应位置，对变量赋值。对象也可以实现解构。

> 数组解构

```javascript
let [a, b, c] = [1, 2, 3];
console.log(a)
console.log(b)
console.log(c) 

```

如果解构不成功，变量的值为undefined。

> 对象解构

```javascript
 let person = { name: 'zhangsan', age: 20 }; 
 let { name, age } = person;
 console.log(name); // 'zhangsan' 
 console.log(age); // 20
```

```javascript
 let {name: myName, age: myAge} = person; // myName myAge 属于别名
 console.log(myName); // 'zhangsan' 
 console.log(myAge); // 20
```

### 箭头函数

ES6中新增的定义函数的方式，用来简化函数定义语法。

```javascript
() => {} 
const fn = () => {}
```

函数体中只有一句代码，且代码的执行结果就是返回值，可以省略大括号

```javascript
 function sum(num1, num2) { 
     return num1 + num2; 
 }
 const sum = (num1, num2) => num1 + num2; 
```

 如果形参只有一个，可以省略小括号

```javascript
 function fn (v) {
     return v;
 } 
 const fn = v => v;
```

箭头函数不绑定this关键字，箭头函数中的this，指向的是函数定义位置的上下文this。

```javascript
 const obj = { name: '张三'} 
 function fn () { 
     console.log(this);
     return () => { 
         console.log(this)
     } 
 } 
 const resFn = fn.call(obj); 
 resFn();
```

> 箭头函数的重要特性：箭头函数从动议自己的环境继承 this 关键字的值，而不是像以其他方式定义的函数那样定义自己的调用上下文。

### 剩余参数

剩余参数和解构配合使用

```javascript
 let students = ['wangwu', 'zhangsan', 'lisi'];
 let [s1, ...s2] = students; 
 console.log(s1);  // 'wangwu' 
 console.log(s2);  // ['zhangsan', 'lisi']
```

### 严格模式和非严格模式

[JS基础：严格模式与非严格模式的区别 - 掘金 (juejin.cn)](https://juejin.cn/post/6946804445267099684)

**严格模式**的概念是从ECMAScript5引入的，通过严格模式，可以在**函数内部选择进行较为严格的全局或局部的错误条件检测**。

1. 严格模式通过抛出错误来消除了一些原有静默错误。
2. 严格模式修复了一些导致 JavaScript引擎难以执行优化的缺陷：有时候，相同的代码，严格模式可以比非严格模式下运行得更快。
3. 严格模式禁用了在ECMAScript的未来版本中可能会定义的一些语法。

开启严格模式：**"use strict";**

**严格模式与非严格模式的区别**

1. 严格模式下变量必须声明才能使用
2. 严格模式下禁止使用with语句
3. 严格模式下创建eval作用域
4. 严格模式下禁止this关键字指向全局对象
5. 严格模式下禁止在函数内部遍历调用栈
6. 严格模式下无法删除变量
7. 严格模式下 显示报错
8. 严格模式下，不允许对禁止扩展的对象添加新属性
9. 严格模式下，禁止删除一个不可删除的属性
10. 严格模式下禁止重复变量声明
11. 严格模式下函数不能有重名的参数
12. 严格模式下禁止八进制写法

