satic

关键字是静态的意思

可以修饰成员方法

可以修饰成员变量



static修饰的特点：

- 被类的所有对象共享
- 可以通过类名调用
  - 建议使用  类.属性  进行赋值

static访问特点

非静态的成员方法

- 能访问静态的成员变量
- 能访问非静态的成员变量
- 能访问静态的成员方法
- 能访问非静态的成员方法

```java
// 非静态成员变量
    private int age = 20;
    // 静态成员变量
    public static String un ;

    // 非静态成员方法
    public void show1(){
        System.out.println(un);
        System.out.println(age);
        show2();
        show3();
    }
```

静态的成员方法

- 能访问静态的成员方法
- 能访问静态的成员变量
- 总结： 静态的成员方法只能访问静态的成员变量

```java
 // 非静态成员变量
    private int age = 20;
    // 静态成员变量
    public static String un;
// 非静态的成员方法
 	public void show2(){}
    // 静态成员方法
    protected static void show3(){}
    public static void show4(){
        System.out.println(un);
//        System.out.println(age);  // 报错
//        show2();  // 报错
        show3();
    
```

想要访问非静态的成员与方法需要new一个类对象

```java
Fu f = new Fu();
System.out.println(f,age);
f.show2()
```

