---
﻿title: JavaScript：你应该知道的true和false
date: 2016/12/1 20:46:25
categories: 
- 翻译
tags:
- JavaScript
---

跟其他大多数的计算机语言一样，JavaScript也支持Boolean类型的数据，这些值可以被设置为`true` 或者`false` 。另外，JavaScript中的所有东西都有一个默认的布尔值，一般称为真值（truthy）或者假值（falsy）。在处理真值和假值时会有一点奇怪，尤其是变量与变量之间进行比较的时候。理解更多相关的怪异规则会对我们开发调试复杂的客户端应用程序很有帮助。
<!--more-->
### 真值和假值

下面这些值在JavaScript中都是`falsy`：
- false
- 0 （数字零）
- "" （空字符串）
- null
- undefined
- NaN （一个特殊的Number值，意为Not-a-Number!）

除上面几个值以外，其他所有值都是`truthy`，包括字符串"0", "false", 空函数，空数组，空对象。
```javascript
var a = !!(0); // 把变量的值设为false
var b = !!("0"); // true
```
### 假值的比较
`Falsy values`遵循一些看起来怪怪的比较规则，这些规则可能会导致程序出现一些逻辑错误。

假值`false`，`0`，`""`三者是相等的，并且它们之间可以相互比较。
```javascript
var c = (false == 0); // true
var d = (false == ""); // true
var e = (0 == ""); // true
```
假值`null`，`undefined`，除了它们自身之外和任何值都不相等。
```javascript
var f = (null == false); // false
var g = (null == null); // true
var h = (undefined == undefined); // true
var i = (undefined == null); // true
```
最后，假值 **NaN** 和任何值都不相等，包括 NaN 本身！
```javascript
var j = (NaN == null); // false
var k = (NaN == NaN); // false
```
你应该知道`typeof(NaN)`返回"Number"。幸运的是，JavaScript有一个核心函数`isNaN()`来判断一个值是否是NaN。
##### 如果还是有疑惑
那么请在使用真值、假值容易导致逻辑错误的地方，使用严格相等（===）和严格不相等（!==）吧。这两个操作符会同时比较对象的类型和值。
```javascript
var l = (false == 0); // true
var m = (false === 0); // false
```
在你写JavaScript代码的时候，真值和假值让你痛苦过吗？

作者简介：Craig Buckler是一名英国特约web顾问，他早在1995年就 搭建了一个在IE 2.0 上面展示的页面。从那时候开始，他就开始倡导web标准，可访问性，HTML5技术的最佳实践。他已经在[SitePoint](https://www.sitepoint.com/)上面写了超过1000篇文章，你可以在这里找到他[@craigbukler](http://twitter.com/craigbuckler)。

原文：[https://www.sitepoint.com/javascript-truthy-falsy/](https://www.sitepoint.com/javascript-truthy-falsy/)
作者：Craig Buckler
译者：杨忠勋
