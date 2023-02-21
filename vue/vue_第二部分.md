### 命名空间规范

[Vue.js命名风格指南（易记版） - 掘金 (juejin.cn)](https://juejin.cn/post/6961226664869101605)

- `camelCase`（驼峰式 ）
- `kebab-case`（短横线连接式）
- `PascalCase`（帕斯卡命名式）
- `Snake`（下划线连接式）

1、采用 `kebab-case`命名的：

- 文件夹
- 单文件组件
- 组件在html模板中使用（ `<my-component></my-component>`）
- 在模板中prop传入属性到子组件（ `<my-componnetset-text="hello"/>`）
- 所有事件名（ `this.$emit('api-reload')`）

2、采用 `PascalCase`命名：

- 公共基础组件（ `MfcSelect`）
- js中components注册组件时（ `importMyComponentfrom'./my-component.vue'`）
- 组件的name属性（ `name:'MyComponent'`）

3、采用 `camelCase` 命名：

- 子组件接收prop属性

```js
props: {
    setText: String
}
```

### computed-计算属性

[vue 的computed - 之鹿喵 - 博客园 (cnblogs.com)](https://www.cnblogs.com/zhilu/p/15252046.html)

定义：当其依赖的属性的值发生变化时，计算属性会重新计算，反之，则使用缓存中的属性值。

1、与方法区别：计算属性基于缓存依赖，属性依赖改变重新渲染，方法每次都会重新渲染

2、与watch区别：

+ 计算属性可以处理多个属性汇总或者计算出一个总的结果（一个多对一或者一对）；

+ watch监听可以处理监听一个”对象“，从而去改变其他一些列的属性或者对象；

**get（读取）和set（设值）**

```js
var vm = new Vue({
    el: '#example',
    data: {
        message: 'Hello'
    },
    computed: {
        updateMessage: {
            get: function() {
                console.log('计算属性', this.message)
                return this.message
            },
            set: function(newVal) {
                this.message = newVal
                console.log('newVal', newVal)
            }
        }
    },
    mounted () {
        this.updateMessage = '222'
        console.log('测试：', this)
    },
})

// 打印结果
1 newVal: 222,
2 计算属性： 222
```

### 模板引用：ref

vue自带的获取DOM的方法

+ 获取DOM，操作DOM

```
<template>
  <div id="app">
    <div ref="testDom">11111</div>
    <button @click="getTest">获取test节点</button>
  </div>
</template>

<script>
export default {
  methods: {
    getTest() {
      console.log(this.$refs.testDom)
    }
  }
};
</script>
```

+ 获取组件，拿到组件中的变量和方法



### 父组件传值到子组件

> 1、props

```js
<!--父组件-->
<!--数据透视弹窗区域-->
<pivotDialog ref="pivotRef" :originData="originData" :pivotDataForm="pivotDataForm"
:sensorList="sensorList" @pivotDataFromChild="pivotDataFromChild"></pivotDialog>

<!--子组件-->
props: ["originData", "sensorList", "pivotDataForm"]   // 变量：单向传值
```

> 2、this.$refs.(定义的ref).(子组件methods)

注意：弹窗组件visible建议用此种方法

```vue
<!--父组件-->
<pivotDialog ref="pivotRef" :originData="originData" :pivotDataForm="pivotDataForm"
:sensorList="sensorList" @pivotDataFromChild="pivotDataFromChild"></pivotDialog>

this.$refs.pivotRef.openDialog()

<!--子组件pivotDialog-->
<!--数据透视弹窗区域-->
<el-dialog title="数据透视" :visible.sync="showDialog" width="40%">
    <div>内容</div>
    <span slot="footer" class="dialog-footer">
        <el-button type="primary" @click="pivotData">确 定</el-button>
<el-button @click="showDialog = false">取 消</el-button>
</span>
</el-dialog>

openDialog() {
    this.showDialog = true;
},
```

### 子组件向父组件传值

1、this.$emit('父组件方法名','参数列表')

```js
<!--父组件-->
pivotDataFromChild(val) {
    this.filterCopyData = val;
},

<!--子组件-->
this.$emit('pivotDataFromChild', filterData)
```

2、this.$parent.(method)

```js
<!--父组件-->
components: {pivotDialog},
    openPivotDialog() {
      this.$refs.pivotRef.openDialog()
    },
<!--子组件-->
this.$parent.openPivotDialog()
```

### 依赖注入

[vue中的依赖注入provide和inject（简单易懂） - Ynline - 博客园 (cnblogs.com)](https://www.cnblogs.com/Ynline/p/16857403.html)

`provide/inject`选项：这对选项允许一个祖先组件向其所有子孙后代组件注入一个依赖，不论组件层次有多深，并在起上下游关系成立的时间里始终生效。

provide就相当于加强版父组件prop，可以跨越中间组件`，`inject就相当于加强版子组件的props

### vuex

[Vuex 是什么？ | Vuex (vuejs.org)](https://vuex.vuejs.org/zh/)

[vue中使用vuex(超详细) - 掘金 (juejin.cn)](https://juejin.cn/post/7013325675129995272)

vuex是一个专为 Vue.js 应用程序开发的**状态管理模式**， 采用**集中式存储**管理应用的所有组件的状态，解决多组件数据通信。(简单来说就是管理数据的,相当于一个仓库,里面存放着各种需要共享的数据,所有组件都可以拿到里面的数据)

安装：`npm install vuex --save`

1.state 统一定义管理公共数据

2.mutations: 使用它来修改数据

3.getters: 类似于vue中的计算属性

4.actions: 类似于methods,用于发起异步请求,比如axios

5.modules: 模块拆分

```js
import Vue from 'vue'
import Vuex from 'vuex'
Vue.use(Vuex)
export default new Vuex.Store({
    state: { // 存放数据 和data类似
    },
    mutations: { // 用来修改state和getters里面的数据
    },
    getters: { // 相当于计算属性
    },
    actions: { // vuex中用于发起异步请求
    },
    modules: {// 拆分模块
    }
})
```

