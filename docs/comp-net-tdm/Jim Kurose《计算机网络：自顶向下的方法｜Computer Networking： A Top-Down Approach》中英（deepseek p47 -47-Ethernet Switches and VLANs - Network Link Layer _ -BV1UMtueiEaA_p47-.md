# Jim Kurose《计算机网络：自顶向下的方法｜Computer Networking： A Top-Down Approach》中英（deepseek p47 -47-Ethernet Switches and VLANs - Network Link Layer _ -BV1UMtueiEaA_p47-

In this video we look at layer2 switches and VLs， let's get started。



![](img/d2fbffd82fdf7151d878b2487d2405ff_1.png)

Now let's look at switches and specifically we'll be looking at Ethernet switches。

 which operate based on the Ethernet addressing and protocol that we've been looking at in recent videos。



![](img/d2fbffd82fdf7151d878b2487d2405ff_3.png)

When we talk about a switch， we're referring to a layer2 device that actively performs storing and forwarding of ethernet frames。

Certainly in the core of the network， you may find other layer2 protocols and switches associated with those protocols。

But since Ethernet is the device that you're most likely to encounter。

 we'll stick to discussing Ethernet switches。So the basic operation is that the switch looks at the destination address of the frame and determines what reports the frame should be forwarded to。

In accessing the links it will be using the CSMACD algorithm that's part of Ethernet The operation of the switch itself is transparent。

 meaning that the hosts operate as if there's a direct connection between them。

 whether or not there's a switch in the middle。At least for the basic functionality。

 switches do not require configuration and can operate in a plug and play manner due to their self learning behavior。



![](img/d2fbffd82fdf7151d878b2487d2405ff_5.png)

Here we have an ethernet land with a switch in the middle， the switch has six ports。

 one dedicated to each of the hosts。So unlike the Ether architectures that we talked about before。

 where it was a shared medium that all the hosts were contending for。

 each of these links is a separate collision domain。

And because there's only two interfaces on each link， they can run a full duplex。

So each of the switches ports， operates using the Ethernet protocol independently of all the other ports。

The switches also perform buffering， so just as we saw with the routing switching plane。

 if there's contention for an outgoing port， packets can be buffered temporarily and then transmitted once the port is available。

And as before， we can also have congestion to the point that the buffer will overflow and drop packets。

When you put all of this together， it means that we can have simultaneous flows going on through the switch。

So in this case we have A transmitting to a prime simultaneously with B transmitting to B prime。

 and there's no contention between these flows， they're able to happen simultaneously and each can utilize their full link bandwidth。

Of course， if we have two different hosts transmitting to one host， in this case。

 A to a prime and C to A prime， they're going to have to share the bandwidth on the link between the switch and a prime。

 so the switch will buffer packets temporarily and interleave them。

 but if the total rate exceeds the bandwidth of the a prime link。

 then the buffer will start to drop packets。

![](img/d2fbffd82fdf7151d878b2487d2405ff_7.png)

Now we already said that the switch doesn't require any configuration to perform its basic functions。

So the question is， how does it note a forward frames to a prime out the correct interface？

We also already said that the switch uses the destination Mac addresses in the frames。

So somehow it has to learn that frames destined to a prime's Mac address need to be forwarded out port4。

 and indeed this is what is stored in switch is forwarding table， the Mac address。

 associatedso port and a timeout。If you remember back to layer3 routers。

 we had to configure the routing table either manually or using a dynamic routing protocol。

 so how does a layer 2 switch essentially perform the same forwarding function without this configuration step？



![](img/d2fbffd82fdf7151d878b2487d2405ff_9.png)

In the case of a switch， it does not have a routtting protocol and does not need to communicate with other switches。

 instead it is able to learn which hosts can be reached through which interface and the processes as follows。

We have a sending a frame to a prime， and at this point we'll say the switch has just started up and its forwarding table is empty；

 however any time the switch receives a frame， it can read the source address and it's just learned what interface it can use to reach that source address。

So from this incoming frame， it's just learned that A is on interface1。

 but while that information is great for next time it needs to send a frame to A。

 it doesn't help the switch get the frame to a prime。

