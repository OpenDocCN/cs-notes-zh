# 019：相机系统与屏幕震动 🎮

![](img/7d44c52568183ee28453dce79ee0ef2b_1.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_3.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_4.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_5.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_7.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_9.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_11.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_13.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_15.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_17.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_19.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_21.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_23.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_25.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_27.png)

在本节课中，我们将学习如何为游戏实现一个相机系统，并在此基础上添加屏幕震动效果，以增强游戏的视觉反馈和打击感。我们将重构碰撞检测系统，使其更加健壮，并引入一个基于弹簧物理的相机来管理屏幕震动。

![](img/7d44c52568183ee28453dce79ee0ef2b_29.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_31.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_33.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_35.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_37.png)

## 概述

![](img/7d44c52568183ee28453dce79ee0ef2b_39.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_41.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_43.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_45.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_47.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_49.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_51.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_53.png)

上一节我们完成了游戏的核心玩法。本节我们将重点改进两个核心系统：碰撞检测和视觉反馈。首先，我们会重构碰撞检测逻辑，解决之前存在的边缘问题。然后，我们将引入一个相机系统，并利用它来实现屏幕震动效果，让游戏中的碰撞、击打等事件更具冲击力。

![](img/7d44c52568183ee28453dce79ee0ef2b_55.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_57.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_59.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_61.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_63.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_64.png)

## 重构碰撞检测系统

![](img/7d44c52568183ee28453dce79ee0ef2b_66.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_68.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_70.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_72.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_74.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_76.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_78.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_80.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_82.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_84.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_86.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_88.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_90.png)

在之前的实现中，碰撞检测的逻辑是遍历所有方块，然后检查每个球是否与之碰撞。这种方法在某些边缘情况下（例如球同时与多个方块接触或移动速度过快时）可能导致不准确或“穿墙”的现象。

![](img/7d44c52568183ee28453dce79ee0ef2b_92.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_94.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_96.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_98.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_100.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_102.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_104.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_106.png)

我们的目标是让碰撞检测更加精确和可预测。核心思路是：**为每个球计算其在本帧内的预期移动路径（从当前位置 `ball.P` 到目标位置 `ball.DesiredP`），然后与所有方块进行“扫描”测试，找出路径上最早发生碰撞的点。**

![](img/7d44c52568183ee28453dce79ee0ef2b_108.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_110.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_112.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_114.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_116.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_118.png)

以下是实现这一思路的关键步骤：

![](img/7d44c52568183ee28453dce79ee0ef2b_120.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_122.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_124.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_126.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_127.png)

1.  **计算移动路径**：对于每个活动的球，计算其基于速度的目标位置。
    ```c
    v2 DesiredP = V2Add(Ball->P, V2Scale(Ball->Dp, Dt));
    ```

![](img/7d44c52568183ee28453dce79ee0ef2b_129.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_131.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_133.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_135.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_137.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_139.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_141.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_143.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_145.png)

2.  **扫描测试**：遍历所有存活的方块。对于每个方块，我们计算球从 `Ball->P` 移动到 `DesiredP` 的路径是否会与之相交，并计算出相交点的时间参数 `t`（0 表示路径起点，1 表示路径终点）。我们记录下最小的 `t` 值（即最早发生的碰撞）以及对应的方块。

![](img/7d44c52568183ee28453dce79ee0ef2b_147.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_149.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_151.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_153.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_155.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_157.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_159.png)

3.  **处理碰撞**：如果发生了碰撞（即最小 `t` 值小于 1）：
    *   将球的位置更新到碰撞发生点：`Ball->P = V2Lerp(OldP, DesiredP, MinT)`。
    *   根据碰撞发生在 X 轴还是 Y 轴，反转球在对应方向上的速度。
    *   销毁被击中的方块，并触发相关效果（如增加球的大小、播放音效、添加屏幕震动）。
    *   由于一次移动可能尚未完成（`MinT < 1`），我们需要用剩余的运动量（`1 - MinT`）重复步骤 2 和 3，直到移动完成或不再发生碰撞。这确保了单帧内可以正确处理连续碰撞。

