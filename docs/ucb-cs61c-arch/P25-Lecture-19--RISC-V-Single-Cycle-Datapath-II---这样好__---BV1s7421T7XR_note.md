![](img/65cde3ea2a06440d50b8a7aca51197c0_0.png)

# 🧠 课程 P25：第19讲 - RISC-V 单周期数据通路 II

在本节课中，我们将继续学习如何构建一个RISC-V单周期CPU的数据通路。我们将重点关注如何实现加载（Load）、存储（Store）、分支（Branch）和跳转（Jump）等指令，并理解即时数生成（Immediate Generation）模块的工作原理。

![](img/65cde3ea2a06440d50b8a7aca51197c0_2.png)

![](img/65cde3ea2a06440d50b8a7aca51197c0_4.png)

---

![](img/65cde3ea2a06440d50b8a7aca51197c0_6.png)

![](img/65cde3ea2a06440d50b8a7aca51197c0_8.png)

![](img/65cde3ea2a06440d50b8a7aca51197c0_10.png)

## 📊 数据通路现状回顾

![](img/65cde3ea2a06440d50b8a7aca51197c0_12.png)

![](img/65cde3ea2a06440d50b8a7aca51197c0_14.png)

![](img/65cde3ea2a06440d50b8a7aca51197c0_16.png)

上一节我们介绍了加法（ADD）、减法（SUB）和立即数加法（ADDI）指令的数据通路实现。本节中，我们来看看如何将内存访问和程序控制流指令集成到这个框架中。

![](img/65cde3ea2a06440d50b8a7aca51197c0_18.png)

![](img/65cde3ea2a06440d50b8a7aca51197c0_20.png)

目前，我们的数据通路已经包含了程序计数器（PC）、指令存储器、寄存器文件、算术逻辑单元（ALU）以及一个控制单元。然而，我们还没有将数据存储器（Data Memory）连接到系统中。

![](img/65cde3ea2a06440d50b8a7aca51197c0_22.png)

![](img/65cde3ea2a06440d50b8a7aca51197c0_24.png)

![](img/65cde3ea2a06440d50b8a7aca51197c0_26.png)

![](img/65cde3ea2a06440d50b8a7aca51197c0_28.png)

![](img/65cde3ea2a06440d50b8a7aca51197c0_0.png)

![](img/65cde3ea2a06440d50b8a7aca51197c0_30.png)

![](img/65cde3ea2a06440d50b8a7aca51197c0_32.png)

![](img/65cde3ea2a06440d50b8a7aca51197c0_34.png)

数据通路的工作流程如下：
1.  **PC** 存储当前指令地址。
2.  指令存储器根据PC的地址读取指令。
3.  指令被解码，控制单元产生相应的控制信号。
4.  寄存器文件根据指令中的 `rs1` 和 `rs2` 字段读取数据。
5.  **B选择多路复用器（MUX）** 决定ALU的第二个操作数是来自寄存器 `rs2` 还是来自即时数生成模块。
6.  ALU执行计算。
7.  结果可能被写回寄存器文件（对于算术指令）。

![](img/65cde3ea2a06440d50b8a7aca51197c0_36.png)

整个操作是**边沿触发**的。在时钟上升沿，寄存器文件会根据 `RegWrite` 控制信号决定是否将数据写入目标寄存器 `rd`。

![](img/65cde3ea2a06440d50b8a7aca51197c0_38.png)

---

## 🧳 实现加载指令（LW）

![](img/65cde3ea2a06440d50b8a7aca51197c0_40.png)

加载指令（如 `lw rd, offset(rs1)`）用于从内存中读取一个字并存入寄存器。它使用 **I-type** 格式。

![](img/65cde3ea2a06440d50b8a7aca51197c0_42.png)

![](img/65cde3ea2a06440d50b8a7aca51197c0_44.png)

![](img/65cde3ea2a06440d50b8a7aca51197c0_46.png)

以下是加载指令需要执行的操作：
1.  计算内存地址：`address = Reg[rs1] + sign-extend(offset)`
2.  从该地址读取内存数据。
3.  将读取到的数据写入目标寄存器 `rd`。
4.  将PC更新为下一条指令地址（PC+4）。

![](img/65cde3ea2a06440d50b8a7aca51197c0_48.png)

![](img/65cde3ea2a06440d50b8a7aca51197c0_50.png)

![](img/65cde3ea2a06440d50b8a7aca51197c0_52.png)

为了实现加载，我们需要在数据通路中添加两个新组件：
*   **数据存储器（D-Mem）**：用于读写数据。
*   **写回选择多路复用器（WB Select MUX）**：用于选择写回寄存器文件的数据是来自ALU的输出还是来自数据存储器的输出。

