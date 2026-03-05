# 编写你自己的操作系统：14：桌面与窗口 🖥️

在本节课中，我们将继续完成图形用户界面框架，具体实现桌面和窗口类。我们将学习如何创建可交互的桌面环境，并实现窗口的拖拽功能。

## 概述

![](img/ea253ac465ac5a1fbfb1430ecea87b67_1.png)

![](img/ea253ac465ac5a1fbfb1430ecea87b67_3.png)

上一节我们介绍了GUI框架的基础结构，但尚未实现桌面和窗口类。本节我们将完成这些核心组件的实现，构建一个简单的图形界面。

## 继续GUI框架的实现

上一节我们介绍了GUI框架的基础结构，本节中我们来看看如何实现具体的桌面和窗口类。首先，我们需要解决编译问题，因为之前未将相关对象文件加入编译。

### 修复编译错误

在编译时，我们遇到了几个错误。主要问题在于`Widget`类缺少`ContainsCoordinate`方法的实现，并且`CommonGraphicsContext`的引用方式有误。

以下是修复方法：
```cpp
bool Widget::ContainsCoordinate(int32_t x, int32_t y)
{
    return (x >= this->x) && (x < (this->x + this->w)) &&
           (y >= this->y) && (y < (this->y + this->h));
}
```
这个方法检查给定的坐标是否在部件的边界框内。需要注意的是，这里传入的坐标是相对于父部件的相对坐标。

### 优化事件处理

当前`CompositeWidget`中的鼠标移动事件处理代码有些冗余。更优雅的方式是检查鼠标是否从一个部件移到了另一个部件，并相应地触发`OnMouseLeave`和`OnMouseEnter`事件。不过，为了简化，我们暂时保持现有实现。

### 改进键盘和鼠标事件处理

为了让部件能够处理键盘和鼠标事件，我们进行以下改进：

1. 让`Widget`类继承自`KeyboardEventHandler`，这样部件可以直接处理键盘事件
2. 让`Desktop`类继承自`MouseEventHandler`，以便处理鼠标事件
3. 为`CompositeWidget`添加添加子部件的方法

以下是关键代码修改：
```cpp
class Widget : public KeyboardEventHandler {
    // ... 现有代码
};

![](img/ea253ac465ac5a1fbfb1430ecea87b67_5.png)

![](img/ea253ac465ac5a1fbfb1430ecea87b67_7.png)

class Desktop : public CompositeWidget, public MouseEventHandler {
    // ... 现有代码
};
```

## 实现桌面类 🖥️

桌面是一个特殊的复合部件，它需要处理鼠标移动并将其转换为绝对坐标，同时负责绘制鼠标光标。

### 桌面类的构造函数

桌面类的构造函数初始化鼠标位置为屏幕中心：
```cpp
Desktop::Desktop(uint32_t w, uint32_t h, uint8_t color) 
    : CompositeWidget(0, 0, 0, w, h, color),
      MouseX(w/2), MouseY(h/2) {
}
```

### 鼠标事件处理

桌面需要处理鼠标的移动、按下和释放事件：

1. **鼠标移动**：将相对移动转换为绝对坐标，并确保光标不超出屏幕边界
2. **鼠标按下/释放**：将事件传递给相应的部件处理

以下是鼠标移动处理的核心逻辑：
```cpp
void Desktop::OnMouseMove(int8_t x, int8_t y) {
    // 调整移动速度
    x /= 4;
    y /= 4;
    
    // 确保不超出屏幕边界
    int32_t newMouseX = MouseX + x;
    if(newMouseX < 0) newMouseX = 0;
    if(newMouseX >= w) newMouseX = w - 1;
    
    int32_t newMouseY = MouseY + y;
    if(newMouseY < 0) newMouseY = 0;
    if(newMouseY >= h) newMouseY = h - 1;
    
    // 处理鼠标移动事件
    CompositeWidget::OnMouseMove(MouseX, MouseY, newMouseX, newMouseY);
    
    // 更新鼠标位置
    MouseX = newMouseX;
    MouseY = newMouseY;
}
```

