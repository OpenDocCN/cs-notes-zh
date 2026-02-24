# UCB《互联网导论：架构与协议｜CS 168 Introduction to the Internet： Architecture and Protocols》 - P14：-13- Midterm Review.2022 - GPT中英字幕课程资源 - BV1VcrrYUEL5

![](img/bdc6f073bc8f7cd0a4d5d030f60ff103_0.png)

Okay。We're back， fingers crossed that this works。 midtime review。

 maybe we should go through it very quickly while we can。



![](img/bdc6f073bc8f7cd0a4d5d030f60ff103_2.png)

Jumping straight with all logistics。 Sha has had a number of posts on Ed so you can get all information about exam logistics there。

 The plan here is to cover the technical material that's on the midterm And so just a few get a few things out of the way coverage。

 What topics are we going to cover on the midterm。 everything we've covered in lecture so far。

 except last lectures discussion on reliability Okay so the acts timeouts， that's not on the midterm。

 Everything else is。In general， the test is only going to assume that you know the material we've covered in lecture。

So everything we've covered in lecture is fair game。 We're not covering。

 If we've not covered it in lecture or discussion section。

 then we're not going to cover it on the midterm。To the extent that you're using the textbook。

 use it to， you know， clify for extra information or to clify concepts for yourself。

But always treat what we've said in lecture as ground truth。

 So if there's something where the text differs from what we've said in lecture。

 what we've said in lecture is what you should assume for the midterm。Okay， in general。

 just rule of thumb for you to know there's nothing on the test that involves complicated math or very lengthy calculations。

 So if you find yourself going down that path， you're probably on the wrong track。

 so use that as a hint to yourself。

![](img/bdc6f073bc8f7cd0a4d5d030f60ff103_4.png)

Other general guidelines。It is。 you should understand you know how things work and the solutions and algorithms we've discussed in class。

 but also be prepared to kind of copy and apply them to context that we may not have covered in class。

 So， for example， we might say， consider an A that is not following gox with policies for BGP。

 How would such and such work。 You should be expecting to do that。

 or we could be taking a solution we've discussed in class and applying it in a scenario or context that you haven't seen before。

 So like here's a very strange topology。 you get this particular sequence of failures。

 What would happen to distance vector， something like that。In general。

 we are not testing your ability to memorize stuff we've covered。

 We're testing whether you've understood how things work。 So again。

 use that know as a mental picture for if you feel like we're testing how many bits were in the I header that was probably not the goal of the question。

 So use that to check whether you're on track。In general， if you see something that looks unexpected。

 don't let this taunt you。 You have learned all the pieces。

 the building blocks you need to reason through a problem。

So in terms of format I believe we've released a number of midterms from the prior year。

 so I hope you have a pretty good sense of what the style of the exam is we're kind of following the same style so you can expect a set of about 25 quick questions they vary in level of difficulty and then we have a set of these deep dive questions on specific topics。

So pace yourself accordingly， often not always， questions would tend to get harder as you work your way down towards the end of a question。

 so if you find that you're getting stuck on something， maybe move on， come back to it later。

 don't spend all of your time on that last question in the quick question set。嗯。

What else attitudeitude， don't panic if you don't know something。

 we aren't expecting anyone to get 100%。 None of us did。 None of the days。 I got a few wrong myself。

 So， and this is despite having done this many times， so。

Just know that that's kind of the expectation。 Don't panic if there's one question you aren't getting。

 You' probably doingt just fine。 Again， be confident that you have learned all the things you need to know in lecture in order to solve a problem。

 So there is nothing in a problem that should require you to know something that was not covered in lecture。

Stay calm， as always， you can reason through it。 I have no doubt。

 So this gives you and what is the plan。 You know， we're going to try and walk through。

One half a semester is worth of material。 And so clearly。

 I'm not going to do a deep dive on any particular thing。

 What I am going to do is walk through all the topics， the concepts as well as the details。

 highlighting what it is。 I expect you to know for the me。As always。

 just because I didn't cover it in this review does not mean that you don't have to know it。

 but if I did cover it in this review， you probably definitely should know it for the midterm I think of the way you should use this review is kind of as a checklist you know it's maybe a half an hour to go through so when you go through it use it as a checklist of oh you know I was supposed to know this do I know it Yes or no go check if you don't know it and come back to it That's at least how I find these。

Mtga used to be somewhat useful。My plan for today's lecture is I'm going to summarize。

 I'm going to walk through the concepts， just highlighting what you need to know I'm not going to explain。

 but I also have probably if I just keep talking to myself。

 I have maybe 45 minutes at most one hour worth of material。

 So I am expecting you stop me any time you want to go into more detail on something repeating a concept repeating the point I just stated。

Why did you say that Any questions you have stop me and we can go into it。

Without any questions on midtms before we get started？All right， so let's。Going very bottom up。

 we started this class with talking about links right what you should know about links are the important properties of links。

 the bandwidth of a link， the propagation delay of a link。

 this notion of the bandwidth delay product of a link and what it represents the capacity of the link。

 And from those， you should be able to calculate how long it takes for packets to get delivered or for data to get delivered from one point to another。

 you should know the components of that delay， transmission delay。

 time to get bits on the wire propagation delay， which is the time it takes to travel across the wire。

 as well as queuing delay and why we encounter queuing delay。Okay， you should also just be， you know。

 without doing calculations， be comfortable with ideas like， oh， I give you more bandwidth。

 What happens to your delay， or I give you a longer link。 that is higher propagation delay。

 What happens to your transfer time， What happens to application performance。 Okay。

 so just be intuitively comfortable with these properties of a link。

