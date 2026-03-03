# 101：单周期处理器SystemVerilog实现 🖥️

![](img/5946d95f116a18f7be260544864ccd36_0.png)

在本节中，我们将学习如何用SystemVerilog硬件描述语言实现一个RISC-V单周期处理器。我们将从顶层模块开始，逐步深入到数据通路和控制器的各个子模块，并了解如何编写测试平台来验证设计的正确性。

## 概述

本教程将详细讲解一个RISC-V单周期处理器的SystemVerilog实现。该处理器实现了包括加载、存储、算术运算、逻辑运算、分支和跳转在内的基本指令集。我们将遵循自顶向下的方法，首先介绍测试平台和顶层模块，然后深入到处理器、控制器和数据通路的内部结构。

![](img/5946d95f116a18f7be260544864ccd36_2.png)

## 测试平台

![](img/5946d95f116a18f7be260544864ccd36_3.png)

![](img/5946d95f116a18f7be260544864ccd36_5.png)

测试平台用于实例化被测设备，提供时钟和复位信号，并检查运行结果是否正确。

以下是测试平台的核心部分：

![](img/5946d95f116a18f7be260544864ccd36_7.png)

![](img/5946d95f116a18f7be260544864ccd36_8.png)

```systemverilog
// 实例化被测设备（整个处理器）
riscv_singlecycle dut (.clk(clk), .reset(reset), ...);

![](img/5946d95f116a18f7be260544864ccd36_10.png)

![](img/5946d95f116a18f7be260544864ccd36_11.png)

// 生成周期为10个时间单位的时钟
always #5 clk = ~clk;

![](img/5946d95f116a18f7be260544864ccd36_13.png)

// 应用持续22个时间单位的复位信号
initial begin
    reset = 1;
    #22;
    reset = 0;
end
```

为了验证结果，测试平台在每个时钟的下降沿检查内存写操作。如果处理器将数值`71`写入地址`84`，则表明仿真成功。如果发生其他内存写操作，则忽略或报告仿真失败。

![](img/5946d95f116a18f7be260544864ccd36_15.png)

```systemverilog
always @(negedge clk) begin
    if (memwrite && dataadr === 32'h54 && writedata === 32'h47) begin
        $display("Simulation succeeded");
        $stop;
    end else if (memwrite && dataadr !== 32'h50) begin
        $display("Simulation failed");
        $stop;
    end
end
```

## 顶层模块

上一节我们介绍了测试平台，本节中我们来看看处理器的顶层模块。顶层模块包含处理器、指令存储器和数据存储器。

![](img/5946d95f116a18f7be260544864ccd36_17.png)

这些模块通过以下信号连接：
*   程序计数器（PC）从处理器输出到指令存储器。
*   数据存储器接收来自处理器的内存写使能、数据地址和写入数据信号，并向处理器返回读取数据。

```systemverilog
module top(input logic clk, reset, output logic [31:0] writedata, dataadr, output logic memwrite);
    logic [31:0] pc, instr, readdata;
    // 实例化处理器
    riscv_singlecycle cpu(clk, reset, pc, instr, memwrite, dataadr, writedata, readdata);
    // 实例化指令存储器
    imem imem(pc[7:2], instr);
    // 实例化数据存储器
    dmem dmem(clk, memwrite, dataadr, writedata, readdata);
endmodule
```

![](img/5946d95f116a18f7be260544864ccd36_19.png)

### 数据存储器

![](img/5946d95f116a18f7be260544864ccd36_21.png)

数据存储器是一个同步读写存储器，包含64个32位字。

![](img/5946d95f116a18f7be260544864ccd36_23.png)

![](img/5946d95f116a18f7be260544864ccd36_24.png)

以下是其读写操作：
*   **读操作**：`assign readdata = ram[address];`
*   **写操作**：在时钟上升沿，如果写使能信号为真，则执行写入。`if (we) ram[address] <= writedata;`

![](img/5946d95f116a18f7be260544864ccd36_26.png)

### 指令存储器

![](img/5946d95f116a18f7be260544864ccd36_28.png)

指令存储器包含64个32位字，并在初始化时载入一个由18条机器语言指令组成的程序。

其读操作使用相同的惯用语法：`assign instr = ram[address];`

## 处理器模块

