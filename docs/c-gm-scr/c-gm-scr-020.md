# 020：动画关卡过渡 🎮

![](img/ffd282b2d431f9765c707d3effca38b7_1.png)

![](img/ffd282b2d431f9765c707d3effca38b7_3.png)

![](img/ffd282b2d431f9765c707d3effca38b7_5.png)

![](img/ffd282b2d431f9765c707d3effca38b7_7.png)

![](img/ffd282b2d431f9765c707d3effca38b7_9.png)

![](img/ffd282b2d431f9765c707d3effca38b7_11.png)

![](img/ffd282b2d431f9765c707d3effca38b7_13.png)

![](img/ffd282b2d431f9765c707d3effca38b7_15.png)

![](img/ffd282b2d431f9765c707d3effca38b7_17.png)

在本节课中，我们将学习如何为游戏添加动画关卡过渡效果，并修复一些游戏玩法上的问题。我们将从回顾当前游戏进度开始，然后逐步实现关卡间的平滑动画切换，包括菜单到游戏以及游戏到菜单的过渡。

![](img/ffd282b2d431f9765c707d3effca38b7_19.png)

![](img/ffd282b2d431f9765c707d3effca38b7_21.png)

![](img/ffd282b2d431f9765c707d3effca38b7_23.png)

![](img/ffd282b2d431f9765c707d3effca38b7_25.png)

![](img/ffd282b2d431f9765c707d3effca38b7_27.png)

![](img/ffd282b2d431f9765c707d3effca38b7_29.png)

## 概述

![](img/ffd282b2d431f9765c707d3effca38b7_31.png)

![](img/ffd282b2d431f9765c707d3effca38b7_33.png)

![](img/ffd282b2d431f9765c707d3effca38b7_35.png)

![](img/ffd282b2d431f9765c707d3effca38b7_37.png)

![](img/ffd282b2d431f9765c707d3effca38b7_39.png)

![](img/ffd282b2d431f9765c707d3effca38b7_41.png)

![](img/ffd282b2d431f9765c707d3effca38b7_43.png)

![](img/ffd282b2d431f9765c707d3effca38b7_45.png)

![](img/ffd282b2d431f9765c707d3effca38b7_47.png)

![](img/ffd282b2d431f9765c707d3effca38b7_49.png)

![](img/ffd282b2d431f9765c707d3effca38b7_51.png)

![](img/ffd282b2d431f9765c707d3effca38b7_53.png)

![](img/ffd282b2d431f9765c707d3effca38b7_55.png)

在之前的课程中，我们已经构建了一个包含多种游戏模式的完整游戏，如经典打砖块、俄罗斯方块变体和太空侵略者变体。本节课，我们将专注于提升游戏的视觉和听觉体验，通过实现动画关卡过渡来使游戏流程更加流畅和专业。

![](img/ffd282b2d431f9765c707d3effca38b7_57.png)

![](img/ffd282b2d431f9765c707d3effca38b7_59.png)

![](img/ffd282b2d431f9765c707d3effca38b7_60.png)

![](img/ffd282b2d431f9765c707d3effca38b7_62.png)

![](img/ffd282b2d431f9765c707d3effca38b7_64.png)

![](img/ffd282b2d431f9765c707d3effca38b7_66.png)

![](img/ffd282b2d431f9765c707d3effca38b7_68.png)

![](img/ffd282b2d431f9765c707d3effca38b7_70.png)

![](img/ffd282b2d431f9765c707d3effca38b7_72.png)

![](img/ffd282b2d431f9765c707d3effca38b7_74.png)

![](img/ffd282b2d431f9765c707d3effca38b7_76.png)

![](img/ffd282b2d431f9765c707d3effca38b7_78.png)

![](img/ffd282b2d431f9765c707d3effca38b7_79.png)

![](img/ffd282b2d431f9765c707d3effca38b7_80.png)

---

![](img/ffd282b2d431f9765c707d3effca38b7_81.png)

![](img/ffd282b2d431f9765c707d3effca38b7_83.png)

![](img/ffd282b2d431f9765c707d3effca38b7_85.png)

![](img/ffd282b2d431f9765c707d3effca38b7_87.png)

![](img/ffd282b2d431f9765c707d3effca38b7_89.png)

![](img/ffd282b2d431f9765c707d3effca38b7_91.png)

![](img/ffd282b2d431f9765c707d3effca38b7_93.png)

![](img/ffd282b2d431f9765c707d3effca38b7_95.png)

![](img/ffd282b2d431f9765c707d3effca38b7_97.png)

## 回顾当前游戏进度

![](img/ffd282b2d431f9765c707d3effca38b7_99.png)

![](img/ffd282b2d431f9765c707d3effca38b7_101.png)

在开始新内容之前，让我们先回顾一下经过20次直播后游戏已达到的状态。目前游戏包含以下特性：

![](img/ffd282b2d431f9765c707d3effca38b7_103.png)

![](img/ffd282b2d431f9765c707d3effca38b7_105.png)

![](img/ffd282b2d431f9765c707d3effca38b7_107.png)

![](img/ffd282b2d431f9765c707d3effca38b7_109.png)

![](img/ffd282b2d431f9765c707d3effca38b7_111.png)

![](img/ffd282b2d431f9765c707d3effca38b7_113.png)

![](img/ffd282b2d431f9765c707d3effca38b7_115.png)

*   一个完整的打砖块核心玩法。
*   屏幕震动和粒子系统等视觉特效。
*   多种增益和减益道具。
*   三种独特的游戏模式变体：俄罗斯方块风格、弹球风格和太空侵略者风格。
*   主菜单、存档系统和音频混合器。

![](img/ffd282b2d431f9765c707d3effca38b7_117.png)

![](img/ffd282b2d431f9765c707d3effca38b7_119.png)

![](img/ffd282b2d431f9765c707d3effca38b7_121.png)

