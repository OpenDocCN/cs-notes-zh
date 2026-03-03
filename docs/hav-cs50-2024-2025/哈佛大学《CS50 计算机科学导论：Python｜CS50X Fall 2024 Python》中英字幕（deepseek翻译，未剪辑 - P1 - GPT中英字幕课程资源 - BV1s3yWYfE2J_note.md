# CS50 计算机科学导论：Python｜第6周：Python入门 🐍

![](img/09d66d88cdde50070a54b5ce3b7ef036_1.png)

![](img/09d66d88cdde50070a54b5ce3b7ef036_2.png)

![](img/09d66d88cdde50070a54b5ce3b7ef036_3.png)

## 概述

![](img/09d66d88cdde50070a54b5ce3b7ef036_5.png)

![](img/09d66d88cdde50070a54b5ce3b7ef036_6.png)

在本节课中，我们将从C语言过渡到Python语言。我们将学习Python的基本语法、核心概念，并通过对比C语言来理解Python作为高级语言的优势。课程内容包括变量、数据类型、条件语句、循环、函数、列表、字典、异常处理以及如何使用第三方库。我们将通过实际代码示例，展示Python如何简化编程任务，提高开发效率。

---

## 从C到Python的过渡

![](img/09d66d88cdde50070a54b5ce3b7ef036_8.png)

上一节我们介绍了课程的整体目标，本节中我们来看看为什么选择Python以及它与C语言的主要区别。

![](img/09d66d88cdde50070a54b5ce3b7ef036_10.png)

C语言是一种低级语言，需要程序员手动管理内存等底层细节。而Python是一种高级语言，自动处理许多底层任务，使编程更加简单和高效。例如，在C语言中实现“Hello, World!”需要多行代码，而在Python中只需一行。

![](img/09d66d88cdde50070a54b5ce3b7ef036_12.png)

![](img/09d66d88cdde50070a54b5ce3b7ef036_14.png)

![](img/09d66d88cdde50070a54b5ce3b7ef036_15.png)

**代码示例：**
```python
print("Hello, World!")
```

![](img/09d66d88cdde50070a54b5ce3b7ef036_17.png)

Python是一种解释型语言，而C是编译型语言。这意味着在Python中，你可以直接运行代码，无需编译步骤。

![](img/09d66d88cdde50070a54b5ce3b7ef036_19.png)

**运行Python程序的命令：**
```bash
python hello.py
```

---

![](img/09d66d88cdde50070a54b5ce3b7ef036_21.png)

## Python的基本语法

![](img/09d66d88cdde50070a54b5ce3b7ef036_23.png)

![](img/09d66d88cdde50070a54b5ce3b7ef036_25.png)

上一节我们了解了Python的优势，本节中我们来看看Python的基本语法，包括变量、输入输出和字符串处理。

### 变量和输入

![](img/09d66d88cdde50070a54b5ce3b7ef036_27.png)

在Python中，声明变量时无需指定数据类型，解释器会自动推断。例如，使用`input`函数获取用户输入：

![](img/09d66d88cdde50070a54b5ce3b7ef036_29.png)

**代码示例：**
```python
answer = input("What's your name? ")
print(f"Hello, {answer}")
```

### 字符串处理

![](img/09d66d88cdde50070a54b5ce3b7ef036_31.png)

![](img/09d66d88cdde50070a54b5ce3b7ef036_32.png)

![](img/09d66d88cdde50070a54b5ce3b7ef036_34.png)

Python提供了丰富的字符串处理方法，例如`lower()`方法可以将字符串转换为小写：

![](img/09d66d88cdde50070a54b5ce3b7ef036_36.png)

**代码示例：**
```python
s = input("Do you agree? ").lower()
if s in ["y", "yes"]:
    print("Agreed")
```

---

## 条件语句和循环

上一节我们介绍了Python的基本语法，本节中我们来看看条件语句和循环结构。

![](img/09d66d88cdde50070a54b5ce3b7ef036_38.png)

![](img/09d66d88cdde50070a54b5ce3b7ef036_40.png)

![](img/09d66d88cdde50070a54b5ce3b7ef036_41.png)

### 条件语句

![](img/09d66d88cdde50070a54b5ce3b7ef036_43.png)

