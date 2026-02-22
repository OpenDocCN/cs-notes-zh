# 23：NS3的外部工具 🛠️

在本节课中，我们将学习网络模拟器3（NS3）所使用的一系列第三方工具。这些工具对于分析和可视化模拟结果至关重要，其中一些工具将伴随你的整个职业生涯。

![](img/37052bd0e38d838dda5f306cebce956a_1.png)

上一节我们介绍了NS3的基本架构，本节中我们来看看这些强大的辅助工具。

## Wireshark 数据包分析器

![](img/37052bd0e38d838dda5f306cebce956a_3.png)

Wireshark是一个网络数据包分析器或数据包追踪器。它可以分析各种网络数据包。如果你想设计自己的协议和自定义数据包结构，Wireshark也能进行分析。例如，它可以处理TCP、UDP、SNMP等多种协议。

![](img/37052bd0e38d838dda5f306cebce956a_5.png)

网络数据包分析器会捕获网络数据包，并尽可能详细地显示数据包信息，甚至可以达到比特级别的细节。NS3之所以包含Wireshark，是因为它能够处理一种名为“数据包捕获”的文件，通常简称为Pcap文件。

![](img/37052bd0e38d838dda5f306cebce956a_7.png)

以下是Wireshark的主要功能列表：
*   它可以创建各种统计信息。
*   它可以根据多种条件为数据包着色。
*   它可以根据多种条件搜索数据包。
*   它可以根据多种条件过滤数据包。
*   它可以导出数据。
*   它可以保存、显示和导入数据包。

Wireshark适用于Linux、Mac和Windows等所有主流操作系统。在Ubuntu Linux上，你可以使用以下命令安装：
```bash
sudo apt install wireshark
```
在Fedora上，你可以使用：
```bash
sudo dnf install wireshark
```
默认情况下，只有超级用户（root）才能访问所有网络接口。为了让普通用户也能使用Wireshark监控接口，需要进行额外配置。

---

![](img/37052bd0e38d838dda5f306cebce956a_9.png)

![](img/37052bd0e38d838dda5f306cebce956a_11.png)

## NetAnim 网络动画器

NetAnim是网络动画器的缩写。它是一个用于可视化NS3模拟过程的工具。

不建议直接通过Linux系统包管理器安装NetAnim，因为这可能与NS3生成的XML动画文件不兼容。正确的安装方法如下，每一行对应一个终端命令：
```bash
sudo apt-get update
sudo apt-get install qt4-dev-tools
```
安装完成后，在NS3的`netanim-3.10x`目录下，运行`./netanim`命令来启动动画器。

![](img/37052bd0e38d838dda5f306cebce956a_13.png)

要在源代码中启用NetAnim，需要进行以下配置。首先，在头文件部分包含：
```cpp
#include "ns3/netanim-module.h"
```
然后，在`Simulator::Run()`函数之前，添加如下代码来设置动画接口和节点位置：
```cpp
AnimationInterface anim ("animation.xml");
anim.SetConstantPosition (node, x, y);
```
这段代码会生成一个XML文件，该文件可以在NetAnim窗口中打开并播放动画。

---

## Trace-Matrix 追踪矩阵分析器

![](img/37052bd0e38d838dda5f306cebce956a_15.png)

Trace-Matrix是一个第三方追踪矩阵分析软件。你可以从`tracematrix.net`或`SourceForge`网站下载其最新版本。

在Windows系统中，可以直接双击JAR文件运行。在Linux或Mac系统中，需要在终端使用以下命令运行：
```bash
java -jar tracematrix.jar
```
该软件处理的是NS3生成的`.tr`格式的追踪文件，这种文件包含ASCII格式的追踪数据。

![](img/37052bd0e38d838dda5f306cebce956a_17.png)

要在代码中启用ASCII追踪，需要在`Simulator::Run()`函数之前添加代码。例如，为CSMA和Wi-Fi助手类启用追踪：
```cpp
AsciiTraceHelper ascii;
csma.EnableAsciiAll (ascii.CreateFileStream ("csma.tr"));
phy.EnableAsciiAll (ascii.CreateFileStream ("wifi.tr"));
```
运行模拟后，会生成`csma.tr`和`wifi.tr`两个文件，你可以用Trace-Matrix分别打开它们进行分析。

