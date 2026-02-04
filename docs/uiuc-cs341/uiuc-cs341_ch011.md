# 网络

在过去 10-20 年中，网络已经成为计算机最重要的用途之一。如今，我们大多数人无法忍受没有 WiFi 或任何连接的地方，因此作为程序员，了解网络和如何在网络上进行编程通信至关重要。尽管这可能听起来很复杂，但 POSIX 已经定义了很好的标准，使得连接到外部世界变得容易。POSIX 还允许你深入了解底层，并优化每个连接的各个小部分，以编写高性能的程序。

作为下一章中你将了解更多内容的补充，我们将对尺寸的表示法进行严格规定。这意味着当我们提到千（Kilo-）、兆（Mega-）等国际单位制（SI）前缀时，我们始终指的是 10 的幂。一个千字节等于一千字节，一个兆字节等于一千千字节，依此类推。如果我们需要提到字节，我们将使用更准确的术语 Kibibyte。Mibibyte 和 Gibibyte 分别是 Megabyte 和 Gigabyte 的类似物。我们做出这种区分是为了确保我们不会差 24。这种误称的原因将在文件系统章节中解释。

## OSI 模型

开源互连 7 层模型（OSI 模型）是一系列定义了基础设施和协议标准的段，用于无线电通信的形式，在我们的案例中是互联网。7 层模型如下

1.  第 1 层：物理层。这些是实际携带波特率穿越导线的波形。顺便说一句，比特不会穿越导线，因为在大多数介质中，你可以改变一个波形的两个特性——振幅和频率——并在每个时钟周期中传输更多的比特。

1.  第 2 层：链路层。这是每个代理对某些事件（错误检测、嘈杂的信道等）的反应方式。这是以太网和 WiFi 所在的地方。

1.  第 3 层：网络层。这是互联网的核心。底下的两个协议处理直接连接的两个不同计算机之间的通信。这一层负责将数据包从一端路由到另一端。

1.  第 4 层：传输层。这一层指定了数据切片的接收方式。底下的三层不保证数据包接收的顺序，也不保证数据包丢失时会发生什么。通过使用不同的协议，这一层可以做到。

1.  第 5 层：会话层。这一层确保如果上一层的连接丢失，下一层可以建立新的连接，并且对最终用户来说，看起来就像什么都没发生一样。

1.  第 6 层：表示层。这一层处理加密、压缩和数据转换。例如，在不同操作系统之间的可移植性，如将换行符转换为 Windows 换行符。

1.  第 7 层：应用层。HTTP 和 FTP 都定义在这一层。这通常是我们在整个互联网上定义协议的地方。作为程序员，我们只有在认为可以创建比下面所有层次都更适合我们需求的算法时，才会向下层移动。

这本书不会深入探讨网络技术。我们将重点关注第 3 层、第 4 层和第 7 层的一些方面，因为这些对于你打算与互联网打交道的人来说是至关重要的，在职业生涯的某个阶段你肯定会这样做。至于另一个定义，协议是一套由互联网工程任务组提出的规范，它规定了协议实现者如何在特定情况下使他们的程序或电路行为。

## 第 3 层：互联网协议

以下是对互联网协议（IP）的简要介绍，这是将信息数据报从一台机器发送到另一台机器的主要方式。“IP4”，或者更确切地说，IPv4 是互联网协议的第 4 版本，它描述了如何在网络中从一个机器发送信息数据包到另一个机器。即使到了 2018 年，IPv4 仍然主导着互联网流量，但谷歌报告称，现在有 24 个国家通过 IPv6 提供了他们 15%的流量（“2018 年 IPv6 部署状态” 2018）。IPv4 的一个显著限制是源地址和目的地址限制在 32 位。IPv4 是在一个认为有 40 亿台设备连接到同一网络的想法是不可想象或至少不值得增加数据包大小的时代设计的。IPv4 地址通常以四个八位字节序列的形式书写，由点分隔，例如“255.255.255.0”。

每个 IPv4 数据报都包含一个小的头部——通常是 20 个八位字节，它包括源地址和目的地址。从概念上讲，源地址和目的地址可以分为两部分：网络号，高位的位和低位位代表该网络上的特定主机号。

一个较新的数据包协议 IPv6 解决了 IPv4 的许多限制，如使路由表更简单和 128 位地址。然而，根据 2018 年的比较，很少有网络流量是基于 IPv6 的（“2018 年 IPv6 部署状态” 2018）。我们以八个四进制分隔符的序列书写 IPv6 地址，例如“1F45:0000:0000:0000:0000:0000:0000:0000”。由于这可能会变得难以管理，我们可以省略零“1F45::”。一台机器可以有一个 IPv6 地址和一个 IPv4 地址。

存在一些特殊的 IP 地址。IPv4 中的一个例子是，IPv6 作为或也称为 localhost。发送到 127.0.0.1 的数据包永远不会离开该机器；该地址指定为同一台机器。还有很多其他地址，由某些八位字节为零或 255（最大值）表示。您不需要知道所有术语，请记住，一台机器在全球互联网上可以拥有的实际 IP 地址数量小于“原始”地址的数量。本书涵盖了 IP 如何处理路由、分片和重新组装上层协议。以下是一个更深入的说明。

### IPv6 是怎么回事？

![IPv6 数据包可分性](img/file41.png)

IPv6 数据包可分性

IPv6 的一个大特性是地址空间。世界在很久以前就耗尽了 IP 地址，并一直在使用黑客手段来解决这个问题。有了 IPv6，就有足够的内部和外部地址，即使我们发现外星文明，我们可能也不会耗尽。另一个好处是，这些地址是租用的而不是购买的，这意味着如果互联网物联网发生重大事件，需要更改块地址方案，这是可以做到的。

另一个重要特性是通过 IPsec 实现的安全性。IPv4 在设计时几乎没有考虑安全性。因此，现在在高层有类似于 TLS 的关键交换，允许您加密通信。

另一个特性是简化处理。为了使互联网更快，IPv4 和 IPv6 头部在硬件中进行了验证。这意味着所有头部选项都按顺序在电路中处理。问题是，随着 IPv4 规范的增长，包括大量头部，硬件不得不变得越来越先进以支持这些头部。IPv6 重新排序头部，以便在更少的硬件周期内丢弃和路由数据包。在互联网的情况下，每个周期在尝试路由全球流量时都很重要。

### 我的地址是什么？

要获取当前机器的 IP 地址链表，请使用，它将返回包括其他接口在内的 IPv4 和 IPv6 IP 地址链表。我们可以检查每个条目并使用来打印主机的 IP 地址。该结构包括家族，但不包括结构的 sizeof。因此，我们需要根据家族手动确定结构的大小。

```c
(family == AF_INET) ? sizeof(struct sockaddr_in) : sizeof(struct sockaddr_in6)
```

完整的代码如下所示。

```c
int required_family = AF_INET; // Change to AF_INET6 for IPv6
struct ifaddrs *myaddrs, *ifa;
getifaddrs(&myaddrs);
char host[256], port[256];

for (ifa = myaddrs; ifa != NULL; ifa = ifa->ifa_next) {
 int family = ifa->ifa_addr->sa_family;
 if (family == required_family && ifa->ifa_addr) {
 int ret = getnameinfo(ifa->ifa_addr,
 (family == AF_INET) ? sizeof(struct sockaddr_in) :
 sizeof(struct sockaddr_in6),
 host, sizeof(host), port, sizeof(port)
 , NI_NUMERICHOST | NI_NUMERICSERV)
 if (0 == ret) {
 puts(host);
 }
 }
}
```