From links we went to Voers and we said that Voers interconnect links or you can start to build this topology and for the first few lectures we you know talked about Voers as this fairly black box concept。

 but then more recently we jumped into actually what a Voer looks like internally and in Rob's lecture we went into great detail on the internals of this。



![](img/bdc6f073bc8f7cd0a4d5d030f60ff103_6.png)

This is also， as you review one of the things I like about networking。

 it's also both the challenge of networking is you kind of have to keep all the pieces in your head。

Many other subjects， when you go study them， you learn algorithm A， and then you forget all about it。

 and you can go learn algorithm B， and the two have nothing to do with each other。

That's not the case for networking。 Networking is more where you learn these pieces。

 but they're all going to fit together almost like a puzzle， which is kind of fun。

 So test yourself on whether you understand how these pieces fit。 So， for example。

 if I took this I routeer， you reset said the I routeer forwards packets from an input port to an output port。

You should now know what does that mean forwarding a packet， So packet comes in。

 It has a header and a payload。You also now know what that header looks like， right So you can see。

 what happens on this line card。I have to be able to pass the packet。

 So remember all those version bits in the I P header。 Then you can say I have to dec a T， T L。

then you can ask yourself， you know， why do we have a TT or we have a T because of loops。

Why do we have loops， Because roing is is distributed asynchronous process by which we compute forwarding tables。

 And so sometimes we can have loops while things are converging。 That's why we have a detail。 Okay。

 so you get that。 Then you update the checkum。 Why do we have a check some。Check that。 you know that。

After you've done the TTL and check some calculation， what do you do next， You do an IP lookup。

What do you do the I look up on on the destination I address。How do you do it。

 You do it with longest prefix match。 Why do you need longest prefix match。

 Because we are aggregating IP P addresses。 Why are we aggregating them for scalability reasons。

And so once you have that lookup， then you forward your packet out the outgoing port。

Where did that forwarding table come from， That's where the control processor in this picture comes in。

 right， That's where we areing， running all of these routing algorithms。

That tells you now that control plane processor。 That's the control plane of this routeer。

 Everything else we talked about is the data plane。

So you should be able to understand the big picture， things like control plane data plane。

 and could you sit down to how these individual pieces are actually working。

 So things you should know about about us。 well processor versus line cardss。

 what's getting done at each， This notion of a control plane versus a data plane。

 The notion of a fast path versus a slow path and what gets processed where。



![](img/bdc6f073bc8f7cd0a4d5d030f60ff103_8.png)

And in general， know that the biggest challenge and when we talk about routeers is that on this data plane。

 we need really， really high performance。 Okay so things like options， things like fragmentation。

 they're stressful to the data plane。Going on without apology。 So we had links and routers。

 Ultimately， we said the reason we have all of this is to connect and ho。

And hosts where we run applications and host one to communicate with each other。

 We went from there to saying that a fundamental challenge in networking is this question of how we do routing。

 We then spent many lectures of these lectures on how the basic kind of fundamentals and concepts and routing and how routing is implemented。

Okay， so we talked about this notion of valid routing state。

 You should be very comfortable with what that means， no dead ends。

 no loops for any given destination。Then we moved on to this notion of， okay。

 we have valid routing state。 But what does it mean to pick good parts？

 And so we went into this question of link costs and computing least cost parts。

So this is starting to optimize for some notion of cost metric。

We talked about what those cost metrics might be。 if we tell you nothing。

 then assume the cost metric is one， but otherwise。

 typically cost metrics are things like the latency of the link。

 So you're optimizing for something like latency。You should know that sometimes we achieve forwarding through these things other ways like default routes and static routes。

AndSo static route was when a route network operator goes in and manually configures a route that says for this destination。

 go out this port。 Why do they do that， Because， for example。

 you need to know where your destination host is connected to the router。

 And we said destinations don't participate in routing。

 So how does a routerer know where the destination is， because we put in a static route。

Default route is very convenient if the only certain routeer has only one link or network has only one link to the rest of the network。

 then a default route is very convenient。 It says anything that's left over go out that link。这。

Convenient summarization。 In all other cases， we' run this routing algorithm or this gruting protocol。

Any questions？Yep。Yes。

![](img/bdc6f073bc8f7cd0a4d5d030f60ff103_10.png)

Yeah， what was the fast path versus the slow path， This entire path on the routeto where data packets come in。

 they get quickly processed and sent out。The output port， we call that the fast part。

 This is usually implemented in hardware。 and we'll do a very fixed set of functions like， you know。

 pass the packet， updateate the T Tl， check some， do the IP lookup， sendend it out。

 This is all built in hardware。 Hard is very good at going very fast for very simple and limited set of functions。

If you needed to do anything fancier to the packet。

 you would bump it up to the control plane processor where you might process the packet for things like options。

 or you need to look more closely at the packet。 That's one distinction between。

From a performance standpoint， fast bath and slow bath。Typically。

 we implement the data plane or forwarding data packets on the fast path because we get lots of data packets。

We implement routing algorithms and the routing protocols。 So B， GP distance vector Li state。

 those run on the control processor。Because we aren't sending that many routing updates and control pill packets and actually running a B TP computation or distance vector is more complex。

Okay， so there's control plane versus data plane。And this fast part versus slow part。

The slow path typically runs on the control processor。 This gets confusing sometimes for people。

Anyone want me to repeat that？

![](img/bdc6f073bc8f7cd0a4d5d030f60ff103_12.png)

