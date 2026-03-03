# 斯坦福大学《计算机网络｜Introduction to Computer Networking CS 144 2018》中英字幕deepseek - P84：-084-Routing 64.zh_en - GPT中英字幕课程资源 - BV1bVqNYFEGg

So welcome to unit six unit six is about routing， so the basic question of how do we get a packet from A to B across a large network such as danger？

We've already been implicitly assuming that there was a way for packets to be delivered from one side of the internet to the other and all of the exercises。

 assignments， videos that we've been working on so far now we're actually going to look at the methods and the approaches that we can use to forward and route those packets through the internet。

So there's a very obvious place to start and that is what if each packet contained a list of all the routers that it was going to pass through and then just found its own way through the network just with the state entirely contained within the packet that would work that's one way to do it but it's not how the internet works that method what we call source routing was considered to be both inefficient and potentially a security loophole and we'll see that in the videos coming up instead as you know。

 the internet uses forwarding tables， each router contains a forwarding table that tells it for each destination prefix。

 which path or which next hop to send a packet to。And so the next question to ask is。

 how do those4ing tables get populated？For that， we use an algorithm and that algorithm runs as a distributed algorithm so that the routers can come to a conclusion as to the entries that they will put into those forwarding tables。

The basic approach that gets used is that the routers will build a spanning tree。

 spanning tree is a tree， therefore it has no loops。

 and it's spanning in that it provides a way for every source to reach a given destination so the root of the tree is at the destination and the leaves are all of the other sources so that they can send on the spanning tree to reach that destination。

So the routers now have to build that spanning tree and there are two wellknown algorithms that we'll be describing in upcoming videos and how those 14 table entries get built in order to create that' the spanning tree。

 the first one is called the Belmon Ford algorithm also known as a distance factor algorithm and you'll see why it's called the distance factor in an upcoming video。

The alternative method which is now more widely used is called Dyextra's algorithm or Dytra's shortest path first algorithm。

 and this is known as a Li state algorithm and again you'll see that described in detail in an upcoming video。

You're also going to see how these algorithms are actually used in the internet today。 Well。

 first off， the internet has a collection of many different parties。

 each with their own networks which are somehow interconnected。

So we're going to talk a little bit about the notion of an autonomous system。

 an administrative domain of routing within the internet， for example。

 Stanford is an autonomous system， it's actually multiple ones like the Stanford Line Acccelerator is its own autonomous system and then there's domain Stanford campus。

 many large ISP， in fact might have multiple ASs， not a huge number。

 multiple autonomous systems or ASs。嗯。And there are different kinds of ASs， for example。

 Stanford doesn't route transit traffic across the internet， it acts as an EAS or a stUub ASS。

So within an autonomous system， there are two basic routing algorithms that are used。

Rip and OSPF R is a distance vector protocol whereas OSPF is a Li state protocol generally today almost everyone uses OSPF in order to define their routing tables within an autonomous system it is。

 for example， what Stanford uses。But then the routing between autonomous systems uses a different protocol EGP or the border gateway protocol。

It turns out that often autonomous systems don't necessarily want to expose what their internal network is like。

 and so just doing a shortest path can be tricky， so instead BGP adds some additional mechanisms like actually knowing the path that packets might take in order that to allow autonomous systems sort of hide their internals will giving enough information that routers can pick free path。

And so suddenly we've so far been talking mostly about applications and transport and all these things happening end to end。

 this is the unit we're going to look inside the middle and see what are actually the pieces that work and the mechanisms in the algorithms to make the internet work as it does today。

 and so when you come to the end of this unit you should have a very good idea of the different strategies that we can take in order to route packets from A to B。

