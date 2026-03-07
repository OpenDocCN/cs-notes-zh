# 009：IR（SLIR）生成 🧠

在本节课中，我们将学习如何为我们的编译器生成中间表示（IR）。我们将创建一个名为SLIR（Serene Language Intermediate Representation）的简单IR，它直接映射自抽象语法树（AST）。我们将使用MLIR的TableGen工具来定义方言和操作，并最终生成IR。

## 概述

上一节我们讨论了语义分析，本节我们将看看如何将分析后的AST转换为IR。IR生成是连接前端（解析、分析）和后端（优化、代码生成）的关键桥梁。我们将创建一个简单的方言，包含几个基础操作，并使用MLIR的构建器（Builder）来生成IR。

## 定义方言与操作

为了生成IR，我们首先需要定义一个MLIR方言（Dialect）。方言是一组相关操作的集合。我们将使用MLIR的ODS（Operation Definition Specification）框架，通过TableGen来定义我们的方言和操作，这比直接用C++定义要简单得多。

以下是定义我们方言（`serene`）和三个基础操作（`value`， `fn`， `return`）的ODS文件核心内容：

```tablegen
// 定义 serene 方言
def Serene_Dialect : Dialect {
  let name = "serene";
  let cppNamespace = "serene";
  let summary = "Serene Language Dialect";
  let description = [{
    This is a minimal dialect for the Serene compiler wiring.
  }];
}

// 定义所有 serene 操作的基础类
class Serene_Op<string mnemonic, list<Trait> traits = []> :
    Op<Serene_Dialect, mnemonic, traits>;

![](img/e848665f6c73b4117590a6b17ec88bf2_1.png)

![](img/e848665f6c73b4117590a6b17ec88bf2_3.png)

// 定义 value 操作，用于表示一个整数值
def ValueOp : Serene_Op<"value"> {
  let summary = "integer value operation";
  let arguments = (ins I64Attr:$value);
  let results = (outs I64);
  let verifier = [{ return ::verify(*this); }];
  let builders = [
    OpBuilder<(ins "int64_t":$value), [{
      build($_builder, $_state, value);
    }]>
  ];
}

// 定义 fn 操作，用于表示函数定义
def FnOp : Serene_Op<"fn", [IsolatedFromAbove]> {
  let summary = "function operation";
  let arguments = (ins StrAttr:$name,
                       DictionaryAttr:$args,
                       OptionalAttr<StrAttr>:$visibility);
  let regions = (region AnyRegion:$body);
  let results = (outs I64);
}

// 定义 return 操作，用于从函数返回
def ReturnOp : Serene_Op<"return", [HasParent<"FnOp">, Terminator]> {
  let summary = "return operation";
  let arguments = (ins AnyType:$operand);
  let assemblyFormat = "attr-dict $operand `:` type($operand)";
}
```

**代码解释**:
*   `Serene_Dialect`: 定义了方言的基本信息，如名称和C++命名空间。
*   `Serene_Op`: 是一个辅助类，所有具体操作都继承自它，简化了定义。
*   `ValueOp`: 表示一个整数值。它有一个`I64`类型的属性（`$value`）作为输入，并产生一个`I64`类型的结果。我们还定义了一个自定义的构建器（`builder`）方法。
*   `FnOp`: 表示函数定义。它包含函数名、参数字典、可见性等属性，并拥有一个区域（`region`）来表示函数体。`IsolatedFromAbove`是一个特质（Trait），表示此区域与上层作用域隔离。
*   `ReturnOp`: 表示返回语句。`HasParent<"FnOp">`特质确保它只出现在`FnOp`内部，`Terminator`特质表示它是一个基本块的终结操作。`assemblyFormat`定义了该操作在文本格式中的打印样式。

## 配置构建与生成C++代码

定义了ODS文件后，我们需要配置CMake，使用TableGen工具将其转换为实际的C++头文件和源文件。

以下是在CMakeLists.txt中的关键配置：

