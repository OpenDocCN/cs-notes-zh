# WebXR基础VR开发：第22讲：基础虚拟现实体验 🦒

![](img/04166cf832cf3cd5409b884aa894351f_0.png)

![](img/04166cf832cf3cd5409b884aa894351f_1.png)

![](img/04166cf832cf3cd5409b884aa894351f_3.png)

![](img/04166cf832cf3cd5409b884aa894351f_4.png)

在本节课中，我们将学习如何使用A-Frame框架创建一个基础的虚拟现实场景。我们将从一个简单的3D模型开始，逐步添加动画、灯光、阴影和基础的交互功能，最终构建一个兼容Cardboard和PC VR头显的VR体验。

![](img/04166cf832cf3cd5409b884aa894351f_6.png)

![](img/04166cf832cf3cd5409b884aa894351f_7.png)

## 概述

![](img/04166cf832cf3cd5409b884aa894351f_9.png)

![](img/04166cf832cf3cd5409b884aa894351f_10.png)

![](img/04166cf832cf3cd5409b884aa894351f_12.png)

我们将创建一个包含旋转长颈鹿模型的VR场景。场景将设置夜晚的灯光效果，并添加一个聚光灯来照亮模型。我们还会实现基础的交互功能，例如通过凝视（Cardboard）或控制器射线来与场景互动。课程将涵盖如何将普通3D场景转换为VR场景，并确保其在不同设备上的兼容性。

![](img/04166cf832cf3cd5409b884aa894351f_14.png)

---

![](img/04166cf832cf3cd5409b884aa894351f_16.png)

## 从3D场景到VR场景 🎮

![](img/04166cf832cf3cd5409b884aa894351f_18.png)

![](img/04166cf832cf3cd5409b884aa894351f_19.png)

上一节我们介绍了课程目标。本节中，我们来看看如何将一个基础的3D场景转换为一个功能完整的VR场景。

![](img/04166cf832cf3cd5409b884aa894351f_21.png)

![](img/04166cf832cf3cd5409b884aa894351f_23.png)

![](img/04166cf832cf3cd5409b884aa894351f_25.png)

我们的起点是一个简单的A-Frame HTML文件，它包含一个从Google Poly导入的长颈鹿模型和一个平面。

![](img/04166cf832cf3cd5409b884aa894351f_27.png)

```html
<!DOCTYPE html>
<html>
  <head>
    <script src="https://aframe.io/releases/1.2.0/aframe.min.js"></script>
    <script src="https://unpkg.com/aframe-google-poly-component@1.1.0/dist/aframe-google-poly-component.min.js"></script>
  </head>
  <body>
    <a-scene>
      <a-entity google-poly="assetId:5vbJ5vildOq" position="0 0 -5" rotation="-90 0 0" scale="0.5 0.5 0.5" id="giraffe"></a-entity>
      <a-plane position="0 -1 -6" rotation="-90 0 0" width="10" height="10" color="#7BC8A4" shadow="receive: true"></a-plane>
      <a-sky color="green"></a-sky>
    </a-scene>
  </body>
</html>
```

![](img/04166cf832cf3cd5409b884aa894351f_29.png)

![](img/04166cf832cf3cd5409b884aa894351f_30.png)

![](img/04166cf832cf3cd5409b884aa894351f_31.png)

![](img/04166cf832cf3cd5409b884aa894351f_32.png)

![](img/04166cf832cf3cd5409b884aa894351f_33.png)

![](img/04166cf832cf3cd5409b884aa894351f_34.png)

![](img/04166cf832cf3cd5409b884aa894351f_36.png)

目前，这只是一个3D网页。为了使其支持VR，我们需要添加VR模式所需的组件，例如控制器和相机装置。

![](img/04166cf832cf3cd5409b884aa894351f_38.png)

![](img/04166cf832cf3cd5409b884aa894351f_40.png)

![](img/04166cf832cf3cd5409b884aa894351f_42.png)

以下是添加基础VR控制器支持的关键代码块。我们将一个包含相机和手柄控制器的“相机装置”实体添加到场景中。

![](img/04166cf832cf3cd5409b884aa894351f_44.png)

![](img/04166cf832cf3cd5409b884aa894351f_45.png)

![](img/04166cf832cf3cd5409b884aa894351f_46.png)

![](img/04166cf832cf3cd5409b884aa894351f_48.png)

![](img/04166cf832cf3cd5409b884aa894351f_49.png)

![](img/04166cf832cf3cd5409b884aa894351f_50.png)

