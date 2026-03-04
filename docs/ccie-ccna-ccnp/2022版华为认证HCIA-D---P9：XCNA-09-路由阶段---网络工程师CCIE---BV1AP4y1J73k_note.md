# 华为认证HCIA-DATACOM教程：P9：XCNA-09-路由阶段性实验

## 概述
在本节课中，我们将进行一个路由综合实验。我们将使用四台路由器，模拟一个包含不同路由协议的网络环境，并最终实现跨协议网络的端到端通信。通过这个实验，我们将巩固静态路由、RIP和OSPF协议的基本配置，并理解不同网络区域间通信的原理。

## 路由协议阶段性回顾
在开始实验之前，我们先简要回顾一下NA阶段学习的路由协议要点。

对于OSPF协议，在NA阶段，你需要知道它的五种报文类型，以及它通过Hello报文和SLA（链路状态通告）来发现和建立邻居关系。至于详细的LSA类型（1到7类）和原理，将在NP阶段深入学习。

对于实验要求，从接触模拟器开始，你需要掌握：修改设备系统名、配置接口IP地址、配置静态路由，以及配置RIP和OSPF这类动态路由协议。

学完路由部分后，网络工程师还需要学习二层技术。在NA阶段，二层技术主要了解VLAN的作用、划分方法以及不同VLAN间如何通信，此外还包括交换机的工作模式。这些内容将在后续课程中学习。

## 实验拓扑与目标
本次实验的拓扑结构如下：我们拥有四台路由器（R1, R2, R3, R4）和两台PC（PC5, PC6）。

*   **R1与R2之间**：运行OSPF协议。
*   **R3与R4之间**：运行EIGRP协议（思科模拟器部分）或OSPF协议（华为模拟器部分）。
*   **R2与R3之间**：不运行任何动态路由协议，依靠静态路由或默认路由进行通信。

**实验目标**：实现PC5（192.168.10.0/24网段）与PC6（192.168.20.0/24网段）之间的相互通信。

## 思科设备配置演示
首先，我们在思科模拟器上完成此实验。

![](img/700693dcb848678642156f566b697922_1.png)

### 第一步：基础IP地址配置
我们需要为所有路由器的接口和环回口配置IP地址，并为PC配置IP地址及网关。

**地址规划原则**：
*   直连链路地址：例如R1-R2使用192.168.12.0/24，R2-R3使用192.168.23.0/24，R3-R4使用192.168.34.0/24。
*   环回口地址：R1为1.1.1.1/32，R2为2.2.2.2/32，R3为3.3.3.3/32，R4为4.4.4.4/32。
*   PC网关地址：PC5的网关（R1的G0/1接口）为192.168.10.254/24；PC6的网关（R4的G0/1接口）为192.168.20.254/24。

**配置示例（R1）**：
```bash
Router> enable
Router# configure terminal
Router(config)# hostname R1
R1(config)# interface loopback 0
R1(config-if)# ip address 1.1.1.1 255.255.255.255
R1(config-if)# interface gigabitEthernet 0/0
R1(config-if)# ip address 192.168.12.1 255.255.255.0
R1(config-if)# no shutdown
R1(config-if)# interface gigabitEthernet 0/1
R1(config-if)# ip address 192.168.10.254 255.255.255.0
R1(config-if)# no shutdown
```
使用 `show ip interface brief` 命令可以查看接口状态与IP地址信息。

**关于环回口（Loopback）**：
环回口是一个虚拟接口，主要作用有两个：标识路由器本身和模拟路由器身后的网络。它的掩码可以不是32位，但配置为32位时，在路由表中代表一个精确的主机路由。在后续学习BGP等协议时，环回口将发挥重要作用。

### 第二步：配置动态路由协议
在R1和R2上配置OSPF协议。

**OSPF配置要点**：
1.  **进程号**：本地有效，邻居间可以不同。
2.  **Router ID**：最好手动指定，通常使用环回口地址。选举顺序为：优先选择最大的环回口地址；若无环回口，则选择最大的物理接口IP地址。
3.  **宣告网络**：可以使用 `network` 命令加反掩码进行宣告。反掩码中，0表示精确匹配，1表示任意。

**配置示例（R1）**：
```bash
R1(config)# router ospf 1
R1(config-router)# router-id 1.1.1.1
R1(config-router)# network 1.1.1.1 0.0.0.0 area 0
R1(config-router)# network 192.168.12.0 0.0.0.255 area 0
```
配置完成后，可以使用 `show ip ospf neighbor` 查看邻居状态，`show ip route ospf` 查看OSPF学习到的路由。

