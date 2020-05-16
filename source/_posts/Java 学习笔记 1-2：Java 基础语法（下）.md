---
title: Java 学习笔记 1-2：Java 基础语法（下）
author: Chic Cheung
tags:
  - Java
  - 学习路线
categories: Java
index_img: /img/3.jpg
banner_img: /img/3.jpg
abbrlink: 2ebd720
date: 2020-05-07 19:04:33
---



## 数组的定义和访问

### 容器和数组

容器：将多个数据存储到一起，每个数据称为该容器的元素

数组：存储数据长度固定的容器，数据类型必须一致。既可以存储基本数据类型，也可以存储引用数据类型。

### 数组的定义

- 方式一：

  ```java
  //数组存储的数据类型[] 数组名字 = new 数组存储的数据类型[长度]; 
  int[] arr = new int[3];
  ```

  数组定义格式详解： 

  - 数组存储的数据类型： 创建的数组容器可以存储什么数据类型。 

  - [] : 表示数组。 
  - 数组名字：为定义的数组起个变量名，满足标识符规范，可以使用名字操作数组。 
  - new：关键字，创建数组使用的关键字。 
  - 数组存储的数据类型： 创建的数组容器可以存储什么数据类型。 
  - [长度]：数组的长度，表示数组容器中可以存储多少个元素。 
  - 数组的长度一旦指定，不可更改。  

- 方式二：

  ```java
  //数据类型[] 数组名 = new 数据类型[]{元素1,元素2,元素3...}; 
  int[] arr = new int[]{1,2,3,4,5};
  ```

- 方式三：

  ```java
  //数据类型[] 数组名 = {元素1,元素2,元素3...}; 
  int[] arr = {1,2,3,4,5};
  ```

### 数组的访问

- 索引(index)： 每一个存储到数组的元素，都会获得一个从 `0` 开始的编号，这个编号称为索引。

- 数组的长度属性： 每个数组长度固定，获取到数组长度的语句为：`数组名.length`  ，返回值类型为 `int` 。

- 最大索引为 `数组名.length - 1` 。

- 数组元素的获取与赋值：

  ```java
  public static void main(String[] args) {
    
    //定义存储int类型数组，赋值元素1，2，3，4，5
    int[] arr = {1,2,3,4,5};
    
    //为0索引元素赋值为6
    arr[0] = 6;
    
    //获取数组0索引上的元素
    int i = arr[0];
    System.out.println(i);
    
    //直接输出数组0索引元素
    System.out.println(arr[0]);
  }
  ```

##  `JVM` 的内存划分

|  区域名称  |              作用               |
| :--------: | :-----------------------------: |
|   寄存器   |       提供给 `CPU` 来使用       |
| 本地方法栈 |  `JVM` 使用操作系统功能时使用   |
|   方法区   |    存储可以运行的字节码文件     |
|   堆内存   | 存储通过 `new` 创建的对象或数组 |
|   方法栈   |      方法运行时使用的内存       |

## 数组操作

*数组作为方法参数传递，传递的参数是数组内存的地址*

### 数组遍历

*数组遍历： 将数组中的每个元素分别获取出来*

```java
public static void main(String[] args) {
  int[] arr = { 1, 2, 3, 4, 5 };
  for (int i = 0; i < arr.length; i++){
    System.out.println(arr[i]);
  }
}
```

### 数组元素最大值

*从数组的所有元素中找出最大值*

```java
public static void main(String[] args) { 
  int[] arr = { 5, 15, 2000, 10000, 100, 4000 }; 
  
  //定义变量，保存数组中0索引的元素 
  int max = arr[0]; 
  
  //取出每个元素和 max 比较,大于 max 则记录
  for (int i = 0; i < arr.length; i++){
    if (arr[i] > max){
      max = arr[i]; 
    } 
  }
  System.out.println("数组最大值是： " + max); 
}
```

### 数组反转

*将数组中的元素颠倒顺序*

```java
public static void main(String[] args) { 
  
  int[] arr = { 1, 2, 3, 4, 5 }; 
  
  /*循环中定义变量min=0最小索引 
  max=arr.length‐1最大索引 
  min++,max‐‐ 
  */ 
  
  for(int min = 0, max = arr.length ‐ 1; 
      min <= max;
      min++, max‐‐){
    //利用第三方变量完成数组中的元素交换 
    int temp = arr[min]; 
    arr[min] = arr[max]; 
    arr[max] = temp; 
  }// 反转后，遍历数组 
  for (int i = 0; i < arr.length; i++) { 
    System.out.println(arr[i]); 
  } 
}
```



### 常见问题

- 数组索引越界 `ArrayIndexOutOfBoundsException`
  
  ```java
  public static void main(String[] args){
    int[] arr = {1,2,3};
    System.out.println(arr[3]);
  }
  ```
  
- 空指针异常 `NullPointerException`
  
  ```java
  public static void main(String[] args) {
    int[] arr = {1,2,3};
    arr = null;
    System.out.println(arr[0]);
  ｝
  ```

## 方法

*完成特定功能的代码块*

```java
修饰符 返回值类型 方法名(参数类型 参数名1，参数类型 参数名2…){
			函数主体代码;
			return 返回值;
}
```

写方法前需要考虑 返回值类型 和 参数列表 怎么写

### 方法重载

*在同一个类中，允许存在一个以上的同名方法，只要它们的参数个数或者参数类型不同即可。*

#### 特点

- 与返回值类型无关，只看方法名和参数列表
- 在调用时，JVM 通过参数列表的不同来区分同名方法

