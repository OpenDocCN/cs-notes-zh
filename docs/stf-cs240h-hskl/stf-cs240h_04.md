# MVars 再访

+   练习：编写转账函数在账户之间转移资金

    +   `wget` [`cs240h.stanford.edu/transfer.hs`](http://cs240h.scs.stanford.edu/transfer.hs)

    ```
    import Control.Concurrent import Control.Monad type Account = MVar Double transfer :: Double -> Account -> Account -> IO () transfer amount from to = ???
    ```

    +   应该能够与多个线程一起原子地工作

    +   例如，其他线程不应该看到任何一个账户中的资金或两个账户中的资金

    +   如果账户中资金不足，则不要转移资金

+   例子：

    ```
    *Main> :load "transfer.hs" Ok, modules loaded: Main. *Main> main 9.0 1.0
    ```

## 第一次尝试解决方案

```
type Account = MVar Double transfer :: Double -> Account -> Account -> IO () transfer amount from to = modifyMVar_ from $ \bf -> do when (bf < amount) $ fail "not enough money" modifyMVar_ to $ \bt -> return $! bt + amount return $! bf - amount
```

+   上述代码有什么问题？

## 第一次尝试解决方案

```
type Account = MVar Double transfer :: Double -> Account -> Account -> IO () transfer amount from to = modifyMVar_ from $ \bf -> do when (bf < amount) $ fail "not enough money" modifyMVar_ to $ \bt -> return $! bt + amount return $! bf - amount
```

+   上述代码有什么问题？

    1.  在同时在两个方向转移资金时可能会发生死锁

        ```
        forkIO $ transfer 1 ac1 ac2 forkIO $ transfer 1 ac2 ac1
        ```

    1.  当账户中没有足够的资金时抛出异常很丑陋...如果我们只是等待足够的资金出现然后完成转账会怎样？

+   你会如何解决＃1？

## 第二次尝试解决方案

+   策略：对第二个`MVar`使用非阻塞[`tryTakeMVar`](http://www.haskell.org/ghc/docs/latest/html/libraries/base-4.7.0.0/Control-Concurrent-MVar.html#v:tryTakeMVar)

    +   如果失败，释放两者并以不同顺序重试

```
transfer :: Double -> Account -> Account -> IO () transfer amount from to = do let tryTransfer = modifyMVar from $ \ bf -> do when (bf < amount) $ fail "not enough money" mbt <- tryTakeMVar to case mbt of Just bt -> do putMVar to $! bt + amount return (bf - amount, True) Nothing -> return (bf, False) ok <- tryTransfer unless ok $ safetransfer (- amount) to from
```

+   这已经够恶心了吗？

    +   如果没有，在`from`中没有足够的资金时让代码休眠

    +   ...或修复以正确处理异步异常

## [软件事务内存](http://hackage.haskell.org/package/stm)

+   如果我们改用类似数据库的事务呢？

    +   读取和写入一堆变量

    +   写入最初进入日志，然后在最后以原子方式提交

    +   是否出现不一致的视图或与另一个更新冲突？没问题，只需中止并重试整个事务

+   在 C 或 Java 中很难做到

    +   如果事务期间向网络或文件系统写入会怎样？

    +   “外部化”操作不容易回滚

+   但在 Haskell 中，`IO`类型（或其缺乏）可以控制副作用

+   幻灯片灵感来自[[Peyton Jones]](http://research.microsoft.com/en-us/um/people/simonpj/papers/stm/beautiful.pdf)中的优秀文章

## [STM](http://hackage.haskell.org/package/stm)基础知识

+   新的变量类型`TVar a`（有点像[`IORef a`](http://www.haskell.org/ghc/docs/latest/html/libraries/base-4.7.0.0/Data-IORef.html)）

    +   模块[`Control.Concurrent.TVar`](http://hackage.haskell.org/package/stm-2.4.3/docs/Control-Concurrent-STM-TVar.html)提供给你

    ```
    newTVarIO :: a -> IO (TVar a) readTVarIO :: TVar a -> IO a readTVar :: TVar a -> STM a writeTVar :: TVar a -> a -> STM () modifyTVar :: TVar a -> (a -> a) -> STM () -- lazy modifyTVar' :: TVar a -> (a -> a) -> STM () -- strict
    ```

+   新的[`STM`单子](http://hackage.haskell.org/package/stm-2.4.3/docs/Control-Monad-STM.html)允许`TVar`访问但没有不可逆的副作用

    ```
    atomically :: STM a -> IO a
    ```

    +   `atomically`让你从`IO`中运行`STM`计算

    +   你会得到：一个全局锁的语义+细粒度锁的并行性！

    +   作为交换，你放弃了执行外部化的`IO`操作的能力

## STM 示例

```
type Account = TVar Double transfer :: Double -> Account -> Account -> STM () transfer amount from to = do modifyTVar' from (subtract amount) modifyTVar' to (+ amount) main :: IO () main = do ac1 <- newTVarIO 10 ac2 <- newTVarIO 0 atomically $ transfer 1 ac1 ac2
```

+   注意：`subtract a b = b - a`

    +   语言瑕疵：与所有其他二元运算符不同，无法使用`(- a)`创建部分，因为那是一元否定（即`0-a`）

+   如果账户中没有足够的资金，你想等待吗？

## 中止

```
retry :: STM a orElse :: STM a -> STM a -> STM a
```

+   `retry`中止事务

    +   但`STM`知道`TVar`的代码读取以检测冲突...

    +   可以休眠直到某些`TVar`代码读取发生变化而无需显式条件变量

    ```
    transfer :: Double -> Account -> Account -> STM () transfer amount from to = do bf <- readTVar from when (amount > bf) retry modifyTVar' from (subtract amount) modifyTVar' to (+ amount)
    ```

+   `orElse`如果第一个操作中止则尝试第二个操作（如果两个都中止则休眠）

    ```
    transfer2 :: Double -> Account -> Account -> Account -> STM () transfer2 amount from1 from2 to = atomically $ transferSTM amount from1 to `orElse` transferSTM amount from2 to
    ```

    +   实际上提供了嵌套事务

## 强制执行不变量

```
alwaysSucceeds :: STM a -> STM ()
```

+   `alwaysSucceeds`在每次事务后添加不变量检查

    （不变量抛出异常或其返回值被忽略）

+   例如：假设你对负账户余额很担心

```
newAccount :: Double -> STM Account newAccount balance = do tv <- newTVar balance alwaysSucceeds $ do balance <- readTVar tv when (balance < 0) $ fail "negative balance" return tv bogus :: IO () bogus = do ac <- atomically $ newAccount 10 atomically $ modifyTVar ac (subtract 15)
```

+   将立即捕获错误并回滚错误事务

```
*Main> bogus *** Exception: negative balance
```

## 转换话题...

+   让我们回到纯函数式代码

+   编译器如何在内存中表示数据？

## 天真的 Haskell 数据表示

+   一个值需要一个构造函数，加上参数

    +   在运行时，需要确定值的构造函数，但不需要确定其类型

        （编译器已经对程序进行了类型检查，因此没有运行时类型检查）

    ```
    struct Val { unsigned long constrno; /* constructor # */ struct Val *args[]; /* flexible array */ };
    ```

    +   对于像`[Int]`这样的类型，`constrno`可能为`[]`的 0，`(:)`的 1，其中`[]`具有 0 大小的`args`，`(:)`具有 2 个元素的`args`

    +   对于像`Int`这样的类型，`constrno`可以是实际的整数，没有`args`

    +   对于单构造函数类型（例如`Point`），不使用`constrno`

+   到目前为止我们的方法存在问题

    +   没有办法表示异常或惰性计算

    +   垃圾收集器需要知道`args`中有多少元素

    +   诸如`Int`之类的小值总是需要追踪指针

## 增加间接层来描述值

```
typedef struct Val { const struct ValInfo *info; struct Val *args[]; } Val; /* Statically allocated at compile time. Only one per  * constructor (or closure-creating expression, etc.) */ struct ValInfo { struct GCInfo gcInfo; /* for garbage collector */ enum { CONSTRNO, FUNC, THUNK, IND } tag; union { unsigned int constrno; Val *(*func) (const Val *closure, const Val *arg); Exception *(*thunk) (Val *closure); }; };
```

+   `gcInfo`指示`args`中有多少个`Val *`以及它们的位置

+   `tag == CONSTRNO`表示`constrno`有效，如上一张幻灯片所示

+   `tag == IND`表示`args[0]`是指向另一个`Val`的间接*转发指针*，联合体未使用；如果`args`的大小增长，则此方法很有用

## 函数值

+   具有`ValInfo`的`tag == FUNC`的`Val`使用`func`字段

    ```
     Val *(*func) (const Val *closure, const Val *arg);
    ```

+   要将函数`f`应用于参数`a`（其中两者都是类型为`Val *`的值）：

    ```
     f->info->func (f, a);
    ```

+   请注意，`func`的第一个参数（`closure`）是函数`Val`本身

    +   提供一个*闭包*环境，以便可以重复使用`ValInfo`/`func`

+   `func`的第二个参数（`arg`）是函数正在评估的参数`a`

+   假设所有函数都只接受一个参数

    +   逻辑上这是没问题的，因为我们有柯里化

    +   为了性能，真正的编译器必须优化多参数情况

## 闭包

+   顶层绑定不需要`func`的`closure`参数

    ```
    addOne :: Int -> Int addOne x = x + 1
    ```

    +   函数`addOne`的`Val`可以具有零长度的`args`

+   本地绑定可能需要`closure`中的环境值

    ```
    add :: Int -> (Int -> Int) add n = \m -> addn m where addn m = n + m
    ```

    +   编译器只会为本地函数`addn`生成一次代码

    +   但从逻辑上讲，每次调用`add`都会有一个单独的`addn`函数（带有不同的`n`）

    +   因此，每个`addn`实例都是不同的`Val`，但都共享相同的`ValInfo`

    +   在每个`Val`中使用`args[0]`来指定`n`的值

## 惰性计算值

+   一个带有`tag == THUNK`的`Val`使用`ValInfo`中的`thunk`字段

    ```
     Exception *(*thunk) (Val *closure);
    ```

    +   *更新* `v`（将其转换为非惰性）或返回一个非`NULL`的`Exception *`

+   要评估一个惰性计算：

    ```
     v->info->thunk (v);
    ```

+   惰性计算和函数之间有两个重要区别

    +   一个函数需要一个参数，而一个惰性计算不需要

    +   函数值是不可变的，而惰性计算会更新自身

+   还要注意，惰性计算可能会抛出异常

    +   函数也可以，但为了简单起见，让函数返回一个会抛出异常的惰性计算

## 强制执行

+   将 thunk 转换为非 thunk 称为*强制*它

+   如果一个 thunk 的返回值不适合 thunk 的`args`怎么办？

    +   这就是为什么我们有`IND` `ValInfo`标记--分配新的`Val`，在旧的`Val`中放置间接转发指针

+   一个可能的强制实现，遍历`IND`指针：

    ```
    Exception *force (Val **vp) { for (;;) { if ((*vp)->info->tag == IND) *vp = (*vp)->arg[0]; else if ((*vp)->info->tag == THUNK) { Exception *e = (*vp)->info->thunk (*vp); if (e) return e; } else return NULL; } }
    ```

## 柯里化

+   让我们使用柯里化的简单实现（GHC 非常复杂）

+   将`closure->args`设置为先前柯里化参数列表的头部

    ```
    const3 :: a -> b -> c -> a const3 a b c = a
    ```

    +   编译器发出 3 个`ValInfo`和 3 个`const3`函数

    +   顶层绑定的`ValInfo`具有`func = const3_1`

    +   `const3_1`创建`Val v1`，其中`arg[0]`是第一个参数（`a`），`info->func = const3_2`

    +   `const3_2`创建一个`Val v2`，其中`arg[0]`是第二个参数（`b`），`arg[1]`是`v1`，`info->func`是`const3_3`

    +   `const3_3`可以访问所有参数，并实际实现`const3`

+   共享参数具有共同的参数尾部，只评估一次

    ```
     let f = const3 (superExpensive 5) -- v1, evaluated once in (f 1 2, f 3 4)
    ```

## 柯里化示例的代码

```
const3 :: a -> b -> c -> a const3 a b c = a
```

```
Val *const3_1 (Val *ignored, Val *a) { v = (Val *) gc_malloc (offsetof (Val, args[1])); v->info = &const3_2_info; /* func = const3_2 */ v->args[0] = a; return v; } Val *const3_2 (Val *closure, Val *b) { v = (Val *) gc_malloc (offsetof (Val, args[2])); v->info = &const3_3_info; /* func = const3_3 */ v->args[0] = b; v->args[1] = closure; return v; } Val *const3_3 (Val *v, Val *c) { return v->args[1]->args[0]; }
```

## 未装箱类型

+   不幸的是，现在`Int`有更多的开销

    +   要使用，必须检查`i->info->tag`，然后访问`i->info->constr`

    +   此外，每个数字都需要一个不同的`ValInfo`结构（但`ValInfo`是静态分配的--你怎么知道程序将需要哪些数字）

+   思路：有特殊的*未装箱*类型，不使用`struct Val`

    ```
    union Arg { struct Val *boxed; /* most values are boxed */ unsigned long unboxed; /* "primitive" values */ }; typedef struct Val { const struct ValInfo *info; union Arg args[]; /* args can be boxed or unboxed */ } Val;
    ```

    +   未装箱类型没有构造函数，不能是 thunk（没有`ValInfo`）

    +   可以适合单个寄存器或取代`Val *`参数的位置

    +   必须扩展`GCInfo`以识别哪些参数是装箱的，哪些不是

## GHC 中的未装箱类型

+   GHC 暴露了未装箱类型（尽管不是 Haskell 的一部分）

    +   符号使用`#`字符--必须使用[`-XMagicHash`](http://www.haskell.org/ghc/docs/latest/html/users_guide/syntax-extns.html#magic-hash)选项启用

    +   有未装箱类型（`Int#`）和对它们的原始操作（`+#`）

    +   参见[GHC.Prim](http://www.haskell.org/ghc/docs/latest/html/libraries/ghc-prim-0.3.1.0/GHC-Prim.html)或在 GHCI 中键入"`:browse GHC.Prim`"

    +   也有[未装箱常量](http://www.haskell.org/ghc/docs/latest/html/users_guide/syntax-extns.html#magic-hash)--`2#`, `'a'#`, `2##`（无符号），`2.0##`

+   `Int`到底是什么？

    +   单构造函数数据类型，带有单个未装箱参数

    ```
    Prelude> :set -XMagicHash Prelude> :m +GHC.Types GHC.Prim Prelude GHC.Types GHC.Prim> :i Int data Int = I# Int# -- Defined in GHC.Types ... Prelude GHC.Types GHC.Prim> case 1 of I# u -> I# (u +# 2#) 3
    ```

    +   让`Int`包含 thunk，但一旦评估就避免指针解引用

## 未装箱类型的限制

+   不能用未装箱类型实例化类型变量

    ```
    {-# LANGUAGE MagicHash #-} import GHC.Prim data FastPoint = FastPoint Double# Double# -- ok fp = FastPoint 2.0## 2.0## -- ok -- Error: can't pass unboxed type to polymorphic function fp' = FastPoint 2.0## (id 2.0##) -- Error: can't use unboxed type as type parameter noInt :: Maybe Int# noInt = Nothing
    ```

+   通过使未装箱类型成为不同种类的类型来强制执行

    ```
    Prelude GHC.Types GHC.Prim> :kind Int# Int# :: #
    ```

    +   请记住类型变量的种类是星号（∗，∗ → ∗等），而不是`#`

    +   多态性有效，因为所有种类为∗的类型都表示为`Val *`

## 重新审视`seq`

+   回想一下`seq :: a -> b -> b`

    +   如果强制`seq a b`，那么首先强制`a`，然后强制并返回`b`

+   考虑以下代码（类似于并发讲座）：

    ```
    infiniteLoop = infiniteLoop :: Char -- loops forever seqTest1 = infiniteLoop `seq` "Hello" -- loops forever seqTest2 = str `seq` length str -- returns 6 where str = infiniteLoop:"Hello"
    ```

    +   `seqTest1`永远挂起，而`seqTest2`愉快地返回 6

+   `seq`只强制`Val`，而不是`Val`的`arg`字段

    +   `seqTest2`的`seq`强制`str`的构造函数`(:)`，但不强制头部或尾部

    +   这被称为将`str`放入*弱头正规形式*（WHNF）

    +   无法完全评估任意数据类型（但参见[Control.DeepSeq](http://hackage.haskell.org/packages/archive/deepseq/latest/doc/html/Control-DeepSeq.html)）

## 例子：假设的`seq`实现

```
const struct ValInfo seq_info = { some_gcinfo, THUNK, .thunk = &seq_thunk }; Val *seq_2 (Val *closure, Val *b) { /* assume seq_1 put first arg of (seq a b) in closure */ c = (Val *) gc_malloc (offsetof (Val, args[2])); c->info = &seq_info; c->args[0] = closure->args[0]; c->args[1] = b; return c; } Exception *seq_thunk (Void *c) { Exception *e = force (&c->args[0]); if (!e) { c->info = &ind_info; /* ValInfo with tag = IND */ c->args[0] = c->args[1]; /* forward to b */ } return e; }
```

## 重新审视严格性

+   回顾数据声明中字段的严格性标志

    ```
    data IntWrapper = IntWrapper !Int
    ```

    +   `Int`之前有`!`，表示它必须是严格的

    +   严格意味着`Int`的`ValInfo`不能有`tag` `THUNK`或`IND`

+   访问严格的`Int`只会触及一个缓存行

    +   回顾`data Int = I# Int#`只有一个构造函数

    +   加上严格标志意味着`tag == CONSTRNO`，所以知道`ValInfo`中有什么

    +   另外`Int#`是非装箱的

    +   因此，一旦`IntWrapper`被强制，立即可以安全地访问`Int`

        ```
         myIntWrapper.arg[0].boxed->arg[0].unboxed
        ```

## 严格性的语义效果

+   严格性主要用于优化

    +   避免建立长链的 thunks

    +   为了节省检查 thunk 是否已评估的开销

+   但具有语义效果：非严格的`Int`不仅仅是一个数字

    +   也可以在评估时抛出异常或永远循环

    +   这种行为可以被建模为一个特殊值 ⊥（"底部"）

    +   因此，`Int`的值为{0, 1}⁶⁴ ∪ {⊥}

    +   包含值 ⊥ 的类型称为*lifted*

+   注意 1：非装箱类型必然是非 lifted 的

+   注意 2：`!Int`不是一种一流类型，只对`data`字段有效

    ```
    data SMaybe a = SJust !a | SNothing -- ok, data field strictAdd :: !Int -> !Int -> !Int -- error type StrictMaybeInt = Maybe !Int -- error
    ```

## 重新审视`case`语句

+   `case`语句模式匹配可以强制 thunks

    +   一个*不可辩驳*的模式总是匹配的

    +   由单个变量或`_`组成的模式是不可辩驳的

    +   任何非不可辩驳的模式都会强制评估参数

    +   匹配从上到下进行，而在备选方案内从左到右进行

+   函数模式匹配与`case`相同

    +   回想`undefined :: a`是一个值为 ⊥ 的`Prelude`符号

    ```
    f ('a':'b':rest) = rest f _ = "ok" test1 = f (undefined:[]) -- error test2 = f ('a':undefined) -- error test3 = f ('x':undefined) -- "ok" (didn't force tail)
    ```

+   在模式之前加上`~`使其不可辩驳

    ```
    three = (\ ~(h:t) -> 3) undefined -- evaluates to 3
    ```

## `newtype`声明

+   我们已经看到了引入新类型的两种方式

    +   `data` -- 创建一个新的（装箱的）类型，增加了`Val`包装器的开销

    +   `type` -- 为现有类型创建一个别名，没有额外开销

+   有时你想要一个由现有类型实现的新类型

    +   例如，可能希望`Meters`、`Seconds`、`Grams`都由`Double`实现

    +   使用`type`会使它们变得同义，容易出错

    +   可能希望为每个实例使用不同的`Show`，这在`type`中是不可能的

    +   可以说`data Meters = Meters Double` -- 但会增加开销

+   `newtype`关键字引入了没有额外开销的新类型

    +   使用方式与`data`相同，但限于一个构造函数和一个字段

    +   这是因为所有类型检查都是在编译时进行的

## `newtype`语义

+   这两个声明之间的语义差异是什��？

    ```
    newtype NTInt = NTInt Int deriving (Show)
    ```

    ```
    data SInt = SInt !Int deriving (Show)
    ```

+   练习：假设你有

    ```
    uNTInt = NTInt undefined uSInt = SInt undefined
    ```

    编写代码，使`uNTInt`与`uSInt`的行为不同

## `newtype`语义

+   这两个声明之间的语义差异是什么？

    ```
    newtype NTInt = NTInt Int deriving (Show)
    ```

    ```
    data SInt = SInt !Int deriving (Show)
    ```

+   `NTInt`构造函数是一个"虚假"的仅在编译时存在的构造

    +   解构`newtype`的`case`语句编译成空

    ```
    newtype NTInt = NTInt Int deriving (Show) uNTInt = NTInt undefined testNT = case uNTInt of NTInt _ -> True -- returns True
    ```

    +   相反，强制一个值（通过匹配构造函数）会强制严格字段

    ```
    data SInt = SInt !Int deriving (Show) uSInt = SInt undefined testS = case uSInt of SInt _ -> True -- undefined
    ```

## [`UNPACK`](http://www.haskell.org/ghc/docs/latest/html/users_guide/pragmas.html#unpack-pragma)指令

+   当适用时，`newtype`几乎总是比`data`更好

+   多字段数据类型怎么办？

    ```
    data TwoInts = TwoInts !Int !Int
    ```

    +   字段是严格的，我们知道它们将具有`CONSTRNO` `ValInfo`

    +   为什么不直接将`Int#`直接放入`TwoInts` `Val`的`args`中？

    +   GHC 提供了一个`UNPACK`指令来做到这一点

        ```
        data TwoInts = TwoInts {-# UNPACK #-} !Int {-# UNPACK #-} !Int
        ```

    +   适用于任何具有单构造器数据类型的严格字段

+   与`newtype`不同，`UNPACK`并不总是胜出

    +   如果将字段作为参数传递，将需要重新装箱它

+   `-funbox-strict-fields`标志展开*所有*严格字段

## [`ByteString`](http://www.haskell.org/ghc/docs/latest/html/libraries/bytestring-0.10.4.0/index.html)

+   Haskell `String`显然不是很高效

+   严格`ByteString`可以高效地操作原始字节

    ```
    import qualified Data.ByteString as S import qualified Data.ByteString.Char8 as S8
    ```

    +   实现了类似于列表的接口：`S.head`、`S.tail`、`S.length`、`S.foldl`、`S.cons`（类似于`:`）、`S.empty`（类似于`[]`）、`S.hPut`（类似于`hPutStr`）、`S.readFile`

    +   必须导入限定以避免名称冲突

    +   `S.pack`和`S.unpack`转换为/从`[Word8]`

    +   `S8`具有与`S`相同的函数，但使用`Char`而不是`Word8`--这意味着您会丢失`Char`的高位（使用来自[utf8-string](http://hackage.haskell.org/package/utf8-string)的[`toString`](http://hackage.haskell.org/packages/archive/utf8-string/0.3.7/doc/html/Data-ByteString-UTF8.html#v:toString)来避免丢失）

+   实现

    ```
    data ByteString = PS {-# UNPACK #-} !(ForeignPtr Word8) {-# UNPACK #-} !Int -- offset {-# UNPACK #-} !Int -- length
    ```

## [惰性`ByteString`](http://www.haskell.org/ghc/docs/latest/html/libraries/bytestring-0.10.4.0/Data-ByteString-Lazy.html)

+   同一软件包实现了[*惰性* `ByteString`](http://www.haskell.org/ghc/docs/latest/html/libraries/bytestring-0.10.4.0/Data-ByteString-Lazy.html)

    ```
    import qualified Data.ByteString.Lazy as L import qualified Data.ByteString.Lazy.Char8 as L8
    ```

    +   提供了与严格`ByteString`模块大部分相同的函数

+   令人困惑的是两个模块对许多事物使用相同的名称

    +   查看导入限定以理解代码是很重要的

    +   更糟糕的是：文档没有限定符号名称

        提示：**将鼠标悬停在符号上并查看 URL 以找出模块**

    +   此外，`S.ByteString`和`S8.ByteString`是相同类型（重新导出的），类似地，`L.ByteString`和`L8.ByteString`也是如此

    +   `S.ByteString`和`L.ByteString` *不*是相同类型，但可以转换：

    ```
    fromChunks :: [S.ByteString] -> L.ByteString toChunks :: L.ByteString -> [S.ByteString]
    ```

## 惰性`ByteString`实现

+   惰性`ByteString`是以严格的方式实现的

    ```
    data ByteString = Empty | Chunk {-# UNPACK #-} !S.ByteString ByteString
    ```

    +   不变性：`Chunk`的第一个参数（`S.ByteString`）永远不会为`null`

    +   基本上是严格`ByteString`的链表

    +   Head 是严格的，tail 不是，允许惰性计算或 I/O

+   何时使用严格/惰性`ByteString`？

    +   当需要惰性时显然使用惰性（例如，惰性 I/O，无限或循环字符串等）

    +   惰性也在连接方面更快（需要构建一个新的`S.ByteString`列表，但不复制它们包含的数据）

    +   严格使得实现诸如字符串搜索之类的功能变得更加容易

    +   将严格转换为惰性`ByteString`是廉价的，反之则不是（因此，如果一个库可以在惰性`ByteString`上高效工作，最好暴露该功能）
