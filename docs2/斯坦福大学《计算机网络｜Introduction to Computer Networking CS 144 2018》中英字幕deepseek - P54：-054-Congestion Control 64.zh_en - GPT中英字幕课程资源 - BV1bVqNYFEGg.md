# 斯坦福大学《计算机网络｜Introduction to Computer Networking CS 144 2018》中英字幕deepseek - P54：-054-Congestion Control 64.zh_en - GPT中英字幕课程资源 - BV1bVqNYFEGg

Yeah。So in this unit， we're going to be learning about how to control congestion in networks。

You already know about something called flow control。

 F control is when we try to prevent a sender from overwhelming a receiver。

By the receiver telling the sender to slow down。Congestion control is essentially extending that notion to the network as a whole。

 you can imagine that if senders were to send too many packets into the network。

 they're going to overwhelm the network， the buffers and the routers are going to fill out。

 the links are going to overflow and we're going to start dropping pack。公里 not very good。

So congestion control is about preventing the senders from overwhelming。

So that leads us naturally to ask how do we do it， what do we want from a congestion control mechanism first clearly it needs to prevent the overwhelming from happening and the second thing is we generally want it to spread the pain evenly。

 we want to make sure that all of the flows that are being controlled are being controlled in a fair and equal way。

So one of the big questions that comes up is we want to control congestion， but how should we do it。

 where should we do it， should we do it at the edge， should we do within the network？

Well if we follow the end to end argument。Right， the strong end to end up。

It would say that we want the network to just forward packets。

 and we want the intelligence to be at the edges。And so that's actually in practice often what's done today。

So in this unit we're going to talk about TCP and how TCP controls congestion。

 it turns out it's one of its most important features that a TCP sender a TCP receiver or particularly a sender。

Can control how many packets it puts into a network to make sure that it doesn't overwhelm the network。

 controls the congestion。And so it's this end to end approach leaving the inside of the network simple。

 and it turns out you can just do it at the edge and it turns out you could do it very， very well。

So TCP congestion control chose to use a particular algorithm called added increased multiplicative decrease or AIMD。

And it turns out that this algorithm has a bunch of really interesting properties when you actually look at how it behaves in even very large complex networks with millions of flows competing。

 it has some very nice stable properties that allow it to control congestion well and also in a fair way。

Turns out that it's such an important idea by many it's considered one of the crown jewels of networking。

 it's one of the most important intellectual ideas to go found its way into the network， it's in TCP。

 it's been in TCP now for about 25 years and so it's a very significant part of controlling congestion in the internet。

So in this unit， you're going to be learning about what congestion control is。

The kinds of properties that we would like from a congestion control algorithm。What the specific。

Congestion control mechanisms are that are used in TCP， the AIMD that Phil just mentioneded。

 and you're going to be learning a lot of details about how that works。

 how it's implemented in practice， how it works in different scenarios。

 what happens when you have one flow or what happens when you have many flows。

 and you're going to be learning a lot about not only what TCP is today。

 but its going to give you a lot of insight into what TCP congestion control might become in the future。

