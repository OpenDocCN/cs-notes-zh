# UCB《互联网导论：架构与协议｜CS 168 Introduction to the Internet： Architecture and Protocols》 - P10：-9- Interdomain Routing.2022 - GPT中英字幕课程资源 - BV1VcrrYUEL5

Oh yeah， it is true。Do folks want to move forward。A little bit coier。

So quick announcement now discussion section has been permanently moved from being between 9 to 10 AM to 1 to 2 PMm same day。

 but so you have more later our options。Thanks， so topic for today。

 we're going to start with a new topic altogether。 We're done with intra domainomain routing。

 topic is still routing。 but in the context of inter domainomain。

 what we call inter domainomain routing or routing across domains。And so far。

 all of the lectures you've seen with Muphy lecturing。

 we talked about routing on a graph that looked like this made up of routers and links and N hosts。

And if you remember， Murphy made the point that this is how we tend to do routing within a single domain。

And so from now and we're going to focus on kind of this notion of a domain or more formally what we'd call an autonomous system。

 and I'm going to define that in a second。And we're not going to worry so much about the details of how routers and links are interconnected within this domain。

Okay，Instead， we're going to focus on the domain as a logical node。 so think of it as one node。Okay。

 I'm going to represent it with clouds， just like we had squares for routers and circles for in。

And more generally， we're going to focus on what we call this interdomain topology or the AS graph。

 the autonomous system graph。 So this is kind of the end to end view on the Internet of how different networks or different domains are interconnected。

Okay，Specifically， we're going to focus on this question of how do I find a path。

Across this A S graph。 So this is， we're finally in the realm of doing an end to end path across the Internet。

 across multiple ISps。And at the same time， we shouldn't forget that actually that path is not going through clouds。

 it's going through a series of links and routers that are within each of these domains。

But for the most part， you know， we're not going to talk about that in this lecture。

In the next lecture， we'll get back to talking about how intra domainin and inter domainomain actually intersect。

 how they integrate。But for today， we're going to stick with this picture of。

 I have a graph that's made up of these clouds or A Ss that are interconnected。啊。

And I'd like to start by just taking a closer look at one of these domains or autonomous systems。

 and what is it exactly and。What is so special about the inter domainomain topology and autonomous systems。

And so autonomous systems I'll be using the term domain and ASS interchangeably autonomous system is a slightly more formal term for what we've been calling a domain informally。

 and an autonomous system is simply a network that is under the administrative control of one entity。

So UC Berkeley is an autonomous system because the UC Berkeley staff decide how to operate our network。

 AT& T is another A S。 France Telecom， Deutsch Telecom。

 and are many autonomous systems or A Ss across the Internet。And as I said， often call informally。

 we're going to call them domains。 What defines or what makes a network an autonomous system is the fact that it has been assigned a unique autonomous system number or ASN。

This is a number that's assigned by this organization called IAN。

 I think Mufi talked about it in the context of assigning IP addresses。 So if you want to be an AS。

 you have to go to I canN， you have to make your case and you get an autonomous system number。

Book here， for example， is A S N number 25。Fun fact， this is John Pota。

 he was one of the early internet pioneers really influential in the design of TCPIP and actually in this context。

 until his death， he was a single person that handed out ASN numbers for the entire internet so he had one person doing all ASN management for the entire internet this is now of course this organization I can with lots of international laws and so on。

 but way back there was this one guy handling it。

![](img/9472cf10abb0617fa7326eaf700edef3_1.png)

Just if you curious is you know how many yess do we have on the internet， this is going up to 2020。

 I believe this number is close to 100，000 now， so that kind of tells you the scale of the AS graph。

 it's about 10，000 nodes。

![](img/9472cf10abb0617fa7326eaf700edef3_3.png)

If you're curious where they go， as you can see， the US is hoging the last largest number of autonomous systems。

 this is not surprising。 Brazil is number two， which was somewhat surprising to me。 but in general。

 you see these handed out across the world。は。From our perspective as we talk about autonomous systems。

 there kind of two common kinds of As that we're going to talk about and that are important for how we do roing The first is what we call a stub AS This is an AS whose only it only exists and its only job is to provide connectivity to its directly connected users or hosts。



![](img/9472cf10abb0617fa7326eaf700edef3_5.png)

So it's not in the business of carrying traffic between other As。

 It only exists to carry traffic to and from its directly attached host。

So UC Berkeley is an autonomous stub ears。Typically， you'll find that enterprises， businesses。

 people that are not in the business of providing network connectivity。 That's not why they exist。

 Those tend to be WSs， enterprises and so on。给。The other kind， what we call transit A Ss。

 These are A Ss that will carry traffic on behalf of other A Ss。

 So these are the the A S you'd expect， A T& T， Vaizon and so on。

 They're kind of in the business of Internet connectivity。That's the reason for existence。

And in practice， you know， we'll get to this a little bit more in slides going forward。

 But in practice， there's quite a bit of variance in the nature of transit As。

 So you might have a transit A S， for example， that covers California。

And then you might have a transit A， what we call tier1 As that cover the entire globe。Okay。

 so there's a little bit of hierarch given amongst transit agenciess。With bind out。

 this is an important distinction。 Stub A S is only for your directly attached users， Trans A Ss。

 you carry traffic for other A Ss。

![](img/9472cf10abb0617fa7326eaf700edef3_7.png)

So I want to talk a little bit more about that inter domainomain topology and what makes it unique。

 What makes it so different from all the graphs and topologies you've been thinking about so far is that the topology is shaped by business relationships between the As。

So now when I say that on the AS curve， A and B are neighbors。

It means they have a physical connection， just like two routers that had a link between them。

 That is still true。But it also crucially means that they have a business relationship。

 by which I mean they have a legal contract that defines what service they are providing to each other and how they interact。

And that really determines why we have the topology we have。

 And so there are three basic kinds of these business relationships on the Internet。

 If I take two As， X and Y， you the relationships they can have with each other。

 you can either be a customer of another A S。Or you can be a provider to another ears。

All the two aces could be pures。And so to， what does that mean。

 The business implication is if you're a customer， then you're paying your provider。

 So customers always pay providers and peers don't pay each other。 They exchange traffic。

 but they don't pay each other for that exchange。So as an example。

 you can think of Berkeley signing up with AT And T in order to connect to the rest of the Internet。

Berkeley would be AT&T's customer。And A D And D would be Bkeley's provider。Okay。Why do A Ss peer。

 I will get to that in a minute。 But typically， the assumption underlying why two A Ss appear peers。

The reason it makes sense for them to be peers is they kind of the same size or scale and that they exchange roughly equivalent amounts of traffic。

And this is all codified in， you know， the contracts that they signed with each other。

 Therell be something that says， for example， that you， over a month。

 the 90th percentile of traffic that I sent you。Is within 10% of the 9% dial of traffic that you sent me。

So there's some technical definition of equal traffic。That's in a contract。

 And it's kind of how we decide that were， we're meeting the condition to be fierceed。给。

And so let's talk a little bit now about you know， how these affect topology。

 Any questions on this so far。Goodty intuitive， I think。



![](img/9472cf10abb0617fa7326eaf700edef3_9.png)

