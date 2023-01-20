# ‘==’操作符

对于数值类型的数据进行比较时，使用==

```java
"adsdsaw"=="adsdsaw"if(1==3);
// 返回false
if("adsdsaw"=="adsdsaw")
// 返回true
```

对于引用的对象类型进行比较时

```java
// 他比较的是引用对象的数据内存地址
// 只有指向同一对象时才会时true
// 比较的对象需要是有关系的，否则会出现编译报错
```

```java
String s1 = new String("abc");
String s2 = new String("abc");
// 赋值后的abc的内存地址相同
String s3 = "abc";
String s4 = "abc";
// 开始比较
System.out.println(s1==s2); // false
System.out.println(s3==s4); // true
System.out.println(s1.equals(s2)); // true
System.out.println(s3.equals(s4)); // true
```

# equals比较内容

内容相同为true，不同false



### 注意

- 对于对象来说，特殊的类 String、File、Date，使用==时比较的是对象（对象的内存地址）
- equals 比较的是内容
- 除了特殊类之外的其他普通对象，==与equals比较的都是对象的内存地址。
- 如果想要改变某一个类的equals，不想用equals来比较对象的内存地址，就需要重写equals方法