# 史蒂文斯理工学院【中英⚡计算机系统管理｜CS615 2021 System Administration】 p37 p36 Week 07, Segment 3 - The Domain Name System, Part III -BV11QQcYmEzD_p37-

Hello and welcome back to CS615 System Administration。This is week 7 in segment 3。

 and we'll try to wrap up our discussion of the domain name system。Now， obviously。

 this will leave out many discussions since the topic as vast as the DNS cannot be adequately covered in just a few short videos。

 but I hope it will have provided enough of an overview to ensure that you are ready to troubleshoot D NS related issues with a sufficient understanding of the underlying infrastructure and beyond what most people know about name resolution。

That is， as with all the other topics in this series。

 we're shooting for just enough detail to let you know how much more there is to understand and hopefully we your appetite for more。

But let's go back to where we left off in our last video。 Remember。

 we went through the details of a complete host name look up from a DN S resolver。

 starting at the root name server， then hitting the G T L D name server。

 then the name server authoritative for the Yahoo dot com zone down to the delegated Y F1 dot Yahoo dot com zone。

We followed the packets for this book up because we wanted to avoid having to defer to magic steps in between。

And so we determined that we really needed to begin our query away at the top of the domain namespace。

 the root。But let's be honest。 we kind of cheated a bit here， didn't we， We said。

 let's ask the route。But we never specified just how we knew where to find the route。

 That is we did defer to an initial step of magic。Which seemed unfair。

So let's talk about the root of the domain name system。

We know that the root name servers have I addresses。

 that they really cannot be all that different from any other authoritative name server。 In the end。

 they are simply name services authoritative for a single zone。

 It just so happens that that zone is the root of the domain name space。

But if this is just another name server and the route is really just another regular zone。

 then we should be able to look up the name servers responsible for the root zone via the DNS。

And look at that。 That works。Here we see the dig tells us that when we look for N's records。

 we get back 13 answers。As well as an additional 27 records。

 the name server thinks might be useful to us。The answer section here shows the various route name service named a route service dot net through M dot route service dot net。

That is， we have 13 route name services in total。 Y 13。

Well it turns out that 13 Ns records fit neatly into a single 512 by UP packet。

 So having 13 name service means you only need to send a signal packet back。 Now， of course。

 nowadays， the additional information where including balloons the packet above the 512 bys。

 which is why you will find in your TCP done packet that the response was truncated and your resolver will try to query over TCP。

But， anyway。In addition to the NS replies， we also get the IP addresses of the name service。

 which of course， are all dual stack IPV4 and IPV6。So when we run our Dcom。

 it queed our local resolver for the root name server and as information。

And presumably the name server that perform an NSs query， just like we discussed in our last video。

 but that means that we have another chicken egg problem。

 If we want to ask the root server about the NS records for the root server。

 we need to know what the root servers are。And so it is indeed the case that every name server installation does require this information to be provided so as to be able to bootstrap itself。

And here。Under Etsy Na Db root。c is where we find that information on this particular system。

This file is part of the namey software distribution， Ie bind。But as it says here。

 it's also available from the internet via FTP from the Internetnic server。In other words。

 when you set up a new resolver， you need to somehow get this information。

 Now this information may be outdated。 So once you start your server。

 it will immediately look up the name server information for the route again itself and then cache that possibly overriding information from this file。

But here we have the NSA and Qua records for all the 13 route name servers。

Now let's compare to what we find on interne。And here we go。

We see that this file is current as of March 17th and looks pretty much identical to our copy。Now。

 this is no coincidence。 The root name server information doesn't change all that often。

 since as you can imagine， that could lead to a number of problems when the new name server installation comes up with no cache file。

 But either way， we are once again relying on copying around what amounts to a slightly more advanced hosts table。

 just like when we started out in the early days of the internet。

Funny more things change the more they stay the samehuh。

But let's get back to the fact that we have only 13 different route name servers。

That seems a bit fragile， doesn't it， I mean， sure there are some redundancy。

 But if 13 servers are the low bearing backbone of the DN S for the entire Internet then any sufficiently motivated adversary could try to take them down and bring the Internet to a standstill。

 I mean， dossing 13 servers really shouldn't take all that much， right。Fortunately。

 there are more than just 13 route name servers。 What we saw up until now is that there are 13 route name server authorities。

 the A route， the B route， et cetera all the way until the M route。

But each of these routes are comprised of dozens or hundreds of individual servers。

If you go to Roservice。org， itll show you a nice map of just how distributed the route authorities are。

For starters， the 13 routes are operated by 12 independent and international organizations so as to ensure that no single country has control over the domain name space。

Each of these authorities then distributed their service globally as shown here。

If we'd drill down into the US。You can see， for example， that。Right here in New York。

We have nine root server instances， the AC， D， E， F， and J routes respectively。

The footprint of the different routes is global， but not all routes have serviced in the same locations。

For example， up here in Nuke， there's only a K route operated by ripe。

With many more varied distribution again here in Europe。As you can tell。

 the different route servers are operated by different organizations。

 and each organization may deploy their respective route services in different locations。