So we're going to look at a lot of these A curves。 So let me walk through this a little slowly so you kind of internalize in your head what's going on here。

 So this is a topology with5 A Ss， A to E。And I'm showing you here the relationship between。

These As where I have this directed I for provider customer。

 And so you can see in this graph we have a bunch of provider customer relationships。

 and then I have a different Ioid edge， which I don't have any in this right now。

 but we would be using this other type of edge to denote a peering relationship between two As。

And just to put it up there。 So you have it。 Remember， customers pay。

 providers and peers don't pay each other。So in this example， D is a custom of B。

 B is a provider to D。But at the same time， B is a customer of A。 A does not have any providers。

 It has multiple customers。You could map this to D could be Berkeley， D could be regional。

 California， ISP。 A could be a global AMD。So if I looked at this graph。

 I would say that DNE are sub As。They don't have any customer yeses。And A， B。

 and C are transit assetss。Because they're carrying， for example， B。

 is carrying traffic between D and E。Is carrying traffic between B and C。And in general。

 when we draw these graphs， we're going to draw star as at the bottom and increasingly larger transit as at the top。

 So there's kind of this hierarchy。Yeah， and so， in fact， inside， if you look inside A T。

 they have portions of their network where they have directly attached hosts and directly attached customers。

 but they are also providing transit。 And so typically， we would call those transit。

 but they are playing the role of mo。Not necessarily no。So on this figure here。

 I'm going to say that I think it would be a great idea for B and C to have a peering link or to have a peering relationship。

Anyone， and agree with me， anyone。One thing， say why。Exactly， so let's say DNA talked a lot。

And that traffic has to go BAC。Both B and C have to pay a to carry that traffic。So at some point。

 they're going to look at their traffic and say， this is quite expensive。

 If we just directly appeared， we would actually save money on both sides， both B and C。

Wind by putting in that peeling link。Okay， so this is why we have peering relationships。

It saves money for some of these transit assetss。Any questions on that？哎。



![](img/9472cf10abb0617fa7326eaf700edef3_11.png)

So moving forward， let's go back to this kind of A graph。 In fact。

 is you wouldn't have an AS S graph that looks exactly like what I have up here。 Instead。

 you would have one that looks more complicated like this where you have a large number of these As at the top。

 And the reason is largely for geopolitical reasons Nobody wants to have this one global layers that is an American company or an Asian company。

 every country wants to know that they have subset of options that they are not dependent on one。

Single administrative entity。 So we tend to have a large number of these As on the top。

And all of these as on the top will peer with each other。So these are as we call Tier 1 As。

 They at the very top of the hierarchy。So what defines the tier 1 A S is it does not have a provider。

And it with all other tier 1 As。Beyond that， there's a little bit of kind of informal notion of what makes you a tier 1 A S。

 Typically， if you look at the characteristics， these two things always hold。

 You don't have a provider， which means that you never pay anyone to carry traffic for you。

And you peel with all the other Tier1 yearss。Sort of informally， if you look at them。

 they tend to be across at more than one continent。

So you typically not have a tier 1 A that is in only one continent and they tend to own these kinds of transocic links that go transatlantic links。

 transspecific links， These are very expensive。 they take care to manage。

 So the point at which you own and operate those links you've kind of graduated to be at Tier 1 AS examples。

 you know you'd probably heard of them AtTNT and Verorizon obviously the U ones we all know in Europe。

 British telecom， Deutsch Telecom in Asia， Singtel N TT。

 those are some of the ASs that people would consider Tier1。

This is kind of the context now that we've set up for inter domainomain routing。

 Everything is going to be。We're going to talk about how we select parts and routes is going to be in the context of this kind of。

Set up this ecosystem of A Ss and business relationships。 So any questions before I move on。Yeah。

not necessarily， we use the term interchangeably。 an auto you can be an ISP without， okay。

 this is in the weeds of the details。 so don't worry about it from an example perspective。

 but you can be an ISP without being an autonomous system。So you could， for example。

 say that you're in a Google part of California， where there is no connectivity。

 And so you're going to be an ISP in the sense that you go set up infrastructure and you provide connectivity to the people in that area。

But actually， you just get a prefix from AT AndT。 You don't have your own autonomous system。

So that's a little bit just come， you know。Differences in the practice。

 But the way we'll be using it IP and E S， you can think of them as equivalent。Yeah。

So all the Ti1 A Ss will connect to each other。In a foot mesh。Any other questions on this？

That's the red link on top。Yes， a lot all the time。 So as a Ti1 A S。

 certainly you would like it if these lower level As don't appear and you they send all the traffic through you。

 They can't stop you from。EveryS acts independently in making those business relationships。

So there you can block people from peering。That's an interesting question the questions would you call someone like Google and AWS tier 1 A not they have the footprint and the scale of a tier 1 A。

 so they have the global networks。 They have the transit links。

 typicallyy we don't because these cloud providers don't provide transit。

Meaning you go through Google's network if you're going to Google or from Google。

But Google will not carry traffic typically to go between AW as and Azure， for example。

 And you can do it on top。 but that's not a service， they said。

So you can't sign up with Google the way you do with ATMD。

And there's no technical reason they couldn't do it。 It's just not the business there。And yet。

Any other questions？

![](img/9472cf10abb0617fa7326eaf700edef3_13.png)

哎。So where we're going to go from here now is if you have this ecosystem in your heads。

 we're going to start to design what that interdooma routing should look like。

 And anytime we talk about， we're going to design something， we have to start with what are good。

So what are the goals for inter domain routing In the context of intra domain routing。

 we had these very clear goals。 We said we want valid routes and we want least cost route。No loops。

 no deads and least cost。 in the context of inter domain， we still want all of those things。

 We still want valid routes。You never want to go that。Not a good idea。

 but we have two additional goods。Any thoughts？Okay， so stay within your system。

 I'm going to say that， yes。Ruce cost。Anything else？Yeah。

 so that is the big one though I'm going to call it what we call as policy。 so the two goals。

 one is scalability because now we are talking about routing at Internet scale。

 this is not routing within a single domain。 we are literally talking about all the billions of hosts on the Internet。

 That's the job of interdomain routing。 But the second goal is。

 you know what all of you are getting at， which is what I'm gonna to call policy。

 but it's a slightly lu guozi term at this point。 we make it more concrete。 a few slides from now。

 but think of it as meeting the business goals of the operator。

 which could be to mostly to save money or to make money。So let's get to scaling。

 And I'm going to go through this a little fast because I think Murphy touched on it a bit bit， yep。

We'll get to that hold that thought in just a minute where you're absolutely right。

 different countries will want to run their networks in their own way。

 I'm going to say that they want to have their own policies and we'll talk about how they get to do that in just a few slides。

Okay， so let's talk about scaling first。 What is the scaling challenge。

 It's simply that if I'm a goter on the Internet， give me any destination。

 and I have to know how to forward。 I have to know how to。

Find that next hop and send the bucket on its way。Nive solution， we've talked about this。 you know。

 you could have an entry for every one of the2 to the 32 IP addresses clearly that would not scale。

 and Muphy went over this。And so Murphy in his last lecture said。

 the key to scaling is how we do hosted dressing。

![](img/9472cf10abb0617fa7326eaf700edef3_15.png)

