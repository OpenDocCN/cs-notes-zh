# UCB《互联网导论：架构与协议｜CS 168 Introduction to the Internet： Architecture and Protocols》 - P24：-22- Software-Defined Networking (SDN) (Scott Shenker - UC Berkeley).2022 - GPT中英字幕课程资源 - BV1VcrrYUEL5

Okay。Good morning。Thank you for coming I want to apologize once again for。

Disrupting your schedule and showing up unannounced or announced within the last 10 hours。啊。

So I also， I'm going be talking about software defined networking， which。Presumably。

 most of you have not heard about at all。So I will explain where it came from and why you might spend 80 minutes listening about it。

But before Warren that。This is my first classroom lecture in four years。 So this is going to be。

Rough。At least my practice runs were， please ask questions when I'm floundering so that we don't all have to have the embarrassment of an old man just muttering to himself。

啊。But at several points in the lecture， I'm going to ask a question。

I don't really want you to answer。 It is my signal to you to go think about this question。

I'm going to shut up for a bit。 My problem when I listen to lectures is when the speaker says something interesting。

 I start thinking about it， I lose track。 So this is my signal to you。

 You can actually think about something for a little bit， and then I will bring you back。

And the lecture is going to start very slowly with lots of generalities。

That's because software defined networking or SDN， it's a solution to a problem。

But if you don't understand what the problem was， the solution is going to appear completely unmotivated and boring。

So I'm going to provide a lot of background on the context， but things do get more specific。

Toward the end。 So the goal for today。Is to provide the why of software defined networking。

Why it was needed， why it came about。There'll be some history， some gossip。And some postta rationale。

 I'm not going to tell you what we were thinking at the time because that's too embarrassing。

 but I can tell you what we should have been thinking at the time to make it all make sense。

But there's almost none of the real how of how SDN in the real world works today。 you know。

 there are a bunch of papers you can read。 Sylvia is actually working on some ways to improve SDN over the ways that you know it's original。

Design， but， but the main point， at least what you should walk away from this class。

 isn't about the details of the how， but a sort of the why and the overall structure。Of the answer。

Now， what I am presenting is the canonical， ideal version of what SDN looked like if it went straight from。

 you know， a paper or a textbook into real networks。 But that's not the way it worked。

 So nobody uses。SDN in the form， I'll be describing it。

 But what they do use sort of resembles this conceptually so that this clean form is the right way to learn the conceptual foundations。

 And then if you ever do go into networking， you'll find out what's going on in the real world。

So I want to begin with two questions。First， what is SDL？So SDN is a way of managing networks。

 I will make that more precise， but it's sort of。Not how you actually physically transport packets。

 but sort of how you manage how the network transports packets。

But it is not revolutionary technology。 You're not going to sit here and think， wow， you know。

 I never would have thought of that。 Or this is magic。It's just a way of organizing。

Network functionality。So why should we waste an entire lecture on how to organize functionality？Well。

 you're actually wasting an entire semester。On the Internet architecture。

 and that is just about organizing functionality。 There is nothing clever。

In the Internet architecture， there is nothing that if I told you design a transport protocol。

 Here are the requirements， you could have done that。

What was magical about the Internet is recognizing that by decomposing things into those four layers。

 you could build an architecture that has remained functional and essentially unchanged for 40 years with。

 you know。😊，8Order of magnitude increases in speed，7 orders of magnitude increases in size。

 That's magical。To design something that lasts that long。So。That。

 that's the deep wisdom of the Internet architecture is that it could withstand all that。

 Not that there is some piece of cleverness in it。So I can tell you up front。

That there is nothing clever in SDN。But we can hope that it's wise。

But we won't know this for 30 or 40 years。Okay， but thats， that's all SDN is， the way to organize。



![](img/29e5a62f4d2f55d9599d2b2009af5ab7_1.png)

The management of networks。So where did SDN come from？So。About 2004。 So you'll find it in。

 in many fields when theres a new idea。 Actually， there are many different groups who've been thinking about it。

 And so that's true about SDN。 that around 2004， there were groups that。

Princeton and CMU that werere doing something called RCP in 4D。

There was a group at Stanford and Berkeley that was Nick NCune and at Stanford。

grarad student Martin Casado， and then myself that were looking at design s and ethane that were sort of had very similar flavors。

 and then there were a bunch of industrial efforts， most of which have gone unpublished。At Google。

 Microsoft， and AT&T and other places， all of which had a similar flavor。

 some of which we didn't know about， particularly the industrial efforts at the time。

 but there was a lot of this stuff that started around 2004。That in 2008。Sort of SDN became a thing。

The name came from actually the MIT technology review， none of us picked it。

 just a writer there decided that's what to call these things。

 and then there were two sort of early papers， the Knox network operating system that came out of a startup named Nisra and the Open flow switch interface。

 which came out of Stanford Nissra。Now， just in terms of gossip that Nisra is a company that came out of。

 was founded by Nick Martin and myself。And。Unlike a lot of startups where， you know。

 originally had an idea and you went and you tried to commercialize it。

 we tried to do everything but。We have this idea。 We took it to all the routed vendor。

We told them about the idea。 We begged them to think about it。 And they all。Just ignored it。

And then we finally went to Cisco。 We had good friends at Cisco。 So we went。

 we presented Martin presented the ideas， and they told us basically we were fools that it wasn't gonna to work。

 It wasn't gonna to scale。 It was going to fall apart of it。

 And we yelled at each other for an hour and a half because these were friends。 So we。

 we could have an honest discussion。 at the end of it， I got up。那什我。

You're not listening to us anymore， we're not listening to you anymore。

But I will bet my house and we're going to kick your ass。And in the。Parking lot。

 we decided to do a startup because we just couldn't get anybody to listen。So， that's。

Howundndasro was formed to try and get this technology out into the world。

Then only three years later。The Open networking Foundation。

Came into being that was the sort of standards body。For。Software defined networking。

 and it had everybody who's in networking， all these companies join。

And what was remarkable about it is the organization had very strict。

Intellectual property requirements that said basically anything you do or say in here zone goes into public good。

 you can't sue each other over any of these related technologies。

 we were told by various companies nobody will ever join everybody did。

So this is like three years after the idea that it had become sort of。

A widespread organization with like 200 members， industrial members。

But that's actually not a very honest story about where SDN came from。



![](img/29e5a62f4d2f55d9599d2b2009af5ab7_3.png)

Because the true story is it came from Martin Casado。 He actually sort of was interning at Iixie。

 came into my office and sort of explained this idea about how you should manage networks。

And that was sort of the birth of SDN。 it you， modified over the years。

 but it basically just came from our team's head， and Nick and I were just sort of passengers on the ride。



![](img/29e5a62f4d2f55d9599d2b2009af5ab7_5.png)

So what what's the current status of SDN？It's I think sort of universally accepted。

 at least in its conceptual form。As the right way to do networks。It's commercialized。

 It's in production use， the business units who sell it， you know， have huge and growing revenue。

