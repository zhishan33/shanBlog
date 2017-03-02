---
layout: default
title: iscroll notes
---
## 添加和移除默认事件

### e.preventDefault()



```
	<script>
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
		
		Loaded();
		
	</script>
```

## 异步加载

### myScroll.refresh();

<p>{{ page.date | date_to_string }}</p>