# 编写你自己的操作系统：5：中断处理 🛠️

在本节课中，我们将开始与硬件进行真正的交互，学习如何设置中断描述符表（IDT）来处理来自硬件（如键盘和定时器）的中断信号。这是操作系统能够响应外部事件的关键一步。

## 概述

上一节我们介绍了与硬件通信的基本概念。本节中，我们来看看如何通过设置中断描述符表来让CPU能够接收并处理硬件中断。我们将创建一个中断管理器，编写汇编处理程序，并最终配置可编程中断控制器（PIC）。

## 中断描述符表（IDT）的作用

当硬件（例如键盘）产生一个事件时，它会通过可编程中断控制器（PIC）向CPU发送一个中断信号。然而，计算机启动时，PIC默认不会将这些信息传递给CPU。我们需要先设置好中断描述符表，然后才能告诉PIC开始传递中断信息。

![](img/37d40cf8bcd5725d9e95d729ea0e833b_1.png)

如果没有设置IDT，中断会导致一个通用保护错误，可能使计算机重启或虚拟机终止。

IDT中的每个条目（称为门描述符）需要包含以下信息：
*   **中断号**：一个8位整数（`uint8_t`），用于标识是哪个中断（例如，键盘中断是1，定时器中断是0）。
*   **处理程序地址**：一个指向内存中中断处理函数（handler）的指针（`void*`）。
*   **代码段选择子**：告诉处理器在执行处理程序前切换到哪个内存段（例如，从用户空间切换到内核空间）。
*   **访问权限**：一个0到3的数字，表示特权级别（0是内核空间，3是用户空间）。
*   **一些标志位**。

## 中断处理程序的挑战与设计

![](img/37d40cf8bcd5725d9e95d729ea0e833b_3.png)

在高级语言（如C++）中，我们可能希望中断处理函数能直接接收中断号作为参数，例如 `void handleInterrupt(uint8_t number)`。但CPU无法直接做到这一点，因为它不能假设当前栈是否安全可用（例如，栈可能仍指向用户空间）。

![](img/37d40cf8bcd5725d9e95d729ea0e833b_5.png)

![](img/37d40cf8bcd5725d9e95d729ea0e833b_7.png)

![](img/37d40cf8bcd5725d9e95d729ea0e833b_9.png)

![](img/37d40cf8bcd5725d9e95d729ea0e833b_11.png)

![](img/37d40cf8bcd5725d9e95d729ea0e833b_13.png)

因此，CPU无法将中断号压入栈。解决方案是为每一个中断号编写不同的处理程序代码。这样，中断0、中断1等都有各自独立的入口点。

![](img/37d40cf8bcd5725d9e95d729ea0e833b_15.png)

这些处理程序最好用汇编语言编写，因为CPU在跳转到处理程序时处于不确定状态，而C++编译器生成的代码可能会改变寄存器状态，影响之前执行的代码。我们的设计是：
1.  用汇编宏为每个中断生成一个独立的处理程序。
2.  该处理程序将其中断号压栈，然后跳转到一个统一的C++函数。
3.  在C++函数中，我们可以进行更高级别的处理。

## 实现步骤

![](img/37d40cf8bcd5725d9e95d729ea0e833b_17.png)

![](img/37d40cf8bcd5725d9e95d729ea0e833b_19.png)

![](img/37d40cf8bcd5725d9e95d729ea0e833b_20.png)

![](img/37d40cf8bcd5725d9e95d729ea0e833b_22.png)

![](img/37d40cf8bcd5725d9e95d729ea0e833b_23.png)

以下是实现中断处理机制的核心步骤。

![](img/37d40cf8bcd5725d9e95d729ea0e833b_25.png)

![](img/37d40cf8bcd5725d9e95d729ea0e833b_27.png)

### 1. 创建汇编中断处理桩

我们首先创建几个文件：`interruptstubs.s`（汇编桩代码），`interrupts.h`（头文件）和`interrupts.cpp`（C++实现）。

![](img/37d40cf8bcd5725d9e95d729ea0e833b_29.png)

在 `interrupts.h` 中，我们定义一个 `InterruptManager` 类，它包含一个静态方法 `handleInterrupt`。这个方法目前只是接收中断号和当前栈指针，并原样返回栈指针（为后续的任务切换做准备）。

![](img/37d40cf8bcd5725d9e95d729ea0e833b_31.png)

```cpp
// interrupts.h 示例片段
class InterruptManager {
public:
    static uint32_t handleInterrupt(uint8_t interruptNumber, uint32_t stackPointer);
};
```

### 2. 编写汇编宏生成处理程序

在 `interruptstubs.s` 中，我们编写一个汇编宏 `INTERRUPT_REQUEST`，它为每个中断号生成特定的处理程序标签（如 `InterruptRequest0x00`）。

![](img/37d40cf8bcd5725d9e95d729ea0e833b_33.png)

![](img/37d40cf8bcd5725d9e95d729ea0e833b_35.png)

每个生成的处理程序会：
*   保存所有寄存器的值。
*   将其对应的中断号移入一个特定变量。
*   跳转到统一的 `interrupt_common` 桩代码。

