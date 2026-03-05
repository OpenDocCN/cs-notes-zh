# 022：队列简介 🚶‍♂️➡️🚶‍♀️

![](img/627617deb2be122c0ae3b5d6df290bc3_1.png)

![](img/627617deb2be122c0ae3b5d6df290bc3_2.png)

![](img/627617deb2be122c0ae3b5d6df290bc3_3.png)

在本节课中，我们将学习一种新的数据结构——队列。我们将从抽象数据类型（ADT）的角度来理解队列，介绍其核心概念、基本操作以及典型应用场景。

![](img/627617deb2be122c0ae3b5d6df290bc3_5.png)

![](img/627617deb2be122c0ae3b5d6df290bc3_6.png)

---

![](img/627617deb2be122c0ae3b5d6df290bc3_8.png)

![](img/627617deb2be122c0ae3b5d6df290bc3_10.png)

![](img/627617deb2be122c0ae3b5d6df290bc3_11.png)

## 队列的逻辑视图

![](img/627617deb2be122c0ae3b5d6df290bc3_13.png)

![](img/627617deb2be122c0ae3b5d6df290bc3_15.png)

上一节我们介绍了栈，它是一种后进先出的结构。本节中我们来看看队列，它与栈不同，遵循“先进先出”的原则。

![](img/627617deb2be122c0ae3b5d6df290bc3_17.png)

![](img/627617deb2be122c0ae3b5d6df290bc3_19.png)

![](img/627617deb2be122c0ae3b5d6df290bc3_21.png)

队列是一种数据结构，其中**最先进入的元素将最先被取出**。我们通常称之为 **FIFO** 结构。

![](img/627617deb2be122c0ae3b5d6df290bc3_23.png)

![](img/627617deb2be122c0ae3b5d6df290bc3_25.png)

与栈的插入和删除都在同一端（栈顶）进行不同，队列的插入和删除发生在不同的两端：
*   **入队** 操作在队列的**尾部**进行。
*   **出队** 操作在队列的**头部**进行。

我们可以将队列想象成一个两端开口的管道，元素从一端进入，从另一端离开。

![](img/627617deb2be122c0ae3b5d6df290bc3_27.png)

![](img/627617deb2be122c0ae3b5d6df290bc3_28.png)

![](img/627617deb2be122c0ae3b5d6df290bc3_29.png)

![](img/627617deb2be122c0ae3b5d6df290bc3_30.png)

![](img/627617deb2be122c0ae3b5d6df290bc3_31.png)

![](img/627617deb2be122c0ae3b5d6df290bc3_32.png)

---

![](img/627617deb2be122c0ae3b5d6df290bc3_34.png)

![](img/627617deb2be122c0ae3b5d6df290bc3_35.png)

![](img/627617deb2be122c0ae3b5d6df290bc3_37.png)

## 队列的抽象数据类型（ADT）与操作

![](img/627617deb2be122c0ae3b5d6df290bc3_39.png)

![](img/627617deb2be122c0ae3b5d6df290bc3_40.png)

![](img/627617deb2be122c0ae3b5d6df290bc3_42.png)

作为抽象数据类型，我们只定义队列支持的操作，而不关心其具体实现细节。以下是队列的核心操作接口：

![](img/627617deb2be122c0ae3b5d6df290bc3_44.png)

![](img/627617deb2be122c0ae3b5d6df290bc3_45.png)

以下是队列ADT的基本操作：

![](img/627617deb2be122c0ae3b5d6df290bc3_46.png)

![](img/627617deb2be122c0ae3b5d6df290bc3_48.png)

1.  **`Enqueue(x)`**：在队列的**尾部**插入一个元素 `x`。
    *   代码示例：`void Enqueue(int x);`
2.  **`Dequeue()`**：从队列的**头部**移除一个元素，并返回该元素。
    *   代码示例：`int Dequeue();`
3.  **`Front()`**：返回队列**头部**的元素，但不移除它。
    *   代码示例：`int Front();`
4.  **`IsEmpty()`**：检查队列是否为空。
    *   代码示例：`bool IsEmpty();`

![](img/627617deb2be122c0ae3b5d6df290bc3_50.png)

![](img/627617deb2be122c0ae3b5d6df290bc3_51.png)

> **注意**：不同编程语言或库中，这些操作的名称可能不同。例如，入队操作也可能被称为 `Push`，出队操作也可能被称为 `Pop`。但 `Enqueue` 和 `Dequeue` 是队列上下文中最常用的名称。

![](img/627617deb2be122c0ae3b5d6df290bc3_53.png)

![](img/627617deb2be122c0ae3b5d6df290bc3_54.png)

