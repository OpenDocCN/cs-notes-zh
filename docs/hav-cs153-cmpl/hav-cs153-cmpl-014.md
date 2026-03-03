# 014：函数编译入门 🚀

![](img/26373566c56bdb122c6b2b539a054056_1.png)

在本节课中，我们将要学习如何为函数式编程语言实现编译。我们将从理解函数作为“一等公民”的语义开始，逐步深入到如何将这些概念转化为高效的编译策略。

## 概述 📋

函数式编程语言的核心特性之一是函数可以作为值来传递和返回。为了理解如何编译这样的语言，我们首先需要明确其运行时语义。我们将从两种不同的语义描述方法入手：**替换语义**和**环境语义**。理解这些语义是后续实现编译器的关键基础。

## 从替换语义到环境语义 🔄

上一节我们介绍了函数式编程的基本概念。本节中我们来看看如何精确地描述其执行过程。

### 替换语义

替换语义是一种直观但低效的语义描述方式。其核心思想是：当应用一个函数时，我们将函数体中的形式参数替换为实际参数值，然后对替换后的表达式求值。

例如，对于函数 `fun x -> x + 1` 应用于参数 `5`，我们先将函数体 `x + 1` 中的 `x` 替换为 `5`，得到 `5 + 1`，然后求值得 `6`。

在代码中，这体现为一个递归的求值函数和一个替换函数。

```ocaml
(* 简化的求值函数 *)
let rec eval (e : expr) : value =
  match e with
  | Int i -> Int i
  | Add (e1, e2) ->
      let Int i1 = eval e1 in
      let Int i2 = eval e2 in
      Int (i1 + i2)
  | Lambda (x, e_body) -> Lambda (x, e_body) (* 函数本身即是值 *)
  | Var x -> error "Unbound variable"
  | App (e1, e2) ->
      let Lambda (x, e_body) = eval e1 in
      let v = eval e2 in
      eval (subst v x e_body) (* 关键步骤：替换后求值 *)

(* 替换函数 *)
let rec subst (v : value) (x : string) (e : expr) : expr =
  match e with
  | Int i -> Int i
  | Add (e1, e2) -> Add (subst v x e1, subst v x e2)
  | Var y -> if y = x then v else Var y
  | App (e1, e2) -> App (subst v x e1, subst v x e2)
  | Lambda (y, e_body) ->
      if y = x then Lambda (y, e_body) (* 避免捕获 *)
      else Lambda (y, subst v x e_body)
```

替换语义的问题在于效率低下。每次函数应用都需要遍历整个函数体进行替换，然后再次遍历进行求值。

### 环境语义与闭包

为了解决效率问题，我们引入**环境语义**。环境（`environment`）是一个从变量名到值（`value`）的映射。在求值时，我们携带当前环境，遇到变量时直接从环境中查找其值，而无需进行替换。

![](img/26373566c56bdb122c6b2b539a054056_3.png)

![](img/26373566c56bdb122c6b2b539a054056_4.png)

![](img/26373566c56bdb122c6b2b539a054056_6.png)

对于嵌套函数，关键挑战在于如何处理函数体内引用的、定义在其外部作用域中的变量（自由变量）。解决方案是**闭包**。

**闭包**是一个包含函数定义和其创建时环境的对（`pair`）。它“闭合”了函数，为其所有自由变量提供了绑定。

以下是使用闭包的环境语义求值函数：

```ocaml
type value =
  | VInt of int
  | VClosure of env * string * expr (* 环境，形参，函数体 *)

and env = (string * value) list

let rec eval_env (env : env) (e : expr) : value =
  match e with
  | Int i -> VInt i
  | Var x -> List.assoc x env (* 从环境中查找 *)
  | Add (e1, e2) ->
      let VInt i1 = eval_env env e1 in
      let VInt i2 = eval_env env e2 in
      VInt (i1 + i2)
  | Lambda (x, e_body) -> VClosure (env, x, e_body) (* 创建闭包！ *)
  | App (e1, e2) ->
      let VClosure (closure_env, x, e_body) = eval_env env e1 in
      let v_arg = eval_env env e2 in
      (* 在闭包环境（包含自由变量绑定）的基础上，添加形实参绑定，求值函数体 *)
      eval_env ((x, v_arg) :: closure_env) e_body
```

通过使用环境和闭包，我们将替换操作延迟并分散到了变量查找中，避免了低效的全局替换。

## 从语义到编译 🛠️

理解了函数在运行时的行为（通过闭包和环境）后，我们就可以设计编译策略了。核心思想是将高级的语义概念转化为低级的运行时数据结构与代码。

### 闭包转换与 Lambda 提升

编译函数式语言的两个关键步骤是**闭包转换**和**Lambda 提升**。

1.  **闭包转换**：将每个函数值显式地表示为一个闭包结构。在类 C 的语言中，这通常是一个包含**函数指针**和**环境指针**的结构体。
2.  **Lambda 提升**：将所有嵌套函数“提升”为顶级函数。因为这些函数现在通过显式传递的环境参数来访问自由变量，它们不再需要嵌套在语法上。

以下是一个转换示例：

原始代码（类 OCaml）：
```ocaml
let add = fun x -> fun y -> y + x in
let inc = add 1 in
inc 5
```

转换后（类 C）：
```c
// 被提升的内部函数，显式接收环境参数
int f_inner(Env* env, int y) {
    int x = lookup(env, "x"); // 从环境中查找自由变量 x
    return y + x;
}

// 外部函数，也接收环境参数，返回一个闭包
Closure* f_outer(Env* env, int x) {
    Env* new_env = extend_env(env, "x", x); // 扩展环境，绑定 x
    // 创建闭包：包含函数指针 f_inner 和环境 new_env
    Closure* clo = malloc(sizeof(Closure));
    clo->code = &f_inner;
    clo->env = new_env;
    return clo;
}

// 主函数
int main() {
    Closure* inc = f_outer(empty_env, 1); // 部分应用，得到闭包
    int result = apply(inc, 5); // 应用闭包：调用 clo->code(clo->env, 5)
    return result;
}
```

### 环境表示与内存管理

环境需要动态扩展（当进入函数时）并且其生命周期可能比创建它的函数调用更长（闭包可能被返回并在其他地方使用）。因此，环境通常需要在**堆**上分配内存，而不是栈上。

这引出了一个有趣的类比：**闭包和对象**在本质上非常相似。一个对象可以看作是一个记录字段值（环境）和方法指针（函数指针）的结构体。两者在表达力上是等价的，编译技术也相互借鉴。

## 总结 🎯

本节课中我们一起学习了函数式语言编译的基础。

*   我们从**替换语义**出发，理解了函数应用的基本原理，但认识到其效率缺陷。
*   我们引入了**环境语义**和**闭包**的概念，这是一种更高效的运行时模型，通过将变量绑定存储在环境中并在使用时查找，避免了昂贵的复制操作。
*   最后，我们探讨了如何基于闭包模型进行编译，即**闭包转换**（将函数表示为显式的代码与环境对）和**Lambda 提升**（将嵌套函数转为顶级函数，通过参数显式传递环境）。我们还注意到环境需要在堆上管理，并且闭包与面向对象中的对象有深刻的联系。

![](img/26373566c56bdb122c6b2b539a054056_8.png)

![](img/26373566c56bdb122c6b2b539a054056_9.png)

下一讲中，我们将更深入地探讨函数编译的细节，特别是环境的具体实现和优化技术。