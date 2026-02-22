# 网络模拟器3教程：39：使用NS3实现路由信息协议（RIP）🔗

在本节课中，我们将学习一个名为路由信息协议（RIP）的协议。RIP属于距离向量路由协议类别。我们将通过NS3模拟，了解RIP的工作原理，特别是其三种关键机制：水平分割、毒性逆转以及无水平分割模式。

## 概述

距离向量路由意味着每个节点只将自己的路由表传输给最近的邻居。这些邻居再依次将它们的路由表传输给它们自己的邻居，以此类推，形成一个网络链。这样，网络中的所有节点都拥有不完整的信息，但整个网络作为一个整体，每个节点最终都能获得关于整个网络的完整信息。RIP就是距离向量路由协议的一个例子。

在本模拟中，我们将看到在NS3中如何实现RIP，并观察启用**水平分割**、**无水平分割**和**毒性逆转**这三种选项时，路由表如何变化，从而理解这三种机制在RIP协议中的作用。

## 核心概念解析

在深入模拟之前，我们先来理解RIP协议中涉及的三个核心概念。

![](img/044848cb6d6e5b88253944a87a9e5e75_1.png)

### 无水平分割的问题

考虑一个由三个路由器R1、R2、R3组成的简单网络，它们彼此相连。假设网络`10.0.1.0/16`连接在R3上。

*   **初始状态**：R3将关于`10.0.1.0/16`的路由更新发送给R2，R2再发送给R1。
*   **链路故障**：假设R2与R3之间的链路发生故障。
*   **问题发生**：在无水平分割模式下，R1仍然会向R2发送路由更新（声称可以通过R1到达`10.0.1.0/16`），而R2在收到这个错误信息后，又会更新自己的路由表并可能将信息发回给R1（或R3，如果链路恢复），这可能导致R1和R2之间形成**路由环路**，数据包在两个路由器之间无限循环，无法到达真正目的地。

**核心问题**：无水平分割可能导致网络在发生故障后产生无限循环。

### 水平分割机制

水平分割是一种简单的改进机制。其规则是：**从一个接口学到的路由，不会再从该接口通告出去**。

沿用上面的例子：
当R2与R3之间的链路失效后，R1从R2（通过接口A）学到了通往`10.0.1.0/16`的路由。如果启用了水平分割，那么R1**不会**通过接口A（即朝向R2的方向）再次通告这条路由。这样就切断了错误信息反向传播的路径，从而**避免了R1和R2之间形成环路**。

### 毒性逆转机制

毒性逆转是水平分割的增强版，也称为“带毒性逆转的水平分割”。其规则是：**从一个接口学到的路由，仍然会从该接口通告出去，但会将其度量（成本）设置为无穷大（在RIP中为16）**。

再次使用上面的例子：
当R2与R3的链路失效后，R1会通过接口A向R2发送路由更新，告知通往`10.0.1.0/16`的路由，但**度量值设为16**。R2收到这个“毒化”的路由后，会立刻明白通过R1到达`10.0.1.0/16`是不可行的（成本无穷大），从而迅速将该路由标记为失效。这不仅能防止环路，还能**加速整个网络的收敛速度**，因为错误信息被明确标记并传播。

**RIP中的无穷大**：在RIP协议中，跳数16被定义为无穷大，表示网络不可达。任何度量值达到或超过16的路由都会被丢弃。

## NS3模拟实例分析

现在，我们通过一个NS3模拟示例来具体观察这些机制。考虑以下网络拓扑：

```
SRC (源) --(1)-- A --(1)-- B --(1)-- DST (目的)
                  |         |         |
                  |(1)      |(1)      |(1)
                  C ----(10)--- D
```
*(注：括号内数字为链路成本/跳数)*

*   **最优路径**：初始时，SRC到DST的最短路径是 `SRC -> A -> B -> DST`，总成本为 1+1+1 = **3**。
*   **高成本链路**：C和D之间的链路成本为10。
*   **模拟事件**：
    1.  模拟运行约3秒后，网络拓扑建立。
    2.  在40秒时，手动断开路由器B和D之间的链路（成本1的链路）。
    3.  链路断开导致原路径失效。RIP协议需要时间重新收敛。
    4.  大约在44秒（故障后4秒），网络通过发现新路径 `SRC -> A -> C -> D -> DST` 恢复连通，但新路径成本为 1+1+10+1 = **13**。
*   **观察点**：我们将通过打印路由表，查看在30秒、60秒、90秒时，各路由器（A, B, C, D）到达目标网络`10.0.6.0`（DST）的路径和成本变化，特别是故障发生（40秒）前后。

### NS3代码关键部分解析

以下是实现上述模拟逻辑的NS3代码关键步骤的说明：

1.  **启用日志**：为了观察协议内部运作，需要启用相关组件的日志。
    ```cpp
    LogComponentEnable("Rip", LOG_LEVEL_INFO);
    LogComponentEnable("RipNg", LOG_LEVEL_INFO);
    LogComponentEnable("Ipv4Interface", LOG_LEVEL_INFO);
    // ... 其他组件（Icmpv4L4Protocol, Ipv4L3Protocol, ArpCache, Ping）的日志
    ```

![](img/044848cb6d6e5b88253944a87a9e5e75_3.png)

2.  **设置水平分割策略**：通过命令行参数或直接赋值，选择要测试的RIP变体。
    ```cpp
    // 定义策略枚举
    std::string splitHorizon = "PoisonReverse"; // 可选项："NoSplitHorizon", "SplitHorizon", "PoisonReverse"
    // 在代码中根据选择设置RIP助手的属性
    if (splitHorizon == "NoSplitHorizon") {
        rip.SetAttribute("SplitHorizon", StringValue("NoSplitHorizon"));
    } else if (splitHorizon == "SplitHorizon") {
        rip.SetAttribute("SplitHorizon", StringValue("SplitHorizon"));
    } else { // PoisonReverse
        rip.SetAttribute("SplitHorizon", StringValue("PoisonReverse"));
    }
    ```

