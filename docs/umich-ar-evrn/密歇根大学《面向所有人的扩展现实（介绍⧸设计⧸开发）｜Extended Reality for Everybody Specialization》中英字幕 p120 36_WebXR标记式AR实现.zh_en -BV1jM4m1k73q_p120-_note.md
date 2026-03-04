# WebXR标记式AR实现：第36章：基于标记的WebXR AR体验教程 🎯

![](img/190e3597363144eddd250d4ccc81286b_0.png)

![](img/190e3597363144eddd250d4ccc81286b_1.png)

在本节课中，我们将学习如何使用A-Frame和AR.js库在WebXR中创建基于标记（Marker-Based）的增强现实体验。我们将从基础的单标记跟踪开始，逐步探索多标记跟踪、交互实现，并最终构建一个包含3D模型和动画的完整AR场景。

![](img/190e3597363144eddd250d4ccc81286b_3.png)

## 概述

基于标记的AR体验通常围绕一个3D模型展开，可能包含简单的动画、光影效果，偶尔会有菜单或提示。交互方式主要是基于光标的，因为我们通常没有实体控制器。语音交互较为少见，而隐式交互则多与标记本身的位置相关。

---

## 单标记跟踪入门 🚀

![](img/190e3597363144eddd250d4ccc81286b_5.png)

![](img/190e3597363144eddd250d4ccc81286b_6.png)

首先，我们从一个基础的AR.js模板开始。这个模板能检测特定的标记（例如“hero”标记），并在其上方显示一个虚拟物体。

![](img/190e3597363144eddd250d4ccc81286b_8.png)

以下是核心的HTML结构代码：

![](img/190e3597363144eddd250d4ccc81286b_10.png)

```html
<!DOCTYPE html>
<html>
<head>
  <script src="https://aframe.io/releases/1.2.0/aframe.min.js"></script>
  <script src="https://raw.githack.com/AR-js-org/AR.js/master/aframe/build/aframe-ar.js"></script>
</head>
<body style='margin : 0px; overflow: hidden;'>
  <a-scene embedded arjs='sourceType: webcam;'>
    <a-marker preset='hiro'>
      <a-box position='0 0.5 0' material='color: red;'></a-box>
    </a-marker>
    <a-entity camera></a-entity>
  </a-scene>
</body>
</html>
```

![](img/190e3597363144eddd250d4ccc81286b_11.png)

![](img/190e3597363144eddd250d4ccc81286b_13.png)

![](img/190e3597363144eddd250d4ccc81286b_15.png)

**关键点解析：**
*   `a-marker` 组件定义了要跟踪的标记类型（如 `preset='hiro'`）。
*   标记内部的3D物体（如 `a-box`）的坐标系原点 `(0,0,0)` 位于标记的中心。
*   为了让物体“站立”在标记上，我们通常需要将其沿Y轴向上移动，例如 `position='0 0.5 0'`（假设盒子默认高度为1）。

![](img/190e3597363144eddd250d4ccc81286b_17.png)

![](img/190e3597363144eddd250d4ccc81286b_19.png)

![](img/190e3597363144eddd250d4ccc81286b_20.png)

![](img/190e3597363144eddd250d4ccc81286b_21.png)

为了获得更好的跟踪视觉反馈，我们可以在标记位置添加一个半透明的平面。

![](img/190e3597363144eddd250d4ccc81286b_23.png)

![](img/190e3597363144eddd250d4ccc81286b_24.png)

![](img/190e3597363144eddd250d4ccc81286b_26.png)

```html
<a-marker preset='hiro'>
  <a-plane position='0 0 0' rotation='-90 0 0' material='opacity: 0.5; side: double;'></a-plane>
  <!-- 你的3D物体放在这里 -->
</a-marker>
```

![](img/190e3597363144eddd250d4ccc81286b_28.png)

![](img/190e3597363144eddd250d4ccc81286b_30.png)

---

![](img/190e3597363144eddd250d4ccc81286b_31.png)

## 构建“Hello World” AR场景 🌍

![](img/190e3597363144eddd250d4ccc81286b_33.png)

![](img/190e3597363144eddd250d4ccc81286b_35.png)

![](img/190e3597363144eddd250d4ccc81286b_37.png)

上一节我们实现了基础的单标记跟踪。本节中，我们来看看如何将一个更复杂的A-Frame“Hello World”场景集成到AR中。

![](img/190e3597363144eddd250d4ccc81286b_38.png)

![](img/190e3597363144eddd250d4ccc81286b_40.png)

直接复制典型的A-Frame场景代码会导致模型尺寸过大。这是因为AR场景的尺度由标记的物理大小决定。解决方案是将整个场景包裹在一个父实体中，并对其进行缩放和位置调整。

