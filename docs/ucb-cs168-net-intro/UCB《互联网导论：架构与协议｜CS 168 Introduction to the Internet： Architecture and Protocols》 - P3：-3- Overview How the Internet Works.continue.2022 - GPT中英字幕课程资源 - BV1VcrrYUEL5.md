# UCB《互联网导论：架构与协议｜CS 168 Introduction to the Internet： Architecture and Protocols》 - P3：-3- Overview How the Internet Works.continue.2022 - GPT中英字幕课程资源 - BV1VcrrYUEL5

Good morning， everyone。 Let's get started。 Just a quick announcement Monday there will not be any discussion sections because of Labor Day。

 but we will still have a worksheet and we will have a recording of a walk through the worksheet。

 so do follow that。跟。Excellent。So with that， this lecture we're going to continue with that broad overview that we started last time of this kind of bottom up view of the internet。

 and so we're going to wrap up that discussion， wrap up our discussion of circuit versus packet switching and then we're going to the second half of this lecture start that top down overview。

And so just a quick recap from last lecture， we said that one of the fundamental questions in networking is how do you want to share network resources。

 and we said there are two highlevel canonical approaches。

 One is based on this idea that you're going to reserve bandwidth for the duration of your communication。

 and the other is this idea that you're just going to send your data and hope that the network can handle it。

 So that's the best effort model。And in terms of how we implement these approaches， we said again。

 two canonical approaches， circuit switching is。The de facto way by which one would try to implement reservations and packet switching is how we implement best effort delivery。

Still， a recap of how circuit switching works is this idea that if I want a certain amount of reserved bandwidth between these two blue end host。

 I'm going to take the peaked amount of whatever the application needs in terms of a bandwidth。

In order to have that communication， send a reservation request through the network。

It will follow the path that the routing algorithm has picked。

 And if all the switches along the way can actually accommodate that 10 Mbit per second。

 then we've established what we call a circuit where a circuit means I have that 10 Mbit per second reserved bandwidth for this particular flow。

And when you're done again， the endhos will initiate what we call a teardown circuit message。

 which is kind of like garbage collection， basically going along that path saying I no longer need this reservation。

 you can let go those resources。And so that's the basic idea We had behind circuit switching。

 packet switching。 I think we've done this many times。 now， you basically have a packet。

 It has a destination。 You send it into the network， and each switch is going to treat。

That bucket independently。So where we got to was this discussion or discussion about which approach is better circuit versus packet switching。

 And so I'm going to turn to you to give me the answers here。 And you know。

 anytime I ask you which approach is better， the first question you should ask is。

What are your metrics or what are the dimensions along which we are going to compare。

 And so any ideas， what should be our criteria for deciding which one is better。What matters。行。

Backets so simple。那们。Build on what I think you're getting at with that。

 which is if I have a very large packet， maybe it's not going to make it through。

 And so a circuit would have been a better way of guaranteeing that I would get the resources I need。

 Okay， anything else。有。So how robust is this to how likely is failure are going to be or how likely a dropback is going to be versus okay。

 I thought you were going somewhere else， that's also a valid point。Can I lump those into。

How what kind of service am I going to get， Am I get going to get good performance for my network。

Anying else we should worry about。行。Toput， so can I say efficiency， Like。

 how well am I using network resources， yeah。本案个认证的。Bick place。Lots of things that can happen。

 what else should we worry about as we think about implementing circuit switching or packet switching？

Complexity， which one's going to be simpler， which one's going to need more mechanism， other things。

You have two out of fighting the four that I had。For tolerances。

Which one of them is more robust to things in the network feeling？And okay， the next one。

 So the four that I had was， you know， the first。 and it's， everyone always overlooks this。

 but we shouldn't。 is this actually a useful abstraction。So ultimately。

 we are building the internet in order to build applications。

And so one might ask which of circuit versus packet switching is a better abstraction for applications。

 and this is important because that's kind of like the API we're exposing to applications and so it matters that it's a useful or good API and they're very different in circuit switching what as an application developer the abstraction that the network is giving me is you can ask for a certain amount of bandwidth。

 and if I tell you that you have it， then you as an application you're guaranteed to have that amount of bandwidth to the end hostst。

Whereas back is switching， on the other hand， our best effort。

The abstraction is giving an application is send data。 and that's it。The rest is up to you。

 You may get 10 M per second。 You may get 1 M per second。

 It may change over the duration of your flow。 So a very different abstraction。

The other one was efficiency and in particular efficiency at scale。

 so this was the answers that popped up around how well are you using network resources because remember bandwidth is expensive。

 Operas deploy links with a certain amount of bandwidth。 They want that bandwidth to be well used。

Also， efficiency matters because applications， the more bandwidth you can get out of your network。

 presumably better performance you can get。Handling failures， we've said that the internet is vast。

 links go up and down， switches go up and down， any solution or architecture we come up with has to be resilient to those kinds of failures。

And finally， complexity of implementation， because the Internet， again， is a large scale。

 complicated system。 If you're going to try and engineer something that's incredibly complicated。

 you're probably not going to get very far with it。Any thoughts on these as goals？没。

What do you think from an application viewpoint as an abstraction。

 If you were an application developer， which abstraction would you like better。

Which one do you think is easier to build an application on top of？有。Probably the reservation one。

 right It's kind of one。 you get better performance because you think about what's the maximum performance your flown needs。

 What's the maximum bandwidth， And then you have it。

 It's guaranteed to be there in the network for you。It's also exactly what the point。

 which is it's predictable and understandable。And if you think about just when you write code。

 for example， you have a multi threaded program and you run it on cloud instance somewhere。

Whether if you have four callss versus if you had 8 goalss。

 or if you have 32 gigs versus 64 gig given to your application， your performance varies。

 And if no one told you how many codes you were going to have at what point in time or how much memory you were going to be assigned versus not would be very complicated to reason about the performance you'd expect from your network from your application and the same is true from the networking perspective if my available bandwidth keeps changing。

 that's going to add some complexity to my application and reasoning about application performance。

But the other reason is it's actually a very intuitive abstraction as a business model。

 If you think of it from an operator' standpoint。If you had this abstraction， you could say， well。

 you customer end host， you asked me for 10 Mbit per second。 I gave you 10 megs。

 So this is how much I'm going to charge you。 If you ask me for 15 Mbit per second。

 I'm going to charge you more。 There's a hook in there to charge based on usage。

And if you think about it， that's what we do in the cloud as well。 You pay for a fo call instance。

 or you pay for an eight co instance。 You pay more for more。Instances with more memory。

 Why shouldn't we expect the same from the Internet。

 Why shouldn't operators expect to be able to charge based on use。They're not going to be able to。

 but it seems very reasonable as a goal to want this kind of abstraction。

 And that's largely the appeal of circuit switching is that it seemed like an appealing abstraction。

What about which one makes more efficient use of network capacity Before I go here。

 actually let me pause any questions on this idea of circuits versus best effort。As。

 as an abstraction。So efficiency， which one do we think makes more efficient use of network capacity。

