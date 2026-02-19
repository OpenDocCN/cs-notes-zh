# 计算机思维导论-Julia：L10：随机模拟建模 🎲

![](img/b8e1d125d9ff89215ae2d0f3136f14a4_1.png)

![](img/b8e1d125d9ff89215ae2d0f3136f14a4_3.png)

![](img/b8e1d125d9ff89215ae2d0f3136f14a4_5.png)

在本节课中，我们将学习如何使用概率来模拟随时间变化的系统。我们将建立一个简单的模型，用于模拟机械部件或灯泡的失效过程。通过这个过程，我们将探索如何定义新类型、扩展函数以及进行随机模拟。

---

![](img/b8e1d125d9ff89215ae2d0f3136f14a4_7.png)

![](img/b8e1d125d9ff89215ae2d0f3136f14a4_9.png)

## 概述 📋

![](img/b8e1d125d9ff89215ae2d0f3136f14a4_11.png)

![](img/b8e1d125d9ff89215ae2d0f3136f14a4_13.png)

![](img/b8e1d125d9ff89215ae2d0f3136f14a4_15.png)

![](img/b8e1d125d9ff89215ae2d0f3136f14a4_17.png)

我们将建立一个“灯泡失效”模型。在这个模型中，一组灯泡最初是完好的（绿色），在每个时间步，每个灯泡都有一定的概率失效（变为红色），并在下一个时间步永久失效（变为紫色）。我们将通过这个简单的随机过程，学习如何连接微观的个体行为与宏观的系统行为。

![](img/b8e1d125d9ff89215ae2d0f3136f14a4_19.png)

上一节我们介绍了随机模拟的基本概念，本节中我们来看看如何具体实现一个简单的随机过程模型。

---

## 模型描述与模拟 🔧

![](img/b8e1d125d9ff89215ae2d0f3136f14a4_21.png)

![](img/b8e1d125d9ff89215ae2d0f3136f14a4_23.png)

![](img/b8e1d125d9ff89215ae2d0f3136f14a4_25.png)

![](img/b8e1d125d9ff89215ae2d0f3136f14a4_27.png)

![](img/b8e1d125d9ff89215ae2d0f3136f14a4_29.png)

我们有一个灯泡阵列，每个灯泡的状态随时间变化。模型的核心规则如下：
*   初始时，所有灯泡都是完好的（状态为0）。
*   在每个时间步 `t`，每个仍完好的灯泡以概率 `p` 失效。
*   如果一个灯泡在时间 `t` 失效，我们将其状态标记为 `t`（表示失效时间）。
*   失效后的灯泡在后续时间步状态保持不变（永久失效）。

![](img/b8e1d125d9ff89215ae2d0f3136f14a4_31.png)

以下是模拟这个过程的Julia代码核心逻辑：

![](img/b8e1d125d9ff89215ae2d0f3136f14a4_33.png)

```julia
function simulate_failure(N, p, max_time)
    # 初始化状态矩阵，0表示完好
    state = zeros(Int, N, N)
    for t in 1:max_time
        for i in 1:N, j in 1:N
            # 如果灯泡完好，则进行随机测试
            if state[i, j] == 0 && rand() < p
                state[i, j] = t  # 记录失效时间
            end
        end
    end
    return state
end
```

![](img/b8e1d125d9ff89215ae2d0f3136f14a4_35.png)

![](img/b8e1d125d9ff89215ae2d0f3136f14a4_37.png)

---

![](img/b8e1d125d9ff89215ae2d0f3136f14a4_39.png)

![](img/b8e1d125d9ff89215ae2d0f3136f14a4_41.png)

![](img/b8e1d125d9ff89215ae2d0f3136f14a4_43.png)

## 可视化绘图 🎨

![](img/b8e1d125d9ff89215ae2d0f3136f14a4_45.png)

![](img/b8e1d125d9ff89215ae2d0f3136f14a4_47.png)

为了直观展示模拟结果，我们需要绘制灯泡阵列。这涉及到在特定坐标上绘制形状（如圆形和方形）。

![](img/b8e1d125d9ff89215ae2d0f3136f14a4_49.png)

![](img/b8e1d125d9ff89215ae2d0f3136f14a4_51.png)

![](img/b8e1d125d9ff89215ae2d0f3136f14a4_53.png)

![](img/b8e1d125d9ff89215ae2d0f3136f14a4_55.png)

![](img/b8e1d125d9ff89215ae2d0f3136f14a4_57.png)

![](img/b8e1d125d9ff89215ae2d0f3136f14a4_59.png)

![](img/b8e1d125d9ff89215ae2d0f3136f14a4_61.png)

以下是绘制矩形和圆形的辅助函数：

