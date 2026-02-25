# 2：反思活动与OCaml自定义类型 🧠

![](img/8988002a35f2508a39599753650b3add_0.png)

在本节课中，我们将首先反思学习编程语言和编译器的个人动机，然后深入探索OCaml编程语言，特别是其强大的模式匹配功能和自定义类型系统。我们将通过一系列实践活动来巩固这些概念。

## 课程概述与反思活动 🤔

上一节我们初步接触了OCaml。本节中，我们首先将花时间思考一个核心问题：我们为何在此学习编程语言与编译器？理解个人动机有助于将课程内容与长远目标联系起来。

编程语言和编译器不仅是计算机科学的基础，也是连接人类意图与机器执行的桥梁。掌握它们，意味着获得了设计和构建新工具的能力，从而让更多人能够利用计算解决实际问题。

现在，请花两分钟时间，静心思考以下问题，并简要记录你的想法：
*   编程语言和编译器的知识如何与你未来两年、五年甚至更长远的目标相关联？
*   你希望利用这些知识解决什么样的问题，或创造什么样的价值？

思考完毕后，请与你身边的同学进行简短交流。

---

## 回顾与深入：OCaml模式匹配 🔍

在上一节的活动中，我们学习了OCaml的`match`表达式和模式匹配。本节中，我们将通过一个具体的例子，来更深入地理解模式匹配的执行顺序和括号`()`在分组时的重要性。

请看以下代码片段，并预测A、B、C三处分别会输出什么：

![](img/8988002a35f2508a39599753650b3add_2.png)

```ocaml
let read_to_course prior current =
  match prior with
  | "CS61A" -> "ready"
  | _ -> match current with
         | "CS61B" -> "not sure"
         | _ -> "not sure about that either"
```

**预测：**
*   A. `read_to_course "CS61A" "CS160"` 输出：`"ready"`
*   B. `read_to_course "CS70" "CS61B"` 输出：`"not sure"`
*   C. `read_to_course "CS70" "CS160"` 输出：`"not sure about that either"`

然而，实际在OCaml中运行代码C时，却得到了`"not sure"`。这是为什么呢？

![](img/8988002a35f2508a39599753650b3add_4.png)

![](img/8988002a35f2508a39599753650b3add_6.png)

问题在于编译器的解析方式。对于编译器而言，代码的结构实际上是这样的：
```ocaml
let read_to_course prior current =
  match prior with
  | "CS61A" -> "ready"
  | _ -> match current with
         | "CS61B" -> "not sure"
  | _ -> "not sure about that either" (* 这个分支属于外层的match！ *)
```
第二个通配符 `_` 被错误地关联到了外层的`match prior with`，而不是内层的`match current with`。因此，当`prior`不是`"CS61A"`时，会直接匹配到第一个通配符`_`，其对应的分支是另一个`match`表达式，该表达式最终返回`"not sure"`。

![](img/8988002a35f2508a39599753650b3add_8.png)

**解决方案是使用括号`()`进行明确分组：**
```ocaml
let read_to_course prior current =
  match prior with
  | "CS61A" -> "ready"
  | _ -> (match current with
         | "CS61B" -> "not sure"
         | _ -> "not sure about that either")
```
现在，整个内层的`match`表达式被括号包裹，作为一个整体返回。此时再运行，A、B、C的输出就符合我们最初的预测了。

**核心要点：**
*   OCaml不依赖缩进来决定代码结构，它依赖语法符号（如括号、分号）。
*   当嵌套使用`match`时，使用括号`()`来明确表达式的分组范围是避免混淆的好习惯。
*   编译器会按顺序尝试匹配`match`中的每个分支，并使用第一个匹配成功的分支。

![](img/8988002a35f2508a39599753650b3add_10.png)

![](img/8988002a35f2508a39599753650b3add_12.png)

---

## 探索OCaml自定义类型 🏗️

理解了基础的模式匹配后，本节我们来看看OCaml一个非常强大的特性：自定义类型。这允许我们根据问题领域创建专属的数据结构。

![](img/8988002a35f2508a39599753650b3add_14.png)

![](img/8988002a35f2508a39599753650b3add_16.png)

![](img/8988002a35f2508a39599753650b3add_18.png)

### 定义简单枚举类型

![](img/8988002a35f2508a39599753650b3add_20.png)

首先，我们定义一个表示布料的简单类型：
```ocaml
type fabric = Linen | Cotton | Wool
```
*   `type` 是定义新类型的关键字。
*   `fabric` 是我们新类型的名称（惯例用小写字母开头）。
*   `Linen`、`Cotton`、`Wool` 是这个类型的**构造器**。它们代表了`fabric`类型可能的值，类似于其他语言中的枚举值。

