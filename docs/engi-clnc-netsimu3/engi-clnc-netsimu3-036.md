# 36：第1：在Ubuntu 22.04中安装NS-3.38 🖥️

在本节课中，我们将学习如何在Ubuntu 22.04操作系统中安装网络模拟器NS-3.38。我们将从系统环境准备开始，逐步完成下载、解压、编译和测试的完整流程。

## 概述

安装NS-3需要完成几个关键步骤：首先更新系统并安装必要的编译工具和依赖包，然后下载NS-3.38源代码，接着解压并进入目录进行编译配置，最后通过运行示例程序来验证安装是否成功。整个过程大约需要10到15分钟。

![](img/6d1999ebab153062dd97c1b5654b7fb6_1.png)

![](img/6d1999ebab153062dd97c1b5654b7fb6_3.png)

## 第一步：安装系统依赖包

在全新的Ubuntu 22.04系统上，首先需要更新软件包列表并安装一些基础编译工具和库。这些是编译NS-3所必需的。

以下是需要执行的命令：

```bash
sudo apt update
sudo apt install build-essential autoconf automake libxmu-dev
```

执行这些命令后，系统将安装`gcc`、`g++`、`make`等编译工具以及`autoconf`、`automake`等自动化配置工具。

## 第二步：下载NS-3.38源代码

接下来，我们需要获取NS-3.38的源代码。访问NS-3官方网站（nsnam.org），找到并点击“Latest Release”链接，当前最新版本是NS-3.38。下载其压缩包（通常是`.tar.bz2`格式）到本地。

## 第三步：安装额外的可选包（推荐）

为了确保NS-3的所有功能（如网络动画`NetAnim`、数据包分析`Wireshark`等）都能正常工作，建议安装一系列额外的软件包。这可以避免后续因缺少依赖而出现的错误。

你可以从视频描述或NS-3官方文档中复制一个更全面的安装命令列表。一个示例如下：

```bash
sudo apt install g++ python3 python3-dev pkg-config sqlite3 cmake libxml2-dev libgtk-3-dev libboost-all-dev libgsl-dev libsqlite3-dev qtbase5-dev qtchooser qt5-qmake qtbase5-dev-tools gir1.2-goocanvas-2.0 python3-gi python3-gi-cairo python3-pygraphviz gir1.2-gtk-3.0 ipython3 openmpi-bin openmpi-common openmpi-doc libopenmpi-dev tcpdump wireshark
```

执行此命令会安装一整套开发库和工具，具体耗时取决于你的网络和电脑速度。

## 第四步：解压源代码包

下载完成后，需要解压源代码包。有两种常用方法：使用图形界面（GUI）或终端命令。为了便于新手理解，这里介绍图形界面方法。

1.  找到下载的压缩文件（例如 `ns-allinone-3.38.tar.bz2`）。
2.  右键点击该文件。
3.  选择“提取到此处”或“Extract Here”。
4.  建议将解压后的文件夹放在你的用户主目录（`/home/你的用户名/`）下，这样便于后续查找和操作。

解压完成后，你会在主目录下看到一个名为 `ns-allinone-3.38` 的文件夹。

## 第五步：配置与编译NS-3

现在进入核心的编译环节。我们需要使用NS-3自带的构建脚本进行配置和编译。

1.  打开终端。
2.  使用 `cd` 命令进入解压后的目录：
    ```bash
    cd ns-allinone-3.38
    ```
3.  运行配置和编译命令。以下命令启用了示例程序和测试套件：
    ```bash
    ./build.py --enable-examples --enable-tests
    ```

这个编译过程会持续10到15分钟，期间终端会输出大量的编译信息。请耐心等待直到完成。

## 第六步：测试安装是否成功

![](img/6d1999ebab153062dd97c1b5654b7fb6_5.png)

编译完成后，我们需要验证NS-3是否被正确安装。最直接的方法是运行其自带的示例程序。

首先，我们可以运行一个简单的“Hello Simulator”程序：

```bash
./ns3 run hello-simulator
```

如果终端输出“Hello Simulator”字样，则表明核心安装成功。

此外，NS-3还提供了许多其他示例。你可以尝试运行 `first` 和 `second` 这两个基础示例：

```bash
./ns3 run first
./ns3 run second
```

成功运行这些示例并看到相应的网络模拟输出，即证明你的NS-3环境已经完全准备就绪，可以开始进行网络协议的仿真实验了。

## 总结

![](img/6d1999ebab153062dd97c1b5654b7fb6_7.png)

本节课中，我们一起学习了在Ubuntu 22.04系统上安装NS-3.38的完整步骤。我们首先安装了必要的系统依赖和编译工具，然后下载并解压了源代码。接着，我们通过运行 `./build.py` 命令配置和编译了NS-3。最后，通过执行 `hello-simulator`、`first` 等示例程序，我们验证了安装的成功。现在，你已经拥有了一个可用的NS-3仿真环境，可以开始探索网络模拟的世界了。