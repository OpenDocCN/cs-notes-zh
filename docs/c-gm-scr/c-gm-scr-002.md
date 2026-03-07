# 002：游戏玩法与碰撞检测 🎮

![](img/2c5915bbf2791187d13c00d769bdde9e_1.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_3.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_5.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_6.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_8.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_10.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_12.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_14.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_15.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_16.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_18.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_20.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_22.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_24.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_26.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_28.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_30.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_32.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_34.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_36.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_38.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_40.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_42.png)

在本节课中，我们将学习如何为我们的C语言游戏添加核心的游戏玩法和碰撞检测系统。我们将从控制玩家板开始，然后实现球的物理运动，最后构建一个能够处理球与玩家、墙壁以及砖块之间交互的碰撞系统。

![](img/2c5915bbf2791187d13c00d769bdde9e_44.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_45.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_46.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_48.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_49.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_51.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_53.png)

---

![](img/2c5915bbf2791187d13c00d769bdde9e_55.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_57.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_58.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_60.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_62.png)

## 概述

![](img/2c5915bbf2791187d13c00d769bdde9e_64.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_66.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_68.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_70.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_72.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_73.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_75.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_77.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_79.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_81.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_83.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_85.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_87.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_89.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_91.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_93.png)

上一节我们创建了基础的平台层和引擎，使我们能够渲染图形和处理输入。本节中，我们将在此基础上构建实际的游戏内容。我们的目标是制作一个打砖块游戏的克隆，并逐步添加更有趣的玩法。

![](img/2c5915bbf2791187d13c00d769bdde9e_95.png)

我们将首先实现鼠标控制玩家板，然后添加球和基本的物理运动。核心挑战在于实现一个精确的碰撞检测系统，使球能够与玩家板、墙壁以及砖块正确交互。

![](img/2c5915bbf2791187d13c00d769bdde9e_97.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_99.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_101.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_103.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_105.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_107.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_109.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_111.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_113.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_115.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_117.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_119.png)

---

![](img/2c5915bbf2791187d13c00d769bdde9e_121.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_123.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_125.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_127.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_129.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_131.png)

## 鼠标控制玩家板 🖱️

![](img/2c5915bbf2791187d13c00d769bdde9e_133.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_135.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_137.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_139.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_141.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_143.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_145.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_147.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_149.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_151.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_153.png)

为了创建打砖块游戏，第一步是让鼠标光标控制屏幕上的小方块（即玩家板），而不是使用键盘。这能提供更有趣的游戏体验。

![](img/2c5915bbf2791187d13c00d769bdde9e_155.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_156.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_158.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_160.png)

以下是实现步骤：

![](img/2c5915bbf2791187d13c00d769bdde9e_162.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_164.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_166.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_168.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_170.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_172.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_174.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_176.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_178.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_180.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_182.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_184.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_186.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_188.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_190.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_192.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_194.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_196.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_198.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_200.png)

1.  **获取鼠标位置**：在Windows平台层中，我们调用 `GetCursorPos` 函数来获取鼠标在屏幕坐标系中的位置。
2.  **坐标转换**：由于获取的是屏幕坐标，我们需要使用 `ScreenToClient` 函数将其转换为相对于我们游戏窗口的坐标。
3.  **坐标系统转换**：Windows的坐标系原点在左上角，Y轴向下。而我们的游戏世界坐标系原点在中心，Y轴向上。因此，我们需要对Y坐标进行转换：`y = 窗口高度 - y`。
4.  **像素到世界单位**：鼠标坐标最初是像素值。为了与游戏世界中的其他物体（使用世界单位）进行交互，我们需要一个辅助函数将像素坐标转换为世界坐标。

![](img/2c5915bbf2791187d13c00d769bdde9e_202.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_204.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_206.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_208.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_210.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_212.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_214.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_216.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_218.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_220.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_222.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_224.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_226.png)

