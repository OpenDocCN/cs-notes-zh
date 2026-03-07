# 010：位图与子像素渲染 🎮

![](img/7011eb2fe997e9d598bb4046015d583f_1.png)

![](img/7011eb2fe997e9d598bb4046015d583f_3.png)

![](img/7011eb2fe997e9d598bb4046015d583f_5.png)

![](img/7011eb2fe997e9d598bb4046015d583f_7.png)

![](img/7011eb2fe997e9d598bb4046015d583f_9.png)

![](img/7011eb2fe997e9d598bb4046015d583f_10.png)

![](img/7011eb2fe997e9d598bb4046015d583f_12.png)

![](img/7011eb2fe997e9d598bb4046015d583f_14.png)

![](img/7011eb2fe997e9d598bb4046015d583f_15.png)

![](img/7011eb2fe997e9d598bb4046015d583f_17.png)

![](img/7011eb2fe997e9d598bb4046015d583f_19.png)

![](img/7011eb2fe997e9d598bb4046015d583f_21.png)

![](img/7011eb2fe997e9d598bb4046015d583f_23.png)

![](img/7011eb2fe997e9d598bb4046015d583f_25.png)

![](img/7011eb2fe997e9d598bb4046015d583f_26.png)

![](img/7011eb2fe997e9d598bb4046015d583f_28.png)

![](img/7011eb2fe997e9d598bb4046015d583f_30.png)

![](img/7011eb2fe997e9d598bb4046015d583f_32.png)

![](img/7011eb2fe997e9d598bb4046015d583f_34.png)

![](img/7011eb2fe997e9d598bb4046015d583f_35.png)

在本节课中，我们将为游戏引擎添加位图支持，让道具拥有独特的图标，使玩家能更直观地识别增益和减益效果。我们还将实现子像素精度的渲染，让慢速移动的物体动画更加平滑。

![](img/7011eb2fe997e9d598bb4046015d583f_37.png)

![](img/7011eb2fe997e9d598bb4046015d583f_39.png)

![](img/7011eb2fe997e9d598bb4046015d583f_41.png)

![](img/7011eb2fe997e9d598bb4046015d583f_42.png)

![](img/7011eb2fe997e9d598bb4046015d583f_44.png)

![](img/7011eb2fe997e9d598bb4046015d583f_46.png)

![](img/7011eb2fe997e9d598bb4046015d583f_47.png)

![](img/7011eb2fe997e9d598bb4046015d583f_48.png)

![](img/7011eb2fe997e9d598bb4046015d583f_50.png)

![](img/7011eb2fe997e9d598bb4046015d583f_51.png)

![](img/7011eb2fe997e9d598bb4046015d583f_53.png)

## 概述 📋

![](img/7011eb2fe997e9d598bb4046015d583f_55.png)

![](img/7011eb2fe997e9d598bb4046015d583f_57.png)

![](img/7011eb2fe997e9d598bb4046015d583f_59.png)

![](img/7011eb2fe997e9d598bb4046015d583f_61.png)

![](img/7011eb2fe997e9d598bb4046015d583f_63.png)

![](img/7011eb2fe997e9d598bb4046015d583f_65.png)

![](img/7011eb2fe997e9d598bb4046015d583f_67.png)

![](img/7011eb2fe997e9d598bb4046015d583f_69.png)

![](img/7011eb2fe997e9d598bb4046015d583f_71.png)

![](img/7011eb2fe997e9d598bb4046015d583f_73.png)

在之前的课程中，我们已经创建了一个包含多种游戏模式和道具（如无敌、三连发、评论等）的弹球游戏。目前，这些道具仅以彩色方块显示。本节课的目标是：
1.  为这些道具加载并显示自定义的位图图标。
2.  实现子像素渲染，提升慢速移动物体（如玩家挡板）的视觉平滑度。

![](img/7011eb2fe997e9d598bb4046015d583f_75.png)

![](img/7011eb2fe997e9d598bb4046015d583f_77.png)

![](img/7011eb2fe997e9d598bb4046015d583f_79.png)

![](img/7011eb2fe997e9d598bb4046015d583f_80.png)

![](img/7011eb2fe997e9d598bb4046015d583f_82.png)

![](img/7011eb2fe997e9d598bb4046015d583f_84.png)

![](img/7011eb2fe997e9d598bb4046015d583f_86.png)

![](img/7011eb2fe997e9d598bb4046015d583f_88.png)

![](img/7011eb2fe997e9d598bb4046015d583f_90.png)

通过实现位图，玩家可以更清楚地了解每个道具的作用，从而做出更有策略性的选择。

![](img/7011eb2fe997e9d598bb4046015d583f_92.png)

![](img/7011eb2fe997e9d598bb4046015d583f_93.png)

![](img/7011eb2fe997e9d598bb4046015d583f_95.png)

