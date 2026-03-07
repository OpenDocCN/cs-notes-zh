# 史蒂文斯理工学院【中英⚡计算机系统管理｜CS615 2021 System Administration】 p30 p29 Week 05, Segment 6 - Networking I： A Network of Networks -BV11QQcYmEzD_p30-

Hello， welcome back to CS615 System Administration。

This is week 5 segment 6 and after we discovered in our last video that the internet has a physical component with real world impact。

 we'll now look at exactly how the internet is comprised of independent networks。

We've already seen that we connect to the internet across the globe by using， for example。

 submarine communications cables， which physically connect one continent to another。

 And we intuitively understand that obviously， there are different legal entities controlling the endpoints of these cables。

 and thus， the connectivity that is made possible by them。

And so this is one direct implication of the nature of the internet of it being not a single network。

 but a network of networks。And this network of networks has really taken off since its humble beginnings back in the 1960s and 70s。

 hasn't it？As early as 1984， the John Gage from Sun Microsytems coined the phrase  the network is the computer。

 meaning that all the computers are merely connected interfaces to the larger network。

You see the idea of putting all your compute resources onto the network is not all that new。

But admittedly this led to some confusion， so it's useful to clear things up。

 the network is indeed the network and the computer remains the computer。But now about that network。

 it's not really one network。 And even though we all think of computing resources that are reachable via the network as being in magical cloud land。

Of course， system administrators know all too well that there is no cloud on other people's computers After all。

 at some point somebody somewhere has to maintain these resources。But okay。

 let's focus more on the network， or rather the networks that make up this network。

Networks have a tendency to grow if we connect to endpoints， it's trivial。

If we connect multiple devices， we need a network layer， as we've already discussed。

 if the devices are within the same broadcast domain such as being connected via switch。

 then we have a layer2 network。And we can connect multiple such layer two networks with one another using a layer 3 device or router。

 And this way， we have also already discussed the need to supplement our IP blocks。

 as you will recall。But so， of course， we will eventually want to connect multiple such networks。

 and when we do that， we begin to talk about autonomous systems， networks that are grouped together。

The various networks within such an autonomous system。

May be made up of independent networks using separate IP space。

 IP space that has been allocated to the controlling entity down from IA to the RIR and the LIR as we discussed in an earlier video。

And so as we connect these autonomous systems， we are building the Internet。

What you see here is the visualization of the routing path of the Internet Circa in 1997。

 color coded by which R IR assigned the space and grouped via connection path。

 The central stars in this graph represent the systems that are connected to more other networks。

This network looks a bit different now in 2021， with obviously more networks and more connections between the networks and more geographical regions。

 but still representing the routing paths as before。

And these routing paths are based primarily on knowledge about exactly these autonomous systems since the B gateway protocol or BGP shares its routes。

 that is the reachability of the different networks by average ASS number it can talk to。

But where do we get our A S numbers from。Who would better be in a position to assign A S numbers than the same entity that also allocates a P space？

So yes， we once again go back to Iena， which allocates ASS number blocks to the RIrs。

 which then allocate the specific ASS numbers similar to how I blocks are managed。Okay。

 so how do we find out what our A number is One way to look at the information about a given network block allocation is via the who is command which queries the various network information centers via the whois protocol。

As you can see here， the query usually starts at Aena and then may query the relevant RIs for the information。

 and in this way the protocol is similar to the DNS protocol。

 which we'll discuss in some detail in the future video。

So if we want to find out about our Stevens netpl， then we pass in our web server IP address。

And we can then see。That Aena tells us that it had allocated the 15，5 slash 8 block to Aaron。

 which then tells us。That it allocated the 1，5，5，2，46 block to Stevens back in 1991。

Arandon also provides us with a URL。That gives additional information about this net block。

So let's see what they show us there。Hey， look at that as Jason neat。

Looks like there's a fair different information about the net block and its owner here。

Let's see if we can extract the ASS number from this。There we go， Stevens A's number is 16889。Now。

 if we look at the information from Aaron in more detail。

 we find that Stevens has been allocated to multiple IP blocks。Which we can then extract here2。

Did I mention that I like Jason and JQ， really useful。Anyway。

So we see that Stevens has multiple net blocks， not just the 1，5，5，2，4。

6 s 16 net block we see so often。In fact， it looks like Stevens also has an IPV 6 network allocated。

's just unfortunate that it doesn't seem to be used much。But allright。

 so now we can start to visualize how our network connects to others。

Let's say that at the bottom network here represents Stevens I。e。 A S 16889。

With its net blocks used in whatever way Stephens deems fit。

But now what is the ASS number of the network that Stevens connects to？For that。

 let's just find out what the path that our packets take when we talk to some web server on the internet。

We'll be looking in much more detail into how the trace ro utility works in one of our next videos。

 but I trust you're familiar with it。When we trace our packets to say the Yahoo website。

 then we get back output that shows us the different hops along the way。

Here we see that we're jumping from where we started to another address in 155，246 s 16。

 then an RFFCC 1918 address that is a private network address。

Then some other 155246/16 addresses before we then leave the Stevens network and eventually find our way to the Yahoo networks。

So， now。Let's take take a look at the first non Stephens address here，1，3，1，5，6，2，5，1，1，0，5。Okay。

 so this address is in a net block that's assigned to the New Jersey Higher Education Network。

