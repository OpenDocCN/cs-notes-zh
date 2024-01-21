# 信号，第四部分：Sigaction

## 我如何使用`sigaction`？ 

您应该使用`sigaction`而不是`signal`，因为它具有更好定义的语义。不同操作系统上的`signal`会执行不同的操作，这是**不好的**，`sigaction`更具可移植性，如果需要，对于线程更好地定义。

要更改进程的“信号处理方式” - 即当信号传递到您的进程时会发生什么 - 使用`sigaction`

您可以使用系统调用`sigaction`来设置信号的当前处理程序，或者读取特定信号的当前信号处理程序。

```cpp
int sigaction(int signum, const struct sigaction *act, struct sigaction *oldact);
```

sigaction 结构包括两个回调函数（我们只会看'handler'版本），一个信号掩码和一个标志字段。

```cpp
struct sigaction {
               void     (*sa_handler)(int);
               void     (*sa_sigaction)(int, siginfo_t *, void *);
               sigset_t   sa_mask;
               int        sa_flags;
}; 
```

## 我如何将`signal`调用转换为等效的`sigaction`调用？

假设您为警报信号安装了信号处理程序，

```cpp
signal(SIGALRM, myhandler);
```

等效的`sigaction`代码是：

```cpp
struct sigaction sa; 
sa.sa_handler = myhandler;
sigemptyset(&sa.sa_mask);
sa.sa_flags = 0; 
sigaction(SIGALRM, &sa, NULL)
```

但是，我们通常也可以设置掩码和标志字段。掩码是在信号处理程序执行期间使用的临时信号掩码。SA_RESTART 标志将自动重新启动一些（但不是所有）否则会提前返回（带有 EINTR 错误）的系统调用。后者意味着我们可以在一定程度上简化其余代码，因为可能不再需要重启循环。

```cpp
sigfillset(&sa.sa_mask);
sa.sa_flags = SA_RESTART; /* Restart functions if  interrupted by handler */     
```

## 我如何使用 sigwait？

Sigwait 可以用来一次读取一个挂起的信号。`sigwait`用于同步等待信号，而不是在回调中处理它们。多线程程序中典型的 sigwait 用法如下所示。请注意，线程信号掩码首先被设置（并将被新线程继承）。这可以防止信号被*传递*，因此它们将保持挂起状态，直到调用 sigwait。还要注意，相同的设置 sigset_t 变量被 sigwait 使用 - 除了设置被阻塞信号的集合之外，它被用作 sigwait 可以捕获和返回的信号集合。

编写自定义信号处理线程（如下面的示例）的一个优点是，现在您可以使用更多的 C 库和系统函数，否则不能安全地在信号处理程序中使用，因为它们不是异步信号安全的。

基于`http://pubs.opengroup.org/onlinepubs/009695399/functions/pthread_sigmask.html`

```cpp
static sigset_t   signal_mask;  /* signals to block         */

int main (int argc, char *argv[])
{
    pthread_t sig_thr_id;      /* signal handler thread ID */
    sigemptyset (&signal_mask);
    sigaddset (&signal_mask, SIGINT);
    sigaddset (&signal_mask, SIGTERM);
    pthread_sigmask (SIG_BLOCK, &signal_mask, NULL);

    /* New threads will inherit this thread's mask */
    pthread_create (&sig_thr_id, NULL, signal_thread, NULL);

    /* APPLICATION CODE */
    ...
}

void *signal_thread (void *arg)
{
    int       sig_caught;    /* signal caught       */

    /* Use same mask as the set of signals that we'd like to know about! */
    sigwait(&signal_mask, &sig_caught);
    switch (sig_caught)
    {
    case SIGINT:     /* process SIGINT  */
        ...
        break;
    case SIGTERM:    /* process SIGTERM */
        ...
        break;
    default:         /* should normally not happen */
        fprintf (stderr, "\nUnexpected signal %d\n", sig_caught);
        break;
    }
}
```