![](img/7011eb2fe997e9d598bb4046015d583f_97.png)

![](img/7011eb2fe997e9d598bb4046015d583f_99.png)

## 实现位图支持 🖼️

上一节我们为游戏添加了旋转矩形和粒子系统等视觉效果。本节中，我们来看看如何为游戏引擎添加位图渲染功能。

![](img/7011eb2fe997e9d598bb4046015d583f_101.png)

![](img/7011eb2fe997e9d598bb4046015d583f_103.png)

![](img/7011eb2fe997e9d598bb4046015d583f_105.png)

![](img/7011eb2fe997e9d598bb4046015d583f_107.png)

![](img/7011eb2fe997e9d598bb4046015d583f_109.png)

![](img/7011eb2fe997e9d598bb4046015d583f_111.png)

![](img/7011eb2fe997e9d598bb4046015d583f_113.png)

![](img/7011eb2fe997e9d598bb4046015d583f_115.png)

### 1. 创建并加载位图文件

![](img/7011eb2fe997e9d598bb4046015d583f_117.png)

![](img/7011eb2fe997e9d598bb4046015d583f_119.png)

![](img/7011eb2fe997e9d598bb4046015d583f_121.png)

![](img/7011eb2fe997e9d598bb4046015d583f_123.png)

![](img/7011eb2fe997e9d598bb4046015d583f_125.png)

![](img/7011eb2fe997e9d598bb4046015d583f_127.png)

![](img/7011eb2fe997e9d598bb4046015d583f_129.png)

![](img/7011eb2fe997e9d598bb4046015d583f_131.png)

首先，我们需要创建位图文件并将其加载到游戏中。

![](img/7011eb2fe997e9d598bb4046015d583f_133.png)

![](img/7011eb2fe997e9d598bb4046015d583f_135.png)

**步骤：**
1.  使用图像编辑工具（如Photoshop）创建简单的像素画图标（例如8x8或16x16像素），并保存为PNG格式。
2.  在代码中创建文件读取功能，将PNG文件加载到内存中。
3.  使用第三方库（如`stb_image`）将压缩的PNG数据解码为未压缩的像素数据。

![](img/7011eb2fe997e9d598bb4046015d583f_137.png)

![](img/7011eb2fe997e9d598bb4046015d583f_139.png)

![](img/7011eb2fe997e9d598bb4046015d583f_141.png)

![](img/7011eb2fe997e9d598bb4046015d583f_143.png)

**核心代码：**
```c
// 定义字符串结构体，用于存储文件数据
typedef struct {
    char* data;
    u64 size;
} string;

![](img/7011eb2fe997e9d598bb4046015d583f_145.png)

![](img/7011eb2fe997e9d598bb4046015d583f_147.png)

![](img/7011eb2fe997e9d598bb4046015d583f_149.png)

![](img/7011eb2fe997e9d598bb4046015d583f_151.png)

![](img/7011eb2fe997e9d598bb4046015d583f_153.png)

![](img/7011eb2fe997e9d598bb4046015d583f_155.png)

![](img/7011eb2fe997e9d598bb4046015d583f_157.png)

![](img/7011eb2fe997e9d598bb4046015d583f_159.png)

![](img/7011eb2fe997e9d598bb4046015d583f_161.png)

![](img/7011eb2fe997e9d598bb4046015d583f_163.png)

![](img/7011eb2fe997e9d598bb4046015d583f_165.png)

![](img/7011eb2fe997e9d598bb4046015d583f_167.png)

![](img/7011eb2fe997e9d598bb4046015d583f_169.png)

![](img/7011eb2fe997e9d598bb4046015d583f_171.png)

![](img/7011eb2fe997e9d598bb4046015d583f_173.png)

![](img/7011eb2fe997e9d598bb4046015d583f_175.png)

// 读取整个文件的函数
internal string OS_ReadEntireFile(char* filepath) {
    string result = {0};
    // 使用Windows API打开和读取文件
    HANDLE file_handle = CreateFileA(...);
    if(file_handle != INVALID_HANDLE_VALUE) {
        LARGE_INTEGER file_size;
        GetFileSizeEx(file_handle, &file_size);
        result.size = file_size.QuadPart;
        result.data = VirtualAlloc(0, result.size, ...);
        ReadFile(file_handle, result.data, ...);
        CloseHandle(file_handle);
    }
    return result;
}

![](img/7011eb2fe997e9d598bb4046015d583f_177.png)

![](img/7011eb2fe997e9d598bb4046015d583f_179.png)

![](img/7011eb2fe997e9d598bb4046015d583f_181.png)

![](img/7011eb2fe997e9d598bb4046015d583f_183.png)

![](img/7011eb2fe997e9d598bb4046015d583f_185.png)

![](img/7011eb2fe997e9d598bb4046015d583f_187.png)

![](img/7011eb2fe997e9d598bb4046015d583f_189.png)

![](img/7011eb2fe997e9d598bb4046015d583f_191.png)

![](img/7011eb2fe997e9d598bb4046015d583f_193.png)

![](img/7011eb2fe997e9d598bb4046015d583f_195.png)

![](img/7011eb2fe997e9d598bb4046015d583f_197.png)

![](img/7011eb2fe997e9d598bb4046015d583f_199.png)

// 使用stb_image加载PNG数据
internal bitmap LoadPNG(char* filepath) {
    bitmap result = {0};
    string image = OS_ReadEntireFile(filepath);
    // stbi_load_from_memory 从内存加载图像
    result.pixels = (u32*)stbi_load_from_memory((u8*)image.data, image.size,
                                                &result.width, &result.height,
                                                &result.channels, 4); // 强制RGBA四通道
    // 注意：Windows使用BGRA格式，可能需要交换颜色通道
    return result;
}
```

