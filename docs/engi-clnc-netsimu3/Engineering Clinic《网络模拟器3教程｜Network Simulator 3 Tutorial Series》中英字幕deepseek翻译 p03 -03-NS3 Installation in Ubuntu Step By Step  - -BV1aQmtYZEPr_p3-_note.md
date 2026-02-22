# 网络模拟器3教程：03：Ubuntu系统逐步安装指南 🖥️

在本节课中，我们将学习如何在Ubuntu 16.04操作系统上逐步安装网络模拟器3（NS3）。本教程将指导您完成从系统更新到编译运行第一个示例的全部过程。

![](img/66368da4129403fa7d1bc890022926b2_1.png)

![](img/66368da4129403fa7d1bc890022926b2_3.png)

## 概述与准备工作

首先，请确保您使用的是Ubuntu 16.04操作系统。本教程录制于2018年3月，但安装步骤对于后续版本同样具有参考价值。我们将使用两个窗口进行操作：一个用于记录命令的文本编辑器，另一个用于执行安装命令的终端。

![](img/66368da4129403fa7d1bc890022926b2_5.png)

![](img/66368da4129403fa7d1bc890022926b2_6.png)

## 第一步：更新系统包列表

安装任何软件前，更新系统包列表是一个好习惯。这能确保我们获取到最新的软件源信息。

![](img/66368da4129403fa7d1bc890022926b2_8.png)

以下是更新命令：
```bash
sudo apt update
```
执行此命令后，系统会检查可用的更新。如果所有包都已是最新，则会显示相应提示。

## 第二步：升级已安装的包

![](img/66368da4129403fa7d1bc890022926b2_10.png)

![](img/66368da4129403fa7d1bc890022926b2_11.png)

接下来，我们可以选择升级系统中已安装的包到最新版本。

升级命令如下：
```bash
sudo apt upgrade
```
如果您的系统近期已更新过，此步骤可能会很快完成，并提示无需升级。

![](img/66368da4129403fa7d1bc890022926b2_13.png)

## 第三步：安装NS3所需的依赖库

![](img/66368da4129403fa7d1bc890022926b2_15.png)

NS3的运行和编译依赖于大量的开发库。在安装NS3本身之前，必须先安装这些依赖项，以避免后续出现错误或警告。

以下是需要安装的依赖包长命令：
```bash
sudo apt install gcc g++ python python-dev mercurial bzr gdb valgrind gsl-bin libgsl0-dev libgsl0ldbl flex bison tcpdump sqlite sqlite3 libsqlite3-dev libxml2 libxml2-dev libgtk2.0-0 libgtk2.0-dev vtun lxc uncrustify doxygen graphviz imagemagick texlive texlive-extra-utils texlive-latex-extra texlive-font-utils texlive-lang-portuguese texlive-latex-recommended python-sphinx dia python-pygraphviz python-kiwi python-pygoocanvas libgoocanvas-dev python-pygccxml
```
这个命令将安装包括C/C++编译器、Python开发环境、构建工具（如CMake、Mercurial）、图形库（如GTK、QT4）以及各种Python库在内的大量软件包，总计约223MB。安装过程中，如果遇到关于Wireshark权限的警告，选择允许普通用户运行即可。

![](img/66368da4129403fa7d1bc890022926b2_17.png)

## 第四步：下载并解压NS3源码

假设您已将NS3的源码压缩包（例如 `ns-allinone-3.27.tar.bz2`）下载到主目录（`~/`）。您可以从官方网站 `nsnam.org` 获取。

首先，进入您的主目录：
```bash
cd $HOME
```
然后，使用 `tar` 命令解压源码包。`-j` 选项用于处理bz2压缩，`-x` 表示解压，`-v` 显示详细过程，`-f` 指定文件名。

![](img/66368da4129403fa7d1bc890022926b2_19.png)

![](img/66368da4129403fa7d1bc890022926b2_21.png)

