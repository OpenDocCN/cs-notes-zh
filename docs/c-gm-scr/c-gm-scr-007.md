# 007：为游戏增添“果汁” 🎮

![](img/06038cb1cd219389e961b5d06c0686c3_1.png)

![](img/06038cb1cd219389e961b5d06c0686c3_3.png)

![](img/06038cb1cd219389e961b5d06c0686c3_5.png)

![](img/06038cb1cd219389e961b5d06c0686c3_7.png)

![](img/06038cb1cd219389e961b5d06c0686c3_9.png)

在本节课中，我们将学习如何为游戏增添“果汁”，即通过调整视觉效果、动画和物理反馈来提升游戏的“手感”和互动体验。我们将从为玩家挡板添加弹性动画和拖尾效果开始，让游戏变得更加生动有趣。

![](img/06038cb1cd219389e961b5d06c0686c3_11.png)

![](img/06038cb1cd219389e961b5d06c0686c3_13.png)

![](img/06038cb1cd219389e961b5d06c0686c3_15.png)

---

![](img/06038cb1cd219389e961b5d06c0686c3_17.png)

![](img/06038cb1cd219389e961b5d06c0686c3_19.png)

![](img/06038cb1cd219389e961b5d06c0686c3_21.png)

![](img/06038cb1cd219389e961b5d06c0686c3_23.png)

![](img/06038cb1cd219389e961b5d06c0686c3_25.png)

![](img/06038cb1cd219389e961b5d06c0686c3_27.png)

![](img/06038cb1cd219389e961b5d06c0686c3_29.png)

## 概述

![](img/06038cb1cd219389e961b5d06c0686c3_31.png)

![](img/06038cb1cd219389e961b5d06c0686c3_33.png)

![](img/06038cb1cd219389e961b5d06c0686c3_35.png)

上一节我们清理了游戏玩法，使其更具凝聚力。本节我们将专注于提升游戏的“感觉”，通过添加视觉反馈和动态效果，让游戏互动起来更加流畅和令人满意。

![](img/06038cb1cd219389e961b5d06c0686c3_37.png)

![](img/06038cb1cd219389e961b5d06c0686c3_39.png)

![](img/06038cb1cd219389e961b5d06c0686c3_41.png)

![](img/06038cb1cd219389e961b5d06c0686c3_43.png)

![](img/06038cb1cd219389e961b5d06c0686c3_44.png)

![](img/06038cb1cd219389e961b5d06c0686c3_46.png)

![](img/06038cb1cd219389e961b5d06c0686c3_47.png)

![](img/06038cb1cd219389e961b5d06c0686c3_49.png)

![](img/06038cb1cd219389e961b5d06c0686c3_51.png)

![](img/06038cb1cd219389e961b5d06c0686c3_52.png)

![](img/06038cb1cd219389e961b5d06c0686c3_54.png)

![](img/06038cb1cd219389e961b5d06c0686c3_55.png)

![](img/06038cb1cd219389e961b5d06c0686c3_57.png)

![](img/06038cb1cd219389e961b5d06c0686c3_59.png)

我们将实现以下内容：
1.  为玩家挡板添加基于弹簧物理的挤压拉伸动画。
2.  为球体添加带有淡出效果的拖尾。
3.  实现可移动、有弹性的墙壁碰撞效果。
4.  根据球的状态改变其颜色。

![](img/06038cb1cd219389e961b5d06c0686c3_61.png)

![](img/06038cb1cd219389e961b5d06c0686c3_63.png)

![](img/06038cb1cd219389e961b5d06c0686c3_65.png)

![](img/06038cb1cd219389e961b5d06c0686c3_67.png)

![](img/06038cb1cd219389e961b5d06c0686c3_68.png)

![](img/06038cb1cd219389e961b5d06c0686c3_70.png)

![](img/06038cb1cd219389e961b5d06c0686c3_72.png)

---

![](img/06038cb1cd219389e961b5d06c0686c3_74.png)

![](img/06038cb1cd219389e961b5d06c0686c3_76.png)

![](img/06038cb1cd219389e961b5d06c0686c3_78.png)

![](img/06038cb1cd219389e961b5d06c0686c3_80.png)

![](img/06038cb1cd219389e961b5d06c0686c3_82.png)

![](img/06038cb1cd219389e961b5d06c0686c3_84.png)

![](img/06038cb1cd219389e961b5d06c0686c3_85.png)

![](img/06038cb1cd219389e961b5d06c0686c3_87.png)

![](img/06038cb1cd219389e961b5d06c0686c3_89.png)

![](img/06038cb1cd219389e961b5d06c0686c3_91.png)

![](img/06038cb1cd219389e961b5d06c0686c3_93.png)

![](img/06038cb1cd219389e961b5d06c0686c3_95.png)

![](img/06038cb1cd219389e961b5d06c0686c3_97.png)

![](img/06038cb1cd219389e961b5d06c0686c3_99.png)

