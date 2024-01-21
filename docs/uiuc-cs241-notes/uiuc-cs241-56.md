# 网络，第二部分：使用 getaddrinfo

## 如何使用`getaddrinfo`将主机名转换为 IP 地址？

函数`getaddrinfo`可以将人类可读的域名（例如`www.illinois.edu`）转换为 IPv4 和 IPv6 地址。实际上，它将返回一个 addrinfo 结构的链表：

```cpp
struct addrinfo {
    int              ai_flags;
    int              ai_family;
    int              ai_socktype;
    int              ai_protocol;
    socklen_t        ai_addrlen;
    struct sockaddr *ai_addr;
    char            *ai_canonname;
    struct addrinfo *ai_next;
};
```

使用起来非常简单。例如，假设你想找出[www.bbc.com](http://www.bbc.com)的网页服务器的数值 IPv4 地址。我们分两个阶段来做。首先使用 getaddrinfo 构建可能连接的链表。其次使用`getnameinfo`将二进制地址转换为可读形式。

```cpp
#include <stdio.h>
#include <stdlib.h>
#include <sys/types.h>
#include <sys/socket.h>
#include <netdb.h>

struct addrinfo hints, *infoptr; // So no need to use memset global variables

int main() {
  hints.ai_family = AF_INET; // AF_INET means IPv4 only addresses

  int result = getaddrinfo("www.bbc.com", NULL, &hints, &infoptr);
  if (result) {
    fprintf(stderr, "getaddrinfo: %s\n", gai_strerror(result));
    exit(1);
  }

  struct addrinfo *p;
  char host[256],service[256];

  for(p = infoptr; p != NULL; p = p->ai_next) {

    getnameinfo(p->ai_addr, p->ai_addrlen, host, sizeof(host), service, sizeof(service), NI_NUMERICHOST);
    puts(host);
  }

  freeaddrinfo(infoptr);
  return 0;
}
```

典型输出：

```cpp
212.58.244.70
212.58.244.71 
```

## [www.cs.illinois.edu](http://www.cs.illinois.edu)如何转换为 IP 地址？

神奇！不是开玩笑，使用了一个名为“DNS”（域名服务）的系统。如果一台机器本地没有答案，那么它会向本地 DNS 服务器发送一个 UDP 数据包。这个服务器反过来可能会查询其他上游 DNS 服务器。

## DNS 安全吗？

DNS 本身很快，但不安全。DNS 请求未加密，容易受到“中间人”攻击的影响。例如，咖啡店的互联网连接可以轻松篡改您的 DNS 请求，并为特定域返回不同的 IP 地址

## 如何连接到 TCP 服务器（例如网页服务器）？

TODO 有三个基本的系统调用，你需要连接到远程机器：

```cpp
getaddrinfo -- Determine the remote addresses of a remote host
socket  -- Create a socket
connect  -- Connect to the remote host using the socket and address information 
```

如果`getaddrinfo`调用成功，它将创建一个`addrinfo`结构的链表，并将给定的指针设置为指向第一个。

套接字调用创建一个传出套接字并返回一个描述符（有时称为“文件描述符”），可以与`read`和`write`等一起使用。在这个意义上，它是网络模拟`open`打开文件流的功能-只是我们还没有将套接字连接到任何地方！

最后，连接调用尝试连接到远程机器。我们传递原始套接字描述符，以及存储在 addrinfo 结构中的套接字地址信息。有不同类型的套接字地址结构（例如 IPv4 与 IPv6），可能需要更多的内存。因此，除了传递指针外，还传递了结构的大小：

```cpp
// Pull out the socket address info from the addrinfo struct:
connect(sockfd, p->ai_addr, p->ai_addrlen)
```

## 如何释放为 addrinfo 结构的链表分配的内存？

在清理代码的一部分上调用`freeaddrinfo`，在最顶层的`addrinfo`结构上：

```cpp
void freeaddrinfo(struct addrinfo *ai);
```

## 如果 getaddrinfo 失败，我可以使用`strerror`打印出错误吗？

不。使用`getaddrinfo`进行错误处理有点不同：

+   返回值*就是*错误代码（即不要使用`errno`）

+   使用`gai_strerror`获取等效的简短英文错误文本：

```cpp
int result = getaddrinfo(...);
if(result) { 
   const char *mesg = gai_strerror(result); 
   ...
}
```

## 我可以只请求 IPv4 或 IPv6 连接吗？仅限 TCP？

是的！使用传递给`getaddrinfo`的 addrinfo 结构来定义你想要的连接类型。

例如，要指定基于 IPv6 的基于流的协议：

```cpp
struct addrinfo hints;
memset(hints, 0, sizeof(hints));

hints.ai_family = AF_INET6; // Only want IPv6 (use AF_INET for IPv4)
hints.ai_socktype = SOCK_STREAM; // Only want stream-based connection
```

## 关于使用`gethostbyname`的代码示例呢？

旧函数`gethostbyname`已被弃用；这是将主机名转换为 IP 地址的旧方法。端口地址仍然需要使用 htons 函数手动设置。使用更新的`getaddrinfo`更容易编写支持 IPv4 和 IPv6 的代码

## 是这么简单！？

是也不是。创建一个简单的 TCP 客户端很容易-但是网络通信提供了许多不同级别的抽象，以及可以在每个抽象级别设置的几个属性和选项（例如，我们还没有讨论可以操纵套接字选项的`setsockopt`）。有关更多信息，请参阅此[指南](http://www.beej.us/guide/bgnet/output/html/multipage/getaddrinfoman.html)。
