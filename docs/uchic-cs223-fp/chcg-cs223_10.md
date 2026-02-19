# 二项堆

为简单起见，我们将继续使用`Int`堆。我们的实现（[`BinomialHeaps.elm`](https://www.classes.cs.uchicago.edu/archive/2015/winter/22300-1/public-code/BinomialHeaps.elm)）导出与先前最小堆实现相同的类型签名。

#### 二项树：表示和不变性

```
type alias Rank = Int
type Tree = Node Rank Int (List Tree)

rank (Node r _ _) = r
root (Node _ x _) = x 
```

秩为`r`的*二项树*的定义如下。

+   `Node 0 n []`是秩为`0`的二项树。

+   如果`ts`是具有秩`r-1`到`0`的`r`个二项树的列表，则`Node r n ts`是秩为`r > 0`的二项树。

秩为`r`的二项树有*2^(`r`)*个节点。

#### 链接

秩为`r + 1`的二项树是通过将两个秩为`r`的树链接在一起形成的，使其中一个成为另一个的最左子节点。

下面的`link`函数链接两个二项树，选择保留两个元素中较小的一个作为根。因此，如果`t1`和`t2`都是堆有序的，则结果也是堆有序的。

```
link : Tree -> Tree -> Tree
link t1 t2 =
  let (Node r x1 c1) = t1
      (Node _ x2 c2) = t2
  in
    if | x1 <= x2  -> Node (1+r) x1 (t2::c1)
       | otherwise -> Node (1+r) x2 (t1::c2) 
```

#### 二项堆：表示和不变性

```
type alias InternalHeap = List Tree
type Heap = WrapHeap InternalHeap 
```

*二项堆*是一组堆有序的二项树列表，严格按秩严格递增的顺序排列。包含*n*个元素的二项堆使用最多*O(log n)*个二项树表示，类似于*n*的二进制表示。

#### 堆接口

```
empty : Heap
empty = WrapHeap []

isEmpty : Heap -> Bool
isEmpty h = h == empty 
```

`findMin`函数在所有二项树中搜索最小的根，时间复杂度为*O(log n)*。

```
findMin : Heap -> Maybe Int
findMin (WrapHeap ts) = case ts of
  [] -> Nothing
  _  -> ts |> List.map root |> List.foldl1 min |> Just 
```

请参考作业 3，了解如何实现`findMin`，使其在*O(1)*时间内运行，就像其他堆实现一样。

#### 插入

将元素插入二项堆需要对具有相同秩的树进行成对`链接`。可以将其类比为算术加法中的“和”和“进位”位。这类似于算术加法。

```
insertTree : Tree -> InternalHeap -> InternalHeap
insertTree t ts = case ts of
  []      -> [t]
  t'::ts' -> if
    | rank t == rank t' -> insertTree (link t t') ts'
    | rank t <  rank t' -> t :: ts

insert : Int -> Heap -> Heap
insert x (WrapHeap ts) = WrapHeap (insertTree (Node 0 x []) ts) 
```

对`insertTree`有*O(m)*次递归调用（其中*m*是`ts`的长度），每次执行*O(1)*的工作（链接两个树）。因此，`insert`的运行时间为*O(m) = O(log n)*。

#### 合并

```
merge_ : InternalHeap -> InternalHeap -> InternalHeap
merge_ ts1 ts2 = case (ts1, ts2) of
  ([], _) -> ts2
  (_, []) -> ts1
  (t1::ts1', t2::ts2') ->
    if | rank t1 < rank t2 -> t1 :: merge_ ts1' ts2
       | rank t2 < rank t1 -> t2 :: merge_ ts2' ts1
       | otherwise         -> insertTree (link t1 t2) (merge_ ts1' ts2')

merge : Heap -> Heap -> Heap
merge (WrapHeap ts1) (WrapHeap ts2) = WrapHeap (merge_ ts1 ts2) 
```

要分析`merge_`的运行时间，设*m*为`ts1`和`ts2`中树的总数。前两种情况的运行时间为*O(1)*。每次对`merge_`的递归调用会使*m*减少一次（在第三和第四种情况下）或两次（在第五种情况下）。第三和第四种情况中的 cons 操作需要*O(1)*的工作。在第五种情况中，`link`需要*O(1)*的时间，`insertTree`需要*O(m)*的时间，对`merge_`的递归调用需要*T(m-2)*的时间。共有*O(m)*次递归调用，每次最多需要*O(m)*的时间。结果是*O(m²)*的运行时间，即*O(log²(n))*，其中*n*是要合并的两个堆中描述的元素的总数。

然而，可以使用更微妙的分析来证明`merge_`的实现在*O(log n)*时间内运行。这个论点需要更仔细地计算`link`被调用的次数（这是`insertTree`和`merge_`的关键所在），基于合并列表和以二进制表示形式添加两个数字之间的类比。

对于我们的目的，我们将考虑一个替代的、一次性的定义（也来自[这篇文章](http://stackoverflow.com/questions/11462626/should-melding-merging-of-binomial-heaps-be-done-in-one-pass-or-two)），这样分析起来稍微容易一些。

```
merge' : InternalHeap -> InternalHeap -> InternalHeap
merge' ts1 ts2 = case (ts1, ts2) of
  ([], _) -> ts2
  (_, []) -> ts1
  (t1::ts1', t2::ts2') ->
    if | rank t1 < rank t2 -> t1 :: merge' ts1' ts2
       | rank t2 < rank t1 -> t2 :: merge' ts2' ts2
       | otherwise         -> merge_wc (link t1 t2) ts1' ts2'

merge_wc : Tree -> InternalHeap -> InternalHeap -> InternalHeap
merge_wc t ts1 ts2 = case (ts1, ts2) of
  ([], _) -> insertTree t ts2
  (_, []) -> insertTree t ts1
  (t1::ts1', t2::ts2') ->
    let (r,r1,r2) = (rank t, rank t1, rank t2) in
    if | r <  r1 && r <  r2 -> t :: merge' ts1 ts2
       | r <  r1 && r == r2 -> merge_wc (link t t2) ts1 ts2'
       | r == r1 && r <  r2 -> merge_wc (link t t1) ts1' ts2
       | r == r1 && r == r2 -> merge_wc (link t t1) ts1' ts2 
```

让*T(m)*和*S(m)*分别表示`merge'`和`merge_wc`的运行时间，其中*m*是两个输入列表中树的数量的上限。考虑`merge'`的五种情况：

+   情况 1 和 2：*T(m)* = *O(1)*

+   情况 3 和 4：*T(m)* = *O(1)* + *T(m-1)*

+   情况 5：*T(m)* = *O(1)* + *S(m-2)*

考虑`merge_wc`的六种情况：

+   情况 1 和 2：*S(m)* = *O(m)*

+   情况 3：*S(m)* = *O(1)* + *T(m)*

+   情况 4、5 和 6：*S(m)* = *O(1)* + *S(m-1)*

在这两个函数之间最多有*O(m)*次互相递归调用。对`merge_wc`的最后一次调用可能需要*O(m)*时间，但所有其他调用都只需要*O(1)*时间。因此，这两个函数的最坏情况运行时间分别为*O(m)+O(m) = O(m)*时间。也就是说，*O(log n)*时间。

#### 删除

```
removeMinTree : InternalHeap -> (Tree, InternalHeap)
removeMinTree ts = case ts of
  [t]    -> (t, [])
  t::ts' ->
    let (t',ts'') = removeMinTree ts' in
    if | root t < root t' -> (t, ts')
       | otherwise        -> (t', t::ts'')

deleteMin : Heap -> Maybe Heap
deleteMin (WrapHeap ts) = case ts of
  [] -> Nothing
  _  -> let (Node _ x ts1, ts2) = removeMinTree ts in
        Just <| WrapHeap <| merge_ (List.reverse ts1) ts2 
```

#### 寻找（重新审视）

我们可以重用`removeMinTree`辅助函数来重新实现`findMin`。

```
findMin : Heap -> Maybe Int
findMin (WrapHeap ts) = case ts of
  [] -> Nothing
  _  -> ts |> removeMinTree |> fst |> root |> Just 
```

## 阅读

#### 必需的

+   Okasaki，第 3.2 章
