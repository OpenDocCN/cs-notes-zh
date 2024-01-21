# 同步，第二部分：计数信号量

## 什么是计数信号量？

计数信号量包含一个值，并支持两个操作“等待”和“发布”。发布增加信号量并立即返回。“等待”将在计数为零时等待。如果计数不为零，则信号量将减少计数并立即返回。

一个类比是饼干罐中的饼干数量（或者宝箱中的金币数量）。在拿饼干之前，调用“等待”。如果没有剩下饼干，那么`等待`将不会返回：它将等待，直到另一个线程通过调用 post 增加信号量。

简而言之，“发布”增加并立即返回，而“等待”将在计数为零时等待。在返回之前，它将减少计数。

## 我如何创建一个信号量？

本页介绍了未命名信号量。不幸的是，Mac OS X 目前还不支持这些。

首先决定初始值是零还是其他值（例如数组中剩余空间的数量）。与 pthread 互斥锁不同，创建信号量没有捷径 - 使用`sem_init`

```cpp
#include <semaphore.h>

sem_t s;
int main() {
  sem_init(&s, 0, 10); // returns -1 (=FAILED) on OS X
  sem_wait(&s); // Could do this 10 times without blocking
  sem_post(&s); // Announce that we've finished (and one more resource item is available; increment count)
  sem_destroy(&s); // release resources of the semaphore
}
```

## 我可以从不同的线程调用 wait 和 post 吗？

可以！与互斥锁不同，增量和减量可以来自不同的线程。

## 可以使用信号量代替互斥锁吗？

是的 - 虽然信号量的开销更大。要使用信号量：

+   用计数为一初始化信号量。

+   用`...lock`替换`sem_wait`

+   用`...unlock`替换`sem_post`

互斥锁是一个在“发布”之前始终“等待”的信号量

```cpp
sem_t s;
sem_init(&s, 0, 1);

sem_wait(&s);
// Critical Section
sem_post(&s);
```

## 我可以在信号处理程序中使用 sem_post 吗？

是的！`sem_post`是少数几个可以在信号处理程序中正确使用的函数之一。这意味着我们可以释放一个等待的线程，该线程现在可以进行所有我们不允许在信号处理程序本身内调用的调用（例如`printf`）。

```cpp
#include <stdio.h>
#include <pthread.h>
#include <signal.h>
#include <semaphore.h>
#include <unistd.h>

sem_t s;

void handler(int signal)
{
    sem_post(&s); /* Release the Kraken! */
}

void *singsong(void *param)
{
    sem_wait(&s);
    printf("I had to wait until your signal released me!\n");
}

int main()
{
    int ok = sem_init(&s, 0, 0 /* Initial value of zero*/); 
    if (ok == -1) {
       perror("Could not create unnamed semaphore");
       return 1;
    }
    signal(SIGINT, handler); // Too simple! See note below

    pthread_t tid;
    pthread_create(&tid, NULL, singsong, NULL);
    pthread_exit(NULL); /* Process will exit when there are no more threads */
}
```

请注意，健壮的程序不会在多线程程序中使用`signal()`（“在多线程进程中使用 signal()的效果是未指定的。”- 信号手册页）；一个更正确的程序将需要使用`sigaction`。

## 我如何找到更多信息？

阅读手册页：

+   [sem_init](http://man7.org/linux/man-pages/man3/sem_init.3.html)

+   [sem_wait](http://man7.org/linux/man-pages/man3/sem_wait.3.html)

+   [sem_post](http://man7.org/linux/man-pages/man3/sem_post.3.html)

+   [sem_destroy](http://man7.org/linux/man-pages/man3/sem_destroy.3.html)
