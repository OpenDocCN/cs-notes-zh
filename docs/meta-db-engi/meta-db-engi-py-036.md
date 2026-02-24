# 数据库工程师：P36：什么是函数式编程 🧮

在本节课中，我们将要学习函数式编程的基本概念。这是一种与面向对象编程等模型不同的编程范式，特别擅长高速处理大量数据。我们将探讨纯函数、递归、字符串反转以及Python中实用的`map`和`filter`函数。

## 函数的角色

首先，我们来探讨函数的作用。函数接收一些输入，进行处理，然后产生一些输出。函数主要分为两种类型：传统函数和纯函数。

![](img/cecb9b8ecdf1ee765a5ed13ce4c520da_1.png)
![](img/cecb9b8ecdf1ee765a5ed13ce4c520da_2.png)

纯函数无论被调用多少次，总是执行相同的操作并返回相同的结果。传统函数和纯函数之间存在几个关键区别。

以下是它们的主要区别：

![](img/cecb9b8ecdf1ee765a5ed13ce4c520da_1.png)

![](img/cecb9b8ecdf1ee765a5ed13ce4c520da_2.png)

![](img/cecb9b8ecdf1ee765a5ed13ce4c520da_4.png)

*   传统函数可以访问和修改全局状态中的变量，但纯函数不能。
*   传统函数和纯函数都可以访问局部状态中的变量。
*   传统函数可以改变状态，而纯函数不能。
*   传统函数的输出不依赖于输入，而纯函数的输出则依赖于输入。

## 函数式编程的本质

![](img/cecb9b8ecdf1ee765a5ed13ce4c520da_4.png)

上一节我们介绍了函数的类型，本节中我们来看看函数式编程的核心思想。

![](img/cecb9b8ecdf1ee765a5ed13ce4c520da_6.png)

函数式编程本质上是一种利用函数来编写清晰、一致且可维护代码的编程范式。

![](img/cecb9b8ecdf1ee765a5ed13ce4c520da_8.png)
![](img/cecb9b8ecdf1ee765a5ed13ce4c520da_9.png)

![](img/cecb9b8ecdf1ee765a5ed13ce4c520da_6.png)

与我们之后将学习的面向对象编程相比，函数式编程在设计上有所不同。

![](img/cecb9b8ecdf1ee765a5ed13ce4c520da_11.png)

![](img/cecb9b8ecdf1ee765a5ed13ce4c520da_8.png)

![](img/cecb9b8ecdf1ee765a5ed13ce4c520da_9.png)

函数式编程不会改变函数作用域之外的数据。

![](img/cecb9b8ecdf1ee765a5ed13ce4c520da_13.png)

![](img/cecb9b8ecdf1ee765a5ed13ce4c520da_11.png)

这意味着函数应避免修改输入数据或传递的参数，而应只返回被调用函数的预期结果。

![](img/cecb9b8ecdf1ee765a5ed13ce4c520da_13.png)

![](img/cecb9b8ecdf1ee765a5ed13ce4c520da_15.png)
![](img/cecb9b8ecdf1ee765a5ed13ce4c520da_16.png)

函数被认为是独立或自包含的，这有助于代码的简洁和优雅。

![](img/cecb9b8ecdf1ee765a5ed13ce4c520da_18.png)

![](img/cecb9b8ecdf1ee765a5ed13ce4c520da_15.png)

![](img/cecb9b8ecdf1ee765a5ed13ce4c520da_16.png)

事实上，许多强类型的面向对象语言已将函数式编程融入其结构中。为了支持函数式编程，语言本身需要允许将函数作为参数传递，并允许函数将另一个函数返回给其调用者。

## Python中的函数

![](img/cecb9b8ecdf1ee765a5ed13ce4c520da_18.png)

了解了函数式编程的原则后，我们来看看它在Python中的体现。