嗯。嗯。没被上。So routing algorithms within a domain。 So we first started with， you know， this fairly。

 I would say， simple view of graphs and how you compute routes over graphs。

 And we talked about three different approaches to routing。

 What distance vector link state and spanning tree protocol。 You should be very。

 very familiar with how each of these work。 down to the details of you know， how what。

Updates get sent， how forwarding entries get computed and so on。You should also。

 to the level that you can apply them in different toppologies and different scenarios。

 all three of them。

![](img/bdc6f073bc8f7cd0a4d5d030f60ff103_14.png)

So let's walk through each one at a time。 So distance vector a distributed asynchronous protocol where every router is independently running this distance vector computation。

 The basic idea is that a router I as a router。 I'm going to tell all my neighbors about my least cost distance to every destination。

And then likewise， I listen to what my neighbors tell me and for every destination。

 I pick the least cost path。And then I remember the next hope or the neighbor。

On my way to that destination， along that least cost path。

You should know the components of this solution in detail where we advertise gos。

 the logic or the rules for when you update your gos。

 so if you remember Murphy said if you hear about a destination you've not heard about before。

 put it in your table， if you hear a lower cost distance for a destination than what you currently have in your table。

 then update your entry。Or if you hear from your current next hop with a change in the distance。

 then always accept it because that next hop knows best。

We also talked about periodic process triggered updates。

 And then we talked about this challenge of convergence， which is when things change。

 Routing is very simple when there's nothing changing in the network。 If you have links go up down。

 link costs that change destinations that arise arise， then everyone has to recompute。

And while you're recomputing， youre in this state where you haven't converged。

 So until you come back and you converge to your least cost parts。

 we call that period of time convergence。

![](img/bdc6f073bc8f7cd0a4d5d030f60ff103_16.png)

So you should understand all the things that can happen when things go wrong when gouters fail。

 linksnk fail。 advertisements are dropped， how this can lead to the counting to infinity problem。

RightAnd why we have this max on how far up you can count。But also understand how。

 what determines that convergence time， how we have T TL values and how we have these advertisement rules that can affect your convergence time。

 either make it long or make it short。 So if we had nothing but the simple baseline distance vector。

 then the time it takes you to converge is largely dictated by how frequently you send out updates that periodic advertisement interval and your T TL。

 which is how long you hold on。To work out when you've stopped hearing advertisements。Okay。

And so we talked about these three different rules or ways by which you can reduce your convergence time and avoid loops that happen when things change。

 Split Hon was this notion of if you are my next hop。

 I'm not going to tell you about my path to the destinations for which you are my next hop。

 This makes sense， right intuitively， if I'm going through you why would I try and advertise that route back to you。

 It's like asking for a loop。Poison rivers takes that further and says。

 instead of not telling your neighbor， just tell your neighbor you have a cost of infinity。

 And there's a very particular scenario in which poison rivers helps actually reduce that convergence time。

 And mu you walked through it。 Alex repeated it again。 walk through that again。

 make sure you're understanding it。And then poisoning a route is this other way of actually reducing convergence time where when your route goes away。

 you immediately tell your neighbors I have a cost of infinity。

And Mufi had this very nice example where you can see how that very。



![](img/bdc6f073bc8f7cd0a4d5d030f60ff103_18.png)

Quickly reduces your convergencestein。 So to make sure you're following all of those。

 I think what's a very helpful way pick a few apologies。 I tend to like these two， but you know。

 pick something more complicated。 walk through scenarios where if you fail failed this link。

 what would happen， if you had split her eyes in poison rivers or poisoning。

 if you change the link cost， what would happen。 if the destination went away， what would happen。

And again， I'd highly encourage you go back through Alex's notes and presentations on how these different optimizations combine。



![](img/bdc6f073bc8f7cd0a4d5d030f60ff103_20.png)

Any questions on distance like that？So links state like a different approach， again。

 a seemingly simple approach， the idea here， kind of the flip， the inverse of distance vector。

 the idea is every router is going to get the state of all links and all destinations in the entire network。

And then it's going to use that global information of that map to build this full graph of the network and compute least cost parts over that graph。

And then every router is going to just store the next hop for every destination in its forwarding table。

OkaySo I have the full topology。 I compute the entire path， and then I just stole my next hop。Again。

 it's simple conceptually， but things you should be aware of here is how does flooding work in L state？

So remember， if you go back to Murphy's lectures， we can if you just flooded naively where you say when I get a packet。

 I'm gonna to send it to all my neighbors other than the one I received it on。

 you can have this exponential growth in the number of messages that are going around。

 And so Li state was doing this thing where it's remembering the highest sequence number。 So it says。

 have I seen this message before。 And if not， then I flooded。 otherwise I suppress it。

 And that's how flooding is reasonable for Li state。Also， problems， you can have during convergence。

 It's easy to underestimate them with link state， but you still do have problems during convergence。



![](img/bdc6f073bc8f7cd0a4d5d030f60ff103_22.png)

And then in addition to knowing exactly how distance vector exactly how Li state works。

 be comfortable with how they differ at a high level as an approach。

 so distance vector is a global computation where everyone's computing parts in a distributed fashion across the entire network。

 but you're doing it using local data， based on what your neighbors told you。

 Li state is almost the inverse where every route is locally computing the parts。

But it's doing that using global information about the entire network that its collected。



![](img/bdc6f073bc8f7cd0a4d5d030f60ff103_24.png)

And finally， last approach was learning switches and STP。Why did we want this。

 Remember in all the IP routing distance back Li state， we said your host。

 the location of your destinations was kind of statically put in at routers。

 So routers knew where destinations were。 But what if you have this kind of plug and play network where you can take a host and move it from one place to another。

 if you didn't have those statically enter routes。 So then learning switches an SP is a very elegant way of doing this。

 The basic idea is that you're going to learn routes from watching where data packets come from。

 So when host a tries to send a packet to B。The router that receives it says， aha。

 I now know where it is， and you can learn accordingly from where data packets come from。

