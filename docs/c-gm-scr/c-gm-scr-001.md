# 001：平台层与软件渲染 🎮

![](img/65cad47fe79d6d7fa64b4e5575d06d39_1.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_3.png)

在本节课中，我们将学习如何使用C语言从零开始构建一个游戏。我们将从最基础的平台层开始，包括创建窗口、处理输入和实现软件渲染。这是整个系列的第一部分，目标是建立一个可以运行游戏的基础框架。

## 概述

我们将创建一个简单的游戏框架，包括窗口管理、输入处理和软件渲染。通过这个过程，你将理解游戏引擎的基本组成部分，并为后续的游戏开发打下坚实的基础。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_5.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_7.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_9.png)

## 为什么选择C语言？

![](img/65cad47fe79d6d7fa64b4e5575d06d39_11.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_13.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_15.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_17.png)

我们选择C语言而不是C++或其他游戏引擎，主要有三个原因：
1.  **学习编程和游戏编程**：通过从底层开始构建，我们可以更深入地理解编程和游戏开发的原理。
2.  **教学目的**：我们希望提供一个简单易懂的教程，即使是编程初学者也能跟上。
3.  **乐趣**：C语言相对简单直接，能让我们更专注于游戏设计和实现，而不是复杂的语言特性。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_19.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_21.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_22.png)

## 开发计划

![](img/65cad47fe79d6d7fa64b4e5575d06d39_24.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_26.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_28.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_29.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_31.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_32.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_34.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_36.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_38.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_40.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_42.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_44.png)

我们的开发将分为几个阶段：
1.  **初始平台层**：创建窗口、输入和渲染系统。
2.  **基础游戏玩法**：实现一个简单的打砖块游戏原型。
3.  **引擎改进**：添加位图支持、音频、多线程等功能。
4.  **游戏玩法扩展**：在基础游戏上添加更多有趣的玩法和关卡。
5.  **最终优化**：进行性能优化和发布准备。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_46.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_48.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_50.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_52.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_54.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_56.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_58.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_60.png)

## 开发环境设置

![](img/65cad47fe79d6d7fa64b4e5575d06d39_62.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_64.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_66.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_68.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_70.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_72.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_74.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_76.png)

我们使用以下工具进行开发：
- **编译器**：Visual Studio的CL编译器
- **文本编辑器**：4coder
- **操作系统**：Windows

![](img/65cad47fe79d6d7fa64b4e5575d06d39_78.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_80.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_82.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_83.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_85.png)

以下是基本的构建脚本：

![](img/65cad47fe79d6d7fa64b4e5575d06d39_87.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_89.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_91.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_93.png)

```batch
@echo off
pushd build
cl ..\code\win32_platform.c /nologo /Zi /FC /link user32.lib gdi32.lib /incremental:no /opt:ref
popd
```

![](img/65cad47fe79d6d7fa64b4e5575d06d39_95.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_97.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_99.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_101.png)

## 创建窗口

![](img/65cad47fe79d6d7fa64b4e5575d06d39_103.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_105.png)

首先，我们需要创建一个窗口。在Windows中，我们使用`WinMain`作为入口点，而不是标准的`main`函数。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_107.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_109.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_111.png)

```c
#include <windows.h>

![](img/65cad47fe79d6d7fa64b4e5575d06d39_113.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_115.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_117.png)

LRESULT CALLBACK WindowProc(HWND hwnd, UINT uMsg, WPARAM wParam, LPARAM lParam)
{
    switch (uMsg)
    {
        case WM_CLOSE:
        case WM_DESTROY:
            GlobalRunning = false;
            break;
        default:
            return DefWindowProc(hwnd, uMsg, wParam, lParam);
    }
    return 0;
}

int WINAPI WinMain(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPSTR lpCmdLine, int nShowCmd)
{
    // 注册窗口类
    WNDCLASS WindowClass = {0};
    WindowClass.style = CS_HREDRAW | CS_VREDRAW;
    WindowClass.lpfnWndProc = WindowProc;
    WindowClass.hInstance = hInstance;
    WindowClass.lpszClassName = "GameWindowClass";
    
    RegisterClass(&WindowClass);
    
    // 创建窗口
    HWND Window = CreateWindowEx(
        0,
        "GameWindowClass",
        "Breakout",
        WS_OVERLAPPEDWINDOW | WS_VISIBLE,
        CW_USEDEFAULT, CW_USEDEFAULT,
        1280, 720,
        0, 0, hInstance, 0
    );
    
    // 主循环
    GlobalRunning = true;
    while (GlobalRunning)
    {
        MSG Message;
        while (PeekMessage(&Message, 0, 0, 0, PM_REMOVE))
        {
            TranslateMessage(&Message);
            DispatchMessage(&Message);
        }
        
        // 游戏更新和渲染将在这里进行
    }
    
    return 0;
}
```

