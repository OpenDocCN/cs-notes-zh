# 004：编程游戏机制 🎮

![](img/2d11af16ffb245ab1947921d1bfbeeda_1.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_2.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_4.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_6.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_7.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_9.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_11.png)

在本节课中，我们将继续从零开始用C语言制作游戏。上一节我们开始为游戏本身实现一些机制和想法。本节中，我们将进一步构建这些机制，并开始构建一个更有趣的游戏。

![](img/2d11af16ffb245ab1947921d1bfbeeda_13.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_15.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_17.png)

我们从一个空白文件开始，你可以观看整个开发过程。之前的三个直播录像可以在YouTube页面（youtube.com/DanZDan）观看，你也可以在dazam.h.o下载每一集的源代码和可执行文件。

![](img/2d11af16ffb245ab1947921d1bfbeeda_19.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_21.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_23.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_24.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_26.png)

## 概述与当前进度

![](img/2d11af16ffb245ab1947921d1bfbeeda_28.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_29.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_31.png)

上一节我们从一个打砖块（Breakout）克隆开始，并逐步实现了一些我们自己的新想法。我们尝试了不同形状的砖墙，并开始制作能量道具（Power-ups），虽然还没有完成。

![](img/2d11af16ffb245ab1947921d1bfbeeda_33.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_35.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_37.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_39.png)

今天，我们将继续这项工作，并更多地构建游戏机制。首先，我们需要改变游戏玩法和代码的结构。我们将从基于“游戏模式”转向基于“关卡”的系统。每个关卡可以选择其想要的任何机制。

## 核心游戏机制设计

基于之前的讨论，我计划从四个基本机制开始，外加两个额外方面。

![](img/2d11af16ffb245ab1947921d1bfbeeda_41.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_43.png)

### 1. 能量道具与负面效果
*   **能量道具**：玩家希望获得的增益效果。
*   **负面效果**：玩家需要避免的减益效果，可以看作是反向的能量道具。

![](img/2d11af16ffb245ab1947921d1bfbeeda_45.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_47.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_49.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_51.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_53.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_55.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_57.png)

### 2. 生命系统
这个机制基于上节课的一个想法：当砖块被摧毁时，随机复活其邻居。我们将实现一个生命系统。每个砖块有最大生命值（例如5点）。当它的生命值从5降到4时，会为相邻砖块增加1点生命。这意味着你需要小心选择先摧毁哪些砖块，否则可能会让问题变得更糟。

![](img/2d11af16ffb245ab1947921d1bfbeeda_59.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_61.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_63.png)

### 3. 对手机制
这是我认为最酷的机制。将有两种类型的砖块和两个球。每种球只能摧毁与其颜色对应的砖块。例如，红色球只能摧毁红色砖块，绿色球只能摧毁绿色砖块。这样会形成有趣的策略和视觉区分。

![](img/2d11af16ffb245ab1947921d1bfbeeda_65.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_67.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_69.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_71.png)

### 4. 砖块布局与移动
*   **砖块布局**：我们已经尝试过普通墙、交错排列、间隔排列等。我们还可以设计更疯狂的形状，比如圆形或倾斜的竞技场形状。
*   **砖块移动**：这是游戏的原始核心想法。我们将为不同关卡添加不同的砖块移动模式，这将是游戏真正的亮点。

![](img/2d11af16ffb245ab1947921d1bfbeeda_73.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_75.png)

基于这些机制，我们可以构建有趣的关卡。原来的“游戏模式”系统将转变为“关卡”系统。

![](img/2d11af16ffb245ab1947921d1bfbeeda_77.png)

## 代码重构：从游戏模式到关卡

![](img/2d11af16ffb245ab1947921d1bfbeeda_79.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_81.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_83.png)

首先，我们需要将现有的游戏模式代码重构为关卡系统。

![](img/2d11af16ffb245ab1947921d1bfbeeda_85.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_87.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_89.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_91.png)

以下是重构的核心步骤：

