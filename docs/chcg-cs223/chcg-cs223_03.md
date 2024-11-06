# Elm 中的 FRP 简介

假设我们想要编写一些 JavaScript（伪代码）来跟踪用户当前是否按下了鼠标按钮。我们可能会先定义一个可变变量，然后安装两个“回调”函数，当 JavaScript 运行时系统触发`mousedown`和`mouseup`事件时，这两个函数会被调用：

```
// the "state"
var isDown = false;

// the "view" of the state
function printIsDown() { mainElement.innerHTML = isDown.toString(); }

// event handlers to update the state
function handleMouseDown() { isDown = true;  printIsDown(); }
function handleMouseUp()   { isDown = false; printIsDown(); }

// the "controller" that maps events to handlers
element.addEventListener("mousedown", handleMouseDown);
element.addEventListener("mouseup",   handleMouseUp); 
```

（注意：这个示例的目的是清晰地展示状态管理的结构，所以我们将避免自然的重构冲动。）

这是一个非常绕弯的方法，可以简单描述为“仅当鼠标按钮被按下时为`true`的布尔值”。当管理依赖于多个事件和多个中间计算的状态时，情况很快变得更加复杂。

*函数式响应式编程（FRP）*是一种范式，它允许直接使用函数式编程的构建块来实现*时变*值（如`isDown`），而不是像上面那样使用突变和回调。

## [什么是 Signal？](http://elm-lang.org/learn/What-is-FRP.elm)

