# 同步，第六部分：实现屏障

## 如何等待 N 个线程在继续下一步之前到达某一点？

假设我们想要执行一个多线程计算，它有两个阶段，但我们不想在第一阶段完成之前进入第二阶段。

我们可以使用一种称为**屏障**的同步方法。当一个线程到达屏障时，它将在屏障处等待，直到所有线程到达屏障，然后它们将一起继续。

想象一下，就像和一些朋友一起去远足。你们约定在每个山顶等待彼此（并且你心里记下了你的团队有多少人）。假设你是第一个到达第一个山顶的人。你会在山顶等待你的朋友。他们一个接一个地到达山顶，但直到你的团队中的最后一个人到达之前，没有人会继续前进。一旦他们到达，你们就会一起继续。

Pthreads 有一个实现这一点的函数`pthread_barrier_wait()`。您需要声明一个`pthread_barrier_t`变量，并使用`pthread_barrier_init()`对其进行初始化。`pthread_barrier_init()`将参与屏障的线程数作为参数。[这里有一个例子。](https://github.com/angrave/SystemProgramming/wiki/Sample-program-using-pthread-barriers)

现在让我们实现自己的屏障，并使用它在大型计算中同步所有线程。

```cpp
double data[256][8192]

1 Threads do first calculation (use and change values in data)

2 Barrier! Wait for all threads to finish first calculation before continuing

3 Threads do second calculation (use and change values in data)
```

线程函数有四个主要部分-

```cpp
void *calc(void *arg) {
  /* Do my part of the first calculation */
  /* Am I the last thread to finish? If so wake up all the other threads! */
  /* Otherwise wait until the other threads has finished part one */
  /* Do my part of the second calculation */
}
```

我们的主线程将创建 16 个线程，并将每个计算分成 16 个单独的部分。每个线程将被赋予一个唯一的值（0,1,2,..15），以便它可以处理自己的块。由于(void*)类型可以保存小整数，我们将通过将其转换为 void 指针来传递`i`的值。

```cpp
#define N (16)
double data[256][8192] ;
int main() {
    pthread_t ids[N];
    for(int i = 0; i < N; i++)  
        pthread_create(&ids[i], NULL, calc, (void *) i);
```

请注意，我们永远不会将此指针值解引用为实际的内存位置-我们只会将其直接转换回整数：

```cpp
void *calc(void *ptr) {
// Thread 0 will work on rows 0..15, thread 1 on rows 16..31
  int x, y, start = N * (int) ptr;
  int end = start + N; 
  for(x = start; x < end; x++) for (y = 0; y < 8192; y++) { /* do calc #1 */ }
```

第 1 个计算完成后，我们需要等待较慢的线程（除非我们是最后一个线程！）。因此，跟踪已经到达我们的屏障（也称为“检查点”）的线程数量：

```cpp
// Global: 
int remain = N;

// After calc #1 code:
remain--; // We finished
if (remain ==0) {/*I'm last!  -  Time for everyone to wake up! */ }
else {
  while (remain != 0) { /* spin spin spin*/ }
}
```

然而，上述代码存在竞争条件（两个线程可能尝试递减`remain`），并且循环是一个忙循环。我们可以做得更好！让我们使用条件变量，然后我们将使用广播/信号函数唤醒睡眠的线程。

提醒一下，条件变量类似于一个房子！线程在那里睡觉（`pthread_cond_wait`）。您可以选择唤醒一个线程（`pthread_cond_signal`）或所有线程（`pthread_cond_broadcast`）。如果当前没有线程在等待，那么这两个调用将不起作用。

条件变量版本通常与忙循环不正确的解决方案非常相似-接下来我们将展示。首先，让我们添加一个互斥锁和条件全局变量，不要忘记在`main`中初始化它们...

```cpp
//global variables
pthread_mutex_t m;
pthread_cond_t cv;

main() {
  pthread_mutex_init(&m, NULL);
  pthread_cond_init(&cv, NULL);
```

我们将使用互斥锁来确保只有一个线程在一次修改`remain`。最后到达的线程需要唤醒*所有*睡眠的线程-因此我们将使用`pthread_cond_broadcast(&cv)`而不是`pthread_cond_signal`

```cpp
pthread_mutex_lock(&m);
remain--; 
if (remain ==0) { pthread_cond_broadcast(&cv); }
else {
  while(remain != 0) { pthread_cond_wait(&cv, &m); }
}
pthread_mutex_unlock(&m);
```

当线程进入`pthread_cond_wait`时，它释放互斥锁并进入睡眠状态。在将来的某个时刻，它将被唤醒。一旦我们将线程从睡眠中唤醒，它在返回之前必须等待直到可以锁定互斥锁。请注意，即使一个睡眠的线程提前醒来，它也会检查 while 循环条件并在必要时重新进入等待。

**上述屏障不可重用**这意味着如果我们将其放入任何旧的计算循环中，代码很可能会遇到屏障死锁或线程比一个迭代更快的情况。思考一下如何使上述屏障可重用，这意味着如果多个线程在循环中调用`barrier_wait`，则可以保证它们处于相同的迭代。