**像素到世界坐标转换公式**：
```c
V2 PixelsToWorld(V2I pixel_coordinate, Render_Buffer render_buffer, f32 scale) {
    V2 result;
    // 1. 偏移到中心
    result.x = (f32)pixel_coordinate.x - (f32)render_buffer.width * 0.5f;
    result.y = (f32)pixel_coordinate.y - (f32)render_buffer.height * 0.5f;

    // 2. 根据宽高比调整
    f32 aspect_multiplier = (render_buffer.height > render_buffer.width) ? ((f32)render_buffer.height / (f32)render_buffer.width) : 1.0f;

    // 3. 除以缩放比例和宽高比乘数，得到世界坐标
    result.x /= (aspect_multiplier * scale);
    result.y /= (aspect_multiplier * scale);

    // 注意：Y轴可能需要反转，取决于你的坐标系
    result.y = -result.y;

    return result;
}
```

![](img/2c5915bbf2791187d13c00d769bdde9e_228.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_230.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_232.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_234.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_235.png)

完成这些步骤后，玩家板就能平滑地跟随鼠标移动了。

![](img/2c5915bbf2791187d13c00d769bdde9e_237.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_238.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_240.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_242.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_244.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_246.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_248.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_250.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_252.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_254.png)

---

![](img/2c5915bbf2791187d13c00d769bdde9e_256.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_258.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_260.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_262.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_264.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_266.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_268.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_270.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_272.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_274.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_276.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_278.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_279.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_280.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_282.png)

## 创建球与基础物理 ⚽

![](img/2c5915bbf2791187d13c00d769bdde9e_284.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_285.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_287.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_289.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_291.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_293.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_295.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_297.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_299.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_301.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_303.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_305.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_307.png)

有了可控制的玩家板，下一步是创建球并为其添加基础物理运动。

![](img/2c5915bbf2791187d13c00d769bdde9e_309.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_311.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_313.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_314.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_316.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_318.png)

以下是实现步骤：

![](img/2c5915bbf2791187d13c00d769bdde9e_320.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_321.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_323.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_325.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_327.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_329.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_331.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_333.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_335.png)

1.  **定义球的状态**：我们需要记录球的位置 (`ball_p`) 和速度 (`ball_dp`)。
2.  **初始化**：在游戏循环开始时，设置球的初始位置和速度。例如，让球从屏幕上方以一定速度下落。
3.  **更新位置**：每一帧，根据球的速度和帧间隔时间 (`dt`) 来更新球的位置。这需要基础的向量加法运算。
4.  **渲染球**：使用一个固定大小的矩形来代表球，并为其选择一个醒目的颜色。

![](img/2c5915bbf2791187d13c00d769bdde9e_337.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_339.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_341.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_343.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_345.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_347.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_349.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_351.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_353.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_355.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_357.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_359.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_361.png)

**球的位置更新公式**：
```c
// 假设有向量加法函数 add_v2 和标量乘法函数 mul_v2
ball_p = add_v2(ball_p, mul_v2(ball_dp, dt));
```

![](img/2c5915bbf2791187d13c00d769bdde9e_363.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_365.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_367.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_369.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_371.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_373.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_375.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_377.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_379.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_381.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_382.png)

通过调整初始速度，我们可以控制球的移动快慢，为碰撞检测做准备。

![](img/2c5915bbf2791187d13c00d769bdde9e_384.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_386.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_388.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_390.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_392.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_394.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_396.png)

---

![](img/2c5915bbf2791187d13c00d769bdde9e_398.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_400.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_402.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_404.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_406.png)

## 实现碰撞检测系统 💥

![](img/2c5915bbf2791187d13c00d769bdde9e_408.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_410.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_412.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_414.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_416.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_418.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_420.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_422.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_424.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_426.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_428.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_430.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_432.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_434.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_436.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_438.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_440.png)

游戏玩法的核心是碰撞检测。我们需要检测球与玩家板、球与墙壁以及球与砖块之间的碰撞。

![](img/2c5915bbf2791187d13c00d769bdde9e_442.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_444.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_446.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_448.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_450.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_452.png)

### AABB（轴对齐边界框）碰撞检测

![](img/2c5915bbf2791187d13c00d769bdde9e_454.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_456.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_458.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_460.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_462.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_464.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_466.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_468.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_470.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_472.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_474.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_475.png)

