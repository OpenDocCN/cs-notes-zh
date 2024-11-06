# 你好，世界

我是 Bryan O'Sullivan。

我在 Facebook 工作。

之前，我创办了一家公司，其中一半产品是用 Haskell 构建的。

我写了一本关于 Haskell 的书。

我写了一些 Haskell 库。

## 让我们谈谈测试

有任何教授曾经和你谈过测试吗？

## 工业中的测试

对于测试软件，有几种“最先进”的方法：

+   Excel 电子表格上满满的手工操作（我没有编造这个）

+   单元测试

+   集成测试

+   模糊测试

## 我对什么感兴趣？

今天，我想谈谈单元测试及其更有趣的后代。

无耻地从维基百科借鉴：

```
public class TestAdder { public void testSum() { Adder adder = new AdderImpl(); assert(adder.add(1, 1) == 2); assert(adder.add(1, 2) == 3); assert(adder.add(2, 2) == 4); assert(adder.add(0, 0) == 0); assert(adder.add(-1, -2) == -3); assert(adder.add(-1, 1) == 0); assert(adder.add(1234, 988) == 2222); } }
```

## 问题出在哪里？

计算下面的测试用例数量。

```
public class TestAdder { public void testSum() { Adder adder = new AdderImpl(); assert(adder.add(1, 1) == 2); assert(adder.add(1, 2) == 3); assert(adder.add(2, 2) == 4); assert(adder.add(0, 0) == 0); assert(adder.add(-1, -2) == -3); assert(adder.add(-1, 1) == 0); assert(adder.add(1234, 988) == 2222); } }
```

好吧，不要。是 7。

## 单元测试的限制

单元测试只在一定程度上有用。

你的耐心和想出恶劣边界情况的能力是非常有限的。

最好明智地使用它们。

但是怎么做呢？

## 外包

对于耐心，我们有计算机。

对于恶劣的边界情况，我们有随机数生成器。

让我们把它们用起来。

## 一个简单的例子：UTF-16 编码

UTF-16 是一种 Unicode 编码，它：

+   获取一个*代码点*（一个 Unicode 字符）

+   将其转换为 1 或 2 个 16 位*代码单元*

变长编码：

+   0x10000 以下的代码点被编码为单个代码单元

+   在 0x10000 及以上，两个代码单元

## 编码单个代码点

我们知道 `Char` 表示一个 Unicode 代码点。

`Word16` 类型表示一个 16 位值。

```
import Data.Word (Word16)
```

`encodeChar` 的类型签名应该是什么？

```
encodeChar :: ???
```

## 基本情况很容易

我们可以很容易地将单代码单元的情况转换为一些 Haskell，使用一些方便的函数。

```
import Data.Char (ord) ord :: Char -> Int fromIntegral :: (Integral a, Num b) => a -> b
```

我们使用 `fromIntegral` 将 `Int` 转换为 `Word16`，因为 Haskell 不会为我们明确强制转换。

```
encodeChar :: Char -> [Word16] encodeChar x | w < 0x10000 = [fromIntegral w] where w = ord x
```

## 两个代码单元的情况

要编码大于 0x10000 的代码点，我们需要一些新的位操作函数。

```
import Data.Bits ((.&.), shiftR)
```

`.&.` 运算符给我们位运算*与*，而 `shiftR` 是右移。

```
encodeChar :: Char -> [Word16] encodeChar x | w < 0x10000 = [fromIntegral w] | otherwise = [fromIntegral a, fromIntegral b] where w = ord x a = ((w - 0x10000) `shiftR` 10) + 0xD800 b = (w .&. 0x3FF) + 0xDC00
```

## 基本测试

如果你想要单元测试，`HUnit` 是你需要的包。

```
import Test.HUnit (assertEqual) testASCII = assertEqual "ASCII encodes as one code unit" 1 (length (encodeChar 'a'))
```

## 一个糟糕的测试

让我们故意写一个虚假的测试。

```
badTest = do assertEqual "sestertius encodes as one code unit" 1 (length (encodeChar '\x10198'))
```

如果我们在 `ghci` 中运行这个：

```
ghci> badTest *** Exception: HUnitFailure "sestertius encodes as one code unit\nexpected: 1\n but got: 2"
```

不太美观，但有效。

## 但等等：单元测试？

所以我只是写了单元测试，现在我要向你展示如何编写它们？

好吧，我们可以推广超出单元测试的限制。

## 一个更大图景的代理

我们真正想要这个测试做什么？

```
testASCII = do assertEqual "ASCII encodes as one code unit" 1 (length (encodeChar 'a'))
```

