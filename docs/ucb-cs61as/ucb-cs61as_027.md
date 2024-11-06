# 变量和环境

## 定义变量

我们使用`define`来为变量赋值。

例如，`(define x 2)`将值`2`赋给`x`：

```
-> (define x 2)
-> x
2
-> (+ x 5)
7 
```

在调用`(define x 2)`之后，我们说`x`被*绑定*到`2`。变量绑定存储在*环境*中，我们将在第三单元更详细地讨论。

## 检查理解

假设以下内容被输入到 Racket 解释器中：

```
(define pi 3.14159)
(define radius 3)

(define area (* radius radius pi))
(define circumference (* 2 pi radius)) 
```

`area`会评估为什么？`circumference`会评估为什么？
