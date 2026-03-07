# 015：LLVM ORC JIT 🚀

在本节课中，我们将要学习LLVM ORC JIT API。ORC（On-Request Compilation）是LLVM中用于即时编译（JIT）的现代、灵活的API，它取代了旧的MCJIT。我们将通过理解其核心概念和查看示例代码，来学习如何使用它构建一个简单的JIT引擎。

## 概述与背景

在过去的几个月里，我一直在尝试使用不同的方法构建一个最小化的JIT引擎。最终，我成功实现了一个非常精简的JIT引擎。它的主要功能是能够编译命名空间。目前，它在插入命名空间时会立即进行编译（即时编译），虽然这并非最佳方案，但作为一个最小化实现是可以接受的。未来我计划对其进行改进。

![](img/8bb683619a38f7c097464957d6c7506a_1.png)

![](img/8bb683619a38f7c097464957d6c7506a_3.png)

我还实现了重新加载命名空间的功能。例如，在一个REPL环境中，用户可能要求重新加载某个命名空间，引擎需要能够管理命名空间的不同版本，因为可能有些代码还在引用旧版本。

![](img/8bb683619a38f7c097464957d6c7506a_5.png)

在开发过程中，我经常需要考虑Serene语言的各种规范细节。因此，现在是时候开始正式编写Serene语言的规范了。我计划以Scheme语言规范为基础，保留我喜欢的部分，添加缺失的功能，并移除不喜欢的部分，最终形成Serene的规范。

![](img/8bb683619a38f7c097464957d6c7506a_7.png)

![](img/8bb683619a38f7c097464957d6c7506a_9.png)

在深入JIT引擎的实现之前，我们需要更好地理解ORCv2。

## ORC JIT 核心概念 📚

ORC JIT的设计围绕一系列核心概念。理解这些术语对于阅读文档和示例代码至关重要。以下是几个关键概念：

![](img/8bb683619a38f7c097464957d6c7506a_11.png)

*   **执行会话**：一个`ExecutionSession`代表一个正在运行的JIT程序会话。它包含了JIT动态链接库、错误报告以及内存化（memoization）等所有相关组件。你可以将其视为JIT引擎的运行实例。
*   **JIT地址**：`JITTargetAddress`是指向已编译代码内存地址的简单包装类型，本质上是一个指针。
*   **JIT动态链接库**：`JITDylib`类代表一个包含JIT代码的单元，类似于动态链接库。在我们的场景中，一个命名空间编译后通常会对应一个`JITDylib`。它本质上是一个符号表，记录了编译代码中的符号（如函数名）及其在内存中的位置。
*   **物化单元**：`MaterializationUnit`是ORC实现惰性（延迟）编译的关键。当我们向JIT引擎添加代码（如一个LLVM模块）时，我们可以不立即编译它，而是创建一个`MaterializationUnit`来“持有”这个模块的定义。只有当后续真正需要查找（lookup）或调用某个符号时，引擎才会要求该单元“物化”（即编译）对应的代码并放入内存。
*   **物化责任**：`MaterializationResponsibility`用于跟踪`MaterializationUnit`。它在`JITDylib`和`MaterializationUnit`之间充当桥梁，负责通知双方物化过程是成功还是失败。

![](img/8bb683619a38f7c097464957d6c7506a_13.png)

![](img/8bb683619a38f7c097464957d6c7506a_15.png)

`JITDylib`、`MaterializationUnit`和`MaterializationResponsibility`这三个概念的组合非常强大。默认情况下，使用它们可以实现“按需编译”，即在符号查找时进行编译。ORC甚至提供了更惰性的方式，可以将编译延迟到第一次调用函数时才进行。

![](img/8bb683619a38f7c097464957d6c7506a_17.png)