So I thought you paing your hand。行。Best effort， say why。Yes， so anyone disagree with that。No。

 so you're absolutely right and what I would say is that packet switching is typically more efficient and that reason what typically is in there for exactly the reason you were describing。

 which is it depends a little bit on how bursty your flow is or how bursty your traffic sources and to see this kind of visually let's think about one example。

 let's say I had a 30 megabit per second link and I have three sources that have flows that they want to initiate reservations with and each source needs a constant rate of 10 megabit per second This means throughout the duration of that flow the source wants to send exactly 10 megabits per second。

In this context， packet switching and reservations。

 both of them are actually going to be equally efficient。Both of them are going to do equally well。

 visually， if you want to see that， you know， if I had this pipe with 30 MB per second and I had three sources that were asking for 10 meg each。

 you can see that the pipe is fully used and every one of the sources got exactly what they needed。

 So everyone's happy。 We have efficiency， and we have happy sources。

We would have had the same with packet switching。 The network just had the capacity to absorb all of the demand。

But what if we'd said that those three sources look like this， where their demand is bursty。

 There's a period of time where they have some amount of demand。

 And then it's not actually using the network anymore during the rest of the flow。

And that peak usage was actually more than 10 Mbit per second。 It was 12，11 and 13。With reservations。

 what would happen if this was。What my sources needed。And here。

 the duration of the flow is the entire width of this demand that I've drawn here。

What would happen if you were running a circuit switchitch network？行。

You reserve the peak for the entire thing， for which flows。ForSo let's walk through this。

 The first source comes along and says， I need a reservation for 12 Mbit per second。The network says。

 that's good。You get to go。The second one turns up and says。

 I need a reservation for 11 M per second。We're still good。I grant the 11。

 And then the third one comes along and says， I need a reservation for 13 MB per second。

 The network no longer has 13 M per second available。

So the typical option with reservations is that you will allow two flows to reserve their peak rate。

 That's what they asked because the network has no way of knowing that the end the source doesn't actually need the full reservation over the entire duration of the flow The network just believes what the source says and gives hands out that bandwidth for all the network knows it's going to be So  one is going to be sending a 12 me throughout。

So stool is going to be sending an 11 me word。 It doesn't know。

 So it hands out those two reservations， but it must turn away the third floor。

And so if you think about what's going on in that pipe now while I have these two reservations。

I have satisfied two of my sources， but my network is highly underutilized。

 it's underutilized both when each of those flows is not using the full reservation and it's underutilized because I had this leftover capacity that was not enough。

To actually hand out to any other source。Question。Right， so the question here is that。

 you know why didn't the blue source let go of the reservation。

 This is a particular example where I'm saying the duration of the flow is the entire width in time there。

 So you're right that if the blue source had torn down the reservation at the end of its demand where it start sending traffic。

 then we would have not had a problem， but that's just not what this example is trying。

Any other questions on this？行。Yeah so this is a great question。

 do people try to actually do the sources， try to make the traffic they generate more efficient in the sense that it'll consume the full reservation in practice in when we get talk about NLS circuits a little bit at the end yes people will try very hard to make full use of that MPLS connection but sometimes it's also the nature of the application and for example。

 if this was a web browsing session the way we browses you know you click on a link and then you read there's some quiet time and then you click on another link or you click on a video and then you get again more demand so inherently depending on the application。

 some applications are inherently choppy and bursty there's not much you can do about it。

Any other questions？So what would have happened with best effort with best effort。

 every source would have just sent their traffic。 And if you look at how these sources line up in time。

We actually， we got lucky。 There was plenty of demand。 There's no overloading。

 Every one of the sources is happy。This is actually very much the same as the example we had with statistical multiplexing and why statistical multiplexing works at all。

What this example is showing you is that statistical multiplexing works better with best effort。

 service than it does with circuit switching， because we are multiplexing at the granularity of packets。

 not flows。So this is， in this case， best effort would have made much more efficient use of network resources。

Any questions on this？So this is really the broader distinction about。

 you know kind of know your workload and the difference between smooth versus bursty applications。

 And so typically we characterize a flow of an application by the ratio between the application' peak demand rate and the average。

Demand that it has。 And so a smoother application or some applications will have a fairly low issue。

 The peaks are not much more than the average。Streaming medias or audio。

 video are typical examples of that。 You don't see a huge amount of variation。

So those we would tend to call pretty smooth applications。But others and famously。

 data applications tend to be much more bursty。 They can have peak to average ratios around the hundreds。

This also tells you why the old phone network was designed to be a circuit switch network because when you place a voice call。

 they're not typically long silences you placed a voice call in order to talk to someone and then when you hung up you're done so the idea of circuit switching was actually it made sense because you have this smooth constant rate demand。

And at the same time， you're very sensitive to performance because we hear disturbances in audio。

 and so it made sense to have that guaranteed bandwidth。

So going back to that question about which one is more efficient， typically packet switching。

 where it typically depends on the burstiness of your traffic sources。And again。

 the root cause of why packet switching is more efficient is because we stood multiplexing at a finer granularity。

 individual packets can come in and fill the gaps as needed。

 whereas with reservations we are multiplexing at the granularity of entire flows。

 the entire duration of a flow。Any other differences in efficiency？

So not just this statistical multiplexing。 Are there other reasons why。

One of the other would be more efficient。有。So exactly。

 so switch you spend some time to set up the circuit。 so imagine if I had an IoT sensor at home。

 it takes a temperature reading and every five minutes it sends one reading to the cloud。

Totally normal behavior for something like a sensor。So it sends 100 bytes every five minutes。

 It's a very small amount of traffic。 Imagine if every five minutes I have to set up a circuit。

 ask for reservation， get the acknowledgement back， send out my hundred0 bytes。

 stay down the circuit。 All of that work just to send00 bytes。

You're spending much more time and bandwidth than the actual amount of data you had to send。 So。

 again， circuit switching is not the best fit for when you have very small amounts of traffic to send。

How is it on efficiency， Let's move on to handling failure。

 Any questions on efficiency before I move on。So what happens in the event of a failure。

 So let's say I'm back with my。Picture where I have this part。 This is the green part。

 This is the part that the routing algorithm picked。 We've not gone into how it does it。

 but just say the network has decided this is the part that follows from source to destination。

What do I do if I have a failure。So this switch went down。

 Let's think about it first in the context of packet switching。So anytime I have a switch go down。

 the network。 First， the network has to do something about it。

 It has to detect that that switch went down and it has to recompute a different path。

Through the network that avoids that switch， that's failed。Okay， so this is， in this case now。

 let's say that the network by running this gruting algorithm。

 pick this new path going between the source and destination。So at this point。

 the the network has fixed the problem。 It has found a different path。What。

 what does the end hosts have to do if I'm doing packet switching。行。Nothing， exactly。

 The end hostst has to do nothing。 The end host didn't even have to know there was a failure。

 Now you just send your packet when the packet reaches that fork green outer there。

 it's going to send it to the new switch instead of the failed one。

