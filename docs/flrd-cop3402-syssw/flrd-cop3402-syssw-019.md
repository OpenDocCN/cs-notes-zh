# 019：编译器实现 - 函数实现 🛠️

![](img/ddbc8774efa72a0058f10611c2f0b711_1.png)

![](img/ddbc8774efa72a0058f10611c2f0b711_3.png)

![](img/ddbc8774efa72a0058f10611c2f0b711_4.png)

![](img/ddbc8774efa72a0058f10611c2f0b711_6.png)

![](img/ddbc8774efa72a0058f10611c2f0b711_8.png)

在本节课中，我们将学习如何在编译器层面实现函数。我们将探讨函数调用的底层机制，特别是栈帧的构建与销毁，以及如何生成遵循特定调用约定的汇编代码。

---

![](img/ddbc8774efa72a0058f10611c2f0b711_10.png)

![](img/ddbc8774efa72a0058f10611c2f0b711_12.png)

![](img/ddbc8774efa72a0058f10611c2f0b711_13.png)

![](img/ddbc8774efa72a0058f10611c2f0b711_15.png)

![](img/ddbc8774efa72a0058f10611c2f0b711_17.png)

![](img/ddbc8774efa72a0058f10611c2f0b711_19.png)

![](img/ddbc8774efa72a0058f10611c2f0b711_21.png)

## 函数语义回顾

上一节我们介绍了函数在指令级别的模拟。本节中，我们来看看如何编写一个编译器，使其能生成实现我们期望函数行为的汇编代码。

每个函数调用都拥有自己独立的栈帧。这是实现递归和多次函数调用的关键。在C语言中，每次函数调用都会获得该函数的一份新的局部状态。

## 调用约定与应用程序二进制接口

为了实现函数的局部状态，我们需要在汇编层面遵循一套标准。这套标准被称为**调用约定**或**应用程序二进制接口**。它规定了栈帧的布局、参数传递方式、返回值存放位置以及寄存器的保存责任。

调用约定是系统相关的。例如，在x86-64架构的System V ABI（Linux等系统使用）中，前六个整型参数通过寄存器传递，其余参数通过栈传递。

![](img/ddbc8774efa72a0058f10611c2f0b711_23.png)

以下是System V x86-64 ABI的关键点：
*   **参数寄存器**：`%rdi`, `%rsi`, `%rdx`, `%rcx`, `%r8`, `%r9`
*   **返回值寄存器**：`%rax`
*   **栈指针寄存器**：`%rsp`
*   **基指针寄存器**：`%rbp`
*   **被调用者保存的寄存器**：例如 `%rbx`, `%r12-%r15`（被调用函数必须在使用前保存其值，并在返回前恢复）

![](img/ddbc8774efa72a0058f10611c2f0b711_25.png)

![](img/ddbc8774efa72a0058f10611c2f0b711_27.png)

## 栈帧布局详解

![](img/ddbc8774efa72a0058f10611c2f0b711_29.png)

理解栈帧的构建是理解函数实现的核心。栈帧的构建是调用者（caller）和被调用者（callee）协作完成的。

以下是调用一个函数 `my_func(a, b, c, d, e, f, g, h)` 时，栈帧的构建过程示意图：

```
高地址
+-------------------+
| 调用者的栈帧       | <--- %rbp (调用前)
+-------------------+
| 参数 h             | <--- 由调用者压栈
+-------------------+
| 参数 g             | <--- 由调用者压栈
+-------------------+
| 返回地址           | <--- `call` 指令自动压栈
+-------------------+
| 旧的 %rbp          | <--- 被调用者 prologue 压栈
+-------------------+
| 被调用者保存的寄存器| <--- 例如 push %rbx
+-------------------+
| 局部变量           |
| ...               |
+-------------------+
|                   | <--- %rsp (函数执行中)
低地址
```

![](img/ddbc8774efa72a0058f10611c2f0b711_31.png)

![](img/ddbc8774efa72a0058f10611c2f0b711_32.png)

![](img/ddbc8774efa72a0058f10611c2f0b711_34.png)

![](img/ddbc8774efa72a0058f10611c2f0b711_36.png)

**构建过程分解：**

![](img/ddbc8774efa72a0058f10611c2f0b711_38.png)

![](img/ddbc8774efa72a0058f10611c2f0b711_40.png)

![](img/ddbc8774efa72a0058f10611c2f0b711_41.png)

![](img/ddbc8774efa72a0058f10611c2f0b711_43.png)

![](img/ddbc8774efa72a0058f10611c2f0b711_45.png)

![](img/ddbc8774efa72a0058f10611c2f0b711_47.png)

