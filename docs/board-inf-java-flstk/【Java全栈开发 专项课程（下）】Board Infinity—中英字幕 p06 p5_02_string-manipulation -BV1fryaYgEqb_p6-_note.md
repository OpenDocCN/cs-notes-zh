# Java全栈开发：06：字符串操作 📝

![](img/1446e815ab4b67c6d79c3fbab523cb67_0.png)

在本节课中，我们将学习如何在Java中声明和操作字符串。我们将使用字符串字面量、字符串对象以及各种字符串方法来完成常见的任务。

![](img/1446e815ab4b67c6d79c3fbab523cb67_2.png)

---

## 字符串的声明

首先，我们来看看如何声明字符串。在Java中，主要有两种方式：使用字符串字面量和使用`new`关键字创建字符串对象。

以下是两种声明方式的示例：

```java
// 使用字符串字面量声明
String str1 = "Hello";

![](img/1446e815ab4b67c6d79c3fbab523cb67_4.png)

// 使用字符串对象声明
String str2 = new String("World");
```

你可以通过`System.out.println()`方法来打印这些字符串，以验证它们的内容。

---

## 字符串的拼接

上一节我们介绍了如何声明字符串，本节中我们来看看如何将多个字符串连接在一起。你可以使用加号`+`运算符来拼接字符串字面量和字符串对象。

以下是拼接字符串的示例：

```java
// 拼接字符串字面量和字符串对象
String str3 = str1 + str2;
System.out.println(str3);
```

运行这段代码，你将看到输出结果为`HelloWorld`。

![](img/1446e815ab4b67c6d79c3fbab523cb67_6.png)

---

## 常用的字符串方法

Java提供了许多内置的字符串方法，用于执行各种操作。以下是几个最常用的方法：

1.  **`length()`**：计算字符串的长度，包括空格。
2.  **`charAt(index)`**：获取字符串中指定索引位置的字符。
3.  **`concat(string)`**：将当前字符串与另一个字符串连接。
4.  **`substring(startIndex, endIndex)`**：提取字符串中从`startIndex`到`endIndex-1`的子串。
5.  **`equals(string)`**：比较两个字符串是否相等。
6.  **`contains(substring)`**：检查字符串是否包含指定的子串。
7.  **`toUpperCase()`**：将字符串转换为大写。
8.  **`toLowerCase()`**：将字符串转换为小写。
9.  **`trim()`**：移除字符串两端的空白字符。

---

## 字符串方法示例

让我们通过一些代码示例来演示这些方法的具体用法：

```java
// 计算字符串长度
int length = str3.length();
System.out.println("Length: " + length);

// 获取指定索引的字符
char firstChar = str3.charAt(0);
System.out.println("First character: " + firstChar);

// 使用concat方法拼接字符串
String concatenated = str1.concat(str2);
System.out.println("Concatenated: " + concatenated);

// 提取子串
String substring = str3.substring(0, 5);
System.out.println("Substring: " + substring);

// 比较字符串是否相等
boolean isEqual = str1.equals(str2);
System.out.println("Are they equal? " + isEqual);

// 检查是否包含子串
boolean containsHello = str3.contains("Hello");
System.out.println("Contains 'Hello'? " + containsHello);

// 转换为大写
String upperCase = str3.toUpperCase();
System.out.println("Uppercase: " + upperCase);

// 转换为小写
String lowerCase = str3.toLowerCase();
System.out.println("Lowercase: " + lowerCase);

// 移除空白字符
String stringWithSpaces = "  Hello World  ";
String trimmed = stringWithSpaces.trim();
System.out.println("Trimmed: '" + trimmed + "'");
```

运行上述代码，你将看到每个方法的输出结果，从而更好地理解它们的功能。

---

![](img/1446e815ab4b67c6d79c3fbab523cb67_8.png)

## 总结

![](img/1446e815ab4b67c6d79c3fbab523cb67_10.png)

![](img/1446e815ab4b67c6d79c3fbab523cb67_11.png)

本节课中我们一起学习了Java中字符串的基本操作。我们首先介绍了如何使用字符串字面量和字符串对象来声明字符串，然后探讨了如何拼接字符串。接着，我们详细讲解了多个常用的字符串方法，并通过代码示例演示了它们的用法。掌握这些基础知识将帮助你在实际编程中更有效地处理字符串数据。