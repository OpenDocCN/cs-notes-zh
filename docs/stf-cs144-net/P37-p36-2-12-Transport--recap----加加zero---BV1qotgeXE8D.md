# P37：p36 2-12 Transport (recap) - 加加zero - BV1qotgeXE8D

![](img/073b7f2be6df5be9db5b3a0a6ea28633_0.png)

在这一单元中，你学习了传输层，特别是你学习了今天在用的三个最重要的传输层。

![](img/073b7f2be6df5be9db5b3a0a6ea28633_2.png)

第一个tcp，或传输控制协议被超过九十五 percent的互联网应用使用。

![](img/073b7f2be6df5be9db5b3a0a6ea28633_4.png)

tcp几乎被普遍使用。

![](img/073b7f2be6df5be9db5b3a0a6ea28633_6.png)

因为它提供了几乎所有应用都希望的可靠的端到端的双向字节流服务。

![](img/073b7f2be6df5be9db5b3a0a6ea28633_8.png)

本单元中的大部分视频是关于tcp的，你学习了我们如何检测到一个包在途中未被送达或被损坏。

![](img/073b7f2be6df5be9db5b3a0a6ea28633_10.png)

并学习了tcp用于成功重传数据的机制。

![](img/073b7f2be6df5be9db5b3a0a6ea28633_12.png)

直到正确送达，我们花费了三个视频。

![](img/073b7f2be6df5be9db5b3a0a6ea28633_14.png)

探索了在不同不可靠的互联网上可靠传输数据的不同方法。

![](img/073b7f2be6df5be9db5b3a0a6ea28633_16.png)

我们研究的第二个传输层是udp或用户数据报协议。

![](img/073b7f2be6df5be9db5b3a0a6ea28633_18.png)

udp，由不需要tcp提供的保证交付服务的应用程序使用。

![](img/073b7f2be6df5be9db5b3a0a6ea28633_20.png)

或者是因为应用程序以其私有的方式处理重传。

![](img/073b7f2be6df5be9db5b3a0a6ea28633_22.png)

或者是因为应用程序只需要可靠的交付，udp所做的只是取应用数据并创建udp数据报。

![](img/073b7f2be6df5be9db5b3a0a6ea28633_24.png)

udp数据报标识出数据应该发送到的应用程序。

![](img/073b7f2be6df5be9db5b3a0a6ea28633_26.png)

在另一端，就这些了，尽管很少有应用使用udp。

![](img/073b7f2be6df5be9db5b3a0a6ea28633_28.png)

我们看到了dns和dhcp的例子。

![](img/073b7f2be6df5be9db5b3a0a6ea28633_30.png)

这些都是简单的请求响应查询协议。

![](img/073b7f2be6df5be9db5b3a0a6ea28633_32.png)

![](img/073b7f2be6df5be9db5b3a0a6ea28633_33.png)

icmp的主要工作是在事情出错时发送反馈。

![](img/073b7f2be6df5be9db5b3a0a6ea28633_35.png)

例如，如果路由器接收到一个ip数据包但不知道下一个应该发送到哪里，那么它会发送一个icmp消息回源，让源知道。



![](img/073b7f2be6df5be9db5b3a0a6ea28633_37.png)

"ICMP非常有用，可以帮助我们理解为什么端到端的通信不能有效工作"。

![](img/073b7f2be6df5be9db5b3a0a6ea28633_39.png)

最后，"你学习了指导互联网设计最重要的总体建筑原则之一"。

![](img/073b7f2be6df5be9db5b3a0a6ea28633_41.png)

"并继续引导我们的思考至今"，它被称为端到端原则，我们学习了端到端的两个版本。

![](img/073b7f2be6df5be9db5b3a0a6ea28633_43.png)

较温和的版本说，有些功能只能正确地实现。

![](img/073b7f2be6df5be9db5b3a0a6ea28633_45.png)

"在网络的边缘或边缘地带"，"这些明显需要在那里从头到尾实施"。

![](img/073b7f2be6df5be9db5b3a0a6ea28633_47.png)

