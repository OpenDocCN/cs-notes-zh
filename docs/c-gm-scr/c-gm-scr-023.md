# 023：游戏完成！🎮

![](img/c990a1d1bc1607ec62b9419da49f4cdf_1.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_3.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_5.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_7.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_9.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_11.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_12.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_14.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_16.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_18.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_20.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_22.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_24.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_25.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_27.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_29.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_31.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_33.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_35.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_37.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_39.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_41.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_43.png)

在本节课中，我们将一起回顾并完成游戏的最终开发工作。我们将重点修复音频系统的多线程崩溃问题，并进行一些最后的打磨，例如居中显示文本、添加配置选项等，为游戏在Steam平台上的发布做好准备。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_45.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_47.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_49.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_51.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_53.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_55.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_57.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_58.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_60.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_62.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_64.png)

---

![](img/c990a1d1bc1607ec62b9419da49f4cdf_66.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_68.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_70.png)

## 概述与目标 🎯

![](img/c990a1d1bc1607ec62b9419da49f4cdf_72.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_74.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_76.png)

大家好，欢迎来到“从零开始用C语言制作游戏”系列的第23次直播。从第一行代码开始，我们已经一起见证了游戏的整个开发过程。现在，正如屏幕上所示，我们非常接近在Steam上发布这款游戏了。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_78.png)

我们的主要目标是希望今天能完成开发，或者至少取得重大进展，因为我计划在下周（2019年9月20日，星期五）发布它。为了实现这个目标，我们还有一些收尾工作需要处理。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_80.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_82.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_84.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_86.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_88.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_90.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_92.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_94.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_96.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_97.png)

以下是今天的主要任务：
1.  **修复音频系统**：上次直播我们改进了音频，但效果不佳，并且在直播结束时出现了崩溃，今天需要快速修复。
2.  **进行一些打磨工作**：可能包括调整游戏难度、优化视觉效果等。
3.  **添加配置选项**：例如解锁帧率限制。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_99.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_101.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_103.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_105.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_107.png)

如果你希望跟随学习，可以在我的网站下载游戏和源代码。你也可以在YouTube上观看整个开发过程的直播录像。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_109.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_111.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_113.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_115.png)

现在，让我们开始吧！

![](img/c990a1d1bc1607ec62b9419da49f4cdf_117.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_119.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_121.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_123.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_125.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_127.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_129.png)

---

![](img/c990a1d1bc1607ec62b9419da49f4cdf_131.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_133.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_135.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_137.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_139.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_141.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_143.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_145.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_147.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_149.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_151.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_152.png)

## 修复音频系统崩溃 🔧

![](img/c990a1d1bc1607ec62b9419da49f4cdf_154.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_156.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_158.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_159.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_161.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_162.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_164.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_166.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_168.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_169.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_171.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_173.png)

上一节我们介绍了游戏接近完成的状态，本节中我们来看看如何解决最棘手的音频崩溃问题。这个问题源于我们的音频系统是多线程的：一个线程负责播放声音，另一个线程（主线程）可能同时请求播放新的声音，导致数据竞争和崩溃。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_175.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_177.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_179.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_181.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_183.png)

### 核心问题分析

![](img/c990a1d1bc1607ec62b9419da49f4cdf_185.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_187.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_189.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_191.png)

问题的核心在于，当游戏线程（例如，在生成粒子效果时）调用 `play_sound` 函数来启动一个声音时，它可能会修改一个正在被音频线程读取和处理的 `playing_sound` 结构体。这种不加保护的并发访问导致了未定义行为，通常是崩溃。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_193.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_195.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_197.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_199.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_201.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_203.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_205.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_207.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_209.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_211.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_213.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_214.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_216.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_218.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_220.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_221.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_223.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_225.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_227.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_228.png)

### 解决方案：实现自旋锁

