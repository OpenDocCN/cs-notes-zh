# 010：代码回顾 - 第一个OpenGL三角形

![](img/6ab7998c43878633e9219fe63c1d9f40_0.png)

![](img/6ab7998c43878633e9219fe63c1d9f40_0.png)

![](img/6ab7998c43878633e9219fe63c1d9f40_2.png)

在本节课中，我们将对之前编写的代码进行一次回顾。我们将逐段分析代码，确保理解每个独立部分的功能。本次回顾将遵循图形渲染管线的流程，从程序初始化、顶点数据设置、管线创建到最终的绘制循环。

![](img/6ab7998c43878633e9219fe63c1d9f40_4.png)

![](img/6ab7998c43878633e9219fe63c1d9f40_5.png)

![](img/6ab7998c43878633e9219fe63c1d9f40_6.png)

![](img/6ab7998c43878633e9219fe63c1d9f40_7.png)

![](img/6ab7998c43878633e9219fe63c1d9f40_8.png)

![](img/6ab7998c43878633e9219fe63c1d9f40_9.png)

## 全局变量声明

![](img/6ab7998c43878633e9219fe63c1d9f40_11.png)

![](img/6ab7998c43878633e9219fe63c1d9f40_12.png)

首先，我们来看代码顶部的全局变量声明。在入门系列中，为了方便理解，我们暂时使用全局变量来管理状态。这些变量主要涉及SDL窗口设置和OpenGL管线对象。

![](img/6ab7998c43878633e9219fe63c1d9f40_14.png)

![](img/6ab7998c43878633e9219fe63c1d9f40_15.png)

![](img/6ab7998c43878633e9219fe63c1d9f40_16.png)

![](img/6ab7998c43878633e9219fe63c1d9f40_17.png)

![](img/6ab7998c43878633e9219fe63c1d9f40_18.png)

以下是部分关键全局变量：
*   `gGraphicsPipelineProgramID`： 图形管线程序对象的ID。
*   `gVertexArrayObject`： 顶点数组对象（VAO）的ID。
*   `gVertexBufferObject`： 顶点缓冲对象（VBO）的ID。
*   `gVertexPositions`： 存储顶点位置数据的向量。
*   `gVertexShaderSource` 和 `gFragmentShaderSource`： 存储顶点和片段着色器源代码的字符串。

![](img/6ab7998c43878633e9219fe63c1d9f40_20.png)

![](img/6ab7998c43878633e9219fe63c1d9f40_22.png)

## 程序初始化

![](img/6ab7998c43878633e9219fe63c1d9f40_24.png)

![](img/6ab7998c43878633e9219fe63c1d9f40_25.png)

上一节我们介绍了全局变量，本节中我们来看看程序初始化函数 `InitializeProgram`。这个函数负责设置SDL窗口和OpenGL上下文。

![](img/6ab7998c43878633e9219fe63c1d9f40_27.png)

以下是初始化程序的主要步骤：
1.  初始化SDL的视频子系统。
2.  设置OpenGL版本为4.1，并选择核心模式（Core Profile），以移除旧版兼容功能。
3.  配置深度缓冲区等渲染设置。
4.  创建SDL窗口并检查是否成功。
5.  创建OpenGL上下文。上下文是一个封装了OpenGL状态的大对象。
6.  使用GLEW库加载所有OpenGL函数指针。

![](img/6ab7998c43878633e9219fe63c1d9f40_29.png)

![](img/6ab7998c43878633e9219fe63c1d9f40_31.png)

## 顶点数据规范

![](img/6ab7998c43878633e9219fe63c1d9f40_33.png)

![](img/6ab7998c43878633e9219fe63c1d9f40_34.png)

![](img/6ab7998c43878633e9219fe63c1d9f40_36.png)

初始化窗口和上下文后，下一步是准备要渲染的几何数据。这是 `VertexSpecification` 函数的工作。

![](img/6ab7998c43878633e9219fe63c1d9f40_38.png)

![](img/6ab7998c43878633e9219fe63c1d9f40_39.png)

![](img/6ab7998c43878633e9219fe63c1d9f40_40.png)

![](img/6ab7998c43878633e9219fe63c1d9f40_42.png)

该函数主要完成以下任务：
1.  **定义顶点数据**： 将三角形的三个顶点坐标（X, Y, Z）存入 `gVertexPositions` 向量。
2.  **生成顶点数组对象（VAO）**： VAO用于描述顶点数据在缓冲区中的布局。调用 `glGenVertexArrays` 生成。
3.  **生成顶点缓冲对象（VBO）**： VBO用于在GPU上存储顶点数据。调用 `glGenBuffers` 生成。
4.  **绑定并传输数据**： 绑定VAO和VBO，然后使用 `glBufferData` 将CPU上的顶点数据复制到GPU的VBO中。需要计算数据的总字节大小：`sizeof(float) * 顶点数量 * 每个顶点的分量数`。
5.  **设置顶点属性指针**： 通过 `glVertexAttribPointer` 告诉OpenGL如何解析VBO中的数据。例如，我们的数据是连续的浮点数，每3个值（X, Y, Z）构成一个顶点属性（位置）。
6.  **启用顶点属性**： 调用 `glEnableVertexAttribArray` 启用对应的顶点属性位置。
7.  **清理状态**： 解绑VAO和VBO，避免意外修改。

