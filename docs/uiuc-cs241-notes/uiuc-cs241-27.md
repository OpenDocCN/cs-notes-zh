# Pthreads，第二部分：实际应用

## 更多的 pthread 函数

## 如何创建一个 pthread？

参见[Pthreads Part 1](https://github.com/angrave/SystemProgramming/wiki/Pthreads,-Part-1:-Introduction)，介绍了 `pthread_create` 和 `pthread_join`

## 如果我调用 `pthread_create` 两次，我的进程会有多少个堆栈？

你的进程将包含三个堆栈 - 每个线程一个。第一个线程在进程启动时创建，然后你创建了另外两个。实际上可能会有更多的堆栈，但现在让我们忽略这个复杂性。重要的想法是每个线程都需要一个堆栈，因为堆栈包含自动变量和旧的 CPU PC 寄存器，以便在函数完成后可以返回执行调用函数。

## 一个完整进程和一个线程之间的区别是什么？

此外，与进程不同，同一进程中的线程可以共享相同的全局内存（数据和堆段）。

## `pthread_cancel` 是做什么的？

停止一个线程。请注意，线程可能不会立即停止。例如，当线程进行操作系统调用（例如 `write`）时，它可以被终止。

在实践中，`pthread_cancel` 很少被使用，因为它不给线程一个机会在自身之后进行清理（例如，它可能已经打开了一些文件）。另一种实现方法是使用一个布尔（int）变量，其值用于通知其他线程它们应该完成并进行清理。

## `exit` 和 `pthread_exit` 之间有什么区别？

`exit(42)` 退出整个进程并设置进程的退出值。这相当于在主方法中返回 42。进程内的所有线程都会停止。

`pthread_exit(void *)` 只会停止调用线程，即调用 `pthread_exit` 后线程永远不会返回。如果没有其他线程在运行，pthread 库将自动完成进程。`pthread_exit(...)` 等同于从线程函数返回；两者都会完成线程，并为线程设置返回值（void *指针）。

在 `main` 线程中调用 `pthread_exit` 是简单程序确保所有线程完成的常见方法。例如，在下面的程序中，`myfunc` 线程可能没有时间开始。

```cpp
int main() {
  pthread_t tid1, tid2;
  pthread_create(&tid1, NULL, myfunc, "Jabberwocky");
  pthread_create(&tid2, NULL, myfunc, "Vorpel");
  exit(42); //or return 42;

  // No code is run after exit
}
```

接下来的两个程序将等待新线程完成-

```cpp
int main() {
  pthread_t tid1, tid2;
  pthread_create(&tid1, NULL, myfunc, "Jabberwocky");
  pthread_create(&tid2, NULL, myfunc, "Vorpel");
  pthread_exit(NULL); 

  // No code is run after pthread_exit
  // However process will continue to exist until both threads have finished
}
```

或者，我们可以在每个线程上进行连接（即等待它完成），然后从主函数返回（或调用 exit）。

```cpp
int main() {
  pthread_t tid1, tid2;
  pthread_create(&tid1, NULL, myfunc, "Jabberwocky");
  pthread_create(&tid2, NULL, myfunc, "Vorpel");
  // wait for both threads to finish :
  void* result;
  pthread_join(tid1, &result);
  pthread_join(tid2, &result); 
  return 42;
}
```

请注意，pthread_exit 版本会创建线程僵尸，但这不是长时间运行的进程，所以我们不在乎。

## 线程如何被终止？

+   从线程函数返回

+   调用 `pthread_exit`

+   使用 `pthread_cancel` 取消线程

+   终止进程（例如 SIGTERM）；exit()；从 `main` 返回

## `pthread_join` 的目的是什么？

+   等待线程完成

+   清理线程资源

+   获取线程的返回值

## 如果不调用 `pthread_join` 会发生什么？

已完成的线程将继续消耗资源。最终，如果创建了足够多的线程，`pthread_create` 将失败。在实践中，这只是长时间运行进程的问题，但对于简单的短暂进程来说并不是问题，因为当进程退出时，所有线程资源都会被自动释放。

## 我应该使用 `pthread_exit` 还是 `pthread_join`？

`pthread_exit` 和 `pthread_join` 都会让其他线程自行完成（即使在主线程中调用）。但是，只有 `pthread_join` 会在指定线程完成时返回。`pthread_exit` 不会等待，它会立即结束线程，并且不会给你继续执行的机会。

## 你能把指针从一个线程传递给另一个线程的堆栈变量吗？

是的。但是你需要非常小心关于堆栈变量的生命周期。

```cpp
pthread_t start_threads() {
  int start = 42;
  pthread_t tid;
  pthread_create(&tid, 0, myfunc, &start); // ERROR!
  return tid;
} 
```

上面的代码是无效的，因为函数`start_threads`很可能会在`myfunc`开始之前返回。该函数传递了`start`的地址，但是当`myfunc`执行时，`start`已经不在作用域内，其地址将被重新用于另一个变量。

以下代码是有效的，因为栈变量的生命周期比后台线程长。

```cpp
void start_threads() {
  int start = 42;
  void *result;
  pthread_t tid;
  pthread_create(&tid, 0, myfunc, &start); // OK - start will be valid!
  pthread_join(tid, &result);
} 
```

## 竞争条件简介

## 我怎样才能创建十个具有不同起始值的线程。

以下代码应该启动十个值为 0,1,2,3,...9 的线程，但运行时打印出`1 7 8 8 8 8 8 8 8 10`！你能看出为什么吗？

```cpp
#include <pthread.h>
void* myfunc(void* ptr) {
    int i = *((int *) ptr);
    printf("%d ", i);
    return NULL;
}

int main() {
    // Each thread gets a different value of i to process
    int i;
    pthread_t tid;
    for(i =0; i < 10; i++) {
        pthread_create(&tid, NULL, myfunc, &i); // ERROR
    }
    pthread_exit(NULL);
}
```

上面的代码存在“竞争条件” - i 的值正在改变。新线程稍后启动（在示例输出中，最后一个线程在循环结束后启动）。

为了克服这种竞争条件，我们将为每个线程提供一个指向其自己数据区域的指针。例如，对于每个线程，我们可能希望存储 id、起始值和输出值：

```cpp
struct T {
  pthread_t id;
  int start;
  char result[100];
};
```

这些可以存储在数组中 -

```cpp
struct T *info = calloc(10 , sizeof(struct T)); // reserve enough bytes for ten T structures 
```

并且每个数组元素都传递给每个线程 -

```cpp
pthread_create(&info[i].id, NULL, func, &info[i]); 
```

## 为什么有些函数（例如 asctime、getenv、strtok、strerror）不是线程安全的？

为了回答这个问题，让我们看一个简单的函数，它也不是“线程安全”的

```cpp
char *to_message(int num) {
    char static result [256];
    if (num < 10) sprintf(result, "%d : blah blah" , num);
    else strcpy(result, "Unknown");
    return result;
}
```

在上面的代码中，结果缓冲区存储在全局内存中。这很好 - 我们不希望返回指向栈上无效地址的指针，但整个内存中只有一个结果缓冲区。如果两个线程同时使用它，那么一个线程将破坏另一个：

| 时间 | 线程 1 | 线程 2 | 注释 |
| --- | --- | --- | --- |
| 1 | `to_m(5)` |  |  |
| 2 |  | `to_m(99)` | 现在两个线程都会看到结果缓冲区中存储的是“未知” |

## 什么是条件变量、信号量、互斥锁？

这些是同步锁，用于防止竞争条件，并确保同一程序中运行的线程之间的正确同步。此外，这些锁在概念上与内核内部使用的原语相同。

## 使用线程而不是分叉进程有什么优势吗？

是的！在线程之间共享信息很容易，因为线程（同一进程的线程）存在于相同的虚拟内存空间中。此外，创建线程比创建（分叉）进程要快得多。

## 使用线程而不是分叉进程有什么缺点吗？

是的！没有隔离！因为线程存在于同一个进程中，一个线程可以访问与其他线程相同的虚拟内存。一个线程可以终止整个进程（例如，尝试读取地址零）。

## 您可以使用多个线程分叉一个进程吗？

是的！但是子进程只有一个线程（这是调用`fork`的线程的克隆）。我们可以将其视为一个简单的例子，后台线程在子进程中从不打印出第二条消息。

```cpp
#include <pthread.h>
#include <stdio.h>
#include <unistd.h>

static pid_t child = -2;

void *sleepnprint(void *arg) {
  printf("%d:%s starting up...\n", getpid(), (char *) arg);

  while (child == -2) {sleep(1);} /* Later we will use condition variables */

  printf("%d:%s finishing...\n",getpid(), (char*)arg);

  return NULL;  
}
int main() {
  pthread_t tid1, tid2;
  pthread_create(&tid1,NULL, sleepnprint, "New Thread One");
  pthread_create(&tid2,NULL, sleepnprint, "New Thread Two");

  child = fork();
  printf("%d:%s\n",getpid(), "fork()ing complete");
  sleep(3);

  printf("%d:%s\n",getpid(), "Main thread finished");

  pthread_exit(NULL);
  return 0; /* Never executes */
}
```

```cpp
8970:New Thread One starting up...
8970:fork()ing complete
8973:fork()ing complete
8970:New Thread Two starting up...
8970:New Thread Two finishing...
8970:New Thread One finishing...
8970:Main thread finished
8973:Main thread finished 
```

实际上，在分叉之前创建线程可能会导致意外错误，因为（如上所示）其他线程在分叉时立即终止。另一个线程可能刚刚锁定了互斥锁（例如通过调用 malloc），并且再也不会解锁。高级用户可能会发现`pthread_atfork`有用，但我们建议您通常尽量避免在分叉之前创建线程，除非您完全了解这种方法的限制和困难。

## 还有其他情况下`fork`可能比创建线程更可取吗。

创建单独的进程很有用

+   当需要更多安全性时（例如，Chrome 浏览器为不同的标签使用不同的进程）

+   在运行现有和完整的程序时，需要一个新进程（例如，启动'gcc'）

+   当您遇到同步原语并且每个进程都在系统中操作某些东西时

## 我怎样才能找到更多信息？

在[man 页面](http://man7.org/linux/man-pages/man3/pthread_create.3.html)中查看完整示例，并在[pthread 参考指南](http://man7.org/linux/man-pages/man7/pthreads.7.html)中查看。另外：[简明的第三方示例代码，解释创建、连接和退出](http://www.thegeekstuff.com/2012/04/terminate-c-thread/)
