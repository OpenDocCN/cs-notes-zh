# 005：实现核心游戏设计 🎮

![](img/a8dd2b7c2e064a5802e967ba681ac481_1.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_3.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_4.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_6.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_8.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_10.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_12.png)

在本节课中，我们将开始实现游戏的核心设计理念。我们将为游戏添加新的关卡类型，例如“Pong”和“太空侵略者”，并实现一些基础的游戏系统，如生命值和随机数生成器。我们的目标是将经典的街机游戏玩法融入到我们的打砖块游戏中。

![](img/a8dd2b7c2e064a5802e967ba681ac481_14.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_16.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_18.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_20.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_22.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_24.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_26.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_28.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_30.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_32.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_34.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_36.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_38.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_40.png)

## 概述与回顾

![](img/a8dd2b7c2e064a5802e967ba681ac481_42.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_44.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_46.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_48.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_50.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_52.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_54.png)

上一节我们为游戏添加了多种道具和特殊方块。本节我们将在此基础上，构建更复杂的关卡逻辑。

![](img/a8dd2b7c2e064a5802e967ba681ac481_56.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_58.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_60.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_62.png)

我们目前已经拥有一个基础的游戏框架，包括渲染、物理模拟和碰撞检测。现在，我们将引入“关卡状态”的概念，并为不同的游戏模式（如Pong和太空侵略者）编写特定的模拟逻辑。

![](img/a8dd2b7c2e064a5802e967ba681ac481_64.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_66.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_68.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_70.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_72.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_74.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_76.png)

## 实现Pong风格关卡 🏓

![](img/a8dd2b7c2e064a5802e967ba681ac481_78.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_80.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_82.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_84.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_86.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_88.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_89.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_91.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_92.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_94.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_96.png)

首先，我们创建一个类似Pong游戏的关卡。在这个关卡中，一排方块将作为一个整体（“敌人”）移动，并尝试追踪或躲避球。

![](img/a8dd2b7c2e064a5802e967ba681ac481_98.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_100.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_102.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_104.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_106.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_108.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_110.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_112.png)

### 1. 创建关卡状态结构体

![](img/a8dd2b7c2e064a5802e967ba681ac481_114.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_116.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_118.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_120.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_122.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_124.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_126.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_128.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_130.png)

为了管理关卡的特定数据（如敌人的位置和速度），我们首先在全局游戏状态中添加一个`level_state`联合体。目前，我们先为Pong关卡创建一个简单的状态。

![](img/a8dd2b7c2e064a5802e967ba681ac481_132.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_133.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_135.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_137.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_139.png)

```c
typedef struct {
    v2 p; // 位置
    v2 dp; // 速度
    v2 ddp; // 加速度
} pong_state;

![](img/a8dd2b7c2e064a5802e967ba681ac481_141.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_142.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_144.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_146.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_148.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_150.png)

typedef union {
    pong_state pong;
    // 未来会为其他关卡类型添加更多状态
} level_state;

![](img/a8dd2b7c2e064a5802e967ba681ac481_152.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_154.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_156.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_158.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_160.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_161.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_163.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_165.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_167.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_169.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_171.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_172.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_174.png)

level_state g_level_state;
```

![](img/a8dd2b7c2e064a5802e967ba681ac481_176.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_178.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_179.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_181.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_182.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_184.png)

### 2. 初始化与模拟

![](img/a8dd2b7c2e064a5802e967ba681ac481_186.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_188.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_190.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_192.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_194.png)

在游戏开始或进入新关卡时，我们需要初始化对应的状态。在Pong关卡的模拟函数中，我们将实现一个简单的AI：让敌人根据球的位置进行加速移动。

![](img/a8dd2b7c2e064a5802e967ba681ac481_196.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_198.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_200.png)

```c
void simulate_pong_level(level_state* state, f32 dt) {
    pong_state* pong = &state->pong;
    v2 ball_pos = g_balls[0].p; // 假设我们只有一个球

    // 简单的AI逻辑：如果球在右边，则向右加速；反之向左
    if(ball_pos.x > pong->p.x) {
        pong->ddp.x = 10.0f;
    } else if(ball_pos.x < pong->p.x) {
        pong->ddp.x = -10.0f;
    }

    // 添加摩擦力，使运动更平滑
    v2 friction = v2_mul(pong->dp, -0.5f);
    pong->ddp = v2_add(pong->ddp, friction);

    // 基础运动方程：更新速度和位置
    // v = v0 + a * t
    pong->dp = v2_add(pong->dp, v2_mul(pong->ddp, dt));
    // s = s0 + v * t
    pong->p = v2_add(pong->p, v2_mul(pong->dp, dt));

    // 限制敌人在屏幕范围内移动
    f32 arena_half_size_x = 40.0f; // 根据实际舞台大小调整
    f32 enemy_half_size_x = 1.0f; // 根据敌人大小调整
    if(pong->p.x > arena_half_size_x - enemy_half_size_x) {
        pong->p.x = arena_half_size_x - enemy_half_size_x;
        pong->dp.x *= -0.5f; // 碰到墙壁后反弹并减速
    }
    if(pong->p.x < -arena_half_size_x + enemy_half_size_x) {
        pong->p.x = -arena_half_size_x + enemy_half_size_x;
        pong->dp.x *= -0.5f;
    }
}
```