我们使用AABB碰撞检测，因为它简单高效，适用于我们的矩形物体。基本思想是：两个轴对齐的矩形相交，当且仅当它们在X轴和Y轴上的投影都重叠。

![](img/2c5915bbf2791187d13c00d769bdde9e_477.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_479.png)

**AABB碰撞检测函数**：
```c
b32 AABBvsAABB(V2 p1, V2 half_size1, V2 p2, V2 half_size2) {
    // 检查X轴重叠
    b32 overlap_x = (p1.x + half_size1.x > p2.x - half_size2.x) &&
                    (p1.x - half_size1.x < p2.x + half_size2.x);
    // 检查Y轴重叠
    b32 overlap_y = (p1.y + half_size1.y > p2.y - half_size2.y) &&
                    (p1.y - half_size1.y < p2.y + half_size2.y);

    // 两个轴都重叠才发生碰撞
    return (overlap_x && overlap_y);
}
```

![](img/2c5915bbf2791187d13c00d769bdde9e_481.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_483.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_485.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_487.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_488.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_490.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_492.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_494.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_496.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_498.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_500.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_502.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_504.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_506.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_508.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_510.png)

### 球与玩家板碰撞

![](img/2c5915bbf2791187d13c00d769bdde9e_512.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_514.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_516.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_518.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_520.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_522.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_523.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_525.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_527.png)

当检测到球与玩家板碰撞时，我们不仅需要让球反弹，还可以根据玩家板的水平移动速度来影响球的水平速度，从而增加游戏的可控性。

![](img/2c5915bbf2791187d13c00d769bdde9e_529.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_531.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_533.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_535.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_537.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_539.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_541.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_543.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_545.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_547.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_549.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_550.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_552.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_554.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_556.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_558.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_560.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_562.png)

1.  **反弹**：反转球的Y轴速度 (`ball_dp.y = -ball_dp.y`)。
2.  **速度影响**：计算玩家板本帧的水平速度，并将其一部分加到球的水平速度上。这需要将玩家板的像素位移转换为每秒钟的世界单位位移。
    ```c
    // 计算玩家板水平速度（世界单位/秒）
    player_dp.x = (player_desired_p.x - player_p.x) / dt;
    // 将部分速度加到球上
    ball_dp.x += player_dp.x * 0.5f; // 0.5f是一个影响系数，可以调整
    ```
3.  **防止卡住**：简单的速度反转可能导致球在下一帧仍然与板重叠，造成“卡住”或反复反弹。一个解决方案是，只在球朝向玩家板移动（即 `ball_dp.y < 0`）时才检测碰撞并反弹。

![](img/2c5915bbf2791187d13c00d769bdde9e_564.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_566.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_567.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_569.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_571.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_573.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_575.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_577.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_579.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_581.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_583.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_585.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_587.png)

### 球与墙壁碰撞

![](img/2c5915bbf2791187d13c00d769bdde9e_589.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_591.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_593.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_595.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_597.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_599.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_601.png)

为了让球在游戏区域内运动，我们需要检测球与墙壁（游戏区域边界）的碰撞。

![](img/2c5915bbf2791187d13c00d769bdde9e_603.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_604.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_606.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_608.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_610.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_612.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_614.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_616.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_618.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_620.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_622.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_624.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_626.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_628.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_630.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_632.png)

1.  **定义游戏区域**：我们定义一个“竞技场”矩形作为游戏区域的边界。
2.  **碰撞检测与响应**：
    *   **左右墙壁**：如果球碰到左右墙壁，反转其X轴速度 (`ball_dp.x = -ball_dp.x`)，并可能将球的位置修正到刚好接触墙壁的位置，防止穿透。
    *   **上下墙壁**：如果球碰到上墙壁，同样反转Y轴速度。如果球碰到下墙壁（即玩家板没接住），可以触发游戏结束逻辑。

![](img/2c5915bbf2791187d13c00d769bdde9e_634.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_636.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_638.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_640.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_642.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_644.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_646.png)

