# Python装饰器入门教程：P18：装饰器入门

![](img/bea56f8bc14b9ea3760a592a2d1f384c_1.png)

## 概述

![](img/bea56f8bc14b9ea3760a592a2d1f384c_3.png)

在本节课中，我们将要学习Python中的装饰器。装饰器是一种强大的工具，它允许你修改或增强函数的行为，而无需更改函数本身的代码。我们将从基础概念开始，逐步学习如何编写和使用装饰器，最终理解它们如何让你的代码更简洁、更可重用。

---

## 章节1：什么是装饰器？🎯

装饰器本质上是一个函数，它接收另一个函数作为参数，并返回一个新的函数。使用装饰器可以在不修改原函数代码的情况下，为其添加额外的功能。

### 一个简单的例子

让我们从一个简单的例子开始，看看装饰器能做什么。假设我们有一个计算缓慢的函数，我们想缓存它的结果以提高效率。

```python
import time
from functools import lru_cache

def slow_square(n):
    """一个模拟耗时计算的函数"""
    time.sleep(3)  # 模拟长时间计算
    return n * n

# 不使用装饰器，每次调用都很慢
print(slow_square(3))  # 等待3秒后输出 9
print(slow_square(3))  # 再次等待3秒后输出 9
```

现在，我们使用标准库中的 `@lru_cache` 装饰器来缓存结果。

```python
@lru_cache(maxsize=None)
def slow_square(n):
    time.sleep(3)
    return n * n

print(slow_square(3))  # 第一次调用，等待3秒后输出 9
print(slow_square(3))  # 第二次调用，立即输出 9（结果已缓存）
print(slow_square(4))  # 新参数，等待3秒后输出 16
```

通过这个例子，我们可以看到装饰器的两个关键优势：
1.  **语法简洁**：使用 `@decorator_name` 的语法，清晰明了。
2.  **代码复用**：`@lru_cache` 可以轻松应用到任何需要缓存的函数上，无需在每个函数内部编写缓存逻辑。

![](img/bea56f8bc14b9ea3760a592a2d1f384c_5.png)

---

## 章节2：理解函数作为一等公民 🧱

上一节我们介绍了装饰器的外观和作用。要深入理解装饰器如何工作，我们需要先了解Python中“函数是一等公民”这个概念。

这意味着函数可以像整数、字符串等对象一样被处理。具体来说，你可以：
*   将函数赋值给变量。
*   将函数作为参数传递给另一个函数。
*   从一个函数中返回另一个函数。

### 将函数赋值给变量

![](img/bea56f8bc14b9ea3760a592a2d1f384c_7.png)

![](img/bea56f8bc14b9ea3760a592a2d1f384c_9.png)

![](img/bea56f8bc14b9ea3760a592a2d1f384c_10.png)

![](img/bea56f8bc14b9ea3760a592a2d1f384c_11.png)

```python
def greet(name):
    return f"Hi {name}"

![](img/bea56f8bc14b9ea3760a592a2d1f384c_13.png)

![](img/bea56f8bc14b9ea3760a592a2d1f384c_15.png)

# 将函数赋值给新变量
say_hello = greet
print(say_hello("Alice"))  # 输出: Hi Alice
```

### 将函数作为参数传递

```python
def shout(text):
    return text.upper() + "!"

def whisper(text):
    return text.lower() + "..."

def greet(name, formatter):
    """formatter 参数接收一个函数"""
    message = formatter(f"Hello {name}")
    print(message)

![](img/bea56f8bc14b9ea3760a592a2d1f384c_17.png)

![](img/bea56f8bc14b9ea3760a592a2d1f384c_18.png)

greet("Bob", shout)   # 输出: HELLO BOB!
greet("Bob", whisper) # 输出: hello bob...
```

### 函数引用 vs. 函数调用

这是一个非常重要的区别：
*   `function_name` 是对函数本身的**引用**。
*   `function_name()` 是**调用**函数，并获取其返回值。

![](img/bea56f8bc14b9ea3760a592a2d1f384c_20.png)

```python
print(greet)    # 输出: <function greet at 0x...> (函数对象)
print(greet())  # 错误！缺少参数。如果 greet() 返回 None，则输出 None。
```

![](img/bea56f8bc14b9ea3760a592a2d1f384c_22.png)

![](img/bea56f8bc14b9ea3760a592a2d1f384c_23.png)

在传递函数时，我们传递的是它的引用（不带括号）。

![](img/bea56f8bc14b9ea3760a592a2d1f384c_25.png)

![](img/bea56f8bc14b9ea3760a592a2d1f384c_27.png)

---

