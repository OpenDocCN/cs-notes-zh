# CS50X 计算机科学导论 C语言：1：C语言入门

![](img/dd24156253db04e74fc14922ba497b1f_1.png)

在本节课中，我们将要学习如何开始使用C语言进行编程。我们将从回顾上周的Scratch编程概念开始，然后逐步过渡到C语言的基本语法和结构。我们将学习如何编写、编译和运行第一个C程序，并探索变量、条件语句、循环和函数等核心概念。

## 概述

上一节我们介绍了Scratch编程环境，通过拖拽积木块实现了简单的程序。本节中，我们来看看如何将这些概念转化为C语言代码。我们将从编写一个简单的“Hello, World!”程序开始，逐步深入到更复杂的编程结构。

## 从Scratch到C

在Scratch中，我们使用“当绿旗被点击”积木块来启动程序，并使用“说”积木块来显示文本。在C语言中，这些概念被转化为文本代码。

以下是Scratch中“Hello, World!”程序的等效C代码：

```c
#include <stdio.h>

![](img/dd24156253db04e74fc14922ba497b1f_3.png)

int main(void)
{
    printf("hello, world\n");
}
```

![](img/dd24156253db04e74fc14922ba497b1f_5.png)

在这个C程序中：
*   `#include <stdio.h>` 是一个头文件，它包含了`printf`函数所需的代码。
*   `int main(void)` 是程序的入口点，类似于Scratch中的“当绿旗被点击”。
*   `printf("hello, world\n");` 是输出函数，类似于Scratch中的“说”积木块。`\n`是一个转义序列，表示换行。

![](img/dd24156253db04e74fc14922ba497b1f_7.png)

## 编程环境：VS Code

我们将使用一个名为Visual Studio Code（VS Code）的编程环境。这是一个行业标准的工具，我们使用其云端版本，可以通过网址`code.cs50.io`访问。

VS Code的界面包括：
*   **代码标签页**：用于编写代码。
*   **终端窗口**：用于输入命令来编译和运行程序。
*   **文件资源管理器**：用于查看和管理文件。
*   **活动栏**：包含各种功能图标，包括CS50的聊天机器人“小鸭子”。

## 编写第一个C程序

现在，让我们在VS Code中实际编写并运行我们的第一个C程序。

![](img/dd24156253db04e74fc14922ba497b1f_9.png)

以下是创建和运行C程序的基本步骤：

![](img/dd24156253db04e74fc14922ba497b1f_11.png)

1.  **创建源文件**：在终端中输入`code hello.c`来创建一个名为`hello.c`的新文件。
2.  **编写代码**：在代码标签页中输入上述C程序。
3.  **编译程序**：在终端中输入`make hello`。这个命令会调用编译器，将源代码（`hello.c`）转换为机器代码（`hello`）。
4.  **运行程序**：在终端中输入`./hello`来执行编译后的程序。

![](img/dd24156253db04e74fc14922ba497b1f_13.png)

![](img/dd24156253db04e74fc14922ba497b1f_14.png)

如果一切顺利，你将在终端中看到输出“hello, world”。

![](img/dd24156253db04e74fc14922ba497b1f_16.png)

## 理解代码结构

让我们更详细地分解这个简单的C程序。

![](img/dd24156253db04e74fc14922ba497b1f_18.png)

### 头文件

![](img/dd24156253db04e74fc14922ba497b1f_20.png)

![](img/dd24156253db04e74fc14922ba497b1f_22.png)

![](img/dd24156253db04e74fc14922ba497b1f_24.png)

`#include <stdio.h>` 这一行告诉编译器包含标准输入输出库。这个库提供了`printf`等函数。如果不包含这个头文件，编译器将无法识别`printf`函数。

![](img/dd24156253db04e74fc14922ba497b1f_26.png)

### 主函数

![](img/dd24156253db04e74fc14922ba497b1f_28.png)

`int main(void)` 定义了程序的主函数。每个C程序都必须有一个`main`函数，它是程序开始执行的地方。括号内的`void`表示这个函数不接受任何参数。

### 输出函数

`printf` 是一个用于格式化输出的函数。它接受一个字符串作为参数，并将其打印到屏幕上。字符串必须用双引号括起来。

![](img/dd24156253db04e74fc14922ba497b1f_30.png)

### 转义序列

在字符串中，`\n` 是一个转义序列，代表换行符。它告诉计算机将光标移动到下一行的开头。其他常见的转义序列包括：
*   `\"`：打印一个双引号。
*   `\\`：打印一个反斜杠。

## 获取用户输入

在Scratch中，我们使用“询问并等待”积木块来获取用户输入。在C语言中，我们可以使用CS50库中的`get_string`函数来实现类似的功能。

以下是获取用户姓名并打招呼的C程序：

```c
#include <cs50.h>
#include <stdio.h>

int main(void)
{
    string answer = get_string("What's your name? ");
    printf("hello, %s\n", answer);
}
```

在这个程序中：
*   `#include <cs50.h>` 包含了CS50库，它提供了`get_string`和`string`类型。
*   `string answer = get_string("What's your name? ");` 这一行声明了一个名为`answer`的字符串变量，并将用户输入的值赋给它。
*   `printf("hello, %s\n", answer);` 使用`%s`作为占位符，将`answer`变量的值插入到输出字符串中。

## 条件语句

