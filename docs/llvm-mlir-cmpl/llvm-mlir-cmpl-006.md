# 006：语义分析器 🧠

在本节课中，我们将要学习编译器的下一个关键阶段：语义分析。我们将探讨语义分析器的作用，它如何检查程序的逻辑正确性，以及如何通过重写抽象语法树（AST）来为后续的代码生成阶段做准备。

---

## 概述

在之前的课程中，我们介绍了读取器和AST构建器。它们负责将源代码转换为表示其语法结构的AST。然而，语法正确的程序在逻辑上可能仍然是无意义的。语义分析器的任务就是确保程序在逻辑上也是正确的，例如检查类型是否匹配，以及识别诸如“调用一个数字”这类语义错误。

## 关于前几集问题的解答

![](img/a4f2cba96bb70490c3b21f4895f7607b_1.png)

在开始之前，我们先回答几个关于上一集的问题。

![](img/a4f2cba96bb70490c3b21f4895f7607b_3.png)

### 为什么没有实现链表？

![](img/a4f2cba96bb70490c3b21f4895f7607b_5.png)

![](img/a4f2cba96bb70490c3b21f4895f7607b_7.png)

在上一集的实现中，列表是围绕`std::vector`的包装器。我们的目标是先创建一个简单的编译器，然后在此基础上构建。目前，我们不需要实现一个真正的链表。在未来的类型系统阶段，我们将需要创建一个MLIR类型系统中的列表类型，这与C++的链表不同。

![](img/a4f2cba96bb70490c3b21f4895f7607b_9.png)

![](img/a4f2cba96bb70490c3b21f4895f7607b_10.png)

### 为什么使用`std::vector`而不是LLVM集合？

![](img/a4f2cba96bb70490c3b21f4895f7607b_12.png)

![](img/a4f2cba96bb70490c3b21f4895f7607b_13.png)

![](img/a4f2cba96bb70490c3b21f4895f7607b_15.png)

![](img/a4f2cba96bb70490c3b21f4895f7607b_17.png)

LLVM提供了许多替代标准库类型的数据结构，例如`llvm::SmallVector`。这些替代品通常更快、更高效。目前，为了代码的清晰易懂，我们使用了大家熟悉的`std::vector`。未来在重构代码时，我们会将其替换为LLVM的替代类型。

---

## 什么是语义分析？

![](img/a4f2cba96bb70490c3b21f4895f7607b_19.png)

![](img/a4f2cba96bb70490c3b21f4895f7607b_20.png)

![](img/a4f2cba96bb70490c3b21f4895f7607b_22.png)

语义分析阶段会检查AST，确保程序符合语言规范，在逻辑上是正确的。例如，考虑以下代码片段：

![](img/a4f2cba96bb70490c3b21f4895f7607b_24.png)

![](img/a4f2cba96bb70490c3b21f4895f7607b_26.png)

```lisp
(4 main)
```

从语法上看，这是一个有效的列表。但从语义上看，它试图调用一个数字（4），这是没有意义的。语义分析器的工作就是捕获这类错误。

## 语义分析中的重写

![](img/a4f2cba96bb70490c3b21f4895f7607b_28.png)

![](img/a4f2cba96bb70490c3b21f4895f7607b_30.png)

在我们的Serene编译器中，语义分析阶段不仅进行错误检查，还会对AST进行重写。我们通过识别特定的模式，将通用的列表节点替换为更具语义的专用节点。

以下是一个例子，展示了语义分析前后的AST变化：

**源代码:**
```lisp
(def main (fn [] (prn (main))))
```

**原始AST (语法表示):**
```
List
├── Symbol: def
├── Symbol: main
└── List
    ├── Symbol: fn
    ├── List: []        ; 参数列表
    └── List
        ├── Symbol: prn
        └── List
            └── Symbol: main
```

**重写后的AST (语义表示):**
```
Def
├── Symbol: main
└── Fn
    ├── List: []        ; 参数列表
    └── Call
        ├── Target: prn  ; 解析后的符号
        └── Args: [Call
                    ├── Target: main ; 解析后的符号
                    └── Args: []]
```