![](img/65cde3ea2a06440d50b8a7aca51197c0_54.png)

控制信号的变化：
*   **B选择（B-sel）**：设置为 `1`，选择即时数作为ALU的第二个操作数。
*   **ALU操作（ALU-op）**：设置为 `add`，用于计算地址。
*   **内存读/写（MemRW）**：设置为 `read`。
*   **写回选择（WB-sel）**：设置为 `1`，选择从数据存储器读取的数据写回寄存器。
*   **寄存器写使能（RegWrite）**：设置为 `1`，允许写回寄存器文件。

![](img/65cde3ea2a06440d50b8a7aca51197c0_56.png)

![](img/65cde3ea2a06440d50b8a7aca51197c0_38.png)

![](img/65cde3ea2a06440d50b8a7aca51197c0_58.png)

![](img/65cde3ea2a06440d50b8a7aca51197c0_60.png)

**注意**：RISC-V还有加载字节（LB）、加载半字（LH）等指令。它们的基本流程与 `LW` 相同，但在从内存读取完整字后，需要额外的逻辑来提取、符号扩展或零扩展相应的字节或半字。这通常通过额外的多路复用器和逻辑门实现。

![](img/65cde3ea2a06440d50b8a7aca51197c0_62.png)

---

![](img/65cde3ea2a06440d50b8a7aca51197c0_64.png)

![](img/65cde3ea2a06440d50b8a7aca51197c0_66.png)

## 📤 实现存储指令（SW）

![](img/65cde3ea2a06440d50b8a7aca51197c0_68.png)

存储指令（如 `sw rs2, offset(rs1)`）用于将寄存器的值存入内存。它使用 **S-type** 格式。

![](img/65cde3ea2a06440d50b8a7aca51197c0_70.png)

![](img/65cde3ea2a06440d50b8a7aca51197c0_72.png)

以下是存储指令需要执行的操作：
1.  计算内存地址：`address = Reg[rs1] + sign-extend(offset)`
2.  将寄存器 `rs2` 的值写入计算出的内存地址。
3.  将PC更新为下一条指令地址（PC+4）。

![](img/65cde3ea2a06440d50b8a7aca51197c0_74.png)

![](img/65cde3ea2a06440d50b8a7aca51197c0_76.png)

与加载指令的关键区别在于：
*   需要同时读取 `rs1`（基地址）和 `rs2`（要存储的数据）两个寄存器。
*   向数据存储器执行**写**操作。
*   **不更新**寄存器文件。

![](img/65cde3ea2a06440d50b8a7aca51197c0_78.png)

![](img/65cde3ea2a06440d50b8a7aca51197c0_80.png)

![](img/65cde3ea2a06440d50b8a7aca51197c0_81.png)

![](img/65cde3ea2a06440d50b8a7aca51197c0_82.png)

![](img/65cde3ea2a06440d50b8a7aca51197c0_83.png)

控制信号的变化：
*   **即时数选择（Imm-sel）**：设置为 `S`，表示S-type即时数格式。
*   **B选择（B-sel）**：设置为 `1`，选择即时数。
*   **ALU操作（ALU-op）**：设置为 `add`，用于计算地址。
*   **内存读/写（MemRW）**：设置为 `write`。
*   **寄存器写使能（RegWrite）**：设置为 `0`，因为不写回寄存器。

对于存储指令，**写回选择（WB-sel）** 信号是“无关项”（don‘t care）。因为 `RegWrite` 为 `0`，无论WB-sel选择什么，都不会对寄存器文件产生实际影响。

![](img/65cde3ea2a06440d50b8a7aca51197c0_85.png)

![](img/65cde3ea2a06440d50b8a7aca51197c0_87.png)

![](img/65cde3ea2a06440d50b8a7aca51197c0_64.png)

---

## 🚦 实现分支指令（BEQ, BNE, BLT等）

![](img/65cde3ea2a06440d50b8a7aca51197c0_89.png)

![](img/65cde3ea2a06440d50b8a7aca51197c0_91.png)

![](img/65cde3ea2a06440d50b8a7aca51197c0_93.png)

分支指令（如 `beq rs1, rs2, offset`）用于实现条件跳转。它使用 **B-type** 格式。

![](img/65cde3ea2a06440d50b8a7aca51197c0_95.png)

![](img/65cde3ea2a06440d50b8a7aca51197c0_97.png)

![](img/65cde3ea2a06440d50b8a7aca51197c0_99.png)

