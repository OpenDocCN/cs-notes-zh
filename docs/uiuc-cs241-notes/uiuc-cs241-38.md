# 同步，第八部分：环形缓冲区示例

## 什么是环形缓冲区？

环形缓冲区是一种简单的、通常是固定大小的存储机制，其中连续的内存被视为循环的，并且两个索引计数器跟踪队列的当前开始和结束。由于数组索引不是循环的，所以当移动到数组的末尾时，索引计数器必须回绕到零。当数据被添加（入队）到队列的前端或从队列的尾部移除（出队）时，缓冲区中的当前项目形成一个似乎环绕轨道的列车！一个简单的（单线程）实现如下所示。请注意，enqueue 和 dequeue 没有防止下溢或上溢——当队列已满时可能添加一个项目，当队列为空时可能移除一个项目。例如，如果我们向队列中添加了 20 个整数（1,2,3...），并且没有移除任何项目，那么值`17,18,19,20`将覆盖`1,2,3,4`。我们现在不会解决这个问题，而是在创建多线程版本时，我们将确保在环形缓冲区已满或为空时，enqueue 和 dequeue 线程被阻塞。

```cpp
void *buffer[16];
int in = 0, out = 0;

void enqueue(void *value) { /* Add one item to the front of the queue*/
  buffer[in] = value;
  in++; /* Advance the index for next time */
  if (in == 16) in = 0; /* Wrap around! */
}

void *dequeue() { /* Remove one item to the end of the queue.*/
  void *result = buffer[out];
  out++;
  if (out == 16) out = 0;
  return result;
}
```

## 实现环形缓冲区的注意事项是什么？

很容易写出 enqueue 或 dequeue 方法的以下紧凑形式（N 是缓冲区的容量，例如 16）：

```cpp
void enqueue(void *value)
  b[ (in++) % N ] = value;
}
```

这种方法似乎可以工作（通过简单的测试等），但包含一个微妙的错误。通过足够多的 enqueue 操作（略多于 20 亿次），`in`的 int 值将溢出并变为负数！模运算符`％`保留符号。因此，你可能会写入`b[-14]`，例如！

一个紧凑的形式是正确的使用位掩码，提供 N 是 2^x（16,32,64,...）

```cpp
b[ (in++) & (N-1) ] = value;
```

这个缓冲区还没有防止缓冲区下溢或上溢。为此，我们将转向我们的多线程尝试，它将阻塞一个线程，直到有空间或至少有一个项目可以移除。

## 检查多线程实现的正确性（示例 1）

以下代码是一个不正确的实现。会发生什么？`enqueue`和/或`dequeue`会阻塞吗？互斥性是否得到满足？缓冲区会下溢吗？缓冲区会上溢吗？为了清晰起见，`pthread_mutex`缩写为`p_m`，我们假设 sem_wait 不会被中断。

```cpp
#define N 16
void *b[N]
int in = 0, out = 0
p_m_t lock
sem_t s1,s2
void init() { 
    p_m_init(&lock, NULL)
    sem_init(&s1, 0, 16)
    sem_init(&s2, 0, 0)
}

enqueue(void *value) {
    p_m_lock(&lock)

    // Hint: Wait while zero. Decrement and return
    sem_wait( &s1 ) 

    b[ (in++) & (N-1) ] = value

    // Hint: Increment. Will wake up a waiting thread 
    sem_post(&s1) 
    p_m_unlock(&lock)
}
void *dequeue(){
    p_m_lock(&lock)
    sem_wait(&s2)
    void *result = b[(out++) & (N-1) ]
    sem_post(&s2)
    p_m_unlock(&lock)
    return result
}
```

## 分析

在继续阅读之前，看看你能找到多少错误。然后确定如果线程调用 enqueue 和 dequeue 方法会发生什么。

+   enqueue 方法在同一个信号量（s1）上等待和发布，equeue 也是如此（s2）即我们减少值然后立即增加值，因此在函数结束时，信号量值不变！

