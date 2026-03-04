# 097：AR-VR框架应用答疑会 🎓

![](img/84dfb47be7e35e8c419bfa1eae2faa09_1.png)

![](img/84dfb47be7e35e8c419bfa1eae2faa09_2.png)

![](img/84dfb47be7e35e8c419bfa1eae2faa09_4.png)

![](img/84dfb47be7e35e8c419bfa1eae2faa09_6.png)

在本节答疑会中，我们将聚焦于专项课程的第三门课程——开发课程，特别是使用A-Frame框架进行WebXR开发。我们将回顾课程作业要求，并通过一个太阳系示例项目，演示如何从构思到实现一个完整的3D、VR及AR场景。本节内容旨在为初学者提供清晰的指引和实用的技巧。

---

## 课程概述与答疑会目标

大家好。这是本学期计划的三次答疑会之一。本次答疑会主要针对扩展现实专项课程的第三门开发课程。

![](img/84dfb47be7e35e8c419bfa1eae2faa09_8.png)

这门课程专注于开发，涵盖了多种平台，包括Unity、Unreal Engine以及WebXR（使用A-Frame）。课程旨在教授如何在不同平台上进行XR开发，而不仅仅是学习某个特定工具。今天的答疑会将重点讨论A-Frame，并展示如何完成课程中的作业。

![](img/84dfb47be7e35e8c419bfa1eae2faa09_10.png)

课程作业主要包含三个部分：
1.  **构建3D场景**：创建一个基础的3D环境。
2.  **构建VR场景**：将3D场景扩展为更具沉浸感的虚拟现实体验。
3.  **构建AR场景**：创建基于标记或无标记的增强现实体验。

![](img/84dfb47be7e35e8c419bfa1eae2faa09_12.png)

![](img/84dfb47be7e35e8c419bfa1eae2faa09_13.png)

接下来，我们将深入了解A-Frame，并逐步构建一个太阳系示例项目。

![](img/84dfb47be7e35e8c419bfa1eae2faa09_15.png)

![](img/84dfb47be7e35e8c419bfa1eae2faa09_17.png)

![](img/84dfb47be7e35e8c419bfa1eae2faa09_18.png)

![](img/84dfb47be7e35e8c419bfa1eae2faa09_20.png)

---

![](img/84dfb47be7e35e8c419bfa1eae2faa09_22.png)

![](img/84dfb47be7e35e8c419bfa1eae2faa09_24.png)

![](img/84dfb47be7e35e8c419bfa1eae2faa09_25.png)

![](img/84dfb47be7e35e8c419bfa1eae2faa09_26.png)

## A-Frame简介与核心工具

![](img/84dfb47be7e35e8c419bfa1eae2faa09_28.png)

![](img/84dfb47be7e35e8c419bfa1eae2faa09_30.png)

A-Frame是一个基于HTML的WebXR框架，它让构建3D和XR体验变得像编写网页一样简单。其核心思想是使用HTML标签（称为“实体”）来描述3D世界中的对象。

![](img/84dfb47be7e35e8c419bfa1eae2faa09_32.png)

![](img/84dfb47be7e35e8c419bfa1eae2faa09_33.png)

### 关键工具：场景检查器与代码控制台

![](img/84dfb47be7e35e8c419bfa1eae2faa09_35.png)

![](img/84dfb47be7e35e8c419bfa1eae2faa09_36.png)

在开始开发前，掌握两个关键工具至关重要：**场景检查器**和**浏览器开发者控制台**。

![](img/84dfb47be7e35e8c419bfa1eae2faa09_38.png)

![](img/84dfb47be7e35e8c419bfa1eae2faa09_39.png)

**场景检查器**是一个内置的调试工具，允许你实时查看和修改场景中的元素。激活它的键盘快捷键是：
*   **Windows系统**：`Ctrl + Alt + I`
*   **Mac系统**：`Ctrl + Option + I`

![](img/84dfb47be7e35e8c419bfa1eae2faa09_41.png)

![](img/84dfb47be7e35e8c419bfa1eae2faa09_42.png)

激活后，你可以选择场景中的物体，查看其属性（如位置、旋转、材质），甚至直接修改这些属性。虽然修改不会永久保存，但这是一个极佳的学习和调试方式。

**浏览器开发者控制台**（通常按F12打开）对于查看JavaScript错误、日志输出和网络请求至关重要。推荐使用Chrome浏览器以获得最佳的WebXR支持。

![](img/84dfb47be7e35e8c419bfa1eae2faa09_44.png)

### A-Frame基础模板

