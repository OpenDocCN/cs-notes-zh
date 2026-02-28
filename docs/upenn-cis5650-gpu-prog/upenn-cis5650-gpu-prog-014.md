# 014：从CUDA到WebGPU的SAXPY计算教程 🚀

![](img/20cb9720d4b8b89b9cfd6e59e05c448f_1.png)

![](img/20cb9720d4b8b89b9cfd6e59e05c448f_3.png)

在本节课中，我们将学习如何将一个简单的CUDA计算任务——SAXPY（单精度a乘X加Y）——移植到WebGPU平台上。我们将通过对比CUDA和WebGPU的API，理解图形API如何用于通用计算，并亲自动手实现一个完整的WebGPU计算流程。

![](img/20cb9720d4b8b89b9cfd6e59e05c448f_5.png)

![](img/20cb9720d4b8b89b9cfd6e59e05c448f_7.png)

![](img/20cb9720d4b8b89b9cfd6e59e05c448f_9.png)

## 概述 📋

SAXPY是一个基础的向量运算，公式为：**z = a * x + y**。在CUDA中，我们熟悉其编程流程：分配主机与设备内存、复制数据、启动内核、取回结果。WebGPU作为一个新兴的、跨平台的图形与计算API，其工作流与CUDA有相似之处，但也存在显著差异，特别是在初始化、资源绑定和着色器调用方面。

上一节我们回顾了CUDA中SAXPY的实现，本节中我们来看看如何在WebGPU中完成相同的任务。

## 从CUDA到WebGPU的思维转换 🔄

CUDA是专为NVIDIA GPU设计的“计算优先”API。你可以直接启动内核进行计算。而传统的图形API（如OpenGL）即使要进行通用计算，也需要经过帧缓冲、光栅化管线等图形流程。WebGPU在一定程度上弥合了这种差异，它既可以用于图形渲染，也可以像CUDA一样用于纯计算任务。

WebGPU的设计考虑了Web环境的安全性、隐私性和跨平台需求，使其成为在浏览器中进行客户端机器学习推理等任务的绝佳选择。

![](img/20cb9720d4b8b89b9cfd6e59e05c448f_11.png)

## 项目结构与CPU基准实现 💻

![](img/20cb9720d4b8b89b9cfd6e59e05c448f_13.png)

![](img/20cb9720d4b8b89b9cfd6e59e05c448f_15.png)

我们的教程将遵循一个清晰的流程。首先，我们设置一个简单的HTML页面作为包装器，并实现CPU版本的SAXPY作为验证基准。

![](img/20cb9720d4b8b89b9cfd6e59e05c448f_17.png)

以下是项目的基本HTML结构：

```html
<!DOCTYPE html>
<html>
<head>
    <title>WebGPU SAXPY</title>
    <style> /* 一些美化页面的CSS */ </style>
</head>
<body>
    <h1>WebGPU SAXPY 测试</h1>
    <script type="module" src="webgpu_saxpy.js"></script>
</body>
</html>
```

![](img/20cb9720d4b8b89b9cfd6e59e05c448f_19.png)

![](img/20cb9720d4b8b89b9cfd6e59e05c448f_21.png)

![](img/20cb9720d4b8b89b9cfd6e59e05c448f_23.png)

接下来，我们在JavaScript中实现CPU版本的SAXPY逻辑，用于生成测试数据并验证GPU结果。

![](img/20cb9720d4b8b89b9cfd6e59e05c448f_25.png)

![](img/20cb9720d4b8b89b9cfd6e59e05c448f_27.png)

![](img/20cb9720d4b8b89b9cfd6e59e05c448f_29.png)

![](img/20cb9720d4b8b89b9cfd6e59e05c448f_31.png)

![](img/20cb9720d4b8b89b9cfd6e59e05c448f_33.png)

![](img/20cb9720d4b8b89b9cfd6e59e05c448f_35.png)

![](img/20cb9720d4b8b89b9cfd6e59e05c448f_37.png)

![](img/20cb9720d4b8b89b9cfd6e59e05c448f_39.png)

