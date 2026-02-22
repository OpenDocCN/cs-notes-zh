# NS3教程：09：MANET路由协议比较与仿真分析

在本教程中，我们将学习如何使用网络模拟器NS3来比较四种移动自组织网络路由协议：AODV、DSDV、OLSR和DSR。我们将从理解源代码开始，逐步完成仿真运行、数据提取和结果可视化。

![](img/d481ec03e01e2fe5b3f9a4893d20b763_1.png)

## 概述

我们将使用NS3自带的示例程序 `manet-routing-compare.cc` 作为基础。本教程将指导你如何复制、编译并运行该程序，生成仿真数据，并使用Python和Gnuplot等工具分析结果，最终绘制出协议性能对比图。

![](img/d481ec03e01e2fe5b3f9a4893d20b763_3.png)

![](img/d481ec03e01e2fe5b3f9a4893d20b763_5.png)

## 准备工作

上一节我们介绍了本教程的目标和使用的工具。本节中，我们来看看运行此项目所需的具体环境和文件准备。

**步骤1：复制源代码文件**

首先，我们需要将示例文件复制到NS3的`scratch`文件夹中，这是运行自定义仿真的标准位置。

*   源文件路径：`ns-3.29/examples/routing/manet-routing-compare.cc`
*   目标路径：`ns-3.29/scratch/`

**步骤2：检查NS3版本与环境**

确保你使用的NS3版本（例如3.29）与代码兼容。本教程在Ubuntu 18.04系统上完成。

## 源代码解析

上一节我们准备好了仿真文件。本节中，我们来深入理解 `manet-routing-compare.cc` 源代码的结构和关键部分。

该程序定义了一个名为 `RoutingExperiment` 的C++类来管理整个仿真实验。

**核心类结构**

以下是 `RoutingExperiment` 类的主要成员：

```cpp
class RoutingExperiment
{
public:
    RoutingExperiment(); // 构造函数
    void Run (int nSinks, double txp, std::string CSVfileName); // 运行仿真
    void CommandSetup (int argc, char **argv); // 命令行参数设置
private:
    Ptr<Socket> SetupPacketReceive (Ipv4Address addr, Ptr<Node> node); // 设置数据包接收
    void ReceivePacket (Ptr<Socket> socket); // 接收数据包的回调函数
    void CheckThroughput (); // 计算并记录吞吐量
    uint32_t port; // 端口号
    uint32_t bytesTotal; // 接收的总字节数
    uint32_t packetsReceived; // 接收的数据包总数
    std::string m_CSVfileName; // 输出CSV文件名
    int m_nSinks; // 接收节点（Sink）的数量
    std::string m_protocolName; // 协议名称
    double m_txp; // 发射功率
    bool m_traceMobility; // 是否启用移动性追踪
};
```

**关键参数配置**

在 `Run` 函数中，程序设置了仿真的核心参数，我们可以根据需求修改：

*   `nWifi = 50`： 网络中的节点总数。
*   `totalTime = 200`： 总仿真时间（秒）。
*   `rate = “2048bps”`： 应用层数据发送速率。
*   `nodeSpeed = 20`： 节点移动速度（米/秒）。
*   `nodePause = 0`： 节点暂停时间（秒）。
*   `protocol = 2`： 路由协议选择（1:OLSR, 2:AODV, 3:DSDV, 4:DSR）。

**协议选择逻辑**

程序使用一个 `switch` 语句来根据 `protocol` 变量的值选择并安装相应的路由协议：

```cpp
switch (protocol)
{
    case 1:
        olsr.Install (); // 安装OLSR协议
        break;
    case 2:
        aodv.Install (); // 安装AODV协议
        break;
    case 3:
        dsdv.Install (); // 安装DSDV协议
        break;
    case 4:
        dsrMain.Install (dsr, adhocNodes); // 安装DSR协议
        break;
    default:
        NS_FATAL_ERROR (“No such protocol:” << protocol);
}
```

**数据记录与输出**

程序通过以下方式记录仿真数据：

1.  **CSV文件**： 记录随时间变化的吞吐量、接收包数等信息。文件名由 `m_CSVfileName` 指定。
2.  **FlowMonitor**： 一个强大的工具，能生成包含流统计信息（如延迟、丢包率）的XML文件。要使用它，需要在源代码头部添加包含语句：
    ```cpp
    #include “ns3/flow-monitor-helper.h”
    ```
3.  **Mobility Trace**： 如果启用 (`m_traceMobility=true`)，会生成记录节点移动轨迹的文件。
4.  **ASCII Trace**： 可生成详细的底层收发事件记录文件（`.tr`），用于深度分析。

## 运行仿真与数据分析

![](img/d481ec03e01e2fe5b3f9a4893d20b763_7.png)

上一节我们详细分析了源代码。本节中，我们来看看如何编译、运行仿真并处理生成的数据。

**步骤3：编译与运行仿真**

在NS3根目录（`ns-3.29`）下打开终端，执行以下命令来运行仿真：

![](img/d481ec03e01e2fe5b3f9a4893d20b763_9.png)

![](img/d481ec03e01e2fe5b3f9a4893d20b763_11.png)

```bash
./waf --run scratch/manet-routing-compare
```

仿真运行需要一些时间（约数分钟），完成后会在当前目录生成输出文件。

![](img/d481ec03e01e2fe5b3f9a4893d20b763_13.png)

![](img/d481ec03e01e2fe5b3f9a4893d20b763_15.png)

