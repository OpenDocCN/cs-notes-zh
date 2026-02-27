# 002：环境设置 🛠️

![](img/6fa6be3cfe1b9922af8dbd3d2d21e8c8_1.png)

![](img/6fa6be3cfe1b9922af8dbd3d2d21e8c8_3.png)

![](img/6fa6be3cfe1b9922af8dbd3d2d21e8c8_5.png)

在本节课中，我们将学习如何为COMP6771课程设置C++开发环境。我们将从最基本的编译开始，逐步介绍如何使用Gitlab、CMake构建系统以及VS Code编辑器来编写、构建和测试C++程序。

![](img/6fa6be3cfe1b9922af8dbd3d2d21e8c8_7.png)

![](img/6fa6be3cfe1b9922af8dbd3d2d21e8c8_8.png)

## 概述

设置开发环境通常是学习新课程时最大的挑战之一。本节内容专门设计来帮助你快速上手。我们将熟悉Gitlab、学习C++编译的基础知识、构建第一个程序并进行测试。虽然C++环境设置并非通用，但本教程将针对本课程（COMP6771）的具体要求进行说明。

![](img/6fa6be3cfe1b9922af8dbd3d2d21e8c8_10.png)

## 基础编译：从C到C++

![](img/6fa6be3cfe1b9922af8dbd3d2d21e8c8_12.png)

![](img/6fa6be3cfe1b9922af8dbd3d2d21e8c8_14.png)

![](img/6fa6be3cfe1b9922af8dbd3d2d21e8c8_15.png)

上一节我们介绍了课程概况，本节中我们来看看如何编译一个简单的C++程序。C++的编译过程与C语言非常相似。

![](img/6fa6be3cfe1b9922af8dbd3d2d21e8c8_17.png)

![](img/6fa6be3cfe1b9922af8dbd3d2d21e8c8_19.png)

首先，我们创建一个简单的C++文件。以下是一个基础示例：
```cpp
#include <iostream>

int main() {
    std::cout << "Hello world\n";
    std::cout << "hello";
    return 0;
}
```
你可以观察到它与C语言的两个主要区别：
1.  头文件从 `#include <stdio.h>` 变为了 `#include <iostream>`。`iostream`是C++的输入输出流库。
2.  输出语句从 `printf` 变为了 `std::cout <<`。这种语法用于在C++中打印内容。

现在，我们来编译这个程序。编译C++程序与编译C程序类似，但使用的是 `g++` 编译器。
```bash
g++ -o out file.cpp
```
这个命令会将 `file.cpp` 编译成一个名为 `out` 的可执行文件。运行该程序：
```bash
./out
```
程序将输出“Hello world”和“hello”。C++向后兼容C语言，这意味着你也可以使用 `g++` 编译器来编译纯C代码。

![](img/6fa6be3cfe1b9922af8dbd3d2d21e8c8_21.png)

## 多文件编译与构建系统的必要性

当程序变得复杂，涉及多个文件时，手动编译会变得繁琐。例如，如果你有 `main.cpp`、`age.cpp` 和 `age.h` 三个文件，编译命令会变长：
```bash
g++ -o out main.cpp age.cpp
```
在大型项目中，可能有成百上千个文件，管理依赖关系和编译顺序将非常困难。虽然可以使用Makefile，但它扩展性不佳。因此，现代C++项目通常使用构建系统，例如我们课程中使用的 **CMake**。构建系统可以自动化处理多文件编译、库依赖（如测试框架）等复杂任务。

![](img/6fa6be3cfe1b9922af8dbd3d2d21e8c8_23.png)

## 课程环境设置实战

![](img/6fa6be3cfe1b9922af8dbd3d2d21e8c8_25.png)

为了让你能顺利开始课程实践，以下是设置COMP6771开发环境的步骤。我们推荐使用UNSW的Vlab系统。

**第一步：克隆教程仓库**
首先，你需要将教程代码克隆到本地。在终端中执行以下命令：
```bash
git clone <教程仓库的URL>
cd <仓库目录>
```

![](img/6fa6be3cfe1b9922af8dbd3d2d21e8c8_27.png)

**第二步：运行环境设置脚本**
导航到克隆的仓库目录后，运行提供的bash脚本以安装必要组件：
```bash
bash scripts/setup.sh
```
此过程可能需要几分钟。完成后，关闭VS Code。

![](img/6fa6be3cfe1b9922af8dbd3d2d21e8c8_29.png)

![](img/6fa6be3cfe1b9922af8dbd3d2d21e8c8_30.png)

