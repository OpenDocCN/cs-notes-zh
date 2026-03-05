# 051：AVL树源码解析 🧮

在本节课中，我们将一起学习AVL树的源代码实现。我们将分析一个用Java编写的递归式AVL树，理解其核心数据结构、平衡因子的维护以及插入和删除操作背后的逻辑。请确保你已经学习了之前关于AVL树旋转、插入和删除的三节课程，以便更好地理解即将展示的代码。

## 源码概览与演示

上一节我们探讨了AVL树的理论操作，本节中我们来看看其具体的代码实现。

![](img/07d81f9fd4e51f44b327832f10487ce5_1.png)

首先，本节所使用的完整源代码可以在Github仓库中找到：
> Github链接: github.com/sphysia/data_structures

在深入代码之前，我们先看一个AVL树的动态演示。我编译并运行了Java代码，程序随机生成了一棵AVL树并插入了一些节点。你可以观察到，即使经过随机插入，这棵树依然保持了良好的平衡性。如果这是一棵普通的二叉搜索树，结构可能会松散许多，这正体现了AVL树在维持平衡方面的优势。

现在，我们开始解析源代码。

## AVL树类结构定义

以下是AVL树核心类的定义，它包含了节点内部类和树的基本框架。

```java
public class AVLTreeRecursive <T extends Comparable<T>> {
    // 节点内部类定义
    private class Node {
        // 节点属性与构造函数
    }
    // 树的根节点和节点计数器
    private Node root;
    private int nodeCount = 0;
    // 核心方法：插入、删除、查询等
}
```

这个类是一个泛型类，要求存储的元素类型 `T` 必须实现 `Comparable` 接口，以便进行比较。它主要包含一个私有的 `Node` 内部类和几个关键属性。

## 节点内部类详解

接下来，我们详细查看构成AVL树基础的节点内部类。

```java
private class Node {
    // 平衡因子，计算公式为: bf = height(right subtree) - height(left subtree)
    public int bf;
    // 节点存储的实际值
    public T value;
    // 节点高度，初始为0
    public int height;
    // 左右子节点的引用
    public Node left, right;
    public Node(T value) {
        this.value = value;
    }
}
```

节点类封装了AVL树的核心信息：
*   **`bf`**： 平衡因子。这是AVL树平衡的关键，其值定义为 **`右子树高度 - 左子树高度`**。对于平衡节点，`bf` 的值应为 -1， 0 或 1。
*   **`value`**： 节点存储的数据。
*   **`height`**： 以该节点为根的子树的高度。叶子节点的高度为0。
*   **`left`， `right`**： 指向左、右子节点的指针。

![](img/07d81f9fd4e51f44b327832f10487ce5_3.png)

## 辅助方法：更新与平衡工具

在实现插入和删除操作前，我们需要一些辅助方法来维护树的平衡状态。

### 1. 更新节点高度与平衡因子

这是一个关键操作，在每次树的结构发生变化后（如旋转、插入子节点），都必须调用它来重新计算节点的高度和平衡因子。

```java
// 更新一个节点的高度和平衡因子
private void update(Node node) {
    // 处理空节点情况
    if (node == null) return;
    // 计算左右子树的高度，空子树高度为-1
    int leftNodeHeight = (node.left == null) ? -1 : node.left.height;
    int rightNodeHeight = (node.right == null) ? -1 : node.right.height;
    // 更新本节点高度: 1 + 左右子树中较高的那个高度
    node.height = 1 + Math.max(leftNodeHeight, rightNodeHeight);
    // 更新平衡因子: 右子树高度 - 左子树高度
    node.bf = rightNodeHeight - leftNodeHeight;
}
```

### 2. 平衡操作：旋转

当节点的平衡因子超出 `[-1， 1]` 的范围时，需要通过旋转来恢复平衡。以下是四种旋转情况的实现。

```java
// 左旋 (适用于左左情况)
private Node leftLeftCase(Node node) {
    return rightRotation(node);
}
// 右旋 (适用于右右情况)
private Node rightRightCase(Node node) {
    return leftRotation(node);
}
// 左右旋 (适用于左右情况)
private Node leftRightCase(Node node) {
    node.left = leftRotation(node.left);
    return leftLeftCase(node);
}
// 右左旋 (适用于右左情况)
private Node rightLeftCase(Node node) {
    node.right = rightRotation(node.right);
    return rightRightCase(node);
}
```

每种情况都对应着之前课程中讲解的一种不平衡模式，并通过调用基本的右旋或左旋操作来解决。

### 3. 基础旋转方法

以下是实现平衡的最基本操作：右旋转和左旋转。