### 绘制桌面

桌面的绘制包括两个部分：
1. 调用父类的`Draw`方法绘制所有子部件
2. 在鼠标位置绘制光标

以下是绘制方法：
```cpp
void Desktop::Draw(GraphicsContext* gc) {
    CompositeWidget::Draw(gc);
    
    // 绘制白色十字光标
    for(int i = -2; i <= 2; i++) {
        PutPixel(gc, MouseX + i, MouseY, 0xFF);  // 水平线
        PutPixel(gc, MouseX, MouseY + i, 0xFF);  // 垂直线
    }
}
```

需要注意的是，在绘制像素前需要检查坐标是否合法：
```cpp
void PutPixel(GraphicsContext* gc, int32_t x, int32_t y, uint8_t color) {
    if(x >= 0 && x < gc->Width && y >= 0 && y < gc->Height) {
        gc->FrameBuffer[y * gc->PixelsPerScanLine + x] = color;
    }
}
```

![](img/ea253ac465ac5a1fbfb1430ecea87b67_9.png)

![](img/ea253ac465ac5a1fbfb1430ecea87b67_11.png)

## 实现窗口类 🪟

![](img/ea253ac465ac5a1fbfb1430ecea87b67_13.png)

![](img/ea253ac465ac5a1fbfb1430ecea87b67_14.png)

窗口类允许用户通过拖拽来移动窗口位置。我们通过跟踪鼠标状态来实现这一功能。

![](img/ea253ac465ac5a1fbfb1430ecea87b67_15.png)

![](img/ea253ac465ac5a1fbfb1430ecea87b67_17.png)

### 窗口类的状态管理

![](img/ea253ac465ac5a1fbfb1430ecea87b67_19.png)

窗口类需要跟踪是否正在被拖拽：
```cpp
class Window : public CompositeWidget {
private:
    bool Dragging;
    
public:
    Window(Widget* parent, int32_t x, int32_t y, 
           int32_t w, int32_t h, uint8_t color);
    
    void OnMouseDown(int32_t x, int32_t y, uint8_t button);
    void OnMouseUp(int32_t x, int32_t y, uint8_t button);
    void OnMouseMove(int32_t oldX, int32_t oldY, 
                     int32_t newX, int32_t newY);
};
```

![](img/ea253ac465ac5a1fbfb1430ecea87b67_21.png)

### 鼠标事件处理

窗口的鼠标事件处理逻辑如下：

![](img/ea253ac465ac5a1fbfb1430ecea87b67_23.png)

1. **鼠标按下**：如果按下左键，开始拖拽
2. **鼠标释放**：停止拖拽
3. **鼠标移动**：如果正在拖拽，更新窗口位置

![](img/ea253ac465ac5a1fbfb1430ecea87b67_25.png)

以下是关键实现：
```cpp
void Window::OnMouseDown(int32_t x, int32_t y, uint8_t button) {
    CompositeWidget::OnMouseDown(x, y, button);
    Dragging = (button == 1);  // 左键
}

void Window::OnMouseMove(int32_t oldX, int32_t oldY, 
                         int32_t newX, int32_t newY) {
    CompositeWidget::OnMouseMove(oldX, oldY, newX, newY);
    
    if(Dragging) {
        this->x += newX - oldX;
        this->y += newY - oldY;
    }
}
```

## 集成到内核中 🔧

![](img/ea253ac465ac5a1fbfb1430ecea87b67_27.png)

![](img/ea253ac465ac5a1fbfb1430ecea87b67_29.png)

![](img/ea253ac465ac5a1fbfb1430ecea87b67_31.png)

现在我们将桌面和窗口集成到操作系统中：

![](img/ea253ac465ac5a1fbfb1430ecea87b67_33.png)

