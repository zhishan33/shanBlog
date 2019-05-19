---
layout: default
title: css 通用设置
date: 2019-05-18 +0800
categories: css
tags: [css, css3]
---

# CSS 通用设置

## 1. 移动端

1. 视网膜屏下的像素设置（1px 像素问题）
   {% highlight ruby %}
     <style>
       .border {border: 1px solid #999;}
       @media screen and (min-device-pixel-ratio:1.5){
         //.border {border: 0.7px solid #999;}
         .border {transform:scaleY(0.7);}
       }
       @media screen and (min-device-pixel-ratio:2){
         //.border {border: 0.5px solid #999;}
         .border {transform:scaleY(0.5);}
       }
       @media screen and (min-device-pixel-ratio:3){
         //.border {border: 0.33333px solid #999;}
         .border {transform:scaleY(0.33333);}
       }
     </style>

{% endhighlight %}

- 从 nodejs 官网(https://nodejs.org/en/download/)下载 Linux Binaries (x64)源代码
- 解压 node 源代码包

```

  tar -xvf node-v10.15.3-linux-x64.tar.xz -C /media/home/application/

```

## 2. 建立软连接

```

   sudo ln -s /media/home/application/node-v10.15.3-linux-x64/bin/node /usr/local/bin/node
   sudo ln -s /media/home/application/node-v10.15.3-linux-x64/bin/npm /usr/local/bin/npm


```

## 3. 修改 npm 安装包默认目录

```

  npm config set prefix="/media/home/application/npm-global"
  npm config set cache="/media/home/application/npm-cache"

```

## 4. 安装 nrm

{% highlight ruby %}

- 创建 nrm 软连接

* 利用 nrm 查看 npm 安装源
* 切换 npm 安装源
  {% endhighlight %}

```
  npm i install -g nrm
  sudo ln -s /media/home/application/npm-global/bin/nrm /usr/local/bin/nrm
  nrm ls
  nrm use taobao

```

## 5. 开始安装 vue-cli

```

  npm install -g @vue/cli
  sudo ln -s /media/home/application/npm-global/bin/vue /usr/local/bin/vue

```

## 相关链接

<!-- - [首页](https://zhishan33.github.io/shanBlog/) -->

- [首页]({{ site.baseurl }}/)
- [Linux 下 Vue 开发环境搭建一篇全搞定](https://blog.csdn.net/FormulaRoom/article/details/73920741)

> {{page.date | date: '%Y, %b %d' }}
