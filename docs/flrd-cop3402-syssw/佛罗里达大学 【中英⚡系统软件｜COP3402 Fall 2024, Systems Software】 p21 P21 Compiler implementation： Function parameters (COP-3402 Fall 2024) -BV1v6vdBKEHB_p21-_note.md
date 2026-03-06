# 系统软件：21：函数参数实现

![](img/ac4f7550dbb27f1025eb49558cd3136b_1.png)

![](img/ac4f7550dbb27f1025eb49558cd3136b_3.png)

![](img/ac4f7550dbb27f1025eb49558cd3136b_5.png)

在本节课中，我们将学习如何在汇编层面实现函数调用，特别是函数参数的传递机制。我们将基于System V ABI（应用程序二进制接口）的约定，详细讲解调用者（caller）和被调用者（callee）如何协作，通过寄存器和栈来传递参数。

上一节我们介绍了函数定义、序言（prologue）和尾声（epilogue）的基本结构。本节中，我们将重点探讨函数参数的传递规则。

## 概述：参数传递约定

在System V ABI（64位）中，函数参数通过寄存器和栈共同传递。具体规则如下：
*   前六个参数通过指定的寄存器传递。
*   第七个及之后的参数通过栈传递，并且按从右到左的顺序压入栈中。

以下是用于传递前六个参数的寄存器顺序：
```
RDI, RSI, RDX, RCX, R8, R9
```

![](img/ac4f7550dbb27f1025eb49558cd3136b_7.png)

## 栈帧回顾与参数位置

![](img/ac4f7550dbb27f1025eb49558cd3136b_9.png)

回忆一下函数调用时的栈帧布局。被调用函数的栈帧中，局部变量存储在基指针（RBP）的负偏移处，而传入的参数则存储在基指针（RBP）的正偏移处。

```
+-------------------+
| ...               | 高地址
+-------------------+
| 参数n (RBP+...)   | <-- 由调用者压入栈的参数
| ...               |
| 参数7 (RBP+16)    |
| 返回地址 (RBP+8)   |
| 旧的RBP (RBP)      | <-- 当前RBP指向这里
+-------------------+
| 局部变量1 (RBP-8)  |
| 局部变量2 (RBP-16) | <-- 被调用者分配的局部变量空间
| ...               |
+-------------------+
```

## 单个参数的传递示例

![](img/ac4f7550dbb27f1025eb49558cd3136b_11.png)

让我们通过一个简单的例子来理解整个过程。假设我们有一个函数 `param_test`，它接收一个参数，并将其赋值给局部变量 `x`，然后返回 `x`。

**Simple IR代码示例：**
```
function param_test
  local x
  local in_param : param
  x = in_param
  return x
end
```

一个调用该函数的 `main` 函数如下：
```
function main
  local ret_val
  local param
  param = 7
  ret_val = param_test(param)
end
```

### 调用者（main）的汇编代码

调用者 `main` 负责设置参数并调用函数。

![](img/ac4f7550dbb27f1025eb49558cd3136b_13.png)

以下是 `main` 函数中与调用相关的关键汇编代码片段：
```assembly
; ... 序言和局部变量分配代码 ...

; 1. 设置参数：将局部变量 `param` 的值（位于 RBP-32）加载到 RDI 寄存器
movq    -32(%rbp), %rdi

; 2. 调用函数
call    param_test

![](img/ac4f7550dbb27f1025eb49558cd3136b_15.png)

; 3. 调用后清理栈（此例中无栈传参，所以加0）
addq    $0, %rsp

![](img/ac4f7550dbb27f1025eb49558cd3136b_17.png)

; 4. 保存返回值：将 RAX 中的返回值存入局部变量 `ret_val`（位于 RBP-24）
movq    %rax, -24(%rbp)

; ... 尾声和返回代码 ...
```
**代码解释：**
*   `movq -32(%rbp), %rdi`: 根据约定，第一个参数放入 `RDI` 寄存器。这里我们将存储在栈偏移 `-32` 处的 `param` 变量的值复制到 `RDI`。
*   `call param_test`: 执行调用指令，它会将返回地址压栈并跳转到 `param_test`。
*   `addq $0, %rsp`: 如果通过栈传递了参数，调用后需要调整栈指针 `RSP` 来“弹出”这些参数。本例中没有，所以加0。
*   `movq %rax, -24(%rbp)`: 根据约定，函数的返回值存储在 `RAX` 寄存器中。调用返回后，我们将 `RAX` 的值保存到局部变量 `ret_val` 中。