![](img/84dfb47be7e35e8c419bfa1eae2faa09_46.png)

![](img/84dfb47be7e35e8c419bfa1eae2faa09_47.png)

![](img/84dfb47be7e35e8c419bfa1eae2faa09_49.png)

![](img/84dfb47be7e35e8c419bfa1eae2faa09_51.png)

一个最基本的A-Frame场景模板如下所示：

```html
<html>
  <head>
    <script src="https://aframe.io/releases/1.4.0/aframe.min.js"></script>
  </head>
  <body>
    <a-scene>
      <!-- 3D物体将在这里添加 -->
      <a-box position="-1 0.5 -3" rotation="0 45 0" color="#4CC3D9"></a-box>
      <a-sphere position="0 1.25 -5" radius="1.25" color="#EF2D5E"></a-sphere>
      <a-plane position="0 0 -4" rotation="-90 0 0" width="4" height="4" color="#7BC8A4"></a-plane>
      <a-sky color="#ECECEC"></a-sky>
    </a-scene>
  </body>
</html>
```

![](img/84dfb47be7e35e8c419bfa1eae2faa09_53.png)

![](img/84dfb47be7e35e8c419bfa1eae2faa09_55.png)

![](img/84dfb47be7e35e8c419bfa1eae2faa09_56.png)

![](img/84dfb47be7e35e8c419bfa1eae2faa09_58.png)

![](img/84dfb47be7e35e8c419bfa1eae2faa09_60.png)

这个模板包含了A-Frame库，并定义了一个简单的场景，其中有一个立方体、一个球体、一个平面和天空背景。

![](img/84dfb47be7e35e8c419bfa1eae2faa09_62.png)

![](img/84dfb47be7e35e8c419bfa1eae2faa09_63.png)

---

![](img/84dfb47be7e35e8c419bfa1eae2faa09_65.png)

![](img/84dfb47be7e35e8c419bfa1eae2faa09_66.png)

## 项目实战：构建太阳系3D场景 🌞

上一节我们介绍了A-Frame的基础工具和模板，本节中我们来看看如何应用这些知识来构建课程要求的3D场景。我们将以创建一个互动的太阳系为例。

### 第一步：设计与规划

![](img/84dfb47be7e35e8c419bfa1eae2faa09_68.png)

在编码之前，进行设计规划非常重要。这符合第二门课程（设计课程）中强调的设计思维流程。

![](img/84dfb47be7e35e8c419bfa1eae2faa09_70.png)

![](img/84dfb47be7e35e8c419bfa1eae2faa09_71.png)

![](img/84dfb47be7e35e8c419bfa1eae2faa09_72.png)

![](img/84dfb47be7e35e8c419bfa1eae2faa09_74.png)

1.  **灵感来源**：参考NASA的太阳系模拟器等现有体验。
2.  **绘制草图**：简单勾勒出场景布局，例如太阳在中心，地球绕太阳公转，月球绕地球公转。
3.  **定义目标**：明确场景中需要包含的元素，例如3D模型、光照、动画和交互。

![](img/84dfb47be7e35e8c419bfa1eae2faa09_76.png)

![](img/84dfb47be7e35e8c419bfa1eae2faa09_77.png)

![](img/84dfb47be7e35e8c419bfa1eae2faa09_79.png)

![](img/84dfb47be7e35e8c419bfa1eae2faa09_81.png)

### 第二步：搭建基础场景

![](img/84dfb47be7e35e8c419bfa1eae2faa09_83.png)

![](img/84dfb47be7e35e8c419bfa1eae2faa09_84.png)

我们从A-Frame基础模板开始，逐步添加元素。

![](img/84dfb47be7e35e8c419bfa1eae2faa09_86.png)

1.  **创建天体和轨道**：使用`<a-sphere>`标签创建太阳、地球和月球，并通过设置`position`和`animation`属性让它们动起来。
2.  **添加材质与纹理**：为球体应用从NASA等合法来源获取的纹理贴图，使它们看起来更真实。例如，为地球应用昼夜两种纹理。
3.  **设置光照与环境**：添加点光源（模拟太阳光），并设置雾效和背景颜色来营造空间感。

以下是让地球绕太阳旋转的动画代码示例：

![](img/84dfb47be7e35e8c419bfa1eae2faa09_88.png)

![](img/84dfb47be7e35e8c419bfa1eae2faa09_89.png)

![](img/84dfb47be7e35e8c419bfa1eae2faa09_91.png)

![](img/84dfb47be7e35e8c419bfa1eae2faa09_93.png)

