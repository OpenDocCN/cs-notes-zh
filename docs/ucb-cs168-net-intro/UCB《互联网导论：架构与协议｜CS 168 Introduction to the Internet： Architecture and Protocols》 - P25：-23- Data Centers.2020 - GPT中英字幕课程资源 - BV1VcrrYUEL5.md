# UCB《互联网导论：架构与协议｜CS 168 Introduction to the Internet： Architecture and Protocols》 - P25：-23- Data Centers.2020 - GPT中英字幕课程资源 - BV1VcrrYUEL5

Yeah。

![](img/12a7c548ececc129e6107863b71b7fff_1.png)

Okay， so let's get started topic for today's data centers， as you all know。😊。

Just a few announcements before that final exam， I think you all know this just wanted to say it one more time。

 April 30th， details on Piazza soon to be on Piazza。One additional note。

 the finals with a view material which was scheduled for Tuesday。

 we won't have a live Zoom lecture instead Murphy and I are going over these independent video recordings that are going to cover the lectures that we've covered we're going to focus on lectures since the midterm and so also for the final。

The final is going to be based primarily on the material that's happened that we've covered since the midterm and so that's what the review is going to focus on Scott Jennkker's lectures still at the same time live Zoom lecture April 23rd and 28th do attend it's a treat that we managed to get him so let's all do him the good see of turning up and being engaged。

And that was it in terms of。😊，Announcement， so let's get started。You know data centers， everyone。

 all of you know what data centers are of course at least we have our own idea of what it is if you look up a place like Wikipedia or something it'll tell you that a data center is computing infrastructure in one physical location shared by multiple users and applications and that's actually a pretty good definition of what a data center is it is though a pretty broad definition in the sense that if you follow this definition data centers go way back you know you could go back to the very first computer the INIAC in the 1940s and it was in one location it was shared by multiple users and applications。

😊，It was actually one computer， this entire room is one computer。

 it was also the only computer that everyone had to use。

And so that's pretty different from what we currently think of as data centers。

 but you know the natural evolution does actually start from kind of this notion of a machine room or a computing room。

This picture， of course， changed radically over the years most。I would say the biggest impact。

 the biggest reason was the development of the personal computer or the microprocessor。

 and that in effect led to rather than building one room with a giant computer。

 everyone was going out and buying a bunch of these personal computers and building their own machine room so this is a machine room instead of service computers that service as a small group。

😊，We tend to think of this as ancient， but actually if you walk through Soda Hall。

 you'll quite find pretty much on every floor has its own machine room。

And then the natural evolution from there was to something that today we would call a private data center which is just a big machine room and so again this is we talk mostly about clouds and Googles and Microsoft。

 but these private data centers are actually ubiquitous and if you added up all the machines in all of these private data centers。

They probably I would guess outnumber or equal that of the cloud provider。

 so Berkeley for example has a 10，000 square foot location on Firstt Avenue that is Berkeley's private data center。

 pretty much every enterprise out there even today does have a private data center。

But that's said and done when we talk about data centers today we tend to talk about what people would call nowadays these hyperscale data centers。

 this is one locational set of locations that have millions of servers that are re useded not just by one enterprise or one company。

 but in the case of cloud computing by pretty much anyone that wants to run any application on the cloud。

And so our context when we're talking in this。😊，Clas。

 I want you to just have it in your head that we're really focusing on these modern hyperscale data centers。

If you had to talk about a private enterprise data center， I probably wouldn't give the same lecture。

 so just keep in mind that that's our context is the Googles and thearrowrows and the Alibabas of the world。

And you know you could do an entire semester， in fact certain universities do just talking about cloud networking and data center networking we're going to do one lecture。

And so the theme earlier， what I want us to focus on is how and why networking and data centers is different from everything that we've talked about all semester along。

And so think of it as I want you to get the high auto bits on how things change and why they change。

 we're not going to do a super deep dive on any one aspect of data center networking。

 but if you're interested encourage you come。Take the graduate networking course。

 we do much more data center networking at the graduate course level。Okay。

 so with that plan for this lecture， we're going to just start by highlighting these unique characteristics of data center networks and then the aspects I'm going to go deeper in on is one is the kind of the design of these networks like what is the topology。

 how due to addressing and routing。And then this question of congestion control and transport。

 if we have time。And again， the focus is going to be on how we approach these questions。

Differently in this context of data centers。Okay， so with that。

 how are data center networks different from the ones we've talked about so far， any thoughts。

 just quick thoughts？At a very high level。Well， I mean。

 you can control the entire thing yourself right， like I mean。

 like the company within their data center， they can control the network。

 they can probably run their own like， you know， internal protocols that you're not going to see out on the Internet right so single global control a huge impact。

 and that's a theme we're going to be coming back to repeatedly。That's one。😊。

I actually had only four。Tell lots of little differences， but I thought four that really stand out。

Someone wants to chime in， jump on the chat channel otherwise Is going to keep going。

First is sort of scale in one location it wouldn't be correct to just say scale very hard to beat the scale of the internet the internet is huge in scale。

 but this idea that you can have hundreds of thousands or almost a million in some case servers in one location or endpoints in one location is pretty unique to these kinds of hyper scale data centers。

Administered by a single organization what Mark just brought up the fact that you as a single organization have control both that you can sort of implement centralized policy and central control。

 but also that you control both the network and the end hostst and I say to bearing degrees here because this is slightly different depending on whether your own data center infrastructure。

 so what I mean by that is Google's infrastructure that they use to support Gmail and search and so on on YouTube versus you're supporting a cloud infrastructure that other customers will come and run on。

In all cases you control a network， if you're building out your own infrastructure。

 you completely control the end hosts as well what I mean by that is you control。

The network interface cards， you control the operating system， the version of the operating system。

 if you choose to change your TCP stack， you can go ahead and do so。

You can do all of that as a single organization with one decision maker in the context of a data center if you're in a cloud in the endhost context。

 you still do control kind of the lower layers of the stack so you control the hypervisor。

 you control the network interface cards。But the guest OS within a VM may be outside of your control。

 I mean it is out of your control。The other form of control that's fairly unique to this context is you actually place you have control over the placement of traffic sources and sinks if you think of a normal internet ISP like Beon。

 let's say。They don't have the option of saying， oh。

 I'm going to take the YouTube stream from this house and transfer it to the neighbor。

 that just doesn't make sense。But in a data center context。

 you can do that that's also incredibly powerful because you're effectively controlling where traffic is coming from or going to。

The third thing point I had is that there's much， much less heterogeneity so if you go back to the very first lecture when we talked about the internet。

 we said it was remarkable for its heterogeneity， you have pacemakers that are end hosts。

 you have cars that may be end hosts， you might have these supercomputers that are end hostse。

By and large in a data center you kind of have servers and often it's not just servers。

 it's maybe just the current generation and the previous generation that you upgrade your servers every three or four years。

 so you don't have all these problems that come from having equipment that's 40 years old。

 equipment that varies in power and speed and capacity and so on。

