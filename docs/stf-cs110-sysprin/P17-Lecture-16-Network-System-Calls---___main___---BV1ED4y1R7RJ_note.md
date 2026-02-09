# 网络系统调用教程 P17：第16讲 🌐

![](img/1175ce1bb2aa4c74fdf727bbf8d79962_1.png)

![](img/1175ce1bb2aa4c74fdf727bbf8d79962_3.png)

在本节课中，我们将学习网络编程中的核心系统调用，特别是如何通过套接字（socket）实现不同计算机之间的通信。我们将从解析主机名开始，逐步深入到创建客户端和服务器套接字的具体步骤。

---

## 主机名解析与IP地址获取 🔍

上一节我们讨论了多线程与多进程的交互。本节中，我们来看看网络编程的基础：如何将人类可读的主机名（如 `www.facebook.com`）转换为计算机可识别的IP地址。

### `gethostbyname` 函数

`gethostbyname` 函数用于根据主机名获取其对应的IP地址信息。它接收一个主机名字符串，并返回一个 `struct hostent` 结构体指针。

```c
struct hostent *gethostbyname(const char *name);
```

如果解析失败，该函数返回 `NULL`。失败原因可能是DNS服务器故障、网络问题或主机名不存在。

![](img/1175ce1bb2aa4c74fdf727bbf8d79962_5.png)

### `struct hostent` 结构体

![](img/1175ce1bb2aa4c74fdf727bbf8d79962_7.png)

该结构体包含了主机的详细信息。以下是其核心字段：

![](img/1175ce1bb2aa4c74fdf727bbf8d79962_9.png)

![](img/1175ce1bb2aa4c74fdf727bbf8d79962_11.png)

*   `h_name`: 指向官方主机名的指针。
*   `h_aliases`: 一个指向字符串指针数组的指针，表示该主机的别名列表。列表以 `NULL` 指针结束。
*   `h_addrtype`: 地址类型，例如 `AF_INET` 代表IPv4地址。
*   `h_length`: 地址长度（字节数）。对于IPv4，此值为4。
*   `h_addr_list`: 一个指向网络地址指针数组的指针。对于IPv4，每个地址是一个 `struct in_addr`。列表以 `NULL` 指针结束。

![](img/1175ce1bb2aa4c74fdf727bbf8d79962_13.png)

![](img/1175ce1bb2aa4c74fdf727bbf8d79962_15.png)

`struct in_addr` 是一个特殊的结构体，通常只包含一个成员 `s_addr`，它是一个表示IPv4地址的32位无符号整数。

![](img/1175ce1bb2aa4c74fdf727bbf8d79962_17.png)

### 字节序问题

![](img/1175ce1bb2aa4c74fdf727bbf8d79962_19.png)

![](img/1175ce1bb2aa4c74fdf727bbf8d79962_21.png)

![](img/1175ce1bb2aa4c74fdf727bbf8d79962_22.png)

计算机存储多字节数据（如32位IP地址）有两种顺序：**小端序**（低位字节在前）和**大端序**（高位字节在前）。为了保证网络通信的一致性，数据在发送前需要转换为**网络字节序**（大端序）。我们使用以下函数进行转换：

![](img/1175ce1bb2aa4c74fdf727bbf8d79962_24.png)

![](img/1175ce1bb2aa4c74fdf727bbf8d79962_26.png)

*   `htons()`: 将16位短整型（如端口号）从主机字节序转换为网络字节序。
*   `htonl()`: 将32位长整型从主机字节序转换为网络字节序。
*   `ntohs()`: 将16位短整型从网络字节序转换回主机字节序。
*   `ntohl()`: 将32位长整型从网络字节序转换回主机字节序。

![](img/1175ce1bb2aa4c74fdf727bbf8d79962_28.png)

![](img/1175ce1bb2aa4c74fdf727bbf8d79962_30.png)

![](img/1175ce1bb2aa4c74fdf727bbf8d79962_32.png)

![](img/1175ce1bb2aa4c74fdf727bbf8d79962_34.png)

![](img/1175ce1bb2aa4c74fdf727bbf8d79962_36.png)

### 示例：解析主机名

