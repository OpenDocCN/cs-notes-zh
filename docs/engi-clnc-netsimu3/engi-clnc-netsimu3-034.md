# 34：在Ubuntu 22.04中安装NS3 3.36.1 🖥️

## 概述

在本节课中，我们将学习如何在Ubuntu 22.04操作系统上安装网络模拟器NS3的最新版本3.36.1。这个新版本引入了一个重要的变化：它移除了旧的Waf构建系统，转而使用CMake系统。因此，编译和运行脚本的命令与旧版本有所不同。本教程将提供完整的安装步骤，确保初学者能够顺利完成安装。

## 安装步骤

### 第一步：更新系统包管理器

首先，我们需要更新系统的包管理器，以确保能够获取到最新的软件包列表。这是安装任何新软件前的标准步骤。

![](img/b2aaf21becb30ea1ba07adf133f35068_1.png)

![](img/b2aaf21becb30ea1ba07adf133f35068_2.png)

请在终端中执行以下命令：
```bash
sudo apt update
```

### 第二步：安装必要的依赖包

接下来，我们需要安装NS3运行和编译所需的所有依赖软件包。以下命令将安装一个完整的软件包集合，安装完成后，您通常不需要再安装其他额外的软件。

以下是需要安装的软件包列表：
*   `g++`
*   `gcc`
*   `python3`
*   `python3-dev`
*   `pkg-config`
*   `sqlite3`
*   `cmake`
*   `ninja-build`
*   `git`
*   `qtbase5-dev`
*   `qtchooser`
*   `qt5-qmake`
*   `qtbase5-dev-tools`
*   `mercurial`

您可以使用以下命令一次性安装它们：
```bash
sudo apt install g++ gcc python3 python3-dev pkg-config sqlite3 cmake ninja-build git qtbase5-dev qtchooser qt5-qmake qtbase5-dev-tools mercurial
```

### 第三步：下载并解压NS3

所有依赖安装完成后，我们需要从NS3的官方网站下载NS3 3.36.1的源代码压缩包。请注意，网站上也有旧版本，但旧版本可能仍在使用旧的Waf系统。如果您想使用新的CMake系统，请确保下载3.36.1或更高版本。

![](img/b2aaf21becb30ea1ba07adf133f35068_4.png)

下载完成后，建议将压缩包解压到您的用户主目录。例如，如果您的用户名是`user`，主目录路径通常是`/home/user`。

您可以通过图形界面右键点击文件并选择“解压到...”来完成，也可以使用命令行。以下是解压命令：
```bash
tar -jxvf ns-allinone-3.36.1.tar.bz2
```
这个命令会将文件解压到当前目录下的`ns-allinone-3.36.1`文件夹中。

![](img/b2aaf21becb30ea1ba07adf133f35068_6.png)

### 第四步：配置与编译NS3

现在，进入解压后生成的NS3主目录，开始配置和编译过程。

首先，使用`cd`命令进入目录：
```bash
cd ns-allinone-3.36.1/ns-3.36.1
```

然后，运行配置命令。这个命令会启用示例和测试，这对于学习和验证安装非常有用。
```bash
./ns3 configure --enable-examples --enable-tests
```

配置完成后，开始编译。这个过程可能需要一些时间，具体取决于您的硬件。在固态硬盘上可能需要10到15分钟，在虚拟机或机械硬盘上可能需要更长时间。
```bash
./ns3 build
```
> **提示**：如果在虚拟机中编译过程因内存不足而停止，您可以尝试临时增加虚拟机的内存容量，完成安装后再降低。

![](img/b2aaf21becb30ea1ba07adf133f35068_8.png)

### 第五步：测试安装是否成功

编译完成后，我们需要测试NS3是否能正常运行。新版本中，运行脚本的命令已从`./waf`改为`./ns3`。

首先，运行一个简单的测试程序来验证核心功能：
```bash
./ns3 run hello-simulator
```
如果安装成功，您将在终端看到“Hello Simulator”的输出。

上一节我们验证了核心安装，本节中我们来看看如何运行实际的网络模拟脚本。

![](img/b2aaf21becb30ea1ba07adf133f35068_10.png)

### 第六步：运行网络模拟脚本

NS3自带了许多示例脚本，位于`examples/tutorial`目录下。为了运行我们自己的脚本，通常将其复制到`scratch`目录下。

![](img/b2aaf21becb30ea1ba07adf133f35068_12.png)

例如，要运行一个名为`first.cc`的C++脚本，命令如下（注意不需要指定`.cc`扩展名）：
```bash
./ns3 run scratch/first
```

如果要运行一个Python脚本，例如`first.py`，则必须指定完整的文件名和`.py`扩展名：
```bash
./ns3 run scratch/first.py
```
运行这些命令后，您将看到相应的网络模拟输出，这表明您的NS3环境已经完全配置好，可以开始使用了。

## 总结

![](img/b2aaf21becb30ea1ba07adf133f35068_14.png)

![](img/b2aaf21becb30ea1ba07adf133f35068_15.png)

本节课中我们一起学习了在Ubuntu 22.04上完整安装NS3 3.36.1的流程。关键点包括：使用`sudo apt update`和`sudo apt install`来准备环境；从官网下载并解压源代码；使用`./ns3 configure`和`./ns3 build`命令进行配置和编译；最后，使用`./ns3 run`命令来测试安装和运行模拟脚本。请记住，从NS3 3.36.1开始，旧的`./waf`命令已被新的`./ns3`命令取代。现在，您的NS3开发环境已经就绪，可以开始探索网络模拟了。