---

![](img/37052bd0e38d838dda5f306cebce956a_19.png)

## 数据包捕获 (PCAP) 与 TCPdump

数据包捕获功能可以生成PCAP文件，这些文件可以用Wireshark或TCPdump进行分析。

在代码中启用PCAP捕获的方法与ASCII追踪类似，但针对的是点对点、Wi-Fi物理层和CSMA等助手类。例如：
```cpp
pointToPoint.EnablePcapAll ("third");
phy.EnablePcapAll ("third");
csma.EnablePcapAll ("third");
```
这段代码会为每个网络接口生成独立的PCAP文件，文件名格式类似于`third-0-0.pcap`、`third-0-1.pcap`等。

![](img/37052bd0e38d838dda5f306cebce956a_21.png)

TCPdump是一个命令行网络分析工具。你可以使用如下命令分析PCAP文件：
```bash
tcpdump -tt -r filed.pcap
```
这对于希望深入理解TCP/IP协议栈的网络管理员来说非常有用。

![](img/37052bd0e38d838dda5f306cebce956a_23.png)

---

## Flow Monitor 流监控器

Flow Monitor是NS3中一个非常强大的内置工具，能够提供详尽的流级别统计数据，例如数据包丢失、丢包、传输/接收能量以及收发数据包数量等。

![](img/37052bd0e38d838dda5f306cebce956a_25.png)

要使用Flow Monitor，首先需要在源代码中包含头文件：
```cpp
#include "ns3/flow-monitor-helper.h"
```
然后，在`Simulator::Run()`函数之前安装流监控器：
```cpp
Ptr<FlowMonitor> flowMonitor;
FlowMonitorHelper flowHelper;
flowMonitor = flowHelper.InstallAll ();
```
模拟运行结束后，将统计数据写入XML文件：
```cpp
flowMonitor->SerializeToXmlFile ("flow-monitor.xml", true, true);
```
分析这个XML文件，你可以获得关于协议、端口号、数据包流等丰富信息。

---

![](img/37052bd0e38d838dda5f306cebce956a_27.png)

## PyViz 可视化工具

![](img/37052bd0e38d838dda5f306cebce956a_29.png)

PyViz是一个基于Python的可视化工具，但因其依赖包已从Ubuntu仓库移除，在较新系统中可能无法工作。它的功能与NetAnim类似，但更集成于NS3内部。

你可以通过以下两种方式之一在运行脚本时启动PyViz：
```bash
./waf --run scratch/first --vis
```
或
```bash
./waf --run scratch/first --visualizer
```
如果环境配置正确，这将打开一个图形化窗口，动态显示网络模拟过程。

---

## Gnuplot 绘图工具

Gnuplot是一个功能强大、开源且专业的绘图软件，是值得终身学习的工具。绝大多数学术期刊出版物中的图表都使用Gnuplot生成。它支持Windows、Linux和Mac系统，完全免费。

以下是一个简单的Gnuplot脚本示例，用于生成PNG格式的图表：
```gnuplot
set terminal png size 600,480
set output 'filed.png'
set title "Title of the graph"
plot "filed.dat" using 1:2 with linespoints title "Congestion"
```
这段脚本将数据文件`filed.dat`中的第一列作为X轴，第二列作为Y轴，绘制带有点的线图，并添加图例“Congestion”。你还可以在同一张图中绘制多条曲线，甚至直接绘制数学函数，例如：
```gnuplot
plot x**2 + 2*x + 1
```
Gnuplot的强大之处在于，你可以将复杂的绘图指令写在一个脚本文件中，轻松生成大量高质量、可出版的图表。

---

![](img/37052bd0e38d838dda5f306cebce956a_31.png)

![](img/37052bd0e38d838dda5f306cebce956a_33.png)

本节课中我们一起学习了NS3的多种外部和内部工具。从用于深度数据包分析的Wireshark，到用于动态可视化的NetAnim和PyViz，再到用于数据分析的Trace-Matrix、Flow Monitor和Gnuplot，这些工具共同构成了NS3强大的后处理与分析生态系统。掌握这些工具，将极大地提升你设计、运行和分析网络模拟实验的能力。