# 055：Java中的构造器链

![](img/824e8166ebcad577eb30538a52a8e84c_0.png)

![](img/824e8166ebcad577eb30538a52a8e84c_2.png)

![](img/824e8166ebcad577eb30538a52a8e84c_0.png)

在本节课中，我们将学习Java中的构造器链。构造器链是指在当前对象中，一个构造器调用另一个构造器的过程。我们将探讨如何在同一类内部以及通过继承来实现构造器链，并理解其核心目的。

## 概述

构造器链的主要目的是通过一系列不同的构造器传递参数，并将初始化逻辑集中在一个地方完成。这可以通过两种方式实现：在同一类中使用 `this` 关键字，或在父子类之间使用 `super` 关键字。

## 同一类中的构造器链

首先，我们来看如何在同一类内部实现构造器链。这需要使用 `this` 关键字来调用当前类的其他构造器。

以下是一个示例，演示了在同一个类中，多个构造器如何相互调用：

```java
public class Student {
    int id;
    String name;
    int age;

    // 默认构造器
    public Student() {
        this(101, "Carl", 23); // 调用三参数构造器
    }

    // 双参数构造器
    public Student(int id, String name) {
        this(id, name, 0); // 调用三参数构造器
    }

    // 三参数构造器
    public Student(int id, String name, int age) {
        this.id = id;
        this.name = name;
        this.age = age;
    }

    public void display() {
        System.out.println("ID: " + id + ", Name: " + name + ", Age: " + age);
    }

    public static void main(String[] args) {
        Student s1 = new Student(); // 调用默认构造器
        s1.display();
    }
}
```

在上面的代码中，创建 `Student` 对象时，执行流程如下：
1.  调用默认构造器 `Student()`。
2.  默认构造器通过 `this(101, "Carl", 23)` 调用三参数构造器。
3.  三参数构造器完成成员变量 `id`、`name` 和 `age` 的初始化。
4.  控制权返回默认构造器，但此时初始化已完成，因此最终打印出 `ID: 101, Name: Carl, Age: 23`。

这种方式确保了无论通过哪个构造器创建对象，最终的初始化逻辑都集中在三参数构造器中完成。

## 通过继承实现的构造器链

上一节我们介绍了同一类中的构造器链，本节中我们来看看如何通过继承关系实现构造器链。这需要使用 `super` 关键字来调用父类的构造器。

在继承中，当创建子类对象时，会首先调用父类的构造器。如果父类有默认构造器，这个过程会自动发生。但如果父类只有带参数的构造器，则必须在子类构造器中显式使用 `super` 来调用。

以下是一个通过继承实现构造器链的示例：

```java
// 父类
class Person {
    String name;

    // 父类带参数构造器
    public Person(String name) {
        this.name = name;
        System.out.println("Person类带参数构造器被调用。");
    }
}

// 子类
class Employee extends Person {
    String designation;

    // 子类带参数构造器
    public Employee(String name, String designation) {
        super(name); // 必须显式调用父类带参数构造器
        this.designation = designation;
        System.out.println("Employee类构造器被调用。");
    }
}

public class Main {
    public static void main(String[] args) {
        Employee emp = new Employee("Alice", "高级经理");
    }
}
```

在上面的代码中，创建 `Employee` 对象时，执行流程如下：
1.  调用 `Employee` 的构造器 `Employee("Alice", "高级经理")`。
2.  该构造器首先通过 `super("Alice")` 调用父类 `Person` 的带参数构造器。
3.  父类构造器初始化 `name` 并打印信息。
4.  控制权返回子类构造器，初始化 `designation` 并打印信息。

如果子类构造器中没有显式写出 `super(...)`，编译器会自动添加一个无参数的 `super()` 来调用父类的默认构造器。如果父类没有默认构造器，则会导致编译错误。

## 总结

![](img/824e8166ebcad577eb30538a52a8e84c_4.png)

![](img/824e8166ebcad577eb30538a52a8e84c_6.png)

本节课中我们一起学习了Java中的构造器链。我们了解到，构造器链是让多个构造器协同工作、集中初始化逻辑的有效方式。在同一类中，我们使用 **`this(参数列表)`** 来调用本类的其他构造器。在继承关系中，我们使用 **`super(参数列表)`** 来调用父类的构造器，并且这是初始化父类状态的必要步骤。掌握这两种方式，有助于你编写出更清晰、更易维护的Java代码。