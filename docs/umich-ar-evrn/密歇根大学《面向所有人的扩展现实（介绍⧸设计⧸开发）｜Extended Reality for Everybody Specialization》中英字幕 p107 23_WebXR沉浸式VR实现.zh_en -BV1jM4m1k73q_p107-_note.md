# WebXR沉浸式VR实现：23：构建沉浸式VR体验 🦒

![](img/285b3d0d8cd79b90331f1aa8449fcace_0.png)

![](img/285b3d0d8cd79b90331f1aa8449fcace_1.png)

![](img/285b3d0d8cd79b90331f1aa8449fcace_3.png)

![](img/285b3d0d8cd79b90331f1aa8449fcace_5.png)

![](img/285b3d0d8cd79b90331f1aa8449fcace_7.png)

在本节课中，我们将学习如何将一个基础的WebXR场景扩展为一个功能丰富的沉浸式虚拟现实体验。我们将从之前创建的Cardboard兼容场景出发，逐步添加环境、物理效果、声音、粒子系统、传送和交互功能，最终构建一个支持高端VR头显（如Oculus Rift S）的完整应用。

![](img/285b3d0d8cd79b90331f1aa8449fcace_9.png)

![](img/285b3d0d8cd79b90331f1aa8449fcace_10.png)

---

## 环境与光照设置 🌲

![](img/285b3d0d8cd79b90331f1aa8449fcace_12.png)

![](img/285b3d0d8cd79b90331f1aa8449fcace_13.png)

![](img/285b3d0d8cd79b90331f1aa8449fcace_15.png)

![](img/285b3d0d8cd79b90331f1aa8449fcace_16.png)

上一节我们完成了基础的交互场景。本节中，我们来看看如何为场景添加一个逼真的环境。

![](img/285b3d0d8cd79b90331f1aa8449fcace_18.png)

![](img/285b3d0d8cd79b90331f1aa8449fcace_20.png)

首先，我们需要引入A-Frame的环境组件来替换简单的平面地面。这个组件提供了预设的森林、山脉等环境，并自带光照和雾效。

![](img/285b3d0d8cd79b90331f1aa8449fcace_22.png)

![](img/285b3d0d8cd79b90331f1aa8449fcace_24.png)

![](img/285b3d0d8cd79b90331f1aa8449fcace_26.png)

![](img/285b3d0d8cd79b90331f1aa8449fcace_28.png)

以下是添加环境组件的代码：

![](img/285b3d0d8cd79b90331f1aa8449fcace_30.png)

![](img/285b3d0d8cd79b90331f1aa8449fcace_32.png)

```html
<!-- 在<a-scene>标签内添加 -->
<a-entity environment="preset: forest; shadow: true; skyType: atmosphere;"></a-entity>
```

![](img/285b3d0d8cd79b90331f1aa8449fcace_34.png)

添加后，原有的平面地面可能会与环境产生视觉冲突（如闪烁）。解决方法有两种：
1.  将原有平面的`position`的Y轴值略微提高（例如 `position="0 0.01 0"`），使其渲染在环境地面之上。
2.  直接移除原有平面，因为环境组件已经提供了地面。

我们选择移除原有平面，并使用环境组件自带的点光源。可以通过`lightPosition`属性调整光源方向，从而控制阴影的位置。

![](img/285b3d0d8cd79b90331f1aa8449fcace_36.png)

```html
<a-entity environment="preset: forest;
                       shadow: true;
                       skyType: atmosphere;
                       lightPosition: -1 2 4;">
</a-entity>
```

![](img/285b3d0d8cd79b90331f1aa8449fcace_38.png)

---

## 添加背景音效与交互声音 🔊

![](img/285b3d0d8cd79b90331f1aa8449fcace_40.png)

![](img/285b3d0d8cd79b90331f1aa8449fcace_41.png)

声音是营造沉浸感的关键元素。我们可以为场景添加循环播放的环境背景音。

在A-Frame中，使用`<a-sound>`组件添加声音。由于浏览器的自动播放策略，背景音通常不会自动播放，需要用户交互来触发。

以下是实现代码：

![](img/285b3d0d8cd79b90331f1aa8449fcace_43.png)

![](img/285b3d0d8cd79b90331f1aa8449fcace_45.png)

