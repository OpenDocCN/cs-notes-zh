# POSIX，第一部分：错误处理

## 什么是 POSIX 错误处理？

在其他语言中，你可能会看到异常处理的实现。尽管在 C 中你技术上可以使用它们（你保留一个非常 try/catch 块的堆栈，并使用`setjmp`和`longjmp`分别进入这些块），但 C 中的错误处理通常是用 posix 错误处理来完成的，代码通常看起来像这样。

```cpp
int ret = some_system_call()
if(ret == ERROR_CODE){
switch(errno){
// Do different stuff based on the errno number.
}
}

```

在内核中，使用`goto`来清理应用程序的不同部分是非常常见的。**你不应该使用 goto**，因为它会使代码更难阅读。内核中的 goto 是出于必要性而存在的，所以不要学习它。

## `errno`是什么，何时设置它？

POSIX 定义了一个特殊的整数`errno`，当系统调用失败时会设置它。`errno`的初始值是零（即没有错误）。当系统调用失败时，它通常会返回-1 来指示错误并设置`errno`。

## 多线程呢？

每个线程都有自己的`errno`副本。这非常有用；否则一个线程的错误会干扰另一个线程的错误状态。

## `errno`何时重置为零？

除非你明确将它重置为零！当系统调用成功时，它们*不*会重置`errno`的值。

这意味着你只应该依赖 errno 的值，如果你知道一个系统调用失败了（例如它返回了-1）。

## 使用`errno`的注意事项和最佳实践是什么？

当复杂的错误处理使用库调用或系统调用可能改变`errno`的值时要小心。实际上，将`errno`的值复制到一个 int 变量中更安全：

```cpp
// Unsafe - the first fprintf may change the value of errno before we use it!
if (-1 == sem_wait(&s)) {
   fprintf(stderr, "An error occurred!");
   fprintf(stderr, "The error value is %d\n", errno);
}
// Better, copy the value before making more system and library calls
if (-1 == sem_wait(&s)) {
   int errno_saved = errno;
   fprintf(stderr, "An error occurred!");
   fprintf(stderr, "The error value is %d\n", errno_saved);
}
```

同样，如果你的信号处理程序进行了任何系统或库调用，那么最好的做法是保存 errno 的原始值，并在返回之前恢复该值：

```cpp
void handler(int signal) {
   int errno_saved = errno;

   // make system calls that might change errno

   errno = errno_saved;
}
```

## 如何打印出与特定错误号相关联的字符串消息？

使用`strerror`来获取错误值的简短（英文）描述

```cpp
char *mesg = strerror(errno);
fprintf(stderr, "An error occurred (errno=%d): %s", errno, mesg);
```

## perror 和 strerror 有什么关系？

在之前的页面中，我们使用 perror 将错误打印到标准错误输出。使用`strerror`，我们现在可以编写一个简单的`perror`实现：

```cpp
void perror(char *what) {
   fprintf(stderr, "%s: %s\n", what, strerror(errno));
}
```

## 使用 strerror 的注意事项是什么？

不幸的是，`strerror`不是线程安全的。换句话说，两个线程不能同时调用它！

有两种解决方法：首先，我们可以使用互斥锁来定义一个临界区和一个本地缓冲区。所有调用`strerror`的地方都应该使用相同的互斥锁。

```cpp
pthread_mutex_lock(&m);
char *result = strerror(errno);
char *message = malloc(strlen(result) + 1);
strcpy(message, result);
pthread_mutex_unlock(&m);
fprintf(stderr, "An error occurred (errno=%d): %s", errno, message);
free(message);
```

或者使用不太便携但线程安全的`strerror_r`

## EINTR 是什么？对 sem_wait、read、write 有什么影响？

当信号（例如 SIGCHLD、SIGPIPE 等）传递到进程时，一些系统调用可能会被中断。此时，系统调用可能会返回而不执行任何操作！例如，可能没有读/写字节，信号量等待可能没有等待。

这种中断可以通过检查返回值和`errno`是否为 EINTR 来检测。在这种情况下，应该重试系统调用。通常会看到以下类型的循环，它包装了一个系统调用（比如 sem_wait）。"

```cpp
while ((-1 == systemcall(...)) && (errno == EINTR)) { /* repeat! */}
```

小心写成`== EINTR`，而不是`= EINTR`。

或者，如果结果值需要稍后使用...

```cpp
while ((-1 == (result = systemcall(...))) && (errno == EINTR)) { /* repeat! */}
```

在 Linux 上，调用`read`和`write`到本地磁盘通常不会返回 EINTR（相反，函数会自动为您重新启动）。然而，对应于网络流的文件描述符上调用`read`和`write`*可能*会返回 EINTR。

## 哪些系统调用可能会被中断并需要包装？

使用手册页！手册页包括系统调用可能设置的错误（即 errno 值）列表。一个经验法则是'慢'（阻塞）调用（例如写入套接字）可能会被中断，但快速的非阻塞调用（例如 pthread_mutex_lock）不会。

来自 Linux 信号 7 手册页。

"如果在系统调用或库函数调用被阻塞时调用了信号处理程序，那么：

+   信号处理程序返回后，调用将自动重新启动；或者

+   调用失败，并显示错误 EINTR。发生这两种行为取决于接口以及信号处理程序是否使用了 SA_RESTART 标志（请参阅 sigaction(2)）。这些细节在 UNIX 系统中各不相同；以下是 Linux 的细节。

如果对以下接口之一的阻塞调用被信号处理程序中断，那么如果使用了 SA_RESTART 标志，则在信号处理程序返回后，调用将自动重新启动；否则，调用将失败，并显示错误 EINTR：

+   对“慢”设备的 read(2)，readv(2)，write(2)，writev(2)和 ioctl(2)调用。 “慢”设备是指 I/O 调用可能会无限期地阻塞的设备，例如终端，管道或套接字。（根据此定义，磁盘不是慢设备。）如果对慢设备的 I/O 调用在被信号处理程序中断时已经传输了一些数据，则调用将返回成功状态（通常是传输的字节数）。

请注意，很容易相信设置'SA_RESTART'标志就足以使整个问题消失。不幸的是，这并不是真的：仍然有可能有系统调用会提前返回并设置`EINTR`！有关详细信息，请参阅[signal(7)](https://cs-education.github.io/sysassets/man_pages/html/man7/signal.7.html)。

## Errno 异常？

有一些 POSIX 实用程序有自己的 errno。其中一个是当您调用`getaddrinfo`函数来检查错误并将其转换为字符串时，可以使用[gai_strerror](https://linux.die.net/man/3/gai_strerror)。不要混淆它们！
