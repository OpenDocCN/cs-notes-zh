# 002：创建窗口 🪟

![](img/5fb0c3c3ba80d52477b28d97b06dd36d_0.png)

在本节课中，我们将学习如何使用GLFW库创建一个OpenGL窗口。上一节我们介绍了如何在Visual Studio中配置OpenGL环境，本节中我们来看看如何初始化GLFW并创建一个可以交互的窗口。

![](img/5fb0c3c3ba80d52477b28d97b06dd36d_2.png)

## 概述

![](img/5fb0c3c3ba80d52477b28d97b06dd36d_4.png)

![](img/5fb0c3c3ba80d52477b28d97b06dd36d_5.png)

我们将通过以下步骤创建一个基本的OpenGL窗口：
1.  初始化GLFW库。
2.  配置OpenGL版本和核心模式。
3.  创建窗口对象。
4.  将窗口设置为当前上下文。
5.  创建一个渲染循环，让窗口保持打开状态。

## 初始化与终止GLFW

![](img/5fb0c3c3ba80d52477b28d97b06dd36d_7.png)

![](img/5fb0c3c3ba80d52477b28d97b06dd36d_8.png)

使用GLFW的第一步是初始化它，以便我们可以调用其功能函数。初始化成功后，在程序结束前也必须正确地终止它，以释放资源。

以下是初始化GLFW的代码：

![](img/5fb0c3c3ba80d52477b28d97b06dd36d_10.png)

![](img/5fb0c3c3ba80d52477b28d97b06dd36d_11.png)

```cpp
glfwInit();
```

在`main`函数结束时，我们需要添加终止GLFW的代码：

![](img/5fb0c3c3ba80d52477b28d97b06dd36d_13.png)

```cpp
glfwTerminate();
```

![](img/5fb0c3c3ba80d52477b28d97b06dd36d_14.png)

![](img/5fb0c3c3ba80d52477b28d97b06dd36d_15.png)

![](img/5fb0c3c3ba80d52477b28d97b06dd36d_16.png)

## 配置OpenGL版本

GLFW默认不知道我们使用哪个版本的OpenGL，因此需要通过“提示”来告知它。我们使用`glfwWindowHint`函数来设置这些提示，它接受一个提示类型和一个值作为参数。

![](img/5fb0c3c3ba80d52477b28d97b06dd36d_18.png)

例如，我们需要设置主版本号和次版本号。因为我们使用的是OpenGL 3.3，所以主版本号为3，次版本号也为3。

![](img/5fb0c3c3ba80d52477b28d97b06dd36d_20.png)

![](img/5fb0c3c3ba80d52477b28d97b06dd36d_21.png)

```cpp
glfwWindowHint(GLFW_CONTEXT_VERSION_MAJOR, 3);
glfwWindowHint(GLFW_CONTEXT_VERSION_MINOR, 3);
```

![](img/5fb0c3c3ba80d52477b28d97b06dd36d_22.png)

## 选择OpenGL配置文件

![](img/5fb0c3c3ba80d52477b28d97b06dd36d_24.png)

![](img/5fb0c3c3ba80d52477b28d97b06dd36d_25.png)

OpenGL配置文件可以理解为函数集合。主要有两种：
*   **核心模式**：只包含现代函数。
*   **兼容模式**：包含现代函数和已废弃的旧函数。

为了使用现代OpenGL功能，我们选择核心模式。

![](img/5fb0c3c3ba80d52477b28d97b06dd36d_27.png)

```cpp
glfwWindowHint(GLFW_OPENGL_PROFILE, GLFW_OPENGL_CORE_PROFILE);
```

![](img/5fb0c3c3ba80d52477b28d97b06dd36d_28.png)

![](img/5fb0c3c3ba80d52477b28d97b06dd36d_29.png)

![](img/5fb0c3c3ba80d52477b28d97b06dd36d_30.png)

## 创建窗口对象

![](img/5fb0c3c3ba80d52477b28d97b06dd36d_32.png)

