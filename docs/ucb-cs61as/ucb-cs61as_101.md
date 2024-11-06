# 伙伴 B 的练习

## 问题 B3

为人们定义一个 `take-all` 方法。如果给出该消息，一个人应该拿走当前位置尚未被任何人拥有的��有东西。

```
> (ask someperson 'take-all) 
```

## 问题 B4：第 1 部分

任何人都可以从任何人那里拿走东西是不现实的。我们想给我们的角色一个 `strength`，然后只有第一个人的 `strength` 大于第二个人的时候，第一个人才能从第二个人那里拿东西。

然而，我们不会通过添加本地 `strength` 变量来使人类类变得混乱。这是因为我们可以预期随着程序的进一步开发，我们可能会想要添加更多属性。人们可以拥有 *魅力* 或 *智慧*；事物可以是 *食物* 或不是；地方可以是 *室内* 或不是。因此，你将创建一个名为 `basic-object` 的类，它保留一个名为 `properties` 的本地变量，其中包含一个属性值表，就像我们在第 6 课中使用 `get` 和 `put` 一样。然而，`get` 和 `put` 指的是所有操作的一个固定表；在这种情况下，我们需要为每个对象单独的表。文件 `tables.scm` 包含了表抽象数据类型的实现：

+   构造函数：`(make-table)` 返回一个新的空表。

+   修改器：`(insert! key value table)` 向表中添加一个新的键值对。

+   选择器：`(lookup key table)` 返回相应的值，如果键不在表中，则返回 `#f`。

你将在 [SICP 3.3.3 (pp. 266-268)](https://mitpress.mit.edu/sicp/full-text/sicp/book/node63.html) 中学习表是如何实现的。现在，只需将它们视为原始的。

你将修改 `person`、`place` 和 `thing` 类，使它们从 `basic-object` 继承。这个对象将接受一个 `put` 消息，以便以下调用做正确的事情：

```
 > (ask Brian 'put 'strength 100) 
```

此外，`basic-object` 应该将任何未被识别为该名称属性请求的消息视为请求。

```
 > (ask Brian 'strength)
    100 
```

应该在不必在类定义中显式编写 `strength` 方法的情况下工作。

不要忘记，如果你要求列表中没有的属性，属性列表机制会返回 `#f`。这意味着即使我们没有在对象中 `put` 该属性，以下调用也不应该出错：

```
 > (ask Brian 'charisma) 
```

这对于真假属性很重要，除非我们明确为它们 `put` 一个 `#t` 值，否则它们将自动为 `#f`（但不会出错）。

给人们一些合理的初始力量。（每个新实例化的人对象应该是相同的。）后来，他们可以通过进食变得更强。

## 问题 B4：第 2 部分

你会注意到类型谓词 `person?` 检查参数的类型是否是列表 `'(person police thief)` 的成员。这意味着 `person?` 过程必须保持一个从 `person` 继承的所有类的列表，如果我们创建一个新的子类，这将很麻烦。

我们将利用属性列表来实现一个更好的类型检查系统。如果我们向 person 类添加一个名为 `person?` 的方法，并让它始终返回 `#t`，那么任何属于 person 类型的对象都将自动继承此方法。没有从 person 继承的对象将找不到 `person?` 方法，并且在其属性表中找不到 `person?` 条目，因此它们将返回 `#f`。

同样，地方应该有一个 `place?` 方法，东西应该有一个 `thing?` 方法。

```
> (ask brian 'person?)
 #t 
```

添加这些类型方法，并将类型谓词过程的实现更改为这种新实现（在 `adv.scm` 的底部）。不要忘记添加 `place?` 的定义。

新的类型谓词应该执行以下操作：

```
 > (person? brian)
 #t
 > (place? soda)
 #t
 > (thing? coffee)
 #t 
```

记住 `person?` 应该适用于从 `person` 继承的类，如稍后定义的 `thief` 和 `police`。`place?` 和 `thing` 也是如此。

## 问题 B5：第 1 部分

在现代，许多地方允许您连接到网络。将 `hotspot` 定义为一种允许网络连接的地方。每个热点应该有一个 `name` 和一个 `password` 作为必须知道的实例变量以便连接。

```
> (define library (instantiate hotspot 'library 1234))   
;name of hotspot is library, password is 1234 
```

（注意：我们设想的是每个网络一个密码，而不是像 AirBears 那样每个人一个密码。）热点有一个 `connect` 方法，带有两个参数，一个 `laptop`（一种即将发明的东西）和一个密码。如果密码正确，并且笔记本在热点中，则将其添加到已连接笔记本的列表中，否则返回错误。当笔记本离开热点时，将其从列表中移除。

```
> (ask library 'connect somelaptop 1234) 
```

热点还有一个 `surf` 方法，带有两个参数，一个笔记本和一个文本字符串，例如

```
 "http://www.cs.berkeley.edu" 
```

如果笔记本连接到网络，则 surf 方法应该

```
 (system (string-append "lynx " url)) 
```

当 URL 是文本字符串参数时（注意在 "lynx " 中的 x 后面有一个空格），否则返回错误。

```
> (ask library 'surf somelaptop "http://www.cs.berkeley.edu") 
```

## 问题 B5：第 2 部分

现在发明 `laptop` 类。笔记本有一个实例变量，即其名称。

```
> (define somelaptop (instantiate laptop 'somelaptop) 
```

笔记本是一种具有两个额外方法的东西：`connect`，带有密码作为参数，向笔记本所在的地方发送一个 `connect` 消息。如果密码错误，则返回错误。

```
> (ask somelaptop 'connect 1234) 
```

笔记本还有另一个方法，`surf`，带有一个 URL 文本字符串作为参数，向其所在的地方发送一个 `surf` 消息。因此，每当笔记本进入新的热点时，用户必须请求连接到该热点的网络；当笔记本离开热点时，它必须自动断开网络连接。（如果它在除热点之外的地方，`surf` 消息将不被理解；如果它在热点中但未连接，则返回错误）。

```
> (ask somelaptop 'surf "www.berkeley.edu") 
```
