# UCB《互联网导论：架构与协议｜CS 168 Introduction to the Internet： Architecture and Protocols》 - P11：-10- Designing IP.2022 - GPT中英字幕课程资源 - BV1VcrrYUEL5

i， good morning， everyone。 Let's get started after recording issues topic for today。

 we're going to wrap up BGP and move on to designing IP and I'll explain what that means in a minute。

 just a quick recap of where we are。 if you remember in the context of B GP。

 we spent the last lecture talking about the highle goals， the high level approach and by and large。

 we didn't really get into the weeds of how the protocol works at sort of the router level。

 And so that's what the plan is for today。 quick recap of where we are。

 you know all of last lecture when we talked about interdomain routing。

 our model was a topology that looked like the one that's up here。

 which is what we call the AS graph or the autonomous system， Inter domainomain graph。

 where each node in this graph is one autonomous system。



![](img/d525653c4bea9a81a8605e4131d2a1f5_1.png)

And I hope you remember， but just to recap， you should now know how BGP works at the level of this ASS curve。

 we said destinations are prefixes。 each autonomous system advertises the prefixes it can reach and its path to those prefixes and each autonomous system listens to those advertisements and selects the routes it wants based on policy and we talked about these Gg expert rules for what those policies look like。

So at the A S level， you now know how B G P works。 The main challenge we're going to address today is that。

 of course， in reality， there is no such physical entity as an A S， per say。

 What we have is a network of routers and links。

![](img/d525653c4bea9a81a8605e4131d2a1f5_3.png)

And so the real challenge is how we implement that B G P A S level policy making when every single router is acting independently。

 So how do you actually do a distributed implementation of what we've been discussing so far。Okay。

 and in particular， within this graph， we highlighted that you have certain routers that are kind of special in the sense that they are border routers。

 which means that one of their neighbors is in a different autonomous system。



![](img/d525653c4bea9a81a8605e4131d2a1f5_5.png)

So wrapping up B G P means the main question we have left to discuss is how do we distribute distribute this B GP process。

 How do we make sure that all the routers in an A S are actually implementing what we were saying and A S was implementing before？

 And so sub questions are， know what's the goal of border routers versus interior routers。

 How do we actually integrate the intra domain routing with this inter domainoma routing。

 So the two finally have to meet together。And then what are the actual messages。

 protocol messages that are being exchanged between routeers in order to achieve this。



![](img/d525653c4bea9a81a8605e4131d2a1f5_7.png)

So one of the things you'll hear when you people talk about BTP is they'll say these routers speak BTP。

 This is just BTP specific language for a certain way of implementing the BTP protocol。

 What it means is you know when we talk about who speaks BTP。

 we're talking about which routers are advertising these routes。

 these different prefixes and the answer is that in BTP it's the border routers。



![](img/d525653c4bea9a81a8605e4131d2a1f5_9.png)

So the border outers are what we call B T P speakers。



![](img/d525653c4bea9a81a8605e4131d2a1f5_11.png)

OkayWhat does it mean to speak B2 B it means you implement the B2P protocol specification。

 So if you're looking for punishment， the entire B2P protocol spec is out there， you can go read it。

 It's many hundreds of pages long。 I wouldn't recommend but it's if you want to know all the goE detail So what it means when I say you implement the B2 P protocol It means you have code running at that route that implements that protocol specification It knows how to send out the messages that are in that specification。

 It knows how to receive them and what actions to take when you receive those B2P messages and that's what we're going to talk about today。

So specifies what messages B G P speakers exchange， both their syntax and their semantics。

 So what actions you take when you receive these BG P messages。



![](img/d525653c4bea9a81a8605e4131d2a1f5_13.png)

One point to highlight before going forward， I think somebody actually raised this last time。

 Not all border routers in an autonomous system have to speak B G P or have to actually run B G P。

 The canonical example。 And this is， again， what helps scaling on the Internet。

 Let's say you had a customer that only has one provider。

So it entire the entire autonomous system connects to the Internet to one provider。 So this is。

 let's say Berkeley， for example， has one provider。 It's AT&T。

 That's the way Berkeley connects to the Internet。 In that case， you don't really need to run BGP。

 And if you go back to Mophys lectures on default routes and static outs。

 we're going to use the same trick here。 So in that case。

 what we're going to do is we're going to say that the provider is going to advertise the prefix on behalf of its customer。

And the customer is just simply gonna have a default route that says， for all addresses。

 not in my autonomous system。 Just go to my provider。



![](img/d525653c4bea9a81a8605e4131d2a1f5_15.png)

So what that looks like is this example here。 have have a provider and a customer。

 The customer has been given the prefix 130。 132。Slash 16。

 what the customer is going to do is it's going to configure the routers within its own A S to say if theres any address that is not 132 do130 132。

 just send the packet to my providers's network。That's all you have to do。

 And in your provider's network， what you're going to do is have a static out that says any destination that is with the prefix 130 do 132。

 just send it to my customer。 And then you're going。

 the provider is going to play the role of the B TP speaker on behalf of the customer。

 which means it's going to advertise that prefix to the rest of the Internet on behalf of the customer。

We should just know that this special case exists。 The rest of the lecture。

 we're not going to worry about this particular case。 Any question on these default routes in BG B。



![](img/d525653c4bea9a81a8605e4131d2a1f5_17.png)

Okay， so with that second terminology， BTP specific terminology。

 is you'll hear this term BTP sessions。 What session is is just two neighboring routers that are exchanging BT P messages back and forth。

 We say that they're engaging in a BTP session。And so if you look at one of these border routers。

 they have two types of B GP sessions。 One is the session that a border router has with a border route in a different autonomous system。

 So run by a different operator。 We call this an external B GP session， or E BGP session。



![](img/d525653c4bea9a81a8605e4131d2a1f5_19.png)

![](img/d525653c4bea9a81a8605e4131d2a1f5_20.png)

The second type of session is the exchange of messages that happens between a border router with all the other routers。

 both border and interior routers within its own domain。Within that A。

 we call these internal BGP sessions or I BGP sessions。these are IBGP sessions here in the red。



![](img/d525653c4bea9a81a8605e4131d2a1f5_22.png)

If your head is starting to hurt EBGP I BGP， IGP， I don't blame mu， let's recap them very quickly。

 EBGP sessions are sessions that a border router has with border routers in a different autonomous system。

This is how you're going to hear about prefixes that are out in the Internet outside of your autonomous system。

 This is also how you're going to tell the rest of the Internet about prefixes in your own autonomous system。

IBGP sessions between a border router and the other routers within its own domain。

 This is how you're going to take that information you hear from other autonomous systems and you're going to distribute it within your domain。

It's a distribution mechanism to share what you've learned。From the inter domainoma sessions。

And finally， IGP is interior gateway protocol。 You've heard this before in Murphy's lectures。

 This is just the formal term for an intro domain roing protocol。

 It's how routing is done within a domain。 This is our distance vector， our link state。

 you know form the protocol names are OPF everything that we heard in Murphy's lectures。

So how do all these pieces come together？ Yeah So if I go back to this A S graph now。

 I have my links with costs on them within my domain。