配置完成后，我们可以创建窗口了。`GLFWwindow`是GLFW中表示窗口对象的数据类型。

![](img/5fb0c3c3ba80d52477b28d97b06dd36d_34.png)

我们使用`glfwCreateWindow`函数来创建窗口，它需要五个参数：窗口宽度、窗口高度、窗口标题、是否全屏（这里设为`NULL`表示否），以及最后一个不重要的参数（通常也为`NULL`）。

以下是创建窗口的代码示例：

![](img/5fb0c3c3ba80d52477b28d97b06dd36d_36.png)

![](img/5fb0c3c3ba80d52477b28d97b06dd36d_37.png)

```cpp
GLFWwindow* window = glfwCreateWindow(800, 600, “My OpenGL Window”, NULL, NULL);
if (window == NULL) {
    std::cout << “Failed to create GLFW window” << std::endl;
    glfwTerminate();
    return -1;
}
```

![](img/5fb0c3c3ba80d52477b28d97b06dd36d_39.png)

![](img/5fb0c3c3ba80d52477b28d97b06dd36d_41.png)

为了程序的健壮性，我们添加了简单的错误检查，如果窗口创建失败，会打印错误信息并终止GLFW。

## 设置当前上下文

![](img/5fb0c3c3ba80d52477b28d97b06dd36d_43.png)

![](img/5fb0c3c3ba80d52477b28d97b06dd36d_44.png)

创建窗口后，我们需要告诉GLFW将这个窗口设置为当前OpenGL渲染的上下文。上下文是一个抽象的概念，它持有OpenGL的状态和所有数据。

使用以下函数将我们创建的窗口设为当前上下文：

![](img/5fb0c3c3ba80d52477b28d97b06dd36d_46.png)

![](img/5fb0c3c3ba80d52477b28d97b06dd36d_47.png)

```cpp
glfwMakeContextCurrent(window);
```

![](img/5fb0c3c3ba80d52477b28d97b06dd36d_48.png)

## 渲染循环

![](img/5fb0c3c3ba80d52477b28d97b06dd36d_50.png)

如果现在运行程序，窗口会一闪而过立即关闭。这是因为`main`函数执行完毕，程序就退出了。为了让窗口保持打开，我们需要一个循环，在用户主动关闭窗口前不断处理事件和刷新画面。

![](img/5fb0c3c3ba80d52477b28d97b06dd36d_52.png)

这个循环被称为“渲染循环”或“游戏循环”。我们使用`glfwWindowShouldClose`函数来检查窗口是否被要求关闭。

![](img/5fb0c3c3ba80d52477b28d97b06dd36d_53.png)

![](img/5fb0c3c3ba80d52477b28d97b06dd36d_54.png)

```cpp
while (!glfwWindowShouldClose(window)) {
    glfwSwapBuffers(window);
    glfwPollEvents();
}
```
*   `glfwSwapBuffers(window)`：交换前后缓冲区，将渲染好的图像显示到窗口上。
*   `glfwPollEvents()`：处理例如键盘输入、鼠标移动等事件。

最后，在循环结束、退出`main`函数之前，别忘了删除窗口对象。

![](img/5fb0c3c3ba80d52477b28d97b06dd36d_56.png)

![](img/5fb0c3c3ba80d52477b28d97b06dd36d_57.png)

```cpp
glfwDestroyWindow(window);
```

![](img/5fb0c3c3ba80d52477b28d97b06dd36d_59.png)

## 总结

![](img/5fb0c3c3ba80d52477b28d97b06dd36d_60.png)

本节课中我们一起学习了创建一个基本OpenGL窗口的完整流程。我们初始化并配置了GLFW，设置了OpenGL 3.3核心模式，创建了窗口对象并将其设为当前上下文，最后通过一个渲染循环让窗口能够持续显示并响应用户操作。这是所有OpenGL应用程序的基础框架。在下一节中，我们将学习如何在窗口中绘制第一个三角形。