If you don't have a go， you're going to flood。And the way STP does flooding is different from Li state instead of doing what L state did。

In STP flooding works by first building this loop we topology。

And so we do that using the STP protocol。 You should understand why with learning switches。

 we have a different approach to flooding。Anyone remember。How。

 how is L state making flooding scalable。要。Yeah， so Li state had sequence numbers， and it said。

 have I received this link state update before。It could do that because it was actually storing that link state update。

So it had some local state to compare to and say， yes， I have it。 Oh no， I don't。

 And it could store those link state updates because it's controlled state。

 and there's not that much of it。 So it's fine。 And it was going to store that state in any case。

With learning switches and STP， we are talking about flooding data packets。

 So there's no way a switch or routeer can store all the data packets it's seen and say， aha。

 I've seen this data packet before。So we need a different approach。

 And that approach is to build this spanning tree。So be comfortable with why you need a spanning tree。

How it's used in learning switches。 It's used。For how we flood data packets。

And then also know how we actually build STP， which is building the spanning tree is very similar to how we did distance vector with one major change。

 which is that we are simultaneously learning what the root of your spanning tree is as well as your path to that route。

So remember， S TP was， we have one spanning tree。That's rooted at a particular route that gets picked based on the Id。

And so when we flood packets， we only flooded over this loopy spanning tree。

now the pros and cons of SP versus something like distance vector and Li state。

 SP and learning switches have this nice plug and play property for destinations。 On the other hand。

 this entire idea of just disabling a certain number of links is not the most efficient way to be using your links in your bandwidth in the network。

Which is why learning switches and SDP are typically used in fairly small networks。



![](img/bdc6f073bc8f7cd0a4d5d030f60ff103_26.png)

Any questions on。Intra domain routing or those click gouting。Okay。So where are we。

 we went from links to routeers to topologies to how we actually route over those topologies。

 At this point， we have all the components we need to start thinking about domains and interdomain routing。

 This is a picture from one of Murphy's lectures where we said that routing within a domain by which I mean the routing used to reach a destination within a domain。



![](img/bdc6f073bc8f7cd0a4d5d030f60ff103_28.png)

Is what we call an IGP routing protocol or interior gateway protocol and distance vector link data are examples of IGP protocols。

But we also need some solution by which we learn about routes to destinations， not in my domain。

 destinations， somewhere routes。 And that was the inter domainoma routing problem。

 And our canonical protocol there is BGPO， the border Gateway protocol。

 and the Interdoomain routing problem。 This is referred as EGPO exterior gateway protocol。Yes。

 so BGP is an example of an exterior gateway protocol or an EGP。

 list link state and distance vector examples of your interior gateway protocols or IGP。So again。

 intra domainin is to reach destinations within your domain。

 In domain is so that a routeer within one domain knows how to reach destinations that are in a different domain。



![](img/bdc6f073bc8f7cd0a4d5d030f60ff103_30.png)

And so what was a domain， we said it was a network under administrative control。

 you should be very comfortable with what ASs are， this notion that you have an AS number。

 understand the types of ASs， so we said you can have transit versus sub ASs depending on whether you're carrying traffic across your AS on behalf of a source and destination not in your AS versus all you just have destinations that are within your AS that was a stub。



![](img/bdc6f073bc8f7cd0a4d5d030f60ff103_32.png)

Tier 1 transit providers， These were the top， typically the back global As。

 They're all connected with each other。 They all peer with each other。 They have no provider。

You have to be really， really deeply understand the business relationships between A Ss and their implications。

 This notion of customer provider relationships or peer to peer relationships。

 the fact that customers pay providers and peers do not pay each other。

When we talked about inter domainomain gouting， we said our challenges are very different from what we discussed in intra domainomain gouting through scalability and policy。



![](img/bdc6f073bc8f7cd0a4d5d030f60ff103_34.png)

And scalability， we said that we achieve scalability largely through hierarchical addressing。

And we had this example。 I'll come back to it。 But hiarchicular dressing was， you know。



![](img/bdc6f073bc8f7cd0a4d5d030f60ff103_36.png)

Internalize that IB addresses are hierarchical。 They' hierarchical at multiple levels in the structure。

 the fact that you have network prefix with a host suffix。

They' are hierarchical in how they are allocated， so we have this organization I can that will give a large prefix to regional registries that will hand out smaller prefixes to it someone like AT&T that will hand out even smaller prefixes。

To a customer a S like Berkeley。And then those prefixes are assigned to different domains。

 and inter domainomain routing works on prefixes。So an entry in your forwarding table that you compute from your inter domainoma routing。

 that's a prefix。

![](img/bdc6f073bc8f7cd0a4d5d030f60ff103_38.png)

And then finally， we said that those prefixes can be aggregated。So this further helps scalability。

 but within limit that if we have things like multihoming in this example here。

 you can see where you had multihoming required Verizon to have two entries。

Rather than just one going to AT&D。Any questions on？I'd be addressing。Autonommous systems。

 how they are set up。

![](img/bdc6f073bc8f7cd0a4d5d030f60ff103_40.png)

So moving on with Ip addresses， we said， because we have this。Cidder。

 and we have this IP address aggregation。 This gives us scalability。

 but it complicates the IP lookup process。 The IP lookup process is now not an exact match on your destination address。

 Instead， it's the longest prefix match。 Okay， so understand longest prefix match and why this destination address matched the fourth and not the third。

