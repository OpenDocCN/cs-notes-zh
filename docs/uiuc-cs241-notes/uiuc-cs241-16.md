# 分叉，第一部分：介绍

## 警告

进程分叉是一个非常强大（也非常危险）的工具。如果出错并导致分叉炸弹（稍后在本页解释），**你可能会导致整个系统崩溃**。为了减少这种可能性，通过在命令行中输入`ulimit -u 40`来将最大进程数限制为一个小数字，例如 40。请注意，此限制仅适用于用户，这意味着如果你引发了分叉炸弹，那么你将无法杀死你刚刚创建的所有进程，因为调用`killall`需要你的 shell 来`fork()`...讽刺吧？那么我们该怎么办呢？一个解决方案是提前生成另一个用户（例如 root）的另一个 shell 实例并从那里杀死进程。另一个方法是使用内置的`exec`命令杀死所有用户进程（小心，你只有一次机会）。最后，你可以重新启动系统 :)

在测试`fork()`代码时，请确保你有根用户和/或物理访问权限。如果你必须远程处理`fork()`代码，请记住，在紧急情况下**kill -9 -1**会帮助你。

总结：如果你没有准备好，`fork`可能会**非常**危险。**你已经被警告过了。**

## 分叉介绍

## `fork`做什么？

`fork`系统调用克隆当前进程以创建一个新进程。它通过复制现有进程的状态创建一个新进程（子进程），有一些细微的差异（下面讨论）。子进程不是从 main 开始。相反，它像父进程一样从`fork()`返回。

## 什么是最简单的`fork()`例子？

这是一个非常简单的例子...

```cpp
printf("I'm printed once!\n");
fork();
// Now there are two processes running
// and each process will print out the next line.
printf("You see this line twice!\n");
```

## 为什么这个例子会打印两次 42？

以下程序打印出 42 两次 - 但`fork()`在`printf`之后！？为什么？

```cpp
#include <unistd.h> /*fork declared here*/
#include <stdio.h> /* printf declared here*/
int main() {
   int answer = 84 >> 1;
   printf("Answer: %d", answer);
   fork();
   return 0;
}
```

`printf`行*只执行一次，但请注意打印的内容没有刷新到标准输出（没有打印换行，我们没有调用`fflush`或更改缓冲模式）。因此，输出文本仍然在进程内存中等待发送。当执行`fork()`时，整个进程内存被复制，包括缓冲区。因此，子进程从一个非空输出缓冲区开始，该缓冲区将在程序退出时刷新。

## 如何编写针对父进程和子进程不同的代码？

检查`fork()`的返回值。返回值`-1` = 失败；`0` = 在子进程中；正数 = 在父进程中（返回值是子进程 id）。以下是记住哪个是哪个的一种方法：

子进程可以通过调用`getppid()`找到其父进程 - 被复制的原始进程 - 因此不需要从`fork()`获得任何额外的返回信息。然而，父进程只能从`fork`的返回值中找到新子进程的 id：

```cpp
pid_t id = fork();
if (id == -1) exit(1); // fork failed 
if (id > 0)
{ 
// I'm the original parent and 
// I just created a child process with id 'id'
// Use waitpid to wait for the child to finish
} else { // returned zero
// I must be the newly made child process
}
```

## 什么是分叉炸弹？

'分叉炸弹'是指尝试创建无限数量的进程。下面是一个简单的例子：

```cpp
while (1) fork();
```

这通常会使系统几乎停滞，因为它试图为大量准备运行的进程分配 CPU 时间和内存。评论：系统管理员不喜欢分叉炸弹，可能会设置每个用户可以拥有的进程数量的上限，或者可能会撤销登录权限，因为它会为其他用户的程序带来麻烦。你也可以使用`setrlimit()`来限制创建的子进程数量。

分叉炸弹并不一定是恶意的 - 它们偶尔会由于学生编码错误而发生。

Angrave 建议《黑客帝国》三部曲，机器和人最终共同努力击败不断增殖的 Agent-Smith，是基于一个基于 AI 驱动的分叉炸弹的电影情节。

## 等待和执行

## 父进程如何等待子进程完成？

使用`waitpid`（或`wait`）。

```cpp
pid_t child_id = fork();
if (child_id == -1) { perror("fork"); exit(EXIT_FAILURE);}
if (child_id > 0) { 
  // We have a child! Get their exit code
  int status; 
  waitpid( child_id, &status, 0 );
  // code not shown to get exit status from child
} else { // In child ...
  // start calculation
  exit(123);
}
```

## 我可以让子进程执行另一个程序吗？

