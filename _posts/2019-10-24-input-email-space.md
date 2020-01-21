---
layout: default
title: html5 input email space
date: 2019-10-24 +0800
categories: html5
tags: [html5,input, email, space, notes]
---

## 当 input type="email" 时 监听input事件时，按下空格键不触发input事件
> 记录今日在处理输入框过滤空格时，一直处理不了，花了很长时间打补丁，下班回家又重新尝试找问题，发现原来type="text"时按下空格键正常触发input事件，但是type=email时不触发input事件

```html
  <input type="email" oninput="alert(this.value)" placeholder="email">
  <input type="text" oninput="alert(this.value)" placeholder="text">
```
---

<div>
  <input type="email" oninput="alert(this.value)" placeholder="email">
  <input type="text" oninput="alert(this.value)" placeholder="text">
</div>

---

## 相关链接

* [首页](https://zhishan33.github.io/shanBlog/)

> {{page.date | date: '%Y, %b %d' }}
