# 032：在Python命令行工具中添加环境变量 🛠️

![](img/d7dcadf03ca48802ab3670956b9dcc6b_0.png)

在本节课中，我们将学习如何为Python命令行工具添加环境变量支持。环境变量是一种灵活的方式，允许用户在不直接修改命令行参数的情况下配置工具的行为。

## 概述

我们将基于一个名为 `blockpie` 的命令行工具进行演示。该工具目前有一个 `--debug-level` 选项，用于设置调试级别。我们的目标是允许用户通过环境变量来设置这个值，而不仅仅是通过命令行标志。

## 实现步骤

上一节我们介绍了基本的命令行参数解析。本节中，我们来看看如何集成环境变量。

### 1. 修改Click选项定义

为了支持环境变量，我们需要修改 `click.option` 装饰器的参数。具体来说，是添加一个 `envvar` 关键字参数。

以下是修改后的代码示例：

```python
@click.option(
    '-d', '--debug-level',
    default=1,
    type=int,
    help='Set the debug level. Optionally, use environment variable BLOCKPIE_DEBUG_LEVEL.',
    envvar='BLOCKPIE_DEBUG_LEVEL'  # 新增的环境变量参数
)
```

在这段代码中：
*   `envvar='BLOCKPIE_DEBUG_LEVEL'` 指定了环境变量的名称。
*   当用户运行命令时，Click会首先检查命令行是否提供了 `--debug-level` 参数。如果没有，它会去查找名为 `BLOCKPIE_DEBUG_LEVEL` 的环境变量，并使用其值。
*   如果两者都未提供，则使用 `default=1` 作为默认值。

### 2. 更新帮助信息

为了让用户知道可以使用环境变量，我们在帮助文本中明确说明了这一点。这通过 `help` 参数实现。

### 3. 测试环境变量功能

修改完成后，我们需要验证功能是否按预期工作。以下是几种测试方法：

首先，我们通过命令行标志测试基本功能是否正常。

```bash
python blockpie.py --debug-level 3
```

如果一切正常，这将打印出调试级别为3。

接下来，我们测试环境变量。有两种方式设置环境变量：

**方法一：在命令前临时设置（仅对该命令生效）**

```bash
BLOCKPIE_DEBUG_LEVEL=4 python blockpie.py
```
运行此命令，工具将打印出调试级别4，因为它读取了环境变量的值。

**方法二：使用 `export` 命令设置（对当前终端会话生效）**

```bash
export BLOCKPIE_DEBUG_LEVEL=5
python blockpie.py
```
运行后，工具将打印出调试级别5。你可以使用 `env` 命令查看当前所有环境变量，确认 `BLOCKPIE_DEBUG_LEVEL=5` 已存在。

若要临时更改，可以回到**方法一**，或在同一个终端会话中使用新的 `export` 命令覆盖。

## 总结

![](img/d7dcadf03ca48802ab3670956b9dcc6b_2.png)

![](img/d7dcadf03ca48802ab3670956b9dcc6b_3.png)

本节课中我们一起学习了如何为Python Click命令行工具添加环境变量支持。
1.  我们通过在 `@click.option` 装饰器中添加 `envvar` 参数，将选项与环境变量绑定。
2.  我们更新了帮助信息，以指导用户。
3.  我们实践了两种设置环境变量的方法：临时内联设置和使用 `export` 命令。
这是一种非常直接的方式来增强命令行工具的灵活性，允许用户通过环境变量进行配置，这在容器化（如Docker）和脚本化场景中尤其有用。