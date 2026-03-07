# 017：自定义ORC层 🧱

在本节课中，我们将学习如何为基于ORC的JIT引擎创建自定义层。我们将通过创建两个具体的层来理解其工作原理：一个用于添加命名空间（Namespace），另一个用于添加抽象语法树（AST）。自定义层允许我们将任何程序表示形式（如AST、字节码）集成到JIT编译流程中。

上一节我们介绍了ORC层的基本概念，它们是构建JIT引擎的基石。本节中，我们将深入探讨如何创建自定义层。

## 项目进展与重构

在开始之前，先同步一下项目进展。经过前17集的努力，我们已经完成了一个具备基本功能的编译器框架。这个框架包含了JIT引擎、MLIR、诊断系统、语义分析器、解析器等核心组件。虽然每个组件的功能尚不完善（例如，错误处理仅打印信息），但我们的目标——将它们连接起来形成一个可工作的基本设计——已经实现。

![](img/c7f866b218336c088c7edc01b4426b8a_1.png)

为了便于未来开发者与LLVM项目协作，我重构了项目结构，使其遵循与LLVM源码树相似的目录组织方式。同时，我也重构了构建系统，为每个组件添加了独立的CMake目标，这使得从源码安装编译器更加清晰和可定制。在达到一个里程碑后，进行代码审查、清理、文档更新和编写测试是确保代码质量的重要步骤。完成这些重构后，我们将专注于改进各个组件，并开始设计具体的编程语言规范。

![](img/c7f866b218336c088c7edc01b4426b8a_3.png)

![](img/c7f866b218336c088c7edc01b4426b8a_5.png)

![](img/c7f866b218336c088c7edc01b4426b8a_7.png)

## ORC层回顾

![](img/c7f866b218336c088c7edc01b4426b8a_9.png)

![](img/c7f866b218336c088c7edc01b4426b8a_11.png)

![](img/c7f866b218336c088c7edc01b4426b8a_13.png)

![](img/c7f866b218336c088c7edc01b4426b8a_15.png)

让我们快速回顾一下ORC层的关键概念。一个基于ORC的JIT引擎由一系列层（Layer）构成，这些层形成一个层次结构。每一层只了解其下游的层，并通过调用下游层的接口来传递计算结果。

![](img/c7f866b218336c088c7edc01b4426b8a_17.png)

层将不同类型的程序表示（如AST、LLVM IR）包装在**物化单元（Materialization Unit）**中。这些单元存储在JIT动态链接库（JITDylib）里。每个物化单元负责描述其包装的定义（即符号），并包含如何将这些定义**物化（Materialize）** 的逻辑。**物化责任（Materialization Responsibility）** 对象则负责跟踪这些定义，并在符号被成功物化或发生错误时通知JITDylib。

## 创建自定义层

![](img/c7f866b218336c088c7edc01b4426b8a_19.png)

![](img/c7f866b218336c088c7edc01b4426b8a_21.png)

要创建一个自定义层，我们需要完成以下两步：
1.  创建一个**物化单元**，用于物化我们特定的程序表示（例如命名空间或AST）。
2.  创建**层类**本身。虽然层类不需要继承特定基类，但按照ORC的惯例，它通常包含 `add`、`emit` 和 `getInterface` 这三个核心成员函数。

![](img/c7f866b218336c088c7edc01b4426b8a_23.png)

![](img/c7f866b218336c088c7edc01b4426b8a_25.png)

![](img/c7f866b218336c088c7edc01b4426b8a_27.png)

![](img/c7f866b218336c088c7edc01b4426b8a_29.png)

![](img/c7f866b218336c088c7edc01b4426b8a_31.png)

接下来，我们将通过代码示例来具体说明。我们有两个示例层：`NSLayer`（用于添加命名空间）和 `ASTLayer`（用于添加AST）。让我们先从更简单的 `NSLayer` 开始。

![](img/c7f866b218336c088c7edc01b4426b8a_33.png)

![](img/c7f866b218336c088c7edc01b4426b8a_35.png)

