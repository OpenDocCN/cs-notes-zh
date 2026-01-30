# 课程名称：多维数组与图像处理 🖼️

## 课程编号：P16

在本节课中，我们将要学习多维数组，特别是二维数组的概念、语法及其应用。我们将通过一个具体的例子——使用二维数组来表示和操作图像像素——来深入理解这一数据结构。课程内容将涵盖二维数组的声明、遍历、以及如何利用它进行基础的图像处理，例如调整图像亮度和大小。

---

上周，我有一些助教帮忙代课。我离开的原因是妻子出现健康问题，需要住院。她现在情况好转。问题恰好发生在周一、周三和周五。我开玩笑说希望事情能发生在周二或周四。我们目前正在尝试要孩子，经历了一个医疗程序，这引起了一些并发症和疼痛，但她现在好多了。好消息是其他方面进展顺利，但她尚未怀孕。我们正在努力。有学生开玩笑说想让我以他的名字给孩子命名。

有几个简短的公告。本周四有期中考试。学习材料已发布，包含许多练习题和答案。可以通过下载Eclipse项目或访问代码分发网站来练习和测试答案。提高考试成绩的最佳方法是大量练习。考试时会提供语法参考纸。请提前查看。

从管理角度看，请合理安排时间。期中复习会议将于明晚7点到9点在教室举行，由课代表带领，进行练习题讲解和答疑。如果需要特定住宿安排，请今天联系我们。

关于考试范围，期中考试涵盖截至上周五的内容，包括数组。今天讲的多维数组不在期中考试范围内，但属于课程内容，会在期末考试中出现。现在开始今天的讲座。

![](img/cbef116051fdbcaf33915134e3787637_1.png)

---

![](img/cbef116051fdbcaf33915134e3787637_3.png)

## 多维数组简介 📊

上一节我们提到了课程安排，本节中我们来看看什么是多维数组。

多维数组指的是二维或三维数组等。本课程将专注于二维数组。数组是用于存储值的索引集合。二维数组则按行和列组织数据。

为什么需要数组？数组可以避免声明大量单独的变量。例如，无需声明七个变量，只需创建一个包含七个元素的数组。数组还能对数据进行排序和搜索。有时，程序运行前无法确定需要存储多少数据（例如，用户输入游戏场数），数组允许动态处理数据量。

二维数组的声明方式是在类型后使用两对方括号 `[][]`。

```java
int[][] grid = new int[3][5]; // 一个3行5列的整数二维数组
```

第一个索引代表行数，第二个索引代表列数。访问元素需使用两组方括号，例如 `grid[0][0]` 访问左上角元素。

关于数组的动态性：程序启动时，可以根据需要（如学生数量）创建特定大小的数组。但数组一旦创建，其大小就固定了。后续课程会学习可调整大小的 `ArrayList`。

![](img/cbef116051fdbcaf33915134e3787637_5.png)

---

## 遍历二维数组 🔄

![](img/cbef116051fdbcaf33915134e3787637_7.png)

上一节我们介绍了二维数组的声明，本节中我们来看看如何遍历它。

遍历一维数组使用从0到 `array.length - 1` 的循环。遍历二维数组需要在两个维度上循环，通常使用嵌套循环，并以行主序（先遍历行，再遍历每行中的列）进行。

```java
for (int row = 0; row < array2D.length; row++) {
    for (int col = 0; col < array2D[row].length; col++) {
        // 处理 array2D[row][col]
    }
}
```
`array2D.length` 获取行数，`array2D[row].length` 获取指定行的列数。这种写法便于在数组尺寸变化时自动调整。

也可以按列主序遍历，只需交换循环顺序。选择哪种方式取决于具体任务。

![](img/cbef116051fdbcaf33915134e3787637_9.png)

打印二维数组内容时，使用 `Arrays.deepToString(array2D)` 可得到可读的输出。

---

![](img/cbef116051fdbcaf33915134e3787637_11.png)

![](img/cbef116051fdbcaf33915134e3787637_13.png)

## 二维数组的内存表示与锯齿数组 🧩

![](img/cbef116051fdbcaf33915134e3787637_15.png)

从技术上讲，二维数组是“数组的数组”。即使我们将其画成矩形，内存中每一行都是一个独立的一维数组。

![](img/cbef116051fdbcaf33915134e3787637_17.png)

![](img/cbef116051fdbcaf33915134e3787637_19.png)

这引出了“锯齿数组”的概念，即每一行可以有不同长度。

```java
int[][] jagged = new int[3][];
jagged[0] = new int[2];
jagged[1] = new int[4];
jagged[2] = new int[3];
```

![](img/cbef116051fdbcaf33915134e3787637_21.png)

![](img/cbef116051fdbcaf33915134e3787637_23.png)

何时使用锯齿数组？例如，用行代表学生，列代表作业，每个学生提交的作业数量可能不同。帕斯卡三角形也是锯齿数组的一个应用实例，可以避免浪费内存。

![](img/cbef116051fdbcaf33915134e3787637_25.png)

---

## 图像与像素表示 🎨

上一节我们探讨了二维数组的一般概念，本节中我们将其应用于图像处理。

![](img/cbef116051fdbcaf33915134e3787637_27.png)

计算机图像由像素点组成。每个像素的颜色由红（R）、绿（G）、蓝（B）三个值混合而成，每个值范围是0到255。