![](img/b8e1d125d9ff89215ae2d0f3136f14a4_63.png)

![](img/b8e1d125d9ff89215ae2d0f3136f14a4_65.png)

![](img/b8e1d125d9ff89215ae2d0f3136f14a4_67.png)

```julia
function rectangle(x, y, w, h)
    xs = [x, x+w, x+w, x]
    ys = [y, y, y+h, y+h]
    return (xs, ys)
end

![](img/b8e1d125d9ff89215ae2d0f3136f14a4_69.png)

![](img/b8e1d125d9ff89215ae2d0f3136f14a4_71.png)

![](img/b8e1d125d9ff89215ae2d0f3136f14a4_73.png)

![](img/b8e1d125d9ff89215ae2d0f3136f14a4_75.png)

![](img/b8e1d125d9ff89215ae2d0f3136f14a4_77.png)

![](img/b8e1d125d9ff89215ae2d0f3136f14a4_79.png)

![](img/b8e1d125d9ff89215ae2d0f3136f14a4_81.png)

![](img/b8e1d125d9ff89215ae2d0f3136f14a4_83.png)

![](img/b8e1d125d9ff89215ae2d0f3136f14a4_85.png)

function circle(x, y, r, n=30)
    θ = range(0, 2π, length=n)
    xs = x .+ r .* cos.(θ)
    ys = y .+ r .* sin.(θ)
    return (xs, ys)
end
```

![](img/b8e1d125d9ff89215ae2d0f3136f14a4_87.png)

![](img/b8e1d125d9ff89215ae2d0f3136f14a4_89.png)

![](img/b8e1d125d9ff89215ae2d0f3136f14a4_91.png)

![](img/b8e1d125d9ff89215ae2d0f3136f14a4_93.png)

![](img/b8e1d125d9ff89215ae2d0f3136f14a4_95.png)

![](img/b8e1d125d9ff89215ae2d0f3136f14a4_97.png)

![](img/b8e1d125d9ff89215ae2d0f3136f14a4_99.png)

在绘图时，我们可以使用 `fill=true` 参数来填充形状，并使用 `annotate!` 函数添加文本标签。字符串插值（`$`）可以方便地将变量值嵌入标签字符串中。

![](img/b8e1d125d9ff89215ae2d0f3136f14a4_101.png)

---

![](img/b8e1d125d9ff89215ae2d0f3136f14a4_103.png)

![](img/b8e1d125d9ff89215ae2d0f3136f14a4_105.png)

![](img/b8e1d125d9ff89215ae2d0f3136f14a4_107.png)

## 数据分析与宏观视角 📊

![](img/b8e1d125d9ff89215ae2d0f3136f14a4_109.png)

![](img/b8e1d125d9ff89215ae2d0f3136f14a4_111.png)

![](img/b8e1d125d9ff89215ae2d0f3136f14a4_113.png)

运行模拟后，我们可以统计每个时间步处于不同状态（绿色/红色/紫色）的灯泡数量。

以下是可能的数据分析步骤：
1.  **统计数量**：遍历状态矩阵，根据存储的值（0表示完好，`t` 表示在时间 `t` 失效）对灯泡进行分类计数。
2.  **绘制曲线**：将完好灯泡数量、新失效灯泡数量随时间变化的曲线绘制出来。
3.  **观察规律**：我们会发现，完好灯泡数量的曲线相对平滑，而每个时间步新失效数量的曲线噪声较大。这是因为累计数量（完好总数）对随机波动有平滑作用。

单个模拟的结果具有随机性。为了得到更稳定的规律，我们可以进行多次独立模拟并计算平均值。

---

## 随机变量与类型定义 🎲

上述模型中的每个灯泡，其“是否失效”的行为可以用一个**伯努利随机变量**来建模。伯努利随机变量模拟了一次加权硬币抛掷，它以概率 `p` 取值为1（成功/失效），以概率 `1-p` 取值为0（失败/完好）。

在Julia中，我们可以创建一个新类型来封装这个随机变量及其参数。

```julia
struct Bernoulli
    p::Float64  # 成功概率
end
```

![](img/b8e1d125d9ff89215ae2d0f3136f14a4_115.png)

![](img/b8e1d125d9ff89215ae2d0f3136f14a4_117.png)

![](img/b8e1d125d9ff89215ae2d0f3136f14a4_119.png)

接着，我们可以为这个新类型扩展已有的通用函数。例如，定义如何从 `Bernoulli` 对象中随机采样：

![](img/b8e1d125d9ff89215ae2d0f3136f14a4_121.png)

![](img/b8e1d125d9ff89215ae2d0f3136f14a4_123.png)

```julia
import Base: rand
function rand(b::Bernoulli)
    return Int(rand() < b.p)
end
```

