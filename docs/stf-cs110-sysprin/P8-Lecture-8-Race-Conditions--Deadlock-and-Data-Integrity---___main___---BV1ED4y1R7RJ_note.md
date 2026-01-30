![](img/186d56cf3cf36e03a3d35caf5aa63c69_1.png)

# 课程8：竞争条件、死锁与数据完整性 🧩

![](img/186d56cf3cf36e03a3d35caf5aa63c69_3.png)

![](img/186d56cf3cf36e03a3d35caf5aa63c69_5.png)

在本节课中，我们将学习进程间通信中信号处理的高级概念，特别是如何识别和避免竞争条件与死锁。我们将通过分析一个简单的Shell程序示例，来理解信号阻塞、自旋等待以及`sigsuspend`系统调用的正确用法，以确保程序的逻辑正确性和数据完整性。

![](img/186d56cf3cf36e03a3d35caf5aa63c69_7.png)

---

![](img/186d56cf3cf36e03a3d35caf5aa63c69_9.png)

## 概述

![](img/186d56cf3cf36e03a3d35caf5aa63c69_11.png)

![](img/186d56cf3cf36e03a3d35caf5aa63c69_13.png)

信号是进程间通信的一种重要机制，但不当的信号处理会导致竞争条件和数据不一致。本节课我们将深入探讨以下内容：
1.  回顾信号处理的基本机制。
2.  分析由信号引发的典型竞争条件。
3.  学习使用信号屏蔽（`sigprocmask`）来避免竞争。
4.  理解并避免低效的自旋等待。
5.  掌握使用`sigsuspend`系统调用来安全地等待信号。

![](img/186d56cf3cf36e03a3d35caf5aa63c69_15.png)

![](img/186d56cf3cf36e03a3d35caf5aa63c69_17.png)

![](img/186d56cf3cf36e03a3d35caf5aa63c69_19.png)

![](img/186d56cf3cf36e03a3d35caf5aa63c69_20.png)

---

![](img/186d56cf3cf36e03a3d35caf5aa63c69_22.png)

## 信号处理回顾与一个误导的更正

上一节我们介绍了信号处理函数和`SIGCHLD`信号。这里需要先纠正一个之前的误导。

在之前的例子中，我们讨论了子进程执行`execvp`后，其原有的信号处理器会如何。**正确的理解是**：当子进程调用`execvp`时，原进程的整个程序映像（包括其安装的信号处理器）会被新程序取代。因此，原进程中的信号处理器将不复存在，新程序会使用默认的信号处理方式或自己安装新的处理器。

![](img/186d56cf3cf36e03a3d35caf5aa63c69_24.png)

![](img/186d56cf3cf36e03a3d35caf5aa63c69_26.png)

**关键点**：`execvp`会摧毁调用它的进程中原有的一切，原程序中的任何代码（包括信号处理器）都不会再被执行。

---

## 发送信号：`kill`与`raise`系统调用

![](img/186d56cf3cf36e03a3d35caf5aa63c69_28.png)

除了操作系统内核产生信号，进程也可以主动发送信号。这主要通过两个系统调用实现：

*   **`kill`**: 向指定进程ID（PID）的进程发送一个信号。它的命名并不准确，并非总是“杀死”进程。
    ```c
    kill(pid, SIGUSR1); // 向进程pid发送SIGUSR1信号
    ```
*   **`raise`**: 向进程自身发送一个信号。
    ```c
    raise(SIGSTOP); // 进程向自己发送SIGSTOP信号，使自己暂停
    ```

以下是一个简单的示例程序，演示`raise`的用法：
```c
#include <stdio.h>
#include <signal.h>
#include <unistd.h>

![](img/186d56cf3cf36e03a3d35caf5aa63c69_30.png)

![](img/186d56cf3cf36e03a3d35caf5aa63c69_32.png)

int main() {
    printf("我将终止自己的进程。\n");
    raise(SIGKILL); // 进程向自己发送SIGKILL信号
    // 以下代码永远不会执行
    printf("这行不会打印。\n");
    return 0;
}
```

