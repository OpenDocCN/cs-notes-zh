# GPU编程和框架：3：WebGPU 入门教程 🚀

![](img/27abea06e675c0ec2dc4e187af5c1777_1.png)

## 概述

在本节课中，我们将学习 WebGPU，这是现代 Web 图形编程的新标准。我们将了解它为何被创建，其核心概念，并通过一个简单的“Hello Triangle”示例来学习其基本用法。课程内容基于宾夕法尼亚大学 CIS 5650 课程中 Google Chrome GPU 团队工程师的客座讲座。

---

## 为什么需要 WebGPU？🤔

上一节我们回顾了图形 API 的历史。本节中我们来看看为什么需要一个新的 Web 图形 API。

![](img/27abea06e675c0ec2dc4e187af5c1777_3.png)

![](img/27abea06e675c0ec2dc4e187af5c1777_5.png)

![](img/27abea06e675c0ec2dc4e187af5c1777_7.png)

WebGL 是 WebGPU 的前身，它基于 OpenGL ES，而 OpenGL 的设计理念可以追溯到 1992 年。虽然 WebGL 应用广泛（例如 Google Maps），但其底层架构已无法充分利用现代 GPU 的硬件特性。

![](img/27abea06e675c0ec2dc4e187af5c1777_9.png)

![](img/27abea06e675c0ec2dc4e187af5c1777_11.png)

![](img/27abea06e675c0ec2dc4e187af5c1777_13.png)

![](img/27abea06e675c0ec2dc4e187af5c1777_15.png)

![](img/27abea06e675c0ec2dc4e187af5c1777_17.png)

![](img/27abea06e675c0ec2dc4e187af5c1777_18.png)

![](img/27abea06e675c0ec2dc4e187af5c1777_20.png)

![](img/27abea06e675c0ec2dc4e187af5c1777_22.png)

在 2014 年至 2016 年间，行业推出了新的原生图形 API：
*   **Metal** (Apple, 2014)
*   **Direct3D 12** (Microsoft, 2015)
*   **Vulkan** (Khronos Group, 2016)

![](img/27abea06e675c0ec2dc4e187af5c1777_24.png)

![](img/27abea06e675c0ec2dc4e187af5c1777_26.png)

这些“显式”API 的设计更贴近现代 GPU 的并行架构，能提供更好的性能和更低的开销。Web 平台需要跟上这一趋势，因此 WebGPU 应运而生。它是一个全新的、跨浏览器的 API，旨在抽象 Metal、D3D12 和 Vulkan，同时更好地融入 Web 平台和 JavaScript 生态。

![](img/27abea06e675c0ec2dc4e187af5c1777_28.png)

![](img/27abea06e675c0ec2dc4e187af5c1777_30.png)

与 WebGL2 相比，WebGPU 引入了关键的新特性，例如：
*   **计算着色器** (`compute shaders`)
*   **间接绘制** (`indirect drawing`)
*   **渲染包** (`render bundles`)
*   更灵活的 Canvas 集成
*   更完善的错误提示和调试功能

![](img/27abea06e675c0ec2dc4e187af5c1777_32.png)

![](img/27abea06e675c0ec2dc4e187af5c1777_34.png)

最重要的是，它移除了 OpenGL 中复杂的全局状态机，使得 API 更易于学习和使用。

---

## WebGPU 核心概念 🧠

理解了 WebGPU 的诞生背景后，本节我们来深入探讨其核心架构和对象模型。

![](img/27abea06e675c0ec2dc4e187af5c1777_36.png)

WebGPU 的 API 设计围绕几个核心对象展开，它们共同协作以向 GPU 提交命令。其复杂程度介于 WebGL 和 Vulkan 之间，旨在教会你适用于所有现代图形 API 的核心概念。

以下是初始化 WebGPU 并绘制一个三角形所涉及的主要步骤和对象：

### 1. 适配器 (`Adapter`) 和设备 (`Device`)
这是初始化的第一步。`Adapter` 代表系统上的一个物理或逻辑 GPU 实现。通过它，你可以查询硬件的能力（特性和限制）。

