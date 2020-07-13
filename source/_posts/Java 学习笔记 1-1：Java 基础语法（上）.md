---
title: Java 学习笔记 1-1：Java 基础语法（上）
author: Chic Cheung
tags:
  - Java
  - 学习路线
categories: Java
index_img: /img/3.jpg
banner_img: /img/3.jpg
abbrlink: fef6955d
date: 2020-05-03 12:26:03
---



## 历史背景

- Java 之父 —— James Gosling
- 1995 年 Sun 公司发布 Java1.0 版本
- 1997 年发布 Java 1.1 版本
- 1998 年发布 Java 1.2 版本
- 2000 年发布Java 1.3 版本
- 2002 年发布 Java 1.4 版本
- 2004 年发布 Java 1.5 版本
- 2006 年发布 Java 1.6 版本
- 2009 年 Oracle 甲骨文公司收购 Sun 公司
- 2011 年发布 Java 1.7 版本
- 2014 年发布 Java 1.8 版本
- 2017 年发布 Java 9.0 版本
- 2018 年发布 Java 10.0 版本
- 2018 年发布 Java 11.0 版本
- 截至 2020 年，最新的长期支持版本为 Java 11.0
- Java 语言平台包括：
  - Java SE：桌面端开发
  - Java ME：移动端开发（被 Android 替代）
  - Jave EE：企业级开发	



## 计算机基础

### 二进制

*计算机中全部采用二进制数表示，它只包含 0、1两个数，逢二进一。每一个0或者每一个1，叫做一个bit（比特）。*

