![](img/a24171389b50634ece0607b1841cc3fe_1.png)

# CS110 课程介绍与文件系统基础 🖥️

在本节课中，我们将学习 CS110 课程的整体概览，并深入探讨计算机系统的基础知识，特别是 Linux 文件系统的核心概念和操作。

![](img/a24171389b50634ece0607b1841cc3fe_3.png)

## 课程概述 📚

![](img/a24171389b50634ece0607b1841cc3fe_5.png)

CS110 是计算机系统原理课程。本课程假设你已经修过 CS106A、CS106B 和 CS107 或同等课程。课程内容具有挑战性，将涵盖大型程序的构建、数据结构、C++ 类以及系统级编程概念。

课程主要围绕五个核心主题展开：
1.  **Unix 文件系统**：深入理解文件系统的构建方式、文件追踪和存储机制。
2.  **多进程**：学习如何让程序同时运行多个任务，包括进程创建（`fork`）和协调。
3.  **信号处理**：作为多进程的一部分，学习进程间通信的基本机制。
4.  **多线程**：在单个进程内实现并发任务，并处理相关的同步问题。
5.  **网络编程**：构建客户端和服务器程序，实现跨机器通信。

本课程包含八个编程作业、一次期中考试和一次期末考试。课程将大量使用 C 和 C++ 进行编程，并侧重于理解操作系统底层原理。

![](img/a24171389b50634ece0607b1841cc3fe_7.png)

## 讲师与课程安排 👨‍🏫

![](img/a24171389b50634ece0607b1841cc3fe_9.png)

![](img/a24171389b50634ece0607b1841cc3fe_11.png)

讲师 Chris Gregg 拥有电气工程背景和教学经验。课程将在周一、周三的固定时间进行讲座，周五则安排实验课。课程网站、Piazza 和 Slack 将作为主要的信息发布和交流平台。

课程评分中，作业占 40%，期中考试占 20%，期末考试占 35%，课堂参与占 5%。迟交作业会有相应的分数折减政策。

![](img/a24171389b50634ece0607b1841cc3fe_13.png)

## 深入文件系统 💾

![](img/a24171389b50634ece0607b1841cc3fe_15.png)

![](img/a24171389b50634ece0607b1841cc3fe_17.png)

上一节我们介绍了课程的整体框架，本节中我们来看看第一个核心主题：Unix/Linux 文件系统的基础操作。

![](img/a24171389b50634ece0607b1841cc3fe_19.png)

### 文件与目录操作

![](img/a24171389b50634ece0607b1841cc3fe_21.png)

在终端中，我们使用 `ls` 命令列出目录内容。使用 `ls -al` 可以查看详细信息，包括以点（`.`）开头的隐藏文件。其中，`.` 代表当前目录，`..` 代表上级目录。

### 文件权限

![](img/a24171389b50634ece0607b1841cc3fe_23.png)

`ls -l` 输出的信息中包含了文件权限，例如 `-rwxr-xr-x`。权限分为三组：
*   **所有者权限**：文件创建者的权限。
*   **组权限**：文件所属用户组的权限。
*   **其他用户权限**：系统上其他所有用户的权限。

![](img/a24171389b50634ece0607b1841cc3fe_25.png)

每组权限包含三个字符，分别代表：
*   `r`：读权限。
*   `w`：写权限。
*   `x`：执行权限。

![](img/a24171389b50634ece0607b1841cc3fe_27.png)

权限可以用八进制数字表示，每位数字对应一组权限（`r=4`, `w=2`, `x=1`）。例如，权限 `rwxr-xr-x` 可以表示为 **755**。

![](img/a24171389b50634ece0607b1841cc3fe_29.png)

![](img/a24171389b50634ece0607b1841cc3fe_31.png)

![](img/a24171389b50634ece0607b1841cc3fe_32.png)

### 系统调用：打开与创建文件

![](img/a24171389b50634ece0607b1841cc3fe_34.png)

![](img/a24171389b50634ece0607b1841cc3fe_36.png)

![](img/a24171389b50634ece0607b1841cc3fe_38.png)

![](img/a24171389b50634ece0607b1841cc3fe_40.png)

![](img/a24171389b50634ece0607b1841cc3fe_42.png)

在 C 语言中，我们可以使用系统调用来直接与操作系统交互，进行文件操作。`open` 是一个关键的系统调用，用于打开或创建文件。

