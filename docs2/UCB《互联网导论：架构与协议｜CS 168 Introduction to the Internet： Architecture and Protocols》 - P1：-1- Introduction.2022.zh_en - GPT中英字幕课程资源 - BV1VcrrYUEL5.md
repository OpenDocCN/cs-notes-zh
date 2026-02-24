# UCB《互联网导论：架构与协议｜CS 168 Introduction to the Internet： Architecture and Protocols》 - P1：-1- Introduction.2022.zh_en - GPT中英字幕课程资源 - BV1VcrrYUEL5

![](img/daae0b59001c172eb1675e7c4e16700f_0.png)

Good morning everyone and welcome to CS 168， I am Serviia Ranasmi and I'll be your instructor for this semester。

😊，Just to go into what we hope to cover today， two topics at a very high level。

 the first is I would like to give you a sense of what this course is going to be about。

 what you can expect to learn and not learn what is the workload and so on。

And then we take a quick break and the second half of this lecture will talk about class logistics。

 exams， creating lead policies， enrollment and so on。And so jumping into it， you know。

 to give you a sense of what this class is about， I thought what I' would do is start with the title of this course。

 so we say introduction to the internet protocols and architectureect。And there are three key terms。

 internet protocols and architecture， and so what we're going to do for the next 40 minutes or so is dive a little deeper into each one of these terms and break down what we mean by them and what's involved in studying about these terms。

😊，So let's start with the internet， we obviously all of us know what the internet is。

 but more specifically when you know you ask about or talk about the internet。

 it can have two very different meanings depending on whom you're talking to。

If you ask me or one of your Ts or one of you by the end of this semester。

The term internet means to us something that's like plumbing infrastructure。

 it's the infrastructure that ties together all of the devices we have that want to communicate。

And the technologies that are needed to build that infrastructure and make it function are things in terms that probably most people have never heard about。

 things like TCP， BGP， DNS， ISIS， and so on。And the other meaning though。

 if you ask your parents or your grandparents or many of your friends what they think of as the internet。

 it tends to mean this ecosystem of applications that are built on top of the above infrastructure。

 so this is things like Netflix and YouTube and Twitter and Facebook and so on。😊，For this class。

 when we talk about the internet， we're really using the first definition。

This class is about how we build that infrastructure that underlies all of these applications and for me at least I find this question about how did one go off and build this global infrastructure that supports all of these applications。

😊，Personally， I find that the more interesting question of the two。

 know I'm sure these applications are all very interesting。

 but enabling them seems like a really powerful piece of technology。😊，And so with that。

 let me try and dig a little deeper into what I mean by infrastructure plumbing infrastructure。

 the analogy we often like to give you know， if you talk about why internet infrastructure is like plumbing。

 it's a little bit， you know if you think about the utility system and the entire giant massive ecosystem and infrastructure built up to bring water to your home。

That's plumbing infrastructure and you turn on the tap and you collect that water。

 what you do with that water there's lots of different things right and the plumbing infrastructure doesn't actually care。

And so that's a little bit what I mean by infrastructure， but let's unpack what exactly is。😊。

This internet infrastructure， what are the components of this infrastructure？

And at a high level there are really three pieces of three important components the first what we call Endhost。

 these are any devices that are using the internet。

 they're using the internet to communicate we each of us have way too many of them your iPad。

 your smartphone， your laptops， companies like Google will have thousands or millions even of servers that are hosting content that are also endhosts on the internet。

😊，And these days we have things like TVs and your car is using the internet one of my favorite ones is something like a hot pacemaker these days you can get a pacemaker that will directly communicate the status of your health to doctors and so really the scope of these devices that are using the internet is ever increasing fascinatingly diverse for the purpose of this class we're going to represent them by this blue dot and we're going to say that this is an endhost。

The second component is something we' call a switch these are devices that are not necessarily running applications。

 but they are using or they're helping these end hosts to communicate so their job is to help other devices communicate。

And so switch might be the $10 home routeer you have at home。

 it could be the $10 million routeer that AT&T is deploying in their global backbone network。

Your phone， when you。Configure it to act as a hotspot， it's a switch on the internet。

it so we have end hosts and we have switches and the last piece as you'd expect are links。

 these are the links that connect end hoststs to switches and that connect switches to other switches。

And again much like endhos and switches， there's a whole variety of the kinds of links you can expect。

 you have copper links， you have cables， you have fiber optic links， you have wireless links。

 you can take an entire class in the E department just on how you should build a fiber link how do you build a lasers。

 how do you have good signal strength and so on the same there are multiple classes on how you build wireless links or wireless technologies we're not really in this class going to get into the specifics of any one particular link technology we operate slightly our view of networking a slightly higher level we for the most part we're going to be in this course abstracting all of these different。

😊，LisLi technologies or low level technologies as just a link。

 it serves to interconnect to endpoints。And so from a nuts and bolts picture。

 this is kind of what the internet infrastructure is made up of。

 but this picture is not complete with one without one additional ingredient and that is that you know if you think of the internet it's not an idea or concept。

 it's an artifact， it's an actual thing you can touch it， you can poke it。😊。

And because it is know an artifact and a commercial artifact。

 we need someone who is building this infrastructure， operating it， managing it， upgrading it。

 and so on。And what is unique about the internet is that there is no one entity or organization that runs the internet instead the internet has a wide variety of companies or institutions that each own and operate and manage one part of the internet they have their own。

Portion of the network that they are in charge of。And so these might be companies like AT&T for example。

 or UC Berkeley there's an entire networking team in Berkeley that builds and operates and manages Berkeley's networking infrastructure。

 in fact there are multiple teams that we have campus networking we have each department has their own networking and so on a company like AWS also has a massive network and this has been a switch over time where it used to be that there were companies like the ATNTs and Verizs of the world that owned and operated networking the network infrastructure and then there were companies that built applications on top。

But with cloud computing this view of the world has changed and now cloud providers all build and operate large global networks。

 so for example， the largest network in the world today is actually Google's backbone network。

The important thing to keep in mind though， when we talk about these providers and we're going to call them ISPs or internet service providers。

 and the important thing is that they operate their administratively， economically。

 they are independent entities， and they operate independently。

So AT&T gets to build and run their network the way they choose to without consulting or agreeing with Google or with UC Berkeley。

 for example。And this might seem like it's not a technical factor。

 like it's an economic financial concern， but it actually has deep implications for how we build and how the technology works。

