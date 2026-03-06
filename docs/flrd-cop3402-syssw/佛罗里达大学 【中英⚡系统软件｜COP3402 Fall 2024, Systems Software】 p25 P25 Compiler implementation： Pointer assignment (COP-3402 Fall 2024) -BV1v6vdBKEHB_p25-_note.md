# 系统软件：P25：编译器实现 - 指针赋值 (COP-3402 Fall 2024)

![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_0.png)

![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_2.png)

![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_4.png)

![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_6.png)

![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_8.png)

![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_0.png)

![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_10.png)

![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_12.png)

欢迎回到系统软件课程。今天是课程主要内容的最后一讲，我们将完成编译器的实现，并讲解如何实现指针，以及如何编译使用指针的代码。

![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_14.png)

![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_16.png)

![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_2.png)

![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_18.png)

## 概述

在本节课中，我们将要学习如何为指针操作生成汇编代码。我们将重点讲解指针赋值（`*ptr = value`）的实现，这是指针操作中最核心的部分之一。我们将从复习指针的基本操作开始，然后深入探讨如何将高级语言中的指针赋值语句转换为底层的x86-64汇编指令。

上一节我们介绍了指针的引用（`&`）和解引用（`*`）操作在中间表示（IR）中的语义。本节中我们来看看如何将这些IR操作，特别是解引用赋值，翻译成具体的汇编代码。

## 复习：指针操作与简单IR

![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_4.png)

![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_20.png)

指针操作在简单IR中与C语言非常相似，主要包括三种操作：
*   **引用**：获取变量的地址，例如 `t1 = &x`。
*   **解引用**：获取指针指向的值，例如 `t2 = *t1`。
*   **解引用赋值**：向指针指向的地址写入值，例如 `*t1 = 11`。

这些操作的语义与C语言一致。

![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_6.png)

关于这些IR操作的语义有任何问题吗？我想大家已经在C语言中见过这些操作了，它们的语义是相同的。

关于栈帧和RBP寄存器：RBP是一个寄存器，它总是指向当前函数的栈帧起始地址。这是一个由编译器维护的不变量。只要调用约定被正确实现，RBP寄存器在任何时候都持有指向栈帧的指针。因此，在生成代码时，我们可以始终依赖RBP来定位栈帧中的变量。

![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_22.png)

![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_24.png)

![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_26.png)

关于数据类型：在简单IR和汇编层面，我们主要处理64位整数。字符和字符串本质上也是数字（字符是8位数字，字符串是字符数组）。机器层面没有内置的类型表示，类型是编程语言创造的概念。指令决定了如何解释寄存器或内存中的二进制数据（是作为地址、整数还是其他）。

![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_28.png)

![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_30.png)

关于调用C函数：由于我们遵循System V应用二进制接口（ABI），我们可以调用C函数（如`malloc`）并获取其返回值。`malloc`返回一个指针，我们可以像操作其他数字一样对这个指针进行加减运算。不过，由于数据类型宽度的差异，与C库的完全互操作可能会遇到一些问题。

![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_32.png)

![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_34.png)

## 计算变量的地址

![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_18.png)

让我们通过一个具体例子来理解如何访问变量及其地址。假设我们有一个栈帧，变量`x`的偏移量是`-24`（相对于RBP）。RBP寄存器的值是`80`（指向栈帧顶部）。

![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_20.png)

以下汇编指令的作用是访问变量`x`的值：
```assembly
mov RAX, [RBP - 24]
```
这条指令的意思是：取RBP的值（80），减去24得到地址56，然后将内存地址56处存储的值加载到RAX寄存器中。这是一种间接加载操作。

那么，如何获取变量`x`的地址（即56）并将其存储到寄存器（例如RAX）中呢？我们需要的不是加载地址56处的值，而是计算地址56本身。

方法是直接计算RBP加上偏移量：
```assembly
mov RAX, RBP
add RAX, -24
```
或者更简洁地：
```assembly
lea RAX, [RBP - 24]
```
执行后，RAX寄存器将保存地址值56。这就是我们实现引用操作（`&x`）的方式：生成计算变量地址的代码，并将该地址存入目标变量（如`t1`）对应的栈槽中。

**核心概念**：获取变量地址的公式为 `变量地址 = RBP + 变量偏移量`。

![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_36.png)

![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_38.png)

## 实现解引用操作

![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_40.png)

解引用操作（`t2 = *t1`）是加载指针指向的值。

![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_30.png)

![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_42.png)

假设`t1`中存储着地址56（即指向变量`x`）。实现解引用的汇编代码如下：
1.  首先，将`t1`的值（地址）加载到寄存器（如RAX）。
    ```assembly
    mov RAX, [RBP - 40] # 假设t1的偏移是-40
    ```
    RAX现在等于56。
2.  然后，使用括号语法进行间接加载，将RAX所指向地址的值存入另一个寄存器（如RBX）。
    ```assembly
    mov RBX, [RAX]
    ```
    这条指令会去访问内存地址56，将其存储的值（假设是8）加载到RBX中。
3.  最后，将RBX中的值存储到`t2`对应的栈槽中。
    ```assembly
    mov [RBP - 48], RBX # 假设t2的偏移是-48
    ```

![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_44.png)

**核心概念**：解引用加载的汇编模式为 `mov 目标寄存器, [地址寄存器]`。

## 实现解引用赋值操作

本节的核心是解引用赋值操作（`*t1 = 11` 或 `*t1 = t2`），即向指针指向的内存地址写入数据。

![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_46.png)

![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_48.png)

![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_42.png)

![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_50.png)

这个操作与解引用加载相反。我们不是从地址加载值，而是向地址存储值。语义是：取`t1`的值作为一个地址，然后将右侧的值存入该地址。