knowThe Googles and the Microsofts and the Amazons of the world all use it。

 the carriers have sort of adopted it。It's not fully adopted by router vendors。

 it's sort of hard to tell whether they've actually taken in much of the ideas at all。

 So in this talk， I will catch myself at times referring to the present tense as the time before SDN。

 So if it's confusing， just to ask me whether I'm referring to the SDN time or the before SDN time。

Because the the sort of， the hyperscalers have totally adopted it。

 and the router vendors have almost not。And I think I will explain later why I think that's true。Now。

This will be very hard for you to imagine that anybody cares about anything other than machine learning。

 because that that's the state of the world today。 But in the early 200s。

 networking and the Internet were the big things。And SDN。Had an insane level of hype was。Just。

 you know， it sort of not only captured the imagination。

 but but it became this sort of it's going to solve everything and then it came crashing down because it's not。

 it's just， it doesn't work miracles， merely makes things easier。

 but what it's one of the more extreme hype cycles that I've ever seen。



![](img/29e5a62f4d2f55d9599d2b2009af5ab7_7.png)

嗯。But it eventually， as you saw on the first bullet。

 it did get adopted even after the sort of hype died down。But the real question。

Is why the rapid adoption from know the first papers in 2008 to a standards body in 2011 that had everybody involved。

How could that happen？You know， this is incredibly fast for any field。

 but particularly for networking， which is hardware based。

 and that changes very slowly and standards based， which change even more slowly。

 So why did that happen。So。When a technology is adopted so quickly。

 it must be answering some pain point。It's especially true in networking because of the hardware and the standards base。

 it's got to be a very extreme。Pain point， so what was that pain point？

So the one thing that probably， So there are two pain points I want to talk about。 The first one。

You're probably not going to read about certainly not in a textbook。And that is。

Cisco is extreme market power that if you look at the networking。呃。Sort of ecosystem back then。

 And I'll get these figures wrong。 but conceptually the right。 Cisco had like 80% market share。

 They had 60% profit margins。 If Cisco had a bug in their code and you were a router vendor。

 you had to be compatible with their bug。 We called it Cisco bug compatible。

 that it didn't matter that you were right and they were wrong。

 You had to mimic their bug because everybody used Cisco and you had to interoperate with Cisco So they dominated the market。

So anybody who wasn't Cisco wanted any technology that might hurt Cisco because it might help them。

 So that's why everybody joined， even though they had to give up intellectual property rights to a lot of ideas。

 just because。You know， Cisco was so dominant that， you know。

 there was no other way to break into the market。 So that explains why the vendors were so fast to adopt。

But doesn't explain why users would care。And so most of this lecture will be about why users cared。

And that's the poor state of network management。

![](img/29e5a62f4d2f55d9599d2b2009af5ab7_9.png)

And so I'm going to now talk about network management， but I want to answer any questions。Not O。

So what is network management？So I'm sure you've heard about the two planes and networking。

 There's the data plane， which is a packet comes in。 I look at the packet header。

 I look at my local forwarding state。 I make a decision like， you know。

 this is the destination address。 It should go to this you know destination address。

 I look at my routing table that will tell me what port I should send it out and I send it。

That's the data plane。That's IP well understood based on local information。

And then there's the control plane， and that's how you compute that forwarding state。That's how you。

 you know what to do with the packet。 And that necessarily involves the rest of the system。

 where it's the data plane。 I don't care what anybody else is doing with the packets。

 I'm just doing what I care about。不。Like for routing， I care about what the network topology is。

 So I need to know about the rest of the system。And so that the control plane involves coordination with the rest of the system。

 And so my definition of network management here is really everything that has to do with the control plane。

 Anything that sets up that state。Whether you do it， manually。

 whether you do it through an algorithm， however you do it， that's the control plane。



![](img/29e5a62f4d2f55d9599d2b2009af5ab7_11.png)

Now， when the Internet was first invented， the goals for the control plane。Were really quite simple。

Basic connectivity。So you just say。I have a packet， I'm supposed to deliver it from here to here。

I look at the packet header。 I look at my local forwarding state， and I just deliver it。 I'm done。

So you have these。Global distributed routing protocols。Global here sort of means within a domain。

 When domains started getting defined， then global here means within a domain。

And then the other goal， when domain， when interdma routing finally took hold in the Internet was。

 how do I route between domains。And that's again， basic connectivity。

 except that you now have to be policy compliant。So basically。

 you had who the two goals were connectivity within a domain and policy compliant connectivity。

Between domain。That。That's all the internet had to do。So the control plane was just about routing。

And people worked on routing algorithms， but nobody thought network management was hard。🤧。

For a long time， these were the only relevant goals。So what other goals are relevant now？

What's made the networks more complicated？

![](img/29e5a62f4d2f55d9599d2b2009af5ab7_13.png)

So here are a few examples。 There's isolation of logical lands。

 these L2 networks that I think you just talked about。So in an L2 network。

You have these broadcast protocols， that things like DHCP。

DHCP broadcast their messages so that they up reachach all of the DHCP servers。

 You don't need to know。Where they are， they don't need to know where you are in the beginning。

So you have these broadcast protocols。They can also be used like Apple's bojour to find printers。

 You broadcast a message， and that anything that identifies as a printer can respond。

 and you can find resources。 So these， these L2 broadcast messages are very useful。

But they don't scale。 I you can't do this if you have a network with you know 100 million hosts。

 you can't possibly scale to that level。 And it's also invasive。

 I may not want people knowing where my printers are or other resources。

 I only want to reveal that to people within my group or local organization。

So what people said is what we really want are these logical L2 networks。

That we want to limit the scope of broadcast so that a broadcast only goes to a limited scope so I can find out the server you know。

 let's say the printers that are nearby， but nobody who's far away from me can find out about my resources。

 So that retains the usefulness， but it copes with scaling。And to provide some degree of isolation。

 So these became very widely used， these V Las， these virtual lands。

Of whichch is just a tag in the L 2 header， that says。You know。

 you configure figure a switch so that it sees when it's got this tag， which ports it should。

Forward the packet。嗯。So it controls where these broadcast packets go。

 It can create multiple L2 networks， and routers are used to connect them。

So these are very widely used， but there's no magical way of setting these V L。

Configurations that typically theyre， they're administered by scripts or by hand。



![](img/29e5a62f4d2f55d9599d2b2009af5ab7_15.png)

AtLe， you know， when I say now， I mean， this is in the， the sort of。15 years ago。Then access control。

So， you know， if you're running a bank。And somebody walks into the lobby and connects to Wi Fi。

 You want to make sure that they cannot connect your backend server that contains the bank balances。

 So you have to provide some kind of access control。For security。

 and these are imposed by routers using what we call as or access control lists。

That basically say things like。If your header looks like this， then what action do you take。

 So you might say， if you're not using port 80 that I' going to drop your packet or if your source address comes from the addresses I'm handing out of the lobby。

 I'm going to drop your packets。 So you have these set of rules about what you do with packets。

These these as， and they're used for security。 And again。

 they're typically configured manually or through scripts。

 There's not some automatic distributed algorithm to do these。



![](img/29e5a62f4d2f55d9599d2b2009af5ab7_17.png)

