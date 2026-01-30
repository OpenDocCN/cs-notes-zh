![](img/c93999a69e3717f65bb2911756bbe5a1_1.png)

# GAMES106-现代图形绘制流水线原理与实践 - P3：图形绘制流水线的基本原理与实践(二) 🎬

![](img/c93999a69e3717f65bb2911756bbe5a1_3.png)

![](img/c93999a69e3717f65bb2911756bbe5a1_5.png)

在本节课中，我们将继续深入学习 Vulkan 图形绘制流水线，重点探讨 Vulkan 对象的创建、内存管理以及调试工具的使用。课程内容将围绕作业讲解、核心概念解析和实践演示展开。

![](img/c93999a69e3717f65bb2911756bbe5a1_7.png)

![](img/c93999a69e3717f65bb2911756bbe5a1_9.png)

---

![](img/c93999a69e3717f65bb2911756bbe5a1_11.png)

![](img/c93999a69e3717f65bb2911756bbe5a1_13.png)

## 课程回顾与作业讲解 📋

![](img/c93999a69e3717f65bb2911756bbe5a1_15.png)

![](img/c93999a69e3717f65bb2911756bbe5a1_17.png)

上一节我们介绍了 Vulkan 的基础架构和绘制流程。本节中，我们首先回顾课程安排并详细讲解第一次作业的要求。

课程安排如下：
*   第一课时：讲解 Vulkan 基础架构和绘制流程。
*   第二课时（本节）：讲解 Vulkan 对象创建、内存管理以及调试方法和工具。
*   第三课时（下周三）：讲解 Vulkan 多线程同步以及基于移动端的常见优化和实践。

![](img/c93999a69e3717f65bb2911756bbe5a1_19.png)

![](img/c93999a69e3717f65bb2911756bbe5a1_21.png)

![](img/c93999a69e3717f65bb2911756bbe5a1_23.png)

以下是关于第一次作业的详细说明。

![](img/c93999a69e3717f65bb2911756bbe5a1_25.png)

![](img/c93999a69e3717f65bb2911756bbe5a1_26.png)

### 作业框架与模型

![](img/c93999a69e3717f65bb2911756bbe5a1_28.png)

![](img/c93999a69e3717f65bb2911756bbe5a1_30.png)

作业基于提供的代码框架完成。在下载代码仓库时，请使用 `git submodule update` 命令同步拉取所有第三方库。

![](img/c93999a69e3717f65bb2911756bbe5a1_32.png)

![](img/c93999a69e3717f65bb2911756bbe5a1_34.png)

![](img/c93999a69e3717f65bb2911756bbe5a1_36.png)

作业需要使用一个特定的模型文件。请将该文件下载并解压到项目的 `data` 文件夹中。该模型是一个带有骨骼动画的模型。

### 作业要求

当前作业框架（Homework 1）仅能加载静态的 glTF 模型，且材质处理简单（仅颜色），光照实现不完整（仅一个方向光）。本次作业需要在此基础上进行改进，具体要求如下：

1.  **支持 glTF 骨骼动画**：正确读取并播放模型中的骨骼动画。
2.  **支持 glTF PBR 材质**：完整实现模型的 PBR 材质渲染，包括法线贴图、自发光贴图等。
3.  **进阶要求（额外通道）**：实现一个色调映射（Tonemap）函数。**关键点**：必须通过增加一个额外的渲染通道（Render Pass）来实现该函数，**不能**直接将其写在片元着色器（Fragment Shader）的末尾。函数形式如下：
    ```cpp
    // 输入一个颜色，输出映射后的颜色
    vec3 tonemap(vec3 color) { ... }
    ```

**重要提示**：作业必须在提供的 `homework1` 框架基础上修改，不要提交其他框架的代码。

### 参考资料与示例

为了帮助大家完成作业，框架中提供了多个示例代码，可以通过取消注释 `setupWorkingExample` 函数中的相应行来启用和运行：
*   `gltf_skin`：演示如何读取 glTF 骨骼动画。
*   `pbr_base`：演示基于方向光的 PBR 实现。
*   `example_pbr_ibl`：演示基于环境光的 PBR 实现。

