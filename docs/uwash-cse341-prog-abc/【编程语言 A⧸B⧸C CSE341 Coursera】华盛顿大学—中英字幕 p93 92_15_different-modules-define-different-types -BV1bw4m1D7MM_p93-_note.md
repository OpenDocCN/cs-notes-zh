# 模块系统：第15节：不同模块定义不同类型 🧩

在本节课中，我们将完成对模块系统的学习，重点澄清一个关于多个结构共享同一签名时的常见误解。

上一节我们探讨了签名和结构的基本关系。本节中，我们来看看当多个结构实现同一个包含抽象类型的签名时，会发生什么。

## 核心概念

多个结构可以实现同一个签名，即使该签名中包含抽象类型。然而，**每个结构的具体实现都会引入一个全新的、彼此不同的类型**。

## 代码示例与分析

以下是演示这一概念的代码。我们定义了三个结构（`Rational1`、`Rational2`、`Rational3`），它们都实现了同一个签名 `RATIONAL_C`。

![](img/406d449ff4f890abc90140c4ac48e91b_1.png)

```sml
(* 签名定义 *)
signature RATIONAL_C =
sig
  type rational
  val make_frac : int * int -> rational
  val to_string : rational -> string
end

![](img/406d449ff4f890abc90140c4ac48e91b_2.png)

(* 结构1：使用约分实现 *)
structure Rational1 : RATIONAL_C =
struct
  type rational = int * int
  fun make_frac (x, y) = ... (* 约分逻辑 *)
  fun to_string (x, y) = Int.toString x ^ "/" ^ Int.toString y
end

(* 结构2：不约分实现 *)
structure Rational2 : RATIONAL_C =
struct
  type rational = int * int
  fun make_frac (x, y) = (x, y) (* 不约分 *)
  fun to_string (x, y) = Int.toString x ^ "/" ^ Int.toString y
end

(* 结构3：可能使用不同内部表示 *)
structure Rational3 : RATIONAL_C =
struct
  datatype rational = Frac of int * int
  fun make_frac (x, y) = Frac (x, y)
  fun to_string (Frac (x, y)) = Int.toString x ^ "/" ^ Int.toString y
end
```

每个结构都可以独立使用，并正常工作：
```sml
Rational1.to_string (Rational1.make_frac (9, ~6)); (* 返回 "-3/2" *)
Rational3.to_string (Rational3.make_frac (9, ~6)); (* 返回 "-3/2" *)
```

## 关键限制：禁止混合使用

以下是核心限制，初学者务必理解：

**你不能在不同结构之间混合使用其值或函数。** 尝试这样做将无法通过类型检查。

例如，以下代码是错误的：
```sml
Rational3.to_string (Rational1.make_frac (9, ~6)); (* 类型错误！ *)
Rational1.to_string (Rational2.make_frac (9, ~6)); (* 类型错误！ *)
```

## 原因解析

为什么不允许混合使用？原因如下：

1.  **类型不同**：尽管签名相同，但每个结构定义的 `rational` 类型都是独立的抽象类型。例如：
    *   `Rational1.to_string` 的类型是 **`Rational1.rational -> string`**。
    *   `Rational2.to_string` 的类型是 **`Rational2.rational -> string`**。
    编译器视 `Rational1.rational` 和 `Rational2.rational` 为完全不同的类型，就像 `int` 和 `string` 不同一样。

2.  **维护抽象与不变性**：这是最重要的原因。每个结构可能维护着不同的内部不变性。例如，`Rational1` 保证分数总是约分的，而 `Rational2` 则不保证。如果允许将 `Rational2` 创建的未约分分数传给 `Rational1` 的函数，就可能破坏 `Rational1` 所依赖的内部假设，导致输出错误结果（如期望得到“-3/2”，却打印出“-9/6”）。

## 总结

本节课中我们一起学习了模块系统的一个关键特性：

*   多个结构（模块）可以实现同一个签名。
*   每个结构都会定义自己独有的抽象类型，即使它们签名相同。
*   **禁止在不同结构之间混合使用其值和函数**，这是类型系统强制执行的规则。
*   这一规则至关重要，它确保了：
    *   抽象边界不被破坏。
    *   每个库内部维护的不变性和属性得到遵守。
    *   类型安全得以保障，就像防止将整数误用作字符串一样。

![](img/406d449ff4f890abc90140c4ac48e91b_4.png)

理解这一点，对于构建可靠、模块化的ML程序至关重要。