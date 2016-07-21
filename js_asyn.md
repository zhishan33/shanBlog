#js中ajax的异步执行与同步执行

@(笔记)[ajax]

##工作中的问题

>在循环之前给元素标记一种状态，然后执行循环体每一次循环都有一次**ajax**请求，循环结束之后恢复元素状态。

##参考了以下代码，复习了ajax同步异步编程知识

###代码块
<div id="output"></div>
<button onclick="updateSync ()">Run Sync</button>
<button onclick="updateAsync ()">Run Async</button>

function updateSync() {

    for (var i = 0; i < 1000; i++) {
        document.getElementById('output').innerHTML = i;
    }
    
}
function updateAsync() {

    var i = 0;
    function updateLater() {
        document.getElementById('output').innerHTML = (i++);
        if (i < 1000) {
            setTimeout(updateLater, 0);
        }
    }
    updateLater();
    
}

>由于js是单线程的所以运行updateSync函数导致UI更新被阻塞，setTimeout让updateLater函数异步执行，可以看到看到UI界面上从0到999快速地更新过程。

###代码块
function synchronizedCode() {

    var last = new Date().getTime();
    var count = 0;
    while (true) {
        var now = new Date().getTime();
        if (now - last > 1000 * 2) {
            last = now;
            count++;
            console.log('the '+count+'th count');
        }
        if (count > 5) {
            console.log('exist while.');
            break;
        }
    }
    
}

(function() {

    setTimeout(function() {console.log('setTimeout 0 occured first.');},0);
    setTimeout(function() {console.log('setTimeout 0 occured second.');},0);
    
    synchronizedCode();
    
})();

###输出结果
the 1th count.

the 2th count.

the 3th count.

the 4th count.

the 5th count.

exist while.

setTimeout 0 occured first.

setTimeout 0 occured second.

>使用setTimeout函数时，尽管延时为0，js的执行顺序还是发生了改变。







##参考文件
- [js中的异步执行时间探究](http://echizen.github.io/tech/2016/03-05-asynchronous)
- [JavaScript异步编程](https://software.intel.com/zh-cn/articles/asynchronized-javascript-programming)
- [js异步之惑](http://blog.whyun.com/posts/js/)
