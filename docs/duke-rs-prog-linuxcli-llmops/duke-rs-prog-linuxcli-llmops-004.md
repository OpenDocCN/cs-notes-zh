# 004：引言_1

在本节课中，我们将学习如何使用Python构建一个命令行工具。我们将从最基础的环境搭建开始，涵盖Python开发中必需的概念，如虚拟环境。接着，我们会构建一个最简单的、无依赖的单文件命令行工具。之后，我们将进一步学习使用一个具体的框架——Click框架。本教程将采用一个真实世界的用例：与操作系统中的命令行工具交互，以获取硬盘和块设备信息，并用Python处理和呈现这些数据。这在系统工程中非常常见。

## 开发环境搭建与虚拟环境

首先，我们需要设置Python开发环境。对于Python开发而言，使用虚拟环境是至关重要的。虚拟环境可以为每个项目创建独立的Python运行环境，避免包依赖冲突。

以下是创建和激活虚拟环境的步骤：

1.  **创建虚拟环境**：在项目目录下，运行 `python -m venv venv` 命令。这会在当前目录创建一个名为 `venv` 的文件夹，其中包含独立的Python解释器和包管理工具。
2.  **激活虚拟环境**：
    *   在Windows系统上，运行 `venv\Scripts\activate`。
    *   在macOS或Linux系统上，运行 `source venv/bin/activate`。
3.  激活后，终端提示符通常会显示虚拟环境名称，表示你已在该环境中工作。之后使用 `pip install` 安装的包将只影响当前虚拟环境。

## 构建最简单的命令行工具

上一节我们介绍了环境准备，本节中我们来看看如何构建一个最简单的Python命令行工具。这个工具将是一个独立的Python脚本，不依赖任何外部库。

创建一个名为 `simple_cli.py` 的文件，并添加以下代码：

```python
#!/usr/bin/env python3
import sys

def main():
    if len(sys.argv) > 1:
        print(f"Hello, {sys.argv[1]}!")
    else:
        print("Hello, World!")

if __name__ == "__main__":
    main()
```

这个脚本的功能是：如果运行命令时提供了参数，则向该参数问好；否则，输出“Hello, World!”。

使其可执行并运行：
1.  在终端中，使用 `chmod +x simple_cli.py` 命令为脚本添加可执行权限。
2.  可以直接运行 `python simple_cli.py`，或者使用 `./simple_cli.py`（在Unix-like系统上）来执行。

## 使用Click框架构建增强工具

虽然简单的脚本可以工作，但对于需要复杂参数解析、子命令和帮助文档的工具，使用框架会更高效。接下来，我们将使用Click框架来重构并增强我们的工具。

首先，在激活的虚拟环境中安装Click：
```bash
pip install click
```

然后，创建一个新的文件 `enhanced_cli.py`，使用Click重写功能：

```python
#!/usr/bin/env python3
import click

@click.command()
@click.option('--name', default='World', help='The person to greet.')
@click.option('--count', default=1, help='Number of greetings.')
def hello(name, count):
    """A simple program that greets NAME for a total of COUNT times."""
    for _ in range(count):
        click.echo(f"Hello, {name}!")

if __name__ == '__main__':
    hello()
```

这个工具通过 `--name` 参数指定问候对象，通过 `--count` 参数指定问候次数，并且自动生成了帮助文档（通过 `--help` 查看）。

## 实战：与系统工具交互

现在，我们将应用所学知识，完成一个真实用例：与系统工具交互。我们将使用Python调用 `lsblk`（列出块设备）命令，解析其输出，并以更友好的格式呈现信息。

以下是实现此功能的脚本 `disk_info.py` 的核心部分：

```python
#!/usr/bin/env python3
import subprocess
import json
import click

![](img/a5e2dfb574afef143924f97ca6102269_1.png)

def get_lsblk_json():
    """调用 lsblk 命令并以JSON格式获取输出"""
    result = subprocess.run(['lsblk', '--json', '--output', 'NAME,SIZE,TYPE,MOUNTPOINT'],
                            capture_output=True, text=True)
    if result.returncode == 0:
        return json.loads(result.stdout)
    else:
        click.echo(f"Error running lsblk: {result.stderr}", err=True)
        return None

@click.command()
def list_disks():
    """列出系统上的磁盘和分区信息"""
    data = get_lsblk_json()
    if data:
        click.echo("Available block devices:")
        for device in data.get('blockdevices', []):
            click.echo(f"  - {device['name']} ({device['size']}) [{device['type']}]")
            if 'mountpoint' in device and device['mountpoint']:
                click.echo(f"    Mounted at: {device['mountpoint']}")

if __name__ == '__main__':
    list_disks()
```

这个脚本定义了 `get_lsblk_json` 函数来安全地调用系统命令并解析JSON输出。`list_disks` 命令则使用Click来格式化并显示这些信息，例如设备名、大小、类型和挂载点。

## 总结

本节课中我们一起学习了构建Python命令行工具的完整流程。我们从搭建虚拟开发环境开始，创建了一个最简单的无依赖脚本，然后引入了Click框架来高效处理命令行参数。最后，我们完成了一个实战项目，使用Python调用并解析系统 `lsblk` 工具的输出，从而掌握了与操作系统底层交互的基本方法。这套流程是开发更复杂命令行应用的基础。