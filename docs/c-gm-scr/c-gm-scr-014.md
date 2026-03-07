# 014：实现音效 🔊

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_1.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_3.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_5.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_7.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_9.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_11.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_13.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_14.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_16.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_18.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_20.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_22.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_24.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_26.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_28.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_30.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_32.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_34.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_36.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_37.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_39.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_41.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_43.png)

在本节课中，我们将为游戏添加各种音效，并修复音频系统中存在的一些问题。我们将从修复一个已知的菜单选择bug开始，然后改进音频混合器的核心逻辑，最后为游戏中的各种事件（如碰撞、得分、获得道具等）添加丰富的声音效果。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_45.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_47.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_49.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_51.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_53.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_55.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_57.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_59.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_61.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_63.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_65.png)

## 概述 📋

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_67.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_69.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_71.png)

上一节我们为游戏添加了主菜单音乐。本节中，我们将重点实现游戏内的音效系统。我们会修复音频混合器中的一些bug，优化音量和平滑过渡的计算方式，并为玩家移动、球体碰撞、方块破坏、获得道具等事件添加对应的音效，让游戏体验更加生动。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_73.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_75.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_77.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_79.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_81.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_83.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_85.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_87.png)

## 修复菜单选择Bug 🐛

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_89.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_91.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_93.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_95.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_97.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_99.png)

首先，我们修复一个已知的bug：即使关卡被锁定，玩家仍然可以通过点击进入。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_101.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_103.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_105.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_107.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_109.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_111.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_113.png)

这个bug出现在检查关卡是否锁定的逻辑中。我们需要确保只有当关卡未锁定时，点击才会生效。修复方法是在处理鼠标点击事件时，先检查 `level->locked` 状态。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_115.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_117.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_119.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_121.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_123.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_125.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_127.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_129.png)

**核心代码修改：**
```c
// 在关卡选择逻辑中
if (!level->locked && is_mouse_over_level) {
    // 进入该关卡
}
```

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_131.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_133.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_135.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_137.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_139.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_141.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_143.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_145.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_147.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_149.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_151.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_153.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_155.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_157.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_159.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_161.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_163.png)

修复后，只有解锁的关卡才能被点击进入。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_165.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_167.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_169.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_171.png)

## 改进音频混合器 🔊

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_173.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_174.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_176.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_178.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_180.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_182.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_184.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_186.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_188.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_190.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_192.png)

上一节我们构建了基础的音频混合器。本节中，我们将对其进行多项改进，使其更稳定、音质更好。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_194.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_196.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_198.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_200.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_201.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_203.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_204.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_205.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_207.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_209.png)

### 1. 添加音频削波指示器

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_211.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_213.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_214.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_216.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_218.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_220.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_222.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_224.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_226.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_228.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_230.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_232.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_234.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_236.png)

为了防止音频失真，我们之前添加了削波（clamping）功能。现在，我们添加一个简单的视觉（或打印）指示器，当发生削波时进行提示，便于调试。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_238.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_240.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_242.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_243.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_245.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_247.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_249.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_251.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_253.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_255.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_257.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_259.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_260.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_262.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_263.png)

**核心代码：**
```c
if (left_sample * 0.5f < min_value || left_sample * 0.5f > max_value ||
    right_sample * 0.5f < min_value || right_sample * 0.5f > max_value) {
    printf("Audio clipped!\n"); // 指示发生了削波
}
```

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_265.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_267.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_269.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_271.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_273.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_275.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_276.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_278.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_280.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_282.png)

### 2. 优化音高变化算法

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_284.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_286.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_288.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_290.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_292.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_294.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_295.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_297.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_299.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_301.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_303.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_305.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_307.png)

之前，当我们以8倍速播放声音时，由于采样点跳跃过大，会导致波形被严重裁剪，产生难听的噪音。为了解决这个问题，我们创建了一个更低音调的正弦波（`sine3.wav`）来替代原有的高音调声音，在高速播放时效果更好。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_309.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_311.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_313.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_315.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_317.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_319.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_320.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_321.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_323.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_325.png)

**核心思路：**
对于需要改变音效（如玩家快速移动时的“嗖嗖”声），我们不再单纯地提高原始音频的播放速度，而是换用一个更适合高速播放的、音调更低的基础音频样本。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_327.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_329.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_331.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_333.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_335.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_337.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_339.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_341.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_343.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_345.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_347.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_349.png)

