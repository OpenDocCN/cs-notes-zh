# CCNA教程合集：P10：CCNA10 - 网络设备配置与地址管理

## 概述
在本节课中，我们将学习网络设备的基础配置方法，包括路由器的硬件组成、操作系统模式、接口IP地址的配置，以及IP地址的两种分配方式：手工配置与动态分配（DHCP）。我们将从实际操作出发，帮助初学者掌握网络工程师必备的入门技能。

---

## IPv4与IPv6的演进思考
上一节我们介绍了IPv4与IPv6的基础知识。本节中，我们来探讨从IPv4迁移到IPv6可能带来的影响，特别是对运营商业务模式的潜在改变。

![](img/ebc00da1dde994d1c0390fac95b9f363_1.png)

![](img/ebc00da1dde994d1c0390fac95b9f363_2.png)

![](img/ebc00da1dde994d1c0390fac95b9f363_4.png)

![](img/ebc00da1dde994d1c0390fac95b9f363_5.png)

IPv4地址只有32位，地址空间不足，因此企业内网普遍使用私有地址，并通过运营商的专线或VPN服务实现互联。这构成了运营商的重要收入来源。

IPv6拥有充足的地址空间，理论上可以实现端到端的公有地址直接通信，这可能削弱运营商专线/VPN业务的价值。然而，运营商可以通过提高IPv6公有地址的售卖费用，或引导客户继续使用IPv6中的私有地址（唯一本地地址，`FC00::/7`）并配合NAT，来维持其商业模式。

![](img/ebc00da1dde994d1c0390fac95b9f363_7.png)

![](img/ebc00da1dde994d1c0390fac95b9f363_8.png)

![](img/ebc00da1dde994d1c0390fac95b9f363_9.png)

此外，IPv6原生集成了IPsec安全框架，能为所有通信提供加密保护，这增加了网络监听难度。从“棱镜门”等事件可以看出，数据安全与监听能力是各国政府在技术迁移时可能考虑的因素。但技术总是在博弈中发展，我们应积极学习并为IPv6的部署做好准备。

![](img/ebc00da1dde994d1c0390fac95b9f363_11.png)

![](img/ebc00da1dde994d1c0390fac95b9f363_12.png)

![](img/ebc00da1dde994d1c0390fac95b9f363_14.png)

---

![](img/ebc00da1dde994d1c0390fac95b9f363_16.png)

## 网络设备的IP地址配置
网络设备（如路由器、交换机）和终端主机（如PC）必须配置IP地址才能进行网络通信。配置方式主要分为两种：手工配置和自动配置。

### 手工配置IP地址
手工配置适用于需要固定地址的设备，如服务器、网络设备的管理接口等。其优点是地址稳定，便于管理和远程访问。

以下是手工配置的具体方法：

#### 1. 为Windows PC手工配置IP地址
*   打开“控制面板” > “网络和共享中心” > “更改适配器设置”。
*   右键点击使用的网卡，选择“属性”。
*   双击“Internet 协议版本 4 (TCP/IPv4)”。
*   选择“使用下面的IP地址”，依次填入IP地址、子网掩码、默认网关和DNS服务器地址。

#### 2. 为Cisco路由器手工配置IP地址
路由器没有图形界面，需要通过命令行接口(CLI)进行配置。首先，我们需要了解路由器的硬件和操作系统。

**路由器硬件组成**：
*   **CPU**：执行计算和处理指令。
*   **RAM**：随机存取存储器，存放运行时的数据，如**运行配置文件(`running-config`)**。断电后数据丢失。
*   **NVRAM**：非易失性RAM，存放**启动配置文件(`startup-config`)**。断电后数据不丢失。
*   **Flash**：闪存，存放操作系统镜像文件(`IOS`映像)。
*   **ROM**：只读存储器，存放开机自检程序和一个简化的操作系统（ROMMON模式），用于故障恢复。
*   **接口**：用于连接网络。

![](img/ebc00da1dde994d1c0390fac95b9f363_18.png)

![](img/ebc00da1dde994d1c0390fac95b9f363_20.png)

![](img/ebc00da1dde994d1c0390fac95b9f363_22.png)

![](img/ebc00da1dde994d1c0390fac95b9f363_24.png)

**Cisco IOS操作系统模式**：
用户通过控制台线或远程方式登录路由器后，会进入不同的操作模式，每种模式的权限不同。

![](img/ebc00da1dde994d1c0390fac95b9f363_26.png)

![](img/ebc00da1dde994d1c0390fac95b9f363_28.png)

*   **用户模式(`>`)**: 权限最低，主要用于查看基本信息。
    ```bash
    Router>
    ```
*   **特权模式(`#`)**: 拥有最高权限（15级），可以执行所有查看命令和进入配置模式。
    ```bash
    Router> enable
    Router#
    ```
*   **全局配置模式(`(config)#`)**: 在此模式下进行的配置影响整个设备。
    ```bash
    Router# configure terminal
    Router(config)#
    ```
