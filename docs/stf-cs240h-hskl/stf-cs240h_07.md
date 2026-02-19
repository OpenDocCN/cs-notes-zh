# 函子，单子，等等

在我们关于测试的讲座中，我们与谦卑的函子交谈。

```
class Functor f where  fmap :: (a -> b) -> f a -> f b
```

但我们对函子的直觉有多好？

## 对列表的函子

请告诉我以下内容计算什么：

```
fmap (+1) [1,2,3]
```

## 对列表的函子

请告诉我以下内容计算什么：

```
import Data.Char fmap toUpper "qwertyuiop"
```

## 对`Maybe`的函子

让我们避免与标准的`Functor`类发生名称冲突：

```
class MyFunctor f where  myfmap :: (a -> b) -> f a -> f b
```

请为`Maybe`编写一个`MyFunctor`实例。

你有 2 分钟。

## 对`Maybe`的函子

让我们避免与标准的`Functor`类发生名称冲突：

```
class MyFunctor f where  myfmap :: (a -> b) -> f a -> f b
```

这是一个`Maybe`的`MyFunctor`实例。

```
instance MyFunctor Maybe where myfmap _ Nothing = Nothing myfmap f (Just a) = Just (f a)
```

## 对单位元的函子

请向我口述一个`Identity`的`MyFunctor`实例。

```
newtype Identity a = Identity a
```

（你可以在`Data.Functor.Identity`中找到这种类型。）

## 函子的一种观点

假设我们将函子看作一个容器。

我们知道函子对容器内部的事物有什么影响？

容器本身的结构如何？

## 构造一个元组

你可能还没有遇到“成对”运算符：

```
(,) :: a -> b -> (a, b)
```

给定两个参数，它返回由这些参数组成的对。

## 对对的部分应用

由于`(,)`是一个运算符，我们可以用括号将其包围以将其用作函数。

```
ghci> :type (,) 'X' True (,) 'X' True :: (Char, Bool)
```

典型的 Haskell 风格，我们可以部分应用函数以产生另一个函数：

```
ghci> :type (,) 'X' (,) 'X' :: b -> (Char, b)
```

## 类型签名和元组

好的，我们可以在前缀位置使用`(,)`作为一个函数。

我们也可以将`(,)`写成*类型构造函数*。

```
foo :: b -> (,) Char b foo b = (,) 'X' b
```

这意味着*完全相同*的签名：

```
foo :: b -> (Char, b)
```

## 对元组的函子

对于对的`MyFunctor`实例应该是什么样子的？

```
instance MyFunctor ((,) a) where {- ... -}
```

记住，对于一个类型成为`MyFunctor`的实例，我们需要一个自由类型参数：

```
class MyFunctor f where  myfmap :: (a -> b) -> f a -> f b
```

按照惯例，我们选择对的第二个元素在我们的`MyFunctor`实例中是自由的。

`myfmap`应该是什么样子？

## 变得更奇怪

我们的函子作为容器的隐喻有多有用？

回想一下神秘的`Identity`类型。

```
newtype Identity a = Identity a
```

由于这是一个`newtype`，它没有运行时表示。

严格来说，它并不是真正的容器：

+   除了类型系统机制，没有什么“外部”可以“内部”。

## 为什么要谈论前缀运算符？

我提到`(,)`作为前缀运算符有一个目的。

我们可以用`(->)`运算符描述函数做同样的事。

```
foo :: (->) Char Bool foo c = isUpper c
```

由于我们能够为对写一个`MyFunctor`实例：

```
instance MyFunctor ((,) a) where myfmap f (a, b) = (a, f b)
```

我们能为函数做同样的事吗？

## 函数的函子

```
instance MyFunctor ((,) a) where myfmap f (a, b) = (a, f b)
```

有人想试试吗？

```
instance MyFunctor ((->) a) where {- ... -}
```

## 函数的函子

定义并不难想出：

```
instance MyFunctor ((->) a) where myfmap f g = \x -> f (g x)
```

但这意味着什么？

+   显然*不*是一个容器。

## 对 IO 的函子

我们已经在`IO`的上下文中涉及了函子。

```
readFile "/etc/passwd"
```

这执行一个真实世界的动作，并给我们一个`String`。

```
(length . lines) `fmap` readFile "/etc/passwd"
```

这执行相同的真实世界动作，并给我们...*什么*？

## 函子定律

映射恒等函数对结果没有影响。

```
fmap id === id
```

映射两个函数的组合与组合相同函数的映射是相同的。

```
fmap (g . h) = (fmap g) . (fmap h)
```

## 重新审视提升

编写`fmap`类型的标准方式可能有点晦涩：

```
class Functor f where  fmap :: (a -> b) -> f a -> f b
```

## 重新审视提升

Haskell 中的函数总是*柯里化*的，所以 `fmap` “实际上是”一个参数的函数，返回另一个函数。

