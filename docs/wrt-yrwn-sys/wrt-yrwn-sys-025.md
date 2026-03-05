# 025：互联网控制消息协议 (ICMP) 🛰️

在本节课中，我们将学习如何为互联网控制消息协议（ICMP）实现一个处理器。ICMP是一个相对简单的网络协议，主要用于诊断和错误报告，例如我们熟悉的`ping`命令。我们将基于之前实现的IPv4处理器来构建它。

上一节我们介绍了IPv4协议及其处理器。它负责查看数据包中的协议字段，并将数据传递给相应的上层协议处理器。到目前为止，我们还没有为这些上层协议编写任何处理器，但今天我们将改变这一点。

## ICMP协议简介

ICMP协议结构简单。根据维基百科，一个ICMP消息至少包含8字节的头部。其核心字段包括：
*   **类型 (Type)**：一个8位整数，指示消息的类型（例如，请求或回复）。
*   **代码 (Code)**：一个8位整数，提供关于类型的更详细信息。
*   **校验和 (Checksum)**：一个16位整数，用于验证数据的完整性。
*   **数据 (Data)**：可变长度的附加信息，对于`ping`（回显请求）而言，通常包含一个标识符和序列号。

对于`ping`操作，当收到一个类型为8的ICMP回显请求时，我们只需将类型改为0（回显应答），重新计算校验和，然后将数据原样发回即可。

## 实现ICMP处理器

以下是实现ICMP处理器的核心步骤。我们将创建一个继承自`InternetProtocolHandler`的类。

### 1. 定义ICMP消息结构

首先，我们需要一个结构体来表示ICMP头部。

```cpp
struct ICMPHeader {
    uint8_t type;
    uint8_t code;
    uint16_t checksum;
    uint32_t data; // 对于ping请求/应答，通常包含标识符和序列号
} __attribute__((packed));
```

### 2. 创建ICMP处理器类

我们的`ICMPHandler`类将继承自`InternetProtocolHandler`，并处理协议号1（ICMP）。

![](img/5b44c4cd9610b3cffa6b16d014fa720f_1.png)

![](img/5b44c4cd9610b3cffa6b16d014fa720f_3.png)

```cpp
class ICMPHandler : public InternetProtocolHandler {
public:
    ICMPHandler(InternetProtocolProvider* backend);
    ~ICMPHandler();

    // 重写基类的数据接收处理方法
    virtual bool OnInternetProtocolReceived(uint32_t srcIP_BE, uint32_t dstIP_BE, uint8_t* internetprotocolPayload, uint32_t size);

    // 发送一个ping请求
    void RequestEchoReply(uint32_t ip_be);
};
```

### 3. 实现构造函数

构造函数非常简单，只需调用基类构造函数并指定ICMP的协议号（1）。

```cpp
ICMPHandler::ICMPHandler(InternetProtocolProvider* backend)
: InternetProtocolHandler(backend, 0x01) // ICMP的协议号是1
{
}
```

### 4. 实现发送Ping请求

要发送一个ping请求，我们需要构建一个ICMP消息。

![](img/5b44c4cd9610b3cffa6b16d014fa720f_5.png)

![](img/5b44c4cd9610b3cffa6b16d014fa720f_6.png)

```cpp
void ICMPHandler::RequestEchoReply(uint32_t ip_be) {
    ICMPHeader icmp;
    icmp.type = 8; // ICMP Echo Request
    icmp.code = 0;
    icmp.data = 0x1337; // 可以设置为任意值，此处是一个示例标识
    icmp.checksum = 0;
    // 计算校验和（可以使用IPv4中的相同方法）
    icmp.checksum = InternetProtocolProvider::Checksum((uint16_t*)&icmp, sizeof(ICMPHeader));

    // 通过基类方法发送消息
    Send(ip_be, (uint8_t*)&icmp, sizeof(ICMPHeader));
}
```

### 5. 处理接收到的ICMP数据