1.  将 `current_game_mode` 变量改为 `current_level`。
2.  将 `simulate_game_mode` 函数改为 `simulate_level`。
3.  在游戏全局状态中，用关卡状态替换游戏模式状态。
4.  修改关卡切换逻辑，例如 `advance_level` 函数。
5.  移除旧的游戏模式相关代码，确保能量道具等系统现在与关卡关联。

![](img/2d11af16ffb245ab1947921d1bfbeeda_93.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_95.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_97.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_99.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_101.png)

重构后的主要结构变化如下：
```c
// 之前
Game_State {
    Game_Mode current_game_mode;
    // ...
};

![](img/2d11af16ffb245ab1947921d1bfbeeda_103.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_105.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_107.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_109.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_111.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_113.png)

// 之后
Game_State {
    s32 current_level;
    // ...
};

void simulate_level(s32 level) {
    switch(level) {
        case 0: // 普通模式
            // ...
            break;
        case 1: // 墙模式
            // ...
            break;
        // ... 更多关卡
    }
}
```

## 实现能量道具系统

![](img/2d11af16ffb245ab1947921d1bfbeeda_115.png)

上一节我们开始了能量道具系统，现在我们来完成它。我们首先测试让第一排的每个砖块都掉落一个“无敌”能量道具。

![](img/2d11af16ffb245ab1947921d1bfbeeda_117.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_119.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_121.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_123.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_125.png)

### 能量道具下落与碰撞
我们让能量道具以一定速度下落，并检测其与玩家的碰撞。

![](img/2d11af16ffb245ab1947921d1bfbeeda_127.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_129.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_131.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_133.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_135.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_137.png)

能量道具的速度和碰撞检测代码如下：
```c
// 能量道具下落
power_block->p.y += power_block_speed * dt;

![](img/2d11af16ffb245ab1947921d1bfbeeda_139.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_141.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_143.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_145.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_147.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_148.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_150.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_151.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_153.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_155.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_157.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_158.png)

// 与玩家碰撞检测
if (rects_overlap(power_block->p, power_block_half_size,
                  player->p, player_half_size)) {
    power_block->kind = Power_Inactive; // 停用能量道具
    // 根据能量道具类型应用效果
    switch(power_block->kind) {
        case Power_Invincibility:
            invincibility_time = 5.0f; // 5秒无敌时间
            break;
        // ... 其他能量道具
    }
}
```

![](img/2d11af16ffb245ab1947921d1bfbeeda_160.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_162.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_163.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_165.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_167.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_169.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_171.png)

### 无敌效果实现
我们不再使用布尔变量 `is_invincible`，而是使用一个计时器 `invincibility_time`。当时间大于0时，玩家处于无敌状态。

![](img/2d11af16ffb245ab1947921d1bfbeeda_173.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_175.png)

无敌状态的检测和更新：
```c
// 更新无敌时间
if (invincibility_time > 0) {
    invincibility_time -= dt;
}

![](img/2d11af16ffb245ab1947921d1bfbeeda_177.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_179.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_181.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_183.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_185.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_187.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_189.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_191.png)

// 检测是否无敌（用于渲染和逻辑）
bool is_invincible_now = (invincibility_time > 0);
```

![](img/2d11af16ffb245ab1947921d1bfbeeda_193.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_195.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_197.png)

## 实现三连发能量道具

![](img/2d11af16ffb245ab1947921d1bfbeeda_199.png)

这个能量道具的效果是：当球从玩家处弹起时，会额外生成两个球，但这些额外球只在向上运动时存在，一旦向下运动就会消失。

![](img/2d11af16ffb245ab1947921d1bfbeeda_201.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_203.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_204.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_206.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_208.png)

### 球系统重构
为了支持多个球，我们首先重构球系统。我们创建一个球结构体数组，并添加标志位来管理球的状态（如是否活跃、是否会在向下运动时被销毁）。

![](img/2d11af16ffb245ab1947921d1bfbeeda_210.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_212.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_214.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_216.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_218.png)

