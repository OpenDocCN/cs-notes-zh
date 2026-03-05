# 编写你自己的操作系统：P8：鼠标驱动 🖱️

![](img/3e7b57a65ebc69688a6a55c003bd59af_0.png)

在本节课中，我们将学习如何为我们的操作系统添加鼠标支持。鼠标与键盘类似，都是通过中断与系统通信。我们将了解如何接收鼠标数据包、解析鼠标移动和按键信息，并在屏幕上显示一个简单的光标。

上一节我们介绍了键盘驱动，本节中我们来看看如何实现鼠标驱动。

![](img/3e7b57a65ebc69688a6a55c003bd59af_2.png)

![](img/3e7b57a65ebc69688a6a55c003bd59af_4.png)

## 准备工作与键盘功能完善

![](img/3e7b57a65ebc69688a6a55c003bd59af_6.png)

![](img/3e7b57a65ebc69688a6a55c003bd59af_8.png)

在开始鼠标驱动之前，我们先回顾一下键盘功能的改进。为了处理大小写字母，我们添加了一个静态布尔变量 `shift` 来跟踪 Shift 键的状态。

以下是关键代码逻辑：
```c
static bool shift = false;
// ... 在键盘中断处理中 ...
case 0x2A: // 左Shift按下
case 0x36: // 右Shift按下
    shift = true;
    break;
case 0xAA: // 左Shift释放
case 0xB6: // 右Shift释放
    shift = false;
    break;
case 0x1E: // 'A' 键
    if(shift) {
        // 输出大写 'A'
    } else {
        // 输出小写 'a'
    }
    break;
```

此外，为了避免编译器警告，我们在 Makefile 的 GCC 参数中添加了 `-Wno-builtin-declaration-mismatch`。

## 鼠标驱动概述

![](img/3e7b57a65ebc69688a6a55c003bd59af_10.png)

鼠标驱动与键盘驱动非常相似。主要区别在于，鼠标每次事件（移动或按键）会发送一个由三个字节组成的数据包。我们需要完整接收这三个字节才能正确解析鼠标状态。

![](img/3e7b57a65ebc69688a6a55c003bd59af_12.png)

我们将创建一个三字节的缓冲区来存储数据包，并使用一个偏移量来跟踪当前接收的是第几个字节。

![](img/3e7b57a65ebc69688a6a55c003bd59af_14.png)

## 实现鼠标驱动

![](img/3e7b57a65ebc69688a6a55c003bd59af_16.png)

首先，我们创建鼠标驱动的头文件，其结构与键盘驱动类似。

以下是鼠标驱动的核心数据结构：
```c
class MouseDriver : public InterruptHandler {
    Port8Bit dataPort;
    Port8Bit commandPort;
    uint8_t buffer[3];
    uint8_t offset;
    uint8_t buttons;
    int8_t x, y;
public:
    MouseDriver(InterruptManager* manager);
    ~MouseDriver();
    virtual uint32_t HandleInterrupt(uint32_t esp);
};
```

### 初始化鼠标

在构造函数中，我们需要初始化鼠标并启用中断。

![](img/3e7b57a65ebc69688a6a55c003bd59af_18.png)

![](img/3e7b57a65ebc69688a6a55c003bd59af_20.png)

以下是初始化步骤：
1.  向命令端口写入 `0xA8` 以启用鼠标。
2.  向命令端口写入 `0x20` 请求当前状态。
3.  读取数据端口，将第二位（`0x02`）置为1以启用鼠标中断。
4.  将新状态写回命令端口 `0x60`。
5.  向命令端口写入 `0xD4` 后，再向数据端口写入 `0xF4` 以激活鼠标。

![](img/3e7b57a65ebc69688a6a55c003bd59af_22.png)

### 处理鼠标中断

![](img/3e7b57a65ebc69688a6a55c003bd59af_24.png)

鼠标使用中断号 `0x2C`。在中断处理程序中，我们需要读取状态端口，检查是否有数据可读（状态的第6位为1）。

![](img/3e7b57a65ebc69688a6a55c003bd59af_26.png)

以下是中断处理流程：
1.  从数据端口读取一个字节，存入 `buffer[offset]`。
2.  偏移量 `offset` 加1，对3取模，确保在0、1、2之间循环。
3.  当完成一个数据包的接收（即 `offset` 再次为0）时，解析 `buffer` 中的三个字节。

### 解析鼠标数据包

![](img/3e7b57a65ebc69688a6a55c003bd59af_28.png)

