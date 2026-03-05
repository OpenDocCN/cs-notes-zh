# Python打包教程：P6：2021年Python打包新标准

![](img/c0cc4b88a8773b6e24b57cc4aa655318_1.png)

![](img/c0cc4b88a8773b6e24b57cc4aa655318_3.png)

![](img/c0cc4b88a8773b6e24b57cc4aa655318_5.png)

在本节课中，我们将学习Python打包的最新标准，特别是如何使用`pyproject.toml`文件来编写易于构建的项目。我们将了解如何维护明确、可预测且可读的构建信息，这些信息可以被人类和机器更好地理解。

## 概述：为什么需要新的打包标准？ 🎯

过去，Python打包主要依赖于`setup.py`和`setup.cfg`文件，这导致构建过程不够明确，且严重依赖于特定的工具链。新的`pyproject.toml`标准旨在解决这些问题，通过分离构建前端、构建后端和集成前端，为项目提供更灵活、更可靠的构建方式。

## 核心概念：现代Python打包架构 🏗️

上一节我们介绍了新标准的必要性，本节中我们来看看现代Python打包的核心架构。它将打包过程清晰地分为三个独立的类别。

以下是三种主要的工具类别：

1.  **构建后端**：负责将源代码转换为分发格式（如wheel文件）。项目作者选择并记录在`pyproject.toml`中。
    *   **公式/代码示例**：`build-backend = “setuptools.build_meta”`

2.  **构建前端**：处理用户交互（如命令行界面、显示进度和错误）。它负责为构建后端准备执行环境。
    *   **公式/代码示例**：`pip`、`build`

3.  **集成前端**：负责安装已构建的分发包，并解析和安装其依赖项。
    *   **公式/代码示例**：`pip`、`conda`

这种分离使得项目作者、构建者和安装者可以独立选择各自偏好的工具，提高了生态系统的灵活性。

![](img/c0cc4b88a8773b6e24b57cc4aa655318_7.png)

## 历史回顾：从distutils到pip 📜

![](img/c0cc4b88a8773b6e24b57cc4aa655318_9.png)

上一节我们了解了现代打包架构，本节中我们来看看Python打包是如何一步步发展到今天的。理解历史有助于我们明白为什么新标准是必要的。

Python打包的演变大致经历了以下几个阶段：

1.  **distutils**：Python 1.6引入的标准库模块。它提供了最初的打包功能，但功能有限，且已被弃用。
2.  **setuptools**：作为distutils的扩展出现，引入了`easy_install`作为集成前端，并增加了依赖管理等功能。
3.  **pip**：取代了`easy_install`，成为主流的集成前端。它简化了安装过程，并能从版本控制系统安装包。

长期以来，`pip`和`setuptools`的组合掩盖了构建前端、构建后端和集成前端的界限，导致了一些混乱和“引导问题”。

## 关键问题：为什么需要pyproject.toml？ ❓

上一节我们回顾了历史，本节中我们来看看一个具体的、由旧标准导致的问题，以及`pyproject.toml`如何解决它。

一个常见的问题是“缺少wheel包”的错误。当使用`pip`从源代码安装一个没有`pyproject.toml`的旧项目时，可能会遇到类似以下的错误：

```
error: invalid command ‘bdist_wheel’
```

这个错误的根源在于，`pip`（作为构建前端）试图调用`setuptools`（作为构建后端）来构建一个wheel文件，但`setuptools`本身并不知道如何构建wheel，它需要一个额外的`wheel`包。旧的标准无法明确声明这个构建时依赖。

**解决方案**：在项目的`pyproject.toml`文件中明确声明构建后端及其依赖。

```toml
[build-system]
requires = [“setuptools”, “wheel”]
build-backend = “setuptools.build_meta”
```

![](img/c0cc4b88a8773b6e24b57cc4aa655318_11.png)

这样，任何构建工具在开始构建前，都会确保这些依赖已安装，从而避免了令人困惑的错误。

## 实践指南：如何创建和使用pyproject.toml 🛠️

上一节我们了解了`pyproject.toml`的重要性，本节中我们来看看如何实际为你的项目创建和使用它。

![](img/c0cc4b88a8773b6e24b57cc4aa655318_13.png)

使用`pyproject.toml`能带来诸多好处：构建环境明确、工具选择灵活、项目结构更清晰。

![](img/c0cc4b88a8773b6e24b57cc4aa655318_15.png)

以下是现代化你的项目打包的步骤：

1.  **创建基本的`pyproject.toml`文件**：即使你仍使用旧工具，添加此文件也能避免“wheel错误”。
    ```toml
    [build-system]
    requires = [“setuptools”, “wheel”]
    build-backend = “setuptools.build_meta”
    ```

2.  **停止将`setup.py`用作脚本**：它的脚本功能正在被淘汰。将构建逻辑交给外部的构建工具（如`build`）。

3.  **将元数据迁移到`setup.cfg`**：`setuptools`目前主要通过`setup.cfg`读取项目元数据（如名称、版本、依赖）。尝试将`setup.py`中的所有配置信息移入`setup.cfg`。

4.  **最终目标：移除`setup.py`**：当所有配置都移至`setup.cfg`和`pyproject.toml`后，你可以完全删除`setup.py`文件，实现完全声明式的配置。

## 总结 📝

![](img/c0cc4b88a8773b6e24b57cc4aa655318_17.png)

本节课中我们一起学习了2021年Python打包的新标准。我们了解了现代打包架构将过程分为构建后端、构建前端和集成前端。我们回顾了打包工具的历史演变，并分析了旧标准导致的典型问题。最后，我们掌握了如何通过创建和配置`pyproject.toml`文件来现代化项目构建，使其更明确、可靠和易于维护。

![](img/c0cc4b88a8773b6e24b57cc4aa655318_19.png)

![](img/c0cc4b88a8773b6e24b57cc4aa655318_21.png)

记住，打包是一个不断发展的领域，持续学习最新的实践和工具对你的项目大有裨益。