球结构体和标志位定义：
```c
#define BALL_FLAG_ACTIVE       (1 << 0)
#define BALL_FLAG_DESTROY_ON_DP_DOWN (1 << 1) // 向下运动时销毁
#define BALL_FLAG_RIVAL_A      (1 << 2) // 对手球类型A
#define BALL_FLAG_RIVAL_B      (1 << 3) // 对手球类型B
#define BALL_FLAG_ADJUST_SPEED (1 << 4) // 需要调整速度

![](img/2d11af16ffb245ab1947921d1bfbeeda_220.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_222.png)

typedef struct {
    v2 p; // 位置
    v2 dp; // 速度
    v2 half_size;
    f32 base_speed;
    f32 speed_multiplier;
    u32 flags; // 状态标志位
} Ball;

Ball balls[MAX_BALLS]; // 球数组
```

![](img/2d11af16ffb245ab1947921d1bfbeeda_224.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_226.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_228.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_230.png)

### 三连发生成逻辑
当玩家获得三连发能量道具并接球时，我们生成两个额外的球。

![](img/2d11af16ffb245ab1947921d1bfbeeda_232.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_234.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_236.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_238.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_240.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_242.png)

生成额外球的代码逻辑：
```c
if (triple_shot_count > 0) {
    triple_shot_count--;
    // 生成两个额外的球
    for (int i = 0; i < 2; ++i) {
        Ball* new_ball = get_next_available_ball(); // 获取下一个可用的球
        if (new_ball) {
            // 初始化新球的位置和速度
            new_ball->p = player->p;
            new_ball->p.y += player_half_size.y;
            new_ball->dp.x = some_offset_x; // 设置一些横向偏移
            new_ball->dp.y = ball_base_speed; // 向上运动
            new_ball->base_speed = ball_base_speed;
            new_ball->speed_multiplier = 1.0f;
            // 设置标志位：活跃，且向下运动时销毁
            new_ball->flags = BALL_FLAG_ACTIVE | BALL_FLAG_DESTROY_ON_DP_DOWN;
        }
    }
}
```

![](img/2d11af16ffb245ab1947921d1bfbeeda_244.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_246.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_248.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_250.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_252.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_254.png)

### 球运动与销毁逻辑
我们需要在球运动循环中检测 `BALL_FLAG_DESTROY_ON_DP_DOWN` 标志。当球的速度向下（dp.y > 0）且碰到砖块或顶部时，将其销毁（取消活跃标志）。

![](img/2d11af16ffb245ab1947921d1bfbeeda_256.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_258.png)

球运动与销毁检测：
```c
for (each active ball) {
    // 更新球的位置
    ball->p.x += ball->dp.x * dt;
    ball->p.y += ball->dp.y * dt;

    // 检测与砖块碰撞
    if (ball_block_collision(ball, block)) {
        if (HAS_FLAG(ball->flags, BALL_FLAG_DESTROY_ON_DP_DOWN) && ball->dp.y > 0) {
            // 销毁球：清除活跃标志
            ball->flags &= ~BALL_FLAG_ACTIVE;
        }
        // ... 其他碰撞处理
    }

    // 检测与顶部碰撞
    if (ball->p.y <= top_boundary) {
        if (HAS_FLAG(ball->flags, BALL_FLAG_DESTROY_ON_DP_DOWN) && ball->dp.y > 0) {
            ball->flags &= ~BALL_FLAG_ACTIVE;
        }
        // ... 反弹逻辑
    }
}
```

![](img/2d11af16ffb245ab1947921d1bfbeeda_260.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_262.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_264.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_266.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_268.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_270.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_272.png)

## 实现彗星能量道具

![](img/2d11af16ffb245ab1947921d1bfbeeda_274.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_276.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_278.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_280.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_282.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_284.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_286.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_288.png)

彗星能量道具使球在向上运动时不受砖块反弹影响，直接穿透并摧毁砖块，但在向下运动时恢复正常。

![](img/2d11af16ffb245ab1947921d1bfbeeda_290.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_292.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_294.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_296.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_298.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_300.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_302.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_304.png)

### 彗星效果实现
我们添加一个 `comet_time` 计时器。当时间大于0时，如果球向上运动（dp.y < 0），则在与砖块碰撞时不改变方向。

