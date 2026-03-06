# 050：构造器入门指南

在本节课中，我们将学习Java中构造器的概念、类型及其使用方法。构造器是面向对象编程中用于初始化新创建对象的核心工具。

---

## 什么是构造器？🤔

构造器是一种特殊类型的方法，用于初始化类的对象。当创建对象时，构造器会被自动调用。构造器的名称必须与它所属的类名完全相同。

例如，一个名为 `Car` 的类，其构造器也命名为 `Car`。

```java
public class Car {
    // 这是一个构造器
    public Car() {
        // 初始化代码
    }
}
```

![](img/cb8eccd93a50815199a5128deddeb330_1.png)

---

## 构造器的类型

上一节我们介绍了构造器的基本定义，本节中我们来看看构造器的两种主要类型：默认构造器和参数化构造器。

### 默认构造器

默认构造器不接受任何参数。如果类中没有显式定义任何构造器，Java编译器会自动提供一个默认构造器。

以下是默认构造器的一个示例：

```java
public class Book {
    public Book() {
        // 默认构造器
        System.out.println("一个Book对象被创建了。");
    }
}
```

### 参数化构造器

参数化构造器允许在创建对象时传入参数，用于以不同的初始状态初始化对象。

以下是参数化构造器的一个示例：

```java
public class Student {
    String name;
    int age;

    // 参数化构造器
    public Student(String studentName, int studentAge) {
        name = studentName;
        age = studentAge;
    }
}
```

---

## 构造器链

理解了基本构造器后，我们来看看如何通过构造器链来简化代码。构造器链指的是一个构造器调用同一个类中的另一个构造器，这通常使用 `this()` 关键字实现。

以下是构造器链的一个示例：

```java
public class Rectangle {
    int length;
    int width;

    // 默认构造器调用参数化构造器
    public Rectangle() {
        this(1, 1); // 调用下面的构造器
    }

    // 参数化构造器
    public Rectangle(int l, int w) {
        length = l;
        width = w;
    }
}
```

---

## 私有构造器与单例模式

最后，我们来探讨一种特殊的构造器用法——私有构造器。私有构造器通常用于实现单例模式，确保一个类在程序中只有一个实例。

以下是使用私有构造器实现单例模式的一个示例：

```java
public class Singleton {
    private static Singleton instance;

    // 私有构造器，防止外部通过new创建实例
    private Singleton() {
    }

    // 提供全局访问点
    public static Singleton getInstance() {
        if (instance == null) {
            instance = new Singleton();
        }
        return instance;
    }
}
```

---

## 总结📚

本节课中我们一起学习了Java构造器的核心知识。我们了解了构造器是一种用于初始化对象的特殊方法，其名称与类名相同。我们探讨了默认构造器和参数化构造器的区别与用法，学习了如何使用构造器链来优化代码结构，并介绍了私有构造器在实现单例设计模式中的应用。掌握这些概念是进行有效Java面向对象编程的基础。