And also said the way we do host addressing， if there's one word you should remember about IP addressing。

 It's hierarchical。 It's hierarchical in the format， in the structure of the address。

 It's hierarchical in how we allocate the addresses。 And finally。

 it's hi We're going talk Mo St on those first two points。

 The last point is what I'm going to try and elaborate on today。

 which is how that hierarchy leads to gouting scalability。So just a quick recap of his lecture。

 remember， IP addresses is 32 Bs。 You can divide them into network prefix and a host suffix。

And the way allocation or the way we hand out addresses。

 all the hosts in the network will share the same prefix。

The important thing here is I can represent all the hosts in that network by just a prefix。

And he also talked about how we have this dotted coordnotation where I'm going to have something like a slash 23 to tell you what the prefix。

In this address is。For my convenience in this lecture， I'm going to use。

 it would be slash 16 rather than trying to readed out numbers。 Otherwise。

 I always read them out wrong。But this is， again， the structure。

 the hierarchical structure of an I address。Any questions on this。Okay， great。

 So what is key for inter domainomain routing is you have to realize that destinations in inter domainoma routing。

 they are now prefixes。So in all the loing we've talked about so far， distance vector Li state。

 a destination was the host address， the full host address。In inter domainoma routing。

 our destination is going to be a prefix。

![](img/9472cf10abb0617fa7326eaf700edef3_17.png)

Which represents all the hosts in that network。And why does this lead to scalability。

 It should be pretty clear if you look at a topology like this。And we said， LB L， LBL had a。Slash 16。

 you know， xtt Y and UB had a slash 16 of P dot Q。 And they're both customers of AT And T。Well。

 if you go look at a gouting table in Verizon's network。It just has to have two entries。

One for each prefix。This is already a massive improvement。

We've basically aggregated all of those host。 You could have had two to the 16 horse in LBL and 2 to the 16 in UCB。

Instead of inumigating all of them， I just have to store two prefixes。

AndThis also tells you how we enter domain roing， how we're making this scale。

 The prefix is going to get you to the final domain。To Berkeley or to Albia。

And then only within that domain， you're going to worry about getting to the exact host。Is this。

Makes sense， Re。

![](img/9472cf10abb0617fa7326eaf700edef3_19.png)

The second aspect of why hierarchical addressing helps is that the allocation is hierarchical。 Again。

 Muphy had this slide where he said a dress assignment， you know。

 you get from I gives out prefixes to regional registries that give it out to organizations like AT&T that then you keep subdividing your prefix space as you allocated。



![](img/9472cf10abb0617fa7326eaf700edef3_21.png)

![](img/9472cf10abb0617fa7326eaf700edef3_22.png)

familiarm。Why does this help me going back to the example we had。Here， I could have said， well。

 A T And T could have said LB L and Bekeley are both my customers。

 Instead of giving them these completely destroyeding prefixes。

 I have this address space that's slash8。A dot something。

 I'm going to go and hand out A dot B to LBL， and Bkeley gets an A dot C。

And so what happens to Verizon St。It now just has to store one entry that says。

 if you A dot anything， just go to AT and D。So there's two slightly different forms of aggregation that have happened。

 The first one was just saying I'm aggregating all the host addresses into one prefix。

And now I'm saying I'm going to actually aggregate prefixes into shorter prefixes。And so。

 we're getting kind of。This benefit from exploiting hierarchical addressing。

 There's another benefit to hierarchical allocation and addressing。 So let's say how UCSF came along。

And is given the prefix A or D。What changes a。Does anything change？No， right。

It's a local change within AT&T's network。 Theguyon doesn't even need to know about it。

So you get all this yet another level of scalability。 You don't send updates when you don't need to。

So we like hierarchical allocation because of that。

 hierarchical allocation and dressinging enables a。



![](img/9472cf10abb0617fa7326eaf700edef3_24.png)

Learn that lesson in your head。It's not perfect， though。

 And the reason it isn't is because ultimately， in order to get aggregation。

 hierarchy in addresses has to match the hierarchy in the topology。



![](img/9472cf10abb0617fa7326eaf700edef3_26.png)

What do I mean by that？ Let's go back to this picture here。

And we done beautiful hierarchical allocation and hierarchical dressinging in this example。

 It matched the topology we had。Now， let's say that Albia feels like they， you know。

 they don't want to be dependent on just one provider。 They really can't afford。

And any kind of outage。 So they say， I'm also going to sign up with Verizon as my providers。

 I'm going to have two providers。This is something we call multihoming， it happens all the time。

Any E， S or enterprise that is very sensitive to being having outages might multi home。

 They will go to different multiple providers and say。

I'm signing up with both of you for connectivity。 What happens to Va guysson's forwarding table in this。

If I did nothing， I would just send my traffic to AT& T， which means my red link is going unused。

 which never makes sense。LDL paid for that link。 They want it used。What。

 what would the guys have to do， They would have to change their voting entries to make this work。

Yeah， exactly。 You would have to add yet another entry that says if you're going specifically to A ort B。

Then you need to go over this red link。Anything else that has a prefix a you go。To attend。

When we talk about IP routes we're going to talk about how we implement this prefix matching。

 we call it longest prefix matching to decide which of the two links you should go out on。So。

 but the thing to note here is that when we do multihoing， it limits。The efficiency of a。

And that's because we're breaking this assumption that hierarchical address allocation matches maps onto a topology。



![](img/9472cf10abb0617fa7326eaf700edef3_28.png)

， so IP addressing and why we get scalability， aggregation is what gives us routing scalability。

But at the same time， the problem is aggregation can be broken by multihoing。Okay。

 where mother goinging again means you've connected to more than one provider。

And so where we end up at typically is kind of just where how the two factors play out。

 So on the internet， you will see some providers that worry a lot about multihoming making their tables larger。

In certain parts of the network， there isn't much multihoming。

 So you get very nice aggregation and scalability。There's no solution per se， to multihoing。

It exists。Causes us some scaling challenges。In here。



![](img/9472cf10abb0617fa7326eaf700edef3_30.png)

Yeah。Great question。Should we have given LB two different prefixes。We could have。 right。

 That's your question。 And one， you advertise  one Px to Verizon， another one to ATMT。

You totally could you're losing something there。 What is it。

The thing you're losing is that for any given address， you don't have the redundancy then。

So let's say LBL had A dot B and also had B dot Q。If I now have a server that was given the I address。

 A dot B do something。If8 goes down。You can't reach that server， even though I have a as a provider。

You could then do tricks later on to say， I'm going to give this over two addresses。

 and I'm going to go， you know when we talk about the DNS。

 we can talk about then you can have the name LBL dot gov map to two LP addresses。

 but that's kind of solving that problem at a higher level。Did that make sense， to。



![](img/9472cf10abb0617fa7326eaf700edef3_32.png)

So recapping scaling， a gota must be able to reach any destination。

 we don't like the naive approach of enumigating all destinations。

 and so instead we have hierarchical addressing。Where you have an entry for a range of addresses。

Hyarchical addressing is key to scaling。 You know， we talk about scalable routing。

 It's clearly the addressing that's making the routing scalable。

So the key to why the Internet is scalable has more to do with addressing than withing per。



