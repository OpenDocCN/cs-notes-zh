# 同步，第四部分：关键部分问题

## 候选解决方案

## 什么是关键部分问题？

如已在[Synchronization, Part 3: Working with Mutexes And Semaphores](/angrave/SystemProgramming/wiki/Synchronization%2C-Part-3%3A-Working-with-Mutexes-And-Semaphores)中讨论的，我们的代码中有一些关键部分只能由一个线程同时执行。我们将这种要求描述为“互斥排他”；只有一个线程（或进程）可以访问共享资源。

在多线程程序中，我们可以使用互斥锁和解锁调用来包装关键部分：

```cpp
pthread_mutex_lock() - one thread allowed at a time! (others will have to wait here)
... Do Critical Section stuff here!
pthread_mutex_unlock() - let other waiting threads continue
```

我们如何实现这些锁定和解锁调用？我们能创建一个保证互斥的算法吗？下面显示了一个不正确的实现，

```cpp
pthread_mutex_lock(p_mutex_t *m)     { while(m->lock) {}; m->lock = 1;}
pthread_mutex_unlock(p_mutex_t *m)   { m->lock = 0; }
```

乍一看，代码似乎是有效的；如果一个线程尝试锁定互斥量，稍后的线程必须等到锁被释放。然而，这种实现*不能满足互斥*。让我们从两个大致同时运行的线程的角度仔细观察这个“实现”。在下表中，时间从上到下依次进行-

| 时间 | 线程 1 | 线程 2 |
| --- | --- | --- |
| 1 | `while(lock) {}` |  |
| 2 |  | `while(lock) {}` |
| 3 | `lock = 1` | `lock = 1` |

哎呀！存在竞争条件。不幸的是，两个线程都检查了锁并读取了一个错误的值，因此能够继续执行。

## 关键部分问题的候选解决方案。

为了简化讨论，我们只考虑两个线程。请注意，这些论点适用于线程和进程，经典的 CS 文献讨论了这些问题，涉及到需要对关键部分或共享资源进行独占访问（即互斥）的两个进程。

提高标志表示线程/进程进入关键部分的意图。

请记住，下面概述的伪代码是较大程序的一部分；线程或进程通常需要在进程的生命周期中多次进入关键部分。因此，想象每个示例都包裹在一个循环中，在循环中线程或进程在其他事务上工作了一段随机时间。

下面描述的候选解决方案有什么问题吗？

```cpp
// Candidate #1
wait until your flag is lowered
raise my flag
// Do Critical Section stuff
lower my flag 
```

答案：候选解决方案＃1 也存在竞争条件，即它不能满足互斥排他，因为两个线程/进程都可以读取对方的标志值（=降低）并继续。

这表明我们应该在检查其他线程的标志之前*提高*标志 - 这是下面的候选解决方案＃2。

```cpp
// Candidate #2
raise my flag
wait until your flag is lowered
// Do Critical Section stuff
lower my flag 
```

候选方案＃2 满足互斥 - 不可能同时有两个线程在关键部分内。然而，这段代码存在死锁问题！假设两个线程希望同时进入关键部分：

| 时间 | 线程 1 | 线程 2 |
| --- | --- | --- |
| 1 | `raise my flag` |  |
| 2 |  | `raise my flag` |

| 3 | `wait...` | `wait...` |

哎呀，现在两个线程/进程都在等待对方降低他们的标志。现在两者都将永远无法进入关键部分！

这表明我们应该使用轮流变量来尝试解决谁应该继续的问题。

## 轮流解决方案

以下候选解决方案＃3 使用轮流变量礼貌地允许一个线程，然后另一个线程继续

```cpp
// Candidate #3
wait until my turn is myid
// Do Critical Section stuff
turn = yourid 
```

候选方案＃3 满足互斥（每个线程或进程都可以独占访问关键部分），但是两个线程/进程必须采取严格的轮流方式来使用关键部分；即它们被迫进入交替的关键部分访问模式。例如，如果线程 1 希望每毫秒读取一个哈希表，但另一个线程每秒写入一个哈希表，那么读取线程必须再等待 999 毫秒才能再次从哈希表中读取。这种“解决方案”是不有效的，因为我们的线程应该能够取得进展并在没有其他线程当前在关键部分时进入关键部分。

## 对关键部分问题的解决方案的期望属性？

在解决关键部分问题中，我们希望的有三个主要的理想属性

+   互斥 - 线程/进程获得独占访问权；其他线程/进程必须等待，直到它退出关键部分。

+   有界等待 - 如果线程/进程必须等待，那么它只能等待有限的时间（不允许无限等待时间！）。有界等待的确切定义是，在给定进程进入之前，任何其他进程可以进入其关键部分的次数有一个上限（非无限）。

+   进度 - 如果没有线程/进程在关键部分内，那么线程/进程应该能够继续进行（取得进展）而无需等待。

在考虑这些想法的基础上，让我们检查另一个候选解决方案，只有在两个线程同时需要访问时才使用基于轮换的标志。

