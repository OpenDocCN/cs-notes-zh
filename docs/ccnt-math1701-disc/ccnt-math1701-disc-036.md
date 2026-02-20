# 离散数学：L36：用反例反驳蕴含命题 🧮

![](img/69fb15b2c5d82dbdf10986cccaee13f7_0.png)

![](img/69fb15b2c5d82dbdf10986cccaee13f7_2.png)

![](img/69fb15b2c5d82dbdf10986cccaee13f7_3.png)

![](img/69fb15b2c5d82dbdf10986cccaee13f7_5.png)

![](img/69fb15b2c5d82dbdf10986cccaee13f7_6.png)

![](img/69fb15b2c5d82dbdf10986cccaee13f7_7.png)

在本节课中，我们将学习如何通过构造反例来证明一个蕴含命题是假的。我们将从一个具体的数学命题入手，分析其结构，并展示如何找到一个反例来推翻它。

![](img/69fb15b2c5d82dbdf10986cccaee13f7_9.png)

![](img/69fb15b2c5d82dbdf10986cccaee13f7_10.png)

![](img/69fb15b2c5d82dbdf10986cccaee13f7_12.png)

![](img/69fb15b2c5d82dbdf10986cccaee13f7_13.png)

## 概述

![](img/69fb15b2c5d82dbdf10986cccaee13f7_15.png)

![](img/69fb15b2c5d82dbdf10986cccaee13f7_17.png)

![](img/69fb15b2c5d82dbdf10986cccaee13f7_18.png)

![](img/69fb15b2c5d82dbdf10986cccaee13f7_19.png)

我们首先面对一个命题：对于任意整数 A 和 B，如果 A² > B²，那么 A > B。我们的目标是判断这个命题的真假。如果它是假的，我们将通过找到一个具体的反例来证明。

![](img/69fb15b2c5d82dbdf10986cccaee13f7_21.png)

![](img/69fb15b2c5d82dbdf10986cccaee13f7_22.png)

![](img/69fb15b2c5d82dbdf10986cccaee13f7_23.png)

## 分析命题与初步尝试

![](img/69fb15b2c5d82dbdf10986cccaee13f7_24.png)

![](img/69fb15b2c5d82dbdf10986cccaee13f7_25.png)

![](img/69fb15b2c5d82dbdf10986cccaee13f7_27.png)

![](img/69fb15b2c5d82dbdf10986cccaee13f7_28.png)

上一节我们介绍了本节课的目标。本节中，我们来看看如何分析这个具体的命题。

![](img/69fb15b2c5d82dbdf10986cccaee13f7_30.png)

![](img/69fb15b2c5d82dbdf10986cccaee13f7_31.png)

![](img/69fb15b2c5d82dbdf10986cccaee13f7_32.png)

![](img/69fb15b2c5d82dbdf10986cccaee13f7_33.png)

命题的形式是：如果 P（即 A² > B²）成立，那么 Q（即 A > B）也成立。为了判断其真假，我们可以先尝试从假设 P 出发，推导出 Q。

![](img/69fb15b2c5d82dbdf10986cccaee13f7_35.png)

![](img/69fb15b2c5d82dbdf10986cccaee13f7_36.png)

一种自然的思路是对不等式 A² > B² 两边同时开平方根，试图得到 A > B。然而，开平方根会引入正负号的问题。这意味着从 `√(A²) > √(B²)` 并不能直接得到 `A > B`，因为 `√(A²) = |A|`，而 `|A| > |B|` 并不能保证 `A > B`。这个正负号的复杂性提示我们，原命题可能是假的。

![](img/69fb15b2c5d82dbdf10986cccaee13f7_37.png)

![](img/69fb15b2c5d82dbdf10986cccaee13f7_38.png)

![](img/69fb15b2c5d82dbdf10986cccaee13f7_39.png)

![](img/69fb15b2c5d82dbdf10986cccaee13f7_41.png)

![](img/69fb15b2c5d82dbdf10986cccaee13f7_42.png)

![](img/69fb15b2c5d82dbdf10986cccaee13f7_43.png)

## 寻找反例

![](img/69fb15b2c5d82dbdf10986cccaee13f7_45.png)

