# 001：一小时内编写你的操作系统

![](img/59eaeaecbe2491e5aee4b05d60ae8c6f_1.png)

![](img/59eaeaecbe2491e5aee4b05d60ae8c6f_3.png)

![](img/59eaeaecbe2491e5aee4b05d60ae8c6f_5.png)

在本教程中，我们将学习如何从零开始编写一个简单的操作系统内核。我们将使用C++和汇编语言，并通过GRUB引导加载程序来启动我们的内核。教程将涵盖从设置开发环境、理解计算机启动过程，到编写内核代码并将其加载到内存中的完整流程。

## 准备工作与开发环境

上一节我们介绍了本教程的目标，本节中我们来看看开始编写操作系统前需要做的准备工作。

首先，你需要准备以下软件和开发环境。以下是所需的工具列表：
*   **GNU编译器集合**：包括C++编译器 `g++`。
*   **GNU汇编器**：`as`。
*   **开发库**：`libc6-dev-i386` 包。

本教程选择使用C++而非C语言进行开发。C++在保持高性能的同时，提供了面向对象等现代编程范式，是性能与现代特性的良好折中。

## 计算机启动流程

在开始编码之前，理解计算机从开机到执行我们代码的完整流程至关重要。

当你启动计算机时，主板上的BIOS（基本输入输出系统）会首先运行。BIOS是一段固件，它执行硬件自检，然后将控制权交给引导加载程序。

具体流程如下：
1.  BIOS将其自身代码从ROM复制到RAM中。
2.  BIOS指示CPU从特定内存地址开始执行，即运行BIOS固件代码。
3.  BIOS以低级方式与硬盘通信，读取硬盘主引导记录（MBR）中的前512字节（引导扇区）到内存。
4.  BIOS跳转到引导加载程序代码。本教程使用**GRUB**作为引导加载程序。
5.  GRUB比BIOS更复杂，它能理解分区表和文件系统。它会读取配置文件（如 `/boot/grub/grub.cfg`），并在屏幕上显示可引导的操作系统列表。
6.  当你选择一个条目（例如我们的自制系统）后，GRUB会根据配置找到内核文件（例如 `kernel.bin`），将其加载到内存中。
7.  最后，GRUB跳转到我们内核的入口点，此时我们的代码开始执行。

## 内核入口与栈指针问题

上一节我们了解了引导流程，本节中我们来看看编写内核时遇到的第一个技术挑战。

当GRUB将控制权交给我们的内核时，存在一个关键问题：**GRUB不会设置栈指针（ESP寄存器）**。而C/C++程序在开始运行时期望栈指针已被正确设置，以便进行函数调用、局部变量存储等操作。

为了解决这个问题，我们需要编写两个文件：
1.  **`loader.S`**：一个汇编文件，负责设置栈指针，然后跳转到我们的C++内核主函数。
2.  **`kernel.cpp`**：我们的C++内核主文件。

编译和链接过程如下：
*   使用汇编器 `as` 编译 `loader.S`，生成 `loader.o`。
*   使用C++编译器 `g++` 编译 `kernel.cpp`，生成 `kernel.o`。
*   使用链接器 `ld` 将两个目标文件 `loader.o` 和 `kernel.o` 合并，生成最终的可引导内核文件 `kernel.bin`。

此外，需要注意的是，计算机启动时CPU处于**32位兼容模式**。因此，我们的内核也将被编写为32位程序以兼容此模式。

## 创建项目文件与Makefile

现在，让我们开始创建项目。首先在空目录中创建以下文件：
*   `loader.S`
*   `kernel.cpp`
*   `linker.ld`
*   `Makefile`

`Makefile` 用于自动化编译和链接过程。其核心规则如下：

