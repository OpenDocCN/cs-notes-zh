# 022：以太网帧处理 🖧

## 概述
在本节中，我们将学习如何为操作系统中的网络设备驱动添加以太网帧处理功能。我们将创建一个框架，用于接收原始网络数据，并根据其类型（如ARP或IPv4）将其分发给相应的协议处理器。

---

## 以太网帧结构
上一节我们介绍了网络设备驱动的基础。本节中，我们来看看如何处理驱动接收到的原始数据。这些数据遵循以太网帧格式。

一个以太网帧包含以下部分：
*   **目标MAC地址**：6字节，指定数据包的目的地。如果地址是 `0xFFFFFFFFFFFF`，则表示这是一个广播包，发送给网络中的所有设备。
*   **源MAC地址**：6字节，标识数据包的发送者。
*   **以太类型**：2字节，用于标识帧内承载的上层协议类型（如ARP或IPv4）。这些值采用大端字节序存储。
*   **数据载荷**：帧的实际内容。
*   **帧校验序列**：4字节，用于错误检测。

![](img/27ed800ab109012f21807e8cfaaadd9a_1.png)

我们的驱动已经可以发送和接收这种原始数据。现在的目标是附加一个处理器来检查这些数据，并决定将其传递给哪个上层协议。

---

![](img/27ed800ab109012f21807e8cfaaadd9a_3.png)

## 设计处理器框架
我们将采用一种面向对象的方式来实现这个处理器框架，使用控制反转模式，这在面向对象编程中很常见。

![](img/27ed800ab109012f21807e8cfaaadd9a_5.png)

![](img/27ed800ab109012f21807e8cfaaadd9a_7.png)

![](img/27ed800ab109012f21807e8cfaaadd9a_8.png)

我们将创建一个处理器数组。每个处理器可以将自己注册到这个数组中。当收到数据时，我们会遍历这个数组，找到能处理该以太类型的处理器。

![](img/27ed800ab109012f21807e8cfaaadd9a_10.png)

以下是核心类的设计思路：

![](img/27ed800ab109012f21807e8cfaaadd9a_11.png)

1.  **`EthernetFrameHandler`（以太网帧处理器基类）**：所有具体协议处理器（如ARP、IPv4）都将继承自这个类。它包含一个处理接收帧的虚方法。
    ```cpp
    class EthernetFrameHandler {
    public:
        EthernetFrameHandler(EthernetFrameProvider* backend, uint16_t etherType);
        ~EthernetFrameHandler();
        virtual bool OnEthernetFrameReceived(uint8_t* payload, uint32_t size);
        void Send(uint8_t* destMac, uint32_t size);
    };
    ```

![](img/27ed800ab109012f21807e8cfaaadd9a_13.png)

![](img/27ed800ab109012f21807e8cfaaadd9a_15.png)

2.  **`EthernetFrameProvider`（以太网帧提供者）**：作为网络设备驱动的后端接口。它管理一个`EthernetFrameHandler`指针数组，并负责将接收到的帧分发给正确的处理器。它还需要提供发送数据的能力。
    ```cpp
    class EthernetFrameProvider {
    public:
        EthernetFrameProvider();
        ~EthernetFrameProvider();
        bool HandleFrame(uint8_t* buffer, uint32_t size);
        void SendFrame(uint8_t* destMac, uint16_t etherType, uint8_t* buffer, uint32_t size);
        uint64_t GetMACAddress();
    };
    ```

---

## 实现帧处理流程
以下是处理接收到的数据帧的主要步骤：

1.  **解析帧头**：将接收到的数据缓冲区映射到一个帧头结构体上，以便访问目标地址、源地址和以太类型字段。
    ```cpp
    struct EthernetFrameHeader {
        uint8_t dstMAC[6];
        uint8_t srcMAC[6];
        uint16_t etherType;
    } __attribute__((packed));
    ```

2.  **检查目标地址**：判断该帧是否是发送给本机的（匹配本机MAC地址）或是一个广播帧。如果不是，则忽略。

![](img/27ed800ab109012f21807e8cfaaadd9a_17.png)

3.  **查找处理器**：根据帧头中的`etherType`字段，在已注册的处理器数组中查找对应的处理器。

![](img/27ed800ab109012f21807e8cfaaadd9a_19.png)

4.  **分发数据**：如果找到匹配的处理器，则将帧的**数据载荷部分**（即去除帧头后的数据）传递给该处理器的`OnEthernetFrameReceived`方法。

5.  **处理回复**：如果处理器方法返回`true`，表示需要发送回复。此时，我们需要：
    *   交换帧头中的源MAC地址和目标MAC地址（将原发送者设为目标，将本机MAC设为源）。
    *   将修改后的整个帧（包含新的帧头和处理后/新的载荷）交还给网络驱动发送出去。

---

## 实现数据发送
处理器也可能需要主动发送数据。`EthernetFrameHandler`的`Send`方法将利用其后端提供者`EthernetFrameProvider`来发送帧。

![](img/27ed800ab109012f21807e8cfaaadd9a_21.png)

![](img/27ed800ab109012f21807e8cfaaadd9a_23.png)

发送数据时，需要：
1.  分配内存，大小为 `以太网帧头大小 + 数据载荷大小`。
2.  填充帧头：设置目标MAC、源MAC（本机地址）和以太类型。注意字节序转换。
3.  拷贝数据载荷到帧头之后的内存中。
4.  调用后端提供者的发送函数，将完整的帧传递给网络设备驱动。

![](img/27ed800ab109012f21807e8cfaaadd9a_25.png)

![](img/27ed800ab109012f21807e8cfaaadd9a_27.png)

---

![](img/27ed800ab109012f21807e8cfaaadd9a_29.png)

## 总结
本节课中我们一起学习了如何为操作系统的网络子系统构建一个基础的以太网帧处理框架。我们定义了`EthernetFrameHandler`和`EthernetFrameProvider`两个核心类，实现了接收帧的解析、处理器分发以及回复发送的流程。这个框架为后续实现ARP、IPv4等具体网络协议处理器奠定了基础。下一节，我们将利用这个框架来实现地址解析协议。