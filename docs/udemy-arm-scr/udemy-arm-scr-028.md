# 028：07.2 为相关ADC寄存器分配符号名称

![](img/148ba4c33d2e12f8b358fd5c0fa28d75_1.png)

![](img/148ba4c33d2e12f8b358fd5c0fa28d75_3.png)

![](img/148ba4c33d2e12f8b358fd5c0fa28d75_5.png)

在本节课中，我们将学习如何为STM32开发板的ADC（模数转换器）外设编写汇编语言驱动程序。我们将从创建一个新项目开始，并逐步为所有必要的ADC寄存器分配符号名称，为后续的驱动代码编写打下基础。

![](img/148ba4c33d2e12f8b358fd5c0fa28d75_7.png)

## 创建新项目

![](img/148ba4c33d2e12f8b358fd5c0fa28d75_9.png)

首先，我们需要在集成开发环境中创建一个新的项目。

1.  选择 `Project` -> `New Project`。
2.  创建一个名为 `ADC` 的文件夹。
3.  将项目也命名为 `ADC`。
4.  选择我们的目标开发板型号：`STM32F411VET`。
5.  在配置中，选择正确的核心（Core）和启动文件（Startup）。
6.  在项目结构中，创建一个名为 `app` 的源文件组。
7.  右键点击 `app` 组，选择 `Add New Item`，创建一个名为 `main.s` 的汇编源文件。

至此，项目的基本框架已经搭建完成。

## 复用已有的LED配置

![](img/148ba4c33d2e12f8b358fd5c0fa28d75_11.png)

在本次实验中，我们将使用一个ADC引脚和一个LED。我们将从ADC引脚读取模拟值，并通过一个条件语句，在模拟值超过特定阈值时点亮LED。

![](img/148ba4c33d2e12f8b358fd5c0fa28d75_13.png)

![](img/148ba4c33d2e12f8b358fd5c0fa28d75_15.png)

因此，我们需要复用之前为LED配置好的寄存器符号名称。以下是相关的定义：

```assembly
RCC_BASE_AHBENR    EQU 0x40023830  ; AHB外设时钟使能寄存器基址偏移
GPIOA_BASE         EQU 0x40020000  ; GPIOA端口基址
GPIOA_MODER_OFFSET EQU 0x00        ; 模式寄存器偏移量
GPIOA_ODR_OFFSET   EQU 0x14        ; 输出数据寄存器偏移量
MODER5_OUT         EQU (1 << 10)   ; 设置PA5为输出模式
LED_ON             EQU (1 << 5)    ; 设置PA5输出高电平，点亮LED
LED_OFF            EQU (0 << 5)    ; 设置PA5输出低电平，熄灭LED
```

## 确定ADC的时钟总线

![](img/148ba4c33d2e12f8b358fd5c0fa28d75_17.png)

要使用一个外设，首先需要查看其系统框图，以确定它是连接到AHB总线还是APB总线，从而知道需要通过哪个总线来使能其时钟。

![](img/148ba4c33d2e12f8b358fd5c0fa28d75_19.png)

根据STM32F411的数据手册中的系统框图，`ADC1` 模块连接在 `APB2` 总线上。因此，我们需要通过APB2外设时钟使能寄存器来为ADC1提供时钟。

## 定义ADC相关寄存器符号名称

接下来，我们将根据参考手册，查找并定义配置ADC所需的所有关键寄存器的基址、偏移量和相关配置位。

![](img/148ba4c33d2e12f8b358fd5c0fa28d75_21.png)

![](img/148ba4c33d2e12f8b358fd5c0fa28d75_23.png)

### 1. 使能ADC时钟

首先，定义APB2外设时钟使能寄存器及其用于ADC1的使能位。

```assembly
; APB2外设时钟使能寄存器
RCC_APB2ENR_OFFSET EQU 0x44
RCC_APB2ENR        EQU RCC_BASE + RCC_APB2ENR_OFFSET
ADC1_EN            EQU (1 << 8)    ; 设置第8位为1，使能ADC1时钟
```

### 2. ADC外设基地址

从数据手册的内存映射表中，找到ADC1的基地址。

```assembly
; ADC1外设基地址
ADC1_BASE          EQU 0x40012000
```

