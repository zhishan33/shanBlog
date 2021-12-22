---
layout: default
title: git cherry-pick | git stash
date: 2021-12-22 +0800
categories:
tags: [git, notes]
---

## git cherry-pick

```git
git cherry-pick dev-pay
```

上面代码表示将dev-pay分支的最近一次提交，转移到当前分支。

```git
git cherry-pick <commitHash>
```

上面代码表示将**commitHash**提交，转移到当前分支。

```git
git cherry-pick <HashA>^..<HashB>
```

上面代码表示将转移一系列的连续提交(包含提交 HashA)，转移到当前分支。

## git stash (工作流被打断,需要先做别的需求)

```git
git stash save "save msg"

```

上面代码表示：存储当前未提交的文件，并添加备注。

```git
git stash show
```

上面代码表示：显示做了哪些改动，默认show第一个存储。

```git
git stash pop
```

上面代码表示：恢复之前存储的工作目录，将存储堆栈中的对应stash删除。

## 相关链接

- [git cherry-pick 教程](https://ruanyifeng.com/blog/2020/04/git-cherry-pick.html)
- [首页](https://zhishan33.github.io/shanBlog/)

> {{page.date | date: '%Y, %b %d'}}
> 