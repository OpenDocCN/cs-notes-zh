![](img/b722cc16ca1d3c2df0cf7fd1160cee9b_0.png)

# 计算机网络课程 P31：TCP连接关闭的有限状态机详解 🔄

![](img/b722cc16ca1d3c2df0cf7fd1160cee9b_2.png)

在本节课中，我们将深入学习TCP协议如何关闭一个连接。我们将通过分析一个**有限状态机**来精确理解TCP连接关闭过程中的各种状态和转换，这比单纯的口语描述要精确得多。

![](img/b722cc16ca1d3c2df0cf7fd1160cee9b_4.png)

---

![](img/b722cc16ca1d3c2df0cf7fd1160cee9b_6.png)

![](img/b722cc16ca1d3c2df0cf7fd1160cee9b_7.png)

上一节我们介绍了TCP连接建立的过程，本节中我们来看看TCP连接是如何优雅关闭的。

![](img/b722cc16ca1d3c2df0cf7fd1160cee9b_9.png)

## 连接关闭的起点

![](img/b722cc16ca1d3c2df0cf7fd1160cee9b_11.png)

第二个问题的答案是“关闭的”。TCP连接从**关闭**状态开始。

![](img/b722cc16ca1d3c2df0cf7fd1160cee9b_13.png)

![](img/b722cc16ca1d3c2df0cf7fd1160cee9b_15.png)

当用户程序调用 `connect()` 系统调用时，连接会从**关闭**状态过渡到 **SYN_SENT** 状态。

![](img/b722cc16ca1d3c2df0cf7fd1160cee9b_17.png)

在 **SYN_SENT** 状态中，如果用户程序调用 `close()`，那么状态会沿着一条边直接回到**关闭**状态。

![](img/b722cc16ca1d3c2df0cf7fd1160cee9b_19.png)

## 已建立的连接

![](img/b722cc16ca1d3c2df0cf7fd1160cee9b_21.png)

![](img/b722cc16ca1d3c2df0cf7fd1160cee9b_23.png)

当连接成功建立后，我们的socket就处于**建立**状态，双方可以开始交换数据。

![](img/b722cc16ca1d3c2df0cf7fd1160cee9b_25.png)

## TCP关闭连接的六个状态

![](img/b722cc16ca1d3c2df0cf7fd1160cee9b_27.png)

![](img/b722cc16ca1d3c2df0cf7fd1160cee9b_29.png)

蓝色框中的六个状态描述了TCP如何关闭一个连接。

![](img/b722cc16ca1d3c2df0cf7fd1160cee9b_31.png)

谈论“关闭”连接有时需要区分，因为“关闭”在系统调用中有一个特定含义。一个连接在一方关闭它之后，可能仍然存在。

![](img/b722cc16ca1d3c2df0cf7fd1160cee9b_33.png)

TCP建立连接和关闭连接的过程存在对称性。连接建立使用 **SYN**（同步）包，而连接关闭则使用 **FIN**（结束）包。

![](img/b722cc16ca1d3c2df0cf7fd1160cee9b_35.png)

## 主动关闭与被动关闭

![](img/b722cc16ca1d3c2df0cf7fd1160cee9b_37.png)

![](img/b722cc16ca1d3c2df0cf7fd1160cee9b_39.png)

如果连接的任意一方首先调用 `close()`，它将进入 **FIN_WAIT_1** 状态。这使它向连接的另一端发送一个 **FIN** 包。

![](img/b722cc16ca1d3c2df0cf7fd1160cee9b_41.png)

发起这个操作的一方被称为**主动关闭者**。

![](img/b722cc16ca1d3c2df0cf7fd1160cee9b_43.png)

![](img/b722cc16ca1d3c2df0cf7fd1160cee9b_44.png)

另一方接收到 **FIN** 包后，会沿着状态图的蓝色边移动到 **CLOSE_WAIT** 状态。它会保持在这个状态，直到其内部的用户程序也调用 `close()`。这时，它才会发送自己的 **FIN** 包。

![](img/b722cc16ca1d3c2df0cf7fd1160cee9b_46.png)

## 连接关闭的复杂性

![](img/b722cc16ca1d3c2df0cf7fd1160cee9b_48.png)

这里情况变得复杂，因为TCP连接是**双向的**。

