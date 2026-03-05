# 编写你自己的操作系统：4：硬件通信与端口 🖥️

在本节课中，我们将学习如何与计算机硬件进行通信。上一节我们介绍了操作系统开发的基础，本节中我们来看看与硬件交互的核心机制——端口。

## 概述

CPU与键盘、鼠标等硬件设备通信，需要通过一种称为“端口”的机制。端口是硬件设备的地址，CPU通过向特定端口发送或接收数据来与设备交互。本节将创建一个面向对象的端口类，用于封装这种通信，并改进我们的屏幕输出功能。

## 端口通信原理

当你在键盘上按下一个键时，一个信号会发送到可编程中断控制器。默认情况下，PIC会忽略这个信号。为了接收按键信息，我们必须通过端口告诉PIC不要忽略它。

因此，在与硬件进行双向通信之前，我们需要一种方法来发送和接收数据。中断（将在下一节讨论）会通知CPU何时有数据需要接收。

从技术上讲，CPU通过一个多路复用器和解复用器连接到不同的硬件。你可以向这个系统输入一个端口号，它就会将数据发送到或从该端口接收数据。例如，PIC的端口号是 `0x20`。

在汇编语言中，使用 `out` 指令向端口发送数据。它接受两个参数：端口号和要发送的数据。然而，我们使用C++编程，需要一种更优雅的方式。

## 创建端口类

直接内联汇编代码调用 `out` 指令的方式不够面向对象。理想的设计是创建一个 `Port` 对象，它知道自己的端口号和带宽（8位、16位或32位），并提供 `Read` 和 `Write` 方法。这样，使用者就无需关心底层细节。

以下是创建端口类的步骤：

1.  **创建基类**：`Port` 基类存储端口号，并定义纯虚的读写接口。
2.  **创建派生类**：创建 `Port8Bit`、`Port16Bit`、`Port32Bit` 等派生类，实现特定带宽的读写操作。
3.  **处理慢速端口**：某些8位端口写入后需要等待，因此可以创建一个 `Port8BitSlow` 类来继承 `Port8Bit` 并重写 `Write` 方法，在写入后添加空操作指令以延迟。

### 代码实现

首先，创建头文件 `port.h`：

```cpp
#ifndef PORT_H
#define PORT_H

![](img/255810a0e158f70dcd8fb72cf29aa6ac_1.png)

#include “types.h”

![](img/255810a0e158f70dcd8fb72cf29aa6ac_3.png)

![](img/255810a0e158f70dcd8fb72cf29aa6ac_5.png)

class Port {
protected:
    Port(uint16_t portnumber);
    ~Port();
    uint16_t portnumber;
};

class Port8Bit : public Port {
public:
    Port8Bit(uint16_t portnumber);
    ~Port8Bit();
    virtual void Write(uint8_t data);
    virtual uint8_t Read();
};

class Port8BitSlow : public Port8Bit {
public:
    Port8BitSlow(uint16_t portnumber);
    ~Port8BitSlow();
    virtual void Write(uint8_t data);
};

class Port16Bit : public Port {
public:
    Port16Bit(uint16_t portnumber);
    ~Port16Bit();
    void Write(uint16_t data);
    uint16_t Read();
};

class Port32Bit : public Port {
public:
    Port32Bit(uint16_t portnumber);
    ~Port32Bit();
    void Write(uint32_t data);
    uint32_t Read();
};

#endif
```

接着，在 `port.cpp` 中实现这些类：

