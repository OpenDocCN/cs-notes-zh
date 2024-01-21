# 文件系统，第六部分：内存映射文件和共享内存

## 操作系统如何将我的进程和库加载到内存中？

通过将文件的内容映射到进程的地址空间。如果许多程序只需要对同一个文件进行读取访问（例如/bin/bash，C 库），那么相同的物理内存可以在多个进程之间共享。

相同的机制可以被程序用来直接将文件映射到内存

## 如何将文件映射到内存？

下面显示了一个将文件映射到内存的简单程序。需要注意的关键点是：

+   mmap 需要一个文件描述符，所以我们需要先打开文件

+   我们寻找我们想要的大小并写入一个字节，以确保文件足够长

+   完成后调用 munmap 将文件从内存中取消映射。

这个例子还显示了预处理器常量“**LINE**”和“**FILE**”，它们保存了当前正在编译的文件的行号和文件名。

```cpp
#include <stdio.h>
#include <stdlib.h>
#include <sys/types.h>
#include <sys/stat.h>
#include <sys/mman.h>
#include <fcntl.h>
#include <unistd.h>
#include <errno.h>
#include <string.h>

int fail(char *filename, int linenumber) { 
  fprintf(stderr, "%s:%d %s\n", filename, linenumber, strerror(errno)); 
  exit(1);
  return 0; /*Make compiler happy */
}
#define QUIT fail(__FILE__, __LINE__ )

int main() {
  // We want a file big enough to hold 10 integers 
  int size = sizeof(int) * 10;

  int fd = open("data", O_RDWR | O_CREAT | O_TRUNC, 0600); //6 = read+write for me!

  lseek(fd, size, SEEK_SET);
  write(fd, "A", 1);

  void *addr = mmap(0, size, PROT_READ | PROT_WRITE, MAP_SHARED, fd, 0);
  printf("Mapped at %p\n", addr);
  if (addr == (void*) -1 ) QUIT;

  int *array = addr;
  array[0] = 0x12345678;
  array[1] = 0xdeadc0de;

  munmap(addr,size);
  return 0;

}
```

我们的二进制文件的内容可以使用 hexdump 列出

```cpp
$ hexdump data
0000000 78 56 34 12 de c0 ad de 00 00 00 00 00 00 00 00
0000010 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00
0000020 00 00 00 00 00 00 00 00 41 
```

细心的读者可能会注意到我们的整数是以最低有效字节格式写入的（因为这是 CPU 的字节序），而且我们分配了一个多出一个字节的文件！

`PROT_READ | PROT_WRITE`选项指定了虚拟内存保护。选项`PROT_EXEC`（这里没有使用）可以设置为允许 CPU 在内存中执行指令（例如，如果您映射了一个可执行文件或库，这将非常有用）。

## 内存映射文件的优势是什么

对于许多应用程序，主要优势是：

简化编码-文件数据立即可用。无需解析传入数据并将其存储在新的内存结构中。

文件共享-内存映射文件在多个进程之间共享相同数据时特别高效。

对于简单的顺序处理，内存映射文件不一定比标准的“基于流”的`read` / fscanf 等方法更快。

## 如何在父进程和子进程之间共享内存？

简单-使用`mmap`而不是文件-只需指定 MAP_ANONYMOUS 和 MAP_SHARED 选项！

```cpp
#include <stdio.h>
#include <stdlib.h>
#include <sys/types.h>
#include <sys/stat.h>
#include <sys/mman.h> /* mmap() is defined in this header */
#include <fcntl.h>
#include <unistd.h>
#include <errno.h>
#include <string.h>

int main() {

  int size = 100 * sizeof(int);  
  void *addr = mmap(0, size, PROT_READ | PROT_WRITE, MAP_SHARED | MAP_ANONYMOUS, -1, 0);
  printf("Mapped at %p\n", addr);

  int *shared = addr;
  pid_t mychild = fork();
  if (mychild > 0) {
    shared[0] = 10;
    shared[1] = 20;
  } else {
    sleep(1); // We will talk about synchronization later
    printf("%d\n", shared[1] + shared[0]);
  }

  munmap(addr,size);
  return 0;
}
```

## 我可以使用共享内存进行 IPC 吗？

是的！作为一个简单的例子，你可以只保留几个字节，并在想要子进程退出时更改共享内存中的值。共享内存是一种非常高效的进程间通信形式，因为没有复制开销-这两个进程实际上共享相同的*物理*内存帧。

[转到文件系统：第七部分](https://github.com/angrave/SystemProgramming/wiki/File-System,-Part-7:-Scalable-and-Reliable-Filesystems)