### 3. ADC状态寄存器 (ADC_SR)

![](img/148ba4c33d2e12f8b358fd5c0fa28d75_25.png)

![](img/148ba4c33d2e12f8b358fd5c0fa28d75_27.png)

状态寄存器用于检查模数转换是否完成。我们关注其中的 `EOC` (End Of Conversion) 位。

```assembly
; ADC状态寄存器
ADC1_SR_OFFSET     EQU 0x00
ADC1_SR            EQU ADC1_BASE + ADC1_SR_OFFSET
ADC1_SR_EOC_FLAG   EQU (1 << 1)    ; EOC标志位，转换完成时由硬件置1
```

### 4. ADC控制寄存器2 (ADC_CR2)

此寄存器用于启用/禁用ADC模块，以及控制转换的启动方式。

![](img/148ba4c33d2e12f8b358fd5c0fa28d75_29.png)

```assembly
; ADC控制寄存器2
ADC1_CR2_OFFSET    EQU 0x08
ADC1_CR2           EQU ADC1_BASE + ADC1_CR2_OFFSET
CR2_ADON_EN        EQU 0x00000001  ; 第0位，置1以启用ADC1
CR2_SWSTART        EQU (1 << 30)   ; 软件启动转换
CR2_EXTEN_DISABLED EQU (0 << 28)   ; 禁用外部触发，使用软件触发
```

### 5. ADC规则序列寄存器 (ADC_SQR1, ADC_SQR3)

这些寄存器用于配置转换序列的长度和顺序。

```assembly
; 规则序列寄存器1 - 设置转换序列长度
ADC1_SQR1_OFFSET   EQU 0x2C
ADC1_SQR1          EQU ADC1_BASE + ADC1_SQR1_OFFSET
SQR1_LEN_1         EQU (0 << 20)   ; 设置转换序列长度为1

; 规则序列寄存器3 - 设置转换序列中的第一个通道
ADC1_SQR3_OFFSET   EQU 0x34
ADC1_SQR3          EQU ADC1_BASE + ADC1_SQR3_OFFSET
SQR3_FIRST_CH1     EQU (1 << 0)    ; 设置转换序列从通道1开始
```

在STM32中，ADC通道号通常与引脚号对应。例如，`PA1` 对应通道1，`PB15` 对应通道15。

### 6. ADC数据寄存器 (ADC_DR)

转换完成后，模拟量转换得到的数字值将存储在此寄存器中。

```assembly
; ADC数据寄存器
ADC1_DR_OFFSET     EQU 0x4C
ADC1_DR            EQU ADC1_BASE + ADC1_DR_OFFSET
```

### 7. 配置ADC引脚模式

用于ADC的GPIO引脚必须设置为模拟模式。这通过配置GPIO的模式寄存器实现。

```assembly
; 配置PA1为模拟模式 (用于ADC)
MODER1_ANALOG      EQU (0x3 << 2)  ; 设置MODER1[3:2] = 0b11，即模拟模式
```

## 总结

本节课中，我们一起学习了为STM32的ADC外设编写汇编驱动程序的准备工作。我们完成了以下关键步骤：

1.  创建了新的项目框架。
2.  复用了已有的LED GPIO配置。
3.  通过查阅数据手册和参考手册，确定了ADC1连接在APB2总线上。
4.  系统性地查找并定义了所有必需的ADC寄存器符号名称，包括：
    *   时钟使能寄存器 (`RCC_APB2ENR`)
    *   ADC外设基地址 (`ADC1_BASE`)
    *   状态寄存器 (`ADC1_SR`) 及转换完成标志 (`EOC`)
    *   控制寄存器2 (`ADC1_CR2`) 及其启用、软件触发位
    *   规则序列寄存器 (`ADC1_SQR1`, `ADC1_SQR3`) 用于配置转换
    *   数据寄存器 (`ADC1_DR`) 用于读取转换结果
    *   GPIO模式配置，将ADC引脚设置为模拟模式。

![](img/148ba4c33d2e12f8b358fd5c0fa28d75_31.png)

现在，我们已经为ADC外设分配了所有相关的符号名称，为下一节课实际编写驱动程序代码做好了充分准备。在下一节中，我们将利用这些定义，初始化ADC并实现模拟信号的读取。