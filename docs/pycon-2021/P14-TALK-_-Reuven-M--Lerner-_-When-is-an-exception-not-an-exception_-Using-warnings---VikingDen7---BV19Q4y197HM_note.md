# Python 异常处理：P14：何时异常不是异常？使用警告 🚨

![](img/e3bf99e35cbdc0130ca1be7c66c2a65e_1.png)

![](img/e3bf99e35cbdc0130ca1be7c66c2a65e_2.png)

![](img/e3bf99e35cbdc0130ca1be7c66c2a65e_3.png)

![](img/e3bf99e35cbdc0130ca1be7c66c2a65e_4.png)

![](img/e3bf99e35cbdc0130ca1be7c66c2a65e_6.png)

在本节课中，我们将要学习 Python 中的警告机制。与会导致程序中断的异常不同，警告是一种温和的提醒，用于提示用户当前的操作虽然暂时可行，但未来可能引发问题。我们将探讨警告的用途、如何创建和过滤警告，以及如何在你的代码中有效地使用它们。

---

![](img/e3bf99e35cbdc0130ca1be7c66c2a65e_8.png)

## 现实世界的类比：燃油警告灯 ⛽

在深入代码之前，让我们通过一个现实世界的例子来理解警告的概念。汽车有一个燃油表，当燃油即将耗尽时，仪表盘上会亮起一个黄色的警告灯。这个灯不会让汽车立即停止，但它会持续地、令人烦恼地提醒你：“你需要加油了，否则很快会抛锚。” 它旨在促使你改变行为，避免更严重的后果。

在软件中，我们也经常遇到类似的情况：用户或代码即将做一些可能导致未来错误的事情，但尚未造成实际损害。这时，我们就需要一个像“低燃油灯”一样的机制来发出警告。

---

## 为什么需要警告？🤔

上一节我们介绍了警告的现实类比，本节中我们来看看为什么 Python 需要单独的警告机制，而不是使用已有的异常或简单的打印语句。

**使用异常的问题**：
异常就像一通必须接听的电话，如果你不处理（捕获）它，程序就会终止。这对于那些“未来可能出问题，但现在还能运行”的情况来说过于严厉了。我们不想因为一个非致命性的提醒而让整个程序崩溃。

**使用打印语句的问题**：
简单的 `print()` 输出不够正式，容易与正常的程序输出混淆，并且无法被系统地过滤、捕获或重定向。

因此，Python 的 `warnings` 模块在“异常”和“打印”之间提供了一个完美的折中方案。它允许我们发出引人注目的提醒，同时保持程序的运行，并且提供了强大的过滤和控制能力。

---

## 如何发出警告？🚦

了解了警告的必要性后，我们来看看如何在代码中实际创建一个警告。

首先，需要从标准库中导入 `warnings` 模块。

```python
import warnings
```

假设我们有一个简单的函数 `hello(name)`，现在我们想修改它的 API，让它接受一个名字列表而不是单个字符串。为了给用户过渡的时间，我们可以在新版本发布前，在函数中添加一个警告。

以下是发出警告的方法：

```python
# hello.py
import warnings

def hello(name):
    # 发出一个警告，提示API即将更改
    warnings.warn(
        "The 'hello' function will soon require a list of names as input.",
        UserWarning
    )
    return f"Hello, {name}!"
```

当用户调用 `hello(“World”)` 时，他们会在控制台看到类似下面的输出，但程序会继续执行：

```
hello.py:5: UserWarning: The ‘hello‘ function will soon require a list of names as input.
  warnings.warn(message, UserWarning)
Hello, World!
```

输出包含了文件名、行号、警告类别和具体消息，帮助开发者定位问题。关键是，函数调用正常完成了。

---

## 警告的类别与自定义 📂

Python 内置了多种警告类别，用于区分不同严重程度和类型的警告：

*   **Warning**: 所有警告类的基类。
*   **UserWarning**: 用户代码生成的警告（默认类别）。
*   **DeprecationWarning**: 针对已弃用功能的警告。
*   **SyntaxWarning**: 针对可疑语法的警告。
*   **RuntimeWarning**: 针对可疑运行时行为的警告。
*   **FutureWarning**: 针对未来语义会改变的警告。

