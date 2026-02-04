# 背景

## 系统架构

本节是对系统架构主题的简要回顾，这些主题对于系统编程是必需的。

### 汇编

什么是汇编？汇编是您在不直接编写 1 和 0 的情况下所能达到的最低级的机器语言。每台计算机都有一个架构，并且该架构有一个相关的汇编语言。每个汇编指令都与一组 1 和 0 一一对应，这些 1 和 0 告诉计算机确切要做什么。例如，以下是在广泛使用的 x86 汇编语言中向内存地址 20 加一的指令（维基图书 2018）——您也可以在（指南 2011）第 2A 节下查找加法指令，尽管它更为冗长。

```c
add BYTE PTR [0x20], 1
```

为什么我们要提到这一点？因为虽然你将在大多数课程中使用 C 语言，但代码实际上会被翻译成这种形式。对于竞态条件和原子操作，这会产生严重的后果。

### 原子操作

如果没有其他处理器应该中断它，则操作是原子的。以上述汇编代码向寄存器加一为例。在架构中，它实际上可能在电路上有几个不同的步骤。操作可能首先从 ram 的 stick 中获取内存值，然后将其存储在缓存或寄存器中，最后写回（Schweizer, Besta, and Hoefler 2015）——在*fetch-and-add*的描述下，尽管你的微架构可能不同。或者根据性能操作，它可能将那个值保持在缓存或该进程的本地寄存器中——尝试导出增加变量的优化汇编。问题在于如果两个处理器同时尝试这样做。两个处理器可能同时复制内存地址的值，加一，并将相同的结果写回，导致值只增加一次。这就是为什么我们在现代系统中有一组特殊的指令称为原子操作。如果一个指令是原子的，它确保一次只有一个处理器或线程执行任何中间步骤。在 x86 中，这是通过前缀（指南 2011，1120）完成的。

```c
lock add BYTE PTR [0x20], 1
```

为什么我们不把这一切都这样做？这会使命令变慢！如果每次计算机做某事时都必须确保其他核心或处理器没有在做任何事情，它将会慢得多。大多数时候我们会用特殊考虑来区分这些。这意味着，当我们使用类似的东西时，我们会告诉你。大多数时候，你可以假设指令是未锁定的。

### 缓存

哎，是的，缓存。计算机科学中最大的问题之一。我们所说的缓存是指处理器缓存。如果在读取或写入时特定的地址已经在缓存中，处理器将对该缓存执行操作，例如添加和更新实际内存，稍后因为更新内存是慢的（英特尔 2015 第 3.4 节）。如果没有，处理器将从内存芯片请求一块内存并将其存储在缓存中，淘汰最不常使用的页面——这取决于缓存策略，但英特尔确实使用了这种方法。这样做是因为 l3 处理器缓存在时间上比内存快大约三倍（Levinthal 2009，22），但确切的速度会根据时钟速度和架构而变化。自然地，这会导致问题，因为有两个相同值的副本，在所引用的论文中这指的是未共享的行。这不是一个关于缓存的课程，但你应该知道这可能会如何影响你的代码。一个简短但不完整的列表可能是

1.  竞态条件！如果一个值存储在两个不同的处理器缓存中，那么这个值应该由单个线程访问。

1.  速度。有了缓存，你的程序可能会神秘地看起来更快。只需假设最近发生或内存中相邻的读取和写入操作是快速的。

1.  副作用。每次读取或写入都会影响缓存状态。虽然大多数时候这不会有所帮助或造成伤害，但了解这一点很重要。请查阅英特尔程序员指南中有关锁前缀的更多信息。

### 中断

中断是系统编程的重要组成部分。中断在内部是一个电信号，当发生某些事情时传递给处理器——这是一个硬件中断（“第三章 硬件中断”，n.d.）。然后硬件决定这是否是它应该处理的事情（例如，处理旧键盘和鼠标的键盘或鼠标输入）或者应该传递给操作系统。操作系统随后决定这是否是它应该处理的事情（例如，从磁盘分页内存表）或者应用程序应该处理的事情（例如，SEGFAULT）。如果操作系统决定这是进程或程序应该处理的事情，它会发送一个**软件故障**，然后这个软件故障就会传播。应用程序随后决定这是否是一个错误（SEGFAULT）或者不是（例如 SIGPIPE）并向用户报告。应用程序还可以向内核和硬件发送信号。这是一个过于简化的说法，因为有一些硬件故障不能被忽略或屏蔽，但这个课程不是教你如何构建操作系统。

这的一个重要应用就是系统调用的服务方式！有一套经过良好建立的寄存器，根据内核的规则，参数会放入其中，以及一个由内核再次定义的系统调用“编号”。然后操作系统触发一个中断，内核捕获并服务系统调用（Garg 2006）。

操作系统开发者和指令集开发者都不喜欢在系统调用时引起中断的开销。现在，系统使用了一种更干净的方式来安全地将控制权转移到内核，并安全地返回。安全意味着什么在这个课程的范围之外，但它持续存在。

### 可选：超线程

超线程是一种新技术，它根本不是多线程。超线程允许一个物理核心在操作系统中表现为多个虚拟核心（Guide 2011，第 51 页）。操作系统可以在这这些虚拟核心上调度进程，一个核心将执行它们。每个核心交错执行进程或线程。当核心等待一个内存访问完成时，它可能执行另一个进程线程的几个指令。整体结果是更短的时间内执行了更多的指令。这潜在地意味着你可以减少为小型设备供电所需的核心数量。

