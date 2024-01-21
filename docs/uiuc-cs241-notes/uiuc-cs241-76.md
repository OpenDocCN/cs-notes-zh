# 进程控制，第一部分：使用信号的等待宏

## 等待宏

## 我能找出我的子进程的退出值吗？

您可以找到子进程退出值的最低 8 位（`main()`的返回值或包含在`exit()`中的值）：使用“等待宏” - 通常会使用“WIFEXITED”和“WEXITSTATUS”。有关更多信息，请参阅`wait`/`waitpid`手册页。

```cpp
int status;
pid_t child = fork();
if (child == -1) return 1; //Failed
if (child > 0) { /* I am the parent - wait for the child to finish */
  pid_t pid = waitpid(child, &status, 0);
  if (pid != -1 && WIFEXITED(status)) {
     int low8bits = WEXITSTATUS(status);
     printf("Process %d returned %d" , pid, low8bits);
  }
} else { /* I am the child */
 // do something interesting
  execl("/bin/ls", "/bin/ls", ".", (char *) NULL); // "ls ."
}
```

一个进程只能有 256 个返回值，其余的位是信息性的。

## 位移

请注意，没有必要记住这一点，这只是对状态变量内部存储信息的高级概述。

[Android 源代码](https://android.googlesource.com/platform/prebuilts/gcc/linuxx86/host/i686-linux-glibc2.7-%0A4.6/+/tools_r20/sysroot/usr/include/bits/waitstatus.h)

/*如果 WIFEXITED(STATUS)，则为状态的低 8 位。*/

#define __WEXITSTATUS(status) (((status) & 0xff00) >> 8)

/*如果 WIFSIGNALED(STATUS)，则为终止信号。*/

#define __WTERMSIG(status) ((status) & 0x7f)

/*如果 WIFSTOPPED(STATUS)，则为停止子进程的信号。*/

#define __WSTOPSIG(status) __WEXITSTATUS(status)

/*如果 STATUS 指示正常终止，则为非零。*/

#define __WIFEXITED(status) (__WTERMSIG(status) == 0)

内核有一种内部方式来跟踪发出信号、退出或停止的情况。该 API 被抽象化，以便内核开发人员可以随意更改。

## 小心。

请记住，如果前提条件得到满足，那么宏才有意义。这意味着如果进程被发出信号，进程的退出状态将不会被定义。宏不会为您进行检查，因此需要编程来确保逻辑正确。

## 信号

## 什么是信号？

信号是内核为我们提供的一种构造。它允许一个进程异步地向另一个进程发送信号（想象一条消息）。如果该进程想要接受信号，它可以，然后对于大多数信号，可以决定如何处理该信号。这里是一个信号的简短列表（非全面）。

| 名称 | 默认操作 | 通常用例 |
| --- | --- | --- |
| `SIGINT` | 终止进程（可捕获） | 告诉进程停止 |
| `SIGQUIT` | 终止进程（可捕获） | 告诉进程停止 |
| `SIGSTOP` | 停止进程（无法捕获） | 停止进程以便继续 |
| `SIGCONT` | 继续进程 | 继续运行进程 |
| `SIGKILL` | 终止进程（无法忽略） | 你想让你的进程消失 |

## 我能暂停我的子进程吗？

是的！您可以通过发送 SIGSTOP 信号来暂时暂停运行中的进程。如果成功，它将冻结一个进程；即进程将不再分配任何 CPU 时间。

要允许进程恢复执行，请发送 SIGCONT 信号。

例如，这是一个每秒慢慢打印一个点的程序，最多 59 个点。

```cpp
#include <unistd.h>
#include <stdio.h>
int main() {
  printf("My pid is %d\n", getpid() );
  int i = 60;
  while(--i) { 
    write(1, ".",1);
    sleep(1);
  }
  write(1, "Done!",5);
  return 0;
}
```

我们将首先在后台启动进程（注意末尾的&）。然后通过使用 kill 命令从 shell 进程发送信号给它。

```cpp
>./program &
My pid is 403
...
>kill -SIGSTOP 403
>kill -SIGCONT 403 
```

## 如何从 C 中杀死/停止/暂停我的子进程？

在 C 中，使用`kill` POSIX 调用向子进程发送信号，

```cpp
kill(child, SIGUSR1); // Send a user-defined signal
kill(child, SIGSTOP); // Stop the child process (the child cannot prevent this)
kill(child, SIGTERM); // Terminate the child process (the child can prevent this)
kill(child, SIGINT); // Equivalent to CTRL-C (by default closes the process)
```

正如我们上面看到的，在 shell 中也有一个 kill 命令，例如获取正在运行的进程列表，然后终止进程 45 和进程 46

```cpp
ps
kill -l 
kill -9 45
kill -s TERM 46 
```

## 如何检测“CTRL-C”并优雅地清理？

我们将在后面回到信号 - 这只是一个简短的介绍。在 Linux 系统上，如果您有兴趣了解更多信息，请参阅`man -s7 signal`（例如系统和库调用的异步信号安全列表）。

信号处理程序内部的可执行代码有严格的限制。大多数库和系统调用都不是“异步信号安全”的 - 它们不能在信号处理程序内部使用，因为它们不是可重入安全的。在单线程程序中，信号处理瞬间中断程序执行，以执行信号处理程序代码。假设您的原始程序在执行`malloc`库代码时被中断；malloc 使用的内存结构将不处于一致状态。在信号处理程序中调用`printf`（它使用`malloc`）是不安全的，并将导致“未定义行为”，即不再是一个有用的、可预测的程序。实际上，您的程序可能会崩溃，计算或生成不正确的结果，或者停止运行（“死锁”），具体取决于在执行信号处理程序代码时您的程序正在执行什么。

信号处理程序的一个常见用途是设置一个布尔标志，该标志偶尔被轮询（读取），作为程序正常运行的一部分。例如，

```cpp
int pleaseStop ; // See notes on why "volatile sig_atomic_t" is better

void handle_sigint(int signal) {
  pleaseStop = 1;
}

int main() {
  signal(SIGINT, handle_sigint);
  pleaseStop = 0;
  while ( ! pleaseStop) { 
     /* application logic here */ 
   }
  /* cleanup code here */
}
```

上述代码在纸上看起来可能是正确的。但是，我们需要向编译器和将执行`main()`循环的 CPU 核心提供提示。我们需要防止编译器优化：表达式`! pleaseStop`似乎是一个循环不变量，即永远为真，因此可以简化为`true`。其次，我们需要确保`pleaseStop`的值不是使用 CPU 寄存器缓存的，而是始终从主存中读取和写入。`sig_atomic_t`类型意味着变量的所有位可以被读取或修改为“原子操作” - 一个不可中断的操作。不可能读取由一些新位值和旧位值组成的值。

通过使用正确类型的`volatile sig_atomic_t`指定`pleaseStop`，我们可以编写可移植的代码，其中主循环将在信号处理程序返回后退出。在大多数现代平台上，`sig_atomic_t`类型可以与`int`一样大，但在嵌入式系统上，它可以与`char`一样小，并且只能表示（-127 至 127）的值。

```cpp
volatile sig_atomic_t pleaseStop;
```

这种模式的两个示例可以在“COMP”中找到，这是一个基于终端的 1Hz 4 位计算机（[`github.com/gto76/comp-cpp/blob/1bf9a77eaf8f57f7358a316e5bbada97f2dc8987/src/output.c#L121`](https://github.com/gto76/comp-cpp/blob/1bf9a77eaf8f57f7358a316e5bbada97f2dc8987/src/output.c#L121)）。使用了两个布尔标志。一个用于标记`SIGINT`（CTRL-C）的传递，并优雅地关闭程序，另一个用于标记`SIGWINCH`信号以检测终端调整大小并重新绘制整个显示。


