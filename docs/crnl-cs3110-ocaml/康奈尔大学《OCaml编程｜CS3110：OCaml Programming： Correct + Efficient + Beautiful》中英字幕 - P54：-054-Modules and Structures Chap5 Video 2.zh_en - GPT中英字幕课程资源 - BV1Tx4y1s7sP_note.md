# OCaml编程：5.2：模块与结构体 🧩

在本节课中，我们将学习OCaml中的模块（Modules）和结构体（Structures）。它们是组织代码、创建层次化命名空间的重要工具，能有效解决命名冲突问题。

## 概述：命名冲突问题

上一节我们介绍了自定义类型和函数。本节中我们来看看当代码规模增长时可能遇到的一个常见问题：命名冲突。

结构体为我们在OCaml中提供了层次化的命名空间。让我们回顾一下上周看到的一些代码。

我们有一个列表类型和一个树类型，以及分别作用于它们的两个`map`函数。这次，我将这两个函数都命名为`map`。

```ocaml
type 'a mylist = Nil | Cons of 'a * 'a mylist
let rec map f = function
  | Nil -> Nil
  | Cons (h, t) -> Cons (f h, map f t)

type 'a tree = Leaf | Node of 'a tree * 'a * 'a tree
let rec map f = function
  | Leaf -> Leaf
  | Node (l, v, r) -> Node (map f l, f v, map f r)

let list = Cons (1, Cons (2, Cons (3, Nil)))
let result = map (fun x -> x + 1) list
```

当我尝试对`mylist`进行`map`操作时，这会产生一个问题。因为这里的`map`一词指向其最近的定义，即作用于树的`map`函数。它遮蔽了之前定义的用于列表的`map`函数。实际上，没有办法恢复那个早期的定义，除非我们使用结构体。

## 解决方案：使用模块和结构体

为了解决上述问题，让我们将`mylist`的定义封装在OCaml称为模块的结构中。

我们将该模块命名为`MyList`。它是一个以关键字`struct`开始，以关键字`end`结束的结构体。我将对`tree`做同样的事情，模块`Tree`也是一个结构体。

```ocaml
module MyList = struct
  type 'a mylist = Nil | Cons of 'a * 'a mylist
  let rec map f = function
    | Nil -> Nil
    | Cons (h, t) -> Cons (f h, map f t)
end

module Tree = struct
  type 'a tree = Leaf | Node of 'a tree * 'a * 'a tree
  let rec map f = function
    | Leaf -> Leaf
    | Node (l, v, r) -> Node (map f l, f v, map f r)
end
```

现在，`map`这个词是未绑定的，因为它不再像之前那样定义在顶层作用域中。相反，我现在必须说`MyList.map`来获取其`MyList`版本，这就是我在这里想要的。或者说`Tree.map`，这当然不是我想要的，它会返回我们之前看到的原始错误。

因此，我们创建了一个名为`MyList`的模块，并将其绑定到这个结构体。该结构体内部包含我们一直编写的所有代码。这基本上为我们提供了一种创建具有层次化名称的代码嵌套级别的方法。

## 结构体与类型名称

关于结构体和模块名称，一个可能令人惊讶的地方是，当涉及类型时，名称本身位于何处。

如果我们查看`list`的类型，可以看到它的类型是`int MyList.mylist`。`MyList`是我们在模块`MyList`内部定义的类型构造器。该类型构造器以类型变量`'a`为参数。因此，`list`的类型是`int MyList.mylist`。因为名称`mylist`定义在模块`MyList`内部，所以模块名加点号放在类型名前面。

模块名不会放在类型变量前面。可以把这个类型变量想象成传递给某种类型级别函数的参数。所以在这里，`int`被传递给了`MyList.mylist`。

我们也可以查看`tree`并看到相同的现象。

## 解决模块内构造器的引用

现在你会看到我们有一个错误，因为OCaml不知道这里的`Node`是什么意思。它不知道我们指的是`Tree`模块内部的`Node`。我们可以通过几种不同的方式向OCaml表明我们想要那个。

一种方式是在这里使用`Tree.Node`。一旦OCaml知道了这一点，它就不会强迫我们在其余这些地方写`Tree.Leaf`，类型推断引擎会解决这个问题。

```ocaml
let t = Tree.Node (Tree.Leaf, 5, Tree.Leaf)
```

另一种帮助类型推断的方法是手动注解`t`的类型。

```ocaml
let t : int Tree.tree = Node (Leaf, 5, Leaf)
```

现在我们不必在任何构造器前面加上`Tree.`了。

## 关键概念总结

以下是使用模块和结构体的核心要点：

*   **模块定义**：使用 `module 模块名 = struct ... end` 语法。
*   **访问成员**：使用 `模块名.成员名`（如 `MyList.map`）来访问模块内部的类型、函数或值。
*   **作用域**：模块内的定义具有自己的命名空间，不会污染顶层作用域。
*   **类型注解**：在引用模块内定义的类型时，格式为 `模块名.类型名`（如 `int MyList.mylist`）。
*   **类型推断辅助**：提供显式的类型注解（如 `: int Tree.tree`）可以帮助编译器理解代码意图，从而简化构造器的使用。

## 本节课总结

本节课中我们一起学习了OCaml的模块和结构体。我们看到了如何利用它们将相关的代码组织在一起，创建清晰的层次化命名空间，从而避免不同部分代码之间的命名冲突。通过`模块名.成员名`的访问方式，我们可以明确地引用特定模块中的定义，这使得大型程序的构建和维护变得更加清晰和可靠。