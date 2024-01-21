# 同步复习问题

## 主题

+   原子操作

+   临界区

+   生产者消费者问题

+   使用条件变量

+   使用计数信号量

+   实现一个屏障

+   实现环形缓冲区

+   使用 pthread_mutex

+   实现生产者消费者

+   分析多线程代码

## 问题

+   什么是原子操作？

+   为什么以下内容在并行代码中不起作用？

```cpp
//In the global section
size_t a;
//In pthread function
for(int i = 0; i < 100000000; i++) a++;
```

这将会是什么？

```cpp
//In the global section
atomic_size_t a;
//In pthread function
for(int i = 0; i < 100000000; i++) atomic_fetch_add(a, 1);
```

+   原子操作有哪些缺点？哪个更快：保留一个本地变量还是进行多个原子操作？

+   什么是临界区？

+   一旦确定了临界区，保证只有一个线程会进入该区域的一种方法是什么？

+   在这里确定临界区

```cpp
struct linked_list;
struct node;
void add_linked_list(linked_list *ll, void* elem){
    node* packaged = new_node(elem);
    if(ll->head){
         ll->head = 
    }else{
         packaged->next = ll->head;
         ll->head = packaged;
         ll->size++;
    }

}

void* pop_elem(linked_list *ll, size_t index){
    if(index >= ll->size) return NULL;

    node *i, *prev;
    for(i = ll->head; i && index; i = i->next, index--){
        prev = i;
    }

    //i points to the element we need to pop, prev before
    if(prev->next) prev->next = prev->next->next;
    ll->size--;
    void* elem = i->elem;
    destroy_node(i);
    return elem;
}
```

临界区可以有多紧凑？

+   什么是生产者消费者问题？以上述部分如何成为生产者消费者问题？生产者消费者问题与读者写者问题有什么关系？

+   什么是条件变量？为什么使用条件变量比使用“while”循环更有优势？

+   为什么这段代码很危险？

```cpp
if(not_ready){
     pthread_cond_wait(&cv, &mtx);
}
```

+   什么是计数信号量？给我一个类似于饼干罐/比萨盒/有限食物的比喻。

+   什么是线程屏障？

+   使用计数信号量来实现屏障。

+   编写一个生产者/消费者队列，再来一个生产者/消费者栈？

+   给我一个使用条件变量的读者-写者锁的实现，使用你需要的任何结构，它只需要支持以下函数

```cpp
void reader_lock(rw_lock_t* lck);
void writer_lock(rw_lock_t* lck);
void reader_unlock(rw_lock_t* lck);
void writer_unlock(rw_lock_t* lck);
```

唯一的规定是在“reader_lock”和“reader_unlock”之间，没有写者可以写。在写者锁之间，只有一个写者可以一次写作。

+   编写代码使用仅三个计数信号量实现生产者消费者。假设可以有多个线程调用 enqueue 和 dequeue。确定每个信号量的初始值。

+   编写代码使用条件变量和互斥锁实现生产者消费者。假设可以有多个线程调用 enqueue 和 dequeue。

+   使用 CVs 实现 add(unsigned int)和 subtract(unsigned int)阻塞函数，永远不允许全局值大于 100。

+   使用 CVs 为 15 个线程实现一个屏障。

+   以下陈述有多少是真的？

    +   可以有多个活跃的读者

    +   可以有多个活跃的写者

    +   当有活跃的写者时，活跃的读者数量必须为零

    +   如果有活跃的读者，则活跃的写者数量必须为零

    +   一个写者必须等到当前活跃的读者完成

+   待办事项：分析多线程代码片段
