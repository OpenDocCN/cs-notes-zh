![](img/0fbdc1feba2d29043deae9fd1f8d9e51_1.png)

# 课程 P61：TCP Tahoe 的 RTT 估计与自时钟机制 ⏱️

![](img/0fbdc1feba2d29043deae9fd1f8d9e51_3.png)

![](img/0fbdc1feba2d29043deae9fd1f8d9e51_5.png)

![](img/0fbdc1feba2d29043deae9fd1f8d9e51_7.png)

在本节课中，我们将学习 TCP Tahoe 协议中引入的两个关键机制：**往返时间估计**和**自时钟**。这些机制与拥塞窗口、慢启动等概念共同构成了 TCP 的拥塞控制基础，使得互联网能够稳定工作。

![](img/0fbdc1feba2d29043deae9fd1f8d9e51_9.png)

![](img/0fbdc1feba2d29043deae9fd1f8d9e51_11.png)

---

![](img/0fbdc1feba2d29043deae9fd1f8d9e51_13.png)

![](img/0fbdc1feba2d29043deae9fd1f8d9e51_15.png)

![](img/0fbdc1feba2d29043deae9fd1f8d9e51_17.png)

## 回顾 TCP Tahoe 的三个基本机制

![](img/0fbdc1feba2d29043deae9fd1f8d9e51_19.png)

![](img/0fbdc1feba2d29043deae9fd1f8d9e51_21.png)

上一节我们介绍了 TCP Tahoe 的三个基本机制，它们共同实现了拥塞控制。本节中，我们来看看其中两个更深入的机制：RTT 估计和自时钟。

![](img/0fbdc1feba2d29043deae9fd1f8d9e51_23.png)

![](img/0fbdc1feba2d29043deae9fd1f8d9e51_25.png)

![](img/0fbdc1feba2d29043deae9fd1f8d9e51_27.png)

---

![](img/0fbdc1feba2d29043deae9fd1f8d9e51_29.png)

![](img/0fbdc1feba2d29043deae9fd1f8d9e51_31.png)

## RTT 估计的重要性

![](img/0fbdc1feba2d29043deae9fd1f8d9e51_33.png)

![](img/0fbdc1feba2d29043deae9fd1f8d9e51_35.png)

往返时间估计对于重传和超时至关重要。如果 RTT 估计过短，会导致不必要的重传，浪费网络容量并可能错误触发慢启动。如果 RTT 估计过长，则会在数据包实际丢失后等待过久才重传，降低效率。

![](img/0fbdc1feba2d29043deae9fd1f8d9e51_37.png)

![](img/0fbdc1feba2d29043deae9fd1f8d9e51_39.png)

在分组交换网络中，RTT 是高度动态变化的，网络负载的变化也会显著影响延迟。因此，需要一个能够快速、准确估计路径延迟的算法。

![](img/0fbdc1feba2d29043deae9fd1f8d9e51_41.png)

---

![](img/0fbdc1feba2d29043deae9fd1f8d9e51_43.png)

![](img/0fbdc1feba2d29043deae9fd1f8d9e51_45.png)

## 简单的 RTT 估计算法及其问题

![](img/0fbdc1feba2d29043deae9fd1f8d9e51_47.png)

在 TCP Tahoe 之前，使用一种简单的估计算法。该算法维护一个 RTT 估计值 `r`，并通过指数加权移动平均来更新它。

![](img/0fbdc1feba2d29043deae9fd1f8d9e51_49.png)

以下是该算法的核心公式：

![](img/0fbdc1feba2d29043deae9fd1f8d9e51_51.png)

```
r = α * r + (1 - α) * m
```

![](img/0fbdc1feba2d29043deae9fd1f8d9e51_53.png)

![](img/0fbdc1feba2d29043deae9fd1f8d9e51_55.png)

其中：
*   `r` 是当前的 RTT 估计值。
*   `m` 是最近一次测量的 RTT 值。
*   `α` 是历史样本的权重因子（0 < α < 1）。α 值越高，表示越重视历史数据；α 值越低，表示越重视最新测量。

![](img/0fbdc1feba2d29043deae9fd1f8d9e51_57.png)

![](img/0fbdc1feba2d29043deae9fd1f8d9e51_59.png)

超时时间则设置为 `β * r`，通常 `β = 2`。这意味着，如果超过两倍的平均估计时间仍未收到确认，就触发超时。

![](img/0fbdc1feba2d29043deae9fd1f8d9e51_61.png)

![](img/0fbdc1feba2d29043deae9fd1f8d9e51_63.png)

然而，这种方法存在一个问题：它只考虑了 RTT 的平均值，而没有考虑其**方差**。对于 RTT 分布很集中的连接，`β=2` 过于保守，会导致不必要的等待。对于 RTT 分布很分散的连接，`β=2` 又过于激进，会导致大量不必要的重传。

![](img/0fbdc1feba2d29043deae9fd1f8d9e51_65.png)

![](img/0fbdc1feba2d29043deae9fd1f8d9e51_67.png)

---

![](img/0fbdc1feba2d29043deae9fd1f8d9e51_69.png)

![](img/0fbdc1feba2d29043deae9fd1f8d9e51_71.png)

## TCP Tahoe 的改进：引入方差估计

![](img/0fbdc1feba2d29043deae9fd1f8d9e51_73.png)

![](img/0fbdc1feba2d29043deae9fd1f8d9e51_75.png)

TCP Tahoe 通过将 RTT 的**方差**概念纳入估计，解决了上述问题。算法不仅计算 RTT 的指数加权移动平均，还计算估计误差的指数加权移动平均方差。

![](img/0fbdc1feba2d29043deae9fd1f8d9e51_77.png)

以下是改进后的估计算法步骤：

