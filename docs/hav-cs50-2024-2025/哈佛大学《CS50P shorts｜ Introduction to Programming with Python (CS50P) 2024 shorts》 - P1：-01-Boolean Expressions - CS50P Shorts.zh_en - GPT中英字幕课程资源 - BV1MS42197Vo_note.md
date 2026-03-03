# Python编程入门：01：布尔表达式

![](img/7af27a3ffbd98e722ebde863387af091_0.png)

![](img/7af27a3ffbd98e722ebde863387af091_0.png)

在本节课中，我们将要学习布尔表达式。布尔表达式是编程中用于判断条件真假的表达式，它们通常返回 `True` 或 `False` 值。通过结合布尔运算符，我们可以构建更复杂的逻辑判断，从而编写出更简洁、更高效的代码。

## 课程概述

在之前关于条件语句的课程中，我们编写了一个根据用户偏好的难度和玩家数量来推荐纸牌游戏的程序。本节课，我们将探讨如何改进该程序的设计，重点是利用布尔表达式和布尔运算符来减少代码重复，并更早地验证用户输入的有效性。

## 改进程序设计的思路

上一节我们介绍了条件语句的基本用法。本节中我们来看看如何优化程序逻辑。观察之前的代码，我们发现存在大量重复的条件判断。例如，检查用户输入的难度和玩家数量是否有效的代码块非常相似。这种重复不仅使代码冗长，也降低了可维护性。

以下是我们可以改进的几个方面：
1.  在程序开始时就验证用户输入是否符合预期。
2.  使用布尔运算符组合多个条件，减少嵌套的 `if` 语句。
3.  使代码逻辑更清晰，更易于阅读。

## 使用布尔表达式验证输入

首先，我们可以在获取用户输入后，立即检查其有效性。我们希望确保用户输入的难度是“difficult”或“casual”，玩家模式是“multiplayer”或“single player”。

一个基本的布尔表达式示例如下：
```python
difficulty == "difficult"
```
这个表达式会判断变量 `difficulty` 的值是否等于字符串 `"difficult"`，并返回 `True` 或 `False`。

但是，我们需要检查用户输入是否是“difficult”**或**“casual”。这时，我们可以使用布尔运算符 `or` 来组合两个表达式：
```python
difficulty == "difficult" or difficulty == "casual"
```
这个组合表达式只要其中一个子表达式为真，整个表达式就为真。

然而，我们的目标实际上是检查用户输入**是否不**在这两个有效选项之内。为此，我们可以使用另一个布尔运算符 `not`。`not` 运算符会对其后的表达式结果进行取反（真变假，假变真）。

因此，完整的验证逻辑可以写成：
```python
if not (difficulty == "difficult" or difficulty == "casual"):
    print("Enter a valid difficulty.")
    return
```
这段代码的意思是：如果用户输入的难度**不是**“difficult”**也**不是“casual”，则提示用户输入有效的难度，并结束程序。

我们可以对玩家数量的输入进行同样的验证：
```python
if not (players == "multiplayer" or players == "single player"):
    print("Enter a valid number of players.")
    return
```
通过这种方式，我们在程序逻辑深入之前就处理了无效输入，使代码结构更清晰。

## 使用布尔运算符简化游戏推荐逻辑

在验证了输入的有效性后，我们进入游戏推荐的核心逻辑。之前的代码使用了多层嵌套的 `if-else` 语句。我们可以使用布尔运算符 `and` 来同时检查两个条件，从而简化结构。

例如，推荐“poker”游戏的条件是：难度为“difficult”**且**玩家模式为“multiplayer”。我们可以用 `and` 运算符将其合并为一个条件：
```python
if difficulty == "difficult" and players == "multiplayer":
    print("Poker")
```
类似地，我们可以为其他三种组合定义条件：
```python
elif difficulty == "difficult" and players == "single player":
    print("Klondike")
elif difficulty == "casual" and players == "multiplayer":
    print("Hearts")
```
最后，由于我们已经确保了输入只能是两种难度和两种玩家模式的四种有效组合，前三个条件都不满足时，就只剩下“casual”和“single player”这一种情况。因此，我们可以直接用 `else` 来处理：
```python
else:
    print("Clock")
```
这种写法将原本可能冗长的条件判断浓缩为几个清晰、并列的逻辑分支。

## 测试改进后的程序

让我们来测试一下改进后的程序是否按预期工作。

1.  **测试无效难度输入**：当输入“medium”作为难度时，程序应提示“Enter a valid difficulty.”。
2.  **测试无效玩家数量输入**：当输入“difficult”和“two player”时，程序应提示“Enter a valid number of players.”。
3.  **测试四种有效组合**：
    *   输入“difficult”和“multiplayer”，应推荐“Poker”。
    *   输入“difficult”和“single player”，应推荐“Klondike”。
    *   输入“casual”和“multiplayer”，应推荐“Hearts”。
    *   输入“casual”和“single player”，应推荐“Clock”。

经过测试，程序在所有情况下都运行正确。

![](img/7af27a3ffbd98e722ebde863387af091_2.png)

![](img/7af27a3ffbd98e722ebde863387af091_2.png)

## 课程总结

本节课中我们一起学习了布尔表达式和布尔运算符（`and`, `or`, `not`）的用法。我们看到了如何利用它们来：
*   在程序早期验证用户输入。
*   将多个简单的条件组合成更复杂的逻辑判断。
*   简化条件语句的结构，使代码更简洁、更易读。

通过重构之前的游戏推荐程序，我们实践了这些概念，实现了相同的功能，但代码逻辑更加清晰和健壮。布尔表达式是构建程序逻辑的基础工具，熟练掌握它们对编写高效代码至关重要。