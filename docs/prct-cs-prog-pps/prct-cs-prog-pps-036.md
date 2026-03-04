# 计算机科学：以目的为导向的编程（Java）：36：点电荷模拟

![](img/51c6dfd71cbd845032f01bc74a5e8b71_0.png)

## 概述
在本节课中，我们将学习如何实现一个表示点电荷的抽象数据类型（ADT）。我们将从理解点电荷的物理概念开始，然后逐步实现一个`Charge`类，并编写客户端程序来可视化和操作点电荷。通过这个过程，你将掌握如何创建自定义数据类型，并利用它们来模拟现实世界中的物理现象。

---

## 点电荷的抽象数据类型

上一节我们介绍了抽象数据类型的概念。本节中，我们来看看如何为一个具体的物理概念——点电荷——定义ADT。

点电荷是一个理想化的粒子模型，它带有电荷。我们将创建一个抽象数据类型，允许Java程序操作点电荷对象。

该数据类型的值包括：
*   **位置**：一个由两个`double`值（X, Y）表示的坐标。
*   **电荷量**：一个`double`值，表示电学上的电荷。

以下是该ADT的操作：
*   **构造函数**：根据给定的位置（X, Y）和电荷量创建一个新的点电荷。
*   **`potentialAt`方法**：接收另一个点（X, Y）作为参数，返回由该点电荷在该点产生的电势（一个`double`值）。
*   **`toString`方法**：返回该点电荷的字符串表示形式，便于调试和输出。

---

## 物理背景与公式

为了给这个抽象数据类型注入实际意义，我们需要了解一点物理背景。这不是物理课，我们只关注核心概念。

电势用于衡量点电荷对其周围空间的影响。它随电荷量的增加而线性增加，并随距离的增加而反比例减小。在二维空间中，电势与距离成反比；在三维空间中，则与距离的平方成反比。

数学上，如果一个点电荷位于点 (Rx, Ry)，电荷量为 Q，我们想计算它在另一点 (X, Y) 产生的电势 Vc(X, Y)。设 R 为两点之间的距离。

电势的计算公式为：
**Vc(X, Y) = (8.99 × 10^9) * Q / R**

其中，8.99 × 10^9 是一个物理常数（库仑常数）。当存在多个电荷时，某一点的总电势等于各个电荷在该点产生的电势之和。这个定律与万有引力定律（三维空间中的平方反比律）类似。

---

## 实现`Charge`类

现在，我们开始实现`Charge`类。最佳实践是从一个测试客户端开始，这有助于在编写代码前明确期望的行为。

### 测试客户端
以下是`Charge`类的一个简单测试客户端。它测试了构造函数和两个方法。

```java
public static void main(String[] args) {
    Charge c = new Charge(0.51, 0.63, 21.3);
    StdOut.println(c);
    double v = c.potentialAt(0.21, 0.71);
    StdOut.println(v);
}
```
我们手动计算一下预期结果：两点间X方向距离为0.3，Y方向距离为0.4，因此距离 R = sqrt(0.3² + 0.4²) = 0.5。电势 V = (8.99e9 * 21.3) / 0.5 ≈ 3.6e11。运行代码应首先打印电荷信息，然后打印此电势值。

### 实例变量
实例变量定义了数据类型的值。我们使用`private`修饰符来隐藏实现细节，确保数据类型的抽象性。使用`final`修饰符表示对象在构造后不可变，这符合点电荷在模拟中通常不变的特性。

```java
public class Charge {
    private final double rx, ry; // 位置
    private final double q;      // 电荷量
    // ... 构造函数和方法
}
```
每个`Charge`对象都拥有自己的一组实例变量值。

### 构造函数
构造函数用于创建和初始化新对象。它接收客户端提供的参数，并将其赋值给实例变量。

```java
public Charge(double x0, double y0, double q0) {
    rx = x0;
    ry = y0;
    q = q0;
}
```
客户端使用`new`关键字调用构造函数，系统会创建一个新对象，根据代码设置其值，并返回对该对象的引用。