### 3. 修正音量和平滑过渡

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_351.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_353.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_355.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_357.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_358.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_360.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_362.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_363.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_365.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_367.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_369.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_370.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_372.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_373.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_375.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_377.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_379.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_381.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_382.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_384.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_386.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_388.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_390.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_391.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_393.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_395.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_397.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_399.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_400.png)

之前，音量的更新和音高的速度乘数（`speed_multiplier`）每音频帧（约1/60秒）才更新一次。这对于需要平滑过渡的效果（如根据玩家速度变化的音量）来说不够精细。我们应该**每音频采样点**都更新这些值。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_402.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_404.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_406.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_408.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_410.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_412.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_414.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_416.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_418.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_420.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_422.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_424.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_425.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_427.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_429.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_431.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_432.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_434.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_435.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_437.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_438.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_440.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_442.png)

**修改前（每帧更新）：**
```c
// 在音频更新函数中，每帧执行一次
sound->volume = lerp(sound->volume, sound->target_volume, dt);
sound->position += sound->speed_multiplier;
```

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_444.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_445.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_447.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_449.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_451.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_453.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_455.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_457.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_459.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_461.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_463.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_465.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_467.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_469.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_471.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_473.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_475.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_476.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_478.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_480.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_482.png)

**修改后（每采样点更新）：**
我们需要将音量渐变和位置更新的计算移到内部采样循环中，并根据每采样点的时间增量（`dt_per_sample`）来更新。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_484.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_486.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_488.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_490.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_492.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_493.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_495.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_497.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_499.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_500.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_502.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_504.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_506.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_508.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_510.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_512.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_513.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_515.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_516.png)

**核心公式：**
`dt_per_sample = 1.0 / samples_per_second`

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_518.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_519.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_521.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_523.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_525.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_526.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_527.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_529.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_530.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_532.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_534.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_536.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_538.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_539.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_540.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_542.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_544.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_545.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_546.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_548.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_550.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_552.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_554.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_556.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_557.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_558.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_560.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_561.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_562.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_564.png)

在混合每个采样点时，应用微小的渐变：
`sound->volume = lerp(sound->volume, sound->target_volume, fade_speed * dt_per_sample);`
`sound->position += sound->speed_multiplier * dt_per_sample;`

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_566.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_568.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_570.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_572.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_573.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_575.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_577.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_579.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_581.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_583.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_584.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_586.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_588.png)

### 4. 修复循环播放和声道计数错误

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_590.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_592.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_594.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_596.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_598.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_600.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_602.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_603.png)

在音频混合器的循环播放逻辑中，存在两个问题：
1.  当播放位置超过样本总数时，我们错误地将其直接设为0，而不是减去总样本数，这会导致计算错误。
2.  在计算下一个采样点索引时，没有考虑音频的声道数。我们的样本计数是单声道的，但存储是交错的（左、右、左、右...）。因此，在索引样本数据时，需要乘以声道数。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_605.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_607.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_609.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_611.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_613.png)

**修复后的核心代码：**
```c
// 计算当前和下一个采样点的索引（考虑声道数）
s32 sample_index0 = (s32)sound->position * sound->channels;
s32 sample_index1 = sample_index0 + sound->channels;

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_615.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_617.png)

// 处理循环
if (sound->looping) {
    if (sample_index1 >= sound->sample_count * sound->channels) {
        sample_index1 -= sound->sample_count * sound->channels;
    }
} else {
    // 非循环播放，到达末尾后停止
    if (sample_index0 >= sound->sample_count * sound->channels) {
        sound->playing = false;
        return;
    }
}
```

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_619.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_621.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_623.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_625.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_627.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_629.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_631.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_633.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_635.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_637.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_639.png)

## 为游戏事件添加音效 🎮

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_641.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_643.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_645.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_647.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_649.png)

现在，音频系统的基础已经稳固，我们可以开始为各种游戏事件添加音效了。以下是我们要添加的主要音效列表：

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_651.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_653.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_655.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_657.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_659.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_661.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_663.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_665.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_667.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_669.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_671.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_673.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_675.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_677.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_679.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_681.png)

*   **玩家移动音效：** 使用正弦波声音，根据玩家移动的速度和方向改变音高和音量，营造出“挤压拉伸”的动感效果。
*   **球与挡板碰撞音效：** 使用烟花爆炸声，并添加随机音高和音量变化，增加趣味性。
*   **球与墙壁碰撞音效：** 使用弹簧声。
*   **方块被破坏音效：** 使用爆炸声，并根据方块的位置在立体声中定位。
*   **游戏开始/结束/生命值减少音效：** 添加对应的提示音。
*   **获得道具音效：** 为增益道具和减益道具分别添加积极和消极的音效。
*   **彗星道具音效：** 包含一个开始的“嗖”声和一个循环的拖尾音效。
*   **界面交互音效：** 为菜单选择等操作添加点击声。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_683.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_685.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_687.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_689.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_691.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_693.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_694.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_696.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_698.png)