我们真的在断言*每个* ASCII 代码点都编码为单个代码单元。

```
testOne char = do assertEqual "ASCII encodes as one code unit" 1 (length (encodeChar char))
```

## 嗯：更好了吗？

如果我们参数化我们的测试会怎样：

```
testOne char = do assertEqual "ASCII encodes as one code unit" 1 (length (encodeChar char))
```

并从一个测试框架中驱动它：

```
testASCII = mapM_ testOne ['\0'..'\127']
```

## 盘点

这更好，因为我们的原始测试被泛化了。

这也更糟，因为我们正在详尽列举每一个测试输入。

我们在这里得以成功是因为 Unicode 很小，计算机很快。

但这是事情的*原则*：自动化更好！

## 进入 QuickCheck

忘掉 `HUnit`，这是我们将专注的包。

```
import Test.QuickCheck prop_encodeOne c = length (encodeChar c) == 1
```

在 `ghci` 中：

```
ghci> quickCheck prop_encodeOne +++ OK, passed 100 tests.
```

## 刚刚发生了什么？

为什么 `quickCheck` 会这样说：

```
+++ OK, passed 100 tests.
```

它做了以下事情：

+   *生成*了 100 个随机值给我们

+   将每个传递给 `prop_encodeOne`

+   确保每个测试都通过了

## 现在我头疼了

让我们回顾一下我们的“测试函数”：

```
prop_encodeOne c = length (encodeChar c) == 1
```

这是*非常可疑的*。

我们知道 `encodeChar` 有时会产生长度为 2 的列表。

那么我们的 100 次测试为什么通过了？

## 从小开始

对于大多数类型，QuickCheck 操作的一个方便的假设是“小”测试用例比大的更有用。

当小的随机输入测试通过时，它会生成“更大”的输入。

只进行 100 次测试，我们几乎不可能生成一个编码为两个代码单元的代码点。

## 幕后：生成值

QuickCheck 到底是如何做到的？

它需要能够生成随机值。

它通过类型类实现这一点。

```
-- Generator type. data Gen a -- The set of types for which we -- can produce random values. class Arbitrary a where  arbitrary :: Gen a
```

## 幕后：一些机制

```
-- Generate a random value within a range. choose :: Random a => (a,a) -> Gen a instance Arbitrary Bool where arbitrary = choose (False,True) instance Arbitrary Char {- ... -}
```

## 幕后：可测试的事物

```
-- Simply protection for a Gen. data Property = MkProperty (Gen a) -- The set of types that can be tested. class Testable prop -- The instance bodies are not interesting. instance Testable Bool instance (Arbitrary a, Show a, Testable prop) => Testable (a -> prop)
```

上面的两个实例至关重要。

## 这是如何工作的？

让我们用一个类型签名来编写我们的测试函数。

```
prop_encodeOne :: Char -> Bool prop_encodeOne c = length (encodeChar c) == 1
```

而 `quickCheck`：

```
quickCheck :: Testable prop => prop -> IO ()
```

## 再看一遍

如果 `quickCheck` 接受 `prop_encodeOne`，那么后者必须是 `Testable` 的一个实例。

```
prop_encodeOne :: Char -> Bool quickCheck :: Testable prop => prop -> IO ()
```

但是如何？通过这两个实例。

```
-- Satisfied by the result type instance Testable Bool -- Satisfied by the argument and result instance (Arbitrary a, Show a, Testable prop) => Testable (a -> prop)
```

## 长话短说

如果我们向 `quickCheck` 传递一个函数，那么：

+   只要它的参数都是 `Arbitrary` 和 `Show` 的实例

+   *并且*只要其结果是 `Testable` 的一个实例

*然后* `quickCheck` 可以：

+   *生成*所有必要类型的*任意*值，

+   对这些值运行我们的测试，

+   并确保我们的测试始终通过

## 那又怎样？

我们仍然有一个失败的测试！

`quickCheck` 告诉我们它总是通过---但实际上不应该！

为什么？我们必须阅读源代码。

```
module Test.QuickCheck.Arbitrary where instance Arbitrary Char where arbitrary = chr `fmap` oneof [choose (0,127), choose (0,255)]
```

哦，太好了，QuickCheck 只会生成 8 位字符。

我们假设它最终会生成足够大的输入对于 `Char` 是错误的。

因此我们的测试永远不会失败。

多么...不幸啊！

## 编写一个新的 Arbitrary 实例

现在我们面临一个挑战。

我们想要一个几乎与 `Char` 相同但具有不同 `Arbitrary` 实例的类型。

要创建这样一种类型，我们使用 `newtype` 关键字。

```
newtype BigChar = Big Char deriving (Eq, Show)
```