![](img/7011eb2fe997e9d598bb4046015d583f_201.png)

### 2. 渲染位图

![](img/7011eb2fe997e9d598bb4046015d583f_203.png)

![](img/7011eb2fe997e9d598bb4046015d583f_205.png)

![](img/7011eb2fe997e9d598bb4046015d583f_207.png)

![](img/7011eb2fe997e9d598bb4046015d583f_209.png)

![](img/7011eb2fe997e9d598bb4046015d583f_211.png)

加载位图后，我们需要在屏幕上绘制它。这涉及到将位图的UV坐标（0到1的范围）映射到屏幕像素坐标。

![](img/7011eb2fe997e9d598bb4046015d583f_213.png)

![](img/7011eb2fe997e9d598bb4046015d583f_215.png)

**核心概念：**
- **UV坐标**：一个归一化的二维坐标系统，用于表示纹理（位图）上的位置。`(0,0)`通常代表左上角，`(1,1)`代表右下角。
- **采样**：根据UV坐标从位图像素数组中获取颜色的过程。

![](img/7011eb2fe997e9d598bb4046015d583f_217.png)

![](img/7011eb2fe997e9d598bb4046015d583f_219.png)

![](img/7011eb2fe997e9d598bb4046015d583f_221.png)

![](img/7011eb2fe997e9d598bb4046015d583f_223.png)

![](img/7011eb2fe997e9d598bb4046015d583f_225.png)

**渲染位图函数：**
```c
internal void DrawBitmap(bitmap* bitmap, v2 p, v2 half_size) {
    // 计算目标矩形在屏幕上的边界
    f32 x0 = p.x - half_size.x;
    f32 x1 = p.x + half_size.x;
    f32 y0 = p.y - half_size.y;
    f32 y1 = p.y + half_size.y;

    // 将屏幕坐标转换为整数像素坐标
    i32 min_x = (i32)(x0 + 0.5f);
    i32 max_x = (i32)(x1 + 0.5f);
    i32 min_y = (i32)(y0 + 0.5f);
    i32 max_y = (i32)(y1 + 0.5f);

    // 遍历目标矩形内的每个像素
    for(i32 y = min_y; y < max_y; ++y) {
        for(i32 x = min_x; x < max_x; ++x) {
            // 计算当前像素在目标矩形中的UV坐标
            f32 u = MapIntoRange((f32)x, x0, x1, 0.0f, 1.0f);
            f32 v = MapIntoRange((f32)y, y0, y1, 0.0f, 1.0f);

            // 将UV坐标转换为位图像素坐标
            i32 src_x = (i32)(u * (bitmap->width - 1) + 0.5f);
            i32 src_y = (i32)(v * (bitmap->height - 1) + 0.5f);

            // 从位图中获取颜色（注意可能的BGRA格式转换）
            u32* pixel = bitmap->pixels + src_y * bitmap->width + src_x;
            u32 color = *pixel;

            // 将颜色绘制到屏幕缓冲区
            DrawPixel(x, y, color);
        }
    }
}
```

![](img/7011eb2fe997e9d598bb4046015d583f_227.png)

![](img/7011eb2fe997e9d598bb4046015d583f_229.png)

![](img/7011eb2fe997e9d598bb4046015d583f_231.png)

![](img/7011eb2fe997e9d598bb4046015d583f_233.png)

![](img/7011eb2fe997e9d598bb4046015d583f_235.png)

![](img/7011eb2fe997e9d598bb4046015d583f_237.png)

**颜色格式转换：**
由于Windows通常使用BGRA字节顺序，而加载的像素数据可能是RGBA，因此可能需要在加载后或渲染前交换红色和蓝色通道。

![](img/7011eb2fe997e9d598bb4046015d583f_239.png)

![](img/7011eb2fe997e9d598bb4046015d583f_241.png)