![](img/a8dd2b7c2e064a5802e967ba681ac481_202.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_203.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_205.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_207.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_209.png)

### 3. 关联方块与敌人

![](img/a8dd2b7c2e064a5802e967ba681ac481_211.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_213.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_215.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_217.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_219.png)

关卡中的方块位置需要相对于敌人的位置来计算。我们在创建方块时，存储其相对于敌人的初始位置偏移量。

![](img/a8dd2b7c2e064a5802e967ba681ac481_221.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_222.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_224.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_226.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_228.png)

```c
typedef struct {
    v2 relative_p; // 相对于关卡“敌人”原点的位置
    v2 p; // 在世界中的实际位置，由 relative_p + enemy_p 计算得出
    // ... 其他方块属性
} block;

void simulate_block_for_level(block* b, level_state* state) {
    // 根据关卡类型更新方块的绝对位置
    // 例如，对于Pong关卡：
    pong_state* pong = &state->pong;
    b->p = v2_add(b->relative_p, pong->p);
}
```

![](img/a8dd2b7c2e064a5802e967ba681ac481_230.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_232.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_234.png)

在游戏主循环中，我们先调用`simulate_pong_level`更新敌人位置，然后遍历所有方块，调用`simulate_block_for_level`更新每个方块的位置。

![](img/a8dd2b7c2e064a5802e967ba681ac481_236.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_238.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_240.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_242.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_244.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_246.png)

## 实现太空侵略者关卡 👾

![](img/a8dd2b7c2e064a5802e967ba681ac481_248.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_249.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_251.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_253.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_255.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_257.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_259.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_260.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_262.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_264.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_266.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_268.png)

接下来，我们实现一个类似“太空侵略者”的关卡。敌人方块将成群结队地水平移动，到达边界后下移并反向。

![](img/a8dd2b7c2e064a5802e967ba681ac481_270.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_272.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_274.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_276.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_278.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_280.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_282.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_284.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_286.png)

### 1. 创建侵略者状态

![](img/a8dd2b7c2e064a5802e967ba681ac481_288.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_290.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_292.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_294.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_296.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_298.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_300.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_302.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_304.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_306.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_307.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_309.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_311.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_313.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_315.png)

我们为太空侵略者关卡定义一个新的状态结构体。

![](img/a8dd2b7c2e064a5802e967ba681ac481_317.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_319.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_321.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_323.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_325.png)

```c
typedef struct {
    v2 enemy_p; // 整个侵略者群的原点位置
    f32 movement_timer;
    f32 movement_target_time;
    b32 is_moving_right;
    b32 should_move_down;
} invaders_state;
```

![](img/a8dd2b7c2e064a5802e967ba681ac481_327.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_328.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_330.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_332.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_334.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_336.png)

### 2. 初始化与群体运动逻辑

![](img/a8dd2b7c2e064a5802e967ba681ac481_338.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_340.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_342.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_344.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_346.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_348.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_350.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_352.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_354.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_356.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_358.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_360.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_362.png)

在关卡开始时，我们初始化状态，并设置一个计时器来控制侵略者群的移动节奏。

![](img/a8dd2b7c2e064a5802e967ba681ac481_364.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_366.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_368.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_370.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_372.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_373.png)

```c
void simulate_invaders_level(level_state* state, f32 dt) {
    invaders_state* inv = &state->invaders;

    inv->movement_timer += dt;
    if(inv->movement_timer >= inv->movement_target_time) {
        inv->movement_timer -= inv->movement_target_time;

        if(inv->should_move_down) {
            // 向下移动一行
            inv->enemy_p.y -= 2.0f;
            inv->should_move_down = false;
        } else {
            // 水平移动
            if(inv->is_moving_right) {
                inv->enemy_p.x += 10.0f;
            } else {
                inv->enemy_p.x -= 10.0f;
            }
        }

        // 检查是否到达屏幕边缘，如果是，则标记下一次需要向下移动并转向
        f32 left_boundary = -25.0f;
        f32 right_boundary = 25.0f;
        if(inv->enemy_p.x >= right_boundary) {
            inv->is_moving_right = false;
            inv->should_move_down = true;
        } else if(inv->enemy_p.x <= left_boundary) {
            inv->is_moving_right = true;
            inv->should_move_down = true;
        }
    }
}
```

