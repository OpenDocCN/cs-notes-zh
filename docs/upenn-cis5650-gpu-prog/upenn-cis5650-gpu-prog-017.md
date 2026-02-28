# 017：Vulkan实验一与高斯溅射项目介绍

![](img/3a23afc523800bfaacb053f8b5862fcf_0.png)

![](img/3a23afc523800bfaacb053f8b5862fcf_2.png)

![](img/3a23afc523800bfaacb053f8b5862fcf_3.png)

![](img/3a23afc523800bfaacb053f8b5862fcf_5.png)

![](img/3a23afc523800bfaacb053f8b5862fcf_7.png)

在本节课中，我们将学习两个核心内容。首先，我们会介绍课程项目五——基于WebGPU的高斯溅射渲染。其次，我们将开始Vulkan图形API的实验课程第一部分，学习其初始化、资源创建和管线设置等基础知识。

![](img/3a23afc523800bfaacb053f8b5862fcf_9.png)

![](img/3a23afc523800bfaacb053f8b5862fcf_10.png)

---

## 🎯 项目五：3D高斯溅射渲染概述

上一节我们介绍了本节课的整体安排，本节中我们来看看项目五的具体内容。3D高斯溅射是一种不同于传统三角形渲染的点云渲染技术。

**核心思想**：该技术源于统计学中的高斯分布。我们不是渲染三角形，而是渲染一系列点（称为“溅射”）。每个点周围有一个类似高斯分布的区域，具有颜色变化等属性，然后将所有点的颜色混合在一起形成最终图像。

**数学基础**：在3D空间中，一个高斯分布由均值（点的中心位置）和协方差矩阵定义。协方差矩阵描述了数据点相对于中心点的变化程度，在渲染中即表示颜色等属性围绕中心点的变化范围。

**协方差变换**：我们可以像在常规图形管线中一样，通过旋转矩阵和缩放矩阵来变换协方差，从而改变高斯分布的形状。

**项目流程**：在实际论文中，该技术需要从不同相机角度训练场景并采样点云。但在我们的项目中，我们只关注渲染部分。我们将使用预训练的场景、相机文件和点云文件。

![](img/3a23afc523800bfaacb053f8b5862fcf_12.png)

![](img/3a23afc523800bfaacb053f8b5862fcf_13.png)

![](img/3a23afc523800bfaacb053f8b5862fcf_15.png)

![](img/3a23afc523800bfaacb053f8b5862fcf_17.png)

![](img/3a23afc523800bfaacb053f8b5862fcf_19.png)

以下是渲染管线的核心步骤：
1.  **加载数据**：加载提供的3D高斯数据。
2.  **预处理**：将3D高斯数据投影到2D屏幕空间。这包括视锥体裁剪、计算3D协方差矩阵并将其投影到2D、评估球谐函数获取颜色，以及根据深度对溅射点进行排序（因为我们需要像处理透明纹理一样从后向前渲染）。
3.  **渲染**：将每个高斯溅射视为一个面向视图方向的四边形实例进行渲染。在片段着色器中，根据2D高斯方程计算颜色和不透明度，然后混合所有颜色。

![](img/3a23afc523800bfaacb053f8b5862fcf_21.png)

![](img/3a23afc523800bfaacb053f8b5862fcf_23.png)

**2D投影公式**：3D协方差到2D的投影类似于我们为三角形渲染所做的MVP变换，公式涉及视图变换矩阵和雅可比矩阵：
`Σ' = J * W * Σ * W^T * J^T`
其中，`Σ`是3D协方差矩阵，`W`是视图变换矩阵，`J`是投影的雅可比矩阵。

**颜色计算**：在片段着色器中，我们使用2D二次方程来计算不透明度。颜色从中心呈指数衰减，中心点的颜色系数由球谐函数得出。

**项目代码结构**：主要需要实现 `GaussianRenderer` 和相关的计算着色器（预处理）与渲染着色器。`PointCloudRenderer` 已基本实现，用于辅助调试。

**注意事项**：
*   数据传输到GPU时使用半精度浮点数以节省带宽。
*   在GPU预处理阶段，需要使用原子操作来更新实例计数和派发参数。
*   必须确保每一帧都根据深度对溅射点进行排序，以实现正确的从后向前混合。

---

![](img/3a23afc523800bfaacb053f8b5862fcf_25.png)

![](img/3a23afc523800bfaacb053f8b5862fcf_27.png)

## ⚙️ Vulkan实验一：初始化与资源管理

上一节我们介绍了高斯溅射项目，本节中我们开始学习Vulkan实验的第一部分。Vulkan是一个现代的、显式的、跨平台的底层图形API。

