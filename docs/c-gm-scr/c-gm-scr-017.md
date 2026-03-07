# 017：游戏性改进与动画 🎮

![](img/d4175b7c7da94dffbf39910f5457f6a6_1.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_2.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_4.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_6.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_8.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_10.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_12.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_14.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_16.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_18.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_20.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_22.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_24.png)

在本节课中，我们将专注于游戏性的改进，特别是动画和帧率独立性的修复。上一节我们优化了渲染器，现在可以安全地回到游戏性编程，扩展关卡并提升整体游戏体验。

![](img/d4175b7c7da94dffbf39910f5457f6a6_26.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_28.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_30.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_32.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_34.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_36.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_38.png)

## 概述 📋

![](img/d4175b7c7da94dffbf39910f5457f6a6_40.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_42.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_44.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_46.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_48.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_50.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_52.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_54.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_56.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_58.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_60.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_61.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_63.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_65.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_67.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_69.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_71.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_73.png)

本节课我们将解决几个关键问题：修复鼠标光标在游戏窗口外时的异常行为，确保玩家移动和音效在不同帧率下表现一致，为游戏添加新的动画效果（如能量块的脉动动画），并锁定游戏帧率以获得更稳定的体验。

![](img/d4175b7c7da94dffbf39910f5457f6a6_75.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_77.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_79.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_81.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_83.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_84.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_86.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_88.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_89.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_91.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_93.png)

## 鼠标光标修复 🖱️

![](img/d4175b7c7da94dffbf39910f5457f6a6_95.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_97.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_99.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_101.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_103.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_105.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_107.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_108.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_110.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_112.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_114.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_116.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_118.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_120.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_122.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_124.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_126.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_128.png)

上一节我们介绍了渲染优化，本节中我们来看看如何修复一个影响游戏体验的鼠标问题。当玩家按Alt+Tab切换出游戏窗口时，鼠标光标会变得不受控制，导致玩家视角疯狂旋转。

![](img/d4175b7c7da94dffbf39910f5457f6a6_130.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_131.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_133.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_134.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_136.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_138.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_140.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_142.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_144.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_146.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_148.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_150.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_152.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_154.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_156.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_158.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_160.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_162.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_164.png)

问题的根源在于鼠标输入计算依赖于一个固定的屏幕中心点坐标。当窗口失去焦点时，我们不应再使用该中心点来计算鼠标移动差值。

![](img/d4175b7c7da94dffbf39910f5457f6a6_166.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_168.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_170.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_172.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_174.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_176.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_178.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_180.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_182.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_184.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_186.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_188.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_190.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_192.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_193.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_195.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_197.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_199.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_201.png)

以下是修复步骤的核心代码逻辑：

![](img/d4175b7c7da94dffbf39910f5457f6a6_203.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_204.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_206.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_208.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_210.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_212.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_214.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_216.png)

```c
// 仅在游戏窗口激活且鼠标被锁定时，才将光标重置到屏幕中心并隐藏
if (window_is_active && mouse_is_locked) {
    SetCursorPos(center_screen_x, center_screen_y);
    ShowCursor(FALSE); // 隐藏光标
} else {
    // 当窗口失去焦点时，恢复默认光标并显示
    SetCursor(LoadCursor(NULL, IDC_ARROW));
    ShowCursor(TRUE);
}

![](img/d4175b7c7da94dffbf39910f5457f6a6_218.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_219.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_221.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_223.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_225.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_227.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_229.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_231.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_233.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_235.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_237.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_239.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_241.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_243.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_245.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_247.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_249.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_251.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_253.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_255.png)

// 计算鼠标移动差值时，使用上一帧的鼠标位置，而不是固定的中心点
mouse_delta_x = new_mouse_x - old_mouse_x;
mouse_delta_y = new_mouse_y - old_mouse_y;
old_mouse_x = new_mouse_x;
old_mouse_y = new_mouse_y;
```

![](img/d4175b7c7da94dffbf39910f5457f6a6_257.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_259.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_261.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_263.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_265.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_267.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_269.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_271.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_273.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_275.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_277.png)

通过上述修改，我们确保了只有当游戏窗口处于活动状态且玩家需要控制时，鼠标才会被锁定和隐藏。这解决了切换窗口导致的视角失控问题。