And there might have been a period of time while the network was busy figuring out this link is down。

 I need to go this way and recomputing parts。 there might have been a period of time when packets were getting dropped because I had no path。

But the end host didn't have to know。So it's as simple as it gets in terms of from the end horse perspective。

This is as simple as it gets in terms of fault toleranceance or failure recovery。

You just send your buckets。What about t circuit switching？So again， with sucket switching。

 the switch is going to fail。 The network is going to recompute a new path。

 It has now found this new green path。What does the end hosts have to do。行。

The endhouse has to send another reservation， right。

 And the reason is because we had set up this circuit。

 all the switches had reserved 10 Mbit per second。Along the path。

 And now one of that switch failed and the path is going through a new switch。

 That new switch made no guarantee that it had 10 MB per second。 It has no reservation state。

 So you have no idea whether that new switch can actually accommodate the reservation or not。

Even more， you don't even know that the switches that used to be on the old part are the same switches that are now on the new path。

So you also have to free up the resources from the previous reservation。So what you have to do。

 you have to actually tear down。The previous reservation。

And then you have to send a new reservation request in going through the network。

And there's even no guarantee that this reservation will work because there's no guarantee that the new switches along this new path actually have that amount of bandwidth。

so to recap， this should start， I hope to sound more circuit switching should start to sound more complicated to you to recap failure。

 covering in packet switching， the link goes down。 What do you do。

 The network has to first detect the failure。 It has to recalculate a new path。

 This is the job of the routing control plate。And then the end host and the individual flows to absolutely nothing。

 They just continue sending packets。 The destination has not changed。 The path has changed。

 but the end host doesn't need to know about it。With circuit switching。

 you have to do everything that you did with packet switching。

 So the network still has to find a new path。 But in addition now。

 the end host has to detect or learn about this failure。

 It then has to tear down the old reservation and establish a new reservation。

And if you think about it， all end hostss that had a flow going through that switch that failed have to do this。

So think of this now from the perspective of you have a switch that's in the middle of Google or ETNT's backbone。

 it has millions of flows。And that switch went down。 It took down millions of flows with it。

 You have millions of sources that have to react by sending new reservation requests。

And probably they were going to do that at the same time just to make things worse。So。

It's not sounding so pretty， as a。Falult all wind design。

Let's move on finally to complexity of implementation。 And here I mean a little bit。

 know aside from failure。How which one do we think is more complex And so this is why you're going to start to realize that the design I've given you so far is actually far from being a complete design。

 we have to extend it in order to make it work So let's think about that。

 So what we've said so far is that a source is going to send a reservation request to the destination and I said you know it's going to go 10 mega 10 megabit ask every switch along the way and every switch is going to say yes。

That sounds good， and you can now have a circuit established。

But how do the switches actually know that the reservation went through and how to switch 1 and 2。

 Let's say it the reservation request went through 1，1 set years，2 set years。

How do does switch to know that3 and 4 are going to say yes。

 How do you actually know that the reservation made it through all the way。It's not a trick question。

 You have to extend the design。 So what more， what new mechanism would you add to the design。

So let's say the next thing we're going to do is we're going to say this reservation request goes all the way to the destination and every switch along the way is going in the reservation say yes or no。

 and if everyone said yes， then the destination is going to send a confirming the reservation message that will travel back to the source。

That's a reasonable extension。So that's how we could say we've extended the design so that the switch is no。

If the reservation went through， But what happens if the reservation request is lost along the way。

So one said yes， two said yes。But then， the reservation was dropped。

So cleanle never even saw the reservation request。What do we want to have happen？

So we're going to extend the design yet again。 We're going to say every switch holds a timer。

And that timer， I'm going to when I accept a reservation request。

 I'm going to set a timer and if the timer goes off before I see a confirmation coming back。

 I'm going to say this reservation didn't make it and I'm going to release those resources。

And delete that reservation。Sounds reasonable。行。So what happens if the confirmation that the reservation made it is is now lost。

 So let's say the reservation went through1，2，3，4。 everyone gave it a thumbs up。

 The destination is sending the confirmation back， goes through4， goes through3。

 so three and4 now thank great， this reservation is confirmed。And then I dropped the gun。

What do I do。WellWhat's going to happen， first let's step through that。

 Those timers at one and2 are going to expire，So now we're in the state where one and two don't have a reservation。

 don't have a reservation state。And three and four do have reservation state。 What shall we do？Yeah。

So one approach you could have is that one and two could send out a message saying。My time I expired。

 I'm deleting this reservation。St down that state。That's one option。Anything else you could do。

That I think is the most sensibleten option， but there are more。Right， so you've got to repeat。

 resend the confirmation request multiple times。 So in the hope that at least one of them makes it through。

 It's probably no guarantee， but yes。You could have the host have a timer and say I didn't get a confirmation。

 so now I'm going to send a cancellation。What happens if you sent that cancellation and then the confirmation came in while you sent the cancellation。

So。As you can see， the part I'm trying to get at is not that it is impossible to design this。

We can design this， and people did design this。 It's that it' there are a lot of corner cases。

 It's a complicated system to get right。So for example。

 what should the end host do if the reservation has declined？

So I asked for 10 megabits per second and it was declined。Ideas people have had， well， you know。

 you could have asked the switches to tell you what reservation they could have given you。

 So at least the applicant source could say， well， I couldn't get 10。

 but it looked like 8 would have made it。 And then you try 8。Still。

 no guarantee for someone else might have booked it while you were in the process of negotiating from 10 to 8。

 What happens when the underlying route changes， That's all of the faultwin mechanisms we describe。

 You have to detect failure or detect change。 We adjust just。Repeat your reservation and so on。

 So again。We could and designed this。 People did。 They spent years designing this system。

 but it's hard。Why do you think it's hard， Like what is fundamentally hard about this problem that we are trying to solve。

Yep。Time is inchony， the fact that different。Nos are doing different things at slightly different times。

 Sure， yeah。Depenencies to make it all work。 Yes build on that a little bit。

 That's a word I'm looking for。What are those dependencies？

What am I dependent on for the reservation。都比。Set up correct。Right。

 so the dependency is different systems。A setting up this object that have， and they have to agree。

 So the word I'm looking for is consistency。 What we've created with reservations is we're creating state in the network。

These switches are creating state at every switcher creating state that says do I have this reservation or not。

 So it's a lot of state， It's for every flow in the Internet。

It's highly dynamic state because every time I start or stop af， I have to go and create the state。

And perhaps most crucially， that state has to be consistent across all of the switches。

 All of the switches have to agree whether that reservation made it or not。

 whether that reservation is torn down or not。And if you've in CS162 or some other class。

 if you've studied about consensus algorithms and Paxos。

You know that that is fundamentally a different very difficult problem that in an asynchronous system。

 having a bunch of participants agree on an outcome is just an inherently hard problem。

 It requires many rounds of communication and very complicated protocols。

 even in context like data centers， people make very sparing use of algorithms like fos and so on。

 they tend to be a performance bottleneck。 So trying to achieve consensus across the Internet at the time scales of flows coming and going with all these uncoordinated participants is just a very hard problem。

