# CS50x 2024：第1讲：C语言入门 🚀

![](img/9b3478adcf58801ce6a8c57047480262_0.png)

![](img/9b3478adcf58801ce6a8c57047480262_2.png)

![](img/9b3478adcf58801ce6a8c57047480262_3.png)

![](img/9b3478adcf58801ce6a8c57047480262_4.png)

![](img/9b3478adcf58801ce6a8c57047480262_6.png)

![](img/9b3478adcf58801ce6a8c57047480262_8.png)

在本节课中，我们将学习如何从上周的Scratch图形化编程过渡到更传统、更底层的C语言编程。我们将探索C语言的基本语法，包括变量、函数、条件语句和循环，并了解如何编写、编译和运行C程序。同时，我们也会探讨计算机在表示数字时的一些根本性限制。

![](img/9b3478adcf58801ce6a8c57047480262_10.png)

![](img/9b3478adcf58801ce6a8c57047480262_12.png)

---

## 从Scratch到C语言 🔄

![](img/9b3478adcf58801ce6a8c57047480262_14.png)

![](img/9b3478adcf58801ce6a8c57047480262_15.png)

![](img/9b3478adcf58801ce6a8c57047480262_17.png)

上一周我们使用Scratch学习了编程的基本概念，如函数、循环和条件语句。本节中，我们来看看如何将这些概念转化为C语言代码。

![](img/9b3478adcf58801ce6a8c57047480262_19.png)

在Scratch中，我们使用“当绿旗被点击”积木来启动程序。在C语言中，我们使用一个名为 `main` 的特殊函数作为程序的起点。Scratch中的“说”积木在C语言中对应的是 `printf` 函数。

以下是Scratch中的“Hello, World!”程序与C语言版本的对比：

![](img/9b3478adcf58801ce6a8c57047480262_21.png)

**Scratch:**
```
当绿旗被点击
说 Hello, world!
```

![](img/9b3478adcf58801ce6a8c57047480262_23.png)

![](img/9b3478adcf58801ce6a8c57047480262_24.png)

![](img/9b3478adcf58801ce6a8c57047480262_26.png)

**C语言:**
```c
#include <stdio.h>

![](img/9b3478adcf58801ce6a8c57047480262_28.png)

![](img/9b3478adcf58801ce6a8c57047480262_30.png)

int main(void)
{
    printf("hello, world\n");
}
```

![](img/9b3478adcf58801ce6a8c57047480262_32.png)

![](img/9b3478adcf58801ce6a8c57047480262_34.png)

![](img/9b3478adcf58801ce6a8c57047480262_35.png)

在C语言中，`#include <stdio.h>` 告诉编译器我们想要使用标准输入输出功能，`printf` 函数就包含在其中。`\n` 是一个特殊字符，代表换行。

![](img/9b3478adcf58801ce6a8c57047480262_37.png)

---

## 编写、编译和运行C程序 ⚙️

![](img/9b3478adcf58801ce6a8c57047480262_39.png)

要运行C程序，我们需要三个步骤：编写源代码、编译源代码为机器码、运行生成的可执行文件。

![](img/9b3478adcf58801ce6a8c57047480262_41.png)

![](img/9b3478adcf58801ce6a8c57047480262_43.png)

以下是这三个步骤对应的命令：
1.  **`code hello.c`**：创建或打开一个名为 `hello.c` 的源代码文件。
2.  **`make hello`**：使用编译器将 `hello.c` 编译成名为 `hello` 的可执行文件。
3.  **`./hello`**：运行编译好的 `hello` 程序。

我们将在名为VS Code的云端编程环境中完成这些操作。这个环境包含一个文本编辑器（用于写代码）和一个终端窗口（用于输入命令）。

---

![](img/9b3478adcf58801ce6a8c57047480262_45.png)

![](img/9b3478adcf58801ce6a8c57047480262_47.png)

![](img/9b3478adcf58801ce6a8c57047480262_49.png)

## 变量和用户输入 📝

在Scratch中，我们使用“询问”积木来获取用户输入，并将答案存储在“回答”变量中。在C语言中，我们使用CS50库中的 `get_string` 函数来实现类似功能。

以下是获取用户姓名并打招呼的C语言程序：

![](img/9b3478adcf58801ce6a8c57047480262_51.png)

![](img/9b3478adcf58801ce6a8c57047480262_52.png)

```c
#include <cs50.h>
#include <stdio.h>

![](img/9b3478adcf58801ce6a8c57047480262_54.png)

int main(void)
{
    string answer = get_string("What's your name? ");
    printf("hello, %s\n", answer);
}
```