![](img/d4175b7c7da94dffbf39910f5457f6a6_279.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_281.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_282.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_284.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_286.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_288.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_290.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_292.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_294.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_296.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_298.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_300.png)

## 帧率独立性与动画修复 ⚙️

![](img/d4175b7c7da94dffbf39910f5457f6a6_302.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_304.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_306.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_308.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_310.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_312.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_314.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_316.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_318.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_320.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_322.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_324.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_326.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_328.png)

接下来，我们需要确保玩家的视觉反馈（如拉伸动画）和音效（如移动音高）在不同帧率下表现一致。之前，这些效果依赖于每帧的时间增量（delta time），但在低帧率下会表现异常。

![](img/d4175b7c7da94dffbf39910f5457f6a6_330.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_332.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_334.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_336.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_338.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_340.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_342.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_344.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_346.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_348.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_350.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_352.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_353.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_355.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_356.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_357.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_359.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_360.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_362.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_363.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_364.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_366.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_368.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_370.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_372.png)

核心问题在于“目标速度”的计算单位不一致。我们需要确保所有基于时间的计算都使用“每秒单位”而非“每帧单位”。

![](img/d4175b7c7da94dffbf39910f5457f6a6_374.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_375.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_376.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_378.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_380.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_381.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_383.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_384.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_386.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_387.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_389.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_391.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_392.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_394.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_396.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_398.png)

以下是针对玩家移动音效的修复公式：

![](img/d4175b7c7da94dffbf39910f5457f6a6_400.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_401.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_403.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_405.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_407.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_409.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_411.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_412.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_414.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_415.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_417.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_418.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_419.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_420.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_422.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_424.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_426.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_427.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_428.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_429.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_430.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_432.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_434.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_435.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_437.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_439.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_441.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_442.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_443.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_445.png)

**原始问题代码：**
`target_volume = abs(player_target_dp); // dp 是每帧单位`

![](img/d4175b7c7da94dffbf39910f5457f6a6_446.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_447.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_449.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_450.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_452.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_454.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_455.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_457.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_459.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_461.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_463.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_465.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_467.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_469.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_471.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_473.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_475.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_477.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_479.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_480.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_482.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_483.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_485.png)

**修正后代码：**
`target_volume = abs(player_target_dp) * dt; // 转换为每秒单位，再通过dt转换为每帧变化量`

![](img/d4175b7c7da94dffbf39910f5457f6a6_487.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_489.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_490.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_492.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_494.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_496.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_498.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_500.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_502.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_503.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_505.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_507.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_509.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_511.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_513.png)

对于玩家模型的弹簧动画，我们使用了简谐运动公式来模拟滞后和拉伸效果：

![](img/d4175b7c7da94dffbf39910f5457f6a6_515.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_517.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_519.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_521.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_523.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_525.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_527.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_529.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_531.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_533.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_534.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_536.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_537.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_539.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_540.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_542.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_543.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_545.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_547.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_549.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_551.png)

```c
// 简化的弹簧系统更新
// desired_p: 目标位置（基于玩家输入）
// visual_p: 当前视觉位置
// visual_dp: 当前视觉速度
// spring_constant: 弹簧系数
// damping_constant: 阻尼系数

![](img/d4175b7c7da94dffbf39910f5457f6a6_553.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_555.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_557.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_559.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_561.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_562.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_564.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_566.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_568.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_570.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_572.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_573.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_575.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_577.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_579.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_581.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_583.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_585.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_587.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_589.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_591.png)

// 计算弹簧力 (Hooke‘s law)
vec2 spring_force = spring_constant * (desired_p - visual_p);
// 计算阻尼力
vec2 damping_force = damping_constant * (desired_dp - visual_dp);
// 计算加速度 (F = ma)
vec2 acceleration = (spring_force + damping_force) * dt; // 乘以 dt 确保帧率独立

![](img/d4175b7c7da94dffbf39910f5457f6a6_593.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_595.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_596.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_598.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_600.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_602.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_604.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_606.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_608.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_610.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_612.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_614.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_615.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_617.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_619.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_621.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_623.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_625.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_627.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_628.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_629.png)

// 更新速度和位置
visual_dp += acceleration;
visual_p += visual_dp * dt;
```

![](img/d4175b7c7da94dffbf39910f5457f6a6_631.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_633.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_635.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_636.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_638.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_640.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_642.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_643.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_645.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_647.png)