关于 glTF 格式中骨骼和材质的详细描述，可以参考 glTF 官方文档。

---

![](img/c93999a69e3717f65bb2911756bbe5a1_38.png)

## Vulkan 对象创建 🏗️

![](img/c93999a69e3717f65bb2911756bbe5a1_40.png)

上一节我们概述了完整的渲染管线。本节中，我们来看看管线每个阶段所对应的 Vulkan 对象及其创建方法。

Vulkan 绘制管线中涉及的主要对象包括：
*   **Buffer** 和 **Image**：用于存储顶点、索引、 uniform 数据和纹理。
*   **Pipeline**：定义整个图形绘制管线的状态和着色器。
*   **Descriptor Set**：用于向管线传递 uniform 变量等资源。

### 对象创建通用模式

![](img/c93999a69e3717f65bb2911756bbe5a1_42.png)

Vulkan 创建对象的函数遵循统一的模式：`vkCreate[Object]`。例如，创建缓冲区的函数是 `vkCreateBuffer`。

该模式通常包含以下参数：
1.  `VkDevice`：逻辑设备。
2.  描述要创建对象的结构体（例如 `VkBufferCreateInfo`）。
3.  自定义内存分配器（通常可传 `nullptr` 使用默认分配器）。
4.  返回创建对象句柄的指针。

所有 Vulkan 函数都通过返回 `VkResult` 来指示操作成功或错误类型。

### 创建 Buffer 的流程

![](img/c93999a69e3717f65bb2911756bbe5a1_44.png)

以下是创建一个 Uniform Buffer 的典型步骤，创建 Image 的流程与此类似：

![](img/c93999a69e3717f65bb2911756bbe5a1_46.png)

1.  **创建 Buffer 对象**：使用 `vkCreateBuffer`，并通过 `VkBufferCreateInfo` 指定其用途（如 `VK_BUFFER_USAGE_UNIFORM_BUFFER_BIT`）和大小。
2.  **查询内存需求**：使用 `vkGetBufferMemoryRequirements` 获取该 Buffer 实际需要的内存大小和对齐要求。这里查询的大小可能与申请时指定的大小不同，因为驱动可能出于优化目的进行内存对齐。
3.  **分配内存**：使用 `vkAllocateMemory` 分配一块符合要求的内存。需要根据内存用途（CPU可见、GPU本地等）指定正确的内存类型。
4.  **绑定内存与 Buffer**：使用 `vkBindBufferMemory` 将分配的内存与创建的 Buffer 对象绑定起来，`offset` 参数通常为 0。

**关键点**：Vulkan 允许开发者自定义内存分配器来管理 CPU 端的内存分配。而 GPU 内存的分配和管理，Vulkan 也提供了一套机制，我们将在内存管理部分详细讨论。

![](img/c93999a69e3717f65bb2911756bbe5a1_48.png)

---

## Render Pass 与 Framebuffer 🖼️

在配置好绘制所需的数据后，我们需要定义绘制的目标（输出到哪里）以及绘制过程中的状态。这就是 Render Pass 和 Framebuffer 的作用。

### Render Pass

![](img/c93999a69e3717f65bb2911756bbe5a1_50.png)

Render Pass 对象描述了单个渲染过程中涉及的附件（Attachment）、子通道（Subpass）以及它们之间的依赖关系。

它主要定义两部分：
1.  **附件描述（Attachment Description）**：定义输出目标（如颜色附件、深度附件）的格式、在渲染开始和结束时的操作（如清除、存储）以及内存布局（Layout）。
2.  **子通道描述（Subpass Description）**：定义该子通道引用哪些附件作为输入/输出，以及多个子通道之间的依赖关系。

