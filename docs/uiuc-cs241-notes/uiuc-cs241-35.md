# 同步，第五部分：条件变量

## 条件变量简介

## 热身

给这些属性命名！

+   "一次只有一个进程（/线程）可以进入 CS"

+   "如果等待，那么另一个进程只能进入 CS 有限次数"

+   "如果没有其他进程在 CS 中，那么进程可以立即进入 CS"

参见[Synchronization, Part 4: The Critical Section Problem](/angrave/SystemProgramming/wiki/Synchronization%2C-Part-4%3A-The-Critical-Section-Problem)获取答案。

## 什么是条件变量？如何使用它们？什么是虚假唤醒？

+   条件变量允许一组线程睡眠，直到被唤醒！您可以唤醒一个线程或所有正在睡眠的线程。如果只唤醒一个线程，那么操作系统将决定唤醒哪个线程。您不直接唤醒线程，而是'信号'条件变量，然后将唤醒一个（或所有）正在条件变量内睡眠的线程。

+   条件变量与互斥锁和循环一起使用（用于检查条件）。

+   偶尔，一个等待的线程可能会出现无缘无故地唤醒（这称为*虚假唤醒*）！这不是问题，因为您总是在循环内使用`wait`，该循环测试必须为真才能继续。

+   在条件变量中睡眠的线程通过调用`pthread_cond_broadcast`（唤醒所有）或`pthread_cond_signal`（唤醒一个）来唤醒。请注意，尽管函数名中有"signal"，但这与 POSIX 的`signal`无关！

## `pthread_cond_wait`做什么？

调用`pthread_cond_wait`执行三个动作：

+   解锁互斥锁

+   等待（睡眠，直到在同一条件变量上调用`pthread_cond_signal`）

+   在返回之前，锁定互斥锁

## （高级话题）为什么条件变量也需要互斥锁？

条件变量需要互斥锁有三个原因。最容易理解的是，它可以防止早期唤醒消息（`signal`或`broadcast`函数）被“丢失”。想象一下以下事件序列（时间向下运行页面），其中条件在调用`pthread_cond_wait`之前 _ 刚好 _ 满足。在这个例子中，唤醒信号丢失了！

| 线程 1 | 线程 2 |
| --- | --- |
| `while( answer < 42) {` |  |
|  | `answer++` |
|  | `p_cond_signal(cv)` |
| `p_cond_wait(cv,m)` |  |

如果两个线程都锁定了互斥锁，则在调用`pthread_cond_wait(cv, m)`之后（然后在内部解锁互斥锁）之后才能发送信号

第二个常见的原因是，更新程序状态（`answer`变量）通常需要互斥锁 - 例如，多个线程可能正在更新`answer`的值。

第三个微妙的原因是满足实时调度的考虑，我们在这里只概述：在时间关键的应用程序中，等待的线程应该允许具有*最高优先级*的线程先继续。为了满足这个要求，调用`pthread_cond_signal`或`pthread_cond_broadcast`之前也必须锁定互斥锁。对于好奇的人，可以在[这里](https://groups.google.com/forum/?hl=ky#!msg/comp.programming.threads/wEUgPq541v8/ZByyyS8acqMJ)找到更长的历史讨论。

## 为什么会存在虚假唤醒？

出于性能考虑。在多 CPU 系统上，可能会发生竞争条件，导致唤醒（信号）请求被忽略。内核可能不会检测到这个丢失的唤醒调用，但可以检测到可能发生的情况。为了避免潜在的丢失信号，唤醒线程以便程序代码可以再次测试条件。

## 例子

条件变量*总是*与互斥锁一起使用。

在调用*wait*之前，必须锁定互斥锁，并且*wait*必须用循环包装。

```cpp
pthread_cond_t cv;
pthread_mutex_t m;
int count;

// Initialize
pthread_cond_init(&cv, NULL);
pthread_mutex_init(&m, NULL);
count = 0;

pthread_mutex_lock(&m);
while (count < 10) {
   pthread_cond_wait(&cv, &m); 
/* Remember that cond_wait unlocks the mutex before blocking (waiting)! */
/* After unlocking, other threads can claim the mutex. */
/* When this thread is later woken it will */
/* re-lock the mutex before returning */
}
pthread_mutex_unlock(&m);

//later clean up with pthread_cond_destroy(&cv); and mutex_destroy 

// In another thread increment count:
while (1) {
  pthread_mutex_lock(&m);
  count++;
  pthread_cond_signal(&cv);
  /* Even though the other thread is woken up it cannot not return */
  /* from pthread_cond_wait until we have unlocked the mutex. This is */
  /* a good thing! In fact, it is usually the best practice to call */
  /* cond_signal or cond_broadcast before unlocking the mutex */
  pthread_mutex_unlock(&m);
}
```

## 实现计数信号量

+   我们可以使用条件变量实现计数信号量。

+   每个信号量都需要一个计数、一个条件变量和一个互斥锁

```cpp
typedef struct sem_t {
  int count; 
  pthread_mutex_t m;
  pthread_condition_t cv;
} sem_t;
```

实现`sem_init`以初始化互斥锁和条件变量

```cpp
int sem_init(sem_t *s, int pshared, int value) {
  if (pshared) { errno = ENOSYS /* 'Not implemented'*/; return -1;}

  s->count = value;
  pthread_mutex_init(&s->m, NULL);
  pthread_cond_init(&s->cv, NULL);
  return 0;
}
```

我们的`sem_post`实现需要增加计数。我们还将唤醒任何在条件变量内睡眠的线程。请注意，我们锁定并解锁互斥锁，因此一次只有一个线程可以在临界区内。

```cpp
sem_post(sem_t *s) {
  pthread_mutex_lock(&s->m);
  s->count++;
  pthread_cond_signal(&s->cv); /* See note */
  /* A woken thread must acquire the lock, so it will also have to wait until we call unlock*/

  pthread_mutex_unlock(&s->m);
}
```

我们的`sem_wait`实现可能需要睡眠，如果信号量的计数为零。就像`sem_post`一样，我们使用锁来包装临界区（这样一次只有一个线程可以执行我们的代码）。请注意，如果线程确实需要等待，那么互斥锁将被解锁，允许另一个线程进入`sem_post`并唤醒我们的睡眠！

请注意，即使线程被唤醒，在从`pthread_cond_wait`返回之前，它必须重新获取锁，因此它将不得不等待一小段时间（例如，直到`sem_post`完成）。

```cpp
sem_wait(sem_t *s) {
  pthread_mutex_lock(&s->m);
  while (s->count == 0) {
      pthread_cond_wait(&s->cv, &s->m); /*unlock mutex, wait, relock mutex*/
  }
  s->count--;
  pthread_mutex_unlock(&s->m);
}
```

**等待`sem_post`不断调用`pthread_cond_signal`会不会破坏`sem_wait`？** 答案：不会！在计数非零之前，我们无法跳出循环。实际上，这意味着`sem_post`即使没有等待的线程，也会不必要地调用`pthread_cond_signal`。更高效的实现只会在必要时调用`pthread_cond_signal`，即：

```cpp
  /* Did we increment from zero to one- time to signal a thread sleeping inside sem_post */
  if (s->count == 1) /* Wake up one waiting thread!*/
     pthread_cond_signal(&s->cv);
```

## 其他信号量考虑

+   真正的信号量实现包括队列和调度问题，以确保公平性和优先级，例如唤醒最高优先级的最长睡眠线程。

+   另外，`sem_init`的高级用法允许信号量在进程之间共享。我们的实现仅适用于同一进程内的线程。
