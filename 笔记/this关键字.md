# this

1. this是一个关键字，是一个引用，保存内存地址指向自身（类似Python中的self）是一个特殊变量，存在于对象内部,**在堆内存中**
2. this可以使用在实例方法中，也可以使用在构造方法中
3. this在实例方法中其实代表的是当前对象。
4. this不能使用在静态方法中（类似python 中@staticmethod的函数不能传入self）
5. this在区分局部变量和实例变量的术后不能省略，其他时候编译器自动添加this
6. this() 这种语法只能出现在构造方法第一行，表示当前构造方法调用本类其他的构造方法，目的代码复用

```java
// 练习题
/**
*定义一个日期类，表示年月日信息。
* 要求：调用无参构造方法，默认创建日期是1970年1月1日，调用有参构造方法创建参数的日期对象
*/
```

```java
// 对象类
package com.kuang.work;

public class CreateDateTime {
    int year = 1970;
    int month = 1;
    int day = 1;

    public CreateDateTime() {

    }

    public CreateDateTime(int year,int month,int day){
        this.year = year;
        this.month = month;
        this.day = day;

    }
}

```

```java
// 创建对象
package com.kuang.work;

public class DateTime {
    public static void main(String[] args) {
        CreateDateTime cd = new CreateDateTime();
        CreateDateTime cd2 = new CreateDateTime(2022,12,30);
        System.out.println(cd.year+"."+ cd.month+"."+ cd.day);
        System.out.println(cd2.year+"."+ cd2.month+"."+ cd2.day);
    }
}

```

