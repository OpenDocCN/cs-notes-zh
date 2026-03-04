# 扩展现实开发：第8章：WebXR平台入门实践 🚀

![](img/7a2f83583c2eb552671755264b5cf7e4_0.png)

![](img/7a2f83583c2eb552671755264b5cf7e4_1.png)

在本节课中，我们将学习如何使用A-Frame作为主要工具来开发WebXR场景。我们将涵盖A-Frame的基础知识、开发环境设置，并实际操作创建和运行VR与AR场景。

---

## A-Frame概述 🧱

上一节我们介绍了WebXR的概念，本节中我们来看看A-Frame这个具体的开发工具。

A-Frame是一个基于Three.js和WebGL的Web框架。Three.js是一个流行的图形库，它构建在WebGL之上，允许A-Frame渲染3D场景。A-Frame通过引入一系列以`a-`为前缀的HTML标签（如`<a-scene>`、`<a-box>`、`<a-cylinder>`）来简化3D场景的创建。

![](img/7a2f83583c2eb552671755264b5cf7e4_3.png)

![](img/7a2f83583c2eb552671755264b5cf7e4_4.png)

A-Frame遵循**实体-组件系统（ECS）**架构，拥有丰富的开源组件库。它内置了资源管理系统，支持图像、视频、音频以及3D模型（首选GLTF格式，也支持OBJ/MTL等格式）。

![](img/7a2f83583c2eb552671755264b5cf7e4_6.png)

## 开发环境与工具 🛠️

![](img/7a2f83583c2eb552671755264b5cf7e4_8.png)

![](img/7a2f83583c2eb552671755264b5cf7e4_9.png)

![](img/7a2f83583c2eb552671755264b5cf7e4_10.png)

![](img/7a2f83583c2eb552671755264b5cf7e4_11.png)

要开始使用A-Frame，你需要一个合适的开发环境。以下是几种推荐的选择：

*   **Glitch**：一个在线代码编辑器，可以即时预览场景，非常适合快速原型设计和学习。
*   **CodePen**：另一个流行的在线前端开发环境，你可以创建“笔”来编写和展示A-Frame代码。
*   **GitHub**：适合更专业的开发工作流，你可以托管代码并使用本地服务器进行开发。

A-Frame还附带一个非常实用的**检查器（Inspector）**。在A-Frame场景中按下 `Ctrl + I`（Windows）或 `Cmd + Option + I`（Mac）即可打开。它虽然不是像Unity那样的完整编辑器，但允许你：
*   使用3D控件（Gizmos）直观地移动、旋转和缩放场景中的物体。
*   查看和修改实体的组件属性。
*   将调整后的值复制到你的代码中。

![](img/7a2f83583c2eb552671755264b5cf7e4_13.png)

![](img/7a2f83583c2eb552671755264b5cf7e4_14.png)

## 创建你的第一个A-Frame场景 🌍

现在，让我们动手创建一个基础的A-Frame场景。我们将从经典的“Hello WebVR”示例开始。

核心的A-Frame场景结构如下：
```html
<a-scene>
  <a-box position="-1 0.5 -3" rotation="0 45 0" color="#4CC3D9"></a-box>
  <a-sphere position="0 1.25 -5" radius="1.25" color="#EF2D5E"></a-sphere>
  <a-cylinder position="1 0.75 -3" radius="0.5" height="1.5" color="#FFC65D"></a-cylinder>
  <a-plane position="0 0 -4" rotation="-90 0 0" width="4" height="4" color="#7BC8A4"></a-plane>
  <a-sky color="#ECECEC"></a-sky>
</a-scene>
```

![](img/7a2f83583c2eb552671755264b5cf7e4_16.png)

在这个场景中：
*   `<a-scene>` 是根容器，所有3D对象都包含在其中。
*   `<a-box>`、`<a-sphere>`、`<a-cylinder>`、`<a-plane>` 是基本的几何图形实体。
*   `position`、`rotation`、`color` 等是这些实体的属性。
*   `<a-sky>` 用于设置场景的背景。

![](img/7a2f83583c2eb552671755264b5cf7e4_18.png)

