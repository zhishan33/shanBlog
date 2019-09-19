---
layout: default
title: js extends
date: 2019-09-17 +0800
categories: js
tags: [js]
---

## js 继承

> 通过构造函数继承

```

  function Parent(param1,param2){
    this.param1 = param1
    this.param2 = param2
    Parent.prototype.publicFunc = function(){
      console.log('this is public func')
    }
  }

  const child = new Parent('param1','param2')

```

> 原型继承

```
  function creatObj(o){
    function F(){}
    F.prototype = o;
    return new F();
  }

```

> 寄生继承

```

  const obj = {
    name: 'name',
    age: '20'
  }
  function User(obj){
    let o = Object.create(obj);
    o.prototype.publicFunc = function(){
      console.log('--public func--')
    }
    return o;
  }

```

> 寄生组合式

```
  function inherit(child,parent){
    const p = Object.create(parent.prototype);
    child.protoptype = p;
    p.constructor = child;
  }
```

## 相关链接
- [首页](https://zhishan33.github.io/shanBlog/)

> {{page.date | date: '%Y, %b %d' }}