![](img/c7f866b218336c088c7edc01b4426b8a_37.png)

![](img/c7f866b218336c088c7edc01b4426b8a_39.png)

### 1. 命名空间层（NSLayer）

![](img/c7f866b218336c088c7edc01b4426b8a_41.png)

![](img/c7f866b218336c088c7edc01b4426b8a_43.png)

在我们的编译器中，一个命名空间（Namespace）包含一组函数和符号，通常对应一个源文件。首先，我们需要一个函数将命名空间编译成LLVM IR。ORC使用 `ThreadSafeModule` 来包装LLVM模块，以支持线程安全操作。

![](img/c7f866b218336c088c7edc01b4426b8a_45.png)

![](img/c7f866b218336c088c7edc01b4426b8a_47.png)

![](img/c7f866b218336c088c7edc01b4426b8a_49.png)

以下是 `NSLayer` 类的定义框架：
```cpp
class NSLayer {
public:
    NSLayer(SerContext& ctx, Layer& baseLayer, Mangle& mangler, DataLayout& dl);
    Error add(ResourceTrackerSP rt, StringRef nsName);
    Error emit(MaterializationResponsibility R, Namespace* ns);
    MaterializationUnit::Interface getInterface(Namespace* ns);
private:
    SerContext& Ctx;
    Layer& BaseLayer;
    Mangle& Mangler;
    DataLayout& DL;
};
```
*   **构造函数**：接收并保存上下文、下游层、名字修饰器和数据布局的引用。
*   **`add` 函数**：这是层的主要接口，用于向JIT引擎添加新的命名空间。它接收一个资源追踪器（`ResourceTracker`）和命名空间名称。
*   **`emit` 函数**：由物化单元调用，负责将命名空间编译成LLVM IR并传递给下游层。
*   **`getInterface` 函数**：用于生成物化单元的接口，描述该单元包含哪些符号。

![](img/c7f866b218336c088c7edc01b4426b8a_51.png)

#### `add` 函数详解

![](img/c7f866b218336c088c7edc01b4426b8a_53.png)

![](img/c7f866b218336c088c7edc01b4426b8a_55.png)

![](img/c7f866b218336c088c7edc01b4426b8a_57.png)

![](img/c7f866b218336c088c7edc01b4426b8a_58.png)

![](img/c7f866b218336c088c7edc01b4426b8a_60.png)

![](img/c7f866b218336c088c7edc01b4426b8a_62.png)

`add` 函数是向JIT引擎添加内容的入口。其工作流程如下：
1.  通过命名空间名称，从上下文（`SerContext`）中读取并创建对应的 `Namespace` 对象。这个过程可能涉及从磁盘读取文件、解析、语义分析等。
2.  使用传入的 `ResourceTracker` 获取关联的 `JITDylib`。
3.  创建一个自定义的物化单元 `NSMaterializationUnit`，并将当前层和刚创建的 `Namespace` 对象传递给它。
4.  调用 `JITDylib` 的 `define` 函数，将这个物化单元和资源追踪器一起注册进去。这样，JIT引擎就知道如何找到和物化这个命名空间包含的符号了。

![](img/c7f866b218336c088c7edc01b4426b8a_64.png)

#### 物化单元（NSMaterializationUnit）

![](img/c7f866b218336c088c7edc01b4426b8a_66.png)

![](img/c7f866b218336c088c7edc01b4426b8a_68.png)

![](img/c7f866b218336c088c7edc01b4426b8a_69.png)

![](img/c7f866b218336c088c7edc01b4426b8a_71.png)

![](img/c7f866b218336c088c7edc01b4426b8a_73.png)

![](img/c7f866b218336c088c7edc01b4426b8a_75.png)

![](img/c7f866b218336c088c7edc01b4426b8a_76.png)

![](img/c7f866b218336c088c7edc01b4426b8a_78.png)