![](img/c990a1d1bc1607ec62b9419da49f4cdf_230.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_232.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_234.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_236.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_238.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_239.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_241.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_243.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_245.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_247.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_249.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_251.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_253.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_255.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_257.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_259.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_261.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_263.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_265.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_267.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_269.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_271.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_272.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_274.png)

为了解决这个问题，我们需要在访问共享的 `playing_sound` 数据时进行同步。我们将为每个 `playing_sound` 结构体添加一个简单的锁机制。这里我们使用一个原子操作来实现一个“自旋锁”。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_276.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_278.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_280.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_282.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_284.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_286.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_288.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_290.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_292.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_294.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_296.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_297.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_299.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_301.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_303.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_305.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_307.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_309.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_311.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_313.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_315.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_317.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_319.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_321.png)

首先，我们在 `playing_sound` 结构体中添加一个状态标志：

![](img/c990a1d1bc1607ec62b9419da49f4cdf_323.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_325.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_327.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_329.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_331.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_333.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_335.png)

```c
typedef struct {
    // ... 其他成员（声音数据、位置、音量等）
    volatile u32 access; // 访问状态标志：SOUND_NORMAL, SOUND_READING, SOUND_WRITING
} playing_sound;

![](img/c990a1d1bc1607ec62b9419da49f4cdf_337.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_339.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_341.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_343.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_345.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_347.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_349.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_351.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_352.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_354.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_356.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_358.png)

#define SOUND_NORMAL 0
#define SOUND_READING 1
#define SOUND_WRITING 2
```

![](img/c990a1d1bc1607ec62b9419da49f4cdf_360.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_362.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_364.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_366.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_368.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_370.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_372.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_374.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_376.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_378.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_380.png)

然后，我们修改 `play_sound` 函数。在尝试使用一个空闲的声音槽位之前，我们必须先“锁定”它（将其状态从 `SOUND_NORMAL` 改为 `SOUND_WRITING`）。我们使用原子比较交换操作来确保这个更改是线程安全的：

![](img/c990a1d1bc1607ec62b9419da49f4cdf_382.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_384.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_386.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_388.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_390.png)

```c
// 在 play_sound 函数中寻找空闲声音槽位的部分
for(u32 sound_index = 0; sound_index < immutable_sound_count; ++sound_index) {
    playing_sound *sound = playing_sounds + ((next_playing_sound + sound_index) % immutable_sound_count);
    
    volatile u32 original_access = SOUND_NORMAL;
    volatile u32 new_access = SOUND_WRITING;
    
    // 原子操作：只有当 sound->access 等于 original_access (SOUND_NORMAL) 时，才将其设置为 new_access (SOUND_WRITING)
    u32 result = InterlockedCompareExchange((volatile LONG*)&sound->access, new_access, original_access);
    
    if(result == original_access) {
        // 成功锁定！现在可以安全地初始化这个声音槽位
        sound->samples = samples;
        sound->sample_count = sample_count;
        // ... 设置其他参数 ...
        sound->active = true;
        
        // 操作完成后，将状态改回 SOUND_NORMAL，允许音频线程读取
        sound->access = SOUND_NORMAL;
        
        // ... 更新 next_playing_sound 等 ...
        break;
    }
    // 如果锁定失败（状态不是 NORMAL），则继续尝试下一个槽位
}
```

![](img/c990a1d1bc1607ec62b9419da49f4cdf_392.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_394.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_396.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_398.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_400.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_402.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_404.png)

同样地，在音频线程的 `update_game_audio` 函数中，在读取和处理一个声音之前，也需要先获取锁（将其状态从 `SOUND_NORMAL` 改为 `SOUND_READING`），处理完毕后再释放。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_406.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_407.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_409.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_411.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_413.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_415.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_417.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_419.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_421.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_423.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_425.png)

### 关键概念：原子操作与 volatile 关键字

