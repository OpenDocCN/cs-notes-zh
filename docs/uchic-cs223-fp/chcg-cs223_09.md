# 左偏堆

#### 表示

为简单起见，我们将继续使用`Int`堆。节点`T r i a b`包含其等级`r`，即其最右脊柱的长度。

```
type alias Rank = Int

type Heap = E | T Rank Int Heap Heap 
```

左偏堆的辅助函数：

```
rank h  = case h of { E -> 0      ; T r _ _ _ -> r                   }

value h = case h of { E -> maxInt ; T _ i _ _ -> i                   }

left h  = case h of { E -> E      ; T _ _ a _ -> a                   }

right h = case h of { E -> E      ; T _ _ _ b -> b                   }

size h  = case h of { E -> 0      ; T _ _ a b -> 1 + size a + size b } 
```

#### 不变性

+   *∀`h`. (`value(h)` ≤ `value(left(h))`) ∧ (`value(h)` ≤ `value(right(h))`)*

+   *∀`h`. `rank(left(h))` ≥ `rank(right(h))`*

**课堂练习**

```
log = logBase 2 
```

+   证明：*∀`h`. `rank(h)` = `r` ⇒ `size(h)` ≥ `2^r - 1`*

+   证明：*∀`h`. `size(h)` = `n` ⇒ `rank(h)` ≤ `log(floor(n+1)))`*

因此，大小为`n`的左偏堆`h`的右脊柱具有*O(`log n`)*个元素。

#### 合并

与常规最小堆不同，左偏堆的合并速度很快（快于*O(n)*），因为利用了右脊柱短小（*O(log n)*）的事实。

辅助函数`makeT`创建一个存储`x`并根据其等级将`h1`和`h2`定位为其子节点的`T`节点。

```
makeT : Int -> Heap -> Heap -> Heap
makeT x h1 h2 =
let (r1,r2) = (rank h1, rank h2) in if
  | r1 >= r2  -> T (1+r2) x h1 h2
  | otherwise -> T (1+r1) x h2 h1 
```

以下是`makeT`的等效定义。

```
makeT x h1 h2 =
  let (l,r) = if | rank h1 >= rank h2 -> (h1, h2)
                 | otherwise          -> (h2, h1) in
  T (1 + rank r) x l r 
```

`merge`函数通过选择两个最小值中较小的一个并递归合并来组合两个非空堆，使用`makeT`将“更重”的子树放在左侧。

```
merge : Heap -> Heap -> Heap
merge h1 h2 = case (h1, h2) of
  (_, E) -> h1
  (E, _) -> h2 
  (T _ x1 l1 r1, T _ x2 l2 r2) ->
    if | x1 <= x2  -> makeT x1 l1 (merge r1 h2)
       | otherwise -> makeT x2 l2 (merge h1 r2) 
```

`makeT`函数在*O(1)*时间内运行。`merge`的运行时间由其递归调用主导。设* n *为两个堆中较大堆的大小。左偏性质确保每个堆的右脊柱具有*O(log n)*个元素。因为递归调用遍历其中一个输入堆的右脊柱，所以最多有*O(log n)*个递归调用，每个调用执行*O(1)*的工作。因此，`merge`在*O(log n)*时间内运行。

#### 接口的其余部分

```
empty       = E
singleton x = T 1 x E E 
```

插入和删除可以根据`merge`来定义，因此每个操作都在*O(log n)*时间内运行。

```
insert : Int -> Heap -> Heap
insert x h = merge (singleton x) h

deleteMin : Heap -> Maybe Heap
deleteMin h = case h of
  E         -> Nothing
  T r _ a b -> Just (merge a b) 
```

实现堆抽象的其余部分是直接的。

```
findMin : Heap -> Maybe Int
findMin h = case h of
  E         -> Nothing
  T _ i _ _ -> Just i

isEmpty : Heap -> Bool
isEmpty h = h == empty 
```

我们的实现（[`LeftistHeaps.elm`](https://www.classes.cs.uchicago.edu/archive/2015/winter/22300-1/public-code/LeftistHeaps.elm)）导出与以前的最小堆基本相同的类型签名。

```
module LeftistHeaps
  (Heap, empty, isEmpty, findMin, insert, deleteMin, merge) where
  ... 
```

注意`insert`序列如何将元素大量堆积到左侧。

```
> import LeftistHeaps (..)
> insert 1 <| insert 2 <| insert 3 <| empty
T 1 1 (T 1 2 (T 1 3 E E) E) E : LeftistHeaps.Heap 
```

## 阅读

#### 必需

+   Okasaki，第 3.1 章
