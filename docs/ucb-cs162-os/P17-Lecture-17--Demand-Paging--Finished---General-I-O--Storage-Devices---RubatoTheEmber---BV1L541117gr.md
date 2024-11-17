# P17：第17讲：按需分页（已完成）、通用I/O、存储设备 - RubatoTheEmber - BV1L541117gr

好的。

![](img/69f56b8db82e9345ac24f839eeec2786_1.png)

欢迎大家从春假回来。我将接管一段时间。希望大家度过了愉快的春假，实际上有一点放松，而不是一直工作。我第一次去了优胜美地，那真是太棒了，如果你们有机会去的话，一定要去。好了，我们将从安东尼那里接着讲。

有些事情我可以继续推进幻灯片，这里很好，如果你还记得，我们已经讨论了很多关于虚拟内存的内容。而虚拟内存的一个优点，当然是你可以拥有比实际内存更多的表面内存。虚拟内存还有很多其他的优点，但如果你将虚拟内存视为一个缓存系统，其中物理内存作为磁盘的缓存。

然后我们可以得出像这样的结果，令人惊讶的是，它可能也出现在了你的期中考试中。所以这里的想法是，如果有一部分时间我们必须执行页面未命中并去磁盘拉取数据。那么我们就可以开始讨论平均访问时间。所以我在这里称之为有效访问时间。

仅仅为了好玩，你知道的，这就像缓存一样。例如，这个较低版本的例子。稍等一下，我忘记了，我得先把这个调出来，这里是激光指示器。所以下面这个较低的。命中时间，我将使用第二个方程。那么命中时间是什么呢？命中时间就是它实际上在 DRAM 中，未命中的惩罚是指如果我们必须去磁盘获取数据并重新加载它时发生的情况。

那么让我们看看是否能以这种方式计算出一些东西。例如，如果你的内存访问时间是 200 纳秒，去磁盘的时间是 8 毫秒，未命中的概率是 P，1-P 就是命中的概率，那么我们实际上可以写出一个方程。例如，200 纳秒是命中时间，再加上 P 乘以 8 毫秒。

但是正如你在高中化学课上学到的，我希望你永远不要混淆单位。所以我们必须将时间单位从毫秒转换为纳秒，例如，我们得到这样的一个方程。这个方程看起来并不那么有趣，直到你真正尝试代入一些数字。比如说，如果每千次访问中有一次导致页面错误，而我们的平均访问时间是8。

2 微秒，尽管 DRAM 的访问时间是 200 纳秒。那么这里的关键是什么呢？你永远都不想遇到页面错误，对吧？这相当于一个 40 倍的因子。所以实际上，你知道，接下来你可以使用这个方程，令人惊讶的是，我们实际上也在期中考试中考过这个内容。那么如果我们想要将延迟减少到 10% 以下呢？那么 10 加上 10% 就是将 200 纳秒乘以 1。

我们可以进行计算，看到我们需要在不到400,000次访问中发生页面缺失，才能确保合理的访问时间。所以再次强调，绝对不要发生页面缺失。好的。那么这导致了什么呢？这导致了上一讲关于**替换策略**的讨论，当我们要把一个页换出去到磁盘时，我们必须非常小心地选择要换出的页面。

好的，因为这是成本所在。好，关于这个非常简单的计算有问题吗？从这个计算的结论基本上是我们希望我们的替换策略非常好。好的。所以我们讨论过时钟算法，如果你记得的话。

所以这个思路是，你将系统中的所有页面链接成一个循环的时钟，并且有一个叫做时钟指针的东西。每当发生页面缺失时。假设每个物理页面都在使用中。

所以当发生页面缺失时，我们会前进时钟指针，尝试找出要替换的页面。另一个安东尼讲过的重点是，LRU在每次访问时做起来有点太昂贵了。所以我们想要替换的不是最旧的页面，而是一个旧的页面。这就是这些近似算法的全部要点。时钟算法也不例外。因此，简单的思路是，硬件通过TLB中的使用位来处理，基本上是通过页表项来实现。

它基本上是说这个页已经被使用过了。那我们怎么处理呢？我们把它设为零。如果等我们转回来时它又被设为1，我们就知道它被访问过，因此它不是旧页面，而是新页面，是新错误。好的，我不想深入讨论这个，因为安东尼已经讲过了，但关于时钟算法一般有没有问题？大家都好吗？你们在考试前已经深入学习过这个，所以应该都能很好的掌握吧？

好的。我继续前进。有任何关于时钟算法的问题吗？一直想得到解答的？没有，好。接下来我想再强调一下，确保我们都清楚的是，内存管理单元是一块硬件。

页表通常存储在物理内存中，并且以特定的方式结构化。那么，页表中有什么呢？它就是这些页表项。所以这些页表项，每个页表项，比如这是x86版本的，32位地址空间看起来像这样。当你要转换虚拟地址时，你会按照我们之前讨论过的方式将其分解。

最终，在通过页表之后，你会得到这个页表项。它描述了你将要转换到的物理页。例如，其中有一个页框号，表示它在内存中的位置。还有一些其他的位，这些访问位有特定含义。例如。

这里有一个存在位。如果它没有设置为1，那么这个页面表项对应的页面框架是无效的，我们会发生页面错误。好的，接下来其他的位是用来执行类似时钟算法等操作，或者用来标记一个页面为只读而不是读写。好的，关于这一点有问题吗？好的，那我们接着往下讲。现在，当然我可能会问你们一个问题。

所有的页面表项在不同架构中是一样的吗？可能不是，对吧？这就是你在考试时会选择错误并解释原因的类型问题。显然，这对64位地址空间来说行不通，因为物理页面框架只有20位。好的，现在你们可能还记得上一讲结束时提到的那个二次机会算法。

我觉得有趣的是，二次机会算法的背景是他们原本想做时钟算法，但因为操作系统团队告诉硬件团队不需要使用位，所以不能这么做。好的，结果硬件团队该怎么办呢？他们想出了二次机会算法，好的，我知道有同学在这方面有问题。在嗯，教程中也有提到，我想快速地回顾一下。

所以这里的思路是，标记为绿色的页面就是已经被映射的页面。那么，什么叫做“映射”？就是说，如果我们查看我们的页面表项，它们被标记为物理页，对吧，能够访问，可能这就意味着它已经被映射了。那么这些绿色的页面，硬件只需要取一个虚拟地址并将其转换成一个物理地址。

这里根本没有涉及操作系统。好的，以上是那些标记为绿色的页面。至于我们为什么用FIFO来管理它们，我知道在Piazza上有相关问题，原因是我们没有其他办法，因为操作系统无法记录它需要做LRU或其他算法的任何统计信息，我们能做的最好的就是FIFO。好的，我想确保大家都理解这一点，这是我们能做的最好的方法，因为我们是直接从处理器通过MMU到硬件，再到物理页面进行映射的。

没有相关信息。好的，那么我们怎么才能把它做成类似时钟算法那样的“旧页面”状态呢？嗯，我们把一些黄色页面放在LRU列表中，但将其映射为不可访问。因此它们仍在内存中，但页面表项被标记为不可用。好的，正如Anthony多次提到的，如何让这个方法起作用呢？我们有了双重账本。

