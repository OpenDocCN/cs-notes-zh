# NS3教程：P37-P38：NetSimluyzer - NS3的3D可视化工具 🖥️

![](img/f7bc724df1a79496e84ac21ac5738b9b_0.png)

在本节课中，我们将学习如何为NS3安装一个名为NetSimluyzer的软件。这是一个三维场景模拟器，可以可视化所有节点，并包含建筑物模型。无论是无线网络、有线网络还是混合网络，我们都可以使用它。NS3会生成一个JSON文件，NetSimluyzer可以通过这个JSON文件打开并展示模拟场景。

## 概述 📋

本教程将指导你完成在Ubuntu 22.04系统上，为NS3版本3.38安装NetSimluyzer版本1.0.7的全过程。NetSimluyzer是一个强大的软件，用于可视化NS3模拟的三维视图。我们将分步安装NS3核心、NetSimluyzer模块以及独立的NetSimluyzer可视化软件。

## 安装步骤 🛠️

### 第一步：安装NS3.38及NetSimluyzer模块

首先，我们需要安装NS3.38，并确保它能识别NetSimluyzer模块。这个过程较为复杂，因为NS3需要支持NetSimluyzer。

以下是安装所需的命令和步骤：

1.  **更新系统包列表**：
    ```bash
    sudo apt update
    ```
    在安装任何Linux软件前，建议首先更新包列表。

2.  **安装必要的依赖包**：
    复制并执行以下命令来安装NS3所需的一系列库。这个过程可能需要10到50分钟，具体取决于你的网络速度和系统性能。
    ```bash
    sudo apt install -y g++ python3 python3-dev pkg-config sqlite3 cmake python3-setuptools git qtbase5-dev qtchooser qt5-qmake qtbase5-dev-tools gir1.2-goocanvas-2.0 python3-gi python3-gi-cairo python3-pygraphviz gir1.2-gtk-3.0 ipython3 openmpi-bin openmpi-common openmpi-doc libopenmpi-dev autoconf cvs bzr unrar gdb valgrind uncrustify doxygen graphviz imagemagick texlive texlive-extra-utils texlive-latex-extra texlive-font-utils dvipng latexmk python3-sphinx dia gsl-bin libgsl-dev libgslcblas0 tcpdump sqlite sqlite3 libsqlite3-dev libxml2 libxml2-dev libgtk2.0-0 libgtk2.0-dev vtun lxc libc6-dev-i386 libclang-dev llvm-dev python3-pip libboost-all-dev libfreetype6-dev libpng-dev
    ```

3.  **解压NS3安装包**：
    假设你已经下载了`ns-allinone-3.38.tar.bz2`文件到主目录。你可以通过终端命令或图形界面右键点击并选择“提取”来解压。
    ```bash
    tar xjf ns-allinone-3.38.tar.bz2
    ```

4.  **下载并集成NetSimluyzer模块**：
    进入NS3目录下的`contrib`文件夹，下载NetSimluyzer模块。
    ```bash
    cd ns-allinone-3.38/ns-3.38/contrib
    git clone https://github.com/GabrielJaguar/NetSimulyzer.git
    ```
    下载完成后，将其重命名为`netsimulyzer`。
    ```bash
    mv NetSimulyzer netsimulyzer
    ```

5.  **配置并编译NS3**：
    返回NS3主目录，运行配置脚本，启用示例和测试。
    ```bash
    cd ../..
    ./ns-3.38/ns3 configure --enable-examples --enable-tests
    ```
    配置完成后，开始编译。这个过程可能需要10到20分钟，取决于你的电脑CPU和内存。
    ```bash
    ./ns-3.38/ns3 build
    ```

至此，NS3.38与NetSimluyzer模块的安装就完成了。接下来，我们安装独立的NetSimluyzer可视化软件。

### 第二步：安装独立的NetSimluyzer软件

现在，我们打开一个新的终端窗口，来安装用于打开JSON文件的三维可视化软件。