![](img/27abea06e675c0ec2dc4e187af5c1777_38.png)

```javascript
const adapter = await navigator.gpu.requestAdapter();
const device = await adapter.requestDevice();
```
`Device` 是 WebGPU 的主要接口，用于创建所有资源（缓冲区、纹理等）并获取用于提交命令的队列 (`Queue`)。

### 2. 画布上下文 (`Canvas Context`)
与 WebGL 不同，WebGPU 的上下文与设备绑定，而不是与画布 (`Canvas`) 一对一绑定。
```javascript
const context = canvas.getContext(‘webgpu’);
context.configure({
    device: device,
    format: navigator.gpu.getPreferredCanvasFormat(),
});
```

### 3. 缓冲区 (`Buffer`) 与数据上传
缓冲区用于在 CPU 和 GPU 之间传递数据（如顶点数据）。创建时需要指定大小和用途，且创建后不可更改。
```javascript
// 创建顶点数据
const vertices = new Float32Array([...]);
// 创建 GPU 缓冲区
const vertexBuffer = device.createBuffer({
    size: vertices.byteLength,
    usage: GPUBufferUsage.VERTEX | GPUBufferUsage.COPY_DST,
});
// 将数据从 CPU 写入 GPU 缓冲区
device.queue.writeBuffer(vertexBuffer, 0, vertices);
```

![](img/27abea06e675c0ec2dc4e187af5c1777_40.png)

![](img/27abea06e675c0ec2dc4e187af5c1777_42.png)

![](img/27abea06e675c0ec2dc4e187af5c1777_44.png)

### 4. 着色器与 WGSL
WebGPU 使用一种新的着色语言 **WGSL** (WebGPU Shading Language)。它的语法类似 Rust，并且单个模块可以包含多个入口点（如顶点和片段着色器）。
```wgsl
// 示例：简单的顶点着色器
@vertex
fn vs_main(@location(0) position: vec4<f32>) -> @builtin(position) vec4<f32> {
    return position;
}
```
着色器模块通过 `device.createShaderModule` 创建。

### 5. 渲染管线 (`Render Pipeline`)
这是 WebGPU 的一个关键概念。在 WebGL 中，混合、深度测试等状态是动态设置的。而在 WebGPU 中，几乎所有渲染状态都必须在管线创建时预先定义并打包成一个不可变的对象。
```javascript
const renderPipeline = device.createRenderPipeline({
    vertex: {
        module: shaderModule,
        entryPoint: ‘vs_main’,
        buffers: [/* 顶点缓冲区布局 */]
    },
    fragment: {
        module: shaderModule,
        entryPoint: ‘fs_main’,
        targets: [{ format: canvasFormat }]
    },
    primitive: { topology: ‘triangle-list’ },
    layout: ‘auto’ // 管线布局
});
```
这种方式允许驱动进行大量预编译和优化，提升了运行时效率。

### 6. 命令编码与提交
WebGPU 采用命令缓冲模式。你首先创建一个 `CommandEncoder`，然后在其中记录命令（如复制缓冲区、开始渲染通道），最后将这些命令编码并提交到队列中执行。
```javascript
// 创建命令编码器
const commandEncoder = device.createCommandEncoder();
// 开始一个渲染通道
const renderPass = commandEncoder.beginRenderPass({
    colorAttachments: [{
        view: context.getCurrentTexture().createView(),
        loadOp: ‘clear’,
        storeOp: ‘store’,
        clearValue: [0, 0, 0, 1],
    }]
});
// 设置管线、顶点缓冲区，并发出绘制命令
renderPass.setPipeline(renderPipeline);
renderPass.setVertexBuffer(0, vertexBuffer);
renderPass.draw(3); // 绘制 3 个顶点（一个三角形）
// 结束通道并完成编码
renderPass.end();
// 提交命令到 GPU 队列
const commandBuffer = commandEncoder.finish();
device.queue.submit([commandBuffer]);
```
这个过程是异步的，命令被记录并提交后，由 GPU 在适当的时候执行。

---

## 数据绑定：如何将资源传递给着色器 🔗

