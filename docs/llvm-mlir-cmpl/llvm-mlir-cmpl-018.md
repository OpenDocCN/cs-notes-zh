# 018：JIT引擎实现（第一部分）🚀

在本节课中，我们将学习如何为Serin语言实现一个基础的JIT引擎。我们将这个引擎命名为“Halley”。本节将重点介绍其整体架构、核心类的设计以及如何创建引擎实例、添加命名空间和AST。

## 概述

经过前几节对JIT基础概念的讨论，本节我们将把理论付诸实践，构建一个可工作的JIT引擎实现。虽然这是最简实现，但足以将编译器的各个部分连接起来。我们的实现包装了LLVM的`LLJIT`和`LLLazyJIT`，并包含对象缓存层。

![](img/41443cc609cfde8da0940c468d78d542_1.png)

![](img/41443cc609cfde8da0940c468d78d542_2.png)

## Halley引擎设计

![](img/41443cc609cfde8da0940c468d78d542_4.png)

![](img/41443cc609cfde8da0940c468d78d542_5.png)

![](img/41443cc609cfde8da0940c468d78d542_7.png)

我们的JIT引擎实现围绕`Halley`类展开。它包装了LLVM的JIT基础设施，并提供了两种操作模式。

![](img/41443cc609cfde8da0940c468d78d542_9.png)

![](img/41443cc609cfde8da0940c468d78d542_11.png)

### 核心类型定义

首先，我们定义了一些核心类型，用于错误处理和函数指针包装。LLVM使用`llvm::Expected`类型来处理可能出错的操作。

![](img/41443cc609cfde8da0940c468d78d542_13.png)

```cpp
using MaybeJit = llvm::Expected<std::unique_ptr<Halley>>;
using MaybeJitPtr = llvm::Expected<JitPtr>;
```

![](img/41443cc609cfde8da0940c468d78d542_15.png)

### 对象缓存层

为了实现对象缓存，我们继承了LLVM的`llvm::ObjectCache`类，并重写了两个关键函数。

![](img/41443cc609cfde8da0940c468d78d542_17.png)

![](img/41443cc609cfde8da0940c468d78d542_18.png)

![](img/41443cc609cfde8da0940c468d78d542_19.png)

以下是需要重写的函数：
*   `notifyObjectCompiled`: 当模块编译完成并生成对象缓冲区时，此函数被调用以缓存该缓冲区。
*   `getObject`: 当需要某个模块的已编译对象时，此函数被调用以从缓存中查询并返回。

![](img/41443cc609cfde8da0940c468d78d542_21.png)

![](img/41443cc609cfde8da0940c468d78d542_23.png)

![](img/41443cc609cfde8da0940c468d78d542_25.png)

缓存存储在一个`std::map`中，键是模块标识字符串，值是`llvm::MemoryBuffer`的唯一指针。

![](img/41443cc609cfde8da0940c468d78d542_27.png)

![](img/41443cc609cfde8da0940c468d78d542_29.png)

### Halley 类

![](img/41443cc609cfde8da0940c468d78d542_31.png)

`Halley`类是我们的JIT引擎核心。它目前直接包装了`llvm::JIT`基类指针，这虽然可行，但限制了我们对`LLLazyJIT`特有功能的使用。未来我们需要一个更好的包装类型。

![](img/41443cc609cfde8da0940c468d78d542_33.png)

![](img/41443cc609cfde8da0940c468d78d542_34.png)

![](img/41443cc609cfde8da0940c468d78d542_36.png)

![](img/41443cc609cfde8da0940c468d78d542_38.png)

类的主要属性包括：
*   `engine`: 指向LLVM JIT引擎基类的唯一指针。
*   `cache`: 我们自定义对象缓存层的唯一指针。
*   `jit_target_machine_builder`: 用于创建目标机器的数据结构。
*   `data_layout`: 对数据布局的引用。
*   `active_ns`: 当前执行所在的活跃命名空间的共享指针。
*   `lazy_mode`: 指示当前是否处于惰性（延迟）编译模式的标志。

![](img/41443cc609cfde8da0940c468d78d542_40.png)

![](img/41443cc609cfde8da0940c468d78d542_42.png)

![](img/41443cc609cfde8da0940c468d78d542_44.png)

![](img/41443cc609cfde8da0940c468d78d542_46.png)

构造函数接收上下文、目标机器构建器和数据布局。但我们通常使用静态的`make`函数来创建实例。

![](img/41443cc609cfde8da0940c468d78d542_48.png)

![](img/41443cc609cfde8da0940c468d78d542_49.png)

![](img/41443cc609cfde8da0940c468d78d542_50.png)

![](img/41443cc609cfde8da0940c468d78d542_51.png)

重要的成员函数有：
*   `lookup`: 用于在已编译代码中查找符号地址。
*   `addNS`: 向引擎添加一个完整的命名空间进行编译。
*   `addAST`: 向当前活跃命名空间添加一个AST（抽象语法树）进行增量编译。
*   `dumpToObjectFile`: 用于调试，将编译后的对象数据转储到文件。

![](img/41443cc609cfde8da0940c468d78d542_53.png)

![](img/41443cc609cfde8da0940c468d78d542_55.png)

![](img/41443cc609cfde8da0940c468d78d542_57.png)

## 实现细节

![](img/41443cc609cfde8da0940c468d78d542_59.png)

![](img/41443cc609cfde8da0940c468d78d542_61.png)

![](img/41443cc609cfde8da0940c468d78d542_63.png)

现在，让我们深入`lib/serin/jit/halley.cpp`文件，看看这些功能是如何实现的。

![](img/41443cc609cfde8da0940c468d78d542_65.png)

