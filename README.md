# Vue.js 源码启示录

Vue.js 源码学习记录仓库，源码部分实现，问题记录......

> Note: 本仓库仅实现 Vue.js 核心 MVVM 功能，未考虑兼容性，未实现 AST 语法树和模板编译等功能，仅供参考。

## I. 深入响应式原理

### 1. initData()

初始化数据

### 2. observe()

观察数据

- Observer 观察者类

  - 添加观察者标记
  - 对象劫持
  - 数组劫持

#### 对象属性劫持

- defineReactive()
  - 遍历属性，定义响应式
  - 属性劫持，代理存取访问器
  - 递归代理嵌套对象
  - 递归代理新值

#### 数组变异方法劫持

- observeArray()
  遍历元素，代理嵌套对象
- protoAugment() / copyAugment()
  原型链劫持，扩展数组方法

### 3. proxy()

数据代理
