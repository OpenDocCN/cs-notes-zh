# 惰性

大多数主流的函数式语言采用*急切*（又名*严格*）的评估策略，其中一个表达式即使其结果值不需要或仅需要部分结果时也会被完全评估。正如我们将看到的，有时候惰性评估某些表达式会有优势。惰性评估有两个重要方面：

1.  *暂停*（又名*延迟*）计算，直到实际需要其结果为止（又名*要求*或*强制*）；以及

1.  *备忘*（又名*缓存*）暂停计算的结果，以防再次需要其值。

许多急切的语言，包括 Elm，在选择性引入惰性方面提供了额外的语言构造。我们将通过两个示例编码——自然数和流——来阐明和说明惰性评估的动机。

## 自然数

我们将逐步介绍几种自然数的编码，并在其中定义一些简单的操作。

#### 第一版 — [`Nat.elm`](https://www.classes.cs.uchicago.edu/archive/2015/winter/22300-1/public-code/Laziness/Nat.elm)

我们首先归纳地定义 `Nat`ural 数字，它要么是`Z`ero，要么是某个其他 `Nat`ural 数字的`S`uccessor。

```
type Nat = Z | S Nat 
```

接下来，让我们定义函数 `toInt` 和 `fromInt` 来将 `Nat`ural 数字转换为和从 `Int`egers 转换为。

```
fromInt : Int -> Nat
fromInt n =
  if | n <= 0    -> Z
     | otherwise -> S (fromInt (n-1)) 
```

如果我们试用 `fromInt`，我们会发现它很快就会使堆栈溢出。

```
> fromInt 0
Z : Nat.Nat

> fromInt 1
S Z : Nat.Nat

> fromInt 10
S (S (S (S (S (S (S (S (S (S Z))))))))) : Nat.Nat

> fromInt 10000
RangeError: Maximum call stack size exceeded 
```

