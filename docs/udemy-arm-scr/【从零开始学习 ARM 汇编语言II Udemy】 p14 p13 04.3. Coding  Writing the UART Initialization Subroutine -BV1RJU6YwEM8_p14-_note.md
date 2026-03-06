# ARM汇编语言：04.3：编写UART初始化子程序 🛠️

![](img/43d7f0e4c4d4018c44c4499793747496_0.png)

在本节课中，我们将学习如何为STM32微控制器编写一个UART（通用异步收发传输器）初始化的汇编语言子程序。我们将一步步配置相关寄存器，以启用UART模块并设置其基本参数。

---

![](img/43d7f0e4c4d4018c44c4499793747496_2.png)

## 概述

UART是一种常见的串行通信协议。在嵌入式系统中，初始化UART通常涉及配置GPIO引脚、启用相关时钟模块，并设置UART本身的控制寄存器。本节教程将引导你完成这些步骤。

## 代码结构与设置

首先，我们设置代码段的基本结构。我们使用Thumb指令集，并定义一个`main`标签作为程序入口。程序启动后，将跳转到我们即将编写的`uart_init`子程序。

```assembly
    .area .text
    .thumb
    .align 2
    .global main

main:
    b uart_init
```

## 启用GPIOA和UART时钟

![](img/43d7f0e4c4d4018c44c4499793747496_4.png)

初始化UART的第一步是启用GPIO端口A和UART2模块的时钟。这通过操作RCC（复位和时钟控制）寄存器来完成。

以下是配置步骤：
1.  加载RCC APB2外设时钟使能寄存器（`RCC_APB2ENR`）的地址到寄存器`R0`。
2.  读取该地址的当前值到`R1`。
3.  使用逻辑或（`OR`）操作，将`GPIOAEN`位（用于启用GPIOA时钟）置1。
4.  将结果写回`RCC_APB2ENR`寄存器。
5.  对`RCC_APB1ENR`寄存器重复类似操作，将`USART2EN`位置1以启用UART2时钟。

对应的C语言操作类似于：
```c
RCC->APB2ENR |= GPIOAEN;
RCC->APB1ENR |= USART2EN;
```

在汇编中实现如下：
```assembly
    ldr r0, =RCC_APB2ENR
    ldr r1, [r0]
    orr r1, #GPIOAEN
    str r1, [r0]

    ldr r0, =RCC_APB1ENR
    ldr r1, [r0]
    orr r1, #USART2EN
    str r1, [r0]
```

## 配置GPIOA引脚为复用功能

UART2的发送（TX）和接收（RX）引脚通常映射到GPIOA的特定引脚（如PA2和PA3）。我们需要将这些引脚配置为复用功能模式。

![](img/43d7f0e4c4d4018c44c4499793747496_6.png)

配置步骤如下：
1.  加载GPIOA复用功能低位寄存器（`GPIOA_AFRL`）的地址到`R0`。
2.  读取当前值到`R1`。
3.  使用`OR`操作，为PA2引脚设置正确的复用功能编码（例如`AF7`）。
4.  将结果存回寄存器。

![](img/43d7f0e4c4d4018c44c4499793747496_8.png)

在C语言中，这类似于：
```c
GPIOA->AFR[0] |= AF7 << (2 * 4); // 为PA2设置AF7
```

![](img/43d7f0e4c4d4018c44c4499793747496_10.png)

汇编实现：
```assembly
    ldr r0, =GPIOA_AFRL
    ldr r1, [r0]
    orr r1, #(AF7 << 8)        ; PA2位于AFRL寄存器的位8-11
    str r1, [r0]
```

## 设置GPIOA引脚模式

接下来，需要将PA2引脚的模式设置为复用功能输出。

![](img/43d7f0e4c4d4018c44c4499793747496_12.png)

配置步骤如下：
1.  加载GPIOA模式寄存器（`GPIOA_MODER`）的地址到`R0`。
2.  读取当前值到`R1`。
3.  使用`OR`操作，将PA2对应的模式位设置为`0b10`（复用功能模式）。
4.  将结果存回。

C语言示例：
```c
GPIOA->MODER |= (0b10 << (2 * 2)); // 设置PA2为复用模式
```

汇编实现：
```assembly
    ldr r0, =GPIOA_MODER
    ldr r1, [r0]
    orr r1, #(0b10 << 4)        ; PA2位于MODER寄存器的位4-5
    str r1, [r0]
```

## 配置UART波特率

UART通信速率由波特率寄存器（`USART2_BRR`）控制。我们需要根据系统时钟和期望的波特率计算并写入一个特定的值。

