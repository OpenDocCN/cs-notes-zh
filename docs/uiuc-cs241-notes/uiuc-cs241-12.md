# C 编程，第五部分：调试

## 《C 程序调试指南》

这将是一个帮助您调试 C 程序的大型指南。您可以检查错误的不同级别，我们将逐个介绍。请随时添加您在调试 C 程序中发现有用的任何内容，包括但不限于，调试器的使用，识别常见错误类型，陷阱和有效的搜索技巧。

## 在代码中调试

## 清洁代码

使用辅助函数使您的代码模块化。如果有重复的任务（例如在 MP2 中获取连续块的指针），请将它们制作为辅助函数。确保每个函数都非常擅长做一件事，这样您就不必两次调试。

假设我们正在通过每次迭代找到最小元素来进行选择排序，如下所示，

```cpp
void selection_sort(int *a, long len){
     for(long i = len-1; i > 0; --i){
         long max_index = i;
         for(long j = len-1; j >= 0; --j){
             if(a[max_index] < a[j]){
                  max_index = j;
             }
         }
         int temp = a[i];
         a[i] = a[max_index];
         a[max_index] = temp;
     }

}
```

许多人可以看到代码中的错误，但将上述方法重构为

```cpp
long max_index(int *a, long start, long end);
void swap(int *a, long idx1, long idx2);
void selection_sort(int *a, long len);
```

而错误特别在一个函数中。

最后，我们不是一个关于重构/调试代码的课程--事实上，大多数系统代码都很糟糕，你不想读它。但是为了调试，长远来看，采用一些实践可能对你有好处。

## 断言！

使用断言来确保您的代码在某个特定点之前工作--并且重要的是，确保您以后不会破坏它。例如，如果您的数据结构是双向链表，您可以这样做，assert(node->size == node->next->prev->size)来断言下一个节点指向当前节点。您还可以检查指针是否指向预期的内存地址范围，而不是 null，->size 是合理的等等。NDEBUG 宏将禁用所有断言，因此在调试完成后不要忘记设置它。[`www.cplusplus.com/reference/cassert/assert/`](http://www.cplusplus.com/reference/cassert/assert/)

使用 assert 的一个快速示例是，假设我正在使用 memcpy 编写代码

```cpp
assert(!(src < dest+n && dest < src+n)); //Checks overlap
memcpy(dest, src, n);
```

这个检查可以在编译时关闭，但会帮助您避免大量的调试麻烦！

## printfs

当一切都失败时，疯狂地打印！您的每个函数都应该知道它要做什么（例如，find_min 最好找到最小的元素）。您希望测试每个函数是否正在做它设定的事情，并确切地查看代码在哪里出错。在竞态条件的情况下，tsan 可能有所帮助，但让每个线程在特定时间打印数据可能有助于您识别竞态条件。

## Valgrind

（待办事项）

## Tsan

ThreadSanitizer 是 Google 的一个工具，内置在 clang（和 gcc）中，可以帮助您检测代码中的竞态条件。有关该工具的更多信息，请参阅 Github 维基。

请注意，使用 tsan 会使您的代码变慢一些。

```cpp
#include <pthread.h>
#include <stdio.h>

int Global;

void *Thread1(void *x) {
    Global++;
    return NULL;
}

int main() {
    pthread_t t[2];
    pthread_create(&t[0], NULL, Thread1, NULL);
    Global = 100;
    pthread_join(t[0], NULL);
}
// compile with gcc -fsanitize=thread -pie -fPIC -ltsan -g simple_race.c
```

我们可以看到变量 Global 存在竞态条件。主线程和使用 pthread_create 创建的线程将尝试同时更改值。但是，ThreadSantizer 能否捕捉到它呢？

```cpp
$ ./a.out
==================
WARNING: ThreadSanitizer: data race (pid=28888)
  Read of size 4 at 0x7f73ed91c078 by thread T1:
    #0 Thread1 /home/zmick2/simple_race.c:7 (exe+0x000000000a50)
    #1  :0 (libtsan.so.0+0x00000001b459)

  Previous write of size 4 at 0x7f73ed91c078 by main thread:
    #0 main /home/zmick2/simple_race.c:14 (exe+0x000000000ac8)

  Thread T1 (tid=28889, running) created by main thread at:
    #0  :0 (libtsan.so.0+0x00000001f6ab)
    #1 main /home/zmick2/simple_race.c:13 (exe+0x000000000ab8)

SUMMARY: ThreadSanitizer: data race /home/zmick2/simple_race.c:7 Thread1
==================
ThreadSanitizer: reported 1 warnings 
```

如果我们使用调试标志编译，那么它将给我们变量名。

## GDB

介绍：[`www.cs.cmu.edu/~gilpin/tutorial/`](http://www.cs.cmu.edu/%7Egilpin/tutorial/)

#### 以编程方式设置断点

在使用 GDB 调试复杂的 C 程序时，一个非常有用的技巧是在源代码中设置断点。

```cpp
int main() {
    int val = 1;
    val = 42;
    asm("int $3"); // set a breakpoint here
    val = 7;
}
```

```cpp
$ gcc main.c -g -o main && ./main
(gdb) r
[...]
Program received signal SIGTRAP, Trace/breakpoint trap.
main () at main.c:6
6       val = 7;
(gdb) p val
$1 = 42
```

#### 检查内存内容

[`www.delorie.com/gnu/docs/gdb/gdb_56.html`](http://www.delorie.com/gnu/docs/gdb/gdb_56.html)

例如，

```cpp
int main() {
    char bad_string[3] = {'C', 'a', 't'};
    printf("%s", bad_string);
}
```

```cpp
$ gcc main.c -g -o main && ./main
$ Cat ZVQ�� $
```

```cpp
(gdb) l
1   #include <stdio.h>
2   int main() {
3       char bad_string[3] = {'C', 'a', 't'};
4       printf("%s", bad_string);
5   }
(gdb) b 4
Breakpoint 1 at 0x100000f57: file main.c, line 4.
(gdb) r
[...]
Breakpoint 1, main () at main.c:4
4       printf("%s", bad_string);
(gdb) x/16xb bad_string
0x7fff5fbff9cd: 0x63    0x61    0x74    0xe0    0xf9    0xbf    0x5f    0xff
0x7fff5fbff9d5: 0x7f    0x00    0x00    0xfd    0xb5    0x23    0x89    0xff

(gdb)
```

在这里，通过使用带有参数`16xb`的`x`命令，我们可以看到从内存地址`0x7fff5fbff9c`（`bad_string`的值）开始，printf 实际上会看到以下字节序列作为字符串，因为我们提供了一个没有空终止符的格式不正确的字符串。

`0x43 0x61 0x74 0xe0 0xf9 0xbf 0x5f 0xff 0x7f 0x00`