*   **内存管理器**：`MemoryManager`负责JIT引擎的内存管理，如分配和释放用于存放编译代码的内存。ORC默认提供了几种内存管理器，例如`SectionMemoryManager`，它能满足大多数用例。
*   **层**：ORC的整个设计都围绕“层”的概念。一个JIT引擎是由多个层连接而成的管道。代码从一端输入，经过各个层的处理（如编译、链接、转换），最终在另一端产生结果（如可执行代码）。这种设计极其灵活和强大。
*   **资源追踪器**：`ResourceTracker`是ORC用于追踪已编译代码资源的答案。当你向JIT添加一个模块时，可以用它来追踪。你可以通过它来移除已编译的代码。
*   **线程安全模块**：`ThreadSafeModule`是普通LLVM模块的包装器，它提供了线程安全的访问方式。在与ORC JIT交互时，我们主要使用`ThreadSafeModule`。

## ORC 高级API与使用方式 🛠️

ORC提供了基于层的设计，允许我们构建自己的JIT引擎。同时，它也内置了两个可以直接使用的JIT引擎：`LLJIT` 和 `LLLazyJIT`。

![](img/8bb683619a38f7c097464957d6c7506a_19.png)

*   **LLJIT**：一个开箱即用的JIT引擎，使用ORC API构建，可以进行一定程度的定制。它不是完全惰性的，在查找符号时就会编译该符号对应的代码。
*   **LLLazyJIT**：继承自`LLJIT`，但更加惰性。它直到第一次调用函数时，才会编译该函数的代码。

![](img/8bb683619a38f7c097464957d6c7506a_21.png)

我们有两种主要方式来创建JIT引擎：

![](img/8bb683619a38f7c097464957d6c7506a_23.png)

1.  包装`LLJIT`或`LLLazyJIT`。这是我们当前实现所采用的方式。
2.  直接使用ORC API从头构建自己的JIT引擎。我也在仓库中尝试了这种方式。

![](img/8bb683619a38f7c097464957d6c7506a_25.png)

![](img/8bb683619a38f7c097464957d6c7506a_27.png)

![](img/8bb683619a38f7c097464957d6c7506a_28.png)

![](img/8bb683619a38f7c097464957d6c7506a_30.png)

![](img/8bb683619a38f7c097464957d6c7506a_31.png)

![](img/8bb683619a38f7c097464957d6c7506a_32.png)

未来，我们可能会结合这两种方式。

![](img/8bb683619a38f7c097464957d6c7506a_34.png)

## 代码示例解析 💻

![](img/8bb683619a38f7c097464957d6c7506a_36.png)

![](img/8bb683619a38f7c097464957d6c7506a_38.png)

![](img/8bb683619a38f7c097464957d6c7506a_40.png)

现在，让我们通过LLVM源码中的例子来看看`LLJIT`的基本用法。

![](img/8bb683619a38f7c097464957d6c7506a_42.png)

![](img/8bb683619a38f7c097464957d6c7506a_44.png)

![](img/8bb683619a38f7c097464957d6c7506a_46.png)

### 示例1：最简单的LLJIT使用

![](img/8bb683619a38f7c097464957d6c7506a_48.png)

以下是一个使用`LLJIT`编译并运行一个简单加法函数的例子。

![](img/8bb683619a38f7c097464957d6c7506a_50.png)

![](img/8bb683619a38f7c097464957d6c7506a_52.png)

![](img/8bb683619a38f7c097464957d6c7506a_54.png)

![](img/8bb683619a38f7c097464957d6c7506a_56.png)

![](img/8bb683619a38f7c097464957d6c7506a_58.png)

![](img/8bb683619a38f7c097464957d6c7506a_60.png)

![](img/8bb683619a38f7c097464957d6c7506a_62.png)

