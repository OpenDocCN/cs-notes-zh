# ARM汇编语言入门II：09.2：为SysTick寄存器分配符号名称 🎯

![](img/a5f2a90e33f5d060f9ef65d15043e912_1.png)

![](img/a5f2a90e33f5d060f9ef65d15043e912_3.png)

![](img/a5f2a90e33f5d060f9ef65d15043e912_5.png)

在本节课中，我们将学习如何为SysTick定时器编写驱动程序。我们将通过为相关的寄存器分配符号名称来开始这个过程，这是编写底层硬件驱动代码的第一步。

![](img/a5f2a90e33f5d060f9ef65d15043e912_7.png)

## 概述

SysTick定时器是ARM Cortex-M系列处理器的一个核心外设。这意味着它的设计由ARM公司定义，并且在不同厂商（如TI、ST）生产的Cortex-M芯片中，其寄存器的地址和功能是相同的。因此，我们编写的驱动程序可以跨不同的Cortex-M4开发板工作。

为了编写驱动程序，我们首先需要查阅ARM提供的官方文档（Cortex-M4通用用户指南），以获取SysTick寄存器的确切内存地址和功能描述。然后，我们将为这些寄存器定义易于理解的符号名称，以便在后续的代码中使用。

## 创建新项目

首先，我们需要创建一个新的项目来编写我们的代码。

以下是创建新项目的步骤：
1.  新建一个项目。
2.  将项目存储在一个指定的文件夹中。
3.  将项目命名为“SysTick”。
4.  选择目标开发板为TM4C123GH6PM。

## 理解SysTick定时器

上一节我们创建了项目，本节中我们来看看SysTick定时器的核心概念。SysTick是一个24位的递减计数器。它从“重载值寄存器”中加载一个初始值，然后开始递减计数。当计数到0时，它会触发一个中断（如果已启用），并自动从重载值寄存器中重新加载数值，开始下一轮计数。

为了控制和使用这个定时器，我们需要操作三个主要的寄存器：
*   **控制与状态寄存器 (SysTick Control and Status Register)**：用于启用定时器、选择时钟源、启用中断以及检查计数是否完成。
*   **重载值寄存器 (SysTick Reload Value Register)**：用于设置定时器递减计数的初始值。
*   **当前值寄存器 (SysTick Current Value Register)**：用于读取定时器当前的计数值。

![](img/a5f2a90e33f5d060f9ef65d15043e912_9.png)

## 查找寄存器地址

![](img/a5f2a90e33f5d060f9ef65d15043e912_11.png)

![](img/a5f2a90e33f5d060f9ef65d15043e912_13.png)

![](img/a5f2a90e33f5d060f9ef65d15043e912_15.png)

由于SysTick是核心外设，其寄存器地址在ARM架构中是固定的。我们需要从《Cortex-M4通用用户指南》中查找这些地址，而不是从特定芯片（如TM4C）的数据手册中查找。

![](img/a5f2a90e33f5d060f9ef65d15043e912_17.png)

![](img/a5f2a90e33f5d060f9ef65d15043e912_19.png)

在文档中，我们可以找到SysTick寄存器的内存映射。例如，控制与状态寄存器的地址是 `0xE000E010`。

## 分配符号名称

现在，我们将为这些寄存器以及寄存器内部的特定控制位定义符号名称。遵循半导体厂商（如德州仪器TI）在官方头文件中的命名惯例，可以使我们的代码更具可读性和可移植性。

以下是需要定义的符号名称列表：
*   `NVIC_ST_CTRL_R`：对应SysTick控制与状态寄存器，地址为 `0xE000E010`。
*   `NVIC_ST_RELOAD_R`：对应SysTick重载值寄存器，地址为 `0xE000E014`。
*   `NVIC_ST_CURRENT_R`：对应SysTick当前值寄存器，地址为 `0xE000E018`。

此外，我们还需要为控制寄存器中的各个功能位定义掩码：
*   `NVIC_ST_CTRL_COUNT`：计数完成标志位（第16位），用于检查定时器是否已计数到0。
*   `NVIC_ST_CTRL_CLK_SRC`：时钟源选择位（第2位），设置为1表示使用处理器内核时钟。
*   `NVIC_ST_CTRL_INTEN`：中断使能位（第1位），用于启用SysTick中断。
*   `NVIC_ST_CTRL_ENABLE`：定时器使能位（第0位），用于启动或停止SysTick定时器。
*   `NVIC_ST_RELOAD_M`：重载值的最大24位数值，即 `0x00FFFFFF`。

在汇编代码中，这些定义通常使用 `.equ` 指令来实现：
```assembly
NVIC_ST_CTRL_R    .equ 0xE000E010
NVIC_ST_RELOAD_R  .equ 0xE000E014
NVIC_ST_CURRENT_R .equ 0xE000E018

NVIC_ST_CTRL_COUNT  .equ 0x00010000
NVIC_ST_CTRL_CLK_SRC .equ 0x00000004
NVIC_ST_CTRL_INTEN   .equ 0x00000002
NVIC_ST_CTRL_ENABLE  .equ 0x00000001
NVIC_ST_RELOAD_M     .equ 0x00FFFFFF
```

## 复用GPIO符号定义

为了让LED闪烁，我们还需要控制GPIO（通用输入输出）引脚。由于在之前的课程中已经为GPIO相关寄存器（如方向寄存器、数据寄存器、数字使能寄存器）定义了符号名称，我们可以直接将这些定义复制到当前项目中，无需重新编写。

![](img/a5f2a90e33f5d060f9ef65d15043e912_21.png)

## 总结

本节课中，我们一起学习了SysTick定时器作为ARM Cortex-M核心外设的基本概念。我们通过查阅ARM官方文档确定了其寄存器的固定地址，并遵循行业惯例为这些寄存器及其控制位分配了清晰的符号名称。这为下一节课实际编写SysTick驱动程序并实现精确延时功能奠定了坚实的基础。在下一节，我们将利用这些定义来初始化定时器并创建延时函数。