# 032：广度优先与深度优先策略 🌳

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_0.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_2.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_4.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_6.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_7.png)

在本节课中，我们将要学习二叉树的遍历。当我们处理树结构时，经常需要访问树中的所有节点。

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_9.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_10.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_11.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_12.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_13.png)

树不像数组或链表那样是线性数据结构。在线性数据结构中，存在逻辑上的起点和终点，因此我们可以从一端开始，将指针不断移向另一端。

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_15.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_16.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_17.png)

对于像链表这样的线性数据结构，每个节点或元素只有一个后继元素。但树是非线性数据结构。这里我画了一棵二叉树，节点中填充了字符数据。在树中，当我们指向某个特定节点时，可能会有多个可能的方向和多个可能的后继节点。

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_19.png)

例如，在这棵二叉树中，如果我们从根节点 F 开始，有两个可能的方向：向左到 D，或者向右到 J。如果我们选择了一个方向，那么之后我们必须以某种方式返回，再去往另一个方向。

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_21.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_22.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_23.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_24.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_25.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_26.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_27.png)

因此，树的遍历并非直截了当。本节课我们将讨论树遍历的算法。树遍历可以正式定义为：以某种顺序访问树中每个节点恰好一次的过程。对我们而言，“访问”一个节点意味着读取或处理该节点中的数据，在本节课中，特指打印节点中的数据。

根据访问节点的顺序，树遍历算法大致可以分为两类：广度优先遍历和深度优先遍历。

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_29.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_30.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_31.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_32.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_33.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_34.png)

## 广度优先遍历与深度优先遍历 🧭

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_36.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_37.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_38.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_39.png)

广度优先遍历和深度优先遍历是遍历或搜索图（Graph）的通用技术。图是一种数据结构，我们目前尚未在本系列中讨论图，将在后续课程中介绍。现在只需知道，树是图的一种特殊形式。本节课我们将在树的背景下讨论这两种遍历策略。

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_41.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_43.png)

在广度优先方法中，我们会先访问同一深度或层级的所有节点，然后再访问下一层级的节点。

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_45.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_46.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_47.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_49.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_51.png)

在我展示的这棵二叉树中，值为 F 的根节点位于第 0 层（L0）。节点的深度定义为从根节点到该节点的路径上的边数，根节点的深度为 0。节点 D 和 J 位于深度 1，即第 1 层。这四个节点位于第 2 层。这三个节点位于第 3 层。最后，值为 H 的节点位于第 4 层。

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_53.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_54.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_55.png)

在广度优先方法中，我们可以从第 0 层开始。第 0 层只有根节点，因此我们访问根节点 F。第 0 层完成后，我们进入第 1 层，从左到右访问节点：先访问 D，然后访问 J。第 1 层完成后，我们进入第 2 层，顺序是 B、E、G、K。接着进入第 3 层：A、C、I。最后进入第 4 层：H。

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_56.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_58.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_59.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_60.png)

这种针对树的广度优先遍历称为**层序遍历**。我们稍后会讨论如何用程序实现它。在这种顺序中，我们逐层、从左到右地访问节点。在广度优先方法中，对于任何节点，我们会在访问其任何孙节点之前，先访问其所有子节点。

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_62.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_63.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_64.png)

在这棵树中，我们先访问 F，然后访问 D。访问 D 后，我们不会立即沿着深度方向去访问 D 的子节点（如 B 或 E），而是接着去访问 J。

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_65.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_67.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_68.png)

## 深度优先遍历的核心思想 🔍

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_70.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_71.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_72.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_74.png)

在深度优先方法中，如果我们访问一个子节点，我们会先完成该子节点的整个子树，然后再去访问下一个子节点。

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_75.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_76.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_78.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_79.png)

在这棵树中，从根节点 F 开始，如果我们向左走到 D，那么我们应该先访问完 D 的整个左子树（即沿着这条路径的所有孙节点），然后再去访问 F 的右子节点 J。同样地，当我们访问 J 时，也会先访问完 J 的整个右子树。

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_81.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_83.png)

在深度优先方法中，访问左子树、右子树和根节点的相对顺序可以不同。例如，我们可以先访问右子树，然后根节点，再左子树；或者先访问根节点，然后左子树，再右子树。相对顺序可以变化，但深度优先策略的核心思想是：访问一个子节点意味着访问该路径上的整个子树。

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_85.png)

记住，“访问”一个节点就是读取、处理或打印该节点中的数据。

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_87.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_88.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_89.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_90.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_91.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_92.png)

## 三种深度优先遍历策略 📝

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_93.png)

根据左子树、右子树和根节点的相对顺序，有三种流行的深度优先策略。

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_95.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_96.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_97.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_98.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_99.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_100.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_101.png)

1.  **先序遍历**：首先访问根节点，然后递归地以相同方式访问左子树，最后访问右子树。
    *   **公式/代码表示**：`DLR` (Data, Left, Right)
2.  **中序遍历**：首先递归地访问左子树，然后访问根节点，最后访问右子树。
    *   **公式/代码表示**：`LDR` (Left, Data, Right)
3.  **后序遍历**：首先递归地访问左子树，然后访问右子树，最后访问根节点。
    *   **公式/代码表示**：`LRD` (Left, Right, Data)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_103.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_104.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_105.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_106.png)

总共有六种可能的左、右、根排列方式，但按照惯例，左子树总是在右子树之前被访问。因此，我们只使用这三种策略，变化的只是根节点的位置：如果在左、右之前，就是先序；如果在中间，就是中序；如果在左、右之后，就是后序。

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_108.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_109.png)

