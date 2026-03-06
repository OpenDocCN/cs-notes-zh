# 003：编写 GPIO 输出驱动

![](img/eae157d3ea1b00721452d924b5cc88f5_0.png)

![](img/eae157d3ea1b00721452d924b5cc88f5_2.png)

![](img/eae157d3ea1b00721452d924b5cc88f5_3.png)

在本节课中，我们将学习如何为 STM32 微控制器编写一个基本的 GPIO 输出驱动程序。我们将使用汇编语言来操作寄存器，从而控制连接到 GPIO 引脚上的 LED。我们将从定义寄存器的符号地址开始，逐步编写初始化 GPIO 和点亮 LED 的代码。

## 定义寄存器符号地址

上一节我们了解了 GPIO 的基本原理，本节中我们来看看如何用汇编语言操作具体的寄存器。首先，我们需要为相关的内存地址创建易于理解的符号名称。

以下是定义寄存器基地址和偏移量的步骤：

1.  **定义 RCC 基地址**：复位和时钟控制单元的基地址是 `0x40023800`。
    ```
    RCC_BASE EQU 0x40023800
    ```

2.  **定义 AHB1 外设时钟使能寄存器偏移量**：该寄存器相对于 RCC 基地址的偏移是 `0x30`。
    ```
    AHB1ENR_OFFSET EQU 0x30
    ```

3.  **构造完整的 AHB1 使能寄存器地址**：将基地址与偏移量相加，得到寄存器的完整地址。
    ```
    RCC_AHB1ENR EQU RCC_BASE + AHB1ENR_OFFSET
    ```
    在 C 语言中，这等价于访问结构体成员 `RCC->AHB1ENR`。

![](img/eae157d3ea1b00721452d924b5cc88f5_5.png)

4.  **定义 GPIOA 基地址**：GPIO 端口 A 的基地址是 `0x40020000`。
    ```
    GPIOA_BASE EQU 0x40020000
    ```

5.  **定义模式寄存器偏移量**：模式寄存器位于端口基地址的 `0x00` 偏移处。
    ```
    MODER_OFFSET EQU 0x00
    ```

![](img/eae157d3ea1b00721452d924b5cc88f5_7.png)

![](img/eae157d3ea1b00721452d924b5cc88f5_9.png)

6.  **构造完整的 GPIOA 模式寄存器地址**：
    ```
    GPIOA_MODER EQU GPIOA_BASE + MODER_OFFSET
    ```

![](img/eae157d3ea1b00721452d924b5cc88f5_11.png)

7.  **定义输出数据寄存器偏移量**：输出数据寄存器的偏移量是 `0x14`。
    ```
    ODR_OFFSET EQU 0x14
    ```

8.  **构造完整的 GPIOA 输出数据寄存器地址**：
    ```
    GPIOA_ODR EQU GPIOA_BASE + ODR_OFFSET
    ```

## 定义配置常量

![](img/eae157d3ea1b00721452d924b5cc88f5_13.png)

除了地址，我们还需要定义配置引脚时用到的位掩码常量。

以下是需要定义的常量：

![](img/eae157d3ea1b00721452d924b5cc88f5_15.png)

*   **GPIOA 时钟使能位**：在 `RCC_AHB1ENR` 寄存器中，使能 GPIOA 的位是第 0 位（`1 << 0`）。
    ```
    GPIOA_EN EQU (1 << 0)
    ```
*   **引脚模式配置**：要将 PA5 配置为输出模式，需要在 `GPIOA_MODER` 寄存器的第 10 和 11 位写入 `01`（即 `1 << 10`）。
    ```
    MODE5_OUT EQU (1 << 10)
    ```
*   **引脚输出电平**：要设置 PA5 输出高电平以点亮 LED，需要设置 `GPIOA_ODR` 寄存器的第 5 位（`1 << 5`）。
    ```
    LED_ON EQU (1 << 5)
    ```

![](img/eae157d3ea1b00721452d924b5cc88f5_17.png)

## 编写初始化代码

![](img/eae157d3ea1b00721452d924b5cc88f5_19.png)

现在，我们可以开始编写实际的汇编代码来初始化外设并控制 LED。

![](img/eae157d3ea1b00721452d924b5cc88f5_20.png)

代码区域和入口点定义如下：
```
    AREA |.text|, CODE, READONLY, ALIGN=2
    THUMB
    EXPORT __main
```
`__main` 标签是程序的入口点。

### GPIO 初始化子程序

![](img/eae157d3ea1b00721452d924b5cc88f5_22.png)