![](img/d525653c4bea9a81a8605e4131d2a1f5_24.png)

So within my domain， I'm going to run my IGP， you know， distance vector Li state， whatever I want。

 my IGP protocol。It's going to compute least cost parts。 At this point。

 I have routes to all destinations within my own domain。

 including to my border routeers or to other routers in my domain。Then with E BGP。

 I'm going to learn about external destination prefixes。And then I'm going to take those prefix。

 those routes that I've learned and share them with all the routers in my domain。

And every border of route is going to do this。This might look not very scalable。

 We'll come back to that， in a bit。But at this point。

 any router anywhere in my domain has all the information it needs to reach any destination on the Internet。

So if I take a router， you know， let's say the one that's going on the part label 3。

 the part that's going to follow if given a destination prefix outside its domain is it knows from the IBGP session。

 which eager router， What is the border router in its own domain that it has to exit traffic through to reach that prefix。

And it knows from its intra domain routing protocol。How to reach that border out。

And so it can reach any destination on the Internet。 Let's make that a little more specific。

 So in this case， let's say that the domain where all 7 is had a prefix A do B， slash 16。

It would have told our one about this through its EBGP session。Our one would have told all the goers。

 including our two in this example， about that prefix through its IBGP session。

And so now our two knows that to get to A dot B， it has to reach our one。

And in in turn knows how to reach our one because of the intra domain loading protocol。The IGP。



![](img/d525653c4bea9a81a8605e4131d2a1f5_26.png)

Let me repeat this one more way， different way。 And then let's pause and see whether that made sense。

 because this is really how all the pieces come together。 So it should be clear。

 So every router underneath A has two routing tables。 conceptually， this is how we think about it。

 One is from IGP from running an intratro domainoma protocol。

 I have a table that tells me what my next top is to all my internal destinations。From IBGP。

What I learned is which border router， which egress router I should use to get to any destination prefix。

 not in my domain。So that's like my next top in some sense is my border routeer in this case。

And so now if I'm trying to， I'm giving a packet， remember the packet has an I P address。

 and I'm going to try and forward it。If that packet's IP address is within my own domain。

Then I just have to look up the table that was computed for my IGP。I look up the destination address。

 I get the next Ho outto。 I send it on。 I'm done。If that address， however。

 was an I P address that's outside of my domain， I'm going to do a two step lookup。

The first thing I'm going to do is I'm going to look at the prefix for that destination address。

 and I'm going to know which eagergress or which border routeto I have to send the packet towards。

And then I'm going to take that bottle outer and say， what is my next hop。Using the intra domain。

 because the intratro domain protocol told me how to reach all my protocol routeers。

Any questions on this？一。我这。Yeah， that's a great question。

 How does the border router reach all the interior routers。

 It knows how to reach them at the connectivity level because weve run the intratro domain loaduting protocol In practice。

 the implementation B G P actually runs on top of TCP， which we haven't covered yet。

 But you don't need to know that for now。 For now， you know， how do I reach my interior routers。

 because my intro domain protocol built up the parts to them。Any other questions？is this clear。

 Anyone want me to repeat it。

![](img/d525653c4bea9a81a8605e4131d2a1f5_28.png)

Okay， so in reality， what I've described to you is one way of configuring how the intra domain and routing and BTP interact or how they integrate In practice。

 there are few different ways to configure a domain and different providers do it slightly differently。

 the one we've talked about， which is option one here。

 This is what we're assuming in this class is that a border router runs IBTP sessions to all the other routers in its domain both interior and border routers。

So if I have n routers in my domain and B border routers， this means I have n times B sessions。

 IBGP sessions within my domain， which is quite a bit， depending on the size of your network。

 this might be a problem or if it's not then you know this is probably the simplest way to do things in this class。

 this is what we assume。Just so you know that there are other ways to configure a domain。

 Another common one。 and I think Mufi touched on this in one lecture is that a border router will only have IBGP sessions to other border routers。

 not to interior routers。And then each border route is going to inject that prefix as though it was a directly attached destination address into the IGP。

So now you have prefixes being advertised into the IGP。

Does anyone is that reasonably clear to people。

![](img/d525653c4bea9a81a8605e4131d2a1f5_30.png)

唉。Yeah， good question。 Let me go back to that picture here。 So what would this mean。

 Let's say that this route to R1 got a dot B。

![](img/d525653c4bea9a81a8605e4131d2a1f5_32.png)

And there's the other border out on the right。 Let's call it X。And R one would have told x。

 I have a prefix A dot B。In this case， this doesn't really work very well， but you could have had R1。

 Let me hold that back。 A1 could have just injected A or B as a destination into the IGP protocol itself。

 So it looks like a destination from the point of view of the IGP protocol。O。In this particular case。

 which is why it gets confusing。 let me just say it briefly and then not go any further。

 Our one could have also told another border routeer that border routeer could have advertised。

 could have chosen if it was doing the I thing chosen not to advertise it as a destination because it doesn't actually have a path or it could have advertised a very high cost path。

Going there。 But then you'd have to do some。Additional stuff to make that work。 So let's not that。



![](img/d525653c4bea9a81a8605e4131d2a1f5_34.png)

![](img/d525653c4bea9a81a8605e4131d2a1f5_35.png)

The third option。 and actually， this is probably the most common in the very large scale providers is they'll run a separate appliance or device called a route reflector。

 Think of this as a special server。 and the job of that server is it sets up IBGP sessions to all the border routeers。

 So it sucks in all the routes advertised to any border routeer in its domain。

 It runs a computation to select parts and it goes off in programs all the routeers in your domain。

 this is called a route reflector。 No they exist in this class were just assuming option one。

 So make sure that option one is clear to you。Any questions。



![](img/d525653c4bea9a81a8605e4131d2a1f5_37.png)

哎。So how is all of this actually implemented in terms of protocol messages and protocol exchanges。

 So the key here again， the BgP protocol specification has quite a few message types in this class we're going focus really on what we call a route update but just again。

 know that there are many other types， for example， there's a type of message to open a session。

 There's another type of message called a keep alive just to say this session is still active。

 This border router is still up and so on。 The one that we care about is what we call a route update type of message。

 This is a message that informs a border router， either I have a new path to this destination prefix or I have an update you know maybe I haveve changed some of the path length or the actual path associated with this destination or sometimes what we call a route withdrawal。

 which is a border router telling another border router I no longer have a path to this prex。



![](img/d525653c4bea9a81a8605e4131d2a1f5_39.png)

Okay，So let's take a little bit into what gout updates look like at the highest level。

 Gut updates are as simple as they get。 It's I have a prefix。

 and I have a set of what we call attributes associated with that prefix。



![](img/d525653c4bea9a81a8605e4131d2a1f5_41.png)

Okay， so the prefix is exactly what we've been talking about。 It's you know a slash 16， a slash 24。

 whatever you want。 It represents a whole bunch of destination hosts aggregated into a prefix。

 The attributes are a general mechanism that we use to describe or express properties about routes。

 And as you're going to see all of the secret source， all the smarts of BGpss。

