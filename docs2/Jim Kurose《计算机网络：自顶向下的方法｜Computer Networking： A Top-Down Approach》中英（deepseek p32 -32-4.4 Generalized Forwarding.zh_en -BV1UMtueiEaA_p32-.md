# Jim Kurose《计算机网络：自顶向下的方法｜Computer Networking： A Top-Down Approach》中英（deepseek p32 -32-4.4 Generalized Forwarding.zh_en -BV1UMtueiEaA_p32-

。You'll hopefully remember from our earlier discussion of what's inside a router that a router operates basically by looking at the destination address in an arriving IP datagram。

 looking up that destination address in forwarding table and determining the appropriate output port Now that's the way routers have worked literally for decades but in the past deck at a new form of forwarding known as generalized forwarding has taken whole and in generalized forwarding as we'll see many more fields other than the destination address can be consulted and also there's a much wider range of actions that can be taken so in this section we're going to look at generalized forwarding we're going to look at the match plus action abstraction and we're going look at an emerging standard for generalized forwarding known as openflow so let's get started。

Well， let's begin by reviewing what we learned earlier。 when we looked at what's inside a router。

 Here's the scenario。 a datagram's arriving to a router。

 and the router needs to figure out what to do with the datagram。 Remember。

 the router has a forwarding table。 The router looks at the destination I P address in the header of the arriving datagram and matches that address to a forwarding table entry and that entry indicates the appropriate router output port to which the packet should be forwarded。

 The router then takes the action of forwarding the packet to the port。

 That's destination based forwarding。 That's what we learned about earlier。Well。

 generalize forwarding well generalizes its behavior in two ways。 First。

 the match can be performed on many different header fields in the arriving packet in the link layer。

 frame header， the network layer， Datagram header or the transport layer segment header。

 And secondly， the action space is going to be much broader than just forwarding， as we'll see。

In this case of generalized forwarding， the forwarding tables sometimes referred to as a flow table。

 And as we just mentioned， the action that a router can take when a match is found for a packet could be to forward the packet to a given output port。

 as we saw with destination base forwarding to block or drop the packet。 That's what a firewall does。

 to modify the packet， maybe to rewrite the header。 Hey。

 that's what Nat does or maybe to send the packet to the SDN controller。

 There can also be priorities associated with each flow rule and also counters for the numbers of packets matching the flow values。

We see this routers flow table here with a match column and an associated action column。

 let's take a look at an example。In the example here。

 the first Match+ action rule says that any packet with a destination IP address of 3。

4/16 should be forwarded to output1 note that the stars here represent wildcard or don't care values。

The second rule says that any packet coming from 1。2/lash 16 should be dropped。

 and the final rule says that any packets from source IP address 10。1。2。

3 should be encapsulated and forwarded to the SDN controller。Now， if multiple flows。

 that's the say multiple rows are matched， some kind of preference priority mechanism is going to be needed to select the specific action to be taken。

Well， so far， our discussions has been generic。 So let's now take a look at a specific generalized forwarding approach that's been standardized。

 It's known as open flow。 and we'll take a look at the original open flow 1 do 0 specification。

In Open Flow 1。0， any of 12 different header fields can be used in the match。As you might expect。

 one can specify a match on a number of different network layer IP header fields， the IP source。

 IP destination， upper layer protocol and type of service fields， all of which we've studied earlier。

 in addition to these network layer header fields， one can also match on transport layer port source and destination numbers。

 so for instance， one could block or specifically allow services at well-known port numbers。

And matching can also be done at the link layer as well。 We've not yet studied the link layer。

 but we will soon。 So that's the matching。 Here are some of the actions that can be taken on a match。

 Well， the packet can be forwarded to a particular output port or duplicated and sent to a set of ports。

 The packet could be dropped。 The fields in any of the headers we see below could be modified and rewritten。

