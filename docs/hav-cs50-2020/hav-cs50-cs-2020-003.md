# 🖥️ 哈佛 CS50 课程笔记 ｜ 第3讲：C语言（语法与格式）2

在本节课中，我们将深入学习C语言的核心语法与格式，包括数据类型、运算符、条件语句、循环以及函数。我们将把上一节课中Scratch的图形化概念转化为C语言的文本代码，并理解计算机在表示数字时的基本限制。

## 📊 数据类型与变量

![](img/cebeed9e0b28f665c194a66b2d3ef30a_1.png)

上一节我们介绍了C语言的基本结构，本节中我们来看看如何存储不同类型的数据。在C语言中，变量不仅可以存储文本字符串，还可以存储多种其他类型的数据，这些被称为**数据类型**。

![](img/cebeed9e0b28f665c194a66b2d3ef30a_3.png)

![](img/cebeed9e0b28f665c194a66b2d3ef30a_5.png)

以下是C语言中一些最常见的数据类型：

*   **`int`**：用于存储整数，例如 `3` 或 `-10`。
*   **`float`**：用于存储浮点数（带小数点的实数），例如 `3.14159`。
*   **`double`**：类似于 `float`，但精度更高。
*   **`char`**：用于存储单个字符，例如 `'A'` 或 `'?'`。
*   **`long`**：用于存储更大的整数。
*   **`string`**：用于存储文本字符串（来自CS50库）。

![](img/cebeed9e0b28f665c194a66b2d3ef30a_7.png)

为了从用户获取不同类型的数据，CS50库提供了相应的函数：

![](img/cebeed9e0b28f665c194a66b2d3ef30a_9.png)

*   `get_string`：获取字符串。
*   `get_char`：获取单个字符。
*   `get_int`：获取整数。
*   `get_float`：获取浮点数。
*   `get_long`：获取长整数。

![](img/cebeed9e0b28f665c194a66b2d3ef30a_11.png)

## 🔢 数据类型的大小与限制

![](img/cebeed9e0b28f665c194a66b2d3ef30a_13.png)

这些数据类型（如 `int` 和 `float`）在计算机内存中只占用有限数量的位（bits）。例如，一个 `int` 通常使用 **32位**，这意味着它最多能表示大约 **40亿** 个不同的值（包括正数和负数）。如果你需要存储更大的数字，就需要使用 `long`（64位）这样的数据类型。

![](img/cebeed9e0b28f665c194a66b2d3ef30a_15.png)

这种限制会导致一些问题，例如著名的 **Y2K问题**（用两位数字表示年份）和即将到来的 **2038年问题**（32位时间戳溢出）。

## 📝 `printf` 的格式代码

在使用 `printf` 打印变量时，你必须使用正确的**格式代码**来告诉函数如何解释你传入的数据。

以下是常用的格式代码：

*   `%c`：打印单个字符 (`char`)。
*   `%f`：打印浮点数 (`float` 或 `double`)。
*   `%i` 或 `%d`：打印整数 (`int`)。
*   `%li`：打印长整数 (`long`)。
*   `%s`：打印字符串 (`string`)。

![](img/cebeed9e0b28f665c194a66b2d3ef30a_17.png)

例如，要打印一个浮点数并显示10位小数，可以使用 `%.10f`。

![](img/cebeed9e0b28f665c194a66b2d3ef30a_19.png)

![](img/cebeed9e0b28f665c194a66b2d3ef30a_21.png)

## ➕ 运算符

![](img/cebeed9e0b28f665c194a66b2d3ef30a_23.png)

C语言支持多种运算符来进行数学和逻辑运算。

以下是基本的数学运算符：

![](img/cebeed9e0b28f665c194a66b2d3ef30a_25.png)

*   `+`：加法
*   `-`：减法
*   `*`：乘法
*   `/`：除法
*   `%`：取模（求余数）

## 🧮 实践：创建一个加法计算器

让我们运用以上知识，创建一个简单的加法计算器程序。

```c
#include <cs50.h>
#include <stdio.h>

int main(void)
{
    // 从用户获取第一个整数
    int x = get_int("x: ");
    // 从用户获取第二个整数
    int y = get_int("y: ");
    // 计算并打印结果
    printf("Sum: %i\n", x + y);
}
```

![](img/cebeed9e0b28f665c194a66b2d3ef30a_27.png)

**程序说明**：
1.  使用 `get_int` 获取用户输入的两个整数，并分别存储在变量 `x` 和 `y` 中。
2.  使用 `printf` 和 `%i` 格式代码打印 `x + y` 的结果。

![](img/cebeed9e0b28f665c194a66b2d3ef30a_29.png)

## ⚠️ 整数溢出与类型转换

![](img/cebeed9e0b28f665c194a66b2d3ef30a_31.png)

![](img/cebeed9e0b28f665c194a66b2d3ef30a_33.png)

如果你尝试将两个很大的整数（例如20亿）相加，结果可能超出 `int` 的表示范围，导致**整数溢出**，得到一个错误的值。这时应使用 `long` 类型。

在进行除法时，如果操作数都是整数，C语言会进行**整数除法**，结果会被**截断**（丢弃小数部分）。为了得到浮点数结果，你需要将至少一个操作数转换为浮点类型。

**错误的整数除法**：
```c
int x = 1;
int y = 2;
float z = x / y; // z 将是 0.000000，因为 1/2 的整数结果是 0
```

**正确的浮点数除法（使用类型转换）**：
```c
int x = 1;
int y = 2;
float z = (float) x / (float) y; // z 将是 0.500000
```
`(float)` 是一种**类型转换**，它告诉编译器将 `x` 和 `y` 当作浮点数来处理。