![](img/7011eb2fe997e9d598bb4046015d583f_243.png)

![](img/7011eb2fe997e9d598bb4046015d583f_245.png)

![](img/7011eb2fe997e9d598bb4046015d583f_247.png)

## 实现子像素渲染 🔍

![](img/7011eb2fe997e9d598bb4046015d583f_249.png)

![](img/7011eb2fe997e9d598bb4046015d583f_250.png)

![](img/7011eb2fe997e9d598bb4046015d583f_252.png)

![](img/7011eb2fe997e9d598bb4046015d583f_254.png)

![](img/7011eb2fe997e9d598bb4046015d583f_256.png)

![](img/7011eb2fe997e9d598bb4046015d583f_258.png)

![](img/7011eb2fe997e9d598bb4046015d583f_260.png)

在基础渲染中，当物体移动速度小于一个像素每帧时，其位置在转换为整数像素坐标时会“卡顿”，导致动画不平滑。子像素渲染通过处理像素的分数部分来解决这个问题。

![](img/7011eb2fe997e9d598bb4046015d583f_262.png)

![](img/7011eb2fe997e9d598bb4046015d583f_264.png)

![](img/7011eb2fe997e9d598bb4046015d583f_266.png)

![](img/7011eb2fe997e9d598bb4046015d583f_268.png)

![](img/7011eb2fe997e9d598bb4046015d583f_270.png)

![](img/7011eb2fe997e9d598bb4046015d583f_272.png)

![](img/7011eb2fe997e9d598bb4046015d583f_274.png)

![](img/7011eb2fe997e9d598bb4046015d583f_276.png)

![](img/7011eb2fe997e9d598bb4046015d583f_277.png)

![](img/7011eb2fe997e9d598bb4046015d583f_279.png)

![](img/7011eb2fe997e9d598bb4046015d583f_281.png)

![](img/7011eb2fe997e9d598bb4046015d583f_283.png)

![](img/7011eb2fe997e9d598bb4046015d583f_285.png)

![](img/7011eb2fe997e9d598bb4046015d583f_287.png)

![](img/7011eb2fe997e9d598bb4046015d583f_289.png)

![](img/7011eb2fe997e9d598bb4046015d583f_291.png)

![](img/7011eb2fe997e9d598bb4046015d583f_293.png)

### 原理

![](img/7011eb2fe997e9d598bb4046015d583f_295.png)

![](img/7011eb2fe997e9d598bb4046015d583f_297.png)

![](img/7011eb2fe997e9d598bb4046015d583f_299.png)

![](img/7011eb2fe997e9d598bb4046015d583f_301.png)

![](img/7011eb2fe997e9d598bb4046015d583f_303.png)

![](img/7011eb2fe997e9d598bb4046015d583f_305.png)

![](img/7011eb2fe997e9d598bb4046015d583f_307.png)

![](img/7011eb2fe997e9d598bb4046015d583f_309.png)

![](img/7011eb2fe997e9d598bb4046015d583f_311.png)

![](img/7011eb2fe997e9d598bb4046015d583f_313.png)

![](img/7011eb2fe997e9d598bb4046015d583f_315.png)

![](img/7011eb2fe997e9d598bb4046015d583f_317.png)

![](img/7011eb2fe997e9d598bb4046015d583f_319.png)

假设一个矩形正在缓慢向右移动。在某一帧，它的左边缘位于像素`100.3`的位置。传统渲染会将其取整到像素`100`开始绘制。子像素渲染则：
1.  在像素`100`处绘制一条垂直边，但其不透明度仅为`0.7`（因为`0.3`的部分实际上属于前一个像素位置）。
2.  从像素`101`开始完整绘制矩形的其余部分。
这样，矩形的移动在视觉上就是连续平滑的，而不是跳跃的。

![](img/7011eb2fe997e9d598bb4046015d583f_321.png)

![](img/7011eb2fe997e9d598bb4046015d583f_323.png)

![](img/7011eb2fe997e9d598bb4046015d583f_325.png)

![](img/7011eb2fe997e9d598bb4046015d583f_327.png)

![](img/7011eb2fe997e9d598bb4046015d583f_329.png)

![](img/7011eb2fe997e9d598bb4046015d583f_331.png)

![](img/7011eb2fe997e9d598bb4046015d583f_333.png)

![](img/7011eb2fe997e9d598bb4046015d583f_335.png)

![](img/7011eb2fe997e9d598bb4046015d583f_337.png)

### 实现方法

![](img/7011eb2fe997e9d598bb4046015d583f_339.png)

![](img/7011eb2fe997e9d598bb4046015d583f_341.png)

![](img/7011eb2fe997e9d598bb4046015d583f_343.png)

![](img/7011eb2fe997e9d598bb4046015d583f_345.png)

