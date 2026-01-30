![](img/380946b35847df540656d0e2970d3578_0.png)

# GAMES001-图形学中的数学 - P10：场论初步 - GAMES-Webinar - BV1MF4m1V7e3

## 概述

在本节课中，我们将学习场论初步，包括标量场、向量场、梯度、散度、旋度等概念，并探讨它们在图形学中的应用。

## 标量场

**定义**：标量场是一个定义在空间中的标量函数，例如温度场、密度场等。

**表示**：用 \( F \) 表示，例如 \( F(x, y, z) \)。

**梯度**：标量场的梯度是一个向量，表示函数增长最快的方向。

**公式**： \( \nabla F = \frac{\partial F}{\partial x} \mathbf{i} + \frac{\partial F}{\partial y} \mathbf{j} + \frac{\partial F}{\partial z} \mathbf{k} \)

## 向量场

**定义**：向量场是一个定义在空间中的向量函数，例如速度场、力场等。

**表示**：用 \( \mathbf{F} \) 表示，例如 \( \mathbf{F}(x, y, z) = (F_x, F_y, F_z) \)。

**散度**：向量场的散度是一个标量，表示向量场在空间中的发散程度。

**公式**： \( \nabla \cdot \mathbf{F} = \frac{\partial F_x}{\partial x} + \frac{\partial F_y}{\partial y} + \frac{\partial F_z}{\partial z} \)

**旋度**：向量场的旋度是一个向量，表示向量场在空间中的旋转程度。

**公式**： \( \nabla \times \mathbf{F} = \left( \frac{\partial F_z}{\partial y} - \frac{\partial F_y}{\partial z} \right) \mathbf{i} + \left( \frac{\partial F_x}{\partial z} - \frac{\partial F_z}{\partial x} \right) \mathbf{j} + \left( \frac{\partial F_y}{\partial x} - \frac{\partial F_x}{\partial y} \right) \mathbf{k} \)

## 场论的应用

**高斯定理**：高斯定理描述了向量场的散度与通量之间的关系。

**公式**： \( \iiint_V (\nabla \cdot \mathbf{F}) dV = \iint_S (\mathbf{F} \cdot \mathbf{n}) dS \)

**斯托克斯定理**：斯托克斯定理描述了向量场的旋度与环量之间的关系。

**公式**： \( \iint_S (\nabla \times \mathbf{F}) \cdot \mathbf{n} dS = \oint_C (\mathbf{F} \cdot \mathbf{t}) ds \)

## 总结

![](img/380946b35847df540656d0e2970d3578_2.png)

![](img/380946b35847df540656d0e2970d3578_4.png)

本节课介绍了场论初步的概念，包括标量场、向量场、梯度、散度、旋度等，并探讨了它们在图形学中的应用。这些概念对于理解图形学中的各种算法非常重要。