# 40：第30讲：并行性 II - OpenMP 与共享问题 🔄

![](img/871db9a38be557766c273c0ebed8a644_1.png)

在本节课中，我们将学习线程级并行性的第二部分，重点介绍 OpenMP 这一并行编程库，并探讨在共享内存编程中可能遇到的“竞争条件”等核心问题。

![](img/871db9a38be557766c273c0ebed8a644_3.png)

![](img/871db9a38be557766c273c0ebed8a644_5.png)

---

![](img/871db9a38be557766c273c0ebed8a644_7.png)

## 并行编程语言概览 🗺️

上一节我们介绍了线程级并行性的基本概念。本节中我们来看看支持并行编程的不同语言层次。

![](img/871db9a38be557766c273c0ebed8a644_9.png)

![](img/871db9a38be557766c273c0ebed8a644_11.png)

并行编程可以在不同层次上进行，例如控制多台机器或控制单个机器的多个核心。目前存在大约40多种支持并行编程的语言。

![](img/871db9a38be557766c273c0ebed8a644_13.png)

![](img/871db9a38be557766c273c0ebed8a644_15.png)

以下是选择编程语言时需要考虑的一些因素：
*   **明确控制与高级抽象**：像 C 这样的语言允许程序员明确控制硬件操作（例如，如何将数据从一个部分移动到另一个部分）。而像 Python 这样的高级语言则更关注“要做什么”，由编译器或运行时系统决定“如何做”。
*   **任务类型差异**：不同的应用领域（如科学计算、网络服务器）对并行性的需求不同。
*   **输入/输出（I/O）处理**：I/O 操作通常是异步和不可预测的，这本身就是一种并发问题，需要特定的语言特性来处理。

![](img/871db9a38be557766c273c0ebed8a644_17.png)

在 CS61C 课程中，我们重点使用 C 语言，并引入 **OpenMP** 库来帮助我们利用多核处理器进行并行计算。

![](img/871db9a38be557766c273c0ebed8a644_19.png)

---

![](img/871db9a38be557766c273c0ebed8a644_21.png)

## 什么是 OpenMP？ 🧵

OpenMP 是一个支持共享内存并行编程的 C 语言扩展。它的主要优点是允许程序员通过最少的代码修改来实现并行化。

![](img/871db9a38be557766c273c0ebed8a644_23.png)

其核心思想是使用 **编译指导语句**。这些语句以 `#pragma omp` 开头，对于不支持 OpenMP 的编译器来说，它们会被忽略。只有当你包含了 OpenMP 头文件并启用了相应编译选项时，这些语句才会生效。

![](img/871db9a38be557766c273c0ebed8a644_25.png)

OpenMP 采用 **fork-join** 并行执行模型：
1.  程序开始时只有一个主线程。
2.  遇到并行区域时，主线程“派生”出一组工作线程。
3.  所有线程在并行区域内执行代码。
4.  并行区域结束时，所有工作线程“合并”，只剩下主线程继续执行。

![](img/871db9a38be557766c273c0ebed8a644_27.png)

线程是操作系统调度的软件实体，它们被映射到硬件核心上执行。为了获得准确的性能测试结果，应确保在运行并行程序时，系统负载较低。

![](img/871db9a38be557766c273c0ebed8a644_29.png)

![](img/871db9a38be557766c273c0ebed8a644_31.png)

---

![](img/871db9a38be557766c273c0ebed8a644_33.png)

## 使用 OpenMP 并行化循环 🔄

![](img/871db9a38be557766c273c0ebed8a644_35.png)

一个非常常见的并行模式是并行化 `for` 循环。假设我们有一个从 0 到 99 的循环，在拥有 4 个核心的系统上，理想情况是将迭代空间大致平均地分给 4 个线程执行。

使用 OpenMP 可以极其简单地实现这一点。以下是一个基本示例：

![](img/871db9a38be557766c273c0ebed8a644_37.png)

