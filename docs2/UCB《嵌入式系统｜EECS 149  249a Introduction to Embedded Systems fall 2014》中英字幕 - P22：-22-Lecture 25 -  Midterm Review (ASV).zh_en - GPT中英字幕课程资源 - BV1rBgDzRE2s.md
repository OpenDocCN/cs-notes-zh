# UCB《嵌入式系统｜EECS 149  249a Introduction to Embedded Systems fall 2014》中英字幕 - P22：-22-Lecture 25 -  Midterm Review (ASV).zh_en - GPT中英字幕课程资源 - BV1rBgDzRE2s

Nothing。You can hear me。Barely， all right， let's see what the deal is here itops。啊。

Is that any better？Okay。All right。A couple of announcements if you're planning still to be ordering parts for your project。

Today is the last day。Okay， our staff is sufficiently stressed out about trying to make these quick turnaround。

嗯So。Make sure you contact your GSI today if you need to order additional parts and depending on who you're ordering it from。

 it may already be too late to get them in time。Some of the suppliers。

 we think we can get them in time for you to be able to use them， so please don't。

Don't wait until after today， if you do， then you're going to have to spend your own money and order it directly but using whatever mechanism you can to get it as quickly as you can。

Okay， so today is the last lecture， we have a midterm。On Thursday， it'll be in this room。

The project presentations will be two weeks。From tomorrow。Okay， and we're going to start at 8 a。

And we're going to use this room。And I encourage you all to come hear what your colleagues have to say there's some really amazing projects and you know if you've got the time。

 hopefully you're done with finals and you you want to see what your colleagues have done。

 please you know come spend some time， it's a lot to ask for everyone to spend the entire day。

 but as an extra incentive we're going to provide pizza at lunchtime。So。

 but we ask you to not just come grab a pizza and leave if you come get pizza。

 you have to sit through at least。Two of your colleagues presentations， okay。

 let's say that is a minimum。You should contact your GSI about scheduling your slot for your team during the day。

 we have this room from 8 amm until 3 pm。Which is not enough time。

So we're trying to get another room for the rest of the afternoon。

So we'll have to move for the tail end of the project presentations。

 if you have a project that where you want to do a demo in Corey Hall as part of your presentation。

 that would be a convenient one to schedule after 3 pm。Okay， so let your GSI know about that。

Any questions for me？Yes。Well， if you can do your demo here， that's great， okay。

 if it's difficult to transport， then let's schedule it for after 3 pm。Okay。

 we ask everyone to provide a video snippet of whatever you've built as well as part of your deliverables。

Okay， so you can use that in your presentation。But we do we really like live demos。

 they're much more compelling than video snippets okay but if it's not transportable。

 let's do it after 3 pm if it is transportable then please do it in this room the structure of the presentations will be similar to the many project presentations that you did you will have 10 minutes。

And we will cut you off after 10 minutes， and then there'll be a little bit of Q&A， okay？

And so plan for 10 minutes， plan carefully。All right， any other questions for me？Okay。

 so today what I'd like to do is spend no more than 15 minutes， I'll cap this at 1130。

 wrapping up the networking discussion， which I had really two more points that I'd like to make about wireless networking。

And these are really more in the spirit of technology that I think you should watch。

Because it's cool stuff， it's happening and it's not going to be on the midterm。

But I think it'll be useful for you to have some perspective on what's going on here。



![](img/948e65e23b22241b84ce2652673b67aa_1.png)

So we did start talking about wireless networks and there's essentially three categories here。

 the personal area networks which are short range local area networks。

 which are a more intermediate range and wide area networks like the ones that are used for cell phones or I mentioned briefly SGFox。

 which is specifically aimed at Internet of things applications， so it's an extremely low cost。嗯。

Intended to be ubiquitous。Wireless service。With very low bit rates。Very low bit rates， very low cost。

Those things go together， but an interesting technology to watch。嗯。系い。

I'd like to just talk briefly about。Wireless network apologies， okay。

 because I believe that there's a very strong trend towards mesh networking。

which is really not what we have widely deployed today。

 what's widely deployed today is more star networking where you've got an access point that's connected to a wired network。

 but then the wireless network， every device communicates individually with that access point。Okay。

 in a mesh network， the wireless devices are communicating with each other and relaying messages for each other。

Okay， and theres some experimental work in actually doing that， even with cell phones， for example。

 just using the fact that all cell phones have w-fi radios。

 even if you don't have a w-fi access point， you can get two cell phones to talk to each other through WiF and that you can use this to relay signals and route signals essentially through other people's cell phones。

 which means that you can kind of bypass the telecom networks。

 which is I think an interesting technology that's emerging。

It's also a very interesting technology in the context of wireless sensors and actuators。

 and you know pretty much all of these wireless devices tend to be battery powered。

 so energy consumption is a really big issue and mesh networking has a huge advantage over star networking if in that the average distance over which you need to communicate with a radio signal is smaller。

Because if you can use intermediate devices to relay your signal。

 then you don't have to transmit as far， so you can use significantly less energy in the radio if you can set up wireless mesh networks。

But there's problems， okay， in particular， one of the biggest challenges is that if you are a wireless node and you're functioning as a relay for other wireless nodes。

 then you might think that， well， I have to keep my radio on all the time because I can't be useful as a relay unless I'm listening for incoming radio signals。

But if you keep your radio on all the time， you're going to deplete your battery very quickly。So。

People have developed slotted networks。Where。啊。You have nodes that are actually waking up。

 turning on their radio， listening for incoming signals， and then going back to sleep。

 and this essentially requires clock synchronization。So you've got to have all your nodes。

Their clocks have to be sufficiently synchronized that they know when to wake up， they wake up。

 and then they communicate， and then they go back to sleep。

And last time I talked a little bit about how clock synchronization protocols work in wired networks and describe the IEE 1588。