Because we are doing longest prefix， not。Maximizing the number of bits that match。



![](img/bdc6f073bc8f7cd0a4d5d030f60ff103_42.png)

We also talked about how you implement longest prefix match。 So you should be。

Comfortable with how this is actually done。 We're not。 you know。

 we could have taken an IP address and matched it against all the prefixes in our tables。

 I would have been slow。 So instead， we built this kind of prefix tree and we have this algorithm where you walk down the prefix tree to find the longest prefix match。

And when you find the longest prefix match， then you find the next hot port that you're going to send the packet out on。

So again， taking stock， what we now know if you wanted to have an AS， you would go is what is an AS。

 a portion of a network that's under a single administrative control to be an AS。

 you go out and get an AS number from ICN， you then set up your ASS level topology by either being a customer provider peer to other ASs。

 you obtain a prefix which represents all the hosts within that AS and now the last part in the interdomain picture that we have to think about is how do we actually establish routes between those prefixes。



![](img/bdc6f073bc8f7cd0a4d5d030f60ff103_44.png)

![](img/bdc6f073bc8f7cd0a4d5d030f60ff103_45.png)

The big challenge here was policy。We talked at length about what we mean by policy and what are typical policies。

 The challenge with policies is that an AS is going to want to pick parts based on policy。

It has its preferences for how it wants to get to a destination prefix。

But it has we have to allow an AS to implement those policies while preserving autonomy and privacy。

 AS should be able to implement whatever policy it wants and should not have to reveal its topology or its policies。

 at least not explicitly to other ASs。We said in principle you could do whatever crazy policy you want。

 but in practice the typical policies have to do with these business relationships and how money is exchanged and so we had this intuitive notion of routing follows the money。



![](img/bdc6f073bc8f7cd0a4d5d030f60ff103_47.png)

We then talked at length about how you would actually implement this policy routing。

 and we said that in interdoomain routing or BTP， the way policy is implemented lies in how you these rules around how you export routes and how you select routes or import routes to a prefix。

 So the setup was very much like distance vector， but now its A is exchanging prefixes and their path。

To different prefixes。But we said there are four big differences relative to distance vector。

 I want to see if I can actually remember them。 One is that you actually advertise the entire path vector。

 not the just not just the least cost。 The other was that you actually you can aggregate prefixes as you go。

 The third is that you don't have to export。 or you don't have to advertise a route to every possible prefix。

 And the last one was， I forget。I believe it in the lecture notes。

 I believes that it's not necessarily the highest performance part that which you pick are not just the least cost。

Decision is actually based on policy。Okay， so where does policy get implemented。

 It gets implemented in your choice of which。Loouts yourre importing and which ones you're exporting。

Okay，And this is where Gug expertford is actually implemented is in this important export policy。

 And so again， what was important export。 So import is when somebody advertises a route to me。



![](img/bdc6f073bc8f7cd0a4d5d030f60ff103_49.png)

Do I， which one do I actually select。And in selecting a go determines how I'm going to send traffic to that destination。

And we said in selecting， you will always prefer customer over a peer over a provider。

This was to make money， otherwise save it and only pay if you have to。

Exporting a route had to do with how your decision about whether you advertise a prefix or a path to your other neighbors。

 So when you advertise it， what that means is they will send you traffic to Kay to that destination。

 So it's the decision about am I willing to carry that traffic。

And so we said this is the export rules。 If that path gets prefix gets advertised by a customer。

 I'm going to export it to everyone because I'm happy to send traffic to that customer。

 If it's advertised to me by a pure provider， I'm only going to export it to my customer。Again。

 because my customer will pay me whereas the pure provider want。You should be very。

 very comfortable with the C expert rules， comfortable all the way from， you know， why we have them。

That this notion of how money gets exchanged， how they get implemented in the form of these export and import policies and actually how they get exchanged when we get to how BGP actually gets implemented。

Yeah。Right， so， and that was when we got to attributes and how you actually do attributes， right。Oh。

 so we have， for example， the local preference。 I'm getting to that in a minute， but okay。

 let's jump hold on to that for a second and we'll get to it when I put that up。

 So how is BT P implemented， So you should understand the whole of B versus interior routeers。



![](img/bdc6f073bc8f7cd0a4d5d030f60ff103_51.png)

And you should also understand the goal of E BGP versus IBGP versus IGP。

So we have this picture that looked like this where we had border routeers or routers at connect。

To a routeer in a different A。 In routers， All their neighbors are within the same a S。

And we said border routeers will have these E BGP sessions with routers in other domains。

 and they will also have IBGP sessions with routers， interior routers and all routeers within N A S。

Many people get confused between IBGP and IGP because we think when we look at the picture。

 an interior router is routing is gunning an IGP protocol。

 it's also gunning or participating in this IBGP session。

 important to remember they're doing very different things。 The IGP protocol。

 This is the intra domainoma protocol is establishing connectivity between all。

Voutters and hosts within that A。The IBGP session is how an interior router knows how to reach destinations in a different domain。

Yeah。It uses IGP。 So it's actually running TCP on top of。 You mean for the IGP sessions， right。Yes。

Yeah。Any other questions on this picture？Any prefix。

 this is where the import and export policy and maybe this is also the earlier question。

 So if you take the black router there， it's receiving advertisements from some other ears for any prefix that that A is willing to carry traffic for。

And then likewise， if I take what prefixes that about is advertising to the other A S。

 when I advertise a prefix， I'm telling that A S I'm willing to carry traffic to this destination。