![](img/cebeed9e0b28f665c194a66b2d3ef30a_35.png)

## 🔁 条件语句 (`if`, `else if`, `else`)

条件语句允许程序根据不同的情况做出决策。这与Scratch中的“如果...那么”积木块相对应。

**语法**：
```c
if (条件)
{
    // 如果条件为真，执行这里的代码
}
else if (另一个条件)
{
    // 如果第一个条件为假，但此条件为真，执行这里的代码
}
else
{
    // 如果以上条件都为假，执行这里的代码
}
```

**重要区别**：
*   **赋值**使用单个等号 `=`。
*   **相等比较**使用两个等号 `==`。

**示例**：比较两个数的大小
```c
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
```

![](img/cebeed9e0b28f665c194a66b2d3ef30a_37.png)

## 🔂 循环 (`while`, `for`)

循环用于重复执行一段代码。

![](img/cebeed9e0b28f665c194a66b2d3ef30a_39.png)

![](img/cebeed9e0b28f665c194a66b2d3ef30a_41.png)

**`while` 循环**：当条件为真时，重复执行。
```c
int i = 0;
while (i < 3)
{
    printf("meow\n");
    i++; // i++ 是 i = i + 1 的简写
}
```

![](img/cebeed9e0b28f665c194a66b2d3ef30a_43.png)

**`for` 循环**：更简洁的循环写法，将初始化、条件和更新写在一行。
```c
for (int i = 0; i < 3; i++)
{
    printf("meow\n");
}
```
这个 `for` 循环等同于上面的 `while` 循环。

![](img/cebeed9e0b28f665c194a66b2d3ef30a_45.png)

**`do...while` 循环**：先执行一次循环体，再检查条件。适用于至少需要执行一次的情况。
```c
int n;
do
{
    n = get_int("Positive integer: ");
}
while (n < 1);
```

## 🧱 实践：打印砖块图案

![](img/cebeed9e0b28f665c194a66b2d3ef30a_47.png)

我们可以使用**嵌套循环**（一个循环 inside 另一个循环）来打印网格图案，比如超级马里奥中的砖块。

![](img/cebeed9e0b28f665c194a66b2d3ef30a_49.png)

```c
for (int i = 0; i < 3; i++) // 外层循环控制行数
{
    for (int j = 0; j < 3; j++) // 内层循环控制每行的砖块数
    {
        printf("#");
    }
    printf("\n"); // 每打印完一行后换行
}
```
**输出**：
```
###
###
###
```

![](img/cebeed9e0b28f665c194a66b2d3ef30a_51.png)

![](img/cebeed9e0b28f665c194a66b2d3ef30a_53.png)

## 📦 函数与抽象

![](img/cebeed9e0b28f665c194a66b2d3ef30a_55.png)

![](img/cebeed9e0b28f665c194a66b2d3ef30a_57.png)

函数允许我们将代码块封装起来并命名，以便重复使用，这实现了**抽象**——隐藏复杂细节。

**定义函数**：
```c
// 函数原型声明，告诉编译器这个函数稍后会定义
void meow(void);

int main(void)
{
    meow(); // 调用函数
}

// 函数定义
void meow(void)
{
    printf("meow\n");
}
```

![](img/cebeed9e0b28f665c194a66b2d3ef30a_59.png)

**带参数的函数**：
```c
void meow(int n) // 函数接受一个整数参数 n
{
    for (int i = 0; i < n; i++)
    {
        printf("meow\n");
    }
}

int main(void)
{
    meow(3); // 调用函数，并传入参数 3
}
```

![](img/cebeed9e0b28f665c194a66b2d3ef30a_63.png)

**带返回值的函数**：
```c
int get_positive_int(void)
{
    int n;
    do
    {
        n = get_int("Positive Integer: ");
    }
    while (n < 1);
    return n; // 返回获取到的正整数
}

int main(void)
{
    int i = get_positive_int(); // 调用函数，并将返回值赋给 i
    printf("%i\n", i);
}
```

## ⚡ 语法糖

**语法糖**是指一种让代码写起来更简洁、更易读的语法，它并不提供新功能，只是更方便。

*   `counter = counter + 1;` 可以简写为 `counter += 1;`
*   进一步简写为 `counter++;` （递增1）
*   同理，`counter--;` 用于递减1。

## 🧠 变量的作用域

变量的**作用域**指的是变量在代码中可以被访问的区域。通常，在花括号 `{}` 内声明的变量只在该花括号内有效。

```c
int main(void)
{
    int n = 5; // 变量 n 在此函数内有效
    if (n > 0)
    {
        int m = 10; // 变量 m 只在这个 if 语句的花括号内有效
        printf("%i\n", m);
    }
    // printf("%i\n", m); // 错误！m 在这里不再存在
}
```

![](img/cebeed9e0b28f665c194a66b2d3ef30a_67.png)

## 🎯 总结

本节课中我们一起学习了C语言的核心语法构件。我们从Scratch的图形化编程过渡到了C语言的文本编程，掌握了如何声明和使用不同的**数据类型**，利用**运算符**进行计算，使用**条件语句**让程序做决策，以及通过**循环**重复执行任务。我们还学会了如何创建自己的**函数**来实现代码抽象和复用。

同时，我们也认识到了计算机的基本限制：由于使用有限数量的位来表示数据，无论是整数还是浮点数，都存在**精度限制**和**表示范围限制**。理解这些限制对于编写正确、健壮的程序至关重要。

![](img/cebeed9e0b28f665c194a66b2d3ef30a_69.png)

现在，你已经具备了用C语言解决更复杂问题的基础知识，可以开始着手你的第一个问题集了！