And then there's traffic engineering。 So， you know， if you've got a big network。You have， you know。

 traffic， you have a traffic matrix of， you know， from each site in your network。

 you're sending a certain amount of traffic to all the other sites。 That's a matrix。

 and you want to route your traffic in a way。 So none of the links are overloaded。I mean。

 congestion control can do its thing， but you still want to avoid overloading certain links。

And so you want to choose the routes to spread out the load。

There are a bunch of methods for doing this that that I I won't go into here。

 but it's typically done with a centralized computation。 I， I take this traffic matrix of， you know。

 where does this site typically send its traffic。And then I figure out what are the set of paths that I want these traffic to take。

 So none of the links are overloaded。 I do that in a centralized computation。

I figure out what the routing state should be， and then I push it back out into the network。

So the point is that while network management in the beginning have just connectivity。

 That was your goal。 You develop routing algorithms， and you're done。Now you've got many goals。

All of these goals are the job of the control plane。

And currently the control plan by currently meaning that the state of the art 15 years ago， you know。

 these mechanisms can be globally distributed as in routing algorithms or manual or scripted。

 like as or V Las or centralized， like traffic engineering。 So you've got all these mechanisms。



![](img/29e5a62f4d2f55d9599d2b2009af5ab7_19.png)

And the bottom line is that there are many different control。Plain mechanisms。

Each design from scratch。 we want to design a new route and you just， you start from scratch。

 You don't build on anything else。And you've got all these different implementations。

None of them are particularly well designed， like the scripts they used to set up fieldlands and so forth。

 that they haven't had the 30 years of attention paid to them that we have to the data plane。

So the network control plane as of 15 years ago， when we started this work was a complicated mess。

With mediocre functionality。So that was the pain point is that。Controlling networks was really hard。

 And it's a big contrast with a simple and functional data plane that has remained unchanged and still works。



![](img/29e5a62f4d2f55d9599d2b2009af5ab7_21.png)

Any questions at this point？Okay。So。How have we managed to survive？Because networking works。

So and it's basically your network admins。They're the ones who have to handle all this complexity。

And the nice thing is that that the networks got more complicated。

 The control plane got more complicated。Gradually， so network administrators sort of coped with the complexity as it came。

 and they understand all the aspects of the networking。

 And they've got to keep all these details in their mind。 And I remember talking to them。 you know。

 when we were starting the company。 And you'd ask them how the network works。 And no no， in OSPF。

 no no， you've got this field and that flags not。 And this isn't going to happen。 And you。

 like how they kept this in their mind was mind boggling。嗯。And networks。

 and at least networks at that point required these large expert admin staffs。

 and if you compare like the number of admins you need per router to the number of admins you need per server。

 it's off by a factor of 10， at least， it's just sort of managing a network was much harder than the kinds of things you do for computation。

And so this is how we survive by having these people whose。

 whose job it was to master this complexity。So this ability to master complexity is both a blessing。

And it's a curse。

![](img/29e5a62f4d2f55d9599d2b2009af5ab7_23.png)

So now I'm going tell you a story about why it's both and the difference between the two。

So just as background。I did my training as a theoretical physicist。 I took a postdoc in physics。

 and then I joined Xerox's Palo Alto Research Center。 Do people know what Xerox Park was。Not okay。

 not many。 So Xerox Park was basically where modern piecess were invented and modern interfaces were invented。

 It's what Apple。I don't want to say stole。 I mean， Steve Jo visited。

Jox Fox showed him all the technology。 So it's not like， you know， he stole the technology。

 but that's what the Macintosh was built on was copying these ideas。So。



![](img/29e5a62f4d2f55d9599d2b2009af5ab7_25.png)

I arrived in 1984 and in 1985， so you， a year， year and a half after I joined。

Don Norman came to visit Gerard's Park。Now， you probably haven't heard of Don Norman。

 either Don Norman was lead UI designer at Apple。So he was coming to park， so here is Apple。you know。

 I was a physicist。 So like my ego was not involved in this。

 but like certainly the computer scientist at Sherack Park thought， we invented this stuff。

 We know about user interfaces。 How could somebody come and tell us， you know。

 you who built the Mac this cheap piece of shit。 You know。

 how dare you come and try and tell us how to build user interfaces。 You know this was。

 so the auditorium was packed with， you know，300 engineers mostly mail lots of energy in the room。

And so Don Norman is introduced he， he's a charismatic man， even older than I am。 And he came up。

It just comes upon you。Just looks at us for， you know， it felt like forever。

 but it was probably 30 seconds， but he just looks at us， and then he said。How many of you？

Drivever's stick shift。So do you know what a stick shift is？Okay， so manual transmission。 So。

 it's very hard to get a manual transmission in the US。 It's more popular in Europe。

 But so back then， it was。A littlettle more popular。But actually。

 it was still unusual to be driving a mail trip。 Well， but， you know， this is a bunch。

 mostly male engineers。 So a bunch of hands went up。

 And you could tell them if I drive a stick shift， you know。And so he looks at us， and he says。

None of you should ever design a user interface。😡。

![](img/29e5a62f4d2f55d9599d2b2009af5ab7_27.png)

Didn't go over。So what was his point？😡，Why would he come？

And ask about5 shifts and then tell us that we shouldn't be designing user interfaces。Well。

 his point was， and this really just， you know， worked my mind the ability to master complexity。

Great， it's valuable， but it's not the same。Is the ability to extract simplicity。So each has a troll。

 So when you're getting a system to work for the first time， you've got a master of the complexity。

You know， so like when we were first building cars， we had to， you know。

 we had to shift gears to make sure that the RPMs didn't got， you know。

 we didn't burn out the engine。 That was our job because it was still。

 it was a miracle that the car worked in the first place。

But when you want to make a system easy to use。Basically， you extract the simplicity。

 And so what is your automatic transmission， Do you want to go forward。

 Do you want to go back or do you want to park。Just tell me that and I can handle the rest。

So that's basically what automatic transmission is。 Give me the high level specification。

 I can't decide whether you want to go forward back or park。

 You have to tell me that I will do the rest。So that extracting the simplicity is trying to say。

 what what， what kind of external input do I need and I'll take care of everything else。

But there are two different skills。And his point was。You'll never。

 succeed in extracting simplicity if you don't recognize that it's a different skill set。

And so his point was， if you enjoy driving a manual transmission， then you like mastering complexity。

 That means you probably shouldn't be the one trying to figure out how to get rid of it because you like it。

😊，This is something you like doing。 So that was his point。



![](img/29e5a62f4d2f55d9599d2b2009af5ab7_29.png)

So what is my point？So why would I bring this up？So networking had never made the distinction。😡。

And so had never made the transition from mastering complexity to extracting simplicity。

And what I mean by that is， until SDN。The networking field just focused on mastering complexity。

 The networking experts were the ones who knew that in OSPF。

 there's a special field that if you said that， things will work。

 And if you don't it's going to fall apart。 and they thought that was a perfectly fine way to run a protocol。

You know， because the people who knew it， they knew it， but。Network management。

 as you had these increasing demands on network management to do more and more complicated things。

 then that just wasn't enough。So simplifying network management。Requires extracting simplicity。

