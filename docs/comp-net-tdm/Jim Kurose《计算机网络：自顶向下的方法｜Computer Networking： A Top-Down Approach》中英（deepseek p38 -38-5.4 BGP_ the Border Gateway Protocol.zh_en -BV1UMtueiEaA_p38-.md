# Jim Kurose《计算机网络：自顶向下的方法｜Computer Networking： A Top-Down Approach》中英（deepseek p38 -38-5.4 BGP_ the Border Gateway Protocol.zh_en -BV1UMtueiEaA_p38-

In this section we're going to study BGP， the border gateway routing protocol BGP is the de facto Interdomain routing protocol that's used in the internet today for this reason sometimes referred to as the glue that binds together the internet。

 the network of networks together Now when we studied OSPF we saw that OSPF was a fairly straightforward implementation of Dystra's Li state routing algorithm BGP has its origins in the distance vector algorithm but in addition to studying how BGP is implemented and how it operates we're also going to spend a good deal of time looking at how BGP allows network operators to implement routing policy to control how packets that are routed to and from network's customers networks is actually control and how a network handles transit traffic we'll see that BGP is much is as much about policy as it is。

About performance and so I think you're going to find this pretty interesting。Well。

 let's begin with an overview of BGP basics。 And BGP is a really important protocol。

 It's really right up there with IP。 It's arguably one of the two most important internet protocols。

 Now， as we'll see， BGP has its origins in the distance vector protocols it distributed and its asynchronous。

 But as we've mentioned， BGPism is as much about policy as it is about computing least cost paths from sources to destinations。

 BGP allows a network to advertise its existence to the rest of the Internet。

 as well as the paths that it has to these destination networks。 It allows a BGP router to say， hey。

 here I am， and here's who I can reach and in particular。

 here's the paths that I have to these destinations that I can reach。 Well。

 let's unpack this statement a little bit。 What this means is that on the receiving side。

 BGP provides each autonomous system with the means to obtain destination network reachability information。

from its neighbors， router can then determine whether or not to actually use these paths based on policy。

 for example， a policy might be not to use a path that passes through a given ISP or through a given country。

BGP also provides each autonomous system with the means to propagate reachability information to routers within its own network。

 This communication with routers inside of an autonomous system is done through the I BGP protocol。

 And finally， theres a very subtle but also very powerful policy issue of what destination reachability information that an autonomous system wants to pass on to its neighbors。

 If I'm an autonomous system and say， I know I can reach destination X。

 do I really want to tell my neighboring networks that I can reach destination X。 If so。

 they might try to route packet through me to get to X and maybe I don't want that to happen。

 So you can see a policy aspect to which path an autonomous system advertises as well as which paths it chooses to use。

This figure shows the two flavors of BGP EBGP runs between two routers that are in different autonomous systems。

 IBGP runs between two routers that are within the same autonomous system， and as we see here。

 Gway routers run both EBGP and IBGP。So let's take a look at two BGP routers sometimes called BGP peers or BGP speakers that are interacting with each other。

 BGP peers exchange BGP messages over semi permanent TCP connections using port 179。

 they advertise paths to different destination network prefixes， for example， to s 24/ 16 network。

For this reason， because BGP advertise paths， BGP is sometimes known as a PA vector protocol。

In this example here， when network X attaches to AS3， AS3 now knows it can reach X。

 and so AS3 gateway3A here advertises the path AS3 comma X to AS2 gateway to C， and in this way。

 AS2 learns about the reachability of x through AS3。

 and it's important to note that when AS3 advertises the path to X。

 AS3 is essentially promising to AS2 that it is both able and willing to forward datagrams towards X。

Let's wrap up our discussion of BGP basics by listing the BGP messages that are used by the BGP protocol there's an open and a notification message that are used to open and close BGP session keep message for when not much is happening and then there's the all importantant BGP update message this is the message that's used to advertise a path or withdraw a previously advertised path you can read all about the BGP messages in RFC 4271。

Okay， so that's it for the basics of BGP next we're going to dive down deeper into some of the details of BGP。

 particular we're going to look at the notion of PAS。

 path advertisement and how path advertisements can be used to control routing policy。

