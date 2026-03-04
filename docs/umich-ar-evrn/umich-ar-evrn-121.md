# 121：WebXR无标记AR实现

![](img/68dbc4bc4cf08c5695a755fbe87a81b9_0.png)

![](img/68dbc4bc4cf08c5695a755fbe87a81b9_1.png)

![](img/68dbc4bc4cf08c5695a755fbe87a81b9_3.png)

![](img/68dbc4bc4cf08c5695a755fbe87a81b9_5.png)

在本节课中，我们将学习如何使用A-Frame和WebXR技术创建无标记增强现实（AR）体验。我们将从基础场景开始，逐步添加3D模型、动画、光照，并最终实现基于平面检测的物体放置功能。

![](img/68dbc4bc4cf08c5695a755fbe87a81b9_7.png)

## 概述

![](img/68dbc4bc4cf08c5695a755fbe87a81b9_9.png)

![](img/68dbc4bc4cf08c5695a755fbe87a81b9_11.png)

![](img/68dbc4bc4cf08c5695a755fbe87a81b9_13.png)

![](img/68dbc4bc4cf08c5695a755fbe87a81b9_15.png)

我们将创建一个无标记AR场景，允许用户在真实环境中放置和查看3D对象。课程将涵盖场景设置、模型加载、光照调整以及使用最新的WebXR功能进行平面检测和物体放置。

![](img/68dbc4bc4cf08c5695a755fbe87a81b9_17.png)

![](img/68dbc4bc4cf08c5695a755fbe87a81b9_19.png)

![](img/68dbc4bc4cf08c5695a755fbe87a81b9_21.png)

## 基础场景设置

![](img/68dbc4bc4cf08c5695a755fbe87a81b9_23.png)

![](img/68dbc4bc4cf08c5695a755fbe87a81b9_25.png)

![](img/68dbc4bc4cf08c5695a755fbe87a81b9_26.png)

![](img/68dbc4bc4cf08c5695a755fbe87a81b9_28.png)

![](img/68dbc4bc4cf08c5695a755fbe87a81b9_30.png)

首先，我们从标准的A-Frame模板开始，并移除天空盒，以创建一个适合AR的基础场景。

![](img/68dbc4bc4cf08c5695a755fbe87a81b9_32.png)

![](img/68dbc4bc4cf08c5695a755fbe87a81b9_34.png)

```html
<a-scene>
  <a-box position="0 0.5 -1" rotation="0 45 0" color="#4CC3D9"></a-box>
</a-scene>
```

![](img/68dbc4bc4cf08c5695a755fbe87a81b9_36.png)

![](img/68dbc4bc4cf08c5695a755fbe87a81b9_38.png)

![](img/68dbc4bc4cf08c5695a755fbe87a81b9_40.png)

![](img/68dbc4bc4cf08c5695a755fbe87a81b9_42.png)

![](img/68dbc4bc4cf08c5695a755fbe87a81b9_44.png)

## 调整模型尺寸与位置

![](img/68dbc4bc4cf08c5695a755fbe87a81b9_46.png)

![](img/68dbc4bc4cf08c5695a755fbe87a81b9_48.png)

![](img/68dbc4bc4cf08c5695a755fbe87a81b9_50.png)

![](img/68dbc4bc4cf08c5695a755fbe87a81b9_52.png)

![](img/68dbc4bc4cf08c5695a755fbe87a81b9_54.png)

为了使3D对象在AR中看起来比例合适，我们需要调整其尺寸和初始位置。以下是如何将一个模型缩小并放置在相机前方一米处。

![](img/68dbc4bc4cf08c5695a755fbe87a81b9_56.png)

```html
<a-entity gltf-model="url(./model.glb)" scale="0.01 0.01 0.01" position="0 0 -1"></a-entity>
```

![](img/68dbc4bc4cf08c5695a755fbe87a81b9_58.png)

![](img/68dbc4bc4cf08c5695a755fbe87a81b9_60.png)

## 添加动画效果

![](img/68dbc4bc4cf08c5695a755fbe87a81b9_62.png)

![](img/68dbc4bc4cf08c5695a755fbe87a81b9_64.png)

![](img/68dbc4bc4cf08c5695a755fbe87a81b9_66.png)

![](img/68dbc4bc4cf08c5695a755fbe87a81b9_68.png)