![](img/7011eb2fe997e9d598bb4046015d583f_347.png)

![](img/7011eb2fe997e9d598bb4046015d583f_349.png)

![](img/7011eb2fe997e9d598bb4046015d583f_351.png)

![](img/7011eb2fe997e9d598bb4046015d583f_353.png)

![](img/7011eb2fe997e9d598bb4046015d583f_355.png)

![](img/7011eb2fe997e9d598bb4046015d583f_357.png)

![](img/7011eb2fe997e9d598bb4046015d583f_359.png)

![](img/7011eb2fe997e9d598bb4046015d583f_361.png)

![](img/7011eb2fe997e9d598bb4046015d583f_363.png)

![](img/7011eb2fe997e9d598bb4046015d583f_365.png)

![](img/7011eb2fe997e9d598bb4046015d583f_367.png)

![](img/7011eb2fe997e9d598bb4046015d583f_369.png)

以下是修改后的矩形绘制函数，添加了对左边缘和右边缘的子像素处理：

![](img/7011eb2fe997e9d598bb4046015d583f_371.png)

![](img/7011eb2fe997e9d598bb4046015d583f_373.png)

![](img/7011eb2fe997e9d598bb4046015d583f_375.png)

![](img/7011eb2fe997e9d598bb4046015d583f_377.png)

![](img/7011eb2fe997e9d598bb4046015d583f_379.png)

![](img/7011eb2fe997e9d598bb4046015d583f_381.png)

![](img/7011eb2fe997e9d598bb4046015d583f_383.png)

![](img/7011eb2fe997e9d598bb4046015d583f_385.png)

![](img/7011eb2fe997e9d598bb4046015d583f_387.png)

![](img/7011eb2fe997e9d598bb4046015d583f_389.png)

![](img/7011eb2fe997e9d598bb4046015d583f_391.png)

```c
internal void DrawRectangleSubpixel(v2 p, v2 half_size, v4 color) {
    f32 x0 = p.x - half_size.x;
    f32 x1 = p.x + half_size.x;
    f32 y0 = p.y - half_size.y;
    f32 y1 = p.y + half_size.y;

    i32 min_x = (i32)(x0 + 0.5f);
    i32 max_x = (i32)(x1 + 0.5f);
    i32 min_y = (i32)(y0 + 0.5f);
    i32 max_y = (i32)(y1 + 0.5f);

    // 计算左边缘的分数部分和alpha值
    f32 x0_f = x0 - (f32)min_x;
    f32 alpha_left = 1.0f - x0_f;
    if(alpha_left > 0.0f) {
        // 绘制左边缘的“半透明”像素列
        DrawRectangle((v2){min_x, (y0+y1)/2}, (v2){0.5f, half_size.y},
                      (v4){color.r, color.g, color.b, color.a * alpha_left});
    }

    // 计算右边缘的分数部分和alpha值
    f32 x1_f = (f32)(max_x) - x1;
    f32 alpha_right = 1.0f - x1_f;
    if(alpha_right > 0.0f) {
        // 绘制右边缘的“半透明”像素列
        DrawRectangle((v2){max_x, (y0+y1)/2}, (v2){0.5f, half_size.y},
                      (v4){color.r, color.g, color.b, color.a * alpha_right});
    }

    // 绘制矩形的内部（不包含已特殊处理的边缘）
    i32 inner_min_x = (x0_f > 0.0f) ? min_x + 1 : min_x;
    i32 inner_max_x = (x1_f > 0.0f) ? max_x - 1 : max_x;
    DrawRectangleSolid(inner_min_x, inner_max_x, min_y, max_y, color);
}
```
**注意**：这是一个简化的示意实现。完整的实现还需要处理上边缘和下边缘，并避免对四个角进行重复混合。对于玩家挡板等主要水平移动的物体，处理左右边缘即可显著提升视觉效果。

![](img/7011eb2fe997e9d598bb4046015d583f_393.png)

![](img/7011eb2fe997e9d598bb4046015d583f_395.png)

![](img/7011eb2fe997e9d598bb4046015d583f_397.png)

![](img/7011eb2fe997e9d598bb4046015d583f_399.png)

![](img/7011eb2fe997e9d598bb4046015d583f_401.png)

![](img/7011eb2fe997e9d598bb4046015d583f_403.png)

![](img/7011eb2fe997e9d598bb4046015d583f_405.png)

![](img/7011eb2fe997e9d598bb4046015d583f_407.png)

![](img/7011eb2fe997e9d598bb4046015d583f_409.png)

![](img/7011eb2fe997e9d598bb4046015d583f_411.png)

![](img/7011eb2fe997e9d598bb4046015d583f_413.png)

![](img/7011eb2fe997e9d598bb4046015d583f_415.png)

![](img/7011eb2fe997e9d598bb4046015d583f_417.png)