通过将加速度乘以 `dt`，我们确保了无论帧率高低，弹簧的物理行为都是一致的。

![](img/d4175b7c7da94dffbf39910f5457f6a6_649.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_651.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_653.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_655.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_657.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_659.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_661.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_663.png)

## 锁定帧率 🎯

![](img/d4175b7c7da94dffbf39910f5457f6a6_665.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_667.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_669.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_671.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_673.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_675.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_677.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_678.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_680.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_682.png)

为了保证一致的体验并简化动画调试，我们为游戏添加了帧率锁定功能。目标是稳定在60帧每秒（FPS）。

![](img/d4175b7c7da94dffbf39910f5457f6a6_684.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_686.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_687.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_689.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_691.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_693.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_695.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_697.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_698.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_699.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_700.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_702.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_704.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_706.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_707.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_709.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_711.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_713.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_715.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_717.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_718.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_720.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_722.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_724.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_726.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_728.png)

以下是实现帧率锁定的逻辑：

![](img/d4175b7c7da94dffbf39910f5457f6a6_730.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_732.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_734.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_735.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_737.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_738.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_739.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_740.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_741.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_743.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_744.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_745.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_747.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_749.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_751.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_753.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_755.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_757.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_759.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_761.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_763.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_765.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_767.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_769.png)

```c
double target_seconds_per_frame = 1.0 / 60.0; // 目标帧时间
double work_seconds_elapsed = ... // 计算游戏逻辑和渲染耗时

![](img/d4175b7c7da94dffbf39910f5457f6a6_771.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_773.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_775.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_777.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_779.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_781.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_783.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_785.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_787.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_788.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_790.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_792.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_794.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_796.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_797.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_799.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_801.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_803.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_805.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_806.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_808.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_809.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_811.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_813.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_815.png)

double seconds_elapsed_for_frame = work_seconds_elapsed;
if (seconds_elapsed_for_frame < target_seconds_per_frame) {
    // 如果本帧耗时少于目标时间，则休眠剩余时间
    double seconds_to_sleep = target_seconds_per_frame - seconds_elapsed_for_frame;
    DWORD milliseconds_to_sleep = (DWORD)(seconds_to_sleep * 1000.0);
    if (milliseconds_to_sleep > 0) {
        Sleep(milliseconds_to_sleep);
    }
    // 更新实际使用的帧时间
    seconds_elapsed_for_frame = target_seconds_per_frame;
}
dt = seconds_elapsed_for_frame; // 用于本帧所有基于时间的计算
```

![](img/d4175b7c7da94dffbf39910f5457f6a6_817.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_819.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_821.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_822.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_824.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_825.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_827.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_829.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_831.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_832.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_834.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_836.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_838.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_840.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_841.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_843.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_845.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_847.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_849.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_851.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_853.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_855.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_857.png)

锁定帧率后，动画和物理模拟的调试变得更加可预测。

![](img/d4175b7c7da94dffbf39910f5457f6a6_859.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_861.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_863.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_865.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_867.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_869.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_871.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_873.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_875.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_876.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_878.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_880.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_882.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_884.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_886.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_888.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_889.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_891.png)

## 游戏性增强与新动画 ✨

![](img/d4175b7c7da94dffbf39910f5457f6a6_893.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_895.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_897.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_899.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_901.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_903.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_905.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_907.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_909.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_911.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_913.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_914.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_916.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_918.png)

在解决了基础技术问题后，我们为游戏添加了新的视觉和听觉反馈。

![](img/d4175b7c7da94dffbf39910f5457f6a6_920.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_922.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_924.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_926.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_928.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_930.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_932.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_934.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_936.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_938.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_940.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_942.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_944.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_946.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_948.png)

### 能量块动画

![](img/d4175b7c7da94dffbf39910f5457f6a6_950.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_952.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_954.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_956.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_958.png)

能量块现在会呈现脉动动画，在生成时由小变大，以吸引玩家注意。

![](img/d4175b7c7da94dffbf39910f5457f6a6_960.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_962.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_964.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_966.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_967.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_969.png)