![](img/ea253ac465ac5a1fbfb1430ecea87b67_34.png)

### 创建桌面和窗口

以下是创建桌面和两个窗口的示例代码：
```cpp
// 创建桌面
Desktop* desktop = new Desktop(320, 200, 0x00);

// 创建第一个窗口（红色）
Window* window1 = new Window(desktop, 10, 10, 100, 50, 0x04);
desktop->AddChild(window1);

// 创建第二个窗口（绿色）
Window* window2 = new Window(desktop, 40, 40, 120, 60, 0x02);
desktop->AddChild(window2);
```

### 连接输入设备

将桌面连接到鼠标和键盘驱动程序：
```cpp
// 连接鼠标
mouseDriver->SetEventHandler(desktop);

![](img/ea253ac465ac5a1fbfb1430ecea87b67_36.png)

// 连接键盘
keyboardDriver->SetEventHandler(desktop);
```

![](img/ea253ac465ac5a1fbfb1430ecea87b67_38.png)

### 更新显示

在系统主循环中定期重绘桌面：
```cpp
while(1) {
    desktop->Draw(graphicsContext);
    // ... 其他系统任务
}
```

## 性能优化考虑 ⚡

当前实现存在明显的性能问题，主要是频繁重绘整个屏幕导致的闪烁。以下是几种优化思路：

### 1. 局部更新机制

更好的方法是只更新屏幕上发生变化的部分：
- 维护一个无效区域列表
- 只重绘这些无效区域
- 使用内存复制来移动窗口内容

### 2. 从后向前绘制

当前实现从后向前绘制（先桌面后窗口），但更高效的方式可能是：
- 从前向后绘制
- 使用矩形裁剪避免重复绘制

### 3. 图形硬件加速

利用图形硬件的特性：
- 使用硬件矩形绘制功能
- 批量操作像素数据
- 直接内存访问(DMA)

### 4. 双缓冲技术

使用双缓冲可以消除闪烁：
- 在后台缓冲区绘制
- 完成后交换到前台显示

## 文本渲染支持 📝

![](img/ea253ac465ac5a1fbfb1430ecea87b67_40.png)

要在图形模式下显示文本，我们需要位图字体。可以使用公开领域的8x8像素字体：

以下是使用位图字体渲染文本的基本思路：
```cpp
void DrawChar(GraphicsContext* gc, int32_t x, int32_t y, 
              char c, uint8_t color) {
    uint8_t* font = &font8x8_basic[c * 8];
    
    for(int row = 0; row < 8; row++) {
        uint8_t rowData = font[row];
        for(int col = 0; col < 8; col++) {
            if(rowData & (1 << col)) {
                PutPixel(gc, x + col, y + row, color);
            }
        }
    }
}
```

## 总结

本节课中我们一起学习了如何实现操作系统的图形用户界面。我们完成了以下内容：

1. **修复了编译问题**，实现了缺失的方法
2. **创建了桌面类**，能够处理鼠标移动和绘制光标
3. **实现了窗口类**，支持基本的拖拽功能
4. **将GUI集成到内核**中，创建了可交互的桌面环境
5. **讨论了性能优化**的各种可能性
6. **介绍了文本渲染**的基本方法

虽然当前实现存在性能问题，但框架设计具有良好的抽象性。通过改进图形驱动程序，可以获得更好的性能和分辨率，而无需修改上层GUI代码。

这个GUI框架为创建更复杂的界面元素（如按钮、文本框等）奠定了基础。下一节课，我们将开始学习多任务处理，让多个程序能够同时运行。

![](img/ea253ac465ac5a1fbfb1430ecea87b67_42.png)

---

**关键要点回顾：**
- GUI框架采用分层设计，便于扩展和维护
- 桌面负责坐标转换和光标绘制
- 窗口支持基本的交互操作
- 性能优化是GUI开发的重要考虑因素
- 良好的抽象设计使得更换底层驱动程序变得容易