![](img/a24171389b50634ece0607b1841cc3fe_44.png)

![](img/a24171389b50634ece0607b1841cc3fe_46.png)

![](img/a24171389b50634ece0607b1841cc3fe_48.png)

![](img/a24171389b50634ece0607b1841cc3fe_50.png)

![](img/a24171389b50634ece0607b1841cc3fe_52.png)

![](img/a24171389b50634ece0607b1841cc3fe_54.png)

以下是 `open` 系统调用的基本用法：
```c
#include <fcntl.h>
#include <unistd.h>

![](img/a24171389b50634ece0607b1841cc3fe_56.png)

int open(const char *pathname, int flags, mode_t mode);
```
*   `pathname`：文件路径。
*   `flags`：指定打开方式，如 `O_RDONLY`（只读）、`O_WRONLY`（只写）、`O_RDWR`（读写）、`O_CREAT`（创建文件）、`O_EXCL`（与 `O_CREAT` 共用，确保文件不存在时才创建）。
*   `mode`：指定新创建文件的权限（八进制数，如 `0644`）。

![](img/a24171389b50634ece0607b1841cc3fe_58.png)

![](img/a24171389b50634ece0607b1841cc3fe_60.png)

![](img/a24171389b50634ece0607b1841cc3fe_62.png)

![](img/a24171389b50634ece0607b1841cc3fe_64.png)

![](img/a24171389b50634ece0607b1841cc3fe_66.png)

![](img/a24171389b50634ece0607b1841cc3fe_68.png)

系统调用成功时返回一个**文件描述符**（一个小的非负整数），失败时返回 -1。

![](img/a24171389b50634ece0607b1841cc3fe_70.png)

![](img/a24171389b50634ece0607b1841cc3fe_72.png)

![](img/a24171389b50634ece0607b1841cc3fe_73.png)

![](img/a24171389b50634ece0607b1841cc3fe_75.png)

![](img/a24171389b50634ece0607b1841cc3fe_77.png)

### 权限掩码 (umask)

![](img/a24171389b50634ece0607b1841cc3fe_79.png)

![](img/a24171389b50634ece0607b1841cc3fe_81.png)

![](img/a24171389b50634ece0607b1841cc3fe_83.png)

创建文件时，实际生效的权限是 `mode` 参数与当前 `umask` 的反码进行按位与操作的结果。`umask` 指定了哪些权限位应该被**禁用**。

![](img/a24171389b50634ece0607b1841cc3fe_85.png)

![](img/a24171389b50634ece0607b1841cc3fe_86.png)

例如，如果 `umask` 是 `022`（二进制 `000010010`），而 `mode` 设置为 `0666`（二进制 `110110110`），则最终文件权限为 `0644`（`110100100`），即组和其他用户的写权限被屏蔽。

![](img/a24171389b50634ece0607b1841cc3fe_88.png)

![](img/a24171389b50634ece0607b1841cc3fe_90.png)

![](img/a24171389b50634ece0607b1841cc3fe_92.png)

![](img/a24171389b50634ece0607b1841cc3fe_94.png)

![](img/a24171389b50634ece0607b1841cc3fe_96.png)

以下程序演示了如何获取和设置 `umask`：
```c
#include <sys/stat.h>
#include <sys/types.h>
#include <stdio.h>

int main() {
    mode_t old_mask = umask(0); // 设置umask为0，并获取旧值
    printf("Old umask was: %03o\n", old_mask);
    umask(old_mask); // 恢复旧umask
    return 0;
}
```

![](img/a24171389b50634ece0607b1841cc3fe_98.png)

![](img/a24171389b50634ece0607b1841cc3fe_100.png)

![](img/a24171389b50634ece0607b1841cc3fe_101.png)

![](img/a24171389b50634ece0607b1841cc3fe_103.png)

![](img/a24171389b50634ece0607b1841cc3fe_105.png)

### 实践：文件复制程序

![](img/a24171389b50634ece0607b1841cc3fe_107.png)

![](img/a24171389b50634ece0607b1841cc3fe_109.png)

![](img/a24171389b50634ece0607b1841cc3fe_111.png)

![](img/a24171389b50634ece0607b1841cc3fe_113.png)

![](img/a24171389b50634ece0607b1841cc3fe_115.png)

![](img/a24171389b50634ece0607b1841cc3fe_117.png)

理解了文件打开和读写后，我们可以实现一个简单的文件复制程序，模拟 `cp` 命令的基本功能。

