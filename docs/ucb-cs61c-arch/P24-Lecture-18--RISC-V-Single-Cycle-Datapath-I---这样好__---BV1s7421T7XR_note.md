![](img/3c5dbac18c72a5b3cb44e1e02a09fdef_0.png)

# 课程 P24：第18讲 - RISC-V 单周期数据通路 I 🧠

在本节课中，我们将开始构建一个CPU。我们将把过去几周学到的关于电路、门和延迟的概念整合起来，从一个小模块——数据通路——开始构建。本节课和下一节课将专注于理解并设计一个能够执行RISC-V ISA指令的简单单周期处理器。

---

![](img/3c5dbac18c72a5b3cb44e1e02a09fdef_2.png)

## 概述：从抽象到实现

![](img/3c5dbac18c72a5b3cb44e1e02a09fdef_4.png)

在计算机系统的抽象层次中，我们正从底层的逻辑门向上构建，目标是到达指令集架构（ISA）层。我们之前从高级语言开始向下探索，现在我们将从底层硬件向上构建，最终在ISA层汇合。

![](img/3c5dbac18c72a5b3cb44e1e02a09fdef_6.png)

![](img/3c5dbac18c72a5b3cb44e1e02a09fdef_8.png)

处理器可以看作由两个主要部分组成：**数据通路**和**控制单元**。数据通路包含执行实际操作（如算术运算）的硬件（如寄存器、ALU），而控制单元则是“大脑”，它告诉数据通路该执行什么操作。

![](img/3c5dbac18c72a5b3cb44e1e02a09fdef_10.png)

---

![](img/3c5dbac18c72a5b3cb44e1e02a09fdef_12.png)

## 核心构建模块回顾 🔧

在开始连接数据通路之前，我们先回顾几个将要用到的基本逻辑模块。我们将以框图的形式来思考它们，而不是具体的门电路。

![](img/3c5dbac18c72a5b3cb44e1e02a09fdef_14.png)

### 多路复用器 (Mux)

![](img/3c5dbac18c72a5b3cb44e1e02a09fdef_16.png)

多路复用器根据一个选择信号，在两个输入之间选择一个作为输出。

*   **功能**：在输入A和B之间选择。
*   **控制**：选择信号 `S`。
*   **行为**：
    *   如果 `S = 1`，则输出 `C = A`。
    *   如果 `S = 0`，则输出 `C = B`。

### 加法器 (Adder)

![](img/3c5dbac18c72a5b3cb44e1e02a09fdef_18.png)

加法器将两个n位数值相加。

![](img/3c5dbac18c72a5b3cb44e1e02a09fdef_20.png)

![](img/3c5dbac18c72a5b3cb44e1e02a09fdef_22.png)

*   **功能**：计算 `A + B`。
*   **输入**：两个n位值 `A` 和 `B`。
*   **输出**：n位和 `S`，可能还有进位信号。

![](img/3c5dbac18c72a5b3cb44e1e02a09fdef_24.png)

### 算术逻辑单元 (ALU)

![](img/3c5dbac18c72a5b3cb44e1e02a09fdef_26.png)

ALU可以执行多种算术和逻辑操作，具体操作由一个选择信号决定。

*   **功能**：对输入 `A` 和 `B` 执行指定操作（如加、减、异或）。
*   **控制**：`ALUop` 选择信号，决定执行哪种操作。
*   **输出**：操作结果 `Result`。

![](img/3c5dbac18c72a5b3cb44e1e02a09fdef_28.png)

### 状态元素：寄存器与存储器

CPU将组合逻辑模块（如Mux、ALU）与状态元素（如寄存器、存储器）结合起来。状态元素在时钟的控制下存储信息。

*   **同步系统**：在时钟的每个上升沿，状态元素可能会更新。在其他时间，它们输出当前存储的值。
*   **关键概念**：组合逻辑块的输出会立即传递，但状态元素只在时钟上升沿“捕获”输入值进行更新。

![](img/3c5dbac18c72a5b3cb44e1e02a09fdef_30.png)

---

## 处理器中的状态元素 🗃️

![](img/3c5dbac18c72a5b3cb44e1e02a09fdef_32.png)

在我们的CPU执行过程中，每个时钟周期可能会更新以下几个状态元素。

### 程序计数器 (PC)

![](img/3c5dbac18c72a5b3cb44e1e02a09fdef_34.png)

![](img/3c5dbac18c72a5b3cb44e1e02a09fdef_36.png)

PC是一个存储当前指令地址的寄存器。

![](img/3c5dbac18c72a5b3cb44e1e02a09fdef_38.png)

*   **行为**：在时钟上升沿且写使能有效时，用输入数据更新其输出。其他时间，它持续输出当前地址。

### 寄存器文件 (Register File)

寄存器文件是一组寄存器（如RISC-V的32个寄存器）的集合。

![](img/3c5dbac18c72a5b3cb44e1e02a09fdef_40.png)