```javascript
// 初始化随机向量和标量
function initSaxpy(size) {
    const x = new Float32Array(size);
    const y = new Float32Array(size);
    const z = new Float32Array(size); // 初始化为0
    const a = Math.random();
    for (let i = 0; i < size; i++) {
        x[i] = Math.random();
        y[i] = Math.random();
    }
    return { size, a, x, y, z };
}

![](img/20cb9720d4b8b89b9cfd6e59e05c448f_41.png)

![](img/20cb9720d4b8b89b9cfd6e59e05c448f_43.png)

![](img/20cb9720d4b8b89b9cfd6e59e05c448f_45.png)

![](img/20cb9720d4b8b89b9cfd6e59e05c448f_47.png)

// CPU版本SAXPY
function cpuSaxpy(size, a, x, y, z) {
    for (let i = 0; i < size; i++) {
        z[i] = a * x[i] + y[i];
    }
    return z;
}
```

## 初始化WebGPU设备 ⚙️

在WebGPU中开始计算之前，我们必须先初始化并获取GPU设备。这与CUDA中设置设备的概念类似。

```javascript
async function initWebGpu() {
    // 1. 检查浏览器是否支持WebGPU
    if (!navigator.gpu) {
        throw new Error('WebGPU not supported');
    }

    // 2. 请求GPU适配器（Adapter）
    const adapter = await navigator.gpu.requestAdapter();
    if (!adapter) {
        throw new Error('No GPU adapter found');
    }
    // 获取适配器信息（类似CUDA的deviceProp）
    const adapterInfo = await adapter.requestAdapterInfo();

    // 3. 请求GPU设备（Device）
    const device = await adapter.requestDevice();
    if (!device) {
        throw new Error('No GPU device found');
    }

    console.log(`GPU: ${adapterInfo.vendor} ${adapterInfo.architecture}`);
    return { adapter, adapterInfo, device };
}
```
`requestAdapter`获取的是GPU的抽象信息，而`requestDevice`才是我们后续操作（如创建缓冲区、管线）所依赖的具体设备对象。这个过程是异步的，我们使用`async/await`语法来处理。

## 在GPU上分配与传输内存 📦

在CUDA中，我们使用`cudaMalloc`和`cudaMemcpy`。在WebGPU中，我们使用`device.createBuffer`来创建缓冲区，并通过不同的方式填充数据。

以下是创建和填充输入缓冲区`x`的两种方法：

```javascript
async function webgpuSaxpy(device, size, a, x, y) {
    // 方法一：创建时映射(MAP)，在CPU端填充后取消映射
    const xBuffer = device.createBuffer({
        label: 'x buffer',
        size: x.byteLength,
        usage: GPUBufferUsage.STORAGE, // 用作存储
        mappedAtCreation: true, // 创建时映射到CPU
    });
    // 获取CPU端的ArrayBuffer视图并填充数据
    new Float32Array(xBuffer.getMappedRange()).set(x);
    xBuffer.unmap(); // 取消映射，数据上传至GPU

    // 方法二：先创建缓冲区，再用queue.writeBuffer写入
    const yBuffer = device.createBuffer({
        label: 'y buffer',
        size: y.byteLength,
        usage: GPUBufferUsage.STORAGE | GPUBufferUsage.COPY_DST,
    });
    device.queue.writeBuffer(yBuffer, 0, y); // 直接写入GPU缓冲区

    // 创建用于存储结果的Z缓冲区
    const zBuffer = device.createBuffer({
        label: 'z buffer',
        size: x.byteLength,
        usage: GPUBufferUsage.STORAGE | GPUBufferUsage.COPY_SRC,
    });

    // 创建Uniform缓冲区，用于传递标量a和大小size
    const uniformBuffer = device.createBuffer({
        label: 'uniforms',
        size: 2 * Float32Array.BYTES_PER_ELEMENT, // 两个float
        usage: GPUBufferUsage.UNIFORM | GPUBufferUsage.COPY_DST,
    });
    const uniformData = new Float32Array([a, size]);
    device.queue.writeBuffer(uniformBuffer, 0, uniformData);
}
```
`GPUBufferUsage`标志定义了缓冲区的用途：
*   `STORAGE`： 用作计算着色器的存储。
*   `COPY_DST`： 可作为数据拷贝的目标（CPU->GPU）。
*   `COPY_SRC`： 可作为数据拷贝的源（GPU->CPU）。
*   `UNIFORM`： 用作统一变量（Uniform）缓冲区。

