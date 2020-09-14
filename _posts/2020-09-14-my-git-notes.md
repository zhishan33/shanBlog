---
layout: default
title: git 冲突解决
date: 2020-09-14 +0800
categories:
tags: [git, notes]
---

## git pull

1. git fetch 从远程获取最新版本到本地，不会自动合并分支
2. git rebase 重新定义起点
3. git pull 的默认行为是 git fetch + git merge
4. git pull --rebase 的默认行为是 git fetch + git rebase

## 执行完 git pull --rebase 之后如果有合并冲突

1. git rebase --abort 会放弃合并，回到 rebase 操作之前的状态，之前的提交的不会丢弃；
2. 使用 \$git rebase --continue
   > 本地如果产生冲突，手动解决冲突之后，用"git add"命令去更新这些内容的索引(index)，然后只要执行: git rebase --continue 就可以线性的连接本地分支与远程分支，无误之后就回退出，回到主分支上。

## 相关链接

- [git 的突出解决--git rebase 之 abort、continue、skip](https://www.cnblogs.com/chenjunjie12321/p/6876220.html)
- [首页](https://zhishan33.github.io/shanBlog/)

> {{page.date | date: '%Y, %b %d' }}