![](img/2d11af16ffb245ab1947921d1bfbeeda_306.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_308.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_310.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_312.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_314.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_316.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_318.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_320.png)

彗星状态下的碰撞处理：
```c
void ball_block_collision(Ball* ball, Block* block) {
    if (comet_time > 0 && ball->dp.y < 0) {
        // 彗星状态且球向上：直接摧毁砖块，不改变球的方向
        block->life = 0; // 或调用摧毁砖块的函数
        // 注意：这里不执行后面的反弹代码
        return;
    }
    // 正常的碰撞反弹逻辑
    // ...
}
```

![](img/2d11af16ffb245ab1947921d1bfbeeda_322.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_324.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_326.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_328.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_330.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_332.png)

## 实现负面效果（能量道具的相反面）

![](img/2d11af16ffb245ab1947921d1bfbeeda_334.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_336.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_338.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_340.png)

负面效果与能量道具类似，但产生对玩家不利的效果。我们将其统一称为“能量块”，但种类不同。

![](img/2d11af16ffb245ab1947921d1bfbeeda_342.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_344.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_346.png)

### 负面效果种类
我们计划实现以下几种负面效果：
1.  **坚固砖块**：一段时间内砖块无法被摧毁。
2.  **反向控制**：颠倒玩家的左右移动控制。
3.  **缓慢玩家**：降低玩家的移动速度。

![](img/2d11af16ffb245ab1947921d1bfbeeda_348.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_350.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_352.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_354.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_356.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_358.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_360.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_362.png)

### 负面效果的生成与碰撞
负面效果的生成逻辑与能量道具类似，但可能出现在更高的砖排上。碰撞检测后，根据种类应用负面效果。

![](img/2d11af16ffb245ab1947921d1bfbeeda_364.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_366.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_368.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_370.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_371.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_373.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_375.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_377.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_378.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_380.png)

负面效果应用示例（反向控制）：
```c
case Power_InvertedControls:
    inverted_controls_time = 5.0f; // 5秒反向控制
    break;
```

![](img/2d11af16ffb245ab1947921d1bfbeeda_382.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_384.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_386.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_388.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_390.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_392.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_394.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_396.png)

在玩家移动逻辑中检测反向控制：
```c
f32 mouse_delta_x = input->mouse.x - old_mouse.x;
if (inverted_controls_time > 0) {
    mouse_delta_x = -mouse_delta_x; // 反向控制
}
player->desired_p.x += mouse_delta_x * some_sensitivity;
```

![](img/2d11af16ffb245ab1947921d1bfbeeda_398.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_400.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_402.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_404.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_406.png)

**注意**：在实现反向控制和缓慢玩家时，我们遇到了技术挑战（如鼠标移动到屏幕边缘时的处理），因此标记为待办事项，稍后解决。

![](img/2d11af16ffb245ab1947921d1bfbeeda_408.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_410.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_412.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_414.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_416.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_418.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_420.png)

## 实现对手机制

对手机制是：有两种颜色的砖块（如红和绿）和两种颜色的球。每种球只能摧毁同色的砖块，会穿过异色砖块。

![](img/2d11af16ffb245ab1947921d1bfbeeda_422.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_424.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_426.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_428.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_430.png)

### 砖块与球的颜色标记
我们在砖块和球的结构体标志位中添加 `RIVAL_A` 和 `RIVAL_B` 标志。

![](img/2d11af16ffb245ab1947921d1bfbeeda_432.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_434.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_436.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_438.png)

设置砖块颜色模式（棋盘格）：
```c
for (int y = 0; y < rows; ++y) {
    for (int x = 0; x < cols; ++x) {
        Block* block = &blocks[y * cols + x];
        if ((x + y) % 2 == 0) {
            block->flags |= BLOCK_FLAG_RIVAL_A;
            block->color = rival_a_color; // 例如红色
        } else {
            block->flags |= BLOCK_FLAG_RIVAL_B;
            block->color = rival_b_color; // 例如绿色
        }
    }
}
```

![](img/2d11af16ffb245ab1947921d1bfbeeda_440.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_442.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_444.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_446.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_448.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_450.png)