在代码框架的 `setupRenderPass` 函数中，我们定义了两个附件（颜色附件和深度附件），并设置它们在渲染前执行清除操作（`loadOp = VK_ATTACHMENT_LOAD_OP_CLEAR`），在渲染后存储结果（`storeOp = VK_ATTACHMENT_STORE_OP_STORE`）。同时，也定义了这些附件在进入和离开 Render Pass 时的布局状态。

![](img/c93999a69e3717f65bb2911756bbe5a1_52.png)

![](img/c93999a69e3717f65bb2911756bbe5a1_54.png)

**关于 Layout 的理解**：`VkImageLayout` 表示图像在不同用途下的内存布局状态。对于初学者，可以将其简单理解为图像的一种“使用状态”，例如“作为颜色附件”、“作为被采样的纹理”、“作为拷贝源”等。以状态机的方式理解比记忆具体布局更容易。

![](img/c93999a69e3717f65bb2911756bbe5a1_56.png)

### Framebuffer

如果说 Render Pass 定义了渲染过程的“模板”或“流程”，那么 Framebuffer 就是根据这个模板，指定本次渲染具体使用哪些图像视图（Image View）作为附件。

![](img/c93999a69e3717f65bb2911756bbe5a1_58.png)

在代码的 `setupFramebuffers` 函数中，我们为交换链（Swapchain）中的每一个图像都创建了一个 Framebuffer。每个 Framebuffer 都绑定了对应的交换链图像视图作为颜色附件，以及一个公共的深度图像视图作为深度附件。

![](img/c93999a69e3717f65bb2911756bbe5a1_60.png)

![](img/c93999a69e3717f65bb2911756bbe5a1_62.png)

---

![](img/c93999a69e3717f65bb2911756bbe5a1_64.png)

## Pipeline 与管线布局 ⚙️

定义了渲染目标和流程后，我们需要创建最重要的对象之一：图形管线（Graphics Pipeline）。它定义了从顶点输入到最终颜色输出的完整处理过程。

### Pipeline 创建

创建 Pipeline 需要填充一个庞大的 `VkGraphicsPipelineCreateInfo` 结构体，它包含了管线所有阶段的状态：
*   **顶点输入状态**：定义顶点数据的格式和绑定方式。
*   **着色器阶段**：指定编译好的顶点着色器和片元着色器模块。
*   **视口与裁剪状态**：定义输出图像的区域和裁剪规则。
*   **光栅化状态**：定义多边形填充模式、是否剔除背面等。
*   **多重采样状态**：定义抗锯齿相关设置。
*   **深度与模板测试状态**。
*   **颜色混合状态**：定义多个颜色附件如何混合。
*   **动态状态**：定义哪些状态可以在绘制时动态修改（如视口大小）。
*   **管线布局**：定义描述符集（Descriptor Set）和推送常量（Push Constant）的布局。
*   **Render Pass**：指定该管线所兼容的 Render Pass。

![](img/c93999a69e3717f65bb2911756bbe5a1_66.png)

在作业框架中，`createPipeline` 函数详细展示了如何设置这些状态。例如，它定义了顶点数据的四个属性（位置、法线、UV、颜色），并绑定了对应的着色器。

![](img/c93999a69e3717f65bb2911756bbe5a1_68.png)

![](img/c93999a69e3717f65bb2911756bbe5a1_70.png)

### 着色器编译

Vulkan 使用 SPIR-V 字节码格式的着色器。我们可以使用 Vulkan SDK 中的工具（如 `dxc` 或 `glslangValidator`）将高级着色语言（HLSL/GLSL）编译为 SPIR-V。

例如，使用 `dxc` 编译一个 HLSL 片元着色器的命令可能如下：
```bash
dxc -T ps_6_0 -E main -spirv -fspv-target-env=vulkan1.2 Shader.hlsl -Fo Shader.frag.spv
```
作业提交时，请记得附上你编译好的着色器文件。

![](img/c93999a69e3717f65bb2911756bbe5a1_72.png)

![](img/c93999a69e3717f65bb2911756bbe5a1_73.png)

