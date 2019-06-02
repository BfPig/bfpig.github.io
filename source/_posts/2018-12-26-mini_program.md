---
title: 在小程序中使用Async/Await
date: 2018-12-26 00:17:05 +0800
comments: true
categories: [前端笔记,小程序]
tags:
  - 小程序
  - 前端笔记
---

截止2018-12-26，最先版本的小程序依旧不支持ES7的语法Async/Await

为了让小程序支持Async/Await，这里要用到一个库[regenerator](https://github.com/facebook/regenerator)

我们最终要引用到的文件就是`regenerator-runtime.js`

在utils中import 

```
import regeneratorRuntime from './regenerator-runtime/runtime-module'

```

正常使用Async/Await即可！

（没有抓住圣诞节的尾巴，就依旧只能提前祝自己狗狗快乐一声了）