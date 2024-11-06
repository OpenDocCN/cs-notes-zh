# 基本动画

到目前为止，我们所有的渲染都是“静态”的，即状态或模型值独立于时间（尽管它们依赖于其他变化的值，如鼠标位置和点击）。

现在我们将通过一个示例来跟踪时间以*动画化*我们渲染的内容。我们的目标是绘制每个鼠标点击周围逐渐消失的圆圈。

### 带时间戳的点击

我们将从在我们的应用程序中定义`State`为`Click`列表开始，其中每个值记录点击的`Time`和位置。

```
type alias Click = (Time.Time, (Int,Int))
type alias State = List Click 
```

初始`State`的定义以及在每次`Click`时更新它的函数都是微不足道的。

```
initState = []
upstate   = (::) 
```

为了在开发过程中提供帮助，让我们渲染最近的`Click`以查看我们应用程序的`State`如何变化。

```
view (w,h) clicks =
  let str = case clicks of
              []   -> T.asText "No clicks yet"
              p::_ -> T.asText p
  in
    C.collage w h [C.toForm str] 
```

现在我们需要使用原始信号来“驱动”我们的应用程序。特别是，我们需要跟踪时间和鼠标点击。[定义时间的一种方法](http://elm-lang.org/edit/examples/Reactive/Fps.elm)是对[`Time.fps`](http://package.elm-lang.org/packages/elm-lang/core/1.0.0/Time)返回的时间增量求和。

```
time : Signal Time.Time
time = Signal.foldp (+) 0 (Time.fps 10) 
```

接下来，我们可以通过在更新`Mouse.clicks`时采样`time`和`Mouse.position`来为点击生成时间戳。请注意，我们如何使用`(<~)`和`(~)`运算符调用[`Signal.map2`](http://package.elm-lang.org/packages/elm-lang/core/1.0.0/Signal)（带有更好的语法）以配对时间和位置值。

```
clicks : Signal Click
clicks =
  let onClick = Signal.sampleOn Mouse.clicks in
  (,) <~ onClick time ~ onClick Mouse.position 
```

现在我们可以根据`clicks`信号更新我们的`State`，以便将最新的一个渲染到屏幕上。

```
state : Signal State
state = Signal.foldp upstate initState clicks

main =
  view <~ Window.dimensions ~ state 
```

将时间戳附加到变化的值的这种模式适用于以下泛化：

```
timestamp : Signal a -> Signal (Time.Time, a)
timestamp sig =
  (,) <~ Signal.sampleOn sig time ~ sig

clicks : Signal Click
clicks = timestamp (Signal.sampleOn Mouse.clicks Mouse.position) 
```

实际上，[`Time`](http://package.elm-lang.org/packages/elm-lang/core/1.0.0/Time)库提供了一个`timestamp`函数，尽管行为略有不同：附加到值的时间戳记录系统时间（通过`Time.every`），而不是应用程序时间（通过`Time.fps`计算）。

### 绘制所有点

我们将从为所有点击绘制圆圈开始，不考虑它们的时间戳。有几个因素需要考虑：

+   鼠标坐标（由`Mouse.position`产生）是相对于窗口左上角指定的，

+   `collage`（我们将用它来绘制整个窗口）居中于窗口中间，而

+   `move`（提供正参数）将`Shapes`在 collage 中向上和向右移动。

考虑到这些，我们绘制点如下：

```
view (w,h) clicks =

  let str     = case clicks of
                  []   -> T.asText "No clicks yet"
                  p::_ -> T.asText p
      circ    = C.filled Color.darkBlue (C.circle 20)
      (fw,fh) = (toFloat w, toFloat h)
      (dx,dy) = (-fw/2, fh/2)
      dots =
        clicks |> List.map (\(_,(x,y)) ->
          circ |> C.move (toFloat x + dx, toFloat (-y) + dy))
  in

    C.collage w h (dots ++ [C.toForm str]) 
```

这个里程碑的源代码可以在[`FadingDots0.elm`](https://www.classes.cs.uchicago.edu/archive/2015/winter/22300-1/public-code/Animations/FadingDots0.elm)找到，并且[这里](https://www.classes.cs.uchicago.edu/archive/2015/winter/22300-1/public-code/Animations/FadingDots0.html)是演示示例。

### 绘制最近的点

为了只显示最近的点，我们需要在`State`中跟踪当前时间 —— 没有其他地方可以放置它！

```
type alias State = (Time.Time, List Click)

initState = (0, []) 
```

更新函数将新的`Click`的时间戳`t`存储为当前时间（即最近更新的当前时间）。

```
upstate (t,xy) (_,clicks) = (t, (t,xy)::clicks) 
```

现在我们在我们的`State`中有了`now`时间，我们只能为最近的，比如说，两秒内发生的点击绘制点。如果需要，`tfade`绑定允许我们调整此参数。

```
view (w,h) (now,clicks) =

  let str     = case clicks of {[] -> T.asText "..."; p::_ -> T.asText p}
      circ    = C.filled Color.darkBlue (C.circle 20)
      (fw,fh) = (toFloat w, toFloat h)
      (dx,dy) = (-fw/2, fh/2)
      tfade   = 2 * Time.second
      dots =
        clicks |> List.concatMap (\(t,(x,y)) -> if
          | (now-t) > tfade -> []
          | otherwise ->
              [circ |> C.move (toFloat x + dx, toFloat (-y) + dy)]
        )
  in

    C.collage w h (dots ++ [C.toForm str]) 
```

此里的关键代码可以在[`FadingDots1.elm`](https://www.classes.cs.uchicago.edu/archive/2015/winter/22300-1/public-code/Animations/FadingDots1.elm)中找到，并且[这里](https://www.classes.cs.uchicago.edu/archive/2015/winter/22300-1/public-code/Animations/FadingDots1.html)是演示效果。

这是很好的进展，但是点可能会停留超过两秒；旧点只有在下一个点击发生时才会“丢弃”，这可能会是任意远的将来。那么，我们能做些什么呢？

### 合并信号

我们应用程序的`State`（在`main`中）被定义为仅对`clicks`的更改做出反应，但我们还希望对`time`的更改做出反应，以便我们能够及时“丢弃”旧的点击。以下函数将两个信号合并为一个：

```
Signal.merge : Signal a -> Signal a -> Signal a 
```

我们不能立即`merge`信号`time`和`clicks`，因为它们产生不同类型的值。不过，不用担心，因为我们可以定义一个新的数据类型来描述任一信号产生的值。然后，我们的更新函数将分别处理每种类型的值。

```
type Update = NewTime Time.Time | NewClick Click

upstate u (_,clicks) = case u of
  NewTime t       -> (t, clicks)
  NewClick (t,xy) -> (t, (t,xy)::clicks) 
```

注意`NewTime`和`NewClick`值如何携带新时间`t`以跟踪更新的`State`中的时间。

当我们修改`upstate`时，我们也可以优化我们的`State`表示，以便它仅包含将要呈现的那些点。下面的`pruneOld`函数利用了`State`中点击是按年轻到年长排序的不变性。因此，一旦找到第一个“陈旧”的点，它就会停止遍历点击。

```
pruneOld now clicks = case clicks of
  [] -> []
  (t,xy) :: clicks' -> if
    | (now-t) > tfade -> []
    | otherwise       -> (t,xy) :: pruneOld now clicks'

upstate u (_,clicks) = case u of
  NewTime t       -> (t, pruneOld t clicks)
  NewClick (t,xy) -> (t, (t,xy) :: pruneOld t clicks) 
```

现在我们更新我们的`main`来`merge`这两个信号，其中它们的值适当地使用`NewTime`和`NewClick`数据构造器包装。

```
state = Signal.foldp upstate initState
          (Signal.merge (NewTime  <~ time)
                        (NewClick <~ clicks)) 
```

### 动画：淡出

我们已经到了尾声。点现在将迅速消失，但让它们逐渐淡出，并且同时增大尺寸以实现漂亮的扩散效果。

对于每次鼠标点击，我们将`pct`定义为从点首次出现（其时间戳`t`）到完全消失（`t + tfade`）之间经过的时间百分比。我们使用这个系数来计算圆圈的透明度以及其增加的半径。

```
setAlpha : Float -> Color.Color -> Color.Color
setAlpha a c =
  let rgb = Color.toRgb c in
  Color.rgba rgb.red rgb.green rgb.blue a

view (w,h) (now,clicks) =

  let
      (fw,fh) = (toFloat w, toFloat h)
      (dx,dy) = (-fw/2, fh/2)
      color a = setAlpha a Color.darkBlue
      rad pct = 20 + 100 * pct
      circ pct = C.filled (color (1-pct)) (C.circle (rad pct))
      dots =
        clicks |> List.map (\(t,(x,y)) ->
          let pct = (now-t) / tfade in
          circ pct |> C.move (toFloat x + dx, toFloat (-y) + dy))
  in

    C.collage w h dots 
```

注意，`view`不再需要过滤旧点，因为`upstate`已经处理了。更加令人愉快的工作分解！

![](https://www.classes.cs.uchicago.edu/archive/2015/winter/22300-1/public-code/Animations/FadingDots2.html)

现在我们正在绘制较大的圆圈，帧之间的延迟变得更加明显。所以，让我们加大它。

```
time = Signal.foldp (+) 0 (Time.fps 40) 
```

最终版本包含在 [`FadingDots2.elm`](https://www.classes.cs.uchicago.edu/archive/2015/winter/22300-1/public-code/Animations/FadingDots2.elm) 中。看看它在[action](https://www.classes.cs.uchicago.edu/archive/2015/winter/22300-1/public-code/Animations/FadingDots2.html)中的效果！

### 跟踪时间的不同方式

注意，有两种不同的方法来跟踪 Elm 应用程序运行了多长时间：一种是通过累加由`Time.fps`产生的时间增量（就像我们在这个例子中做的那样），另一种是将`Time.every`的当前值与其初始值进行比较。这两种方法并不总是产生相同的结果！要进行调查，请尝试 Stuart Kurtz 的[`Lag.elm`](https://www.classes.cs.uchicago.edu/archive/2015/winter/22300-1/public-code/Animations/Lag.elm) 示例。