在Scratch中，我们使用“如果-那么”积木块来实现条件判断。在C语言中，我们使用`if`、`else if`和`else`关键字。

以下是一个比较两个数字的C程序：

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

在这个程序中，我们使用`get_int`函数获取两个整数，然后使用条件语句比较它们的大小。

## 循环

![](img/dd24156253db04e74fc14922ba497b1f_32.png)

在Scratch中，我们使用“重复”积木块来执行循环。在C语言中，我们使用`while`、`do while`和`for`循环。

以下是使用`for`循环打印“meow”三次的C程序：

![](img/dd24156253db04e74fc14922ba497b1f_34.png)

```c
#include <stdio.h>

int main(void)
{
    for (int i = 0; i < 3; i++)
    {
        printf("meow\n");
    }
}
```

在这个程序中，`for`循环初始化一个计数器`i`，只要`i < 3`为真，就执行循环体，并在每次迭代后递增`i`。

![](img/dd24156253db04e74fc14922ba497b1f_36.png)

![](img/dd24156253db04e74fc14922ba497b1f_37.png)

![](img/dd24156253db04e74fc14922ba497b1f_39.png)

## 函数

![](img/dd24156253db04e74fc14922ba497b1f_41.png)

在Scratch中，我们可以创建自定义积木块。在C语言中，我们可以创建函数。

以下是一个自定义函数`meow`的C程序：

```c
#include <stdio.h>

void meow(void);

int main(void)
{
    for (int i = 0; i < 3; i++)
    {
        meow();
    }
}

![](img/dd24156253db04e74fc14922ba497b1f_43.png)

![](img/dd24156253db04e74fc14922ba497b1f_44.png)

void meow(void)
{
    printf("meow\n");
}
```

![](img/dd24156253db04e74fc14922ba497b1f_46.png)

在这个程序中：
*   `void meow(void);` 是函数原型，它告诉编译器`meow`函数的存在。
*   `void meow(void)` 是函数定义，它指定了函数的具体实现。

![](img/dd24156253db04e74fc14922ba497b1f_48.png)

## 设计更好的代码

![](img/dd24156253db04e74fc14922ba497b1f_50.png)

在编程中，我们不仅要追求代码的正确性，还要关注代码的设计和风格。

![](img/dd24156253db04e74fc14922ba497b1f_52.png)

![](img/dd24156253db04e74fc14922ba497b1f_53.png)

![](img/dd24156253db04e74fc14922ba497b1f_54.png)

以下是评价代码质量的三个维度：

![](img/dd24156253db04e74fc14922ba497b1f_56.png)

![](img/dd24156253db04e74fc14922ba497b1f_57.png)

![](img/dd24156253db04e74fc14922ba497b1f_59.png)

![](img/dd24156253db04e74fc14922ba497b1f_60.png)

![](img/dd24156253db04e74fc14922ba497b1f_61.png)

![](img/dd24156253db04e74fc14922ba497b1f_62.png)

![](img/dd24156253db04e74fc14922ba497b1f_63.png)

1.  **正确性**：代码是否按照预期工作？
2.  **设计**：代码是否高效、可读性强？
3.  **风格**：代码的格式是否一致、美观？

![](img/dd24156253db04e74fc14922ba497b1f_65.png)

![](img/dd24156253db04e74fc14922ba497b1f_66.png)

![](img/dd24156253db04e74fc14922ba497b1f_68.png)

在CS50中，我们提供了以下工具来帮助改进代码：
*   `check50`：检查代码的正确性。
*   `style50`：检查代码的风格。
*   `design50`：提供代码设计方面的建议。

![](img/dd24156253db04e74fc14922ba497b1f_70.png)

## 常见问题与陷阱

在编程过程中，我们可能会遇到一些常见的问题和陷阱。

### 整数溢出

当整数变量的值超过其所能表示的范围时，会发生整数溢出。例如，32位有符号整数的最大值是2,147,483,647。如果尝试存储更大的值，结果会“绕回”到负数。

```c
#include <stdio.h>
#include <cs50.h>

int main(void)
{
    int dollars = 1;
    while (true)
    {
        char c = get_char("Here's $%i. Double it and give it to the next person? ", dollars);
        if (c == 'y' || c == 'Y')
        {
            dollars *= 2;
        }
        else
        {
            break;
        }
    }
    printf("You're walking away with $%i.\n", dollars);
}
```

在这个程序中，如果不断同意加倍，`dollars`的值最终会溢出，变成负数或零。

### 浮点数精度

计算机使用有限数量的位来表示浮点数，因此无法精确表示所有实数。这可能导致精度误差。

```c
#include <stdio.h>
#include <cs50.h>

int main(void)
{
    int x = get_int("What's x? ");
    int y = get_int("What's y? ");
    printf("%.50f\n", (float) x / y);
}
```

在这个程序中，即使用`float`类型进行除法，结果也可能显示不精确的小数部分。

## 总结

![](img/dd24156253db04e74fc14922ba497b1f_72.png)

本节课中我们一起学习了C语言的基本概念和语法。我们从Scratch过渡到C，编写了第一个“Hello, World!”程序，并探索了变量、条件语句、循环和函数等核心概念。我们还讨论了代码的正确性、设计和风格，以及整数溢出和浮点数精度等常见问题。通过不断练习和探索，你将逐渐掌握C语言编程，并能够构建更复杂的程序。