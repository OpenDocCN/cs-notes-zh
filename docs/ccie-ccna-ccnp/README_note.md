# CCIE/CCNA/CCNP 笔记：1：OSPF 基础与配置

在本节课中，我们将要学习开放最短路径优先协议的基础概念、工作原理以及基本配置方法。OSPF是一种广泛使用的内部网关协议，用于在单一自治系统内决策路由。

## OSPF 基本概念

上一节我们介绍了本课程的目标，本节中我们来看看OSPF的核心定义与特点。OSPF全称为开放最短路径优先，它是一种链路状态路由协议。路由器通过交换链路状态通告来了解整个网络的拓扑结构。每台OSPF路由器都会使用SPF算法，以自己为根计算到达所有目的网络的最短路径树。

其核心算法**迪杰斯特拉算法**的公式可表示为：
**`最短路径成本 = 累计链路成本`**
其中，链路成本通常基于带宽计算，例如 `Cost = Reference Bandwidth / Interface Bandwidth`。

## OSPF 工作原理

了解了基本概念后，我们深入探讨OSPF的工作机制。OSPF路由器通过与邻居建立邻接关系来同步链路状态数据库。这个过程涉及几个关键状态和报文交换。

以下是OSPF建立邻接关系的几个主要步骤：

*   **Down状态**：初始状态，未收到任何Hello报文。
*   **Init状态**：收到邻居的Hello报文，但邻居列表中未包含自己的Router ID。
*   **2-Way状态**：双方在Hello报文中都看到了对方的Router ID，邻居关系建立。在广播网络中，此时会选举DR和BDR。
*   **ExStart状态**：开始主从关系选举，准备交换LSA摘要。
*   **Exchange状态**：相互交换数据库描述包，即LSA的摘要信息。
*   **Loading状态**：根据摘要，请求并接收完整的LSA信息。
*   **Full状态**：邻接关系完全建立，双方的链路状态数据库同步。

## OSPF 基础配置

掌握了工作原理，现在我们可以开始进行实际配置。在Cisco设备上启用OSPF涉及几个基本命令。

以下是在路由器上配置OSPF的基本流程：

1.  进入全局配置模式：`Router# configure terminal`
2.  启用OSPF进程并进入路由器配置模式：`Router(config)# router ospf <进程ID>`
    *   进程ID仅在本地有效，用于区分同一设备上的多个OSPF进程。
3.  宣告直连网络并指定区域：`Router(config-router)# network <网络地址> <反掩码> area <区域号>`
    *   例如，将接口192.168.1.0/24宣告进区域0：`network 192.168.1.0 0.0.0.255 area 0`

一个简单的配置示例如下：
```cisco
interface GigabitEthernet0/0
 ip address 10.1.1.1 255.255.255.0
!
router ospf 1
 network 10.1.1.0 0.0.0.255 area 0
```

## 验证与排错

配置完成后，必须验证OSPF是否按预期运行。Cisco IOS提供了丰富的查看命令。

以下是常用的OSPF验证命令列表：

*   查看OSPF邻居状态：`show ip ospf neighbor`
*   查看OSPF接口信息及成本：`show ip ospf interface brief`
*   查看路由器的OSPF路由表：`show ip route ospf`
*   查看OSPF的链路状态数据库：`show ip ospf database`

如果邻居无法达到Full状态，可以检查以下常见问题：接口是否启用、网络宣告是否正确、Hello/Dead计时器是否匹配、区域ID是否一致以及认证配置是否相同。

本节课中我们一起学习了OSPF的基础知识。我们明确了OSPF作为一种链路状态协议的特性，理解了其通过建立邻接关系、同步数据库并计算最短路径树的工作流程。同时，我们掌握了在Cisco路由器上进行OSPF基本配置、宣告网络以及使用关键命令进行验证和基础排错的方法。这些是理解和部署OSPF网络的基石。