![](img/ac4f7550dbb27f1025eb49558cd3136b_19.png)

### 被调用者（param_test）的汇编代码

被调用者 `param_test` 负责从约定位置获取参数，执行操作，并设置返回值。

以下是 `param_test` 函数的关键汇编代码片段：
```assembly
param_test:
    ; ... 序言代码 ...

    ; 为局部变量分配栈空间（此例中为16字节对齐后的24字节）
    subq    $24, %rsp

    ; 1. 获取参数：将第一个参数（在RDI中）保存到局部变量 `in_param`（位于RBP-16）
    movq    %rdi, -16(%rbp)

    ; 2. 执行赋值：将 `in_param` 的值赋给局部变量 `x`（位于RBP-8）
    movq    -16(%rbp), %rax
    movq    %rax, -8(%rbp)

    ; 3. 设置返回值：将 `x` 的值（位于RBP-8）放入 RAX 寄存器
    movq    -8(%rbp), %rax

    ; ... 尾声代码 ...
    ret
```
**代码解释：**
*   `movq %rdi, -16(%rbp)`: 函数开始执行后，首先从约定好的 `RDI` 寄存器中取出调用者传递的第一个参数值，并将其存储到为参数 `in_param` 预留的栈空间（`RBP-16`）中。这是一种简单的实现策略，将所有参数都转存到栈上的局部变量空间，简化了编译器的寄存器分配管理。
*   中间的赋值操作 `x = in_param` 通过通用寄存器 `RAX` 作为中转实现。
*   `movq -8(%rbp), %rax`: 在返回前，根据约定，需要将返回值放入 `RAX` 寄存器。这里我们把局部变量 `x` 的值存入 `RAX`。

## 多个参数的传递示例

![](img/ac4f7550dbb27f1025eb49558cd3136b_21.png)

![](img/ac4f7550dbb27f1025eb49558cd3136b_23.png)

![](img/ac4f7550dbb27f1025eb49558cd3136b_25.png)

当参数超过6个时，超出的部分需要通过栈来传递。考虑一个接收8个参数的函数 `param_test8`。

![](img/ac4f7550dbb27f1025eb49558cd3136b_27.png)

![](img/ac4f7550dbb27f1025eb49558cd3136b_29.png)

![](img/ac4f7550dbb27f1025eb49558cd3136b_31.png)

![](img/ac4f7550dbb27f1025eb49558cd3136b_33.png)

![](img/ac4f7550dbb27f1025eb49558cd3136b_35.png)

**Simple IR代码示例：**
```
function param_test8
  local x
  local a : param
  local b : param
  local c : param
  local d : param
  local e : param
  local f : param
  local g : param
  local h : param
  x = c
  return x
end
```

![](img/ac4f7550dbb27f1025eb49558cd3136b_37.png)

![](img/ac4f7550dbb27f1025eb49558cd3136b_38.png)

![](img/ac4f7550dbb27f1025eb49558cd3136b_40.png)

![](img/ac4f7550dbb27f1025eb49558cd3136b_42.png)

![](img/ac4f7550dbb27f1025eb49558cd3136b_43.png)

### 调用者设置多个参数

![](img/ac4f7550dbb27f1025eb49558cd3136b_45.png)

![](img/ac4f7550dbb27f1025eb49558cd3136b_47.png)

调用者需要按规则设置前6个寄存器，并将第7、8个参数压栈。

![](img/ac4f7550dbb27f1025eb49558cd3136b_49.png)

![](img/ac4f7550dbb27f1025eb49558cd3136b_50.png)