啊，对了，我们应该尾递归地定义函数，并使用[`Trampoline`](http://package.elm-lang.org/packages/elm-lang/core/1.1.0/Trampoline)库，以便它们在恒定的堆栈空间中运行。

```
fromInt : Int -> Nat
fromInt n =
  let foo acc n =
    if | n <= 0    -> Done acc
       | otherwise -> Continue (\_ -> foo (S acc) (n-1))
  in trampoline (foo Z n)

toInt : Nat -> Int
toInt n =
  let foo acc n = case n of
    Z    -> Done acc
    S n' -> Continue (\_ -> foo (1 + acc) n')
  in trampoline (foo 0 n) 
```

那应该能解决问题...

```
> fromInt 10000
RangeError: Maximum call stack size exceeded 
```

或者不。好吧，是时候进行更多的调查新闻了。我们可以启动 Elm Reactor 来开始调试。或者我们可以懒惰一点（双关语），继续在 REPL 中四处探索。

```
> let _ = fromInt 10000 in ()
() : () 
```

这很有趣。调用 `fromInt` 并不是问题所在。所以打印结果的动作导致堆栈溢出？让我们编写我们自己的（跳板式）打印函数来测试这个假设。

```
strNat : Nat -> String
strNat n =
  let foo acc n = case n of
    Z    -> Done acc
    S n' -> Continue (\_ -> foo ("S" ++ acc) n')
  in trampoline (foo "Z" n) 
```

的确，这很有效... 直到我们用尽堆栈空间为止。

```
> fromInt 10000 |> strNat
" ... SSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSZ" : String

> fromInt 10000000 |> strNat
" ... SSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSZ" : String

> fromInt 100000000 |> strNat
FATAL ERROR: JS Allocation failed - process out of memory 
```

现在我们已经解决了调用栈和堆空间的问题，让我们回到使用 `Nat` 进行编程的任务上。我们可以通过逐一剥离 `y` 的 `S`uccessor 标签并将其包装在 `x` 周围来将两个 `Nat` 相加。

```
plus : Nat -> Nat -> Nat
plus x y =
  let foo acc n = case n of
    Z    -> Done acc
    S n' -> Continue (\_ -> foo (S acc) n')
  in trampoline (foo x y) 
```

这个 `plus` 函数编码了我们 `Nat` 类型的加法的通常概念。

```
> plus (fromInt 0) (fromInt 0) |> strNat
"Z" : String

> plus (fromInt 0) (fromInt 2) |> strNat
"SSZ" : String

> plus (fromInt 10) (fromInt 2) |> strNat
"SSSSSSSSSSSSZ" : String

> plus (fromInt 10) (fromInt 2) |> toInt
12 : Int 
```

我们可以通过一次剥离一个数据构造器来为`Nat`定义`eq`uality。

```
eqNat : Nat -> Nat -> Bool
eqNat x y =
  let foo x y = case (x, y) of
    (Z, Z)       -> Done True
    (S x', S y') -> Continue (\() -> foo x' y')
    _            -> Done False
  in trampoline (foo x y) 
```

这似乎运行得很顺利...

```
> eqNat (fromInt 0) (fromInt 0)
True : Bool

> eqNat (fromInt 0) (fromInt 2)
False : Bool

> eqNat (fromInt 10) (fromInt 2)
False : Bool 
```

... 但对于一些看起来应该很容易决定的比较来说，速度真的很慢。

```
> eqNat (fromInt 10000) (fromInt 10000000)
False : Bool

> eqNat (fromInt 0) (fromInt 10000000)
False : Bool 
```

问题在于，在急切评估下，两个 `Nat`ural 数字在调用 `eqNat` 之前都会被完全评估，然后非常快速地决定最后两个不等式。

#### 使用 Thunks 延迟评估 — [`ThunkNat.elm`](https://www.classes.cs.uchicago.edu/archive/2015/winter/22300-1/public-code/Laziness/ThunkNat.elm)

在急切语言中延迟评估表达式`e`的常见方法是定义一个函数`\() -> e`，称为*thunk*，它在评估表达式之前等待一个虚拟参数。

为了延迟计算自然数的表示，我们将移植上述实现。在我们对`Nat`的新表示中，一个`S`uccessor 值存储了它所继承的`Nat`的延迟计算。`force`函数用于评估一个被挂起的计算。

```
type Nat = Z | S (Thunk Nat)

type alias Thunk a = () -> a

force : Thunk a -> a
force thunk = thunk () 
```

请注意，实现以下函数*不*是一个好主意，因为对`delay`的调用将强制评估其参数！

```
delay : a -> Thunk a
delay e = \() -> e 
```

要实现`fromInt`，我们不再需要`trampoline`，因为没有直接递归调用；相反，后一种情况立即返回一个`S`uccessor 值（可能在以后某个时候导致对`fromInt`的调用）。

```
fromInt n =
  if | n <= 0    -> Z
     | otherwise -> S (\_ -> fromInt (n-1)) 
```

注意我们对非`Z`ero 数的新表示方法与以前有很大不同：

```
> import Nat as N
> import ThunkNat (..)

> N.fromInt 10
S (S (S (S (S (S (S (S (S (S Z))))))))) : Nat.Nat

> fromInt 10
S <function> : ThunkNat.Nat 
```

与`fromInt`不同，`toInt`确实需要立即进行递归调用，因为结果类型（`Int`）的表示中没有延迟计算的概念。因此，我们希望采用`trampoline`策略。

```
toInt n =
  let foo acc n = case n of
    Z    -> Done acc
    S n' -> Continue (\_ -> foo (1 + acc) (force n'))
  in trampoline (foo 0 n) 
```

和以前一样，`fromInt`和`toInt`是反函数：

```
> fromInt 100000000 |> toInt
100000000 : Int 
```

注意`toInt`如何使用`force`来评估存储在`Nat`中的所有嵌套挂起。像这样的函数被称为*单块*，而像`fromInt`这样的函数被称为*增量*，因为它不会触发所有嵌套悬挂的评估。

```
> fromInt 100000000 |> toInt
100000000 : Int 
```

另一个单一功能的例子是`strNat`。

```
strNat n =
  let foo acc n = case n of
    Z    -> Done acc
    S n' -> Continue (\_ -> foo ("S" ++ acc) (force n'))
  in trampoline (foo "Z" n) 
```

但是，由于打印`S`uccessor 值的表示现在非常快速，因此此函数不再需要用于上述其原始目的。

```
> fromInt 10000
S <function> : ThunkNat.Nat

> fromInt 10000 |> strNat
" ... SSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSSZ" : String 
```

现在我们可以回到延迟评估`Nat`的动机。

```
eqNat x y =
  let foo x y = case (x, y) of
    (Z, Z)       -> Done True
    (S x', S y') -> Continue (\_ -> foo (force x') (force y'))
    (_, _)       -> Done False
  in trampoline (foo x y) 
```

当`x`和`y`表示相同的数字时，`eqNat`评估`x`和`y`中所有嵌套的挂起。否则，它只评估足够的延迟表示，以演示对应数据构造函数的差异。因此，所有以下比较都运行得很快，不像我们最初的[`Nat.elm`](https://www.classes.cs.uchicago.edu/archive/2015/winter/22300-1/public-code/Laziness/Nat.elm)实现。

```
> fromInt 0 `eqNat` fromInt 0
True : Bool

> fromInt 0 `eqNat` fromInt 2
False : Bool

> fromInt 10 `eqNat` fromInt 2
False : Bool

> fromInt 10000 `eqNat` fromInt 10000000
False : Bool

> fromInt 0 `eqNat` fromInt 10000000
False : Bool 
```

我们用以下增量实现`plus`完成了原始模块的移植。

```
plus x y = case y of
  Z    -> x
  S y' -> S (\_ -> plus x (force y')) 
```

因此，以下比较很快地进行了评估。

```
> fromInt 0 `eqNat` (fromInt 10000000 `plus` fromInt 10000000)
False : Bool 
```

**旁注：**如果我们让 Elm 使用内置的相等性来比较`Nat`会发生什么？

```
> fromInt 0 == fromInt 0
True : Bool

> fromInt 0 == fromInt 1
False : Bool

> fromInt 1 == fromInt 2
Error: Equality error: general function equality is undecidable,
and therefore, unsupported 
```

Elm 在尝试比较两个不同的函数值时会抛出运行时错误。公平地说。但请注意，函数值之间的“物理相等性”是支持的。

```
> fromInt 1 == fromInt 1
Error: Equality error: general function equality is undecidable,
and therefore, unsupported

> let foo = fromInt 1 in foo == foo
True : Bool 
```

#### Thunks 的记忆化 — [`LazyNat.elm`](https://www.classes.cs.uchicago.edu/archive/2015/winter/22300-1/public-code/Laziness/LazyNat.elm)

定义悬浮和增量函数可能是非常有价值的技术，但没有免费的午餐。一个延迟值的表示是一个*闭包*，它是一个用于评估的函数，以及所有由函数引用的自由变量的绑定。因此，随意延迟计算可能会导致大量这些闭包的积累。因此，应该将对延迟计算的使用限制在能够定义增量函数的情况下，这样做的好处就会超过延迟计算所带来的开销。

另一个问题是同样的延迟计算可能会被要求超过一次。如果计算需要大量资源来评估，那么每次重做工作都是不可取的。在一个只有严格求值的纯语言中，没有其他选择：每次强制执行一个延迟计算，它都必须被重新评估。因此，许多严格的语言提供了专门用于操作延迟计算的构造，保证延迟计算的结果在将来再次强制执行时被缓存。术语*惰性求值*通常用于描述对延迟计算的支持，保证最多只评估一次这样的计算。

在 Elm 中，[`Lazy`](http://package.elm-lang.org/packages/maxsnew/lazy/1.0.0/Lazy) 库提供了对惰性求值的支持。（`Lazy` 是一个社区库，所以需要一个[`elm-package.json`](https://www.classes.cs.uchicago.edu/archive/2015/winter/22300-1/public-code/Laziness/elm-package.json)文件来声明这个依赖关系。）`lazy` 函数将 `Thunk a` 转换为 `Lazy a` 值，`force` 评估这个值，重用之前对 `force` 的任何调用的结果。

```
lazy  : (_Tuple0 -> a) -> Lazy a
force : Lazy a -> a 
```

[`lazy`](https://github.com/maxsnew/lazy/blob/1.0.0/src/Native/Lazy.js) 的本机 JavaScript 实现使用一个可变变量（称为 `isForce`）来跟踪特定的延迟是否已经被评估，并使用一个可变变量（称为 `value`）来存储这个结果。

要获得记忆化的好处，将 [`ThunkNat.elm`](https://www.classes.cs.uchicago.edu/archive/2015/winter/22300-1/public-code/Laziness/ThunkNat.elm) 改用 `Lazy` 库是很简单的。首先，我们重新定义 `Nat` 类型如下。

```
type Nat = Z | S (Lazy Nat) 
```

然后，我们在每个延迟值的前面添加一个 `lazy` 的调用。结果的实现可以在[`LazyNat.elm`](https://www.classes.cs.uchicago.edu/archive/2015/winter/22300-1/public-code/Laziness/LazyNat.elm)中找到。（使用 `diff` 或 `vimdiff` 来查看这两个文件的相似之处。）

使用这个实现，我们现在期望第二次强制执行昂贵的悬浮应该几乎是瞬间的。正如我们之前讨论的，`eqNat` 的最坏情况是当它的两个参数相等时。所以让我们以对 `eqNat` 的调用作为一个慢计算的例子。

```
> import LazyNat (..)

> foo i = fromInt i `eqNat` fromInt i
<function> : Int -> Bool

> foo 100000
True : Bool

> foo 1000000
True : Bool 
```

上面的最后一个操作非常缓慢。因此，我们应该能够延迟其评估，`force` 并记录其结果，并且在第二次重新评估时几乎立即重新评估。但第二个 `force` 与第一个一样慢！

```
> slow = lazy (\_ -> foo 1000000)
Lazy <function> : Lazy.Lazy Bool

> force slow
True : Bool

> force slow   -- still slow... :-(
True : Bool 
```

幸好我们还带着调查记者的帽子。

```
> force slow
True : Bool

> (force slow, force slow, force slow, force slow, force slow)
(True,True,True,True,True) : ( Bool, Bool, Bool, Bool, Bool ) 
```

这两个表达式需要大约相同的时间来评估，这表明对于后一种情况，缓存正在起作用。因此，看来原生的记忆表在 REPL 操作之间不会持久存在。

**可选练习** — 编写一个 Elm 程序来测量评估上述两个表达式所需的时间（例如，使用 `Time.fps`）。

## 流

一个常见的包含惰性的数据结构是*流*（又称*惰性列表*）。通过之前的例子详细了解了 Elm 中的惰性后，我们在这里讨论流的内容将会很简要，主要集中在选择正确的表示方式上。

#### 第一次尝试 — [`NotSoLazyList.elm`](https://www.classes.cs.uchicago.edu/archive/2015/winter/22300-1/public-code/Laziness/NotSoLazyList.elm)

表示 `LazyList` 的一种可能性是以下类型。

```
type LazyList a
  = Nil
  | Cons (Lazy a) (LazyList a) 
```

然而，这种数据类型描述的列表并不是非常惰性。我们可以定义一个函数 `range: Int -> Int -> LazyList Int`，并演示一个具有 *n* 个元素的 `LazyList` 立即构建 *n* 个 `Cons` 单元格。

```
> range 1 10
Cons (Lazy <function>)
 (Cons (Lazy <function>)
  (Cons (Lazy <function>)
   (Cons (Lazy <function>)
    (Cons (Lazy <function>)
     (Cons (Lazy <function>)
      (Cons (Lazy <function>)
       (Cons (Lazy <function>)
        (Cons (Lazy <function>)
         (Cons (Lazy <function>) Nil)))))))))
    : NotSoLazyList.LazyList Int 
```

#### 第二次尝试 — [`PrettyLazyList.elm`](https://www.classes.cs.uchicago.edu/archive/2015/winter/22300-1/public-code/Laziness/PrettyLazyList.elm)

另一个选择是以下内容。

```
type LazyList a
  = Nil
  | Cons a (Lazy (LazyList a)) 
```

这很好，但请注意，非 `Nil` 列表必须评估其第一个值。考虑一下 `Int` 的 `range` 的表示是什么样子。

```
> range 1 10
Cons 1 (Lazy <function>) : PrettyLazyList.LazyList Int 
```

#### 最终尝试 — [`LazyList.elm`](https://www.classes.cs.uchicago.edu/archive/2015/winter/22300-1/public-code/Laziness/LazyList.elm)

我们真正想要的是列表中的所有元素，包括第一个元素，都要延迟到需要时才进行评估。我们可以按如下方式实现这一点。

```
type alias LazyList a = Lazy (LazyListCell a)

type LazyListCell a
  = Nil
  | Cons a (LazyList a) 
```

要考虑的一些事情：为什么我们在之前定义惰性 `Nat` 时没有使用类似的策略？

`range` 函数是增量的。注意 *微不足道的* 悬挂 `lazy (\_ -> Nil)`。

```
range : Int -> Int -> LazyList Int
range i j =
  if | i > j     -> lazy (\_ -> Nil)
     | otherwise -> lazy (\_ -> Cons i (range (i+1) j)) 
```

我们也可以描述无限流。

```
infinite : Int -> LazyList Int
infinite i = lazy (\_ -> Cons i (infinite (i+1))) 
```

`take` 函数是增量的。

```
take : Int -> LazyList a -> LazyList a
take k l = case (k, force l) of
  (0, _)         -> lazy (\_ -> Nil)
  (_, Nil)       -> lazy (\_ -> Nil)
  (_, Cons x xs) -> lazy (\_ -> Cons x (take (k-1) xs)) 
```

`take` 的更懒惰版本：

```
take k l =
  if | k == 0    -> lazy (\_ -> Nil)
     | otherwise ->
         case force l of
           Nil       -> lazy (\_ -> Nil)
           Cons x xs -> lazy (\_ -> Cons x (take (k-1) xs)) 
```

增量函数的作用：

```
> infinite 1
Lazy <function> : Lazy.Lazy (LazyList.LazyListCell Int)

> infinite 1 |> take 10
Lazy <function> : Lazy.Lazy (LazyList.LazyListCell Int)

> infinite 1 |> take 10 |> toList
[1,2,3,4,5,6,7,8,9,10] : List Int 
```

将流转换为 `List` 是单体的：

```
toList : LazyList a -> List a
toList l =
  let foo acc l = case force l of
    Nil       -> Done acc
    Cons x xs -> Continue (\_ -> foo (x::acc) xs)
  in
  List.reverse <| trampoline <| foo [] l 
```

`drop` 函数也是单体的，但不一定会强制执行流中的每个悬挂。

```
drop : Int -> LazyList a -> LazyList a
drop k l =
  let foo k l =
    if | k == 0 -> Done l
       | otherwise ->
           case force l of
             Nil       -> Done (lazy (\_ -> Nil))
             Cons _ xs -> Continue (\_ -> foo (k-1) xs)
  in trampoline (foo k l) 
```

例如：

```
> infinite 1 |> drop 10 |> take 10 |> toList
[11,12,13,14,15,16,17,18,19,20] : List Int 
```

使用 `append` 组合两个流是增量的。

```
append : LazyList a -> LazyList a -> LazyList a
append xs ys = case force xs of
  Nil        -> ys
  Cons x xs' -> lazy (\_ -> Cons x (append xs' ys)) 
```

反转流是单体的。注意 `lazy (\_ -> Cons x acc)` 是另一个微不足道的悬挂的示例。值 `x` 和 `acc` 已经被评估过了，因此构建 `Cons` 值不会强制执行任何额外的计算。

```
reverse : LazyList a -> LazyList a
reverse l =
  let foo acc xs = case force xs of
    Nil        -> Done acc
    Cons x xs' -> Continue (\_ -> foo (lazy (\_ -> Cons x acc)) xs')
  in trampoline (foo (lazy (\_ -> Nil)) l) 
```

我们的最终单体示例函数检查相等性。

```
eq : LazyList a -> LazyList a -> Bool
eq x y =
  let foo x y = case (force x, force y) of
    (Cons x xs, Cons y ys) ->
      Continue (\_ -> if x == y then foo xs ys else Done False)
    (Nil, Nil) -> Done True
    _          -> Done False
  in
  trampoline (foo x y) 
```

与 `Nat` 的相等性一样，我们对 `LazyList` 的相等性的实现可以更快地决定不等式，而不是对常规的 `List`。

```
> [] == [1..10000000]
False : Bool

> [] == [1..100000000]
FATAL ERROR: JS Allocation failed - process out of memory

> import LazyList (..)
> import Lazy (..)

> range 1 0 `eq` range 1 1000000
False : Bool

> range 1 0 `eq` range 1 10000000
False : Bool

> range 1 0 `eq` range 1 1000000000000000
False : Bool

> range 1 0 `eq` infinite 1
False : Bool 
```

## 阅读

#### 必需的

+   Okasaki，第四章
