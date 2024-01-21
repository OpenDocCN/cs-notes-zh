# 同步，第一部分：互斥锁

## 解决临界区

## 什么是临界区？

临界区是一段代码，只能由一个线程同时执行，如果程序要正确运行。如果两个线程（或进程）同时在临界区内执行代码，那么可能程序可能不再具有正确的行为。

## 仅仅递增一个变量是否是临界区？

可能。递增变量（`i++`）是通过三个单独的步骤执行的：将内存内容复制到 CPU 寄存器。增加 CPU 中的值。将新值存储在内存中。如果内存位置只能由一个线程访问（例如下面的自动变量`i`），则不可能发生竞争条件，也没有与`i`相关的临界区。但是，`sum`变量是全局变量，并且被两个线程访问。可能两个线程可能同时尝试递增变量。

```cpp
#include <stdio.h>
#include <pthread.h>
// Compile with -pthread

int sum = 0; //shared

void *countgold(void *param) {
    int i; //local to each thread
    for (i = 0; i < 10000000; i++) {
        sum += 1;
    }
    return NULL;
}

int main() {
    pthread_t tid1, tid2;
    pthread_create(&tid1, NULL, countgold, NULL);
    pthread_create(&tid2, NULL, countgold, NULL);

    //Wait for both threads to finish:
    pthread_join(tid1, NULL);
    pthread_join(tid2, NULL);

    printf("ARRRRG sum is %d\n", sum);
    return 0;
}
```

上述代码的典型输出是`ARGGGH sum is 8140268`每次运行程序时都会打印不同的总和，因为存在竞争条件；代码无法阻止两个线程同时读写`sum`。例如，两个线程都将当前的 sum 值复制到运行每个线程的 CPU 中（假设为 123）。两个线程都将其自己的副本增加一。两个线程写回该值（124）。如果线程在不同时间访问了 sum，则计数将为 125。

## 如何确保一次只有一个线程可以访问全局变量？

你的意思是，“帮助 - 我需要一个互斥体！”如果一个线程当前正在临界区内，我们希望另一个线程等到第一个线程完成。为此，我们可以使用互斥体（Mutual Exclusion 的缩写）。

对于简单的示例，我们需要添加的代码最少只有三行：

```cpp
pthread_mutex_t m = PTHREAD_MUTEX_INITIALIZER; // global variable
pthread_mutex_lock(&m); // start of Critical Section
pthread_mutex_unlock(&m); //end of Critical Section
```

一旦我们完成了互斥体，我们还应该调用`pthread_mutex_destroy(&m)`。请注意，您只能销毁未锁定的互斥体。对已销毁的锁调用 destroy，初始化已初始化的锁，锁定已锁定的锁，解锁未锁定的锁等都是不受支持的（至少对于默认的互斥体），通常会导致未定义的行为。

## 如果我锁定了互斥体，是否会阻止所有其他线程？

不，其他线程将继续。只有当一个线程尝试锁定已经锁定的互斥体时，线程才必须等待。一旦原始线程解锁互斥体，第二个（等待的）线程将获取锁并能够继续。

## 还有其他创建互斥体的方法吗？

可以。您可以仅对全局（“静态”）变量使用宏 PTHREAD_MUTEX_INITIALIZER。m = PTHREAD_MUTEX_INITIALIZER 等同于更通用的`pthread_mutex_init(&m,NULL)`。init 版本包括用于在性能和额外错误检查以及高级共享选项之间进行权衡的选项。

```cpp
pthread_mutex_t *lock = malloc(sizeof(pthread_mutex_t)); 
pthread_mutex_init(lock, NULL);
//later
pthread_mutex_destroy(lock);
free(lock);
```

关于“init”和“destroy”需要记住的事情：

+   多个线程的初始化/销毁具有未定义的行为

+   销毁锁定的互斥体具有未定义的行为

+   基本上尝试遵循一个线程初始化一个互斥体，而且只有一个线程初始化一个互斥体的模式。

## 互斥体陷阱

## `所以 pthread_mutex_lock`在其他线程读取相同变量时会停止吗？

不，互斥体不是那么聪明 - 它与代码（线程）一起工作，而不是数据。只有当另一个线程在锁定的互斥体上调用`lock`时，第二个线程才需要等待，直到互斥体被解锁。

考虑

```cpp
int a;
pthread_mutex_t m1 = PTHREAD_MUTEX_INITIALIZER,
                 m2 = = PTHREAD_MUTEX_INITIALIZER;
// later
// Thread 1
pthread_mutex_lock(&m1);
a++;
pthread_mutex_unlock(&m1);

// Thread 2
pthread_mutex_lock(&m2);
a++;
pthread_mutex_unlock(&m2);
```

仍会导致竞争条件。

## 我可以在 fork 之前创建互斥体吗？

是的 - 但是子进程和父进程将不共享虚拟内存，并且每个进程都将拥有独立于其他进程的互斥体。