Well let's begin our study of path advertisement by looking at the path advertisement itself when a BGPE router advertises a path it advertises two things。

 first of all it advertises the destination for that path。

 the ciarized address/24/16 address of the destination where that path is going to terminate。

 and the second thing that's advertises a set of attributes associated with that path。

 the most important attribute of that path is the AS path attribute。

 the AS path attribute enumerates the entire list of autonomous systems that would be path through in routing from the current network to that destination network。

We've said that BGP is a policy based routing protocol， and now we can see exactly what that means。

 First， a router receiving a route advertisement uses policy to decide whether or not to use a path that's just been advertised to it。

 For example， as we said earlier， a policy might be never to accept a path that passes through ISPW or passes through country Y。

A router also uses policy to decide whether or not to advertise a particular path to a neighboring autonomous system if I don't advertise a path to a neighbor。

 that neighbor can never send me traffic that uses that path and maybe that's exactly what I want。

Here's an example showing how a path advertisement propagates among and within autonomous systems。

Let's say that based on policy， router 3A decides that it will advertise a path to destinationation X to autonomous system 2 AS2。

A2 router 2C receives this path advertisement AS3 comma X via EGP from router 3A based on AS2 policy。

 router 2C then accepts the path AS3 comma X and propagates this path via IPBGP to all of the AS2 routers。

And then based on AS2 policy， AS2 router 2A can then advertise via EBGP， path AS2， AS3。

 comma X to AS1 router 1C， and in this manner autonomous system AS1 learns about a path 2 X via AS2 and AS3。

Now， it's possible for a B， GP router to learn about multiple different paths to the same destination as we see in this example here。

 And in this example， A S1 gateway router 1 C has learned about a lower path to X via AS S 2 and A S3。

 router 1 C also learns about another path， A S3 comma X。

 this upper path here directly from router 3 A， and in this example based on policy， router 1 C。

 say chooses the path， A S3 comma X and advertises this path within As S1 via I BGP。Now。

 let's take a look at how path advertisements can be used to implement routing policy to make a concrete。

 Let's assume that policy is the following。 and ISP only wants to forward datagrams that have either a source or a destination in one of its customer ISps。

 And this is actually a real worldorl policy。 Why would an ISP want to forward traffic that's just passing through。

 That's called transit traffic， transitit traffic generates no income。

 It's only the ISP's customer networks that are actually paying for service from this ISP。

 So the ISP's policy understandably is to only route traffic that has either a source or a destination in one of the customer networks of that ISP。

Here's an example。 Let's say that networks， A， B and C are provider networks and networks X。

 W and Y are customer networks。 Since W is a customer of A。

 A is very happy to advertise the path A W to B and C A saying， hey。

 if you want to route to W route through B A， really， if a didn't advertise this。

 then no traffic would flow to W through A。 Okay， fair enough。

 but now let's look at what happens at B。 Does B really want to tell C that there's a path。 B， A W。

 Well， maybe not， W isn't a customer of B。 And if B tells C that it B has a path to W。

 then C could route traffic to W V a B， and B has no desire or economic incentive to serve as a transit network for traffic flowing from B to A。

 And as a result， B probably wouldn't advertise the route B。AW to C， and consequently。

 C has no idea that a path actually exists to W via B。

Here's another policy based path advertisement Quandary。 Look at network X。

 It's a customer to both networks B and network C。 That's called being dual home As a customer。

 It's attached to both B And C， but it really has no desire to route traffic between B and C。

 even though it could。 So X doesn't tell B that it has a path to C and doesn't tell C that it has a path to B。

 And as a result， X would never carry transit traffic between B and C。Well。

 I hope you can really appreciate now how policy is such an important consideration in BGP and how an ISP can use path advertisement as a mechanism to implement routing policy。

 it was really an eye opener for me to see how much issues of policy rather than cost really dominated how interdomain routing is done in the internet。

