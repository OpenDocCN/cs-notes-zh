# 网络模拟器3教程：29：在Ubuntu 20.04上安装NS-3.31 🛠️

在本节课中，我们将学习如何在64位Ubuntu 20.04操作系统上安装NS-3.31网络模拟器。我们将提供详细的逐步指导，确保初学者能够顺利完成安装。

## 概述

NS-3.31是网络模拟器3的一个版本。由于Python 2已停止支持，安装过程需要适配Python 3。本教程将指导你完成从系统更新到编译NS-3.31的全部步骤。

## 安装步骤

上一节我们介绍了课程目标，本节中我们来看看具体的安装步骤。以下是安装NS-3.31所需的完整命令序列。

首先，确保你有一个新安装的Ubuntu 20.04系统。打开终端，执行以下命令来更新系统并安装必要的构建工具。

```bash
sudo apt update
sudo apt install build-essential autoconf automake libxmu-dev
```

![](img/52c402136a02583284e3bed802ea45ec_1.png)

![](img/52c402136a02583284e3bed802ea45ec_3.png)

`build-essential` 包含了编译任何应用程序所需的基本软件。`autoconf` 和 `automake` 是自动化配置工具。`libxmu-dev` 是用于图形性能的开发库。

接下来，安装一系列NS-3.31运行所依赖的软件包。以下是需要安装的包列表。

```bash
sudo apt install gcc g++ python python3 python3-dev pkg-config sqlite3 cmake
sudo apt install python3-setuptools git mercurial qt5-default
sudo apt install gir1.2-goocanvas-2.0 python3-gi python3-gi-cairo python3-pygraphviz
sudo apt install gir1.2-gtk-3.0 ipython3 openmpi-bin openmpi-common openmpi-doc
sudo apt install libopenmpi-dev libxml2 libxml2-dev libc6-dev libc6-dev-i386
sudo apt install libclang-dev llvm-dev automake python3-pip
sudo apt install libgtk-3-dev vtun lxc uml-utilities
sudo apt install libboost-signals-dev libboost-filesystem-dev
sudo apt install wireshark
```

![](img/52c402136a02583284e3bed802ea45ec_5.png)

在安装Wireshark时，系统会询问是否允许非超级用户捕获数据包。根据你的安全策略选择“是”或“否”。

安装过程需要下载约442MB的数据，具体时间取决于你的网速。

## 配置与编译NS-3.31

所有依赖包安装完成后，我们就可以开始配置和编译NS-3.31了。首先，需要获取NS-3.31的源代码。

![](img/52c402136a02583284e3bed802ea45ec_7.png)

假设你已经从官网下载了 `ns-allinone-3.31.tar.bz2` 文件，并将其放置在 `~/Downloads` 目录下。请将其复制到你的主目录并解压。

```bash
cp ~/Downloads/ns-allinone-3.31.tar.bz2 ~/
cd ~
tar -xjf ns-allinone-3.31.tar.bz2
```

![](img/52c402136a02583284e3bed802ea45ec_9.png)

解压后，你会得到一个名为 `ns-allinone-3.31` 的文件夹。进入该文件夹，准备构建NS-3。

![](img/52c402136a02583284e3bed802ea45ec_11.png)

![](img/52c402136a02583284e3bed802ea45ec_13.png)

```bash
cd ns-allinone-3.31
```

![](img/52c402136a02583284e3bed802ea45ec_15.png)

现在，运行构建脚本。以下命令将启用示例程序并进行构建。

![](img/52c402136a02583284e3bed802ea45ec_17.png)

```bash
./build.py --enable-examples --enable-tests
```

构建过程会编译大量模块，可能需要10到20分钟。构建完成后，终端会显示已构建和未构建的模块列表。

在本次安装中，有五个模块可能不会被构建：
*   `brite`
*   `click`
*   `openflow`
*   `visualizer`

`visualizer` 是NS-3内置的动画工具，`openflow` 用于软件定义网络，`click` 是模块化路由器。对于初学者的大多数实验，这些模块不是必需的。

## 验证安装

![](img/52c402136a02583284e3bed802ea45ec_19.png)

![](img/52c402136a02583284e3bed802ea45ec_20.png)

构建成功后，我们需要验证NS-3是否安装正确。进入NS-3的主目录并运行一个简单的测试。

```bash
cd ns-3.31
./waf --run hello-simulator
```

如果安装成功，你将看到输出 “Hello Simulator”。这表明核心模拟器已正常工作。

为了进一步测试，我们可以运行教程中的示例程序。

![](img/52c402136a02583284e3bed802ea45ec_22.png)

```bash
cd examples/tutorial
cp first.cc second.cc
./waf --run first
```

运行 `first` 示例（一个简单的点对点网络模拟）可以确认更多功能是否正常。关于此示例的详细解释，可以参考本系列的其他教程视频。

## 总结

本节课中我们一起学习了在全新的Ubuntu 20.04系统上安装NS-3.31网络模拟器的完整流程。我们首先更新了系统并安装了所有必要的依赖包，然后下载、配置并编译了NS-3.31源代码，最后通过运行测试程序验证了安装成功。遵循这些步骤，你应该能够搭建起可用的NS-3.31仿真环境，为后续的网络协议和拓扑实验做好准备。