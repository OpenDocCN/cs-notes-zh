# 15：网络基础介绍 🖧

![](img/cadd01ed9181ee7a91b8f70291dda578_1.png)

在本节课中，我们将要学习计算机网络的基础知识，包括服务器与客户端的概念、端口与套接字的作用，以及如何编写一个简单的网络程序来实现通信。

![](img/cadd01ed9181ee7a91b8f70291dda578_3.png)

---

## 概述

![](img/cadd01ed9181ee7a91b8f70291dda578_5.png)

![](img/cadd01ed9181ee7a91b8f70291dda578_7.png)

![](img/cadd01ed9181ee7a91b8f70291dda578_9.png)

网络是将两台或多台计算机连接起来进行通信的技术。它类似于进程间的管道，但范围更广，可以实现不同计算机之间的数据交换。互联网和万维网都基于此原理工作。

![](img/cadd01ed9181ee7a91b8f70291dda578_11.png)

![](img/cadd01ed9181ee7a91b8f70291dda578_13.png)

我们将从基础概念开始，逐步学习如何创建一个服务器程序来监听连接，以及如何创建一个客户端程序来请求服务。

![](img/cadd01ed9181ee7a91b8f70291dda578_15.png)

![](img/cadd01ed9181ee7a91b8f70291dda578_17.png)

![](img/cadd01ed9181ee7a91b8f70291dda578_18.png)

![](img/cadd01ed9181ee7a91b8f70291dda578_20.png)

![](img/cadd01ed9181ee7a91b8f70291dda578_22.png)

---

![](img/cadd01ed9181ee7a91b8f70291dda578_24.png)

![](img/cadd01ed9181ee7a91b8f70291dda578_25.png)

![](img/cadd01ed9181ee7a91b8f70291dda578_27.png)

## 服务器与客户端

![](img/cadd01ed9181ee7a91b8f70291dda578_29.png)

![](img/cadd01ed9181ee7a91b8f70291dda578_31.png)

![](img/cadd01ed9181ee7a91b8f70291dda578_33.png)

![](img/cadd01ed9181ee7a91b8f70291dda578_35.png)

上一节我们介绍了网络的基本概念，本节中我们来看看网络通信中的两个核心角色：服务器和客户端。

服务器是一台等待其他计算机（客户端）发起连接的计算机。客户端则是主动向服务器发起连接请求的一方。例如，当你访问一个网站时，你的浏览器是客户端，而托管网站的计算机就是服务器。

![](img/cadd01ed9181ee7a91b8f70291dda578_37.png)

![](img/cadd01ed9181ee7a91b8f70291dda578_39.png)

![](img/cadd01ed9181ee7a91b8f70291dda578_40.png)

服务器必须提前设置并运行，才能响应客户端的连接请求。一个服务器可以同时处理多个客户端的连接。

![](img/cadd01ed9181ee7a91b8f70291dda578_42.png)

![](img/cadd01ed9181ee7a91b8f70291dda578_44.png)

![](img/cadd01ed9181ee7a91b8f70291dda578_46.png)

![](img/cadd01ed9181ee7a91b8f70291dda578_48.png)

![](img/cadd01ed9181ee7a91b8f70291dda578_50.png)

---

![](img/cadd01ed9181ee7a91b8f70291dda578_52.png)

![](img/cadd01ed9181ee7a91b8f70291dda578_54.png)

![](img/cadd01ed9181ee7a91b8f70291dda578_56.png)

## 端口与套接字

![](img/cadd01ed9181ee7a91b8f70291dda578_58.png)

![](img/cadd01ed9181ee7a91b8f70291dda578_60.png)

![](img/cadd01ed9181ee7a91b8f70291dda578_62.png)

![](img/cadd01ed9181ee7a91b8f70291dda578_64.png)

理解了服务器和客户端的关系后，我们来看看它们是如何具体建立连接的。这需要通过**端口**和**套接字**来实现。

![](img/cadd01ed9181ee7a91b8f70291dda578_66.png)

**套接字**是一个用于标识网络连接的整数，范围通常是0到65535。你可以将其理解为一个虚拟的进程ID，它代表了一个特定的网络连接端点。

![](img/cadd01ed9181ee7a91b8f70291dda578_68.png)

**端口号**是套接字的具体编号。服务器会监听一个特定的端口，等待客户端连接。当客户端想要连接服务器时，它需要知道服务器的IP地址和端口号。

![](img/cadd01ed9181ee7a91b8f70291dda578_70.png)

![](img/cadd01ed9181ee7a91b8f70291dda578_72.png)

以下是查看当前计算机上正在监听的端口的命令示例：
```bash
netstat -plnt
```

