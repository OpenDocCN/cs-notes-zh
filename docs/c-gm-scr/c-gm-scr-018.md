# 018：关卡设计与游戏玩法 🎮

![](img/f50787a48fc38bca0b94a2fc47cf7c96_1.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_3.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_5.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_7.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_8.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_10.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_12.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_14.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_16.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_18.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_19.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_21.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_23.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_25.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_27.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_29.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_31.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_33.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_35.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_37.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_39.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_41.png)

在本节课中，我们将学习如何为游戏设计一个新的关卡，特别是创建一个类似“俄罗斯方块”的游戏模式。我们将从零开始构建这个关卡，包括设计方块的生成、移动、旋转逻辑，以及如何与游戏的其他系统（如碰撞、得分、生命值）进行整合。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_43.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_45.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_47.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_49.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_51.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_53.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_55.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_57.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_59.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_61.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_63.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_65.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_67.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_68.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_70.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_72.png)

---

![](img/f50787a48fc38bca0b94a2fc47cf7c96_74.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_76.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_78.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_80.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_82.png)

## 概述

![](img/f50787a48fc38bca0b94a2fc47cf7c96_84.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_86.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_88.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_90.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_92.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_94.png)

上一节我们改进了游戏的音效和手感，并测试了各种增益/减益效果。本节中，我们将专注于创建一个全新的“俄罗斯方块”关卡。这个关卡的核心玩法是：各种形状的方块会从屏幕上方落下，玩家需要用球拍反弹小球来击碎这些方块。随着游戏进行，方块会旋转、加速，并带来新的挑战。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_96.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_97.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_99.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_101.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_103.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_105.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_107.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_109.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_111.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_113.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_115.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_116.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_118.png)

---

![](img/f50787a48fc38bca0b94a2fc47cf7c96_120.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_122.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_124.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_125.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_127.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_129.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_131.png)

## 关卡初始化与视觉设计

![](img/f50787a48fc38bca0b94a2fc47cf7c96_133.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_135.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_137.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_139.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_141.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_143.png)

首先，我们需要为新关卡设置一个独特的视觉风格。这包括背景颜色、方块颜色以及菜单文本颜色。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_145.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_147.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_149.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_151.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_153.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_154.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_156.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_158.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_160.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_162.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_164.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_166.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_168.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_170.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_172.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_174.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_176.png)

以下是初始化关卡颜色和菜单文本的代码片段：

![](img/f50787a48fc38bca0b94a2fc47cf7c96_178.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_180.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_182.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_184.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_186.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_188.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_190.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_192.png)

```c
// 设置俄罗斯方块关卡的背景色和方块颜色
level_state.tetris.background_color = 0xAD0BD9E0;
level_state.tetris.block_color = 0x89898989;

![](img/f50787a48fc38bca0b94a2fc47cf7c96_194.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_196.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_198.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_200.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_202.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_204.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_206.png)

// 在菜单中添加该关卡的文本项
menu_add_item(&game_state.menu, "Tetris", ...);
```

![](img/f50787a48fc38bca0b94a2fc47cf7c96_208.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_210.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_212.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_214.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_216.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_218.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_220.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_222.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_224.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_226.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_228.png)

我们从一个配色网站选取了鲜艳的颜色组合，以营造“俄罗斯方块”经典、多彩的氛围。背景使用较深的紫色，而方块则使用一系列随机生成的明亮颜色。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_230.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_232.png)

---

![](img/f50787a48fc38bca0b94a2fc47cf7c96_234.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_236.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_238.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_240.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_242.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_244.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_245.png)

## 方块形状的生成与渲染

![](img/f50787a48fc38bca0b94a2fc47cf7c96_247.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_248.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_250.png)

俄罗斯方块的核心是各种形状的“方块组”。我们需要定义这些形状，并能够将它们渲染到屏幕上。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_252.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_254.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_256.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_258.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_260.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_262.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_264.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_266.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_268.png)

以下是定义和生成方块形状的步骤：

![](img/f50787a48fc38bca0b94a2fc47cf7c96_270.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_272.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_274.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_276.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_278.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_280.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_282.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_284.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_286.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_288.png)

1.  **定义形状数据**：我们使用一个3x3的布尔矩阵来定义每个形状。`1` 表示该位置有方块，`0` 表示没有。
    ```c
    // 例如，“L”形和方形
    bool shape_L[3][3] = {{1,0,0}, {1,0,0}, {1,1,0}};
    bool shape_square[3][3] = {{1,1,0}, {1,1,0}, {0,0,0}};
    ```