设置球的颜色和标志：
```c
// 球0为类型A
balls[0].flags |= BALL_FLAG_RIVAL_A;
balls[0].color = rival_a_color;

![](img/2d11af16ffb245ab1947921d1bfbeeda_452.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_454.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_456.png)

// 球1为类型B
balls[1].flags |= BALL_FLAG_RIVAL_B;
balls[1].color = rival_b_color;
```

![](img/2d11af16ffb245ab1947921d1bfbeeda_458.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_460.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_462.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_464.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_466.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_468.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_469.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_471.png)

### 碰撞检测与处理
在球与砖块碰撞时，检查颜色是否匹配。如果不匹配，则忽略碰撞（球穿过砖块）。

![](img/2d11af16ffb245ab1947921d1bfbeeda_473.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_475.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_477.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_479.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_481.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_483.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_484.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_486.png)

对手机制的碰撞逻辑：
```c
bool can_destroy = false;
if (HAS_FLAG(ball->flags, BALL_FLAG_RIVAL_A) && HAS_FLAG(block->flags, BLOCK_FLAG_RIVAL_A)) {
    can_destroy = true;
} else if (HAS_FLAG(ball->flags, BALL_FLAG_RIVAL_B) && HAS_FLAG(block->flags, BLOCK_FLAG_RIVAL_B)) {
    can_destroy = true;
}

![](img/2d11af16ffb245ab1947921d1bfbeeda_488.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_490.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_492.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_494.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_496.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_498.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_500.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_502.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_504.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_506.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_508.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_510.png)

if (!can_destroy) {
    // 颜色不匹配，球穿过砖块，不执行任何破坏或反弹逻辑
    return;
}
// 颜色匹配，执行正常的摧毁和反弹逻辑
// ...
```

![](img/2d11af16ffb245ab1947921d1bfbeeda_512.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_514.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_516.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_518.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_520.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_522.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_524.png)

### 双球速度调整
当两个球同时存在时，为了避免它们同时从不同位置击中玩家导致无法防御，我们尝试实现一个速度调整机制。当某个球即将击中玩家，而另一个球也即将在相近时间击中时，调整后一个球的速度，使它们错开时间击中玩家。

![](img/2d11af16ffb245ab1947921d1bfbeeda_526.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_528.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_530.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_532.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_534.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_536.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_538.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_540.png)

速度调整的基本思路（简化版）：
```c
f32 calculate_speed_adjustment(Ball* ball_to_adjust, Ball* other_ball) {
    // 计算两个球到达玩家的大致时间
    f32 dist_a = ball_to_adjust->p.y - player->p.y; // 假设玩家在下方
    f32 time_a = dist_a / fabs(ball_to_adjust->dp.y);

    f32 dist_b = other_ball->p.y - player->p.y;
    f32 time_b = dist_b / fabs(other_ball->dp.y);

    f32 time_diff = time_a - time_b;
    // 将时间差映射到速度缩放因子（例如0.5到1.0之间）
    f32 scale = clamp(0.5f + 0.5f * time_diff, 0.5f, 1.0f);
    return scale;
}
```

![](img/2d11af16ffb245ab1947921d1bfbeeda_542.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_544.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_546.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_548.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_550.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_552.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_554.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_556.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_558.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_560.png)

在球改变方向（即将向下运动）时调用此函数，并调整其速度。

![](img/2d11af16ffb245ab1947921d1bfbeeda_562.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_564.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_566.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_568.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_570.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_572.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_573.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_575.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_577.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_579.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_581.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_583.png)

## 构建示例关卡

![](img/2d11af16ffb245ab1947921d1bfbeeda_585.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_587.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_589.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_591.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_593.png)

为了测试我们的机制，我们构建了几个简单的示例关卡。

![](img/2d11af16ffb245ab1947921d1bfbeeda_595.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_597.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_599.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_601.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_603.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_605.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_607.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_609.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_611.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_613.png)

### 关卡0：普通打砖块
这是基础关卡，使用普通的砖块布局和颜色，没有特殊的对手机制或复杂的能量道具。

