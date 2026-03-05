# 037：二叉搜索树的中序后继节点 🔍

![](img/6a9b92df06a5a2551f62473daa3ab9cb_1.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_3.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_4.png)

在本节课中，我们将学习如何解决二叉搜索树上的一个有趣问题：给定树中的一个节点，找到它的中序后继节点。中序后继节点指的是，在对二叉搜索树进行中序遍历时，紧跟在给定节点之后被访问的那个节点。

![](img/6a9b92df06a5a2551f62473daa3ab9cb_6.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_8.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_9.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_11.png)

## 中序遍历回顾 📚

![](img/6a9b92df06a5a2551f62473daa3ab9cb_12.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_13.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_15.png)

上一节我们介绍了问题的定义，本节中我们来看看理解问题的基础——中序遍历。

![](img/6a9b92df06a5a2551f62473daa3ab9cb_17.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_18.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_19.png)

中序遍历是一种深度优先的遍历方式。对于二叉树中的任意节点，遍历顺序遵循“左子树 -> 根节点 -> 右子树”的递归规则。这意味着对于每个节点，我们总是先访问其所有左子节点，然后访问该节点本身，最后访问其所有右子节点。

![](img/6a9b92df06a5a2551f62473daa3ab9cb_21.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_23.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_24.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_25.png)

以下是中序遍历的递归函数实现框架：

![](img/6a9b92df06a5a2551f62473daa3ab9cb_27.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_28.png)

```cpp
void inorderTraversal(Node* root) {
    if (root == NULL) return;
    inorderTraversal(root->left);  // 访问左子树
    visit(root);                   // 访问根节点
    inorderTraversal(root->right); // 访问右子树
}
```

该函数包含两个递归调用，分别用于遍历左子树和右子树。中序遍历的时间复杂度为 **O(n)**，其中 `n` 是树中的节点总数，因为每个节点恰好被访问一次。

![](img/6a9b92df06a5a2551f62473daa3ab9cb_30.png)

## 二叉搜索树与中序序列 🔢

![](img/6a9b92df06a5a2551f62473daa3ab9cb_32.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_34.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_36.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_38.png)

二叉搜索树是一种特殊的二叉树，它满足一个关键性质：对于树中任意节点，其左子树中所有节点的值都小于该节点的值，其右子树中所有节点的值都大于该节点的值。这个性质可以用以下公式描述：

![](img/6a9b92df06a5a2551f62473daa3ab9cb_40.png)

对于节点 `node`：
*   所有 `node.left` 子树中的节点值 < `node.data`
*   所有 `node.right` 子树中的节点值 > `node.data`

![](img/6a9b92df06a5a2551f62473daa3ab9cb_41.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_42.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_43.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_45.png)

当我们对一棵二叉搜索树执行中序遍历时，一个重要的特性是：访问到的节点值序列是**升序排列**的。因此，寻找一个节点的中序后继，本质上就是在升序序列中寻找它的下一个值。

![](img/6a9b92df06a5a2551f62473daa3ab9cb_47.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_48.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_49.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_50.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_51.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_52.png)

虽然我们可以通过完整的中序遍历来找到后继节点，但这种方法的时间复杂度是 O(n)，效率不高。在二叉搜索树中，我们期望像查找、插入这样的操作能在 **O(h)** 时间内完成（`h` 为树高）。对于一个平衡的二叉搜索树，`h ≈ log₂(n)`，这使得操作非常高效。因此，我们的目标是设计一个时间复杂度为 **O(h)** 的算法来寻找中序后继。

![](img/6a9b92df06a5a2551f62473daa3ab9cb_54.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_56.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_57.png)

## 寻找中序后继的算法逻辑 🤔

现在，我们来探讨如何高效地找到中序后继。算法需要处理两种情况，这取决于给定节点是否有右子树。

![](img/6a9b92df06a5a2551f62473daa3ab9cb_59.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_60.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_61.png)

### 情况一：节点有右子树

![](img/6a9b92df06a5a2551f62473daa3ab9cb_63.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_65.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_66.png)

如果给定节点 `current` 拥有右子树，那么它的中序后继一定存在于这个右子树中。更具体地说，后继节点是**其右子树中值最小的节点**，也就是右子树里的“最左”节点。

**原因**：根据中序遍历“左-根-右”的顺序，访问完 `current` 节点后，下一个要访问的就是其右子树。而在右子树中，我们需要先遍历完所有左子节点，才能访问根节点，因此第一个被访问的节点就是右子树里的最左节点。

![](img/6a9b92df06a5a2551f62473daa3ab9cb_68.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_70.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_71.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_72.png)

### 情况二：节点没有右子树

![](img/6a9b92df06a5a2551f62473daa3ab9cb_74.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_75.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_77.png)

如果给定节点 `current` 没有右子树，情况就稍微复杂一些。我们需要向上回溯，找到这样一个祖先节点：`current` 节点位于该祖先节点的**左子树**中。这个祖先节点就是 `current` 的中序后继。

![](img/6a9b92df06a5a2551f62473daa3ab9cb_78.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_79.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_81.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_82.png)

**原因**：当 `current` 没有右子树时，意味着以 `current` 为根的子树已经遍历完毕。程序将回溯到 `current` 的父节点。如果 `current` 是其父节点的左孩子（即 `current` 在父节点的左子树中），那么根据“左-根-右”的顺序，父节点就是下一个被访问的节点，即后继。如果 `current` 是其父节点的右孩子，则说明父节点已经在访问 `current` 之前被访问过了，我们需要继续向上回溯，直到找到一个祖先节点，使得 `current` 位于它的左子树中。

