# 史蒂文斯理工学院【中英⚡计算机系统管理｜CS615 2021 System Administration】 p26 p25 Week 05, Segment 2 - Networking I, IPv4 Basics & CIDR subnetting -BV11QQcYmEzD_p26-

Hello and welcome back to CS615 System Administration。This is week 5 segment 2。

 and after we looked at the details of the IP packet in the last video。

 I think it's time to quickly rehash some of the basics of IPV4。

So in this video we'll take a look at what exactly an IPV4 address looks like and how we sort out where on the network it is placed。

 we'll discuss the concept of class for networking from the early days of the internet。

 as well as the ubiquitous subting approach known as classless Interdomain routing or cider。

Remember in our last video， we looked at this illustration of the network packet with respect to the IP protocol。

 and we noted that it contains two IPV4 addresses， the source address。

 as well as the destination address。The destination address in our example was 1，5，5，2，4，6，56，11。

 The address of the Steven Seas Web server， which in our I P header， of course。

 was represented as binary digits。Which gets us to a very first and rather basic observation。

IBV4 addresses are 32 bit numbers。Meaning we have exactly 2 to the 32 possibilities for the entirety of the IPV4 IP space。

 Sometimes that we'll get back to our next video and we talk about IP exhaustion and IPV6。

So our IPV 4 address is a 32 bit binary number， but a 32 bit binary number is somewhat undy and hard to remember。

Which is why we commonly divide these 32 bits into four octs。

Each of theseocts is then represented with a decimal value and separated by a dot leading to the common dollar decimal representation of the I address。

 or 155，246，5611 in our example here。Although， of course， we can represent theocts and hex as well。

 if we like， we've seen this being done in the TC P Dm Hex output with a destination that was did indeed show up as exactly 9 B。

 F 6，38，0 B。But how does this 32 bit number， even if divided into fouroccts help us understand where on the network the address might be or what other systems it might be able to talk to？

To understand that。We note that each IP address is divided into a network and a host component。

Here we observe that the first 16 bits represent the network portion of the address and the last 16 bits。

 the host portion。But what does this mean the network portion。Well。

 hosting the same network can communicate with one another without the help of a router。

We call this being within the same broadcast domain。

 and it's an example of the difference between layer 2， the network layer and layer 3。

 the transport layer。A packet addressed to a host in the same layer2 network can be delivered by a network switch。

If the host is on a different network， then you need to layer three capable device such as a router。

How do we know what the network portion of an IP is？In the early days of the internet。

 all you had to do was look at the first three bits of the address。

 which could tell you exactly which class of a network the address was on。

So we had a total of three classes of networks known as a Class A， a class B， and a Class D network。

Except of course， there were really five different classes you could identify by inspection of the first four bits。



![](img/2e3273e948dfe780c569e287db5d7919_1.png)

Specifically， if the 302bit IP address started with a 0。

 then you knew you had a class a network where the first 8 B comprised the network portion of the address。

 meaning you had 24 bits remaining for the host portion。

 allowing you to address 2 to the 24 or over 16 million hosts within the same broadcast domainming。

If the first two bits were 1 and0， then you had a class B network with 16 bits of network portion and 16 bits used for the host portion。

If the first three bits were 1，1 and0， then you had a Class C network with 24 Bs of network。

 8 B host portion。But then we also have the class D and E networks where class D is reserved for multicast addresses and class E was early and reserveservd just in case。

Remember， IPV4 was intended to be an experiment， and so we reserved a chunk of addresses for future use。

 the ClassI network shown here。But okay， so if you had a class BIP address that meant that you had 16 B network portion and 16 B host portion。

 meaning you were on the same broadcast main as about 64，000 other hosts。That's one big network。

Chances are you didn't need such a large network and would have preferred to have a smaller network。



![](img/2e3273e948dfe780c569e287db5d7919_3.png)

So instead of just looking at the IP address and dividing the network and host portion based on the first few bits。

 we then introduced the concept of a net mask。 That is we added a second 32 bit number that was used to mask certain bits in the original address。

All the bits that were once would represent the network portion and all the bits that were zero would represent the host portion。

Now， the advantage of this was that even if you had such a class B network IP address as the one shown here。

