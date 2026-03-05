# 007：键盘驱动 🎹

在本节课中，我们将学习如何响应硬件中断，并实现一个键盘驱动程序，使我们能够从键盘接收输入并在屏幕上显示出来。

## 概述

上一节我们成功建立了CPU与可编程中断控制器（PIC）的连接，并接收到了来自硬件时钟的第一个中断。然而，系统在接收到中断后停止了运行，因为我们没有向PIC发送中断处理完成的确认信号。本节中，我们将解决这个问题，并构建一个面向对象的键盘驱动框架。

## 从静态函数回到对象

![](img/97221e766c222cd97bf1e14d0769de1c_1.png)

我们面临的问题是，当硬件中断发生时，CPU会从C++世界跳转到汇编代码，最终进入一个静态的C++处理函数。为了利用面向对象的特性，我们需要从这个静态函数回到`InterruptManager`对象实例中，以便访问与PIC通信的端口。

以下是解决方案：我们在`interrupts.h`中定义一个指向当前活动中断管理器的静态指针。

```cpp
class InterruptManager {
    ...
    static InterruptManager* ActiveInterruptManager;
    ...
};
```

在`interrupts.cpp`中初始化这个静态指针，并在`InterruptManager`的`Activate`和`Deactivate`方法中设置它。

![](img/97221e766c222cd97bf1e14d0769de1c_3.png)

![](img/97221e766c222cd97bf1e14d0769de1c_5.png)

![](img/97221e766c222cd97bf1e14d0769de1c_6.png)

![](img/97221e766c222cd97bf1e14d0769de1c_7.png)

![](img/97221e766c222cd97bf1e14d0769de1c_8.png)

```cpp
InterruptManager* InterruptManager::ActiveInterruptManager = 0;

![](img/97221e766c222cd97bf1e14d0769de1c_10.png)

InterruptManager::InterruptManager(...) {
    ...
    if(ActiveInterruptManager != 0)
        ActiveInterruptManager->Deactivate();
    ActiveInterruptManager = this;
    ...
}
```

![](img/97221e766c222cd97bf1e14d0769de1c_12.png)

现在，在汇编代码调用的静态处理函数`HandleInterrupt`中，我们可以通过这个静态指针调用对象实例的`DoHandleInterrupt`方法。

![](img/97221e766c222cd97bf1e14d0769de1c_14.png)

![](img/97221e766c222cd97bf1e14d0769de1c_16.png)

```cpp
extern "C" void HandleInterrupt(...) {
    if(InterruptManager::ActiveInterruptManager != 0) {
        InterruptManager::ActiveInterruptManager->DoHandleInterrupt(...);
    }
}
```

![](img/97221e766c222cd97bf1e14d0769de1c_18.png)

这样，我们就成功地从静态环境回到了对象实例中，可以访问PIC的端口了。

![](img/97221e766c222cd97bf1e14d0769de1c_20.png)

![](img/97221e766c222cd97bf1e14d0769de1c_22.png)

## 向PIC发送中断结束信号

![](img/97221e766c222cd97bf1e14d0769de1c_24.png)

在`DoHandleInterrupt`方法中，我们现在可以向PIC发送中断处理完成的确认信号（EOI - End Of Interrupt）。这是通过向PIC的命令端口（主PIC为0x20，从PIC为0xA0）写入特定值（0x20）来实现的。

我们需要为所有硬件中断（我们已将其重映射到0x20到0x2F）发送EOI。如果中断号大于等于0x28（即来自从PIC的中断），我们需要同时向主PIC和从PIC发送EOI。

```cpp
void InterruptManager::DoHandleInterrupt(...) {
    // ... 处理中断 ...

    // 发送EOI给PIC
    if(0x20 <= interruptNumber && interruptNumber < 0x30) {
        commandPort.Write(0x20); // 主PIC EOI
        if(0x28 <= interruptNumber)
            commandPort.Write(0x20); // 从PIC EOI
    }
}
```

![](img/97221e766c222cd97bf1e14d0769de1c_26.png)

![](img/97221e766c222cd97bf1e14d0769de1c_28.png)

![](img/97221e766c222cd97bf1e14d0769de1c_29.png)

完成这一步后，系统将能够持续接收和处理中断，而不会停止。

![](img/97221e766c222cd97bf1e14d0769de1c_30.png)

![](img/97221e766c222cd97bf1e14d0769de1c_32.png)

![](img/97221e766c222cd97bf1e14d0769de1c_33.png)

![](img/97221e766c222cd97bf1e14d0769de1c_35.png)

## 创建中断处理器基类

![](img/97221e766c222cd97bf1e14d0769de1c_37.png)

为了以面向对象的方式处理不同的硬件中断（如键盘、鼠标），我们创建一个`InterruptHandler`基类。每个具体的驱动程序（如键盘驱动）都将继承自这个类。

以下是`InterruptHandler`基类的定义：

```cpp
class InterruptHandler {
protected:
    InterruptManager* interruptManager;
    uint8_t interruptNumber;

    InterruptHandler(InterruptManager* manager, uint8_t num);
    ~InterruptHandler();
public:
    virtual uint32_t HandleInterrupt(uint32_t esp);
};
```

![](img/97221e766c222cd97bf1e14d0769de1c_39.png)

![](img/97221e766c222cd97bf1e14d0769de1c_41.png)

`InterruptManager`类需要维护一个`InterruptHandler`指针数组。在构造函数中，`InterruptHandler`将自己注册到管理器的这个数组中。在`DoHandleInterrupt`方法中，管理器会查找并调用对应中断号的处理器的`HandleInterrupt`方法。