- **十进制转二进制：**辗转相除法/除二取余法

  ![111](https://gitee.com/chiccheung/uPic/raw/master/uPic/111.jpg)



- **二进制转十进制：**各位数字累加求和（8421 编码）

  ![112](https://gitee.com/chiccheung/uPic/raw/master/uPic/112.jpg)

### 字节 / Byte

*计算机内的最小存储单元*

8个bit（二进制位） 0000-0000表示为1个字节，写成 1 byte 或者 1 B

- 8 bit  =  1 Byte
- 1024 B = 1 KB
- 1024 KB = 1 MB
- 1024 MB = 1 GB
- 1024 GB = 1 TB

### 常用 DOS 命令

| <center>**命令**</center> | <center>**操作**</center> |
| :------: | :------------------: |
|   `C:`   |      切换 C 盘       |
|  `dir`   | 列出当前目录下的文件 |
|   `cd`   |      进入文件夹      |
| `cd ..`  |    退回上一级目录    |
|  `cd \`  |     移动到根目录     |
|  `cls`   |         清屏         |



## 开发环境

### JRE & JDK

- JRE 包括：JVM（Java 虚拟机）、核心类库

- JDK 包括：JRE ，开发工具

- 运行 Java 程序可安装 JRE/JDK，开发需要安装 JDK

### 跨平台性

- 所谓跨平台性，即一次编写，到处运行

- Java 源码经过编译，会生成 `.class` 后缀的字节码文件，再经过 JVM 翻译为机器码供机器运行

- 各操作系统均存在相应版本的 JVM，因此 Java 具有良好的跨平台性和可移植性

  ![113](https://gitee.com/chiccheung/uPic/raw/master/uPic/113.jpg)

### Open JDK & Oracle JDK

- 部分 Oracle JDK 未开源的代码，由 Open JDK 重新编写

### OpenJDK 两种安装方式：

- [IntelliJ IDEA](https://www.jetbrains.com/idea/) 可在创建项目时下载 [OpenJDK](https://openjdk.java.net)

- 在 macOS 下，可以使用 [Homebrew](https://brew.sh) 安装 [OpenJDK](https://openjdk.java.net)，命令如下：

  `brew install openjdk`



## 入门程序

### Hello World

```java
// 打印 Hello World！语句 
public calss HelloWorld{
  public static void main(String[] args){
    System.out.println("Hello World!\n");
  }
}
```

*`main` 方法是程序执行的起点*

- **编译**：将 Java 源文件编译成 `.class` 后缀文件，在此过程中， 编译器会检查是否有语法上的错误。 
- **运行**：将 `.class` 文件交给 JVM，翻译为机器码并执行。
- **注释：为代码增加可读性**
  - 单行注释：以 `//` 开头，换行结束
  - 多行注释：以 `/*` 开头，  `*/` 结束 
  - 文档注释：以 `/**` 开头， `*/` 结束

- 编译命令：`javac Java源文件名.后缀名` 

  例：`javac HelloWorld.java`

- 运行命令：`java 类名`

  例：`java HelloWorld`



## 关键字

*Java 预先定义的标识符，具有特殊含义*

## 标识符

*用于标识 包，类，方法，变量*

### 命名规则：

- 可以包含字母，数字，美元符号和下划线。 

- 不能以数字开头。

- 不能是关键字。

### 命名规范：

- 类名：首字母大写，后面每个单词首字母大写（大驼峰式）；

- 方法名： 首字母小写，后面每个单词首字母大写（小驼峰式）；

- 变量名：全部小写。

## 常量

分为：整数常量，小数常量，字符常量（单引号，一个字符，必须有内容)，字符串常量（双引号，可以为空），布尔常量，空常量（null）。

![114](https://gitee.com/chiccheung/uPic/raw/master/uPic/114.jpg)

## 变量

*变量名称：在同一个大括号范围内，变量的名字不可以相同*

*变量赋值：定义的变量，不赋值不能使用*

**基本数据类型**：包括整型，浮点型，字符型，布尔型。

**引用数据类型**：包括类，数组，接口。

| **数据类型** | **关键字**     | 占用字节数 | **取值范围**          |
| ------------ | -------------- | ---------- | --------------------- |
| 字节型       | byte           | 1          | -128~127              |
| 短整型       | short          | 2          | -32768~32767          |
| 整型         | int（默认）    | 4          | -(2^31)~2^(31-1)      |
| 长整型       | long           | 8          | -(2^63)~2^(63-1)      |
| 单精度浮点数 | float          | 4          | 1.4013E-45~3.4028E+38 |
| 双精度浮点数 | double（默认） | 8          | 4.9E-324~1.7977E+308  |
| 字符型       | char           | 2          | 0-65535               |
| 布尔型       | boolean        | 1          | true，false           |

*long类型：建议数据后加 L。*

*float类型：建议数据后加 F。*



**语法**：数据类型 变量名 = 数据值; 

如： `int num = 0;`

## 类型转换

*自动转换是 Java 自动执行的，而显示转换需要我们自己手动执行*



隐式转换：byte、short、char - int - long - float - double

显示转换：`数据类型 变量名 = （数据类型）被转数据值；`



## ASCII 编码表



*编码表 ：就是将人类的文字和一个十进制数进行对应起来组成一张表格。*

*ASCII 编码表（ American Standard Code for Information Interchange 美国标准信息交换码）*



| 字符 | 数字 |
| :--: | :--: |
|  0   |  48  |
|  9   |  57  |
|  a   |  65  |
|  z   |  90  |
|  A   |  97  |
|  Z   | 122  |



## 运算符

*对常量和变量进行操作的符号称为运算符*

- 算术运算符：`+，-，*，/，%，++，--`
  - *整数相除只能得到整数，要想得到小数，就必须有浮点数参与运算*
  - *模运算 `%` 常用来判断一个数是否可以被另一个数整除*
  - *`++` 和 `--` 在前面时，如： `int count = ++i;` `i` 先自增 `1` ，再被赋值给 `count`，在后面时，先被赋值，再自增*
  - 对字符串使用 `+` ，做的不是加法运算，而是字符串拼接。
  - 字符串和其他类型的数据做拼接，得到的是字符串类型。
- 赋值运算符：`=，+=，-=，*=，/=，%=`
- 关系运算符：`==，!=，>，>=，<，<=`
- 逻辑运算符：`	&，|，^，!，&&，|| `
  - *`&&` 和 `&`的最终结果一样。但 `&&` 具有短路效果。*
  - *`||` 和 `|` 同理。*
- 三元运算符
  - 例： `int choice = (a==b)?30:40;`
  - 如果 `a==b` 为 `true`，`choice` 是 `30`
  - 如果 `a==b` 为 `false`，`choice` 是 `40`

## 接收输入：Scanner

- 导包
  - `import java.util.Scanner;`
- 创建对象
  - `Scanner sc = new Scanner(System.in);`
- 接收数据
  - `int num = sc.nextInt();`

## 流程控制

- 顺序执行：从上到下，逐行执行

  ```java
  public static void main(String[] args){
    //顺序执行，根据编写的顺序，从上到下运行 
    System.out.println(1); 
    System.out.println(2); 
    System.out.println(3);
  }
  ```

- 判断执行：

  - if 语句

    ```java
    if(判断条件1){
      执行语句1;
    } else if(判断条件2){
      执行语句2;
    }
    ...
    else if(判断条件n){
      执行语句n;
    }else{
      执行语句n+1;
    } 
    ```
  
  - switch 语句

    *表达式的数据类型，可以是byte，short，int，char，enum（枚举），JDK7后可以接收字符串*

    ```java
    public static void main(String[] args){
      //定义变量，判断是星期几
      int weekday = 6; 
      //switch语句实现选择 
      switch(weekday) {
        case 1:
          System.out.println("星期一"); 
          break;
        case 2:
          System.out.println("星期二"); 
          break;
        case 3:
          System.out.println("星期三");
          break;
        case 4:
          System.out.println("星期四");
          break;
        case 5:
          System.out.println("星期五");
          break;
        case 6:
          System.out.println("星期六");
          break;
        case 7:
          System.out.println("星期日");
          break;
        default:
          System.out.println("你输入的数字有误");
          break;
      }
    }
    ```

- 循环执行：

  - for 循环

    ```java
    /*
    for(初始化表达式①; 布尔表达式②; 步进表达式④){
      循环体③
    }
    */
    for(int x = 0; x < 10; x++) {
      System.out.println("HelloWorld"+x);
    }
    ```

  - while 循环

    ```java
    /*
    初始化表达式① 
    while(布尔表达式②){
      循环体③
      步进表达式④
    }
    */
    public static void main(String[] args){
      //打印 10 次 HelloWorld
      
      //定义初始化变量
      int i = 1;
      
      //循环条件 <= 10
      while(i<=10{
        System.out.println("HelloWorld"); 
        //步进
        i++;
      }
    }
    ```

  - do-while 循环

    ```java
    /*
    初始化表达式① 
    do{
    循环体③ 步进表达式④
    }while(布尔表达式②);
    */
    public static void main(String[] args) { 
      int x=1;
      do{
        System.out.println("HelloWorld");
        x++;
      }while(x<=10);
    }
    ```

    

- 跳转控制：

  - continue 语句结束本次循环，继续下一次的循环
  - break 语句：终止switch或者循环

- 其他循环：

  - 死循环：没有步进语句或跳出语句
  - 嵌套循环：循环内再循环，如二维数组遍历

## 随机数生成：Random

- 导包
  - `import java.util.Random;`
- 创建对象
  - `Random r = new Random();`
- 产生 0~10 范围内的随机整数
  - `int rand_num = r.nextInt(10);`

