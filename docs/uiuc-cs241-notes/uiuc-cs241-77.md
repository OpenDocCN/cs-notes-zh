# 信号，第二部分：未决信号和信号掩码

## 信号深入解析

## 我如何了解更多关于信号的信息？

Linux 手册中讨论了第 2 节中的信号系统调用。第 7 节中还有一篇较长的文章（尽管在 OSX/BSD 中没有）：

```cpp
man -s7 signal 
```

## 信号术语

+   生成-信号是由 kill 系统调用在内核中创建的。

+   未决-尚未传递，但即将传递

+   已屏蔽-因为没有信号处理方式允许信号被传递，所以尚未传递

+   已传递-传递到进程，正在执行描述的操作

+   捕获-当进程阻止信号摧毁它并做其他事情时

## 进程的信号处理方式是什么？

对于每个进程，每个信号都有一个处理方式，这意味着当信号传递到进程时将发生什么操作。例如，默认的 SIGINT 处理方式是终止它。信号处理方式可以通过调用 signal()（这很简单，但在不同的 POSIX 架构上实现上有微妙的变化，也不建议用于多线程程序）或`sigaction`（稍后讨论）来更改。您可以将进程对所有可能信号的处理方式想象成一个函数指针条目表（每个可能信号一个）。

信号的默认处理方式可以是忽略信号、停止进程、继续已停止的进程、终止进程，或者终止进程并转储一个“核心”文件。请注意，核心文件是进程内存状态的表示，可以使用调试器进行检查。

## 可以排队多个信号吗？

不是-但是可能有信号处于未决状态。如果信号处于未决状态，这意味着它尚未传递到进程。信号处于未决状态的最常见原因是进程（或线程）当前已阻止了该特定信号。

如果特定信号，例如 SIGINT，处于未决状态，则不可能再次排队相同的信号。

*是*可能有多个不同类型的信号处于未决状态。例如，SIGINT 和 SIGTERM 信号可能是未决的（即尚未传递到目标进程）

## 如何屏蔽信号？

信号可以通过设置进程信号掩码或者在编写多线程程序时设置线程信号掩码来屏蔽（意味着它们将保持在未决状态）。

## 线程/子进程中的处理方式

## 创建新线程时会发生什么？

新线程继承了调用线程的掩码的副本

```cpp
pthread_sigmask( ... ); // set my mask to block delivery of some signals
pthread_create( ... ); // new thread will start with a copy of the same mask
```

## 分叉时会发生什么？

子进程继承了父进程的信号处理方式。换句话说，如果在分叉之前安装了 SIGINT 处理程序，那么子进程在传递 SIGINT 时也会调用处理程序。

请注意，分叉期间子进程的未决信号*不*会被继承。

## 执行期间会发生什么？

信号掩码和信号处理方式都会传递到 exec-ed 程序。[`www.gnu.org/software/libc/manual/html_node/Executing-a-File.html#Executing-a-File`](来源) 未决信号也会被保留。信号处理程序会被重置，因为原始处理程序代码随着旧进程一起消失了。

## 分叉期间会发生什么？

子进程继承了父进程的信号处理方式和父进程的信号掩码的副本。

例如，如果在父进程中阻塞了`SIGINT`，那么在子进程中也会被阻塞。例如，如果父进程为 SIG-INT 安装了处理程序（回调函数），那么子进程也会执行相同的行为。

但是未决信号不会被子进程继承。

## 如何在单线程程序中屏蔽信号？

使用`sigprocmask`！使用 sigprocmask，您可以设置新的掩码，向进程掩码添加新的要屏蔽的信号，并解除当前被屏蔽的信号。您还可以通过传递非空值来确定现有掩码（并在以后使用）。

```cpp
int sigprocmask(int how, const sigset_t *set, sigset_t *oldset);` 
```

来自 sigprocmask 的 Linux 手册页，

```cpp
SIG_BLOCK: The set of blocked signals is the union of the current set and the set argument.
SIG_UNBLOCK: The signals in set are removed from the current set of blocked signals. It is permissible to attempt to unblock a signal which is not blocked.
SIG_SETMASK: The set of blocked signals is set to the argument set. 
```

sigset 类型的行为类似于位图，只是使用函数而不是使用&和|来显式设置和取消位。

在修改一个位之前忘记初始化信号集是一个常见的错误。例如，

```cpp
sigset_t set, oldset;
sigaddset(&set, SIGINT); // Ooops!
sigprocmask(SIG_SETMASK, &set, &oldset)
```

正确的代码将集合初始化为全部打开或全部关闭。例如，

```cpp
sigfillset(&set); // all signals
sigprocmask(SIG_SETMASK, &set, NULL); // Block all the signals!
// (Actually SIGKILL or SIGSTOP cannot be blocked...)

sigemptyset(&set); // no signals 
sigprocmask(SIG_SETMASK, &set, NULL); // set the mask to be empty again
```

## 如何在多线程程序中阻止信号？

在多线程程序中阻止信号与单线程程序类似：

+   使用 pthread_sigmask 而不是 sigprocmask

+   阻止所有线程中的信号，以防止其异步传递

确保信号在所有线程中被阻止的最简单方法是在创建新线程之前在主线程中设置信号掩码

```cpp
sigemptyset(&set);
sigaddset(&set, SIGQUIT);
sigaddset(&set, SIGINT);
pthread_sigmask(SIG_BLOCK, &set, NULL);

// this thread and the new thread will block SIGQUIT and SIGINT
pthread_create(&thread_id, NULL, myfunc, funcparam);
```

就像我们在 sigprocmask 中看到的那样，pthread_sigmask 包括一个“how”参数，用于定义如何使用信号集：

```cpp
pthread_sigmask(SIG_SETMASK, &set, NULL) - replace the thread's mask with given signal set
pthread_sigmask(SIG_BLOCK, &set, NULL) - add the signal set to the thread's mask
pthread_sigmask(SIG_UNBLOCK, &set, NULL) - remove the signal set from the thread's mask
```

## 在多线程程序中如何传递待处理的信号？

信号被传递到任何未阻止该信号的信号线程。

如果两个或更多线程可以接收信号，那么哪个线程将被中断是任意的！
