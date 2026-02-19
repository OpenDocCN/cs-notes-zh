# 拉链和镜头

让我们稍微谈谈良好行为的 Haskell 程序。

因此，像以下这样的良好类型但不终止的结构是被禁止的：

```
loop :: Bool loop = loop wtf :: Bool wtf = undefined crash :: Bool crash = error "fnord"
```

## 回到基础知识

我们可以从以下类型构造多少个值？

```
data Bool = False | True
```

## 排序

另一个众所周知的类型：

```
data Ordering = LT | EQ | GT
```

显然，我们可以构造三种不同类型的值。

## 一个零值类型

在 Haskell 2010 中，我们可以创建无法构造任何值的类型：

```
data Empty
```

这种类型没有值构造函数（我们不能在其上使用 `deriving` 语法）。

“为什么？”你可能会问。用类型进行编程时编译。

## 零、一、二…

所以没什么大不了的，我们可以创建具有零个或多个构造函数的类型：

```
data Empty
```

```
data One = One
```

```
data Bool = False | True
```

## 添加一些参数

鉴于这些：

```
data Ordering = LT | EQ | GT data Bool = False | True
```

这是另一个值得思考的类型。

```
data A = A Bool | B Ordering
```

花一分钟计算这个可以有多少个值。我们来做一个快速调查。

## 抽象 I

现在这个熟悉类型可以有多少个值？

```
(a,b)
```

## 抽象 II

现在这个熟悉类型可以有多少个值？

```
data Either a b = Left a | Right b
```

## 代数 I

为什么我们将这些称为*乘积*类型？

```
(a,b,c) data Product a b c = Product a b c
```

它们可以容纳的值的数量等于：

*a* × *b* × *c*

## 代数 II

对于*和*类型的命名也是一样的：

```
data Sum a b c = A a | B b | C c
```

它们可以容纳的值的数量等于：

*a* + *b* + *c*

## 处理嵌套数据

假设我们正在编写一个基准测试工具。我们以 criterion 为例。

测量产生嘈杂的样本。

## 异常值的影响

我们想要了解样本数据中的异常值如何影响样本均值和标准差。

```
data OutlierEffect = Unaffected -- ^ Less than 1% effect. | Slight -- ^ Between 1% and 10%. | Moderate -- ^ Between 10% and 50%. | Severe -- ^ Above 50% (i.e. measurements -- are useless).
```

我们的 `OutlierEffect` 类型嵌入在另一个携带额外信息的类型中。

```
data OutlierVariance = OutlierVariance {  ovEffect :: OutlierEffect , ovDescription :: String , ovFraction :: Double }
```

## 更多嵌套

而 `OutlierVariance` 嵌入在另一个类型中。

```
data SampleAnalysis = SampleAnalysis {  anMean :: [Double] , anStdDev :: [Double] , anOutlierVar :: OutlierVariance }
```

它嵌套在*另一个*类型中。

```
data Payload = Payload {  sample :: [Double] , sampleAnalysis :: SampleAnalysis , outliers :: Outliers }
```

## 访问数据很容易

即使有三层嵌套，也很容易在给定 `Payload` 的情况下访问 `OutlierEffect`。

```
effect :: Payload -> OutlierEffect effect = ovEffect . anOutlierVar . sampleAnalysis
```

这些记录访问器函数很方便！

## 更新，不那么多

好的，假设我们想要“*修改*”一个嵌入在 `Payload` 中的 `OutlierEffect`。

```
editEffect :: (OutlierEffect -> OutlierEffect) -> Payload -> Payload editEffect eff payload = payload { sampleAnalysis = analysis { anOutlierVar = variance { ovEffect = eff effect } } } where analysis = sampleAnalysis payload variance = anOutlierVar analysis effect = ovEffect variance
```

这太可怕了！它几乎看起来不像 Haskell。

## 这是什么？

我们刚刚看到了 Haskell 的记录更新语法的实际操作。

```
setAddrZip :: Zip -> Address -> Address setAddrZip zip addr = addr { addrZip = zip }
```

这个符号意味着：

+   完全复制记录 `addr`。

+   复制时，将 `addrZip` 字段设置为 `zip`。

这是一种“编辑”值的方式，保持原始值不变，但不需要我们指定要复制的每个字段。

正如我们所见，这也是一种非常不可组合的技巧。

## 我们实际想要的是

我们的要求：

1.  访问记录中的字段。

1.  组合*访问*，以便我们可以检查嵌套记录中的字段。

1.  更新记录中的字段。

1.  组合*更新*，以便我们可以修改嵌套记录中的字段。

使用 Haskell 的记录语法，我们得到 #1 和 #2，有点像 #3（如果我们眯起眼睛），#4 很可怕。

## 该怎么办？

假设我们有一对。

