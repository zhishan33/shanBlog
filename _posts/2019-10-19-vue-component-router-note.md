---
layout: default
title: vue router component notes
date: 2019-10-19 +0800
categories: vue
tags: [vue, router, component, notes]
---

## vue router component notes

### 问题：导航到下一个路由组件过程中，前一个路由组件的beforeDestroy钩子函数似乎晚于下一个路由组件的created钩子函数

```js
 //befoure router component
 {
	 beforeDestroy(){
		 console.log('before route component run beforeDestroy')
	 }
 }
 //next router component
 {
	 created(){
		 console.log('next route component run created')
	 },
	 mounted(){
		 console.log('next route component run mounted')
	 }
 }

```

### run result 

```js
	'next route component run created'
	'before route component run beforeDestroy'
	'next route component run mounted'
```

## 相关链接

* [首页](https://zhishan33.github.io/shanBlog/)

> {{page.date | date: '%Y, %b %d' }}
