# 并行性

## 入门

要使用本节中的想法，您需要我们的并发库。从实验室计算机（或通过 SSH）中，将以下内容键入您的 Scheme 解释器：

```
(load "~cs61as/lib/concurrency.scm") 
```

## 概述

在涉及任何形式的并行性时，我们通常认为的许多事情在普通编程中变得棘手。这些情况包括：

+   多处理器（硬件）共享数据

+   软件多线程（模拟并行性）

+   操作系统输入/输出设备处理程序

这在 CS 162（操作系统）中有更详细的介绍。

## 为什么并行性很困难

要简单地看出问题所在，想想 Scheme 表达式

```
(set! x (+ x 1)) 
```

正如您将在 61C 中更详细地了解的那样，Scheme 将这转换为一系列指令发送到您的计算机。细节取决于特定的计算机模型，但会类似于这样：

```
lw $8, x        ; Put the value of x into processor register number 8.
addi $8, $8, 1  ; Take the value of register 8, add 1 to it, and put  
                ; the new value back into register 8.
sw $8, x        ; Set the value in register 8 as the value of x. 
```

您不必理解这里代码的细节（您将在 61C 中学习），但您应该知道正在发生什么。

（*寄存器*是计算机放置值的地方，以便它可以对其进行操作。因此，计算机通常不能立即将 1 添加到 x - 它必须首先将 x 的值放入寄存器，然后才能将 1 添加到其中。）

通常我们期望这些指令序列会产生期望的效果。如果这些指令之前 x 的值为 100，那么之后应该是 101。

但想象一下，这三条指令序列可能会被中间发生的其他事件打断。具体来说，假设还有其他人也试图将 1 添加到 x 的值。现在我们可能会有这样的序列：

```
my process      value of x   other process
----------      ----------   -------------  
  $8 = ??        x = 100       $9 = ??

lw $8, x  
  $8 = 100       x = 100       $9 = ??

addi $8, $8, 1  
  $8 = 101       x = 100       $9 = ??

                             lw $9, x  
  $8 = 101       x = 100       $9 = 100

                             addi $9, $9, 1  
  $8 = 101       x = 100       $9 = 101

                             sw $9, x  
  $8 = 101       x = 101       $9 = 101

sw $8, x  
  $8 = 101       x = 101       $9 = 101 
```

x 的最终值将是 101，而不是正确的 102。

我们需要解决这个问题的一般思路是关键部分，这意味着一系列不得中断的指令。从加载开始到存储结束的三条指令是一个关键部分。

实际上，我们不必说这些指令不能被打断；我们必须强制执行的唯一条件是它们不能被使用变量 x 的另一个进程打断。如果另一个进程同时想要将 1 添加到 y，那没问题。因此，我们希望能够说出类似于

```
reserve x
lw $8, x
addi $8, 1
sw $8, x
release x 
```

## 抽象级别

计算机实际上并没有像`reserve`和`release`这样的指令，但我们会看到它们提供了类似的机制。典型的编程环境包括三个抽象级别的并发控制机制：

```
SICP name        What's protected              Provided by
---------        ----------------              -----------
serializer       high level abstraction        programming language
                   (procedure, object, ...)

mutex            critical section              operating system

test-and-set!    one atomic                    hardware
                   state transition 
```

在 SICP 中，串行器和互斥体是抽象数据类型。有一个使用互斥体实现的构造函数`make-serializer`，以及一个使用`test-and-set!`实现的构造函数`make-mutex`，后者是一个（在我们的情况下是模拟的）硬件指令。

我们将在接下来的章节中讨论串行器和互斥体。