![](img/700693dcb848678642156f566b697922_3.png)

在R3和R4上配置EIGRP协议（思科私有）。

![](img/700693dcb848678642156f566b697922_5.png)

**EIGRP配置要点**：
1.  **进程号**：必须与邻居路由器一致。
2.  **关闭自动汇总**：使用 `no auto-summary` 命令。
3.  **宣告网络**：同样使用 `network` 命令加反掩码。

![](img/700693dcb848678642156f566b697922_7.png)

**配置示例（R3）**：
```bash
R3(config)# router eigrp 90
R3(config-router)# no auto-summary
R3(config-router)# eigrp router-id 3.3.3.3
R3(config-router)# network 3.3.3.3 0.0.0.0
R3(config-router)# network 192.168.34.0 0.0.0.255
```
配置完成后，使用 `show ip eigrp neighbors` 和 `show ip route eigrp` 进行验证。

### 第三步：配置静态路由/默认路由实现互通
此时，PC5无法ping通PC6。因为R1没有去往192.168.20.0/24网段的路由，R2没有去往3.3.3.3或192.168.20.0/24的路由。

![](img/700693dcb848678642156f566b697922_9.png)

**解决方案**：在未运行动态协议的链路上，通过配置静态默认路由，引导数据包传递。

1.  在R1上配置默认路由，指向R2。
    ```bash
    R1(config)# ip route 0.0.0.0 0.0.0.0 192.168.12.2
    ```
2.  在R2上配置默认路由，指向R3。
    ```bash
    R2(config)# ip route 0.0.0.0 0.0.0.0 192.168.23.3
    ```
3.  在R3上配置默认路由，指向R2（用于回包）。
    ```bash
    R3(config)# ip route 0.0.0.0 0.0.0.0 192.168.23.2
    ```
4.  在R4上配置默认路由，指向R3。
    ```bash
    R4(config)# ip route 0.0.0.0 0.0.0.0 192.168.34.3
    ```

**通信过程分析（以PC5 ping PC6为例）**：
1.  PC5发送数据包，目的IP为PC6，查询本地路由，发现非本地网段，将数据包发往网关R1。
2.  R1查询路由表，没有精确匹配PC6的路由，但有一条默认路由，将数据包转发给R2。
3.  R2同样通过默认路由转发给R3。
4.  R3查询路由表，通过EIGRP协议学到了192.168.20.0/24的路由，将数据包转发给R4。
5.  R4将数据包送达PC6。
6.  PC6回复数据包，目的IP为PC5。R4通过默认路由发给R3。
7.  R3通过默认路由发给R2。
8.  R2查询路由表，通过OSPF协议学到了192.168.10.0/24的路由，将数据包转发给R1。
9.  R1将数据包送达PC5。

至此，端到端通信建立。在整个过程中，三层IP地址（源IP和目的IP）始终保持不变，而二层MAC地址在每一跳都会改变。

### 第四步：高级技巧——默认路由下放
手动配置多台设备的默认路由比较繁琐。在实际网络中，可以使用“默认路由下放”技术。例如，在OSPF中，可以在边界路由器（R3）上配置：
```bash
R3(config)# router ospf 1
R3(config-router)# default-information originate
```
这条命令会将R3上的默认路由以OSPF外部路由（O*E2）的形式发布给OSPF区域内的其他路由器（如R4），实现自动学习，无需每台设备手动配置。此技术细节将在NP课程中详解。

## 华为设备配置演示
接下来，我们在华为模拟器上完成一个类似的实验，将EIGRP替换为RIP和OSPF。

![](img/700693dcb848678642156f566b697922_11.png)

![](img/700693dcb848678642156f566b697922_13.png)

![](img/700693dcb848678642156f566b697922_15.png)

![](img/700693dcb848678642156f566b697922_17.png)

![](img/700693dcb848678642156f566b697922_19.png)

### 第一步：基础IP地址配置
华为设备接口默认开启。配置命令与思科类似，但掩码可以简写（如`24`代表255.255.255.0）。

![](img/700693dcb848678642156f566b697922_21.png)

![](img/700693dcb848678642156f566b697922_23.png)

![](img/700693dcb848678642156f566b697922_25.png)

**配置示例（R1）**：
```bash
<Huawei> system-view
[Huawei] sysname R1
[R1] interface LoopBack 0
[R1-LoopBack0] ip address 1.1.1.1 32
[R1-LoopBack0] interface GigabitEthernet 0/0/0
[R1-GigabitEthernet0/0/0] ip address 192.168.12.1 24
[R1-GigabitEthernet0/0/0] interface GigabitEthernet 0/0/1
[R1-GigabitEthernet0/0/1] ip address 192.168.10.254 24
```
使用 `display ip interface brief` 查看接口信息。

