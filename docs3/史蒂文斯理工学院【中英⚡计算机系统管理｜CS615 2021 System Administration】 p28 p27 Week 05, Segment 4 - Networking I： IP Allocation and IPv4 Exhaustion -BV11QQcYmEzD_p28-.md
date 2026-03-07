# 史蒂文斯理工学院【中英⚡计算机系统管理｜CS615 2021 System Administration】 p28 p27 Week 05, Segment 4 - Networking I： IP Allocation and IPv4 Exhaustion -BV11QQcYmEzD_p28-

Hello and welcome back to CS615 System Administration。This is week 5 segment 4。

 and so far we've covered a fair bit of ground with respect to the IP protocol。

 having looked at the details of the IPV4 and IPV6 headers， but we've avoided the difficult question。

 Mommy， where do IP addresses come from？And just why do we have an IPV 4 and an IPV 6 address。

 And wait a second， what happened to IPV 5。Alright。

 let's quickly resolve that last question because that's easy。

 there is in fact an IP layer protocol using protocolcol version 5， the internet stream protocol。

 and yes， logically there also were in fact protocols versions 1。

2 and 3 with version 3 being the first version in which TCP and IP were split。

But let's get back to IPV4。As we said， an IPV4 address is a 32 bit number。

 meaning we can have exactly2 to the 32 such numbers。2 to the 32 is a large number。

 and so the entire IPV4 internet address space is approximately 4。3 billion IP addresses。Well。

 at least that's the theoretical space we have。Now， how do you go about getting one of those？

As you may know， many systems come up and seemingly magically acquire an IP address via EG DHCP。

Where do they get that address from？Let's take Stevens， for example。

 how did we end up with almost all our Ipies beginning with 155，246？To answer that。

 let's take a short trip back in time to the early days of the Internet When I P address space management and much more lay in the hands of just one man。

 more or less， John Postsper。

![](img/8111a01c0ac4dadabe3c88bf66126a65_1.png)

John Pasler was an immensely influential person in the development of the internet and initially administered the Internet Ass Numbers Authority。

 or IAena， meaning when an organization needed to have a P space assigned， he took care of this。

He also co authored a significant number of RFCs， including those that became the foundation of a dominium system。

 which we revisit in a future video lecture。But obviously having any one person in charge of IP address space allocation is not a scalable solution。

 and so the administration of IENena was transferred to IAN。Now。

 I'm really glossing over an incredibly impressive history of one of the biggest Internet pioneers and architects。

 So I strongly recommend you read up and John Pasel on your own。

 You likely have heard of Pastel's law， also known as the robustness principle and software programming。

Be liberal in what you accept and conservative in what you send。 This， too。

 is named after John Pastel。But okay， so we now have IAA。

 a nonprofit standards organization which oversees global IP address and autonomous systems number allocation。

 route zone management， etc。Well revisit these areas in future videos。

 but for today we'll stay focused on the management of the IP spaces。



![](img/8111a01c0ac4dadabe3c88bf66126a65_3.png)

So IEA is in control of the IPV 4 and IPV6 spaces， meaning it can take out large net blocks and assign them to other entities。

Now you'll note that I have illustrated the IP spaces as missing certain parts that are not available to Ana to hand out。

Which is because for both IPV4 and IPV6， there are certain net blocks that are reserved for special purposes。

 such as the RFC 1918 private IP space you are all familiar with and is IPV6 equivalent。Anyway。

 so of the net blocks that remain available。IAna may then assign large chunks to the regional Internet registries。

 such as the African Network Information Centre or Ephrenic。

The Asia Pacific Network Information Center， or Apninic。

The American Registry for Internet Numb or Aaron。The Latin America and Caribbean Network Information Center or Lachnic。

And the Rezo IP repair， network Ordination C or Re NCC。

