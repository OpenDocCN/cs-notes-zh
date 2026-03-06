Java全栈开发：10：List接口详解 📚

在本节课中，我们将要学习Java集合框架中的List接口。List接口扩展了Collection接口，用于存储有序的数据集合，并且允许包含重复元素。我们将了解其基本概念、语法以及实现它的几个主要类。

---

![](img/c5cd0dfb63367f64e4147793066f932c_1.png)

### 什么是List接口？ 📋

![](img/c5cd0dfb63367f64e4147793066f932c_2.png)

List接口用于存储**有序**的数据集合，并且可以包含**重复**的元素。这里的“有序”指的是元素被插入的顺序会被保留。

List中的元素可以通过它们在列表中的位置（即索引）来访问或插入。Java使用**基于0的索引**，这意味着索引从0开始计数。

这个接口位于 `java.util` 包中。

---

### List接口的实现类 🏗️

Java中有多个类实现了List接口，主要包括以下三个：

*   **ArrayList**
*   **LinkedList**
*   **Vector**

这三个类允许我们通过迭代来操作一组特定类型的对象。我们只需要理解这个接口默认声明了哪些抽象方法以及它们的功能，例如 `add`、`remove`、`clear`、`size`、`iterator`、`contains` 等等。

---

### 如何使用List接口？ 💻

现在，让我们从语法开始，看看如何通过初始化这些实现类来创建List接口的引用变量。

你可以在主方法中这样写：`List` 是一个接口，它位于 `java.util` 包中。我们需要指定要存储的数据类型，这里我们以包装类 `Integer` 为例。

首先，我创建一个 `LinkedList` 的引用变量。需要再次强调，**你不能直接实例化List接口**。你可以看到，如果尝试 `new List<>()`，编译器会报错并要求提供具体实现，因为List是一个接口。我们必须使用它的具体实现类，如 `LinkedList`、`Vector` 或 `ArrayList`。

以下是如何创建不同List实现类的示例：

```java
// 创建一个LinkedList
List<Integer> linkedList = new LinkedList<>();

// 创建一个ArrayList
List<Integer> arrayList = new ArrayList<>();

// 创建一个Vector
List<Integer> vectorList = new Vector<>();
```

请注意，在实例化这些具体类时，我指定了数据类型 `Integer`。正如之前提到的，List是一个**泛型**接口，它的实现类也是泛型的。你需要根据你想要操作或存储的对象类型，在实例化时传入相应的数据类型。

---

### 总结 📝

本节课我们一起学习了Java中的List接口。我们了解到List是一个用于存储有序、可重复元素集合的接口。它位于 `java.util` 包中，并且不能被直接实例化。我们介绍了三个主要的实现类：`ArrayList`、`LinkedList` 和 `Vector`，并学习了如何通过它们来创建List类型的引用变量。关键在于理解List的泛型特性，并在创建时指定要存储的数据类型。

![](img/c5cd0dfb63367f64e4147793066f932c_4.png)

在下一节中，我们将更深入地探讨 `ArrayList` 的具体用法。敬请期待，我们下节课再见！