## 轮换和标志解决方案

以下是 CSP 的正确解决方案吗？

```cpp
\\ Candidate #4
raise my flag
if your flag is raised, wait until my turn
// Do Critical Section stuff
turn = yourid
lower my flag 
```

一位教师和另一位 CS 教师最初也是这样认为的！然而，分析这些解决方案是棘手的。甚至关于这个特定主题的同行评审论文中也包含不正确的解决方案！乍一看，它似乎满足互斥、有界等待和进度：基于轮换的标志仅在出现平局时使用（因此允许进度和有界等待），并且似乎满足互斥。然而....也许你可以找到一个反例？

候选#4 失败，因为一个线程不会等到另一个线程降低他们的标志。经过一番思考（或灵感），可以创建以下场景来演示互斥不满足。

想象第一个线程运行这段代码两次（所以轮换标志现在指向第二个线程）。当第一个线程仍然在关键部分内时，第二个线程到达。第二个线程可以立即继续进入关键部分！

| 时间 | 轮换 | 线程#1 | 线程#2 |
| --- | --- | --- | --- |
| 1 | 2 | `raise my flag` |  |
| 2 | 2 | `if your flag is raised, wait until my turn` | `raise my flag` |
| 3 | 2 | `// Do Critical Section stuff` | `if your flag is raised, wait until my turn`（真的！） |
| 4 | 2 | `// Do Critical Section stuff` | `// Do Critical Section stuff` - 糟糕 |

## 有效的解决方案

## Peterson 的解决方案是什么？

Peterson 在 1981 年的一篇两页论文中发表了他的小说和令人惊讶的简单解决方案。下面显示了他算法的一个版本，使用了共享变量`turn`：

```cpp
\\ Candidate #5
raise my flag
turn = your_id
wait until your flag is lowered and turn is yourid
// Do Critical Section stuff
lower my flag 
```

该解决方案满足互斥、有界等待和进度。如果线程#2 将轮换设置为 2 并且当前在关键部分内。线程#1 到达，*将轮换设置回 1*，现在等待直到线程 2 降低标志。

