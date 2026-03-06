# 019：从C代码调用UART子程序 🚀

在本节课中，我们将学习如何从C语言代码中调用我们之前编写的UART（通用异步收发传输器）汇编子程序。我们将创建一个项目，将汇编子程序导出，并在C语言中调用它们，最终实现与C标准输入输出库（如`printf`和`scanf`）的绑定，以便更方便地进行串口通信。

## 项目准备与文件结构

上一节我们完成了UART功能的汇编实现。本节中，我们来看看如何将这些功能集成到C语言项目中。

首先，我们需要复制并重命名上一个项目，并创建新的文件。

以下是创建项目文件结构的步骤：
1.  复制上一个项目，并重命名为新项目（例如“09_UART_Call_From_C”）。
2.  在项目中添加一个新的C源文件 `main.c`。
3.  添加一个新的汇编源文件 `uart.s`。
4.  将旧项目 `main.s` 文件中的汇编代码复制到新的 `uart.s` 文件中。
5.  从项目中移除旧的 `main.s` 文件。

## 修改汇编文件：导出子程序

现在，我们需要修改 `uart.s` 文件，使其不再是程序的入口点，而是作为一个包含可调用子程序的库文件。

我们需要使用 `EXPORT` 关键字来声明我们希望从C代码中访问的子程序。同时，可以移除或注释掉与LED初始化相关的代码，因为本教程专注于UART功能。

修改后的 `uart.s` 文件关键部分如下：
```assembly
    EXPORT uart_init
    EXPORT uart_read_char
    EXPORT uart_write_char

uart_init:
    ; ... 初始化代码 (移除了LED部分) ...
    BX LR

uart_read_char:
    ; ... 读取字符的代码 ...
    BX LR

![](img/1f32b935d0cd38192028add8c2e2af61_1.png)

![](img/1f32b935d0cd38192028add8c2e2af61_2.png)

uart_write_char:
    ; ... 写入字符的代码 ...
    BX LR
```
通过 `EXPORT` 指令，`uart_init`、`uart_read_char` 和 `uart_write_char` 这三个子程序就可以被外部C文件调用了。

## 创建C语言主程序

接下来，我们在 `main.c` 文件中编写C语言代码来调用这些汇编子程序。

首先，我们需要声明这些外部函数。在C语言中，我们使用 `extern` 关键字来声明定义在其他文件（这里是汇编文件）中的函数。

```c
// 声明外部汇编函数
extern void uart_init(void);
extern void uart_write_char(char c);
extern char uart_read_char(void);
```
声明完成后，我们就可以在 `main` 函数中调用它们了。一个简单的测试是初始化UART后，发送一个字符‘H’。
```c
int main(void)
{
    uart_init();          // 初始化UART
    uart_write_char('H'); // 发送字符 'H'
    while(1)
    {
        // 主循环
    }
}
```
编译并下载程序到开发板后，打开串口调试工具，应该能看到不断输出的‘H’字符，这证明从C调用汇编子程序成功。

## 绑定C标准库：实现printf和scanf

为了能使用 `printf` 和 `scanf` 这样强大的格式化输入输出函数，我们需要将C标准库的底层输入输出重定向到我们的UART函数。这通过实现 `_read` 和 `_write` 系统调用（或类似的底层IO函数）来完成。

具体来说，我们需要实现 `fgetc` 和 `fputc` 函数，它们会被标准库的 `printf` 和 `scanf` 调用。

以下是 `main.c` 中实现重定向的关键代码：
```c
#include <stdio.h>
#include <rt_sys.h>

// 重定向标准输入：从UART读取字符
int fgetc(FILE *f) {
    char c = uart_read_char(); // 调用汇编函数读取字符
    if (c == '\r') {           // 如果收到回车符，转换为换行符并回显
        uart_write_char(c);
        c = '\n';
    }
    uart_write_char(c);        // 回显字符
    return (int)c;
}

// 重定向标准输出：向UART写入字符
int fputc(int c, FILE *f) {
    uart_write_char((char)c);  // 调用汇编函数写入字符
    return c;
}
```
这段代码将标准输入（键盘）映射到从UART读取数据，将标准输出（屏幕）映射到向UART写入数据。这样，`printf` 函数就会自动通过UART发送字符串，`scanf` 函数则会从UART接收数据。

## 功能测试

绑定完成后，我们就可以在C代码中自由地使用 `printf` 和 `scanf` 了。下面是一个简单的测试函数：
```c
void test_io(void) {
    int num;
    char str[80];

    printf("Please enter a number:\n");
    scanf("%d", &num);
    printf("The number entered is: %d\n", num);

    printf("Please type a character string:\n");
    scanf("%s", str);
    printf("The string entered is: %s\n", str);

    printf("Hello, Assembly World!\n");
}

![](img/1f32b935d0cd38192028add8c2e2af61_4.png)

int main(void) {
    uart_init();  // 初始化UART
    test_io();    // 运行测试
    while(1);
}
```
编译并运行程序，通过串口终端，你可以看到提示信息，输入数字和字符串后，程序会正确地回显你输入的内容，并打印出“Hello, Assembly World!”。这证明了我们的UART汇编子程序已成功与C标准输入输出库集成。

![](img/1f32b935d0cd38192028add8c2e2af61_6.png)

## 总结

![](img/1f32b935d0cd38192028add8c2e2af61_8.png)

本节课中我们一起学习了如何从C代码调用ARM汇编语言编写的UART子程序。我们首先创建了独立的汇编模块并导出函数，然后在C语言中声明并调用这些函数。最后，通过重定向C标准库的底层IO函数，我们实现了 `printf` 和 `scanf` 与硬件UART的绑定，从而能够以更熟悉、更强大的方式进行串口通信开发。这套方法为混合语言编程和嵌入式系统开发提供了坚实的基础。