要从命令行获取您的 IP 地址，请使用 Windows 的。

然而，此命令为每个接口生成大量输出，因此我们可以使用 grep 过滤输出。

```c
ifconfig | grep inet

Example output:
    inet6 fe80::1%lo0 prefixlen 64 scopeid 0x1
    inet 127.0.0.1 netmask 0xff000000
    inet6 ::1 prefixlen 128
    inet6 fe80::7256:81ff:fe9a:9141%en1 prefixlen 64 scopeid 0x5
    inet 192.168.1.100 netmask 0xffffff00 broadcast 192.168.1.255
```

要获取远程网站的 IP 地址，该函数可以将可读的域名（例如）转换为 IPv4 和 IPv6 地址。它将返回一个 addrinfo 结构体的链表：

```c
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

例如，假设你想找出位于的 Web 服务器的数值 IPv4 地址。我们分两个阶段来做这件事。首先，使用 getaddrinfo 构建可能的连接的链表。其次，使用将其中的一个二进制地址转换为可读形式。

```c
#include <stdio.h>
#include <stdlib.h>
#include <sys/types.h>
#include <sys/socket.h>
#include <netdb.h>

struct addrinfo hints, *infoptr; // So no need to use memset global variables

int main() {
 hints.ai_family = AF_INET; // AF_INET means IPv4 only addresses

 // Get the machine addresses
 int result = getaddrinfo("www.bbc.com", NULL, &hints, &infoptr);
 if (result) {
 fprintf(stderr, "getaddrinfo: %s\n", gai_strerror(result));
 exit(1);
 }

 struct addrinfo *p;
 char host[256];

 for(p = infoptr; p != NULL; p = p->ai_next) {
 // Get the name for all returned addresses
 getnameinfo(p->ai_addr, p->ai_addrlen, host, sizeof(host), NULL, 0, NI_NUMERICHOST);
 puts(host);
 }

 freeaddrinfo(infoptr);
 return 0;
}
```

可能的输出。

```c
212.58.244.70
212.58.244.71
```

可以使用.指定 IPv4 或 IPv6。只需在上面的代码中将 ai_family 属性替换为以下内容。

```c
hints.ai_family = AF_UNSPEC
```

如果你在想计算机是如何将主机名映射到地址的，我们将在第 7 层讨论这个问题。剧透一下：这是一个名为 DNS 的服务。在我们进入下一节之前，重要的是要注意一个网站可以有多个 IP 地址。这可能是为了提高机器的效率。如果谷歌或 Facebook 只有一个服务器将它们的所有入站请求路由到其他计算机，他们可能不得不在那个计算机或数据中心上花费巨额资金。相反，他们可以为不同的地区分配不同的 IP 地址，并让计算机选择。通过非首选 IP 地址访问网站并不糟糕。页面可能会加载得更慢。

## 第 4 层：TCP 和客户端

![额外：TCP 头部规范](img/file42.png)

额外：TCP 头部规范

今天的互联网上大多数服务都使用 TCP，因为它有效地隐藏了互联网底层、数据包级别的复杂性。TCP 或传输控制协议是一个基于连接的协议，它建立在 IPv4 和 IPv6 之上，因此可以描述为“TCP/IP”或“IP 上的 TCP”。TCP 在两台机器之间创建了一个*管道*，并抽象化了互联网的低级数据包特性。因此，在大多数情况下，通过 TCP 连接发送的字节被成功交付且未损坏。高性能和易出错的代码甚至不会假设这一点！

TCP 有许多特性使其与其他传输协议 UDP 区分开来。

1.  端口与 IP 地址一起，你只能向一台机器发送数据包。如果你想一台机器处理多个数据流，你必须手动使用 IP 地址来做。TCP 给程序员提供了一套虚拟套接字。客户端指定要发送数据包的套接字，TCP 协议确保等待在该端口上接收数据包的应用程序收到数据。一个进程可以在特定端口上监听传入的数据包。然而，只有具有超级用户（root）访问权限的进程才能监听小于 1024 的端口。任何进程都可以监听 1024 或更高的端口。一个常用的端口是 80 号。它用于未加密的 HTTP 请求或网页。例如，如果网页浏览器连接到，它将连接到 80 端口。

1.  重传数据包可能会因为网络错误或拥塞而丢失。因此，它们需要被重新传输。同时，重传不应该导致更多数据包丢失。这需要在网络拥塞和速度之间进行权衡。

1.  乱序数据包。由于 IP 中的各种原因，数据包可能会被更优地路由。如果一个数据包在另一个数据包之前到达，协议应该检测并重新排序它们。

1.  重复数据包。数据包可能会到达两次。因此，协议需要能够区分在溢出条件下具有序列号的两个数据包。

1.  错误纠正。TCP 有一个校验和来处理位错误。但这很少被使用。

1.  流量控制。流量控制是在接收方执行的。这可能是为了防止一个慢速接收方被数据包淹没。处理 10000 或 1000 万个并发连接的服务器可能需要告诉接收方减速，但保持连接，因为负载。还有确保本地网络流量稳定的问题。

1.  阻塞控制。阻塞控制是在发送方执行的。阻塞控制是为了防止发送方将太多数据包发送到网络中。这很重要，以确保每个 TCP 连接都得到公平对待。这意味着离开计算机连接到谷歌和 YouTube 的两个连接将获得相同的带宽和 ping。可以很容易地定义一个协议，它将占用所有带宽，而将其他协议抛在后面，但这往往是有害的，因为很多时候将计算机限制为单个 TCP 连接会产生相同的结果。

1.  面向连接/生命周期导向。你可以想象 TCP 连接是一系列通过管道发送的字节。尽管 TCP 连接有一个“生命周期”。TCP 通过 SYN SYN-ACK ACK 来处理建立连接。这意味着客户端将发送一个同步包，告诉 TCP 从哪个起始序列号开始。然后接收方将发送一个确认同步号的 SYN-ACK 消息。然后客户端将通过最后一个数据包确认这一点。现在连接两端都可以进行读写。TCP 将发送数据，接收数据的一方将确认已收到数据包。如果一段时间内没有发送数据包，TCP 将通过交换零长度数据包来确保连接仍然活跃。在任何时候，客户端和服务器都可以发送一个 FIN 包，这意味着服务器将不会传输。这个包可以通过位来修改，只关闭特定连接的读或写端。当所有端点都关闭时，连接结束。

TCP 虽然不提供很多功能。

1.  安全性。连接到一个声称是特定网站的 IP 地址并不验证该声明（如 TLS）。你可能会向恶意计算机发送数据包。

1.  加密。任何人都可以监听明文 TCP。传输中的数据包是明文。像密码这样重要的事情很容易被旁观者窃取。

1.  会话重连。如果 TCP 连接中断，则必须创建一个新的整个连接，并且传输必须从头开始。这是由一个更高层次的协议处理的。

1.  请求的分隔。TCP 是自然面向连接的。在 TCP 上通信的应用程序需要找到一种独特的方式来告诉对方这个请求或响应已经结束。HTTP 通过两个回车符分隔标题，并使用长度字段或一直监听直到连接关闭。

### 关于网络顺序的说明

整数可以以最低有效字节优先或最高有效字节优先的方式表示。只要机器本身在内部是一致的，这两种方法都是合理的。对于网络通信，我们需要在约定的格式上达成一致。

返回网络字节顺序的 16 位无符号整数‘short’值 xyz。返回网络字节顺序的 32 位无符号整数‘long’值 xyz。任何更长的整数都需要计算机指定顺序。

这些函数被读取为“主机到网络”。逆函数（, ）将网络顺序的字节值转换为主机顺序。那么，主机顺序是小端序还是大端序？答案是——这取决于你的机器！它取决于运行代码的主机的实际架构。如果架构碰巧与网络顺序相同，则函数返回相同的整数。对于 x86 机器，主机和网络顺序是不同的。

除非另有约定，每次读取或写入低级 C 网络结构，即端口号和地址信息时，请记住使用上述函数以确保正确转换为/从机器格式。否则，显示或指定的值可能是不正确的。

这一点不适用于在事先协商字节序的协议。如果两台计算机在转换网络顺序的消息时受到 CPU 的限制——这在高性能系统中的 RPC 中很常见——那么如果它们具有相似的端序，协商以发送小端序可能是有价值的。

为什么网络顺序被定义为大端序？简单的答案是 RFC1700 这样规定（Reynolds 和 Postel 1994)。如果你想了解更多信息，我们将引用那篇著名的文章，该文章为特定版本进行了辩护（Cohen 1980)。最重要的是，它是标准的。当我们没有标准时会发生什么？我们有 4 种不同的 USB 插头类型（常规、Micro、Mini 和 USB-C），它们之间相互作用不佳。在此处包含相关的 XKCD [标准](https://xkcd.com/927/)。

### TCP 客户端

有三个基本的系统调用用于连接到远程机器。

1.  如果调用成功，它将创建一个结构体的链表，并将给定的指针设置为指向第一个。

    此外，您还可以使用 hints 结构来仅获取某些条目，如特定的 IP 协议等。addrinfo 结构被传递进去以定义您想要的连接类型。例如，要指定基于流的 IPv6 协议，可以使用以下代码片段。

    ```c
    struct addrinfo hints;
    memset(&hints, 0, sizeof(hints));

    hints.ai_family = AF_INET6; // Only want IPv6 (use AF_INET for IPv4)
    hints.ai_socktype = SOCK_STREAM; // Only want stream-based connection
    ```

    “家族”的其他模式是和，分别表示 IPv4 和未指定。如果你正在寻找一个你不确定 IP 版本的服务，这可能很有用。自然地，如果你指定了 UNSPEC，你会在字段中获取版本。

    使用的错误处理略有不同。返回值*就是*错误代码。为了将其转换为可读的错误，请使用以获取等效的简短英文错误文本。

    ```c
    int result = getaddrinfo(...);
    if(result) {
     const char *mesg = gai_strerror(result);
     ...
    }
    ```

1.  套接字调用创建一个网络套接字并返回一个可以用于和的描述符。在这种情况下，它是打开文件流的网络类似物——只不过我们还没有将套接字连接到任何东西！

    套接字的创建使用一个域，对于或，是是否使用 UDP、TCP 或其他某些其他套接字类型，是针对我们的示例的协议配置的可选选择。在这个例子中，我们可以将其保留为 0 作为默认值。这个调用在内核中创建一个套接字对象，可以通过它与外部世界/网络进行通信。你可以使用的结果来填写参数，或者手动提供它们。

    套接字调用返回一个整数——一个文件描述符——对于 TCP 客户端，你可以将其用作常规文件描述符。你可以使用和来接收或发送数据包。

    TCP 套接字类似于，常用于需要 IPC 的情况。我们之前没有提到它，因为使用适合网络的设备在单个线程上的进程之间进行通信是过度杀鸡。

1.  最后，connect 调用尝试连接到远程机器。我们传递原始套接字描述符以及存储在 addrinfo 结构体内的套接字地址信息。存在不同类型的套接字地址结构，可能需要更多的内存。因此，除了传递指针外，还需要传递结构的大小。为了帮助识别错误和错误，检查所有网络调用的返回值是一个好习惯，包括

    ```c
    // Pull out the socket address info from the addrinfo struct:
    connect(sockfd, p->ai_addr, p->ai_addrlen)
    ```

1.  （可选）为了清理代码，在第一级结构上调用。

已有一个旧函数已被弃用。这是将主机名转换为 IP 地址的旧方法。端口号仍然需要使用函数手动设置。使用较新的方法来支持 IPv4 和 IPv6 要简单得多。

这就是创建一个*简单*的 TCP 客户端所需的所有内容。然而，网络通信提供了许多不同级别的抽象以及可以在每个级别设置的多个属性和选项。例如，我们还没有讨论过如何操作套接字选项。你还可以与较低的协议进行交互，因为内核提供了有助于这一点的原语。请注意，你需要以 root 权限创建原始套接字。此外，你需要有大量的“设置”或启动代码，准备好你的数据报可能因为格式错误而被丢弃。有关更多信息，请参阅此[指南](http://www.beej.us/guide/bgnet/output/html/multipage/getaddrinfoman.html)。

### 发送一些数据

一旦我们建立了成功的连接，我们就可以像任何旧的文件描述符一样读取或写入。记住，如果您连接到网站，您希望遵守 HTTP 协议规范以获得任何有意义的结果。有库可以做到这一点。通常，您不会在套接字级别连接。读取或写入的字节数可能小于预期。因此，检查和的返回值非常重要。下面是一个简单的 HTTP 客户端，它向符合 URL 的 URL 发送请求。首先，我们将从无聊的部分和解析代码开始。

```c
typedef struct _host_info {
 char *hostname;
 char *port;
 char *resource;
} host_info;