所以我们有类似账本的东西来跟踪这些黄色页面，以及它们应该被映射到哪里，尽管它们还没有被映射。所以当处理器尝试访问一个黄色页面时，嗯，你会遇到页面错误，因为它被标记为无效或不可用。然后你会对其做某些处理。好的，绿色页面则可以全速访问。

但如果发生页面错误，我们可能会因为页面是黄色的而发生页面错误。它在内存中但被标记为无效，或者它在磁盘上。这是我们的两种选择。那么我们该怎么办呢？如果是黄色页面，那么好处就是我们只需将一个绿色页面移到黄色列表，将黄色页面移到绿色列表。为什么我们能这么做呢？我们把这个绿色页面标记为现在不再存在。

我们把这个黄色页面标记为已存在。好了，瞧。我们实际上没有做任何磁盘操作。我们做的只是调整了页面表项。好了，为什么这样就能近似LRU呢？为什么这能给我们一种LRU的近似呢？有人想试试回答吗？是的，很好，我喜欢这个回答。

所以如果你使用一个页面，它要么会在绿色列表中，你没说过这一点，但它是对的，要么它在黄色列表中，然后你把它拉回到绿色列表，所以所有最近的页面都会回到绿色列表。如果它不再是最近的，它会停留在黄色列表中。

当我们执行这个过程时，它最终会被推向黄色列表中最老的页面，所以这给了我们一种近似。实际上，还有另一种情况，如果我们发生页面错误，但它甚至不在黄色列表中，那时我们就会从磁盘将它拉到绿色列表中。

到这个时候，我们将LRU的牺牲者踢出去，那就是最老的页面，因为很长时间没人触碰它。好了。就是这样。好了，这就是为什么第二次机会列表有点像时钟算法，它会给我们一个最老的页面，尽管有些不同。

这涉及更多的页面错误。但它仍然是近似的。我把"近似"放在引号里，因为这对LRU很重要。好了。好吧，在我离开之前，还有其他问题吗？是的。很好的问题，问题是，如果我能在黄色列表上做LRU，为什么我不能在绿色列表上做呢？

对。那是你的问题。有人想回答一下吗？是的。所以答案是非常好的。正如这里所说的，那样会非常昂贵。而原因是，记住什么是真正的LRU，它意味着每次我对一个页面执行加载或存储时，我将它从列表的中间移到前面。所以这意味着每次加载或存储都会重新排列列表。真的很昂贵，对吧？

所以每次加载或存储实际上是多个加载或存储。所以通过近似，我们允许一些页面在绿色列表中非常快速。然后，我们将它们过滤出来，并在黄色列表中做LRU，但我们不会做得太频繁，因此它不会那么昂贵。所以这就是答案。很好。回答了你的问题吗？太好了。所以。

我们可以做很多事情，没错，我们可以让绿色列表非常小，这样就能实现非常好的LRU，但是这样代价高昂；我们也可以让绿色列表变得非常大，黄色列表变得非常小，这种情况下我们基本上会有FIFO行为。但这种方式更快，当然，如果我们有太多FIFO行为，最终会导致滑动异常，这有点不幸。所以很好，这就是一个真实的算法，VMS就使用了这个算法，它是有效的。

关键是我认为我们喜欢讨论这个的原因，实际上它向你展示了，你可以通过页表项做一些有趣的事情，而不仅仅是说，如果它无效，就在磁盘上；如果它有效，就在内存中，我做了一些更有趣的事情，对吧，我说，“嗯”。

它可以映射到内存中，也可以不映射到内存或磁盘上，我通过操作页表项来实现这一点，基本上拥有另一本书集，这些书是离线的，可以让我知道发生了什么。好了，问题是我原以为在操作系统没有介入的情况下，不能做LRU，而在绿色区域根本做不了LRU，没错，绿色区域确实不能做LRU，但是整个系统有一种类似LRU的行为。

所以这是一个旧页面要丢弃，而不是最旧的页面，就像时钟算法一样。好了，为什么我们要这样实现？因为我们缺少一个使用位。硬件没有使用位。好的，有其他问题吗？有没有什么燃眉之急的问题，在春假时你就得考虑第二机会算法，因为它实在是太有趣了。

不。

![](img/69f56b8db82e9345ac24f839eeec2786_3.png)

好的。好了，所以我们可以利用我刚刚给你们展示的那个方法。那么，顺便问一下，为什么黄色被称为“第二机会”？

![](img/69f56b8db82e9345ac24f839eeec2786_5.png)

因为我们把它取消映射了，对吧，它仍然在内存中，并且有第二次机会回来使用。对吧？所以我们可以用相同的思路，即使我们有一个时钟指针。

![](img/69f56b8db82e9345ac24f839eeec2786_7.png)

所以我们可以做常规的时钟算法，但不是针对每个页面错误都执行时钟算法，而是周期性地执行时钟算法，将一堆页面放入我们所说的空闲列表中。在这个空闲列表中，我们将管理FIFO，这样当我们需要一个新页面时，页面错误发生时，列表里就有一个页面可以使用。

那么，为什么这样有利呢？嗯，如果我们有脏页，也就是已经写入的页面，我们可以让时钟算法说它们虽然脏，但使用频率不高，因此把它放到空闲列表中。然后，因为它是按FIFO管理的，等它到达列表头时，页面换出就已经完成，而且它不再脏，变干净了。好了，这就是一种方法。

另一种方法是允许我们缓冲一组空闲页面，并允许我们在后台进行脏页面清理，这样当我们真正需要一个页面时，它已经准备好了。好的，它有点像一个**第二次机会列表**，因为如果我试图访问这些页面之一，而它正好在空闲列表上，我就把它重新拉回到时钟算法中，因为我不必访问磁盘。

好的，关于这个想法的优点是，当我们真正需要一个页面来处理页面错误时，**时钟算法**不再位于关键路径上。我们只需抓取一个空闲页面，启动磁盘，瞧，页面就可以了，而不是在那个时刻就必须运行时钟算法。好了，有问题吗？很好。顺便说一下，这些不同的事情有很多变种，所以我们给你们提供了一些关于这些事情如何运作的想法，但是拥有一个空闲页面列表来缓冲时钟算法，确实有助于将它从关键路径中移除。

好的。很好。那么现在有一些细节。比如说，我们该怎么做？当我们的算法，无论是时钟算法、第二次机会算法、第二时钟算法、空闲列表算法，决定要完全驱逐一个页面时，我们该怎么做？因为当我们驱逐一个页面帧时，说明我们已经决定要替换它。这个页面可能被多个不同的页面表条目所指向。

进程A和进程B共享一个物理页面，它们的页面表中都有该页面。那么现在，当我们想要将这个页面驱逐出去时，我们需要反向映射到每个页面表中指向该页面的条目，这样我们就可以取消映射它们。好了，这叫做**反向页面映射**。你可以通过每个页面表线性地查找它，显然这是个坏主意，对吧？