😊，And this is because we have to remember that each of these ISPs they're in a competitive environment ET&T is competing with Verizon。

 Google is competing with AWS and Azure and so there is competing entities that are working together to provide。

😊，Network connectivity， but because they act independently and because they are competing entities。

They don't always reveal the information they that they might one might think you want them to so for example。

 if a link in AT&T goes down AT&T might not want to tell anyone about it necessarily。

 they will do whatever they can to。Have it not affect other users， but they won't tell everyone， hey。

 my link is done。And so now another if you're a Verizon or if you're Google。

For your users you have to kind of figure out whether there's a fault somewhere and you have to decide oh it looks like AT&T is not performing that well so I'm actually going to send my traffic somewhere else and so this is why you know sometimes as a user if you've had bad internet connectivity and you call your ISP and they don't quite seem to know what's wrong either or it takes them a long time to figure out what's wrong it's because they have there these multiple ISPs that are doing kind of their own thing。

And so even though this comes from the fact that they are independent administrative entities。

 the implications for how we design technology are great right。

 this is are deep because think of this as you know you're building a system where you get no notifications when there are failures or you have no visibility into where failures are and so you start designing other methods like for example you might send traffic for multiple vantage points and you would say oh。

 you know every time my traffic hits AT&T in the West Coast I start seeing poor performance that's how I decide。

😊，That there's a problem with ATTs network and then you decide how to react to that。

 so you've now built an entire failure detection method that。

Kind of accommodates the fact that you're working in an ecosystem where different companies are operating different parts of the infrastructure。

So that's ISP。And that's actually what we have here， a pretty complete。

 high level but complete view of what internet infrastructure looks like。

And you know a lot of this semester is going to be both understanding how this whole picture works。

 but also digging into individual pieces of this infrastructure and how they work。

 so making this picture get more and more detailed over time。What do we do with this infrastructure。

 what's the point of having this entire infrastructure？

Kind of nice thing about the internet is I can summarize the job that the internet does or the task of the internet very succinctly with just one line。

 which is that the job of the internet is to transfer or the job of this infrastructure really is to transfer data between EndHse so we build up all of this infrastructure for that one task。

 transfer data between EndHse。So if I have an end host here， it has some data to send。

What I'm going to do is find a path through the network from that source to that destination。

And then I'm going to move that data along that path。This might seem like a really simple task。

 it's not as simple as it might sound so for example let's think about setting finding that path that you have to find a path a sequence of these switches and links。

😊，That takes you from the source to a destination。You have to make sure you have enough capacity along that path。

For you to be able to send that data， you have to make sure that there's no failure at a particular point in time along that path。

And even if you've done all of that you have to make sure actually that that path is it meets the needs of the ISPs that the ISP is running their infrastructure okay with you sending data on that particular path so for example if Google told perfectly there's no way you can send me that traffic then this would not be a viable path and so you have to take that into account。

So not as simple as it seems， but conceptually simple to understand。😊。

It's also while this might seem like a very simple task and very obvious task， like of course。

 your infrastructure is designed to transfer data between endHs。😊。

This goal is actually a little more subtle and a little wiser than it might seem at first glance。

 it's easy to overlook the wisdom of this goal in the following sense that。

I did not say that the goal of the internet is to transfer YouTube data between NHse。

If that had been the goal of the internet， we would have had an internet that transfers YouTube data and Netflix would have had to build their own internet to transfer Netflix data that's not what we have what we have instead is a very general infrastructure。

And you might be thinking， yeah， of course it seems obvious。

 why would you ever build an internet for YouTube and an internet for Netflix。

 but it's worth noting that actually prior to the internet。

All the communication networks that people had built before then were purpose built they were built for a particular use case。

 a great example of this is the phone network the phone network was a global communication infrastructure that had been built for one goal to carry audio traffic and so the only thing the phone network ever did was carry voice traffic。

That was pretty much it whereas on the internet instead the early designers of the internet。

 they built this one communication infrastructure that has served all kinds of needs when they first built this infrastructure you know there was no email。

 there was no web there was no Netflix， no YouTube， no TikTok。😊。

And yet they built an infrastructure that because it was designed to be general。

 was able to support all of these applications over the years。And so it's。A simple particularly。

 I think， elegant goal for communication infrastructure to have。To take my data。

It has to not have a failure at any particular point in time。But importantly。

 also it has to match the economic arrangements between Ips。I cannot say， oh。

 there's a link here between Chicago and San Francisco I'm going to send my data on it。

 I can only send my data over it if let's say AM TH Chicago and Verizon at in San Francisco have agreed that it is okay for me to send my data over that traffic over that link。

来 the box。A simple thing like a part is actually quite complex when you unpacked。😊。

It's also this sounds like a very simple goal。 Trans data between and host， Pre obvious almost。

But it's actually a wiser goal than it seems at first， because notice just for example。

 it doesn't say that the goal of the Internet is to transfer YouTube traffic data between N。

If that had been the goal of the Internet， the only thing we would have done with the Internet was watch YouTube。

Instead， we do all of these other things。And this again， sounds like you would say。

 why would you ever build a network， an Internet that is for YouTube data。It seems obvious to us now。

 but if you think of all communication networks that were built prior to the internet。

 they were purpose built。So the phone network was built to carry audio。

 That is the only thing the phone network ever did。

The military would build networks to allow their submargs to communicate。

 And that was the only use they had for it。 The National labs had a network for file transfers。

 All they did with it was transfer files。The Internet was the first infrastructure that was built to be a general focused。

 communication。And， you know， we enjoy all the benefits from that design decision having been made。

 And it's actually nice to realize that the people that benefit the Internet。

 they made that design decision at a point in time when they had no idea what the Internet was going to be used for。

 They found people who transfer files。我装出垃圾板。They never thought females， another part of the world。

 They thought never thought of。即咗 and doing like that。

So that's kind of cool that you built an infrastructure that would evolve to do all these things that no one had imagined。

Today we talk about self driving T and AI and BIOB。Okay， so with that， that was the internet。

 and I hope you get kind of what aspect of the internet we are interested in in this stuff。

The second victim here is protocol。And we talk about protocols。

 let me go back to that picture we had， but let me focus only on the endpoint。

 let's forget about those switches and links for a minute。😊。