让我们加上括号以澄清这一点。

```
class Functor f where  fmap :: (a -> b) -> (f a -> f b)
```

它将第一个参数从普通函数提升到在这个一切都被 `f` 遮蔽的宇宙中运行的函数。

## 为什么要专注于函子？

你会在 Haskell 中到处看到这些该死的东西。

除了 `Monoid`，`Functor` 是 Haskell 中最简单的抽象之一。

`(->) a` 是一个 `Functor`（但*不是*一个容器）是*无价的*：

+   它让我们不再使用限制性的容器为中心的隐喻来思考这些抽象。

## 给 `f` 一个名字

```
class Functor f where  fmap :: (a -> b) -> (f a -> f b)
```

因此容器只是一个训练轮的隐喻。

用一个名字来泛指这个 `f` 东西仍然是有帮助的。

我们将其称为*上下文*。

## 上下文

`[]` 函子：

+   上下文是一个列表。

`(->) a` 函子：

+   我们的上下文是一个具有类型 `a` 的第一个参数的函数（一个“只读环境”）。

`IO` 函子：

+   我们的上下文是可能具有真实世界影响的计算。

## Applicative

这是我们在表达上的下一个阶梯。

```
class Functor f => Applicative f where  pure :: a -> f a  (<*>) :: f (a -> b) -> f a -> f b
```

`pure` 函数接受一个值并将其提升到我们的新上下文中。

## “applicative”一词的来源

`(<*>)` 怎么样？

考虑它与 `fmap` 和 `($)` 的相似之处。

```
(<*>) :: f (a -> b) -> f a -> f b fmap :: (a -> b) -> f a -> f b ($) :: (a -> b) -> a -> b
```

*它们显然都有关联！*

+   `($)` 是函数应用

+   `fmap` 是函数应用提升到函子

+   `(<*>)` 是函数应用提升到函子，但初始函数也被包裹在我们的上下文 `f` 中

这就是“applicative”这个名字的起源。

## Applicative laws

就像单子和函子一样，`Applicative` 的实例也必须遵循一些规律。

在这种情况下，有 4 条规律。

