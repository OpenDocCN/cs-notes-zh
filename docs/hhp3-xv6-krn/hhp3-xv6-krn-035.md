# XV6 操作系统内核：第35讲：文件描述符与打开的文件 📂

![](img/35cd93d6268150de11d15fb03852d126_0.png)

在本节课中，我们将学习 XV6 内核中文件描述符和打开文件的核心概念。我们将探讨文件描述符如何作为进程与文件、管道和设备之间的桥梁，并深入了解内核中用于管理这些资源的 `file` 结构体。通过分析相关代码，我们将理解文件如何被打开、共享和关闭。

## 概述

“文件”一词有多种含义，容易造成混淆。它可能指磁盘上的常规文件、目录（也是一种文件）或设备文件。在 C 语言编程中，用户态程序使用 `FILE` 结构体，并通过库函数（如 `fopen`、`fread`）操作文件。然而，这些库函数最终会调用 `open`、`read`、`write`、`close` 等系统调用，通过一个称为“文件描述符”的小整数与内核通信。

在 XV6 内核中，有一个名为 `file` 的核心数据结构，它代表了内核视角下的一个“打开的文件”。本讲将详细解析这个结构体及其管理机制。

## 核心数据结构：`struct file`

内核使用 `struct file` 来表示一个打开的文件。它定义在 `file.h` 中，主要包含以下字段：

```c
struct file {
  enum { FD_NONE, FD_PIPE, FD_INODE, FD_DEVICE } type;
  int ref; // 引用计数
  char readable; // 可读标志
  char writable; // 可写标志
  struct pipe *pipe; // 指向管道（如果类型是 FD_PIPE）
  struct inode *ip; // 指向索引节点（如果类型是 FD_INODE 或 FD_DEVICE）
  uint off; // 文件偏移量（用于常规文件/目录）
  short major; // 主设备号（用于设备文件）
};
```

*   **`type`**: 表示文件类型：未使用（`FD_NONE`）、管道（`FD_PIPE`）、索引节点文件（`FD_INODE`，指常规文件或目录）或设备（`FD_DEVICE`）。
*   **`ref`**: **引用计数**，记录有多少个指针指向这个 `file` 结构体。当 `ref` 为 0 时，该结构体空闲可用。
*   **`readable` / `writable`**: 标志位，指示此打开实例是只读、只写还是可读写。
*   **`pipe`**: 如果类型是 `FD_PIPE`，则指向对应的 `struct pipe`。
*   **`ip`**: 如果类型是 `FD_INODE` 或 `FD_DEVICE`，则指向对应的 `struct inode`（索引节点）。
*   **`off`**: 文件当前的读写偏移量（仅对 `FD_INODE` 类型有效）。
*   **`major`**: 主设备号（仅对 `FD_DEVICE` 类型有效）。

## 文件描述符与进程的关系

每个进程都有一个 `struct proc` 结构体，其中包含一个 `struct file*` 类型的数组 `ofile`：

```c
struct proc {
  // ... 其他字段
  struct file *ofile[NOFILE]; // 打开文件表
  // ... 其他字段
};
```

常量 `NOFILE` 定义了每个进程最多能同时打开的文件数量（在 XV6 中通常是 16）。这个数组的索引就是**文件描述符**（一个小的整数）。

当进程进行 `open` 系统调用时，内核会找到一个空闲的 `file` 结构体进行初始化，并将其指针放入 `ofile` 数组中第一个空闲的位置，然后返回该位置的索引作为文件描述符。随后的 `read`、`write`、`close` 等系统调用都需要使用这个文件描述符，内核通过它找到对应的 `file` 结构体。

在 Unix 传统中，文件描述符 0、1、2 通常预留给标准输入（stdin）、标准输出（stdout）和标准错误（stderr）。

## 文件结构体的共享与偏移量

`file` 结构体是内核资源，可以被多个进程共享。例如：
1.  当一个进程调用 `fork()` 创建子进程时，子进程会复制父进程的整个 `ofile` 数组。这意味着子进程获得了指向相同 `file` 结构体的指针，内核会增加这些 `file` 结构体的引用计数 (`ref++`)。
2.  两个独立的进程通过 `open` 系统调用打开同一个文件，会获得两个独立的 `file` 结构体，但它们指向同一个 `inode`。