![](img/6fa6be3cfe1b9922af8dbd3d2d21e8c8_32.png)

**第三步：在VS Code中打开项目**
使用以下命令在VS Code中打开当前项目文件夹：
```bash
code .
```

![](img/6fa6be3cfe1b9922af8dbd3d2d21e8c8_34.png)

![](img/6fa6be3cfe1b9922af8dbd3d2d21e8c8_35.png)

![](img/6fa6be3cfe1b9922af8dbd3d2d21e8c8_37.png)

![](img/6fa6be3cfe1b9922af8dbd3d2d21e8c8_39.png)

**第四步：配置CMake工具链**
在VS Code中按下 `Ctrl+Shift+P`，打开命令面板，然后输入并选择“CMake: Select a Kit”。从列表中选择标记为“comp6771”的工具链。

![](img/6fa6be3cfe1b9922af8dbd3d2d21e8c8_41.png)

**第五步：配置与重新加载项目**
1.  再次按下 `Ctrl+Shift+P`，输入“CMake: Configure”并执行，以配置项目。
2.  配置完成后，需要重新加载窗口以使扩展生效。按下 `Ctrl+Shift+P`，输入“Developer: Reload Window”并执行。

![](img/6fa6be3cfe1b9922af8dbd3d2d21e8c8_43.png)

至此，你的开发环境就设置完成了。这些步骤通常每个实验或作业只需要执行一次。

![](img/6fa6be3cfe1b9922af8dbd3d2d21e8c8_45.png)

## 构建与运行你的第一个程序

![](img/6fa6be3cfe1b9922af8dbd3d2d21e8c8_47.png)

环境设置好后，我们来构建并运行一个简单的C++程序。项目代码通常位于 `source` 目录下。

![](img/6fa6be3cfe1b9922af8dbd3d2d21e8c8_49.png)

**构建程序**
在VS Code中，按下 `Ctrl+Shift+P`，输入“CMake: Build Target”并执行。在弹出的文本框中输入要构建的目标名称，例如 `hello_exe`（对应 `source/hello.cpp` 文件），然后按回车。终端会显示构建过程，成功后会提示“Build finished with exit code 0”。

![](img/6fa6be3cfe1b9922af8dbd3d2d21e8c8_51.png)

![](img/6fa6be3cfe1b9922af8dbd3d2d21e8c8_53.png)

![](img/6fa6be3cfe1b9922af8dbd3d2d21e8c8_55.png)

**运行程序**
构建生成的可执行文件位于 `build` 目录下，其路径结构与源文件对应。要运行刚构建的 `hello_exe`，可以在终端中执行：
```bash
./build/source/hello_exe
```

**添加新文件**
如果你想添加一个新文件（如 `hello2.cpp`）并让其可被构建，需要更新 `CMakeLists.txt` 文件。在该文件中添加一行，例如：
```
add_executable(hello_exe2 source/hello2.cpp)
```
保存后，需要重新加载VS Code窗口（`Ctrl+Shift+P` -> “Reload Window”），之后就可以选择 `hello_exe2` 作为构建目标了。

## 测试框架简介

在C++中，我们使用专业的测试框架（如Catch2）来编写测试，而不是简单的 `assert`。以下是一个简单的测试用例示例：
```cpp
#include <catch2/catch.hpp>
TEST_CASE("Addition works") {
    int a = 5;
    int b = 4;
    CHECK(a + b == 9);
}
```
**构建与运行测试**
测试文件在 `CMakeLists.txt` 中被定义为测试目标（例如使用 `add_test`）。你可以像构建普通程序一样构建测试目标（如 `hello_test`）。构建成功后，在终端运行：
```bash
./build/tests/hello_test
```
测试框架会执行所有 `CHECK` 断言并报告结果。在VS Code中，你也可以使用 `Ctrl+Shift+P` 并执行“Run Tests”命令来编译并运行所有测试。

## 总结

![](img/6fa6be3cfe1b9922af8dbd3d2d21e8c8_57.png)

本节课中我们一起学习了COMP6771课程的C++开发环境设置。我们从最基础的 `g++` 命令行编译开始，理解了多文件编译的复杂性，从而引入了CMake构建系统的必要性。我们一步步完成了在Vlab和VS Code中的环境配置，学习了如何构建、运行程序以及如何使用Catch2测试框架。掌握这个环境是完成本课程后续学习和作业的基础。虽然涉及一些新工具，但一旦设置完成，它们将大大简化代码管理和测试过程。