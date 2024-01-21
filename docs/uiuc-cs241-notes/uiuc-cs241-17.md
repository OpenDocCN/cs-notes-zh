# 分叉，第二部分：分叉，执行，等待

## 模式

## 以下的'exec'示例是做什么的？

```cpp
#include <unistd.h>
#include <fcntl.h> // O_CREAT, O_APPEND etc. defined here

int main() {
   close(1); // close standard out
   open("log.txt", O_RDWR | O_CREAT | O_APPEND, S_IRUSR | S_IWUSR);
   puts("Captain's log");
   chdir("/usr/include");
   // execl( executable,  arguments for executable including program name and NULL at the end)

   execl("/bin/ls", /* Remaining items sent to ls*/ "/bin/ls", ".", (char *) NULL); // "ls ."
   perror("exec failed");
   return 0; // Not expected
}
```

上述代码中没有错误检查（我们假设 close、open、chdir 等都按预期工作）。

+   open：将使用最低可用的文件描述符（即 1）；因此标准输出现在转到日志文件。

+   chdir：将当前目录更改为/usr/include

+   execl：用/bin/ls 替换程序图像，并调用它的 main()方法

+   perror：我们不希望到达这里 - 如果到达了，那么 exec 失败了。

## 微妙的 fork 炸弹错误

这段代码有什么问题

```cpp
#include <unistd.h>
#define HELLO_NUMBER 10

int main(){
    pid_t children[HELLO_NUMBER];
    int i;
    for(i = 0; i < HELLO_NUMBER; i++){
        pid_t child = fork();
        if(child == -1){
            break;
        }
        if(child == 0){ //I am the child
             execlp("ehco", "echo", "hello", NULL);
        }
        else{
            children[i] = child;
        }
    }

    int j;
    for(j = 0; j < i; j++){
        waitpid(children[j], NULL, 0);
    }
    return 0;
}

```

我们拼错了`ehco`，所以我们无法`exec`它。这是什么意思？我们只创建了 2**10 个进程，而不是 10 个进程，炸毁了我们的机器。我们如何防止这种情况？在 exec 后立即放置一个退出，这样如果 exec 失败，我们就不会炸毁我们的机器。

## 子进程从父进程继承了什么？

+   打开文件句柄。如果父进程稍后寻求，比如，回到文件的开头，那么这也会影响子进程（反之亦然）。

+   信号处理程序

+   当前工作目录

+   环境变量

有关更多详细信息，请参阅[fork man page](http://linux.die.net/man/2/fork)。

## 子进程与父进程有什么不同？

进程 ID 是不同的。在子进程中调用`getppid()`（注意两个'p'）将得到与在父进程中调用 getpid()相同的结果。有关更多详细信息，请参阅 fork man page。

## 我如何等待我的子进程完成？

使用`waitpid`或`wait`。父进程将暂停，直到`wait`（或`waitpid`）返回。请注意，此解释忽略了重新启动的讨论。

## fork-exec-wait 模式是什么

一个常见的编程模式是调用`fork`，然后是`exec`和`wait`。原始进程调用 fork，创建一个子进程。然后子进程使用 exec 来启动一个新程序的执行。与此同时，父进程使用`wait`（或`waitpid`）来等待子进程完成。请参阅下面的完整代码示例。

## 我如何启动一个同时运行的后台进程？

不要等待它们！您的父进程可以继续执行代码，而无需等待子进程。请注意，在实践中，通过在调用 exec 之前关闭打开的文件描述符，后台进程也可以与父进程的输入和输出流断开连接。

然而，在父进程完成之前完成的子进程可能会变成僵尸。有关更多信息，请参阅僵尸页面。

## 僵尸

## 好的父母不会让他们的孩子变成僵尸！

当一个子进程完成（或终止）时，它仍然占据内核进程表中的一个槽。只有在子进程被“等待”后，该槽才会再次可用。

一个长时间运行的程序可能会通过不断创建进程而永远不等待它们来创建许多僵尸。

## 太多僵尸会有什么影响？

最终，内核进程表中会没有足够的空间来创建新进程。因此，`fork()`会失败，并且可能使系统难以/无法使用 - 例如，仅登录就需要一个新进程！

## 系统如何帮助防止僵尸？

一旦一个进程完成，它的任何子进程都将被分配给“init” - 具有 pid 为 1 的第一个进程。因此，这些子进程将看到 getppid()返回值为 1。这些孤儿最终会完成，并在短暂的时刻成为僵尸。幸运的是，init 进程会自动等待它的所有子进程，从而将这些僵尸从系统中移除。

## 我如何防止僵尸？（警告：简化的答案）

等待你的孩子！

```cpp
waitpid(child, &status, 0); // Clean up and wait for my child process to finish.
```

请注意，我们假设获得 SIGCHLD 事件的唯一原因是子进程已经完成（这并不完全正确 - 有关更多详细信息，请参阅 man page）。

一个健壮的实现还会检查中断状态，并在循环中包含上述内容。继续阅读，了解更健壮的实现的讨论。

## 我如何使用 SIGCHLD 异步等待我的子进程？（高级）

警告：本节使用了我们尚未完全介绍的信号。当子进程完成时，父进程会收到 SIGCHLD 信号，因此信号处理程序可以等待该进程。下面显示了一个稍微简化的版本。

```cpp
pid_t child;

void cleanup(int signal) {
  int status;
  waitpid(child, &status, 0);
  write(1,"cleanup!\n",9);
}
int main() {
   // Register signal handler BEFORE the child can finish
   signal(SIGCHLD, cleanup); // or better - sigaction
   child = fork();
   if (child == -1) { exit(EXIT_FAILURE);}

   if (child == 0) { /* I am the child!*/
     // Do background stuff e.g. call exec 
   } else { /* I'm the parent! */
      sleep(4); // so we can see the cleanup
      puts("Parent is done");
   }
   return 0;
} 
```

然而，上面的例子忽略了一些微妙的地方：

+   可能有多个子进程已经完成，但父进程只会收到一个 SIGCHLD 信号（信号不会排队）

+   SIGCHLD 信号可能是因为其他原因而发送的（例如，子进程暂时停止）

下面显示了一个更健壮的代码来清除僵尸进程。

```cpp
void cleanup(int signal) {
  int status;
  while (waitpid((pid_t) (-1), 0, WNOHANG) > 0) {}
}
```

## 那么什么是环境变量？

环境变量是系统为所有进程保留的变量。您的系统现在已经设置了这些！在 Bash 中，您可以检查其中一些

```cpp
$ echo $HOME
/home/bhuvy
$ echo $PATH
/usr/local/sbin:/usr/bin:... 
```

如何在 C/C++中获取这些？您可以使用`getenv`和`setenv`函数

```cpp
char* home = getenv("HOME"); // Will return /home/bhuvy
setenv("HOME", "/home/bhuvan", 1 /*set overwrite to true*/ );
```

## 那么这些环境变量对父进程/子进程有什么意义呢？

每个进程都有自己的环境变量字典，这些变量会被复制到子进程中。这意味着，如果父进程更改其环境变量，它不会传递给子进程，反之亦然。如果您想要使用不同的环境变量执行程序，这在 fork-exec-wait 三部曲中很重要。

例如，您可以编写一个 C 程序，循环遍历所有时区，并执行`date`命令以打印出所有本地的日期和时间。环境变量用于各种程序，因此修改它们很重要。


