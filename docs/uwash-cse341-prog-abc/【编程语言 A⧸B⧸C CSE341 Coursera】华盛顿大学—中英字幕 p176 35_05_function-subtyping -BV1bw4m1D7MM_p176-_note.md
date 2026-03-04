# 编程语言 A/B/C CSE341 Coursera：35：函数子类型化 🧩

在本节课中，我们将要学习函数子类型化。这是整个课程中最反直觉的概念之一，但也是学习编程语言课程的核心内容。我们将探讨函数类型之间何时存在子类型关系，这对于理解高阶函数和面向对象编程中的方法重写至关重要。

![](img/2b8765943879e8c7a91399fce3bb5b8a_1.png)

## 函数子类型化概述

上一节我们介绍了记录（Record）的子类型化。本节中我们来看看函数类型的子类型化。首先，我们需要明确一个前提：当调用一个函数时，你可以传递一个该函数期望参数类型的子类型。同样，当函数返回一个结果时，你可以将该结果视为其父类型。这是常规的子类型化，与函数调用本身无关。

更有趣的问题是：**一个函数类型本身何时是另一个函数类型的子类型？** 这在拥有高阶函数的语言中非常重要。假设一个函数的参数本身也是一个函数，其类型为 `T1 -> T2`（使用ML语法，表示接受 `T1` 类型参数并返回 `T2` 类型结果）。我们能否传递一个 `T3 -> T4` 类型的函数作为参数？在什么情况下可以？显然，`T1 -> T2` 和 `T3 -> T4` 必须以某种方式相关联。我们将尝试找出这种关系。

这不仅对高阶函数语言的子类型化很重要，也直接关系到面向对象语言中的方法重写子类型化。我们先从函数入手来理解，这样会更容易一些。

## 示例：高阶函数 `dist_moved`

为了理解函数子类型化，我们从一个不涉及子类型化的高阶函数示例开始。这个函数叫做 `dist_moved`。

```ml
(* dist_moved 的类型: ( {x:real, y:real} -> {x:real, y:real} ) -> {x:real, y:real} -> real *)
fun dist_moved f p =
    let val new_point = f p
        val dx = #x new_point - #x p
        val dy = #y new_point - #y p
    in Math.sqrt(dx*dx + dy*dy)
    end
```

![](img/2b8765943879e8c7a91399fce3bb5b8a_3.png)

`dist_moved` 函数接受一个函数 `f` 和一个点 `p`。它用点 `p` 调用函数 `f`，然后计算点 `p` 与 `f(p)` 之间的距离并返回。

*   `f` 的类型是 `{x:real, y:real} -> {x:real, y:real}`，即接受一个点并返回一个点。
*   `p` 是一个点 `{x:real, y:real}`。

以下是一个完全正常的调用：

```ml
(* flip 函数：将点的 x 和 y 坐标取反 *)
fun flip p = {x = ~(#x p), y = ~(#y p)}
(* flip 的类型: {x:real, y:real} -> {x:real, y:real} *)

val d = dist_moved flip {x=3.0, y=4.0}
```

这里没有子类型化，因为 `flip` 的类型与 `dist_moved` 期望的 `f` 的类型完全一致。

![](img/2b8765943879e8c7a91399fce3bb5b8a_5.png)

## 返回类型的协变（Covariance）

现在，让我们考虑一个不同的调用。`dist_moved` 的定义不变，但我们想传入一个名为 `flip_green` 的函数。

```ml
(* flip_green 函数：翻转坐标并添加颜色字段 *)
fun flip_green p = {x = ~(#x p), y = ~(#y p), color = "green"}
(* flip_green 的类型: {x:real, y:real} -> {x:real, y:real, color:string} *)
```

`flip_green` 的返回类型是 `{x:real, y:real, color:string}`，它比 `dist_moved` 期望的返回类型 `{x:real, y:real}` 多了一个 `color` 字段。

`dist_moved` 并不期望这个确切的类型。然而，如果我们引入这样一条子类型化规则：**如果 `T2` 是 `T4` 的子类型，那么 `T1 -> T2` 是 `T1 -> T4` 的子类型**，那么调用就是合法的。换句话说，我们允许在函数的返回类型中进行子类型化。

**一个函数被允许返回比所需更多（即包含额外字段）的结果。** 这在术语上称为函数类型在其返回类型上是 **协变的（covariant）**。协变意味着子类型化的方向相同：如果 `T2 <: T4`，那么 `(T1 -> T2) <: (T1 -> T4)`。

因此，`flip_green` 的类型 `{x:real, y:real} -> {x:real, y:real, color:string}` 是 `dist_moved` 所期望的类型 `{x:real, y:real} -> {x:real, y:real}` 的子类型。这个调用是安全的，因为 `dist_moved` 只使用返回结果的 `x` 和 `y` 字段，而 `flip_green` 返回的记录恰好包含这些字段（并且更多）。

## 参数类型的逆变（Contravariance）

那么参数类型呢？考虑另一个我们试图传递给 `dist_moved` 的函数 `flip_if_green`。

```ml
(* flip_if_green 函数：仅当点为绿色时才翻转 *)
fun flip_if_green p =
    if #color p = "green"
    then {x = ~(#x p), y = ~(#y p)}
    else {x = #x p, y = #y p}
(* flip_if_green 的类型: {x:real, y:real, color:string} -> {x:real, y:real} *)
```

