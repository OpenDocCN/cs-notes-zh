# Rust编程（基础）：P51：关联函数与构造函数演示 🏗️

![](img/9b12c4034ea94949b2ee0849bf941199_0.png)

在本节课中，我们将学习Rust中一个非常实用的概念：**关联函数**。关联函数是定义在类型（如结构体）上下文中的函数，它不需要一个具体的实例（即不需要`self`参数）。我们将重点探讨如何使用关联函数来创建**构造函数**，这是一种自动化创建结构体实例并设置默认值的强大方式。

## 结构体定义

首先，我们从一个简单的结构体定义开始。假设我们正在构建一个用户系统，需要一个`User`结构体来存储用户信息。

```rust
struct User {
    username: String,
    email: String,
    uri: String,
    active: bool,
}
```

这个结构体包含用户名、邮箱、URI以及一个表示用户是否活跃的布尔值字段。这种简单的定义方式对于直接创建实例是可行的。

## 实现块与关联函数

上一节我们介绍了`User`结构体的基本定义。本节中，我们来看看如何使用`impl`（实现）块来为结构体扩展功能。`impl`关键字用于为特定类型（如结构体）实现功能。

```rust
impl User {
    // 关联函数将在这里定义
}
```

通过`impl User`，我们为`User`类型添加了新的能力。实现块内可以定义两种主要类型的函数：**关联函数**和**方法**。我们首先关注不需要实例的关联函数。

## 构造函数：`new` 函数

以下是创建构造函数的具体步骤。构造函数通常命名为`new`，这是一个约定俗成的做法，用于创建结构体的新实例。

1.  在`impl`块中，定义一个名为`new`的函数。
2.  这个函数**不接收**`self`参数，因为它是一个关联函数，而不是方法。
3.  函数的参数通常对应结构体的字段。
4.  在函数体内，返回一个构建好的结构体实例。

```rust
impl User {
    fn new(username: String, email: String, uri: String) -> User {
        User {
            username,
            email,
            uri,
            active: true, // 设置默认值
        }
    }
}
```

注意，我们在构造函数中做了一个重要的抽象：将`active`字段默认设置为`true`。这基于一个合理的假设：新创建的用户默认是活跃的。这样做避免了每次创建实例时都需要手动设置该字段，简化了调用过程。

## 使用构造函数

了解了如何定义构造函数后，现在让我们看看如何调用它来创建`User`实例。

```rust
let new_user = User::new(
    String::from("my_username"),
    String::from("pretodesa@example.com"),
    String::from("https://doc.rust-lang.org"),
);
```

我们使用结构体名`User`、双冒号`::`和函数名`new`来调用这个关联函数。通过传递必要的参数，我们就获得了一个`active`字段默认为`true`的新用户实例。

## 实例方法：接收 `self` 参数

除了构造函数，我们还可以在`impl`块中定义**方法**。方法与关联函数的区别在于，它的第一个参数是`self`，代表调用该方法的实例本身。这允许我们修改或查询实例的内部状态。

以下是一个实例方法的例子，它用于停用用户账户：

```rust
impl User {
    // ... 之前的 new 函数 ...

    fn deactivate(&mut self) {
        self.active = false;
        println!("Account status for {} is now: {}", self.username, self.active);
    }
}
```

这个方法接收一个可变的`self`引用（`&mut self`），因此它可以修改`active`字段的值。

要调用这个方法，你需要一个可变的`User`实例：

```rust
let mut new_user = User::new(...); // 创建可变实例
println!("Account status is: {}", new_user.active); // 输出: true
new_user.deactivate(); // 调用方法修改状态
println!("Account status is now: {}", new_user.active); // 输出: false
```

当`deactivate`方法被调用时，它操作的是`new_user`这个具体的实例，将其`active`状态改为`false`。

## 总结

本节课中我们一起学习了Rust中`impl`块的两个核心用途。

*   **关联函数**：例如构造函数`new`，它不依赖于实例（没有`self`参数），通过`StructName::function_name()`的语法调用。它非常适合用于执行初始化逻辑和提供默认值。
*   **实例方法**：它第一个参数是`self`（或`&self`、`&mut self`），代表当前实例。通过`instance.method_name()`的语法调用，用于执行与特定实例相关的操作，如修改字段或计算属性。

![](img/9b12c4034ea94949b2ee0849bf941199_2.png)

通过`impl`关键字，我们可以有组织地为结构体添加各种功能，使代码更加模块化和易于维护。构造函数帮助我们简化对象的创建过程，而实例方法则封装了对对象状态的操作。