And we had never bothered to do that before。For the control plane。Just never happen。

So how do you force people to make the transition from。You know，I'm a master of the universe。

 I can figure out how to get this done。 Why do I need simplicity？You know， we're really good at it。

 You know， the people who ran networks， They were really good at it。

 It wasn't that the networks were failing， and it worked for us for decades。

 How do you get people to change。So in general， how do you make people change？

It's one very simple way to do it。W does you make them cry？

So I'm going to tell a story about me and how I cried。😡。

And this is sort of what happened in our field。So I love math from an early age。

And my father was an experimental physic。 you know， he would occasionally talk to me about it。

 And then I， you know， I don't know what grade it was 7th or 8。

 or whenever you learn algebra back in the dark ages when I went to school， but。

He could tell I wasn't learning algebra。I was doing fine， but I wasn't learning algebra。

 So he asked me about it。 You know， I would show them the problems。 I'd say， yeah， yeah。

 the answer is2 and what。I get it in about five seconds。You know， I was doing fine in the class。

 but he could tell I wasn't learning algebra。And so he finally sat me down， he said，Scott。

Your problem is， you're too good at arithmetic。So you're not bothering to learn algebra。

And so what did he do， And so I said， you know， I don't need help。So he gave me this problem。

So what did I do？I cried， and then I learned after。Because I finally realized no。

 it wasn't going to work。 whereas， in class， they give you these simple problems。

But once you started giving me hard problems， I realized I was never going to be able to solve those。

 so I learned algebra。And， you know， that's the story of sort of。

 you have to make people actually realize they've hit a wall。Before the change。



![](img/29e5a62f4d2f55d9599d2b2009af5ab7_31.png)

So the question is， how do you make network operators cry？

And here it's what convinced network operators that they needed STM。And。I'm going to tell this story。

And its it sound like we at Na Sierro or Martin in particular were brilliant about this。 And we。

 you know， we just got freaking lucky。So the timing。

 we had no idea how to make them cry when we started the company。嗯。So。

The way you make network operatives cries， you first。You make them manage large data centers。

Hundreds of thousands of machines， tens of thousands of switches。People were running these。 you know。

 pushing the limits of what people could do， but they could do them。But then。

 and this is what tipped the balance， Multi tenencies， meaning that large data centers can host。Many。

 many。Customers。That's what gave rise to the modern public cloud。

Each of them think you need to give them the illusion that they're managing their own network。

So if there are 1000 such customers， you take the numbers I gave you before。

You add three orders of magnitude。And it went way beyond what anybody could handle。 Nobody said， oh。

 no， no， don't worry about， give me an extra week。 and I'll be able to handle this。 They flat out。

 just could not do it。Now， did we know that multi tenantant data centers were。Coming。Absolutely not。

They came to us， but we had no idea they were。

![](img/29e5a62f4d2f55d9599d2b2009af5ab7_33.png)

So these network operators。😡，We're now weeping。 They just could not handle this。

 So they'd been beaten by complexity。And so the era of these ad hoc control mechanisms was over。

You needed something else。So we needed a simpler， more systematic design。

 We couldn't do arithmetic anymore。 We needed algebra。

That's what people realize is we finally need something different than what we were doing before。

But I want to note。The contrast， both to admit how stupid we were。 but also。

 so we thought when we founded Nisra that， oh， SN， you know， all this network control。

 people who need security， they're gonna to love us because you can really make sure that people in the lobby can't access。

 know， you can make sure programmatically and do all this stuff。

 So we'd go make the pitch at banks and they's not they very interested。 know。

 And then we'd call back the next week you know， we're okay with Ales and V。You know， it works。

Then when we stumbled across these multi tenantant data centers。We talked to them， we explained them。

 you know， they said， no， you know， we're really interested。 We said， but but it doesn't work yet。

And this is when you know you've got a product market if they said， we don't care。You know。

 they had no other way of doing it。 So they'll take the technology and try and make it work。In that。

That's when we， that's how we found people were willing to adopt the change。

 not by selling to the people who were doing okay， but we had a better solution by people who were just。

Just dying under the burden of complexity。So that， so the answer to the question of why the rapid adoption。

 that was it。 I mean， it's both the Cisco problem， but also that that these multi tenantant data centers were by far the fastest growing niche。

 This sort of the biggest area of greenfield network expansion。And they needed SDM。

And so all the router vendors were shifting to that because it wasn't where Cisco was particularly strong because it was a relatively new market and that SDN was the solution。

So。What do we do now？嗯。You know， I mean， going back in time that sort of we。

 we recognize that we can't do。Multitenant data centers with our standard techniques。

 how do we design SDN？So we've been defeated by complexity in data centers。

 we had to extract simplicity。And so the question is how do you extract？Supposed。

So this is something computer science has been doing。Its entire lifetime。

 So let's think about programming。 You know， in the beginning， you had no abstractions。

 You had to worry about where every bite was stored and how to extract it and what to do with it。

 and mastering complexity was critical。Then you went to higher level languages like operating systems that gave you files systems and the like。

 and so you didn't have to worry about every little byte。

 you just worried about files and transacting with files and then we had higher level levels of object orientation and garbage collection and so forth that took up care of a bunch of other things。

And so abstractions are the key to extracting simplicity。



![](img/29e5a62f4d2f55d9599d2b2009af5ab7_35.png)

And so there's a brilliant talk by Barbara Liskoff with her turn award talk。

On the power of abstraction where she just boiled it down。

 which is modularity based on abstraction is the way things get done。

 it basically says in computer science， we have one trick。It's modularity from abstraction。

 just if you want to build a big usable system， This is what you use。

 It's the only way to build a big usable system。That's because abstractions。

Give you interfaces that is behind the abstractions or some functionality。

 you don't need to know how it's implemented。 you just have this interface and you have this nice。

 clean modularity where you know， somebody else will take care of this。

 I just need to take care of what I'm taking care of。Whereas， you know， I'll explain later。

 But routing algorithms weren't like that at all。 They had to do everything at once。So if， if。

If abstractions are the way you think about networking。

 what about the current network abstractions at the time？

So we going consider the data plane and the control plane separately because they have very different jobs。

 So it's not like they have the same set of abstractions。



![](img/29e5a62f4d2f55d9599d2b2009af5ab7_37.png)

So。This， I'm not sure if you've seen this picture， but it。

 but the idea should be very familiar to the data plane has this brilliant set of abstractions。

That if I'm building an application。I built it on top of a reliable by stream。Abstraction。

So I stick bites in。 I read bytes off。 I don't care what the network is doing。

 I know it'll be reliable in order， everything。When you're building a transport protocol。

 you build it on best effort， global delivery。 I don't know that packets are going to arrive。

 but I know if I stick it in， the network will try and deliver them to the other end。

I don't have to worry about how they do that。Then if I'm trying to build I。

 that's global best effort packet delivery， I build it on these L2 networks that I stick a packet in。

 and the L2 network will try and take it to the the other next opera router or to the destination。

And then all of these are built on this low level of just physical transfer of bits。

So this is the four layer。Internet architecture。But for very cleanly defined tasks， you don't care。