端口号分为几个范围：
*   **0-1023**：系统端口，通常用于标准服务（如HTTP的80端口，SSH的22端口）。
*   **1024-49151**：注册端口，可供用户程序申请使用。
*   **49152-65535**：动态或私有端口，可供临时使用。

![](img/cadd01ed9181ee7a91b8f70291dda578_74.png)

两台计算机不能在同一端口上同时运行监听服务。

![](img/cadd01ed9181ee7a91b8f70291dda578_76.png)

---

![](img/cadd01ed9181ee7a91b8f70291dda578_78.png)

![](img/cadd01ed9181ee7a91b8f70291dda578_80.png)

![](img/cadd01ed9181ee7a91b8f70291dda578_81.png)

## 编写时间服务器

![](img/cadd01ed9181ee7a91b8f70291dda578_83.png)

现在我们已经了解了端口和套接字，让我们动手实践，编写一个简单的服务器程序。这个服务器将监听客户端的连接，并在连接建立后，向客户端发送当前的格林威治标准时间。

以下是创建服务器套接字并进入监听循环的核心代码框架：
```cpp
int server = createServerSocket(portNumber);
while (true) {
    int client = accept(server, nullptr, nullptr); // 等待客户端连接
    publishTime(client); // 向客户端发送时间
    close(client); // 关闭客户端连接
}
```
`createServerSocket` 函数封装了底层的系统调用，用于创建和绑定服务器套接字。`accept` 函数会阻塞，直到有客户端连接进来。

---

![](img/cadd01ed9181ee7a91b8f70291dda578_85.png)

![](img/cadd01ed9181ee7a91b8f70291dda578_87.png)

## 处理时间数据

![](img/cadd01ed9181ee7a91b8f70291dda578_89.png)

![](img/cadd01ed9181ee7a91b8f70291dda578_91.png)

在 `publishTime` 函数中，我们需要获取当前时间并将其格式化为字符串发送给客户端。

我们使用 `time` 函数获取自1970年1月1日（Unix纪元）以来的秒数，这是一个 `time_t` 类型的整数。然后使用 `gmtime` 函数将其转换为包含年、月、日等详细信息的 `struct tm` 结构体。最后，使用 `strftime` 函数将时间格式化为字符串。

需要注意的是，标准的 `gmtime` 函数返回一个指向静态内存的指针，这在多线程环境下是不安全的。因此，在编写多线程服务器时，应使用其线程安全版本 `gmtime_r`。

![](img/cadd01ed9181ee7a91b8f70291dda578_93.png)

![](img/cadd01ed9181ee7a91b8f70291dda578_95.png)

以下是获取并格式化时间的代码示例：
```cpp
time_t rawtime;
time(&rawtime);
struct tm tm;
gmtime_r(&rawtime, &tm); // 线程安全版本
char timeStr[128];
strftime(timeStr, sizeof(timeStr), "%c", &tm);
// 然后将 timeStr 发送给客户端
```

---

## 使用 Socket++ 库简化操作

![](img/cadd01ed9181ee7a91b8f70291dda578_97.png)

![](img/cadd01ed9181ee7a91b8f70291dda578_99.png)

![](img/cadd01ed9181ee7a91b8f70291dda578_101.png)

![](img/cadd01ed9181ee7a91b8f70291dda578_103.png)

![](img/cadd01ed9181ee7a91b8f70291dda578_105.png)

![](img/cadd01ed9181ee7a91b8f70291dda578_107.png)

上一节我们手动处理了数据的写入和连接关闭，过程稍显繁琐。本节中我们来看看如何使用 `Socket++` 库来简化网络编程。

![](img/cadd01ed9181ee7a91b8f70291dda578_108.png)

![](img/cadd01ed9181ee7a91b8f70291dda578_110.png)

![](img/cadd01ed9181ee7a91b8f70291dda578_112.png)

![](img/cadd01ed9181ee7a91b8f70291dda578_114.png)

`Socket++` 库提供了更高级的抽象，可以像操作C++标准流（如 `cout`）一样操作网络连接，并自动管理缓冲区和资源释放。

![](img/cadd01ed9181ee7a91b8f70291dda578_116.png)

![](img/cadd01ed9181ee7a91b8f70291dda578_118.png)

![](img/cadd01ed9181ee7a91b8f70291dda578_120.png)

使用 `Socket++` 重写时间发送逻辑的代码如下：
```cpp
#include <socket++/sockstream.h>
// ... 创建 client 套接字 ...
sockbuf sb(client);
iosockstream ss(&sb);
ss << timeStr << endl;
// 退出作用域时，sockbuf的析构函数会自动关闭client
```
这使得代码更加简洁易读。

![](img/cadd01ed9181ee7a91b8f70291dda578_122.png)

![](img/cadd01ed9181ee7a91b8f70291dda578_124.png)

