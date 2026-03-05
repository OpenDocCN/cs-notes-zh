# 034：二叉树的深度优先遍历 🌳

![](img/def8e156c486e964b5fec4df027d80a5_1.png)

![](img/def8e156c486e964b5fec4df027d80a5_2.png)

![](img/def8e156c486e964b5fec4df027d80a5_3.png)

![](img/def8e156c486e964b5fec4df027d80a5_4.png)

![](img/def8e156c486e964b5fec4df027d80a5_5.png)

![](img/def8e156c486e964b5fec4df027d80a5_7.png)

![](img/def8e156c486e964b5fec4df027d80a5_8.png)

![](img/def8e156c486e964b5fec4df027d80a5_9.png)

在本节课中，我们将要学习二叉树的三种深度优先遍历算法：前序遍历、中序遍历和后序遍历。上一节我们介绍了二叉树的层序遍历（广度优先遍历），本节中我们来看看基于递归思想的深度优先策略。

![](img/def8e156c486e964b5fec4df027d80a5_11.png)

![](img/def8e156c486e964b5fec4df027d80a5_12.png)

![](img/def8e156c486e964b5fec4df027d80a5_13.png)

![](img/def8e156c486e964b5fec4df027d80a5_15.png)

![](img/def8e156c486e964b5fec4df027d80a5_16.png)

![](img/def8e156c486e964b5fec4df027d80a5_17.png)

![](img/def8e156c486e964b5fec4df027d80a5_18.png)

## 深度优先遍历的核心思想

![](img/def8e156c486e964b5fec4df027d80a5_20.png)

![](img/def8e156c486e964b5fec4df027d80a5_21.png)

![](img/def8e156c486e964b5fec4df027d80a5_22.png)

深度优先遍历的策略是，当我们选择了一个方向（例如向左），就会先访问完该方向上的所有节点（即整个子树），然后才会转向其他方向。

![](img/def8e156c486e964b5fec4df027d80a5_24.png)

![](img/def8e156c486e964b5fec4df027d80a5_25.png)

![](img/def8e156c486e964b5fec4df027d80a5_26.png)

![](img/def8e156c486e964b5fec4df027d80a5_27.png)

![](img/def8e156c486e964b5fec4df027d80a5_29.png)

![](img/def8e156c486e964b5fec4df027d80a5_30.png)

![](img/def8e156c486e964b5fec4df027d80a5_31.png)

![](img/def8e156c486e964b5fec4df027d80a5_32.png)

访问一个节点意味着读取或处理该节点的数据。访问一棵子树则意味着以深度优先策略访问该子树中的所有节点。

![](img/def8e156c486e964b5fec4df027d80a5_34.png)

![](img/def8e156c486e964b5fec4df027d80a5_35.png)

![](img/def8e156c486e964b5fec4df027d80a5_37.png)

![](img/def8e156c486e964b5fec4df027d80a5_39.png)

整个遍历过程可以看作一个递归问题：访问整棵树等价于 **访问根节点 + 访问左子树 + 访问右子树**。

![](img/def8e156c486e964b5fec4df027d80a5_41.png)

![](img/def8e156c486e964b5fec4df027d80a5_42.png)

![](img/def8e156c486e964b5fec4df027d80a5_43.png)

![](img/def8e156c486e964b5fec4df027d80a5_45.png)

![](img/def8e156c486e964b5fec4df027d80a5_46.png)

![](img/def8e156c486e964b5fec4df027d80a5_47.png)

## 三种遍历方式的定义

![](img/def8e156c486e964b5fec4df027d80a5_49.png)

![](img/def8e156c486e964b5fec4df027d80a5_51.png)

![](img/def8e156c486e964b5fec4df027d80a5_52.png)

![](img/def8e156c486e964b5fec4df027d80a5_53.png)

![](img/def8e156c486e964b5fec4df027d80a5_55.png)

在约定**左子树总是先于右子树访问**的前提下，根节点（R）、左子树（L）、右子树（R）的访问顺序有三种排列，对应三种遍历方式：

![](img/def8e156c486e964b5fec4df027d80a5_57.png)

![](img/def8e156c486e964b5fec4df027d80a5_59.png)

![](img/def8e156c486e964b5fec4df027d80a5_60.png)

![](img/def8e156c486e964b5fec4df027d80a5_61.png)

![](img/def8e156c486e964b5fec4df027d80a5_62.png)

以下是三种遍历方式的定义：
*   **前序遍历**：顺序为 **根节点 -> 左子树 -> 右子树**。
*   **中序遍历**：顺序为 **左子树 -> 根节点 -> 右子树**。
*   **后序遍历**：顺序为 **左子树 -> 右子树 -> 根节点**。

![](img/def8e156c486e964b5fec4df027d80a5_63.png)

![](img/def8e156c486e964b5fec4df027d80a5_65.png)

![](img/def8e156c486e964b5fec4df027d80a5_66.png)

![](img/def8e156c486e964b5fec4df027d80a5_68.png)

![](img/def8e156c486e964b5fec4df027d80a5_69.png)

