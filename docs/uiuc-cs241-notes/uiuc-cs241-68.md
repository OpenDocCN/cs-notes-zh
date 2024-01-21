# 文件系统，第四部分：使用目录

## 如何找出文件（inode）是常规文件还是目录？

使用`S_ISDIR`宏来检查 stat 结构中的模式位：

```cpp
struct stat s;
stat("/tmp", &s);
if (S_ISDIR(s.st_mode)) { ... 
```

请注意，稍后我们将编写健壮的代码来验证 stat 调用是否成功（返回 0）；如果“stat”调用失败，我们应该假设 stat 结构内容是任意的。

## 我如何递归进入子目录？

首先是一个谜题-在以下代码中你能找到多少个错误？

```cpp
void dirlist(char *path) {

  struct dirent *dp;
  DIR *dirp = opendir(path);
  while ((dp = readdir(dirp)) != NULL) {
     char newpath[strlen(path) + strlen(dp->d_name) + 1];
     sprintf(newpath,"%s/%s", newpath, dp->d_name);
     printf("%s\n", dp->d_name);
     dirlist(newpath);
  }
}

int main(int argc, char **argv) { dirlist(argv[1]); return 0; }
```

你找到了所有 5 个错误吗？

```cpp
// Check opendir result (perhaps user gave us a path that can not be opened as a directory
if (!dirp) { perror("Could not open directory"); return; }
// +2 as we need space for the / and the terminating 0
char newpath[strlen(path) + strlen(dp->d_name) + 2]; 
// Correct parameter
sprintf(newpath,"%s/%s", path, dp->d_name); 
// Perform stat test (and verify) before recursing
if (0 == stat(newpath,&s) && S_ISDIR(s.st_mode)) dirlist(newpath)
// Resource leak: the directory file handle is not closed after the while loop
closedir(dirp);
```

## 什么是符号链接？它们是如何工作的？我怎么做一个？

```cpp
symlink(const char *target, const char *symlink);
```

要在 shell 中创建符号链接，请使用`ln -s`

要将链接的内容读取为文件，请使用“readlink”

```cpp
$ readlink myfile.txt
../../dir1/notes.txt 
```

要读取符号链接的元（stat）信息，请使用“lstat”而不是“stat”

```cpp
struct stat s1, s2;
stat("myfile.txt", &s1); // stat info about  the notes.txt file
lstat("myfile.txt", &s2); // stat info about the symbolic link
```

## 符号链接的优点

+   可以引用尚不存在的文件

+   与硬链接不同，可以引用目录以及常规文件

+   可以引用存在于当前文件系统之外的文件（和目录）

主要缺点：比常规文件和目录慢。当读取链接的内容时，它们必须被解释为目标文件的新路径。

## “/dev/null”是什么，何时使用？

文件“/dev/null”是存储您永远不需要读取的位的好地方！发送到“/dev/null/”的字节永远不会被存储-它们只是被丢弃。 “/dev/null”的常见用途是丢弃标准输出。例如，

```cpp
$ ls . >/dev/null 
```

## 为什么我想设置目录的粘性位？

当目录的粘性位被设置时，只有文件的所有者、目录的所有者和 root 用户才能重命名（或删除）该文件。当多个用户对共享目录具有写访问权限时，这是有用的。

粘性位的常见用途是用于共享和可写的“/tmp”目录。

## 为什么 shell 和脚本程序以“#!/usr/bin/env python”开头？

答：为了可移植性！虽然可能会将完全合格的路径写入 python 或 perl 解释器，但这种方法不是可移植的，因为您可能已将 python 安装在不同的目录中。

要克服这一点，使用“env”实用程序来查找并执行用户路径上的程序。env 实用程序本身通常存储在“/usr/bin”中-必须使用绝对路径指定。

## 如何制作“隐藏”文件，即不被“ls”列出？我如何列出它们？

简单！创建以“.”开头的文件（或目录）-然后（默认情况下）它们不会被标准工具和实用程序显示。

这通常用于将配置文件隐藏在用户的主目录中。例如，“ssh”将其首选项存储在一个名为“.sshd”的目录中。

要列出所有文件，包括通常隐藏的条目，请使用带有“-a”选项的“ls”

```cpp
$ ls -a
.           a.c         myls
..          a.out           other.txt
.secret 
```

## 如果我关闭目录上的执行位会发生什么？

目录的执行位用于控制目录内容是否可列出。

```cpp
$ chmod ugo-x dir1
$ ls -l
drw-r--r--   3 angrave  staff   102 Nov 10 11:22 dir1 
```

但是，当尝试列出目录的内容时，

```cpp
$ ls dir1
ls: dir1: Permission denied 
```

换句话说，目录本身是可发现的，但其内容无法列出。

## 什么是文件通配（由谁执行）？

在执行程序之前，shell 将参数扩展为匹配的文件名。例如，如果当前目录有三个以 my 开头的文件名（my1.txt mytext.txt myomy），那么

```cpp
$ echo my* 
```

扩展到

```cpp
$ echo my1.txt mytext.txt myomy 
```