一个完整的三字节数据包包含以下信息：
*   **字节0 (`buffer[0]`)**： 按键状态和标志位。
*   **字节1 (`buffer[1]`)**： X轴移动量（有符号）。
*   **字节2 (`buffer[2]`)**： Y轴移动量（有符号，方向与直觉相反）。

以下是解析和更新光标位置的代码：
```c
if(offset == 0) {
    // 恢复旧光标位置的颜色
    // ...

    // 更新光标位置
    x += buffer[1];
    y -= buffer[2]; // Y轴方向相反

    // 限制光标在屏幕范围内 (0-79, 0-24)
    if(x < 0) x = 0;
    if(x >= 80) x = 79;
    if(y < 0) y = 0;
    if(y >= 25) y = 24;

    // 在新光标位置翻转颜色以显示光标
    // ...

    // 处理按键状态变化
    for(uint8_t i = 0; i < 3; i++) {
        if((buffer[0] & (1<<i)) != (buttons & (1<<i))) {
            // 第 i 个按键状态发生了变化
            // 可以在这里添加按键处理逻辑
        }
    }
    // 更新旧的按键状态
    buttons = buffer[0];
}
```

![](img/3e7b57a65ebc69688a6a55c003bd59af_30.png)

### 在屏幕上显示光标

![](img/3e7b57a65ebc69688a6a55c003bd59af_32.png)

我们通过翻转屏幕上光标所在位置字符的前景色和背景色来模拟光标。

![](img/3e7b57a65ebc69688a6a55c003bd59af_34.png)

![](img/3e7b57a65ebc69688a6a55c003bd59af_36.png)

![](img/3e7b57a65ebc69688a6a55c003bd59af_37.png)

![](img/3e7b57a65ebc69688a6a55c003bd59af_38.png)

以下是翻转颜色的公式：
```c
// 假设 videoMemory 是 uint16_t* 类型，指向 0xB8000
uint16_t* location = videoMemory + (80 * y + x);
uint8_t character = (*location) & 0xFF; // 低字节是字符
uint8_t attribute = (*location >> 8) & 0xFF; // 高字节是属性

// 翻转前景色和背景色
uint8_t newAttribute = ((attribute & 0xF0) >> 4) | ((attribute & 0x0F) << 4);

![](img/3e7b57a65ebc69688a6a55c003bd59af_40.png)

// 写回视频内存
*location = character | (newAttribute << 8);
```

![](img/3e7b57a65ebc69688a6a55c003bd59af_42.png)

![](img/3e7b57a65ebc69688a6a55c003bd59af_44.png)

## 注意事项与调试技巧

在实现过程中，你可能会遇到鼠标行为异常的问题。一个常见的原因是数据包接收的起始偏移量 `offset` 不正确。它可能不是从0开始。

如果鼠标行为异常，首先尝试将 `offset` 的初始值在0、1、2之间切换。这是一个快速的调试方法。

![](img/3e7b57a65ebc69688a6a55c003bd59af_46.png)

![](img/3e7b57a65ebc69688a6a55c003bd59af_48.png)

另外，在虚拟机中运行时，鼠标可能默认被主机捕获。你需要按键盘右侧的 `Ctrl` 键将鼠标控制权释放给客户操作系统。

## 代码结构与设计思考

目前，我们在鼠标驱动中断处理程序中直接操作了视频内存。这在设计上是不好的，因为它将硬件驱动与具体的用户界面逻辑紧密耦合。

![](img/3e7b57a65ebc69688a6a55c003bd59af_50.png)

更好的设计是创建一个 `MouseEventHandler` 类，其中包含诸如 `OnMouseMove`、`OnButtonDown`、`OnButtonUp` 等虚方法。然后，在鼠标驱动中持有该处理器的一个指针或引用，并在适当的时候调用这些方法。这样可以将输入事件的处理逻辑与底层驱动分离开来。

![](img/3e7b57a65ebc69688a6a55c003bd59af_52.png)

## 总结与展望

![](img/3e7b57a65ebc69688a6a55c003bd59af_54.png)

本节课中我们一起学习了如何为操作系统实现鼠标驱动。我们了解了鼠标数据包的格式，学会了如何接收和解析鼠标的移动与按键信息，并在屏幕上实现了一个简单可见的光标。

至此，我们的操作系统已经具备了基本的人机交互能力：可以启动、向屏幕输出、接收和处理中断、响应键盘输入以及跟踪鼠标。

![](img/3e7b57a65ebc69688a6a55c003bd59af_56.png)

在接下来的课程中，我们将暂时停下功能开发，转而整理项目结构，使其更清晰、更易于扩展，为后续实现更复杂的功能（如网络、图形模式等）打下坚实的基础。