![](img/68dbc4bc4cf08c5695a755fbe87a81b9_70.png)

为了让场景更生动，我们可以为模型添加动画。以下代码为长颈鹿模型添加了一个简单的摇摆动画。

![](img/68dbc4bc4cf08c5695a755fbe87a81b9_72.png)

![](img/68dbc4bc4cf08c5695a755fbe87a81b9_74.png)

```html
<a-animation attribute="rotation" dur="2000" fill="forwards" to="0 360 0" repeat="indefinite"></a-animation>
```

![](img/68dbc4bc4cf08c5695a755fbe87a81b9_76.png)

![](img/68dbc4bc4cf08c5695a755fbe87a81b9_78.png)

![](img/68dbc4bc4cf08c5695a755fbe87a81b9_80.png)

## 配置光照与阴影

在AR中，虚拟对象的光照需要与真实环境融合。我们将设置环境光和聚光灯来模拟真实光源。

![](img/68dbc4bc4cf08c5695a755fbe87a81b9_82.png)

![](img/68dbc4bc4cf08c5695a755fbe87a81b9_83.png)

![](img/68dbc4bc4cf08c5695a755fbe87a81b9_85.png)

以下是设置环境光和聚光灯的代码示例。

![](img/68dbc4bc4cf08c5695a755fbe87a81b9_87.png)

```html
<!-- 环境光 -->
<a-entity light="type: ambient; color: #CCC; intensity: 0.7"></a-entity>
<!-- 聚光灯 -->
<a-entity light="type: spot; angle: 60; penumbra: 1; intensity: 1.5; color: #FFF; target: #giraffe" position="1 1.8 -0.5"></a-entity>
```

![](img/68dbc4bc4cf08c5695a755fbe87a81b9_89.png)

![](img/68dbc4bc4cf08c5695a755fbe87a81b9_91.png)

![](img/68dbc4bc4cf08c5695a755fbe87a81b9_93.png)

## 实现平面检测与物体放置

我们将使用WebXR的平面检测（Hit Testing）功能，允许用户通过点击屏幕将物体放置在检测到的平面上。

![](img/68dbc4bc4cf08c5695a755fbe87a81b9_95.png)

![](img/68dbc4bc4cf08c5695a755fbe87a81b9_97.png)

以下是实现平面检测和物体放置的核心代码结构。

```javascript
// 初始化WebXR会话并启用平面检测
navigator.xr.requestSession('immersive-ar', { requiredFeatures: ['hit-test'] }).then(onSessionStarted);
```

![](img/68dbc4bc4cf08c5695a755fbe87a81b9_99.png)

![](img/68dbc4bc4cf08c5695a755fbe87a81b9_101.png)

## 在HoloLens上测试

我们将在HoloLens设备上测试我们的WebXR AR场景，确保其在头戴式设备上也能良好运行。

## 实用技巧与最佳实践

在开发无标记AR体验时，遵循一些最佳实践可以显著提升用户体验。

以下是几个关键的开发建议。

1.  **提供放置预览**：在用户确认放置前，显示一个半透明的对象预览，让用户了解最终效果。
2.  **融合环境光照**：根据环境调整虚拟对象的光照和阴影，使其看起来更真实。
3.  **为遮挡渲染和光照估计做准备**：虽然这些功能在WebXR中尚不完善，但在代码中预留接口，以便未来轻松集成。
4.  **使用360° VR或基于标记的AR进行原型设计**：在开发早期，可以利用这些技术快速测试场景布局和光照效果。
5.  **允许用户调整体验**：考虑提供选项，让用户能调整虚拟对象的尺寸或布局，以适应不同的环境。
6.  **适配检测到的平面**：根据检测到的平面（如桌面、地面）的尺寸和方向，动态调整虚拟内容的布局。

## 总结

![](img/68dbc4bc4cf08c5695a755fbe87a81b9_103.png)

![](img/68dbc4bc4cf08c5695a755fbe87a81b9_105.png)

本节课我们一起学习了如何使用A-Frame和WebXR创建无标记AR体验。我们从搭建基础场景开始，逐步添加了3D模型、动画和自定义光照，并最终实现了基于平面检测的交互式物体放置功能。虽然WebXR的某些高级功能仍处于发展阶段，但我们已经能够利用现有技术构建引人入胜的AR应用。希望你能将这些知识应用到自己的项目中，创造出更丰富的沉浸式体验。