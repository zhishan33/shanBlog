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

## add date(2019-10-21)

### 命令 --link **网络并入**

```bash
docker run -p 3306:3306 --name mymysql -v $PWD/conf:/etc/mysql/conf.d -v $PWD/logs:/logs -v $PWD/data:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=123456 -d mysql:5.6
docker run --name my-php -v E:/project/docker/nginx/www:/www -d php:5.6-fpm

docker run --name my-nginx-php -p 80:80 -d -v E:/project/nginx/www:/usr/share/nginx/html:ro -v E:/project/nginx/conf.d:/etc/nginx/conf.d:ro -v E:/project/nginx/logs:/logs:ro --link my-php:php nginx

docker run --name my-nginx-php -p 80:80 -d -v E:/project/docker/nginx/www:/usr/share/nginx/html:ro -v E:/project/docker/nginx/conf.d:/etc/nginx/conf.d:ro --link my-php:php nginx

docker run --name my-mysql-php -p 3306:3306 -d -v E:/project/mysql/conf:/etc/mysql -v E:/project/mysql/logs:/logs -v E:/project/mysql/data:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=root --link my-php mysql:5.6

docker run --name my-mysql-php -p 3306:3306 -d -v E:/project/docker/mysql/conf:/etc/mysql -v E:/project/docker/mysql/logs:/logs -v E:/project/docker/mysql/data:/var/lib/mysql -e MYSQL_ROOT_PASSWORD=root --link my-php mysql:5.6

docker run --name my-phpmyadmin -p 8080:80 --link my-mysql-php:db -d phpmyadmin/phpmyadmin:latest

docker run -d --name myadmin -e PMA_HOST=$(ip route show | grep docker0 | awk '{print $9}') -e PMA_PORT=3306 -p 8080:80 phpmyadmin/phpmyadmin

```

### 运行容器终端

```bash
docker exec -ti containerName /bin/bash
```

### 安装vim
1. apt-get update
2. apt-get install vim

## 相关链接

* [首页](https://zhishan33.github.io/shanBlog/)

> {{page.date | date: '%Y, %b %d' }}