*   **读取**：随时可以读取 `rs1` 和 `rs2` 指定寄存器的值。
*   **写入**：在时钟上升沿且写使能 (`RegWEn`) 有效时，将数据 `dataW` 写入 `rd` 指定的寄存器。

![](img/3c5dbac18c72a5b3cb44e1e02a09fdef_42.png)

![](img/3c5dbac18c72a5b3cb44e1e02a09fdef_44.png)

### 存储器 (Memory)

我们将存储器视为一个“黑盒”。为了简化设计，我们将其分为两个部分：
*   **指令存储器 (IMem)**：只读，存储所有指令。
*   **数据存储器 (DMem)**：可读写，存储程序数据。

![](img/3c5dbac18c72a5b3cb44e1e02a09fdef_46.png)

*   **读取**：给定地址 `addr`，输出该地址的数据 `readData`。
*   **写入**：在时钟上升沿且写使能 (`MemRW`) 有效时，将数据 `dataW` 写入地址 `addr`。

![](img/3c5dbac18c72a5b3cb44e1e02a09fdef_48.png)

![](img/3c5dbac18c72a5b3cb44e1e02a09fdef_50.png)

---

## 单周期处理器执行阶段 🔄

![](img/3c5dbac18c72a5b3cb44e1e02a09fdef_52.png)

![](img/3c5dbac18c72a5b3cb44e1e02a09fdef_54.png)

![](img/3c5dbac18c72a5b3cb44e1e02a09fdef_56.png)

将所有功能一次性连接起来非常复杂。因此，我们将指令执行过程分解为几个概念阶段，这使设计、调试和优化变得更容易。

以 `lw` (加载字) 指令为例，其执行阶段可概括为：
1.  **取指 (Fetch)**：根据PC值从指令存储器读取指令。
2.  **译码 (Decode)**：解析指令，确定操作类型和所需的寄存器。
3.  **执行 (Execute)**：在ALU中计算内存地址（例如，寄存器值+立即数）。
4.  **访存 (Memory Access)**：从数据存储器读取数据。
5.  **写回 (Write Back)**：将读出的数据写回目标寄存器。

![](img/3c5dbac18c72a5b3cb44e1e02a09fdef_58.png)

同时，**PC会更新为下一条指令的地址（PC+4）**。所有这些操作都在**一个时钟周期**内完成，因此称为“单周期”处理器。控制单元负责协调每个阶段数据通路需要完成的工作。

![](img/3c5dbac18c72a5b3cb44e1e02a09fdef_60.png)

![](img/3c5dbac18c72a5b3cb44e1e02a09fdef_62.png)

![](img/3c5dbac18c72a5b3cb44e1e02a09fdef_64.png)

---

![](img/3c5dbac18c72a5b3cb44e1e02a09fdef_66.png)

## 构建第一个简单数据通路 🧱

![](img/3c5dbac18c72a5b3cb44e1e02a09fdef_68.png)

让我们从最简单的指令开始，逐步构建数据通路。

### 示例1：仅支持 `add` 指令的处理器

假设我们的ISA只有一条指令：`add rd, rs1, rs2`。

![](img/3c5dbac18c72a5b3cb44e1e02a09fdef_70.png)

![](img/3c5dbac18c72a5b3cb44e1e02a09fdef_71.png)

我们需要更新的状态：
1.  PC: `PC = PC + 4`
2.  寄存器文件：目标寄存器 `rd` 的值更新为 `rs1 + rs2`。

![](img/3c5dbac18c72a5b3cb44e1e02a09fdef_73.png)

![](img/3c5dbac18c72a5b3cb44e1e02a09fdef_75.png)

以下是该数据通路的关键连接步骤：

![](img/3c5dbac18c72a5b3cb44e1e02a09fdef_77.png)

![](img/3c5dbac18c72a5b3cb44e1e02a09fdef_79.png)

![](img/3c5dbac18c72a5b3cb44e1e02a09fdef_81.png)

![](img/3c5dbac18c72a5b3cb44e1e02a09fdef_83.png)

*   **PC更新**：PC的输出连接到“加4”模块，其结果反馈回PC的输入，以便在下一个时钟沿更新。
*   **取指与译码**：PC值也作为地址输入指令存储器(IMem)，读取32位指令。指令的特定字段（位[11:7]为`rd`，[19:15]为`rs1`，[24:20]为`rs2`）被拆分出来，连接到寄存器文件。
*   **执行**：寄存器文件输出的 `data1` (rs1值) 和 `data2` (rs2值) 送入加法器。
*   **写回**：加法器的结果连接到寄存器文件的写入数据端 `dataW`。控制单元需产生寄存器写使能信号 `RegWEn`。

![](img/3c5dbac18c72a5b3cb44e1e02a09fdef_85.png)

![](img/3c5dbac18c72a5b3cb44e1e02a09fdef_87.png)