配置步骤如下：
1.  加载`USART2_BRR`寄存器的地址到`R0`。
2.  由于波特率值通常超过8位，我们使用`movw`指令将一个16位常数（例如`BRR_CF`）移动到`R1`。
3.  将`R1`的值存储到`USART2_BRR`寄存器。

![](img/43d7f0e4c4d4018c44c4499793747496_14.png)

C语言操作：
```c
USART2->BRR = BRR_CF;
```

![](img/43d7f0e4c4d4018c44c4499793747496_16.png)

![](img/43d7f0e4c4d4018c44c4499793747496_18.png)

汇编实现：
```assembly
    ldr r0, =USART2_BRR
    movw r1, #BRR_CF
    str r1, [r0]
```

## 配置UART控制寄存器

UART有多个控制寄存器（CR1， CR2， CR3），用于配置数据位、停止位、奇偶校验等参数。最佳实践是在配置前先禁用UART（清零CR1的UE位），但为了流程清晰，我们先配置其他寄存器，最后再启用。

![](img/43d7f0e4c4d4018c44c4499793747496_20.png)

以下是配置CR1、CR2、CR3的步骤：
1.  分别加载`USART2_CR1`， `USART2_CR2`， `USART2_CR3`的地址到`R0`。
2.  将预定义的配置常数（`CR1_CF`， `CR2_CF`， `CR3_CF`）移动到`R1`。注意常数的位宽，选择`mov`或`movw`指令。
3.  将`R1`的值直接写入对应的控制寄存器（这里使用直接写入而非`OR`操作，因为我们是在设置初始配置）。

C语言示例：
```c
USART2->CR1 = CR1_CF;
USART2->CR2 = CR2_CF;
USART2->CR3 = CR3_CF;
```

汇编实现：
```assembly
    ; 配置 CR1
    ldr r0, =USART2_CR1
    mov r1, #CR1_CF
    str r1, [r0]

    ; 配置 CR2
    ldr r0, =USART2_CR2
    mov r1, #CR2_CF
    str r1, [r0]

    ; 配置 CR3
    ldr r0, =USART2_CR3
    mov r1, #CR3_CF
    str r1, [r0]
```

## 启用UART模块

![](img/43d7f0e4c4d4018c44c4499793747496_22.png)

在完成所有配置后，最后一步是启用UART模块本身。这需要设置控制寄存器1（CR1）中的`UE`（UART Enable）位。

![](img/43d7f0e4c4d4018c44c4499793747496_24.png)

![](img/43d7f0e4c4d4018c44c4499793747496_26.png)

**重要提示**：由于CR1寄存器之前已经被写入配置（`CR1_CF`），我们不能直接写入一个新值覆盖它，否则会清除之前的配置。因此，这里必须使用“友好编程”的方式，即使用`OR`操作仅修改`UE`位。

配置步骤如下：
1.  再次加载`USART2_CR1`寄存器的地址到`R0`。
2.  读取其当前值到`R1`。
3.  使用`OR`操作，将`USART2_CR1_UE`位置1。
4.  将结果存回寄存器。

![](img/43d7f0e4c4d4018c44c4499793747496_28.png)

C语言操作：
```c
USART2->CR1 |= USART2_CR1_UE;
```

汇编实现：
```assembly
    ldr r0, =USART2_CR1
    ldr r1, [r0]
    orr r1, #USART2_CR1_UE
    str r1, [r0]
```

## 子程序返回

完成所有初始化步骤后，使用`bx lr`指令从`uart_init`子程序返回到主程序。

```assembly
    bx lr
```

![](img/43d7f0e4c4d4018c44c4499793747496_30.png)

## 总结

![](img/43d7f0e4c4d4018c44c4499793747496_32.png)

![](img/43d7f0e4c4d4018c44c4499793747496_33.png)

本节课中，我们一起学习了如何从头开始编写一个UART初始化的汇编子程序。我们逐步完成了以下核心任务：
1.  启用GPIOA和UART2的时钟。
2.  将GPIOA的特定引脚配置为UART复用功能。
3.  设置UART的波特率。
4.  配置UART的控制寄存器（CR1， CR2， CR3）。
5.  最后启用UART模块。

![](img/43d7f0e4c4d4018c44c4499793747496_35.png)

![](img/43d7f0e4c4d4018c44c4499793747496_36.png)

我们强调了在修改已配置的寄存器时（如最后启用UART），使用`OR`操作进行位操作的重要性，以避免覆盖现有设置。在下一节课中，我们将基于这个初始化好的UART，编写发送数据的子程序。