"可靠的文件传输和安全是两个我们见过的例子"。

![](img/073b7f2be6df5be9db5b3a0a6ea28633_49.png)

帮助这些特性可以通过为网络添加函数来实现，这是允许的，但这些只能帮助，不能替代端到端的功能。

![](img/073b7f2be6df5be9db5b3a0a6ea28633_51.png)

第二个，端到端原则的更强大版本说，如果我们能在端主机上实现一个功能。

![](img/073b7f2be6df5be9db5b3a0a6ea28633_53.png)

那么我们应该，基本思想是网络应该保持简单。

![](img/073b7f2be6df5be9db5b3a0a6ea28633_55.png)

流畅，以尽可能少的特性去出错，以减缓速度或需要升级。

![](img/073b7f2be6df5be9db5b3a0a6ea28633_57.png)

它假设端主机相当智能，例如，笔记本电脑或智能手机。

![](img/073b7f2be6df5be9db5b3a0a6ea28633_59.png)

并且可以实现应用程序所需的许多功能。

![](img/073b7f2be6df5be9db5b3a0a6ea28633_61.png)

在本单元中，你学习了五个主要主题，一，三种广泛使用的传输层，Tcb用于可靠地将字节流从应用程序传递到应用程序。



![](img/073b7f2be6df5be9db5b3a0a6ea28633_63.png)

Udp是用于在不可靠的应用程序之间传递图表的方式。

![](img/073b7f2be6df5be9db5b3a0a6ea28633_65.png)

并且icp是检测事情出错的一种方法。

![](img/073b7f2be6df5be9db5b3a0a6ea28633_67.png)

二，TCP的工作原理，特别强调了它如何可靠地将字节从两个应用程序之间传递。

![](img/073b7f2be6df5be9db5b3a0a6ea28633_69.png)

您学习了如何检测数据错误和丢失的包。

![](img/073b7f2be6df5be9db5b3a0a6ea28633_71.png)

以及如何重新传输包，以及几种不同的重传策略。

![](img/073b7f2be6df5be9db5b3a0a6ea28633_73.png)

包括选择性，重复并返回，您学习了基本TCP机制如何使用返回，并使用滑动窗口跟踪未确认的未发送字节。

![](img/073b7f2be6df5be9db5b3a0a6ea28633_75.png)

您还学习了TCP状态机，这跟踪TCP连接的当前状态。

![](img/073b7f2be6df5be9db5b3a0a6ea28633_77.png)

三，你学习UDP如何工作。

![](img/073b7f2be6df5be9db5b3a0a6ea28633_79.png)

并解释为什么它被少数应用程序使用，或者我们学习了ICMP如何工作。

![](img/073b7f2be6df5be9db5b3a0a6ea28633_81.png)

并解释它如何帮助我们检测通信中断。

![](img/073b7f2be6df5be9db5b3a0a6ea28633_83.png)

用于监控两个端主机之间的路由性能，你学习了端到端原则，这是互联网设计和许多其他通信系统在整个课程中的重要总体原则。



![](img/073b7f2be6df5be9db5b3a0a6ea28633_85.png)

以及许多其他通信系统。

![](img/073b7f2be6df5be9db5b3a0a6ea28633_87.png)

在你进入世界并利用你的网络专业知识后，你会发现许多人在讨论这个原则来帮助指导他们的设计决策。

![](img/073b7f2be6df5be9db5b3a0a6ea28633_89.png)

![](img/073b7f2be6df5be9db5b3a0a6ea28633_90.png)

所以你现在应该对三个传输层有很好的理解，你应该理解不同的重传策略和tcp为什么使用滑动窗口。

![](img/073b7f2be6df5be9db5b3a0a6ea28633_92.png)

你应该知道tcp为什么使用连接。

![](img/073b7f2be6df5be9db5b3a0a6ea28633_94.png)

它们如何建立，以及维护它们的有限状态机。

![](img/073b7f2be6df5be9db5b3a0a6ea28633_96.png)