How the task is done below you， this is why the Internet has been able to survive， you know。

 huge numbers of orders of magnitude changes because these abstractions have survived the test of time。

Almost unchanged。

![](img/29e5a62f4d2f55d9599d2b2009af5ab7_39.png)

So what about control plane abstraction？What abstractions do we have in the control plan？

You're right， nothing。

![](img/29e5a62f4d2f55d9599d2b2009af5ab7_41.png)

We had nothing。这是。We had all these different goals。

But the techniques to achieve one goal didn't use any。 There was no modularity。

 didn't reuse anything from techniques using other goals。 You know， you had distributed algorithms。

 you had scripting， you had traffic engineering。 So there was all this mechanism。Without abstraction。

So there were too many mechanisms。 And actually， the functionality in any one of them wasn't particularly good because you had to designed it from scratch。



![](img/29e5a62f4d2f55d9599d2b2009af5ab7_43.png)

So all SDN is。All STN is。Is an exercise in finding the control plane abstraction。

This has been a very long way in the lecture so far of the only need for SDN。

Is that the network administrators were using arithmetic。But suddenly needed algebra。

And we have to talk about how SDN met that。 meaning。

 what are the abstractions they needed in order to build a control plane。那招我是这样的。

So those abstractions and so what's the right way to think about a control plane that makes it easy？

It's systematic。Okay， so how do you find abstractions。

So what you do is you start off with a task you need to perform。はい。You know。

 sort of for network for the data plane， it was end to end reliable byte stream。

 That's what you want to build applications on。 So you start there。And then you decompose that task。

 And what the data plane did is they decompose it in those four tasks。And you， each one of them。

 anybody could design an implementation。Understanding what the abstractions were， that was brilliant。

And then you define an abstraction for each of these subtasks。

And so let's do that for the control point。So that's what we're going to do。So the basic task。

 the overarching task， is to compute the forwarding state。Given all these other demands。Ultimately。

The data plane needs state。In affording it to switch， router， whatever。Indeed。

 state there that tells it to do the right thing。 For， drop。Send it here rather than there。

But that's the job of the control plane is to compute that state。

 and then the data plane will just act on it。So that this overall task of computing the forwarding state has several subtasks or constraints。

 things you have to take care of。

![](img/29e5a62f4d2f55d9599d2b2009af5ab7_45.png)

So what are。One is it's got to be consistent。With low level hardware and software。That is。

You have a network that conceptually could have routers or switches from all sorts of vendors。

 They have different lowlel mechanisms for how they， their hardware stores their tables。

 how you do a lookup when a packet it comes in， how they look at it。

 So you need to be able to deal with the fact that not all routers have their internal data structure。

 have the same internal data structure。Second， you have to realize that a lot of these computations。

For control plane， depend on the entire network state。

 certainly routing algorithms do that I need to know where everybody is to know how to route。

Not where everybody is， but so I need to know of the network topology in order to route。

And then I actually need to， after I figured out this routing state。

 I need to compute the routing state for every individual switch。And router in the network。

I can't just say， oh， you know， A shouldn't talk to B。 I。

 I have to actually figure out what the entries are for everybody。So the pre SDN approach。

Is you design one off mechanisms。For all of these。就。When you're designing them routing algorithm。

 Cisco goes and designs a routing algorithm。 It's designed around their internal data structures。

Then you follow some algorithm that， you， communicates with all the other Cisco routers and exchanges data and so forth。

And this is a sign of how much we loved complexity at the time that we thought this was natural。

But if you were in any other field in computer science， they would look at this and say， what。

 why are you redoing all this work Every time you design a routing algorithm why。

Why why aren't you sort of。You know， sharing any of these mechanisms。

And so what they would have done is define abstractions to handle each of these subtests independently。

And that's what we should。 Now， in defense networking， what happened is the control plane sort of。

Started emerging gradually， meaning all these control requirements。 So it didn't。 And typically。

 they were in commercial environments。 It wasn't something the network research community was。

In is deep contact with of the operational requirements of running a network。

 So it didn't get a lot of attention。 And so these requirements grew up gradually。 But finally。

 you know， when SDN started， it was time to look at these and say， how do we do this。

 So what are the abstractions that let us do this。

![](img/29e5a62f4d2f55d9599d2b2009af5ab7_47.png)

So that's what leads to SDM。 So what we want to do is separate these concerns with abstractions。

 but I want to stop here。You've been a very quiet crowd。You've been advertised as being。Not so quiet。

Okay， I'm going to bore you to death。Okay， so we need to separate these concerns with abstractions。嗯。

The first one was be compatible with low level， hardware and software。

So what you needed is an abstraction that said， this is what I want you as a router to do。

But I don't care what your internal data structures are。 I just。

 I want to tell you what you should be doing。 And then you need to figure out in terms of your own implementation。

 how to do it。So you need an abstraction for what I would call a general forwarding model。

You need to make decisions based on the entire network。

 which means you need some abstraction that can give you a picture of the network state。

So you need to know what the network looks like， here's what it looks like。

And you need to compute the configuration of each physical device。It is you need。

 you want to do have something that might make that task easier rather than having you do it all。

 And so the point is that。For a routing algorithm， right now。

 each of these things are done by a single coherent routing algorithm。

 So we want to is separate them and provide abstractions that hide these difficulties， so。

The forwarding abstract。So here， what you want to do is you want to express the。

 the intent independent of how it's actually implemented on the forwarding chip。

 You don't want to deal with proprietary hardware and software。Open flow。

 I don't know whether you've heard of open flow。 Thank goodness。 but it was。During the Hait M。SDN。

 it was sort of seen as equivalent to SDM。Which was a mistake。

 But it's a standard interface to a switch。It在。With the open flow protocol。

 I can tell you what you should be doing with this packet。

 And then you figure out how to translate from openflow。 And it basically says。

 if the header looks like this， then take this action。

 And so the 300 page spec for open flow is a bunch of rules for how to specify headers and a bunch of rules for how to specify actions。

 but。There there's nothing interesting there。 It's just。It。

 it's sort of a specification for how you describe headers and how you describe actions。



![](img/29e5a62f4d2f55d9599d2b2009af5ab7_49.png)

Okay， what about the second would make decisions based on the entire network？

So here you need an abstraction for the network state。 And so how do you get this。

 How do you support this network state abstraction。

And so what you want to do is abstract away the various distributed mechanisms that we've come。

 you know sort of the distributed mechanisms that are in link state routing that are in disinfectant routing that all of these other mechanisms we've used。

 what we want to say is instead you don't have to worry about， here's a global network field。

You figure out what you want to do， but here's what the network does looks like。

 and so it's annotated network graph by annotating it has link speeds and latencies and failure rates or whatever you want to describe。

 but it just describes the network as a graph。And it's implemented。

Through something we call a network operating system， that is。

 this runs on servers and the network we call them controllers， they're replicated for reliability。

 but basically it the information flows to and from the network operating system that is the network operating system collects from individual routers。

whoho their neighbors are。So it collects the topology from them。

But then when it's told what the network should do。

 it goes and tells each one of them using the open flow spec， this is how you should forward package。