![](img/190e3597363144eddd250d4ccc81286b_42.png)

以下是调整后的代码示例：

![](img/190e3597363144eddd250d4ccc81286b_44.png)

![](img/190e3597363144eddd250d4ccc81286b_46.png)

```html
<a-marker preset='hiro'>
  <a-entity position='0 0 -2' scale='0.25 0.25 0.25'>
    <!-- 原始的A-Frame Hello World场景内容 -->
    <a-box position="-1 0.5 -3" rotation="0 45 0" color="#4CC3D9"></a-box>
    <a-sphere position="0 1.25 -5" radius="1.25" color="#EF2D5E"></a-sphere>
    <a-cylinder position="1 0.75 -3" radius="0.5" height="1.5" color="#FFC65D"></a-cylinder>
    <a-plane position="0 0 -4" rotation="-90 0 0" width="4" height="4" color="#7BC8A4"></a-plane>
  </a-entity>
</a-marker>
```

![](img/190e3597363144eddd250d4ccc81286b_48.png)

![](img/190e3597363144eddd250d4ccc81286b_50.png)

**调整要点：**
1.  **缩放 (`scale`)**: 将整个场景缩小（例如0.25倍），使其与标记尺寸匹配。
2.  **位置 (`position`)**: 将场景沿Z轴负方向移动（例如 `0 0 -2`），使其出现在标记后方一定距离，便于观看。

---

![](img/190e3597363144eddd250d4ccc81286b_52.png)

![](img/190e3597363144eddd250d4ccc81286b_54.png)

## 实现AR交互 👆

在VR中，我们学习了多种交互方式。在基于标记的AR中，我们将重点实现基础的光标交互。

![](img/190e3597363144eddd250d4ccc81286b_56.png)

![](img/190e3597363144eddd250d4ccc81286b_58.png)

![](img/190e3597363144eddd250d4ccc81286b_60.png)

![](img/190e3597363144eddd250d4ccc81286b_62.png)

首先，我们创建一个带有透明度的红色盒子作为交互对象。

```html
<a-marker preset='hiro'>
  <a-box id="myBox" position="0 0.5 0" color="red" opacity="0.8"></a-box>
</a-marker>
```

![](img/190e3597363144eddd250d4ccc81286b_64.png)

![](img/190e3597363144eddd250d4ccc81286b_65.png)

![](img/190e3597363144eddd250d4ccc81286b_67.png)

![](img/190e3597363144eddd250d4ccc81286b_68.png)

接着，我们需要在场景中添加一个光标。由于AR.js中存在一个已知问题，直接将 `rayOrigin` 设置为 `mouse` 可能无法正常工作。更可靠的方法是在相机上添加光标组件。

![](img/190e3597363144eddd250d4ccc81286b_70.png)

```html
<a-entity camera look-controls>
  <a-cursor rayOrigin="mouse"></a-cursor>
</a-entity>
```

![](img/190e3597363144eddd250d4ccc81286b_72.png)

![](img/190e3597363144eddd250d4ccc81286b_73.png)

![](img/190e3597363144eddd250d4ccc81286b_75.png)

然后，我们可以使用JavaScript来为盒子添加交互事件（如鼠标移入/移出改变颜色）。

```html
<script>
  // 获取盒子元素
  const boxEl = document.querySelector('#myBox');
  // 定义交互函数
  function changeColorToBlue() {
    boxEl.setAttribute('color', 'blue');
  }
  function changeColorToRed() {
    boxEl.setAttribute('color', 'red');
  }
  // 添加事件监听器
  boxEl.addEventListener('mouseenter', changeColorToBlue);
  boxEl.addEventListener('mouseleave', changeColorToRed);
</script>
```

**更优实践：** 使用A-Frame的组件化思维，通过 `event-set-component` 可以更声明式地实现交互，无需编写JavaScript。

```html
<a-box id="myBox" position="0 0.5 0" color="red" opacity="0.8"
       event-set__enter="_event: mouseenter; color: blue"
       event-set__leave="_event: mouseleave; color: red">
</a-box>
```

![](img/190e3597363144eddd250d4ccc81286b_77.png)

![](img/190e3597363144eddd250d4ccc81286b_79.png)

这种交互在手机上同样有效，`mouseenter/mouseleave` 事件会对应转换为触摸事件。

---

## 加载3D模型与动画 🦒

现在，让我们引入更丰富的3D内容。我们将使用 `google-poly` 组件加载一个长颈鹿模型，并为其添加动画。

![](img/190e3597363144eddd250d4ccc81286b_81.png)

