![](img/aaaefbf2efbb53e09751d053216a6b5a_1.png)

# GAMES401-泛动引擎(PeriDyno)物理仿真编程与实践 - P1：物理仿真及PeriDyno开源引擎架构简介 🚀

在本节课中，我们将学习物理仿真的基本概念，并了解PeriDyno开源物理仿真引擎的整体架构。课程将从宏观背景入手，逐步深入到引擎的模块化设计、开发流程和核心思想，为后续的实践课程打下基础。

## 概述：物理仿真与人工智能

我们的世界可以粗略地分为物质世界和精神世界。物理仿真研究的是我们赖以生存的客观物质世界，例如海洋、火焰、汽车等符合物理规律的存在。它旨在用计算机模拟这些物理介质的力学行为。

人工智能则主要研究精神世界中的内容，如运动、感觉、语言理解、视觉等。

在图形学领域，物理仿真为虚拟世界赋予真实的物理属性。例如，在游戏中，它确保角色不会穿墙而过，跳跃符合重力规律。从更宏大的视角看，物理仿真技术是构建高度拟真虚拟世界的基石。

## 物理仿真引擎的作用

物理仿真引擎能为开发者提供以下支持：
*   **提供开发脚手架**：为初学者或新算法实践提供基础框架。
*   **集成通用功能**：封装与仿真核心算法无关的模块，如渲染、UI、数据导入导出等，让研究者专注于算法本身。
*   **便于算法对比**：引擎内集成多种算法，便于进行研究对比或响应审稿意见。

## PeriDyno引擎架构概览

一个典型的仿真引擎（以PeriDyno为例）包含多个层次：
*   **硬件层**：与CPU、GPU、内存、硬盘打交道的底层API。
*   **基础数据结构与算法层**：包含数据库、图形接口、碰撞检测等通用算法。
*   **核心仿真算法层**：集成各种仿真算法，如有限元法（FEM）、光滑粒子流体动力学（SPH）、刚体动力学等。
*   **管理层与交互层**：包含场景管理、模块管理、UI界面等，用于组合算法并可视化。

## 开发环境搭建与工作流程

以下是基于Windows平台搭建PeriDyno开发环境的基本流程，分为构建、配置和开发三个阶段。

### 第一阶段：获取源码（Git）

Git是一个分布式版本控制系统，用于管理代码的修改历史、支持多人协作开发。

![](img/aaaefbf2efbb53e09751d053216a6b5a_3.png)

以下是Git的核心概念与常用指令：

**初始化与克隆**
*   `git init`：在当前目录初始化一个新的Git仓库。
*   `git clone --recursive <仓库地址>`：克隆远程仓库到本地。**必须添加 `--recursive` 参数**，以同步拉取所有子模块。

**同步与提交**
*   `git fetch`：从远程仓库获取最新信息。
*   `git pull`：拉取远程仓库的更新并合并到本地。
*   `git push`：将本地提交推送到远程仓库。
*   `git add`：将文件更改添加到暂存区。
*   `git commit -m “提交信息”`：提交更改到本地仓库。

![](img/aaaefbf2efbb53e09751d053216a6b5a_5.png)

![](img/aaaefbf2efbb53e09751d053216a6b5a_7.png)

**分支管理**
*   `git branch <分支名>`：创建新分支。
*   `git checkout <分支名>`：切换到指定分支。
*   `git merge <分支名>`：将指定分支合并到当前分支。

建议使用GUI工具（如GitHub Desktop, SmartGit, SourceTree）进行可视化操作，更为直观便捷。

### 第二阶段：生成工程（CMake）

克隆源码后，需要使用CMake工具生成具体的IDE工程文件（如Visual Studio的.sln文件）。

![](img/aaaefbf2efbb53e09751d053216a6b5a_9.png)

操作步骤如下：
1.  打开CMake GUI。
2.  设置源码路径（包含`CMakeLists.txt`的根目录）。
3.  设置生成路径（建议新建一个`build`目录）。
4.  点击“Configure”，选择编译器（如Visual Studio 2019）和平台（x64）。
5.  解决可能的配置错误（例如，若启用Qt，需手动指定Qt5Config.cmake文件的路径）。
6.  点击“Generate”生成工程文件。

![](img/aaaefbf2efbb53e09751d053216a6b5a_11.png)

![](img/aaaefbf2efbb53e09751d053216a6b5a_12.png)

![](img/aaaefbf2efbb53e09751d053216a6b5a_14.png)

![](img/aaaefbf2efbb53e09751d053216a6b5a_16.png)

![](img/aaaefbf2efbb53e09751d053216a6b5a_18.png)

![](img/aaaefbf2efbb53e09751d053216a6b5a_20.png)

### 第三阶段：开发与调试（IDE）

![](img/aaaefbf2efbb53e09751d053216a6b5a_22.png)

![](img/aaaefbf2efbb53e09751d053216a6b5a_24.png)

![](img/aaaefbf2efbb53e09751d053216a6b5a_25.png)

