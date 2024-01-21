# 同步，第三部分：使用互斥锁和信号量

## 线程安全的堆栈

## 什么是原子操作？

用维基百科的话来说，

> 如果一个操作（或一组操作）在系统的其他部分看起来是瞬间发生的，那么它就是原子的或不可中断的。没有锁，只有简单的 CPU 指令（“从内存中读取这个字节”）是原子的（不可分割的）。在单 CPU 系统中，可以暂时禁用中断（这样一系列操作就不能被中断），但实际上原子性是通过使用同步原语来实现的，通常是互斥锁。

递增变量（`i++`）*不*是原子的，因为它需要三个不同的步骤：将位模式从内存复制到 CPU；使用 CPU 的寄存器进行计算；将位模式复制回内存。在这个递增序列期间，另一个线程或进程仍然可以读取旧值，并且当递增序列完成时，对同一内存的其他写入也会被覆盖。

## 我如何使用互斥锁使我的数据结构线程安全？

请注意，这只是一个介绍 - 编写高性能的线程安全数据结构需要自己的书！这是一个简单的数据结构（堆栈），它不是线程安全的：

```cpp
// A simple fixed-sized stack (version 1)
#define STACK_SIZE 20
int count;
double values[STACK_SIZE];

void push(double v) { 
    values[count++] = v; 
}

double pop() {
    return values[--count];
}

int is_empty() {
    return count == 0;
}
```

堆栈的版本 1 不是线程安全的，因为如果两个线程同时调用 push 或 pop，那么结果或堆栈可能是不一致的。例如，想象一下，如果两个线程同时调用 pop，那么两个线程可能读取相同的值，两个线程可能读取原始计数值。

要将其转换为线程安全的数据结构，我们需要确定我们代码的*关键部分*，即哪些部分的代码必须一次只有一个线程。在上面的例子中，`push`，`pop`和`is_empty`函数访问相同的变量（即内存），并且堆栈的所有关键部分。

当`push`（和`pop`）正在执行时，数据结构处于不一致状态（例如计数可能尚未写入，因此可能仍然包含原始值）。通过用互斥锁包装这些方法，我们可以确保一次只有一个线程可以更新（或读取）堆栈。

以下是一个候选的“解决方案”。它正确吗？如果不是，它将如何失败？

```cpp
// An attempt at a thread-safe stack (version 2)
#define STACK_SIZE 20
int count;
double values[STACK_SIZE];

pthread_mutex_t m1 = PTHREAD_MUTEX_INITIALIZER;
pthread_mutex_t m2 = PTHREAD_MUTEX_INITIALIZER;

void push(double v) { 
    pthread_mutex_lock(&m1);
    values[count++] = v;
    pthread_mutex_unlock(&m1);
}

double pop() {
    pthread_mutex_lock(&m2);
    double v = values[--count];
    pthread_mutex_unlock(&m2);

    return v;
}

int is_empty() {
    pthread_mutex_lock(&m1);
    return count == 0;
    pthread_mutex_unlock(&m1);
}

```

上面的代码（“版本 2”）至少包含一个错误。花点时间看看你能不能找到错误，并弄清楚后果。

如果三个线程同时调用`push()`，锁`m1`确保只有一个线程在操作堆栈（两个线程将需要等待，直到第一个线程完成（调用解锁），然后第二个线程将被允许继续进入临界区，最后第三个线程将在第二个线程完成后被允许继续）。

类似的论点也适用于并发调用（同时调用）`pop`。然而，版本 2 不会阻止`push`和`pop`同时运行，因为`push`和`pop`使用两个不同的互斥锁。

在这种情况下，修复很简单 - 对 push 和 pop 函数都使用相同的互斥锁。

代码还有第二个错误；`is_empty`在比较后返回，不会解锁互斥锁。然而，错误不会立即被发现。例如，假设一个线程调用`is_empty`，稍后第二个线程调用`push`。这个线程会神秘地停止。使用调试器，你可以发现线程在`push`方法内的 lock()方法处被卡住，因为之前的`is_empty`调用没有解锁。因此，一个线程的疏忽导致了任意其他线程在以后的时间出现问题。

以下是更好的版本 -

```cpp
// An attempt at a thread-safe stack (version 3)
int count;
double values[count];
pthread_mutex_t m = PTHREAD_MUTEX_INITIALIZER;

void push(double v) { 
  pthread_mutex_lock(&m); 
  values[count++] = v;
  pthread_mutex_unlock(&m);
}
double pop() {
  pthread_mutex_lock(&m);
  double v = values[--count];
  pthread_mutex_unlock(&m);
  return v;
}
int is_empty() {
  pthread_mutex_lock(&m);
  int result= count == 0;
  pthread_mutex_unlock(&m);
  return result;
}
```

版本 3 是线程安全的（我们已经确保了所有关键部分的互斥），但有两点需要注意：

+   `is_empty`是线程安全的，但它的结果可能已经过时，即在线程得到结果时，堆栈可能不再为空！

+   没有保护免受下溢（在空堆栈上弹出）或上溢（在已满堆栈上推入）

后一点可以使用计数信号量来修复。

该实现假定为单个堆栈。更通用的版本可能会将互斥锁作为内存结构的一部分，并使用 pthread_mutex_init 来初始化互斥锁。例如，