![](img/bea56f8bc14b9ea3760a592a2d1f384c_29.png)

## 章节3：创建简单的装饰器 🛠️

![](img/bea56f8bc14b9ea3760a592a2d1f384c_31.png)

![](img/bea56f8bc14b9ea3760a592a2d1f384c_33.png)

![](img/bea56f8bc14b9ea3760a592a2d1f384c_35.png)

![](img/bea56f8bc14b9ea3760a592a2d1f384c_37.png)

基于上一节的知识，我们现在可以尝试构建自己的装饰器。装饰器的核心模式是：一个接收函数作为参数的函数，它内部定义并返回一个新的“包装”函数。

![](img/bea56f8bc14b9ea3760a592a2d1f384c_39.png)

### 第一个装饰器：反转输出

让我们创建一个装饰器，它使被装饰的函数将其输出文本反转。

![](img/bea56f8bc14b9ea3760a592a2d1f384c_41.png)

![](img/bea56f8bc14b9ea3760a592a2d1f384c_43.png)

```python
def reverse_factory(func):
    """这是一个装饰器工厂，它返回一个装饰器函数。"""
    def wrapper(text):
        # 调用原函数，但传入反转后的参数
        result = func(text[::-1])
        return result
    return wrapper

# 使用装饰器
@reverse_factory
def greet(name):
    return f"Hi {name}"

print(greet("Python"))  # 输出: Hi nohtyP
```

`@reverse_factory` 语法是以下代码的简写（语法糖）：
```python
def greet(name):
    return f"Hi {name}"
greet = reverse_factory(greet) # 用装饰器返回的新函数替换原函数
```

![](img/bea56f8bc14b9ea3760a592a2d1f384c_45.png)

关键点在于，装饰后，`greet` 这个名字不再指向原来的 `greet` 函数，而是指向了 `reverse_factory(greet)` 返回的 `wrapper` 函数。

![](img/bea56f8bc14b9ea3760a592a2d1f384c_47.png)

---

## 章节4：编写通用装饰器 🌉

我们最初的 `reverse_factory` 装饰器只能处理接收一个 `text` 参数的函数。一个健壮的装饰器应该能处理各种不同签名的函数。为此，我们需要使用 `*args` 和 `**kwargs`。

*   `*args` 用于接收任意数量的位置参数，并将其打包成一个元组。
*   `**kwargs` 用于接收任意数量的关键字参数，并将其打包成一个字典。

![](img/bea56f8bc14b9ea3760a592a2d1f384c_49.png)

![](img/bea56f8bc14b9ea3760a592a2d1f384c_51.png)

![](img/bea56f8bc14b9ea3760a592a2d1f384c_53.png)

### 练习1：在函数调用前后打印信息

以下是编写一个通用装饰器的练习，该装饰器会在被装饰函数执行前后打印信息。

![](img/bea56f8bc14b9ea3760a592a2d1f384c_55.png)

![](img/bea56f8bc14b9ea3760a592a2d1f384c_57.png)

![](img/bea56f8bc14b9ea3760a592a2d1f384c_58.png)

**要求**：编写装饰器 `before_and_after`，使其能应用于任何函数，并在函数调用前后打印 “Before” 和 “After”。

![](img/bea56f8bc14b9ea3760a592a2d1f384c_60.png)

![](img/bea56f8bc14b9ea3760a592a2d1f384c_61.png)

```python
def before_and_after(func):
    def wrapper(*args, **kwargs):
        print("Before")
        # 调用原函数并保存其返回值
        result = func(*args, **kwargs)
        print("After")
        # 返回原函数的返回值
        return result
    return wrapper

![](img/bea56f8bc14b9ea3760a592a2d1f384c_63.png)

![](img/bea56f8bc14b9ea3760a592a2d1f384c_65.png)

@before_and_after
def greet(name):
    print(f"Hi {name}")

![](img/bea56f8bc14b9ea3760a592a2d1f384c_67.png)

![](img/bea56f8bc14b9ea3760a592a2d1f384c_69.png)

![](img/bea56f8bc14b9ea3760a592a2d1f384c_70.png)

![](img/bea56f8bc14b9ea3760a592a2d1f384c_72.png)

greet("World")
# 输出:
# Before
# Hi World
# After
```

![](img/bea56f8bc14b9ea3760a592a2d1f384c_73.png)

![](img/bea56f8bc14b9ea3760a592a2d1f384c_75.png)

![](img/bea56f8bc14b9ea3760a592a2d1f384c_76.png)

![](img/bea56f8bc14b9ea3760a592a2d1f384c_77.png)

![](img/bea56f8bc14b9ea3760a592a2d1f384c_78.png)

