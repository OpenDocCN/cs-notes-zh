# 13：内核启动流程与时钟中断 🚀

![](img/6feeb9aa16f9013c104ca27c22fe10cf_0.png)

在本节课中，我们将学习 xv6 操作系统的内核启动流程，并了解时钟中断是如何初始化和处理的。我们将重点分析 `entry.S` 和 `start.c` 这两个文件中的代码。这些代码主要在机器模式下执行，并在最后切换到监管者模式，跳转到 `main` 函数。

## 启动代码概览

上一节我们介绍了课程目标，本节中我们来看看启动过程涉及的两个核心文件。

*   **`entry.S`**：包含一小段汇编代码，用于初始化栈指针并跳转到 `start` 函数。
*   **`start.c`**：包含 `start` 和 `timerinit` 两个函数，负责设置机器模式下的各种寄存器，最终通过 `mret` 指令进入监管者模式的 `main` 函数。

## 栈空间分配

在多核系统中，每个核心都需要自己独立的栈空间。以下是 `start.c` 中为每个核心分配栈空间的代码。

```c
__attribute__ ((aligned (16))) char stack0[4096 * NCPU];
```
*   `NCPU` 是一个常量，设置为 8，表示系统最多支持 8 个核心。
*   为每个核心分配一个 4096 字节（4KB）的页面作为栈。
*   `__attribute__ ((aligned (16)))` 确保这个数组在 16 字节边界上对齐。

## 汇编入口点：`entry.S`

现在，让我们进入汇编代码部分，看看系统是如何开始执行的。

```assembly
.section .text
.globl _entry
_entry:
    la sp, stack0
    li a0, 1024*4
    csrr a1, mhartid
    addi a1, a1, 1
    mul a0, a0, a1
    add sp, sp, a0
    call start
spin:
    j spin
```
*   `.section .text` 指示将后续代码放入可执行的文本段。
*   `.globl _entry` 将 `_entry` 标签声明为全局符号，以便链接器识别。
*   `la sp, stack0` 将 `stack0` 数组的地址加载到栈指针寄存器 `sp`。
*   接下来的指令根据当前核心的 ID (`mhartid`) 计算该核心栈的顶部地址，并设置 `sp`。
*   `call start` 跳转到 `start.c` 中的 `start` 函数。
*   如果 `start` 函数意外返回，代码将进入 `spin` 处的无限循环。

## 机器模式初始化：`start` 函数

在 `entry.S` 设置好栈之后，控制权交给了 `start` 函数。这个函数在机器模式下执行，为进入监管者模式做准备。

```c
void start() {
    // 设置 mstatus 寄存器，准备在 mret 后进入监管者模式
    unsigned long x = r_mstatus();
    x &= ~MSTATUS_MPP_MASK;
    x |= MSTATUS_MPP_S;
    w_mstatus(x);

    // 设置 mret 后要跳转的地址为 main 函数
    w_mepc((uint64)main);

    // 禁用分页（SATP 寄存器置零）
    w_satp(0);

    // 将中断和异常委托给监管者模式处理
    w_medeleg(0xffff);
    w_mideleg(0xffff);

    // 在监管者模式下启用外部设备、软件和时钟中断（虽然时钟中断委托无效）
    w_sie(r_sie() | SIE_SEIE | SIE_STIE | SIE_SSIE);

    // 配置物理内存保护（PMP），允许监管者模式访问所有物理内存
    w_pmpaddr0(0x3fffffffffffffull);
    w_pmpcfg0(0xf);

    // 初始化时钟中断
    timerinit();

    // 将核心 ID 写入 tp 寄存器，供 mycpu() 等函数使用
    w_tp(r_mhartid());

    // 执行 mret，切换到监管者模式并跳转到 main 函数
    asm volatile("mret");
}
```
以下是 `start` 函数的关键步骤说明：
1.  **设置机器状态 (`mstatus`)**：清除之前的特权模式位，并设置为从监管者模式“返回”。
2.  **设置异常程序计数器 (`mepc`)**：指向 `main` 函数，这样 `mret` 指令就会跳转到那里。
3.  **禁用转换 (`satp`)**：确保在进入 `main` 时未启用分页。
4.  **委托中断和异常**：通过 `medeleg` 和 `mideleg` 寄存器，将大多数中断和异常的处理委托给监管者模式。**注意：时钟中断 (`MTI`) 无法被委托**。
5.  **启用监管者模式中断**：在 `sie` 寄存器中启用相应位，允许监管者模式接收中断。
6.  **配置物理内存保护 (PMP)**：简化设置，使监管者模式能访问所有物理内存。
7.  **初始化时钟**：调用 `timerinit()` 函数。
8.  **保存核心 ID**：将核心 ID 写入 `tp` 寄存器，这是一个经常用于存储核心特定信息的寄存器。
9.  **切换模式**：执行 `mret` 指令。这会根据之前设置的 `mstatus` 和 `mepc`，将特权级切换到监管者模式，并开始执行 `main` 函数。

## 时钟中断初始化：`timerinit` 函数