### 方法实现
方法实现了ADT的操作。注意，在实例方法中，我们可以直接引用实例变量（如`rx`, `ry`, `q`），这些值属于调用该方法的对象。

**`potentialAt`方法**根据公式计算电势：
```java
public double potentialAt(double x, double y) {
    double k = 8.99e09;
    double dx = x - rx;
    double dy = y - ry;
    return k * q / Math.sqrt(dx*dx + dy*dy);
}
```

**`toString`方法**提供对象的字符串表示：
```java
public String toString() {
    return q + " at (" + rx + ", " + ry + ")";
}
```

至此，我们完成了`Charge`类的完整实现，包括实例变量、构造函数、方法和测试客户端。

---

## 可视化电势：一个更复杂的客户端

现在我们已经创建了`Charge`数据类型，让我们来看一个更有趣的客户端，尝试可视化单位正方形区域内各点的电势。

### 辅助方法
首先，我们需要两个静态辅助方法。

1.  **读取电荷数组**：从标准输入读取多个电荷的位置和电荷量，并返回一个`Charge`数组。
    ```java
    public static Charge[] readCharges() {
        int n = StdIn.readInt();
        Charge[] a = new Charge[n];
        for (int i = 0; i < n; i++) {
            double x = StdIn.readDouble();
            double y = StdIn.readDouble();
            double q = StdIn.readDouble();
            a[i] = new Charge(x, y, q);
        }
        return a;
    }
    ```
2.  **电势转颜色**：将一个电势值`V`转换为0-255之间的灰度值。
    ```java
    public static Color toColor(double v) {
        int gray = (int) (128 + v / 2.0e10);
        if (gray < 0) gray = 0;
        if (gray > 255) gray = 255;
        return new Color(gray, gray, gray);
    }
    ```

### 主可视化客户端
利用上述辅助方法，我们可以编写一个客户端来可视化单位正方形内的电势分布。

```java
public static void main(String[] args) {
    Charge[] a = readCharges(); // 读取电荷
    int size = 800;
    Picture pic = new Picture(size, size);
    for (int col = 0; col < size; col++) {
        for (int row = 0; row < size; row++) {
            double x = (double) col / size;
            double y = (double) row / size;
            double v = 0.0;
            for (int i = 0; i < a.length; i++) // 计算总电势
                v += a[i].potentialAt(x, y);
            Color c = toColor(v); // 转换为颜色
            pic.set(col, size - 1 - row, c); // 设置像素（翻转Y轴）
        }
    }
    pic.show();
}
```
给定一个包含三个电荷的输入文件，运行此程序将生成一幅灰度图像，其中亮度表示电势高低。通过修改输入数据，我们可以轻松研究不同电荷配置下的电势分布，例如包含正负电荷的九电荷系统。

### 进阶可视化
通过简单的代码修改，我们可以实现更丰富的交互和显示效果：
*   **动态电荷**：移除实例变量的`final`修饰符，并添加代码跟踪鼠标，可以实现电荷移动的交互式模拟。
*   **等势线**：修改`toColor`方法，使颜色值不连续变化（例如乘以37后取模），可以直观地显示出等势线，这是一种非常简洁的计算机科学可视化方法。

---

![](img/51c6dfd71cbd845032f01bc74a5e8b71_2.png)

![](img/51c6dfd71cbd845032f01bc74a5e8b71_4.png)

## 总结
本节课中，我们一起学习了如何为点电荷创建和使用抽象数据类型。我们从定义ADT的API开始，基于物理公式实现了`Charge`类，并编写了测试客户端。随后，我们构建了更复杂的客户端程序，实现了电势分布的可视化，甚至通过简单技巧展示了等势线。整个过程的核心在于，我们能够定义自己的数据类型，并编写直接操作这些类型对象的程序，从而简洁有力地模拟和探索物理现象。