# 049：Getter与Setter方法详解 🔧

![](img/71e04b7432737df6a2337321b0b528b1_0.png)

![](img/71e04b7432737df6a2337321b0b528b1_2.png)

在本节课中，我们将学习面向对象编程中一个核心概念——封装，并重点讲解如何通过Getter和Setter方法来实现数据隐藏。我们将了解为何需要这些方法，以及如何利用它们来控制对类中私有属性的访问。

## 封装与数据隐藏

上一节我们介绍了类的基本结构，本节中我们来看看如何保护类中的数据。在Java中，类的字段（变量）在类的实例中成为对象属性。为了增加控制，我们可以将访问修饰符设置为`private`。

**核心概念**：`private`修饰符意味着该数据成员只能在定义它的类内部被访问，这被称为“数据隐藏”。如果需要在类定义之外使用私有成员，就必须提供公共方法。

## Getter与Setter方法的作用

Getter和Setter方法（也称为访问器和修改器）是访问和修改私有属性的桥梁。它们不仅允许外部代码与私有属性交互，还能让你灵活地控制属性的访问权限。

![](img/71e04b7432737df6a2337321b0b528b1_4.png)

以下是访问权限的三种类型：
*   **只读属性**：仅提供Getter方法。
*   **只写属性**：仅提供Setter方法。
*   **读写属性**：同时提供Getter和Setter方法。

## 实践：创建Person类

![](img/71e04b7432737df6a2337321b0b528b1_6.png)

为了演示，我们创建一个`Person`类，它包含两个私有成员：`firstName`和`lastName`。我们将为它们创建Getter和Setter方法，以便从类外部访问。

```java
public class Person {
    // 私有成员变量
    private String firstName;
    private String lastName;
    private int age;

    // Getter 方法用于读取firstName
    public String getFirstName() {
        return this.firstName;
    }

    // Setter 方法用于设置firstName
    public void setFirstName(String firstName) {
        this.firstName = firstName;
    }

    // Getter 方法用于读取lastName
    public String getLastName() {
        return this.lastName;
    }

    // Setter 方法用于设置lastName
    public void setLastName(String lastName) {
        this.lastName = lastName;
    }
}
```

现在，我们可以创建`Person`类的实例，并通过其公共方法来访问私有属性：

```java
Person person = new Person();
person.setFirstName("King");
person.setLastName("Coer");
System.out.println(person.getFirstName() + " " + person.getLastName());
// 输出：King Coer
```

## 在Setter方法中添加验证逻辑

Getter和Setter方法的另一个强大功能是可以在其中添加业务逻辑或验证。例如，对于`age`属性，我们可以确保设置的值是合理的。

```java
public class Person {
    // ... 其他属性 ...

    private int age;

    public int getAge() {
        return this.age;
    }

    public void setAge(int age) {
        // 添加验证：年龄必须大于等于18岁
        if (age >= 18) {
            this.age = age;
        } else {
            System.out.println("Invalid age.");
            // 可以选择抛出异常或设置默认值
            this.age = 0;
        }
    }
}
```

使用带验证的Setter方法：

```java
Person person = new Person();
person.setAge(16); // 输出：Invalid age.
System.out.println(person.getAge()); // 输出：0

person.setAge(32); // 验证通过
System.out.println(person.getAge()); // 输出：32
```

## 控制访问权限

你可以根据需求决定为属性提供哪些方法：
*   若希望属性**只读**，则仅实现Getter方法。
*   若希望属性**只写**，则仅实现Setter方法。
*   若希望属性**可读写**，则同时实现Getter和Setter方法。

## 总结

本节课中我们一起学习了封装的核心实践——使用Getter和Setter方法。我们了解到：
1.  `private`修饰符用于实现数据隐藏。
2.  Getter方法用于安全地**读取**私有属性。
3.  Setter方法用于安全地**修改**私有属性，并可在其中加入验证逻辑。
4.  通过选择性地提供Getter或Setter方法，可以精确控制属性的访问权限（只读、只写或读写）。

![](img/71e04b7432737df6a2337321b0b528b1_8.png)

一个拥有完整Getter和Setter方法的类（常被称为POJO或模型类）是构建Java应用程序实体的基础。掌握这个概念对后续学习至关重要。