时钟中断需要特殊处理，因为它必须在机器模式下处理。`timerinit` 函数负责其初始化。

首先，我们需要了解一个核心数据结构 `timer_scratch`，它为每个核心存储了处理时钟中断所需的信息。

```c
// 每个核心有 5 个 64 位字的存储区域
uint64 timer_scratch[NCPU][5];
```
这个数组的每个元素（对应一个核心）布局如下：
*   **偏移 0-15**：用于临时保存寄存器 `a1-a3`。
*   **偏移 24**：存储该核心的 `mtimecmp` 寄存器地址。
*   **偏移 32**：存储时钟中断间隔（1000000 个周期）。

以下是 `timerinit` 函数的代码：

```c
void timerinit() {
    int id = r_mhartid(); // 获取当前核心 ID
    // 设置第一次时钟中断：当前时间 + 1000000 周期
    *(uint64*)CLINT_MTIMECMP(id) = *(uint64*)CLINT_MTIME + interval;

    // 获取当前核心的 timer_scratch 区域指针
    uint64 *scratch = &timer_scratch[id][0];
    // 保存 mtimecmp 寄存器地址和间隔值
    scratch[3] = CLINT_MTIMECMP(id);
    scratch[4] = interval;
    // 将区域地址写入核心的 mscratch 寄存器
    w_mscratch((uint64)scratch);

    // 设置机器模式陷阱向量地址为 timervec
    w_mtvec((uint64)timervec);

    // 启用机器模式中断
    w_mstatus(r_mstatus() | MSTATUS_MIE);
    // 特别启用机器模式下的时钟中断 (MTIE)
    w_mie(r_mie() | MIE_MTIE);
}
```
函数步骤如下：
1.  **设置首次中断**：向当前核心的 `mtimecmp` 寄存器写入一个未来的时间点（当前时间 + 1000000 周期）。
2.  **准备暂存区**：将 `mtimecmp` 的地址和中断间隔存储到该核心的 `timer_scratch` 区域中。
3.  **设置 `mscratch`**：将该区域的地址存入 `mscratch` 寄存器，以便中断处理程序快速找到它。
4.  **设置陷阱向量**：将机器模式陷阱向量地址 (`mtvec`) 设置为 `timervec`。当时钟中断发生时，硬件会自动跳转到此处。
5.  **启用中断**：在机器状态 (`mstatus`) 中全局启用中断，并在机器中断启用 (`mie`) 寄存器中特别启用时钟中断。

## 时钟中断处理程序：`timervec`

当时钟中断发生时，CPU 在机器模式下跳转到 `timervec`（位于 `kernelvec.S` 中）。这个处理程序的主要职责是安排下一次中断，并触发一个监管者模式的软件中断，让内核进行真正的调度处理。

```assembly
.globl timervec
.align 4
timervec:
    csrrw a0, mscratch, a0
    sd a1, 0(a0)
    sd a2, 8(a0)
    sd a3, 16(a0)

    ld a1, 24(a0)
    ld a2, 32(a0)
    ld a3, 0(a1)
    add a3, a3, a2
    sd a3, 0(a1)

    li a1, 2
    csrw sip, a1

    ld a3, 16(a0)
    ld a2, 8(a0)
    ld a1, 0(a0)
    csrrw a0, mscratch, a0
    mret
```
处理流程如下：
1.  **保存上下文**：利用 `mscratch` 指向的暂存区，快速保存 `a0-a3` 寄存器。
2.  **安排下次中断**：从暂存区加载 `mtimecmp` 地址和间隔值，计算新的中断时间并写回寄存器。
3.  **触发软件中断**：向监管者中断待处理寄存器 `sip` 写入值 `2`（对应监管者软件中断位 `SSIP`）。这会在监管者模式中产生一个待处理的中断。
4.  **恢复上下文并返回**：恢复所有保存的寄存器，然后执行 `mret` 返回被中断的代码。
5.  **内核处理**：当监管者模式代码（内核）下次启用中断时，会处理这个软件中断。内核的中断处理程序会将其解释为一次时钟中断，并执行进程调度等操作。

## 总结

本节课中我们一起学习了 xv6 内核的启动流程和时钟中断机制。

1.  系统从汇编入口 `_entry` 开始，为每个核心设置栈指针。
2.  `start` 函数在机器模式下初始化硬件状态，将大多数中断委托给监管者模式，并最终通过 `mret` 指令跳转到监管者模式的 `main` 函数。
3.  由于时钟中断无法委托，`timerinit` 函数在机器模式下对其进行特殊设置：初始化第一次中断时间，并准备好中断处理程序 `timervec` 所需的数据。
4.  当时钟中断发生时，机器模式下的 `timervec` 处理程序负责重置下一次中断时间，并通过触发一个监管者软件中断的方式，将控制权交还给内核进行真正的调度处理。

![](img/6feeb9aa16f9013c104ca27c22fe10cf_2.png)

这个设计巧妙地将必须在机器模式下处理的硬件定时器中断，与内核在监管者模式下进行的调度逻辑分离开来。