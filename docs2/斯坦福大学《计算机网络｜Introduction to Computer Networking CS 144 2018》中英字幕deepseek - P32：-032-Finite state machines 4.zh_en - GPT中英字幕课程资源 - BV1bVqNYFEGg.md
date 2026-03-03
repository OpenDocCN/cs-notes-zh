# 斯坦福大学《计算机网络｜Introduction to Computer Networking CS 144 2018》中英字幕deepseek - P32：-032-Finite state machines 4.zh_en - GPT中英字幕课程资源 - BV1bVqNYFEGg

The answer to the second question is closed。

![](img/a28aaee3eb88032635702acce8b1878d_1.png)

We start in the closed state， then the user program calls connect and we transition to the S S state。



![](img/a28aaee3eb88032635702acce8b1878d_3.png)

While in the SinNS state， the user program calls close。



![](img/a28aaee3eb88032635702acce8b1878d_5.png)

So there's an edge from Scent on the close event。

![](img/a28aaee3eb88032635702acce8b1878d_7.png)

Back to the closed state。

![](img/a28aaee3eb88032635702acce8b1878d_9.png)

So now our sockets are in the established state， they're exchanging data。

 the six states in blue boxes are how TCP tears down a connection or how it closes it。



![](img/a28aaee3eb88032635702acce8b1878d_11.png)

![](img/a28aaee3eb88032635702acce8b1878d_12.png)

It's sometimes useful to talk about tearing down a connection because the word close means something in terms of system calls a connection exists after one side closes it。

 as we'll see。

![](img/a28aaee3eb88032635702acce8b1878d_14.png)

![](img/a28aaee3eb88032635702acce8b1878d_15.png)

There's symmetry between how TCP sets up a connection and how it tears it down。



![](img/a28aaee3eb88032635702acce8b1878d_17.png)

Where connection establishment uses synchronization or S packets。

 connection tearraan uses Finnish or fin packets。

![](img/a28aaee3eb88032635702acce8b1878d_19.png)

![](img/a28aaee3eb88032635702acce8b1878d_20.png)

If one of the sides of the connection calls close， itvers along the right edge on the left to the thin weight one state。



![](img/a28aaee3eb88032635702acce8b1878d_22.png)

This caused it to send a thin packet to the other side of the connection。



![](img/a28aaee3eb88032635702acce8b1878d_24.png)

This is called the active closer because it starts the operation。



![](img/a28aaee3eb88032635702acce8b1878d_26.png)

The other side receives the f and takes the blue edge on the right to the closed weight state。



![](img/a28aaee3eb88032635702acce8b1878d_28.png)

It remains in this state until the program site calls close at which point it sends a fin。



![](img/a28aaee3eb88032635702acce8b1878d_30.png)

Here's where it gets a little complicated。

![](img/a28aaee3eb88032635702acce8b1878d_32.png)

A TCP connection is bidirectional， the active closer has closed its direction of the connection。

 so it can't write any more data。

![](img/a28aaee3eb88032635702acce8b1878d_34.png)

But it could be the passive closer has more data to send。

 so the passive closer can continue to send data， which the active closer receives and acknowledges。

 or it could close its side of the connection too。

![](img/a28aaee3eb88032635702acce8b1878d_36.png)

![](img/a28aaee3eb88032635702acce8b1878d_37.png)

![](img/a28aaee3eb88032635702acce8b1878d_38.png)

Or it could even have decided to close that connection at the same time。

 such that we have two fin packets crossing each other in the network。



![](img/a28aaee3eb88032635702acce8b1878d_40.png)

From the thin weight one state。

![](img/a28aaee3eb88032635702acce8b1878d_42.png)

Where the active closure is， there are three possible outcomes。



![](img/a28aaee3eb88032635702acce8b1878d_44.png)

First， the passive closer might acknowledge the f but not send a f。



![](img/a28aaee3eb88032635702acce8b1878d_46.png)

In this case， the passive closure is in the closed weight state and can continue to send data。



![](img/a28aaee3eb88032635702acce8b1878d_48.png)

This is the lowermost edge where the active closer enters the thin weight2 state。



![](img/a28aaee3eb88032635702acce8b1878d_50.png)

Second， the passive closer might close its side too。



![](img/a28aaee3eb88032635702acce8b1878d_52.png)

Acknowledging the f and sending a fin of its own。 This is the middle edge to the time weight state。



![](img/a28aaee3eb88032635702acce8b1878d_54.png)

Finally， it could be that both sides actively closed at almost the same time and send fins to each other。

 In this case， both are in the Finnin weight one state。😊。



![](img/a28aaee3eb88032635702acce8b1878d_56.png)

![](img/a28aaee3eb88032635702acce8b1878d_57.png)

Each one will see a fin from the other side that doesn't act its own f。 In this case。

 we transition to the closing state， and when our fin is acknowledged。

 we transition to the time weight state just as with the middle edge。



![](img/a28aaee3eb88032635702acce8b1878d_59.png)

![](img/a28aaee3eb88032635702acce8b1878d_60.png)

![](img/a28aaee3eb88032635702acce8b1878d_61.png)

TCP transitions from thin weight2 to time weight when we receive a fin from the other side。



![](img/a28aaee3eb88032635702acce8b1878d_63.png)

![](img/a28aaee3eb88032635702acce8b1878d_64.png)

It then stays in the time wait for a period of time until it can safely transition to close。



![](img/a28aaee3eb88032635702acce8b1878d_66.png)

The final blue edge from last act to close。Occurs when the passive closers thin is acknowledged。



![](img/a28aaee3eb88032635702acce8b1878d_68.png)

![](img/a28aaee3eb88032635702acce8b1878d_69.png)

![](img/a28aaee3eb88032635702acce8b1878d_70.png)

Now on one hand， that's a lot of detail， there are 12 states covering lots of cases。



![](img/a28aaee3eb88032635702acce8b1878d_72.png)

But I hope you can see how this finitescape machine makes what was previously a few colloquial descriptions and gives them detail and precision。



![](img/a28aaee3eb88032635702acce8b1878d_74.png)

Trying to implement a properly interoperating TCP based on those descriptions would be really hard。



![](img/a28aaee3eb88032635702acce8b1878d_76.png)

![](img/a28aaee3eb88032635702acce8b1878d_77.png)

This diagram precisely specifies how TCP behaves， and so it's tremendously useful。



![](img/a28aaee3eb88032635702acce8b1878d_79.png)

![](img/a28aaee3eb88032635702acce8b1878d_80.png)