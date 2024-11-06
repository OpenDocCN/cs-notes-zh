# 表示集合

## 集合简介

我们已经看到如何使用列表或树来引入结构的层次结构。有时我们不关心结构的层次结构；我们只需要知道某个数据是否在结构中。对于这个问题，一个有用的结构是**集合** - 一组唯一的数据。换句话说，集合永远不会包含两个相同的元素。例如，{cats dogs bears squirrels cats}不是一个集合，因为"cats"出现了两次。相反，{cats dogs bears squirrels}是一个集合。

在本课程中，我们将使用列表来表示一个集合 ADT。这意味着我们可以使用`list`创建集合，并使用`car`和`cdr`从集合中选择。���集将由一个空列表`null`表示。展望未来，这里是我们将为集合 ADT 定义的一些函数：

+   `element-of-set?`检查某个数据是否在集合中

+   `adjoin-set`向集合添加新数据。

+   `intersection-set`给定两个集合，返回一个只包含两个集合中都有的元素的新集合

## `element-of-set?`

`element-of-set?`接受两个参数，一个元素`x`和一个`set`，如果`x`在`set`中，则返回`#t`，否则返回`#f`：

```
(define (element-of-set? x set)
  (cond ((null? set) #f)
        ((equal? x (car set)) #t)
        (else (element-of-set? x (cdr set))))) 
```

这段代码类似于`memq`。我们使用`equal?`，因为集合的成员可以是数字、符号或其他任何东西。

**测试你的理解**

假设 set1 和 set2 的长度都为 n。

下面的函数调用的运行时间是多少？

```
(element-of-set? (car set1) set2) 
```

## `adjoin-set`

让我们继续学习`adjoin-set`！这个函数再次接受一个元素`x`和一个`set`。如果`x`是`set`的成员（我们可以使用我们的`element-of-set?`函数来检查），则不执行任何操作。否则，将`x`添加到`set`中：

```
(define (adjoin-set x set)
  (if (element-of-set? x set)
      set
      (cons x set))) 
```

## `intersection-set`

