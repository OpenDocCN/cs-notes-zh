# 028：在Python中创建带子命令的命令行工具

![](img/4182da30b2d2d5a34fe1c3e2f61bd552_0.png)

在本节课中，我们将学习如何使用Python的`click`框架，为现有的命令行工具添加子命令功能。我们将从一个简单的工具开始，逐步将其改造为支持多个子命令的结构。

## 概述

我们一直在使用一个名为`lsblk`的Linux命令行工具，并将其功能导入到Python中，创建了`blockpi`工具。目前，`blockpi`接受一个设备名作为位置参数。本节的目标是为其添加子命令（例如`info`和`nice`），使工具结构更清晰、功能更模块化。

## 创建命令组

首先，我们需要将现有的单一命令转换为一个可以包含子命令的命令组。这是通过`click.group()`装饰器实现的。

以下是创建命令组`main`的步骤：

```python
import click

@click.group()
def main():
    pass
```

我们将原来的`main`函数重命名为`info`，并将其作为`main`命令组的一个子命令。同时，需要将`@click.command()`装饰器替换为`@main.command()`，以表明`info`是`main`组下的一个子命令。

```python
@main.command()
@click.argument('device')
def info(device):
    # 原有的命令逻辑
    run_lsblk(device)
```

完成此更改后，运行`blockpi --help`，你将看到`info`被列为一个可用的子命令。要获取`info`子命令的帮助信息，可以运行`blockpi info --help`。

## 添加全局选项

有时，我们希望某些选项（如`--verbose`）对所有子命令都可用，而不是仅对某个特定子命令有效。这可以通过将选项添加到命令组（`main`）上来实现。

```python
@click.group()
@click.option('--verbose', is_flag=True, help='启用详细输出模式。')
def main(verbose):
    pass
```

现在，`--verbose`选项将出现在顶级帮助信息中，作为全局选项供所有子命令使用。

## 添加更多子命令

我们可以继续为命令组添加更多子命令，以扩展工具的功能。例如，添加一个`nice`子命令，用于美化输出格式。

以下是添加`nice`子命令的步骤：

1.  定义`nice`子命令函数。
2.  为其添加必要的参数或选项。
3.  在函数内部实现特定的逻辑，例如使用`pprint`模块来美化输出。

```python
from pprint import pprint

@main.command()
@click.argument('device')
def nice(device):
    # 调用底层函数，并传入特定参数以触发美化输出逻辑
    result = run_lsblk(device, nice=True)
    pprint(result)
```

在底层函数`run_lsblk`中，我们需要接收`nice`参数，并根据其值决定是否使用美化打印。

```python
def run_lsblk(device, nice=False):
    # ... 执行命令获取输出 ...
    if nice:
        pprint(output)
    else:
        print(output)
```

## 测试与验证

完成代码修改后，需要在终端中进行测试，以确保所有功能按预期工作。

以下是测试步骤：

1.  运行`blockpi --help`，确认`info`和`nice`子命令已列出，并且`--verbose`作为全局选项出现。
2.  分别运行`blockpi info <设备名>`和`blockpi nice <设备名>`，验证它们能正确执行并输出结果。
3.  如果遇到错误（例如参数传递问题），根据错误信息调整代码，确保函数签名和参数传递正确。

## 总结

![](img/4182da30b2d2d5a34fe1c3e2f61bd552_2.png)

本节课中，我们一起学习了如何使用Python的`click`框架为命令行工具添加子命令。关键步骤包括：使用`@click.group()`创建命令组，使用`@<group_name>.command()`定义子命令，以及将全局选项添加到命令组上。通过这种方式，我们可以构建出结构清晰、易于扩展的命令行工具。