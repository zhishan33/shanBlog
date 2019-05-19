---
layout: default
title: java 多线程
tags: [java]
---

# 创建多线程

> 方法1、继承Thread类     方法2、待续

## 继承

> 继承Thread类
1. 定义子类继承Thread类
2. 重写Thread类中的run方法，在run中定义要运行的代码
3. 通过Thread子类创建线程
4. 调用子类的start方法启动并运行线程（jvm会自动执行run）

```

  class ChildThread extends Thread {
    private String name;
    ChildThread(String name){
      this.name = name;
    }

    public void run(){
      for(int i=0; i<10; i++){
        System.out.println(name+"******i="i);
      }
    }

  }

  class DemoThread {
    public static void main(String[] args){
      ChildThread childThread1 = new ChildThread("子线程1")；
      ChildThread childThread2 = new ChildThread("子线程2")；

      childThread1.start();
      childThread2.start();
    }
  }

```


## 相关链接
- [首页](http://zhishan33.github.io/shanBlog/)

<p>{{ page.date | date_to_string }}</p>