```html
<a-entity id="cameraRig" position="0 1.6 0">
  <!-- 相机 -->
  <a-entity camera look-controls wasd-controls position="0 0 0">
  </a-entity>
  <!-- 左手控制器 -->
  <a-entity hand-controls="hand: left" laser-controls="hand: left"></a-entity>
  <!-- 右手控制器 -->
  <a-entity hand-controls="hand: right" laser-controls="hand: right"></a-entity>
</a-entity>
```

![](img/04166cf832cf3cd5409b884aa894351f_52.png)

![](img/04166cf832cf3cd5409b884aa894351f_54.png)

![](img/04166cf832cf3cd5409b884aa894351f_55.png)

![](img/04166cf832cf3cd5409b884aa894351f_57.png)

添加这段代码后，在支持WebXR的浏览器中，场景将提供进入VR模式的按钮。使用PC VR头显时，用户可以看到虚拟的手柄和射线。

![](img/04166cf832cf3cd5409b884aa894351f_59.png)

![](img/04166cf832cf3cd5409b884aa894351f_61.png)

---

![](img/04166cf832cf3cd5409b884aa894351f_63.png)

![](img/04166cf832cf3cd5409b884aa894351f_64.png)

![](img/04166cf832cf3cd5409b884aa894351f_66.png)

![](img/04166cf832cf3cd5409b884aa894351f_68.png)

## 为模型添加动画 🔄

![](img/04166cf832cf3cd5409b884aa894351f_70.png)

![](img/04166cf832cf3cd5409b884aa894351f_72.png)

![](img/04166cf832cf3cd5409b884aa894351f_74.png)

![](img/04166cf832cf3cd5409b884aa894351f_75.png)

![](img/04166cf832cf3cd5409b884aa894351f_77.png)

现在我们的场景已经支持VR，接下来让场景中的元素动起来。我们将为长颈鹿模型添加一个简单的旋转动画。

![](img/04166cf832cf3cd5409b884aa894351f_79.png)

A-Frame提供了内置的动画组件。我们可以通过`animation`属性来定义动画。以下是让长颈鹿在Y轴上轻微摇摆的动画代码：

```html
<a-entity google-poly="assetId:5vbJ5vildOq"
          position="0 0 -5"
          rotation="-90 0 0"
          scale="0.5 0.5 0.5"
          id="giraffe"
          animation="property: rotation.y;
                     from: -88;
                     to: -95;
                     dur: 3500;
                     easing: easeOutElastic;
                     loop: true;
                     dir: alternate">
</a-entity>
```

![](img/04166cf832cf3cd5409b884aa894351f_81.png)

![](img/04166cf832cf3cd5409b884aa894351f_82.png)

![](img/04166cf832cf3cd5409b884aa894351f_84.png)

![](img/04166cf832cf3cd5409b884aa894351f_85.png)

![](img/04166cf832cf3cd5409b884aa894351f_86.png)

**代码解释**：
*   `property: rotation.y`： 指定动画作用于Y轴旋转。
*   `from` 和 `to`： 定义动画的起始和结束值。
*   `dur`： 动画持续时间（毫秒）。
*   `easing`： 缓动函数，这里使用`easeOutElastic`产生弹性效果。
*   `loop: true`： 动画循环播放。
*   `dir: alternate`： 动画方向交替，形成来回摇摆的效果。

![](img/04166cf832cf3cd5409b884aa894351f_88.png)

![](img/04166cf832cf3cd5409b884aa894351f_90.png)

![](img/04166cf832cf3cd5409b884aa894351f_92.png)

![](img/04166cf832cf3cd5409b884aa894351f_94.png)

![](img/04166cf832cf3cd5409b884aa894351f_96.png)

![](img/04166cf832cf3cd5409b884aa894351f_98.png)

![](img/04166cf832cf3cd5409b884aa894351f_100.png)

---

![](img/04166cf832cf3cd5409b884aa894351f_102.png)

![](img/04166cf832cf3cd5409b884aa894351f_104.png)

![](img/04166cf832cf3cd5409b884aa894351f_106.png)

![](img/04166cf832cf3cd5409b884aa894351f_108.png)

## 设置灯光与阴影 💡

![](img/04166cf832cf3cd5409b884aa894351f_110.png)

![](img/04166cf832cf3cd5409b884aa894351f_112.png)

![](img/04166cf832cf3cd5409b884aa894351f_114.png)

灯光对于营造场景氛围至关重要。我们将把默认的绿色天空改为暗色，并添加一个聚光灯来突出长颈鹿模型，同时启用阴影。

