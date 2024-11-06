# 杂项 Elm 演示 I

## 演示：[`elm-diagrams`](http://package.elm-lang.org/packages/vilterp/elm-diagrams/3.0.0)

查看 Pete 的用于在空间中组合 2D 图形的酷库，以及一些示例[这里](https://github.com/vilterp/elm-diagrams)。

## 演示：[`stage`](http://package.elm-lang.org/packages/imeckler/stage/1.5.0)（现在称为[`piece`](http://package.elm-lang.org/packages/imeckler/piece/2.0.0)）

查看 Izaak 的用于在时间中组合图形的酷库，以及一些示例[这里](https://github.com/imeckler/isomdemo)和[这里](https://github.com/imeckler/shortwords)。

## 演示：通过端口使用本地存储

#### [HTML5 本地存储](http://www.w3schools.com/html/html5_webstorage.asp)

参见[`LocalStorage.html`](https://www.classes.cs.uchicago.edu/archive/2015/winter/22300-1/public-code/Ports/LocalStorage.html)一个示例，说明如何使用 JavaScript 在网页访问之间保存信息（按域名分）。

#### Elm[Ports](http://elm-lang.org/learn/Ports.elm)

传出端口用于从 Elm 通信到 JavaScript，传入端口用于从 JavaScript 通信到 Elm。

定义一个 Elm 模块[`CountPageVisits.elm`](https://www.classes.cs.uchicago.edu/archive/2015/winter/22300-1/public-code/Ports/CountPageVisits.elm)，其中包含`port`s，它们就像“外部”`Signal`s 一样：

```
module CountPageVisits where

import Text (plainText)
import Signal
import Mouse

port count : Signal Int

port reset : Signal ()
port reset = Mouse.clicks

main =
  Signal.map (\i -> plainText ("Counter: " ++ toString i)) count 
```

在一个 JavaScript 文件[`Ports.js`](https://www.classes.cs.uchicago.edu/archive/2015/winter/22300-1/public-code/Ports/Ports.js)中，加载 Elm 模块`Elm.CountPageVisits`，并`send`到其传入端口，并`subscribe`到其传出端口：

```
function getCount()       { ... }
function incCount()       { ... }
function resetCount()     { ... }
function getAndIncCount() { ... }

var myApp = Elm.fullscreen(Elm.CountPageVisits, {
  count: getAndIncCount()
});

myApp.ports.reset.subscribe(function(event) {
  resetCount();
  myApp.ports.count.send(getAndIncCount());
}); 
```

编译 Elm 模块为 JavaScript...

```
% elm-make CountPageVisits.elm --output=CountPageVisits.js 
```

... 然后在[`CountPageVisits.html`](https://www.classes.cs.uchicago.edu/archive/2015/winter/22300-1/public-code/Ports/CountPageVisits.html)中将各部分组合起来。

## 导入社区包

到目前为止，我们只使用了[核心包库](http://package.elm-lang.org/packages/elm-lang/core/1.0.0)。还有越来越多的[社区包](http://package.elm-lang.org/packages)。使用它们很容易。只需定义一个指定要导入的库的`elm-package.json`文件即可。

假设我们想要使用[这个 HTML 包](http://package.elm-lang.org/packages/evancz/elm-html/2.0.0)。将该包的位置添加到一个否则是样板`elm-package.json`文件中：

```
{
    "version": "1.0.0",
    "summary": "helpful summary of your project, less than 80 characters",
    "repository": "https://github.com/USER/PROJECT.git",
    "license": "BSD3",
    "source-directories": [
        "."
    ],
    "exposed-modules": [],
    "dependencies": {
        "elm-lang/core": "1.1.0 <= v < 2.0.0",
        "evancz/elm-html": "2.0.0 <= v < 3.0.0"
    }
} 
```

该包导出的 Elm 模块的名称在其[文档页面](http://package.elm-lang.org/packages/evancz/elm-html/2.0.0)的顶部列出。您也可以在文档页面上点击“查看源代码”，查看[`elm-package.json`文件](https://github.com/evancz/elm-html/blob/2.0.0/elm-package.json)。

现在，在 Elm 文件`HtmlTest.elm`中`import`并使用该库...

```
module HtmlTest where

import Html (..)

main =
     toElement 500 500
  <| div []
  <| [ h1 [] [text "Header 1"]
     , ol [] [li [] [text "one"], li [] [text "two"], li [] [text "three"]]
     , ul [] [li [] [text "one"], li [] [text "two"], li [] [text "three"]]
     , button [] [text "click me"]
     , input [] [text "type here"]
     ] 
```

... 并且适当版本的库将被下载到本地的`elm-stuff/`目录中：

```
% ls
HtmlTest.elm    elm-package.json

% elm-make HtmlTest.elm --output=HtmlTest.html
Some new packages are needed. Here is the upgrade plan.

  Install:
    elm-lang/core 1.1.0
    evancz/elm-html 2.0.0
    evancz/virtual-dom 1.2.2

Do you approve of this plan? (y/n) y
Downloading elm-lang/core
Downloading evancz/elm-html
Downloading evancz/virtual-dom
Packages configured successfully!
Compiled 38 files
Successfully generated HtmlTest.html

% ls
HtmlTest.elm    HtmlTest.html   elm-package.json  elm-stuff 
```

在后续的作业和项目任务中，您可以提交一个`elm-package.json`来声明您希望使用的任何社区库。

如果你最终建立了自己的有用库，考虑[发布它们](http://package.elm-lang.org/)！
