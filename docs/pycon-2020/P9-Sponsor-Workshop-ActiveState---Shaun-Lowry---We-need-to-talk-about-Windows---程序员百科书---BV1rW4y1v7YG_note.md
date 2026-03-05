# Python构建与分发：P9：我们需要谈谈Windows

![](img/5635b753cebce3913b253195e367fbcd_0.png)

## 概述
在本节课中，我们将探讨Python在Windows平台上的构建过程，分析其与Linux和macOS构建的差异，并了解ActiveState平台如何致力于改进这一过程，以提供更可靠、可重复且易于维护的Python运行时。

## 背景：ActiveState平台简介
在深入探讨Windows构建的具体问题之前，我们先简要了解一下ActiveState及其平台。ActiveState在构建和分发开源语言运行时方面拥有超过20年的经验，是Python软件基金会的创始成员之一。其核心产品ActiveState平台旨在为开发者提供自定义的、跨平台的运行时环境。

该平台允许用户选择所需依赖项，并生成攻击面更小的轻量级分发版。它通过自动依赖解析、多层缓存和分布式构建系统，高效地处理构建工作。平台目前支持Python、Perl和Tcl，未来将通过API支持更多语言。

## 三大平台的Python构建对比
上一节我们介绍了ActiveState平台，本节中我们来看看在不同操作系统上构建Python核心的差异。我们将对比Linux、macOS和Windows的构建流程、复杂度和面临的挑战。

### Linux上的Python构建
在Linux上构建Python相对简单直接。

以下是典型的Linux构建步骤：
1.  确保系统已安装基本的开发构建工具（如`gcc`, `make`）。
2.  运行配置脚本（`./configure`），可以使用默认选项或指定自定义路径（如OpenSSL库的位置）。
3.  执行`make`命令进行编译。

构建过程可以概括为以下代码流程：
```bash
# 安装基础构建工具 (以Debian/Ubuntu为例)
sudo apt-get install build-essential

# 进入Python源代码目录
cd Python-3.x.x

![](img/5635b753cebce3913b253195e367fbcd_2.png)

# 配置构建参数
./configure --prefix=/usr/local

![](img/5635b753cebce3913b253195e367fbcd_4.png)

# 编译
make

![](img/5635b753cebce3913b253195e367fbcd_6.png)

# 安装 (可选)
sudo make install
```
系统上已安装的依赖库版本通常兼容，即使不兼容，也较容易通过包管理器安装或自行编译特定版本来解决。

![](img/5635b753cebce3913b253195e367fbcd_8.png)

### macOS上的Python构建
在macOS上构建Python与Linux类似，但通常采用框架构建方式。

以下是macOS构建的关键点：
1.  需要安装Xcode命令行工具。
2.  使用`--enable-framework`选项运行配置脚本。
3.  依赖管理可以通过Homebrew等工具方便地处理。

构建命令示例如下：
```bash
cd Python-3.x.x
./configure --enable-framework
make
```
与Linux类似，依赖库版本的选择和管理也相对灵活。

### Windows上的Python构建
现在，我们需要重点讨论Windows。Windows上的Python构建过程与前两者有显著不同，它严重依赖于本地的Visual Studio构建系统。

以下是Windows构建的主要特点和挑战：
1.  **环境要求苛刻**：需要特定版本的Visual Studio、特定的工作负载以及合适的Windows SDK组合。在未专门配置的机器上几乎不可能成功构建。
2.  **构建系统独特**：Python使用一系列Visual C++项目文件（`.vcxproj`）和批处理文件进行构建。核心入口点是 `PCbuild\build.bat`。
3.  **依赖管理僵化**：C库依赖（如OpenSSL）的版本在Python发布时即被固定，无法轻易更新。这带来了安全风险和灵活性限制。
4.  **缺乏透明度和缓存能力**：对于像ActiveState这样的外部构建系统，无法洞察或控制这些硬编码的依赖，导致无法为构建输出生成准确的哈希值（Merkle Tree），从而难以实现有效的缓存和构建复用。

一个典型的Windows构建命令如下：
```cmd
cd Python-3.x.x\PCbuild
build.bat -p x64
```
此过程会通过批处理脚本自动获取外部依赖的源代码或二进制文件。

![](img/5635b753cebce3913b253195e367fbcd_10.png)

![](img/5635b753cebce3913b253195e367fbcd_12.png)

## ActiveState的解决方案与未来计划
面对Windows构建的诸多挑战，ActiveState正在采取行动进行改进。

当前，为了能够更新关键依赖（如OpenSSL），ActiveState采用了一种临时方案：下载所需版本的依赖库，并将其解压到构建系统期望的目录结构中，替换掉旧的版本。但这并非长久之计。

因此，ActiveState计划开发一个新的、更灵活的Visual C++/MSBuild构建系统。该系统的核心目标是：
*   **支持预构建库作为依赖**：允许使用像ActiveState平台这样的外部系统来提供依赖项，同时也兼容传统的从源码构建的方式。
*   **贡献给上游社区**：ActiveState计划将此改进后的构建系统贡献给Python社区，希望被上游采纳。
*   **提升跨平台一致性**：最终目标是使Windows上的Python构建能像在Linux和macOS上一样，实现可靠、可重复且易于升级的体验，让开发者能轻松获取安全、稳定的Python版本。

![](img/5635b753cebce3913b253195e367fbcd_14.png)

## 总结
本节课中我们一起学习了Python在不同操作系统上的构建过程。我们看到，在Linux和macOS上构建Python相对顺畅，而在Windows上则面临环境配置复杂、依赖管理僵化、缺乏构建缓存等挑战。ActiveState基于其多年的企业级运行时构建经验，不仅揭示了这些问题，还正着手通过开发一个更灵活的构建系统来从根本上改善Windows上的Python构建与分发体验，旨在为所有Python开发者提供更好的跨平台一致性。