```html
<a-sphere id="earth" radius="0.5" src="assets/earth-day.jpg">
  <a-animation attribute="rotation"
               dur="20000"
               fill="forwards"
               to="0 360 0"
               repeat="indefinite">
  </a-animation>
</a-sphere>
```

### 第三步：实现交互与多视角

![](img/84dfb47be7e35e8c419bfa1eae2faa09_95.png)

为了增加场景的趣味性和完成作业要求，我们可以添加一些交互功能。

![](img/84dfb47be7e35e8c419bfa1eae2faa09_97.png)

![](img/84dfb47be7e35e8c419bfa1eae2faa09_99.png)

以下是实现的一些关键交互：

*   **切换昼夜**：通过按下‘N’键，切换地球的纹理（从白天地图切换到黑夜地图），并改变场景光照颜色。
*   **显示/隐藏轨道**：通过按下‘V’键，控制是否显示行星的运行轨迹线。
*   **多相机视角**：实现按‘C’键在不同预置相机间切换的功能，例如一个跟随地球的相机，一个跟随月球的相机，以及一个自由飞行相机。

![](img/84dfb47be7e35e8c419bfa1eae2faa09_101.png)

![](img/84dfb47be7e35e8c419bfa1eae2faa09_103.png)

![](img/84dfb47be7e35e8c419bfa1eae2faa09_105.png)

这些交互主要通过编写JavaScript函数，监听键盘事件并修改相应实体的属性来实现。

---

![](img/84dfb47be7e35e8c419bfa1eae2faa09_107.png)

![](img/84dfb47be7e35e8c419bfa1eae2faa09_108.png)

## 进阶：将3D场景转换为VR与AR体验 🥽

![](img/84dfb47be7e35e8c419bfa1eae2faa09_110.png)

![](img/84dfb47be7e35e8c419bfa1eae2faa09_112.png)

![](img/84dfb47be7e35e8c419bfa1eae2faa09_114.png)

我们已经完成了一个功能丰富的3D太阳系场景，接下来看看如何将其升级为VR和AR体验。

![](img/84dfb47be7e35e8c419bfa1eae2faa09_115.png)

![](img/84dfb47be7e35e8c419bfa1eae2faa09_117.png)

![](img/84dfb47be7e35e8c419bfa1eae2faa09_119.png)

![](img/84dfb47be7e35e8c419bfa1eae2faa09_120.png)

### 创建VR版本

![](img/84dfb47be7e35e8c419bfa1eae2faa09_122.png)

![](img/84dfb47be7e35e8c419bfa1eae2faa09_124.png)

将现有3D场景转换为VR体验，核心是添加对VR设备的支持和自然的交互方式。

![](img/84dfb47be7e35e8c419bfa1eae2faa09_126.png)

![](img/84dfb47be7e35e8c419bfa1eae2faa09_128.png)

![](img/84dfb47be7e35e8c419bfa1eae2faa09_129.png)

![](img/84dfb47be7e35e8c419bfa1eae2faa09_130.png)

以下是需要添加的关键组件：

![](img/84dfb47be7e35e8c419bfa1eae2faa09_132.png)

![](img/84dfb47be7e35e8c419bfa1eae2faa09_134.png)

![](img/84dfb47be7e35e8c419bfa1eae2faa09_135.png)

![](img/84dfb47be7e35e8c419bfa1eae2faa09_136.png)

1.  **相机设备**：使用`<a-entity camera="active: true”>`和`<a-entity oculus-go-controls>`等组件来配置VR相机和控制器。
2.  **移动机制**：集成`teleport-controls`组件，允许用户通过瞬移在场景中自由移动。
3.  **手部交互**：使用`super-hands`等组件，让用户可以用虚拟手抓取、移动场景中的物体（例如行星）。这通常还需要添加物理引擎组件来处理碰撞。

![](img/84dfb47be7e35e8c419bfa1eae2faa09_137.png)

![](img/84dfb47be7e35e8c419bfa1eae2faa09_139.png)

![](img/84dfb47be7e35e8c419bfa1eae2faa09_141.png)

![](img/84dfb47be7e35e8c419bfa1eae2faa09_142.png)

![](img/84dfb47be7e35e8c419bfa1eae2faa09_143.png)

你可以从一个VR项目模板开始，然后将你的太阳系内容移植进去，这样可以快速获得基础的VR交互功能。

![](img/84dfb47be7e35e8c419bfa1eae2faa09_145.png)

![](img/84dfb47be7e35e8c419bfa1eae2faa09_146.png)

