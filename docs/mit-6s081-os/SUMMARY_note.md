# MIT 6.S081 操作系统工程课程笔记索引 📚

在本教程中，我们将一起浏览MIT 6.S081操作系统工程课程的全部中文及英文版笔记。这些笔记涵盖了从操作系统基础概念到高级主题的完整内容，是学习操作系统设计与实现的宝贵资源。

## 课程概述 🎯

本课程笔记集合了麻省理工学院著名的6.S081操作系统工程课程的核心内容。课程从操作系统的基本概念和实例入手，逐步深入到内存管理、进程调度、文件系统、并发控制、虚拟化等高级主题。通过学习这些笔记，你可以系统地理解现代操作系统的核心机制与设计哲学。

## 笔记列表 📝

以下是所有可用的课程笔记，按大致的学习顺序排列。

*   **P1：Lecture 1 - Introduction and Examples 中文版** - 课程介绍与实例分析。
*   **P2：Lecture 3 - OS Organization and System Calls 中文版** - 操作系统组织架构与系统调用。
*   **P3：Lecture 4 - Page Tables 中文版** - 页表机制详解。
*   **P4：Lecture 5 - RISC-V Calling Convention and Stack Frames 中文版** - RISC-V调用约定与栈帧。
*   **P5：Lecture 6 - Isolation & System Call Entry/Exit 中文版** - 隔离机制与系统调用入口/出口。
*   **P6：Lecture 7 - Q&A for Labs 中文版Beta** - 实验相关问题解答。
*   **P7：Lecture 8 - Page Faults 中文版** - 缺页异常处理。
*   **P8：Lecture 9 - Interrupts 中文版** - 中断机制。
*   **P9：Lecture 10 - Multiprocessors and Locks 中文版** - 多处理器与锁。
*   **P10：Lecture 11 - Thread Switching 中文版** - 线程切换。
*   **P11：Lecture 12 - Q&A #2 (COW lab) 英文版** - 第二次问答（写时复制实验）。
*   **P12：Lecture 13 - Sleep & Wakeup 英文版** - 睡眠与唤醒机制。
*   **P13：Lecture 14 - File Systems 英文版** - 文件系统。
*   **P14：Lecture 15 - Crash Recovery 英文版** - 崩溃恢复。
*   **P15：Lecture 16 - File System Performance and Fast Crash Recovery 英文版** - 文件系统性能与快速崩溃恢复。
*   **P16：Lecture 17 - Virtual Memory for Applications 英文版** - 应用程序的虚拟内存。
*   **P17：Lecture 18 - OS Organization 英文版** - 操作系统组织架构（进阶）。
*   **P18：Lecture 19 - Virtual Machines 英文版** - 虚拟机。
*   **P19：Lecture 20 - Kernels and High-Level-Languages (HLL) 英文版** - 内核与高级编程语言。
*   **P20：Lecture 21 - Networking 英文版** - 网络。
*   **P21：Lecture 22 - Meltdown 英文版** - Meltdown漏洞分析。
*   **P22：Lecture 23 - RCU 英文版** - 读-复制-更新机制。
*   **P23：Lecture 24 - Final Q&A lecture 英文版** - 最终问答课程。

## 如何使用本索引 🛠️

上一节我们列出了所有可用的课程笔记，本节中我们来看看如何高效地使用它们进行学习。

建议初学者按照列表顺序（P1至P23）进行学习，因为课程内容具有连贯性和递进性。每个笔记文件都对应课程的一次讲座，包含了核心概念、关键代码和设计思路。

在学习过程中，可以重点关注以下核心概念的代码或公式描述：
*   **系统调用**：用户程序通过 `ecall` 指令陷入内核。
*   **地址转换**：虚拟地址通过页表转换为物理地址，其核心是查表过程。
*   **上下文切换**：保存和恢复寄存器状态的过程，是实现多任务的基础。
*   **锁机制**：例如自旋锁的基本操作 `acquire()` 和 `release()`，用于保护临界区。
*   **文件系统结构**：理解inode、目录项和数据块的组织关系。

## 总结 📖

本节课中我们一起学习了MIT 6.S081操作系统工程课程的全部笔记索引。我们了解了课程的整体脉络，从操作系统导论开始，历经内存管理、并发控制、文件系统等核心模块，最终到达虚拟化、网络和安全等高级主题。这份索引为你提供了一个清晰的学习路径图，希望你能通过系统地学习这些材料，深入理解操作系统的精髓，并能够动手实践，构建自己的操作系统知识体系。