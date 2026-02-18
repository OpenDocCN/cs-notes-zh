# 21：第16讲 SDS状态与有限状态机 🧠

![](img/e5b0af1fbde738bee5694c53ec1e75d7_0.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_2.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_4.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_6.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_8.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_10.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_12.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_14.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_16.png)

在本节课中，我们将学习数字系统中的状态概念，并深入探讨有限状态机（FSM）的工作原理。我们将从回顾布尔逻辑问题开始，然后逐步构建一个累加器电路，并最终理解如何用时序逻辑和寄存器来实现状态记忆。

![](img/e5b0af1fbde738bee5694c53ec1e75d7_18.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_20.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_22.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_24.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_26.png)

---

![](img/e5b0af1fbde738bee5694c53ec1e75d7_28.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_30.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_32.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_34.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_36.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_38.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_40.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_42.png)

## 回顾布尔逻辑问题 🔍

![](img/e5b0af1fbde738bee5694c53ec1e75d7_44.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_46.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_48.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_50.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_52.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_54.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_56.png)

上一节我们介绍了组合逻辑，本节我们来看看之前留下的三个布尔逻辑问题，以巩固理解。

![](img/e5b0af1fbde738bee5694c53ec1e75d7_58.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_60.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_62.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_64.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_66.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_68.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_70.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_72.png)

以下是三个问题的解答思路：

![](img/e5b0af1fbde738bee5694c53ec1e75d7_74.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_76.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_78.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_79.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_81.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_83.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_85.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_87.png)

1.  **证明 (A AND (A OR B)) OR B 等于 B**
    *   简单的方法是制作真值表。
    *   第二种方法是使用布尔代数进行化简：
        `(A AND (A OR B)) OR B = (A AND A) OR (A AND B) OR B = A OR (A AND B) OR B`
        应用吸收律：`A OR (A AND B) = A`， 因此表达式简化为 `A OR B`。
        但注意，原表达式实际等价于 `B`。更严谨的推导需利用 `A OR (A AND B) = A`，并结合其他定律，最终可证明其等于 `B`。

2.  **能否将两个两输入门级联，构成一个三输入门？**
    *   对于 **AND**、**OR**、**XOR** 门，可以通过级联两个两输入门来实现三输入功能。例如：`(A AND B) AND C` 等价于三输入 AND。
    *   但对于 **NAND** 门，级联两个两输入 NAND `(A NAND B) NAND C` 并不能等价于一个三输入 NAND 门。可以通过对比真值表来验证。

![](img/e5b0af1fbde738bee5694c53ec1e75d7_89.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_91.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_93.png)

3.  **能否仅使用 NAND 或 NOR 门构造其他逻辑门？**
    *   答案是肯定的。NAND 和 NOR 被称为“通用逻辑门”。例如，将 NAND 门的两个输入连接在一起，就构成了一个反相器（NOT门）。再通过组合，可以构建出 AND、OR 等所有基本门电路。

![](img/e5b0af1fbde738bee5694c53ec1e75d7_95.png)

---

![](img/e5b0af1fbde738bee5694c53ec1e75d7_97.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_99.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_101.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_103.png)

## 从累加器模式到状态电路 ➕

![](img/e5b0af1fbde738bee5694c53ec1e75d7_105.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_107.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_109.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_111.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_113.png)

在编程中，我们熟悉累加器模式，例如求和：`S = S + X[i]`。在硬件中实现此功能，需要能够“记住”当前和 `S` 的值，这就是**状态**。

![](img/e5b0af1fbde738bee5694c53ec1e75d7_115.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_117.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_119.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_121.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_123.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_125.png)

我们首先尝试一个直接反馈的想法：将加法器的输出直接接回其输入。但这行不通，原因有二：
1.  无法控制何时读取下一个输入 `X[i]`。
2.  无法将累加和 `S` 初始化为零。

![](img/e5b0af1fbde738bee5694c53ec1e75d7_127.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_129.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_131.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_133.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_135.png)

