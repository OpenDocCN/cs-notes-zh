# Python异常处理：P8-09：处理异常 🐍

![](img/3da79c5f3a811d02b8a7746b49573be0_0.png)

在本节课中，我们将要学习如何在Python程序中处理异常。当程序运行出错时，我们可以捕获这些错误，并尝试在程序运行时进行修正，从而提升程序的健壮性和用户体验。

## 概述

我们将通过一个存在缺陷的程序示例，逐步学习如何使用`try`和`except`语句块来优雅地处理不同类型的错误，例如`ValueError`和`KeyError`。

## 一个存在问题的程序

我们从一个名为`distances.py`的程序开始。这个程序的目标是：给定一个包含航天器及其与地球距离（以天文单位AU为单位）的字典，将用户输入的航天器距离转换为米并输出。

```python
# 初始有问题的代码示例
distances = {
    "Voyager 1": "163",
    "Pioneer 10": "80AU",
    # ... 其他数据
}

def convert(au):
    return au * 149597870700  # 1 AU 等于多少米

# ... 主程序逻辑
```

然而，这个程序存在一些问题。例如，字典中的值`"163"`是字符串，而`"80AU"`则包含了非数字字符，这会导致后续计算出错。

## 尝试运行并发现问题

当我们运行程序并输入“Voyager 1”时，程序并没有输出预期的米数，而是引发了一个内存错误。这是因为字符串`"163"`与数字进行乘法运算时，Python将其解释为重复字符串操作，导致内存溢出。

**解决方案**：我们需要将字符串转换为数字。可以使用`float()`函数来实现，这样可以处理整数和小数。

![](img/3da79c5f3a811d02b8a7746b49573be0_2.png)

```python
# 改进：将字符串转换为浮点数
au = float(distances[spacecraft])
meters = convert(au)
print(f"{meters} meters")
```

经过修改后，再次输入“Voyager 1”，程序成功计算并输出了正确的距离（米）。

## 处理更复杂的错误：ValueError

上一节我们修复了类型错误，但数据中还存在其他问题。例如，对于“Pioneer 10”，其值为`"80AU"`，这无法被`float()`函数转换，会引发`ValueError`异常。

以下是处理此类异常的方法。

### 使用 try-except 块

Python 使用 `try` 和 `except` 块来捕获和处理异常。

```python
try:
    # 尝试执行可能出错的代码
    au = float(distances[spacecraft])
    meters = convert(au)
    print(f"{meters} meters")
except ValueError:
    # 如果发生 ValueError，则执行这里的代码
    print(f"Can't convert '{distances[spacecraft]}' to a float.")
    return
```

通过这种方式，当用户输入“Pioneer 10”时，程序不会崩溃，而是会打印一条友好的错误信息并优雅地退出。

## 处理多种异常：KeyError

在`try`块中，除了`ValueError`，还可能发生其他异常。例如，如果用户输入了一个不在字典中的航天器名称，程序会引发`KeyError`。

我们可以为不同类型的异常分别编写处理逻辑。

```python
try:
    au = float(distances[spacecraft])
    meters = convert(au)
    print(f"{meters} meters")
except ValueError:
    # 处理值转换错误
    print(f"Can't convert '{distances[spacecraft]}' to a float.")
    return
except KeyError:
    # 处理键不存在错误
    print(f"'{spacecraft}' is not in the dictionary.")
    return
```

现在，如果用户输入“James Webb Space Telescope”（一个不存在的键），程序会捕获`KeyError`并输出相应的提示信息。

## 最佳实践

*   **具体化异常类型**：尽量捕获具体的异常（如`ValueError`、`KeyError`），而不是使用通用的`except Exception`。这有助于更精确地定位和处理问题，避免隐藏其他潜在错误。
*   **预见异常**：在编写代码时，应提前思考哪些操作可能失败，并为其编写异常处理代码。
*   **提供友好反馈**：异常处理的目标之一是改善用户体验，因此应向用户提供清晰、有用的错误信息，而不是晦涩的技术堆栈跟踪。

## 总结

本节课中我们一起学习了Python异常处理的核心机制。我们了解到：
1.  程序运行时常会遇到意外错误（异常）。
2.  使用 `try` 和 `except` 语句块可以捕获并处理这些异常。
3.  可以针对不同类型的异常（如 `ValueError`、`KeyError`）编写不同的处理逻辑。
4.  良好的异常处理能使程序更健壮，并为用户提供更好的体验。

![](img/3da79c5f3a811d02b8a7746b49573be0_4.png)

![](img/3da79c5f3a811d02b8a7746b49573be0_5.png)

通过预见和处理潜在错误，我们可以编写出更可靠、更专业的Python程序。