**核心特点**：与OpenGL等传统API相比，Vulkan没有全局状态，需要程序员显式管理几乎所有资源状态。这带来了更大的控制权和优化空间，但也增加了代码复杂度。

### 初始化Vulkan

以下是创建Vulkan实例和逻辑设备的基本步骤：

1.  **创建实例**：实例管理应用程序的全局状态。创建时需要填写 `VkInstanceCreateInfo` 结构体，指定应用信息、启用的扩展和验证层。
    ```cpp
    VkInstance instance;
    VkInstanceCreateInfo createInfo{};
    createInfo.sType = VK_STRUCTURE_TYPE_INSTANCE_CREATE_INFO;
    createInfo.pApplicationInfo = &appInfo;
    // ... 设置扩展和层
    vkCreateInstance(&createInfo, nullptr, &instance);
    ```

2.  **选择物理设备**：枚举系统中的GPU（物理设备），并根据属性（如是否为独立显卡）选择最合适的一个。
    ```cpp
    uint32_t deviceCount = 0;
    vkEnumeratePhysicalDevices(instance, &deviceCount, nullptr);
    std::vector<VkPhysicalDevice> devices(deviceCount);
    vkEnumeratePhysicalDevices(instance, &deviceCount, devices.data());
    // ... 遍历 devices 并选择
    ```

3.  **创建逻辑设备**：通过选择的物理设备创建逻辑设备，这是与GPU交互的主要接口。在此步骤中，我们需要启用设备特性、扩展，并创建命令队列。
    ```cpp
    VkDevice device;
    VkDeviceCreateInfo deviceCreateInfo{};
    deviceCreateInfo.sType = VK_STRUCTURE_TYPE_DEVICE_CREATE_INFO;
    deviceCreateInfo.queueCreateInfoCount = static_cast<uint32_t>(queueCreateInfos.size());
    deviceCreateInfo.pQueueCreateInfos = queueCreateInfos.data();
    // ... 设置特性和扩展
    vkCreateDevice(physicalDevice, &deviceCreateInfo, nullptr, &device);
    ```

**队列**：队列用于向GPU提交命令缓冲区（绘制、计算、内存传输）。队列属于队列族，不同的族支持不同类型的操作（如图形、计算、传输）。使用异步计算队列可以帮助平衡内存密集型与计算密集型任务，提高GPU占用率。

### 创建资源：图像与缓冲区

![](img/3a23afc523800bfaacb053f8b5862fcf_29.png)

![](img/3a23afc523800bfaacb053f8b5862fcf_30.png)

资源（如图像和缓冲区）在Vulkan中需要显式创建并绑定到设备内存。

![](img/3a23afc523800bfaacb053f8b5862fcf_32.png)

![](img/3a23afc523800bfaacb053f8b5862fcf_34.png)

**创建图像**：图像可以表示最多三维的数据数组。创建时需要指定用途（如用作存储图像、采样器或渲染目标）、格式和布局。
```cpp
VkImageCreateInfo imageInfo{};
imageInfo.sType = VK_STRUCTURE_TYPE_IMAGE_CREATE_INFO;
imageInfo.imageType = VK_IMAGE_TYPE_2D;
imageInfo.format = VK_FORMAT_R8G8B8A8_UNORM;
imageInfo.usage = VK_IMAGE_USAGE_STORAGE_BIT | VK_IMAGE_USAGE_SAMPLED_BIT;
// ... 设置其他参数
vkCreateImage(device, &imageInfo, nullptr, &image);
```

![](img/3a23afc523800bfaacb053f8b5862fcf_36.png)

![](img/3a23afc523800bfaacb053f8b5862fcf_38.png)

**图像布局**：图像布局表示图像数据在内存中的排列方式，不同的管线阶段可能需要不同的布局。Vulkan要求程序员使用管线屏障显式地进行布局转换，而WebGPU等API会自动处理。

![](img/3a23afc523800bfaacb053f8b5862fcf_40.png)

**创建缓冲区**：缓冲区相对简单，本质是一块内存。创建时需要指定大小和用途。
```cpp
VkBufferCreateInfo bufferInfo{};
bufferInfo.sType = VK_STRUCTURE_TYPE_BUFFER_CREATE_INFO;
bufferInfo.size = bufferSize;
bufferInfo.usage = VK_BUFFER_USAGE_STORAGE_BUFFER_BIT;
vkCreateBuffer(device, &bufferInfo, nullptr, &buffer);
```