这个类型被命名为 `BigChar`；它的构造函数被命名为 `Big`。

我们使用 `deriving` 来重用底层 `Char` 类型的 `Eq` 实例，并生成一个新的 `Show` 实例。

## 接下来呢？

我们想要能够详细说明这一点：

```
instance Arbitrary BigChar where arbitrary = {- ... what? ... -}
```

最高的 Unicode 代码点是 0x10FFFF。

我们想要在这个范围内生成值。

我们之前看到过这个：

```
-- Generate a random value within a range. choose :: Random a => (a,a) -> Gen a
```

## 随机值：困难的方式

为了使用 `choose`，我们必须使 `BigChar` 成为 `Random` 的一个实例。

这是一个冗长的做法：

```
import Control.Arrow (first) import System.Random instance Random BigChar where random = first Big `fmap` random randomR (Big a,Big b) = first Big `fmap` randomR (a,b)
```

## 随机值：更容易

如果我们想避免上一张幻灯片中的样板代码，我们可以使用一个技巧：

+   `GeneralizedNewtypeDeriving` 语言扩展

+   这使得 GHC 可以自动为我们派生一些非标准的类型类实例，例如 `Random`。

```
{-# LANGUAGE GeneralizedNewtypeDeriving #-} import System.Random newtype BigChar = Big Char deriving (Eq, Show, Random)
```

+   我们所做的一切只是在上面的 `deriving` 子句中添加了 `Random`。

+   正如其名称所示，这仅适用于 `newtype` 关键字。

## 我们的实例，以及重新运行

一个带有主体的实例：

```
instance Arbitrary BigChar where arbitrary = choose (Big '0',Big '\x10FFFF')
```

一个解包 `BigChar` 值的新测试：

```
prop_encodeOne3 (Big c) = length (encodeChar c) == 1
```

让我们试一试：

```
ghci> quickCheck prop_encodeOne3 *** Failed! Falsifiable (after 1 test): Big '\317537'
```

太棒��！我们的失败的测试立即失败了...

...但它给了我们一个*反例*，一个我们的测试函数可靠失败的输入！

## QuickCheck 的魔力

这里的美妙之处有几个方面：

+   我们编写一个简单的 Haskell 函数，接受一些输入并返回一个`Bool`

+   QuickCheck 为我们生成随机测试用例，并测试我们的函数

+   如果一个测试用例失败，它会告诉我们输入是什么

## 那又怎样？

单元测试方式：

+   一堆单元测试，是对一个主题的小变化

QuickCheck 方式：

+   你期望普遍成立的一个属性

+   自动、随机生成的测试输入

+   帮助您找出错误的反例

## 还有什么？

当测试失败时，随机输入存在问题：

+   它们通常是*大的*。

+   大的东西对人类来说很难处理。

+   大值通常需要更长时间来查看。

从一个随机失败的输入开始：

+   我们想找到导致测试失败的*最小*输入。

QuickCheck 称之为*缩小*。

## 微型实验室：缩小一个 BigChar

获取以下源文件：

```
curl -O http://cs240h.cs.stanford.edu/ShrinkChar.hs
```

使用`ghci`进行一些探究，为`shrinkChar`编写一个主体。

```
instance Arbitrary BigChar where arbitrary = choose (Big '0',Big '\x10FFFF') shrink (Big c) = map Big (shrinkChar c) -- Write a body for this. shrinkChar c = undefined
```

你有 5 分钟。

## 生成与过滤值

这里有两种不同的生成测试值的方法。

首先，直接生成它们（看看第 2 行）：

```
prop_encodeOne2 = do c <- choose ('\0', '\xFFFF') return $ length (encodeChar c) == 1
```

其次，生成任意值，但*过滤*以便只得到有意义的值：

```
-- These two are basically the same, modulo verbosity. prop_encodeOne4 (Big c) = (c < '\x10000') ==> length (encodeChar c) == 1 prop_encodeOne5 = do Big c <- arbitrary `suchThat` (< Big '\x10000') return $ length (encodeChar c) == 1
```

## 生成与过滤

通常更有效的方法是仅生成您需要的值，不进行任何过滤。

有时，通过过滤来识别好的值（通过过滤）比想出如何生成它们更容易。

如果 QuickCheck 必须生成太多失败`suchThat`或其他过滤器的值，它将放弃，并且可能不会运行您想要的测试数量。

+   为了效率*和*确保 QuickCheck 能够生成足够的值进行测试，值得尝试只生成好的值。

## 迷你实验室：更多代码！

获取以下源代码：

```
curl -O http://cs240h.cs.stanford.edu/Utf16.hs
```

