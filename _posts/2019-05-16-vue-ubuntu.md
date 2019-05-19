---
layout: default
title: ubuntu下安装vue-cli
date: 2019-05-16 +0800
categories: vue
tags: [vue, ubuntu]
---

# Ubuntu 下如何安装 vue-cli

## 1. 安装nodejs
  + 从nodejs官网(https://nodejs.org/en/download/)下载Linux Binaries (x64)源代码
  + 解压node源代码包

  ```

  tar -xvf node-v10.15.3-linux-x64.tar.xz -C /media/home/application/

  ```

## 2. 建立软连接

```

   sudo ln -s /media/home/application/node-v10.15.3-linux-x64/bin/node /usr/local/bin/node
   sudo ln -s /media/home/application/node-v10.15.3-linux-x64/bin/npm /usr/local/bin/npm

```

## 3. 修改npm安装包默认目录

```

  npm config set prefix="/media/home/application/npm-global"
  npm config set cache="/media/home/application/npm-cache"

```

## 4. 安装nrm
  + 创建nrm软连接
   - 利用nrm查看npm安装源
   - 切换 npm 安装源

```
  npm i install -g nrm
  sudo ln -s /media/home/application/npm-global/bin/nrm /usr/local/bin/nrm
  nrm ls
  nrm use taobao

```

## 5. 开始安装vue-cli

```
  npm install -g @vue/cli
  sudo ln -s /media/home/application/npm-global/bin/vue /usr/local/bin/vue

```



## 相关链接
- [首页](https://zhishan33.github.io/shanBlog/)
- [Linux下Vue开发环境搭建一篇全搞定](https://blog.csdn.net/FormulaRoom/article/details/73920741)

> {{page.date | date: '%Y, %b %d' }}
