# 信号，第三部分：触发信号

## 如何从 shell 发送信号给进程？

您已经知道发送`SIG_INT`的一种方法，只需在 shell 中键入`CTRL-C`。您还可以使用`kill`（如果知道进程 ID）和`killall`（如果知道进程名称）。

```cpp
# First let's use ps and grep to find the process we want to send a signal to
$ ps au | grep myprogram
angrave  4409   0.0  0.0  2434892    512 s004  R+    2:42PM   0:00.00 myprogram 1 2 3

#Send SIGINT signal to process 4409 (equivalent of `CTRL-C`)
$ kill -SIGINT 4409

#Send SIGKILL (terminate the process)
$ kill -SIGKILL 4409
$ kill -9 4409 
```

`killall`类似，只是它是根据程序名称匹配。下面的两个例子，发送`SIGINT`然后`SIGKILL`来终止正在运行`myprogram`的进程。

```cpp
# Send SIGINT (SIGINT can be ignored)
$ killall -SIGINT myprogram

# SIGKILL (-9) cannot be ignored! 
$ killall -9 myprogram 
```

## 如何从正在运行的 C 程序发送信号给进程？

使用`raise`或`kill`

```cpp
int raise(int sig); // Send a signal to myself!
int kill(pid_t pid, int sig); // Send a signal to another process
```

对于非根进程，信号只能发送给相同用户的进程，即你不能随便 SIGKILL 我的进程！参见 kill(2)即 man -s2 以获取更多详细信息。

## 如何向特定线程发送信号？

使用`pthread_kill`

```cpp
int pthread_kill(pthread_t thread, int sig)
```

在下面的示例中，执行`func`的新创建的线程将被`SIGINT`中断。

```cpp
pthread_create(&tid, NULL, func, args);
pthread_kill(tid, SIGINT);
pthread_kill(pthread_self(), SIGKILL); // send SIGKILL to myself
```

## `pthread_kill（threadid，SIGKILL）`会杀死进程还是线程？

它将杀死整个进程。尽管单个线程可以设置信号掩码，但信号处理（每个信号执行的处理程序/动作表）是*每个进程*而不是*每个线程*。这意味着`sigaction`可以从任何线程调用，因为您将为进程中的所有线程设置信号处理程序。

## 如何捕获（处理）信号？

您可以选择异步或同步地处理挂起的信号。

安装信号处理程序以异步处理信号使用`sigaction`（或者，对于简单的示例，`signal`）。

同步捕获挂起信号使用`sigwait`（它会阻塞，直到信号被传递）或`signalfd`（它也会阻塞并提供一个文件描述符，可以使用`read()`来检索挂起的信号）。

参见`Signals, Part 4`以获取使用`sigwait`的示例