![](img/186d56cf3cf36e03a3d35caf5aa63c69_34.png)

![](img/186d56cf3cf36e03a3d35caf5aa63c69_36.png)

---

![](img/186d56cf3cf36e03a3d35caf5aa63c69_38.png)

![](img/186d56cf3cf36e03a3d35caf5aa63c69_40.png)

![](img/186d56cf3cf36e03a3d35caf5aa63c69_42.png)

![](img/186d56cf3cf36e03a3d35caf5aa63c69_44.png)

## 简单Shell中的问题：未回收的后台进程

![](img/186d56cf3cf36e03a3d35caf5aa63c69_46.png)

现在，让我们将焦点转向一个实际的例子——一个简单的Shell。最初的版本可能如下伪代码所示：

```c
void simple_shell() {
    pid_t pid = fork();
    if (pid == 0) {
        // 子进程：执行命令（例如通过execvp）
        execvp(...);
    } else {
        // 父进程
        if (command_is_background) {
            printf("[%d] %s\n", pid, command);
            // 问题：没有等待子进程，导致“僵尸进程”
        } else {
            waitpid(pid, ...); // 等待前台进程
        }
    }
}
```

**问题**：当命令在后台运行时，父进程（Shell）没有调用`waitpid`来回收结束的子进程。这会导致子进程结束后变成“僵尸进程”，占用系统资源，直到Shell本身终止。

---

## 引入信号处理器：回收子进程

![](img/186d56cf3cf36e03a3d35caf5aa63c69_48.png)

![](img/186d56cf3cf36e03a3d35caf5aa63c69_50.png)

为了解决后台进程的回收问题，我们为Shell安装一个`SIGCHLD`信号处理器。

![](img/186d56cf3cf36e03a3d35caf5aa63c69_52.png)

![](img/186d56cf3cf36e03a3d35caf5aa63c69_54.png)

```c
void sigchld_handler(int sig) {
    pid_t pid;
    while ((pid = waitpid(-1, NULL, WNOHANG)) > 0) {
        // 成功回收一个已终止的子进程
        printf("进程 %d 已结束。\n", pid);
    }
}
```

![](img/186d56cf3cf36e03a3d35caf5aa63c69_56.png)

这个处理器会在任何子进程状态改变时被调用，并使用`WNOHANG`参数非阻塞地回收所有已终止的子进程。

![](img/186d56cf3cf36e03a3d35caf5aa63c69_58.png)

---

![](img/186d56cf3cf36e03a3d35caf5aa63c69_60.png)

![](img/186d56cf3cf36e03a3d35caf5aa63c69_62.png)

![](img/186d56cf3cf36e03a3d35caf5aa63c69_64.png)

## 竞争条件的出现

![](img/186d56cf3cf36e03a3d35caf5aa63c69_66.png)

![](img/186d56cf3cf36e03a3d35caf5aa63c69_68.png)

然而，仅仅添加信号处理器会引入**竞争条件**。考虑以下逻辑，我们想跟踪前台进程的PID（`fg_pid`）：

![](img/186d56cf3cf36e03a3d35caf5aa63c69_70.png)

1.  父进程`fork`出子进程。
2.  如果它是前台进程，父进程将`fg_pid`设置为子进程的PID。
3.  父进程调用一个函数（如`wait_for_foreground`）等待`fg_pid`被清零（清零操作在信号处理器中完成）。
4.  子进程可能非常快地结束，并在父进程执行第2步（设置`fg_pid`）**之前**，信号处理器就被调用。
5.  信号处理器将`fg_pid`清零。
6.  父进程随后将`fg_pid`设置为子进程PID，然后进入等待循环。
7.  此时，`fg_pid`不为零，但子进程已结束，信号处理器不会再被触发，导致父进程永远等待下去。

![](img/186d56cf3cf36e03a3d35caf5aa63c69_72.png)

![](img/186d56cf3cf36e03a3d35caf5aa63c69_74.png)

