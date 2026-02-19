# 堆

*最小堆*是满足最小堆属性的完全二叉树，该属性要求每个节点都不大于其子节点。（*最大堆*类似地被定义）。

堆抽象被定义为任何有序的元素类型。但为了简单起见，我们将专门处理`Int`堆，由类型`Heap`描述；我们将在下面讨论更一般的、多态的堆类型。以下类型签名定义了我们的`Heap`接口：

```
empty     : Heap
isEmpty   : Heap -> Bool
findMin   : Heap -> Maybe Int
insert    : Int -> Heap -> Heap
deleteMin : Heap -> Maybe Heap
merge     : Heap -> Heap -> Heap 
```

#### 数组作为堆

堆通常被实现为数组。回顾一下（来自第二次作业）使用广度优先搜索对节点进行排序的方案：

```
 Level 1              0

    Level 2        1           2

    Level 3     3     4     5     6

               . .   . .   . .   . . 
```

完全二叉树的节点可以以广度优先顺序存储在数组`a`中...

```
 i:     0   1   2   3   4   5   6   ...
           ----------------------------------
   a[i]:   | 0 | 1 | 2 | 3 | 4 | 5 | 7 | ...
           ---------------------------------- 
```

然后导航存储在`a[i]`中的节点的父节点和子节点边很容易：

+   父节点存储在`a[(i-1)//2]`，

+   左子节点（如果存在）存储在`a[(2*i)+1]`中，

+   右子节点（如果存在）存储在`a[(2*i)+2]`中。

在命令式语言中，检索数组中的任意元素需要*O(1)*时间。在函数式语言中，纯函数数组通常是基于平衡搜索树实现的，这些树通常提供对任意元素的*O(log n)*访问。

