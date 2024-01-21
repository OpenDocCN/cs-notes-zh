# 文件系统，第二部分：文件是索引节点（其他一切都只是数据...）

大意：忘记文件名：'索引节点'就是文件。

通常认为文件名是'实际'文件。不是！相反，将索引节点视为文件。索引节点包含元信息（最后访问、所有权、大小）并指向用于保存文件内容的磁盘块。

## 那么...我们如何实现一个目录？

目录只是名称到索引节点号的映射。POSIX 提供了一小组函数来读取每个条目的文件名和索引节点号（见下文）

让我们想想它在实际文件系统中是什么样子。理论上，目录就像实际文件一样。磁盘块将包含*目录条目*或*dirent*。这意味着我们的磁盘块可以看起来像这样

| 索引节点号 | 名称 |
| --- | --- |
| 2043567 | `hi.txt` |

...

每个目录条目可以是固定大小，也可以是可变的 C 字符串。这取决于特定文件系统在较低级别实现的方式。

## 我如何找到文件的索引节点号？

从 shell 中，使用带有`-i`选项的`ls`

```cpp
$ ls -i
12983989 dirlist.c      12984068 sandwich.c 
```

从 C 中调用 stat 函数之一（下面介绍）。

## 我如何找出文件（或目录）的元信息？

使用 stat 调用。例如，要找出我的'notes.txt'文件上次访问的时间 -

```cpp
   struct stat s;
   stat("notes.txt", & s);
   printf("Last accessed %s", ctime(s.st_atime));
```

实际上有三个版本的`stat`；

```cpp
       int stat(const char *path, struct stat *buf);
       int fstat(int fd, struct stat *buf);
       int lstat(const char *path, struct stat *buf);
```

例如，您可以使用`fstat`来查找与该文件关联的文件描述符的文件的元信息

```cpp
   FILE *file = fopen("notes.txt", "r");
   int fd = fileno(file); /* Just for fun - extract the file descriptor from a C FILE struct */
   struct stat s;
   fstat(fd, & s);
   printf("Last accessed %s", ctime(s.st_atime));
```

第三个调用'lstat'我们将在介绍符号链接时讨论。

除了访问、创建和修改时间之外，stat 结构还包括索引节点号、文件长度和所有者信息。

```cpp
struct stat {
               dev_t     st_dev;     /* ID of device containing file */
               ino_t     st_ino;     /* inode number */
               mode_t    st_mode;    /* protection */
               nlink_t   st_nlink;   /* number of hard links */
               uid_t     st_uid;     /* user ID of owner */
               gid_t     st_gid;     /* group ID of owner */
               dev_t     st_rdev;    /* device ID (if special file) */
               off_t     st_size;    /* total size, in bytes */
               blksize_t st_blksize; /* blocksize for file system I/O */
               blkcnt_t  st_blocks;  /* number of 512B blocks allocated */
               time_t    st_atime;   /* time of last access */
               time_t    st_mtime;   /* time of last modification */
               time_t    st_ctime;   /* time of last status change */
           };
```

## 我如何列出目录的内容？

让我们编写我们自己的'version of 'ls'来列出目录的内容。

```cpp
#include <stdio.h>
#include <dirent.h>
#include <stdlib.h>
int main(int argc, char **argv) {
    if(argc == 1) {
        printf("Usage: %s [directory]\n", *argv);
        exit(0);
    }
    struct dirent *dp;
    DIR *dirp = opendir(argv[1]);
    while ((dp = readdir(dirp)) != NULL) {
        puts(dp->d_name);
    }

    closedir(dirp);
    return 0;
}
```

## 我如何读取目录的内容？

答：使用 opendir readdir closedir 例如，这是一个非常简单的'ls'实现，用于列出目录的内容。

```cpp
#include <stdio.h>
#include <dirent.h>
#include <stdlib.h>
int main(int argc, char **argv) {
    if(argc ==1) {
        printf("Usage: %s [directory]\n", *argv);
        exit(0);
    }
    struct dirent *dp;
    DIR *dirp = opendir(argv[1]);
    while ((dp = readdir(dirp)) != NULL) {
        printf("%s %lu\n", dp-> d_name, (unsigned long)dp-> d_ino );
    }

    closedir(dirp);
    return 0;
}
```

注意：在调用 fork()后，父进程或子进程可以使用 readdir()、rewinddir()或 seekdir()。如果父进程和子进程都使用上述方法，行为是未定义的。

## 我如何检查文件是否在当前目录中？

例如，要查看特定目录是否包含文件（或文件名）'名称'，我们可以编写以下代码。（提示：你能发现错误吗？）

```cpp
int exists(char *directory, char *name)  {
    struct dirent *dp;
    DIR *dirp = opendir(directory);
    while ((dp = readdir(dirp)) != NULL) {
        puts(dp->d_name);
        if (!strcmp(dp->d_name, name)) {
        return 1; /* Found */
        }
    }
    closedir(dirp);
    return 0; /* Not Found */
}
```