写一个`decodeUtf16`的定义：

```
decodeUtf16 :: [Word16] -> [Char]
```

决定一些 QuickCheck 测试，编写它们，并运行它们。

你有 15 分钟。

## 调整测试的大小

测试数据生成器有一个隐含的大小参数，隐藏在`Gen`类型中。

QuickCheck 从生成小的测试用例开始；随着测试的进行，它会增加大小。

“大小”的含义是特定于`Arbitrary`实例的���求。

+   列表的`Arbitrary`实例将其解释为“任意值列表的最大长度”。

我们可以使用`sized`函数找到当前大小，并使用`resize`在本地修改它：

```
sized :: (Int -> Gen a) -> Gen a resize :: Int -> Gen a -> Gen a
```

## 提升

我们现在应该对`Functor`类很熟悉了：

```
class Functor f where  fmap :: (a -> b) -> f a -> f b
```

这将一个纯函数“提升”到函子`f`中。

一般来说，“提升”将一个概念转化为在不同（有时更一般）环境中工作的方式。

例如，我们也可以使用`Monad`类定义函数的提升：

```
liftM :: (Monad m) => (a -> b) -> m a -> m b liftM f action = do b <- action return (f b)
```

## fmap 和 liftM

注意类型签名之间的相似之处：

```
fmap :: (Functor f) => (a -> b) -> f a -> f b liftM :: (Monad m) => (a -> b) -> m a -> m b
```

所有的`Monad`实例都可能是`Functor`的实例。理想情况下，它们应该相互定义：

```
class (Functor m) => Monad m where {- blah blah -}
```

由于历史原因，这两个类是分开的，因此我们为它们编写单独的实例，然后重用代码：

```
instance Monad MyThingy where {- whatever -} instance Functor MyThingy where fmap = liftM
```

## 为什么会出现这样的离题？

原来将纯函数提升到单子中是非常常见的。

事实上，`Control.Monad`为我们定义了一堆额外的组合子。

```
liftM2 :: (Monad m) => (a -> b -> c) -> m a -> m b -> m b liftM2 f act1 act2 = do a <- act1 b <- act2 return (f a b)
```

这些组合子一直延伸到`liftM5`。

看起来熟悉吗？有用吗？

## 一个更紧凑的任意实例

之前：

```
data Point a = Point a a instance (Arbitrary a) => Arbitrary (Point a) where arbitrary = do x <- arbitrary y <- arbitrary return (Point x y)
```

之后：

```
import Control.Monad (liftM2) instance (Arbitrary a) => Arbitrary (Point a) where arbitrary = liftM2 Point arbitrary arbitrary
```

## 微型实验室：收缩一个点

QuickCheck 为我们提供了收缩元组的机制。

利用这个机制来收缩一个`Point`。

```
curl -O http://cs240h.cs.stanford.edu/TestPoint.hs
```

花 3 分钟。

```
import Control.Monad import Test.QuickCheck data Point a = Point a a deriving (Eq, Show) instance (Arbitrary a) => Arbitrary (Point a) where arbitrary = liftM2 Point arbitrary arbitrary -- TODO: provide a body for shrink shrink = undefined
```

## 测试递归数据类型

假设我们有一个树类型：

```
data Tree a = Node (Tree a) (Tree a) | Leaf a deriving (Show)
```

这里是一个明显的`Arbitrary`实例：

```
instance (Arbitrary a) => Arbitrary (Tree a) where arbitrary = oneof [ liftM Leaf arbitrary , liftM2 Node arbitrary arbitrary ]
```

`oneof`组合子随机选择一个生成器。

```
oneof :: [Gen a] -> Gen a
```

## 怎么了，医生？

潜在的麻烦：

+   这个生成器可能根本不会终止！

+   它可能会产生*巨大*的树。

我们可以使用`sample`函数生成并打印一些任意数据。

```
sample :: (Show a) => Gen a -> IO ()
```

这有助于我们探究发生了什么。

## 一个更安全的实例

这就是尺寸机制拯救的地方。

```
instance (Arbitrary a) => Arbitrary (Tree a) where arbitrary = sized tree tree :: (Arbitrary a) => Int -> Gen (Tree a) tree 0 = liftM Leaf arbitrary tree n = oneof [ liftM Leaf arbitrary , liftM2 Node subtree subtree ] where subtree = tree (n `div` 2)
```

## 这一切的目的是什么

QuickCheck 相当不错。花时间学会如何使用它。

学会很好地使用它比单元测试更难，但回报丰厚。

此外：

+   我们真的希望看到您在未来的实验和最终项目中提供 QuickCheck 测试。

愉快！