![](img/27abea06e675c0ec2dc4e187af5c1777_46.png)

![](img/27abea06e675c0ec2dc4e187af5c1777_48.png)

上一节我们介绍了如何配置管线并发出绘制命令。本节中我们来看看如何将缓冲区、纹理等资源（数据）传递到着色器中供其使用。

![](img/27abea06e675c0ec2dc4e187af5c1777_50.png)

![](img/27abea06e675c0ec2dc4e187af5c1777_52.png)

![](img/27abea06e675c0ec2dc4e187af5c1777_54.png)

![](img/27abea06e675c0ec2dc4e187af5c1777_56.png)

在 WGSL 着色器中，你可以通过 `@group` 和 `@binding` 属性来声明需要绑定的资源。
```wgsl
@group(0) @binding(0) var<uniform> myUniforms: MyUniformStruct;
@group(0) @binding(1) var myTexture: texture_2d<f32>;
@group(0) @binding(2) var mySampler: sampler;
```

![](img/27abea06e675c0ec2dc4e187af5c1777_58.png)

![](img/27abea06e675c0ec2dc4e187af5c1777_60.png)

![](img/27abea06e675c0ec2dc4e187af5c1777_62.png)

![](img/27abea06e675c0ec2dc4e187af5c1777_64.png)

![](img/27abea06e675c0ec2dc4e187af5c1777_65.png)

在 JavaScript 端，这个过程分为两步：

![](img/27abea06e675c0ec2dc4e187af5c1777_67.png)

![](img/27abea06e675c0ec2dc4e187af5c1777_69.png)

![](img/27abea06e675c0ec2dc4e187af5c1777_71.png)

![](img/27abea06e675c0ec2dc4e187af5c1777_73.png)

![](img/27abea06e675c0ec2dc4e187af5c1777_75.png)

![](img/27abea06e675c0ec2dc4e187af5c1777_77.png)

![](img/27abea06e675c0ec2dc4e187af5c1777_79.png)

**1. 创建绑定组布局 (`Bind Group Layout`)**：
它定义了着色器中一个绑定组（`@group`）的结构，即每个绑定槽（`@binding`）期望的资源类型（如只读缓冲区、可写存储纹理等）。
```javascript
const bindGroupLayout = device.createBindGroupLayout({
    entries: [
        {
            binding: 0,
            visibility: GPUShaderStage.VERTEX | GPUShaderStage.FRAGMENT,
            buffer: { type: ‘uniform’ }
        },
        {
            binding: 1,
            visibility: GPUShaderStage.FRAGMENT,
            texture: { sampleType: ‘float’ }
        },
        // ... 其他绑定
    ]
});
```

![](img/27abea06e675c0ec2dc4e187af5c1777_81.png)

**2. 创建绑定组 (`Bind Group`)**：
它根据布局，将具体的资源（如缓冲区对象、纹理视图）绑定到对应的槽位上。
```javascript
const bindGroup = device.createBindGroup({
    layout: bindGroupLayout,
    entries: [
        { binding: 0, resource: { buffer: uniformBuffer } },
        { binding: 1, resource: myTextureView },
        // ... 其他资源
    ]
});
```

![](img/27abea06e675c0ec2dc4e187af5c1777_83.png)

在渲染通道中，你只需设置整个绑定组即可：
```javascript
renderPass.setBindGroup(0, bindGroup);
```
这种将相关资源分组绑定的设计，减少了需要调用的 API 次数，并符合现代 GPU 的工作方式。

![](img/27abea06e675c0ec2dc4e187af5c1777_85.png)

![](img/27abea06e675c0ec2dc4e187af5c1777_87.png)

---

## 调试与最佳实践 🐛

![](img/27abea06e675c0ec2dc4e187af5c1777_89.png)

![](img/27abea06e675c0ec2dc4e187af5c1777_91.png)

掌握了基本绘制和数据绑定后，开发中难免会遇到问题。本节我们来看看 WebGPU 提供的调试工具和一些性能优化的最佳实践。

![](img/27abea06e675c0ec2dc4e187af5c1777_93.png)

