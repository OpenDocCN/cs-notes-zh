# 哈佛 CS50-WEB 7：L2- Python编程语言全解 1 (变量，字符串格式化，条件与循环) 🐍

![](img/7197b85a91b83e27dfb773cad9c71625_0.png)

![](img/7197b85a91b83e27dfb773cad9c71625_0.png)

在本节课中，我们将要学习Python编程语言的基础知识。Python是一门功能强大且易于上手的语言，非常适合用于构建应用程序。我们将从最简单的程序开始，逐步介绍变量、字符串格式化、条件判断、循环以及几种核心的数据结构。通过本节课的学习，你将能够编写并运行基本的Python程序。

## 第一个Python程序 👋

我们将从一个经典的“Hello World”程序开始。这个程序虽然简单，但它展示了Python程序的基本结构和运行方式。

在Python中，我们可以使用内置的 `print` 函数来输出信息。`print` 函数接收一个参数，这个参数就是要打印到屏幕上的内容。

以下是我们的第一个程序：

```python
print("hello world!")
```

为了运行这个程序，我们需要将其保存为一个以 `.py` 为扩展名的文件，例如 `hello.py`。然后，在终端中使用Python解释器来执行它。

```bash
python hello.py
```

运行后，你将在终端中看到输出：`hello world!`。这就是我们使用Python编写的第一个程序。

![](img/7197b85a91b83e27dfb773cad9c71625_10.png)

## 变量与数据类型 🔢

![](img/7197b85a91b83e27dfb773cad9c71625_12.png)

像许多编程语言一样，Python也支持变量。变量用于存储数据，以便在程序后续使用。

![](img/7197b85a91b83e27dfb773cad9c71625_14.png)

![](img/7197b85a91b83e27dfb773cad9c71625_16.png)

为变量赋值的语法非常简单。例如，`a = 28` 这行代码将整数值 `28` 存储在名为 `a` 的变量中。

与C或Java等语言不同，Python是一种动态类型语言。这意味着你不需要在声明变量时指定其类型，Python解释器会自动推断出值的类型。

![](img/7197b85a91b83e27dfb773cad9c71625_18.png)

以下是Python中一些常见的数据类型：

![](img/7197b85a91b83e27dfb773cad9c71625_20.png)

*   **整数 (int)**：例如 `28`。
*   **浮点数 (float)**：例如 `1.5`。
*   **字符串 (string)**：用单引号或双引号括起来的文本，例如 `‘hello’` 或 `“world”`。
*   **布尔值 (bool)**：表示真或假，写作 `True` 或 `False`。
*   **None类型**：表示没有值，写作 `None`。

## 获取用户输入与字符串操作 ⌨️

上一节我们介绍了变量，本节中我们来看看如何与用户交互。Python内置的 `input` 函数可以提示用户输入信息。

让我们编写一个程序，询问用户的名字并向他们问好。

```python
name = input("What‘s your name? ")
print("hello, " + name)
```

![](img/7197b85a91b83e27dfb773cad9c71625_22.png)

在这个程序中，`input` 函数显示提示信息并等待用户输入。用户输入的内容（一个字符串）被赋值给变量 `name`。然后，我们使用 `+` 运算符将字符串 `“hello, “` 和变量 `name` 的值连接起来，形成最终的问候语。

![](img/7197b85a91b83e27dfb773cad9c71625_24.png)

除了使用 `+` 连接字符串，Python还提供了一种更现代、更便捷的字符串格式化方法：**f-string**（格式化字符串）。

使用f-string的方法是在字符串前加上字母 `f`，然后在字符串内部用花括号 `{}` 包裹变量名或表达式。

```python
name = input("What‘s your name? ")
print(f"hello, {name}")
```

![](img/7197b85a91b83e27dfb773cad9c71625_26.png)

![](img/7197b85a91b83e27dfb773cad9c71625_28.png)

这段代码与上一段功能完全相同，但使用f-string让代码更清晰易读。花括号 `{name}` 会被变量 `name` 的实际值替换。

## 条件判断 🔀

程序经常需要根据不同的情况执行不同的代码。这时就需要用到条件判断。

![](img/7197b85a91b83e27dfb773cad9c71625_30.png)

让我们编写一个程序，判断用户输入的数字是正数、负数还是零。

![](img/7197b85a91b83e27dfb773cad9c71625_32.png)

```python
n = int(input("Number: "))

if n > 0:
    print("n is positive")
elif n < 0:
    print("n is negative")
else:
    print("n is zero")
```

以下是这段代码的解析：

![](img/7197b85a91b83e27dfb773cad9c71625_34.png)

1.  `int(input(...))`：`input` 函数返回的是字符串。为了进行数值比较，我们使用 `int()` 函数将用户输入的字符串转换为整数。
2.  `if n > 0:`：这是条件判断的开始。如果 `n > 0` 这个表达式为 `True`，则执行下面缩进的代码块。
3.  `elif n < 0:`：`elif` 是 `else if` 的缩写。如果第一个条件不满足（`n` 不大于0），则检查这个条件。如果 `n < 0` 为 `True`，则执行对应的代码块。
4.  `else:`：如果以上所有条件都不满足，则执行 `else` 下面的代码块。
5.  **缩进**：在Python中，缩进（通常是4个空格）至关重要。它定义了代码块的归属。属于 `if`、`elif` 或 `else` 的代码都必须统一缩进。

![](img/7197b85a91b83e27dfb773cad9c71625_36.png)

![](img/7197b85a91b83e27dfb773cad9c71625_38.png)

## 序列：字符串、列表与集合 📚