**墙壁碰撞处理示例（右墙）**：
```c
if (ball_p.x + ball_half_size.x > arena_half_size.x) {
    // 反转X速度
    ball_dp.x = -ball_dp.x;
    // 可选：将球的位置修正到墙边
    ball_p.x = arena_half_size.x - ball_half_size.x;
}
```

![](img/2c5915bbf2791187d13c00d769bdde9e_648.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_649.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_651.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_653.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_655.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_657.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_659.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_661.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_663.png)

### 球与砖块碰撞

![](img/2c5915bbf2791187d13c00d769bdde9e_665.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_666.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_668.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_670.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_672.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_674.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_676.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_678.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_680.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_682.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_684.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_686.png)

这是游戏的主要目标。我们需要管理一组砖块，检测球与每个砖块的碰撞，并在碰撞时销毁砖块并让球反弹。

![](img/2c5915bbf2791187d13c00d769bdde9e_688.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_690.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_692.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_694.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_696.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_698.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_700.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_702.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_704.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_705.png)

1.  **砖块数据结构**：为砖块创建一个结构体，至少包含位置 (`p`)、是否存活 (`life`) 和半大小 (`half_size`)。
2.  **初始化砖块网格**：在游戏初始化时，创建一个砖块网格。计算每个砖块的位置，使其在屏幕上居中排列。
3.  **碰撞检测与响应**：
    *   遍历所有存活的砖块。
    *   对每个砖块，使用AABB检测与球的碰撞。
    *   如果发生碰撞，将砖块的 `life` 减为0（销毁），并让球反弹。
4.  **反弹方向判定**：简单的速度反转（同时反转X和Y）可能导致不自然的行为。更精确的方法是判断球是从砖块的哪一侧撞入的，然后只反转相应的速度分量。这可以通过比较球在本帧的旧位置和当前位置与砖块边界的关系来实现（一种简化的“扫描”法）。

![](img/2c5915bbf2791187d13c00d769bdde9e_707.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_709.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_711.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_713.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_715.png)

**简化的砖块碰撞方向判断**：
```c
// ball_p_old 是球上一帧的位置
if (AABBvsAABB(block_p, block_half_size, ball_p, ball_half_size)) {
    // 销毁砖块
    block_life = 0;

    // 判断是从左右撞入还是上下撞入
    // 如果球的旧位置在砖块的左侧且新位置在右侧（或反之），则反转X速度
    if ((ball_p_old.x < block_p.x - block_half_size.x && ball_p.x >= block_p.x - block_half_size.x) ||
        (ball_p_old.x > block_p.x + block_half_size.x && ball_p.x <= block_p.x + block_half_size.x)) {
        ball_dp.x = -ball_dp.x;
    }
    // 否则，假设是从上下撞入，反转Y速度
    else {
        ball_dp.y = -ball_dp.y;
    }
}
```

![](img/2c5915bbf2791187d13c00d769bdde9e_717.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_719.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_721.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_723.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_725.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_727.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_729.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_730.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_732.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_734.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_736.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_738.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_740.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_742.png)

### 更精确的扫描碰撞检测

![](img/2c5915bbf2791187d13c00d769bdde9e_744.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_746.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_748.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_750.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_752.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_754.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_756.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_758.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_760.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_762.png)

上述简化方法在球速很快或砖块很小时可能失效。更健壮的方法是使用**扫描碰撞检测**。其核心思想是：将球在本帧的移动视为一条从旧位置 (`start`) 到新位置 (`end`) 的线段。我们检测这条线段与砖块（扩大球自身半径后的）AABB的相交。

![](img/2c5915bbf2791187d13c00d769bdde9e_764.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_766.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_768.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_770.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_772.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_774.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_776.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_778.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_780.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_782.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_784.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_786.png)

1.  **计算线段**：`start = ball_p_old`, `end = ball_p_desired` (或 `ball_p`)。
2.  **分别计算X轴和Y轴的相交参数**：对于每个轴，计算线段需要移动多少比例（`t`值，范围0到1）才能与砖块的边界接触。
3.  **确定最早碰撞的轴**：比较X轴和Y轴的 `t` 值，较小的那个代表最先发生碰撞的边界。
4.  **响应碰撞**：根据最早碰撞的边界（左/右或上/下）来反转相应的速度分量，并可以将球的位置修正到碰撞点。