```
(a,b)
```

我们想编辑它的第二个元素。

```
editSnd :: (b -> c) -> (a,b) -> (a,c) editSnd f (a,b) = (a, f b)
```

让我们提到我们对第二个元素感兴趣，*专注*于它。

编辑第一个元素同样容易。

```
editFst :: (a -> c) -> (a,b) -> (c,b) editFst f (a,b) = (f a, b)
```

## 空位

当编辑一个 tole 时，让我们称要填充的插槽为*空位*。

这里，空位在第二个位置。

```
editSnd :: (b -> c) -> (a,b) -> (a,c) editSnd f (a,b) = (a, f b)
```

而在这里，它在第一个。

```
editFst :: (a -> c) -> (a,b) -> (c,b) editFst f (a,b) = (f a, b)
```

## 计算空位

如果我们从 `(a,b)` 中去掉 `b`，那么得到的伪类型有多少个值？

## 计算洞的数量

如果我们从 `(a,b)` 中去掉 `b`，那么得到的伪类型有多少个值？

如果我们从 `(a,b)` 中去掉 `a`，会怎样？

## 计算洞的数量

如果我们从 `(a,b)` 中去掉 `b`，那么得到的伪类型有多少个值？

如果我们从 `(a,b)` 中去掉 `a`，会怎样？

如果我们想从 `(a,b,c)` 中删除一些任意字段，我们可以通过类型表示这一点。

```
data Hole3 a b c = AHole b c | BHole a c | CHole a b
```

## 计算洞的数量

我们可以将 `(x,x,x)` 的值的数量写为 *x* × *x* × *x*，或者 *x*³。

如果我们在下面的 `a`、`b` 和 `c` 中用 `x` 替换，那么类型 `Hole3` 会有多少不同的值？

```
data Hole3 a b c = AHole b c | BHole a c | CHole a b
```

## 计算洞的数量

我们可以将 `(x,x,x)` 的值的数量写为 *x* × *x* × *x*，或者 *x*³。

如果我们在下面的 `a`、`b` 和 `c` 中用 `x` 替换，那么类型 `Hole3` 会有多少不同的值？

```
data Hole3 x x x = AHole x x | BHole x x | CHole x x
```

嗯，那是 3*x*²。

这是否让你想起了符号微分？

## 回到对

这里有一种对的洞类型。

```
data PairHole a b = HoleFst b | HoleSnd a
```

如果我们从洞中取出一个值，我们需要将其存储在某个地方，以便我们可以处理它。

```
data PairZipper a b c = PZ c (PairHole a b)
```

为什么我们有一个额外的类型参数 `c`？

+   因此，我们可以选择稍后在洞中存储什么类型的值。

## 快速练习

请为下面的两个未定义函数提供函数体。

你有一分钟。

```
data PairHole a b = HoleFst b | HoleSnd a data PairZipper a b c = PZ c (PairHole a b) focusFst :: (a,b) -> PairZipper a b a focusFst = undefined focusSnd :: (a,b) -> PairZipper a b b focusSnd = undefined
```

