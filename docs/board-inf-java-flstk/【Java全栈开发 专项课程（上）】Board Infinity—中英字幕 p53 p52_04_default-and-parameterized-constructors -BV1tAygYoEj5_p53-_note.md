# Java全栈开发：04：默认与带参构造函数 🏗️

![](img/9ec8ab188e31fd121f1c5bfcefb78ff2_0.png)

![](img/9ec8ab188e31fd121f1c5bfcefb78ff2_2.png)

在本节课中，我们将学习Java中两种重要的构造函数：默认构造函数和带参构造函数。我们将通过一个学生类的例子，理解它们如何工作、如何创建以及如何使用。

![](img/9ec8ab188e31fd121f1c5bfcefb78ff2_4.png)

---

![](img/9ec8ab188e31fd121f1c5bfcefb78ff2_6.png)

## 概述

构造函数是类的一种特殊方法，用于在创建对象时初始化该对象的数据成员。Java提供了默认构造函数，也允许我们创建自定义的带参构造函数，以便更灵活地初始化对象。

---

## 默认构造函数

上一节我们介绍了类的基本概念，本节中我们来看看如何初始化一个类的对象。首先，我们创建一个`Student`类，它包含`studentID`、`name`和`age`属性。

```java
public class Student {
    int studentID;
    String name;
    int age;
}
```

如果我们在创建`Student`对象时不提供任何初始值，并调用一个显示详情的方法，这些属性仍然会有值。这是因为每个类都隐式地继承自`Object`类，而`Object`类有一个特殊的构造函数（默认构造函数），它会为数据成员提供默认初始值。

以下是默认初始值的规则：
*   `int`类型的默认值是`0`。
*   `String`类型的默认值是`null`。
*   `float`类型的默认值是`0.0`。
*   `boolean`类型的默认值是`false`。

当我们使用`new Student()`创建对象时，这个默认构造函数会被自动调用，从而完成初始化。

---

## 创建自定义默认构造函数

我们可以创建自己的默认构造函数来覆盖系统提供的默认行为。构造函数没有返回类型，且名称必须与类名完全相同。

```java
public class Student {
    int studentID;
    String name;
    int age;

    // 自定义默认构造函数
    public Student() {
        studentID = 100;
        name = "Unknown";
        age = 80;
    }
}
```

现在，每当创建`Student`对象时，都会调用这个自定义的构造函数，将`studentID`初始化为100，`name`初始化为"Unknown"，`age`初始化为80。

---

## 带参构造函数

使用自定义默认构造函数的问题是，所有创建的对象都会有相同的初始值。为了解决这个问题，我们可以创建带参构造函数，在创建对象时传入特定的值。

以下是创建带参构造函数的步骤：
1.  构造函数名与类名相同。
2.  在括号内定义参数列表。
3.  在构造函数体内，将参数值赋给类的数据成员。

```java
public class Student {
    int studentID;
    String name;
    int age;

    // 带参构造函数
    public Student(int sID, String sName, int sAge) {
        studentID = sID;
        name = sName;
        age = sAge;
    }
}
```

创建对象时，我们可以这样传递参数：
```java
Student student1 = new Student(101, "King Kocher", 23);
```
此时，`student1`对象的`studentID`、`name`和`age`将分别被初始化为101、"King Kocher"和23。

---

## 使用`this`关键字

当构造函数的参数名与类的数据成员名相同时，编译器会产生混淆。为了明确指定，我们需要使用`this`关键字。`this`代表当前对象的引用。

```java
public class Student {
    int studentID;
    String name;
    int age;

    public Student(int studentID, String name, int age) {
        this.studentID = studentID; // 将参数studentID赋给当前对象的studentID
        this.name = name;
        this.age = age;
    }
}
```
`this.studentID`指向当前对象的`studentID`属性，而等号右边的`studentID`指的是构造函数的参数。这是一种常见的编码规范，可以增强代码的可读性。

---

## 构造函数重载

一个类中可以同时存在多个构造函数，只要它们的参数列表（参数类型、数量或顺序）不同。这被称为**构造函数重载**。

```java
public class Student {
    int studentID;
    String name;
    int age;

    // 默认构造函数
    public Student() {
        studentID = 100;
        name = "Unknown";
        age = 80;
    }

    // 带参构造函数1
    public Student(int id, String n) {
        studentID = id;
        name = n;
        age = 18; // 给age一个默认值
    }

    // 带参构造函数2
    public Student(int id, String n, int a) {
        studentID = id;
        name = n;
        age = a;
    }
}
```
根据创建对象时提供的参数，Java会自动调用匹配的构造函数。

---

## 总结

![](img/9ec8ab188e31fd121f1c5bfcefb78ff2_8.png)

![](img/9ec8ab188e31fd121f1c5bfcefb78ff2_9.png)

本节课中我们一起学习了Java构造函数的核心概念。我们了解到，默认构造函数由Java隐式提供，用于初始化默认值。我们可以创建自定义的默认构造函数和带参构造函数，以便更精确地控制对象的初始化状态。使用`this`关键字可以解决参数与属性同名时的歧义。最后，通过构造函数重载，我们可以为一个类提供多种初始化方式，使代码更加灵活。掌握这些知识是进行面向对象编程的重要基础。

![](img/9ec8ab188e31fd121f1c5bfcefb78ff2_11.png)

![](img/9ec8ab188e31fd121f1c5bfcefb78ff2_12.png)

---
🎼 敬请关注后续课程，学习更多内容。下次见！