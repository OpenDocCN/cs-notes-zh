# 编写你自己的操作系统：A09：TCP与简易HTTP服务器 🖥️

![](img/7dbc400bd678ed3d1daabde601b2f13b_1.png)

在本节课中，我们将继续学习传输控制协议（TCP），并尝试实现一个简易的HTTP服务器。我们将调试之前遇到的连接问题，并最终实现与外部网络（如Web浏览器）的基本通信。

---

![](img/7dbc400bd678ed3d1daabde601b2f13b_3.png)

![](img/7dbc400bd678ed3d1daabde601b2f13b_5.png)

## 概述

上一节我们介绍了TCP连接的基本握手过程。本节中，我们将深入调试连接问题，修正数据包长度计算错误，并最终实现一个能够响应HTTP请求的简易服务器。

---

## 调试TCP连接问题 🔍

![](img/7dbc400bd678ed3d1daabde601b2f13b_7.png)

在上一节的末尾，我们遇到了TCP连接异常和数据传输问题。首先，我们需要减少网络驱动程序的输出，以便更清晰地观察TCP数据包。

![](img/7dbc400bd678ed3d1daabde601b2f13b_9.png)

以下是修改网络驱动程序，使其仅打印TCP部分（从第34字节开始）的代码：

![](img/7dbc400bd678ed3d1daabde601b2f13b_11.png)

![](img/7dbc400bd678ed3d1daabde601b2f13b_13.png)

```c
// 仅打印从第34字节开始的数据（跳过14字节以太网帧头和20字节IPv4头）
print_bytes_from_offset(packet_data, 34);
```

![](img/7dbc400bd678ed3d1daabde601b2f13b_15.png)

![](img/7dbc400bd678ed3d1daabde601b2f13b_17.png)

修改后，控制台输出变得清晰，我们主要看到TCP消息。最初几条消息是ARP请求，可以忽略。我们重点关注后续的TCP消息。

---

![](img/7dbc400bd678ed3d1daabde601b2f13b_19.png)

## 分析TCP消息

![](img/7dbc400bd678ed3d1daabde601b2f13b_21.png)

我们发送并接收了多条消息。每条TCP消息包含源端口、目标端口、序列号、确认号等字段。关键信息在于标志位（Flags）。

![](img/7dbc400bd678ed3d1daabde601b2f13b_23.png)

例如，我们发送的标志位是 `0x02`，这代表 **SYN**（同步）标志。然而，我们期望在连接建立后发送 **SYN-ACK**（同步-确认）标志，即 `0x12`。

检查内核代码发现，我们在 `TCP connect` 函数中存在逻辑错误，导致重复创建了监听套接字。修正后，我们成功收到了正确的 `SYN-ACK` 响应。

---

![](img/7dbc400bd678ed3d1daabde601b2f13b_25.png)

![](img/7dbc400bd678ed3d1daabde601b2f13b_27.png)

## 数据传输与确认

成功建立连接后，我们尝试发送数据 “Hello TCP”。我们为数据包设置了 **PSH**（推送）和 **ACK**（确认）标志。PSH标志要求接收方立即处理数据，而不是缓冲。

我们成功将数据发送到了虚拟机外部，并收到了确认响应。这是一个重要的里程碑，表明我们的操作系统能够通过TCP与外部机器通信。

![](img/7dbc400bd678ed3d1daabde601b2f13b_29.png)

---

## 连接关闭与问题排查

在关闭连接时，我们遇到了异常。Netcat（我们使用的测试工具）发送了 **FIN-ACK**（结束-确认）标志，我们进行了确认，但随后收到了重复的数据包。

问题根源在于之前IPv4视频中提到的数据包长度计算错误。我们错误地将整个以太网帧的长度（包括填充的零字节）添加到了确认号中，导致序列号与远程机器不同步。

修正方法是计算IP消息的实际长度，忽略末尾的填充零字节。以下是修正逻辑：

![](img/7dbc400bd678ed3d1daabde601b2f13b_31.png)

```c
// 查找消息中最后一个非零字节的位置
int actual_length = find_last_non_zero(packet_data, total_length);
acknowledgement_number += actual_length; // 仅添加有效数据长度
```

修正后，确认号正确，连接能够正常关闭。

---

## 实现TCP重置（RST）功能

在某些异常情况下，我们需要发送 **RST**（重置）标志来终止连接。我们在TCP处理函数中添加了重置逻辑。

如果收到非法数据或需要强制终止连接，我们构造一个临时的TCP套接字，设置相应的序列号和确认号，并发送RST标志包。

以下是发送RST的示例代码：

```c
if (need_reset) {
    TCP_Socket temp_socket;
    temp_socket.sequence_number = incoming_ack_number;
    temp_socket.acknowledgement_number = incoming_sequence_number;
    send_tcp_packet(&temp_socket, RST_FLAG);
}
```

测试表明，重置功能正常工作，能够立即终止连接。

![](img/7dbc400bd678ed3d1daabde601b2f13b_33.png)

![](img/7dbc400bd678ed3d1daabde601b2f13b_35.png)

---

![](img/7dbc400bd678ed3d1daabde601b2f13b_37.png)

![](img/7dbc400bd678ed3d1daabde601b2f13b_39.png)

## 实现简易HTTP服务器 🌐

最后，我们实现一个简易的HTTP服务器。当收到HTTP GET请求时，我们返回一个简单的HTML页面。

以下是处理HTTP请求并响应的代码：

```c
if (strstr(request, "GET / HTTP")) {
    char response[] = "HTTP/1.1 200 OK\r\n"
                      "Content-Type: text/html\r\n"
                      "\r\n"
                      "<html><head><title>MyOS</title></head>"
                      "<body><h1>Hello from MyOS!</h1></body></html>";
    send_tcp_data(socket, response, strlen(response));
}
```

![](img/7dbc400bd678ed3d1daabde601b2f13b_41.png)

![](img/7dbc400bd678ed3d1daabde601b2f13b_42.png)

![](img/7dbc400bd678ed3d1daabde601b2f13b_44.png)

![](img/7dbc400bd678ed3d1daabde601b2f13b_46.png)

![](img/7dbc400bd678ed3d1daabde601b2f13b_48.png)

我们在内核中创建一个监听套接字，并在收到请求时发送上述响应。通过浏览器访问虚拟机的IP地址，我们成功收到了HTML页面。

![](img/7dbc400bd678ed3d1daabde601b2f13b_50.png)

![](img/7dbc400bd678ed3d1daabde601b2f13b_51.png)

---

![](img/7dbc400bd678ed3d1daabde601b2f13b_53.png)

![](img/7dbc400bd678ed3d1daabde601b2f13b_54.png)

## 总结

本节课中我们一起学习了：

1.  **调试TCP连接**：通过减少日志输出和分析标志位，定位并修正了连接建立问题。
2.  **修正长度计算错误**：解决了因IP消息长度计算错误导致的序列号不同步问题。
3.  **实现TCP重置**：添加了发送RST标志来异常终止连接的功能。
4.  **构建简易HTTP服务器**：实现了一个能够响应HTTP GET请求并返回HTML页面的基本服务器。

![](img/7dbc400bd678ed3d1daabde601b2f13b_56.png)

我们的操作系统现在能够通过TCP/IP协议栈与外部世界（如Web浏览器）进行通信，这是一个重要的进步。虽然实现中仍有一些边界情况未处理，但核心功能已可运行。

下一节课，我们将开始探索文件系统，具体是FAT32格式。敬请关注！

---