以下是安装步骤：

1.  **从GitHub克隆源码**：
    ```bash
    cd ~
    git clone https://github.com/GabrielJaguar/NetSimulyzer.git
    ```

2.  **创建并进入构建目录**：
    ```bash
    cd NetSimulyzer
    mkdir build
    cd build
    ```

3.  **使用CMake配置项目**：
    ```bash
    cmake -DCMAKE_BUILD_TYPE=Release ..
    ```
    注意：避免使用并行编译选项（如`-j`），它可能导致系统卡顿。

4.  **编译并安装软件**：
    ```bash
    cmake --build .
    sudo cmake --install .
    ```

现在，NetSimluyzer可视化软件也已安装成功。

## 验证安装 ✅

上一节我们完成了所有软件的安装，本节我们来验证安装是否成功。

### 验证NS3安装

![](img/f7bc724df1a79496e84ac21ac5738b9b_2.png)

运行以下命令检查NS3是否安装成功：
```bash
cd ns-allinone-3.38/ns-3.38
./ns3 run hello-simulator
```
如果命令成功执行并输出相关信息，则表明NS3安装正确。

![](img/f7bc724df1a79496e84ac21ac5738b9b_4.png)

### 验证NetSimluyzer模块

NetSimluyzer模块自带了一些示例，例如展示无人机、地面节点和智能手机的模拟。我们可以通过运行这些示例来测试。

以下是运行示例的步骤：

1.  **复制示例文件**：
    将NetSimluyzer模块中的示例源代码复制到NS3的`scratch`目录下，这是运行自定义脚本的地方。
    ```bash
    cp contrib/netsimulyzer/examples/*.cc scratch/
    ```

![](img/f7bc724df1a79496e84ac21ac5738b9b_6.png)

2.  **编译并运行一个示例**：
    我们以`mobility-buildings-example.cc`为例。在NS3主目录下执行：
    ```bash
    ./ns3 run scratch/mobility-buildings-example
    ```
    程序运行后，会在当前目录生成一个JSON文件（例如`netsimulyzer-output.json`）。这个文件包含了模拟的所有三维信息。

![](img/f7bc724df1a79496e84ac21ac5738b9b_8.png)

3.  **使用NetSimluyzer可视化**：
    打开NetSimluyzer软件，加载上一步生成的JSON文件。
    ```bash
    netsimulyzer
    ```
    在软件界面中，点击“Load”按钮，选择你的JSON文件。你将看到三维场景，其中包含编号的节点（如节点0、1、2、3）。在本示例中，节点2和3是地面无人机，在二维平面上移动。

![](img/f7bc724df1a79496e84ac21ac5738b9b_10.png)

4.  **运行模拟**：
    在NetSimluyzer界面中，你可以将默认的10毫秒模拟时间增加到50毫秒，然后点击运行。你将看到节点根据NS3模拟的逻辑在三维空间中移动。

![](img/f7bc724df1a79496e84ac21ac5738b9b_12.png)

通过这种方式，任何使用NetSimluyzer API的NS3网络模拟都可以在这个三维可视化工具中打开和观察。

## 总结 🎯

![](img/f7bc724df1a79496e84ac21ac5738b9b_12.png)

本节课我们一起学习了如何为NS3安装和配置NetSimluyzer三维可视化工具。我们完成了三个主要部分：
1.  安装了NS3.38并集成了NetSimluyzer模块。
2.  安装了独立的NetSimluyzer可视化软件。
3.  通过运行示例程序，验证了整个安装流程，并成功将NS3的模拟结果在三维视图中呈现出来。

![](img/f7bc724df1a79496e84ac21ac5738b9b_14.png)

现在，你可以利用这个强大的工具，更直观地分析和展示你的NS3网络模拟了。在下一个视频中，我们将深入讲解示例的源代码，帮助你理解如何编写自己的三维模拟场景。