And we set the goal of the Internet is to transfer data。

But then we all know what we're doing with the Internet。That's how we use。The Internet。

And so if you dig a little bit into any one of these applications。

Any internet application is a distributed application。And somewhere the two endpoint。

Somebody has getting some code that if you take。Into that quote， what youll see is something like。

 let's say Alice wants to send something to Bob Somewhere in there is a send message call。

 I'm going to send a message to Bob。And somewhere in involves and see code that says。

 I'm going to receive a message。So when you go out and you know you have a job and if your job involves writing code。

 there will come a point in time where you have to write a distributed application and I actually can't think of any application we write today that's not a distributed application。

 Nobody writes single CPUU code anymore， just not a thing。

So when you get tasked withing that application， even if you know nothing or don't care about switches and links and the plumbing of the internet。

What you will have to do is write a specification for how the endpoint in your application are exchanging messages。

How do you use that send the code。And so you could design a specification that looked something like in my what what called protocol。

 but in my message。Exition。But， somebody has to say hello。

And then the other endpoint has to say hello back。And then Alice says， can you give me that file？

And then， Bob respond with the fire。This is a perfectly reasonable。

 sensible way to design this necessary specification。😊。

It tells you what the expected behavior from both sidess。

It's not the only way you could have defined specification。

 You could have instead of that very civilized coaches。Spation。

 you could have said the way I want Alice involved to communicate。

Al says hello and then Alice very aggressively， so give me the file， give me that file。

 give me that file and doesn't stop until she gets that fight。Which one is better， You know。

 I this aggressive specification better。The previous one。This is obviously bad。

It's actually not obviously bad。 It really depends on what your goal was。

 If your goal was to get that file as soon as possible and you had plenty of network capacity to burn。

This is the totallyifying way to go about doing it。If you wanted to be more careful then， you know。

 make sure both sides are ready， then the previous justation was。

Once you define your specification though， that determines your application's behavior。

 It determines your application's performance as well to some degree。

 And so you will find endless people optimizing these semester specifications。But once you define it。

 both sides are expected to forward。 So， for example， if you had gone。

 if your design was that very courteous specification。Then this， when Alice does this。

 this is a violation of your specification。Maybe it's because you had a bug in your code。

 this was not acceptable behavior。Or maybe Alice is malicious。And that's wonderful。

So going about tell you what the correct behavior points is。

AndSo to look at what a protocol is is a specification of the messages that communicating entities will exchange。

😊，It's the syntax of those messages， it's the semantics。Mesセジ。た就的。

It's very much like conversational conventions。 when we meet。

 we have these conventions that are engageded in our heads about how we communicate to wait for't I。

It's something polite like with the other person to respond back。

Designing a good protocol is actually harder than it first seems。

 because you realize that one of the things on the Internet is you have to reason about every possible behavior from both endpoints。

 So what happens if Alice said hello， and Bob did not say hello for a very long time。

 Should Alice say hello again。 Should Alice try somebody else。

What if I try saying hello to a different person， and then Bob comes back and says， hello， I'm here。

哦，我的。And they said， hell。Bob responded with hello， and then he said， give me that file。 And Bob said。

 hello and。You have to reason about every possibility thing。

 what a bo crashed in the middle of that communication。😊，And so this is what makes protocol design。

 I think fun， but also very often you will find that this causes a ton of bugs in people that are not where they find message specification or protocol specification。

Actually leads to endless bugs and debugging sessions the railroad。With that， our last。

Stone that we had here architecture。And to get to architecture。

 this is a little the hardest to explain and also I think this is the course that talks about system architecture most deeply in some way。

😊，And so I'm going to take you in a little bit of a detail before I get to talking about what Internet architecture means。

And then I'm going to go with。Why study the Internet。What why they discuss， Why should you be in。

Both도하는 about all。There's an easy and obvious answer that one can offer。

 which is that the Internet has and is continuing to transform pretty much everything。

 everything and how we live our lives。 Think about how you would have known to come here。

I just bath you know at this time。If we didn't have the Internet。

Pretty much every aspect of our license。Influenced or helped or aided by the Internet from how you reach was。

 if you read the news。The Internet is a huge factor in how was talking。

In how the economy of countries goes up and down and so on。It's actually。

 when you think about the transformative aspect of the Internet。

 you'd have to almost go as far by a ascilin press as the telephone system to think of a technology that so transforms society and the way。

Ithi is kind of cool。 And it happened in not that much time。

You probably you were born in a time when the Internet was everywhere well and you just assumed。

 but suddenly for me， that was not the case。I was had easy one generation away from you。

 and I indeed had access to the Internet when I was young age undergrad。

 So I had an Internet free childhood team。 You probably can't imagine what。looks like。

But that was reality。 And one generation that's going transformed the entire way the entire global。

But you knew this。 You didn't need me to tell you that the Internet is important。

 All that this is telling you is it's important， but you knew that。

What I would want you to think about is why is the internet interesting？

As computer scientists and as technologists， why is the Internet interesting？And this interesting。

 you know， the Internet actually networking as a field is not that old。

Compared to fields like algorithms or even AI or compilers， programming languages。

Butley had their first go networking faculty was the own storyeller still very much here。

 not even in a one of our senior faculty。 He joined them I think 2000 or so。

So it's a relatively new field within computer science。😊，And you know， what。

 why networking is a field was often a puzzle， even with amongst computer scientists。

 So if you ask the keys， for example。They will always。

 they will often ask questions like what is your formal model for the Internet？Or instant optum。

But the Internet has no formal model， and we know would be very cool if we had it。

 but we have no notion， certainly no great upon notion about what it means to have an optimal internet。

 So this is very strange to case。 How do you solve a problem metric find your problem。

It's also even for operating systems or traditional software computer scientists。They think， well。

 we've always had inter process communication， like we've always had this notion of processes and they communicate。

 So what's so special about now that communication is happening over。And we'll get into all this。

The hardware people are often even the most。Confuseue， confused。 If you're a CPU architect。

 you know what your CPU is doing every single cycle。You know。

 exactly how many cycles it takes an instruction to execute。

 There are well definedfin performance benchmarks that guide the entire industry and research。

 A CPU designer can compete and come back and say， my CPU runs X percent faster。

 it takes1% less power and you won， you know what success is。Not so clear on the Internet。

 So they ask you， what are your performance benchmarks for the Internet or how is the Internet performing today。

 There isn't a simple answer to that。I can't get onto the Internet， shameing me。

 but that doesn't mean the Internet is not a form。What does it actually mean to talk about performance on the Internet？

