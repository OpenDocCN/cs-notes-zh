# 006：游戏调试与改进 🎮

![](img/fb0e7f46d547648aaa046497e55447ae_1.png)

![](img/fb0e7f46d547648aaa046497e55447ae_3.png)

![](img/fb0e7f46d547648aaa046497e55447ae_5.png)

![](img/fb0e7f46d547648aaa046497e55447ae_7.png)

在本节课中，我们将对之前开发的游戏进行调试和改进。我们将修复累积的bug，完成未实现的功能，并添加一个简单的计分系统，让游戏体验更加完整。

![](img/fb0e7f46d547648aaa046497e55447ae_9.png)

![](img/fb0e7f46d547648aaa046497e55447ae_11.png)

![](img/fb0e7f46d547648aaa046497e55447ae_13.png)

## 概述 📋

![](img/fb0e7f46d547648aaa046497e55447ae_15.png)

![](img/fb0e7f46d547648aaa046497e55447ae_17.png)

![](img/fb0e7f46d547648aaa046497e55447ae_19.png)

![](img/fb0e7f46d547648aaa046497e55447ae_21.png)

![](img/fb0e7f46d547648aaa046497e55447ae_23.png)

![](img/fb0e7f46d547648aaa046497e55447ae_25.png)

![](img/fb0e7f46d547648aaa046497e55447ae_27.png)

![](img/fb0e7f46d547648aaa046497e55447ae_29.png)

![](img/fb0e7f46d547648aaa046497e55447ae_31.png)

![](img/fb0e7f46d547648aaa046497e55447ae_33.png)

![](img/fb0e7f46d547648aaa046497e55447ae_35.png)

上一节我们为游戏添加了多种玩法机制，如特殊方块和能量道具。本节我们将专注于解决这些新功能引入的问题，并完善游戏的核心体验。我们将修复鼠标控制、完成能量道具、添加计分系统，并解决一些碰撞检测的bug。

![](img/fb0e7f46d547648aaa046497e55447ae_37.png)

![](img/fb0e7f46d547648aaa046497e55447ae_39.png)

![](img/fb0e7f46d547648aaa046497e55447ae_41.png)

![](img/fb0e7f46d547648aaa046497e55447ae_43.png)

---

![](img/fb0e7f46d547648aaa046497e55447ae_45.png)

![](img/fb0e7f46d547648aaa046497e55447ae_47.png)

![](img/fb0e7f46d547648aaa046497e55447ae_49.png)

![](img/fb0e7f46d547648aaa046497e55447ae_51.png)

![](img/fb0e7f46d547648aaa046497e55447ae_53.png)

![](img/fb0e7f46d547648aaa046497e55447ae_55.png)

![](img/fb0e7f46d547648aaa046497e55447ae_57.png)

## 添加计分系统 📊

![](img/fb0e7f46d547648aaa046497e55447ae_59.png)

![](img/fb0e7f46d547648aaa046497e55447ae_60.png)

![](img/fb0e7f46d547648aaa046497e55447ae_62.png)

![](img/fb0e7f46d547648aaa046497e55447ae_64.png)

![](img/fb0e7f46d547648aaa046497e55447ae_66.png)

首先，我们为游戏添加一个计分系统。这能让玩家看到自己的进度，增加游戏的可玩性。

![](img/fb0e7f46d547648aaa046497e55447ae_68.png)

![](img/fb0e7f46d547648aaa046497e55447ae_70.png)

![](img/fb0e7f46d547648aaa046497e55447ae_72.png)

![](img/fb0e7f46d547648aaa046497e55447ae_74.png)

![](img/fb0e7f46d547648aaa046497e55447ae_75.png)

![](img/fb0e7f46d547648aaa046497e55447ae_77.png)

![](img/fb0e7f46d547648aaa046497e55447ae_79.png)

### 绘制数字功能

![](img/fb0e7f46d547648aaa046497e55447ae_81.png)

![](img/fb0e7f46d547648aaa046497e55447ae_83.png)

![](img/fb0e7f46d547648aaa046497e55447ae_85.png)

![](img/fb0e7f46d547648aaa046497e55447ae_87.png)

为了显示分数，我们需要一个能在屏幕上绘制数字的函数。由于我们还没有实现位图字体，这里先使用一个简单的“画线”方法来绘制数字。

![](img/fb0e7f46d547648aaa046497e55447ae_89.png)

![](img/fb0e7f46d547648aaa046497e55447ae_91.png)

![](img/fb0e7f46d547648aaa046497e55447ae_93.png)

![](img/fb0e7f46d547648aaa046497e55447ae_95.png)

![](img/fb0e7f46d547648aaa046497e55447ae_97.png)

![](img/fb0e7f46d547648aaa046497e55447ae_99.png)

![](img/fb0e7f46d547648aaa046497e55447ae_101.png)

以下是绘制数字的核心逻辑。我们遍历数字的每一位，根据数字值绘制对应的线段组合。

![](img/fb0e7f46d547648aaa046497e55447ae_102.png)