Also much less heterogeneity in terms of ground trip times， like you're staying within one location。

 so you're not you don't have underwater links and satellite links。

 much less heterogeneity in terms of technology， but you don't have this mix of not just cellular and DSL and fiber optics。

 but like five generations of cellular technology and so on。So in general。

 you can actually design around having some notion of bounded heterogeneity。

And then the last one was much more emphasis on performance， again。

 going back to when we started this class， you know。

 we talked about the listing and Clark's papers of what the goals for the internet were。

 when they were designing the internet， what were their key goals。And if you remember。

 performance was actually just not on that list， they had efficiency somewhere in the middle of the list of priorities。

But actually like minimizing latency， maximizing throughput is sort of not the most important thing designers worrieded about。

In the data center context， this is critical， this is how a data center provider differentiates themselves from their competition。

 every millisecond counts， every half a millisecond counts and we're going to get back to that in a bit。

😊，So that was kind of my main list of what I would say。Really the differentiators that matter。

 any questions on this before I move on？Okay， so thenre moving on。

 let's now start talking about how those differences are going to lead us to slightly different choices and let's start with just infrastructure like。

What actually does a data center look like and how do you build one before I go forward the two people I wanted to highlight that really I think actually remarkably all of the material in this slide deck。

Dived some work that they did so I just wanted to call them out one is Ammin Vad he was a Berkeley Es undergrad also got his PhD here。

 then moved on to the faculty at UC San Diego。And when he was on sabbatical， he went。

 he spent his sabbatical time at Google and this was I think in like 2004 or 2005 and really started learning about how they were building their clusters and what the networking needs were and so on。

 and he went back to UC San Diego after that sabbatical and with his students worked on really what has become the blueprint for how we build。

These large data centers。He hugely influential， Google did eventually manage to entice him to leave UC San Diego and join Google full time。

 so he's now at Google and he actually runs all of system infrastructure at Google so not just the networking but also virtualization servers and so on so。

Really just an industry leader in terms of how data centers get done。

The other name that belongs on this list is Albert Greenberg， he not Cal。

 but in East Coaster for the most part of his life。

But he spent most of his career actually at AT&T labs as a researcher at AT&T。And again。

 did a lot of seminal work there we talked about Gau Expford。

He was both Le Ga and General Oxfordxford at the time were in his group at AT&T and he was really like a mentor to them。

And he had a lot of seminar really creative ideas around how people should be building networks that he worked on when he was a researcher at ATT and Scott will probably talk about this when he talks about SDN because in many ways that work you could almost view it as a precursor to SDN。

 but after spending decades at AT&D he kind of got fed up of frustrated at being there so AtTT is a very conservative oldt company and the research group they had all these great ideas that they could do。

That weren't getting picked up and put into practice So he moved to Microsoft research and like Ammin started getting exposed to very early days of data centers。

And like I mean built out almost it's funny the work came out at almost the same time。

 they both kind of had the same idea expressed slightly differently but so that also has become a blueprint for how industry does data center networking he now runs all of Azure networking so again they've remained very influential and active in how data centers have evolved。

With that， what does a data center network look like？So let's just start very small， go bottom up。

We have a bunch of servers。That's our compute nodes。

Every one of the servers is connected to a top of rack switch。

 so this is a pretty typically not that expensive switch。

 the core chip that goes into one of these switches is like $200 or something。

And then you have these links， so that's a server rack and we have these links connecting every server from its network interface card up to a top of rack switch so 10 gigab per second is pretty standard maybe even low end today it's probably 40 gigabits per second I'm going to be talking about this as the servers access link and when I talk about a server that's。

Generating traffic at line rate， I mean it's generating at that limit or the rate of its access link so today you can think of it as 10 gig or maybe 40 gig。

so that's a server rack and in a data center we just have lots and lots of these racks just to give you a sense of scale so let's say that a typical building or data center location would have say 200000 servers and you'd have maybe 50 servers in a rack okay so that should give you an idea of you'd have thousands of these racks in one place and we want to interconnect these thousands of racks or these kind of order 100000 servers that's kind of what we're pushing for and that's standard today so this is not even being ambitious that's just。

Representative of Kagan State。And so a central question we're going to be talking about is really how do you network these Gs and the goal here。

 the thinking has always been to be very kind of application developer friendly in the sense that we want application developers to be able to guide all of these big data distributed applications without ever waing about the network coming in the way so they should never have to work around limits of the network so that's kind of the goal that's driving all of this。

😊，And so before we go into how we do this， we should talk a little bit about what the traffic looks like and what the traffic requirements are。

Okay。So let's at very high level， you know， if you had a simple web search。

 what does this look like to a data center， you ship your request off to some server in the data center。

And that server is then going to farm off a whole bunch of queries。

 it's maybe querying the index for that search engine， it's maybe querying the user profile。

 maybe it's generating ads for to respond and so on and then it's shipping a response back。

What matters for our context of what's important is a distinction between traffic that's coming into the data center from the outside world。

And the traffic that's within the data center。And this was sort of a very simple toy example。😊。

How complex are these kinds of what we call？What is an aggregate？

Qual is where you know you have one request come in and it kind of farms out recursively all of these internal requests。

This is just one stat from a study published by Facebook where they say that for one popular page that's being loaded。

 so you're getting one request from the outside world。

 you might be generating an average of 521 MeCashD lookup。

 so this is lookups on the internal key values store。

Okay so all of those hourss coming out inside on average 500 of them and they'd actually go on to talk about how in many cases it could be like 2000 or so。

A different type of workload that we'll talk about often is not necessarily something that's in response to a user request。

 but could just be analytics on the data that's stored within the cloud。

 so mining your data for insights and so on， running Mad， Par Hadoop and so on。And again。

 in the context of those workloads。All of that request quest response traffic is happening within the data center。

Okay so where I'm going with this， so if we talk about data center traffic。

 you typically hear people talk about nots out traffic。

 this is traffic that's going between the data center and the outside world okay so this is like the user sending and their request to the data center。

And then we talk about East West traffic， this is traffic between servers within the data center。

And by all accounts and everything we've heard from all data center operators。

 Eastwet traffic is several orders of magnitude larger than north South traffic。

 and so that's really going to be our focus is focusing on how we support this eastwe traffic。Yeah。

Is it a big deal or you know what are we talking about in terms of volumes the volume of traffic is large and going so this is a graph showing the aggregate traffic on the Y axis with time on the X axis it's normalized typically most of these data centers when they release data they never tell you what the absolute numbers are unfortunately so they'll normalize it so you can see a trend and so the really the takeaway here is if you look at this there's a 50 x growth in traffic over a period of about six years so that's pretty remarkable that's way faster than most low even。

And so we have to support a huge amount of this eastwe traffic。😊。

And the Eastwest traffic is going quickly， you can't just hope to deploy bigger links or faster routers。

And so that becomes our central question is how do we support these high volumes of east West traffic？