![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_46.png)

以下是实现 `*t1 = 11` 的汇编步骤：
1.  将`t1`的值（地址）加载到RAX。
    ```assembly
    mov RAX, [RBP - 40]
    ```
2.  将右侧的立即数（11）加载到RBX。
    ```assembly
    mov RBX, 11
    ```
3.  使用间接存储，将RBX的值存入RAX所指向的地址。
    ```assembly
    mov [RAX], RBX
    ```
    执行后，内存地址56处的值被更新为11。

如果右侧是一个变量，例如 `*t1 = t2`，步骤类似：
1.  将`t1`的值（地址）加载到RAX。
    ```assembly
    mov RAX, [RBP - 40]
    ```
2.  将`t2`的值加载到RBX。
    ```assembly
    mov RBX, [RBP - 48]
    ```
3.  进行间接存储。
    ```assembly
    mov [RAX], RBX
    ```

**核心概念**：解引用赋值的汇编模式为 `mov [地址寄存器], 源操作数`。这里的括号`[ ]`在汇编中就是解引用操作。

## 完整示例与状态变化

让我们通过一个完整的简单IR程序，跟踪其执行过程中栈帧和寄存器的状态变化。

考虑以下IR代码：
```
x = 8
y = 9
t1 = &x
t2 = *t1
*t1 = 11
t3 = x
```

假设栈帧起始地址（RBP）为80，变量偏移量为：x: -24, y: -32, t1: -40, t2: -48, t3: -56。

以下是编译器生成的可能汇编代码及状态分析：

![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_52.png)

![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_54.png)

1.  `x = 8`
    ```assembly
    mov RAX, 8
    mov [RBP - 24], RAX
    ```
    *   状态：地址56（80-24）的值变为8。

![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_56.png)

![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_58.png)

![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_60.png)

![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_62.png)

2.  `y = 9`
    ```assembly
    mov RAX, 9
    mov [RBP - 32], RAX
    ```
    *   状态：地址48（80-32）的值变为9。

![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_64.png)

![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_65.png)

3.  `t1 = &x`
    ```assembly
    mov RAX, RBP
    add RAX, -24        ; RAX = 80 - 24 = 56
    mov [RBP - 40], RAX
    ```
    *   状态：地址40（80-40）的值变为56（x的地址）。

![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_67.png)

![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_69.png)

![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_71.png)

4.  `t2 = *t1`
    ```assembly
    mov RAX, [RBP - 40] ; RAX = 56
    mov RBX, [RAX]      ; RBX = [56] = 8
    mov [RBP - 48], RBX
    ```
    *   状态：地址32（80-48）的值变为8。

![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_73.png)

![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_75.png)

5.  `*t1 = 11`
    ```assembly
    mov RAX, [RBP - 40] ; RAX = 56
    mov RBX, 11
    mov [RAX], RBX      ; [56] = 11
    ```
    *   **关键状态变化**：地址56（x）的值从8变为11。注意，`t1`本身（地址40）存储的地址56并没有改变。

![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_77.png)

![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_79.png)

![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_81.png)

![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_83.png)

![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_85.png)

![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_87.png)

6.  `t3 = x`
    ```assembly
    mov RAX, [RBP - 24] ; RAX = [56] = 11
    mov [RBP - 56], RAX
    ```
    *   状态：地址24（80-56）的值变为11。因为通过指针`t1`修改了`x`，所以此时读取的`x`值是11。

![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_89.png)

![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_91.png)

![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_93.png)

![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_95.png)

![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_97.png)

![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_99.png)

这个例子清晰地展示了指针如何使得通过一个变量（`t1`）间接修改另一个变量（`x`）的值成为可能。

![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_101.png)

## 关于CodeGen4项目

![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_52.png)

CodeGen4项目要求你实现编译器后端中处理指针操作的部分。模板与CodeGen3类似，你只需要实现三个函数来分别处理引用、解引用和解引用赋值操作。

需要生成的汇编模板本质上就是我们上面讨论的代码片段：
*   **引用**：计算 `RBP + offset` 并存入目标地址。
*   **解引用**：从源地址加载值到寄存器A，然后 `mov 寄存器B, [寄存器A]`，最后存入目标地址。
*   **解引用赋值**：将右值加载到寄存器B，将左值地址加载到寄存器A，然后执行 `mov [寄存器A], 寄存器B`。

项目的代码量不大，但需要仔细理解何时加载变量值、何时进行间接内存访问。理解本节课的示例是完成项目的关键。

![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_103.png)

![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_105.png)

## 总结

本节课中我们一起学习了编译器实现中指针赋值的处理。我们回顾了指针的基本操作在IR中的表示，重点深入探讨了解引用赋值（`*ptr = value`）的汇编实现机制。

**核心要点总结**：
1.  指针的本质是存储地址的变量，在机器层面与整数没有区别。
2.  访问栈帧变量依赖于 **`RBP`寄存器**和**固定偏移量**。
3.  引用操作 `&x` 通过计算 **`RBP + offset_of_x`** 实现。
4.  解引用操作 `*ptr` 通过汇编指令 **`mov 目标, [地址寄存器]`** 实现。
5.  解引用赋值操作 `*ptr = val` 通过汇编指令 **`mov [地址寄存器], 源`** 实现。
6.  括号 `[ ]` 在汇编中就是解引用操作，它根据寄存器的值进行内存加载或存储。

理解这些底层机制，不仅有助于完成编译器项目，也能让你更深刻地理解C语言中指针的行为、数组访问的本质以及缓冲区溢出等安全问题的根源。指针的强大和危险，都源于这种直接操作内存地址的能力。

![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_107.png)

![](img/34ecb85e0eceaa5ab67bc89154c7d7fb_107.png)