host_info *get_info(char *uri) {
 // ... Parses the URI/URL
}

void free_info(host_info *info) {
 // ... Frees any info
}

int main(int argc, char *argv[]) {
 if(argc != 2) {
 fprintf(stderr, "Usage: %s http://hostname[:port]/path\n", *argv);
 return 1;
 }
 char *uri = argv[1];
 host_info *info = get_info(uri);
 host_info *temp = send_request(info);

 return 0;
}
```

发送请求的代码如下。我们首先必须做的事情是连接到一个地址。

```c
struct addrinfo current, *result;
memset(&current, 0, sizeof(struct addrinfo));
current.ai_family = AF_INET;
current.ai_socktype = SOCK_STREAM;

getaddrinfo(info->hostname, info->port, &current, &result);

connect(sock_fd, result->ai_addr, result->ai_addrlen)

freeaddrinfo(result);
```

下一段代码发送请求。以下是每个头部的含义。

1.  "GET %s HTTP/1.0" 这是指请求动词与路径的插值。这意味着使用 HTTP/1.0 方法在路径上执行 GET 动词。

1.  "Connection: close" 表示一旦请求完成，请关闭连接。此行不会用于任何其他连接。考虑到 HTTP 1.0 不允许您发送多个请求，这有点多余，但鉴于存在不兼容的技术，最好是明确指出。

1.  "Accept: */*" 这意味着客户端愿意接受任何内容。

更健壮的代码还会检查写入是否失败或调用是否被中断。

```c
char *buffer;
asprintf(&buffer,
 "GET %s HTTP/1.0\r\n"
 "Connection: close\r\n"
 "Accept: */*\r\n\r\n",
 info->resource);