```cpp
#include “port.h”

Port::Port(uint16_t portnumber) {
    this->portnumber = portnumber;
}
Port::~Port() {}

![](img/255810a0e158f70dcd8fb72cf29aa6ac_7.png)

![](img/255810a0e158f70dcd8fb72cf29aa6ac_9.png)

![](img/255810a0e158f70dcd8fb72cf29aa6ac_11.png)

![](img/255810a0e158f70dcd8fb72cf29aa6ac_12.png)

Port8Bit::Port8Bit(uint16_t portnumber) : Port(portnumber) {}
Port8Bit::~Port8Bit() {}
void Port8Bit::Write(uint8_t data) {
    __asm__ volatile(“outb %0, %1” : : “a”(data), “Nd”(portnumber));
}
uint8_t Port8Bit::Read() {
    uint8_t result;
    __asm__ volatile(“inb %1, %0” : “=a”(result) : “Nd”(portnumber));
    return result;
}

![](img/255810a0e158f70dcd8fb72cf29aa6ac_14.png)

Port8BitSlow::Port8BitSlow(uint16_t portnumber) : Port8Bit(portnumber) {}
Port8BitSlow::~Port8BitSlow() {}
void Port8BitSlow::Write(uint8_t data) {
    __asm__ volatile(“outb %0, %1\njmp 1f\n1: jmp 1f\n1:” : : “a”(data), “Nd”(portnumber));
}

![](img/255810a0e158f70dcd8fb72cf29aa6ac_16.png)

Port16Bit::Port16Bit(uint16_t portnumber) : Port(portnumber) {}
Port16Bit::~Port16Bit() {}
void Port16Bit::Write(uint16_t data) {
    __asm__ volatile(“outw %0, %1” : : “a”(data), “Nd”(portnumber));
}
uint16_t Port16Bit::Read() {
    uint16_t result;
    __asm__ volatile(“inw %1, %0” : “=a”(result) : “Nd”(portnumber));
    return result;
}

![](img/255810a0e158f70dcd8fb72cf29aa6ac_18.png)

Port32Bit::Port32Bit(uint16_t portnumber) : Port(portnumber) {}
Port32Bit::~Port32Bit() {}
void Port32Bit::Write(uint32_t data) {
    __asm__ volatile(“outl %0, %1” : : “a”(data), “Nd”(portnumber));
}
uint32_t Port32Bit::Read() {
    uint32_t result;
    __asm__ volatile(“inl %1, %0” : “=a”(result) : “Nd”(portnumber));
    return result;
}
```

![](img/255810a0e158f70dcd8fb72cf29aa6ac_20.png)

最后，将 `port.cpp` 添加到 `Makefile` 的编译源文件中。

![](img/255810a0e158f70dcd8fb72cf29aa6ac_22.png)

## 改进 Makefile：添加清理功能

为了方便开发，我们在 `Makefile` 中添加一个标准的 `clean` 目标，用于删除所有生成的目标文件和可执行文件。

![](img/255810a0e158f70dcd8fb72cf29aa6ac_24.png)

```makefile
clean:
    rm -f *.o
    rm -f mykernel.bin
    rm -f mykernel
```

运行 `make clean` 后，可以重新运行 `make run` 来构建一切。

## 改进屏幕输出：实现光标和换行

![](img/255810a0e158f70dcd8fb72cf29aa6ac_26.png)

![](img/255810a0e158f70dcd8fb72cf29aa6ac_28.png)

我们当前的 `printf` 函数有一个问题：每次调用都从屏幕左上角开始写入，会覆盖之前的内容。我们需要实现一个光标系统来跟踪下一个字符的写入位置。

屏幕是80字符宽、25行高。光标位置可以通过公式计算：

![](img/255810a0e158f70dcd8fb72cf29aa6ac_30.png)

**内存位置 = 80 * y + x**

![](img/255810a0e158f70dcd8fb72cf29aa6ac_32.png)

其中 `x` 是列号，`y` 是行号。

以下是改进 `printf` 的逻辑：

![](img/255810a0e158f70dcd8fb72cf29aa6ac_34.png)

1.  根据光标位置 `(x, y)` 计算视频内存地址。
2.  写入字符后，`x` 增加。
3.  如果 `x >= 80`，则执行换行：`x = 0`, `y++`。
4.  如果 `y >= 25`（屏幕已满），则清屏（将所有位置写入空格），并将光标重置到 `(0, 0)`。
5.  支持 `\n` 换行符：当遇到 `\n` 时，直接执行换行操作。

![](img/255810a0e158f70dcd8fb72cf29aa6ac_36.png)

![](img/255810a0e158f70dcd8fb72cf29aa6ac_37.png)

![](img/255810a0e158f70dcd8fb72cf29aa6ac_39.png)

![](img/255810a0e158f70dcd8fb72cf29aa6ac_40.png)

改进后的 `printf` 函数将表现得更加符合预期。

## 总结

本节课中我们一起学习了硬件通信的基础。我们创建了一个面向对象的端口类库，用于封装不同带宽的端口读写操作，这为后续与键盘等硬件交互打下了基础。同时，我们改进了 `Makefile` 并实现了带光标和换行功能的屏幕输出，使我们的操作系统雏形更加实用。下一节，我们将开始与可编程中断控制器通信，并通过中断真正接收来自硬件的数据。