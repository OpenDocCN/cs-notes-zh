# 网络，第四部分：构建一个简单的 TCP 服务器

## `htons`是什么，何时使用它？

整数可以以最低有效字节优先或最高有效字节优先表示。只要机器本身在内部一致，任何方法都是合理的。对于网络通信，我们需要在约定的格式上进行标准化。

`htons(xyz)`以网络字节顺序返回 16 位无符号整数“short”值 xyz。`htonl(xyz)`以网络字节顺序返回 32 位无符号整数“long”值 xyz。

这些函数被读作“主机到网络”；反向函数（ntohs、ntohl）将网络排序的字节值转换为主机排序。那么，主机排序是小端还是大端？答案是-这取决于您的机器！这取决于运行代码的主机的实际架构。如果架构恰好与网络排序相同，那么这些函数的结果就是参数。对于 x86 机器，主机和网络排序是不同的。

总结：无论何时读取或写入低级 C 网络结构（例如端口和地址信息），请记住使用上述函数确保正确转换为/从机器格式。否则，显示或指定的值可能是不正确的。

## 用于创建服务器的“大 4”网络调用是什么？

创建 TCP 服务器所需的四个系统调用是：`socket`、`bind`、`listen`和`accept`。每个都有特定的目的，并且应按上述顺序调用。

端口信息（由 bind 使用）可以手动设置（许多旧的仅 IPv4 的 C 代码示例都这样做），也可以使用`getaddrinfo`创建

我们稍后也会看到 setsockopt 的示例。

## 调用`socket`的目的是什么？

为网络通信创建一个端点。一个新的套接字本身并不特别有用；虽然我们已经指定了基于数据包或基于流的连接，但它并没有绑定到特定的网络接口或端口。相反，套接字返回一个网络描述符，可以在以后调用 bind、listen 和 accept 时使用。

## 调用`bind`的目的是什么

`bind`调用将抽象套接字与实际网络接口和端口关联起来。可以在 TCP 客户端上调用 bind，但通常不需要指定出站端口。

## 调用`listen`的目的是什么

`listen`调用指定了等待处理的传入连接的队列大小，即尚未被`accept`分配网络描述符的连接。高性能服务器的典型值为 128 或更多。

## 为什么服务器套接字是被动的？

服务器套接字不会主动尝试连接到另一个主机；相反，它们等待传入的连接。此外，当对等方断开连接时，服务器套接字不会关闭。相反，当远程客户端连接时，它会立即被转移到未使用的端口号以进行未来通信。

## 调用`accept`的目的是什么

一旦服务器套接字被初始化，服务器调用`accept`等待新的连接。与`socket`、`bind`和`listen`不同，这个调用将会阻塞。也就是说，如果没有新的连接，这个调用将会阻塞，只有当一个新的客户端连接时才会返回。

注意，`accept`调用返回一个新的文件描述符。这个文件描述符特定于特定的客户端。常见的编程错误是使用原始服务器套接字描述符进行服务器 I/O，然后惊讶地发现网络代码失败了。

## 创建 TCP 服务器的注意事项是什么？

+   使用被动服务器套接字的套接字描述符（如上所述）

+   未指定`getaddrinfo`的 SOCK_STREAM 要求

+   无法重用现有端口。

+   不初始化未使用的结构条目

+   如果端口当前正在使用，`bind`调用将失败

注意，端口是每台机器的，而不是每个进程或每个用户的。换句话说，当另一个进程使用该端口时，您不能使用端口 1234。更糟糕的是，默认情况下，端口在进程结束后会被“占用”。

## 服务器代码示例

下面是一个工作的简单服务器示例。请注意，此示例不完整 - 例如，它既不关闭套接字描述符，也不释放`getaddrinfo`创建的内存。

```cpp
#include <string.h>
#include <stdio.h>
#include <stdlib.h>
#include <sys/types.h>
#include <sys/socket.h>
#include <netdb.h>
#include <unistd.h>
#include <arpa/inet.h>

int main(int argc, char **argv)
{
    int s;
    int sock_fd = socket(AF_INET, SOCK_STREAM, 0);

    struct addrinfo hints, *result;
    memset(&hints, 0, sizeof(struct addrinfo));
    hints.ai_family = AF_INET;
    hints.ai_socktype = SOCK_STREAM;
    hints.ai_flags = AI_PASSIVE;

    s = getaddrinfo(NULL, "1234", &hints, &result);
    if (s != 0) {
            fprintf(stderr, "getaddrinfo: %s\n", gai_strerror(s));
            exit(1);
    }

    if (bind(sock_fd, result->ai_addr, result->ai_addrlen) != 0) {
        perror("bind()");
        exit(1);
    }

    if (listen(sock_fd, 10) != 0) {
        perror("listen()");
        exit(1);
    }

    struct sockaddr_in *result_addr = (struct sockaddr_in *) result->ai_addr;
    printf("Listening on file descriptor %d, port %d\n", sock_fd, ntohs(result_addr->sin_port));

    printf("Waiting for connection...\n");
    int client_fd = accept(sock_fd, NULL, NULL);
    printf("Connection made: client_fd=%d\n", client_fd);

    char buffer[1000];
    int len = read(client_fd, buffer, sizeof(buffer) - 1);
    buffer[len] = '\0';

    printf("Read %d chars\n", len);
    printf("===\n");
    printf("%s\n", buffer);

    return 0;
}
```

## 为什么我的服务器不能重用端口？

默认情况下，当套接字关闭时，端口不会立即释放。相反，端口会进入“TIMED-WAIT”状态。这可能会在开发过程中导致重大混乱，因为超时可能会使有效的网络代码看起来失败。

要能够立即重用端口，需要在绑定端口之前指定`SO_REUSEPORT`。

```cpp
int optval = 1;
setsockopt(sfd, SOL_SOCKET, SO_REUSEPORT, &optval, sizeof(optval));

bind(....
```

这里是[一个关于`SO_REUSEPORT`的扩展 stackoverflow 入门讨论](http://stackoverflow.com/questions/14388706/socket-options-so-reuseaddr-and-so-reuseport-how-do-they-differ-do-they-mean-t)。
