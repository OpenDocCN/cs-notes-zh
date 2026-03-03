# CS50X 计算机科学导论：第2讲：数组 🧮

![](img/a005845a5246e3935adf3ddf2b2b3e95_0.png)

![](img/a005845a5246e3935adf3ddf2b2b3e95_1.png)

![](img/a005845a5246e3935adf3ddf2b2b3e95_3.png)

![](img/a005845a5246e3935adf3ddf2b2b3e95_5.png)

![](img/a005845a5246e3935adf3ddf2b2b3e95_7.png)

![](img/a005845a5246e3935adf3ddf2b2b3e95_9.png)

在本节课中，我们将学习数组的概念，理解编译过程的细节，并探索调试代码的新工具。我们还将了解如何通过命令行参数与程序交互，并初步接触加密算法的基本思想。

![](img/a005845a5246e3935adf3ddf2b2b3e95_11.png)

![](img/a005845a5246e3935adf3ddf2b2b3e95_13.png)

![](img/a005845a5246e3935adf3ddf2b2b3e95_15.png)

---

![](img/a005845a5246e3935adf3ddf2b2b3e95_17.png)

## 编译过程揭秘 🔍

![](img/a005845a5246e3935adf3ddf2b2b3e95_19.png)

上一节我们介绍了C语言的基础知识，本节中我们来看看代码从编写到运行的幕后过程。

![](img/a005845a5246e3935adf3ddf2b2b3e95_21.png)

![](img/a005845a5246e3935adf3ddf2b2b3e95_23.png)

![](img/a005845a5246e3935adf3ddf2b2b3e95_24.png)

当你输入 `make hello` 时，实际上发生了一个多步骤的编译过程，而不仅仅是“魔法”。这个过程可以分解为四个主要步骤：

1.  **预处理**
2.  **编译**
3.  **汇编**
4.  **链接**

![](img/a005845a5246e3935adf3ddf2b2b3e95_26.png)

### 预处理

![](img/a005845a5246e3935adf3ddf2b2b3e95_28.png)

![](img/a005845a5246e3935adf3ddf2b2b3e95_30.png)

![](img/a005845a5246e3935adf3ddf2b2b3e95_31.png)

预处理步骤处理所有以 `#` 开头的指令（称为预处理指令）。例如，`#include <cs50.h>` 和 `#include <stdio.h>`。编译器会找到这些头文件，并将其中的代码（如函数原型）复制粘贴到你的源文件中。

![](img/a005845a5246e3935adf3ddf2b2b3e95_33.png)

### 编译

![](img/a005845a5246e3935adf3ddf2b2b3e95_35.png)

编译步骤将预处理后的C代码（高级语言）转换为另一种更低级的语言，称为**汇编语言**。汇编语言更接近计算机硬件的理解方式。

### 汇编

汇编步骤将汇编代码转换为计算机真正能理解的**机器码**，即由0和1组成的二进制指令。

### 链接

![](img/a005845a5246e3935adf3ddf2b2b3e95_37.png)

链接是最后一步。如果你的程序使用了其他文件中的代码（例如 `cs50.c` 或 `stdio.c` 中的函数），链接器会将所有已编译的机器码文件“链接”或合并在一起，生成最终的可执行程序。

![](img/a005845a5246e3935adf3ddf2b2b3e95_39.png)

![](img/a005845a5246e3935adf3ddf2b2b3e95_41.png)

**总结**：`make` 命令自动化了上述所有步骤。你也可以直接使用编译器 `clang`，但需要手动指定更多参数，例如 `clang -o hello hello.c` 来命名输出文件，或 `clang -o hello hello.c -lcs50` 来链接第三方库。

![](img/a005845a5246e3935adf3ddf2b2b3e95_43.png)

---

## 调试技术 🐛

编写代码时难免出错，本节我们将学习几种有效的调试方法。

### 1. printf 调试法

![](img/a005845a5246e3935adf3ddf2b2b3e95_45.png)

最直接的方法是在代码中插入 `printf` 语句，打印出变量的值或程序执行到哪一步，以观察程序的实际行为。

**示例**：
```c
for (int i = 0; i <= 3; i++)
{
    printf("i is %i\n", i); // 打印循环变量
    printf("#\n");
}
```
通过观察 `i` 的值，你可以发现循环多执行了一次，从而将条件 `i <= 3` 修正为 `i < 3`。

### 2. 使用调试器 debug50

对于更复杂的问题，使用集成调试器更高效。在VS Code中，你可以使用 `debug50`。

**步骤如下**：
1.  在代码行号左侧点击设置**断点**（红色圆点）。
2.  在终端运行 `debug50 ./your_program`。
3.  调试器会在断点处暂停执行。
4.  使用调试控制台（步过、步入、继续等按钮）逐行执行代码，并观察左侧“变量”窗口中值的变化。

这允许你以“人类速度”检查程序状态，而无需添加大量 `printf` 语句。

![](img/a005845a5246e3935adf3ddf2b2b3e95_47.png)