Protocol， you could do something similar in wireless， this particular technology。

 wireless heart was developed by people here at Berkeley and became standardized as part of the 80215。

4E protocol， and it's much simpler actually than 1588。

 it's a pretty brutefor clock synchronization protocol。It's not nearly as precise as 1588。

 it gives you precisions on the order of milliseconds rather than nanoseconds。

 so many orders of magnitude sloppier， but good enough to get pretty decent synchronization and good enough to make wireless sensor nodes be able to run for many years on a coin cell battery。

By just turning on their radio only very rarely。Okay。

 so this is a pretty cool technology and definitely up and coming。Now。

 another one of the big energy costs in battery powered devices is the IP stack。

Just you know communicating with the internet can use up a lot of jos okay and the problem is getting worse with internet of things creating many。

 many devices because the internet protocol address space is not big enough for the internet of things。

 the address space that we're all familiar with， you know， the 128 dot， whatever dot， whatever， dot。

 whatever is a 32 bit address space。So you've only got 4 billion addresses。That's nothing。

 that's not enough， okay。And so IPV6 uses 128 bit address。

 but the energy cost of an IPV6 stack is much higher than the already high energy cost of an IPV4。

 there is no IPV5， by the way。They skipped five for some reason， like windows is skipping nine。嗯。

You know， but anyway。But there's a rather cool technology called CoAP constrained application protocol。

 which was also the development of which was also led by people here at Berkeley， David Cueller。

 who was heavily involved in the development of this technology。

And what that does is create enclaves of local area networks where you just use a 16 bit address。

Okay， and then there's a gateway that does the translation of your 16 bit addresses and。

Creates basically a full full featured internet interface。

To a very low energy consumption wireless device that has far from a full featured Internet connection。

 But through the gateway， it behaves as if it had a full featured Internet connection。 Okay。

 so that's another。Cool emerging protocol to keep an eye out for。Now， Wifi。

 I think you're all pretty familiar with， okay， it was developed in the 1990s。

 AT&T was the main lead on that。嗯。It tends to require larger antennas and more energy than Bluetooth or the 80215 networks。

Um but。Wifi is really designed for internet access。

 and so devices that have wfi tend to provide full featured internet interfaces。

 including often a complete。Not only a complete IP stack， but also support for HtTP。

 which is web accesses。And there's a very strong trend。

To be using web technology for accessing endpoint devices。

 sensors and actuators okay an example of this is the electric IP， which is a device。

 this is a microprocessor with a wfi radio and a multichannel A to D converter on a form factor。

On the form factor of an SD card。ok。And the way that this works is you download an app to configure the access to the WiF network for this thing。

But how would you get the wF credentials into this device？Okay。Well。

 electricAmp has a very clever technique where you download this app。On your phone。

 the phone has the wF credentials， so it already knows how to get on the local wF。

You run the app and the screen blinks。You hold the screen up to this end of the electric a。

And it has a little photocell receptor。And it just measures the blinking of the screen and says， oh。

 you're giving me the IP credentials for the WiF network。Okay。It gets the code。

 gets on the Wifi network， communicates using HTTP to a server that the electricI provides。

And starts sending A to D measurements to that server。Okay。

 so you can wire up sensors to this thing and then go to the server and read your sensor data now the latencies are large。

 you know， I mean it's typically more than a second latency between when you take the measurement and you get it back from the server。

And the sample rates are very limited， I think we've determined experimentally that they limit you to。

 I don't know， something on the order of 20 samples per second， so not a very high sample rate。

 but you know a pretty clever kind of plug technology if you need sensor somewhere where you don't have a convenient wired access。

Okay， so this use of web technology is generally referred to as restful interfaces these days。

 so rest stands for representational state transfer and it's more than just。

The fact that you use a URL to get access， that's part of what rest is about okay。

 so if I want to read a sensor value。I construct a URL like this， I give internet domain name。

 a port。And then。A string that is typically proprietary。

 so if it if you're accessing electricmp data， there's a particular syntax to that string that you need to follow so a typical example would be you want to read the value of a sensor that has this ID you would construct a string like this and what you get back is a J string。

That is the latest sensor reading。OkayNow rest is more than just using this kind of URL to access it。

 it also has included in the principle that the server。Doesn't keep any state about the client。Okay。

 so it doesn't remember who you are on successive accesses to that URL。

So if you need a service that carries any state， you have to carry the state locally and then encode the state in this string and each time you communicate with the server。

 you give it your updated state。Okay， so that's a key feature of rest。

 it makes the servers much simpler and much more scalable okay。

 because now a server can handle requests on any machine okay so if you have you know a whole data center。

You don't need the request to go to a particular machine that happens to be storing your state。

 you can go to any machine in the data center because everything it needs to know to service the request is in the URL。

Okay。So that's a key property of the restful interface。

This is being used quite a lot in Internet of Things architectures today。

 where the typical architecture is you've got some device that uses a wireless network。

 this is a Phils Hugh light bulb， it communicates with a gateway which is typically provided by the same vendor。

As the device， that's not going to scale， by the way， okay， because we're envisioning you hundreds。

 thousands of these devices pervading provided by many different vendors and eventually you're going to have such a big stack of gateways。

your whole office will be taken up with gateways， so there's got to be a better way to do this。

 but nevertheless this is how it's done today， the gateway communicates with a cloudbased server and then an app on the phone will communicate with the device through that cloud based server that's the typical architecture。

There's a number of challenges with that kind of architecture。



![](img/948e65e23b22241b84ce2652673b67aa_3.png)

You know， smartphone apps as the interface doesn't scale either。

 right if you have 100 different devices in your。House。

And you have 100 different apps to access them。you want to turn on your living room lights and you got to scroll through all your apps and your code。

 figure out which light it is， turn it on， that's never going to compete with a light switch on the wall。

 so there needs to be other ways of composing these services。