![](img/41443cc609cfde8da0940c468d78d542_66.png)

![](img/41443cc609cfde8da0940c468d78d542_67.png)

![](img/41443cc609cfde8da0940c468d78d542_68.png)

![](img/41443cc609cfde8da0940c468d78d542_70.png)

![](img/41443cc609cfde8da0940c468d78d542_71.png)

![](img/41443cc609cfde8da0940c468d78d542_73.png)

### 创建引擎实例

`makeHalley`函数是创建`Halley`实例的入口点。它根据Serin上下文中的配置（如目标三元组）来设置引擎。

创建过程主要步骤如下：
1.  从上下文获取目标三元组，创建`JITTargetMachineBuilder`。
2.  调用`Halley::make`静态函数，传入构建器和上下文。
3.  在`make`函数内部，获取目标数据布局。
4.  创建`Halley`实例。
5.  设置ORC（On-Request Compilation）层：包括对象链接层和编译层。
    *   对象链接层使用`RTDyldObjectLinkingLayer`和`SectionMemoryManager`。
    *   编译层使用`IRCompileLayer`，并根据上下文设置优化级别。
6.  根据`lazy_mode`标志，创建`LLLazyJIT`（惰性模式）或`LLJIT`（急切模式）引擎实例。
7.  将引擎设置到`Halley`实例中。
8.  向引擎的主JIT动态库添加生成器。
9.  返回创建好的`Halley`实例。

![](img/41443cc609cfde8da0940c468d78d542_75.png)

![](img/41443cc609cfde8da0940c468d78d542_76.png)

![](img/41443cc609cfde8da0940c468d78d542_78.png)

### 添加命名空间

![](img/41443cc609cfde8da0940c468d78d542_80.png)

`addNS`函数负责将一个完整的命名空间添加到JIT引擎中进行编译。

![](img/41443cc609cfde8da0940c468d78d542_82.png)

![](img/41443cc609cfde8da0940c468d78d542_83.png)

![](img/41443cc609cfde8da0940c468d78d542_85.png)

其工作流程如下：
1.  根据命名空间名称和当前JIT动态库计数，生成一个唯一的JIT动态库名称（例如`user1`， `user2`）。
2.  为这个命名空间创建一个新的JIT动态库。
3.  将命名空间编译为目标机器代码（LLVM IR）。
4.  将生成的LLVM模块包装成线程安全模块。
5.  **打包函数参数**：这是一个关键步骤，它遍历模块中的所有函数，将它们包装进一个具有统一调用接口的函数中。这简化了后续的符号查找和调用。我们将在下一节详细讨论。
6.  使用`addIRModule`方法将包装后的模块添加到对应的JIT动态库中。

### 添加AST

![](img/41443cc609cfde8da0940c468d78d542_87.png)

![](img/41443cc609cfde8da0940c468d78d542_89.png)

`addAST`函数用于向当前活跃的命名空间增量地添加AST。这在交互式REPL环境中非常有用。

其工作流程如下：
1.  获取当前活跃的命名空间。
2.  将新的AST追加到该命名空间的AST树中。
3.  计算新AST在树中的起始偏移量。
4.  从该偏移量开始，编译命名空间树中新增的部分（而无需重新编译整个树）。
5.  同样，将编译得到的模块进行“函数参数打包”处理。
6.  获取该活跃命名空间对应的最新JIT动态库。
7.  将打包后的模块添加到这个动态库中。

![](img/41443cc609cfde8da0940c468d78d542_91.png)

![](img/41443cc609cfde8da0940c468d78d542_92.png)

### 符号查找

![](img/41443cc609cfde8da0940c468d78d542_94.png)

![](img/41443cc609cfde8da0940c468d78d542_95.png)

`lookup`函数是调用已编译代码的入口。它根据Serin语言中的符号表达式来查找对应的函数地址。

![](img/41443cc609cfde8da0940c468d78d542_97.png)

![](img/41443cc609cfde8da0940c468d78d542_99.png)

查找过程如下：
1.  从符号中解析出它所属的命名空间名称。
2.  从上下文中获取该命名空间对象。
3.  获取该命名空间对应的最新JIT动态库。
4.  由于我们进行了“函数参数打包”，需要根据原始符号名生成打包后的函数名。
5.  在JIT动态库中查找这个打包后的函数名，获取其地址。
6.  将地址转换为统一的函数指针类型并返回。调用者可以使用这个指针来执行编译后的代码。

![](img/41443cc609cfde8da0940c468d78d542_101.png)

![](img/41443cc609cfde8da0940c468d78d542_102.png)

![](img/41443cc609cfde8da0940c468d78d542_103.png)

![](img/41443cc609cfde8da0940c468d78d542_105.png)

## 总结

![](img/41443cc609cfde8da0940c468d78d542_107.png)

本节课我们一起学习了Serin编译器JIT引擎“Halley”的第一部分实现。我们了解了它的整体设计，包括对象缓存层和核心的`Halley`类。我们详细探讨了如何创建引擎实例，以及如何通过`addNS`和`addAST`函数向引擎添加代码。最后，我们看到了如何通过`lookup`函数来查找并获取已编译函数的地址，为实际调用做好准备。

![](img/41443cc609cfde8da0940c468d78d542_109.png)

![](img/41443cc609cfde8da0940c468d78d542_110.png)

![](img/41443cc609cfde8da0940c468d78d542_112.png)

![](img/41443cc609cfde8da0940c468d78d542_114.png)

当前实现是一个功能可用的最小集合，它成功地将LLVM的JIT功能与我们的编译器前端连接起来。在下一节课中，我们将深入探讨“函数参数打包”这个关键技术的实现细节，它是实现统一函数调用接口的核心。