![](img/7011eb2fe997e9d598bb4046015d583f_419.png)

![](img/7011eb2fe997e9d598bb4046015d583f_421.png)

![](img/7011eb2fe997e9d598bb4046015d583f_423.png)

![](img/7011eb2fe997e9d598bb4046015d583f_424.png)

![](img/7011eb2fe997e9d598bb4046015d583f_426.png)

![](img/7011eb2fe997e9d598bb4046015d583f_428.png)

![](img/7011eb2fe997e9d598bb4046015d583f_430.png)

## 整合与优化 🛠️

![](img/7011eb2fe997e9d598bb4046015d583f_432.png)

![](img/7011eb2fe997e9d598bb4046015d583f_434.png)

![](img/7011eb2fe997e9d598bb4046015d583f_436.png)

![](img/7011eb2fe997e9d598bb4046015d583f_438.png)

![](img/7011eb2fe997e9d598bb4046015d583f_440.png)

![](img/7011eb2fe997e9d598bb4046015d583f_442.png)

![](img/7011eb2fe997e9d598bb4046015d583f_444.png)

![](img/7011eb2fe997e9d598bb4046015d583f_446.png)

![](img/7011eb2fe997e9d598bb4046015d583f_448.png)

![](img/7011eb2fe997e9d598bb4046015d583f_450.png)

![](img/7011eb2fe997e9d598bb4046015d583f_452.png)

![](img/7011eb2fe997e9d598bb4046015d583f_454.png)

![](img/7011eb2fe997e9d598bb4046015d583f_456.png)

![](img/7011eb2fe997e9d598bb4046015d583f_458.png)

![](img/7011eb2fe997e9d598bb4046015d583f_460.png)

![](img/7011eb2fe997e9d598bb4046015d583f_462.png)

![](img/7011eb2fe997e9d598bb4046015d583f_464.png)

![](img/7011eb2fe997e9d598bb4046015d583f_466.png)

将位图渲染集成到游戏中的步骤如下：

![](img/7011eb2fe997e9d598bb4046015d583f_468.png)

![](img/7011eb2fe997e9d598bb4046015d583f_470.png)

![](img/7011eb2fe997e9d598bb4046015d583f_471.png)

![](img/7011eb2fe997e9d598bb4046015d583f_473.png)

![](img/7011eb2fe997e9d598bb4046015d583f_474.png)

![](img/7011eb2fe997e9d598bb4046015d583f_476.png)

![](img/7011eb2fe997e9d598bb4046015d583f_478.png)

![](img/7011eb2fe997e9d598bb4046015d583f_480.png)

![](img/7011eb2fe997e9d598bb4046015d583f_482.png)

![](img/7011eb2fe997e9d598bb4046015d583f_484.png)

![](img/7011eb2fe997e9d598bb4046015d583f_486.png)

![](img/7011eb2fe997e9d598bb4046015d583f_488.png)

![](img/7011eb2fe997e9d598bb4046015d583f_490.png)

![](img/7011eb2fe997e9d598bb4046015d583f_492.png)

![](img/7011eb2fe997e9d598bb4046015d583f_494.png)

![](img/7011eb2fe997e9d598bb4046015d583f_495.png)

![](img/7011eb2fe997e9d598bb4046015d583f_497.png)

![](img/7011eb2fe997e9d598bb4046015d583f_499.png)

![](img/7011eb2fe997e9d598bb4046015d583f_501.png)

![](img/7011eb2fe997e9d598bb4046015d583f_503.png)

![](img/7011eb2fe997e9d598bb4046015d583f_505.png)

![](img/7011eb2fe997e9d598bb4046015d583f_507.png)

![](img/7011eb2fe997e9d598bb4046015d583f_509.png)

以下是整合位图到游戏逻辑中的关键步骤：

![](img/7011eb2fe997e9d598bb4046015d583f_511.png)

![](img/7011eb2fe997e9d598bb4046015d583f_513.png)

![](img/7011eb2fe997e9d598bb4046015d583f_515.png)

![](img/7011eb2fe997e9d598bb4046015d583f_517.png)

![](img/7011eb2fe997e9d598bb4046015d583f_519.png)

![](img/7011eb2fe997e9d598bb4046015d583f_521.png)

![](img/7011eb2fe997e9d598bb4046015d583f_523.png)

![](img/7011eb2fe997e9d598bb4046015d583f_525.png)

![](img/7011eb2fe997e9d598bb4046015d583f_527.png)

![](img/7011eb2fe997e9d598bb4046015d583f_529.png)

![](img/7011eb2fe997e9d598bb4046015d583f_530.png)

![](img/7011eb2fe997e9d598bb4046015d583f_532.png)

![](img/7011eb2fe997e9d598bb4046015d583f_534.png)

![](img/7011eb2fe997e9d598bb4046015d583f_536.png)