![](img/f50787a48fc38bca0b94a2fc47cf7c96_290.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_292.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_294.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_296.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_298.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_300.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_302.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_304.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_306.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_308.png)

2.  **生成方块**：根据形状数据，在指定位置生成对应的游戏方块实体。
    ```c
    void spawn_tetris_shape(int shape_index, V2 spawn_position) {
        bool (*shape)[3] = tetris_shapes[shape_index];
        for (int y = 0; y < 3; y++) {
            for (int x = 0; x < 3; x++) {
                if (shape[y][x]) {
                    Block* block = get_next_available_block();
                    block->position = spawn_position + (V2){x * (block_size*2 + spacing), y * (block_size*2 + spacing)};
                    block->color = get_random_bright_color();
                    block->parent_p = &level_state.tetris.enemy_p; // 关联到关卡状态
                }
            }
        }
    }
    ```

![](img/f50787a48fc38bca0b94a2fc47cf7c96_310.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_312.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_314.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_316.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_318.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_320.png)

3.  **随机颜色**：为了让关卡更生动，每个方块组使用随机但明亮的颜色。
    ```c
    Color get_random_bright_color() {
        int r = 100 + rand() % 156;
        int g = 100 + rand() % 156;
        int b = 100 + rand() % 156;
        return (Color){r, g, b, 255};
    }
    ```

![](img/f50787a48fc38bca0b94a2fc47cf7c96_322.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_324.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_326.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_328.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_329.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_331.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_333.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_335.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_337.png)

---

![](img/f50787a48fc38bca0b94a2fc47cf7c96_339.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_341.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_343.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_345.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_347.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_349.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_351.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_353.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_355.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_357.png)

## 方块的移动与速度控制

![](img/f50787a48fc38bca0b94a2fc47cf7c96_359.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_361.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_363.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_365.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_367.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_369.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_371.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_373.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_375.png)

方块需要从屏幕顶部向下移动。我们设计了一个速度系统，让方块在屏幕顶部移动较快，接近底部时变慢，以增加游戏的可玩性和策略深度。

以下是控制方块移动速度的逻辑：

![](img/f50787a48fc38bca0b94a2fc47cf7c96_377.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_379.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_381.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_383.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_385.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_387.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_389.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_391.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_393.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_395.png)

```c
void simulate_tetris_level() {
    for (int i = 0; i < level_state.tetris.shapes_spawned; i++) {
        V2* shape_p = &level_state.tetris.enemy_p[i];
        // 速度基于方块在屏幕上的Y轴位置计算
        // 位置越高（值越小），速度越快；位置越低（值越大），速度越慢
        float speed_factor = 65.0f - (shape_p->y / arena.half_size.y) * 30.0f;
        speed_factor = clamp(speed_factor, 10.0f, 65.0f); // 限制速度范围
        shape_p->y += speed_factor * global_dt;
    }
}
```

![](img/f50787a48fc38bca0b94a2fc47cf7c96_397.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_399.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_401.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_403.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_405.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_407.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_409.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_411.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_413.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_415.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_417.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_419.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_421.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_423.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_425.png)

这个公式 `65.0f - (y_position / screen_height) * 30.0f` 确保了速度从顶部的约65单位/秒平滑地减少到底部的约35单位/秒。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_427.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_429.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_431.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_433.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_435.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_437.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_439.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_441.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_443.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_445.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_447.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_449.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_451.png)

---

![](img/f50787a48fc38bca0b94a2fc47cf7c96_453.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_455.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_457.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_459.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_461.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_463.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_464.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_466.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_468.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_470.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_472.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_474.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_476.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_478.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_480.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_482.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_484.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_486.png)

## 游戏逻辑与关卡流程

![](img/f50787a48fc38bca0b94a2fc47cf7c96_488.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_490.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_492.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_494.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_496.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_498.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_500.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_502.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_504.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_506.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_508.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_510.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_511.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_513.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_514.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_516.png)

一个完整的关卡需要有开始、进行、胜利/失败的条件。我们设计了多波次的方块生成，并引入了旋转和增益/减益效果来增加难度和趣味性。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_518.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_520.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_522.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_524.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_526.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_528.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_530.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_532.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_534.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_536.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_538.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_540.png)

以下是关卡流程的控制逻辑：

![](img/f50787a48fc38bca0b94a2fc47cf7c96_542.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_544.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_546.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_547.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_549.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_551.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_553.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_555.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_557.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_559.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_561.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_563.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_565.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_567.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_569.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_571.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_573.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_575.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_577.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_579.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_581.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_583.png)