上面的代码有一个微妙的错误：它泄漏资源！如果找到匹配的文件名，那么'closedir'将不会作为早期返回的一部分调用。opendir 打开的任何文件描述符和分配的任何内存都不会被释放。这意味着最终进程将耗尽资源，并且`open`或`opendir`调用将失败。

修复的方法是确保我们在每个可能的代码路径中释放资源。在上面的代码中，这意味着在`return 1`之前调用`closedir`。忘记释放资源是一个常见的 C 编程错误，因为 C 语言中没有支持确保所有代码路径都始终释放资源。

## 使用 readdir 的陷阱是什么？例如，递归搜索目录？

有两个主要的陷阱和一个考虑：`readdir`函数返回“.”（当前目录）和“..”（父目录）。如果要查找子目录，需要明确排除这些目录。

对于许多应用程序来说，首先检查当前目录，然后递归搜索子目录是合理的。这可以通过将结果存储在链接列表中来实现，或者重置目录结构以从头开始重新开始。

最后要注意的一点：`readdir`不是线程安全的！对于多线程搜索，请使用`readdir_r`，它要求调用者传递现有 dirent 结构的地址。

有关 readdir 的更多详细信息，请参阅 readdir 的 man 页面。

## 我如何确定目录条目是否是目录？

答：使用`S_ISDIR`来检查 stat 结构中存储的模式位

要检查文件是否为常规文件，请使用`S_ISREG`，

```cpp
   struct stat s;
   if (0 == stat(name, &s)) {
      printf("%s ", name);
      if (S_ISDIR( s.st_mode)) puts("is a directory");
      if (S_ISREG( s.st_mode)) puts("is a regular file");
   } else {
      perror("stat failed - are you sure I can read this file's meta data?");
   }
```

## 目录也有 inode 吗？

是的！虽然更好的想法是，一个目录（就像一个文件）*是*一个 inode（带有一些数据-目录名称和 inode 内容）。它碰巧是一种特殊类型的 inode。

来自[Wikipedia](http://en.wikipedia.org/wiki/Inode)：

> Unix 目录是关联结构的列表，每个结构包含一个文件名和一个 inode 号。

请记住，inode 不包含文件名-只包含其他文件元数据。

## 如何让相同的文件出现在文件系统中的两个不同位置？

首先要记住，文件名！=文件。将 inode 视为'文件'，目录只是一个名称列表，每个名称都映射到一个 inode 号。其中一些 inode 可能是常规文件 inode，其他可能是目录 inode。

如果我们已经在文件系统上有一个文件，我们可以使用'ln'命令创建到相同 inode 的另一个链接

```cpp
$ ln file1.txt blip.txt 
```

然而，blip.txt *是*相同的文件；如果我编辑 blip，我正在编辑与'file1.txt!'相同的文件！我们可以通过显示两个文件名指向相同的 inode 来证明这一点：

```cpp
$ ls -i file1.txt blip.txt
134235 file1.txt
134235 blip.txt 
```

这些链接（也称为目录条目）称为'硬链接'

等效的 C 调用是`link`

```cpp
link(const char *path1, const char *path2);

link("file1.txt", "blip.txt");
```

为了简单起见，上面的例子在同一个目录中创建了硬链接，但是硬链接可以在同一个文件系统的任何地方创建。

## 当我`rm`（删除）一个文件时会发生什么？

当您删除文件（使用`rm`或`unlink`）时，您正在从目录中删除一个 inode 引用。但是 inode 可能仍然被其他目录引用。为了确定文件的内容是否仍然需要，每个 inode 都保留一个引用计数，每当创建或销毁新链接时，该引用计数都会更新。

## 案例研究：最小化文件重复的备份软件

硬链接的一个示例用途是有效地在不同时间点创建文件系统的多个存档。一旦存档区域有特定文件的副本，未来的存档可以重用这些存档文件，而不是创建重复的文件。苹果的“Time Machine”软件就是这样做的。

## 我可以像常规文件一样创建目录的硬链接吗？

不。好吧是的。不是真的...实际上你并不真的想这样做，是吗？POSIX 标准说不，你不可以！`ln`命令只允许 root 执行此操作，只有在提供`-d`选项时才能执行此操作。但是，即使 root 也可能无法执行此操作，因为大多数文件系统会阻止它！

为什么？

## 文件系统的完整性假设目录结构（不包括我们稍后将讨论的软链接）是从根目录可达的非循环树。如果允许目录链接，强制执行或验证此约束将变得昂贵。打破这些假设可能导致文件完整性工具无法修复文件系统。递归搜索可能永远不会终止，目录可能有多个父目录，但“..”只能指向一个父目录。总的来说，这是一个坏主意。