![](img/06038cb1cd219389e961b5d06c0686c3_101.png)

## 为玩家挡板添加弹簧动画 🏓

![](img/06038cb1cd219389e961b5d06c0686c3_103.png)

![](img/06038cb1cd219389e961b5d06c0686c3_105.png)

![](img/06038cb1cd219389e961b5d06c0686c3_107.png)

![](img/06038cb1cd219389e961b5d06c0686c3_108.png)

![](img/06038cb1cd219389e961b5d06c0686c3_110.png)

![](img/06038cb1cd219389e961b5d06c0686c3_112.png)

![](img/06038cb1cd219389e961b5d06c0686c3_114.png)

![](img/06038cb1cd219389e961b5d06c0686c3_116.png)

![](img/06038cb1cd219389e961b5d06c0686c3_118.png)

首先，我们希望玩家挡板的移动更加生动，而不是僵硬地跟随鼠标。我们将实现一个简单的弹簧系统，让挡板的视觉位置平滑地“追赶”目标位置（即鼠标位置）。

![](img/06038cb1cd219389e961b5d06c0686c3_120.png)

![](img/06038cb1cd219389e961b5d06c0686c3_122.png)

### 核心概念与代码

![](img/06038cb1cd219389e961b5d06c0686c3_124.png)

![](img/06038cb1cd219389e961b5d06c0686c3_126.png)

![](img/06038cb1cd219389e961b5d06c0686c3_128.png)

![](img/06038cb1cd219389e961b5d06c0686c3_130.png)

![](img/06038cb1cd219389e961b5d06c0686c3_132.png)

![](img/06038cb1cd219389e961b5d06c0686c3_134.png)

![](img/06038cb1cd219389e961b5d06c0686c3_136.png)

![](img/06038cb1cd219389e961b5d06c0686c3_138.png)

![](img/06038cb1cd219389e961b5d06c0686c3_140.png)

![](img/06038cb1cd219389e961b5d06c0686c3_142.png)

![](img/06038cb1cd219389e961b5d06c0686c3_144.png)

我们引入两个新变量来代表挡板的视觉状态：
*   `player_visual_p`: 挡板当前的渲染位置。
*   `player_visual_dp`: 挡板当前的速度。

在每帧更新中，我们使用弹簧物理公式来计算视觉位置的变化：

![](img/06038cb1cd219389e961b5d06c0686c3_146.png)

![](img/06038cb1cd219389e961b5d06c0686c3_148.png)

![](img/06038cb1cd219389e961b5d06c0686c3_150.png)

![](img/06038cb1cd219389e961b5d06c0686c3_152.png)

![](img/06038cb1cd219389e961b5d06c0686c3_154.png)

![](img/06038cb1cd219389e961b5d06c0686c3_156.png)

![](img/06038cb1cd219389e961b5d06c0686c3_158.png)

![](img/06038cb1cd219389e961b5d06c0686c3_160.png)

```c
// 计算朝向目标位置（player_desired_p）的加速度
v2 spring_acceleration = (player_desired_p - player_visual_p) * spring_stiffness;
// 计算阻尼力（与当前速度方向相反）
v2 damping_force = -player_visual_dp * damping_coefficient;

![](img/06038cb1cd219389e961b5d06c0686c3_162.png)

![](img/06038cb1cd219389e961b5d06c0686c3_164.png)

![](img/06038cb1cd219389e961b5d06c0686c3_166.png)

![](img/06038cb1cd219389e961b5d06c0686c3_168.png)

// 合力
v2 total_acceleration = spring_acceleration + damping_force;

![](img/06038cb1cd219389e961b5d06c0686c3_170.png)

![](img/06038cb1cd219389e961b5d06c0686c3_172.png)

![](img/06038cb1cd219389e961b5d06c0686c3_174.png)

![](img/06038cb1cd219389e961b5d06c0686c3_176.png)

![](img/06038cb1cd219389e961b5d06c0686c3_178.png)

![](img/06038cb1cd219389e961b5d06c0686c3_180.png)

![](img/06038cb1cd219389e961b5d06c0686c3_182.png)

![](img/06038cb1cd219389e961b5d06c0686c3_184.png)

![](img/06038cb1cd219389e961b5d06c0686c3_186.png)

![](img/06038cb1cd219389e961b5d06c0686c3_188.png)

![](img/06038cb1cd219389e961b5d06c0686c3_190.png)

![](img/06038cb1cd219389e961b5d06c0686c3_192.png)

![](img/06038cb1cd219389e961b5d06c0686c3_194.png)

![](img/06038cb1cd219389e961b5d06c0686c3_196.png)

![](img/06038cb1cd219389e961b5d06c0686c3_198.png)

![](img/06038cb1cd219389e961b5d06c0686c3_200.png)

// 更新速度 (v = v0 + a * dt)
player_visual_dp += total_acceleration * dt;

![](img/06038cb1cd219389e961b5d06c0686c3_201.png)

![](img/06038cb1cd219389e961b5d06c0686c3_203.png)

![](img/06038cb1cd219389e961b5d06c0686c3_205.png)

![](img/06038cb1cd219389e961b5d06c0686c3_207.png)

![](img/06038cb1cd219389e961b5d06c0686c3_209.png)

![](img/06038cb1cd219389e961b5d06c0686c3_211.png)

![](img/06038cb1cd219389e961b5d06c0686c3_213.png)

![](img/06038cb1cd219389e961b5d06c0686c3_215.png)

![](img/06038cb1cd219389e961b5d06c0686c3_217.png)

![](img/06038cb1cd219389e961b5d06c0686c3_219.png)

![](img/06038cb1cd219389e961b5d06c0686c3_221.png)

![](img/06038cb1cd219389e961b5d06c0686c3_223.png)

![](img/06038cb1cd219389e961b5d06c0686c3_225.png)

![](img/06038cb1cd219389e961b5d06c0686c3_227.png)

![](img/06038cb1cd219389e961b5d06c0686c3_229.png)

// 更新位置 (p = p0 + v * dt)
player_visual_p += player_visual_dp * dt;
```