```cpp
// Support for multiple stacks (each one has a mutex)
typedef struct stack {
  int count;
  pthread_mutex_t m; 
  double *values;
} stack_t;

stack_t* stack_create(int capacity) {
  stack_t *result = malloc(sizeof(stack_t));
  result->count = 0;
  result->values = malloc(sizeof(double) * capacity);
  pthread_mutex_init(&result->m, NULL);
  return result;
}
void stack_destroy(stack_t *s) {
  free(s->values);
  pthread_mutex_destroy(&s->m);
  free(s);
}
// Warning no underflow or overflow checks!

void push(stack_t *s, double v) { 
  pthread_mutex_lock(&s->m); 
  s->values[(s->count)++] = v; 
  pthread_mutex_unlock(&s->m); }

double pop(stack_t *s) { 
  pthread_mutex_lock(&s->m); 
  double v = s->values[--(s->count)]; 
  pthread_mutex_unlock(&s->m); 
  return v;
}

int is_empty(stack_t *s) { 
  pthread_mutex_lock(&s->m); 
  int result = s->count == 0; 
  pthread_mutex_unlock(&s->m);
  return result;
}
```

示例用法：

```cpp
int main() {
    stack_t *s1 = stack_create(10 /* Max capacity*/);
    stack_t *s2 = stack_create(10);
    push(s1, 3.141);
    push(s2, pop(s1));
    stack_destroy(s2);
    stack_destroy(s1);
}
```

## 堆栈信号量

## 如果堆栈为空或已满，我如何强制我的线程等待？

使用计数信号量！使用计数信号量来跟踪剩余空间的数量，另一个信号量来跟踪堆栈中项目的数量。我们将称这两个信号量为'sremain'和'sitems'。记住，`sem_wait`会在信号量的计数被另一个线程调用`sem_post`减少到零时等待。

```cpp
// Sketch #1

sem_t sitems;
sem_t sremain;
void stack_init(){
  sem_init(&sitems, 0, 0);
  sem_init(&sremain, 0, 10);
}

double pop() {
  // Wait until there's at least one item
  sem_wait(&sitems);
  ...

void push(double v) {
  // Wait until there's at least one space
  sem_wait(&sremain);
  ...
```

草图＃2 已经实现了太早的`post`。在 push 中等待的另一个线程可能会错误地尝试写入一个已满的堆栈（同样，等待 pop()的线程可能会过早地继续）。

```cpp
// Sketch #2 (Error!)
double pop() {
  // Wait until there's at least one item
  sem_wait(&sitems);
  sem_post(&sremain); // error! wakes up pushing() thread too early
  return values[--count];
}
void push(double v) {
  // Wait until there's at least one space
  sem_wait(&sremain);
  sem_post(&sitems); // error! wakes up a popping() thread too early
  values[count++] = v;
}
```

草图 3 实现了正确的信号量逻辑，但你能发现错误吗？

```cpp
// Sketch #3 (Error!)
double pop() {
  // Wait until there's at least one item
  sem_wait(&sitems);
  double v= values[--count];
  sem_post(&sremain);
  return v;
}

void push(double v) {
  // Wait until there's at least one space
  sem_wait(&sremain);
  values[count++] = v;
  sem_post(&sitems); 
}
```

草图 3 正确地使用信号量强制执行了缓冲区满和缓冲区空的条件。然而，没有*互斥*：两个线程可以同时处于*临界区*，这将破坏数据结构（或至少导致数据丢失）。修复方法是在临界区周围包装一个互斥锁：

```cpp
// Simple single stack - see above example on how to convert this into a multiple stacks.
// Also a robust POSIX implementation would check for EINTR and error codes of sem_wait.

// PTHREAD_MUTEX_INITIALIZER for statics (use pthread_mutex_init() for stack/heap memory)

pthread_mutex_t m= PTHREAD_MUTEX_INITIALIZER; 
int count = 0;
double values[10];
sem_t sitems, sremain;

void init() {
  sem_init(&sitems, 0, 0);
  sem_init(&sremains, 0, 10); // 10 spaces
}

double pop() {
  // Wait until there's at least one item
  sem_wait(&sitems);

  pthread_mutex_lock(&m); // CRITICAL SECTION
  double v= values[--count];
  pthread_mutex_unlock(&m);

  sem_post(&sremain); // Hey world, there's at least one space
  return v;
}

void push(double v) {
  // Wait until there's at least one space
  sem_wait(&sremain);

  pthread_mutex_lock(&m); // CRITICAL SECTION
  values[count++] = v;
  pthread_mutex_unlock(&m);

  sem_post(&sitems); // Hey world, there's at least one item
}
// Note a robust solution will need to check sem_wait's result for EINTR (more about this later)
```

## 常见的互斥锁陷阱是什么？

+   由于愚蠢的拼写错误而锁定/解锁错误的互斥锁

+   未解锁互斥锁（由于在错误条件下提前返回）

+   资源泄漏（未调用`pthread_mutex_destroy`）

+   使用未初始化的互斥锁（或使用已被销毁的互斥锁）

+   在线程上两次锁定互斥锁（未首先解锁）

+   死锁和优先级反转（我们稍后会讨论这些）