![](img/eae157d3ea1b00721452d924b5cc88f5_23.png)

我们创建一个名为 `GPIOA_Init` 的子程序来执行所有初始化操作。

以下是初始化 GPIOA 的步骤：

1.  **使能 GPIOA 时钟**：
    *   将 `RCC_AHB1ENR` 的地址加载到寄存器 R0。
    *   读取该地址的当前值到 R1。
    *   将 `GPIOA_EN` 掩码与 R1 的值进行**或**操作，以在不影响其他位的情况下使能 GPIOA 时钟。
    *   将结果写回 `RCC_AHB1ENR`。
    ```assembly
    ; C 代码: RCC->AHB1ENR |= GPIOA_EN;
    LDR R0, =RCC_AHB1ENR   ; 加载 RCC_AHB1ENR 地址到 R0
    LDR R1, [R0]           ; 读取地址中的值到 R1
    ORR R1, #GPIOA_EN      ; 将 GPIOA 使能位设为 1
    STR R1, [R0]           ; 将新值存回 RCC_AHB1ENR
    ```

2.  **配置 PA5 为输出模式**：
    *   将 `GPIOA_MODER` 的地址加载到寄存器 R0。
    *   读取当前值到 R1。
    *   将 `MODE5_OUT` 掩码与 R1 的值进行**或**操作，以设置 PA5 为输出模式。
    *   将结果写回 `GPIOA_MODER`。
    ```assembly
    ; C 代码: GPIOA->MODER |= MODE5_OUT;
    LDR R0, =GPIOA_MODER   ; 加载 GPIOA_MODER 地址到 R0
    LDR R1, [R0]           ; 读取地址中的值到 R1
    ORR R1, #MODE5_OUT     ; 设置 PA5 模式位为输出
    STR R1, [R0]           ; 将新值存回 GPIOA_MODER
    ```

![](img/eae157d3ea1b00721452d924b5cc88f5_25.png)

![](img/eae157d3ea1b00721452d924b5cc88f5_27.png)

![](img/eae157d3ea1b00721452d924b5cc88f5_29.png)

3.  **设置 PA5 输出高电平（点亮 LED）**：
    *   将 `GPIOA_ODR` 的地址加载到寄存器 R0。
    *   将 `LED_ON` 的值加载到寄存器 R1。
    *   将 R1 的值写入 `GPIOA_ODR`，使 PA5 输出高电平。
    ```assembly
    ; C 代码: GPIOA->ODR = LED_ON;
    LDR R0, =GPIOA_ODR     ; 加载 GPIOA_ODR 地址到 R0
    LDR R1, =LED_ON        ; 加载 LED_ON 值到 R1
    STR R1, [R0]           ; 将值写入 ODR 以点亮 LED
    ```
    子程序最后使用 `BX LR` 指令返回。

![](img/eae157d3ea1b00721452d924b5cc88f5_31.png)

![](img/eae157d3ea1b00721452d924b5cc88f5_33.png)

### 主程序循环

主程序 `__main` 首先跳转到 `GPIOA_Init` 子程序进行初始化，然后进入一个无限循环。

![](img/eae157d3ea1b00721452d924b5cc88f5_35.png)

![](img/eae157d3ea1b00721452d924b5cc88f5_37.png)

```assembly
__main
    BL GPIOA_Init          ; 调用初始化子程序
Loop
    B Loop                 ; 无限循环，保持程序运行
    ALIGN
    END
```

![](img/eae157d3ea1b00721452d924b5cc88f5_39.png)

![](img/eae157d3ea1b00721452d924b5cc88f5_41.png)

## 程序验证

![](img/eae157d3ea1b00721452d924b5cc88f5_43.png)

![](img/eae157d3ea1b00721452d924b5cc88f5_45.png)

将代码编译并下载到 STM32 开发板后，连接到 PA5 引脚的 LED 应该被点亮。这证明我们成功使用汇编语言编写了 GPIO 输出驱动程序。

![](img/eae157d3ea1b00721452d924b5cc88f5_47.png)

![](img/eae157d3ea1b00721452d924b5cc88f5_49.png)

![](img/eae157d3ea1b00721452d924b5cc88f5_50.png)

本节课中我们一起学习了如何为 STM32 的 GPIO 编写汇编驱动。我们从定义寄存器的符号地址和配置常量开始，然后逐步编写了使能时钟、配置引脚模式和设置输出电平的代码。通过这个实践，我们掌握了使用汇编语言直接操作硬件寄存器的基本方法。