And our goal here is， again， ideally， informally if you think about it。

I want every server in the data center to be able to talk to any other server in the data center at its full link rate。

If we can support this， then that's a great model for application developers right they own a server。

 they have a 10 gig link， they can just talk to any other server。

 it really simplifies distributed programming。Slightly more formally。

 what we're saying is that we want a network with high bisection bandwidth。

Is this a term that's familiar to？People。Okay， so let's go over what bisection bandwidth it so bisection bandwidth is actually a pretty simple idea it's you say you take a graph it's a formal definition from you know graph theory it's you take a graph and you want to partition the graph into two equal halves。

😊，And then you want to look at how much bandwidth there is between those two halves and so the way we talk about it is we say you pick the minimum number of links that you must cut in the graph in order to partition that network into two equal halves。

 so it's like a minimum cut， but it's a minimum cut in order to get two equal halves。

And then we add up the bandwidth of the links in that cut。And that's our bisection bandwidth。Okay。

Let me repeat that one more time， so we look for the minimum number of links that are going to partition the graph into two equal halves and then the bandwidth of those links is our bisection bandwidth。

So when we talk about full bisection bandwidth， what we're saying is that the bisection bandwidth should be such。

So that all the nodes in one half in one partition can talk to all the other nodes in the other partition simultaneously at full line weight。

Okay， so I divided， I took n nodes in a graph， I divided it into n by two。

So each partition has n by two。And now I'm saying the n by two nodes in one partition can talk to the n by two nodes in the other partition。

At the full capacity of their access link。So if I had end nodes， my bisection bandwidth。

 if my bisection bandwidth is n by two times R， then I have full bisection bandwidth。Informally。

 this just means any node in the left can talk to any node in the right at full line grade。

Did that make sense？Would anyone like me to repeat that？Going once。Okay。

 so we would like to have a network that has full bisection bandwidth because then basically it means anyone can talk to anyone at full access at full rate line rate。

😊，But in practice that's incredibly expensive to do so it's quite common to do what people will call oversubscription。

 which informally is just how far off we've formed full bisection bandwidth。More formally。

 if you look at the guph literature， it's defined as the ratio of the worst case achievable bandwidth。

To full bisection bandwidth。 So you take a certain traffic pattern between nodes in one partition to nodes in the other partition and you'd look at actually how much traffic can they send before we have。

Max out the links that are between the two partitions。That's the achievable bandwidth。

 we would divide that by the full bisection bandwidth。And so you'd say， maybe， you know， I got。

I'm half， which means I'm amount only at half of the full bisection bandwidth。

So going back to we want a network with high bisection bandwidth， would anyone like me。

 was that concept clear to everyone or should I repeat it， it's basically take the gov。

Take the set of endpoints， divide them into two equal partitions and ask how much bandwidth do I have between the two partitions？

And what we aim aim for is lots of bandwidth。Conceptually clear。

 even if the exact definitions are not。Can I get some response？I'm going to O。Thank you。Moving on。

 So let's say talk a little bit about how we're going to get this high bi sectionction bandwidth。

 And I'm going to walk through a few design options that are。😊，Clearly broken， perhaps。

 but I think it's useful in order to kind of set the path towards where we're trying to go。Okay。

 so let's start with what I'm going to call a big switch put。

 which is I'm going to take every one of those gaps。

And I'm going to connect them all to one giant switch。Okay。

And this is clearly a bad idea for many reasons one is the number of ports I'm going to have at a switch is on the order of the number of racks that I need so just to put some numbers here。

 we said we would need thousands of racks。And typically， if you look at some of the switches today。

 they have port satellite in the hundreds， so thousand0 is not something that's very easily achievable。

😊，Bigger problem is that the speed or the switching speed is basically order number of servers times the server access speed because we're basically connecting。

All the servers to this big switch going through the top of rack switchitch。

 but if we're saying we want full bisection bandwidth。

 we're basically saying all servers should be able to talk to each other through this big switch。

How bad is that if we said I have 100，000 servers and they are 40 gigabbits per second。

 we're talking about a switch that has order petbits so petbits is 10 to the 15 right so we're going mega gigertega betterbits so that is not something we know how to build todayteabbit switches exist petabbit switches do not。

And so really this approach。So it was obvious to you at the beginning， but it doesn't scale。

And sort of a subtle point to make here is that even if we could build such a big switch。

 right because maybe you know， we put a whole bunch of really small people in a room and they figure out how to build this big switch。

😊，It would be a highly custom or non commodity design。

 and that typically means that it would be a very expensive design。I want to just。

Spend a little couple of minutes talking about this notion of commodity design because this runs through all of data center design people want commodity solutions what do we I think we all intuitively understand what we mean by that in this context typically what it would mean is that there's typically a generation of technology that is commonly available it's widely available at a particular time。

😊，And because of that， it actually drives the cost down。Right， and so for example， today。

 if you said。10 gig or 40 gig is commodity。 You can get a 10 gig link or 40 gig link。

 You can get it from， you know， hundreds of different vendors。

Usually not expensive because you have 100 different vendors but on the other hand if I said oh I want a switch with a onetbit per second link that's not so commodity anymore and while I can go buy it there's probably two vendors that I can go get it firm and if I look typically at the dollar per bit of what is commodity technology versus the dollar per bit for what is kind of cutting edge or emerging technology。

 they can be a huge difference they can be like between two times more expensive to 10 times more expensive for what is commodity versus not commodity。

And so these data center providers really want a solution that is commodity another reason why commodity is building off of commodity pieces is important to them is to avoid being locked into a particular vendor if you design your data center in such a way that the only person in the entire market that can build it for you is Cisco then if you go Google or Microsoft or Amazon you don't want to be in that position because then what if Cisco starts charging you too much or what if Cisco goes out of business then you don't have a viable plan so we're going to come back to this theme over and over we want commodity designs that was hugely influential in shaping。

How people design data centers。So that was a big switch we didn't like at what if we took another perhaps obvious topology。

 a tree network and so we just built a tree of switches on top of these top of rack switches。

 this takes care of the problem of having this fan out of  a thousand ports that no one knows how to build。

But if we just said， oh， we have all links that are the same capacity。

 we're clearly not going to have that bisection bandwidth， that high bisection bandwidth。

 if all the servers on the left hand side decided to talk at the same time to all the servers on the right hand side。

We're going to very quickly overload the tree at the top， the node at the top。

 and the length of the top。So this wouldn't work either。

So what we might then consider is something called a fat tree。

 this is actually a name I did not invent it。So a fat tree is basically a tree。

But the links as you go up the tree get fatter， they get higher capacity how high capacity should they get if you're in know graft carry land is whatever capacity you want in order to support whatever bisection bandwidth you want so if you wanted full bisection bandwidth。

Those links at the top would very quickly get very fat。

 so fat that in fact we don't know how to build them or at least not with commod solutions。So。

 in a factory。The port count problem goes away。The un' congested at the top of the tree problem goes away。