![](img/06038cb1cd219389e961b5d06c0686c3_231.png)

![](img/06038cb1cd219389e961b5d06c0686c3_233.png)

![](img/06038cb1cd219389e961b5d06c0686c3_235.png)

![](img/06038cb1cd219389e961b5d06c0686c3_237.png)

![](img/06038cb1cd219389e961b5d06c0686c3_239.png)

![](img/06038cb1cd219389e961b5d06c0686c3_241.png)

![](img/06038cb1cd219389e961b5d06c0686c3_243.png)

通过调整 `spring_stiffness`（弹簧刚度）和 `damping_coefficient`（阻尼系数），我们可以获得从松软到紧绷的不同手感。

![](img/06038cb1cd219389e961b5d06c0686c3_245.png)

### 实现挤压拉伸

![](img/06038cb1cd219389e961b5d06c0686c3_247.png)

![](img/06038cb1cd219389e961b5d06c0686c3_249.png)

![](img/06038cb1cd219389e961b5d06c0686c3_251.png)

为了让挡板在撞墙时更有冲击感，我们根据其与墙壁的“挤压”程度来动态调整其高度（Y轴大小）。

![](img/06038cb1cd219389e961b5d06c0686c3_253.png)

![](img/06038cb1cd219389e961b5d06c0686c3_255.png)

![](img/06038cb1cd219389e961b5d06c0686c3_257.png)

![](img/06038cb1cd219389e961b5d06c0686c3_259.png)

![](img/06038cb1cd219389e961b5d06c0686c3_261.png)

![](img/06038cb1cd219389e961b5d06c0686c3_263.png)

![](img/06038cb1cd219389e961b5d06c0686c3_265.png)

![](img/06038cb1cd219389e961b5d06c0686c3_267.png)

![](img/06038cb1cd219389e961b5d06c0686c3_269.png)

![](img/06038cb1cd219389e961b5d06c0686c3_271.png)

![](img/06038cb1cd219389e961b5d06c0686c3_273.png)

![](img/06038cb1cd219389e961b5d06c0686c3_275.png)

![](img/06038cb1cd219389e961b5d06c0686c3_277.png)

以下是计算挤压因子并调整大小的逻辑：

![](img/06038cb1cd219389e961b5d06c0686c3_279.png)

![](img/06038cb1cd219389e961b5d06c0686c3_281.png)

![](img/06038cb1cd219389e961b5d06c0686c3_283.png)

![](img/06038cb1cd219389e961b5d06c0686c3_285.png)

![](img/06038cb1cd219389e961b5d06c0686c3_287.png)

![](img/06038cb1cd219389e961b5d06c0686c3_288.png)

![](img/06038cb1cd219389e961b5d06c0686c3_290.png)

![](img/06038cb1cd219389e961b5d06c0686c3_291.png)

![](img/06038cb1cd219389e961b5d06c0686c3_292.png)

![](img/06038cb1cd219389e961b5d06c0686c3_294.png)

![](img/06038cb1cd219389e961b5d06c0686c3_296.png)

![](img/06038cb1cd219389e961b5d06c0686c3_298.png)

![](img/06038cb1cd219389e961b5d06c0686c3_300.png)

![](img/06038cb1cd219389e961b5d06c0686c3_302.png)

