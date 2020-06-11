---
layout: default
title: ubuntu 开机挂在硬盘
date: 2020-06-11 +0800
categories:
tags: [ubuntu, mount, disk, notes]
---

## ubuntu 开机挂载硬盘

1. 创建虚拟目录

```shell
  sudo mkdir /media/wins/diskE
```

2. 查看要挂载的硬盘的UUID和type

```shell
sudo blkid
```

3. 编辑/etc/fstab文件**在文件最后一行添加UUID=0E12A07812A06705 /media/home/apps               ntfs    errors=defaults 0       0**
> UUID和tpye换上然后在/后面加上**要挂载路径**，把errors=remount-ro改为defaults，后面的1改0

```shell
sudo gedit /etc/fstab
UUID=0E12A07812A06705 /media/home/apps               ntfs    errors=defaults 0       0
```

## 相关链接

- [首页](https://zhishan33.github.io/shanBlog/)

> {{page.date | date: '%Y, %b %d' }}