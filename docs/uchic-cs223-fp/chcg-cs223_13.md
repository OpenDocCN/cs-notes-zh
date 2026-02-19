# 红黑树

红黑树是大致平衡的二叉搜索有序树，导致*O(log n)*的成员、插入和删除操作。本讲座的代码可以在[`RedBlackTrees.elm`](https://www.classes.cs.uchicago.edu/archive/2015/winter/22300-1/public-code/RedBlackTrees.elm)中找到。

红黑树中的所有节点都被彩色为红色或黑色。空节点被视为黑色。

```
type Color = R | B
type Tree  = E | T Color Tree Int Tree

color t = case t of {T c _ _ _ -> c; E -> B} 
```

#### 不变式

如果一棵树`t`是有效的红黑树，则：

+   `t`满足二叉搜索顺序属性。也就是说，`bso t == True`，其中

    ```
    bso t = case t of
      E         -> True
      T _ l x r -> (l == E || root l < x) &&
                   (r == E || x < root r) &&
                   bso l && bso r

    root t = case t of {T _ _ x _ -> x} 
    ```

+   树`t`的根节点是黑色的。也就是说，`color t == B`。

+   `t`中没有红节点有一个红子。也就是说，`noRedRed t == True`，其中

    ```
    noRedRed t = case t of
      E                   -> True
      T R (T R _ _ _) _ _ -> False
      T R _ _ (T R _ _ _) -> False
      T _ l _ r           -> List.all noRedRed [l, r] 
    ```

+   从`t`的根到叶的每条路径都包含相同数量的黑节点。也就是说，`okBlack t == True`，其中

    ```
    okBlack t = case blackHeight t of {Just _ -> True; _ -> False}

    blackHeight t = case t of
      E -> Just 0
      T c l _ r ->
        let i = case c of {B -> 1; R -> 0} in
        case (blackHeight l, blackHeight r) of
          (Just n, Just m) -> if
            | n == m    -> Just (i + n)
            | otherwise -> Nothing
          _ -> Nothing 
    ```

    当`blackHeight t == Just n`时，我们将`n`称为`t`的*黑高度*。

    ```
    bh = fromJust << blackHeight

    fromJust mx = case mx of Just x -> x 
    ```

    请注意，路径长度中不包括`E`节点。

总结不变式：

```
rb t = bso t && color t == B && noRedRed t && okBlack t 
```

#### 属性

`noRedRed`不变式的一个结果是，在红黑树`t`中从根到叶的最长路径的长度最多是最短路径的两倍。因此，`height t <= 2 * bh t`，其中

```
height t = case t of
  E         -> 0
  T _ l _ r -> 1 + max (height l) (height r)

size t = case t of
  E         -> 0
  T _ l _ r -> 1 + size l + size r 
```

**课堂练习**

+   证明：*∀`t`. `rb t` ⇒ `size t` ≥ `2^(bh t) - 1`*

+   证明：*∀`t`. `rb t` ⇒ `height t` ≤ `2(log(1 + size t))`*

因此，大小为`n`的红黑树`t`的高度为*O(`log n`)*。

## 成员资格

在红黑树中查找元素的过程就像在不平衡的二叉搜索树中查找元素一样（*参见* [`findBST`](https://www.classes.cs.uchicago.edu/archive/2015/winter/22300-1/lectures/AsymptoticAnalysis.html)）。

```
member : Int -> Tree -> Bool
member x t = case t of
  E -> False
  T _ l y r -> if
    | x == y    -> True
    | x <  y    -> member x l
    | otherwise -> member x r 
```

## 插入

当不考虑维护二叉搜索树的平衡性时，插入过程沿着树中的路径向下走，根据顺序属性进行左右转向。然后，如果在树中找不到元素，则将其添加为叶子。

这种天真的方法可以简单地在最终位置添加一个黑节点，满足`noRedRed`不变式，但不幸的是，它不能保持`blackHeight`属性。

相反，插入算法的思想是将新节点标记为红色，可能导致临时的红-红违规，然后沿着搜索路径向上走，修复并向上传播任何违规。算法保持的不变式是一次只允许一个红-红违规。

`ins`函数沿着搜索路径向下走，将一个红节点插入为新的叶子，然后沿着搜索路径向上走，调用`balance`来修复任何临时的红-红违规。

```
ins : Int -> Tree -> Tree
ins x t =
  case t of
    E -> T R E x E
    T c l y r -> if
      | x == y    -> t
      | x <  y    -> balance c (ins x l) y r
      | otherwise -> balance c l y (ins x r) 
```

`balance`函数查找红-红违规，这可以出现四种配置之一。在每种情况下，解决方案都是相同的。

```
balance : Color -> Tree -> Int -> Tree -> Tree
balance c l val r =
  case (c, l, val, r) of
    (B, T R (T R a x b) y c, z, d) -> T R (T B a x b) y (T B c z d)
    (B, T R a x (T R b y c), z, d) -> T R (T B a x b) y (T B c z d)
    (B, a, x, T R (T R b y c) z d) -> T R (T B a x b) y (T B c z d)
    (B, a, x, T R b y (T R c z d)) -> T R (T B a x b) y (T B c z d)
    _                              -> T c l val r 
```

当处理包含它的黑色父节点时，`balance`函数修复红红违例。如果`ins`将红红违例传播到根部，就没有调用`balance`来修复它。因此，插入算法的最后一步是无条件地将新的根节点着色为黑色。

```
insert : Int -> Tree -> Tree
insert x t =
  let (T _ l y r) = ins x t in
    T B l y r 
```

#### 合同

尽管在纸上证明伪代码的属性非常好，但动态检查函数的输入和输出行为是否符合预期通常也很有用。

其中一种测试风格被称为*设计合同*，其中一个函数可以装饰为描述调用方应满足的参数前置条件和被调用方应建立的返回值后置条件的谓词（`Bool`值函数）。

例如，该函数

```
\x -> e 
```

可能期望`x`满足某些谓词`pArg`并且可能打算`e`满足某些谓词`pRet`。如果其中任何期望在运行时被违反，则应报告错误（最理想情况下，可以帮助确定程序哪个部分负责失败）。

下面是重新编写上述函数的一种方法，其中包含了前置条件和后置条件。请注意，这个函数是对原始函数的“包装器”。

```
\x ->
  let _ =
    if | pArg x    -> ()
       | otherwise -> Debug.crash "..." in
  let ret = e in
    if | pRet ret  -> ret
       | otherwise -> Debug.crash "..." 
```

插入算法有点棘手，所以让我们定义带有合同的包装器版本，以获得对实现与我们在纸上进行的分析相符的更多信心。

我们首先定义一些辅助函数。

```
check s p x =
  if | p x       -> x
     | otherwise -> Debug.crash (s ++ "\n" ++ toString x)

checkArg s = check ("ARG CONTRACT ERROR: " ++ s)
checkRet s = check ("RET CONTRACT ERROR: " ++ s) 
```

现在，我们将定义前面函数的版本（标记为`'`），每次调用时都执行合同检查。在实践中，我们可能希望包含更多描述性错误字符串以报告失败情况。

整体`insert'`算法期望其参数满足`rb`并返回满足`rb`的更新树。

```
insert' x t_ =
  let t = checkArg "[insert']" rb t_ in
  let ret =
    let (T _ l y r) = ins' x t in
       T B l y r
  in
  checkRet "[insert']" rb ret 
```

`ins'`的前置条件很有趣，因为其参数应满足除了根的颜色可能为红色之外的所有红黑树不变量。结果树的`blackHeight`与原始树相同，可能存在一个红红违例。我们将从`ins'`（以及下面的`balance'`）中省略`bso`后置条件，以节省一些运行时开销。

```
ins' x t_ =
  let t = checkArg "[ins']" rbExceptRoot t_ in
  let ret =
    case t of
      E -> T R E x E
      T c l y r -> if
        | x == y    -> t
        | x <  y    -> balance' c (ins' x l) y r
        | otherwise -> balance' c l y (ins' x r)
  in
  checkRet "[ins']" (\t' -> bh t' == bh t && maybeOneRedRed t') ret

rbExceptRoot t = bso t && noRedRed t && okBlack t

maybeOneRedRed t = oneRedRed t || noRedRed t

oneRedRed t = case t of
  E                             -> False
  T R (T R _ _ _) _ (T R _ _ _) -> False
  T R (T R l1 _ r1) _ r         -> List.all noRedRed [l1, r1, r]
  T R l _ (T R l2 _ r2)         -> List.all noRedRed [l, l2, r2]
  T _ l _ r                     -> False 
```

`balance'`函数期望子树`l`和`r`具有相同的`blackHeight`，并且其中最多有一个红红违例。结果树的`blackHeight`与直接使用`T`数据构造函数构造的树相同，而不是通过不同的旋转。如果触发了四种重新平衡情况之一，则结果树`t'`没有`noRedRed`违例。否则，（未转换的）树`t'`可能有一个。因此，后置条件是`maybeOneRedRed`。

```
balance' c l val r_ =
  let r = 
    checkArg "[balance']" (�rg ->
      (bh l == bh arg) &&
      (xor [  noRedRed l &&  noRedRed arg
           , oneRedRed l &&  noRedRed arg
           ,  noRedRed l && oneRedRed arg ])) r_
  in
  let ret =
    case (c, l, val, r) of
      (B, T R (T R a x b) y c, z, d) -> T R (T B a x b) y (T B c z d)
      (B, T R a x (T R b y c), z, d) -> T R (T B a x b) y (T B c z d)
      (B, a, x, T R (T R b y c) z d) -> T R (T B a x b) y (T B c z d)
      (B, a, x, T R b y (T R c z d)) -> T R (T B a x b) y (T B c z d)
      _                              -> T c l val r
  in
  checkRet "[balance']"
    (\t' -> maybeOneRedRed t' && bh t' == bh (T c l val r)) ret

xor bs = List.filter (\b -> b == True) bs == [True] 
```

因为前置和后置条件在每次函数调用时都会被评估（并且我们提供的谓词在其参数的大小上是线性的），所以这些版本比原始版本运行*慢得多*。

```
> t = buildRandom insert 1000        -- fast

> t' = buildRandom insert' 1000      -- slow

> t == t'
True : Bool 
```

然而，在程序开发过程中，我们经常愿意在性能和帮助测试和识别错误之间进行权衡。

尝试在实现中引入一些错误以触发运行时的合同违规。

一些语言，如[Racket](http://racket-lang.org/)，为指定和检查约束提供了广泛的支持。我们可以想象扩展 Elm，使我们能够编写以下更精确的函数类型，这些类型会自动转换为我们手动编写的包装函数。请注意，在这种语法中，类型由谓词函数“细化”。

```
insert' : x:Int -> t:Tree{rb t} -> t':Tree{rb t'}

ins' : x:Int -> t:Tree{rb t} -> t':Tree{bh t' == bh t && maybeOneRedRed t'}

balance' : c:Color
        -> l:Tree
        -> val:Int
        -> r:Tree{bh l == bh r && xor [ ... ]}
        -> t':Tree{bh t' == bh (T c l val r) && maybeOneRedRed t'} 
```

更好的做法是让语言*静态*地确定这些约束在运行时*永远*不会被违反，因此不需要动态检查。

可惜，在这门课程中，我们不会涉及*软件验证*技术或能够推理出这些精细程序不变量的*依赖类型系统*。但这是一个长期存在且非常活跃的研究领域。

## 删除

从红黑树中删除元素比插入元素要困难得多。我们不会在课堂上讲解删除算法。如果你感兴趣，可以查看 Matt Might 的[这篇文章](http://matt.might.net/articles/red-black-delete/)。

## 栈溢出

很棒，我们有一个快速的，*O(log n)*插入算法...

```
> buildRandom insert 1000        -- fast

> buildRandom insert 10000
RangeError: Maximum call stack size exceeded 
```

...但是`10000`的对数并不是很大，但我们仍然崩溃了。怎么回事？

```
> randomInts 1000
...

> randomInts 10000
RangeError: Maximum call stack size exceeded 
```

啊，问题出在生成一个大型的`List`的随机数，而不是我们的插入算法。遗憾。敬请关注更多信息。

## 阅读

#### 必需

+   Okasaki，第 3.3 章