Now， while interdomain routing and path advertisements determine the paths that packets take。

 we still have to address the issue of how the forwarding tables going to be populated in order to implement the forwarding policies that are consistent with packets taking a given path。

 let's take a look at that next。This example shows how path to destinations outside of an autonomous system are instantiated in a router's forwarding table using IBGP。

 So recall that routers 1A，1 B and 1 D learn about how to get to X via an IBGP message from node 1 C who says。

 hey， the path to X goes through me 1 c。Let's now look at router 1 D。

 router 1 D knows from its OSPF intra domainomain routing that to forward datagrams to 1 c。

 it should forward them via interface 1， and so 1 D also knows that to forward datagrams to destination X now should also forward these datagrams via interface 1。

 because that's the interface used to reach 1 C。And over here at 1 a。

 suppose that OSPF intradomain routing says that to get to router 1 C。

1 a should forward datagrams using local interface 2。

 And so 1 A knows that to forward datagrams towards x。

 It should therefore also forward these datagrams via interface 2。

 The end result is that traffic from 1 a destined to x will first be forwarded from 1 a to 1 D。

 and then forward it from 1 D to 1 c and then forward it from 1 c into autonomous system AS 3。Lastly。

 there's a form of VG P intra domainomain routing known as hot potato routing。

 Ho potato routing says that when roing to an external destination。

 forward this packet to the local gateway that's closest to me without worrying about the overall cost of getting to the destination。

 The goal is simply to get this packet out of my network as quickly as possible。In this example here。

 2D will forward a packet destined to X via 2A rather than via 2C。 Of course。

 this myopic decision isn't always the best global decision。 In this example here。

 there are more AsS hops involved in routing via 2A then routing via 2C。

 This is called hot potato routing because you're trying to get the packet out of the network with the least cost possible。

 you may remember the game of hot potato when you're a kid。

 you're past a ball and you want to get rid of it as fast as possible so not to be caught holding the ball when the game ends you just want to get rid of the ball。

アプてなアプ。ハプ这ハ。potato hot potato， potato potato， potato！あて了。h it's lovely。

 it really makes me think that actually playing hot potato might even be more fun than learning about BGP and hot potato routing。

Well that wraps up our discussion of BGP and I hope it has been fun to learn about BGP and BGP hot potato routing and let's wrap up our larger discussion of the practice of interdomain routing by reflecting on some of the differences between intra domainomain routing like OSPF and Interdomain routing like BGP What we've seen is that an interdomain routing。

 policy considerations really dominate an ISP wants to have the policy knobs and able to be able to control how it routes traffic to and from its customers networks and how it handles transit traffic。

Another critical consideration in internet routing is that of scalability。

 concernsns about minimizing forwarding table size and the amount of routing update traffic。😊。

We learned that the separation of intra domain and intra domain routing meant that intradoma routing information didn't propagate outside of an autonomous system。

 And so the rest of the Internet never even saw routing information from within any particular domain。

 It's a good thing， given the millions of networks that make up the Internet。In OSPF。

 we learned about the use of hierarchical routing to limit the scope of full topological information。

 even within a single autonomous system。 And we learned here。

 And also when we studied internet addressing in Chapter 4 about how B GP routes to ciderized destination networks and how a single ciderized network address can actually represent a large number of networks within an address block。

 And let's wrap up by coming back to performance， we saw that at the application and the transport layer and even an intra domain routing。

 that performance matters。 we've said that milliseconds count。 It's interesting to note， though。

 that for inner domain routing and B GP， we've seen that policy considerations clearly dominate over performance。

😊，And so that wraps up our discussion of the practice of internet routing。

 taking a look at both the OSPF and the BGP protocols in particular。

 I hope you found those interesting。 I know it's a little jarring actually after studying routing algorithms。

 looking at link state algorithms， the distance vector algorithm and seeing those actually implementing in intrat domain routing like W and OSPF to see that at the inter domain level。

 how policy rather than path costs so dominates the discussion。 Well， coming up next。

 we're going to take a step back and we're going to look at general approaches towards implementing a control plane。

 in particular， we've seen that both with BGP and with OSPF。

 they take a per router approach towards implementing the control plane。

 we're going to take a look at an alternative way to implementing a control plane where the computations themselves of the paths is actually physically removed from the routers themselves。

 maybe implemented。In a data center that's placed far away from the routers themselves。

 this is an approach that's come to be known as software defined networking so that's coming up next。

 so stay tuned。

![](img/ba9eea044185edb3562b5e96e44be777_1.png)

![](img/ba9eea044185edb3562b5e96e44be777_2.png)