![](img/700693dcb848678642156f566b697922_27.png)

![](img/700693dcb848678642156f566b697922_29.png)

![](img/700693dcb848678642156f566b697922_31.png)

### 第二步：配置动态路由协议
在R1和R2上配置RIP协议。

![](img/700693dcb848678642156f566b697922_33.png)

![](img/700693dcb848678642156f566b697922_35.png)

![](img/700693dcb848678642156f566b697922_37.png)

![](img/700693dcb848678642156f566b697922_39.png)

![](img/700693dcb848678642156f566b697922_41.png)

**RIP配置要点**：需要关闭自动汇总，并且宣告的是主类网络。

![](img/700693dcb848678642156f566b697922_43.png)

![](img/700693dcb848678642156f566b697922_45.png)

**配置示例（R1）**：
```bash
[R1] rip 1
[R1-rip-1] version 2
[R1-rip-1] undo summary
[R1-rip-1] network 192.168.10.0
[R1-rip-1] network 192.168.12.0
[R1-rip-1] network 1.0.0.0
```
使用 `display rip 1 neighbor` 和 `display ip routing-table protocol rip` 查看信息。

![](img/700693dcb848678642156f566b697922_47.png)

在R3和R4上配置OSPF协议。

![](img/700693dcb848678642156f566b697922_49.png)

![](img/700693dcb848678642156f566b697922_50.png)

**配置示例（R3）**：
```bash
[R3] ospf 1 router-id 3.3.3.3
[R3-ospf-1] area 0
[R3-ospf-1-area-0.0.0.0] network 3.3.3.3 0.0.0.0
[R3-ospf-1-area-0.0.0.0] network 192.168.34.0 0.0.0.255
```
使用 `display ospf peer brief` 和 `display ip routing-table protocol ospf` 查看信息。

![](img/700693dcb848678642156f566b697922_52.png)

![](img/700693dcb848678642156f566b697922_54.png)

![](img/700693dcb848678642156f566b697922_56.png)

![](img/700693dcb848678642156f566b697922_58.png)

### 第三步：配置静态默认路由及下放
为实现通信，仍需配置默认路由。华为配置命令如下：
```bash
[R1] ip route-static 0.0.0.0 0.0.0.0 192.168.12.2
[R2] ip route-static 0.0.0.0 0.0.0.0 192.168.23.3
[R3] ip route-static 0.0.0.0 0.0.0.0 192.168.23.2
```
在华为OSPF中，同样可以下放默认路由，在R3的OSPF进程下配置：
```bash
[R3-ospf-1] default-route-advertise
```
配置后，R4会自动学习到一条下一跳为R3的默认路由（通过OSPF）。

![](img/700693dcb848678642156f566b697922_60.png)

![](img/700693dcb848678642156f566b697922_62.png)

![](img/700693dcb848678642156f566b697922_64.png)

![](img/700693dcb848678642156f566b697922_66.png)

![](img/700693dcb848678642156f566b697922_68.png)

## 关键命令总结
以下是本实验涉及的核心查看命令对比：

![](img/700693dcb848678642156f566b697922_70.png)

![](img/700693dcb848678642156f566b697922_72.png)

| 功能 | 思科命令 | 华为命令 |
| :--- | :--- | :--- |
| 查看接口IP | `show ip interface brief` | `display ip interface brief` |
| 查看路由表 | `show ip route` | `display ip routing-table` |
| 查看OSPF邻居 | `show ip ospf neighbor` | `display ospf peer brief` |
| 查看OSPF路由 | `show ip route ospf` | `display ip routing-table protocol ospf` |
| 查看OSPF数据库 | `show ip ospf database` | `display ospf lsdb` |
| 查看RIP路由 | `show ip route rip` | `display ip routing-table protocol rip` |
| 查看EIGRP邻居 | `show ip eigrp neighbors` | N/A |
| 查看EIGRP路由 | `show ip route eigrp` | N/A |

![](img/700693dcb848678642156f566b697922_74.png)

## 总结
本节课我们一起完成了一个综合性的路由实验。我们回顾并实践了静态路由、RIP和OSPF协议的配置，重点解决了在不同路由协议区域之间通过静态默认路由实现通信的问题。我们还探讨了数据包端到端转发过程中IP地址和MAC地址的变化规律，并简要介绍了“默认路由下放”这一高级特性。理解这些原理和配置，是构建和维护复杂网络的基础。下一阶段，我们将进入二层交换技术的学习。