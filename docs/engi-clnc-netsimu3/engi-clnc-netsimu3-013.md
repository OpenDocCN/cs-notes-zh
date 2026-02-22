# 13：NS3中的流监控器（Flow Monitor）📊

在本节课中，我们将学习如何在NS3网络模拟器中使用流监控器（Flow Monitor）来监控和分析网络性能。流监控器是一个强大的工具，可以生成详细的XML报告，帮助我们计算诸如延迟、抖动、丢包率、吞吐量等多种网络性能指标。

## 概述

流监控器是NS3提供的一个组件，用于监控网络中的数据流。它可以生成一个XML文件，其中包含了每个数据流的详细统计信息。通过分析这个文件，我们可以评估网络的整体性能。

![](img/901819938fc25a39855358583152eedc_1.png)

上一节我们介绍了网络模拟的基础，本节中我们来看看如何使用流监控器来量化网络性能。

![](img/901819938fc25a39855358583152eedc_3.png)

![](img/901819938fc25a39855358583152eedc_5.png)

![](img/901819938fc25a39855358583152eedc_7.png)

## 第一步：准备示例文件

首先，我们需要将NS3自带的两个示例脚本复制到`scratch`目录下，以便进行修改和实验。

以下是需要复制的文件：
*   `examples/tutorial/third.cc`
*   `examples/routing/manet-routing-compare.cc`

你可以通过终端命令或图形界面文件管理器来完成复制操作。

## 第二步：在代码中添加流监控器

为了在模拟中使用流监控器，我们需要在源代码中包含必要的头文件并添加几行初始化代码。

![](img/901819938fc25a39855358583152eedc_9.png)

需要包含的头文件是：
```cpp
#include “ns3/flow-monitor.h”
#include “ns3/flow-monitor-helper.h”
```

![](img/901819938fc25a39855358583152eedc_11.png)

![](img/901819938fc25a39855358583152eedc_13.png)

接着，在模拟代码中（通常在调用`Simulator::Run()`之前），添加以下代码来创建和安装流监控器：

![](img/901819938fc25a39855358583152eedc_15.png)

```cpp
// 创建流监控器对象
Ptr<FlowMonitor> flowMonitor;
FlowMonitorHelper flowHelper;
flowMonitor = flowHelper.InstallAll();
```

![](img/901819938fc25a39855358583152eedc_17.png)

最后，在模拟运行结束之后（`Simulator::Run()`之后），添加代码将监控结果写入XML文件：

![](img/901819938fc25a39855358583152eedc_19.png)

![](img/901819938fc25a39855358583152eedc_21.png)

![](img/901819938fc25a39855358583152eedc_23.png)

```cpp
flowMonitor->SerializeToXmlFile(“你的文件名.xml”, true, true);
```

![](img/901819938fc25a39855358583152eedc_25.png)

例如，在`third.cc`中，我们可以将文件名设置为`third.xml`。

## 第三步：编译并运行示例

![](img/901819938fc25a39855358583152eedc_27.png)

完成代码修改后，我们需要编译并运行脚本以生成包含流监控数据的XML文件。

使用以下命令编译并运行`third.cc`示例：
```bash
./waf --run scratch/third
```

运行成功后，你会在当前目录下找到生成的XML文件（如`third.xml`）。这个文件包含了模拟过程中所有数据流的详细记录。

## 第四步：解析与分析XML文件

生成了XML文件后，我们需要解析它以获取有意义的性能指标。NS3自带了一个Python脚本`flowmon-parse-results.py`，可以帮助我们进行初步分析。

首先，找到该脚本的位置（通常在`src/flow-monitor/examples/`目录下），并将其复制到你的工作目录。然后使用以下命令解析XML文件：

![](img/901819938fc25a39855358583152eedc_29.png)

![](img/901819938fc25a39855358583152eedc_31.png)

```bash
python flowmon-parse-results.py third.xml
```

