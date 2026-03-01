# C语言入门：18_03_01：使用Valgrind发现问题 🔍

![](img/1b8513cab39df20ba979097dd0f16952_0.png)

在本节课中，我们将学习如何使用Valgrind工具来发现和调试C程序中的内存错误。我们将通过一个具体的例子，演示如何定位并修复一个由未初始化变量引起的bug。

---

## 概述

Valgrind是一个强大的内存调试和分析工具。它可以帮助我们发现程序运行时难以察觉的错误，例如使用未初始化的内存、内存泄漏或非法内存访问。本节我们将通过一个名为`broken`的程序实例，演示Valgrind的基本使用流程。

## 程序分析

首先，我们来看一下Drew提供的程序`broken`。该程序由一个`quadratic`函数和`main`函数组成。

`quadratic`函数旨在计算二次多项式 `a*x² + b*x + c` 的值。其函数声明如下：
```c
double quadratic(double a, double b, double c, double x);
```
在`main`函数中，程序使用两组不同的参数调用`quadratic`函数，并打印结果。

第一组参数 `(1, -2, 0.5, 3)` 的计算结果是正确的，输出为3.5。
然而，第二组参数 `(-1, 3, 1, 2)` 的计算结果出现了错误。根据公式 `(-1)*2² + 3*2 + 1`，正确结果应为3，但程序输出并非如此。

## 使用Valgrind定位问题

为了找出问题根源，我们使用Valgrind来运行程序。以下是运行命令：
```bash
valgrind ./broken
```
Valgrind报告了多达156个错误，来自52个不同的上下文。这表明程序中存在严重问题。通常，修复第一个报告的错误可以连带解决后续的许多错误。

Valgrind报告的第一个错误信息是：“Conditional jump or move depends on uninitialized values”。关键词是“uninitialized values”（未初始化的值）。错误发生在调用`printf`函数时。

为了获取更精确的错误位置信息，我们使用`--track-origins=yes`选项重新运行Valgrind：
```bash
valgrind --track-origins=yes ./broken
```
新的报告指出，这个未初始化的值是在`quadratic`函数中通过栈分配创建的。具体指向了源代码的第5行。

## 修复Bug

我们查看源代码第5行附近的代码。第5行是函数声明，第6行声明了变量`total`，第7行则执行了 `total += ...` 的操作。
```c
double total; // 第6行：声明变量
total += a * x * x; // 第7行：使用未初始化的total进行加法操作
```
问题在于，变量`total`在声明后没有赋予初始值（例如0），就直接用于加法运算。这导致了未定义行为。

修复方法很简单：将`total`初始化为0。
```c
double total = 0.0;
```
修复后重新编译并运行程序，两组测试用例都输出了正确的结果：3.5和3。

我们再次运行Valgrind进行验证。这次报告显示：“ERROR SUMMARY: 0 errors from 0 contexts”。这表明所有内存错误都已被修复。报告还显示“All heap blocks were freed -- no leaks are possible”，说明没有内存泄漏，这对于当前课程阶段是理想的结果。

## 编译器警告的作用

值得一提的是，许多此类错误也可以通过启用编译器的警告选项来发现。例如，使用GCC的`-Wall`选项编译未修复的程序：
```bash
gcc -Wall -o broken broken.c
```
编译器会给出警告：“‘total’ is used uninitialized in this function”，并指出具体的代码行号。这为我们提供了非常有用的调试信息。

然而，需要指出的是，编译器的静态分析有时会遗漏一些错误，而这些错误可能被Valgrind在运行时动态检测到。因此，结合使用编译器警告和Valgrind工具，是确保代码质量的更佳实践。

---

## 总结

![](img/1b8513cab39df20ba979097dd0f16952_2.png)

本节课中，我们一起学习了如何使用Valgrind工具来调试C程序。我们通过一个实际案例，经历了从发现问题（程序输出错误）、使用Valgrind定位错误根源（未初始化变量）、到最终修复错误（初始化变量）的完整流程。同时，我们也了解了编译器警告在辅助调试中的作用。掌握这些工具和方法，将帮助你更高效地编写出健壮、无错的C语言程序。