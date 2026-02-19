# 惰性队列

回想一下，[`FastQueue.elm`](https://www.classes.cs.uchicago.edu/archive/2015/winter/22300-1/public-code/Queues/FastQueue.elm)的实现（在教科书中称为“批处理队列”实现），每个操作的摊销成本为*O(1)*，包括`dequeue`，其最坏情况成本为*O(n)*。 然而，摊销分析假设没有`Queue`对象被用作超过一个`Queue`操作的输入。 我们现在将看到使用惰性的队列实现，以实现*O(1)*的摊销边界，尽管每个队列可能被持久使用。

考虑来自教科书的以下示例，在这个示例中，`q_0`是一个队列，其`front`和`back`列表的长度相等，都为`m`。

```
q_0         =  ...             -- |front| = |back| = m
q_1         =  dequeue q_0
q_2         =  dequeue q_1
           ... 
q_m         =  dequeue q_m_minus_1
q_m_plus_1  =  dequeue q_m 
```

使用`FastQueue`的实现，操作`dequeue q_m_minus_1`触发对`List.reverse`的调用，其运行时间为*O(`m`)*；所有其他对`dequeue`的调用都在*O(1)*时间内运行。 在没有持久性的情况下，摊销分析能够推断出这个*昂贵*操作与*廉价*操作相比发生的频率较低，并且任何序列的*n*个`FastQueue`操作总共需要*O(n)*的时间。

## 一个天真的方法 — [`LazyBatchedQueue.elm`](https://www.classes.cs.uchicago.edu/archive/2015/winter/22300-1/public-code/Laziness/LazyBatchedQueue.elm)

作为第一次尝试，我们可以将`FastQueue`的实现移植，使其使用[`LazyList`](https://www.classes.cs.uchicago.edu/archive/2015/winter/22300-1/public-code/Laziness/LazyList.elm)（也称为流）并记忆涉及昂贵调用`List.reverse`的计算。

我们首先将`front`和`back`定义为`LazyList`而不是`List`。

```
type Queue a = Q { front : LazyList a, back : LazyList a } 
```

`empty`队列包含两个空的`LazyList`。

```
empty = mkQ nil nil

nil = lazy (\_ -> Nil) 
```

就像在`FastQueue`中一样，我们将保持`front`仅在`back`为空时为空的不变性。 结果，我们通过强制`front`评估为`LazyListCell`，然后检查它是否为`Nil`来检查`Queue`是否为空。

```
isEmpty (Q {front, back}) =
  case force front of
    Nil -> True
    _   -> False 
```

注意：为什么定义`isEmpty = (==) empty`不是一个好主意？

`enqueue`、`dequeue`和`peek`的实现与之前类似，只是创建和模式匹配`LazyListCell`而不是典型的`List`单元。

```
enqueue x (Q {front, back}) =
  checkFront front (lazy (\_ -> Cons x back))

dequeue (Q {front, back}) = case force front of
  Nil       -> Nothing
  Cons _ f' -> Just (checkFront f' back)

peek (Q {front, back}) = case force front of
  Nil      -> Nothing
  Cons x _ -> Just x 
```

回想一下，`checkFront`函数强制执行并重新建立，如果需要的话，`front`仅为空，如果`back`为空的话。 一个首选项是以下内容。

```
checkFront f b = case force f of
  Nil -> mkQ (reverse b) nil
  _   -> mkQ f b 
```

然而，这个版本强制（单体）`reverse`函数立即处理整个`LazyList`，即使没有更多的`dequeue`或`peek`操作需要这个结果。 更糟糕的是，昂贵的`reverse`操作将在每次评估昂贵的操作`dequeue q_m_minus_1`时执行。

将`reverse`计算暂停如下会更好。

```
checkFront f b = case force f of
  Nil -> mkQ (lazy (\_ -> force (reverse b))) nil
  _   -> mkQ f b 
```

这会延迟`reverse`直到实际需要结果的`LazyList`，并且在再次评估昂贵操作时记忆结果。

尽管如此，如果再次评估操作`dequeue q_m_minus_2`，将创建一个完全不同的`reverse`悬挂，因此惰性和记忆化无法帮助分摊成本。因此，这种对`FastQueue`的简单转换并未解决持久地使用`Queue`的任意版本所面临的挑战。

注意：您可能想要使用`diff`或`vimdiff`查看[`FastQueue.elm`](https://www.classes.cs.uchicago.edu/archive/2015/winter/22300-1/public-code/Queues/FastQueue.elm)和[`LazyBatchedQueue.elm`](https://www.classes.cs.uchicago.edu/archive/2015/winter/22300-1/public-code/Laziness/LazyBatchedQueue.elm)的更改，以了解添加惰性所需的更改。

## 一个巧妙的方法 — [`BankersQueue.elm`](https://www.classes.cs.uchicago.edu/archive/2015/winter/22300-1/public-code/Laziness/BankersQueue.elm)

更巧妙的方法基于这样一个想法，即让`dequeue q_0`创建一个悬挂，涉及到`reverse`，直到`dequeue q_m`操作才强制执行。将悬挂的创建和评估分开允许用 *O(m)* 时间来支付 *O(m)* 成本昂贵的 `reverse` 操作的费用。

为了实现这一策略，我们不会等到`front`列表即将变空之前再颠倒`back`列表。相反，一旦`back`列表变得比`front`列表长，就会立即对`back`列表进行`reverse`操作，然后将其追加到`front`列表中，以保持`Queue`中元素的正确顺序。关键在于由以下定义的`LazyList`：

```
front `append` reverse back 
```

不会立即执行对`reverse`的单片调用，因为`append`是一个增量函数。只有在对`front`列表进行足够多次`dequeue`调用后，才会对`back`进行颠倒。让我们来看一下这种策略的实现，然后讨论它在面对上述问题序列时的表现。

这种表示方式保持了`front`和`back`流的显式`Int`eger 大小。

```
type Queue a = Q Int (LazyList a) Int (LazyList a) 
```

描述`empty`队列很简单。

```
nil = lazy (\_ -> Nil)

empty = Q 0 nil 0 nil

isEmpty (Q i _ _ _) = i == 0 
```

当`front`流的大小大于`0`时，`peek`调用[`LazyList`](https://www.classes.cs.uchicago.edu/archive/2015/winter/22300-1/public-code/Laziness/LazyList.elm)`head`操作，该操作`force`评估`LazyListCell`并返回生成的`Cons`值的第一个元素。

```
peek (Q i front j back) =
  if | i == 0    -> Nothing
     | otherwise -> Just (head front) 
```

如果`back`流严格小于`front`流，则（惰性地）将新元素`x`添加到`back`中。否则，将`back`进行`reverse`操作并（惰性地）追加到`front`中，适当更新大小计数。

```
enqueue x (Q i front j back) =
  if | j < i     -> Q i front (j+1) (lazy (\_ -> Cons x back))
     | otherwise -> Q (i+j+1) (front `append` reverse back) 0 nil 
```

类似地，`dequeue`检查操作是否导致`back`流比新的`front`流更长，在这种情况下，将`back`进行`reverse`操作并追加到新的`front`中。请回忆[`LazyList`](https://www.classes.cs.uchicago.edu/archive/2015/winter/22300-1/public-code/Laziness/LazyList.elm)`tail`操作会`force`其参数并返回生成的`Cons`值的第二个元素。

```
dequeue (Q i front j back) =
  if | i == 0    -> Nothing
     | i == j    -> Just (Q (i+j-1) (tail front `append` reverse back) 0 nil)
     | otherwise -> Just (Q (i-1) (tail front) j back) 
```

这两个操作可以重构为使用一个通用的`check`函数，该函数强制实施`rear`永远不会比`front`长的不变量。

```
enqueue x (Q i front j back) =
  check i front (j+1) (lazy (\_ -> Cons x back))

dequeue (Q i front j back) =
  if | i == 0    -> Nothing
     | otherwise -> Just (check (i-1) (tail front) j back)

check i front j back =
  if | j > i     -> Q (i+j) (front `append` reverse back) 0 nil
     | otherwise -> Q i front j back 
```

即使使用持久数据结构，这种方法也能很好地处理，考虑之前的*m*次`dequeue`操作序列。第一个`dequeue q_0`创建了一个涉及`reverse`的悬挂，被`dequeue q_m`操作强制执行。序列中没有其他操作创建悬挂。因此，要再次强制调用`reverse`需要另一个对`dequeue q_0`的调用，后跟*m-1*次对`dequeue`的调用。因此，`reverse`的*O(m)*成本可以摊销到必须在其之前进行的*O(m)*操作序列中。

教科书的第 6.1、6.2 和 6.3 节展示了如何通过调整银行家方法来适应惰性评估，从而形式化这一论点。

## 另一个聪明的方法 — [`PhysicistsQueue.elm`](https://www.classes.cs.uchicago.edu/archive/2015/winter/22300-1/public-code/Laziness/PhysicistsQueue.elm)

教科书描述了另一种实现类似于`BankersQueue`所采用的策略的方法。在该版本中，（增量的）`append`函数等到`front`变为空时才将（整体的）`reverse`函数应用于`back`。

因为`back`列表只被整体函数处理，所以不需要使用`LazyList`来表示它。因此，对表示的一个更改是使用普通的`List`代替`back`。

```
type Queue a = Q Int (LazyList a) Int (List a) 
```

使用这种表示，之前的关键操作变为

```
front `append'` List.reverse back 
```

假设

```
append' : LazyList a -> List a -> LazyList a 
```

是一个增量函数。（**练习** — 实现`append'`。）

因为这个`append'`函数像`append`一样是增量的，所以生成的列表不会立即完全评估。事实证明，即使这个连接是急切地执行的，摊销分析也可以得到工作。因此，对表示的第二个更改是将`front`存储为`Lazy List`（一个被挂起的普通`List`）而不是`LazyList`（一个流）。

```
type Queue a = Q Int (Lazy (List a)) Int (List a) 
```

使用这种表示，之前的关键操作变为：

```
force front ++ List.reverse back 
```

这种表示的一个结果是，`peek`和`dequeue`必须`force`整个悬挂的`front`列表。为了降低这些操作的成本，对表示的最终更改是保留一个额外的（已评估的）`List`，称为`pre`，它是（悬挂的`List`）`front`的前缀，以便快速访问`front`的前端。

```
type Queue a = Q (List a) Int (Lazy (List a)) Int (List a) 
```

像在`BankersQueue`中一样，`back`的大小永远不允许大于`front`。此外，只有当`front`为空时，才允许`pre`为空。`check`和`checkPre`函数强制执行这些不变量。

```
check pre i front j back =
  if | j <= i    -> checkPre pre i front j back
     | otherwise ->
         let front' = lazy (\_ -> force front ++ List.reverse back) in
         checkPre pre (i+j) front' 0 []

checkPre pre i front j back =
  case pre of
    [] -> Q (force front) i front j back
    _  -> Q pre i front j back 
```

空：

```
empty = Q [] 0 (lazy (\_ -> [])) 0 []

isEmpty (Q _ i _ _ _) = i == 0 
```

`enqueue`操作将添加到`back`，而`peek`则从`pre`中提取，这是`front`的部分评估前端。

```
enqueue x (Q pre i front j back) = check pre i front (j+1) (x::back)

peek (Q pre _ _ _ _) = maybeHead pre

maybeHead xs = case xs of {[] -> Nothing; x::_ -> Just x} 
```

注意，`dequeue`使用`List.tail`来更新`pre`和`front`。

```
dequeue (Q pre i front j back) =
  if | i == 0    -> Nothing
     | otherwise -> let pre'   = List.tail pre in
                    let front' = lazy (\_ -> List.tail (force front)) in
                    Just (check pre' (i-1) front' j back) 
```

课本的第 6.4 节展示了如何将物理学家的方法改编为考虑惰性求值并用来论证这种实现，就像`BankersQueue`一样，即使在持久访问的情况下也具有*O(1)*摊销成本。

## 阅读

#### 推荐

+   Okasaki，第 6.1—6.4 章。虽然我们在这门课上不会涵盖会计技术，但鼓励你多次阅读这些材料，以帮助理解基本机制。
