# 013：主菜单、存档系统与音频改进 🎮

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_1.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_3.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_5.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_7.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_9.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_11.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_12.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_14.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_16.png)

在本节课中，我们将学习如何为我们的C语言游戏添加主菜单、一个完整的存档系统以及改进音频功能。我们将修复一些已知的Bug，并实现音乐、音效的播放与控制，让游戏体验更加完整和流畅。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_18.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_20.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_22.png)

---

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_24.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_26.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_28.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_30.png)

## 概述

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_32.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_34.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_36.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_38.png)

上一节我们完成了游戏引擎的核心渲染与粒子系统改进。本节中，我们将重点实现游戏的“上层建筑”：一个可交互的主菜单，用于保存和加载游戏进度与高分的存档系统，以及一套完整的音频管理系统，包括背景音乐和多种音效。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_40.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_42.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_44.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_45.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_47.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_49.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_51.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_53.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_55.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_57.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_59.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_61.png)

---

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_63.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_65.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_67.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_69.png)

## 修复已知Bug 🐛

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_71.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_73.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_75.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_77.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_79.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_81.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_83.png)

在开始新功能之前，我们首先修复了几个在测试中发现的游戏Bug，以确保代码的稳定性。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_85.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_87.png)

### 修复方块生命值Bug

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_89.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_91.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_93.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_95.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_97.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_99.png)

在之前的版本中，当一个方块被两个球在同一帧击中时，其生命值可能会被错误地减到负数，导致逻辑错误。我们通过添加断言和优化碰撞检测后的返回逻辑来修复此问题。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_101.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_103.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_105.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_107.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_109.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_111.png)

**核心代码修改：**
```c
// 在方块碰撞检测函数中
if (block_life > 0) {
    block_life--;
    if (block_life <= 0) {
        // 标记方块被摧毁
        was_destroyed = true;
        // 提前退出循环，避免同一帧内多次处理
        break;
    }
} else {
    // 断言，如果生命值已为0或负数，则不应进入此逻辑
    assert(block_life > 0);
}
```

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_113.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_114.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_116.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_118.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_120.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_122.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_124.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_126.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_128.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_130.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_131.png)

### 修复渲染器崩溃Bug

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_133.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_135.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_137.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_139.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_141.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_143.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_145.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_147.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_149.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_151.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_153.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_154.png)

在旋转矩形的渲染代码中，存在一个关于宽度和高度变量的拼写错误，这可能导致数组越界和程序崩溃。我们修正了变量名并添加了适当的边界检查。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_156.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_158.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_160.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_162.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_164.png)

**核心代码修改：**
```c
// 修正前
x_clamped = clamp(x, 0, bitmap->width);
width_clamped = clamp(width, 0, bitmap->height); // 错误：使用了 height

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_166.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_167.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_169.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_171.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_172.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_174.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_175.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_177.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_179.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_181.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_183.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_185.png)

// 修正后
x_clamped = clamp(x, 0, bitmap->width);
width_clamped = clamp(width, 0, bitmap->width); // 正确：使用 width
```

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_187.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_189.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_191.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_193.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_195.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_197.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_199.png)

### 添加开发模式暂停功能

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_201.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_203.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_205.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_206.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_208.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_210.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_212.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_214.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_216.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_218.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_220.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_222.png)

为了方便调试，我们添加了一个开发专用的暂停功能。按下F1键可以暂停/继续游戏模拟，并自动解锁/锁定鼠标光标。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_224.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_226.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_228.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_230.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_232.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_234.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_236.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_238.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_240.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_242.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_244.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_245.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_247.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_249.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_251.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_253.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_255.png)

**核心代码实现：**
```c
// 在输入处理部分
if (is_pressed(KEY_F1)) {
    game_state->is_paused = !game_state->is_paused;
    game_state->is_mouse_locked = !game_state->is_paused; // 暂停时解锁鼠标
}
// 在游戏更新循环中
if (!game_state->is_paused) {
    simulate_game(dt);
}
```

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_257.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_259.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_261.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_262.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_264.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_266.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_268.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_270.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_272.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_274.png)

---

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_276.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_277.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_279.png)

## 实现主菜单 🖥️

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_281.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_283.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_285.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_287.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_289.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_291.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_293.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_295.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_297.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_299.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_301.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_303.png)

接下来，我们为游戏创建了一个主菜单界面。玩家可以使用鼠标或键盘（通过控制挡板）在菜单中导航并选择关卡。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_305.png)

### 菜单状态与绘制

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_307.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_309.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_311.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_313.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_315.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_317.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_319.png)

我们引入了`game_mode`状态变量来区分菜单状态和游戏状态。在菜单模式下，我们绘制一个简单的关卡列表。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_321.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_323.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_325.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_327.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_329.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_331.png)

**核心概念：**
- **游戏状态 (`game_mode`)**：一个枚举或整数，标识当前是处于`GAME_MODE_MENU`还是`GAME_MODE_PLAY`。
- **关卡选择**：根据玩家控制的“光标”（即游戏中的挡板）在屏幕上的水平位置，计算当前“悬停”在哪个关卡数字上。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_333.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_335.png)