```c
// 计算挡板右侧与墙壁右侧的“挤压”距离
f32 squeeze_distance = (player_visual_p.x + player_half_size.x) - arena_right_wall_p;
f32 squeeze_factor = 0.0f;

![](img/06038cb1cd219389e961b5d06c0686c3_304.png)

![](img/06038cb1cd219389e961b5d06c0686c3_306.png)

![](img/06038cb1cd219389e961b5d06c0686c3_308.png)

![](img/06038cb1cd219389e961b5d06c0686c3_310.png)

![](img/06038cb1cd219389e961b5d06c0686c3_312.png)

![](img/06038cb1cd219389e961b5d06c0686c3_314.png)

![](img/06038cb1cd219389e961b5d06c0686c3_316.png)

![](img/06038cb1cd219389e961b5d06c0686c3_318.png)

![](img/06038cb1cd219389e961b5d06c0686c3_320.png)

![](img/06038cb1cd219389e961b5d06c0686c3_322.png)

if (squeeze_distance > 0.0f) {
    // 如果挤入墙壁，计算挤压因子
    squeeze_factor = squeeze_distance;
    // 同时将挡板位置推回，避免穿透
    player_desired_p.x -= squeeze_factor;
}

![](img/06038cb1cd219389e961b5d06c0686c3_324.png)

![](img/06038cb1cd219389e961b5d06c0686c3_326.png)

![](img/06038cb1cd219389e961b5d06c0686c3_328.png)

![](img/06038cb1cd219389e961b5d06c0686c3_330.png)

![](img/06038cb1cd219389e961b5d06c0686c3_332.png)

![](img/06038cb1cd219389e961b5d06c0686c3_334.png)

![](img/06038cb1cd219389e961b5d06c0686c3_335.png)

![](img/06038cb1cd219389e961b5d06c0686c3_337.png)

![](img/06038cb1cd219389e961b5d06c0686c3_338.png)

// 根据挤压因子调整挡板高度：挤压时变矮，拉伸时变高
player_half_size.y = base_height - fabsf(player_visual_dp.x) * scale_factor + squeeze_factor * squash_intensity;
```

![](img/06038cb1cd219389e961b5d06c0686c3_340.png)

![](img/06038cb1cd219389e961b5d06c0686c3_342.png)

![](img/06038cb1cd219389e961b5d06c0686c3_344.png)

![](img/06038cb1cd219389e961b5d06c0686c3_346.png)

![](img/06038cb1cd219389e961b5d06c0686c3_348.png)

![](img/06038cb1cd219389e961b5d06c0686c3_350.png)

![](img/06038cb1cd219389e961b5d06c0686c3_352.png)

![](img/06038cb1cd219389e961b5d06c0686c3_354.png)

![](img/06038cb1cd219389e961b5d06c0686c3_356.png)

---

![](img/06038cb1cd219389e961b5d06c0686c3_358.png)

![](img/06038cb1cd219389e961b5d06c0686c3_360.png)

![](img/06038cb1cd219389e961b5d06c0686c3_361.png)

![](img/06038cb1cd219389e961b5d06c0686c3_363.png)

![](img/06038cb1cd219389e961b5d06c0686c3_365.png)

![](img/06038cb1cd219389e961b5d06c0686c3_367.png)

![](img/06038cb1cd219389e961b5d06c0686c3_369.png)

![](img/06038cb1cd219389e961b5d06c0686c3_371.png)

![](img/06038cb1cd219389e961b5d06c0686c3_372.png)

![](img/06038cb1cd219389e961b5d06c0686c3_374.png)

## 为球体添加拖尾效果 🌈

![](img/06038cb1cd219389e961b5d06c0686c3_376.png)

![](img/06038cb1cd219389e961b5d06c0686c3_378.png)

接下来，我们为移动的球体添加视觉拖尾，以增强其速度感和轨迹可见性。

![](img/06038cb1cd219389e961b5d06c0686c3_380.png)

![](img/06038cb1cd219389e961b5d06c0686c3_382.png)

![](img/06038cb1cd219389e961b5d06c0686c3_384.png)

![](img/06038cb1cd219389e961b5d06c0686c3_386.png)

![](img/06038cb1cd219389e961b5d06c0686c3_388.png)

![](img/06038cb1cd219389e961b5d06c0686c3_390.png)

![](img/06038cb1cd219389e961b5d06c0686c3_392.png)

![](img/06038cb1cd219389e961b5d06c0686c3_394.png)

![](img/06038cb1cd219389e961b5d06c0686c3_396.png)

### 实现思路

![](img/06038cb1cd219389e961b5d06c0686c3_398.png)

![](img/06038cb1cd219389e961b5d06c0686c3_400.png)

![](img/06038cb1cd219389e961b5d06c0686c3_402.png)

![](img/06038cb1cd219389e961b5d06c0686c3_404.png)

![](img/06038cb1cd219389e961b5d06c0686c3_406.png)

![](img/06038cb1cd219389e961b5d06c0686c3_408.png)

![](img/06038cb1cd219389e961b5d06c0686c3_410.png)

我们为每个球体维护一个固定大小的轨迹点数组，构成一个环形缓冲区。在球体移动过程中，每隔固定时间间隔（而非每帧）在当前位置添加一个新的轨迹点。每个轨迹点拥有一个生命周期，随着时间递减。渲染时，我们根据轨迹点的生命周期设置其透明度（生命周期越长，越不透明），从而实现淡出效果。

