# 高阶函数和函数字面量

这是一个计算从 \(a\) 到 \(b\) 的整数和的函数（[higher1.kts](https://github.com/otfried/cs109-kotlin/raw/master/tutorial/40-lambda/higher1.kts)):

```
fun sumInt(a: Int, b: Int): Int {
  var s = 0
  for (i in a .. b)
    s += i
  return s
}

```

这里是计算从 \(a\) 到 \(b\) 的整数立方和的代码：

```
fun sumCubes(a: Int, b: Int): Int {
  var s = 0
  for (i in a .. b)
    s += i * i * i
  return s
}

```

注意 sumInt 和 sumCubes 几乎相同——它们只在每次循环迭代中添加到 s 的表达式上有所不同。

这两个函数是计算表达式的特殊情况

\[ \sum_{i=a}^b f(i) \]对于不同选择的函数 \(f\)。

如果数学有一种表示这种常见表达式的符号，那么计算机科学也应该有。我们应该能够编写一个以函数 \(f\) 作为参数的函数 sum。

在 Kotlin 中，我们可以这样做：([higher2.kts](https://github.com/otfried/cs109-kotlin/raw/master/tutorial/40-lambda/higher2.kts)):

```
fun sum(a: Int, b: Int, f: (Int) -> Int): Int {
  var s = 0
  for (i in a..b) 
    s += f(i)
  return s
}

```

注意三个参数的类型：a 和 b 是整数，但 f 有一个更有趣的类型：(Int) -> Int。这种类型表示从整数到整数的函数。一般来说，表示 (A, B, ...) -> R 的符号表示一个接受类型为 A、B 等的参数并返回类型为 R 的结果的函数。

要调用函数 sum，我们需要为参数 f 提供一个参数值。现代编程语言如 Kotlin（以及 Scala、Swift、Java 自 Java 8 以来，以及 C++自 C++11 以来）使得可以定义一个函数而无需给它命名。这被称为函数字面量、匿名函数或 lambda。

注意对于其他基本对象，我们经常定义"无名称"对象：我们不需要为每个字符串或每个整数命名。例如，我们不必写成这样：

```
>>> val str: String = "Hello CS109"
>>> val a: Int = 13
>>> println(str); println(a)

```

相反，我们只需写成：

```
>>> println("Hello CS109"); println(13)

```

直接写在程序中的对象的值称为字面量。例如，写入 1234 是一个整数字面量，写入"CS109"是一个字符串字面量。

函数字面量的语法包含包含参数的大括号，一个右箭头，以及一些计算结果的代码。例如，将整数提升到其立方的函数写为

```
{ x: Int -> x * x * x }

```

计算两个整数的和的函数字面量如下所示：

```
{ a: Int, b: Int -> a + b }

```

执行函数字面量的效果是创建一个函数对象（不给它命名）：

```
>>> { x: Int -> x * x * x }
kotlin.jvm.functions.Function1<java.lang.Integer, java.lang.Integer>

```

一个函数对象存在于堆上，就像其他对象一样。我们可以为其指定一个名称，或将其引用存储在集合或另一个对象中。而且，由于它是一个函数对象，我们可以像调用函数一样调用它。

这里我们创建一个函数对象并立即使用一个参数调用它：

```
>>> { x: Int -> x * x * x }(3)
27

```

这里我们为函数对象指定一个名称，并使用它来使用不同的参数调用它：

```
s
>>> val f = { x: Int -> x * x * x }
>>> f(3)
27
>>> f(7)
343
>>> f(-30)
-27000

```

这里我们在列表中存储了几个函数对象：

```
>>> val g = listOf({ x: Int -> x * x },
...                { x: Int -> x * x * x },
...                { x: Int -> x * x * x * x })
>>> g0
4
>>> g1
8
>>> g2
16

```

回到我们的函数 sum，现在我们可以使用它来计算整数的和以及立方的和：

```
>>> :load higher2.kts
>>> sum(1, 100, { x: Int -> x } )
5050
>>> sum(1, 100, { x: Int -> x * x * x } )
25502500

```

实际上，在这种情况下，编译器可以自动确定函数文字中参数的类型。编译器知道 sum 的最后一个参数是类型为 (Int) -> Int 的函数，因此它知道作为参数编写的任何函数文字的类型应该是此类型。因此，我们可以在函数文字中省略类型：

```
>>> sum(1, 100, { x -> x } )
5050
>>> sum(1, 100, { x -> x * x * x } )
25502500

```

此外，末尾的括号闭合混乱了一点，因此 Kotlin 有一个很好的约定：如果函数调用中的最后一个参数是函数文字，则可以在函数调用的括号之后写它：

```
>>> sum(1, 100) { x -> x } 
5050
>>> sum(1, 100) { x -> x * x * x } 
25502500

```

最后，另一个常规经常简化代码：当函数文字只有一个参数时，我们可以省略参数和右箭头，并在函数文字中使用魔术名称 it 作为参数：（[higher3.kts](https://github.com/otfried/cs109-kotlin/raw/master/tutorial/40-lambda/higher3.kts)）：

```
>>> sum(1, 100) { it }
5050
>>> sum(1, 100) { it * it * it }
25502500

```

像 sum 这样的函数被称为高阶函数，因为它们接受另一个函数对象作为参数：高阶函数是一个作用于其他函数的“元函数”。

高阶函数使我们能够自然地表达一个函数是问题输入的一部分的想法，例如：

+   打印给定函数的函数值表（参见[table.kts](https://github.com/otfried/cs109-kotlin/raw/master/tutorial/40-lambda/table.kts)）。

+   对函数进行数值积分（参见[table.kts](https://github.com/otfried/cs109-kotlin/raw/master/tutorial/40-lambda/integrate.kts)）。

+   寻找函数的不动点。