![](img/c990a1d1bc1607ec62b9419da49f4cdf_427.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_429.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_431.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_433.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_435.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_437.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_439.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_441.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_443.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_444.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_446.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_448.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_450.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_452.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_454.png)

*   **原子操作**：像 `InterlockedCompareExchange` 这样的操作确保“比较”和“交换”这两个步骤作为一个不可分割的整体执行。这防止了另一个线程在我们“比较”之后但“交换”之前修改目标值，这是实现无锁数据结构或轻量级锁的基础。
*   **volatile 关键字**：它告诉编译器和CPU，这个变量的值可能会被当前线程之外的代理（例如另一个线程）意外更改，因此禁止对其进行某些优化（例如将变量值缓存到寄存器中）。在多线程编程中，对共享变量使用 `volatile` 是必要的，但请注意，`volatile` **本身并不提供原子性或互斥性**，它只是防止了编译器层面的优化错误。同步仍然需要依靠原子操作或锁。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_456.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_458.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_460.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_462.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_464.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_466.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_468.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_470.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_472.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_474.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_476.png)

通过实现这个简单的状态锁，我们确保了同一时间只有一个线程能对某个 `playing_sound` 实例进行写入或读取操作，从而解决了数据竞争导致的崩溃问题。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_478.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_480.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_482.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_484.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_486.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_488.png)

---

![](img/c990a1d1bc1607ec62b9419da49f4cdf_490.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_492.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_494.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_496.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_498.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_500.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_502.png)

## 游戏打磨与优化 ✨

![](img/c990a1d1bc1607ec62b9419da49f4cdf_503.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_505.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_507.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_509.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_511.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_513.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_515.png)

解决了核心的音频崩溃后，我们可以进行一些提升游戏体验的打磨工作。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_517.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_519.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_521.png)

### 居中显示分数文本

![](img/c990a1d1bc1607ec62b9419da49f4cdf_523.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_525.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_527.png)

在游戏主菜单中，我们发现分数数字没有像其他文本一样居中显示，这影响了视觉效果。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_529.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_531.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_533.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_535.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_537.png)

以下是解决方案的思路：
1.  在绘制数字字符串之前，先计算整个字符串的总像素宽度。
2.  由于我们的数字字体中，数字“1”比其他数字窄，需要特殊处理。
3.  计算出总宽度后，将起始绘制位置向左移动“总宽度的一半”，即可实现居中。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_539.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_541.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_543.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_545.png)

我们修改了 `draw_number` 函数，在正式绘制前先遍历一遍所有数字字符，计算总宽度和最后一个字符的宽度，然后调整绘制起点。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_547.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_549.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_551.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_553.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_555.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_557.png)

```c
// 修改后的 draw_number 函数片段（概念代码）
s32 total_width = 0;
s32 last_char_width = 0;
for(u32 digit_index = 0; digit_index < digit_count; ++digit_index) {
    u32 digit = digits[digit_index];
    s32 char_width = (digit == 1) ? (2 * square_dim) : (4 * square_dim);
    total_width += char_width;
    if(digit_index == digit_count - 1) {
        last_char_width = char_width;
    }
}
// 调整起始X坐标：原坐标 - 总宽度/2 + 最后一个字符宽度/2（用于微调）
p.x = center_x - total_width/2 + last_char_width/2;
// 然后进行实际的绘制循环
```

![](img/c990a1d1bc1607ec62b9419da49f4cdf_559.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_561.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_563.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_565.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_567.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_569.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_571.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_573.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_575.png)

### 添加垂直同步（V-Sync）配置选项

![](img/c990a1d1bc1607ec62b9419da49f4cdf_577.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_579.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_581.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_583.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_585.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_587.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_589.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_591.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_593.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_595.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_597.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_599.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_601.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_603.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_605.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_607.png)

为了让游戏运行更平滑，我们之前锁定了帧率。现在，我们通过游戏的配置文件（.fig）来提供是否锁定帧率的选项，让玩家可以自行选择。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_609.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_610.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_612.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_614.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_616.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_618.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_620.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_622.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_624.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_626.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_628.png)

