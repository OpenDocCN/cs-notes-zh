# 052：无对象时的null 🧩

![](img/7fd6fae5b9b162b7d4ee817a288fe5b3_0.png)

在本节课中，我们将要学习Java中一个非常重要的概念：`null`。我们将探讨`null`的含义、它的用途、如何检查它，以及在使用它时需要注意的陷阱。理解`null`对于编写健壮的算法至关重要，尤其是在处理可能不存在的数据时。

---

![](img/7fd6fae5b9b162b7d4ee817a288fe5b3_2.png)

## 什么是 `null`？ 🤔

在编写从CSV文件中查找最高温度的算法时，我们写下了一些步骤，这些步骤对应着Java中一个尚未介绍的概念：**“无”** 的概念。如何将“没有东西”这个想法转化为代码呢？

这引出了Java中一个重要的新概念：`null`。在Java以及许多其他编程语言中，`null`意味着“无”或“没有对象”。这个概念非常重要，因为在算法中，经常需要引用一个“不存在”的值。

---

## `null` 的用途 🛠️

![](img/7fd6fae5b9b162b7d4ee817a288fe5b3_4.png)

`null`主要有两种用途。

### 1. 初始化变量

你可以用`null`来初始化一个变量。例如，代码 `CSVRecord largestSoFar = null;` 意味着将 `largestSoFar` 初始化为“不存在任何东西”。

![](img/7fd6fae5b9b162b7d4ee817a288fe5b3_6.png)

### 2. 表示不存在的答案

当算法需要表示“答案不存在”或“没有这样的东西”时，从方法中返回`null`是一种恰当的表示方式。

---

![](img/7fd6fae5b9b162b7d4ee817a288fe5b3_8.png)

## 检查 `null` ✅

![](img/7fd6fae5b9b162b7d4ee817a288fe5b3_10.png)

在算法中，检查一个表达式是否等于`null`非常有用。你可以使用 `==` 操作符进行检查。

![](img/7fd6fae5b9b162b7d4ee817a288fe5b3_12.png)

在正在编写的算法中，你需要检查 `largestSoFar` 是否为空，即 `if (largestSoFar == null)`。

---

## `null` 的陷阱：空指针异常 ⚠️

![](img/7fd6fae5b9b162b7d4ee817a288fe5b3_14.png)

有一件事你不能对`null`值做：**调用它的方法**。因为`null`意味着没有对象，尝试在一个“不存在的东西”上调用方法是毫无意义的。

例如，以下代码虽然可以编译通过，但存在问题：
```java
CSVRecord record = null;
String value = record.get("Temperature");
```
第二行代码在运行时会导致程序崩溃。

![](img/7fd6fae5b9b162b7d4ee817a288fe5b3_16.png)

你会收到类似这样的错误信息：
```
Exception in thread "main" java.lang.NullPointerException
```
这个错误信息告诉你程序出了问题。

![](img/7fd6fae5b9b162b7d4ee817a288fe5b3_18.png)

*   **`Exception`** 通常意味着你的程序出现了错误。
*   **`java.lang.NullPointerException`** 表示你试图对`null`执行需要一个实际对象才能完成的操作，在本例中就是尝试调用它的方法。

---

## `null` 的类型之谜 🔍

在讨论`null`时，请记住所有表达式都有类型。之前我们学过，在编写和思考代码时，了解表达式的类型非常重要。这就引出了一个重要问题：`null`是什么类型？

我们写了 `CSVRecord largestSoFar = null;` 并告诉你这是合法的。那么，`null`的类型似乎是`CSVRecord`。但这真的合理吗？Java会被设计成“无”的类型是`CSVRecord`吗？我们难道不应该也能为其他类型表示“无”吗？

实际上，Java有一个特殊的**`null`类型**。与其他类型不同，你无法在程序中写出这个类型的名称。你不能声明这种`null`类型的变量，也不能创建返回类型是这种特殊类型的方法。

![](img/7fd6fae5b9b162b7d4ee817a288fe5b3_20.png)

字面量`null`是一个特殊类型，并且这个类型可以**转换为任何对象类型**。也就是说，Java允许你将它赋值给任何对象类型的变量，从返回类型是对象类型的方法中返回它，或者将它与其他任何类型的对象进行比较。

![](img/7fd6fae5b9b162b7d4ee817a288fe5b3_21.png)

---

![](img/7fd6fae5b9b162b7d4ee817a288fe5b3_23.png)

![](img/7fd6fae5b9b162b7d4ee817a288fe5b3_24.png)

## 原始类型与对象类型 📦

![](img/7fd6fae5b9b162b7d4ee817a288fe5b3_26.png)

你可能注意到我们刚才说的是“任何**对象类型**”，而不是“任何类型”。这是因为Java的类型分为两大类：**原始类型**和**对象类型**。

**原始类型不能为`null`**。
到目前为止，你已经见过四种原始类型：`int`、`double`、`char`和`boolean`。还有另外四种你没见过的：`byte`、`short`、`long`和`float`。这些类型是Java内置的，它们只是纯数据，没有任何与之关联的方法，并且**不能为`null`**。

**另一类是对象类型，它可以为`null`**。
到目前为止，你已经见过许多对象类型，例如`FileResource`、`String`、`CSVRecord`和`Pixel`等等。通常，任何包含方法的类型都是对象类型。同样，你编写的任何类也都是对象类型。

![](img/7fd6fae5b9b162b7d4ee817a288fe5b3_28.png)

原始类型和对象类型之间还有其他一些区别，但目前与我们无关，你将在以后学习它们。

---

## 总结 📝

本节课中，我们一起学习了Java中的`null`值。我们了解到：
*   `null` 表示“无对象”或“不存在”。
*   它常用于**初始化变量**或表示**方法没有有效返回值**。
*   可以使用 `==` 操作符来**检查一个变量是否为`null`**。
*   在`null`上调用方法会导致**`NullPointerException`** 运行时错误。
*   `null` 本身有一个特殊的类型，它可以被赋值给任何**对象类型**的变量。
*   Java的类型分为**原始类型**（如`int`, `double`，不能为`null`）和**对象类型**（如`String`, `CSVRecord`，可以为`null`）。

![](img/7fd6fae5b9b162b7d4ee817a288fe5b3_30.png)

理解并正确使用`null`是避免常见编程错误、编写更可靠代码的关键一步。