**偏移量 (`off`)** 是每个 `file` 结构体独立的。这意味着，即使两个进程共享同一个文件（通过同一个 `inode`），如果它们拥有各自的 `file` 结构体，那么它们的读写位置 (`off`) 是独立的。但如果它们共享同一个 `file` 结构体（例如通过 `fork`），那么它们就共享同一个偏移量。

## 内核如何管理 file 结构体

内核在启动时，会静态分配一个固定大小的 `file` 结构体数组（在 XV6 中是 100 个），由一个全局变量 `ftable` 管理：

```c
struct {
  struct spinlock lock;
  struct file file[NFILE];
} ftable;
```

*   **`lock`**: 一个自旋锁，用于保护整个 `ftable`，主要是保护每个 `file` 结构体中 `ref` 字段的并发修改。
*   **`file[NFILE]`**: `file` 结构体数组。

管理这个池的核心函数在 `file.c` 中：

1.  **`filealloc()`**: 分配一个空闲的 `file` 结构体。它遍历 `ftable.file` 数组，找到第一个 `ref == 0` 的项，将其 `ref` 设为 1，并返回指针。此过程受 `ftable.lock` 保护。
2.  **`filedup(struct file *f)`**: 增加一个 `file` 结构体的引用计数 (`ref++`)。当 `fork` 复制文件描述符时调用。
3.  **`fileclose(struct file *f)`**: 关闭文件。它将引用计数减一 (`ref--`)。如果 `ref` 变为 0，则意味着这个结构体不再被任何进程引用，需要被释放。释放过程包括：
    *   如果类型是 `FD_PIPE`，则调用 `pipeclose()` 处理管道。
    *   如果类型是 `FD_INODE` 或 `FD_DEVICE`，则调用 `iput()` 减少对应 `inode` 的引用，必要时释放 `inode` 或删除磁盘文件。

## 示例：`filestat` 系统调用实现

![](img/35cd93d6268150de11d15fb03852d126_2.png)

让我们通过 `fstat` 系统调用的实现，来看如何从文件描述符获取文件信息。用户调用 `fstat(fd, &st)`。

1.  系统调用入口 `sys_fstat()` (在 `sysfile.c` 中) 被触发。
2.  它调用 `argfd(0, &fd, &f)` 来获取用户传入的文件描述符 `fd`，并找到对应的 `struct file* f`。
3.  接着调用 `filestat(f, &st)`。
4.  `filestat` 函数（在 `file.c` 中）：
    *   检查 `f->type`，如果是 `FD_INODE` 或 `FD_DEVICE`，则可以通过 `f->ip` 访问 `inode`。
    *   获取 `inode` 的锁（一个睡眠锁）。
    *   调用 `stati()` 函数，将 `inode` 中的信息（如设备号、inode 号、文件类型、链接数、大小等）填充到一个内核态的 `stat` 结构体中。
    *   释放 `inode` 锁。
    *   使用 `copyout()` 将内核态的 `stat` 结构体数据复制到用户空间指针 `&st` 所指向的位置。
5.  如果一切顺利，返回 0，否则返回 -1。

## 锁的职责

*   **`ftable.lock`**: 保护 `file.ref` 字段的原子性增减。
*   **`inode.lock`**: 保护 `inode` 本身的内容以及 `file.off` 字段。因为多个进程可能通过不同的 `file` 结构体操作同一个 `inode`，所以对偏移量的读写需要同步。
*   `file` 结构体的其他字段（如 `type`, `readable`, `writable`, `pipe`, `ip`, `major`）在分配初始化后就不会改变，因此不需要额外的锁保护。

## 总结

本节课我们一起学习了 XV6 内核中文件描述符和打开文件的核心机制。我们明确了 `struct file` 是内核内部表示一个“打开上下文”的关键数据结构，它通过引用计数 (`ref`) 管理生命周期，并通过类型字段区分管道、普通文件和设备。文件描述符是进程 `ofile` 数组的索引，是用户程序与内核 `file` 对象交互的句柄。我们还了解了 `fork` 如何共享文件描述符，以及 `fstat` 系统调用的实现路径。理解这些概念是掌握操作系统文件系统与 I/O 管理的基础。在下一讲中，我们将继续分析 `fileread` 和 `filewrite` 函数的实现。