或者你可以使用一个通常叫做**核心映射**的结构。它将物理页面映射到所有包含它的页面表中，这样当我们想要把它从内存中驱逐并取消映射时，我们就可以使用这个反向页面表来查找它。好了，它必须非常快，因为你需要在释放页面时迅速找到所有指向该页面帧的页面表。

因为这可能是页面错误的关键路径。好的，并且有很多选择，所以对于每个页面描述符，你都要保留一个指向它的页面表条目的列表，因此，如果你查看它们，我不知道，比如在Linux内核中，你会看到每个物理页面或页面范围可能都有一个描述它的小结构。

所以你现在要做的是，跟踪所有这些页面，找到需要的那些页面。然后从那个入口出发，去找到所有包含它的页面表项。这可能非常昂贵。因此，Linux通过一次分配一段页面来缓冲多个这些操作。我们不会详细讨论这个问题，因为如果你仔细想一想，你会发现这实际上与我们最初进行分页时的目标——避免外部碎片——是相违背的，因为现在我们实际上是给出了页面的范围。

好的，问题？好的，那么现在让我们处理最后一个话题。到目前为止，我们讨论的都是页面替换。实际上，问题是当需要新的物理页面时，我们如何决定要淘汰哪个物理页面，尤其是因为分页操作的发生。

那么我们到底是如何在不同进程之间分配内存的呢？实际上，这个时钟算法的描述方式有点像假设整个世界只有一个进程，它正在进行分页操作，这就是最初的描述方式，我们没有去讨论多个进程的复杂性。

但如果我们有不同的架构呢？我们该怎么办？比如，我们可以说每个进程得到相同份额的内存，或者进程得到不同份额的内存，或者它们都共享一个大的内存池。这里有很多选择。

也许有些进程需要完全从内存中交换出去。好的，我们可能需要考虑这个问题。但每个进程肯定需要一个最小的页面数，才能继续运行。如果一个进程正在运行，我可以给你一个非常简单的例子。基本上，你需要确保每个进程在完全加载到内存后，能够继续向前执行。这里有个简单的例子，虽然稍微复杂一点，但足够有趣。

比如说，IBM 370的情况。事实证明，字符串移动指令至少需要六页内存才能继续执行。为什么？因为指令是六个字节，可能会跨越两页。你需要两页来处理“from”，再需要两页来处理“to”。因此，为了重新启动正在执行SS移动指令的进程，必须有足够的页面。

你实际上必须确保这六个页面都在内存中，才能使其运行。好的，所以像你非常熟悉的RISC架构（比如RISC-V）要比这个简单得多，因为它只有一条指令，数据将访问的页面通常只有两页。

好的，但当然我们必须关注最小化的因素。因此我们可以在这里讨论一些替换策略，例如，我们可以讨论全局替换。当一个进程因为发生了页面错误而需要页面时，我们可以想象，每个页面框架都在一个巨大的时钟中，我们就从时钟中抓取下一个页面。

块对吧，这就是我们之前讨论的方式。但如果采用本地替换策略，可以通过给每个进程分配一定比例的页面来实现更多控制，每个进程都有自己的时钟。好吧，现在我们为什么要做第二种方式呢？来吧。好，它更快，因为你不需要同步，尽管使用时钟算法时。

你实际上绕过了很多同步机制，尤其是当你有一个空闲列表时，实际上你只是从空闲列表中取出东西。所以速度在这里是一个可能性，但也有其他原因。是的，公平性更高。你是什么意思？当然，我们在这门课上并不知道“公平”究竟意味着什么，对吧？我们并不知道它是什么。所以我喜欢这个回答，公平的意思就是更公平。

这里的“公平”意味着一个进程不能从另一个进程那里抢走大量内存。好吧。如果你考虑到实时任务，我们稍微讨论了一下实时任务，那么我们可能会说，需要给进程分配最小数量的页面，以确保它能够正确地向前推进。所以我们会给它一些其他进程无法夺走的页面。

如果我们进行全局替换，那么就会出现这样一个问题：可能会有一个进程干扰到另一个进程。好吧，太好了。所以，如果你稍微想一想，回想一下我们在调度方面做的事情，我们一开始使用了类似循环调度的方式。

最终我们到了 CFS（完全公平调度器），我们为每个进程分配一定比例的 CPU 时间，这样就更容易理解公平性了。总的来说，因为我们给每个进程分配了 CPU 周期的流速。这是一个类似的概念，我们会为每个进程分配一个明确的最小页面数。

所以，除了全局与本地的区别，我们还有其他一些选项，例如，如果我们采用本地策略，现在会怎么做呢？我们可以给每个进程分配相等的内存。例如，如果总共有 100 个内存页面，5 个进程，那么每个进程分配 20 个页面。

好吧，或者我们可以进行某种比例分配。更大的进程获得更多的内存。好吧，我在这里展示的这个方程是：你先计算进程的总大小，然后这个大小占所有进程总大小的比例，就是它应该获得的内存比例。好吧，一旦你弄明白它在做什么，这个就不复杂了。

但实际上这有一些微妙的缺点，谁能告诉我为什么这不好吗？听起来不错吧？对，没错，你可能会让程序中充满一些什么都不做的库。好吧，实际上，你每天都在完全没有恶意的情况下做这件事，比如你链接了一个大型加密库，但实际上只使用了其中的 ECC 部分来做签名。所以它并不是你程序的核心部分。如果我决定分配多少物理页面是基于我的程序大小，那么这就变得很单薄了。

它与我需要的内容无关，更多的是与代码的默认大小有关，对吧？好吧，另一个方法是我可以通过优先级来做。所以我可以使用基于优先级的比例方案，而不是基于大小。你知道的，所以行为可能是进程 PI 产生了一个页面错误。你还是从低优先级进程中选择一个帧。

如果你想做优先级的话，可能这有点道理，对吧？所以也许我们应该做一些自适应的事情。但是如果我们想做一些自适应的事情，我们就得有办法来确定一个进程到底需要多少内存，而不是依赖这些静态的概念。有没有人能想到我们可以采取什么样的自适应方式来决定一个进程需要多少内存？

预测工作集。我喜欢这个。这是有可能的。是的。我们还可以怎么做呢？工作集是一个页面大小，对吧？我们怎么预测工作集呢？我猜我们得先定义工作集意味着什么，对吧？所以让我们搞清楚这一点。我们来看一下。如果我们想减少容量时间。

通过动态改变页面数来减少未命中。所以记住，容量未命中是缓存未命中的一种。它所表达的是，我正在遇到页面错误，因为我没有分配足够的内存。所以如果我增加内存的数量，而且我没有使用 FIFO，那么我应该能够减少未命中的数量，对吧？更多内存，减少未命中。

除非我们使用FIFO，否则我们就会遇到所谓的“女士异常”，对吧？所以我们可以这么做。我们可以说，看一下我们给每个进程分配的帧数。如果我们给它们一个小的数字，就会发生很多页面错误。如果我们给它们一个大的数字，就会发生较少的页面错误。

我们可以想象一个阈值。我们真正想做的是尽量调整。这样进程就能处于某个范围内。如果它们的错误率太高，说明它们的内存不足；如果它们几乎不发生错误，那么它们可能内存过多，我们可以尝试通过调整页面帧数来把它们调整到这个理想的范围内。好吧，这样做会有一个很好的折衷，如果你有很多进程，每个进程都能进入这个页面错误率范围。

