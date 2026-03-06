# ARM 汇编语言：II：10.3：编写 UART 驱动 🚀

![](img/cfadd29ee48ba00c2f0d82ea4505529b_0.png)

## 概述
在本节课程中，我们将学习如何为 ARM 微控制器编写一个 UART 驱动程序。我们将从初始化 UART 模块开始，逐步配置其时钟、引脚、波特率等关键参数，并最终实现一个可用的初始化子程序。

---

![](img/cfadd29ee48ba00c2f0d82ea4505529b_2.png)

![](img/cfadd29ee48ba00c2f0d82ea4505529b_4.png)

## 编写 UART 初始化子程序

![](img/cfadd29ee48ba00c2f0d82ea4505529b_6.png)

上一节我们介绍了 UART 的基本概念，本节中我们来看看如何用汇编语言实现其初始化过程。

![](img/cfadd29ee48ba00c2f0d82ea4505529b_8.png)

首先，我们定义代码段并设置入口点。

```assembly
    .area .text
    .code 16
    .align 2
    .thumb
    .global __main
__main:
    b uart_init
```

![](img/cfadd29ee48ba00c2f0d82ea4505529b_10.png)

![](img/cfadd29ee48ba00c2f0d82ea4505529b_12.png)

接下来，我们开始实现 `uart_init` 子程序。第一步是保存链接寄存器的值。

![](img/cfadd29ee48ba00c2f0d82ea4505529b_14.png)

![](img/cfadd29ee48ba00c2f0d82ea4505529b_16.png)

```assembly
uart_init:
    push {lr}
```

### 启用 UART 时钟
我们需要启用 UART 模块的时钟。这通过设置 `RCGCUART` 寄存器的相应位来完成。

![](img/cfadd29ee48ba00c2f0d82ea4505529b_18.png)

```assembly
    ldr r1, =SYSCTL_RCGCUART_R
    ldr r0, [r1]
    orr r0, r0, #UART0_EN
    str r0, [r1]
```

![](img/cfadd29ee48ba00c2f0d82ea4505529b_20.png)

对应的 C 语言操作是：
```c
SYSCTL_RCGCUART_R |= UART0_EN;
```

### 启用 GPIO 端口时钟
UART 引脚通常映射到特定的 GPIO 端口（例如 Port A）。我们需要启用该端口的时钟。

![](img/cfadd29ee48ba00c2f0d82ea4505529b_22.png)

![](img/cfadd29ee48ba00c2f0d82ea4505529b_23.png)

![](img/cfadd29ee48ba00c2f0d82ea4505529b_25.png)

```assembly
    ldr r1, =SYSCTL_RCGCGPIO_R
    ldr r0, [r1]
    orr r0, r0, #GPIO_PORTA_EN
    str r0, [r1]
```

![](img/cfadd29ee48ba00c2f0d82ea4505529b_27.png)

![](img/cfadd29ee48ba00c2f0d82ea4505529b_29.png)

对应的 C 语言操作是：
```c
SYSCTL_RCGCGPIO_R |= GPIO_PORTA_EN;
```

### 配置 UART 引脚
以下是配置 UART 引脚（PA0 和 PA1）为数字功能和备用功能的步骤。

首先，数字使能 PA0 和 PA1 引脚。

```assembly
    ldr r1, =GPIO_PORTA_DEN_R
    ldr r0, [r1]
    orr r0, r0, #0x03
    str r0, [r1]
```

![](img/cfadd29ee48ba00c2f0d82ea4505529b_31.png)

其次，设置引脚为备用功能（UART）。

![](img/cfadd29ee48ba00c2f0d82ea4505529b_33.png)

![](img/cfadd29ee48ba00c2f0d82ea4505529b_35.png)

```assembly
    ldr r1, =GPIO_PORTA_AFSEL_R
    ldr r0, [r1]
    orr r0, r0, #0x03
    str r0, [r1]
```