+   s1 的初始值为 16，因此信号量永远不会减少到零——如果环形缓冲区已满，enqueue 不会阻塞——因此可能会发生溢出。

+   s2 的初始值为零，因此调用 dequeue 将始终阻塞并且永远不会返回！

+   互斥锁和 sem_wait 的顺序需要交换（但是这个示例是如此破碎，以至于这个错误没有影响！）##检查多线程实现的正确性（示例 1）

以下代码是一个不正确的实现。会发生什么？`enqueue`和/或`dequeue`会阻塞吗？互斥性是否得到满足？缓冲区会下溢吗？缓冲区会上溢吗？为了清晰起见，`pthread_mutex`缩写为`p_m`，我们假设 sem_wait 不会被中断。

```cpp
void *b[16]
int in = 0, out = 0
p_m_t lock
sem_t s1, s2
void init() {
    sem_init(&s1,0,16)
    sem_init(&s2,0,0)
}

enqueue(void *value){

 sem_wait(&s2)
 p_m_lock(&lock)

 b[ (in++) & (N-1) ] = value

 p_m_unlock(&lock)
 sem_post(&s1)
}

void *dequeue(){
  sem_wait(&s1)
  p_m_lock(&lock)
  void *result = b[(out++) & 15]
  p_m_unlock(&lock)
  sem_post(&s2)

  return result;
}
```

### 分析

+   s2 的初始值为 0。因此，在第一次调用 sem_wait 时，enqueue 将阻塞，即使缓冲区为空！

+   s1 的初始值为 16。因此，在第一次调用 sem_wait 时，dequeue 不会阻塞，即使缓冲区为空——糟糕，下溢！dequeue 方法将返回无效数据。

+   该代码不满足互斥性；两个线程可以同时修改 `in` 或 `out`！ 该代码似乎使用了互斥锁。不幸的是，该锁从未使用 `pthread_mutex_init()` 或 `PTHREAD_MUTEX_INITIALIZER` 进行初始化 - 因此该锁可能无效（`pthread_mutex_lock` 可能什么也不做）

## 正确实现环形缓冲区

伪代码（`pthread_mutex` 缩写为 `p_m` 等）如下所示。

由于互斥锁存储在全局（静态）内存中，因此可以使用 `PTHREAD_MUTEX_INITIALIZER` 进行初始化。如果我们在堆上为互斥锁分配了空间，那么我们将使用 `pthread_mutex_init(ptr, NULL)`

```cpp
#include <pthread.h>
#include <semaphore.h>
// N must be 2^i
#define N (16)

void *b[N]
int in = 0, out = 0
p_m_t lock = PTHREAD_MUTEX_INITIALIZER
sem_t countsem, spacesem

void init() {
  sem_init(&countsem, 0, 0)
  sem_init(&spacesem, 0, 16)
}
```

`enqueue` 方法如下所示。请注意：

+   该锁仅在临界区（对数据结构的访问）期间保持。

+   完整的实现需要防止由于 POSIX 信号而导致 `sem_wait` 提前返回。

```cpp
enqueue(void *value){
 // wait if there is no space left:
 sem_wait( &spacesem )

 p_m_lock(&lock)
 b[ (in++) & (N-1) ] = value
 p_m_unlock(&lock)

 // increment the count of the number of items
 sem_post(&countsem)
}
```

`dequeue` 实现如下所示。请注意 `enqueue` 的同步调用的对称性。在两种情况下，如果空间计数或项目计数为零，函数首先会等待。

```cpp
void *dequeue(){
  // Wait if there are no items in the buffer
  sem_wait(&countsem)

  p_m_lock(&lock)
  void *result = b[(out++) & (N-1)]
  p_m_unlock(&lock)

  // Increment the count of the number of spaces
  sem_post(&spacesem)

  return result
}
```

## 思考

+   如果 `pthread_mutex_unlock` 和 `sem_post` 调用的顺序被交换会发生什么？

+   如果 `sem_wait` 和 `pthread_mutex_lock` 调用的顺序被交换会发生什么？