![](img/7d44c52568183ee28453dce79ee0ef2b_161.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_163.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_165.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_167.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_169.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_171.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_173.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_175.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_177.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_179.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_181.png)

4.  **处理嵌入情况**：如果检测开始时球就已经在方块内部（例如上一帧结束时已接触），我们将这次碰撞的时间 `t` 设为 0，并立即处理碰撞响应，防止球被卡住。

![](img/7d44c52568183ee28453dce79ee0ef2b_183.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_185.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_187.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_189.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_191.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_193.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_195.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_197.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_199.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_200.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_202.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_203.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_205.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_207.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_209.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_211.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_213.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_215.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_217.png)

通过这种基于扫描和迭代的方法，我们的碰撞系统变得更加健壮，能够更准确地处理高速移动和复杂碰撞场景。

![](img/7d44c52568183ee28453dce79ee0ef2b_219.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_221.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_223.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_225.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_227.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_229.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_231.png)

## 实现相机系统

![](img/7d44c52568183ee28453dce79ee0ef2b_232.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_234.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_236.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_238.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_240.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_242.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_244.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_246.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_248.png)

为了实现屏幕震动，我们首先需要一个统一的相机来管理视图变换。在此之前，游戏中的所有绘制都是直接使用世界坐标。

![](img/7d44c52568183ee28453dce79ee0ef2b_250.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_252.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_254.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_256.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_257.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_259.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_261.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_263.png)

1.  **定义相机结构**：我们创建一个简单的相机，包含位置 (`P`)、速度 (`Dp`) 和加速度 (`Ddp`)。
    ```c
    typedef struct {
        v2 P;
        v2 Dp;
        v2 Ddp;
    } camera;
    ```
    在游戏状态中初始化这个相机。

![](img/7d44c52568183ee28453dce79ee0ef2b_265.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_267.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_269.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_271.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_273.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_275.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_277.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_279.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_281.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_283.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_285.png)

2.  **修改绘制函数**：将所有直接绘制调用（如 `DrawRect`, `DrawBitmap` 等）中使用的世界坐标，减去相机的位置 (`Camera.P`)。这样，当相机移动时，整个游戏世界就会朝相反方向移动，从而产生屏幕移动的效果。
    ```c
    // 修改前
    DrawRect(P, Size, Color);
    // 修改后
    v2 DrawP = V2Sub(P, GameState->Camera.P);
    DrawRect(DrawP, Size, Color);
    ```

![](img/7d44c52568183ee28453dce79ee0ef2b_287.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_289.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_291.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_293.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_295.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_297.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_299.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_301.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_303.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_305.png)

3.  **更新相机位置**：我们使用一个**弹簧物理模型**来更新相机。这能让相机的移动带有平滑的弹性效果，非常适合用来实现屏幕震动。
    *   **期望位置**：相机的期望位置通常是 `(0, 0)`，即屏幕中心。
    *   **弹簧力**：根据胡克定律，弹簧力与位移成正比。我们计算当前位置与期望位置的差值，乘以一个弹性系数 (`k`)，得到加速度的一部分。
    *   **阻尼力**：为了阻止无限震动，我们添加一个与速度成正比、方向相反的阻尼力，乘以一个阻尼系数 (`d`)。
    *   **合成加速度**：将上述两个力（除以质量，这里假设为1）合成为相机的加速度 `Ddp`。
    *   **积分更新**：使用半隐式欧拉积分法，用加速度 `Ddp` 和速度 `Dp` 来更新相机的位置 `P`。
    ```c
    // 简化的弹簧更新逻辑
    v2 Displacement = V2Sub(TargetP, Camera.P);
    Camera.Ddp = V2Add(V2Scale(Displacement, k), V2Scale(Camera.Dp, -d));
    Camera.Dp = V2Add(Camera.Dp, V2Scale(Camera.Ddp, Dt));
    Camera.P = V2Add(Camera.P, V2Scale(Camera.Dp, Dt));
    ```

