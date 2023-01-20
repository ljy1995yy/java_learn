x instanceof A：检验x是否是类A的对象，返回值是boolean。

- 要求：x所属的类与A必须是子类和父类的关系，否则编译报错
- 如果x属于类A的子类B，xinstanceof A 结果为true。

父类

```java
package com.duotai;

public class Animal {
    public int age = 40;
    public void eat(){
        System.out.println("动物吃");
    }
}

```

子类Cat

```java
package com.duotai;

public class Cat extends Animal{
    public int age = 20;
    public int weight = 10;
    @Override
    public void eat() {
        System.out.println("猫吃鱼");
    }

    public void playGame(){
        System.out.println("猫咪玩捉迷藏");
    }
}

```

子类 Dog

```java
package com.duotai;

public class Dog extends Animal{
    @Override
    public void eat() {
        System.out.println("狗吃骨头");
    }

    public void looDoor(){
        System.out.println("狗看门");
    }
    public void playGame(){
        System.out.println("猫咪玩捉迷藏");
    }
}
```

执行类中

```java
if(aa instanceof Animal){

}else if (cc instanceof Animal){

}else if (dd instanceof Cat){ // 报错
    // 原因： dd的类是Dog，但是Dog与Cat类不是父子类的关系
    
}
```