![](img/b722cc16ca1d3c2df0cf7fd1160cee9b_50.png)

![](img/b722cc16ca1d3c2df0cf7fd1160cee9b_52.png)

主动关闭者已经关闭了自己方向的连接，所以它不能再发送任何数据。但被动关闭者可能还有数据要发送。因此，被动关闭者可以继续发送数据，而主动关闭者接收并确认这些数据。或者，被动关闭者也可以选择关闭自己这一侧。

![](img/b722cc16ca1d3c2df0cf7fd1160cee9b_54.png)

甚至可能出现双方几乎同时决定关闭连接的情况，这样网络上就会有两个 **FIN** 包交叉传递。

![](img/b722cc16ca1d3c2df0cf7fd1160cee9b_56.png)

## 三种可能的关闭结果

![](img/b722cc16ca1d3c2df0cf7fd1160cee9b_58.png)

![](img/b722cc16ca1d3c2df0cf7fd1160cee9b_59.png)

以下是连接关闭时可能出现的三种情况：

![](img/b722cc16ca1d3c2df0cf7fd1160cee9b_61.png)

1.  **半关闭（Half-Close）**：被动关闭者确认（ACK）了主动关闭者的 **FIN**，但没有立即发送自己的 **FIN**。在这种情况下，被动关闭者处于 **CLOSE_WAIT** 状态，并可以继续发送数据。主动关闭者则进入 **FIN_WAIT_2** 状态。
2.  **顺序关闭（Orderly Close）**：被动关闭者在确认（ACK）主动关闭者的 **FIN** 后，也发送了自己的 **FIN**。这是通往 **TIME_WAIT** 状态的中间路径。
3.  **同时关闭（Simultaneous Close）**：双方几乎同时主动关闭，都向对方发送了 **FIN**。在这种情况下，双方都处于 **FIN_WAIT_1** 状态。每一方都会收到一个并非回应自己 **FIN** 的 **FIN** 包，这时双方会转换到 **CLOSING** 状态。

![](img/b722cc16ca1d3c2df0cf7fd1160cee9b_63.png)

![](img/b722cc16ca1d3c2df0cf7fd1160cee9b_65.png)

## 最终状态：TIME_WAIT 与 CLOSED

![](img/b722cc16ca1d3c2df0cf7fd1160cee9b_67.png)

当主动关闭者发送的 **FIN** 被对方确认（ACK）后，它会从 **FIN_WAIT_2** 状态切换到 **TIME_WAIT** 状态。

![](img/b722cc16ca1d3c2df0cf7fd1160cee9b_69.png)

TCP保持在 **TIME_WAIT** 状态一段时间（通常是2MSL，即两倍的最大段生命周期），以确保网络中所有属于此连接的旧数据包都已消失，之后才可以安全地切换到 **CLOSED** 状态。

![](img/b722cc16ca1d3c2df0cf7fd1160cee9b_71.png)

![](img/b722cc16ca1d3c2df0cf7fd1160cee9b_72.png)

从 **LAST_ACK** 状态到 **CLOSED** 状态的最后一条蓝色边，发生在被动关闭者发送的 **FIN** 被确认时。

![](img/b722cc16ca1d3c2df0cf7fd1160cee9b_74.png)

## 总结与意义

![](img/b722cc16ca1d3c2df0cf7fd1160cee9b_76.png)

一方面，这是一个包含大量细节的模型，有十二个状态，覆盖了许多边界情况。

![](img/b722cc16ca1d3c2df0cf7fd1160cee9b_78.png)

但我希望你能看到，这个**有限状态机**如何将之前口语化的描述变得具体和精确。试图仅基于口语描述来实现一个正确、健壮的TCP协议将非常困难。而这个状态图精确地规定了TCP在各种情况下的行为，是协议实现的可靠蓝图。

![](img/b722cc16ca1d3c2df0cf7fd1160cee9b_80.png)

![](img/b722cc16ca1d3c2df0cf7fd1160cee9b_81.png)

本节课中，我们一起学习了TCP连接关闭的完整过程，通过分析有限状态机，我们理解了**主动关闭**、**被动关闭**、**半关闭**以及**同时关闭**等不同场景下的状态流转。掌握这个状态机对于深入理解TCP协议的可靠性和复杂性至关重要。