# 数字设计和计算机架构：4.7：有限状态机 (FSMs) 🧠

![](img/cf79c90b780381891a4e35b0ed2e60f6_1.png)

在本节中，我们将学习如何在硬件描述语言（HDL）中描述有限状态机（FSM）。我们将探讨摩尔型和米利型FSM的区别，并通过两个具体示例——一个三分频计数器和一个序列检测器——来演示如何将状态转移图直接转换为SystemVerilog代码。

## 从状态图到硬件描述

上一节我们介绍了有限状态机的基本概念。本节中我们来看看如何在SystemVerilog中描述它们。

与硬件设计中的FSM一样，我们在SystemVerilog中描述的有限状态机也由三个逻辑块组成：次态逻辑、输出逻辑和状态寄存器。

以下是我们的摩尔型FSM和米利型FSM的示意图。两者都包含次态逻辑、输出逻辑和状态寄存器。米利型FSM的区别在于，其输出逻辑由当前状态和输入共同驱动，而在摩尔型FSM中，输出逻辑仅取决于当前状态。

## 三分频计数器示例

假设我们有一个三分频计数器。其复位状态为S0，由双圆圈表示。在每个时钟边沿，状态发生转移。它被称为“三分频”是因为输出信号的频率是输入时钟频率的三分之一。

以下是状态转移过程：
*   状态从S0开始。
*   在第一个时钟边沿，转移到S1。
*   在第二个时钟边沿，转移到S2。
*   在第三个时钟边沿，回到S0，并重复此循环。

输出仅在S0状态为高。如果时钟周期为1纳秒（频率1 GHz），则输出周期为3纳秒（频率1/3 GHz），因此实现了三分频。

现在，我们看看如何将这个状态转移图转换为SystemVerilog中的FSM模块。

```systemverilog
module divide_by_three_fsm (
    input logic clk, reset,
    output logic q
);
```

这个FSM在S0状态时断言输出q。因此，在S0时q为高，在S1和S2时q为低，如此循环。

我们首先定义一个状态类型，以便使用符号S0、S1、S2，而不是具体的二进制编码。

```systemverilog
typedef enum logic [1:0] {S0, S1, S2} statetype;
statetype state, nextstate;
```

接着，我们定义三个逻辑块，就像在硬件中一样：状态寄存器、次态逻辑和输出逻辑。

状态寄存器就是一个存储当前状态的寄存器。

```systemverilog
// 状态寄存器
always_ff @(posedge clk, posedge reset)
    if (reset) state <= S0;
    else       state <= nextstate;
```

次态逻辑根据当前状态决定下一个状态。

```systemverilog
// 次态逻辑
always_comb
    case (state)
        S0: nextstate = S1;
        S1: nextstate = S2;
        S2: nextstate = S0;
        default: nextstate = S0; // 重要：包含默认情况
    endcase
```

输出逻辑根据当前状态产生输出。

```systemverilog
// 输出逻辑
assign q = (state == S0);
```

在这个FSM中，我们希望输出仅在S0状态断言。如果我们希望它在S0和S1状态都断言，代码应为 `assign q = (state == S0) | (state == S1);`。一个常见错误是写成 `S0 | S1`，这是对状态编码值进行按位或操作，而不是逻辑或，会导致错误。

## 序列检测器示例（摩尔型）

接下来是另一个摩尔型FSM的例子：一个检测序列“01”的序列检测器。在复位状态S0，如果检测到输入a为0，则转移到S1。在S1状态，如果检测到a为1，则转移到S2并断言输出。否则，根据输入进行其他状态转移。

例如，输入a随时间变化，每当出现“0”后紧跟“1”的序列时，输出就应该断言。

现在我们在HDL中描述它。我们可以直接从状态转移图编写SystemVerilog代码，无需设计具体电路。

我们同样有三个状态，因此需要2位状态变量。如果有更多状态（例如5个），则需要3位状态变量（`[2:0]`）。

状态寄存器与之前相同。次态逻辑根据当前状态和输入a决定下一个状态。

```systemverilog
// 次态逻辑
always_comb
    case (state)
        S0: if (a) nextstate = S0;
            else   nextstate = S1;
        S1: if (a) nextstate = S2;
            else   nextstate = S1;
        S2: if (a) nextstate = S0;
            else   nextstate = S1;
        default: nextstate = S0; // 重要：包含默认情况
    endcase
```

输出逻辑中，输出仅在S2状态为真。

```systemverilog
// 输出逻辑
assign smile = (state == S2); // 注意：使用双等号进行比较操作
```

## 序列检测器示例（米利型）

现在考虑同一个序列检测器，但用米利型FSM实现。我们仍然寻找“0”后跟“1”的序列。在米利型中，当处于S0状态且输入a为0时，转移到S1。当处于S1状态且输入a为1时，**立即断言输出**并转移到S0。米利型FSM的输出时序与摩尔型略有不同。

将其转换为SystemVerilog模块。我们仍然直接从状态转移图编写代码。

这里我们只有两个状态，因此只需要1位状态变量（`logic` 类型）。在米利型FSM中，次态逻辑和输出逻辑可以合并到一个组合逻辑块中描述。

```systemverilog
// 次态与输出组合逻辑
always_comb begin
    smile = 1‘b0; // 默认输出为0
    case (state)
        S0: if (a) begin
                nextstate = S0;
            end else begin
                nextstate = S1;
            end
        S1: if (a) begin
                nextstate = S0;
                smile = 1‘b1; // 检测到序列，断言输出
            end else begin
                nextstate = S1;
            end
        default: nextstate = S0;
    endcase
end
```

注意，我们在`case`语句之前将`smile`默认赋值为0。这样，除非在`case`语句的特定分支（如S1且a为1时）被显式赋值，否则输出保持为0。这确保了组合逻辑对所有可能的输入（状态和a）都是确定性的，同时避免了在每个分支都重复书写`smile = 1‘b0;`，使代码更简洁。

## 总结

![](img/cf79c90b780381891a4e35b0ed2e60f6_3.png)

本节课中我们一起学习了如何在SystemVerilog中描述有限状态机。我们回顾了摩尔型与米利型FSM的核心区别：摩尔型的输出仅依赖于当前状态，而米利型的输出依赖于当前状态和输入。我们通过三分频计数器和“01”序列检测器两个例子，详细演示了如何将状态转移图转换为包含状态寄存器、次态逻辑和输出逻辑三个部分的HDL代码。关键要点包括：使用`enum`定义状态类型以提高代码可读性；在组合逻辑的`case`语句中务必包含`default`分支；正确使用比较运算符（`==`）和赋值语句；对于米利型机，可以在逻辑块开始处为输出设置默认值以简化代码。掌握这些方法，你就能直接使用HDL来描述复杂的时序逻辑行为了。