我们可以使用二维数组来表示这些像素。斯坦福 `acm.graphics` 库中的 `GImage` 类可以加载和显示图像。

```java
GImage image = new GImage("filename.png");
```

![](img/cbef116051fdbcaf33915134e3787637_29.png)

![](img/cbef116051fdbcaf33915134e3787637_31.png)

`GImage` 对象提供了处理像素的方法：
*   `int[][] pixels = image.getPixelArray();` 获取代表像素颜色的二维数组。
*   `image.setPixelArray(pixels);` 将修改后的像素数组设置回图像。

![](img/cbef116051fdbcaf33915134e3787637_33.png)

像素在数组中的位置 `pixels[row][col]` 对应图像上的行和列。注意，这通常与 `(x, y)` 坐标相反，`x` 对应列，`y` 对应行。在代码中，可以暂时忽略 `(x, y)` 的叫法，直接用 `(row, col)` 思考以避免混淆。

---

![](img/cbef116051fdbcaf33915134e3787637_35.png)

![](img/cbef116051fdbcaf33915134e3787637_37.png)

## 图像处理实战：调整亮度 💡

现在，让我们编写代码来修改图像。我们将创建一个方法，使被点击的图像变亮。

思路是：
1.  获取图像的像素数组。
2.  遍历每个像素。
3.  增加该像素的R、G、B值。
4.  将修改后的像素数组设置回图像。

以下是实现步骤的代码框架：

```java
private void brightenImage(GImage image) {
    int[][] pixels = image.getPixelArray();
    for (int row = 0; row < pixels.length; row++) {
        for (int col = 0; col < pixels[row].length; col++) {
            int pixel = pixels[row][col];
            int red = GImage.getRed(pixel);
            int green = GImage.getGreen(pixel);
            int blue = GImage.getBlue(pixel);
            // 增加亮度，但不超过255
            red = Math.min(255, red + 10);
            green = Math.min(255, green + 10);
            blue = Math.min(255, blue + 10);
            // 将新的RGB值重新打包成一个整数像素值
            pixels[row][col] = GImage.createRGBPixel(red, green, blue);
        }
    }
    image.setPixelArray(pixels);
}
```

![](img/cbef116051fdbcaf33915134e3787637_39.png)

![](img/cbef116051fdbcaf33915134e3787637_41.png)

在事件处理中调用：
```java
GObject obj = getElementAt(e.getX(), e.getY());
if (obj instanceof GImage) {
    brightenImage((GImage) obj);
}
```

**注意**：单个像素值是一个整数，它封装了透明度（Alpha）和R、G、B四个通道的信息。因此，我们需要使用 `GImage.getRed`、`getGreen`、`getBlue` 方法来提取颜色分量，修改后再用 `GImage.createRGBPixel` 方法打包回去。

---

## 更多图像处理：颜色滤镜与缩放 🔍

![](img/cbef116051fdbcaf33915134e3787637_43.png)

![](img/cbef116051fdbcaf33915134e3787637_45.png)

我们可以修改算法来实现不同的效果。例如，创建一个“橙色”滤镜，可以增加红色，略微减少蓝色：

```java
private void makeOrange(GImage image) {
    int[][] pixels = image.getPixelArray();
    for (int row = 0; row < pixels.length; row++) {
        for (int col = 0; col < pixels[row].length; col++) {
            int pixel = pixels[row][col];
            int red = GImage.getRed(pixel);
            int green = GImage.getGreen(pixel);
            int blue = GImage.getBlue(pixel);
            red = Math.min(255, red + 20);
            blue = Math.max(0, blue - 10); // 确保不低于0
            pixels[row][col] = GImage.createRGBPixel(red, green, blue);
        }
    }
    image.setPixelArray(pixels);
}
```

![](img/cbef116051fdbcaf33915134e3787637_47.png)

如果想放大图像（例如放大两倍），我们不能直接调整原数组大小。需要创建一个新的、更大的二维数组，然后将原图像的像素值映射到新数组中。

基本思路：
1.  创建一个长宽均为原图两倍的新像素数组 `newPixels`。
2.  遍历原图 `oldPixels` 的每个像素 `(r, c)`。
3.  将该像素的颜色值，填充到新数组 `newPixels` 中 `(2*r, 2*c)`, `(2*r, 2*c+1)`, `(2*r+1, 2*c)`, `(2*r+1, 2*c+1)` 这四个位置。
4.  将 `newPixels` 设置为图像的像素数组。

实现此算法需要仔细处理索引映射，这是作业五中的一个核心任务。

---

## 总结 📝

本节课中我们一起学习了：
1.  **二维数组**的概念、声明和遍历方法。
2.  二维数组在内存中是“数组的数组”，并由此引出**锯齿数组**。
3.  如何利用二维数组表示图像的**像素**。
4.  使用 `GImage` 类进行基础的**图像处理**，包括调整亮度和应用颜色滤镜。
5.  通过创建新数组来实现图像**缩放**的基本思路。

![](img/cbef116051fdbcaf33915134e3787637_49.png)

核心在于掌握嵌套循环遍历二维数组的模式，以及理解像素颜色值的拆分与组合。这些知识是完成图像处理类作业的基础。请结合发布的练习题和作业进行实践，以巩固理解。