![](img/bdc6f073bc8f7cd0a4d5d030f60ff103_53.png)

So how， how do we actually do this？ Remember that route advertisements look like prefixes and attributes。

Basically pre fixes was。What we just discussed is the destination prefixes。

 But we talked about four types of attributes that influence your route selection。

 One was the A S path。The other one was met and IGP。 so going back to policies。

 high level policies always want to make or save money as per the Gg expert rules。

Once we're good with that， then what we do is try to select the best performing path。

 which is where A S path comes in。 You pick the shortest A S path。

 And then when you're done with that， you try to optimize for your use of bandwidth。

 And that was the little dance between meed and IGB。

Which determines whether your traffic leaves how far through your network， your traffic is carried。

 So going back， I think to your question now about how do I actually implement。The Ga experts。

 one way is in local preference， that attribute， because I assign a local preference to a particular neighbor。

And that tells me whether I like routes coming from that neighbor or not when I propagate that route。

Yes。So there you have a policy that decides， do I advertise this， Is this a customer go amount。

Even local pre is hard coded， in some sense。an operator goes in and configures that all routes coming in on this link have a local preference of this value。

 And if you look through the example we had with。Some 3 and00 that those were manually configured by your operator。

Any other questions on？So things you should， you should know how BGP works both at the high level。

 this money follows。Vouting follows money notion and the Gg expert rules。

 You should be able to apply to different kinds of BGP toppologies。

 You should also know how BGP actually implements all of this and how attributes like meed and IGP and ASPA and all interact。

You should have at least at a high level some sense of BGP's limitations and security issues not expecting you to know this in any great detail。

 but just have a sense of， you know， for example， BGP may not take a part that is the most optimal in terms of part length because it's prioritizing policy over performance so at that level you should have a sense of BGP's limitations。

Any questions here before we move on？

![](img/bdc6f073bc8f7cd0a4d5d030f60ff103_55.png)

Okay， so where are we， we went kind of bottom up。 We went from links to goers topologies。

 intra domainomain gouting， intra domainomain gouting， which has a very different set of concerns。

 It has to do without the administrative setup of the Internet and how addressing is done。

And so at this point， we actually have all the pieces we need for any to host on the Internet to communicate。

 Okay so you should be able to take a picture like this and step through， you know。

 where did NYU get its address from， How did NYU learn about Berkeley's address。

How what are the guys in an AT and T X3 exchanging in terms of VGP clouds。

 What protocols are running at different points。What does a packet header look like when the link cross Ver to A& T。

 Does it look different going from on the link between A0& T and Berkeley。The answer is no。

's kind of a trick question。 You update the I header。

 but it's the same IP header being carried through。

You should also understand which protocols are running on different links， where E BGP is running。

 where IBGP is running， where IGP is running and so on。Any questions？So we move on。行。Right。

 so and we haven't covered Ethernet。 So， you know we've covered learning switches and STP。

 You should know how learning switch and STP works。

 Learning switches and STP are usually applied in ethernet networks， which are an L2 network。

 We haven't covered Ethernet。 So we're not going to expect you to know Ethernet on the exam。

That's it。 What is an L2 network versus L 3， It's really whether you're routing on Ip addresses versus some kind of lower level L2。

Address。That's the entire difference。 And when you cross from， So typically。

 an L2 network would be a particular technology like Ethernet。

And it would have its own technology specific way of doing routing。

And it does have the ability if you have a multih network or graph that is made up of that same L2。

Technology， so typically， the example is ethernet。 You should Ethernet at L2 should be able to carry the packet from one end to another off that local network。

Yeah。In fact， Ethernet pretty much is the only one that uses it。Yeah， you。

 you should know how SDP works at the algorithmic level and how learning switches and enable plug and play and how that works without worrying too much about the context in which it's being placed。

 But you should know the tradeoffs like STP floods So you know。Ignore certain links。

 And you can know that without knowing anything about Internet， so。That do什么。Any other questions。



![](img/bdc6f073bc8f7cd0a4d5d030f60ff103_57.png)

Okay， so backing up now， we've gone kind of very bottom up。做。

Figure out how we've reviewed how all the plumbing works。 Let's go now again top down。

 and you know we've talked about how what gets implemented and how it gets implemented。

 We should not lose sight about why things were done a certain way And we spent a lot of time on this in the first few lectures of this class come back to it after you've now understood how things work。

 So going way back to lecture number one。 we said the goal of the Internet was to allow host to communicate across multiple networks。

 You now know how host commicative across multiple networks。 You know about Bgp。

 you know money gets exchanged。 You know about how addresses get configured about where a network operator goes to get addresses。

 You know all of that。 But come back to you know what was some of the underlying design decisions and why did we like them and make sure that you understand that now in the context of understanding how these different protocols work。

So going back all the way to the very first lectures。

 we said that the internet reflects certain fundamental design choices on why it's built this particular way。

 and you should know those and you should be able to appreciate them。

 So there were three main ones I want to highlight the decision to have a best effort service model that was this idea that I'm going to send a packet and I kind of hope it gets delivered。



![](img/bdc6f073bc8f7cd0a4d5d030f60ff103_59.png)

And we said even before that that inherently a network is a shared resource。

 All of us as users are sharing the bandwidth and capacity of that network。

And we said that there two cannot That was the notion of statistical multiplexing。

 So be comfortable with what is。Statistical multiplexing and why we use it。

 It's much more efficient than have giving， you know。

 every user dedicated slice of the Internet would have never scaled and been hugely expensive。

 So we like statistical multiplexing， and we like sharing。