```c
#include <stdio.h>
#include <omp.h>

int main() {
    omp_set_num_threads(4); // 建议使用4个线程
    int a[10];
    int n = 10;

    #pragma omp parallel for
    for (int i = 0; i < n; i++) {
        int thread_id = omp_get_thread_num();
        a[i] = i + thread_id * 10;
        printf("Thread %d: a[%d] = %d\n", thread_id, i, a[i]);
    }

    // 打印结果
    for (int i = 0; i < n; i++) {
        printf("%d ", a[i]);
    }
    printf("\n");
    return 0;
}
```
这段代码通过 `#pragma omp parallel for` 指令将后续的 `for` 循环并行化。每个线程会执行一部分迭代，`omp_get_thread_num()` 函数返回当前线程的 ID。运行程序时，迭代分配到线程的顺序是不确定的。

![](img/871db9a38be557766c273c0ebed8a644_39.png)

![](img/871db9a38be557766c273c0ebed8a644_41.png)

![](img/871db9a38be557766c273c0ebed8a644_43.png)

---

![](img/871db9a38be557766c273c0ebed8a644_45.png)

## 实战案例：并行计算 π 值 🥧

![](img/871db9a38be557766c273c0ebed8a644_47.png)

让我们通过一个计算 π 值的实例来深入理解 OpenMP。我们使用数值积分法，公式如下：

**π = ∫₀¹ (4 / (1 + x²)) dx**

我们可以用黎曼和来近似这个积分。以下是串行实现的代码：

![](img/871db9a38be557766c273c0ebed8a644_49.png)

![](img/871db9a38be557766c273c0ebed8a644_51.png)

![](img/871db9a38be557766c273c0ebed8a644_53.png)

```c
#include <stdio.h>
#include <math.h>

![](img/871db9a38be557766c273c0ebed8a644_55.png)

![](img/871db9a38be557766c273c0ebed8a644_57.png)

static long num_steps = 1000000; // 积分步数
double step;

![](img/871db9a38be557766c273c0ebed8a644_59.png)

![](img/871db9a38be557766c273c0ebed8a644_61.png)

int main() {
    int i;
    double x, pi, sum = 0.0;
    step = 1.0 / (double) num_steps;

    for (i = 0; i < num_steps; i++) {
        x = (i + 0.5) * step; // 取中点
        sum = sum + 4.0 / (1.0 + x * x);
    }
    pi = step * sum;
    printf("Pi = %.15f\n", pi);
    return 0;
}
```

![](img/871db9a38be557766c273c0ebed8a644_63.png)

### 第一次尝试：简单的并行化及其问题

我们尝试直接添加并行指令：

```c
#pragma omp parallel for private(x) reduction(+:sum)
for (i = 0; i < num_steps; i++) {
    x = (i + 0.5) * step;
    sum = sum + 4.0 / (1.0 + x * x);
}
```
但请注意，这里存在一个关键问题。如果像最初那样将 `sum` 声明为单个共享变量，多个线程同时读写 `sum` 会导致错误。这就是一种 **竞争条件**。

![](img/871db9a38be557766c273c0ebed8a644_65.png)

![](img/871db9a38be557766c273c0ebed8a644_67.png)

### 正确的并行化：使用归约子句

正确的做法是使用 OpenMP 的 **`reduction`** 子句。它指示每个线程创建自己的 `sum` 变量私有副本，在循环结束时自动将所有私有副本的值相加到全局变量中。

![](img/871db9a38be557766c273c0ebed8a644_69.png)

![](img/871db9a38be557766c273c0ebed8a644_71.png)

```c
#include <stdio.h>
#include <omp.h>

![](img/871db9a38be557766c273c0ebed8a644_73.png)

![](img/871db9a38be557766c273c0ebed8a644_75.png)

![](img/871db9a38be557766c273c0ebed8a644_77.png)

static long num_steps = 1000000;
double step;

![](img/871db9a38be557766c273c0ebed8a644_79.png)

![](img/871db9a38be557766c273c0ebed8a644_81.png)

![](img/871db9a38be557766c273c0ebed8a644_83.png)

int main() {
    int i;
    double pi, sum = 0.0;
    step = 1.0 / (double) num_steps;

    #pragma omp parallel for reduction(+:sum)
    for (i = 0; i < num_steps; i++) {
        double x = (i + 0.5) * step;
        sum += 4.0 / (1.0 + x * x);
    }
    pi = step * sum;
    printf("Parallel Pi = %.15f\n", pi);
    return 0;
}
```
通过 `reduction(+:sum)` 子句，我们安全高效地实现了并行计算，并能获得显著的加速比。