以下是调用 `param_test8` 的关键汇编代码片段：
```assembly
; 设置前6个参数到寄存器
movq    -32(%rbp), %rdi  ; 参数 a -> RDI
movq    -40(%rbp), %rsi  ; 参数 b -> RSI
movq    -48(%rbp), %rdx  ; 参数 c -> RDX
movq    -56(%rbp), %rcx  ; 参数 d -> RCX
movq    -64(%rbp), %r8   ; 参数 e -> R8
movq    -72(%rbp), %r9   ; 参数 f -> R9

; 将第7、8个参数压栈（注意顺序：先压h，再压g）
pushq   -88(%rbp)        ; 参数 h
pushq   -80(%rbp)        ; 参数 g

![](img/ac4f7550dbb27f1025eb49558cd3136b_52.png)

; 调用函数
call    param_test8

![](img/ac4f7550dbb27f1025eb49558cd3136b_54.png)

![](img/ac4f7550dbb27f1025eb49558cd3136b_56.png)

; 调用后清理栈：弹出两个8字节参数
addq    $16, %rsp

![](img/ac4f7550dbb27f1025eb49558cd3136b_58.png)

![](img/ac4f7550dbb27f1025eb49558cd3136b_60.png)

; 保存返回值
movq    %rax, -24(%rbp)
```
**关键点：**
*   寄存器参数按固定顺序 (`RDI`, `RSI`, `RDX`, `RCX`, `R8`, `R9`) 设置。
*   栈传参时，参数按**从右向左**的顺序压栈。即最后一个参数 `h` 先压栈，然后才是 `g`。
*   函数返回后，使用 `addq $16, %rsp` 将栈指针上移16字节，相当于弹出了刚才压入的两个参数，恢复了栈的平衡。

### 被调用者获取多个参数

![](img/ac4f7550dbb27f1025eb49558cd3136b_62.png)

![](img/ac4f7550dbb27f1025eb49558cd3136b_64.png)

被调用者需要从寄存器以及栈上的正确位置获取所有参数。

![](img/ac4f7550dbb27f1025eb49558cd3136b_66.png)

以下是 `param_test8` 函数获取参数的关键汇编代码片段：
```assembly
param_test8:
    ; ... 序言和局部空间分配 ...

    ; 获取前6个寄存器中的参数
    movq    %rdi, -8(%rbp)   ; a
    movq    %rsi, -16(%rbp)  ; b
    movq    %rdx, -24(%rbp)  ; c
    movq    %rcx, -32(%rbp)  ; d
    movq    %r8,  -40(%rbp)  ; e
    movq    %r9,  -48(%rbp)  ; f

    ; 获取栈上的第7个参数 (g)
    movq    16(%rbp), %rax   ; 参数 g 在 RBP+16
    movq    %rax, -56(%rbp)

    ; 获取栈上的第8个参数 (h)
    movq    24(%rbp), %rax   ; 参数 h 在 RBP+24
    movq    %rax, -64(%rbp)

    ; ... 函数主体和返回 ...
```
**关键点：**
*   寄存器中的参数被复制到栈帧中对应的局部变量位置（负偏移）。
*   栈上传入的参数位于**正偏移**处。因为 `call` 指令压入了返回地址（`RBP+8`），所以第一个栈参数从 `RBP+16` 开始，第二个从 `RBP+24` 开始，以此类推。

## 总结

本节课中我们一起学习了函数参数传递的完整实现机制。

1.  **调用者（Caller）的职责**：
    *   将前6个参数放入指定的寄存器：`RDI`, `RSI`, `RDX`, `RCX`, `R8`, `R9`。
    *   将第7个及之后的参数按**从右向左**的顺序压入栈中。
    *   使用 `call` 指令调用函数。
    *   函数返回后，调整栈指针 `RSP` 以清理通过栈传递的参数。
    *   从 `RAX` 寄存器中获取函数的返回值。

2.  **被调用者（Callee）的职责**：
    *   在序言中建立自己的栈帧。
    *   从约定的寄存器（`RDI`等）和栈位置（`RBP+16`等）获取传入的参数值，通常将它们保存到为本地区量分配的栈空间中。
    *   将返回值存入 `RAX` 寄存器。
    *   在尾声恢复栈帧并执行 `ret` 指令返回。

![](img/ac4f7550dbb27f1025eb49558cd3136b_68.png)

理解并遵循这套ABI约定，是确保不同模块（甚至是用不同语言编写的模块）能够正确互操作的关键。这也为你的编译器生成能与C语言程序链接的代码奠定了基础。