But we are left with this problem of how do I get these fat links and these high link speeds and switching capacity at the top？

So as a logical view， what you should think is that as a logical concept。

 what I want to build is a factory。😊，But I don't actually know how to build it in a way that's scalable or that doesn't require some kind of specialized links and specialized switches。

Good。Is this clear so far？Any questions or anything that I can repeat？Yeah， can I reex the factory。

 So the factory is exactly the same as a tree。With only one difference。

 which is that as I go up the hierarchy towards the root of the tree。At every level。

The links get fatter What do I mean by that they just have more capacity so let's walk through an example right let's say that I had just for simplicity I'm going to say let's say we had 10 servers in Iraq。

Okay。And each server has， so that's these within a rack here。

 each server has a 10 gig link connecting it to its top of rack。Switch， okay。So I have tens of us。

Each talking at 10 gig。To the top of that。And so if I didn't want to have any risk of congesesting。

 what capacity should this link be to people see my cursor？

The link between the top of rack and one node above it。so I have 10 servers each with yeah。

 so going up from that top of wax switch， I want this link to be 100 gigabs per second so one link 100 gigabits per second。

That was just 10 servers times 10 gig。Now here at this switch I had two of them and this is a toy example。

 so it's only two。But let's say it was two then this fat link over here going between。

The root and one level below would be 200 gigabbits per second。Now mobilelististically， typically。

 rather than just two racks below， I would have， let's say， 20 racks。

And so actually this would not be 200 gigabits per second， it would be two1abbits per second。

So it's just a tree apology， but the capacity or the speed of each link as I go up the tree is getting fatter。

 it's increasing in capacity。Does that make sense？Can I repeat that one more time for anyone okay so we like this model right if I really could build a2 tiabbit per second link at the root or a 20 tiabbit per second link at the root。

 this would be great because I don't have a high port count I do have high bisection bandwidth and I'm happy。

😊，But I can't actually build those fatlink， so we still need an alternative。

And the alternative to that is something called a cross network this is actually a very very old idea of a network was developed in the 1950s people would build telephone switching networks out of this so in this context you know if you look at the switch as a whole to the left here the input telephone lines to the right or the output telephone lines。

 if you wanted to place a call from an input line to an output line you would find a path through the cross network and set up the connection between the two telephone lines。

😊，So this is a cross network。😊，It's basically you're building a larger。

Switch or a larger network out of a whole bunch of smaller switches or smaller network。

Switch elements and so this has the theme of we want to build a large high capacity network using small and in our case it's going to be commodity building blocks。

Let me pause a second just to read the chat channel。

Would the factory not scale because the capacity of the links depend on the situation absolutely so let me go back to this if we were in a context where you know these links at the bottom were one gigabit per second and I only had let's say 100 servers and let's say if we did the math and we said oh this link at the top needs to be 100 gigabits per second then you could absolutely build a factory for that context。

😊，But our context is we have 100，000 of these servers， so let's say we have 40 servers in Iraq。

And our context is that typically access links are like 10 or 40 gig。

And so very quickly this becomes hundreds of gigabits per second。

 this becomes tiabbits per second and so on。so let me look at the next question so in this bise model we are saying hosts want to talk to hosts in the other partition。

 but how about communication within one partition yes so you actually want any host to be able to talk to any other host。

In the network in its entirety， usually it's talking about one partition to the next partition is the worst case。

 so if we talk about that， then all host can talk to each other at full line rate。

 so it certainly is the case that I want two servers in the same graph to be able to talk。

At their full line rate and the top of rack switch will do that for me。So at every point。

 we have to ensure that any server can talk to any other server at full line weight。

If we have full bisection bandwidth， we are guaranteed that basically。Because remember。

 bisection bandwidth is the worst case partition。Let me keep going to some of the chat questions。

Yeah。Should I move on？Okay， so back to the cross network so why do we like the cross network we're going to build a high capacity switch out of a collection or an arrangement of these smaller cheaper switches right so if I look at this figure and I look at one little switch here it's a four by four switch right has eights。

😊，In the old phone network terminology， they would have called this a four by four。

And yet they've been connected together in such a way that effectively what they've built with this close network。

Is a 16 by 16 switch right so 16 inputs。16een outputs。So in the old cluster terminology。

 you would say you've built a 16 by 16 network using four by four switches。And you could go further。

 you could make this a 32 by 32 by just adding more of these rows and more of the links。

 and more rows and more status， more columns， so you could scale this out。

And so some of the important properties that you should notice here is that all of the switches。

Have giveive me just a second because my chat channel is hiding my own slide。

All of the switches have the same number of ports if you look at any one of these little switches in this figure。

D了 bit boots。so we eliminated the problem that the giantants switch had where it had to have a port effectively for every rack。

Moreover， the number of ports is actually low in this case it's four by four and I could by combining more of these built pretty much whatever capacity network I wanted。

And the last important point is that if you look at this topology， all link speeds are the same。

So both these internal links， the external links， all of the links are the same speed。

And if you build this kind of cross network， you can prove that it has full bisection bandwidth。

or that there's configurations of clause networks where you have full bisection bandwidth and that's kind of a result that comes in the graph theory。

 there are entire courses in graph theory that will talk about different ways of analyzing close networks and so on。

😊，So that's kind of the basic idea behind the close network。

 I haven't yet told you how we're going to use it for the data center， but this is。

Conceptly the cross network， the important thing to remember is you can you're building a bigger switch or bigger network out of collection of these small cheap switches。

And the port count is the same and a constant on every one of those switches and the link speeds are the same。

 so you're not scaling badly。Any questions on the idea behind close。

 I don't expect you to be able to analyze a close network or draw one on your own。

 but just to get the idea of what's going on here。This this good？So quick question。

 is each box a switch， yes？And so in the 1950s， this is how they built telephone networks。

 each of these was a little switch and they would build one giant。😊。

Telephone switching fabric by putting them together。Okay。

 so how are we going to use this for the data center case。 So first observation is we don't actually。

 our context is not really that I have a set of。phyhysically different input and output lines instead。

 you know every server is both generating traffic and receiving traffic so it's both an input line and an output line。

So actually this right hand side of the clause we don't quite need it。

 we're going to go from the left from input on the left we're going to go through the clause network and go back out to another one of these left hand side links okay so this is actually called a folded clause network again if you go into the graph theory。

And what we're going to do is we're going to take one of these folded cloud networks and every one of those。

Left hand side input links is effectively a top of rack switch connecting to a switch above right so we're going to have a whole bunch of these racks。

So conceptually that's how we want to use a close network and this was exactly the proposal that Aina Vat and his students at UC San Diego had when they were proposing how to think about future data center designs。

Let me pause here for a minute， any more questions on this notion of ala network？

And how you use it in the data center。Okay， let me go forward and so this is this is a picture that's。

Wait question so so which is the top of wax switch the bottom level so in in this figure so this figure is a little is copied from the Baat paper。