Each of these RIrs manages the allocations for a specific geographical region。

 which illustrates the distributed nature of the internet， despite its obvious US origins。By the way。

 Randwell Monroe， the artist behind XKcD did a neat illustration of the IP space。

 which I recommended check out。Anyway， so the RIRs together are loosely organized as the Numb resource organization or NRO。

 which helps coordinate internal governance on this level。Now。

 each of the R Is have been assigned I P space by Ayena。

And can then further divide and assign those net plug to the so called local Internet registries to use or further allocate。

Most of these LIRs are Internet service providers。Or academic institutions。

 as well as large scale enterprises， as shown here under Er。

So to answer our earlier question as to how Stevens got its I space。

 it was allocated to Stevens by Aaron from a net block assigned to it by Aena。Now， Aaron is， however。

 a bit of a special case due to the US centric management of the Internet in the early days。

 Aaron did receive a large number of historical allocations。

 which it then may further allocate to another RR， such as in the example of the 15792 s 16 net shown here。

 which it delegates to Lani。Which Lachnic may then further delegate in its entirety to。

 as shown here， the University of Buenos Aires in Argentina。

So we see that I space may actually have geographical properties。

 and if you've been working with these networks for long enough。

 you may even have memorized some and know that， hey。

 this traffic connecting to my system comes from Asia， for example。But that can be a bit misleading。

 since obviously， I addresses do not have a specific physical location inherently bound to it。

 but rather， it's a question for the administrative ownership of the I space。 But that， in turn。

 can be used to see the geolocation databases around the world。



![](img/8111a01c0ac4dadabe3c88bf66126a65_5.png)

Anyway， the LI arsenal further delegate the net blocks as they see fit。

 possibly dividing them using Nems， as we discussed in a previous video。For example。

 we know that Stevens， having been assigned the 155246/16 net block。

 has assigned the 15524689/24 net block to the CS department。

 and we can observe that Verizon after having bought Yahoo a few years ago became the new owner of the net shown here and specifically assigned several IP addresses to a specific service。

We also note that the allocation from my Aa at the top down to the end sides oftentimes follows some general rules。

For IPV4space， for example， IAA only handles s 8 allocations， which adheres to the RIrs。

The R Irs tend to divide the s As into smaller networks and hand out， for example， s16s to the LIrs。

 which then can divide the network further as we just noted。But okay。

 so now we know where IPRS has come from， But then why do we have IPV 6 in addition to IPV 4。Well。

 think about the allocations we just discussed。 Our IPV 4 space is 32 B， because， well。

 that's what Visf thought would be a reasonable choice for a little experiment to see if this Internet thing might take off or not。



![](img/8111a01c0ac4dadabe3c88bf66126a65_7.png)

Turns out it did。 And we've been stuck with us 302 bit space ever since。Even though 4。

3 billion addresses sounds like a lot， it really isn't。For starters。

 we don't even get the full 2 to the 32 space for use on the internet。

There are certain blocks that are reserved， as I mentioned earlier， the private I P space。

 for example， as well as several other net blocks reserved for different purposes。

Those together make up approximately 13% of the entire IPV4 space。

But not only that in the early days of the Internet。Allocs were made rather liberally。

 And so some of the early participants did get entire class A networks assigned over 16 million addresses assigned to AT& T。

 Apple， M I T， et cetera。The other problem is that organizations themselves have not been allocating space efficiently themselves。

 leading to fragmented subnets， requiring additional allocation after the effect。



![](img/8111a01c0ac4dadabe3c88bf66126a65_9.png)

And of course， it's not helping that we're now putting light bulbs and refrigerators and toothbrushes on the internet。

 each requiring our occasions to。So the 2 to the 32 addresses we started out with quickly began to be depleted。

Ayena exhausted its pool of unallocated s 8 networks just about 10 years ago。

 and the R Rs then followed quickly with Ak in April 2011。Re in 2012。Lchic in 2014。Aarron in 2015。

And ephrennic in January last year， meaning we are officially out of IP P addresses in the IPV4 space。

