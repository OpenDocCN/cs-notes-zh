# Python代码补全器构建教程：1：概述与核心概念

![](img/d12cab4ccfc4304f1aba514a1562280c_1.png)

![](img/d12cab4ccfc4304f1aba514a1562280c_2.png)

在本教程中，我们将学习如何构建一个Python代码补全器。代码补全是现代代码编辑器的核心功能，它能提升开发效率、减少拼写错误并帮助开发者探索API。我们将从基础概念讲起，并逐步构建一个简单的补全器原型。

## 为什么代码补全很重要

代码补全为开发者提供了多项关键优势。

以下是其主要价值：

*   **可发现性**：无需翻阅文档，即可在编辑器中直接发现库和模块的可用API。
*   **速度**：通过输入少量字符并按下Tab键，快速补全长变量名或函数名。
*   **准确性**：避免拼写错误，并在编码时获得即时反馈，增强信心。
*   **流畅性**：帮助开发者保持专注和高效的“心流”状态。

## 代码补全的核心：理解程序

代码补全器的核心任务是回答“程序员接下来要输入什么？”。

为了回答这个问题，补全器必须理解光标周围的程序上下文。将源代码视为纯文本处理非常困难。幸运的是，Python解释器为我们提供了强大的工具——**解析**。

当Python运行程序时，它首先会将源代码文本转换为一种称为**抽象语法树**的结构化表示。

例如，对于以下代码：
```python
def greet():
    message = "Hello world"
    alert(message)
```
其AST（抽象语法树）可以概念化地表示为：
```
Module
└── FunctionDef(name='greet')
    ├── args: arguments(args=[])
    └── body: [
        Assign(targets=[Name(id='message')], value=Constant(value='Hello world')),
        Expr(value=Call(func=Name(id='alert'), args=[Name(id='message')]))
    ]
```
AST将代码转化为一系列易于程序遍历和操作的对象。Python标准库中的`ast`模块可以轻松完成这项工作：
```python
import ast
tree = ast.parse("x = 42")
```
通过解析代码，我们就能以结构化的方式“理解”程序，这是构建代码补全器的基石。

---

上一节我们介绍了代码补全的意义和解析的核心概念。本节中，我们将利用这些知识，开始构建一个最基础的代码补全器。

# Python代码补全器构建教程：2：构建基础补全器

我们的目标是：遍历AST，记录当前作用域中已定义的变量名，并在光标位置提供这些变量作为补全建议。

我们用一个特殊符号（例如`__CURSOR__`）来代表光标在源代码中的位置。

以下是构建基础补全器的步骤：

1.  **解析代码**：将包含光标标记的源代码字符串解析为AST。
2.  **遍历AST**：遍历树中的语句，构建当前作用域内已知变量名的集合。
3.  **识别光标**：在遍历过程中，检查是否遇到了代表光标的节点。
4.  **提供补全**：当遇到光标时，将已收集的变量名列表作为补全建议返回。

让我们用代码实现这个逻辑。假设我们有一个简单的代码片段：`x = 1\ny = 2\nz = __CURSOR__`。

```python
import ast

# 1. 解析包含光标的代码
source_code = "x = 1\ny = 2\nz = __CURSOR__"
tree = ast.parse(source_code)

# 2. 初始化变量集合和补全结果
variables_in_scope = set()
completions = []

# 3. 遍历AST
for statement in tree.body:
    if isinstance(statement, ast.Assign):
        # 这是一个赋值语句，例如 `x = 1`
        for target in statement.targets:
            if isinstance(target, ast.Name):
                # 将变量名加入作用域集合
                variable_name = target.id
                variables_in_scope.add(variable_name)

        # 检查赋值语句的值是否是我们的光标标记
        if isinstance(statement.value, ast.Name) and statement.value.id == "__CURSOR__":
            # 4. 遇到光标，提供当前作用域内的变量作为补全
            completions = sorted(variables_in_scope)

print("补全建议：", completions)
# 输出：补全建议： ['x', 'y']
```
这个简单的程序演示了代码补全的核心原理：通过解析和理解代码结构来提供上下文相关的建议。

---

上一节我们构建了一个能处理全局作用域变量的基础补全器。本节中我们来看看如何处理更复杂的代码结构，比如函数。

# Python代码补全器构建教程：3：处理函数与作用域

在函数内部，可用的变量包括函数参数、函数体内定义的变量以及外层作用域（如全局变量）的变量。我们的补全器需要理解这种作用域嵌套。

我们需要升级遍历逻辑，使其能够递归地处理像函数定义这样的复合语句。

以下是关键改进点：

*   **递归遍历**：当遇到`ast.FunctionDef`节点时，需要递归遍历其函数体。
*   **作用域建模**：为每个函数创建一个新的作用域，它继承自父作用域，并包含其参数和局部变量。

让我们修改代码以支持函数作用域。我们使用一个递归函数`walk`来遍历AST。

