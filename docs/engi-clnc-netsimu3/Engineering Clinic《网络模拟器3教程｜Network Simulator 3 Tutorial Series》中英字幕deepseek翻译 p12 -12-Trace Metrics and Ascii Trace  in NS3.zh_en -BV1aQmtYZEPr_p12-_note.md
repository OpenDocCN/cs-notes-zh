# NS3教程：第12章：Trace Metrics与Ascii Trace 📊

![](img/86bbba1aa6cec0d875d005f4fe211c4a_1.png)

![](img/86bbba1aa6cec0d875d005f4fe211c4a_3.png)

![](img/86bbba1aa6cec0d875d005f4fe211c4a_5.png)

![](img/86bbba1aa6cec0d875d005f4fe211c4a_7.png)

![](img/86bbba1aa6cec0d875d005f4fe211c4a_8.png)

![](img/86bbba1aa6cec0d875d005f4fe211c4a_9.png)

![](img/86bbba1aa6cec0d875d005f4fe211c4a_10.png)

![](img/86bbba1aa6cec0d875d005f4fe211c4a_11.png)

![](img/86bbba1aa6cec0d875d005f4fe211c4a_13.png)

在本节课中，我们将学习如何在NS3中启用Ascii Trace（ASCII跟踪）功能，并使用Trace Matrix软件来分析生成的跟踪文件，从而获取网络性能指标，如吞吐量、有效吞吐量、延迟和丢包率等。

![](img/86bbba1aa6cec0d875d005f4fe211c4a_15.png)

![](img/86bbba1aa6cec0d875d005f4fe211c4a_17.png)

![](img/86bbba1aa6cec0d875d005f4fe211c4a_19.png)

![](img/86bbba1aa6cec0d875d005f4fe211c4a_21.png)

---

## 概述

上一节我们介绍了如何运行一个基本的NS3仿真。本节中，我们来看看如何启用详细的跟踪功能，并利用外部工具对仿真数据进行可视化分析。我们将重点学习Ascii Trace的启用方法以及Trace Matrix软件的使用。

![](img/86bbba1aa6cec0d875d005f4fe211c4a_23.png)

![](img/86bbba1aa6cec0d875d005f4fe211c4a_25.png)

## 启用Ascii Trace

![](img/86bbba1aa6cec0d875d005f4fe211c4a_27.png)

为了生成可供分析的跟踪文件，我们需要在NS3源代码中启用Ascii Trace功能。这主要涉及两个部分：节点移动性跟踪和Wi-Fi物理层信道跟踪。

![](img/86bbba1aa6cec0d875d005f4fe211c4a_29.png)

以下是需要在仿真脚本中添加的核心代码：

```cpp
// 启用移动性跟踪
AsciiTraceHelper ascii;
MobilityHelper mobility;
mobility.EnableAsciiAll (ascii.CreateFileStream ("manet-trace.mob"));

// 启用Wi-Fi物理层跟踪
WifiPhyHelper wifiPhy;
wifiPhy.EnableAsciiAll (ascii.CreateFileStream ("manet-trace.tr"));
```

**代码解释**：
1.  `AsciiTraceHelper` 和 `MobilityHelper` 类用于创建节点移动轨迹的跟踪文件（扩展名为 `.mob`）。
2.  `WifiPhyHelper` 类用于创建Wi-Fi物理层信道活动的跟踪文件（扩展名为 `.tr`）。
3.  执行仿真后，这两个文件将出现在你的工作目录中。

修改代码后，需要重新编译并运行仿真以生成跟踪文件。

## 安装Trace Matrix软件

![](img/86bbba1aa6cec0d875d005f4fe211c4a_31.png)

![](img/86bbba1aa6cec0d875d005f4fe211c4a_33.png)

![](img/86bbba1aa6cec0d875d005f4fe211c4a_35.png)

![](img/86bbba1aa6cec0d875d005f4fe211c4a_37.png)

为了分析生成的 `.tr` 跟踪文件，我们需要使用一个名为Trace Matrix的专用软件。该软件是一个Java应用程序。

![](img/86bbba1aa6cec0d875d005f4fe211c4a_39.png)