The latency of cloud based services can be substantial， there's also privacy concerns。

 right if all your data is going to the cloud and back。

You lose control of it and you never really can be sure who's watching you when you're doing this。

 whereas if you keep data local， you have a better chance of preserving your privacy。

The other thing is that there's a lot of moving parts in these。

 and so there's a lot of things that can go wrong and often you know you're just blind。

 you have no idea what's gone wrong is if my wfi connection is the server gone down you could be any of a number of things and it's often very hard to debug these things。

嗯。This Internet of things。啊。Phenomenon is way overhyped today。Okay。

 and that's reflected here by this chart that was published by Gartner。

 Gartner is a media organization， so they do a bunch of technical publications and every year。

For the last several years， they've been publishing what they call their hype cycle。

Where they track technologies and put them in phases， the first phase is an innovation trigger。

 this is when the technology is just emerging。Then that gets followed by the peak of inflated expectations。

At which in September of 2014， they put the Internet of things at the peak of inflated expectations。

Followed inevitably by the trough of disillusionment。

As people discover that the latency through these cloudbased services is not good enough。

 the reliability of your front door lock has gone from you know 50 years no maintenance to you have to be an IP specialist。

 an IT specialist to keep being able to enter your house so there's going to be a trough of disillusionment。

 I pretty much guarantee it but hopefully after that there will be a slope of enlightenment and a plateau of productivity and this is going to require some technology changes here and I think the current kind of brute force techniques there been a need to evolve。

We have a research project called the Terracewarm Research Project， which involved nine universities。

嗯。Where Berkeley is the lead and we're specifically addressing this problem。

 trying to get us to this plateau of productivity sooner， more safely， and with more confidence。O。

That's enough about networking。Any questions about that？



![](img/948e65e23b22241b84ce2652673b67aa_5.png)

Yes。

![](img/948e65e23b22241b84ce2652673b67aa_7.png)

We haven't really given you any problem set assignments about networking。

So the networking content in this course is meant to be helpful for your projects more than for the midterm。

 okay， and also just you know for one of as I've stated repeatedly in this class。

In addition to kind of showing you how things are done today。

 which is I think what a typical embedded systems class does。

I'd like you to walk out of this class with some understanding of where it's going。

And also why it needs to change right what's wrong with the way that it works today okay。

 and so you know what I'm in this discussion of networking， you know。

 hopefully it's somewhat helpful to put your project efforts in context because I think almost all of them involve networking。

But perhaps more importantly just you know， for your own。Information and。Career development。Okay。

All right， so what I'd like to do is spend the next 45 minutes just。

Reminding you what we've done with emphasis on you what are the topics of interest for the midterm that's coming up on Thursday。

 and I encourage you to ask me questions about that might be related to that as we go。嗯。

And then we'll conclude with a course evaluation， hopefully the HKN folks will show up。At some point。

Are they here already？All right。This is the map of the textbook。

And this textbook was written for this course， so you know it kind of follows the structure of the course。

Pretty well， there's this center thrust thread rather。That's focused on design。

 and if you go to another university and take a course in embedded systems。

I know I just had dinner last week with the guy who teaches this course at CMU embeddedd systems course。

 and it's exclusively this thread， they don't do anything here and anything here。

And that's really more typical， it's very much focused on the design of these systems。

But I think what we're trying to do in this class is really instill the value of modeling and the connection that that has with design。

And the value of analysis， and you can't do the analysis without the modeling。

 it's just impossible and so what I'd like to do today is kind of try to give you some perspective of how these pieces fit together in my head。

Okay， and hopefully it'll help you understand why this course has the particular topics in it that we've chosen to do I should emphasize that this list of topics is really incomplete。

 you know， there's a lot。A lot of technology involved in these kinds of systems。

 and we can't cover it all。But hopefully we've given you a useful introduction to the various pieces so you can dive in more deeply later on。

 and at the end I'll give you some guidance follow on courses， if the subject interests you。

 what other courses should you take。 so the emphasis for midterm two is on the low ends of these threads。

As you know， but it's somewhat cumulative because to some degree know these are dependency relationships。

 these arrows。And。The later stuff does depend on the earlier stuff。

 so we assume you won't have forgotten everything from the first half of the semester。Okay。All right。

 so the emphasis has been on cyber physical systems， I don't know。

 did Alberto talk about the origin of that term in the first lecture。

 that was a long time ago you probably don't even remember。If he did or not。let me just tell you。

 okay， so the term was coined actually by Helen Gill。

 who was at the National Science Foundation at the time she's since retired。嗯。And at the time。

 a lot of people got it confused with cyber securitycurity。

 They thought cyber physical systems was just another word for cybersecurity。It's not。

 right and in fact， cybersecurity and cyber physical systems actually share the same roots。Which。

You know，Most popularly， cyberspace was a to。A toined， a term coined。

By William Gibson in the novel Neurmancer。And you know he used it as this virtual space that people jacked into and interacted with one another。

And。But even that has much deeper roots， the term cyberbernetics was coined by Norbert Wiener who was he was at MIT at the time。

 and he had done radar development during World War II， that's kind of how he made his name。

 he was one of the key developers of radar。But he used the term cybernetics to talk about the conjunction of communication and control。

And if you look at what he wrote about it， it was really prescient。 I mean。

 he was really talking about computation， interacting with physical dynamics。

But he didn't describe it as computation because at that time。

 control was always done with analog circuits。Okay， so it was analog computers doing the control。But。

That was the cyber part， and they were interacting with physical dynamics。That they were controlling。

 and there was communication between these devices。Okay， so it was really， you know， in a way。

 cybernetics is really an awfully good term for cyber physical systems。

 but it's viewed by most people as kind of an old fashioned term。

And you can't start a programming NSF based on an old fashioned term， so you need a new term。