### 实现方式

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_700.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_702.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_704.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_706.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_708.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_710.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_712.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_714.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_716.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_718.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_720.png)

我们创建一个辅助函数 `play_sound_with_variation`，用于播放带有随机音高/音量变化的音效，使重复的声音不那么单调。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_722.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_724.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_726.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_728.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_730.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_732.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_734.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_736.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_738.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_740.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_741.png)

**核心代码示例：**
```c
void play_sound_with_variation(Loaded_Sound* sound, f32 volume, f32 pitch_variation) {
    f32 random_pitch = 1.0f + (random_float() * 2.0f - 1.0f) * pitch_variation;
    f32 random_volume = volume * (0.9f + random_float() * 0.2f); // 音量轻微变化

    // 调用底层音频播放函数，设置 random_pitch 和 random_volume
    internal_play_sound(sound, random_volume, random_pitch);
}
```

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_743.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_745.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_747.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_749.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_751.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_753.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_755.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_757.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_758.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_760.png)

然后，在游戏的相应事件处调用这个函数或直接的 `play_sound` 函数。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_762.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_764.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_766.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_768.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_770.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_772.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_774.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_776.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_778.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_780.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_782.png)

## 实现立体声定位 🎧

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_784.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_786.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_787.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_789.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_791.png)

为了让音效更具沉浸感，我们实现简单的立体声定位。思路是：为需要定位的音效（如球的声音、方块爆炸声）指定一个声源位置（`source_x`）。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_793.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_795.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_797.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_799.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_801.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_803.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_804.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_806.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_808.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_810.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_812.png)

在音频混合器处理该音效的每个采样点时，根据玩家（听众）的当前位置（`listener_x`）和声源位置计算一个“声像”（pan）值。这个值用于调整左右声道的音量平衡。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_814.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_816.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_818.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_820.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_822.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_824.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_826.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_828.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_830.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_832.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_834.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_836.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_838.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_840.png)

**核心计算逻辑：**
```c
// 计算声像值，范围大约在 [-1.0, 1.0] 之间，-1为最左，1为最右
f32 pan = (source_x - listener_x) * 0.01f; // 0.01f 是一个缩放因子，用于调整效果强度
pan = clamp(pan, -1.0f, 1.0f);

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_842.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_844.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_846.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_848.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_849.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_851.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_853.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_855.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_857.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_858.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_860.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_862.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_864.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_866.png)

// 根据声像调整左右声道增益
f32 left_gain = 1.0f - max(0.0f, pan);
f32 right_gain = 1.0f + min(0.0f, pan);

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_868.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_869.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_871.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_872.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_874.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_876.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_878.png)

// 在混合时应用增益
left_sample += sound_sample * left_gain * sound->volume;
right_sample += sound_sample * right_gain * sound->volume;
```

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_880.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_882.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_884.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_886.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_888.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_889.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_891.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_893.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_895.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_896.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_898.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_900.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_902.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_903.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_905.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_907.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_909.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_911.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_913.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_915.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_916.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_918.png)

我们为球的声音、彗星尾迹声、方块爆炸声等添加了声源定位，这样玩家就能听出球是从左侧还是右侧飞过的。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_920.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_922.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_924.png)

## 总结 🏁

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_926.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_928.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_930.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_932.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_934.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_935.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_937.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_939.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_940.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_941.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_943.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_945.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_947.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_948.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_950.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_952.png)

本节课中我们一起学习了如何为C语言游戏实现一个完整的音效系统。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_954.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_956.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_958.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_960.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_962.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_964.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_966.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_968.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_970.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_972.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_974.png)

我们首先修复了音频混合器的关键bug，包括循环逻辑、声道计数和每采样点更新问题。然后，我们为游戏中的几乎所有交互事件添加了丰富多彩的音效，从细微的玩家移动到激烈的爆炸碰撞。最后，我们还实现了简单的立体声定位，让声音空间感更强。

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_976.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_978.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_980.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_982.png)

![](img/35cc7b407d7f4707e0d68b6c750d9e6f_984.png)

通过这些工作，我们的游戏从视觉到听觉都变得完整而富有吸引力，为后续添加更多游戏模式和内容打下了坚实的基础。在接下来的课程中，我们将利用这个强大的音频系统，继续完善游戏玩法。