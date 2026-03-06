# 037：编写 GPIO 输入驱动 🚦

![](img/9a1f969d49c88dfec2f82fe36d0b7da2_0.png)

![](img/9a1f969d49c88dfec2f82fe36d0b7da2_2.png)

![](img/9a1f969d49c88dfec2f82fe36d0b7da2_4.png)

![](img/9a1f969d49c88dfec2f82fe36d0b7da2_6.png)

在本节课中，我们将学习如何为 ARM 微控制器编写 GPIO 输入驱动程序。我们将扩展已有的 GPIO 初始化函数，使其能够处理输入引脚（如按钮），并编写一个读取按钮状态的子程序，根据不同的按钮按下情况来控制 LED 灯。

![](img/9a1f969d49c88dfec2f82fe36d0b7da2_8.png)

## 概述

上一节我们完成了 GPIO 输出的初始化。本节中，我们将在此基础上，解锁并配置 GPIO 输入引脚，并实现一个读取按钮状态并根据状态控制 LED 的逻辑。

## 扩展 GPIO 初始化函数

![](img/9a1f969d49c88dfec2f82fe36d0b7da2_10.png)

我们的 GPIO 初始化子程序目前只初始化了时钟和 PF1（红色 LED）作为输出。现在，我们需要解锁 PF0 端口，并将绿色 LED 和两个开关（按钮）配置好。

![](img/9a1f969d49c88dfec2f82fe36d0b7da2_12.png)

### 解锁 PF0 端口

某些 GPIO 端口（如 PF0）在默认情况下是锁定的，需要先解锁才能配置。以下是解锁 PF0 的步骤：

1.  将解锁密钥（`LOCK_KEY`）加载到寄存器。
2.  将该密钥写入 GPIO 端口 F 的锁定寄存器（`GPIOF_LOCK_R`）。

对应的汇编代码如下：
```assembly
LDR R1, =GPIOF_LOCK_R   @ 加载锁定寄存器地址到 R1
LDR R0, =LOCK_KEY       @ 加载解锁密钥到 R0
STR R0, [R1]            @ 将密钥写入锁定寄存器，解锁 PF0
```

![](img/9a1f969d49c88dfec2f82fe36d0b7da2_14.png)

![](img/9a1f969d49c88dfec2f82fe36d0b7da2_15.png)

### 提交更改

解锁后，需要向提交寄存器写入特定值以确认更改。我们将 `0xFF` 写入 GPIO 端口 F 的提交寄存器（`GPIOF_CR_R`）。
```assembly
LDR R1, =GPIOF_CR_R     @ 加载提交寄存器地址到 R1
MOV R0, #0xFF           @ 将立即数 0xFF 移动到 R0
STR R0, [R1]            @ 将 0xFF 写入提交寄存器
```

### 配置引脚方向

![](img/9a1f969d49c88dfec2f82fe36d0b7da2_17.png)

方向寄存器（`GPIOF_DIR_R`）用于设置引脚是输入（0）还是输出（1）。红色 LED（PF1）已设置为输出。现在，我们需要将绿色 LED 对应的引脚也设置为输出。开关引脚默认即为输入（0），因此无需额外设置。

![](img/9a1f969d49c88dfec2f82fe36d0b7da2_19.png)

我们使用**按位或（OR）**操作来设置绿色 LED 的位，而不影响其他已配置的位：
```assembly
LDR R1, =GPIOF_DIR_R    @ 加载方向寄存器地址到 R1
LDR R0, [R1]            @ 读取当前方向寄存器的值到 R0
ORR R0, R0, #LED_GREEN  @ 将绿色 LED 对应的位设置为 1（输出）
STR R0, [R1]            @ 将新值写回方向寄存器
```

### 数字功能使能

![](img/9a1f969d49c88dfec2f82fe36d0b7da2_21.png)

数字使能寄存器（`GPIOF_DEN_R`）用于启用引脚的数字功能。我们需要使能红色 LED、绿色 LED 以及两个开关引脚。

![](img/9a1f969d49c88dfec2f82fe36d0b7da2_23.png)

我们可以通过**按位或（OR）**操作一次性设置所有需要的位：
```assembly
LDR R1, =GPIOF_DEN_R            @ 加载数字使能寄存器地址到 R1
MOV R0, #(LED_RED | LED_GREEN | SWITCH1 | SWITCH2) @ 将所有需要使能的位合并到 R0
STR R0, [R1]                    @ 将值写入数字使能寄存器
```

### 配置上拉电阻

对于输入引脚（开关），我们通常需要启用内部上拉电阻，以确保引脚在未按下时保持稳定的高电平。这通过上拉寄存器（`GPIOF_PUR_R`）实现。

![](img/9a1f969d49c88dfec2f82fe36d0b7da2_25.png)

以下是启用两个开关上拉电阻的代码：
```assembly
LDR R1, =GPIOF_PUR_R    @ 加载上拉寄存器地址到 R1
LDR R0, [R1]            @ 读取当前上拉寄存器的值到 R0
ORR R0, R0, #SWITCH1    @ 启用开关1的上拉电阻
ORR R0, R0, #SWITCH2    @ 启用开关2的上拉电阻
STR R0, [R1]            @ 将新值写回上拉寄存器
```