---

![](img/a005845a5246e3935adf3ddf2b2b3e95_49.png)

## 数组 📦

当我们需要存储一系列相同类型的数据（例如多个分数）时，为每个数据创建单独的变量非常繁琐且难以维护。这时就需要用到**数组**。

数组是一种数据结构，它在内存中连续存储多个相同类型的值。

### 声明和访问数组

![](img/a005845a5246e3935adf3ddf2b2b3e95_51.png)

![](img/a005845a5246e3935adf3ddf2b2b3e95_53.png)

**语法**：
```c
数据类型 数组名[元素数量];
```
**示例**：存储三个分数
```c
int scores[3]; // 声明一个能容纳3个整数的数组
scores[0] = 72; // 初始化第一个元素（索引从0开始）
scores[1] = 73; // 初始化第二个元素
scores[2] = 33; // 初始化第三个元素
```
**关键点**：
*   数组索引从 **0** 开始。
*   使用 `数组名[索引]` 来访问或修改特定位置的元素。

### 使用循环处理数组

结合循环，可以更优雅地处理数组。

**示例**：计算平均分
```c
#include <cs50.h>
#include <stdio.h>

// 常数定义
const int N = 3;

![](img/a005845a5246e3935adf3ddf2b2b3e95_55.png)

![](img/a005845a5246e3935adf3ddf2b2b3e95_57.png)

// 函数原型
float average(int length, int array[]);

int main(void)
{
    int scores[N];
    for (int i = 0; i < N; i++)
    {
        scores[i] = get_int("Score: ");
    }
    printf("Average: %f\n", average(N, scores));
}

// 计算平均值的函数
float average(int length, int array[])
{
    int sum = 0;
    for (int i = 0; i < length; i++)
    {
        sum += array[i];
    }
    return sum / (float) length;
}
```
**代码说明**：
*   使用常量 `N` 定义数组大小，便于修改。
*   `average` 函数接收数组长度和数组本身作为参数。在函数参数中，数组用 `int array[]` 表示。
*   在函数内部，通过循环遍历数组元素进行计算。

---

## 字符串本质 🔤

上一节我们使用了字符串，本节中我们来看看字符串在C语言中是如何实现的。

在C语言中，**字符串实际上就是一个字符数组**。每个字符串的末尾都有一个特殊的字符 `\0`（空字符，ASCII值为0），用来标记字符串的结束。

**示例**：字符串 “HI!” 在内存中的存储
```
索引:   0    1    2    3
字符:  ‘H’  ‘I’  ‘!’  ‘\0’
ASCII:  72   73   33    0
```

### 手动计算字符串长度

![](img/a005845a5246e3935adf3ddf2b2b3e95_59.png)

![](img/a005845a5246e3935adf3ddf2b2b3e95_61.png)

我们可以通过循环查找 `\0` 字符来确定字符串长度。

**示例**：
```c
#include <cs50.h>
#include <stdio.h>

![](img/a005845a5246e3935adf3ddf2b2b3e95_63.png)

![](img/a005845a5246e3935adf3ddf2b2b3e95_64.png)

int main(void)
{
    string name = get_string("Name: ");
    int n = 0;
    while (name[n] != '\0')
    {
        n++;
    }
    printf("%i\n", n);
}
```
当然，更简单的方法是使用标准库函数 `strlen`（来自 `<string.h>`）：
```c
#include <cs50.h>
#include <stdio.h>
#include <string.h> // 引入字符串库

int main(void)
{
    string name = get_string("Name: ");
    int length = strlen(name);
    printf("%i\n", length);
}
```

![](img/a005845a5246e3935adf3ddf2b2b3e95_66.png)

![](img/a005845a5246e3935adf3ddf2b2b3e95_67.png)

### 字符大小写转换

利用ASCII码表，我们可以进行字符大小写转换。大写字母和小写字母的ASCII值相差32。

**示例**：将字符串转换为大写（手动实现）
```c
#include <cs50.h>
#include <stdio.h>
#include <string.h>

int main(void)
{
    string s = get_string("Before: ");
    printf("After:  ");
    for (int i = 0, n = strlen(s); i < n; i++)
    {
        if (s[i] >= 'a' && s[i] <= 'z')
        {
            printf("%c", s[i] - 32); // 小写转大写
        }
        else
        {
            printf("%c", s[i]);
        }
    }
    printf("\n");
}
```
更佳实践是使用 `<ctype.h>` 库中的 `toupper` 函数：
```c
#include <cs50.h>
#include <ctype.h>
#include <stdio.h>
#include <string.h>

int main(void)
{
    string s = get_string("Before: ");
    printf("After:  ");
    for (int i = 0, n = strlen(s); i < n; i++)
    {
        printf("%c", toupper(s[i])); // 使用库函数
    }
    printf("\n");
}
```
**优化点**：在循环条件 `i < strlen(s)` 中，`strlen` 函数会在每次循环时都被调用，效率低下。更好的做法是在循环开始前计算一次长度并存储。

---