All right， so。You're experiencing cyber physical systems in the lab， for sure。

 every one of the projects is dealing with a cyber physical system。And you know。

 these involve some computational platform， some network fabric。

 and some physical plant and interactions between these things。

Now what I'd like to do is spend a few minutes pondering about this structure and specifically about the use of modeling and analysis。

Given this kind of structure。ok。And as I've said repeatedly。One of my goals is to。

Help you realize that the technology that you're dealing with is immature。

 if you walk out of this class thinking you're an expert。In embedded systems。

 you're diluting yourself。 Nobody is an expert in embedded systems。 It's an immature technology。

 We're all groping in the dark。And it's going to get much better。

So what I'd like to do is really paint for you the picture of how it is， what's missing here。

 what is the key gap？So。Let me focus on the problem of determinism。So if you have a system like this。

There's a lot of sources of nondeminism， right， you have physical noise。Your sensors are subject to。

Those of you who are using RSSI measurements， for example， to try to measure distance。

Realize holy cow， that's really a very， very bad measure of distance。Very noisy， okay。

 subject to lots of。Lots of inaccuracies。 that's one source of nondeminism。

You have imperfect actuation and you try to have an effect on the physical world。

 the mechanics of the actuator will introduce noise。You have parts， failures in the physical system。

 these are inevitable。In the network fabric， you have unknowable delays， notice I said unknowable。

 not just unknown。You can't know them。Right not only。Don't you know them。

 but you actually can't know。You have packet losses， okay？In the computational platform。

 you have unknowable execution times， noticeice again I didn't just say unknown。

 even though we had a whole chapter on analyzing execution time。It's a fiction。

execution time is actually unknowable today in most architectures。

And you have uncontrollable scheduling。Okay， you might think that earliest deadline first is doing what you want。

But really， you need to be skeptical。And there's anomalies that can happen。

 things finish early and that causes deadlines to be missed。

 so there's a lot of sources of nondeminism in these systems。So in the face of such nondeminism。

Should we be talking about deterministic models for cyber physical systems？What do you think？Well。

 one possibility would be say， no， that would be ridiculous。 That's hopeless。

 That's just beating your head against the wall， right。

The reality of their systems is that they're highly non deterministic。

So we should only be working with non deterministic models。That's one approach。

 and you will hear that approach from many people out there。ok。But I don't believe in that approach。

And I'd like to explain why。And I think that， you know。

 this explanation will hopefully give you some insight into why we've picked the particular topics in this class。

 why did we look at。Synchronous composition of state machines。If you ask yourself that question。

 right did you use it in writing the C code for your project in the lab？Probably not directly。

Okay so why did we include it， What does it have to do with embedded systems？

I claim that it has to do with it。What is coming？To solve the problems around embedded systems and cyber physical systems。

 we are going to need deterministic models。Okay。So but deterministic models of non deterministic systems。

It's really important in modeling to keep clear in your head the distinction between the model and the thing being modeled。

 they're not the same thing。Two different things completely。Engineers confuse them all the time。

You're working on a piece of C code and you think you're working on an implementation， you're not。

 you're working on a model。Okay， C is an imperative programming language。

 and you're constructing a model that says。Change the state of the machine this way。 Now。

 change it again this way。Okay， but the physical realization is really something quite different from that C program。

 so you're actually working with a model of that program。

So you've got to keep the distinction between the model and the thing being modeled。

 and so this guy Solomon Wolf Gluham。Ha a wonderful quote where he says。

You will never strike oil by drilling through the map。 the map is your model。

 the desert is your physical system。And if you confuse the two， you might drill through the map。

 which would be ridiculous。Okay。But in no way does this diminish the value of a map？

So I think Alberto made this point on the first lecture， right？

I think he also cited what I've been calling the COets principle。Which is that。

And the reason I cite this is that I learned this from Herman Koitz when I went to a conference in Munich。

And I was thoroughly jet lagged and had to give a talk early in the morning。

 went down to the breakfast room at the hotel Blearyeyide。And happened to sit down。

 The place was full。 so there were no。Empty tables。 But I recognized Herman。 So I SAT down with him。

 and we got into a conversation。And he told me his view of the role of models and it kind of blew my mind and I actually had never thought of it this way。

 and so I really learned this principle from him， it turns out that this principle is actually codified in the procedures that are used to certify nuclear power plants in the US。

So Hermann didn't invent the principle。 It's actually written down as one of the。

Princiipples under which you can get certification to operate a nuclear power plant。

And the principle is that any definitive statement you make about a system is not a statement about the system。

It's a statement about the model of the system。 you cannot make definitive statements about a system。

You can make definitive statements about models。So if you assert that your C program is working correctly。

That it computes some function。That's an assertion about the model。

Will the C program actually do that at runtime， well， hopefully？In fact， probably， in fact。

 almost certainly。But not certainly。ok。The seed program may malfunction because an alpha particle flips a bit in your memory。

It may malfunction because your chip is overheating， your microprocessor is overheating。

 okay it may malfunction because the connection to your power supply is has a cold solder joint and you're occasionally getting disruptions in the power supply。

There's all kinds of reasons that your C program， once it's realized in the physical world。

 will not behave like the model。ok。But that doesn't in any way。

 say that you can't make a definitive statement about the C program because the C program is a model。

And you can prove properties about that model。Okay。You can state with 100% confidence。

This line of Z code is not reachable， for example， well。

 it's a little hard with C because you can mess with the stack。

 you can write directly to the program counter， et cetera， et cetera。

If you use a more modern language like Java， you actually can make definitive statements， okay？

But any such definitive statements are always about models， okay， so that said。

Go back to this question。We've got wildly non deterministic systems。

Does it make sense to come up with deterministic models for it？I'm going to argue yes。

And I'm going to do it by pointing out that we've done it before。ok。

We've come up with deterministic models for wildly non deterministic systems。Okay， transistors。

 semiconductor or circuits。Are wildly non deterministic， it's electrons and holes sloshing around。

