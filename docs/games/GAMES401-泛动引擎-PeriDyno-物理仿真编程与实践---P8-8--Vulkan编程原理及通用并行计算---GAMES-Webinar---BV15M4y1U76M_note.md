![](img/2b41ed1fb0d8c4ed3a6198eba0898af1_0.png)

# GAMES401-泛动引擎(PeriDyno)物理仿真编程与实践 - P8：Vulkan编程原理及通用并行计算 🚀

## 概述

在本节课中，我们将学习Vulkan编程的基本原理及其在通用并行计算中的应用。课程将首先介绍Vulkan API的概况和通用并行计算的概念，然后通过一个具体的例子展示如何使用Vulkan编写并行计算程序。由于直接使用原始Vulkan API较为复杂，我们还将探讨如何通过封装来降低编程复杂度，并介绍Vulkan后端如何与PeriDyno框架集成。最后，我们会分享一些前期探索中发现的问题，并展示简单的案例。

## Vulkan简介与通用并行计算概念

上一节我们概述了课程内容，本节中我们来看看Vulkan是什么以及通用并行计算的基本概念。

Vulkan最早于2015年的GDC上被提出，并于2016年正式发布。其设计初衷是整合渲染与仿真计算，使用统一的API来处理这两大核心任务，被誉为下一代图形接口，旨在未来替代OpenGL。Vulkan因其更靠近底层硬件，能够提供更高的性能和更直接的GPU控制能力，但同时也带来了更高的编程复杂度。

GPU API的发展伴随着GPU硬件的进步。早期的OpenGL（1992年）主要用于固定功能管线的三维场景处理，不具备可编程能力。随后，微软推出了DirectX，形成了独立于OpenGL的标准。随着可编程需求的增长，DirectX 9引入了HLSL着色语言，OpenGL也引入了GLSL，使得顶点着色器等特定阶段具备了可编程能力。

为了兼顾移动设备，OpenGL ES作为OpenGL的子集被发展出来。然而，早期的图形API主要面向渲染，用其编写复杂的仿真算法代价高昂。2007年CUDA的提出是一个里程碑，它重新定义了GPU的用途，使其能够处理任何与渲染无关的通用计算任务。2009年，为了建立行业标准，提出了专门针对通用并行计算的OpenCL。2014年，Apple推出了旨在融合图形与计算的Metal API。最终，在2016年，旨在统一渲染与计算、并由开源组织维护的Vulkan正式发布。

Vulkan相比其他API更底层，它将更多硬件特性暴露给开发者，这带来了潜在的性能提升，但也显著提高了对开发者的要求和编程的复杂度。

## 并行计算API的选择考量

在了解了Vulkan的由来后，我们需要思考如何为并行计算任务选择合适的API。以下是CUDA、OpenCL和Vulkan在一些关键方面的对比：

*   **混合编译支持**：CUDA支持设备端代码与主机端C++代码在同一文件中编译，简化了开发。OpenCL和Vulkan目前不支持，需要维护分离的代码，增加了维护成本。
*   **调试工具**：复杂的仿真算法需要强大的调试工具支持。目前三者都支持，但CUDA的工具链可能更成熟易用。
*   **跨平台能力**：CUDA严重依赖NVIDIA硬件，跨平台能力弱。OpenCL和Vulkan的跨平台能力更好，其中Vulkan在PC端和移动端的兼容性最广。
*   **C++支持**：仿真算法逻辑复杂，C++的面向对象封装能极大降低代码复杂度。CUDA和OpenCL支持C/C++，而Vulkan目前主要支持C，需要退回到C的编程规范，且不支持模板等高级特性。

选择时需结合自身需求：若进行特定研究，CUDA最为方便；若需考虑移动端或跨平台，则Vulkan是更好的选择。

## 使用原始Vulkan API编写并行计算程序

上一节我们讨论了如何选择API，本节我们将尝试使用最原始的Vulkan API来编写一个简单的并行计算程序，以此感受其复杂性。

![](img/2b41ed1fb0d8c4ed3a6198eba0898af1_2.png)

我们的任务是实现两个数组A和B的求和，并将结果存入数组C。用CUDA实现这个任务对初学者来说可能只需几小时，但用原始Vulkan API实现则困难得多。

