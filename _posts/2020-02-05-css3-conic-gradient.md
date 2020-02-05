---
layout: default
title: css3 conic-gradient notes
date: 2020-02-05 +0800
categories: css
tags: [css, css3, notes]
---

## css3 圆锥渐变 conic-gradient


```
  <div class="circle-progress" data-progress = "30%"></div>
  .circle-progress {
    height: 300px;
    width: 300px;
    border-radius: 50%;
    background: conic-gradient(pink 0, pink 30%, grey 30%, grey 100%);
    position: relative;
  }
  .circle-progress::after {
    content: attr(data-progress);
    text-align: center;
    line-height: 290px;
    font-size: 2em;
    display: block;
    position: absolute;
    /* clip: rect(5px 295px 295px 5px); */
    background-color: white;
    top: 5px;
    right: 5px;
    bottom: 5px;
    left: 5px;
    border-radius: 50%;
  }

```


## 相关链接

* [首页](https://zhishan33.github.io/shanBlog/)

> {{page.date | date: '%Y, %b %d' }}