![](img/69fb15b2c5d82dbdf10986cccaee13f7_47.png)

![](img/69fb15b2c5d82dbdf10986cccaee13f7_48.png)

![](img/69fb15b2c5d82dbdf10986cccaee13f7_50.png)

上一节我们分析了从假设推导结论的困难之处，这源于正负号。本节中，我们来看看如何通过构造具体的数字例子来寻找反例。

![](img/69fb15b2c5d82dbdf10986cccaee13f7_51.png)

![](img/69fb15b2c5d82dbdf10986cccaee13f7_53.png)

![](img/69fb15b2c5d82dbdf10986cccaee13f7_54.png)

既然正负号可能是关键，我们就应该尝试使用负数。以下是具体的尝试步骤：

![](img/69fb15b2c5d82dbdf10986cccaee13f7_56.png)

![](img/69fb15b2c5d82dbdf10986cccaee13f7_57.png)

![](img/69fb15b2c5d82dbdf10986cccaee13f7_58.png)

![](img/69fb15b2c5d82dbdf10986cccaee13f7_59.png)

![](img/69fb15b2c5d82dbdf10986cccaee13f7_60.png)

首先，我们尝试一个没有负数的例子，例如 A=4， B=3。此时，4²=16 > 9=3² 成立，并且 4 > 3 也成立。这个例子支持原命题，但它没有涉及负数。

![](img/69fb15b2c5d82dbdf10986cccaee13f7_62.png)

![](img/69fb15b2c5d82dbdf10986cccaee13f7_64.png)

接下来，我们尝试一个包含负数的例子。令 A = -4， B = 3。
*   计算 P： (-4)² = 16， 3² = 9。因为 16 > 9，所以条件 `A² > B²` 成立。
*   检查 Q： -4 > 3 吗？不，-4 小于 3。所以结论 `A > B` 不成立。

![](img/69fb15b2c5d82dbdf10986cccaee13f7_66.png)

![](img/69fb15b2c5d82dbdf10986cccaee13f7_67.png)

![](img/69fb15b2c5d82dbdf10986cccaee13f7_68.png)

![](img/69fb15b2c5d82dbdf10986cccaee13f7_69.png)

![](img/69fb15b2c5d82dbdf10986cccaee13f7_70.png)

![](img/69fb15b2c5d82dbdf10986cccaee13f7_71.png)

![](img/69fb15b2c5d82dbdf10986cccaee13f7_72.png)

于是，我们找到了一个具体的整数对 (A, B) = (-4, 3)，它使得前提 P 为真，但结论 Q 为假。这就构成了原命题的一个反例。由于原命题声称“对于所有整数 A, B”该蕴含关系都成立，只要找到一个反例，就足以证明整个命题为假。

![](img/69fb15b2c5d82dbdf10986cccaee13f7_74.png)

![](img/69fb15b2c5d82dbdf10986cccaee13f7_75.png)

![](img/69fb15b2c5d82dbdf10986cccaee13f7_76.png)

![](img/69fb15b2c5d82dbdf10986cccaee13f7_77.png)

## 反例法的原理

![](img/69fb15b2c5d82dbdf10986cccaee13f7_79.png)

![](img/69fb15b2c5d82dbdf10986cccaee13f7_80.png)

![](img/69fb15b2c5d82dbdf10986cccaee13f7_81.png)

![](img/69fb15b2c5d82dbdf10986cccaee13f7_82.png)

上一节我们通过一个具体例子演示了如何找到反例。本节中，我们来看看这种方法背后通用的逻辑原理。

![](img/69fb15b2c5d82dbdf10986cccaee13f7_84.png)

![](img/69fb15b2c5d82dbdf10986cccaee13f7_85.png)

我们的目标是证明一个形如 **∀x (P(x) ⇒ Q(x))** 的命题是假的。这里，∀x 表示“对于所有x”，P(x)和Q(x)是关于x的谓词（即条件）。

![](img/69fb15b2c5d82dbdf10986cccaee13f7_86.png)

![](img/69fb15b2c5d82dbdf10986cccaee13f7_87.png)