![](img/9472cf10abb0617fa7326eaf700edef3_34.png)

Any questions before we move on to Paul？ so let's talk about， you know。

 we said the goal for inter domainomain routing was to enforce policy， to allow operators。

 A operators to enforce policy。Policy is a sort of nebulous term。

 So what do I mean exactly by policy， What we're going to see is that。

A policy as an administrator's preference for what kind of parts they they like to see on the Internet。

And the aral A S wants their freedom to pick that out based on policy。

 going back to an earlier comment， every A S has their own notion of what policies they want to implement。

 And just to get to it， you know， what do I mean by policy， an A S。

Examples of A S policies would be things like， I don't want to carry this traffic coming from this A S through my network。

That's a policy。 But maybe it's your competitor。 Maybe you don't like the customers they serve。

 Maybe you don't like the content。 It's really whatever reason。 No one cares what your reason is。

 That's your policy。 You don't want to carry that A。Different policy could be。

 I would prefer it if my traffic could be carried by S number 10 instead of S number 4。

 That's a preference over which all A is I would like to go through。Or under no circumstance。

 you know， do I want to go through as 54， or whenever possible， I would like to not go through。

Those are all examples of policies in。The Internet context and in interdomain routing。

 we say you can implement whatever policy you want that we do not constrain the policies that E implement。

 So you could imagine a crazy policy where E says on Mondays， I want to go this way。 on Tuesdays。

 I want to go that way。 That should be doable in an interdomain routing solution。

The thing to take away is。None of this has to do with least cost parts。

We're not talking about having one global metric， and we want a least cost path based on that metric。

 That's just not what's driving without selection。So if I said， oh， everyone can do anything。

 you know， it sounds like the wild。 How do we ever make progress， We do talk about typical policies。

 what are the typical policies that all As want to implement and。F， they make a lot of sense。

 They just common sense that this is what A S is want to do。

 And those get basically two principles for typical policies。

So if I'm an A S and I am in the business of moving traffic around。

 the policies or the principles I would make sense to me come down to money。

 And the first one is that if you're an A S， you shouldn't accept or you typically don't accept to carry traffic if you're not being paid。

This is， why would I be。Investing in all that bandwidth and carrying traffic。

 if no one's paying me for it。Does that make sense？So what that means really。

 is if you go back to those business relationships of customer provider and peers。

The only reason I would carry traffic is if it's going to or coming from a customer。

One end of that traffic has to be to a customer。 Otherwise， I'm not getting paid。

So my principle or that drives my policies is I'm not going to carry traffic unless I get paid。

 which means I'm only going to carry traffic if it comes form or goes to a customer。

The second one is。That when I send traffics， or the first principle was about when somebody sends me traffic and asks me to carry it when I' am I going to say yes。

The second one is when I choose to send traffic to someone else。In deciding where I send my traffic。

 I want to either make money or I want to save money。

What this means in turn is I'm always going to prefer， ideally。

 I would like to send traffic to a customer because they pay me for it。

But if I can't send it to a customer， I'm going to prefer to send it to a peer because at least that's free。

And my last resort， the thing I will do only when I have no other choice is I will send it to a provider。

And again， this is all about where you send traffic to a question。什么。Okay。Does that。

That comes from or goes to a customer。So if we're going to get to that in a minute。

 But the answer is， if the traffic came to me from upia。Right。I would look at that traffic。

 and I would say， should I carry it， The answer would depend on where it's going。

 If it's going to a customer， then I would， I would carry it because my customer is going to pay。

So what the implications of these policies are is kind of interesting because what it tells us is if you look at the ASS graph。

 not all parts on the AS graph are valid just because I have a connected graph with edges。

 doesn't mean all parts are valid Instead the parts that are valid we say roing follows the money。



![](img/9472cf10abb0617fa7326eaf700edef3_36.png)

A path is valid if it makes sense in terms of how money flows along that path。跟。

So let's look at this example， if I said here are two parts， these two blue parts。

Do you think this is a valid path from an inter domainoma。Perspective。

 when I think about these principles of。How money flows do we like this path？Yeah， let's look at it。

 for example， from the perspective of E。Is getting paid by D to carry that traffic。

 so it makes sense。Is not getting paid by B。Carring tracking between D and B。

 but that's fine because it's getting paid by D。The same is true for B。You could say， well。

 D is paying， but D has no choice。It's a stus。 It has to pays provided to carry traffic。

So when we talked about， I only when I send traffic。

I first try a customer link while D has no customers。Then I try a peer link。 where D has no peers。

 So then。I fall back to a provider link。 D has a provider。 So it's sending it to you。Yeah。

 so why in practice is do we have these cus on top， right like this A S at the very top。

 In this example， there's probably no good reason why you would want to have Q。 But in general。

 the reason is because a smaller A cannot appear with every other A S in the world。 that's just。

 you know， if you have an A S that covers， let's say California。

If that A S had to single handedly connect you to every other As in the world without one of these Tier1 As。

 they would have to have relationships with every A S in Africa， in Europe， in Asia。

Which that's just not what their business is。 right。 That's a physical link。 So instead， they say。

 I'm just going to go to A T and AT And T is feel better。Right， so the star base is here， typically。

 the principle we are invoking， you could say is where do I send traffic and you try。

 you don't have customers， You don't have pills。 So you send it to the providers。

 So it's kind of like a redundant application of the principle。It doesn't violate it。

 It's just not very interesting。What do we think about this open pot？Is this a valid one？

Does going follow the money here？Yeah， so everyone saying no， right。

 And you see this by looking at ASB。EB is carrying traffic between A to C doesn't get paid by A。

 doesn't get paid by C。 So why would you ever do that， Not a great idea， So traffic not allowed。

This is pointing at a more general rule that As will provide transit between their customers。

You're not going to provide transit where there isn't a customer on one end。

And peers are not going to provide transit between other peers。

 So you're not gonna to have an A S that is taking traffic from one peerer and sending it to another peer。

Why would you do that？What do we think about this book？Even worse than。

 B is not getting paid by a and then is getting charged by Q。

This would be a sneaky thing for you to try to do。 They've tried。

If you set up your BGP policies correctly。You would not be doing this。So an。

 this points again to a more general rule that an A S will only carry traffic to or its customers over peering link。

I'm never going to take traffic from a peer and send it to my provider。What about this one？Bad to。

 In this case， F is getting charged by A and charged by C。This is effective。

 This is like ATMT sending their traffic to Berkeley and saying， hey， can you go it to Hizon。

And then Bookley gets charged twice。So we， we call this property， and we'll get back to it later。

 The results are value free。 You never go down the curve to a customer and then go back up。

It just doesn't make sense。

![](img/9472cf10abb0617fa7326eaf700edef3_38.png)

So hopefully， now when we talk about that administrative preferences of policy shape into domain routing。

 I hope you understand what that means。行。The key thing here now。

 we want A S is to have the freedom to pick these routes based on their policy。

They have to be able to do this with two properties。 One is autonomy， and the other one is privacy。

 So let's talk about what those mean。 When I say A S is one autonomy。

 What I mean by that is that every A S should be able or have the freedom to pick its own policies。

And it should be able to implement that policy without coordinating with any other ears。