![](img/5946d95f116a18f7be260544864ccd36_30.png)

![](img/5946d95f116a18f7be260544864ccd36_31.png)

现在让我们进入处理器模块内部。处理器由数据通路和控制器两部分组成。

数据通路接收时钟、复位信号以及来自控制器的一系列控制信号，并产生零标志位输出。控制器接收指令和零标志位，并产生控制数据通路所需的控制信号。

![](img/5946d95f116a18f7be260544864ccd36_33.png)

在Verilog中，必须声明连接模块之间的所有内部信号。如果未声明，Verilog会默认其为单比特信号，这可能导致多比特信号（如立即数源或ALU控制信号）行为错误。

![](img/5946d95f116a18f7be260544864ccd36_35.png)

```systemverilog
module riscv_singlecycle(input logic clk, reset,
                         output logic [31:0] pc,
                         input logic [31:0] instr,
                         output logic memwrite,
                         output logic [31:0] aluout, writedata,
                         input logic [31:0] readdata);
    // 控制器产生的控制信号
    logic [1:0] immsrc, resultsrc;
    logic alusrc, regwrite, zero;
    logic [1:0] pcsrc;
    logic [2:0] alucontrol;
    // 数据通路产生的零标志位
    // ... 控制器和数据通路实例化 ...
endmodule
```

## 控制器

控制器由主译码器、ALU译码器和用于计算PC源（程序计数器下一个值来源）的逻辑组成。

以下是控制器的主要组成部分：
*   **主译码器**：接收7位操作码（op）字段，并产生大部分控制信号。
*   **ALU译码器**：接收ALU操作码（ALUOp）和指令中的几位字段，产生3位ALU控制信号。
*   **PC源逻辑**：在发生分支（且条件为零）或执行跳转指令时，决定如何更新程序计数器。

### 主译码器

![](img/5946d95f116a18f7be260544864ccd36_37.png)

主译码器采用查找表（真值表）的方式实现。在SystemVerilog中，通常使用`case`语句来描述。

为了提高代码可读性和可维护性，我们定义一个11位的总线`controls`来集中存放所有控制信号。在`case`语句中为`controls`赋值，然后再将其拆分到各个独立的控制信号输出。

![](img/5946d95f116a18f7be260544864ccd36_39.png)

例如，对于R型指令（操作码`0110011`），控制信号组合为：
*   `regwrite = 1`（寄存器写使能）
*   `immsrc = xx`（立即数源，不关心）
*   `alusrc = 0`（ALU源B选择寄存器文件）
*   `branch = 0`（非分支指令）
*   `memwrite = 0`（不写内存）
*   `resultsrc = 00`（结果来自ALU）
*   `jump = 0`（非跳转指令）
*   `aluop = 10`（需查看指令功能字段）

![](img/5946d95f116a18f7be260544864ccd36_41.png)

![](img/5946d95f116a18f7be260544864ccd36_43.png)

```systemverilog
always_comb begin
    case(op)
        7'b0110011: controls = 11'b1_xx_0_0_0_00_0_10; // R-type
        // ... 其他指令 ...
        default: controls = 11'bxxxxxxxxxxx; // 非法指令
    endcase
end
// 拆分控制信号
assign {regwrite, immsrc, alusrc, branch, memwrite, resultsrc, jump, aluop} = controls;
```

![](img/5946d95f116a18f7be260544864ccd36_45.png)

![](img/5946d95f116a18f7be260544864ccd36_47.png)

### ALU译码器

ALU译码器也以真值表形式描述。它根据`ALUOp`信号和指令中的功能字段（`funct3`和`funct7`），产生具体的`ALUControl`信号。

![](img/5946d95f116a18f7be260544864ccd36_49.png)

![](img/5946d95f116a18f7be260544864ccd36_51.png)

## 数据通路

数据通路包含实现处理器功能所需的所有硬件组件。