骨架：[`cs240h.scs.stanford.edu/Hole1.hs`](http://cs240h.scs.stanford.edu/Hole1.hs)

## 我的解决方案

```
data PairHole a b = HoleFst b | HoleSnd a data PairZipper a b c = PZ c (PairHole a b) focusFst :: (a,b) -> PairZipper a b a focusFst (a,b) = PZ a (HoleFst b) focusSnd :: (a,b) -> PairZipper a b b focusSnd (a,b) = PZ b (HoleSnd a)
```

这样做的一个好处？

+   多态性强制只能有一种可能的���现。

## 逆转换

显然，我们还需要能够从拉链器转换回一对。

```
unfocusFst :: PairZipper a b a -> (a,b) unfocusFst (PZ a (HoleFst b)) = (a,b) unfocusSnd :: PairZipper a b b -> (a,b) unfocusSnd (PZ b (HoleSnd a)) = (a,b)
```

## 访问专注值

现在我们有专注函数来获取一对的第一个或第二个元素，我们可以为我们的拉链器类型编写一个通用访问器函数。

```
view :: PairZipper a b c -> c view (PZ c _) = c
```

在 `ghci` 中尝试：

```
>>> view (focusFst ("hello",1)) "hello" >>> view (focusSnd ("hello",1)) 1
```

## 编辑专注值

这是更有趣的部分。

```
over :: (c -> c) -> PairZipper a b c -> PairZipper a b c over f (PZ c l) = PZ (f c) l
```

再次在 `ghci` 中： 

```
>>> unfocusSnd . over succ . focusSnd $ ("hello",1::Int) ("hello",2)
```

## 编辑第二部分

这在 `ghci` 中会打印什么？

```
>>> unfocusFst . over length . focusFst $ ("hello",1::Int)
```

## 编辑第二部分

这在 `ghci` 中会打印什么？

```
>>> unfocusFst . over length . focusFst $ ("hello",1::Int)
```

这是一个类型错误！`over` 不够多态。

不好的版本：

```
over :: (c -> c) -> PairZipper a b c -> PairZipper a b c over f (PZ c l) = PZ (f c) l
```

好版本允许编辑以更改正在编辑的字段的类型：

```
over :: (c -> d) -> PairZipper a b c -> PairZipper a b d over f (PZ c l) = PZ (f c) l
```

## 嗯

这种方法存在问题。

我们必须指定我们在“管道”的两端专注的字段。

+   这是重复的。

我们能否组合这些，以便我们可以先“focusFst”，然后“focusSnd”以获得另一个拉链器？

+   不。

## 将事物粘合在一起

与其保持 `focusFst` 和 `unfocusFst` 分开，并手动将它们连接在一起，不如自动管理它们。

```
data Focused t a b = Focused {  focused :: a , rebuild :: b -> t }
```

一个 `Focused` 是一个由以下组成的对：

+   专注的元素

+   一个知道如何重建原始值的函数

```
type Focuser s t a b = s -> Focused t a b
```

一个 `Focuser` 是一个接受一个值并给我们一个 `Focused` 的函数。

## 为什么这么多态？

回想一下，我们最初的 `over` 定义不够多态。

我们无法在编辑对时更改第一个元素的类型。

```
>>> unfocusFst . over length . focusFst $ ("hello",1::Int)
```

嗯，`Focused` 和 `Focuser` 有很多类型参数，以确保这种通用性。

## 另一个视角

```
data Focused t a b = Focused {  focused :: a , rebuild :: b -> t }
```

`Focused` 实际上表示：

+   我正在专注于一个 `a`

+   我可能会将其类型更改为 `b`

+   当我最终完成专注时，我会给你一个`t`（这是`s`，每个`a`替换为`b`的`s`）

## 再看一遍

```
type Focuser s t a b = s -> Focused t a b
```

`Focuser`的“含义”是：

+   你给我一个`s`

+   我将专注于一个`a`

+   我可能会将其类型更改为`b`

+   当我完成专注时，我可能会将我给你的东西从`s`改为`t`（再次是每个`a`替换为`b`的`s`）

## 一些机制

用于处理这些类型的函数：

```
unfocus :: Focused s a a -> s unfocus (Focused focused rebuild) = rebuild focused view :: Focuser s t a b -> s -> a view l s = focused (l s) over :: Focuser s t a b -> (a -> b) -> s -> t over l f s = let Focused focused rebuild = l s in rebuild (f focused)
```

我们的朋友`focusFst`和`focusSnd`在这个框架中重新定义：

```
_1 :: Focuser (a,b) (c,b) a c _1 (a,b) = Focused a (\c -> (c,b)) _2 :: Focuser (a,b) (a,c) b c _2 (a,b) = Focused b (\c -> (a,c))
```

## 你的回合

这是你的脚手架：

```
data Focused t a b = Focused {  focused :: a , rebuild :: b -> t } type Focuser s t a b = s -> Focused t a b
```

花两分钟来实现这个：

```
focusHead :: Focuser [a] [a] a a focusHead = undefined
```

它应该专注于列表的头部，这样我们就可以在`ghci`中运行这个：

```
>>> over focusHead toUpper "anita" "Anita"
```

骨架：[`cs240h.scs.stanford.edu/Focus.hs`](http://cs240h.scs.stanford.edu/Focus.hs)

## 再次抽象

我们最有趣的两个函数有很多共同之处。

```
over :: Focuser s t a b -> (a -> b) -> s -> t view :: Focuser s t a b -> s -> a
```

我们如何统一这些类型？

+   通过抽象来决定使用什么类型。

```
wat :: Focuser s t a b -> (a -> f b) -> s -> f t
```

## 类型级别的乐趣

这里，`f`是一个类型级别的函数。

```
wat :: Focuser s t a b -> (a -> f b) -> s -> f t
```

如果我们提供类型级别的恒等函数，`f`消失了，我们得到了`over`的类型：

```
wat :: Focuser s t a b -> (a -> f b) -> s -> f t over :: Focuser s t a b -> (a -> b) -> s -> t
```

使用类型级别的`const a`函数，我们得到了`view`的类型：

```
wat :: Focuser s t a b -> (a -> f b) -> s -> f t view :: Focuser s t a b {- ignored -} -> s -> a
```

## 类型级别的恒等

在[`Data.Functor.Identity`](http://hackage.haskell.org/package/transformers/docs/Data-Functor-Identity.html)中定义：

```
newtype Identity a = Identity { runIdentity :: a } instance Functor Identity where fmap f (Identity a) = Identity (f a)
```

## 类型级别的 const

在[`Control.Applicative`](http://hackage.haskell.org/package/base/docs/Control-Applicative.html#v:Const)中定义：

```
newtype Const a b = Const { getConst :: a } instance Functor (Const a) where fmap _ (Const v) = Const v
```

## 我们的最终类型

```
{-# LANGUAGE RankNTypes #-} type Lens s t a b = forall f. Functor f => (a -> f b) -> s -> f t
```

从我们作为透镜库编写者的角度：

我们在这里使用`forall`来明确表示*我们控制*我们使用的`Functor`，而不是我们的调用者。

我们选择`Identity`或`Const a`来获取`over`和`view`的正确类型。

## 我们的最终类型

```
{-# LANGUAGE RankNTypes #-} type Lens s t a b = forall f. Functor f => (a -> f b) -> s -> f t
```

从我们作为透镜库编写者的角度：

我们必须向用户解释这个类型。

+   给我一个`s`，我会专注于其类型为`a`的元素

+   如果你使用`over`进行编辑，你可以将那些`a`类型改为`b`

+   编辑完成后，你会得到一个`t`，如果你没有将`a`改为`b`，那么它将是`s`

## 新机制

```
{-# LANGUAGE RankNTypes #-} import Control.Applicative import Data.Functor.Identity type Lens s t a b = forall f. Functor f => (a -> f b) -> s -> f t over :: Lens s t a b -> (a -> b) -> s -> t over l f s = runIdentity (l (Identity . f) s) view :: Lens s t a b -> s -> a view l s = getConst (l Const s)
```

## 元组部分

如果我们打开这个：

```
{-# LANGUAGE TupleSections #-}
```

并写下这个：

```
(a,)
```

它等同于这个：

```
\b -> (a,b)
```

## 更多机制

```
{-# LANGUAGE TupleSections #-} _1 :: Lens (a,b) (c,b) a c _1 f (a,b) = (,b) <$> f a _2 :: Lens (a,b) (a,c) b c _2 f (a,b) = (a,) <$> f b _head :: Lens [a] [a] a a _head f (a:as) = (:as) <$> f a
```

## 组合访问

在`ghci`中：

```
>>> view (_1 . _head) ("foo",True) 'f'
```

为什么这与传统的组合顺序不同？

```
>>> (head . fst) ("foo",True) 'f'
```

## 透镜的组合

透镜到底是*用来做什么*的？

+   它将对结构的*部分*的操作转换为对*整个*结构的操作。

因此：

+   `_1`和`_2`并*不*只是“获取器”，它们获取一个*完整对*并专注于其第一个或第二个元素。

+   就是`view`和`over`决定了获取器或设置器的性质。

那么组合透镜意味着什么？

如果你写`_1 . _head`，你正在：

+   获取整个对，并专注于它的第一个元素

+   获取整个对，并专注于列表头部*在对的第一个元素内*

## 组合修改

让我们想想如何使用透镜机制来给我们一个名字首字母大写的对。

```
("anita", True)
```

## 1: 为什么透镜是可组合的？

乍一看，很难说出为什么`_1 . _head`甚至能通过类型检查：

```
_1 :: Functor f => (a -> f c) -> (a, b) -> f (c, b) _head :: Functor f => (a -> f a) -> [a] -> f [a]
```

尤其是——为什么我们可以使用`.`进行函数组合？

## 2: 为什么透镜是可组合的？

关键在于记住，一个带有 2 个参数的函数实际上是一个返回函数的 1 个参数的函数。

```
_1 :: Functor f => (a -> f c) -> ((a, b) -> f (c, b)) _head :: Functor f => (a -> f a) -> ([a] -> f [a]) _1._head :: Functor f => (a -> f a) -> ([a], b) -> f ([a], b)
```

## 接下来呢？

最好的开始地方是从“入门级”开始：

+   [lens-family-core 包](http://hackage.haskell.org/package/lens-family-core)是最容易学习的

+   也有最容易阅读的源代码：强烈推荐！

完整的操作：

+   [lens 包](http://lens.github.io/)更加强大，更加抽象，更加难以学习。

+   由于庞大而有些争议

在实践中变得越来越广泛使用：

+   我的[wreq HTTP 库](http://www.serpentine.com/wreq)

## 镜头操作符的指南

`^.`是`view`（类似于“getter”）

`%~`是`over`（类似于“编辑器”）

`.~`是`over` – 但接受一个*值*而不是*函数*（类似于“setter”）

`&`只是带有翻转参数的`$`

使用如下：

```
foo & someField %~ ('a':) & otherField .~ 'b'
```

（“被修改的事物，后跟链式修饰符。”）
