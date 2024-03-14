# 6\. 生成函数的奇点分析

> 原文：[`ac.cs.princeton.edu/60singularity`](https://ac.cs.princeton.edu/60singularity)
> 
> 译者：[飞龙](https://github.com/wizardforcel)
> 
> 协议：[CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/)


## VI.1 基本奇点分析理论一瞥

## VI.2 标准尺度下的系数渐近

## VI.3 转移

## VI.4 奇点分析过程

## VI.5 多个奇点

## VI.6 插曲：适合奇点分析的函数

## VI.7 反函数

## VI.8 多对数

## VI.9 函数复合

## VI.10 闭包性质

## VI.11 陶伯理论和达布方法

## VI.12 观点

#### 网络练习

## VI.1

使用标准函数尺度直接推导出以下 CFG 中字符串数量的渐近表达式：S = E + U×Z×S + D×Z×S, U = Z + U×U×Z, D = Z + D×D×Z。

## VI.2

给出一个关于每个节点具有 0、2 或 3 个子节点的根有序树数量的渐近表达式。表示这样一棵树需要多少位？

## VI.3

（D. 卡特）*彩虹树*是一种根有序树，其中每个节点都是四种颜色之一，规则是每个节点与其父节点的颜色不同，并且只能有彼此颜色不同的子节点。（请注意，没有节点可以有超过 3 个子节点。）给出一个关于具有$N$个节点的彩虹树数量的~表达式。

#### 选定实验

## 程序 VI.1

以第 6 讲中的绘图风格，在以原点为中心的大小为 10 的单位正方形中绘制$1/\Gamma(z)$的$r$和$\theta$图。[点击这里](http://ac.cs.princeton.edu/Java/complexplot)访问用于讲座的 Java 代码。