好的，现在还不是工作集，但它已经接近了，对吧？它是在试图降低成本。这更像是我们在本讲中开始讨论的有效访问时间公式，对吧？试图减少它。好了，假设我们没有足够的内存。抖动会发生，没错，我们会讨论抖动，但我们从高层次来看这个问题，假设我们真的没有足够的内存。

在整个调度讨论的最后，我们稍微提到过，如果你只是没有足够的 CPU 周期怎么办？你就买一台新机器，对吧。所以你应该知道的是，资源分配政策总是在试图在多个不同的消费者之间分配有限的资源。

到某个时刻，你的资源就不够了，你必须找到更大的资源来解决问题。好吧，我知道我这么说很有趣，但你必须时刻记住这一点，对吧？到某个时候，你的资源分配根本无法解决问题，因为你就是没有足够的资源。好吧，我们先假设我们暂时有足够的资源。

![](img/69f56b8db82e9345ac24f839eeec2786_9.png)

但我们来谈谈抖动吧，抖动的有趣之处在于，这种情况发生在一个进程没有足够的页面时，这实际上会导致 CPU 利用率低，而操作系统大部分时间都在进行磁盘交换。

这里有一个例子，我们要做的事情是，例如，我们可能会增加更多的线程来尝试进行大量计算。一开始，更多的线程为我们提供了更多的并行性，一切看起来都很好，但是之后我们没有足够的页面，也没有足够的 CPU，实际上，当我们尝试做更多的事情时，效果就开始下降了。我们根本没有足够的资源。好吧，抖动的范围大致就是在这种情况下，任何类型的并行性增加或者尝试做更多的工作都不起作用，因为我们没有足够的资源。

当你处于分页状态时，就像我们之前讨论的那样，抖动就是那种情况：你尝试访问某些内容，或者把它从磁盘拉出来，同时你又尝试另一个进程，这个进程也没有足够的资源，所以它也从磁盘拉取内容，对吧？所以，你总是会看到每个进程都在等待从磁盘加载某些东西。它会在数据返回时运行，然后立刻再进行分页。

这就是页面错误，然后你跳到下一个进程，所以没有进展发生，操作系统只是在进行页面调入和调出，没有实际的计算发生。好吧，这就是抖动。好了，那么我们如何检测抖动呢？

那么，如何应对抖动（thrashing）呢？检测抖动的一个好方法是什么？当然，你可以看看有多少程序正在等待交换，如果它们都在等待，那么很可能是有问题的，对吧？我还会指出这张图，看看如果每个人都处在那种状态下。

![](img/69f56b8db82e9345ac24f839eeec2786_11.png)

高失误率区域，情况就不好了。对吧？所以，嗯，抖动就是不好的。那么我们该怎么办呢？抖动通常是因为有太多进程同时运行，且它们试图使用最少的内存。

所以，也许，如果没有更好的办法，完全将一个进程换出到磁盘，彻底将其从内存中交换出去，运行其他进程一段时间，然后再把它完全调回内存，可能会让整个系统运行得更好。这听起来很激烈，但实际上，与试图保持所有进程都在内存中并让它们做最少的工作相比，这反而能加速整个系统。

好的，现在我们可以稍微谈一下这个问题。关于工作集的问题，在这里我有一个图，横轴是执行时间，纵轴实际上是地址数，好吗？所以这些小灰色的点代表在某一时刻对该地址的访问。好，大家跟得上吗？所以在任何时刻，如果我们直接看上去。

我们看到的是，在那段时间内所有被使用的地址。事实上，如果我们查看一个窗口，在任何一段时间内，我们可以查看所有被访问的地址。这些都是我们需要在内存中保持的地址，以便系统能够继续前进，明白吗？所以我们可以把它想成，通常它会被称为工作集。

但如果我们将窗口扫描到执行的过程中，我们看到的是，在任何给定的范围内，正在使用的模式是什么，或者说，正在使用的地址是什么。好，这就是工作集。它是一个最小的页面数，足以让进程正常运行。

而且，工作集所需的内存不足基本上会导致抖动。因此，如果我们有太多的进程，且所有工作集的总和超出了内存的容量，你就会遇到抖动的情况。好，在这里我们可以稍微正式一点。这里是一个工作集模型。

如果我们看页面引用，顺便说一下，可以把这些看作是地址。比如 2，6，1，5，7，7，5，1 等等。工作集基本上是说，在任何给定的时刻，有一个表示历史的增量。如果我们看所有在这个增量中被访问的页面，那么这些就是工作集，所以在这里是 1，2，5，6，7，当然，这里是 3 和 4。好。

所以需要注意的是，工作集是会随时间变化的。好，程序会经历不同的阶段。当它变化时，可能会有不同数量的页面，甚至在某些情况下。所以这里的工作集只有两个页面，而之前的工作集是五个页面。好。

所以这表示的是，为了能够向前推进，必须保留在内存中的内容。因此，在这里，在这个时间框架内，第一个增量，如果我们有很多进程，每个进程都有很多页面，那么将它们加起来可能会超过内存容量。与此不同，在这段时间内，可能有很多进程。

每个进程可能只需要几个页面，那么你可能不会发生抖动（thrashing）。所以实际上运行的进程总数可能随着时间变化，造成抖动的情况也会变化，这是一个纯粹的动态系统。好，实际上，工作集基本上是指最近的增量中被引用的所有页面，增量是无论是什么。如果增量太小，它就无法包含实际的局部性。

所以我们希望它足够大，以便对发生的引用进行平均化。如果它太大，基本上就是整个程序，就像“嗯，那不有用”。它只是程序的所有页面引用，但并没有真正谈到任何特定时间段的情况。而显然，如果增量趋近于无穷大，那我们就讨论了程序访问的每一个地址。

但是，如果这个程序运行了一周，甚至一个小时，那就不太有用了，因为它并没有告诉我们某一特定时间段内的页面错误率。好的，然后如果我们取某一时刻的工作集，并把它加总到所有进程中。

这是我们需要的总物理页面数。来避免抖动。抖动基本上发生在D大于我们拥有的内存时。好的，我在这里暂停一下。这不是复杂的数学问题。只是我们为每个进程计算工作集，然后把它们加总起来。

如果这些页面的总数大于我们拥有的内存，那我们就会遇到问题，并且开始抖动。好的，有问题吗？很好。所以，从某种意义上说，这实际上是在定义抖动的现象，对吧？

![](img/69f56b8db82e9345ac24f839eeec2786_13.png)

所以，这里有个问题。有人问，即使没有上下文切换，抖动是否仍然会发生。

![](img/69f56b8db82e9345ac24f839eeec2786_15.png)

嗯，当发生抖动时，你所做的就是上下文切换。因为发生的情况是，你必须访问磁盘，而在页面从磁盘加载的同时，你正在切换到另一个进程。所以，与聊天中所说的不同，我会说，抖动是一种你所做的唯一事情就是上下文切换的情况。好的。

