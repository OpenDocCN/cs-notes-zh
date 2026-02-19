# Elm 中的 ML 入门

我们将使用 [Elm v0.14](http://elm-lang.org/blog/announce/0.14.elm)。如果在本季度发布了较小的语言修订版，我们将决定是否升级。您应该尽快 [启动 Elm](https://www.classes.cs.uchicago.edu/archive/2015/winter/22300-1/assignments/HW0.html) ，以确保您拥有可用的开发环境。

让我们用一些 REPL（读取-求值-打印循环）中的示例来开始。

```
% elm-repl
Elm REPL 0.4 <https://github.com/elm-lang/elm-repl#elm-repl>
Type :help for help, :exit to exit
> 
```

### 基本值

```
> True
True : Bool

> False
False : Bool

> 'a'
"'a' : Char

> "abc"
"abc" : String

> 3.0
3 : Float 
```

没有小数点的数字文字由类型变量`number`描述，该类型描述了`Int`和`Float`。

```
> 3
3 : number 
```

阅读上面的最后一行的一种方法是“对于每一种类型`number`，使得`number`=`Int`或`number`=`Float`，3 都有类型`number`。”换句话说，“3 具有类型`Int`和`Float`”，根据表达式的使用方式，Elm 类型检查器将选择将类型变量`number`实例化为其中一个类型。

```
> truncate 3
3 : Int

> truncate 3.0
3 : Int 
```

如果您熟悉 Haskell，请将`number`看作是“内置”到语言中的类型类。Elm 没有对类型类的普遍支持，但它确实有一些特殊用途的类型类，比如`number`。

### 元组

元组将两个或多个表达式封装成一个单个表达式。元组的类型记录了组件的数量和每个组件的类型。

```
> (True, False)
(True,False) : ( Bool, Bool )

> (1, 2, 3.0)
(1,2,3) : ( number, number, Float ) 
```

孤立的表达式更喜欢保持孤立：

```
> ("Leave me alone!")
"Leave me alone!" : String

> (((((("Leave me alone!"))))))
"Leave me alone!" : String 
```

### 函数

与大多数函数式语言一样，所有函数都接受一个参数并返回一个值。

```
> exclaim = \s -> s ++ "!"
<function> : String -> String

> exclaim s = s ++ "!"
<function> : String -> String

> exclaim "Hi"
"Hi!" : String 
```

*非柯里化*风格中的多参数：

```
> plus (x,y) = x + y
<function> : ( number, number ) -> number

> plus = \(x,y) -> x + y
<function> : ( number, number ) -> number

> plus xy = fst xy + snd xy
<function> : ( number, number ) -> number 
```

*柯里化*风格中的多参数：

```
> plus x y = x + y
<function> : number -> number -> number

> plus x = \y -> x + y
<function> : number -> number -> number

> plus = \x -> \y -> x + y
<function> : number -> number -> number 
```

*柯里化函数*的部分应用：

```
> plus7 = plus 7
<function> : number -> number

> plus7 1
8 : number

> plus7 11
18 : number 
```

如果我们想将我们的`plus`函数限制为`Int`而不是任意的`number`，我们需要一种方法将`number`“转换”为`Int`。虽然 [`Basics`](http://package.elm-lang.org/packages/elm-lang/core/1.0.0/Basics) 库没有提供这样的`toInt`函数，但我们可以定义一些东西来帮助自己：

```
> toInt n = n // 1
<function> : Int -> Int 
```

这并不完全满足我们所寻求的类型`number -> Int`... 但仔细考虑后，我们实际上并不真正需要那种类型的转换函数。为什么不呢？

```
> plusInt x y = (toInt x) + y
<function> : Int -> Int -> Int

> plusInt x y = toInt (x + y)
<function> : Int -> Int -> Int 
```

### 类型注释

Elm，像大多数 ML 方言一样，自动推断大多数类型。然而，手动声明“顶层”定义的类型注释通常是一个好的实践（我们很快会看到“局部”定义）。

在 Elm 源文件中（例如 [`IntroML.elm`](https://www.classes.cs.uchicago.edu/archive/2015/winter/22300-1/public-code/IntroML.elm)），顶层定义可以在类型注释之前。类型检查器将检查实现是否实际满足您声明的类型。

```
plus : number -> number -> number
plus x y = x + y

plusInt : Int -> Int -> Int
plusInt x y = x + y 
```

请注意，通过对`plusInt`使用显式注释，我们避免了之前需要使用绕道的`toInt`函数的需要。事实上，我们可以重构定义如下：

```
plusInt : Int -> Int -> Int
plusInt = plus 
```

这个版本真正强调了我们的`plusInt`的*实现*比向函数的*客户端*公开的 API（即类型）更一般化的事实。设计软件充满了这样的决策。

### 导入模块

现在我们已经开始将定义放入源文件中了，那么我们如何从 REPL 和其他文件中导入它们呢？请注意，文件[`IntroML.elm`](https://www.classes.cs.uchicago.edu/archive/2015/winter/22300-1/public-code/IntroML.elm)定义了同名模块，可以通过几种方式导入。

以下`import`将要求对所有导入的定义进行限定以供使用。

```
> import IntroML

> IntroML.plusInt 2 3
5 : Int 
```

另一个选项是指定要导入和使用的定义并进行限定。即使使用了限定，也不会访问`IntroML`中的其他定义。

```
> import IntroML (plusInt)

> plusInt 2 3
5 : Int

> IntroML.plus 2.0 3.0
... Error: Could not find variable 'IntroML.plus'. ... 
```

但是，您可以重新导入相同的模块以允许对其他成员进行限定访问。

```
> import IntroML (plusInt) \
| import IntroML

> plusInt 2 3
5 : Int

> IntroML.plus 2.0 3.0
5 : Float

> IntroML.exclaim "Whoa..."
"Whoa...!" : String 
```

请注意，在 REPL 中输入多行表达式时使用`\`字符。如果相反，在 REPL 中依次输入两个`import`表达式，则似乎最近的一个会优先。但是，在源文件中，情况并非如此。很快在处理`List`时，这将会变得有用。

您还可以导入所有定义以供无限制使用。

```
> import IntroML (..)

> (plusInt 2 3, exclaim "Cool")
(5,"Cool!") : ( Int, String ) 
```

最后，您还可以为导入的模块定义一个缩写。

```
> import IntroML as M

> M.plusInt 2 3
5 : Int 
```

啊，选择真是太多了！这种灵活性会派上用场，因为在导入许多模块时很难记住函数的定义位置。此外，许多模块将定义具有流行名称的函数，例如`map`和`foldr`，因此需要限定访问。

您可能已经注意到，我们开始使用一些库函数而没有任何`import`。这是因为[`Basics`](http://package.elm-lang.org/packages/elm-lang/core/1.0.0/Basics)以及其他一些非常常见的库，例如[`Maybe`](http://package.elm-lang.org/packages/elm-lang/core/1.0.0/Maybe)，是默认打开的。

### 条件

条件表达式必须在两个分支上返回相同类型的值。

```
> if 1 == 1 then "yes" else "no"
"yes" : String

> if False then 1.0 else 1
1 : Float 
```

有一个方便的语法用于多路 if 表达式，这使得编写嵌套条件非常整洁。

```
> if | 1 == 1 -> 1.0 \
|    | 1 == 2 -> 1
1 : Float 
```

[`Basics`](http://package.elm-lang.org/packages/elm-lang/core/1.0.0/Basics)将`otherwise`定义为`True`的同义词，这可以提高多路条件语句的可读性。

```
> otherwise
True : Bool

> if | 1 == 1    -> 1.0 \
|    | otherwise -> 1
1 : Float 
```

尽管多路条件很棒，但与编写嵌套条件相比，它们确实引入了一个潜在的陷阱。如果*没有*谓词（也称为“保护”或“where 子句”）的计算结果为`True`会发生什么？

```
> if | 1 == 2 -> "uh oh..."
Error: Runtime error in module Repl (on line 5, column 3 to 27)
Non-exhaustive pattern match in multi-way-if expression.
It is best to use 'otherwise' as the last branch of multi-way-if. 
```

啊，运行时错误。请注意，由于条件始终需要指定`else`分支，因此无法使用条件来编写相同的表达式。不必过分担心，只需确保在多路条件中处理了所有情况，因为类型检查器不会帮助您处理这种错误。

如果*多个*谓词的计算结果为`True`呢？

```
> if | 1 == 1 -> 1 \
|    | 2 == 2 -> 2
1 : number 
```

预期的是，每个谓词都是按自上而下的顺序进行测试的，满足条件的第一个谓词获胜。再次注意，类型检查器不会抱怨第二个子句在运行时永远*不会*被评估。虽然在这种情况下很容易看出，但通常情况下识别不可达代码是不可决定的。

关于条件语句还有一件事要知道：空白很重要。确保所有模式都对齐，你就会做得很好。

### 多态类型

类型变量是以小写字母开头并且通常是单个字符的标识符。

```
> choose b x y = if b then x else y
<function> : Bool -> a -> a -> a 
```

与上面讨论的`number`类型一样，应该将此函数类型解读为在类型变量的“定义”范围内具有一个隐式的“forall”：“对于所有类型`a`，`choose`具有类型`Bool -> a -> a -> a`。

当调用诸如`choose`之类的多态函数时，Elm（像其他 ML 方言一样）将根据值参数自动*实例化*类型变量为适当的类型参数。

```
> choose True True False      -- a instantiated to Bool
> choose True "a" "b"         -- a instantiated to String
> choose True 1.0 2.0         -- a instantiated to Float
> choose True 1 2             -- a instantiated to number 
```

这些函数调用可以被认为是接受类型参数（对于函数的每个全称量化类型变量一个）的，这些参数由类型检查器自动推断。如果 Elm 的语法允许显式类型实例化，则上述表达式可能看起来像：

```
choose [Bool] True False
choose [String] "a" "b"
choose [Float] 1.0 2.0
choose [number] 1 2 
```

想象一下，在 Elm 中，多态类型需要显式的 forall 量词。使用类型参数`T`实例化多态类型的结果是通过*替换*类型变量的绑定出现来获得的。

```
choose : forall a. Bool -> a      -> a      -> a

choose [Bool]    : Bool -> Bool   -> Bool   -> Bool
choose [String]  : Bool -> String -> String -> String
choose [Float]   : Bool -> Float  -> Float  -> Float
choose [number]  : Bool -> number -> number -> number 
```

就像程序变量的特定选择并不重要一样，类型变量的特定选择也不重要。因此，多态类型在重命名方面是等价的。例如，`choose`可以被注释为选择不同于`a`的变量名的多态类型。

```
choose : Bool -> b -> b -> b 

choose : Bool -> c -> c -> c 

choose : Bool -> thing -> thing -> thing 
```

所有这些类型都是等价的。然而，在类型检查函数后，Elm 可能会选择推翻您对类型变量的选择。

```
> import IntroML

> IntroML.choose
<function> : Bool -> a -> a -> a 
```

如果`choose`被注释如下会发生什么？

```
choose : Bool -> number -> number -> number 
```

该注释下的`choose`函数通过了类型检查，但是此类型比先前的类型更为限制。请记住，如前所述，`number`只能被实例化为`Int`和`Float`类型。Elm 对特定变量`number`的特殊处理——而不是其他标识符——是 Elm 将有限形式的类型类强行加入语言的方式。这是一个非常有趣的设计选择！

当我们讨论时，还有另一个特殊的目的类型变量称为`comparable`，它用于描述可以使用排序关系进行比较的类型。有关更多信息，请参见[`Basics`](http://package.elm-lang.org/packages/elm-lang/core/1.0.0/Basics)。

```
> (<)
<function> : comparable -> comparable -> Bool

> 1 < 2
True : Bool

> 1 < 2.0
True : Bool

> "a" < "ab"
True : Bool

> (2, 1) < (1, 2)
False : Bool

> (1 // 1) < 2.0
... Type mismatch ...

> True < False
... Looks like you want something comparable, but the only valid comparable
    types are Int, Float, Char, String, lists, or tuples. ... 
```

### 闲聊：Bug 猎取

请注意，似乎存在一个[开放的编译器错误](https://github.com/elm-lang/elm-compiler/issues/694)，其中多态类型可能被错误打印。考虑：

```
> id1 (a) = (a)
i<function> : a -> a

> id2 (a,b) = (a,b)
<function> : ( a, b ) -> ( a, b )

> id3 (a,b,c) = (a,b,c)
<function> : ( a, b, b ) -> ( a, b, b )

> id4 (a,b,c,d) = (a,b,c,d)
<function> : ( a, b, b, b ) -> ( a, b, b, b ) 
```

对于`id1`和`id2`推断出的类型与我们的预期相符，但对于`id3`和`id4`却不是。后两者的推断类型是正确的，但它们似乎不必要地受限，重新使用了（绑定的）类型变量`b`，而不是为参数`c`和`d`选择不同的变量。

作为调查问题的一种方式，我们可以将以下带注释的定义放在[`IntroML.elm`](https://www.classes.cs.uchicago.edu/archive/2015/winter/22300-1/public-code/IntroML.elm)中，以查看编译器的反馈。

```
id5 : (t1,t2,t3,t4,t5) -> (t1,t2,t3,t4,t5)
id5 (a,b,c,d,e) = (a,b,c,d,e) 
```

瞧，`id5`通过了类型检查，具有我们归因的合适的通用类型，但在 REPL 中显示的类型在重命名上不等效：

```
> import IntroML

> IntroML.id5
<function> : ( a, b, b, b, b ) -> ( a, b, b, b, b ) 
```

我们可以进行更深入的调查，试图确定 bug 是否表现在为`id5`分配的类型中，或者只表现在为`id5`打印的类型中。以下交互显示了后者，更为温和的 bug：

```
> IntroML.id5 ('a', "b", 1.0, 1, True)
('a',"b",1,1,True) : ( Char, String, Float, number, Bool ) 
```

很酷，也许我们有一些潜力进行调查性新闻报道... 或者没有。无论如何，即使在成熟软件中也会出现 bug，所以我们不能期望编译器现在就完美无缺。话虽如此，语言和工具已经相当健壮（感谢社区！），我们在本课程中将充分利用它们。

当我们遇到这样的 bug 时，我们可以在 Piazza 上相互帮助排查问题（“`elm`”标签似乎是一个合理的选择）；仔细查找[编译器](https://github.com/elm-lang/elm-compiler/issues)、[REPL](https://github.com/elm-lang/elm-repl/issues)、[标准库](https://github.com/elm-lang/elm-package/issues/)和[反应器](https://github.com/elm-lang/elm-reactor/issues)中已知的未解决问题；在[Elm 邮件列表](https://groups.google.com/forum/#!forum/elm-discuss)上寻找相关讨论；并撰写建设性、清晰的错误报告提交给语言社区。你甚至可能会发现 bug 并决定成为 Elm 的贡献者！

### 列表

不用多说了，列表。注意`import`将“cons”操作符引入范围：

```
> import List ((::))

> 1::2::3::4::[]
[1,2,3,4] : List number

> [1,2,3,4]
[1,2,3,4] : List number 
```

目前还没有一种方法可以从模块中导入*所有*中缀操作符以供未限定使用，也没有支持限定操作符的支持，但是有[提案](https://groups.google.com/forum/#!searchin/elm-discuss/operator/elm-discuss/1BSng3MWIq0/ZGaFp4PoabQJ)支持这些特性。

对于那些在此记分的人，上面的列表语法部分是 OCaml（`(::)`代替`(:)`作为 cons，而不是`;`）和部分 Haskell（`,`用于分隔元素，而不是`;`）的组合。

数值范围的语法简写：

```
> [1..6]
[1[1,2,3,4,5,6] : List number

> [1.0..6.0]
[1,2,3,4,5,6] : List Float 
```

`String`不像在 Haskell 中那样是`Char`的列表：

```
> ['a','b','c']
['a','b','c'] : List Char

> "abc"
"abc" : String

> ['a','b','c'] == "abc"
... Type mismatch ... 
```

模式匹配以解构列表：

```
> len xs = case xs of \
|   x::xs -> 1 + len xs \
|   []    -> 0
<function> : List a -> number

> len [1..3]
3 : number

> len []
0 : number 
```

一行上的多个 case：

```
> len xs = case xs of {_::xs -> 1 + len xs; [] -> 0}
<function> : List a -> number

> len [1..10]
10 : number

> len ['a','b','c'] 
```

不完全模式：

```
> hd xs = case xs of \
|   x::_ -> x
<function> : List a -> a

> hd [0]
hd 0 : number

> hd []
Error: Runtime error in module Repl (between lines 4 and 5)
Non-exhaustive pattern match in case-expression.
Make sure your patterns cover every case! 
```

和多路条件语句一样，模式匹配时空白字符很重要。确保你的`cases`排列得整齐。

### 高阶函数

经典之作：

```
> import List ((::), filter, map, foldr, foldl)

> filter
<function: filter> : (a -> Bool) -> List a -> List a

> filter (\x -> x `rem` 2 == 0) [1..10]
[2,4,6,8,10] : List Int

> map
<function: map> : (a -> b) -> List a -> List b

> map (\x -> x ^ 2) [1..10]
[1,4,9,16,25,36,49,64,81,100] : List number

> foldr
<function: foldr> : (a -> b -> b) -> b -> List a -> b

> foldr (\x acc -> x :: acc) [] [1..10]
[1,2,3,4,5,6,7,8,9,10] : List number

> foldl
<function: foldl> : (a -> b -> b) -> b -> List a -> b

> foldl (\x acc -> x :: acc) [] [1..10]
[10,9,8,7,6,5,4,3,2,1] : List number 
```

以下强调了上述 lambda 是*η-展开*的：

```
> (::)
<function> : a -> List a -> List a

> foldl (\x acc -> (::) x acc) [] [1..10]
[10,9,8,7,6,5,4,3,2,1] : List number 
```

*η-缩减*版本更好：

```
> foldl (::) [] [1..10]
[10,9,8,7,6,5,4,3,2,1] : List number 
```

### 数据类型

列表是一种内置的*归纳数据类型*。您可以定义自己的数据类型（或“不相交和”或“乘积和”）。每个类型构造函数都定义了一个或多个数据构造函数，每个数据构造函数都定义为“持有”零个或多个值。

```
> type Diet = Herb | Carn | Omni | Other String

> Carn
Carn : Repl.Diet

> Omni
Omni : Repl.Diet

> Other "Lactose Intolerant"
Other ("Lactose Intolerant") : Repl.Diet 
```

非空构造数据本身就是函数：

```
> Other
<function> : String -> Repl.Diet 
```

使用数据类型模拟值的“异构”列表：

```
> diets = [Herb, Herb, Omni, Other "Vegan", Carn]
[Herb,Herb,Omni,Other "Vegan",Carn] : List Repl.Diet 
```

模式匹配是“使用”或“解构”构造值的（唯一）方法：

```
> maybeHuman d = case d of \
|   Carn -> False \
|   _    -> True
<function> : Repl.Diet -> Bool

> List.map maybeHuman diets
[True,True,True,True,False] : List Bool 
```

与以往一样，要小心处理非穷尽和冗余模式。

### 错误类型

我们上面的“head”函数`hd`在其参数非空时会导致运行时错误。处理错误情况的另一种方法是明确跟踪它们，通过引入用于明确表示错误或缺乏有意义答案的数据值。

例如，类型

```
> type MaybeInt = YesInt Int | NoInt 
```

描述了两种值：标记为`YesInt`的值*包含*一个`Int`，以及标记为`NoInt`的值，不*包含*任何其他数据。换句话说，后者可用于编码当没有有意义的`Int`可返回时：

```
> hd xs = case xs of \
|   x::xs' -> YesInt x \
|   []     -> NoInt
<function> : List Int -> Repl.MaybeInt

> hd [1..4]
YesInt 1 : Repl.MaybeInt

> hd []
NoInt : Repl.MaybeInt 
```

啊，比运行时错误好多了！

此`MaybeInt`类型仅定义为与`Int`一起使用，但相同模式 —— 有意义结果的存在或不存在 —— 将出现在所有不同类型的值中。

多态数据类型来拯救：

```
> type MaybeData a = YesData a | NoData 
```

与调用多态函数时一样，类型变量对于像`MaybeData`这样的类型构造函数会被实例化为特定类型参数，以匹配它所使用的值的种类。

多态数据类型和多态函数组成了一个强大的二人组：

```
> hd xs = case xs of \
|   x::_ -> YesData x \
|   []   -> NoData
<function> : List a -> Repl.MaybeData a

> hd ['a','b','c']
YesData 'a' : Repl.MaybeData Char

> hd ["a","b","c"]
YesData 'a' : Repl.MaybeData String

> hd [1..4]
YesData 1 : Repl.MaybeData number

> hd []
NoData : Repl.MaybeData a 
```

对于每种类型`a`，`NoData`都有类型`a`。酷，`NoData`是一个多态*常量*，其类型可以根据使用方式进行实例化或特化。

`MaybeData`模式非常常见，有一个名为[`Maybe`](http://package.elm-lang.org/packages/elm-lang/core/1.0.0/Maybe)的库提供了以下类型，与我们的类型类似但名称不同：

```
type Maybe a = Just a | Nothing 
```

还有一个相关的库和类型叫做[`Result`](http://package.elm-lang.org/packages/elm-lang/core/1.0.0/Result)，它概括了`Maybe`模式。查看它们，还可以查看[`IntroML.elm`](https://www.classes.cs.uchicago.edu/archive/2015/winter/22300-1/public-code/IntroML.elm)以获取一些简单示例。

### 中缀运算符

在[Basics](http://package.elm-lang.org/packages/elm-lang/core/1.0.0/Basics)中有一堆非常有用的中缀运算符，所以四处看看。确保访问`(<|)`、`(|>)`、`(<<)`和`(>>)`，它们可用于编写优雅的函数应用链。

### Let-Expressions

到目前为止，我们只使用顶层定义。Elm 的`let`表达式允许定义变量，这些变量是“局部”于封闭范围的。与其他语言特性一样，空格很重要，因此确保等式对齐。

```
plus3 a =
  let b = a + 1 in
  let c = b + 1 in
  let d = c + 1 in
    d 
```

不需要写那么多`let`和`in`：

```
plus3 a =
  let b = a + 1
      c = b + 1
      d = c + 1
  in
    d 
```

太多的本地变量有时会使含义变得模糊（就像太少的变量一样）。在这种情况下，“管道化”定义

```
plus3 a = a |> plus 1 |> plus 1 |> plus 1 
```

而且，更好的是，通过函数组合的定义方式

```
plus3 = plus 1 << plus 1 << plus 1 
```

可以说，更易读。

## 阅读

#### 必需的

+   [语法参考](http://elm-lang.org/learn/Syntax.elm)

+   库：[`基础`](http://package.elm-lang.org/packages/elm-lang/core/1.0.0/Basics)，[`可能性`](http://package.elm-lang.org/packages/elm-lang/core/1.0.0/Maybe)，[`列表`](http://package.elm-lang.org/packages/elm-lang/core/1.0.0/List)

#### 推荐的

+   浏览一些 [Elm 示例](http://elm-lang.org/Examples.elm)

+   浏览更多的 [标准库](http://package.elm-lang.org/packages/elm-lang/core/1.0.0/)

#### 额外的

+   如果你想看看另外两种 ML 方言的语法和特性，可以看看[这个](http://www.mpi-sws.org/~rossberg/sml-vs-ocaml.html)和[这个](http://adam.chlipala.net/mlcomp/)。