![](img/04166cf832cf3cd5409b884aa894351f_116.png)

首先，我们移除绿色天空，并添加一个环境光和一个聚光灯。

![](img/04166cf832cf3cd5409b884aa894351f_118.png)

![](img/04166cf832cf3cd5409b884aa894351f_120.png)

![](img/04166cf832cf3cd5409b884aa894351f_121.png)

```html
<!-- 环境光，为整个场景提供基础照明 -->
<a-light type="ambient" color="#333"></a-light>

![](img/04166cf832cf3cd5409b884aa894351f_123.png)

![](img/04166cf832cf3cd5409b884aa894351f_124.png)

<!-- 聚光灯，聚焦照亮长颈鹿 -->
<a-entity light="type: spot;
                 angle: 20;
                 intensity: 0.75;
                 color: #FFF;
                 castShadow: true;
                 target: #giraffe"
          position="3 3 -3">
</a-entity>
```

![](img/04166cf832cf3cd5409b884aa894351f_126.png)

![](img/04166cf832cf3cd5409b884aa894351f_127.png)

![](img/04166cf832cf3cd5409b884aa894351f_129.png)

![](img/04166cf832cf3cd5409b884aa894351f_131.png)

**代码解释**：
*   **环境光** (`type="ambient"`)：均匀地照亮所有物体，没有方向，用于防止阴影区域完全黑暗。
*   **聚光灯** (`type="spot"`)：从一个点朝特定方向发射锥形光。
    *   `angle`： 光束的角度。
    *   `intensity`： 光的强度。
    *   `castShadow: true`： 允许此光源产生阴影。
    *   `target: #giraffe`： 将光指向ID为`giraffe`的实体。

![](img/04166cf832cf3cd5409b884aa894351f_133.png)

![](img/04166cf832cf3cd5409b884aa894351f_135.png)

为了让阴影正确显示，我们还需要确保接收阴影的平面（`a-plane`）和投射阴影的模型（长颈鹿）设置了正确的属性。

```html
<!-- 平面接收阴影 -->
<a-plane ...
         shadow="receive: true">
</a-plane>

![](img/04166cf832cf3cd5409b884aa894351f_137.png)

![](img/04166cf832cf3cd5409b884aa894351f_139.png)

<!-- 模型投射阴影（需模型本身支持） -->
<a-entity google-poly="..."
          shadow="cast: true">
</a-entity>
```

![](img/04166cf832cf3cd5409b884aa894351f_141.png)

![](img/04166cf832cf3cd5409b884aa894351f_143.png)

![](img/04166cf832cf3cd5409b884aa894351f_145.png)

![](img/04166cf832cf3cd5409b884aa894351f_147.png)

![](img/04166cf832cf3cd5409b884aa894351f_148.png)

---

![](img/04166cf832cf3cd5409b884aa894351f_150.png)

![](img/04166cf832cf3cd5409b884aa894351f_152.png)

![](img/04166cf832cf3cd5409b884aa894351f_153.png)

![](img/04166cf832cf3cd5409b884aa894351f_155.png)

![](img/04166cf832cf3cd5409b884aa894351f_157.png)

## 实现Cardboard兼容与基础交互 👁️

![](img/04166cf832cf3cd5409b884aa894351f_159.png)

![](img/04166cf832cf3cd5409b884aa894351f_161.png)

![](img/04166cf832cf3cd5409b884aa894351f_163.png)

![](img/04166cf832cf3cd5409b884aa894351f_164.png)

为了让使用Cardboard等3DoF头显的用户也能进行交互，我们需要添加一个凝视光标。同时，我们为基础交互添加一个事件系统。

![](img/04166cf832cf3cd5409b884aa894351f_166.png)

![](img/04166cf832cf3cd5409b884aa894351f_168.png)

![](img/04166cf832cf3cd5409b884aa894351f_170.png)

以下是添加凝视光标和VR大按钮的代码：

![](img/04166cf832cf3cd5409b884aa894351f_172.png)

```html
<a-scene>
  <!-- 在相机内添加凝视光标 -->
  <a-entity camera look-controls>
    <a-cursor fuse="true" fuse-timeout="2000"
              animation__click="property: scale; startEvents: click; from: 0.1 0.1 0.1; to: 1 1 1; dur: 150"
              animation__fusing="property: scale; startEvents: fusing; from: 1 1 1; to: 0.1 0.1 0.1; dur: 1500"
              animation__mouseleave="property: scale; startEvents: mouseleave; to: 1 1 1; dur: 500">
    </a-cursor>
  </a-entity>

  <!-- 大的VR入口按钮（CSS样式） -->
  <style>
    .a-enter-vr-button {
      width: 200px !important;
      height: 100px !important;
      font-size: 24px !important;
    }
  </style>
</a-scene>
```