## 命令行参数 🖥️

![](img/a005845a5246e3935adf3ddf2b2b3e95_69.png)

![](img/a005845a5246e3935adf3ddf2b2b3e95_70.png)

程序可以从命令行接收输入，这些输入称为**命令行参数**。

### 访问命令行参数

`main` 函数可以修改其参数来接收这些输入。

![](img/a005845a5246e3935adf3ddf2b2b3e95_72.png)

![](img/a005845a5246e3935adf3ddf2b2b3e95_73.png)

**新的 main 函数签名**：
```c
int main(int argc, string argv[])
```
*   `argc`（参数计数）：一个整数，表示命令行中输入了多少个词。
*   `argv`（参数向量）：一个字符串数组，存储了命令行中输入的所有词。

![](img/a005845a5246e3935adf3ddf2b2b3e95_75.png)

![](img/a005845a5246e3935adf3ddf2b2b3e95_76.png)

**约定**：
*   `argv[0]` 始终是程序的名称（例如 `./greet`）。
*   用户提供的参数从 `argv[1]` 开始。

**示例**：一个简单的问候程序
```c
#include <cs50.h>
#include <stdio.h>

![](img/a005845a5246e3935adf3ddf2b2b3e95_78.png)

int main(int argc, string argv[])
{
    if (argc == 2)
    {
        printf("hello, %s\n", argv[1]);
    }
    else
    {
        printf("hello, world\n");
    }
}
```
**运行示例**：
```
$ ./greate
hello, world

![](img/a005845a5246e3935adf3ddf2b2b3e95_80.png)

![](img/a005845a5246e3935adf3ddf2b2b3e95_82.png)

![](img/a005845a5246e3935adf3ddf2b2b3e95_83.png)

$ ./greate David
hello, David
```

### 程序退出状态

`main` 函数返回的整数称为**退出状态**或**退出代码**。这是一种程序与操作系统或其他程序通信的方式，表明自己是成功结束还是遇到了错误。

**约定**：
*   `0` 表示**成功**。
*   任何**非零值**（通常是1）表示**失败**（或某种错误）。

![](img/a005845a5246e3935adf3ddf2b2b3e95_85.png)

![](img/a005845a5246e3935adf3ddf2b2b3e95_86.png)

**示例**：在之前的程序中加入退出状态
```c
#include <cs50.h>
#include <stdio.h>

![](img/a005845a5246e3935adf3ddf2b2b3e95_88.png)

int main(int argc, string argv[])
{
    if (argc != 2)
    {
        printf("Missing command-line argument\n");
        return 1; // 返回 1 表示错误
    }
    printf("hello, %s\n", argv[1]);
    return 0; // 返回 0 表示成功
}
```
在终端中，可以使用 `echo $?` 命令查看上一个执行程序的退出状态。

![](img/a005845a5246e3935adf3ddf2b2b3e95_90.png)

---

## 密码学初探 🔐

最后，我们简要探讨密码学，这是本周问题集的另一个主题。加密是将信息（明文）打乱成密文的过程，而解密则是其反向过程。

### 凯撒密码

一种古老的加密算法是**凯撒密码**。它的原理是将明文中的每个字母在字母表中向后移动一个固定的位置（这个位置就是密钥）。

**加密示例**（密钥为1）：
*   明文：`HI!`
*   密文：`IJ!` （H->I, I->J, ! 不变）

**解密**则是将密文中的每个字母向前移动相同的位数。

如果密钥是13，则这种特殊的凯撒密码称为 **ROT13**。一个有趣的现象是，ROT26（移动26位）等于没有移动，因此密文和明文相同，这并不安全。

现代加密算法远比凯撒密码复杂，但理解其基本原理是学习更高级概念的良好起点。在本周的问题集中，你将有机会实现类似的加密算法。

![](img/a005845a5246e3935adf3ddf2b2b3e95_92.png)

---

## 总结 📝

本节课中我们一起学习了：
1.  **编译过程的四个阶段**：预处理、编译、汇编、链接，理解了 `make` 命令背后的工作。
2.  **强大的调试工具**：包括 `printf` 调试法和 `debug50` 集成调试器的使用。
3.  **数组**：如何声明、初始化和使用数组来高效存储和处理一系列数据。
4.  **字符串的本质**：认识到字符串就是字符数组，并以 `\0` 结尾，学会了使用 `strlen` 等字符串函数。
5.  **命令行参数**：如何让程序从命令行接收输入，并通过 `argc` 和 `argv` 访问它们。
6.  **程序退出状态**：使用 `return` 语句向系统返回成功或错误代码。
7.  **密码学基础**：了解了凯撒密码的基本原理，为后续的编程实践打下基础。

![](img/a005845a5246e3935adf3ddf2b2b3e95_94.png)

![](img/a005845a5246e3935adf3ddf2b2b3e95_95.png)

这些概念和工具将帮助你更深入地理解计算机如何工作，并为你解决更复杂的编程问题（如计算文本阅读等级、实现加密算法）做好准备。