# 008：粒子系统编程 🎮

![](img/13f3c34aeca4e45732e15609ba01749b_1.png)

![](img/13f3c34aeca4e45732e15609ba01749b_3.png)

![](img/13f3c34aeca4e45732e15609ba01749b_5.png)

![](img/13f3c34aeca4e45732e15609ba01749b_7.png)

![](img/13f3c34aeca4e45732e15609ba01749b_8.png)

![](img/13f3c34aeca4e45732e15609ba01749b_10.png)

![](img/13f3c34aeca4e45732e15609ba01749b_12.png)

![](img/13f3c34aeca4e45732e15609ba01749b_14.png)

![](img/13f3c34aeca4e45732e15609ba01749b_16.png)

![](img/13f3c34aeca4e45732e15609ba01749b_18.png)

![](img/13f3c34aeca4e45732e15609ba01749b_19.png)

![](img/13f3c34aeca4e45732e15609ba01749b_21.png)

![](img/13f3c34aeca4e45732e15609ba01749b_23.png)

在本节课中，我们将学习如何为游戏添加一个粒子系统。粒子系统可以极大地提升游戏的视觉效果，例如为球体添加轨迹、方块被摧毁时的爆炸效果等。我们将从修复一些遗留的Bug开始，然后逐步构建一个简单但功能强大的粒子系统。

![](img/13f3c34aeca4e45732e15609ba01749b_25.png)

![](img/13f3c34aeca4e45732e15609ba01749b_27.png)

![](img/13f3c34aeca4e45732e15609ba01749b_29.png)

![](img/13f3c34aeca4e45732e15609ba01749b_31.png)

![](img/13f3c34aeca4e45732e15609ba01749b_33.png)

![](img/13f3c34aeca4e45732e15609ba01749b_35.png)

![](img/13f3c34aeca4e45732e15609ba01749b_37.png)

![](img/13f3c34aeca4e45732e15609ba01749b_39.png)

![](img/13f3c34aeca4e45732e15609ba01749b_41.png)

![](img/13f3c34aeca4e45732e15609ba01749b_43.png)

## 概述与准备工作

![](img/13f3c34aeca4e45732e15609ba01749b_45.png)

![](img/13f3c34aeca4e45732e15609ba01749b_47.png)

![](img/13f3c34aeca4e45732e15609ba01749b_49.png)

![](img/13f3c34aeca4e45732e15609ba01749b_51.png)

![](img/13f3c34aeca4e45732e15609ba01749b_53.png)

![](img/13f3c34aeca4e45732e15609ba01749b_55.png)

![](img/13f3c34aeca4e45732e15609ba01749b_57.png)

![](img/13f3c34aeca4e45732e15609ba01749b_59.png)

![](img/13f3c34aeca4e45732e15609ba01749b_61.png)

上一节我们为游戏添加了一些视觉润色，如球体轨迹和玩家挤压拉伸动画，但也引入了一些Bug。本节我们将首先修复这些Bug，然后专注于实现粒子系统。

![](img/13f3c34aeca4e45732e15609ba01749b_63.png)

![](img/13f3c34aeca4e45732e15609ba01749b_64.png)

![](img/13f3c34aeca4e45732e15609ba01749b_66.png)

![](img/13f3c34aeca4e45732e15609ba01749b_68.png)

![](img/13f3c34aeca4e45732e15609ba01749b_70.png)

![](img/13f3c34aeca4e45732e15609ba01749b_72.png)

![](img/13f3c34aeca4e45732e15609ba01749b_74.png)

![](img/13f3c34aeca4e45732e15609ba01749b_76.png)

![](img/13f3c34aeca4e45732e15609ba01749b_78.png)

![](img/13f3c34aeca4e45732e15609ba01749b_80.png)

![](img/13f3c34aeca4e45732e15609ba01749b_82.png)