嗯。So just to recap circuits versus packets， the push for circuit switching is better application performance because you have your peak rate reserved for you。

And it's more predictable and understandable。Gose for packet switching， better efficiency。

 faster startup， easier recovery from failure and a simple implementation for all the reasons we went into。

So what is the internet used today by default packet switching？

So packet switching is what the internet is based on。

Thats said there is limited use of a protocol we call RVP， which stands for Re Reservation protocol。

 This you can think of RVP as kind of the protocol we've been designing here in class。

 That's the basic idea behind RVP。Provis use it， but they use it in a very limited way。

 and it's limited in many dimensions。 It isn't exposed to end host。 So an end host cannot just say。

 I want a reservation and have the network give it to them。It's typically。

 they use it almost to set up state， not so much to actually reserve bandwidth。

So it's a very water down form of the protocol， and it's only typically used within one network。

 So for example， Google uses it in their global backbone network。What is very common， though。

 is that you will find people that go out and buy dedicated links。

Things like MPLS circuits or these lines。And what these links look like。

 the typical use case would be within an enterprise between branch offices， for example。

 so Wells Fargo and San Francisco might want to have a dedicated link or what they call a dedicated circuit to their office in San Jose。

And pretty much any enterprise。That I'm aware of of mid scale to large scale enterprise will have a large number of these NLs circuits or dedicated links。

 Bley has a number of these NLs circuits， for example。

They're quite different from the dynamic reservations we've talked about though in the sense that so one they're highly expensive if you want to get an NPLS circuit。

 it's usually 10 to 20 x getting a normal internet connection。They are often statically set up。

 so if you know they want that Wells Fargo wants that circuit。

 someone in Wells Fargo will call AT& T for example， and say。

 can I get a circuit 100 megabits per second dedicated between San Francisco and Sanse。

For reasons I've never fully understood， this takes months for ATMT to set up。

And then they'll come back and give Wells Fargo this soet， Wells Fargo will have this socket for use。

And the assignment is not at the gun laity of flows， it's Wells Fargo's circuit。

 all of Wells Fargo traffic between Senators Gu San Jose might go over that link。

And going back to the point someone raised earlier。

 Wells Fargo will be very careful about what traffic they put on that MPL S circuitet because it's expensive So they tend to put high priority traffic on there。

And so it's a far cry from the vision of highly dynamic reservations that we've talked about。

 It's actually more like a。Non statisticalically multied。 I went out and bought a link for myself。

And it's also pretty painful if you ask Ser here， Ser has had the dubious pleasure of actually setting up trying to set up one of these links to between Berkeley and AWS took many months and was a painful process。

And so one of the things when you go out， for example， an internship person， you know。

 you're working at a company， they'll tell you， are you on the public Internet。

What they mean by that is typically if you're working in a branch office。

 they'll have an MPLS circuit， and they'll also have this connection to the best effort packet switch internet。

And you can people will talk about I you on the public Internet。

 What they mean is areO not using that MPLS circuit。When I first heard that term。

 I confused me because I thought there's only one Internet。

 All it means is you're not on an M S circuit。So you might be wondering given everything I've said about reservations and you know we're not using it。

 why did we bother talking about it， And you know， isn't it obvious that we shouldn't be doing circuit switching or reservations at the granity of flows like we talked about。

A little bit of history here is， you， the early internet when people first built it was always a packet switch network。

And you know the application it was initially built for was files， file transfers。

 but if you start looking at， you know about the late 80s to early 90s。

 so the internet went commercial， the government stopped funding and running the internet around the early 90s。

That's when everyone in the community， both in research and in industry。

 thought that the Internet should transition to doing circuit switching。

And the reasons for this actually made sense at the time， right because one they were saying， well。

 we're going to transition into being a commercial network。 And so ISP are going to have to charge。

 And so it's a much more natural way to charge。The other reason was they believed that the killer app for the Internet was going to be voice calls and TV。

 live TV。And， you know， the reasons for that again made sense。 users at that time。

 What did they do in terms of communication， They did voice calls and they watch TV。

 And so if you were a network operator， instead of building independent networks to carry voice traffic and to carry TV and then carry data。

 wouldn't it make sense to have one Internet。That carried all of that。

And because voice and video famously need high quality constant rate traffic。

 wouldn't it make sense to put circuit switching into the Internet so that we can do voice and video。

So that was the reason why everyone believed you needed circuit switching and people spent 10 plus years in the 90s。

 this was a hot topic trying to make circuit switching work。

 Many of the people who worked on this you know， people that should be familiar to you here at Berkeley。

 So Alice VP， for example， the protocol I just described Scott Shankka was one of the people that developed it while he was at Zoxx Park together with Li X Zhang was the other main inventor of that。

Jon Styer， when his PhD thesis was showing how you could emulate circuit switching to get very tight guarantees on packet delay。

 so what he call quality of service， that's the result that got him his job here at Berkeley。

Nick McCune is a professor at Stanford when he was a PhD student here he developed these circuit switches。

 he showed how you could build hardware circuit switches that could do circuits set up and tear down very efficiently and very quickly so he did a number of startups in that space Cisco acquired them the standards bodies embraced IVP This was how the Internet people thought was going to go。

But yet， it didn't actually happen。 And ultimately。

 this vision of reservations and circuit switching is viewed as a failed vision。 You know。

 And if you ask me why it's all the reasons we talked about that technically。

 it's a hard design to get right。 And there's a lot of complexity。But that's not the full story。

 Weve often build complicated engineering artifacts， over engineered artifacts。

We have many of those in existence。 Why do you think what else contributed to kind of the death of this vision。

行。对。That's one reason。 That's an excellent reason。 The killer app turned out to be email in the Web。

 not voice and video。 I mean， we have Netflix and Skype and all these things now。

 but in the late 90s， the killer app was email in the Web。

 No question about it going all the way up to the 2000s and so on。And you know。

 this makes sense when you think about it in retrospect， if you were a user。

 you had your phone was working just fine。 Your TV was working just fine。

 The email and the Web were things you could not do without the Internet。

 So that was really the game changer for people。What else？

We now do have Netflix and Skype and other things working on the Internet。 What changed。

 Why do they work now when before we thought they couldn't work。やep。That's a fair point。

 The links bandwidth went up。 We now have much higher bandwidth links。

It's hard to get people to change in terms of the what they used to， in terms of audio and。

From packet， yes， there was certainly an inertia in the sense that but the Internet was small still in those days。

 But you're right， even at that point in time。Switching the Internet from one model to the other wasn't trivial。

Bs bandwidthand has gotten cheaper。 Yeah， the dollarll up a bit。 That's actually a good point。

 The question about whether circuit switching would have been a better financial economic model than packet switching。

 I don't think we actually have consensus on that。 People don't really know。 And sometimes。

 we never got to try it out。Most people， the assumption would be that actually circuit switching would have made operators more money because they could have more easily charged for by use from higher usage。

 whereas today， operators struggled with this head。 overnight。

 people went from using their cell phones to place calls to watching video。

 And so their consumption of bandwidth went up 10，2000 x in a very short period of time。

 but carriers didn't actually get paid more for it。So。

 the the economics around circuit versus back switching is。Complicated and unclear， I would say。