```cpp
// 创建一个简单的LLVM IR模块，其中包含一个`add1`函数
ThreadSafeModule createDemoModule() {
  // ... 创建模块和函数的LLVM IR代码 ...
  auto M = std::make_unique<Module>("test", Ctx);
  // ... 构建函数体：`return argument + 1` ...
  return ThreadSafeModule(std::move(M), std::make_unique<LLVMContext>());
}

![](img/8bb683619a38f7c097464957d6c7506a_64.png)

![](img/8bb683619a38f7c097464957d6c7506a_65.png)

![](img/8bb683619a38f7c097464957d6c7506a_66.png)

![](img/8bb683619a38f7c097464957d6c7506a_67.png)

![](img/8bb683619a38f7c097464957d6c7506a_68.png)

![](img/8bb683619a38f7c097464957d6c7506a_70.png)

![](img/8bb683619a38f7c097464957d6c7506a_72.png)

![](img/8bb683619a38f7c097464957d6c7506a_74.png)

int main() {
  // 初始化LLVM
  InitializeNativeTarget();
  InitializeNativeTargetAsmPrinter();

  // 创建LLJIT实例
  auto JIT = LLJITBuilder().create();
  if (!JIT) { /* 处理错误 */ }

  // 创建演示模块
  auto M = createDemoModule();

  // 将模块添加到JIT引擎中
  if (auto Err = JIT->addIRModule(std::move(M))) { /* 处理错误 */ }

  // 查找`add1`符号
  auto Add1Sym = JIT->lookup("add1");
  if (!Add1Sym) { /* 处理错误 */ }

  // 获取函数地址并转换为函数指针
  auto *Add1 = (int (*)(int))Add1Sym->getAddress();

  // 调用JIT编译的函数
  int Result = Add1(42);
  printf("Result: %d\n", Result); // 输出：Result: 43

  return 0;
}
```

![](img/8bb683619a38f7c097464957d6c7506a_75.png)

![](img/8bb683619a38f7c097464957d6c7506a_77.png)

![](img/8bb683619a38f7c097464957d6c7506a_79.png)

![](img/8bb683619a38f7c097464957d6c7506a_80.png)

![](img/8bb683619a38f7c097464957d6c7506a_82.png)

这段代码清晰地展示了使用`LLJIT`的流程：
1.  初始化LLVM。
2.  使用`LLJITBuilder`创建JIT实例。
3.  创建包含目标代码的`ThreadSafeModule`。
4.  通过`addIRModule`将模块加入引擎。
5.  通过`lookup`查找符号，这会触发编译。
6.  获取函数地址，进行类型转换后调用。

![](img/8bb683619a38f7c097464957d6c7506a_84.png)

![](img/8bb683619a38f7c097464957d6c7506a_86.png)

![](img/8bb683619a38f7c097464957d6c7506a_88.png)

![](img/8bb683619a38f7c097464957d6c7506a_90.png)

![](img/8bb683619a38f7c097464957d6c7506a_92.png)

`LLJITBuilder`提供了多种成员函数，允许我们定制JIT引擎，例如设置目标机器、数据布局、自定义编译层或链接层等。

![](img/8bb683619a38f7c097464957d6c7506a_94.png)

![](img/8bb683619a38f7c097464957d6c7506a_95.png)

![](img/8bb683619a38f7c097464957d6c7506a_97.png)

![](img/8bb683619a38f7c097464957d6c7506a_98.png)

![](img/8bb683619a38f7c097464957d6c7506a_100.png)

![](img/8bb683619a38f7c097464957d6c7506a_102.png)

### 示例2：使用转换层转储目标文件

![](img/8bb683619a38f7c097464957d6c7506a_104.png)

![](img/8bb683619a38f7c097464957d6c7506a_106.png)

![](img/8bb683619a38f7c097464957d6c7506a_108.png)

这个例子展示了如何在编译过程中介入，将生成的目标代码转储到文件中。

![](img/8bb683619a38f7c097464957d6c7506a_110.png)

![](img/8bb683619a38f7c097464957d6c7506a_112.png)

![](img/8bb683619a38f7c097464957d6c7506a_113.png)

![](img/8bb683619a38f7c097464957d6c7506a_114.png)

