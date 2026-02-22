# 网络模拟器3教程：14：VANETs中的路由 - 第二部分 🚗

![](img/469a37569b8d54da48cf406637506b05_1.png)

![](img/469a37569b8d54da48cf406637506b05_3.png)

在本节课中，我们将学习如何分析在VANETs（车载自组织网络）路由模拟中生成的结果。我们将使用SUMO生成真实交通场景，将其转换为ns-3可用的移动性文件，运行模拟，并最终评估和可视化不同路由协议的性能指标。

![](img/469a37569b8d54da48cf406637506b05_5.png)

![](img/469a37569b8d54da48cf406637506b05_7.png)

上一节我们介绍了如何在ns-3中设置和运行VANET路由模拟。本节中，我们来看看如何生成模拟数据并对其进行分析。

## 步骤一：使用SUMO生成交通场景 🗺️

![](img/469a37569b8d54da48cf406637506b05_9.png)

![](img/469a37569b8d54da48cf406637506b05_10.png)

![](img/469a37569b8d54da48cf406637506b05_12.png)

![](img/469a37569b8d54da48cf406637506b05_14.png)

![](img/469a37569b8d54da48cf406637506b05_16.png)

![](img/469a37569b8d54da48cf406637506b05_18.png)

![](img/469a37569b8d54da48cf406637506b05_20.png)

首先，我们需要使用SUMO生成一个真实的交通移动性场景。

![](img/469a37569b8d54da48cf406637506b05_22.png)

![](img/469a37569b8d54da48cf406637506b05_23.png)

![](img/469a37569b8d54da48cf406637506b05_25.png)

以下是生成交通场景的步骤：

![](img/469a37569b8d54da48cf406637506b05_27.png)

![](img/469a37569b8d54da48cf406637506b05_29.png)

![](img/469a37569b8d54da48cf406637506b05_31.png)

![](img/469a37569b8d54da48cf406637506b05_33.png)

![](img/469a37569b8d54da48cf406637506b05_35.png)

1.  导航到SUMO的`tools`目录。
2.  运行`osmWebWizard.py`脚本以打开浏览器配置界面。
    ```bash
    python osmWebWizard.py
    ```
3.  在浏览器界面中，选择你希望模拟的地理区域。建议选择一个较小的区域以减少计算负载。
4.  配置交通参数，例如车辆类型（小汽车、卡车、公交车）和交通密度（车辆数/小时/公里）。
5.  设置模拟持续时间（例如100秒）。
6.  点击“生成场景”并下载生成的文件。

![](img/469a37569b8d54da48cf406637506b05_37.png)

![](img/469a37569b8d54da48cf406637506b05_38.png)

![](img/469a37569b8d54da48cf406637506b05_40.png)

![](img/469a37569b8d54da48cf406637506b05_42.png)

![](img/469a37569b8d54da48cf406637506b05_44.png)

![](img/469a37569b8d54da48cf406637506b05_46.png)

运行结束后，你会在`tools`目录下得到一个以日期和时间命名的文件夹，其中包含`sumo-config.sumocfg`等配置文件。你可以使用以下命令在SUMO GUI中查看生成的交通流：
```bash
sumo-gui sumo-config.sumocfg
```

![](img/469a37569b8d54da48cf406637506b05_47.png)

![](img/469a37569b8d54da48cf406637506b05_49.png)

![](img/469a37569b8d54da48cf406637506b05_51.png)

## 步骤二：将SUMO轨迹转换为ns-3移动性文件 🔄

![](img/469a37569b8d54da48cf406637506b05_53.png)

SUMO生成的轨迹需要转换为ns-3能够识别的移动性跟踪文件。

![](img/469a37569b8d54da48cf406637506b05_55.png)

![](img/469a37569b8d54da48cf406637506b05_57.png)

![](img/469a37569b8d54da48cf406637506b05_59.png)

![](img/469a37569b8d54da48cf406637506b05_61.png)

以下是转换步骤：

1.  首先，将SUMO配置转换为浮动车辆数据（FCD）跟踪文件。
    ```bash
    sumo -c osm.sumocfg --fcd-output trace.xml
    ```
    此命令会生成一个包含所有车辆移动详细信息的`trace.xml`文件。
2.  接着，使用SUMO工具`traceExporter.py`将FCD跟踪文件转换为ns-3的移动性跟踪文件（`.tcl`格式）。
    ```bash
    python traceExporter.py --fcd-input trace.xml --ns2mobility-output mobility.tcl
    ```
    请确保正确设置SUMO_HOME环境变量，以便脚本能找到所需模块。
3.  转换完成后，打开`mobility.tcl`文件，记录关键信息，例如节点总数和模拟总时间。这些信息在后续的ns-3脚本配置中至关重要。