![](img/9b3478adcf58801ce6a8c57047480262_56.png)

![](img/9b3478adcf58801ce6a8c57047480262_57.png)

代码解析：
*   `#include <cs50.h>`：引入CS50库，它提供了 `get_string` 和 `string` 类型等便利功能。
*   `string answer = ...`：声明一个名为 `answer` 的字符串变量，并将 `get_string` 函数的返回值（即用户输入）存储在其中。
*   `printf("hello, %s\n", answer)`：打印问候语。`%s` 是一个占位符，它会被后面变量 `answer` 的值替换。

![](img/9b3478adcf58801ce6a8c57047480262_59.png)

---

![](img/9b3478adcf58801ce6a8c57047480262_61.png)

![](img/9b3478adcf58801ce6a8c57047480262_62.png)

![](img/9b3478adcf58801ce6a8c57047480262_64.png)

![](img/9b3478adcf58801ce6a8c57047480262_65.png)

## 条件语句 🤔

![](img/9b3478adcf58801ce6a8c57047480262_67.png)

![](img/9b3478adcf58801ce6a8c57047480262_69.png)

条件语句允许程序根据不同的情况做出决策。在Scratch中，我们使用“如果-那么”积木。在C语言中，我们使用 `if`、`else if` 和 `else` 关键字。

![](img/9b3478adcf58801ce6a8c57047480262_71.png)

以下是一个比较两个整数的C语言程序：

```c
#include <cs50.h>
#include <stdio.h>

int main(void)
{
    int x = get_int("What's x? ");
    int y = get_int("What's y? ");

    if (x < y)
    {
        printf("x is less than y\n");
    }
    else if (x > y)
    {
        printf("x is greater than y\n");
    }
    else
    {
        printf("x is equal to y\n");
    }
}
```

![](img/9b3478adcf58801ce6a8c57047480262_73.png)

代码使用 `get_int` 获取两个整数，然后通过一系列条件判断来比较它们的大小。使用 `else if` 和 `else` 可以避免不必要的重复判断，使逻辑更高效。

![](img/9b3478adcf58801ce6a8c57047480262_75.png)

---

![](img/9b3478adcf58801ce6a8c57047480262_77.png)

## 循环 🔁

![](img/9b3478adcf58801ce6a8c57047480262_79.png)

![](img/9b3478adcf58801ce6a8c57047480262_81.png)

![](img/9b3478adcf58801ce6a8c57047480262_83.png)

循环用于重复执行一段代码。在Scratch中，我们使用“重复”积木。在C语言中，我们主要使用 `while` 循环和 `for` 循环。

**使用 `while` 循环打印三次“meow”：**
```c
int i = 0;
while (i < 3)
{
    printf("meow\n");
    i++;
}
```

![](img/9b3478adcf58801ce6a8c57047480262_85.png)

![](img/9b3478adcf58801ce6a8c57047480262_86.png)

![](img/9b3478adcf58801ce6a8c57047480262_88.png)

![](img/9b3478adcf58801ce6a8c57047480262_89.png)

![](img/9b3478adcf58801ce6a8c57047480262_91.png)

![](img/9b3478adcf58801ce6a8c57047480262_92.png)

**使用 `for` 循环实现相同功能（更常用）：**
```c
for (int i = 0; i < 3; i++)
{
    printf("meow\n");
}
```
`for` 循环的括号内包含三部分：初始化 (`int i = 0`)、条件 (`i < 3`)、更新 (`i++`)。它更紧凑，是循环计数的标准写法。

![](img/9b3478adcf58801ce6a8c57047480262_94.png)

![](img/9b3478adcf58801ce6a8c57047480262_96.png)

---

![](img/9b3478adcf58801ce6a8c57047480262_98.png)

![](img/9b3478adcf58801ce6a8c57047480262_100.png)

![](img/9b3478adcf58801ce6a8c57047480262_101.png)

## 自定义函数 🛠️

![](img/9b3478adcf58801ce6a8c57047480262_103.png)

![](img/9b3478adcf58801ce6a8c57047480262_105.png)

![](img/9b3478adcf58801ce6a8c57047480262_107.png)

我们可以创建自己的函数来组织代码并实现复用。这类似于在Scratch中创建自定义积木。

![](img/9b3478adcf58801ce6a8c57047480262_109.png)

![](img/9b3478adcf58801ce6a8c57047480262_111.png)

![](img/9b3478adcf58801ce6a8c57047480262_112.png)

以下是一个自定义函数 `meow`，它接受一个参数 `n` 并打印“meow” `n` 次：

![](img/9b3478adcf58801ce6a8c57047480262_114.png)

