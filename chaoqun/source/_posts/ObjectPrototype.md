---
title: ObjectPrototype
date: 2018-10-23 19:58:56
tags: [object,原型链]

---

> 学习上容易忘得一次总结
<!--more-->

### Array.prototype.slice.call(arguments)

1.Array.prototype.slice.call(arguments)能将具有length属性的对象转成数组

```
var a={length:2,0:'first',1:'second'};

Array.prototype.slice.call(a);//  ["first", "second"]

```



方法

适用范围

描述


for..in |数组，对象 |获取可枚举的实例和原型属性名
:----|:----:|----: 
Object.keys() 数组，对象 |返回可枚举的实例属性名组成的数组 
Object.getPropertyNames() |数组，对象 |返回除原型属性以外的所有属性（包括不可枚举的属性）名组成的数组 
for..of |可迭代对象(Array, Map, Set, arguments等) |返回属性值 



