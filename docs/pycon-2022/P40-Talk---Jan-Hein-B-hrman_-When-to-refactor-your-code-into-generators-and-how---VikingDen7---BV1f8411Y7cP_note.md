# Python 重构教程：第 1 章：何时以及如何将循环重构为生成器管道 🚀

![](img/33efdd09484518636e8cf628d585467b_1.png)

在本教程中，我们将学习如何识别代码中重复的循环模式，并掌握通过重构将其转化为更优雅、更易维护的生成器管道的技巧。我们将从一段虚构但典型的代码开始，逐步引入生成器、`itertools`模块等概念，最终实现代码的简化与优化。

---

## 识别重复的循环模式

我们从一个虚构的场景开始：为“斐波那契序列粉丝俱乐部”的产品负责人编写几个函数。首先，我们需要一个函数，返回小于某个阈值的所有斐波那契数。

斐波那契序列的定义是：序列中的每个数字是前两个数字的和。通常从 `0` 和 `1` 开始。

以下是第一个函数的实现：
```python
def fibonacci_until(threshold: int) -> list[int]:
    result = []
    a, b = 0, 1  # 当前和下一个斐波那契数
    while a < threshold:
        result.append(a)
        a, b = b, a + b  # 计算新的当前和下一个数
    return result
```

产品负责人随后要求更多功能：获取序列中第 `n` 个（从0开始索引）斐波那契数、获取前 `n` 个斐波那契数、以及获取大于等于某个值的最小斐波那契数。

我们逐一实现这些功能后，会发现代码中存在明显的重复模式。上一节我们介绍了第一个函数，本节中我们来看看其他几个函数的实现，并分析其中的共同点。

以下是所有四个函数的简化视图，它们都遵循相似的结构：
1.  初始化斐波那契寄存器 `a` 和 `b`。
2.  根据不同的条件（阈值、计数）进入循环。
3.  在循环中更新 `a` 和 `b`。
4.  最终返回单个值或列表。

这种重复不仅增加了维护成本，也容易在修改时引入错误。我们的目标是消除这种冗余。

---

## 重构的概念与挑战

重构是在不改变代码外部行为的前提下，重新组织代码内部结构，以提升可读性、降低复杂度和提高可维护性。

面对我们代码中的模式，直接提取公共行（如初始化或更新寄存器）收效甚微。一个笨拙的方法是创建一个“超级函数”，通过标志参数来控制所有行为，但这会导致函数签名复杂、类型注解丑陋且代码难以理解。

**错误的示范（超级函数）**：
```python
from typing import Union

def ugly_combined_function(
    mode: bool, param: int
) -> Union[int, list[int]]:
    # ... 复杂且难以维护的逻辑 ...
    pass
```
这不是正确的做法。关键在于我们需要从更高的概念层面思考：这些函数都在做两件事——**生成斐波那契数序列**和**根据特定条件处理这个序列**。我们可以将数据生成部分分离出来。

---

## 引入生成器函数

生成器函数是分离数据生成逻辑的完美工具。它是一个包含 `yield` 表达式的函数，调用时会返回一个生成器迭代器。每次迭代时，它生成一个值并暂停，保持所有局部状态，直到下次被请求时继续执行。

那么，如何编写一个生成斐波那契数列的生成器呢？

以下是一个优雅的斐波那契生成器实现：
```python
def fibgen():
    """生成无限的斐波那契数列。"""
    a, b = 0, 1
    while True:
        yield a
        a, b = b, a + b
```
这个生成器清晰地表达了斐波那契序列的生成逻辑，并且与具体的停止条件（如“小于阈值”或“前N个”）解耦。

如何使用这个生成器呢？我们可以直接在循环中消费它：
```python
# 打印前10个斐波那契数
for _, fib in zip(range(10), fibgen()):
    print(fib)
```
现在，数据生成部分已经被成功分离。接下来，我们看看如何优雅地处理这些生成的数据。

---

## 利用 `itertools` 构建处理管道

Python 标准库中的 `itertools` 模块提供了一组快速、内存高效的迭代器工具。它们可以像管道一样组合起来，简洁地表达各种处理逻辑。此外，`more-itertools` 包提供了更多便捷的配方。

以下是使用这些工具重新实现之前四个功能的方法：

**1. 小于阈值的斐波那契数列表**
使用 `takewhile`，它从迭代器中取值，直到谓词条件为假。
```python
from itertools import takewhile

def fibonacci_until_refactored(threshold: int) -> list[int]:
    return list(takewhile(lambda x: x < threshold, fibgen()))
```

**2. 第 n 个斐波那契数**
使用 `islice` 进行迭代器切片，然后使用 `more_itertools.one` 确保只取一个值。
```python
from itertools import islice
from more_itertools import one

def nth_fibonacci_refactored(n: int) -> int:
    # n 是0起始的索引
    return one(islice(fibgen(), n, n + 1))
```

**3. 前 n 个斐波那契数列表**
同样使用 `islice`，指定停止位置。
```python
def first_n_fibonacci_refactored(n: int) -> list[int]:
    return list(islice(fibgen(), n))
```

**4. 大于等于某值的最小斐波那契数**
使用 `dropwhile` 丢弃不满足条件的值，然后取第一个。
```python
from itertools import dropwhile
from more_itertools import first

def smallest_fib_gte_refactored(n: int) -> int:
    return first(dropwhile(lambda x: x < n, fibgen()))
```

通过组合生成器和 `itertools`，我们将命令式的、混杂着控制流和数据生成的循环，重构为了声明式的、易于理解的管道操作。每个函数的核心逻辑变得一目了然。

---

## 总结与资源

在本教程中，我们一起学习了如何识别代码中可重构的循环模式，其特点是数据生成逻辑与处理逻辑混杂在一起。我们引入了生成器函数来分离和封装无限或惰性的数据序列。最后，我们利用 `itertools` 和 `more-itertools` 中的强大工具，将复杂的循环条件重构为清晰的生成器管道。

这种重构方式使代码：
*   **更易维护**：关注点分离，每部分代码职责单一。
*   **更易读**：声明式的管道操作比命令式的循环更贴近问题描述。
*   **更灵活**：生成器是惰性的，适合处理大型或无限序列。

**进一步学习资源**：
*   [斐波那契数 - 维基百科](https://en.wikipedia.org/wiki/Fibonacci_number)
*   [Python 术语表：生成器](https://docs.python.org/3/glossary.html#term-generator)
*   [`itertools` — 官方文档](https://docs.python.org/3/library/itertools.html)
*   [`more-itertools` — PyPI](https://pypi.org/project/more-itertools/)

鼓励你阅读 `itertools` 的文档，你会发现其中许多工具都能让你的代码更具表达力。例如，在处理需要分块写入数据库的大量数据时，`more_itertools.chunked` 会非常有用。

![](img/33efdd09484518636e8cf628d585467b_3.png)

希望本教程能帮助你在未来写出更优雅、更 Pythonic 的代码！