So let's look at what else happens when a frame arrives at a switch。



![](img/d2fbffd82fdf7151d878b2487d2405ff_11.png)

As we just saw， it records the source Mac address and the port that it came in on to populate its forwarding table。

The Mac address is used as the key or index to this table Now as we've mentioned before。

 there's no structural relationship between the Mac addresses and their position in the network。

 so searching this switch table requires exact matching。

If it finds a switch table entry for the destination Mac address in the frame。

 it then has to check and see if it received this frame on the same interface。

 meaning it won't send the frame back out the same port that it just came in on so as long as the port in the table is not the same one that the frame came in on。

 it will then forward the ethernet frame based on the switch table。

 but what about the case where the destination Mac address is not yet in the switch table In that case the switch will send it out all interfaces and this is where you can see that the behavior drastically diverges from the process of layer3 forwarding。

In layer 3， the default behavior is to drop packets that have no matching forwarding record。

 and the reason for this is scalability。Swches are used in local subnets with relatively small numbers of hosts on each subnet。

So they can afford to flood a packet to the whole network every now and then to facilitate the process of learning Mac addresses。

Routers， on the other hand， could not default to this behavior because if they did。

 they would end up forwarding packets to unknown destinations to the entire internet。



![](img/d2fbffd82fdf7151d878b2487d2405ff_13.png)

So let's walk through the rest of our example， we have a sending a frame to a prime and no entries in the switches forwarding table so far。

As the frame arrives at the switch， it learns from the source field of the frame and populates A Mac address and port number in the forwarding table。

Since a prime is not in the forwarding table， it has to fall back to its default behavior and flood the frame out all of the other interfaces。

Since the frame went out all the ports， a prime received it and can respond back。

Switz sends a frame to A via the switch and the switch already knows what interface A lives on so it can selectively send it out that port。

 and it also just learned what interface a prime is on so it can populate its switch table accordingly。

Now any future frames from A to A prime will only need to be sent out the port to A prime and will no longer need to be flooded。

So that's the basics of how a switch is able to populate its forwarding table without the destinations being configured。

The same behavior works even when multiple switches are connected together。

 so now we have one switch with three hosts connected to multiple other switches。

 and this is a common enterprise situation where you might have one switch connecting all the offices on the hallway and all of the hallway switches connected back to a building switch so if I need to get frames from A to G。

 it works exactly the same way。A will send out the frame to S1 and if it doesn't know what interface G's Mac address is on。

 it will flood that out to all the hosts， now the flooded frame will get to S4 which will perform the same behavior。

 so if none of the hosts have G's Mac address in their table。

 A's frame will reach every single host on the entire network。

So we certainly don't want the flooding process to happen too often because it does consume resources on every link in the network。

However， once G gets A' is frame and replies back， every switch along the path will learn what interface to use to get to G and the flooding for G's Mac address will stop。



![](img/d2fbffd82fdf7151d878b2487d2405ff_15.png)

Now let's tie this into the bigger picture。We have some number of switches connected together and these can use self learning to reach every other host on that layer2 network。

 and since all of these switches are hanging off one port from the rider。

 they must all be part of the same IP subnet。So the self learning process stops when it reaches the router。

Unlike a switch， the router will only accept Ethernet frames with the router's Mac address in the destination field。

The router will not forward ethernet frames with other destination addresses。

 and so the scope of this flooding self learning discovery process is confined to a single IP subnet。



![](img/d2fbffd82fdf7151d878b2487d2405ff_17.png)

As a reminder， let's look at the network stack on each of these devices。

 we have our end hosts running the entire network stack。

And then we have routers which are layer three devices， so as a package versus a router。

 the first layer 2 header is stripped off and the router just forwards to IP Datagram。

 and then it creates a whole new layer 2 frame on the output port。However。

 when that frame reaches a switch， the switch does not remove the layerer 2 header。

 it just makes its forwarding decision based on the existing layerer 2 destination address。

