# 23：自动化上下文切换

![](img/3ff95a2c2e3cf093be36d09f2459737c_0.png)

在本节课中，我们将学习如何自动化上下文切换过程，这是构建实时操作系统（RTOS）的核心步骤。我们将基于上一课手动推导的算法，开始构建一个名为“Miro”的极简RTOS内核。

![](img/3ff95a2c2e3cf093be36d09f2459737c_2.png)

![](img/3ff95a2c2e3cf093be36d09f2459737c_4.png)

![](img/3ff95a2c2e3cf093be36d09f2459737c_6.png)

## 概述

![](img/3ff95a2c2e3cf093be36d09f2459737c_8.png)

![](img/3ff95a2c2e3cf093be36d09f2459737c_10.png)

在上一课中，我们探讨了RTOS的核心思想：通过频繁地在多个后台循环（线程）之间切换CPU，来模拟并发执行。我们手动推导了上下文切换的算法。本节课的目标是将这个算法转化为实际的、可自动执行的代码。

## 创建Miro RTOS项目

首先，我们需要为我们的RTOS创建一个独立的项目结构。

以下是创建步骤：
1.  复制上一课的目录并重命名为“lesson23”。
2.  在新目录中打开Microvision项目。
3.  添加一个名为“Miro”的新项目组。
4.  在该组中创建两个文件：`miro.h`（头文件，包含API）和`miro.c`（源文件，包含实现）。

在`miro.h`文件中，我们首先定义线程控制块（TCB）数据结构，用于表示一个线程。

```c
typedef struct OS_thread {
    void *sp; // 私有栈指针
    // ... 未来可扩展其他成员
} OS_thread;
```

![](img/3ff95a2c2e3cf093be36d09f2459737c_12.png)

![](img/3ff95a2c2e3cf093be36d09f2459737c_14.png)

## 实现线程启动函数

接下来，我们需要一个函数来初始化线程栈，为线程的首次执行准备好寄存器上下文。

以下是线程启动函数 `OS_thread_start` 的实现要点：
*   **函数签名**：接收TCB指针、线程处理函数指针、栈内存地址和大小。
*   **栈对齐**：确保栈指针按ARM Cortex-M要求的8字节边界对齐。
*   **构建栈帧**：在栈上按正确顺序放置初始寄存器值，包括程序计数器（PC）指向线程函数。
*   **栈预填充**：用特定模式（如`0xDEADBEEF`）填充剩余栈空间，便于调试时观察栈使用情况。

![](img/3ff95a2c2e3cf093be36d09f2459737c_16.png)

![](img/3ff95a2c2e3cf093be36d09f2459737c_18.png)

```c
void OS_thread_start(OS_thread *me,
                     OS_thread_handler thread_handler,
                     void *stack_sto,
                     uint32_t stack_size);
```

![](img/3ff95a2c2e3cf093be36d09f2459737c_20.png)

## 利用PendSV异常进行上下文切换

![](img/3ff95a2c2e3cf093be36d09f2459737c_22.png)

上下文切换需要在中断返回时进行。为了避免在每个中断服务程序（ISR）中重复编写切换代码，我们利用ARM Cortex-M的一个专用异常：**PendSV**。

其工作原理如下：
1.  在需要切换上下文时（例如，在SysTick中断的调度器中），我们通过设置系统控制块（SCB）中的`ICSR`寄存器的位28来**触发**PendSV异常。
2.  PendSV异常被设置为**最低优先级**，确保它不会抢占其他中断，只会在当前中断处理完毕后才执行。
3.  在PendSV异常处理程序中，我们执行实际的上下文切换汇编代码。

我们需要在系统初始化时设置PendSV的优先级为最低。

```c
// 在 miro.c 的 OS_init() 函数中
#define NVIC_SYSPRI14 (*((volatile uint32_t *)0xE000ED20))
#define NVIC_PENDSV_PRI (0xFF) // 最低优先级
NVIC_SYSPRI14 = (NVIC_SYSPRI14 & 0x00FFFFFF) | (NVIC_PENDSV_PRI << 16);
```

## 实现调度器与触发切换

现在，我们来实现触发上下文切换的调度器函数 `OS_sched`。

![](img/3ff95a2c2e3cf093be36d09f2459737c_24.png)