![](img/1175ce1bb2aa4c74fdf727bbf8d79962_38.png)

![](img/1175ce1bb2aa4c74fdf727bbf8d79962_40.png)

![](img/1175ce1bb2aa4c74fdf727bbf8d79962_42.png)

以下是使用 `gethostbyname` 和 `inet_ntop`（将网络地址转换为点分十进制字符串）的代码示例：

![](img/1175ce1bb2aa4c74fdf727bbf8d79962_44.png)

![](img/1175ce1bb2aa4c74fdf727bbf8d79962_46.png)

![](img/1175ce1bb2aa4c74fdf727bbf8d79962_48.png)

![](img/1175ce1bb2aa4c74fdf727bbf8d79962_50.png)

![](img/1175ce1bb2aa4c74fdf727bbf8d79962_52.png)

```c
#include <netdb.h>
#include <arpa/inet.h>
#include <stdio.h>

![](img/1175ce1bb2aa4c74fdf727bbf8d79962_54.png)

![](img/1175ce1bb2aa4c74fdf727bbf8d79962_56.png)

![](img/1175ce1bb2aa4c74fdf727bbf8d79962_58.png)

![](img/1175ce1bb2aa4c74fdf727bbf8d79962_60.png)

![](img/1175ce1bb2aa4c74fdf727bbf8d79962_62.png)

![](img/1175ce1bb2aa4c74fdf727bbf8d79962_64.png)

![](img/1175ce1bb2aa4c74fdf727bbf8d79962_66.png)

void resolve_hostname(const char* hostname) {
    struct hostent *he = gethostbyname(hostname);
    if (he == NULL) {
        fprintf(stderr, "无法解析主机名: %s\n", hostname);
        return;
    }

    printf("官方名称: %s\n", he->h_name);

    // 遍历地址列表
    struct in_addr **addr_list = (struct in_addr **)he->h_addr_list;
    for (int i = 0; addr_list[i] != NULL; i++) {
        char ip_str[INET_ADDRSTRLEN];
        inet_ntop(AF_INET, addr_list[i], ip_str, sizeof(ip_str));
        printf("IP地址 %d: %s\n", i+1, ip_str);
    }
}
```

![](img/1175ce1bb2aa4c74fdf727bbf8d79962_68.png)

---

![](img/1175ce1bb2aa4c74fdf727bbf8d79962_70.png)

![](img/1175ce1bb2aa4c74fdf727bbf8d79962_72.png)

![](img/1175ce1bb2aa4c74fdf727bbf8d79962_74.png)

## 套接字地址结构 🏗️

![](img/1175ce1bb2aa4c74fdf727bbf8d79962_76.png)

![](img/1175ce1bb2aa4c74fdf727bbf8d79962_78.png)

在深入创建套接字之前，我们需要理解用于表示网络地址的通用结构。

![](img/1175ce1bb2aa4c74fdf727bbf8d79962_80.png)

![](img/1175ce1bb2aa4c74fdf727bbf8d79962_82.png)

![](img/1175ce1bb2aa4c74fdf727bbf8d79962_84.png)

### 通用套接字地址：`struct sockaddr`

![](img/1175ce1bb2aa4c74fdf727bbf8d79962_86.png)

![](img/1175ce1bb2aa4c74fdf727bbf8d79962_88.png)

![](img/1175ce1bb2aa4c74fdf727bbf8d79962_90.png)

![](img/1175ce1bb2aa4c74fdf727bbf8d79962_92.png)

![](img/1175ce1bb2aa4c74fdf727bbf8d79962_94.png)

这是一个通用的地址结构，用于在函数调用中传递地址信息。其定义如下：

![](img/1175ce1bb2aa4c74fdf727bbf8d79962_96.png)

![](img/1175ce1bb2aa4c74fdf727bbf8d79962_98.png)

```c
struct sockaddr {
    sa_family_t sa_family; // 地址族（如 AF_INET, AF_INET6）
    char        sa_data[14]; // 协议地址
};
```

![](img/1175ce1bb2aa4c74fdf727bbf8d79962_100.png)

![](img/1175ce1bb2aa4c74fdf727bbf8d79962_102.png)

![](img/1175ce1bb2aa4c74fdf727bbf8d79962_104.png)