`flip_if_green` 的参数类型是 `{x:real, y:real, color:string}`，它要求参数具有所有三个字段。然而，在 `dist_moved` 中，我们传递给 `f` 的参数 `p` 并没有 `color` 字段。

```ml
(* 这将导致运行时错误！尝试读取不存在的 color 字段 *)
val d_bad = dist_moved flip_if_green {x=3.0, y=4.0} (* 类型检查应失败 *)
```

如果你尝试运行这段程序，它是不健全的（unsound）。它会尝试读取一个没有 `color` 字段的记录的 `color` 字段。因此，我们必须确保这样的代码**不能**通过类型检查。

所以，**我们不能仅仅因为 `T3` 是 `T1` 的子类型，就允许 `T3 -> T2` 是 `T1 -> T2` 的子类型**。我们不能说“假设这个函数不需要所有字段也没关系”。它确实需要所有字段（或者可能需要）。因此，**不能从函数的参数中删除字段**。我们不应该有这样的类型检查规则。

但令人惊讶的是，**反过来是允许的**。只要子类型化的方向是相反的，就允许在函数参数类型上进行子类型化。

规则如下：**如果 `T3` 是 `T1` 的子类型（`T3 <: T1`），那么 `T1 -> T2` 是 `T3 -> T2` 的子类型（`(T1 -> T2) <: (T3 -> T2)`）**。注意这里的方向是翻转的：参数类型的子类型关系与函数类型的子类型关系方向相反。

这在术语上称为 **逆变（contravariance）**。它意味着：**一个函数可以对其参数做出比所需更少的假设**（即，它可以接受一个更“宽泛”、要求更少的参数类型）。

示例：

```ml
(* flip_x_y0 函数：只使用 x 坐标，y 坐标固定为0 *)
fun flip_x_y0 p = {x = ~(#x p), y = 0.0}
(* flip_x_y0 的类型: {x:real} -> {x:real, y:real} *)
```

`flip_x_y0` 的参数类型是 `{x:real}`，它不要求参数有 `y` 字段。我们可以将它传递给 `dist_moved`，因为 `dist_moved` 期望的函数类型是 `{x:real, y:real} -> {x:real, y:real}`。

这里，`{x:real, y:real}` 是 `{x:real}` 的子类型（因为前者拥有后者所有字段且更多）。根据逆变规则，`({x:real} -> {x:real, y:real})` 是 `({x:real, y:real} -> {x:real, y:real})` 的子类型。因此，调用是安全的：`dist_moved` 会传递一个具有 `x` 和 `y` 字段的点给 `flip_x_y0`，而 `flip_x_y0` 只使用 `x` 字段，这完全没问题。

## 结合协变与逆变

我们可以同时应用这两种思想。以下是最终示例：

```ml
(* flip_x_make_green 函数：只使用 x 坐标，返回带颜色的点 *)
fun flip_x_make_green p = {x = ~(#x p), y = 0.0, color = "green"}
(* flip_x_make_green 的类型: {x:real} -> {x:real, y:real, color:string} *)
```

![](img/2b8765943879e8c7a91399fce3bb5b8a_7.png)

`flip_x_make_green` 只要求其参数具有 `x` 字段，但返回一个具有 `x`、`y` 和 `color` 字段的记录。我们可以将它传递给 `dist_moved`：

```ml
val d_final = dist_moved flip_x_make_green {x=3.0, y=4.0} (* 类型检查通过，运行安全 *)
```

`dist_moved` 期望的类型是 `{x:real, y:real} -> {x:real, y:real}`。
`flip_x_make_green` 的类型是 `{x:real} -> {x:real, y:real, color:string}`。

根据函数子类型化的完整规则，这是成立的：
1.  **参数逆变**：`{x:real, y:real} <: {x:real}` （`T3 <: T1`）
2.  **返回协变**：`{x:real, y:real, color:string} <: {x:real, y:real}` （`T2 <: T4`）

因此，`({x:real} -> {x:real, y:real, color:string}) <: ({x:real, y:real} -> {x:real, y:real})`，调用是安全的。

## 函数子类型化的完整规则

综合以上，函数子类型化的通用规则是：

**如果 `T3` 是 `T1` 的子类型（`T3 <: T1`），并且 `T2` 是 `T4` 的子类型（`T2 <: T4`），那么 `T1 -> T2` 是 `T3 -> T4` 的子类型（`(T1 -> T2) <: (T3 -> T4)`）。**

用更专业的术语来说：**函数子类型化在其参数上是逆变的，在其返回结果上是协变的**。

理解这一点对于理解面向对象编程中的子类型化和方法重写的安全性至关重要，我们将在下一节中看到。

## 总结与强调

本节课中我们一起学习了函数子类型化。这是本课程中最反直觉的概念。当你感到困惑时，可以回顾并研究这些示例，或者创建自己的示例，以确信参数必须是逆变的，否则会破坏类型系统的健全性。

许多聪明人都曾在这个问题上犯过错。我想强调这一点：在你职业生涯的某个时刻，你、你的上司或你的朋友都可能犯这个错误。因此，我希望你至少记住这里有一些“反常”的规则。你可以随时回看这段视频。

![](img/2b8765943879e8c7a91399fce3bb5b8a_9.png)

最后，记住这个核心结论：**函数（和方法）的子类型化在参数上必须是逆变的，这不是你直观上认为的方向**。掌握这一点是理解高级类型系统的关键一步。