1.  **调用者（绿色部分）**：
    *   将前六个参数（a-f）放入指定的寄存器。
    *   将剩余参数（g, h）压入栈中（`%rsp` 递减）。
    *   执行 `call my_func` 指令。该指令将下一条指令的地址（返回地址）压栈，然后跳转到 `my_func` 的代码。

2.  **被调用者 Prologue（蓝色部分）**：
    *   `push %rbp`：将调用者的基指针保存到栈上。
    *   `mov %rsp, %rbp`：将当前栈指针设置为新的基指针，从而建立当前函数的栈帧基准。
    *   `push %rbx`（可选）：保存需要被调用者保护的寄存器。

![](img/ddbc8774efa72a0058f10611c2f0b711_49.png)

![](img/ddbc8774efa72a0058f10611c2f0b711_51.png)

![](img/ddbc8774efa72a0058f10611c2f0b711_53.png)

![](img/ddbc8774efa72a0058f10611c2f0b711_55.png)

![](img/ddbc8774efa72a0058f10611c2f0b711_57.png)

![](img/ddbc8774efa72a0058f10611c2f0b711_59.png)

3.  **被调用者 Epilogue（函数返回前）**：
    *   `mov %rbp, %rsp`：将栈指针恢复为基指针的值，从而“弹出”所有局部变量。
    *   `pop %rbp`：恢复调用者的基指针。
    *   `ret`：从栈中弹出返回地址，并跳转回去。返回值应已存放在 `%rax` 寄存器中。

**关键点**：
*   编译器在编译时就知道每个局部变量和参数相对于 `%rbp` 的偏移量，因此可以生成形如 `movl $42, -8(%rbp)` 的指令来访问变量 `xx`。
*   `%rbp` 链（每个栈帧保存的上一个 `%rbp`）使得在调试时回溯调用栈成为可能。

![](img/ddbc8774efa72a0058f10611c2f0b711_61.png)

![](img/ddbc8774efa72a0058f10611c2f0b711_63.png)

![](img/ddbc8774efa72a0058f10611c2f0b711_65.png)

## 汇编代码生成实例

![](img/ddbc8774efa72a0058f10611c2f0b711_67.png)

现在，我们来看一个完整的、由编译器生成的简单汇编程序示例。它包含一个 `main` 函数和一个 `func` 函数，`main` 调用 `func`。

![](img/ddbc8774efa72a0058f10611c2f0b711_69.png)

![](img/ddbc8774efa72a0058f10611c2f0b711_71.png)

![](img/ddbc8774efa72a0058f10611c2f0b711_73.png)

![](img/ddbc8774efa72a0058f10611c2f0b711_75.png)

![](img/ddbc8774efa72a0058f10611c2f0b711_77.png)

![](img/ddbc8774efa72a0058f10611c2f0b711_79.png)

以下是编译器需要为每个函数生成的核心汇编结构：

![](img/ddbc8774efa72a0058f10611c2f0b711_81.png)

![](img/ddbc8774efa72a0058f10611c2f0b711_82.png)

![](img/ddbc8774efa72a0058f10611c2f0b711_84.png)

![](img/ddbc8774efa72a0058f10611c2f0b711_86.png)

![](img/ddbc8774efa72a0058f10611c2f0b711_88.png)

![](img/ddbc8774efa72a0058f10611c2f0b711_90.png)

![](img/ddbc8774efa72a0058f10611c2f0b711_92.png)

![](img/ddbc8774efa72a0058f10611c2f0b711_94.png)

![](img/ddbc8774efa72a0058f10611c2f0b711_96.png)

```assembly
    .text
    .globl main
    .type main, @function
main:
    # Prologue
    push %rbp
    mov %rsp, %rbp
    push %rbx

    # 函数体：调用 func
    call func

    # Epilogue
    mov %rbp, %rsp
    pop %rbp
    ret

    .globl func
    .type func, @function
func:
    # Prologue
    push %rbp
    mov %rsp, %rbp
    push %rbx

    # 函数体：返回常量 5
    mov $5, %rax

    # Epilogue
    mov %rbp, %rsp
    pop %rbp
    ret
```

![](img/ddbc8774efa72a0058f10611c2f0b711_98.png)

![](img/ddbc8774efa72a0058f10611c2f0b711_100.png)

![](img/ddbc8774efa72a0058f10611c2f0b711_102.png)

![](img/ddbc8774efa72a0058f10611c2f0b711_104.png)

**代码解释**：
*   `.text` 等以点开头的指令是汇编器伪指令，用于定义节区和元数据。
*   `main:` 和 `func:` 是标签，代表函数的入口地址。
*   **Prologue** 和 **Epilogue** 的代码对于每个函数都是固定的模板（在没有局部变量和参数的情况下）。
*   `call func` 生成函数调用。
*   `mov $5, %rax` 对应 `return 5;` 语句，将返回值放入 `%rax`。

