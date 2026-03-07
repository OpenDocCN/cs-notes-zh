# 011：SLIR降级

在本节课中，我们将学习如何将自定义的SLIR方言降级到MLIR的其他方言，特别是标准方言和LLVM方言。这是将我们的高级中间表示转换为可执行代码的关键步骤。

## 概述

在前几节中，我们创建了一个编译器，它读取类Lisp语言的源代码，生成抽象语法树，进行语义分析，并最终生成我们自定义的SLIR方言。在上一节中，我们介绍了MLIR的Pass基础设施。本节中，我们将利用Pass基础设施，将SLIR方言中的操作转换为MLIR标准方言中的操作，并最终降级到LLVM方言。

## 什么是方言降级？

MLIR允许我们创建自定义方言，每种方言可能专用于特定任务。降级是指将一个方言中的操作转换为另一个方言中的操作的过程。我们的最终目标是将SLIR转换为LLVM方言，然后由LLVM后端生成目标代码。通常，这不是直接转换，而是通过一个或多个中间方言逐步完成。

MLIR提供了一个名为“方言转换”的框架来简化此过程，它构建在Pass基础设施之上。使用它需要完成两件必需的事情和一件可选的事情：
1.  **目标转换**：定义我们希望转换到的目标方言。
2.  **重写模式**：定义如何将源方言中的特定操作重写为目标方言中的操作。
3.  **类型转换器（可选）**：如果我们的方言有自定义类型，需要定义如何将这些类型转换为目标方言中的类型。

此外，还有**完全转换**与**部分转换**的概念。完全转换会转换整个方言；部分转换则只转换一部分操作，将剩余操作留给后续的Pass处理。

## 实现降级Pass

现在，我们来看看如何实现将SLIR降级到标准方言的Pass。

### Pass的注册与结构

首先，我们需要在Pass管理器中注册并添加我们的降级Pass。在我们的编译器上下文中，根据不同的编译阶段，我们向Pass管理器添加不同的Pass。

```cpp
// 这是一个示例，展示如何将降级Pass添加到Pass管理器
if (compilationPhase == “MLIR”) {
    passManager.addPass(createSLIRLoweringToMLIRPass());
}
if (compilationPhase == “LIR”) {
    passManager.addPass(createSLIRLoweringToMLIRPass());
    passManager.addPass(createStdToLLVMDialectPass());
}
```

我们的降级Pass是一个操作特定的Pass，它只处理模块操作。其核心是 `runOnOperation` 函数。

### 设置转换目标与合法性

在 `runOnModule` 函数中，我们首先创建转换目标，并标记哪些方言或操作是“合法”的。

```cpp
void SLIRToMLIRPass::runOnModule() {
    mlir::ModuleOp module = getOperation();
    mlir::ConversionTarget target(getContext());

    // 将标准方言标记为合法目标
    target.addLegalDialect<mlir::StandardOpsDialect>();
    // 将我们的SLIR方言标记为非法，意味着必须转换它
    target.addIllegalDialect<serene::sereneDialect>();

    // 可以标记特定操作为合法（例如，某些操作想留到后续Pass处理）
    // target.addLegalOp<serene::PrintOp>();
}
```

标记一个操作为“合法”意味着如果Pass没有提供该操作的重写模式，Pass管理器可以接受它。标记为“非法”则意味着必须提供重写模式将其转换，否则Pass会失败。

### 定义重写模式

接下来，我们需要为SLIR中的每个操作定义重写模式。重写模式是一个继承自 `OpRewritePattern` 的结构体，它需要实现 `matchAndRewrite` 函数。

以下是处理 `ValueOp`（表示一个常数值）的重写模式示例：

```cpp
struct ValueOpLowering : public mlir::OpRewritePattern<serene::ValueOp> {
    ValueOpLowering(mlir::MLIRContext *ctx) : OpRewritePattern<serene::ValueOp>(ctx) {}

    mlir::LogicalResult matchAndRewrite(serene::ValueOp op,
                                         mlir::PatternRewriter &rewriter) const override {
        // 1. 从ValueOp中获取常数值和位置信息
        mlir::Attribute valueAttr = op->getAttr(“value”);
        mlir::Location loc = op.getLoc();

        // 2. 由于模块顶层不能直接放置常量操作，我们将其包装在一个函数中
        llvm::SmallVector<mlir::Type, 1> argTypes; // 无参数
        mlir::Type returnType = rewriter.getI64Type(); // 返回i64类型
        auto funcType = rewriter.getFunctionType(argTypes, returnType);

        // 3. 创建一个函数操作
        auto funcOp = rewriter.create<mlir::FuncOp>(loc, “unique_name”, funcType);
        mlir::Block *entryBlock = funcOp.addEntryBlock();
        rewriter.setInsertionPointToStart(entryBlock);

        // 4. 在函数体内创建标准方言的常量操作
        auto constOp = rewriter.create<mlir::ConstantIntOp>(loc, valueAttr.cast<mlir::IntegerAttr>().getInt(), 64);
        // 5. 创建返回操作
        rewriter.create<mlir::ReturnOp>(loc, constOp.getResult());

        // 6. 将函数设置为私有（因为这个包装函数是内部使用的）
        funcOp.setPrivate();

        // 7. 删除原始的、非法的ValueOp
        rewriter.eraseOp(op);

        return mlir::success();
    }
};
```

