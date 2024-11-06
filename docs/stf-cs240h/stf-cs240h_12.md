# 一个 Haskell 编译器

## David Terei

## 为什么要了解 GHC 的工作原理？

+   理解 Core 和 STG - 性能。

+   熟悉函数术语。

+   理解执行模型 - 合理的成本模型。

## GHC 的流水线

Haskell -> GHC Haskell -> Core -> STG -> Cmm -> Assembly

## GHC 支持在不安全变体上的 Haskell

原始类型（GHC.Prim）：

+   Char#、Int#、Word#、Double#、Float#

+   Array#、ByteArray#、ArrayArray#，

+   MutVar#、TVar#、MVar#

+   State#、exceptions

所有原始类型都是*未提升*的 - 不能包含 ⊥。

## GHC 支持在不安全变体上的 Haskell

所有 Int 的变体（In8、Int16、Int32、Int64）在 64 位机器上内部由 Int#（64 位）表示。

```
data Int32 = I32# Int# deriving (Eq, Ord, Typeable) instance Num Int32 where (I32# x#) + (I32# y#) = I32# (narrow32Int# (x# +# y#)) ...
```

数据构造函数*提升*了一个类型，允许 ⊥。

## GHC 通过 RealWorld 令牌实现 IO

+   IO Monad 是一个状态传递的单子。

```
newtype IO a = IO (State# RealWorld -> (# State# RealWorld, a #)) returnIO :: a -> IO a returnIO x = IO $ \ s -> (# s, x #) bindIO :: IO a -> (a -> IO b) -> IO b bindIO (IO m) k = IO $ \ s -> case m s of (# new_s, a #) -> unIO (k a) new_s
```

+   `RealWorld` 令牌通过数据依赖强制排序。

```
unsafePerformIO :: IO a -> a unsafePerformIO m = unsafeDupablePerformIO (noDuplicate >> m) unsafeDupablePerformIO :: IO a -> a unsafeDupablePerformIO (IO m) = lazy (case m realWorld# of (# _, r #) -> r)
```

+   各种不安全函数丢弃 `RealWorld` 令牌。

## Core：一个小型函数中间语言

+   思路：将 Haskell 映射到一个更容易优化和编译的小语言。

+   函数式惰性语言

+   它只包含少量结构！

```
variables, literals, let, case, lambda abstraction, application
```

+   一般来说，`let` 表示分配，`case` 表示评估。

## 一个幻灯片中的 Core

```
data Expr b -- "b" for the type of binders,  = Var Id | Lit Literal | App (Expr b) (Arg b) | Lam b (Expr b) | Let (Bind b) (Expr b) | Case (Expr b) b Type [Alt b] | Type Type | Cast (Expr b) Coercion | Coercion Coercion | Tick (Tickish Id) (Expr b) data Bind b = NonRec b (Expr b) | Rec [(b, (Expr b))] type Arg b = Expr b type Alt b = (AltCon, [b], Expr b) data AltCon = DataAlt DataCon | LitAlt Literal | DEFAULT
```

