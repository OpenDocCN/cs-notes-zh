# Python编程入门：P14：pytest测试框架入门 🧪

![](img/93d4a5eaf6ba9e7f6e5364bdc0897463_0.png)

在本节课中，我们将学习如何使用 `pytest` 模块来更全面、更高效地测试我们的Python代码。我们将通过一个具体的例子，学习如何编写测试函数、测试不同类型的输入以及如何处理浮点数精度问题。

## 概述

我们将从一个名为 `convert.py` 的程序开始，它的功能是将天文单位转换为米。我们将为这个程序编写测试，学习 `pytest` 的核心概念，包括断言、异常测试和浮点数近似比较。

---

## 编写待测试的程序

首先，我们有一个 `convert.py` 文件，其中包含一个 `convert` 函数。这个函数接受一个天文单位值，并将其转换为米。如果输入不是整数或浮点数，它会抛出一个 `TypeError`。

```python
def convert(AU):
    if not isinstance(AU, (int, float)):
        raise TypeError("AU must be an int or float")
    return AU * 149597870700
```

上一节我们介绍了待测试的程序，本节中我们来看看如何为它编写测试。

---

## 创建测试文件

按照 `pytest` 的约定，测试文件应以 `test_` 开头。因此，我们创建一个名为 `test_convert.py` 的文件。

在文件开头，我们需要导入 `pytest` 模块以及要测试的函数。

```python
import pytest
from convert import convert
```

现在，我们可以在 `test_convert.py` 中编写测试函数了。按照约定，每个测试函数的名字也应以 `test_` 开头。

---

## 编写基础测试

最简单的测试是验证函数对于特定输入是否能返回正确的输出。我们将测试 `convert(1)` 是否等于 `149597870700`。

以下是测试整数转换的步骤：

1.  定义一个以 `test_` 开头的函数。
2.  在函数中使用 `assert` 语句来声明期望的结果。
3.  如果断言失败，`pytest` 会报告测试未通过。

```python
def test_conversion():
    assert convert(1) == 149597870700
```

运行 `pytest` 命令，如果看到一个小点 `.`，就表示这个测试通过了。

为了更全面，我们应该测试多个有代表性的输入。例如，测试 `convert(50)`。

```python
def test_conversion():
    assert convert(1) == 149597870700
    assert convert(50) == 7479893535000
```

再次运行 `pytest`，两个断言都必须通过，该测试函数才算通过。

---

## 测试异常情况

我们的 `convert` 函数在输入类型错误时会抛出 `TypeError`。测试这种异常行为同样重要。

`pytest` 提供了一个简洁的语法来测试代码是否按预期抛出了异常。

以下是测试错误处理的步骤：

1.  使用 `pytest.raises()` 上下文管理器。
2.  在这个代码块中调用会触发异常的代码。
3.  如果指定的异常被抛出，测试通过；否则，测试失败。

```python
def test_error():
    with pytest.raises(TypeError):
        convert("1")
```

运行 `pytest`，现在应该看到两个测试函数（`test_conversion` 和 `test_error`）都通过了。

---

## 处理浮点数测试

测试浮点数时，我们需要考虑计算机中浮点数的精度限制。两个理论上相等的浮点数，在计算机中可能因为微小的舍入误差而不完全相等。

`pytest` 提供了 `approx` 函数来处理浮点数的近似比较，允许我们设置一个容差范围。

以下是测试浮点数转换的步骤：

1.  使用 `pytest.approx()` 包装期望值。
2.  `approx` 会使用合理的默认容差进行比较。
3.  我们也可以使用 `abs` 参数自定义绝对容差。

```python
def test_float_conversion():
    expected_value = 149597870.691
    # 使用默认容差
    assert convert(0.001) == pytest.approx(expected_value)
    # 使用自定义容差，例如 ±0.1
    assert convert(0.001) == pytest.approx(expected_value, abs=0.1)
```

调整容差时需要注意：不应该为了通过测试而随意放宽容差，而应该根据应用场景的科学要求预先设定合理的容差，并确保代码能满足这个精度。

---

## 总结

本节课中我们一起学习了 `pytest` 测试框架的基础知识。

我们学习了如何：
*   创建符合约定的测试文件（`test_*.py`）和测试函数（`test_*`）。
*   使用 `assert` 语句进行基本的相等性测试。
*   使用 `pytest.raises()` 来测试函数是否按预期抛出异常。
*   使用 `pytest.approx()` 来比较浮点数，处理精度问题，并了解了如何设置容差。

![](img/93d4a5eaf6ba9e7f6e5364bdc0897463_2.png)

![](img/93d4a5eaf6ba9e7f6e5364bdc0897463_3.png)

通过编写这些测试，我们可以更自信地确保代码在各种情况下都能正确运行，并且在未来修改代码时，能快速发现是否引入了错误。