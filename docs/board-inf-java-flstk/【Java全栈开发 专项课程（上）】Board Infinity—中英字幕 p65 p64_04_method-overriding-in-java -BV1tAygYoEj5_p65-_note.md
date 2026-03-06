# Java全栈开发：04：方法重写（Method Overriding）🚀

![](img/1ef1c82a1b5df125d9cf958a45832cf0_0.png)

在本节课中，我们将要学习Java面向对象编程中的一个核心概念——**方法重写**。这是实现**动态多态**的关键技术之一。我们将通过对比方法重载，并借助一个具体的代码示例，来清晰地理解方法重写的定义、规则和应用场景。

![](img/1ef1c82a1b5df125d9cf958a45832cf0_2.png)

## 概述：什么是方法重写？

![](img/1ef1c82a1b5df125d9cf958a45832cf0_4.png)

上一节我们介绍了多态的基本概念，本节中我们来看看实现动态多态的一种具体方式：方法重写。

当子类拥有一个与父类**方法签名完全相同**（方法名、返回类型、参数列表均相同）的方法时，就发生了方法重写。在程序运行时，Java虚拟机会根据实际创建的对象类型来决定调用哪个方法，这个过程就是方法重写。

## 方法重写 vs. 方法重载

为了更好地理解方法重写，我们将其与方法重载进行对比。以下是两者的核心区别：

*   **发生位置**：方法重载发生在**同一个类**中；方法重写发生在具有**继承关系**的父子类之间。
*   **方法签名**：方法重载要求方法名相同，但**参数列表必须不同**；方法重写要求方法名、返回类型和参数列表**必须完全相同**。
*   **目的**：方法重载是为了提供处理不同数据的**同名方法**，实现编译时多态；方法重写是子类对父类方法的**重新定义**，以实现运行时多态和功能扩展。

简单来说，重载是“一个类，多个同名但参数不同的方法”；重写是“父子类，签名完全相同的两个方法，子类覆盖父类”。

## 方法重写的代码示例

理论需要实践来巩固。接下来，我们通过一个具体的例子来演示方法重写是如何工作的。

首先，我们创建一个`Person`（人）基类，它包含姓名、年龄属性和一个打印详细信息的方法。

```java
class Person {
    String name;
    int age;

    // 构造方法
    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }

    // 打印信息的方法
    public void printDetails() {
        System.out.println("Name is: " + name);
        System.out.println("Age is: " + age);
    }
}
```

现在，我们创建一个`Employee`（员工）类来继承`Person`类。员工除了姓名和年龄，还有职位和薪水。我们需要重写`printDetails`方法，以打印员工特有的信息。

```java
class Employee extends Person {
    String designation;
    double salary;

    // 构造方法，使用super调用父类构造方法
    public Employee(String name, int age, String designation, double salary) {
        super(name, age); // 初始化从父类继承的属性
        this.designation = designation;
        this.salary = salary;
    }

    // 重写父类的printDetails方法
    @Override
    public void printDetails() {
        super.printDetails(); // 首先调用父类方法打印基础信息
        System.out.println("Designation is: " + designation); // 然后打印子类特有信息
        System.out.println("Salary is: " + salary);
    }
}
```

最后，我们创建一个测试类来观察方法重写的效果。

```java
public class TestOverriding {
    public static void main(String[] args) {
        // 创建Employee对象
        Employee emp = new Employee("Alice", 30, "Software Engineer", 80000.0);
        // 调用printDetails方法
        emp.printDetails();
    }
}
```

运行以上代码，输出结果将是：
```
Name is: Alice
Age is: 30
Designation is: Software Engineer
Salary is: 80000.0
```

可以看到，当我们通过`Employee`类的对象调用`printDetails()`方法时，执行的是子类中重写后的版本。子类方法通过`super.printDetails()`先调用了父类的逻辑，然后添加了自己的逻辑，从而**扩展**了父类的功能。

## 总结

![](img/1ef1c82a1b5df125d9cf958a45832cf0_6.png)

本节课中我们一起学习了Java中的方法重写。我们明确了方法重写是实现运行时多态（动态多态）的机制，它发生在继承体系中，要求子类方法与父类方法具有完全相同的方法签名。通过重写，子类可以重新定义从父类继承来的方法行为，实现功能的**专业化扩展**。记住，方法重写（Override）与方法重载（Overload）是两种完全不同的概念，前者关乎继承与多态，后者关乎同一类中的方法命名。

![](img/1ef1c82a1b5df125d9cf958a45832cf0_8.png)

![](img/1ef1c82a1b5df125d9cf958a45832cf0_10.png)

> 提示：方法重写也可以与抽象类和接口结合使用，我们将在后续课程中详细探讨。