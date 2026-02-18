# 46：第35讲 - 虚拟内存性能与I/O设备 🚀

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_0.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_1.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_3.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_5.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_7.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_9.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_11.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_13.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_15.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_17.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_19.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_21.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_22.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_24.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_26.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_28.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_30.png)

在本节课中，我们将要学习如何评估虚拟内存系统的性能，并了解计算机如何与各种输入/输出设备进行交互。我们将从缓存与虚拟内存的对比开始，逐步深入到I/O设备的连接机制、数据传输方式，并最终理解现代计算机如何通过网络进行通信。

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_32.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_34.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_36.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_38.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_40.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_42.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_44.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_46.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_48.png)

## 虚拟内存性能评估 🔍

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_50.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_52.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_54.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_56.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_57.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_59.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_61.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_63.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_65.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_67.png)

上一节我们介绍了虚拟内存系统的工作原理和实现。本节中，我们来看看如何评估它的性能。评估虚拟内存性能的原则与评估缓存性能的原则相同。

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_69.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_71.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_73.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_75.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_77.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_79.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_81.png)

以下是缓存系统与虚拟内存系统的关键参数对比：

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_83.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_85.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_87.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_89.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_91.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_93.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_95.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_97.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_99.png)

*   **缓存块/行** 对应于虚拟内存系统中的 **页面**。
*   **缓存未命中** 对应于 **页面错误**。
*   缓存块大小通常为32到64字节，而典型页面大小为KB级别，有时更小或更大（如8到16KiB），但通常处理4KiB页面。
*   缓存中的放置策略可以是直接映射、组相联或全相联。在虚拟内存系统中，页面放置通常是 **全相联** 的。
*   缓存中的替换策略可以是最近最少使用或随机等。在虚拟内存系统中，通常希望使用 **最近最少使用** 策略，但有时会用先进先出或随机策略来近似。
*   缓存可以选用直写或回写策略。在虚拟内存系统中，我们只使用 **回写**，因为写入磁盘的惩罚非常高。

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_101.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_103.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_105.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_107.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_109.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_111.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_113.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_115.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_117.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_118.png)

### 性能计算

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_120.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_122.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_123.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_125.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_127.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_129.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_131.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_132.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_134.png)

虚拟内存是位于主存之下的一个内存层级。在我们之前的计算中，一切停止在主存级别。现在，虚拟内存通过分页将DRAM扩展到了磁盘中。

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_136.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_138.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_140.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_142.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_144.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_146.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_148.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_149.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_151.png)

因此，每条指令的周期和平均内存访问时间的计算方式将被沿用，但这次我们将主存视为某种中级缓存。我们需要检查缓存命中/未命中，然后可能命中RAM或最终访问磁盘。

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_153.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_155.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_157.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_159.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_161.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_163.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_165.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_167.png)

以下是我们关心的一些参数：

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_169.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_170.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_172.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_174.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_176.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_178.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_180.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_181.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_183.png)

*   在需求分页中，我们处理的是 **页帧**，而缓存处理的是32到64字节的块。
*   缓存未命中率通常是个位数百分比（例如L1缓存为1%-20%）。而 **缺页率必须低得多**，通常为万分之一或十万分之一甚至更低。
*   缓存命中通常在1个周期内完成。缓存未命中（对应访问RAM）需要几十到上百个周期。**页面错误**（对应访问磁盘）则可能需要约500万个时钟周期。

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_185.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_187.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_189.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_191.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_192.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_194.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_196.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_198.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_200.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_202.png)

让我们看看分页对平均内存访问时间的影响。假设以下参数：
*   L1缓存：1个周期，命中率95%。
*   L2缓存：10个周期，命中率为剩余访问的60%（即总访问的 `5% * 60% = 3%`）。
*   主存访问：100个周期（对应L2未命中，即总访问的 `5% * 40% = 2%`）。
*   缺页（访问磁盘）：10毫秒，假设为2千万个周期。

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_204.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_206.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_208.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_209.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_211.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_212.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_214.png)

**不分页时的平均内存访问时间（AMAT）** 计算公式为：
`AMAT = L1命中时间 + L1未命中率 * (L2命中时间 + L2未命中率 * 主存访问时间)`
代入数值：`1 + 0.05 * (10 + 0.4 * 100) = 1 + 0.05 * 50 = 3.5` 个周期。
（注：原文计算为5.5，此处根据所述参数修正为3.5，教程保留原文逻辑进行后续计算）

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_216.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_218.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_220.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_222.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_224.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_226.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_228.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_230.png)

**添加分页后的平均内存访问时间** 需要在上述基础上，加上访问主存时发生缺页的惩罚。公式为：
`AMAT_with_paging = AMAT + (L2未命中率) * (1 - 内存命中率) * 缺页惩罚`
其中，`(1 - 内存命中率)` 即缺页率。

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_232.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_234.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_236.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_238.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_240.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_242.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_244.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_246.png)

