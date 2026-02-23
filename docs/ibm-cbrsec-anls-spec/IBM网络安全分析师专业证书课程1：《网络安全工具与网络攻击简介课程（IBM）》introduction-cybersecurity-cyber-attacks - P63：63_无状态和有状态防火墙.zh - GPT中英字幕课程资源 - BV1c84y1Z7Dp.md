# IBM网络安全分析师专业证书课程1：《网络安全工具与网络攻击简介课程（IBM）》introduction-cybersecurity-cyber-attacks - P63：63_无状态和有状态防火墙.zh - GPT中英字幕课程资源 - BV1c84y1Z7Dp

![](img/d23d8bd840afb636c9d697d09996127c_0.png)

Yes。In this video， you will learn to describe the difference between a stateful and a stateless firewall。

Describe the trade offs when moving from a stateless to a stateful firewall Okay so next up we're going to talk about a little bit about firewalls。



![](img/d23d8bd840afb636c9d697d09996127c_2.png)

![](img/d23d8bd840afb636c9d697d09996127c_3.png)

As far was as you already probably know， can filter traffic between networks。

Depending on the type of firewalls， they handle packets differently。

 firewalls can be multiho as well， meaning they have multiple mixs or network interface connectors connected to different networks so that's basically to put in other words。

 we have one ni connected to the Internet， and then we have one ni connected to our local network。

 They are also different type of firewalls， but we'll go over a few of them stateless and stateful。

 which are the most common ones。And we will see a lot of one and the more secure one。

So a statement followss as the word says， they have no concept of the state。

 they can also be called packet filters， they make their decisions based on layer 3 and layer4 information。

 meaning I in port。They lacked the sense of estate state。And it's， of course， they're less secure。

 as you can see from the image on your left on the top。

 you see an ICMP E request and the corresponding ICMP Ep being accepted by the firewall。

 but on the bottom， an attacker is just sending E replies that is not preceded by an echo request and the packet filter or the stainless firewall actually allows that packet through。

On a state firewalls that we will see next， that E reply， if it's not followed by an echo request。

 it will be denied the firewall。Stickple firewalls。

 they have state tables that basically allowed the firewall to compare current package with previous packets。

This actually makes the firewall a little bit slower， but far more secure than a stateless filewall。

 Sometimes they are also called application firewalls。

 and they can make decisions based on layer 7 information。

 meaning they could also filter information based on the type of website that somebody is visiting。

As you can see from the image on your left， ICMP E request and then the corresponding EC replyp being accepted but when a effectiveer tries to send an ICMP E reply。

 the stateful file will go through the state table to take that that EC replyp has no corresponding previous EC request and block that traffic or。

There's one more type of firewall that we will discuss， and they're called proxy firewalls。

 They basically act as an intermedia the area server。 As you can see from the image below。

 it is between two notes， of course， computer and the server。

But it actually terminates the connection once the computer initiates the connection with the bank。

As you can see also， it has two three way handshakes between two devices， meaning。

Computer 1 will initiate a connection with the server。

 but the firewall will actually make that connection back to computer1。

 And then the flexyifier will initiate another connection with the tank itself。

 So it will sit between two devices like a man in the middle。And it will be will。

 this will allow the prexy firewall to filter a bunch of traffic and actually analyze it even better。



![](img/d23d8bd840afb636c9d697d09996127c_5.png)