Under the force of electric fields， they're messy， they're analog， they're random。

They're subject to thermal noise effects X。Okay， highly non deterministic systems。

 And yet there's a very， very nice。Deterministic model that， in my opinion， is。

Perhaps one of the key enablers of the 20th century information technology revolution。

Which is synchronous digital logic。The fact that you can abstract away those messy transistors as gates。

Put them between latches。And if you clock those latches at appropriate rates， the system behaves。

Almost perfectly。Like this very nice， simple， deterministic model would predict。Almost perfectly。

Right？The circuit， you can make a digital circuit。That will。Perfectly emulate a model。

 a deterministic model， a billion times a second， flawlessly for years。

 so if you think of the number of computations that's done at a billion times per second over years。

 it's a very vast number。Right and you can make。A physical realization that behaves just like this deterministic model with almost perfect fidelity。

That's a very， very powerful property。And， in fact。In the circuits world。

 there's been lots of people advocating asynchronous circuits。

 and there's lots of technical advantages to asynchronous circuits。But they've never caught on。

You know，40 years of research， and they still can't compete with these synchronous circuits because you lose this determinism。

And the determinism is an incredibly valuable property。

So deterministic model of a non deterministic system。Give you another deterministic model。This one。

 I think。Also underpins the success of the information technology revolution。

Single threaded imperative programs。Okay， these are deterministic models。 And guess what。

 The physical realization is the same one that I just showed you。 It's synchronous digital logic。

 which is itself an abstraction of these messy transistors with electrons and holes sshing around。

Okay。But nevertheless， we have a deterministic model， you can write a single threaded program。That。

For which we have a physical realization that is extremely high fidelity。

It will almost perfectly always behave like the model predicts。That's an extremely valuable property。

 And by the way， as soon as you make this multi threaded。

You lose this determinism property and youve paid a big price now。ok。It's a big price。

 one of the trends that's happening in the Internet of things world is to not go to multi threaded imperative programs。

 just don't go there。Okay， so go instead with event driven technologies like what's used in JavaScript。

 where everything executes in a single thread。And。As a consequence。

 you regain the determinism of the model。Okay。That's one of the very strong trends in IoT these days。

 and I think it's a very positive one。All right。Let me give you a different kind of deterministic model。

 one that we looked at early in the semester。Theterministic model of physical dynamic。

a differential equation describing， for example， a motor or a generator。

This is a deterministic model， it happens to be operating in a time continuum unlike the synchronous model of synchronous digital logic or the imperative model of programs。

But it's still a deterministic model。And I would argue that this deterministic model is the reason that airplanes fly reliably。

 that cars work。That the industrial revolution happened， that we were able to make big machines。Okay。

 and。Engineer them。So that they did the right thing。Okay， now for these models。

 the physical system doesn't typically come as close。As the two previous models。

 so you have a deterministic model， but it's a coarser approximation of the physical system。

Almost always。ok。But it's still incredibly useful， right without that deterministic model。

 you can't analyze the stability of a helicopter。You can't analyze the effect that the aors have on the trajectory of an airplane。

Okay， so these deterministic models are extremely useful。

 even though the systems that they're modeling are actually intrinsically non deterministic。

Now here's the problem with cyber physical systems。Three。

 very powerful deterministic models that are widely used in engineering。

This kind of model deterministic differential equations。Single threaded imperative programs。

 synchronous digital logic。What happens when you put these together to get cyber physical systems？

Because we need the cyber， we need the physical。As soon as you put them together。

 the model becomes non deterministic。Instant。We've lost the determinism。

Take a single threaded imperative program， hook that up to a differential equation。

 what's the interaction？Who knows？Implement it on the bench and find out。Right。We are actually。

 we don't have a deterministic model for the interactions between those things。

 because in order to have a deterministic model， we need to be able to understand in great detail。

 the timing。And the timing is not included in the cyber models。It's just not there。Okay。

So if you talk about a single threaded imperative program。

 what does it mean to correctly execute that program？Well。

 the correctness of the execution has nothing to do with how long it takes to do anything。Okay。

 your C program is will execute perfectly correctly on a machine with a 1 kilohertz clock。

As it will on a machine with a1 gigahertz clock。Okay。

The correctness of the execution of the program doesn't depend on the timing。

So how do you control timing in programs？Well， you actually have to step outside of the single threaded imperative programming model。

We learned how to do that。You set up， you write to a memory map register to talk to an external piece of hardware。

Which isn't part of your programming model at all。 As far as the programming model is concerned。

 all you've done is written of value to memory。But there's a side effect implemented by the hardware。

That the hardware will raise an interrupt request sometime later。When later？

It depends on the hardware。Right。And do you know what that hardware is， well， no。

 actually you probably don't even have a model of what that hardware is， well。

 you kind of have a model in the spec sheet for the particular board that you're using。ok。

If you delve into the documentation， it gives you kind of a model of how the timer works。

 but that model is not included in your program and so the program as an engineering artifact says nothing about timing。

 it just as you write to a memory location。And something happens。So in effect。

 if you're programming embedded systems， you're not using a map。There's no map。

 there's no abstraction that you're working with that is talking about the overall system dynamics。

ThatThis to me， is the major flaw and the biggest intellectual challenge with cyber physicalical systems is how can we in fact。

Regain。A deterministic model for these kinds of systems。And I'll give you a hint。

 I'll show you some ideas about how to do that， but the point is。

 so soon as you put these things together， you've got your single threaded imperative program。

 you could come up with a deterministic model of your network as well， okay。Discreet event models。

 like used in the widely used network simulator NS S3。It's a deterministic。

 concurrent model of computation， and you can come up with deterministic models of networks。

I don't confuse this， by the way， you can have a deterministic model that you use for Monte Carlo simulations。

So you can use a deterministic model to simulate random phenomena。ok。

