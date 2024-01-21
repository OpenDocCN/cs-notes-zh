# 网络，第五部分：关闭端口，重用端口和其他技巧

## 关闭和关闭之间有什么区别？

当您不再需要从套接字读取更多数据，写入更多数据或完成两者时，请使用`shutdown`调用。当您关闭套接字以进行进一步写入（或读取）时，该信息也会发送到连接的另一端。例如，如果您在服务器端关闭套接字以进行进一步写入，那么稍后，阻塞的`read`调用可能返回 0，表示不再需要更多字节。

当您的进程不再需要套接字文件描述符时，请使用`close`。

如果在创建套接字文件描述符后进行了`fork`，则所有进程都需要在套接字资源可以重新使用之前关闭套接字。如果您关闭套接字以进行进一步读取，那么所有进程都会受到影响，因为您已更改了套接字，而不仅仅是文件描述符。

良好编写的代码将在调用`close`之前`shutdown`套接字。

## 当我重新运行我的服务器代码时，它不起作用！为什么？

默认情况下，套接字关闭后，端口进入超时状态，在此期间不能重新使用（“绑定到新套接字”）。

通过在绑定到端口之前设置套接字选项 REUSEPORT 可以禁用此行为：

```cpp
    int optval = 1;
    setsockopt(sock_fd, SOL_SOCKET, SO_REUSEPORT, &optval, sizeof(optval));

    bind(sock_fd, ...);
```

## TCP 客户端可以绑定到特定端口吗？

是的！实际上，出站 TCP 连接会自动绑定到客户端上未使用的端口。通常情况下，不需要在客户端上显式设置端口，因为系统会智能地在合理的接口上找到一个未使用的端口（例如，如果当前通过 WiFi 连接，则是无线网卡）。但是，如果您需要明确选择特定的以太网卡，或者防火墙仅允许从特定范围的端口值进行出站连接，则可能会有用。

要显式绑定到以太网接口和端口，请在`connect`之前调用`bind`

## 谁连接到我的服务器？

`accept`系统调用可以选择性地通过传递 sockaddr 结构提供有关远程客户端的信息。不同的协议具有不同的`struct sockaddr`变体，它们的大小也不同。使用最简单的结构是`sockaddr_storage`，它足够大以表示所有可能类型的 sockaddr。请注意，C 没有任何继承模型。因此，我们需要将我们的结构明确转换为“基本类型”结构 sockaddr。

```cpp
    struct sockaddr_storage clientaddr;
    socklen_t clientaddrsize = sizeof(clientaddr);
    int client_id = accept(passive_socket,
            (struct sockaddr *) &clientaddr,
             &clientaddrsize);
```

我们已经看到`getaddrinfo`可以构建 addrinfo 条目的链表（每个条目都可以包含套接字配置数据）。如果我们想要将套接字数据转换为 IP 和端口地址怎么办？输入`getnameinfo`，它可以用于将本地或远程套接字信息转换为域名或数字 IP。类似地，端口号可以表示为服务名称（例如端口 80 的“http”）。在下面的示例中，我们请求客户端 IP 地址和客户端端口号的数字版本。

```cpp
    socklen_t clientaddrsize = sizeof(clientaddr);
    int client_id = accept(sock_id, (struct sockaddr *) &clientaddr, &clientaddrsize);
    char host[256], port[256];
    getnameinfo((struct sockaddr *) &clientaddr,
          clientaddrsize, host, sizeof(host), port, sizeof(port),
          NI_NUMERICHOST | NI_NUMERICSERV);
```

待办事项：讨论 NI_MAXHOST 和 NI_MAXSERV，以及 NI_NUMERICHOST

## getnameinfo 示例：我的 IP 地址是多少？

要获取当前计算机的 IP 地址的 IP 地址链表，请使用`getifaddrs`，它将返回 IPv4 和 IPv6 IP 地址的链接列表（可能还包括其他接口）。我们可以检查每个条目并使用`getnameinfo`打印主机的 IP 地址。ifaddrs 结构包括家族，但不包括结构的大小。因此，我们需要根据家族（IPv4 v IPv6）手动确定结构的大小。

```cpp
 (family == AF_INET) ? sizeof(struct sockaddr_in) : sizeof(struct sockaddr_in6)
```

完整的代码如下所示。

```cpp
    int required_family = AF_INET; // Change to AF_INET6 for IPv6
    struct ifaddrs *myaddrs, *ifa;
    getifaddrs(&myaddrs);
    char host[256], port[256];
    for (ifa = myaddrs; ifa != NULL; ifa = ifa->ifa_next) {
        int family = ifa->ifa_addr->sa_family;
        if (family == required_family && ifa->ifa_addr) {
            if (0 == getnameinfo(ifa->ifa_addr,
                                (family == AF_INET) ? sizeof(struct sockaddr_in) :
                                sizeof(struct sockaddr_in6),
                                host, sizeof(host), port, sizeof(port)
                                 , NI_NUMERICHOST | NI_NUMERICSERV  ))
                puts(host);
            }
        }
```

## 我的机器的 IP 地址是多少（shell 版本）

答案：使用`ifconfig`（或 Windows 的 ipconfig）。但是这个命令为每个接口生成大量输出，因此我们可以使用 grep 过滤输出。

```cpp
ifconfig | grep inet

Example output:
    inet6 fe80::1%lo0 prefixlen 64 scopeid 0x1 
    inet 127.0.0.1 netmask 0xff000000 
    inet6 ::1 prefixlen 128 
    inet6 fe80::7256:81ff:fe9a:9141%en1 prefixlen 64 scopeid 0x5 
    inet 192.168.1.100 netmask 0xffffff00 broadcast 192.168.1.255 
```
