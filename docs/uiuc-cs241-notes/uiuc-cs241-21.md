# 内存，第一部分：堆内存介绍

## C 动态内存分配

## 当我调用 malloc 时会发生什么？

函数`malloc`是一个 C 库调用，用于保留一块连续的内存。与堆栈内存不同，内存保持分配状态，直到使用相同指针调用`free`。还有`calloc`和`realloc`，下面将讨论它们。

## malloc 可能失败吗？

如果`malloc`无法保留更多内存，则返回`NULL`。健壮的程序应该检查返回值。如果您的代码假设`malloc`成功，但实际上没有成功，那么当它尝试写入地址 0 时，您的程序很可能会崩溃（段错误）。

## 堆在哪里，有多大？

堆是进程内存的一部分，它没有固定的大小。当您调用`malloc`（`calloc`，`realloc`）和`free`时，C 库将执行堆内存分配。

首先快速回顾一下进程内存：进程是程序的运行实例。每个进程都有自己的地址空间。例如，在 32 位机器上，您的进程大约有 40 亿个地址可供使用，但并非所有这些地址都是有效的，甚至映射到实际的物理内存（RAM）。在进程的内存中，您将找到可执行代码、堆栈空间、环境变量、全局（静态）变量和堆。

通过调用`sbrk`，C 库可以根据程序对堆内存的需求增加堆的大小。由于堆和堆栈（每个线程一个）需要增长，我们将它们放在地址空间的相对两端。因此，对于典型的架构，堆将向上增长，堆栈向下增长。

真相：现代操作系统内存分配器不再需要`sbrk`-相反，它们可以请求独立的虚拟内存区域并维护多个内存区域。例如，大量请求可以放置在与小分配请求不同的内存区域中。但是，这个细节是一个不需要的复杂性：碎片化和有效分配内存的问题仍然存在，因此我们将忽略这个实现细节，并将其写成堆是一个单一区域的样子。

如果我们编写一个多线程程序（稍后会详细介绍），我们将需要多个堆栈（每个线程一个），但只有一个堆。

在典型的架构中，堆是`数据段`的一部分，它从代码和全局变量的上方开始。

## 程序需要调用 brk 或 sbrk 吗？

通常不需要（尽管调用`sbrk(0)`可能会很有趣，因为它告诉您堆当前的结束位置）。相反，程序使用`malloc，calloc，realloc`和`free`，它们是 C 库的一部分。当需要额外的堆内存时，这些函数的内部实现将调用`sbrk`。

```cpp
void *top_of_heap = sbrk(0);
malloc(16384);
void *top_of_heap2 = sbrk(0);
printf("The top of heap went from %p to %p \n", top_of_heap, top_of_heap2);
```

示例输出：`堆的顶部从 0x4000 到 0xa000`

## 什么是 calloc？

与`malloc`不同，`calloc`将内存内容初始化为零，并且还接受两个参数（项目的数量和每个项目的字节大小）。一个朴素但可读的`calloc`实现如下：

```cpp
void *calloc(size_t n, size_t size)
{
    size_t total = n * size; // Does not check for overflow!
    void *result = malloc(total);

    if (!result) return NULL;

// If we're using new memory pages 
// just allocated from the system by calling sbrk
// then they will be zero so zero-ing out is unnecessary,

    memset(result, 0, total);
    return result; 
}
```

