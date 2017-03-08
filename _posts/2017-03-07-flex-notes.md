---
layout: default
title: flex notes
---
 

## flex 老语法（只涉及webkit内核浏览器）

```
	<style type="text/css">
	
		/*
		 * 定义容器
		 */
		.flexbox {
			
			display:-webkit-box;
			display:box;
		
		}
		/*
		 *  定义子元素主轴对齐方式
		 *	box-pack: start | end | center | justify;
    	 *	 主轴对齐：左对齐（默认） | 右对齐 | 居中对齐 | 左右对齐
		 */
		.flexbox{
		    -webkit-box-pack: justify;
		    box-pack: justify;
		}
		
		/*
		 * 定义子元素交叉轴对齐方式
		 * box-align: start | end | center | baseline | stretch;
    	 * 交叉轴对齐: 顶部对齐（默认） | 底部对齐 | 居中对齐 | 文本基线对齐 | 上下对齐并铺满
		 */
		.flexbox{
		    -webkit-box-align: center;
		    box-align: center;
		}
	</style>
```

## flex 新语法 （只涉及webkit内核浏览器）

```
	<style type="text/css">
		/*
		 * 定义容器
		 */
		.flexbox {
			display:-webkit-flex;
			display:flex;
		}
		/*
		 *  定义子元素主轴对齐方式
		 *justify-content: flex-start | flex-end | center | space-between | space-around;
    	 *    主轴对齐方式：左对齐（默认） | 右对齐 | 居中对齐 | 两端对齐 | 平均分布
		 */
		.flexbox{
		    -webkit-justify-content: space-between;
		    justify-content: space-between;
		}
		
		/*
		 * 定义子元素交叉轴对齐方式
		 *  align-items: flex-start | flex-end | center | baseline | stretch;
    	 *交叉轴对齐方式：顶部对齐（默认） | 底部对齐 | 居中对齐 | 上下对齐并铺满 | 文本基线对齐
		 *
		 */
		.flexbox{
		    -webkit-align-items: center;
		    align-items: center;
		}
	</style>
```

## flex 兼容写法（只涉及webkit内核浏览器）

```
	<style type="text/css">
		.flexbox {
			display:-webkit-flex;
			display:flex;
			-webkit-box-pack: end;
		    box-pack: end;
		    -webkit-justify-content: flex-end;
		    justify-content: flex-end;
		    -webkit-box-align: center;
		    box-align: center;
		    -webkit-align-items: center;
		    align-items: center;
		}
	</style>
```

## flex 兼容写法部分浏览器（如支付宝内置UC）需要子元素是的块级元素，如果不是就要手动设置为块级元素；

## 相关链接
- [Flex布局新旧混合写法详解（兼容微信）](https://segmentfault.com/a/1190000003978624)

<p>{{ page.date | date_to_string }}</p>