---

## 理解竞争条件与锁机制 ⚠️🔒

当多个线程同时访问和修改同一共享资源（如变量）时，如果执行结果依赖于线程执行的特定顺序，就会发生 **竞争条件**。这会导致程序行为不确定和结果错误。

![](img/871db9a38be557766c273c0ebed8a644_85.png)

### 竞争条件示例

考虑两个线程同时执行一个简单的递增操作：`counter = counter + 1;`。
假设 `counter` 初始值为 100。我们期望两个线程执行后结果为 102。

![](img/871db9a38be557766c273c0ebed8a644_87.png)

![](img/871db9a38be557766c273c0ebed8a644_89.png)

但由于操作不是原子的（可分解为加载、计算、存储），可能会发生以下交错执行：
1.  线程 A 加载 `counter` (值 100)。
2.  线程 B 加载 `counter` (值 100)。
3.  线程 A 计算 100+1=101，并存储回 `counter` (现为 101)。
4.  线程 B 计算 100+1=101，并存储回 `counter` (覆盖为 101)。
最终结果是 101 而不是 102。这就是竞争条件导致的错误。

![](img/871db9a38be557766c273c0ebed8a644_91.png)

![](img/871db9a38be557766c273c0ebed8a644_93.png)

![](img/871db9a38be557766c273c0ebed8a644_95.png)

### 锁：一种同步机制

解决竞争条件的一种基本方法是使用 **锁**。锁确保一次只有一个线程可以进入被保护的代码区域（临界区）。

锁的基本逻辑是：
*   **加锁**：线程在进入临界区前尝试获取锁。如果锁已被占用，则等待。
*   **执行**：获得锁后，线程安全地执行临界区代码。
*   **解锁**：执行完毕后释放锁，允许其他线程获取。

然而，实现一个正确的锁本身也需要硬件指令支持（如测试并设置指令），以避免在锁的实现上出现竞争条件。OpenMP 提供了高级的同步指令（如 `critical` 区域），避免了手动操作锁的复杂性。

![](img/871db9a38be557766c273c0ebed8a644_97.png)

```c
#pragma omp critical
{
    // 这部分代码一次只能被一个线程执行
    shared_counter = shared_counter + 1;
}
```

![](img/871db9a38be557766c273c0ebed8a644_99.png)

![](img/871db9a38be557766c273c0ebed8a644_101.png)

---

![](img/871db9a38be557766c273c0ebed8a644_103.png)

![](img/871db9a38be557766c273c0ebed8a644_105.png)

![](img/871db9a38be557766c273c0ebed8a644_107.png)

## 总结 📚

![](img/871db9a38be557766c273c0ebed8a644_109.png)

本节课我们一起学习了：
1.  **OpenMP 简介**：一个通过编译指导语句实现共享内存并行的 C 语言扩展库，采用 fork-join 执行模型。
2.  **并行化循环**：使用 `#pragma omp parallel for` 指令可以轻松地将循环迭代分配给多个线程执行。
3.  **实战计算 π**：通过数值积分案例，学习了如何使用 `reduction` 子句来安全地处理并行计算中的累加问题，避免竞争条件。
4.  **竞争条件**：理解了当多个线程无序访问共享资源时会导致不确定的程序行为和数据错误。
5.  **同步机制**：认识了锁作为保护临界区、解决竞争条件的基本概念，并了解到 OpenMP 提供了更高级的同步原语。

![](img/871db9a38be557766c273c0ebed8a644_111.png)

![](img/871db9a38be557766c273c0ebed8a644_113.png)

OpenMP 以其对现有代码改动量小的特点，成为了共享内存并行编程的重要工具。然而，编写正确的并行程序需要仔细考虑数据共享与同步，以避免竞争条件等陷阱。