首先，在解析配置文件的代码中添加对新键值对的识别：
```c
// 在 parse_fig_file 函数中
else if(strings_are_equal(identifier, “locked_fps”)) {
    game_config->locked_fps = string_to_bool(value);
}
```

![](img/c990a1d1bc1607ec62b9419da49f4cdf_630.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_632.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_634.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_636.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_638.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_640.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_642.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_644.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_646.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_647.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_649.png)

然后，在游戏主循环中，根据 `game_config->locked_fps` 的值来决定是否进行睡眠以控制帧率。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_651.png)

```c
// 游戏主循环片段
while(running) {
    // ... 处理输入、更新游戏、渲染 ...
    
    if(game_config->locked_fps) {
        // 计算本帧耗时，并睡眠以确保帧率稳定（例如60FPS）
        Sleep(calculate_sleep_time());
    }
}
```

![](img/c990a1d1bc1607ec62b9419da49f4cdf_653.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_655.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_657.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_659.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_660.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_662.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_664.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_666.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_668.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_670.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_672.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_674.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_675.png)

### 其他小改进

![](img/c990a1d1bc1607ec62b9419da49f4cdf_677.png)

*   **鼠标光标**：我们改进了逻辑，在游戏窗口激活时，每帧都将鼠标光标重置到屏幕中心，以防止它意外移出窗口。虽然在全屏双显示器下可能仍有极端情况，但这是一个常见的解决方案。
*   **俄罗斯方块关卡反馈**：在俄罗斯方块关卡中，当方块旋转时，我们添加了声音效果和粒子特效，让游戏反馈更加清晰和有趣。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_679.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_681.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_682.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_684.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_686.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_688.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_690.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_692.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_694.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_696.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_698.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_700.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_702.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_704.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_705.png)

---

![](img/c990a1d1bc1607ec62b9419da49f4cdf_707.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_709.png)

## 总结与展望 🚀

![](img/c990a1d1bc1607ec62b9419da49f4cdf_711.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_713.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_715.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_717.png)

在本节课中，我们一起完成了游戏的最终开发冲刺。我们深入探讨并解决了一个复杂的多线程音频崩溃问题，通过实现原子操作和状态标志实现了简单的线程同步。此外，我们还对游戏进行了多项打磨工作，包括居中显示文本、添加帧率控制选项、增强关卡反馈等，显著提升了游戏的完成度和用户体验。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_719.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_721.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_723.png)

回顾整个系列，我们从零开始，实现了窗口创建、软件渲染、物理碰撞、粒子系统、音频播放、关卡设计、配置文件解析等一系列功能，最终完成了一个包含多种游戏模式（打砖块、太空侵略者、俄罗斯方块）的可玩、可发布的游戏。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_725.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_727.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_729.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_731.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_733.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_735.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_737.png)

**游戏现已完成开发！** 接下来的直播将是发布庆祝活动，我们将正式在Steam上推出这款游戏。感谢所有一路跟随这个系列的朋友，你们的观看和互动给了我巨大的动力。通过这个项目，我不仅完成了一款游戏，更深入学习了C语言、系统编程和游戏开发的诸多细节。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_739.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_741.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_743.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_745.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_747.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_749.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_751.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_753.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_755.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_757.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_759.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_761.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_763.png)

对于未来，我计划以此为基础，开始构建一个更通用、模块化的2D游戏引擎，并开发更多不同类型的游戏。如果你对游戏开发、引擎构建或编程学习感兴趣，欢迎继续关注我的频道。

![](img/c990a1d1bc1607ec62b9419da49f4cdf_765.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_767.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_769.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_771.png)

![](img/c990a1d1bc1607ec62b9419da49f4cdf_773.png)

再次感谢大家，我们下次直播（发布日）见！