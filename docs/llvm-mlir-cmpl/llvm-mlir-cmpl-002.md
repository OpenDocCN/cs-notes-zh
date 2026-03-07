# 002：基础环境搭建 🛠️

在本节课中，我们将学习如何为Serene编译器项目搭建基础的开发环境。这包括安装必要的依赖项，特别是从源代码编译LLVM，以及了解项目自带的构建脚本。

## 概述 📋

在开始编译器开发之前，我们需要配置好开发环境。本节将指导你完成LLVM的安装、构建脚本的使用，并对项目源代码结构进行初步了解。

## 安装依赖项

以下是构建Serene编译器所需的主要依赖项。建议从源代码编译LLVM以获得最佳兼容性。

### LLVM项目

LLVM是核心依赖。虽然许多Linux发行版通过包管理器提供预编译的LLVM，但为了获得更好的结果并满足Serene的特定需求（例如后续使用MLIR），建议从源代码编译。

*   **版本选择**：你可以使用当前的稳定版本（如LLVM 17），也可以使用最新的开发版本。Serene项目基于C++17。
*   **编译架构**：需要至少支持X86架构。
*   **编译模式**：建议使用`Release`模式进行编译。`Debug`模式编译时间极长，且会拖慢后续基于LLVM的代码编译速度。

### 其他工具

除了LLVM，还需要以下工具，它们通常可以通过系统包管理器安装：

*   **CMake**：构建系统生成器。
*   **Ninja**：构建工具。
*   **ccache**：编译缓存工具，能显著加速重复编译过程。
*   **Valgrind**：用于检测内存泄漏等问题的工具。

## 从源代码编译LLVM

上一节我们介绍了所需的依赖项，本节中我们来看看如何具体从源代码编译LLVM。

1.  **获取源代码**：克隆或下载LLVM的源代码。
2.  **创建构建目录**：在源代码目录外创建一个独立的构建目录。
3.  **配置CMake**：在构建目录中运行CMake命令来生成Ninja构建系统。需要启用一些关键选项。

以下是配置CMake时建议使用的重要选项：

```bash
cmake -G Ninja ../llvm-source \
  -DCMAKE_BUILD_TYPE=Release \
  -DLLVM_TARGETS_TO_BUILD="X86" \
  -DLLVM_ENABLE_PROJECTS="clang;lld;mlir;clang-tools-extra;compiler-rt" \
  -DCMAKE_C_COMPILER=clang \
  -DCMAKE_CXX_COMPILER=clang++
```

> **注意**：`-DCMAKE_C_COMPILER=clang` 和 `-DCMAKE_CXX_COMPILER=clang++` 这两个选项要求你的系统已安装Clang。如果未安装，可以省略，使用系统默认的GCC编译LLVM，或者先通过包管理器安装Clang。

4.  **编译与安装**：使用`ninja`命令进行编译，完成后运行`ninja install`进行安装。
5.  **配置环境变量**：将LLVM安装目录下的`bin`文件夹路径添加到系统的`PATH`环境变量中。

> **提示**：编译LLVM是一个耗时很长的过程，在一台现代笔记本电脑上可能需要1到1.5小时，请耐心等待。

## 使用Serene构建脚本

LLVM安装完成后，我们就可以开始构建Serene项目了。项目根目录下提供了一个名为`b`的构建脚本，它是CMake的封装，简化了构建流程。

### 脚本功能简介

该脚本接收子命令作为参数，并执行相应的操作。在运行脚本前，请确保位于Serene项目的根目录下。

![](img/99c2abdffacc17fd11a975f25f75ec1f_1.png)

![](img/99c2abdffacc17fd11a975f25f75ec1f_3.png)

以下是`b`脚本支持的一些重要子命令：

![](img/99c2abdffacc17fd11a975f25f75ec1f_5.png)

*   `./b build`：清理旧构建，重新生成构建系统并从头编译所有内容（Debug模式）。
*   `./b build-release`：功能同上，但使用Release模式编译。
*   `./b compile`：不重新生成构建系统，仅编译发生更改的文件。在开发过程中最常使用。
*   `./b run <参数>`：运行已编译的Serene编译器二进制文件，并将`<参数>`传递给它。
*   `./b test`：清理并构建整个项目，然后运行所有测试用例。
*   `./b memcheck`：使用Valgrind工具构建并运行项目，用于调试内存泄漏问题。

![](img/99c2abdffacc17fd11a975f25f75ec1f_7.png)

### 示例：构建与运行

![](img/99c2abdffacc17fd11a975f25f75ec1f_9.png)

首先，使用`build`命令进行完整构建：

![](img/99c2abdffacc17fd11a975f25f75ec1f_11.png)

```bash
./b build
```

![](img/99c2abdffacc17fd11a975f25f75ec1f_13.png)

如果后续修改了源代码，可以使用`compile`命令进行增量编译，这比重新构建要快得多：

![](img/99c2abdffacc17fd11a975f25f75ec1f_15.png)

```bash
./b compile
```

![](img/99c2abdffacc17fd11a975f25f75ec1f_17.png)

编译成功后，可以使用`run`命令来运行编译器。例如，编译一个Serene源文件并输出其MLIR表示：

```bash
./b run --show-mlir /path/to/hello.sn
```

## 项目源代码结构简介

在深入了解代码之前，让我们先熟悉一下Serene项目的目录结构，这有助于你更好地导航代码库。

*   `bin/`：存放`serene.cpp`，这是编译器的主入口点。
*   `build/` 和 `build-release/`：由构建脚本生成的临时构建目录。
*   `include/serene/`：存放所有的头文件（`.h`、`.hpp`）。
*   `src/serene/`：存放所有C++源文件（`.cpp`）的实现。头文件对应的实现通常放在这里，且文件名与头文件一致。
*   `test/`：存放所有的测试用例。
*   `dev.org`：一个Org-mode格式的文件，包含了项目的高层待办事项（TODO）和大量与编译器构建相关的学习资源链接，对于初学者非常有价值。

## 总结 🎯

本节课我们一起学习了搭建Serene编译器开发环境的基础步骤。我们强调了从源代码编译LLVM的重要性，介绍了项目自带的构建脚本`b`及其常用命令，并对项目的源代码结构有了初步了解。现在，你的开发环境应该已经准备就绪，可以开始探索和修改Serene编译器的代码了。

![](img/99c2abdffacc17fd11a975f25f75ec1f_19.png)

在下一节课中，我们将探讨编程语言设计的一些高层基本概念，并分析使用LLVM的优缺点。