![](img/65cad47fe79d6d7fa64b4e5575d06d39_119.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_121.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_123.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_125.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_127.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_129.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_131.png)

## 软件渲染

![](img/65cad47fe79d6d7fa64b4e5575d06d39_133.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_135.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_137.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_139.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_141.png)

我们将使用软件渲染，这意味着我们将直接在内存中绘制像素，然后将其显示在屏幕上。这比硬件渲染更易于理解和调试。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_143.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_145.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_147.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_149.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_151.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_152.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_153.png)

### 渲染缓冲区

![](img/65cad47fe79d6d7fa64b4e5575d06d39_155.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_157.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_159.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_161.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_163.png)

我们需要创建一个渲染缓冲区来存储像素数据。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_165.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_167.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_169.png)

```c
typedef struct
{
    int Width;
    int Height;
    u32* Pixels;
    BITMAPINFO BitmapInfo;
} render_buffer;

![](img/65cad47fe79d6d7fa64b4e5575d06d39_171.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_173.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_175.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_177.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_179.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_181.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_183.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_185.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_187.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_189.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_191.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_193.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_195.png)

render_buffer GlobalRenderBuffer;
```

![](img/65cad47fe79d6d7fa64b4e5575d06d39_196.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_198.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_200.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_202.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_204.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_206.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_208.png)

### 初始化渲染缓冲区

![](img/65cad47fe79d6d7fa64b4e5575d06d39_210.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_212.png)

当窗口大小改变时，我们需要重新分配渲染缓冲区。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_214.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_216.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_218.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_220.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_222.png)

```c
void ResizeRenderBuffer(render_buffer* Buffer, int Width, int Height)
{
    if (Buffer->Pixels)
    {
        VirtualFree(Buffer->Pixels, 0, MEM_RELEASE);
    }
    
    Buffer->Width = Width;
    Buffer->Height = Height;
    
    // 分配像素内存
    Buffer->Pixels = (u32*)VirtualAlloc(
        0,
        sizeof(u32) * Width * Height,
        MEM_COMMIT | MEM_RESERVE,
        PAGE_READWRITE
    );
    
    // 设置位图信息
    Buffer->BitmapInfo.bmiHeader.biSize = sizeof(Buffer->BitmapInfo.bmiHeader);
    Buffer->BitmapInfo.bmiHeader.biWidth = Width;
    Buffer->BitmapInfo.bmiHeader.biHeight = -Height;  // 负值表示从上到下
    Buffer->BitmapInfo.bmiHeader.biPlanes = 1;
    Buffer->BitmapInfo.bmiHeader.biBitCount = 32;
    Buffer->BitmapInfo.bmiHeader.biCompression = BI_RGB;
}
```

![](img/65cad47fe79d6d7fa64b4e5575d06d39_224.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_226.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_228.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_230.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_232.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_234.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_236.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_238.png)

### 绘制到屏幕

![](img/65cad47fe79d6d7fa64b4e5575d06d39_240.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_242.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_243.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_245.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_247.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_249.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_250.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_252.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_254.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_256.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_258.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_260.png)

使用`StretchDIBits`函数将我们的像素缓冲区绘制到屏幕上。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_262.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_264.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_265.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_267.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_269.png)

```c
void DisplayBuffer(HDC DeviceContext, render_buffer* Buffer)
{
    StretchDIBits(
        DeviceContext,
        0, 0, Buffer->Width, Buffer->Height,
        0, 0, Buffer->Width, Buffer->Height,
        Buffer->Pixels,
        &Buffer->BitmapInfo,
        DIB_RGB_COLORS,
        SRCCOPY
    );
}
```

![](img/65cad47fe79d6d7fa64b4e5575d06d39_271.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_273.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_275.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_277.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_279.png)

## 输入处理

![](img/65cad47fe79d6d7fa64b4e5575d06d39_281.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_282.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_284.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_286.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_288.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_290.png)

我们需要处理键盘输入。Windows通过消息系统发送输入事件。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_292.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_294.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_296.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_298.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_300.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_301.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_302.png)

### 输入结构

![](img/65cad47fe79d6d7fa64b4e5575d06d39_304.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_305.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_307.png)

我们创建一个结构来存储输入状态。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_309.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_311.png)

```c
typedef struct
{
    bool IsDown;
    bool Changed;
} button;

![](img/65cad47fe79d6d7fa64b4e5575d06d39_313.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_315.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_317.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_319.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_320.png)

typedef struct
{
    button Buttons[4];  // 左、右、上、下
} input;
```

