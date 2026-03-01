# 056：重构版本 🛠️

![](img/b7cacb23e5ff8f360efce6cab45534b7_0.png)

在本节课中，我们将学习一个重要的编程实践：**代码重构**。我们将通过一个具体的例子，了解如何识别并消除代码中的重复部分，从而提高代码的可维护性和健壮性。

## 概述

上一节我们实现了寻找最高温度的功能。虽然代码功能已经完成，但其中存在一个常见问题：**代码重复**。本节中，我们将学习如何通过提取公共代码到一个独立的方法中来解决这个问题，这个过程称为**重构**。

## 识别问题：代码重复

从功能上看，代码已经完成。但令人不适的是，在两个不同的方法中出现了大量重复的代码。

我知道代码重复是因为我在两个方法之间进行了复制和粘贴。在编程中，这不是一种好的实践。

![](img/b7cacb23e5ff8f360efce6cab45534b7_2.png)

因为如果那段代码存在问题，问题现在会在多个地方出现。你将不得不在所有不同的地方尝试修复它。

## 解决方案：提取公共方法

![](img/b7cacb23e5ff8f360efce6cab45534b7_4.png)

![](img/b7cacb23e5ff8f360efce6cab45534b7_6.png)

因此，我想做的是提取出那段公共代码，并将其放入一个独立的方法中。这里我将其命名为 `getLargestOfTwo`。这样我就可以在所有其他方法中重用那段代码。

![](img/b7cacb23e5ff8f360efce6cab45534b7_8.png)

我复制粘贴的部分是出现在“多日最高温”方法和“文件中最高温”方法中的同一个 `if` 语句。

以下是需要重构的重复逻辑的核心概念，它比较两个值并返回较大的一个：

```java
if (largestSoFar == null || currentTemp > largestSoFar) {
    largestSoFar = currentTemp;
}
```

我将从原方法中剪切这段代码，并将其放入 `getLargestOfTwo` 方法中，包括在最后返回“目前最大值”。

这样我就能得到正确的结果。我不需要对代码做任何修改，因为在我的特定案例中，所有变量命名都是一致的。两个方法都称当前值为 `currentRow`，最大值称为 `largestSoFar`。

![](img/b7cacb23e5ff8f360efce6cab45534b7_10.png)

![](img/b7cacb23e5ff8f360efce6cab45534b7_11.png)

`largestSoFar` 应该保持不变，除非它为 `null`，或者除非 `currentTemp` 更大。在这两种情况下，我应该更新 `largestSoFar`，否则 `largestSoFar` 就是正确的值。

## 实现重构方法

![](img/b7cacb23e5ff8f360efce6cab45534b7_13.png)

所以，我的方法将如下所示。它只包含那个 `if-else` 语句，以及它自己的返回语句。

```java
private double getLargestOfTwo(double currentVal, double largestSoFar) {
    if (largestSoFar == null || currentVal > largestSoFar) {
        return currentVal;
    } else {
        return largestSoFar;
    }
}
```

![](img/b7cacb23e5ff8f360efce6cab45534b7_15.png)

## 应用重构方法

现在，我可以在原方法中使用它。将原来的 `if` 语句替换为一行代码：

![](img/b7cacb23e5ff8f360efce6cab45534b7_17.png)

```java
largestSoFar = getLargestOfTwo(currentRow, largestSoFar);
```

![](img/b7cacb23e5ff8f360efce6cab45534b7_19.png)

这行代码将完成 `if` 语句的工作，并将结果存储在那里。

同样地，我现在可以将这一行代码复制并粘贴到“多文件最高温”方法中，再次替换掉相同的 `if-else` 逻辑。

我从文件中获取当前行，然后获取两者中的较大值。

## 编译与测试

![](img/b7cacb23e5ff8f360efce6cab45534b7_21.png)

现在让我们继续编译，以确保一切正常。哦，我是不是拼错了什么？没有大写？

![](img/b7cacb23e5ff8f360efce6cab45534b7_22.png)

然后，因为我复制粘贴了它，所以我必须修复两次，这正是我之前警告过你的问题。所以现在，希望在我修复了这两处之后，它能编译通过。

![](img/b7cacb23e5ff8f360efce6cab45534b7_24.png)

现在我们必须返回去测试它，以确保一切都是正确的。我将创建一个新的 CSV 文件进行测试，因为即使我移动了代码，它也不应该改变功能，但我想实际确认这一点。

![](img/b7cacb23e5ff8f360efce6cab45534b7_25.png)

我将测试“单日最高温”。果然，它给出了 2015年1月2日的 54 度。

![](img/b7cacb23e5ff8f360efce6cab45534b7_27.png)

我将调用“多日最高温”方法，并返回去选择我们一直用于测试的那两天。果然，它仍然认为是 54 度。

## 总结

通过这次测试，我对移动代码所做的更改没有影响功能感到满意。但现在我对我的代码更有信心了，因为那段被重复的大段代码，现在我已经处理好了，它只出现在一个地方。所以，如果我以后发现那段代码有问题，我可以回到那一个地方进行修复。

![](img/b7cacb23e5ff8f360efce6cab45534b7_29.png)

本节课中，我们一起学习了**代码重构**的核心价值：通过消除重复代码，将公共逻辑提取为独立方法，我们提升了代码的**可维护性**和**可读性**。记住，避免复制粘贴，时刻思考代码的复用性，是成为优秀程序员的重要一步。