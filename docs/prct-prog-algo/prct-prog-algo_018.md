# 3.4   案例研究:   N 体模拟

> 原文：[`introcs.cs.princeton.edu/java/34nbody`](https://introcs.cs.princeton.edu/java/34nbody)

在本节中，我们编写一个面向对象的程序，动态模拟 *n* 个身体在相互引力影响下的运动。

## 弹跳球。

数据类型 Ball.java 表示具有给定位置 \((r_x, r_y)\) 的球，它以固定速度 \((v_x, v_y)\) 在坐标为 −1 到 +1 的盒子中移动。当它与边界碰撞时，根据弹性碰撞定律反弹。

> ![添加矢量以移动球](img/0a74711369e2da400dd552c6b1a0997f.png)

客户端 BouncingBalls.java 接受一个命令行参数 *n* 并创建 *n* 个随机弹跳球。

## N 体模拟。

弹跳球模拟基于 *牛顿第一定律*：运动中的物体保持相同速度的运动，除非受到外力的作用。将该示例装饰以包含重力导致我们进入一个迷住科学家多年的基本问题。给定一个由相互影响的 *n* 个身体组成的系统，受到引力作用，问题是描述它们的运动。

+   *Body 数据类型.* 数据类型 Body.java 表示具有给定位置 \((r_x, r_y)\), 速度 \((v_x, v_y)\), 和质量 \(m\) 的身体。它应用 *牛顿第三定律*（解释了两个身体之间的引力）来确定作用在身体上的净力：

    > $$ \boldsymbol{F} = G \frac{m_1 m_2}{r²} $$

    和 *牛顿第二定律*（解释外力如何直接影响加速度和速度）。

    > $$ \boldsymbol{F} = m \boldsymbol{a} $$

    它使用 Vector.java 数据类型来表示位移、速度和力作为矢量量。

    > ![Body 数据类型 API](img/4a3db88c0c4f95460fd93a35352e2586.png)

+   *Universe 数据类型.* Universe.java 接受一个命令行参数 `dt`，从标准输入读取一个宇宙，并使用时间量子 `dt` 模拟宇宙。以下是数据文件格式的示例：

    > ![n 体模拟的数据文件格式](img/ae222ac7b21fbaf4ef22ec2e15af3439.png)

    以下静态图像 2body.txt, 3body.txt, 和 4body.txt 是通过修改 Universe.java 和 Body.java 来绘制白色身体，然后在灰色背景上绘制黑色身体而制作的。

    > ![2-, 3-, 和 4-体系的模拟](img/239e0e02a08d33b7c892b0e9e1e07e2a.png)

#### 练习

1.  从第 1.5 节开发一个面向对象的版本的 BouncingBall.java。包括一个构造函数，该构造函数以随机方向和随机速度（在合理范围内）开始每个球的运动，并且一个测试客户端，从命令行接受一个整数 *n* 并模拟 *n* 个弹跳球的运动。

    *解决方案*: Ball.java 和 BouncingBalls.java.

1.  在一个不适用牛顿第二定律的宇宙中会发生什么？这种情况对应于 `Body` 中的 `forceTo()` 总是返回零矢量。

    *解决方案*: 身体将沿着直线运动，根据它们的初始速度。

#### 创意练习

1.  **N 体模拟跟踪.** 编写一个客户端 UniverseTrace.java 产生类似书中静态图像的 n 体模拟系统的跟踪。

#### 网页练习

1.  **彩色弹跳球.** 修改 Ball.java 和 BouncingBalls.java 以将每个球与颜色关联起来。将你的程序命名为 ColoredBall.java 和 BouncingColoredBalls.java.

1.  **摩擦和阻力.** 修改 Ball.java 以包含摩擦和阻力。将你的数据类型命名为 DeluxeBall.java.

1.  **基于重力模拟器的生成音乐。** 根据 n 体模拟生成音乐，其中当物体碰撞时发出音符。Simran Gleason 的[网站](http://www.art.net/~simran/GenerativeMusic/kepler.html)描述了这一过程，并包括示例视频。