And this goes on all the way doing guidance。Why do you have a job that the internet seems to be working？

And so those are a few defining characteristics。😊，Those are a few sort of things that make networking as a feel confusing to people。

I don't have a py answer for you， but you know， this is exactly what networking is。 and this is why。

What I think the best way we had with explaining to people why it's interesting， and this is。

 I would say， an indication of a field that's still relatively young。

 like the fact that I have to talk for half now about why the internet is interesting is to think about a few defining characteristics of the internet。

So one is the distinction between a network versus the internet。

We have had communication technologies or network technologies for far longer than the Internet。

 even when we were beating on drums， that was a communication technology。

 So the Internet is not about a new or particular form of networking technology。

 It's not about ethernet。 It's not about cellular。 It's not about5 G 6 to or Wifi。

And we've always had those， we will always continue to have those。 The Internet is larger than that。

Instead， the goal of the Internet really is。To tie different networks together。

That when you read the opening lines of。The goals and motivation for the teams that built the original Internet。

 Their reasoning was we already have these kind of isolated pockets of networks。

 We have radio networks here。 We have the you know， high speed network for the national lab here。

 We want to be able to interconnect all。So it's not about how to build a particular network。

 It's about how to interpret。And that in itself is kind of an unusual goal。How do you。

Sa X percent good at interconnecting networks。Inherently of。

Not where they defined goal in terms of the traditional metrics and language that we used to。

At the same time， it is very powerful to be able to say I'm going to interconnect different networks。

 What do we do or what do we try to achieve in order to interconnect。Different networks。

We try to come up with a common language by which when these networks interface。

 they can understand the data on both sides。And so that leads us to what is， I think。

 actually probably the key defining aspect of the internet， which is it's a catated system。

That by design， it is intended to be a system where each ISPO， each entity。

 can build their network the way they want it we build。

And then we're just going to figure out we're going to cooperate in order to make those two networks interact。

This has a strange implication because you know interopcability is the most important goal and we have。

Tens of hundreds of thousands of ISP that interconnect with home the network。

But what it means is it gives rise to this fundamental challenge of how do you interconnect competing entities。

have competing network providers。 and yet the only way they get any value is for them to cooperate with each other。

So agency cannot say， I'm only going to connect to Google。

 I'm not going to connect to Amazon because even if they do that， they lose all their customers。

 and everyone wants to get。So they have to connect with people。

 Google cannot tell their customers andm not going to connect to Amazon。 All Google's customers are。

So one way or the other， they have to figure out a way to go。

And they cooperate through this common language or common protocol that willll be developing。

But it does lead to a constant tussle between business and technical factors。

So think about it from the perspective of your designing that common protocol。

 the common language between these ISCs。What information should you expose or if you're thinking of it as an API。

 What information should。Google Exp Amazon。If you're thinking of it from a technical perspective of finding parts and sending your data。

You should expose all kinds of information， you should say this is my topology。

 this is my current load， this is the cost of going over these lengths。

 these are the failures I'm happening having and if you expose all of that information。

 then you know the other side can do a great job of sending in just the right amount of traffic and just the right time in the right bus。

😊，So we would have a very efficient level， high performance， very reliable and so on。

But if you're honest， you don't really want to share all of that information right because it's your secret sauce。

Its the things you do to make your network perform more efficiently or more cost effectively than someone else。

And even worse， if your network is actually not that good。

Certain don't want to expose that information。So instead you get into this back and forth where yes。

 you could have designed a protocol that was optimal performance or optimal at cost or optimal or something。

 but is it crafted。Is to the incentives of ISP actually line up is the way that they actually settle money between them。

 Does that match what you're asking at a technical level？

And so you have this constant back and forth between technical factors and real world factors around incentives and economics and so on。

And this also complicates innovation。So I said that way we're going to federalerate the system is we're going to come to this common language that we speak the same language and hence we can exchange data back and forth。

But if you're a commercial entity， you know， how do you win， You win by differentiation。

 You win by having an innovation or a future that no one else has。

But if I have this great feature that I cannot expose to customers and I cannot expose to others because no one can use it if it's not part of a common language。

Then what's。It's like having your own personal vocabulary that no one else understands。

So it's very hard to figure out how you innovate。While still working in this graduate environment。

Similarly， upgrades， we've been talking about going from IPV 4 to IPV6 for 25 years now。

 you cannot have one day where you say， hey， the entire internet is going to upgrade today Every single I three a day。

 you're going to go from IPV 4 to IPV6。It not an option。

So instead you have to reason about I have a network that some people have IV4， some people have IV3。

 some have a mix of more， how do we work in this kind of environment？这犯罪为什？

Fundamental goals that me have to address and have to deal with that。 we design the Internet。

Federation， though， you those are all the challenges that come with federation when it has enabled this tremendous state。

 I think we've all seen these stats and I'm going to bo you。

I've tried to impressless you with how many people。

What is worth noting is that actually fedvation enable this tremendous scale。

Because it said everyone can build an networks on their own。

 and we're going to pull it together and be that much bigger they scale quickly。

All of these impressive stats that we see on our internet， our field now covers this internet scale。

😊，Internet scale apps， Internet scale clouds， it's just become part of our language in computer science。

In all this diversity and the dynamic range， however that told you， you know。

 you can have all of these different kinds of links and different link technologies。😊。

But you also have tremendous diversity and heterogeneity in performance。So for example。

 if I look at two servers that are next to each other in a data center。

 they can communicate at microsecond scale。😊，If I'm sending traffic to a satellite。

 it can take seconds。And the same thing goes with packet laws that can have extremely reliable links to links that drop most of you。

 90% of the traffic you see if it's an underwater cable of some。And so every time we design。

 we have to design for this kind of。Extreme heterogene and。

 And I want to emphasize if you're talking here about。Six or eight orders of magnitude。

If you listen to， for example， often CPU designers， they'll say， well。

 I'm going go from 32 GB of memory to 64 GB of memory。 or my cache is going from 16 night to 30 to9。

 and everyone gets all excited and concerned about it。 That's do。What do you going from1 to hundred。

And everyone has to have processes and think about it and everyone's worried about it。看。