![](img/aaaefbf2efbb53e09751d053216a6b5a_27.png)

![](img/aaaefbf2efbb53e09751d053216a6b5a_29.png)

用Visual Studio打开生成的.sln文件，即可进行编译、运行和调试。

![](img/aaaefbf2efbb53e09751d053216a6b5a_31.png)

![](img/aaaefbf2efbb53e09751d053216a6b5a_32.png)

![](img/aaaefbf2efbb53e09751d053216a6b5a_34.png)

![](img/aaaefbf2efbb53e09751d053216a6b5a_35.png)

![](img/aaaefbf2efbb53e09751d053216a6b5a_36.png)

![](img/aaaefbf2efbb53e09751d053216a6b5a_38.png)

![](img/aaaefbf2efbb53e09751d053216a6b5a_40.png)

![](img/aaaefbf2efbb53e09751d053216a6b5a_41.png)

![](img/aaaefbf2efbb53e09751d053216a6b5a_43.png)

![](img/aaaefbf2efbb53e09751d053216a6b5a_45.png)

![](img/aaaefbf2efbb53e09751d053216a6b5a_47.png)

创建一个新项目的基本方法是：在`examples/`目录下复制一个现有样例的CMake脚本和源码，修改工程名称，并重新运行CMake生成。新项目会出现在解决方案中，编译后运行会显示一个基础的GUI窗口。

![](img/aaaefbf2efbb53e09751d053216a6b5a_48.png)

![](img/aaaefbf2efbb53e09751d053216a6b5a_50.png)

![](img/aaaefbf2efbb53e09751d053216a6b5a_52.png)

![](img/aaaefbf2efbb53e09751d053216a6b5a_54.png)

## PeriDyno核心架构：四层模型

![](img/aaaefbf2efbb53e09751d053216a6b5a_56.png)

![](img/aaaefbf2efbb53e09751d053216a6b5a_58.png)

![](img/aaaefbf2efbb53e09751d053216a6b5a_60.png)

![](img/aaaefbf2efbb53e09751d053216a6b5a_62.png)

PeriDyno采用**场景(Scene) -> 节点(Node) -> 管线(Pipeline) -> 模块(Module)**的四层结构来实现高度模块化和解耦。

![](img/aaaefbf2efbb53e09751d053216a6b5a_64.png)

### 1. 数据 (Field)

![](img/aaaefbf2efbb53e09751d053216a6b5a_66.png)

数据层是模块间输入输出的载体。主要分为两类：
*   **基本类型**：数据量小，可直接在CPU/GPU间传递。使用`DEF_VAR`宏定义，例如：
    ```cpp
    DEF_VAR(float, FloatValue, "A float value");
    ```
*   **数组类型**：用于存储大规模数据（如粒子位置）。使用`DEF_ARRAY`宏定义，例如：
    ```cpp
    DEF_ARRAY(float, FloatArray, DeviceType::GPU, "An array of floats");
    ```
所有定义的数据字段都会自动与UI界面联动，可在运行时动态调整参数。

![](img/aaaefbf2efbb53e09751d053216a6b5a_68.png)

![](img/aaaefbf2efbb53e09751d053216a6b5a_70.png)

### 2. 模块 (Module)

![](img/aaaefbf2efbb53e09751d053216a6b5a_72.png)

![](img/aaaefbf2efbb53e09751d053216a6b5a_74.png)

![](img/aaaefbf2efbb53e09751d053216a6b5a_76.png)

![](img/aaaefbf2efbb53e09751d053216a6b5a_77.png)

![](img/aaaefbf2efbb53e09751d053216a6b5a_78.png)

模块是实现具体算法功能的最小单元。它声明所需的输入字段、输出字段和控制参数。例如，一个SPH密度计算模块会输入粒子位置和邻居信息，输出密度值。

![](img/aaaefbf2efbb53e09751d053216a6b5a_79.png)

![](img/aaaefbf2efbb53e09751d053216a6b5a_81.png)

![](img/aaaefbf2efbb53e09751d053216a6b5a_83.png)

![](img/aaaefbf2efbb53e09751d053216a6b5a_84.png)

### 3. 节点 (Node)

![](img/aaaefbf2efbb53e09751d053216a6b5a_86.png)

![](img/aaaefbf2efbb53e09751d053216a6b5a_88.png)

![](img/aaaefbf2efbb53e09751d053216a6b5a_90.png)

节点是数据（拓扑结构和场）的容器。一个节点包含：
*   **状态字段**：描述物理对象的状态（如位置、速度）。
*   **管线**：组织模块执行顺序的图结构。
*   **节点输入/输出**：允许整个节点作为数据端口进行传递，简化复杂数据流的连接。

![](img/aaaefbf2efbb53e09751d053216a6b5a_92.png)

![](img/aaaefbf2efbb53e09751d053216a6b5a_94.png)

### 4. 场景 (Scene) 与管线 (Pipeline)

![](img/aaaefbf2efbb53e09751d053216a6b5a_96.png)

