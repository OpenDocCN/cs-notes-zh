# 62：使用pytest编写测试 🧪

在本节课中，我们将学习如何使用 `pytest` 模块为Python代码编写简单的单元测试。`pytest` 是Python中最流行的单元测试模块之一，它允许你以最少的努力进行测试，并且代码简洁、文档完善。

## 创建待测试的函数

首先，我们创建一个名为 `add.py` 的文件，并在其中定义两个简单的函数。

![](img/363c2600b442d256dce40854ce94899f_1.png)

```python
def add(a, b):
    return a + b

def sub(a, b):
    return a - b
```

以上代码定义了两个函数：`add` 用于计算两个数的和，`sub` 用于计算两个数的差。

## 编写测试文件

接下来，我们创建另一个名为 `test_addition.py` 的文件来编写测试用例。

首先，我们需要导入待测试的模块和 `pytest`。

```python
import add
import pytest
```

然后，我们定义测试函数。良好的实践是使用 `test_` 作为函数名的前缀。

以下是测试用例的编写步骤：

1.  每个测试函数应专注于测试一个特定的功能。
2.  在函数内部，我们使用 `assert` 关键字来断言某个条件为真。
3.  `assert` 语句会检查代码中的条件，并期望一个布尔值（`True` 或 `False`）。当返回值为 `True` 时，测试通过；为 `False` 时，测试失败。

现在，让我们为加法和减法函数编写具体的测试。

```python
def test_add():
    assert add.add(4, 5) == 9

def test_sub():
    assert add.sub(4, 5) == -1
```

在 `test_add` 函数中，我们断言 `4 + 5` 的结果等于 `9`。在 `test_sub` 函数中，我们断言 `4 - 5` 的结果等于 `-1`。

## 运行测试

要运行测试，请在终端中切换到文件所在目录，并执行以下命令：

```bash
python -m pytest test_addition.py
```

如果两个断言都为真，你将看到类似以下的输出，其中的两个点（`..`）表示两个测试都通过了。

```
test_addition.py .. 
```

## 理解测试失败

为了理解测试失败的情况，我们可以故意修改一个断言。例如，将减法测试的预期结果从 `-1` 改为 `-2`。

```python
def test_sub():
    assert add.sub(4, 5) == -2  # 这会导致测试失败
```

再次运行 `pytest`，输出将发生变化：

```
test_addition.py .F
```

这里，一个点（`.`）表示 `test_add` 通过，一个 `F` 表示 `test_sub` 失败。`pytest` 还会在下方详细显示失败的原因，指出期望值与实际值不匹配。

## 关于assert语句的更多细节

`assert` 语句不仅限于使用相等运算符（`==`）。你可以使用任何返回布尔值的比较，例如小于（`<`）、大于（`>`），或者关键字如 `in`、`not in`。

一个测试函数中可以包含多个 `assert` 语句。**只有当函数内所有 `assert` 语句都通过时，该测试才算通过**。

例如：

```python
def test_multiple_asserts():
    assert add.add(1, 1) == 2
    assert add.add(0, 0) == 0
    assert add.add(-1, 1) == 0
```

你也可以编写一个不执行任何断言的测试，直接使用 `pass` 语句。这样的测试会自动通过，但这通常不是好的实践，因为它没有实际验证任何功能。

```python
def test_pass_example():
    pass  # 此测试总是通过
```

## 运行特定的测试

如果你只想运行测试文件中的某个特定测试函数，可以在命令行中指定函数名。

```bash
python -m pytest test_addition.py::test_add
```

![](img/363c2600b442d256dce40854ce94899f_3.png)

这条命令将只运行 `test_addition.py` 文件中的 `test_add` 函数。

## 总结

![](img/363c2600b442d256dce40854ce94899f_5.png)

本节课中，我们一起学习了使用 `pytest` 进行单元测试的基础知识。我们了解了如何创建待测试的函数，如何编写以 `test_` 开头的测试函数，以及如何使用 `assert` 语句来验证代码行为。我们还实践了如何运行所有测试、如何解读测试通过或失败的结果，以及如何运行特定的测试函数。掌握这些是确保代码质量的重要一步。