![](img/fb0e7f46d547648aaa046497e55447ae_104.png)

![](img/fb0e7f46d547648aaa046497e55447ae_106.png)

![](img/fb0e7f46d547648aaa046497e55447ae_108.png)

![](img/fb0e7f46d547648aaa046497e55447ae_109.png)

![](img/fb0e7f46d547648aaa046497e55447ae_111.png)

![](img/fb0e7f46d547648aaa046497e55447ae_113.png)

![](img/fb0e7f46d547648aaa046497e55447ae_115.png)

![](img/fb0e7f46d547648aaa046497e55447ae_117.png)

![](img/fb0e7f46d547648aaa046497e55447ae_119.png)

![](img/fb0e7f46d547648aaa046497e55447ae_121.png)

![](img/fb0e7f46d547648aaa046497e55447ae_123.png)

```c
void DrawNumber(int number, V2 position, float size, V4 color) {
    // 遍历数字的每一位
    int digit = number % 10;
    // 根据digit的值（0-9），调用DrawRect绘制对应的线段
    // 例如，数字0需要绘制一个矩形框
    if(digit == 0) {
        DrawRect(position, V2{size, size*2}, color); // 示例，实际需要更复杂的绘制
    }
    // ... 处理其他数字
    number /= 10; // 移动到下一位
}
```

![](img/fb0e7f46d547648aaa046497e55447ae_125.png)

![](img/fb0e7f46d547648aaa046497e55447ae_127.png)

![](img/fb0e7f46d547648aaa046497e55447ae_128.png)

![](img/fb0e7f46d547648aaa046497e55447ae_130.png)

![](img/fb0e7f46d547648aaa046497e55447ae_132.png)

![](img/fb0e7f46d547648aaa046497e55447ae_134.png)

![](img/fb0e7f46d547648aaa046497e55447ae_136.png)

![](img/fb0e7f46d547648aaa046497e55447ae_138.png)

![](img/fb0e7f46d547648aaa046497e55447ae_140.png)

![](img/fb0e7f46d547648aaa046497e55447ae_142.png)

我们在游戏循环中调用这个函数，在屏幕左上角显示当前分数。

![](img/fb0e7f46d547648aaa046497e55447ae_144.png)

![](img/fb0e7f46d547648aaa046497e55447ae_146.png)

![](img/fb0e7f46d547648aaa046497e55447ae_148.png)

![](img/fb0e7f46d547648aaa046497e55447ae_149.png)

![](img/fb0e7f46d547648aaa046497e55447ae_151.png)

![](img/fb0e7f46d547648aaa046497e55447ae_153.png)

```c
// 在渲染循环中
DrawNumber(game_state->score, V2{-arena_half_size_x + 15, arena_half_size_y - 15}, 5.0f, V4{1,1,1,1});
```

![](img/fb0e7f46d547648aaa046497e55447ae_155.png)

![](img/fb0e7f46d547648aaa046497e55447ae_157.png)

![](img/fb0e7f46d547648aaa046497e55447ae_159.png)

![](img/fb0e7f46d547648aaa046497e55447ae_161.png)

![](img/fb0e7f46d547648aaa046497e55447ae_163.png)

![](img/fb0e7f46d547648aaa046497e55447ae_165.png)

![](img/fb0e7f46d547648aaa046497e55447ae_167.png)

![](img/fb0e7f46d547648aaa046497e55447ae_169.png)

![](img/fb0e7f46d547648aaa046497e55447ae_171.png)

![](img/fb0e7f46d547648aaa046497e55447ae_173.png)

![](img/fb0e7f46d547648aaa046497e55447ae_175.png)

### 分数计算逻辑

![](img/fb0e7f46d547648aaa046497e55447ae_177.png)

![](img/fb0e7f46d547648aaa046497e55447ae_179.png)

![](img/fb0e7f46d547648aaa046497e55447ae_181.png)

![](img/fb0e7f46d547648aaa046497e55447ae_183.png)

![](img/fb0e7f46d547648aaa046497e55447ae_185.png)

![](img/fb0e7f46d547648aaa046497e55447ae_187.png)

![](img/fb0e7f46d547648aaa046497e55447ae_189.png)

![](img/fb0e7f46d547648aaa046497e55447ae_191.png)

接下来，我们需要确定何时增加分数。我们决定在方块被摧毁时增加分数。

![](img/fb0e7f46d547648aaa046497e55447ae_193.png)

![](img/fb0e7f46d547648aaa046497e55447ae_195.png)

![](img/fb0e7f46d547648aaa046497e55447ae_197.png)

![](img/fb0e7f46d547648aaa046497e55447ae_199.png)

![](img/fb0e7f46d547648aaa046497e55447ae_201.png)

![](img/fb0e7f46d547648aaa046497e55447ae_203.png)

![](img/fb0e7f46d547648aaa046497e55447ae_205.png)

![](img/fb0e7f46d547648aaa046497e55447ae_207.png)

![](img/fb0e7f46d547648aaa046497e55447ae_209.png)

