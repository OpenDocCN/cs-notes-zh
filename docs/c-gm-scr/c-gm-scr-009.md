# 009：图形编程 - 旋转矩形 🎮

![](img/886a749eaaa9f80910ebb04a9f92609c_1.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_2.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_4.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_5.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_7.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_9.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_11.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_13.png)

## 概述
在本节课中，我们将学习如何为我们的游戏引擎添加绘制旋转矩形的功能。我们将从基础概念开始，逐步实现旋转矩阵、点积投影和边界框优化，最终将这一功能应用到粒子系统中，使游戏视觉效果更加丰富。

![](img/886a749eaaa9f80910ebb04a9f92609c_15.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_17.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_19.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_21.png)

---

![](img/886a749eaaa9f80910ebb04a9f92609c_23.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_25.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_27.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_29.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_31.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_33.png)

## 回顾与目标设定
上一节我们专注于游戏玩法，改进了场地、动画并添加了粒子系统。本节中，我们将暂时后退一步，专注于增强游戏引擎的图形功能，使其更加健壮，以便实现更酷的效果。

![](img/886a749eaaa9f80910ebb04a9f92609c_35.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_37.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_39.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_41.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_43.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_45.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_47.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_49.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_51.png)

我们注意到需要实现几个功能，其中最主要的是绘制旋转的矩形和位图。今天我们将从旋转矩形开始。

![](img/886a749eaaa9f80910ebb04a9f92609c_53.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_55.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_57.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_59.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_61.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_63.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_64.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_66.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_68.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_70.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_72.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_74.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_76.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_78.png)

---

![](img/886a749eaaa9f80910ebb04a9f92609c_80.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_82.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_84.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_86.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_88.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_90.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_92.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_94.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_96.png)

## 基础渲染系统
目前，我们的Windows平台层创建并分配了一个像素缓冲区，游戏通过`render_buffer`结构体访问它。我们建立了一个非常基础的渲染系统，可以执行各种操作，例如绘制矩形像素、绘制透明矩形、绘制警报等。我们还做了一些独立的功能，比如像素坐标与世界坐标的转换，以及一些辅助函数。

![](img/886a749eaaa9f80910ebb04a9f92609c_98.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_100.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_102.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_104.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_106.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_108.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_110.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_112.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_114.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_116.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_118.png)

现在，我们需要添加一个绘制旋转矩形的函数。

![](img/886a749eaaa9f80910ebb04a9f92609c_120.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_122.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_124.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_126.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_128.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_130.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_132.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_134.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_135.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_136.png)

---

![](img/886a749eaaa9f80910ebb04a9f92609c_138.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_140.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_141.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_143.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_145.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_146.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_148.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_150.png)

## 实现旋转矩形绘制函数
我们将创建一个名为`draw_rotated_rect`的函数。它的基本思路是接收位置、尺寸、角度和颜色作为参数。

![](img/886a749eaaa9f80910ebb04a9f92609c_152.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_154.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_156.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_158.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_160.png)

首先，我们需要计算旋转后矩形的顶点。我们从一个未旋转的矩形开始，其顶点由中心点和半尺寸定义。

![](img/886a749eaaa9f80910ebb04a9f92609c_162.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_164.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_166.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_168.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_170.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_172.png)

为了旋转这些点，我们需要将其视为矩阵变换。一个2D旋转矩阵定义如下：

![](img/886a749eaaa9f80910ebb04a9f92609c_174.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_176.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_178.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_180.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_182.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_184.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_186.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_188.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_190.png)

**公式：**
```
[ cos(θ)  -sin(θ) ]
[ sin(θ)   cos(θ) ]
```

![](img/886a749eaaa9f80910ebb04a9f92609c_192.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_194.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_195.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_197.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_199.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_201.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_203.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_205.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_207.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_209.png)

我们将为每个顶点构建并应用这个旋转矩阵。

![](img/886a749eaaa9f80910ebb04a9f92609c_211.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_213.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_215.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_217.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_219.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_221.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_223.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_225.png)

以下是初始的函数框架和矩阵乘法辅助函数：

![](img/886a749eaaa9f80910ebb04a9f92609c_227.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_229.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_231.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_233.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_235.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_237.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_239.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_241.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_243.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_245.png)