```makefile
# 定义编译器和参数
CXXFLAGS = -m32 -nostdlib -fno-builtin -fno-rtti -fno-exceptions -fno-leading-underscore
ASFLAGS = --32
LDFLAGS = -m elf_i386 -T linker.ld

# 从.cpp生成.o
%.o: %.cpp
    g++ $(CXXFLAGS) -c $< -o $@

# 从.S生成.o
%.o: %.S
    as $(ASFLAGS) -c $< -o $@

# 链接所有.o文件生成kernel.bin
kernel.bin: linker.ld loader.o kernel.o
    ld $(LDFLAGS) -o $@ loader.o kernel.o

![](img/59eaeaecbe2491e5aee4b05d60ae8c6f_7.png)

![](img/59eaeaecbe2491e5aee4b05d60ae8c6f_9.png)

# 安装内核到/boot目录
install: kernel.bin
    cp kernel.bin /boot/mykernel.bin
```

## 编写汇编引导器 (loader.S)

`loader.S` 文件是内核的入口点，它主要完成三件事：定义多引导头、设置栈空间、跳转到C++主函数。

其核心代码如下：

```assembly
# 定义多引导头，使GRUB识别本文件为合法内核
.set MAGIC, 0x1BADB002
.set FLAGS, 0
.set CHECKSUM, -(MAGIC + FLAGS)

![](img/59eaeaecbe2491e5aee4b05d60ae8c6f_11.png)

![](img/59eaeaecbe2491e5aee4b05d60ae8c6f_13.png)

![](img/59eaeaecbe2491e5aee4b05d60ae8c6f_15.png)

.section .multiboot
    .long MAGIC
    .long FLAGS
    .long CHECKSUM

![](img/59eaeaecbe2491e5aee4b05d60ae8c6f_17.png)

# 设置栈空间（2MB）和栈指针
.section .bss
.align 16
stack_bottom:
.skip 2 * 1024 * 1024 # 2 MiB
stack_top:

.section .text
.global _start
.type _start, @function
_start:
    # 设置栈指针
    mov $stack_top, %esp

    # 调用C++内核主函数
    call kernel_main

    # 内核主函数不应返回，若返回则进入无限循环
    cli
loop:
    hlt
    jmp loop
```
**代码解释**：
*   `.multiboot` 节包含GRUB所需的“魔数”和校验和，这是一个约定。
*   `.bss` 节预留了2MB的未初始化空间作为内核栈。
*   `_start` 是入口点：它将栈顶地址 `stack_top` 加载到ESP寄存器，然后调用 `kernel_main` 函数。

## 编写C++内核 (kernel.cpp)

在 `kernel.cpp` 中，我们将实现内核的主函数。一个关键点是，在独立环境中（没有操作系统支持），我们不能使用标准库函数（如 `printf`），因为它们是依赖操作系统和C库的。

因此，我们需要自己实现一个向屏幕输出文本的函数。在文本模式下，屏幕内容映射到内存地址 `0xB8000`。每个字符占用两个字节：低字节是ASCII码，高字节是颜色属性。

以下是 `kernel.cpp` 的初始实现：

```cpp
// 定义视频内存地址
volatile unsigned short* video_memory = (unsigned short*)0xB8000;

![](img/59eaeaecbe2491e5aee4b05d60ae8c6f_19.png)

![](img/59eaeaecbe2491e5aee4b05d60ae8c6f_21.png)

![](img/59eaeaecbe2491e5aee4b05d60ae8c6f_23.png)

![](img/59eaeaecbe2491e5aee4b05d60ae8c6f_25.png)

// 自定义字符串打印函数
void print_string(const char* str) {
    for(int i = 0; str[i] != '\0'; ++i) {
        // 写入字符，保留原有的颜色属性（高字节）
        video_memory[i] = (video_memory[i] & 0xFF00) | str[i];
    }
}

// 内核主函数
extern "C" void kernel_main() {
    // 在屏幕左上角打印欢迎信息
    print_string("Hello from My Operating System!");

    // 内核永不退出，进入无限循环
    while(true) {
        // 空循环
    }
}
```
**代码解释**：
*   `video_memory` 是一个指向视频内存的指针。
*   `print_string` 函数遍历字符串，将每个字符的ASCII码写入视频内存的对应位置，同时通过 `& 0xFF00` 操作保留该位置原有的颜色属性。
*   `extern "C"` 用于防止C++编译器对函数名进行修饰（name mangling），确保汇编代码可以正确调用 `kernel_main`。
*   内核主函数打印一条消息后，进入无限循环。