分支指令需要执行的操作：
1.  比较寄存器 `rs1` 和 `rs2` 的值。
2.  根据比较结果和分支类型（如相等、不相等、小于等），决定是否跳转。
3.  如果跳转（分支被采纳），则 `PC = PC + sign-extend(offset)`
4.  如果不跳转（分支未被采纳），则 `PC = PC + 4`

![](img/65cde3ea2a06440d50b8a7aca51197c0_101.png)

![](img/65cde3ea2a06440d50b8a7aca51197c0_103.png)

![](img/65cde3ea2a06440d50b8a7aca51197c0_105.png)

这引入了新的挑战：我们需要在同一个周期内进行**比较**和**计算两个可能的目标地址**（PC+4 和 PC+offset）。

![](img/65cde3ea2a06440d50b8a7aca51197c0_107.png)

![](img/65cde3ea2a06440d50b8a7aca51197c0_109.png)

解决方案是引入一个**分支比较器（Branch Comparator）** 模块和额外的地址计算硬件。

![](img/65cde3ea2a06440d50b8a7aca51197c0_111.png)

**分支比较器模块**：
*   **输入**：`rs1` 和 `rs2` 的数据值，以及一个控制信号 `BrUn`（表示是无符号比较）。
*   **输出**：两个标志位 `BrEq`（相等）和 `BrLt`（小于）。
*   控制逻辑根据指令类型（如 `BEQ`, `BLT`, `BGE`）和比较器输出的 `BrEq`、`BrLt` 信号，生成最终的 `PC-sel` 信号，以选择下一个PC值是 `PC+4` 还是 `PC+offset`。

**地址计算**：
*   `PC+4` 由已有的加法器计算。
*   `PC+offset` 由ALU计算。此时，通过 **A选择（A-sel）** 多路复用器选择PC（而不是`rs1`）作为ALU的第一个操作数，通过 **B选择（B-sel）** 选择即时数作为第二个操作数，然后执行加法。

![](img/65cde3ea2a06440d50b8a7aca51197c0_107.png)

![](img/65cde3ea2a06440d50b8a7aca51197c0_113.png)

![](img/65cde3ea2a06440d50b8a7aca51197c0_115.png)

![](img/65cde3ea2a06440d50b8a7aca51197c0_117.png)

---

![](img/65cde3ea2a06440d50b8a7aca51197c0_119.png)

![](img/65cde3ea2a06440d50b8a7aca51197c0_121.png)

## 🧩 即时数生成模块详解

不同的指令格式（I-type, S-type, B-type, J-type, U-type）其即时数在32位指令字中的位置和拼接方式都不同。即时数生成模块的作用就是根据**即时数选择（Imm-sel）** 控制信号，从指令中提取正确的位，并进行符号扩展，生成一个统一的32位即时数。

以下是核心的拼接逻辑（假设指令位从高到低编号为31到0）：

![](img/65cde3ea2a06440d50b8a7aca51197c0_123.png)

*   **公共部分**：所有类型的即时数，其最高位（指令位31）都用于符号扩展。
*   **I-type (e.g., ADDI, LW)**：
    *   即时数位[11:0] = 指令位[31:20]
*   **S-type (e.g., SW)**：
    *   即时数位[11:5] = 指令位[31:25]
    *   即时数位[4:0] = 指令位[11:7]
*   **B-type (e.g., BEQ)**：
    *   即时数位[12, 10:5, 4:1, 11] = 指令位[31, 30:25, 11:8, 7]
    *   *注意：B-type即时数的最低位总是0（因为地址按半字对齐），这与S-type不同。*
*   **J-type (e.g., JAL)** 和 **U-type (e.g., LUI, AUIPC)** 也有各自独特的位拼接模式。

![](img/65cde3ea2a06440d50b8a7aca51197c0_125.png)

![](img/65cde3ea2a06440d50b8a7aca51197c0_127.png)

在硬件上，这个模块由一系列将指令特定位连接到输出即时数特定位的连线，以及根据 `Imm-sel` 信号选择不同输入源的多路复用器构成。

![](img/65cde3ea2a06440d50b8a7aca51197c0_129.png)

![](img/65cde3ea2a06440d50b8a7aca51197c0_133.png)

---

![](img/65cde3ea2a06440d50b8a7aca51197c0_131.png)

![](img/65cde3ea2a06440d50b8a7aca51197c0_133.png)

## 🦘 实现跳转指令（JAL, JALR）

跳转指令用于无条件改变程序流。

