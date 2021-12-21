---
layout: default
title: svn ignore
date: 2020-11-07 +0800
categories:
tags: [svn, notes]
---

## svn ignore 的用法（忽略文件及目录）

若想创建了一个文件夹，并且把它加入版本控制，但忽略文件夹中的所有文件的内容：

𝑠𝑣𝑛𝑚𝑘𝑑𝑖𝑟𝑠𝑝𝑜𝑜𝑙 svn propset svn:ignore '*' spool
$ svn ci -m 'Adding "spool" and ignoring its contents.'

若想创建一个文件夹，但不加入版本控制，即忽略这个文件夹：

𝑚𝑘𝑑𝑖𝑟𝑠𝑝𝑜𝑜𝑙 svn propset svn:ignore 'spool' .
$ svn ci -m 'Ignoring a directory called "spool".'

若已经创建了文件夹，并加入了版本控制，现在想忽略这个文件夹，但要保持文件夹的内容：

𝑠𝑣𝑛𝑒𝑥𝑝𝑜𝑟𝑡𝑠𝑝𝑜𝑜𝑙𝑠𝑝𝑜𝑜𝑙−𝑡𝑚𝑝 svn rm spool
𝑠𝑣𝑛𝑐𝑖−𝑚′𝑅𝑒𝑚𝑜𝑣𝑖𝑛𝑔𝑖𝑛𝑎𝑑𝑣𝑒𝑟𝑡𝑒𝑛𝑡𝑙𝑦𝑎𝑑𝑑𝑒𝑑𝑑𝑖𝑟𝑒𝑐𝑡𝑜𝑟𝑦"𝑠𝑝𝑜𝑜𝑙".′ mv spool-tmp spool

```shell

 svn propset svn:ignore 'spool' .

 svn ci -m 'Ignoring a directory called "spool".'
```
 >

如果想在SVN提交时，忽略某个文件，也就是某个文件不提交，可以使用

svn propedit svn:ignore命令。

下面详细介绍一下使用步骤。

单纯的看svn官方文档和一些网上搜索的资料，有时候真的不如亲自试验的好。

svn propedit svn:ignore 目录名称。

注意，在使用这个SVN的属性编辑前，你得确保后面的“目录名称”是SVN版本控制的目录。

如果要忽略此目录下的文件，可以如下操作。

比如，想忽略/product目录下的test.php文件。前提是/product目录必须在svn版本控制下，而test.php文件不在svn版本控制。

svn st先看一下状态，会显示如下：

?     /product/test.php

我们需要将test.php文件加入忽略列表。

此时先设置SVN默认的编辑器

export SVN_EDITOR=vim

然后，使用svn propedit svn:ignore ,用法如下

svn propedit svn:ignore /product

此时会出现一个VIM的编辑窗口，表示需要将某个文件加入到忽略列表里

我们在编辑窗口中，写入

test.php

然后保存，并退出VIM编辑器。

这时候会有一个提示：属性 “svn:ignore” 于 “product” 被设为新值。

表示文件test.php的svn:ignore属性设置成功。

然后使用svn st查看，会显示：

M        product

我们需要提交，然后这个svn:ignore属性才会起作用

svn ci -m '忽略test.php文件'

这时候，无论你如何修改test.php文件，再使用svn st时，也不会出现修改提示符合M了。

### 递归恢复文件夹

> svn revert --depth infinity '.git'

## 相关链接

- [svn ignore 的用法（忽略文件及目录）](https://www.cnblogs.com/lixiuran/p/11817178.html)
- [首页](https://zhishan33.github.io/shanBlog/)

> {{page.date | date: '%Y, %b %d' }}