是的。在 fork 后使用其中一个[`exec`](http://man7.org/linux/man-pages/man3/exec.3.html)函数。`exec`函数集用正在调用的进程映像替换进程映像。这意味着`exec`调用后的任何代码行都将被替换。任何其他要求子进程执行的工作都应该在`exec`调用之前完成。

[Wikipedia 文章](https://en.wikipedia.org/wiki/Exec_(system_call)#C_language_prototypes)在帮助您理解 exec 系列名称方面做得很好。

命名方案可以缩短如下

> 每个的基础都是 exec（执行），后面跟着一个或多个字母：

> e - 指向环境变量的指针数组被显式传递给新的进程映像。

> l - 命令行参数被逐个传递（列表）给函数。

> p - 使用 PATH 环境变量来查找要执行的文件名。

> v - 命令行参数作为指针数组（向量）传递给函数。

```cpp
#include <unistd.h>
#include <sys/types.h> 
#include <sys/wait.h>
#include <stdlib.h>
#include <stdio.h>

int main(int argc, char**argv) {
  pid_t child = fork();
  if (child == -1) return EXIT_FAILURE;
  if (child) { /* I have a child! */
    int status;
    waitpid(child , &status ,0);
    return EXIT_SUCCESS;

  } else { /* I am the child */
    // Other versions of exec pass in arguments as arrays
    // Remember first arg is the program name
    // Last arg must be a char pointer to NULL

    execl("/bin/ls", "ls","-alh", (char *) NULL);

    // If we get to this line, something went wrong!
    perror("exec failed!");
  }
}
```

## 执行另一个程序的简单方法

使用`system`。以下是如何使用它的方法：

```cpp
#include <unistd.h>
#include <stdlib.h>

int main(int argc, char**argv) {
  system("ls");
  return 0;
}
```

`system`调用将分叉，执行由参数传递的命令，原始父进程将等待其完成。这也意味着`system`是一个阻塞调用：父进程在由`system`启动的进程退出之前无法继续。这可能有用，也可能没有。此外，`system`实际上创建了一个 shell，然后给出字符串，这比直接使用`exec`更耗费资源。标准 shell 将使用`PATH`环境变量搜索与命令匹配的文件名。对于许多简单的运行此命令问题，使用 system 通常足够了，但对于更复杂或微妙的问题，它可能很快变得有限，并且它隐藏了分叉-执行-等待模式的机制，因此我们鼓励您学习并使用`fork` `exec`和`waitpid`。

## 最愚蠢的 fork 示例是什么？

下面显示了一个稍微愚蠢的例子。它会打印什么？尝试使用多个参数运行您的程序。

```cpp
#include <unistd.h>
#include <stdio.h>
int main(int argc, char **argv) {
  pid_t id;
  int status; 
  while (--argc && (id=fork())) {
    waitpid(id,&status,0); /* Wait for child*/
  }
  printf("%d:%s\n", argc, argv[argc]);
  return 0;
}
```

令人惊奇的并行明显 O(N) *sleepsort*是今天的愚蠢赢家。首次发布于[2011 年的 4chan](https://dis.4chan.org/read/prog/1295544154)。下面显示了这种糟糕但有趣的排序算法的一个版本。

```cpp
int main(int c, char **v)
{
        while (--c > 1 && !fork());
        int val  = atoi(v[c]);
        sleep(val);
        printf("%d\n", val);
        return 0;
}
```

注意：由于系统调度程序的工作方式，该算法实际上并不是 O(N)。虽然有并行算法可以在每个进程中以 O(log(N))运行，但这不幸地不是其中之一。

## 子进程与父进程有什么不同？

关键区别包括：

+   由`getpid()`返回的进程 ID。由`getppid()`返回的父进程 ID。

+   当子进程完成时，父进程通过信号 SIGCHLD 被通知，但反之则不然。

+   子进程不会继承未决信号或定时器警报。完整列表请参阅[fork man page](http://man7.org/linux/man-pages/man2/fork.2.html)

## 子进程共享打开的文件句柄吗？

是的！实际上，两个进程都使用相同的底层内核文件描述符。例如，如果一个进程将随机访问位置倒回到文件的开头，那么两个进程都会受到影响。

子进程和父进程都应该`close`（或`fclose`）它们的文件描述符或文件句柄。

## 如何获取更多信息？

阅读 man 页面！

+   [fork](http://man7.org/linux/man-pages/man2/fork.2.html)

+   [exec](http://man7.org/linux/man-pages/man3/exec.3.html)

+   [wait](http://man7.org/linux/man-pages/man2/wait.2.html)