![](img/186d56cf3cf36e03a3d35caf5aa63c69_76.png)

![](img/186d56cf3cf36e03a3d35caf5aa63c69_78.png)

这就是一个典型的竞争条件：操作的结果依赖于进程调度（即步骤2和步骤4-5谁先发生）。

![](img/186d56cf3cf36e03a3d35caf5aa63c69_80.png)

---

![](img/186d56cf3cf36e03a3d35caf5aa63c69_82.png)

## 使用信号屏蔽消除竞争条件

![](img/186d56cf3cf36e03a3d35caf5aa63c69_84.png)

为了避免上述竞争，我们需要**阻塞（屏蔽）** `SIGCHLD`信号，直到父进程准备好处理它。我们使用`sigprocmask`系统调用。

以下是修改后的安全流程：

1.  **在`fork`之前**，父进程阻塞`SIGCHLD`信号。
    ```c
    sigset_t mask, oldmask;
    sigemptyset(&mask);
    sigaddset(&mask, SIGCHLD);
    sigprocmask(SIG_BLOCK, &mask, &oldmask); // 阻塞SIGCHLD
    ```
2.  执行`fork`。
3.  **在子进程中**，解除对`SIGCHLD`的阻塞（因为子进程通常不需要关心这个信号）。
4.  **在父进程中**：
    *   如果是后台进程，直接返回，信号处理器稍后会处理。
    *   如果是前台进程，先设置`fg_pid = child_pid`。
    *   然后解除对`SIGCHLD`信号的阻塞。
    *   最后，调用函数等待前台进程结束。

![](img/186d56cf3cf36e03a3d35caf5aa63c69_86.png)

这样，确保了在`fg_pid`被正确设置之前，`SIGCHLD`信号处理器绝对不会被调用，从而消除了竞争。

![](img/186d56cf3cf36e03a3d35caf5aa63c69_88.png)

---

![](img/186d56cf3cf36e03a3d35caf5aa63c69_90.png)

![](img/186d56cf3cf36e03a3d35caf5aa63c69_92.png)

## 低效的自旋等待及其避免

![](img/186d56cf3cf36e03a3d35caf5aa63c69_94.png)

![](img/186d56cf3cf36e03a3d35caf5aa63c69_96.png)

在等待前台进程结束的函数中，我们最初可能这样写：
```c
void wait_for_foreground(pid_t pid) {
    fg_pid = pid;
    while (fg_pid == pid) {
        // 空循环，什么也不做，直到信号处理器将fg_pid清零
    }
}
```
这种循环称为**自旋等待**。它会持续占用CPU资源（使一个核心使用率达到100%），浪费电力且可能导致系统响应变慢。

我们希望进程在等待时能让出CPU。一个天真的改进是使用`sleep`或`usleep`，但这不够优雅且可能引入延迟。另一个想法是使用`pause()`函数，它会令进程休眠，直到收到任何信号。但这会引入新的**死锁**风险：

![](img/186d56cf3cf36e03a3d35caf5aa63c69_98.png)

![](img/186d56cf3cf36e03a3d35caf5aa63c69_100.png)

1.  父进程设置`fg_pid`。
2.  在调用`pause()`**之前**，子进程结束，信号处理器被调用并清空`fg_pid`。
3.  父进程调用`pause()`，此时已经没有未处理的`SIGCHLD`信号来唤醒它，导致父进程永远休眠。

---

![](img/186d56cf3cf36e03a3d35caf5aa63c69_102.png)

## 安全的等待：`sigsuspend`系统调用

解决这个问题的正确方法是使用`sigsuspend`系统调用。它原子化地执行两个操作：1) 将进程的信号掩码替换为指定的集合；2) 使进程休眠，直到收到一个未被屏蔽的信号。