![](img/6ab7998c43878633e9219fe63c1d9f40_43.png)

## 创建图形管线

![](img/6ab7998c43878633e9219fe63c1d9f40_45.png)

![](img/6ab7998c43878633e9219fe63c1d9f40_46.png)

![](img/6ab7998c43878633e9219fe63c1d9f40_47.png)

![](img/6ab7998c43878633e9219fe63c1d9f40_48.png)

![](img/6ab7998c43878633e9219fe63c1d9f40_50.png)

![](img/6ab7998c43878633e9219fe63c1d9f40_52.png)

![](img/6ab7998c43878633e9219fe63c1d9f40_54.png)

设置好顶点数据后，我们需要定义如何处理这些数据，这就是创建图形管线。`CreateGraphicsPipeline` 函数负责编译、链接着色器，最终生成一个可用的着色器程序。

![](img/6ab7998c43878633e9219fe63c1d9f40_56.png)

![](img/6ab7998c43878633e9219fe63c1d9f40_57.png)

![](img/6ab7998c43878633e9219fe63c1d9f40_59.png)

![](img/6ab7998c43878633e9219fe63c1d9f40_61.png)

以下是创建图形管线的过程：
1.  **编译着色器**： 分别编译顶点着色器（`gVertexShaderSource`）和片段着色器（`gFragmentShaderSource`）。`CompileShader` 函数内部会创建着色器对象、附加源代码并进行编译。
2.  **错误检查**： 在 `CompileShader` 函数中，包含了对编译是否成功的检查。如果着色器代码有语法错误（如拼写错误、缺少分号），可以通过日志获取错误信息，这对调试至关重要。
3.  **创建着色器程序**： 调用 `glCreateProgram` 创建一个程序对象。
4.  **附加并链接**： 将编译好的顶点和片段着色器附加到程序对象上，然后调用 `glLinkProgram` 进行链接。链接成功后，就得到了一个完整的图形管线程序 `gGraphicsPipelineProgramID`。

![](img/6ab7998c43878633e9219fe63c1d9f40_63.png)

![](img/6ab7998c43878633e9219fe63c1d9f40_64.png)

![](img/6ab7998c43878633e9219fe63c1d9f40_66.png)

![](img/6ab7998c43878633e9219fe63c1d9f40_68.png)

## 主渲染循环

一切准备就绪后，程序进入主渲染循环。这是实时图形应用的核心，通常遵循“处理输入 -> 更新状态 -> 绘制 -> 呈现”的模式。

![](img/6ab7998c43878633e9219fe63c1d9f40_70.png)

![](img/6ab7998c43878633e9219fe63c1d9f40_72.png)

![](img/6ab7998c43878633e9219fe63c1d9f40_73.png)

主循环的结构如下：
1.  **处理输入**： `ProcessInput` 函数轮询SDL事件（如键盘、鼠标事件），并更新程序状态（例如，设置退出标志 `gQuit`）。
2.  **预绘制设置**： `PreDraw` 函数设置OpenGL的渲染状态。这通常包括：
    *   使用 `glUseProgram` 激活我们的图形管线程序。
    *   设置视口（`glViewport`）。
    *   用特定颜色清除颜色缓冲区和深度缓冲区（`glClear`）。
3.  **执行绘制**： `Draw` 函数发出实际的绘制命令。
    *   绑定我们之前设置的VAO（`glBindVertexArray`），告诉OpenGL顶点数据的格式。
    *   调用 `glDrawArrays` 函数。这个函数是启动图形管线的关键，它指示OpenGL使用当前绑定的VAO和激活的着色器程序，从第0个顶点开始，绘制3个顶点（即一个三角形）。
    *   绘制完成后，可以选择解绑VAO和程序对象以进行清理。
4.  **交换缓冲区**： 调用 `SDL_GL_SwapWindow`。由于SDL使用双缓冲机制，`glDrawArrays` 的绘制结果先提交到后缓冲区（Back Buffer），此函数将后缓冲区的内容交换到前缓冲区（Front Buffer）显示在屏幕上，从而避免画面撕裂。

![](img/6ab7998c43878633e9219fe63c1d9f40_75.png)

## 总结

![](img/6ab7998c43878633e9219fe63c1d9f40_77.png)

![](img/6ab7998c43878633e9219fe63c1d9f40_78.png)

本节课中我们一起回顾了创建第一个OpenGL三角形的完整代码流程。我们按照图形渲染管线的顺序，逐步分析了程序初始化、顶点数据规范、着色器程序创建以及主渲染循环的各个步骤。理解这个基础流程对于后续学习更复杂的OpenGL概念至关重要。在接下来的课程中，我们将以此为基础，添加更多功能。