![](img/7a2f83583c2eb552671755264b5cf7e4_20.png)

![](img/7a2f83583c2eb552671755264b5cf7e4_21.png)

在浏览器中打开这个HTML文件，你可以用鼠标拖拽来环视场景，并使用 `W/A/S/D` 键在场景中“行走”。

![](img/7a2f83583c2eb552671755264b5cf7e4_23.png)

![](img/7a2f83583c2eb552671755264b5cf7e4_24.png)

## 在VR设备中运行场景 🥽

要让场景在VR头显（如Oculus Rift S）中运行，你需要：
1.  使用支持WebXR的浏览器，例如 **Firefox** 或 **Chrome（需开启标志）**。
2.  确保你的VR头显已正确连接电脑。
3.  在A-Frame场景中，点击出现的 **“Enter VR”** 按钮。

![](img/7a2f83583c2eb552671755264b5cf7e4_26.png)

![](img/7a2f83583c2eb552671755264b5cf7e4_27.png)

![](img/7a2f83583c2eb552671755264b5cf7e4_28.png)

![](img/7a2f83583c2eb552671755264b5cf7e4_29.png)

成功进入后，你将沉浸在这个3D世界中。A-Frame会自动处理立体渲染和头部追踪。

## 将场景转换为AR体验 📱

![](img/7a2f83583c2eb552671755264b5cf7e4_31.png)

将VR场景转换为AR体验主要涉及两个关键变化：

![](img/7a2f83583c2eb552671755264b5cf7e4_33.png)

![](img/7a2f83583c2eb552671755264b5cf7e4_34.png)

1.  **背景替换**：将固定的背景（如 `<a-sky>`）替换为设备的实时摄像头画面。
2.  **比例调整**：AR中的物体需要以符合现实世界感知的比例出现（通常较小且靠近用户）。

以下是一个简单的AR场景框架示例：
```html
<a-scene embedded arjs>
  <!-- 使用摄像头作为背景 -->
  <a-camera gps-camera rotation-reader> </a-camera>
  <!-- 将原有物体组合到一个实体中，方便整体缩放和定位 -->
  <a-entity position="0 1.2 -1" scale="0.15 0.15 0.15">
    <a-box position="-1 0.5 -3" color="#4CC3D9"></a-box>
    <a-sphere position="0 1.25 -5" color="#EF2D5E"></a-sphere>
    <!-- ... 其他几何体 -->
  </a-entity>
</a-scene>
```
*   我们添加了 `arjs` 组件（需要引入AR.js库）来启用AR功能。
*   将物体包裹在 `<a-entity>` 中，并通过 `scale` 属性将其整体缩小，使其在手机屏幕上看起来大小合适。
*   调整 `position` 使物体悬浮在摄像头前方一个舒适的位置。

在手机上通过支持WebXR的浏览器（如iOS的WebARonARKit或安卓的ARCore兼容浏览器）访问该页面，即可看到3D物体叠加在现实世界画面上。

## 实时编辑与工作流 🔄

![](img/7a2f83583c2eb552671755264b5cf7e4_36.png)

![](img/7a2f83583c2eb552671755264b5cf7e4_38.png)

使用Glitch或CodePen等在线编辑器的一个巨大优势是**实时预览**。你可以：
*   在代码编辑器一侧修改代码（例如颜色、位置）。
*   另一侧的预览窗口会几乎即时更新。
*   如果你正戴着VR头显，也能立刻看到场景的变化。

这种即时反馈循环极大地加快了学习和开发调试的速度。

![](img/7a2f83583c2eb552671755264b5cf7e4_40.png)

---

![](img/7a2f83583c2eb552671755264b5cf7e4_42.png)

本节课中我们一起学习了WebXR开发的核心工具A-Frame。我们从其基础架构讲起，介绍了开发环境与检查器工具，并逐步实践了如何创建基础3D场景、在VR设备中运行它，以及如何将其转换为移动AR体验。A-Frame以其基于Web技术的亲和力，为有一定网页开发基础的学习者提供了一个接触XR开发的绝佳入口。在接下来的课程中，我们将继续探索更复杂的交互和组件。