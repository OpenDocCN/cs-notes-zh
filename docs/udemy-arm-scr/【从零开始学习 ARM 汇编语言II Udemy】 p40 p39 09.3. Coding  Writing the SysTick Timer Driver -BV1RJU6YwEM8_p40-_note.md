# ARM 汇编语言：09.3：编写 SysTick 定时器驱动

![](img/31a00097cea802ce8520180d2a299d3b_0.png)

![](img/31a00097cea802ce8520180d2a299d3b_2.png)

![](img/31a00097cea802ce8520180d2a299d3b_4.png)

在本节课中，我们将要学习如何为 ARM Cortex-M 微控制器编写 SysTick 定时器的驱动程序。我们将从初始化 GPIO 开始，然后配置 SysTick 定时器，为后续实现延时功能打下基础。

![](img/31a00097cea802ce8520180d2a299d3b_6.png)

## 初始化 GPIO

上一节我们介绍了驱动的基本结构，本节中我们来看看如何初始化 GPIO 端口。以下是初始化 GPIO 子程序的步骤。

![](img/31a00097cea802ce8520180d2a299d3b_8.png)

首先，我们需要启用 GPIOF 端口的时钟访问。

```assembly
GPIO_Init:
    LDR R1, =RCC_AHB2ENR
    LDR R0, [R1]
    ORR R0, R0, #GPIOF_EN
    STR R0, [R1]
    NOP
```

![](img/31a00097cea802ce8520180d2a299d3b_10.png)

![](img/31a00097cea802ce8520180d2a299d3b_12.png)

接下来，我们需要设置红色 LED 引脚的方向为输出。

```assembly
    LDR R1, =GPIOF_DIR
    LDR R0, [R1]
    ORR R0, R0, #LED_RED
    STR R0, [R1]
```

最后，我们启用该引脚的数字化功能。

```assembly
    LDR R1, =GPIOF_DEN
    LDR R0, [R1]
    ORR R0, R0, #LED_RED
    STR R0, [R1]
    BX LR
```

![](img/31a00097cea802ce8520180d2a299d3b_14.png)

![](img/31a00097cea802ce8520180d2a299d3b_16.png)

完成 GPIO 初始化后，我们就可以在 `__main` 函数中调用它。

![](img/31a00097cea802ce8520180d2a299d3b_18.png)

```assembly
__main:
    BL GPIO_Init
```

## 初始化 SysTick 定时器

在 GPIO 初始化之后，我们需要初始化 SysTick 定时器。以下是实现 `SysTick_Init` 子程序的步骤。

![](img/31a00097cea802ce8520180d2a299d3b_20.png)

首先，在修改任何配置之前，建议先禁用定时器。

![](img/31a00097cea802ce8520180d2a299d3b_22.png)

```assembly
SysTick_Init:
    LDR R1, =NVIC_ST_CTRL_R
    MOV R0, #0
    STR R0, [R1]
```

然后，我们将最大值加载到重载寄存器中。

![](img/31a00097cea802ce8520180d2a299d3b_24.png)

```assembly
    LDR R1, =NVIC_ST_RELOAD_R
    LDR R0, =0x00FFFFFF
    STR R0, [R1]
```

![](img/31a00097cea802ce8520180d2a299d3b_26.png)

接着，通过向当前值寄存器写入任意值（例如 0）来清除它。

![](img/31a00097cea802ce8520180d2a299d3b_28.png)

```assembly
    LDR R1, =NVIC_ST_CURRENT_R
    MOV R0, #0
    STR R0, [R1]
```

![](img/31a00097cea802ce8520180d2a299d3b_30.png)

最后，我们选择时钟源并启用 SysTick 定时器。

```assembly
    LDR R1, =NVIC_ST_CTRL_R
    MOV R0, #NVIC_ST_CTRL_ENABLE
    ORR R0, R0, #NVIC_ST_CTRL_CLK_SRC
    STR R0, [R1]
    BX LR
```

![](img/31a00097cea802ce8520180d2a299d3b_32.png)

初始化完成后，我们在主函数中调用它。

```assembly
    BL SysTick_Init
```

![](img/31a00097cea802ce8520180d2a299d3b_34.png)

## 总结

![](img/31a00097cea802ce8520180d2a299d3b_36.png)

![](img/31a00097cea802ce8520180d2a299d3b_37.png)

本节课中我们一起学习了如何为 ARM Cortex-M 编写基础的设备驱动。我们首先实现了 GPIO 的初始化，配置了 LED 引脚。然后，我们详细配置了 SysTick 定时器，包括禁用、设置重载值、清除当前值和最终启用定时器。在下一课中，我们将基于这个已初始化的定时器来实现延时子程序。