```c
internal void
draw_rotated_rect(render_buffer *renderer, v2 p, v2 half_size, f32 angle, u32 color) {
    // 将角度从度转换为弧度
    f32 angle_rad = degrees_to_radians(angle);

    // 计算正弦和余弦
    f32 cos_theta = cosf(angle_rad);
    f32 sin_theta = sinf(angle_rad);

    // 构建旋转矩阵
    m2 rotation_matrix = {cos_theta, -sin_theta,
                          sin_theta,  cos_theta};

    // 定义未旋转的矩形四个顶点（相对于中心）
    v2 points[4];
    points[0] = v2{-half_size.x, -half_size.y}; // 左下
    points[1] = v2{ half_size.x, -half_size.y}; // 右下
    points[2] = v2{ half_size.x,  half_size.y}; // 右上
    points[3] = v2{-half_size.x,  half_size.y}; // 左上

    // 旋转每个顶点
    for (int i = 0; i < 4; ++i) {
        points[i] = multiply_m2_v2(rotation_matrix, points[i]);
        // 加上中心位置，转换到世界坐标
        points[i] = v2_add(points[i], p);
        // 可选：在此处进行世界坐标到像素坐标的转换
    }

    // ... 后续进行绘制或碰撞检测
}

![](img/886a749eaaa9f80910ebb04a9f92609c_247.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_249.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_251.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_253.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_255.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_257.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_259.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_261.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_263.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_265.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_267.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_269.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_271.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_273.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_275.png)

// 2x2 矩阵与 2D 向量乘法
internal v2
multiply_m2_v2(m2 m, v2 v) {
    v2 result;
    result.x = m.e[0][0] * v.x + m.e[0][1] * v.y;
    result.y = m.e[1][0] * v.x + m.e[1][1] * v.y;
    return result;
}
```

![](img/886a749eaaa9f80910ebb04a9f92609c_277.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_279.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_281.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_283.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_285.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_287.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_289.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_291.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_293.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_295.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_297.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_299.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_301.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_303.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_305.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_307.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_309.png)

---

![](img/886a749eaaa9f80910ebb04a9f92609c_311.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_313.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_315.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_317.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_319.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_321.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_323.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_325.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_327.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_329.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_331.png)

## 碰撞检测：点与旋转矩形
仅仅绘制旋转矩形还不够，我们还需要检测像素点是否在旋转矩形内，以便进行填充绘制。这与轴对齐边界框（AABB）的检测不同，我们需要进行**定向边界框（OBB）**的检测。

![](img/886a749eaaa9f80910ebb04a9f92609c_333.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_335.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_337.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_339.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_341.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_343.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_345.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_347.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_349.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_351.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_353.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_355.png)

基本思想是：对于矩形的每条边，我们将其视为一个轴。要测试一个点`P`是否在矩形内，我们将点`P`投影到每条边的法线轴（或从矩形中心到顶点的向量）上，并检查投影是否在矩形在该轴上的投影范围内。

![](img/886a749eaaa9f80910ebb04a9f92609c_357.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_359.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_361.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_363.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_365.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_367.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_369.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_371.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_373.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_375.png)

以下是检测步骤的概述：

![](img/886a749eaaa9f80910ebb04a9f92609c_377.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_379.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_381.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_383.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_384.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_386.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_388.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_390.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_392.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_394.png)

1.  获取旋转矩形的四个顶点。
2.  计算矩形的两条主轴（例如，从`points[0]`到`points[1]`的向量，以及从`points[0]`到`points[3]`的向量）。
3.  对于要测试的每个像素点，计算其到矩形中心（或一个顶点）的向量。
4.  将该向量分别投影到两个主轴上。
5.  检查每个投影值是否在矩形在该轴上的最小和最大投影值之间。如果所有条件都满足，则点在矩形内。

![](img/886a749eaaa9f80910ebb04a9f92609c_396.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_398.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_400.png)

我们在`draw_rotated_rect`函数内部实现了这个逻辑，用于决定是否绘制该像素。

![](img/886a749eaaa9f80910ebb04a9f92609c_402.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_404.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_406.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_408.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_410.png)

---

![](img/886a749eaaa9f80910ebb04a9f92609c_412.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_413.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_415.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_417.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_419.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_421.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_423.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_425.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_427.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_429.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_431.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_433.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_435.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_437.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_439.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_441.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_443.png)

## 性能优化：边界框裁剪
在渲染函数中，我们最初遍历了整个屏幕的像素来测试碰撞，这是非常低效的。我们可以通过计算旋转矩形在屏幕上的**轴向包围盒（AABB）**来大幅优化性能。

![](img/886a749eaaa9f80910ebb04a9f92609c_445.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_447.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_449.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_451.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_453.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_455.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_457.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_459.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_461.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_463.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_465.png)

即使矩形是旋转的，我们也可以找到其所有顶点在X和Y方向上的最小值和最大值，从而得到一个能包围旋转矩形的、轴对齐的边界框。我们只需要遍历这个边界框内的像素即可。

![](img/886a749eaaa9f80910ebb04a9f92609c_467.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_469.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_471.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_473.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_475.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_477.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_479.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_481.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_483.png)

以下是优化步骤：

![](img/886a749eaaa9f80910ebb04a9f92609c_485.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_487.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_489.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_491.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_493.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_495.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_497.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_499.png)

1.  在计算了旋转矩形的四个顶点（像素坐标）后，找出它们的最小和最大X、Y值。
2.  将这些边界值钳制到屏幕缓冲区范围内。
3.  只在这个缩小后的矩形区域内循环遍历像素。

![](img/886a749eaaa9f80910ebb04a9f92609c_501.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_503.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_505.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_506.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_508.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_510.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_512.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_514.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_515.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_517.png)