如果你希望下载游戏及其源代码，可以访问 [dayd.h.o](http://dayd.h.o)，下载上一个版本的执行文件和源代码，以便跟随编程。

![](img/13f3c34aeca4e45732e15609ba01749b_84.png)

![](img/13f3c34aeca4e45732e15609ba01749b_86.png)

![](img/13f3c34aeca4e45732e15609ba01749b_88.png)

![](img/13f3c34aeca4e45732e15609ba01749b_90.png)

![](img/13f3c34aeca4e45732e15609ba01749b_92.png)

![](img/13f3c34aeca4e45732e15609ba01749b_94.png)

## 修复遗留Bug

![](img/13f3c34aeca4e45732e15609ba01749b_96.png)

![](img/13f3c34aeca4e45732e15609ba01749b_98.png)

![](img/13f3c34aeca4e45732e15609ba01749b_100.png)

![](img/13f3c34aeca4e45732e15609ba01749b_102.png)

![](img/13f3c34aeca4e45732e15609ba01749b_104.png)

![](img/13f3c34aeca4e45732e15609ba01749b_106.png)

![](img/13f3c34aeca4e45732e15609ba01749b_107.png)

![](img/13f3c34aeca4e45732e15609ba01749b_109.png)

![](img/13f3c34aeca4e45732e15609ba01749b_111.png)

![](img/13f3c34aeca4e45732e15609ba01749b_113.png)

![](img/13f3c34aeca4e45732e15609ba01749b_115.png)

![](img/13f3c34aeca4e45732e15609ba01749b_117.png)

![](img/13f3c34aeca4e45732e15609ba01749b_119.png)

![](img/13f3c34aeca4e45732e15609ba01749b_121.png)

![](img/13f3c34aeca4e45732e15609ba01749b_123.png)

我们首先需要修复一个当多个球体撞击天花板时出现的严重Bug。这个Bug导致游戏逻辑混乱。

![](img/13f3c34aeca4e45732e15609ba01749b_125.png)

![](img/13f3c34aeca4e45732e15609ba01749b_127.png)

![](img/13f3c34aeca4e45732e15609ba01749b_129.png)

![](img/13f3c34aeca4e45732e15609ba01749b_131.png)

![](img/13f3c34aeca4e45732e15609ba01749b_133.png)

![](img/13f3c34aeca4e45732e15609ba01749b_135.png)

![](img/13f3c34aeca4e45732e15609ba01749b_137.png)

![](img/13f3c34aeca4e45732e15609ba01749b_139.png)

![](img/13f3c34aeca4e45732e15609ba01749b_141.png)

![](img/13f3c34aeca4e45732e15609ba01749b_143.png)

![](img/13f3c34aeca4e45732e15609ba01749b_144.png)

![](img/13f3c34aeca4e45732e15609ba01749b_146.png)

![](img/13f3c34aeca4e45732e15609ba01749b_148.png)

![](img/13f3c34aeca4e45732e15609ba01749b_150.png)

![](img/13f3c34aeca4e45732e15609ba01749b_151.png)

![](img/13f3c34aeca4e45732e15609ba01749b_153.png)

![](img/13f3c34aeca4e45732e15609ba01749b_155.png)

以下是重现和修复该Bug的步骤：

![](img/13f3c34aeca4e45732e15609ba01749b_157.png)

![](img/13f3c34aeca4e45732e15609ba01749b_159.png)

![](img/13f3c34aeca4e45732e15609ba01749b_161.png)

![](img/13f3c34aeca4e45732e15609ba01749b_163.png)

![](img/13f3c34aeca4e45732e15609ba01749b_165.png)

![](img/13f3c34aeca4e45732e15609ba01749b_166.png)

![](img/13f3c34aeca4e45732e15609ba01749b_168.png)

![](img/13f3c34aeca4e45732e15609ba01749b_170.png)

![](img/13f3c34aeca4e45732e15609ba01749b_172.png)

![](img/13f3c34aeca4e45732e15609ba01749b_174.png)

![](img/13f3c34aeca4e45732e15609ba01749b_176.png)

![](img/13f3c34aeca4e45732e15609ba01749b_178.png)

![](img/13f3c34aeca4e45732e15609ba01749b_180.png)

1.  创建一个可控的场景：生成10个“三连发”道具。
2.  当多个球体同时撞击天花板时，观察游戏行为异常。
3.  通过打印调试信息，我们发现问题是球体在非激活状态下仍然参与了某些循环计算。
4.  检查代码，发现一个拼写错误导致逻辑判断失误。将 `ball->active` 的错误引用更正。

![](img/13f3c34aeca4e45732e15609ba01749b_182.png)

**核心修复代码：**
```c
// 修复前的错误代码
if (ball->active) {
    // 处理逻辑...
}

![](img/13f3c34aeca4e45732e15609ba01749b_184.png)

![](img/13f3c34aeca4e45732e15609ba01749b_186.png)

![](img/13f3c34aeca4e45732e15609ba01749b_188.png)

![](img/13f3c34aeca4e45732e15609ba01749b_190.png)

![](img/13f3c34aeca4e45732e15609ba01749b_192.png)

![](img/13f3c34aeca4e45732e15609ba01749b_194.png)

![](img/13f3c34aeca4e45732e15609ba01749b_196.png)

![](img/13f3c34aeca4e45732e15609ba01749b_198.png)

![](img/13f3c34aeca4e45732e15609ba01749b_200.png)

![](img/13f3c34aeca4e45732e15609ba01749b_202.png)

![](img/13f3c34aeca4e45732e15609ba01749b_204.png)

![](img/13f3c34aeca4e45732e15609ba01749b_206.png)

![](img/13f3c34aeca4e45732e15609ba01749b_208.png)

![](img/13f3c34aeca4e45732e15609ba01749b_210.png)

![](img/13f3c34aeca4e45732e15609ba01749b_212.png)

// 修复后的正确代码
if (ball->active) {
    // 处理逻辑...
}
```
修复这个拼写错误后，天花板碰撞的Bug得以解决。

![](img/13f3c34aeca4e45732e15609ba01749b_214.png)

![](img/13f3c34aeca4e45732e15609ba01749b_216.png)

![](img/13f3c34aeca4e45732e15609ba01749b_218.png)

![](img/13f3c34aeca4e45732e15609ba01749b_220.png)

![](img/13f3c34aeca4e45732e15609ba01749b_221.png)

![](img/13f3c34aeca4e45732e15609ba01749b_223.png)

![](img/13f3c34aeca4e45732e15609ba01749b_225.png)

![](img/13f3c34aeca4e45732e15609ba01749b_226.png)

![](img/13f3c34aeca4e45732e15609ba01749b_228.png)

![](img/13f3c34aeca4e45732e15609ba01749b_230.png)

![](img/13f3c34aeca4e45732e15609ba01749b_232.png)

![](img/13f3c34aeca4e45732e15609ba01749b_234.png)

## 实现基础粒子系统

![](img/13f3c34aeca4e45732e15609ba01749b_236.png)

![](img/13f3c34aeca4e45732e15609ba01749b_237.png)

![](img/13f3c34aeca4e45732e15609ba01749b_239.png)

![](img/13f3c34aeca4e45732e15609ba01749b_241.png)

![](img/13f3c34aeca4e45732e15609ba01749b_243.png)

![](img/13f3c34aeca4e45732e15609ba01749b_245.png)

![](img/13f3c34aeca4e45732e15609ba01749b_247.png)

![](img/13f3c34aeca4e45732e15609ba01749b_249.png)

![](img/13f3c34aeca4e45732e15609ba01749b_251.png)

![](img/13f3c34aeca4e45732e15609ba01749b_253.png)

![](img/13f3c34aeca4e45732e15609ba01749b_255.png)

![](img/13f3c34aeca4e45732e15609ba01749b_257.png)

解决了主要Bug后，我们现在可以开始构建粒子系统。粒子系统的基本思想是管理一系列具有位置、速度、生命周期和颜色等属性的小对象（粒子）。

![](img/13f3c34aeca4e45732e15609ba01749b_259.png)

![](img/13f3c34aeca4e45732e15609ba01749b_261.png)

![](img/13f3c34aeca4e45732e15609ba01749b_263.png)

![](img/13f3c34aeca4e45732e15609ba01749b_265.png)

![](img/13f3c34aeca4e45732e15609ba01749b_267.png)

![](img/13f3c34aeca4e45732e15609ba01749b_269.png)

![](img/13f3c34aeca4e45732e15609ba01749b_270.png)

![](img/13f3c34aeca4e45732e15609ba01749b_272.png)

![](img/13f3c34aeca4e45732e15609ba01749b_274.png)

![](img/13f3c34aeca4e45732e15609ba01749b_276.png)

![](img/13f3c34aeca4e45732e15609ba01749b_278.png)

### 定义粒子结构

![](img/13f3c34aeca4e45732e15609ba01749b_280.png)

![](img/13f3c34aeca4e45732e15609ba01749b_282.png)

![](img/13f3c34aeca4e45732e15609ba01749b_284.png)

![](img/13f3c34aeca4e45732e15609ba01749b_285.png)

![](img/13f3c34aeca4e45732e15609ba01749b_287.png)

![](img/13f3c34aeca4e45732e15609ba01749b_289.png)

![](img/13f3c34aeca4e45732e15609ba01749b_291.png)

![](img/13f3c34aeca4e45732e15609ba01749b_293.png)

![](img/13f3c34aeca4e45732e15609ba01749b_295.png)

![](img/13f3c34aeca4e45732e15609ba01749b_297.png)

![](img/13f3c34aeca4e45732e15609ba01749b_299.png)

![](img/13f3c34aeca4e45732e15609ba01749b_301.png)

首先，我们需要定义一个结构体来代表单个粒子。

![](img/13f3c34aeca4e45732e15609ba01749b_303.png)

![](img/13f3c34aeca4e45732e15609ba01749b_305.png)

**粒子结构体代码：**
```c
typedef struct {
    V2 p;          // 位置
    V2 dp;         // 速度
    V2 half_size;  // 大小
    float life;    // 生命周期，从1.0到0.0
    u32 color;     // 颜色
} Particle;
```

![](img/13f3c34aeca4e45732e15609ba01749b_307.png)

![](img/13f3c34aeca4e45732e15609ba01749b_309.png)

![](img/13f3c34aeca4e45732e15609ba01749b_311.png)

### 初始化与渲染粒子

![](img/13f3c34aeca4e45732e15609ba01749b_313.png)

![](img/13f3c34aeca4e45732e15609ba01749b_315.png)

![](img/13f3c34aeca4e45732e15609ba01749b_317.png)

![](img/13f3c34aeca4e45732e15609ba01749b_319.png)

![](img/13f3c34aeca4e45732e15609ba01749b_321.png)

![](img/13f3c34aeca4e45732e15609ba01749b_323.png)

![](img/13f3c34aeca4e45732e15609ba01749b_325.png)

![](img/13f3c34aeca4e45732e15609ba01749b_327.png)

![](img/13f3c34aeca4e45732e15609ba01749b_329.png)

![](img/13f3c34aeca4e45732e15609ba01749b_331.png)

接下来，我们初始化一个粒子数组，并在每一帧中更新和渲染它们。

![](img/13f3c34aeca4e45732e15609ba01749b_333.png)

![](img/13f3c34aeca4e45732e15609ba01749b_335.png)

![](img/13f3c34aeca4e45732e15609ba01749b_337.png)

![](img/13f3c34aeca4e45732e15609ba01749b_339.png)

![](img/13f3c34aeca4e45732e15609ba01749b_341.png)

![](img/13f3c34aeca4e45732e15609ba01749b_343.png)

![](img/13f3c34aeca4e45732e15609ba01749b_344.png)

![](img/13f3c34aeca4e45732e15609ba01749b_346.png)

![](img/13f3c34aeca4e45732e15609ba01749b_348.png)

**粒子更新与渲染逻辑：**
```c
// 假设有一个全局粒子数组和索引
Particle particles[MAX_PARTICLES];
int next_particle = 0;

![](img/13f3c34aeca4e45732e15609ba01749b_350.png)

![](img/13f3c34aeca4e45732e15609ba01749b_352.png)

![](img/13f3c34aeca4e45732e15609ba01749b_354.png)

![](img/13f3c34aeca4e45732e15609ba01749b_356.png)

![](img/13f3c34aeca4e45732e15609ba01749b_358.png)

![](img/13f3c34aeca4e45732e15609ba01749b_360.png)

![](img/13f3c34aeca4e45732e15609ba01749b_362.png)

// 在游戏循环中更新粒子
for (int i = 0; i < MAX_PARTICLES; ++i) {
    Particle *particle = &particles[i];
    if (particle->life > 0.0f) {
        // 更新位置
        particle->p.x += particle->dp.x * dt;
        particle->p.y += particle->dp.y * dt;
        // 减少生命周期
        particle->life -= dt;
        // 根据生命周期设置透明度并渲染
        float alpha = particle->life; // 简单线性衰减
        u32 render_color = (particle->color & 0x00FFFFFF) | ((u32)(alpha * 255) << 24);
        draw_rectangle(particle->p, particle->half_size, render_color);
    }
}
```

![](img/13f3c34aeca4e45732e15609ba01749b_364.png)

![](img/13f3c34aeca4e45732e15609ba01749b_366.png)

![](img/13f3c34aeca4e45732e15609ba01749b_367.png)

![](img/13f3c34aeca4e45732e15609ba01749b_369.png)

![](img/13f3c34aeca4e45732e15609ba01749b_371.png)

![](img/13f3c34aeca4e45732e15609ba01749b_373.png)

![](img/13f3c34aeca4e45732e15609ba01749b_375.png)

![](img/13f3c34aeca4e45732e15609ba01749b_377.png)

![](img/13f3c34aeca4e45732e15609ba01749b_379.png)

![](img/13f3c34aeca4e45732e15609ba01749b_381.png)

![](img/13f3c34aeca4e45732e15609ba01749b_383.png)

![](img/13f3c34aeca4e45732e15609ba01749b_385.png)

### 生成粒子

![](img/13f3c34aeca4e45732e15609ba01749b_387.png)

![](img/13f3c34aeca4e45732e15609ba01749b_388.png)

![](img/13f3c34aeca4e45732e15609ba01749b_390.png)

![](img/13f3c34aeca4e45732e15609ba01749b_392.png)

![](img/13f3c34aeca4e45732e15609ba01749b_394.png)

![](img/13f3c34aeca4e45732e15609ba01749b_396.png)

![](img/13f3c34aeca4e45732e15609ba01749b_398.png)

![](img/13f3c34aeca4e45732e15609ba01749b_400.png)

![](img/13f3c34aeca4e45732e15609ba01749b_402.png)

![](img/13f3c34aeca4e45732e15609ba01749b_404.png)

![](img/13f3c34aeca4e45732e15609ba01749b_406.png)

![](img/13f3c34aeca4e45732e15609ba01749b_408.png)

![](img/13f3c34aeca4e45732e15609ba01749b_410.png)

![](img/13f3c34aeca4e45732e15609ba01749b_412.png)

我们需要一个函数来在特定位置生成（或“孵化”）粒子。

![](img/13f3c34aeca4e45732e15609ba01749b_414.png)

![](img/13f3c34aeca4e45732e15609ba01749b_416.png)

![](img/13f3c34aeca4e45732e15609ba01749b_418.png)

![](img/13f3c34aeca4e45732e15609ba01749b_420.png)

![](img/13f3c34aeca4e45732e15609ba01749b_422.png)

![](img/13f3c34aeca4e45732e15609ba01749b_424.png)

![](img/13f3c34aeca4e45732e15609ba01749b_426.png)

![](img/13f3c34aeca4e45732e15609ba01749b_428.png)

![](img/13f3c34aeca4e45732e15609ba01749b_430.png)

![](img/13f3c34aeca4e45732e15609ba01749b_432.png)

![](img/13f3c34aeca4e45732e15609ba01749b_434.png)

![](img/13f3c34aeca4e45732e15609ba01749b_436.png)

![](img/13f3c34aeca4e45732e15609ba01749b_438.png)

![](img/13f3c34aeca4e45732e15609ba01749b_440.png)

![](img/13f3c34aeca4e45732e15609ba01749b_442.png)

![](img/13f3c34aeca4e45732e15609ba01749b_444.png)

![](img/13f3c34aeca4e45732e15609ba01749b_446.png)

**生成粒子函数：**
```c
void spawn_particle(V2 p, V2 dp, V2 half_size, float life, u32 color) {
    Particle *particle = &particles[next_particle];
    next_particle = (next_particle + 1) % MAX_PARTICLES;

    particle->p = p;
    particle->dp = dp;
    particle->half_size = half_size;
    particle->life = life;
    particle->color = color;
}
```

![](img/13f3c34aeca4e45732e15609ba01749b_448.png)

![](img/13f3c34aeca4e45732e15609ba01749b_450.png)

![](img/13f3c34aeca4e45732e15609ba01749b_452.png)

![](img/13f3c34aeca4e45732e15609ba01749b_454.png)

![](img/13f3c34aeca4e45732e15609ba01749b_455.png)

![](img/13f3c34aeca4e45732e15609ba01749b_457.png)

![](img/13f3c34aeca4e45732e15609ba01749b_459.png)

![](img/13f3c34aeca4e45732e15609ba01749b_461.png)

![](img/13f3c34aeca4e45732e15609ba01749b_463.png)

![](img/13f3c34aeca4e45732e15609ba01749b_464.png)

![](img/13f3c34aeca4e45732e15609ba01749b_466.png)

![](img/13f3c34aeca4e45732e15609ba01749b_468.png)

![](img/13f3c34aeca4e45732e15609ba01749b_470.png)

![](img/13f3c34aeca4e45732e15609ba01749b_472.png)

## 应用粒子效果

![](img/13f3c34aeca4e45732e15609ba01749b_474.png)

![](img/13f3c34aeca4e45732e15609ba01749b_476.png)

![](img/13f3c34aeca4e45732e15609ba01749b_478.png)

![](img/13f3c34aeca4e45732e15609ba01749b_480.png)

有了基础的粒子系统，我们可以将其应用到游戏的不同场景中。

![](img/13f3c34aeca4e45732e15609ba01749b_482.png)

![](img/13f3c34aeca4e45732e15609ba01749b_484.png)

![](img/13f3c34aeca4e45732e15609ba01749b_486.png)

![](img/13f3c34aeca4e45732e15609ba01749b_488.png)

![](img/13f3c34aeca4e45732e15609ba01749b_490.png)

![](img/13f3c34aeca4e45732e15609ba01749b_491.png)

![](img/13f3c34aeca4e45732e15609ba01749b_493.png)

![](img/13f3c34aeca4e45732e15609ba01749b_495.png)

![](img/13f3c34aeca4e45732e15609ba01749b_496.png)

![](img/13f3c34aeca4e45732e15609ba01749b_498.png)

### 球体轨迹

![](img/13f3c34aeca4e45732e15609ba01749b_500.png)

![](img/13f3c34aeca4e45732e15609ba01749b_502.png)

![](img/13f3c34aeca4e45732e15609ba01749b_504.png)

![](img/13f3c34aeca4e45732e15609ba01749b_505.png)

![](img/13f3c34aeca4e45732e15609ba01749b_507.png)

![](img/13f3c34aeca4e45732e15609ba01749b_509.png)

![](img/13f3c34aeca4e45732e15609ba01749b_511.png)

![](img/13f3c34aeca4e45732e15609ba01749b_513.png)

将之前简单的球体轨迹替换为粒子系统。根据球体的速度动态调整生成粒子的频率和颜色。

![](img/13f3c34aeca4e45732e15609ba01749b_515.png)

![](img/13f3c34aeca4e45732e15609ba01749b_517.png)

![](img/13f3c34aeca4e45732e15609ba01749b_519.png)

![](img/13f3c34aeca4e45732e15609ba01749b_521.png)

![](img/13f3c34aeca4e45732e15609ba01749b_523.png)

![](img/13f3c34aeca4e45732e15609ba01749b_525.png)

![](img/13f3c34aeca4e45732e15609ba01749b_527.png)

![](img/13f3c34aeca4e45732e15609ba01749b_529.png)

**球体轨迹粒子生成：**
```c
// 在球体更新循环中
if (ball->active) {
    // 计算基于速度的粒子生成率
    float speed_sq = ball->dp.x * ball->dp.x + ball->dp.y * ball->dp.y;
    float spawn_rate = clamp(1.0f / (speed_sq * 0.01f), 0.1f, 1.0f);

    // 根据生成率决定是否生成粒子
    if (random_float() < spawn_rate * dt) {
        V2 trail_p = ball->p;
        V2 random_dp = {random_bilateral() * 2.0f, random_bilateral() * 2.0f};
        // 颜色可以根据速度变化，例如从深蓝到浅蓝
        float t = clamp((speed_sq - 2500.0f) / 10000.0f, 0.0f, 1.0f);
        u32 color = lerp_color(0xFF3333AA, 0xFF7777FF, t);
        spawn_particle(trail_p, random_dp, (V2){1.5f, 1.5f}, 0.3f, color);
    }
}
```

![](img/13f3c34aeca4e45732e15609ba01749b_531.png)

![](img/13f3c34aeca4e45732e15609ba01749b_533.png)

![](img/13f3c34aeca4e45732e15609ba01749b_535.png)

![](img/13f3c34aeca4e45732e15609ba01749b_537.png)

![](img/13f3c34aeca4e45732e15609ba01749b_539.png)

![](img/13f3c34aeca4e45732e15609ba01749b_541.png)

![](img/13f3c34aeca4e45732e15609ba01749b_543.png)

![](img/13f3c34aeca4e45732e15609ba01749b_545.png)

![](img/13f3c34aeca4e45732e15609ba01749b_547.png)

![](img/13f3c34aeca4e45732e15609ba01749b_549.png)

### 方块摧毁爆炸

![](img/13f3c34aeca4e45732e15609ba01749b_551.png)

![](img/13f3c34aeca4e45732e15609ba01749b_553.png)

![](img/13f3c34aeca4e45732e15609ba01749b_555.png)

![](img/13f3c34aeca4e45732e15609ba01749b_557.png)

![](img/13f3c34aeca4e45732e15609ba01749b_559.png)

![](img/13f3c34aeca4e45732e15609ba01749b_561.png)

![](img/13f3c34aeca4e45732e15609ba01749b_563.png)

![](img/13f3c34aeca4e45732e15609ba01749b_565.png)

![](img/13f3c34aeca4e45732e15609ba01749b_567.png)

![](img/13f3c34aeca4e45732e15609ba01749b_569.png)

当方块被球体击中摧毁时，生成一个爆炸性的粒子效果。

![](img/13f3c34aeca4e45732e15609ba01749b_571.png)

![](img/13f3c34aeca4e45732e15609ba01749b_573.png)

![](img/13f3c34aeca4e45732e15609ba01749b_575.png)

![](img/13f3c34aeca4e45732e15609ba01749b_577.png)

![](img/13f3c34aeca4e45732e15609ba01749b_579.png)

![](img/13f3c34aeca4e45732e15609ba01749b_581.png)

![](img/13f3c34aeca4e45732e15609ba01749b_583.png)

![](img/13f3c34aeca4e45732e15609ba01749b_585.png)

![](img/13f3c34aeca4e45732e15609ba01749b_587.png)

![](img/13f3c34aeca4e45732e15609ba01749b_589.png)

**方块摧毁粒子效果：**
```c
// 在方块摧毁的函数中
void on_block_destroyed(V2 block_p, u32 block_color) {
    int particle_count = 20;
    for (int i = 0; i < particle_count; ++i) {
        V2 random_dp = {
            random_float_in_range(-10.0f, 10.0f),
            random_float_in_range(-10.0f, 10.0f)
        };
        V2 random_size = {
            2.0f + random_bilateral() * 0.2f,
            2.0f + random_bilateral() * 0.2f
        };
        float life = 0.75f + random_bilateral() * 0.1f;
        spawn_particle(block_p, random_dp, random_size, life, block_color);
    }
}
```

![](img/13f3c34aeca4e45732e15609ba01749b_591.png)

![](img/13f3c34aeca4e45732e15609ba01749b_593.png)

![](img/13f3c34aeca4e45732e15609ba01749b_595.png)

![](img/13f3c34aeca4e45732e15609ba01749b_597.png)

![](img/13f3c34aeca4e45732e15609ba01749b_599.png)

![](img/13f3c34aeca4e45732e15609ba01749b_601.png)

![](img/13f3c34aeca4e45732e15609ba01749b_603.png)

![](img/13f3c34aeca4e45732e15609ba01749b_605.png)

![](img/13f3c34aeca4e45732e15609ba01749b_607.png)

![](img/13f3c34aeca4e45732e15609ba01749b_609.png)

![](img/13f3c34aeca4e45732e15609ba01749b_611.png)

![](img/13f3c34aeca4e45732e15609ba01749b_613.png)

![](img/13f3c34aeca4e45732e15609ba01749b_615.png)

### 墙壁撞击效果

![](img/13f3c34aeca4e45732e15609ba01749b_617.png)

![](img/13f3c34aeca4e45732e15609ba01749b_619.png)

![](img/13f3c34aeca4e45732e15609ba01749b_621.png)

![](img/13f3c34aeca4e45732e15609ba01749b_623.png)

![](img/13f3c34aeca4e45732e15609ba01749b_625.png)

![](img/13f3c34aeca4e45732e15609ba01749b_627.png)

![](img/13f3c34aeca4e45732e15609ba01749b_629.png)

![](img/13f3c34aeca4e45732e15609ba01749b_631.png)

![](img/13f3c34aeca4e45732e15609ba01749b_633.png)

![](img/13f3c34aeca4e45732e15609ba01749b_635.png)

![](img/13f3c34aeca4e45732e15609ba01749b_637.png)

![](img/13f3c34aeca4e45732e15609ba01749b_639.png)

同样地，当球体撞击墙壁时，也可以生成一小簇粒子，增强打击感。

![](img/13f3c34aeca4e45732e15609ba01749b_641.png)

![](img/13f3c34aeca4e45732e15609ba01749b_643.png)

![](img/13f3c34aeca4e45732e15609ba01749b_645.png)

![](img/13f3c34aeca4e45732e15609ba01749b_647.png)

![](img/13f3c34aeca4e45732e15609ba01749b_649.png)

![](img/13f3c34aeca4e45732e15609ba01749b_651.png)

![](img/13f3c34aeca4e45732e15609ba01749b_653.png)

![](img/13f3c34aeca4e45732e15609ba01749b_655.png)

![](img/13f3c34aeca4e45732e15609ba01749b_657.png)

![](img/13f3c34aeca4e45732e15609ba01749b_659.png)

![](img/13f3c34aeca4e45732e15609ba01749b_661.png)

## 视觉优化与调整

![](img/13f3c34aeca4e45732e15609ba01749b_663.png)

![](img/13f3c34aeca4e45732e15609ba01749b_665.png)

![](img/13f3c34aeca4e45732e15609ba01749b_667.png)

在实现了基本功能后，我们对粒子效果进行了一系列优化：

![](img/13f3c34aeca4e45732e15609ba01749b_669.png)

![](img/13f3c34aeca4e45732e15609ba01749b_671.png)

![](img/13f3c34aeca4e45732e15609ba01749b_672.png)

![](img/13f3c34aeca4e45732e15609ba01749b_674.png)

![](img/13f3c34aeca4e45732e15609ba01749b_676.png)

![](img/13f3c34aeca4e45732e15609ba01749b_678.png)

![](img/13f3c34aeca4e45732e15609ba01749b_680.png)

![](img/13f3c34aeca4e45732e15609ba01749b_682.png)

![](img/13f3c34aeca4e45732e15609ba01749b_684.png)

1.  **颜色动态变化**：使粒子颜色根据其速度或所属实体动态变化，增加视觉丰富度。
2.  **大小与生命周期随机化**：为爆炸粒子添加大小和生命周期的随机变化，使效果更自然。
3.  **性能限制**：为避免粒子数量爆炸导致性能问题，我们为粒子的生成率和总数设置了上限。
4.  **与游戏状态结合**：例如，当玩家获得“彗星”能力时，改变轨迹粒子的颜色和生命周期，使其看起来更炫酷。

![](img/13f3c34aeca4e45732e15609ba01749b_686.png)

![](img/13f3c34aeca4e45732e15609ba01749b_688.png)

![](img/13f3c34aeca4e45732e15609ba01749b_690.png)

![](img/13f3c34aeca4e45732e15609ba01749b_692.png)

![](img/13f3c34aeca4e45732e15609ba01749b_694.png)

![](img/13f3c34aeca4e45732e15609ba01749b_696.png)

![](img/13f3c34aeca4e45732e15609ba01749b_698.png)

![](img/13f3c34aeca4e45732e15609ba01749b_700.png)

![](img/13f3c34aeca4e45732e15609ba01749b_702.png)

## 总结

![](img/13f3c34aeca4e45732e15609ba01749b_704.png)

本节课中我们一起学习了如何为C语言游戏实现一个粒子系统。我们从修复一个多球体碰撞Bug开始，然后逐步构建了粒子的数据结构、更新渲染逻辑以及生成函数。我们将粒子系统应用到了球体轨迹、方块摧毁爆炸和墙壁撞击等多个场景中，并进行了颜色、大小、随机性等视觉优化。

![](img/13f3c34aeca4e45732e15609ba01749b_706.png)

通过添加粒子系统，游戏的视觉反馈和整体观感得到了显著提升。在接下来的课程中，我们将继续优化引擎，例如添加旋转矩形支持（让粒子轨迹更平滑）和音频系统，让游戏变得更加完整和有趣。

![](img/13f3c34aeca4e45732e15609ba01749b_708.png)

![](img/13f3c34aeca4e45732e15609ba01749b_710.png)

![](img/13f3c34aeca4e45732e15609ba01749b_712.png)

![](img/13f3c34aeca4e45732e15609ba01749b_714.png)

![](img/13f3c34aeca4e45732e15609ba01749b_716.png)

![](img/13f3c34aeca4e45732e15609ba01749b_717.png)

---
*教程内容源自直播流《【从零开始用C语言制作游戏】 p08 Making a game in C from scratch! Ep 08： -Programming a Particle Sys》，并依据要求进行了整理、翻译与重构。*