![](img/fb0e7f46d547648aaa046497e55447ae_211.png)

在检测方块被摧毁的函数中，我们增加分数。为了增加策略性，分数会根据玩家剩余的生命值进行倍增：生命值越多，每个方块的基础分值越高。

![](img/fb0e7f46d547648aaa046497e55447ae_213.png)

![](img/fb0e7f46d547648aaa046497e55447ae_215.png)

![](img/fb0e7f46d547648aaa046497e55447ae_217.png)

![](img/fb0e7f46d547648aaa046497e55447ae_219.png)

![](img/fb0e7f46d547648aaa046497e55447ae_221.png)

![](img/fb0e7f46d547648aaa046497e55447ae_223.png)

![](img/fb0e7f46d547648aaa046497e55447ae_225.png)

![](img/fb0e7f46d547648aaa046497e55447ae_227.png)

![](img/fb0e7f46d547648aaa046497e55447ae_229.png)

```c
// 在TestForWinCondition函数中，当方块被摧毁时
game_state->score += 10 * game_state->lives; // 基础分乘以生命值
```

![](img/fb0e7f46d547648aaa046497e55447ae_231.png)

![](img/fb0e7f46d547648aaa046497e55447ae_233.png)

![](img/fb0e7f46d547648aaa046497e55447ae_235.png)

![](img/fb0e7f46d547648aaa046497e55447ae_237.png)

![](img/fb0e7f46d547648aaa046497e55447ae_239.png)

![](img/fb0e7f46d547648aaa046497e55447ae_241.png)

![](img/fb0e7f46d547648aaa046497e55447ae_243.png)

此外，我们还添加了一个连击奖励。如果玩家在不丢失球的情况下连续摧毁多个方块，会获得额外的分数加成。

![](img/fb0e7f46d547648aaa046497e55447ae_245.png)

![](img/fb0e7f46d547648aaa046497e55447ae_247.png)

![](img/fb0e7f46d547648aaa046497e55447ae_249.png)

![](img/fb0e7f46d547648aaa046497e55447ae_251.png)

![](img/fb0e7f46d547648aaa046497e55447ae_253.png)

![](img/fb0e7f46d547648aaa046497e55447ae_254.png)

![](img/fb0e7f46d547648aaa046497e55447ae_256.png)

![](img/fb0e7f46d547648aaa046497e55447ae_258.png)

![](img/fb0e7f46d547648aaa046497e55447ae_260.png)

```c
// 全局变量，记录上次摧毁方块的时间
static f32 last_block_destroyed_time = 0;
static int touchless_bonus = 0; // 无触球连击数

![](img/fb0e7f46d547648aaa046497e55447ae_262.png)

![](img/fb0e7f46d547648aaa046497e55447ae_264.png)

![](img/fb0e7f46d547648aaa046497e55447ae_266.png)

![](img/fb0e7f46d547648aaa046497e55447ae_268.png)

![](img/fb0e7f46d547648aaa046497e55447ae_270.png)

![](img/fb0e7f46d547648aaa046497e55447ae_272.png)

![](img/fb0e7f46d547648aaa046497e55447ae_274.png)

![](img/fb0e7f46d547648aaa046497e55447ae_276.png)

![](img/fb0e7f46d547648aaa046497e55447ae_278.png)

![](img/fb0e7f46d547648aaa046497e55447ae_280.png)

![](img/fb0e7f46d547648aaa046497e55447ae_281.png)

![](img/fb0e7f46d547648aaa046497e55447ae_283.png)

![](img/fb0e7f46d547648aaa046497e55447ae_285.png)

// 当球碰到玩家挡板时，重置连击
touchless_bonus = 0;

![](img/fb0e7f46d547648aaa046497e55447ae_287.png)

![](img/fb0e7f46d547648aaa046497e55447ae_289.png)

![](img/fb0e7f46d547648aaa046497e55447ae_291.png)

![](img/fb0e7f46d547648aaa046497e55447ae_293.png)

![](img/fb0e7f46d547648aaa046497e55447ae_295.png)

![](img/fb0e7f46d547648aaa046497e55447ae_297.png)

![](img/fb0e7f46d547648aaa046497e55447ae_299.png)

![](img/fb0e7f46d547648aaa046497e55447ae_301.png)

![](img/fb0e7f46d547648aaa046497e55447ae_303.png)

// 当摧毁一个方块时
touchless_bonus++;
game_state->score += touchless_bonus * 5; // 连击奖励
last_block_destroyed_time = game_state->current_time;
```

![](img/fb0e7f46d547648aaa046497e55447ae_305.png)

![](img/fb0e7f46d547648aaa046497e55447ae_307.png)

![](img/fb0e7f46d547648aaa046497e55447ae_309.png)

![](img/fb0e7f46d547648aaa046497e55447ae_311.png)

![](img/fb0e7f46d547648aaa046497e55447ae_313.png)

![](img/fb0e7f46d547648aaa046497e55447ae_315.png)

---

![](img/fb0e7f46d547648aaa046497e55447ae_317.png)

