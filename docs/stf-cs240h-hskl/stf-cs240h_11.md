# Web 和数据库编程

## 2014 年 5 月 15 日 - CS240H

## 在我们开始之前…

如果你想在笔记本电脑上跟进到最后：

+   对于 ghc-7.6：

    ```
    $ cabal install simple wai-handler-devel
    ```

+   对于 ghc-7.8

    ```
    $ git clone git://github.com/alevy/simple.git $ git clone git://github.com/alevy/postgresql-orm.git $ cd simple $ cabal install $ cd ../postgresql-orm $ cabal install $ cabal install wai-handler-devel
    ```

你还需要安装 PostgreSQL

## 议程

1.  简介/动机

1.  在 Haskell 中建模 Web 应用程序

1.  构建内容管理系统

## 为什么你应该关心 Web 编程？

> +   互联网开始变得 *非常* 流行
> +   
> +   如果你正在构建某些东西，很有可能你会将其部署为一个互联网 Web 应用程序
> +   
> +   即使你的应用程序看起来不太“网页化”
> +   
> +   HTTP 正在成为普遍的通用协议，用于 API（内部和外部）
> +   
>     +   良好的客户端支持
>     +   
>     +   良好的服务器端支持（框架、SSL、虚拟域等）
>     +   
>     +   易于“向管理层推销”

## 人们如何编写 Web 应用程序？

+   实际上，这取决于…

+   一个繁忙的框架空间

+   曾经被 Java 主导

    +   像“Java Servlet Container”、“J2EE”、“Enterprise Java Beans”、“POJO”这样的术语

    +   每个人在 90 年代末/21 世纪初都有一个非常糟糕的经历

    +   Java 仍然是主要的服务器端语言，例如 Google、Amazon

+   酷炫的孩子们大多在使用动态语言

    +   Ruby/Ruby on Rails/Sinatra

    +   Python/Django

    +   node.js/express

    +   PHP

    +   等等…

## Web 编程 - 今天最流行的语言？

. . .

## 但为什么要使用动态语言？

## 但为什么要使用动态语言？

## 更简洁

例如没有类型声明

```
x = 123 def incr(y) y + 1 end
```

对比

```
protected static int x = 123; public static int incr(int y) { return y + 1; }
```

## 但为什么要使用动态语言？

## 高级特性

像闭包一样

```
Array.map(myarr, new Runnable() { public void run(int elm) { return elm * 42; } })
```

对比。

```
myarr.map {|elm| elm * 42}
```

## 但为什么要使用动态语言？

## 其他不太具有说服力的原因

+   快速开发和原型设计

+   动态语言好因为 *动态* 网站！

> “在渲染网页时，通常会有很多组件在网页上进行交互。你在这里有按钮，在那里有小部件，在一个网页上可能有几十个，甚至可能有几十个或上百个网页在你的网站上，它们都是 **动态** 的。[…] 使用静态类型语言实际上是相当不灵活的。[…] 就像整个系统必须进行类型检查才能移动一个按钮一样”
> 
> - 来自 Twitter 的 Nick Kallen

## 这真的是关于动态性吗？

## 没有类型声明（但仍然有类型）

```
x = 123 -- :: Num a => a incr y = y + 1 -- :: Num a => a -> a
```

## 闭包

```
map (* 42) myarr
```

## 很多论点实际上都是关于 Java 等语言的弱点。

## 在 Haskell 中建模 Web 应用程序

+   声称：一个 Web 应用程序做三件事：

    1.  解析来自客户端的请求

    1.  执行一些副作用（例如读取/写入数据库）

    1.  为客户端生成一些响应

+   给定以下两种类型：

    ```
    data Request = Request {pathInfo :: [String], requestMethod :: Method, ...} data Response = Response Status [Header] String
    ```

+   为 `Application` 填写类型：

    ```
    type Application = ...
    ```

模板代码：`cs240h.scs.stanford.edu/Application.hs`

## 在 Haskell 中建模 Web 应用程序

```
```haskell 数据 Request = Request {pathInfo :: [String], requestMethod :: Method, ...} 数据 Response = Response Status [Header] String 类型 Application = Request -> IO Response ```
```

## 我们刚刚实现了 WAI 包 - “Web Application Interface”！

## WAI 包

+   服务器和应用程序之间的通用接口，这样你可以混合和匹配

+   服务器：

    +   warp

    +   FastCGI

    +   wai-handler-devel（用于开发）

+   应用框架：

    +   Yesod

    +   Scotty

    +   Hails（厚颜无耻的插播）

    +   简单（厚颜无耻的宣传）

    +   其他通过适配器

## WAI 包

```
data Request = Request {  requestMethod :: Method , httpVersion :: HttpVersion , rawPathInfo :: ByteString , rawQueryString :: ByteString , requestHeaders :: RequestHeaders , isSecure :: Bool , remoteHost :: SockAddr , pathInfo :: [Text] , queryString :: Query , requestBody :: Source IO ByteString , vault :: Vault , requestBodyLength :: RequestBodyLength , requestHeaderHost :: Maybe B.ByteString , requestHeaderRange :: Maybe B.ByteString } data Response = ResponseFile Status ResponseHeaders FilePath (Maybe FilePart) | ResponseBuilder Status ResponseHeaders Builder | ResponseSource Status ResponseHeaders (forall b. WithSource IO (C.Flush Builder) b) | ResponseRaw (forall b. WithRawApp b) Response type Application = Request -> IO Response
```