![](img/9a1f969d49c88dfec2f82fe36d0b7da2_27.png)

至此，GPIO 初始化函数 `gpio_init` 就完成了对所有必要引脚（两个输出 LED 和两个输入开关）的配置。

![](img/9a1f969d49c88dfec2f82fe36d0b7da2_29.png)

## 编写 GPIO 读取子程序

![](img/9a1f969d49c88dfec2f82fe36d0b7da2_31.png)

![](img/9a1f969d49c88dfec2f82fe36d0b7da2_33.png)

现在我们需要一个子程序来读取开关的状态。我们将创建一个名为 `gpio_read` 的子程序。

### 读取数据寄存器

开关的状态存储在 GPIO 端口 F 的数据寄存器（`GPIOF_DATA_R`）中。我们读取这个寄存器的值。
```assembly
LDR R1, =GPIOF_DATA_R   @ 加载数据寄存器地址到 R1
LDR R0, [R1]            @ 将数据寄存器的值读入 R0
```

### 检查开关状态

读取到的值包含了所有引脚的状态。我们使用**按位与（AND）**操作来屏蔽出我们关心的开关位（SWITCH1 和 SWITCH2）。
```assembly
AND R0, R0, #(SWITCH1 | SWITCH2) @ 屏蔽出两个开关的状态位
```
执行此操作后，`R0` 寄存器中只有对应开关的位是有效的。如果开关被按下（引脚接地），对应的位将是 0；如果未按下（由上拉电阻拉高），对应的位将是 1。

最后，使用 `BX LR` 指令返回，此时 `R0` 中包含了开关的状态信息。

## 在主程序中处理输入

![](img/9a1f969d49c88dfec2f82fe36d0b7da2_35.png)

在主程序循环中，我们首先调用 `gpio_init` 进行初始化，然后进入一个循环，不断读取开关状态并作出响应。

### 读取并比较状态

![](img/9a1f969d49c88dfec2f82fe36d0b7da2_37.png)

![](img/9a1f969d49c88dfec2f82fe36d0b7da2_39.png)

在循环中，我们调用 `gpio_read` 子程序，然后将返回值与预定义的“按下”状态进行比较。
```assembly
loop:
    BL gpio_read        @ 调用读取子程序，结果在 R0 中
    CMP R0, #SWITCH1_PRESSED @ 比较 R0 是否等于开关1被按下的状态
    BEQ switch1_pressed @ 如果相等，跳转到开关1处理程序
    CMP R0, #SWITCH2_PRESSED @ 比较 R0 是否等于开关2被按下的状态
    BEQ switch2_pressed @ 如果相等，跳转到开关2处理程序
    B loop              @ 否则，继续循环
```

![](img/9a1f969d49c88dfec2f82fe36d0b7da2_41.png)

### 处理开关1按下

![](img/9a1f969d49c88dfec2f82fe36d0b7da2_43.png)

当检测到开关1被按下时，我们跳转到 `switch1_pressed` 标签处。在这里，我们将红色 LED 的值加载到 `R0`，然后调用一个通用的 `led_on` 子程序来点亮它。
```assembly
switch1_pressed:
    MOV R0, #LED_RED    @ 将红色LED的位模式放入R0
    BL led_on           @ 调用点亮LED的子程序
    B loop              @ 返回主循环
```

### 处理开关2按下

![](img/9a1f969d49c88dfec2f82fe36d0b7da2_45.png)

![](img/9a1f969d49c88dfec2f82fe36d0b7da2_46.png)

类似地，处理开关2按下，点亮绿色 LED。
```assembly
switch2_pressed:
    MOV R0, #LED_GREEN  @ 将绿色LED的位模式放入R0
    BL led_on           @ 调用点亮LED的子程序
    B loop              @ 返回主循环
```

![](img/9a1f969d49c88dfec2f82fe36d0b7da2_48.png)

### 实现 LED 点亮子程序

`led_on` 子程序负责将传入的 `R0` 值（包含要点亮的 LED 位模式）写入数据寄存器，从而控制相应的 GPIO 引脚输出高电平，点亮 LED。
```assembly
led_on:
    LDR R1, =GPIOF_DATA_R @ 加载数据寄存器地址
    STR R0, [R1]        @ 将 R0 中的值（LED位模式）写入寄存器
    BX LR               @ 返回调用处
```

## 练习与总结

本节课中，我们一起学习了如何编写一个完整的 GPIO 输入驱动。我们扩展了初始化函数以支持输入引脚，编写了读取按钮状态的子程序，并在主程序中实现了根据不同按钮控制不同 LED 的逻辑。

目前程序只处理了单个按钮按下的情况。作为练习，请你尝试实现以下功能：
1.  **无按钮按下**：当两个按钮都未按下时，调用一个 `led_off` 子程序来关闭所有 LED。
2.  **两个按钮同时按下**：当两个按钮同时被按下时，你可以选择点亮蓝色 LED（如果板子支持），或者同时点亮红色和绿色 LED。

![](img/9a1f969d49c88dfec2f82fe36d0b7da2_50.png)

通过完成这个练习，你将更深入地理解 GPIO 输入输出的协同工作以及条件判断在嵌入式编程中的应用。如果在实现过程中遇到任何问题，可以随时回顾本教程或寻求进一步的帮助。