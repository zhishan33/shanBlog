---
layout: default
title: iscroll notes
tags: [other]
---
## 添加和移除默认事件

### e.preventDefault()



```
	<script>
		/*
		 * 默认事件函数函数表达式
		 */
		var preEvent = function(e){e.preventDefault();}
		
		var myScroll;
        function Loaded() {
            myScroll = new IScroll('#wrapper', {
                mouseWheel: true,
                snap: true, //执行传送带效果
                click: true,
                taps: true
            });
        }
		document.addEventListener('touchmove', preEvent, false);
		/*
		 * 数据成功后，调用方法。
		 */
		
		Loaded();
		
		/*
		 * 退出后，移除监听事件，清楚内存占用。
		 */
		
		document.removeEventListener('touchmove', preEvent, false);
		myScroll = null;
	</script>
```

## 异步加载

### myScroll.refresh();

## css3 

```
	<style type="text/css">
		#Wrapper {
			touch-action:none;
		}
	</style>
```

## 相关链接
- [iScroll 5 API 中文版](https://iiunknown.gitbooks.io/iscroll-5-api-cn/content/)

<p>{{ page.date | date_to_string }}</p>