```java
// 右旋转
private Node rightRotation(Node node) {
    Node newParent = node.left;
    node.left = newParent.right;
    newParent.right = node;
    // 旋转后，必须更新被移动的节点的高度和平衡因子
    update(node);
    update(newParent);
    return newParent;
}
// 左旋转
private Node leftRotation(Node node) {
    Node newParent = node.right;
    node.right = newParent.left;
    newParent.left = node;
    // 旋转后，必须更新被移动的节点的高度和平衡因子
    update(node);
    update(newParent);
    return newParent;
}
```

旋转操作不仅改变了节点的链接关系，最后调用 `update` 方法确保相关节点的 `height` 和 `bf` 信息是正确的。

### 4. 平衡节点

这个方法根据当前节点的平衡因子 `bf`，判断属于哪种不平衡情况，并调用相应的旋转方法。

```java
// 平衡以`node`为根的子树
private Node balance(Node node) {
    // 左子树更高，可能导致左左或左右情况
    if (node.bf == -2) {
        // 左左情况: 左子节点的平衡因子 <= 0
        if (node.left.bf <= 0) {
            return leftLeftCase(node);
        // 左右情况: 左子节点的平衡因子 > 0
        } else {
            return leftRightCase(node);
        }
    // 右子树更高，可能导致右右或右左情况
    } else if (node.bf == +2) {
        // 右右情况: 右子节点的平衡因子 >= 0
        if (node.right.bf >= 0) {
            return rightRightCase(node);
        // 右左情况: 右子节点的平衡因子 < 0
        } else {
            return rightLeftCase(node);
        }
    }
    // 平衡因子在-1，0，1之间，树是平衡的，直接返回原节点
    return node;
}
```

## 核心操作：插入与删除

掌握了平衡工具后，我们来看AVL树最核心的插入和删除操作，它们都是递归实现的。

![](img/07d81f9fd4e51f44b327832f10487ce5_5.png)

### 插入操作

插入操作递归地找到合适的位置添加新节点，并在回溯路径上更新和平衡每个节点。

```java
public boolean insert(T value) {
    // 如果值已存在，则不插入
    if (value == null || contains(value)) return false;
    root = insert(root, value);
    nodeCount++;
    return true;
}
private Node insert(Node node, T value) {
    // 递归基准情况: 到达空位，创建新节点
    if (node == null) return new Node(value);
    // 比较大小，决定插入左子树还是右子树
    int cmp = value.compareTo(node.value);
    if (cmp < 0) {
        node.left = insert(node.left, value);
    } else {
        node.right = insert(node.right, value);
    }
    // 回溯: 更新当前节点的高度和平衡因子，然后进行平衡操作
    update(node);
    return balance(node);
}
```

### 删除操作

删除操作比插入更复杂，需要处理找到替代节点（左子树的最大值或右子树的最小值）的情况。

```java
public boolean remove(T elem) {
    if (elem == null || !contains(elem)) return false;
    root = remove(root, elem);
    nodeCount--;
    return true;
}
private Node remove(Node node, T value) {
    if (node == null) return null;
    int cmp = value.compareTo(node.value);
    // 递归查找要删除的节点
    if (cmp < 0) {
        node.left = remove(node.left, value);
    } else if (cmp > 0) {
        node.right = remove(node.right, value);
    } else {
        // 找到要删除的节点
        // 情况1: 只有右子树或没有子树
        if (node.left == null) {
            return node.right;
        // 情况2: 只有左子树
        } else if (node.right == null) {
            return node.left;
        // 情况3: 有左右子树
        } else {
            // 选择左子树中的最大值作为后继节点
            if (node.left.height > node.right.height) {
                T successorValue = findMax(node.left);
                node.value = successorValue; // 用后继值覆盖当前值
                node.left = remove(node.left, successorValue); // 删除原来的后继节点
            // 选择右子树中的最小值作为后继节点
            } else {
                T successorValue = findMin(node.right);
                node.value = successorValue; // 用后继值覆盖当前值
                node.right = remove(node.right, successorValue); // 删除原来的后继节点
            }
        }
    }
    // 回溯: 更新当前节点的高度和平衡因子，然后进行平衡操作
    update(node);
    return balance(node);
}
// 辅助方法：查找子树中的最小/最大值
private T findMin(Node node) { while (node.left != null) node = node.left; return node.value; }
private T findMax(Node node) { while (node.right != null) node = node.right; return node.value; }
```

![](img/07d81f9fd4e51f44b327832f10487ce5_7.png)

## 总结

本节课中我们一起学习了AVL树的递归式Java源码实现。我们从类的整体结构开始，深入分析了`Node`节点的构成，然后逐步讲解了维持AVL树平衡的核心机制：包括更新高度和平衡因子的`update`方法，以及处理四种不平衡情况的旋转操作`balance`。最后，我们剖析了插入`insert`和删除`remove`这两个关键操作的递归实现逻辑，看到了它们如何在修改树结构后，通过回溯路径调用`update`和`balance`来确保树的平衡性。理解这份源码，能帮助你巩固AVL树的理论知识，并掌握如何将其转化为实际的代码。