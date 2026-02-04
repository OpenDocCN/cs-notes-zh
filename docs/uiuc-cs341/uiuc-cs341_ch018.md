# 死后报告（Post Mortems）

本章旨在作为一个大型的“我们为什么要学习所有这些”的解答。在你之前的所有课程中，你都在学习如何去做。如何编程一个数据结构，如何编写一个 for 循环，如何证明某事。这是第一堂主要关注**不**做什么的课程。因此，我们从过去的经历中获得了真正的经验。坐下来，随着我们讲述过去程序员的难题，浏览这一章。即使你处理的是像网页开发这样更高级别的事情，一切最终都关联到系统。

## 壳击（Shell Shock）

必需条件：附录/Shell

这是一条进入大多数壳的后门。这个漏洞允许攻击者利用环境变量来执行任意代码。

```c
$ env x='() { :;}; echo vulnerable' bash -c "echo this is a test"
vulnerable...
```

这意味着在任何一个使用环境变量且不对其输入进行清理（提示：没有人清理环境变量输入，因为他们认为它是安全的）的系统上，你都可以在其他人的机器上执行你想要的任何代码，包括设置一个网络服务器。

经验教训：在生产机器上，确保有一个最小的操作系统（例如带有 DietLibc 的 BusyBox），这样你就可以理解系统中的大部分代码及其有效性。添加多层抽象和检查，以确保数据不会泄露。例如，上述问题在于如果允许与攻击者通信，信息就会返回给攻击者。这意味着你可以通过只允许少数端口的连接来加固你的机器端口。此外，你可以加固你的系统，使其永远不会执行 exec 调用以执行任务（即执行 exec 调用以更新值），而是使用 C 或你喜欢的编程语言来完成。虽然你没有灵活性，但你对自己的用户可以做什么有了安全感。

## 心脏出血（Heartbleed）

必需条件：C 语言入门