![](img/86bbba1aa6cec0d875d005f4fe211c4a_41.png)

以下是安装步骤：
1.  从官方网站下载Trace Matrix的JAR文件。
2.  确保系统已安装Java运行环境（JRE）。可以通过命令 `java -version` 检查。
3.  将下载的JAR文件解压到一个文件夹中。

## 使用Trace Matrix分析数据

Trace Matrix可以解析NS3生成的Ascii Trace文件，并计算出多种性能指标。

以下是使用Trace Matrix的基本流程：
1.  在终端中，导航到包含Trace Matrix JAR文件的目录。
2.  使用命令 `java -jar trace-matrix.jar` 启动软件。
3.  在软件界面中，打开由NS3生成的 `.tr` 文件。
4.  软件将自动分析文件，并显示摘要信息，如总数据包数、发送/接收/丢弃的数据包数量、总仿真时间等。

![](img/86bbba1aa6cec0d875d005f4fe211c4a_43.png)

## 关键性能指标

通过Trace Matrix，我们可以获取并导出以下几类核心性能指标：

![](img/86bbba1aa6cec0d875d005f4fe211c4a_45.png)

### 1. 吞吐量与有效吞吐量
*   **吞吐量**：指通过某个节点的总数据速率（包括中转数据）。计算公式可简化为：`总字节数 / 仿真时间`。
*   **有效吞吐量**：指成功送达最终目的地的应用层数据速率。它衡量的是网络对用户“有用”的吞吐量。

![](img/86bbba1aa6cec0d875d005f4fe211c4a_47.png)

在Trace Matrix的“Throughput & Goodput”选项卡中，可以查看每个节点的这两项数据，并导出为数据文件用于绘图。

### 2. Lambda因子（平均包速率）
Lambda因子表示每个节点在仿真期间的平均每秒数据包数量。它反映了节点的活跃程度。该数据可以在“Lambda”选项卡中查看和导出。

![](img/86bbba1aa6cec0d875d005f4fe211c4a_49.png)

![](img/86bbba1aa6cec0d875d005f4fe211c4a_51.png)

### 3. 延迟变化
在“Delay Variation”选项卡中，可以分析UDP流的端到端延迟变化情况。软件支持生成线性或对数坐标的图形，并能导出Gnuplot脚本，以便生成高质量的矢量图（如PDF）。

### 4. 接收速率与丢包率
软件还能提供数据包接收速率以及数据包丢弃（通常由于队列满导致）的统计信息，帮助评估网络拥塞情况。

## 数据可视化

![](img/86bbba1aa6cec0d875d005f4fe211c4a_53.png)

![](img/86bbba1aa6cec0d875d005f4fe211c4a_55.png)

导出的数据文件（如吞吐量、Lambda值）可以使用Gnuplot等工具进行可视化。

![](img/86bbba1aa6cec0d875d005f4fe211c4a_57.png)

以下是一个使用Gnuplot绘制吞吐量和有效吞吐量对比图的示例脚本：

```gnuplot
set terminal png size 1200,800
set output "throughput-goodput.png"
set title "Throughput vs Goodput per Node"
set xlabel "Node Number"
set ylabel "Rate (bytes/sec)"
plot "throughput-goodput.data" using 1:2 with linespoints title "Throughput", \
     "" using 1:3 with linespoints title "Goodput" lw 2
```

执行此脚本将生成一个PNG图像，清晰地展示每个节点的吞吐量与有效吞吐量的差异。

## 总结

本节课中我们一起学习了NS3中性能分析的重要环节。
1.  我们首先学习了如何在仿真脚本中启用**Ascii Trace**功能，以生成详细的移动性和物理层跟踪文件。
2.  接着，我们介绍了如何使用**Trace Matrix**这款Java软件来加载和分析 `.tr` 跟踪文件。
3.  最后，我们探讨了如何利用该软件提取并可视化关键的**网络性能指标**，包括吞吐量、有效吞吐量、包速率和延迟变化。

![](img/86bbba1aa6cec0d875d005f4fe211c4a_59.png)

掌握这些技能，你就能对NS3仿真结果进行定量分析，从而更科学地评估和比较不同网络协议或配置的性能。