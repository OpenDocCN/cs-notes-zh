# 按钮、通道和 2D 图形

在本教程中，我们将通过 Elm 中的几个 FRP 示例进行更多实例讲解。我们的激励应用程序将是构建一个可以使用按钮更新的整数计数器。

我们将从应用程序 `State` 开始：

```
type alias State = Int
initState        = 0
upstate _ i      = i + 1 
```

为了加快开发进程，我们将首先以虚拟常量信号的形式定义`main`。

```
main =
  Signal.map2 view Window.dimensions
    (Signal.foldp upstate initState (Signal.constant ())) 
```

而且，为了为我们的 GUI 建立基础，我们首先要设置一个简单的渲染函数，将计数器的当前值写入屏幕中央。我们将一些库绑定到单个字母名称以便简洁（例如 `E` 对应 [`Graphics.Element`](http://package.elm-lang.org/packages/elm-lang/core/1.0.0/Graphics-Element)，`T` 对应 [`Text`](http://package.elm-lang.org/packages/elm-lang/core/1.0.0/Text)，以及 `C` 对应 [`Graphics.Collage`](http://package.elm-lang.org/packages/elm-lang/core/1.0.0/Graphics-Collage)）。注意 `E.container` 如何用于定义具有特定位置的内容的已调整大小的 `Element`，而 `E.flow` 则将一组 `Elements` 沿着特定的 `Direction` 放置在一起。

```
view (w,h) i =
     E.color Color.gray
  <| E.container w h E.middle
  <| E.flow E.down
       [ i |> toString |> T.plainText ] 
```

在计数器显示下面，我们想要绘制两个按钮，一个用于递增，一个用于清除。[`Graphics.Input`](http://package.elm-lang.org/packages/elm-lang/core/1.0.0/Graphics-Input) 库提供以下内容来构建按钮：

```
button : Signal.Message -> String -> Element 
```

`Signal.Message` 是什么？这种类型描述了通过 `Channel`（也在 [`Signal`](http://package.elm-lang.org/packages/elm-lang/core/1.0.0/Signal) 中定义）发送的值。好的，那么 `Channel` 是什么呢？

### 通道

通道提供了一种通过其中传递消息（指定类型）的“管道”来创建的方式，这些消息可以从 Elm 应用程序的一部分发送到另一部分。它们是通过函数创建的：

```
Signal.channel : a -> Channel a 
```

我喜欢把通道看作是“动态生成的信号”。但是为什么需要一个单独的机制呢？

在我们迄今所做的编程中，我们首先使用 Elm 提供的一堆基本信号，然后我们根据它们导出其他信号。但是这些衍生信号不会生成新的事件或消息。相反，整个程序可以被认为是将对基本信号的更新传播开来。这种程序结构通过信号图的无环性得以体现。

但是如果程序员想要定义新的信号呢？例如，假设程序员想要将 *n* 个按钮绘制到屏幕上，每个按钮都应该有自己的事件，例如 `Mouse.clicks`，但它是“本地”于按钮而不是整个窗口。那么，如果程序员确切地知道数字 *n* 是多少，并且如果 Elm 提供了足够多的单独按钮信号（`Button1.clicks`、`Button2.clicks`、`Button3.clicks` 等），那么就可以使用这些原始信号。但是如果这个数字很大，而且在运行程序之前是不知道的呢？为此，我们需要一种动态生成信号的方法。

通道是 Elm 提供的解决方案。它们是信号之外的一个单独机制，并且它们是不纯的。每次调用`channel`函数时，它都会在世界中创建一个新的管道，可以被应用程序组件用来通信。

哎呀！我们已经超出了纯函数模型的范围？FRP 的其他更具表现力的表述不需要像这样单独的机制。在这些“高阶”FRP 系统中，*信号的信号*可以用来编码动态生成的信号。但是，随着这种表现力的增强，设计和有效实现方面也带来了其他挑战，这些挑战是正在进行研究的主题。

相比之下，Elm 采用了“一阶”FRP 的平衡，禁止了信号的信号，而是为常见情况提供了单独的通道机制，用于动态生成的按钮和需要响应典型浏览器事件的 HTML 元素。一旦创建了`Channel`，它就可以使用函数转换为`Signal`：

```
Signal.subscribe : Channel a -> Signal a 
```

Elm 的新颖之处之一在于它提供了对此语言设计选择的日益实用的实现。时间将告诉我们它是否取得了良好的平衡！

### 回到按钮

现在，回到`button`函数，我们需要定义`Signal.Message`（使用[`Signal.send`](http://package.elm-lang.org/packages/elm-lang/core/1.0.0/Signal)函数）在每次单击按钮时发送的消息。

```
send : Channel a -> a -> Message 
```

请注意，此函数定义了一个通道（类型为`Channel a`）和在某个请求上发送的消息（类型为`a`），但此函数本身不会“发送”消息。相反，以`Signal.Message`作为参数的库函数（如[`Graphics.Input`](http://package.elm-lang.org/packages/elm-lang/core/1.0.0/Graphics-Input)中的`button`和[`Graphics.Input.Field`](http://package.elm-lang.org/packages/elm-lang/core/1.0.0/Graphics-Input-Field)）是在某些浏览器事件上启动消息发送的函数。

请回忆我们上面的`upstate`函数忽略了它的第一个参数，并简单地递增了`State`。所以，让我们从定义一个`Channel`开始，用它发送虚拟值，每个值都会触发更新。

```
ch : Signal.Channel ()
ch = Signal.channel () 
```

然后，我们将向我们的视图添加两个按钮，这些按钮通过通道`ch`发送虚拟消息`()`。

```
 [ i |> toString |> T.plainText
   , button (Signal.send ch ()) "Increment" 
   , button (Signal.send ch ()) "Clear" 
   ] 
```

最后，我们将在`main`中`subscribe`到`ch`以便在每次发送消息时进行`upstate`（也就是说，每次单击其中一个两个按钮时）。

```
main =
  Signal.map2 view Window.dimensions
    (Signal.foldp upstate initState (Signal.subscribe ch)) 
```

这是一个有用的检查点，因为我们有了两个“工作中”的按钮。但我们显然需要重新组织事物，以便第二个按钮重置计数器而不是增加它。为了实现这一点，我们需要区分我们的按钮可能发送的两种不同类型的消息，并定义我们的`upstate`函数来相应地更新`State`。

```
type CounterEvent = Inc | Clear
upstate e i       = case e of {Clear -> 0; Inc -> i + 1}

ch : Signal.Channel CounterEvent
ch = Signal.channel Clear 
```

最后，我们需要更新每个按钮发送的消息。顺便说一句，让我们也在计数器和按钮之间添加一些空间（使用[`List.intersperse`](http://package.elm-lang.org/packages/elm-lang/core/1.0.0/List)和[`E.spacer`](http://package.elm-lang.org/packages/elm-lang/core/1.0.0/Graphics-Element)）。

```
vspace = E.spacer 0 10

view (w,h) i =
     E.color Color.gray
  <| E.container w h E.middle
  <| E.flow E.down
  <| List.intersperse vspace
       [ i |> toString |> T.plainText
       , button (Signal.send ch Inc) "Increment" 
       , button (Signal.send ch Clear) "Clear" 
       ] 
```

现在我们有一个可以工作的计数器了！查看[源代码](https://www.classes.cs.uchicago.edu/archive/2015/winter/22300-1/public-code/Buttons/Buttons0.elm)和[演示](https://www.classes.cs.uchicago.edu/archive/2015/winter/22300-1/public-code/Buttons/Buttons0.html)。

### 设置按钮样式

已经让我们的计数器基本功能正常运行了，现在让我们让它看起来更好看一点吧。这个功能

```
customButton : Signal.Message -> Element -> Element -> Element -> Element 
```

在[`Graphics.Input`](http://package.elm-lang.org/packages/elm-lang/core/1.0.0/Graphics-Input)中，根据按钮的状态（向上、悬停或向下），需要三个`Elements`来绘制。我们可以利用这一点来使用不同的颜色。

```
myButton evt s =
  let b = button evt s in
  customButton evt
    (E.color Color.lightYellow b)
    (E.color Color.lightOrange b)
    (E.color Color.lightBlue   b) 
```

在`view`中调用`myButton`而不是`button`然后就会呈现出我们稍微花哨一点的按钮。这很酷，但默认样式仍然不太好看。最好在按钮周围加上边框，并且改变字体样式使其更易读。在[`Graphics.Input`](http://package.elm-lang.org/packages/elm-lang/core/1.0.0/Graphics-Input)、[`Graphics.Element`](http://package.elm-lang.org/packages/elm-lang/core/1.0.0/Graphics-Element)和[`Text`](http://package.elm-lang.org/packages/elm-lang/core/1.0.0/Text)的类型签名中查找，似乎没有库函数能够完全满足我们的要求。因此，我们必须使用一个更低级别的“无结构”图形库。

### 无结构的 2D 图形

`Graphics.Element`有许多有用的布局函数，但如果我们想要进行更自由的绘图，我们需要使用[`Graphics.Collage`](http://package.elm-lang.org/packages/elm-lang/core/1.0.0/Graphics-Collage)库。工作类型是一个`Form`，有许多创建它们的方法。

`circle`和`rect`等函数会创建`Shape`值。

```
circle : Float -> Shape

rect : Float -> Float -> Shape 
```

我们如何将`Shape`转换为`Form`？在文档中搜索类型签名"`Shape -> Form`"可以找到几个函数，比如`filled`和`outlined`。

```
filled : Color -> Shape -> Form

outlined : LineStyle -> Shape -> Form 
```

一旦我们完成了一些`Form`的构建，如何将它们转换为`Element`以便进行渲染呢？啊，搜索类型签名"`Form -> Element`"会发现以下内容：

```
collage : Int -> Int -> List Form -> Element 
```

如果我们有一个`Element`想要混入到无结构的图形画布中怎么办呢。搜索"`Element -> Form`"会发现：

```
toForm : Element -> Form 
```

现在让我们利用一些工具来为我们的计数器按钮添加样式。首先，让我们使用[`Text`](http://package.elm-lang.org/packages/elm-lang/core/1.0.0/Text)库来更好地格式化字符串。

```
strStyle : String -> E.Element
strStyle = T.fromString >> T.height 30 >> T.centered 
```

接下来，让我们为绘制边框定义一个自定义行样式，而不是使用称为 `defaultLineStyle` 的默认样式。这些值由包含多个参数的[记录类型](http://elm-lang.org/learn/Syntax.elm#records) `LineStyle` 描述。我们只想自定义其中的一部分参数，因此我们可以使用记录更新语法创建一个新记录，它与 `defaultLineStyle` 几乎相同，只是有一些改变。

```
lineStyle =
  let ls = C.defaultLine in
    { ls | color <- Color.darkCharcoal,
           width <- 10 } 
```

注意，这里我们使用了 `ls` 作为一个变通方法，因为目前解析器只允许在复制记录时使用一个语法变量（没有模块限定符，比如这里的 "`C.`"）。

现在我们将绘制自定义按钮，但我们将使用画廊而不是以前的普通按钮来定义每个三个 `Elements`。

```
btnW = 200
btnH = 60

myButton evt s =
  let mkBtn c =
    C.collage btnW btnH [
        C.filled c (C.rect btnW btnH)
      , C.outlined lineStyle (C.rect btnW btnH)
      , strStyle s |> C.toForm
    ]
  in
  customButton evt
    (mkBtn Color.lightYellow)
    (mkBtn Color.lightOrange)
    (mkBtn Color.lightBlue) 
```

`myButton` 函数以三个步骤绘制一个按钮：首先是实心颜色，然后是边框，最后是按钮标签。传递给 `collage` 的 `Form` 列表被解释为按增加的 z-顺序排列，这意味着每个后续元素都会在前一个元素的顶部呈现。因此，我们必须将标签放在实心矩形之后，这样它就不会被隐藏。

最后一个微调是，让我们改变计数器显示的样式以匹配我们的按钮。为了使显示居中，我们创建一个与按钮宽度相同的容器，并在其中居中文本。

```
 ...
  <| List.intersperse vspace
       [ i |> toString |> strStyle |> E.container btnW btnH E.middle
         ...
       ] 
```

![](https://www.classes.cs.uchicago.edu/archive/2015/winter/22300-1/public-code/Buttons/Buttons1.html)

我们的计数器现在比以前更时尚！查看[源代码](https://www.classes.cs.uchicago.edu/archive/2015/winter/22300-1/public-code/Buttons/Buttons1.elm)和[演示](https://www.classes.cs.uchicago.edu/archive/2015/winter/22300-1/public-code/Buttons/Buttons1.html)。

## "纯按钮"

由于之前讨论了通道和不纯性，你们中的一些人可能无法完全享受我们的按钮示例。如果你一直在想是否有其他方法，我为你在纯度方面的纯洁感鼓掌。在 Elm 中定义按钮的另一种方法，但它也有其他主要缺点。

这个想法是只使用原始鼠标信号，并手动在我们自己的代码中跟踪窗口中的按钮位置。换句话说，我们可以自己编写一个小的事件系统和渲染器。这种方法将放弃[`Graphics.Element`](http://package.elm-lang.org/packages/elm-lang/core/1.0.0/Graphics-Element)中提供的许多抽象的好处。但是，如果我们真的下决心，我们可以遵循这种方法。我们将解决实现计数器应用程序所需的部分内容。

每当鼠标被点击时，我们需要确定其位置是否在一个“按钮”内。因此，我们必须跟踪按钮的边界（以像素为单位）。除了计数器，为了开发目的，让我们显示最后一次点击的位置。

```
type alias Pt    = (Int, Int)
type alias State = (Pt, Int)
initState        = ((-1,-1), 0) 
```

`Mouse.positions`报告的位置将`(0,0)`视为窗口的左上角，因此我们使用负的 x 和 y 值来表示没有点击时的初始状态。

为了简单起见，让我们将计数器显示和按钮放在左上角，彼此之间没有间隔。这将简化我们的像素计算。在定义了显示和按钮的宽度和高度之后，我们可以仅在点击出现在“按钮”的边界内时才在`State`中更新计数器。

```
btnW = 200
btnH = 60

upstate : Pt -> State -> State
upstate (x,y) (_,i) =
  let inPlace i x y = x <= btnW && y >= i * btnH && y < (i+1) * btnH in
  let j =
    if | inPlace 1 x y -> i + 1    -- Increment "button"
       | inPlace 2 x y -> 0        -- Clear "button"
       | otherwise     -> i        -- elsewhere
  in
  ((x,y), j) 
```

然后，我们设置控制器以根据最近鼠标点击位置的更改触发更新。

```
main =
  Signal.map view
    (Signal.foldp upstate initState
      (Signal.sampleOn Mouse.clicks Mouse.position)) 
```

最后是视图。在使用[`Graphics.Collage`](http://package.elm-lang.org/packages/elm-lang/core/1.0.0/Graphics-Collage)库时，重要的是要意识到`collage`的坐标系是以 collage 的中心为中心，而`move`（提供正参数）会将`Shapes`在 collage 中向上和向右移动。（在完成作业 1 时，您可能已经自己发现了这一点。）

这是一个非常快速粗糙的计数器和按钮的渲染，考虑到这两个因素。

```
strStyle : String -> E.Element
strStyle = T.fromString >> T.height 30 >> T.centered

view : State -> E.Element
view st =
  let rows     = 3
      w        = btnW
      h        = rows * btnH
      place i  = C.moveY (btnH - (i-1)*btnH)
      rect c   = C.filled c (C.rect btnW btnH)
      text c s = C.toForm <| color c <| strStyle s
  in
  C.collage w h
    [ place 1 <| rect Color.lightGray
    , place 1 <| text Color.lightGray <| toString st
    , place 2 <| rect Color.lightYellow
    , place 2 <| text Color.lightYellow "Increment"
    , place 3 <| rect Color.lightOrange
    , place 3 <| text Color.lightOrange "Clear"
    , C.outlined C.defaultLine (C.rect w h)
    ] 
```

这是[源代码](https://www.classes.cs.uchicago.edu/archive/2015/winter/22300-1/public-code/Buttons/PureButtons.elm)和[演示](https://www.classes.cs.uchicago.edu/archive/2015/winter/22300-1/public-code/Buttons/PureButtons.html)。为了好玩，您可能希望继续沿着这条路继续实现之前的整个应用程序，采用无`Channel`风格。如果您这样做了，请花点时间思考一下您的视图是否变得不那么纯粹。