如果你感兴趣，可以在 [Typeclassopedia](http://www.haskell.org/haskellwiki/Typeclassopedia#Laws_2) 上查看。

## 只有一个 `Applicative` 实例

```
class Functor f => Applicative f where  pure :: a -> f a  (<*>) :: f (a -> b) -> f a -> f b
```

这将让我们感受到 `Applicative` 类的风格。

```
instance Applicative Maybe where pure x = Just x
```

`(<*>)` 的实现应该是什么样的？

```
-- (<*>) :: f (a -> b) -> f a -> f b (<*>) :: Maybe (a -> b) -> Maybe a -> Maybe b
```

花 2 分钟写下你自己的。

## 只有一个 `Applicative` 实例

```
class Functor f => Applicative f where  pure :: a -> f a  (<*>) :: f (a -> b) -> f a -> f b
```

这将让我们感受到 `Applicative` 类的风格。

```
instance Applicative Maybe where pure x = Just x
```

`(<*>)` 的实现应该是什么样的？

```
(<*>) :: Maybe (a -> b) -> Maybe a -> Maybe b Just f <*> Just x = Just (f x) _ <*> _ = Nothing
```

## 进一步研究

如果你想对 `Applicative` 有一些很好的理解：

+   写出列表、`Identity` 和 `(->) a` 的实例

附加材料：

```
newtype MyConst a b = MyConst a
```

为上面的 `MyConst` 类型编写 `Functor` 和 `Applicative` 实例。

## 为什么这么麻烦？

这是一个小小的 `Applicative` 驱动的解析器，用于 URL 编码的字节，如 `%27`。

```
import Control.Applicative import Data.Char (chr) import Numeric (readHex) import Text.Parsec (char, hexDigit) import Text.Parsec.String (Parser) hexChar :: Parser Char hexChar = char '%' *> (combo <$> hexDigit <*> hexDigit) where combo a b = case readHex [a,b] of [(n,"")] -> chr n _ -> error "wat"
```

这取决于：

```
-- Sequence two actions, discarding the result of the first. (*>) :: Applicative f => f a -> f b -> f b -- You'll see this everywhere. (<$>) = fmap
```

## 深入探讨

让我们解析一个完整的 `application/x-www-form-urlencoded` 字符串。

它们看起来像这样：

```
name=bryan+o%27sullivan&city=san+francisco
```

顶层解析器：

```
query = pair `sepBy` char '&'
```

我们稍后会重新讨论 `sepBy`。

```
-- Zero or more elements, separated by a separator. sepBy :: Alternative f => f a -> f sep -> f [a]
```

首先，我们必须理解 `Alternative`。

## `Alternative` 类

这个类将单子与应用函子结合起来：

```
class Applicative f => Alternative f where  empty :: f a  (<|>) :: f a -> f a -> f a
```

`empty` 对应于 `mempty`。

+   在解析时，把它看作“解析失败”。

`(<|>)` 对应于 `mappend`/`(<>)`。

+   在解析时，把它看作“尝试第一个解析；如果失败，尝试第二个”。

## 一些方便的组合子

注意

```
-- Zero or more elements, separated by a separator. sepBy :: Alternative f => f a -> f sep -> f [a] sepBy p sep = sepBy1 p sep <|> pure [] -- One or more elements, separated by a separator. sepBy1 :: Alternative f => f a -> f sep -> f [a] sepBy1 p sep = (:) <$> p <*> many (sep *> p) many :: Alternative f => f a -> f [a]
```

## 更多解析

```
pair :: Parser (String, Maybe String) pair = (,) <$> many1 urlChar <*> optional (char '=' *> many urlChar) urlChar = oneOf urlBaseChars <|> hexChar <|> ' ' <$ char '+'
```

新的组合子：

```
optional :: Alternative f => f a -> f (Maybe a) -- Replace all locations in the input with the same value. (<$) :: Functor f => a -> f b -> f a
```

## 我们完整的解析器

这段代码非常紧凑和可读！

```
query = pair `sepBy` char '&' pair :: Parser (String, Maybe String) pair = (,) <$> many1 urlChar <*> optional (char '=' *> many urlChar) urlChar = oneOf urlBaseChars <|> hexChar <|> ' ' <$ char '+' hexChar :: Parser Char hexChar = char '%' *> (eval <$> hexDigit <*> hexDigit) where eval a b = case readHex [a,b] of [(n,"")] -> chr n _ -> error "wat" urlBaseChars = ['a'..'z']++['A'..'Z']++['0'..'9']++"$-_.!*'(),"
```

## 最后，进入`Monad`

每个`Applicative`都是一个`Functor`。

每个`Monad`都是一个`Applicative`。

```
class Monad m where  return :: a -> m a  (>>=) :: m a -> (a -> m b) -> m b
```

`return`与`pure`相同。

那么`(>>=)`（"bind"）呢？

它在我们的思维世界中的位置是什么？

## 一个方便的变体

有一个名为`(=<<)`的标准函数，它与`(>>=)`完全相同，但其参数顺序被翻转。

```
(>>=) :: Monad m => m a -> (a -> m b) -> m b (=<<) :: Monad m => (a -> m b) -> m a -> m b
```

我们为什么要在意呢？

## 让我们重新审视之前的幻灯片

还记得这个吗？

```
(<*>) :: Applicative f => f (a -> b) -> f a -> f b fmap :: Functor f => (a -> b) -> f a -> f b ($) :: (a -> b) -> a -> b
```

这些都是将函数应用于值的不同方式。

## 让我们重新审视之前的幻灯片

一个小的变化：添加`(=<<)`。

```
(=<<) :: Monad m => (a -> m b) -> m a -> m b (<*>) :: Applicative f => f (a -> b) -> f a -> f b fmap :: Functor f => (a -> b) -> f a -> f b ($) :: (a -> b) -> a -> b
```

所以，实际上，`(>>=)`运算符只是另一种应用运算符，但是它翻转的参数顺序使这一点变得模糊。

## `Functor`和`Applicative`不能做什么

考虑带有函子和应用函子的应用场景：

```
(<*>) :: Applicative f => f (a -> b) -> f a -> f b fmap :: Functor f => (a -> b) -> f a -> f b
```

我们如何确保它们只能在容器的*元素*上操作？

+   它们的函数参数*完全看不到或影响*`f`。

+   因此，它们*必须*对容器的封闭结构（或计算上下文，或其他任何东西）毫不在意。

## 从`Applicative`到`Monad`

`Monad`的关键在于`a -> m b`函数可以接受一个普通的 Haskell 值，并*用它来决定*返回什么`m b`：

+   它能够影响容器的结构，改变上下文，启动核弹，或者其他什么。

```
(=<<) :: Monad m => (a -> m b) -> m a -> m b (<*>) :: Applicative f => f (a -> b) -> f a -> f b
```

与`Applicative`相比，`Monad`既更强大*又*更难理解。

## 这些类的现在和将来

`Applicative`和`Functor`是相关的。 `Monad`与其他两者无关，这是历史的偶然。

这将随着 GHC 7.10 改变。

## 一个有用的经验法则

总是尽量使用*最不强大的*抽象。

优先使用`Applicative`而不是`Monad`。

优先使用`Functor`而不是`Applicative`。

(当然，除非你不能。)

为什么？

+   抽象越不强大，理解其行为就越容易。

+   对你和你的用户来说，执行踩脚事件变得更加困难。