```cpp
int main() {
  // ... 初始化与创建JIT ...

  auto &JT = *JIT;

  // 获取JIT引擎中的对象转换层
  auto *ObjLinkingLayer = JT.getObjectLinkingLayer();

  // 向转换层添加一个回调函数，在目标代码生成后将其写入文件
  ObjLinkingLayer->setTransform(
      [](std::unique_ptr<MemoryBuffer> Obj) -> std::unique_ptr<MemoryBuffer> {
        // 将Obj中的内容写入文件 `output.o`
        // ...
        return std::move(Obj); // 将缓冲区返回给下一层
      });

  // ... 添加模块、查找符号、调用函数 ...
}
```
这里的关键是`getObjectLinkingLayer()`和`setTransform`。转换层允许我们在编译流水线的特定阶段插入自定义逻辑，这充分体现了ORC层的强大和灵活性。

![](img/8bb683619a38f7c097464957d6c7506a_116.png)

![](img/8bb683619a38f7c097464957d6c7506a_117.png)

![](img/8bb683619a38f7c097464957d6c7506a_118.png)

![](img/8bb683619a38f7c097464957d6c7506a_120.png)

![](img/8bb683619a38f7c097464957d6c7506a_122.png)

![](img/8bb683619a38f7c097464957d6c7506a_124.png)

### 示例3：定义绝对符号

![](img/8bb683619a38f7c097464957d6c7506a_126.png)

有时，JIT编译的代码需要与宿主程序（C++代码）中定义的变量或函数交互。这可以通过定义“绝对符号”来实现。

```cpp
int main() {
  // ... 初始化与创建JIT ...

  // 在C++程序中定义的变量
  bool InitializerRunFlag = false;
  bool InitializerRan = false;

  // 获取主JIT动态链接库
  auto &MainJD = JIT->getMainJITDylib();

  // 将C++变量的地址定义为JIT中的符号
  // 1. 定义 `InitializerRunFlag` 符号
  if (auto Err = MainJD.define(
          absoluteSymbols({{Mangle("InitializerRunFlag"),
                            JITEvaluatedSymbol::fromPointer(&InitializerRunFlag)}}))) {
    /* 处理错误 */
  }

  // 2. 定义 `InitializerRan` 符号
  if (auto Err = MainJD.define(
          absoluteSymbols({{Mangle("InitializerRan"),
                            JITEvaluatedSymbol::fromPointer(&InitializerRan)}}))) {
    /* 处理错误 */
  }

  // ... 添加包含引用这些符号的IR模块 ...
  // JIT编译的代码现在可以通过这些符号名访问到C++变量`InitializerRunFlag`和`InitializerRan`
}
```
这种方法非常有用。例如，在实现Serene的标准库时，部分功能可以用高效的C++实现，然后通过定义绝对符号的方式暴露给JIT编译的Serene代码使用，而无需将其编译为LLVM IR。

![](img/8bb683619a38f7c097464957d6c7506a_128.png)

![](img/8bb683619a38f7c097464957d6c7506a_130.png)

## 总结

![](img/8bb683619a38f7c097464957d6c7506a_132.png)

![](img/8bb683619a38f7c097464957d6c7506a_133.png)

![](img/8bb683619a38f7c097464957d6c7506a_135.png)

本节课我们一起学习了LLVM ORC JIT的基础知识。我们首先了解了ORC JIT的核心概念，包括`ExecutionSession`、`JITDylib`、`MaterializationUnit`、层（Layers）等。然后，我们探讨了ORC提供的两种高级JIT引擎`LLJIT`和`LLLazyJIT`，以及两种构建JIT的方式。最后，我们通过分析三个LLVM源码中的示例，具体学习了如何使用`LLJIT`添加模块、查找符号、调用函数，以及如何利用转换层和绝对符号实现更高级的功能。

![](img/8bb683619a38f7c097464957d6c7506a_137.png)

![](img/8bb683619a38f7c097464957d6c7506a_139.png)

ORC JIT的设计非常出色，它将成为我们编译器的重要组成部分。在接下来的课程中，我们将继续深入ORC，并逐步将其集成到Serene编译器中。