```html
<!-- 定义一个自动播放但可能被浏览器阻止的背景音 -->
<a-sound src="assets/background.mp3" autoplay="true" loop="true" rolloffFactor="0"></a-sound>

<!-- 更可靠的方法：通过点击场景来播放声音 -->
<a-entity id="soundTrigger" sound="src: assets/background.mp3; on: click;"></a-entity>
```

`rolloffFactor: 0`意味着声音音量不会随距离衰减，在整个场景中都能听到。

---

## 引入物理系统 🏀

为了让物体具有真实的坠落和碰撞效果，我们需要为场景添加物理系统。A-Frame社区提供了`aframe-physics-system`组件。

首先，在HTML头部引入物理系统库：

![](img/285b3d0d8cd79b90331f1aa8449fcace_47.png)

```html
<script src="https://cdn.jsdelivr.net/gh/n5ro/aframe-physics-system@v4.0.1/dist/aframe-physics-system.min.js"></script>
```

![](img/285b3d0d8cd79b90331f1aa8449fcace_49.png)

![](img/285b3d0d8cd79b90331f1aa8449fcace_51.png)

![](img/285b3d0d8cd79b90331f1aa8449fcace_53.png)

![](img/285b3d0d8cd79b90331f1aa8449fcace_55.png)

然后，在场景中启用物理系统，并为需要受物理影响的物体添加`dynamic-body`属性，为静态物体（如地面）添加`static-body`属性。

![](img/285b3d0d8cd79b90331f1aa8449fcace_57.png)

![](img/285b3d0d8cd79b90331f1aa8449fcace_59.png)

以下是添加一个可掉落小球的示例：

![](img/285b3d0d8cd79b90331f1aa8449fcace_61.png)

![](img/285b3d0d8cd79b90331f1aa8449fcace_63.png)

![](img/285b3d0d8cd79b90331f1aa8449fcace_65.png)

![](img/285b3d0d8cd79b90331f1aa8449fcace_67.png)

![](img/285b3d0d8cd79b90331f1aa8449fcace_69.png)

```html
<a-scene physics="debug: false;">

  <!-- 静态地面 -->
  <a-plane static-body position="0 -1 0" rotation="-90 0 0" width="100" height="100" color="#000" shadow></a-plane>

  <!-- 动态小球（食物） -->
  <a-sphere class="interactable" dynamic-body position="0 2 -4" radius="0.3" color="green" shadow></a-sphere>

![](img/285b3d0d8cd79b90331f1aa8449fcace_71.png)

![](img/285b3d0d8cd79b90331f1aa8449fcace_73.png)

![](img/285b3d0d8cd79b90331f1aa8449fcace_75.png)

![](img/285b3d0d8cd79b90331f1aa8449fcace_77.png)

![](img/285b3d0d8cd79b90331f1aa8449fcace_78.png)

![](img/285b3d0d8cd79b90331f1aa8449fcace_79.png)

</a-scene>
```

---

## 创建粒子系统（雨雪效果） 🌧️

粒子系统可以用来模拟雨、雪、火焰等效果，极大地增强场景的动态感和沉浸感。我们将使用`aframe-particle-system-component`组件。

![](img/285b3d0d8cd79b90331f1aa8449fcace_81.png)

![](img/285b3d0d8cd79b90331f1aa8449fcace_83.png)

引入组件库后，可以轻松添加一个下雨效果：

![](img/285b3d0d8cd79b90331f1aa8449fcace_85.png)

![](img/285b3d0d8cd79b90331f1aa8449fcace_87.png)

```html
<script src="https://cdn.jsdelivr.net/gh/idewine/aframe-particle-system-component@v1.1.3/dist/aframe-particle-system-component.min.js"></script>

<a-entity particle-system="preset: rain;
                           color: #AAAAFF;
                           velocityValue: 0 0 -5;
                           particleCount: 5000;">
</a-entity>
```

请注意，某些环境组件可能与粒子系统存在兼容性问题，可能导致渲染异常。如果遇到问题，可以尝试调整环境组件的`fog`属性或粒子系统的参数。

![](img/285b3d0d8cd79b90331f1aa8449fcace_89.png)

![](img/285b3d0d8cd79b90331f1aa8449fcace_91.png)

---

![](img/285b3d0d8cd79b90331f1aa8449fcace_93.png)

![](img/285b3d0d8cd79b90331f1aa8449fcace_94.png)

## 实现传送与控制器交互 🎮