So both of these devices perform forwarding and we even discuss a switching fabric that's inside of a router。

 so the real difference is in the criteria for the forwarding decision。

Routers use routing algorithms to compute forwarding tables based on IP addresses。

But switches learn layerer 2 Mac addresses and populate their switch table based on those。



![](img/d2fbffd82fdf7151d878b2487d2405ff_19.png)

Now we'll look at VLNs， which is an enhanced functionality that modifies the way switches work in order to increase flexibility。



![](img/d2fbffd82fdf7151d878b2487d2405ff_21.png)

We've mentioned the flooding aspect of the switchitchM address learning process and this is clearly a scalability concern。

 anytime you take one packet and flood it to the whole network that's an exponential consumption of resources。

 and we've also seen some other protocols that use broadcast traffic。

So any packet using the destination broadcast address also gets flooded to the entire Sw Ethernet subnet。

One answer to this is to break up the subnet into multiple smaller subnets。

 and this improves efficiency by reducing the number of hosts that will hear every single flooded frame。

However， this can decrease flexibility if physical wiring has to be changed every time users move around and need to be connected back to a particular switch because it's separated by a router So in this example we have a CS user that's going to have an office physically in the EE department but wants to be on the CS switch。

So in that sort of environment it's easier to maintain a flat switched land like we see in this picture and not have to worry about where a user is physically in that network topology。

 so we have these two competing goals。We want to break up our broadcast domain for efficiency。

 but we want one large flat network for convenience。



![](img/d2fbffd82fdf7151d878b2487d2405ff_23.png)

BLs are the solution to this。We can take one physical switch and divide it up into multiple logical switches。

For example， if we have a switch for a hallway， but the users in that hallway fall into two different logical groups。

 we don't really want to have to add a separate physical switch and run the associated cabling from a router to that switch and from that switch to certain offices。

Instead， we make a software configuration change on the existing switch and are able to partition the user that way。

And so that switch is going to operate just like it was two physical switches or more。

 we can have large numbers of vNs configured if need be。

We also have some flexibility in how this is done， we can take physical ports and assign them to Vians。



![](img/d2fbffd82fdf7151d878b2487d2405ff_25.png)

Or we could assign certain Mac addresses to certain ValLN。

 so no matter which port that particular computer plugs into。

 it will always be on the ValLN that it's configured to be on。Now， as we mentioned。

 the point of separating this into two logical switches is to increase efficiency by reducing the number of hosts that hear broadcast or flooded messages。

And that means that these two vans need to be on separate subnets separated by a router。

So each of those Valans will need an uplink back to either other switches in their VLan or to a router interface。



![](img/d2fbffd82fdf7151d878b2487d2405ff_27.png)

Typically we're going to have VLins spanning multiple switches。

 and so in the simplest case to connect these switches we would need a link connecting the red Veillain and a separate link connecting the blue Veillain。



![](img/d2fbffd82fdf7151d878b2487d2405ff_29.png)

But that would cause its own scalability issue with the need to run multiple cables in parallel between these devices and extra consumption of switch ports。

 soveals include the concept of trunk ports， frames from multipleveals can be sent over the trunk port and they have an additional header field that tells the receiver whichvealan they belong to。

This Vlan header was not part of the original Ethernet specification， so it's added in 802。1Q。



![](img/d2fbffd82fdf7151d878b2487d2405ff_31.png)

An 802。1 Q frame takes our original ethernet frame and adds a couple fields right in front of the type。

These include the tag protocol identifier， the VLN ID itself。

 which you see has 12 bits so we can define many different VLNs if need B。

And a three bit priority field。

![](img/d2fbffd82fdf7151d878b2487d2405ff_33.png)

That wraps up our discussion of switches and Fance。Which we might call virtualized switches。

Our next topic is looking at MPLS。Multiprotocol label switching。

 which is a mechanism for virtualizing links。See you then。



![](img/d2fbffd82fdf7151d878b2487d2405ff_35.png)

We hope you enjoyed this video， if you found it to be useful。

 please click the like button to be notified when more videos are posted for this class。

 please subscribe to our channel and click the bell。

