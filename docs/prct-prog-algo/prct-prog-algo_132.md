# 3\.   组合参数和多变量生成函数

> 原文：[`ac.cs.princeton.edu/30mgf`](https://ac.cs.princeton.edu/30mgf)
> 
> 译者：[飞龙](https://github.com/wizardforcel)
> 
> 协议：[CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/)


## III.1 双变量生���函数（BGFs）简介

## III.2 双变量生成函数和概率分布

## III.3 继承参数和普通 MGFs

## III.4 继承参数和指数 MGFs

## III.5 递归参数

## III.6 完全生成函数和离散模型

## III.7 附加构造

## III.8 极值参数

## III.9 视角

#### 选定练习

## 注 III.17

*Cayley 树中的叶子和节点度分布*。对于 Cayley 树，证明具有标记叶子数$u$的双变量 EGF 是方程的解$$T(z,u)=uz+z(e^{T(z,u)}-1).$$然后证明随机 Cayley 树中叶子的平均数量渐近于$ne^{-1}$，更一般地，随机大小为$n$的 Cayley 树中出度为$k$的节点的平均数量渐近于$$n\cdot e^{-1}\, {1\over k!}.$$度数因此近似描述为速率为 1 的泊松分布。

## 注 III.21

*Bhaskara Acharya 之后（约 1150 年）*。考虑所有使用数字 1 一次，数字 2 两次，...，数字 9 九次形成的十进制数字。这些数字都有 45 位。计算它们的和$S$，并惊讶地发现$S$等于`45875559600006153219084769286399999999999999954124440399993846780915230713600000.` 这个数字有一长串的 9（还有更多隐藏的 9！）。有一个简单的解释吗？这个练习受到印度数学家 Bhaskara Acharya 在 1150 年左右发现的多项式系数的启发。

#### 选定实验

## Program III.1

编写一个程序，生成大小为$N$的 1000 个随机排列，其中$N$ = $10³$，$10⁴$，...（尽可能多），并绘制循环数的分布，验证平均值集中在$H_N$处。

#### 网页练习

## III.1

(Exercise 5.13 in *Analysis of Algorithms*) 一个长度为$N$的随机比特串中没有 00 的平均 1 比特数是多少？

## III.2

（E. Neyman）使用符号方法和 OBGF 计算具有$N$位数字的随机三进制（基数 3）数字中数字之和的平均值。对于$N=1$，结果是(0 + 1 + 2)/3 = 1。对于$N=2$，有九种可能性 00, 01, 02, 10, 11, 12, 20, 21, 22，结果是(0 + 1 + 2 + 1 + 2 + 3 + 2 + 3 + 4)/9 = 2。*注意*：这不是解决这个问题的最简单方法——这个问题的目的是测试你对这种技术的理解。

## III.3

（D. Mavrides）推导一个整数组合集合中 1 的 OBGF，并用它计算随机选择的$N$的组合中预期的 1 的数量。

## III.4

（M. Bahrani）比特串中的一个*run*是一串连续相同比特的最大序列。例如，字符串 11010100001 有 7 个 runs，长度分别为 2、1、1、1、1、4、1。长度为$N$的随机二进制串中平均 runs 的数量是多少？列出相应的水平和垂直 OBGFs。二进制串中 runs 的数量分布是否集中？

## III.5

（T. Ratigan）推导一个组合结构，导致涉及具有$n$节点的 Catalan 树中度为$d$的节点数量的 OBGF 的方程。解出$d=1$的方程，并给出随机$n$节点 Catalan 树中度为 1 的节点数量的渐近估计。

## III.6

（M. Tyler）将*单位$n$-超立方体*定义为点集$[0,1]^n \subset \mathbb{R}^n$。例如，单位 0-超立方体是一个点，而单位 3-超立方体是单位立方体。将单位$n$-超立方体的*$k$-面*定义为$n$-超立方体外部的$k$-超立方体的副本。更正式地说，单位$n$-超立方体的$k$-面是形式为$\prod_{1\le i\le n}S_i$的集合，其中对于每个$i$在$1$和$n$之间，$S_i$要么是$\{0\}$，要么是$\{1\}$，要么是$[0,1]$，并且恰好有$k$个指数$i$使得$S_i = [0,1]$。推导出一种组合构造，导致一个 OBGF 和单位$n$-超立方体中$k$-面的数量的显式公式。使用 OBGF 推导出单位$n$-超立方体的随机面的维度的期望值。

## III.7

（F. Dong）考虑从{1，...，N}到{1，...，k}的随机映射。对于$k>2$，证明偶数大小的原像数量在期望上大于奇数大小的原像数量。

## III.8

（A. Alag）给出一个~近似值，用于$N$的随机组合中偶数项的平均数量。