![](img/2b41ed1fb0d8c4ed3a6198eba0898af1_4.png)

Vulkan的执行流程包含多个对象和步骤：
1.  **创建Instance**：应用程序的顶层实例。
2.  **选择Physical Device**：选择执行计算的物理显卡。
3.  **创建Logical Device**：在物理设备上创建逻辑设备，用于实际执行。
4.  **获取队列**：逻辑设备包含图形队列、计算队列和传输队列。计算任务主要使用计算队列。
5.  **分配内存与Buffer**：在GPU上分配数据存储空间。Vulkan的数据传递通常需要通过一个称为“暂存缓冲区”的中转区域。
6.  **准备计算着色器**：编写计算内核代码，例如使用GLSL，并编译成SPIR-V中间字节码。
7.  **创建管线与描述符集**：创建计算管线，并通过描述符集来绑定管线执行所需的具体数据Buffer。
8.  **记录与提交命令**：在命令池中创建命令缓冲区，记录绑定管线、描述符集、分派计算任务等命令，最后将命令缓冲区提交到队列中执行。

即使对于这样一个简单的数组相加任务，使用原始Vulkan API编写的代码也可能长达数百行，且极易出错，调试困难。

## 降低Vulkan编程复杂度：Catalina封装

![](img/2b41ed1fb0d8c4ed3a6198eba0898af1_6.png)

面对如此高的复杂度，我们需要寻找方法来简化Vulkan在仿真计算中的使用。PeriDyno框架中集成了一个名为Catalina的Vulkan后端，它通过封装来隐藏底层细节。

![](img/2b41ed1fb0d8c4ed3a6198eba0898af1_8.png)

Catalina主要引入了以下几个核心结构进行抽象：
*   **VkSystem**：管理Instance、物理设备选择等全局初始化。
*   **VkContext**：管理逻辑设备及其队列。
*   **VkProgram**：对标CUDA的Kernel函数，用于执行计算任务。
*   **VkVariable**：数据抽象基类，其子类包括：
    *   `VkDeviceBuffer`: 用于分配大的缓存。
    *   `VkUniform`: 用于数据量小且易变的参数。
    *   `VkConstant`: 用于基本不变的常量。

通过这种封装，编写一个Vulkan计算任务的流程被大大简化。例如，实现数组相加的`VkProgram`声明和调用代码如下所示：

```cpp
// 声明一个VkProgram (对标CUDA kernel)
VK_PROGRAM_BEGIN(ArrayAdd) // 类似 CUDA 的 __global__ 声明
    // 定义输入参数，类似CUDA kernel的参数列表
    VK_PARAM(VK_INOUT_BUFFER, float, a);
    VK_PARAM(VK_IN_BUFFER, float, b);
    VK_PARAM(VK_CONSTANT, int, n);
VK_PROGRAM_END

// 调用VkProgram
ArrayAdd->flush(128, n/128, a, b, n); // 类似CUDA的kernel调用<<<...>>>
```

![](img/2b41ed1fb0d8c4ed3a6198eba0898af1_10.png)

这种封装使得主机端代码量从数百行减少到数十行，显著降低了研发成本。此外，Catalina还支持`VkMultiProgram`将多个Kernel组合记录到同一个命令缓冲区中执行，以优化需要频繁切换Kernel的仿真循环性能。

![](img/2b41ed1fb0d8c4ed3a6198eba0898af1_12.png)

![](img/2b41ed1fb0d8c4ed3a6198eba0898af1_14.png)

## Vulkan后端与PeriDyno框架的集成

![](img/2b41ed1fb0d8c4ed3a6198eba0898af1_16.png)

![](img/2b41ed1fb0d8c4ed3a6198eba0898af1_18.png)

为了保持引擎框架与GPU后端的无关性，PeriDyno在架构上进行了调整。核心思路是引入中间层来屏蔽底层细节。

![](img/2b41ed1fb0d8c4ed3a6198eba0898af1_20.png)

![](img/2b41ed1fb0d8c4ed3a6198eba0898af1_22.png)

![](img/2b41ed1fb0d8c4ed3a6198eba0898af1_24.png)

在计算层面，框架识别的是如`Field`、`Array`等抽象数据结构，并不关心其由CUDA还是Vulkan分配。因此，在具体后端与引擎框架之间，通过`VArray`等中间数据结构提供统一接口，从而避免因接入新后端而调整引擎架构。

