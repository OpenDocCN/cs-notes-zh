# 027：二叉搜索树 🎯

![](img/bb7151e6bd3062ace2030a53bb8a53a8_1.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_2.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_3.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_5.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_7.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_9.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_10.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_11.png)

在本节课中，我们将要学习一种特殊的二叉树——**二叉搜索树**。它是一种高效的数据结构，能够支持快速的数据搜索和更新操作。我们将从理解其必要性开始，逐步探讨其定义、性质以及核心操作的时间复杂度。

![](img/bb7151e6bd3062ace2030a53bb8a53a8_13.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_15.png)

上一节我们介绍了二叉树的基本概念，本节中我们来看看一种应用广泛的特殊二叉树。

![](img/bb7151e6bd3062ace2030a53bb8a53a8_17.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_18.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_19.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_20.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_21.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_22.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_23.png)

## 为什么需要二叉搜索树？🤔

![](img/bb7151e6bd3062ace2030a53bb8a53a8_25.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_26.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_28.png)

假设你需要存储一个可修改的数据集合（例如一组整数），并希望高效地执行以下操作：
*   **搜索**：快速查找集合中是否存在某个记录。
*   **插入**：向集合中添加一个新记录。
*   **删除**：从集合中移除一个记录。

![](img/bb7151e6bd3062ace2030a53bb8a53a8_30.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_31.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_33.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_34.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_36.png)

你会选择什么数据结构？以下是两种常见选择及其操作的时间复杂度分析。

![](img/bb7151e6bd3062ace2030a53bb8a53a8_38.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_39.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_41.png)

### 使用数组

![](img/bb7151e6bd3062ace2030a53bb8a53a8_43.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_45.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_46.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_47.png)

如果使用一个足够大的数组来存储集合，并标记列表的末尾，各操作的时间复杂度如下：

![](img/bb7151e6bd3062ace2030a53bb8a53a8_48.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_49.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_50.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_52.png)

*   **搜索**：在最坏情况下，需要遍历整个数组。时间复杂度为 **O(n)**。
*   **插入**：如果数组未满，只需在末尾添加元素并更新标记。时间复杂度为 **O(1)**。但如果数组已满，需要创建新数组并复制数据，此时时间复杂度为 **O(n)**。
*   **删除**：删除元素后，需要将其右侧所有元素向左移动一位以保持连续性。在最坏情况下，时间复杂度为 **O(n)**。

![](img/bb7151e6bd3062ace2030a53bb8a53a8_54.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_55.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_56.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_57.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_59.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_60.png)

### 使用链表

![](img/bb7151e6bd3062ace2030a53bb8a53a8_62.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_63.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_65.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_67.png)

如果使用链表来存储集合，各操作的时间复杂度如下：

![](img/bb7151e6bd3062ace2030a53bb8a53a8_69.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_71.png)

*   **搜索**：在最坏情况下，需要遍历整个链表。时间复杂度为 **O(n)**。
*   **插入**：在链表头部插入，时间复杂度为 **O(1)**。
*   **删除**：需要先找到要删除的节点，在最坏情况下需要遍历整个链表。时间复杂度为 **O(n)**。

![](img/bb7151e6bd3062ace2030a53bb8a53a8_73.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_74.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_75.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_76.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_78.png)

### 现有方案的局限性

![](img/bb7151e6bd3062ace2030a53bb8a53a8_80.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_81.png)

对于搜索操作，**O(n)** 的时间复杂度在处理大规模数据时可能成为瓶颈。例如，如果一次比较耗时 `10^-6` 秒，在包含1亿条记录的集合中搜索，最坏情况可能需要100秒，这通常是不可接受的。

![](img/bb7151e6bd3062ace2030a53bb8a53a8_83.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_84.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_85.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_86.png)

我们能否做得更好？如果使用**有序数组**，我们可以利用**二分查找**算法将搜索的时间复杂度降至 **O(log n)**。对于1亿条数据，最多只需约27次比较，速度极快。

![](img/bb7151e6bd3062ace2030a53bb8a53a8_87.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_88.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_89.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_91.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_92.png)