Or the packet could be encapsulated and forwarded to the SDN controller。

 which would then presumably take some kind of control action。Well。

 we've seen that Open flowlows Mat plus action rules allow us to do a lot more than just destination based forwarding。

 so let's take a look at a few specific examples。In this first example here， well。

 this just shows that one can implement destination based forwarding using openflow。

 So in some sense， generalize forwarding can do everything that destination based forwarding can do。

 That's good to know In this example， Datagrams destined to IP address 51 60。

 8 should be forwarded to router output port 6。The second example here shows how openFll rules can be used to implement a firewall。

 the effect of this rule， which says blocklock all datagrams destined to DCCP port 22 is effectively the shut off SSH service。

 which uses port 22 downstream from this router。Anyone trying to SSH to a host reachable through this router would be blocked。

 That's to say their datagrams trying to open an SSH connection at some remote host would be dropped here at this router。

The third example is also a firewall rule， it says to block all datagrams sent by host 128。119。1。1。

 this is a host being blacklisted。And this last example says that all layer2 frames destined to this Mac address here should be forwarded to output port 3。

This is just a traditional link layer forwarding of layer to frames。

And so we've seen through these examples that the match plus action abstraction can be used to accomplish the functionality of a number of different kinds of devices。

MatchPlus Action accomplishes network layer destination based forwarding MatchPlus A accomplishes link layer switching。

 and we've just seen a couple of firewalling examples and with the ability to rewrite headers。

 MatchPlus action can also be used to accomplish na like types of services as well。

Well that's all really cool， but these actions that we've talked about so far are local actions。

 let's step back now and take a look at the bigger the network wide picture and here。

 if you think about it， the ability to specify a set of flow tables is going to allow us the ability to specify network wide behaviors as well。

 including routing， let's take a look。Well， when we get to the network layer control plane and software defined networking。

 we'll see how this is done， but this should hopefully make some sense to you already if we can generate。

 if we can craft the individual forwarding tables in all routers in the network。

 then we can implement any network wide routing we actually want。

We can compute the forwarding tables in an SDN controller。

 We can generate the tables via a program in the SDN controller and install them in the routers。

 In this case， there's no need for a routing protocol since the forwarding tables are computed in the SN controller。

 That's a really powerful idea but maybe one that hasn't quite been mainstreamed yet。 Well。

 here's a simple example of specifying and end routing behavior。

 Suppose we want traffic from host 5 and host 6 here。

 destined to host 3 and host 4 here to be routed via S 1 here。

 Note that this means specifically that traffic won't be forwarded over this direct link here between S 3 and S2。

 Let's take a look at the forwarding tables。TheForing table here in S3 indicates that anything from IP addresses 10。

3/16 and destined to IP addresses 10。2/16 should be forwarded out of Local port 3。

The forwarding table here in S1 indicates that anything from IP address range 10。

3/16 and destined to 10。2/lash16 should be forwarded out of local port 4。

And the forwarding table here in S2 says that traffic coming in on port 2 and destined to 10。2。0。

3 needs to be forwarded via local port 3 and that traffic coming in on port 2 and destined to 10。2。0。

4 needs to be forwarded via local port4。Well， let's summarize what we've learned here about generalized forwarding and match plus action。

 We've seen that it's possible to match over many fields in the link network and transport layer headers。

 We've seen that the local actions include forwarding packets， dropping packets。

 modifying header fields and packets or sending match packets to a controller。

 These local actions allow for layer 3 routing layer 2 switching。

 firewalling and net like functions all to be accomplished under this single match plus action abstraction。

And perhaps most importantly， and sort of giving us a sneak preview ahead into the control plane。

 we've seen that an SDN controller can effectively program network wide behaviors like routing by carefully crafting the flow table entries。

So we've seen that matchchPlus action allows a wide range of functionality to be implemented and why is that Well。

 if you step back and really think about it， MatchPlus action is a limited form of programmability that is being able to program around or to take per packet processing steps and this kind of thinking actually goes back to a DARPA program about 20 years ago known as active networking and networking researchers today are very actively looking into the question of programming languages for specifying and executing this kind of per packet processing behavior perhaps the most visible of these activities is the P4 programming language and if you're interested in that you can check out P4。

 org So coming up next we're going to take a look at middle boxes and thatll give us an opportunity to look at some big picture questions also about internet architecture。

 so stay tuned。

![](img/a4c5a9b8f226181cfa85d707b7833590_1.png)

![](img/a4c5a9b8f226181cfa85d707b7833590_2.png)