```cmake
# 设置TableGen，从 .td 文件生成 C++ 代码
mlir_tablegen(SereneOps.h.inc -gen-op-decls)
mlir_tablegen(SereneOps.cpp.inc -gen-op-defs)
mlir_tablegen(SereneDialect.h.inc -gen-dialect-decls)
mlir_tablegen(SereneDialect.cpp.inc -gen-dialect-defs)

# 将生成的文件添加为库的依赖
add_dependencies(sereneCore SereneOpsGen SereneDialectGen)
```

TableGen会为我们生成 `SereneOps.h.inc`、`SereneDialect.h.inc` 等文件，其中包含了操作和方言的类声明与定义。在我们的C++代码中，只需包含这些生成的文件即可使用定义好的方言和操作。

## 在编译器上下文中加载方言

我们的编译器状态由`SereneContext`类管理。在它的构造函数中，我们需要加载我们将要使用的所有MLIR方言。

```cpp
SereneContext::SereneContext() {
  // 加载 serene 方言和 MLIR 标准方言
  getMLIRContext().loadDialect<serene::SereneDialect>();
  getMLIRContext().loadDialect<mlir::StandardOpsDialect>();
}
```

这样，`SereneContext`就持有了一个`MLIRContext`，并且预先加载了必要的方言，为后续的IR生成做好了准备。

## 生成IR：从AST到MLIR模块

IR生成的核心入口是`Namespace`类的`generate`函数。它遍历该命名空间下的AST，为每个节点生成对应的IR操作，并将它们组装成一个MLIR模块。

以下是生成过程的关键步骤：

```cpp
llvm::Expected<mlir::OwningModuleRef> Namespace::generate() {
  // 1. 为当前MLIR上下文创建一个构建器(Builder)
  mlir::OpBuilder builder(&getContext());

  // 2. 创建一个空的MLIR模块，位置暂时未知
  auto unknownLoc = builder.getUnknownLocation();
  auto module = mlir::ModuleOp::create(unknownLoc, getName());

  // 3. 获取当前命名空间的AST并遍历
  auto &tree = getTree();
  for (auto &node : tree) {
    // 为每个AST节点生成IR，并添加到模块中
    if (auto expr = node->generateIR(*this, module)) {
      // 生成成功，expr可能是一个操作结果
    } else {
      // 处理生成错误
      return expr.takeError();
    }
  }

  // 4. 验证整个模块的IR是否符合规则
  if (failed(module.verify())) {
    // 验证失败，发出错误信息
    emitError(...);
    module.erase();
    return makeError(...);
  }

  // 5. (可选) 在此可以运行一些MLIR优化或转换Pass
  // passManager.run(module.get());

  // 6. 返回拥有该模块的智能指针
  return mlir::OwningModuleRef(module);
}
```

**流程解析**:
1.  **创建构建器**：`OpBuilder`是创建MLIR操作的工厂，它需要一个`MLIRContext`。
2.  **创建模块**：所有操作最终都必须包含在一个`ModuleOp`中。
3.  **遍历AST生成IR**：这是最核心的一步。我们调用每个AST节点（表达式）的`generateIR`方法。该方法使用构建器创建对应的MLIR操作，并将其插入到正确的位置（例如，函数体内部）。
4.  **验证模块**：生成完成后，调用`verify()`确保IR的结构和类型是合法的。
5.  **运行Pass**：我们可以在此插入MLIR的Pass管理器，对生成的IR进行优化或 lowering（ lowering 指将高级IR转换为更低级IR的过程）。
6.  **返回结果**：使用`OwningModuleRef`智能指针返回模块，它会在离开作用域时自动销毁模块。

## 具体AST节点的IR生成示例

让我们看看几个具体AST节点（如数字字面量、函数定义）是如何实现`generateIR`方法的。

**数字字面量（NumberExpr）的IR生成**：

```cpp
// 数字节点生成一个 `serene.value` 操作
mlir::Value NumberExpr::generateIR(serene::Namespace &ns,
                                   mlir::ModuleOp &module) const {
  auto &builder = ns.getBuilder();
  // 将源码位置转换为MLIR位置
  auto loc = getLocation().toMLIRLocation(ns);
  // 使用构建器创建 `serene.value` 操作，传入整数值
  auto valueOp = builder.create<serene::ValueOp>(loc, getValue());
  // 返回该操作产生的 SSA 值
  return valueOp.getResult();
}
```

