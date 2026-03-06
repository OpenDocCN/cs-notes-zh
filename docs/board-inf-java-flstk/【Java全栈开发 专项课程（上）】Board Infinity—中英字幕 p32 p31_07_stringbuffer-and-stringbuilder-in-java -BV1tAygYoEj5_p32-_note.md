Java全栈开发：07：StringBuffer与StringBuilder详解 🧵

![](img/180ac47cf3362a439316b49844259284_1.png)

在本节课中，我们将要学习Java中两个重要的类：`StringBuffer`和`StringBuilder`。我们将探讨它们与普通`String`类的区别，理解“可变性”的概念，并通过代码示例比较它们的性能与使用场景。

---

![](img/180ac47cf3362a439316b49844259284_3.png)

在上一节中，我们讨论了`String`及其方法，并了解到`String`对象是不可变的。这意味着每次修改字符串内容时，实际上都会创建一个新的`String`对象。

![](img/180ac47cf3362a439316b49844259284_1.png)

然而，`StringBuffer`是一个可变的类，这意味着它的内容可以被修改。它提供了一种在Java中创建可变字符串的方式，并且是线程安全的，允许多个线程同时安全地使用和修改它。

为了实现线程安全的优势，`StringBuffer`的实现相对较重。与之类似但不同的另一个类是`StringBuilder`。

![](img/180ac47cf3362a439316b49844259284_3.png)

`StringBuffer`拥有诸如`append`、`insert`、`delete`和`reverse`等方法，这些方法允许直接修改字符串内容。接下来，让我们通过实践来理解它。

以下是创建和使用`StringBuffer`的基本步骤：

1.  首先，需要实例化`StringBuffer`对象，它位于`java.lang`包中。
2.  可以为其分配一个初始字符串，例如“Hello”。
3.  使用`append`方法可以向现有内容追加新的字符串。
4.  可以打印出最终的字符串内容。

```java
StringBuffer buffer = new StringBuffer("Hello");
buffer.append(" World");
System.out.println(buffer.toString()); // 输出：Hello World
```

此外，你还可以检查`StringBuffer`的初始容量。如果初始化时不指定内容，它将有一个默认的初始容量。

```java
StringBuffer buffer = new StringBuffer();
System.out.println(buffer.capacity()); // 输出默认容量，例如 16
```

当你向其中添加内容时，容量会根据需要自动增加。这就是`StringBuffer`的基本工作原理。

---

接下来，我们将`StringBuffer`与`StringBuilder`进行比较。`StringBuilder`同样提供可变字符串的功能，但它缺乏线程安全性，因此不能被多个线程同时安全使用。这是两者之间的主要区别。

让我们也实现一个`StringBuilder`的示例：

```java
StringBuilder builder = new StringBuilder("Hello");
builder.append(" World");
System.out.println(builder.toString()); // 输出：Hello World
```

从表面上看，两者的操作和结果是相同的。但正如之前提到的，它们在性能上存在差异。为了展示这一点，我们可以进行一个简单的性能测试。

我们将分别使用`StringBuffer`和`StringBuilder`执行大量追加操作，并计算各自所需的时间：

```java
// 测试 StringBuffer
long startTime = System.currentTimeMillis();
StringBuffer buffer = new StringBuffer("Hello");
for (int i = 0; i < 10000; i++) {
    buffer.append("World");
}
long timeTakenByBuffer = System.currentTimeMillis() - startTime;
System.out.println("Time taken by StringBuffer: " + timeTakenByBuffer + " ms");

// 测试 StringBuilder
startTime = System.currentTimeMillis();
StringBuilder builder = new StringBuilder("Hello");
for (int i = 0; i < 10000; i++) {
    builder.append("World");
}
long timeTakenByBuilder = System.currentTimeMillis() - startTime;
System.out.println("Time taken by StringBuilder: " + timeTakenByBuilder + " ms");
```

运行上述代码后，你会发现`StringBuilder`所花费的时间通常少于`StringBuffer`。

🎼 这是因为`StringBuilder`虽然不保证线程安全，但正因如此，它的实现更轻量，在单线程环境下执行修改操作的速度比`StringBuffer`更快。

---

本节课中我们一起学习了`StringBuffer`和`StringBuilder`。关键点总结如下：
*   **`String`是不可变的**，而**`StringBuffer`和`StringBuilder`是可变的**。
*   **`StringBuffer`是线程安全的**，但性能相对较低。
*   **`StringBuilder`不是线程安全的**，但在单线程环境下性能更高。
*   选择使用哪个类取决于你的具体需求：需要线程安全时用`StringBuffer`，追求单线程性能时用`StringBuilder`。

![](img/180ac47cf3362a439316b49844259284_5.png)

![](img/180ac47cf3362a439316b49844259284_5.png)