![](img/cecb9b8ecdf1ee765a5ed13ce4c520da_20.png)
![](img/cecb9b8ecdf1ee765a5ed13ce4c520da_21.png)

在Python中，函数是所谓的“一等公民”。这本质上意味着它们与字符串和数字具有同等的地位。

![](img/cecb9b8ecdf1ee765a5ed13ce4c520da_20.png)

![](img/cecb9b8ecdf1ee765a5ed13ce4c520da_23.png)
![](img/cecb9b8ecdf1ee765a5ed13ce4c520da_24.png)

![](img/cecb9b8ecdf1ee765a5ed13ce4c520da_21.png)

它们可以被赋值给变量、作为参数传递或返回给调用者。

![](img/cecb9b8ecdf1ee765a5ed13ce4c520da_26.png)

![](img/cecb9b8ecdf1ee765a5ed13ce4c520da_23.png)

![](img/cecb9b8ecdf1ee765a5ed13ce4c520da_24.png)

## Python内置函数示例

现在，让我们探索几个Python中可用的函数示例。以`sorted`函数为例。

![](img/cecb9b8ecdf1ee765a5ed13ce4c520da_26.png)

`sorted`函数接受一个项目列表，然后返回一个排序后的列表。

![](img/cecb9b8ecdf1ee765a5ed13ce4c520da_28.png)

![](img/cecb9b8ecdf1ee765a5ed13ce4c520da_28.png)

你可以使用`sorted`函数按字母顺序列出项目。通过将一个咖啡列表传递给`sorted`函数，返回的结果是按字母顺序排序的列表。

```python
coffees = [‘Latte‘, ‘Espresso‘, ‘Cappuccino‘]
sorted_coffees = sorted(coffees)
print(sorted_coffees)  # 输出: [‘Cappuccino‘, ‘Espresso‘, ‘Latte‘]
```

![](img/cecb9b8ecdf1ee765a5ed13ce4c520da_30.png)

![](img/cecb9b8ecdf1ee765a5ed13ce4c520da_30.png)

函数式编程的一大优点是，某些任务背后的逻辑已经为你内置好了。函数是可重用的，因此节省了大量开发时间。

## 创建自定义函数

但你是否知道，你也可以根据自身需求创建特定的函数？让我们看一个简单的例子。假设你想将咖啡的名字倒序拼写。

![](img/cecb9b8ecdf1ee765a5ed13ce4c520da_32.png)

![](img/cecb9b8ecdf1ee765a5ed13ce4c520da_32.png)

这可能不完全实用，但它很好地展示了函数式编程。

![](img/cecb9b8ecdf1ee765a5ed13ce4c520da_34.png)

![](img/cecb9b8ecdf1ee765a5ed13ce4c520da_34.png)

你可以创建自己的简单反转函数来实现这一点。定义函数，我们称之为`reverse_string`，并为其分配变量`str`。现在使用切片函数返回`str`的值。你将在课程后面了解更多关于切片函数的知识。

```python
def reverse_string(s):
    return s[::-1]
```

然后，将一个变量赋值为`map`函数的结果。`map`函数接受反转函数作为其第一个参数，然后是可迭代的咖啡列表。它会自动处理迭代，遍历每种咖啡并对其应用反转函数。

```python
coffees = [‘Latte‘, ‘Espresso‘, ‘Cappuccino‘]
reversed_coffees = list(map(reverse_string, coffees))
print(reversed_coffees)  # 输出: [‘ettaL‘, ‘osserpsE‘, ‘oniccuppaC‘]
```

![](img/cecb9b8ecdf1ee765a5ed13ce4c520da_36.png)

![](img/cecb9b8ecdf1ee765a5ed13ce4c520da_36.png)

## 总结

本节课中，我们一起学习了函数式编程是什么，并介绍了Python中内置函数的例子。我们了解了纯函数与传统函数的区别，函数式编程的核心原则，以及如何在Python中利用函数作为一等公民的特性来编写清晰、可复用的代码。