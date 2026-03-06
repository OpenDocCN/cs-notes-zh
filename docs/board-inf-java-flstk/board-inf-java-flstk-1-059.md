# 059：实现类之间的继承 👨‍💻

![](img/d88a358dd7c24bb95284c6a976e99f25_0.png)

![](img/d88a358dd7c24bb95284c6a976e99f25_2.png)

在本节课中，我们将要学习如何在Java中实现类之间的继承。我们将通过一个具体的例子，从创建一个基础的`Student`类开始，逐步扩展其功能，最终构建一个包含学生成绩和体育分数的多级继承体系，并计算总分和平均分。

## 概述

继承是面向对象编程的核心概念之一，它允许我们基于现有类创建新类，从而实现代码的重用和扩展。本节将通过一个学生信息管理的示例，演示如何创建父类、子类，以及如何处理多级继承和方法重写。

![](img/d88a358dd7c24bb95284c6a976e99f25_4.png)

---

![](img/d88a358dd7c24bb95284c6a976e99f25_6.png)

## 创建父类：Student类

首先，我们创建一个基础的`Student`类。这个类包含一些基本的数据成员（如学号、姓名）和成员函数（如录入和显示详细信息）。

```java
class Student {
    private int rollNumber;
    private String name;

    public void acceptDetail() {
        // 代码示例：使用Scanner录入rollNumber和name
    }

    public void displayDetail() {
        // 代码示例：打印rollNumber和name
    }
}
```

上一节我们介绍了基础的`Student`类，本节中我们来看看如何扩展它。

## 创建子类：Marks类

为了存储学生的客观题和主观题分数，我们不直接修改`Student`类，而是创建一个新的`Marks`类来继承它。这样做的好处是保持了`Student`类的稳定性，同时增加了新功能。

```java
class Marks extends Student {
    protected float objectiveMarks;
    protected float subjectiveMarks;

    public void acceptDetail() {
        super.acceptDetail(); // 调用父类方法
        // 代码示例：录入objectiveMarks和subjectiveMarks
    }

    public void displayDetail() {
        super.displayDetail(); // 调用父类方法
        // 代码示例：打印objectiveMarks和subjectiveMarks
    }
}
```

以下是关键点说明：
*   `extends`关键字用于建立继承关系。
*   子类可以拥有自己的数据成员（如`objectiveMarks`）。
*   子类可以重写父类的方法（如`acceptDetail`）。
*   使用`super`关键字可以调用父类中被重写的方法。

当创建子类对象时，内存会同时分配给父类和子类的数据成员。通过子类对象，我们可以调用父类和子类的方法。

## 多级继承：Sports类

现在，我们进一步扩展功能，创建一个`Sports`类来继承`Marks`类，用于记录学生的体育分数。这形成了多级继承链：`Student` -> `Marks` -> `Sports`。

```java
class Sports extends Marks {
    protected float score;

    public void acceptDetail() {
        super.acceptDetail();
        // 代码示例：录入score
    }

    public void displayDetail() {
        super.displayDetail();
        // 代码示例：打印score
    }
}
```

通过这种方式，`Sports`类间接继承了`Student`和`Marks`的所有属性和方法。

![](img/d88a358dd7c24bb95284c6a976e99f25_8.png)

## 访问控制：protected关键字

![](img/d88a358dd7c24bb95284c6a976e99f25_10.png)

在尝试从`Result`类中访问`Marks`类的分数时，我们发现如果数据成员是`private`的，则无法直接访问。为了解决跨继承层次的访问问题，我们将这些成员改为`protected`。

**访问修饰符区别**：
*   `private`：仅在本类内可访问。
*   `protected`：在本类、同一包内以及所有子类中可访问。
*   `public`：在任何地方都可访问。

因此，我们将`Marks`类中的分数变量改为`protected`，以便在继承链下游的类中访问。

## 最终计算：Result类

最后，我们创建一个`Result`类来继承`Sports`类，并计算总分和平均分。

```java
class Result extends Sports {
    private float totalMarks;
    private float averageMarks;

    public void calculate() {
        totalMarks = objectiveMarks + subjectiveMarks + score;
        averageMarks = totalMarks / 3;
        System.out.println("Total Marks: " + totalMarks);
        System.out.println("Average Marks: " + averageMarks);
    }
}
```

以下是程序执行的步骤：
1.  创建`Result`类的对象。
2.  调用`acceptDetail()`方法，由于多级继承和方法重写，会依次调用整个继承链上的录入方法。
3.  调用`displayDetail()`方法，显示所有信息。
4.  调用`calculate()`方法，计算并输出总分和平均分。

运行示例：
输入：学号`101`，姓名`King`，客观分`43`，主观分`89`，体育分`97`。
输出：总分`273`，平均分`91`。

---

## 总结

![](img/d88a358dd7c24bb95284c6a976e99f25_12.png)

本节课中我们一起学习了Java继承的核心实践。我们从创建一个简单的`Student`类开始，通过继承依次构建了`Marks`、`Sports`和`Result`类，演示了单继承、方法重写、使用`super`关键字调用父类方法、`protected`访问控制符的作用，以及多级继承的概念。这个示例清晰地展示了如何通过继承来分层组织代码，增强功能，同时保持代码的可维护性和可扩展性。