We talked about two canonical approaches to sharing。

 One was this notion of reservation that a user and end hostst is going to explicitly reserve some bandwidth along a path for some durationation of time。

And as opposed to a best effort where I just send my packet。 and I hope it gets through。

And we talked about two canonical designs for implementing each of these。

 One was reservations implemented by this thing we said was circuit switching and then of course best effort was packet switching and after those first few lectures we've only talked about packet switching because that is what the internet does but you should remember this notion of reservations and the tradeoff relative to best effort and also at a high level the implications for implementing reservations in the way that circuit switching did so remember this was you know an end hostst when you want to reserve bandwidth you set up a circuit by saying sending this control message through the network saying I'd like to reserve some bandwidth。

And then you get an acknowledgement saying， you're good。 I've reserved some bandwidth。

 and then you can send traffic。Over that circuit until you're done with it。

 at which point you tag it down。

![](img/bdc6f073bc8f7cd0a4d5d030f60ff103_61.png)

That was so good switching。Understand the trade offs between circuit switching versus packet switching。

 And what was， you know， the pros and cons of each approach。

You're obviously not expected to know circuit switching in detail because we didn't cover it。

 but we covered it at enough of a level that you should be able to understand the trade offs。

Any questions on circuit versus packet switching。 I know that was a while back。没。

They're both a form of sharing， so they're both a form of implement statistical multixing。

 but they do at very different granularities。 Circuitcuit switching is at the granularity of a circuit。

 You've booked that bandwidth for the entire duration。 So whether you're using it or not。

That bandwidth is reserved for the duration of the reservation。



![](img/bdc6f073bc8f7cd0a4d5d030f60ff103_63.png)

Any other questions？Okay， so the second design choice that we emphasized was this notion of modularity through layering and going back to the layers we discussed。

 we talked about breaking down end to end communication into these tasks that we then arranged or organized in these five layers going from applications on the top。

 building on top of a reliable delivery service on top of best effort global delivery that used best effort。

 local delivery。

![](img/bdc6f073bc8f7cd0a4d5d030f60ff103_65.png)

All the way to actually putting bits on a wire。This was L1 to L 7。

And we said that once you have these li。

![](img/bdc6f073bc8f7cd0a4d5d030f60ff103_67.png)

We introduced this notion of protocols。 This is the language by which pure layers communicate。

So two pure layers on either end， we have protocol so that they know the syntax and somantics。

 They know how to understand each other。 going back to that CEOs exchanging letters example。



![](img/bdc6f073bc8f7cd0a4d5d030f60ff103_69.png)

We had this figure that is important to remember， which is that at every layer。

 you can have multiple protocol implementations。Except at the network layer where we have one universal protocol。

 that's I。Things to remember that three important properties to remember in this picture。

 One is that we have this notion of strict layering。

So every layer builds only on the functions implemented at the layer below and it supports the API that the layer on top builds。

给。Those the questions怎。Yeah， good question。 West P youP in this picture。

You got something that triggered many people with SN。 That was one of the。PP is not here。

 This is the data plane。Learing。So this picture is capturing all the data plane protocols。

So BGP is the control plane。Ford layer 3， but it's not in this figure。Now。怎。

Think about that for a bit。 It's a great point to make。

This protocol diagram is capturing if I have a data packet。

 if I go off on the internet and I catch a data packet。

 these are the set of protocols and headers I could expect to see。

 We actually don't have a nice layered equivalent for the control plane。

We have control plane protocols that support the data plane at each of these layers， but not。

We don't have an equivalent diagram。 There is no control plane for the application layer。

 for example， or control plane for TCP。It's the IP header at some level。

 but also making the IP header work meant you had to have forwarding tables。

 which then meant you need。Link state and distance vector and BGB。You mean， in a physical sense。

 Yeah， it it bits on the wire。 It's the header。When。

 so the question is what do we mean by I protocol。 So strictly speaking。

 it's the IP protocol specification。 It's the IP header。

But then there's a lot of supporting infrastructure that has to go into making routers know how to treat that I P header。

 And there you get your routing， you get your management。Any other questions？

Other things to note in this picture， you can have multiple versions。In a particular layer。

 so for example， we have TCP and UDP。We also have things like Ethernet or the fiber protocol at the layer2。

But we only have one， I believe。行。

![](img/bdc6f073bc8f7cd0a4d5d030f60ff103_71.png)

嗯。So that is the principle， having this notion of layering and having one universal IP layer。

 understand why it was important， not just you know the fact that we have it and why was it important and useful was that innovation was able to happen proceed largely and parallel it。

This is the benefit of having that kind of modularity。



![](img/bdc6f073bc8f7cd0a4d5d030f60ff103_73.png)

Any other questions。I know it's been a while since we talked about it。

Layering and protocols and all of that。The last thing， one of these。

Key design choices that you have to keep in mind was the end to end principle。

 And we've come back to the end to end principle repeatedly when we looked at decisions that were made while designing different protocols or different headers。

The idea behind the end to end principle is it tells us what functionality gets implemented well in the network。

 And so remember， we said we had these five layers。



![](img/bdc6f073bc8f7cd0a4d5d030f60ff103_75.png)

In terms of what layers get implemented Well， we said that all five layers get implemented at the end host。

But only layer 1 to layer 3 gets implemented in the network。We talked about why at length。

 Why is did we do this split， specifically Why did we not implement reliability in the network。

And we attributed that decision to the end to end principle。

We also several times have pointed out that the network layer gets implemented。

 It's the highest layer that gets implemented everywhere。



![](img/bdc6f073bc8f7cd0a4d5d030f60ff103_77.png)