![](img/5b44c4cd9610b3cffa6b16d014fa720f_8.png)

这是处理器的核心。当收到数据时，我们判断其类型并作出响应。

![](img/5b44c4cd9610b3cffa6b16d014fa720f_10.png)

```cpp
bool ICMPHandler::OnInternetProtocolReceived(uint32_t srcIP_BE, uint32_t dstIP_BE, uint8_t* payload, uint32_t size) {
    if(size < sizeof(ICMPHeader))
        return false; // 数据太小，不是有效的ICMP消息

    ICMPHeader* msg = (ICMPHeader*)payload;

    switch(msg->type) {
        case 0: // ICMP Echo Reply
            // 这是我们发出的ping请求的回复
            // 可以在这里处理回复，例如打印信息
            break;
        case 8: // ICMP Echo Request
            // 收到其他主机发来的ping请求，需要回复
            msg->type = 0; // 改为回复类型
            msg->checksum = 0; // 重置校验和以便重新计算
            // 重新计算整个ICMP消息的校验和
            msg->checksum = InternetProtocolProvider::Checksum((uint16_t*)msg, sizeof(ICMPHeader));
            // 返回true，表示需要将此回复数据发送出去
            return true;
    }
    return false; // 不处理其他类型的消息
}
```

![](img/5b44c4cd9610b3cffa6b16d014fa720f_12.png)

## 处理ARP缓存问题

![](img/5b44c4cd9610b3cffa6b16d014fa720f_14.png)

在测试时，你可能会发现网关（或目标机器）因为不知道我们的MAC地址而无法直接回复ICMP应答。它会先发送一个ARP请求来查询我们的地址。

![](img/5b44c4cd9610b3cffa6b16d014fa720f_16.png)

为了解决这个问题，我们可以在`ARPHandler`中添加一个方法，主动向目标发送我们的MAC和IP地址信息（类似于一个未经请求的ARP应答），这样目标机器的ARP缓存中就有了我们的记录。

```cpp
void ARPHandler::RequestMACAddress(uint32_t IP_BE) {
    // ... 先发送正常的ARP请求 ...
    // 收到ARP回复后，可以再主动发送一次包含自身信息的ARP消息
    ARPMessage arp;
    arp.hardwareType = 0x0100; // 以太网
    arp.protocol = 0x0008;     // IPv4
    // ... 设置操作码为应答，填充自身MAC和IP ...
    // 发送这个ARP消息
}
```

在发送ping之前，先调用此方法告知网关我们的地址，可以确保ping流程更顺畅。

![](img/5b44c4cd9610b3cffa6b16d014fa720f_18.png)

## 测试与验证

完成代码后，进行测试。你应该能看到以下流程：
1.  发送ARP请求以获取网关MAC地址。
2.  收到ARP回复。
3.  （可选）主动发送自身信息给网关。
4.  发送ICMP Echo Request (ping)。
5.  收到ICMP Echo Reply。

![](img/5b44c4cd9610b3cffa6b16d014fa720f_20.png)

在输出日志中，注意观察ICMP消息的类型字段从`8`（请求）变为`0`（应答），并且校验和正确更新。

## 总结

![](img/5b44c4cd9610b3cffa6b16d014fa720f_22.png)

本节课中我们一起学习了ICMP协议的基本原理，并成功实现了一个ICMP协议处理器。我们完成了以下工作：
*   理解了ICMP报文的结构，特别是用于`ping`命令的回显请求与回显应答。
*   创建了`ICMPHandler`类，继承自我们之前构建的网络协议处理框架。
*   实现了发送ping请求和处理ping请求/应答的逻辑。
*   解决了实际网络中可能遇到的ARP缓存问题，使ping测试得以成功。

![](img/5b44c4cd9610b3cffa6b16d014fa720f_24.png)

这个实现相对简单，但它为操作系统添加了重要的网络诊断能力。下一节课，我们可能会探讨更复杂的传输层协议，如UDP，或者转向文件系统相关的主题。