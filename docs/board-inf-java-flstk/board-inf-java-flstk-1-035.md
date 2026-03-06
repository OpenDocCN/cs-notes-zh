# 035：条件结构实战指南

![](img/d59779a97f3f7b6a7adbd69df60406ed_0.png)

在本节课中，我们将学习Java中条件结构的使用方法。我们将通过实际例子，了解`if`、`if-else`、`if-else-if`以及嵌套条件语句的工作原理，并探讨如何将条件语句与逻辑运算符结合使用。

![](img/d59779a97f3f7b6a7adbd69df60406ed_2.png)

---

## 简单的 `if` 语句

首先，我们来看一个简单的`if`语句。假设我们有一个布尔变量`isAuthenticated`，它存储用户是否已通过身份验证。

```java
boolean isAuthenticated = true;
if (isAuthenticated == true) {
    System.out.println("Logged in");
}
```

如果`isAuthenticated`的值为`true`，程序将输出“Logged in”。否则，程序将跳过这个代码块，不执行任何操作。

---

## `if-else` 语句

上一节我们介绍了简单的`if`语句，本节中我们来看看`if-else`语句。当我们需要处理一个条件及其相反情况时，`if-else`结构非常有用。

以下是使用`if-else`重写的例子：

```java
boolean isAuthenticated = true;
if (isAuthenticated == true) {
    System.out.println("Logged in");
} else {
    System.out.println("Not logged in");
}
```

在这个结构中，如果条件为真，则执行`if`块；如果条件为假，则执行`else`块。

---

## `if-else-if` 阶梯语句

接下来，我们探讨更复杂的情况。假设我们需要根据商品的售价和成本价判断盈利状况。

以下是使用多个独立`if`语句的实现方式：

```java
float sellingPrice = 1200;
float costPrice = 1000;

if (sellingPrice > costPrice) {
    System.out.println("Profit");
}
if (costPrice > sellingPrice) {
    System.out.println("Loss");
}
if (sellingPrice == costPrice) {
    System.out.println("No profit, no loss");
}
```

然而，这种方法存在性能问题，因为即使第一个条件为真，程序仍会检查所有后续的`if`语句。

为了优化，我们可以使用`if-else-if`阶梯语句：

```java
float sellingPrice = 1200;
float costPrice = 1000;

if (sellingPrice > costPrice) {
    System.out.println("Profit");
} else if (costPrice > sellingPrice) {
    System.out.println("Loss");
} else {
    System.out.println("No profit, no loss");
}
```

在这种结构中，一旦某个条件为真，执行相应的代码块后，程序就会跳出整个条件判断，不再检查后续条件，从而提高了效率。

---

## 嵌套的 `if-else` 语句

我们也可以使用嵌套的`if-else`语句来实现相同的逻辑：

```java
float sellingPrice = 1200;
float costPrice = 1000;

![](img/d59779a97f3f7b6a7adbd69df60406ed_4.png)

if (sellingPrice > costPrice) {
    System.out.println("Profit");
} else {
    if (costPrice > sellingPrice) {
        System.out.println("Loss");
    } else {
        System.out.println("No profit, no loss");
    }
}
```

嵌套`if-else`和`if-else-if`阶梯语句的输出结果是相同的，你可以根据代码的可读性和逻辑清晰度来选择使用哪一种。

---

## 结合逻辑运算符

在之前的模块中，我们学习了运算符。现在，我们来看看如何将条件语句与逻辑运算符结合使用。

假设有三个布尔变量，分别表示用户是否登录、邮箱是否验证、支付卡信息是否有效。只有当所有条件都为真时，才允许用户进行购买。

以下是使用逻辑运算符`&&`的实现方式：

```java
boolean isLoggedIn = true;
boolean isEmailVerified = false;
boolean isCardInfoValid = true;

if (isLoggedIn && isEmailVerified && isCardInfoValid) {
    System.out.println("You are allowed to make a purchase.");
} else {
    System.out.println("You are not allowed to make a purchase.");
}
```

这种方法简洁明了，使用`&&`运算符确保所有条件必须同时为真。

---

## 使用嵌套条件实现

同样的逻辑也可以使用嵌套的`if`语句来实现：

```java
boolean isLoggedIn = true;
boolean isEmailVerified = false;
boolean isCardInfoValid = true;

if (isLoggedIn) {
    if (isEmailVerified) {
        if (isCardInfoValid) {
            System.out.println("You are allowed to make a purchase.");
        } else {
            System.out.println("Card info invalid. Purchase not allowed.");
        }
    } else {
        System.out.println("Email not verified. Purchase not allowed.");
    }
} else {
    System.out.println("Not logged in. Purchase not allowed.");
}
```

嵌套方式可以让你为每个失败的条件提供更具体的错误信息，但代码结构会更复杂。选择哪种方式取决于你的具体需求和逻辑清晰度。

---

## 总结

本节课中我们一起学习了Java中条件结构的使用。
*   我们了解了基础的`if`语句。
*   我们学习了如何处理两种对立情况的`if-else`语句。
*   我们探讨了用于处理多个互斥条件的`if-else-if`阶梯语句及其性能优势。
*   我们看到了使用嵌套`if-else`实现相同逻辑的另一种方式。
*   最后，我们结合逻辑运算符，学习了如何高效地检查多个条件。

![](img/d59779a97f3f7b6a7adbd69df60406ed_6.png)

![](img/d59779a97f3f7b6a7adbd69df60406ed_8.png)

掌握这些条件结构是进行Java编程决策和流程控制的基础。