## 编写计算着色器（Compute Shader）🖥️

计算着色器相当于CUDA中的内核（kernel）。WebGPU使用基于WGSL（WebGPU Shading Language）的着色器。

```rust
// WebGPU 计算着色器 (WGSL)
@group(0) @binding(0) var<uniform> uniforms: ScalarStruct;
@group(0) @binding(1) var<storage, read> x: array<f32>;
@group(0) @binding(2) var<storage, read> y: array<f32>;
@group(0) @binding(3) var<storage, read_write> z: array<f32>;

struct ScalarStruct {
    scale: f32,
    size: f32,
};

@compute @workgroup_size(256) // 定义工作组大小（线程块大小）
fn computeMain(@builtin(global_invocation_id) global_id: vec3<u32>) {
    let index = global_id.x;
    // 边界检查
    if (index >= u32(uniforms.size)) {
        return;
    }
    // SAXPY 核心计算
    z[index] = uniforms.scale * x[index] + y[index];
}
```
关键概念解析：
*   `@group`和`@binding`： 定义了资源（缓冲区、采样器）在着色器中的绑定位置和顺序，类似于函数参数列表。
*   `@workgroup_size(256)`： **在着色器内部**定义每个工作组（Workgroup，相当于CUDA的线程块）包含的线程数。这是与CUDA的一个主要区别，CUDA的线程块大小是在主机端调用内核时指定的。
*   `@builtin(global_invocation_id)`： 内置变量，等价于CUDA中的 `blockIdx * blockDim + threadIdx`。
*   `var<storage, read>`： 声明一个只读的存储缓冲区变量。

## 创建管线与资源绑定 🔗

![](img/20cb9720d4b8b89b9cfd6e59e05c448f_49.png)

![](img/20cb9720d4b8b89b9cfd6e59e05c448f_51.png)

在WebGPU中，我们需要显式地创建管线布局（Pipeline Layout）和绑定组（Bind Group），将GPU缓冲区和着色器中的绑定点关联起来。

```javascript
// 1. 创建着色器模块
const shaderCode = `...`; // 上一节的WGSL代码字符串
const shaderModule = device.createShaderModule({
    label: 'SAXPY shader',
    code: shaderCode,
});

// 2. 创建绑定组布局（Bind Group Layout）
// 描述着色器中@binding的顺序和类型
const bindGroupLayout = device.createBindGroupLayout({
    label: 'SAXPY bind group layout',
    entries: [
        { // @binding(0) uniforms
            binding: 0,
            visibility: GPUShaderStage.COMPUTE,
            buffer: { type: 'uniform' }
        },
        { // @binding(1) x
            binding: 1,
            visibility: GPUShaderStage.COMPUTE,
            buffer: { type: 'read-only-storage' }
        },
        { // @binding(2) y
            binding: 2,
            visibility: GPUShaderStage.COMPUTE,
            buffer: { type: 'read-only-storage' }
        },
        { // @binding(3) z
            binding: 3,
            visibility: GPUShaderStage.COMPUTE,
            buffer: { type: 'storage' }
        },
    ]
});

// 3. 创建绑定组（Bind Group）
// 将具体的缓冲区对象绑定到布局指定的位置
const bindGroup = device.createBindGroup({
    label: 'SAXPY bind group',
    layout: bindGroupLayout,
    entries: [
        { binding: 0, resource: { buffer: uniformBuffer }},
        { binding: 1, resource: { buffer: xBuffer }},
        { binding: 2, resource: { buffer: yBuffer }},
        { binding: 3, resource: { buffer: zBuffer }},
    ]
});

// 4. 创建计算管线（Compute Pipeline）
const pipelineLayout = device.createPipelineLayout({
    label: 'SAXPY pipeline layout',
    bindGroupLayouts: [bindGroupLayout],
});
const computePipeline = device.createComputePipeline({
    label: 'SAXPY pipeline',
    layout: pipelineLayout,
    compute: {
        module: shaderModule,
        entryPoint: 'computeMain', // 对应WGSL中的函数名
    }
});
```
绑定组布局定义了“槽位”的规格，而绑定组则将实际的资源填入这些槽位。这种设计允许复用布局和资源，提高灵活性。

