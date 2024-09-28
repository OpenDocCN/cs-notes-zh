# P140：p139 9-6 BGP Putting the Inter in Internet Professor Jennifer Rexford Princeton - 加加zero - BV1qotgeXE8D

 influence on the way that AT&T used and deployed BGP and routing in its network。

 And since she's been at Princeton， has done a lot of research in routing， inter-domain routing， BGP。

 and laid some of the groundwork for what we now， know as software-defined networking through her work on 40。

 So hi Jen， how you doing？ Yeah， about yourself。 So this is one of the interviews that we're doing for。

 the online class at Stanford called CS144 and Introduction to Computer Networks。

 And this is the first of the interviews that we're doing using Hangout。 So we're。

 going to see how this goes。 So excuse us if we get some of the technicalities a， little bit wrong。

 So I wanted to ask you a question to start with。 Can you give， us just a brief history of BGP。

 how it came about， what were the basic ideas， and， why it's lasted so long？ Right。

 so BGP is essentially the glue that， holds the disparate parts of the internet together。

 And so it grew up hand-in-hand， with the with the internet。

 So that when the ARPANET was was running in the， sort of in the 80s。

 there was really one core network， the ARPANET itself， and a。

 lot of other networks that connected to it。 And so there wasn't really a need for。

 a sophisticated inter-domain routing protocol。 The network was essentially a， tree。

 Once the NSF net was being commissioned， there is a need to support。

 much more flexible ways for networks to connect to one another。 And in particular。

 networks might connect to each other not only to the NSF net backbone。 And so it。

 became necessary to deal with loops because the topologies were now， potentially cyclic。

 And so BGP was designed to support routing on more， general topologies。

 And then over time it's really grown along with the internet to。

 have to grapple with a lot of issues dealing with scalability。 Running out of， address space。

 having a large number of address blocks that have to be carried， within within the protocol。

 And it's also grown as the business relationships。

 between domains and the services that providers want to offer to their， customers have evolved。

 And so now there's much more of a need years later to be。

 able to allow a service provider to pick one path that might be longer than。

 another because it might be economically advantageous。 Maybe it's cheaper， maybe it。

 has better performance despite being longer。 And similarly for providers to。

 offer services like virtual private networks that don't even connect to the， internet at all。

 And so we've seen over time BGP adapt in many ways to address， both of those kinds of concerns。

 So when you look at BGP now， what do you think， of its main good and bad attributes？

 What are its strengths and weaknesses？ So basically anything that makes the internet the internet。

 which is essentially， what BGP does， it sort of puts the internet in internet， has to reconcile the。

 competing and conflicting goals of the different service providers and other。

 parties that connect to the network。 So no matter what we do whether it's BGP or， something else。

 something has to actually reconcile that there is no global， agreement on what paths are good。

 Or even which paths should be made available， from one domain to another。

 And so in that sense BGP is solving a very difficult。

 problem and it is at least a viable solution to it and it's been remarkably。

 able to adapt over time to address exactly the security， scalability， concerns。

 the concerns about business relationships and even security。

 concerns that have arisen as you've tried to move the internet from a research， network。

 essentially a research experiment that escaped from the lab into。

 something that actually is a global commercial enterprise。 So that's all good。

 It has managed to weather the storm but it is hard to make scale。 It's complex to， configure。

 In fact the protocol itself is in some ways pretty simple。 You know I。

 advertise paths to my neighbors。 They add themselves to the beginning of the， path。

 They pick the path they like best and advertise it on with their neighbors。

 So it's pretty simple but all the action is in how BGP is configured。 And that's。

 one of the reasons BGP is hard to teach because if you look at the protocol spec。

 or even a text books about BGP it mainly just captures that hop-by-hop。

 path-based dissemination of routing information and says very little about。

 how configuration is done。 And so it's a pretty steep learning curve。 People make。

 mistakes and configuring BGP out of naivete and out of fairly low-level。

 broke configuration mechanisms in the routers。 And so we see lots of outages。

 just caused by operator error。 A really good example was the number of years ago。

 Pakistan Telecom was trying to block access to YouTube within Pakistan and。

 accidentally blocked it for the entire world by announcing that they were the。

 best way to reach YouTube and everybody on the internet believed it。 So BGP is。

 definitely vulnerable to these sort of butterfly effects where a small failure。

 or a small configuration mistake in one part of the internet can have these。

 pretty significant global consequences to the extent that people might not be。

 able to watch videos of cats flushing toilets for you know multiple hours at， a time。

 So from that point of view it wasn't really designed to be a robust。

 and secure protocol that one might want for a critical infrastructure like the， internet is become。

 So we always hear stories of， attackers being able to sort of surreptitiously advertise a route or there's。

 the potential for it through a BGP peering session and therefore be able。

 to subvert the routing that takes place。 Do you think that this happens a lot in。

 practice that this is a common way to attack the network？ So I think in practice。

 a lot of the bad guys on the internet actually want the internet to stay up。

 because what they're actually trying to do is either launch it an aisle of service。

 attack on a particular victim or to do a phishing attack and so I think in。

 general most of the bad guys don't want the don't want BGP to go down。 A second。

 reason it might not happen a lot is that adversaries often don't have access to a。

 BGP speaking router of their own to be able to manipulate or just don't have the。

 skill set to do it。 So I would certainly say it's not as prevalent as some of the。

 other forms of cyber attacks we see on the internet。 That said we see several times。

 a year a very high profile outages caused sometimes by operator error。

 sometimes in you know sometimes in ways where it may not be clear if it's。

 actually intentional or an accident so it's certainly a huge vulnerability and。

 when it does fail can have much more global consequences than an attack on a， single victim might。

 So I think it's still a big security concern but， arguably it's not as prevalent as some of the more targeted forms of attack we。

 see on end hosts。 Right so one of the one of the limitations that's often cited of。

 the way that the path factor is is transmitted or advertised to neighbors is。

 that of course when someone when a when a peer advertises a path to me I don't。

 know whether they're actually going to follow that path。 The second thing is。

 they're choosing amongst the many paths that they can advertise to me which one。

 which one they want to advertise to me and so there may be alternatives that I。

 would prefer that they don't even tell me about。 So is it the is this a big。

 limitation in practice or is this just the concern of the sort of the， academicians？

 I think it's somewhat of a concern in practice in that it may very。

 well be that the customer of an ISP would like to pick a path that avoids a。

 particular country that might do wiretapping or censorship is a really good。

 example where you may want to pick paths that avoid a particular intermediate。

 domain and are not able to do so because maybe all of your providers have。

 neglected to offer you such a path even though there might be one that exists。

 on the actual graph and there can also be cases because routing decisions aren't。

 based on on performance that there might be a path with really good。

 performance that's actually available on the graphic you don't see。 I mean a。

 really good example when the Middle East fiber cut happened in the Mediterranean。

 a number of years ago a lot of people started routing the other way around the。

 globe and I heard from this from a number of carriers where they know it。

 wasn't that there weren't routes available but because the routes they。

 happened to learn were much more restricted there were there also there。

 were forced to take traffic on a path the other way around the globe。

 sometimes with much higher latency。 I see。 So I do think that I do think those。

 things matter but I think it's quite fair that if you know if you have。

 multiple providers you may get one path from each of them and still get some of。

 that same path diversity that you might wish you could get from one provider。 Do。

 you think it's common for a path that's advertised to me to be then different。

 from the one that the the advertiser uses in practice in other words they。

 advertise one path to me like that path it fits with my local policy and then。

 they actually use a different one in practice。 Yeah that can certainly happen。

 and it can happen for legitimate reasons for example route aggregation where I。

 might be routing in a very coarse grain big address block and inside the。

 providers domain they've broken that into a much larger number of smaller。

 address blocks that have different paths so in some cases it might just。

 naturally happen because of the scalability mechanisms in the protocol and。

 you can certainly imagine less less benign reasons where that might happen。

 where a path might be advertised to me because I'll be more likely to pick it。

 and someone might be trying to attract my traffic into their network and and then。

 send the traffic on the path that's actually most financially advantageous， for them。

 It's a very nice research work showing that those kind of gaming。

 gaming mechanisms are possible and I think what's particularly interesting。

 about that intellectually is that even the best security extensions to BGP which。

 are not deployed at all today don't prevent that because they mainly secure。

 that the BGP messages themselves really did go through the sequence of。

 autonomous systems that are listed in the ASPAP but all bets are off when it。

 when you send the packets in the data plan there's really very little stopping a。

 domain from installing a different entry in a forwarding table that will send my。

 packets a completely different way so it makes it difficult to do something like。

 let's suppose a government says I only want my traffic to traverse networks that。

 are in my own country or I want to avoid another country even though BGP will let。

 you pick paths based on what autonomous systems are there if you really care to。

 make sure that property holds you may not really be able to count on BGP to give， that to you。

 So another often cited problem with BGP is the， rate that it converges after there's been a routing change and I know that you。

 were very involved in work a number of years ago in both uncovering the problem。

 and then looking for ways to looking ways to solve it。 Can you give us a brief sort。

 of overview of the problem how it was found and then how things stand today？

 Yeah definitely so that there are two issues with BGP and convergence one is。

 whether the system converges at all in other words is it possible that all of。

 these domains making their own local choices about which way they want to send。

 their traffic each continue to convince each other to change their minds about。

 which way to go and never reach a global agreement and the second is even if they。

 do reach global agreement how quickly does that happen and while that。

 transition is happening packets are being lost in flight put in loops。

 delivered out of order people have found that when Skype calls are disrupted or。

 perhaps Google Hangouts as well that it's most likely caused by this BGP。

 convergence behavior rather than by network congestion。 So both are issues do。

 you converge and if so how quickly。 So on the first question it is certainly。

 possible that I want to route through you you want to route through someone else。

 and they want to route through me and we each cause each other to change our。

 minds once I decide to route through you the third party no longer has available。

 the route they might have wanted through me and like mine as well and we continue。

 to chase our tales。 Now in practice that's that's thought not to happen very often。

 and the reason for that is that BGP is first and foremost the money routing。

 protocol not a packet routing protocol。 Routing of packets is kind of a nice。

 side effect and so when I pick a route as an AS I'm picking based on economic。

 factors do I have to pay to send traffic through you because you're my。

 provider do I get revenue from you when I send traffic through you because you're。

 my customer or is it sort of financially neutral because you're my peer。

 And so in the end these sort of protocol oscillations that are permanent。

 suggest some sort of weird financial dynamic taking place where everybody's。

 somehow making money in a cycle and it doesn't really make a lot of sense that。

 that everybody would somehow have it in their financial best interest to pick。

 routes that ultimately cycle back。 So I'm happy if we think this doesn't actually。

 happen and some of the work I was involved in tried to come up with a sort。

 of an economic model and proofs that under certain conditions it can't happen。

 Now that said we do sometimes when I was at AT&T see route oscillation within an。

 autonomous system because BGP is used there as well to disseminate routing。

 information within a domain。 So it's not that the problem never happens but it is。

 somewhat of a rare pathological problem rather than something that seems to happen， a lot。

 On the second question about how quickly do things converge a number of。

 years ago BGP would converge in the order of minutes or even several minutes。

 definitely quite long relative to sort of the 50 milliseconds or less target that a。

 lot of real-time applications need。 And part of that is that BGP keeps。

 exploring alternate paths one after another。 So if the path I'm using is。

 withdrawn from me I explore my next most preferred path which may in fact。

 share the same fate as the path I just lost。 They may have a link in common。 BGP。

 is just advertising the whole path it doesn't tell you any information about。

 shared resources that might affect many many paths and so one after the other I。

 explore them and my neighbors are doing the same and you can end up with sort of。

 an exponential iterative process of exploring those routes。 So that's gotten。

 better because the sort of timers that drive how quickly I can move from one。

 decision to the next have shrunk over the years and and frankly when we even a。

 number of years ago when we looked at this most of the BGP routes are remarkably， stable。

 Ten days or two weeks at a time there are a small number of unstable。

 destinations on the internet that go up and down quite a lot and that's thought。

 to be caused not by routing oscillation but by literally equipment going up or。

 down that might cause a destination to be reachable or unreachable back and forth。

 and in practice those destinations are extremely unpopular。 Now they're either。

 unpopular because you can't reach them in the first place that most traffic going。

 or they're popular and because they're unpopular nobody cares enough to make。

 sure that the network around them is stable but what that all means when you。

 put it together is that the vast majority on the traffic on the internet is going。

 over paths that are often stable for days or even a week or two at a time。 So in。

 some sense between a lot of research a lot of improvements in software and。

 routers and improvements in operational practices have meant that BGP。

 convergence while it still matters is nowhere near as messy a problem as it。

 might have seemed like 15 years ago。 Yeah okay。 One of the things you mentioned。

 earlier is that you know one of the things that makes it hard to teach BGP or。

 it makes it hard as a student to really understand what problem BGP is trying。

 to solve is in some ways it's not it doesn't feel like it's built on the same。

 principled algorithms that you know RIT was originally an OSPF as just a。

 collection of you know policy mechanisms and then path routing and so you know if。

 you look at BGP today is it is it a band-aid that's lived for a long time is。

 it something that you you believe and hope will be around as an into domain。

 routing protocol for a long time in the future or you know if you got if you got。

 the play God for a minute and you know wipe away BGP and replace it with with a。

 new into domain routing system what what would you do would you would you。

 replace it with something that's similar or quite different。 Oh that's a great。

 question so I've the BGP is the protocol I love to hate though in some sense it。

 has proven quite evolvable and it has changed dramatically over the years so a。

 Jakob rector and a talk you give a number of years ago called BGP the triple napkin。

 protocol for for the three napkins on which the protocol was described when it。

 was first designed and I would say it's now the kitchen sink protocol in that the。

 number of steps in its decision process the number of attributes passed around。

 the number of different kinds of things that can be addressed in BGP all of these。

 things have gotten more and more and more complicated and in part that's a a。

 success disaster right it's it's possible to do a lot of things with BGP。

 that were far beyond what it was originally designed to do and so it is a。

 testament to how evolvable it is that it has been evolving in this way but it。

 means that it's just so complicated and so difficult to configure and and also。

 very insecure because what it was originally designed there were no。

 mechanisms for signing and verifying of the routing information and no reliable。

 registries of which autonomous systems are allowed to originate information for。

 a particular address block and so now we're trying to put the cat back in the。

 bag if you will by putting a lot of that security infrastructure together and it's。

 actually quite difficult to do after the fact so in that sense BGP has kind of。

 evolved to a place where it's it's fairly unwieldy that said if you replace BGP you。

 still have to reconcile the fact that different domains have different。

 autonomy and have different priorities for how they want their traffic to be。

 handled so one thing that I'm really interested in along those lines is that。

 it seems weird to me that the economic relationships between domains plays out。

 at the time scale of individual packets or routing protocol messages that's a。

 pretty small time scale for economic concerns to play out and if you look at。

 what's happened in servers virtualization has made it possible to really。

 separate the owner of an infrastructure from the party that's actually running。

 an application on top of that in a virtual machine that might belong to a。

 tenant running on a server that might belong to a company like Google and。

 Microsoft or Amazon and so I'm intrigued by the idea that we can now virtualize。

 networks as well and you've obviously worked on that I have to it'd be nice if。

 I could instead have a virtual network that spans the equipment owned and managed。

 by multiple parties and then control my own fate on top of that virtual。

 topology so again the business relationships don't matter but it's between。

 me and the party whose infrastructure my virtual components are embedded in rather。

 than me and the neighbor I'm side-by-side with or worse yet domains many。

 hops away who have no accountability to me and no visibility to me so I think。

 we can make a routing system that is a lot more flexible and still cognizant of。

 the fact that their real autonomous revenue generating parties involved if。

 we took advantage of some of the innovations and virtualization over the。

 past decade so if someone's watching and they're thinking of going to grad school。

 interested in networking is into domain routing routing still an。

 interesting topic is it becoming an interesting topic it again what do you。

 think what would be your advice I think it's interesting still in two ways that。

 are perhaps different than it was 15 years ago I think one is is rethinking how。

 domains can relate to each other in a new economic reality taking a advantage of。

 virtualization taking advantage of the fact that large content providers are。

 very close to their customers we often one or two hops away making the network。

 in some ways much flatter than it was when BGP was designed so I think revisiting。

 how domains interconnect with one another with video and content distribution in。

 mind and with virtualization and software to find networking in mind I think is an。

 interesting opportunity and in general we found with in or anything interdomain。

 in the internet stinks that is very hard to deploy quality of service。

 security IPV 6 multi cast anything that like that inside the domain is。

 challenging enough but as soon as you need 50，000 parties to cooperate it becomes。

 almost impossible to affect principled change and so I think a lot of the more。

 interesting work on BGP these days is looking more at incremental deployment。

 incentives for an incremental deployment solutions where you get some security。

 gains scale guilt ability gain economic gain even if only a small subset of the。

 internet adopts a technology change and then hopefully it provides incentives for。

 others to take to take part so I think we've entered a domain where I'm。

 intended a domain where work on BGP may be more focused on how to evolve it in a。

 strategic way rather than what a clean slate design of BGP could look like。

 thank you very much Jen this has been really interesting right thank you， [BLANK_AUDIO]。