![](img/0fbdc1feba2d29043deae9fd1f8d9e51_79.png)

![](img/0fbdc1feba2d29043deae9fd1f8d9e51_81.png)

1.  **计算平均 RTT**：
    ```
    Err = M - R
    R = R + g * Err
    ```
2.  **计算平均偏差**：
    ```
    D = D + h * (|Err| - D)
    ```
3.  **设置超时时间**：
    ```
    Timeout = R + 4 * D
    ```

![](img/0fbdc1feba2d29043deae9fd1f8d9e51_83.png)

![](img/0fbdc1feba2d29043deae9fd1f8d9e51_85.png)

![](img/0fbdc1feba2d29043deae9fd1f8d9e51_87.png)

其中：
*   `R` 是估计的平均 RTT。
*   `M` 是最近一次测量的 RTT。
*   `Err` 是测量误差。
*   `D` 是平均偏差（方差的近似）。
*   `g` 和 `h` 是增益因子（通常 `g=1/8`, `h=1/4`）。
*   超时时间设置为 `R + 4 * D`。

![](img/0fbdc1feba2d29043deae9fd1f8d9e51_89.png)

这样，当 RTT 分布集中（方差 `D` 小）时，超时时间接近 `R`，可以快速响应丢包。当 RTT 分布分散（方差 `D` 大）时，超时时间会显著大于 `R`，避免因网络抖动而误判丢包。

![](img/0fbdc1feba2d29043deae9fd1f8d9e51_91.png)

![](img/0fbdc1feba2d29043deae9fd1f8d9e51_93.png)

![](img/0fbdc1feba2d29043deae9fd1f8d9e51_95.png)

---

![](img/0fbdc1feba2d29043deae9fd1f8d9e51_97.png)

![](img/0fbdc1feba2d29043deae9fd1f8d9e51_99.png)

## 自时钟机制

![](img/0fbdc1feba2d29043deae9fd1f8d9e51_101.png)

![](img/0fbdc1feba2d29043deae9fd1f8d9e51_103.png)

TCP Tahoe 的第三个重要改进是**自时钟**机制。这是其最伟大的概念贡献之一。

![](img/0fbdc1feba2d29043deae9fd1f8d9e51_105.png)

![](img/0fbdc1feba2d29043deae9fd1f8d9e51_107.png)

![](img/0fbdc1feba2d29043deae9fd1f8d9e51_109.png)

自时钟的核心思想是：**根据接收到的确认来定时发送新的数据包**。其概念模型如下：

![](img/0fbdc1feba2d29043deae9fd1f8d9e51_111.png)

![](img/0fbdc1feba2d29043deae9fd1f8d9e51_113.png)

1.  发送方有一个“大管道”，可以快速产生数据包。
2.  网络中间存在一个瓶颈链路。
3.  快速发送的数据包经过瓶颈链路时会被“拉伸”，在时间上间隔开来到达接收方。
4.  接收方每收到一个数据包，就发送一个确认。
5.  这些确认包经过瓶颈链路返回发送方时，其到达间隔反映了接收方收到数据包的间隔，即瓶颈链路允许的速率。
6.  发送方只有在收到一个确认后，才发送一个新的数据包。

![](img/0fbdc1feba2d29043deae9fd1f8d9e51_115.png)

![](img/0fbdc1feba2d29043deae9fd1f8d9e51_117.png)

![](img/0fbdc1feba2d29043deae9fd1f8d9e51_119.png)

通过这种方式，发送方发送数据包的速率会自动匹配网络瓶颈链路所能处理的速率，从而避免一次性注入大量数据包导致队列溢出和拥塞。这实现了“管道填充而不溢出”的目标。

![](img/0fbdc1feba2d29043deae9fd1f8d9e51_121.png)

![](img/0fbdc1feba2d29043deae9fd1f8d9e51_123.png)

此外，接收方应积极发送确认（例如重复确认），这为发送方提供了重要的网络状态信号（如丢包），并帮助其维持自时钟节奏。

![](img/0fbdc1feba2d29043deae9fd1f8d9e51_125.png)

![](img/0fbdc1feba2d29043deae9fd1f8d9e51_127.png)

---

![](img/0fbdc1feba2d29043deae9fd1f8d9e51_129.png)

![](img/0fbdc1feba2d29043deae9fd1f8d9e51_131.png)

## 总结与展望

![](img/0fbdc1feba2d29043deae9fd1f8d9e51_133.png)

![](img/0fbdc1feba2d29043deae9fd1f8d9e51_135.png)

![](img/0fbdc1feba2d29043deae9fd1f8d9e51_137.png)

本节课中，我们一起学习了 TCP Tahoe 协议中两个关键的增强机制：
1.  **改进的 RTT 估计**：通过引入**方差**计算，使超时设定更能适应网络抖动的实际情况，减少了不必要的重传和等待。
2.  **自时钟**：通过“收到确认再发送新包”的规则，使发送速率自动适应网络瓶颈带宽，从根源上平滑流量，避免拥塞。

![](img/0fbdc1feba2d29043deae9fd1f8d9e51_139.png)

这些机制与拥塞窗口、慢启动共同构成了 TCP Tahoe 的拥塞控制框架。Van Jacobson 在1988年发表的关于 TCP Tahoe 的论文里程碑式地解决了当时互联网的拥塞崩溃问题。

![](img/0fbdc1feba2d29043deae9fd1f8d9e51_141.png)

![](img/0fbdc1feba2d29043deae9fd1f8d9e51_143.png)

![](img/0fbdc1feba2d29043deae9fd1f8d9e51_144.png)

在接下来的课程中，我们将了解 TCP 拥塞控制的后续发展，如 TCP Reno 和 NewReno，它们引入了快速重传、快速恢复等新机制，进一步优化了性能。