然而，有序数组在插入和删除时，为了保持有序性，需要进行大量的元素移动，这两个操作的时间复杂度仍然是 **O(n)**。

![](img/bb7151e6bd3062ace2030a53bb8a53a8_94.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_95.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_96.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_97.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_99.png)

因此，我们需要一种数据结构，能同时支持**快速的搜索、插入和删除**操作。这就是**二叉搜索树**要解决的问题。

## 什么是二叉搜索树？🌲

![](img/bb7151e6bd3062ace2030a53bb8a53a8_101.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_102.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_103.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_104.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_105.png)

二叉搜索树是一种特殊的二叉树，它满足以下性质：
对于树中的**任意一个节点**：
1.  其**左子树**中所有节点的值都**小于或等于**该节点的值。
2.  其**右子树**中所有节点的值都**大于**该节点的值。
3.  其左、右子树也分别是二叉搜索树。

![](img/bb7151e6bd3062ace2030a53bb8a53a8_107.png)

这个性质是递归定义的。用伪代码可以描述其核心约束：
```
对于任意节点 node：
    node.left 子树中的所有值 <= node.value < node.right 子树中的所有值
```

![](img/bb7151e6bd3062ace2030a53bb8a53a8_108.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_109.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_110.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_111.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_112.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_113.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_114.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_115.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_117.png)

下图展示了一个有效的二叉搜索树示例：
```
        15
       /  \
      10   20
     / \   / \
    8  12 17  25
```
*   根节点15：左子树(8,10,12)均≤15，右子树(17,20,25)均>15。
*   节点10：左孩子8≤10，右孩子12>10。
*   节点20：左孩子17≤20，右孩子25>20。

![](img/bb7151e6bd3062ace2030a53bb8a53a8_118.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_120.png)

如果我们将节点12改为16，那么对于根节点15，其左子树中出现了大于15的值(16)，这违反了二叉搜索树的性质，因此就不再是有效的二叉搜索树。

![](img/bb7151e6bd3062ace2030a53bb8a53a8_121.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_122.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_123.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_125.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_126.png)

## 二叉搜索树的操作效率 ⚡

![](img/bb7151e6bd3062ace2030a53bb8a53a8_128.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_129.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_130.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_131.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_132.png)

在平衡的二叉搜索树中，搜索、插入和删除操作的平均时间复杂度都可以达到 **O(log n)**。这是如何实现的呢？

![](img/bb7151e6bd3062ace2030a53bb8a53a8_133.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_134.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_136.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_137.png)

### 搜索操作

![](img/bb7151e6bd3062ace2030a53bb8a53a8_139.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_140.png)

搜索过程与有序数组的二分查找思想类似：
1.  从根节点开始。
2.  将目标值与当前节点值比较：
    *   如果相等，搜索成功。
    *   如果目标值**小于**当前节点值，根据BST性质，目标只可能存在于**左子树**中，于是进入左子树继续搜索。
    *   如果目标值**大于**当前节点值，则进入**右子树**继续搜索。
3.  重复步骤2，直到找到目标或到达空节点（未找到）。

![](img/bb7151e6bd3062ace2030a53bb8a53a8_142.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_143.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_144.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_145.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_146.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_148.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_149.png)

**每一次比较，我们都丢弃了当前节点的其中一个子树（将近一半的搜索空间）**。在平衡的树中，这导致搜索空间呈指数级缩小（n, n/2, n/4, ...），经过大约 **log₂n** 步后，搜索空间会缩小到1。因此时间复杂度为 **O(log n)**。

![](img/bb7151e6bd3062ace2030a53bb8a53a8_150.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_152.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_153.png)

### 插入操作

![](img/bb7151e6bd3062ace2030a53bb8a53a8_154.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_155.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_156.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_158.png)

插入新节点前，需要先找到正确的插入位置。这个过程与搜索类似：
1.  从根节点开始，比较待插入值与当前节点值。
2.  根据比较结果决定向左或向右子树移动，直到到达一个**空位置**（即某个节点的左孩子或右孩子为空）。
3.  在该空位置创建新节点并建立链接。