![](img/c93999a69e3717f65bb2911756bbe5a1_75.png)

### 管线布局与描述符集

管线布局（Pipeline Layout）定义了着色器可以访问哪些资源，以及这些资源的组织方式。资源通过描述符集（Descriptor Set）进行分组和绑定。

描述符集就像一个资源表，表中的每个条目（描述符）可以是一个 Uniform Buffer、一个纹理采样器或一个存储图像等。将资源分组到不同的描述符集有利于高效更新。

在作业框架的着色器中：
*   绑定到 `set = 0, binding = 0` 的是场景级的 Uniform Buffer（包含相机矩阵、灯光等），所有模型共享。
*   绑定到 `set = 1, binding = 0` 的是材质级的 Uniform Buffer 和纹理，每个材质独有。

在绘制代码中，我们先绑定 `set = 0` 的描述符集（场景数据），然后在绘制每个模型或子网格时，再绑定其对应的 `set = 1` 描述符集（材质数据）。这种分离使得全局数据和频繁变化的数据可以独立、高效地更新。

---

![](img/c93999a69e3717f65bb2911756bbe5a1_77.png)

![](img/c93999a69e3717f65bb2911756bbe5a1_79.png)

## Vulkan 内存管理 💾

![](img/c93999a69e3717f65bb2911756bbe5a1_81.png)

Vulkan 赋予了开发者精细控制内存的能力，理解内存类型和属性对于性能优化至关重要。

### 内存架构与类型

在典型的台式机架构中，CPU 和 GPU 拥有各自独立的内存，通过 PCIe 总线连接。Vulkan 内存根据其属性主要分为几种类型，可以通过 `vkGetPhysicalDeviceMemoryProperties` 查询：

1.  **DEVICE_LOCAL**：GPU 本地内存，GPU 访问速度最快，CPU 通常不能直接访问。适合存储频繁被 GPU 读写的数据，如帧缓冲、深度缓冲。
2.  **HOST_VISIBLE**：CPU 可见内存，CPU 可以映射（map）并读写。适合用于需要从 CPU 频繁更新的数据，如每帧变化的 Uniform Buffer。
3.  **HOST_COHERENT**：保证 CPU 和 GPU 对该内存的写入相互立即可见，无需手动刷新缓存。通常与 `HOST_VISIBLE` 一起使用。
4.  **HOST_CACHED**：CPU 端缓存该内存，适合 CPU 需要频繁读取的数据（如回读渲染结果）。

**注意**：在集成显卡或移动 SoC 上，CPU 和 GPU 可能共享物理内存，情况会有所不同。

### 内存分配策略

直接使用 Vulkan 原生接口管理内存非常复杂。AMD 提供了一个开源库 **Vulkan Memory Allocator (VMA)**，它极大地简化了内存管理。

VMA 将内存用途抽象为更易理解的类型，例如：
*   `VMA_MEMORY_USAGE_GPU_ONLY`：仅 GPU 使用，如纹理、静态顶点缓冲。
*   `VMA_MEMORY_USAGE_CPU_TO_GPU`：从 CPU 上传到 GPU，如每帧更新的 Uniform Buffer。
*   `VMA_MEMORY_USAGE_CPU_ONLY`：暂存内存（Staging Buffer），用于高效的 CPU 到 GPU 数据传输。

### 高效数据上传：Staging Buffer

![](img/c93999a69e3717f65bb2911756bbe5a1_83.png)

对于需要每帧从 CPU 更新到 GPU 的数据（如 Uniform Buffer），一个高效的策略是使用 **Staging Buffer**。

![](img/c93999a69e3717f65bb2911756bbe5a1_85.png)

工作流程如下：
1.  创建一块 `HOST_VISIBLE` 且 `HOST_COHERENT` 的内存作为 Staging Buffer。
2.  CPU 将数据写入 Staging Buffer（通过 `vkMapMemory`/`vkUnmapMemory`）。
3.  在命令缓冲区中，记录一个从 Staging Buffer 拷贝到最终 GPU Buffer 的命令（`vkCmdCopyBuffer`）。
4.  提交命令缓冲区执行。

