# 将元组转换为列表

+   假设你想要将一对`Strings`转换为列表

    ```
    pairToStringList :: (Show a, Show b) => (a, b) -> [String] pairToStringList (a, b) = [show a, show b]
    ```

    ```
    *Main> pairToStringList (True, Just 3) ["True","Just 3"]
    ```

+   现在假设你想要将一对`Enum`转换为`Int`列表

    ```
    pairToIntList :: (Enum a, Enum b) => (a, b) -> [Int] pairToIntList (a, b) = [fromEnum a, fromEnum b]
    ```

+   我们能否将这个函数泛化？想要说：

    ```
    pairToList conv (a, b) = [conv a, conv b] pairToList show (True, Just 3) -- error
    ```

    +   不幸的是，不能将*方法*作为参数传递，只能是*函数*

        ```
        pairToList :: (a -> b) -> (a, a) -> [b]
        ```

## 具有 fundeps 的多态性

+   让我们用一个*类*来表示特殊的多态方法

    ```
    {-# LANGUAGE MultiParamTypeClasses #-} {-# LANGUAGE FunctionalDependencies #-} {-# LANGUAGE FlexibleInstances #-} class Function f a b | f a -> b where  funcall :: f -> a -> b instance Function (a -> b) a b where funcall = id pairToList :: (Function f a c, Function f b c) => f -> (a, b) -> [c] pairToList f (a, b) = [funcall f a, funcall f b]
    ```

+   使用占位符单例类型来表示特定方法

    ```
    data ShowF = ShowF instance (Show a) => Function ShowF a [Char] where funcall _ = show data FromEnumF = FromEnumF instance (Enum a) => Function FromEnumF a Int where funcall _ = fromEnum
    ```

## `Function`的作用

+   现在单例类型就像方法参数一样：

    ```
    *Main> pairToList ShowF (True, 3) ["True","3"] *Main> pairToList FromEnumF (False, 7) [0,7]
    ```

+   现在，如果你想要将任意*n*-元组转换为列表怎么办？

    +   可以为通用元组折叠自动生成实例，例如：

    ```
    class TupleFoldr f z t r | f z t -> r where  tupleFoldr :: f -> z -> t -> r
    ```

    +   对于小元组效果还可以，但在 10 元组左右会出问题，需要更大的`-fcontext-stack`参数

+   不幸的是，我暂时没有编译时的技巧

    +   另一种方法是使用运行时类型信息（RTTI）

    +   RTTI 更容易理解，但会增加运行时开销和错误

    +   我们将在讲座结束时回到静态技巧

## [`DeriveDataTypeable`](http://www.haskell.org/ghc/docs/latest/html/users_guide/deriving.html#deriving-typeable) 扩展

+   Haskell 允许自动派生六个类

    +   `Show`, `Read`, `Eq`, `Ord`, `Bounded`, `Enum`