最后，在端口控制寄存器中，清除并设置 PA0 和 PA1 的引脚控制字段，将其配置为 UART 功能。

![](img/cfadd29ee48ba00c2f0d82ea4505529b_37.png)

![](img/cfadd29ee48ba00c2f0d82ea4505529b_38.png)

```assembly
    ldr r1, =GPIO_PORTA_PCTL_R
    ldr r0, [r1]
    bic r0, r0, #0xFF
    orr r0, r0, #(UART_PCTL_PA0 | UART_PCTL_PA1)
    str r0, [r1]
```

![](img/cfadd29ee48ba00c2f0d82ea4505529b_40.png)

### 配置 UART 模块
现在开始配置 UART 模块本身。首先，在配置前禁用它。

![](img/cfadd29ee48ba00c2f0d82ea4505529b_42.png)

```assembly
    ldr r1, =UART0_CTL_R
    ldr r0, [r1]
    bic r0, r0, #UART_CTL_UARTEN
    str r0, [r1]
```

### 设置波特率
波特率配置分为整数部分和小数部分，计算公式如下：
- **整数部分**：`BRD = SysClk / (16 * BaudRate)`
- **小数部分**：`FBRD = Integer((BRD - IBRD) * 64 + 0.5)`

假设系统时钟为 16 MHz，目标波特率为 115200，则计算如下：
- **整数部分**：`16,000,000 / (16 * 115200) ≈ 8.6805`，取整数 **8**。
- **小数部分**：`(0.6805 * 64 + 0.5) ≈ 44.052`，取整数 **44**。

将计算值写入对应的寄存器。

![](img/cfadd29ee48ba00c2f0d82ea4505529b_44.png)

```assembly
    ; 设置整数波特率
    ldr r1, =UART0_IBRD_R
    mov r0, #8
    str r0, [r1]

    ; 设置小数波特率
    ldr r1, =UART0_FBRD_R
    mov r0, #44
    str r0, [r1]
```

![](img/cfadd29ee48ba00c2f0d82ea4505529b_46.png)

### 设置数据帧格式
我们需要配置数据位长度、停止位和奇偶校验。这里我们配置为 8 位数据位，无奇偶校验，1 位停止位。

```assembly
    ldr r1, =UART0_LCRH_R
    ldr r0, [r1]
    bic r0, r0, #0xFF
    orr r0, r0, #(UART_LCRH_WLEN_8 | UART_LCRH_PEN_NONE)
    str r0, [r1]
```

### 启用 UART
所有配置完成后，重新启用 UART 模块。

```assembly
    ldr r1, =UART0_CTL_R
    ldr r0, [r1]
    orr r0, r0, #UART_CTL_UARTEN
    str r0, [r1]
```

### 结束初始化
最后，恢复链接寄存器并返回。

![](img/cfadd29ee48ba00c2f0d82ea4505529b_48.png)

![](img/cfadd29ee48ba00c2f0d82ea4505529b_49.png)

![](img/cfadd29ee48ba00c2f0d82ea4505529b_51.png)

![](img/cfadd29ee48ba00c2f0d82ea4505529b_53.png)

```assembly
    pop {lr}
    bx lr
```

---

## 总结
本节课中我们一起学习了如何从头开始编写一个 ARM UART 驱动程序的初始化部分。我们涵盖了以下关键步骤：
1.  启用 UART 和 GPIO 端口的时钟。
2.  配置 GPIO 引脚为 UART 备用功能。
3.  禁用 UART 以进行安全配置。
4.  根据系统时钟和目标波特率计算并设置波特率寄存器。
5.  配置 UART 的数据帧格式。
6.  最后重新启用 UART 模块。

![](img/cfadd29ee48ba00c2f0d82ea4505529b_55.png)

![](img/cfadd29ee48ba00c2f0d82ea4505529b_57.png)

这个初始化子程序为后续的数据收发功能奠定了基础。在下一课中，我们将继续创建用于读取和写入数据的子程序。