这是相反的。那么，强制缺失又是怎样的呢？如果你考虑强制缺失，它是指页面首次被访问时发生的缺失。第一次被触及的页面，或者如果我们由于抖动原因交换整个过程并重新加载这些页面，它们也可以被称为强制缺失。结果发现，操作系统有几种方式来处理这些情况。

其中一种是聚类的概念，即当你在一个页面上发生页面错误时，会同时读取该页面周围的多个页面。好，我们在缓存中怎么称呼这种现象呢？空间局部性。非常好。所以，正如我们下次在讨论磁盘时将要学到的那样，特别是在旋转存储中，如果你同时读取一串连续的数据，磁盘读取的效率会大幅提升。

好的，如果我们从单个轨道中抓取一堆页面，那比一次抓取一页要高效得多。所以，集群化的这个概念，当我们遇到一次未命中时就抓取一堆页面，实际上是一种非常有效的方式，既能提高页面调度效率，也能处理强制未命中的情况，前提是存在某种空间局部性。好的，接下来，另一个有趣的地方是，一些操作系统已经实现了，如果你实际上有某种机制来追踪进程的工作集。

所以有一些页面结构会指示当前这个进程的状态，工作集包含这些页面。然后，每当进程休眠并重新启动时，你可以提前预取工作集，确保它不会马上发生页面错误。对吧？这是一种有趣的预测方法，基本上如果我查看过去的情况会是怎样的。

在我把它挂起或交换到磁盘之前，什么是工作集？一旦我把它拿回来，我会确保所有这些页面都被提前取回，这样我就不太可能马上遇到页面错误了，因为我已经把工作集加载到内存中了。好的，大家有问题吗？好了，好的。我想我们大部分时间会结束今天的分页内容了。我确实想谈谈期中考试的事。我们在春假前就做完了考试。

我想如果你们对重评分请求有任何疑问，它们明天截止，所以确保及时提交。Piazza上有一个期中考试的问题讨论区。在春假期间，我回答了很多问题，那里有一些问题在积累，我们会继续处理。但总的来说，我们的平均成绩和上次差不多，所以这次考试没有变得更简单。

我猜第五个问题对大家来说有点长。问题非常长，所以Sean我们的小组负责人在Piazza上发布了一个回答，详细解释了第五个问题的每个步骤，如果你们想看详细的内容，可以查看。别被那些文字吓到。

他试图把话说得非常详细，尽量确保每个人都能理解。第二个项目是这个星期六，大家应该都知道吧，所以我就不再多说了。第三个项目是下一个项目，截止日期是4月3日。请注意，这两个项目都不是4月1日，所以它们不是愚人节的玩笑，尽管它们确实有截止日期。真难以相信我们已经走完了三分之二的课程了。

我想我不太习惯共同授课，所以感觉好像已经有一段时间没在这里讲课了。不过，不管怎样。别忘了提交你们的重评分请求。我还想再分享一点小知识。你们是计算机科学领域的精英，必须掌握你们的单位。

好吧，我们假设你知道单位。例如。有些人实际上在期中考试时问过，知道多少微秒等于一毫秒之类的。我们假设你知道这个。好吧，如果你不知道，查看一下也不会有什么坏处。因为我期望基础工程学的人会知道这些东西。好吧，这里有一些特别有用的单位，毫秒、微秒、纳秒、皮秒。

我假设你知道一分钟是 60 秒，一小时是 3600 秒。但是。这些是很好的知识。还有一些其他的也很好知道。所以。这些将在接下来的讲座中涉及到。通常情况下，bit 是小写的 b，byte 是大写的 B。好吧，记住这一点。并且 W 是一个。

这取决于。好的，W 代表字（word）。通常情况下。我会说字代表处理器原生整数的位数。所以对于 32 位处理器，一个字是 32 位。不幸的是。它接管了世界。因为在 8086 中，W 是 16 位。如果你专门处理英特尔处理器，W 就是 16 位，双字（double word）实际上是 32 位。好吧，我并不支持这种疯狂的方式，我只是告诉你们。

好吧，这实际上意味着如果有人提到 W，问一下是否不清楚。因为。对于 x86 来说，W 实际上是 16 位，我讨厌它，因为我每次都会忘记。你知道，作为一名计算机架构师，多年来 W 对我来说总是表示处理器的原生整数大小。但是对于英特尔来说并非如此。所以，好的。这里有一些有趣的东西，现在有点棘手。

因为。如果你在处理内存。那么 kilobyte（千字节）。实际上意味着 1024 字节。好吧，现在我想在 61 B 中他们称之为 kibby。听起来像是你喂猫的东西，对吧？一个 kibby 咬。 但是。不幸的是，在现实世界中，千字节 kby。如果你在处理内存的话，它和 kibby 咬是一样的。好吧，不管怎样。

所以你可以看到这里，比如说一个兆字节（megabyte）或者兆（maybe）是 1024 的平方，也就是 2 的 20 次方。好吧，等等。这部分你可能没有意识到，所以一个千字节（kilobyte）或者 tebibyte（tiB）是 2 的 10 次方，兆字节（megabyte）或者 mebibyte（MiB）是 2 的 20 次方，千兆字节（gigabyte）或者 gibibyte（GiB）是 2 的 30 次方，等等。我的最爱是更高端的，比如说 tebibyte（TiB）是 2 的 40 次方，拍字节（petabyte）是 2 的 50 次方，艾克字节（exabyte）是 2 的 60 次方。

好吧，有人知道接下来是什么吗？它是 yada。总之。如果你知道这些，这很好。好吧。所以，当你处理几乎所有其他的东西，除了内存之外。我们使用的是 10 的幂。这些是 2 的幂，这些是 10 的幂。你看到了区别了吗？

好的，当我们谈论磁盘带宽或网络带宽时，当我们谈到一个千兆字节时，它将是10的九次方字节。不是你知道的，2的30次方字节。好了，再次声明，这种疯狂不是我发明的，这就是事情的运作方式，实际上磁盘制造商喜欢说他们给你100GB的东西。

它将是10的九次方字节，而不是你知道的1.1乘以10的九次方。所以查看你的规格。现在这些差异不大，但你应该知道，它肯定可能会出现在考试中。

我尽量小心，也许会给你们解释一下KiB表示法，但我想把这个写下来。只不过是让你们知道，这种情况几乎只会出现在61B课程和一些其他问题网站上，但不一定出现在现实世界中。

你必须处理它。再说一遍，世界是一个奇怪而美妙的地方。你知道DRAM的特点就是它是显式的2的幂，因为地址是，位数，它们是2的幂，几乎世界上其他的东西都是10的幂，因为我们有10个数字。为什么内存是唯一一个倾向于使用KiB，我不知道，或者是MiB，或者是GiB。

这只是世界的规则。有些制造商实际上甚至尝试过这样做。它们已经满了，所以有时候你实际上会看到这种G.I.B表示法。大多数时候你不会看到，但我想指出这一点。这样你可能在考试时知道要留意它，如果你实际上在查看任何东西的规格时，只需留意。

有时候人们喜欢说，磁盘制造商使用这些10的幂，而不是2的幂，这样他们是在作弊。你知道，他们购买的人他们的供应商可能是这样。我不知道这是否成立，只是，这样的规则就是如此，所以留意一下。