“*信号*是随时间变化的值。”在 Elm 中，[`Mouse.isDown`](http://package.elm-lang.org/packages/elm-lang/core/1.0.0/Mouse)是语言提供的一个原始信号，类型为`Signal Bool`。我们可以将`isDown`视为始终指向“当前”值，而不必担心它如何被更新的底层细节。

更好的是，我们可以使用函数式编程的构建块*抽象*和*组合*信号。例如，我们可以使用

```
Signal.map : (a -> b) -> Signal a -> Signal b 
```

将纯函数`not`，即对`Bool`进行取反的操作，应用到当前值`isDown`上，实现如下

```
isUp = Signal.map (fun curValIsDown -> not curValIsDown) Mouse.isDown 
```

或者更清晰地说：

```
isUp = Signal.map not Mouse.isDown 
```

结果是一个布尔值信号（类型为`Signal Bool`），当`Mouse.isDown`信号更新时，它也会更新。这是多么酷？

正如名称所示，`Signal.map`的行为和类型类似于操作其他类型数据的映射函数 — [`List.map`](http://package.elm-lang.org/packages/elm-lang/core/1.0.0/List)、[`String.map`](http://package.elm-lang.org/packages/elm-lang/core/1.0.0/String)、[`Maybe.map`](http://package.elm-lang.org/packages/elm-lang/core/1.0.0/Maybe)、[`Dict.map`](http://package.elm-lang.org/packages/elm-lang/core/1.0.0/Dict) 等。

## 渲染到 HTML

在 HTML 窗口中写入是 Elm 程序的主要*效果*。Elm 模块中的`main`定义指定了要渲染的内容，这个内容采用了[`Graphics.Element`](http://package.elm-lang.org/packages/elm-lang/core/1.0.0/Graphics-Element)库中定义的`Element`值的形式。

在测试不会呈现任何 HTML 的程序时，`elm-repl`非常方便（注意在这些情况下我们没有必要定义`main`）。但现在你可能想要在浏览器中尝试这些示例了 —— 通过使用`elm-make`编译 Elm 源文件（参见[HW0](https://www.classes.cs.uchicago.edu/archive/2015/winter/22300-1/assignments/HW0.html)进行复习）；使用[在线](http://elm-lang.org/try)的实时编辑器；或者本地构建[Elm 网站](https://github.com/elm-lang/elm-lang.org)，这样你就可以在没有互联网连接的情况下运行自己的实时编辑器。

第一个例子：

```
import Text (plainText)
import Graphics.Element (Element)

main : Element
main =
  plainText "Hello, world!" 
```

除了提供许多用于操作文本的函数之外，[`Text`](http://package.elm-lang.org/packages/elm-lang/core/1.0.0/Text)库还提供了`plainText`来将`String`转换为`Element`，这是我们需要在`main`中提供的值类型，以便进行呈现。还请注意，`导入`语句用于将类型的名称（例如`Element`）以及值（例如`plainText`）加载到作用域中。

实际上，因为我们经常会想要随着时间的推移改变呈现的内容，所以`main`定义实际上是`Element`的*信号*（即类型为`Signal Element`的信号）。当将`main`定义为类型为`Element`而不是`Signal Element`的表达式`e`时，它将被解释为信号`Signal.constant e`，其中函数

```
Signal.constant : a -> Signal a 
```

将一个纯值转换成`Signal`，一个常量信号。所以我们也可以写得更加明确：

```
main : Signal Element
main =
  Signal.constant (plainText "Hello, world!") 
```

现在我们已经向世界介绍了自己，让我们写一些稍微有趣的东西到窗口中，比如，当前鼠标按钮是否正在被按下。为此，我们利用了[`Basics`](http://package.elm-lang.org/packages/elm-lang/core/1.0.0/Basics)中的`toString`函数：

```
import Text (plainText)
import Graphics.Element (Element)
import Mouse
import Signal

isUp = Signal.map not Mouse.isDown

main : Signal Element
main =
  Signal.map (\b -> plainText (toString b)) isUp 
```

尝试一下并点击周围。你也可以玩一下[官方的 IsDown 示例](http://elm-lang.org/edit/examples/Reactive/IsDown.elm)。

#### 关于导入的说明

请注意，大多数库，甚至是非常常见的库，都需要明确的`导入`。我认为这在学习语言时会特别方便，因为它需要仔细理解库的结构和目的。

还请注意，在上面的例子中，我选择了混合使用合格和非合格的`导入`。随着你编写 Elm 代码的经验增加，你会发现一种适合自己的`导入`风格。这将取决于诸如你计划从给定模块中使用多少函数之类的因素 —— 我不知道你，但我打算在[`Mouse`](http://package.elm-lang.org/packages/elm-lang/core/1.0.0/Mouse)库中疯狂使用很多函数，而且我不想明确列出它的所有定义 —— 以及导入的名称有多独特 —— `plainText`远不如，比如说，`map`容易被其他导入的模块定义，因此在不加限定地使用`plainText`似乎对我来说是一个不错的选择。

#### 关于函数组合的一点说明

根据你的先前经验和喜好，你可能更喜欢放弃上面`main`定义中的匿名 lambda，而是选择一个更强调函数组合的 lambda，例如

```
(\b -> b |> toString |> plainText) 
```

或

```
(toString >> plainText) 
```

或

```
(\b -> plainText <| toString <| b) 
```

或

```
(plainText << toString) 
```

所有这些定义是等效的，所以选择你最喜欢的风格，并且能很好地融入周围的代码。

[`Basics`](http://package.elm-lang.org/packages/elm-lang/core/1.0.0/Basics) 定义了这些中缀运算符。同时也看看 [`Text.asText`](http://package.elm-lang.org/packages/elm-lang/core/1.0.0/Text)，它类似于 `(plainText << toString)`。

## 从过去折叠

现在让我们考虑一个稍微有趣的例子，来计算并显示用户点击鼠标按钮的次数。Elm 中没有这样的信号内建，因此我们将根据提供的信号定义自己的信号。

一种选择是建立在鼠标点击事件的基础上，这与我们见过的鼠标按下事件是分开但密切相关的。为此，Elm 提供了原始

```
Mouse.clicks : Signal () 
```

它为每次鼠标按钮点击产生虚拟的“单位”值（写作 `()`），对应于虚拟的“单位”类型（也写作 `()`）。释放按钮不会触发对这个信号的更新。

#### 基本的模型-视图-控制器架构

为了构建一个`Signal`来渲染`Element`，通常将工作分为三个部分会很方便。

1.  *模型* 跟踪产生所需结果所需的所有信息。我们可能有时会懒惰，有时（实际上经常）将模型称为*状态*，但我们不要被误导以为在源级别有任何可变的东西。

    为了显示点击次数，我们只需维护一个整数计数器：

    ```
    type alias State = Int

    initState : State
    initState = 0 
    ```

    使用`alias`关键字将 `State` 定义为完全等同于 `Int`；它只是一个简写，不定义新类型。类型别名可以用来缩写长类型以及给出关于类型预期用途的指示。

1.  *视图* 定义了如何将模型渲染到屏幕上。在这种情况下，它相当简单：

    ```
    view : State -> Element
    view s = asText s 
    ```

    或者更简洁地说：

    ```
    view = asText 
    ```

1.  *控制器* 定义了信号和在信号更新时转换和渲染状态的函数之间的连接。为此，我们使用函数

    ```
    Signal.foldp : (a -> b -> b) -> b -> Signal a -> Signal b 
    ```

    将折叠函数应用于信号产生的*所有*值（类型为 `a`），从某个初始状态（类型为 `b`）开始，并将其转换为状态值信号（类型为 `b`）。实际上，这与为其他数据类型提供的折叠模式相同：

    ```
    List.foldl : (a -> b -> b) -> b -> List a -> b
    List.foldr : (a -> b -> b) -> b -> List a -> b 
    ```

    对于 `Signal`，这个操作称为“从过去折叠”，而不是“从左边折叠”。从“右边”折叠意味着从“未来”折叠……

    要完成我们的任务，我们定义一个折叠函数 `step`，然后将所有内容放在 `main` 中，如下所示：

    ```
    step : a -> State -> State
    step _ i = i + 1

    main : Signal Element
    main =
      Signal.map view (Signal.foldp step initState Mouse.clicks) 
    ```

将此程序下载为[`IntroFRP.elm`](https://www.classes.cs.uchicago.edu/archive/2015/winter/22300-1/public-code/IntroFRP.elm)，并[尝试](http://elm-lang.org/try)一下。您还可以查看[CountClicks 示例](http://elm-lang.org/edit/examples/Reactive/CountClicks.elm)。

有一点需要考虑：我们是否可以使用`Mouse.isDown`信号而不是`Mouse.clicks`来实现这个功能？

最后，假设我们想要跟踪时间的流逝而不是点击次数。通过将我们的`main`定义分解为通用形式，我们可以实现这一点。

```
main = Signal.map VIEW (Signal.foldp UPDATE INIT_STATE BASE_SIGNAL) 
```

我们可以通过对先前定义进行微小调整来实现这一点：

```
main =
  Signal.map view (Signal.foldp step initState (Time.every Time.second)) 
```

查看[`Time`](http://package.elm-lang.org/packages/elm-lang/core/1.0.0/Time)库。

#### 等一下...

我们将 Elm 代码分解为模型、视图和控制器，就像我们开始时的 JavaScript 代码一样。那么，我们到底获得了什么？

嗯，在 JavaScript 中，我们会在事件处理程序中编写逻辑，以确定哪些状态的部分需要更新以响应不同的事件。在 Elm 中，我们直接将新信号定义为现有信号的函数，并且将其留给 Elm 编译器和运行时来确定何时以及如何重新计算从更原始的信号派生的信号值。所以，我们获得了很多！

这引出了一个问题：编译器将如何弄清楚这一切？

## 编译为 JavaScript

Elm 编译器负责生成目标 JavaScript，管理可变状态和事件处理程序，类似于我们开始时的伪代码。理解 Elm 程序的结构的一种方法是将其视为*信号图*，其中节点是计算单元，边表示值的流动。信号图的入边是"原始"JavaScript 信号或事件，如鼠标按下、鼠标抬起、鼠标点击等。图的其余部分构成了一个纯函数，以这些原始信号为基础定义。

因此，一个天真的方法是基于*任何*信号的更改重新计算*整个*程序。这显然是低效的，也是不必要的，因为信号图的许多部分可能独立于许多原始信号的更改。

相反，编译器跟踪信号图中的依赖关系，并使用并发消息传递系统更有效地重新计算仅依赖于原始信号更改的程序部分。

我们不会深入讨论编译过程的任何细节，但是你可以在下面发布的阅读链接中找到更多信息。但是，从基本的角度来看，我们对过程可能是如何工作的直觉应该类似于我们对函数语言（即使没有 FRP）的优化编译器的直觉：源语言可能是纯函数的，具有不断复制的不可变数据结构，但是我们知道，在底层，编译器正在努力识别重新使用和缓存先前计算结果的机会。事实上，随着我们研究如何在纯函数语言中实现高效数据结构的几周内，我们将看到更多这一原则。

## 2D 图形

[`Graphics.Element`](http://package.elm-lang.org/packages/elm-lang/core/1.0.0/Graphics-Element) 库定义了一个用于排列文本、图像和其他 `Element` 的 API。此外，[`Graphics.Collage`](http://package.elm-lang.org/packages/elm-lang/core/1.0.0/Graphics-Collage) 库提供了定义自由形状图形（包括形状、线条、颜色等）的工具。通过浏览 [Elm 示例页面](http://elm-lang.org/Examples.elm) 上的 2D 形状示例来开始探索。作业 1 将提供一个真正深入挖掘的理由。

## 阅读

#### 必须的

+   库：[`Signal`](http://package.elm-lang.org/packages/elm-lang/core/1.0.0/Signal)，[`Graphics.Element`](http://package.elm-lang.org/packages/elm-lang/core/1.0.0/Graphics-Element)，[`Graphics.Collage`](http://package.elm-lang.org/packages/elm-lang/core/1.0.0/Graphics-Collage)。当您查阅 `Signal` 库时，请注意 `isUp` 函数如何使用一个方便的中缀运算符重写：

    ```
    isUp = not <~ Mouse.isDown 
    ```

    "通过 `Mouse.isDown` 信号通过 `not` 函数。"

#### 推荐的

+   查看更多的 [Elm 示例](http://elm-lang.org/Examples.elm)

+   查看更多的 [标准库](http://package.elm-lang.org/packages/elm-lang/core/1.0.0/)

#### 附加

对于 FRP 的更全面背景和 Elm 的介绍，您可能想要略读 Evan Czaplicki 的一些部分。

+   [高级论文](http://elm-lang.org/papers/concurrent-frp.pdf) 和

+   [PLDI 2013 论文](http://people.seas.harvard.edu/~chong/pubs/pldi13-elm.pdf)，作者是 [Stephen Chong](http://people.seas.harvard.edu/~chong/)。

您会发现一些术语和语言特性已经改变（例如，`Signal.lift` 现在称为 `Signal.map`）。您还会找到我们在本课程中不涵盖的编译过程的详细解释。