以下是使用`sigsuspend`的安全模式：
```c
void wait_for_foreground(pid_t pid) {
    fg_pid = pid;
    sigset_t empty_mask;
    sigemptyset(&empty_mask);
    
    while (fg_pid == pid) {
        // 原子化地：1) 解除所有信号阻塞（使用空掩码） 2) 休眠
        sigsuspend(&empty_mask);
        // 当任何信号（尤其是SIGCHLD）到达并处理完毕后，从这里恢复
    }
    // sigsuspend返回后，原始的信号掩码（阻塞SIGCHLD）会自动恢复
}
```

**工作原理**：
1.  进入循环时，`SIGCHLD`信号仍被阻塞。
2.  调用`sigsuspend(&empty_mask)`。这个调用会：
    *   临时将进程的信号掩码替换为空掩码（即不阻塞任何信号，包括`SIGCHLD`）。
    *   立即将进程置于睡眠状态。
3.  由于`SIGCHLD`不再被阻塞，正在等待的子进程终止信号会立即送达，触发信号处理器。
4.  信号处理器回收子进程，并将`fg_pid`清零。
5.  信号处理器返回后，`sigsuspend`也随之返回，并**自动恢复**到调用前的信号掩码（即重新阻塞`SIGCHLD`）。
6.  循环检查发现`fg_pid`已不等于`pid`，循环结束。

![](img/186d56cf3cf36e03a3d35caf5aa63c69_104.png)

`sigsuspend`的原子性（临时解除阻塞和进入睡眠是一个不可分割的操作）完美避免了`pause()`可能遇到的死锁情况。

---

## 期中考试样题分析

![](img/186d56cf3cf36e03a3d35caf5aa63c69_106.png)

最后，我们通过一个往期期中考试题目来巩固对信号执行顺序的理解。

![](img/186d56cf3cf36e03a3d35caf5aa63c69_108.png)

考虑以下程序：
```c
void handler(int sig) { printf(“pirate“); exit(0); }
int main() {
    signal(SIGUSR1, handler);
    pid_t pid = fork();
    if (pid == 0) {
        printf(“ghost“);
        return 0;
    } else {
        kill(pid, SIGUSR1);
        printf(“ninja“);
        return 0;
    }
}
```
假设所有`printf`输出是原子的。请问输出序列“ghost ninja pirate”是否可能？

![](img/186d56cf3cf36e03a3d35caf5aa63c69_110.png)

![](img/186d56cf3cf36e03a3d35caf5aa63c69_112.png)

**分析**：
1.  `fork`后，子进程可能先执行，打印“ghost”。
2.  父进程执行`kill`发送`SIGUSR1`给子进程，然后立即打印“ninja”。
3.  子进程在`return 0;`**之前**收到信号，跳转到`handler`，打印“pirate”并调用`exit(0)`直接终止（不会执行`return 0;`）。
4.  因此，输出“ghost ninja pirate”是**可能**的。

![](img/186d56cf3cf36e03a3d35caf5aa63c69_114.png)

**关键点**：信号的传递和接收是异步的。子进程的主执行流（打印“ghost”）和信号处理流（打印“pirate”）是互斥的，但它们的相对顺序取决于调度。`exit(0)`会立即终止进程，阻止“ghost”在信号处理后被打印。

---

## 总结

本节课我们一起深入学习了信号处理中的高级议题：
1.  **竞争条件**：当多个进程（或信号处理器）以不可预测的顺序访问和修改共享数据（如全局变量`fg_pid`）时发生。
2.  **信号屏蔽**：使用`sigprocmask`阻塞特定信号，是保护关键代码段、消除竞争条件的核心手段。
3.  **自旋等待**：应避免使用消耗CPU的空循环来等待事件。
4.  **安全等待信号**：使用`sigsuspend`系统调用可以原子化地解除信号阻塞并进入睡眠，是避免死锁、安全等待信号发生的标准方法。
5.  **逻辑推理**：通过分析程序代码和信号异步特性，可以推理出可能的输出序列，这是理解和调试并发程序的重要技能。

![](img/186d56cf3cf36e03a3d35caf5aa63c69_116.png)

掌握这些概念，对于编写正确、高效且稳健的并发程序至关重要。