### 互联网套接字地址（IPv4）：`struct sockaddr_in`

![](img/1175ce1bb2aa4c74fdf727bbf8d79962_106.png)

![](img/1175ce1bb2aa4c74fdf727bbf8d79962_108.png)

![](img/1175ce1bb2aa4c74fdf727bbf8d79962_110.png)

![](img/1175ce1bb2aa4c74fdf727bbf8d79962_112.png)

这是实际用于IPv4通信的地址结构。它包含具体的地址信息。

![](img/1175ce1bb2aa4c74fdf727bbf8d79962_114.png)

```c
struct sockaddr_in {
    sa_family_t    sin_family; // 地址族，必须为 AF_INET
    in_port_t      sin_port;   // 端口号（网络字节序）
    struct in_addr sin_addr;   // IPv4地址
    unsigned char  sin_zero[8]; // 填充字段，通常设为0
};
```

### 类型转换

由于像 `connect`、`bind` 这样的系统调用接收通用的 `struct sockaddr*` 指针，我们在传递 `struct sockaddr_in` 地址时需要进行强制类型转换。

![](img/1175ce1bb2aa4c74fdf727bbf8d79962_116.png)

```c
struct sockaddr_in server_addr;
// ... 填充 server_addr ...
connect(sockfd, (struct sockaddr *)&server_addr, sizeof(server_addr));
```

系统调用内部通过检查 `sa_family` 字段来判断具体的地址类型并进行相应处理。

![](img/1175ce1bb2aa4c74fdf727bbf8d79962_118.png)

---

## 创建客户端套接字 🖥️➡️🌐

![](img/1175ce1bb2aa4c74fdf727bbf8d79962_120.png)

![](img/1175ce1bb2aa4c74fdf727bbf8d79962_122.png)

客户端套接字用于主动发起与远程服务器的连接。

创建客户端套接字主要分为以下几步：

1.  **解析服务器主机名**：使用 `gethostbyname` 获取服务器的IP地址。
2.  **创建套接字描述符**：使用 `socket()` 系统调用创建一个新的套接字。
3.  **填充服务器地址结构**：创建一个 `struct sockaddr_in`，填入服务器IP、端口，并确保字节序正确。
4.  **发起连接**：使用 `connect()` 系统调用尝试连接到服务器。
5.  **错误处理**：如果任何步骤失败，需要妥善关闭已打开的套接字描述符。

以下是核心代码框架：

![](img/1175ce1bb2aa4c74fdf727bbf8d79962_124.png)

```c
int create_client_socket(const char* hostname, int port) {
    // 1. 解析主机名
    struct hostent *he = gethostbyname(hostname);
    if (he == NULL) return -1;

    // 2. 创建套接字
    int sockfd = socket(AF_INET, SOCK_STREAM, 0);
    if (sockfd < 0) return -1;

    // 3. 填充服务器地址
    struct sockaddr_in server_addr;
    memset(&server_addr, 0, sizeof(server_addr));
    server_addr.sin_family = AF_INET;
    server_addr.sin_port = htons(port); // 转换端口字节序
    // 复制IP地址，注意h_addr_list是指针的指针
    server_addr.sin_addr = *((struct in_addr *)he->h_addr_list[0]);

    // 4. 发起连接
    if (connect(sockfd, (struct sockaddr *)&server_addr, sizeof(server_addr)) < 0) {
        close(sockfd); // 5. 连接失败，关闭套接字
        return -1;
    }
    // 连接成功，返回套接字描述符
    return sockfd;
}
```

![](img/1175ce1bb2aa4c74fdf727bbf8d79962_126.png)

![](img/1175ce1bb2aa4c74fdf727bbf8d79962_128.png)

**注意**：调用此函数成功获取套接字后，使用者负责在通信结束时调用 `close()` 关闭它。

![](img/1175ce1bb2aa4c74fdf727bbf8d79962_130.png)

![](img/1175ce1bb2aa4c74fdf727bbf8d79962_132.png)

![](img/1175ce1bb2aa4c74fdf727bbf8d79962_134.png)

---

![](img/1175ce1bb2aa4c74fdf727bbf8d79962_136.png)