```c
// 计算边界框
i32 min_x = (i32)floorf(min(min(points[0].x, points[1].x), min(points[2].x, points[3].x)));
i32 max_x = (i32)ceilf(max(max(points[0].x, points[1].x), max(points[2].x, points[3].x)));
i32 min_y = (i32)floorf(min(min(points[0].y, points[1].y), min(points[2].y, points[3].y)));
i32 max_y = (i32)ceilf(max(max(points[0].y, points[1].y), max(points[2].y, points[3].y)));

![](img/886a749eaaa9f80910ebb04a9f92609c_519.png)

// 钳制到屏幕范围
min_x = clamp(min_x, 0, renderer->width - 1);
max_x = clamp(max_x, 0, renderer->width - 1);
min_y = clamp(min_y, 0, renderer->height - 1);
max_y = clamp(max_y, 0, renderer->height - 1);

![](img/886a749eaaa9f80910ebb04a9f92609c_521.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_523.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_525.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_527.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_529.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_531.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_533.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_535.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_537.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_539.png)

// 只遍历边界框内的像素
for (i32 y = min_y; y <= max_y; ++y) {
    for (i32 x = min_x; x <= max_x; ++x) {
        // ... 点与OBB碰撞检测 ...
    }
}
```

![](img/886a749eaaa9f80910ebb04a9f92609c_541.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_543.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_545.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_546.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_548.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_550.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_552.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_554.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_556.png)

---

![](img/886a749eaaa9f80910ebb04a9f92609c_558.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_560.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_561.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_563.png)

## 整合到粒子系统
实现基础功能后，我们创建了一个`draw_transparent_rotated_rect`函数，它支持透明度（alpha混合）。

![](img/886a749eaaa9f80910ebb04a9f92609c_565.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_567.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_569.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_571.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_573.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_575.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_577.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_579.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_580.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_582.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_584.png)

然后，我们将旋转矩形功能整合到粒子系统中：
1.  修改粒子生成函数，为每个粒子添加一个随机的初始旋转角度。
2.  对于球体的轨迹粒子，我们根据球体的运动方向计算一个“朝向”角度，使粒子矩形与运动方向对齐。这可以通过计算速度向量的反正切（`atan2`）来实现。

![](img/886a749eaaa9f80910ebb04a9f92609c_586.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_588.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_590.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_592.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_594.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_596.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_598.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_600.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_602.png)

**公式：**
```
angle = atan2(velocity.y, velocity.x) // 结果在 -π 到 π 弧度之间
```
注意需要将弧度转换为度，并根据我们的坐标系进行可能的偏移（例如减去90度）。

![](img/886a749eaaa9f80910ebb04a9f92609c_604.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_606.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_608.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_610.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_612.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_614.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_616.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_618.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_620.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_622.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_624.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_626.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_628.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_630.png)

整合后，游戏中的粒子效果（如球体轨迹、方块爆炸）变得更加生动和逼真。

![](img/886a749eaaa9f80910ebb04a9f92609c_632.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_634.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_636.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_638.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_639.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_641.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_643.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_645.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_647.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_649.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_651.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_652.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_654.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_656.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_658.png)

---

![](img/886a749eaaa9f80910ebb04a9f92609c_660.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_662.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_664.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_666.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_667.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_669.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_670.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_672.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_674.png)

## 总结
本节课我们一起学习了图形编程中的一个核心概念：旋转矩形的绘制与碰撞检测。

![](img/886a749eaaa9f80910ebb04a9f92609c_676.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_678.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_680.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_682.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_684.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_686.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_688.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_690.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_692.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_694.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_696.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_698.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_700.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_701.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_703.png)

我们完成的工作包括：
1.  **理解旋转矩阵**：学习了如何用2x2矩阵表示2D旋转。
2.  **实现顶点变换**：通过矩阵乘法计算旋转后矩形的顶点。
3.  **定向边界框（OBB）碰撞检测**：使用点积投影方法判断点是否在旋转矩形内。
4.  **性能优化**：通过计算轴对齐包围盒（AABB）来限制像素遍历范围，大幅提升渲染效率。
5.  **功能整合**：将旋转矩形绘制功能成功应用到游戏引擎中，特别是增强了粒子系统的视觉效果。

![](img/886a749eaaa9f80910ebb04a9f92609c_705.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_707.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_709.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_711.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_713.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_715.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_717.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_719.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_721.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_723.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_724.png)

通过手动实现这些功能，我们不仅为游戏添加了重要的图形能力，也深入理解了背后的数学原理和优化技巧。这为我们接下来实现更复杂的图形功能（如位图绘制、亚像素精度渲染）打下了坚实的基础。

![](img/886a749eaaa9f80910ebb04a9f92609c_726.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_728.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_730.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_732.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_734.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_736.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_738.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_740.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_742.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_744.png)

---
**下一步**：在接下来的课程中，我们将探索位图（Bitmap）的支持，以便在游戏中显示更复杂的图像，例如道具图标，并可能研究亚像素精度渲染来使边缘更加平滑。

![](img/886a749eaaa9f80910ebb04a9f92609c_746.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_748.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_749.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_751.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_753.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_755.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_757.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_758.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_760.png)

![](img/886a749eaaa9f80910ebb04a9f92609c_762.png)

你可以访问项目网站下载最新的游戏和源代码，并在YouTube上观看从第一行代码开始的所有开发过程。