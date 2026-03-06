# Java全栈开发：04：创建类与对象

![](img/3597f8f98f5923ed2d60435187d66ba2_0.png)

在本节课中，我们将学习如何定义一个类，以及如何通过创建该类的对象（实例化）来访问其成员。这是面向对象编程的核心基础。

---

![](img/3597f8f98f5923ed2d60435187d66ba2_2.png)

## 概述

类是创建对象的蓝图。它定义了对象的属性（数据成员）和行为（成员函数）。我们将创建一个简单的`Student`类，包含ID、姓名和年龄属性，并实现输入和显示这些信息的方法。

---

## 创建Student类

首先，我们来定义一个名为`Student`的类。这个类将包含描述学生的数据成员和操作这些数据的成员函数。

以下是`Student`类的基本结构：

```java
public class Student {
    // 数据成员
    int studentID;
    String studentName;
    int studentAge;

    // 成员函数
    public void acceptDetails() {
        // 用于接受用户输入
    }

    public void displayDetails() {
        // 用于显示学生信息
    }
}
```

---

## 实现成员函数

上一节我们定义了类的结构，本节中我们来看看如何实现具体的功能。我们需要在`acceptDetails`方法中获取用户输入，并在`displayDetails`方法中打印信息。

为了在多个方法中使用输入功能，我们可以在类级别创建一个`Scanner`对象。

以下是`acceptDetails`方法的实现：

```java
import java.util.Scanner;

public class Student {
    // 数据成员
    int studentID;
    String studentName;
    int studentAge;
    Scanner scanner = new Scanner(System.in); // 类级别的Scanner对象

    public void acceptDetails() {
        System.out.println("Enter student ID:");
        studentID = scanner.nextInt();
        scanner.nextLine(); // 消耗换行符
        System.out.println("Enter student name:");
        studentName = scanner.nextLine();
        System.out.println("Enter student age:");
        studentAge = scanner.nextInt();
    }
}
```

接下来是`displayDetails`方法的实现。请注意，我们不需要传递任何参数，因为方法可以直接访问类级别的数据成员。

```java
    public void displayDetails() {
        System.out.println("Student ID is: " + studentID);
        System.out.println("Student name is: " + studentName);
        System.out.println("Student age is: " + studentAge);
    }
```

---

## 实例化对象与访问成员

现在我们已经定义了一个完整的类，接下来需要在主方法中创建它的对象并调用其方法。

理解下面这行代码非常重要：
```java
Student student = new Student();
```
这行代码包含两部分：
*   **`Student student`**：声明一个名为`student`的引用变量，其类型为`Student`。这还不是对象本身。
*   **`new Student()`**：使用`new`关键字在内存中实际创建一个`Student`对象。此时，对象的数据成员会获得内存空间。

创建对象后，我们可以通过引用变量`.`（点）操作符来访问其成员函数。

```java
public class Main {
    public static void main(String[] args) {
        // 创建第一个Student对象
        Student student = new Student();
        student.acceptDetails();
        student.displayDetails();
    }
}
```

运行程序，它将提示你输入学生信息，然后将其打印出来。

---

## 创建多个对象

一个类可以创建多个独立的实例。每个对象都有自己的内存空间，通过其引用变量进行访问。

以下是创建和使用多个对象的示例：

```java
public class Main {
    public static void main(String[] args) {
        // 创建第一个对象
        Student student = new Student();
        System.out.println("Enter details for first student:");
        student.acceptDetails();
        student.displayDetails();

        // 创建第二个对象
        Student student1 = new Student();
        System.out.println("\nEnter details for second student:");
        student1.acceptDetails();
        student1.displayDetails();
    }
}
```

程序将依次为两个学生对象获取并显示信息，每个对象都维护着自己独立的数据。

---

## 总结

![](img/3597f8f98f5923ed2d60435187d66ba2_4.png)

本节课中我们一起学习了面向对象编程的基础操作：
1.  **定义类**：使用`class`关键字创建蓝图，包含数据成员和成员函数。
2.  **实现方法**：在方法内部编写逻辑，可以直接访问类级别的变量。
3.  **实例化对象**：使用`new`关键字创建类的具体实例，理解引用变量与对象的区别。
4.  **访问成员**：通过对象引用后跟`.`操作符来调用方法或访问属性。
5.  **多个对象**：一个类可以创建多个独立的对象，每个对象都有自己的状态。

![](img/3597f8f98f5923ed2d60435187d66ba2_6.png)

希望你现在清楚了如何创建类、编写其成员，以及如何通过创建对象来使用它们。每个对象都拥有自己独立的上下文环境。在接下来的课程中，我们将继续学习更多面向对象编程的实际应用。