在渲染层面，思路类似。渲染引擎`JawEngine`并不直接与Vulkan或CUDA后端交互，而是通过一个`GPUBackend`中间层，这使得未来集成其他渲染库（如VTK、Unreal）成为可能。

这种解耦设计使得拓展新的计算或渲染后端变得更加方便。

![](img/2b41ed1fb0d8c4ed3a6198eba0898af1_26.png)

## Vulkan用于仿真计算的挑战与注意事项

![](img/2b41ed1fb0d8c4ed3a6198eba0898af1_28.png)

![](img/2b41ed1fb0d8c4ed3a6198eba0898af1_30.png)

尽管Vulkan能力强大，但在用于仿真计算研发时，仍面临一些挑战：

1.  **数据对齐问题**：Vulkan需要开发者显式处理数据结构的字节对齐（通常是16字节），而CUDA编译器会自动处理。对齐不当会导致数据错误。
2.  **代码重复与维护**：由于不支持混合编译，CPU和GPU端需要分别定义相同的数据结构，任何一端的修改都需同步到另一端，容易出错且维护成本高。
3.  **特性支持限制**：Vulkan目前不支持C++、模板，且部分硬件对`float`原子操作支持不佳，这对流体等仿真至关重要。
4.  **厂商实现差异**：不同硬件厂商对Vulkan特性的支持千差万别，为实现真正的跨平台，仍需做大量适配和优化工作。
5.  **性能与易用性权衡**：Vulkan更底层，在计算密集度足够高时性能优于CUDA。但对于小规模计算或快速原型开发，其复杂的编程模型可能抵消性能优势。

![](img/2b41ed1fb0d8c4ed3a6198eba0898af1_32.png)

![](img/2b41ed1fb0d8c4ed3a6198eba0898af1_34.png)

![](img/2b41ed1fb0d8c4ed3a6198eba0898af1_36.png)

因此，Vulkan目前更适合用于对性能有极致要求、且计算规模较大的个别计算步骤的加速，而非快速开发复杂的仿真系统。

![](img/2b41ed1fb0d8c4ed3a6198eba0898af1_38.png)

![](img/2b41ed1fb0d8c4ed3a6198eba0898af1_40.png)

![](img/2b41ed1fb0d8c4ed3a6198eba0898af1_42.png)

## 案例展示与总结

![](img/2b41ed1fb0d8c4ed3a6198eba0898af1_44.png)

![](img/2b41ed1fb0d8c4ed3a6198eba0898af1_46.png)

![](img/2b41ed1fb0d8c4ed3a6198eba0898af1_48.png)

![](img/2b41ed1fb0d8c4ed3a6198eba0898af1_50.png)

![](img/2b41ed1fb0d8c4ed3a6198eba0898af1_52.png)

![](img/2b41ed1fb0d8c4ed3a6198eba0898af1_54.png)

![](img/2b41ed1fb0d8c4ed3a6198eba0898af1_56.png)

![](img/2b41ed1fb0d8c4ed3a6198eba0898af1_58.png)

最后，我们通过一个简单的粒子发射与流动的案例，演示了Vulkan后端与PeriDyno蓝图系统的协同工作。该案例验证了从后端对接到引擎蓝图集成的整个流程是可行的。此外，PeriDyno中也提供了基于Vulkan的点、线、面基本渲染模块，以及一些未开源的尝试性案例（如刚体、浅水波、弹性体），证明了Vulkan能够完成多种物理仿真任务，只是研发代价不同。

![](img/2b41ed1fb0d8c4ed3a6198eba0898af1_60.png)

![](img/2b41ed1fb0d8c4ed3a6198eba0898af1_62.png)

**总结**
本节课我们一起学习了Vulkan API的基本原理及其在通用并行计算中的应用。我们了解了Vulkan的设计目标与复杂之处，探讨了如何通过封装来降低其编程复杂度，并介绍了其与PeriDyno框架的集成方式。同时，我们也认识到将Vulkan用于复杂仿真系统研发目前仍面临数据对齐、代码维护、特性支持等多方面的挑战。对于初学者，建议仍以CUDA作为并行计算入门工具，而将Vulkan作为性能优化和跨平台部署时的进阶选择。