```c
// 能量块动画更新
power_block->animation_timer += dt * animation_speed_multiplier;
if (power_block->animation_timer > 1.0f) {
    power_block->animation_timer = 0.0f;
    power_block->animation_direction *= -1; // 反转动画方向
}

![](img/d4175b7c7da94dffbf39910f5457f6a6_971.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_973.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_975.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_976.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_978.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_980.png)

// 根据计时器计算当前缩放比例 (0.3 到 1.0 之间)
float t = power_block->animation_timer;
if (power_block->animation_direction < 0) {
    t = 1.0f - t;
}
float scale = 0.3f + 0.7f * t; // 线性插值
power_block->half_size_x = base_half_size * scale;
power_block->half_size_y = base_half_size * scale;
```

![](img/d4175b7c7da94dffbf39910f5457f6a6_982.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_984.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_986.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_987.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_989.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_991.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_993.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_995.png)

### 动态音效

![](img/d4175b7c7da94dffbf39910f5457f6a6_997.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_999.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_1001.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_1003.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_1004.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_1005.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_1007.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_1009.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_1011.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_1013.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_1015.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_1017.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_1019.png)

根据社区建议，我们为下落的能量块添加了音效，并且音调会随着其下落而升高，营造出紧迫感。

![](img/d4175b7c7da94dffbf39910f5457f6a6_1021.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_1023.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_1025.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_1027.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_1029.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_1031.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_1033.png)

```c
// 计算能量块在垂直方向上的归一化位置 (0=顶部， 1=底部)
float normalized_y = map_range(power_block->p.y,
                               arena_top,
                               arena_bottom,
                               0.0f, 1.0f);
// 位置越低，音调越高
float pitch_multiplier = 1.0f + normalized_y;
sound_set_pitch(power_block->sound_id, pitch_multiplier);

![](img/d4175b7c7da94dffbf39910f5457f6a6_1035.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_1037.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_1039.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_1041.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_1043.png)

// 多个能量块同时存在时，降低总音量以避免声音过大
float volume = 0.15f / (float)active_power_block_count;
sound_set_target_volume(power_block->sound_id, volume);
```

![](img/d4175b7c7da94dffbf39910f5457f6a6_1045.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_1047.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_1049.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_1051.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_1053.png)

### 关卡调整

![](img/d4175b7c7da94dffbf39910f5457f6a6_1055.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_1057.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_1059.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_1061.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_1062.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_1064.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_1066.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_1068.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_1070.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_1072.png)

我们还对现有关卡进行了微调，以提升游戏性和节奏：
*   **打砖块模式**：调整了砖块布局和球拍偏移量，使游戏流程更顺畅。
*   **乒乓球模式**：显著提升了AI对手的反应速度，并调整了起始位置，使对局更具挑战性。
*   **太空入侵者模式**：敌人移动速度现在会随着玩家击破砖块数量而增加，提高了游戏后期的难度。

![](img/d4175b7c7da94dffbf39910f5457f6a6_1074.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_1076.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_1078.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_1080.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_1081.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_1083.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_1085.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_1086.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_1088.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_1090.png)

## 总结 🏁

![](img/d4175b7c7da94dffbf39910f5457f6a6_1092.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_1094.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_1096.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_1098.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_1100.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_1102.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_1103.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_1105.png)

本节课中我们一起学习了多项游戏性改进的关键技术。

![](img/d4175b7c7da94dffbf39910f5457f6a6_1107.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_1109.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_1111.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_1113.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_1115.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_1117.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_1119.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_1121.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_1122.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_1124.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_1126.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_1128.png)

我们首先修复了鼠标光标在窗口切换时的异常行为，提升了游戏的稳定性。接着，我们深入解决了帧率依赖性问题，通过统一时间单位和使用帧率独立的物理公式，确保了玩家动画和音效在各种性能环境下表现一致。然后，我们实现了帧率锁定功能，为开发和测试提供了稳定的基础。

![](img/d4175b7c7da94dffbf39910f5457f6a6_1130.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_1132.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_1134.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_1136.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_1137.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_1139.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_1141.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_1142.png)

在内容层面，我们为能量块添加了吸引人的脉动动画和动态音效，并根据社区反馈调整了多个关卡的参数，显著提升了游戏的可玩性和挑战性。

![](img/d4175b7c7da94dffbf39910f5457f6a6_1144.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_1146.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_1148.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_1150.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_1152.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_1154.png)

![](img/d4175b7c7da94dffbf39910f5457f6a6_1156.png)

这些改进标志着我们的游戏从“可运行”向“打磨完善”又迈进了一步。在接下来的课程中，我们将继续完善碰撞系统，并可能添加新的关卡和最终的游戏润色。