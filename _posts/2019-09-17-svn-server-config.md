---
layout: default
title: svn server config
date: 2019-09-17 +0800
categories: svn
tags: [svn, config]
---

## svn server config

## svn服务器(https://sliksvn.com/download/)


### 创建svn仓库

```
   svnadmin create d:/svn/app/shop 
   
```

### 启动仓库

```

  svnserve.exe -d -r d:/svn/app

```

### 配置开启匿名账号(d:/svn/app/shop/svnserve.conf)

```

  before -> #anon-access = write
  after  -> anon-access = write

```

### 配置账号（d:/svn/app/shop/passwd）与权限(d:/svn/app/shop/authz)
* 关闭匿名账号


```
  d:/svn/app/shop/svnserve.conf
  
  before -> anon-access = write
  after  -> anon-access = none
  
  before -> #password-db = passwd
  after  -> password-db = passwd
  
  before -> #authz-db = authz
  after  -> authz-db = authz
  
  创建账号密码
  d:/svn/app/shop/passwd
  before -> [users]
            # harry = harryssecret
            # sally = sallysecret
            
  after  -> [users]
            # harry = harryssecret
            # sally = sallysecret
            zhangsan = zhangsan123
            lisi = lisi123
            
  
  设置账号权限   
  d:/svn/app/shop/authz
  
  before -> 
  
  after -> [shop:/]            #仓库
           zhangsan = rw       #读写 
           lisi = r            #读
           * =                 #其他人无权限
  
  设置工作组权限
  
  before -> [groups]
            # harry_and_sally = harry,sally
            # harry_sally_and_joe = harry,sally,&joe
            
  after -> [groups]
            # harry_and_sally = harry,sally
            # harry_sally_and_joe = harry,sally,&joe
            php = php1,php2,php3
  
  after -> [shop:/]            #仓库
           @php = rw           #工作组
  
```

### 开放限制目录权限

```
  设置账号权限   
  d:/svn/app/shop/authz
  
  before -> 
  
  after -> [shop:/model]       #仓库目录
           zhangsan = rw       #读写 
           lisi = r            #读
           * =                 #其他人无权限


```

### 开机启动svn服务

```

  sc create svnd binPath="d:/svn/server/bin/svnserve.exe -r d:/svn/app --service" start= auto

```

### 删除svn服务 *sc delete svnd*

### 同步文件到web服务器
* copy d:/svn/app/shop/hooks/post-commit.tmpl d:/svn/app/shop/hooks/post-commit.bat

> the post-commit.bat content is as follows

```
  SET SVN="D:/svn/server/bin/svn.exe"
  SET DIR="web server dir"
  (call %SVN% update %DIR% --username username --password pwd)
  
```



## 相关链接
- [首页](https://zhishan33.github.io/shanBlog/)

> {{page.date | date: '%Y, %b %d' }}
