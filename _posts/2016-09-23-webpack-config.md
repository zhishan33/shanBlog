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

### devServer

```

module.exports = {
	devServer: {
		contentBase:"../dist/webpack_react/build",
		colors:true,
		inline:true,
		hot:true,
		historyApiFallback:true	
	},
	plugins:[
		new webpack.HotModuleReplacementPlugin() //热加载插件
	],
	module:{
		loaders:[
			{
				test:'/.js$/',
				loader:'babel',
				exclude: /node_modules/,
				query:{
					presets:['es2015','react']
				}
			},
			{test:'/.scss$/',loader:'style!css!sass'},
			{test:'/.(png|jpg|jpeg)/',loader:'url?limit=8192'}
		]
	}
}

```

## 指令的意思

1. **webpack-dev-server**  在localhost:8080建立一个web服务器 
2. **--devtool eval** 为你的代码创建源地址。当有任何报错的时候可以让你更加精确地定位到文件和行号
3. **--progress** 显示合并代码进度
4. **--colors**  命令行中显示颜色！
5. **--content-base**  指向设置的输出目录,默认webpack-dev-server会为根文件夹提供本地服务器，如果想为另外一个目录下的文件提供本地服务器，应该在这里设置其所在目录
6. **--config** 指定配置文件
7. **--inline** 设置为true，当源文件改变时会自动刷新页面
8. **--hot** 实现功能热加载。(plugins)

## loaders 

- **test：**一个匹配loaders所处理的文件的拓展名的正则表达式（必须）
- **loader：**loader的名称（必须）
- **include/exclude:**手动添加必须处理的文件（文件夹）或屏蔽不需要处理的文件（文件夹）（可选）；
- **query：**为loaders提供额外的设置选项（可选）


## 参考文件
- [介绍  React Webpack 小书](https://fakefish.github.io/react-webpack-cookbook/Running-a-workflow.html)
- [入门Webpack，看这篇就够了](http://blog.csdn.net/kun5706947/article/details/52596766)