![](img/fb0e7f46d547648aaa046497e55447ae_318.png)

![](img/fb0e7f46d547648aaa046497e55447ae_320.png)

![](img/fb0e7f46d547648aaa046497e55447ae_322.png)

![](img/fb0e7f46d547648aaa046497e55447ae_324.png)

![](img/fb0e7f46d547648aaa046497e55447ae_326.png)

![](img/fb0e7f46d547648aaa046497e55447ae_328.png)

![](img/fb0e7f46d547648aaa046497e55447ae_330.png)

## 修复鼠标控制与能量道具 🖱️

![](img/fb0e7f46d547648aaa046497e55447ae_332.png)

上一节我们尝试实现“反向控制”和“慢速移动”能量道具时遇到了问题，原因是直接使用鼠标绝对位置存在边界限制。本节我们将采用更稳健的方法。

![](img/fb0e7f46d547648aaa046497e55447ae_334.png)

![](img/fb0e7f46d547648aaa046497e55447ae_336.png)

### 锁定鼠标到屏幕中心

![](img/fb0e7f46d547648aaa046497e55447ae_338.png)

![](img/fb0e7f46d547648aaa046497e55447ae_340.png)

解决方案是将鼠标锁定在游戏窗口中心，然后只读取鼠标的移动增量（Delta）。这样无论鼠标如何移动，我们都能获得精确的相对位移，解决了屏幕边界的问题。

![](img/fb0e7f46d547648aaa046497e55447ae_342.png)

![](img/fb0e7f46d547648aaa046497e55447ae_344.png)

![](img/fb0e7f46d547648aaa046497e55447ae_346.png)

![](img/fb0e7f46d547648aaa046497e55447ae_348.png)

![](img/fb0e7f46d547648aaa046497e55447ae_349.png)

![](img/fb0e7f46d547648aaa046497e55447ae_351.png)

![](img/fb0e7f46d547648aaa046497e55447ae_353.png)

![](img/fb0e7f46d547648aaa046497e55447ae_355.png)

![](img/fb0e7f46d547648aaa046497e55447ae_357.png)

![](img/fb0e7f46d547648aaa046497e55447ae_359.png)

以下是实现的核心步骤：

![](img/fb0e7f46d547648aaa046497e55447ae_361.png)

![](img/fb0e7f46d547648aaa046497e55447ae_363.png)

![](img/fb0e7f46d547648aaa046497e55447ae_365.png)

![](img/fb0e7f46d547648aaa046497e55447ae_367.png)

![](img/fb0e7f46d547648aaa046497e55447ae_369.png)

![](img/fb0e7f46d547648aaa046497e55447ae_371.png)

![](img/fb0e7f46d547648aaa046497e55447ae_373.png)

1.  获取屏幕中心坐标。
2.  在每一帧开始时，将鼠标设置到屏幕中心。
3.  计算当前帧鼠标位置与中心点的差值，作为移动增量。
4.  使用这个增量来控制玩家挡板。

![](img/fb0e7f46d547648aaa046497e55447ae_375.png)

![](img/fb0e7f46d547648aaa046497e55447ae_377.png)

```c
// 在平台层代码中（例如Windows）
POINT center_screen;
center_screen.x = screen_size.x / 2;
center_screen.y = screen_size.y / 2;
SetCursorPos(center_screen.x, center_screen.y); // 将鼠标设置到中心

![](img/fb0e7f46d547648aaa046497e55447ae_379.png)

![](img/fb0e7f46d547648aaa046497e55447ae_381.png)

![](img/fb0e7f46d547648aaa046497e55447ae_383.png)

// 获取鼠标当前位置（此时应在中心附近）
POINT current_mouse_pos;
GetCursorPos(¤t_mouse_pos);

![](img/fb0e7f46d547648aaa046497e55447ae_385.png)

// 计算增量
mouse_delta.x = (f32)(current_mouse_pos.x - center_screen.x);
mouse_delta.y = (f32)(current_mouse_pos.y - center_screen.y);
```

![](img/fb0e7f46d547648aaa046497e55447ae_387.png)

### 完善能量道具

![](img/fb0e7f46d547648aaa046497e55447ae_389.png)

![](img/fb0e7f46d547648aaa046497e55447ae_391.png)

![](img/fb0e7f46d547648aaa046497e55447ae_393.png)

修复鼠标控制后，之前未完成的能量道具现在可以正常工作了。

![](img/fb0e7f46d547648aaa046497e55447ae_395.png)

![](img/fb0e7f46d547648aaa046497e55447ae_397.png)

![](img/fb0e7f46d547648aaa046497e55447ae_399.png)

![](img/fb0e7f46d547648aaa046497e55447ae_401.png)

*   **慢速玩家 (Slow Player)**：当触发时，降低玩家挡板的移动速度乘数。
    ```c
    if(slow_player_timer > 0) {
        speed_multiplier = 0.5f; // 速度减半
        slow_player_timer -= dt;
    }
    ```
