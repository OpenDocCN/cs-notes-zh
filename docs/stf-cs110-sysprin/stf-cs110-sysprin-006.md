# 6：execvp, pipe, dup2, signals 🚀

在本节课中，我们将要学习多进程编程中的几个核心概念：如何使用 `execvp` 运行新程序，如何通过 `pipe` 和 `dup2` 在进程间建立通信管道，以及如何利用 `signals` 处理进程间的事件通知。这些是构建更复杂程序（如你自己的shell）的基础。

## 概述：多进程与进程间通信

上一节我们介绍了 `fork` 系统调用，它允许我们创建新的进程。本节中我们来看看如何让新进程执行不同的程序，以及如何让父子进程之间进行数据交换和事件通知。

![](img/e8c16a216dab678dec1c79e51f021b08_1.png)

![](img/e8c16a216dab678dec1c79e51f021b08_3.png)

我们将通过构建一个简单的 `shell` 程序来串联这些概念，它能运行命令、处理后台进程，并管理进程间的输入输出。

![](img/e8c16a216dab678dec1c79e51f021b08_5.png)

![](img/e8c16a216dab678dec1c79e51f021b08_7.png)

![](img/e8c16a216dab678dec1c79e51f021b08_9.png)

![](img/e8c16a216dab678dec1c79e51f021b08_11.png)

---

![](img/e8c16a216dab678dec1c79e51f021b08_12.png)

![](img/e8c16a216dab678dec1c79e51f021b08_14.png)

## 1. 使用 execvp 运行新程序 🔄

![](img/e8c16a216dab678dec1c79e51f021b08_16.png)

![](img/e8c16a216dab678dec1c79e51f021b08_18.png)

![](img/e8c16a216dab678dec1c79e51f021b08_20.png)

![](img/e8c16a216dab678dec1c79e51f021b08_22.png)

`execvp` 是 `exec` 函数家族的一员，它的作用是**用另一个程序替换当前进程的内存映像**。这意味着调用 `execvp` 后，原进程的代码就不再运行，转而执行新的程序。

![](img/e8c16a216dab678dec1c79e51f021b08_24.png)

![](img/e8c16a216dab678dec1c79e51f021b08_26.png)

![](img/e8c16a216dab678dec1c79e51f021b08_28.png)

**核心公式**：
```c
int execvp(const char *file, char *const argv[]);
```
*   `file`: 要执行的程序名。
*   `argv`: 传递给新程序的参数列表（类似于 `main` 函数的 `argv`），必须以 `NULL` 指针结束。

![](img/e8c16a216dab678dec1c79e51f021b08_30.png)

通常，我们不会直接在父进程中调用 `execvp`，因为这会终止父进程。更常见的模式是：
1.  父进程调用 `fork()` 创建子进程。
2.  在子进程中调用 `execvp()` 来运行新程序。
3.  父进程继续执行原有逻辑。

![](img/e8c16a216dab678dec1c79e51f021b08_32.png)

以下是一个简单示例 `mysystem` 函数，它模拟了系统调用 `system()` 的部分功能：

![](img/e8c16a216dab678dec1c79e51f021b08_34.png)

![](img/e8c16a216dab678dec1c79e51f021b08_36.png)

![](img/e8c16a216dab678dec1c79e51f021b08_38.png)

```c
pid_t pid = fork();
if (pid == 0) {
    // 子进程：运行 /bin/sh 来解释执行命令
    char *args[] = {"/bin/sh", "-c", command, NULL};
    execvp(args[0], args);
    // 如果 execvp 成功，不会执行到这里
    exit(1);
} else {
    // 父进程：等待子进程结束
    waitpid(pid, &status, 0);
}
```

在这个模式中，子进程被 `/bin/sh`（即shell程序）“吞噬”，并由它来执行用户输入的命令（如 `ls`）。

![](img/e8c16a216dab678dec1c79e51f021b08_40.png)

![](img/e8c16a216dab678dec1c79e51f021b08_42.png)

---

![](img/e8c16a216dab678dec1c79e51f021b08_44.png)

![](img/e8c16a216dab678dec1c79e51f021b08_46.png)

![](img/e8c16a216dab678dec1c79e51f021b08_48.png)

![](img/e8c16a216dab678dec1c79e51f021b08_49.png)

![](img/e8c16a216dab678dec1c79e51f021b08_51.png)