+   [`DeriveDataTypeable`](http://www.haskell.org/ghc/docs/latest/html/users_guide/deriving.html#deriving-typeable) 扩展添加了另外两个：`Typeable`，`Data`

    ```
    data MyType = Con1 Int | Con2 String deriving (Typeable, Data)
    ```

    +   这些类型以各种方式编码运行时类型信息

    +   `Data`要求内部类型（`Int`，`String`）也要有实例

    +   `Typeable`要求任何类型参数都要有实例

    ```
    -- MyTyCon only typeable when a is data MyTyCon a = MyTyCon a deriving (Typeable, Data)
    ```

    +   大多数标准库类型都有`Typeable`和`Data`实例

+   提供了被称为“scrap your boilerplate”的编程方法

    +   GHC 的支持由两篇论文描述：[[Boilerplate1]](http://research.microsoft.com/en-us/um/people/simonpj/papers/hmap/hmap.ps), [[Boilerplate2]](http://research.microsoft.com/en-us/um/people/simonpj/papers/hmap/gmap2.ps)

## [`Typeable`](http://hackage.haskell.org/packages/archive/base/latest/doc/html/Data-Typeable.html#t:Typeable) 类

+   `import Data.Typeable` 来获取`Typeable`类：

    ```
    class Typeable a where  typeOf :: a -> TypeRep -- Note: never evaluates argument data TypeRep -- Opaque, but instance of Eq, Ord, Show, Typeable
    ```

+   这使我们能够比较类型是否相等

    ```
    rtTypeEq :: (Typeable a, Typeable b) => a -> b -> Bool rtTypeEq a b = typeOf a == typeOf b
    ```

    ```
    *Main> rtTypeEq True False True *Main> rtTypeEq True 5 False
    ```

+   没什么了不起！

    +   我们难道不能在编译时使用`OverlappingInstances`来做到这一点吗？

    +   动态地进行这个操作不太激动人心，但是不同

    +   并且允许一个非常重要的函数...

## 类型转换

+   GHC 有一个名为[`unsafeCoerce`](http://hackage.haskell.org/packages/archive/base/latest/doc/html/Unsafe-Coerce.html#v:unsafeCoerce)的函数

    ```
    unsafeCoerce :: a -> b
    ```

    +   注意：它不只是返回⊥

    +   如果名称不吓到你，类型签名应该会

+   让我们使用`Typeable`来创建一个安全的`cast`函数

    ```
    cast :: (Typeable a, Typeable b) => a -> Maybe b cast a = fix $ \ ~(Just b) -> if typeOf a == typeOf b then Just $ unsafeCoerce a else Nothing
    ```

    ```
    *Main> cast "hello" :: Maybe String Just "hello" *Main> cast "hello" :: Maybe Int Nothing
    ```

    +   如果`typeOf`在两种不同类型上始终返回不同的`TypeRep`，则是安全的

    +   通过`deriving (Typeable)`保证；SafeHaskell 不允许手动实例

## 泛化转换

+   要转换单子计算等，使用泛化转换，`gcast`：

    ```
    import Data.Maybe (fromJust) gcast :: (Typeable a, Typeable b) => c a -> Maybe (c b) gcast ca = mcr where mcr = if typeOf (unc ca) == typeOf (unc $ fromJust mcr) then Just $ unsafeCoerce ca else Nothing  unc :: c x -> x unc = undefined
    ```

    ```
    *Main> fromJust $ gcast (readFile "/etc/issue") :: IO String "\nArch Linux \\r (\\n) (\\l)\n\n" *Main> fromJust $ gcast (readFile "/etc/issue") :: IO Int *** Exception: Maybe.fromJust: Nothing
    ```

+   注意在`gcast`的定义中未定义的函数`unc`

    +   常见的习惯用法--不会有问题，因为`typeOf`不是严格的

    +   回想一下上下文`Typeable b =>`就像一个隐藏的参数；通常使用带有类型签名的未定义函数来解包类型并获取字典

## 使用`Typeable`：`mkT`[[Boilerplate1]](http://research.microsoft.com/en-us/um/people/simonpj/papers/hmap/hmap.ps)

+   `mkT`（“创建转换”）在一个类型上的行为类似于`id`

    ```
    mkT :: (Typeable a, Typeable b) => (b -> b) -> a -> a
    ```

+   例子：

    ```
    newtype Salary = Salary Double deriving (Show, Data, Typeable) raiseSalary :: (Typeable a) => a -> a raiseSalary = mkT $ \(Salary s) -> Salary (s * 1.04)
    ```

    ```
    *Main> raiseSalary () () *Main> raiseSalary 7 7 *Main> raiseSalary (Salary 7) Salary 7.28
    ```

+   练习：实现`mkT`

    +   提示：函数类型`(->)`是`Typeable`，因此`Data.Typeable`导出：

    ```
    instance (Typeable a, Typeable b) => Typeable (a -> b) where ...
    ```

## 解决方案

```
mkT :: (Typeable a, Typeable b) => (b -> b) -> a -> a mkT f a = case cast f of Just g -> g a Nothing -> a
```

+   注意 Haskell 类型推断的魔力

    +   `g`应用于`a`，因此必须具有类型`a -> a`

    +   因此`cast f`必须具有类型`Maybe (a -> a)`

    +   因此编译器知道要使用`(b -> b)`的`Typeable`字典作为参数，以及`(a -> a)`的字典作为`cast`的返回

+   [[Jones]](http://web.cecs.pdx.edu/~mpj/thih/)详细解释了 Haskell 的类型推断

+   注意，更复杂的实现可以使用标准的`maybe`函数

    ```
    maybe :: b -> (a -> b) -> Maybe a -> b maybe b _ Nothing = b maybe _ f (Just a) = f a
    ```

    ```
    mkT :: (Typeable a, Typeable b) => (b -> b) -> (a -> a) mkT f = maybe id id $ cast f
    ```

## 使用`Typeable`：`mkQ`[[Boilerplate1]](http://research.microsoft.com/en-us/um/people/simonpj/papers/hmap/hmap.ps)

+   计算一个类型或返回默认值的函数：

    ```
    mkQ :: (Typeable a, Typeable b) => r -> (b -> r) -> a -> r mkQ defaultVal fn a = ...
    ```

    +   `mkQ`代表“创建查询”

+   例子

    ```
    salaryVal :: Typeable a => a -> Double salaryVal = mkQ 0 $ \(Salary s) -> s
    ```

    ```
    *Main> salaryVal () 0.0 *Main> salaryVal 7 0.0 *Main> salaryVal (Salary 7) 7.0
    ```

+   练习：实现`mkQ`

## 解决方案

```
mkQ :: (Typeable a, Typeable b) => r -> (b -> r) -> a -> r mkQ defaultVal fn a = case cast a of Just b -> fn b Nothing -> defaultVal
```

+   或者如果你想要变得花哨：

```
mkQ :: (Typeable a, Typeable b) => r -> (b -> r) -> a -> r mkQ defaultVal fn = maybe defaultVal fn . cast
```

## 多类型函数：`extQ`

+   `mkQ`只适用于一种类型

    +   让我们将`mkQ`的输出扩展到另一种类型[[Boilerplate1]](http://research.microsoft.com/en-us/um/people/simonpj/papers/hmap/hmap.ps)

    ```
    extQ :: (Typeable a, Typeable b) => (a -> r) -> (b -> r) -> a -> r extQ q f a = case cast a of Just b -> f b Nothing -> q a
    ```

+   现在可以级联多个相同类型的查询函数

    ```
    myShow :: Typeable a => a -> String myShow = mkQ "unknown type" (show :: Int -> String) `extQ` (show :: Bool -> String) `extQ` (show :: Integer -> String) `extQ` (const "no floating point" :: Double -> String)
    ```

    +   回想默认的结合性是左结合（`infixl 9 `extQ``）

    +   有点繁琐，但如果元组包含有限数量的类型，可以近似实现讲座开始时的`tupleToList`目标

## [`ExistentialQuantification`](http://www.haskell.org/ghc/docs/latest/html/users_guide/data-type-extensions.html#existential-quantification)扩展

+   允许在`data`声明的右侧引入类型变量

    ```
    {-# LANGUAGE ExistentialQuantification #-} data Step s a = Done | Skip !s | Yield !a !s data Stream a = forall s. Stream (s -> Step s a) !s 
    ```

    +   给定类型为`Stream a`的值，存在一个类型`s`，使得...

        但语法使用`forall`，而不是`exists`，以避免引入新关键字

    +   非常安全的扩展（`Control.Exception`依赖于它）

+   不要与[`Rank2Types`](http://www.haskell.org/ghc/docs/latest/html/users_guide/other-type-extensions.html#universal-quantification)混淆，其中`forall`表示所有类型`s`：

    ```
    data Stream a = Stream (forall s. s -> Step s a)
    ```

+   对于存在变量的上下文，就像隐藏的字典字段

    ```
    data Showable = forall a. (Show a) => Showable a instance Show Showable where show (Showable a) = "Showable " ++ show a
    ```

    +   一个`Showable`值既有类型为`a`的值，也有`Show`的字典

## 例子：动态类型

+   [`Data.Dynamic`](http://hackage.haskell.org/packages/archive/base/latest/doc/html/Data-Dynamic.html)具有类型`Dynamic`，可以容纳任何`Typeable`

    ```
    data Dynamic -- opaque type toDyn :: Typeable a => a -> Dynamic fromDynamic :: Typeable a => Dynamic -> Maybe a
    ```

+   实际实现略显复杂

    +   使用`unsafeCoerce`将所有内容强制转换为占位符`Obj`类型

+   但是使用`ExistentialQuantification`可以安全地实现：

    ```
    data Dynamic = forall a. Typeable a => Dynamic a toDyn :: Typeable a => a -> Dynamic toDyn = Dynamic fromDynamic :: Typeable a => Dynamic -> Maybe a fromDynamic (Dynamic a) = cast a
    ```

## 例子：可扩展异常[[Marlow]](http://community.haskell.org/~simonmar/papers/ext-exceptions.pdf)

+   GHC 运行时实现了原始的、不安全的异常

    ```
    raise# :: a -> b catch# :: IO a -> (b -> IO a) -> IO a -- slight simplification
    ```

    +   必须确保，如所使用，`b`始终是相同类型，否则会得到不安全的强制转换

+   实际上，希望有许多异常类型，组织成一个层次结构

+   [`Control.Exception`](http://hackage.haskell.org/packages/archive/base/latest/doc/html/Control-Exception.html) 实现安全的、分层的异常

    +   `raise#` 和 `catch#` 只会被一个类型调用：`SomeException`

    ```
    class (Typeable e, Show e) => Exception e where  toException :: e -> SomeException toException = SomeException -- default impl  fromException :: SomeException -> Maybe e fromException (SomeException e) = cast e -- default impl data SomeException = forall e. Exception e => SomeException e deriving Typeable -- note use of ExistentialQuantification instance Show SomeException where show (SomeException e) = show e
    ```

## 抛出和捕获异常

```
class (Typeable e, Show e) => Exception e where  toException :: e -> SomeException  fromException :: SomeException -> Maybe e
```

+   要抛出异常，首先将其转换为类型 `SomeException`

    ```
    throw :: Exception e => e -> a throw e = raise# (toException e)
    ```

+   要捕获异常，必须确保它与所需类型匹配

    ```
    -- Define catchX because catch#'s real type more complicated catchX :: IO a -> (b -> IO a) -> IO a catchX (IO a) handler = IO $ catch# a (unIO . handler) catch :: (Exception e) => IO a -> (e -> IO a) -> IO a catch action handler = catchX action handler' where handler' se = maybe (throwIO se) handler $ fromException se
    ```

    +   注意 `handler` 使 `fromException se` 使用 `e` 的 `Exception` 字典

## 制作分层异常

+   很容易添加自己的顶级异常类型

    ```
    data MyException = MyException deriving (Show, Typeable) instance Exception MyException -- use default methods
    ```

+   但你也可以创建一系列异常类型的层次结构

    ```
    data AppError = forall e. Exception e => AppError e deriving (Typeable) instance Show AppError where show (AppError e) = show e instance Exception AppError data Error1 = Error1 deriving (Show, Typeable) instance Exception Error1 where toException = toException . AppError fromException se = do -- using Maybe as a Monad here AppError e <- fromException se cast e -- Now can do the same for Error2, and catch both as AppError
    ```

    +   让你只捕获 `Error1`，或任何 `AppError`

## [`Data`](http://hackage.haskell.org/packages/archive/base/latest/doc/html/Data-Data.html#t:Data) 类

```
class Typeable a => Data a where ...
```

+   `Data` 类允许对数据结构进行通用遍历和构造

    +   定义 `gfoldl` 和 `gunfold` 方法如下

    ```
    data T a b = C1 a b | C2 deriving (Typeable, Data) gfoldl k z (C1 a b) = z C1 `k` a `k` b gfoldl k z C2 = z C2 toConstr (C1 _ _) = ... -- encodes constructor number toConstr C2 = ... gunfold k z c = case constrIndex c of 1 -> k (k (z C1)) 2 -> z C2
    ```

+   现在可以处理所有大小的元组了！但是：

    +   一旦引入类型，事情变得更加丑陋 [cosmetic]

    +   可用的唯一字典是 `Data` 和 `Typeable` [fundamental]

    +   所有的运行时类型检查都很慢 [fundamental]

## 我们能在编译时做吗？

+   替代方案：将通用编程推到编译时 [[Magalhães]](http://dreixel.net/research/pdf/gdmh.pdf)

+   让我们看一个简化的实现

    +   `wget` [`cs240h.stanford.edu/metadata.hs`](http://www.scs.stanford.edu/14sp-cs240h/metadata.hs)

+   高层次思想：假设你自动派生了`Show`类似的实例：

    ```
    class MyShow a where myShow :: a -> String instance MyShow MyType where myShow = genericMyShow
    ```

    +   引入通用的`MetaData`类，编译器可以生成实例

    ```
    class MetaData d m | d -> m, m -> d where -- not what GHC does  fromData :: d -> m  toData :: m -> d
    ```

    +   还有一个`MyShow`特定的元类，是这样的吗？

    ```
    class MetaMyShow a where metaMyShow :: a -> String genericMyShow :: (MetaData d m, MetaMyShow m) => d -> String genericMyShow = metaMyShow . fromData
    ```

## [`DefaultSignatures`](http://www.haskell.org/ghc/docs/latest/html/users_guide/type-class-extensions.html#class-default-signatures) 扩展

+   我们可以使用[`DefaultSignatures`](http://www.haskell.org/ghc/docs/latest/html/users_guide/type-class-extensions.html#class-default-signatures) 扩展做得更好

+   允许不适用于所有实例的默认方法

```
{-# LANGUAGE DefaultSignatures #-} class MyShow a where  myShow :: a -> String default myShow :: (MetaData a m, MetaMyShow m) => a -> String myShow = genericMyShow
```

+   使声明实例变得更容易

```
instance MyShow MyType
```

+   让我们看看如何设计这样一个`MetaData`类

    +   `wget` [`cs240h.stanford.edu/metadata.hs`](http://www.scs.stanford.edu/14sp-cs240h/metadata.hs)

## [`DeriveGeneric`](http://www.haskell.org/ghc/docs/latest/html/users_guide/generic-programming.html) 扩展

+   编译器支持单个`Generic`类，将任何数据类型转换为可以通用计算的`Rep`： 

    ```
    {-# LANGUAGE TypeFamilies #-} class Generic a where type Rep a :: * -> *  from :: a -> Rep a x  to :: Rep a x -> a
    ```

+   `type Rep` 使用了称为 `TypeFamilies` 的扩展。可以理解为：

    ```
    class Generic a rep | a -> rep where  from :: a -> rep x  to :: rep x -> a
    ```

+   像我们简单的例子一样，除了所有的都是∗ → ∗类型

    +   为什么？也许是因为你需要博士学位才能使用这个扩展？

    +   （据说将来会支持种类为∗ → ∗的通用类型，因此可以制作通用的`Functor`类似实例）

## 单元类型的`Rep`

```
{-# LANGUAGE DeriveGeneric, TypeFamilies, TypeOperators,  FlexibleInstances, FlexibleContexts, UndecidableInstances #-} import GHC.Generics data X = X -- because we are dealing with types of kind * -> * undef2 :: mi c f p -> f p undef2 _ = undefined -- A unit type has one constructor and no arguments data T1 = C1 deriving (Show, Generic)
```

```
*Main> :t from C1 from C1 :: Rep T1 x *Main> :t (undefined :: Rep T1 X) (undefined :: Rep T1 X) :: D1 Main.D1T1 (C1 Main.C1_0T1 U1) X *Main> datatypeName (from C1) "T1" *Main> moduleName (from C1) "Main" *Main> conName $ undef2 (from C1) "C1"
```

## [`GHC.Generics`](http://www.haskell.org/ghc/docs/latest/html/libraries/base-4.7.0.0/GHC-Generics.html) 内容（第一部分）

```
{-# LANGUAGE TypeFamilies, KindSignatures, TypeOperators #-} -- | Unit: used for constructors without arguments data U1 p = U1 -- | Meta-information (constructor names, etc.) newtype M1 i c f p = M1 { unM1 :: f p } -- | Three flavors of meta-information for variable i data D; type D1 = M1 D -- c instance of Datatype, f is C1 (or :+:) data C; type C1 = M1 C -- c instance of Constructor, f is S1 (or :*:) data S; type S1 = M1 S -- c instance of Selector, f is U1 (or Rec0) class Datatype d where  datatypeName :: t d (f :: * -> *) a -> String  moduleName :: t d (f :: * -> *) a -> String class Constructor c where  conName :: t c (f :: * -> *) a -> String class Selector s where  selName :: t s (f :: * -> *) a -> String
```

## 带有构造函数参数的类型

```
data T2 = C2 { t2a :: Bool } deriving (Show, Generic) data T3 = C3 { t3a :: Bool, t3b :: Bool } deriving (Show, Generic)
```

```
*Main> :t (undefined :: Rep T2 X) (undefined :: Rep T2 X) :: D1 Main.D1T2 (C1 Main.C1_0T2 (S1 Main.S1_0_0T2 (Rec0 Bool))) X *Main> -- This was U1 for type T1 ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^ *Main> conName (undef2 $ from $ C2 True) "C2" *Main> selName (undef2 $ undef2 $ from $ C2 True) "t2a" *Main> :t (undefined :: Rep T3 X) (undefined :: Rep T3 X) :: D1 Main.D1T3 (C1 Main.C1_0T3 (S1 Main.S1_0_0T3 (Rec0 Bool) :*: S1 Main.S1_0_1T3 (Rec0 Bool))) X
```

+   注意选择器是我们简单示例没有的一个特性

    +   让你从类型中挑选出记录名称

## [`GHC.Generics`](http://www.haskell.org/ghc/docs/latest/html/libraries/base-4.7.0.0/GHC-Generics.html) 内容（第 2 部分）

```
-- Used to glue multiple constructor arguments together data (:*:) f g p = f p :*: g p infixr 6 :*: -- Used to represent a type with multiple constructors data (:+:) f g p = L1 { unL1 :: f p } | R1 { unR1 :: g p } infixr 5 :+: -- Used to hold actual concrete values of constructor arguments newtype K1 i c p = K1 { unK1 :: c } type Rec0 = K1 R -- From two slides ago: data U1 p = U1 -- Unit constructors (no arguments) newtype M1 i c f p = M1 { unM1 :: f p } data D; type D1 = M1 D -- c instance of Datatype, f is C1 or :+: data C; type C1 = M1 C -- c instance of Constructor, f is S1 or :*: data S; type S1 = M1 S -- c instance of Selector, f is U1 or Rec0
```

+   再次忽略参数`p`（这里是为了使类型的种类为∗ → ∗）

+   `M1`存在，所以一个单一的遍历方法可以跳过`D1`、`C1`和`S1`

+   可以说`newtype Rec0 c p = K1 c`，但有些实例使用`K1 P`

## `Generic`实例会是什么样子？

```
data T a b = C1 a b | C2 deriving (Show, Generic) data T_ instance Datatype T_ where datatypeName _ = "T" moduleName _ = "Main" data T_C1_ data T_C2_ instance Constructor T_C1_ where conName _ = "C1" instance Constructor T_C2_ where conName _ = "C2" type Rep0T_ a_0 b_1 = D1 T_ (C1 T_C1_ (S1 NoSelector (Rec0 a_0) :*: S1 NoSelector (Rec0 b_1)) :+: (C1 T_C2_ U1)) instance Generic (T a_0 b_1) where type Rep (T a_0 b_1) = Rep0T_ a_0 b_1 from (C1 f0 f1) = M1 (L1 (M1 (M1 (K1 f0) :*: M1 (K1 f1)))) from (C2) = M1 (R1 (M1 U1)) to (M1 (L1 (M1 (M1 (K1 f0) :*: M1 (K1 f1))))) = C1 f0 f1 to (M1 (R1 (M1 U1))) = C2
```

## 我们如何使用这个？

+   假设我们正在定义自己的`Show`类似的类

    ```
    class MyShow a where myShow :: a -> String instance MyShow [Char] where myShow = show instance MyShow Int where myShow = show
    ```

+   希望它能适用于所有用户定义的数据类型

    +   让我们定义一个类`Show1`来处理烦人的`p`参数

    ```
    {-# LANGUAGE FlexibleInstances, UndecidableInstances,  OverlappingInstances, TypeSynonymInstances, TypeOperators,  TypeFamilies, TemplateHaskell, FlexibleContexts #-} class MyShow1 f where myShow1 :: f p -> String
    ```

    +   让我们定义通用的遍历方法

    ```
    instance (MyShow1 f) => MyShow1 (M1 i c f) where -- for D1, S1 myShow1 m1 = myShow1 (unM1 m1) instance (MyShow1 f, MyShow1 g) => MyShow1 (f :+: g) where myShow1 (L1 a) = myShow1 a myShow1 (R1 a) = myShow1 a
    ```

## `MyShow1`的非通用实例

+   当我们遇到一个构造函数时，想要打印出名称

    ```
    instance (Constructor c, MyShow1 f) => MyShow1 (C1 c f) where myShow1 m1 = conName m1 ++ myShow1 (unM1 m1)
    ```

    +   我们正在使用`OverlappingInstances`，因为已经有`M1`实例

+   当没有构造函数参数时，不显示任何内容

    ```
    instance MyShow1 U1 where myShow1 _ = ""
    ```

+   当我们有多个构造函数参数时，显示它们全部

    ```
    instance (MyShow1 f, MyShow1 g) => MyShow1 (f :*: g) where myShow1 (fp :*: gp) = myShow1 fp ++ myShow1 gp
    ```

+   当你遇到实际值时，显示它

    ```
    instance (MyShow c) => MyShow1 (K1 i c) where myShow1 k1 = ' ' : myShow (unK1 k1)
    ```

    +   现在我们正在调用`myShow`，但我们还没有为许多类型定义它

## 实现一个通用的`MyShow`

+   现在可以根据`MyShow1`来定义通用的`MyShow`

    ```
    instance (Generic a, MyShow1 (Rep a)) => MyShow a where myShow a = myShow1 $ from a
    ```

+   我们能避免`OverlappingInstances`吗？

    +   可以定义`Show1`的单独的`D1`、`S1`实例（简单）

    +   可以完全避免通用实例

        推荐的用法只是定义一个*函数* `myShowDefault`，然后

    ```
    myShowDefault :: (Generic a, MyShow1 (Rep a)) => a -> String myShowDefault a = myShow1 $ from a instance MyShow T1 where myShow = myShowDefault instance MyShow T2 where myShow = myShowDefault instance MyShow T3 where myShow = myShowDefault ...
    ```

    +   仍然存在`[Char]`与`[a]`之间不同行为的问题