And we get the ASS number。 We'll use a different who is server here that's set up to provide just that information。

There， that's pretty convenienthuh？😊，Okay， so now we've identified the A S number of the next network。

 As S 21，9，7，6 in this case of NJ H。And we could do this manually for each hop along the way。

 but fortunately， the trace for utility has an option to do this for us。So we have Stevens AS 1689。

Then in J edge A is 21，9，7，6。Then， A S 46，37。And ASS 10，310， which appears to be Yahoo' AS number。

 but there's also AS S 26，101 showing that， of course， an organization can have multiple ASS numbers。

So with that information， our image of how the packets go through the different networks can now be filled in。

Stevens ASS 16889 is connected to NJH AS 21976， which connects to AS 4637 and from there to Yahoo's AS 10310 and AS 26101。

So we see that the connections between the networks are made in specific locations， it seems。

This process of connecting the different networks is called peering。

 and it takes place in the form of an actual physical connection between the systems of these entities。

 allowing them to exchange routing information via aBGP。

These connections are made at so called peering points or internet exchange points， or IXPs。

 and strategically located data warehouses around the globe。



![](img/3d049b4931937bf5779f2ab866e3fa71_1.png)

And one of the great things about this， like so much on the internet。

 is that it's primarily public information。That is。

 we can look up who is peering with whom in what location why， for example， the peerering DB website。

So if we take the NJ edge as number 21976。And plug it in here。

Then we see a fair bit of information about this organization， including which IXP is peering at。

One of them is the New York International Internet Exchange point， or NY II X。

 which we also see reflected over here in the DNS name of the next hop in As 4637。Which。

Belongs to Telstra。Which then connects to As 10，3，10。Which is one of Yahoo's AS's numbers。

And the entry。Here shows all the IXP's Yahoo Pieret。

Which turns out to be quite a few all over the globe。Now， the packets hopped around AS 10。

310 for a bit before going into ASs 26，101。But。We don't find that A S in appearing D B。

And neither do we find Stevens ASS 16889 in the P& DB。

Because both of those networks do not appear with any other networks。

 That is not every network directly appearss with others at a public IXP。

 In addition to the public peering locations， there are also， of course。

 private connections that are made， such as between Stevens and NJH。

 which provides the network connectivity to the larger internet here。



![](img/3d049b4931937bf5779f2ab866e3fa71_3.png)

The larger networks like Telstras， AS 4637 then connect many more other networks and thus become a central point in the network visualization we saw at the beginning of this video。

Now， as you can imagine， these peering points， the internet exchanges where these connections are made between the large carriers need to have some big pipes。

And as that is a large selling point， you can often find some interesting stats on their websites。

The Amsterdam Internet Exchange is one of the largest IXpiece in the world and shows the daily throughput of 9。

4ter per second。The daily stats show nicely how traffic drops down a bit at night。

 ramps up during the day， peaks after dinner and then drops off again。

Monthly and yearly stas then show an increase in overall throughput over time。The German DECX。

 another one of the world's largest IXPs， also has some stats with similar patterns。

As does the Moscow exchange， although here the throughput is a bit lower than in Amsterdam or Frankfurt。

With even lower rates for IPV 6， it appears。The NY Iia X stats look like this。



![](img/3d049b4931937bf5779f2ab866e3fa71_5.png)

The Toronto Exchange stats like this。

![](img/3d049b4931937bf5779f2ab866e3fa71_7.png)

And the Netnot exchange in Sweden like this。So I'm sure you've noticed the graphs all look similar。

 not only in the patterns they show， but also eagerly in identical in style。

This is no surprise as they are generated using one of the standard open source network traffic graphing tools around MRTG。

Even JPNP seems to be using MRTG。And if you get involved with any network architecture and administration。

 you're quite likely to become very familiar with graphs that all look like this。All right。

 I think we can break here and conclude our journey through this network of networks。

To ensure you internalize the lessons we illustrated here。

 I recommend that you try to identify AS numbers of other organizations and companies and find out where they appear using the tools we've shown in this video。

Try to find out what happens when two organizations develop a dispute and one wants to deep here to remove the connection with the other。

 there have been several cases where two competing companies use this or the threat of deeping as a means to harm their competitors。

On Wikipedia， you can find a list of the largest internet exchange points and you can browse their websites to find some stats like we showed a second ago。

But there are also some locations that are less open。 the network access point of the Americas。

 for example， is housed by Equinix， a huge colocation provider。

 try to find out more about these exchanges。Finally。

 if all of this interests you enough that you want to be part of the community of network operators that literally and physically built the internet。

😊，You can join the North American Network Opera Group or Nnoc。

 The public meetinging list is a really interesting place to hang out and learn about the structure of the Internet and the various aspects most people higher up the stick。

 never think about。O。And with that， we're concluding our first week of networking。

 but as I threatened， I mean， promised， we are not done yet with this topic。

In our next couple of videos， we'll again go down the packet level to trace traffic of different applications and protocols。

 but we also will need to take a look at just how our host knows， how and where to send packets。

 You'll be getting intimately familiar with TC P dump and the various sts tools。

 Hope you're looking forward to it。 Until then， Thanks for watching， cheers。😊。



![](img/3d049b4931937bf5779f2ab866e3fa71_9.png)