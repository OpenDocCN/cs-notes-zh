# 编译成 JavaScript 并在浏览器中运行

Kotlin 自带一个编译器，将 Kotlin 源代码编译成 JavaScript，准备好包含在网页中。因此，你可以创建完全在 Web 浏览器中运行的应用程序。

为了帮助你入门，这里有一些提示和一个示例项目。

我们首先创建一个新目录。我们将在此目录中创建三个文件：

+   canvas.html：浏览器加载的网页；

+   canvas.js：从网页加载的 JavaScript 代码；

+   jscanvas.js：我们将使用的 org.otfried.cs109js.JsCanvas 类的 JavaScript 代码；

+   kotlin.js：JavaScript 的 Kotlin 标准库。

让我们从最后一个开始：kotlin.js 包含在 Kotlin 编译器附带的 kotlin-jslib.jar 文件中。用你喜欢的工具提取 kotlin.js 并将其放在你的新目录中（jar 文件只是被简单压缩的存档）。

文件 jscanvas.js 也很容易获得：它包含在你之前安装过的档案 cs109-jslib.jar 中。

这是一个示例 HTML 文件（[canvas.html](https://github.com/otfried/cs109-kotlin/raw/master/js/canvas/canvas.html)）：

```
<html>
<head>
<meta charset="utf-8">
<script src="kotlin.js"></script>
<script src="jscanvas.js"></script>
<script src="canvas.js"></script>
</head>
<body onload="javascript:Kotlin.modules['canvas'].canvas.start();">
<canvas width="600" height="300" id="canvas"></canvas>
<div id="text">This is a fun paragraph. </div>
</body>
</html>

```

在文档的头部，我们加载两个库和我们自己的 JavaScript 代码 canvas.js（我们仍然需要生成）。在 body 中，我们包含两个元素：一个 HTML 画布，这是一个我们可以从 JavaScript 自由绘制的矩形区域，和一个文本分区（稍后我们可以从 JavaScript 中更新）。

现在从你的浏览器加载此文件：你应该看到一个空白的白色矩形和下面的文本。

此时，我们应该在 Web 浏览器中打开 JavaScript 控制台。这是 JavaScript 的所有输出，以及任何错误消息，将会显示的地方。在 Firefox 中，使用菜单、开发者、Web 控制台。在 Safari 中，转到设置并勾选“显示开发菜单”复选框，然后转到新出现的开发菜单并打开控制台。

到目前为止，控制台应该只显示一个错误消息：

```
TypeError: Kotlin.modules.canvas is undefined

```

这是 body 标签中 onload 属性的响应。在这里，我们指示 JavaScript 在网页完全加载后（这一点很重要，因为我们希望所有 HTML 元素在代码运行时都存在）在 canvas.js 脚本中执行包 canvas 中的函数 start。

剩下的是编写这个 start 函数并生成 canvas.js。这里是一个第一个示例（[canvas1.kt](https://github.com/otfried/cs109-kotlin/raw/master/js/canvas/canvas1.kt)）：

```
package canvas

import org.otfried.cs109js.JsCanvas
import org.otfried.cs109.Color

import kotlin.browser.document
import org.w3c.dom.*

fun start() {
  println("Hello World from Javascript")

  val canvas = JsCanvas("canvas")
  canvas.clear(Color.GREEN)

  val text = document.getElementById("text")
  text?.appendChild(document.createTextNode("Was du hier liest ist kein Gedicht.")) 
}

```

我们需要通过以下方式将该文件编译成 JavaScript：

```
$ kotlinc-js -output canvas.js canvas1.kt 

```

kotlinc-js 是 Kotlin 到 JavaScript 的编译器。我指定输出文件名（在从 JavaScript 调用时对应于模块 Kotlin.modules['canvas']）。开始处的包声明将 start 函数放在 canvas 包中，因此需要从 JavaScript 中调用它作为

```
Kotlin.modules['canvas'].canvas.start();

```

这正是我们在 onload 属性中编写的内容。

现在重新加载网页，画布矩形会变成绿色，底部的文本也会改变。在 JavaScript 控制台中，你应该会看到 println 语句的输出。

让我们通过添加一些颜色、文本和透明度来使我们的绘图更加有趣（[canvas2.kt](https://github.com/otfried/cs109-kotlin/raw/master/js/canvas/canvas2.kt)）：

```
package canvas

import org.otfried.cs109js.JsCanvas
import org.otfried.cs109.Color

object Controller {
  val canvas = JsCanvas("canvas")
  var x = 30.0
  var y = 50.0
  var alpha = 45.0

  fun draw() {
    canvas.clear(Color.WHITE)
    canvas.setAlpha(48)
    canvas.setColor(Color.GREEN)
    canvas.drawRectangle(10.0, 10.0, 100.0, 100.0)
    canvas.setAlpha(255) // opaque
    for (i in 0 .. 5) {
      for (j in 0 .. 5) {
        canvas.setColor(Color(Math.floor(255-42.5*i), Math.floor(255-42.5*j), 0))
        canvas.drawRectangle(150.0 + j*25.0, i*25.0, 25.0, 25.0)
      }
    }
    canvas.translate(x, y)
    canvas.setAlpha(128)
    canvas.rotate(alpha)
    canvas.setColor(Color.RED)
    canvas.setFont(32.0)
    canvas.drawText("Lovely", 0.0, 0.0)
  }
}

fun start() {
  println("Canvas2 starting...")
  Controller.draw()
}

```

我们再次编译：

```
$ kotlinc-js -output canvas.js canvas2.kt 

```

现在重新加载网页，画布应该包含一个透明的绿色正方形，在上面有一些半透明的红色文本，右侧还有一个漂亮的颜色图案。

到目前为止都很顺利，现在让我们添加一些交互性。当你在画布上点击鼠标时，文本应该移动到这个位置。按下键盘上的 'a'、's'、'w' 和 'z' 键可以用来移动文本，按下 'j' 和 'k' 键可以旋转它（[canvas3.kt](https://github.com/otfried/cs109-kotlin/raw/master/js/canvas/canvas3.kt)）：

```
package canvas

import org.otfried.cs109js.JsCanvas
import org.otfried.cs109.Color

import kotlin.browser.window
import org.w3c.dom.events.*

object Controller {
  val canvas = JsCanvas("canvas")
  var x = 30.0
  var y = 50.0
  var alpha = 45.0

  fun draw() {
    canvas.save()
    canvas.clear(Color.WHITE)
    canvas.setAlpha(48)
    canvas.setColor(Color.GREEN)
    canvas.drawRectangle(10.0, 10.0, 100.0, 100.0)
    canvas.setAlpha(255) // opaque
    for (i in 0 .. 5) {
      for (j in 0 .. 5) {
        canvas.setColor(Color(Math.floor(255-42.5*i), Math.floor(255-42.5*j), 0))
        canvas.drawRectangle(150.0 + j*25.0, i*25.0, 25.0, 25.0)
      }
    }
    canvas.translate(x, y)
    canvas.setAlpha(128)
    canvas.rotate(alpha)
    canvas.setColor(Color.RED)
    canvas.setFont(32.0)
    canvas.drawText("Lovely", 0.0, 0.0)
    canvas.restore()
  }

  fun keyDown(e: Event) {
    val ek = e as KeyboardEvent
    var k = ek.key
    if (k === undefined)
      k = "${ek.keyCode.toChar().toLowerCase()}"
    when (k) {
    "a" -> x -= 3
    "s" -> x += 3
    "w" -> y -= 3
    "z" -> y += 3
    "j" -> alpha += 10.0
    "k" -> alpha -= 10.0
    else -> return
    }
    draw()
    e.preventDefault()
  }

  fun mouseDown(e: Event) {
    val em = e as MouseEvent
    x = em.offsetX
    y = em.offsetY
    draw()
  }
}

fun start() {
  println("Canvas3 starting...")
  println("Active keys are aswzjk")
  Controller.draw()
  window.addEventListener("keydown", { Controller.keyDown(it) }, true)
  window.addEventListener("mousedown", { Controller.mouseDown(it) }, true)
}

```

我们再次编译：

```
$ kotlinc-js -output canvas.js canvas3.kt 

```

重新加载网页。现在你应该能够点击画布并看到文本移动到这个位置。当你按下其中一个活动键时，文本应该移动和旋转。

最后，让我们给我们的绘图添加一些动画效果。按下 'g' 键开始动画，并再次暂停。现在的代码还会调整画布大小以填满整个浏览器窗口，只留下一点空间给滚动条和底部的文本（[canvas4.kt](https://github.com/otfried/cs109-kotlin/raw/master/js/canvas/canvas4.kt)）：

```
package canvas

import org.otfried.cs109js.JsCanvas
import org.otfried.cs109.Color

import kotlin.browser.window
import org.w3c.dom.events.*

object Controller {
  val canvas = JsCanvas("canvas")
  // change canvas size to fill entire browser window
  init {
    canvas.canvas.width = window.innerWidth.toInt() - 20
    canvas.canvas.height = window.innerHeight.toInt() - 50
  }

  var x = 30.0
  var y = 50.0
  var alpha = 45.0
  var animate = false
  var timeStamp = 0.0

  fun draw() {
    canvas.save()
    canvas.clear(Color.WHITE)
    canvas.setAlpha(48)
    canvas.setColor(Color.GREEN)
    canvas.drawRectangle(10.0, 10.0, 100.0, 100.0)
    canvas.setAlpha(255) // opaque
    for (i in 0 .. 5) {
      for (j in 0 .. 5) {
        canvas.setColor(Color(Math.floor(255-42.5*i), Math.floor(255-42.5*j), 0))
        canvas.drawRectangle(150.0 + j*25.0, i*25.0, 25.0, 25.0)
      }
    }
    canvas.translate(x, y)
    canvas.setAlpha(128)
    canvas.rotate(alpha)
    canvas.setColor(Color.RED)
    canvas.setFont(32.0)
    canvas.drawText("Lovely", 0.0, 0.0)
    canvas.restore()
    if (animate)
      window.requestAnimationFrame { animate(it) }
  }

  fun animate(s: Double) {
    val delta = s - timeStamp
    timeStamp = s
    x += delta / 2.0
    if (x > canvas.width)
      x = 0.0
    alpha += 0.3 * delta
    if (alpha >= 360.0)
      alpha = 0.0
    draw()
  }

  fun keyDown(e: Event) {
    val ek = e as KeyboardEvent
    var k = ek.key
    if (k === undefined)
      k = "${ek.keyCode.toChar().toLowerCase()}"
    when (k) {
    "a" -> x -= 3
    "s" -> x += 3
    "w" -> y -= 3
    "z" -> y += 3
    "j" -> alpha += 10.0
    "k" -> alpha -= 10.0
    "g" -> {
        if (!animate)
          timeStamp = window.performance.now()
        animate = !animate
    }
    else -> return
    }
    draw()
    e.preventDefault()
  }

  fun mouseDown(e: Event) {
    val em = e as MouseEvent
    x = em.offsetX
    y = em.offsetY
    draw()
  }
}

fun start() {
  println("Canvas3 starting...")
  println("Active keys are aswzjk and g for animation")
  Controller.draw()
  window.addEventListener("keydown", { Controller.keyDown(it) }, true)
  window.addEventListener("mousedown", { Controller.mouseDown(it) }, true)
}

```

现在你可以编写自己的 web 应用程序了。或者尝试一下 我的实现 的 2048 游戏。移动键是 'u'、'd'、'l' 和 'r'。

#### 直接使用 Javascript Canvas API

我的 JsCanvas 类很方便，因为你可以使用相同的绘图代码来绘制位图和 CS109 Android 框架，当然，你也可以从 HTML 文件中移除 jscanvas.js 文件，并直接使用 JavaScript 函数来绘制到画布上。查看 [canvas-nojscanvas.kt](https://github.com/otfried/cs109-kotlin/raw/master/js/canvas/canvas-nojscanvas.kt) 可以看到没有 JsCanvas 的最新版本是什么样子的。你可能会发现 [Mozilla 文档](https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D) 有所帮助：虽然它是为 JavaScript 设计的，但其中很多代码在 Kotlin 中也可以不变地使用。
