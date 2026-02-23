# xv6 操作系统内核：25：休眠锁（Sleeplocks）

![](img/a77f8de350785fd55f92ac3a26cc229a_0.png)

## 概述
在本节课中，我们将学习 xv6 操作系统内核中的休眠锁（Sleep Locks）。我们将了解休眠锁与自旋锁（Spin Locks）的区别，并详细解析休眠锁的数据结构、初始化、获取、释放以及调试功能。休眠锁允许进程在持有锁时进入睡眠状态，适用于需要长时间持有锁的场景。

## 休眠锁与自旋锁的对比
上一节我们介绍了自旋锁，它要求锁的持有时间必须非常短，并且在持有期间不允许进程进入睡眠状态。本节中我们来看看休眠锁，它解决了自旋锁在长时间持有锁时的局限性。

自旋锁有两个主要函数：`acquire` 和 `release`。获取自旋锁的函数会在一个紧密循环中等待锁被释放，这适用于多核系统，因为锁通常很快就会被释放。然而，如果需要在获取锁和释放锁之间等待很长时间，或者需要在此期间调用 `sleep` 函数让进程挂起，自旋锁就不适用了，因为它会占用 CPU 核心进行无意义的循环等待。

休眠锁则允许进程在持有锁时进入睡眠状态。在 xv6 的实现中，休眠锁也有对应的获取和释放函数，分别是 `acquiresleep` 和 `releasesleep`。

## 休眠锁的数据结构
以下是休眠锁的核心数据结构，它包含四个字段：

```c
struct sleeplock {
    uint locked;       // 锁状态：1 表示被持有，0 表示空闲
    struct spinlock lk; // 保护本结构体的自旋锁
    char *name;        // 锁的名称，用于调试
    int pid;           // 持有锁的进程 ID
};
```

*   `locked` 是一个布尔值，表示锁是否被持有。
*   `lk` 是一个自旋锁，用于保护 `locked` 和 `pid` 字段的并发访问。
*   `name` 是锁的名称，仅用于调试。
*   `pid` 记录当前持有锁的进程 ID。

## 休眠锁的函数实现
以下是休眠锁相关函数的实现细节。

### 初始化函数 `initsleeplock`
此函数用于初始化一个休眠锁结构体。

```c
void initsleeplock(struct sleeplock *lk, char *name) {
    initlock(&lk->lk, "sleep lock");
    lk->name = name;
    lk->locked = 0;
    lk->pid = 0;
}
```

它初始化了保护锁的自旋锁 `lk`，设置了锁的名称 `name`，并将锁状态 `locked` 和持有者进程 ID `pid` 清零，表示锁处于未持有状态。

### 获取锁函数 `acquiresleep`
此函数用于获取一个休眠锁。

```c
void acquiresleep(struct sleeplock *lk) {
    acquire(&lk->lk); // 获取保护锁的自旋锁
    while (lk->locked) { // 如果休眠锁已被持有
        sleep(lk, &lk->lk); // 进入睡眠，等待锁被释放
    }
    lk->locked = 1; // 标记锁为已持有
    lk->pid = myproc()->pid; // 记录当前进程 ID
    release(&lk->lk); // 释放保护锁的自旋锁
}
```

1.  首先获取保护休眠锁结构的自旋锁 `lk->lk`。
2.  检查 `locked` 字段。如果锁已被其他进程持有（`locked == 1`），则调用 `sleep` 函数让当前进程进入睡眠状态。`sleep` 函数会原子性地释放自旋锁 `lk->lk` 并使进程睡眠，以避免错过唤醒信号。
3.  当进程被唤醒并重新获得自旋锁后，再次检查 `locked` 字段。如果锁已空闲，则跳出循环。
4.  将 `locked` 设置为 1，并记录当前进程的 ID 到 `pid` 字段。
5.  最后释放保护用的自旋锁 `lk->lk`。

### 释放锁函数 `releasesleep`
此函数用于释放一个休眠锁。

```c
void releasesleep(struct sleeplock *lk) {
    acquire(&lk->lk); // 获取保护锁的自旋锁
    lk->locked = 0; // 标记锁为空闲
    lk->pid = 0; // 清除持有者进程 ID
    wakeup(lk); // 唤醒所有等待此锁的进程
    release(&lk->lk); // 释放保护锁的自旋锁
}
```

1.  获取保护休眠锁结构的自旋锁 `lk->lk`。
2.  将 `locked` 字段设置为 0，表示锁已空闲。
3.  将 `pid` 字段清零。
4.  调用 `wakeup(lk)` 唤醒所有正在等待此休眠锁（通过相同的通道地址 `lk` 标识）的进程。
5.  释放保护用的自旋锁 `lk->lk`。

![](img/a77f8de350785fd55f92ac3a26cc229a_2.png)

### 调试函数 `holdingsleep`
此函数用于检查当前进程是否持有指定的休眠锁，主要用于错误检测。

```c
int holdingsleep(struct sleeplock *lk) {
    int r;
    acquire(&lk->lk); // 获取保护锁的自旋锁
    r = lk->locked && (lk->pid == myproc()->pid);
    release(&lk->lk); // 释放保护锁的自旋锁
    return r;
}
```

1.  获取保护休眠锁结构的自旋锁 `lk->lk`。
2.  检查条件：锁被持有（`locked == 1`）且持有者进程 ID 等于当前进程的 ID。
3.  释放保护用的自旋锁 `lk->lk`。
4.  返回检查结果。如果返回假（0），内核可能会触发 panic 以指示错误。

## 总结
本节课中我们一起学习了 xv6 操作系统内核中的休眠锁。我们了解了休眠锁与自旋锁的关键区别：休眠锁允许进程在持有锁时进入睡眠状态，适用于需要长时间操作的临界区。我们详细分析了休眠锁的数据结构，它包含一个用于内部保护的自旋锁。我们还逐步解析了休眠锁的初始化、获取、释放以及用于调试的检查函数的工作原理。掌握休眠锁是理解 xv6 中涉及长时间等待或 I/O 操作的同步机制的重要一步。