On the Internet。 and it's not just over time that you have six or eight orders of magnitude。

At any point in time on the internet， we have a range of six to eight orders of magnitude of diversity。

So think now when you go back to that protocol or， very conservative。

What of all the going hello back and forth versus sister just sending all with your traffic。

You have to think about what kind of links is this。嗰话家 on。If it's going run over a satellite link。

 this is going to perform very differently from if you're running over a De bit Ethernet link in the data center。

So again， that heterogeneity and designing codeV， this is again。

 become part of what we think of as designing internet scale systems。

It extends not just to performance， it extends to the kinds of endpoints we see。

 the applications we see the users we。Including the fact that malicious users are now part of。

Combine that with another fundamental constraint is asynchronous operation。

 There is nothing we can do to go faster than the speed of light。In sending our data。

So if you think about this， consider a very simple protocol or message exchange where your machine in Berkeley is sending a message to New York。

And let's say you've had speed up like。Dad transfers， the best you could hope for。

To go the point through all the number crunching， it's basically saying。

 if I send a message for go from New York and back and I take just a geod and assume I'm traveling at this sea of light。

It's going to take me about 27 milliseconds for me to send a message and get a response back from you。

If I don think of a 3 gigahhertz state， they would pretty standard state today。

That is my machine Adtly， waiting for 27 milliseconds。That amount of time is。

I you take a think of that。Cys go second and。's yeah about 84 million cycles。

If I say that a modern CPU can do one instruction per cycle， which is pretty reasonable。

 that's 84 million instructions that your CPU could have been worrying about。

Or doing things could have been working while that message was going to New York and back。

So I think you is not going to stall while I wait for that message to come back。

So it's going to continue executing some kinds of instructions。What does this mean。

 This means that when my message comes back to。My state， the state of my system。

Has fundamentally changed from when I sent that message。 It is no longer the same。

The state of the machine in New York that sents that message has also changed by the time I hear about it。

And so this gives guys to fundamentally。 We have to deal with the fact that communication feedback is always needed。

And we have to deal with this aschrony in how we design applications。

And so when I tell about a failure， it actually happened worldwide。

What happened to all the traffic I'd sent？The queen when I。The failure happened and I actually。

And you think about all those messages were they lost， how will I know they were lost。

 what happened them？And then adding to all of this is point to failure。

 There are many components along the part from a network interface card switches to the links to the machines at the end。

The find there was the components along box between。There's easily generated not hundreds of them。

If you said that， you know， thats you have 50 components and each one of them was selective about 99% of the time。

 That means there's a 40% chance that communication will。But something along the box。

And then you have aynchrony。 It's going to take you some time to actually hear about that failure。

So again， hand failure up scale under all of。Extreme scale， extreme heteroity。

 isynchronly and being prone to failure。😊，The Internet is designed or the designers of the internet were the first ever actually developed the template for how to address this。

And that failure handling is actually now how pretty much all cloud systems or any system we built on top of the Internet。

We follow some of those。As to that finally constant evolution， touched on this earlier。

 the Internet that we knew， not just in the 70s when they first started building it。

 but even the 90s or the 200s， completely different from the Internet we have。And again。

 this means you cannot design for six story。 It's not like saying I'm designing for YouTube。

Orm designing for voice。 You're really designing for a very wide range of potential applications。

 including ones that you want to thought up with。So do we have all of that thing that the internet is a petated system。

 enormous almost scale， extremely heterogeneous， asynchronous， point of failure and constant cable。

So going back to this question about is internet architect or internet design， is it a science。

 is it an art what is it， it's too complex with theoretical models。

How do you model all of these constraints that I've told you about。Its。

Also the working code doesn't mean that much。 Let's say I write a piece of codes。

A new way of finding a God。My code compiles， I test it。

But it doesn't match the incentives of what ISCs want。

So what does it mean that I should compile my code， Not very much。

 I didn't design it to actually meet the customers needs some。 How would I even invest it。

 I could test it in a lab with 10 machines。But doesn't tell me very much about whether it's going run on the Internet at scale with failures and so on。

Performance benchmarks are definitely now。 I can measure the parts on the Internet。

 There are billions of parts on the Internet。 There's no way I can measure all of。

Even if I level the performance of a path today， it's going to change five minutes from now because different users and different applications will be sending。

It would definitely a change in the year when you have completely different applications。

So this question of how do you measure performance on the Internet is a huge field。

 People have conferences about this entire companies dedicated to doing the best jam about measuring internet。

And so all of this again， the creation of the Internet required a new design paradigm time when people started building the Internet computer。

Then have the tools。Necessarily to allow them to build the Internet。

 They didn't have the language needed to do it。 And so they invented their own。 And that is really。

 in a way what theyre going study in this class。 And it's impacted the Internet。 And so you know。

 when you learn about this， you'll learn how the Internet was built。

 But those principless carry over。 All of cloud computing， I would say， is now built on those。

Anytime you build a distributed application that runss at scale on the internet。

 you're going to invoke some of these principles。And so， you know。

 Ive said that it is quite a new Internet design by。What is a design5 language。

It's kind of like a pattern or a template for how you build a system。😊。

That's based on a certain set of design principles。

And these are the design principles that we're going to be talking about all semester long enough。

 not going to make sense to you today。 I don't expect it to。

I'm just listing them out for you to see we'll be going into these in great detail over the course of the。

What is what noting is that？Almost every single one of these concludes and certainly the combination of them。

Had never been done before， was a radical departure of consist at the time。

Let's let me take just one example to make that concrete。

 This notion of her best effort service model。What do I mean by that when you build a system。

 you know， and in this case， a network or the internet。

The question you have to answer is what is the service model that the network should support？

So what I mean by that， think of it almost like an API or contract。 What does an endvo get to expect。

 What does a user get to expect from。So that's what I mean by a service model that's like this contract。

If you want the designer of the Internet thinking about this question。How would you answer that。

 What would seem to you like a reasonable contract， a useful contract。

There's some pretty obvious possibilities。 One would be， you know。

 you give me the network of the data， I guarantee that I will deliver the data to the destination。

That seems like a value intuitive。Useful contract。Even better you could say， I'm going to。我的。

I'm going to guarantee that data will be delivered within some bound time， within next millisecond。😊。

It's actually more useful because you could build a business module around it where we all compete on what exit。

