# OCaml编程：3.14：变体类型与模式匹配（第一部分）🎯

在本节课中，我们将学习如何使用模式匹配来处理变体类型。我们将通过一个计算几何图形中心点的例子，来理解如何根据不同的变体构造器执行不同的代码逻辑。

---

## 概述

假设我们有一个表示几何图形的变体类型 `shape`，它可以是圆形或矩形。我们的目标是编写一个函数，根据传入的图形类型，计算并返回其中心点坐标。

## 变体类型定义

首先，我们定义 `shape` 类型。它使用两个构造器：`Circle` 和 `Rectangle`。

```ocaml
type point = float * float
type shape =
  | Circle of point * float
  | Rectangle of point * point
```

*   `Circle` 构造器接受一个点（圆心）和一个浮点数（半径）。
*   `Rectangle` 构造器接受两个点（左下角和右上角）。

## 编写中心点计算函数

现在，我们开始编写 `center` 函数。其类型签名为 `shape -> point`。

```ocaml
let center s =
  match s with
  | Circle (center_point, _) -> center_point
  | Rectangle (lower_left, upper_right) ->
      (* 计算矩形中心点的逻辑将放在这里 *)
      failwith "to do"
```

函数的核心是 `match` 表达式。它检查输入 `s` 是 `Circle` 还是 `Rectangle`。

*   如果匹配到 `Circle`，我们直接提取并返回其自带的 `center_point`。
*   如果匹配到 `Rectangle`，我们提取其两个角点 `lower_left` 和 `upper_right`。目前我们先用 `failwith "to do"` 占位，以保证代码能编译。

## 完善矩形中心点计算

上一节我们介绍了函数的基本结构，本节中我们来看看如何计算矩形的中心点。矩形的中心是其对角线的中点，即两个角点坐标的平均值。

首先，我们编写一个辅助函数来计算两个数的平均值。

```ocaml
let avg a b = (a +. b) /. 2.
```

接下来，在 `Rectangle` 分支中，我们需要从两个点中提取坐标，并计算平均值。

以下是计算矩形中心点的完整步骤：
1.  使用模式匹配从 `lower_left` 点提取 `x_ll` 和 `y_ll` 坐标。
2.  使用模式匹配从 `upper_right` 点提取 `x_ur` 和 `y_ur` 坐标。
3.  计算X坐标的平均值 `avg x_ll x_ur`。
4.  计算Y坐标的平均值 `avg y_ll y_ur`。
5.  返回由这两个平均值构成的新点 `(x_avg, y_avg)`。

```ocaml
let center s =
  match s with
  | Circle (center_point, _) -> center_point
  | Rectangle (lower_left, upper_right) ->
      let (x_ll, y_ll) = lower_left in
      let (x_ur, y_ur) = upper_right in
      let x_avg = avg x_ll x_ur in
      let y_avg = avg y_ll y_ur in
      (x_avg, y_avg)
```

**注意**：在模式匹配元组时，虽然可以省略括号，但根据 OCaml 社区的风格指南，建议保留括号以使代码更清晰。

## 测试函数

让我们在交互式环境（utop）中测试这个函数。

```ocaml
(* 定义图形 *)
let my_circle = Circle ((0., 0.), 5.)
let my_rect = Rectangle ((-1., -1.), (1., 1.))

(* 计算中心点 *)
center my_circle (* 应返回 (0., 0.) *)
center my_rect   (* 应返回 (0., 0.) *)
```

测试结果符合预期：圆心在原点，矩形的中心点也在原点。

---

![](img/3e24cc62ff121727c50aa85613ecb348_1.png)

## 总结

![](img/3e24cc62ff121727c50aa85613ecb348_3.png)

本节课中我们一起学习了变体类型模式匹配的核心应用。
1.  我们使用 `match` 表达式根据变体构造器（`Circle` 或 `Rectangle`）进行分支判断。
2.  在匹配分支中，我们可以直接解构出构造器所携带的数据（如点的坐标、半径）。
3.  我们通过编写辅助函数和逐步计算，完成了矩形中心点的逻辑。
4.  模式匹配是处理变体类型、列表、元组等复合数据结构的强大且安全的工具，它能确保所有可能的情况都被考虑。