有一个简单的方法来记住这三种深度优先算法：用字母 D 表示访问节点（读取数据），L 表示进入左子树，R 表示进入右子树。
*   先序遍历对每个节点执行 `DLR`：先读取数据，然后向左，左子树完成后向右。
*   中序遍历对每个节点执行 `LDR`：先完成左子树，然后读取当前节点数据，然后向右。
*   后序遍历对每个节点执行 `LRD`：先向左，左子树完成后向右，然后读取当前节点数据。

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_110.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_111.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_112.png)

先序、中序和后序遍历使用递归实现起来非常简单直观，我们将在后续讨论实现。现在让我们看看对于示例树，这三种遍历的顺序分别是什么。

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_114.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_115.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_116.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_117.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_118.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_119.png)

## 手动推导遍历顺序 ✍️

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_121.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_122.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_123.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_124.png)

上一节我们介绍了三种深度优先遍历的策略，本节我们来看看如何为示例树手动推导出具体的遍历顺序。

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_126.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_127.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_129.png)

**先序遍历顺序推导**：
我们从根节点 F 开始，遵循 `DLR` 规则。
1.  访问 F (D)。
2.  进入 F 的左子树 (L)，即以 D 为根的子树。
    *   访问 D (D)。
    *   进入 D 的左子树 (L)，即以 B 为根的子树。
        *   访问 B (D)。
        *   进入 B 的左子树 (L)，即节点 A。
            *   访问 A (D)。（A 无左右子树，返回）
        *   进入 B 的右子树 (R)，即节点 C。
            *   访问 C (D)。（C 无左右子树，返回）
    *   进入 D 的右子树 (R)，即节点 E。
        *   访问 E (D)。（E 无左右子树，返回）
3.  进入 F 的右子树 (R)，即以 J 为根的子树。
    *   访问 J (D)。
    *   进入 J 的左子树 (L)，即以 G 为根的子树。
        *   访问 G (D)。
        *   （G 无左子树）
        *   进入 G 的右子树 (R)，即节点 I。
            *   访问 I (D)。
            *   进入 I 的左子树 (L)，即节点 H。
                *   访问 H (D)。（H 无左右子树，返回）
            *   （I 无右子树）
    *   进入 J 的右子树 (R)，即节点 K。
        *   访问 K (D)。（K 无左右子树，返回）

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_131.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_132.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_133.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_135.png)

因此，先序遍历顺序为：**F, D, B, A, C, E, J, G, I, H, K**

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_137.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_139.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_140.png)

**中序遍历顺序推导**：
我们从根节点 F 开始，遵循 `LDR` 规则。
1.  进入 F 的左子树 (L)，完成后再访问 F。
    *   进入 D 的左子树 (L)，完成后再访问 D。
        *   进入 B 的左子树 (L)，完成后再访问 B。
            *   进入 A 的左子树 (L)（为空），访问 A (D)，进入 A 的右子树 (R)（为空）。A 完成。
        *   访问 B (D)。
        *   进入 B 的右子树 (R)。
            *   进入 C 的左子树 (L)（为空），访问 C (D)，进入 C 的右子树 (R)（为空）。C 完成。
    *   访问 D (D)。
    *   进入 D 的右子树 (R)。
        *   进入 E 的左子树 (L)（为空），访问 E (D)，进入 E 的右子树 (R)（为空）。E 完成。
2.  访问 F (D)。
3.  进入 F 的右子树 (R)。
    *   进入 J 的左子树 (L)，完成后再访问 J。
        *   进入 G 的左子树 (L)（为空），访问 G (D)。
        *   进入 G 的右子树 (R)。
            *   进入 I 的左子树 (L)。
                *   进入 H 的左子树 (L)（为空），访问 H (D)，进入 H 的右子树 (R)（为空）。H 完成。
            *   访问 I (D)。
            *   进入 I 的右子树 (R)（为空）。
    *   访问 J (D)。
    *   进入 J 的右子树 (R)。
        *   进入 K 的左子树 (L)（为空），访问 K (D)，进入 K 的右子树 (R)（为空）。K 完成。

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_142.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_143.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_144.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_146.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_148.png)

因此，中序遍历顺序为：**A, B, C, D, E, F, G, H, I, J, K**

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_150.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_151.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_152.png)

**后序遍历顺序推导**：
遵循 `LRD` 规则，推导过程类似，结果为：**A, C, B, E, D, H, I, G, K, J, F**

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_154.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_156.png)

> **提示**：示例树实际上是一棵二叉搜索树（BST），对于每个节点，左子树所有节点的值都小于它，右子树所有节点的值都大于它。因此，中序遍历（左-根-右）二叉搜索树会得到一个**有序的列表**。你可以验证上面的中序遍历结果 A, B, C, D, E, F, G, H, I, J, K 确实是升序排列的。

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_157.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_158.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_159.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_161.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_162.png)

## 总结 📚

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_164.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_165.png)

本节课中我们一起学习了二叉树的遍历策略。
*   我们首先理解了树作为非线性数据结构，其遍历比线性结构更复杂。
*   接着，我们学习了两种主要的遍历分类：**广度优先遍历**（层序遍历）和**深度优先遍历**。
*   然后，我们深入探讨了三种深度优先遍历策略：**先序遍历** (`DLR`)、**中序遍历** (`LDR`) 和**后序遍历** (`LRD`)，并通过示例树手动推导了它们的访问顺序。
*   最后，我们了解到中序遍历二叉搜索树会得到一个有序序列。

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_166.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_167.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_168.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_170.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_171.png)

在下一节课中，我们将讨论如何用代码实现这三种遍历算法。