**绘制关卡列表代码逻辑：**
```c
// 计算每个关卡选项的Y轴位置
float first_y = -60.0f;
float delta_y = 120.0f / (level_count + 1);
for (int i = 0; i < level_count; ++i) {
    float y_pos = first_y + (i * delta_y);
    // 根据关卡是否解锁决定颜色
    u32 color = level_saves[i].is_unlocked ? COLOR_WHITE : COLOR_DARK_GRAY;
    draw_number(i+1, vec2(0, y_pos), 5.0f, color);
}
```

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_337.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_339.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_341.png)

### 菜单交互逻辑

玩家通过移动挡板（在菜单中作为光标）来选择关卡。当光标移动到某个关卡数字上并按下鼠标左键或特定按键时，游戏将切换到对应的关卡。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_343.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_345.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_347.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_349.png)

**计算悬停关卡的公式：**
```c
// player_pos_x 是挡板的X坐标
// first_x 是第一个关卡选项的X坐标
// delta_x 是每个选项之间的间隔
int hot_level = (int)((player_pos_x - first_x) / delta_x);
// 确保 hot_level 在有效范围内 [0, level_count-1]
hot_level = clamp(hot_level, 0, level_count - 1);
```

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_351.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_353.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_355.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_357.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_359.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_361.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_363.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_365.png)

---

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_367.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_369.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_371.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_373.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_375.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_377.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_379.png)

## 实现存档系统 💾

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_381.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_383.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_384.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_386.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_388.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_390.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_391.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_393.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_395.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_397.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_399.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_401.png)

存档系统是游戏的重要组成部分，它允许我们保存玩家的进度（已解锁的关卡）和每个关卡的最高分。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_403.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_405.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_407.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_408.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_410.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_411.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_413.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_415.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_417.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_419.png)

### 存档数据结构

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_421.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_423.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_425.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_427.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_429.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_431.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_433.png)

我们定义了一个结构体来保存每个关卡的信息，并创建了一个数组来管理所有关卡的存档。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_435.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_437.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_439.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_441.png)

**数据结构定义：**
```c
typedef struct {
    b32 is_unlocked;    // 关卡是否已解锁
    s32 high_score;     // 该关卡的最高分
} Level_Save;

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_443.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_445.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_447.png)

Level_Save level_saves[MAX_LEVELS]; // 全局存档数组
```

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_449.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_451.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_453.png)

### 存档的加载与保存

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_455.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_457.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_458.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_460.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_462.png)

我们实现了两个核心函数：`save_game` 和 `load_game`。它们负责将 `level_saves` 数组写入硬盘文件，以及从文件中读取数据并加载回内存。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_464.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_466.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_468.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_470.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_472.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_474.png)

**存档流程：**
1.  **游戏启动时 (`initialize_game`)**：调用 `load_game`。如果存档文件存在，则读取数据；如果不存在，则初始化一个默认存档（通常只有第一关解锁）。
2.  **游戏过程中**：
    *   当玩家成功通过一个关卡时，解锁下一关。
    *   当玩家获得新的高分时，更新对应关卡的 `high_score`。
    *   在这些关键节点，调用 `save_game` 将最新状态写入文件。
3.  **游戏退出时**：也可以选择调用 `save_game` 进行最终保存。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_475.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_477.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_479.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_481.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_483.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_485.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_487.png)

**文件操作核心代码（Windows平台示例）：**
```c
b32 save_game() {
    Save_Data data;
    data.version = SAVE_FILE_VERSION;
    data.level_count = MAX_LEVELS;
    memcpy(data.levels, level_saves, sizeof(level_saves));

    // 调用平台层函数写入文件
    return platform_write_save_file("data/save.dat", &data, sizeof(data));
}

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_489.png)

b32 load_game() {
    Save_Data data;
    if (platform_read_save_file("data/save.dat", &data, sizeof(data))) {
        if (data.version == SAVE_FILE_VERSION && data.level_count == MAX_LEVELS) {
            memcpy(level_saves, data.levels, sizeof(level_saves));
            return true;
        }
    }
    // 加载失败，初始化默认存档
    initialize_default_saves();
    return false;
}
```

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_491.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_493.png)

---

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_495.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_497.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_499.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_501.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_503.png)

## 改进音频系统 🔊

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_505.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_507.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_509.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_511.png)

我们极大地丰富了游戏的音频体验，添加了背景音乐、多种音效并改进了音频混合逻辑。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_513.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_515.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_517.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_519.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_521.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_523.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_524.png)

### 音乐管理与切换

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_526.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_528.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_530.png)

我们加载了两段音乐：主菜单音乐和游戏进行音乐。根据 `game_mode` 的切换，平滑地淡入淡出对应的音乐。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_532.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_534.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_536.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_538.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_540.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_542.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_543.png)

**音乐状态控制：**
```c
// 切换到游戏模式时
set_target_volume(&menu_music, 0.0f); // 菜单音乐淡出
set_target_volume(&gameplay_music, 1.0f); // 游戏音乐淡入
start_game();

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_545.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_547.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_549.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_551.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_553.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_554.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_556.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_558.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_560.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_561.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_563.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_565.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_567.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_569.png)

// 切换回菜单模式时
set_target_volume(&gameplay_music, 0.0f);
set_target_volume(&menu_music, 1.0f);
```

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_571.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_573.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_575.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_576.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_578.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_580.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_582.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_584.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_586.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_588.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_590.png)

