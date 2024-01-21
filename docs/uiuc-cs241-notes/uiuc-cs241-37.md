# 同步，第七部分：读者写者问题

## 读者写者问题是什么？

想象一下，您有一个键值映射数据结构，被许多线程使用。只要数据结构没有被写入，多个线程应该能够同时查找（读取）值。写者不那么合群-为了避免数据损坏，一次只有一个线程可以修改（`write`）数据结构（此时不能有读者正在读取）。

这是*读者写者问题*的一个例子。也就是说，我们如何有效地同步多个读者和写者，以便多个读者可以一起阅读，但写者可以获得独占访问？

下面显示了一个不正确的尝试（“锁”是`pthread_mutex_lock`的简写）：

## 尝试＃1

```cpp
read() {
  lock(&m)
  // do read stuff
  unlock(&m)
}

```

```cpp
write() {
  lock(&m)
  // do write stuff
  unlock(&m)
}

```

至少我们的第一次尝试不会遭受数据损坏（读者必须在写者写作时等待，反之亦然）！但是读者也必须等待其他读者。所以让我们尝试另一种实现..

## 尝试＃2：

```cpp
read() {
  while(writing) {/*spin*/}
  reading = 1
  // do read stuff
  reading = 0
}

```

```cpp
write() {
  while(reading &#124;&#124; writing) {/*spin*/}
  writing = 1
  // do write stuff
  writing = 0
}

```

我们的第二次尝试遭受了竞争条件的影响-想象一下，如果两个线程同时调用`read`和`write`（或同时调用 write）。两个线程都将能够继续进行！其次，我们可以有多个读者和多个写者，因此让我们跟踪读者或写者的总数。这就是我们尝试＃3，

## 尝试＃3

请记住，`pthread_cond_wait`执行*三*个动作。首先，它会原子解锁互斥锁，然后休眠（直到被`pthread_cond_signal`或`pthread_cond_broadcast`唤醒）。第三，唤醒的线程必须在返回之前重新获取互斥锁。因此，只有一个线程实际上可以在由 lock 和 unlock()方法定义的临界区域内运行。

下面的实现＃3 确保如果有任何写者在写作，读者将进入 cond_wait。

```cpp
read() {
    lock(&m)
    while (writing)
        cond_wait(&cv, &m)
    reading++;

/* Read here! */

    reading--
    cond_signal(&cv)
    unlock(&m)
}
```

但是因为候选＃3 在读取之前没有解锁互斥锁，所以一次只能有一个读者读取。更好的版本在读取之前解锁：

```cpp
read() {
    lock(&m);
    while (writing)
        cond_wait(&cv, &m)
    reading++;
    unlock(&m)
/* Read here! */
    lock(&m)
    reading--
    cond_signal(&cv)
    unlock(&m)
}
```

这是否意味着写者和读者可以同时读和写？不！首先，记住 cond_wait 要求线程在返回之前重新获取互斥锁。因此，只有一个线程可以在临界区域（用**标记）内执行代码！

```cpp
read() {
    lock(&m);
**  while (writing)
**      cond_wait(&cv, &m)
**  reading++;
    unlock(&m)
/* Read here! */
    lock(&m)
**  reading--
**  cond_signal(&cv)
    unlock(&m)
}
```

写者必须等待所有人。互斥由锁来保证。

```cpp
write() {
    lock(&m);
**  while (reading || writing)
**      cond_wait(&cv, &m);
**  writing++;
**
** /* Write here! */
**  writing--;
**  cond_signal(&cv);
    unlock(&m);
}
```

上述候选＃3 还使用`pthread_cond_signal`；这只会唤醒一个线程。例如，如果许多读者正在等待写者完成，那么只有一个正在睡眠的读者将被唤醒。读者和写者应该使用`cond_broadcast`，以便所有线程都应该唤醒并检查它们的 while 循环条件。

## 饥饿的写者

上述候选＃3 遭受饥饿。如果读者不断到来，那么写者将永远无法继续进行（“读取”计数永远不会减少到零）。这被称为*饥饿*，并且在重负载下会被发现。我们的修复方法是为写者实现有界等待。如果写者到达，他们仍然需要等待现有的读者，但是未来的读者必须被放置在“等待区”中等待写者完成。可以使用变量和条件变量来实现“等待区”（以便我们可以在写者完成后唤醒线程）。

我们的计划是，当写者到达并在等待当前读者完成之前，注册我们的写入意图（通过增加计数器'writer'）。下面是草图-

```cpp
write() {
    lock()
    writer++

    while (reading || writing)
    cond_wait
    unlock()
  ...
}
```

并且当写者为非零时，传入的读者将不被允许继续。请注意，“写者”表示写者已到达，而“读取”和“写入”计数器表示有*活动*读者或写者。

```cpp
read() {
    lock()
    // readers that arrive *after* the writer arrived will have to wait here!
    while(writer)
    cond_wait(&cv,&m)

    // readers that arrive while there is an active writer
    // will also wait.
    while (writing) 
        cond_wait(&cv,&m)
    reading++
    unlock
  ...
}
```

## 尝试＃4

以下是我们对读者-写者问题的第一个工作解决方案。请注意，如果你继续阅读关于“读者写者问题”的内容，你会发现我们通过给予写者对锁的优先访问来解决了“第二个读者写者问题”。这个解决方案并不是最佳的。然而，它满足了我们最初的问题（N 个活跃读者，单个活跃写者，避免了如果有持续的读者流的话写者饥饿）。

你能识别出任何改进吗？例如，你会如何改进代码，以便我们只唤醒读者或一个写者？

```cpp
int writers; // Number writer threads that want to enter the critical section (some or all of these may be blocked)
int writing; // Number of threads that are actually writing inside the C.S. (can only be zero or one)
int reading; // Number of threads that are actually reading inside the C.S.
// if writing !=0 then reading must be zero (and vice versa)

reader() {
    lock(&m)
    while (writers)
        cond_wait(&turn, &m)
    // No need to wait while(writing here) because we can only exit the above loop
    // when writing is zero
    reading++
    unlock(&m)

  // perform reading here

    lock(&m)
    reading--
    cond_broadcast(&turn)
    unlock(&m)
}

writer() {
    lock(&m)  
    writers++  
    while (reading || writing)   
        cond_wait(&turn, &m)  
    writing++  
    unlock(&m)  
    // perform writing here 
    lock(&m)  
    writing--  
    writers--  
    cond_broadcast(&turn)  
    unlock(&m)  
}
```
