# 028：传输控制协议 (TCP) - 发送数据

## 概述

在本节课中，我们将继续实现传输控制协议（TCP）。上一节我们开始了TCP的实现，本节我们将重点实现通过TCP连接发送数据的功能。这个过程涉及构建TCP数据包、计算校验和以及处理连接状态。

![](img/adaaf5650105b681046c845f2ba80836_1.png)

## 计算TCP校验和

上一节我们介绍了TCP的基本结构，本节中我们来看看如何为TCP数据包计算校验和。TCP校验和的计算方式与IPv4校验和类似，但输入的数据不同。我们需要将TCP头部、要发送的数据以及一个“TCP伪头部”一起作为输入。

TCP伪头部包含以下信息（均为大端字节序）：
*   源IP地址（32位）
*   目标IP地址（32位）
*   协议号（固定为6，代表TCP，以16位存储）
*   TCP报文段总长度（16位）

**公式**：`TCP校验和 = IPv4校验和算法( TCP伪头部 + TCP头部 + 数据 )`

## 实现数据发送

现在，让我们进入发送数据的具体实现。`send`方法需要处理标志位、序列号并构建完整的数据包。

以下是构建和发送TCP数据包的关键步骤：

![](img/adaaf5650105b681046c845f2ba80836_3.png)

![](img/adaaf5650105b681046c845f2ba80836_5.png)

1.  **分配缓冲区**：分配足够容纳伪头部、TCP头部和用户数据的缓冲区。
2.  **设置伪头部**：在缓冲区起始处填充伪头部的各个字段。
3.  **设置TCP头部**：在伪头部之后填充TCP头部字段，包括源端口、目标端口、序列号、确认号、数据偏移、标志位、窗口大小等。
4.  **设置选项**：如果数据包包含SYN（同步）标志，需要设置特定的选项字段（例如MSS）。
5.  **复制数据**：将用户要发送的数据复制到TCP头部之后的缓冲区位置。
6.  **计算校验和**：对整个缓冲区（伪头部+头部+数据）调用IPv4校验和算法，并将结果填入头部的校验和字段。
7.  **发送数据**：将缓冲区中从TCP头部开始的部分（不包括伪头部）发送出去。

![](img/adaaf5650105b681046c845f2ba80836_7.png)

![](img/adaaf5650105b681046c845f2ba80836_9.png)

**代码**示例（概念性）：
```c
void send_tcp_packet(...) {
    // 1. 分配缓冲区
    buffer = allocate( PSEUDO_HEADER_SIZE + TCP_HEADER_SIZE + data_length );

    // 2. & 3. 设置伪头部和TCP头部
    write_pseudo_header(buffer, src_ip, dst_ip, TCP_PROTOCOL, total_length);
    write_tcp_header(buffer + PSEUDO_HEADER_SIZE, src_port, dst_port, seq, ack, flags, ...);

    // 4. 处理选项（如SYN）
    if (flags & SYN) {
        set_tcp_options(...);
    }

    // 5. 复制数据
    copy_data(buffer + PSEUDO_HEADER_SIZE + TCP_HEADER_SIZE, user_data, data_length);

    // 6. 计算校验和
    checksum = calculate_ipv4_checksum(buffer, total_length + PSEUDO_HEADER_SIZE);
    write_checksum_to_header(buffer + PSEUDO_HEADER_SIZE, checksum);

    // 7. 发送（从TCP头部开始）
    network_send(buffer + PSEUDO_HEADER_SIZE, total_length);
}
```

![](img/adaaf5650105b681046c845f2ba80836_11.png)

## 连接测试与问题排查

![](img/adaaf5650105b681046c845f2ba80836_13.png)

![](img/adaaf5650105b681046c845f2ba80836_15.png)

实现发送功能后，我们尝试发起一个TCP连接（发送SYN包）。测试显示，系统成功发送了SYN包，并且收到了来自目标服务器（如Netcat服务器）的SYN-ACK响应。

![](img/adaaf5650105b681046c845f2ba80836_17.png)

然而，连接并未成功建立，因为我们还没有实现处理接收到的SYN-ACK包并回复ACK确认的逻辑。这导致了服务器端超时重传SYN-ACK。这验证了我们的发送功能是有效的，但完整的TCP握手流程尚未完成。

## 总结

本节课中我们一起学习了如何实现TCP协议的数据发送功能。我们详细讲解了TCP校验和的计算方法，它需要伪头部、TCP头部和数据的共同参与。接着，我们逐步实现了构建和发送TCP数据包的过程。目前，我们已经能够发送数据、发起连接（SYN）以及处理监听和断开等基本操作。下一节，我们将实现TCP的数据接收和处理逻辑，最终完成一个能够与外界通信的、可工作的TCP协议栈。