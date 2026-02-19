# 尾递归

上次，我们在尝试生成随机数列表时遇到了问题。

```
randomInts n =
  let seed = Random.initialSeed 0 in
  fst (Random.generate (Random.list n (Random.int 0 10000)) seed)

> randomInts 1000
[ ... ] : List Int

> randomInts 10000
RangeError: Maximum call stack size exceeded 
```

`10000`并不算很大，但我们仍然耗尽了"调用栈"空间。

以下示例表明，数字列表本身的大小并不是问题所在...

```
> [1..10000]
[ ... ] : List number

> [1..100000]
[ ... ] : List number

> [1..1000000]
[ ... ] : List number

> [1..10000000]
[ ... ] : List number

> [1..100000000]
FATAL ERROR: JS Allocation failed - process out of memory 
```

好吧，最终会的。但对于像`10000`这样的小数字来说不是。在某个时刻（在最后两个示例交互之间）可能需要更多内存（也称为"堆"空间，尽管与我们学习的堆数据结构无关），而我们可能无法或不被允许使用。

但调用栈错误与堆错误非常不同。调用栈用于跟踪当前正在执行的函数堆栈。随着程序的执行，调用栈会增长和缩小。一般来说，相对于堆所分配的内存，调用栈所占用的内存要小得多。这是有道理的，因为计算的代码通常比其操作的数据要小得多。

因此，调用栈错误意味着我们有太多"未完成"的函数调用，它们正在等待它们的被调函数返回才能继续。自然地，递归定义的函数会堆积大量"栈帧"，因此在功能语言中特别是在鼓励（或强制，在纯函数语言的情况下）程序员大量使用递归的情况下，耗尽栈空间是一个严重问题。

