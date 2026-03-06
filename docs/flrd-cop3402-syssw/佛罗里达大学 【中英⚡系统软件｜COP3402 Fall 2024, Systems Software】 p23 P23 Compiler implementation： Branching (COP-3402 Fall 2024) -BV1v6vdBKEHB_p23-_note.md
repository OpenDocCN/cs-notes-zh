# 系统软件：COP3402：编译器实现 - 分支处理 🧭

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_1.png)

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_2.png)

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_4.png)

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_6.png)

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_7.png)

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_9.png)

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_11.png)

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_13.png)

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_15.png)

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_16.png)

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_18.png)

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_20.png)

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_21.png)

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_23.png)

在本节课中，我们将学习如何为我们的中间表示（IR）编译器实现分支功能。我们将探讨如何将简单IR中的条件跳转和无条件跳转指令转换为Intel x86-64汇编代码。上一节我们介绍了算术运算的代码生成，本节中我们来看看更复杂的控制流处理。

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_25.png)

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_27.png)

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_29.png)

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_31.png)

## 概述 📋

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_33.png)

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_35.png)

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_36.png)

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_38.png)

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_40.png)

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_42.png)

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_44.png)

编译器后端的主要任务之一是将高级控制流结构（如条件语句和循环）转换为目标机器的低级跳转指令。在简单IR中，我们使用 `if-goto` 和 `goto` 指令来表示分支。在x86-64汇编中，对应的概念是条件跳转和无条件跳转指令（如 `JMP`, `JLE`, `JG` 等）。实现分支的关键在于理解如何设置条件码（标志寄存器）以及如何根据这些标志生成正确的跳转指令。

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_46.png)

## 1. 分支的基本概念与目标 🎯

我们的目标是将简单IR中的分支指令转换为等价的Intel汇编指令。

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_48.png)

在简单IR中，分支指令如下所示：
```
L1:
    if x <= 10 goto L2
    x = 11
    goto L3
L2:
    x = x + 1
L3:
```

在x86-64汇编中，对应的结构使用标签和跳转指令：
```
L1:
    # 比较 x 和 10， 然后条件跳转
    ...
    jle L2
    # x = 11 的代码
    ...
    jmp L3
L2:
    # x = x + 1 的代码
L3:
```

**核心机制**：在底层，分支通过修改**指令指针寄存器（RIP）**来实现。`jmp` 或 `jle` 等指令会计算一个新的RIP值（当前RIP + 偏移量），从而改变下一条要执行的指令地址。

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_50.png)

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_52.png)

## 2. 从高级条件语句到低级分支的转换 🔄

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_54.png)

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_55.png)

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_57.png)

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_59.png)

高级语言中的结构化控制流（如 `if-else`, `while`）在汇编级别并不存在，必须用一系列跳转指令来模拟。

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_61.png)

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_63.png)

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_65.png)

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_67.png)

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_69.png)

以下是一个将C语言 `if` 语句转换为简单IR和汇编的思维过程示例：

C语言代码：
```c
if (x > 10) {
    x = 11;
} else {
    x = 20;
}
```

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_71.png)

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_73.png)

一种常见的转换策略是“跳过”策略。我们检查相反的条件，如果为真，则跳过 `if` 块，直接执行 `else` 块。

对应的简单IR可能是：
```
    if x <= 10 goto ELSE_LABEL  # 检查相反条件
    x = 11                      # if 块
    goto END_LABEL              # 跳过 else 块
ELSE_LABEL:
    x = 20                      # else 块
END_LABEL:
```

**关键点**：编译器通常会将条件“反转”，以便让“不成立”的分支去执行跳转，让“成立”的分支顺序执行紧随其后的代码。这样可以减少不必要的跳转指令。

## 3. 循环的转换示例 🔁

循环（如 `while`）可以看作是一个带跳转的 `if` 语句。

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_75.png)

C语言 `while` 循环：
```c
while (x > 0) {
    sum = sum + 1;
    x = x - 1;
}
```

转换为简单IR的一种方式（将条件检查放在循环头部）：
```
LOOP_HEAD:
    if x <= 0 goto LOOP_END   # 条件不成立则退出循环
    sum = sum + 1             # 循环体
    x = x - 1
    goto LOOP_HEAD            # 跳回头部进行下一次检查
LOOP_END:
```

另一种方式（`do-while`风格，将条件检查放在循环尾部）：
```
LOOP_BODY:
    sum = sum + 1             # 循环体至少执行一次
    x = x - 1
    if x > 0 goto LOOP_BODY   # 条件成立则继续循环
```

## 4. x86-64汇编中的条件跳转 ⚙️

在x86-64汇编中，实现条件分支需要两个步骤：
1.  **比较操作**：使用 `CMP` 指令设置标志寄存器。
2.  **条件跳转**：使用如 `JLE`（小于等于时跳转）、`JG`（大于时跳转）等指令，根据标志寄存器的状态决定是否跳转。

简单IR的 `if x <= y goto L` 指令在汇编中的实现模板如下：

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_77.png)

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_79.png)