write(sock_fd, buffer, strlen(buffer));
free(buffer);
```

最后一段代码是发送请求的驱动代码。如果您想方便地使用以下代码将文件描述符作为文件对象打开，请随意使用。但请注意，不要忘记将缓冲区设置为零，否则您可能会双重缓冲输入，这会导致性能问题。

```c
void send_request(host_info *info) {
 int sock_fd = socket(AF_INET, SOCK_STREAM, 0);
 // Re-use address is a little overkill here because we are making a
 // Listen only server and we don't expect spoofed requests.
 int optval = 1;
 int retval = setsockopt(sock_fd, SOL_SOCKET, SO_REUSEADDR, &optval,
 sizeof(optval));
 if(retval == -1) {
 perror("setsockopt");
 exit(1);
 }
 // Connect using code snippet

 // Send the get request

 // Open so you can use getline
 FILE *sock_file = fdopen(sock_fd, "r+");
 setvbuf(sock_file, NULL, _IONBF, 0);

 ret = handle_okay(sock_file);
 fclose(sock_file);
 close(sock_fd);
}
```

上面的示例演示了使用超文本传输协议向服务器发送请求。一般来说，有六个部分

1.  方法。GET、POST 等。

1.  资源。“/” “/index.html” “/image.png”

1.  协议“HTTP/1.0”

1.  一个新行（）。请求总是有回车符。

1.  任何其他旋钮或开关参数

1.  请求的实际主体由两个新行分隔。请求的主体要么是如果指定了大小，要么是直到接收方关闭他们的连接。

服务器第一次响应行描述了使用的 HTTP 版本以及请求是否成功，使用三位响应代码。

```c
HTTP/1.1 200 OK
```

如果客户端请求了一个不存在的路径，例如，那么第一行包含的响应代码是众所周知的响应代码。

```c
HTTP/1.1 404 Not Found
```

更多信息，RFC 7231 提供了今天最常见 HTTP 方法的最新规范（Fielding 和 Reschke 2014)。

## 第 4 层：TCP 服务器

创建最小 TCP 服务器所需的四个系统调用是、、、和。每个都有特定的目的，并且应该按照上述顺序大致调用

1.  要创建网络通信的端点。一个新的套接字本身存储字节。尽管我们指定了基于数据包或流连接，但它未绑定到特定的网络接口或端口。相反，套接字返回一个网络描述符，可以用于后续的 bind、listen 和 accept 调用。

    作为一个问题，这些套接字必须声明为被动。被动服务器套接字等待另一个主机连接。相反，它们等待传入连接。此外，当对等方断开连接时，服务器套接字保持打开。相反，客户端通过服务器上的一个特定于该连接的单独活动套接字进行通信。

    由于 TCP 连接由发送者的地址和端口以及接收者的地址和端口定义，因此特定的服务器端口可以有一个被动服务器套接字，但可以有多个活动套接字。每个当前打开的连接都有一个。服务器的操作系统维护一个查找表，将唯一的元组与活动套接字关联起来，以便将传入的数据包正确路由到正确的套接字。

1.  该调用将一个抽象套接字与一个实际的网络接口和端口关联起来。可以在 TCP 客户端上调用 bind。bind 使用的端口号可以手动设置（许多较老的仅支持 IPv4 的 C 代码示例就是这样做的），或者使用 来创建。

    默认情况下，当服务器套接字关闭后，端口会在一段时间后释放。相反，端口进入“TIMED-WAIT”状态。这可能导致在开发过程中出现重大混淆，因为超时可能会使有效的网络代码看起来像失败了。

    要能够立即重用端口，请在绑定端口之前指定。

    ```c
    int optval = 1;
    setsockopt(sfd, SOL_SOCKET, SO_REUSEPORT, &optval, sizeof(optval));

    bind(...);
    ```

    这里有一个关于[socket 选项 so-reuseaddr 和 so-reuseport 的扩展 stackoverflow 入门讨论](http://stackoverflow.com/questions/14388706/socket-options-so-reuseaddr-and-so-reuseport-how-do-they-differ-do-they-mean-t)。

1.  该调用指定了未处理传入连接的队列大小。这是由 没有分配给文件描述符的连接。对于高性能服务器，典型值是 128 或更多。

1.  一旦服务器套接字初始化完成，服务器就会调用等待新的连接。与 和 不同，这个调用将会阻塞，除非设置了非阻塞选项。如果没有新的连接，这个调用将会阻塞，并且只有在新的客户端连接时才会返回。返回的 TCP 套接字与一个特定的元组相关联，并将用于所有未来匹配此元组的传入和传出 TCP 数据包。

    注意，该调用返回一个新的文件描述符。这个文件描述符特定于某个客户端。使用原始服务器套接字描述符进行服务器 I/O 是一种常见的编程错误，然后你会 wonder 为什么网络代码失败了。

    系统调用可以通过传递 sockaddr 结构体来提供有关远程客户端的信息。不同的协议有不同的，它们的大小不同。最简单的结构体是，它足够大，可以表示所有可能的类型。请注意，C 语言没有继承模型。因此，我们需要显式地将我们的结构体转换为基类型结构体 sockaddr。

    ```c
    struct sockaddr_storage clientaddr;
    socklen_t clientaddrsize = sizeof(clientaddr);
    int client_id = accept(passive_socket,
     (struct sockaddr *) &clientaddr,
     &clientaddrsize);
    ```

    我们已经看到可以构建一个 addrinfo 条目链表，并且这些条目中的每一个都可以包含套接字配置数据。如果我们想将套接字数据转换为 IP 和端口号呢？可以使用该工具将本地或远程套接字信息转换为域名或数字 IP。同样，端口号也可以表示为服务名。例如，端口号 80 通常用作接收 HTTP 请求的入站连接端口。在下面的示例中，我们请求客户端 IP 地址和客户端端口号的数字版本。

    ```c
     socklen_t clientaddrsize = sizeof(clientaddr);
     int client_id = accept(sock_id, (struct sockaddr *) &clientaddr, &clientaddrsize);
     char host[NI_MAXHOST], port[NI_MAXSERV];
     getnameinfo((struct sockaddr *) &clientaddr,
     clientaddrsize, host, sizeof(host), port, sizeof(port),
     NI_NUMERICHOST | NI_NUMERICSERV);
    ```

    可以使用宏来表示主机名的最大长度，以及端口号的最大长度。将主机名作为数字 IP 地址获取，同样对于端口号，虽然通常以数字开头，但也可以使用字符串表示。有关更多信息，请参阅[Open BSD man pages](https://man.openbsd.org/getnameinfo.3#NI_NUMERICHOST)

1.  and

    当你不再需要从套接字读取更多数据、写入更多数据或完成这两项操作时，使用该调用。当你对套接字的读取和/或写入端调用时，该信息也会发送到连接的另一端。如果你在服务器端关闭套接字以进行进一步写入，那么稍后，一个阻塞调用可能会返回 0，表示不再期望更多字节。同样，向已关闭读取的 TCP 连接写入将生成 SIGPIPE 信号

    当你的进程不再需要套接字文件描述符时使用。

    如果在创建套接字文件描述符后执行了操作，则所有进程都需要在套接字资源可以重用之前关闭套接字。如果你关闭套接字以进行进一步读取，所有进程都会受到影响，因为你已经改变了套接字，而不是文件描述符。良好的代码会在调用之前关闭套接字。

创建服务器有几个需要注意的问题。

+   使用被动服务器套接字的套接字描述符（如上所述）

+   在 getaddrinfo 中未指定 SOCK_STREAM 要求

+   无法重用现有端口。

+   未初始化未使用的结构体条目

+   如果端口当前正在使用中，该调用将失败。端口是针对机器的，而不是针对进程或用户。换句话说，你不能在另一个进程使用该端口时使用端口 1234。更糟糕的是，端口默认情况下在进程完成后会被“绑定”。

### 示例服务器

下面是一个工作简单服务器示例。注意：此示例是不完整的。例如，套接字文件描述符保持打开状态，由创建的内存保持分配。首先，我们获取当前机器的地址信息。

```c
struct addrinfo hints, *result;
memset(&hints, 0, sizeof(struct addrinfo));
hints.ai_family = AF_INET;
hints.ai_socktype = SOCK_STREAM;
hints.ai_flags = AI_PASSIVE;

