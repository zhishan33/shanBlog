---
layout: default
title: webpack config
---
### Welcome webpack config

## package.json

```
{
	"scripts": {
		"dev": "webpack-dev-server --devtool eval --progress --colors --hot --content-base src/webpack_react/build --config webpackconfig/webpack_react.config.js"
	}
}

```

## 指令的意思

1. **webpack-dev-server**  在localhost:8080建立一个web服务器 
2. **--devtool eval** 为你的代码创建源地址。当有任何报错的时候可以让你更加精确地定位到文件和行号
3. **--progress** 显示合并代码进度
4. **--colors**  命令行中显示颜色！
5. **--content-base**  指向设置的输出目录
6. **--config** 指定配置文件

## 参考文件
- [介绍  React Webpack 小书](https://fakefish.github.io/react-webpack-cookbook/Running-a-workflow.html)
