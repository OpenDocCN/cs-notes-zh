# 9.3\. 数值积分

> 原文：[`introcs.cs.princeton.edu/java/93integration`](https://introcs.cs.princeton.edu/java/93integration)
> 
> 译者：[飞龙](https://github.com/wizardforcel)
> 
> 协议：[CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/)


本节正在大力施工中。

**中点法则。** 目标：给定一个变量的连续函数 f(x)，计算从 a 到 b 的区间上的∫ f(x) dx。通过 M = (b-a) * f(c)来估计积分，其中 c = (a + b)/2。

**梯形法则。** 目标：给定一个变量的连续函数 f(x)，计算从 a 到 b 的区间上的∫ f(x) dx。TrapezoidalRule.java 使用梯形法则数值积分一个变量的函数。我们可以使用公式 T = (b-a)/2 (f(a) + f(b))来估计从 a 到 b 的 f(x)的积分。将区间从 a 到 b 分成 N 个等距间隔的子区间（并合并公共项），我们得到公式：

![梯形法则](img/1c6be0ef112dd88d0717512203980305.png)

其中区间[a, b]被分成 N 个均匀大小的子区间，h = (b - a) / N。在某些技术条件下，如果 N 很大，则上述公式是积分的一个很好的估计。

**辛普森法则。** 梯形法则在实践中很少用于积分。对于光滑的 f，中点法则的精度大约是梯形法则的两倍，并且误差具有不同的符号。通过结合这两个表达式，我们得到 f 的更准确的估计：S = 2/3*M + 1/3*T。这种组合被称为辛普森 1/3 法则。S = (b-a)/6 (f(a) + 4f(c) + f(b))，其中 c = (a + b)/2。将区间从 a 到 b 分成 N 个等距间隔的子区间（并合并公共项），我们得到公式：

![辛普森 1/3 法则](img/c84638e04ce5452df5a21b32d701dc10.png)

其中区间[a, b]被分成 N 个均匀大小的子区间，h = (b - a) / (N - 1)，而 2/3 和 4/3 的系数在内部交替。这里有一些关于数值积分的不错的[动画](http://www.ecs.fullerton.edu/~mathews/a2001/Animations/Quadrature/)。在某些技术条件下，如果 N 很大，则上述公式是积分的一个很好的估计。程序 SimpsonsRule.java 从 a = 0 到 b = 2 数值积分 x⁴ log (x + sqrt(x² + 1))。

**程序组织。** 为了编写可重复使用的积分例程，我们希望能够创建一个类`TrapezoidalRule`并传递一个要被积分的任意连续函数。实现这一目标的一种方法是声明一个连续函数的接口，该接口具有一个名为`eval`的方法，该方法接受一个实数参数 x 并返回 f(x)。

```java
public interface ContinuousFunction {
    public double eval(double x);
}

```

然后，我们可以实现误差函数为

```java
public class NormalPDF implements ContinuousFunction {
    private double mu;
    private double sigma;
    public NormalPDF(double mu, double sigma) {
        this.mu = mu;
        this.sigma = sigma;
    }
    public double eval(double x) {
        return Math.exp(- x * x / 2) / Math.sqrt(2 * Math.PI);  // mu, sigma
    }
}

```

**自适应积分。** Matlab 函数`quad`使用外推辛普森法则的自适应积分。[参考第六章，Cleve Moler。]

```java
Q1 = h/6  (f(a) + 4f(c) + f(b)), where c = (a + b)/2  [Simpson]
Q2 = h/12 (f(a) + 4f(d) + 2f(c) + 4f(e) + f(b)),      [Simpson over two subintervals]
     where d = (a + c)/2, e = (c + b)/2

Q  = Q2 + (Q2 - Q1) / 15         [ 6th order Newton-Cotes / Weddle's Rule]

```

梯形法则通过将区间分成固定数量的等距子区间，并通过梯形逼近每个子区间中的面积来近似曲线下的面积。通过使用可变数量的子区间并根据曲线的形状选择它们，我们通常可以获得更精细的近似。在*自适应积分*中，我们估计从 a 到 b 曲线下的面积两次，一次使用 Q1，一次使用 Q2。如果这两个估计足够接近，我们使用 Q = Q2 + (Q2 - Q1)/ 15 来估计面积。否则，我们将区间分成从 a 到 c 和从 c 到 b 的两个相等子区间，其中 c 是中点(a + b) / 2。我们计算每个部分的面积（递归使用自适应积分）并将结果相加。程序 AdaptiveQuadrature.java 实现了这种策略。

如果我们小心一些，可以在一次迭代到下一次迭代中保存函数评估，并且每次递归调用只需两次函数评估。（见练习。）

当积分 1 / (3x - 1) 从 x = 0 到 1 时，我们的方法失败得很惨。积分具有非奇异性，我们的函数将陷入无限循环。一个工业强度的实现应该诊断这种情况并报告适当的错误信息。

**蒙特卡罗积分。** 基于大数定律的理论。通过拒绝方法估计圆的面积。飞镖板。在几杯啤酒后在爱尔兰酒吧扔飞镖... 程序 Dartboard.java 读取一个命令行整数 N，将 N 个均匀分布在单位盒中的飞镖扔出，并绘制结果。下面的图片展示了 N = 1,000、10,000 和 100,000 的样本结果。

| ![蒙特卡罗积分](img/ccb7e54882b182a15db70ade2c0acad4.png) | ![蒙特卡罗积分](img/c0a8d498be085823dc397129f080f1c5.png) | ![蒙特卡罗积分](img/8d3426c7edc481555faa20c43c842118.png) |
| --- | --- | --- |

另一种观点：2D 蒙特卡洛积分 f(x, y) = 1，如果 x² + y² ≤ 1。展示直方图 - 标准差正态分布的图。

为了估计 f 在多维体积 V 上的积分，我们在体积中随机选择 N 个点 x[1]、x[2]、...、x[N]。我们对积分的估计是随机点落在 f 以下的比例乘以体积 = V <f>，其中

```java
<f> =  1/N * (f(x1) + ... + f(x2))
<f2> = 1/N * (f2(x1) + ... + f2(x2))

```

蒙特卡罗积分的基本定理断言，f 在 V 上的积分等于 V <f> +- V sqrt((<f²> - <f>²) / N)。关键观察是误差随着 1 / sqrt(N) 增加。这意味着你必须将模拟次数增加四倍才能将你的近似精度提高一倍。然而，这与维度无关！在一到两个维度中不具竞争力，但在更高维度中表现出色。

*圆环的质心。* 举个例子（摘自《数值食谱》第 221 页），假设我们想要估计一个圆环和两个平面的交点的重量和质心，由满足点 (x, y, z) 的定义

```java
z2 + (sqrt(x2 + y2) - 3)2 ≤ 1
x ≥ 1
y ≥ -3

```

我们必须计算积分 f(x, y, z) = ρ，fx = xρ，fy = yρ 和 fz = zρ。质心然后是 (f[x]/f, f[y]/f, f[z]/f)。为了从圆环中均匀采样点 (x, y, z)，我们使用拒绝方法。在这种情况下，圆环被包含在矩形框内，其中 1 ≤ x ≤ 4，-3 ≤ y ≤ 4，-1 ≤ z ≤ 1。程序 Torus.java 接受一个命令行参数 N，并使用 N 个样本点计算这些量。

**高斯 cdf。** 通过从高斯分布生成随机数并记录小于 z 的值的比例来估计高斯 cdf Phi(z)。这是重要性抽样的一个例子。注意：无法在负无穷到正无穷之间均匀采样。

#### 练习

1.  对 f(x) = x^x 从 x = 0 积��到 x = 1。

    *答案*：1 - 2^(-2) + 3^(-3) - 4^(-4) + ... = 0.78343...

1.  数值积分 f(x) = e^(-x) sin(8x^(2/3)) 从 0 积分到 2。

1.  对 f(x) = sin(x²) 从 x = 0 积分到 x = pi。

1.  对 f(x) = cos(20 x²) 从 x = 0 积分到 x = 1。

1.  使用梯形法则数值积分 f(x) = 4 sqrt(1 - x²) 从 x = -1 积分到 1。注意收敛到真实答案 xyz 的速度较慢。

1.  编写一个计算正弦积分 Si(x) 的程序，它被定义为 (sin t) / t 从 0 积分到 x。

1.  编写一个计算 Fresnel 正弦积分 FresnelSi(x) 的程序，它被定义为 sin (π/2 t²) 从 0 积分到 x。

1.  使用蒙特卡洛积分来近似 f(x, y) = x² + 6xy + y² 在单位圆内 (x² + y² ≤ 1) 的二维积分。

#### 创意练习