![](img/65cad47fe79d6d7fa64b4e5575d06d39_322.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_323.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_324.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_326.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_328.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_330.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_332.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_334.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_335.png)

### 处理输入消息

![](img/65cad47fe79d6d7fa64b4e5575d06d39_337.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_338.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_340.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_342.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_344.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_346.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_348.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_350.png)

在消息循环中处理键盘输入。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_352.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_354.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_356.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_358.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_359.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_361.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_363.png)

```c
case WM_KEYDOWN:
case WM_KEYUP:
{
    bool WasDown = ((Message.lParam & (1 << 30)) != 0);
    bool IsDown = ((Message.lParam & (1 << 31)) == 0);
    
    if (Message.wParam == VK_LEFT)
    {
        GlobalInput.Buttons[BUTTON_LEFT].IsDown = IsDown;
        GlobalInput.Buttons[BUTTON_LEFT].Changed = (WasDown != IsDown);
    }
    // 处理其他按键...
}
break;
```

![](img/65cad47fe79d6d7fa64b4e5575d06d39_365.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_367.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_369.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_371.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_373.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_375.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_377.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_379.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_381.png)

### 重置输入状态

![](img/65cad47fe79d6d7fa64b4e5575d06d39_383.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_385.png)

每帧开始时重置输入状态。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_387.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_389.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_391.png)

```c
void ResetInput(input* Input)
{
    for (int i = 0; i < ARRAY_COUNT(Input->Buttons); i++)
    {
        Input->Buttons[i].Changed = false;
    }
}
```

![](img/65cad47fe79d6d7fa64b4e5575d06d39_393.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_395.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_397.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_398.png)

## 游戏循环集成

![](img/65cad47fe79d6d7fa64b4e5575d06d39_399.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_401.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_403.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_405.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_407.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_409.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_411.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_413.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_415.png)

现在我们将所有部分集成到游戏循环中。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_417.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_418.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_420.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_422.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_424.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_426.png)

```c
while (GlobalRunning)
{
    // 处理输入
    MSG Message;
    while (PeekMessage(&Message, 0, 0, 0, PM_REMOVE))
    {
        switch (Message.message)
        {
            case WM_KEYDOWN:
            case WM_KEYUP:
                // 处理键盘输入
                break;
                
            case WM_CLOSE:
            case WM_DESTROY:
                GlobalRunning = false;
                break;
                
            default:
                TranslateMessage(&Message);
                DispatchMessage(&Message);
                break;
        }
    }
    
    // 获取设备上下文
    HDC DeviceContext = GetDC(Window);
    
    // 更新游戏
    SimulateGame(&GlobalInput, DeltaTime);
    
    // 渲染游戏
    DisplayBuffer(DeviceContext, &GlobalRenderBuffer);
    
    // 释放设备上下文
    ReleaseDC(Window, DeviceContext);
    
    // 计算帧时间
    CalculateDeltaTime();
}
```

![](img/65cad47fe79d6d7fa64b4e5575d06d39_428.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_430.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_432.png)

## 像素独立渲染

为了让游戏在不同分辨率下表现一致，我们需要实现像素独立渲染。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_434.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_436.png)

### 坐标转换

![](img/65cad47fe79d6d7fa64b4e5575d06d39_438.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_440.png)

我们将游戏世界的坐标转换为屏幕像素坐标。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_442.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_444.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_446.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_448.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_450.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_452.png)

```c
void DrawRect(vector2 Position, vector2 HalfSize, u32 Color)
{
    // 转换为像素坐标
    f32 AspectMultiplier = (f32)GlobalRenderBuffer.Width / 16.0f;
    if ((f32)GlobalRenderBuffer.Width / (f32)GlobalRenderBuffer.Height < 1.77f)
    {
        AspectMultiplier = (f32)GlobalRenderBuffer.Height / 9.0f;
    }
    
    // 计算屏幕位置
    int X0 = (int)((Position.X - HalfSize.X) * AspectMultiplier + (f32)GlobalRenderBuffer.Width * 0.5f);
    int Y0 = (int)((Position.Y - HalfSize.Y) * AspectMultiplier + (f32)GlobalRenderBuffer.Height * 0.5f);
    int X1 = (int)((Position.X + HalfSize.X) * AspectMultiplier + (f32)GlobalRenderBuffer.Width * 0.5f);
    int Y1 = (int)((Position.Y + HalfSize.Y) * AspectMultiplier + (f32)GlobalRenderBuffer.Height * 0.5f);
    
    // 限制在屏幕范围内
    X0 = Clamp(X0, 0, GlobalRenderBuffer.Width);
    Y0 = Clamp(Y0, 0, GlobalRenderBuffer.Height);
    X1 = Clamp(X1, 0, GlobalRenderBuffer.Width);
    Y1 = Clamp(Y1, 0, GlobalRenderBuffer.Height);
    
    // 绘制矩形
    DrawRectInPixels(X0, Y0, X1, Y1, Color);
}
```