**绑定内存**：图像和缓冲区本身不持有内存，需要先查询内存需求，然后分配设备内存并与之绑定。
```cpp
VkMemoryRequirements memRequirements;
vkGetImageMemoryRequirements(device, image, &memRequirements);
VkMemoryAllocateInfo allocInfo{};
allocInfo.sType = VK_STRUCTURE_TYPE_MEMORY_ALLOCATE_INFO;
allocInfo.allocationSize = memRequirements.size;
allocInfo.memoryTypeIndex = findMemoryType(memRequirements.memoryTypeBits, VK_MEMORY_PROPERTY_DEVICE_LOCAL_BIT);
vkAllocateMemory(device, &allocInfo, nullptr, &imageMemory);
vkBindImageMemory(device, image, imageMemory, 0);
```

![](img/3a23afc523800bfaacb053f8b5862fcf_42.png)

![](img/3a23afc523800bfaacb053f8b5862fcf_44.png)

**从主机更新数据**：如果CPU需要更新缓冲区数据，通常的流程是：
1.  创建一个主机可见的暂存缓冲区。
2.  将数据复制到暂存缓冲区。
3.  创建一个设备本地的目标缓冲区。
4.  通过命令缓冲区，将数据从暂存缓冲区复制到目标缓冲区。
5.  销毁暂存缓冲区。

![](img/3a23afc523800bfaacb053f8b5862fcf_46.png)

### 描述符与管线布局

![](img/3a23afc523800bfaacb053f8b5862fcf_48.png)

![](img/3a23afc523800bfaacb053f8b5862fcf_49.png)

![](img/3a23afc523800bfaacb053f8b5862fcf_51.png)

![](img/3a23afc523800bfaacb053f8b5862fcf_53.png)

上一节我们创建了资源，本节中我们来看看如何将这些资源绑定到着色器。在Vulkan中，这通过描述符和描述符集完成。

**描述符**：描述符描述了资源如何绑定到着色器的一个资源槽。

![](img/3a23afc523800bfaacb053f8b5862fcf_55.png)

![](img/3a23afc523800bfaacb053f8b5862fcf_57.png)

**描述符集**：描述符被分组到描述符集中。创建描述符集前，需要先创建描述符集布局，它定义了该集合中所有绑定的格式。
```cpp
VkDescriptorSetLayoutBinding layoutBinding{};
layoutBinding.binding = 0; // 与着色器中的 binding 对应
layoutBinding.descriptorType = VK_DESCRIPTOR_TYPE_STORAGE_IMAGE;
layoutBinding.stageFlags = VK_SHADER_STAGE_COMPUTE_BIT;
VkDescriptorSetLayoutCreateInfo layoutInfo{};
layoutInfo.sType = VK_STRUCTURE_TYPE_DESCRIPTOR_SET_LAYOUT_CREATE_INFO;
layoutInfo.bindingCount = 1;
layoutInfo.pBindings = &layoutBinding;
vkCreateDescriptorSetLayout(device, &layoutInfo, nullptr, &descriptorSetLayout);
```

**更新描述符集**：分配描述符集后，需要将具体的资源（缓冲区或图像视图）写入其中。
```cpp
VkDescriptorImageInfo imageInfo{};
imageInfo.imageView = storageImageView;
imageInfo.imageLayout = VK_IMAGE_LAYOUT_GENERAL;
VkWriteDescriptorSet descriptorWrite{};
descriptorWrite.sType = VK_STRUCTURE_TYPE_WRITE_DESCRIPTOR_SET;
descriptorWrite.dstSet = descriptorSet;
descriptorWrite.dstBinding = 0;
descriptorWrite.descriptorType = VK_DESCRIPTOR_TYPE_STORAGE_IMAGE;
descriptorWrite.pImageInfo = &imageInfo;
vkUpdateDescriptorSets(device, 1, &descriptorWrite, 0, nullptr);
```

![](img/3a23afc523800bfaacb053f8b5862fcf_59.png)

![](img/3a23afc523800bfaacb053f8b5862fcf_60.png)

**最佳实践**：建议根据资源的更新频率和用途将描述符分组到不同的描述符集中，例如一个集合用于每帧更新的数据，另一个用于静态数据。

### 创建图形与计算管线

![](img/3a23afc523800bfaacb053f8b5862fcf_62.png)

![](img/3a23afc523800bfaacb053f8b5862fcf_64.png)

有了描述符集布局，我们就可以创建管线布局，并最终创建管线。

![](img/3a23afc523800bfaacb053f8b5862fcf_66.png)

![](img/3a23afc523800bfaacb053f8b5862fcf_68.png)

**着色器模块**：Vulkan着色器通常用GLSL/HLSL编写，但必须编译为SPIR-V中间表示才能使用。
```cpp
VkShaderModuleCreateInfo createInfo{};
createInfo.sType = VK_STRUCTURE_TYPE_SHADER_MODULE_CREATE_INFO;
createInfo.codeSize = codeSize;
createInfo.pCode = reinterpret_cast<const uint32_t*>(code);
vkCreateShaderModule(device, &createInfo, nullptr, &shaderModule);
```

