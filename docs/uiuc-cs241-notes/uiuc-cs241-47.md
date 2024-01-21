# 管道，第一部分：管道介绍

## 什么是 IPC？

进程间通信是一个进程与另一个进程交流的任何方式。你已经看到了这种虚拟内存的一种形式！一块虚拟内存可以在父进程和子进程之间共享，从而进行通信。你可能想把那块内存包装在`pthread_mutexattr_setpshared(&attrmutex, PTHREAD_PROCESS_SHARED);`互斥锁（或者进程范围的互斥锁）中，以防止竞争条件。

还有更多标准的 IPC 方式，比如管道！考虑一下，如果你在终端中输入以下内容

```cpp
$ ls -1 | cut -d'.' -f1 | uniq | sort | tee dir_contents
```

以下代码做了什么（如果你愿意，你可以跳过这个）？好吧，它`ls`当前目录（-1 表示它每行输出一个条目）。然后`cut`命令取得第一个句点之前的所有内容。Uniq 确保所有行都是唯一的，sort 对它们进行排序，tee 输出到一个文件。

重要的部分是 bash 创建了**5 个单独的进程**并将它们的标准输出/标准输入与管道连接起来，轨迹看起来像这样。

(0) ls (1)------>(0) cut (1)------->(0) uniq (1)------>(0) sort (1)------>(0) tee (1)

管道中的数字是每个进程的文件描述符，箭头表示重定向或管道输出的位置。

## 什么是管道？

POSIX 管道几乎像它的真实对应物 - 你可以把字节塞进一端，它们会按照相同的顺序出现在另一端。然而，与真实的管道不同，流动方向总是相同的，一个文件描述符用于读取，另一个用于写入。`pipe`系统调用用于创建管道。

```cpp
int filedes[2];
pipe (filedes);
printf("read from %d, write to %d\n", filedes[0], filedes[1]);
```

这些文件描述符可以与`read`一起使用 -

```cpp
// To read...
char buffer[80];
int bytesread = read(filedes[0], buffer, sizeof(buffer));
```

和`write` -

```cpp
write(filedes[1], "Go!", 4);
```

## 我怎样使用管道与子进程通信？

使用管道的常见方法是在分叉之前创建管道。

```cpp
int filedes[2];
pipe (filedes);
pid_t child = fork();
if (child > 0) { /* I must be the parent */
    char buffer[80];
    int bytesread = read(filedes[0], buffer, sizeof(buffer));
    // do something with the bytes read 
}
```

然后子进程可以向父进程发送消息：

```cpp
if (child == 0) {
   write(filedes[1], "done", 4);
}
```

## 我可以在单个进程中使用管道吗？

简短回答：是的，但我不确定你为什么要这样做 LOL！

以下是一个向自己发送消息的示例程序：

```cpp
#include <unistd.h>
#include <stdlib.h>
#include <stdio.h>

int main() {
    int fh[2];
    pipe(fh);
    FILE *reader = fdopen(fh[0], "r");
    FILE *writer = fdopen(fh[1], "w");
    // Hurrah now I can use printf rather than using low-level read() write()
    printf("Writing...\n");
    fprintf(writer,"%d %d %d\n", 10, 20, 30);
    fflush(writer);

    printf("Reading...\n");
    int results[3];
    int ok = fscanf(reader,"%d %d %d", results, results + 1, results + 2);
    printf("%d values parsed: %d %d %d\n", ok, results[0], results[1], results[2]);

    return 0;
}
```

以这种方式使用管道的问题在于写入管道可能会阻塞，即管道只有有限的缓冲容量。如果管道已满，写入进程将被阻塞！缓冲区的最大大小取决于系统；典型值从 4KB 到 128KB。

```cpp
int main() {
    int fh[2];
    pipe(fh);
    int b = 0;
    #define MESG "..............................."
    while(1) {
        printf("%d\n",b);
        write(fh[1], MESG, sizeof(MESG))
        b+=sizeof(MESG);
    }
    return 0;
}
```

参见[Pipes，第二部分：管道编程秘密](/angrave/SystemProgramming/wiki/Pipes%2C-Part-2%3A-Pipe-programming-secrets)