Kind of packed into these attributes。 So you can think of them as。They describe a route。 in know。

 one way mentally to think about it is it's a set of key value pairs associated with a route where the key is a particular attribute type。

 the values， the value of that attribute。 And we're going to use those to implement policy and to do route selection and route export decisions。

Again， some attributes are local to an A。 So there are some attributes that will be associated with a prefix or associated with a path that a border router will never share with border routeers outside its domain or with any router outside its domain。

 so they're local。They there are also attributes that are propagated in E BTP without advertisement。

 So there are attributes that will get propagated across the Internet。And in general。

 there are many standardized attributes， we are going to talk about four important ones in this class。



![](img/d525653c4bea9a81a8605e4131d2a1f5_43.png)

So first attribute， something we've discussed already is this notion of an AS path。

 So if you remember from the last lecture， we said BTP is a path vector protocol。

 It actually when you advertise a prefix， you enumerate the sequence of autonomous systems needed to reach that prefix。

 and this is how we prevent loops。So A S path is just that vector of A Ss that you're traveling to to get to that prefix。

 It's and go to advertisements。 So what it would look like is something like this。

 So let's say in this example， I have Princeston and Queenton is a S 88。 It has a prefix 128 dot 12。

1，12 s 16， and it's connected to A and D。So的。Pinnceton and AT N T are going to have an E BGP session between their border routeers。

And in that session， Princeton is going to advertise。 This is my prefix。

If I dig into what that advertisement looks like， and we're getting now a little bit into the syntax of these messages。

What that message is going to say is here's my prefix，1，28 dot 1，12， so on。

 And here is my A S path attribute。And my A S part attribute at this point just says AS S 88。

 because that's where the prefix is。That message is going to get propagated through IBTP。

 and so on to this other router on the right。Which is still in AT&T's domain。And now A& D， let's say。

 is going to advertise that prefix further to Berkeley。

If I go look at what that message being advertised between A T& T and Berkeley looks like， again。

 it has the I P prefix。 It's the same prefix unchanged。Now， the A S path attribute says 7，0，1，8，88。

 So you know that your path is you're going to through A and T and then to Princeton。

So pretty simple A P records。

![](img/d525653c4bea9a81a8605e4131d2a1f5_45.png)

The vector of A S is needed to reach that destination prefix。The second attribute。

 Any questions on ESpo。Pretty much doing what we said path vector would do。

 The second attribute is what we call local pros or local pre。

 This is actually where go expert gets implemented。

 and all the gouting follows money gets reflected in local P。So。

The way local Pf is used is to choose between different A S parts。

 Local preference is local to an A S。 As the name suggests， it also makes sense because remember。

 we said Aes don't like to publicize their policies about customers versus providers versus peers and so on。

 So local pre stays within a domain。 That means it's carried only in IBGP sessions and IBGP messages。

And in general， local per， the higher the value， the more preferred it is。 So it's quite intuitive。

 Let's go back to our example here。 And now in this case， we have Princeton again， A S 88 up there。

 and we Ive complicated the picture a little bit in that Princeton now reaches A T N T potentially through A S 100 or through AS S 200。

It has a pot。So A& T can reach to Princeton， either through AS 100 or AS 200。

The way we're going to use local preference is that let's say AT And T prefers using the path 2 S 100。

 because maybe 100 is。A customer and 200 disappear。Just to reflect cow export。

 So what A And T is going to configure its border routeers to do is it's going to say at that border router。

 when you get a prefix advertised by A S 100。Add to that path internally， when you store that path。

Add a local value of， let's say，300。 The value doesn't matter。 I'm just picking it out of nowhere。

And so now if you looked at the routing table within that border router。

 you'd see a part that says something like for this destination prefix。

 your A S path is 180 and then followed by 88。 And this gout has a local pref of 300。

You would likewise configure on the other end。 You don't like a S 200 as much。

 So you would do the same configuration。 But you would say I'm going to give it a local per value of 100。

Okay， so it's lower preference。And now， IBGP is going to share those entries with all the other routers in the domain。

And so now， what is any routeer going to do in order to implement Ga expert。

 the only thing sort of mechanistically that a routeer has to do is say。

 I'm going to pick a path to that prefix。 I have two options for how to get to that prefix。

 I'm going to pick the one with the higher local。So I'm going to go to 100。Any questions on this？

To manually often。 so the operator knows what kind of relationships they have with A 100 versus A 200。

 so they configure their routeers to say local pref。Coming from this A is 300。 coming from that。

 A is 100。Which should cause you some discomfort。Any other questions。

Does this fully implement gog export？ So gog experts said， you know， customer better than pure。

 So assuming 100 is a customer and 200 is。What happens if A S 100 goes down or it withdraws the out。

You'd need to update the table and you take out 300 the first entry。

But you would use your path going through 200。 right So it's， it's doing the right thing。

 It's prioritizing。 It's not eliminating routes。嗯。How would you actually， I think your question is。

 how would you actually know to get rid of that route。

 So this is where route update that's a withdrawal would come in。 So A S 100， you know。

 either you time out the route and then the border route would would withdraw it or A 100 might explicitly withdraw the route。

Any other questions。

![](img/d525653c4bea9a81a8605e4131d2a1f5_47.png)

Right， so let's actually move on to。A slightly more complicated case now。 And as you'll see。

 you know， the B to P， conceptually， the approach is simple。

 and what we're trying to do is very intuitive， implementing it in a distributed fashion。

 given the realities of how A S is interconnect is where things get a little tricky。

 So this is the same not the same example as before， because so far。

 we've been assuming there's one link between two A Ss。In reality。

 what is very common is that two autonomous systems， especially large ones。

 will have connections between them at multiple places。 So if you're ATN T and Verizon。

 you probably have connections between the two networks on the East Coast， in Chicago。

 on the West Coast， in Europe and Asia。 So you have multiple of these connections between two different As。

Okay，And so now when you think about， you know， going back to this Prince to Berkeley path。

 you kind of have two parts either you can go through something like， let's say， the orange。

Level routeer path， or you could go through this green path here。

So notice this is the same AS level path。 I'm going Queenston， the lies in AT& T Berkeley。

So the A S level is the same part at the go level。It's a pretty different path， right， in one case。

You're switching from AT&T to Verizon on the West Coast。 and on the other case。

 you're switching between them on the East Coast。Which one do you think。

Verizon would prefer between these two。The California out。 So the organ one。W。Yeah， okay。

 interesting。 That's a valid argument。 Not the one。 So the。

 the proposed answer was Vaguson would prefer it because you're using your own go。

 So you're assuming Vaguson would like to have control over the part In reality。

 Vaguson would like the other way， because it uses less of its bandwidth。😊。

Which is an expensive commodity so。Reasonable argument。 I was going the other way。

 So let's say that Verguson likes the green pot。Because in this case， you know。

 I'm saving my bandwidth。 There's another reason。 O， let's go with that。

 How would Vagaon try to influence the way traffic enters their network。

So Vageson has is advertising Princeton's prefix。To AT And D。 And somehow。

 Verryyson would like to tell AT And D， hey， I would prefer it if you send me traffic to Princeton over。