### 音效播放

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_592.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_594.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_596.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_598.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_600.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_602.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_604.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_606.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_607.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_608.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_610.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_612.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_613.png)

我们为游戏事件添加了多种音效，例如方块被击中、砖块被摧毁、玩家获得无敌状态等。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_615.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_617.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_618.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_620.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_622.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_624.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_626.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_628.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_630.png)

**音效池管理：**
为了避免同时播放过多音效导致内存或性能问题，我们实现了一个简单的音效池。音效被添加到播放队列中，由音频混合器按顺序播放。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_632.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_634.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_636.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_638.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_640.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_642.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_644.png)

**播放音效的示例：**
```c
// 当方块被摧毁时
if (block_destroyed) {
    int sound_index = rand_int(0, BRICK_SOUND_COUNT - 1);
    play_sound(&brick_sounds[sound_index]);
}

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_646.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_648.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_650.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_651.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_652.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_654.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_656.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_657.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_659.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_661.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_663.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_665.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_667.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_669.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_671.png)

// 当球击中挡板时
if (ball_hit_paddle) {
    // 使用循环播放的一组音效，产生有节奏的连续击打声
    play_sound(&hit_sounds[next_hit_sound_index]);
    next_hit_sound_index = (next_hit_sound_index + 1) % HIT_SOUND_COUNT;
}
```

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_673.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_675.png)

### 动态音频生成：玩家移动音效

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_677.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_679.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_681.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_683.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_685.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_687.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_689.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_691.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_693.png)

我们实现了一个动态生成的音效，用于反馈玩家的移动。挡板移动越快，产生的音调越高，音量也越大。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_695.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_697.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_699.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_701.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_703.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_705.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_706.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_708.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_710.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_712.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_713.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_714.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_716.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_718.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_720.png)

**实现原理：**
1.  使用一个正弦波 (`sin`) 作为基础声音。
2.  根据玩家挡板每帧的移动速度 (`velocity_x`) 来计算目标音高 (`pitch_multiplier`) 和目标音量。
3.  在音频回调函数中，动态调整正在播放的正弦波的频率和振幅。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_722.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_724.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_726.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_728.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_730.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_732.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_733.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_735.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_737.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_738.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_739.png)

**核心公式与代码：**
```c
// 在每帧更新中计算目标值
target_pitch = 0.5f + abs(player_velocity_x) * 0.1f; // 基础音高 + 速度影响
target_pitch = clamp(target_pitch, 0.5f, 2.0f); // 限制音高范围
target_volume = abs(player_velocity_x) * 0.05f;

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_741.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_743.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_745.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_747.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_749.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_750.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_752.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_753.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_754.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_756.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_758.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_760.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_762.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_764.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_766.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_767.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_769.png)

// 在音频混合器中平滑过渡并生成样本
sound->pitch = move_towards(sound->pitch, target_pitch, dt * 10.0f);
sound->volume = move_towards(sound->volume, target_volume, dt * 3.0f);

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_770.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_771.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_773.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_774.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_776.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_778.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_780.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_782.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_784.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_786.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_788.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_790.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_792.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_793.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_794.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_796.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_798.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_800.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_801.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_803.png)

// 生成带音高变化的样本
float sample_index = sound->position;
float sample = sinf(2.0f * PI * sample_index * BASE_FREQUENCY * sound->pitch / SAMPLE_RATE);
output_sample = sample * sound->volume;
sound->position += sound->pitch; // 根据音高调整播放进度
```

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_805.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_807.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_809.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_811.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_812.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_814.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_816.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_818.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_819.png)

---

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_821.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_823.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_825.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_827.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_829.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_831.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_833.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_834.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_836.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_838.png)

## 总结

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_840.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_842.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_844.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_845.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_847.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_848.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_849.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_851.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_853.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_854.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_855.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_857.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_859.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_861.png)

本节课中我们一起学习了如何为C语言游戏添加关键的“游戏性”层功能。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_863.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_865.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_867.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_869.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_871.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_872.png)

1.  **我们修复了多个Bug**，使游戏逻辑更加健壮。
2.  **我们实现了一个可交互的主菜单**，玩家可以直观地选择关卡。
3.  **我们构建了一个完整的存档系统**，能够持久化保存游戏进度和最高分。
4.  **我们极大地增强了音频系统**，引入了背景音乐、多种事件音效和一个根据玩家操作动态生成的音效，显著提升了游戏的沉浸感。

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_874.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_876.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_877.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_879.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_881.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_882.png)

![](img/80ebbaad2eb9948dc69a50a6f8cfb116_884.png)

通过这些改进，我们的游戏从一个纯粹的技术演示，变得更像一款完整的、可供反复游玩的正式作品。在接下来的课程中，我们将进入“打磨阶段”，专注于优化用户体验、完善各个游戏模式以及进行最终的整合与测试。