# 013：源码管理器 🗂️

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_1.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_3.png)

在本节课中，我们将学习如何为我们的编译器实现一个源码管理器。源码管理器负责加载、管理和跟踪编译器处理的所有源代码文件。我们将了解为什么需要它，并查看一个基于LLVM源码管理器设计的简化版本。

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_5.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_7.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_9.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_11.png)

## 概述

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_13.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_15.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_17.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_18.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_20.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_22.png)

上一节我们介绍了代码生成，并成功将Serene代码编译成了可执行文件。本节中，我们来看看编译器前端的一个重要组件——源码管理器。它的核心作用是统一管理所有源代码文件，包括从文件系统加载、处理导入关系以及为后续的解析和语义分析提供数据。

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_24.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_26.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_28.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_30.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_31.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_33.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_35.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_36.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_38.png)

## LLVM源码管理器简介

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_40.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_42.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_43.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_44.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_46.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_48.png)

LLVM自带一个源码管理器，但其设计主要服务于Clang编译器，与C/C++语言特性（如`#include`预处理指令）深度绑定。因此，对于我们的Serene语言前端，直接使用它不够灵活。

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_50.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_52.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_54.png)

LLVM源码管理器的主要组件包括：
*   **`SourceManager`类**：管理一个`SrcBuffer`的向量。
*   **`SrcBuffer`结构体**：封装一个内存缓冲区（`MemoryBuffer`），存储文件内容，并提供一些辅助功能，如按行分割文本、根据行号或指针获取位置。
*   **诊断处理器**：允许前端注册一个回调函数来处理源码管理器报告的错误。
*   **包含目录（Include Directories）**：用于查找头文件的路径列表。

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_56.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_57.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_59.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_61.png)

由于其与Clang的强关联性，我们决定参考其设计，实现一个更适合Serene的版本。

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_63.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_65.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_67.png)

## 我们的源码管理器实现

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_69.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_71.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_72.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_73.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_75.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_76.png)

我们的源码管理器基于LLVM版本进行了简化和定制，移除了不必要的通用性，并集成了我们自己的错误处理机制。

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_78.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_80.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_82.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_84.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_85.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_86.png)

### 核心数据结构

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_88.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_89.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_91.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_93.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_95.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_96.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_98.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_100.png)

以下是我们的`SrcBuffer`结构体的关键部分：

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_102.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_104.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_106.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_107.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_109.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_110.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_112.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_114.png)

```cpp
struct SrcBuffer {
  std::unique_ptr<MemoryBuffer> buffer;
  std::vector<const char *> line_starts; // 行起始位置
  llvm::Optional<LocationRange> import_loc; // 导入位置（替换了LLVM的include_loc）
  // ... 其他辅助方法，如 getLineNumber
};
```

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_116.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_117.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_118.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_120.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_121.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_123.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_125.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_127.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_128.png)

我们的`SourceManager`类核心成员如下：

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_130.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_131.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_133.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_134.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_136.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_138.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_140.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_142.png)

```cpp
class SourceManager {
  std::vector<SrcBuffer> buffers; // 缓冲区列表
  llvm::StringMap<unsigned> ns_table; // 命名空间名到缓冲区ID的映射
  std::vector<std::string> load_paths; // 文件加载路径（类似include目录）
  // ... 移除了通用的诊断处理器
};
```

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_144.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_145.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_147.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_149.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_151.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_152.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_154.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_156.png)

### 主要功能与方法

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_158.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_160.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_162.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_164.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_166.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_167.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_169.png)

以下是源码管理器提供的主要功能：

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_171.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_172.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_174.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_175.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_177.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_178.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_180.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_182.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_184.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_186.png)

*   **添加加载路径**：通过`addLoadPath`方法，用户可以指定查找`.serene`文件的目录。
*   **查找并读取命名空间**：这是最重要的方法`readNamespace`。它接收一个命名空间名称（如`serene.example`），将其转换为文件路径（如`serene/example.serene`），然后在`load_paths`中查找该文件。
*   **管理缓冲区**：找到文件后，将其内容读入一个新的`SrcBuffer`，并分配一个缓冲区ID（从1开始）。同时，在`ns_table`中记录命名空间与缓冲区ID的映射。
*   **错误处理**：如果文件未找到或读取失败，方法会返回一个`ErrorTree`类型的错误，而不是抛出异常。这与我们编译器其他部分的错误处理策略一致。

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_188.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_189.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_191.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_193.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_195.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_197.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_198.png)

### 工作流程解析

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_199.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_201.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_203.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_204.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_206.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_208.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_210.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_212.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_214.png)

`readNamespace`函数的工作流程可以概括为以下几个步骤：

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_216.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_218.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_219.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_221.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_223.png)

1.  **路径转换与查找**：调用`findFileInLoadPaths`，将命名空间名转换为文件路径，并在加载路径中顺序查找。
2.  **文件读取**：找到文件后，使用LLVM的`MemoryBuffer`机制将文件内容加载到内存。
3.  **创建缓冲区**：将内存缓冲区添加到`buffers`向量中，并获取其ID。
4.  **记录映射**：在`ns_table`中建立命名空间名到缓冲区ID的映射。
5.  **调用解析器**：将缓冲区内容传递给解析器（Reader），生成抽象语法树（AST）。
6.  **语义分析与树扩展**：对AST运行语义分析器（Semantic Analyzer），如果成功，则调用命名空间的`expandTree`方法，将分析后的AST节点加入到该命名空间的AST节点列表中。
7.  **返回结果**：最终返回一个指向该命名空间对象的共享指针。

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_225.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_226.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_227.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_228.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_229.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_231.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_233.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_235.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_237.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_238.png)

## 与编译器其他部分的集成

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_240.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_242.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_244.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_246.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_248.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_250.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_252.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_254.png)

为了让源码管理器生效，我们需要对现有代码做一些调整：

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_256.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_257.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_259.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_260.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_261.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_263.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_265.png)

*   **上下文集成**：`Context`类现在持有一个`SourceManager`实例。
*   **解析器适配**：`Reader`的`read`函数被重载，现在可以接受一个`MemoryBuffer`的引用作为输入，从而直接从源码管理器的缓冲区中读取内容。
*   **主入口点更改**：编译器的主入口点（如`serene.cpp`）不再手动处理文件加载。它现在直接调用`context.getSourceManager().readNamespace(...)`来启动编译流程。

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_267.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_269.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_271.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_272.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_274.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_275.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_277.png)

## 总结

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_279.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_280.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_281.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_283.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_285.png)

![](img/eeac6f665f9b88d3ccd50e726b93f9a2_287.png)

本节课我们一起学习了源码管理器（Source Manager）的概念与实现。我们了解到，虽然LLVM提供了相关的组件，但为了更好的适配性，我们基于其思想实现了一个定制版本。我们的源码管理器核心职责是管理源代码文件的生命周期：根据命名空间名定位文件、加载内容、维护文件缓存以及处理导入关系。通过集成源码管理器，我们的编译器前端结构变得更加清晰和模块化，为后续支持多文件编译和更复杂的模块系统打下了基础。下一节，我们将开始探讨即时编译（JIT）的基础概念，为最终实现Serene的JIT功能做准备。