简单来说，缓冲区检查没有限制。SSL 心跳非常简单。服务器发送一个特定长度的字符串，第二个服务器应该发送相同长度的字符串回来。问题是有人可以恶意地改变请求的大小，使其大于他们发送的大小（例如发送“cat”但请求 500 字节），从而从服务器获取关键信息，如密码。关于这个问题的[相关 XKCD](https://xkcd.com/1354/)。

经验教训：检查你的缓冲区！了解缓冲区和字符串之间的区别。

## 污点牛（Dirty Cow）

必需条件：进程/虚拟内存

[污点牛（Dirty Cow）](https://en.wikipedia.org/wiki/Dirty_COW)

通常，进程可以访问一组只读的内存映射，如果它们尝试写入，则会得到一个段错误。脏 COW 是一种漏洞，其中许多线程试图同时访问同一块内存，希望其中一个线程翻转 NX 位和可写位。之后，攻击者可以修改页面。这可以做到有效用户 ID 位，进程可以假装它以 root 身份运行并启动 root shell，从而允许从普通 shell 访问系统。

学到的教训：内核中的自旋锁很难。

## 熔毁

在背景部分有一个这样的例子

## 漏洞

在安全部分进行检查。

## 火星路径探测器

必要部分：同步和一点调度

[Pathfinder Link](https://www.microsoft.com/en-us/research/people/mbj/#!just-for-fun)

火星路径探测器是一项试图收集火星气候数据的任务。探测器使用单个总线与不同部分通信。由于这是 1997 年，硬件本身没有像高效锁定这样的高级功能，因此操作系统开发者必须使用互斥锁来规范。架构相当简单。有一个线程控制信息总线上的数据，通信线程和数据收集线程，根据调度的高、常规和低优先级。另一个注意事项是，如果某个间隔发生中断，一个任务正在运行，而另一个任务需要调度，那么具有更高优先级的任务获胜。

导致一切开始失败的模式是数据收集线程开始向总线写入，信息总线线程正在等待数据。然后通信线程进来抢占其他低优先级线程**而低优先级线程仍然持有互斥锁**。这意味着当常规优先级线程尝试锁定总线时，漫游车会死锁。经过一段时间后，系统会重置，但不好留给机会。

这个教训是什么？不要让应用程序本身处理同步。定义一个处理互斥锁定的模块，并让该模块通过文件、IPC 等方式进行通信。

## 火星再次

必要部分：内存分配

[火星](https://www.computerworld.com/article/2574759/data-storage-solutions/out-of-memory-problem-caused-mars-rover-s-glitch.html)

简而言之，他们用完了内存。详细来说，他们用完了内存、磁盘空间和交换空间。这个故事告诉我们什么？确保编写能够处理文件故障，并在关闭和内存不足时处理文件的代码，这样操作系统就可以热交换文件以释放内存。还要清理文件，假设你的临时目录大约是总大小的百分之一或千分之一，并使用它。

## 2038 年

必要部分：C 语言简介

[2038](https://en.wikipedia.org/wiki/Year_2038_problem)

这是一个尚未发生的问题。Unix 时间戳被保存为从特定一天（1970 年 1 月 1 日）开始的秒数。这被存储为一个 32 位有符号整数。到 2038 年 3 月，这个数字将溢出。对于大多数现代操作系统来说，这不是问题，因为它们存储 64 位有符号整数，这足以让我们持续到时间的尽头，但对于我们无法更改内部硬件的嵌入式设备来说，这是一个问题。请继续关注，看看会发生什么。

得到的教训：像你的应用程序有一天会变得很大一样进行规划。

## 2003 年东北大停电

必须包含的章节：同步

[2003](https://en.wikipedia.org/wiki/Northeast_blackout_of_2003)

一个竞争条件触发了一系列未定义的事件，导致北美东北大部分地区停电了相当长一段时间。这个错误还导致备份系统和日志系统关闭或失败，以至于人们一个小时都不知道有这个错误。确切翻转的位未知，但已经实施了补丁。

得到的教训：将代码模块化以定位故障（即保持进程间的竞争条件不同）。如果你需要在进程间进行同步，确保你的故障检测系统不会与你的系统交织在一起。

## 苹果 iOS Unicode 处理

必须包含的章节：C 语言入门

[使用文本让你的 iPhone 崩溃](http://appleinsider.com/articles/15/05/26/bug-in-ios-notifications-handling-crashes-iphones-with-a-simple-text)

为什么我们要教授字符串解析？因为即使是专业的软件开发者，这也是一件很难做到的事情。这个错误在尝试解析一系列 Unicode 字符时允许了大量的未定义行为。苹果可能知道为什么会发生这种情况，但我们的猜测是字符串解析发生在内核内部，并达到了段错误。当你内核中出现段错误时，你的内核会崩溃，整个设备会重新启动。未定义行为意味着任何事情，而且这个错误导致了大量不同的事情发生。

得到的教训：模糊你的内核

## 苹果 SSL 验证

必须包含的章节：C 语言入门

[苹果 Bug](https://en.wikipedia.org/wiki/Unreachable_code#Examples)

由于苹果代码中的一个 goto 错误，一个函数总是返回 SSL 证书有效。自然，黑客能够使用一些相当疯狂的网站名称逃脱。

得到的教训：始终括号括起 if 语句，谨慎使用 goto。如果你需要使用 goto，写另一个函数或带有贯穿的 switch 语句（仍然不好）。

## 索尼 Rootkit 安装

必须包含的章节：C 语言入门/进程

[Root Kit 丑闻](https://en.wikipedia.org/wiki/Sony_BMG_copy_protection_rootkit_scandal)

想象一下。那是 2005 年，Limewire 在几年前出现，互联网是一个不断增长的非法活动池——当然，现在并不是说这个问题已经解决了。索尼知道它没有足够的计算能力来监控整个互联网或绕过人们用来绕过版权保护的各种技术。那么他们做了什么？拥有 2200 万张音乐 CD，他们要求用户在操作系统上安装一个 rootkit，这样索尼就可以监控设备上的不道德行为。

除了隐私问题之外，相信我，有很多，最大的问题是如果 rootkit 编程不正确，它将成为每个人系统的后门。rootkit 是一段通常安装在内核侧的代码，它跟踪用户几乎做的任何事情。访问了哪些网站，点击了什么或按了什么键等。如果黑客发现这一点，并且有从用户空间级别访问该 API 的方法，这意味着任何程序都可以发现有关你的设备的重要信息。不用说，人们都很愤怒。

经验教训：安装一个杀毒软件和/或 apparmor，并确保应用程序只请求合理的权限。如果你犹豫不决，可以尝试使用 Windows 沙盒或保留一个牺牲的虚拟机来测试安装它是否会使你的电脑变得糟糕。不要信任证书，信任代码。

## 文明与甘地

必需章节：C 语言简介

[甘地的侵略性](https://www.geek.com/games/why-gandhi-is-always-a-warmongering-jerk-in-civilization-1608515/)

这可能是游戏玩家都知道的，为什么像甘地这样在现实生活中非暴力的角色在文明视频游戏中会表现得如此具有侵略性。在原始游戏中，游戏将侵略性保持为无符号整数。在游戏过程中，整数可以递减，然后由于甘地已经为零，问题就出现了。这导致他成为游戏中最具侵略性的角色。

经验教训：从这个教训中得出的结论是**永远**不要使用未签名的数字，除非你有明确的书面理由（理由包括你需要了解溢出行为，你正在进行位操作，你正在进行位掩码）。在其他所有情况下，进行类型转换。

## Shell 脚本之苦

必需章节：C 语言简介/Appending

[Steam](https://www.pcworld.com/article/2871653/scary-steam-for-linux-bug-erases-all-the-personal-files-on-your-pc.html)

Steam 中有一个简单的错误，导致 Steam 以类似以下方式删除了你的所有文件

```c
$ ROOT=$(cd $0/; echo $PWD);
$ rm -rf $ROOT
```

如果$0 或传递给脚本的第一个参数不存在会发生什么？你会变成 root 用户，并删除你的整个电脑。

经验教训：在脚本上始终进行参数检查，如果你预期某个命令会失败，请明确列出它。你还可以将 rm 别名设置为 mv，然后稍后删除垃圾文件。

## Appnexus 双重释放

必需章节：C 语言简介/Malloc

[双重释放](https://techblog.appnexus.com/2013-09-17-outage-postmortem-586b19ae4307)

Appnexus 使用异步垃圾回收器，当它认为对象未被使用时，会回收堆的不同部分。其架构是，一个元素在不可用列表中，然后被移到待释放列表中。如果在一定时间内该元素未被使用，它就会被释放并添加到空闲列表中。这很好，直到两个线程同时尝试删除同一个对象，将其添加到列表中两次。在更短的时间内，其中一个对象被删除，删除操作被通知到其他计算机。

经验教训：如果你需要，避免制作黑客软件。模块化，设置内存限制，并监控代码的不同部分，然后手动优化。没有通用的万能垃圾回收器适合所有人。即使是高度测试的 JVM，如果你想要从中获得性能，也需要一些推动。

## ATT 级联故障 - 1990

必要章节：C 语言简介

[解释](http://users.csc.calpoly.edu/~jdalbey/SWE/Papers/att_collapse.html)

错误在上面的链接中解释得很好。我们建议阅读以了解更多信息。一系列网络延迟导致全国一些电话交换机认为其他交换机在它们不可用时是可操作的。当交换机重新上线时，它们意识到它们有大量的待路由电话，并开始这样做。其他路由故障和重启只是使问题更加复杂。

经验教训：实际上在这里不使用 C 语言可能会有所帮助，因为更严格的模糊测试（尽管在当今时代，C++由于其语言结构可能会更糟）。这个故事真正的教训是网络是随机的，并且预期代码中的任何一点都可能发生跳跃。这意味着编写模拟并在它们发生之前通过随机延迟运行它们来找出错误。

“4. Memcheck：内存错误检测器。”不详。*Valgrind*。[`valgrind.org/docs/manual/mc-manual.html`](http://valgrind.org/docs/manual/mc-manual.html)。

“断言。”不详。*Cplusplus.com*. cplusplus.com. [`www.cplusplus.com/reference/cassert/assert/`](http://www.cplusplus.com/reference/cassert/assert/)

Bovet, Daniel，和 Marco Cesati. 2005. *理解 Linux 内核*. O'Reilly & Associates Inc.

Chandy, K. M.，和 J. Misra. 1984. “饮酒者问题。” *ACM 程序设计语言系统（ACM Trans. Program. Lang. Syst.）* 6 (4): 632–46。[`doi.org/10.1145/1780.1804`](https://doi.org/10.1145/1780.1804)。

“第三章：硬件中断。”不详。*第三章：硬件中断*。Red Hat。[`access.redhat.com/documentation/en-US/Red_Hat_Enterprise_MRG/1.3/html/Realtime_Reference_Guide/chap-Realtime_Reference_Guide-Hardware_interrupts.html`](https://access.redhat.com/documentation/en-US/Red_Hat_Enterprise_MRG/1.3/html/Realtime_Reference_Guide/chap-Realtime_Reference_Guide-Hardware_interrupts.html)。

Coffman, Edward G，Melanie Elphick，和 Arie Shoshani. 1971. “系统死锁。” *ACM 计算调查（CSUR）* 3 (2): 67–78.

Cohen, Danny. 1980\. “关于圣战和和平呼吁。” *IETF*。IETF。 [`www.ietf.org/rfc/ien/ien137.txt`](https://www.ietf.org/rfc/ien/ien137.txt).

Conway, R.W., W.L. Maxwell, and L.W. Miller. 1967\. *调度理论*。Addison-Wesley 出版公司。 [`books.google.com/books?id=CSozAAAAMAAJ`](https://books.google.com/books?id=CSozAAAAMAAJ).

“DEC Pdp-10 Ka10 控制面板。” n.d. *RICM*。RICM。 [`www.ricomputermuseum.org/Home/interesting_computer_items/dec-pdp-ka10`](http://www.ricomputermuseum.org/Home/interesting_computer_items/dec-pdp-ka10).

“定义。” 2018\. *开放组基础规范第 7 版，2018 年版*。开放组/IEEE。 [`pubs.opengroup.org/onlinepubs/9699919799/basedefs/V1_chap03.html#tag_03_210`](http://pubs.opengroup.org/onlinepubs/9699919799/basedefs/V1_chap03.html#tag_03_210).

Dekker, T.J., and Edsgar Dijkstra. 1965\. “关于进程描述的顺序性。” *E.W.Dijkstra 档案：关于进程描述的顺序性 (EWD 35)*。德克萨斯大学奥斯汀分校。 [`www.cs.utexas.edu/users/EWD/transcriptions/EWD00xx/EWD35.html`](http://www.cs.utexas.edu/users/EWD/transcriptions/EWD00xx/EWD35.html).

Dijkstra, Edsger W. n.d. “顺序进程的分层排序。” [`www.cs.utexas.edu/users/EWD/ewd03xx/EWD310.PDF`](http://www.cs.utexas.edu/users/EWD/ewd03xx/EWD310.PDF).

Duff, Tom. n.d. “Tom Duff 关于 Duff 设备。” *Tom Duff 关于 Duff 设备*。 [`www.lysator.liu.se/c/duffs-device.html`](https://www.lysator.liu.se/c/duffs-device.html).

“环境变量。” 2018\. *环境变量*。开放组/IEEE。 [`pubs.opengroup.org/onlinepubs/9699919799/basedefs/V1_chap08.html`](https://pubs.opengroup.org/onlinepubs/9699919799/basedefs/V1_chap08.html).

Evans, Julia. 2018\. “文件描述符。” *Julia 的绘画*。Julia Evans。 [`drawings.jvns.ca/file-descriptors/`](https://drawings.jvns.ca/file-descriptors/).

“Exec。” 2018\. *Exec*。开放组/IEEE。 [`pubs.opengroup.org/onlinepubs/9699919799/functions/exec.html`](https://pubs.opengroup.org/onlinepubs/9699919799/functions/exec.html).

“执行文件。” n.d. *执行文件 (GNU C 库)*。GNU 项目。 [`www.gnu.org/software/libc/manual/html_node/Executing-a-File.html#Executing-a-File`](https://www.gnu.org/software/libc/manual/html_node/Executing-a-File.html#Executing-a-File).

Fielding, Roy T., and Julian Reschke. 2014\. “超文本传输协议 (HTTP/1.1): 语义和内容。” 请求评论。RFC 7231；RFC 编辑。 [`doi.org/10.17487/RFC7231`](https://doi.org/10.17487/RFC7231).

“Fork。” 2018\. *Fork*。开放组/IEEE。 [`pubs.opengroup.org/onlinepubs/9699919799/functions/fork.html`](https://pubs.opengroup.org/onlinepubs/9699919799/functions/fork.html).

“FORTRAN IV 程序员参考手册.” 1972. 手册. 马萨诸塞州梅纳德: 数字设备公司. [`www.bitsavers.org/www.computer.museum.uq.edu.au/pdf/DEC-10-AFDO-D%20decsystem10%20FORTRAN%20IV%20Programmer%27s%20Reference%20Manual.pdf`](http://www.bitsavers.org/www.computer.museum.uq.edu.au/pdf/DEC-10-AFDO-D%20decsystem10%20FORTRAN%20IV%20Programmer%27s%20Reference%20Manual.pdf).

加雷，M. R.，R. L. 格拉汉姆，和 J. D. 乌尔曼. 1972. “内存分配算法的最坏情况分析.” 在 *第四届年度 ACM 计算机理论研讨会论文集*，143–50. STOC ‘72. 纽约，纽约，美国: ACM. [`doi.org/10.1145/800152.804907`](https://doi.org/10.1145/800152.804907).

加尔，马努. 2006. “Linux 2.6 中的 Sysenter 基于的系统调用机制.” *马努的公开文章和项目*. [`articles.manugarg.com/systemcallinlinux2_6.html`](http://articles.manugarg.com/systemcallinlinux2_6.html).

“GDB: GNU 项目调试器.” 2019. *GDB: GNU 项目调试器*. 自由软件基金会. [`www.gnu.org/software/gdb/`](https://www.gnu.org/software/gdb/).

指南，部分. 2011. “Intel 64 和 IA-32 架构软件开发者手册.” *第 3B 卷：系统编程指南，部分* 2.

哈尔科尔-巴尔特，M. 2013. *计算机系统性能建模与设计：排队论的实际应用*. 计算机系统性能建模与设计：排队论的实际应用. 剑桥大学出版社. [`books.google.com/books?id=75SbigDGK0kC`](https://books.google.com/books?id=75SbigDGK0kC).

海曼，哈里斯. 1966. “关于并发程序控制中问题的评论.” *Commun. ACM* 9 (1): 45. [`doi.org/10.1145/365153.365167`](https://doi.org/10.1145/365153.365167).

(IBM)，国际商业机器公司. 1958 年 8 月. *IBM 709 数据处理系统参考手册*. 国际商业机器公司 (IBM). [`archive.computerhistory.org/resources/text/Fortran/102653991.05.01.acc.pdf`](http://archive.computerhistory.org/resources/text/Fortran/102653991.05.01.acc.pdf).

“IEEE 浮点运算标准.” 2008. *IEEE Std 754-2008*, 八月, 1–70. [`doi.org/10.1109/IEEESTD.2008.4610935`](https://doi.org/10.1109/IEEESTD.2008.4610935).

Inc., 苹果公司. 2017. “XNU 内核.” *GitHub 仓库*. [`github.com/apple/darwin-xnu`](https://github.com/apple/darwin-xnu); GitHub.

英特尔，CAT. 2015. “通过利用缓存分配技术提高实时性能.” *英特尔公司，四月*. 

“国际.” 不定日期. *IEC*. IEC. [`www.iec.ch/si/binary.htm`](https://www.iec.ch/si/binary.htm).

“ISO C 标准.” 2005. 标准. 日内瓦，瑞士: 国际标准化组织. [`www.open-std.org/jtc1/sc22/wg14/www/docs/n1124.pdf`](http://www.open-std.org/jtc1/sc22/wg14/www/docs/n1124.pdf).

琼斯，拉里. 2010. “WG14 N1539 委员会草案 Iso/Iec 9899: 201x.” 国际标准化组织.

Kernighan, B.W., and D.M. Ritchie. 1988\. *C 编程语言*. 普伦蒂斯-霍尔计算机软件系列。普伦蒂斯-霍尔。[`books.google.com/books?id=161QAAAAMAAJ`](https://books.google.com/books?id=161QAAAAMAAJ).

Knuth, D.E. 1973\. *计算机编程艺术：基础算法*. 阿迪森-韦斯利计算机科学和信息处理系列，第 1-2 卷。阿迪森-韦斯利。[`books.google.com/books?id=dC05RwAACAAJ`](https://books.google.com/books?id=dC05RwAACAAJ).

Kocher, Paul, Daniel Genkin, Daniel Gruss, Werner Haas, Mike Hamburg, Moritz Lipp, Stefan Mangard, Thomas Prescher, Michael Schwarz, and Yuval Yarom. 2018\. “Spectre 攻击：利用推测执行。” *arXiv 预印本 arXiv:1801.01203*.

Leroy, Xavier. 2017\. “我在英特尔 Skylake 处理器中找到的一个错误。” *我在英特尔 Skylake 处理器中找到的一个错误*。[`gallium.inria.fr/blog/intel-skylake-bug/`](http://gallium.inria.fr/blog/intel-skylake-bug/).

Levinthal, David. 2009\. “英特尔酷睿 i7 处理器和英特尔至强 5500 处理器性能分析指南。” *英特尔性能分析指南* 30: 18.

Love, Robert. 2010\. *Linux 内核开发*. 第 3 版。阿迪森-韦斯利专业出版社。

“mmap。” 2018\. *mmap*. 开放集团。[`pubs.opengroup.org/onlinepubs/9699919799/functions/mmap.html`](http://pubs.opengroup.org/onlinepubs/9699919799/functions/mmap.html).

“malloc 概述。” 2018\. *malloc 内部机制 - Glibc Wiki*. 自由软件基金会。[`sourceware.org/glibc/wiki/MallocInternals`](https://sourceware.org/glibc/wiki/MallocInternals).

Peterson, Gary L. 1981\. “关于互斥问题的神话。” *信息处理信件* 12: 115–16.

Rangan, C.P., V. Raman, and R. Ramanujam. 1999\. *软件技术基础与理论计算机科学：第 19 届会议，印度钦奈，1999 年 12 月 13-15 日论文集*。计算机软件技术基础与理论计算机科学。斯普林格。[`books.google.com/books?id=0uHME7EfjQEC`](https://books.google.com/books?id=0uHME7EfjQEC).

Reynolds, J., and J. Postel. 1994\. “分配号码。” RFC 1700\. RFC 编辑；互联网请求评论；RFC 编辑。

Rice, H. G. 1953\. “可递归枚举集的类别及其决策问题。” *美国数学学会汇刊* 74 (2): 358–66\. [`www.jstor.org/stable/1990888`](http://www.jstor.org/stable/1990888).

Ritchie, Dennis M. 1993\. “C 语言的发展。” *SIGPLAN 通知* 28 (3): 201–8\. [`doi.org/10.1145/155360.155580`](https://doi.org/10.1145/155360.155580).

Schweizer, Hermann, Maciej Besta, and Torsten Hoefler. 2015\. “在现代架构上评估原子操作的成本。” 在 *2015 国际并行架构与编译会议 (Pact)* 中，445–56\. IEEE.

Silberschatz, A., P.B. Galvin, and G. Gagne. 2005\. *操作系统概念*. 威利。[`books.google.com/books?id=FH8fAQAAIAAJ`](https://books.google.com/books?id=FH8fAQAAIAAJ).

———. 2006\. *操作系统原理，第 7 版*. Wiley 学生版. Wiley India Pvt. Limited. [`books.google.com/books?id=WjvX0HmVTlMC`](https://books.google.com/books?id=WjvX0HmVTlMC).

“源到 Sys/Wait.h.” 不早于. *Sys/Wait.h 源*. superglobalmegacorp. [`unix.superglobalmegacorp.com/Net2/newsrc/sys/wait.h.html`](http://unix.superglobalmegacorp.com/Net2/newsrc/sys/wait.h.html).

“ssh(1).” 不早于. *OpenBSD 手册页*. OpenBSD. [`man.openbsd.org/ssh.1`](https://man.openbsd.org/ssh.1).

Stallings, William. 2011\. *操作系统：内部结构和设计原理第 7 版. 由 Stallings (国际经济版)*. PE. [`www.amazon.com/Operating-Systems-Internals-Principles-International/dp/9332518807?SubscriptionId=0JYN1NVW651KCA56C102&tag=techkie-20&linkCode=xm2&camp=2025&creative=165953&creativeASIN=9332518807`](https://www.amazon.com/Operating-Systems-Internals-Principles-International/dp/9332518807?SubscriptionId=0JYN1NVW651KCA56C102&tag=techkie-20&linkCode=xm2&camp=2025&creative=165953&creativeASIN=9332518807).

“IPv6 部署状态 2018.” 2018\. *互联网协会*. 互联网协会. [`www.internetsociety.org/resources/2018/state-of-ipv6-deployment-2018/`](https://www.internetsociety.org/resources/2018/state-of-ipv6-deployment-2018/).

Šorn, Jure. 2015\. “Gto76/Comp-Cpp.” *GitHub*. [`github.com/gto76/comp-cpp/blob/1bf9a77eaf8f57f7358a316e5bbada97f2dc8987/src/output.c`](https://github.com/gto76/comp-cpp/blob/1bf9a77eaf8f57f7358a316e5bbada97f2dc8987/src/output.c).

“ThreadSanitizerCppManual.” 2018\. *ThreadSanitizerCppManual*. Google. [`github.com/google/sanitizers/wiki/ThreadSanitizerCppManual`](https://github.com/google/sanitizers/wiki/ThreadSanitizerCppManual).

“用户数据报协议.” 1980\. 请求评论. RFC 768；RFC 编辑器. [`doi.org/10.17487/RFC0768`](https://doi.org/10.17487/RFC0768).

Van der Linden, Peter. 1994\. *专家 C 编程：深层次 C 秘密*. Prentice Hall 专业版.

Virtamo, Jorma. 不早于. “38.3143 排队论 / Them/G/1/Queue.” *38.3143 排队论 / TheM/G/1/Queue*. 阿尔托大学. [`www.netlab.tkk.fi/opetus/s383143/kalvot/E_mg1jono.pdf`](https://www.netlab.tkk.fi/opetus/s383143/kalvot/E_mg1jono.pdf).

“虚拟内存分配和分页.” 2001\. *GNU C 库 - 虚拟内存分配和分页*. 自由软件基金会. [`ftp.gnu.org/old-gnu/Manuals/glibc-2.2.3/html_chapter/libc_3.html`](https://ftp.gnu.org/old-gnu/Manuals/glibc-2.2.3/html_chapter/libc_3.html).

Wikibooks. 2018\. “x86 汇编 — Wikibooks，免费教科书项目.” [`en.wikibooks.org/w/index.php?title=X86_Assembly&oldid=3477563`](https://en.wikibooks.org/w/index.php?title=X86_Assembly&oldid=3477563).

Wilson, Paul R., Mark S. Johnstone, Michael Neely, and David Boles. 1995\. “动态存储分配：综述与批判性评论.” 在 *内存管理*，由 Henry G. Baler 编著，1–116\. 柏林，海德堡：Springer Berlin Heidelberg.

n.d. IEEE. [`pubs.opengroup.org/onlinepubs/009695399/functions/pthread_sigmask.html`](http://pubs.opengroup.org/onlinepubs/009695399/functions/pthread_sigmask.html).