So if I want to do Monday this way， Tuesday， that way。I get to decide that。

 and I don't have to ask my other As to cooperate。That's autonomy。 I also want privacy， S N S。

So As are very sensitive to things like telling the world about what their business relationships are。

Sometimes they don't even like to talk about who their peers are， who their customers are。

They certainly don't want to tell everyone what their policies are。

And I have this sort of explicitly。 they don't want to explicitly announce these choices to others。

 Why Why am I kind of saying explicitly a bit of a weasel word there。Yeah。Yeah。

 because when you make a policy， it determines how your traffic flows。

 so the out impact of those policies is kind of visible if you look at how traffic flows on the internet。

 so you could kind of try to reverse engineer what business relationships exist and you know what policies different As are implementing by sending enough traffic and observing from different vantage points and trying to give engineer。

 there are companies that do this and a lot of research papers try to do this to understand what ASs are doing。

But they don't want to have to explicitly announce their policies。And think to note。

 your policy is what we are trying to achieve。implementing these policies is the goal of interdoamine gouting。

Doing it with while respecting autonomy and privacy， these are requirements on how we do。Yeah。

Rightai， so in Tro to recap， the A S topology reflects business relationships between As。

Those business relationships， in turn， impact what routes we consider acceptable。

And so interdooma routing， when we design an interdooma routing solution。

 we have to make the goal is to make sure we can support those policy choices in a way that respects autonomy and privacy。

And so BGP， or border gateway protocol is the protocol on the Internet that does interdomain routing。

 That's what we're going to be studying。 It is certainly not the only way to implement interdomain routing。

 but it's kind of it stood the test of time。 is how we've been doing routing on the Internet since whoever。

 So it's still deployed everywhere。

![](img/9472cf10abb0617fa7326eaf700edef3_40.png)

Just a little bit of background here on BGP。 The idea of routing on a graph。

 everything we've studied with distance vector and Li state。

 The fundamentals of that were rooted in computer science a long time ago， long before the Internet。

 things like ditros and down。 This idea of how you route between autonomous nodes that have business policies。

Just never existed before the Internet。And， in fact， the first 10 years of the Internet。

 it did not exist。 The Internet was one。Government run network。 No one worried about these things。

 So the development of B GP actually came fairly， you know。

 late in the sense that it followed the development of the Internet。

 and B G P was starting to be specified and deployed。

Roughly at the time when the US government said we are no longer runningning the Internet and handed it over to commercial entities。

 So it was a little bit of learn as you go and build as you go。So because of that， as you'll see。

 BGP is not a perfect protocol， you know， there are certain things that I think if we got to wipe the slate clean。

 we would do differently and we'll talk about those。But on the other hand， it's proven effective。

You'll see lots of research papers。That talk about， here's a better way to do B GP。Invariably。

 when you poke at them， they seem to do like about 40% of what BGP does。So， you know。

 theyre simpler than BGP， but they're not really as general or powerful。

 or they do by the time they do everything BGP does， they tend to be not that simple anymore。

So B GP is the thing we， we all in the research community。 We love to try and。Beat vgip。

 but it's proven to be a pretty difficult goal。

![](img/9472cf10abb0617fa7326eaf700edef3_42.png)

嗯。Let's take it two minute quick， and then we'll actually get into the how inter domainoma routing works。

Okay， let's let's actually design into domain out now。

 So a quicklycap of our setup here is we have a graph。 notess in the graph are Es。

Destinations are I P prefixes， and links represent both physical links and business relationships。

And we've talked about what we kinds of parts we like。 this kind of money。Follows， going。

 follows money， kind of parts and so on。 Let's talk about how we actually implement that。

And so when we think of how we're going design inter domainoma routing。

 we kind of we've learned already。 we have these two canonical approaches to routing that we've discussed with link state and distance vector。

If you had to choose one as your starting point， it's not going to solve all the problems we need。

 But if you had to pick a starting point， which would you pick。And one。Yep。Yeah， exactly。

 We would pick distance vector。 And the reason is we don't like Li state because Li state offers no privacy。

 You have to broadcast your neighbor information to the entire graph。And we said。

 yeses don't want to reveal their business relationships。Even worse， it offers no autonomy。

 The only way L state works is because we all agreed on what metric we're optimizing。For that。

 I have to reveal my policies to everyone so that they can say， oh。

 this is how this A S would pick parts。Otherwise， links say it doesn't work。So， distance vector is。

More attractive starting point。The problem is it wasn't designed to implement policy。

 It was also doing least cost routing the hook that we're going to exploit a distance vector to make it do what we want is the fact that distance vector is working by advertising per destination。

Costs or per destination， part selection。And so that's going to be our hook。

 I' make it clear in a minute， but it's going to be a hook because it's going to allow us to say on a per destination basis。

 I'm going to hear advertisements from other yess and on a poor destination basis。

 I'm going to implement some kind of policy in which routes I think。And I don't have。

 I do it locally。 I don't have to reveal it to everyone。That sounded big。 We'll get to。

How that makes sense in a bit。 So BGP extends distance vector in order to accommodate policy。

 The way we're going to talk about how BGP works， because BgP gets very detailed very quickly。

 So instead， we're going to talk about going from distance vector to BgP at kind of an approach level and how policy is implemented。

 And then next， lecture show we' are actually going to get into the details of。



![](img/9472cf10abb0617fa7326eaf700edef3_44.png)

PGP messages and so on。 But at this point， we're still in the general approach。

SoThe basic idea behind B G P， Fu member distance vector。 What was the basic idea。

 I tell all my neighbors about my least cost path to every destination。 So for each destination。

 I say this is my least cost path。And then I listen to what my neighbors tell me。

 and I pick the best route to every destination。Based on what I hear。

And we iterate between those two。We're going to do the same exactly for BGP so in BGP。

 we are going to say that an AS so now a node is an ASS advertises its best route to a prefix。

 We call this export， This is BGP terminology for advertising so an AS will export its best routes to all its neighboring As。

And at the same time， each A is going to listen。To all the advertisements it received。

And it's going to select what it thinks is the best go for each advertised prefix。

And we're going to go back and forth between those two。 This should sound very familiar to you。

 This is what this inspector did。 The change is that policy is going to be。

Implemented in terms of which valves you advertise and which valves you select。



![](img/9472cf10abb0617fa7326eaf700edef3_46.png)

跟。So when we say B GP is inspired by a distance vector， their three similarities is really。

 One is that we're doing these per destination advertisements。Destinations for BGPR prefixes。

The second， there's no global sharing of network topology information。 Instead。

 what we have is this iterative， distributed convergence process。At no point am I telling everyone。

 these are my neighbors。 these are my policies。That said。

 we are going to have to change distance vector。 and that four crucial differences。

I think we've kind of touched on a。

![](img/9472cf10abb0617fa7326eaf700edef3_48.png)

Most， if not all of them， but let's compete them。 So we make sure we're clear。

The first is that B T P may aggregate destinations。 So if you remember in distance vector。

 you got an advertisement that said， for this destination， here's my。Least cost。

At no point did I mess with that destination， right。

 I just took that destination and I updated my least first path， and then I advertised it back out。

I didn't tamper with what that destination was。 In BGP， we do do that。 For example。

 AT And T in this context， might hear advertisements from LBL， UCB and UC SL。