为了解决这个问题，我们需要引入能够存储状态的元件。

![](img/e5b0af1fbde738bee5694c53ec1e75d7_137.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_139.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_141.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_143.png)

---

![](img/e5b0af1fbde738bee5694c53ec1e75d7_145.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_147.png)

## 核心元件：D触发器与寄存器 💾

![](img/e5b0af1fbde738bee5694c53ec1e75d7_149.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_151.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_153.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_155.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_157.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_159.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_161.png)

状态存储的基础是 **D触发器**。

![](img/e5b0af1fbde738bee5694c53ec1e75d7_163.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_165.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_167.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_169.png)

*   **符号与功能**：一个 D 触发器有一个数据输入 **D**，一个时钟输入 **CLK**，和一个数据输出 **Q**。在时钟信号 **CLK** 的上升沿（从0变1的瞬间），它会采样输入 **D** 的值，并在短暂延迟后，将该值输出到 **Q** 并保持稳定，直到下一个时钟上升沿。
*   **时序参数**（关键概念）：
    *   **建立时间 (Setup Time)**：在时钟上升沿**之前**，输入 **D** 必须保持稳定的最短时间。
    *   **保持时间 (Hold Time)**：在时钟上升沿**之后**，输入 **D** 必须继续保持稳定的最短时间。
    *   **时钟到Q延迟 (Clock-to-Q Delay)**：从时钟上升沿到输出 **Q** 稳定有效所需的时间。
*   **寄存器**：一个多位宽的存储单元，由多个并行的 D 触发器构成，共用同一个时钟和复位信号。

![](img/e5b0af1fbde738bee5694c53ec1e75d7_171.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_173.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_175.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_177.png)

**公式/代码描述**：
```
行为描述：
在每一个 CLK 上升沿：
    Q <= D // 将 D 的值赋给 Q
时序约束：
    D 必须在时间窗口 [T_setup 之前, T_hold 之后] 内稳定。
```

---

![](img/e5b0af1fbde738bee5694c53ec1e75d7_179.png)

## 构建正确的累加器电路 ⚙️

![](img/e5b0af1fbde738bee5694c53ec1e75d7_181.png)

现在，我们使用一个寄存器来构建可工作的累加器。

![](img/e5b0af1fbde738bee5694c53ec1e75d7_183.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_185.png)

**电路结构**：
1.  一个加法器，有两个输入：`X[i]` 和 `S[i-1]`。
2.  一个寄存器，其输入 **D** 连接加法器的输出 `S[i]`，其输出 **Q** 反馈回加法器作为 `S[i-1]`。
3.  寄存器由全局时钟 **CLK** 控制，并有一个复位信号 **RST** 用于在开始时将 `S` 清零。

![](img/e5b0af1fbde738bee5694c53ec1e75d7_187.png)

**工作原理**：
1.  初始时刻，**RST** 有效，寄存器输出 `S[-1] = 0`。
2.  第一个时钟周期：输入 `X[0]` 与 `S[-1] (0)` 相加，产生 `S[0] = X[0]`。在时钟上升沿，`S[0]` 被存入寄存器。
3.  第二个时钟周期：寄存器输出变为 `S[0]`，与 `X[1]` 相加，产生 `S[1] = X[0] + X[1]`，并在下一个时钟沿存入。
4.  如此反复，寄存器始终保存着之前的累加和，实现了状态记忆。

![](img/e5b0af1fbde738bee5694c53ec1e75d7_189.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_191.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_193.png)

---

## 系统时序与最大时钟频率 ⏱️

![](img/e5b0af1fbde738bee5694c53ec1e75d7_195.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_197.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_199.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_201.png)

电路能跑多快（时钟频率多高）受限于最长的信号路径延迟。

![](img/e5b0af1fbde738bee5694c53ec1e75d7_203.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_205.png)