![](img/6a9b92df06a5a2551f62473daa3ab9cb_84.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_85.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_87.png)

为了向上回溯，我们需要从树的根节点开始，向下搜索到 `current` 节点，并记录路径。在这个过程中，每当我们需要向左子节点移动时（即 `current.data < ancestor.data`），当前的 `ancestor` 节点就可能是后继节点（因为 `current` 在它的左子树里）。我们持续更新这个可能的 `successor`，直到找到 `current` 节点。最后记录的 `successor` 就是我们要找的答案。

![](img/6a9b92df06a5a2551f62473daa3ab9cb_89.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_90.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_91.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_93.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_94.png)

## 算法实现（C++）💻

![](img/6a9b92df06a5a2551f62473daa3ab9cb_96.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_98.png)

基于上述逻辑，我们可以编写 `getSuccessor` 函数。该函数接收树的根节点指针和需要查找后继的节点数据值，返回后继节点的指针。

![](img/6a9b92df06a5a2551f62473daa3ab9cb_100.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_102.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_104.png)

以下是核心代码实现：

![](img/6a9b92df06a5a2551f62473daa3ab9cb_105.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_107.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_109.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_111.png)

```cpp
// 辅助函数：在BST中查找值为data的节点
Node* Find(Node* root, int data) {
    if(root == NULL) return NULL;
    else if(root->data == data) return root;
    else if(root->data < data) return Find(root->right, data);
    else return Find(root->left, data);
}

![](img/6a9b92df06a5a2551f62473daa3ab9cb_113.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_115.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_117.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_119.png)

// 辅助函数：找到子树中的最小节点（最左节点）
Node* FindMin(Node* root) {
    if(root == NULL) return NULL;
    while(root->left != NULL)
        root = root->left;
    return root;
}

![](img/6a9b92df06a5a2551f62473daa3ab9cb_121.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_122.png)

// 主函数：获取中序后继
Node* GetSuccessor(Node* root, int data) {
    // 1. 搜索包含data的当前节点
    Node* current = Find(root, data);
    if(current == NULL) return NULL; // 节点不存在

    // 2. 情况1：节点有右子树
    if(current->right != NULL) {
        return FindMin(current->right); // 返回右子树中的最小节点
    }
    // 3. 情况2：节点没有右子树
    else {
        Node* successor = NULL;
        Node* ancestor = root;
        // 从根开始向下遍历到当前节点，并记录可能的后继
        while(ancestor != current) {
            if(current->data < ancestor->data) {
                successor = ancestor; // 当前祖先可能是后继
                ancestor = ancestor->left; // 向左走
            }
            else {
                ancestor = ancestor->right; // 向右走
            }
        }
        return successor; // 返回找到的后继，可能为NULL（如最大节点）
    }
}
```

![](img/6a9b92df06a5a2551f62473daa3ab9cb_124.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_125.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_126.png)

### 代码解析

![](img/6a9b92df06a5a2551f62473daa3ab9cb_128.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_129.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_130.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_131.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_133.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_134.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_135.png)

1.  **查找节点**：首先使用 `Find` 函数在BST中找到目标节点 `current`。这是一个标准的BST查找操作，时间复杂度为 O(h)。
2.  **处理有右子树的情况**：如果 `current->right` 不为空，则调用 `FindMin` 函数在其右子树中寻找最左节点并返回。
3.  **处理无右子树的情况**：初始化 `successor` 为 `NULL`，`ancestor` 为根节点。通过一个 `while` 循环从根节点向下走到 `current` 节点。在每一步，如果 `current` 的数据小于 `ancestor` 的数据，说明 `current` 在 `ancestor` 的左子树中，此时 `ancestor` 是一个潜在的后继，我们更新 `successor` 并走向左孩子；否则，走向右孩子。循环结束时，`successor` 中存储的就是我们需要的祖先节点。

![](img/6a9b92df06a5a2551f62473daa3ab9cb_137.png)

整个 `GetSuccessor` 函数的时间复杂度为 **O(h)**，其中 `h` 是树的高度，这符合我们对高效算法的期望。

![](img/6a9b92df06a5a2551f62473daa3ab9cb_139.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_140.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_141.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_142.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_143.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_144.png)

## 总结 🎯

![](img/6a9b92df06a5a2551f62473daa3ab9cb_146.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_147.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_148.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_150.png)

本节课我们一起学习了如何在二叉搜索树中寻找给定节点的中序后继。我们首先回顾了中序遍历的性质，并理解了在BST中，中序序列是升序的这一关键点。

![](img/6a9b92df06a5a2551f62473daa3ab9cb_152.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_153.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_154.png)

核心算法分为两种情况：
1.  若节点有右子树，则后继是**其右子树中的最小节点**。
2.  若节点无右子树，则后继是**从根节点到该节点的路径上，最后一个将其置于左子树中的祖先节点**。

![](img/6a9b92df06a5a2551f62473daa3ab9cb_156.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_158.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_159.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_160.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_161.png)

我们实现了时间复杂度为 O(h) 的算法，这对于保持平衡的二叉搜索树来说效率非常高。理解这个算法后，尝试编写寻找中序前驱节点的函数将是一个很好的练习。在接下来的课程中，我们将继续探索二叉树和二叉搜索树上的更多有趣问题。