![](img/2d11af16ffb245ab1947921d1bfbeeda_615.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_617.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_619.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_621.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_623.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_625.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_627.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_628.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_630.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_632.png)

### 关卡1：墙模式 + 能量道具/负面效果
使用之前“墙”的砖块布局。我们在特定的几排砖块上硬编码生成能量道具和负面效果，以测试它们的生成和效果。

![](img/2d11af16ffb245ab1947921d1bfbeeda_634.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_636.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_638.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_640.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_642.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_644.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_646.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_648.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_650.png)

### 关卡2：体育场模式 + 对手机制
创建一个8x8的砖块网格，并应用棋盘格颜色模式（对手机制）。同时激活两个不同颜色的球，玩家必须用对应的球去摧毁对应颜色的砖块。

![](img/2d11af16ffb245ab1947921d1bfbeeda_652.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_654.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_656.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_658.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_660.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_662.png)

## 遇到的问题与待办事项

![](img/2d11af16ffb245ab1947921d1bfbeeda_664.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_666.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_668.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_670.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_672.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_674.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_676.png)

在实现过程中，我们遇到了一些需要后续调试和解决的问题：

![](img/2d11af16ffb245ab1947921d1bfbeeda_678.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_680.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_682.png)

1.  **彗星能量道具bug**：彗星效果有时会中途停止，需要调试。
2.  **三连发球行为异常**：额外球的生成和销毁逻辑可能存在bug，导致意外行为。
3.  **对手机制双球速度调整**：当前的调整算法还不完善，有时会导致不可预测的球速。
4.  **负面效果控制问题**：反向控制和缓慢玩家的实现因鼠标输入处理问题被标记为待办。
5.  **生命系统尚未实现**：我们计划了生命系统（砖块生命值变化影响邻居），但尚未编码。
6.  **缺乏随机数系统**：目前能量道具的生成是硬编码的，需要引入随机性。
7.  **代码需要清理和重构**：随着机制增加，代码变得有些杂乱，需要提取辅助函数、整理结构。

![](img/2d11af16ffb245ab1947921d1bfbeeda_684.png)

## 总结与下一步计划

![](img/2d11af16ffb245ab1947921d1bfbeeda_686.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_688.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_690.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_692.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_694.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_696.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_698.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_700.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_702.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_704.png)

本节课中，我们一起学习了如何将游戏从“游戏模式”结构重构为更灵活的“关卡”系统。我们实现并测试了多个核心游戏机制：

![](img/2d11af16ffb245ab1947921d1bfbeeda_706.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_708.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_710.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_712.png)

*   **能量道具系统**：完成了无敌、三连发、彗星等效果。
*   **负面效果系统**：开始了坚固砖块、反向控制等效果的框架。
*   **对手机制**：实现了颜色匹配的砖块与球系统，并尝试了双球速度调整。
*   **关卡构建**：创建了普通、墙模式、体育场模式等示例关卡来展示机制。

![](img/2d11af16ffb245ab1947921d1bfbeeda_714.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_716.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_718.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_720.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_721.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_723.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_725.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_727.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_729.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_731.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_732.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_734.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_736.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_738.png)

尽管遇到了一些bug和未完成的部分，但游戏已经具备了多种有趣的玩法可能性。

![](img/2d11af16ffb245ab1947921d1bfbeeda_740.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_742.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_744.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_746.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_748.png)

**下一步计划**：
1.  调试当前已知的bug（彗星、三连发球）。
2.  实现生命系统。
3.  完善对手机制的双球平衡性。
4.  引入随机数系统用于能量道具生成。
5.  实现砖块移动系统（这是游戏的核心魅力所在）。
6.  进行代码清理、引擎改进和最终关卡设计。

![](img/2d11af16ffb245ab1947921d1bfbeeda_750.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_751.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_753.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_755.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_757.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_758.png)

![](img/2d11af16ffb245ab1947921d1bfbeeda_760.png)

你可以访问 dazam.h.o 下载本集的源代码，并在YouTube上观看完整的开发过程录像。期待在下次直播中继续完善这个游戏！