![](img/901819938fc25a39855358583152eedc_33.png)

![](img/901819938fc25a39855358583152eedc_35.png)

![](img/901819938fc25a39855358583152eedc_36.png)

![](img/901819938fc25a39855358583152eedc_38.png)

该脚本会输出每个流的统计摘要，例如平均延迟、发送/接收的比特数和包数等。

![](img/901819938fc25a39855358583152eedc_40.png)

![](img/901819938fc25a39855358583152eedc_42.png)

![](img/901819938fc25a39855358583152eedc_44.png)

## 第五步：使用Python脚本进行可视化

![](img/901819938fc25a39855358583152eedc_46.png)

为了更直观地分析性能，我们可以编写Python脚本，利用`matplotlib`库将数据绘制成图表。脚本的核心逻辑是解析XML文件，提取关键指标（如比特率、延迟、丢包数），然后将它们绘制出来。

以下是一个简化的脚本结构示例：

```python
import xml.dom.minidom
import sys
import matplotlib.pyplot as plt

![](img/901819938fc25a39855358583152eedc_48.png)

# 初始化列表来存储数据
bitrates = []
losses = []
delays = []

# 解析XML文件
DOMTree = xml.dom.minidom.parse(“third.xml”)
collection = DOMTree.documentElement

# 遍历XML中的每个“Flow”元素，提取数据并添加到列表中
flows = collection.getElementsByTagName(“Flow”)
for flow in flows:
    # 提取 txBytes, rxBytes, delaySum 等属性值
    # 计算比特率、丢包率、平均延迟
    # bitrates.append(calculated_bitrate)
    # losses.append(calculated_loss)
    # delays.append(calculated_delay)
    pass

![](img/901819938fc25a39855358583152eedc_50.png)

![](img/901819938fc25a39855358583152eedc_52.png)

![](img/901819938fc25a39855358583152eedc_54.png)

# 使用matplotlib绘制图表
fig, axs = plt.subplots(3)
axs[0].plot(bitrates, ‘b-‘)
axs[0].set_title(‘Flow Bit Rates’)
# … 设置其他子图
plt.tight_layout()
plt.savefig(‘results.pdf’)
plt.show()
```

运行此脚本将生成一个PDF文件，其中包含了比特率、丢包和延迟随数据流变化的曲线图。

![](img/901819938fc25a39855358583152eedc_56.png)

![](img/901819938fc25a39855358583152eedc_58.png)

## 第六步：分析复杂网络场景

为了观察更真实的网络性能，我们可以对更复杂的示例（如`manet-routing-compare.cc`）应用相同的流监控步骤。这个脚本模拟了移动自组织网络（MANET）中的多种路由协议，会产生更大量的数据流和更丰富的性能变化。

![](img/901819938fc25a39855358583152eedc_60.png)

按照第二、三步修改、编译并运行该示例，生成XML报告文件（例如`manet.xml`）。然后使用第四、五步的方法进行解析和可视化分析。在复杂的场景中，你可能会观察到更高的延迟变化、更多的丢包以及不同流之间比特率的显著差异。

![](img/901819938fc25a39855358583152eedc_62.png)

![](img/901819938fc25a39855358583152eedc_64.png)

![](img/901819938fc25a39855358583152eedc_66.png)

![](img/901819938fc25a39855358583152eedc_67.png)

## 总结

![](img/901819938fc25a39855358583152eedc_69.png)

![](img/901819938fc25a39855358583152eedc_71.png)

本节课中我们一起学习了NS3中流监控器（Flow Monitor）的使用方法。我们从准备示例文件开始，逐步完成了在代码中集成监控功能、运行模拟生成数据、解析XML报告，到最后使用Python进行数据可视化的全过程。流监控器是评估网络协议和拓扑性能的利器，掌握它对于进行深入的网络仿真研究至关重要。通过分析生成的图表，我们可以直观地比较不同网络配置下的性能优劣。