## 调度计算与读取结果 🚦

一切准备就绪后，我们通过命令编码器（Command Encoder）来录制并提交执行命令。

![](img/20cb9720d4b8b89b9cfd6e59e05c448f_53.png)

```javascript
// 1. 创建命令编码器
const encoder = device.createCommandEncoder({ label: 'SAXPY encoder' });

![](img/20cb9720d4b8b89b9cfd6e59e05c448f_55.png)

![](img/20cb9720d4b8b89b9cfd6e59e05c448f_57.png)

![](img/20cb9720d4b8b89b9cfd6e59e05c448f_59.png)

// 2. 开始计算通道（Compute Pass）
const pass = encoder.beginComputePass({ label: 'SAXPY compute pass' });
pass.setPipeline(computePipeline);
pass.setBindGroup(0, bindGroup); // 设置绑定组，0对应@group(0)
// 调度计算！计算网格大小 = ceil(size / workgroup_size)
const workgroupCount = Math.ceil(size / 256);
pass.dispatchWorkgroups(workgroupCount); // 启动工作组
pass.end();

// 3. 创建用于回读的暂存缓冲区
const stagingBuffer = device.createBuffer({
    size: zBuffer.size,
    usage: GPUBufferUsage.MAP_READ | GPUBufferUsage.COPY_DST,
});

![](img/20cb9720d4b8b89b9cfd6e59e05c448f_61.png)

![](img/20cb9720d4b8b89b9cfd6e59e05c448f_63.png)

![](img/20cb9720d4b8b89b9cfd6e59e05c448f_64.png)

// 4. 复制结果到暂存缓冲区
encoder.copyBufferToBuffer(
    zBuffer, 0,        // 源缓冲区
    stagingBuffer, 0,  // 目标缓冲区
    zBuffer.size
);

![](img/20cb9720d4b8b89b9cfd6e59e05c448f_66.png)

![](img/20cb9720d4b8b89b9cfd6e59e05c448f_68.png)

![](img/20cb9720d4b8b89b9cfd6e59e05c448f_70.png)

// 5. 提交命令到GPU队列执行
device.queue.submit([encoder.finish()]);

![](img/20cb9720d4b8b89b9cfd6e59e05c448f_72.png)

![](img/20cb9720d4b8b89b9cfd6e59e05c448f_74.png)

![](img/20cb9720d4b8b89b9cfd6e59e05c448f_76.png)

// 6. 将暂存缓冲区映射到CPU并读取数据
await stagingBuffer.mapAsync(GPUMapMode.READ);
const zResult = new Float32Array(stagingBuffer.getMappedRange().slice());
stagingBuffer.unmap(); // 使用完毕后取消映射

// 7. 与CPU结果对比验证
let success = true;
for (let i = 0; i < size; i++) {
    if (Math.abs(zResult[i] - cpuZ[i]) > 1e-5) {
        success = false;
        break;
    }
}
console.log(`WebGPU SAXPY ${success ? '成功' : '失败'}`);
```
注意：
*   `dispatchWorkgroups(workgroupCount)` 指定了要调度的工作组数量，相当于CUDA中内核启动的网格大小。
*   WebGPU命令是异步的。`mapAsync` 确保了在数据可用之前，CPU端的读取操作会等待。
*   每个命令编码器在调用 `finish()` 并提交后就不能再使用。