![](img/06038cb1cd219389e961b5d06c0686c3_412.png)

![](img/06038cb1cd219389e961b5d06c0686c3_414.png)

![](img/06038cb1cd219389e961b5d06c0686c3_416.png)

![](img/06038cb1cd219389e961b5d06c0686c3_418.png)

![](img/06038cb1cd219389e961b5d06c0686c3_420.png)

![](img/06038cb1cd219389e961b5d06c0686c3_422.png)

![](img/06038cb1cd219389e961b5d06c0686c3_424.png)

以下是添加和更新轨迹的核心代码结构：

![](img/06038cb1cd219389e961b5d06c0686c3_426.png)

![](img/06038cb1cd219389e961b5d06c0686c3_428.png)

![](img/06038cb1cd219389e961b5d06c0686c3_430.png)

![](img/06038cb1cd219389e961b5d06c0686c3_432.png)

![](img/06038cb1cd219389e961b5d06c0686c3_434.png)

![](img/06038cb1cd219389e961b5d06c0686c3_436.png)

![](img/06038cb1cd219389e961b5d06c0686c3_438.png)

![](img/06038cb1cd219389e961b5d06c0686c3_440.png)

![](img/06038cb1cd219389e961b5d06c0686c3_442.png)

![](img/06038cb1cd219389e961b5d06c0686c3_444.png)

![](img/06038cb1cd219389e961b5d06c0686c3_446.png)

```c
// 定义轨迹点结构
typedef struct {
    v2 p;
    f32 life;
    u32 color;
} trail_point;

![](img/06038cb1cd219389e961b5d06c0686c3_448.png)

![](img/06038cb1cd219389e961b5d06c0686c3_449.png)

![](img/06038cb1cd219389e961b5d06c0686c3_451.png)

![](img/06038cb1cd219389e961b5d06c0686c3_453.png)

![](img/06038cb1cd219389e961b5d06c0686c3_455.png)

![](img/06038cb1cd219389e961b5d06c0686c3_457.png)

![](img/06038cb1cd219389e961b5d06c0686c3_459.png)

![](img/06038cb1cd219389e961b5d06c0686c3_461.png)

![](img/06038cb1cd219389e961b5d06c0686c3_463.png)

![](img/06038cb1cd219389e961b5d06c0686c3_465.png)

![](img/06038cb1cd219389e961b5d06c0686c3_466.png)

// 在球体更新中，计时并添加新轨迹点
ball->trail_timer -= dt;
if (ball->trail_timer <= 0.0f) {
    ball->trail_timer = trail_spawn_interval; // 重置计时器

    trail_point* new_trail = &ball->trails[ball->next_trail_index];
    new_trail->p = ball->p;
    new_trail->life = 1.0f; // 初始生命周期为1
    new_trail->color = ball->trail_color;

    // 移动环形缓冲区索引
    ball->next_trail_index = (ball->next_trail_index + 1) % ARRAY_COUNT(ball->trails);
}

![](img/06038cb1cd219389e961b5d06c0686c3_468.png)

![](img/06038cb1cd219389e961b5d06c0686c3_470.png)

![](img/06038cb1cd219389e961b5d06c0686c3_472.png)

![](img/06038cb1cd219389e961b5d06c0686c3_474.png)

![](img/06038cb1cd219389e961b5d06c0686c3_476.png)

![](img/06038cb1cd219389e961b5d06c0686c3_478.png)

![](img/06038cb1cd219389e961b5d06c0686c3_480.png)

![](img/06038cb1cd219389e961b5d06c0686c3_482.png)

![](img/06038cb1cd219389e961b5d06c0686c3_484.png)

![](img/06038cb1cd219389e961b5d06c0686c3_486.png)

![](img/06038cb1cd219389e961b5d06c0686c3_488.png)

![](img/06038cb1cd219389e961b5d06c0686c3_490.png)

![](img/06038cb1cd219389e961b5d06c0686c3_492.png)

![](img/06038cb1cd219389e961b5d06c0686c3_494.png)

// 渲染所有存活的轨迹点
for (int i = 0; i < ARRAY_COUNT(ball->trails); ++i) {
    trail_point* trail = &ball->trails[i];
    if (trail->life > 0.0f) {
        // 根据生命周期计算透明度
        f32 alpha = trail->life;
        draw_rectangle_transparent(trail->p, ball_half_size, trail->color, alpha);
        // 更新生命周期
        trail->life -= dt * decay_rate;
    }
}
```

![](img/06038cb1cd219389e961b5d06c0686c3_496.png)

![](img/06038cb1cd219389e961b5d06c0686c3_497.png)

![](img/06038cb1cd219389e961b5d06c0686c3_499.png)

![](img/06038cb1cd219389e961b5d06c0686c3_500.png)

