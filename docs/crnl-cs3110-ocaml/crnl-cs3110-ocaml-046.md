# 046：高阶函数 🧠

在本节课中，我们将要学习OCaml中一个核心且强大的概念：高阶函数。我们将探讨函数如何像其他数据一样被传递和返回，并通过具体例子理解其应用。

---

![](img/f647ba869b3da0bbdaadb49b55e6c69d_1.png)

我们已经在OCaml的数据和类型上花费了不少时间。现在，让我们回到函数的概念上，甚至可以将函数本身视为一种数据。

我们之前提到过，函数是值，我们可以在任何使用值的地方使用它们。这意味着函数可以作为参数传递给其他函数，也可以作为其他函数的结果被返回。在OCaml中，这种特性使得函数成为“高阶”的。所谓“高阶”，就是指函数可以像其他类型的值一样被传递和使用。

让我们从编写几个函数开始。

```ocaml
let double x = 2 * x
```
`double`函数将其参数加倍。

```ocaml
let square x = x * x
```
`square`函数计算其参数的平方。

如果我们想将一个数字翻四倍（quadruple）呢？一种写法是：
```ocaml
let quad x = 4 * x
```
但我们也可以用另一种方式编写，即使用两次`double`函数：
```ocaml
let quad_prime x = double (double x)
```
我们之前学过管道运算符（`|>`），也可以用它来写`quad`：
```ocaml
let quad_double_prime x = x |> double |> double
```
以上是编写`quad`函数的几种不同方式。

现在，假设我们想计算一个数字的四次方（fourth power）。我们可以这样写：
```ocaml
let fourth x = x * x * x * x
```
这与`quad`的写法有些类似。我们也可以用类似重写`quad`的方式来重写它：
```ocaml
let fourth_prime x = square (square x)
```
或者使用管道运算符：
```ocaml
let fourth_double_prime x = x |> square |> square
```
这为我们提供了编写同一函数的多种方式。

---

这些函数本身可能并不那么有趣，但让我们看看在构建`quad`和`fourth`时的相似之处。为了构建`quad`，我们应用了两次`double`函数。为了构建`fourth`，我们应用了两次`square`函数。这里存在一个“应用函数两次”的概念。

在代码中，每当你注意到这种重复的操作时，一个好的问题是：我能否将其抽象出来？能否将这个功能提取出来，使其成为独立的代码片段，从而避免重复编写？

因此，让我们编写一个函数，它能够将另一个函数应用两次。

```ocaml
let twice f x = f (f x)
```
`twice`函数接受一个函数`f`和一个参数`x`，然后将`f`应用到这个参数上两次。

让我们看看这个函数的类型。`twice`接受一个类型为`'a -> 'a`的函数（即输入和输出类型相同），然后接受一个该输入类型的值，并返回一个相同类型的值。

现在，我可以使用`twice`来重新编写之前的一些函数。例如：
```ocaml
let quad_triple_prime x = twice double x
```
这里，我取`double`函数，并将其对`x`应用两次。这就是高阶函数的应用：我们实际上在使用`twice`这个函数，它接受另一个函数作为参数。

我可以用同样的方式处理`fourth`：
```ocaml
let fourth_triple_prime x = twice square x
```
当然，我也可以使用管道运算符来编写`twice`：
```ocaml
let twice_pipe f x = x |> f |> f
```
这同样有效。

---

我还可以为`quad`和`fourth`做另一件事：省略参数。

我可以将`quad`重写为：
```ocaml
let quad_four_primes = twice double
```
注意，这里的`quad_four_primes`没有接收参数。它等于`twice double`。那么`twice double`是什么呢？从上面`twice`的类型可以看出，它接受一个函数和一个参数，并返回一个输出。但如果我们只将`twice`应用于它的第一个参数（函数`f`），就像这里的`twice double`，那么它返回的是一个函数。具体来说，是一个类型为`'a -> 'a`的函数（在这里，由于`double`是基于整数定义的，所以是`int -> int`类型）。

这再次体现了高阶性。这里的`twice`是一个高阶函数，因为当我们只给它第一个输入（函数）时，它返回一个函数作为输出。我们之前在部分应用（partial application）中见过这种特性。

我同样可以对`fourth`做类似处理：
```ocaml
let fourth_four_primes = twice square
```

---

我们之所以详细查看了所有这些不同的写法，是为了深入理解“高阶”的含义。它意味着我们可以像使用语言中其他类型的值一样使用函数：将它们传递给其他函数，甚至将函数作为结果返回。

![](img/f647ba869b3da0bbdaadb49b55e6c69d_3.png)

本节课中我们一起学习了高阶函数的概念，包括如何定义接受函数作为参数的函数，以及如何通过部分应用返回新的函数。这是函数式编程中实现代码抽象和复用的强大工具。