## 2. 实现一个简单的后台 Shell 🐚

![](img/e8c16a216dab678dec1c79e51f021b08_53.png)

![](img/e8c16a216dab678dec1c79e51f021b08_55.png)

基于 `fork` 和 `execvp`，我们可以构建一个能处理前台和后台命令的简易shell。

![](img/e8c16a216dab678dec1c79e51f021b08_57.png)

![](img/e8c16a216dab678dec1c79e51f021b08_59.png)

**核心逻辑**：
*   读取用户输入的命令。
*   如果命令以 `&` 结尾，则标记为**后台运行**。
*   `fork` 出子进程，在子进程中用 `execvp` 执行命令。
*   在父进程中：
    *   如果是**前台命令**，则调用 `waitpid` 等待子进程结束，再显示下一个提示符。
    *   如果是**后台命令**，则**不等待**，直接显示下一个提示符，让子进程在后台独立运行。

![](img/e8c16a216dab678dec1c79e51f021b08_61.png)

以下是关键代码片段：

![](img/e8c16a216dab678dec1c79e51f021b08_63.png)

```c
// 解析命令，判断是否以 '&' 结尾
int run_in_background = is_background_command(args);

pid_t pid = fork();
if (pid == 0) {
    // 子进程执行命令
    execvp(args[0], args);
    exit(1); // execvp 失败时才执行
} else if (pid > 0) {
    // 父进程
    if (!run_in_background) {
        // 前台运行：等待子进程
        waitpid(pid, &status, 0);
    } else {
        // 后台运行：打印进程ID后立即返回
        printf("[%d] %s\n", pid, command);
    }
}
```
这样，当用户输入 `sleep 10 &` 时，shell会立刻返回提示符，而 `sleep` 命令则在后台继续执行。

---

## 3. 使用 pipe 建立进程间通信管道 🚰

![](img/e8c16a216dab678dec1c79e51f021b08_65.png)

![](img/e8c16a216dab678dec1c79e51f021b08_67.png)

![](img/e8c16a216dab678dec1c79e51f021b08_69.png)

`pipe` 系统调用创建了一个**单向通信通道**，用于两个进程（通常是父子进程）间传递数据。它返回两个文件描述符（file descriptor）：一个用于读取，一个用于写入。

![](img/e8c16a216dab678dec1c79e51f021b08_71.png)

![](img/e8c16a216dab678dec1c79e51f021b08_73.png)

**核心公式**：
```c
int pipe(int fds[2]);
```
调用成功后：
*   `fds[0]` 成为管道的**读取端**。
*   `fds[1]` 成为管道的**写入端**。
*   写入 `fds[1]` 的数据可以从 `fds[0]` 读取。

![](img/e8c16a216dab678dec1c79e51f021b08_75.png)

**重要特性**：调用 `fork` 后，子进程会继承父进程打开的文件描述符。因此，父子进程可以通过同一个管道进行通信。通常的用法是：
*   父进程关闭读取端 (`fds[0]`)，只保留写入端，向管道写数据。
*   子进程关闭写入端 (`fds[1]`)，只保留读取端，从管道读数据。

![](img/e8c16a216dab678dec1c79e51f021b08_77.png)

以下是一个简单的管道示例，父进程向子进程发送字符串：

```c
int fds[2];
pipe(fds); // 创建管道

![](img/e8c16a216dab678dec1c79e51f021b08_79.png)

pid_t pid = fork();
if (pid == 0) {
    // 子进程：关闭写入端，准备读取
    close(fds[1]);
    char buffer[128];
    read(fds[0], buffer, sizeof(buffer));
    printf("Child read: %s\n", buffer);
    close(fds[0]);
    exit(0);
} else {
    // 父进程：关闭读取端，准备写入
    close(fds[0]);
    write(fds[1], "Hello from parent", 18);
    close(fds[1]); // 关闭写入端表示数据发送完毕
    waitpid(pid, NULL, 0); // 等待子进程
}
```
**注意**：`read` 调用会**阻塞**，直到有数据可读或管道写入端全部关闭。父进程关闭写入端 (`fds[1]`) 是通知子进程“数据已发送完”的关键。

![](img/e8c16a216dab678dec1c79e51f021b08_81.png)

![](img/e8c16a216dab678dec1c79e51f021b08_83.png)

