# 幻影

让我们思考一个我们见过但没有注意到的编程模式。

## 模式：I

```
0
```

```
0 + n == n n + 0 == n
```

```
(a + b) + c == a + (b + c)
```

## 模式：II

```
1
```

```
1 * n == n n * 1 == n
```

```
(a * b) * c == a * (b * c)
```

## 模式：III

```
[]
```

```
[] ++ n == n n ++ [] == n
```

```
(a ++ b) ++ c == a ++ (b ++ c)
```

## 模式：IV

```
True
```

```
True && n == n n && True == n
```

```
(a && b) && c == a && (b && c)
```

## 抽象的模式

类型类：

```
class Monoid a where -- A "zero element"  mempty :: a -- An associative operation  mappend :: a -> a -> a
```

你在哪里可以找到这个类型类？

```
import Data.Monoid
```

## 单子

`Monoid` 的实例必须遵守一些规则。

规则 1：单位元素

```
mempty `mappend` n == n n `mappend` mempty == n
```

规则 2：我们的结合操作 *必须确实结合*。

```
(a `mappend` b) `mappend` c == a `mappend` (b `mappend` c)
```

## 规则？

单子来自抽象代数。

在抽象代数中，必须为真的规则被称为 *公理*。

也称为 *规律*。

在 Haskell 中，这些规则/公理/法则是如何强制执行的？

+   它们不是。

## 列表的单子

这是最简单和最熟悉于 Haskell 程序员的情况：

```
instance Monoid [a] where mempty = [] xs `mappend` ys = xs ++ ys
```

快速测验：

+   还有哪些定义符合 `Monoid` 的规律？

+   它们有任何意义吗？

## 数字的单子？

数字是一个有趣的案例。

加法作为单子：

+   单位 `0`

+   结合运算符 `+`

乘法作为单子：

+   单位 `1`

+   结合运算符 `*`

## 我们何时使用类型类？

假设你想将一个代码模式抽象成一个类型类。

在什么情况下这可能效果最好？

+   当对于给定类型只有 *一个* "规范" 行为时。

对于列表，我们的 `Monoid` 实例 *是* 规范的：

+   遵循规律的任何其他行为都只是 *奇怪* 的。

对于数字，我们有两种合理的行为：

+   没有一个 `Monoid` 实例可以被称为规范的！

## 乘法的单子

```
newtype Product a = Product { getProduct :: a } deriving (Eq, Ord, Read, Show, Bounded) instance Num a => Monoid (Product a) where mempty = Product 1 Product x `mappend` Product y = Product (x * y)
```

## 加法的单子

```
newtype Sum a = Sum { getSum :: a } deriving (Eq, Ord, Read, Show, Bounded) instance Num a => Monoid (Sum a) where mempty = Sum 0 Sum x `mappend` Sum y = Sum (x + y)
```

## `Either` 类型

存在一个名为 `Either` 的内置类型。

```
data Either a b = Left a | Right b
```

按照惯例：

+   `Left` 表示 "出了问题"

+   `Right` 表示 "结果是成功"

常用如下：

```
type Result a = Either String a
```

（其中 `String` 携带一个错误消息）

## 编码练习

创建一个 `Monoid` 实例，从一系列 `Either` 值中获得 *第一个成功*。

期望的行为：

```
Left "you goofed" `mappend` Left "i win!" `mappend` Right "rats! you won!" == Right "rats! you won!"
```

你有五分钟。

## 编码练习的环境设备

如果你导入 `Data.Monoid`，你将有以下定义可用：

```
class Monoid a where  mempty :: a  mappend :: a -> a -> a data Either a b = Left a | Right b
```

## 语言障碍

你试过写这样的代码吗？

```
instance Monoid (Either a b) where mempty = Left {- what ??? -} Right a `mappend` _ = Right a _ `mappend` b = b
```

当你试图定义 `mempty` 时肯定会遇到麻烦。

为什么？

## 类型量化

在 Haskell 中，类型变量被 *量化*。

它们代表给定域中的所有类型。

如果没有提到类型类，类型变量隐式地被 *普遍* 量化。

我们可以明确地写出这些量词：

```
length :: forall a. [a] -> Int
```

"`length` 函数必须接受任何列表，无论它包含什么类型的数据。"

## 全称量化

全称量化在这里为什么相关？

```
instance Monoid (Either a b) where mempty = Left {- what ??? -}
```

## 全称量化

全称量化在这里为什么相关？

```
instance Monoid (Either a b) where mempty = Left {- what ??? -}
```

由于 `mempty` 给出了一个 "零元素"，它必须以某种方式为类型 `a` 产生一个零元素。