So get not大给拿出 머리。Or you could have a contract and says， you give me your data。

I'm going to try and deliver it， and I will confirm。

 I will give you a confirmation of whether I succeeded or whether I failed。

This might be maybe a more sensible idea of a contract in the Internet context because I said theories are common。

 So I will tell you whether I succeeded。The Internet actually did none of these。 Instead。

 the Internet service model is what we call a best effort service model。😊。

The Internet guarantees that it will try to do。You give the network data。

 It will try to hand it to the destination。 It may work。 It may not work。

If it works so it doesn't work， it's not actually going to tell you whether it' successfully delivered your data might silently drop。

It up to you都这。So it's an extremely weak contract in somes sense。

But it was also a very powerful contract because it almost it lowered the bulk on what you expect from the networks you are interconnecting。

 Imagine if we have said every network that wants to connect to the Internet has to have at least 10 gig per second has to have four liness of reliability。

 has to have， you know， at least。Fair sharing of resources to。We would have had one them。

Because it's very hard to build a network that needs all of those。

 And it would have raised the bar on every single network。 Certainly。

 it could not have started out by interconnecting networks that already exist。

So that's one example of an internet， a a design principle that emerged from the creation of the internet。

 and that now influences all of us， I think Alex posted on Ed saying that Zoom broadcasts are going to be best at。

😊，We actually to Singapore join it as because we all know what best effort。

So going back to this question of internet design paradigm。

 there these principles that now routine be adopted in modern systems。😊，Cloed computer。

 you can go through all kinds of services that have less effort and were out around trouble。

What is important to remember， though it is just one design。 This is not about jobma。

 I'm not here to indoctrinate you with the five principles over 10 principles of Internet architecture。

 and you must appreciate them and you must always apply them。That's not。

It is after just one design that people actually put together quite a long time ago。But， you know。

 it has issues。 There are certain some of these choices that in the context of the modern internet are no longer such a great。

Choice， for example， security。No way on this list， actually， is the security figure。

 If we had to design the Internet again， we know we would。Pse。Or， you know。

 that things have were just a bad idea early on or things that are now a bad idea and need to change。

 And so we by we and， both research community and industry。

 we are still revisiting and debating these big questions。

 I it's not like everyones tinkling on the sides of the industry。

We all implementing radical change on the。So for example。

 one of the things you might have heard of SN。Software defined networking。

Was this idea that came back and said， you know， decentralization has had its benefit。

Like it's made managing natural studies。So if you have to go in and program individual switches。

 you can't have higher level abstractions where you program the network and so on。So at end。

 was hugely successful。 It's also now about， you know，15 years old。And so now there's new proposals。

 Alex at Google is working on something called DSSDN， which is saying， you know。

 we lost some of the benefits of decentralization when we did SDN。Can we now not go back to the past。

 but can we learn from that and try to get the best rest and listen。

Lots of other proposals like that。 N we network function virtualization is all these acronyms。

 It was a was and kind of is a very hot topic in networking about five years ago。

 When you start outsided one in this space that we really coming at the question of， you know。

 traditionally， we assume that the Internet infrastructure is dumb。

 What I mean by typically is stateless。 There's no information about users or applications thats stored inside the network。

But there are lots of reasons， particularly if you're an IC。

 why you might want smart or intelligence in your network。One example would be you don't trust。

If you don't trust any host。Tss your own network infrastructure。 So you want to put。

Smartto inclusion detection or filtering or things like that in your network。

So NFV was a move to say how do we， revisit the architecture to allow intelligence inside the network。

And there's more a hot one today， that's the buzz whatever wear edge computer。

Like if we want to do smart calls， A VR， know we want to be really close to the user or for privacy。

 you want data to be maintained in your home or in your enterprise， in your company。

 So edge computing comes in。 So again， going back to revisiting this question of the enter and design cluster。

And so on layering， the wireless people have always been very frustrated at the principles we call layering because they say you get terrible performance。

 If you would just let me you know， violate layering， I could give you 10x wireless。

So there are all these ongoing things that we visit some of these design principless we'll be talking about。

😊，And so backing up the level， you know， the Internet poses a design challenge I think。

No other computer system。And from its creation， what we as a field and as a community learn was a new way。

 a new approach， a new paradigm for building and designing systems。

And that has shaped how we think about systems mobile。Not just the internet。

 but any complex disturbance system。And when we think about that。

 we reason about what the prioritization。What are fundamental constraints。

 What can I not change like speed of light versus things back in trade off。What are the abstractions。

 How do I decompose a problem？These are things we all do when we do system design。

 and the Internet gives us a great template for how to reason about these questions。

 because it's an incredibly hard design problem。And this is why going back to the question。😊。

Going through these kind of questions， this is a lesson in how to architect a network system。

Asking and asking these questions， this is about what we mean by architect。distributedbuted system。

 And when I talk to my colleagues of friends who are。In industry oil development jobs。

 particularly the more senior ones。 If you ask them how they spend their time， again。

 this would be know people have been in industry five plus years。

 They will tell you they spend more than 50% of their time in design discussions。In design meetings。

Arguing about exactly these kinds of questions with their views。

And it's spent a decreasing amount of time actually writing the。That implements that design。

RightSo learning how to engage or analyze or participate in the design discussion is extremely important。

And so that gets me to， you know， this last topic of architecture。

Network architecture is more about thinking rigorously than it is about doing rigorous math。

 I'm not going to teach you complex。K not from that I wouldn't know them myself。

But what we are going to do is actually obsessively think about why am I designing the system like this。

 Why is this the light design versus the other one。

 Your exams will be of the type where we give you two designs。

 and you have to understand the trade offs。You have to understand tradeoffs rather than running benchmarks because as I said on the internet。

 it's always possible to get a measurement that tells you what you want。It's much more about。

 The big picture is much harder do。And ultimately， it's far more about practicality than optimality。

 weighing all of these conflicting constraints that we have in the design。

If they do it like this can be a powerful thing， I think the history of the internet teaches us。

And so know just to wrap up this piece， what I hope CS1608 will teach you is how the internet works。

 I'm a big believer in the fact that you only really understand a high level principle if you understand how it was put into practice。

If you actually understand how things work， then you will understand why a particular design choice was important。

So you will learn about all these。Pre letter acronym photoball， DP， ViP and PNS。