![](img/59eaeaecbe2491e5aee4b05d60ae8c6f_27.png)

## 链接器脚本 (linker.ld)

![](img/59eaeaecbe2491e5aee4b05d60ae8c6f_29.png)

![](img/59eaeaecbe2491e5aee4b05d60ae8c6f_31.png)

链接器脚本 `linker.ld` 指导链接器如何将不同目标文件（`.o`）中的各个段（section）组合到最终的可执行文件（`.bin`）中。这对于控制内核在内存中的布局至关重要。

一个基础的链接器脚本如下：

```ld
/* 指定入口点为 _start（在loader.S中定义） */
ENTRY(_start)

/* 输出文件格式和架构 */
OUTPUT_FORMAT(elf32-i386)
OUTPUT_ARCH(i386)

SECTIONS {
    /* 内核从1MB地址开始加载（GRUB的约定） */
    . = 1M;

    /* 首先放置多引导头，确保GRUB能正确识别 */
    .multiboot : {
        *(.multiboot)
    }

    /* 接着是代码段（.text） */
    .text : {
        *(.text)
    }

    /* 然后是只读数据段（.rodata） */
    .rodata : {
        *(.rodata)
    }

    /* 接着是已初始化的数据段（.data） */
    .data : {
        *(.data)
    }

    /* 最后是未初始化的数据段和栈空间（.bss） */
    .bss : {
        *(COMMON)
        *(.bss)
    }
}
```

![](img/59eaeaecbe2491e5aee4b05d60ae8c6f_33.png)

![](img/59eaeaecbe2491e5aee4b05d60ae8c6f_35.png)

![](img/59eaeaecbe2491e5aee4b05d60ae8c6f_37.png)

## 配置GRUB并测试运行

![](img/59eaeaecbe2491e5aee4b05d60ae8c6f_39.png)

![](img/59eaeaecbe2491e5aee4b05d60ae8c6f_41.png)

所有代码编写完成后，最后一步是配置GRUB来引导我们的内核。

![](img/59eaeaecbe2491e5aee4b05d60ae8c6f_43.png)

![](img/59eaeaecbe2491e5aee4b05d60ae8c6f_45.png)

1.  **编译**：在项目目录运行 `make` 命令，生成 `kernel.bin`。
2.  **安装**：运行 `sudo make install`，将 `kernel.bin` 复制到 `/boot/mykernel.bin`。
3.  **配置GRUB**：编辑GRUB配置文件 `/boot/grub/grub.cfg`，在文件末尾添加一个新的菜单项：
    ```bash
    menuentry "My Operating System" {
        multiboot /boot/mykernel.bin
        boot
    }
    ```
4.  **重启测试**：保存配置文件后，重启计算机。在GRUB启动菜单中，你应该能看到“My Operating System”选项。选择它，如果一切顺利，屏幕上将显示“Hello from My Operating System!”。

![](img/59eaeaecbe2491e5aee4b05d60ae8c6f_47.png)

![](img/59eaeaecbe2491e5aee4b05d60ae8c6f_49.png)

![](img/59eaeaecbe2491e5aee4b05d60ae8c6f_51.png)

## 总结

本节课中我们一起学习了如何编写一个最简单的操作系统内核。我们从理解计算机启动流程和GRUB引导加载程序的作用开始，然后解决了独立环境编程的核心挑战——设置栈指针和实现基本输出。通过创建汇编引导器 (`loader.S`)、C++内核 (`kernel.cpp`)、链接器脚本 (`linker.ld`) 和自动化构建脚本 (`Makefile`)，我们成功构建了一个能被GRUB加载并能在屏幕上打印信息的最小内核。这为后续深入探索操作系统开发（如中断处理、内存管理、进程调度等）奠定了坚实的基础。在下一个阶段，建议在虚拟机中进行开发测试，以提升效率。