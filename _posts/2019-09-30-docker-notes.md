---
layout: default
title: docker notes
date: 2019-09-30 +0800
categories: docker
tags: [poweroff, notes]
---

## docker notes

### 常见命令

```bash
#!/bin/bash
#查看镜像
docker images
docker ps -a
docker ps -l
docker start
docker stop
docker restart
docker rm (container-name|container-id)
docker inspect (container-name|container-id)

```

### 创建数据卷(win10)

> Docker Desttop -> setting -> Shared Drives e:

```bash
docker run -d -p 8088:80 --name my-nginx -v E:/project/nginx/www:/usr/share/nginx/html -v E:/project/nginx/conf/nginx.conf:/etc/nginx/nginx.conf -v E:/project/nginx/logs:/var/log/nginx nginx
```

### 构建本地镜像

1. 新建**Dockerfile**文件
2. 构建镜像
3. 创建容器

```Dockerfile
FORM nginx
COPY ./www/index.html /usr/share/nginx/html/index.html
EXPOSE 80

```

```bash
docker build -t my-nginx .
```

```bash
docker run -d --rm -p 4445:80 my-nginx
```

## 相关链接

* [首页](https://zhishan33.github.io/shanBlog/)

> {{page.date | date: '%Y, %b %d' }}
