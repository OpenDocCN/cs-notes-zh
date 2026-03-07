# 史蒂文斯理工学院【中英⚡计算机系统管理｜CS615 2021 System Administration】 p33 p32 Week 06, Segment 3 - Networking II： ARP and NDP -BV11QQcYmEzD_p33-

Hello and welcome back to CS615 System Administration This is Week 6 segment 3 and we beginning a series of bite size videos covering some of the more common protocols you regularly encounter as a system administrator across the standard TCPIP stack。

While some of this may be familiar to you from other classes。

 I hope that you will find at least something useful in each segment。😊，In this video。

 we'll discuss the address resolution protocol or ARP and its IPV6 equivalent。

 the neighborigh Discovery Pro or NDP。We already saw orbit in our last video。

 but especially the comparison to the IPV6 NDP should help illustrate a few important concepts。

His first spoke at the a cache of a few systems。On our typical you see two instance。

 it'll look something like this。But since our instance resides in a dedicated VPC。

 and we don't have any other systems spun up there。

 there is not going to be a whole lot of local traffic on this network。

So let's see what things look like under our Stevens Linux lab systems。Okay。

 this is perhaps a bit more interesting， as we can see， numerous systems on our network。

But to illustrate the use of the R protocol， we need to be able to flush the cache and capture packets for which we need super user privileges。

So let me show you some real world traffic from my personal virtual server。All right。

 not particularly exciting。 Only a few entries here， but at least now we can start our analysis。

We run a TCP dump capturing all a traffic。Then flush the a cache。Next。

 we generate some IPV4 network traffic。

![](img/875e42bf2881a4551345425144976e0f_1.png)

ICMP Echo Re Echorely also known as Ping in this case。And then display the Ap cache。

We can now stop the easyP dump again and take a look at what traffic we captured。Oh， wow。

 look at that。 That's a lot of packets we saw here。If you run this through WC。

 you'd see with almost 6，000 packets here。Now， obviously not all of these were from our system。

 so let's take a look。You see a whole bunch of who has requests showing that those requests made by other systems are broadcast to all devices in the broadcast domain。

Down here， we see 1，6，6，84 I 240， asking for our I P address，1，6，6，84，7，99。

And the It reply is what we are then sending Uniuchcast to that address。

We see a whole lot of other who has requests with the only is that replies being our answers to other hosts asking where we are。

Although every now and then we also oversee other isat messages without a who has request。

This is known as a gratuitous ab。 a reply that nobody asked for。

 This commonly happens when the new interface comes up to let the switch know where this device is。

Okay， so to recap and visualize once more， we saw requests from other systems asking who has this IP address。

 please let me know。Such requests are sent by the sending system with a destination make address of all once。

 or FFF F。Which the switch then broadcasts to all systems in the broadcast domain mean。

Which is why we sitting on our system up here in the top left that 16684 799。

 were able to see the request。In other words， who has is a broadcast request。

The reply to that request， which we did not see。Was delivered via a uniccast only to the system that made the specific request。

But if a system wants to announce to everybody in the broadcast domain its location。

 then it can send a so called gratuitous arp， which again， has a destination address of all ones。

And thus is also broadcast to all systems。Finally， it's worth noting that it's possible for you to observe addresses outside of your subnet。

 but that are still within your broadcast domain。This might be the case if the switching question has multiple subnets in the same Vlan。

 which thus combines those subnets into the same broadcast domain。Allright， so that's Ap。

 and as we've seen， this is IPV for Ondi。What happens in the IPV 6 world here？



![](img/875e42bf2881a4551345425144976e0f_3.png)

In IPV 6， there is no ap， but instead the drop of discovering your neighbors is handled by Well。

 the neighbor Discovery protocol， which utilizes ICM。

So let's try another TCP dump this time collecting ICMPV6 traffic。

We flush our neighbor discovery table。And send out a few IPV 6 Packers to trigger the neighbor discovery from our end。



![](img/875e42bf2881a4551345425144976e0f_5.png)

After this， we can look at our NDP table。😊，And find this entry over here。O。

So let's take a look at the network packets we captured。Oh， like before， that's a lot。

 almost a thousand packets。Let's look again at our IP addresses。And what's our default IPV 6 route。

There。This link local address。😮，And our global scope address is this one over here。

Let's see if that shows up in our TCP dump。There。So we see an ICMPV6s NA solicitation from our global address to this FF02 column Col 1 address here。

 asking who has the address of our default route？Note that the low order 24 Bs。

Of the address we're looking for is combined with the FF or2 column column 1 column FF prefix that the default route。

Repllies to our global address。To do that， we then see the default rod ask， hey。

 who has this global address that I'm supposed to reply to？

To which we reply from our link local address down here。Now， let's look at our NDP cache。Two entries。

If we send an ICMP echo request to this special address here， FF or2， column and column 1 then。

Look at that。 We get a lot of replies back。And our NDP Ca now has a lot more entries。

This is because this address， FF02， column column 1 is the All node multicast address with us requested a reply from all Is in that multicast address。

Let's compare and visualize like we did before。Here has all the setup up。

 just like before with the various IPV6 addresses。Know that each system has both a linked local address as well as a global address。

If we want to find out what the Mac addresses of a given IPV6 address。

 then we issue a neighbor solicitation to the so called solicited note multicast address。

This address is determined by combining the FF42 column column1 column FF prefix with a low order 24 bits of the desired destination address。

Any system with an IPV6 address matching those low order bits joins that specific multicast address。

 and our request is then multicast to only those addresses。

 unlike in the case of Ap where these requests were broadcast to all systems in the broadcast domain。

The reply， the neighbor advertisement， then is returned as a Unicast target is message。But of course。

 we can send messages to all systems via the All nodes multicast address。

 which is link local in scopepe and which then gets delivered to all systems and that link local broadcast domain similar to the A requests we saw for IPV4。



![](img/875e42bf2881a4551345425144976e0f_7.png)

All right， then to recap。We saw the address resolutionol protocolcol or ARP to find an RFCA26 and used for IPV4。

We saw the who has requests going out as a broadcast。

And the is that replies being uncast unless broadcast as gratuitous announcements。For IPV6。

 we saw the neighborigh Disc protocol， and we saw different addressrocopes in play。

The neighbor's solicitation， who has， went to the special solicited note multicast address。

 While the neighbor advertisement target is went to the global Unicast address that made the request。

But like gratuitous our announcements， we can also generate similar unsolicited neighbor advertisements。

 which is simulated via the pink packet sent to the All Nos multicast address。

Now it's worth noting that in IPV6， the neighbor discovery protocol happens inside of the network layer using ICMPV6。

We'll take a closer look at what else happens with ICMP in our next video。

Make sure to play around with TCP dump and capture packets on your own systems。

We'll be using TCP dump more and more in the next few videos。Until then， thanks for watching， cheer。



![](img/875e42bf2881a4551345425144976e0f_9.png)