This goer that's on the east Coast。So I need some dish。

 Nothing in what I've told you so far would work。That we we don't have anything in the protocol that would allow Vergeson to implement this。

 And so the third attribute is an attribute that is designed to help。



![](img/d525653c4bea9a81a8605e4131d2a1f5_49.png)

Autonomous systems influence how traffic enters their network。

 It's an attribute called M or multi exit discriminator。

 And we're going to use it when A is typically the ways used when A S is have two or more links between them。

And the idea is to try and tell the other autonomous system how close a prefix is to the link over which it's being advertised。

Okay， so let's go back to that picture here。 We had。In this case。

 the AS that's announcing the prefix， this is Verizon as advertising， for instance prefix。

 and it has these two links over which it's going to advertise it。1 on the East Coast。

 one on the West Coast。The way it's going to use it is me as an attribute is when it advertises the route over the East Coast。

 it's going to say， and again， I'm just the exact values don't matter。 It's going to say。

 here's the prefix。 Here's the A S part。 This advertisement has a med field of， let's say，10。Okay。

And when it does it on the West Coast， it's going to give it a med field that's higher。 let's say 50。

Okay， so if you think of these as costs， like our least cost routing， it's kind of trying to say。

The link on the East Coast has a lower cost。Does this make sense？And so now， AT& T， when it hears it。

 has the option of saying， Vaguon is trying to tell me to use this link here on the East Coast。

It's and saving bandwidth is not the only reason Va guysizon might do this。 Let's say AT And T had。

 instead of。A customer that was Berkeley on the West Coast。 Let's say it had NY U on the East Coast。

 If you had no meds， NY U， the path from NY U to Princeton。

 you would have no way of knowing whether you should send it over the East Coast link or the West Coast link。

 But it would make so much more sense to send it over the East Coast link instead of sending it across the country and then back across the country。

So met is a way you can think of it of kind of extending our notion of least cost。

Gouting across domains。Again， it's an attribute。 It's a hint。

 There is no reason AT N T has to adopt it。 but if AT N T chooses to listen to what theon is telling it through its mefield。

 then it will choose。The me part， the part that has a lower me。你看。Any questions here？Yeah。

 great question。 Hol on to that thought for just half a slide， same question。



![](img/d525653c4bea9a81a8605e4131d2a1f5_51.png)

Okay， so exactly that question， which path or which route does AT and T prefer。And so the guys said。

 I prefer the green out。 That's what it did with its mefield。But in this case。

I think somebody has said this already。 If you are AT T， you would prefer the organ throughout。Again。

 under the assumption that we are trying to save our own bandwidth。sDoes this make sense to everyone？

So what would AT And T do。Ignoing mes， what would AT& T。Try and do to， in order to use the。

The West Coast exit route instead of the east Coast exit route。

It's clear to everyone why you want to AT and you prefers the orange path。

RightBecause the green pot is consuming A And T's own bandwidth across the country。 So what could。

What could ATMT do。呀。Right， the sort of the the suggestion was make the internal links very high cost。

 The thing to remember is actually， AT& T doesn't have to do anything to do that。 right。

 We already have intro domain routing and our intro domain costs。



![](img/d525653c4bea9a81a8605e4131d2a1f5_53.png)

So if all I did was look at the intra domain cost or the IGp cost。



![](img/d525653c4bea9a81a8605e4131d2a1f5_55.png)

And I said， I got the same prefix advertised to me from two different routers。And when。

 when you're leaving Berkeley here， you look at what is my IGP cost to the exit router on the west Coast versus the IGP cost to the exit router on the east Coast。

 And you're just going to say， I'm going to pick。

![](img/d525653c4bea9a81a8605e4131d2a1f5_57.png)

The exit router that has the lowest IGP cost。 This is something called hot potato routing。

 And everyone does it。So if you send traffic that's leaving the network。

 they will send it out of their network as soon as possible unless sometimes unless you pay them。

 you pay the provider to carry your traffic further。 So of this is very common in cloud providers。

 if you， for example， sign up with Azure and you sign up for you don't sign up for any special treatment in their network。

 then they will take when your traffic is leaving Azure servers， they will hot potato your traffic。

 they will send it out of Azure network as the first chance they get。If you pay Israelz an extra fee。

 then they will actually carry。Your traffic across Azure's network until you know as far as they can。

 close to the destination。The assumption being that Azure is running a better network than the public Internet。

So what is IGP costs， again， IGP costs are local to an A。

 right no one's going to advertise their IGP costs outside of the A and all it does is when its every router。

 what it does is when you get the same prefix advertised by two different border routers。

 you pick the border router with a lower IGP cost。OkaySo let's go back to that picture here now And now I'm adding internal IGP costs to ATT's network。

And again， remember， these costs private to AT&T。And it's not going to share them with anyone else on the Internet。

And now were going to say that if you were this router over here。

 they organ run trying to get to Verizons network。 You would go through the border router on what was the east Coast in our earlier picture。

 If you were somewhere in the middle， you would just pick whichever one was the lower IGP cost。

 In this case， happened to be the one on the West Coast。On the one on the right。行。



![](img/d525653c4bea9a81a8605e4131d2a1f5_59.png)

一。Yeah， so so that's that was exactly the next point。 So hold on。

 let's come back to see if you still have the question when we are done with this。

If you're looking at this， you should be thinking， wait a minute。 this IGP cost is。

Sending me in a different direction from what the med attribute was trying to say。

 so Verizon was using med to say， come in on the left out or not the right。

 A T and T is saying I'm sending my traffic out on the left， not the right。

 because it's the shortest spot。 So IGP can conflict with med。 This is not uncommon。 This happens。

 And so， you know， going back to that example we had where Verizon was saying a med of 10 for the left and 50 for the right。

 Well， in this case， A T and T is just not respecting the med。

Is there a problem with this necessarily。Anyone think it's a problem。Yeah。

 so there might be some contractual back and bickering， but it nothing breaks in your go yeah。电记分。

Okay， topyin can turn around and do the same。 So， in fact， this happens。



![](img/d525653c4bea9a81a8605e4131d2a1f5_61.png)

All the time on the Internet。 So， for example， if you see two providers A and B and you're looking at traffic going between the east and West Coast。

 what is quite common， for example， traffic going from B to a destination in San Francisco。

B would immediately hot potato the traffic and send it over A network。

But the returnton traffic coming back from the destination。To the source。

A is also going to hot potato it and send it over Bs network。 everyone playss the same game。

 The point to notice here is that you have asymmetric parts。

Your path from a source to a destination may not be the same as the path back from the destination to the source。

This doesn't necessarily cause a problem， but it does tell us why we isymme on the Internet is common。

And it happens， know， by design， not necessarily as an accident here。So this is why I was asking。

 is there actually a problem， Like， could you get into a loop， How would you get into a loop。

So the reason you wouldn't， in this case。 So let's take the。

 the green you're going the traffic going from the source to the destination San Francisco Francisco。

For a to send it back， the destination would have to B And B， which is not the case here。

So you're still following an advertised path to the destination。 So you're not going to have loops。

So there might be some unhappiness between providers and they might。

 you know get on the phone and talk to each other about it and massage their policies。

 but it's not causing your packets to be dropped or to loop。Any questions？Oh， great question。