**优势**：
*   **减少同步**：拷贝操作在 GPU 命令流中，与渲染有序进行，避免了 CPU 直接写入 GPU 内存可能需要的显式同步。
*   **提高性能**：Staging Buffer 通常位于一块 CPU 和 GPU 都能高效访问的特殊内存区域。
*   **简化逻辑**：避免了在 GPU 使用资源时，CPU 误写入导致的数据竞争问题。

作业框架中更新 Uniform Buffer 使用的是简单的 `map/unmap` 方式。作为练习，大家可以尝试将其改造为使用 Staging Buffer 的方式。

---

![](img/c93999a69e3717f65bb2911756bbe5a1_87.png)

![](img/c93999a69e3717f65bb2911756bbe5a1_89.png)

## Vulkan 绘制命令记录 🖌️

![](img/c93999a69e3717f65bb2911756bbe5a1_91.png)

Vulkan 的绘制是异步的。CPU 将绘制命令记录到命令缓冲区（Command Buffer）中，然后提交给 GPU 的队列执行。

### 命令记录流程

一个基本的绘制命令序列如下：
1.  `vkBeginCommandBuffer`：开始记录命令。
2.  `vkCmdBeginRenderPass`：开始一个 Render Pass，定义渲染目标和作用域。
3.  设置视口和裁剪矩形（`vkCmdSetViewport`, `vkCmdSetScissor`）。
4.  绑定图形管线（`vkCmdBindPipeline`）。
5.  绑定顶点缓冲区和索引缓冲区（`vkCmdBindVertexBuffers`, `vkCmdBindIndexBuffer`）。
6.  绑定描述符集（`vkCmdBindDescriptorSets`）。
7.  记录绘制命令（`vkCmdDraw` 或 `vkCmdDrawIndexed`）。
8.  `vkCmdEndRenderPass`：结束 Render Pass。
9.  `vkEndCommandBuffer`：结束命令记录。

![](img/c93999a69e3717f65bb2911756bbe5a1_93.png)

![](img/c93999a69e3717f65bb2911756bbe5a1_95.png)

在作业框架的 `buildCommandBuffers` 函数中，我们可以看到这个流程的具体实现。它绑定了场景的全局描述符集（`set = 0`），然后遍历 glTF 模型的节点和网格，为每个材质绑定其独有的描述符集（`set = 1`），并推送模型矩阵（使用 Push Constant），最后发起绘制调用。

### 命令缓冲区的重用

![](img/c93999a69e3717f65bb2911756bbe5a1_97.png)

Vulkan 的一个高效特性是命令缓冲区可以重用。在作业框架中，命令缓冲区在初始化时创建并记录一次。在后续每帧渲染时，只要绘制内容没有变化，就直接提交已记录好的命令缓冲区，无需 CPU 再次介入记录。这显著降低了 CPU 开销，使其能专注于逻辑、模拟等任务。

![](img/c93999a69e3717f65bb2911756bbe5a1_99.png)

![](img/c93999a69e3717f65bb2911756bbe5a1_101.png)

---

![](img/c93999a69e3717f65bb2911756bbe5a1_103.png)

![](img/c93999a69e3717f65bb2911756bbe5a1_105.png)

![](img/c93999a69e3717f65bb2911756bbe5a1_107.png)

## 调试工具与方法 🔧

![](img/c93999a69e3717f65bb2911756bbe5a1_109.png)

![](img/c93999a69e3717f65bb2911756bbe5a1_111.png)

最后，我们来介绍一些强大的 Vulkan 调试和性能分析工具。

![](img/c93999a69e3717f65bb2911756bbe5a1_113.png)

![](img/c93999a69e3717f65bb2911756bbe5a1_115.png)

### 1. RenderDoc

RenderDoc 是一个功能强大的图形调试器，支持 Vulkan。