The other， so I think you folks got everything。 The one other thing was people actually re go to applications to be adaptive。

 So everyone was used to the characteristics of voice calls or the characteristics of a TV stream。

But no one thought， well， what if we changed the way people send audio and video， So， for example。

 now， what do you do when you have a bad connection。

 You degrade the quality of the video automatically。That's what all of these players will do。

 The same with audio。 If you are having trouble， it starts doing things where， you know。

 you can think of it as it sends every packet it twice or every packet it three times so that you're more tolerant。

To bad performance in some way in the network。And so just while as there was one community working on trying to make circuit switching work。

 there was another part of the community that was saying were just going to go and rewrite applications and that group was actually also based out of Berkeley。

 it was Van Jacobson's group at LBL， Steve McCn， Martin Vely。

 who was on the faculty in E they wrote some of the earliest audio and video streaming tools on the Internet This was in the 90s actually。

So this is， I think， useful as a lesson in terms of， you know。

 we have as mental model often as people who design。Technical solutions of what the user wants。

 But sometimes when you hand a user a new technology， a user behavior changes。

So users moved to email and video。 users became more tolerant of video and audio quality that was valuable。

That's one other reason why I like to talk about reservations。

 Do you see something happening in a computing ecosystem today that might make reservations more or less relevant。

陶瓷行。So online gaming， I would say some people are even more concerned about things like ARVR or your self driving car where the repercussions of having to be adaptive。

It's a little unclear what it means to have an adaptive self driving call。 This makes people nervous。

 Certainly when people talk about remote surgery or things like that。

 they want that guaranteed bandwidth。Anyone都。Cloud computing。

 and so cloud computing is the one context in which if you talk to cloud providers。

 this is something they actually worry about。 And they have good reason to worry about in the following sense that when you go on your job in the cloud。

You get told you have so nis and you have so much memory。

And you begun your application and you know exactly what resources you have。

 and you can reason about the performance。You don't have the same abstraction because of in the network。

 So you can say I wanted 1 gig。ANe connection。 But that's only talking about the connection between your VM and。

Your network interface card。 So your first link， leaving your server。

Tells you nothing about the performance you can expect to see between two hosts。

And so it's actually cloud providers will joke where they say when they have a tenant who's seeing bad performance。

 the first thing the tenant will do is they tell the cloud provider your network sucks。

It's the network fault and they don't actually know whether it's the network fault。

 but the network is the one thing where it's not clear what performance you're getting into to end。

 and so a large number of cloud providers would say that they're interested in solutions that not across the internet that still seems like a really hard problem。

 but even within a data center， could I get some guarantee or some idea of what bandwidth I have between two VMs or two servers。

So think about that。 How would you solve reservations in that context， It's kind of a fun。F moment。

Without any questions？Okay， so then let's leave circuit switching and reservations behind from now on。

 we're going to live in the world of internet packet switching and I want to take five minutes or so to just do a slightly deeper dive on packet switching and how that works Okay。

 so we've going back to that early pipe view where we have a pipe and we have packets occupying the pipe。

The link。 And we were drawing it with in this fashion。 I now want to look at a switch。

 and I'm going to say this switch has these two links coming in。

And all the traffic coming in on those links at that switch is trying to go out on this pipe。

 on this outgoing link。So think of it from the perspective of the switch as these packets are going to arrive at the switch coming in on these two links。

Is there any problem receiving these packets and putting it out on the link？

In this particular example， no。At every point in time， the switch received exactly one packet。

 and there was enough capacity on the outgoing link。 There was no overload。

What if I had a scenario like this？Is there enough capacity on the outgoing link。

To accommodate all the packets that I have on the left。Someone says no， anyone want to say， yes。

 if I just summed up the packets and I looked at them。Outgo link。Yeah， in total， yes。

 but at this particular point in time， the switch has two packets that want to be sent out。

 So this is a scenario we call transient overload。In the sense that if I looked at the total demand for that outgoing link。

 I have enough capacity for it。But that at this point in time。

 because sources were bursty and uncoordinated and everyones best effort。

 they just send their packets in at this point in time。

 the switch cannot take two packets and put it out on the link。So we call this transient overload。

 This is not a rare event because we have bursty sources and packet switching。

 this happens all the time in every switch， any all of the internet you'll find this kind of transient overload。

 What would you do to handle it。行。So now in this picture。

 we're going to add a queue and the queue is going to store a packet。

 So when you had these two packets， the switch is going to pick one of them to send out。

 and it's going to put the other one in the queue。At the next point in time。

 the switch can now choose it has a packet in the queue that needs to go out and it has two packets on its links that also need to go out。

 So there's what we call a packet scheduling decision to be made here。

 Which of these three packets should I choose and it's subtle and by acute problem but we'll get to it later in the semester for now we're just going to say the switch picks the first packet that came in it's going to do first come first serve So the switch is going to take that blue packet out of the queue。

 Take the other two packets and put them in the queue。At this point in time now。

 the switch has these packets in the queue。 It has no packets on the links。

 So it's going to do what we call draining the queue。

 It's going to start draining the queue and send out packets from its queue。

 And it's going to keep doing this。 We had no problem。

The queue here was there to absorb transient births。So we have queuees in switches。

 and they are there to absorb these transient bolts。 But what if my traffic demand look like this。

And I had a queue。I could still put a queuee。It would a some of these packets。

We call this situation persistent overload。There's no magic I can do here。 I have to。

 I I cannot pack all of those packets on the outgoing link。So what am I going to do instead。

 I'm going to put some of them in the queue， but eventually。I'm going to drop packets。

And so this is why the network drops packets because you can only have a finite amount of buffering。

 And so if I'm under persistent overload at some point， I'm going to drop packets。

So this is one of the yep。Yeah。Yeah， so think of it as I deleted that memory。

I just released that buffer， and that data disappeared。Interesting question。

What else would you do with it。's what the thought， yeah。啊。Okay， great question。

 What else could you have done if you didn't want to drop the packet， What else could you have done。

O， that's also a good answer。 You could have sent it out to a different link。

 if I had a different link， you know， maybe a random link。Yeah， why not。 That's a random link。

Or you could have sent it if you had a different path。 That would be what networks do do。

 They'll send it on a different path。What else could you have done？

 There was a hint of the answer there， but。嗯。Yeah， so actually。

 how it works is you'll have a certain queue that has。 It's a buffer。 It's a memory buffer。

 And let's say I have buffer space to store  hundred0 packets。And packet one came in。

 I put it in the buffer。 And Ive filled up every one of those。Entries。