![](img/bb7151e6bd3062ace2030a53bb8a53a8_159.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_160.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_161.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_162.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_164.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_165.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_167.png)

由于查找位置的过程是 **O(log n)**，而创建节点和建立链接是 **O(1)**，因此整体插入操作的平均时间复杂度也是 **O(log n)**。**与数组不同，这里不需要移动任何现有元素**。

### 删除操作

![](img/bb7151e6bd3062ace2030a53bb8a53a8_169.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_170.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_171.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_172.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_173.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_174.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_175.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_176.png)

删除操作稍复杂一些，但基本步骤是：
1.  **搜索**要删除的节点（**O(log n)**）。
2.  根据该节点的子节点情况（无子节点、有一个子节点、有两个子节点）进行不同的链接调整。
3.  调整链接的操作是 **O(1)**。

![](img/bb7151e6bd3062ace2030a53bb8a53a8_177.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_178.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_180.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_181.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_182.png)

因此，删除操作的平均时间复杂度同样是 **O(log n)**。

![](img/bb7151e6bd3062ace2030a53bb8a53a8_184.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_185.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_186.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_187.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_188.png)

## 平衡的重要性 ⚖️

![](img/bb7151e6bd3062ace2030a53bb8a53a8_189.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_190.png)

上述 **O(log n)** 的效率是基于二叉搜索树是**平衡**的这一前提。一棵树是平衡的，粗略地说，是指其左右子树的高度相差不大。

![](img/bb7151e6bd3062ace2030a53bb8a53a8_192.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_193.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_194.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_195.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_196.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_197.png)

考虑同样一组数据 `{8, 10, 12, 15, 17, 20, 25}`，可以构造出不同的BST：

![](img/bb7151e6bd3062ace2030a53bb8a53a8_198.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_200.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_201.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_202.png)

*   **平衡的BST（最佳情况）**：如上文示例，操作效率为 **O(log n)**。
    ```
        15
       /  \
      10   20
     / \   / \
    8  12 17  25
    ```
*   **不平衡的BST（最坏情况）**：如果数据按顺序插入（如8,10,12,15,...），树会退化成一条链。
    ```
        8
         \
          10
           \
            12
             \
              15
               \
                17
                 \
                  20
                   \
                    25
    ```
    在这种情况下，搜索、插入、删除都退化为链表的遍历操作，时间复杂度变为 **O(n)**。

![](img/bb7151e6bd3062ace2030a53bb8a53a8_204.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_205.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_206.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_207.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_208.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_209.png)

因此，在实际使用中，我们需要通过算法（如AVL树、红黑树）来维护二叉搜索树的平衡性，从而避免最坏情况，保证操作的高效性。我们将在后续课程中详细讨论这些平衡技术。

## 总结 📚

![](img/bb7151e6bd3062ace2030a53bb8a53a8_211.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_212.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_213.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_214.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_215.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_216.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_217.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_218.png)

本节课我们一起学习了二叉搜索树的核心知识：

![](img/bb7151e6bd3062ace2030a53bb8a53a8_219.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_220.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_222.png)

1.  **动机**：为了解决有序数组插入/删除慢，以及链表/无序数组搜索慢的问题，我们需要一种能同时支持快速搜索、插入和删除的数据结构。
2.  **定义**：二叉搜索树是一种二叉树，其中任意节点的左子树所有值 ≤ 节点值 < 右子树所有值。
3.  **操作效率**：在**平衡**的二叉搜索树中，搜索、插入和删除操作的平均时间复杂度均为 **O(log n)**。
4.  **关键思想**：利用树的结构和节点值的排序性质，在每一步操作中都能丢弃大约一半的搜索空间，这是其高效的根本原因。
5.  **注意事项**：必须维护树的平衡性，否则在最坏情况下（树退化为链表），时间复杂度会恶化到 **O(n)**。

![](img/bb7151e6bd3062ace2030a53bb8a53a8_224.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_225.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_226.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_227.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_228.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_229.png)

下一节课，我们将深入探讨二叉搜索树的具体代码实现。