对于子树，我们以同样的递归方式进行访问。例如，在前序遍历中，对于左子树，我们同样按照“根-左-右”的顺序进行。

![](img/def8e156c486e964b5fec4df027d80a5_71.png)

![](img/def8e156c486e964b5fec4df027d80a5_72.png)

![](img/def8e156c486e964b5fec4df027d80a5_74.png)

![](img/def8e156c486e964b5fec4df027d80a5_75.png)

![](img/def8e156c486e964b5fec4df027d80a5_77.png)

## 前序遍历的代码实现与解析

![](img/def8e156c486e964b5fec4df027d80a5_79.png)

![](img/def8e156c486e964b5fec4df027d80a5_81.png)

![](img/def8e156c486e964b5fec4df027d80a5_82.png)

![](img/def8e156c486e964b5fec4df027d80a5_83.png)

![](img/def8e156c486e964b5fec4df027d80a5_85.png)

这些算法的实现非常直观。让我们先看看前序遍历的代码。

![](img/def8e156c486e964b5fec4df027d80a5_87.png)

![](img/def8e156c486e964b5fec4df027d80a5_88.png)

以下是前序遍历函数的C/C++伪代码描述：
```c
void Preorder(struct node* root) {
    if(root == NULL) return; // 基线条件：空树则返回
    printf("%c ", root->data); // 1. 访问根节点
    Preorder(root->left); // 2. 递归访问左子树
    Preorder(root->right); // 3. 递归访问右子树
}
```
其中，节点结构体定义如下：
```c
struct node {
    char data;
    struct node* left;
    struct node* right;
};
```

![](img/def8e156c486e964b5fec4df027d80a5_90.png)

![](img/def8e156c486e964b5fec4df027d80a5_91.png)

![](img/def8e156c486e964b5fec4df027d80a5_92.png)

![](img/def8e156c486e964b5fec4df027d80a5_93.png)

![](img/def8e156c486e964b5fec4df027d80a5_94.png)

![](img/def8e156c486e964b5fec4df027d80a5_95.png)

函数首先检查根节点是否为空（基线条件）。若非空，则执行三步操作：打印当前节点数据，然后递归调用自身处理左子树，最后递归处理右子树。

![](img/def8e156c486e964b5fec4df027d80a5_97.png)

![](img/def8e156c486e964b5fec4df027d80a5_98.png)

![](img/def8e156c486e964b5fec4df027d80a5_99.png)

![](img/def8e156c486e964b5fec4df027d80a5_100.png)

![](img/def8e156c486e964b5fec4df027d80a5_101.png)

![](img/def8e156c486e964b5fec4df027d80a5_102.png)

### 递归过程可视化

![](img/def8e156c486e964b5fec4df027d80a5_103.png)

![](img/def8e156c486e964b5fec4df027d80a5_104.png)

![](img/def8e156c486e964b5fec4df027d80a5_105.png)

![](img/def8e156c486e964b5fec4df027d80a5_106.png)

![](img/def8e156c486e964b5fec4df027d80a5_107.png)

![](img/def8e156c486e964b5fec4df027d80a5_109.png)

![](img/def8e156c486e964b5fec4df027d80a5_110.png)

为了理解递归如何工作，我们以一个具体的二叉树为例，逐步跟踪 `Preorder` 函数的执行。

![](img/def8e156c486e964b5fec4df027d80a5_112.png)

![](img/def8e156c486e964b5fec4df027d80a5_113.png)

![](img/def8e156c486e964b5fec4df027d80a5_114.png)

假设我们有一棵二叉树，根节点地址为200，其数据为 ‘F’。调用 `Preorder(200)`。
1.  根非空，打印 ‘F’。
2.  递归调用 `Preorder(150)` 访问左子树。原调用暂停。
3.  对于 `Preorder(150)`，打印 ‘D’，然后递归调用 `Preorder(400)`。
4.  此过程持续进行，直到遇到空节点（`root == NULL`），函数直接返回，上一级调用得以恢复并继续执行。

![](img/def8e156c486e964b5fec4df027d80a5_116.png)

![](img/def8e156c486e964b5fec4df027d80a5_117.png)

![](img/def8e156c486e964b5fec4df027d80a5_118.png)

![](img/def8e156c486e964b5fec4df027d80a5_119.png)

递归调用会在程序内存的**调用栈**中分配空间。虽然代码中没有显式使用额外内存，但递归隐式地使用了栈空间。

![](img/def8e156c486e964b5fec4df027d80a5_120.png)

![](img/def8e156c486e964b5fec4df027d80a5_121.png)

![](img/def8e156c486e964b5fec4df027d80a5_122.png)

![](img/def8e156c486e964b5fec4df027d80a5_123.png)

![](img/def8e156c486e964b5fec4df027d80a5_124.png)

![](img/def8e156c486e964b5fec4df027d80a5_125.png)

![](img/def8e156c486e964b5fec4df027d80a5_126.png)

![](img/def8e156c486e964b5fec4df027d80a5_128.png)

### 空间复杂度分析

![](img/def8e156c486e964b5fec4df027d80a5_129.png)