It's a little bit of a toy example， so in this figure here the first lowest level of switches is the top of rack switch。

And this is a bit of a toy example in that， you know。

 every switch has four ports and it only has two servers。😊，But this is the top of wax switch。

 this is what they'd call an aggregation switch and a core switch。

So this is a toy example of a data center network with 16 servers。

And interconnected by a folded clause network。And let's just check that it has all of the properties we liked right so every one of these switches has exactly four ports。

Every one of these links is going to be the same speed， so if the server to top of rack switch。

Link is 10 gigabits per second， then every one of these links in this topology is going to be only 10 gigabits per second。

So we're not buying fancy high speed links。And this is going to give us high bisection bandwidth。

 so one point I wanted to make is when you go out or talk to many people。

 they'll say that data centers build factory networks。

And this is an unfortunate consequence of the confusion when this paper was published。

 so in this paper what they said is。That they were using the cross network to emulate a factory network。

 and then they continued to call it a factory network， which logically if you're looking at it。

 this is a factory where if you said that the root is that entire top level。

Of switches and then you know the next level in the tree is just by aggregating different numbers of switches at each level。

 and as you can see the links get fatter at the top so this is。

A close network that's emulating a factory that is true， it is not exactly a factory network。

As Google has gone forward， they've corrected themselves and called this a cross network。

 but the original paper called it a factory network and that name is stuck for better for worse。

So we're going to call it a close network。So a question from up and up is it expensive to have some knee links so here's a way to think about it right you can have 1010 gigabit per second links or you can have 100 gigabit per second link。

😊，And bit。It's usually cheaper to have 110 gigabits per second link。

 so usually the current commodity link speed is cheaper per bit。

thanhan having one high speed link or having some advanced speed link there's a separate question which is maybe what you meant also by is it expensive which is isn't it a pain to have so knee links？

Just in terms of the cabbbling and the wiring and we'll get to that in a minute。

Does that answer the question？Okay， so let's just wake up。

Whether we' are happy with this close network， okay so it。Equal small port counts。

Small lowpe links or at least not highpe links， high bisection bandwidth if you look across any level in this topology so starting between the servers in the top of rack and then between any two successive stages of switches you'll see that we have the same bandwidth available whatever that is so if we had X gigabits per second at the level connecting servers to the top of rack we have x gigabbits per second at the top level so you can build extremely high bisection bandwidth in this way。

You could also if you chose to over provision you could just say I'm not going to build I'm going to take out two of these switches at the top level and take out all of their links and in that case you'd have x by2 at the top and so you would have oversubscribed by a factor of two so you don't have to build a full bisection bandwidth network。

It also offers you many parts between any two source and destination。

 any pair of source and destination， you have multiple parts between them。

 so it's also very fault tolerant right if one switch goes down you can always send your traffic along a different path。

So it has a lot of redundancy built into the topology。And so overall。

 we like this topology right is any questions about why we like it or why this is a good topology to be working with？

Okay， so moving on and this is pretty much what most of the large data center providers this is kind of the blueprint of the template they're following there's a paper published in 2015 so this is you know almost 10 years after Iid weard'sco at San Diego started working on this that talks about all the generations of C apologies that they've had at Google and how they've evolved in time and how they've scaled in time and what worked and what didn't work and so this is actually a picture from that paper showing one of their cost apologies。

If you're looking at this you know in one of the questions that someone alluded to。

 this is a lot of links and so yes， in fact how you do this wiring has turned into a problem of its own and this。

😊，Papers around how you do aggregates of cabling together and Google you can walk through and see a whole their layout of cables and how they manage that。

 yes， that is a downside to the factories。Vars of the design are common。

 so these are figures showing to the left is from Microsoft。

 This was actually Albert Kberg's work at pretty much the same time of proposing a very similar design。

 The right is a 2015 paper from Facebook showing how they build their networks and again it has。

Basically different variants of the clause topology。

And so that's kind of the blueprint or the norm and how people are building。

Data center toppologies to today， I should point out that you know。

 closed topology is one in a kind of family of what people will call parallelal graphs or parallelal interconnects。

There are these topologies that tend to have a regular structure that have a lot of parallelal path between any source and destination so there's been work looking at is the clause topology actually the best topology from that family or could you actually do something better so there's a whole literature there looking at are there better topology so I wouldn't say this is set in stone for the rest of time？

But this is how things get done today。So wecap what we was wanted with high bisection bandwidth that you could do in a coste and scalable manner。

 this is actually a classic example of scale out versus scale up design。

 so is that a concept that you've heard before that you've studied in CS162 probably or that you're familiar with this notion of scale out versus scaleup？

Yeah， so scale up is this， you know， with the kind of the old way of thinking scale up scale up design refers to I have a component。

😊，If I want to scale it， so I wanted to go faster to be more powerful。

 I build a bigger version of the same thing and that's kind of what supercomputers did for many generations side you build it bigger。

 you make it go faster， you put more memory， more CPU in it。

Scaale Out says that the way I get more capacity is I add more of these cheap components。

That's kind of scale out and pretty much all of data centers and cloud are built have this notion of scale out design deeply。

 deeply ingrained in how they build systems and that's actually how we build software systems as well today right when you build a spark or map reduced job you're scaling the processing capacity of your map reduced job by having more parallelism by running more workers or more threads。

And so this is very much in that spirit。Is that true。Okay。

So let's move on from that so we're going to take now in our heads that clause based topologies are how we are building the physical wiring of our data center so now we have a topology。

 what are we going to do with it and it's very important to realize that the clause based topology means we have a physical topology that offers us high bisection bandwidth。

We now have to design all the other layers of our network and actually our stack and our software to be able to exploit this bandwidth so for example。

 routing must exploit all the parts available between a source and a destination。

If we're not using all the parts。It's not very useful to us that that topology was fantastic。

Likewise， our transport protocol and our congestion control protocol has to be able to send traffic to fill those pipes。

Otherwise， again， right if I gave you 100 gigabit per second capacity。

 better you're sending at one gig， then not very useful。

So all parts of the design above that topology。Haveve to be able to exploit it in order to actually achieve this high bisection bandwidth。

And so we're going to talk about two of those aspects。

 one is how you do gouting and addressing and again if time we'll talk about congestion control。

 but again the goal here， the focus is how do we make full use of that bandwidth？

I'm going to talk in each case about two design options。

 one is kind of a very incremental design in terms of incremental as a delta over what we had prior to data centers or to traditional solutions。

And the other solution I'll talk about in each case is kind of more clean slate radical solution that has been implemented and deployed。

 but it's a nice example of。😊，Kind of thinking out of the box in context where you can right in data center context。

 you can kind of。One of the big nice things is you have the option to design from scratch it's a clean slate like you have single administrative control you control both the end host and the network so you can design the entire system to suit your needs。

Okay， so with that what is our incremental approach to doing routing on top of a clause based topology one option i'm going to say is let's just think about extending distance vector and link state any thoughts on how you'd do that？

