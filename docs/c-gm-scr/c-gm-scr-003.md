# 003：游戏玩法编程与关卡设计 🎮

![](img/d64d01b71ce34c065794ea9c9a82a965_1.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_3.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_5.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_7.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_8.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_10.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_12.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_14.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_16.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_18.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_20.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_22.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_24.png)

在本节课中，我们将继续完善我们的打砖块游戏。我们将专注于游戏玩法的改进，包括调整球的物理特性、设计不同的砖块布局、实现游戏胜利与失败条件，并开始构建一个支持多种游戏模式的系统。

![](img/d64d01b71ce34c065794ea9c9a82a965_26.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_28.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_30.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_31.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_33.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_35.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_37.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_39.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_41.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_43.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_44.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_46.png)

---

![](img/d64d01b71ce34c065794ea9c9a82a965_48.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_50.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_52.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_54.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_56.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_58.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_60.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_62.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_64.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_66.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_68.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_70.png)

## 概述

![](img/d64d01b71ce34c065794ea9c9a82a965_72.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_74.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_76.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_78.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_80.png)

上一节我们成功实现了基础的碰撞检测系统。本节中，我们将在此基础上，对游戏的核心玩法进行一系列调整和扩展。我们将修改球与挡板的交互方式，设计多种砖块排列模式，并引入游戏状态管理，为后续添加更复杂的游戏机制打下基础。

![](img/d64d01b71ce34c065794ea9c9a82a965_82.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_84.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_86.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_88.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_89.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_91.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_93.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_95.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_97.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_99.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_101.png)

## 调整球与挡板的交互

![](img/d64d01b71ce34c065794ea9c9a82a965_103.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_105.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_107.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_108.png)

首先，我们来修改球与挡板碰撞后的反弹逻辑。原始的《打砖块》游戏中，球的水平速度取决于击中挡板的位置，而不是挡板的速度。

![](img/d64d01b71ce34c065794ea9c9a82a965_110.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_112.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_114.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_116.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_118.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_120.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_122.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_124.png)

我们将用以下代码替换原有的基于挡板速度的计算方式：

![](img/d64d01b71ce34c065794ea9c9a82a965_126.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_128.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_130.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_132.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_134.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_136.png)

```c
ball_dp.x = (ball_p.x - player_p.x) * 10.0f;
```

![](img/d64d01b71ce34c065794ea9c9a82a965_138.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_140.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_142.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_144.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_146.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_148.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_150.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_152.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_154.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_156.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_158.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_160.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_162.png)

这个公式 `ball_dp.x = (ball_p.x - player_p.x) * 10.0f` 使得球反弹的水平方向完全由击中挡板的相对水平位置决定。击中挡板左侧，球向左反弹；击中右侧，则向右反弹。系数 `10.0f` 用于控制反弹的强度。

![](img/d64d01b71ce34c065794ea9c9a82a965_164.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_166.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_168.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_170.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_172.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_173.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_175.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_177.png)

## 改进砖块布局与视觉效果

![](img/d64d01b71ce34c065794ea9c9a82a965_179.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_180.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_182.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_184.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_186.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_188.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_190.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_192.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_194.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_196.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_198.png)

接下来，我们调整砖块的生成方式，使其排列更美观，并增加颜色渐变效果。

![](img/d64d01b71ce34c065794ea9c9a82a965_200.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_202.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_204.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_206.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_208.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_210.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_212.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_214.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_216.png)

以下是初始化砖块位置和颜色的核心循环代码：

![](img/d64d01b71ce34c065794ea9c9a82a965_218.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_219.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_221.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_223.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_225.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_227.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_229.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_231.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_233.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_234.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_236.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_238.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_240.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_242.png)

```c
for(int y = 0; y < NUM_BLOCK_Y; ++y) {
    for(int x = 0; x < NUM_BLOCK_X; ++x) {
        // 计算位置，增加砖块间距
        block_p.x = (x * (block_half_size.x * 2.1f)) - offset_x;
        block_p.y = (y * (block_half_size.y * 2.1f)) + arena.half_size.y * 0.5f;
        // 根据行数设置颜色渐变
        block_color = (1.0f - (float)y / (float)NUM_BLOCK_Y) * 255;
    }
}
```

![](img/d64d01b71ce34c065794ea9c9a82a965_244.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_246.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_248.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_250.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_252.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_254.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_256.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_258.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_260.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_262.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_264.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_266.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_268.png)

我们通过将间距系数从 `2.0f` 改为 `2.1f`，在砖块间创造了细小的缝隙。同时，颜色根据砖块所在行数进行线性渐变，顶行最亮，底行最暗。

![](img/d64d01b71ce34c065794ea9c9a82a965_270.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_272.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_274.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_276.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_278.png)

## 实现首次发球机制

![](img/d64d01b71ce34c065794ea9c9a82a965_280.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_282.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_284.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_286.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_288.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_290.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_292.png)

为了增加游戏策略性，我们引入“首次发球”机制：游戏开始时，球第一次穿过砖块层不会发生碰撞，直到被玩家挡板反弹一次后，碰撞才生效。

![](img/d64d01b71ce34c065794ea9c9a82a965_294.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_296.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_298.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_300.png)

我们通过一个布尔变量 `first_ball_move` 来控制：

![](img/d64d01b71ce34c065794ea9c9a82a965_302.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_304.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_306.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_308.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_310.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_312.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_314.png)