Like an array or something that had  hundred0 entries。 and I filled all hundred0 of them。

 And our new packet came in。So what do I do Normally。

 what I would have done is I would have copied the packet from the link to the buffer。

 but I don't have space now。 so I just don't copy it。Literally。

 that packet is gone from the universe。I'm going to go back to that question。

 what else could we have done if we didn't want to drop it？Well。

 I'm always sending one of them through。 The problem is I had two to send。

 So I'm going to send one of them， right。But I was going to drop the other one。

 if I didn't want to drop。The answer that was sort there was， could I have。Slowed down the。

Person upstream， Could I have told the switch that was sending me to me packets。

Stop sending me to me buckets。That a reasonable solution。有的。快。Upgrade the switch。 Yes。

 but that's very different time scale。 But yeah， that is eventually exactly what people will do is they'll say this link。

 just I keep dropping packets here。 I'm going to go upgraded。 This can take surprisingly long。

For example， we' were having discussions at Google around a link that they know has been overloaded for months。

Other thoughts。Say that again。Yes， so you could have told sources that they cannot send more。

More than this rate。 So this is kind of going back to the idea of telling the source hey slow down。

 I cannot handle this much weight。 And there is actually a protocol that is quite widely used in data centers these days where they have this notion of a pause message or pause film control where an overloaded switch will tell the switch is upstream。

 Hey， can you pause。It also gets tricky to do， right， because， you know， you have to pause it。

 then you kind of want to unpause it。 So how long are you pausing it for。

 to what degree are you pausing it for。 So this also can get pretty complicated。

Right so the question is how does a bidirectional link work Again。

 this is very much a physical layer thing typically you can have completely what we call a full duplex link。

 which is I can receive at 100 gig and I can send it 100 gig and those two are completely independent。

 This is not as true in wireless because wireless you have interference but for all the lectures and what we are talking about we're going to assume these kind of full duplex links the two directions are independent。

so just keep in mind， it's a nice observation， a nice thought that you could have had a different design rather than drop if you could have tried to throttle or pause upstream such as a question。

If I heard the question right is how do you choose which packet to drop Excel question is well that is yet another scheduling decision so just like you have this packet scheduling decision about which packet do I choose when I have to send three。

 which one do I choose it's kind of the complement to which one do I draw。For as we talk again。

 there's a whole space of things you could do。 you could say I'm going to drop the lowest priority packet or I'm going to drop the packet that's been sitting around the longest because it's already delayed。

 What for our model working model in this class is going to be you drop from tail drop so you drop from the end of the queue。

Right， so we're starting to design aldM and pause messages and so on。 So you're right。

 So the suggestion was， could we in the pause message give some information about at what point in time were pausing so that the upstream which has some idea which packets are not going to make it And so you have some idea of which ones to retransmit or which ones have successfully gone through。

 You could That's not how these protocols work today。

 This is a fair amount of complexity involved in that remember then you have to actually keep state about individual packets like which packet sequence numbers have。

You've been sending， which switches don't typically do。Remember that 10 nanoseconds I this。

 Every time we ask the switch to do more。 It's a fair amount of complexity。 Can we gonna move on。

 I want to update our thinking that in some of the earlier slides based on the discussion we've just had。

 we talked about packet delay。 And we said it was transmission delay and propagation delay。

 I'm now going to update that to say it's those two plus queuing delay because any time you spend sitting in the queue is time delay that the packet in。

Likewise， going back to that life of a packet so far， we said， packet arrives it a switch。

 switch forwards the packet to its next hop， and you repeat this until you reach the destination。

 I'm to update this now to say the switch can buffer or even drop a packet。

And this last step of the repeats until either you reach the destination or the packet is dropped。

So this is the impact queuing has on the life of a packet。So with that， if you look at this。

 you should now be able to identify two new challenges that we've introduced。

 and these are going to be two additional topics we're going to study。

 One of them is the reliable packet delivery。So we've just understood now that the network can drop packets。

One of the common reasons is because you've overflowed the Q or the buffer in the switch。 And again。

 I'm going to use buffer and Q interchangeably。 They mean the same thing。

But there are the reasons why you could drop a packet。

 if the switch crashed while it had a whole bunch of packet stored in its queue。So again。

 you could have drop packets， or sometimes link technology can corrupt because you know signal reasons。

 you can corrupt a packet。 So these are all reasons why you can lose a packet。

But the application ultimately wants that data to be reliably transferred。You don't want。

 depending on the context， you don't want your data to just mysteriously disappear。

And so we're going to have to design this question of how do we actually do reliable。Data transfers。

 given that the network is unliable。The other question topics that the library transport is actually going to be your second project。

 that's going to be keeping us busy for a fair amount of time and how TCP does reliability。

The other challenge that should have come to mind is this question of what we call congestion control。

 packetet switching means that network capacity is allocated on demand。But at the same time。

 every end host is independently deciding and starting flows and stopping flows and deciding how much traffic to send。

And this gives guys a very tricky scenario where， you know。

 how fast I send impacts the performance that you see。

 because we are both going to share a link somewhere。

And so we have to come up with a solution by which every end host。

Figures out at what rate it's going to send traffic into the network。

 and it's going to need to pick a rate such that the NOC is good performance。

 but it's not harming other sources。 And at the same time。

 we're making full use of the resources available in the network。

So it's going to be like a distributed rate selection process。

 And how do we do that and how do we adapt to it as flows come and go。

 So congestion control is a major topic that we're going to spend several lectures on and later on in the semester。

And so going back to our list of important topics for the semester。

 it was the list we've talked about before， reliability and congestion controller are the two other fundamental topics I'm going to add to this list。

And then what else just to wrap up that stream， what else are we going to do this semester。

 a few advanced or specialized topics， security， I'm going to talk about security throughout CS161 there's a much more in-depth study of security。

 The internet is full of security problems because no one ever designed it to be secure。

It's a sort of one sentence summary of why we have the CS161。

 half of it devoted to internet security。How do we the web， how do we organize download content。

 how the web works， how do we manage our networks and SDN。

 What else do we have on the path you know had this fairly simple model of switches in reality we have things like firewalls and load balances and more complicated devices in the network。

 we're going to spend some time on those and then we're going to talk about certain specialized networks like cellular networks。

 data center networks and so on。So with that， hopefully you have a。Good mapap of the。

Topics we're going to govern this master。 Let's take a。2 minute break。

 And then we're gonna switch gears quite a bit。でるこり。With。



![](img/a4d5006811219f07307dd8250bee290d_1.png)

W for source。 let's get started again， and I'm going way too slow。 We're going to switch gears now。

 we've done with the bottom up approach。 we've done the overview of topics。

 We're going to take a top down look at the Internet。 And as you'll see。

 it's a pretty different way of looking at it。嗯。So I just wanted to start really high level。

How do you solve a problem typically？So if you， you know。

 go to your an internship or you're given a class project and you're set told。Here's a problem。

 Go solve it。How do you go about this？ And this is。Not a deep question。

 It's a more mechanistic question。 What steps do you take。Y。Waking it down。Anything else？Yep。公共粉。

I want to ignore that answer。Perfectly good solution， but not what I was looking for y。