（高级说明：使用共享内存有高级选项，允许子进程和父进程共享互斥体，如果使用正确的选项并使用共享内存段。请参阅[stackoverflow 示例](http://stackoverflow.com/questions/19172541/procs-fork-and-mutexes)）

## 如果一个线程锁定了一个互斥锁，另一个线程能解锁它吗？

不行。同一个线程必须解锁它。

## 我可以使用两个或更多的互斥锁吗？

是的！事实上，通常每个需要更新的数据结构都有一个锁。

如果你只有一个锁，那么两个线程之间可能会对锁有显著的争用，这是不必要的。例如，如果两个线程正在更新两个不同的计数器，可能不需要使用相同的锁。

然而，简单地创建许多锁是不够的：重要的是能够推理关于临界区的问题，例如，一个线程不能在更新期间读取两个数据结构，而这两个数据结构暂时处于不一致的状态。

## 调用 lock 和 unlock 会有任何开销吗？

调用`pthread_mutex_lock`和`_unlock`会有一些开销；然而这是你为了程序正确运行所付出的代价！

## 最简单的完整示例？

下面显示了一个完整的示例

```cpp
#include <stdio.h>
#include <pthread.h>

// Compile with -pthread
// Create a mutex this ready to be locked!
pthread_mutex_t m = PTHREAD_MUTEX_INITIALIZER;

int sum = 0;

void *countgold(void *param) {
    int i;

    //Same thread that locks the mutex must unlock it
    //Critical section is just 'sum += 1'
    //However locking and unlocking a million times
    //has significant overhead in this simple answer

    pthread_mutex_lock(&m);

    // Other threads that call lock will have to wait until we call unlock

    for (i = 0; i < 10000000; i++) {
    sum += 1;
    }
    pthread_mutex_unlock(&m);
    return NULL;
}

int main() {
    pthread_t tid1, tid2;
    pthread_create(&tid1, NULL, countgold, NULL);
    pthread_create(&tid2, NULL, countgold, NULL);

    //Wait for both threads to finish:
    pthread_join(tid1, NULL);
    pthread_join(tid2, NULL);

    printf("ARRRRG sum is %d\n", sum);
    return 0;
}
```

在上面的代码中，线程在进入计数室之前获取了锁。关键部分只有`sum+=1`，所以下一个版本也是正确的但更慢 -

```cpp
    for (i = 0; i < 10000000; i++) {
        pthread_mutex_lock(&m);
        sum += 1;
        pthread_mutex_unlock(&m);
    }
    return NULL;
}
```

这个过程运行得更慢，因为我们一百万次锁定和解锁互斥锁，这是昂贵的 - 至少与递增一个变量相比是昂贵的。（在这个简单的例子中，我们并不真正需要线程 - 我们可以加两次！）一个更快的多线程示例是使用一个自动（本地）变量添加一百万，然后在计算循环结束后将其添加到共享总数中：

```cpp
    int local = 0;
    for (i = 0; i < 10000000; i++) {
       local += 1;
    }

    pthread_mutex_lock(&m);
    sum += local;
    pthread_mutex_unlock(&m);

    return NULL;
}
```

## 如果我忘记解锁会发生什么？

死锁！我们稍后会谈论死锁，但如果多个线程调用这个循环会有什么问题。

```cpp
while(not_stop){
    //stdin may not be thread safe
    pthread_mutex_lock(&m);
    char *line = getline(...);
    if(rand() % 2) { /* randomly skip lines */
         continue;
    }
    pthread_mutex_unlock(&m);

    process_line(line);
}
```

## 我什么时候可以销毁互斥锁？

你只能销毁一个未锁定的互斥锁

## 我可以将 pthread_mutex_t 复制到新的内存位置吗？

不行，将互斥锁的字节复制到新的内存位置，然后使用副本是*不*支持的。

## 互斥锁的简单实现会是什么样的？

下面显示了一个简单（但不正确！）的建议。`unlock`函数只是解锁互斥锁并返回。lock 函数首先检查锁是否已经被锁定。如果当前已经被锁定，它将继续检查，直到另一个线程解锁互斥锁。

```cpp
// Version 1 (Incorrect!)

void lock(mutex_t *m) {
  while(m->locked) { /*Locked? Nevermind - just loop and check again!*/ }

  m->locked = 1;
}
void unlock(mutex_t *m) {
  m->locked = 0;
}
```

版本 1 使用了“忙等待”（不必要地浪费 CPU 资源），但更严重的问题是：我们有一个竞争条件！

如果两个线程同时调用`lock`，有可能两个线程都会将'm_locked'读取为零。因此，两个线程都会认为它们对锁有独占访问权，然后两个线程都会继续。哎呀！

我们可以尝试通过在循环内调用`pthread_yield()`来减少一点 CPU 开销 - pthread_yield 建议操作系统暂时不使用 CPU，因此 CPU 可能被分配给等待运行的线程。但这并不能解决竞争条件。我们需要一个更好的实现 - 你能想出如何防止竞争条件吗？

## 我怎样才能了解更多？

[玩！](http://cs-education.github.io/sys) 阅读 man page！

+   [pthread_mutex_lock man page](http://linux.die.net/man/3/pthread_mutex_lock)

+   [pthread_mutex_unlock man page](http://linux.die.net/man/3/pthread_mutex_unlock)

+   [pthread_mutex_init man page](http://linux.die.net/man/3/pthread_mutex_init)

+   [pthread_mutex_destroy man page](http://linux.die.net/man/3/pthread_mutex_destroy)