Dinor。Were advertising distance to a destination and then we pick the shortest or the best。

The neighbour， with the best distance。How would you extend it to run on a close apology？Remember。

 our goal is to use all the parts and all the bandwidth available。

pretty straightforward fix instead of just remembering and breaking ties and picking one next hop neighbor to the destination。

 let's just modify the algorithm to remember all the next hop neighbors that had an equally good path on equal cost path to the destination。

If I go back to。This figure here。嗯。Not this one， not this。If I go back and I say。

 let me look at this one switch over here and think of。

It's next hop going to any destination that's orange green or red it has two possibilities this top switch or the next top switch so instead of breaking a tie based on router ID or whatever it's just going to remember both of them。

That's a basic idea， so pretty small change to distance vector。

But that would allow me to remember both nexttops and both parts。Is that true？

Would someone like me to repeat that？I haven't told you how we're going to use those next shops。

I'm just saying if we ran distance vector on a closed topology。

And every switch remembered all the next hops that have an equally good cost to the destination。

Then we'd be good in terms of discovering routes。Did that make sense to people？Yeah。Okay， thank you。

Likewise linked it right we ran extras on a graph and we said and we have this tie breaking rule we picked a shortest path to each destination。

 you could as equally just compute all the shortest paths to each destination and then keep all the next hops that have that equal cost。

So the notion of equal cost here， the only thing that's changed in the cost topology is that I have multiple next half nodes that all have the same。

 I always have multiple next half nodes that have。The same cost to a destination。

So I'm going to remember all of those next hops now。

And so then the only remaining question really is， how do you spread traffic across the next hops？😊。

And again， the two options here one is you do per packet load balancing right so every time a packet comes in。

 I pick the next top either random or in some groundro fashion from the set of possible next hops。

 is that clear？So a question here on the chat， if a routeut is slightly costliier than the best one but better distributes the load would we never consider it in this solution that I've described to you no we are only taking neighbors that advertise。

The same cost， so it's equal cost。I'm not sure what you meant by， but better distributes the load。

 So you mean use even。Other neighbors that have a slightly longer path in order to do better load balancing does that work。

You had't mind。Yeah， so you know， in theory， you could do that in practice in a across topology。

 you have so many neighbors that have the same cost。😊。

But that you're actually getting pretty good load balancing without even considering that。

 but as a general idea， yeah， absolutely you could do that if you do that。

 then you have to make sure you don't end up with loops。

You don't want you sent it to someone that then sends it。

 you want to make sure that at every point your cost is decreasing and so you're not looping。

 but that aside aside yes， you could certainly think of doing that。Okay。

 so let's say we were doing this for packet load balancing we do a very good job of spreading traffic across the multiple parts that downside to this approach is you could make TCP very unhappy so one way you could make TCP very unhappy is just reordering so if I had five。

😊，Next top neighbors and I'm sending packets you know one two。

 three four five on five different links， they're going to follow different parts through the network and for minor differences in queuing along those paths or any number of reasons that the could get those packets out of order so it could get them like543 to one。

And what is it going to do when it gets？Instead of getting packets in order 12345。

 it's going to get them in order 54321， what would happen with TP？So at the centerer。

 what would you get you would get basically duplicate acts？

You would get duplicate X until the right packet arrives。

 which means you would enter fast re transmit， you would cut your congestion window。

 you would cut your weight， this would not work so well。More generally。

 there's just a number of reasons why TCP is really fundamentally not designed to run on top of multiple parallel parts。

 you know， for example， you have one ground trip time estimation。

But what is a ground trip time estimate when you actually have five parts instead of one part。

 you ought to have five different ground trip time estimates？

Another way in which it's broken is if you think about it， every time you have a packet drop。

 you cut your weight in half。But you actually dropped a packet along one out of your five parts so you didn't need to cut your weight in half that was excessive because the other four parts did not drop any packets so there's just lots of reasons why tCP is really not designed for routing over or having packets transport over multiple parallel path there is a standard called multipath tCP that has emerged just exactly to address。

This problem of if I have three parts， three parallel parts between a sender and a receiver。

 how do I run TCP on top of those three parallel parts？

But we're not going to go into multiple TCP is the problem clear about why TCP running on top of multiple parallelal parts is not a great idea。

😊，Okay so how do you fix this the simple fix and this is the industry standard thing to do is to not do per packet load balancing and instead do per flow load balancing and so what this says is you pick one next hop for a given flow。

😊，And all packets from that flow are going to follow the same path。

 so we're not going to get this perfect you know spreading all of your traffic packets in a flow across multiple links instead the load balancing we're getting is by balancing flows across different path so different flows。

 even if I took one source and destination pair if they had 10 flows between them。

Those different flows might go on different parts。But within any given flu， we're following one part。

OkayHow would you do this simple and standard way to do this is you hash the flow5 double so when a packet comes in。

 you take the source destination address IP address。

 port numbers and protocol and you hash it to pick one of your next H options and then all packets in that flow are going to go over the same next top。

This is actually so if you use this， the traffic is not as perfectly load balanced as with per packet load balancing。

 but TCP remains happy and you're still spreading traffic at the level of flows。😊。

So this is basically the idea behind a protocol called equal cost multipath forwarding。

 which basically spreads flows across equal cost next hop neighbors。So is this clear？

What we're going to do in this first design option。

 we're going to take a clause then a distance vector length state with some extensions。

 and then we're going to do something like per flow load balancing to actually forward the traffic across all of those multiple parts。

Any questions before I move on？Is the path deterministic for given flow yes？😊。

If I have four next talk neighbors and I'm。Doing this hash based selection of the next hop。

 then I'm always going to pick the next hop。Why use TCP couldn't you make certain reliability guarantees about the network since you control it we're going back to the end to end argument though here yes。

 you could try and make your network as reliable as possible。

If you wanted it to be absolutely loss free， you normally Tnet for example wouldn't give you that and so you still do want your end host protocol to implement reliability does it actually have to use TCP per se you're absolutely right it doesn't have to but。

At least if we're building out of commodity andnet length。

 you do need some form of reliability protocol and hosts。That's it。

 there are certain networks that Infinnneand is a network technology that guarantees you that every link is lossless。

And so you there are。Data centers that use in Finnneand and they use different and whose software for that。

 they don't use DCP。All right， so let me recap this design possibility so the possibility is we extend distance vector link state this is certainly doable and it's doable with relatively incremental modifications。

😊，Nonetheless， this is not the most scalable solution and so if you think about both distance vector and Li state how they scale you have per destination without advertisements here you potentially have 100。

000 plus destinations。And you have linked data advertisements for every single link。

 and as we drew that factory out， you saw there's a large number of links。So this is。

Certainly doable， it's not the most scalable。 It's also not widely done to the extent that people do things like this。

 they usually。Pition that factory into subregions and then run a protocol within that subregion。

The early days of data centers people actually tried to do this at this point， I think very few。

 as far as I know， none of the major cloud providers or data center providers do this。