---

![](img/cadd01ed9181ee7a91b8f70291dda578_126.png)

![](img/cadd01ed9181ee7a91b8f70291dda578_128.png)

## 引入多线程提升性能

![](img/cadd01ed9181ee7a91b8f70291dda578_130.png)

![](img/cadd01ed9181ee7a91b8f70291dda578_132.png)

![](img/cadd01ed9181ee7a91b8f70291dda578_134.png)

我们之前编写的服务器一次只能处理一个客户端请求，效率很低。本节我们将利用多线程技术来提升服务器的并发处理能力。

![](img/cadd01ed9181ee7a91b8f70291dda578_136.png)

我们可以使用**线程池**。当有新的客户端连接时，服务器主线程迅速接受连接，然后将处理该客户端请求的任务（如 `publishTime`）提交给线程池中的一个空闲线程去执行。这样，主线程就可以立即返回去接受下一个连接，而多个客户端请求可以被并行处理。

以下是使用线程池调度任务的核心代码：
```cpp
ThreadPool pool(4); // 创建包含4个工作线程的线程池
while (true) {
    int client = accept(server, nullptr, nullptr);
    pool.schedule([client] {
        publishTime(client);
        close(client);
    });
}
```
在下一个作业中，你将有机会自己实现一个线程池。

---

## 编写时间客户端

![](img/cadd01ed9181ee7a91b8f70291dda578_138.png)

![](img/cadd01ed9181ee7a91b8f70291dda578_140.png)

服务器准备就绪后，我们需要一个客户端来测试它。编写客户端相对更简单。

![](img/cadd01ed9181ee7a91b8f70291dda578_141.png)

![](img/cadd01ed9181ee7a91b8f70291dda578_143.png)

![](img/cadd01ed9181ee7a91b8f70291dda578_145.png)

客户端的核心任务是连接到指定服务器的指定端口，然后读取服务器发送回来的数据。

![](img/cadd01ed9181ee7a91b8f70291dda578_147.png)

![](img/cadd01ed9181ee7a91b8f70291dda578_149.png)

以下是客户端代码的核心部分：
```cpp
int clientSocket = createClientSocket(serverHost, portNumber);
sockbuf sb(clientSocket);
iosockstream ss(&sb);
string timeline;
getline(ss, timeline); // 读取服务器发来的一行数据
cout << timeline << endl;
```
`createClientSocket` 函数负责建立到服务器的连接。之后，我们同样可以使用 `Socket++` 库来方便地读取数据。

![](img/cadd01ed9181ee7a91b8f70291dda578_151.png)

![](img/cadd01ed9181ee7a91b8f70291dda578_153.png)

---

![](img/cadd01ed9181ee7a91b8f70291dda578_154.png)

![](img/cadd01ed9181ee7a91b8f70291dda578_156.png)

![](img/cadd01ed9181ee7a91b8f70291dda578_157.png)

## 探索 HTTP 协议

我们构建了自定义协议的时间服务器。在现实世界中，最常用的应用层协议是 **HTTP**（超文本传输协议）。本节我们通过一个简单工具来直观感受HTTP。

我们可以使用 `telnet` 命令手动模拟一个HTTP客户端。`telnet` 可以建立到任何TCP服务器的纯文本连接。

![](img/cadd01ed9181ee7a91b8f70291dda578_159.png)

![](img/cadd01ed9181ee7a91b8f70291dda578_161.png)

![](img/cadd01ed9181ee7a91b8f70291dda578_162.png)

例如，连接到谷歌的Web服务器（端口80）并请求主页：
```bash
telnet google.com 80
```
连接成功后，手动输入HTTP请求：
```
GET / HTTP/1.1
Host: google.com
```
（输入两个空行结束请求头）
服务器将返回谷歌首页的HTML代码。这直观地展示了浏览器与Web服务器之间的通信本质。

![](img/cadd01ed9181ee7a91b8f70291dda578_164.png)

---

## 总结

![](img/cadd01ed9181ee7a91b8f70291dda578_166.png)

![](img/cadd01ed9181ee7a91b8f70291dda578_168.png)

本节课中我们一起学习了计算机网络的基础知识。我们从服务器与客户端模型入手，理解了端口和套接字作为通信端点的作用。我们实践了如何编写一个多线程的时间服务器，以及与之配套的客户端程序，并使用了 `Socket++` 库来简化网络I/O操作。最后，我们通过 `telnet` 工具窥探了HTTP协议的工作方式，为后续学习更复杂的网络应用打下了基础。

![](img/cadd01ed9181ee7a91b8f70291dda578_170.png)

网络编程的核心在于理解连接是如何建立、数据是如何在套接字之间可靠传输的。掌握了这些基础，你就能构建出各种网络应用程序。