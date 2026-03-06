# 047：访问修饰符演示

![](img/dbd8d9672c9f53949ed2598ee5932b2a_0.png)

在本节课中，我们将通过一个具体的程序示例，学习如何在Java程序中使用访问修饰符。我们将了解不同访问修饰符的作用范围，并通过修改代码来观察其效果。

---

![](img/dbd8d9672c9f53949ed2598ee5932b2a_2.png)

## 概述

访问修饰符用于控制类、变量、方法和构造函数的访问权限。理解它们对于编写安全、结构清晰的Java代码至关重要。本节将通过一个学生类的例子，演示`private`、`default`和`protected`修饰符的实际应用。

## 默认访问修饰符

首先，我们来看一个没有显式声明访问修饰符的类。在下面的代码中，类、数据成员和方法都没有指定修饰符。

```java
class Student {
    int studentID;
    String name;
    int age;

    void acceptDetails() {
        // 接受输入细节的代码
    }

    void displayDetails() {
        // 显示细节的代码
    }
}
```

即使我移除`acceptDetails`和`displayDetails`方法前的访问修饰符，程序依然可以正常运行。这是因为在Java中，如果一个类成员没有指定任何访问修饰符，它就拥有**默认**（或称包私有）的访问权限。

默认访问权限意味着该成员可以在**同一个包内的任何地方**被访问。例如，在同一个包内的另一个类中，我可以这样访问：

```java
// 在同一个包内的另一个类中
Student student1 = new Student();
student1.age = 23; // 可以访问，因为age是默认修饰符
```

## 使用私有访问修饰符

然而，我可能不希望类的数据成员（如`studentID`和`name`）在类定义之外被直接访问和修改。为了实现更好的封装，我可以将它们声明为`private`。

```java
class Student {
    private int studentID;
    private String name;
    int age; // 保持为默认访问权限

    // ... 方法定义
}
```

现在，如果我在另一个类中尝试直接访问`studentID`或`name`，编译器将会报错。

```java
// 在另一个类中
Student student1 = new Student();
student1.studentID = 10; // 编译错误：studentID 在 Student 中是 private 访问控制
student1.name = "King";   // 编译错误：name 在 Student 中是 private 访问控制
student1.age = 23;        // 可以访问，因为age是默认修饰符
```

`private`修饰符将成员的访问范围限制在**声明它的类内部**。这是实现数据隐藏和保护的关键。

## 公共访问修饰符与类

对于包含`main`方法的类，它通常需要被Java虚拟机（JVM）加载和执行，因此这个类本身必须是`public`的。

```java
public class ClassesAndObjectsExample {
    public static void main(String[] args) {
        // 程序入口
    }
}
```

如果你的项目结构中有不同的文件夹（包），并且你需要从其他包访问`Student`类，那么`Student`类也必须声明为`public`。

```java
package com.example.model;

public class Student {
    // ... 成员定义
}
```

## 受保护的访问修饰符

`protected`访问修饰符主要用于继承的场景。当一个成员被声明为`protected`时，它可以在**同一个包内**以及**任何子类中**被访问，即使子类位于不同的包。

```java
package com.example.base;

public class Parent {
    protected int protectedField; // 受保护的成员
}
```

```java
package com.example.child;
import com.example.base.Parent;

public class Child extends Parent {
    void accessProtected() {
        protectedField = 10; // 可以访问，因为Child是Parent的子类
    }
}
```

关于`protected`修饰符在继承中的具体应用，我们将在后续讲解继承概念的课程中详细讨论。

## 总结

![](img/dbd8d9672c9f53949ed2598ee5932b2a_4.png)

本节课我们一起学习了Java中访问修饰符的使用：
1.  **默认**修饰符允许在同一个包内访问。
2.  **`private`** 修饰符将访问权限严格限制在类内部，是实现封装的核心。
3.  **`public`** 修饰符允许在任何地方访问，常用于需要被广泛调用的类和方法。
4.  **`protected`** 修饰符主要用于继承体系，允许子类访问父类的成员。

![](img/dbd8d9672c9f53949ed2598ee5932b2a_6.png)

理解并正确使用这些访问修饰符，是构建健壮、可维护Java应用程序的基础。在下一节关于继承的课程中，我们将更深入地探讨`protected`修饰符的应用。