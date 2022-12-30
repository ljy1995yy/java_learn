# JAVA

### java三种平台

```tex
Java语言：完全面向对象（java语言底层实际上是C++实现的。）
Java被分为三大块：
	J2SE：标准版（基础，要学java，必须先学习SE。基础
	语法+基础库）
	J2EE：企业版（专门为企业开发软件，为企业提供解决方案。
	例如：OA办公系统，保险行业的系统，金融行业的系统，
	医院系统....）
	J2ME：微型版（专门为微型设备做嵌入式开发的。）

```

### JDK/JRE/JVM的关系

```tex
JDK：Java开发工具箱
JRE：Java运行环境
JVM：Java虚拟机
JDK包括JRE，JRE包括JVM
JVM是不能独立安装的。JDK和JRE都是可以独立安装的。
安装JDK的时候：JRE就自动安装了，同时JRE内部的JVM
也就自动安装了。
```

### java的执行步骤

```tex
编写/编译/解释,编译期间检查Java语法,
如果出现错误,则不会产生类文件,
解释期间则将类文件装进JVM中,解释成二进制文件,然
后机器才能识别运行.
```



环境：jdk 1.8.0-21

ide:idea

使用流程

文件名 Hello.java

```java
public class Hello{
    public static void main(String[] args){
        System.out.println("Hello");
    }
}
```

```\
执行流程
$javas Hello.java
$java Hello
```

Java的一个类

类是java执行的最小单元

java执行至少需要一个类



## idea的使用

File -> new -> project -java

生成.idea与src文件

在src中创建java文件，什么文件名自动生成什么名字的函数

```java
public class Hello {
    public static void main(String[] args) {
        System.out.println("你好啊"); // 这是打印语句
    }
}
```

### 自动生成代码

```/
psvm -> main
sout ->  System.out.println("")  
注意需要""
```

### 注释代码

```java
// 单行注释
/* 
多行注释
*/
/**
* 文档注释
*/
```

