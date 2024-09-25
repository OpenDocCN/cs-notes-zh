# 【计算机网络 CS144】斯坦福—中英字幕 - P31：p30 2-6d Finite state machines 4 - 加加zero - BV1qotgeXE8D

![](img/b722cc16ca1d3c2df0cf7fd1160cee9b_0.png)

第二个问题的答案是关闭的，我们从关闭状态开始。

![](img/b722cc16ca1d3c2df0cf7fd1160cee9b_2.png)

然后用户程序调用connect，我们过渡到sin send状态，在sin send状态中。

![](img/b722cc16ca1d3c2df0cf7fd1160cee9b_4.png)

用户程序调用close，所以从sin send到close事件上有一条边回到关闭状态。

![](img/b722cc16ca1d3c2df0cf7fd1160cee9b_6.png)

![](img/b722cc16ca1d3c2df0cf7fd1160cee9b_7.png)

所以现在我们的socket处于建立状态，它们正在交换数据。

![](img/b722cc16ca1d3c2df0cf7fd1160cee9b_9.png)

蓝色框中的六个状态是tcp如何关闭连接，或如何关闭它。

![](img/b722cc16ca1d3c2df0cf7fd1160cee9b_11.png)

谈论关闭连接有时是有用的，因为'关闭'在系统调用中有一个含义。

![](img/b722cc16ca1d3c2df0cf7fd1160cee9b_13.png)

连接在一方关闭它后存在。

![](img/b722cc16ca1d3c2df0cf7fd1160cee9b_15.png)

正如我们将看到的，tcp如何设置连接与如何关闭它存在对称性。

![](img/b722cc16ca1d3c2df0cf7fd1160cee9b_17.png)

其中，连接建立使用同步或发送包，连接关闭使用FIN或发送包。

![](img/b722cc16ca1d3c2df0cf7fd1160cee9b_19.png)

如果连接的任何一方调用close，它将沿着左图的右边缘移动到薄权重的一状态。

![](img/b722cc16ca1d3c2df0cf7fd1160cee9b_21.png)

这使它向连接的另一侧发送一个薄包。

![](img/b722cc16ca1d3c2df0cf7fd1160cee9b_23.png)

这被称为主动关闭者，因为它开始操作。

![](img/b722cc16ca1d3c2df0cf7fd1160cee9b_25.png)

另一方接收FIN并沿着右图的蓝边移动到关闭权重状态。

![](img/b722cc16ca1d3c2df0cf7fd1160cee9b_27.png)

它保持这个状态，直到程序内部调用close。

![](img/b722cc16ca1d3c2df0cf7fd1160cee9b_29.png)

这时它发送FIN。

![](img/b722cc16ca1d3c2df0cf7fd1160cee9b_31.png)

这里是它变得复杂的地方，tcp连接是双向的。

![](img/b722cc16ca1d3c2df0cf7fd1160cee9b_33.png)

主动关闭者已经关闭了连接的方向，所以它不能再写任何数据。

![](img/b722cc16ca1d3c2df0cf7fd1160cee9b_35.png)

但可能是被动关闭者有更多的数据要发送，所以被动关闭者可以继续发送数据，主动关闭者接收并确认。

![](img/b722cc16ca1d3c2df0cf7fd1160cee9b_37.png)

或者它可以关闭自己的一方。

![](img/b722cc16ca1d3c2df0cf7fd1160cee9b_39.png)

或者甚至可能决定在同一时间关闭连接。

![](img/b722cc16ca1d3c2df0cf7fd1160cee9b_41.png)

这样我们在网络上就有两个薄包从in权重一状态交叉，其中，主动关闭者是。

![](img/b722cc16ca1d3c2df0cf7fd1160cee9b_43.png)

![](img/b722cc16ca1d3c2df0cf7fd1160cee9b_44.png)

有三种可能的结果，首先。

![](img/b722cc16ca1d3c2df0cf7fd1160cee9b_46.png)

被动关闭者可能承认FIN但不发送FIN，在这种情况下。

![](img/b722cc16ca1d3c2df0cf7fd1160cee9b_48.png)

被动关闭者处于关闭等待状态并可以继续发送数据，这是主动关闭者进入fin权重二状态的最低边缘。

![](img/b722cc16ca1d3c2df0cf7fd1160cee9b_50.png)

其次。

![](img/b722cc16ca1d3c2df0cf7fd1160cee9b_52.png)

被动关闭者也可能关闭自己的一方，承认FIN并发送自己的发IN。

![](img/b722cc16ca1d3c2df0cf7fd1160cee9b_54.png)

这是到time权重状态的中间边缘。

![](img/b722cc16ca1d3c2df0cf7fd1160cee9b_56.png)

最后，可能是双方几乎同时主动关闭，并发送FIN给对方，在这种情况下，双方都在fin权重一状态。

![](img/b722cc16ca1d3c2df0cf7fd1160cee9b_58.png)

![](img/b722cc16ca1d3c2df0cf7fd1160cee9b_59.png)

每个一方都会看到来自另一方的不作为其自己FIN的FIN，在这种情况下，我们过渡到关闭状态。

![](img/b722cc16ca1d3c2df0cf7fd1160cee9b_61.png)

当我们的FIN被确认时。

![](img/b722cc16ca1d3c2df0cf7fd1160cee9b_63.png)

我们的FIN被确认，我们切换到时间加权状态，就像中间边缘一样。

![](img/b722cc16ca1d3c2df0cf7fd1160cee9b_65.png)

Tcp从权重状态切换到时间权重状态。

![](img/b722cc16ca1d3c2df0cf7fd1160cee9b_67.png)

当我们从另一方收到FIN时，然后它保持在时间状态，等待一段时间，直到它可以安全地切换到关闭状态。

![](img/b722cc16ca1d3c2df0cf7fd1160cee9b_69.png)

从最后一幕到关闭的最后一条蓝色边缘发生在被动关闭者的FIN被确认时。

![](img/b722cc16ca1d3c2df0cf7fd1160cee9b_71.png)

![](img/b722cc16ca1d3c2df0cf7fd1160cee9b_72.png)

现在，一方面，这是一个大量的细节，有十二个状态，覆盖了许多情况。

![](img/b722cc16ca1d3c2df0cf7fd1160cee9b_74.png)

但我希望你可以看到，这个有限状态机如何使先前的。

![](img/b722cc16ca1d3c2df0cf7fd1160cee9b_76.png)

一些口语描述，并给它们细节和精确度，试图实现一个正确中断的tcp，基于描述将非常困难。

![](img/b722cc16ca1d3c2df0cf7fd1160cee9b_78.png)

这个图表精确地指定tcp的行为。

![](img/b722cc16ca1d3c2df0cf7fd1160cee9b_80.png)

![](img/b722cc16ca1d3c2df0cf7fd1160cee9b_81.png)