![](img/7011eb2fe997e9d598bb4046015d583f_538.png)

![](img/7011eb2fe997e9d598bb4046015d583f_540.png)

![](img/7011eb2fe997e9d598bb4046015d583f_542.png)

![](img/7011eb2fe997e9d598bb4046015d583f_543.png)

![](img/7011eb2fe997e9d598bb4046015d583f_545.png)

![](img/7011eb2fe997e9d598bb4046015d583f_546.png)

![](img/7011eb2fe997e9d598bb4046015d583f_548.png)

![](img/7011eb2fe997e9d598bb4046015d583f_550.png)

1.  **加载所有资源**：在游戏初始化时，加载所有道具的位图（无敌、三连发、评论、TNT、乌龟、反向控制、坚固方块等）。
2.  **修改渲染逻辑**：在绘制道具的代码中，将原来的彩色方块绘制替换为对应的位图绘制函数调用。使用`switch`语句根据道具类型选择正确的位图。
3.  **添加视觉反馈**：为“无敌”状态添加一个半透明的力场动画位图，并使其透明度随时间变化，以提示玩家剩余的无敌时间。
4.  **优化性能**：
    -   由于添加了图像库，编译时间可能变长。可以考虑在开发时排除不使用的库功能。
    -   子像素渲染会增加每帧的绘制操作，对于移动缓慢的物体是值得的，但对于快速移动的物体可能不是必需的。

![](img/7011eb2fe997e9d598bb4046015d583f_552.png)

![](img/7011eb2fe997e9d598bb4046015d583f_554.png)

![](img/7011eb2fe997e9d598bb4046015d583f_556.png)

![](img/7011eb2fe997e9d598bb4046015d583f_558.png)

![](img/7011eb2fe997e9d598bb4046015d583f_560.png)

![](img/7011eb2fe997e9d598bb4046015d583f_561.png)

![](img/7011eb2fe997e9d598bb4046015d583f_563.png)

![](img/7011eb2fe997e9d598bb4046015d583f_565.png)

![](img/7011eb2fe997e9d598bb4046015d583f_567.png)

![](img/7011eb2fe997e9d598bb4046015d583f_569.png)

![](img/7011eb2fe997e9d598bb4046015d583f_571.png)

![](img/7011eb2fe997e9d598bb4046015d583f_573.png)

![](img/7011eb2fe997e9d598bb4046015d583f_575.png)

![](img/7011eb2fe997e9d598bb4046015d583f_577.png)

![](img/7011eb2fe997e9d598bb4046015d583f_579.png)

![](img/7011eb2fe997e9d598bb4046015d583f_581.png)

![](img/7011eb2fe997e9d598bb4046015d583f_583.png)

![](img/7011eb2fe997e9d598bb4046015d583f_585.png)

![](img/7011eb2fe997e9d598bb4046015d583f_587.png)

![](img/7011eb2fe997e9d598bb4046015d583f_589.png)

![](img/7011eb2fe997e9d598bb4046015d583f_591.png)

![](img/7011eb2fe997e9d598bb4046015d583f_592.png)

![](img/7011eb2fe997e9d598bb4046015d583f_594.png)

![](img/7011eb2fe997e9d598bb4046015d583f_596.png)

## 总结 🎯

![](img/7011eb2fe997e9d598bb4046015d583f_598.png)

![](img/7011eb2fe997e9d598bb4046015d583f_600.png)

![](img/7011eb2fe997e9d598bb4046015d583f_602.png)

![](img/7011eb2fe997e9d598bb4046015d583f_604.png)

![](img/7011eb2fe997e9d598bb4046015d583f_606.png)

![](img/7011eb2fe997e9d598bb4046015d583f_608.png)

![](img/7011eb2fe997e9d598bb4046015d583f_610.png)

![](img/7011eb2fe997e9d598bb4046015d583f_612.png)

![](img/7011eb2fe997e9d598bb4046015d583f_614.png)

![](img/7011eb2fe997e9d598bb4046015d583f_615.png)

![](img/7011eb2fe997e9d598bb4046015d583f_617.png)

![](img/7011eb2fe997e9d598bb4046015d583f_619.png)

![](img/7011eb2fe997e9d598bb4046015d583f_621.png)

![](img/7011eb2fe997e9d598bb4046015d583f_623.png)

![](img/7011eb2fe997e9d598bb4046015d583f_625.png)

本节课中我们一起学习了两个提升游戏视觉质量的核心技术：

![](img/7011eb2fe997e9d598bb4046015d583f_627.png)

![](img/7011eb2fe997e9d598bb4046015d583f_629.png)

![](img/7011eb2fe997e9d598bb4046015d583f_631.png)

![](img/7011eb2fe997e9d598bb4046015d583f_633.png)