But what I also more than that want you to take away from it is why these technologies work they do。

 the way they do。And through that process is really what I hope you learned from this class is how to reason through a complex medical system。

😊，So you， when you go out and you're in these design discussions， in your jobs that you will。

 because you've practiced them over here。It understanding those principles and being able to articulate them and the reason about them。

With that， let's take a。W， let's say few minutes and then we will continue with cloud。月有靓即冇事。

That's right。啊。我的。不清。是不是。Okay。He send me have connectivity working again。 Let's start again。

 class logistics。 Let me jump straight into。嗯。😮，Something had to start working。II just my name。这。

Teaching staff， see the course website for details about all of us。

 you already know me Sylvia a little bit of background on myself， I got my PhD from Berkeley many。

 many years ago， got my undergraduate degree in India and computer engineering where I was subjected to learning about transistors and circuits things that I haven't done since coming to Berkeley fortunately I worked in industry about 10 years after graduating came back to the faculty in 2011 and I've been here ever since Dedtener a startup along the way I just spent a year at Google but networking one way or the other has been my focus work pretty much from the time I joined the PhD program in Berkeley so I'm fond of networking as you can tell my teaching style I' am a social teacher have to confess I am a much better teacher and the class engages with me so you know I know we didn't do that today but in lectures going forward what I enjoy about networking and systems is this question of design and having design discussion。

So I really like it when the class interacts with me when you say I don't think that is a good design or why do you say that it's a good design that makes me much less boring I also in case you haven't realized I talk we do fast。

 the more bored you look， the faster I talk because I feel like let me put them out of their miseries so I talk faster and faster。

So one more reason to stop me and ask questions。TA staff， we are incredibly lucky this year。

 we have Sean who is a head TA， he was head TA for CS162， so many of you know him probably。😊，I。嗯。

I feel doly fortunate now Alex like whom many of you may not know。

 but he actually got his undergrad degree just a couple years ago。

 I think at Berkeley where he was TA for this class with Scott Shanker at the time so when I heard that I grabbed him as soon as I could。

😊，Project Ts we are very lucky we have silvery and Zhong they're both senior PhD students they actually ran the projects the last time I offered this class and this year we have Tenzin and Kenneth who are joining in on the projects to add more horsepower to running projects so very happy they could all be him and then on the section side in addition to Alex and Sean we have Sarah Mark and Nek they are all again graduate students with us in the networking systems research group that I co run with Scott Schger so slightly unusual maybe to have so many graduate students on TA staff but you know we haven't taught this course in two and a half years so it was actually hard to impossible to find undergrads who've taken the class and so big shout out to Sean and Kenneth for taking on a class that they haven't actually taken themselves and to all the PhD students。

That was intended as a compliment in case it came out wrong。😊，You know。

 I think it shows courage and can do attitude and also shout out to all our PhDV and graduate students who are taking time out from research to actually。

 you know help me teach this class。😊，So with that enrollment and waitlist the class size will not increase as you can tell we are already a fairly small T18。

 so waitlisted students will be let in as students drop from the class we on the coast half we do not handle the wait list so please don't send us questions about getting off of the waitlist we can't help you。

And concurrent enrollment students， you will be handled after the wait list。

 given that the wait list is 200 students almost I think the odds are low， so I'm sorry for that。

Recordings the lectures will be recorded and posted online。

 we will make every effort to release these recordings the day off by evening is a reasonable expectation。

Things happen so if that doesn't happen be patient with us once in a while sections will also be recorded we will have one section recorded offline that will be posted and I push I had deleted this we were going to make a best effort attempt to live stream on zoom this lecture the wifi here is really bad so i'm not sure what we're going to do about that。

All sections are on Monday。 this is by design it you know， hopefully you can。

Look through the lecture materials over the weekend and go in on Monday with all your questions for the Ts。

 but it also helps it kind of acts as a recap of what we did the previous week so when you come into lecture on Tuesday you have all the material ready to go。

You can go to whatever lecture you want Let us know section I mean the class workload is Ive been told this is plus S to light overload let's see how what we can do about that we have no no no I'm andking two projects one on routing one on transport design we do have selftest after class so after every class we believe a self testest I'll say a little bit more about that and then new this year we're going to try an experiment we're going have one homework assignment that's based on reading a research paper it's always struck me as a little sad that we are you are in the best research university know the top research institution for computer science in the world and you get very little exposure to research so we're going to read this one research paper that actually talks about the creation and the founding。

You knowDe principles of the internet it's a beautiful paper it's very accessible we'll read it at the end of the semester by which time you have the foundation and then we'll have a homework quiz on it okay well see out goes and then exam midterm and finals in terms of grading the bulk of your graders on the projects and the exams with 5% for the self tests and 5% for this homework。

Extensions and late policy， this is all on the website。

So I'm just going to go through it very quickly if you have reasons why you need an extension fill out an extension form Sean will post information about this。

 there are no extensions for the staff quizzes， they're already extremely generous as I'll get to in a minute。

Projects and homeworks have late assignment penalties as listed here and do note any projects turned in after December 9 will not be accepted。

Think these are fairly standard policies， but if any questions or concerns。Feel free to ask。

So Se test will be posted after each lecture it'll be available by 5 pm on the day of lecture and you have a week to fill it out if theyre actually very quick shouldn't take you more than 10 minutes honestly after class。

Your score is not important， you're not created on getting thequiz correct you're grade on participation you must try if we do things to make sure that you're not blindly filling out the form just for the sake of it that you've actually tried to answer the questions The goal is really for both you and I to understand whether you're keeping up or getting the basic concepts of the lecture it helps to steer what we emphasize。

It's 5% of your grades so it's an easy5% don't miss it you can skip up to three selftest without penalties so it's very generous in that it's an easy assignment you have a week to do it and you're not graded on correctness okay so please don't email us asking for extensions on selft because this is as easy as it gets exams are pretty standard closed book OpenC sheetet the date and time on the website we are going have alternate finals exams they will be offered in the time slots after the normal exam time slot and Sean posted about this on Ed about alternate exams you have to request it and get approval from us in order to take the alternate exam。

Any questions on alternate exams or exams？Okay lectures and participation classes will be recorded I as I mentioned do enjoy attendance and so I highly recommend it ask and answer questions when you're in the class。

 this is something I strongly believe in the only dumb question is to not ask a question that you are here to learn。

And so it would never make sense to not ask a question if it's going to help you understand question。