Peterson 原始文章 pdf 的链接：[G. L. Peterson: "关于互斥问题的神话"，信息处理通讯 12(3) 1981, 115–116](http://dl.acm.org/citation.cfm?id=945527)

## Peterson 的解决方案是第一个解决方案吗？

不，Dekkers 算法（1962 年）是第一个可以证明正确的解决方案。以下是该算法的一个版本。

```cpp
raise my flag
while(your flag is raised) :
   if it's your turn to win :
     lower my flag
     wait while your turn
     raise my flag
// Do Critical Section stuff
set your turn to win
lower my flag 
```

请注意，无论循环迭代零次、一次还是多次，进程的标志在关键部分始终被提升。此外，该标志可以被解释为立即意图进入关键部分。只有在另一个进程也提升了标志时，一个进程才会推迟，降低他们的意图标志并等待。

## 我可以只在 C 或汇编中实现 Peterson 的（或 Dekkers）算法吗？

是的 - 通过一点搜索，甚至今天也可以在特定简单的移动处理器上找到它的生产应用：Peterson 的算法用于实现 Tegra 移动处理器的低级 Linux 内核锁（由 Nvidia 的系统级芯片 ARM 处理器和 GPU 核心）[`android.googlesource.com/kernel/tegra.git/+/android-tegra-3.10/arch/arm/mach-tegra/sleep.S#58`](https://android.googlesource.com/kernel/tegra.git/+/android-tegra-3.10/arch/arm/mach-tegra/sleep.S#58)

然而，一般来说，CPU 和 C 编译器可以重新排序 CPU 指令或使用 CPU 核心特定的本地缓存值，如果另一个核心更新共享变量，则这些值可能是过时的。因此，对于大多数平台来说，简单的伪代码到 C 的实现太天真了。你现在可以停止阅读了。

哦... 你决定继续阅读。好吧，这里有龙！别说我们没警告过你。考虑这是一个高级和棘手的话题，但（剧透）有一个美好的结局。

考虑以下代码，

```cpp
while(flag2 ) { /* busy loop - go around again */
```

一个高效的编译器会推断`flag2`变量在循环内部永远不会改变，因此测试可以优化为`while(true)`。使用`volatile`可以在一定程度上防止这种类型的编译器优化。

独立指令可以被优化编译器重新排序，或者在运行时由 CPU 的乱序执行优化重新排序。如果代码需要变量被修改和检查以及精确的顺序，这些复杂的优化。

一个相关的挑战是 CPU 核心包括数据缓存，用于存储最近读取或修改的主内存值。修改后的值可能不会立即写回主内存或重新从内存中读取。因此，数据更改，例如上面示例中的标志和转换变量的状态，可能不会在两个 CPU 核心之间共享。

但是有一个美好的结局。幸运的是，现代硬件使用“内存栅栏”（也称为内存屏障）CPU 指令来解决这些问题，以确保主内存和 CPU 缓存处于合理和一致的状态。更高级别的同步原语，如`pthread_mutex_lock`，将调用这些 CPU 指令作为其实现的一部分。因此，在实践中，使用互斥锁的临界区周围的锁定和解锁调用足以忽略这些低级问题。

进一步阅读：我们建议阅读以下网帖，讨论在 x86 进程上实现 Peterson 算法以及关于内存屏障的 Linux 文档。

[`bartoszmilewski.com/2008/11/05/who-ordered-memory-fences-on-an-x86/`](http://bartoszmilewski.com/2008/11/05/who-ordered-memory-fences-on-an-x86/) [`lxr.free-electrons.com/source/Documentation/memory-barriers.txt`](http://lxr.free-electrons.com/source/Documentation/memory-barriers.txt)

## 硬件解决方案

## 我们如何在硬件上实现临界区问题？

我们可以使用 C11 原子操作来完美地做到这一点！完整的解决方案在这里详细说明（这是一个自旋锁互斥体，[futex](https://locklessinc.com/articles/mutex_cv_futex/)的实现可以在网上找到）。

```cpp
typedef struct mutex_{
    atomic_int_least8_t lock;
    pthread_t owner;
} mutex;

#define UNLOCKED 0
#define LOCKED 1
#define UNASSIGNED_OWNER 0

int mutex_init(mutex* mtx){
    if(!mtx){
        return 0;
    }
    atomic_init(&mtx->lock, UNLOCKED); // Not thread safe the user has to take care of this
    mtx->owner = UNASSIGNED_OWNER;
    return 1;
}
```

这是初始化代码，这里没有什么花哨的。我们将互斥体的状态设置为未锁定，并将所有者设置为已锁定。

```cpp
int mutex_lock(mutex* mtx){
    int_least8_t zero = UNLOCKED;
    while(!atomic_compare_exchange_weak_explicit
            (&mtx->lock, 
             &zero, 
             LOCKED,
             memory_order_relaxed,
             memory_order_relaxed)){
        zero = UNLOCKED;
        sched_yield(); //Use system calls for scheduling speed
    }
    //We have the lock now!!!!
    mtx->owner = pthread_self();
    return 1;
}
```

天啊！这段代码是做什么的？首先，它初始化一个变量，我们将保持为未锁定状态。[原子比较和交换](https://en.wikipedia.org/wiki/Compare-and-swap)是大多数现代架构支持的指令（在 x86 上是`lock cmpxchg`）。这个操作的伪代码看起来像这样

```cpp
int atomic_compare_exchange_pseudo(int* addr1, int* addr2, int val){
    if(*addr1 == *addr2){
        *addr1 = val;
        return 1;
    }else{
        *addr2 = *addr1;
        return 0;
    }
}
```

除了它是*原子*完成的，意味着在一个不可中断的操作中完成。*弱*部分是什么意思？原子指令也容易出现**虚假失败**，这意味着这些原子函数有两个版本，一个*强*和一个*弱*，强保证成功或失败，而弱可能失败。我们使用弱部分是因为弱部分更快，而且我们在一个循环中！这意味着如果它失败得更频繁，我们也没关系，因为我们会继续旋转。

这个内存顺序是什么？我们之前讨论过内存栅栏，这就是它！我们不会详细讨论，因为这超出了本课程的范围，但不超出[本文](https://gcc.gnu.org/wiki/Atomic/GCCMM/AtomicSync)的范围。

在 while 循环内，我们未能获取到锁！我们将零重置为 unlocked 并睡一会儿。当我们醒来时，我们再次尝试获取锁。一旦成功交换，我们就进入了临界区！我们为解锁方法设置了互斥体的所有者，并返回成功。

在使用原子操作时，这如何保证互斥性，我们并不完全确定！但在这个简单的例子中，我们可以，因为能够成功期望锁处于 UNLOCKED（0）状态并将其交换到 LOCKED（1）状态的线程被认为是赢家。我们如何实现解锁？

```cpp
int mutex_unlock(mutex* mtx){
    if(unlikely(pthread_self() != mtx->owner)){
        return 0; //You can't unlock a mutex if you aren't the owner
    }
    int_least8_t one = 1;
    //Critical section ends after this atomic
    mtx->owner = UNASSIGNED_OWNER;
    if(!atomic_compare_exchange_strong_explicit(
                &mtx->lock, 
                &one, 
                UNLOCKED,
                memory_order_relaxed,
                memory_order_relaxed)){
        //The mutex was never locked in the first place
        return 0;
    }
    return 1;
}
```

为了满足 API，除非你是拥有它的人，否则你不能解锁互斥体。然后我们取消互斥体所有者，因为在原子操作之后临界区已经结束。我们希望进行强交换，因为我们不想阻塞（pthread_mutex_unlock 不会阻塞）。我们期望互斥体被锁住，然后将其交换到解锁状态。如果交换成功，我们就解锁了互斥体。如果交换失败，这意味着互斥体是 UNLOCKED，我们试图将其从 UNLOCKED 切换到 UNLOCKED，保持解锁的非阻塞。
