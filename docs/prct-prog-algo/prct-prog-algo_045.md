# 8.2 编译器、解释器和仿真器

> 原文：[`introcs.cs.princeton.edu/java/82compiler`](https://introcs.cs.princeton.edu/java/82compiler)
> 
> 译者：[飞龙](https://github.com/wizardforcel)
> 
> 协议：[CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/)


本节正在大规模施工中。

## 编译器和解释器。

*编译器*是一个程序，它以某种高级编程语言的程序作为输入，并输出某种机器架构的机器语言代码。机器语言代码随后可以使用不同的输入数据多次执行。例如，Unix 程序`g++`将一个 C++源文件转换为一个可以在 Sparc 微处理器上本地运行的机器可执行文件`a.out`。第二个例子，Java 编译器`javac`将一个`.java`源文件转换为一个用*Java 字节码*编写的`.class`文件，这是一个名为*Java 虚拟机*的虚拟机器的机器语言。

*解释器*是一个程序，它以源程序和程序数据作为输入，并逐条翻译源程序。例如，Java 解释器`java`将一个`.class`文件翻译为可以在底层机器上本地执行的代码。第二个例子，程序 VirtualPC 将为 Intel Pentium 架构（IBM-PC 克隆）编写的程序解释为 PowerPC 架构（Macintosh）的程序。这使得 Macintosh 用户可以在他们的计算机上运行 Windows 程序。

为什么 Java 通常解释而不是编译？编译的主要优势是最终得到了可以在您的计算机上高效执行的原始机器语言代码。然而，它只能在一种类型的机器架构上执行（Intel Pentium，PowerPC）。将编译为像 Java 字节码这样的中间语言然后解释的主要优势是可以实现*平台独立性*：您可以在不同类型的机器架构上解释相同的`.class`文件。然而，解释字节码通常比执行预编译的机器语言代码慢。使用 Java 字节码的第二个优势是它充当您的计算机和程序之间的缓冲区。这使您可以从互联网下载一个不受信任的程序并在您的计算机上执行它，同时提供一些保证。由于您正在运行 Java 解释器（而不是原始机器语言代码），您受到一层防护，可防范恶意程序。正是 Java 和 Java 字节码的结合产生了一个平台独立和安全的环境，同时还包含了一整套现代编程抽象。

Java 字节码和 java 解释器并不固有地特定于 Java 编程语言。例如，您可以使用 Jython 将 Python 编程语言编译为 Java 字节码，然后使用`java`来解释它。有类似的 ML、Lisp 和 Fortran 编译器将编译为 Java 字节码。您还可以使用 Unix 程序`gcj`直接从一个`.java`源文件编译为一个可以在任何 Sparc 微处理器上本地运行的机器可执行��件`a.out`。此外，您可以设计硬件，其机器语言是 Java 字节码。Sun Microsystems 正是这样做的，使 Java 虚拟机不再那么虚拟。

为什么不使用真正的机器语言而是 Java 字节码？Java 字节码比典型的高级编程语言简单得多。为新类型的计算机编写一个 Java 字节码解释器比编写一个完整的 Java 编译器要容易得多。

#### 创意练习

1.  **布尔表达式求值。** 编写一个程序来[评估由位、一元运算符(~)、二元运算符(&, ^, |)和括号组成的布尔表达式](http://cgm.cs.mcgill.ca/~msuder/courses/250/assignments/3/3.pdf)，使用与 Java 相同的优先级规则。这里是一个使用[两个栈](http://cgm.cs.mcgill.ca/~msuder/courses/250/assignments/3/solutions/3.pdf)的解决方案，一个用于存储位，另一个用于存储运算符。