*   **反向控制 (Inverted Controls)**：当触发时，将鼠标移动增量取反。
    ```c
    if(inverted_controls_timer > 0) {
        mouse_delta.x = -mouse_delta.x;
        inverted_controls_timer -= dt;
    }
    ```

![](img/fb0e7f46d547648aaa046497e55447ae_403.png)

![](img/fb0e7f46d547648aaa046497e55447ae_405.png)

![](img/fb0e7f46d547648aaa046497e55447ae_407.png)

![](img/fb0e7f46d547648aaa046497e55447ae_409.png)

![](img/fb0e7f46d547648aaa046497e55447ae_411.png)

![](img/fb0e7f46d547648aaa046497e55447ae_413.png)

![](img/fb0e7f46d547648aaa046497e55447ae_415.png)

![](img/fb0e7f46d547648aaa046497e55447ae_417.png)

![](img/fb0e7f46d547648aaa046497e55447ae_419.png)

现在，所有能量道具（包括瞬间击杀、坚固方块等）都已完全实现并可以正常交互。

![](img/fb0e7f46d547648aaa046497e55447ae_421.png)

![](img/fb0e7f46d547648aaa046497e55447ae_423.png)

![](img/fb0e7f46d547648aaa046497e55447ae_425.png)

![](img/fb0e7f46d547648aaa046497e55447ae_427.png)

![](img/fb0e7f46d547648aaa046497e55447ae_429.png)

![](img/fb0e7f46d547648aaa046497e55447ae_431.png)

![](img/fb0e7f46d547648aaa046497e55447ae_433.png)

![](img/fb0e7f46d547648aaa046497e55447ae_435.png)

---

![](img/fb0e7f46d547648aaa046497e55447ae_437.png)

![](img/fb0e7f46d547648aaa046497e55447ae_439.png)

![](img/fb0e7f46d547648aaa046497e55447ae_441.png)

![](img/fb0e7f46d547648aaa046497e55447ae_443.png)

![](img/fb0e7f46d547648aaa046497e55447ae_445.png)

![](img/fb0e7f46d547648aaa046497e55447ae_447.png)

![](img/fb0e7f46d547648aaa046497e55447ae_449.png)

![](img/fb0e7f46d547648aaa046497e55447ae_451.png)

![](img/fb0e7f46d547648aaa046497e55447ae_453.png)

![](img/fb0e7f46d547648aaa046497e55447ae_455.png)

## 调试与修复游戏性问题 🔧

![](img/fb0e7f46d547648aaa046497e55447ae_457.png)

在开发过程中，我们积累了一些需要修复的bug和需要改进的体验点。

![](img/fb0e7f46d547648aaa046497e55447ae_459.png)

![](img/fb0e7f46d547648aaa046497e55447ae_461.png)

![](img/fb0e7f46d547648aaa046497e55447ae_463.png)

![](img/fb0e7f46d547648aaa046497e55447ae_465.png)

![](img/fb0e7f46d547648aaa046497e55447ae_467.png)

![](img/fb0e7f46d547648aaa046497e55447ae_468.png)

### 修复碰撞反弹逻辑

![](img/fb0e7f46d547648aaa046497e55447ae_470.png)

![](img/fb0e7f46d547648aaa046497e55447ae_472.png)

![](img/fb0e7f46d547648aaa046497e55447ae_474.png)

![](img/fb0e7f46d547648aaa046497e55447ae_476.png)

![](img/fb0e7f46d547648aaa046497e55447ae_478.png)

我们发现球与方块发生X轴方向碰撞时，球的Y轴速度也被重置了，这导致球的轨迹变得不可预测且不自然。我们移除了这行多余的代码，让碰撞反弹更符合物理直觉。

![](img/fb0e7f46d547648aaa046497e55447ae_480.png)

![](img/fb0e7f46d547648aaa046497e55447ae_482.png)

![](img/fb0e7f46d547648aaa046497e55447ae_484.png)

修改前：
```c
// 在DoBallBlockCollision函数中
if(collision_on_x) {
    ball->dP.y = -ball->dP.y; // 不必要的Y轴反转
}
```
修改后：
```c
if(collision_on_x) {
    // 仅处理X轴反转，Y轴速度保持不变
    ball->dP.x = -ball->dP.x;
}
```

![](img/fb0e7f46d547648aaa046497e55447ae_486.png)

![](img/fb0e7f46d547648aaa046497e55447ae_488.png)

![](img/fb0e7f46d547648aaa046497e55447ae_490.png)

![](img/fb0e7f46d547648aaa046497e55447ae_492.png)

![](img/fb0e7f46d547648aaa046497e55447ae_494.png)

![](img/fb0e7f46d547648aaa046497e55447ae_496.png)

![](img/fb0e7f46d547648aaa046497e55447ae_497.png)

![](img/fb0e7f46d547648aaa046497e55447ae_499.png)

![](img/fb0e7f46d547648aaa046497e55447ae_501.png)

![](img/fb0e7f46d547648aaa046497e55447ae_503.png)

