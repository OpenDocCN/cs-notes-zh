# GHC 语言扩展

+   GHC 实现了许多 Haskell 扩展，通过启用

    +   在文件顶部放置`{-# LANGUAGE` *ExtensionName* `#-}`（推荐）

    +   使用`-X`*ExtensionName*编译（不推荐，除了`-XSafe`）

    +   在`ghci`提示符处键入`:set -X`*ExtensionName*（或使用`-X`运行`ghci`...）

+   在 GHC 选项摘要的[语言选项](http://www.haskell.org/ghc/docs/latest/html/users_guide/flag-reference.html#idp14594128)部分列出完整列表

+   有些扩展非常安全可靠

    +   例如，核心库深度依赖扩展

    +   扩展非常表面，很容易转换为 Haskell2010

+   其他扩展被较少接受

    +   例如，使类型推断/检查变得不可判定或非确定性

    +   破坏类型安全

    +   一个无法并入标准的正在进行中的工作

+   许多扩展处于中间/灰色地带

## 背景：Monad 变换器

+   类构造器构建由其他单子参数化的单子

    +   方法[`lift`](http://hackage.haskell.org/packages/archive/transformers/latest/doc/html/Control-Monad-Trans-Class.html#t:MonadTrans)执行来自底层转换单子的操作：

    ```
    class MonadTrans t where  lift :: Monad m => m a -> t m a
    ```

    +   注意单子的种类∗ → ∗，因此变换器的种类为(∗ → ∗) → ∗ → ∗

+   例子：状态变换器单子，[`StateT`](http://hackage.haskell.org/packages/archive/transformers/latest/doc/html/Control-Monad-Trans-State-Lazy.html#v:StateT)

    ```
    newtype StateT s m a = StateT { runStateT :: s -> m (a,s) } instance (Monad m) => Monad (StateT s m) where return a = StateT $ \s -> return (a, s) m >>= k = StateT $ \s0 -> do -- in monad m ~(a, s1) <- runStateT m s0 runStateT (k a) s1 instance MonadTrans (StateT s) where lift ma = StateT $ \s -> do -- in monad m a <- ma return (a, s)
    ```

## 使用`StateT`

+   `get`和`put`允许您修改状态

    ```
    get :: (Monad m) => StateT s m s put :: (Monad m) => s -> StateT s m ()
    ```

+   例子：在 C 中的`x++`的 Haskell 等价物

    ```
    import Control.Monad.Trans import Control.Monad.Trans.State main :: IO () main = runStateT go 0 >>= print where go = do xplusplus >>= lift . print xplusplus >>= lift . print xplusplus = do n <- get; put (n + 1); return n
    ```

    ```
    *Main> main 0 1 ((),2)
    ```

## 练习：实现`get`和`put`

+   回顾`StateT`的实现

```
newtype StateT s m a = StateT { runStateT :: s -> m (a,s) } instance (Monad m) => Monad (StateT s m) where return a = StateT $ \s -> return (a, s) m >>= k = StateT $ \s0 -> do -- in monad m ~(a, s1) <- runStateT m s0 runStateT (k a) s1
```

+   如何实现以下内容？

```
get :: (Monad m) => StateT s m s put :: (Monad m) => s -> StateT s m ()
```

## 练习：实现`get`和`put`

+   回顾`StateT`的实现

```
newtype StateT s m a = StateT { runStateT :: s -> m (a,s) } instance (Monad m) => Monad (StateT s m) where return a = StateT $ \s -> return (a, s) m >>= k = StateT $ \s0 -> do -- in monad m ~(a, s1) <- runStateT m s0 runStateT (k a) s1
```

+   如何实现以下内容？

```
get :: (Monad m) => StateT s m s get = StateT $ \s -> return (s, s) put :: (Monad m) => s -> StateT s m () put s = StateT $ \_ -> return ((), s)
```

## `MonadIO`类

+   有时希望执行 IO 而不考虑当前单子

```
class (Monad m) => MonadIO m where  liftIO :: IO a -> m a instance MonadIO IO where liftIO = id
```

+   让`liftIO`在`StateT`中起作用

    ```
    instance (MonadIO m) => MonadIO (StateT s m) where liftIO = lift . liftIO
    ```

+   现在可以编写使用 IO 并在许多单子中工作的函数：

    ```
    myprint :: (Show a, MonadIO m) => a -> m () myprint a = liftIO $ print $ show a
    ```

+   所有标准 Monad 变换器都实现了`MonadIO`类

    +   `ContT`、`ErrorT`、`ListT`、`RWST`、`ReaderT`、`StateT`、`WriterT`等

## 背景：递归绑定

+   顶层、`let`和`where`绑定在 Haskell 中都是递归的，例如：

    ```
    oneTwo :: (Int, Int) oneTwo = (fst y, snd x) where x = (1, snd y) -- mutual recursion y = (fst x, 2) nthFib :: Int -> Integer nthFib n = fibList !! n where fibList = 1 : 1 : zipWith (+) fibList (tail fibList)
    ```

+   可以使用固定点组合子实现递归

    +   函数[`fix`](http://hackage.haskell.org/packages/archive/base/latest/doc/html/Data-Function.html#v:fix)调用具有其自身结果的函数，用于重新实现上述内容：

        ```
        fix :: (a -> a) -> a fix f = let x = f x in x
        ```

        ```
        oneTwo' :: (Int, Int) oneTwo' = (fst y, snd x) where (x, y) = fix $ \ ~(x0, y0) -> let x1 = (1, snd y0) y1 = (fst x0, 2) in (x1, y1) nthFib' n = fibList !! n where fibList = fix $ \l -> 1 : 1 : zipWith (+) l (tail l)
        ```

## 递归和单子绑定

+   相比之下，单子绑定*不*是递归的

    ```
    do fibList <- return $ 1 : 1 : zipWith (+) fibList (tail fibList) ... -- error, fibList not in scope ^^^^^^^ ^^^^^^^
    ```

+   但[`MonadFix`](http://hackage.haskell.org/packages/archive/base/latest/doc/html/Control-Monad-Fix.html#t:MonadFix)类中的单子具有固定点组合子

    ```
    class Monad m => MonadFix m where  mfix :: (a -> m a) -> m a
    ```

    +   `mfix`可用于实现递归单子绑定[[Erkök00]](http://citeseer.ist.psu.edu/viewdoc/download;jsessionid=13851C3A2D4F33918B9D662C20F30762?doi=10.1.1.43.5313&rep=rep1&type=pdf)，例如：

    ```
    mfib :: (MonadFix m) => Int -> m Integer mfib n = do fibList <- mfix $ \l -> return $ 1 : 1 : zipWith (+) l (tail l) return $ fibList !! n -- ^^^^^
    ```

+   为什么？例如，可能想要用单子模拟电路

    +   如果电路中存在循环，则需要递归

    +   可能仍然希望递归以避免担心语句的顺序

## [`RecursiveDo`](http://www.haskell.org/ghc/docs/latest/html/users_guide/syntax-extns.html#recursive-do-notation) 扩展

+   新的 `rec` 关键字在 `do` 块中引入递归绑定 [[Erkök02]](https://sites.google.com/site/leventerkok/recdo.pdf?attredirects=0)

    +   单子必须是 `MonadFix` 的一个实例（`rec` 展开为 `mfix` 调用）

    ```
    oneTwo'' :: (MonadFix m) => m (Int, Int) oneTwo'' = do rec x <- return (1, snd y) y <- return (fst x, 2) return (fst y, snd x)
    ```

    +   展开为：

    ```
    oneTwo''' :: (MonadFix m) => m (Int, Int) oneTwo''' = do (x, y) <- mfix $ \ ~(x0, y0) -> do x1 <- return (1, snd y0) y1 <- return (fst x0, 2) return (x1, y1) return (fst y, snd x)
    ```

+   在实践中，`RecursiveDo` 有助于构建思维结构

    +   然后可以手动展开，而不需要语言扩展

    +   但单独使用 `mfix` 是非常有用的

## `mfix` 和 `rec` 的示例用法

+   一次性创建递归数据结构

    ```
    data Link a = Link !a !(MVar (Link a)) -- note ! is okay mkCycle :: IO (MVar (Link Int)) mkCycle = do rec l1 <- newMVar $ Link 1 l2 -- but $! would diverge l2 <- newMVar $ Link 2 l1 return l1
    ```

+   调用类的非严格方法（轻松访问返回类型字典）

    ```
    class MyClass t where  myTypeName :: t -> String -- non-strict in argument  myDefaultValue :: t instance MyClass Int where myTypeName _ = "Int" myDefaultValue = 0 getVal :: (MyClass t) => IO t getVal = mfix $ \t -> do -- doesn't use mfix's full power putStrLn $ "Caller wants type " ++ myTypeName t return myDefaultValue
    ```

## 实现 `mfix`

+   热身：[`Identity`](http://hackage.haskell.org/packages/archive/transformers/latest/doc/html/Data-Functor-Identity.html#v:Identity) 单子

    ```
    newtype Identity a = Identity { runIdentity :: a } instance Monad Identity where return = Identity m >>= k = k (runIdentity m)
    ```

    +   `newtype` 编译成空，所以基本上与 `fix` 相同：

    ```
    instance MonadFix Identity where mfix f = let x = f (runIdentity x) in x
    ```

## `fixIO` -- `IO` 单子的不动点

+   在内部，惰性 IO 是通过神奇的 [`unsafeInterleaveIO`](http://hackage.haskell.org/package/base-4.7.0.0/docs/System-IO-Unsafe.html#v:unsafeInterleaveIO) 实现的

    ```
    unsafeInterleaveIO :: IO a -> IO a
    ```

    +   看起来像是一个 `IO` 标识函数，但推迟 IO 直到强制 thunk

    +   危险--不要在家里尝试！不再是一个函数式语言

        ```
        weird :: IO String weird = do xxx <- unsafeInterleaveIO $ do putStrLn "Gotcha!"; return [] return $ 'a':'b':'c':xxx
        ```

+   对于 `IO`，`mfix = fixIO`：

    ```
    fixIO :: (a -> IO a) -> IO a fixIO k = do ref <- newIORef (throw NonTermination) ans <- unsafeInterleaveIO (readIORef ref) result <- k ans writeIORef ref result return result
    ```

    +   这与编译器为纯 `fix` 所做的事情非常相似

## 通用的 `mfix` 是不可能的

+   如果我们尝试为所有单子定义一个类似 `mfix` 的函数会怎样？

    ```
    mbroken :: (Monad m) => (a -> m a) -> m a -- equivalent to mfix? mbroken f = fix (>>= f)
    ```

    +   这等同于

    ```
    mbroken f = mbroken f >>= f
    ```

    +   但对于许多单子，`>>=` 在其第一个参数上是严格的

    ```
    *Main> mfix $ const (return 0) 0 *Main> mbroken $ const (return 0) *** Exception: stack overflow
    ```

+   因此 `mfix` 需要对值进行不动点，而不是对单子动作进行不动点

    +   如何做到这一点是特定于单子的

    +   不适用于所有单子（`ContT`，`ListT`）

## `StateT` 的 `MonadFix` 实例

+   [`StateT`](http://hackage.haskell.org/packages/archive/transformers/latest/doc/html/Control-Monad-Trans-State-Lazy.html#t:StateT) 单子怎么样？

    ```
    newtype StateT s m a = StateT { runStateT :: s -> m (a,s) } instance (Monad m) => Monad (StateT s m) where return a = StateT $ \s -> return (a, s) m >>= k = StateT $ \s0 -> do -- in monad m ~(a, s1) <- runStateT m s0 runStateT (k a) s1
    ```

    +   可能最容易使用 `rec` 符号来看

    ```
    instance MonadFix m => MonadFix (StateT s m) where mfix f = StateT $ \s0 -> do -- in monad m rec ~(a, s1) <- runStateT (f a) s0 return (a, s1)
    ```

    +   但可以轻松实现，无需语言扩展

    ```
    instance MonadFix m => MonadFix (StateT s m) where mfix f = StateT $ \s -> mfix $ \ ~(a, _) -> runStateT (f a) s
    ```

## 复习：类型类

+   一个 [Haskell 2010 类型类声明](http://www.haskell.org/onlinereport/haskell2010/haskellch4.html#x10-760004.3.1) 可以采用以下形式：

    ```
    class ClassName var where  methodName :: Type {- where type references var -}
    ```

    ```
    class (SuperClass var) => ClassName var where ... class (Super1 var, Super2 var) => ClassName var where ... ...
    ```

    +   注意 `var` 不必具有 ∗ 类型

    +   然而，每个方法的类型必须提及 `var`，并且每个方法的上下文中添加了一个隐式的 `(Classname var)`，例如：

        ```
        Prelude> :t return return :: Monad m => a -> m a
        ```

+   一个 [Haskell 2010 实例声明](http://www.haskell.org/onlinereport/haskell2010/haskellch4.html#x10-770004.3.2) 的形式为：

    ```
    instance [context =>] ClassName (TypeCon v1 ... vk) where ...
    ```

    +   注意 `v1` ... `vk` 都是变量且都不同，排除了，例如，`instance C (a,a)` 或 `instance C (Int a)` 或 `instance [[a]]`

## [`MultiParamTypeClasses`](http://www.haskell.org/ghc/docs/latest/html/users_guide/type-class-extensions.html#id559142) 扩展

+   启用具有多个参数的类型类，例如：

    ```
    {-# LANGUAGE MultiParamTypeClasses #-} class Convert a b where convert :: a -> b instance Convert Int Bool where convert = (/= 0) instance Convert Int Integer where convert = toInteger instance (Convert a b) => Convert [a] [b] where convert = map convert
    ```

+   扩展本身相对安全，但鼓励其他扩展

    +   例如，每个方法的类型必须使用每个类型参数

        ```
        class MyClass a b where  aDefault :: a -- can never use (without more extensions...)
        ```

    +   所有类型（参数和返回）必须完全确定

        ```
         convert 0 :: Bool -- error, 0 has type (Num a) => a
        ```

    +   并且通常的实例限制仍然适用

        ```
        instance Convert Int [Char] where convert = show -- error bad param
        ```

        +   `[Char]`--即 `([] Char)`--不是一个有效的实例参数，必须是 `([] a)`

## [`FlexibleInstances`](http://www.haskell.org/ghc/docs/latest/html/users_guide/type-class-extensions.html#instance-decls) 扩展

+   允许更具体的类型参数（相对安全的扩展）。

    +   例如，现在我们可以说：

    ```
    {-# LANGUAGE FlexibleInstances #-} instance Convert Int [Char] where convert = show
    ```

    +   我们可以使所有类型转换为它们自己：

    ```
    instance Convert a a where convert a = a
    ```

    ```
    *Main> convert () :: () () *Main> convert ([1,2,3]::[Int]) :: [Integer] [1,2,3] *Main> convert ([1,2,3]::[Int]) :: [Int] <interactive>:1:1: Overlapping instances for Convert [Int] [Int] instance Convert a a instance Convert a b => Convert [a] [b]
    ```

    +   糟糕，两个实例都适用； GHC 不知道选择哪个

## [`OverlappingInstances`](http://www.haskell.org/ghc/docs/latest/html/users_guide/type-class-extensions.html#instance-overlap) 扩展

+   这个扩展被使用，但也被广泛抨击

    +   只有在实际使用重叠实例时才需要此扩展。

    +   在定义实例的地方启用扩展，而不是在使用的地方启用

    +   当 *I*[1] 可以通过替换 *I*[2] 的变量而创建，并且反之则不成立时，编译器会选择最具体的匹配实例。 *I*[1] 比 *I*[2] 更具体。

    +   上下文（在 `=>` 前面的部分）在选择实例时不予考虑。

+   例如：像 `String` vs. `[a]` 的 `Show` 一样做些什么

    ```
    class MyShow a where myShow :: a -> String instance MyShow Char where myShow = show instance MyShow Int where myShow = show instance MyShow [Char] where myShow = id instance (MyShow a) => MyShow [a] where myShow [] = "[]" myShow (x:xs) = "[" ++ myShow x ++ go xs where go (y:ys) = "," ++ myShow y ++ go ys go [] = "]"
    ```

+   因此，启用 `OverlappingInstances` 是否修复了 `Convert`？

## 最具体的实例

+   最具体的实例是什么？

    ```
    {-# LANGUAGE MultiParamTypeClasses #-} {-# LANGUAGE FlexibleInstances #-} {-# LANGUAGE OverlappingInstances #-} instance Convert a a where ... instance (Convert a b) => Convert [a] [b] where ...
    ```

    ```
    *Main> convert ([1,2,3]::[Int]) :: [Int] <interactive>:1:1: Overlapping instances for Convert [Int] [Int] instance [overlap ok] Convert a a instance [overlap ok] Convert a b => Convert [a] [b]
    ```

    +   没有实例是最具体的！

    +   我们必须添加一个 *第三* 实例来打破这种关系--一个可以通过替换其他两个重叠实例中的变量而创建的实例

    ```
    instance Convert [a] [a] where convert = id
    ```

    ```
    *Main> convert ([1,2,3]::[Int]) :: [Int] [1,2,3]
    ```

## 反对 `OverlappingInstances` 的一个案例

```
module Help where class MyShow a where  myshow :: a -> String instance MyShow a => MyShow [a] where myshow xs = concatMap myshow xs  showHelp :: MyShow a => [a] -> String showHelp xs = myshow xs -- doesn't see overlapping instance module Main where import Help data T = MkT instance MyShow T where myshow x = "Used generic instance" instance MyShow [T] where myshow xs = "Used more specific instance" main = do { print (myshow [MkT]); print (showHelp [MkT]) }
```

```
*Main> main "Used more specific instance" "Used generic instance"
```

## 旁注：`Show` 实际上是如何工作的

+   添加一个额外的帮助方法，`showList`，并附带一个默认定义：

```
class Show a where  show :: a -> String  showList :: [a] -> ShowS showList as = '[' : intercalate ", " (map show as) ++ "]" -- Note actual implementation more efficient but equivalent instance (Show a) => Show [a] where show as = showList as
```

+   `Char` 的 `Show` 实例覆盖了默认的 `showList`。

+   但是必须从一开始就计划好所有这些

    +   想要一种简单的方式来为树或其他数据结构特别处理，而不仅仅是列表？

    +   然后您将被迫使用重叠实例。

## [`FlexibleContexts`](http://www.haskell.org/ghc/docs/latest/html/users_guide/other-type-extensions.html#flexible-contexts) 扩展

+   `MultiParamTypeClasses` 导致无法表达的类型。

    ```
    toInt val = convert val :: Int
    ```

    +   函数 `toInt` 的类型是什么？想要写：

    ```
    toInt :: (Convert a Int) => a -> Int
    ```

    +   但是`(Convert a Int) =>`是一个非法的上下文，因为`Int`不是一个类型变量

+   `FlexibleContexts` 扩展使上述类型合法可写。

    +   是一个相对安全的扩展来使用

+   仍然有一些限制。

    +   上下文中的每个类型变量必须从类型中的一个类型变量可达。

        (可达 = 明确使用，或者在另一个具有可达变量的约束中。)

        ```
        sym :: forall a. Eq a => Int -- illegal
        ```

    +   每个约束必须有一个类型变量。

        ```
        sym :: Eq Int => Bool -- illegal
        ```

## 单子类

+   `liftIO` 从如此多的单子中工作真是太棒了

    +   为什么不为 `StateT` 做类似的事情？让 `get`/`set` 方法

    ```
    {-# LANGUAGE MultiParamTypeClasses #-} {-# LANGUAGE FlexibleInstances #-} class (Monad m) => MonadState s m where  get :: m s  put :: s -> m () instance (Monad m) => MonadState s (StateT s m) where get = StateT $ \s -> return (s, s) put s = StateT $ \_ -> return ((), s)
    ```

+   现在对于每个其他的 `MonadTrans`，将请求传递下去

    +   这就像 `liftIO` 一样。例如，对于 `ReaderT`：

    ```
    instance (MonadIO m) => MonadIO (ReaderT r m) where liftIO = lift . liftIO instance (MonadState s m) => MonadState s (ReaderT r m) where get = lift get put = lift . put
    ```

## 问题：我们破坏了类型推断。

+   还记得 `xplusplus` 吗？

    ```
     xplusplus = do n <- get; put (n + 1); return n
    ```

    +   编译器知道我们处于`StateT Int IO`单子中。

    +   因此可以推断`get`的类型为`Num s => StateT Int IO s`。

    +   但是需要知道`s`才能选择`MonadState`的一个实例！

    +   对于编译器来说，可能有其他匹配的实例，例如，

        ```
        instance MonadState Double (StateT Int IO) where -- would be legal, but exists only in compiler's imagination
        ```

+   由于编译器无法推断`get`的返回类型，必须手动输入类型：

    ```
     xplusplus = do n <- get :: StateT Int IO Int put (n + 1) return n
    ```

    +   呸！缺乏类型推断真的很烦人！

## [`FunctionalDependencies`](http://www.haskell.org/ghc/docs/latest/html/users_guide/type-class-extensions.html#functional-dependencies) 扩展

+   被广泛使用并且被 frowned upon（没有 `OverlappingInstances` 那么糟糕）

    +   也被称为“fundeps”

+   允许类声明某些参数是其他参数的函数

    ```
    class (Monad m) => MonadState s m | m -> s where  get :: m s  put :: s -> m ()
    ```

    +   最好的理解方式是以*实例选择*的方式来思考

    +   "`| m -> s`" 表示可以根据 `m` 而不考虑 `s` 来选择一个实例，因为 **`s` 是 `m` 的函数**

    +   一旦你选择了实例，你就可以使用 `s` 进行类型推断

+   禁止冲突的实例（即使使用了 `OverlappingInstances`）

+   还允许在类型层面进行任意计算[[Hallgren]](http://citeseerx.ist.psu.edu/viewdoc/download;jsessionid=D19C7E3BD1B5C1FC24035542B1494ED9?doi=10.1.1.22.7806&rep=rep1&type=pdf)

    +   但语言委员会希望编译是可决定的和确定的

    +   所以需要添加一些限制

## [可决定实例的充分条件](http://www.haskell.org/ghc/docs/latest/html/users_guide/type-class-extensions.html#instance-rules)

+   实例的解剖：`instance` [*context* `=>`] *head* [`where` *body*]

    +   *context* 包括零个或多个逗号分隔的*断言*

1.  Paterson 条件：对于上下文中的每个断言

    1.  没有类型变量在断言中出现的次数超过头部中出现的次数

        ```
        class Class a b instance (Class a a) => Class [a] Bool -- bad: 2 * a > 1 * a instance (Class a b) => Class [a] Bool -- bad: 1 * b > 0 * b
        ```

    1.  断言的构造和变量比头部少

        ```
        instance (Class a Int) => Class a Integer -- bad: 2 >= 2
        ```

1.  覆盖条件：对于每个 fundep *left* `->` *right*，*right* 中的类型不能有 *left* 中未提及的类型变量

    ```
    class Class a b | a -> b instance Class a (Maybe a) -- ok: a "covered" by left instance Class Int (Maybe b) -- bad: b not covered instance Class a (Either a b) -- bad: b not covered
    ```

## 可决定 vs. 指数级 -- 谁在乎？

+   编者注：语言的可决定性可能被高估了

    +   毕竟计算机并不是具有无限带子的图灵机

+   这个合法的、可决定的程序会使你的 Haskell 编译器崩溃

    ```
    crash = f5 () where f0 x = (x, x) -- type size 2^{2⁰} f1 x = f0 (f0 x) -- type size 2^{2¹} f2 x = f1 (f1 x) -- type size 2^{2²} f3 x = f2 (f2 x) -- type size 2^{2³} f4 x = f3 (f3 x) -- type size 2^{2⁴} f5 x = f4 (f4 x) -- type size 2^{2⁵}
    ```

+   虽然有很多不能被证明可决定的程序可以编译成功

    +   上一张幻灯片的条件是*充分的*，而不是*必要的*

    +   可能还有其他知道你的程序可以编译的方法

    +   或者也许通过试错来弄清楚？

## [`UndecidableInstances`](http://www.haskell.org/ghc/docs/latest/html/users_guide/type-class-extensions.html#undecidable-instances) 扩展

+   提高了 Paterson 和 Coverage 条件

    +   启用时还可以启用`FlexibleContexts`

+   相反，施加了最大递归深度

    +   默认的最大深度是 20

    +   可以使用 `-fcontext-stack=`*n* 选项来增加，例如：

        ```
        {-# OPTIONS_GHC -fcontext-stack=1024 #-} {-# LANGUAGE UndecidableInstances #-}
        ```

+   有点类似于 C++ 模板

    +   gcc 有一个 `-ftemplate-depth=` 选项

    +   注意 C++11 将最小深度从 17 提高到 1024

    +   同样地，人们已经谈论过增加 GHC 的默认上下文堆栈

## `MonadIO` 重新审视

+   回想一下 `MonadIO` 的定义

    ```
    class (Monad m) => MonadIO m where  liftIO :: IO a -> m a instance MonadIO IO where liftIO = id
    ```

+   目前必须为每个转换器定义一个实例

    ```
    instance MonadIO m => MonadIO (StateT s m) where liftIO = lift . liftIO instance MonadIO m => MonadIO (ReaderT t m) where liftIO = lift . liftIO instance MonadIO m => MonadIO (WriterT w m) where liftIO = lift . liftIO ...
    ```

+   使用 `UndecidableInstances`，一个实例可以覆盖所有的转换器！

    ```
    {-# LANGUAGE FlexibleInstances #-} {-# LANGUAGE UndecidableInstances #-} -- undecidable: assertion Monad (t m) no smaller than head instance (MonadTrans t, MonadIO m, Monad (t m)) => MonadIO (t m) where liftIO = lift . liftIO
    ```

## 扩展的摘要

+   我们已经看到了 6 个与类型类相关的扩展

    ```
    {-# LANGUAGE MultiParamTypeClasses #-} -- very conservative {-# LANGUAGE FlexibleInstances #-} -- conservative {-# LANGUAGE FlexibleContexts #-} -- conservative {-# LANGUAGE FunctionalDependencies #-} -- frowned upon {-# LANGUAGE UndecidableInstances #-} -- very frowned upon {-# LANGUAGE OverlappingInstances #-} -- the most controversial
    ```

    +   并不是所有这些都受到社区的好评

    +   但如果你启用了所有六个，它可以非常强大

+   接下来的讲座将探讨启用所有 6 个扩展可以做什么

    +   受[Hlist](http://homepages.cwi.nl/~ralf/HList/paper.pdf)和[OOHaskell](http://homepages.cwi.nl/~ralf/OOHaskell/paper.pdf)的启发

## 热身：类型级别的布尔值

```
data HFalse = HFalse deriving Show data HTrue = HTrue deriving Show class HNot a b | a -> b where hNot :: a -> b instance HNot HFalse HTrue where hNot _ = HTrue instance HNot HTrue HFalse where hNot _ = HFalse
```

```
*Main> hNot HTrue HFalse *Main> hNot HFalse HTrue
```

+   注意`HNot b nb`中的功能依赖如何计算`b`的否定**在类型级别**

+   还没有使用`OverlappingInstances`，让我们开始吧...

## 对类型进行计算

+   我们能计算两个类型是否相等吗？第一次尝试：

    ```
    class TypeEq a b c | a b -> c where typeEq :: a -> b -> c instance TypeEq a a HTrue where typeEq _ _ = HTrue instance TypeEq a b HFalse where typeEq _ _ = HFalse
    ```

    +   问题：`TypeEq a a HTrue`不比`TypeEq a b HFalse`更具体

    +   ... 但`TypeEq a a HTrue`比`TypeEq a b c`更具体

+   请记住，实例选择从不考虑上下文

    +   仅在拒绝失败断言或从功能依赖中推断类型之后

    +   解决方案：在实例选择后使用另一个功能依赖计算`c`

    ```
    class TypeCast a b | a -> b where typeCast :: a -> b instance TypeCast a a where typeCast = id instance TypeEq a a HTrue where typeEq _ _ = HTrue -- as before instance (TypeCast HFalse c) => TypeEq a b c where typeEq _ _ = typeCast HFalse
    ```

## `TypeEq`的实用性

+   评论：`TypeEq`有点像功能依赖的圣杯

    +   如果你可以实现`TypeEq`，你可以通过区分基本情况和递归情况在类型级别进行递归编程！

    +   但深度依赖于`OverlappingInstances`...

+   例如：让我们为`MonadState`做与`MonadIO`相同的事情

    ```
    -- If t is StateT, then do one thing for (t s m) (base case): instance (Monad m) => MonadState s (StateT s m) where get = StateT $ \s -> return (s, s) put = StateT $ \_ -> return ((), s) -- If t is not StateT, do something else (recursive case): instance (MonadTrans t, MonadState s m, Monad (t m)) => MonadState s (t m) where get = lift get put = lift . put
    ```

    +   `MonadIO`更容易，因为类型`IO`不能匹配参数`(t m)`

    +   不幸的是，`StateT s m`匹配*上述两个*实例头

    +   因此需要`OverlappingInstances`来选择`StateT s m`的第一个实例

## 异构列表

+   最后一个扩展：[`TypeOperators`](http://www.haskell.org/ghc/docs/latest/html/users_guide/data-type-extensions.html#infix-tycons)允许以“`:`”开头的中缀类型

    ```
    data a :*: b = Foo a b type a :+: b = Either a b
    ```

+   使用中缀构造函数来定义异构列表

    ```
    data HNil = HNil deriving Show data (:*:) h t = h :*: !t deriving Show infixr 9 :*: -- Example: data A = A deriving Show data B = B deriving Show data C = C deriving Show foo = (A, "Hello") :*: (B, 7) :*: (C, 3.0) :*: HNil
    ```

    ```
    *Main> foo (A,"Hello") :*: ((B,7) :*: ((C,3.0) :*: HNil)) *Main> :t foo foo :: (A, [Char]) :*: ((B, Integer) :*: ((C, Double) :*: HNil))
    ```

## 异构列表上的操作

+   注意我们的列表由成对组成

    ```
    foo :: (A, [Char]) :*: (B, Integer) :*: (C, Double) :*: HNil foo = (A, "Hello") :*: (B, 7) :*: (C, 3.0) :*: HNil
    ```

    +   将第一个元素视为键或标签，第二个元素视为值--如何查找值？

    ```
    class Select k h v | k h -> v where  (.!) :: h -> k -> v instance Select k ((k, v) :*: t) v where (.!) ((_, v) :*: _) _ = v instance (Select k h v) => Select k (kv' :*: h) v where (.!) (kv' :*: h) k = h .! k
    ```

    ```
    *Main> foo .! A "Hello"
    ```

+   再次注意`OverlappingInstances`的重要性

    +   当查找标签的类型与列表头匹配时需要打破递归

+   可以用来实现各种其他功能（连接等）

## 面向对象编程

+   异构可以实现面向对象编程！

    ```
    returnIO :: a -> IO a returnIO = return data GetVal = GetVal deriving Show data SetVal = SetVal deriving Show data ClearVal = ClearVal deriving Show mkVal n self = do val <- newIORef (n :: Int) returnIO $ (GetVal, readIORef val) :*: (SetVal, writeIORef val) :*: (ClearVal, self .! SetVal $ 0) :*: HNil test = do -- prints 7, then 0 x <- mfix $ mkVal 7 x .! GetVal >>= print x .! ClearVal x .! GetVal >>= print
    ```

+   但为什么要用`mfix`？

## "打结递归"

+   `mfix`允许你通过继承覆盖方法

    +   例如，创建一个忽略`SetVal`消息的“const val”

    ```
    mkConstVal n self = do super <- mkVal n self returnIO $ (SetVal, const $ return ()) :*: super test2 = do x <- mfix $ mkConstVal 7 x .! GetVal >>= print x .! ClearVal x .! GetVal >>= print
    ```

    ```
    *Main> test 7 0 *Main> test2 7 7 
    ```

+   `mkVal`对`SetVal`的调用被`mkConstVal`正确地覆盖了