int s = getaddrinfo(NULL, "1234", &hints, &result);
if (s != 0) {
 fprintf(stderr, "getaddrinfo: %s\n", gai_strerror(s));
 exit(1);
}
```

然后我们设置套接字，绑定它，并监听。

```c
int sock_fd = socket(AF_INET, SOCK_STREAM, 0);

// Bind and listen
if (bind(sock_fd, result->ai_addr, result->ai_addrlen) != 0) {
 perror("bind()");
 exit(1);
}

if (listen(sock_fd, 10) != 0) {
 perror("listen()");
 exit(1);
}
```

我们终于准备好监听连接了，所以我们将告诉用户并接受我们的第一个客户端。

```c
struct sockaddr_in *result_addr = (struct sockaddr_in *) result->ai_addr;
printf("Listening on file descriptor %d, port %d\n", sock_fd, ntohs(result_addr->sin_port));

// Waiting for connections like a passive socket
printf("Waiting for connection...\n");
int client_fd = accept(sock_fd, NULL, NULL);
printf("Connection made: client_fd=%d\n", client_fd);
```

之后，我们可以将新的文件描述符视为类似于管道的字节流。

```c
char buffer[1000];
// Could get interrupted
int len = read(client_fd, buffer, sizeof(buffer) - 1);
buffer[len] = '\0';

printf("Read %d chars\n", len);
printf("===\n");
printf("%s\n", buffer);
```

[language=C]

### 抱歉打断

我们需要明确的一个概念是，你需要在你的网络代码中处理中断。这意味着你读取或写入的套接字或已接受的文件描述符可能会在调用过程中被中断——大多数情况下你可能会遇到一个或两个中断。实际上，你系统中的任何调用都可能被中断。我们现在提出这个问题的原因是你通常在等待网络。这比进程慢一个数量级。这意味着中断的可能性更高。

你会如何处理中断？让我们尝试一个快速示例。

```c
while bytes_read isn't count {
 bytes_read += read(fd, buf, count);
 if error is EINTR {
 continue;
 } else {
 break;
 }
}
```

我们可以向你保证，以下代码*会出错*。你能看出为什么吗？表面上，它会在读取或写入后重新启动调用。但当错误是 EINTR 时，会发生什么？缓冲区的内容是否正确？你能发现其他问题吗？

## 第 4 层：UDP

UDP 是一种无连接协议，它建立在 IPv4 和 IPv6 之上。它使用简单。决定目标地址和端口，然后发送你的数据包！然而，网络不保证数据包是否会到达。如果网络拥塞，数据包可能会丢失。数据包可能会重复或顺序错乱。

UDP 的一个典型用例是当接收最新数据比接收所有数据更重要时。例如，一个游戏可能会发送玩家位置的连续更新。流媒体视频信号可能会使用 UDP 发送图片更新。

### UDP 属性

+   通过 UDP 发送的不可靠数据报协议数据包在前往目的地的过程中可能会丢失。这尤其令人困惑，因为如果你只在回环设备上测试——对于大多数用户来说，这是 localhost 或 127.0.0.1——那么数据包很少会丢失，因为没有发送网络数据包。

+   简单 UDP 协议应该比 TCP 有更少的冗余。这意味着对于 TCP，有很多可配置的参数和很多实现中的边缘情况。UDP 是即发即忘。

+   无状态/事务 UDP 协议是无状态的。这使得协议更简单，并允许协议表示简单的交易，如请求或响应查询。发送 UDP 消息的开销也更小，因为没有三次握手。

+   手动流量/拥塞控制你必须手动管理流量和拥塞控制，这是一把双刃剑。一方面，你完全控制着一切。另一方面，TCP 有*数十年的优化*，这意味着你的协议对于其用例需要更高效，以便更利于使用。

+   多播 这是你只能使用 UDP 做的事情之一。这意味着你可以向连接到特定路由器的每个对等体发送消息，该路由器是特定组的一部分。

完整的详细描述可在原始 RFC（“用户数据报协议” 1980）中找到。

虽然你可能不想在不想丢失数据的情况下使用 UDP，但许多协议基于 UDP 进行通信，这需要完整的数据。看看简单的文件传输协议（Trivial File Transfer Protocol），它使用 UDP 仅通过有线可靠地传输文件。当然，涉及更多的配置，但选择 UDP 而不是 TCP 涉及的因素远不止上述这些。

### UDP 客户端

UDP 客户端非常灵活，下面是一个简单的客户端，它通过命令行指定的服务器发送一个数据包。请注意，这个客户端发送数据包后不会等待确认。它发射后即忘。下面的例子也使用了它，因为一些遗留功能在设置客户端时仍然表现得相当不错。

```c
struct sockaddr_in addr;
memset(&addr, 0, sizeof(addr));
addr.sin_family = AF_INET;
addr.sin_port = htons((uint16_t)port);
struct hostent *serv = gethostbyname(hostname);
```

之前的代码通过主机名获取一个匹配项。尽管这不是可移植的，但它完成了工作。首先是要连接到它并使其可重用——就像 TCP 套接字一样。请注意，我们传递的是而不是 。

```c
int sockfd = socket(AF_INET, SOCK_DGRAM, 0);
int optval = 1;
setsockopt(sockfd, SOL_SOCKET, SO_REUSEPORT, &optval, sizeof(optval));
```

然后，我们可以将我们的结构体复制到另一个结构体中。完整的定义可以在手册页中找到，所以安全地复制它们是可行的。

```c
memcpy(&addr.sin_addr.s_addr, serv->h_addr, serv->h_length);
```

然后 UDP 的一个最终有用的部分是，我们可以超时接收数据包，而不是 TCP，因为 UDP 是无连接的。执行此操作的代码片段如下。

```c
struct timeval tv;
tv.tv_sec = 0;
tv.tv_usec = SOCKET_TIMEOUT;
setsockopt(sockfd, SOL_SOCKET, SO_RCVTIMEO, &tv, sizeof(tv));
```

现在，套接字已连接并准备好使用。我们可以用它来发送数据包。我们还应该检查返回值。请注意，如果数据包没有送达，我们不会收到错误，因为这属于 UDP 协议的一部分。然而，对于无效的结构体、错误的地址等，我们会收到错误代码。

```c
char *to_send = "Hello!"
int send_ret = sendto(sock_fd, // Socket
 to_send, // Data
 strlen(to_send), // Length of data
 0, // Flags
 (struct sockaddr *)&ipaddr, // Address
 sizeof(ipaddr)); // How long the address is
