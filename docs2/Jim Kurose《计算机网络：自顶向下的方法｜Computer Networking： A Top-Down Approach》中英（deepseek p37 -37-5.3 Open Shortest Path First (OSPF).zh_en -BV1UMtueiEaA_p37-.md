# Jim Kurose《计算机网络：自顶向下的方法｜Computer Networking： A Top-Down Approach》中英（deepseek p37 -37-5.3 Open Shortest Path First (OSPF).zh_en -BV1UMtueiEaA_p37-

![](img/561829c81bf24426940f197242cd0e07_0.png)

In the last section， our study of routing was primarily theoretical。

 took a look at routing algorithms， both centralized and distributed for computing minimum cost paths from source to destination In this section in the next。

 we're going to look at putting these principles into practice。

 We're going to start by looking at two particular considerations scale and autonomy that are really important in putting these principles into practice for scale。

 how do we do routing when there are literally billions of endpoints to be routed to autonomy has to do with allowing network managers and operators to choose how routing is done both within their own network and how routing is done to distant networks as well。

 We're going to cover two routing protocols here， the open shortest path first OSPF routing algorithm routing protocol for controlling routing within a network。

 and then we're also going to cover in the following section the border gateway protocol BGP。

For routing among networks， so why don't we get started and we're going to start with looking at this issue of scale and also autonomy。



![](img/561829c81bf24426940f197242cd0e07_2.png)

Our study of routing algorithm so far has been pretty idealized。

 We've considered the network as sort of a sea of undistinguishable routers that were connected by links。

 We simply wanted to find a shortest path from a source router to a destination router。 Well。

 in practice， things are a little bit more complicated than that。

 And they're complicated primarily by the issue of scale。

 How is it that we can route to literally billions of end hosts and hundreds of thousands of destination networks。

 If you think about it， a router forwarding table couldn't possibly hold a billion forwarding entries for all of the destination hosts。

 And certainly， when we think about a routing algorithm exchanging distance vector or link state information literally with millions of other entities just as't scalable and use up all the bandwidth within the network just for control purposes。

😊。

![](img/561829c81bf24426940f197242cd0e07_4.png)

And then there's the issue of autonomy。 And this might be a little less obvious。 Remember。

 the Internet is a network of networks。 and each network has an owner operator To what extent can or should that network owner operator be told how to route traffic。

 What autonomy does a network have with respect to its routing。

 We'll see that the Internet approach is twofold first a network can choose to use whatever routing protocol it wants in its own network。

 And secondly， a network will be able to control how traffic from its customer networks is routed towards a destination and how it as a network routes traffic that it carries that's sent to it by other networks。

 Well， let's begin with the issue of scaling。

![](img/561829c81bf24426940f197242cd0e07_6.png)

The internet approach to scaling routing begins with the notion of aggregating routers into networks or into regions that are sometimes called autonomous systems or domains。

 And as we'll see， there's basically two types of routing。

 there's routing protocols for routing within a domain and there are routing protocols for routing among domains。

 and as we'll see， there are different protocols for each And let's start with the notion of routing within a network within an autonomous system。

 This is known as intra domain routing and in intrat domain routing。

 all routers within the domain within the autonomous system within the network are all executing the same routing protocols。

 but different networks， different autonomous systems can choose their own intrat domain routing protocol and as we'll see。

 the edge of every autonomous system is a specialized type of router known as a gateway that will connect one autonomous system to another。



![](img/561829c81bf24426940f197242cd0e07_8.png)

And then there's InterAS， otherwise known as Inter domainomain routing for routing among autonomous systems here a network's gateway is going to perform Inter domainomain routing as well as participate in intra domainoma routing within its own autonomous system。



![](img/561829c81bf24426940f197242cd0e07_10.png)

Here's a network with three autonomous systems， As1， As2 and AS3，3 interconnected networks。

 Each AS has its own intra domainin routing protocol。

 each as could use a different intra domain routing protocol。

 It doesn't really matter to the other AsSs Since that A is just routing within intra domain。

 And we see here， the intra autonomous system routing protocol that's responsible for routing between and among domains。

 The intra domain routing protocol will be used to populate routers forwarding table for destinations within the network。

 But what about traffic des to outside the network。

 It's here that the intraas intra domain routing protocol and a bit of the intraas routing protocol will be used to populate a router forwarding table for destinations outside the network。

 But let's start with the case of routing and forwarding to destinations with。