![](img/20cb9720d4b8b89b9cfd6e59e05c448f_78.png)

![](img/20cb9720d4b8b89b9cfd6e59e05c448f_80.png)

![](img/20cb9720d4b8b89b9cfd6e59e05c448f_82.png)

![](img/20cb9720d4b8b89b9cfd6e59e05c448f_84.png)

![](img/20cb9720d4b8b89b9cfd6e59e05c448f_86.png)

## 注意事项与限制 ⚠️

![](img/20cb9720d4b8b89b9cfd6e59e05c448f_88.png)

![](img/20cb9720d4b8b89b9cfd6e59e05c448f_90.png)

![](img/20cb9720d4b8b89b9cfd6e59e05c448f_92.png)

![](img/20cb9720d4b8b89b9cfd6e59e05c448f_93.png)

![](img/20cb9720d4b8b89b9cfd6e59e05c448f_94.png)

![](img/20cb9720d4b8b89b9cfd6e59e05c448f_95.png)

![](img/20cb9720d4b8b89b9cfd6e59e05c448f_97.png)

![](img/20cb9720d4b8b89b9cfd6e59e05c448f_99.png)

![](img/20cb9720d4b8b89b9cfd6e59e05c448f_101.png)

![](img/20cb9720d4b8b89b9cfd6e59e05c448f_102.png)

![](img/20cb9720d4b8b89b9cfd6e59e05c448f_104.png)

![](img/20cb9720d4b8b89b9cfd6e59e05c448f_106.png)

在移植过程中，需要注意WebGPU的一些特性和限制：

![](img/20cb9720d4b8b89b9cfd6e59e05c448f_108.png)

![](img/20cb9720d4b8b89b9cfd6e59e05c448f_110.png)

1.  **工作组数量限制**： WebGPU对每个维度上可调度的工作组数量有上限（例如65535）。对于大规模计算，可能需要使用多维调度（2D/3D dispatch）来规避。
    ```javascript
    // 1D 调度可能超出限制
    // pass.dispatchWorkgroups(100000); // 可能错误
    // 2D 调度
    const xGroups = Math.ceil(size / 256);
    const yGroups = 1;
    pass.dispatchWorkgroups(xGroups, yGroups);
    ```
2.  **资源绑定**： 着色器中声明的每个 `@binding` 都必须在绑定组中有对应的资源，即使它是一个未使用的占位符，否则管线创建会失败。
3.  **内存映射生命周期**： 缓冲区在映射（`mappedAtCreation: true` 或 `mapAsync`）后，必须在使用完CPU端数据后调用 `unmap()`，才能被GPU命令使用或再次映射。
4.  **平台差异**： 不同GPU适配器的限制（如最大工作组大小、存储缓冲区绑定大小）可能不同，可通过 `adapter.limits` 查询并据此调整代码。

## 总结 🎯

![](img/20cb9720d4b8b89b9cfd6e59e05c448f_112.png)

![](img/20cb9720d4b8b89b9cfd6e59e05c448f_114.png)

本节课我们一起学习了将CUDA SAXPY示例移植到WebGPU的完整过程。我们了解到：

*   WebGPU提供了一个跨平台的、可用于通用计算的现代API。
*   其核心流程包括：初始化设备、创建与填充缓冲区、编写WGSL计算着色器、设置管线与绑定组、调度计算以及回读结果。
*   WebGPU与CUDA在概念上有很多对应关系（如缓冲区对应设备内存、工作组对应线程块），但API设计更显式化，特别是资源绑定和管线状态管理。
*   虽然WebGPU的初始化代码比CUDA更冗长，但其结构清晰，并且强大的绑定模型为复杂应用提供了灵活性。

![](img/20cb9720d4b8b89b9cfd6e59e05c448f_116.png)

通过这个从CUDA到WebGPU的映射练习，我们掌握了在Web环境中利用GPU进行高性能计算的基础。这种知识可以应用于浏览器内的机器学习、科学模拟或任何需要并行计算的任务中。