So both collects information and gives back what I'm going to call configurations。



![](img/29e5a62f4d2f55d9599d2b2009af5ab7_51.png)

So the network operating system， you just think of it as a centralized Li state algorithm。

 What does Li state do， Li state says， I'm going to tell everybody about my neighbors。

And then everybody has a network graph。And here， we send it to。Just， you know。

 a couple of these controllers they're replicated， but sent it to the controller rather than sending it to everybody。

And the controller then computes the forwarding state and hands it back。

And it's some control program that uses the topology as input。And so that it。

 it specifies the state that you go in each using open flow。

 It specifies the state you go in each one of the routers。

And we use the phrase logically centralized because actually they're a set of them use sub consistency protocol so that they stay consistent with each other。

 but so you don't have a single point of failure。

![](img/29e5a62f4d2f55d9599d2b2009af5ab7_53.png)

So this is the picture of what we used to do before SDN。 And you have a bunch of routers of switches。

 and they would have these pairwise exchanges with each other and running some distributed algorithm。

And it's a complicated task specific， distributed algorithm。



![](img/29e5a62f4d2f55d9599d2b2009af5ab7_55.png)

But in SDN， what you do is instead you have a network operating system。

That's really just a server or several servers， but each of the routers talks to the network operating system。

😡，Which then builds a global view。And then you write a control program on top of that global view。

 and that control program can do routing。 it can do access control。 It does whatever。

 but it does it based on that。

![](img/29e5a62f4d2f55d9599d2b2009af5ab7_57.png)

So you can see that this is a major change in the paradigm that rather than building this complicated。

 distributed algorithm， the control program is merely。Applying a function。To the view。

 to this global view， I'd just say if that's what the network looks like。

 This is what I want the routing state to be。 You write a program， a graph algorithm。

So the control program is now just this program over the network operating system API。

And it's just a graph algorithm。 So all the distributed algorithms are in the network operating system。

And the way you configure figure is just。A program looking at a graph。

And then the results of that are passed back to the switches。



![](img/29e5a62f4d2f55d9599d2b2009af5ab7_59.png)

So software defined networking so far just looks like this。



![](img/29e5a62f4d2f55d9599d2b2009af5ab7_61.png)

And at this point， I will insist on a question。So let's say I have a juniper router and I have a Cisco router。

And I'm a control program that computes。What I think the routing tables should be。

And then I tell the network operating to tell all the switches。So the。

 the network operating system needs to have a language。

 It can tell the routers this is what you should do with this packet without caring whether it's Juniper or Cisco。

 And so there's this general abstraction that says。Here's how I will tell you how to look at headers。

 Here's what you should do if it matches that header。That every router。Understands。

 and then they can convert it into what their special AsI is doing and whatever data structure they use in their own hardware and software。

 But it it's this general form of sort of if your header looks like this。

 then this is what you do do it。Yes。Well let me get rid of the term government just because that has too many connotations that。

一。But， yes， it it。All of the。Think of that。None of in this picture。

 none of the routers make independent decisions。They basically， say， here are my neighbors。

 They tell the network operating system， the network operating system。

 the control program looks at all the state。Then just tells them this is what your routing state should be。

所我也。It's not a government you would probably want。You could。there is no logical problem with it。

 It is just that the computational demands of the network operating system are very different than the computational demands of a router。

And so， rather than。Designing it so that assuming that every router sort of has extreme computational capabilities。

 You say we're gonna have some servers。 They're going to do what they do best and routers do what they do best。

 But logically， there's no problem with。Yeah in the middle。

You mean that if we're going through layers， why isn't this introducing a lot of latency is it。Well。

 to some extent。It it's not very different If routers are talking to routers。 Now。

 Rors just talking to servers。So。对。I mean， we， we， we did do some computation， but basically。

 think of it as。You know。I talk to I talk to every router。

 That's not much different than I just talking to a single server and it getting information for everybody and then coming back to me。

You can do the analysis。 And， you know， you maybe argue that there's one round trip time extra in there。

But the ability to sort of centralize the computation and know where it's being done and scale it。

 I think it's typically worth that extra delay。Right no this is supposed to get rid of all current routing over says if you're going to use SDN。

 then you turn off all the other ones。I don't think that's done today。

 And I think I'll get to this later。 but that， yes， that is the point。

So I could pretend that I knew the answer to that question。 I I think the answer is yes。

 just because I see what people do。嗯。That。You know。

 I think these SD N designs of sort of more centralized management can be used for all these tasks。

 but I。That's based on just。General。Impressions， but I couldn't give you a detailed answer。So。

 so I should say this is for every domain， meaning like Berkeley's network would have a global view。

 But right now， I mean。This does not replace BGP。Routing between domains is not covered by this。

But it's sort of within these networks。And， you know， A T has a global view of their network。 And。

 you know， I mean， these companies definitely have them anyway because they've been using them for traffic engineering。

 but it's not。We are not breaking trust boundary。So we are asking A T T to globally manage their network。

 We're not asking A T T to know anything about China Telecom's network。

So that we're definitely not trying to cross those。 So I'm sorry I didn't make that clear。Okay， so。

So now we get to the third。Abstraction， which is compute。The configuration of each physical device。

And the point is， that's actually a real pain for。If， if I'm。Trying to write a control program。

 if I actually have to compute。What every。Physical device with the forwarding state should be。

That's often quite difficult so。You want to avoid that。

And so the third abstraction is what I call a specification abstraction。

It's the control mechanism specifies the desired behavior。

Whether it be isolation or access control or Q OS S or something。

But it should not be responsible for implementing that behavior on the actual physical network。嗯。

Which， because that actually requires computing what the forwarding state should be everywhere。



![](img/29e5a62f4d2f55d9599d2b2009af5ab7_63.png)

So the proposal is this， and then I will explain it with an example and it will become much clearer。

 but。Reose abstractions， I give you an abstract view of the network。

And that abstract view only models enough so that you can state what your desires are。

 what the operator's desires are。And will depend on the task semantics。 You know。

 if it's ales or something else， you know， it's now often called intention based network。

But think of this as providing a compiler in the SDM stack。 and this is what I mean。So I。

 I care about access control。 This is the physical network。 And what I want to tell the network is。

 A can't talk to B。Packets from A should not be delivered to be。

So you can leave that up to me and I can go and say， okay。

 I'm going to pick this router to implement the state that says if you see a packet from A to B。

 drop it。But if I don't know the routing state。Then I may need to place it in a bunch of places。

So the better way is for this abstraction to just say， look。

 I'm going to show you all the nodes in the network。You tell me who can。

 but it looks like a big switch。 You can tell me who can talk to who。Once you tell me that。

 I know what you want to do。😡，I know whether you want to go forward or backward or park。

I know what you want to do。 I can as a compiler， then figure out where to implement that。

 knowing that I've also got the routing state and everything else。

 I can figure out where to implement the forwarding entry that says if your' F a going to be up in a drop。



![](img/29e5a62f4d2f55d9599d2b2009af5ab7_65.png)

And so the SDM stack then changes by inserting a virtualization layer。