但我确实期望你们对大多数这些概念有所了解。好的，你可以把一些常见的概念放在备忘单上，如果需要的话。好了，单位。我们不谈布鲁诺。哦，等一下，我们谈论的是单位。好了，现在，我想我们不谈布鲁诺，在伯克利这里已经不是问题了。

应该在控制台上你们都会看到，我猜与我的10岁孩子在一起，我能看到更多的动画内容。好了，我们继续。接下来我想开始谈论，我希望我们能深入讨论磁盘和文件系统，这是下一个主要话题。我确实想完成一件事。关于内存管理，Unix（抱歉）Linux比我们迄今为止给出的示例要复杂得多。

所以，在 Linux 中，例如，有很多内存区域。比如 DMA 区，它是小于16MB的物理内存。还有普通区域，它介于16MB到896MB之间，然后就是高内存，剩下的部分。这些是怎么来的？嗯，一切都源于历史。所以从历史上看。

你曾经有过32位处理器或16位处理器。这时内存非常大，所以这个普通区域基本上就是你能拥有的。现在，当然没人会购买内存少于4到8TB的机器，所以这个内存映射已经完全过时，但它仍然有效。

好的，特别是以前，如果你进行 DMA，我们可能在讲座结束时再详细讨论这个，如果我们能讲到的话，但肯定会是下次。你只能在物理内存的前16MB内进行干净的 DMA 操作。这对老旧的 DMA 引擎来说是个限制。好的。所以，你知道，那个时候在老旧的 IBM PC 上也可以做到 DMA。

但我们仍然在 Linux 中看到这些常量，如果你查找它们的话。所以每个区域都有自己的空闲列表和活动/非活动列表，它们有点像时钟。好的。活动和非活动的部分，你以为有一个时钟或多个时钟很复杂吗？其实每个区域都有自己的两个时钟，它们会交换。好的。

内核中有许多不同类型的分配。好的，有 slab 分配器，它分配大块页面。也有每页分配器。还有映射和非映射分配的能力，很多有趣的事情，有很多不同类型的分配内存。

所以，当你进行内存分配时，你可以获得所谓的匿名内存，这基本上就像是堆栈并不一定是由文件支持的。或者你可以将文件映射到内存中，并像读取虚拟内存一样访问这些文件，我们下次会讨论这个。好的。所以有很多不同类型的内存，我们还会稍微讨论一下 slab 分配。

我想下次或下下次再做吧。然后，当然，他的分配优先级等等。

![](img/69f56b8db82e9345ac24f839eeec2786_17.png)

有件事挺有意思的，那就是在“熔断”之前。好的，这是典型的内存映射，你之前已经看过了，但我想澄清一下。所以我是32位虚拟空间。从零到0xC，基本上是用户地址。然后从0xC到FFFF，是内核地址。这就是它的分配方式。

好的。那么这需要记住什么呢？在我们的页面表项中有一个小的用户位。然后它就是 DTE。这意味着在这里的任何地址，那个用户位都是零，因为它们仅供内核使用。如果你从32位切换到64位，那么它就大得多。好的，64位就是大。好的。

所以实际上，处理器做的就是这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。

然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。

然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。

然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。

然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。

然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。

然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。

![](img/69f56b8db82e9345ac24f839eeec2786_19.png)

然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。

![](img/69f56b8db82e9345ac24f839eeec2786_21.png)

然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。

然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。

然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。

![](img/69f56b8db82e9345ac24f839eeec2786_23.png)

然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。

然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。

然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。

![](img/69f56b8db82e9345ac24f839eeec2786_25.png)

然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。然后我们要做这个。

然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。

然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。

![](img/69f56b8db82e9345ac24f839eeec2786_27.png)

然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。

然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。

然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。

然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。

然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。

然后我们要做这个。 然后我们要做这个。 然后我们要做这个。 然后我们要做这个。 然后我们要做这个。 然后我们要做这个。 然后我们要做这个。 然后我们要做这个。 然后我们要做这个。 然后我们要做这个。 然后我们要做这个。 然后我们要做这个。

然后我们要做这个。 然后我们要做这个。 然后我们要做这个。 然后我们要做这个。 然后我们要做这个。 然后我们要做这个。 然后我们要做这个。 然后我们要做这个。 然后我们要做这个。 然后我们要做这个。 然后我们要做这个。 然后我们要做这个。

然后我们要做这个。 然后我们要做这个。 然后我们要做这个。 然后我们要做这个。 然后我们要做这个。 然后我们要做这个。 然后我们要做这个。 然后我们要做这个。 然后我们要做这个。 然后我们要做这个。 然后我们要做这个。 然后我们要做这个。

然后我们要做这个。 然后我们要做这个。 然后我们要做这个。 然后我们要做这个。 然后我们要做这个。 然后我们要做这个。 然后我们要做这个。 然后我们要做这个。 然后我们要做这个。 然后我们要做这个。 然后我们要做这个。 然后我们要做这个。

然后我们要做这个。 然后我们要做这个。 然后我们要做这个。 然后我们要做这个。 然后我们要做这个。 然后我们要做这个。 然后我们要做这个。 然后我们要做这个。 然后我们要做这个。 然后我们要做这个。 然后我们要做这个。 然后我们要做这个。

然后我们要做这个。 然后我们要做这个。 然后我们要做这个。 然后我们要做这个。 然后我们要做这个。 然后我们要做这个。 然后我们要做这个。 然后我们要做这个。 然后我们要做这个。 然后我们要做这个。 然后我们要做这个。 然后我们要做这个。

然后我们要做这个。 然后我们要做这个。 然后我们要做这个。 然后我们要做这个。 然后我们要做这个。 然后我们要做这个。 然后我们要做这个。 然后我们要做这个。 然后我们要做这个。 然后我们要做这个。 然后我们要做这个。 然后我们要做这个。

然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。

然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。

然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。

然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。

然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。

然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。

然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。

然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。然后我们将做这个。

![](img/69f56b8db82e9345ac24f839eeec2786_29.png)

然后我们将要做这个。然后我们将要做这个。然后我们将要做这个。然后我们将要做这个。然后我们将要做这个。然后我们将要做这个。然后我们将要做这个。然后我们将要做这个。然后我们将要做这个。然后我们将要做这个。然后我们将要做这个。然后我们将要做这个。

然后我们将要做这个。然后我们将要做这个。然后我们将要做这个。然后我们将要做这个。然后我们将要做这个。然后我们将要做这个。然后我们将要做这个。然后我们将要做这个。然后我们将要做这个。然后我们将要做这个。然后我们将要做这个。然后我们将要做这个。

然后我们将要做这个。然后我们将要做这个。然后我们将要做这个。然后我们将要做这个。然后我们将要做这个。然后我们将要做这个。然后我们将要做这个。然后我们将要做这个。然后我们将要做这个。然后我们将要做这个。然后我们将要做这个。然后我们将要做这个。

然后我们将要做这个。然后我们将要做这个。然后我们将要做这个。然后我们将要做这个。然后我们将要做这个。然后我们将要做这个。然后我们将要做这个。然后我们将要做这个。然后我们将要做这个。然后我们将要做这个。然后我们将要做这个。然后我们将要做这个。