## 步骤三：在ns-3中运行路由模拟 ⚙️

现在，我们将使用转换好的移动性文件在ns-3中运行路由比较模拟。

以下是运行模拟的步骤：

1.  将ns-3示例目录中的路由比较脚本（例如`routing-compare.cc`）复制到你的`scratch`目录。
2.  使用文本编辑器打开该脚本，修改关键参数以匹配你的场景：
    *   `totalNodes`: 设置为`mobility.tcl`中的节点总数（例如32）。
    *   `totalTime`: 设置模拟时间（例如30或100秒）。
    *   `nodeSpeed`: 设置节点速度（例如20 m/s）。
    *   `traceFile`: 指向你生成的`mobility.tcl`文件的路径。
    *   配置输出日志文件的名称。
3.  在终端中，使用不同的协议标识符多次运行该脚本，以比较多种路由协议（如OLSR、AODV、DSDV、DSR）。
    ```bash
    ./waf --run "scratch/routing-compare --protocol=1"  # OLSR
    ./waf --run "scratch/routing-compare --protocol=2"  # AODV
    ./waf --run "scratch/routing-compare --protocol=3"  # DSDV
    ./waf --run "scratch/routing-compare --protocol=4"  # DSR
    ```
4.  每次运行都会生成对应的输出文件（如`OLSR.csv`， `AODV.csv`），其中包含了各种性能指标的数据。

## 步骤四：分析性能指标与结果可视化 📊

模拟运行完成后，我们可以提取关键性能指标并进行可视化比较。

我们将关注以下几个核心指标：
*   **分组投递率 (PDR)**: 成功接收的分组数与发送分组总数之比。
*   **吞吐量 (Goodput)**: 应用层实际接收的有效数据速率。
*   **MAC/PHY层开销 (Overhead)**: 控制信息等开销所占的比例。
*   **接收速率 (Receive Rate)**: 单位时间内接收的分组数。

以下是分析步骤：

![](img/469a37569b8d54da48cf406637506b05_63.png)

![](img/469a37569b8d54da48cf406637506b05_65.png)

1.  **提取数据**：从每个协议的`.csv`输出文件中，提取你关心的指标数据（例如吞吐量和MAC开销）。
2.  **使用电子表格软件**：将提取的数据（例如OLSR、AODV、DSDV、DSR的吞吐量）粘贴到如LibreOffice Calc或Microsoft Excel中。
    *   选中数据列。
    *   插入图表（如柱状图）。
    *   为图表添加标题、X轴（协议名称）和Y轴（指标名称，如“吞吐量 (Kbps)”）。
3.  **使用Gnuplot进行高级绘图**：对于随时间变化的指标（如接收速率），使用Gnuplot可以绘制更精细的曲线图。
    *   创建一个Gnuplot脚本文件（例如`plot_rr.gp`）。
    *   在脚本中设置图形标题、坐标轴标签，并绘制多个数据文件。
        ```gnuplot
        set title \"接收速率对比\"
        set xlabel \"模拟时间 (秒)\"
        set ylabel \"接收速率 (分组/秒)\"
        plot \"OLSR.csv\" using 1:2 with linespoints title \"OLSR\", \\
             \"AODV.csv\" using 1:2 with linespoints title \"AODV\", \\
             \"DSDV.csv\" using 1:2 with linespoints title \"DSDV\", \\
             \"DSR.csv\" using 1:2 with linespoints title \"DSR\"
        ```
    *   在终端运行该脚本：`gnuplot plot_rr.gp`。
4.  **结果解读**：通过对比图表，可以直观地分析哪种协议在你的特定场景（节点数、移动性、时间）下表现更优。例如，你可能会发现DSR协议的开销最低，而AODV的吞吐量在某些时段较高。

![](img/469a37569b8d54da48cf406637506b05_67.png)

![](img/469a37569b8d54da48cf406637506b05_69.png)

## 总结 🎯

![](img/469a37569b8d54da48cf406637506b05_71.png)

![](img/469a37569b8d54da48cf406637506b05_73.png)

![](img/469a37569b8d54da48cf406637506b05_75.png)

本节课中我们一起学习了VANET路由模拟结果分析的完整流程。我们从使用SUMO生成真实交通移动性开始，将其转换为ns-3格式，然后运行了多种路由协议的对比模拟，最后提取关键性能指标并利用电子表格和Gnuplot工具进行了可视化分析。这套方法使你能够系统地评估不同网络协议在动态车载环境下的性能，为深入研究或项目开发奠定了基础。在接下来的课程中，我们将探索如何使用Flow Monitor等更强大的工具来深入分析网络流量的细节。