![](img/3ff95a2c2e3cf093be36d09f2459737c_26.png)

以下是调度器 `OS_sched` 的核心逻辑：
*   **线程指针**：维护两个全局的`volatile`指针：`OS_curr`（指向当前运行线程）和`OS_next`（指向下一个要运行的线程）。
*   **触发条件**：当`OS_next`与`OS_curr`不同时，才触发PendSV异常。
*   **临界区保护**：对`OS_curr`和`OS_next`的访问必须在**禁用中断**的临界区内进行，以防止竞态条件。

```c
void OS_sched(void) {
    if (OS_next != OS_curr) {
        // 触发 PendSV 异常
        *((volatile uint32_t *)0xE000ED04) = (1 << 28);
    }
}
// 在 SysTick 中断中调用
void SysTick_Handler(void) {
    __disable_irq(); // 进入临界区
    OS_sched();
    __enable_irq();  // 退出临界区
}
```

## 编写PendSV处理程序（汇编）

最后，也是最关键的一步，是在PendSV异常处理程序中用汇编语言实现上下文切换。

上下文切换的步骤在PendSV处理程序中完成，其汇编逻辑如下：
1.  **判断**：检查`OS_curr`是否为NULL（首次切换时）。
2.  **保存上下文**：如果`OS_curr`非NULL，将寄存器R4-R11压入**当前线程**的栈中，然后更新其TCB中的栈指针（`sp`成员）。
3.  **恢复上下文**：将`OS_next`线程TCB中的栈指针加载到CPU的SP寄存器，并更新`OS_curr`指针。
4.  **加载上下文**：从**新线程**的栈中弹出寄存器R4-R11。
5.  **返回**：启用中断并执行异常返回，CPU将自动从新线程的栈中加载剩余的寄存器（包括PC），从而跳转到新线程继续执行。

```assembly
__asm void PendSV_Handler(void) {
    CPSID I                 // 禁用中断
    LDR R1, =OS_curr        // 加载 OS_curr 地址
    LDR R1, [R1]            // 加载 OS_curr 值
    CBZ R1, PendSV_restore  // 如果为0（首次），跳转到恢复部分
    // 保存当前线程上下文
    PUSH {R4-R11}           // 将R4-R11压入当前栈
    LDR R0, =OS_curr
    LDR R0, [R0]
    STR SP, [R0]            // 保存SP到 OS_curr->sp
PendSV_restore:
    // 恢复下一个线程上下文
    LDR R1, =OS_next
    LDR R1, [R1]            // R1 = OS_next
    LDR R0, [R1]            // R0 = OS_next->sp
    MOV SP, R0              // SP = OS_next->sp
    LDR R0, =OS_curr
    STR R1, [R0]            // OS_curr = OS_next
    // 加载新线程上下文
    POP {R4-R11}            // 从新栈弹出R4-R11
    CPSIE I                 // 启用中断
    BX LR                   // 异常返回，切换到新线程
}
```

## 测试与调试

完成编码后，我们在调试器中测试整个流程：手动设置`OS_next`指针来调度不同的线程，单步执行PendSV汇编代码，观察栈内容的变化和寄存器的保存/恢复，最终验证两个LED线程能够被成功切换并运行。

在首次测试中，我们遇到了一个Bug：线程启动函数中错误地对函数指针再次取址，导致栈上的PC值错误。修复后，上下文切换成功执行。

![](img/3ff95a2c2e3cf093be36d09f2459737c_28.png)

## 总结

本节课中，我们一起学习了如何自动化RTOS的上下文切换。我们构建了Miro RTOS的雏形，包括：
1.  定义了线程控制块（TCB）。
2.  实现了线程栈初始化函数（`OS_thread_start`）。
3.  利用**PendSV**异常作为上下文切换的专用入口。
4.  实现了调度器函数（`OS_sched`）来触发切换。
5.  用**汇编语言**编写了PendSV处理程序，完成了保存和恢复线程上下文的核心操作。

目前，调度（决定`OS_next`是谁）仍是手动的。在下一课中，我们将实现**轮转调度**策略，让我们的RTOS能够自动在多个线程之间进行时间片轮转，从而形成一个完整的、自动化的多任务系统。