游戏源代码和可执行文件可以在我的网站 [dz.h.o](http://dz.h.o) 免费下载。你可以自由使用这些代码。

![](img/ffd282b2d431f9765c707d3effca38b7_123.png)

---

![](img/ffd282b2d431f9765c707d3effca38b7_125.png)

![](img/ffd282b2d431f9765c707d3effca38b7_127.png)

![](img/ffd282b2d431f9765c707d3effca38b7_129.png)

![](img/ffd282b2d431f9765c707d3effca38b7_131.png)

![](img/ffd282b2d431f9765c707d3effca38b7_132.png)

![](img/ffd282b2d431f9765c707d3effca38b7_134.png)

![](img/ffd282b2d431f9765c707d3effca38b7_136.png)

![](img/ffd282b2d431f9765c707d3effca38b7_138.png)

![](img/ffd282b2d431f9765c707d3effca38b7_140.png)

![](img/ffd282b2d431f9765c707d3effca38b7_142.png)

![](img/ffd282b2d431f9765c707d3effca38b7_144.png)

## 修复游戏结束分数重置问题

![](img/ffd282b2d431f9765c707d3effca38b7_146.png)

![](img/ffd282b2d431f9765c707d3effca38b7_148.png)

![](img/ffd282b2d431f9765c707d3effca38b7_150.png)

![](img/ffd282b2d431f9765c707d3effca38b7_152.png)

![](img/ffd282b2d431f9765c707d3effca38b7_154.png)

![](img/ffd282b2d431f9765c707d3effca38b7_156.png)

![](img/ffd282b2d431f9765c707d3effca38b7_157.png)

![](img/ffd282b2d431f9765c707d3effca38b7_159.png)

![](img/ffd282b2d431f9765c707d3effca38b7_161.png)

![](img/ffd282b2d431f9765c707d3effca38b7_163.png)

![](img/ffd282b2d431f9765c707d3effca38b7_165.png)

上一节我们回顾了游戏的整体进度，本节我们来看看需要修复的第一个具体问题。在游戏结束并重新开始时，分数没有正确归零。

![](img/ffd282b2d431f9765c707d3effca38b7_167.png)

![](img/ffd282b2d431f9765c707d3effca38b7_169.png)

![](img/ffd282b2d431f9765c707d3effca38b7_171.png)

![](img/ffd282b2d431f9765c707d3effca38b7_173.png)

![](img/ffd282b2d431f9765c707d3effca38b7_175.png)

以下是修复此问题的核心代码。我们在游戏重新开始的函数中重置分数：

![](img/ffd282b2d431f9765c707d3effca38b7_177.png)

![](img/ffd282b2d431f9765c707d3effca38b7_179.png)

![](img/ffd282b2d431f9765c707d3effca38b7_181.png)

![](img/ffd282b2d431f9765c707d3effca38b7_183.png)

![](img/ffd282b2d431f9765c707d3effca38b7_185.png)

```c
// 在 start_game 函数中
score = 0; // 将分数重置为0
```

![](img/ffd282b2d431f9765c707d3effca38b7_187.png)

![](img/ffd282b2d431f9765c707d3effca38b7_189.png)

![](img/ffd282b2d431f9765c707d3effca38b7_191.png)

![](img/ffd282b2d431f9765c707d3effca38b7_193.png)

这个简单的修改确保了每次新游戏都从零分开始。

![](img/ffd282b2d431f9765c707d3effca38b7_195.png)

![](img/ffd282b2d431f9765c707d3effca38b7_197.png)

![](img/ffd282b2d431f9765c707d3effca38b7_199.png)

![](img/ffd282b2d431f9765c707d3effca38b7_201.png)

![](img/ffd282b2d431f9765c707d3effca38b7_203.png)

![](img/ffd282b2d431f9765c707d3effca38b7_205.png)

![](img/ffd282b2d431f9765c707d3effca38b7_207.png)

![](img/ffd282b2d431f9765c707d3effca38b7_209.png)

![](img/ffd282b2d431f9765c707d3effca38b7_211.png)

---

![](img/ffd282b2d431f9765c707d3effca38b7_213.png)

![](img/ffd282b2d431f9765c707d3effca38b7_215.png)

![](img/ffd282b2d431f9765c707d3effca38b7_217.png)

![](img/ffd282b2d431f9765c707d3effca38b7_219.png)

![](img/ffd282b2d431f9765c707d3effca38b7_221.png)

## 调整俄罗斯方块模式玩法

![](img/ffd282b2d431f9765c707d3effca38b7_223.png)

![](img/ffd282b2d431f9765c707d3effca38b7_225.png)

![](img/ffd282b2d431f9765c707d3effca38b7_227.png)

![](img/ffd282b2d431f9765c707d3effca38b7_229.png)

![](img/ffd282b2d431f9765c707d3effca38b7_231.png)

![](img/ffd282b2d431f9765c707d3effca38b7_233.png)

上一节我们修复了一个小错误，本节中我们来改进俄罗斯方块模式的游戏玩法。我们计划做两个主要调整：

![](img/ffd282b2d431f9765c707d3effca38b7_235.png)

![](img/ffd282b2d431f9765c707d3effca38b7_237.png)

![](img/ffd282b2d431f9765c707d3effca38b7_239.png)

![](img/ffd282b2d431f9765c707d3effca38b7_241.png)

![](img/ffd282b2d431f9765c707d3effca38b7_243.png)

1.  **调整失败条件**：当方块堆积到顶部时，不再直接游戏结束，而是扣除一条生命，玩家有三次机会。
2.  **引入慢动作特效（实验性）**：当击中方块时，尝试添加短暂的慢动作效果以增强打击感。

![](img/ffd282b2d431f9765c707d3effca38b7_245.png)

![](img/ffd282b2d431f9765c707d3effca38b7_247.png)

以下是实现生命值扣除的核心逻辑修改：

![](img/ffd282b2d431f9765c707d3effca38b7_249.png)

![](img/ffd282b2d431f9765c707d3effca38b7_251.png)

![](img/ffd282b2d431f9765c707d3effca38b7_253.png)

```c
// 当方块触顶时
if (block_reaches_top) {
    player_lives--; // 扣除一条生命
    if (player_lives <= 0) {
        trigger_game_over(); // 生命耗尽则游戏结束
    } else {
        reset_ball_and_paddle(); // 否则重置球和挡板，继续游戏
    }
}
```

![](img/ffd282b2d431f9765c707d3effca38b7_255.png)

![](img/ffd282b2d431f9765c707d3effca38b7_257.png)

![](img/ffd282b2d431f9765c707d3effca38b7_259.png)

![](img/ffd282b2d431f9765c707d3effca38b7_261.png)

![](img/ffd282b2d431f9765c707d3effca38b7_263.png)

![](img/ffd282b2d431f9765c707d3effca38b7_265.png)

![](img/ffd282b2d431f9765c707d3effca38b7_267.png)

![](img/ffd282b2d431f9765c707d3effca38b7_269.png)

关于慢动作效果，我们尝试通过临时修改游戏的 `dt_multiplier`（时间乘数）来实现。当击中方块时，我们短暂降低这个值：

![](img/ffd282b2d431f9765c707d3effca38b7_271.png)

![](img/ffd282b2d431f9765c707d3effca38b7_273.png)

![](img/ffd282b2d431f9765c707d3effca38b7_274.png)

![](img/ffd282b2d431f9765c707d3effca38b7_276.png)

![](img/ffd282b2d431f9765c707d3effca38b7_278.png)

![](img/ffd282b2d431f9765c707d3effca38b7_279.png)

![](img/ffd282b2d431f9765c707d3effca38b7_281.png)

![](img/ffd282b2d431f9765c707d3effca38b7_283.png)

![](img/ffd282b2d431f9765c707d3effca38b7_285.png)

![](img/ffd282b2d431f9765c707d3effca38b7_287.png)

![](img/ffd282b2d431f9765c707d3effca38b7_289.png)

![](img/ffd282b2d431f9765c707d3effca38b7_291.png)

![](img/ffd282b2d431f9765c707d3effca38b7_293.png)

![](img/ffd282b2d431f9765c707d3effca38b7_295.png)

![](img/ffd282b2d431f9765c707d3effca38b7_297.png)

![](img/ffd282b2d431f9765c707d3effca38b7_299.png)

```c
// 击中方块时
dt_multiplier = max(0.1f, dt_multiplier - 0.2f); // 确保不低于0.1
// 随后每帧使其逐渐恢复为1.0
dt_multiplier += (1.0f - dt_multiplier) * 0.1f * delta_time;
```

![](img/ffd282b2d431f9765c707d3effca38b7_301.png)

![](img/ffd282b2d431f9765c707d3effca38b7_303.png)

![](img/ffd282b2d431f9765c707d3effca38b7_305.png)

![](img/ffd282b2d431f9765c707d3effca38b7_307.png)

我们还尝试为此搭配一个音效。然而，经过测试，这个慢动作效果可能会影响游戏节奏，最终我们决定移除这个特性，以保持游戏的流畅性。

![](img/ffd282b2d431f9765c707d3effca38b7_309.png)

![](img/ffd282b2d431f9765c707d3effca38b7_311.png)

![](img/ffd282b2d431f9765c707d3effca38b7_313.png)

![](img/ffd282b2d431f9765c707d3effca38b7_315.png)

![](img/ffd282b2d431f9765c707d3effca38b7_317.png)

---

![](img/ffd282b2d431f9765c707d3effca38b7_319.png)

![](img/ffd282b2d431f9765c707d3effca38b7_320.png)

![](img/ffd282b2d431f9765c707d3effca38b7_322.png)

![](img/ffd282b2d431f9765c707d3effca38b7_324.png)

![](img/ffd282b2d431f9765c707d3effca38b7_326.png)

![](img/ffd282b2d431f9765c707d3effca38b7_328.png)

## 实现方块邻居系统与小型方块

![](img/ffd282b2d431f9765c707d3effca38b7_330.png)

![](img/ffd282b2d431f9765c707d3effca38b7_332.png)

![](img/ffd282b2d431f9765c707d3effca38b7_334.png)

![](img/ffd282b2d431f9765c707d3effca38b7_336.png)

![](img/ffd282b2d431f9765c707d3effca38b7_338.png)

![](img/ffd282b2d431f9765c707d3effca38b7_340.png)

![](img/ffd282b2d431f9765c707d3effca38b7_342.png)

![](img/ffd282b2d431f9765c707d3effca38b7_344.png)

![](img/ffd282b2d431f9765c707d3effca38b7_346.png)

![](img/ffd282b2d431f9765c707d3effca38b7_347.png)

![](img/ffd282b2d431f9765c707d3effca38b7_349.png)

![](img/ffd282b2d431f9765c707d3effca38b7_351.png)

上一节我们调整了核心玩法，本节我们为俄罗斯方块模式引入一个“邻居系统”，并生成更小、更密集的方块阵列，以增加游戏的多样性和挑战性。

![](img/ffd282b2d431f9765c707d3effca38b7_353.png)

![](img/ffd282b2d431f9765c707d3effca38b7_355.png)

![](img/ffd282b2d431f9765c707d3effca38b7_357.png)

![](img/ffd282b2d431f9765c707d3effca38b7_359.png)

![](img/ffd282b2d431f9765c707d3effca38b7_360.png)

![](img/ffd282b2d431f9765c707d3effca38b7_362.png)

邻居系统的核心思想是，当方块生成时，它们会与相邻方块连接。摧毁一个方块可能会触发连锁反应。以下是定义方块邻居关系的简化代码结构：

![](img/ffd282b2d431f9765c707d3effca38b7_364.png)

![](img/ffd282b2d431f9765c707d3effca38b7_366.png)

![](img/ffd282b2d431f9765c707d3effca38b7_368.png)

![](img/ffd282b2d431f9765c707d3effca38b7_370.png)

![](img/ffd282b2d431f9765c707d3effca38b7_372.png)

![](img/ffd282b2d431f9765c707d3effca38b7_374.png)

![](img/ffd282b2d431f9765c707d3effca38b7_376.png)

![](img/ffd282b2d431f9765c707d3effca38b7_378.png)

```c
typedef struct Block {
    Vector2 position;
    int health;
    struct Block* neighbors[4]; // 最多4个邻居（上、下、左、右）
    bool is_active;
} Block;

![](img/ffd282b2d431f9765c707d3effca38b7_380.png)

![](img/ffd282b2d431f9765c707d3effca38b7_382.png)

![](img/ffd282b2d431f9765c707d3effca38b7_384.png)

![](img/ffd282b2d431f9765c707d3effca38b7_386.png)

![](img/ffd282b2d431f9765c707d3effca38b7_388.png)

![](img/ffd282b2d431f9765c707d3effca38b7_390.png)

![](img/ffd282b2d431f9765c707d3effca38b7_391.png)

![](img/ffd282b2d431f9765c707d3effca38b7_393.png)

![](img/ffd282b2d431f9765c707d3effca38b7_395.png)

![](img/ffd282b2d431f9765c707d3effca38b7_396.png)

// 在生成方块时初始化邻居关系
void init_block_neighbors(Block* block_array, int total_blocks) {
    for (int i = 0; i < total_blocks; ++i) {
        // ... 计算上下左右方块的索引并赋值给 neighbors 数组 ...
    }
}
```

![](img/ffd282b2d431f9765c707d3effca38b7_398.png)

![](img/ffd282b2d431f9765c707d3effca38b7_400.png)

![](img/ffd282b2d431f9765c707d3effca38b7_402.png)

![](img/ffd282b2d431f9765c707d3effca38b7_404.png)

![](img/ffd282b2d431f9765c707d3effca38b7_406.png)

![](img/ffd282b2d431f9765c707d3effca38b7_408.png)

为了实现更密集的关卡，我们减小了生成方块的尺寸，并增加了水平方向的“车道”数量。这使得屏幕上能同时出现更多、更小的方块群。

![](img/ffd282b2d431f9765c707d3effca38b7_410.png)

![](img/ffd282b2d431f9765c707d3effca38b7_411.png)

![](img/ffd282b2d431f9765c707d3effca38b7_413.png)

![](img/ffd282b2d431f9765c707d3effca38b7_415.png)

![](img/ffd282b2d431f9765c707d3effca38b7_417.png)

![](img/ffd282b2d431f9765c707d3effca38b7_419.png)

![](img/ffd282b2d431f9765c707d3effca38b7_420.png)

![](img/ffd282b2d431f9765c707d3effca38b7_422.png)

![](img/ffd282b2d431f9765c707d3effca38b7_423.png)

![](img/ffd282b2d431f9765c707d3effca38b7_425.png)

![](img/ffd282b2d431f9765c707d3effca38b7_427.png)

![](img/ffd282b2d431f9765c707d3effca38b7_429.png)

![](img/ffd282b2d431f9765c707d3effca38b7_430.png)

```c
// 调整方块大小和生成数量
float block_size = 1.5f; // 更小的尺寸
int num_lanes = (int)(20.0f / block_size); // 根据大小动态计算车道数，实现更密集的布局
```

![](img/ffd282b2d431f9765c707d3effca38b7_432.png)

![](img/ffd282b2d431f9765c707d3effca38b7_433.png)

![](img/ffd282b2d431f9765c707d3effca38b7_434.png)

![](img/ffd282b2d431f9765c707d3effca38b7_436.png)

![](img/ffd282b2d431f9765c707d3effca38b7_438.png)

![](img/ffd282b2d431f9765c707d3effca38b7_440.png)

![](img/ffd282b2d431f9765c707d3effca38b7_442.png)

![](img/ffd282b2d431f9765c707d3effca38b7_443.png)

![](img/ffd282b2d431f9765c707d3effca38b7_445.png)

![](img/ffd282b2d431f9765c707d3effca38b7_446.png)

![](img/ffd282b2d431f9765c707d3effca38b7_448.png)

![](img/ffd282b2d431f9765c707d3effca38b7_450.png)

![](img/ffd282b2d431f9765c707d3effca38b7_451.png)

![](img/ffd282b2d431f9765c707d3effca38b7_452.png)

![](img/ffd282b2d431f9765c707d3effca38b7_454.png)

![](img/ffd282b2d431f9765c707d3effca38b7_456.png)

![](img/ffd282b2d431f9765c707d3effca38b7_458.png)

![](img/ffd282b2d431f9765c707d3effca38b7_460.png)

![](img/ffd282b2d431f9765c707d3effca38b7_462.png)

通过这些修改，俄罗斯方块关卡现在包含大量小型方块群，它们会旋转、下落，并在被摧毁时可能产生连锁反应，极大地丰富了该模式的玩法。

![](img/ffd282b2d431f9765c707d3effca38b7_464.png)

![](img/ffd282b2d431f9765c707d3effca38b7_466.png)

![](img/ffd282b2d431f9765c707d3effca38b7_468.png)

![](img/ffd282b2d431f9765c707d3effca38b7_469.png)

![](img/ffd282b2d431f9765c707d3effca38b7_471.png)

![](img/ffd282b2d431f9765c707d3effca38b7_473.png)

![](img/ffd282b2d431f9765c707d3effca38b7_475.png)

![](img/ffd282b2d431f9765c707d3effca38b7_477.png)

![](img/ffd282b2d431f9765c707d3effca38b7_479.png)

![](img/ffd282b2d431f9765c707d3effca38b7_480.png)

---

![](img/ffd282b2d431f9765c707d3effca38b7_482.png)

![](img/ffd282b2d431f9765c707d3effca38b7_484.png)

![](img/ffd282b2d431f9765c707d3effca38b7_485.png)

![](img/ffd282b2d431f9765c707d3effca38b7_487.png)

![](img/ffd282b2d431f9765c707d3effca38b7_489.png)

![](img/ffd282b2d431f9765c707d3effca38b7_490.png)

![](img/ffd282b2d431f9765c707d3effca38b7_491.png)

![](img/ffd282b2d431f9765c707d3effca38b7_493.png)

![](img/ffd282b2d431f9765c707d3effca38b7_495.png)

![](img/ffd282b2d431f9765c707d3effca38b7_497.png)

![](img/ffd282b2d431f9765c707d3effca38b7_499.png)

![](img/ffd282b2d431f9765c707d3effca38b7_501.png)

![](img/ffd282b2d431f9765c707d3effca38b7_503.png)

![](img/ffd282b2d431f9765c707d3effca38b7_505.png)

## 设计关卡进度与阶段

![](img/ffd282b2d431f9765c707d3effca38b7_507.png)

![](img/ffd282b2d431f9765c707d3effca38b7_509.png)

![](img/ffd282b2d431f9765c707d3effca38b7_511.png)

![](img/ffd282b2d431f9765c707d3effca38b7_513.png)

![](img/ffd282b2d431f9765c707d3effca38b7_515.png)

![](img/ffd282b2d431f9765c707d3effca38b7_517.png)

![](img/ffd282b2d431f9765c707d3effca38b7_519.png)

![](img/ffd282b2d431f9765c707d3effca38b7_521.png)

![](img/ffd282b2d431f9765c707d3effca38b7_523.png)

![](img/ffd282b2d431f9765c707d3effca38b7_525.png)

![](img/ffd282b2d431f9765c707d3effca38b7_527.png)

上一节我们实现了更复杂的方块系统，本节我们来设计俄罗斯方块模式的关卡进度。我们不再使用固定的方块序列，而是设计了一个多阶段的进度系统：

![](img/ffd282b2d431f9765c707d3effca38b7_529.png)

![](img/ffd282b2d431f9765c707d3effca38b7_531.png)

![](img/ffd282b2d431f9765c707d3effca38b7_532.png)

![](img/ffd282b2d431f9765c707d3effca38b7_534.png)

![](img/ffd282b2d431f9765c707d3effca38b7_536.png)

![](img/ffd282b2d431f9765c707d3effca38b7_538.png)

![](img/ffd282b2d431f9765c707d3effca38b7_540.png)

![](img/ffd282b2d431f9765c707d3effca38b7_542.png)

![](img/ffd282b2d431f9765c707d3effca38b7_544.png)

![](img/ffd282b2d431f9765c707d3effca38b7_546.png)

![](img/ffd282b2d431f9765c707d3effca38b7_548.png)

![](img/ffd282b2d431f9765c707d3effca38b7_550.png)

![](img/ffd282b2d431f9765c707d3effca38b7_552.png)

![](img/ffd282b2d431f9765c707d3effca38b7_554.png)

![](img/ffd282b2d431f9765c707d3effca38b7_555.png)

![](img/ffd282b2d431f9765c707d3effca38b7_557.png)

![](img/ffd282b2d431f9765c707d3effca38b7_559.png)

![](img/ffd282b2d431f9765c707d3effca38b7_561.png)

![](img/ffd282b2d431f9765c707d3effca38b7_563.png)

以下是关卡进度状态的定义：

![](img/ffd282b2d431f9765c707d3effca38b7_565.png)

![](img/ffd282b2d431f9765c707d3effca38b7_567.png)

![](img/ffd282b2d431f9765c707d3effca38b7_569.png)

![](img/ffd282b2d431f9765c707d3effca38b7_570.png)

![](img/ffd282b2d431f9765c707d3effca38b7_572.png)

![](img/ffd282b2d431f9765c707d3effca38b7_574.png)

![](img/ffd282b2d431f9765c707d3effca38b7_576.png)

![](img/ffd282b2d431f9765c707d3effca38b7_578.png)

```c
typedef enum {
    LEVEL_PHASE_INITIAL,     // 初始阶段：生成少量大方块
    LEVEL_PHASE_SMALL_WAVE,  // 小型方块波次：生成大量小方块
    LEVEL_PHASE_ROTATING,    // 旋转阶段：生成会旋转的方块群
    LEVEL_PHASE_FINAL_CRAZY  // 最终疯狂阶段：混合所有类型，并增加道具
} LevelPhase;
```

![](img/ffd282b2d431f9765c707d3effca38b7_580.png)

![](img/ffd282b2d431f9765c707d3effca38b7_581.png)

![](img/ffd282b2d431f9765c707d3effca38b7_583.png)

![](img/ffd282b2d431f9765c707d3effca38b7_585.png)

![](img/ffd282b2d431f9765c707d3effca38b7_587.png)

![](img/ffd282b2d431f9765c707d3effca38b7_589.png)

![](img/ffd282b2d431f9765c707d3effca38b7_591.png)

![](img/ffd282b2d431f9765c707d3effca38b7_593.png)

![](img/ffd282b2d431f9765c707d3effca38b7_595.png)

![](img/ffd282b2d431f9765c707d3effca38b7_597.png)

![](img/ffd282b2d431f9765c707d3effca38b7_599.png)

![](img/ffd282b2d431f9765c707d3effca38b7_601.png)

![](img/ffd282b2d431f9765c707d3effca38b7_602.png)

![](img/ffd282b2d431f9765c707d3effca38b7_604.png)

![](img/ffd282b2d431f9765c707d3effca38b7_606.png)

![](img/ffd282b2d431f9765c707d3effca38b7_608.png)

![](img/ffd282b2d431f9765c707d3effca38b7_610.png)

![](img/ffd282b2d431f9765c707d3effca38b7_611.png)

![](img/ffd282b2d431f9765c707d3effca38b7_612.png)

![](img/ffd282b2d431f9765c707d3effca38b7_614.png)

![](img/ffd282b2d431f9765c707d3effca38b7_615.png)

关卡会根据玩家摧毁的方块数量或存活时间来推进阶段。每个阶段会改变方块的生成策略、大小、速度和旋转行为。例如，在最终阶段，我们会同时生成大型带道具的方块和大量高速旋转的小方块。

![](img/ffd282b2d431f9765c707d3effca38b7_617.png)

![](img/ffd282b2d431f9765c707d3effca38b7_619.png)

![](img/ffd282b2d431f9765c707d3effca38b7_621.png)

![](img/ffd282b2d431f9765c707d3effca38b7_623.png)

![](img/ffd282b2d431f9765c707d3effca38b7_625.png)

![](img/ffd282b2d431f9765c707d3effca38b7_627.png)

![](img/ffd282b2d431f9765c707d3effca38b7_628.png)

![](img/ffd282b2d431f9765c707d3effca38b7_630.png)

![](img/ffd282b2d431f9765c707d3effca38b7_632.png)

![](img/ffd282b2d431f9765c707d3effca38b7_634.png)

![](img/ffd282b2d431f9765c707d3effca38b7_636.png)

![](img/ffd282b2d431f9765c707d3effca38b7_638.png)

![](img/ffd282b2d431f9765c707d3effca38b7_640.png)

![](img/ffd282b2d431f9765c707d3effca38b7_642.png)

![](img/ffd282b2d431f9765c707d3effca38b7_644.png)

![](img/ffd282b2d431f9765c707d3effca38b7_646.png)

![](img/ffd282b2d431f9765c707d3effca38b7_647.png)

这种设计使得单次游戏体验充满变化，挑战性逐步提升。

![](img/ffd282b2d431f9765c707d3effca38b7_649.png)

![](img/ffd282b2d431f9765c707d3effca38b7_651.png)

![](img/ffd282b2d431f9765c707d3effca38b7_653.png)

![](img/ffd282b2d431f9765c707d3effca38b7_654.png)

![](img/ffd282b2d431f9765c707d3effca38b7_656.png)

![](img/ffd282b2d431f9765c707d3effca38b7_658.png)

![](img/ffd282b2d431f9765c707d3effca38b7_660.png)

![](img/ffd282b2d431f9765c707d3effca38b7_662.png)

![](img/ffd282b2d431f9765c707d3effca38b7_664.png)

![](img/ffd282b2d431f9765c707d3effca38b7_666.png)

![](img/ffd282b2d431f9765c707d3effca38b7_668.png)

![](img/ffd282b2d431f9765c707d3effca38b7_670.png)

![](img/ffd282b2d431f9765c707d3effca38b7_672.png)

![](img/ffd282b2d431f9765c707d3effca38b7_673.png)

![](img/ffd282b2d431f9765c707d3effca38b7_675.png)

---

![](img/ffd282b2d431f9765c707d3effca38b7_677.png)

![](img/ffd282b2d431f9765c707d3effca38b7_679.png)

![](img/ffd282b2d431f9765c707d3effca38b7_681.png)

![](img/ffd282b2d431f9765c707d3effca38b7_683.png)

![](img/ffd282b2d431f9765c707d3effca38b7_685.png)

![](img/ffd282b2d431f9765c707d3effca38b7_687.png)

## 实现动画关卡过渡

![](img/ffd282b2d431f9765c707d3effca38b7_689.png)

![](img/ffd282b2d431f9765c707d3effca38b7_691.png)

![](img/ffd282b2d431f9765c707d3effca38b7_693.png)

![](img/ffd282b2d431f9765c707d3effca38b7_694.png)

![](img/ffd282b2d431f9765c707d3effca38b7_696.png)

![](img/ffd282b2d431f9765c707d3effca38b7_697.png)

上一节我们设计了关卡的内部阶段，本节我们来实现游戏不同场景之间的动画过渡效果，这是本节课的核心目标。我们将为从菜单进入游戏和从游戏返回菜单添加平滑的动画。

![](img/ffd282b2d431f9765c707d3effca38b7_699.png)

![](img/ffd282b2d431f9765c707d3effca38b7_701.png)

![](img/ffd282b2d431f9765c707d3effca38b7_703.png)

首先，我们定义了一个全局的过渡状态：

![](img/ffd282b2d431f9765c707d3effca38b7_705.png)

![](img/ffd282b2d431f9765c707d3effca38b7_707.png)

![](img/ffd282b2d431f9765c707d3effca38b7_709.png)

![](img/ffd282b2d431f9765c707d3effca38b7_711.png)

![](img/ffd282b2d431f9765c707d3effca38b7_713.png)

![](img/ffd282b2d431f9765c707d3effca38b7_715.png)

![](img/ffd282b2d431f9765c707d3effca38b7_717.png)

![](img/ffd282b2d431f9765c707d3effca38b7_719.png)

```c
float level_transition_t; // 过渡时间因子，从1.0变化到0.0
bool is_in_transition;
```

![](img/ffd282b2d431f9765c707d3effca38b7_721.png)

![](img/ffd282b2d431f9765c707d3effca38b7_723.png)

![](img/ffd282b2d431f9765c707d3effca38b7_725.png)

![](img/ffd282b2d431f9765c707d3effca38b7_727.png)

![](img/ffd282b2d431f9765c707d3effca38b7_728.png)

![](img/ffd282b2d431f9765c707d3effca38b7_730.png)

![](img/ffd282b2d431f9765c707d3effca38b7_732.png)

![](img/ffd282b2d431f9765c707d3effca38b7_734.png)

![](img/ffd282b2d431f9765c707d3effca38b7_736.png)

![](img/ffd282b2d431f9765c707d3effca38b7_737.png)

![](img/ffd282b2d431f9765c707d3effca38b7_739.png)

**从菜单进入游戏的过渡**：
1.  当玩家从菜单选择“开始游戏”时，`level_transition_t` 设置为 `1.0`，并开始递减。
2.  在过渡期间，我们绘制一个覆盖全屏的黑色矩形，其透明度与 `level_transition_t` 关联，实现淡出效果。
3.  同时，游戏场景的墙壁和已存在的方块会从屏幕外动画移动进来。每个方块的Y轴位置都附加了一个基于其索引的偏移量，营造出依次落入的效果。

![](img/ffd282b2d431f9765c707d3effca38b7_741.png)

![](img/ffd282b2d431f9765c707d3effca38b7_743.png)

![](img/ffd282b2d431f9765c707d3effca38b7_745.png)

![](img/ffd282b2d431f9765c707d3effca38b7_747.png)

![](img/ffd282b2d431f9765c707d3effca38b7_749.png)

![](img/ffd282b2d431f9765c707d3effca38b7_751.png)

![](img/ffd282b2d431f9765c707d3effca38b7_752.png)

![](img/ffd282b2d431f9765c707d3effca38b7_754.png)

![](img/ffd282b2d431f9765c707d3effca38b7_756.png)

![](img/ffd282b2d431f9765c707d3effca38b7_758.png)

![](img/ffd282b2d431f9765c707d3effca38b7_759.png)

![](img/ffd282b2d431f9765c707d3effca38b7_760.png)

![](img/ffd282b2d431f9765c707d3effca38b7_761.png)

![](img/ffd282b2d431f9765c707d3effca38b7_763.png)

![](img/ffd282b2d431f9765c707d3effca38b7_765.png)

![](img/ffd282b2d431f9765c707d3effca38b7_767.png)

```c
// 绘制过渡中的方块（示例）
for (int i = 0; i < total_blocks; i++) {
    Block* block = &block_array[i];
    if (!block->is_active) continue;

    // 计算每个方块的独立过渡延迟
    float block_delay = (float)i / (float)total_blocks;
    float block_t = clamp(level_transition_t - block_delay, 0.0f, 1.0f);

    // 应用动画：方块从上方落下
    float anim_y_offset = (1.0f - block_t) * -100.0f; // 从-100像素落到0
    Vector2 draw_pos = {block->position.x, block->position.y + anim_y_offset};

    draw_block(block, draw_pos);
}
```

![](img/ffd282b2d431f9765c707d3effca38b7_769.png)

![](img/ffd282b2d431f9765c707d3effca38b7_771.png)

![](img/ffd282b2d431f9765c707d3effca38b7_773.png)

![](img/ffd282b2d431f9765c707d3effca38b7_775.png)

![](img/ffd282b2d431f9765c707d3effca38b7_776.png)

![](img/ffd282b2d431f9765c707d3effca38b7_778.png)

![](img/ffd282b2d431f9765c707d3effca38b7_780.png)

![](img/ffd282b2d431f9765c707d3effca38b7_782.png)

![](img/ffd282b2d431f9765c707d3effca38b7_784.png)

![](img/ffd282b2d431f9765c707d3effca38b7_785.png)

![](img/ffd282b2d431f9765c707d3effca38b7_787.png)

![](img/ffd282b2d431f9765c707d3effca38b7_789.png)

![](img/ffd282b2d431f9765c707d3effca38b7_791.png)

![](img/ffd282b2d431f9765c707d3effca38b7_793.png)

![](img/ffd282b2d431f9765c707d3effca38b7_795.png)

![](img/ffd282b2d431f9765c707d3effca38b7_797.png)

![](img/ffd282b2d431f9765c707d3effca38b7_798.png)

4.  我们为方块的“落地”添加了间隔播放的音效，增强了质感。
5.  当 `level_transition_t` 达到 `0.0` 时，过渡结束，游戏逻辑正式开始更新。

![](img/ffd282b2d431f9765c707d3effca38b7_800.png)

![](img/ffd282b2d431f9765c707d3effca38b7_802.png)

![](img/ffd282b2d431f9765c707d3effca38b7_804.png)

![](img/ffd282b2d431f9765c707d3effca38b7_806.png)

![](img/ffd282b2d431f9765c707d3effca38b7_808.png)

![](img/ffd282b2d431f9765c707d3effca38b7_810.png)

![](img/ffd282b2d431f9765c707d3effca38b7_812.png)

![](img/ffd282b2d431f9765c707d3effca38b7_814.png)

![](img/ffd282b2d431f9765c707d3effca38b7_816.png)

![](img/ffd282b2d431f9765c707d3effca38b7_818.png)

![](img/ffd282b2d431f9765c707d3effca38b7_819.png)

![](img/ffd282b2d431f9765c707d3effca38b7_821.png)

![](img/ffd282b2d431f9765c707d3effca38b7_823.png)

**从游戏返回菜单的过渡**：
这个过程与上述相反。菜单元素（如标题、选项）会以动画形式进入屏幕。我们使用了类似的动画原理，但方向相反，并且速度更快，以确保菜单的响应感。

![](img/ffd282b2d431f9765c707d3effca38b7_825.png)

![](img/ffd282b2d431f9765c707d3effca38b7_827.png)

![](img/ffd282b2d431f9765c707d3effca38b7_829.png)

![](img/ffd282b2d431f9765c707d3effca38b7_831.png)

![](img/ffd282b2d431f9765c707d3effca38b7_833.png)

![](img/ffd282b2d431f9765c707d3effca38b7_835.png)

![](img/ffd282b2d431f9765c707d3effca38b7_837.png)

![](img/ffd282b2d431f9765c707d3effca38b7_839.png)

![](img/ffd282b2d431f9765c707d3effca38b7_841.png)

![](img/ffd282b2d431f9765c707d3effca38b7_843.png)

![](img/ffd282b2d431f9765c707d3effca38b7_845.png)

---

![](img/ffd282b2d431f9765c707d3effca38b7_847.png)

![](img/ffd282b2d431f9765c707d3effca38b7_849.png)

![](img/ffd282b2d431f9765c707d3effca38b7_851.png)

![](img/ffd282b2d431f9765c707d3effca38b7_853.png)

![](img/ffd282b2d431f9765c707d3effca38b7_855.png)

![](img/ffd282b2d431f9765c707d3effca38b7_857.png)

![](img/ffd282b2d431f9765c707d3effca38b7_859.png)

![](img/ffd282b2d431f9765c707d3effca38b7_861.png)

![](img/ffd282b2d431f9765c707d3effca38b7_863.png)

![](img/ffd282b2d431f9765c707d3effca38b7_865.png)

![](img/ffd282b2d431f9765c707d3effca38b7_867.png)

![](img/ffd282b2d431f9765c707d3effca38b7_869.png)

## 性能优化：替换力场贴图

![](img/ffd282b2d431f9765c707d3effca38b7_871.png)

![](img/ffd282b2d431f9765c707d3effca38b7_873.png)

![](img/ffd282b2d431f9765c707d3effca38b7_875.png)

![](img/ffd282b2d431f9765c707d3effca38b7_877.png)

![](img/ffd282b2d431f9765c707d3effca38b7_879.png)

![](img/ffd282b2d431f9765c707d3effca38b7_880.png)

![](img/ffd282b2d431f9765c707d3effca38b7_881.png)

![](img/ffd282b2d431f9765c707d3effca38b7_882.png)

![](img/ffd282b2d431f9765c707d3effca38b7_884.png)

![](img/ffd282b2d431f9765c707d3effca38b7_886.png)

![](img/ffd282b2d431f9765c707d3effca38b7_888.png)

![](img/ffd282b2d431f9765c707d3effca38b7_890.png)

![](img/ffd282b2d431f9765c707d3effca38b7_892.png)

![](img/ffd282b2d431f9765c707d3effca38b7_894.png)

在实现动画的过程中，我们注意到之前使用的“力场”特效（一个旋转的透明纹理）在未优化的构建中消耗了大量性能（约11毫秒/帧）。

![](img/ffd282b2d431f9765c707d3effca38b7_896.png)

![](img/ffd282b2d431f9765c707d3effca38b7_898.png)

![](img/ffd282b2d431f9765c707d3effca38b7_900.png)

![](img/ffd282b2d431f9765c707d3effca38b7_902.png)

![](img/ffd282b2d431f9765c707d3effca38b7_904.png)

![](img/ffd282b2d431f9765c707d3effca38b7_905.png)

![](img/ffd282b2d431f9765c707d3effca38b7_907.png)

![](img/ffd282b2d431f9765c707d3effca38b7_908.png)

![](img/ffd282b2d431f9765c707d3effca38b7_910.png)

![](img/ffd282b2d431f9765c707d3effca38b7_912.png)

![](img/ffd282b2d431f9765c707d3effca38b7_914.png)

为了提升效率，我们移除了这个纹理文件，改用纯色绘制配合代码生成的条纹来模拟类似效果：

![](img/ffd282b2d431f9765c707d3effca38b7_916.png)

```c
// 用绘制矩形代替纹理绘制
float stripe_height = 10.0f;
int num_stripes = 5;
for (int s = 0; s < num_stripes; ++s) {
    float stripe_y = player_pos.y - (s * stripe_height);
    draw_rectangle((Rectangle){player_pos.x - 20, stripe_y, 40, stripe_height}, GREEN, alpha);
}
```

![](img/ffd282b2d431f9765c707d3effca38b7_918.png)

![](img/ffd282b2d431f9765c707d3effca38b7_920.png)

这项优化将相关渲染开销降低到了可忽略不计的水平，保证了即使在大量动画和特效下，游戏也能保持流畅运行。

![](img/ffd282b2d431f9765c707d3effca38b7_922.png)

![](img/ffd282b2d431f9765c707d3effca38b7_923.png)

![](img/ffd282b2d431f9765c707d3effca38b7_925.png)

![](img/ffd282b2d431f9765c707d3effca38b7_927.png)

![](img/ffd282b2d431f9765c707d3effca38b7_929.png)

![](img/ffd282b2d431f9765c707d3effca38b7_930.png)

![](img/ffd282b2d431f9765c707d3effca38b7_932.png)

![](img/ffd282b2d431f9765c707d3effca38b7_934.png)

![](img/ffd282b2d431f9765c707d3effca38b7_936.png)

![](img/ffd282b2d431f9765c707d3effca38b7_938.png)

![](img/ffd282b2d431f9765c707d3effca38b7_940.png)

![](img/ffd282b2d431f9765c707d3effca38b7_942.png)

![](img/ffd282b2d431f9765c707d3effca38b7_943.png)

![](img/ffd282b2d431f9765c707d3effca38b7_945.png)

![](img/ffd282b2d431f9765c707d3effca38b7_947.png)

---

![](img/ffd282b2d431f9765c707d3effca38b7_949.png)

## 总结

![](img/ffd282b2d431f9765c707d3effca38b7_951.png)

![](img/ffd282b2d431f9765c707d3effca38b7_953.png)

![](img/ffd282b2d431f9765c707d3effca38b7_955.png)

本节课中我们一起学习了如何为游戏添加关键的抛光层内容。

![](img/ffd282b2d431f9765c707d3effca38b7_957.png)

![](img/ffd282b2d431f9765c707d3effca38b7_959.png)

![](img/ffd282b2d431f9765c707d3effca38b7_961.png)

![](img/ffd282b2d431f9765c707d3effca38b7_963.png)

1.  **我们修复了游戏结束逻辑**，确保分数正确重置。
2.  **我们改进了俄罗斯方块模式**，引入了邻居系统、小型方块和多阶段关卡进度，使其玩法更具深度和变化。
3.  **我们成功实现了动画关卡过渡**，为菜单与游戏场景之间的切换添加了淡入淡出、元素滑入和音效，显著提升了游戏的流畅度和专业感。
4.  **我们进行了一项性能优化**，用程序化绘制替代了昂贵的纹理操作，确保了游戏的运行效率。

![](img/ffd282b2d431f9765c707d3effca38b7_965.png)

![](img/ffd282b2d431f9765c707d3effca38b7_967.png)

![](img/ffd282b2d431f9765c707d3effca38b7_969.png)

![](img/ffd282b2d431f9765c707d3effca38b7_971.png)

通过这些工作，我们的游戏在视觉反馈、音频体验和整体流程上都有了质的飞跃。在接下来的课程中，我们将着手处理资源加载优化（如Ogg音频解码和资源打包），为游戏的最终发布做准备。