这被称为文件通配，并在执行命令之前进行处理。即命令的参数与手动输入每个匹配的文件名相同。

## 创建安全目录

假设您在/tmp 中创建了自己的目录，然后设置了权限，以便只有您可以使用该目录（见下文）。这安全吗？

```cpp
$ mkdir /tmp/mystuff
$ chmod 700 /tmp/mystuff 
```

在目录创建和权限更改之间存在一个机会窗口。这导致了几个基于竞争条件的漏洞（攻击者在权限被移除之前以某种方式修改目录）。一些例子包括：

另一个用户用一个硬链接替换`mystuff`，指向第二个用户拥有的现有文件或目录，然后他们就能读取和控制`mystuff`目录的内容。哦不 - 我们的秘密不再是秘密了！

然而，在这个特定的例子中，`/tmp`目录设置了粘滞位，因此其他用户可能无法删除`mystuff`目录，上述简单的攻击场景是不可能的。这并不意味着创建目录，然后稍后将目录设为私有是安全的！更好的版本是从一开始就原子性地创建具有正确权限的目录 -

```cpp
$ mkdir -m 700 /tmp/mystuff 
```

## 如何自动创建父目录？

```cpp
$ mkdir -p d1/d2/d3 
```

如果它们不存在，将自动创建 d1 和 d2。

## 我的默认 umask 是 022；这是什么意思？

umask *减去*（减少）权限位从 777，并且在使用 open、mkdir 等创建新文件和新目录时使用。因此，`022`（八进制）表示组和其他权限不包括可写位。每个进程（包括 shell）都有一个当前的 umask 值。在分叉时，子进程继承父进程的 umask 值。

例如，通过在 shell 中将 umask 设置为 077，可以确保将来创建的文件和目录只能被当前用户访问，

```cpp
$ umask 077
$ mkdir secretdir 
```

作为一个代码示例，假设使用`open()`创建一个新文件，并且模式位是`666`（用户、组和其他的写入和读取位）：

```cpp
open("myfile", O_CREAT, S_IRUSR | S_IWUSR | S_IRGRP | S_IWGRP | S_IROTH | S_IWOTH);
```

如果 umask 是八进制 022，那么创建的文件的权限将是 0666 和~022，即。

```cpp
           S_IRUSR | S_IWUSR | S_IRGRP | S_IROTH
```

## 我怎样才能从一个文件复制字节到另一个文件？

使用多功能的`dd`命令。例如，以下命令将从文件`/dev/urandom`复制 1MB 的数据到文件`/dev/null`。数据被复制为 1024 个块，每个块大小为 1024 字节。

```cpp
$ dd if=/dev/urandom of=/dev/null bs=1k count=1024 
```

上面示例中的输入和输出文件都是虚拟的 - 它们不存在于磁盘上。这意味着传输速度不受硬件功率的影响。相反，它们是内核提供的虚拟文件系统的一部分。虚拟文件`/dev/urandom`提供无限的随机字节流，而虚拟文件`/dev/null`会忽略写入它的所有字节。`/dev/null`的常见用途是丢弃命令的输出，

```cpp
$ myverboseexecutable > /dev/null 
```

另一个常用的/dev 虚拟文件是`/dev/zero`，它提供无限的零字节流。例如，我们可以对读取内核中的流零字节到进程内存并将字节写回内核而不进行任何磁盘 I/O 的操作系统性能进行基准测试。请注意，吞吐量（约 20GB/s）强烈依赖于块大小。对于小块大小，额外的`read`和`write`系统调用的开销将占主导地位。

```cpp
$ dd if=/dev/zero of=/dev/null bs=1M count=1024
1024+0 records in
1024+0 records out
1073741824 bytes (1.1 GB) copied, 0.0539153 s, 19.9 GB/s 
```

## 当我触摸一个文件时会发生什么？

`touch`可执行文件如果文件不存在则创建文件，并且还会更新文件的最后修改时间为当前时间。例如，我们可以用当前时间创建一个新的私有文件：

```cpp
$ umask 077       # all future new files will maskout all r,w,x bits for group and other access
$ touch file123   # create a file if it does not exist, and update its modified time
$ stat file123
  File: `file123'
  Size: 0           Blocks: 0          IO Block: 65536  regular empty file
Device: 21h/33d Inode: 226148      Links: 1
Access: (0600/-rw-------)  Uid: (395606/ angrave)   Gid: (61019/     ews)
Access: 2014-11-12 13:42:06.000000000 -0600
Modify: 2014-11-12 13:42:06.001787000 -0600
Change: 2014-11-12 13:42:06.001787000 -0600 
```

`touch`的一个示例用途是在修改 makefile 中的编译器选项后，强制 make 重新编译未更改的文件。记住，make 是“懒惰的” - 它将比较源文件的修改时间和相应输出文件的修改时间，以确定是否需要重新编译文件。

```cpp
$ touch myprogram.c   # force my source file to be recompiled
$ make 
```

[转到文件系统：第五部分](https://github.com/angrave/SystemProgramming/wiki/File-System,-Part-5:-Virtual-file-systems)