这个 `wrapper(*args, **kwargs)` 结构是装饰器的标准模式，它确保了装饰器可以通用地处理任何函数。

![](img/bea56f8bc14b9ea3760a592a2d1f384c_80.png)

![](img/bea56f8bc14b9ea3760a592a2d1f384c_81.png)

![](img/bea56f8bc14b9ea3760a592a2d1f384c_82.png)

---

![](img/bea56f8bc14b9ea3760a592a2d1f384c_84.png)

## 章节5：处理函数返回值 📦

![](img/bea56f8bc14b9ea3760a592a2d1f384c_86.png)

装饰器不仅可以在函数前后执行代码，还可以修改或处理函数的返回值。让我们通过另一个练习来巩固这个概念。

![](img/bea56f8bc14b9ea3760a592a2d1f384c_88.png)

![](img/bea56f8bc14b9ea3760a592a2d1f384c_90.png)

![](img/bea56f8bc14b9ea3760a592a2d1f384c_91.png)

### 练习2：运行函数两次

![](img/bea56f8bc14b9ea3760a592a2d1f384c_93.png)

![](img/bea56f8bc14b9ea3760a592a2d1f384c_95.png)

![](img/bea56f8bc14b9ea3760a592a2d1f384c_97.png)

**要求**：编写装饰器 `do_twice`，它会使被装饰的函数运行两次，并将两次的结果作为一个元组返回。

![](img/bea56f8bc14b9ea3760a592a2d1f384c_99.png)

![](img/bea56f8bc14b9ea3760a592a2d1f384c_101.png)

![](img/bea56f8bc14b9ea3760a592a2d1f384c_103.png)

```python
import random

![](img/bea56f8bc14b9ea3760a592a2d1f384c_105.png)

def do_twice(func):
    def wrapper(*args, **kwargs):
        # 调用原函数两次
        first_result = func(*args, **kwargs)
        second_result = func(*args, **kwargs)
        # 将两次结果作为元组返回
        return (first_result, second_result)
    return wrapper

![](img/bea56f8bc14b9ea3760a592a2d1f384c_107.png)

![](img/bea56f8bc14b9ea3760a592a2d1f384c_109.png)

@do_twice
def roll_dice():
    return random.randint(1, 6)

![](img/bea56f8bc14b9ea3760a592a2d1f384c_111.png)

![](img/bea56f8bc14b9ea3760a592a2d1f384c_113.png)

print(roll_dice())  # 输出类似: (3, 5)
```

![](img/bea56f8bc14b9ea3760a592a2d1f384c_114.png)

![](img/bea56f8bc14b9ea3760a592a2d1f384c_116.png)

这个例子展示了装饰器如何介入函数的执行流程，并操作其返回结果。

![](img/bea56f8bc14b9ea3760a592a2d1f384c_118.png)

![](img/bea56f8bc14b9ea3760a592a2d1f384c_119.png)

---

![](img/bea56f8bc14b9ea3760a592a2d1f384c_121.png)

![](img/bea56f8bc14b9ea3760a592a2d1f384c_123.png)

![](img/bea56f8bc14b9ea3760a592a2d1f384c_124.png)

## 总结

![](img/bea56f8bc14b9ea3760a592a2d1f384c_126.png)

在本节课中，我们一起学习了Python装饰器的核心知识：

![](img/bea56f8bc14b9ea3760a592a2d1f384c_128.png)

![](img/bea56f8bc14b9ea3760a592a2d1f384c_130.png)

![](img/bea56f8bc14b9ea3760a592a2d1f384c_131.png)

![](img/bea56f8bc14b9ea3760a592a2d1f384c_133.png)

1.  **装饰器是什么**：装饰器是一个接收函数作为参数、并返回一个新函数的函数，用于增强或修改原函数的行为。
2.  **核心概念**：理解“函数是一等公民”是理解装饰器的基础，包括函数赋值、传参和返回。
3.  **装饰器语法**：`@decorator_name` 是 `func = decorator_name(func)` 的简洁写法。
4.  **通用装饰器结构**：使用 `def wrapper(*args, **kwargs):` 来创建能处理任意参数的装饰器，并确保正确传递参数和返回值。
5.  **装饰器的能力**：装饰器可以在函数调用前后执行代码，修改传入参数，处理或替换返回值。

![](img/bea56f8bc14b9ea3760a592a2d1f384c_134.png)

![](img/bea56f8bc14b9ea3760a592a2d1f384c_136.png)

![](img/bea56f8bc14b9ea3760a592a2d1f384c_138.png)

通过掌握装饰器，你可以写出更模块化、更可复用和更易读的Python代码。