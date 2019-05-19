---
layout: default
title: Hbuilder autoprefixer
tags:[hbulider]
---
 

## Hbuilder autoprefixer 预编译

![autoprefixer config](/shanBlog/images/Hbuilder_autoprefixer.png)

### 尝试了好多次 -c config.json 都无效。最后只好修改插件的index.js（C:\Users\Administrator\AppData\Roaming\npm\node_modules\autoprefixer\node_modules\browserslist\index.js）文件的默认配置参数

```
	
	// Default browsers query
	//browserslist.defaults = [
	//    '> 1%',
	//    'last 2 versions',
	//    'Firefox ESR'
	//];
	
	// Default browsers query  from js
	browserslist.defaults = [
	    '> 0.5%',
	    'last 5 versions',
	//    'Firefox ESR'
	];

```


## 相关链接
- [HBuilder中Autoprefixer的配置方法](http://ask.dcloud.net.cn/article/691)

<p>{{ page.date | date_to_string }}</p>