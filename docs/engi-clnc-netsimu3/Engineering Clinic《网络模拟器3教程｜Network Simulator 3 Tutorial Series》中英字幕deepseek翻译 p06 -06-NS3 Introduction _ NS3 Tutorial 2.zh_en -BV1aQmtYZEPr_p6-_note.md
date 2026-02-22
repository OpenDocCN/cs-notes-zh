# 网络模拟器3教程：01：NS3 简介与安装

![](img/940df16f7acfbadc396567b6fb70622d_0.png)

在本节课中，我们将学习网络模拟器3（NS3）的基本概念、它与NS2的主要区别，以及如何在Linux系统上完成NS3的安装与配置。

---

## 概述

NS3是一个开源的离散事件网络模拟器，主要用于研究和教育。与NS2不同，NS3主要基于C++语言，并提供了可选的Python绑定，使其在架构和易用性上更具优势。

## NS3 与 NS2 的主要区别

上一节我们了解了NS3的基本定位，本节中我们来看看它与前代NS2的核心区别。

以下是NS3与NS2的关键差异点：

*   **编程语言**：NS2需要同时掌握**Tcl**和**C++**两种语言。而NS3主要使用**C++**，并可选**Python**进行开发。
*   **架构与维护**：NS2的架构较为陈旧，自2011年后基本停止重大更新。NS3采用模块化库设计，社区活跃，大约每三个月发布一次更新。
*   **跟踪与分析**：NS2生成专用的跟踪文件，需用特定工具分析。NS3生成标准的**pcap**（数据包捕获）文件，可使用**Wireshark**等通用行业工具进行分析。
*   **功能特性**：NS3支持**直接代码执行**，意味着在模拟器中编写的代码逻辑可以部署到真实硬件上运行，这是NS2不具备的功能。
*   **可视化工具**：NS2使用自带的NAM动画器。NS3支持多种外部工具，如**NetAnim**、**PyViz**等，并可与更多第三方数据分析和可视化工具集成。

## NS3 的核心抽象概念

了解版本差异后，我们需要掌握NS3模拟中的五个基本抽象概念，它们是构建任何模拟场景的基石。

以下是NS3的五个核心抽象：

1.  **节点**：代表网络设备，如计算机、路由器或交换机。
2.  **应用**：运行在节点上的软件，用于生成或消费网络流量。
3.  **信道**：节点之间进行通信的媒介，如电缆或无线链路。
4.  **网络设备**：安装在节点上，使节点能够通过信道进行通信的硬件抽象，如网卡。
5.  **拓扑助手**：用于简化复杂网络拓扑配置的辅助类。

## NS3 安装指南

现在，我们开始进行NS3的安装。以下步骤基于Ubuntu系统，这是运行NS3的推荐环境。

### 步骤一：更新系统包

首先，打开终端并更新现有的软件包列表。

```bash
sudo apt-get update
```

### 步骤二：安装必备工具和依赖库

NS3的运行和编译需要一系列开发库和工具。以下是需要安装的软件包列表。

```bash
sudo apt-get install gcc g++ python python3 python3-dev pkg-config sqlite3 cmake build-essential autoconf automake libxml2-dev libgtk-3-dev libgtk2.0-dev vtun lxc wireshark python-pygccxml python-pygraphviz python-kiwi python-gnome2 ipython libc6-dev-i386
```

**注意**：`libc6-dev-i386`（32位库）在某些64位系统上可能不需要，如果安装失败可以忽略。

### 步骤三：下载并解压NS3

访问NS3官网下载稳定版本（例如ns-3.24.1）。将下载的压缩包保存到主目录，然后进行解压。

```bash
tar xjvf ns-allinone-3.24.1.tar.bz2
```

解压后，进入生成的目录。

```bash
cd ns-allinone-3.24.1
```

### 步骤四：构建NS3

使用`waf`构建系统来配置和编译NS3。建议启用示例和测试。

```bash
./waf configure --enable-examples --enable-tests
./waf build
```

这个过程可能需要10到30分钟。完成后，终端会显示哪些模块已成功构建。

### 步骤五：运行测试示例

构建完成后，可以运行一个简单的示例程序来验证安装是否成功。

```bash
./waf --run hello-simulator
```

如果终端输出“Hello Simulator”，则表明NS3已安装成功。

### 步骤六：运行更多示例

NS3自带大量示例程序，位于`examples/`目录下。要运行它们，需要将对应的`.cc`文件复制到`scratch/`目录，然后使用`waf`执行。

例如，运行一个名为`first.cc`的示例：

```bash
cp examples/tutorial/first.cc scratch/
./waf --run scratch/first
```

对于Python脚本，使用`--pyrun`参数：

```bash
./waf --pyrun scratch/my_script.py
```

## 总结

![](img/940df16f7acfbadc396567b6fb70622d_2.png)

本节课中我们一起学习了网络模拟器3的基础知识。我们明确了NS3作为现代网络研究工具的优势，特别是其基于C++的简洁架构和对行业标准工具（如Wireshark）的良好支持。我们详细介绍了安装NS3所需的步骤，从系统准备、依赖安装到最终的构建与测试。现在，你已经拥有了一个可以运行的NS3环境，为后续深入学习网络协议模拟和性能分析打下了基础。