The end to end principle was this argument about from Dave Clark about how we reason about where to place functionality in a network。

And we said the way we should think about it is if you're thinking about implementing a function in the network。

Can you， if you implement it in the network， iss it completely and correctly implemented as a function。

Or do you still need to implement it at the end host。

And if you still need to implement it at the end host。

 can you get away with not implementing it in the network。And something like reliability。

 we walked through this line of argument that said there is no scenario in which having reliable delivery in the network was going to be good enough to actually reliably transfer data between two applications。

Because worst case， your disk crashshed at the receiver before you willlily transfer the data。

 And so if you're going to have to do this end to end check on whether your data was giliably transferred。

 then why bother doing it in the network。But we also said sometimes you might do it as an optimization。

 but not for correctness。That LED us to this kind of layered。Bdom。Okay， so we have layers。

 which is how you break things down。 We have protocols， which is how you communicate between layers。

And then we implement them through these headers and header encapsulations。 So again。

 going back to the CEO example， if you take a letter， you put it in an envelope。

 you put it again in a Fedex envelope。 That's the goal that headers are playing in this picture。

when you look at this picture， you should be comfortable with。

 you know what headers are getting added well。What headers are being removed well and you should be able to say。

 given a particular layer， what headers will that does that layer need to understand or when it receives a packet。

 what layer will be on that packet。And when it sends it up， which layers does it。

 which headers does it actually move before sending it up or which headers does it add before sending it down。

So this entire process of heteroer encapsulation and decapsulation， both what gets done。

 but also why it gets done。Any questions on this？This particular layering architecture。



![](img/bdc6f073bc8f7cd0a4d5d030f60ff103_79.png)

We then moved on to this kind of more complicated view of data packets flowing through the network。

And we say we started at the application where we might have a protocol like HttP。

 So we take some application data。 We'll put it in。An H T TP header。

 which is an application layer header。 We would add a TCP header， add an IP header。

 add an ethernet header， sendend it out。So when you walk through this， just test yourself。

 for example， by saying， okay， if I'm looking at this particular layer implementation here at the routeer。

What headers does it have to understand。What if I look at a。Pack it over here on this link。

 What headers is it going to have。If I look at a packet as it's being transferred between the ethernet to IP interface here。

 what headers does it have。跟。Any questions on this one？



![](img/bdc6f073bc8f7cd0a4d5d030f60ff103_81.png)

No。Okay， so taking stock， we started looking at how we do things and we were looking at the control plane。

 links， goers， topologies， domains， intra and inter domainomain gouting。

Then we switch to why we do things a particular way with took best effort layering the end to end argument。



![](img/bdc6f073bc8f7cd0a4d5d030f60ff103_83.png)

There's one remaining topic which is going back to the data plane， which is the design of IP。

 and I think our entire discussion of IP can be summarized by looking at this IP header。Okay。

 so you should know what。All the fields here are in the sense of what role are they playing。

So we had certain fields for passing packets， certain fields for dealing with strange things that happen in the network like loops ors or loops or corruption。

We have source and destination addresses and so on。So I think just looking at this。

 walking through each field。Reminding yourself why it's there， why we needed it。

 What we do with that field。But also think about our discussion about which of these fields were working out well for the Internet versus not。

 which ones were a good design decision versus not。

 And a lot of that discussion about why the header looks the way it does or how what we did or did not like about the header you can remind yourself by just doing the comparison between IPV6 and IPV4。



![](img/bdc6f073bc8f7cd0a4d5d030f60ff103_85.png)

Like why did we get rid of check sums， Why did we get rid of fragmentation and so on？嗯。Yes。Right。

 so where did the check sum go， if great question， If the end host wanted to check whether the packet was co or not。

 we're going to have a check sum at a higher level in the TCP header when we get to it。Yeah。

 so what would have happened if let's say the corruption。

 I think the worst you can think of is change some bits in the destination address。

 And so your packet was carried to a different destination。 That destination。

 if when it checks the checks sum， it should fail。Fair enough yeah。Yeah， okay。

 what's the worst case you could construct？Yes， and also because those checkss often get checked in practice on your network interface card。

 So， you know， it's not even going to make it to Malitia。 You'd have to have a。

Lucky recipient that received it by having some bits twid， you know， unfortunately on the wire。 So。

 you know， and a totally innocent destination， just lucked out and got that packet and actually knew how to go into your operating system and fish that packet out before it got dropped and said let me check if there So you'd have to have malicious coat sitting on a lucky host。

 able to tap into your operating system。 So I think in practice， people don't worry。😊。

Any other questions on。Any other questions on any of them a do。也。So question is。

 why didn't we do path vector for intradomain routing？ I think it's largely historical， You know。

 probably at the time， people were also worried about long path。

 And so then your path within a domain， you were advertising very long path。

 this would have been a problem。 I suspect if you looked now at this point in time。

 if we got to wipe the slate clean and redo intra domainomain routing， we would say， okay，100。Hops。

 even that is not that many bytes。 But if you go back to the time when people were designing these bandwidth。

 they were very low bandwidth links。 If we talking about 10 kilob per second links。

 So this idea of sending large exchanges across a network topology that we don't know about。

Was concerning。 So for scalability reasons。That is the other thing about the Internet is。

 it's an evolving thing。 We don't get to just reinvent it tomorrow。Any other questions？



![](img/bdc6f073bc8f7cd0a4d5d030f60ff103_87.png)

Okay， with that， then I think that's all I had。All the best。Good luck on the example。

I don't think it's a particularly difficult one。看。

![](img/bdc6f073bc8f7cd0a4d5d030f60ff103_89.png)