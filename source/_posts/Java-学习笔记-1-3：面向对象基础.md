---
title: Java 学习笔记 1-3：面向对象基础
author: Chic Cheung
tags:
  - Java
  - 学习路线
categories: Java
index_img: /img/3.jpg
banner_img: /img/3.jpg
abbrlink: 6e8246c4
date: 2020-05-12 19:55:38
---

## 面向对象思想

### 概述

Java 语言是一种面向对象的程序设计语言，而面向对象思想是一种程序设计思想。 

这里的 **对象** 泛指现实中一切事物，每种事物都具备自己的 **属性** 和 **行为** 。面向对象思想就是在计算机程序设计过程中，参照现实中事物，将事物的属性特征、行为特征 **抽象** 出来，描述成计算机事件的设计思想。

它区别于面向过程思想，强调的是通过调用对象的行为来实现功能，而 **不是** 自己 **一步一步** 的去操作实现。

### 特性

面向对象的三大基本特征：封装、继承和多态。

## 类与对象

- 类：是一组相关属性和行为的集合。可以看成是一类事物的模板，使用事物的属性特征和行为特征来描述该 类事物。
- 对象：是一类事物的具体体现。对象是类的一个实例，必然具备该类事物的属性和行为。
- 关系：
  - 类是对一类事物的描述，是抽象的。 
  - 对象是一类事物的实例，是具体的。 
  - 类是对象的模板，对象是类的实体。

### 类的定义

- 现实世界的事物
  - 属性：事物的描述信息
  - 行为：事物能做什么

- Java 中的类
  - 成员变量：事物的属性
  - 成员方法：事物的行为

- 格式：

  ```java
  /*
  public class ClassName {
    //成员变量 
    //成员方法 
  }
  */
  public class Student{
    
    //成员变量
    String name； //姓名
    int age； //年龄
    
    //成员方法 
    
    //学习的方法 
    public void study() { 
      System.out.println("好好学习，天天向上"); 
    }
    
    //吃饭的方法 
    public void eat() { 
      System.out.println("学习饿了要吃饭"); 
    } 
  }
      
  ```

  

### 对象的使用

- 创建对象：`类名 对象名 = new 类名();`
- 访问成员变量：`对象名.成员变量;`
- 访问成员方法：`对象名.成员方法;`

### 成员变量的默认值

|          | <center>数据类型</center>>     | <center>默认值</center>> |
| :------: | :----------------------------- | :----------------------- |
| 基本类型 | 整数（byte，short，int，long） | 0                        |
|          | 浮点数（float，double）        | 0.0                      |
|          | 字符（char）                   | '\u0000'                 |
|          | 布尔（boolean）                | false                    |
| 引用类型 | 数组，类，接口                 | null                     |



## 封装

### 概述

面向对象编程语言是对客观世界的模拟，客观世界里成员变量都是隐藏在对象内部的，外界无法直接操作和修改。 封装可以被认为是一个保护屏障，防止该类的代码和数据被其他类随意访问。要访问该类的数据，必须通过指定的方式。适当的封装可以让代码更容易理解与维护，也加强了代码的安全性。

### 原则

将 **属性隐藏** 起来，若需要访问某个属性，提供 **公共方法** 对其访问。

### 步骤

-  使用 `private` 关键字来修饰成员变量
- 对需要访问的成员变量，提供对应的一对 `getXxx` 方法 、 `setXxx` 方法

### `private` 关键字

`private` 是一个权限修饰符，代表最小权限

可以修饰成员变量和成员方法

被修饰后的成员变量和成员方法，只在本类中才能访问。 

### `this` 的含义

`this` 代表所在类的当前对象的引用（地址值），即对象自己的引用。方法被谁在调用，``this` 就代表谁。

### 构造方法

当一个对象被创建时候，构造方法用来初始化该对象，给对象的成员变量赋初值。 

*无论你与否自定义构造方法，所有的类都有构造方法。*

Java 自动提供一个无参数构造方法， 一旦自己定义了构造方法，Java 自动提供的默认无参数构造方法就会失效。

#### 构造方法格式

```java
/*
修饰符 构造方法名(参数列表){ 
// 方法体 
}
*/

// 构造方法的写法上，方法名与它所在的类名相同。它没有返回值，所以不需要返回值类型，甚至不需要void。

public class Student { 
  
  private String name; 
  private int age; 
  
  // 无参数构造方法 
  public Student() {} 
  
  // 有参数构造方法 
  public Student(String name,int age) {
    this.name = name;
    this.age = age; 
  } 
}
```

## JavaBean——代码规范

`JavaBean` 是 Java 语言编写类的一种标准规范。符合 JavaBean 的类，要求类必须是具体的和公共的，并且具有无参数的构造方法，提供用来操作成员变量的 set 和 get 方法。

以学生类为例，标准代码如下：

```java
/*
public class ClassName{ 
//成员变量 
//构造方法 
//无参构造方法（必须）
//有参构造方法（建议）
//成员方法 
//getXxx() 
//setXxx() }
*/

public class Student {
  
  //成员变量 
  private String name; 
  private int age; 
  
  //构造方法 
  public Student() {} 
 
  public Student(String name,int age) {
    this.name = name; this.age = age; 
  }
  
  //成员方法 
  public void setName(String name) {
    this.name = name; 
  }
  
  public String getName() {
    return name; 
  }
  
  public void setAge(int age) { 
    this.age = age; 
  }
  
  public int getAge() {
    return age; 
  } 
}
```

测试类，代码如下：

```java
public class TestStudent { 
  public static void main(String[] args) { 
    
    //无参构造使用 
    Student s= new Student(); 
    s.setName("Sam"); 
    s.setAge(18);
    System.out.println(s.getName()+"‐‐‐"+s.getAge());
    
    //带参构造使用 
    Student s2= new Student("Lily",18);
    System.out.println(s2.getName()+"‐‐‐"+s2.getAge()); } }

```