**函数定义（DefExpr）的IR生成（简化版）**：

```cpp
mlir::LogicalResult DefExpr::generateIR(serene::Namespace &ns,
                                        mlir::ModuleOp &module) const {
  auto &builder = ns.getBuilder();
  auto loc = getLocation().toMLIRLocation(ns);

  // 1. 准备函数参数的类型属性列表
  llvm::SmallVector<mlir::NamedAttribute, 4> args;
  for (auto &arg : getArgs()) {
    auto *sym = llvm::dyn_cast<SymbolExpr>(arg.get());
    if (!sym) { /* 错误处理 */ }
    // 为每个参数创建 (名字, 类型) 的属性对，当前类型固定为 i64
    auto typeAttr = builder.getTypeAttr(builder.getI64Type());
    args.emplace_back(builder.getNamedAttr(sym->getName(), typeAttr));
  }

  // 2. 创建 `serene.fn` 操作
  auto fnOp = builder.create<serene::FnOp>(
      loc,
      builder.getI64Type(), // 返回类型
      getName(),            // 函数名
      builder.getDictionaryAttr(args), // 参数字典
      "public"              // 可见性
  );

  // 3. 获取函数的区域（body）并创建入口块
  auto &body = fnOp.body();
  auto *entryBlock = new mlir::Block();
  body.push_back(entryBlock);
  builder.setInsertionPointToStart(entryBlock);

  // 4. 在函数体内生成代码（这里简化为生成一个常量0并返回）
  auto constOp = builder.create<serene::ValueOp>(loc, 0);
  auto returnVal = constOp.getResult();

  // 5. 创建 `serene.return` 操作
  builder.create<serene::ReturnOp>(loc, returnVal);

  // 6. 将函数操作添加到模块中
  module.push_back(fnOp);
  return mlir::success();
}
```

## 查看生成的IR

生成IR后，我们可以将其以文本形式打印出来进行检查。在MLIR中，我们可以控制打印的细节，比如是否包含调试位置信息。

```cpp
// 打印模块，并启用调试信息以显示位置
module.print(llvm::outs(), mlir::OpPrintingFlags().enableDebugInfo());
```

![](img/e848665f6c73b4117590a6b17ec88bf2_5.png)

![](img/e848665f6c73b4117590a6b17ec88bf2_6.png)

启用调试信息后，打印出的IR可能如下所示：

```mlir
module {
  serene.fn @main(%arg0: i64) -> i64 {
    %0 = serene.value 0 : i64 loc(#loc1)
    serene.return %0 : i64 loc(#loc2)
  } loc(#loc0)
}
loc(#loc0) = "main.sr" line:0 column:0
loc(#loc1) = "main.sr" line:1 column:10
loc(#loc2) = "main.sr" line:1 column:15
```

我们可以看到：
*   `serene.fn` 定义了一个函数。
*   `serene.value` 创建了一个常量值。
*   `serene.return` 返回一个值。注意它的打印格式受我们定义的`assemblyFormat`影响，非常简洁。
*   末尾的`loc(...)`表是位置别名，将`#loc0`、`#loc1`等映射到具体的文件、行、列位置，这使得IR在保持可读性的同时包含了完整的源码位置信息。

## 总结

![](img/e848665f6c73b4117590a6b17ec88bf2_8.png)

本节课我们一起学习了编译器IR生成的核心过程。我们使用MLIR的TableGen工具定义了一个简单的`serene`方言及其操作，在编译器上下文中加载它，然后通过遍历AST，利用MLIR的`OpBuilder`将每个节点转换为对应的IR操作，最终组装成一个完整的、可验证的MLIR模块。这个过程为我们后续进行IR转换、优化以及生成LLVM IR打下了坚实的基础。下一节，我们将探讨如何利用MLIR的Pass基础设施来分析和转换我们刚刚生成的SLIR。