![](img/7197b85a91b83e27dfb773cad9c71625_40.png)

Python提供了多种用于存储数据集合的数据结构，我们统称为序列。它们各有特点，适用于不同的场景。

![](img/7197b85a91b83e27dfb773cad9c71625_42.png)

![](img/7197b85a91b83e27dfb773cad9c71625_44.png)

**字符串** 我们已经见过，它本质上是一个字符序列。我们可以通过索引访问其中的单个字符。

![](img/7197b85a91b83e27dfb773cad9c71625_46.png)

![](img/7197b85a91b83e27dfb773cad9c71625_48.png)

```python
name = "Harry"
print(name[0]) # 输出 ‘H‘
print(name[1]) # 输出 ‘a‘
```

**列表 (List)** 是一种可变的、有序的元素集合。列表用方括号 `[]` 表示。

```python
names = ["Harry", "Ron", "Hermione"]
print(names)        # 输出整个列表
print(names[0])     # 输出 ‘Harry‘
```

列表是“可变”的，意味着我们可以修改它。

```python
names.append("Draco") # 在列表末尾添加新元素
names.sort()          # 对列表元素进行排序
print(names)          # 输出排序后的列表
```

**集合 (Set)** 是一个无序的、元素唯一的集合。集合用 `set()` 或花括号 `{}`（注意：空集合必须用 `set()` 创建）表示。

```python
s = set()
s.add(1)
s.add(2)
s.add(3)
s.add(3) # 重复添加，集合中仍只有一个3
print(s) # 输出可能是 {1, 2, 3}，顺序不确定
s.remove(2)
print(s) # 输出可能是 {1, 3}
```

![](img/7197b85a91b83e27dfb773cad9c71625_50.png)

对于任何序列（字符串、列表、集合等），都可以使用内置函数 `len()` 来获取其长度（元素个数）。

![](img/7197b85a91b83e27dfb773cad9c71625_52.png)

```python
print(f"The set has {len(s)} elements.")
```

## 循环 🔁

![](img/7197b85a91b83e27dfb773cad9c71625_54.png)

当我们需要重复执行某段代码时，循环就派上用场了。Python中最常用的循环是 `for` 循环。

![](img/7197b85a91b83e27dfb773cad9c71625_56.png)

`for` 循环可以遍历任何序列。

```python
# 遍历一个数字范围
for i in range(6):
    print(i) # 依次打印 0, 1, 2, 3, 4, 5

![](img/7197b85a91b83e27dfb773cad9c71625_64.png)

# 遍历一个列表
names = ["Harry", "Ron", "Hermione"]
for name in names:
    print(name) # 依次打印每个名字

# 遍历一个字符串（字符序列）
name = "Harry"
for char in name:
    print(char) # 依次打印 H, a, r, r, y
```

`range(6)` 生成一个从0到5的整数序列。`for` 循环会依次将序列中的每个元素赋值给变量（如 `i`、`name`、`char`），并执行循环体内的代码。

![](img/7197b85a91b83e27dfb773cad9c71625_72.png)

## 字典：键值对映射 🗺️

最后，我们来看一个非常强大的数据结构：**字典 (Dictionary)**。字典存储的是键值对映射。你可以通过“键”来快速查找其对应的“值”。

![](img/7197b85a91b83e27dfb773cad9c71625_74.png)

字典用花括号 `{}` 表示，键和值之间用冒号 `:` 分隔。

![](img/7197b85a91b83e27dfb773cad9c71625_76.png)

```python
# 创建一个字典，将人物映射到学院
houses = {
    "Harry": "Gryffindor",
    "Draco": "Slytherin"
}

![](img/7197b85a91b83e27dfb773cad9c71625_78.png)

![](img/7197b85a91b83e27dfb773cad9c71625_80.png)

# 通过键查找值
print(houses["Harry"]) # 输出 ‘Gryffindor‘

![](img/7197b85a91b83e27dfb773cad9c71625_82.png)

# 添加新的键值对
houses["Hermione"] = "Gryffindor"
print(houses["Hermione"]) # 输出 ‘Gryffindor‘
```

![](img/7197b85a91b83e27dfb773cad9c71625_84.png)

字典在Web开发中极其有用，例如可以用来存储用户信息（用户名作为键，用户资料作为值）。

![](img/7197b85a91b83e27dfb773cad9c71625_86.png)

![](img/7197b85a91b83e27dfb773cad9c71625_88.png)

## 总结 📝

本节课中我们一起学习了Python编程语言的基础核心概念。

我们首先编写了第一个Python程序，学会了如何使用 `print` 函数。接着，我们了解了变量和Python中常见的数据类型，如整数、字符串和布尔值。

![](img/7197b85a91b83e27dfb773cad9c71625_90.png)

![](img/7197b85a91b83e27dfb773cad9c71625_92.png)

然后，我们探索了如何通过 `input` 函数与用户交互，并使用字符串连接和f-string来格式化输出。通过条件判断（`if`/`elif`/`else`），我们让程序能够根据不同情况做出决策。

我们还学习了多种数据结构：作为字符序列的**字符串**，可变有序的**列表**，元素唯一且无序的**集合**，以及通过键来映射值的**字典**。利用 `for` 循环，我们可以方便地遍历这些序列中的每一个元素。

![](img/7197b85a91b83e27dfb773cad9c71625_94.png)

![](img/7197b85a91b83e27dfb773cad9c71625_96.png)

掌握这些基础知识是使用Python进行Web编程的坚实第一步。在接下来的课程中，我们将运用这些概念来构建更复杂的应用程序。