![](img/06038cb1cd219389e961b5d06c0686c3_502.png)

![](img/06038cb1cd219389e961b5d06c0686c3_504.png)

![](img/06038cb1cd219389e961b5d06c0686c3_506.png)

![](img/06038cb1cd219389e961b5d06c0686c3_508.png)

![](img/06038cb1cd219389e961b5d06c0686c3_510.png)

![](img/06038cb1cd219389e961b5d06c0686c3_512.png)

![](img/06038cb1cd219389e961b5d06c0686c3_514.png)

![](img/06038cb1cd219389e961b5d06c0686c3_516.png)

![](img/06038cb1cd219389e961b5d06c0686c3_518.png)

![](img/06038cb1cd219389e961b5d06c0686c3_519.png)

![](img/06038cb1cd219389e961b5d06c0686c3_521.png)

![](img/06038cb1cd219389e961b5d06c0686c3_523.png)

为了实现透明渲染，我们需要扩展渲染器，支持带透明度的颜色混合函数 `lerp_color`。

![](img/06038cb1cd219389e961b5d06c0686c3_524.png)

![](img/06038cb1cd219389e961b5d06c0686c3_526.png)

![](img/06038cb1cd219389e961b5d06c0686c3_528.png)

![](img/06038cb1cd219389e961b5d06c0686c3_530.png)

![](img/06038cb1cd219389e961b5d06c0686c3_532.png)

![](img/06038cb1cd219389e961b5d06c0686c3_534.png)

![](img/06038cb1cd219389e961b5d06c0686c3_536.png)

---

![](img/06038cb1cd219389e961b5d06c0686c3_538.png)

![](img/06038cb1cd219389e961b5d06c0686c3_540.png)

![](img/06038cb1cd219389e961b5d06c0686c3_542.png)

![](img/06038cb1cd219389e961b5d06c0686c3_544.png)

## 实现动态墙壁 🧱

![](img/06038cb1cd219389e961b5d06c0686c3_546.png)

![](img/06038cb1cd219389e961b5d06c0686c3_548.png)

![](img/06038cb1cd219389e961b5d06c0686c3_550.png)

![](img/06038cb1cd219389e961b5d06c0686c3_552.png)

为了让游戏世界更具响应性，我们让墙壁在被球撞击时产生轻微的位移和反弹。

![](img/06038cb1cd219389e961b5d06c0686c3_554.png)

![](img/06038cb1cd219389e961b5d06c0686c3_556.png)

![](img/06038cb1cd219389e961b5d06c0686c3_558.png)

![](img/06038cb1cd219389e961b5d06c0686c3_560.png)

![](img/06038cb1cd219389e961b5d06c0686c3_562.png)

![](img/06038cb1cd219389e961b5d06c0686c3_564.png)

### 实现方法

![](img/06038cb1cd219389e961b5d06c0686c3_566.png)

![](img/06038cb1cd219389e961b5d06c0686c3_568.png)

![](img/06038cb1cd219389e961b5d06c0686c3_570.png)

![](img/06038cb1cd219389e961b5d06c0686c3_572.png)

![](img/06038cb1cd219389e961b5d06c0686c3_574.png)

![](img/06038cb1cd219389e961b5d06c0686c3_576.png)

![](img/06038cb1cd219389e961b5d06c0686c3_578.png)

![](img/06038cb1cd219389e961b5d06c0686c3_580.png)

类似于玩家挡板，我们为左侧、右侧和顶部墙壁分别存储其视觉位置和速度（`arena_left_visual_p`, `arena_left_visual_dp` 等）。墙壁也有一个目标位置（即其初始静止位置）。

![](img/06038cb1cd219389e961b5d06c0686c3_582.png)

![](img/06038cb1cd219389e961b5d06c0686c3_584.png)

![](img/06038cb1cd219389e961b5d06c0686c3_586.png)

![](img/06038cb1cd219389e961b5d06c0686c3_588.png)

![](img/06038cb1cd219389e961b5d06c0686c3_590.png)

![](img/06038cb1cd219389e961b5d06c0686c3_592.png)

![](img/06038cb1cd219389e961b5d06c0686c3_594.png)

![](img/06038cb1cd219389e961b5d06c0686c3_596.png)

当球撞击墙壁时，我们根据球的速度给墙壁施加一个冲量：

![](img/06038cb1cd219389e961b5d06c0686c3_598.png)

![](img/06038cb1cd219389e961b5d06c0686c3_600.png)

![](img/06038cb1cd219389e961b5d06c0686c3_602.png)

![](img/06038cb1cd219389e961b5d06c0686c3_604.png)

```c
// 例如，球撞击右侧墙壁
if (ball_collides_with_right_wall) {
    // 给墙壁一个反向的速度
    arena_right_visual_dp -= ball->dp.x * wall_impact_factor;
    // 同时，确保球速不低于最小值，避免卡顿
    ball->dp.x = -maximum(min_ball_speed, fabsf(ball->dp.x));
}
```