通过以上连接，我们得到了一个只能做加法的处理器。

### 示例2：支持 `add` 和 `sub` 指令

![](img/3c5dbac18c72a5b3cb44e1e02a09fdef_89.png)

`add` 和 `sub` 指令格式相似，主要区别在于 `funct7` 字段（指令位[30]）的值不同。我们需要将加法器替换为功能更丰富的ALU。

![](img/3c5dbac18c72a5b3cb44e1e02a09fdef_91.png)

![](img/3c5dbac18c72a5b3cb44e1e02a09fdef_93.png)

数据通路的变化：
*   将加法器块替换为ALU块。
*   ALU需要接收一个 `ALUop` 选择信号来决定做加法还是减法。
*   控制单元会检查指令的 `funct7` 字段（位30），并据此设置 `ALUop` 信号（例如，0为加，1为减）。

![](img/3c5dbac18c72a5b3cb44e1e02a09fdef_95.png)

![](img/3c5dbac18c72a5b3cb44e1e02a09fdef_97.png)

**控制与数据通路的类比**：可以将数据通路想象成国际空间站(ISS)，它能力强大但需要指导；控制单元就像地面任务控制中心，它分析情况（指令），然后向数据通路发送精确的命令（控制信号），告诉它具体做什么操作。

![](img/3c5dbac18c72a5b3cb44e1e02a09fdef_99.png)

![](img/3c5dbac18c72a5b3cb44e1e02a09fdef_101.png)

![](img/3c5dbac18c72a5b3cb44e1e02a09fdef_103.png)

### 示例3：支持 `addi` 指令

![](img/3c5dbac18c72a5b3cb44e1e02a09fdef_105.png)

![](img/3c5dbac18c72a5b3cb44e1e02a09fdef_107.png)

`addi` (立即数加法) 是I-type指令，格式与R-type不同。它将寄存器 `rs1` 的值与一个12位立即数相加。

![](img/3c5dbac18c72a5b3cb44e1e02a09fdef_109.png)

![](img/3c5dbac18c72a5b3cb44e1e02a09fdef_111.png)

![](img/3c5dbac18c72a5b3cb44e1e02a09fdef_113.png)

![](img/3c5dbac18c72a5b3cb44e1e02a09fdef_115.png)

数据通路需要的新改动：
*   **立即数生成**：需要一个模块从指令的特定位（如位[31:20]）提取并符号扩展为32位立即数。
*   **ALU输入选择**：ALU的第二个输入不再总是来自 `rs2`，对于 `addi`，它应来自立即数。因此，需要在 `data2`（来自寄存器文件）和“立即数”之间添加一个多路复用器。
*   **新增控制信号**：控制单元需产生一个新的信号（如 `BSelect`）来控制上述多路复用器，选择立即数作为ALU输入。

**立即数生成模块的直觉**：为了从指令的12位字段生成32位立即数，需要将高位进行符号扩展。即，将12位立即数的最高位（符号位）复制，填充到32位立即数的高20位。

![](img/3c5dbac18c72a5b3cb44e1e02a09fdef_117.png)

![](img/3c5dbac18c72a5b3cb44e1e02a09fdef_119.png)

---

![](img/3c5dbac18c72a5b3cb44e1e02a09fdef_121.png)

![](img/3c5dbac18c72a5b3cb44e1e02a09fdef_123.png)

## 总结 📚

![](img/3c5dbac18c72a5b3cb44e1e02a09fdef_125.png)

![](img/3c5dbac18c72a5b3cb44e1e02a09fdef_127.png)

本节课我们一起学习了构建RISC-V单周期处理器的初步知识。

![](img/3c5dbac18c72a5b3cb44e1e02a09fdef_129.png)

*   我们理解了CPU由**数据通路**（执行部件）和**控制单元**（指挥部件）构成。
*   我们回顾了多路复用器、加法器、ALU、寄存器、存储器等核心硬件模块的抽象功能。
*   我们引入了将指令执行分为多个**阶段**（取指、译码、执行、访存、写回）的概念，这简化了设计。
*   我们通过三个渐进示例，动手构建了数据通路：
    1.  仅支持 `add` 指令的简单通路。
    2.  通过引入ALU和控制，扩展支持 `add` 和 `sub` 指令。
    3.  通过添加立即数生成器和输入选择多路复用器，进一步支持 `addi` 指令。

![](img/3c5dbac18c72a5b3cb44e1e02a09fdef_131.png)

![](img/3c5dbac18c72a5b3cb44e1e02a09fdef_133.png)

![](img/3c5dbac18c72a5b3cb44e1e02a09fdef_135.png)

我们看到了控制信号（如 `RegWEn`， `ALUop`， `BSelect`）如何根据不同的指令，引导数据在通路中正确流动并执行相应操作。下一讲我们将继续完善数据通路，加入对分支、跳转和存储器访问指令的支持。