OpenGL教程：P6：着色器 🎨

在本节课中，我们将深入学习着色器。我们将了解着色器如何作为在GPU上运行的特殊函数，学习GLSL语言的基本结构，并实践如何为每个顶点添加颜色属性，实现从顶点着色器到片段着色器的数据传递。

---

在上一节中，我们为着色器程序、VAO、VBO和EBO创建了一些自定义类。本节中，我们来看看着色器本身。你可以将着色器理解为在GPU上运行的函数。由于它们类似于函数，因此可以接收输入并产生输出。

让我们通过查看默认的顶点着色器来开始学习。初看之下，你可能会认为这是C语言代码，但它实际上是OpenGL的着色语言，即GLSL，其语法与C语言相似。

第一行指定了我们使用的GLSL版本。由于我们使用的是OpenGL 3.3，因此需要对应使用GLSL 330。第二行使用 `layout (location = 0)` 声明了一个输入变量 `aPos`。`layout` 帮助OpenGL解读接收到的顶点数据。在这里，我们声明在第0个布局位置有一个用于存储位置信息的向量数据类型。

对于主函数，我们简单地将 `gl_Position` 赋值为一个四维向量，其中包含我们的位置坐标，以及一个目前可以忽略的第四维任意值。OpenGL能识别关键字 `gl_Position`，并知道将其用作顶点的位置。你可以将此着色器理解为输出了 `gl_Position`，尽管它并未显式地这样做。

另一方面，片段着色器在第二行显式声明它输出一个四维向量 `FragColor`。在主函数中，我们简单地赋予它一个RGBA格式的颜色，用于所有顶点。

但是，与其让所有点共享同一种颜色，不如让我们为每个顶点赋予其专属颜色。

以下是实现此目标的具体步骤：

首先，在顶点数组 `vertices` 中，在每个位置坐标后写入RGB值。

接着，在顶点着色器中添加第二个布局，使用 `layout (location = 1)` 来接收一个名为 `aColor` 的向量。

由于片段着色器是负责处理颜色的，我们需要将颜色从顶点着色器输出到片段着色器。为此，我在顶点着色器中输出一个名为 `color` 的向量，并在主函数中使其等于从顶点数组导入的 `aColor`。

现在，在片段着色器中，我输入一个完全同名的向量 `color`。为输入和输出赋予相同的名称至关重要，否则OpenGL将无法在它们之间建立链接。

此着色器的最后一步是使 `FragColor` 等于 `color`，因为这就是我们要输出的内容。

接下来，我们需要配置顶点属性指针。但在开始之前，必须先修改VAO类中的一个函数。

让我们将 `linkVBO` 函数改为 `linkAttrib`，并添加四个变量：`numComponents`（组件数量）、`type`（数据类型）、`stride`（步长）和 `offset`（偏移量）。

在VAO的CPP文件中进行同样的更改，并将这些新变量作为参数添加到 `glVertexAttribPointer` 函数调用中，具体操作如下方代码所示：

```cpp
void VAO::linkAttrib(VBO& VBO, GLuint layout, GLuint numComponents, GLenum type, GLsizeiptr stride, void* offset) {
    VBO.Bind();
    glVertexAttribPointer(layout, numComponents, type, GL_FALSE, stride, offset);
    glEnableVertexAttribArray(layout);
    VBO.Unbind();
}
```

我们向着色器发送的是一个包含大量字节的数组。为了让OpenGL知道如何正确解析这些数据，我们必须通过 `glVertexAttribPointer` 函数明确告知它数据的组织方式，包括每个属性有多少个分量、数据类型是什么、以及数据在数组中的间隔（步长）和起始位置（偏移量）。

![](img/43d252a872fac42decbc3ba4b3771d23_1.png)

---

![](img/43d252a872fac42decbc3ba4b3771d23_3.png)

本节课中，我们一起学习了着色器作为GPU函数的基本概念，探索了GLSL语言的结构，并实践了为顶点添加颜色属性以及通过同名变量在着色器阶段间传递数据的方法。我们还修改了VAO类以支持更灵活的顶点属性链接。理解这些数据如何被组织和传递，是掌握现代OpenGL渲染流程的关键一步。