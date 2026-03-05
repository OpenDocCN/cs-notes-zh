# Python 单元测试：P3：使用 Pytest 进行单元测试 🧪

![](img/a937c5a7ffe7d3c8204383fd3d5b5753_1.png)

在本节课中，我们将要学习如何使用 Pytest 框架为 Python 代码编写和运行单元测试。Pytest 是一个功能强大且易于使用的测试框架，可以帮助我们确保代码的质量和可靠性。

## 概述

单元测试是软件开发中验证代码最小单元（通常是函数或方法）是否按预期工作的过程。使用 Pytest 可以让我们以简洁的语法编写测试，并轻松地运行和管理它们。

---

### P3：1：安装与基本用法 🔧

![](img/a937c5a7ffe7d3c8204383fd3d5b5753_3.png)

首先，我们需要安装 Pytest。可以通过 Python 的包管理工具 pip 来完成安装。

![](img/a937c5a7ffe7d3c8204383fd3d5b5753_5.png)

![](img/a937c5a7ffe7d3c8204383fd3d5b5753_7.png)

**安装命令如下：**
```bash
pip install pytest
```

![](img/a937c5a7ffe7d3c8204383fd3d5b5753_9.png)

安装完成后，就可以开始编写测试了。Pytest 会自动发现并运行以 `test_` 开头的文件或函数。

![](img/a937c5a7ffe7d3c8204383fd3d5b5753_11.png)

---

### P3：2：编写第一个测试 ✍️

上一节我们介绍了如何安装 Pytest，本节中我们来看看如何编写一个简单的测试函数。

![](img/a937c5a7ffe7d3c8204383fd3d5b5753_13.png)

假设我们有一个计算两个数相加的函数 `add`，存放在 `calculator.py` 文件中：

```python
# calculator.py
def add(a, b):
    return a + b
```

![](img/a937c5a7ffe7d3c8204383fd3d5b5753_15.png)

为了测试这个函数，我们创建一个名为 `test_calculator.py` 的文件。在 Pytest 中，测试函数的名字应以 `test_` 开头。

**一个基本的测试示例如下：**
```python
# test_calculator.py
from calculator import add

def test_add():
    result = add(2, 3)
    assert result == 5
```

在这个测试中，我们使用 `assert` 语句来验证 `add(2, 3)` 的结果是否等于 `5`。如果断言为真，测试通过；否则，测试失败。

---

### P3：3：运行测试 ▶️

编写好测试后，我们需要运行它来验证代码。运行测试非常简单。

**在终端中，切换到测试文件所在的目录，然后执行以下命令：**
```bash
pytest
```

Pytest 会自动发现当前目录及其子目录中所有以 `test_` 开头的文件和函数，并执行它们。运行结果会显示每个测试是通过还是失败。

![](img/a937c5a7ffe7d3c8204383fd3d5b5753_17.png)

---

![](img/a937c5a7ffe7d3c8204383fd3d5b5753_19.png)

### P3：4：使用断言验证结果 ✅

`assert` 语句是 Pytest 测试的核心。它用于检查条件是否为真。如果条件为假，Pytest 会报告测试失败，并显示详细的错误信息。

除了简单的相等断言，Pytest 还支持多种断言方式，用于测试不同的条件。

以下是几种常见的断言示例：

*   **检查相等性：** `assert func() == expected_value`
*   **检查不等性：** `assert func() != value`
*   **检查是否为真：** `assert condition is True`
*   **检查是否包含：** `assert item in collection`
*   **检查是否引发异常：** 使用 `pytest.raises`

例如，测试一个函数是否引发了特定的异常：
```python
import pytest

def test_divide_by_zero():
    with pytest.raises(ZeroDivisionError):
        # 假设 divide 函数在除数为零时会抛出 ZeroDivisionError
        divide(10, 0)
```

---

### P3：5：测试的组织与标记 🏷️

![](img/a937c5a7ffe7d3c8204383fd3d5b5753_21.png)

随着项目规模的增长，测试用例会越来越多。良好的组织和管理测试至关重要。Pytest 提供了测试类和标记（mark）功能来帮助我们。

![](img/a937c5a7ffe7d3c8204383fd3d5b5753_23.png)

**使用测试类：**
可以将相关的测试函数组织在一个类中，类名应以 `Test` 开头。

```python
class TestCalculator:
    def test_add(self):
        assert add(1, 2) == 3

    def test_multiply(self):
        # 假设有 multiply 函数
        assert multiply(2, 3) == 6
```