![](img/65cad47fe79d6d7fa64b4e5575d06d39_454.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_456.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_458.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_459.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_461.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_463.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_464.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_466.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_468.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_470.png)

## 时间管理

![](img/65cad47fe79d6d7fa64b4e5575d06d39_472.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_474.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_476.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_478.png)

为了实现帧率独立的运动，我们需要测量每帧的时间。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_480.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_482.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_484.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_486.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_488.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_490.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_492.png)

### 获取高精度时间

![](img/65cad47fe79d6d7fa64b4e5575d06d39_494.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_496.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_498.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_500.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_501.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_503.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_505.png)

Windows提供了高精度计时器。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_507.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_509.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_511.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_513.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_515.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_517.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_519.png)

```c
void CalculateDeltaTime()
{
    static LARGE_INTEGER LastCounter;
    static LARGE_INTEGER FrequencyCounter;
    static bool FirstTime = true;
    
    if (FirstTime)
    {
        QueryPerformanceFrequency(&FrequencyCounter);
        QueryPerformanceCounter(&LastCounter);
        FirstTime = false;
        DeltaTime = 1.0f / 60.0f;  // 假设第一帧是60FPS
        return;
    }
    
    LARGE_INTEGER CurrentCounter;
    QueryPerformanceCounter(&CurrentCounter);
    
    DeltaTime = (f32)(CurrentCounter.QuadPart - LastCounter.QuadPart) / (f32)FrequencyCounter.QuadPart;
    LastCounter = CurrentCounter;
}
```

![](img/65cad47fe79d6d7fa64b4e5575d06d39_521.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_523.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_525.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_527.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_529.png)

### 帧率独立运动

使用DeltaTime来实现帧率独立的运动。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_531.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_533.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_535.png)

```c
void UpdatePlayer(vector2* PlayerPosition, input* Input, f32 DeltaTime)
{
    f32 Speed = 100.0f;  // 单位：单位/秒
    
    if (Input->Buttons[BUTTON_LEFT].IsDown)
    {
        PlayerPosition->X -= Speed * DeltaTime;
    }
    if (Input->Buttons[BUTTON_RIGHT].IsDown)
    {
        PlayerPosition->X += Speed * DeltaTime;
    }
    // 处理其他方向...
}
```

![](img/65cad47fe79d6d7fa64b4e5575d06d39_537.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_539.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_541.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_543.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_545.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_547.png)

## 总结

![](img/65cad47fe79d6d7fa64b4e5575d06d39_549.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_551.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_553.png)

在本节课中，我们一起学习了如何从零开始用C语言创建游戏的基础框架。我们实现了以下核心功能：

![](img/65cad47fe79d6d7fa64b4e5575d06d39_555.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_557.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_558.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_560.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_562.png)

1.  **窗口创建**：使用Windows API创建和管理游戏窗口。
2.  **软件渲染**：创建渲染缓冲区并实现像素绘制。
3.  **输入处理**：处理键盘输入并创建输入状态系统。
4.  **游戏循环**：集成输入、更新和渲染到主循环中。
5.  **像素独立渲染**：实现坐标转换系统，使游戏在不同分辨率下表现一致。
6.  **时间管理**：使用高精度计时器实现帧率独立的运动。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_564.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_566.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_568.png)

通过这个基础框架，我们已经为下一节课实现游戏玩法做好了准备。在下一节课中，我们将开始创建打砖块游戏的基本玩法。

![](img/65cad47fe79d6d7fa64b4e5575d06d39_570.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_572.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_574.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_576.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_578.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_580.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_582.png)

---

![](img/65cad47fe79d6d7fa64b4e5575d06d39_584.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_586.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_588.png)

**关键代码总结：**

![](img/65cad47fe79d6d7fa64b4e5575d06d39_590.png)

- 窗口创建：`CreateWindowEx`
- 渲染缓冲区：`VirtualAlloc` + `StretchDIBits`
- 输入处理：`PeekMessage` + `WM_KEYDOWN/WM_KEYUP`
- 时间管理：`QueryPerformanceCounter`
- 坐标转换：`(Position * AspectMultiplier) + ScreenCenter`

![](img/65cad47fe79d6d7fa64b4e5575d06d39_592.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_594.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_596.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_598.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_600.png)

![](img/65cad47fe79d6d7fa64b4e5575d06d39_602.png)

现在我们已经有了一个完整的基础框架，可以开始专注于游戏玩法的实现了！