## 创建服务器套接字 🌐➡️🖥️

服务器套接字用于在本地监听，等待客户端的连接请求。

![](img/1175ce1bb2aa4c74fdf727bbf8d79962_138.png)

创建服务器套接字主要分为以下几步：

![](img/1175ce1bb2aa4c74fdf727bbf8d79962_140.png)

![](img/1175ce1bb2aa4c74fdf727bbf8d79962_142.png)

![](img/1175ce1bb2aa4c74fdf727bbf8d79962_144.png)

1.  **创建套接字描述符**：使用 `socket()` 系统调用。
2.  **填充本地地址结构**：创建一个 `struct sockaddr_in`。通常将IP地址设置为 `INADDR_ANY`（0.0.0.0），表示监听本机所有网络接口。端口设置为要监听的端口。
3.  **绑定地址**：使用 `bind()` 系统调用将套接字与特定的IP地址和端口绑定。
4.  **开始监听**：使用 `listen()` 系统调用，将套接字置于被动监听模式，准备接受连接。
5.  **错误处理**：如果绑定或监听失败，需要关闭套接字。

![](img/1175ce1bb2aa4c74fdf727bbf8d79962_146.png)

以下是核心代码框架：

![](img/1175ce1bb2aa4c74fdf727bbf8d79962_148.png)

```c
int create_server_socket(int port, int backlog) {
    // 1. 创建套接字
    int sockfd = socket(AF_INET, SOCK_STREAM, 0);
    if (sockfd < 0) return -1;

    // 2. 填充本地地址（允许任何接口连接）
    struct sockaddr_in server_addr;
    memset(&server_addr, 0, sizeof(server_addr));
    server_addr.sin_family = AF_INET;
    server_addr.sin_addr.s_addr = htonl(INADDR_ANY); // 监听所有IP
    server_addr.sin_port = htons(port); // 设置监听端口

    // 3. 绑定地址
    if (bind(sockfd, (struct sockaddr *)&server_addr, sizeof(server_addr)) < 0) {
        close(sockfd);
        return -1;
    }

    // 4. 开始监听
    // backlog参数定义了等待连接队列的最大长度
    if (listen(sockfd, backlog) < 0) {
        close(sockfd);
        return -1;
    }
    // 监听成功，返回服务器套接字描述符
    return sockfd;
}
```

![](img/1175ce1bb2aa4c74fdf727bbf8d79962_150.png)

**关键点说明**：
*   `INADDR_ANY`：一个特殊地址，表示服务器愿意接受来自任何网络接口（如以太网、Wi-Fi）的连接。
*   `listen()` 的 `backlog` 参数：指定了内核为此套接字排队的最大未完成连接数。超过此数量的连接请求可能会被拒绝。

![](img/1175ce1bb2aa4c74fdf727bbf8d79962_152.png)

服务器套接字创建成功后，可以使用 `accept()` 系统调用来接受具体的客户端连接，该调用会返回一个用于与客户端通信的**新套接字描述符**。原始的服务器套接字继续用于监听新的连接请求。

---

![](img/1175ce1bb2aa4c74fdf727bbf8d79962_154.png)

## 总结 📚

![](img/1175ce1bb2aa4c74fdf727bbf8d79962_156.png)

本节课中我们一起学习了网络系统调用的核心内容：

1.  **主机名解析**：使用 `gethostbyname` 将域名转换为IP地址，并理解了 `struct hostent` 结构体和网络字节序的概念。
2.  **套接字地址结构**：了解了通用的 `struct sockaddr` 和具体的 `struct sockaddr_in`（IPv4）结构体，以及它们之间的类型转换。
3.  **客户端套接字**：掌握了创建客户端连接的流程：解析主机名 -> 创建套接字 -> 填充地址 -> 调用 `connect()`。
4.  **服务器套接字**：掌握了创建服务器监听端口的流程：创建套接字 -> 填充地址（常使用 `INADDR_ANY`） -> 调用 `bind()` -> 调用 `listen()`。

理解这些基础系统调用是进行更高级网络编程（如构建HTTP服务器、聊天程序等）的基石。记住，网络编程涉及许多细节和边界情况，充分的测试和错误处理至关重要。