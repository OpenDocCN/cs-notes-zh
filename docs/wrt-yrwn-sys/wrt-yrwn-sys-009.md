# 009：驱动程序的抽象 🚀

在本节课中，我们将对项目进行整理和抽象。首先，我们将为驱动程序创建一个通用的基类和管理器，以简化代码结构。接着，我们将重构键盘和鼠标驱动程序的输出逻辑，使其更加模块化和可扩展。

## 项目整理的必要性

随着项目代码量的增加，代码结构会变得越来越混乱。为了避免未来难以维护，我们需要尽早进行整理。本节中，我们将首先关注驱动程序的抽象。

## 创建驱动程序基类

上一节我们介绍了具体的键盘和鼠标驱动程序。本节中，我们来看看如何为它们创建一个通用的基类。

我们首先创建两个新文件：`driver.h` 和 `driver.cpp`。在基类中，我们将定义几个核心方法。

![](img/92dddb41e74c356cbdf24295a45e4617_1.png)

![](img/92dddb41e74c356cbdf24295a45e4617_2.png)

以下是驱动程序基类的核心方法：
```cpp
class Driver {
public:
    Driver();
    ~Driver();

    virtual void Activate();
    virtual int Reset();
    virtual void Deactivate();
};
```
*   `Activate()` 方法用于激活硬件。
*   `Reset()` 方法用于重置硬件，并返回需要等待的毫秒数，以确保硬件进入已知状态。
*   `Deactivate()` 方法用于停用硬件。

## 实现驱动程序管理器

为了统一管理所有驱动程序，我们需要一个驱动程序管理器。由于目前还没有动态内存管理，我们将使用一个固定长度的数组来存储驱动程序指针。

![](img/92dddb41e74c356cbdf24295a45e4617_4.png)

以下是驱动程序管理器的核心结构：
```cpp
class DriverManager {
private:
    Driver* drivers[256];
    int numDrivers;

![](img/92dddb41e74c356cbdf24295a45e4617_6.png)

public:
    DriverManager();
    void AddDriver(Driver* driver);
    void ActivateAll();
};
```
驱动程序管理器将负责存储所有驱动程序实例，并在系统启动时统一激活它们。

## 集成键盘和鼠标驱动程序

现在，我们需要让键盘驱动程序和鼠标驱动程序继承自这个新的 `Driver` 基类。

以下是集成步骤：
1.  修改键盘和鼠标驱动程序的类定义，使其继承自 `Driver`。
2.  将硬件初始化的代码移动到基类的 `Activate()` 方法中。
3.  在驱动程序管理器中添加键盘和鼠标驱动程序的实例。

完成集成后，内核只需调用驱动程序管理器的 `ActivateAll()` 方法，即可按顺序初始化所有硬件。

## 重构输出逻辑

目前，键盘驱动程序直接将按键打印到屏幕，这不利于未来的扩展（例如切换到图形模式）。我们将采用面向对象的方式处理这个问题。

![](img/92dddb41e74c356cbdf24295a45e4617_8.png)

![](img/92dddb41e74c356cbdf24295a45e4617_10.png)

我们将创建一个 `KeyboardEventHandler` 类，用于处理键盘事件。

![](img/92dddb41e74c356cbdf24295a45e4617_11.png)

![](img/92dddb41e74c356cbdf24295a45e4617_12.png)

以下是事件处理器的核心结构：
```cpp
class KeyboardEventHandler {
public:
    KeyboardEventHandler();
    virtual void OnKeyDown(char c);
    virtual void OnKeyUp(char c);
};
```
键盘驱动程序将持有一个事件处理器的指针。当按键事件发生时，驱动程序不再直接打印，而是调用事件处理器的对应方法（如 `OnKeyDown`）。默认的事件处理器可以什么都不做。如果我们希望恢复打印功能，可以创建一个派生类并重写这些方法。

## 对鼠标驱动程序进行同样的重构

我们将对鼠标驱动程序进行类似的重构，创建一个 `MouseEventHandler` 类。

以下是鼠标事件处理器的核心方法：
```cpp
class MouseEventHandler {
public:
    MouseEventHandler();
    virtual void OnMouseMove(int xOffset, int yOffset);
    virtual void OnMouseButtonDown(uint8_t button);
    virtual void OnMouseButtonUp(uint8_t button);
};
```
鼠标坐标等状态信息应该存储在事件处理器中，而不是驱动程序里。这样，驱动程序只负责报告移动偏移量和按钮状态，由事件处理器决定如何响应。

## 测试与验证

![](img/92dddb41e74c356cbdf24295a45e4617_14.png)

![](img/92dddb41e74c356cbdf24295a45e4617_16.png)

![](img/92dddb41e74c356cbdf24295a45e4617_18.png)

![](img/92dddb41e74c356cbdf24295a45e4617_20.png)

![](img/92dddb41e74c356cbdf24295a45e4617_21.png)

完成上述重构后，我们进行测试以确保所有功能正常工作。键盘按键和鼠标移动应能通过新的事件处理器正确响应。

![](img/92dddb41e74c356cbdf24295a45e4617_23.png)

![](img/92dddb41e74c356cbdf24295a45e4617_24.png)

![](img/92dddb41e74c356cbdf24295a45e4617_26.png)

![](img/92dddb41e74c356cbdf24295a45e4617_27.png)

## 总结

![](img/92dddb41e74c356cbdf24295a45e4617_29.png)

本节课中我们一起学习了如何对操作系统项目进行代码抽象和整理。我们创建了通用的驱动程序基类和管理器，使硬件初始化更加有序。更重要的是，我们重构了键盘和鼠标的输入处理逻辑，引入了事件处理器模式，将具体的业务逻辑（如屏幕打印）与底层驱动分离，极大地提高了代码的模块化和可扩展性，为未来实现图形界面等功能打下了良好的基础。在下一节课中，我们将进一步整理项目目录结构并引入命名空间。