```

上述代码通过 UDP 简单地发送“Hello”。没有关于数据包是否到达、是否被处理等的想法。

### UDP 服务器

有许多函数调用可用于发送 UDP 套接字。我们将使用较新的来帮助设置套接字结构。记住，UDP 是一个简单的基于数据包（‘数据报’）的协议。两个主机之间不需要建立连接。首先，初始化 hints addrinfo 结构以请求一个 IPv6，被动数据报套接字。

```c
memset(&hints, 0, sizeof(hints));
hints.ai_family = AF_INET6;
hints.ai_socktype =  SOCK_DGRAM;
hints.ai_flags =  AI_PASSIVE;
```

接下来，使用 getaddrinfo 指定端口号。我们不需要指定主机，因为我们正在创建一个服务器套接字，而不是向远程主机发送数据包。小心不要发送“localhost”或其他回环地址的同义词。我们可能会尝试被动监听自己，从而导致绑定错误。

```c
getaddrinfo(NULL, "300", &hints, &res);

sockfd = socket(res->ai_family, res->ai_socktype, res->ai_protocol);
bind(sockfd, res->ai_addr, res->ai_addrlen);
```

端口号小于 1024，因此程序需要特权。我们也可以指定一个服务名称而不是数字端口号。

到目前为止，调用与 TCP 服务器类似。对于基于流的 服务，我们会调用并接受。对于我们的 UDP 服务器，程序可以开始等待数据包的到来。

```c
struct sockaddr_storage addr;
int addrlen = sizeof(addr);

// ssize_t recvfrom(int socket, void* buffer, size_t buflen, int flags, struct sockaddr *addr, socklen_t * address_len);

byte_count = recvfrom(sockfd, buf, sizeof(buf), 0, &addr, &addrlen);
```

addr 结构将保存关于到达数据包的发送者（源）信息。注意类型足够大，可以容纳所有可能的套接字地址类型 - IPv4、IPv6 或任何其他互联网协议。完整的 UDP 服务器代码如下。

```c
#include <string.h>
#include <stdio.h>
#include <stdlib.h>
#include <sys/types.h>
#include <sys/socket.h>
#include <netdb.h>
#include <unistd.h>
#include <arpa/inet.h>

int main(int argc, char **argv) {
 struct addrinfo hints, *res;
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
 char buf[1024];
 ssize_t byte_count = recvfrom(sockfd, buf, sizeof(buf), 0, &addr, &addrlen);
 buf[byte_count] = '\0';

 printf("Read %d chars\n", byte_count);
 printf("===\n");
 printf("%s\n", buf);
 }

 return 0;
}
```

注意，如果您从数据包中执行部分读取，则其余数据将被丢弃。一次 recvfrom 调用对应一个数据包。为了确保有足够的空间，请使用 64 KiB 作为存储空间。

## 第 7 层：HTTP

OSI 模型的第 7 层处理应用层接口。这意味着您可以忽略此层以下的所有内容，将互联网视为一种与另一台计算机通信的方式，这种通信可以是安全的，并且会话可能会重新连接。常见的第 7 层协议如下

1.  HTTP(S) - 超文本传输协议。在 Web 服务器上发送任意数据并执行远程操作。S 标准表示安全，其中 TCP 连接使用 TLS 协议以确保通信不会被旁观者轻易读取。

1.  FTP - 文件传输协议。将文件从一个计算机传输到另一个计算机

1.  TFTP - 简单文件传输协议。与上面相同，但使用 UDP。

1.  DNS - 域名服务。将主机名转换为 IP 地址

1.  SMTP - 简单邮件传输协议。允许向邮件服务器发送纯文本电子邮件

1.  SSH - 安全壳。允许一台计算机远程连接到另一台计算机并执行命令。

1.  Bitcoin - 去中心化加密货币

1.  BitTorrent - 对等文件共享协议

1.  NTP - 网络时间协议。此协议帮助将您的计算机时钟与外界同步

### 我的名字是什么？

记得我们之前讨论过将网站转换为 IP 地址吗？使用了一个名为“DNS”（域名服务）的系统。如果 IP 地址未存在于机器的缓存中，则发送一个 UDP 数据包到本地 DNS 服务器。此服务器可能会查询其他上游 DNS 服务器。

DNS 本身速度快但不够安全。DNS 请求未加密，容易受到“中间人”攻击。例如，咖啡店的互联网连接可以轻易篡改您的 DNS 请求，并返回特定域名的不同 IP 地址。这种篡改通常发生在获取 IP 地址后，通常会通过 HTTPS 建立连接。HTTPS 使用称为 TLS（以前称为 SSL）的协议来确保传输安全并验证主机名是否由证书颁发机构认可。证书颁发机构经常被黑客攻击，因此请小心不要将绿色锁等同于安全。即使有这层额外的安全措施，美国政府最近要求每个人升级他们的 DNS 到 DNSSec，它包括额外的安全技术，以高概率验证 IP 地址确实与主机名相关。

顺便提一下，DNS 的工作原理如下

1.  向您的 DNS 服务器发送一个 UDP 数据包

1.  如果该 DNS 服务器已缓存该数据包，则返回结果

1.  如果没有，向更高层的 DNS 服务器请求答案。缓存并发送结果

1.  如果任一数据包在猜测的超时时间内没有响应，则重发请求。

如果你想查看完整的细节，请随意查看维基百科页面。本质上，存在一个 DNS 服务器的层次结构。首先，有点层次结构。这个层次结构首先解析顶级域名等。接下来，它解析下一级，即。然后本地解析器可以解析任意数量的 URL。例如，伊利诺伊 DNS 服务器处理和。你可以拥有的子域名数量有限，但这通常用于将请求路由到不同的服务器，以避免需要购买许多高性能服务器来路由请求。

## 非阻塞 IO

当你调用时，如果数据不可用，它将等待数据准备好后再返回函数。当你从磁盘读取数据时，这种延迟很短，但当你从慢速网络连接读取时，请求需要很长时间。而且数据可能永远不会到达，导致意外的关闭。

POSIX 允许你设置文件描述符上的一个标志，这样任何对该文件描述符的调用都会立即返回，无论它是否已经完成。在这种模式下，你的调用将启动读取操作，在它工作的时候，你可以做其他有用的工作。这被称为“非阻塞”模式，因为调用不会阻塞。

要设置文件描述符为非阻塞。

```c
// fd is my file descriptor
int flags = fcntl(fd, F_GETFL, 0);
fcntl(fd, F_SETFL, flags | O_NONBLOCK);
```

对于套接字，你可以通过将添加到第二个参数来以非阻塞模式创建它：

```c
fd = socket(AF_INET, SOCK_STREAM | SOCK_NONBLOCK, 0);
```

当一个文件处于非阻塞模式并且你调用时，它将立即返回可用的任何字节。比如说，从你的套接字另一端的服务器传来了 100 个字节，你调用。‘read’将立即返回一个值为 100 的值，这意味着它读取了你请求的 150 个字节中的 100 个。如果你尝试通过调用读取剩余的数据，但最后 50 个字节还没有到达。将返回-1，并将全局错误变量**errno**设置为或。这是系统告诉你数据尚未准备好的方式。

也在非阻塞模式下工作。比如说，你想通过套接字向远程服务器发送 40,000 个字节。系统一次只能发送这么多字节。在非阻塞模式下，将立即返回它能够立即发送的字节数，大约是 23,000。如果你立即再次调用，它将返回-1，并将 errno 设置为或。这是系统告诉你它仍在发送最后一块数据，并且尚未准备好发送更多数据的方式。

有几种方法可以检查你的 IO 是否到达。让我们看看如何使用*select*和*epoll*来实现。我们拥有的第一个接口是 select。如果 POSIX 社区有替代方案，很多人不会选择它，而且在大多数情况下，都有一个替代方案。

```c
int select(int nfds,
fd_set *readfds,
fd_set *writefds,
fd_set *exceptfds,
struct timeval *timeout);
```

给定三组文件描述符，将等待这些文件描述符中的任何一个变为“就绪”。

1.  - 当有可读数据或到达 EOF 时，文件描述符处于就绪状态。

1.  - 当调用 write()将成功时，文件描述符处于就绪状态。

1.  - 系统特定的，定义不明确。只需传递 NULL 即可。

返回就绪文件描述符的总数。如果在由*timeout*定义的时间内没有任何文件描述符变为就绪，它将返回 0。在返回后，调用者需要遍历 readfds 和/或 writefds 中的文件描述符，以查看哪些已就绪。由于 readfds 和 writefds 既作为输入参数也作为输出参数，当指示有就绪文件描述符时，它将覆盖它们以反映只有就绪文件描述符。除非调用者打算只调用一次，否则在调用之前保存 readfds 和 writefds 的副本是一个好主意。以下是一个综合示例。

```c
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