但是这里有一些风险。在使用超线程时，你必须小心优化。一个著名的超线程错误导致程序在至少有两个进程被调度到物理核心、使用特定寄存器并在紧密循环中时崩溃。这个问题实际上通过架构的角度解释得更好。但是，这个实际的应用是通过在 OCaml 主线工作的系统程序员发现的（Leroy 2017）。

## 调试和环境

我要告诉你这个课程的秘密：它是关于更聪明地工作，而不是更努力地工作。这个课程可能会很耗时，但很多人认为它就是这样（以及为什么很多学生不这样认为）的原因是人们对他们的工具相对熟悉。让我们回顾一下你将需要熟悉的一些常见工具。

### ssh

ssh 是 Secure Shell（“Ssh(1),” n.d.）的缩写。它是一种网络协议，允许你在远程机器上启动一个 shell。在这个课程的大部分时间里，你将需要像这样 ssh 到你的虚拟机

```c
$ ssh netid@sem-cs341-VM.cs.illinois.edu
```

如果你不想每次都输入密码，你可以生成一个唯一标识你的机器的 ssh 密钥。如果你已经有了密钥对，你可以跳到复制 id 阶段。

```c
> ssh-keygen -t rsa -b 4096
# Do whatever keygen tells you
# Don't feel like you need a passcode if your login password is secure
> ssh-copy-id netid@sem-cs341-VM.cs.illinois.edu
# Enter your password for maybe the final time
> ssh  netid@sem-cs341-VM.cs.illinois.edu
```

如果你仍然觉得输入太多，你总是可以给主机起别名。你可能需要重新启动你的虚拟机或重新加载 sshd 才能使这个更改生效。配置文件在 Linux 和 Mac 发行版上可用。对于 Windows，你必须使用 Windows Linux 子系统或配置 PuTTY 中的任何别名

```c
> cat ~/.ssh/config
Host vm
 User          netid
 HostName      sem-cs341-VM.cs.illinois.edu
> ssh vm
```

### git

什么是‘git’？Git 是一个版本控制系统。这意味着 git 存储了一个目录的整个历史。我们将该目录称为仓库。所以你需要知道的是一些事情。首先，使用仓库创建器创建你的仓库。如果你还没有登录企业 GitHub，请确保这样做，否则你的仓库将不会为你创建。之后，你的仓库在服务器上创建。Git 是一个分布式版本控制系统，这意味着你需要将一个仓库放到你的虚拟机（VM）上。我们可以通过克隆来实现这一点。无论你做什么，**都不要通过 README.md 教程进行**。

```c
$ git clone https://github.com/illinois-cs-coursework/fa23_cs341_<netid>
```

这将创建一个本地仓库。工作流程是这样的：你在本地仓库上进行更改，将更改添加到当前提交中，实际上提交，并将更改推送到服务器。

```c
$ # edit the file, maybe using vim
$ git add <file>
$ git commit -m "Committing my file"
$ git push origin master
```

现在要很好地解释 git，你需要理解，就我们的目的而言，git 将看起来像是一个链表。你将始终位于 master 的头部，并且你会进行编辑-添加-提交-推送的循环。我们在 GitHub 上有一个单独的分支，我们将反馈推送到特定的分支，你可以在 GitHub 网站上查看。Markdown 文件将包含测试用例和结果（如标准输出）。

有时 git 可能会出错。以下是一些你可能不需要修复你的仓库的命令列表

1.  git-cherry-pick

1.  git-pack

1.  git-gc

1.  git-clean

1.  git-rebase

1.  git-stash/git-apply/git-pop

1.  git-branch

如果你目前在一个分支上，你既看不到

```c
$ git status
On branch master
Your branch is up-to-date with 'origin/master'.
nothing to commit, working directory clean
```

也没有

```c
$ git status
On branch master
Your branch is up-to-date with 'origin/master'.
Changes not staged for commit:
 (use "git add <file>..." to update what will be committed)
 (use "git checkout -- <file>..." to discard changes in working directory)

 modified:   <FILE>
 ...

no changes added to commit (use "git add" and/or "git commit -a")
```

以及类似的内容

```c
$ git status
HEAD detached at 4bc4426
nothing to commit, working directory clean
```

不要慌张，但你的仓库可能处于不可工作的状态。如果你没有接近截止日期，请来办公室时间或在你 Edstem 上提问，我们会很乐意帮助你。在紧急情况下，删除你的仓库并重新克隆（你将不得不添加如上所述的内容）。**这将丢失任何本地未提交的更改。请确保复制任何你在目录外工作的文件，移除并重新复制它们**

如果你想了解更多关于 git 的信息，网上有无数个教程和资源可以帮助你。以下是一些可以帮助你的链接