```python
import ast

def get_completions(source_code):
    tree = ast.parse(source_code)
    completions = [] # 存储最终补全结果

    def walk(node, scope):
        """
        递归遍历AST节点。
        node: 当前AST节点。
        scope: 当前作用域内的变量集合。
        """
        if isinstance(node, ast.Module):
            # 模块节点，遍历其所有语句
            for stmt in node.body:
                walk(stmt, scope)
        elif isinstance(node, ast.FunctionDef):
            # 函数定义节点
            # 1. 创建新作用域，继承父作用域变量
            new_scope = set(scope)
            # 2. 将函数参数添加到新作用域
            for arg in node.args.args:
                new_scope.add(arg.arg)
            # 3. 递归遍历函数体
            for stmt in node.body:
                walk(stmt, new_scope)
        elif isinstance(node, ast.Assign):
            # 赋值语句
            for target in node.targets:
                if isinstance(target, ast.Name):
                    # 将定义的变量加入当前作用域
                    scope.add(target.id)
            # 检查值是否为光标
            if isinstance(node.value, ast.Name) and node.value.id == "__CURSOR__":
                # 找到光标，设置补全建议为当前作用域的所有变量
                nonlocal completions
                completions = sorted(scope)
        # 可以继续添加对其他语句类型（如If, For）的处理

    # 初始作用域可以是内置函数等，这里为空
    initial_scope = set()
    walk(tree, initial_scope)
    return completions

# 测试代码
code_with_function = """
x = 10
def my_func(foo, bar):
    z = __CURSOR__
"""
print("函数内补全：", get_completions(code_with_function))
# 输出：函数内补全： ['bar', 'foo', 'x']
```
现在，我们的补全器已经能够理解函数作用域，并在函数体内提供正确的变量补全了。

![](img/d12cab4ccfc4304f1aba514a1562280c_4.png)

---

上一节我们实现了对函数和作用域的支持。本节中我们来探讨构建实用补全器时面临的主要挑战和解决思路。

# Python代码补全器构建教程：4：挑战与进阶思路

一个用于教学的原型补全器是简单的，但要构建一个能应对真实编程场景的补全器，则需要解决几个关键挑战。

## 1. 处理“向后引用”

在Python中，后面的代码可以定义前面代码中使用的函数或变量。例如：
```python
def double_all(nums):
    return [__CURSOR__(n) for n in nums] # 这里想补全 `twice`

def twice(x):
    return x * 2
```
当从上到下遍历AST时，在光标位置我们还未看到`twice`函数。一个实用的解决方法是**“作弊”**：先记住光标位于`double_all`函数内，然后扫描整个模块获取所有定义，最后再为光标位置提供补全。这种近似处理在实践中效果很好。

## 2. 处理无效（语法错误）代码

程序员在编辑时，代码经常处于语法无效状态。标准库的`ast.parse`遇到语法错误会直接抛出异常，导致无法获得AST。

解决策略包括：
*   **错误恢复解析器**：使用能够容忍错误并生成部分AST的解析器，如`jedi`、`tree-sitter`或`parso`。
*   **文本修补技巧**：尝试自动修复明显的语法错误（如未闭合的引号），使代码可解析。

## 3. 类型推断与智能补全

更高级的补全器能推断变量类型，从而提供属性（`.`）补全。例如，知道`alice`是`Person`类的实例，就能在输入`alice.`时建议`name`属性。

**类型**对于补全器而言，可以宽泛地定义为“任何在运行前我们能知道的关于值的信
息”。这包括：
*   类构造器调用（如`Person()`）。
*   类型注解。
*   对数据结构的认知（如，这个字典的键总是包含`"user_id"`和`"email"`）。

在Web开发中，客户端代码调用服务器API获取JSON数据是一个难点，因为补全器无法预知返回的数据结构。采用像**OpenAPI**规范来描述API接口，或使用全栈框架（如演讲者提到的Anvil）在前后端共享类型信息，是改善这一问题的方向。

---

# Python代码补全器构建教程：5：总结

本节课中我们一起学习了如何从零开始构建一个Python代码补全器。

我们从代码补全的重要性谈起，然后揭示了其核心原理：**通过解析源代码生成抽象语法树（AST），以理解程序结构**。我们利用Python内置的`ast`模块，现场构建了一个能处理变量和函数作用域的基础补全器。

我们也探讨了构建成熟补全器必须面对的挑战：
*   通过“作弊”处理**向后引用**。
*   使用错误恢复解析器或技巧处理**无效代码**。
*   通过**类型推断**实现更智能的属性补全。

最后，我们认识到代码补全器的目标不是进行完美的程序分析，而是**让程序员感到满意和高效**。因此，适当的近似和“作弊”不仅是可接受的，往往是必要的。

![](img/d12cab4ccfc4304f1aba514a1562280c_6.png)

希望本教程能帮助你揭开代码补全器的神秘面纱，并激发你深入探索编译器、解释器或IDE工具链相关领域的兴趣。