**步骤4：处理FlowMonitor XML文件**

仿真会生成一个 `.flowmon` 文件（例如 `AODV.flowmon`）。我们可以使用Python脚本解析此文件并绘制图表。

![](img/d481ec03e01e2fe5b3f9a4893d20b763_17.png)

![](img/d481ec03e01e2fe5b3f9a4893d20b763_18.png)

![](img/d481ec03e01e2fe5b3f9a4893d20b763_20.png)

以下是处理FlowMonitor数据的Python脚本核心逻辑：

```python
import xml.etree.ElementTree as ET
import matplotlib.pyplot as plt

tree = ET.parse(‘AODV.flowmon’) # 解析XML文件
root = tree.getroot()

![](img/d481ec03e01e2fe5b3f9a4893d20b763_22.png)

![](img/d481ec03e01e2fe5b3f9a4893d20b763_24.png)

flow_ids = []
bitrates = []
lost_packets = []
delays = []

![](img/d481ec03e01e2fe5b3f9a4893d20b763_26.png)

![](img/d481ec03e01e2fe5b3f9a4893d20b763_28.png)

for flow in root.findall(‘FlowStats/Flow’):
    # 提取每个流的数据
    tx_packets = float(flow.get(‘txPackets’))
    rx_packets = float(flow.get(‘rxPackets’))
    delay_sum = float(flow.get(‘delaySum’)[:-1]) # 去除’ns‘单位
    lost_packets.append(tx_packets - rx_packets)
    # … 计算比特率、延迟等 …
    bitrates.append(bitrate)
    delays.append(delay)

# 使用matplotlib绘制图表
plt.figure()
plt.subplot(311)
plt.plot(flow_ids, bitrates, ‘ro’)
plt.ylabel(‘Bitrate (bps)’)
# … 绘制其他子图，如丢包数、延迟 …
plt.savefig(‘results.png’)
```

![](img/d481ec03e01e2fe5b3f9a4893d20b763_30.png)

![](img/d481ec03e01e2fe5b3f9a4893d20b763_32.png)

运行脚本：
```bash
python flow_analysis.py AODV.flowmon
```

![](img/d481ec03e01e2fe5b3f9a4893d20b763_34.png)

![](img/d481ec03e01e2fe5b3f9a4893d20b763_36.png)

**步骤5：处理CSV文件并比较协议性能**

仿真生成的CSV文件（如 `AODV.csv`）包含时间、接收速率和接收包数。我们可以使用Gnuplot绘制曲线图。

![](img/d481ec03e01e2fe5b3f9a4893d20b763_38.png)

首先，整理CSV文件，将逗号分隔符替换为空格。然后，创建Gnuplot脚本（`plot.gnuplot`）：

![](img/d481ec03e01e2fe5b3f9a4893d20b763_40.png)

```gnuplot
set terminal png
set output “comparison.png”
set title “接收速率对比”
set xlabel “仿真时间 (秒)”
set ylabel “接收速率”
plot “AODV.csv” using 1:2 with lines title “AODV”, \
     “OLSR.csv” using 1:2 with lines title “OLSR”
```

![](img/d481ec03e01e2fe5b3f9a4893d20b763_42.png)

![](img/d481ec03e01e2fe5b3f9a4893d20b763_44.png)

运行Gnuplot脚本：
```bash
gnuplot plot.gnuplot
```

这将生成一个名为 `comparison.png` 的图片，直观显示AODV和OLSR协议在接收速率上的性能差异。

![](img/d481ec03e01e2fe5b3f9a4893d20b763_46.png)

![](img/d481ec03e01e2fe5b3f9a4893d20b763_48.png)

**步骤6：使用TraceMatric分析详细跟踪文件**

![](img/d481ec03e01e2fe5b3f9a4893d20b763_50.png)

![](img/d481ec03e01e2fe5b3f9a4893d20b763_52.png)

![](img/d481ec03e01e2fe5b3f9a4893d20b763_54.png)

如果启用了ASCII Trace，会生成 `.tr` 文件。可以使用Java工具 **TraceMatric** 来图形化分析这个包含大量底层事件的文件。

![](img/d481ec03e01e2fe5b3f9a4893d20b763_56.png)

1.  确保已安装Java。
2.  下载TraceMatric的JAR文件及其库。
3.  运行命令打开图形界面：
    ```bash
    java -jar tracematric.jar
    ```
4.  在界面中选择生成的 `.tr` 文件进行分析，可以查看各种事件的统计和时序图。

![](img/d481ec03e01e2fe5b3f9a4893d20b763_58.png)

![](img/d481ec03e01e2fe5b3f9a4893d20b763_60.png)

## 总结

![](img/d481ec03e01e2fe5b3f9a4893d20b763_62.png)

![](img/d481ec03e01e2fe5b3f9a4893d20b763_63.png)

![](img/d481ec03e01e2fe5b3f9a4893d20b763_65.png)

在本教程中，我们一起学习了如何使用NS3对MANET路由协议（AODV、DSDV、OLSR、DSR）进行性能比较仿真。我们从理解源代码结构开始，逐步完成了仿真环境的配置、程序的编译运行，以及利用Python、Gnuplot和TraceMatric等工具对仿真生成的FlowMonitor XML文件、CSV数据文件和详细跟踪文件进行多维度分析及可视化。通过修改源代码中的节点数、移动速度、协议类型等参数，你可以进一步探索不同网络场景下各协议的性能表现，为学术研究或项目开发提供数据支持。