首先，引入组件并定义标记和模型。

```html
<script src="https://unpkg.com/aframe-extras@6.1.1/dist/aframe-extras.min.js"></script>
<a-marker preset='hiro'>
  <a-entity gltf-model="https://cdn.glitch.com/.../giraffe.gltf"
            scale="0.05 0.05 0.05"
            rotation="0 180 0"
            animation="property: rotation; to: 0 540 0; dur: 2500; easing: linear; loop: true">
  </a-entity>
</a-marker>
```

![](img/190e3597363144eddd250d4ccc81286b_83.png)

**代码说明：**
*   `gltf-model`: 用于加载GLTF格式的3D模型。
*   `scale`: 根据模型原始大小和标记尺寸调整缩放比例。
*   `animation`: 为模型添加旋转动画，使其持续缓慢旋转。

![](img/190e3597363144eddd250d4ccc81286b_85.png)

---

## 多标记跟踪 🤝

AR.js支持同时跟踪多个不同的标记。我们可以为每个标记分配不同的虚拟内容，创造更复杂的场景。

以下是实现多标记跟踪的示例，我们在“hiro”标记和“kanji”标记上分别放置两个不同大小的长颈鹿模型。

![](img/190e3597363144eddd250d4ccc81286b_87.png)

```html
<a-marker preset='hiro'>
  <a-entity gltf-model="url(giraffe.gltf)"
            scale="0.05 0.05 0.05"
            animation="property: rotation; to: 0 360 0; dur: 3000; loop: true">
  </a-entity>
</a-marker>

<a-marker preset='kanji'>
  <a-entity gltf-model="url(giraffe.gltf)"
            scale="0.02 0.02 0.02"
            animation="property: rotation; to: 0 -360 0; dur: 2000; delay: 1000; loop: true">
  </a-entity>
</a-marker>
```

![](img/190e3597363144eddd250d4ccc81286b_89.png)

通过为两个模型设置不同的 `scale` 和 `animation` 参数（如方向、持续时间、延迟），可以营造出“大长颈鹿”和“小长颈鹿”的生动场景。你可以物理移动不同的标记纸来编排它们之间的空间故事。

![](img/190e3597363144eddd250d4ccc81286b_91.png)

---

![](img/190e3597363144eddd250d4ccc81286b_93.png)

## 高级技巧与最佳实践 💡

![](img/190e3597363144eddd250d4ccc81286b_95.png)

### 1. 使用立方体标记 (AR Cube)
为了提升跟踪鲁棒性，可以使用一种特殊的“立方体标记”。这种标记有六个面，无论如何旋转立方体，至少有一个面能被摄像头看到，从而减少跟踪丢失的情况。

![](img/190e3597363144eddd250d4ccc81286b_97.png)

### 2. 开发调试技巧
*   **禁用自动刷新**：在CodePen或类似环境中开发时，请关闭“自动更新预览”功能，避免每次代码保存都重启摄像头。
*   **调整模型透明度**：将模型的 `opacity` 设置为低于1的值（如0.8），可以让你透过模型看到底部的标记，便于调试对齐和跟踪状态。
*   **使用笔记本摄像头开发**：无需特殊AR设备，普通笔记本摄像头即可用于开发。
*   **用屏幕显示标记**：在测试时，可以直接在手机或电脑屏幕上显示标记图片，无需打印。
*   **切换摄像头**：在浏览器权限设置中，可以切换使用不同的摄像头设备。

![](img/190e3597363144eddd250d4ccc81286b_99.png)

### 3. 注意事项
*   **标记尺寸**：标记尺寸直接影响虚拟物体的感知大小。大标记更容易被检测，小标记则更精致。
*   **勿遮挡标记边框**：确保标记的黑色边框完整可见，这是检测的关键。
*   **平面跟踪限制**：标记需要保持相对平整，弯曲或折叠会导致跟踪失败。

---

## 总结

![](img/190e3597363144eddd250d4ccc81286b_101.png)

![](img/190e3597363144eddd250d4ccc81286b_102.png)

![](img/190e3597363144eddd250d4ccc81286b_103.png)

![](img/190e3597363144eddd250d4ccc81286b_104.png)

本节课中，我们一起探索了基于WebXR和AR.js创建标记式增强现实体验的全过程。我们从最简单的单标记和红色立方体开始，逐步学习了如何集成复杂的3D场景、实现光标交互、加载并动画化3D模型，以及如何利用多标记跟踪来构建更具叙事性的AR场景。最后，我们还分享了一些实用的开发调试技巧和最佳实践。希望你能利用这些知识，创造出属于自己的有趣AR应用！