![](img/7d44c52568183ee28453dce79ee0ef2b_307.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_309.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_311.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_313.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_315.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_317.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_319.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_321.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_323.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_325.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_327.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_329.png)

## 添加屏幕震动效果

![](img/7d44c52568183ee28453dce79ee0ef2b_331.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_333.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_335.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_337.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_339.png)

有了基于弹簧的相机，实现屏幕震动就非常简单了。我们只需要在希望产生震动的游戏事件发生时，给相机的速度 (`Dp`) 施加一个瞬间的冲击力即可。

![](img/7d44c52568183ee28453dce79ee0ef2b_341.png)

以下是添加屏幕震动的关键事件点：

![](img/7d44c52568183ee28453dce79ee0ef2b_343.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_344.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_346.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_348.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_350.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_351.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_353.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_355.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_357.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_359.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_361.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_363.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_365.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_367.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_369.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_371.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_373.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_375.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_377.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_379.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_381.png)

*   **球击中墙壁**：当球与左右或上方墙壁碰撞时。
*   **球击中方块**：当球摧毁一个方块时。
*   **玩家损失生命**：当球掉落到底部，玩家失去一条命时。
*   **敌人撞击墙壁**：在特定的游戏模式（如“打砖块版打飞机”）中，敌机撞到墙壁时。

![](img/7d44c52568183ee28453dce79ee0ef2b_383.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_385.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_387.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_389.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_391.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_393.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_395.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_397.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_399.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_401.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_403.png)

实现方法就是调用一个工具函数，例如 `AddScreenShake(v2 Impulse)`，该函数会将 `Impulse` 向量加到 `Camera.Dp` 上。
```c
void AddScreenShake(v2 Impulse) {
    GameState->Camera.Dp = V2Add(GameState->Camera.Dp, Impulse);
}
```
通过调整冲击力 `Impulse` 的大小和方向，以及相机弹簧的 `k` 和 `d` 参数，我们可以创造出从轻微抖动到剧烈摇晃的不同震动效果。

![](img/7d44c52568183ee28453dce79ee0ef2b_405.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_407.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_409.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_411.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_413.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_414.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_416.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_418.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_419.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_421.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_423.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_425.png)

## 总结

![](img/7d44c52568183ee28453dce79ee0ef2b_427.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_429.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_431.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_432.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_434.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_436.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_438.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_440.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_442.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_443.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_445.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_447.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_449.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_451.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_453.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_455.png)

本节课中我们一起学习了两个重要的游戏开发概念。

![](img/7d44c52568183ee28453dce79ee0ef2b_457.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_459.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_461.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_463.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_465.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_467.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_469.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_471.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_473.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_475.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_477.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_479.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_481.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_483.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_484.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_486.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_488.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_490.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_492.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_494.png)

首先，我们**重构了碰撞检测系统**，从简单的每帧状态检测升级为基于路径扫描和迭代解决的方案。这使得碰撞处理更加精确，尤其是在处理高速物体和复杂接触时，提升了游戏的物理可信度。

![](img/7d44c52568183ee28453dce79ee0ef2b_496.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_498.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_500.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_502.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_504.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_506.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_508.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_510.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_512.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_514.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_516.png)

其次，我们**实现了一个相机系统并添加了屏幕震动**。通过引入一个基于弹簧物理的相机，我们能够以统一的方式管理视图。只需在特定的游戏事件中给相机施加一个力，就能轻松产生各种屏幕震动效果，极大地增强了游戏的画面表现力和操作反馈。

![](img/7d44c52568183ee28453dce79ee0ef2b_518.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_520.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_522.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_523.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_524.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_526.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_528.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_530.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_532.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_534.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_536.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_538.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_540.png)

![](img/7d44c52568183ee28453dce79ee0ef2b_542.png)

这些改进不仅让当前的游戏体验更上一层楼，其中涉及的碰撞处理思路和相机/反馈系统设计，也是你在未来开发其他项目时可以复用的宝贵工具。