![](img/9b3478adcf58801ce6a8c57047480262_115.png)

![](img/9b3478adcf58801ce6a8c57047480262_117.png)

![](img/9b3478adcf58801ce6a8c57047480262_118.png)

```c
#include <stdio.h>

void meow(int n);

int main(void)
{
    meow(3);
}

![](img/9b3478adcf58801ce6a8c57047480262_120.png)

void meow(int n)
{
    for (int i = 0; i < n; i++)
    {
        printf("meow\n");
    }
}
```

![](img/9b3478adcf58801ce6a8c57047480262_122.png)

![](img/9b3478adcf58801ce6a8c57047480262_124.png)

代码解析：
*   `void meow(int n);`：这是函数原型，它告诉编译器 `meow` 函数的存在、其返回值类型 (`void` 表示无返回值) 和参数类型 (`int`)。
*   `void meow(int n) { ... }`：这是函数的实际定义。
*   在 `main` 函数中，我们通过 `meow(3);` 来调用这个函数。

![](img/9b3478adcf58801ce6a8c57047480262_126.png)

![](img/9b3478adcf58801ce6a8c57047480262_127.png)

![](img/9b3478adcf58801ce6a8c57047480262_129.png)

---

![](img/9b3478adcf58801ce6a8c57047480262_131.png)

![](img/9b3478adcf58801ce6a8c57047480262_132.png)

![](img/9b3478adcf58801ce6a8c57047480262_134.png)

## 返回值的函数 📤

![](img/9b3478adcf58801ce6a8c57047480262_136.png)

有些函数不仅执行操作，还会返回一个值供我们使用。例如，`get_int` 返回一个整数。我们也可以创建自己的有返回值的函数。

![](img/9b3478adcf58801ce6a8c57047480262_138.png)

![](img/9b3478adcf58801ce6a8c57047480262_139.png)

以下是一个实现加法运算的函数 `add`：

![](img/9b3478adcf58801ce6a8c57047480262_141.png)

![](img/9b3478adcf58801ce6a8c57047480262_142.png)

```c
#include <stdio.h>

int add(int a, int b);

int main(void)
{
    int x = get_int("x: ");
    int y = get_int("y: ");
    int z = add(x, y);
    printf("%i\n", z);
}

int add(int a, int b)
{
    return a + b;
}
```
`add` 函数接收两个整数参数 `a` 和 `b`，使用 `return` 关键字返回它们的和。在 `main` 函数中，我们将返回值存储在变量 `z` 中并打印。

---

![](img/9b3478adcf58801ce6a8c57047480262_144.png)

## 计算机的局限性 🚧

![](img/9b3478adcf58801ce6a8c57047480262_146.png)

计算机的内存是有限的，这导致它在处理数字时存在一些根本性限制。

1.  **整数溢出**：计算机使用固定数量的比特位（如32位）来存储整数。当数字超过该位数所能表示的最大值时，它会“溢出”并绕回一个很小的值（甚至是负数）。例如，旧的电子游戏《吃豆人》在第256关时屏幕会乱码，就是因为计数变量溢出。
2.  **浮点数精度问题**：计算机无法精确表示所有实数（如 `1/3` 的无限循环小数）。使用有限内存（如32位浮点数）进行存储和计算时，会产生微小的舍入误差。在金融、科学计算等领域，这可能导致严重问题。

历史上著名的“Y2K千年虫”问题和即将到来的“2038年问题”（32位时间戳溢出）都是整数溢出在现实世界中的体现。波音787客机也曾因一个计数器在连续运行248天后溢出，而需要定期重启以重置系统。

---

![](img/9b3478adcf58801ce6a8c57047480262_148.png)

## 总结 📚

![](img/9b3478adcf58801ce6a8c57047480262_150.png)

本节课中我们一起学习了C语言编程的基础。我们从Scratch过渡到C，掌握了如何编写、编译和运行C程序。我们学习了变量、数据类型、使用 `printf` 和 `get_string` 等函数进行输入输出，以及如何使用条件语句和循环来控制程序流程。我们还创建了自定义函数来组织代码。最后，我们探讨了由于计算机内存有限而导致的整数溢出和浮点数精度问题，理解了这些局限性在现实世界中可能引发的后果。

![](img/9b3478adcf58801ce6a8c57047480262_152.png)

![](img/9b3478adcf58801ce6a8c57047480262_154.png)

![](img/9b3478adcf58801ce6a8c57047480262_155.png)

这些知识为我们解决更复杂的问题奠定了坚实的基础。在接下来的课程和问题集中，我们将继续深化对这些概念的理解和应用。