### 调试 (`Debugging`)
WebGPU 设计了比 WebGL 更友好的错误信息。当验证失败时，浏览器会提供包含上下文信息的错误，指出问题出在哪个调用、哪个资源上。
```
// 示例错误信息
Error: Buffer (Player Vertices) usage doesn’t include VERTEX.
    While encoding [RenderPass “Main Render Pass”].
    While calling [CommandEncoder “Frame”].beginRenderPass.
```
为了获得更清晰的错误信息，**请为你创建的所有对象（缓冲区、纹理、通道等）添加标签 (`label`)**。
```javascript
const buffer = device.createBuffer({
    label: ‘Player Vertex Data’, // 添加标签
    size: ...,
    usage: ...
});
```

此外，你还可以使用 **调试组 (`Debug Group`)** 来在开发者工具中结构化你的命令流，便于定位问题。
```javascript
commandEncoder.pushDebugGroup(‘Main Render Loop’);
commandEncoder.pushDebugGroup(‘Render Scene’);
// ... 记录渲染命令
commandEncoder.popDebugGroup(); // ‘Render Scene’
commandEncoder.popDebugGroup(); // ‘Main Render Loop’
```

### 性能最佳实践 (`Best Practices`)
以下是几条重要的性能优化建议：

**1. 尽量减少管线数量**
管线的创建和切换都有成本。尽量复用管线，或通过超级着色器（使用分支或常量）来减少管线变体的数量。

**2. 使用异步管线创建 (`createRenderPipelineAsync`)**
管线编译可能很耗时。使用异步版本可以避免在管线就绪前阻塞提交，并且浏览器可能利用此提示进行并行编译。
```javascript
const pipeline = await device.createRenderPipelineAsync({...});
```

![](img/27abea06e675c0ec2dc4e187af5c1777_95.png)

![](img/27abea06e675c0ec2dc4e187af5c1777_97.png)

![](img/27abea06e675c0ec2dc4e187af5c1777_99.png)

![](img/27abea06e675c0ec2dc4e187af5c1777_101.png)

**3. 在管线间共享绑定组**
如果多个管线使用相同的资源绑定布局（例如相机 Uniform 缓冲区），可以创建并共享同一个绑定组，以减少 `setBindGroup` 的调用。

**4. 使用正确的画布格式**
查询并使用系统首选的画布纹理格式（通常是 `‘bgra8unorm’`），可以避免一次额外的格式转换，提升性能。
```javascript
const format = navigator.gpu.getPreferredCanvasFormat();
context.configure({ device, format });
```

**5. 利用渲染包 (`Render Bundles`)**
对于静态或重复渲染的对象序列，可以将其预记录到 `RenderBundle` 中。之后每帧只需一个调用即可重放所有命令，极大减少了 JavaScript 端的开销。
```javascript
// 创建阶段
const bundleEncoder = device.createRenderBundleEncoder({...});
// ... 在 bundleEncoder 中记录绘制命令
const renderBundle = bundleEncoder.finish();

// 渲染阶段（每帧）
renderPass.executeBundles([renderBundle]);
```

---

## 总结

本节课中我们一起学习了 WebGPU，这是下一代 Web 图形 API。我们从其诞生的背景开始，了解了它为何要取代 WebGL。接着，我们深入探讨了其核心对象模型，包括适配器、设备、缓冲区、管线以及命令编码流程。我们学习了如何通过绑定组和绑定组布局将数据从 JavaScript 端传递到 WGSL 着色器。最后，我们介绍了 WebGPU 强大的调试支持功能，并总结了几条关键的开发与性能优化最佳实践。

![](img/27abea06e675c0ec2dc4e187af5c1777_103.png)

![](img/27abea06e675c0ec2dc4e187af5c1777_105.png)

![](img/27abea06e675c0ec2dc4e187af5c1777_106.png)

WebGPU 的设计更贴近现代 GPU 架构，虽然初始设置比 WebGL 稍显复杂，但其显式的、状态集中的设计消除了许多隐藏的陷阱，使得应用更健壮、性能更可预测，并且所学的概念能直接迁移到其他现代图形 API（如 Vulkan、D3D12）中。