![](img/aaaefbf2efbb53e09751d053216a6b5a_98.png)

![](img/aaaefbf2efbb53e09751d053216a6b5a_100.png)

![](img/aaaefbf2efbb53e09751d053216a6b5a_102.png)

![](img/aaaefbf2efbb53e09751d053216a6b5a_103.png)

![](img/aaaefbf2efbb53e09751d053216a6b5a_104.png)

![](img/aaaefbf2efbb53e09751d053216a6b5a_106.png)

![](img/aaaefbf2efbb53e09751d053216a6b5a_108.png)

场景是节点的集合。每个节点内部包含两条核心管线：
*   **仿真管线**：由一系列计算模块组成，按依赖关系执行，用于更新物理状态。
*   **渲染管线**：由一系列渲染模块组成，用于将数据可视化。

![](img/aaaefbf2efbb53e09751d053216a6b5a_110.png)

![](img/aaaefbf2efbb53e09751d053216a6b5a_112.png)

![](img/aaaefbf2efbb53e09751d053216a6b5a_113.png)

![](img/aaaefbf2efbb53e09751d053216a6b5a_115.png)

![](img/aaaefbf2efbb53e09751d053216a6b5a_117.png)

管线采用**标记(Tag)机制**：当某个模块的数据被更新后，会打上“已更新”标记。后续模块在执行前会检查输入数据的标记，仅当数据发生变化时才重新计算，避免不必要的计算开销。

![](img/aaaefbf2efbb53e09751d053216a6b5a_119.png)

## 核心设计思想：解耦

四层架构的核心目的是实现三个关键解耦：

![](img/aaaefbf2efbb53e09751d053216a6b5a_121.png)

### 1. 仿真计算与数据解耦
将拓扑结构（如点云、四面体网格）和其上定义的场（如速度场、应力场）与具体的仿真算法分离。同一套数据结构可以支持多种算法（如SPH、MPM），同一种算法也可应用于不同数据结构。

![](img/aaaefbf2efbb53e09751d053216a6b5a_123.png)

![](img/aaaefbf2efbb53e09751d053216a6b5a_125.png)

![](img/aaaefbf2efbb53e09751d053216a6b5a_127.png)

![](img/aaaefbf2efbb53e09751d053216a6b5a_129.png)

### 2. 仿真计算与渲染解耦
渲染管线独立于仿真管线。开发者可以灵活地为调试或展示目的，添加不同的渲染模块（如显示触点、法线、矢量场），而无需修改仿真算法本身。

![](img/aaaefbf2efbb53e09751d053216a6b5a_131.png)

### 3. 仿真计算与交互解耦
交互行为（如鼠标拾取、拖拽）被模块化。不同的交互需求可以通过替换或重载交互模块来实现，保证了交互事件能正确映射到仿真场景的世界坐标系中。

![](img/aaaefbf2efbb53e09751d053216a6b5a_133.png)

![](img/aaaefbf2efbb53e09751d053216a6b5a_135.png)

### 多线程协作
在GUI主线程、仿真线程、渲染线程并存的环境下，需要处理数据同步和读写冲突。PeriDyno的策略是将互斥锁的粒度细化到**模块级别**，而非整个场景。这样在某个模块写入数据时，只锁定该模块，其他模块仍可并行执行，最大程度减少线程阻塞。

![](img/aaaefbf2efbb53e09751d053216a6b5a_137.png)

## 课程总结与展望

![](img/aaaefbf2efbb53e09751d053216a6b5a_139.png)

![](img/aaaefbf2efbb53e09751d053216a6b5a_141.png)

![](img/aaaefbf2efbb53e09751d053216a6b5a_143.png)

![](img/aaaefbf2efbb53e09751d053216a6b5a_145.png)

![](img/aaaefbf2efbb53e09751d053216a6b5a_147.png)

![](img/aaaefbf2efbb53e09751d053216a6b5a_149.png)

本节课我们一起学习了物理仿真的宏观背景、PeriDyno引擎的架构概览、开发环境搭建流程以及其核心的四层模型与解耦设计思想。

![](img/aaaefbf2efbb53e09751d053216a6b5a_151.png)

![](img/aaaefbf2efbb53e09751d053216a6b5a_153.png)

![](img/aaaefbf2efbb53e09751d053216a6b5a_155.png)

![](img/aaaefbf2efbb53e09751d053216a6b5a_157.png)

![](img/aaaefbf2efbb53e09751d053216a6b5a_159.png)

我们了解到，PeriDyno通过**场景-节点-管线-模块**的层级结构和**数据-计算-渲染-交互**的解耦设计，旨在提供一个灵活、可扩展的物理仿真研发平台。它既可以帮助初学者快速上手，也能支持研究人员高效开发并对比新算法。

![](img/aaaefbf2efbb53e09751d053216a6b5a_161.png)

在后续课程中，我们将基于此架构，深入具体的仿真算法实践，例如刚体动力学、SPH流体模拟、近场动力学等，并学习如何开发自定义的渲染与交互模块，最终组合成有趣的应用。