4。3 billion addresses pretty much used up。 a problem that we all knew for a long time， was coming。

Which is why IPV6 was introduced way back in 95 and why it's so disappointing to see that now。

10 years after Iena ran out of V4 addresses to allocate。

 we still have organizations and companies that do not support IPV 6。But okay， so with IPV 6。

 what are our default allocations。

![](img/8111a01c0ac4dadabe3c88bf66126a65_11.png)

The R Is generally get assigned a slash 12， which they then delegate to the L Irs in chunks down to a slash 32。

 which those then may delegate to insights and chunks of s 48。And final end user lens， the addresses。

 your Wifi A hands out to you， for example。Being for the most part， a slash 64。Now， think about that。

 most end users will get a slash 64。 that sounds incredibly wasteful。

Sure you can put all your refrigerators and Tvs and light bulbs and toothbrushes on the Fish 64。

 but you still have so many Is left over that are basically wasted。

Aren't we going to run out of IPV6 addresses system in this way？😊。



![](img/8111a01c0ac4dadabe3c88bf66126a65_13.png)

To understand why this is not a problem， it's critical to understand just how large the IPV6 space really is。

2 to the 32 is 4。3 billion addresses， which we just realized really isn't all that much。

Now you're LC CSs major， so hopefully you understand better than the average person exponuniation works。



![](img/8111a01c0ac4dadabe3c88bf66126a65_15.png)

But let's illustrate just how many addresses we have available in the IV6 space。So 2 to the 1。

28 is' a number that。Looks like this。39 decimal digits，340 undesion，282 desion，3 and66 the million。

A really large number。How large a number is that？Let's see。

How many IP addresses we can give every person on the planet。Okay， that's 4。

41 times 10 to the 28 IP addresses per person。That's hard to fathom。

How many atoms are there in a regular human being？Around 7 times 10 to the 27。So。We could give。

S I addresses to every atom of every single person on the planet。An Internet of atoms。

What's another thing that we know They are a let off。I know。Stars。Oh。

 so not enough stars in the Milky Way to really make a dent here。How about the observable universe。

Hey， we could give 340 trillion I addresses to every star in the observable universe。

What if every single star in the observable universe had a planet with people like us。 Well。

 then we could give。Over 44000 Ies to every person on an earth orbit in every single star in the observable universe。

That's how many IP addresses we have， and that's why assigning a slash 64 to every end user is not going to deplete the IPV 6 address pool。

Even though。By assigning a slash 64 or 18 quintillion addresses。We are giving every end user 4。

3 billion IPV for internets。I know exponentiation is fun， isn't it， Anyway。

 I hope this little bit here gives you an idea of the size of the IPV6 address space。

Play around with it some more。 Well， from Al is a pretty neat engine for this sort of thing。



![](img/8111a01c0ac4dadabe3c88bf66126a65_17.png)

Allright， so let's pause here。 We've seen how IP P addresses are assigned。

Ana allocates net blocks to the RARs which carve those up， assign them to the Lrs。

 which then may further the delegateator assign them。Now， look around。

 Can you find out what I P blocks belong to which companies organizations。

How can you go about finding out what geographical region an IP block is allocated to？Next。

 to better understand what IPD4 exhaustion means and practice from an RIR's perspective。

 take a look at the information provided by Sa Aphrodek and see how many IP addresses they have left to assign。

Also， think about why it is that ephrenic is the last one to run out。

And what that says about internet proliferation and traffic distribution around the globe。

Think about what normally happens when a resource becomes scarcee。Oftentimes， a new market emerges。

 Can you find out where and how organizations could trade a P space they might not need any longer。

All of these questions are intended to get you to think about the internet in real world terms。

Meaning， it is not an abstract thing， but has certain physical properties and implications。



![](img/8111a01c0ac4dadabe3c88bf66126a65_19.png)

We'll go into some of the details of the physical structure of the internet in our next video。

Until then， thanks for watching。Cers。