物化单元继承自 `MaterializationUnit`，核心是实现 `materialize` 和 `discard` 函数。
```cpp
class NSMaterializationUnit : public MaterializationUnit {
public:
    NSMaterializationUnit(NSLayer& layer, Namespace* ns)
        : MaterializationUnit(layer.getInterface(ns)), Layer(layer), NS(ns) {}
    StringRef getName() const override { return "NSMaterializationUnit"; }
    void materialize(std::unique_ptr<MaterializationResponsibility> R) override {
        Layer.emit(std::move(R), NS);
    }
    void discard(const JITDylib& JD, const SymbolStringPtr& Sym) override {
        // 处理符号废弃逻辑，例如当函数被重写时
    }
private:
    NSLayer& Layer;
    Namespace* NS;
};
```
*   **`materialize`**：当JIT引擎需要该单元中的符号时，会调用此函数。它简单地调用所属层的 `emit` 函数。
*   **`discard`**：当符号不再需要或被覆盖时调用，用于清理资源。在初始实现中可能为空。
*   **构造函数**：调用层的 `getInterface` 函数来获取该命名空间暴露的符号列表，并传递给基类构造函数。

![](img/c7f866b218336c088c7edc01b4426b8a_80.png)

![](img/c7f866b218336c088c7edc01b4426b8a_82.png)

![](img/c7f866b218336c088c7edc01b4426b8a_83.png)

#### `emit` 函数与 `getInterface` 函数

![](img/c7f866b218336c088c7edc01b4426b8a_85.png)

![](img/c7f866b218336c088c7edc01b4426b8a_87.png)

![](img/c7f866b218336c088c7edc01b4426b8a_89.png)

![](img/c7f866b218336c088c7edc01b4426b8a_91.png)

![](img/c7f866b218336c088c7edc01b4426b8a_93.png)

![](img/c7f866b218336c088c7edc01b4426b8a_94.png)

![](img/c7f866b218336c088c7edc01b4426b8a_96.png)

![](img/c7f866b218336c088c7edc01b4426b8a_98.png)

![](img/c7f866b218336c088c7edc01b4426b8a_99.png)

![](img/c7f866b218336c088c7edc01b4426b8a_100.png)

*   **`emit` 函数**：接收物化责任和 `Namespace` 对象。它调用 `compileNS` 函数将命名空间编译成LLVM IR（一个 `ThreadSafeModule`），然后将这个模块连同物化责任一起传递给下游层（`BaseLayer`）的 `emit` 函数。
*   **`getInterface` 函数**：遍历命名空间的环境（存储全局定义的符号表），为每个顶级定义（如函数）创建一个符号。它使用 `Mangle` 对符号名进行修饰，并设置适当的标志（如可调用`Callable`、已导出`Exported`），最后返回一个包含这些符号的 `MaterializationUnit::Interface`。这个接口告诉JIT引擎该物化单元具体提供了哪些符号。

![](img/c7f866b218336c088c7edc01b4426b8a_102.png)

![](img/c7f866b218336c088c7edc01b4426b8a_104.png)

![](img/c7f866b218336c088c7edc01b4426b8a_105.png)

### 2. 抽象语法树层（ASTLayer）

![](img/c7f866b218336c088c7edc01b4426b8a_107.png)

![](img/c7f866b218336c088c7edc01b4426b8a_108.png)

![](img/c7f866b218336c088c7edc01b4426b8a_110.png)

`ASTLayer` 的结构与 `NSLayer` 非常相似，主要区别在于它处理的是单个AST节点，并且需要在特定命名空间的上下文中进行编译。

![](img/c7f866b218336c088c7edc01b4426b8a_112.png)

![](img/c7f866b218336c088c7edc01b4426b8a_114.png)

![](img/c7f866b218336c088c7edc01b4426b8a_116.png)

![](img/c7f866b218336c088c7edc01b4426b8a_118.png)

其核心函数 `compileAST` 接收一个命名空间和一个AST节点，将该AST添加到命名空间的AST树中，然后请求命名空间从特定偏移量开始编译（即只编译新加的AST，但可以引用上下文中已有的符号）。