但由于 `a` 是普遍量化的，它代表 *每种类型*。

显然没有一个合法的值适用于每种类型。

不可能编写一个明智的实例。

## 一个可能的修复

这也不会通过类型检查：

```
instance Monoid (Either String a) where mempty = Left "fnord" Right a `mappend` _ = Right a _ `mappend` b = b
```

然而，我们可以通过在源文件顶部添加以下内容使其编译通过：

```
{-# LANGUAGE FlexibleInstances #-}
```

## 指示

这是一个特殊格式的注释：

```
{- i am a normal comment -} {-# i am a special comment #-}
```

"特殊" 注释通常包含改变编译器行为的指令（"指示"）。

`LANGUAGE`指令启用非标准语言特性。

```
{-# LANGUAGE FlexibleInstances #-}
```

`FlexibleInstances`使编译器考虑[更多类型类实例作为合法](http://www.haskell.org/ghc/docs/latest/html/users_guide/type-class-extensions.html#instance-rules)，而不仅仅是 Haskell 98 标准允许的。

## 更多关于指令的内容

随着我们的进展，你会看到更多指令。

有些被广泛使用，有些则不是。

有些是安全的，有些不是...

+   直到让类型检查器陷入无限循环！（`UndecidableInstances`）

`FlexibleInstances`被广泛使用且通常安全。

## 回到我们的修复

这*将*通过类型检查：

```
{-# LANGUAGE FlexibleInstances #-} instance Monoid (Either String a) where mempty = Left "fnord" Right a `mappend` _ = Right a _ `mappend` b = b
```

但它是否是规范的？

## 规范性

为什么要担心我们的`Monoid`实例是否规范？

每当声明任何类型类的实例时：

+   它会自动提供给导入你模块的每个模块。

+   你不能说“我不想导入实例`X`” :-(

如果你为一个流行类型类定义一个奇怪的实例，你会“感染”那些导入你模块的人。

+   确保你的实例是有意义的！

## 终于！

通过使用`newtype`，我们不会意外地将一个愚蠢的`Monoid`实例与`Either String a`关联起来。

```
{-# LANGUAGE FlexibleInstances #-} import Data.Monoid newtype FirstRight a b = FirstRight {  getFirstRight :: Either a b } instance Monoid (FirstRight String a) where mempty = FirstRight (Left "suxx0rz") a@(FirstRight (Right _)) `mappend` _ = a _ `mappend` b = b
```

## HTTP POST

让我们向服务器上传一些至关重要的数据。

```
curl --data foo=bar --verbose \ http://httpbin.org/post
```

## 多部分表单上传

当我们向表单 POST 多部分数据（例如上传照片）时，一些信息是强制性的，而其他内容是可选的。

```
data Part = Part { -- name of the <input> tag this belongs to  name :: String -- filename of file we're uploading , fileName :: Maybe FilePath -- type of file , contentType :: Maybe ContentType -- file contents , body :: String } deriving (Show)
```

## 上传数据

假设我们想构建一个支持 POST 的 HTTP 客户端。

网页通常期望多部分表单数据，而 REST API 有不同的需求。

这里有一些类型，让我们能够表示一个 POST 主体。

```
type Param = (String, String) type ContentType = String data Payload = NoPayload | Raw ContentType String | Params [Param] | FormData [Part] deriving (Show)
```

你能为`Payload`编写一个`Monoid`实例吗？

自行决定，然后与伙伴讨论 2 分钟。

## 哼

这部分足够简单：

```
instance Monoid Payload where mempty = NoPayload mappend NoPayload b = b mappend a NoPayload = a mappend (Params a) (Params b) = Params (a++b) {- ... -}
```

剩下的`mappend`呢？

## 语义问题

很容易看出我们如何将`Params`或`FormData`粘合在一起。

```
data Payload = NoPayload | Raw ContentType String | Params [Param] | FormData [Part]
```

然而，混合`Raw`和`Params`，或`Params`和`FormData`，是荒谬的。

一个直接的`Monoid`实例将不得不崩溃（！！！）如果我们尝试这样做。

## 处理失败（糟糕地）

如果我们使用`Maybe`类型来表示对`mappend`的失败尝试呢？

```
{-# LANGUAGE FlexibleInstances #-} -- I dropped the NoPayload constructor. Why? data Payload = Raw ContentType String | Params [Param] | FormData [Part] deriving (Show) instance Monoid (Maybe Payload) where mempty = Nothing mappend Nothing b = b mappend a Nothing = a mappend (Just (Params a)) (Just (Params b)) = Just (Params (a++b)) mappend (Just (FormData a)) (Just (FormData b)) = Just (FormData (a++b)) mappend _ _ = Nothing
```

## 耶？

这样编译是可以的，但存在一个概念问题。

+   每次我们使用`mappend`，我们都必须模式匹配结果，看看`mappend`是否成功。

在 API 设计圈子中，这被称为“糟糕”。

但等等，情况会变得更糟！

## 哦，错误消息，你在哪里？

让我在`ghci`中尝试一下：

```
Just (Params []) `mappend` Just (Params [])
```

## 重叠实例

还记得`FlexibleInstances`吗？

它允许我们为类型`Maybe Payload`编写一个`Monoid`实例。

麻烦的是，`Data.Monoid`已经为`Maybe a`定义了一个实例。

`FlexibleInstances`允许这两个*定义*快乐地共存。

但是当我们想*使用*一个实例时，GHC 不知道该使用哪一个！

## 重叠实例

进入`OverlappingInstances`指令：

```
{-# LANGUAGE FlexibleInstances, OverlappingInstances #-}
```

这允许多个实例共存*并*被使用。

可见的最具体实例将被使用。

一个非常方便的扩展！

+   也是一个指向你脚的大语义枪。

## 重叠实例的问题

为什么要担心`OverlappingInstances`？

+   使得不正确的程序仍然可以通过类型检查。

+   可能导致混乱的错误消息。

+   一个经过类型检查的程序可以通过在某个远程模块中添加一个实例声明来改变其含义。

一方面，你可以[发表关于它们问题的论文](http://web.cecs.pdx.edu/~jgmorris/pubs/morris-icfp2010-instances.pdf)，所以对于学术生涯来说并不糟糕。

## 检查中

我们有一个`Monoid`实例：

+   有一个糟糕的 API

+   使用了一个不靠谱的语言扩展

我们能做得更好吗？

## 幻影类型

让我们在`Payload`类型的左侧添加一个类型参数。

```
data Payload a = NoPayload | Raw ContentType String | Params [Param] | FormData [Part] deriving (Show)
```

类型变量`a`*不出现在 RHS 中*。

我们称之为*幻影类型*。

它是用来做什么的？

## 一个小型的上传 API

```
param :: String -> String -> Payload [Param] param name value = Params [(name, value)]
```

```
filePart :: String -> FilePath -> IO (Payload [Part]) filePart name path = do body <- readFile name return (FormData [Part name (Just path) Nothing body])
```

## 考虑这些类型

```
param :: String -> String -> Payload [Param] filePart :: String -> FilePath -> IO (Payload [Part])
```

注意：

+   第一个函数返回一个`Payload [Param]`

+   第二个返回一个`Payload [Part]`

幻影参数使这些*类型不同*。

+   在每种情况下，运行时表示是相同的。

+   编译器通过防止我们意外混合两者。

## 代码片段

请为下面的`addParams`写一个主体。

```
instance Monoid (Payload [Param]) where mempty = NoPayload mappend = addParams
```

下载你需要的代码：

```
curl -L http://cs240h.scs.stanford.edu/PayloadPhantom.hs
```

你有五分钟。

## 让这一切都起作用

我们为创建`Payload`值有一个受限的公共 API。

```
param :: String -> String -> Payload [Param] filePart :: String -> FilePath -> IO (Payload [Part]) fileString :: String -> Maybe FilePath -> String -> (Payload [Part])
```

我们如何强制执行这一点？

我们导出了类型`Part`的*名称*，但*不导出任何构造函数*。

## 导出一个类型

下面的`(..)`表示“导出类型`Part`及其所有构造函数”。

```
module PayloadPhantom ( Part(..) {- ... trimmed out ... -} ) where
```

## 导出一个类型

下面的`(..)`表示“导出类型`Part`及其所有构造函数”。

```
module PayloadPhantom ( Part(..) {- ... trimmed out ... -} ) where
```

注意下面我们省略了`(..)`，表示“导出类型`Payload`，但*不导出任何构造函数*”。

```
module PayloadPhantom ( Part(..) , Payload -- no constructors {- ... trimmed out ... -} ) where
```

## 导出一个类型

下面的`(..)`表示“导出类型`Part`及其所有构造函数”。

```
module PayloadPhantom ( Part(..) {- ... trimmed out ... -} ) where
```

所以我们导出`Payload`类型，*只有*我们定义和控制的函数（“智能构造函数”）来构造这种类型的值。

```
module PayloadPhantom ( Part(..) , Payload -- no constructors , param , filePart , fileString {- ... trimmed out ... -} ) where
```

## 尝试一下

在`ghci`中：

```
ghci> param "foo" "bar" <> param "baz" "quux" Params [("foo","bar"),("baz","quux")]
```

这使用了我从`Data.Monoid`中喜欢的运算符：

```
(<>) :: Monoid m => m -> m -> m (<>) = mappend
```

如果我们尝试这样做，我们会得到什么？

```
param "foo" "bar" <> fileString "baz" Nothing "quux"
```

## 最后的幺半群

以下哪些情况应该写`Monoid`实例？

```
data Payload a = NoPayload | Raw ContentType String | Params [Param] | FormData [Part] deriving (Show)
```

## 为什么这么在意幺半群？

幺半群有许多优点：

+   简单

+   客户容易使用

+   强迫你早期解决 API 设计问题

## 没有单位的幺半群

喜欢抽象代数的方法吗？

Hackage 上的一个名为`semigroups`的包为我们提供了没有单位操作的幺半群：半群。

唉：

+   `Monoid`类型是在`semigroups`包之前开发的

+   这两者应该有关联，但由于历史原因，它们并没有

## 原则

为什么要关心幻影类型和幺半群？

+   我们想要构建尽可能简单正确的库

幺半群帮助我们专注于简单性。

幻影类型使得构建 API 更容易，编译器可以防止绝对错误的行为。

## 可变变量

我们已经看到了非常方便的`MVar`类型，它表示一个“阻塞可变盒子”：我们可以放入一个值或取出一个值，但如果放入时已满或取出时为空，我们将被阻塞。

尽管`MVar`是行业中最快的阻塞并发结构（它在不到十二秒的时间内完成了 Kessel 跑道！），但我们并不总是希望阻塞语义。

对于需要*非*阻塞更新的情况，有`IORef`类型，它提供了可变引用。

```
import Data.IORef newIORef :: a -> IO (IORef a) readIORef :: IORef a -> IO a writeIORef :: IORef a -> a -> IO () modifyIORef :: IORef a -> (a -> a) -> IO ()
```

## 管理变异

应用程序编写者经常面临这样的问题：

+   我有一个大型应用程序，其中的部分需要在运行时由管理员调整其行为。

当然，解决这种问题的方法有很多种。

让我们考虑一个使用配置数据片段引用的情况。

在`IO`单子中执行的任何代码，如果知道配置引用的名称，都可以检索当前配置：

```
curCfg <- readIORef cfgRef
```

麻烦的是，不规范的代码显然也可能*修改*当前配置，并让我们陷入调试噩梦。

## 幻影类型来拯救！

让我们创建一种新类型的可变引用。

我们使用幻影类型`t`来静态跟踪代码是否被允许修改引用。

```
import Data.IORef newtype Ref t a = Ref (IORef a)
```

记住，我们在这里使用`newtype`意味着`Ref`类型仅在编译时存在：它不会产生*任何*运行时成本。

由于我们使用了幻影类型，我们甚至不需要访问控制类型的值：

```
data ReadOnly data ReadWrite
```

我们已经处于一个良好的位置！我们不仅创建了编译器强制执行的访问控制，而且它将*零*运行时成本。

## 创建一个可变引用

要创建一个新引用，我们只需确保它具有正确的类型。

```
newRef :: a -> IO (Ref ReadWrite a) newRef a = Ref `fmap` newIORef a
```

## 读取和写入可变引用

由于我们希望能够读取只读和读写引用，因此在为`readRef`编写类型签名时不需要提及访问模式。

```
readRef :: Ref t a -> IO a readRef (Ref ref) = readIORef ref
```

当然，只有编译器可以通过类型系统静态证明代码具有写访问权限时，代码才能写入引用。

```
writeRef :: Ref ReadWrite a -> a -> IO () writeRef (Ref ref) v = writeIORef ref v
```

## 将引用转换为只读

这个函数允许我们将任何类型的引用转换为只读引用：

```
readOnly :: Ref t a -> Ref ReadOnly a readOnly (Ref ref) = Ref ref
```

为了防止客户端将只读引用提升为读写引用，我们*不*提供相反方向的函数。

我们还在源文件顶部使用熟悉的构造函数隐藏技术：

```
module Ref ( Ref, -- export type ctor, but not value ctor newRef, readOnly, readRef, writeRef ) where
```

## 进一步阅读

一篇*非常*好的阅读：

+   [使用单子进行数据分析](http://twdkz.wordpress.com/2013/05/31/data-analysis-with-monoids/)

用于 MapReduce 的单子：

+   [Google 的 MapReduce 编程模型---再探](http://userpages.uni-koblenz.de/~laemmel/MapReduce/paper.pdf)