Python中的条件语句使用`if`、`elif`和`else`，无需括号，但需要冒号和缩进。

**代码示例：**
```python
x = int(input("What's x? "))
y = int(input("What's y? "))

if x < y:
    print("x is less than y")
elif x > y:
    print("x is greater than y")
else:
    print("x is equal to y")
```

![](img/09d66d88cdde50070a54b5ce3b7ef036_45.png)

![](img/09d66d88cdde50070a54b5ce3b7ef036_46.png)

### 循环

![](img/09d66d88cdde50070a54b5ce3b7ef036_48.png)

Python支持`for`循环和`while`循环。`for`循环通常与`range`函数结合使用。

![](img/09d66d88cdde50070a54b5ce3b7ef036_50.png)

**代码示例：**
```python
for i in range(3):
    print("Meow")
```

---

## 函数和异常处理

上一节我们学习了条件语句和循环，本节中我们来看看如何定义函数以及如何处理异常。

### 函数定义

在Python中，使用`def`关键字定义函数。函数可以接受参数并返回值。

**代码示例：**
```python
def meow(n):
    for _ in range(n):
        print("Meow")

meow(3)
```

### 异常处理

![](img/09d66d88cdde50070a54b5ce3b7ef036_52.png)

![](img/09d66d88cdde50070a54b5ce3b7ef036_54.png)

Python使用`try`和`except`语句处理异常，避免程序因错误而崩溃。

**代码示例：**
```python
try:
    x = int(input("Enter a number: "))
    print(f"You entered: {x}")
except ValueError:
    print("That's not a valid number!")
```

![](img/09d66d88cdde50070a54b5ce3b7ef036_56.png)

![](img/09d66d88cdde50070a54b5ce3b7ef036_58.png)

![](img/09d66d88cdde50070a54b5ce3b7ef036_59.png)

![](img/09d66d88cdde50070a54b5ce3b7ef036_60.png)

---

## 数据结构和第三方库

![](img/09d66d88cdde50070a54b5ce3b7ef036_62.png)

![](img/09d66d88cdde50070a54b5ce3b7ef036_64.png)

![](img/09d66d88cdde50070a54b5ce3b7ef036_65.png)

![](img/09d66d88cdde50070a54b5ce3b7ef036_66.png)

上一节我们介绍了函数和异常处理，本节中我们来看看Python中的数据结构（如列表和字典）以及如何使用第三方库。

![](img/09d66d88cdde50070a54b5ce3b7ef036_68.png)

![](img/09d66d88cdde50070a54b5ce3b7ef036_69.png)

![](img/09d66d88cdde50070a54b5ce3b7ef036_71.png)

![](img/09d66d88cdde50070a54b5ce3b7ef036_72.png)

### 列表

列表是Python中常用的数据结构，可以动态调整大小。

**代码示例：**
```python
scores = [72, 73, 33]
average = sum(scores) / len(scores)
print(f"Average: {average}")
```

### 字典

![](img/09d66d88cdde50070a54b5ce3b7ef036_74.png)

![](img/09d66d88cdde50070a54b5ce3b7ef036_76.png)

字典用于存储键值对，类似于哈希表。

**代码示例：**
```python
people = {
    "Julia": "+1-617-495-1000",
    "David": "+1-617-495-1000",
    "John": "+1-949-468-2750"
}

name = input("Name: ")
if name in people:
    print(f"Number: {people[name]}")
else:
    print("Not found")
```

### 第三方库

Python拥有丰富的第三方库，可以通过`pip`安装。例如，使用`cowsay`库生成有趣的输出：

**代码示例：**
```python
import cowsay

name = input("What's your name? ")
cowsay.cow(f"Hello, {name}")
```

---

## 总结

![](img/09d66d88cdde50070a54b5ce3b7ef036_78.png)

![](img/09d66d88cdde50070a54b5ce3b7ef036_79.png)

本节课中我们一起学习了Python语言的基础知识。我们从C语言过渡到Python，了解了Python作为高级语言的优势。我们学习了Python的基本语法、条件语句、循环、函数、异常处理、数据结构和第三方库的使用。通过实际代码示例，我们看到了Python如何简化编程任务，提高开发效率。希望这些知识能帮助你在未来的编程项目中更加得心应手！