![](img/def8e156c486e964b5fec4df027d80a5_130.png)

![](img/def8e156c486e964b5fec4df027d80a5_132.png)

调用栈的最大深度取决于树的高度。因此，这些遍历算法的**空间复杂度为 O(h)**，其中 **h** 是树的高度。
*   在最坏情况下（树退化为链表），h = n-1，空间复杂度为 **O(n)**。
*   在最好或平均情况下（平衡树），h = log₂n，空间复杂度为 **O(log n)**。

![](img/def8e156c486e964b5fec4df027d80a5_134.png)

![](img/def8e156c486e964b5fec4df027d80a5_135.png)

![](img/def8e156c486e964b5fec4df027d80a5_136.png)

![](img/def8e156c486e964b5fec4df027d80a5_137.png)

![](img/def8e156c486e964b5fec4df027d80a5_138.png)

![](img/def8e156c486e964b5fec4df027d80a5_139.png)

![](img/def8e156c486e964b5fec4df027d80a5_141.png)

![](img/def8e156c486e964b5fec4df027d80a5_142.png)

## 中序遍历与后序遍历的实现

![](img/def8e156c486e964b5fec4df027d80a5_144.png)

![](img/def8e156c486e964b5fec4df027d80a5_145.png)

![](img/def8e156c486e964b5fec4df027d80a5_147.png)

![](img/def8e156c486e964b5fec4df027d80a5_148.png)

![](img/def8e156c486e964b5fec4df027d80a5_150.png)

![](img/def8e156c486e964b5fec4df027d80a5_151.png)

理解了前序遍历后，中序和后序遍历的代码就非常容易编写了，它们仅在于访问根节点的时机不同。

![](img/def8e156c486e964b5fec4df027d80a5_153.png)

![](img/def8e156c486e964b5fec4df027d80a5_154.png)

![](img/def8e156c486e964b5fec4df027d80a5_155.png)

![](img/def8e156c486e964b5fec4df027d80a5_156.png)

以下是中序遍历函数的代码：
```c
void Inorder(struct node* root) {
    if(root == NULL) return;
    Inorder(root->left); // 1. 递归访问左子树
    printf("%c ", root->data); // 2. 访问根节点
    Inorder(root->right); // 3. 递归访问右子树
}
```

![](img/def8e156c486e964b5fec4df027d80a5_157.png)

![](img/def8e156c486e964b5fec4df027d80a5_158.png)

![](img/def8e156c486e964b5fec4df027d80a5_160.png)

![](img/def8e156c486e964b5fec4df027d80a5_161.png)

![](img/def8e156c486e964b5fec4df027d80a5_162.png)

![](img/def8e156c486e964b5fec4df027d80a5_163.png)

以下是后序遍历函数的代码：
```c
void Postorder(struct node* root) {
    if(root == NULL) return;
    Postorder(root->left); // 1. 递归访问左子树
    Postorder(root->right); // 2. 递归访问右子树
    printf("%c ", root->data); // 3. 访问根节点
}
```

![](img/def8e156c486e964b5fec4df027d80a5_165.png)

![](img/def8e156c486e964b5fec4df027d80a5_166.png)

![](img/def8e156c486e964b5fec4df027d80a5_167.png)

![](img/def8e156c486e964b5fec4df027d80a5_169.png)

![](img/def8e156c486e964b5fec4df027d80a5_170.png)

![](img/def8e156c486e964b5fec4df027d80a5_171.png)

对于一个二叉搜索树，**中序遍历的输出结果恰好是所有节点值的升序序列**。

![](img/def8e156c486e964b5fec4df027d80a5_173.png)

![](img/def8e156c486e964b5fec4df027d80a5_174.png)

![](img/def8e156c486e964b5fec4df027d80a5_175.png)

![](img/def8e156c486e964b5fec4df027d80a5_176.png)

![](img/def8e156c486e964b5fec4df027d80a5_178.png)

![](img/def8e156c486e964b5fec4df027d80a5_179.png)

## 时间复杂度总结

![](img/def8e156c486e964b5fec4df027d80a5_181.png)

对于所有三种深度优先遍历算法，每个节点都会被访问一次（执行一次打印操作）。因此，它们的**时间复杂度都是 O(n)**，其中 **n** 是树中的节点总数。

![](img/def8e156c486e964b5fec4df027d80a5_183.png)

![](img/def8e156c486e964b5fec4df027d80a5_184.png)

![](img/def8e156c486e964b5fec4df027d80a5_185.png)

![](img/def8e156c486e964b5fec4df027d80a5_187.png)

![](img/def8e156c486e964b5fec4df027d80a5_188.png)

![](img/def8e156c486e964b5fec4df027d80a5_189.png)

![](img/def8e156c486e964b5fec4df027d80a5_190.png)

本节课中我们一起学习了二叉树的三种深度优先遍历算法：前序、中序和后序。我们理解了它们基于递归的定义，掌握了其代码实现，并分析了时间与空间复杂度。在接下来的课程中，我们将运用这些遍历方法来解决一些具体的二叉树问题。