![](img/8988002a35f2508a39599753650b3add_22.png)

![](img/8988002a35f2508a39599753650b3add_24.png)

我们可以编写一个函数，根据布料类型计算每码价格：
```ocaml
let cost_per_yard f =
  match f with
  | Linen -> 15
  | Cotton -> 6
  | Wool -> 18

![](img/8988002a35f2508a39599753650b3add_26.png)

![](img/8988002a35f2508a39599753650b3add_27.png)

let _ = cost_per_yard Linen (* 输出: 15 *)
let _ = cost_per_yard Cotton (* 输出: 6 *)
let _ = cost_per_yard Wool (* 输出: 18 *)
```
注意，函数`cost_per_yard`的参数`f`并没有显式标注类型（如`f: fabric`）。OCaml编译器非常智能，它通过观察`match`分支中匹配的构造器（`Linen`、`Cotton`、`Wool`），自动推断出`f`必须是`fabric`类型。

![](img/8988002a35f2508a39599753650b3add_29.png)

![](img/8988002a35f2508a39599753650b3add_31.png)

![](img/8988002a35f2508a39599753650b3add_33.png)

### 定义带有数据的构造器

![](img/8988002a35f2508a39599753650b3add_35.png)

构造器不仅可以标记类型，还可以携带额外的数据。例如，我们定义服装项目及其所需的布料码数：
```ocaml
type garment = Sample | MiniDress | MaxiDress | Suit of int * int

let yards_for g =
  match g with
  | Sample -> 1
  | MiniDress -> 4
  | MaxiDress -> 8
  | Suit (jacket_yards, pant_yards) -> jacket_yards + pant_yards

let _ = yards_for Sample (* 输出: 1 *)
let _ = yards_for (Suit (5, 4)) (* 输出: 9 *)
```
*   `Sample`、`MiniDress`、`MaxiDress` 是不带数据的构造器。
*   `Suit of int * int` 是一个带数据的构造器。它表示一个`Suit`值包含两个整数（夹克和裤子的码数）。`*`在这里用于组合类型，表示元组，而非乘法运算。

### 组合类型与完整示例

![](img/8988002a35f2508a39599753650b3add_37.png)

![](img/8988002a35f2508a39599753650b3add_39.png)

![](img/8988002a35f2508a39599753650b3add_40.png)

现在，我们将`fabric`和`garment`类型结合起来，计算制作一件服装的成本：
```ocaml
let total_cost (g: garment) (f: fabric) : int =
  (yards_for g) * (cost_per_yard f)

let summer_suit_cost = total_cost (Suit (5, 4)) Cotton (* 9码 * 6美元/码 = 54美元 *)
let winter_suit_cost = total_cost (Suit (6, 6)) Wool   (* 12码 * 18美元/码 = 216美元 *)
```

**关于模式匹配完备性的重要提示：**
当我们对一个自定义类型进行`match`时，OCaml会检查是否处理了该类型所有可能的构造器。如果处理了所有情况，编译器不会警告。例如，`match f with` 覆盖了`Linen`、`Cotton`、`Wool`，所以是完备的。
如果后续为`fabric`类型新增了构造器（如`Silk`），但未更新`match`表达式，编译器会发出“模式匹配不完整”的警告，提醒你可能遗漏了情况。这是一种强大的安全保障。

![](img/8988002a35f2508a39599753650b3add_42.png)

---

## 总结与核心收获 🎯

本节课中我们一起学习了以下内容：

1.  **学习动机反思**：我们探讨了学习编程语言和编译器如何与个人长期目标及社会价值产生联系，认识到这门技术是赋能他人、创造新工具的关键。
2.  **OCaml模式匹配的深入理解**：我们通过一个陷阱示例，认识到括号`()`在明确表达式分组、控制`match`结构时的重要性。OCaml编译器按顺序匹配分支，且不依赖缩进。
3.  **OCaml自定义类型**：我们学会了使用 **`type`** 关键字定义新类型，并了解了两种构造器：
    *   **简单构造器**：如`Linen`，用于创建枚举值。
    *   **带参数构造器**：如`Suit of int * int`，用于创建包含数据的复合值。
4.  **类型推断与安全保障**：OCaml能根据`match`中的构造器自动推断变量类型。同时，编译器会检查模式匹配的完备性，确保所有可能的情况都被处理，这大大增强了代码的健壮性。

![](img/8988002a35f2508a39599753650b3add_44.png)

通过定义贴合问题领域的类型，并利用模式匹配来解构它们，我们可以写出既安全又易于理解的OCaml代码。这是函数式编程范式的核心优势之一。