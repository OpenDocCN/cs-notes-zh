# 011：使用 unittest 进行自动化测试 🧪

在本节课中，我们将要学习如何使用 Python 的 `unittest` 模块进行自动化测试。我们将了解它如何将测试代码与功能代码分离，以及它相比 `doctest` 提供的更详细的反馈信息。

---

## 概述

`doctest` 作为函数文档的一部分非常有用。然而，正如之前提到的，当测试数量增多时，它会使代码变得难以阅读。

Python 的 `unittest` 模块提供了另一个测试框架，允许我们将测试代码与被测试的函数分开编写。

我们将通过将 `get_divisors` 函数的 `doctest` 测试转换为 `unittest` 测试来探索 `unittest` 的用法。

---

![](img/7bb18c1c8810a2ef6189869eadf8e020_1.png)

## 对比 doctest 与 unittest

在屏幕左侧是带有 `doctest` 的 `get_divisors` 函数。右侧是其对应的 `unittest` 版本。首先，我们将展示这两者如何实现基本相同的功能。

![](img/7bb18c1c8810a2ef6189869eadf8e020_3.png)

根据我们想使用的框架，我们导入相应的模块：`doctest` 或 `unittest`。

![](img/7bb18c1c8810a2ef6189869eadf8e020_4.png)

```python
# 使用 doctest
import doctest

![](img/7bb18c1c8810a2ef6189869eadf8e020_6.png)

# 使用 unittest
import unittest
```

在 `doctest` 中，我们编写的代码就像在 Python 交互式环境中输入一样，并在下一行写下预期结果。`doctest` 会自动为我们比较两者。

![](img/7bb18c1c8810a2ef6189869eadf8e020_8.png)

```python
def get_divisors(num, possible_divisors):
    """
    >>> get_divisors(8, [1, 2, 3])
    [1, 2]
    """
    # ... 函数实现 ...
```

在 `unittest` 中，我们为每个测试编写一个单独的方法。在该方法中，我们调用要测试的函数。

![](img/7bb18c1c8810a2ef6189869eadf8e020_10.png)

```python
class TestGetDivisors(unittest.TestCase):
    def test_divisors_example(self):
        actual = get_divisors(8, [1, 2, 3])
        expected = [1, 2]
```

然后，我们写下预期结果。与 `doctest` 不同，我们通过调用 `assertEqual` 方法来比较实际结果与预期结果。

![](img/7bb18c1c8810a2ef6189869eadf8e020_12.png)

```python
        self.assertEqual(actual, expected)
```

“断言”某事意味着声称它是真的。在这里，我们断言实际结果应该等于预期结果。

---

![](img/7bb18c1c8810a2ef6189869eadf8e020_14.png)

![](img/7bb18c1c8810a2ef6189869eadf8e020_15.png)

## 执行测试

到目前为止，对于 `doctest` 和 `unittest`，我们都已导入了测试模块并编写了测试代码。接下来，我们需要执行这些测试。

![](img/7bb18c1c8810a2ef6189869eadf8e020_17.png)

`doctest.testmod()` 会检查当前模块中的所有文档字符串，并执行它找到的测试。它会报告实际结果与预期结果之间的任何差异。

```python
if __name__ == '__main__':
    doctest.testmod()
```

`unittest.main()` 会检查当前模块中所有以 `test`（小写）开头的方法，这些方法属于 `TestCase` 的子类。

![](img/7bb18c1c8810a2ef6189869eadf8e020_19.png)

```python
if __name__ == '__main__':
    unittest.main(exit=False) # 在 IDE 中运行时通常传入 exit=False
```

它会调用每个测试方法，并报告任何意外结果。

![](img/7bb18c1c8810a2ef6189869eadf8e020_21.png)

让我们运行测试模块并查看输出。

每个点 `.` 代表一个成功的测试。你可以看到有两个测试，并且它们运行得非常快。

---

## 引入错误并查看反馈

现在，让我们引入一个错误。我们将从一个非空列表开始，将第一个参数的值放入除数列表中。

保存文件并重新运行测试。这次我们得到了大量反馈。不再是点 `.`，我们看到了 `F`。系统会告诉我们每个失败的方法名称，并显示其文档字符串。

我们会看到回溯信息，即导致错误的一系列函数和方法调用。

还会看到断言错误，包括预期值和实际值。

我们甚至能获得关于问题所在的详细信息。在底部，我们看到测试用例子类失败了，因为至少存在一个错误。

![](img/7bb18c1c8810a2ef6189869eadf8e020_23.png)

现在让我们修复那个错误。我们还会放入另一个允许除零的错误，我们将移除旧的 `if` 语句，并用这个新的替换它。是时候重新测试了。

只有一个测试涉及了除以零，所以这次只有一个问题。不是由错误断言引起的 `F`，我们看到了一个 `E`，因为我们对 `get_divisors` 函数的第二次调用导致了一个错误。

再次，我们看到方法名、文档字符串和回溯信息。这次，回溯信息显示，在我们测试模块的第 18 行，我们调用了函数 `get_divisors`，而在 `get_divisors` 函数的第 16 行，这行代码引发了零除错误。

---

## unittest 的优势

如你所见，与 `doctest` 相比，`unittest` 提供了更详细的反馈。我们还将测试与代码分离，这允许我们编写大量测试，而不影响代码的可读性。

通常，我们会为每个要测试的函数编写一个 `TestCase` 子类，并为每个函数调用编写一个测试方法。

---

## 总结

本节课中，我们一起学习了如何使用 Python 的 `unittest` 框架进行自动化测试。我们了解了如何将测试代码与功能代码分离，通过 `assertEqual` 等方法进行断言，以及如何执行测试并解读详细的错误反馈。与 `doctest` 相比，`unittest` 更适合管理大量测试用例，并能提供更清晰的测试报告，有助于编写和维护高质量的代码。