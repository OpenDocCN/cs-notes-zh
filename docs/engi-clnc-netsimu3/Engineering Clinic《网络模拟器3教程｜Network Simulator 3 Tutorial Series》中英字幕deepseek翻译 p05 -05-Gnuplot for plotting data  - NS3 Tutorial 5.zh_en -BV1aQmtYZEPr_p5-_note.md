# NS3教程系列：05：使用Gnuplot绘制数据 📊

在本节课中，我们将学习一个名为Gnuplot的强大工具。Gnuplot是一个用于绘制二维和三维图形的工具，它可以通过简单的代码生成高质量的图表。研究人员和学生在发表论文时，图表的专业性是重要的评判标准之一。虽然我们常用Microsoft Excel等电子表格软件绘图，但Gnuplot作为一个已有三十多年历史的工具，在全球范围内提供了强大的绘图解决方案。

## 安装Gnuplot 🛠️

首先，我们需要安装Gnuplot。在基于Debian的系统（如Ubuntu）上，安装过程非常简单。

以下是安装命令：
```bash
sudo apt install gnuplot
```

安装完成后，您可以在终端输入`gnuplot`命令来启动它。如果已经安装，系统会显示Gnuplot的终端界面，等待您输入命令。

![](img/950d4ea74303d5551c06c9a9a347574b_1.png)

![](img/950d4ea74303d5551c06c9a9a347574b_3.png)

## Gnuplot基础功能

![](img/950d4ea74303d5551c06c9a9a347574b_5.png)

![](img/950d4ea74303d5551c06c9a9a347574b_7.png)

Gnuplot不仅能处理数据文件，还能直接绘制数学函数。例如，在Gnuplot终端中输入以下命令可以绘制正弦函数：
```gnuplot
plot sin(x)
```
这里，`x`是Gnuplot默认识别的变量。同样，您可以绘制余弦函数`cos(x)`或线性方程`4*x + 10`。

![](img/950d4ea74303d5551c06c9a9a347574b_9.png)

## 准备数据文件与脚本文件 📁

![](img/950d4ea74303d5551c06c9a9a347574b_11.png)

为了演示如何使用数据文件绘图，我们需要创建两个文件：一个数据文件和一个Gnuplot脚本文件。

1.  **数据文件 (`my_data.txt`)**：此文件包含我们要绘制的数据。我们创建一个包含四列数据的示例文件：
    *   第一列：可以代表时间或序号（例如：1, 2, 3, ...）。
    *   第二列：代表车辆速度（单位：公里/小时）。
    *   第三列：代表驾驶员年龄。
    *   第四列：代表驾驶员薪水。

    文件内容示例如下：
    ```
    1 34.5 45 2000
    2 38.7 34 24000
    3 32.3 22 34000
    4 41.5 18 43000
    5 35.6 24 2304
    6 24.5 26 562345
    7 56.7 67 670987
    8 62.3 54 45678
    9 65.4 27 3200123
    10 70.1 33 89989
    ```

2.  **脚本文件 (`my_gnu_code.plt`)**：这个文件包含一系列Gnuplot命令，用于控制图形的生成方式。

## 编写第一个绘图脚本 ✍️

现在，让我们编写一个基本的Gnuplot脚本来绘制数据。

在`my_gnu_code.plt`文件中输入以下内容：
```gnuplot
# 设置输出为PDF格式
set terminal pdf
# 设置输出文件名
set output "pred.pdf"
# 设置图表标题
set title "Driver‘s Data"
# 设置X轴标签
set xlabel "Number of Days"
# 设置Y轴标签
set ylabel "Driver‘s Information"
# 绘制数据：使用数据文件的第一列作为X轴，第二列作为Y轴，用线条连接
plot "my_data.txt" using 1:2 with lines title "Speed in kmph"
```

![](img/950d4ea74303d5551c06c9a9a347574b_13.png)

![](img/950d4ea74303d5551c06c9a9a347574b_14.png)

![](img/950d4ea74303d5551c06c9a9a347574b_16.png)

![](img/950d4ea74303d5551c06c9a9a347574b_18.png)

保存文件后，在终端运行以下命令来生成图表：
```bash
gnuplot my_gnu_code.plt
```
命令执行成功后，会在当前目录生成一个名为`pred.pdf`的PDF文件，其中包含了根据第一列和第二列数据绘制的折线图。

![](img/950d4ea74303d5551c06c9a9a347574b_20.png)

## 在同一图表中添加多条曲线 📈

![](img/950d4ea74303d5551c06c9a9a347574b_22.png)

![](img/950d4ea74303d5551c06c9a9a347574b_24.png)