在沉浸式VR中，移动和交互主要依靠手柄控制器。我们将实现两个核心功能：传送移动和物体抓取。

### 传送控制
A-Frame的`teleport-controls`组件允许用户通过手柄指定传送点进行移动。通常将其绑定到非惯用手（如左手）控制器上。

![](img/285b3d0d8cd79b90331f1aa8449fcace_96.png)

```html
<a-entity laser-controls="hand: left" teleport-controls></a-entity>
```

![](img/285b3d0d8cd79b90331f1aa8449fcace_98.png)

### 超级手部交互（抓取物体）
`super-hands`组件提供了强大的抓取、触摸、拖放等交互能力。我们需要引入一系列相关库。

![](img/285b3d0d8cd79b90331f1aa8449fcace_100.png)

![](img/285b3d0d8cd79b90331f1aa8449fcace_102.png)

![](img/285b3d0d8cd79b90331f1aa8449fcace_104.png)

![](img/285b3d0d8cd79b90331f1aa8449fcace_106.png)

![](img/285b3d0d8cd79b90331f1aa8449fcace_108.png)

首先，引入必要的组件：

![](img/285b3d0d8cd79b90331f1aa8449fcace_109.png)

![](img/285b3d0d8cd79b90331f1aa8449fcace_111.png)

![](img/285b3d0d8cd79b90331f1aa8449fcace_113.png)

![](img/285b3d0d8cd79b90331f1aa8449fcace_115.png)

```html
<script src="https://cdn.jsdelivr.net/gh/wmurphyrd/aframe-super-hands-component@v3.1.0/dist/super-hands.min.js"></script>
<script src="https://cdn.jsdelivr.net/gh/wmurphyrd/aframe-physics-extras@v0.2.1/dist/aframe-physics-extras.min.js"></script>
```

![](img/285b3d0d8cd79b90331f1aa8449fcace_117.png)

![](img/285b3d0d8cd79b90331f1aa8449fcace_119.png)

![](img/285b3d0d8cd79b90331f1aa8449fcace_120.png)

然后，为可抓取的物体添加`grabbable`属性，并为手柄控制器添加`super-hands`和`collider`等混入属性（mixins）。

![](img/285b3d0d8cd79b90331f1aa8449fcace_122.png)

![](img/285b3d0d8cd79b90331f1aa8449fcace_124.png)

```html
<!-- 可抓取的食物 -->
<a-sphere class="interactable" grabbable dynamic-body ... ></a-sphere>

![](img/285b3d0d8cd79b90331f1aa8449fcace_126.png)

![](img/285b3d0d8cd79b90331f1aa8449fcace_128.png)

<!-- 右手控制器，具备抓取能力 -->
<a-entity hand-controls="hand: right"
          super-hands
          mixin="collider">
</a-entity>
```

![](img/285b3d0d8cd79b90331f1aa8449fcace_130.png)

![](img/285b3d0d8cd79b90331f1aa8449fcace_132.png)

![](img/285b3d0d8cd79b90331f1aa8449fcace_134.png)

![](img/285b3d0d8cd79b90331f1aa8449fcace_136.png)

这样，用户就可以用手柄抓住“食物”小球，并投掷给长颈鹿了。

![](img/285b3d0d8cd79b90331f1aa8449fcace_137.png)

![](img/285b3d0d8cd79b90331f1aa8449fcace_139.png)

---

![](img/285b3d0d8cd79b90331f1aa8449fcace_141.png)

![](img/285b3d0d8cd79b90331f1aa8449fcace_143.png)

![](img/285b3d0d8cd79b90331f1aa8449fcace_145.png)

## 添加用户界面（UI）与菜单 📱

在VR中，用户界面需要以三维形式融入环境。常见的做法有“抬头显示器”（HUD）和“控制器附着菜单”。

![](img/285b3d0d8cd79b90331f1aa8449fcace_147.png)

![](img/285b3d0d8cd79b90331f1aa8449fcace_148.png)

![](img/285b3d0d8cd79b90331f1aa8449fcace_149.png)

### 抬头显示器（HUD）
HUD将UI元素（如分数、状态）固定在摄像机前方，始终处于用户视野内。

![](img/285b3d0d8cd79b90331f1aa8449fcace_151.png)

![](img/285b3d0d8cd79b90331f1aa8449fcace_153.png)