It's not just turning around and advertising those prefixes to Verizon。Instead。

 it's aggregating them into a shorter prefix。And advertising that shot of we。So for scalability。

 BGP may actually aggregate routes and destinations。Ful prefixes。 That's one big difference。

 Does that make sense。Any questions on that or anyone want me to repeat it。



![](img/9472cf10abb0617fa7326eaf700edef3_50.png)

Okay。The second we've touched on this again， very， you're not necessarily picking shortest parts or least cost parts。

And so BGP， you're going to select the best route based on this general policy that we said every can implement。

And that policy is not optimizing some well agreed upon cost。

So it's perfectly reasonable in BTP to have a topology like this。Where note 2 is going to say。

 I'm going to reach one by going through 3。No2 prefers the path 2，3，1 over 21。That's totally fine。

 And PGB。This should cause you concern。 What's the immediate thing you think of when I tell you I can go 2。

3，1 instead of 2，21。What's the thing we've been worry about so much in this since。Loops。

 at least cost part， resulting had this beautiful property recommending in this cost at every step。

 And so I don't get into loops。If I can't rely on that anymore。I could have oops anywhere。

So how do we actually avoid loop， any ideas？Very different approach from。

All the things that you know， spize and poison poison rivers forget all about。

Go all those techniques。 Is there something completely different you could do to avoid loops。



![](img/9472cf10abb0617fa7326eaf700edef3_52.png)

Yeah， keep track of what that part is。 you should have this slight thought of why didn't this vectoror do that。

What BGP does is instead of doing distance vector routing， it does what we call path vector routing。

And so， we here。When you advertise， you also advertise the path。

 the entire A S level path to that destination。So for example， here， when A advertises to B。

 it says I can reach this destination。V the path E， because you're the onlys。

When B forwards are on to C， it says I can reach the destination along the path B A。

So when C turns around， you know， data goes from C to B to A， but if。

My slides here all mess up the key idea let we recap it the key idea is you advertise the entire part so the distance vector in distance vector routing we sent the distance metric for destination in path vector we're going to send the entire AS path associated with the destination Okay so it's going to do what we did and loop detection now is when C turns around and advertises to a。



![](img/9472cf10abb0617fa7326eaf700edef3_54.png)

It's going to send an advertisement that looks like I'm going to the destination along the path CBE。

So it's actually trivial for E to look at that advertisement and say， I'm on this part。

 This is a loop。 and it throws that advertisement a bit。So you're doing loop detection。

Any questions on this？Great question。 Are't we revealing something about our policies when we do this。

We are。But this， this is kind of the part of exposing your policies that's inevitable。

 What you are exposing is the path you've chosen。 You're not exposing what parts you heard and which parts you rejected。

So you'll right that there is some leakage budgets。I would argue it's almost fundamental。

That you have to reveal this。Any other questions？

![](img/9472cf10abb0617fa7326eaf700edef3_56.png)

哎。So just to recap the key idea advertise the entire path， different from distance vector。

 the benefits loop avoidance is easy。There's another benefit that I actually。

 we don't really know how often this gets used， but it is certainly possible is that you can look at the entire path and base your policies on the entire path。

 not just your next hop。Or not just your cost。 So you could say， oh， this path is going through。

 some country you don't like。Along the way。 And so I'm not going to pick it。

 That's actually something you can do with bejiping。



![](img/9472cf10abb0617fa7326eaf700edef3_58.png)

And the last difference between B，GP and distance vector is what we call selective route advertisement。

 So in distance vector， when the way we've been talking about it all along。

 we've been saying I receive an advertisement for a destination。 I update my least cost。

 and I forward it on。You never had in distance vector， a node that receives。

An advertisement to a destination and says， I don't like this destination。 I'm not advertising it。

That's not how the context we were operating in for intra domain about。

 But that's exactly what we're going to do with BgP。 So in BgP for policy reasons。

 and A S may choose not to advertise the destination。

So I can have a graph like this where B here is from A。AndAbout being advertised and says。

 I'm not going to advertise it to C， because if you advertise it to C。

 you're going to be asked to carry traffic to that destination。 And if B doesn't want to do it。

It is not going to advertise it。Do you see a problem with that。Not that were think every we ask can。

Choose not to advertise certain destinations。It just drops it。This is。Should be。

 a serious cause for concern， Because what this is telling us is reachability is not guaranteed。

With P G B， even if the graph is connected。That means I have links and I can draw this connected curve。

Reachability is determined by whether all the right As along the way chose to advertise path。

Or chose to advertise that prefix。This should sound concerning like how is the internet working。

 we'll get to in a few slides about why in practice。

 most of the time unless we're talking about bugs or misconfiguration。

 why this is not in fact a problem。

![](img/9472cf10abb0617fa7326eaf700edef3_60.png)

So just to recap the four differences， BGP can aggregate destinations and routeuts。

 which we can do in distance vector。 Select is not based on shortest path。

 You advertise the entire path， not just the waste cost。 So it's a path vector protocol。

 and you are selective about which prefixes you choose to advertise。呀。



![](img/9472cf10abb0617fa7326eaf700edef3_62.png)

![](img/9472cf10abb0617fa7326eaf700edef3_63.png)

Right， so typically， you lose some information when you aggregate。

 because what you would be telling Veron is all of these prefixes。Roout it through me at T。

 and you kind of lose the subtle differences between the distance form AT T to maybe LBl。

 UB and UCSF。 You lose that one could argue。You know， that。

That was the only part to those prefixes in any case。 So theres not。 the downside is not that good。

Any other questions， here？Right， so I think the， the question is in the multihoming example we had where we had a link from LBL to Verizon。

And we said Verguon has two entries in its forwarding table。 One is for a slash 8 for 8。

 and the other one would be a slash 16 for8 do B。And so how would Vaizon choose how to send traffic between those two。

I that the。哎。Verizon is not losing any of its own re choosing。Yes。

 so in in that example that we had set up the multihoming example， that particular one。

 Verizon was not using its own range。For LB。Both way， you could do it both ways。

 It really depends on whether you want two parts coming in for that for one given prefix versus having two different prefixes。

 You could have LBL could have also taken a prefix from the guys in it。

 It's just a question of what you were trying to achieve with the multihoming。

And in this context where LBL is asking Verizon to kind of accept its。Vote to8 or B。

That's part of their agreement。 Part of what they're signing up for is you will advertise my prefix for me as a provider。

So it's a dumb thing。

![](img/9472cf10abb0617fa7326eaf700edef3_65.png)

Any other questions？

![](img/9472cf10abb0617fa7326eaf700edef3_67.png)

![](img/9472cf10abb0617fa7326eaf700edef3_68.png)

Moving on， any questions before on how B G P is like and unlike distance vector。

Okay so now let's talk about how policy is actually implemented in this context and so remember we said we have this usual iteration of I export certain routes and then I listen to what everyone's advertising and I import or I select certain routes Let's actually look at that a little bit in action because policy everything we've been talking about you know all these concerns about how money flows and so on。



![](img/9472cf10abb0617fa7326eaf700edef3_70.png)