![](img/fb0e7f46d547648aaa046497e55447ae_505.png)

![](img/fb0e7f46d547648aaa046497e55447ae_507.png)

### 改进双球关卡设计

![](img/fb0e7f46d547648aaa046497e55447ae_509.png)

![](img/fb0e7f46d547648aaa046497e55447ae_511.png)

![](img/fb0e7f46d547648aaa046497e55447ae_513.png)

![](img/fb0e7f46d547648aaa046497e55447ae_515.png)

我们之前设计了一个双球关卡，两个球被标记为不同的“队伍”，玩家需要接住对应颜色的球。但实现后发现节奏难以控制，体验不佳。

![](img/fb0e7f46d547648aaa046497e55447ae_517.png)

![](img/fb0e7f46d547648aaa046497e55447ae_519.png)

![](img/fb0e7f46d547648aaa046497e55447ae_521.png)

![](img/fb0e7f46d547648aaa046497e55447ae_523.png)

![](img/fb0e7f46d547648aaa046497e55447ae_525.png)

![](img/fb0e7f46d547648aaa046497e55447ae_526.png)

![](img/fb0e7f46d547648aaa046497e55447ae_528.png)

![](img/fb0e7f46d547648aaa046497e55447ae_530.png)

我们尝试了一种方案：让每个球在向下运动时，根据其当前位置动态调整速度，确保它们总是间隔固定时间到达玩家区域。虽然数学上可行，但在实际游玩中仍然显得混乱且困难。

![](img/fb0e7f46d547648aaa046497e55447ae_532.png)

![](img/fb0e7f46d547648aaa046497e55447ae_534.png)

![](img/fb0e7f46d547648aaa046497e55447ae_535.png)

![](img/fb0e7f46d547648aaa046497e55447ae_537.png)

![](img/fb0e7f46d547648aaa046497e55447ae_539.png)

![](img/fb0e7f46d547648aaa046497e55447ae_541.png)

![](img/fb0e7f46d547648aaa046497e55447ae_543.png)

![](img/fb0e7f46d547648aaa046497e55447ae_545.png)

![](img/fb0e7f46d547648aaa046497e55447ae_547.png)

![](img/fb0e7f46d547648aaa046497e55447ae_549.png)

![](img/fb0e7f46d547648aaa046497e55447ae_551.png)

![](img/fb0e7f46d547648aaa046497e55447ae_553.png)

经过评估，我们认为这个机制目前对核心游戏体验的贡献有限，且调试成本较高。因此，我们决定**暂时注释掉这个双球关卡**，将精力集中在优化其他更成熟的游戏模式上。未来如果有了更好的设计思路，可以再重新引入。

### 完善墙体生成

![](img/fb0e7f46d547648aaa046497e55447ae_555.png)

![](img/fb0e7f46d547648aaa046497e55447ae_557.png)

![](img/fb0e7f46d547648aaa046497e55447ae_559.png)

![](img/fb0e7f46d547648aaa046497e55447ae_561.png)

![](img/fb0e7f46d547648aaa046497e55447ae_563.png)

![](img/fb0e7f46d547648aaa046497e55447ae_565.png)

![](img/fb0e7f46d547648aaa046497e55447ae_567.png)

![](img/fb0e7f46d547648aaa046497e55447ae_568.png)

为了让砖墙的排列更美观、更像经典的“墙”的形状，我们调整了生成算法。对于每一行，我们让两端的砖块尺寸减半，并适当调整位置，使得墙的轮廓更加平整。

![](img/fb0e7f46d547648aaa046497e55447ae_570.png)

![](img/fb0e7f46d547648aaa046497e55447ae_572.png)

![](img/fb0e7f46d547648aaa046497e55447ae_574.png)

![](img/fb0e7f46d547648aaa046497e55447ae_576.png)

![](img/fb0e7f46d547648aaa046497e55447ae_578.png)

![](img/fb0e7f46d547648aaa046497e55447ae_580.png)

![](img/fb0e7f46d547648aaa046497e55447ae_582.png)

![](img/fb0e7f46d547648aaa046497e55447ae_584.png)

![](img/fb0e7f46d547648aaa046497e55447ae_586.png)

![](img/fb0e7f46d547648aaa046497e55447ae_588.png)

![](img/fb0e7f46d547648aaa046497e55447ae_590.png)

![](img/fb0e7f46d547648aaa046497e55447ae_592.png)