![](img/ddbc8774efa72a0058f10611c2f0b711_106.png)

![](img/ddbc8774efa72a0058f10611c2f0b711_108.png)

![](img/ddbc8774efa72a0058f10611c2f0b711_110.png)

![](img/ddbc8774efa72a0058f10611c2f0b711_112.png)

## 编译器项目实践

![](img/ddbc8774efa72a0058f10611c2f0b711_114.png)

![](img/ddbc8774efa72a0058f10611c2f0b711_116.png)

![](img/ddbc8774efa72a0058f10611c2f0b711_118.png)

在本节的配套项目中，你需要实现一个简单的代码生成器。你只需要处理函数定义、函数调用和返回常量值。

![](img/ddbc8774efa72a0058f10611c2f0b711_120.png)

![](img/ddbc8774efa72a0058f10611c2f0b711_122.png)

![](img/ddbc8774efa72a0058f10611c2f0b711_124.png)

![](img/ddbc8774efa72a0058f10611c2f0b711_126.png)

![](img/ddbc8774efa72a0058f10611c2f0b711_128.png)

![](img/ddbc8774efa72a0058f10611c2f0b711_130.png)

你需要实现四个核心函数来生成对应的汇编代码片段：

![](img/ddbc8774efa72a0058f10611c2f0b711_132.png)

![](img/ddbc8774efa72a0058f10611c2f0b711_134.png)

![](img/ddbc8774efa72a0058f10611c2f0b711_136.png)

![](img/ddbc8774efa72a0058f10611c2f0b711_138.png)

![](img/ddbc8774efa72a0058f10611c2f0b711_140.png)

![](img/ddbc8774efa72a0058f10611c2f0b711_142.png)

![](img/ddbc8774efa72a0058f10611c2f0b711_144.png)

![](img/ddbc8774efa72a0058f10611c2f0b711_145.png)

![](img/ddbc8774efa72a0058f10611c2f0b711_147.png)

![](img/ddbc8774efa72a0058f10611c2f0b711_149.png)

1.  `enter_unit`: 生成汇编文件开头（已提供）。
2.  `enter_function`: 生成函数标签和 prologue。
3.  `enter_call`: 生成 `call` 指令。
4.  `enter_return`: 生成 `mov $<value>, %rax` 指令。
5.  `exit_function`: 生成 epilogue。

![](img/ddbc8774efa72a0058f10611c2f0b711_151.png)

![](img/ddbc8774efa72a0058f10611c2f0b711_153.png)

![](img/ddbc8774efa72a0058f10611c2f0b711_155.png)

![](img/ddbc8774efa72a0058f10611c2f0b711_157.png)

**实现思路**：
你的编译器本质上是一个**文本生成器**。它遍历抽象语法树（AST），并在特定节点触发上述函数，将对应的汇编文本字符串写入输出文件。例如，在 `enter_function` 中，你需要根据 AST 节点中的函数名，生成 `push %rbp\nmov %rsp, %rbp\npush %rbx` 这样的字符串。

![](img/ddbc8774efa72a0058f10611c2f0b711_159.png)

![](img/ddbc8774efa72a0058f10611c2f0b711_161.png)

![](img/ddbc8774efa72a0058f10611c2f0b711_163.png)

![](img/ddbc8774efa72a0058f10611c2f0b711_165.png)

![](img/ddbc8774efa72a0058f10611c2f0b711_167.png)

![](img/ddbc8774efa72a0058f10611c2f0b711_169.png)

![](img/ddbc8774efa72a0058f10611c2f0b711_171.png)

---

![](img/ddbc8774efa72a0058f10611c2f0b711_173.png)

![](img/ddbc8774efa72a0058f10611c2f0b711_175.png)

![](img/ddbc8774efa72a0058f10611c2f0b711_177.png)

![](img/ddbc8774efa72a0058f10611c2f0b711_179.png)

![](img/ddbc8774efa72a0058f10611c2f0b711_181.png)

![](img/ddbc8774efa72a0058f10611c2f0b711_183.png)

![](img/ddbc8774efa72a0058f10611c2f0b711_185.png)

![](img/ddbc8774efa72a0058f10611c2f0b711_187.png)

![](img/ddbc8774efa72a0058f10611c2f0b711_189.png)

本节课中我们一起学习了函数在编译器层面的实现机制。我们深入探讨了调用约定、栈帧的构建与销毁过程，并了解了如何生成正确的 x86-64 汇编代码来实现函数调用。理解这些概念是编写能够处理函数和递归的编译器的关键基础。