![](img/69fb15b2c5d82dbdf10986cccaee13f7_88.png)

![](img/69fb15b2c5d82dbdf10986cccaee13f7_90.png)

![](img/69fb15b2c5d82dbdf10986cccaee13f7_91.png)

根据逻辑规则，要证明一个全称量词命题为假，等价于证明其否定为真。该命题的否定是：
**∃x ¬(P(x) ⇒ Q(x))**
即“存在一个x，使得 P(x) ⇒ Q(x) 不成立”。

![](img/69fb15b2c5d82dbdf10986cccaee13f7_93.png)

![](img/69fb15b2c5d82dbdf10986cccaee13f7_94.png)

![](img/69fb15b2c5d82dbdf10986cccaee13f7_95.png)

![](img/69fb15b2c5d82dbdf10986cccaee13f7_97.png)

那么，一个蕴含式 `P(x) ⇒ Q(x)` 什么时候不成立呢？回顾蕴含式的真值表，只有当 **P(x) 为真且 Q(x) 为假** 时，整个蕴含式才为假。

![](img/69fb15b2c5d82dbdf10986cccaee13f7_99.png)

![](img/69fb15b2c5d82dbdf10986cccaee13f7_101.png)

![](img/69fb15b2c5d82dbdf10986cccaee13f7_102.png)

![](img/69fb15b2c5d82dbdf10986cccaee13f7_103.png)

因此，反例法的核心可以总结如下：
要反驳 **∀x (P(x) ⇒ Q(x))**，我们需要在定义域中找到一个具体的元素（称为反例），使得：
1.  **P(反例) 为真**。
2.  **Q(反例) 为假**。

用公式表示，即找到元素 `a`，满足：
**P(a) ∧ ¬Q(a)**

![](img/69fb15b2c5d82dbdf10986cccaee13f7_105.png)

![](img/69fb15b2c5d82dbdf10986cccaee13f7_106.png)

![](img/69fb15b2c5d82dbdf10986cccaee13f7_107.png)

![](img/69fb15b2c5d82dbdf10986cccaee13f7_108.png)

![](img/69fb15b2c5d82dbdf10986cccaee13f7_109.png)

![](img/69fb15b2c5d82dbdf10986cccaee13f7_110.png)

![](img/69fb15b2c5d82dbdf10986cccaee13f7_111.png)

在我们的例子中：
*   定义域是：所有整数对 (A, B)。
*   P(A, B)：A² > B²
*   Q(A, B)：A > B
*   我们找到的反例 a 是 (A, B) = (-4, 3)。
*   验证：P(-4, 3) 为真（因为16>9），而 Q(-4, 3) 为假（因为-4不大于3）。这完美符合 **P(a) ∧ ¬Q(a)** 的结构。

![](img/69fb15b2c5d82dbdf10986cccaee13f7_113.png)

![](img/69fb15b2c5d82dbdf10986cccaee13f7_114.png)

## 总结

![](img/69fb15b2c5d82dbdf10986cccaee13f7_115.png)

![](img/69fb15b2c5d82dbdf10986cccaee13f7_116.png)

![](img/69fb15b2c5d82dbdf10986cccaee13f7_118.png)

![](img/69fb15b2c5d82dbdf10986cccaee13f7_119.png)

本节课中我们一起学习了如何用反例法反驳一个蕴含命题。关键步骤如下：
1.  识别出命题是全称量词形式的蕴含式：**∀x (P(x) ⇒ Q(x))**。
2.  理解要证明它为假，只需找到一个使 **P(x) 真而 Q(x) 假** 的实例。
3.  在定义域内寻找或构造这样的具体例子。
4.  展示该例子如何满足前提并否定结论，从而完成反驳。

![](img/69fb15b2c5d82dbdf10986cccaee13f7_121.png)

![](img/69fb15b2c5d82dbdf10986cccaee13f7_122.png)

![](img/69fb15b2c5d82dbdf10986cccaee13f7_123.png)

![](img/69fb15b2c5d82dbdf10986cccaee13f7_124.png)

这种方法在数学和逻辑论证中非常强大且常用，因为它简洁有力地证明了某个普遍声称不成立。