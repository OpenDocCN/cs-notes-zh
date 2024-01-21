# 管道，第二部分：管道编程秘密

## 管道陷阱

这里有一个完整的例子，但不起作用！子进程每次从管道中读取一个字节并打印出来-但我们从未看到消息！你能看出原因吗？

```cpp
#include <stdio.h>
#include <stdlib.h>
#include <unistd.h>
#include <signal.h>

int main() {
    int fd[2];
    pipe(fd);
    //You must read from fd[0] and write from fd[1]
    printf("Reading from %d, writing to %d\n", fd[0], fd[1]);

    pid_t p = fork();
    if (p > 0) {
        /* I have a child therefore I am the parent*/
        write(fd[1],"Hi Child!",9);

        /*don't forget your child*/
        wait(NULL);
    } else {
        char buf;
        int bytesread;
        // read one byte at a time.
        while ((bytesread = read(fd[0], &buf, 1)) > 0) {
            putchar(buf);
        }
    }
    return 0;
}

```

父进程将字节`H,i,(空格),C...!`发送到管道中（如果管道已满，可能会阻塞）。子进程开始逐个字节读取管道。在上面的情况下，子进程将读取并打印每个字符。但它永远不会离开 while 循环！当没有字符可读时，它会简单地阻塞并等待更多。

调用`putchar`写出字符，但我们从未刷新`stdout`缓冲区。也就是说，我们已经将消息从一个进程传输到另一个进程，但它还没有被打印出来。要查看消息，我们可以刷新缓冲区，例如`fflush(stdout)`（或者如果输出是到终端，则`printf("\n")`）。更好的解决方案还可以通过检查消息结束标记来退出循环，

```cpp
        while ((bytesread = read(fd[0], &buf, 1)) > 0) {
            putchar(buf);
            if (buf == '!') break; /* End of message */
        }
```

当子进程退出时，消息将被刷新到终端。

## 想要使用 printf 和 scanf 与管道吗？使用 fdopen！

POSIX 文件描述符是简单的整数 0,1,2,3...在 C 库级别，C 用缓冲区和有用的函数如 printf 和 scanf 包装这些，所以我们可以轻松地打印或解析整数、字符串等。如果你已经有了一个文件描述符，那么你可以使用`fdopen`将其自己“包装”成一个 FILE 指针：

```cpp
#include <sys/types.h>
#include <sys/stat.h>
#include <fcntl.h>

int main() {
    char *name="Fred";
    int score = 123;
    int filedes = open("mydata.txt", "w", O_CREAT, S_IWUSR | S_IRUSR);

    FILE *f = fdopen(filedes, "w");
    fprintf(f, "Name:%s Score:%d\n", name, score);
    fclose(f);
```

对于写入文件来说，这是不必要的-只需使用`fopen`，它与`open`和`fdopen`相同。但是对于管道，我们已经有了一个文件描述符-所以现在是使用`fdopen`的好时机！

这里有一个使用管道的完整例子，几乎可以工作！你能发现错误吗？提示：父进程从未打印任何内容！

```cpp
#include <unistd.h>
#include <stdlib.h>
#include <stdio.h>

int main() {
    int fh[2];
    pipe(fh);
    FILE *reader = fdopen(fh[0], "r");
    FILE *writer = fdopen(fh[1], "w");
    pid_t p = fork();
    if (p > 0) {
        int score;
        fscanf(reader, "Score %d", &score);
        printf("The child says the score is %d\n", score);
    } else {
        fprintf(writer, "Score %d", 10 + 10);
        fflush(writer);
    }
    return 0;
}
```

请注意，（未命名的）管道资源将在子进程和父进程都退出后消失。在上面的例子中，子进程将从管道发送字节，父进程将从管道接收字节。然而，从未发送换行符，因此`fscanf`将继续请求字节，因为它正在等待行结束，即它将永远等待！修复方法是确保我们发送一个换行符，这样`fscanf`将返回。

```cpp
change:   fprintf(writer, "Score %d", 10 + 10);
to:       fprintf(writer, "Score %d\n", 10 + 10);
```

## 那我们也需要`fflush`吗？

是的，如果你希望你的字节立即发送到管道中！在本课程开始时，我们假设文件流始终是*行缓冲*，即 C 库每次发送换行符时都会刷新其缓冲区。实际上，这只对终端流有效-对于其他文件流，C 库尝试通过仅在其内部缓冲区满或文件关闭时刷新来提高性能。

## 我什么时候需要两个管道？

如果你需要异步地向子进程发送和接收数据，那么需要两个管道（每个方向一个）。否则，子进程将尝试读取自己的数据，这些数据是为父进程准备的（反之亦然）！

## 关闭管道的陷阱

当没有进程在监听时，进程会收到信号 SIGPIPE！来自 pipe(2)手册页-

```cpp
If all file descriptors referring to the read end of a pipe have been closed,
 then a write(2) will cause a SIGPIPE signal to be generated for the calling process. 
```