You might ask， why bother with Med， Anyone know the answer。

So what would have happened if the green source here was in L A， let's say。Still in B's network。

 but in L。So on the West Coast。Would we have wanted to respect the mefield。So let's step to that。

 So the green sources on the West Coast。A has told B that it can reach。The San Francisco destination。

 it's advertised that path over their link on the East Coast and their link on the West Coast。

If I had no med。B has no idea where the destination is relative to the east Coast or the west Coast。

So would have no indicator for which one is the shorter path。In this case。

 it at least knows that okay， the path on the left is actually the shortest path to the destination。

So it's going to use the， the link on the left。Let me give you maybe a better example。

 Let's say that the green was dot was in Ohio。In the middle of these network。So， going。

To the left or to the right， to the east or the west is similar from Be's perspective in terms of how much bandwidth it's going to consume。

In that case which we wouldn't want to go。It would want to take the link that's closer to the destination because it's a shorter path for its。

On customers。Right， so the me is a useful indicator when there is no conflict between me and IGP。



![](img/d525653c4bea9a81a8605e4131d2a1f5_63.png)

Great question。 Okay， so closing the loop， when we last lecture。

 we talked about how the typical selection policy， when you receive an advertisement。

 how do you select which path you want to use。 And we said that the policies tend to be you want to make or save money。

If they're equal in terms of making or saving money。

 you want to maximize performance means take the shortest path。

And then you want to maximize minimize use of your network bandwidth。

 So you want to save network bandwidth to the extent that you can。

You should now know kind of in terms of mechanisms， how this is implemented。

 make a save money is your local pref value。 This is how we do go expert。Maximize performance。

 That's the length of your E S spot。And minimize use of your network bandwidth。

 That's this dance we play between me and hot potato。



![](img/d525653c4bea9a81a8605e4131d2a1f5_65.png)

So now when you think about how BGP is implemented， it should be very clear to you。

 this is kind of the table for how we apply attributes in a routeut update right So how is BGP implemented。

 I get route updates has a prefix and a set of attributes。

I follow the rules in this priority order that are in this table to decide which routes I'm picking。

And everything we talked about loing follows money。 I want short up。

 I want to have a good balance of performance。 I want to save my bandwidth。

 All of that follows from applying these goals。And this is a priority order。

 That's the important thing to remember。 I always first do local pref。

Because that's about making of saving money。 And then I try to optimize performance and save bandwidth。



![](img/d525653c4bea9a81a8605e4131d2a1f5_67.png)

Any questions？BG be clear。So let's talk about some limitations of PGP at this point。

 You've seen enough of PGP。 You know， What do you think。

What do you thinks that you think would work well in BgP or not work well。

 Where do you see potential problems in the protocol。I had four categories。Yeah。complexity。

Can I somebody says yeah， okay， let's we dig into that Anything else？I've got to view beyond yep。

Han cause。 I'm going to lump that in with。 I think you。

 you've taken complexity to the fact that there's all this manual tuning。Any other。

What about security。I had four classes。Other do people thoughts on security。 How could you imagine。

Misusing B， Gb。行。Points of entry that you have to secure。 That's fair enough。 More basic than that。

Right， so。This is like a deeply problematic part of B GP。

An E S advertise sends an advertisement to you saying， I have this prefix。

 and here's my bo to the prefix。There has no mechanism in B，G P to check that。 you actually。

Have the right to advertise that prefix that that is actually a valid path to that prefix。

There's just nothing in the protocol that is designed to catch that。

There's also no guarantee that you say maybe so you could lie about a prefix。

Completely spoof a prefix。 You could also lie about the path。

 You could say or not choose to not lie about the path in the sense that you advertised a valid path to a prefix。

 Then when you got data packets， you just send them over a different path。

 You don't actually respect the path that you advertised。So it's really just。

 this is an indication of how the Internet was designed in a pre attack， you know。

 pre security concerns， either the fact that there is just no validation of security checks around BTP。

 What would happen if an A S said this is my prefix。 I have this fantastic path to a prefix。

If I just follow the BT P protocols back。Everyone just sends。

Traffic to that prefix we call this prefix hijacking at an autonomous system can claim to be any prefix at once。

 So as you can imagine， in the real world， there are a lot of policies operators can figure a lot of checks in order to make sure know is it strange that suddenly Google is being advertised only from Australia。

 there are all these sanity checks that go on to make sure these prefix is are valid。

 are also protocol standards people are working on that would have cryptographic security around advertisements。

 so you can prove that you own this prefix and you can prove that an advertisement traveled across a set of as parts。

 but deploying them and getting all of that PK infrastructure around it has been slow。

 So securing BGP is still a major issue on the Internet and it's craft not a science we survive because the people who are configuring B G P know their job。

What would you do to make sure that Ns actually follows。The part that's being advertised。

Becauseuse you can imagine you know， using digital signatures or cryptography to make sure that a prefix。

You cannot hijackively fix。 What about making sure that a packet actually follows the path。

 so you could send a packet。 You can't quite quite trace the path that that packet took。

 You could use tools like trace Sc to see what parts the packet follows。

 But it's actually a really hard problem to and an unsolved problem to make sure that a packet followed the path that you thought it was going to follow。

 I would say that's a pretty open problem。You could put a part that you want the packet to follow and hope。

 But if you have a malicious ears， that's not following it。

The fact that you told said what path you want followed。

So every hop along the way would have to do that。 Yes， that would work。Any。啊对。

Thoughalts open sons about B security。So the short answer is that B to P security is a bit of a mess。

And that's why people are very， very careful and who and how their V G be。

Policies and advertisements are configured。Performance。And thoughts on performance。

 So I have a hint here on saying that they performance non issues。

But can you see a concern around performance with BGP。

And so performance here tends to be short paths。行。Nonop。

 I would go beyond what you've said and say that in general。

 policy based out selection is not about picking short path， right， It's about enforcing policy。

 So the path you picked based on policy need not be the shortest path。

 So I said this was a non issueue because this is not by accident。 This is by design。

 Operas are choosing to prioritize policy over path。

The other aspect is that your A S part length can be misleading。

 So if I say I have a one hopop A S part length， there's nothing in B GP or no easy way that allows me to distinguish between that was one A S ho that involved two routers both in California versus1 A S ho that involved 20 routers spread across the globe。

 that detail is actually hidden because we are abstracting all that into an A S path。 Again。

 this is by design。 Ips and As don't want to reveal their internal topology。

 but it does have this implication for performance。Pne to configurationration。

 Someone brought this up。 We have many attributes。 The configuration is often manual and ad hoc。

 Again， configuring Bgp， there's a relatively small number of people who are trusted at large operators to actually configure B GP。

 anytime there's a configuration change， it's done very carefully， it's tested， it's vetted。

 and we still have major issues。 So Bgp misconfiguration is probably the root cause of outages on the Internet。

 And if you Google some of the famous Bgp outages， it's quite entertaining。

 So the examples like Pakistan wanted to censor YouTube。

 And so they wanted to put in configuration that would filter out routes advertising YouTube。

 And they got it wrong。 And so by mistake， they started advertising YouTube to the rest of the Internet。

 And so all YouTube traffic went into Pakistan。 exactly the opposite effect。 Russia。

 I think had a similar thing with Twitter recently somebody did prefix hijacking to hijack all the traffic going to one of these。