![](img/627617deb2be122c0ae3b5d6df290bc3_55.png)

所有这些操作的时间复杂度都应该是 **O(1)**，即常数时间。

![](img/627617deb2be122c0ae3b5d6df290bc3_57.png)

![](img/627617deb2be122c0ae3b5d6df290bc3_58.png)

---

![](img/627617deb2be122c0ae3b5d6df290bc3_60.png)

![](img/627617deb2be122c0ae3b5d6df290bc3_61.png)

![](img/627617deb2be122c0ae3b5d6df290bc3_63.png)

![](img/627617deb2be122c0ae3b5d6df290bc3_65.png)

## 队列操作示例

让我们通过一个简单的例子来演示队列的工作流程。假设我们有一个初始为空的整数队列。

![](img/627617deb2be122c0ae3b5d6df290bc3_67.png)

![](img/627617deb2be122c0ae3b5d6df290bc3_68.png)

![](img/627617deb2be122c0ae3b5d6df290bc3_69.png)

![](img/627617deb2be122c0ae3b5d6df290bc3_70.png)

![](img/627617deb2be122c0ae3b5d6df290bc3_71.png)

以下是操作步骤：

![](img/627617deb2be122c0ae3b5d6df290bc3_73.png)

1.  调用 `Enqueue(2)`。队列状态：`[2]`（头部和尾部都指向2）。
2.  调用 `Enqueue(5)`。队列状态：`[2, 5]`（头部是2，尾部是5）。
3.  调用 `Enqueue(7)`。队列状态：`[2, 5, 7]`。
4.  调用 `Dequeue()`。它移除并返回头部元素 `2`。队列状态变为：`[5, 7]`。
5.  此时调用 `Front()`，将返回头部元素 `5`，但队列保持不变。
6.  调用 `IsEmpty()`，将返回 `false`。

![](img/627617deb2be122c0ae3b5d6df290bc3_75.png)

![](img/627617deb2be122c0ae3b5d6df290bc3_76.png)

![](img/627617deb2be122c0ae3b5d6df290bc3_77.png)

---

![](img/627617deb2be122c0ae3b5d6df290bc3_79.png)

## 队列的应用场景

![](img/627617deb2be122c0ae3b5d6df290bc3_81.png)

队列最常用于处理需要“排队”或“等待”的场景，特别是当存在一个共享资源，而该资源一次只能服务一个请求时。

![](img/627617deb2be122c0ae3b5d6df290bc3_82.png)

以下是两个典型例子：

*   **打印机队列**：网络中的多台计算机向一台共享打印机发送打印任务。打印机一次只能处理一个任务，后续的请求会被放入队列中等待，先到的请求先被打印。
*   **CPU进程调度**：计算机的中央处理器（CPU）是一个共享资源。多个需要运行的进程被放入一个就绪队列中，操作系统从队列头部取出进程为其分配CPU时间片。

![](img/627617deb2be122c0ae3b5d6df290bc3_84.png)

![](img/627617deb2be122c0ae3b5d6df290bc3_85.png)

![](img/627617deb2be122c0ae3b5d6df290bc3_86.png)

![](img/627617deb2be122c0ae3b5d6df290bc3_87.png)

队列在模拟等待、广度优先搜索（BFS）等算法中也有广泛应用，我们将在后续课程中详细讨论。

![](img/627617deb2be122c0ae3b5d6df290bc3_88.png)

![](img/627617deb2be122c0ae3b5d6df290bc3_89.png)

![](img/627617deb2be122c0ae3b5d6df290bc3_90.png)

![](img/627617deb2be122c0ae3b5d6df290bc3_91.png)

![](img/627617deb2be122c0ae3b5d6df290bc3_92.png)

![](img/627617deb2be122c0ae3b5d6df290bc3_93.png)

---

![](img/627617deb2be122c0ae3b5d6df290bc3_95.png)

## 总结

![](img/627617deb2be122c0ae3b5d6df290bc3_97.png)

本节课中我们一起学习了：
1.  队列是一种 **FIFO** 数据结构。
2.  队列的插入（`Enqueue`）在尾部进行，删除（`Dequeue`）在头部进行。
3.  我们定义了队列作为抽象数据类型的基本操作接口。
4.  队列的典型应用是管理共享资源的访问顺序。

![](img/627617deb2be122c0ae3b5d6df290bc3_99.png)

![](img/627617deb2be122c0ae3b5d6df290bc3_100.png)

![](img/627617deb2be122c0ae3b5d6df290bc3_102.png)

在下一节课中，我们将探讨如何用代码实现队列。