![](img/a8dd2b7c2e064a5802e967ba681ac481_375.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_377.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_379.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_381.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_383.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_385.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_387.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_389.png)

同样，我们需要在`simulate_block_for_level`函数中，根据`invaders_state`来更新每个侵略者方块的绝对位置。

![](img/a8dd2b7c2e064a5802e967ba681ac481_391.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_392.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_394.png)

### 3. 失败条件

![](img/a8dd2b7c2e064a5802e967ba681ac481_396.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_398.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_399.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_401.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_402.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_404.png)

当侵略者过于接近玩家（屏幕底部）时，游戏失败。我们可以在模拟每个方块时进行检测。

![](img/a8dd2b7c2e064a5802e967ba681ac481_406.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_408.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_410.png)

```c
void simulate_block_for_level(block* b, level_state* state) {
    // ... 更新方块位置 ...

    // 检查侵略者是否接触到玩家
    invaders_state* inv = &state->invaders;
    if(inv->do_collision_test) {
        if(b->p.y - b->half_size.y < g_player.p.y + g_player.half_size.y) {
            // 触发游戏结束或生命值减少
            lose_life();
            inv->do_collision_test = false; // 重置检测标志
        }
    }
}
```

![](img/a8dd2b7c2e064a5802e967ba681ac481_412.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_414.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_416.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_418.png)

在`simulate_invaders_level`中，当侵略者群整体下移时，将`do_collision_test`标志设置为`true`，以便在下一帧检测碰撞。

![](img/a8dd2b7c2e064a5802e967ba681ac481_420.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_422.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_424.png)

## 实现玩家生命值系统 ❤️

![](img/a8dd2b7c2e064a5802e967ba681ac481_426.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_428.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_430.png)

为了让游戏更有挑战性，我们为玩家添加生命值系统。

![](img/a8dd2b7c2e064a5802e967ba681ac481_432.png)

### 1. 添加生命值变量

![](img/a8dd2b7c2e064a5802e967ba681ac481_434.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_435.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_437.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_439.png)

在玩家结构体中添加生命值。

![](img/a8dd2b7c2e064a5802e967ba681ac481_441.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_443.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_444.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_446.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_448.png)

```c
typedef struct {
    v2 p;
    v2 half_size;
    s32 lives;
    // ... 其他属性
} player;

![](img/a8dd2b7c2e064a5802e967ba681ac481_450.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_452.png)

player g_player;
```

![](img/a8dd2b7c2e064a5802e967ba681ac481_454.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_456.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_458.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_460.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_462.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_464.png)

### 2. 初始化与生命值减少

![](img/a8dd2b7c2e064a5802e967ba681ac481_466.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_468.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_470.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_471.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_473.png)

在游戏开始时初始化生命值。当球掉落到底部或侵略者接触到玩家时，减少生命值。

![](img/a8dd2b7c2e064a5802e967ba681ac481_475.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_476.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_478.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_480.png)

```c
void start_game() {
    // ... 其他初始化 ...
    g_player.lives = 3;
}

![](img/a8dd2b7c2e064a5802e967ba681ac481_482.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_484.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_486.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_488.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_490.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_492.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_494.png)

void lose_life() {
    g_player.lives--;
    if(g_player.lives > 0) {
        // 重置球和玩家位置，继续游戏
        reset_balls();
        reset_player();
    } else {
        // 游戏结束
        game_over();
    }
}
```

![](img/a8dd2b7c2e064a5802e967ba681ac481_496.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_497.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_499.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_501.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_503.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_505.png)

### 3. 在屏幕上显示生命值

![](img/a8dd2b7c2e064a5802e967ba681ac481_507.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_509.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_511.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_513.png)

在渲染函数中，在屏幕角落绘制代表剩余生命值的小图标。

```c
void draw_lives() {
    for(s32 i = 0; i < g_player.lives; ++i) {
        v2 life_icon_p = {
            g_arena_half_size.x - 2.0f + i * 2.5f,
            g_arena_half_size.y - 2.0f
        };
        draw_rect(life_icon_p, (v2){0.5f, 0.5f}, COLOR_WHITE);
    }
}
```

![](img/a8dd2b7c2e064a5802e967ba681ac481_515.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_517.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_519.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_521.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_523.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_525.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_527.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_529.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_531.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_533.png)

## 实现简易随机数生成器 🎲

![](img/a8dd2b7c2e064a5802e967ba681ac481_535.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_537.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_539.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_541.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_543.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_545.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_547.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_549.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_551.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_553.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_555.png)