cト。Companies and manage to actually steal millions of dollars doing that。 So B， G P hijas and。

 some of them are malicious。 A very large number of them are actually just unfortunate miscons。干。

And finally， reachability and convergence I touched on this last time。 If you follow Gag Oxford。

 good things happen。 If you don't follow Gag Exp， all bets are off。

 there's no guarantee even that all destinations would be reachable or that you'd have convergence。

 And in section， you're going to see this very fun example of how if you don't follow Gag Oxford。

 you could have continuous oscillations in which path you' be you selecting。

 So gouting actually never converges。

![](img/d525653c4bea9a81a8605e4131d2a1f5_69.png)

Okay， so without any questions。 let's take a one minute break。

 We are kind of done with P TP at this point。 So any last questions on BT P。let's keep going。

 So rest of today's lecture。 I just want to take talk of where we are in the overall syllabus。

 In some sense， we started with this overview of how the internet works top down bottom up。

 and then we jumped straight into L3 or the network layer。

 which is arguably the most important layer on the Internet。 and we spent many weeks doing routing。

 we've done intra domainin， Interdoomain we've done a addressing。

 So at this point addressing and routing， which I would say is the control plane for the network layer。

I hope you got that that we're fairly complete from that front where we we're going to do this week is go back to the L3 or the network layer data plane。

 Okay so today's lecture， we're going to talk about what the I data packets actually look like and specifically what the I header looks like。

And then next lecture， we have a guest lecture of Google who's going teach us about I routers。

 how they built， how they function。 And we're kind of very lucky to have him because he is the person that represents Google to all router vendors。

 So he really knows what he's talking about。 And he also defined some of the main router management and router configuration protocols that and use everywhere today。

 So open config if you Google it you will find Rob's name。



![](img/d525653c4bea9a81a8605e4131d2a1f5_71.png)

So today， let's talk about designing the I header。 Okay， and designing the I header。

 if you remember going back to one of our earliest lectures， we said we have packets。

 They have headers and payloads。 We tend to not worry so much about the payload because especially at the network player。

 Voers are not looking at the payload。But the header is where all the action is。

 And so that's what we're going to be focused on。 So we're going to talk about the syntax。

 like what fields and how many bits for the I header。 I know that sounds very boringing。

 We try to make it not so boringing。 But more importantly， the semantics。

 Why do we have those fields， What do we use them for and so on。



![](img/d525653c4bea9a81a8605e4131d2a1f5_73.png)

Just a quick recap to get your head back in the right place。 Remember we talked about layering。

 So keep in mind where L 3 and L 3 headers fit between L 4 and L 2 and how we talked about encapsulating packets in headers and then removing headers when you reach the destination。



![](img/d525653c4bea9a81a8605e4131d2a1f5_75.png)

Also， remember， we had this complicated end to end protocol diagram thing to remember here is the fact that the I header or I portion of the packet is relevant both at routers and at endho。

 It really is the end to end。Interface or language。



![](img/d525653c4bea9a81a8605e4131d2a1f5_77.png)

给。Any questions or reminders on the I P header in terms of its goal at that high level。Okay。

 so designing the I header， when you think about designing the I header。

 the way to think about it really is not so differently from how you would think about designing an interface。

 any time you have to build a system， kind of start by thinking about the interface。

 So think of the I header as the interface between the source and the destination and system。

But also， the interface between the source and the network routeers。

So could would not be an exaggeration to say that the IB header is the interface to the Internet。

It's kind of a cool interfaceted design。So when you design it。

 any time we talk about designing something， first thing you should ask yourself is， what's the goal。

So in this context， what task am I trying to accomplish？ And this， again。

 should be no different from when you design an interface for any piece of code you write。

Your module has a certain function。 Your interface has to pass the parameters and the information so that that module can do its job。

It's going to be exactly the same with I P。 We're going to say what tasks are we trying to accomplish and then what information do we need in order to accomplish those job。

 those tasks。And then your I P header is just simply how we capture that information。



![](img/d525653c4bea9a81a8605e4131d2a1f5_79.png)

So with that， what are these tasks。 And remember， I P headers are relevant at routers and they are relevant at the destination host。

 right， This is the send。Communicating both with routers and the destinations。

 So I'm going to give you one example。 The first thing you should do when you receive a packet。

 you have to be able to pulse it。You have to know what kind of packet is this is this's an I packet。

 what fields are there。 So passing the headway and the packet is。Job number one。

 we're going to have to do this at grers and at the destination。What else。What was the job of I B。

How to forward it。 absolutelysute， That was the primary goal of 5 P， right。

 So going to need information in the herald that allows the routeer to forward the packet。

What else do we have to do。So what's a normal part for packaging。So we forward it。

What happens when it reaches the destination。Get at the beut。 Yeah， I'm going find that， so。

Kind of tell the destination what to do with the packet。 right。

 so I need to be able to pass the packet at both routeers and destinations。

I need to be able to forward the packet on to its destination。 This is。

A task that the routers have to do。When the packet reaches the destination end host。

 the destination has to know what to do with it。 because remember， the packet is not really。

 it's not headed to the destination。 It's headed to some application at the destination。

So there's something in the packet header that has to allow the destination to figure out how。

The packet has to be sent next on its journey towards the application。 get to that in a minute。

And then。For most practical purposes， we're going to need a response going back to the source。

 And so again， the destination host has to know how to send the packet back to the source。I have。

 this is a task for out us as well。 and we'll get to why that is in a minute。

 So this is kind of all you would need to do in a well functioning， you know。

 pretty bare bones network。 Anything else you can think of。Yeah， okay， someone else。

Broadly call that deal with problems along the way。

 and we'll get into what potential problems you could run into。

And also then the ability to specify some kind of special or you know。

 more advanced processing that we haven't quite gotten into so far。 So we'll get into that as well。

So these are kind of the tasks， the consolidated list of tasks。 This is all。

The tasks that you need to capture in the I header that。

Your IP header has to have all the information needed to accomplish this set of tasks。

It's not such a long list， actually。

![](img/d525653c4bea9a81a8605e4131d2a1f5_81.png)

So let's go through these a little quickly。 They're fairly intuitive。 I think， to pass a packet。

 what what information would I need in order to be to know how to pass this packet。

Size of the payload， anything else？Size of the header， yeah。IP version number。Great， oops。

 you got all of them。 So first version number for I P。

 Why is it so important that I have a version number。Yeah。

 because if you don't have a version number， you would be stuck with the same header forever for eternity So when you had IPV 4 and you wanted to go to IPV 6。

 if you needed a different format for the header and you didn't have a version number， good luck。

 you wouldn't have been able to implement it。 So a version number just like you have versions for API is critical。

 Also where does the header end， this is because as well get to in a minute。

 the I header is not a fixed size。 So you have to know how many bytes form the header。