## 一个真正简单的应用程序

让我们构建最简单的应用程序，在浏览器中显示一些内容

+   首先安装 `wai` 和 `warp`：

```
$ cabal install wai warp
```

+   最后，构建应用程序！

```
module Main where import qualified Data.ByteString.Lazy.Char8 as L8 import Network.HTTP.Types import Network.Wai import Network.Wai.Handler.Warp (run) app :: Application app req = return $ responseLBS status200 [] $ L8.pack "Hello, World" main :: IO () main = do run 3000 app
```

> +   演示时间！

## 让我们构建一个 CMS！

1.  （非常）快速介绍 *Simple*

1.  （非常）快速介绍 *postgresql-orm*

1.  写一些代码

## *Simple* - 一个 Haskell 的 Web 框架

*Simple* 是一个只有一个类型的 Web 框架：

```
newtype Controller s a = Controller {  runController :: s -> Request -> IO (Either Response a, s) } instance Monad Controller instance Applicative Controller instance MonadIO Controller
```

+   非常小的 WAI `Application` 类型的包装器

+   让我们在任何地方引用 `Request` 而不需要传递它

+   让我们在任何地方引用一些应用程序状态而不需要传递它

+   让我们决定我们已经准备好响应并停止计算

## 一些 *Simple* 组合器

+   停止计算并响应请求：

```
respond :: Response -> Controller s a okHtml :: ByteString -> Response notFound :: Response respond $ okHtml "Hello world"
```

+   获取请求和应用程序状态：

```
request :: Controller s Request controllerState :: Controller s s
```

+   解析查询和表单参数：

```
queryParam' :: Parseable p => Controller s p parseForm :: Controller s ([Param], (ByteString, FileInfo ByteString))
```

## 一些 *Simple* 组合器

+   路由组合器：

```
-- Match on next dir in path routeName :: Text -> Controller s () -> Controller s () routeName "articles" $ ... -- Treat first dir in path as query param routeVar :: Text -> Controller s () -> Controller s () routeName "articles" $ routeVar "name" $ ... -- Match whole pattern of path routePattern :: Text -> Controller s () -> Controller s () routePattern "/articles/:name" $ ... -- Match if no path left routeTop :: Controller s () -> Controller s () -- Match on request method routeMethod :: Method -> Controller s () -> Controller s () routeMethod GET $ routePatter "/articles/:name" -- Match hostname routeHost :: ByteString -> Controller s () -> Controller s ()
```

## 更高级别的 *Simple* 组合器

常见情况是匹配方法和特定路径模式：

```
get :: Text -> Controller s () -> Controller s () get ptrn ctrl = routeMethod GET $ routePattern ptrn ctrl post :: Text -> Controller s () -> Controller s () post ptrn ctrl = routeMethod POST $ routePattern ptrn ctrl
```

因此，一个典型的小应用程序可能如下所示：

```
myapp :: Controller s () myapp = do get "/" $ respond $ okHtml "Hello World" get "/foo" $ respond $ okHtml "bar"
```

## PostgreSQL ORM

+   对象关系映射器（ORM）

    +   从本地类型映射到 SQL

    +   在我们的情况下，映射到 PostgreSQL 风格的 SQL

+   Haskell 类型必须是这种形式：

```
data Article = Article { articleId :: DBKey , articleTitle :: Text , articleBody :: Text , articleShortName :: Text }
```

+   `Model` 类的实例：

```
class Model a where  modelInfo :: ModelInfo a  modelRead :: RowParser a  modelWrite :: a -> [Action] data DBKey = DBKey !Int64 | NullKey data ModelInfo a = ModelInfo {  modelTable :: ByteString , modelColumns :: [ByteString] , modelPrimaryColumn :: Int , modelGetPrimaryKey :: a -> DBKey }
```

## PostgreSQL ORM

+   如果 `Model` 派生自 `Generic`，我们就不需要编写实现

```
{-# LANGUAGE DeriveGeneric #-} import GHC.Generics data Article = Article { articleId :: DBKey , articleTitle :: Text , articleBody :: Text , articleShortName :: Text } deriving (Show, Generic) instance Model Article
```

+   这使我们可以访问：

```
save :: Model a => Connection -> a -> IO () findAll :: Model a => Connection -> IO [a] findRow :: Model a => Connection -> DBRef a -> IO (Maybe a)
```

+   因为我们在 Haskell 中，让我们避免一堆边缘情况：

    +   字段不能为 null（除非它们是 `Maybe`）

    +   字段不能是不同类型的（除非它们是 `Either`）

    +   验证在许多情况下是多余的

## 好的，让我们开始编码：

```
$ cabal install simple $ smpl create my_cms
```