*   **接口配置模式(`(config-if)#`)**: 在此模式下进行的配置只影响特定的接口。
    ```bash
    Router(config)# interface ethernet 0/0
    Router(config-if)#
    ```

![](img/ebc00da1dde994d1c0390fac95b9f363_30.png)

![](img/ebc00da1dde994d1c0390fac95b9f363_32.png)

![](img/ebc00da1dde994d1c0390fac95b9f363_34.png)

![](img/ebc00da1dde994d1c0390fac95b9f363_35.png)

![](img/ebc00da1dde994d1c0390fac95b9f363_37.png)

![](img/ebc00da1dde994d1c0390fac95b9f363_39.png)

**配置路由器接口IP地址步骤**：
假设要为路由器R1的Ethernet0/0接口配置IP地址`12.1.1.1/24`。

![](img/ebc00da1dde994d1c0390fac95b9f363_41.png)

![](img/ebc00da1dde994d1c0390fac95b9f363_43.png)

![](img/ebc00da1dde994d1c0390fac95b9f363_45.png)

![](img/ebc00da1dde994d1c0390fac95b9f363_46.png)

![](img/ebc00da1dde994d1c0390fac95b9f363_48.png)

![](img/ebc00da1dde994d1c0390fac95b9f363_50.png)

![](img/ebc00da1dde994d1c0390fac95b9f363_51.png)

![](img/ebc00da1dde994d1c0390fac95b9f363_53.png)

1.  从用户模式进入特权模式。
    ```bash
    Router> enable
    Router#
    ```
2.  进入全局配置模式。
    ```bash
    Router# configure terminal
    Router(config)#
    ```
3.  进入指定接口的配置模式。
    ```bash
    Router(config)# interface ethernet 0/0
    Router(config-if)#
    ```
4.  配置IP地址和子网掩码，并启用接口（默认关闭）。
    ```bash
    Router(config-if)# ip address 12.1.1.1 255.255.255.0
    Router(config-if)# no shutdown
    ```
5.  返回特权模式，查看接口状态。
    ```bash
    Router(config-if)# end
    Router# show ip interface brief
    ```

### 自动配置IP地址 (DHCP)
对于数量庞大、位置可能变动的终端设备（如员工PC），建议使用动态主机配置协议(DHCP)自动分配IP地址，以实现即插即用，减少管理负担。

**DHCP工作过程**（四步交互）：
1.  **Discover**: 客户端广播发送DHCP发现报文，寻找网络中的DHCP服务器。
2.  **Offer**: DHCP服务器收到Discover后，广播回应一个提供报文，包含可分配的IP地址等信息。
3.  **Request**: 客户端选择一个Offer，广播发送请求报文，正式向该服务器申请IP地址。
4.  **Ack**: 被选中的服务器广播发送确认报文，正式将IP地址租给客户端。

![](img/ebc00da1dde994d1c0390fac95b9f363_55.png)

**配置Cisco路由器作为DHCP服务器**：
以下示例将路由器R1配置为DHCP服务器，为`12.1.1.0/24`网段的主机分配地址。

![](img/ebc00da1dde994d1c0390fac95b9f363_57.png)

1.  在R1上启用DHCP服务。
    ```bash
    R1(config)# service dhcp
    ```
2.  创建DHCP地址池并进入其配置模式。
    ```bash
    R1(config)# ip dhcp pool CCNP-POOL
    R1(dhcp-config)#
    ```
3.  指定要分配的网段和默认网关。
    ```bash
    R1(dhcp-config)# network 12.1.1.0 255.255.255.0
    R1(dhcp-config)# default-router 12.1.1.1
    ```
4.  （可选）指定DNS服务器和域名。
    ```bash
    R1(dhcp-config)# dns-server 8.8.8.8
    R1(dhcp-config)# domain-name cisco.com
    ```
5.  排除不想被自动分配的地址（如已静态使用的地址）。
    ```bash
    R1(config)# ip dhcp excluded-address 12.1.1.1 12.1.1.10
    ```

![](img/ebc00da1dde994d1c0390fac95b9f363_59.png)

![](img/ebc00da1dde994d1c0390fac95b9f363_60.png)

**配置路由器接口作为DHCP客户端**：
将另一台路由器R2的接口配置为自动获取地址。
```bash
R2(config)# interface ethernet 0/0
R2(config-if)# ip address dhcp
R2(config-if)# no shutdown
```

---

![](img/ebc00da1dde994d1c0390fac95b9f363_62.png)

## 总结
本节课我们一起学习了网络设备配置的核心基础。我们首先探讨了IPv6演进对行业的影响，然后重点讲解了IP地址的两种分配方式。通过对比手工配置与DHCP自动配置的适用场景，我们了解到网络设备和关键服务器适合使用固定的手工配置，而普通用户终端则适合使用DHCP实现灵活管理。我们详细演示了在Cisco路由器上如何进行接口IP地址的手工配置，以及如何将一台路由器设置为DHCP服务器和客户端。掌握这些基础操作是成为一名网络工程师的重要第一步。