# 网络，第七部分：非阻塞 I/O，select()和 epoll

### 不要浪费时间等待

通常，当你调用`read()`时，如果数据尚不可用，它将等待数据准备就绪后再返回。当你从磁盘读取数据时，这种延迟可能不会很长，但当你从一个慢速网络连接中读取数据时，如果数据到达的话，可能需要很长时间。

POSIX 允许你在文件描述符上设置一个标志，以便对该文件描述符的任何`read()`调用都会立即返回，无论它是否已经完成。在这种模式下，你的`read()`调用将启动读取操作，而在它工作时，你可以做其他有用的工作。这被称为“非阻塞”模式，因为`read()`的调用不会阻塞。

要将文件描述符设置为非阻塞：

```cpp
    // fd is my file descriptor
    int flags = fcntl(fd, F_GETFL, 0);
    fcntl(fd, F_SETFL, flags | O_NONBLOCK);
```

对于套接字，你可以通过将`SOCK_NONBLOCK`添加到`socket()`的第二个参数来以非阻塞模式创建它。

```cpp
    fd = socket(AF_INET, SOCK_STREAM | SOCK_NONBLOCK, 0);
```

当文件处于非阻塞模式时，你调用`read()`，它将立即返回可用的字节。假设从套接字的另一端的服务器已经到达了 100 个字节，你调用`read(fd, buf, 150)`。`read`将立即返回值 100，表示它读取了你要求的 150 个字节中的 100 个。假设你尝试通过调用`read(fd, buf+100, 50)`来读取剩余的数据，但是最后的 50 个字节还没有到达。`read()`将返回-1，并将全局错误变量**errno**设置为 EAGAIN 或 EWOULDBLOCK。这是系统告诉你数据还没有准备好的方式。

`write()`也可以在非阻塞模式下工作。假设你想使用套接字向远程服务器发送 40,000 字节。系统一次只能发送这么多字节。通常系统一次可以发送大约 23,000 字节。在非阻塞模式下，`write(fd, buf, 40000)`将返回它立即能够发送的字节数，大约为 23,000。如果你立即再次调用`write()`，它将返回-1，并将 errno 设置为 EAGAIN 或 EWOULDBLOCK。这是系统告诉你它仍在忙于发送最后一块数据，并且还没有准备好发送更多数据。

### 如何检查 I/O 何时完成？

有几种方法。让我们看看如何使用*select*和*epoll*来做。

#### select

```cpp
    int select(int nfds, 
               fd_set *readfds, 
               fd_set *writefds,
               fd_set *exceptfds, 
               struct timeval *timeout);
```

给定三组文件描述符，`select()`将等待其中任何一个文件描述符变为“准备就绪”。

+   `readfds` - 在`readfds`中的文件描述符在有可读数据或已达到 EOF 时准备就绪。

+   `writefds` - 在`writefds`中的文件描述符在调用 write()时将会成功。

+   `exceptfds` - 系统特定，定义不清晰。只需将其传递为 NULL。

`select()`返回准备就绪的文件描述符的总数。如果它们在*timeout*定义的时间内没有准备好，它将返回 0。在`select()`返回后，调用者需要循环遍历 readfds 和/或 writefds 中的文件描述符，以查看哪些是准备好的。由于 readfds 和 writefds 充当输入和输出参数，当`select()`指示有准备好的文件描述符时，它会覆盖它们以反映只有准备好的文件描述符。除非调用者的意图是只调用一次`select()`，否则在调用它之前保存 readfds 和 writefds 的副本是个好主意。

```cpp
    fd_set readfds, writefds;
    FD_ZERO(&readfds);
    FD_ZERO(&writefds);
    for (int i=0; i < read_fd_count; i++)
      FD_SET(my_read_fds[i], &readfds);
    for (int i=0; i < write_fd_count; i++)
      FD_SET(my_write_fds[i], &writefds);

    struct timeval timeout;
    timeout.tv_sec = 3;
    timeout.tv_usec = 0;

    int num_ready = select(FD_SETSIZE, &readfds, &writefds, NULL, &timeout);

    if (num_ready < 0) {
      perror("error in select()");
    } else if (num_ready == 0) {
      printf("timeout\n");
    } else {
      for (int i=0; i < read_fd_count; i++)
        if (FD_ISSET(my_read_fds[i], &readfds))
          printf("fd %d is ready for reading\n", my_read_fds[i]);
      for (int i=0; i < write_fd_count; i++)
        if (FD_ISSET(my_write_fds[i], &writefds))
          printf("fd %d is ready for writing\n", my_write_fds[i]);
    }
```

[有关 select()的更多信息](http://pubs.opengroup.org/onlinepubs/9699919799/functions/select.html)

## epoll

*epoll*不是 POSIX 的一部分，但它受 Linux 支持。这是一种更有效的等待多个文件描述符的方式。它会告诉你哪些描述符准备好了。它甚至可以为每个描述符存储少量数据，比如数组索引或指针，使得更容易访问与该描述符相关的数据。

使用 epoll，首先您必须使用[epoll_create()](http://linux.die.net/man/2/epoll_create)创建一个特殊的文件描述符。您不会读取或写入此文件描述符；您只需将其传递给其他 epoll_xxx 函数，并在最后调用 close()。

```cpp
    epfd = epoll_create(1);
```

对于要使用 epoll 监视的每个文件描述符，您需要使用[epoll_ctl()](http://linux.die.net/man/2/epoll_ctl)和`EPOLL_CTL_ADD`选项将其添加到 epoll 数据结构中。您可以向其中添加任意数量的文件描述符。

```cpp
    struct epoll_event event;
    event.events = EPOLLOUT;  // EPOLLIN==read, EPOLLOUT==write
    event.data.ptr = mypointer;
    epoll_ctl(epfd, EPOLL_CTL_ADD, mypointer->fd, &event)
```

要等待某些文件描述符准备就绪，请使用[epoll_wait()](http://linux.die.net/man/2/epoll_wait)。它填充的 epoll_event 结构将包含您在添加此文件描述符时提供的 event.data 中的数据。这使您可以轻松查找与此文件描述符关联的自己的数据。

```cpp
    int num_ready = epoll_wait(epfd, &event, 1, timeout_milliseconds);
    if (num_ready > 0) {
      MyData *mypointer = (MyData*) event.data.ptr;
      printf("ready to write on %d\n", mypointer->fd);
    }
```

假设您正在等待向文件描述符写入数据，但现在您想要等待从中读取数据。只需使用`epoll_ctl()`和`EPOLL_CTL_MOD`选项来更改您正在监视的操作类型。

```cpp
    event.events = EPOLLOUT;
    event.data.ptr = mypointer;
    epoll_ctl(epfd, EPOLL_CTL_MOD, mypointer->fd, &event);
```

要取消订阅一个文件描述符，同时保持其他文件描述符处于活动状态，请使用`epoll_ctl()`和`EPOLL_CTL_DEL`选项。

```cpp
    epoll_ctl(epfd, EPOLL_CTL_DEL, mypointer->fd, NULL);
```

要关闭 epoll 实例，请关闭其文件描述符。

```cpp
    close(epfd);
```

除了非阻塞的`read()`和`write()`之外，对非阻塞套接字上的任何`connect()`调用也将是非阻塞的。要等待连接完成，请使用`select()`或 epoll 等待套接字可写。

## 有关 select 的边缘情况的有趣博文

[`idea.popcount.org/2017-01-06-select-is-fundamentally-broken/`](https://idea.popcount.org/2017-01-06-select-is-fundamentally-broken/)