![](img/950d4ea74303d5551c06c9a9a347574b_26.png)

![](img/950d4ea74303d5551c06c9a9a347574b_28.png)

上一节我们绘制了单条曲线，本节中我们来看看如何在同一张图中叠加多条曲线，以便进行对比。

![](img/950d4ea74303d5551c06c9a9a347574b_30.png)

![](img/950d4ea74303d5551c06c9a9a347574b_32.png)

![](img/950d4ea74303d5551c06c9a9a347574b_34.png)

修改`my_gnu_code.plt`文件，在`plot`命令后添加更多数据系列，用逗号分隔：
```gnuplot
set terminal pdf
set output "pred.pdf"
set title "Driver‘s Data"
set xlabel "Number of Days"
set ylabel "Driver‘s Information"
# 绘制多条曲线：速度（线条）和年龄（带点的线条）
plot "my_data.txt" using 1:2 with lines lw 2 title "Speed in kmph", \
     "my_data.txt" using 1:3 with linespoints title "Age"
```
*   `using 1:3` 表示使用第一列作为X轴，第三列作为Y轴。
*   `with linespoints` 表示图形同时包含线条和数据点。
*   `lw 2` 是 `linewidth 2` 的缩写，用于增加第一条曲线的线条粗细。

![](img/950d4ea74303d5551c06c9a9a347574b_36.png)

![](img/950d4ea74303d5551c06c9a9a347574b_38.png)

![](img/950d4ea74303d5551c06c9a9a347574b_40.png)

再次运行`gnuplot my_gnucode.plt`命令，生成的PDF中将同时显示速度和年龄两条曲线。

![](img/950d4ea74303d5551c06c9a9a347574b_42.png)

![](img/950d4ea74303d5551c06c9a9a347574b_44.png)

## 探索不同的绘图样式 🎨

![](img/950d4ea74303d5551c06c9a9a347574b_46.png)

Gnuplot支持多种绘图样式。以下是几种常见的样式示例，您可以替换`with`后面的关键词来尝试：

![](img/950d4ea74303d5551c06c9a9a347574b_48.png)

1.  **`with impulses`**：绘制脉冲图（垂直线）。
    ```gnuplot
    plot "my_data.txt" using 1:2 with impulses title "Speed"
    ```
2.  **`with points`**：仅绘制数据点，不连接线条。
    ```gnuplot
    plot "my_data.txt" using 1:3 with points title "Age"
    ```

![](img/950d4ea74303d5551c06c9a9a347574b_50.png)

## 生成PNG格式图像并添加参考线 🖼️

![](img/950d4ea74303d5551c06c9a9a347574b_52.png)

![](img/950d4ea74303d5551c06c9a9a347574b_54.png)

有时我们需要生成图像文件（如PNG）用于网页或演示文稿。此外，在图表中添加参考线（如平均线、最低标准线）可以更清晰地传达信息。

![](img/950d4ea74303d5551c06c9a9a347574b_56.png)

![](img/950d4ea74303d5551c06c9a9a347574b_58.png)

以下脚本将生成一个PNG图像，并在图表中添加一条代表最低薪水的水平参考线：
```gnuplot
# 设置输出为PNG格式，并指定图像尺寸为600x400像素
set terminal png size 600,400
# 设置输出文件名
set output "salary.png"
# 设置图表标题和坐标轴标签
set title "Driver‘s Data"
set xlabel "Number of Drivers"
set ylabel "Driver‘s Salary"
# 绘制数据：薪水曲线，并添加一条Y=20000的水平参考线
plot "my_data.txt" using 1:4 with linespoints lw 2 title "Salary in rupees", \
     20000 title "Minimum Salary"
```
运行此脚本后，将生成`salary.png`文件。图中的水平线直观地标出了20000的最低薪水标准，我们可以快速看出有哪些数据点位于此标准之下。

![](img/950d4ea74303d5551c06c9a9a347574b_60.png)

![](img/950d4ea74303d5551c06c9a9a347574b_62.png)

![](img/950d4ea74303d5551c06c9a9a347574b_64.png)

## 总结 📝

![](img/950d4ea74303d5551c06c9a9a347574b_66.png)

![](img/950d4ea74303d5551c06c9a9a347574b_68.png)

本节课中我们一起学习了Gnuplot的基础使用方法。我们了解了如何安装Gnuplot，如何准备数据文件和编写绘图脚本，以及如何生成包含多条曲线、不同样式和参考线的PDF与PNG格式图表。Gnuplot功能强大且灵活，是进行科研数据可视化的优秀工具。掌握这些基础后，您可以进一步探索其绘制直方图、三维曲面图等高级功能。