But the randomness is still deterministic in the computer。

 you generate random numbers according to an algorithm。And you're looking for possible behaviors。

 but there's enormous value in the model itself being deterministic。

And in network simulators and models of networks， these are almost always fundamentally deterministic models。

 even when you overlay on top of them a stochastic behavior。All right。

So you've got this deterministic model of the physical plant。

 this deterministic model of the network， this deterministic model of the single threaded imperative program。

 but when you put these together，The behavior is no longer- there's no deterministic model now that represents the conjunction of those models。

It just doesn't exist。So what do you get when you put these things together。

 whether you get whatever you get from your physical realization。So。As a consequence。

Since the models are disjoint， they have incompatible semantics， okay。

 they don't play together nicely。 You don't get a deterministic model when you compose them。

You're stuck with。The prototype and test style of design。Which many of you in your projects have。

Fing back on。Because， well， it's pretty hard to do otherwise with today's technology。Okay。

It's very challenging to avoid this prototype and test style because we don't have good models that con join these behaviors。

Right？So in this course， we've made several attempts to understand this problem。Okay。

Looking the chapter 10 topic， looking at IO。How interrupt service regime geness work。

How they're really， really messy and really ugly， and they disrupt a lot of the nice properties of single threaded imperative programs。

ok。Certainly， if you want to do timing analysis on programs。

 you typically have to assume that this chapter has been ripped out of the book and thrown away。

And no IO is being done。Because if you're allowing interrupts to occur at arbitrary times。

 then timing analysis of your program is pretty much meaning。So this is a major。

Obstacle really to building reliable systems。It's an obstacle。Yet this is the way IO is done。

By everybody， universally。Will it stay this way， I don't think so。ok。

I'm glad you guys all are learning and have learned how to do this。

Be prepared to throw it away because it will go away， I'm convinced it's a lousy way to do it。嗯。

Multiitasking is even worse。I mean， it becomes enabled by that interrupt style where you can have multiple threads that are interacting through shared memory。

Many of you went to the。Toyota， the talk from Philip Cooperman where he was talking about the Toyota unintended acceleration problems。

 so the Toyota embedded software。Is。Many threads。All interacting with global variables。Unguarded。ok。

Race conditions everywhere。The principle is。You know， well。

If a thread is going to read the value of the variable， it should always read the most recent value。

 of course。Why would you want to read an old value if you could read the most recent value？

The problem is。That。You now have a non deterterministic system。

So you could have a program that reads the most recent value of one variable。

 the most recent value of another variable， but those two values are inconsistent with one another。

Okay。One was updated， the other one hadn't quite gotten updated yet。

 they're out of alignment and they're two inconsistent representations of some physical system。Okay。

You have a non deterministic。Model now， and it becomes completely unanalyzable。It also becomes。

 by the way， completely， almost completely untestable。

One of the great values of a deterministic model is that you can do regression testing。Okay。

 regression testing means。You define the inputs。And you check to see that the outputs match what's expected。

But if the model is non deterministic， then what's expected？You don't know。

 so you can't do regression testing。Okay， so the way you test the Toyota software。

Is you put test drivers into prototypes of cars and have them drive for millions of hours on roads。

That's how you test them because in the absence of a deterministic model。

 you don't really have a better testing technique。Okay。嗯。就。Scheduling。

 you can try to rein in the problem。Put semaphoes and locks in。But this is。Actually。

 a pretty weak technique。 Basically， you're taking a wildly non deterministic model and you're trying to rein in the nondeminism here and there。

They try to keep it under control。ok。That's very different。

 I want to contrast that starkly with synchronous digital logic。

Synchronous digital logic is not about taking a non deterterministic model and reining it in here and there。

It's about throwing out the nondeminism altogether and building a simple deterministic model。

And then making it incumbent on the physical system to match that model。

So if you make transistors and gates。It's up to you to match the model。😡。

As opposed to the usual thing that scientists do right。

Constructs models that have to match the physical world。

An engineer constructs physical systems that have to match the model。

That enables engineers to be creative about modeling。Scientists。

 you know if the model doesn't reflect what the physical world does， it's not a very useful model。

 but with engineers， actually it's not that way。You can come up with useful models and then figure out how to make the physical system match that model。

Okay。ItOne of the reasons I like being an engineer。knowThere's room for creativity there。Okay。

 so scheduling was another。Aspect of how we try to understand the problem notice。

I don't put this in the category of trying to solve the problem。This is part of the problem。ok。

It's not part of the solution。So。The goal of this chapter is to understand the problem。

How to solve it。Is when we get into。Big models of computation。

The synchronous composition of state machines， for example。That's a deterministic model。

Very different from multi threaded programs。Very different from interrupt driven IO。Okay。

It's a detererministic model that you can analyze， you can prove theorems about it。And moreover。

 we know you can create faithful implementations in the physical world， it's been done in circuits。

It was very， very valuable in circuits。Ccus， synchronous digital circuits are in fact following the same model of computation as synchronous reactive compositions of state machines。

 it's the same model of computation， it's a deterministic model of computation。Very valuable。

Once we have deterministic models， we can analyze them。ok。Without the deterministic models。

 it's very difficult to analyze。Okay， but we can analyze them and moreover， we can。

Construct really good engineering technique。So in chapter 14。

 we talked about the substitutability of components。When can if you have a prototype of a system。

 it's working great。Okay， but you used， you overpowered the microprocessor， right， you got。

 it's just a way， way over design， right youve put in a。You know，1 gigahertz。

Arm processor that consumes half a lot of power。And。What you're doing with it is very light。

 so how do you know that you could substitute in something else？In place of that microprocessor。

So this chapter is all about understanding what it means to be able to assert with respect to models when something is a valid substitute for something else。