解压命令如下：
```bash
tar -jxvf ns-allinone-3.27.tar.bz2
```
解压完成后，当前目录下会生成一个名为 `ns-allinone-3.27` 的文件夹。

## 第五步：编译构建NS3

解压后，需要进入该目录并开始编译构建NS3库。NS3支持使用C++或Python进行开发，您可以根据熟悉程度选择。

![](img/66368da4129403fa7d1bc890022926b2_23.png)

![](img/66368da4129403fa7d1bc890022926b2_24.png)

![](img/66368da4129403fa7d1bc890022926b2_26.png)

进入解压后的目录：
```bash
cd ns-allinone-3.27/ns-3.27
```
使用提供的Python构建脚本进行配置和编译。`--enable-examples` 和 `--enable-tests` 选项可以一并编译示例和测试程序。

![](img/66368da4129403fa7d1bc890022926b2_28.png)

构建命令如下：
```bash
./build.py --enable-examples --enable-tests
```
执行此命令将开始编译NS3的所有模块。这是一个耗时过程，在普通机器上可能需要15到30分钟，在虚拟机上可能更久。请耐心等待。屏幕上会显示正在构建的包（总共约70个）。

![](img/66368da4129403fa7d1bc890022926b2_30.png)

![](img/66368da4129403fa7d1bc890022926b2_31.png)

![](img/66368da4129403fa7d1bc890022926b2_32.png)

## 第六步：验证安装与运行示例

![](img/66368da4129403fa7d1bc890022926b2_34.png)

编译成功后，会列出所有已构建和未构建的模块（如`openflow`可能需要单独安装）。接下来，我们通过运行示例程序来验证安装是否成功。

![](img/66368da4129403fa7d1bc890022926b2_36.png)

NS3的应用程序需要放在 `scratch` 目录下才能被执行。首先，我们运行一个内置的简单测试：

![](img/66368da4129403fa7d1bc890022926b2_38.png)

![](img/66368da4129403fa7d1bc890022926b2_40.png)

```bash
./waf --run hello-simulator
```
如果输出“Hello Simulator”，则说明框架基本正常。

![](img/66368da4129403fa7d1bc890022926b2_42.png)

为了运行更复杂的示例，我们需要将示例文件复制到 `scratch` 目录。例如，复制第一个教程文件：

```bash
cp examples/tutorial/first.cc scratch/
cp examples/tutorial/first.py scratch/
```
现在，可以运行C++版本的示例了。注意，运行C++程序时不需要指定文件扩展名。

运行C++示例命令：
```bash
./waf --run scratch/first
```
运行成功后，终端会显示两个节点（node0和node1）之间交换数据包的模拟输出。

![](img/66368da4129403fa7d1bc890022926b2_44.png)

接下来，运行Python版本的同一示例。**注意，运行Python程序时必须指定 `.py` 扩展名。**

![](img/66368da4129403fa7d1bc890022926b2_46.png)

![](img/66368da4129403fa7d1bc890022926b2_47.png)

![](img/66368da4129403fa7d1bc890022926b2_49.png)

运行Python示例命令：
```bash
./waf --pyrun scratch/first.py
```
如果命令格式错误（例如为C++程序加了扩展名，或为Python程序省略了扩展名），NS3会给出明确的错误提示，请根据提示修正命令。

![](img/66368da4129403fa7d1bc890022926b2_51.png)

![](img/66368da4129403fa7d1bc890022926b2_53.png)

## 总结

![](img/66368da4129403fa7d1bc890022926b2_55.png)

本节课中，我们一起完成了在Ubuntu系统上安装网络模拟器3（NS3）的全过程。我们首先更新并升级了系统，然后安装了所有必要的依赖库。接着，下载并解压了NS3源码，使用构建脚本完成了耗时但重要的编译步骤。最后，通过将示例文件移动到 `scratch` 目录并成功运行，验证了NS3安装的正确性。记住，NS3允许您使用C++或Python进行开发，这为不同背景的研究者提供了便利。

---
*更多详细信息和更新，请参考官方网站和社区文档。*