然后我们将要做这个。然后我们将要做这个。然后我们将要做这个。然后我们将要做这个。然后我们将要做这个。然后我们将要做这个。然后我们将要做这个。然后我们将要做这个。然后我们将要做这个。然后我们将要做这个。然后我们将要做这个。然后我们将要做这个。

然后我们将要做这个。然后我们将要做这个。然后我们将要做这个。然后我们将要做这个。然后我们将要做这个。然后我们将要做这个。然后我们将要做这个。然后我们将要做这个。然后我们将要做这个。然后我们将要做这个。然后我们将要做这个。然后我们将要做这个。

然后我们将要做这个。然后我们将要做这个。然后我们将要做这个。然后我们将要做这个。然后我们将要做这个。然后我们将要做这个。然后我们将要做这个。然后我们将要做这个。然后我们将要做这个。然后我们将要做这个。然后我们将要做这个。然后我们将要做这个。

好的，现在我们快速进入输入输出（IO）的部分。抱歉，今天讲得有点长，但也许我们可以继续讨论下去。下次我保证给你们休息时间。如果你查看Hennissi Patterson关于计算机架构的书，它讨论了计算机的五个组成部分，还有处理器内部的许多内容。

你知道，数据路径和流水线这些东西。它们很棒，做起来也很有趣。我自己是一个计算机架构师，我觉得这些东西非常吸引人。但是，如果你只有一个没有输入输出（IO）的处理器，那就像是一个没有身体的脑袋，根本没有趣味。好的，那只是一个加热元件。

好的，今天处理器最有趣的地方是它们的输入输出（IO）。所以这就是为什么我们必须进行一些有趣的讨论。

![](img/69f56b8db82e9345ac24f839eeec2786_31.png)

关于如何进行输入输出（IO）。那么，如何做输入输出呢？到目前为止，在162课程中，我们已经介绍了各种抽象。操作系统应用程序提供的API。我们讨论了同步和调度，但我们还没有讨论输入输出（IO）。好的，这是有意的。但是没有输入输出（IO），计算机是没用的。好的，所以真正的，最有趣和最复杂的部分是。

这个项目最有趣的部分是我们如何处理输入输出（IO）？

更复杂的是，存在成千上万种不同类型的设备，它们都以不同的速度运行。问题是，如何让它们协同工作？你知道，如何标准化接口？设备是不可靠的，我们会遇到媒体故障。

我们遇到了传输错误。我们该如何处理？我们如何使它们可靠？

设备是不可靠的或者运行缓慢。如果我们不知道它们会做什么或何时发生，我们该如何管理它们？

所以，这里有意思的地方是，如果你还记得学期开始时我们谈到的那个虚拟机抽象的想法，我们要做的就是给程序员一个虚拟抽象，使得他们看起来像是拥有无限的内存，所有设备都是完美的。

因此，他们不必编程去担心所有这些混乱的物理细节。好吧，那一开始的确是一个梗，对吧？

因此，我们现在回过头来看，看看这些设备的状况。它们都有这些缺点和局限性，我们现在需要做的就是弄清楚如何提出一个非常干净的虚拟API。这样我们就能让编程变得更简单。好的，这就是我们的目标。我们如何以一种有趣的方式虚拟化这些系统。如果你考虑输入输出（IO）。

它这里有很多可能性，对吧，网络通信，存储的磁盘 I/O，固态硬盘（SSD），键盘，鼠标，扬声器，还有所有这些东西。所以显然我们不能涵盖所有 I/O，但我们将讨论操作系统是如何给你一个虚拟化的 I/O 视图。

![](img/69f56b8db82e9345ac24f839eeec2786_33.png)

好的。如果你还记得，当我们讨论 I/O 基础知识时，我们有一个保护边界，所有的 I/O 都埋在这个保护边界下面。例如，在启动某些东西时，我们必须将数据从存储中拉取到内存中。我们可能会进行一些 I/O，处理器在运行的代码有一个虚拟抽象，能够让存储和网络设备看起来像是理想的设备。

好的。所以操作系统在这里，这个红色边界提供了以 I/O 形式的通用 I/O 服务。实际上，我们有这一系列的时间尺度，这是合适的，正如我们之前所讨论的那样。如果你看一下缓存 L1 缓存访问的时间，可能是0.5纳秒，甚至更小，可能是皮秒级别。然后是从加利福尼亚发一个数据包到荷兰再回来，你知道。

可能是150毫秒。看看我做这次计算的速度，对吧。所以，嗯。我们要处理这些不同规模的所有 I/O 子系统。所以，你知道，这里有一个例子，虽然很老，但比如说，Sun Enterprise 6000的设备传输速率。我把这个放上来是因为我觉得它有点有趣，对吧。

基本上，这些设备的性能差异达到12个数量级。12个数量级。所以我们无论提出什么子系统，都必须处理性能差异达到12个数量级的情况。好的。

![](img/69f56b8db82e9345ac24f839eeec2786_35.png)

所以，你知道，另一个图示是 I/O 设备，你能认出来的都是由 I/O 控制器支持的。好的。这些 I/O 控制器将控制设备，操作系统将与 I/O 控制器进行通信。所以我们必须讨论进程是如何通过 I/O 控制器进行读写和访问 I/O 的。I/O 控制器将是帮助我们构建这些接口的中心化组件。

好的。

![](img/69f56b8db82e9345ac24f839eeec2786_37.png)

所以，这里有一个现代系统的例子，系统里有一个处理器。那就是带有大风扇的东西，因为它很热。但它可能有一个桥接器连接到 PCI 总线，可能还有一个 I/O 卡连接到 SCSI 总线，负责与磁盘通信。还可能有扩展总线连接到其他设备，可能有并行端口，也可能有串行端口。

有网络卡连接起来，做非常高效的工作。所以，你知道，图形控制器，所有这些东西都是通过总线网络连接的，并且必须由那个处理器来控制。所以这里有很多有趣的、复杂的东西。对吧？你们中有多少人打开过桌面电脑或者笔记本电脑，看看里面是什么样子？

有多少人做过这个？你们中的任何人？处理器是一个大东西，但还有很多其他东西。对吧？其他的东西都是这样的，所以我们要尝试搞清楚这一点。

![](img/69f56b8db82e9345ac24f839eeec2786_39.png)

这很有意思。好的，顺便说一下，我还是强烈推荐152这门非常棒的课程，它会告诉你处理器内部的工作原理。我以前也教过这门课。那么，总线是什么呢？你知道，像这样，我有一堆带有“总线”字样的东西。那么，总线到底是什么呢？它是一个公共的电缆系统，用于在设备间进行通信，并且附带有协议。好的。

所以总线通常有一些数据线，它有一些地址线，还有一些控制线。好的，协议内容包括，如果有请求，说明“嘿，我需要某个地址的数据”，它会通过总线发送出去。然后有一个响应方说，“嘿，我准备好了，这是你的数据”，然后你就拿到数据了。好的。