So can we do better， right， I said。Other possibilities to just think from scratch if you were to do this。

Ignore this inspector link state and what we've learned before Any thoughts on how you would。

Do addressing and routing。I have a hinter in the naming of the option。

But any thoughts on how you'd do things differently if you were building on a close network？

So the idea I'm going to proposed and this was the what， I mean， but that's original paper proposed。

Was that we letter a note address。When address an order。

 we pick an IP address such that it exactly captures its exact location in the topology。

And so since the topology is regular， meaning I know it's a close topology。

 I know exactly what the topology is because I built it the address is going to tell me exactly where the node is so let me give you explain that with an example and then we'll go back to that statement and see if we understand it。

😊，So let's say that this was my apology。And I， as a network designer。

 I know that this is the topology I've built。I'm now going to hand out IP addresses to every one of these servers。

 so I have 16 of them。In a manner that reflects where that server is in the topology so this is really just a form of hierarchical addressing so for example I say all the blue servers are 10。

0 do something 10。1 for orange 10。2 for the greens， 10。3 for the reds。And then I do this repeatedly。

 right， So within the blues， I say the two on the left are 10 do 0 do 0。

The ones on the right tend on0。1， and I continue to do this。So now if I tell you， where is node 10。2。

0。1？Like you as a network designer you know exactly where that server is in your topology。

 you didn't need to discover it or have a dynamic advertisement protocol in order to discover it you knew the topology you know how you did a dressing so you know that 10 or two means it's in this green。

Potion 10。2。0 means you went in the first left hand pair and 10。2。0。

1 means it's this particular node here。 so think about what we've done here。

 right we know the topology。We assigned addresses to map exactly to that topology。

And so based on that， we also know what the routing tables need to look like right So if I take this。

Switch row out over here and I'm just for convenience labeling the ports to be one， two， three， four。

We would say that anything that's 10， you go left。Down to this blue switch， anything that's 10。1。

 you go over port number two， 10。2， you go over port number three。And so on。Is this clear？

Would anyone like me to repeat this？Is what I did here clear。Okay。

 so let me pick another switch here just to make sure we are following what's going on here again if I said the ports are 1 to34 I would say anything that's standard0。

0 go out port1 anything thats standard0。1 go out port two anything else go to port3 or port4 I don't really care which it is and then you know you could implement some load balancing scheme the original I mean but paper actually had a nice load balancing scheme looking at the suffix of an address。

 but it's basically some load balancing scheme to pick between three or four let's assume it's CCM or something。

Okay， so that's the loing table at the switch。If I look at a switch at the next level， again。

 10 do 0 to0 do0 is put one。10。0。1。1 is port sorry and I got that it should have been 10。0。0。

1 is port2 and anything else is port 3 or port4。So what have I done effectively， I knew that apology。

 I knew how I assigned addresses。You could imagine writing a simple program that took in a few parameters like you know。

 here's the number of servers， here's the number of stages in your close network。

 here's the degree or how many links each switch has。

And you had a little program that then generated what each of these routing tables looked like。

 you could just go in and directly。Program， the routing table at every one of those switches。

You didn't have to discover where servers were or you didn't have to discover what their addresses were。

So now just this idea of what we've done， the basic idea that we're going to address node so that it precisely tells me where in the topology it is。

 is that clear？Yep， Queen once。So a few implications of this design approach。

 the number of routing entries at every one of these switches。I's just a number of quotes。

It's not order number of silvers so I have perfect aggregation。

 I know exactly which set of addresses hang off of each port because I assigned those addresses in a way that made that happen。

I didn't really need a dynamic or distributor route computation。I ignored one thing around failures。

 but let's get back to that right I could just generate the routing tables from knowledge of the topology。

 it's like I hard codeed the topology and the addresses。It does require careful addressing。

 if you give a server the wrong address， then that misconfiguration would be really。

 really bad in this case。What I note here was link failures， but again， if I had a link failure。

 you could imagine recalculating the routing tables and updating them。

Did this overall approach make sense to people so it's sort of an example of what's possible when you get to design the entire system from scratch and so scalable。

It's using all the parts。So it's doing good load balancing。It's resilient。Any questions on this？

What is meant by the topology being regular， so it's typically regular graphs or regular topologies means that it has a well defined structure。

So we're saying every node。It has you know a fan out of x， so it has so many ports。

 and we're telling exactly which other nodes。That node is connected to。So there's no randomamness。

咩食别。And it's kind of what we are exploiting there is because there's no randomness。

I don't need to go around discovering which server is where and which address is where and which link is where I just know it because that topology is regular so examples of topologies that are regular would be a square。

 a cube， a taus， a mesh。Any of those would be regular， a random curve is not regular。Okay。And again。

 this is exploiting the fact that you get to design your data center this was not an option on the internet where everyone had their own networks even before the internet got formed and every provider is evolving their topology independently and you have no idea how they're evolving their topology in this case we know the topology and that can be a game changer and how we do addressing andloing。

So just to give up topology routing addressing what we wanted when we started was a scalable solution to achieving high bisection bandwidth。

We did this by having a topology that was building a high capacity network or what people will call a fabric from a collection of these smaller switches。

And the topology we were using was a cross topology。

 it's an example for scale out approach where you have multiple parallelal parts between every resource and destination and you get high capacity that way。

And then we designed routing and forwarding solutions that actually exploit that multipath。

Those multiple parts。Any questions before I move on from them？Resulting and forwarding。Okay。

 anything anyone would like me to repeat。Because from this point on， most of what I had to say。

 I think is sort of optional。Okay， so then let's move on， so now let's think about congestion。

 control and transport。And the big big problem we're going to have in data centers is queuing delay and so let me walk through a simple back of the envelope to tell you highlight why queuing delay matters in data centers。

 so if you remember going way back we said packet delay end to end packet delay is a combination of transmission delay。

 how much time it takes me to put that packet on a while。

Coropagation delay which is the time it takes for that packet to travel kind of speed of light limited across the wire and then queuing delay this is if I arrive at a switch over outer and there are other packets in the queue。

 I have to wait for them to be transmitted and that gives me queuing delay。To put some numbers here。

 let's say we had a 10 gig link and  a000 byte packet， okay， so 8000 bits。😊。

Your transmission delay for one packet at one hop， if you divide 8，000 bits by 10 gig， it's 0。

8 microseconds。That's how long it takes me to transmit one packet at one switch。

If we now said that on average， I have a Q size of 10 packets so that there are 10 packets in my queue。

So what I'm saying is when a packet arrives。I can't just be immediately transmitted out。

 I have to wait for on average 10 other packets to be transmitted。

Then at every hope my queeing delay。woWould be the average number of packets in that queue times the transmission delay for each packet。

 right because I have to wait for every packet that's in front of me in the queue to get transmitted。

So if we set I have 10 packets and it takes me 0。8 microseconds to transmit one of them。

 I have to wait for about eight microseconds， this is at one switch。If we said that at every hop。

 so I have to do this at every hop， and let's say we said we have five hops。