```assembly
    movq    -8(%rbp), %rax    # 将变量 x 加载到 %rax
    movq    $10, %rbx         # 将立即数 10 加载到 %rbx
    cmpq    %rbx, %rax        # 比较 %rax 和 %rbx (计算 %rax - %rbx)
    jle     .L2               # 如果 %rax <= %rbx，则跳转到标签 .L2
```

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_81.png)

**公式解释**：
*   `CMP a, b` 指令在内部计算 `b - a`（AT&T语法），并根据结果设置标志位（如零标志ZF、符号标志SF、溢出标志OF等）。
*   条件跳转指令（如 `JLE`）会检查这些标志位的组合，以判断比较结果是否满足“小于或等于”的条件。

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_83.png)

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_85.png)

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_87.png)

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_89.png)

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_91.png)

以下是常用简单IR操作符对应的x86-64条件跳转指令：

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_93.png)

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_95.png)

| 简单IR操作符 | x86-64跳转指令 | 含义 |
| :--- | :--- | :--- |
| `==` | `je` | 相等则跳转 |
| `!=` | `jne` | 不相等则跳转 |
| `<` | `jl` | 小于则跳转 |
| `<=` | `jle` | 小于等于则跳转 |
| `>` | `jg` | 大于则跳转 |
| `>=` | `jge` | 大于等于则跳转 |

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_97.png)

## 5. 代码生成模板与项目实现 💻

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_99.png)

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_101.png)

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_103.png)

在CodeGen3项目中，你需要实现分支功能的代码生成。核心是填充以下几个函数：

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_105.png)

*   `generate_label(ir)`: 生成汇编标签，如 `L1:`。
*   `generate_goto(ir)`: 生成无条件跳转指令 `jmp L1`。
*   `generate_if_goto(ir)`: 生成条件跳转。这是最复杂的部分，需要：
    1.  生成加载两个操作数到寄存器（如 `%rax`, `%rbx`）的代码。
    2.  生成 `cmpq` 指令。
    3.  根据IR中的比较操作符（如 `<=`），选择正确的条件跳转指令（如 `jle`）并附上目标标签。

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_107.png)

以下是一个简化的Python伪代码示例，展示了 `generate_if_goto` 的逻辑：

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_109.png)

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_111.png)

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_113.png)

```python
def generate_if_goto(ir):
    left_operand = ir.left_operand  # 例如变量 ‘x‘
    right_operand = ir.right_operand # 例如常量 10
    op = ir.operator                # 例如 ‘<=‘
    label = ir.label                # 例如 ‘L2‘

    # 1. 加载左操作数到 %rax
    print(f"    movq    {get_operand_code(left_operand)}, %rax")
    # 2. 加载右操作数到 %rbx
    print(f"    movq    {get_operand_code(right_operand)}, %rbx")
    # 3. 比较
    print(f"    cmpq    %rbx, %rax")
    # 4. 根据操作符选择跳转指令
    jump_instruction = {
        ‘<‘: ‘jl‘,
        ‘<=‘: ‘jle‘,
        ‘>‘: ‘jg‘,
        ‘>=‘: ‘jge‘,
        ‘==‘: ‘je‘,
        ‘!=‘: ‘jne‘,
    }[op]
    # 5. 生成条件跳转
    print(f"    {jump_instruction}    {label}")
```

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_115.png)

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_117.png)

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_119.png)

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_121.png)

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_123.png)

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_125.png)

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_127.png)

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_129.png)

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_130.png)

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_132.png)

**辅助函数 `get_operand_code`** 需要能判断操作数是变量（如 `-8(%rbp)`）还是立即数（如 `$10`），并返回相应的汇编代码字符串。

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_134.png)

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_136.png)

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_137.png)

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_138.png)

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_140.png)

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_141.png)

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_143.png)

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_145.png)

## 总结 🏁

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_147.png)

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_149.png)

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_151.png)

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_153.png)

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_155.png)

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_157.png)

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_158.png)

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_160.png)

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_161.png)

本节课中我们一起学习了编译器后端中分支处理的实现。
1.  我们理解了分支的底层原理是修改指令指针（RIP）。
2.  我们探讨了如何将高级语言的结构化控制流（`if-else`, `while`）分解并转换为一系列低级跳转指令，并理解了“反转条件”以优化代码的常见策略。
3.  我们掌握了x86-64汇编中实现条件分支的两步模式：`CMP` 指令设置标志位，然后条件跳转指令（如 `JLE`）根据标志位决定跳转。
4.  最后，我们查看了为简单IR生成分支汇编代码的实用模板，这是完成CodeGen3项目的核心。

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_163.png)

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_165.png)

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_166.png)

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_167.png)

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_169.png)

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_171.png)

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_173.png)

![](img/da712e8a7e1fc71b29ce50ef670ea7ff_175.png)

通过将控制流逻辑从高级的、结构化的表示逐步降低到机器级别的跳转指令，我们向构建一个完整可用的编译器又迈进了一步。