**关键路径**：寄存器A的时钟上升沿 → 寄存器A的Q端输出（T_cq）→ 经过组合逻辑电路（T_comb）→ 到达寄存器B的D端并满足其建立时间（T_setup）。
**最大时钟频率** 由该路径的总延迟决定。

![](img/e5b0af1fbde738bee5694c53ec1e75d7_207.png)

```
最小时钟周期 T_min = T_cq + T_comb + T_setup
最大时钟频率 F_max = 1 / T_min
```

![](img/e5b0af1fbde738bee5694c53ec1e75d7_209.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_211.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_213.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_215.png)

**流水线技术**：为了提升频率（吞吐量），可以在长组合逻辑路径中间插入寄存器，将其分割为多个较短的阶段。这样每个阶段处理时间变短，时钟可以更快。代价是单条数据通过整个电路的**延迟**会增加，但单位时间内处理的数据量（吞吐量）提高了。

![](img/e5b0af1fbde738bee5694c53ec1e75d7_217.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_219.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_221.png)

---

![](img/e5b0af1fbde738bee5694c53ec1e75d7_223.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_225.png)

## 有限状态机 🗺️

![](img/e5b0af1fbde738bee5694c53ec1e75d7_227.png)

有限状态机是描述和设计时序逻辑系统的强大工具。

![](img/e5b0af1fbde738bee5694c53ec1e75d7_229.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_230.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_232.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_234.png)

**构成要素**：
*   **状态**：系统所处的不同模式，如“初始”、“收到1个1”、“收到2个1”。
*   **转移**：状态之间的切换，由**输入**条件触发。
*   **输出**：在某个状态或发生某个转移时产生的信号。

![](img/e5b0af1fbde738bee5694c53ec1e75d7_236.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_238.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_240.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_242.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_244.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_246.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_248.png)

**示例：检测连续三个1**
*   **状态**：S0（初始/未连续收到1），S1（收到1个1），S2（收到连续2个1）。
*   **输入**：位信号 `in`。
*   **输出**：`out`，仅在连续收到第三个1时输出1。
*   **转移**：
    *   在S0状态：若 `in=0`，保持S0；若 `in=1`，进入S1。
    *   在S1状态：若 `in=0`，回到S0；若 `in=1`，进入S2。
    *   在S2状态：若 `in=0`，回到S0；若 `in=1`，输出1并回到S0。

![](img/e5b0af1fbde738bee5694c53ec1e75d7_250.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_252.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_254.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_256.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_258.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_260.png)

**硬件实现**：
FSM可以用我们刚学的结构实现：**组合逻辑**（根据当前状态和输入，计算下一个状态和输出）+ **状态寄存器**（存储当前状态）。

![](img/e5b0af1fbde738bee5694c53ec1e75d7_262.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_264.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_266.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_268.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_270.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_272.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_274.png)

---

![](img/e5b0af1fbde738bee5694c53ec1e75d7_276.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_278.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_280.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_282.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_284.png)

## 总结 📚

![](img/e5b0af1fbde738bee5694c53ec1e75d7_286.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_288.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_289.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_290.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_292.png)

本节课中我们一起学习了：
1.  **状态**的概念：数字系统需要寄存器来记忆信息。
2.  **D触发器与寄存器**：存储状态的基本单元，及其关键的时序参数（建立时间、保持时间、时钟到Q延迟）。
3.  **时序电路设计**：如何利用寄存器构建累加器等具有记忆功能的电路。
4.  **时序分析**：决定了电路的最大工作时钟频率，并引入了**流水线**技术来提升性能。
5.  **有限状态机**：一种描述复杂时序行为的模型，并可通过“组合逻辑+状态寄存器”的标准结构在硬件中实现。

![](img/e5b0af1fbde738bee5694c53ec1e75d7_294.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_296.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_298.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_300.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_302.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_304.png)

![](img/e5b0af1fbde738bee5694c53ec1e75d7_306.png)

这些概念是理解现代处理器和数字系统控制逻辑的基础。