Yeah， I'm going to get to that in a bit， the short answer is not really， but I'll get to it in a bit。

So do come in and ask questions I am sure every one of your has experiences this where you hear someone else ask a question and you were like I was thinking of that too and I didn't want to ask so they really it always just helps everyone to ask questions and 10 years of teaching I honestly cannot think of a time when I thought wow what a dumb question the same for an answer I often hear long answers but it's not a long answer it's not nothing bad it's because that's how you understood it or there was a reasoning that made sense that led to that answer so it's useful for me to hear why you had that answer。

You can also ask very simple questions like I did not understand what you just said。

 can you repeat it， it doesn't have to be some deep question。What I do ask I hate policing students。

 you're all smart and mature otherwise you wouldn't be here。

 so if you come to lecture I ask that you engage with the class don't spend your time browsing or chatting with your friends sitting next to you if you're going to do that we're not enforcing attendance so you're welcome to just not come to class and it's a better use of your time and it's the more respectful thing to do for your fellow students。

Questions answered in real time we have a real time thread on Ed where the Ts would be monitoring and responding to questions the use of this real time thread is really to。

Quickly catch up if you missed something so it's not you know I zoned out can you explain the last 10 minutes of the lecture to me it's also wow what she said made no sense you know I didn't understand it at all then you should ask me the question it's really I missed what was just said or what was that you know can somebody I didn't catch that so it's these very quick clarifying questions so you don't fall behind。

Clas communications is a class website that has I hope all of most of the information you need use Ed for communication as far as possible。

 I am always happy to hear from any of you I don't keep up with all my email very well so if you're going to send a question send it to CS168 that goes to Sean。

 Alex and I and we will try to respond if you have you know there's clearly some deeply unusual question that has to come to only me I'm happy to receive emails。

Thosese material you know as I've tried to give you a sense throughout we still kind of figuring out as a field as a discipline how we teach system design and system architecture and it's a little bit like modularity that you all know why modulularity is important when you guide code how do you teach modulularity often by example and so that's a little bit。

The challenge we face in teaching networking， the way we try to get around it is we try to focus on these fundamental questions like fundamentally in a network you have to solve a routing problem fundamentally you have to solve reliable data transport so we will try to teach you。

You know how to ask those fundamental questions and what is the space of possible designs for those fundamental questions but at the same time we will also focus a fair bit on the current internet design and how things currently work so you will learn that there are 32 bits for an IP address and there are 16 bits for that and you know this is exactly the protocol specification for TCP we will drag you through all of those weeds I kind of think they're fun sometimes but it helps you understand the bigger picture。

What you will leave this classward because of that is a mix of the big picture。

 these overarching design principles and architectural ideas。

 as well as a lot of the details of how things work on the internet。

Fundamental questions that involve you I think I've gone through all of these so I won't touch on them again but they're questions like how do you decompose the job of the internet。

 how do you find a path from power point A to point B。

 how do you do reliable communication when your network is best effort。

 how do you how do different domains talk to each other to cooperate。

 how do you share network resources and so on these are all kind of fundamental questions when you're trying to build a communication system。

So the first half of this course is going to be these basics you know i'm going to start taking almost two weeks just to give you an overview of how the internet works so I want you to have that end to end picture in your head and then we'll start chipping away at individual pieces of it。

And amongst networking faculty and networking textbooks， even there's always a debate about。

 you know， should you go bottom up or should you go top down when you teach how the internet works。

 we're going to do it both ways actually in the overview。

 I'm going to start bottom up so you have a fairly concrete picture and then we'll go come back to it and go top down and talk about what were the goals。

 what were the principles and so on。And then we're going to talk about gouting and reliable data transfer。

 which your two projects are based on。And then the second half of the course is more advanced topic congestion control is this always fun topic that we spend a fair amount of time on it's this question of how do you share network resources because the internet is a shared infrastructure it's shared by users shared by companies shared by applications so nobody can hog the entire internet that wouldn't be fair。

 how do we actually come up with a way of dynamically sharing resources across all the entities。

And then into domain issues the protocols by which differentize these peer how does money flow corresponding to those protocols what is the role of policy and so on and then a set of newer topics these are kind of cutting edge topics even in industry today SDN software Def networking we have the good fortune that Scotch and Google was one of the early proponents of designers of SDN is here and so he's going to do a guest lecture on that we'll talk about data center networks which have some very specific characteristics that are different from the internet the wide area internet as we think of it cellular networks is a new topic this year I figured we all use cellular networks so much that it has to be a core part of our syllabus so we're going to try that this research paper I mentioned and then new this year we're going get have guest lectures from two of the leading architects of Google's global network you know they're not they're the people who actually built and who actually operate and fix the existing network they don't do it themselves but they run these large teams。

That are actually responsible for Google's network。

 so they're going to come and tell us both about what it means to be working in industry in this field as well as their experiences of what it takes to keep really the world's largest network up and running。

What you will not learn is exactly how to configure your network every time I go to dinner and somebody tells me my network is not working and you fix it。

I don't actually know how to do that I'm not sure you will learn how to either from this class you won't learn tiny details of how the Conal networking stack works you know exactly what Linux does that's sort of interesting but just not this class you will learn about kind of this big picture of how the internet works and what the fundamental design pieces are。

Make sure this is what you're looking forward if you wanted to hack the Linux kernel。

 this is not a class for you。Textbooks someone us， this is the textbook we recommend。

 as you can see it believe in the top down approach。😊，To be honest side we。

Put it out there just if you want more reading material if you want to read in greater depth depth on certain pieces。

 we don't expect you to know anything that's not covered in lecture so lectures and section are what we expect you to know but use the textbook if you're enjoying it there's no harm。

So with that for next time， I would ask if you plant a drop， please do so。

 that's the nice thing to do for your fellow students who are on the waitlist。

To check Sean's posts on Ed about alternate exams and extensions。

 discussion sections will start this coming Monday that's August 29 there is no self quiz for today's lecture obviously。

 but they will be starting next Tuesday。With that， I'm happy to take any questions。Ling once twice。

 yep。Yes， I do have office hours there actually tomorrow 9 a to 10 p。

 and I think Sean we have all the office hours posted on our website as well for all the tears。

Any other？Okay， thank you。

![](img/daae0b59001c172eb1675e7c4e16700f_2.png)