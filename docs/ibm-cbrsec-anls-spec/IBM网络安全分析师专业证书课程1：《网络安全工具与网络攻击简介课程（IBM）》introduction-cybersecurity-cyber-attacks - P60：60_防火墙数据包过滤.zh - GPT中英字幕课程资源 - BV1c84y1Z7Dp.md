# IBM网络安全分析师专业证书课程1：《网络安全工具与网络攻击简介课程（IBM）》introduction-cybersecurity-cyber-attacks - P60：60_防火墙数据包过滤.zh - GPT中英字幕课程资源 - BV1c84y1Z7Dp

![](img/3ceb52ef256bb4c62dcae7cbc1c5ec29_0.png)

Yes。In this video， you will learn too。Describe what packet filtering is and how packet filtering firewalls work。



![](img/3ceb52ef256bb4c62dcae7cbc1c5ec29_2.png)

Packet filtering is one of the fundamental technologies for application and。



![](img/3ceb52ef256bb4c62dcae7cbc1c5ec29_4.png)

啊。Enterprise level， firewalls， and fundamentally on a packet by packet decision is made whether to forward or drop the。

It's based on a couple of parameters， so those parameters that we're going to look at。

listed here on slide six， one of the fundamental ones is the source IP address and the destination IP address。

 fundamentally where is it coming from？And where is it going to。And we can make decisions。

Based on those two parameters along， also the transport protocol being used。

And the destination port numbers can also be a filtering side of that。 So TCP and UDP。

Are the two primary transport protocols on the internet is basically how IP packets get moved from IP address to IP address。

 one is a connection list。So a broadcast signal that's UDP and TCP is more point to point。

 We can also filter on message types and we can also filter on synchronization and acknowledgement。

Bits being flat。 Let's take a look at a couple of examples of。Packet filtering。

 So in example one right that we've been a block incoming and outgoing datagrams。

 right those are those of the IP blocks， IP protocols。

 field 17 and either a source or destination port of 23。

 So effectively we the missing we are blocking all UDP flows and all telenet connection flows with at the enterprise edge these are。

Good security protocols。 And this is generally a great application of firewalls to enforce a security policy。

The second one， when we block inbound TCP segments with the acknowledge bit。

 not acknowledge bit set to zero， this is preventing external communicators from making TCP connections with internal clients。

 but allows internal to communicate to the outside。

 which is a security policy says that we trust our inside guys more than we trust our outside guys。



![](img/3ceb52ef256bb4c62dcae7cbc1c5ec29_6.png)