1.  **波次生成**：关卡分为多个波次。当玩家摧毁一个方块组后，会生成新的方块组。
    ```c
    if (blocks_destroyed_in_current_wave >= blocks_in_wave) {
        spawn_tetris_shape(get_random_shape_index(), get_random_lane_x());
        level_state.tetris.current_wave++;
    }
    ```

![](img/f50787a48fc38bca0b94a2fc47cf7c96_585.png)

2.  **旋转方块**：在后面的波次中，方块组会开始旋转，增加挑战性。
    ```c
    if (level_state.tetris.current_wave >= 2) {
        // 每2秒旋转一次
        level_state.tetris.rotation_timer += dt;
        if (level_state.tetris.rotation_timer >= 2.0f) {
            rotate_tetris_shapes(level_state.tetris.current_wave);
            level_state.tetris.rotation_timer = 0.0f;
        }
    }
    ```

![](img/f50787a48fc38bca0b94a2fc47cf7c96_587.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_589.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_591.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_593.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_595.png)

3.  **增益/减益效果**：从第二波开始，方块被击碎后有概率掉落减益效果（如使球拍变小、球速变慢），迫使玩家谨慎选择击打目标。
4.  **失败条件**：如果任何一个方块落到屏幕底部以下，玩家将失去一条生命。
    ```c
    if (block->position.y + block->half_size.y >= player.paddle.position.y) {
        lose_life();
    }
    ```

![](img/f50787a48fc38bca0b94a2fc47cf7c96_597.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_599.png)

---

![](img/f50787a48fc38bca0b94a2fc47cf7c96_601.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_603.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_605.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_607.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_609.png)

## 代码优化与渲染改进

![](img/f50787a48fc38bca0b94a2fc47cf7c96_611.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_613.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_615.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_617.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_618.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_620.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_622.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_624.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_626.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_628.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_630.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_632.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_634.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_636.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_637.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_638.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_640.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_642.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_643.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_645.png)

在开发过程中，我们也对代码结构和渲染效果进行了优化。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_647.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_649.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_651.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_653.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_655.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_657.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_659.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_661.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_663.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_665.png)

1.  **父级指针系统**：我们为方块实体添加了一个 `parent_p` 指针，指向其所属的“形状组”的位置。这样，只需更新父级位置，所有关联方块的位置会自动更新，简化了移动和旋转的逻辑。
    ```c
    typedef struct Block {
        V2 position;
        V2 half_size;
        Color color;
        V2* parent_p; // 指向所属形状组的坐标
        // ... 其他属性
    } Block;
    ```

![](img/f50787a48fc38bca0b94a2fc47cf7c96_667.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_669.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_671.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_673.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_675.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_677.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_679.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_681.png)

2.  **子像素精确渲染**：为了让移动看起来更平滑，特别是对于移动较慢的物体，我们为方块和小球实现了子像素精确渲染。
    ```c
    void draw_rect_smooth(V2 p, V2 half_size, Color color) {
        // 使用浮点数坐标进行渲染计算，实现平滑移动
        int pixel_x = (int)(p.x * subpixel_factor);
        int pixel_y = (int)(p.y * subpixel_factor);
        // ... 实际像素绘制逻辑
    }
    ```

![](img/f50787a48fc38bca0b94a2fc47cf7c96_683.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_685.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_687.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_689.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_691.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_693.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_695.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_697.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_699.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_701.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_703.png)

---

![](img/f50787a48fc38bca0b94a2fc47cf7c96_705.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_707.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_709.png)

## 总结

![](img/f50787a48fc38bca0b94a2fc47cf7c96_711.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_713.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_714.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_716.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_718.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_719.png)

本节课中，我们一起为游戏创建了一个全新的“俄罗斯方块”主题关卡。我们从视觉设计开始，定义了方块的形状和颜色。然后，我们实现了方块的生成、基于位置的动态速度控制以及多波次的游戏流程。为了增加挑战，我们加入了方块旋转和减益效果。最后，我们通过引入父级指针系统和子像素渲染优化了代码结构和视觉表现。

![](img/f50787a48fc38bca0b94a2fc47cf7c96_721.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_723.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_725.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_727.png)

![](img/f50787a48fc38bca0b94a2fc47cf7c96_729.png)

这个关卡将经典的“打砖块”与“俄罗斯方块”的下落玩法相结合，创造了独特的游戏体验。在下一节课中，我们将修复当前存在的碰撞检测问题，并可能为这个关卡添加更多视觉特效和玩法微调。