提示：注意只有写入者（不是读取者）可以使用此信号。为了通知读取者写入者正在关闭管道的端口，你可以写入自己的特殊字节（例如 0xff）或消息（`"再见！"`）

这里有一个捕捉这个信号的例子，但不起作用！你能看出原因吗？

```cpp
#include <stdio.h>
#include <stdio.h>
#include <unistd.h>
#include <signal.h>

void no_one_listening(int signal) {
    write(1, "No one is listening!\n", 21);
}

int main() {
    signal(SIGPIPE, no_one_listening);
    int filedes[2];

    pipe(filedes);
    pid_t child = fork();
    if (child > 0) { 
        /* I must be the parent. Close the listening end of the pipe */
        /* I'm not listening anymore!*/
        close(filedes[0]);
    } else {
        /* Child writes messages to the pipe */
        write(filedes[1], "One", 3);
        sleep(2);
        // Will this write generate SIGPIPE ?
        write(filedes[1], "Two", 3);
        write(1, "Done\n", 5);
    }
    return 0;
}
```

上面代码中的错误是仍然有一个管道的读取者！子进程仍然保持着管道的第一个文件描述符，并记住规范？所有读取者必须关闭。

在分叉时，*关闭子进程和父进程中每个管道的不必要（未使用）端口是常见做法。例如，父进程可能关闭读取端口，子进程可能关闭写入端口（如果有两个管道，则反之亦然）

## 是什么填满了管道？当管道变满时会发生什么？

当写入者向管道写入过多而读者没有读取时，管道会被填满。当管道变满时，所有写入都会失败，直到发生读取。即使在这种情况下，如果管道还有一点空间但不足以容纳整个消息，写入也可能部分失败。

为了避免这种情况，通常有两种方法。要么增加管道的大小。或者更常见的是，修复你的程序设计，使得管道不断被读取。

## 管道是否进程安全？

是的！管道写入是原子的，直到管道的大小。这意味着如果两个进程尝试写入同一个管道，内核会使用管道的内部互斥锁来锁定，进行写入，然后返回。唯一需要注意的是当管道即将变满时。如果两个进程尝试写入，而管道只能满足部分写入，那么该管道写入就不是原子的--要小心！

## 管道的生命周期

无名管道（到目前为止我们见过的那种）存在于内存中（不占用任何磁盘空间），是一种简单高效的进程间通信（IPC）形式，对于流数据和简单消息非常有用。一旦所有进程关闭，管道资源就会被释放。

使用`mkfifo`创建*命名*管道是*无名*管道的一种替代方法。

## 命名管道

## 我如何创建命名管道？

从命令行：`mkfifo` 从 C 语言：`int mkfifo(const char *pathname, mode_t mode);`

你给它路径名和操作模式，它就准备好了！命名管道在磁盘上不占用空间。当操作系统告诉你有一个命名管道时，它实际上是在告诉你它会创建一个指向命名管道的无名管道，就是这样！没有额外的魔法。这只是为了编程方便，如果进程在没有分叉的情况下启动（这意味着无法为无名管道的子进程获取文件描述符）。

## 为什么我的管道挂起？

在命名管道上的读写会一直挂起，直到至少有一个读者和一个写者，记住这一点

```cpp
1$ mkfifo fifo
1$ echo Hello > fifo
# This will hang until I do this on another terminal or another process
2$ cat fifo
Hello
```

当在命名管道上调用任何`open`时，内核会阻塞，直到另一个进程调用相反的 open。也就是说，echo 调用`open(.., O_RDONLY)`，但是它会阻塞，直到 cat 调用`open(.., O_WRONLY)`，然后程序才被允许继续。

## 命名管道的竞争条件。

以下程序有什么问题？

```cpp
//Program 1

int main(){
    int fd = open("fifo", O_RDWR | O_TRUNC);
    write(fd, "Hello!", 6);
    close(fd);
    return 0;
}

//Program 2
int main() {
    char buffer[7];
    int fd = open("fifo", O_RDONLY);
    read(fd, buffer, 6);
    buffer[6] = '\0';
    printf("%s\n", buffer);
    return 0;
}
```

这可能永远不会打印 hello，因为存在竞争条件。由于你在第一个进程中以两种权限打开了管道，open 不会等待读者，因为你告诉操作系统你是读者！有时它看起来像是工作的，因为代码的执行看起来像这样。

| 进程 1 | 进程 2 |
| --- | --- |
| `open(O_RDWR) & write()` |  |
|  | `open(O_RDONLY) & read()` |
| `close() & exit()` |  |
|  | `print() & exit()` |

有时候不会

| 进程 1 | 进程 2 |
| --- | --- |
| `open(O_RDWR) & write()` |  |
| `close() & exit()` | （命名管道被销毁）
| （无限期阻塞）`open(O_RDONLY)` | |