So this abstraction and refinement relation。What we talked about in this chapter is about that substitutability。

 and it's not of much value without deterministic models。

 You need deterministic models to be able to use this kind of。Verification techniques。

 which we looked at in chapter 15， where you do exploration of the state space right。

Another one of the techniques that we looked at。And of course， quantitative analysis。Which was。

Based on a fiction。 you take a program， you break it down into basic blocks。You assume。

 you know that a bound on the execution time of those basic blocks。 which is a bold assumption。

And then you analyze paths through the program。 You can analyze the paths through the program。

 because。It's single threaded imperative programs。It's a deterministic model。

 that's the reason you can do the analysis without the deterministic model。

 you can't do that analysis。ok。So。嗯。Is this a complete solution？No， I mean。

These are attempts to solve the problem and theyre baby steps along the way。

There's a lot more to be done。So let me give you a hint of some of the things you can do。Okay。

So I'd like to start with one research project which is one of my favorite ones。

 some of you have actually been interacting in your projects with this research effort。

My grad student， Michael Zimmer。Is the lead guy on this？

But what he's doing is trying to solve this problem that。

What it means to correctly execute a program has nothing to do with timing。

That's a problem if you're interested in cyber physical systems， cyber physical interactions。

 the physical world cares a lot about timing。It's not going to work。For your software world。

 your cyber world to not care about timing。So how can you make your software care about timing？Now。

 the fact is that the microprocessors on which we build our software。

Are all designed using synchronous digital logic。Okay， pretty much universal。

There's a few experimental ones out there using asynchronous logic。

There' have been experimental ones using asynchronous logic for 40 years， they've never caught on。

Synchronous Digital logic is the solution that works。Because of the determinism in the model。 Okay。

 so the underlying technology in the microprocessor is actually capable of a tremendous deterministic behavior。

It can faithfully emulate a deterministic model。嗯。The problem is the software abstractions that we overlay on top of this。

As soon as we specify that， what that circuit should do is this。We've constructed another model。

And that model has actually hidden from us， one of the key properties of that underlying circuit。

Which is that actually it has very predictable timing。Very controllable timing。Okay。

The abstraction hides that。So we lose that property of the underlying technology as soon as we move to this abstraction。

We can solve that problem Okay so this research project is called pret。

 which is a wonderful acronym because it has at least five meanings。

It stands for precisionciion time processors， Preictable and repeatable timing。

Or performance with repeatable timing， it's easy to get repeatable timing if you don't care about performance。

喂。Just make everything very slow。Okay，And you can get repeatable timing pretty easily。

But if you care about performance， it's much more challenging。

So the fourth meaning is the pret is the French word for ready。 which has a timing connotation。

 and it's the Dutch word for fun。So and it's a fun project。嗯。

This project has been looking at the micro architectureitect level。

 so how do you fix the processor architecture level so that you can regain control over timing at the software level？

So the premise is it's basically rebuilding a bridge between two technologies。

You've got synchronous digital logic that's capable of very repeatable， controllable timing。Okay。

 and you have programs。How can we make those programs have the repeatable， predictable。

 controllable timing of the underlying technology？And the fact is that has not been a goal in computer architecture for the last 40 years。

 So computer architects have invented really fancy techniques。For dealing with deep pipelines。

 for example， you know， doing branch prediction or speculative execution or。Dynamic dispatch。

 these are all techniques that make timing very difficult to predict and very difficult to control。

But on average， they make very good use of a pipeline， so they give you good performance。

 but at the expense of losing control over timing。ok。Similarly， memory hierarchies。

Extremely valuable to have memory hierarchies because。Fast memories are expensive。

 they're expensive in energy。 They're expensive in silicon area， right。

 static ras take at a minimum six or seven transistors versus one transistor dynamic ras。

And they consume a lot more power。So they don't scale as well， right。

 so you need to have memory hierarchies in order to be able to get decent performance。

And caching techniques。Make it extremely difficult to control timing。Cashs。

 especially when you combine them with。IO techniques like interrupts。Become。Extremely difficult。

 if not impossible， to control。Okay， the interrupt service routine can cause your you know。

 data that's in cash to spill at inopportune time and can wildly change the timing behavior of your program。

And moreover， it can do it very， very rarely。By the way， in the context of embedded systems。

 in my opinion。Falults that occur rarely are much worse than faults that occur frequently。ok。

Because faults that occur frequently， you discover them earlier， right faults that occur rarely。

 you might not discover them until you've killed some people。ok。And that's just not okay。

 right so faults that occur rarely are much more treacherous。Then faults that occur frequently。Okay。

 so the pret project is dealing with techniques for。

Getting control over timing for all three of these problem areas。

So to give you a hint of how this is done。In the case of pipelining。Okay。

Typical way that a pipeline works is you inject instructions from a single thread into the pipeline。

 Okay， if one of them is a branch。Okay。Typically， the branch condition isn't known early enough to fetch the next instruction。

So you might speculatively execute an instruction or two， okay， and then throw out the results。

If you guessed wrong。Okay。But instead of doing that。

 why don't you just interleave threads in the pipeline？It's actually an old technique。

 it was first used in the 1960s in the CDC 6600。Where they took。Two， three， four programs。

 interleave them through the same pipeline so that。On a clock cycle by clock cycle basis。

 you're switching between programs。Each program has its own register set。Registers are cheap， okay。

 it's not a lot of memory， so you can replicate your register set the cost of registers， by the way。

Is not the silicon area。It's the number of bits in the instruction word that it takes to address the register。

 That's the cost。The reason for not having a big register set is you need more bits in the instruction word to address the registers。

And that's where you hit the cost， it's not the cost of the hardware。Okay。

 so replicating the hardware is cheap。And then you can interleave instructions through the pipeline and you can make each instruction stream perfectly deterministic。

No need to do branch prediction， no need to do speculative execution。

 everything executes in lockstep with predictable timing。You can use similar techniques and memories。

