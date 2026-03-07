# 史蒂文斯理工学院【中英⚡计算机系统管理｜CS615 2021 System Administration】 p25 p24 Week 05, Segment 1 - Networking I： Layers -BV11QQcYmEzD_p25-

Hello and welcome back to CS615 System Administration。 This is week 5 segment 1。

 and we are starting a longer discussion on networking。😊，In the coming videos。

 we'll dive down into the details of TCP IP networking on a Uni system。

In the process we'll travel up and down both the four layer TCPI stack， the7 layer OSI model。

 discover just how exactly the Uni system figures out how to talk to other systems and learn a bit about the physical structure of the internet。

 as well as a few parts of its governance。These videos may well cover parts of topics you've already learned in other classes。

 but I believe that we should be able to learn something new in each of them still。

So why don't we get started with the most familiar layers off the OS I stack？

I'm sure you've all seen this before， it's how we oftentimes attempt to represent the different functional parts of a communications network。

From the bottom up， we have the physical and data link layers。

 which in the TCP IP4 layer model are combined。Here we're talking about the physical medium and the bit rate。

 full duplex， half duplex， etc。And the node to note transfer of the data using this medium。

Then there's the network layer， we have a moving packets between different networks。

On top of that is the transport layer， where things start to get a bit shady because most of TCP fits in here。

 but TCP also includes features that OSI would classify as belonging in the session layer。

But honestly， there's a lot of confusion around what goes into the session and presentation layers。

 and there's been plenty of criticism of the OSI model。

The dirty truth is that in that socal real world， you really don't even need to know the details here。

 except for some reason people like to ask you about it in tech interviews。

 so make sure to check the Wikipedia page to have the answers they want to hear。The last layer。

 layer 7， and is the final layer that people like to the reference， the application layer。

Most distinctions for day to day discussions fall into either layer 3 and below or layer 7。

But of course， there are two additional layers that nobody ever tells you about。Layer 8。

 the financial layer， meaning at some point， somebody has got to pay for all the things you're doing over here。

 and that will influence how you develop things。 And then， of course。

 you realize that money doesn't come out of nowhere and that there's yet another layer sitting on top。

The political layer， the organization and how it is structured influences how the money is allocated and sets the direction for what is developed。

 deployed and supported。And guess what， you almost always operating on this layer here。

We'll get back to the influence of politics， even on a global scale in future videos。

 but let's leave this theoretical layout model behind for the time being and look at some actual network traffic to better understand what this model is intended to illustrate。



![](img/9083f9407cdb0a00563ed129a2d26cbf_1.png)

So let's start out capturing some network packets。 We do that using the TCP dump utility。

 which we start and run in the background， grabbing the port 80 traffic we're interested in this example。

With thatTCP I running in the background， we make a simple HETP head request to the CS Stevens website。

We don't care about the output。 We just care about the packets that are collected。Okay。

 we bring TCP back to the foreground and interrupt it。

Change the ownership on the output file so we can operate in it as a normal user。

And then we simply take a look at the first packet captured in this file。



![](img/9083f9407cdb0a00563ed129a2d26cbf_3.png)

We see a lot of information here and being able to make sense of raw TCPM output is a critical skill for system administrators。

 as we oftentimes have to troubleshoot network connections and protocols。

So what are we looking at here， How does this relate to the OSsI model we just showed before？

Tell you what？Let's first go back to the much simpler TCP IPP stack model。 Don't worry。

 we'll get back to the TCP number output in a second。So the TCP IP model also uses layers。

 but unlike the OSsI model， it only uses four layers。And as shown in this illustration。

 these layers are actually more like layers of an onion and that each one wraps the other。

It is we're talking about encapsulation， which is nicely illustrated here where we see that the link layer provides a header and a footer that encapsulates the internet layer where we're using in this example anyway。

 the IP protocol， which adds its header and encapsulates the TCP packet。

 which finally includes the application data。

![](img/9083f9407cdb0a00563ed129a2d26cbf_5.png)

So let's map these layers to what we're seeing in the TCP DOM output。Okay。

 so let's look at the details and the hex decimal output here。

The first 24 bytes include the link layer information。The next two bytes。

 tell us what type of protocol is encapsulated。 IP P in this case。Which we find in these 24 bytes。

With the remainder。Being the TCP payload。This nicely illustrates how the encapsulation model translates to actual bytes in a packet capture。



![](img/9083f9407cdb0a00563ed129a2d26cbf_7.png)

So let's go ahead and take a closer look at what exactly is in those bys。The first 12 bites here。

Other the link lay a destination address。With the second 12 by， as the source address。



![](img/9083f9407cdb0a00563ed129a2d26cbf_9.png)

What exactly are there？Well， our link layer data link protocol here is Mac media Max control。

Our network interface， then at zero in this case， has a Mac address as shown here。

Since rather conveniently， the Mac address already has an hex。

 we don't even have to convert anything instead can see it right here in the packet。E076，63-723900。

Okay， so that's our source address。 The N we're setting the data through。

What about the destination address。We can look at our ABc table。

 which keeps the mapping of the Mac addresses to IP addresses on its layer 2 network that it's seen。

So here we see that our destination Mac address，0，0，1， B2，1，7，3，59，5 a。Maps to the IP address。

 166-84-7192。Which we can see to be。Our default gateway。So this makes sense。

 no matter where we are actually looking to send our IP packet。

 if it's not on our layer2 network segment， then we have to hand it off to the default gateway so it can be routed correctly。