![](img/c7f866b218336c088c7edc01b4426b8a_120.png)

![](img/c7f866b218336c088c7edc01b4426b8a_121.png)

![](img/c7f866b218336c088c7edc01b4426b8a_123.png)

![](img/c7f866b218336c088c7edc01b4426b8a_125.png)

![](img/c7f866b218336c088c7edc01b4426b8a_126.png)

`ASTLayer` 的 `add`、`emit`、`getInterface` 函数以及对应的 `ASTMaterializationUnit` 的实现模式与 `NSLayer` 完全一致，只是操作的对象从 `Namespace` 变成了 `AST` 节点。

![](img/c7f866b218336c088c7edc01b4426b8a_128.png)

![](img/c7f866b218336c088c7edc01b4426b8a_130.png)

![](img/c7f866b218336c088c7edc01b4426b8a_131.png)

![](img/c7f866b218336c088c7edc01b4426b8a_132.png)

![](img/c7f866b218336c088c7edc01b4426b8a_134.png)

![](img/c7f866b218336c088c7edc01b4426b8a_136.png)

### 在JIT引擎中集成自定义层

![](img/c7f866b218336c088c7edc01b4426b8a_138.png)

![](img/c7f866b218336c088c7edc01b4426b8a_139.png)

![](img/c7f866b218336c088c7edc01b4426b8a_141.png)

![](img/c7f866b218336c088c7edc01b4426b8a_142.png)

![](img/c7f866b218336c088c7edc01b4426b8a_143.png)

![](img/c7f866b218336c088c7edc01b4426b8a_145.png)

最后，我们看看如何在JIT引擎实例中组织这些层。以下是一个示例引擎的初始化片段：
```cpp
class ExampleJIT {
    ...
    ObjectLayer ObjLayer;
    CompileLayer CompileLayer;
    TransformLayer TransformLayer;
    NSLayer NSLayer;
    ASTLayer ASTLayer;
    ...
    ExampleJIT()
        : CompileLayer(...),
          TransformLayer(CompileLayer, ...),
          NSLayer(ctx, TransformLayer, mangler, dataLayout),
          ASTLayer(ctx, TransformLayer, mangler, dataLayout) {
        // 建立层级的上下游关系
        // NSLayer 和 ASTLayer 并行，下游是 TransformLayer
        // TransformLayer 下游是 CompileLayer
        // CompileLayer 下游是 ObjLayer
    }
};
```
在这个层次结构中，`NSLayer` 和 `ASTLayer` 作为最上层，它们的输出（LLVM IR）传递给 `TransformLayer`（可能进行一些IR转换），然后依次经过 `CompileLayer`（生成目标代码）和 `ObjectLayer`（处理目标文件），最终生成可执行代码。

![](img/c7f866b218336c088c7edc01b4426b8a_147.png)

![](img/c7f866b218336c088c7edc01b4426b8a_149.png)

## 总结

![](img/c7f866b218336c088c7edc01b4426b8a_151.png)

![](img/c7f866b218336c088c7edc01b4426b8a_152.png)

![](img/c7f866b218336c088c7edc01b4426b8a_154.png)

本节课中我们一起学习了如何为ORC JIT引擎创建自定义层。我们了解到：
1.  自定义层的核心是**物化单元**，它封装了特定程序表示（如命名空间、AST）及其物化逻辑。
2.  层本身是一个协调者，通过 `add` 方法接收输入，通过 `emit` 方法将处理结果传递给下游层，并通过 `getInterface` 方法声明其提供的符号。
3.  创建自定义层的过程清晰且模块化，这使得扩展JIT引擎以支持新的程序表示形式变得非常简单。

![](img/c7f866b218336c088c7edc01b4426b8a_156.png)

虽然我们在初始的编译器框架中使用了更简单的设计，但理解如何构建这些自定义层为我们未来增强JIT引擎的功能（例如支持增量编译、字节码加载等）打下了坚实的基础。ORC层的抽象设计非常精妙，它将复杂的JIT编译过程分解为一系列简单、可组合的步骤。