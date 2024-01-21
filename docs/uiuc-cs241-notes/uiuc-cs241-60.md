# 网络，第六部分：创建 UDP 服务器

## 如何创建 UDP 服务器？

有各种可用的函数调用来发送 UDP 套接字。我们将使用较新的 getaddrinfo 来帮助设置套接字结构。

请记住，UDP 是一个简单的基于数据包的协议；两个主机之间没有建立连接。

首先，初始化 hints addrinfo 结构以请求一个 IPv6，被动数据报套接字。

```cpp
memset(&hints, 0, sizeof(hints));
hints.ai_family = AF_INET6; // INET for IPv4
hints.ai_socktype =  SOCK_DGRAM;
hints.ai_flags =  AI_PASSIVE;
```

接下来，使用 getaddrinfo 来指定端口号（我们不需要指定主机，因为我们正在创建一个服务器套接字，而不是向远程主机发送数据包）。

```cpp
getaddrinfo(NULL, "300", &hints, &res);

sockfd = socket(res->ai_family, res->ai_socktype, res->ai_protocol);
bind(sockfd, res->ai_addr, res->ai_addrlen);
```

端口号是<1024，所以程序将需要`root`权限。我们也可以指定一个服务名称，而不是一个数字端口值。

到目前为止，调用与 TCP 服务器类似。对于基于流的服务，我们将调用`listen`和`accept`。对于我们的 UDP 服务器，我们可以开始等待套接字上数据包的到达。

```cpp
struct sockaddr_storage addr;
int addrlen = sizeof(addr);

// ssize_t recvfrom(int socket, void* buffer, size_t buflen, int flags, struct sockaddr *addr, socklen_t * address_len);

byte_count = recvfrom(sockfd, buf, sizeof(buf), 0, &addr, &addrlen);
```

addr 结构将保存有关到达数据包的发送者（源）信息。请注意，`sockaddr_storage`类型足够大，可以容纳所有可能类型的套接字地址（例如 IPv4、IPv6 和其他套接字类型）。

## 完整代码

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

    struct addrinfo hints, *result;
    memset(&hints, 0, sizeof(hints));
    hints.ai_family = AF_INET6; // INET for IPv4
    hints.ai_socktype =  SOCK_DGRAM;
    hints.ai_flags =  AI_PASSIVE;

    getaddrinfo(NULL, "300", &hints, &res);

    int sockfd = socket(res->ai_family, res->ai_socktype, res->ai_protocol);

    if (bind(sockfd, res->ai_addr, res->ai_addrlen) != 0) {
        perror("bind()");
        exit(1);
    }
    struct sockaddr_storage addr;
    int addrlen = sizeof(addr);

    while(1){
        char buffer[1000];
        ssize_t byte_count = recvfrom(sockfd, buf, sizeof(buf), 0, &addr, &addrlen);
        buffer[byte_count] = '\0';
    }

    printf("Read %d chars\n", len);
    printf("===\n");
    printf("%s\n", buffer);

    return 0;
}
```