And then remember， we said I packets are not all the same sites。

 So you also have to know where the packet ends。In order to deliver a packet to the final destination。

 what information do you need in the header。We've had this。Assume the set throughout。Oh， you jumped。

 but yes， to get to the destination， you need the destination address。To get back to the source。

 you need the source address。 next task was tell the destination how to handle the packet。

 And here I want to go back to our protocol diagrams that we had and a different layering。

Architecture that we had earlier。 And remember now that when the packet arrives at the destination。

 it's coming in off the wire and it's traveling up this protocol stack。

So now the packet has reached the destination。 It is at the right I P destination。

And so in your operating system， you've looked at the Ip header and you said， great， I've reached。

TheIP destination。What next。Remember that packet ultimately is being consumed by an application。

What do I need。You need one of those， not the second。 So I need at least the protocol number some。

 something that identifies which protocol at L4 is going to process this packet。

So I received the packet at IP。 I need to know is this a TCP packet in which case I'll send it to be processed by TCP。

Or is it a UDP packet in which case I would hand it to the UDP module。TCP and UDP。

 we've not covered yet， thus。Our next topic， these are different layer4 protocols。

But I need to know which one。The packet has to be sent to next。Does that make sense？

Let me repeat it one more time。 It indicates which protocol should handle the packet next。

 So it's a protocol field。Protocols are given a unique number by again。

 the numbering agency I can or Ana， just like I P addresses and A S numbers。

 different protocols will have a well known protocol value。

Can your protocol field is going to carry that protocol value？

And this is used at the receiving end to demex where the package should go next。不是。Yes。

 so the protocol field is going to be part of the IP header so that the IP layer knows where to send it next。



![](img/d525653c4bea9a81a8605e4131d2a1f5_83.png)

So what does it mean to have a protocol field？ So as I said， these protocols have well known numbers。

 So for example， TCP is 6， UDP 17。And so when in my I P head I say my protocol value is 6。

What that means is that the next header is a TCP header。Okay。

 so it's telling me how to process the packet after IB。If I said it was 17。

 then it tells me that the next header I should expect is the UDP header。Any questions on this？



![](img/d525653c4bea9a81a8605e4131d2a1f5_85.png)

Right， so let me go back to great question。 Let me go back to that very first where is that。



![](img/d525653c4bea9a81a8605e4131d2a1f5_87.png)

Right， so if you remember going down the stack， we added all these headers。

And then when you reached the destination at the I P layer。

 you received a packet and you took off the I header and the next header inside was T CP。

 and you passed it up。So this is saying， I'm going to take off the IP header。 now。

 do I know where to send。Should I send it to TCP or should I send it to UDP。

 That's what the protocol value is telling us。

![](img/d525653c4bea9a81a8605e4131d2a1f5_89.png)

Any other questions？So finally， getting responses back to the source。

 we covered the I need the source IP address。 So taking stock。

 these are the fields we're going to need in the I header so far。



![](img/d525653c4bea9a81a8605e4131d2a1f5_91.png)

We had two more tasks we needed to do。 One was to deal with problems along the way。

 and the other was the specialized handling。 What problems can you。

 do you think we could have in the network。

![](img/d525653c4bea9a81a8605e4131d2a1f5_93.png)

IThink one of them came up， which was I could have some corruption。 Some of my bids get corrupted by。

The equipment along the way。Yeah。Some packets could be dropped， why。

What could I put in the I header to help。To deal with this packet will get dropped。

It's not a bad time，So if we had error messages， then it would make sense to have something like send an E for this packet。

 That's not what the standard IPP does。 It doesn't necessarily send most of the time doesn't send error messages。

 yeah。嗯。是。Would sayy， why would you need sequence numbers。Okay。

 so you right that we will eventually need some sequence numbers。 We're going to do that at L4。

 not at L P， because the job of the network is not to guarantee that packets go in order。

 but we will need them when we get。 you got to another point that well get to a it。

So you need some signature， we're going to call it a checkum， not so much for T。

 but just to make sure that the bits you sent are the bits you received。For whatever reason。

 anything else？you don't want the packet to wander the network。

 And why would the packet wander the network， Because as you remember when we were talking about routing。

 it takes some time for routing to converge and you can have loops while we're waiting for the parts to converge。

 And so if you didn't have any mechanism， these packets would just be looping forever。

 So we're going have something we call a time to live。

 and we're going to drop a packet if it's been going around in the network for too long。Great。

 I think you guys got all the fragmentation was the other one。 So let's go through these loops。

 corruption and fragmentation。 So preventing loops， as I said。

 while we're waiting for routing to converge， it's possible that you have loops for a period of time。

 We don't want packets looping forever in the network。 And so very simple solution。

 we put a time to live in the packet header field。At every hop， as the packet is being forwarded。

 we dec the detail。If the TTL ever hits  zero， this is one time we could send an error message back to the source。

Same time exceeded。 And you used this capability when you did trace Club。Typically。

 you don't have synchronized clocks across water， so you wouldn't do an actual time。

T is work on clock synchronization， so maybe one day， but not yet。Okay。

 so this is a little arbitrary。 In this case， we send a message back to the host saying， hey。

 I dropped your packet。 I exceeded。 and routeers don't always do that for security concerns。

 but it's true that in this case， we designed to have error messages， but in other cases， we don't。

A little arbitrary。 I don't think I have a good reason for that。Any other questions。Okay。

 so just one point to note， if you want to send an error message back to the source。

 this is another reason why we need the source address and why routers need the source address。

Head of corruption。Are people comfortable with the idea that packets bits can get corrupted along the way。

This comes down to， you know， your signal at some level is an analog signal。

 and you look at the power or you look at some signal strength and you decide whether it's a bit one or 0。

 And sometimes if your laser flickered or something a0 could get flip to one。

 so theres physical characteristics of a link。 there are reasons why you could corrupt bits of corrupt packets。

 So check some is just compact。Fingerprint， or you can think of it as a hash。

 or there lots of checks some algorithms out there that will summarize what the data being gathered is。

IP uses a particular form of checksum， the part2 members IP carries compute that checksum only over the IP header。

Okay，And so if it's not correct。 So every time a packet comes in。

 the router or the destination is going to check。 it's going to compute the checkum over the header。

 It's going to compare it to the stored value of the checkum。 If the two are not the same。

 it's just going to drop the packet。This means the check some is updated at every v。

 This is a bit of a。Pain because it's a little expensive to computer checks some。

Why are we computing it at every route。The T T L changed。 anytime I change any value in the header。

 I have to recompute the check some。Why did we include the detail in the header in the check sum calculation。

 Why didn't we just say I'm not going to include the detail。Yeah， to protect the detail。

 but nots not the best reason。 a reasonable design could have been to say。

 I'm going to leave out the detail， but that's not what the earlier designers did。

 Why do we only compute check sums over the header because other bits could be corrupted as well。

Yeah， so the early designers were the job of the network layer。 It's a very pureist thinking。

 L3 is to predict the L3 header。 I'm only computing check sums over the L3 header。