所以它的简单理念是，你有一组公共的电缆，然后你将一堆东西插入其中，现在它们都连接在一起。好的。你会发现，离处理器越近，带宽越高，离它们越远，带宽就越低。好的。那么为什么要用总线呢？嗯，总线让你可以通过一组非常简单的电缆连接各种设备。所以总线的优点是它非常灵活。好的，因为你可以进行平方级别的通信。

缺点是，总线一次只能做一件事。不能想象一下，有100人参加的Zoom会议。好的，你不能同时进行100场对话，只能一个接一个。对吧？所以，这是一个缺点，另一个缺点是物理上的，随着你连接的设备越来越多。

你连接到同一组电缆时，电容就越大，所有东西就会运行得更慢。所以从本质上讲，总线是随着你添加的设备越来越多而变慢的，这在物理上是无法避免的。好的。所以总线很好。它们长得像这样，你们都看过，你把一个大卡插进去。

![](img/69f56b8db82e9345ac24f839eeec2786_41.png)

对，接下来在这些电路板下发生的事情是，你知道这些电缆是如何连接的，它们是并行连接的，你可以同时接入许多设备。好的。这对于灵活性来说很棒，但也有缺点，因为速度受限于电容和最慢设备的响应时间。所以如果你有一个响应非常慢的设备，即便是最快的设备也得等那个慢的设备先回应，才能继续。

好吧，总线本身无法帮助我们解决通信中12个数量级的问题。好吧，我们需要做点别的事情，这里我想给出一个提示。我们有靠近处理器的总线，它们真的很短，然后我们有一堆网关，长的总线和网关，通过建立通信的层次结构，我们可以把慢速的部分推向外面。

而且，靠近的快速部分，或许我们能处理那12个数量级的差距。好吧，这就是你们在我们开始讨论这个问题时会看到的内容，例如 PCI。

![](img/69f56b8db82e9345ac24f839eeec2786_43.png)

这是一个旧的总线，对吧，这个总线并不像IDE总线那么旧，但它在2000年左右就已经存在了。好吧，不够快，因此发生的变化是，像PCI Express总线这样的技术出现了。它不再是一个并行总线，而是一个由非常快速的串行通道组成的集合。所以，你可能有100个通道，每个通道都有一个点对点的连接来实现非常快速的通信，但它没有实际的总线。

好吧，所有的通信都是串行的。而且基本上有一种方法可以决定你需要多少串行通道来满足带宽需求，慢速设备不会妨碍快速设备，等等。我们将要讨论的这种抽象方式的成功之一，是当我们开始进入Linux的IO子系统时，他们可以通过稍微修改一些设备驱动程序，从并行的旧式PCI总线转到PCI Express总线，而且这并不是大问题，大多数操作系统不需要知道差异。

一切都变得更快了。好了，这就是我们的目标。我们能否在系统中实现抽象和层次结构，以便处理这12个数量级的不同设备速度呢？好的。

![](img/69f56b8db82e9345ac24f839eeec2786_45.png)

这里是一个典型的PCI架构的例子，这是一个更现代的系统。你有一个CPU，通过主桥连接到一个PCI总线，该总线通过主桥连接到其他PCI总线，最终连接到USB，即通用串行总线。它有一个通信层次结构，接着是SATA，这是典型的磁盘控制器，等等。好吧。那么，处理器是如何与设备通信的呢？在今天结束之前，我想做几个额外的事情。

但让我们举个例子来说明我所说的通信，因为我认为现在你们都在想，CPU与硬盘之间的通信是合理的，但这到底是什么意思呢？好了，让我们稍微深入一点，花几分钟时间探讨一下。

这是一个CPU，旁边有一个处理器内存总线与内存进行通信。实际上，这意味着，想象一下内存，什么是内存？内存是一个大存储池。你提供一个地址，它会返回一些数据，对吧？或者如果你在写入数据，你会说“这是一个地址，给我一些数据，放入内存中”。所以。

对我们来说，从CPU到内存通常需要数据路径和地址路径。对吧？为了避免我之前提到的电容问题，我们希望这些路径非常短，并且不要有太多设备连接在总线上。好的。所以我们通常会这样做，那个非常快速访问内存的总线有一堆适配器。

然后，这些适配器连接到其他总线，这些总线连接到典型的设备。所以我们在这里做的第一件事是把设备从内存中分离出来，因为内存并不是处理器所做的大部分工作中的关键路径。好的，所以我们有少量的这些总线适配器来与设备通信，设备通常看起来是这样的，里面有一个控制卡。它有一个与某些总线连接的接口，可以生成中断。

它有一个控制器，接收通过这个接口传来的命令。如果这是一个显示控制器，它可能会做一些事情，比如在屏幕上快速绘制三角形。对吧？如果这是一个做得非常适合游戏的显示设备，那么它可能会有一些硬件，可以接收三角形列表，并进行快速的3D渲染。

好的，这种硬件可以在控制器内部。好的。但是从CPU到控制器的这个接口通常非常简单。好的，它是一个芯片，是一组地址，代表对该设备的命令。好的。所以CPU与控制器进行交互，控制器有一组寄存器。我在这里展示它们。

那些寄存器你通常就像访问内存一样读取和写入。当你读取或写入这些内存时，你会了解设备的状态。如果你读取它，或者如果你写入它，你可能会说，继续绘制那些三角形。好的，所以控制接口是在CPU和一组明显的寄存器之间。当你读取和写入它们时，暂停控制就会发生。

可能会有一大堆内存，你可以像访问普通内存那样访问它。所以在显示器本身上，可能会有一大堆内存代表渲染的图像。你可以对它进行读写操作，以查看像素的显示效果。好的。接下来，我们会更详细地讨论这一切是如何工作的。举个例子。

至少有两种完全不同的方式让CPU与设备通信。我们会更详细地讨论这一点。一种是非常传统的方式，其中CPU执行所谓的端口映射I/O指令，你对特定地址进行in和out操作，访问特定的寄存器。好的，第二种方式是目前在一系列设备中更为常见的，它被称为内存映射。

就在那里，如果你想象一下我之前给你展示的地址空间。好了，翻到物理空间，物理空间中有一些部分包含设备。通过在物理空间中读写，我实际上会在设备上引发一些操作。所以，下次我们将更加详细地阐述这个接口。

然后我们将开始讨论一些有趣的设备，特别是存储设备。

![](img/69f56b8db82e9345ac24f839eeec2786_47.png)

让我们谈谈磁盘。好了，总结一下，我们一直在讨论，开始讨论关于I/O设备的类型，这里有很多不同的速度。好了，你知道，从每秒几分之一字节到几千兆字节。我们将讨论很多访问模式和时序。

我们还将更详细地讲解I/O控制器。显然，还有一些通知机制，比如中断和轮询等。好了，然后我们还将讨论设备驱动程序的工作原理。所以，希望你今天余下的时间过得愉快，周四见。

别忘了，明天是撤销请求的截止日期。所以这里有一个问题，关于他在设备上存储的可寻址内存。我们下次会详细讨论这个问题。好吧。

![](img/69f56b8db82e9345ac24f839eeec2786_49.png)

[空白音频]。

![](img/69f56b8db82e9345ac24f839eeec2786_51.png)