You can then divide that network further into smaller networks and subnets by picking a different net mask。

Here we show a 24 bit net mask leaving 8 bits the host portion。

 effectively taking the Class B network and creating a class C subnet within this network。

The 24 bits that are once here are then denoted in the network in so called slash notation as slash 24。

Although we can represent this net mask in decimal notation as well， yielding 255，255。

2550 in this case。You've probably seen this net mask before。

 it's a fairly common one since it creates a reasonably sized network， but at the same time。

 making it easy for humans to quickly identify where this network begins and ends。

 namely exactly at the quad doted boundary。But the net mask doesn't have to align with the decimal dot boundaries。

 After all， it's really just a sequence of bits。 So if you wanted to create a smaller subnet。

We could， for example， use a s 26 network， 1255，255，255，192 and decimal。

Or if we had a need for a larger network， we might use a 22 B network。Fortunately for us。

 we don't need to perform this logic in our head。 After all。

 computers are much better than humans when it comes to manipulating numbers and especially binary numbers。

 So there are all sorts of convenient tools that can help you identify the rightNe mask。😊。



![](img/2e3273e948dfe780c569e287db5d7919_5.png)

For example， we have the IP Celk utility， which you can install from your favorite package manager。

If we pass it， our IP address and the netmask and slash notation using slash 16 in this example。

 then we get back output like this。It shows us the 16 Bs of the network portion， and the net mask。

Being said to all ones。But it also tells us that this was originally a lesbian network address based on inspection of the first two bits。

With 16 buts left for the host portion， we now know how many hosts we can have on the subnet。

Almost 64K。But with 16 bits left， we should be able to get two to the 16 hosts or exactly 64K。

But we are losing two entries。Because the first and last addresses on the network cannot be assigned to a host。

The first address is the network address itself。 and the last address is the so called broadcast address。

 Wherever a packet is sent to this address， it is broadcast to all hosts on the network。

So if we adjust the netm to a slash 24。Then we get the adjusted information as shown here with 24 Bs of network portion and 8 Bs of host portion。



![](img/2e3273e948dfe780c569e287db5d7919_7.png)

Yielding 2 to the8，-2 possible host addresses。As sed 26 then。Looks like this。

26 B for the network portion。6 bits for the host portion。But a Pcal can do more for us。

Suppose you want to take a network and create subnets of different sizes。

Let's say you want to carve up an existing slash 24 into one supplementnet able to contain 24 hosts。

 one for 64 hosts and one for 48 hosts。 What would be the right nest， My asks for that。

That's Oscarky Peacock。It shows us that， for the first network。We'd use a s 27。Able to hold 30 hosts。

For the second subn。We need a slash 25。And for the third up， Ned。We'll need a slash 26。

I Pac also shows us that we still have some network space left。 We could create another slash 27。

 with the remaining I P addresses。So what IPCrk showed us was that the calculations of the sir notation all follow the same logic。

Let's assume you have an IP address， A B， C D slash N，1，5，52，4，6，1156 slash 27， let's say。

Then we know that n represents the number of bits in the net mask that are all once describing the network portion。

I。e。 27 in this example。The total IP address length is 32。

 so the remaining bits available for the host portion are 32 minus n or 32 minus27 Ie5， our example。

The total number of addresses available here is then2 to the power of that number。

Or to do the 5 equals 32 in this example。But we know we can use all of them as we have to subtract2。

Namely， the first address of the network， the network address itself。

 and the last address of the network， the broadcast address。Finally。

 the net mask being just another 32 bit number can also be represented as a decimal quadded address。



![](img/2e3273e948dfe780c569e287db5d7919_9.png)

All right。Time for another break。In this video， we briefly mentioned the historical context of Class networking。

 This is not used any longer， but it's still useful to understand， as always。We then talked about。

The concept of dividing a network into smaller networks by E subnets through the use of a net mass can be identified to different logical steps in this process。

Now， all this applies to IPV 4。 But what about IPV 6。Well we'll talk about that in our next video。

 you will find out that things are quite different in the IPV6 world， but not all different。

It'll be interesting though， so make sure to catch our next video。Thanks for watching， cheer。



![](img/2e3273e948dfe780c569e287db5d7919_11.png)