![](img/04166cf832cf3cd5409b884aa894351f_174.png)

![](img/04166cf832cf3cd5409b884aa894351f_176.png)

![](img/04166cf832cf3cd5409b884aa894351f_178.png)

![](img/04166cf832cf3cd5409b884aa894351f_180.png)

现在，我们使用`event-set`组件来实现一个简单的交互：当用户凝视并触发光标（或点击）长颈鹿时，切换聚光灯的开关。

![](img/04166cf832cf3cd5409b884aa894351f_181.png)

![](img/04166cf832cf3cd5409b884aa894351f_183.png)

![](img/04166cf832cf3cd5409b884aa894351f_185.png)

![](img/04166cf832cf3cd5409b884aa894351f_187.png)

![](img/04166cf832cf3cd5409b884aa894351f_189.png)

首先引入`event-set`组件库：
```html
<script src="https://unpkg.com/aframe-event-set-component@5.0.0/dist/aframe-event-set-component.min.js"></script>
```

![](img/04166cf832cf3cd5409b884aa894351f_191.png)

![](img/04166cf832cf3cd5409b884aa894351f_193.png)

![](img/04166cf832cf3cd5409b884aa894351f_195.png)

![](img/04166cf832cf3cd5409b884aa894351f_197.png)

然后为聚光灯实体添加交互事件：
```html
<a-entity id="spotlight"
          light="type: spot; ..."
          position="3 3 -3"
          event-set__click="_target: #spotlight; _event: click; light.intensity: 0"
          event-set__click-again="_target: #spotlight; _event: click; light.intensity: 0.75; delay: 300">
</a-entity>
```

![](img/04166cf832cf3cd5409b884aa894351f_199.png)

![](img/04166cf832cf3cd5409b884aa894351f_200.png)

![](img/04166cf832cf3cd5409b884aa894351f_201.png)

**代码解释**：
*   第一个`event-set__click`： 当`#spotlight`实体被点击时，将其光强设置为0（关灯）。
*   第二个`event-set__click-again`： 再次被点击时，延迟300毫秒后将光强恢复为0.75（开灯）。通过不同的事件名区分两次点击。

![](img/04166cf832cf3cd5409b884aa894351f_203.png)

![](img/04166cf832cf3cd5409b884aa894351f_204.png)

---

![](img/04166cf832cf3cd5409b884aa894351f_206.png)

![](img/04166cf832cf3cd5409b884aa894351f_208.png)

![](img/04166cf832cf3cd5409b884aa894351f_210.png)

![](img/04166cf832cf3cd5409b884aa894351f_212.png)

![](img/04166cf832cf3cd5409b884aa894351f_213.png)

## 总结

![](img/04166cf832cf3cd5409b884aa894351f_215.png)

![](img/04166cf832cf3cd5409b884aa894351f_217.png)

![](img/04166cf832cf3cd5409b884aa894351f_219.png)

![](img/04166cf832cf3cd5409b884aa894351f_221.png)

![](img/04166cf832cf3cd5409b884aa894351f_223.png)

本节课中我们一起学习了构建一个基础WebXR VR体验的完整流程。

![](img/04166cf832cf3cd5409b884aa894351f_225.png)

![](img/04166cf832cf3cd5409b884aa894351f_227.png)

1.  **搭建VR场景**： 我们从一个基础的3D A-Frame场景开始，通过添加相机装置和控制器支持，将其转换为一个可进入的VR环境。
2.  **添加动态效果**： 我们使用`animation`组件为长颈鹿模型添加了旋转动画，使场景更加生动。
3.  **营造氛围**： 通过设置环境光和聚光灯，我们改变了场景的整体色调，并利用阴影增强了三维空间的真实感。
4.  **实现跨设备交互**： 我们添加了凝视光标以适应Cardboard等设备，并利用`event-set`组件实现了点击模型控制灯光开关的基础交互。

![](img/04166cf832cf3cd5409b884aa894351f_229.png)

![](img/04166cf832cf3cd5409b884aa894351f_230.png)

现在，你拥有了一个包含动画、光影和基础交互的VR场景，它既能在PC VR头显中通过控制器操作，也能在Cardboard中通过凝视进行交互。在接下来的课程中，我们将探索更沉浸式的功能，如传送机制和更复杂的控制器交互。