And that is why our link layer frame has the destination address of our default gateway。

 so our default gateway will then take this packet and unw the link layer information to look at the IP packet inside。

What does no P packet look like。Well， it looks like this。

That is the structure of the IPV4 packet as defined in RFC 791。

Which then allows us to also look at all the different bytes we observed in the TCP dumpm packet and make sense of them。

So the first bite here。Incodedes the I version for in this case。

 as well as the total length of the IP header，5，32 B chunks adding up to 20 bys。

Which we see in ourTCP output up here。The5 up here then also tells us that in this case。

 there are no IPV4 options or pedding， allowinging to determine whether payload。

 the TCP data in our case begins。In the next bite。We encode the differentiated services code point or DSCP bits often used for quality of service assurances。

 as well as the explicit congestion notification or ECN field。Which in our case， does all0。

The next two bytes specify the total length of the packetd， including the header and data。For us。

 this is 60 bytes in total。Already telling us that the TCP payload is 40 bytes in size after you subtract the 20 byte IP header。

Then we have two bytes for identification， which is commonly used to identify I fragments for reassembly if the packet had to be fragmented in transit。

 again， that's all0 for us here。The next two bytes again encode two pieces of information。

The flags with a don't fragment bit being set here and the remaining 13 bits used to identify the offset if your packet had been fragmented。

Since it wasn't that zero， and we end up with hex 40，00 for these two bytes。

Next is the one by TTL telling us how many hops the packet may at most take。

We specify the default 64 here， which then becomes 40 hes over here。

After that comes the by specifying what protocol the encapsulated payload is。For TCP。

 we specify6 over here。Then we have two bytes for the IP head checksup。

Which is a very simple once complement checks on providing minimal corruption protection。For us here。

 that's Hex B903。The remaining 64 bits specify the source and destination IPV 4 addresses。

 which we know to be 32 Bs in size each。The source address here is Hex 16540763。

 and the destination address， Hex 9 B， F6，38，0 B。Since there are no IP options in this packet or the remaining bytes。

 not TCP dump output up here， and thus the TCP payload。But wait， what are the I P addresses。

 We know what they are in Hes。But let's see why we pick these values。

We know that these four bytes here are the source address。And these four bytes。

 the destination address。Let's convert the hex numbers of the source address into decimal。

We can use the BC tool for this and set the input base to 16。

 which then lets us simply enter the hex numbers and itll spit out the decimal values。

So value a6 hex becomes 166 decimal， 54 hecx， 84 decimal， and so on and so on。

Let's look again at our Nick and see what I P address it has。



![](img/9083f9407cdb0a00563ed129a2d26cbf_11.png)

Well， what do you know， our IP errors is indeed 16684799。So that's our source address。

What about the destination address？Well， since I somewhat frequently have a need to convert addresses like this。

 I create the shell function to do the translation from hex to decimal for me more easily。

The slides have a link at the end to a shell file that contains several of these functions if you're interested。

Anyway， so our destination address is Hex 9 B， F 6，38，0 B。Or 1，5，5，2，4，6，56，11。

Which isn't all that surprising since we had tried to make an htP request to ww。cs。tevenstedduu。

 which translates to1552465611， the destination address we observed in the TCP dump output。



![](img/9083f9407cdb0a00563ed129a2d26cbf_13.png)

So we've successfully and completely dissected the link layer network layer information from the single packet we captured。

 congratulations。Now， as you may know， there are other tools that allow you to inspect captured packets。



![](img/9083f9407cdb0a00563ed129a2d26cbf_15.png)

One of them is the popular wirere shark application。

If we load our Pc file into wire shark with that single packet set。

 then we can observe all the same data we pulled under the raw hexpis we observed。Like before。

 we find the link layer source and destination addresses。Over here。😊。

The I before information over here。Broken down by a。Vusion， length。D SCP and ECN Bs。

Length identification， flags， offset。T， T， L， the protocol。Check some。And， finally。

The source and destination addresses。As well as the remainder TCP payload。As you can tell。

 Wishrk is really a useful tool as it can easily identify all these bits for us。

 but I do think it's important for system administrators to be able to tease out the information they need using TCP D。

 which is why I showed the breakdown one by one in this video。



![](img/9083f9407cdb0a00563ed129a2d26cbf_17.png)

Okay， let's take a break here and recap real quick。We've name dropped the OSsI model as required。

 but conceded that the simpler four layer TCPIP model may perhaps be a bit more useful。

We've observed that the IPV 4 IFC is not lying to us。 The information it prescribed is， in fact。

 found exactly where it says it should be。And I think that's a very useful lesson too you can understand any application or protocol if you can follow the specification。

 and the internet RFCs are usually very well written and easy to understand。

And I also hope that I showed that wire shark as useful as it is is not some weird sort of unknowable magic。

 but rather is just the application of understanding the protocol。

I think youll see now you could build a tool like wire shark based on what you've learned here。

 and it conceptually。But this only really got us to the I P layer。

 and we have still a lot of topics left to discuss in our coverage of networking here。

 So let's take a look at what's coming next。In our next video。

 we discuss IPV4 sub neting before we then move on to IPV6 to see how that differs。After that。

 we'll make a short detour， up this stack to layer 9。

 the political layer and discuss how the internet is administered and controlled in a very high level and with a focus on IP space allocation at management。

But we'll also talk a bit about the physical structure of the internet。

I know I know it's all just a series of tubes， or is it， we'll find out。

So enter the next time and thanks for watching， cheer。



![](img/9083f9407cdb0a00563ed129a2d26cbf_19.png)