![](img/97221e766c222cd97bf1e14d0769de1c_43.png)

![](img/97221e766c222cd97bf1e14d0769de1c_44.png)

```cpp
// 在 InterruptManager::DoHandleInterrupt 中
if(handlers[interruptNumber] != 0) {
    esp = handlers[interruptNumber]->HandleInterrupt(esp);
} else {
    // 打印未处理的中断信息
}
```

## 实现键盘驱动程序

![](img/97221e766c222cd97bf1e14d0769de1c_46.png)

![](img/97221e766c222cd97bf1e14d0769de1c_48.png)

![](img/97221e766c222cd97bf1e14d0769de1c_49.png)

现在我们可以创建具体的键盘驱动类`KeyboardDriver`，它继承自`InterruptHandler`。

![](img/97221e766c222cd97bf1e14d0769de1c_51.png)

键盘使用两个I/O端口：
*   **数据端口**：`0x60`，用于读取按键扫描码。
*   **命令端口**：`0x64`，用于向键盘控制器发送命令。

![](img/97221e766c222cd97bf1e14d0769de1c_53.png)

以下是`KeyboardDriver`构造函数的关键步骤，用于初始化和激活键盘：

![](img/97221e766c222cd97bf1e14d0769de1c_55.png)

```cpp
KeyboardDriver::KeyboardDriver(InterruptManager* manager)
    : InterruptHandler(manager, 0x21), // 键盘中断号为0x21
      dataPort(0x60),
      commandPort(0x64) {

    // 清空可能存在的旧按键数据
    while(dataPort.Read() & 0x1);
    // 激活键盘中断
    commandPort.Write(0xAE); // 激活中断
    commandPort.Write(0x20); // 获取当前状态
    uint8_t status = (dataPort.Read() | 1) & ~0x10;
    commandPort.Write(0x60); // 设置状态
    dataPort.Write(status);
}
```

![](img/97221e766c222cd97bf1e14d0769de1c_57.png)

![](img/97221e766c222cd97bf1e14d0769de1c_59.png)

![](img/97221e766c222cd97bf1e14d0769de1c_61.png)

在`HandleInterrupt`方法中，我们从数据端口读取扫描码，并将其转换为可显示的字符。

![](img/97221e766c222cd97bf1e14d0769de1c_63.png)

![](img/97221e766c222cd97bf1e14d0769de1c_65.png)

![](img/97221e766c222cd97bf1e14d0769de1c_67.png)

```cpp
uint32_t KeyboardDriver::HandleInterrupt(uint32_t esp) {
    uint8_t key = dataPort.Read();

    // 忽略某些状态码和NumLock等特殊键
    if(key < 0x80) {
        switch(key) {
            case 0x1E: // 'A' 键的扫描码（示例，因键盘布局而异）
                printf("a");
                break;
            case 0x15: // 'Z' 键的扫描码（在德语键盘上是Y）
                printf("z");
                break;
            // ... 为其他键添加更多case ...
            default:
                printf("KEYBOARD 0x%X", key);
                break;
        }
    }
    return esp;
}
```

![](img/97221e766c222cd97bf1e14d0769de1c_69.png)

![](img/97221e766c222cd97bf1e14d0769de1c_71.png)

![](img/97221e766c222cd97bf1e14d0769de1c_73.png)

![](img/97221e766c222cd97bf1e14d0769de1c_75.png)

**请注意**：从键盘读取的原始扫描码与物理按键对应，而不是字符。不同布局的键盘（如美式、德式）对同一扫描码的解释不同。因此，你需要根据你的键盘布局创建一个完整的扫描码到字符的映射表。

![](img/97221e766c222cd97bf1e14d0769de1c_76.png)

![](img/97221e766c222cd97bf1e14d0769de1c_78.png)

## 在真实硬件上运行

一个重要的注意事项是，本教程中使用的PS/2风格键盘通信方式，在现代计算机上可能无法直接工作，因为大多数现代键盘通过USB连接。

*   在虚拟机（如VirtualBox）中，虚拟硬件模拟了PS/2接口，因此代码可以正常工作。
*   在真实硬件上，你可能需要在BIOS/UEFI设置中启用“Legacy USB Support”或“USB Keyboard Emulation”等选项。该选项会让主板芯片组将USB键盘模拟成PS/2键盘，从而使你的操作系统能够识别。
*   未来，当我们实现USB驱动后，才能原生支持USB键盘。

## 总结

本节课中我们一起学习了操作系统开发的关键一步：实现硬件中断的完整处理流程和键盘输入。

![](img/97221e766c222cd97bf1e14d0769de1c_80.png)

1.  **中断确认**：我们解决了上一节遗留的问题，学会了在中断处理完成后必须向PIC发送EOI信号，否则系统将无法接收后续中断。
2.  **面向对象设计**：通过引入静态指针和`InterruptHandler`基类，我们将中断处理从静态函数迁移到了灵活、可扩展的面向对象框架中。
3.  **键盘驱动**：我们创建了`KeyboardDriver`类，它通过读写特定I/O端口与键盘控制器通信，将原始的按键扫描码转换为字符输出到屏幕。
4.  **现实挑战**：我们了解了扫描码映射的复杂性以及USB键盘在真实硬件上带来的兼容性挑战。

至此，最复杂的基础设施（引导加载程序、GDT、IDT、汇编胶水代码）已经搭建完毕。从下一节开始，我们将基于这个稳固的基础，更快地实现更多功能（例如鼠标驱动），真正开始构建操作系统的上层功能。