---

## 4. 使用 dup2 重定向标准输入输出 🔀

![](img/e8c16a216dab678dec1c79e51f021b08_85.png)

`dup2` 系统调用用于**复制一个文件描述符**。最常见的用途是重定向进程的标准输入（`STDIN_FILENO`, 0）、标准输出（`STDOUT_FILENO`, 1）或标准错误（`STDERR_FILENO`, 2）。

![](img/e8c16a216dab678dec1c79e51f021b08_87.png)

**核心公式**：
```c
int dup2(int oldfd, int newfd);
```
它使 `newfd` 成为 `oldfd` 的副本。如果 `newfd` 已经打开，会先将其关闭。

![](img/e8c16a216dab678dec1c79e51f021b08_89.png)

![](img/e8c16a216dab678dec1c79e51f021b08_91.png)

在管道通信中，我们常用 `dup2` 将子进程的标准输入重定向到管道的读取端。这样，子进程在执行时（例如运行 `sort` 命令），就会从管道读取数据，而不是从键盘输入。

![](img/e8c16a216dab678dec1c79e51f021b08_93.png)

以下是将管道读取端重定向为标准输入的典型用法：

![](img/e8c16a216dab678dec1c79e51f021b08_95.png)

```c
// 假设在子进程中，fds[0]是管道的读取端
close(fds[1]); // 子进程不需要写入端
dup2(fds[0], STDIN_FILENO); // 将标准输入重定向到管道读取端
close(fds[0]); // 重定向后，原始的fds[0]可以关闭了

// 现在执行程序，例如 sort，它会从管道读取输入
execlp("sort", "sort", NULL);
```

---

![](img/e8c16a216dab678dec1c79e51f021b08_97.png)

## 5. 综合示例：创建子进程并传递数据 🧩

![](img/e8c16a216dab678dec1c79e51f021b08_99.png)

![](img/e8c16a216dab678dec1c79e51f021b08_101.png)

![](img/e8c16a216dab678dec1c79e51f021b08_103.png)

结合 `pipe`、`fork`、`dup2` 和 `execvp`，我们可以编写一个 `subprocess` 函数。该函数启动一个子进程（如 `sort`），并返回一个文件描述符给父进程。父进程向这个文件描述符写入数据，数据就会成为子进程的输入。

以下是 `subprocess` 函数的简化框架和 `main` 函数中的用法：

```c
// subprocess_t 结构体，用于返回子进程信息
typedef struct {
    pid_t pid;   // 子进程ID
    int supply_fd; // 父进程写入此fd，数据会供给子进程
} subprocess_t;

subprocess_t subprocess(char *command) {
    int fds[2];
    pipe(fds);
    pid_t pid = fork();

    if (pid == 0) {
        // 子进程
        close(fds[1]); // 关闭写入端
        dup2(fds[0], STDIN_FILENO); // 重定向标准输入到管道
        close(fds[0]);
        // 执行命令
        execlp("/bin/sh", "sh", "-c", command, NULL);
        exit(1);
    } else {
        // 父进程
        close(fds[0]); // 关闭读取端
        subprocess_t sp = {pid, fds[1]};
        return sp;
    }
}

![](img/e8c16a216dab678dec1c79e51f021b08_105.png)

![](img/e8c16a216dab678dec1c79e51f021b08_107.png)

// 在 main 函数中使用
int main() {
    // 启动 sort 命令作为子进程
    subprocess_t sp = subprocess("/usr/bin/sort");

    // 父进程向子进程供给数据
    char *words[] = {"banana", "apple", "cherry"};
    for (int i = 0; i < 3; i++) {
        dprintf(sp.supply_fd, "%s\n", words[i]);
    }
    close(sp.supply_fd); // 关闭供给端，告知子进程输入结束

    waitpid(sp.pid, &status, 0); // 等待子进程结束
    return 0;
}
```
运行此程序，`sort` 子进程会收到单词列表，排序后输出到终端。父进程关闭 `supply_fd` 至关重要，它相当于在终端按下 `Ctrl+D`，告诉 `sort` 输入已结束，可以开始排序了。

![](img/e8c16a216dab678dec1c79e51f021b08_109.png)

![](img/e8c16a216dab678dec1c79e51f021b08_111.png)

---

![](img/e8c16a216dab678dec1c79e51f021b08_113.png)