通过重写，我们将嵌套的列表结构转换为了`Def`、`Fn`和`Call`等节点，这使得AST更清晰，也更容易进行类型检查和后续的MLIR代码生成。

---

## 语义分析器的工作原理

![](img/a4f2cba96bb70490c3b21f4895f7607b_32.png)

![](img/a4f2cba96bb70490c3b21f4895f7607b_34.png)

![](img/a4f2cba96bb70490c3b21f4895f7607b_36.png)

现在，让我们深入代码，看看语义分析器是如何工作的。

![](img/a4f2cba96bb70490c3b21f4895f7607b_38.png)

### 入口点

语义分析器的入口点是一个名为`analyze`的函数。它接收一个设置上下文和一个AST，并返回一个`AnalyzeResult`，其中包含处理后的AST或错误列表。

![](img/a4f2cba96bb70490c3b21f4895f7607b_40.png)

```cpp
// 位于 `include/reader/semantic_analysis.h`
AnalyzeResult analyze(SettingContext &ctx, AST &tree);
```

### 核心逻辑

![](img/a4f2cba96bb70490c3b21f4895f7607b_42.png)

![](img/a4f2cba96bb70490c3b21f4895f7607b_44.png)

`analyze`函数的核心逻辑是遍历AST中的每个节点，并调用其`analyze`成员函数。根据返回的`MaybeNode`结果，我们决定是重写节点、保留原节点还是记录错误。

```cpp
// 简化后的核心循环逻辑
AST new_ast;
std::vector<ErrorPtr> errors;

![](img/a4f2cba96bb70490c3b21f4895f7607b_46.png)

for (auto &node : tree) {
    auto maybe_node = node->analyze(ctx);
    
    if (maybe_node.isSuccess()) {
        auto new_node = maybe_node.getValue();
        if (new_node != nullptr) {
            // 情况1：需要重写，使用新节点
            new_ast.push_back(new_node);
        } else {
            // 情况2：无需重写，保留原节点
            new_ast.push_back(node);
        }
    } else {
        // 情况3：分析失败，记录错误
        errors.push_back(maybe_node.getError());
    }
}

![](img/a4f2cba96bb70490c3b21f4895f7607b_48.png)

if (errors.empty()) {
    return AnalyzeResult::success(new_ast);
} else {
    return AnalyzeResult::failure(errors);
}
```

### 表达式节点的分析

每个表达式节点（如`Symbol`、`Number`、`List`）都必须实现`analyze`接口。

*   **`Symbol`和`Number`节点**：它们直接返回一个包含`nullptr`的成功结果，表示不需要重写。
    ```cpp
    MaybeNode Symbol::analyze(SettingContext &ctx) {
        return MaybeNode::success(nullptr); // 无需重写
    }
    ```

*   **`List`节点**：这是重写发生的地方。`List::analyze`会检查列表的第一个元素是否是特殊形式（如`def`, `fn`）或函数调用，并调用相应的`make`函数来创建新的语义节点。
    ```cpp
    MaybeNode List::analyze(SettingContext &ctx) {
        if (this->elements.empty()) {
            return MaybeNode::success(nullptr);
        }
        auto first = this->elements[0];
        
        // 检查是否为特殊形式或函数调用
        if (auto sym = llvm::dyn_cast<Symbol>(first.get())) {
            if (sym->name == "def") {
                return Def::make(ctx, this);
            } else if (sym->name == "fn") {
                return Fn::make(ctx, this);
            } else {
                // 视为函数调用
                return Call::make(ctx, this);
            }
        }
        // 如果第一个元素不是符号，也视为函数调用
        return Call::make(ctx, this);
    }
    ```

---

## 新的语义节点类型

![](img/a4f2cba96bb70490c3b21f4895f7607b_50.png)

![](img/a4f2cba96bb70490c3b21f4895f7607b_52.png)

在语义分析阶段，我们引入了三种新的节点类型：`Def`、`Fn`和`Call`。

![](img/a4f2cba96bb70490c3b21f4895f7607b_54.png)

![](img/a4f2cba96bb70490c3b21f4895f7607b_56.png)

![](img/a4f2cba96bb70490c3b21f4895f7607b_57.png)

### `Def` 节点