**代码解释**：
*   我们创建了一个匿名函数来包装常量值。
*   在函数体内，使用标准方言的 `ConstantIntOp` 来创建常量。
*   最后，用 `ReturnOp` 返回该常量值，并删除原始的 `ValueOp`。

类似地，我们需要为 `FnOp`（函数定义操作）定义重写模式。在当前的简化实现中，我们暂时忽略函数体，只生成一个返回固定值（如3）的函数框架。在未来的完善中，我们需要遍历函数体AST并生成相应的操作。

### 应用转换

![](img/7fc36f385cafc413fc16da11459887b3_1.png)

![](img/7fc36f385cafc413fc16da11459887b3_3.png)

定义好重写模式后，我们将它们添加到模式集中，并应用部分转换。

```cpp
void SLIRToMLIRPass::runOnModule() {
    // ... 设置target ...

    mlir::OwningRewritePatternList patterns;
    patterns.insert<ValueOpLowering, FnOpLowering>(&getContext());

    if (mlir::failed(mlir::applyPartialConversion(module, target, std::move(patterns)))) {
        signalPassFailure();
        return;
    }
}
```

`applyPartialConversion` 函数会尝试应用所有提供的重写模式。如果任何标记为“非法”的操作没有被成功转换，函数会失败，我们随之通知Pass管理器。

## 从标准方言到LLVM方言

将SLIR降级到标准方言后，下一步是将标准方言降级到LLVM方言。这个过程更加直接，因为MLIR已经为我们提供了内置的转换模式。

```cpp
void StdToLLVMDialectPass::runOnModule() {
    mlir::ModuleOp module = getOperation();
    mlir::ConversionTarget target(getContext());

    // 将LLVM方言标记为合法目标
    target.addLegalDialect<mlir::LLVM::LLVMDialect>();
    // 将模块操作标记为合法（顶级容器）
    target.addLegalOp<mlir::ModuleOp>();

    // 创建类型转换器（当前为空，因为我们没有自定义类型）
    mlir::LLVMTypeConverter typeConverter(&getContext());

    // 使用MLIR内置工具填充标准方言到LLVM方言的转换模式
    mlir::OwningRewritePatternList patterns;
    mlir::populateStdToLLVMConversionPatterns(typeConverter, patterns);

    // 应用完全转换，所有内容都必须转换到LLVM方言
    if (mlir::failed(mlir::applyFullConversion(module, target, std::move(patterns)))) {
        signalPassFailure();
        return;
    }
}
```

`populateStdToLLVMConversionPatterns` 是MLIR提供的一个辅助函数，它自动为许多标准方言操作添加了到LLVM方言的重写模式，极大地简化了我们的工作。

## 运行与验证

通过命令行工具，我们可以指定不同的编译阶段来观察降级过程：

*   `--emit slir`：仅生成原始的SLIR，不运行任何Pass。
*   `--emit mlir`：运行SLIR到标准方言的降级Pass，输出标准方言的MLIR。
*   `--emit lir`：运行SLIR到标准方言，再到LLVM方言的降级Pass，输出LLVM方言的MLIR。

以下是一个简单Serene程序降级后的输出示例：

![](img/7fc36f385cafc413fc16da11459887b3_5.png)

![](img/7fc36f385cafc413fc16da11459887b3_6.png)

![](img/7fc36f385cafc413fc16da11459887b3_8.png)

![](img/7fc36f385cafc413fc16da11459887b3_10.png)

![](img/7fc36f385cafc413fc16da11459887b3_11.png)

**原始SLIR**:
```mlir
module {
  serene.fn @main() -> i64 {
    serene.value 42 : i64
  }
}
```

![](img/7fc36f385cafc413fc16da11459887b3_13.png)

**降级到标准方言后**:
```mlir
module {
  func private @main() -> i64 {
    %0 = constant 42 : i64
    return %0 : i64
  }
}
```

**降级到LLVM方言后**:
```mlir
module {
  llvm.func private @main() -> i64 {
    %0 = llvm.mlir.constant(42 : i64) : i64
    llvm.return %0 : i64
  }
}
```

## 总结

![](img/7fc36f385cafc413fc16da11459887b3_15.png)

![](img/7fc36f385cafc413fc16da11459887b3_17.png)

![](img/7fc36f385cafc413fc16da11459887b3_19.png)

在本节课中，我们一起学习了MLIR中方言降级的核心概念和实现方法。我们首先了解了转换目标、重写模式和类型转换器这三个关键组件。然后，我们逐步实现了将自定义SLIR方言降级到MLIR标准方言的Pass，详细剖析了如何为`ValueOp`和`FnOp`定义重写模式。最后，我们利用MLIR的内置支持，轻松地将标准方言进一步降级到了LLVM方言。这个过程为我们最终生成LLVM IR乃至目标代码奠定了坚实的基础。在下一节课中，我们将探索如何从LLVM方言生成真正的LLVM IR。