Where it actually comes down to where it gets implemented is this question of what routes am I going to import or select and what routes am I going to export or advertise。

 So that's where if you look at the implementation， that's where policy lives。

 right So let's look at this example here where I have these As。

 And I have some destination prefix Some far out on the Internet 1，28 or3 or something。

And I have two parts， Both B and C have the ability to reach that destination。

So I have this green pot， and I have the blue pot。 Both of them are advertising these parts to it。

So A gets is listening。 It hears two routes being advertised。

To bots being advertised for the same prefix。It's going to pick one。Okay。

 that is our selection policy or about input。Step， and that's the step where we're going to inject some amount of policy。

In picking that policy， when I pick which one of these I'm going to take。

 what I am effectively determining is how my traffic is going to leave my network when it goes to that destination。

So here， let's say that A said I actually like the green pot。 So I'm going to choose the green pot。

What that means is that when I route， when a is given traffic or it carriess traffic 4，1。

28 do3 dot something， it is going to send traffic to B。So keep that in your head because remember。

 we said we like when we send traffic， we like to make or save money。So keep that in mind。But now。

 again， when I take that， I've selected that green pot。 That was my import policy。

I have another step of policy， which is now， whom am I going to advertise。Go path 2。And again。

 remember， when I advertise the path， what I'm telling the person I'm advertising it to is you can send me traffic。

 I will carry traffic for this destination。And again， remember， we said。

 I only want to carry if I'm going to make money by doing so。 So in this case。

 let's say that A decided it didn't want to advertise it to Q and it did want to advertise it to P。

So again， this export step of deciding where you advertise your parts。

That's another place where we put policy。Okay， so policy is imposed in how routes imported and exported。

I'm going to repeat this again you， a few times， because。It's intuitive。

 but we trip on it multiple times。 So import determines which part I'm going to use。

ItYour input policy dictates how traffic leaves your network。Your export policy。

 which is the question of which parts do I advertise。 It controls how traffic enters your network。



![](img/9472cf10abb0617fa7326eaf700edef3_72.png)

One last time， import policies， which parts should I use or which parts should I accept determines where traffic goes。

Because say you're choosing the route export policy。

 which is the decision about which parts do I advertise and where do I advertise them。

 determines what traffic enters your network or what traffic you going to carry。

Any questions on this？I've found it's easy to get confused because the import and export is kind of the opposite direction of traffic flow。

So when deciding what to input， you have to decide what you're effectively deciding is where your traffic will get sent。

And then you think about how the money flows。

![](img/9472cf10abb0617fa7326eaf700edef3_74.png)

So we're going to have these important export policies and we've talked so far about you know you have these business relationships and you have these principles around when you send traffic and receive traffic where does the money flu and so on。

 all of that understanding of the language we use for that comes from work done by Alician Gao and Rexford。

 they were both researchers at AT&T labs when they did this work。

 So it was in the early days of the internet where all the As would kind of just setting up their networks since I'm ad hocwe and nobody quite knew what they were doing So they went out and actually surveyed a bunch of these As and try to understand what was in the heads of these network operators what they were doing informally and what they distilled from that what we call the Gao Xxford rules these are rules that capture common So they actually despite the name not rules you don't have to follow them but it's common practice in important export policies。

And basically， they codify or you， show us the pattern behind the scouting follows money。

Intuition that we've had。 So so far， we've been saying routing follows money。

 It's all been very intuitive。 The Ga expert would translate that intuition into import and export policies。

Theyre also very useful because you know we've been saying so far， I'm not sure it's reachable。

 different As can choose different policies。 The GO expert would tell us if every A on the Internet follows these rules。

 we can start to reason more formally about things like convergence。

 about things like reachability and so on。 So it's the closest we have to a more formal。

 vigorous baseline for interdoomain gouting。She doesn't say mean that an A S cannot go do some crazy thing They can。

 but at least this gives us a baseline that makes sense。And as far as we know。

 all ASs follow the G expert ruless。

![](img/9472cf10abb0617fa7326eaf700edef3_76.png)

So with that， what is the Gag expert rule， This is， again， repeating that intuition。

 This says when I hear routes being advertised to me， when I select them or when I import them。

 the rule I'm going to follow is I will always prefer a route that was advertised to me by a customer。

Over advertised by peer and the peer over advertised by a provider。

This directly follows the when you send money， send traffic， you either try to make or save money。

If you're trying to make money， you would always like your customer route。You're trying to save it。

Then you'd prefer pure over provider。And only when you have no choice， will you choose your provider。

In practice， A Ss will use additional rules。 So， you know， you might have， for example， many peers。

 let's say you had no customers， but you had many peers whoses route you could have picked。

So typically， what NES will do is they will apply the G expert rule and they'll say， okay。

 I heard the path advertised from these three ps。And then they'll have additional policies for how to pick amongst those。

And they'll do things like picking based on the performance of the path or you know。

 maximizing use of your network bandwidth and so on。 And when we get to the details of BGP。

 we'll talk about how they implement those。

![](img/9472cf10abb0617fa7326eaf700edef3_78.png)

But the cow expert rule is typically the first rule you apply。Similarly。

 Gg expert on the export side， the question again here was now I have routes for certain that I've selected for certain prefixes。

 Where and whom do I export them to。And so remember here again， when I export route。

 what it means is that I'm accepting to carry traffic to that destination。



![](img/9472cf10abb0617fa7326eaf700edef3_80.png)

So what is the policy we're going to follow？ So what the G expert who tells us is it comes down to this table。

And the question we're going to look at again is I'm going to export that route。

 which means I'm going to be asked to carry traffic to that destination。And we said。

 I only carry traffic if I get paid for it。How do you decide whether you get paid for it。

The way you decide whether you get paid for it。Is you look at who advertise that route to you。

Because that's going to be when you carry traffic， you're going to carry traffic。

To the person that advertised us out to you。So let's look at what those options mean。

 Let's say that you out here。 We have the one in the middle。 and I have a provider。

 A P O B and two customers， C And D。Now， let's say I had a part that was advertised a prefix that was advertised to me by a customer。

 So let's say in this case， that's C advertised a prefix to me。And now。

 my decision as my export policy。And remember， I'm only going to carry if I get paid。Is that I will。

 Who would I export this prefix to？Ex，So the question here is， again。

 without being advertised by sea。钟明。Should I export that route today。Yes， right。

 because I'm going to get paid actually， I'm going to get paid by both CD okay。

Should I export that how to eat。Think about them。I see some people saying yes， some people saying no。

Yes， because let's say I took that route from CNN， advertised it up to E。

So when I get traffic coming back from A to C， I'm getting paid to carry that traffic。C is being。

It is true that I'm also paying。But that is actually also the nature of being a provider。あ。

Requirement that I will only carry traffic if I'm getting paid， that is being met。

Should I advertise that prefix to B。Yeah。我上。They go to S and yes。

You would export to all of them because otherwise you have no guarantee that C is actually reachable by everyone on the Internet。

Because what if B was only connected to one x here and it's not connected to。

Some other part of the Internet。In fact， you definitely should， because。

Let's say that B has some customer X here。But above B， B providerdo is B is y。 let's see。

B is never going to accept to take traffic from why send it to me and go down to see。

