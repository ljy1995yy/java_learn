学生对象类

```java
package com.LL_learn.studentManager;

public class Student {
    private String sid;
    private String name;
    private String age;
    private String address;

    // 构造器（构造方法）
    public Student() {
    }

    public Student(String sid, String name, String age, String address) {
        this.sid = sid;
        this.name = name;
        this.age = age;
        this.address = address;
    }

    // 私有属性的获取和修改方法
    public void setAge(String age) {
        this.age = age;
    }

    public String getAge() {
        return age;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public String getSid() {
        return sid;
    }

    public void setSid(String sid) {
        this.sid = sid;
    }

    public String getAddress() {
        return address;
    }

    public void setAddress(String address) {
        this.address = address;
    }
}
```

学生系统执行类

```java
package com.LL_learn.studentManager;

import java.util.ArrayList;
import java.util.Scanner;

public class StudentManager {
    public static void main(String[] args) {
        ArrayList<Student> array = new ArrayList<Student>();
        // 标志物
        boolean flag = true;
        while (flag){
            // 主页面
            System.out.println("-------欢迎来到学生管理系统---------");
            System.out.println("1，添加学生");
            System.out.println("2.删除学生");
            System.out.println("3.修改学生");
            System.out.println("4.查看所有学生");
            System.out.println("5.退出");
            // 输入数据
            Scanner sc = new Scanner(System.in);
            System.out.println("请输入你的选择");
            String choice_num = sc.nextLine();

            // switch 选择
            switch (choice_num){
                case "1":
                    addStudent(array);
                    break;
                case "2":
                    deleteStudent(array);
                    break;
                case "3":
                    updateStudent(array);
                    break;
                case "4":
                    findStudent(array);
                    break;
                case "5":
                    flag = false;
                    break;
//                    System.exit(0); // jvm退出
                default:
                    System.out.println("输入有误默认退出");
                    flag = false;
                    break;
            }
        }
    }
    public static void addStudent(ArrayList<Student> array){
        Scanner sc = new Scanner(System.in);
        // 为了sid可以在外部被调用，所以在循环外部进行定义
        String sid;
        while (true) {
            System.out.println("请输入学生学号");
            sid = sc.nextLine();
            boolean flag = isUser(array, sid);
            if (flag) {
                System.out.println("你输入的学号已经被使用，重新输入");
            }else {
                break;
            }
        }
        System.out.println("请输入学生姓名");
        String name = sc.nextLine();
        System.out.println("请输入学生年龄");
        String age = sc.nextLine();
        System.out.println("请输入学生地址");
        String address = sc.nextLine();
        Student s = new Student();
        s.setSid(sid);
        s.setAge(age);
        s.setName(name);
        s.setAddress(address);
        array.add(s);
    }
    public static void findStudent(ArrayList<Student> arrayList){
        // 判断数据中是否有数据
        if (arrayList.size()==0){
            System.out.println("无信息，请先添加信息");
            return;
        }
        System.out.print("学号\t姓名\t年龄\t居住地\n");

        for (int i = 0; i < arrayList.size(); i++) {
            Student  s = arrayList.get(i);
            System.out.println(s.getSid()+"\t"+s.getName()+"\t"+s.getAge()+"岁\t"+s.getAddress());
        }
    }
    public static void deleteStudent(ArrayList<Student> arrayList){
        Scanner sc = new Scanner(System.in);
        System.out.println("请输入要删除的学生学号");
        String sid = sc.nextLine();
        int index = -1;
        for (int i = 0; i < arrayList.size(); i++) {
            Student s = arrayList.get(i);
            if(s.getSid().equals(sid)){
                index =i;
                break;
            }
        }
        // 学生信息是否存在的判断
        if(index==-1){
            System.out.println("该信息不存在，请重新输入");
        }else {
            Student remove_people = arrayList.remove(index);
            System.out.println("删除学生"+remove_people.getName()+"成功");
        }
    }
    public static void updateStudent(ArrayList<Student> arrayList){
        Scanner sc = new Scanner(System.in);
        System.out.println("请输入要修改的学生学号");
        String sid = sc.nextLine();
        Student s = new Student();
        // 数组中对象替换
        // 记录下标值(java中下标不存在负值)
        int index = -1;
        for (int i = 0; i < arrayList.size(); i++) {
            Student stu = arrayList.get(i);
            if(stu.getSid().equals(sid)){
                index = i;
                break;
            }
        }
        if (index==-1){
            System.out.println("你修改的学生信息不存在");
        }else {
            // 修改信息
            System.out.println("请输入学生新姓名：");
            String name = sc.nextLine();
            System.out.println("请输入学生新年龄：");
            String age = sc.nextLine();
            System.out.println("请输入学生新地址：");
            String address = sc.nextLine();
            // 创建学生对象
            s.setSid(sid);
            s.setName(name);
            s.setAge(age);
            s.setAddress(address);
            arrayList.set(index,s);
            System.out.println("学生修改成功");
        }
    }
    public static boolean isUser(ArrayList<Student>arrayList,String sid){
        boolean flag=false;
        for (int i = 0; i < arrayList.size(); i++) {
            Student s = arrayList.get(i);
            if(s.getSid().equals(sid)){
                flag=true;
                break;
            }
        }
        return flag;
    }
}
```