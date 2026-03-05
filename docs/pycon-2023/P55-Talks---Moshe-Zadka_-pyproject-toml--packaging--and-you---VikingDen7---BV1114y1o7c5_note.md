# Python打包与`pyproject.toml`：P55：深入解析现代Python项目配置 🐍

![](img/394b7a9f6bd3e3b1b25fd09771c8e7de_1.png)

在本教程中，我们将学习现代Python项目打包的核心工具——`pyproject.toml`文件。我们将了解它的结构、优势以及如何利用它来简化项目配置和依赖管理。

---

## 概述 📋

`pyproject.toml`是Python社区推出的一个标准配置文件，旨在统一项目构建、打包和依赖管理的配置方式。它取代了传统的`setup.py`、`setup.cfg`、`requirements.txt`等多个文件，将所有配置集中在一个地方。

---

## 为什么选择 `pyproject.toml`？ 🤔

上一节我们介绍了`pyproject.toml`的基本概念，本节中我们来看看它相比传统配置方式的优势。

使用`pyproject.toml`的主要好处是简化了配置过程。你不再需要维护多个分散的配置文件。

以下是`pyproject.toml`的几个核心优势：

1.  **统一配置**：将项目元数据、构建系统要求和工具配置集中在一个文件中。
2.  **工具无关性**：支持多种构建后端（如`setuptools`、`flit`、`poetry`），不锁定特定工具。
3.  **声明式语法**：使用TOML格式，清晰易读，易于编写和维护。
4.  **更好的互操作性**：被现代Python工具链（如`pip`、`build`、`twine`）广泛支持。

---

## `pyproject.toml` 文件结构解析 🏗️

了解了其优势后，我们来看看一个典型的`pyproject.toml`文件包含哪些部分。

一个基本的`pyproject.toml`文件主要包含两个部分：`[build-system]`和`[project]`。

以下是各部分的详细说明：

*   **`[build-system]`**：指定构建项目所需的工具。
    ```toml
    [build-system]
    requires = ["setuptools>=61.0", "wheel"]
    build-backend = "setuptools.build_meta"
    ```
    这段代码定义了构建依赖和使用的构建后端。

*   **`[project]`**：定义项目的核心元数据。
    ```toml
    [project]
    name = "my-awesome-package"
    version = "0.1.0"
    authors = [
      {name = "Your Name", email = "you@example.com"},
    ]
    description = "一个非常棒的Python包"
    readme = "README.md"
    license = {text = "MIT"}
    classifiers = [
        "Programming Language :: Python :: 3",
        "License :: OSI Approved :: MIT License",
    ]
    dependencies = [
        "requests>=2.25.0",
        "numpy>=1.20.0",
    ]
    ```
    这里定义了包名、版本、作者、依赖等关键信息。

---

## 定义入口点与脚本 🚪

配置好项目基本信息后，我们还需要定义如何执行我们的代码。这就是入口点的作用。

入口点允许你将包中的特定函数注册为命令行工具或插件。

以下是定义入口点的示例：

```toml
[project.scripts]
my-cli-tool = "mypackage.module:main_function"

[project.gui-scripts]
my-gui-app = "mypackage.gui:launch"

[project.entry-points."some_plugin_group"]
my-plugin = "mypackage.plugin:initialize"
```
*   `project.scripts` 创建命令行脚本。
*   `project.gui-scripts` 创建图形界面脚本（较少使用）。
*   `project.entry-points` 用于插件系统，允许其他工具发现并使用你的模块。

---

## 使用工具特定配置 ⚙️

`pyproject.toml`的强大之处还在于它能配置各种开发工具，保持项目环境的一致性。

你可以为`black`、`isort`、`pytest`、`mypy`等工具添加配置节。

以下是配置代码格式化和测试工具的示例：

```toml
# 配置 Black 代码格式化工具
[tool.black]
line-length = 88
target-version = ['py311']

# 配置 isort 导入排序工具
[tool.isort]
profile = "black"
line_length = 88

# 配置 pytest 测试框架
[tool.pytest.ini_options]
testpaths = ["tests"]
addopts = "-v --strict-markers"
```
通过这种方式，所有开发者都能使用相同的工具设置，确保代码风格统一。

---

## 项目布局与打包实践 📁

正确的项目布局对于打包至关重要。一个清晰的结构能让工具更容易地找到和包含你的代码。

建议将你的Python源代码放在一个以项目名命名的目录中（即`src/`布局或扁平布局）。

以下是两种常见的项目布局示例：

1.  **`src/` 布局**（推荐，避免导入混淆）：
    ```
    my_project/
    ├── pyproject.toml
    ├── README.md
    ├── src/
    │   └── my_package/
    │       ├── __init__.py
    │       └── module.py
    └── tests/
    ```

2.  **扁平布局**：
    ```
    my_project/
    ├── pyproject.toml
    ├── README.md
    ├── my_package/
    │   ├── __init__.py
    │   └── module.py
    └── tests/
    ```
在`pyproject.toml`中，你可以使用`tool.setuptools`来明确指定包目录：
```toml
[tool.setuptools]
packages = ["my_package"]
```

---

## 构建与发布你的包 🚀

所有配置完成后，最后一步就是构建并发布你的包。

现代Python打包使用`build`和`twine`工具，它们能很好地与`pyproject.toml`协同工作。

以下是构建和发布包的步骤：

1.  **安装构建工具**：
    ```bash
    pip install build twine
    ```

![](img/394b7a9f6bd3e3b1b25fd09771c8e7de_3.png)

2.  **构建分发包**：
    ```bash
    python -m build
    ```
    这个命令会在`dist/`目录下生成`.tar.gz`和`.whl`文件。

3.  **上传到PyPI**：
    ```bash
    twine upload dist/*
    ```
    首次上传需要配置PyPI认证信息。

---

## 总结 🎯

本节课中我们一起学习了现代Python项目配置的核心——`pyproject.toml`文件。

我们探讨了它的优势、基本结构、如何定义项目元数据和依赖、配置入口点以及集成各种开发工具。通过采用`pyproject.toml`，你可以创建一个更简洁、更标准化且易于维护的Python项目，与整个Python生态系统无缝集成。记住，从新项目开始就使用它是一个最佳实践。