ok。You can also use similar techniques for IO， there's a British company called ExMoss that makes one of these thread interlead processors。

And the way that they do IO is that they have a variable number of threads that they interleave through the processor。

 When an interrupt request comes in， they just kick in a new register set。

And process the interrupt service routine in that new thread。So the consequence is that if you have。

 say you have four threads running and an interrupt request comes in。

It'll switch over into a mode where five threads are running。Each thread slows down by exactly 20%。

Okay， no more。Gives you a nice bound on the effect that IO can have。

It will slow you down by no more than 20%。Compare that to the standard interrupt service routine。

What's the bound on the timing effect of your interrupts on your program？Well。

In order to know that bound， you need to do an awful lot of analysis of that interrupt service routine。

And make a lot of assumptions that are probably fictitious to begin with。

 it's very difficult to come up with good bounds on the timing effects of IO with the conventional technique。

But with this technique， you can come up with an absolutely rock solid bound on the effect that IO has on your program。

ok。So this creates a number of opportunities， right if you have improvements in determinism。

 which means improvements in analyzability， improvements in testability。Okay。

 you can test programs now。Because you have a well defined correct behavior。

You have substitutable hardware。Right you know， this question of substitutable hardware is an interesting one。

 I first learned the real implications of this when I was talking to a guy who had worked on the Boeing 777。

Which was Boeing's first fly by wire aircraft。So the Boeing 777 started flying in 1995。Okay。

And when an aircraft manufacturer starts making a plane， they expect to make it for 50 years。

The Boeing 777 is still being ordered， still being made。Okay， and will be probably for another 20。

 30 years。This guy who worked on the project told me。

That every Boeing 777 made over that 50 year span。We'll use microprocessors that were made in the early 1990s。

Boeing stockpiled those microprocessors。Boeing is storing those microprocessors in liquid helium to slow down the natural diffusion processes in the silicon。

So that when a。Plae rolls off the production line in the year 2030。

 The microprocessors will still behave the way that they did in 1995。

Couldn't you just put in a faster microprocessor to run the same program？Unfortunately， no。

You have no assurance。That the program will behave the same way。Okay， because。

The correctness of the execution is just the correctness of the execution of that single threaded imperative program。

 and it doesn't say anything about its interaction with the outside world。Okay。

And it cost Boeing approximately a billion dollars just on the certification process for the safety critical software for the 777。

If they decide if they run out of microprocessors。This guy told me they will stop making the plane。

It's too expensive to redo the certification。Okay， they will just stop making the plane。Now， to me。

 this is a profound embarrassment to engineering。 right， This is a failure of engineering。

 It means we don't have good models。Because yes， it's a software defined airplane。No。

 it isn't a software defined airplane actually， after all。

It's defined by the software and the particular microprocessors that were made in the early 1990s。

Boeing insisted that the vendor of the microprocessors manufacture all of the microprocessors on the same production line in the same week。

ok。Because they were worried about smallvariabilities that might occur among the microprocessor implementations。

This is crazy。 I mean， this is just bad engineering。 So this problem will be solved， okay。So。

I think let me make one more point and then I'm going to turn it over to the Ada Kapanu folks 10 minutes is enough to do this it。

O。So。What can you do from a programming model perspective once you've got a prep machine？Okay。

So here's the kind of thing that we'd like to do。We'd like to have a code block shown in green。

And I'd like to embed that in a block that says， all right。

 I want to assure that that block never takes more than 500 milliseconds or whatever。ok。

Now I should always， it's good engineering practice to put in fault handling。Even if you can prove。

That the fault won't occur in your model because it could occur in the physical realization。

 even if it doesn't occur in the model。 right， So you might have a panic routine。

That will catch violations of the timing。Okay， now here's a question。

 how would you do this today in a C program of this conventional microprocessor？嗯ん。

If you think about it， it's actually not so easy right because you want to abort the execution of that code block as soon as you hit that 500 millisecond boundary。

 that suggests you better set a timer interrupt。the interrupt service routine should kick in。

But now you have a bit of a mess to deal with， right because you preempted a program at an arbitrary point in its execution。

And you don't want to resume it。You don't want to return from interrupt。

But it's got a bunch of stuff on the stack。 it's got a bunch of variables。 Okay。

 it may have updated stuff in memory， So you've got a mess to clean up now。

The typical way that's used today is to use a technique in see called set jump and long jump。

And the way that this works is Se Ju is a library procedure。That。Always returns false。Okay。

 whenever you call it， it returns false。That's kind of a stupid library procedure。Well。

But nevertheless， it always returns false， so you start executing your code block。

 you set up a timer interrupt， you start executing your code block。Okay。And。If your timer。

 if your code block completes in time， you deactivate your interrupt request。Allright。And you go on。

 and you're happy。But if your timer interrupt kicks in。

Then you invoke another procedure in this same library called Long jumpump。Okay。What Long jump does。

Is it unrolls the stack back to the point where SeJb was。And returns true。Okay。

So what' will happen now is as soon as you've done this long jump， you go back to that if statement。

 as if you hadn't executed any of this code， anything that got put on the stack is now obliterated。

And you now branch into your panic routine。This is conips。And this is really hard to get right。Okay。

So in the PRt project， we've talked about what we really want is to be able to set a timing requirement。

 execute a code block， and specify what we call the MTFD instruction。MTFT means。Meet the。

Final deadline。Okay。Just do it， okay。There's no excuse except a hardware failure。Okay。

 your only excuse for not for failing to execute this in the specified time is a hardware failure。

Okay， so what we want is a deterministic model， we can do that with prep machines。Okay。

 I'm going to turn it over to the Ada Kaappaooop folks， thanks for your attention。

 and I'll see you on Thursday for the fun part， the midterm。



![](img/948e65e23b22241b84ce2652673b67aa_9.png)

![](img/948e65e23b22241b84ce2652673b67aa_10.png)