![](img/2c5915bbf2791187d13c00d769bdde9e_788.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_790.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_792.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_794.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_796.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_797.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_798.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_800.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_802.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_804.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_806.png)

这种方法能更准确地处理高速运动和各种角度的碰撞，是许多游戏物理引擎的基础。实现它需要一些线性代数的知识，但能显著提升碰撞的可靠性。

![](img/2c5915bbf2791187d13c00d769bdde9e_808.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_809.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_811.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_813.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_815.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_817.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_819.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_821.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_822.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_824.png)

---

![](img/2c5915bbf2791187d13c00d769bdde9e_826.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_828.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_829.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_831.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_833.png)

## 性能优化与收尾工作 🛠️

![](img/2c5915bbf2791187d13c00d769bdde9e_835.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_837.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_839.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_841.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_843.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_845.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_847.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_849.png)

在实现了核心玩法后，我们可以进行一些优化和打磨：

![](img/2c5915bbf2791187d13c00d769bdde9e_851.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_853.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_855.png)

1.  **渲染优化**：我们之前绘制背景（清除屏幕）和绘制竞技场边框是分开的两个全屏操作。可以优化 `draw_rect` 函数，使其只绘制矩形的边框，而不是填充整个矩形内部，从而减少像素填充操作。
2.  **输入平滑**：对于鼠标控制，通常不需要额外的平滑处理，因为鼠标本身提供了连续的输入。但我们可以限制玩家板影响球速的最大值，防止球速过快导致游戏失控。
    ```c
    // 钳制玩家速度对球的影响
    f32 speed_influence = player_dp.x * 0.5f;
    speed_influence = clamp(speed_influence, -100.0f, 100.0f); // 假设-100到100是合理范围
    ball_dp.x += speed_influence;
    ```
3.  **游戏平衡**：调整球的速度、玩家板的影响系数、砖块的布局和数量，来获得最佳的游戏难度和乐趣。
4.  **修复坐标问题**：确保从窗口获取的渲染尺寸是客户区大小 (`GetClientRect`)，而不是整个窗口的大小 (`GetWindowRect`)，这样才能保证鼠标坐标和渲染坐标的对齐。

![](img/2c5915bbf2791187d13c00d769bdde9e_857.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_859.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_861.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_863.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_865.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_867.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_869.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_871.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_873.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_875.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_877.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_879.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_881.png)

---

![](img/2c5915bbf2791187d13c00d769bdde9e_883.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_885.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_887.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_889.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_891.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_893.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_895.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_897.png)

## 总结

![](img/2c5915bbf2791187d13c00d769bdde9e_899.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_901.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_903.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_905.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_907.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_909.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_911.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_913.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_915.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_917.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_919.png)

本节课中，我们一起学习了如何为C语言游戏添加核心玩法。我们从鼠标控制开始，实现了玩家板的移动。然后创建了球并为其添加了基础的物理运动。最后，我们深入探讨了碰撞检测系统，实现了球与玩家板、墙壁以及砖块之间的交互。

![](img/2c5915bbf2791187d13c00d769bdde9e_921.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_923.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_925.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_927.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_929.png)

我们介绍了简单的AABB碰撞检测，并探讨了其局限性。为了解决高速运动下的碰撞问题，我们引入了扫描碰撞检测的概念。虽然实现一个完美的碰撞系统充满挑战，但这是游戏开发中至关重要且有趣的一环。

![](img/2c5915bbf2791187d13c00d769bdde9e_931.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_933.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_935.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_936.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_938.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_940.png)

![](img/2c5915bbf2791187d13c00d769bdde9e_942.png)

现在，我们拥有了一个可玩的打砖块游戏原型！在接下来的课程中，我们可以在此基础上添加更多功能，如粒子特效、音效、更复杂的关卡设计和游戏状态管理，让游戏变得更加丰富和有趣。