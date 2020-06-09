---
layout: default
title: ubuntu In icon
date: 2020-06-03 +0800
categories: 
tags: [css, css3, notes]
---

## ubuntu 添加软链接和图标
### ubuntu 给微信开发工具添加软链接和图标

1. 创建软链接

```shell
sudo ln -s /home/home/devtools/wechat_web_devtools/bin/wxdt /usr/bin/wechat_web_devtools

```

2. 在/usr/share/applications/目录下，新建whecat_web_devtools.desktop文件

```shell
vim /usr/share/applications/whecat_web_devtools.desktop
```

3. 修改文件内容

```shell
   [Desktop Entry]
   Version=v1.02.1910121
   Type=Application
   Terminal=false
   Icon[en_US]=/home/home/devtools/wechat_web_devtools/wechat_web_devtools.png
   Name[en_US]=wechat_web_devtools
   Exec=/home/home/devtools/wechat_web_devtools/bin/wxdt
   Comment[en_US]=wechat_web_devtools
   Icon=/home/home/devtools/wechat_web_devtools/wechat_web_devtools.png
   Name=wechat_web_devtools
   Comment=wechat_web_devtools

```


## 相关链接

* [首页](https://zhishan33.github.io/shanBlog/)

> {{page.date | date: '%Y, %b %d' }}