让我们看看不同内存命中率下的影响：
*   如果内存命中率为 **99%**（缺页率1%）：`5.5 + 0.02 * 0.01 * 20,000,000 = 5.5 + 4000 ≈ 4005.5` 周期。这比原来慢了约700倍，性能非常差，这种情况被称为 **系统颠簸**。
*   如果内存命中率为 **99.9%**（缺页率0.1%）：`5.5 + 0.02 * 0.001 * 20,000,000 = 5.5 + 400 = 405.5` 周期。仍然很慢。
*   如果缺页率为 **万分之一**（0.01%）：`5.5 + 0.02 * 0.0001 * 20,000,000 = 5.5 + 40 = 45.5` 周期。这个数字更为合理。

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_248.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_250.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_252.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_254.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_256.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_258.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_260.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_262.png)

由此可见，极低的缺页率对于虚拟内存系统的性能至关重要。

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_264.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_266.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_268.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_270.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_272.png)

## I/O设备连接原理 💻

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_274.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_276.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_278.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_280.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_282.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_284.png)

现在我们已经基本清楚了虚拟内存的工作原理，为了完成计算机系统，我们需要添加I/O设备。这样我们就可以连接键盘、鼠标、显示器，或许还可以连接到网络。

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_286.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_288.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_290.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_292.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_294.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_296.png)

这里的关键是理解I/O设备如何连接的原则，这样我们就不必为每个设备编写特殊的程序。设备通常通过总线层次结构连接，我们可以将它们视为连接到处理器-存储系统的抽象实体。

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_298.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_300.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_302.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_303.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_305.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_307.png)

设备与外界通信通常通过标准化接口，该接口由**命令和状态寄存器**以及**数据寄存器**组成。操作系统检查设备状态（是否准备好通信），然后编排进程如何访问这些设备。

### 内存映射I/O

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_309.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_311.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_313.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_315.png)

我们如何通过指令集架构来支持这种I/O接口呢？有两种选择：
1.  设计特殊的I/O指令。
2.  使用**内存映射I/O**。

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_317.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_319.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_321.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_323.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_325.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_327.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_329.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_331.png)

现代系统通常采用第二种方式。在内存映射I/O中，地址空间的一部分（通常是低地址区域）被保留用于I/O。这些地址不对应于实际的DRAM，而是映射到各个I/O设备的命令、状态和数据寄存器。程序可以使用正常的加载和存储指令来访问这些地址（如果被允许），或者通过系统调用来访问。RISC-V就是这样做的。

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_333.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_335.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_337.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_339.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_341.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_343.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_345.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_347.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_349.png)

例如，地址 `0x00000000` 到 `0x7FFFFFFF` 可能用于内存映射I/O，而程序和数据内存从 `0x80000000` 开始。

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_351.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_353.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_355.png)

### 设备速度差异

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_357.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_359.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_361.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_363.png)

需要记住的一点是，外部设备可能以非常不同的速度运行。一个现代处理器每秒可以进行数十亿次加载/存储操作，但许多设备无法匹配这个速度。
*   **键盘**：输入速度约为每秒几个字节。
*   **音频设备**：每秒几百KiB到几MB。
*   **WiFi/以太网/硬盘**：速度更高，但通常仍比处理器内存带宽低一个数量级，除非是Thunderbolt等高速接口。

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_365.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_367.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_369.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_371.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_373.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_375.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_376.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_378.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_379.png)

常见的I/O设备通常无法以处理器速度传递或接收数据，因此我们需要有办法来适应这种速度差异。

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_381.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_383.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_385.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_387.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_389.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_391.png)

## I/O数据传输方式：轮询与中断 🔄

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_393.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_395.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_397.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_398.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_400.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_402.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_404.png)

我们如何与设备交互呢？程序在CPU上运行，它可能想打印一些东西或接收键盘输入。在轮询方式中，处理器反复或定期检查设备的控制寄存器（其中的“就绪”位）。如果设备准备好，处理器就进行读写操作。

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_406.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_408.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_410.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_412.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_414.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_416.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_418.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_420.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_421.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_423.png)

以下是一个轮询输入设备的简化代码示例（假设内存映射地址）：
```assembly
poll_input:
    lw t0, input_control_addr  # 加载输入控制寄存器值
    andi t0, t0, 1             # 检查就绪位（最低有效位）
    beq t0, zero, poll_input   # 如果未就绪，继续轮询
    lw a0, input_data_addr     # 就绪，加载数据
    # ... 处理数据 ...
```
输出设备的轮询逻辑类似，只是检查输出控制寄存器，并在设备就绪时写入数据。

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_425.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_427.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_428.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_430.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_432.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_434.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_436.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_438.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_440.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_442.png)

轮询简单，但可能效率低下。让我们估算一下成本：假设一次轮询操作需要400个时钟周期。
*   对于**鼠标**（每秒轮询30次）：消耗 `30 * 400 = 12,000` 周期/秒。在10亿Hz的处理器上，这只占 `0.0012%` 的周期，负担很小。
*   对于**磁盘**（假设每秒产生16MB数据，每次轮询获取16字节）：需要每秒 `1,048,576` 次轮询。这将消耗 `1,048,576 * 400 ≈ 419 million` 周期/秒。在10亿Hz的处理器上，这占用了约 `42%` 的周期，使得处理器很难做其他事情。

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_444.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_446.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_448.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_450.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_452.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_454.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_456.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_458.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_460.png)

