# Python编程入门：1-2：字符串基础 🧵

在本节课中，我们将要学习Python编程中一个非常基础且重要的概念：**字符串**。字符串是构成文本数据的基本单位，理解其定义和基本操作是编写程序的第一步。

## 什么是字符串？

![](img/2243abfb2dad70a31c21901005414ab0_1.png)

字符串是由单引号或双引号括起来的一系列字符。

例如，`'nice'` 是一个字符串。

![](img/2243abfb2dad70a31c21901005414ab0_3.png)

![](img/2243abfb2dad70a31c21901005414ab0_1.png)

同样，`"nice"` 也是一个字符串。

![](img/2243abfb2dad70a31c21901005414ab0_5.png)

![](img/2243abfb2dad70a31c21901005414ab0_3.png)

在Python中，用单引号和双引号定义的字符串是等价的。这意味着 `'nice'` 和 `"nice"` 是相同类型、相同值的字符串。

![](img/2243abfb2dad70a31c21901005414ab0_5.png)

## 字符串的连接

![](img/2243abfb2dad70a31c21901005414ab0_7.png)

我们可以使用加号 `+` 来连接（或链接）字符和字符串。

例如，`‘so’ + ‘ ‘ + ‘wow’` 的结果是 `‘so wow’`。`‘Python is so cool’` 也是一个字符串连接的例子。

![](img/2243abfb2dad70a31c21901005414ab0_7.png)

![](img/2243abfb2dad70a31c21901005414ab0_9.png)

当我们写下 `‘so’ + ‘ ‘ + ‘wow’` 时，Python知道我们试图将这三个字符串片段连接在一起。

![](img/2243abfb2dad70a31c21901005414ab0_10.png)

![](img/2243abfb2dad70a31c21901005414ab0_9.png)

![](img/2243abfb2dad70a31c21901005414ab0_10.png)

![](img/2243abfb2dad70a31c21901005414ab0_12.png)

## 检查数据类型

我们可以检查一个对象是否是字符串。使用 `type()` 函数可以查看对象的类型。

![](img/2243abfb2dad70a31c21901005414ab0_14.png)

例如，`type(‘yes’)` 的返回值是 `str`，表示这是一个字符串。

![](img/2243abfb2dad70a31c21901005414ab0_12.png)

同样，`type(“1.03”)` 的返回值也是 `str`，因为它是一个由数字字符组成的字符串。

![](img/2243abfb2dad70a31c21901005414ab0_16.png)

![](img/2243abfb2dad70a31c21901005414ab0_14.png)

作为对比，`type(1.03)` 的返回值是 `int`（或 `float`，取决于具体实现），因为它是一个数字。

![](img/2243abfb2dad70a31c21901005414ab0_18.png)

![](img/2243abfb2dad70a31c21901005414ab0_16.png)

## 打印字符串

我们可以使用 `print()` 函数输出多个字符串。`print()` 函数会将所有传入的参数依次打印出来，并默认用空格分隔。

例如，`print(‘name’, ‘Brandon’, ‘Krakowski’)` 会输出 `name Brandon Krakowski`。

![](img/2243abfb2dad70a31c21901005414ab0_20.png)

![](img/2243abfb2dad70a31c21901005414ab0_18.png)

我们也可以先使用加号 `+` 将字符串连接成一个整体，然后再打印。

例如，`print(‘name’ + ‘ ‘ + ‘Brandon’ + ‘ ‘ + ‘Krakowski’)`。

![](img/2243abfb2dad70a31c21901005414ab0_20.png)

![](img/2243abfb2dad70a31c21901005414ab0_22.png)

这行代码在 `print()` 命令内部将字符串 `‘name’`、空格、`‘Brandon’`、空格和 `‘Krakowski’` 连接起来，然后打印整个结果。其输出与直接打印多个参数的结果看起来完全相同。

![](img/2243abfb2dad70a31c21901005414ab0_22.png)

## 转义字符

最后，我们学习如何在字符串中使用特殊字符。在Python字符串中，反斜杠 `\` 是一个特殊字符，也称为**转义字符**。

例如，我们想打印：`Brandon’s last name is Krakowski`。如果直接写 `‘Brandon’s last name is Krakowski’`，Python会误认为第二个单引号是字符串的结束，从而导致语法错误。

![](img/2243abfb2dad70a31c21901005414ab0_24.png)

正确的写法是使用转义字符：`print(“Brandon\’s last name is Krakowski”)`。

![](img/2243abfb2dad70a31c21901005414ab0_24.png)

运行这行代码，会正确输出 `Brandon’s last name is Krakowski`。这里的反斜杠 `\` 是一个转义字符，它告诉Python紧随其后的单引号应被视为普通字符，而不是用于界定字符串的符号。

![](img/2243abfb2dad70a31c21901005414ab0_26.png)

---

![](img/2243abfb2dad70a31c21901005414ab0_26.png)

本节课中我们一起学习了Python字符串的基础知识。我们了解了字符串的定义方式（单引号或双引号）、如何使用加号进行连接、如何用 `type()` 函数检查类型、如何使用 `print()` 函数输出字符串，以及如何利用转义字符 `\` 在字符串中表示特殊符号。掌握这些概念是进行后续文本处理和更复杂编程的基础。