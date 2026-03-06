# JavaScript 条件语句教程：第08章：if-else 与 switch 语句

## 概述

在本节课中，我们将学习 JavaScript 中的条件语句。条件语句允许你根据不同的条件执行不同的操作。我们将重点介绍两种最常见的条件语句：`if...else` 语句和 `switch` 语句。

![](img/d4d0c4afdf8934900efd721cc4f69996_1.png)

## if...else 语句

上一节我们介绍了条件语句的基本概念，本节中我们来看看 `if...else` 语句。`if...else` 语句允许你根据一个条件是真是假来执行不同的代码块。

以下是 `if...else` 语句的基本语法：

```javascript
if (condition) {
    // 条件为真时执行的代码
} else {
    // 条件为假时执行的代码
}
```

现在，让我们通过一个例子来理解 `if...else` 条件。

```javascript
let age = 18;

if (age >= 18) {
    console.log("你是一个成年人。");
} else {
    console.log("你还不是一个成年人。");
}
```

![](img/d4d0c4afdf8934900efd721cc4f69996_3.png)

在这个例子中，`if` 语句检查变量 `age` 的值是否大于或等于 18。如果条件为真，则执行 `if` 后面花括号内的代码。如果条件为假，则执行 `else` 后面花括号内的代码。

`else` 条件是可选的，你可以只使用 `if` 条件。但使用 `else` 可以更轻松地处理边界情况。

## switch 语句

![](img/d4d0c4afdf8934900efd721cc4f69996_5.png)

接下来，我们学习 `switch` 语句。`switch` 语句是 JavaScript 中另一种条件语句，它允许你将一个变量与一系列值进行比较，并根据匹配情况执行不同的代码块。

以下是 `switch` 语句的基本语法：

```javascript
switch (expression) {
    case value1:
        // 当 expression 等于 value1 时执行的代码
        break;
    case value2:
        // 当 expression 等于 value2 时执行的代码
        break;
    default:
        // 当没有匹配的 case 时执行的代码
        break;
}
```

现在，让我们创建一个 `switch` 语句的例子。

```javascript
let day = 2;

switch (day) {
    case 1:
        console.log("星期一");
        break;
    case 2:
        console.log("星期二");
        break;
    // 可以继续添加 case 3 到 case 5 对应星期三到星期五
    default:
        console.log("无效的日期");
        break;
}
```

在这个例子中，`switch` 语句检查变量 `day` 的值，并执行与匹配的 `case` 标签关联的代码块。如果 `day` 的值是 2，它将输出“星期二”。如果 `day` 的值是 10（或其他不匹配的值），它将输出“无效的日期”。

![](img/d4d0c4afdf8934900efd721cc4f69996_7.png)

## 总结

本节课中我们一起学习了 JavaScript 中的条件语句。条件语句允许你根据条件是真还是假来执行不同的代码块。

`if...else` 语句用于测试单个条件，并根据其真假值执行不同的代码块。而 `switch` 语句用于将一个变量与一系列值进行比较，并根据匹配情况执行不同的代码块。

一个重要的注意事项是，`switch` 语句通常用作一长串 `if...else` 语句的替代方案，以使代码更具可读性，尤其是在需要检查许多情况时。

![](img/d4d0c4afdf8934900efd721cc4f69996_9.png)

在下一节课中，我们将学习 JavaScript 中的循环结构。