现在让我们看看 Haskell 是如何编译成 [Core](http://hackage.haskell.org/trac/ghc/wiki/Commentary/Compiler/CoreSynType) 的。

## GHC Haskell 到 Core：单态函数

Haskell

```
idChar :: Char -> Char idChar c = c
```

Core

```
idChar :: GHC.Types.Char -> GHC.Types.Char [GblId, Arity=1, Caf=NoCafRefs] idChar = \ (c :: GHC.Types.Char) -> c
```

## GHC Haskell 到 Core：多态函数

Haskell

```
id :: a -> a id x = x idChar2 :: Char -> Char idChar2 = id
```

Core

```
id :: forall a. a -> a id = \ (@ a) (x :: a) -> x idChar2 :: GHC.Types.Char -> GHC.Types.Char idChar2 = id @ GHC.Types.Char
```

## GHC Haskell 到 Core：多态函数

Haskell

```
map :: (a -> b) -> [a] -> [b] map _ [] = [] map f (x:xs) = f x : map f xs
```

Core

```
map :: forall a b. (a -> b) -> [a] -> [b] map = \ (@ a) (@ b) (f :: a -> b) (xs :: [a]) -> case xs of _ { [] -> GHC.Types.[] @ b; : y ys -> GHC.Types.: @ b (f y) (map @ a @ b f ys) }
```

新的 case 语法使评估正在发生的事情变得明显：

```
case e of result { __DEFAULT -> result }
```

## Where 转换为 let

Haskell

```
dox :: Int -> Int dox n = x * x where x = n + 2
```

Core

```
dox :: GHC.Types.Int -> GHC.Types.Int dox = \ (n :: GHC.Types.Int) -> let {  x :: GHC.Types.Int x = GHC.base.plusInt n (GHC.Types.I# 2) } in GHC.base.multInt x x
```

## 模式匹配转换为 case 语句

Haskell

```
iff :: Bool -> a -> a -> a iff True x _ = x iff False _ y = y
```

Core

```
iff :: forall a. GHC.Bool.Bool -> a -> a -> a iff = \ (@ a) (d :: GHC.Bool.Bool) (x :: a) (y :: a) -> case d of _ GHC.Bool.False -> y GHC.Bool.True -> x
```

## 类型类转换为字典

Haskell

```
typeclass MyEnum a where  toId :: a -> Int  fromId :: Int -> a
```

Core

```
data MyEnum a = DMyEnum (a -> Int) (Int -> a) toId :: forall a. MyEnum a => a -> GHC.Types.Int toId = \ (@ a) (d :: MyEnum a) (x :: a) -> case d of _ DMyEnum f1 _ -> f1 x fromId :: forall a. MyEnum a => GHC.Types.Int -> a fromId = \ (@ a) (d :: MyEnum a) (x :: a) -> case d of _ DMyEnum _ f2 -> f2 x
```

## 为每个实例构造一个字典

Haskell

```
instance MyEnum Int where toId = id fromId = id
```

Core

```
fMyEnumInt :: MyEnum GHC.Types.Int fMyEnumInt = DMyEnum @ GHC.Types.Int (id @ GHC.Types.Int) (id @ GHC.Types.Int)
```

## 从字典构造字典

Haskell

```
instance (MyEnum a) => MyEnum (Maybe a) where toId (Nothing) = 0 toId (Just n) = toId n fromId 0 = Nothing fromId n = Just $ fromId n
```

Core

```
fMyEnumMaybe :: forall a. MyEnum a => MyEnum (Maybe a) fMyEnumMaybe = \ (@ a) (dict :: MyEnum a) -> DMyEnum @ (Maybe a) (fMyEnumMaybe_ctoId @ a dict) (fMyEnumMaybe_cfromId @ a dict) fMyEnumMaybe_ctoId :: forall a. MyEnum a => Maybe a -> Int fMyEnumMaybe_ctoId = \ (@ a) (dict :: MyEnum a) (mx :: Maybe a) -> case mx of _ Nothing -> I# 0 Just n -> case (toId @ a dict n) of _ I# y -> I# (1 +# y)
```

## UNPACK 解压类型

Haskell

```
data Point = Point {-# UNPACK #-} !Int {-# UNPACK #-} !Int
```

Core

```
data Point = Point Int# Int#
```

+   只有一个 Point 的数据类型存在，GHC 不会复制它。

## UNPACK 不总是一个好主意

Haskell

```
addP :: P -> Int addP (P x y ) = x + y
```

Core

```
addP :: P -> Int addP = \ (p :: P) -> case p of _ { P x y -> case +# x y of z { __DEFAULT -> I# z } }
```

+   这里有很棒的代码，可以使用未装箱类型。

## UNPACK 不总是一个好主意

Haskell

```
module M where {-# NOINLINE add #-} add x y = x + y module P where addP_bad (P x y) = add x y
```

Core

```
addP_bad = \ (p :: P) -> case p of _ { P x y -> let { x' = I# x y' = I# y  } in M.add x' y' }
```

+   需要不幸地重新装箱这些类型。

## Core 摘要

+   查看 Core 以了解代码的性能如何。

+   可以看到装箱和去箱化。

+   语言仍然是惰性的，但 `case` 表示评估。

## GHC 中间：*Core -> Core*

GHC 所做的许多优化都是通过核心到核心的转换来实现的。

让我们看看其中的两个：

+   严格性和去箱化

+   SpecConstr

```
Fun Fact: Estimated that functional languages gain 20 - 40% improvement from inlining Vs. imperative languages which gain 10 - 15%
```

## 严格性和去箱化

考虑在 Haskell 中实现这个阶乘：

```
fac :: Int -> Int -> Int fac x 0 = a fac x n = fac (n*x) (n-1)
```

+   在 Haskell 中，`x` 和 `n` 必须由指向可能未评估对象（thunks）的指针表示

+   即使评估了，仍然由堆上的“装箱”值表示

## 严格性和去箱化

Core

```
fac :: Int -> Int -> Int fac = \ (x :: Int) (n :: Int) -> case n of _ { I# n# -> case n# of _ 0# -> x __DEFAULT -> let { one = I# 1 n' = n - one x' = n * x } in fac x' n'
```

+   在递归调用之前分配 thunks 并装箱参数

+   但 `fac` 将立即评估 thunks 并解压值！

## 带有严格性分析的 GHC

使用优化编译 `fac`。

```
wfac :: Int# -> Int# -> Int# wfac = \ x# n# -> case n# of _ 0# -> x# _ -> case (n# -# 1#) of n'# _ -> case (n# *# x#) of x'# _ -> $wfac x'# n'# fac :: Int -> Int -> Int fac = \ a n -> case a of I# a# -> case n of I# n# -> case ($wfac a# n#) of r# -> I# r#
```

+   创建一个优化的“工作者”并保留原始函数作为“包装器”以保持接口。

+   必须保留⊥的语义 - `fac` ⊥ `n = optimized(fac)` ⊥ `n`

## SpecConstr：将严格性分析扩展到路径

SpecConstr 的想法是扩展严格性和取消装箱，但是对于在每个代码路径中参数不严格的函数。

考虑这个 Haskell 函数：

```
drop :: Int -> [a] -> [a] drop n [] = [] drop 0 xs = xs drop n (x:xs) = drop (n-1) xs
```

+   对第一个参数不严格：

    +   `drop` ⊥ [] = []

    +   `drop` ⊥ (x:xs) = ⊥

## SpecConstr：将严格性分析扩展到路径

因此我们得到这段代码而不需要额外的优化：

```
drop n xs = case xs of [] -> [] (y:ys) -> case n of I# n# -> case n# of 0 -> [] _ -> let n' = I# (n# -# 1#) in drop n' ys
```

+   但在第一次调用 drop 之后，我们对`n`是严格的并且总是评估它！

## SpecConstr

SpecConstr 通过利用这一点创建`drop`的专门版本，只有在我们通过第一个检查后才调用它。

```
drop n xs = case xs of [] -> [] (y:ys) -> case n of I# n# -> case n# of 0 -> [] _ -> drop' (n# -# 1#) xs -- works with unboxed n drop' n# xs = case xs of [] -> [] (y:ys) -> case n# of 0# -> [] _ -> drop (n# -# 1#) xs
```

+   为了防止代码大小膨胀，GHC 限制它创建的专门函数的数量（使用`-fspec-constr-threshol`和`-fspec-constr-count`标志指定）。

## STG 代码

+   在 Core 之后，GHC 编译到另一种名为 STG 的中间语言。

+   STG 与 Core 非常相似，但有一个很好的附加属性：

    +   惰性是‘显式的’

    +   `case` = *评估* 和唯一的评估发生的地方（在 Core 中是真的）

    +   `let` = *分配* 和唯一的分配发生的地方（在 Core 中不是这样）

    +   因此在 STG 中，我们可以明确看到使用`let`为惰性分配 thunks

+   要查看 STG，请使用：

    ```
    ghc -ddump-stg A.hs > A.stg
    ```

## STG 代码

Haskell

```
map :: (a -> b) -> [a] -> [b] map f [] = [] map f (x:xs) = f x : map f xs
```

STG

```
map :: forall a b. (a -> b) -> [a] -> [b] map = \r [f xs] case xs of _ [] -> [] [] : z zs -> let { bds = \u [] map f zs; bd = \u [] f z; } in : [bd bds]
```

+   Lambda 抽象为`[arg1 arg2] f`

+   `\r` - 可重入

+   `\u` - 可更新（即 thunk）

## 图缩减作为 Haskell 的计算模型

图缩减是惰性函数式语言的良好计算模型。

```
f g = let x = 2 + 2 in (g x, x)
```

## 图缩减作为 Haskell 的计算模型

图缩减是惰性函数式语言的良好计算模型。

```
f g = let x = 2 + 2 in (g x, x)
```

## 图缩减作为 Haskell 的计算模型

图缩减是惰性函数式语言的良好计算模型。

+   图缩减允许惰性评估和共享

+   *let*: 向图中添加新节点。

+   *case*: 表达式评估，导致图被减少。

+   当节点被减少时，它将被替换（或*更新*）为其结果

可以将您的 Haskell 程序视为通过添加新节点到图或减少现有节点来进行。

## GHC 执行模型

+   GHC 使用闭包作为统一表示。

+   堆中的所有对象都是闭包。

+   堆栈帧是一个闭包。

+   GHC 使用继续传递风格。

+   总是跳转到顶部堆栈帧以返回。

+   函数将提前准备堆栈以设置调用链。

## 闭包表示

| 闭包 |  |  | 信息表 |
| --- | --- | --- | --- |
|  |  |  |  |

+   Header 通常只是指向闭包代码和元数据的指针。

+   通过正负偏移量只需一个指针即可获得。

+   Payload 包含闭包的环境（例如自由变量，函数参数）

## 数据闭包

```
data G = G (Int -> Int) {-# UNPACK #-} !Int
```

+   `[Header | Pointers... | Non-pointers...]`

+   Payload 是构造函数的值

+   构造函数的入口代码只返回

```
jmp Sp[0]
```

## 函数闭包

```
f = \x -> let g = \y -> x + y in g x
```

+   [Header | Pointers… | Non-pointers…]

+   Payload 是绑定的自由变量，例如，

    +   `[ &g | x ]`

+   入口代码是函数代码

## 部分应用闭包（PAP）

```
foldr (:)
```

+   `[Header | 元数 | Payload 大小 | 函数 | Payload]`

+   PAP 的元数（应用了 1 个参数的元数为 3 的函数会得到元数为 2 的 PAP）

+   函数是部分应用的函数的闭包

## **Thunk closures**

```
range = [1..100]
```

+   `[Header | 指针... | 非指针...]`

+   Payload 包含表达式的自由变量

+   与函数闭包不同之处在于它们可以被更新

+   入口代码是表达式的代码

## 调用约定

+   在 X86 32 位系统上 - 所有参数通过栈传递

+   在 X86 64 位系统上 - 前 5 个参数通过寄存器传递，其余通过栈传递

+   `R1` 寄存器在 Cmm 代码中通常是指向当前闭包的指针（类似于面向对象语言中的 `this`）。

## 处理 thunk 更新

+   一旦求值，thunk 应该更新它们在图中的节点为计算出的值。

+   GHC 使用*自更新模型* - 代码无条件跳转到一个 thunk。由 thunk 自己更新自己，用值替换代码。

## 处理 thunk 更新

```
mk :: Int -> Int mk x = x + 1
```

```
// thunk entry - setup stack, evaluate x mk_entry() entry: if (Sp - 24 < SpLim) goto gc; I64[Sp - 16] = stg_upd_frame_info; // setup update frame (closure type) I64[Sp - 8] = R1; // set thunk to be updated (payload) I64[Sp - 24] = mk_exit; // setup continuation (+) continuation Sp = Sp - 24; // increase stack R1 = I64[R1 + 8]; // grab 'x' from environment jump I64[R1] (); // eval 'x' gc: jump stg_gc_enter_1 (); }
```

## 处理 thunk 更新

```
mk :: Int -> Int mk x = x + 1
```

```
// thunk exit - setup value on heap, tear-down stack mk_exit() entry: Hp = Hp + 16; if (Hp > HpLim) goto gc; v::I64 = I64[R1] + 1; // perform ('x' + 1) I64[Hp - 8] = GHC_Types_I_con_info; // setup Int closure I64[Hp + 0] = v::I64; R1 = Hp; // point R1 to computed thunk value Sp = Sp + 8; // pop stack jump (I64[Sp + 0]) (); // jump to continuation ('stg_upd_frame_info') gc: HpAlloc = 16; jump stg_gc_enter_1 (); }
```

## stg_upd_frame_info 代码更新一个 thunk 的值

+   要更新一个 thunk 的值，我们需要改变它的头指针。

+   现在应该指向一个简单返回的代码。

+   Payload 现在也需要包含数值。

+   朴素的解决方案是在每次访问 thunk 时同步。

+   但我们不需要！thunk 上的竞争是可以接受的，因为我们可以依赖纯度。竞争只会导致工作的重复。

## stg_upd_frame_info 代码更新一个 thunk 的值

Thunk 闭包：

+   `[Header | Payload]`

+   `Header` = `[ 信息表指针 | 结果槽 ]`

+   当 thunk 未求值时，结果槽为空。

+   更新代码，首先将结果放入结果槽，然后更改信息表指针。

+   在 GHC 支持的所有架构上都可以不同步地进行（需要写屏障）。

## 避免进入值

+   评估模型是我们总是进入一个闭包，即使是值。

+   这对性能来说很差，我们更喜欢避免每次都进入值。

+   GHC 所做的一个优化是*指针标记*。这个技巧是利用指针的最后几位通常为零（32 位系统为最后 2 位，64 位系统为最后 3 位）来存储一个“标记”。

+   GHC 使用这个标记来：

    +   如果对象是一个构造函数，标签包含构造函数编号（如果适用）

    +   如果对象是一个函数，标签包含函数的元数（如果适用）

## 避免进入值

我们之前的示例代码：

```
mk :: Int -> Int mk x = x + 1
```

使用指针标记的变化：

```
mk_entry() entry: ... R1 = I64[R1 + 16]; // grab 'x' from environment if (R1 & 7 != 0) goto cxd; // check if 'x' is eval'd jump I64[R1] (); // not eval'd so eval cxd: jump mk_exit (); // 'x' eval'd so jump to (+) continuation } mk_exit() cx0: I64[Hp - 8] = ghczmprim_GHCziTypes_Izh_con_info; // setup Int closure I64[Hp + 0] = v::I64; // setup Int closure R1 = Hp - 7; // point R1 to computed thunk value (with tag) ... }
```

## 指针标记使你自己的数据类型高效

+   如果闭包是一个构造函数，标签包含构造函数编号（如果适用）。

```
data MyBool a = MTrue a | MFalse a
```

+   将和使用 `Int#` 表示真和假一样高效。