核心修改是在创建砖块的循环中，对首尾砖块进行特殊处理：
```c
V2 block_half_size = {1.5f, 0.75f};
V2 block_relative_p = {0, 0};

![](img/fb0e7f46d547648aaa046497e55447ae_594.png)

![](img/fb0e7f46d547648aaa046497e55447ae_596.png)

![](img/fb0e7f46d547648aaa046497e55447ae_598.png)

![](img/fb0e7f46d547648aaa046497e55447ae_600.png)

![](img/fb0e7f46d547648aaa046497e55447ae_602.png)

![](img/fb0e7f46d547648aaa046497e55447ae_604.png)

![](img/fb0e7f46d547648aaa046497e55447ae_606.png)

// 计算砖块位置
block_relative_p.x = (-num_blocks_x / 2.0f + x) * (block_half_size.x * 2 + spacing) + block_half_size.x;

![](img/fb0e7f46d547648aaa046497e55447ae_608.png)

![](img/fb0e7f46d547648aaa046497e55447ae_610.png)

![](img/fb0e7f46d547648aaa046497e55447ae_611.png)

![](img/fb0e7f46d547648aaa046497e55447ae_613.png)

![](img/fb0e7f46d547648aaa046497e55447ae_615.png)

![](img/fb0e7f46d547648aaa046497e55447ae_617.png)

![](img/fb0e7f46d547648aaa046497e55447ae_619.png)

![](img/fb0e7f46d547648aaa046497e55447ae_620.png)

![](img/fb0e7f46d547648aaa046497e55447ae_622.png)

![](img/fb0e7f46d547648aaa046497e55447ae_623.png)

![](img/fb0e7f46d547648aaa046497e55447ae_625.png)

![](img/fb0e7f46d547648aaa046497e55447ae_627.png)

![](img/fb0e7f46d547648aaa046497e55447ae_629.png)

![](img/fb0e7f46d547648aaa046497e55447ae_631.png)

// 如果是第一行，并且是第一个或最后一个砖块
if(y == 0 && (x == 0 || x == num_blocks_x - 1)) {
    block_half_size.x *= 0.5f; // 宽度减半
    if(x == 0) {
        block_relative_p.x += block_half_size.x; // 右移半个身位
    } else {
        block_relative_p.x -= block_half_size.x; // 左移半个身位
    }
}
```

![](img/fb0e7f46d547648aaa046497e55447ae_633.png)

### 添加简易调试信息打印系统

![](img/fb0e7f46d547648aaa046497e55447ae_635.png)

![](img/fb0e7f46d547648aaa046497e55447ae_637.png)

![](img/fb0e7f46d547648aaa046497e55447ae_639.png)

![](img/fb0e7f46d547648aaa046497e55447ae_641.png)

![](img/fb0e7f46d547648aaa046497e55447ae_643.png)

![](img/fb0e7f46d547648aaa046497e55447ae_645.png)

![](img/fb0e7f46d547648aaa046497e55447ae_647.png)

![](img/fb0e7f46d547648aaa046497e55447ae_649.png)

![](img/fb0e7f46d547648aaa046497e55447ae_651.png)

![](img/fb0e7f46d547648aaa046497e55447ae_653.png)

为了便于后续开发和调试，我们实现了一个非常简单的屏幕信息打印系统。它使用一个环形缓冲区存储消息，并在屏幕上绘制出来。

![](img/fb0e7f46d547648aaa046497e55447ae_655.png)

![](img/fb0e7f46d547648aaa046497e55447ae_657.png)

![](img/fb0e7f46d547648aaa046497e55447ae_659.png)

![](img/fb0e7f46d547648aaa046497e55447ae_661.png)

![](img/fb0e7f46d547648aaa046497e55447ae_663.png)

![](img/fb0e7f46d547648aaa046497e55447ae_665.png)

![](img/fb0e7f46d547648aaa046497e55447ae_667.png)

```c
#define MAX_MESSAGES 32
struct Message {
    int value;
    f32 timer;
    V4 color;
};
Message messages[MAX_MESSAGES];
int current_message = 0;

![](img/fb0e7f46d547648aaa046497e55447ae_669.png)

![](img/fb0e7f46d547648aaa046497e55447ae_671.png)

![](img/fb0e7f46d547648aaa046497e55447ae_673.png)

![](img/fb0e7f46d547648aaa046497e55447ae_675.png)

![](img/fb0e7f46d547648aaa046497e55447ae_677.png)

![](img/fb0e7f46d547648aaa046497e55447ae_679.png)

![](img/fb0e7f46d547648aaa046497e55447ae_681.png)

![](img/fb0e7f46d547648aaa046497e55447ae_683.png)

![](img/fb0e7f46d547648aaa046497e55447ae_685.png)

void PrintInt(int value, V4 color) {
    Message* msg = &messages[current_message];
    msg->value = value;
    msg->color = color;
    msg->timer = 2.0f; // 显示2秒
    current_message = (current_message + 1) % MAX_MESSAGES;
}

![](img/fb0e7f46d547648aaa046497e55447ae_687.png)

![](img/fb0e7f46d547648aaa046497e55447ae_689.png)

![](img/fb0e7f46d547648aaa046497e55447ae_691.png)

![](img/fb0e7f46d547648aaa046497e55447ae_693.png)

![](img/fb0e7f46d547648aaa046497e55447ae_695.png)

![](img/fb0e7f46d547648aaa046497e55447ae_697.png)

![](img/fb0e7f46d547648aaa046497e55447ae_699.png)

![](img/fb0e7f46d547648aaa046497e55447ae_701.png)

![](img/fb0e7f46d547648aaa046497e55447ae_703.png)

![](img/fb0e7f46d547648aaa046497e55447ae_704.png)

![](img/fb0e7f46d547648aaa046497e55447ae_706.png)

![](img/fb0e7f46d547648aaa046497e55447ae_708.png)

![](img/fb0e7f46d547648aaa046497e55447ae_710.png)

// 在渲染循环中绘制所有活跃的消息
for(int i = 0; i < MAX_MESSAGES; ++i) {
    if(messages[i].timer > 0) {
        DrawNumber(messages[i].value, some_position, 2.5f, messages[i].color);
        messages[i].timer -= dt;
    }
}
```
这个系统目前只能打印整数，但足以帮助我们实时监控游戏状态（如球的速度）。