Based on our earlier discussion around peering， it shouldn't come as a surprise to you that many of the route servers are co located in the central network hubs to ensure a physical vicinity and thus reduce round trip time for queries。

The Ero， for example。Is operated by NASA。And is co located all across the globe in over 160 locations。

The be rude。Is operated by the University of Southern California。

 but served from different peering points around the world as well。

Note that operating or one of the route service is not a business。

 It is provided by the route server operators by and large as of public service。

Even if operated by a commercial business such as Cogent， which runs the sea route。

The Fro is run by ISC。 And if you've been wondering just how exactly we are able to have our 1300 individual name servers。

 but only 13 IP addresses， while 26 with each having both an IPV 4 and IPV 6 address。

 then the answer is given right here。 The route server are all using any cast to allow multiple systems to offer the same IP address and to let the routing algorithms determine the closest one。

 generally as determined by number of hops。Now if each route has only two IP addresses but may reach any number of different servers。

 how do you know which one you end up talking to？Well， by and large， it doesn't really matter。

 but there are ways to find out。For example， the Fro operated by ISC offers a lookup like this。

If you ask Everroservice。net for the host name。binin text record using the chaososnet protocol。

 you get back a response it includes as the first label， a 3 data airport code。

Telling us that our F route is located at least somewhere near Dallaslles International Airport in D。

 C。Which makes some sense since our AWS instance here is in the US East region。

 which is served out of data centers in or near Ashburn。

 Virginia that is right next door to Dallases International。Now。

 this result here also illustrate something else that's useful to remember about the DNS。

 It is a distributed database， so can be used for other things beyond just I addresses。

as the use of the chaosnet protocol here shows， even in other contexts。

By using resource records of type text， for example。

 we can put any information into the DNS we want really。

We've already seen a number of different types of resource records。Such as， and as recordsers。

Which again， use the Internet or I N class of records。

Each resource record also has a time to live a TTL which describes for how long a caching Rer may catch the results for。

The Ns records for the root servers are long lived。Roughly five days。

Since they are not likely to change or frequently。But other records。

 especially those that may change more frequently， oftentimes have a shorter T T L。

 which you have to keep in mind when troubleshooting why you are getting different results from those that may be in the authoritative zone。

Another resource record。Is the S O A record for start of authority。

This record defines information about the zone。Includes the name of the primary master。

 the email address of the primary point of contact， the serial number。

 and refresh timeout for secondary name service， as well as a retry expire and TTL number。

Note that the authoritative domain name servers for a domain need not be under that domain。

 and in fact as we show here， some DNS service providers even distribute the name servers across multiple TLDs for redundancy in case one of those becomes unavailable。



![](img/8e4f8a276227d949dd78ca659bb250fc_1.png)

It is also worth noting that two domain names that look similar and that we associate with one another remain entirely distinct。

And can have completely different authorities。Stevenstech。edu is different from Stevens。edu。O。

What other Dionna's records do we have。Since the DNS， such a conveniently distributed database。

 people have found all sorts of uses for it。For example。There's CAA records。

 which provide information about which certificate authorities are allowed to issue certificates for the given domain。

We'll discuss this again when we talk about the HTPS ecosystem here we see that Yahoo only allows the G and global sign to issue certificates under Yahoo com。

Or you can put some humorous text into the DNS for your silly joke domain。

Or you can put your hosts as H key fingerprints into the DNS so that clients can verify who they're connecting to instead of simply accepting any host key mismat as just about every single person on the internet does。

But， of course， the most common I lookups。Remain the resolution of host name to IP address。

 as well as the other way around。But reversing the lookup going from I P address back to host name is somewhat interesting in that it uses different domain。

So let's take a look and go ahead and capture traffic once more。

The reverse lookup of an IP address uses the PTR resource record。

 and the result then looks like this。Note how the IP address was reversed and then looked up in the special ineter Aor domain。

But how would In E Apa know what Stevens decides to name its hosts。

Let's take a look at the packet in wire shark。As expected for any lookup。

 we begin at the route and ask， hey， who's responsible for ARPpa with the response pointing us to a routeserv do net。

Next， we asked that server Hey you， who's responsible for in E Dal Apa。

 and the response includes a list of name service called A in Eer service Do ARP， B in Eer service。

 ARPpa， and so on。But so far so good， not much different from the other lookups we've seen。Now。

 we get into the part where we used the reversed I P address and ask。Who is responsible for 1，5。

5 dot ineter dot Arpa， which tells us the name service run by Aaron is in charge。



![](img/8e4f8a276227d949dd78ca659bb250fc_3.png)

And perhaps this is where we realize that the reversed I addresses allow us to effectively include a who is lookup by net block because the 155/ 8 IP block was allocated to Aaron。

 It's Aaron that knows where to find answers for reverse names。So of course。

 we then ask Aaron for 246。155 in net airportport。Which then tells us it's Nre do Stevens Tech do Eduu。

 that knows more。This is because the 1，5，5，2，46 s 16 block was delegated to Stevens。

 As you remember from our earlier videos。 And so the 2，46。 1。