[有关 select()的更多信息](http://pubs.opengroup.org/onlinepubs/9699919799/functions/select.html) select 的问题以及为什么许多用户不使用它或 poll 的原因是，select 必须线性地遍历每个对象。如果在遍历对象的过程中，任何对象的状态发生变化，select 必须重新启动。如果我们每个集合中都有大量的文件描述符，这将非常低效。有一个替代方案，但并不比这个好多少。

### epoll

不是 POSIX 的一部分，但 Linux 支持它。这是一种更高效地等待多个文件描述符的方法。它将确切地告诉你哪些描述符已准备好。它甚至为你提供了一种方法，可以在每个描述符中存储少量数据，如数组索引或指针，这使得访问与该描述符关联的数据更加容易。

首先，你必须使用[epoll_create()](http://linux.die.net/man/2/epoll_create)创建一个特殊的文件描述符。你不会读取或写入这个文件描述符。你将把它传递给其他 epoll_xxx 函数，并在结束时调用 close()。

```c
int epfd = epoll_create(1);
```

对于你想要使用 epoll 监控的每个文件描述符，你需要使用[epoll_ctl()](http://linux.die.net/man/2/epoll_ctl)和该选项将其添加到 epoll 数据结构中。你可以向其中添加任意数量的文件描述符。

```c
struct epoll_event event;
event.events = EPOLLOUT;  // EPOLLIN==read, EPOLLOUT==write
event.data.ptr = mypointer;
epoll_ctl(epfd, EPOLL_CTL_ADD, mypointer->fd, &event)
```

要等待一些文件描述符变为就绪状态，请使用[epoll_wait()](http://linux.die.net/man/2/epoll_wait)。它填充的 epoll_event 结构将包含你在添加此文件描述符时提供的 event.data 中的数据。这使得你可以轻松查找与该文件描述符关联的数据。

```c
int num_ready = epoll_wait(epfd, &event, 1, timeout_milliseconds);
if (num_ready > 0) {
 MyData *mypointer = (MyData*) event.data.ptr;
 printf("ready to write on %d\n", mypointer->fd);
}
```

假设你正在等待向文件描述符写入数据，但现在你想等待从它读取数据。只需使用该选项更改你正在监控的操作类型。

```c
event.events = EPOLLOUT;
event.data.ptr = mypointer;
epoll_ctl(epfd, EPOLL_CTL_MOD, mypointer->fd, &event);
```

要从 epoll 中取消一个文件描述符的订阅，同时保持其他文件描述符处于活动状态，请使用该选项。

```c
epoll_ctl(epfd, EPOLL_CTL_DEL, mypointer->fd, NULL);
```

要关闭一个 epoll 实例，关闭其文件描述符。

```c
close(epfd);
```

还可以将非阻塞和，任何对非阻塞套接字的调用也将是非阻塞的。要等待连接完成，请使用或 epoll 等待套接字可写。使用 epoll 而不是 select 有原因，但由于接口，这样做存在根本问题。

[关于 select 存在问题的博客文章](https://idea.popcount.org/2017-01-06-select-is-fundamentally-broken/)

### Epoll 示例

让我们分解一下手册页中的 epoll 代码。我们假设我们有一个准备好的 TCP 服务器套接字。我们首先要做的是创建 epoll 设备。

```c
epollfd = epoll_create1(0);
if (epollfd == -1) {
 perror("epoll_create1");
 exit(EXIT_FAILURE);
}
```

下一步是在触发模式下添加监听套接字。

```c
// This file object will be `read` from (connect is technically a read operation)
ev.events = EPOLLIN;
ev.data.fd = listen_sock;

// Add the socket in with all the other fds. Everything is a file descriptor
if (epoll_ctl(epollfd, EPOLL_CTL_ADD, listen_sock, &ev) == -1) {
 perror("epoll_ctl: listen_sock");
 exit(EXIT_FAILURE);
}
```

然后在循环中，我们等待并查看 epoll 是否有任何事件。

```c
struct epoll_event ev, events[MAX_EVENTS];
nfds = epoll_wait(epollfd, events, MAX_EVENTS, -1);
if (nfds == -1) {
 perror("epoll_wait");
 exit(EXIT_FAILURE);
}
```

如果我们在客户端套接字上接收到事件，这意味着客户端有数据准备好读取，我们执行这个操作。否则，我们需要更新我们的 epoll 结构以添加一个新的客户端。

```c
if (events[n].data.fd == listen_sock) {
 int conn_sock = accept(listen_sock, (struct sockaddr *) &addr, &addrlen);
 // Must set to non-blocking
 setnonblocking(conn_sock);

 // We will read from this file, and we only want to return once
 // we have something to read from. We don't want to keep getting
 // reminded if there is still data left (edge triggered)
 ev.events = EPOLLIN | EPOLLET;
 ev.data.fd = conn_sock;
 epoll_ctl(epollfd, EPOLL_CTL_ADD, conn_sock, &ev)
}
```

上述函数为了简洁省略了一些错误检查。请注意，这段代码性能良好，因为我们以触发模式添加了服务器套接字，并且以边缘触发模式添加了每个客户端文件描述符。边缘触发模式将更多的计算留给了应用程序的部分——应用程序必须继续读取或写入，直到文件描述符的字节用完——但它防止了饥饿。一个更高效的实现还会将监听套接字添加为边缘触发，以清除连接队列。 

在开始编程之前，请阅读大部分内容。有很多陷阱。以下是一些更常见的陷阱将详细说明。

### 各种 Epoll 陷阱

使用 epoll 有几个问题。这里我们将详细说明几个。

1.  有两种模式。触发模式和边缘触发模式。触发模式意味着当文件描述符上有事件时，它将在调用 ctl 函数时被 epoll 返回。在边缘触发模式下，调用者只有在从零事件变为事件时才会得到文件描述符。这意味着如果你忘记在文件描述符上读取、写入、接受等操作，直到你得到 EWOULDBLOCK，该文件描述符将被丢弃。

1.  如果在任何时候你复制一个文件描述符并将其添加到 epoll 中，你将从这个文件描述符和复制的文件描述符中接收到事件。

1.  你可以将 epoll 对象添加到 epoll 中。边缘触发和触发模式是相同的，因为 ctl 会将状态重置为零事件

1.  根据条件，你可能会得到一个从 Epoll 关闭的文件描述符。这不是一个错误。这种情况发生的原因是 epoll 在内核对象级别工作，而不是在文件描述符级别。如果内核对象存活时间更长并且设置了正确的标志，进程可能会得到一个关闭的文件描述符。这也意味着如果你关闭文件描述符，就没有办法移除内核对象。

1.  Epoll 有一个标志，在返回文件描述符后将其移除

1.  使用带级联模式的 Epoll 可能会饿死某些文件描述符，因为不知道应用程序将从每个描述符中读取多少数据。

更多信息请参阅或查看附录中提到的更好版本。

## 远程过程调用

RPC 或远程过程调用是我们可以在不同机器上执行过程的想法。在实践中，过程可能在同一台机器上执行。然而，它可能处于不同的上下文中。例如，在具有不同权限和不同生命周期的不同用户下执行操作。

例如，你可能可以向 docker 守护进程发送远程过程调用以更改容器的状态。并非每个应用程序都需要访问整个系统机器，但它们应该能够访问它们创建的容器。

### 权限分离

远程代码将在与调用者不同的用户和权限下执行。在实践中，远程调用可能具有比调用者更多或更少的权限。原则上，这可以通过确保组件以最低权限运行来提高系统的安全性。不幸的是，需要仔细评估安全顾虑，以确保 RPC 机制不会被滥用以执行不希望的操作。例如，RPC 实现可能隐式信任任何连接的客户端执行任何操作，而不是数据子集上的操作子集。

### 存根代码和序列化

存根代码是隐藏执行远程过程调用复杂性的必要代码。存根代码的一个角色是将必要的数据*序列化*为可以发送到远程服务器的字节流格式。

```c
// On the outside, 'getHiscore' looks like a normal function call
// On the inside, the stub code performs all of the work to send and receive data to and from the remote machine.

int getHighScore(char* game) {
 // Marshal the request into a sequence of bytes:
 char* buffer;
 asprintf(&buffer,"getHiscore(%s)!", name);

 // Send down the wire (we do not send the zero byte; the '!' signifies the end of the message)
 write(fd, buffer, strlen(buffer) );

 // Wait for the server to send a response
 ssize_t bytesread = read(fd, buffer, sizeof(buffer));

 // Example: unmarshal the bytes received back from text into an int
 buffer[bytesread] = 0; // Turn the result into a C string

 int score= atoi(buffer);
 free(buffer);
 return score;
}
```

使用字符串格式可能有点低效。一个很好的例子是 Golang 的 gRPC 或 Google RPC。如果你想要检查 C 版本，也可以找到。

服务器存根代码将接收请求，将请求反序列化为有效的内存数据调用底层实现，并将结果发送回调用者。通常，底层库会为你完成这项工作。

要实现 RPC，你需要决定并记录你将使用哪些约定将数据序列化为字节序列。即使是简单的整数也有几种常见的选择。

1.  签名还是未签名？

1.  ASCII、Unicode 文本格式 8，或其他编码？

1.  字节数是固定的还是根据大小可变的。

1.  如果使用二进制，是小端还是大端格式？

要序列化结构体，决定哪些字段需要序列化。可能没有必要发送所有数据项。例如，某些项可能与特定的 RPC 无关，或者可以从其他数据项中重新计算。

要序列化链表，没有必要发送链接指针，而是流式传输值。作为反序列化的一部分，服务器可以从字节序列中重新创建链表结构。

从头节点/顶点开始，可以通过递归访问一个简单的树来创建数据的序列化版本。一个循环图通常需要额外的内存来确保每个边和顶点恰好被处理一次。

### 接口描述语言

手动编写存根代码既痛苦又乏味，容易出错，难以维护，并且难以从实现代码中逆向工程线协议。更好的方法是指定数据对象、消息和服务，以自动生成客户端和服务器代码。现代接口描述语言的例子是 Google 的.proto 文件。

即使如此，远程过程调用（RPC）与本地调用相比，速度显著较慢（10 倍到 100 倍），并且更复杂。RPC 必须将数据序列化为线兼容的格式。这可能需要多次通过数据结构，临时内存分配以及数据表示的转换。

强健的 RPC 存根代码必须智能地处理网络故障和版本问题。例如，服务器可能需要处理仍在运行早期版本存根代码的客户端请求。

一个安全的 RPC 需要实现额外的安全检查，包括身份验证和授权，验证数据并加密客户端和主机之间的通信。很多时候，RPC 系统可以为你高效地完成这些工作。考虑一下，如果你在同一台机器上既有 RPC 客户端又有服务器。启动一个 thrift 或 Google RPC 服务器可以验证并将请求路由到本地套接字，该套接字不会通过网络发送。

### 转移结构化数据

让我们考察三种使用三种不同格式（JSON、XML 和 Google Protocol Buffers）传输数据的方法。JSON 和 XML 是基于文本的协议。以下是一些 JSON 和 XML 消息的示例。

```c
<ticket><price currency='dollar'>10</price><vendor>travelocity</vendor></ticket>
```

```c
{ 'currency':'dollar' , 'vendor':'travelocity', 'price':'10' }
```

Google Protocol Buffers 是一个开源的高效二进制协议，它强调高吞吐量，同时具有低 CPU 开销和最小内存复制。这意味着可以从.proto 规范文件生成多种语言的客户端和服务器存根代码，以将数据序列化到和从二进制流中。

[Google Protocol Buffers](https://developers.google.com/protocol-buffers/docs/overview)通过忽略消息中存在的未知字段来减少版本问题。有关 Protocol Buffers 的更多信息，请参阅其介绍。

通常的链路是抽象出实际的业务逻辑和各种序列化代码。如果你的应用程序在解析 XML、JSON 或 YAML 时成为 CPU 密集型，切换到协议缓冲区！

## 主题

+   IPv4 与 IPv6

+   TCP 与 UDP

+   数据包丢失/基于连接的

+   获取地址信息

+   DNS

+   TCP 客户端调用

+   TCP 服务器调用

+   关闭

+   recvfrom

+   epoll 与 select

+   RPC

## 问题

+   什么是 IPv4？什么是 IPv6？它们之间有什么区别？

+   什么是 TCP？什么是 UDP？请给出两者的优缺点。在什么情况下使用其中一个而不是另一个？

+   哪个协议是无连接的，哪个是基于连接的？

+   DNS 是什么？DNS 采取的路径是什么？

+   网络套接字的作用是什么？

+   设置 TCP 客户端的调用有哪些？

+   设置 TCP 服务器的调用有哪些？

+   网络套接字关闭和关闭之间的区别是什么？

+   何时可以使用和？关于又如何？

+   与相比，有哪些优势？关于又如何？

+   远程过程调用是什么？在什么情况下应该使用它而不是 HTTP 或本地运行代码？

+   marshaling/unmarshaling 是什么？为什么 HTTP 不是 RPC？
