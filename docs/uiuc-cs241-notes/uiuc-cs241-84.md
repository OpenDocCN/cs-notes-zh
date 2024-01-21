# 多线程编程：复习问题

> 警告 - 问题编号可能会更改

## 问题 1

以下代码是否线程安全？重新设计以下代码以使其线程安全。提示：如果消息内存对每次调用都是唯一的，则互斥锁是不必要的。

```cpp
static char message[20];
pthread_mutex_t mutex = PTHREAD_MUTEX_INITIALIZER;

void format(int v) {
  pthread_mutex_lock(&mutex);
  sprintf(message, ":%d:" ,v);
  pthread_mutex_unlock(&mutex);
  return message;
}
```

## 问题 2

以下哪一个不会导致进程退出？

+   从最后一个运行的线程中返回 pthread 的起始函数。

+   原始线程从主函数返回。

+   任何导致分段错误的线程。

+   任何调用`exit`的线程。

+   在仍有其他线程运行时，在主线程中调用`pthread_exit`。

## 问题 3

为以下程序中将打印的"W"字符的数量写一个数学表达式。假设 a、b、c、d 都是小正整数。您的答案可以使用一个返回其最低值参数的'min'函数。

```cpp
unsigned int a=...,b=...,c=...,d=...;

void* func(void* ptr) {
  char m = * (char*)ptr;
  if(m == 'P') sem_post(s);
  if(m == 'W') sem_wait(s);
  putchar(m);
  return NULL;
}

int main(int argv, char** argc) {
  sem_init(s,0, a);
  while(b--) pthread_create(&tid, NULL, func, "W"); 
  while(c--) pthread_create(&tid, NULL, func, "P"); 
  while(d--) pthread_create(&tid, NULL, func, "W"); 
  pthread_exit(NULL); 
  /*Process will finish when all threads have exited */
}
```

## 问题 4

完成以下代码。以下代码应该交替打印`A`和`B`。它表示两个轮流执行的线程。添加条件变量调用到`func`，以便等待的线程不需要不断检查`turn`变量。问：`pthread_cond_broadcast`是必要的还是`pthread_cond_signal`足够？

```cpp
pthread_cond_t cv = PTHREAD_COND_INITIALIZER;
pthread_mutex_t m = PTHREAD_MUTEX_INITIALIZER;

void* turn;

void* func(void* mesg) {
  while(1) {
// Add mutex lock and condition variable calls ...

    while(turn == mesg) { 
        /* poll again ... Change me - This busy loop burns CPU time! */ 
    }

    /* Do stuff on this thread */
    puts( (char*) mesg);
    turn = mesg;

  }
  return 0;
}

int main(int argc, char** argv){
  pthread_t tid1;
  pthread_create(&tid1, NULL, func, "A");
  func("B"); // no need to create another thread - just use the main thread
  return 0;
}
```

## 问题 5

在给定的代码中标识临界区。添加互斥锁以使代码线程安全。添加条件变量调用，使`total`永远不会变成负数或超过 1000。相反，调用应该阻塞，直到可以安全地继续。解释为什么`pthread_cond_broadcast`是必要的。

```cpp
int total;
void add(int value) {
 if(value < 1) return;
 total += value;
}
void sub(int value) {
 if(value < 1) return;
 total -= value;
}
```

## 问题 6

一个非线程安全的数据结构有`size()` `enq` 和 `deq` 方法。使用条件变量和互斥锁来完成线程安全的、阻塞版本。

```cpp
void enqueue(void* data) {
  // should block if the size() would become greater than 256
  enq(data);
}
void* dequeue() {
  // should block if size() is 0
  return deq();
}
```

## 问题 7

您的创业公司提供使用最新交通信息的路径规划。您过度支付的实习生创建了一个非线程安全的数据结构，其中包含两个函数：`shortest`（使用但不修改图）和`set_edge`（修改图）。

```cpp
graph_t* create_graph(char* filename); // called once

// returns a new heap object that is the shortest path from vertex i to j
path_t* shortest(graph_t* graph, int i, int j); 

// updates edge from vertex i to j
void set_edge(graph_t* graph, int i, int j, double time); 

```

为了性能，多个线程必须能够同时调用`shortest`，但是当没有其他线程在`shortest`或`set_edge`内执行时，图只能被一个线程修改。

使用互斥锁和条件变量来实现读者-写者解决方案。下面显示了一个不完整的尝试。尽管这个尝试是线程安全的（因此足够用于演示日！），但它不允许多个线程同时计算`shortest`路径，并且不具有足够的吞吐量。

```cpp
path_t* shortest_safe(graph_t* graph, int i, int j) {
  pthread_mutex_lock(&m);
  path_t* path = shortest(graph, i, j);
  pthread_mutex_unlock(&m);
  return path;
}
void set_edge_safe(graph_t* graph, int i, int j, double dist) {
  pthread_mutex_lock(&m);
  set_edge(graph, i, j, dist);
  pthread_mutex_unlock(&m);
}
```