为了随机生成道具，我们需要一个随机数生成器。我们实现一个简单但高效的Xorshift算法。

![](img/a8dd2b7c2e064a5802e967ba681ac481_557.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_559.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_561.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_563.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_565.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_567.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_569.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_571.png)

### 1. Xorshift算法实现

![](img/a8dd2b7c2e064a5802e967ba681ac481_573.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_575.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_577.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_579.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_581.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_582.png)

```c
static u32 g_random_state = 123456789; // 初始种子

![](img/a8dd2b7c2e064a5802e967ba681ac481_584.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_586.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_588.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_590.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_592.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_594.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_596.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_598.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_599.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_601.png)

u32 random_u32() {
    u32 result = g_random_state;
    result ^= result << 13;
    result ^= result >> 17;
    result ^= result << 5;
    g_random_state = result;
    return result;
}
```

![](img/a8dd2b7c2e064a5802e967ba681ac481_603.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_605.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_607.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_609.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_611.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_613.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_615.png)

### 2. 辅助函数

![](img/a8dd2b7c2e064a5802e967ba681ac481_617.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_619.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_621.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_623.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_625.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_627.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_629.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_631.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_632.png)

基于`random_u32()`，我们可以创建更实用的辅助函数。

![](img/a8dd2b7c2e064a5802e967ba681ac481_634.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_636.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_638.png)

```c
// 生成一个在 [min, max] 范围内的随机整数
s32 random_int_in_range(s32 min, s32 max) {
    u32 range = (max - min) + 1;
    u32 random_value = random_u32() % range;
    return min + (s32)random_value;
}

![](img/a8dd2b7c2e064a5802e967ba681ac481_640.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_642.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_644.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_646.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_648.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_650.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_652.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_654.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_656.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_658.png)

// 以一定概率返回 true
b32 random_chance(f32 probability) {
    // probability 应在 0.0 到 1.0 之间
    u32 max = 10000;
    u32 threshold = (u32)(probability * (f32)max);
    return (random_u32() % max) < threshold;
}
```

![](img/a8dd2b7c2e064a5802e967ba681ac481_660.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_662.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_663.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_665.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_666.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_668.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_670.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_672.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_674.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_676.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_678.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_680.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_682.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_684.png)

### 3. 在生成方块时随机添加道具

![](img/a8dd2b7c2e064a5802e967ba681ac481_686.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_688.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_690.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_692.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_694.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_696.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_698.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_700.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_702.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_704.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_706.png)

在创建方块（尤其是太空侵略者）时，我们可以使用随机数来决定某个方块是否包含道具，以及包含哪种道具。

![](img/a8dd2b7c2e064a5802e967ba681ac481_708.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_710.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_712.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_714.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_716.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_718.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_720.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_722.png)

```c
void create_invader_block(v2 relative_pos) {
    block* b = get_next_available_block();
    b->relative_p = relative_pos;
    // ... 设置其他属性 ...

    // 例如：每5个方块中，有1个会生成随机道具
    if(random_chance(0.2f)) { // 20% 概率
        b->powerup_type = random_int_in_range(0, POWERUP_COUNT - 1);
    } else {
        b->powerup_type = POWERUP_NONE;
    }
}
```

![](img/a8dd2b7c2e064a5802e967ba681ac481_724.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_726.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_728.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_730.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_732.png)

## 总结

![](img/a8dd2b7c2e064a5802e967ba681ac481_734.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_736.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_738.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_740.png)

本节课中我们一起学习了：

![](img/a8dd2b7c2e064a5802e967ba681ac481_742.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_744.png)

1.  **创建复合关卡状态**：我们使用联合体`level_state`来管理不同关卡类型（如Pong、太空侵略者）的特定数据。
2.  **实现Pong关卡逻辑**：我们创建了一个由方块组成的“球拍”，并为其编写了简单的追踪AI和基于物理的运动。
3.  **实现太空侵略者关卡逻辑**：我们实现了侵略者群的波浪式移动模式，并设置了失败条件。
4.  **添加玩家生命值系统**：玩家现在拥有多次游戏机会，生命值会显示在屏幕上。
5.  **实现随机数生成器**：我们使用Xorshift算法生成了随机数，并用于随机分配道具，增加了游戏的不可预测性和重玩价值。

![](img/a8dd2b7c2e064a5802e967ba681ac481_746.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_748.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_750.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_752.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_754.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_755.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_757.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_759.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_761.png)

![](img/a8dd2b7c2e064a5802e967ba681ac481_762.png)

通过这些步骤，我们游戏的核心玩法变得更加丰富和有趣。下一节课，我们将修复目前存在的bug，并可能添加计分系统、更多道具效果，以及新的关卡类型（如俄罗斯方块）。