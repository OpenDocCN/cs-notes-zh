# 091：等价结构 🏗️

在本节课中，我们将学习抽象、签名和抽象类型的重要性，并通过展示与之前有理数结构具有相同签名的其他结构来加深理解。

## 概述

抽象、签名和抽象数据类型的一个核心目的是，允许同一功能的不同实现是等价的。所谓“等价”，是指任何客户端都无法区分你正在使用的是哪一个实现。如果能通过抽象保证客户端无法区分，那么你就可以用一个实现替换另一个。新实现可能添加了不改变旧功能的新功能，可能速度更快，或者你只是希望将选择哪个实现的决定推迟到以后，并保证在更改时客户端不会出错。

## 签名与等价性

上一节我们介绍了抽象和签名的概念，本节中我们来看看如何通过不同的结构实现等价性。

更容易实现的是，两个结构在揭示信息较少的签名下比在揭示信息较多的签名下更可能是等价的。我将通过两个例子来说明这一点，本段展示第一个例子，下一个例子将在后续课程中介绍。

本段将展示一个结构，它像我们之前的有理数结构一样，可以拥有我们之前见过的所有三种签名（Rational A、Rational B 或 Rational C）。在 Rational B 或 Rational C 签名下，它将与之前的结构等价；但在 Rational A 签名下，它不会等价。

## 新结构：`rational2`

让我说明这个结构有何不同。这是一个使用有理数的有趣例子，我稍后会展示代码。

`struct rational2` 与 `struct rational1` 的不同之处在于，它**不**将有理数保持为最简形式。它允许分子和分母是像 9 和 6 这样的值，但 `toString` 函数在返回字符串之前总是会进行约分。

以下是 `rational2` 的代码：

![](img/951d8855a259ba496e3930c6091829ae_1.png)

```sml
structure Rational2 =
struct
  exception BadFrac
  datatype rational = Whole of int | Frac of int * int

  fun make_frac (x, y) =
      if y = 0
      then raise BadFrac
      else Frac (x, y)

  fun add (Whole i, Whole j) = Whole (i + j)
    | add (Whole i, Frac (j, k)) = Frac (j + i*k, k)
    | add (Frac (j, k), Whole i) = Frac (j + i*k, k)
    | add (Frac (a, b), Frac (c, d)) = Frac (a*d + b*c, b*d)

  fun toString (Whole i) = Int.toString i
    | toString (Frac (x, y)) =
        let
          fun gcd (x, y) =
              if x = y
              then x
              else if x < y
              then gcd (x, y-x)
              else gcd (y, x)
          fun reduce (Frac (x, y)) =
              let val d = gcd (abs x, abs y)
              in Frac (x div d, y div d) end
        in
          case reduce (Frac (x, y)) of
              Whole i => Int.toString i
            | Frac (x, y) => (Int.toString x) ^ "/" ^ (Int.toString y)
        end
end
```

关键点在于：
*   `make_frac` 和 `add` 函数**不**进行约分。例如，`make_frac(4, 2)` 返回 `Frac(4, 2)`；`add(Frac(2,3), Frac(1,3))` 返回 `Frac(9, 9)`。
*   `toString` 是**唯一**使用 `gcd` 和 `reduce` 辅助函数进行约分的函数。它在将有理数转换为字符串之前，先将其约分为最简形式。

根据我们的规范属性，这个实现仍然是正确的：它不允许分母为零，并且返回的字符串总是最简形式。

## 签名兼容性

这个新结构可以兼容我们之前见过的所有三种签名。

以下是三种签名的定义：

```sml
(* 签名 RationalA *)
signature RATIONAL_A =
sig
  datatype rational = Whole of int | Frac of int * int
  exception BadFrac
  val make_frac : int * int -> rational
  val add : rational * rational -> rational
  val toString : rational -> string
end

(* 签名 RationalB *)
signature RATIONAL_B =
sig
  type rational (* 抽象类型 *)
  exception BadFrac
  val make_frac : int * int -> rational
  val add : rational * rational -> rational
  val toString : rational -> string
end

(* 签名 RationalC *)
signature RATIONAL_C =
sig
  type rational (* 抽象类型 *)
  exception BadFrac
  val whole : int -> rational
  val make_frac : int * int -> rational
  val add : rational * rational -> rational
  val toString : rational -> string
end
```

`Rational2` 结构可以提供所有这些签名中要求的正确类型的值。对于 `RationalB` 和 `RationalC`，类型 `rational` 是抽象的。

## 等价性分析

现在，让我们思考一个关键问题：如果有一个程序正在使用 `Rational1`，而我进入该程序，将所有对 `Rational1` 的使用替换为 `Rational2`，程序的行为会有所不同吗？

答案取决于我们给这些结构赋予哪个签名。

**情况一：使用签名 `RationalA`**

如果两个结构都使用签名 `RationalA`，那么客户端的行为**可能不同**。

![](img/951d8855a259ba496e3930c6091829ae_3.png)

这是因为 `RationalA` 允许过多操作，它允许客户端直接使用 `Frac` 构造函数构建自己的分数。考虑以下客户端代码：

```sml
Rational1.toString (Rational1.Frac (9, 6))
```

*   对于 `Rational1`（内部保持最简形式），直接返回 `"9/6"`（因为它不重新约分）。
*   对于 `Rational2`，`toString` 会先约分 `Frac(9,6)` 为 `Frac(3,2)`，然后返回 `"3/2"`。

由于两个模块对相同的参数给出了不同的答案，它们**不是等价的**。在替换时需要非常小心。

**情况二：使用签名 `RationalB` 或 `RationalC`**

如果使用签名 `RationalB` 或 `RationalC`，那么**没有**任何对模块的使用会导致两个模块产生不同的结果。

这基本上源于 `rational` 类型是抽象的。给定类型是抽象的，两个模块都强制执行相同的属性（例如，通过 `make_frac` 创建，不允许零分母），并且对于相同的参数总是返回相同的结果（因为客户端只能通过 `make_frac` 和 `add` 创建有理数，而这些操作的结果在 `toString` 时都会被约分）。

因此，当你暴露的信息更少（特别是使类型抽象）时，用一个模块替换另一个模块变得更容易。我们现在已经看到了一个这样的例子。

## 一个重要注意事项

作为最后一点，你可能会想，在 `Rational2` 下，是否可以直接暴露 `Frac` 构造函数，因为 `toString` 会将事物约分为最简形式？答案是**不可以**。

这仍然会允许负分母或零分母，因此，如果你暴露 `Frac` 构造函数，`Rational2` 对于大多数 `Rational1` 不正确的原因来说，也是不正确的。`Rational2` 只是由于其实现方式的偶然性，现在碰巧正确处理了其中的几个原因（例如，`toString` 输出总是最简的），但根本性的抽象违规问题依然存在。

## 总结

![](img/951d8855a259ba496e3930c6091829ae_5.png)

本节课中我们一起学习了：
1.  **抽象的目的**：允许功能的不同实现在客户端看来是等价的，从而实现灵活替换、性能优化或延迟决策。
2.  **`Rational2` 结构**：一个不内部保持最简形式，仅在 `toString` 时约分的有理数实现。
3.  **签名的影响**：在暴露具体类型的签名（如 `RationalA`）下，不同实现可能不等价；而在使用抽象类型的签名（如 `RationalB`/`RationalC`）下，可以保证实现的等价性，使替换更加安全可靠。
4.  **核心结论**：通过使用抽象类型和限制性更强的签名，我们可以隐藏实现细节，从而更容易地创建可互换的模块，这是构建健壮、可维护软件系统的关键。