Why did we even need to check some in the first place？Why do routers， Sorry let me give if you that。

 Why do routers have to check。Whether the packet is corrupt， what would happen if they didn't。Yeah。

 so the exactly that。 the the thinking was， well， what if I have a link that starts malfunctioning。

If I， let me roll that back， what if a router did not check the checkum， What would happen。

 It would forward the packet onto the destination， The packet would be the reach the destination。

 The destination could check whether the packet is correct， whether the checkum is correct。

And if it's not correct， it can drop the packet。So you should think about this。

 start thinking about the end principle。 from a point of view of strictly correctness。

 it would have been fine to have not had routers compute checkss。Would have been good， in fact。

 a little less work for votersers to do。 And the end host could have。

Checked whether the check sum was fine。You would have saved the destination from receiving bad data。

 So would have worked fine。 The thought was， well， we've wasted all this bandwidth for sending。

Crupted data over the network。 This is likely。 People don't worry about it as much anymore because they're more worried about scaling routers than they are about checkums。

 And so we'll get back to that。 This is a decision the IPV for designers made That was maybe not ideal。



![](img/d525653c4bea9a81a8605e4131d2a1f5_95.png)

啊。Last point on the problems。 One of the things that can happen is this question of fragmentation。

 I think this has come up in earlier lectures where we said every link has a maximum transmission unit。

 This is the largest unit of data that that link can carry。

So sometimes the source might send a packet that is larger than some links empty you。

And so when the packet reaches that link， it is the job of the router at the front of that link to do what we call fragmentation。

 which is to take that packet and chunk it up into smaller packets。 Okay。

 so if you had a large packet here and let's say I was chunking it up into 1500。

 which is the typical ethernet empty U。 you would take that packet contents and chunk it up in this case into three independent packets and you would create a new header for each of those fragments。

And then ultimately， you would have to reassemble those fragments back into an original packet。

So it's conceptually， it's an fairly easy thing to understand。 Packet came in too large。

 I'm going to chunk it up and send out fragments。 And then I'm going to reassemble it。

 It gets a little tricky and a little fun in exactly how you design fragmentation。

 So you're going to do this in section。😊，Okay， any questions on fragmentation though conceptually。



![](img/d525653c4bea9a81a8605e4131d2a1f5_97.png)

So with that， you have， we have added three more types of fins to I P header。 We have a T T。

The source address we already had， and we' gonna have a set of fields to do fragmentation。

There's a question somewhere that I yeah。Right， so what would happen if you sent it to the。

 that's a good question if you， if your destination bits were corrupt。

 but they still got you to some valid destination。What that destination accepted。Yes， you're right。

 that could be a problem。 You'd have to have many things that go wrong because you would also have to have a process。

 an application with a port that's sitting there。 so， but in principle， yes。

 you could imagine that bad case。

![](img/d525653c4bea9a81a8605e4131d2a1f5_99.png)

So the last thing in our header was this question of what if your packet wants some kind of special treatment and there's two kinds of special treatment that the early designers of the Internet considered。

 As you've seen these fields are not worked out so well。

 But the first is imagine that you don't want to treat all packets the same。

 you want to indicate some customers that are more important。

 higher quality or traffic that is sensitive to delay or sensitive to throughput and so on。

 If you go back to our very first lectures， this was this idea that the Internet should do more than just best effort traffic delivery。

And then the second was the thought that maybe sometimes you want to do some kind of special functions or features。

 treatment for the packet， like for diagnostics or debugging or other reasons。

 And so there was this entire class of。Fiels called options that got introduced。

So let's take the first of those type of service is exactly what it sounds like。

 It was originally designed to be a set of bits that would tell a out how to treat this packet。

 What kind of service does this packet want either you know delay sensitive。

 who put sensitive over the years many people defined it and redefined it and tried to use it。

 it never really took off the one use of these bits that has persisted is just for priorities if you want to indicate different levels of priority then this is what these bits are used for。

And so today， finally where these bits， these bits are a bit the laughing stock of the protocol designers because they have changed continually。

 But as of now and for quite a few years now， they've been stable at this definition。

 which is you have six bits that we call DSCP， which is basically priority bits。

 These are used to indicate priority。 And then you have two bits that are used by a router to indicate to endho whether they've experienced congestion。

 So we call those E CN。 Don't worry about E CN for now。

 well cover EN when we get to congestion control。So remember though primarily indications of priority。



![](img/d525653c4bea9a81a8605e4131d2a1f5_101.png)

And then the last bit is this idea of options。Here， the thought was， you know。

 what if my guter needs to do more than just fold a packet。

And so there were examples of things people thought that would be useful to do。 One is， for example。

 this idea of recorder route。 What if you want to trace the path the packet has taken。

 I want to be able to tell a router you need to record your I D or record the path as this packet is traveling or if you wanted timestamps for diagnostics or debuing reasons you want the router to put a timest。

 So you know at what time this packet arrived at this router。

Third option that was common was this idea of source routing。What if I want to tell the routeers。

 here's exactly the path I want you to follow， overriding what your routing algorithms told you。

So the thought was you might have these more complex features or more advanced features。

 and the host should be able to tell routeers what those features are。

 So this is why people designed I options again， not very widely used。

Part of the issue with I P options。 One was the minute you said， have a whole set of optional fields。

Your headal length is no longer fixed， and your headal length varies。

And as you try to build hardware routeers， it process back at at very high speed。

Having to deal with variable length headers is complicated because the first thing you have to do is pass exactly what all these bytes are。

So it's harder to have a parallel little implementation， which is what allows hardware to go fast。

And the second problem is many of these options， processing options is an additional processing overhead on the routeer。

 And so they became ways of attacking a goer that if you want to attack a goer。

 you send packets with lots of options set。 And now your exhausting resources are the routeer。

 So again， options kind of mixed luck in terms of how。



![](img/d525653c4bea9a81a8605e4131d2a1f5_103.png)

How they get used on the Internet。 So， but two fields that you will see in your IPV forer for that reason。

 are these type of service bits。

![](img/d525653c4bea9a81a8605e4131d2a1f5_105.png)

And option bits。 I'm going very quickly just flash the I P header here at you because we've covered it。

 So we show the I P headers aligned on 32 B boundaries。 So 4 by。

Feels you'd expect to see in the I header a passing。 You have a version number。

 you have a header length and a total length in bytes。 The header length is in。

Counted in multiples of 32 Bs。So multiples of4 bys。We have the destination I address。

 We have the protocol field， which tells us whether it's TCP or UDP or something else。

 We have the source I address。We have the TTL and the checkum it's 16 bits。

 and then we have a bunch of fragmentation bits that you design in section and lastly。

 we have the type of service and some options。给 so。

If you go pick any IPV4 packet off of the Internet and you look at it。 this is what you'd expect。

 This is what you should。 you have to see。This is the protocol standard。Any questions。



![](img/d525653c4bea9a81a8605e4131d2a1f5_107.png)

Okay， so just next time， which is not Thursday， but the lecture after that。

 will wrap up IPV 4 to IPV 6。 What were the main changes in what we discussed and then just a few security implications of the IPV4 headeder。

With that， thank you。

![](img/d525653c4bea9a81a8605e4131d2a1f5_109.png)