以下是数据通路中的关键组件及其连接：
1.  **程序计数器（PC）逻辑**：包含一个PC寄存器、一个计算PC+4的加法器、一个计算分支目标地址的加法器，以及一个多路选择器用于在PC+4、分支目标或跳转目标之间选择下一个PC值。选择由`pcsrc`控制信号控制。
2.  **寄存器文件**：包含32个32位寄存器。它有两个读端口（根据地址`ra1`和`ra2`输出数据`rd1`和`rd2`）和一个写端口（在时钟上升沿，若写使能`we3`为真，则将数据`wd3`写入地址`wa3`）。寄存器`x0`被硬连线为零。
3.  **立即数扩展器**：根据`immsrc`控制信号，将指令中的立即数字段符号扩展为32位。支持I型、S型、B型和U型指令的立即数格式。
4.  **算术逻辑单元（ALU）**：接收两个32位输入`srcA`和`srcB`，根据`alucontrol`信号执行指定操作，输出32位结果`aluresult`和一个`zero`标志位（当结果为0时置位）。输入`srcB`由一个多路选择器提供，该选择器在寄存器文件读出的数据`rd2`和扩展后的立即数之间选择，由`alusrc`信号控制。
5.  **结果选择多路器**：根据`resultsrc`信号，选择将ALU结果、数据存储器读取的数据或PC+4作为最终结果写回寄存器文件。

![](img/5946d95f116a18f7be260544864ccd36_53.png)

### 立即数扩展逻辑

立即数扩展逻辑根据`immsrc`信号，将指令中的不同位段组合并符号扩展为32位立即数。

![](img/5946d95f116a18f7be260544864ccd36_55.png)

```systemverilog
always_comb begin
    case(immsrc)
        2'b00: immext = {{20{instr[31]}}, instr[31:20]}; // I-type
        2'b01: immext = {{20{instr[31]}}, instr[31:25], instr[11:7]}; // S-type
        2'b10: immext = {{20{instr[31]}}, instr[7], instr[30:25], instr[11:8], 1'b0}; // B-type
        2'b11: immext = {instr[31:12], 12'b0}; // U-type
    endcase
end
```

![](img/5946d95f116a18f7be260544864ccd36_57.png)

![](img/5946d95f116a18f7be260544864ccd36_59.png)

### 寄存器文件

![](img/5946d95f116a18f7be260544864ccd36_61.png)

![](img/5946d95f116a18f7be260544864ccd36_62.png)

寄存器文件是一个标准的三端口（两读一写）同步存储器。

![](img/5946d95f116a18f7be260544864ccd36_64.png)

其关键操作如下：
*   **写操作**：在时钟上升沿，如果写使能`we3`为真且目标地址`wa3`非零，则将数据`wd3`写入`wa3`地址对应的寄存器。向`x0`（地址0）的写入被忽略。
*   **读操作**：组合逻辑输出。如果读地址为0，则输出零；否则输出对应寄存器的值。

```systemverilog
// 寄存器数组
logic [31:0] rf [31:0];
// 写操作
always_ff @(posedge clk) begin
    if (we3 && wa3 != 0) rf[wa3] <= wd3;
end
// 读操作
assign rd1 = (ra1 != 0) ? rf[ra1] : 0;
assign rd2 = (ra2 != 0) ? rf[ra2] : 0;
```

## 其他基本组件

![](img/5946d95f116a18f7be260544864ccd36_66.png)

最后，我们回顾一下数据通路中使用的基本组件的Verilog实现惯用法。

![](img/5946d95f116a18f7be260544864ccd36_67.png)

![](img/5946d95f116a18f7be260544864ccd36_69.png)

以下是常用组件的代码示例：
*   **加法器**：`assign y = a + b;`
*   **可复位的触发器**：
    ```systemverilog
    always_ff @(posedge clk, posedge reset) begin
        if (reset) q <= 0;
        else q <= d;
    end
    ```
*   **2输入多路选择器**：`assign y = s ? d1 : d0;`

## 总结

![](img/5946d95f116a18f7be260544864ccd36_71.png)

本节课中我们一起学习了如何用SystemVerilog实现一个RISC-V单周期处理器。我们从测试平台和顶层模块开始，逐步深入到处理器内部的控制器和数据通路。我们看到，处理器的硬件结构图可以直接对应到SystemVerilog代码中的各个模块和连接。实现的关键在于理解每个硬件组件的功能，并使用正确的Verilog惯用法来描述它们，例如使用`case`语句实现译码器，使用`always_ff`块描述同步寄存器，以及使用连续赋值语句`assign`描述组合逻辑。通过这种自顶向下、模块化的设计方法，我们可以清晰地构建出复杂的数字系统。