And so my queuing delay is now five times that eight microconds， so it's 40 microseconds。Okay。

 everyone with me so far on how in this。Example， we have 40 microseconds on average of queuing delay。

有。Should I repeat that？Okay， we're to continue。So。In the context we've been talking about so far on the internet。

 the propagation delay， if you take the speed of light and you do calculations or you do measurements of the typical propagation delays on the internet。

 we're talking orders tens or hundreds of milliseconds。So East coast to west coast maybe like 70。

 80 milliseconds and so on， and so if you said that you incurred a queuing delay of 40 microseconds。

And a propagation delay of say 100 milliseconds。No one would care about thequeing delay it's in the noise right it's not。

The dominant factor in what's causing the packet delay you experience。

But in a data center between two data servers within a data center。

 the propagation delay can be ordered 10 microseconds or even less actually。

And this is just has to do with just speed of light and physical distance。

 those two servers are not very far away and so your propagation delay is roughly like 10 microseconds。

😊，And so now if you look at this queuing delay of 40 microseconds。

 what we're saying is that the end to end packet delay in the context of a data center may be completely determined or dominated by queuing。

That how much QN you suffer is going to determine the latency of the performance you see。

Is this argument clear to everyone？Okay so what are we going to do about that so you might also ask you know who cares 40 microseconds。

 you care because if you all the statistics that the posts that we see that latency matters hugely so you'll see all these statistics I'm never quite sure how they come up with them but they do and they could put them like a millisecond for example in high frequencyequency trading can cost you 100 million plus a month or something and Akamai has this famous study that shows that if you have100 millisecond delay in a page load time that can lead to a 7% drop in conversion rates or sales。

😊，And so people really really do want to get those latencies down and you might think 100 milliseconds is a long way off from 40 microseconds。

 but then if you combine that with where we started where we said one page load can result in 500 meCashD lookups。

 for example， in the Facebook example， then that 40 microseconds added over you know。😊。

Being accumulated over 500 Mmcte lookups or something， it starts to build up。

So it actually matters in terms of revenue， but the other reason is also a perception there is a lot of competition amongst cloud providers in terms of performance and there are a lot of attention paid to the performance that they sustain so if you look at headlines。

 you'll just see a number of these performance comparisons across clouds。😊。

And so people care about shaving off even a millisecond？

And so then the problem is that if queuing delay dominates the end to end packetcca delay。

TCP was really not your friend if you're trying to lower queuing delay。It's just not。

 it's actually designed in order to fill cues that we keep increasing your weight until that queue overflows。

And this problem is actually made worse because of the typical flows that you see in data centers。

 so all the traffic measurements will show that most flows are short and latency sensitive。

 so this is something like a request response to a MECashP lookup or so on。

But there are also a number of flows that are really really large。

 they are typically throughput sensitive， more than latency sensitive， and this is， for example。

 copying your data over across servers or doing backups and so on。

And so if you just ran TCP in a data center， what you'd have is that the elephant flows very quickly fill up these cues and the mice mice flows that matter see these very high queuing delays。

 so this is the central problem that all of there's been a huge body of work trying to fix congestion control in data centers and this is the key problem they're trying to solve。

I'm debating whether to try and give you a quick sense of what people do in the remaining four minutes。

 so let me give you a very quick sense。Let see how much of it。

6 if it doesn't just try to get the main idea。 So there's again two flavors of solutions。

 one is a more incremental one and the other ones a more radical one。

 The more incremental one that came out of Albert Greenberg's group at Microsoft and folks some。

Sot of folks at Stanford is something called DCCTCP or data center TCP。

And the basic idea is to use an old technique that we've talked about。

 which is explicit congestion notification where Laers want to mark a packet if the packet arrived and the queue was building up。

We were using that in what we talked about in the advanced congestion control lecture in order to actually reduce that queing delay and so DCTCP uses ECN it has a few modifications that honestly you don't need to know and I'm not going to go into them。

 it's really just making more aggressive use of ECN in order to keep the queue very， very small。

What I want to talk about is how well does this do and this is interesting because it gives you a sense of kind of how much performance DCP was leaving on the floor。

And so the metric I'm going to look at here is flow completion time。

 which is measured from the time when the flow starts to when it's completely transferred at the receiver okay that's flow completion time。

We're going to compare that to an ideal flow completion time。

 which think of it just as a lower bound， right which is。

What is the best possible flow completion time you could have had had if you were good and you had global view of exactly when each flow comes and exactly the state at each switch and go along the way。

 don't worry about how it gets calculated。And so the metric that DCTCP looks at is normalized flow completion time。

 which is the flow completion time you achieve compared to that ideal。

 so short way to think about it mental model is how much slower am I than an ideal solution。

And so this is the set of results that they discovered where of course， if you're ideal。

 your normalized flow completion time is one， so what this graph is showing is on the y axis。

 the normalized flow completion time， which is how much better am I than an ideal solution。

 and they're showing that for increasing load on the X axis。And what we see here is， you know。

 if blue is ideal， it's one。Yellow is TCP， which was pretty on bad actually。

And then DCTCP is a huge improvement。What it also shows us is if you're running your network at high loads towards the right hand side of the graph。

You're still about two to3 x farther from optimal than one would have away from ideal。

 so there's room。To improve things by that much。I'm now going to skip over the radical proposal。

 which is P fabric， which I'm going to summarize as being use priorities and give mice flows high priority and give elephant flows low priority。

And just allow sends to just blast their traffic while setting。

That priority level based on how many bites you had less to send， so mice get higher priority。

 elephants get lower priority。The main takeaway is， if I go back to that graph。

 P fabric is this red line here。Which tells us that this kind of more radical design。

 which involves changing both switches and and host in quite a dramatic way。

Could also give us pretty much close to optimal performance。

I realized that was not an in depth enough some， but if the only point I would want you to retain is。

The question of queuing delay is the central problem when we're designing congestion control。

And then I just with TCP is not good at doing。Eliminating queuing delay or TCP is not your best friend if you're trying to reduce queuing delay。

And there are solutions that have been worked on and have been proposed that do actually significantly reduce that queuing delay if you're interested in more information about this let me know and I will post links so you can read up more about them。

So I'm going to skip this and just going straight to the summary。

 data centers new characteristics and goals， some of them are liberating like in particular having centralized control or single administrative control over the entire system and others are constraining in particular this need to use commodity solutions so that we can scale is a major constraint。

Scaling is the must， performance is critically important in some of the other things we talked about like backward compatibility heterogeneity are somewhat less important。

So with that we are pretty much out of time， this is also my last live Zoom lecture that will release the live recording。

 the recordings for the review， so I just wanted to say thank you to everyone I know this was not the dream semester but thank you for you sticking it out and helping us work our way through it and I wish you all the best both in wrapping up the semester as well as you know whatever your next steps are good luck to you all and thank you。



![](img/12a7c548ececc129e6107863b71b7fff_3.png)