![](img/a4f2cba96bb70490c3b21f4895f7607b_59.png)

`Def`节点表示一个绑定定义，例如`(def x 10)`。它包含一个绑定名称和一个值表达式。

*   **`make`函数**：`Def::make`函数负责验证输入列表的格式（必须恰好有三个元素），并创建`Def`节点。它还会在当前的语义作用域中创建这个绑定。
    ```cpp
    // 伪代码，展示Def::make的核心职责
    MaybeNode Def::make(SettingContext &ctx, List *list) {
        // 1. 检查参数数量是否为3
        // 2. 验证第一个元素是'symbol'且名为'def'
        // 3. 验证第二个元素是'symbol'（绑定名）
        // 4. 分析第三个元素（值）
        // 5. 在当前作用域创建绑定
        // 6. 返回新的Def节点
    }
    ```

### `Fn` 节点

`Fn`节点表示一个函数定义（或匿名函数）。它包含函数名（可为空）、参数列表和函数体。

*   **`make`函数**：`Fn::make`函数验证参数，分析函数体，并创建`Fn`节点。如果函数是通过`def`定义的，`Def::make`会调用`setName`来设置函数名。
    ```cpp
    // 伪代码，展示Fn::make的核心职责
    MaybeNode Fn::make(SettingContext &ctx, List *list) {
        // 1. 检查参数数量至少为2
        // 2. 验证第一个元素是'symbol'且名为'fn'
        // 3. 获取第二个元素作为参数列表
        // 4. 获取剩余元素作为函数体
        // 5. 对函数体进行语义分析
        // 6. 返回新的Fn节点
    }
    ```

### `Call` 节点

![](img/a4f2cba96bb70490c3b21f4895f7607b_61.png)

`Call`节点表示一个函数调用。它包含一个目标表达式（要调用的函数）和一个参数列表。

![](img/a4f2cba96bb70490c3b21f4895f7607b_63.png)

*   **`make`函数**：`Call::make`函数分析调用目标（可能是一个需要解析的符号，或者是另一个表达式的结果），分析所有参数，并创建`Call`节点。
    ```cpp
    // 伪代码，展示Call::make的核心职责
    MaybeNode Call::make(SettingContext &ctx, List *list) {
        // 1. 检查列表非空
        // 2. 分析第一个元素（调用目标）
        // 3. 如果目标是符号，在作用域中解析它
        // 4. 分析剩余元素作为参数
        // 5. 返回新的Call节点
    }
    ```

---

## 与编译器交互

![](img/a4f2cba96bb70490c3b21f4895f7607b_65.png)

你可以使用编译器的`semantic`动作来查看经过语义分析后的AST。

![](img/a4f2cba96bb70490c3b21f4895f7607b_67.png)

```bash
./serene hello.sr -action semantic -o output
```

![](img/a4f2cba96bb70490c3b21f4895f7607b_69.png)

![](img/a4f2cba96bb70490c3b21f4895f7607b_70.png)

这将输出重写后的AST，其中原始的列表节点已被替换为`Def`、`Fn`和`Call`等语义节点。

---

## 总结

本节课中，我们一起学习了编译器语义分析阶段的核心内容。

*   **语义分析的作用**：确保语法正确的程序在逻辑上也是有效的，检查类型和语义规则。
*   **AST重写**：通过识别模式（如`def`、`fn`、函数调用），将通用的`List`节点重写为具有明确语义的节点（`Def`、`Fn`、`Call`），这极大地简化了后续的代码生成工作。
*   **新的节点类型**：我们详细介绍了`Def`、`Fn`和`Call`节点的结构及其`make`函数的工作流程。
*   **错误处理**：语义分析器会收集所有遇到的语义错误，而不是在第一个错误处停止。

语义分析是连接前端语法分析和后端代码生成的关键桥梁。它产生的富含语义信息的AST，将使我们下一阶段的工作——将其转换为MLIR中间表示——变得更加直接。

![](img/a4f2cba96bb70490c3b21f4895f7607b_72.png)

在下一节课中，我们将探讨**Serene上下文**、**命名空间**和**作用域**，这些概念对于管理符号解析和绑定至关重要。敬请期待！