![](img/285b3d0d8cd79b90331f1aa8449fcace_154.png)

![](img/285b3d0d8cd79b90331f1aa8449fcace_156.png)

```html
<a-entity camera look-controls>
  <a-entity position="0 0 -1" text="value: Score: 0; align: center;" geometry="primitive: plane; width: 0.5; height: 0.1" material="color: black; opacity: 0.7"></a-entity>
</a-entity>
```

![](img/285b3d0d8cd79b90331f1aa8449fcace_158.png)

![](img/285b3d0d8cd79b90331f1aa8449fcace_160.png)

### 控制器菜单
将菜单附着在控制器上，用户可以通过按钮呼出菜单并进行选择，这是一种更符合VR直觉的交互方式。实现此功能需要编写自定义组件来处理菜单的显示、隐藏以及与控制器按钮的交互。

![](img/285b3d0d8cd79b90331f1aa8449fcace_162.png)

![](img/285b3d0d8cd79b90331f1aa8449fcace_164.png)

![](img/285b3d0d8cd79b90331f1aa8449fcace_166.png)

---

![](img/285b3d0d8cd79b90331f1aa8449fcace_168.png)

![](img/285b3d0d8cd79b90331f1aa8449fcace_169.png)

![](img/285b3d0d8cd79b90331f1aa8449fcace_171.png)

![](img/285b3d0d8cd79b90331f1aa8449fcace_173.png)

![](img/285b3d0d8cd79b90331f1aa8449fcace_175.png)

## 适配Cardboard设备 📱

![](img/285b3d0d8cd79b90331f1aa8449fcace_177.png)

![](img/285b3d0d8cd79b90331f1aa8449fcace_179.png)

虽然本节主要针对高端VR头显，但许多功能经过简化也能在Cardboard上运行。最关键的区别是Cardboard没有手柄，交互主要依靠凝视和点击。

![](img/285b3d0d8cd79b90331f1aa8449fcace_181.png)

![](img/285b3d0d8cd79b90331f1aa8449fcace_182.png)

![](img/285b3d0d8cd79b90331f1aa8449fcace_184.png)

例如，可以实现“凝视传送”：用户注视场景中的特定传送点一段时间后，自动传送到该位置。

```html
<a-entity cursor="fuse: true; fuseTimeout: 1500;"
         animation__click="property: scale; startEvents: click; from: 0.1 0.1 0.1; to: 1 1 1; dur: 150">
  <a-entity position="0 0 -1" geometry="primitive: ring; radiusInner: 0.02; radiusOuter: 0.03" material="color: white; shader: flat"></a-entity>
</a-entity>

![](img/285b3d0d8cd79b90331f1aa8449fcace_186.png)

![](img/285b3d0d8cd79b90331f1aa8449fcace_188.png)

<!-- 传送点 -->
<a-ring class="teleport-spot" radius-inner="0.5" radius-outer="0.6" color="blue" position="2 0 -3"
        event-set__enter="_event: mouseenter; scale: 1.2 1.2 1.2"
        event-set__leave="_event: mouseleave; scale: 1 1 1"
        set-pos-on-click="_event: click; target: #cameraRig; x: 2; z: -3">
</a-ring>
```

![](img/285b3d0d8cd79b90331f1aa8449fcace_190.png)

![](img/285b3d0d8cd79b90331f1aa8449fcace_192.png)

![](img/285b3d0d8cd79b90331f1aa8449fcace_194.png)

---

## 总结 🎯

![](img/285b3d0d8cd79b90331f1aa8449fcace_196.png)

![](img/285b3d0d8cd79b90331f1aa8449fcace_198.png)

本节课中，我们一起学习了如何构建一个完整的沉浸式WebXR VR体验。我们从添加环境与光照开始，逐步引入了背景音效、物理系统、粒子效果，并实现了通过手柄进行传送和抓取物体等高级交互。我们还探讨了为Cardboard设备适配的关键点。通过组合使用这些组件和技术，你可以创造出丰富、互动且引人入胜的虚拟现实世界。

![](img/285b3d0d8cd79b90331f1aa8449fcace_200.png)

![](img/285b3d0d8cd79b90331f1aa8449fcace_202.png)

![](img/285b3d0d8cd79b90331f1aa8449fcace_203.png)

下一步，我们将进入增强现实（AR）部分，探索如何利用WebXR和A-Frame在真实世界中叠加数字内容。