Bes strong potential solutions。The first one， define the problem it's always useful to define the problem。

 what are your goals， what are your priorities and then break it down。

 decompose it into tasks and abstractions and then finally assigning tasks to entities。

 assigning tasks to entities didn't make sense if you were doing all of the work or you were running it on you're thinking of a single piece of code that runs on your laptop as you'll see it's a hugely relevant question when we talk about network design。

So let's start with defining the goal。 I don't want to spend too much time on this。

 We've said this many times。 the goal of the internet or the task that the internet has to solve is to transfer data from one end hostst to another end hostt and to do that across multiple networks。

In a later lecture， we're going to come back and have a more philosophical discussion when we read the research paper about you know wass this the right goal。

 what about the other secondary goals and what was the right prioritization across them。

 We're not going to get into that right now， which is going to take it that our task。

 the problem we have to solve is move data from one end host to the other。

What I do want to spend more time on is this question of how do you decompose that task？

 So now that we know what our task is， how are we going to decompose it into tasks and abstractions。

And the question here is really all about modulularity， like when you build a system。

 I think Bob Glico said it best， modularity based on abstractions is just the way we do things。

You it down， you break down the task into these subpieces and you say this entire component or this entire module。

 you can interface with it through this abstraction of this API and you don't have to care about what's inside How many if you you know Ba Galikov。

So Baweiscope is a professor at MIT， she was won the Turing Award about 10 years ago or more I think now。

 she came up with the idea of data abstraction， really the foundation for object oriented programming and so for that and her work on programming languages。

 she won the Turing Award。If you've not watched it。

 you should really watch her chewing a award lecture。

 or she has a TEed talk to that's shorter and very nice。

 It's all about abstraction and modularity and white matters。So what is modularity you all know this。

 it's we take a system。We decompose it into units， and we say that this entire component。

 here's the abstraction or API by which you interact with that component。

It's crucial in building systems Its crucial because it gives us this separation of concerns。

 they are the people that build that abstraction or implement how that abstraction is going to be implemented。

 and then there are the people that use that abstraction without caring about how it's implemented。

This allows us to write code faster。 It makes code easier to maintain。

It makes the code easier to be used， right We all do this all the time。

And so it plays a crucial role in computer science and computer systems， even beyond systems。

 I would say， the trick always is to find the right modulularity。

And that's what we're going to do in today's lecture in the next one as we go top down。

So we're going to talk about network network systems modularity and in particular。

 internet modularity， as we wanted on the Internet。The need for modularity still applies。

 even when we're talking about a network or we're talking about the Internet。

 I would argue that it's even more important。Thatn't why。

Why is modularity something we obsess about even more in Internet context than when you're writing your favorite application。

That's a good point。 that if something breaks， if we knew exactly where the abstractions were implemented。

 we would be able to identify。Where where do you should from？

The problems are more complex and we need to break it down further。 Yeah。

's see a little bit more about why they're more complex。行。 so you all absolutely right， you know。

 normal modulularities about how you organize code。

And you have your code and you want to decide how you chunk it up， where the routines。

 the APIs and abstractions， and so on。When you talk about the internet or generally any networked implementation。

 that implementation is not just distributed across many lines of code。

 it's also distributed across many devices， like your end hoststs and your switches and it's distributed across different players that the client is very different from the ISP it' very different from the server。

It's also， in fact， even within the client， if I break it down further。

 you have your network interface card vendor， you have your operating system vendor and then you have your application vendor and because networking or usage on the internet is end to end。

 it spans application on one client host all the way to the application running on the server host。

 you have to reason about how your implementation is divided across all the entities。

 devices as well as vendors and entities involved along that end to end path。

So this is why we think so much about do we have the right decomposition？So with that。

 how do we decompose the job of transferring data between Nhot。

 I'm going to ask you to think about it。 But I wanted to start by just giving you an analogy in。

 you can tell we like analogies in this class， just as inspiration。

It's useful to have a picture to relate it to。 So let's say that we had in the real world you had to see use A And B and they want to exchange some nasty message with each other。

 right， This is data that's being communicated in the real world。How would they go about it？

 Let's say see what a guys to be。It folds a letter。

 the CEO folds a letter hands that letter to their administrative read。

The aide puts that letter in an envelope， puts CEOB's name on the envelope。

 and takes that envelope to FedEx。FedEx then puts this letter in a larger Fedex envelope。

Puts whatever addressing or， you know， Seet sauce code。

 Fedex needs to know how to send it to Fedex's network and then ships it out on Fedex's truck。

And then maybe it goes on that Fedex truck。 It makes it to some distribution center。

 gets on a Fedex plane， goes on another truck， makes it to the other CB's office， gets handed。

To C B's aid and then up to the CEO。 So if you think about， you know， the path that that network。

 that letter now is taking， let's think about the physical path that that letter is taking as it travels along。

 CEO on one side handed it to the aid。To FedEx occurs to the world using FedEx back up to the aid and back up to the C。

So we had， this is the physical path that data took。

 It went down from the CEO to Fedex across the world and back up to the other CEO。

That's kind of the physical part that the letter took。

But if you think a little bit about how communication is happening。

 where I mean communication as in who's actually communicating， like understanding the other person。

 it's almost like we have these layers or these levels。

And the peers at one level understand each other。 and they understand different things like the CEO understands a letter。

 The two CEOs both understood the letter。The two Aides understood the envelope with you know。

 this letter needs to go to my ICU。And the Fedex。Infrastructure understands only the Fedex envelope。

So peers at the same level understand the same thing。In this example。Ccially， no one else needs to。

 The CEO probably didn't even know it was Fedex。 They don't care whether it's Fedex or UPS。

That's not something they have to worry about。 Fedex doesn't worry about what's inside the envelope。

 It's not their problem。So。You're starting to see hopefully some separation of concerns coming up here。

The other thing is that the lowest level has the most packaging。

 So if I stopped that Fedex stock on the street and I took that envelope up。

 I would see a Fedex envelope if I opened that up， I would see the AIids envelope。

 if I opened that up， I would see the CEO's letter。 So all of that information was there。

 It was kind of wrapped multiple times。And it was gapped in such a way that every level gets to understand only what they need to understand。

So that's kind of the analogy now think about you know with that as framing。

 how would you break down the internet into tasks and just to narrow the scope。

 I'm not asking you everything on the Internet control plane routing algorithms。

 I'm asking you very specifically the data plane if you wanted to transfer data from one endhost A to an endhos B。

How would you do it？So take a minute just to think about it。

 and then I'll walk through what the Internet actually does。 But it's useful。 use the CEO template。

 see how you would break things down。And so just to the people。

 don't worry about control plane tasks like routing algorithms and so on。O。诶。

Hope you've at least some idea on your head about how you would have built the internet or how you would break down this task I'm going to walk through what the breakdown of tasks is if this seems completely disconnected or you think it's going stop me and ask me why we're doing it this way。

 but if I had to start thinking about how I get data from point A to point B。