有关这些限制的高级讨论在[这里](http://locklessinc.com/articles/calloc/)。

程序员通常使用`calloc`而不是在`malloc`后显式调用`memset`，以将内存内容设置为零。请注意，`calloc(x,y)`与`calloc(y,x)`相同，但您应该遵循手册的约定。

```cpp
// Ensure our memory is initialized to zero
link_t *link  = malloc(256);
memset(link, 0, 256); // Assumes malloc returned a valid address!

link_t *link = calloc(1, 256); // safer: calloc(1, sizeof(link_t));
```

## 为什么 sbrk 首次返回的内存初始化为零？

如果操作系统没有清零物理 RAM 的内容，可能会导致一个进程了解到先前使用过该内存的另一个进程的内存。这将是一个安全漏洞。

不幸的是，这意味着对于在释放任何内存之前进行的`malloc`请求和简单程序（最终使用系统中新保留的内存）来说，内存通常是零。然后程序员错误地编写了假设 malloc'd 内存将*始终*为零的 C 程序。

```cpp
char* ptr = malloc(300);
// contents is probably zero because we get brand new memory
// so beginner programs appear to work!
// strcpy(ptr, "Some data"); // work with the data
free(ptr);
// later
char *ptr2 = malloc(308); // Contents might now contain existing data and is probably not zero
```

## 为什么 malloc 不总是将内存初始化为零？

性能！我们希望 malloc 尽可能快。清零内存可能是不必要的。

## realloc 是什么，什么时候会用到它？

`realloc`允许你调整之前通过 malloc、calloc 或 realloc 在堆上分配的现有内存分配的大小。realloc 最常见的用途是调整用于保存值数组的内存。下面建议一个朴素但可读的 realloc 版本

```cpp
void * realloc(void * ptr, size_t newsize) {
  // Simple implementation always reserves more memory
  // and has no error checking
  void *result = malloc(newsize); 
  size_t oldsize =  ... //(depends on allocator's internal data structure)
  if (ptr) memcpy(result, ptr, newsize < oldsize ? newsize : oldsize);
  free(ptr);
  return result;
}
```

下面显示了 realloc 的错误用法：

```cpp
int *array = malloc(sizeof(int) * 2);
array[0] = 10; array[1] = 20;
// Ooops need a bigger array - so use realloc..
realloc (array, 3); // ERRORS!
array[2] = 30; 
```

上面的代码包含两个错误。首先，我们需要 3*sizeof(int)字节，而不是 3 字节。其次，realloc 可能需要将内存的现有内容移动到新位置。例如，可能没有足够的空间，因为相邻的字节已经被分配。下面显示了 realloc 的正确用法。

```cpp
array = realloc(array, 3 * sizeof(int));
// If array is copied to a new location then old allocation will be freed.
```

一个健壮的版本还会检查`NULL`返回值。注意`realloc`可以用来增加和缩小分配。

## 我在哪里可以读到更多信息？

参见[man 页面](http://man7.org/linux/man-pages/man3/malloc.3.html)！

## 内存分配的速度有多重要？

非常重要！在大多数应用程序中，分配和释放堆内存是常见操作。

## 分配简介

## 最愚蠢的 malloc 和 free 实现是什么，有什么问题？

```cpp
void* malloc(size_t size)
// Ask the system for more bytes by extending the heap space. 
// sbrk Returns -1 on failure
   void *p = sbrk(size); 
   if(p == (void *) -1) return NULL; // No space left
   return p;
}
void free() {/* Do nothing */}
```

上述实现遭受两个主要缺点：

+   系统调用很慢（与库调用相比）。我们应该保留大量内存，只偶尔向系统请求更多。

+   不重用释放的内存。我们的程序从不重用堆内存-它只是不断地要求更大的堆。

如果这个分配器在一个典型的程序中使用，进程将很快耗尽所有可用的内存。相反，我们需要一个能够有效利用堆空间，并且只在必要时请求更多内存的分配器。

## 什么是放置策略？

在程序执行期间，内存被分配和释放，因此堆内存中会有间隙（空洞），可以重新用于未来的内存请求。内存分配器需要跟踪堆的哪些部分当前被分配，哪些部分是可用的。

假设我们当前的堆大小是 64K，尽管并非所有都在使用，因为一些先前通过程序释放的 malloc 内存已经被释放了：

| 16KB free | 10KB allocated | 1KB free | 1KB allocated | 30KB free | 4KB allocated | 2KB free |
| --- | --- | --- | --- | --- | --- | --- |

如果执行一个新的 2KB 的 malloc 请求（`malloc(2048)`），malloc 应该在哪里保留内存？它可以使用最后的 2KB 空洞（恰好是完美的大小！），或者它可以分割其他两个空闲空洞中的一个。这些选择代表不同的放置策略。

无论选择哪个空洞，分配器都需要将空洞分成两部分：新分配的空间（将返回给程序）和一个较小的空洞（如果有剩余空间）。

完美拟合策略找到足够大的最小空洞（至少 2KB）：

| 16KB free | 10KB allocated | 1KB free | 1KB allocated | 30KB free | 4KB allocated | `2KB HERE!` |
| --- | --- | --- | --- | --- | --- | --- |

最坏的拟合策略找到足够大的最大空洞（所以将 30KB 的空洞分成两部分）：

| 16KB free | 10KB allocated | 1KB free | 1KB allocated | `2KB HERE!` | `28KB free` | 4KB allocated | 2KB free |
| --- | --- | --- | --- | --- | --- | --- | --- |

第一个适合策略找到第一个足够大的可用空洞（将 16KB 的空洞分成两部分）：

| `2KB HERE!` | `14KB free` | 10KB allocated | 1KB free | 1KB allocated | 30KB free | 4KB allocated | 2KB free |
| --- | --- | --- | --- | --- | --- | --- | --- |

## 什么是外部碎片？

在下面的例子中，64KB 的堆内存中，有 17KB 被分配，47KB 是空闲的。然而，最大的可用块只有 30KB，因为我们的可用未分配堆内存被分成了更小的块。

| `16KB free` | 10KB allocated | 1KB free | 1KB allocated | 30KB free | 4KB allocated | 2KB free |
| --- | --- | --- | --- | --- | --- | --- |

## 放置策略对外部碎片和性能有什么影响？

不同的策略以不明显的方式影响堆内存的碎片化，这只能通过数学分析或在真实条件下进行仔细模拟（例如模拟数据库或 Web 服务器的内存分配请求）来发现。例如，最佳适配乍看起来似乎是一个很好的策略，但是，如果我们找不到一个完全大小合适的空洞，那么这种放置会产生许多微小的无法使用的空洞，导致高度碎片化。它还需要扫描所有可能的空洞。

首次适配的优势在于它不会评估所有可能的放置，因此更快。

由于最坏适配针对最大的未分配空间，如果需要大量分配，则这是一个不好的选择。

在实践中，首次适配和下次适配（这里没有讨论）通常是常见的放置策略。还有混合方法和许多其他选择（请参见实现内存分配器页面）。

## 编写堆分配器的挑战是什么？

主要挑战是，

+   需要最小化碎片化（即最大化内存利用）

+   需要高性能

+   繁琐的实现（使用链表和指针算术进行大量指针操作）

一些额外的评论：

碎片化和性能都取决于应用程序的分配配置文件，这可以进行评估但无法预测，并且在实践中，在特定的使用条件下，专用分配器通常可以胜过通用实现。

分配器事先不知道程序的内存分配请求。即使我们知道，这也是著名的 NP 难题[背包问题](http://en.wikipedia.org/wiki/Knapsack_problem)！

## 如何实现内存分配器？

好问题。[实现内存分配器](https://github.com/angrave/SystemProgramming/wiki/Memory%2C-Part-2%3A-Implementing-a-Memory-Allocator)