![](img/06038cb1cd219389e961b5d06c0686c3_606.png)

![](img/06038cb1cd219389e961b5d06c0686c3_608.png)

![](img/06038cb1cd219389e961b5d06c0686c3_610.png)

![](img/06038cb1cd219389e961b5d06c0686c3_612.png)

![](img/06038cb1cd219389e961b5d06c0686c3_614.png)

![](img/06038cb1cd219389e961b5d06c0686c3_616.png)

![](img/06038cb1cd219389e961b5d06c0686c3_618.png)

![](img/06038cb1cd219389e961b5d06c0686c3_620.png)

![](img/06038cb1cd219389e961b5d06c0686c3_622.png)

![](img/06038cb1cd219389e961b5d06c0686c3_624.png)

![](img/06038cb1cd219389e961b5d06c0686c3_626.png)

![](img/06038cb1cd219389e961b5d06c0686c3_628.png)

在每帧的模拟中，墙壁的位置也通过弹簧物理系统更新，使其在受到撞击后能平滑地回到目标位置。

![](img/06038cb1cd219389e961b5d06c0686c3_630.png)

![](img/06038cb1cd219389e961b5d06c0686c3_632.png)

![](img/06038cb1cd219389e961b5d06c0686c3_634.png)

![](img/06038cb1cd219389e961b5d06c0686c3_636.png)

![](img/06038cb1cd219389e961b5d06c0686c3_638.png)

![](img/06038cb1cd219389e961b5d06c0686c3_639.png)

![](img/06038cb1cd219389e961b5d06c0686c3_640.png)

![](img/06038cb1cd219389e961b5d06c0686c3_642.png)

![](img/06038cb1cd219389e961b5d06c0686c3_644.png)

![](img/06038cb1cd219389e961b5d06c0686c3_646.png)

![](img/06038cb1cd219389e961b5d06c0686c3_648.png)

![](img/06038cb1cd219389e961b5d06c0686c3_650.png)

![](img/06038cb1cd219389e961b5d06c0686c3_651.png)

![](img/06038cb1cd219389e961b5d06c0686c3_653.png)

---

![](img/06038cb1cd219389e961b5d06c0686c3_655.png)

![](img/06038cb1cd219389e961b5d06c0686c3_657.png)

![](img/06038cb1cd219389e961b5d06c0686c3_659.png)

![](img/06038cb1cd219389e961b5d06c0686c3_661.png)

![](img/06038cb1cd219389e961b5d06c0686c3_663.png)

![](img/06038cb1cd219389e961b5d06c0686c3_665.png)

![](img/06038cb1cd219389e961b5d06c0686c3_667.png)

![](img/06038cb1cd219389e961b5d06c0686c3_669.png)

![](img/06038cb1cd219389e961b5d06c0686c3_671.png)

![](img/06038cb1cd219389e961b5d06c0686c3_673.png)

![](img/06038cb1cd219389e961b5d06c0686c3_675.png)

![](img/06038cb1cd219389e961b5d06c0686c3_677.png)

## 根据状态改变球体颜色 🎨

![](img/06038cb1cd219389e961b5d06c0686c3_679.png)

![](img/06038cb1cd219389e961b5d06c0686c3_681.png)

![](img/06038cb1cd219389e961b5d06c0686c3_683.png)

![](img/06038cb1cd219389e961b5d06c0686c3_685.png)

![](img/06038cb1cd219389e961b5d06c0686c3_687.png)

![](img/06038cb1cd219389e961b5d06c0686c3_689.png)

![](img/06038cb1cd219389e961b5d06c0686c3_691.png)

![](img/06038cb1cd219389e961b5d06c0686c3_692.png)

![](img/06038cb1cd219389e961b5d06c0686c3_694.png)

![](img/06038cb1cd219389e961b5d06c0686c3_696.png)

![](img/06038cb1cd219389e961b5d06c0686c3_697.png)

![](img/06038cb1cd219389e961b5d06c0686c3_699.png)

最后，我们通过改变球体及其拖尾的颜色来提供视觉反馈，例如当球体被“彗星”能量增强或速度很快时。

![](img/06038cb1cd219389e961b5d06c0686c3_701.png)

![](img/06038cb1cd219389e961b5d06c0686c3_703.png)

![](img/06038cb1cd219389e961b5d06c0686c3_705.png)

![](img/06038cb1cd219389e961b5d06c0686c3_707.png)

![](img/06038cb1cd219389e961b5d06c0686c3_709.png)

### 颜色逻辑

![](img/06038cb1cd219389e961b5d06c0686c3_711.png)

![](img/06038cb1cd219389e961b5d06c0686c3_713.png)

![](img/06038cb1cd219389e961b5d06c0686c3_715.png)

![](img/06038cb1cd219389e961b5d06c0686c3_717.png)