Starting at the very lowest level， I have to be able to get bits across a while。

So somewhere I have to know how to make that laser do the right thing or get my radio to send out the right signals。

 That's to get bits across a while。I then't have don to know how to get packets across a while。

 This notion of a unit of data， the set of bits that form a packet。

I then need to be able to deliver packets across a local network。

 Let me spend a little more time on this。 We've said that the Internet interconnects multiple networks。

So I can have one network that's an ethernet network， I can have one that's a wfi network。

 I can have one that's a cellular network。 if I send a message to the cloud， I'm on my phone。

 I'm probably going to go over the cellular network。

 then I'm going to go over some ISPs optical network that I'm going to hit the cloud provider and go through their ethernet network that they have in a data center。

And we said the internet interconnects these networks。

 So each of these networks has to know how to take this unit of data packet and move it through its own network。

So Ethernet has to know how to get an ethernet。We call it a wh。

 but an ethernet packet across the Ethernet network。

Or a unit of data across the cellular alone network。Okay。

 so that's delivering packets across the local network。And then， you know。

 each local network is just moving packets across its own network。

 We need some way of getting that packet to move across different networks。Okay。

 so that's going to be what we call delivering packets across multiple networks。

 And that requires a global address。So I I'm using the Ethernet network to get my packet across Ethernet。

 and then I'm using the fiber network to go across the fiber network。

 but I still need some way of reasoning about how my packet gets to into it。So for example。

 in the CEO context， the address， the postal address of the CEO。

 you know is the global address we all know how to or the entire postal delivery system knows how to get the packet beyond envelope to。

And then finally， and this is starting to get Internet specific。 You。

 we said we could drop data so we need to make sure we can deliver that data reliably。

 We have to be able to compensate for the fact that the network is dropping。Didt。

And then finally the application， you have to do something with that data。 That was the whole point。

So in practice， there's two steps here that we tend to combine into one。

 which is getting a packet across a wire and getting a packet across a local network。

 and that's because it tends to be the same technology。

 right if I have an ethernet network that has four ethernet links it's kind of the same technology to get an ethernet packet across one link and then I'm using ethernet technology again to go across those four links So we collapse that into one and we just say we're delivering。

Best at delivering packets across the wire and the local network。

Does this look like a reasonable breakdown。Probably doesn't cover everything we want to do， but。

Any questions。

![](img/a4d5006811219f07307dd8250bee290d_3.png)

，So now let's start to look at that， you know， in a little bit of that context of levels and layers。

 So in the Internet， the organization we have is at the very lowest layer。

 we worry about the physical transfer bits。Building on top of that。

 we have the abstraction we provide is the best effort packet delivery across a local network。

So it's across an ethernet network or course a cellular network。

And then we build on top of that to do best effort global packet delivery。

And what I mean by build on top of that is in order to achieve global end to end packet delivery。

 I'm going to use the ethernet network's ability to transfer packet across the Ethernet network。

 And then I'm going to use the cellular network's ability to transfer packet across the cellular network and so on。

 And so I'm building end to end delivery out of this building block of local delivery。

And that's why the Internet interconnects networks。Then on top of global packet delivery。

 I'm going to do how do I do reliable data delivery。And I switched two things and going。

To this layer，1， I went from best effort to goel。IfWe all understand what that means， I'm going to。

Do some work at this level in order to make sure my data is getting across reliably。

 But I also switch from packet delivery to data delivery。And this is a remember。

 because we said applications think in terms of data。

 I think they have that image that file that they want to transfer。

 They're not thinking in terms of packets。And so this is the layer where we're going to switch from thinking about data to thinking about packets。

This is going to be the layer that takes that data and chunks it up into packets and worries about putting those packets back into a file or putting it back into data。

And then on top of that， we're going to have applications。So， we call。I'll get you。 just say。

 We call this a strict layered architecture。 What I mean by that is applications。

 the abstraction that they build on top of is that of reliable data delivery。It's an application。

Doesn't worry about what link is underneath or exactly how you。Aieeved reliability。

 It just thinks that it gets reliability data delivery。Which builds on top of this global。

Best effort packet delivery。 So the layer above the global delivery doesn't worry about how the packet got across ethernet networks or fiber networks。

 It just thinks I can get best effort end to end global delivery。

Which builds on top of local packet delivery， as I mentioned， which builds， again。

 on top of the physical transfer bit。And there's other questions on there。

You can have encryption at multiple levels， so you could be encrypting at the application。

 You could be encrypting on a full packet basis。 so we'll get to that in the future lecture。



![](img/a4d5006811219f07307dd8250bee290d_5.png)

AndSo we call this a layered architecture。 So a layer is no different from a component or。

Element of modularity in any system decomposition。 What is different， however。

 is this strict layering that when I say I have a layered architecture。

 one layer can only interact with the layer above it and the layer below it。

So it's using the layer beneath it in order to implement its functionality。

And it exposes some API or some interface or some functionality that is used by the layer above it。

So that's kind of this strict layering organization。

And two layers will only interact only through the interface that one layer exposes。

If this sounds vague， it's going to get a little bit more concrete as we go。

 let's keep going for now any questions。

![](img/a4d5006811219f07307dd8250bee290d_7.png)

So going back to this picture， we said we have this breakdown of tasks they're organized in a strictly layered fashion。

This is why we say when we say the internet has a layered architecture。

 this is exactly what we mean every one of those functions or that layer corresponds to a layer in the Internet architecture。

 so we say we have five layers in the Internet architecture L1 is the physical layer L2 is this best effort。

 local packet delivery we call it the data link layer。L3 is what we call the network layer。

 That's this best effort， global packet delivery。E4 is where we get reliability and data transfer。

 That's the transport layer。And L 7 is what we call the application layer。This is not a typo。



![](img/a4d5006811219f07307dd8250bee290d_9.png)

It's actually L7， just a historical note in the early days of the internet when they standardized these layers there wasn an L5 and an L6 L5 it was called a session layer。

 its job was you know for example when you have a browsing session。

 you have many flows and they're kind of related to your browsing one is getting images one is getting ads one is getting content and so they thought we should have a layer that deals with sessions as an。

Agoate or a combination of flows and the session layer was going to be where we did that。

 And then layer6 was going to be a presentation layer， which is how how should users visualize data。

 How would you help applications with different ways of visualizing data Those functions totally over engineerineed that's why it's disappeared from use Those features do exist。

 People just tend to implement them in the application layer。I had a question， but I won't get it。

 Okay， let me see if I can get it， get through it in the last one minute。

 Why do we have transport layer。

![](img/a4d5006811219f07307dd8250bee290d_11.png)

So we said， going back to。The other slide we said here that we had。

A layer that's dedicated to doing reliable data delivery。 Why not put that in the application。有。

We actually do reliability into end。 so I'm going to in principle what you said could have been true that's not quite how we do it。

 So actually I'm going to leave that question for you to think about why do we have a layer4 transport protocol and we'll pick it up next time。

Next。

![](img/a4d5006811219f07307dd8250bee290d_13.png)