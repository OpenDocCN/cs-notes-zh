# 构建大规模云计算解决方案：P22：GitHub Actions 介绍 🚀

在本节课中，我们将学习如何为项目设置 GitHub Actions，以实现自动化测试和持续集成。我们将从零开始创建一个工作流，并了解其核心组成部分。

---

## 概述

上一节我们完成了项目的基础脚手架搭建。本节中，我们将进入最后一步：设置 GitHub Actions。这是一个自动化工作流工具，可以在代码推送时自动执行一系列任务，如安装依赖、代码检查、运行测试和格式化代码，从而确保代码质量。

## 创建工作流

以下是创建 GitHub Actions 工作流的步骤。

首先，在 GitHub 仓库中点击 **Actions** 图标。界面会显示一些预设的工作流模板，例如部署 Node.js 应用、容器或到 Google Cloud Kubernetes 服务。但我们选择从头开始设置。

我们选择设置一个默认工作流。系统会生成一个名为 `main.yml` 的 YAML 格式文件。这个文件定义了一个基本工作流。简单来说，它告诉 GitHub：当代码被推送到 `master` 或 `main` 分支时，执行一系列操作。如果你已经设置了 `Makefile`，这个过程会变得非常简单。

接下来，我将删除默认内容，并替换为一个我过去使用过的 GitHub Actions 配置。让我们看看其中的一些参数。

```yaml
name: Python application test with Github actions

on: [push]

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
    - uses: actions/checkout@v2
    - name: Set up Python 3.8
      uses: actions/setup-python@v2
      with:
        python-version: '3.8'
    - name: Install dependencies
      run: |
        make install
    - name: Lint with flake8
      run: |
        make lint
    - name: Test with pytest
      run: |
        make test
    - name: Format code
      run: |
        make format
```

![](img/82432ee794309b5b1eb7c4d172000b24_1.png)

工作流文件会被提交到 `.github/workflows` 目录下，文件名为 `main.yml`。你可以根据需要创建任意多个这样的文件，每个文件都会独立运行其定义的任务。例如，之后我们可以设置基于 Google Cloud 的部署或基于 Azure 的测试项目。

## 查看运行结果

要查看工作流的运行情况，可以返回 **Actions** 选项卡。你会看到最近运行的记录，例如“1分钟前”，耗时约29秒。点击记录可以查看详细步骤。

YAML 文件中的每一行都对应界面中的一个步骤。首先是设置任务，然后下载指定的虚拟环境（如 Ubuntu 18.04）。接着设置 Python 3.8，安装 CPython 3.8.6。之后，通过 `make install` 安装项目依赖。这一步验证了项目依赖是否正确。然后，通过 `make lint` 检查代码语法。每次代码变更都会自动验证项目是否正常工作。接着运行 `make test` 执行测试。最后，通过 `make format` 格式化代码。

![](img/82432ee794309b5b1eb7c4d172000b24_3.png)

## 添加状态徽章

![](img/82432ee794309b5b1eb7c4d172000b24_4.png)

![](img/82432ee794309b5b1eb7c4d172000b24_5.png)

为项目添加状态徽章是一个好做法。在构建主页面，点击“创建状态徽章”图标，然后复制徽章的 Markdown 代码。将其添加到项目的 `README.md` 文件中。

```markdown
![Build Status](https://github.com/your-username/your-repo/actions/workflows/main.yml/badge.svg)
```

添加后，徽章会显示每次操作的结果（通过或失败）。这是基于 SaaS 的持续集成系统的一个非常有用的功能。

## 测试失败场景

为了测试工作流在代码出错时的反应，我们可以故意引入一个错误。首先，通过 `git pull` 拉取最新代码。然后，在代码文件（例如 `hello.py`）中添加错误的语法，比如一个未完成的变量定义。

```python
# 这是一个错误的代码示例
bad_variable =  # 缺少赋值
```

![](img/82432ee794309b5b1eb7c4d172000b24_7.png)

![](img/82432ee794309b5b1eb7c4d172000b24_8.png)

保存后，本地运行 `make lint` 会失败。我们提交这个错误代码以触发 GitHub Actions。

```bash
git add hello.py
git commit -m "添加错误代码以测试构建"
git push
```

推送后，GitHub Actions 会自动触发新的构建。在 **Actions** 选项卡中，可以看到构建状态变为橙色（运行中）。点击进入可以实时查看日志。构建会在 `make lint` 步骤失败，并给出具体错误信息（例如“第4行第5字符：无效语法”），这有助于调试。

![](img/82432ee794309b5b1eb7c4d172000b24_10.png)

要修复此问题，只需注释掉或更正错误的代码行，然后再次提交。提交后，工作流会重新运行，并通过所有检查。

## 核心价值与最佳实践

![](img/82432ee794309b5b1eb7c4d172000b24_12.png)

![](img/82432ee794309b5b1eb7c4d172000b24_13.png)

这个自动化构建步骤的核心价值在于它能自动确保项目代码的质量，并提供详细的输出信息。对于 Python 新手、数据科学初学者或编程新人来说，一个常见的误区是忽视自动化测试，认为它增加了额外工作量或看不到直接价值。然而，就像使用 Python 虚拟环境一样，设置持续集成只会帮助你产出更高质量的代码，并加快开发速度。因此，对于任何涉及 Python 的软件项目，这都是一项必需的最佳实践。

---

## 总结

![](img/82432ee794309b5b1eb7c4d172000b24_15.png)

![](img/82432ee794309b5b1eb7c4d172000b24_16.png)

本节课中，我们一起学习了如何为项目设置 GitHub Actions 工作流。我们创建了一个 YAML 配置文件，定义了在代码推送时自动执行的步骤（安装、检查、测试、格式化）。我们还学习了如何查看运行结果、添加状态徽章，以及如何通过引入和修复错误来测试工作流的有效性。掌握持续集成是保证代码质量和提升开发效率的关键实践。