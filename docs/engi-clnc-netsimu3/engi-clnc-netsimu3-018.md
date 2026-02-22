# 18：GPSR协议在ns3中的安装与运行 🚗

在本节课中，我们将学习如何在网络模拟器3（ns-3）中安装和运行GPSR协议。GPSR是一种主要用于车载自组织网络的无状态路由协议。

## 概述

GPSR协议全称为**贪婪周边无状态路由协议**。它主要包含三个版本：**GPSR**、**MM-GPSR**和**P-GPSR**。本科生和研究生可以直接使用这些模块，而博士生或研究人员则可以对其进行修改。本节课将重点介绍该协议的安装过程。

## 安装准备

![](img/f4ce06ce562c8c8320926656f49fcc18_1.png)

![](img/f4ce06ce562c8c8320926656f49fcc18_3.png)

首先，我们需要确保系统满足安装ns-3的先决条件。以下是需要安装的软件包列表：

![](img/f4ce06ce562c8c8320926656f49fcc18_5.png)

![](img/f4ce06ce562c8c8320926656f49fcc18_7.png)

*   `sudo apt-get install gcc g++ python python3`
*   `sudo apt-get install gcc g++ python python3 python3-dev`
*   `sudo apt-get install mercurial python3-setuptools git`
*   `sudo apt-get install qt5-default mercurial`
*   `sudo apt-get install gir1.2-goocanvas-2.0 python-gi python-gi-cairo python-pygraphviz python3-gi python3-gi-cairo python3-pygraphviz gir1.2-gtk-3.0 ipython ipython3`
*   `sudo apt-get install openmpi-bin openmpi-common openmpi-doc libopenmpi-dev`
*   `sudo apt-get install autoconf cvs bzr unrar`
*   `sudo apt-get install gdb valgrind`
*   `sudo apt-get install uncrustify`
*   `sudo apt-get install doxygen graphviz imagemagick`
*   `sudo apt-get install texlive texlive-extra-utils texlive-latex-extra texlive-font-utils dvipng latexmk`
*   `sudo apt-get install python3-sphinx dia`
*   `sudo apt-get install gsl-bin libgsl-dev libgsl23 libgslcblas0`
*   `sudo apt-get install tcpdump`
*   `sudo apt-get install sqlite sqlite3 libsqlite3-dev`
*   `sudo apt-get install libxml2 libxml2-dev`
*   `sudo apt-get install cmake libc6-dev libc6-dev-i386 libclang-dev llvm-dev automake`
*   `sudo apt-get install python-pip`
*   `sudo pip install cxxfilt`
*   `sudo apt-get install libgtk2.0-0 libgtk2.0-dev`
*   `sudo apt-get install vtun lxc`
*   `sudo apt-get install libboost-signals-dev libboost-filesystem-dev`

你可以复制以上命令并在终端中执行，以安装所有必需的依赖项。安装过程可能需要一些时间，具体取决于你的网络速度和系统性能。

![](img/f4ce06ce562c8c8320926656f49fcc18_9.png)

## 下载并安装ns-3

完成环境准备后，接下来我们需要下载并安装特定版本的ns-3。本教程推荐使用**ns-3.23**版本。你可以使用`wget`命令下载压缩包：

![](img/f4ce06ce562c8c8320926656f49fcc18_11.png)

![](img/f4ce06ce562c8c8320926656f49fcc18_13.png)

![](img/f4ce06ce562c8c8320926656f49fcc18_14.png)

```bash
wget https://www.nsnam.org/releases/ns-allinone-3.23.tar.bz2
```

![](img/f4ce06ce562c8c8320926656f49fcc18_16.png)

![](img/f4ce06ce562c8c8320926656f49fcc18_18.png)

![](img/f4ce06ce562c8c8320926656f49fcc18_20.png)

下载完成后，使用以下命令解压文件：

![](img/f4ce06ce562c8c8320926656f49fcc18_22.png)

![](img/f4ce06ce562c8c8320926656f49fcc18_23.png)

```bash
tar xjvf ns-allinone-3.23.tar.bz2
```

![](img/f4ce06ce562c8c8320926656f49fcc18_25.png)

![](img/f4ce06ce562c8c8320926656f49fcc18_27.png)

解压后，你会得到一个名为`ns-allinone-3.23`的文件夹。进入该文件夹：

![](img/f4ce06ce562c8c8320926656f49fcc18_29.png)

```bash
cd ns-allinone-3.23/ns-3.23
```

## 下载并集成GPSR模块

现在，我们需要将GPSR协议的源代码集成到ns-3中。使用`git`命令从GitHub仓库克隆GPSR模块：

```bash
git clone https://github.com/mohittahiliani/PhD-GPSR.git
```

克隆完成后，`PhD-GPSR`文件夹内会包含`examples`、`figures`、`results`、`scripts`和`src`等子目录。我们需要将这些内容复制到ns-3的对应目录中。

以下是需要执行的文件复制操作：

![](img/f4ce06ce562c8c8320926656f49fcc18_31.png)

1.  将`src/`目录下的所有文件夹复制到`ns-3.23/src/`目录中。
2.  将`examples/`目录下的文件复制到`ns-3.23/scratch/`目录中。
3.  将`figures/`、`results/`、`matlab/`、`scripts/`等目录复制到`ns-3.23/`根目录下。

![](img/f4ce06ce562c8c8320926656f49fcc18_33.png)

你可以通过图形界面手动复制粘贴，也可以使用终端命令完成。确保所有文件都放置在了正确的位置。

![](img/f4ce06ce562c8c8320926656f49fcc18_35.png)

![](img/f4ce06ce562c8c8320926656f49fcc18_37.png)

## 编译ns-3与GPSR模块

文件复制完成后，就可以开始编译整个ns-3项目了。在`ns-3.23`目录下，运行以下配置和编译命令：

![](img/f4ce06ce562c8c8320926656f49fcc18_39.png)

```bash
./waf configure --enable-examples --enable-tests CXXFLAGS="-std=c++11"
./waf build
```

编译过程可能需要15到20分钟，具体时间取决于你的电脑性能。编译完成后，终端会显示已成功构建的模块列表，其中应包含`GPSR`、`MM-GPSR`和`P-GPSR`。

![](img/f4ce06ce562c8c8320926656f49fcc18_41.png)

![](img/f4ce06ce562c8c8320926656f49fcc18_42.png)

![](img/f4ce06ce562c8c8320926656f49fcc18_44.png)

## 运行GPSR示例

编译成功后，我们可以运行一个GPSR示例来测试安装是否成功。进入`ns-3.23`目录，执行以下命令：

```bash
./waf --run scratch/gpsr-example
```

![](img/f4ce06ce562c8c8320926656f49fcc18_46.png)

![](img/f4ce06ce562c8c8320926656f49fcc18_48.png)

该命令会启动一个模拟场景。模拟过程可能需要一段时间（例如200秒），期间终端会输出模拟进度。模拟完成后，你可以在`results/`目录下查看生成的性能数据文件，例如**分组投递率**和**平均跳数**等指标。

![](img/f4ce06ce562c8c8320926656f49fcc18_50.png)

## 总结

![](img/f4ce06ce562c8c8320926656f49fcc18_52.png)

本节课我们一起学习了如何在ns-3.23环境中安装和配置GPSR路由协议模块。我们完成了从安装依赖、下载ns-3、集成GPSR源代码到编译和运行示例的完整流程。在下一节课中，我们将深入分析GPSR协议的源代码，并学习如何绘制和分析其性能特征图。