Because that's going to be， you know， like B would get charged， B would not get paid。So in fact。

 you can't rely on B to connect you to the rest of the Internet。 you have to advertise it to it。

You will definitely get bid。 So if I advertise Cs go to A and A sends me traffic to C。

 I will definitely get paid for it by C。 There's a question about do I end up getting paid more by C than I paid A。

 And that's kind of a market dynamics the assumption generally is you figured out how this makes sense for you in terms of how the net money。

Ends up being and that I， you know， if you as an A S are paying a more than youre being paid by your customers。

You've probably not set up your relationships very well。Yes。And the typical context here is。

 you know， think of this as Berkeley。 And then let's say California A S and then AT& T。

 If this California A said I'm not advertising， Berkeley's go to the rest of the Internet。

Then but please in trouble them。So what this means is if my prefix was advertised to me by a customer。

 I am going to export it to everyone。And I'm fine doing that because my customers paying me to carry that traffic。

Everyone happy with this？What if that destination was advertised to you by a peer。 So now。

 let's say that B had advertised the destination prefix to me。And the question again is。

 whom should I export this route to。And again， when I export a route that means I'm willing to carry traffic to that destination。

谁。Customers。What about if I had a allowed advertised to me by a provider。Also customers。喂hy。

So if my provider advertises a prefix to me， that means that I will carry traffic to that destination。

Form C or D， which is fine。And this is， in fact， exactly what we want。 Let's say， you know。

 Facebook was somewhere out there in the world。My customers want to be able to get to it。

And they're going to pay me for it， so I'm finally the setup up。Any questions about this？

Understanding this is key。 So if you have any。Lingering questions about this。



![](img/9472cf10abb0617fa7326eaf700edef3_82.png)

Com once。So I said that the Gao expert rules are nice because they give us a certain baseline that we can make certain statements about how internet gouting works under the assumption that everyone follows G expert。

ItSo also kind of hard to see why someone would not follow Gex rules。

 when you look at kind of the history of outages on the Internet。

They tend to be because someone misconfigured their policy。

 And so they were actually violating cowx food rules when they didn't mean to。

So things like Berkeley。By accident advertised。About to Google to At。 And suddenly。

 all of Google's traffic comes through Berkeley。 They tend to be mistakes。

 If you actually configure your policies correctly。

You typicallyically everyone follows the go expert rules。

But so one of the properties we can talk about if everyone's following the Go expert is that all parts on the inter domainomain graph or on the S graph are what we call valley free routes。

And again， we've covered this intuition。 But what it's saying is if I took a graph where you know。

 customer provider links are going up in the graph and peers are going sideways。

Exactly what we've been talking about。 Then I will never have。

 Ill always have parts that are value free。 There's a kind of proof sketch that you'd see in the discussion section。

 but it's very intuitive。 Why would you have a value if you'd have a value if you went down to a customer and went back up。

 We said we don't like that。 It doesn't make sense。 Gaitz would prevents that。

Or you would have this kind of value if you went to a pure and then went back up。

Which means you're going over a free peering link and then going up over a link that you have to pay for。

 Again， go prevent that。 so we don't see that。 Okay。

 so all parts on this A S graph are what we call value free parts。 Theres a question。Yes， exactly。

 So the path， actually that's a well put。 The path you end up with is a combination of every A node on the graph enforcing that input and export policy。

So when I export a path to you， you can choose not to import it， not select it。

 That means I won't get traffic from you。 But when I export it。

 what I'm saying is I'm willing to carry traffic。 whether you then choose to exercise。

 my offer is your choice。Does that make sense。You don't。

So I exported all that I'm doing when I exported something I'mwill to carry traffic to this destination。

If some A S chooses not to send me， not to pick my path。

 the only way I would see that is I wouldn't get traffic to that destination from that A S。

But there isn't an explicit。 No， thank you。 Keep your part。



![](img/9472cf10abb0617fa7326eaf700edef3_84.png)

Any other questions？So the last thing point to make about the Gv expertford rule is what the Gav expert rule allows us to state is actually a fairly powerful statement about interdomain routing。

 which is that under two assumptions about the AS graph， which I'll get to in a minute。

 if all As follow the Gav Xford rule。And these go policies， then were guaranteed two properties。

 Reability and convergence。 Reachability means any two A Ss on the Internet can。

A guarantee to have a pot。 They can communicate。And convergence。

 meaning allvouchers will agree on that part。So all these things we said about， you know。

 each A S gets to implement their own policy， I can choose not to advertise a destination and so on。

This tells us if you follow the G expert rules。And under these two assumptions。

 which I'll get to in a minute， then we actually can make these。 were reassured。

 We can make these pretty strong claims about reach ability on the Internet。



![](img/9472cf10abb0617fa7326eaf700edef3_86.png)

And so what are those two assumptions They actually keep。

 The two assumptions one is that the graph of customer provider relationships is aic。

 There are no cycles。That means I'll never have a situation where A A is a customer of B。

 and B is a customer of C。 And then C is， again， a customer of A。

And if you think about what the implications of customer provider are in the real world。

 that makes complete sense。 And this would be saying。

Perkeley is a customer of Sonic and Sonic is a customer of AT T。

 and now ATT is a customer of Berkeley。 That should not make sense。 So， but if this assumption holds。

 which we would always expect it to， that's one assumption underlying the Gg expert conclusion。

 The other is that starting from any A。 You can always follow a chain of customer provider。

Parts up to a tier1 years。So I can start from any S AS in the world。

 and if I kept walking up the customer provider path。I will hit a tier 1 E。

 And then remember the tier 1 As are all pairing with each other。

So this should tell you why these two assumptions are key because the assumption that you have no cycles is what allows us to draw this conclusion about convergence。



![](img/9472cf10abb0617fa7326eaf700edef3_88.png)

That we will all settle。 know， You won't oscillate in a loop。

The assumption that we will eventually reach a tier 1 is what guarantees reachability。

 because this means you can always find a path where I work for my stub A up to a tier 1。

And then the tier1 will jump across a appearing link。To a tier 1 A connected to the destination。

 and then we'll walk。Back down the hierarchy to the st areas on the destination side。Again again。

 in section， youll go to。The arguments behind those claims are a little bit more。

 What is important to realize is neither reachability nor convergence are guaranteed if we are in the space of more general policies。

 There's actually been more formal， theoretical work showing that。If you have， you know。

 deviate from something like the Gaex foot rules or these assumptions， even a little bit。

 then all bets are off in terms of what you can say about convergence or reachability on the。

And you do an example in section where you see how routes can oscillate forever and never converge if you。

 if you're not limited to the go expert。

![](img/9472cf10abb0617fa7326eaf700edef3_90.png)

So with that just quick recap， policy is implemented by choosing which routes you import and which routes you export。

The Gao expert would tell us， you know， kind of common sense practice about which gos to import our export in order to make or save money。

 That's the underlying principle is， this is driven by how the money is flowing between these ears。

And if we all follow the cow extra rules， kind of good stuff happens on the Internet。

 we can rely on the Internet。To actually provide universal eability。Any questions。Okay。

 so next lecture， we'll get into the protocol detailed weeds of BGP and also move on to the data plan。

Thank you。

![](img/9472cf10abb0617fa7326eaf700edef3_92.png)