**1. JAL (Jump and Link) - J-type**
*   **操作**：`PC = PC + offset`; `Reg[rd] = PC + 4`
*   **用途**：实现函数调用，将返回地址（PC+4）保存到 `rd`（通常为 `x1` 链接寄存器）。
*   **数据通路**：类似于分支，但总是采纳跳转。使用ALU计算 `PC + offset`，并通过新增的路径将 `PC+4` 值写入寄存器文件。

![](img/65cde3ea2a06440d50b8a7aca51197c0_135.png)

![](img/65cde3ea2a06440d50b8a7aca51197c0_137.png)

![](img/65cde3ea2a06440d50b8a7aca51197c0_139.png)

**2. JALR (Jump and Link Register) - I-type**
*   **操作**：`PC = Reg[rs1] + offset`; `Reg[rd] = PC + 4`
*   **用途**：用于从函数返回或间接跳转。
*   **数据通路**：类似于JAL，但目标地址的计算是 `Reg[rs1] + offset` 而不是 `PC + offset`。因此，A选择多路复用器选择 `rs1`。

![](img/65cde3ea2a06440d50b8a7aca51197c0_141.png)

![](img/65cde3ea2a06440d50b8a7aca51197c0_149.png)

![](img/65cde3ea2a06440d50b8a7aca51197c0_143.png)

---

## ⬆️ 实现U-type指令（LUI, AUIPC）

![](img/65cde3ea2a06440d50b8a7aca51197c0_145.png)

![](img/65cde3ea2a06440d50b8a7aca51197c0_147.png)

U-type指令用于操作大即时数。

![](img/65cde3ea2a06440d50b8a7aca51197c0_149.png)

**1. LUI (Load Upper Immediate)**
*   **操作**：`Reg[rd] = immediate << 12`
*   **用途**：将20位即时数加载到寄存器的高20位，低12位置零。用于构建大的常数。
*   **数据通路**：即时数生成模块产生U-type即时数（高20位来自指令，低12位为0）。通过**写回选择（WB-sel）** 多路复用器的一个新输入（例如，选择“即时数”本身），直接将这个值写回寄存器文件。ALU可能不被使用，或者用于执行“加零”操作。

![](img/65cde3ea2a06440d50b8a7aca51197c0_151.png)

**2. AUIPC (Add Upper Immediate to PC)**
*   **操作**：`Reg[rd] = PC + (immediate << 12)`
*   **用途**：构建相对于PC的大偏移量地址，常用于位置无关代码。
*   **数据通路**：与LUI类似，但需要ALU将PC与U-type即时数相加，然后将结果写回寄存器文件。

![](img/65cde3ea2a06440d50b8a7aca51197c0_153.png)

![](img/65cde3ea2a06440d50b8a7aca51197c0_165.png)

![](img/65cde3ea2a06440d50b8a7aca51197c0_155.png)

![](img/65cde3ea2a06440d50b8a7aca51197c0_157.png)

---

![](img/65cde3ea2a06440d50b8a7aca51197c0_159.png)

![](img/65cde3ea2a06440d50b8a7aca51197c0_161.png)

## 📝 总结

![](img/65cde3ea2a06440d50b8a7aca51197c0_163.png)

![](img/65cde3ea2a06440d50b8a7aca51197c0_165.png)

本节课中我们一起学习了如何扩展RISC-V单周期数据通路以支持更多指令：

![](img/65cde3ea2a06440d50b8a7aca51197c0_167.png)

1.  **加载/存储指令**：引入了数据存储器和写回选择多路复用器，理解了内存读写的控制流程。
2.  **分支指令**：引入了分支比较器模块，学习了如何通过硬件并行计算和选择来条件更新PC。
3.  **跳转指令**：学习了无条件跳转的实现，以及如何保存返回地址。
4.  **U-type指令**：了解了如何处理大即时数，并构建相关地址。
5.  **核心模块**：深入理解了**即时数生成模块**如何通过多路复用和位拼接，为不同格式的指令生成统一的32位即时数。

通过将这些部件全部集成，我们完成了一个能够执行RISC-V基础整数指令集（RV32I）中大部分指令的**单周期CPU数据通路**设计。这是一个重要的里程碑，它为我们理解更复杂的多周期或流水线CPU奠定了基础。

![](img/65cde3ea2a06440d50b8a7aca51197c0_169.png)

![](img/65cde3ea2a06440d50b8a7aca51197c0_171.png)

![](img/65cde3ea2a06440d50b8a7aca51197c0_173.png)

![](img/65cde3ea2a06440d50b8a7aca51197c0_175.png)

![](img/65cde3ea2a06440d50b8a7aca51197c0_175.png)