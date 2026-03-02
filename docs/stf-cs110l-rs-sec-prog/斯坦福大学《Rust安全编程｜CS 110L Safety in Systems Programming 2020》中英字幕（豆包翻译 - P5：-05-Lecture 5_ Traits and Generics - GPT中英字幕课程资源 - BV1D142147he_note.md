# Rust安全编程：第5讲：Trait与泛型

![](img/b826c7c0d862e7e0c0e8c8030c67db48_1.png)

在本节课中，我们将学习Rust中两个核心概念：Trait（特质）和泛型。Trait用于定义共享的行为，而泛型允许我们编写可复用于多种数据类型的代码。我们将通过具体的代码示例来理解这些概念，并学习如何在实际编程中应用它们。

![](img/b826c7c0d862e7e0c0e8c8030c67db48_3.png)

![](img/b826c7c0d862e7e0c0e8c8030c67db48_5.png)

---

![](img/b826c7c0d862e7e0c0e8c8030c67db48_7.png)

## 分组相关功能

在C++和Java等语言中，我们通常使用抽象类或接口来分组相关功能。例如，一个“形状”抽象类可能定义了计算面积和周长的抽象方法。在Rust中，我们使用Trait来实现类似的功能。Trait定义了一个类型可以做什么，例如，如果一个类型实现了`Display`特质，它就知道如何以可读的格式展示自己。

## 什么是Trait？

![](img/b826c7c0d862e7e0c0e8c8030c67db48_9.png)

![](img/b826c7c0d862e7e0c0e8c8030c67db48_10.png)

![](img/b826c7c0d862e7e0c0e8c8030c67db48_11.png)

Trait是Rust中定义共享行为的一种方式。它们类似于其他语言中的接口，但功能更强大。通过Trait，我们可以定义一组方法签名，任何实现该Trait的类型都必须提供这些方法的具体实现。

以下是一些常见的标准库Trait：
*   **`Display`**: 用于格式化输出，例如在`println!`宏中使用。
*   **`Debug`**: 用于调试输出，通常通过`#[derive(Debug)]`自动派生。
*   **`Clone` / `Copy`**: `Clone`允许显式复制数据，`Copy`则改变了赋值运算符`=`的语义，使其执行复制而非所有权转移。
*   **`Drop`**: 定义值离开作用域时发生的清理行为。
*   **`PartialEq` / `Eq`**: 用于定义相等性比较。

## 实现Trait

让我们通过一个链表例子来看如何实现Trait。我们为链表实现`Display`特质，使其能够被打印。

```rust
impl fmt::Display for LinkedList {
    fn fmt(&self, f: &mut fmt::Formatter) -> fmt::Result {
        let mut result = String::new();
        let mut current = &self.head;
        while let Some(node) = current {
            result = format!("{} {}", result, node.val);
            current = &node.next;
        }
        write!(f, "{}", result)
    }
}
```

实现之后，我们就可以直接使用`println!("{}", list);`来打印链表了。

上一节我们介绍了如何手动实现Trait，本节中我们来看看如何让编译器自动为我们生成一些常用Trait的实现。

![](img/b826c7c0d862e7e0c0e8c8030c67db48_13.png)

![](img/b826c7c0d862e7e0c0e8c8030c67db48_14.png)

## 派生Trait

![](img/b826c7c0d862e7e0c0e8c8030c67db48_16.png)

![](img/b826c7c0d862e7e0c0e8c8030c67db48_17.png)

对于许多简单的结构体，Rust编译器可以自动为我们派生（derive）一些Trait的实现，这通过`#[derive(...)]`属性实现。

```rust
#[derive(Debug, PartialEq, Clone, Copy)]
struct Point {
    x: f64,
    y: f64,
}
```

以下是可以通过`#[derive]`自动派生的部分Trait：
*   `Debug`
*   `PartialEq`, `Eq`
*   `PartialOrd`, `Ord`
*   `Clone`
*   `Copy`
*   `Hash`
*   `Default`

## 定义自己的Trait

我们不仅可以实现现有的Trait，还可以定义自己的Trait来描述特定领域的行为。

```rust
pub trait ComputeNorm {
    fn compute_norm(&self) -> f64 {
        // 默认实现
        0.0
    }
}
```

![](img/b826c7c0d862e7e0c0e8c8030c67db48_19.png)

![](img/b826c7c0d862e7e0c0e8c8030c67db48_20.png)

然后，我们可以为不同的类型实现这个Trait：

![](img/b826c7c0d862e7e0c0e8c8030c67db48_22.png)

![](img/b826c7c0d862e7e0c0e8c8030c67db48_23.png)

```rust
impl ComputeNorm for Point {
    fn compute_norm(&self) -> f64 {
        (self.x * self.x + self.y * self.y).sqrt()
    }
}

impl ComputeNorm for Vec<f64> {
    fn compute_norm(&self) -> f64 {
        self.iter().map(|x| x * x).sum::<f64>().sqrt()
    }
}
```

## 使用Trait重载运算符

Trait还可以用来重载运算符。例如，我们可以为`Point`类型实现加法运算符`+`。

```rust
use std::ops::Add;

impl Add for Point {
    type Output = Self;

    fn add(self, other: Self) -> Self::Output {
        Point {
            x: self.x + other.x,
            y: self.y + other.y,
        }
    }
}
```

实现之后，我们就可以使用`let p3 = p1 + p2;`这样的语法了。

## 泛型

![](img/b826c7c0d862e7e0c0e8c8030c67db48_25.png)

![](img/b826c7c0d862e7e0c0e8c8030c67db48_26.png)

泛型允许我们编写不依赖于具体数据类型的代码，从而提高代码的复用性。你已经使用过泛型了，例如`Vec<T>`和`Option<T>`。

![](img/b826c7c0d862e7e0c0e8c8030c67db48_28.png)

### 定义泛型结构体

![](img/b826c7c0d862e7e0c0e8c8030c67db48_30.png)

我们可以定义自己的泛型结构体。

![](img/b826c7c0d862e7e0c0e8c8030c67db48_32.png)

![](img/b826c7c0d862e7e0c0e8c8030c67db48_34.png)

```rust
struct MatchingPair<T> {
    first: T,
    second: T,
}

impl<T> MatchingPair<T> {
    fn new(first: T, second: T) -> Self {
        MatchingPair { first, second }
    }
}
```

### Trait约束

泛型常常与Trait约束（Trait Bound）结合使用，以限制泛型类型参数必须实现某些特定行为。

```rust
impl<T: fmt::Display> fmt::Display for MatchingPair<T> {
    fn fmt(&self, f: &mut fmt::Formatter) -> fmt::Result {
        write!(f, "({}, {})", self.first, self.second)
    }
}
```

上面的代码为所有实现了`Display`特质的类型`T`的`MatchingPair<T>`实现了`Display`特质。这意味着只要`T`能被显示，`MatchingPair<T>`就能被显示，我们无需为每种具体的`T`（如`char`、`i32`、`String`）单独实现。

---

![](img/b826c7c0d862e7e0c0e8c8030c67db48_36.png)

本节课中我们一起学习了Rust中Trait和泛型的核心概念。Trait是定义共享行为的强大工具，允许我们以灵活的方式组织代码功能。泛型则让我们能够编写可复用的代码，而Trait约束确保了泛型代码的类型安全。结合使用Trait和泛型，可以极大地提升Rust代码的表达力和抽象能力。在接下来的课程中，我们将继续探索这些概念在更复杂场景中的应用。