![](img/06038cb1cd219389e961b5d06c0686c3_719.png)

![](img/06038cb1cd219389e961b5d06c0686c3_721.png)

![](img/06038cb1cd219389e961b5d06c0686c3_723.png)

![](img/06038cb1cd219389e961b5d06c0686c3_725.png)

![](img/06038cb1cd219389e961b5d06c0686c3_727.png)

![](img/06038cb1cd219389e961b5d06c0686c3_729.png)

![](img/06038cb1cd219389e961b5d06c0686c3_731.png)

在更新球体轨迹颜色时，我们检查其状态：

![](img/06038cb1cd219389e961b5d06c0686c3_733.png)

![](img/06038cb1cd219389e961b5d06c0686c3_735.png)

![](img/06038cb1cd219389e961b5d06c0686c3_737.png)

![](img/06038cb1cd219389e961b5d06c0686c3_739.png)

![](img/06038cb1cd219389e961b5d06c0686c3_741.png)

![](img/06038cb1cd219389e961b5d06c0686c3_743.png)

![](img/06038cb1cd219389e961b5d06c0686c3_745.png)

![](img/06038cb1cd219389e961b5d06c0686c3_747.png)

![](img/06038cb1cd219389e961b5d06c0686c3_749.png)

![](img/06038cb1cd219389e961b5d06c0686c3_750.png)

```c
// 如果球体被“彗星”能量增强（穿透方块）
if (ball->comet_timer > 0.0f) {
    ball->trail_color = COLOR_RED;
}
// 如果球体速度非常快
else if (length_sq(ball->dp) > fast_speed_threshold) {
    ball->trail_color = COLOR_YELLOW;
}
// 默认颜色
else {
    ball->trail_color = ball->base_color;
}
```

![](img/06038cb1cd219389e961b5d06c0686c3_752.png)

![](img/06038cb1cd219389e961b5d06c0686c3_754.png)

![](img/06038cb1cd219389e961b5d06c0686c3_756.png)

![](img/06038cb1cd219389e961b5d06c0686c3_758.png)

![](img/06038cb1cd219389e961b5d06c0686c3_760.png)

![](img/06038cb1cd219389e961b5d06c0686c3_762.png)

![](img/06038cb1cd219389e961b5d06c0686c3_764.png)

这为玩家提供了即时的、直观的游戏状态反馈。

![](img/06038cb1cd219389e961b5d06c0686c3_766.png)

![](img/06038cb1cd219389e961b5d06c0686c3_768.png)

![](img/06038cb1cd219389e961b5d06c0686c3_770.png)

---

![](img/06038cb1cd219389e961b5d06c0686c3_772.png)

![](img/06038cb1cd219389e961b5d06c0686c3_774.png)

![](img/06038cb1cd219389e961b5d06c0686c3_776.png)

![](img/06038cb1cd219389e961b5d06c0686c3_778.png)

![](img/06038cb1cd219389e961b5d06c0686c3_780.png)

## 总结

![](img/06038cb1cd219389e961b5d06c0686c3_782.png)

![](img/06038cb1cd219389e961b5d06c0686c3_784.png)

![](img/06038cb1cd219389e961b5d06c0686c3_786.png)

本节课我们一起学习了如何为游戏注入“果汁”，显著提升了游戏的视听反馈和操作手感。我们主要实现了：

![](img/06038cb1cd219389e961b5d06c0686c3_788.png)

![](img/06038cb1cd219389e961b5d06c0686c3_790.png)

![](img/06038cb1cd219389e961b5d06c0686c3_792.png)

1.  **弹性挡板**：使用弹簧物理模拟，让挡板移动更加生动，并添加了撞墙时的挤压拉伸效果。
2.  **球体拖尾**：通过环形缓冲区和生命周期管理，实现了带有淡出效果的轨迹，增强了速度感。
3.  **动态墙壁**：让墙壁能够对碰撞做出反应，轻微移动并反弹，使游戏世界更加活泼。
4.  **动态颜色**：根据球体的状态（如增强效果、速度）改变其颜色，提供清晰的视觉反馈。

![](img/06038cb1cd219389e961b5d06c0686c3_794.png)

![](img/06038cb1cd219389e961b5d06c0686c3_796.png)

![](img/06038cb1cd219389e961b5d06c0686c3_798.png)

![](img/06038cb1cd219389e961b5d06c0686c3_800.png)

![](img/06038cb1cd219389e961b5d06c0686c3_802.png)

![](img/06038cb1cd219389e961b5d06c0686c3_804.png)

![](img/06038cb1cd219389e961b5d06c0686c3_805.png)

![](img/06038cb1cd219389e961b5d06c0686c3_807.png)

这些看似微小的调整汇集在一起，极大地丰富了游戏的互动体验。在下一节中，我们可以继续完善这些效果，例如添加方块破坏动画、粒子系统或屏幕震动，让游戏变得更加炫酷和完整。