![](img/fb0e7f46d547648aaa046497e55447ae_712.png)

![](img/fb0e7f46d547648aaa046497e55447ae_714.png)

![](img/fb0e7f46d547648aaa046497e55447ae_716.png)

![](img/fb0e7f46d547648aaa046497e55447ae_718.png)

![](img/fb0e7f46d547648aaa046497e55447ae_720.png)

![](img/fb0e7f46d547648aaa046497e55447ae_722.png)

![](img/fb0e7f46d547648aaa046497e55447ae_724.png)

![](img/fb0e7f46d547648aaa046497e55447ae_726.png)

![](img/fb0e7f46d547648aaa046497e55447ae_728.png)

---

![](img/fb0e7f46d547648aaa046497e55447ae_730.png)

![](img/fb0e7f46d547648aaa046497e55447ae_732.png)

## 当前游戏状态总结 🏁

![](img/fb0e7f46d547648aaa046497e55447ae_734.png)

![](img/fb0e7f46d547648aaa046497e55447ae_736.png)

![](img/fb0e7f46d547648aaa046497e55447ae_738.png)

![](img/fb0e7f46d547648aaa046497e55447ae_740.png)

本节课中我们一起学习了如何进行游戏调试与体验优化。我们完成了以下工作：

![](img/fb0e7f46d547648aaa046497e55447ae_742.png)

![](img/fb0e7f46d547648aaa046497e55447ae_744.png)

![](img/fb0e7f46d547648aaa046497e55447ae_745.png)

![](img/fb0e7f46d547648aaa046497e55447ae_747.png)

![](img/fb0e7f46d547648aaa046497e55447ae_749.png)

![](img/fb0e7f46d547648aaa046497e55447ae_751.png)

![](img/fb0e7f46d547648aaa046497e55447ae_753.png)

![](img/fb0e7f46d547648aaa046497e55447ae_755.png)

![](img/fb0e7f46d547648aaa046497e55447ae_757.png)

![](img/fb0e7f46d547648aaa046497e55447ae_759.png)

1.  **添加了计分系统**：实现了数字绘制功能，引入了基础分、生命值乘数和连击奖励机制。
2.  **彻底修复了鼠标控制**：通过将鼠标锁定到屏幕中心并读取增量，完美支持了“反向控制”和“慢速移动”能量道具。
3.  **完成了所有能量道具**：包括瞬间击杀、坚固方块、反向控制、慢速玩家等，现在都能按预期工作。
4.  **修复了关键bug**：修正了球与方块碰撞时不合理的Y轴速度重置，改善了游戏手感。
5.  **优化了游戏内容**：暂时移除了体验不佳的双球关卡，优化了砖墙的视觉排列，使其更整齐。
6.  **引入了调试工具**：创建了一个简单的屏幕信息打印系统，为后续开发提供便利。

![](img/fb0e7f46d547648aaa046497e55447ae_761.png)

![](img/fb0e7f46d547648aaa046497e55447ae_763.png)

![](img/fb0e7f46d547648aaa046497e55447ae_765.png)

![](img/fb0e7f46d547648aaa046497e55447ae_767.png)

![](img/fb0e7f46d547648aaa046497e55447ae_769.png)

![](img/fb0e7f46d547648aaa046497e55447ae_771.png)

![](img/fb0e7f46d547648aaa046497e55447ae_773.png)

![](img/fb0e7f46d547648aaa046497e55447ae_775.png)

![](img/fb0e7f46d547648aaa046497e55447ae_777.png)

![](img/fb0e7f46d547648aaa046497e55447ae_779.png)

现在，我们的游戏包含了多个可玩的模式：
*   **基础 breakout 模式**：带有各种能量道具的经典打砖块。
*   **Pong 模式**：在 breakout 场景中与AI进行乒乓球对战。
*   **太空侵略者模式**：击败会移动的方块阵列。

![](img/fb0e7f46d547648aaa046497e55447ae_781.png)

![](img/fb0e7f46d547648aaa046497e55447ae_783.png)

![](img/fb0e7f46d547648aaa046497e55447ae_785.png)

游戏的初步玩法框架已经变得完整且有趣。在接下来的课程中，我们将进入“游戏感觉（Game Feel）”优化阶段，为游戏添加动画、粒子效果、音效等，让体验更加生动和富有冲击力。