![](img/b8e1d125d9ff89215ae2d0f3136f14a4_125.png)

![](img/b8e1d125d9ff89215ae2d0f3136f14a4_127.png)

![](img/b8e1d125d9ff89215ae2d0f3136f14a4_129.png)

![](img/b8e1d125d9ff89215ae2d0f3136f14a4_131.png)

我们还可以为定义在 `Statistics` 包中的 `mean` 函数添加方法，来计算伯努利随机变量的理论均值：

![](img/b8e1d125d9ff89215ae2d0f3136f14a4_133.png)

![](img/b8e1d125d9ff89215ae2d0f3136f14a4_135.png)

```julia
using Statistics
function mean(b::Bernoulli)
    return b.p
end
```

![](img/b8e1d125d9ff89215ae2d0f3136f14a4_137.png)

![](img/b8e1d125d9ff89215ae2d0f3136f14a4_139.png)

![](img/b8e1d125d9ff89215ae2d0f3136f14a4_141.png)

![](img/b8e1d125d9ff89215ae2d0f3136f14a4_143.png)

![](img/b8e1d125d9ff89215ae2d0f3136f14a4_145.png)

![](img/b8e1d125d9ff89215ae2d0f3136f14a4_147.png)

![](img/b8e1d125d9ff89215ae2d0f3136f14a4_149.png)

这样，我们就创建了一个计算实体，它既包含了数据（参数 `p`），也包含了对其进行的操作（采样、计算均值）。

![](img/b8e1d125d9ff89215ae2d0f3136f14a4_151.png)

![](img/b8e1d125d9ff89215ae2d0f3136f14a4_153.png)

![](img/b8e1d125d9ff89215ae2d0f3136f14a4_155.png)

![](img/b8e1d125d9ff89215ae2d0f3136f14a4_157.png)

![](img/b8e1d125d9ff89215ae2d0f3136f14a4_159.png)

![](img/b8e1d125d9ff89215ae2d0f3136f14a4_161.png)

![](img/b8e1d125d9ff89215ae2d0f3136f14a4_163.png)

---

![](img/b8e1d125d9ff89215ae2d0f3136f14a4_165.png)

![](img/b8e1d125d9ff89215ae2d0f3136f14a4_167.png)

## 从微观到宏观：确定性方程 🔬

![](img/b8e1d125d9ff89215ae2d0f3136f14a4_169.png)

![](img/b8e1d125d9ff89215ae2d0f3136f14a4_171.png)

![](img/b8e1d125d9ff89215ae2d0f3136f14a4_173.png)

通过对大量独立灯泡的微观行为进行平均，我们可以推导出描述系统宏观行为的确定性方程。

设 `I_t` 为时间 `t` 时完好灯泡的数量。
*   在时间 `t`，有 `I_t` 个灯泡完好。
*   每个灯泡失效的概率为 `p`。
*   因此，在时间 `t` 失效的灯泡数量的**期望值**是 `p * I_t`。

由此，我们可以得到 `I_t` 随时间变化的递推关系：
`I_{t+1} = I_t - p * I_t = (1 - p) * I_t`

这是一个确定性方程。假设初始数量为 `I_0`，我们可以直接解出：
`I_t = (1 - p)^t * I_0`

这表明完好灯泡的数量随时间呈**指数衰减**。当我们将这个确定性方程的解与多次随机模拟的平均结果进行比较时，会发现它们完美吻合。这揭示了在大量个体情况下，随机系统的平均行为可以由一个简单的确定性模型来描述。

---

## 总结 🏁

本节课中我们一起学习了：
1.  **构建随机过程模型**：我们建立了灯泡失效的简单随机模型，其中每个个体在每个时间步以固定概率改变状态。
2.  **实现模拟与可视化**：我们编写了模拟代码，并学习了如何绘制自定义形状来可视化模拟结果。
3.  **定义抽象类型**：我们将伯努利随机变量定义为一种新的Julia类型，并为其扩展了 `rand` 和 `mean` 函数，体现了将数据与操作封装在一起的思想。
4.  **连接微观与宏观**：我们通过分析推导出，大量独立个体随机行为的平均效应，可以用一个描述总数量的确定性指数衰减方程来刻画。这是理解复杂系统的一种强大方法。

![](img/b8e1d125d9ff89215ae2d0f3136f14a4_175.png)

![](img/b8e1d125d9ff89215ae2d0f3136f14a4_177.png)

![](img/b8e1d125d9ff89215ae2d0f3136f14a4_179.png)

这个简单的模型是许多领域（如流行病学、金融、化学）中更复杂模型的基础。通过掌握这些基本概念，你便拥有了分析随机动态系统的起点。