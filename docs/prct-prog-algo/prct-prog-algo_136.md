# 7\.   奇点分析的应用

> 原文：[`ac.cs.princeton.edu/70applications`](https://ac.cs.princeton.edu/70applications)
> 
> 译者：[飞龙](https://github.com/wizardforcel)
> 
> 协议：[CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/)


## VII.1 奇点分析渐近的路线图

## VII.2 集合和指数-对数模式

## VII.3 简单树的种类和反函数

## VII.4 树状结构和隐式函数

## VII.5 无标记非平面树和 P´olya 算子

## VII.6 不可约上下文无关结构

## VII.7 代数函数的一般分析

## VII.8 代数函数的组合应用

## VII.9 普通微分方程和系统

## VII.10 奇点分析和概率分布

## VII.11 视角

#### Web 练习

## VII.1

使用树状模式为具有 $N$ 个叶子的括号的数量开发一个渐近表达式（参见第 69 页的示例 I.15 和第 474 页的注 VII.19）

## VII.2

为大小为 $N$ 的根有序树的数量开发一个渐近表达式，其中没有节点具有单个子节点。

## VII.3

对于以下每个组合结构，给出用于开发渐近枚举结果的适当模式（简单树的种类，指数-对数，或隐式树状类）。当两者都适用时，选择更简单的一个。$A = Z\times SEQ(A)$, $A = Z + SEQ_{>1}(A)$, $A = SET(CYC(Z))$, $B = Z\times (1+B)⁴$, $A = Z\star SET(A)$, $A = Z + SET_{>1}(A)$, $A = SET(CYC_{>1}(Z))$.

## VII.4

（A. Ding）证明在 $N$ 个顶点上的 2-正则简单图中，所有循环长度大于 $r$ 的比例大约为 $e^{3/4}/\sqrt{r}$，对于大的 $r$。

#### 选定实验

## 程序 VII.1

对于括号的生成函数进行 r 和 θ 图（参见 Web 练习 VII.1）。