![](img/84dfb47be7e35e8c419bfa1eae2faa09_147.png)

![](img/84dfb47be7e35e8c419bfa1eae2faa09_148.png)

### 创建AR版本

![](img/84dfb47be7e35e8c419bfa1eae2faa09_149.png)

![](img/84dfb47be7e35e8c419bfa1eae2faa09_151.png)

![](img/84dfb47be7e35e8c419bfa1eae2faa09_152.png)

A-Frame支持两种主要的WebAR方式：基于标记的AR（使用AR.js）和无标记的AR（使用8th Wall或A-Frame的AR模块）。

![](img/84dfb47be7e35e8c419bfa1eae2faa09_154.png)

![](img/84dfb47be7e35e8c419bfa1eae2faa09_156.png)

以下是两种方式的简要说明：

1.  **基于标记的AR**：
    *   需要定义一个特定的图像作为标记（Marker）。
    *   当设备摄像头识别到该标记时，太阳系场景就会在标记上方渲染出来。
    *   优点是实现相对简单，跟踪稳定。

![](img/84dfb47be7e35e8c419bfa1eae2faa09_158.png)

![](img/84dfb47be7e35e8c419bfa1eae2faa09_160.png)

2.  **无标记的AR**：
    *   使用SLAM（即时定位与地图构建）技术，将虚拟物体锚定在真实世界的平面上。
    *   用户打开网页，授予摄像头权限后，就可以直接将太阳系放置在桌面、地板等现实表面上。
    *   体验更自然，但受浏览器和设备支持限制较大（例如iOS支持有限）。

![](img/84dfb47be7e35e8c419bfa1eae2faa09_162.png)

![](img/84dfb47be7e35e8c419bfa1eae2faa09_163.png)

在AR版本中，你同样可以保留3D场景中的交互功能（如切换昼夜），并通过触摸屏手势或屏幕按钮来触发。

![](img/84dfb47be7e35e8c419bfa1eae2faa09_165.png)

---

![](img/84dfb47be7e35e8c419bfa1eae2faa09_167.png)

![](img/84dfb47be7e35e8c419bfa1eae2faa09_169.png)

![](img/84dfb47be7e35e8c419bfa1eae2faa09_170.png)

![](img/84dfb47be7e35e8c419bfa1eae2faa09_172.png)

## 常见问题与趋势探讨 ❓

![](img/84dfb47be7e35e8c419bfa1eae2faa09_174.png)

![](img/84dfb47be7e35e8c419bfa1eae2faa09_176.png)

在答疑会最后，我们探讨了一些学习者提出的常见问题和对未来的展望。

### 关于VR体验中的新手引导

有学习者询问，在VR叙事体验中，应该先弹出2D说明还是让用户直接进入场景。最佳实践是**将引导直接融入3D环境本身**，避免使用破坏沉浸感的2D弹窗。例如，可以将操作提示作为跟随控制器的浮动工具提示，或者在用户首次拿起关键物品时给出上下文提示。

### 关于AR技术趋势与挑战

当前AR技术正变得更加普及。一个显著趋势是VR头显（如Meta Quest 2）开始具备“视频透视”功能，未来随着摄像头升级，可能演变为真正的混合现实设备，这将极大推动AR的普及。

然而，挑战依然存在。一个主要障碍是**WebXR标准的跨平台支持**。目前苹果设备对WebXR的支持较弱，这限制了基于网页的XR体验的广泛传播。一旦标准得到所有主流平台的全力支持，基于Web的XR内容创作和分发将迎来爆发式增长，就像当年Web的普及一样。

---

## 总结与资源

本节课中我们一起学习了如何使用A-Frame框架来逐步完成扩展现实开发课程的作业。我们从创建一个基础的3D太阳系场景开始，为其添加了材质、光照、动画和交互。接着，我们探讨了如何将这个3D场景升级为支持设备追踪和自然交互的VR体验，以及如何通过不同技术将其部署为AR应用。

记住，开发XR体验是一个迭代过程，从简单原型开始，逐步增加复杂性。充分利用A-Frame社区提供的丰富组件和模板，可以大大提高开发效率。

**附加学习资源**：
*   **A-Frame官方文档**：获取最全面的API参考和教程。
*   **Glitch平台**：一个优秀的在线代码编辑和托管平台，非常适合快速原型设计和分享A-Frame项目。
*   **专项课程荣誉作业**：查看其他学习者在课程中完成的优秀项目，获取灵感和学习思路。

希望本次答疑会能帮助你更好地进行XR开发探索。祝你学习愉快！