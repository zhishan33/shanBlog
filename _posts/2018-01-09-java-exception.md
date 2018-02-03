---
layout: default
title: java 基础 异常
---

# 异常分类

> 1、编译异常     2、运行异常

## 关键字

> 1、throw:用于抛出异常   2、throws： 用于声明异常

```
  class ChildException extends Exception {
    ChildException(){
    }
    ChildException(String name){
      super(name);
    }
  }
  
  class Demo throws ChildException {
    void func(){
      throw new ChildException();
    }
  }
  
  class RunDemo {
    public static void main(String[] args){
      Demo d = new Demo();
      
      try{
        d.func();
      } catch(ChildException e){
        e.getMessage();
      } catch(Exception oe){
        System.out.println("other exception");
      }
      
    }
  }
```

> 声明多个异常时，catch（Exception e）放最后；
            




## 相关链接
- [首页](http://zhishan33.github.io/shanBlog/)

<p>{{ page.date | date_to_string }}</p>