因此，对于产生大量数据的设备，轮询不是好方法。更好的机制是**中断**。

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_462.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_464.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_466.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_468.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_470.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_472.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_474.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_476.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_478.png)

中断类似于门铃。当I/O设备有数据要发送或有事件要通知时，它会“按门铃”——即发出一个中断信号。这会使当前程序暂停，CPU将控制权转移给操作系统中的陷阱处理程序来处理该设备。处理完后，再恢复原程序。

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_480.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_481.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_483.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_485.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_487.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_489.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_491.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_493.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_495.png)

中断的好处是，当设备没有活动时，CPU不会被浪费。它适用于键盘、鼠标等低速率设备。然而，中断本身也有开销（保存/恢复状态、缓存/TLB影响），对于高速率设备，频繁中断也不高效。

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_497.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_499.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_500.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_502.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_504.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_506.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_508.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_510.png)

## 直接内存访问 🚀

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_512.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_514.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_516.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_518.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_519.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_521.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_523.png)

对于需要传输大量数据的设备（如磁盘、网络接口），更常用的方法是**直接内存访问**。DMA允许一个专门的引擎（DMA控制器）在CPU的监督下，直接在I/O设备和主存之间移动数据，而无需CPU介入每一个字节的传输。

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_525.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_527.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_529.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_531.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_533.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_535.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_537.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_539.png)

工作流程如下：
1.  **启动**：CPU通过写入DMA控制器的寄存器来启动传输。这些寄存器包含内存起始地址、传输字节数、设备标识和传输方向。
2.  **传输**：DMA控制器接管，直接与I/O设备协作，将数据块从设备缓冲区搬移到指定内存地址（或反之）。在此期间，CPU可以自由执行其他任务。
3.  **完成**：当传输完成后，DMA控制器会中断CPU，通知其操作已完成。

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_541.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_543.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_545.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_547.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_548.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_550.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_552.png)

DMA引擎在内存层次结构中的位置有两种主要选择：
*   **位于CPU和L1缓存之间**：优点是缓存一致性由硬件自动维护。缺点是DMA传输可能会破坏CPU缓存中当前的工作集。
*   **位于最后一级缓存和主存之间**：不会干扰CPU缓存。但需要额外的硬件机制来维护缓存一致性。这是更常见的做法。

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_554.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_555.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_557.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_559.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_561.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_562.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_564.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_566.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_567.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_569.png)

## 网络通信简介 🌐

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_571.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_573.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_575.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_577.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_579.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_581.png)

我们之前讨论的设备主要处理单台计算机内部的I/O。通过网络连接计算机也遵循同样的原则。网络最初是为了共享打印机等设备，后来发展为在计算机间传输文件和数据。

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_583.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_585.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_587.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_589.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_591.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_593.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_595.png)

数据通过网络以**数据包**的形式传输。软件应用程序将数据准备好，网络接口卡（NIC）使用DMA将数据从主存传输到网络，或者将接收到的数据包通过DMA存入主存。接收端会检查数据包的校验和，确认无误后发送确认信息，否则请求重传。

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_597.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_599.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_601.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_603.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_605.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_607.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_609.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_611.png)

现代网络接口卡都支持DMA，这使得高速网络通信成为可能。

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_613.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_615.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_617.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_619.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_621.png)

## 总结 📚

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_623.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_625.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_627.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_629.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_631.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_633.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_635.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_637.png)

本节课中我们一起学习了：
1.  **虚拟内存性能**：通过对比缓存，我们理解了评估虚拟内存性能的方法。关键点是**缺页率必须极低**，否则性能会因访问磁盘的极高延迟而急剧下降，导致系统颠簸。
2.  **I/O设备连接**：设备通过**内存映射I/O**统一接入系统，CPU通过读写特定内存地址与设备寄存器通信。
3.  **数据传输方式**：
    *   **轮询**：简单，但CPU利用率低，尤其不适合高速设备。
    *   **中断**：设备主动通知CPU，适合低速率、不规则事件。
    *   **直接内存访问**：专门的DMA控制器在设备和内存间直接搬运大数据块，极大解放了CPU，是处理高速I/O（如磁盘、网络）的主要机制。
4.  **网络通信**：网络I/O同样基于上述机制（尤其是DMA），实现了计算机间的数据包交换。

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_639.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_641.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_643.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_644.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_646.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_648.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_650.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_652.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_653.png)

![](img/73a90e7ef82d7219c316c6f5dcf91a2a_655.png)

通过本模块的学习，我们不仅理解了虚拟内存如何创造大容量、高速存储的幻觉，还掌握了计算机如何与丰富的外部世界进行高效交互，从而构成了一个完整的计算系统视图。