`intersection-set`稍微有些挑战。给定两个集合`set1`和`set2`，我们需要找到它们的[交集](https://en.wikipedia.org/wiki/Intersection_(set_theory))。我们将不得不以递归方式完成这个任务。让我们将这个问题分为几种情况：

+   如果任一集合为空，则返回`null`。

+   检查`(car set1)`是否在`set2`中。

    +   如果是这样，请将该元素包含在我们的答案中，并在`(cdr set1)`和`set2`上递归调用`intersection-set`。

    +   如果不在`set2`中，则在`(cdr set1)`和`set2`上递归调用`intersection-set`。

这是`intersection-set`的代码：

```
(define (intersection-set set1 set2)
  (cond ((or (null? set1) (null? set2)) '())
        ((element-of-set? (car set1) set2)        
         (cons (car set1)
               (intersection-set (cdr set1) set2)))
        (else (intersection-set (cdr set1) set2)))) 
```

**测试你的理解**

假设 set1 和 set2 的长度都为 n。

下面的函数调用的运行时间是多少？

```
(intersection-set set1 set2) 
```

## 有序列表作为集合

你可能已经注意到，我们之前实现的集合 ADT 相对较慢。找到两个集合的交集可能会相对于它们的大小具有二次运行时间。如果一个集合很大，这种实现将非常慢。但不用担心，我们可以通过使用**有序集合**来加快速度，其中数据必须按递增顺序存储。例如，`(1 3 4)`是一个有序集合，而`(1 5 3 4)`不是。

类似于按字母顺序排列名称将使名册更容易搜索，使用有序列表来表示集合将使搜索和操作它们变得更快。

## `element-of-set?`

有序列表的一个优点是，我们不必总是探索整个集合以找到某个特定元素。让我们对`element-of-set?`进行必要的更改，以利用有序属性。

`element-of-set?`仍然接受两个参数，一个是元素`x`，另一个是`set`。由于我们知道`set`中的元素是有序的，这意味着我们只需要从左到右扫描集合。

+   如果`(car set)`等于`x`，那么我们停止并返回`#t`。

+   否则，如果`(car set)`大于`x`，那么我们知道集合中的所有其他元素都将大于`x`，我们可以在这里停止并返回`#f`。

+   否则，如果`(car set)`小于`x`，我们将不得不继续到`set`中的下一个元素并重复此过程。

这意味着，如果我们幸运地`x`小于或等于`set`的第一个元素，我们甚至可以在不看`set`的其余部分的情况下自动返回`#f`或`#t`！

我们的`element-of-set?`代码将如下所示：

```
(define (element-of-set? x set)
  (cond ((null? set) false)
        ((= x (car set)) true)
        ((< x (car set)) false)
        (else (element-of-set? x (cdr set))))) 
```

**注意：** 我们假设我们集合中的所有元素都是数字。如果不是这种情况，上述代码将出错。

**检验你的理解**

假设`set1`和`set2`是有序列表，且长度都为 n。

下面的函数调用的运行时间是多少？

```
(element-of-set? (car set1) set2) 
```

## `intersection-set`

我们之前对于无序列表的`intersection-set`的实现将一个集合的每个元素与另一个集合的每个元素进行比较，导致其总运行时间为Θ(n²)。为了加快使用有序列表的此功能的速度，让我们使用不同的方法来实现此函数。我们可以将`intersection-set`分为基本情况（与以前相同）：

+   如果任一集合为空，则返回`null`

以及以下递归情况：

+   **`(= (car set1) (car set2))`:** 由于它们共享相同的元素，我们在答案中包含此元素，从两个集合中删除此元素，并通过调用`(intersection-set (cdr set1) (cdr set2))`检查其余部分。

+   **`(< (car set1) (car set2))`:** 由于`(car set2)`是`set2`中的最小元素，我们可以得出结论`(car set1)`小于`set2`的所有元素，因此不能在`set2`中。我们可以通过调用`(intersection-set (cdr set1) set2)`继续使用`set1`中的下一个最大成员进行搜索。

+   **`(> (car set1) (car set2))`:** 这是上述情况的镜像。由于`(car set1)`是`set1`中最小的成员，我们知道`(car set2)`小于`set1`的所有元素，因此不能在`set1`中。我们可以通过调用`(intersection-set set1 (cdr set2))`继续使用`set2`中的下一个最大成员进行搜索。

`intersection-set`的完整代码可以如下所示：

```
(define (intersection-set set1 set2)
  (if (or (null? set1) (null? set2))
      '()    
      (let ((x1 (car set1)) (x2 (car set2)))
        (cond ((= x1 x2)
               (cons x1
                     (intersection-set (cdr set1)
                                       (cdr set2))))
              ((< x1 x2)
               (intersection-set (cdr set1) set2))
              ((< x2 x1)
               (intersection-set set1 (cdr set2))))))) 
```

**检验你的理解**

假设`set1`和`set2`是有序列表，且长度都为 n。

下面的函数调用的运行时间是多少？

```
(intersection-set set1 set2) 
```

## 作为二叉树的集合

*"我想要更快"*

在追求速度的过程中，我们必须摆脱将我们与线性联系在一起的列表的束缚。换句话说，如果我们希望我们的集合 ADT 工作得更快，我们将不得不使用与列表不同的数据结构。使用树如何？

一个**二叉树**就像我们在本课前面描述的树一样，除了一个重要的属性：二叉树的每个节点最多可以有**两个**分支。

使用二叉树表示集合是简单直观的。二叉树中每个节点的**入口**（类似于**数据**）将是集合的一个元素。每个节点还将有一个**左分支**和一个**右分支**；节点的左分支或右分支可以为空。如果两个分支都为空，那么该节点是一个**叶子**。这种数据结构必须遵循一个规则：节点的左分支必须指向具有比节点入口更小的条目的子树。右分支必须指向具有比节点入口更大的条目的子树。换句话说，**节点左侧的所有值必须小于节点，节点右侧的所有值必须大于节点**。

![](img/9011163110fabcf44a2ce30ec582cfc6.jpg)

这个规则引入了对数运行时间的概念。自己尝试在上面最左侧的树中找到`11`。我们从树的根开始，注意到`11`大于`7`，所以我们沿着右分支向下移动。`11`大于`9`，所以我们再次沿着右分支向下移动。我们在树中找到了`11`，可以返回`#t`。

好的，现在让我们尝试证明这种对数运行时间。如果你不想看整个证明，可以直接跳到**TL;DR**部分。

看看下面的最坏情况树：

![](img/c803bb571db02fa03909d4a5dabe4a0e.jpg)

+   你将不得不探索的节点的最大数量，永远等于树的**深度**，或者树有多少层。 （根的深度为 1。）花点时间确认一下。

+   我们已知集合的大小为`n`，因此树中有`n`个节点。

+   在深度 1 处，有 1 个`(2¹ - 1)`节点。在深度 2 处，有 3 个`(2² - 1)`总节点。在深度 3 处，有 7 个`(2³ - 1)`总节点，...最后，在深度`d`处，有`(2^d - 1)`总节点。

我们在第 3 课中学到，在渐近分析中，我们可以忽略常数，所以让我们说在深度`d`处，树中有`2^d`个节点。这意味着任何深度为`d`的树将在树中有`2^d`个节点。

我们知道树中总共有`n`个节点。这意味着`2^d = n`。

经过一些很酷的代数魔术，我们得到`d = log(n)`。

记得我们说过我们将探索的节点的最大数量等于树的深度吗？这意味着在二叉树中查找节点的运行时间是Θ(d) = Θ(logn)。因此，我们证明了使用二叉树表示集合的对数运行时间。哦！

**总结：** 二叉树结构的排序允许我们在每次比较后忽略一半的树。这意味着我们需要探索的节点数最多等于树的**深度**。这导致我们的运行时间为 Θ(log n)。例如，在具有 8 个节点的树中，我们最多只需要 3 次比较，直到达到任何叶子节点。在具有 16 个节点的树中（是前一个的两倍），我们只需要 4 次比较（只多了 1 次比较！）直到达到任何叶子节点。

## 实现二叉树

一种实现二叉树的方法是使用一个列表，其中第一项是元素，第二项是左子树，第三项是右子树。

```
(define (entry tree) (car tree))
(define (left-branch tree) (cadr tree))
(define (right-branch tree) (caddr tree))
(define (make-tree entry left right)
  (list entry left right)) 
```

## `element-of-set?`

我们可以通过以下代码形式化我们的算法，以查找集合中是否存在元素：

```
(define (element-of-set? x set)
  (cond ((null? set) false)
        ((= x (entry set)) true)
        ((< x (entry set))
         (element-of-set? x (left-branch set)))
        ((> x (entry set))
         (element-of-set? x (right-branch set))))) 
```

超级简单的东西。

## `adjoin-set`

如何向二叉树添加元素？由于你需要决定将 x 添加到左子树的叶子还是右子树的叶子，让我们遵循上面的相同算法 `element-of-set?`。

+   如果树为空，则创建一个具有节点条目 `x` 和空左右分支的树。

+   如果 x 等于树的节点，则返回树。（这意味着 `x` 已经在树中，不需要进行任何更改。）

+   如果 x 小于树的节点，则进入左子树。

+   如果 x 大于树的节点，则进入右子树。

这是 `adjoin-set` 的正式算法：

```
(define (adjoin-set x set)
  (cond ((null? set) (make-tree x '() '()))
        ((= x (entry set)) set)
        ((< x (entry set))
         (make-tree (entry set) 
                    (adjoin-set x (left-branch set))
                    (right-branch set)))
        ((> x (entry set))
         (make-tree (entry set)
                    (left-branch set)
                    (adjoin-set x (right-branch set)))))) 
```

## 不平衡树

![](img/0be82a024daf6d0654f81ce7605fbfc0.jpg)

上面的图像是将元素 1、2、3、4、5、6 和 7 按顺序添加到空树的结果。（确保你用纸和笔尝试一下，看看是否是这样）。我们说这棵树是**不平衡**的，因为树的一侧有比另一侧更多的元素。

**测试你的理解**

在上面的不平衡树中，查找一个元素（例如，7）的运行时间是多少？n 是树中的节点数，其中 n = 7。

**挑战：** 你能想到一种顺序添加相同数字的方法，以创建一个平衡的树吗？

## 不同类型的树

之前，我们看到树中的节点可以有任意数量的子节点。这些类型的树有时被称为**N 路树**。对于 N 路树，我们将树的子节点存储为一个森林，或者一组树。我们通过选择器 `(children <tree>)` 检索这个森林。

在前一节中，我们看到了一种更具体的树类型，即二叉树。这棵树中的每个节点最多有 2 个子节点。它们可以通过 `(left-branch <tree>)` 和 `(right-branch <tree>)` 访问。二叉树的构造器也与 N 路树的构造器不同。

当你在处理树时，要弄清楚你正在处理的是什么类型的树，并注意问题提供的构造器和选择器。二叉树的构造器和选择器在 N 路树上根本不起作用！

## 要点

集合是一种特定的数据结构，其中每个元素只出现一次。有多种表示集合的方式（就像基本上所有数据结构一样）。表示的选择会影响不同函数的运行时间。