![](img/3a23afc523800bfaacb053f8b5862fcf_70.png)

![](img/3a23afc523800bfaacb053f8b5862fcf_72.png)

**图形管线**：图形管线的创建非常复杂，需要定义一系列固定功能和可编程阶段的状态，例如：
*   顶点输入状态（绑定描述、属性描述）。
*   输入装配状态（拓扑类型，如三角形列表）。
*   光栅化状态（多边形模式、剔除模式）。
*   视口状态、多重采样状态、深度/模板测试状态、颜色混合状态等。

![](img/3a23afc523800bfaacb053f8b5862fcf_74.png)

**计算管线**：计算管线的创建则简单得多，主要需要指定计算着色器和管线布局。

![](img/3a23afc523800bfaacb053f8b5862fcf_76.png)

![](img/3a23afc523800bfaacb053f8b5862fcf_78.png)

![](img/3a23afc523800bfaacb053f8b5862fcf_80.png)

**渲染通道**：渲染通道是Vulkan图形管线特有的概念，它定义了一组附件（如颜色附件、深度附件）及其在渲染过程中的使用方法。子通道是渲染通道内的子部分，可以优化Tile-Based架构GPU上的带宽。

![](img/3a23afc523800bfaacb053f8b5862fcf_82.png)

**帧缓冲区**：帧缓冲区包装了图像视图，使其能够被渲染通道使用。

![](img/3a23afc523800bfaacb053f8b5862fcf_84.png)

**创建管线布局与管线**：管线布局组合了该管线将使用的所有描述符集布局。最后，将所有状态信息填入 `VkGraphicsPipelineCreateInfo` 来创建图形管线。
```cpp
VkPipelineLayout pipelineLayout;
VkPipelineLayoutCreateInfo pipelineLayoutInfo{};
pipelineLayoutInfo.sType = VK_STRUCTURE_TYPE_PIPELINE_LAYOUT_CREATE_INFO;
pipelineLayoutInfo.setLayoutCount = 1;
pipelineLayoutInfo.pSetLayouts = &descriptorSetLayout;
vkCreatePipelineLayout(device, &pipelineLayoutInfo, nullptr, &pipelineLayout);

![](img/3a23afc523800bfaacb053f8b5862fcf_86.png)

![](img/3a23afc523800bfaacb053f8b5862fcf_88.png)

VkGraphicsPipelineCreateInfo pipelineInfo{};
pipelineInfo.sType = VK_STRUCTURE_TYPE_GRAPHICS_PIPELINE_CREATE_INFO;
pipelineInfo.stageCount = 2; // 顶点和片段着色器阶段
pipelineInfo.pStages = shaderStages;
pipelineInfo.pVertexInputState = &vertexInputInfo;
pipelineInfo.pInputAssemblyState = &inputAssembly;
pipelineInfo.pViewportState = &viewportState;
pipelineInfo.pRasterizationState = &rasterizer;
// ... 设置其他状态
pipelineInfo.layout = pipelineLayout;
pipelineInfo.renderPass = renderPass;
vkCreateGraphicsPipelines(device, VK_NULL_HANDLE, 1, &pipelineInfo, nullptr, &graphicsPipeline);
```

---

## 📝 总结

![](img/3a23afc523800bfaacb053f8b5862fcf_90.png)

![](img/3a23afc523800bfaacb053f8b5862fcf_92.png)

本节课中我们一起学习了两个主要部分。

首先，我们深入了解了**项目五：3D高斯溅射渲染**。我们学习了其基于高斯分布的核心原理、从3D点云到2D屏幕的渲染管线，包括数据加载、预处理（投影、排序）和基于四边形的渲染混合过程。

其次，我们开始了**Vulkan实验课程的第一部分**。我们学习了Vulkan的初始化流程，包括创建实例、选择物理设备、创建逻辑设备和队列。我们探讨了如何创建和管理关键资源，如图像和缓冲区，并理解了图像布局转换的重要性。最后，我们介绍了将资源绑定到着色器的核心机制——描述符和描述符集，并概述了创建复杂图形管线与简单计算管线所需的步骤。

![](img/3a23afc523800bfaacb053f8b5862fcf_94.png)

![](img/3a23afc523800bfaacb053f8b5862fcf_96.png)

Vulkan是一个显式且强大的API，虽然入门曲线陡峭，但能提供深度的硬件控制和优化潜力。在接下来的实验中，我们将继续学习命令缓冲区、同步和渲染循环等内容。