在 `warn()` 函数中，第二个参数用于指定类别。最佳实践是创建自定义的警告类别，这能提供更清晰的语义并方便过滤。自定义警告类应继承自现有的警告类别（如 `UserWarning`）。

```python
# 创建一个自定义警告类别
class MyFeatureWarning(UserWarning):
    """针对我的特定功能发出的警告。"""
    pass

# 使用自定义警告
warnings.warn(“This feature is experimental.”, MyFeatureWarning)
```

---

## 控制警告：过滤与行为 ⚙️

默认情况下，有些警告（如 `DeprecationWarning`）是被过滤掉的，不会显示。我们可以控制警告的行为。Python 定义了六种处理警告的“动作”：

*   `default`: 为每个位置（模块+行号）首次出现的警告打印输出。
*   `error`: 将警告转换为异常（引发）。
*   `ignore`: 忽略警告。
*   `always`: 总是打印警告信息。
*   `module`: 为每个模块首次出现的警告打印输出。
*   `once`: 只打印一次警告（程序生命周期内）。

我们可以通过多种方式设置过滤器：

**1. 命令行方式**：
使用 `-W` 选项。例如，让所有 `UserWarning` 都显示：
```bash
python -W always my_script.py
```
让所有警告都变为异常：
```bash
python -W error my_script.py
```

**2. 代码中设置**：
使用 `warnings.filterwarnings()` 函数。

```python
import warnings
# 忽略所有警告
warnings.filterwarnings(‘ignore’)

# 将特定的自定义警告转为异常
warnings.filterwarnings(‘error’, category=MyFeatureWarning)

# 使用上下文管理器临时修改设置
with warnings.catch_warnings():
    warnings.simplefilter(“ignore”)
    # 在这里调用会产生警告的代码，警告将被忽略
    call_poorly_behaved_function()
```

**3. 环境变量**：
设置 `PYTHONWARNINGS` 环境变量。
```bash
export PYTHONWARNINGS=“always::UserWarning”
```

---

## 何时使用警告？💡

警告是一个强大的工具，应在以下场景考虑使用：

*   **API 变更**：当你计划修改或移除某个函数、类或模块时，提前数个版本发出弃用警告，给用户充足的迁移时间。
*   **常见错误预防**：如果用户常以错误的方式调用你的函数（例如，参数类型不对但尚可转换），可以用警告引导其使用正确方式。著名的例子是 Pandas 的 `SettingWithCopyWarning`。
*   **实验性功能**：对于尚未稳定的新功能，可以发出警告告知用户其接口或行为可能在将来改变。

核心原则是：**对用户友好**。清晰的警告信息应该指出潜在问题，并尽可能提供如何修复的指导。

---

![](img/e3bf99e35cbdc0130ca1be7c66c2a65e_10.png)

## 总结 📝

![](img/e3bf99e35cbdc0130ca1be7c66c2a65e_12.png)

本节课中我们一起学习了 Python 中的警告机制。我们了解到：

1.  **警告**是一种介于异常和打印之间的通信机制，用于提示非紧急的、未来可能发生的问题。
2.  使用 `warnings.warn()` 可以发出警告，并可以指定不同的内置或自定义**警告类别**。
3.  通过**警告过滤器**，我们可以精细地控制警告的行为（如显示、忽略或转为异常），可以通过命令行、代码或环境变量进行配置。
4.  警告在**API弃用**、**预防常见错误**和**标记实验性功能**等场景下非常有用。

![](img/e3bf99e35cbdc0130ca1be7c66c2a65e_14.png)

![](img/e3bf99e35cbdc0130ca1be7c66c2a65e_16.png)

就像汽车的低燃油警告灯一样，善用警告可以帮助你的用户平滑过渡，避免未来“抛锚”在路边。在你的库或应用中适时地添加警告，是维护开发者友好性的重要实践。