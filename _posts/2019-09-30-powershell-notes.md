---
layout: default
title: powershell notes
date: 2019-09-30 +0800
categories: powershell
tags: [poweroff, notes]
---

## powershell notes

### 常见命令

```powershell
 cp ./dist/* ../nginx/www/ -R
 rm ../nginx/www/*
 rm ../nginx/www/* -r

```

### 新建文件

```powershell
new-item filename
```

### 查看目录结构

```powershell
 tree ./dist /a
 tree ./dist /f
```

## 相关链接

* [首页](https://zhishan33.github.io/shanBlog/)

> {{page.date | date: '%Y, %b %d' }}
