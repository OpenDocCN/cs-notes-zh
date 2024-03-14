# 8\.   系统

> 原文：[`introcs.cs.princeton.edu/java/80systems`](https://introcs.cs.princeton.edu/java/80systems)
> 
> 译者：[飞龙](https://github.com/wizardforcel)
> 
> 协议：[CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/)


这一章节正在进行重大改造。

到目前为止，我们知道计算机是什么以及它是如何构建的。我们还知道如何编写 Java 程序来解决有趣的问题。在本节中，我们将通过"揭秘 Java 抽象"来连接这两个概念。关于数据表示的细节，包括链表和对象；编译器、解释器和虚拟机；内存和进程管理；操作系统、网络和常见应用程序，如文字处理器和浏览器。

*系统*使我们能够以高度抽象的方式与计算机进行交互。我们描述了支持编程的计算机系统的基本组件；用于与我们的程序和数据进行交互的操作系统；允许计算机之间进行交互的网络；以及为特定任务提供专门支持的应用系统。