It provides this abstract network view。That would be like that。 You know。

 here are all the endpoints in the network。 You tell me who can connect to who。

And then I compile it down。 So the point is， now in this network stack on the way up goes information。

That the routers tell the network operating system who they're connected to。

 the network operating system tells the virtualization network。 Here's the network map。

 The virtualization layer tells the control program。

 Here is what you need to know in order to tell me what you want me to do。

And depending on what that task is， it can be very simple like。

And then what comes down is the control program says， okay， I've looked at this。Virtualized network。

 I've configured it so that this virtualized network， this simplified network does what I want it to。

And then the virtualization layer sort of takes that and then compiles it down to what the network graph should be doing。

And then the network operating system takes that and then says， okay。

 I now know what every switch should be doing。 I'm going to go tell them using openflow。So that。

The full picture of SDF。Now， nobody builds systems that that follows this exact paradigm。

 but it's the right way to think about it。

![](img/29e5a62f4d2f55d9599d2b2009af5ab7_67.png)

So what does this really mean， It means for like a routing application。

 You look at the graph of the network， you compute the route。

You give it to the SDM platform what passes it on to switches。 It's a graph algorithm。

 not a distributed protocol。 That's how it gets simpler。 If I want to change how I want to route。

 I just change my graph algorithm。 I don't have to say， oh my goodness。 you know what。

 what switches need to talk to whatever other switches in order to compute this thing。 I just。

It's a graph algorithm。For access control applications。I just decide who can talk to who。

 maybe based on security categories or some other， you know， sort of label。

Pass this information to the SDN platform， the appropriate as。

Are added to the network in the right places based on the topology？In the control program。

Doesn't who decides who can talk to who doesn't need to know anything about where people are in the network。



![](img/29e5a62f4d2f55d9599d2b2009af5ab7_69.png)

So there's a very clean separation of concerns。 The control program。

 you just specify your goals based on this abstract， simplified network。

It's driven by what the operator wants。The virtualization layer translates between this abstract network and the physical network。

And then the network operating system translates from this graph。To the actual。Physical devices。



![](img/29e5a62f4d2f55d9599d2b2009af5ab7_71.png)

So in short， we started off by saying the data plane had this nice layering architecture and the control plane had no abstractions。

So what SDM is is layers for the control plane and these are the layers。So that's what's the。

Question。Right， so I mean， when I gave you that big switch， there was a company called Big Switch。

 because that was their point。 They say， we're gonna to pretend the entire network is a big switch。

 It's just one switch everybody is connected to it。

 You put in a routing entry for everybody that says， can they talk to each other or not。

And then we will figure out where to put that the network。

 You don't need to know how to network it is constructed。第二。Right。

 so if all you care about is normal routing， the virtualization layer takes care of routing。

 It says know if you want A to talk to B， I can get packets from A to B， I I do that。

You could also have a virtualization layer that is tuned to Q。

 O S or traffic engineering that will take more complicated。Directions of， okay， I've got。

 I've got a route in such a way that I even out the load or I've got a route in such a way that high priority packets get。

 you know， go on special links so things can get much， much more complicated。So as I said。

 this is a perfectly idealized version。 It's not what it's not nearly the simple。

 but it's the way to think about it。I think it really depends on the。

The sort of the timescales that you're changing， if it's things like as that change the human time scales。

 it's just。嗯。You know， when there's a change in what the operator wants， things change。I mean。

 there are a lot of low level mechanisms that make sure that what the。

SDM platform has said is consistent with what the switches are doing。

By constantly checking to make sure the state is consistent。So remember。

 this is all on the control plane。😡，So data packets are just flying at regular rates。

So all the virtualization layers is doing is' simpler to write your control program。

But it doesn't impact the behavior on the data plane at all。



![](img/29e5a62f4d2f55d9599d2b2009af5ab7_73.png)

You're just scratching your hip， right， That was not a question。Okay。😊，嗯。

So let me just interrupt me when you want to ask。But the important thing。To。

 to note here is that abstractions。Don't replace。Complexity。The network operating system。

 the virtualization layer， they're all complicated pieces of code。

 So it's not like we would Presto magic。 Things got simpler， and it didn't go anywhere。

It just localizes the complexity。That is， the control program becomes much simpler。

But all the complexity is pushed into the reusable code， the SDN platform。

 and that's been the trajectory of everything in computer science。 you push stuff into compilers。

 you push stuff into lower layers that you keep reusing。 And so you're up there writing ja。

 not knowing anything about anything and things work。So that's the big payoff of SDF。So， I want to。

Because I know I'm not going to be able to answer Alex's question。

 So I'm saving for five minutes for me to sort of vamp at the end。 But， so why is SD D N important。

 sort of as a design。It's more modular， enabling faster innovation。

 the control program to become simple。 You know， in all of the hyperscalers that that have these massive networks to run。

 they've adopted something like this。 You know， it's much more complicated much more sophisticated。

 but something like this。 They realize they couldn't use traditional mechanism。

Now as an academic endeavor， what it did is it gave us a set of abstractions to think about the control plane in a way so things like network verification is much more popular and much more used than it was before because you can actually think okay I have a graph I'm going to tell what that graph should do。

 I assume that there are lower level protocols that will make sure that the actual network does what my logical network is doing so by separating it out。

 you can actually try and apply some more formal tools to it。And it's。

 it's a change in the ecosystem。 And this is where。We were fools。We just thought。

We're going to propose SDM。 the world's going to adopt it。 Cisco is going to crumble。And， you know。

 the world will be a nicer place。 You know， we named our software releases after the highway exit between us and Cisco。

You know， that was like our target， we were going to take them down。They're still standing。We failed。

 But， you know， the thought was that if you put all the intelligence in this operating system。

 network operating system， then the。It doesn't matter whose router you buy。

 because the averagevers are now not very intelligent boxes。

So that would mean that all these white boxes would take over the world。 So that hasn't happened。

So why well I'm not going to ask why we're idiots。 that has to do with lots of other factors。

 but why is that a sign were idiotic。And it's because。For the hyperscale， they。

 they have sort of taken this on themselves。 and， you know， they buy whatever they buy and。

 and you know。Cisco isn't the sole provider， but。For places like Berkeley who don't have this sort large internal staff and their own networking software。

When they buy it， they want one throat to choke。So if you've got 16 different brands of routers and software that come from some other places and something breaks and you pick up the phone and says it's not working。

If you're going to say tough， you know， it's probably somebody else。

So now you want a router vendor or networking vendor that if it breaks。

 they will come and they will figure out what the problem is。 And so that。

Even though logically we have separated the functionality。

 you still want one provider because a place like Berkeley just doesn't have a big enough staff to debug all the problems。

 and if you've ever tried to use our Wifi， you will understand that that is a very present problem。



![](img/29e5a62f4d2f55d9599d2b2009af5ab7_75.png)

So I want to end by going through some common。Questions about SDN。 And so I only have， I'm actually。