`interrupt_common` 桩代码会：
*   将中断号和当前栈指针压栈。
*   调用C++函数 `InterruptManager::handleInterrupt`。
*   用函数的返回值（可能是一个新的栈指针）更新栈指针。
*   恢复所有寄存器的值。
*   执行 `iret` 指令从中断返回。

```nasm
; interruptstubs.s 示例片段（NASM语法）
%macro INTERRUPT_REQUEST 1
global InterruptRequest%1
InterruptRequest%1:
    mov byte [interruptNumber], %1 + IRQ_BASE ; IRQ_BASE 通常为 0x20
    jmp interrupt_common
%endmacro

interrupt_common:
    ; 保存所有寄存器...
    pushad
    ; ...
    ; 调用C++处理函数
    call InterruptManager_handleInterrupt
    ; 恢复所有寄存器...
    popad
    ; ...
    iret
```

### 3. 构建中断描述符表（IDT）

在 `InterruptManager` 类中，我们定义一个描述IDT条目的结构体 `GateDescriptor`，并创建一个包含256个条目的数组。

```cpp
// interrupts.h 示例片段
struct GateDescriptor {
    uint16_t handlerAddressLowBits;
    uint16_t gdt_codeSegmentSelector;
    uint8_t reserved;
    uint8_t accessRights;
    uint16_t handlerAddressHighBits;
} __attribute__((packed));
```

构造函数会初始化这个表：
1.  将所有条目默认设置为一个“忽略中断”的处理程序，以防止未处理的中断导致系统崩溃。
2.  为特定的中断（如0x20， 0x21）设置正确的处理程序地址、代码段选择子和访问权限（内核特权级，中断门类型）。

### 4. 加载IDT并配置PIC

创建并填充IDT后，我们需要告诉CPU使用它。这通过 `lidt` 汇编指令完成。

```cpp
// interrupts.cpp 示例片段
struct InterruptDescriptorTablePointer {
    uint16_t size;
    uint32_t base;
} __attribute__((packed));

![](img/37d40cf8bcd5725d9e95d729ea0e833b_37.png)

InterruptDescriptorTablePointer idtPointer;
idtPointer.size = sizeof(GateDescriptor) * 256 - 1;
idtPointer.base = (uint32_t)idt;
asm volatile("lidt (%0)" : : "r" (&idtPointer));
```

![](img/37d40cf8bcd5725d9e95d729ea0e833b_39.png)

仅仅设置IDT还不够，我们还需要告诉可编程中断控制器（PIC）开始向CPU发送中断。计算机通常有一个主PIC和一个从PIC。我们需要通过特定的端口（0x20， 0x21等）向它们发送初始化命令字（ICW），包括设置中断号的偏移量（例如，让主PIC的中断从0x20开始），以避免与CPU内部异常使用的中断号冲突。

```cpp
// 初始化PIC的示例代码
Port8Bit masterCommandPort(0x20);
Port8Bit masterDataPort(0x21);
// ... 初始化从PIC端口

![](img/37d40cf8bcd5725d9e95d729ea0e833b_41.png)

![](img/37d40cf8bcd5725d9e95d729ea0e833b_43.png)

![](img/37d40cf8bcd5725d9e95d729ea0e833b_44.png)

![](img/37d40cf8bcd5725d9e95d729ea0e833b_45.png)

![](img/37d40cf8bcd5725d9e95d729ea0e833b_46.png)

![](img/37d40cf8bcd5725d9e95d729ea0e833b_47.png)

![](img/37d40cf8bcd5725d9e95d729ea0e833b_48.png)

![](img/37d40cf8bcd5725d9e95d729ea0e833b_49.png)

// 发送初始化命令序列
masterCommandPort.Write(0x11); // 初始化开始
masterDataPort.Write(0x20);    // 主PIC中断向量偏移
// ... 其他配置
```

![](img/37d40cf8bcd5725d9e95d729ea0e833b_51.png)

![](img/37d40cf8bcd5725d9e95d729ea0e833b_53.png)

### 5. 启用中断

最后，我们通过 `sti` 汇编指令启用CPU的中断响应。通常，我们会在所有硬件初始化完成、IDT准备就绪后，再调用这个启用中断的方法。

```cpp
void InterruptManager::Activate() {
    asm volatile("sti");
}
```

## 测试与下一步

![](img/37d40cf8bcd5725d9e95d729ea0e833b_55.png)

完成以上步骤后编译运行，如果看到收到了第一个硬件中断（很可能是定时器中断），就证明我们的IDT和PIC配置成功了。目前我们只收到一次中断，因为还没有告诉PIC中断处理已经完成（需要发送“中断结束”EOI命令）。这将是下一节课的内容。

![](img/37d40cf8bcd5725d9e95d729ea0e833b_57.png)

## 总结

本节课中我们一起学习了操作系统中断处理的核心机制。我们了解了中断描述符表的结构与作用，设计了通过汇编桩代码与C++函数协作的中断处理流程，并实现了IDT的构建、加载以及PIC的初始化配置。现在，我们的操作系统已经具备了接收硬件中断信号的基础能力。下一节，我们将学习如何应答中断，并开始与键盘进行实际交互，获取真实的按键信息。