55 dot Inta Apa zone is also delegated to Stevens。 thereby allowing Stevens to add entries into that zone as they see fit。

So when we go up the reversed IP address by Ot。We eventually find our final PTR record。

Here with a response returned by Nrac。tevenstech。edu。

So reverse IP address lookups work almost the same as any other DNS lookup。

 but it requires the reversal of the address to allow for delegation of zone authority along the net block allocation lines neat。

But we still have one problem left。 So， yes， here we go again with a packet capture。

Let's assume we're looking up the IP address of www。 ena。 org。If we look at the packets we captured。

We， of course， see OadNs UDP port 53 traffic， sending our queries and the servers replying with the various responses。

But how do we know that these responses are authentic？This is simple plain UP。

 so any system in the middle could have sent us both with information， right。

Let's look at the results。 Dick returned to us once more。Note over here， it includes the AD flag。

 authenticated data。Somehow， the DNS server got assurance that the data is authentic。

 that it was not manipulated。How did it do that？Let's go again。We capture our DNS packets。

Fluush the cache to make sure we get the whole story and repeat the lookup。We can， then。

Load the PAP file into wirere shark once more and take yet another even closer look at the package we captured。

Here' is our initial query to the route name server about dot org。

 and the response includes not only the Ns records， but also down here， an R6 record。

 a resource record signature。This is a cryptographic signature asserting the integrity of the entire N record set。

If we look further down。We see that the other responses also contain RIig records。

As well as D S records。Delegation signer records used to identify the signing key of the zone。

The final result then。Also includes an R aic。 But， of course， now the question is。

 how do we verify the signature， We need to have a public key for this。How do we get the public key。

 Why the DN S is a distributed look up table。 Let's ask for it。

So here we see the lookup of type Diones key。Which should be in this response here。

But this response was truncated。 The information didn't fit into a single UDP packet。

So we need to try again using TCP。Here you see us asking again this time via a TCP。

And the response is then found over here。So now we can use this T N S key to verify the signature on the earlier results。

 But， of course， we want to have assurance that this record itself was signed using the parent key and so on and so on all the way up to the route。

This system of signing records by different zone keys is known as the domain name system Security extension。

 or DNsec。And as you can tell， we could discuss that topic by itself in several standalone videos。

But for today， let's stop and just summarize some of the important implications and considerations when dealing with the DNS。

For starters and that may be obvious， the DNS contains an incredible amount of critical information and is oftentimes used for all sorts of subtle decisions that assume its correctness in authenticity。

Unfortunately， the DNS does not provide any such guarantees。 Pla text。

 UDP or even TCP without any assurances means that all sorts of things can go wrong。To address this。

 DN St was developed， which we just saw in use。 but unfortunately， it's not widely deployed。

 There are comparatively few domains that use DNsec。

 In part because of practical deployment concerns。 in part to the precisely the importance of criticality of the DN S。

 If you mess up D Nsec， your entire domain faults off the Internet。 That's a pretty big risk。

 and we need to see more robust deployment practices here。Next。

 you may have heard a fair bit of talk about DNS of DLS or DNS over HtTPS in the last few months。

These address different problems or better threat models within the DNS system and are topics we could likewise cover in depth for hours。

For now， I hope that you will research them on your own applying what you've learned here。

Another aspect about the DNS is that it's everywhere and seldom restricted。

 This allows for all sorts of interesting abuse angles， such as data exfiltration via DNS lookups。

 for example。Misconfiguration of the D N S can lead to endless hours wasted。

 and troubleshooting can be tricky due to the nature of the D N S。

 allowing for delegation and different T T Ls on records。 As the saids。

 you will soon learn that if everything's all messed up and nothing makes sense。

 its probably the D N S。Or more likely， somebody thought they were clever and added something to Etsy hosts。

 which I never grow tired of recommending against。But as the DNS sits underneath so much of what we do on the internet。

 you need to remember that if I can control your DNS。

 I can likely do just about anything that otherwise would require very privileged access。

I think we mentioned that when we talked about dominium registrars in an earlier video。Now。

 given how important the DNS is， it's a service that is frequently outsourced to a third party provider。

But you want to keep in mind that every time you do that， you are giving up some control。

 if that provider gets compromised， you are compromised as well。On the other hand， however。

 it is not necessarily the case that you are in a better position to run such a critical service with sufficient redundancy yourself。

 and perhaps it is better to let the experts manage it for you。



![](img/8e4f8a276227d949dd78ca659bb250fc_5.png)

This is the pattern we see over and over when it comes to running services in house versus outsourcing them。

 there isn't the clear， simple， always correct answer。

What makes sense for one organization may not make sense for another。Okay。

 I think this brings us to an end of our discussion of the DN S。 As you can tell。

 it's a topic that lends itself from many a deep dive and can go into many different directions。

 but is critical to understand as without the DN S， nothing much works on the Internet。

So make sure you follow along with all the examples and get busy dissecting Pcaps and wire shark and by hand。

 explore the different domains and see what other interesting things you can find out just by observation。

Until the next time， thanks for watching。Yes释。