![](img/561829c81bf24426940f197242cd0e07_12.png)

In the AS， since that's a bit easier。

![](img/561829c81bf24426940f197242cd0e07_14.png)

There have only been three intrat domain routing protocols that have been adopted in practice。

 The first is the routing information protocol， simply known as Rip RIP was invented in the early 1980s and standardized in RFC  1723。

 It's a classic distance vector protocol where distance vector protocols or exchanged periodically every 30 seconds。

 It was used widely in the 80s， the 90s and into the Os。

 but Rip was eventually overtaken as an intrat domainoma routing protocol by the open shortest path first or OSPF protocol。

 OSPF is a classic Li state protocol that uses Dysrouss algorithm to compute shortest paths is a related protocol known as IIS Inter system to intermediate system routing that's very similar。

 almost identical to OSPF， but standardized by the international standards organization ISO rather than the IETF。

And in just a second， we're going to take a little bit closer look at OSPF because really right now it's the most widely deportiled intratro domain routing protocol in practice。



![](img/561829c81bf24426940f197242cd0e07_16.png)

The third commonly deployed in Tra A routing protocol is EIGRP。

 the enhanced interior gateway routing protocol。 It's also distance vector based。

 and actually it was formerly proprietary within Cisco for decades。

 couldn't actually figure out exactly what was in EIGRP。 however， in 2013 Cisco open sourced EIGRP。

 and it became an open protocol。 Now， let's take a look at the OSPF open shortest pass first routing protocol。

 O and OSPF stands for open， meaning that the specifications publicly available。

 OSPF is a classic link state protocol。 Each routers going to flood OSPF Li state advertisements across the entire autonomous system。

 That is， each OSPF routers going to flood information about each of its attached links that will propagate to all other routers in the autonomous system。

 and so as in a classic。

![](img/561829c81bf24426940f197242cd0e07_18.png)

State algorithm each router has full topology information OSPF then uses Dyster like algorithm to compute each forwarding table。

Multiple link cost metrics are possible。 The amount of bandwidth available。

 the delay associated with the link are two examples of link cost metrics。 And finally。

 one of the most recent innovations in OSPF， really a needed innovation is that all OSPF messages are authenticated。



![](img/561829c81bf24426940f197242cd0e07_20.png)

![](img/561829c81bf24426940f197242cd0e07_21.png)

OSPF can also operate in what's called a hierarchical mode。 OSPF hierarchies have two levels。

 There's a local area。 You can see here in the figure，3 areas， Are 1，2， and 3。

 as well as a backbone and L state advertisements as part of the classicling state algorithm are now only going to be flooded within an area or within a backbone。

 And so you can see how this hierarchical structure is going to scope the amount of information that flows among the routers in the entire hierarchical network。

Each node is going to have detailed information about the full topology within its area or within its backbone。

 So the question is， how do you know how to route to other nodes that are not part of your area or not in the backbone。

 This is the role of the area border routers。 an area border routers going to summarize distances to other destinations in its own area and advertise this to other nodes in the backbone。

 The local routers in an area are going to perform just like classic link state algorithms。

 They're going to flood link state information within the area。

 They're going to compute routing within the area and they're going to forward packets that need to go outside the area to the area border router。

 in the backbone， we see two types of routers。 We see a boundary router that's going to connect this hierarchical OSPF network to the larger outside world to connect to other autonomous systems and then within the backbone。

 There are backbone routers that are going to run OSPF They're going。Flood links state information。

 but will do so only within the back mode。

![](img/561829c81bf24426940f197242cd0e07_23.png)

Well that wraps up the first of our two sections on the practice of internet routing protocols。

 we saw how the issues of scale and autonomy are really important considerations in designing how Internet routing works we took a look at one intra domainomain routing protocol the open shortest path first OSPF protocol that's widely used in the Internet today coming up in the next section we're going to take a look at an Inter domainomain routing protocol。

 the border gateway protocol BGP there's only one Inter domainomain routing protocol and use in the Internet and for that reason BGP sometimes referred to as the glue that holds the Internet together because it's BGP that determines how routing is done among separate autonomous systems。



![](img/561829c81bf24426940f197242cd0e07_25.png)