![](img/044848cb6d6e5b88253944a87a9e5e75_5.png)

![](img/044848cb6d6e5b88253944a87a9e5e75_7.png)

3.  **创建拓扑与安装协议**：创建节点（SRC, DST, A, B, C, D），使用CSMA通道连接它们，并在路由器节点（A, B, C, D）上安装RIP协议栈。
    ```cpp
    // 创建节点
    NodeContainer routers;
    routers.Create(4); // A, B, C, D
    NodeContainer nodes;
    nodes.Create(2); // SRC, DST
    // 连接节点（此处省略具体的PointToPoint或CSMA助手连接代码）
    // ...
    // 安装Internet协议栈和RIP路由
    InternetStackHelper internet;
    RipHelper ripHelper;
    internet.SetRoutingHelper(ripHelper); // 在路由器上使用RIP
    internet.Install(routers);
    internet.Install(nodes); // 在终端节点上安装基础协议栈（通常用静态路由）
    ```

![](img/044848cb6d6e5b88253944a87a9e5e75_9.png)

4.  **配置链路成本与故障**：设置C-D链路的成本为10，并安排在40秒时触发B-D链路断开函数。
    ```cpp
    // 设置C-D链路接口的度量值（成本）为10
    Ptr<Ipv4> ipv4C = routers.Get(2)->GetObject<Ipv4>(); // 节点C
    ipv4C->GetInterfaceMetric(3, 10); // 假设接口3连接D
    Ptr<Ipv4> ipv4D = routers.Get(3)->GetObject<Ipv4>(); // 节点D
    ipv4D->GetInterfaceMetric(1, 10); // 假设接口1连接C

    // 安排在40秒时断开B-D链路
    Simulator::Schedule(Seconds(40.0), &TearDownLink, routerB, routerD, 3, 2);
    // TearDownLink 函数会将指定节点接口设置为down状态
    ```

5.  **生成流量与跟踪**：在SRC和DST之间建立Ping应用以生成流量，并启用数据包捕获（如Wireshark格式）以便后期分析。
    ```cpp
    // 创建Ping应用
    PingHelper ping(interfacesDst.GetAddress(1)); // Ping DST的地址
    ping.SetAttribute("Verbose", BooleanValue(true));
    ApplicationContainer p = ping.Install(nodes.Get(0)); // 安装在SRC上
    p.Start(Seconds(1.0));
    p.Stop(Seconds(110.0));

    // 启用PCAP捕获
    csma.EnablePcapAll("rip-simple-network");
    ```

### 模拟运行与结果分析

运行模拟后，我们可以从以下几个方面观察结果：

![](img/044848cb6d6e5b88253944a87a9e5e75_11.png)

1.  **控制台输出（Ping结果）**：由于在40-44秒左右发生链路故障和收敛，Ping数据包会有一定丢失。输出可能显示类似“66% packets received”的信息，证实了网络中断的存在。
2.  **路由表打印**：如果在代码中启用了`PrintRoutingTable`，可以在30秒、60秒、90秒看到路由器A、B、C、D的路由表。
    *   **30秒（故障前）**：所有路由器到`10.0.6.0`的路径成本应为3（通过B）。
    *   **60秒（故障后，收敛前/收敛中）**：路由器B和D的相关路由可能显示为**度量16（不可达）**，或者正在更新。路由器A和C的路由表可能开始显示经过C的新路径，但成本可能还不是最终值。
    *   **90秒（收敛后）**：所有路由器到`10.0.6.0`的路径应更新为经过C的新路径，总成本显示为**13**（A->C->D->DST：1 + 10 + 1？注意实际跳数：SRC-A(1), A-C(1), C-D(10), D-DST(1) = 13）。在A的路由表中，下一跳可能是C（`10.0.2.2`），度量值为12（A->C->D->DST？这里需要根据具体IP分配计算）。关键点是**成本从3增加到了12或13**。
3.  **Wireshark分析**：打开生成的`.pcap`文件（例如`rip-simple-network-3-2.pcap`对应路由器C的第二个接口），观察RIP更新报文和数据报文（如ICMP Ping）。
    *   在40秒附近，可以看到RIP更新报文频繁交换（触发路由重新计算）。
    *   在流量图上，可以看到在故障期间（约40-44秒），数据包流出现中断或延迟，之后流量恢复，但可能因为路径变长，端到端延迟有细微增加。

通过对比使用`NoSplitHorizon`、`SplitHorizon`和`PoisonReverse`三种模式下的收敛时间和路由表变化，可以直观地理解毒性逆转如何帮助网络更快地摆脱环路状态并稳定下来。

## 总结

![](img/044848cb6d6e5b88253944a87a9e5e75_13.png)

本节课中，我们一起学习了距离向量路由协议的代表——RIP协议。我们首先从理论上分析了RIP协议中**无水平分割**可能引发的路由环路问题，进而介绍了**水平分割**及其增强版**毒性逆转**两种防环机制的工作原理。接着，我们通过一个具体的NS3模拟示例，演示了如何构建一个使用RIP的网络拓扑，如何设置链路成本、触发链路故障，并观察了网络在故障前后的收敛过程。通过分析代码配置、控制台输出的路由表变化以及Wireshark捕获的数据包，我们验证了RIP协议的行为以及不同防环机制的效果。本教程旨在帮助初学者理解RIP的基本概念及其在NS3中的实现方法。