Probably not going to quite finish， but let me rush through this。

 So lots of people ask iss SD N less scalable， secure and resilient， Can it be extended to the W。

 Is open flow the right forwarding abstraction， Is SD N incrementally deployable。

 And the answers are。No， it's not less scalable resilient。 I mean， you can design SD N。

 So it's really terrible along all those dimensions， but you can also design it so that it is。

 you know， scalable and resilient。Can it be extended to the when the answer is yes， And。

 And Sylvia is doing work in that area Is open flow of the right forwarding abstraction。

 I think the community's answer is absolutely not。 Is SD DN incrementally deployable。

 And the answer is yes。And so how can this possibly be， So I want to end by answering that question。

 So I'm going to speed through this a little bit because I've only got 10 minutes。嗯。

And I've got 15 slides。 So most， most of SDDM's design is on software on the servers。 right。

 So you can deploy that fine。But， it's with the assumption that all the routers support support open flow。

That is we assume that I can talk to a router and tell it what to do using Openflow。Okay。

 so that requires either replacing all the routers in the network or having them all upgrade。 Well。

 the router vendors are not going to upgrade their routers to support openflow。

 and they're certainly not in most cases like Berkeley。

 they're not going to replace all their router。

![](img/29e5a62f4d2f55d9599d2b2009af5ab7_77.png)

So the question is， how do we get this deployed， I meaning we're a startup。

 We were trying to bring SDN to market。 How could we possibly convince people to upgrade the routers？

 So， I mean， how could we get this deployed？ So， you know。

 option one is get everyone to deploy new routers。Now。

 it's completely ludicrous only idiots would believe this。 But one of the things。

 if you do a startup， you will realize that a startup is shared insanity。

 you all believe in something that is low probability。😡，Well， we believe this。

 we believed this for about two years。But obviously， we're fools。 So that's not how it happened。

 So how did we deploy SDN。And without them buying new switching hardware。And in some cases。

 not even talking to the networking team at the company that adopted it。是好。Just think about it。

How could we do this？So there are two facts， One most additional control plane functionality。

 besides its just straight routing， delivery of packets can be implemented at the edge。

 access control La， you know， if I don't want A to talk to B。

 then the router at the edge from A can say， oh， you're going to B。

 You're not allowed or if the laptop can say， you're going to be from A， drop it。

 We don't need it in the middle。That applies to almost everything， even traffic engineer。

So the network core only needs to deliver packets。😡，Everything else can be done at the edge。

 The first hop。And so and even pre SDN， you know。Network technologies were pretty good at delivering packets。

So we only need SDN at the network edge。Now， this edge core split arises another context。

 which you probably haven't talking， but the point is we were not the first people to realize， oh。

 we only need things at the edge， not in the core。Fact number two is the operators who were crying were the ones who were running these multi tenantant data sectors。

And so they run hypervisors on the host that support a lot of VMs。

And these two facts gave us an opening。 And so in the next。Six minutes， I will tell you how。

So how do you deploy a virtualized data center？I mean。Virtuual the VMs are supported by hyperviss。

Now， if you're in one V M on the same post， talking to another V M on the same host。

There's a logical switch。 I mean， the software switch that you go through。

They're called virtual switches， that's what you go through to talk to each other。

So you make this virtual switch SN compatible， meaning you make it support open flow。

And if you can do that。You can deploy SDN without touching any hardware。

And because it's a software that runs on a host， a computational host。

 you don't even have to talk to the networking team。At all。

 you just talked to the computational team。 So Open V switchitch was an open flow capable virtual switch that was done by Ben Fft at De。

 basically overnight。

![](img/29e5a62f4d2f55d9599d2b2009af5ab7_79.png)

He said， oh， I should build a open full compatible V switchitch and the next morning it existed。

So it didn't even take seven days and seven nights。 So it was like one night。

 And so it was in Linux and eventually got into Linux and Zen and so forth。And so now。

 STM is deployable。Without any hardware deployment。 And so that's how we were。You know。

 able to deploy the supply only to multi tenant data centers they say， well， that's not good enough。

They were only customers。So it didn't matter。 I mean， and they were the that that's what took off。

 So right now， so I'm actually going to stop here because running through the rest of my slidebs is was of your time。

 But this， this was。This is how SDN finally took off。 is it took the problem。

 the people who had the problem。That we were trying to solve。

 meaning that the ones that were crying actually had the perfect environment for doing a software only deployment。

And so that's where it took off。 And now， you know it's applied more generally and you can have switches that can support Openflow and other things。

 but that's how software defined networking took off first is in the places where it was most needed。

 it was easiest to deploy。 and that was complete in sheer luck。We did not claim on that。

And with that， I will now take even Alex's question。Right， no， right， no， But the point is。

 my virtual switch。 Okay， so I'm on a host。 I have a virtual switch。 I've got a V M。

It doesn't care whether you're talking to VM here or V VM across the network。

 If I say A can't talk to B， it gets to this first hop。

 And this first stop says I have an as that says if this is a packet from A to B， I'll drop it。

 I don't。 It doesn't need to be。 But the point is you need it on the。

 you need a virtual switch on the host in case these and。Okay。

 I don't care whether this is being taped or not。 The Cisco solution to this problem was， oh。

 we should make it go to the hardware router and then back。

 whereasas everybody in the right minds would have said， of course。

 it has to be in the virtual switch。 And so thats。Why we didn't need to go to hardware network。

 Does that answer your question。Going once， yes。Well， you。Okay， first of all。I hate open flow。

 I hated it from the beginning。 I thought it was a bad idea。 not where we should have gone。

 So I'm not defending open flow， but。If， if you're designing a network operating system。

And you want to write a control program and think of。

 think of it think of openflow if the instruction set the， the SDN stack is speaking。

It shouldn't have to know what brand switches you have。

So it doesn't really matter whether it's open floor or something else。

 but something has to be supported by all switches。 So there has to be something。

that was our intention。How much time do we have？Okay， so， so actually， let me。I think even outside。

Of data centers， virtualized data centers。 You really only most of your control can be done at the edge。

Not all of but most of them。Open flow。 Look， if you've got a 300 page spec。

 that is no longer a simple protocol。So the point was， open flow is。

Way too complicated for most routers。And it is not flexible enough for what you want to do with the edge。

 And instead of you just say， look， at the edge， I'm going to have software。Of some kind， you know。

 even if it's just a forwarding box and that， you know。

 you look at a lot of the hyperscalealar networks they've got at at their client facing networks。

 They've got software boxes。So there I can write whatever I want。 I don't need a 300 pages back。

 I just write a program。 And then inside the core of the network。

 I don't need all of the fancy stuff that Openflow developed that did incredibly stand on their head。

 things that are just really hard to implement。And I'm sorry if I offended any of the open flow authors that are。

See this。So that that it like。It wasn't simple enough to do everywhere。 And it was to。

 And like P 4 is now taking over because at least P4， which is this programming like， I don't。

 Did you cover P 4。So it's basically a program interface with programming a switch。At least it's。

Simpler and just a programmable interface that's， okay。

 you can do anything that you can do in this program rather than here's this complicated protocol that every time you want to do something new。

 we have to add a new feature to。We got bought by VMware。Well， I bet my house， so I got to keep it。

They have no memory of that conversation。Okay， thank you very much。