让我们更仔细地看一些示例，定义在[`TailRecursion.elm`](https://www.classes.cs.uchicago.edu/archive/2015/winter/22300-1/public-code/TailRecursion.elm)中供参考。

## 数字上的递归

考虑一个简单的递归函数，对前`n`个正整数求和。

```
sum n =
  if | n <= 0    -> 0
     | otherwise -> n + sum (n-1) 
```

再次，即使是相当小的输入，我们仍然遇到了这个讨厌的调用栈空间错误。

```
> sum 100
5050 : number

> sum 1000
500500 : number

> sum 10000
50005000 : number

> sum 100000
RangeError: Maximum call stack size exceeded 
```

语言（尤其是函数式语言）处理这个问题的方式是达成以下协议：如果程序员编写的递归函数是*尾递归*，那么语言编译器承诺在恒定的栈空间中评估函数（而不是根据递归调用的数量线性增长）。

#### 程序员的义务：定义尾递归函数

如果所有对`f`的递归调用（如果有的话）都出现在尾位置，那么函数`f`是尾递归的。

许多递归函数，但并非全部，可以通过定义一个辅助函数来将其重写为尾递归，该辅助函数将接受一个额外的参数，用于存储"累积"或"运行"结果，在每次递归调用中更新。当不再需要递归调用时，此额外参数的值将作为最终结果返回。

例如，考虑以下尾递归辅助函数来求前`n`个正数的和。

```
sum_tr_ : Int -> Int -> Int
sum_tr_ acc n =
  if | n <= 0    -> acc
     | otherwise -> sum_tr_ (n+acc) (n-1) 
```

最后要做的是实现一个函数，通过提供累积结果的初始值来启动递归。

```
sum_tr = sum_tr_ 0 
```

#### 编译器的义务：将尾递归转换为循环

进入这种协议的语言之所以这样做，是因为尾递归函数可以在具有命令式特性的目标语言中被转换为循环。

例如，假设目标语言包含对可变变量或引用（由`var`创建）、解引用变量（由`!`运算符表示）、更新可变变量（由`:=`运算符表示）和循环的支持，上面的`sum_tr_`函数可能被翻译为类似以下内容的东西。

```
sum_tr_ acc n =
  var i   := n;
  var res := acc;
  while (not (!i <= 0)) {
    res := !i + !res;
    i   := !i - 1;
  }
  !res 
```

注意，可变变量`i`和`res`分别用（不可变的）值`n`和`acc`初始化，并且`while`循环迭代地更新这些变量，只要`i`的当前值为非负。执行循环不会向调用堆栈添加任何帧，因此翻译版本不会出现耗尽堆栈空间以跟踪未完成递归调用的可能性。

尾调用消除对大多数函数式编程语言至关重要。然而，Elm 并没有提供这种优化。事实上，我们的尾递归函数似乎比我们的原始版本更早耗尽堆栈空间！

```
> sum_tr 100
5050 : Int

> sum_tr 1000
500500 : Int

> sum_tr 10000
RangeError: Maximum call stack size exceeded

> sum_tr 100000
RangeError: Maximum call stack size exceeded 
```

Elm 与用户没有达成尾调用消除协议，部分原因是目标语言 JavaScript 不支持它。然而，Elm 提供了一些非常合理的解决方法。

#### Trampolines

[`Trampoline`](http://package.elm-lang.org/packages/elm-lang/core/1.1.0/Trampoline)库提供了一个 API，允许程序员显式地“请求”尾调用优化。为此，程序员不会像上面那样编写一个函数

```
sum_tr_ : Int -> Int -> Int 
```

而是会编写一个非常相似的函数

```
sum_tramp_ : Int -> Int -> Trampoline Int 
```

其中预期函数的返回值被包装在`Trampoline`数据类型中。这种类型的值可以通过`Done`构造函数构造，该构造函数表示递归计算的结束，或者`Continue`，其中包含一个类型为`() -> Trampoline a`的函数，指定如何计算递归计算的下一步。

具体来说，将`sum_tr_`重写为`sum_tramp_`所需的更改只是在每个分支的返回表达式中加上包装。

```
sum_tramp_ : Int -> Int -> Trampoline Int
sum_tramp_ acc n =
  if | n <= 0    -> Done acc
     | otherwise -> Continue (\_ -> sum_tramp_ (n+acc) (n-1)) 
```

`Trampoline`库提供了函数

```
trampoline : Trampoline a -> a 
```

以在常量空间中运行包装的递归函数。因此：

```
sum_tramp = trampoline << sum_tramp_ 0 
```

我们现在可以观察到`sum_tramp`比我们未包装的尾递归版本`sum_tr`更好地扩展。

```
> sum_tr 100000
RangeError: Maximum call stack size exceeded

> sum_tramp 100000
5000050000 : Int

> sum_tramp 1000000
500000500000 : Int

> sum_tramp 10000000
50000005000000 : Int

> sum_tramp 100000000
5000000050000000 : Int 
```

正如你可能已经猜到的，[`Trampoline.elm`](https://github.com/elm-lang/core/blob/1.1.0/src/Trampoline.elm)中`trampoline`的实现使用了一个原生的 JavaScript 函数，在[`Trampoline.js`](https://github.com/elm-lang/core/blob/1.1.0/src/Native/Trampoline.js)中定义，该函数使用循环来评估计算。酷！

注意，上面对`sum_tramp`的最后一次调用仍然非常慢 — 这是由于在 JavaScript 中创建如此多的 thunk 相对昂贵 — 但至少它成功完成了。

关于我们对`sum_tramp_`的定义，还有一件事情要注意，诱人的是将惰性求值重写为对`always`的调用，如下所示：

```
sum_tramp_ acc n =
  if | n <= 0    -> Done acc
     | otherwise -> Continue (always (sum_tramp_ (n+acc) (n-1))) 
```

进一步进行一步会得到以下整洁的定义，这甚至更接近于“理想”的定义`sum_tr_`。

```
sum_tramp_ acc n =
  if | n <= 0    -> Done acc
     | otherwise -> continue (sum_tramp_ (n+acc) (n-1))

continue = Continue << always 
```

不幸的是，我们简化定义的渴望并不是一个好主意。为什么不是呢？

## 列表上的递归

下面是在许多函数式编程语言中定义左折叠的规范方式。

```
foldl : (a -> b -> b) -> b -> List a -> b
foldl f acc xs = case xs of
  []     -> acc
  x::xs' -> foldl f (f x acc) xs' 
```

因为`foldl`是尾递归的，执行尾调用消除的语言会将其重写成类似以下的形式。

```
foldl f acc xs =
  var ys  := xs;
  var res := acc;
  while (not (!ys = [])) {
    let (x::xs') = !ys in
      res := f x !res;
      ys  := xs';
  }
  !res 
```

但是，再次强调，Elm 和 JavaScript 并没有为我们提供自动尾调用消除。

```
> foldl (+) 0 [1..1000]
500500 : number

> foldl (+) 0 [1..10000]
RangeError: Maximum call stack size exceeded 
```

定义一个使用`Trampoline`的版本很简单。

```
foldl_tramp_ : (a -> b -> b) -> b -> List a -> Trampoline b
foldl_tramp_ f acc xs = case xs of
  []     -> Done acc
  x::xs' -> Continue (\_ -> foldl_tramp_ f (f x acc) xs')

foldl_tramp : (a -> b -> b) -> b -> List a -> b
foldl_tramp f init xs = trampoline <| foldl_tramp_ f init xs 
```

啊，好多了。

```
> foldl_tramp (+) 0 [1..10000]
50005000 : number
> foldl_tramp (+) 0 [1..100000]
5000050000 : number
> foldl_tramp (+) 0 [1..1000000]
500000500000 : number 
```

那么，库版本的[`List.foldl`](http://package.elm-lang.org/packages/elm-lang/core/1.0.0/List)使用`Trampoline`吗？

```
> List.foldl (+) 0 [1..1000000]
500000500000 : number 
```

结果并不是这样。相反，它被定义（在[`List.elm`](https://github.com/elm-lang/core/blob/1.0.0/src/List.elm)中）使用了一个本地的 JavaScript 函数（在[`List.js`](https://github.com/elm-lang/core/blob/1.0.0/src/Native/List.js)中定义），并且，不出所料，使用了一个循环！这在道德上与`Trampoline`方法相同，只是被特殊地用于与`List`类型一起工作。

#### 从右边折叠

下面的`foldr`函数的规范定义不是尾递归的。

```
foldr : (a -> b -> b) -> b -> List a -> b
foldr f acc xs = case xs of
  []     -> acc
  x::xs' -> f x (foldr f acc xs') 
```

**可选练习** — 编写一个版本的`foldr`，使得定义内的任何递归都在常量堆栈空间中运行，要么使用`List.foldl`，要么使用`foldl_tramp`。

## 回到随机列表

好了，现在回到我们有问题的`randomInts`函数。为什么会爆栈呢？

查看[`Random.elm`](https://github.com/elm-lang/core/blob/1.1.0/src/Random.elm)会发现问题：`list`是用尾递归函数`listHelp`实现的，但没有使用`Trampoline`或`List.foldl`。

**可选练习** — 编写一个版本的

```
list : Int -> Generator a -> Generator (List a) 
```

使得定义内的递归调用在常量堆栈空间中运行。注意，因为[`Random`](http://package.elm-lang.org/packages/elm-lang/core/1.1.0/Random)模块没有暴露`Generator`数据构造函数，你必须在模块内实现你自己的版本。因此，首先获取[`Random.elm`](https://github.com/elm-lang/core/blob/1.1.0/src/Random.elm)的源代码，然后在其中定义你的函数。

假设你已经将你的模块版本命名为`RandomList`，定义以下测试驱动程序。

```
module TestRandomList where

import Random     as R
import RandomList as R'

randomInts n =
  let seed = R.initialSeed 0 in
  fst (R.generate (R.list n (R.int 0 10000)) seed)

randomInts' n =
  let seed = R'.initialSeed 0 in
  fst (R'.generate (R'.list n (R'.int 0 10000)) seed) 
```

然后，你应该能够演示改进如下。

```
> import TestRandomList (..)

> randomInts 10
[6992,4473,9857,1963,20,8490,708,8552,7773,6495] : List Int

> randomInts' 10
[6992,4473,9857,1963,20,8490,708,8552,7773,6495] : List Int

> randomInts 10000
RangeError: Maximum call stack size exceeded

> randomInts' 10000
[ ... ] : List Int 
```