```c
if(!first_ball_move) {
    // 检测球与砖块的碰撞
    // ...
}
// 当球与玩家挡板碰撞后
first_ball_move = false;
```

![](img/d64d01b71ce34c065794ea9c9a82a965_316.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_318.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_320.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_322.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_324.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_326.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_328.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_330.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_332.png)

## 设计多样化的游戏模式

![](img/d64d01b71ce34c065794ea9c9a82a965_334.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_336.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_338.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_340.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_342.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_344.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_346.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_348.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_350.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_352.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_354.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_356.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_358.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_360.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_362.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_364.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_366.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_368.png)

为了让游戏更有趣，我们开始构建一个支持多种关卡（游戏模式）的系统。我们使用一个枚举来定义不同的模式，并通过 `switch` 语句在初始化时创建不同的砖块布局。

![](img/d64d01b71ce34c065794ea9c9a82a965_370.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_371.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_373.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_375.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_377.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_379.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_381.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_383.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_385.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_387.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_389.png)

以下是定义和切换游戏模式的核心结构：

![](img/d64d01b71ce34c065794ea9c9a82a965_391.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_393.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_395.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_397.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_399.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_401.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_402.png)

```c
typedef enum {
    GameMode_Normal,
    GameMode_Wall,
    GameMode_Construction,
    GameMode_Spaced,
    GameMode_Count
} GameMode;

![](img/d64d01b71ce34c065794ea9c9a82a965_404.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_406.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_407.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_409.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_411.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_413.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_415.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_417.png)

GameMode current_game_mode = GameMode_Normal;
```

![](img/d64d01b71ce34c065794ea9c9a82a965_419.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_421.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_423.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_425.png)

在游戏初始化函数中，我们根据 `current_game_mode` 来调用不同的砖块生成逻辑。

![](img/d64d01b71ce34c065794ea9c9a82a965_427.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_429.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_431.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_433.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_435.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_437.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_439.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_441.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_443.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_445.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_447.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_449.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_451.png)

## 添加游戏胜利与失败条件

![](img/d64d01b71ce34c065794ea9c9a82a965_453.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_455.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_457.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_458.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_460.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_462.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_464.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_466.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_468.png)

一个完整的游戏需要明确的胜利与失败状态。

![](img/d64d01b71ce34c065794ea9c9a82a965_470.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_472.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_474.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_476.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_478.png)

**失败条件**：当球落到屏幕底部以下时，触发游戏结束。
```c
if(ball_p.y - ball_half_size < -arena.half_size.y) {
    // 触发游戏结束逻辑
    game_over = true;
}
```

![](img/d64d01b71ce34c065794ea9c9a82a965_480.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_481.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_483.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_485.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_487.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_489.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_491.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_493.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_495.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_497.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_499.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_500.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_502.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_504.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_505.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_507.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_509.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_511.png)

**胜利条件**：我们记录被摧毁的砖块数量，当所有砖块都被摧毁时，玩家获胜并进入下一关卡。
```c
if(blocks_destroyed >= total_blocks) {
    // 触发胜利逻辑，切换到下一游戏模式
    advance_game_mode = true;
}
```

![](img/d64d01b71ce34c065794ea9c9a82a965_513.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_515.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_517.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_519.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_521.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_523.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_525.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_527.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_529.png)

## 引入道具系统（雏形）

![](img/d64d01b71ce34c065794ea9c9a82a965_531.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_532.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_534.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_536.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_538.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_540.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_542.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_544.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_546.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_548.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_550.png)

我们开始规划一个道具系统。当特定砖块被摧毁时，会生成一个掉落物（如“无敌”或“额外球”道具），玩家需要移动挡板去接住它来获得增益效果。

![](img/d64d01b71ce34c065794ea9c9a82a965_552.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_554.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_556.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_558.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_559.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_561.png)

我们定义了一个简单的结构体来管理道具：

![](img/d64d01b71ce34c065794ea9c9a82a965_563.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_565.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_567.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_569.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_571.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_573.png)

```c
typedef struct {
    v2 p;
    int kind; // 道具类型，如 PowerUp_Invincible
    bool active;
} PowerUp;

PowerUp power_ups[MAX_POWER_UPS];
int next_power_up_index = 0;
```

![](img/d64d01b71ce34c065794ea9c9a82a965_575.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_577.png)

在砖块被摧毁的回调函数中，我们可以尝试生成一个道具。

## 总结

![](img/d64d01b71ce34c065794ea9c9a82a965_579.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_581.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_583.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_585.png)

本节课中我们一起学习了如何深化《打砖块》游戏的玩法。我们调整了球的物理交互，使其更符合经典设定；设计了多种砖块布局，增加了视觉多样性；实现了游戏的核心循环状态——胜利与失败；并初步搭建了一个支持扩展的游戏模式与道具系统框架。

![](img/d64d01b71ce34c065794ea9c9a82a965_587.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_589.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_591.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_592.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_593.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_595.png)

![](img/d64d01b71ce34c065794ea9c9a82a965_597.png)

通过这些改动，我们的游戏从一个基础原型，变得更像一个拥有可玩性和重复挑战性的完整作品。在接下来的课程中，我们将在此基础上添加粒子特效、音效、更复杂的道具以及关卡编辑器，让游戏变得更加丰富和有趣。