![](img/a24171389b50634ece0607b1841cc3fe_119.png)

![](img/a24171389b50634ece0607b1841cc3fe_121.png)

![](img/a24171389b50634ece0607b1841cc3fe_123.png)

![](img/a24171389b50634ece0607b1841cc3fe_125.png)

![](img/a24171389b50634ece0607b1841cc3fe_127.png)

![](img/a24171389b50634ece0607b1841cc3fe_129.png)

以下是核心逻辑的代码框架：
```c
#include <fcntl.h>
#include <unistd.h>
#include <stdio.h>
#include <errno.h>

![](img/a24171389b50634ece0607b1841cc3fe_131.png)

![](img/a24171389b50634ece0607b1841cc3fe_133.png)

#define BUFFER_SIZE 1024

![](img/a24171389b50634ece0607b1841cc3fe_135.png)

![](img/a24171389b50634ece0607b1841cc3fe_137.png)

![](img/a24171389b50634ece0607b1841cc3fe_139.png)

int main(int argc, char *argv[]) {
    if (argc != 3) {
        fprintf(stderr, "Usage: %s <source> <destination>\n", argv[0]);
        return 1;
    }

    int src_fd = open(argv[1], O_RDONLY);
    if (src_fd == -1) { perror("Error opening source file"); return 1; }

    int dest_fd = open(argv[2], O_WRONLY | O_CREAT | O_EXCL, 0644);
    if (dest_fd == -1) {
        if (errno == EEXIST) {
            fprintf(stderr, "Error: Destination file already exists.\n");
        } else {
            perror("Error creating destination file");
        }
        close(src_fd);
        return 1;
    }

    char buffer[BUFFER_SIZE];
    ssize_t bytes_read;
    while ((bytes_read = read(src_fd, buffer, BUFFER_SIZE)) > 0) {
        ssize_t bytes_written = 0;
        while (bytes_written < bytes_read) {
            ssize_t result = write(dest_fd, buffer + bytes_written, bytes_read - bytes_written);
            if (result == -1) { perror("Write error"); break; }
            bytes_written += result;
        }
    }

    close(src_fd);
    close(dest_fd);
    return 0;
}
```
**关键点说明**：
1.  **错误处理**：检查 `open`、`read`、`write` 的返回值，并使用 `perror` 或 `errno` 输出错误信息。
2.  **循环读取与写入**：因为 `read` 和 `write` 调用可能无法一次性传输请求的所有字节（尤其是在网络或特定系统条件下），所以需要在循环中处理，直到所有数据操作完成。
3.  **资源管理**：使用 `close` 系统调用关闭文件描述符，释放系统资源。

![](img/a24171389b50634ece0607b1841cc3fe_141.png)

![](img/a24171389b50634ece0607b1841cc3fe_143.png)

![](img/a24171389b50634ece0607b1841cc3fe_145.png)

![](img/a24171389b50634ece0607b1841cc3fe_146.png)

![](img/a24171389b50634ece0607b1841cc3fe_148.png)

![](img/a24171389b50634ece0607b1841cc3fe_150.png)

## 总结 🎯

![](img/a24171389b50634ece0607b1841cc3fe_152.png)

![](img/a24171389b50634ece0607b1841cc3fe_154.png)

![](img/a24171389b50634ece0607b1841cc3fe_156.png)

![](img/a24171389b50634ece0607b1841cc3fe_157.png)

![](img/a24171389b50634ece0607b1841cc3fe_159.png)

本节课中我们一起学习了 CS110 课程的初步介绍和 Linux 文件系统的基础。我们了解了：
*   课程的核心主题和学习目标。
*   文件权限的概念和八进制表示法。
*   如何使用 `open`、`read`、`write`、`close` 等系统调用进行底层的文件操作。
*   权限掩码 (`umask`) 如何影响新文件的创建。
*   如何构建一个简单的文件复制程序，并处理其中的读写循环和错误情况。

![](img/a24171389b50634ece0607b1841cc3fe_161.png)

![](img/a24171389b50634ece0607b1841cc3fe_163.png)

![](img/a24171389b50634ece0607b1841cc3fe_165.png)

![](img/a24171389b50634ece0607b1841cc3fe_167.png)

这些关于文件系统的知识是理解后续多进程、多线程等高级主题的重要基石。在接下来的课程中，我们将利用这些基础，探索程序如何并发执行并相互通信。