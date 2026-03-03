# 数字设计和计算机架构：4.4：SystemVerilog中的时序逻辑 🧠

![](img/3fc0fc11d52692dbb533c8b269a5e476_1.png)

在本节课中，我们将要学习如何使用SystemVerilog来描述时序逻辑电路，包括锁存器、触发器和有限状态机。我们将重点介绍描述这些电路的标准“惯用语”，并解释为何使用正确的编码风格至关重要。

上一节我们介绍了如何使用赋值语句来指定组合逻辑，本节中我们来看看如何指定时序逻辑。

SystemVerilog使用特定的“惯用语”来描述锁存器、触发器和有限状态机。这些惯用语是我们在SystemVerilog中用来明确指定“这应该是一个锁存器”或“这应该是一个触发器”的固定格式。其他编码风格可能看似正确，但会产生错误的硬件，因此使用我们将要讨论的这些惯用语风格非常重要。

指定这些锁存器和触发器的一般结构总是围绕一个称为“敏感列表”的部分。我们使用 `always` 关键字，后跟一个敏感列表，然后执行一条语句。每当敏感列表中的任何信号发生变化（即事件发生时），就应该执行该语句。

以下是描述一个D触发器的示例。

```systemverilog
module flop (
    input logic clk,
    input logic [3:0] d,
    output logic [3:0] q
);
    always_ff @(posedge clk)
        q <= d;
endmodule
```

我们有关键字 `module` 和模块名（这里我们选择了 `flop`，这取决于电路设计者的选择）。我们有输入 `clk` 和 `d`（这是一个4位输入），以及一个4位输出 `q`。这是我们使用的惯用语：`always_ff` 表示这应该是一个触发器。`@(posedge clk)` 中的 `posedge` 关键字表示在时钟的上升沿（从0变为1时）执行语句。因此，在时钟的上升沿，执行 `q <= d` 这条语句，将 `d` 的值传输给 `q`。当我们综合这段硬件描述时，会得到我们期望的D触发器。

我们也可以指定一个可复位的D触发器。

```systemverilog
module flopr (
    input logic clk,
    input logic reset,
    input logic [3:0] d,
    output logic [3:0] q
);
    always_ff @(posedge clk)
        if (reset) q <= 4‘b0;
        else q <= d;
endmodule
```

现在，除了时钟输入 `clk`，我们还添加了复位输入 `reset`。`always` 语句的这部分是相同的：`always_ff @(posedge clk)`。这意味着当时钟上升沿事件发生时，将执行语句。但它执行的语句现在不同了：如果 `reset` 为真，则 `q` 变为0；否则，`q` 正常地获取 `d` 的值。当 `reset` 为0时，它就像一个普通的D触发器。那么，这是一个异步还是同步可复位的触发器呢？复位操作仅在响应时钟边沿时发生，因此这是一个**同步复位**的D触发器。

我们也可以构建一个异步复位的触发器。

```systemverilog
module flopr_async (
    input logic clk,
    input logic reset,
    input logic [3:0] d,
    output logic [3:0] q
);
    always_ff @(posedge clk or posedge reset)
        if (reset) q <= 4‘b0;
        else q <= d;
endmodule
```

为此，我们需要将希望触发语句评估的事件放入 `always` 语句的敏感列表中。`always_ff @(posedge clk or posedge reset)` 表示整个 `always` 块中的语句将在时钟上升沿 **或** 复位信号上升沿发生时被评估。如果 `reset` 变为高电平（上升沿），它会触发评估。如果 `reset` 为1，`q` 会立即复位，而无需等待时钟上升。因此，这是一个**异步复位**的D触发器。从综合后的符号来看，你无法区分异步和同步复位，需要查看SystemVerilog代码。

我们还可以指定一个带使能端的D触发器。

```systemverilog
module flopr_en (
    input logic clk,
    input logic reset,
    input logic en,
    input logic [3:0] d,
    output logic [3:0] q
);
    always_ff @(posedge clk or posedge reset)
        if (reset) q <= 4‘b0;
        else if (en) q <= d;
endmodule
```

这里有时钟 `clk` 和复位 `reset`，现在我们添加了使能输入 `en`。我们修改代码：如果 `reset` 为真，`q` 变为0；否则，如果 `enable` 为真，则 `q` 获取 `d` 的值。我们没有添加 `else` 语句，因为如果上述条件都不满足，触发器将保持它之前拥有的值（即保持 `q` 的前一个值）。这仍然是一个带使能端的异步复位触发器。你也可以将其改为同步复位并带使能端。

接下来，让我们讨论另一种我们实际上不会使用、并且通常在你的设计中也不应该使用的时序逻辑电路：锁存器。在本课程中，如果你产生了锁存器，那是一个错误。锁存器是一种当时钟为高电平时，`q` 跟随 `d` 变化的元件。

```systemverilog
module latch (
    input logic clk,
    input logic [3:0] d,
    output logic [3:0] q
);
    always_latch
        if (clk) q <= d;
endmodule
```

我们使用关键字 `always_latch`。如果 `clk` 为高，则 `q` 获取 `d` 的值；否则（隐含地），`q` 保持其值。这里的问题是，如果你没有完全指定组合逻辑（例如，在 `if` 语句中缺少 `else` 分支），则可能产生锁存器。在本课程中，你不应该期望出现锁存器。你可能会在综合工具的输出中看到一些警告，例如“警告：产生了锁存器”。你需要查看这些警告并修复问题，通常问题在于没有完全指定组合逻辑。再次强调，如果你的SystemVerilog代码中产生了锁存器，那就是一个错误。

![](img/3fc0fc11d52692dbb533c8b269a5e476_3.png)

本节课中我们一起学习了在SystemVerilog中描述时序逻辑的标准方法，包括D触发器、同步/异步复位触发器、带使能端的触发器，并强调了避免无意中生成锁存器的重要性。正确使用这些惯用语对于生成预期的硬件电路至关重要。