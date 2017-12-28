---
layout: default
title: java 基础 继承 接口
---

# extends

> 实例化对象的过程中 首先运行类的构造方法，存在父类的情况下，在子类的构造方法中首先运行父类的构造方法。

```
  class parent {
    void test(){}
    void test2(){}
  }
  class demo extends parent {
    public static String = "static";
    demo(){
      super()
    }
  }
  

```



# abstract class, interface

> 抽象类中既可以有抽象方法也可以有非抽象方法，而接口中只能用抽象方法，接口可以实现多继承，而类只能单继承

```
  abstract class demo {
    
    void test {
    
    }
    
    abstract void test2{
    
    }
  }
  
  interface Demo1 {
    abstract void fun1(){}
    abstract void fun2(){}
  }
  interface Demo2 {
    abstract void func3(){}
  }
   
  class child extends demo implements Demo1,Demo2 {
     void fun1(){}
     void fun2(){}
     void fun3(){}
  }

```









## 相关链接
- [note](http://zhishan33.github.io/shanBlog/)

<p>{{ page.date | date_to_string }}</p>

