# Java编程和软件工程基础：2-5：字符类 🆎

在本节课中，我们将学习Java中的`Character`类。这个类提供了多种方法，用于判断字符值的属性，例如判断一个字符是否为数字或字母，以及进行大小写转换。

## 概述 📋

`char`是Java中的一种基本数据类型，类似于`int`、`boolean`和`double`。字符值使用单引号指定，例如 `'a'`、`'1'` 和 `' '`。而双引号，如 `"a"`，则表示字符串值。

![](img/6ac0b50bf70d0f9ec9b6e4f6109f655d_1.png)

`Character`类提供了许多有用的静态方法。你可能还记得`Integer.parseInt`和`Double.parseDouble`方法，它们分别属于`Integer`和`Double`类。`Character`类也以类似的方式工作。

## 核心方法与概念 🔧

以下是`Character`类中一些常用的方法。

### 大小写转换方法

`Character.toLowerCase`方法将其参数转换为小写形式并返回。例如，`Character.toLowerCase('G')` 会返回 `'g'`。如果传入的字符已经小写，则返回原值。同样地，`Character.toUpperCase`方法用于转换为大写。

**代码示例：**
```java
char lowerG = Character.toLowerCase('G'); // 结果为 'g'
char upperA = Character.toUpperCase('a'); // 结果为 'A'
```

### 判断方法

`Character`类还包含一系列返回布尔值的方法，用于判断字符的属性。

**以下是几个关键的判断方法：**
*   `Character.isLowerCase(char ch)`: 判断字符是否为小写字母。
*   `Character.isUpperCase(char ch)`: 判断字符是否为大写字母。
*   `Character.isDigit(char ch)`: 判断字符是否为数字。
*   `Character.isLetter(char ch)`: 判断字符是否为字母。

![](img/6ac0b50bf70d0f9ec9b6e4f6109f655d_3.png)

## 实践演示 💻

![](img/6ac0b50bf70d0f9ec9b6e4f6109f655d_4.png)

上一节我们介绍了`Character`类的核心方法，本节中我们通过具体代码来看看这些方法如何应用。

### 示例一：判断字符属性

我们有一个`digitTest`方法。它创建了一个包含大写字母、小写字母、数字和标点符号的测试字符串。然后，它遍历字符串中的每个字符，并调用`Character.isDigit`和`Character.isLetter`方法进行判断。

运行此方法后，控制台会清晰地显示：大写和小写字母被标记为字母，数字字符被标记为数字，而标点符号既不是字母也不是数字。

此外，代码中还演示了如何直接比较字符：
```java
if (ch == '#') {
    System.out.println("It's a hashtag.");
}
```
这提醒我们，字符使用单引号，而字符串使用双引号。

### 示例二：字符转换

在`conversionTest`方法中，我们创建了类似的测试字符串。遍历时，我们为每个字符调用`Character.toUpperCase`和`Character.toLowerCase`方法，并打印原始字符、大写形式和小写形式。

运行结果会显示三列：原始字符、转换后的大写字符和转换后的小写字符。可以看到，数字和标点符号在转换前后保持不变；字母则会被正确转换。

![](img/6ac0b50bf70d0f9ec9b6e4f6109f655d_6.png)

**代码片段回顾：**
```java
char ch = testString.charAt(i);
char upperCh = Character.toUpperCase(ch);
char lowerCh = Character.toLowerCase(ch);
System.out.println(ch + "\t" + upperCh + "\t" + lowerCh);
```

![](img/6ac0b50bf70d0f9ec9b6e4f6109f655d_7.png)

## 总结 🎯

本节课中我们一起学习了Java的`Character`类。我们了解了`char`基本类型，并掌握了如何使用`Character`类的方法来判断字符属性（如是否为数字或字母）以及进行大小写转换。熟练查阅Java官方文档中关于`Character`类的说明，将有助于你在处理字符时编写出更流畅、健壮的代码。