**使用标记：**
标记（mark）允许我们对测试进行分组，例如标记为“慢速测试”或“集成测试”，然后选择性地运行它们。

![](img/a937c5a7ffe7d3c8204383fd3d5b5753_25.png)

首先，在测试函数上使用 `@pytest.mark` 装饰器：
```python
import pytest

![](img/a937c5a7ffe7d3c8204383fd3d5b5753_27.png)

@pytest.mark.slow
def test_very_slow_function():
    # 这是一个运行很慢的测试
    result = slow_function()
    assert result is not None
```

![](img/a937c5a7ffe7d3c8204383fd3d5b5753_29.png)

然后，可以只运行带有特定标记的测试：
```bash
pytest -m slow
```

![](img/a937c5a7ffe7d3c8204383fd3d5b5753_31.png)

或者，排除带有特定标记的测试：
```bash
pytest -m “not slow”
```

---

![](img/a937c5a7ffe7d3c8204383fd3d5b5753_33.png)

### P3：6：使用 Fixture 进行测试准备 🧰

![](img/a937c5a7ffe7d3c8204383fd3d5b5753_35.png)

在测试中，我们经常需要一些公共的 setup（准备）和 teardown（清理）代码，例如创建数据库连接、初始化对象等。Pytest 的 Fixture 功能完美地解决了这个问题。

![](img/a937c5a7ffe7d3c8204383fd3d5b5753_37.png)

Fixture 是一个函数，用 `@pytest.fixture` 装饰器标记。它可以在测试函数中被调用，为其提供所需的数据或状态。

![](img/a937c5a7ffe7d3c8204383fd3d5b5753_39.png)

**定义一个简单的 Fixture：**
```python
import pytest

@pytest.fixture
def sample_data():
    # 这个函数会在测试前执行，返回准备的数据
    data = [1, 2, 3, 4, 5]
    return data
```

![](img/a937c5a7ffe7d3c8204383fd3d5b5753_41.png)

**在测试中使用 Fixture：**
只需将 Fixture 的函数名作为测试函数的参数即可。

```python
def test_sum(sample_data):
    total = sum(sample_data)
    assert total == 15
```

当运行 `test_sum` 时，Pytest 会自动调用 `sample_data` fixture 函数，并将其返回值注入到测试中。

Fixture 还可以设置作用域（如 `function`， `class`， `module`， `session`），并支持自动清理（通过 `yield`）。

---

### P3：7：参数化测试 📊

![](img/a937c5a7ffe7d3c8204383fd3d5b5753_43.png)

有时我们需要用多组不同的输入数据来测试同一个功能，以验证其在不同情况下的行为。手动为每组数据编写一个测试函数非常繁琐。Pytest 的参数化测试功能可以优雅地解决这个问题。

使用 `@pytest.mark.parametrize` 装饰器，我们可以向一个测试函数传递多组参数。

![](img/a937c5a7ffe7d3c8204383fd3d5b5753_45.png)

**参数化测试示例：**
```python
import pytest

![](img/a937c5a7ffe7d3c8204383fd3d5b5753_47.png)

@pytest.mark.parametrize(“input_a, input_b, expected”, [
    (1, 2, 3),
    (5, -1, 4),
    (0, 0, 0),
    (100, 200, 300),
])
def test_add_with_params(input_a, input_b, expected):
    result = add(input_a, input_b)
    assert result == expected
```

Pytest 会将列表中的每一组参数（如 `(1, 2, 3)`）依次传递给 `test_add_with_params` 函数并运行测试。这样，一个测试函数就覆盖了多种测试情况，测试报告也会清晰地显示每一组参数的运行结果。

---

## 总结

本节课中我们一起学习了使用 Pytest 进行 Python 单元测试的核心知识。

![](img/a937c5a7ffe7d3c8204383fd3d5b5753_49.png)

我们首先介绍了如何安装 Pytest，然后学习了编写和运行简单测试的基本流程。接着，我们深入探讨了如何使用 `assert` 语句进行各种验证，以及如何通过测试类和标记来更好地组织测试用例。

最后，我们掌握了两个高级功能：**Fixture** 和 **参数化测试**。Fixture 帮助我们管理测试的依赖和状态，使测试代码更清晰、可复用。参数化测试则让我们能轻松地用多组数据测试同一逻辑，极大地提高了测试的效率和覆盖率。

![](img/a937c5a7ffe7d3c8204383fd3d5b5753_51.png)

通过掌握这些内容，你已经能够为你的 Python 项目构建一个强大、灵活且易于维护的自动化测试套件了。