**主要功能**：
*   **抓帧分析**：捕获某一帧或连续几帧的所有 GPU 命令。
*   **资源检查**：查看任意时刻的缓冲区、纹理内容。
*   **管线状态调试**：查看绘制调用时管线各个阶段的状态、绑定的资源、着色器代码。
*   **动态着色器编辑**：支持在调试器中直接修改着色器代码并实时查看效果，无需重新编译程序。这对于调试着色器逻辑非常方便。

![](img/c93999a69e3717f65bb2911756bbe5a1_117.png)

![](img/c93999a69e3717f65bb2911756bbe5a1_119.png)

![](img/c93999a69e3717f65bb2911756bbe5a1_121.png)

**局限性**：其性能分析（Profiling）功能可能不够精确。

![](img/c93999a69e3717f65bb2911756bbe5a1_123.png)

![](img/c93999a69e3717f65bb2911756bbe5a1_125.png)

![](img/c93999a69e3717f65bb2911756bbe5a1_126.png)

### 2. NVIDIA Nsight Graphics

![](img/c93999a69e3717f65bb2911756bbe5a1_128.png)

![](img/c93999a69e3717f65bb2911756bbe5a1_130.png)

对于 NVIDIA 显卡用户，Nsight Graphics 是性能分析和调试的利器。

![](img/c93999a69e3717f65bb2911756bbe5a1_132.png)

**主要功能**：
*   **精确的性能分析**：提供以微秒为单位的 GPU 时间线分析，能准确找到性能瓶颈。
*   **帧调试**：类似 RenderDoc 的抓帧和状态检查功能。
*   **着色器性能分析**：可以对特定的着色器进行底层性能分析和统计。

![](img/c93999a69e3717f65bb2911756bbe5a1_134.png)

### 3. 其他平台工具
*   **高通 Snapdragon Profiler**：用于在高通设备上进行图形性能分析。
*   **Arm Mobile Studio**：包含 Graphics Analyzer 和 Performance Analyzer，适用于 Arm Mali GPU 的设备。

![](img/c93999a69e3717f65bb2911756bbe5a1_136.png)

![](img/c93999a69e3717f65bb2911756bbe5a1_138.png)

---

![](img/c93999a69e3717f65bb2911756bbe5a1_140.png)

## 总结 🎯

![](img/c93999a69e3717f65bb2911756bbe5a1_142.png)

![](img/c93999a69e3717f65bb2911756bbe5a1_144.png)

本节课我们一起深入学习了 Vulkan 图形绘制流水线的核心实践部分：

![](img/c93999a69e3717f65bb2911756bbe5a1_146.png)

![](img/c93999a69e3717f65bb2911756bbe5a1_148.png)

1.  **作业详解**：明确了第一次作业的目标——实现 glTF 模型的骨骼动画、PBR 材质渲染，并通过额外通道实现色调映射。
2.  **对象创建**：学习了 Vulkan 创建 Buffer、Image、Pipeline 等核心对象的通用模式和具体步骤。
3.  **流程定义**：理解了 Render Pass 和 Framebuffer 如何定义渲染目标和流程。
4.  **内存管理**：探讨了 Vulkan 复杂的内存类型系统，并介绍了使用 VMA 库和 Staging Buffer 策略来简化管理并提升数据上传效率。
5.  **命令记录**：掌握了 Vulkan 异步绘制命令的记录、提交和重用机制。
6.  **调试工具**：了解了 RenderDoc 和 NVIDIA Nsight Graphics 等强大工具，用于调试渲染错误和分析性能瓶颈。

![](img/c93999a69e3717f65bb2911756bbe5a1_150.png)

![](img/c93999a69e3717f65bb2911756bbe5a1_152.png)

![](img/c93999a69e3717f65bb2911756bbe5a1_154.png)

通过本课的学习，你应该对如何使用 Vulkan 组织一次完整的绘制有了更清晰的认识。下节课我们将探讨 Vulkan 的多线程同步机制以及在移动平台上的优化实践。