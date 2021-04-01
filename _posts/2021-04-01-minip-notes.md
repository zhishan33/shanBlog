---
layout: default
title: 小程序开发笔记
date: 2021-04-01 +0800
categories:
tags: [minip, note]
---
## 切换回微信自研chromium 内核。

1. 用户的设备没有微信自研的 chromium 内核；
2. 用户点击过强制切换到 X5 内核的链接，这个问题可以在微信 app 中点击如下链接恢复：**http://debugxweb.qq.com/?set_appbrand_config=WV_KIND_NONE&set_web_config=WV_KIND_NONE&** , 会弹窗“打开网页将使用：WV_KIND_NONE”，重启微信 app 即可切换回chromium 内核。



## 相关链接

- [小程序「同层渲染」那些事(keng)?](https://juejin.cn/post/6881502813105422349)
- [首页](https://zhishan33.github.io/shanBlog/)

> {{page.date | date: '%Y, %b %d'}}