虽然我们还没有讨论如何实现平衡搜索树，但我们将给出平衡搜索树的实现。在 Elm 中，[`Array`](http://package.elm-lang.org/packages/elm-lang/core/1.0.0/Array)库是使用一种称为[宽松基数树](http://infoscience.epfl.ch/record/169879/files/RMTrees.pdf)的数据结构实现的，它在实践中提供了接近常数时间的性能，用于获取和设置任意索引。

#### 内部表示 vs. 外部接口

我们将利用`Array`库（我们将使用`A`修饰）来实现堆抽象。如果我们选择定义和导出

```
type alias Heap = A.Array Int 
```

那么我们模块的客户端将能够看到我们使用数组实现了`Heap`，并且将可以访问我们用来表示`Heap`的`Array`值。如果我们希望将表示隐藏在客户端，我们可以定义一个*新*类型

```
type Heap = WrapHeap (A.Array Int) 
```

并且仅导出我们希望客户端使用的那些函数：

```
module Heaps
  (Heap, empty, isEmpty, findMin, insert, deleteMin, merge) where
  ... 
```

因为这些 API 函数中没有一个“暴露”`Heap`类型的底层表示给客户端（没有类型为`Heap -> A.Array Int`的函数），客户端将无法直接使用`Array`操作符操纵`Heap`。

创建这样的抽象边界有助于软件工程过程，防止客户端（有意或无意地）违反模块实现的不变性，以及通过限制和明确模块之间的边界来促进实现的变更。

为了实现`Heap`抽象，我们将使用以下`Array`操作符：

```
A.empty  : Array a
A.length : Array a -> Int
A.push   : a -> Array a -> Array a
A.get    : Int -> Array a -> Maybe a
A.set    : Int -> a -> Array a -> Array a
A.slice  : Int -> Int -> Array a -> Array a 
```

`A.push`函数创建一个新数组，该数组与输入数组相同，只是在末尾包含一个附加元素。 为了方便起见，我们将定义一个名为`pop`的类似函数，该函数创建一个删除了最后一个元素的新数组。

```
pop : A.Array a -> A.Array a
pop a = A.slice 0 (A.length a - 1) a 
```

我们将从简单的运算符开始。

```
empty : Heap
empty = WrapHeap A.empty

isEmpty : Heap -> Bool
isEmpty (WrapHeap a) = A.length a == 0 
```

请注意，`isEmpty`的定义使用模式匹配来同时解构参数值并将底层数组值绑定到变量`a`。 这个定义等效于以下所有情况：

```
isEmpty h = case h of {WrapHeap a -> A.length a == 0}

isEmpty = \h -> case h of {WrapHeap a -> A.length a == 0}

isEmpty = \h -> let (WrapHeap a) = h in A.length a == 0

isEmpty = \(WrapHeap a) -> A.length a == 0 
```

因为`Heap`类型的值只能由`WrapHeap`数据构造函数构造，所以我们可以在绑定中使用模式（而不是`case`表达式），并确保不会有运行时模式匹配错误。

`findMin`的实现也很简单。

```
findMin : Heap -> Maybe Int
findMin (WrapHeap a) = A.get 0 a 
```

#### 插入

现在让我们来看看第一个非平凡运算符，将`Int`插入`Heap`。 思想是将元素添加到完全二叉树中的下一个位置（方便地表示为数组中的最后一个元素），然后将元素"冒泡"或"渗透"到树中，直到它不再比其父节点大。

```
insert : Int -> Heap -> Heap
insert x (WrapHeap a) =
  let n  = A.length a
      a' = A.push x a in
    Heap (bubbleUp n a') 
```

当我们操作底层的`Array`表示时，我们将确保始终在界限内访问元素。 因此，我们定义了`get`的"不安全"版本：

```
fromJust : Maybe a -> a
fromJust mx = case mx of Just x -> x

justGet : Int -> A.Array a -> a
justGet i a = fromJust (A.get i a) 
```

我们还定义了一个辅助函数，用于交换`Array`中的两个元素：

```
swap : Int -> Int -> A.Array a -> A.Array a
swap i j a =
  a |> A.set i (justGet j a) |> A.set j (justGet i a) 
```

`bubbleUp`函数被定义为如果父节点较大则交换节点`i`与其父节点`(i-1)//2`，如果是，则递归地遍历树。 在我们的实现中，我们使用类型别名`InternalHeap`来引用`A.Array Int`。

```
bubbleUp : Int -> InternalHeap -> InternalHeap
bubbleUp i a = if
  | i == 0 -> a
  | otherwise ->
      let j   = (i-1) // 2
          ch  = justGet i a
          par = justGet j a in
      if par <= ch
      then a
      else a |> swap i j |> bubbleUp j 
```

现在让我们考虑插入算法的最坏情况时间成本。 `insert`函数计算`Array`表示的长度（通过查看文档和实现运行在*O(1)*时间内），在其末尾`push`一个元素（在最坏情况下运行在*O(log n)*时间内）并调用`bubbleUp`。

`bubbleUp`函数利用`justGet`和`swap`。 因为`A.get`在*O(log n)*时间内运行，所以包装函数`justGet`也是如此。 `swap`函数调用了多次`A.set`和`justGet`，每次调用需要*O(log n)*时间。 因此，`swap`需要*O(log n)*时间。 `bubbleUp`函数最多访问*O(log n)*个元素，因为索引`i`在每次递归调用之前都会减半。 因此，有*O(log n)*次对`bubbleUp`的调用，每次调用执行*O(log n)*工作。 因此，`bubbleUp`的运行时间，因此`insert`的运行时间是*O(log²n)*。 在命令式语言中，其中数组操作最坏情况下需要*O(1)*时间，插入算法的最坏情况下运行时间为*O(log n)*。

#### 删除

**更新**：[这里](https://www.classes.cs.uchicago.edu/archive/2015/winter/22300-1/lectures/HeapsBuggy.html)的`deleteMin`版本是错误的。 你能看出为什么吗？

要删除存储在索引 `0` 处的最小元素，我们首先用当前存储在最后位置的值（方便地存储在 `Array` 的最后一个元素中）覆盖根。我们弹出最后一个元素，因为它的值现在存储在根中，然后根据需要“冒泡”或“渗透”这个值。在递归冒泡时，我们选择根较小的子树，以保持堆顺序属性。

```
deleteMin : Heap -> Maybe Heap
deleteMin (WrapHeap a) =
  let n = A.length a in if
    | n == 0    -> Nothing
    | otherwise -> let x = justGet (n-1) a in
                     a |> pop
                       |> A.set 0 x
                       |> bubbleDown 0
                       |> WrapHeap
                       |> Just 
```

对于给定的索引 `i`，左子节点的索引是 `j = 2*i + 1`，右子节点的索引是 `k = 2*i + 2`。如果索引 `i` 处的值小于两个子节点，则输出数组不变。否则，索引 `i` 处的值与两个子树中较小的根交换，并且 `bubbleDown` 在该子树上递归。

```
bubbleDown : Int -> InternalHeap -> InternalHeap
bubbleDown i a =
  let n = A.length a in
  if | i >= n -> a
     | otherwise ->
         let (j, k) = (2*i + 1, 2*i + 2) in
         let i'  = if j < n && justGet j a < justGet i  a then j else i  in
         let i'' = if k < n && justGet k a < justGet i' a then k else i' in
         if | i == i''  -> a
            | otherwise -> a |> swap i i'' |> bubbleDown i'' 
```

对 `bubbleDown` 和 `deleteMin` 的分析类似于插入算法，导致最坏情况下的 *O(log²n)* 时间成本。

#### 合并

有一个通用的算法，通常称为“堆化”，用于合并表示为数组的堆。我们不会在本课程中介绍这个算法，但如果您以前没有见过它，您可能会对它感兴趣。

在我们的 Elm 实现中，我们将假装我们忠实地实现了 `merge` 函数，但实际上我们总是触发运行时错误。

```
merge _ _ = if
  | False -> empty 
```

[`Heaps.elm`](https://www.classes.cs.uchicago.edu/archive/2015/winter/22300-1/public-code/Heaps.elm) 文件包含上述实现。

## 用于堆的多态类型

我们定义了 `Heap` 类型来存储 `Int`，但相同的抽象存在于任何可比较值类型。当然，我们不想为我们可能想要使用的每种不同类型的堆重复实现。

Elm 提供了特殊的多态类型变量 `comparable` 来描述这样的类型。因此我们可以将堆的抽象概括如下。

```
type Heap comparable = WrapHeap (A.Array comparable)

empty     : Heap comparable
isEmpty   : Heap comparable -> Bool
findMin   : Heap comparable -> Maybe comparable
insert    : comparable -> Heap comparable -> Heap comparable
deleteMin : Heap comparable -> Maybe (Heap comparable)
merge     : Heap comparable -> Heap comparable -> Heap comparable 
```

[`PolyHeaps.elm`](https://www.classes.cs.uchicago.edu/archive/2015/winter/22300-1/public-code/PolyHeaps.elm) 文件包含了实现此更通用接口所需的修改。值得注意的是，与 [`Heaps.elm`](https://www.classes.cs.uchicago.edu/archive/2015/winter/22300-1/public-code/Heaps.elm) 相比，类型签名已更改，但值定义未更改。

#### Haskell 风格类型类

我们可能希望根据除 `comparable` “类型类” 中指定的操作符之外的类型定义接口。但是 Elm 不提供一种方式让程序员定义描述一组类型的接口。

在 Haskell 中，用户定义的类型类可以用以下方式来指定堆抽象。

```
class Ord a where
  (<)  :: a -> a -> Bool
  (>=) :: a -> a -> Bool
  (>)  :: a -> a -> Bool
  (<=) :: a -> a -> Bool
  max  :: a -> a -> a
  min  :: a -> a -> a

class Ord a => Heap a where
  empty     : Heap a
  isEmpty   : Heap a -> Bool
  findMin   : Heap a -> Maybe a
  insert    : a -> Heap a -> Heap a
  deleteMin : Heap a -> Maybe (Heap a)
  merge     : Heap a -> Heap a -> Heap a 
```

第二个类定义说明类型 `a` “是一个” `Heap` 如果 (1) `a` “是一个” `Ord` 并且 (2) 可以为该类型定义六个指定的函数。然后，具体的实现被定义为“实现” `Heap` “接口”。

```
type MyHeap a = WrapHeap (Array a)

instance Heap (MyHeap a) where
  insert = ...
  ... 
```

为了简单起见，上述定义没有提及 Haskell 的 `Eq` 类型类。

#### ML 风格模块

在 Standard ML 和 OCaml 中，*签名* 用来描述 *模块*，这些模块是包含值和类型的结构。

```
signature ORDERED =
sig
  type T

  val eq  : T -> T -> bool
  val lt  : T -> T -> bool
  val leq : T -> T -> bool
end

signature HEAP =
sig
  structure Elem : ORDERED

  type H

  val empty     : H
  val isEmpty   : H -> bool
  val insert    : Elem.T -> H -> H
  val merge     : H -> H -> H
  val findMin   : H -> Elem.t option
  val deleteMin : H -> H option
end 
```

通过定义一个以模块为参数并返回另一个模块的 *函数* 来满足 `Heap` 签名的实现。请注意，这些 ML 函数子与 Haskell 的 `Functor` 不是同一概念。

```
functor MyHeap (Element : ORDERED) : HEAP =
struct
  structure Elem = Element

  datatype H = ...

  fun insert = ...
  ...
end 
```