![](img/e8c16a216dab678dec1c79e51f021b08_115.png)

![](img/e8c16a216dab678dec1c79e51f021b08_117.png)

## 6. 使用 signals 处理进程事件 📞

![](img/e8c16a216dab678dec1c79e51f021b08_119.png)

信号（Signal）是内核向进程发送的**异步事件通知**。例如，按下 `Ctrl+C`（发送 `SIGINT`）可以终止前台进程，子进程结束时会向父进程发送 `SIGCHLD` 信号。

![](img/e8c16a216dab678dec1c79e51f021b08_121.png)

![](img/e8c16a216dab678dec1c79e51f021b08_123.png)

我们可以为特定信号注册一个**信号处理函数**（signal handler），当信号发生时，该函数会被调用。

**核心概念**：
*   `SIGCHLD`：子进程状态改变（终止、停止、继续）时发送给父进程。
*   `signal(int signum, void (*handler)(int))`：设置信号处理函数。

一个常见的用途是处理僵尸进程。如果父进程不调用 `waitpid` 回收已终止的子进程，子进程会变成“僵尸”。通过捕获 `SIGCHLD` 信号并在处理函数中调用 `waitpid`，可以及时清理子进程。

以下是一个“迪士尼乐园”的例子，演示了父进程在子进程（孩子们）玩耍时小睡，并在孩子回来时被唤醒：

```c
#include <signal.h>
#include <unistd.h>
#include <sys/wait.h>

int children_done = 0;
void reap_child(int sig) {
    waitpid(-1, NULL, 0); // 回收任意一个已终止的子进程
    children_done++;
}

int main() {
    signal(SIGCHLD, reap_child); // 设置 SIGCHLD 的处理函数

    for (int i = 0; i < 5; i++) {
        if (fork() == 0) {
            // 子进程：模拟玩耍时间
            sleep(3 * (i + 1));
            exit(0);
        }
    }

    // 父进程：等待所有孩子回来
    while (children_done < 5) {
        printf("At least one child is playing, dad naps.\n");
        sleep(5); // sleep 会被到来的 SIGCHLD 信号中断
        printf("Dad wakes up!\n");
    }
    printf("All children back home. Let's leave!\n");
    return 0;
}
```
在这个例子中，`sleep` 会被 `SIGCHLD` 信号中断，父进程每次被唤醒就检查是否有孩子回来。使用信号处理使得父进程无需主动轮询子进程状态。

![](img/e8c16a216dab678dec1c79e51f021b08_125.png)

![](img/e8c16a216dab678dec1c79e51f021b08_127.png)

**注意**：一些信号（如 `SIGKILL`, `SIGSTOP`）不能被捕获或忽略。在信号处理函数中应尽量只做简单操作，避免使用不可重入函数（如 `printf`），本例仅为演示。

![](img/e8c16a216dab678dec1c79e51f021b08_129.png)

![](img/e8c16a216dab678dec1c79e51f021b08_131.png)

---

![](img/e8c16a216dab678dec1c79e51f021b08_133.png)

![](img/e8c16a216dab678dec1c79e51f021b08_135.png)

![](img/e8c16a216dab678dec1c79e51f021b08_137.png)

## 总结 🎯

![](img/e8c16a216dab678dec1c79e51f021b08_139.png)

![](img/e8c16a216dab678dec1c79e51f021b08_141.png)

本节课中我们一起学习了多进程编程的核心工具链：

1.  **`execvp`**：用于在子进程中加载并执行全新的程序。
2.  **Shell 实现**：结合 `fork` 和 `execvp`，可以构建支持前后台任务管理的简单shell。
3.  **`pipe`**：创建单向通信管道，是进程间通信（IPC）的基本方式之一。
4.  **`dup2`**：重定向文件描述符，常用于将管道的一端连接到进程的标准输入或输出。
5.  **综合应用**：通过 `subprocess` 模式，可以灵活地启动子进程并控制其输入源。
6.  **`signals`**：处理异步事件，如使用 `SIGCHLD` 信号高效地回收子进程资源。

![](img/e8c16a216dab678dec1c79e51f021b08_143.png)

掌握这些概念和系统调用，你就有能力编写出像 `shell` 一样可以创建、管理、并与多个进程交互的复杂程序。在接下来的作业中，你将有机会实践这些知识，构建更强大的工具。