![](img/7011eb2fe997e9d598bb4046015d583f_635.png)

![](img/7011eb2fe997e9d598bb4046015d583f_637.png)

![](img/7011eb2fe997e9d598bb4046015d583f_639.png)

![](img/7011eb2fe997e9d598bb4046015d583f_641.png)

![](img/7011eb2fe997e9d598bb4046015d583f_643.png)

![](img/7011eb2fe997e9d598bb4046015d583f_645.png)

![](img/7011eb2fe997e9d598bb4046015d583f_647.png)

![](img/7011eb2fe997e9d598bb4046015d583f_649.png)

![](img/7011eb2fe997e9d598bb4046015d583f_651.png)

1.  **位图渲染**：我们学会了如何从文件加载PNG图像，将其解码为像素数据，并在屏幕上绘制。这使得游戏中的道具拥有了独特且易于识别的图标，极大地改善了游戏的视觉表达和用户体验。
2.  **子像素渲染**：我们探讨了传统整数像素渲染在慢速动画中的缺陷，并实现了一种通过处理像素分数部分来平滑边缘的渲染技巧。这使得玩家挡板等物体的移动看起来更加流畅自然。

![](img/7011eb2fe997e9d598bb4046015d583f_653.png)

![](img/7011eb2fe997e9d598bb4046015d583f_655.png)

![](img/7011eb2fe997e9d598bb4046015d583f_657.png)

![](img/7011eb2fe997e9d598bb4046015d583f_659.png)

![](img/7011eb2fe997e9d598bb4046015d583f_661.png)

![](img/7011eb2fe997e9d598bb4046015d583f_663.png)

![](img/7011eb2fe997e9d598bb4046015d583f_665.png)

![](img/7011eb2fe997e9d598bb4046015d583f_667.png)

![](img/7011eb2fe997e9d598bb4046015d583f_669.png)

![](img/7011eb2fe997e9d598bb4046015d583f_671.png)

![](img/7011eb2fe997e9d598bb4046015d583f_673.png)

![](img/7011eb2fe997e9d598bb4046015d583f_675.png)

![](img/7011eb2fe997e9d598bb4046015d583f_677.png)

![](img/7011eb2fe997e9d598bb4046015d583f_679.png)

![](img/7011eb2fe997e9d598bb4046015d583f_681.png)

![](img/7011eb2fe997e9d598bb4046015d583f_682.png)

![](img/7011eb2fe997e9d598bb4046015d583f_684.png)

![](img/7011eb2fe997e9d598bb4046015d583f_685.png)

![](img/7011eb2fe997e9d598bb4046015d583f_687.png)

![](img/7011eb2fe997e9d598bb4046015d583f_689.png)

![](img/7011eb2fe997e9d598bb4046015d583f_690.png)

![](img/7011eb2fe997e9d598bb4046015d583f_692.png)

![](img/7011eb2fe997e9d598bb4046015d583f_694.png)

![](img/7011eb2fe997e9d598bb4046015d583f_695.png)

![](img/7011eb2fe997e9d598bb4046015d583f_697.png)

![](img/7011eb2fe997e9d598bb4046015d583f_699.png)

![](img/7011eb2fe997e9d598bb4046015d583f_701.png)

通过实现这些功能，我们的游戏引擎在视觉渲染方面变得更加完善。游戏的外观和感觉因为自定义图标和平滑的动画而获得了质的飞跃。

![](img/7011eb2fe997e9d598bb4046015d583f_703.png)

![](img/7011eb2fe997e9d598bb4046015d583f_704.png)

![](img/7011eb2fe997e9d598bb4046015d583f_706.png)

![](img/7011eb2fe997e9d598bb4046015d583f_708.png)

![](img/7011eb2fe997e9d598bb4046015d583f_710.png)

![](img/7011eb2fe997e9d598bb4046015d583f_712.png)

![](img/7011eb2fe997e9d598bb4046015d583f_714.png)

![](img/7011eb2fe997e9d598bb4046015d583f_716.png)

![](img/7011eb2fe997e9d598bb4046015d583f_718.png)

![](img/7011eb2fe997e9d598bb4046015d583f_720.png)

![](img/7011eb2fe997e9d598bb4046015d583f_722.png)

![](img/7011eb2fe997e9d598bb4046015d583f_724.png)

![](img/7011eb2fe997e9d598bb4046015d583f_726.png)

![](img/7011eb2fe997e9d598bb4046015d583f_728.png)

![](img/7011eb2fe997e9d598bb4046015d583f_730.png)

![](img/7011eb2fe997e9d598bb4046015d583f_732.png)

![](img/7011eb2fe997e9d598bb4046015d583f_734.png)

在接下来的课程中，我们将为游戏添加**音频支持**，让游戏世界更加生动，然后进一步探索**多线程**技术来优化性能。敬请期待！