1.  [`git-scm.com/docs/gittutorial`](https://git-scm.com/docs/gittutorial)

1.  [`www.atlassian.com/git/tutorials/what-is-version-control`](https://www.atlassian.com/git/tutorials/what-is-version-control)

1.  [`thenewstack.io/tutorial-git-for-absolutely-everyone/`](https://thenewstack.io/tutorial-git-for-absolutely-everyone/)

### 编辑器

有些人把这当作学习新编辑器的机会，而有些人则不然。第一部分是那些想要学习新编辑器的人。在跨越数十年的编辑器战争中，我们来到了 vim 与 emacs 的战斗。

Vim 是一个文本编辑器和类 Unix 实用工具。你可以通过输入 , 来进入 vim，这会带你进入编辑器。最常用的三种模式是：正常模式、插入模式和命令模式。你从正常模式开始。在这个模式下，你可以使用许多键来移动，最常见的键是（分别对应左、下、上和右）。在 vim 中运行命令时，你可以在输入后输入一个命令。例如，要退出 vim，只需输入 (q 代表退出)。如果你有任何未保存的编辑，你必须保存它们、保存并退出，或者退出并丢弃更改。要编辑，你可以输入以进入插入模式，或者输入以在光标后进入插入模式 **a**。这是 vim 的基本操作。除了互联网上无数的优质资源外，vim 还为初学者提供了自己的内置教程。要访问交互式教程，请在命令行中输入（不在 vim 内部），然后你就准备好了！

Emacs 更像是一种生活方式，我并不是在比喻意义上说。很多人说 emacs 是一个功能强大的操作系统，缺少一个不错的文本编辑器。这意味着 emacs 可以容纳终端、gdb 会话、ssh 会话、代码等等。介绍 GNU-emacs 没有比通过 GNU 文档 [`www.gnu.org/software/emacs/tour/`](https://www.gnu.org/software/emacs/tour/) 更合适的方式了。只需注意，emacs *极其* 强大。你可以用它做几乎所有的事情。有不少学生喜欢其他编程语言的 IDE 特性。要知道你可以设置 emacs 成为一个 IDE，但你必须学习一点 Lisp [`martinsosic.com/development/emacs/2017/12/09/emacs-cpp-ide.html`](http://martinsosic.com/development/emacs/2017/12/09/emacs-cpp-ide.html)。

然后，有些人喜欢使用自己的编辑器。这完全没问题。为此，我们需要 sshfs，它可以在许多不同的机器上运行。

1.  Windows [`github.com/billziss-gh/sshfs-win`](https://github.com/billziss-gh/sshfs-win)

1.  Mac [`github.com/osxfuse/osxfuse/wiki/SSHFS`](https://github.com/osxfuse/osxfuse/wiki/SSHFS)

1.  Linux [`help.ubuntu.com/community/SSHFS`](https://help.ubuntu.com/community/SSHFS)

在那个时刻，你的虚拟机上的文件与你的机器上的文件同步，你可以进行编辑，并且这些编辑将会同步。

在撰写本文时，作者喜欢使用 spacemacs [`spacemacs.org/`](http://spacemacs.org/)，它结合了 vim 和 emacs 的优点，并且克服了它们各自的困难。我将分享我喜欢它的原因，但警告一下，如果你完全没有 vim 或 emacs 的经验，学习曲线加上这门课程可能会过于陡峭。

1.  可扩展。Spacemacs 有一个干净的设计，用 lisp 编写。有 100 多个包可以通过编辑你的 spacemacs 配置并重新加载来安装，从语法检查、自动静态分析等一切。

1.  大部分来自 vim 和 emacs 的优点。Emacs 作为一个快速的编辑器，擅长做任何事情。Vim 擅长快速编辑和移动。Spacemacs 是两者的最佳结合，允许使用 vim 键盘绑定访问所有 emacs 的优点。

1.  完成了大量的预配置。与全新的 emacs 安装相比，许多语言和项目的配置已经为你完成，如 neotree、helm、各种语言层。你所要做的就是使用 neotree 导航到你的项目基础目录，emacs 将变成该编程语言的 IDE。

但显然各有所好。许多人会争论编辑大师们花更多的时间在编辑他们的编辑器上，而不是真正地编辑。

### Clean Code

使用辅助函数使你的代码模块化。如果有重复的任务（例如，在 malloc MP 中获取连续块的指针），将它们做成辅助函数。并确保每个函数都做得很好，这样你就不必调试两次。假设我们正在通过每次迭代找到最小元素来进行选择排序，

```c
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

许多人可以看到代码中的错误，但将上述方法重构可能有所帮助。

```c
long max_index(int *a, long start, long end);
void swap(int *a, long idx1, long idx2);
void selection_sort(int *a, long len);
```

错误特别在一个函数中。最终，这个课程是关于编写系统程序，而不是关于重构/调试你的代码的课程。实际上，大多数内核代码非常糟糕，你不想阅读它——那里的辩护是它需要这样。但为了调试，从长远来看，采用一些这些做法可能对你有益。

### 断言

使用断言来确保你的代码在某个点上正常工作——并且重要的是，确保你以后不会破坏它。例如，如果你的数据结构是双向链表，你可以做些类似的事情来断言下一个节点有一个指向当前节点的指针。你还可以检查指针是否指向一个预期的内存地址范围，非空，->size 是合理的等。宏将禁用所有断言，所以一旦你完成调试，别忘了设置它（“断言”，n.d.）。

这里有一个使用断言的快速示例。假设我们正在使用 memcpy 编写代码。我们想在它之前放一个断言来检查我的两个内存区域是否重叠。如果它们重叠，memcpy 将遇到未定义的行为，所以我们想尽早发现这个问题。

```c
assert( src+n < dest || src >= dest + n); // source should finish before the destination or the source starts after the end of destination
memcpy(dest, src, n);
```

这个检查可以在编译时关闭，但将为你节省大量的调试麻烦！

## Valgrind

Valgrind 是一套工具集，旨在提供调试和性能分析工具，使你的程序更加正确，并检测一些运行时问题（“4. Memcheck：内存错误检测器”，n.d.）。其中最常用的工具是 Memcheck，它可以检测许多在 C 和 C++ 程序中常见的内存相关错误，这些错误可能导致崩溃和不可预测的行为（例如，未释放的内存缓冲区）。要在你的程序上运行 Valgrind：

```c
valgrind --leak-check=full --show-leak-kinds=all myprogram arg1 arg2
```

参数是可选的，默认运行的工具是 Memcheck。输出将以以下形式呈现：分配、释放和错误的数量。假设我们有一个像这样的简单程序：

```c
#include <stdlib.h>

void dummy_function() {
 int* x = malloc(10 * sizeof(int));
 x[10] = 0;        // error 1: Out of bounds write, as you can see here we write to an out of bound memory address.
}                    // error 2: Memory Leak, x is allocated at function exit.

int main(void) {
 dummy_function();
 return 0;
}
```

这个程序编译并运行没有错误。让我们看看 Valgrind 会输出什么。

```c
==29515== Memcheck, a memory error detector
==29515== Copyright (C) 2002-2015, and GNU GPL'd, by Julian Seward et al.
==29515== Using Valgrind-3.11.0 and LibVEX; rerun with -h for copyright info
==29515== Command: ./a
==29515==
==29515== Invalid write of size 4
==29515==    at 0x400544: dummy_function (in /home/rafi/projects/exocpp/a)
==29515==    by 0x40055A: main (in /home/rafi/projects/exocpp/a)
==29515==  Address 0x5203068 is 0 bytes after a block of size 40 alloc'd
==29515==    at 0x4C2DB8F: malloc (in /usr/lib/valgrind/vgpreload_memcheck-amd64-linux.so)
==29515==    by 0x400537: dummy_function (in /home/rafi/projects/exocpp/a)
==29515==    by 0x40055A: main (in /home/rafi/projects/exocpp/a)
==29515==
==29515==
==29515== HEAP SUMMARY:
==29515==     in use at exit: 40 bytes in 1 blocks
==29515==   total heap usage: 1 allocs, 0 frees, 40 bytes allocated
==29515==
==29515== LEAK SUMMARY:
==29515==    definitely lost: 40 bytes in 1 blocks
==29515==    indirectly lost: 0 bytes in 0 blocks
==29515==      possibly lost: 0 bytes in 0 blocks
==29515==    still reachable: 0 bytes in 0 blocks
==29515==         suppressed: 0 bytes in 0 blocks
==29515== Rerun with --leak-check=full to see details of leaked memory
==29515==
==29515== For counts of detected and suppressed errors, rerun with: -v
==29515== ERROR SUMMARY: 1 errors from 1 contexts (suppressed: 0 from 0)
```

**无效写入**：它检测到我们的堆块越界，写入分配块之外。

**肯定丢失**：内存泄漏——你可能忘记释放一个内存块。

Valgrind 是一个有效的工具，用于在运行时检查错误。当涉及到这种行为时，C 语言是特殊的，因此编译你的程序后，你可以使用 Valgrind 来修复编译器可能遗漏的错误，这通常发生在程序运行时。

更多信息，请参阅手册（“4. Memcheck: A Memory Error Detector,” n.d.）

### TSAN

ThreadSanitizer 是 Google 的一项工具，内置在 clang 和 gcc 中，用于帮助你在代码中检测竞态条件（“ThreadSanitizerCppManual” 2018）。注意，使用 tsan 会使你的代码运行速度稍微慢一些。考虑以下代码。

```c
#include <pthread.h>
#include <stdio.h>

int global;

void *Thread1(void *x) {
 global++;
 return NULL;
}

int main() {
 pthread_t t[2];
 pthread_create(&t[0], NULL, Thread1, NULL);
 global = 100;
 pthread_join(t[0], NULL);
}
// compile with gcc -fsanitize=thread -pie -fPIC -ltsan -g simple_race.c
```

我们可以看到变量上存在竞态条件。主线程和创建的线程都会尝试同时更改该值。但是，ThreadSanitizer 能捕捉到它吗？

```c
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

如果我们使用调试标志进行编译，那么它还会给出变量名。

## GDB

GDB 是 GNU 调试器的缩写。GDB 是一个程序，它通过交互式调试帮助你追踪错误（“GDB: The Gnu Project Debugger” 2019）。它可以启动和停止你的程序，四处查看，并设置临时的约束和检查。以下是一些示例。

##### 通过编程方式设置断点

断点是指你希望程序停止执行并将控制权交回调试器的代码行。在用 GDB 调试复杂的 C 程序时，设置源代码中的断点是一个有用的技巧。

```c
int main() {
 int val = 1;
 val = 42;
 asm("int $3"); // set a breakpoint here
 val = 7;
}
```

```c
$ gcc main.c -g -o main
$ gdb --args ./main
(gdb) r
[...]
Program received signal SIGTRAP, Trace/breakpoint trap.
main () at main.c:6
6     val = 7;
(gdb) p val
$1 = 42
```

你也可以通过编程方式设置断点。假设我们没有优化，行号如下

```c
1. int main() {
2.     int val = 1;
3.     val = 42;
4.     val = 7;
5. }
```

我们现在可以在程序开始之前设置断点。

```c
$ gcc main.c -g -o main
$ gdb --args ./main
(gdb) break main.c:4
[...]
(gdb) p val
$1 = 42
```

##### 检查内存内容

我们还可以使用 GDB 来检查不同内存块的内容。例如，

```c
int main() {
 char bad_string[3] = {'C', 'a', 't'};
 printf("%s", bad_string);
}
```

编译后得到

```c
$ gcc main.c -g -o main && ./main
$ Cat ZVQ� $
```

我们现在可以使用 GDB 来查看字符串的特定字节，并推断程序应该在何时停止运行。

```c
(gdb) l
1 #include <stdio.h>
2 int main() {
3     char bad_string[3] = {'C', 'a', 't'};
4     printf("%s", bad_string);
5 }
(gdb) b 4
Breakpoint 1 at 0x100000f57: file main.c, line 4.
(gdb) r
[...]
Breakpoint 1, main () at main.c:4
4     printf("%s", bad_string);
(gdb) x/16xb bad_string
0x7fff5fbff9cd: 0x63  0x61  0x74  0xe0  0xf9  0xbf  0x5f  0xff
0x7fff5fbff9d5: 0x7f  0x00  0x00  0xfd  0xb5  0x23  0x89  0xff
(gdb)
```

这里，通过使用带有参数的命令，我们可以看到从内存地址（值为）开始，实际上会看到以下字节序列作为字符串，因为我们提供了一个没有空终止符的格式错误的字符串。

### 涉及到的 GDB 示例

这就是你的助教如何通过调试一个出错的简单程序。首先，程序的源代码。如果你能立即看到错误，请耐心等待。

```c
#include <stdio.h>

double convert_to_radians(int deg);

int main(){
 for (int deg = 0; deg > 360; ++deg){
 double radians = convert_to_radians(deg);
 printf("%d. %f\n", deg, radians);
 }
 return 0;
}

double convert_to_radians(int deg){
 return ( 31415 / 1000 ) * deg / 180;
}
```

我们如何使用 GDB 进行调试？首先，我们应该加载 GDB。

```c
$ gdb --args ./main
(gdb) layout src; # If you want a GUI type
(gdb) run
(gdb)
```

想要查看源代码吗？

```c
(gdb) l
1	#include <stdio.h>
2 
3	double convert_to_radians(int deg);
4 
5	int main(){
6		for (int deg = 0; deg > 360; ++deg){
7			double radians = convert_to_radians(deg);
8			printf("%d. %f\n", deg, radians);
9		}
10	    return 0;
(gdb) break 7 # break <file>:line or break <file>:function
(gdb) run
(gdb)
```

从运行代码来看，断点甚至没有触发，这意味着代码从未到达那个点。那是因为比较！好吧，翻转符号，现在应该可以工作了，对吧？

```c
(gdb) run
350. 60.000000
351. 60.000000
352. 60.000000
353. 60.000000
354. 60.000000
355. 61.000000
356. 61.000000
357. 61.000000
358. 61.000000
359. 61.000000
```

```c
(gdb) break 14 if deg == 359 # Let's check the last iteration only
(gdb) run
...
(gdb) print/x deg # print the hex value of degree
$1 = 0x167
(gdb) print (31415/1000)
$2 = 0x31
(gdb) print (31415/1000.0)
$3 = 201.749
(gdb) print (31415.0/10000.0)
$4 = 3.1414999999999999
```

这只是最基本的，尽管你们大多数人都能用这个过得去。网上有大量的资源，这里有一些具体的资源可以帮助你开始。

1.  [gdb 简介](http://www.cs.cmu.edu/~gilpin/tutorial/)

1.  [GDB 手册](https://ftp.gnu.org/old-gnu/Manuals/gdb/html_node/gdb_toc.html)

1.  [CppCon 2015: Greg Law “给我 15 分钟，我会改变你对 GDB 的看法”](https://www.youtube.com/watch?v=PorfLSr3DDI)

### Shell

你实际上是用什么来运行你的程序的？是 shell！shell 是一种运行在终端内的编程语言。终端只是一个输入命令的窗口。在 POSIX 系统中，我们通常有一个名为的 shell，它与一个符合 POSIX 规范的 shell 链接。大多数时候，你使用的是一个称为的 shell，它某种程度上符合 POSIX 规范，但有一些实用的内置功能。如果你想更高级，它有一些更强大的功能，比如程序上的 tab 补全和模糊模式。

### 未定义行为清理器

未定义行为清理器是 llvm 项目提供的一个奇妙工具。它允许你使用运行时检查器编译代码，以确保你不会对各种类别执行未定义行为。我们将尝试将其纳入我们的项目，但这需要所有外部库的支持，所以我们可能无法全部完成。[未定义行为清理器文档](https://clang.llvm.org/docs/UndefinedBehaviorSanitizer.html)

#### 未定义行为 - 为什么我们通常无法解决它

也请务必阅读 Chris Lattner 的关于未定义行为的 3 部分博客文章。它可以帮助你了解调试构建和编译器优化的神秘之处。

[每个 C 程序员都应该知道的事情](http://blog.llvm.org/2011/05/what-every-c-programmer-should-know.html)

### Clang 静态构建工具

Clang 提供了编译程序的出色替代工具。如果你想检查可能引起竞态条件、类型转换错误等错误，你只需要做以下操作。

```c
$ scan-build make
```

除了 make 输出之外，你还会得到静态构建警告。

### strace 和 ltrace

strace 和 ltrace 是两个程序，分别跟踪运行程序或命令的系统调用和库调用。这些可能在你的系统上缺失，所以为了安装，请运行以下命令：

```c
$ sudo apt install strace ltrace
```

使用 ltrace 进行调试可能就像找出最后一个失败的库调用的返回调用一样简单。

```c
int main() {
 FILE *fp = fopen("I don't exist", "r");
 fprintf(fp, "a");
 fclose(fp);
 return 0;
}
```

```c
> ltrace ./a.out
 __libc_start_main(0x8048454, 1, 0xbfc19db4, 0x80484c0, 0x8048530 <unfinished ...>
 fopen("I don't exist", "r")                          = 0x0
 fwrite("Invalid Write\n", 1, 14, 0x0 <unfinished ...>
 --- SIGSEGV (Segmentation fault) ---
 +++ killed by SIGSEGV +++
```

ltrace 输出可以让你了解程序在运行时所做的奇怪事情。不幸的是，ltrace 不能用来注入故障，这意味着 ltrace 可以告诉你正在发生什么，但它不能干扰已经发生的事情。

另一方面，`strace`可以修改你的程序。使用`strace`进行调试非常神奇。基本用法是运行带有程序的`strace`，它会给你一个完整的系统调用参数列表。

```c
$ strace head README.md
execve("/usr/bin/head", ["head", "README.md"], 0x7ffff28c8fa8 /* 60 vars */) = 0
brk(NULL)                               = 0x7ffff5719000
access("/etc/ld.so.nohwcap", F_OK)      = -1 ENOENT (No such file or directory)
access("/etc/ld.so.preload", R_OK)      = -1 ENOENT (No such file or directory)
openat(AT_FDCWD, "/etc/ld.so.cache", O_RDONLY|O_CLOEXEC) = 3
fstat(3, {st_mode=S_IFREG|0644, st_size=32804, ...}) = 0
...
```

如果输出太冗长，你可以使用`trace=`与以命令分隔的 syscalls 列表来过滤除了那些调用之外的所有调用。

```c
$ strace -e trace=read,write head README.md
read(3, "\177ELF\2\1\1\3\0\0\0\0\0\0\0\0\3\0>\0\1\0\0\0\260\34\2\0\0\0\0\0"..., 832) = 832
read(3, "# Locale name alias data base.\n#"..., 4096) = 2995
read(3, "", 4096)                       = 0
read(3, "# C Datastructures\n\n[![Build Sta"..., 8192) = 1250
write(1, "# C Datastructures\n", 19# C Datastructures
```

你也可以跟踪文件或目标。

```c
$ strace -e trace=read,write -P README.md head README.md
strace: Requested path 'README.md' resolved into '/mnt/c/Users/user/personal/libds/README.md'
read(3, "# C Datastructures\n\n[![Build Sta"..., 8192) = 1250
```

更新版本的`strace`实际上可以注入故障到你的程序中。当你想偶尔让读取和写入失败时，例如在网络应用程序中，你的程序应该处理这种情况，这很有用。问题是截至 2019 年初，这个版本在 Ubuntu 仓库中缺失。这意味着你将不得不从源代码安装它。

### `printfs`

当所有其他方法都失败时，打印！每个函数都应该有一个关于它将要做什么的想法。你想要测试每个函数是否真的做了它打算做的事情，并确切地看到你的代码在哪里出错。在竞争条件的情况下，tsan 可能有所帮助，但每个线程在特定时间打印数据可以帮助你识别竞争条件。

为了使`printf`函数更有用，尝试创建一个宏，通过它填充调用`printf`时的上下文——即日志语句。一个简单但未经验证的日志语句可能如下所示。尝试进行测试，找出出错的原因，然后记录变量的状态。

```c
 #include <execinfo.h>
 #include <stdio.h>
 #include <stdlib.h>
 #include <stdarg.h>
 #include <unistd.h>

 // bt is print backtrace
 const int num_stack = 10;
 int __log(int line, const char *file, int bt, const char *fmt, ...) {
 if (bt) {
 void *raw_trace[num_stack];
 size_t size = backtrace(raw_trace, sizeof(raw_trace) / sizeof(raw_trace[0]));
 char **syms = backtrace_symbols(raw_trace, size);

 for(ssize_t i = 0; i < size; i++) {
 fprintf(stderr, "|%s:%d| %s\n", file, line, syms[i]);
 }
 free(syms);
 }
 int ret = fprintf(stderr, "|%s:%d| ", file, line);
 va_list args;
 va_start(args, fmt);
 ret += vfprintf(stderr, fmt, args);
 va_end(args);
 ret += fprintf(stderr, "\n");
 return ret;
 }

 #ifdef DEBUG
 #define log(...) __log(__LINE__, __FILE__, 0, __VA_ARGS__)
 #define bt(...) __log(__LINE__, __FILE__, 1, __VA_ARGS__)
 #else
 #define log(...)
 #define bt(...)
 #endif

 //Use as log(args like printf) or bt(args like printf) to either log or get backtrace

 int main() {
 log("Hello Log");
 bt("Hello Backtrace");
 }
```

然后根据需要使用。如果你对如何将 C 程序转换为机器代码有任何疑问，请查看附录中的编译和链接部分。

## 作业 0

```c
// First, can you guess which lyrics have been transformed into this C-like system code?
char q[] = "Do you wanna build a C99 program?";
#define or "go debugging with gdb?"
static unsigned int i = sizeof(or) != strlen(or);
char* ptr = "lathe";
size_t come = fprintf(stdout,"%s door", ptr+2);
int away = ! (int) * "";

int* shared = mmap(NULL, sizeof(int*), PROT_READ | PROT_WRITE, MAP_SHARED | MAP_ANONYMOUS, -1, 0);
munmap(shared,sizeof(int*));

if(!fork()) {
 execlp("man","man","-3","ftell", (char*)0); perror("failed");
}

if(!fork()) {
 execlp("make","make", "snowman", (char*)0); execlp("make","make", (char*)0));
}

exit(0);
```

### 所以你想掌握系统编程？并且得到比 B 更好的成绩？

```c
int main(int argc, char** argv) {
 puts("Great! We have plenty of useful resources for you, but it's up to you to");
 puts(" be an active learner and learn how to solve problems and debug code.");
 puts("Bring your near-completed answers the problems below");
 puts(" to the first lab to show that you've been working on this.");
 printf("A few \"don't knows\" or \"unsure\" is fine for lab 1.\n");
 puts("Warning: you and your peers will work hard in this class.");
 puts("This is not CS225; you will be pushed much harder to");
 puts(" work things out on your own.");
 fprintf(stdout,"This homework is a stepping stone to all future assignments.\n");
 char p[] = "So, you will want to clear up any confusions or misconceptions.\n";
 write(1, p, strlen(p) );
 char buffer[1024];
 sprintf(buffer,"For grading purposes, this homework 0 will be graded as part of your lab %d work.\n", 1);
 write(1, buffer, strlen(buffer));
 printf("Press Return to continue\n");
 read(0, buffer, sizeof(buffer));
 return 0;
}
```

### 观看视频并回答以下问题

**重要！**

浏览器中的虚拟机和 HW0 所需的视频在此处：

[`cs-education.github.io/sys/`](http://cs-education.github.io/sys/)

有问题？评论？请使用本学期的 CS341 Edstem：[`edstem.org/us/courses/61021/discussion/`](https://edstem.org/us/courses/61021/discussion/)

在浏览器中的虚拟机完全运行在 JavaScript 上，在 Chrome 中运行速度最快。请注意，当你重新加载页面时，VM 和任何你编写的代码都会被重置，**所以请将你的代码复制到单独的文档中**。视频后的挑战不是作业 0 的一部分，但通过实践而不是被动观看，你可以学到更多。每个视频结束时的挑战都很有趣。

HW0 问题如下。将你的答案复制到文本文档中，因为你稍后需要在课程中提交它们。

### 第一章

在其中，我们的英勇英雄与标准输出、标准错误、文件描述符以及写入文件进行斗争

1.  **Hello, World! (系统调用风格)** 编写一个程序，使用它打印出 "Hi! My name is <Your Name>"。

1.  **Hello, Standard Error Stream!** 编写一个函数，打印出高度为`n`的三角形到标准错误。你的函数应该具有以下签名，并使用`printf`。当`n = 3`时，三角形应如下所示：

    ```c
    *
    **
    ***
    ```

1.  **写入文件** 将你的程序从“Hello, World!”修改为写入一个名为的文件。确保使用正确的标志和正确的模式（是你的朋友）。

1.  **并非所有内容都是系统调用** 将你的程序从“写入文件”改为，并用. 替换。*确保打印到文件而不是标准输出！*

1.  和之间有哪些区别？

### 第二章

C 类型的大小和它们的限制、数组和指针递增

1.  一个字节中有多少位？

1.  一个中有多少字节？

1.  在你的机器上，以下有多少字节？， ， ， ， 和

1.  在一个 8 字节整数的机器上，变量的声明为。如果数据地址为，那么的地址是什么？

1.  在 C 中，什么与等价？提示：C 在解引用地址之前将其转换为什么？记住，字符串常量的类型是一个数组。

1.  为什么会出现 SEGFAULT？

    ```c
    char *ptr = "hello";
    *ptr = 'J';
    ```

1.  变量的值是多少？

    ```c
    ssize_t str_size = sizeof("Hello\0World")
    ```

1.  变量的值是多少？

    ```c
    ssize_t str_len = strlen("Hello\0World")
    ```

1.  给出一个例子，使得是 3。

1.  给出一个例子，使得在机器上可能是 4 或 8。

### 第三章

程序参数、环境变量以及与字符数组（字符串）一起工作

1.  至少有两种方法可以找到的长度？

1.  代表什么？

1.  环境变量指针存储在哪里（在栈上、在堆上、其他地方）？

1.  在指针为 8 字节的机器上，以下代码：

    ```c
    char *ptr = "Hello";
    char array[] = "Hello";
    ```

    什么是和的值？为什么？

1.  管理自动变量生命周期的数据结构是什么？

### 第四章

堆内存、栈内存以及与结构体一起工作

1.  如果我想在创建它的函数的生命周期结束后使用数据，我应该把它放在哪里？我该如何放置它？

1.  堆内存和栈内存之间的区别是什么？

1.  进程中还有其他类型的内存吗？

1.  填空：在好的 C 程序中，对于每个 malloc，都有一个 ___。

1.  为什么一个可能会失败？一个原因是什么？

1.  和之间有哪些区别？

1.  这段代码片段有什么问题？

    ```c
    free(ptr);
    free(ptr);
    ```

1.  这段代码片段有什么问题？

    ```c
    free(ptr);
    printf("%s\n", ptr);
    ```

1.  如何避免之前的两个错误？

1.  创建一个表示人的，然后创建一个，以便可以将替换为一个单词。一个人应包含以下信息：他们的名字（一个字符串）、他们的年龄（一个整数）以及他们的朋友列表（存储为指向 s 的指针数组的指针）。

1.  现在，在堆上创建两个人，分别是 128 岁和 256 岁的“Agent Smith”和“Sonny Moore”，他们互为朋友。创建创建和销毁 Person（Person 及其名称应位于堆上）的函数。

1.  应该接受一个名字和一个年龄。名字应该复制到堆上。使用 malloc 为每个人保留最多十个朋友的足够内存。确保初始化所有字段（为什么？）。

1.  应该释放人结构体的内存以及存储在堆上的所有属性。销毁一个人不会影响其他人。

### 第五章

使用 ， ， 和 进行文本输入输出和解析。

1.  可以使用哪些函数从和写入字符？

1.  提出一个与的问题。

1.  编写代码解析字符串"Hello 5 World"，并将 3 个变量初始化为"Hello"，5 和"World"。

1.  在包含之前，需要定义什么？

1.  编写一个 C 程序，使用逐行打印文件的内容。

### C 开发

这些是使用编译器和 git 编译和开发的一般性提示。这里的一些网络搜索会有所帮助。

1.  用于生成调试构建的编译器标志是什么？

1.  你修复了 Makefile 中的问题，并再次输入。解释为什么这不足以生成新的构建。

1.  在 Makefile 中的规则之后，使用制表符还是空格来缩进命令？

1.  什么是 do？在 git 的上下文中，a 是什么意思？

1.  show 你什么？

1.  tell 你什么？如果更改其内容，会如何改变其输出？

1.  什么是 do？为什么仅使用 commit 是不够的？

1.  非快进错误拒绝意味着什么？处理这种错误最常见的方法是什么？

### 可选：仅为了乐趣

+   将歌曲歌词转换为 System Programming 和本 wiki 书籍中涵盖的 C 代码，并在课程论坛上分享。

+   在你看来，网上最好的和最差的 C 代码是什么？请在课程论坛上发布链接。

+   编写一个包含故意细微 C 错误的短 C 程序，并在课程论坛上发布，看看其他人是否能发现你的错误。

+   你有没有听说过任何酷的/灾难性的系统编程错误？请随时与你的同学和课程工作人员在课程论坛上分享。

## 伊利诺伊大学具体指南

### 课程论坛

助教和学生助理会收到大量问题。有些是经过充分研究的，有些则不是。这是一份有用的指南，可以帮助你从后者转向前者。哦，我是否提到这是一个向实习经理得分的好方法？问问自己...

1.  我是否在我的虚拟机上运行？

1.  **我是否检查了手册页面？**

1.  我是否在课程论坛上搜索了类似的问题/后续问题？

1.  我是否完全阅读了 MP/实验室规范？

1.  我是否观看了所有的视频？

1.  如果需要，我是否搜索了错误消息及其变体？StackOverflow 呢？

1.  我是否尝试逐步注释、打印和/或逐步执行代码的一部分，以找出错误的确切位置？

1.  **我是否将代码提交到 git，以防助教需要更多上下文？**

1.  我是否在我的课程论坛帖子中包含了控制台/GDB/Valgrind 输出**以及**围绕错误的代码？

1.  我是否修复了与我遇到的问题无关的其他段错误？

1.  我是否遵循了良好的编程实践？（例如封装、限制重复的函数等）

当你在课程论坛上提问并希望快速得到答案时，我们可以给你提供的最大提示是**像尝试回答问题一样提问**。就像在提问之前，先尝试自己回答。如果你在考虑发布

> 嗨，我的代码得了 50 分

听起来很好也很礼貌，但课程工作人员更希望看到以下类似的帖子

> 嗨，我最近在测试 X、Y、Z 中失败了，这些测试大约占当前作业的一半。我注意到它们都与网络和 epoll 有关，但我无法弄清楚它们是如何相互关联的，或者我可能完全偏离了轨道。所以为了测试我的想法，我尝试用各种 get 和 put 请求启动了 1000 个客户端，并验证文件与它们的原始文件匹配。我在正常运行、调试构建、valgrind 或 tsan 时都无法让它失败。我没有收到任何警告，也没有任何预语法检查显示给我任何信息。你能告诉我我对失败的理解是否正确，以及我如何修改我的测试以更好地反映 X、Y、Z 吗？netid: bvenkat2

你不必表现得那么有礼貌，尽管我们会感激，但这会更快地得到回应。如果你试图回答这个问题，你会在问题正文中找到你需要的一切。
