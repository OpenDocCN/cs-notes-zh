# 史蒂文斯理工学院【中英⚡计算机系统管理｜CS615 2021 System Administration】 p03 p2 Week 01, Segment 03 - SysAdmin Core Principles and Rules -BV11QQcYmEzD_p3-

Hello and welcome back to CS S 615 System Administration。This is our our third video for week one。

 and after we discussed the drop of assist system administrator in the last video segment。

 I wanted to introduce you to a few core principles that will be important for us throughout the semester。

More than just maintain computers and infrastructure components。

 system administrators control entire systems with more experience and seniority。

 they are ultimately in charge of building these systems。

 of designing the infrastructure and its components so that the job title frequently morphs into that of a systems or network architect。

So when everything is awesome， system administrators step into the role of planning。

 designing and overseeing the construction of complex systems suitable both for the immediate requirement of today。

 as well as anticipating the needs of the organization down the road。We become super builds。

But in order to accomplish this， we need to build our infrastructure on two basic principles。

Scalability。And security。Neither of these can be added to a system after it has been built。

 Try to apply security after the system interfaces have been defined yields restrictions。

 limitations。Trying to make a system with inherent limitations perform under as circumstances it was not designed for yields。

 hacks and workarounds， and the end result frequently resembles a fragile house of cards more than a solid。

 reliable structure。But there is a third core principle that is necessary。

 and that is what actually enable these other two principles。Simplicity。

Simplicity is simultaneously obvious， and counterintuitive。

Simplicity underlies both scalability and security since reduced complexity implies better defined interfaces。

 minimized ambiguity and communications or data handling and increased flexibility。

As with the other two core aspects， simplicity cannot be added after the fact。

 It must be inherent in the architecture。 Simplic is the enabler of both scalability and security。

Let us look more closely at each of these three core principles。 Let's begin with scalability。

 Scalability is a buzzword often thrown around these days， asking。

 but does it scale is an easy way to seem smart in meetings。

 But let's consider what scalability really means。Suppose you have a website and it becomes really popular。

 Say it was slash do it。 Oh wait， You guys don't know what slash dot is。

 Let's say it was published on the Hecker New frontron page， or a popular Reddit。

You poorlyy web servers were not designed for the sudden increase in traffic。In other words。

 you're getting a system overload。So now what？Whenever you have a resource issue like this。

 there's only so many options。On the one hand， you can scale vertically。

 That is you get a bigger Bier server to handle the increased load。Scaling vertically is great。

 It's usually quite easy to do， as you don't have to change much。 You buy the big as horse here。

 off you go。So you're throwing money at the problem in a way。

 which is a great way of solving many issues if you have money。Also， note， of course。

 that this only buys you time。At some point， you may have even too much of a load for even this monster to carry。

So your other option。Is to scale horizontally。When you scale horizontally。

 you get more of the same and try to distribute the load。

Scaling horizontally may seem a bit better here， since it allows you to continue taking on additional load。

 You just need to keep on adding horses， I mean， in service。

But scaling horizontally isn't quite as easy as scaling vertically。 When you add more servers。

 you then need to distribute the load。 So you add， say， a load balancer， which you know。

 you have to health check and maintain。That is， you're adding complexity。Sorry， no free lunch。

But of course you can also combine the two approaches。

 get more beef your hardware and distribute across them。And oftentimes。

 that's what people mean when they say scalability。

But there's one aspect that is often overlooked once you've scaled up either horizontally or vertically or both。

 you are now running with higher costs。 There is， for true scalability。

 you also want to be able to scale down。If your traffic does not remain the same。

 then you're wasting money。 having a fully pimp out data centre with racks and racks of redundantly load balanced servers is rather silly。

 If you only mix out one easilyasly CPU。As such， our definition of scalability will lean towards the overall flexible nature of scalable systems。

Its ability to adapt to changing requirements at runtime。

One term you'll frequently hear in this context， especially when talking about cloud computing is elasticity。

 which perhaps more apt describes this feature。So whether by vertical or horizontal means a scalable。

 a flexible elastic system is one that readily adapts to changing demand。

 We'll try to keep this in mind throughout the semester。

 but we consider requirements that may spike hundredfold and evaporate again。But for now。

 let's move on to security。And yes， this， by the way。

 is a most accurate depiction of what counts as security in many cases。Al too frequently。

 the software information technology industry treats system security as an afterthought as something that can be added to the final product once it has met all the other functional requirements。

 After the user interface has been determined that after all code has been written。

It is then not surprising that oftentimes people view security and usability as being directly and inversely related。



![](img/25108901f7f292dd10f0b8ee8e4e5261_1.png)

This， however， suggests that the only way to reduce risks is to take away at the risk functionality。

 but any time you do that， the user will work around your restrictions or stop using your product altogether。

Instead， security needs to be built into the system from the design phases on。That is。

 rather than starting out with a solution that provides the desired functionality and then attempt to figure out how to get it to a secure state。

 We should instead begin with a secure， Obit restricted state and then slowly add functionality without compromising safety until the desired capabilities are available。

That is， we need to view security as an enabling factor present at the design's conception when building our minimum viable product。

And this class will often discuss security failures or problems in the products or systems we encounter。

 and quite frequently， we will be able to point to the discrepancy and product design objectives that lead to such a problem。

As such， we'll cover peripherally， at least throughout almost every week。

 as well as in a summarizing fashion towards the end of the semester。

 many aspects of security that relate directly to the computer human systems we care about。

These will include the broad area of cryptography with its ability to aid in the areas of confidentiality。

 integrity and authenticity。Physical security， service availability， service design。

 social engineering， and often generic trust。All of these should help us approach each area and topic we discuss from both the user's point of view。

 asking an understanding what the user actually wants when they use our systems。

 as well as the system or product centric point of view。More often than not。

 where we find that these two intersect with one another more than with the adversarial perspective。

Okay， now for both of these two core properties， scalability and security。

 we have noted that neither can be added later after the fact。



![](img/25108901f7f292dd10f0b8ee8e4e5261_3.png)

To go back to an earlier example Fo our data centres。

 you can't take a mess like this and then slap on some scalability。

Both scalability and security are things that you have to include in your system design right from the beginning。

When that is done， the practical application of these principles yields a reduction of interfaces。

 end points， use cases and overall variances。At this time。

 it's also worth noting the difference between complicated。



![](img/25108901f7f292dd10f0b8ee8e4e5261_5.png)

As illustrated here on the left。And complex。A complex system may be well organized and exhibit a clearological structure。

 yet requires subtle intricate connections or components。

Complicated systems on the other hand are irregular， unpredictable， or difficult to follow。

Scalable and secure systems are less complex and much， much less complicated。

As system administrators， we like kiss。Kiss is well remarkable。

Not for their ridiculous outfit or their pyrotechnics or their plateau shoes。 In fact。

 when they're talking about the band and all， but a core system principle abbreviated S K。Keep it。

 simple， stupid。That is， we are looking to reduce complexity。 complexityplexity is the enemy。

 We will look to resist the temptation to build features we do not need and instead build tools that can be combined。

In that way， we will look to the ex philosophy， which includes the critical directive to build simple tools to do one thing and do it well。

That is， we will create small components that， like Lego blocks， can be combined。

Small little tools that follow the same interfaces and that fit well together。And with such small。

 such simple building blocks。

![](img/25108901f7f292dd10f0b8ee8e4e5261_7.png)

You can build intricate， large and， yes， complex systems。

The Lego Star Wars Millennium Falcon is one of their largest sets。 It consists of over 7500 pieces。

 and so certainly is far from simple。But I think this illustrates a well what we're looking for。

 Small， simple building blocks that can be combined to create complex but well structured systems。

In one part of system administration， well， and software engineering programming and the various other related and overlapping aspects and disciplines consists of the design and implementation of such complex systems that。

 because we keep simplicity in mind in the construction and use of the building blocks will be more fall tolerant。

 more performant， more flexible。And so is simplicity。

 the third core property of exceptional system design is really the enabler of both scalability and security。

 And that's why will I kiss。Now， this concept of simplicity can even be translated beyond just the design or the implementation of systems。

 but also to our approach of problem solving。One way to solve complex and even complicated problems is the application of Oham's razor。

Arrkham's razor has seen many different formulations。

 but the most common one is that for a given problem。

 the simplest explanation is usually the correct one。

This is something that will be useful for you to recall when youre trying to troubleshoot complex systems。

 which tend to fail in complex ways， but often due to simple causes。

A similar golden rule to internalize is the second law of thermodynamics。

 which stipulates that the entropy of an enclosed system increases with time。

Apply to system administration， This tells us that things will move towards greater disorder。

 The more users you have， the more traffic you have， the more systems you have。

 all of these will contribute to more software with more bugs connecting to more other systems and so on and so on。

Systems left running for a long time eventually run out of memory or disk space as they may trigger edge conditions leading to a memory leak。

 Hardware will inevitably fail。Keeping this in mind allows us to anticipate and prepare for the inevitable。

Next in our series of Sis Edmund Law is Handlin's razor。Heandlin's razor is， in a way。

 a variation of Aham's razor。Hanan's rar states that you should never attribute to malice。

 that which is adequately explained by stupidity。It's easy to jump to conclusions and fear a nation state actor has infiltrated your network and planted the back door。

 which changed the permissions on Dev Nolin， which you have stumbled upon my accident。

Or a user may have accidentally done so。Which explanation is simpler and thus。

 according to Aham's razor more likely。Hlon's raor。

 he deserves being called out because especially when you focus on security。

 As system administrators must do as part of their job。 It's easy to see malicious actors everywhere。

But it's worth remembering that any time you prevent accidental failure。

 you also help mitigate the risk of intentional abuse of such a failure mode。

 So Hanlon's razr can help you in grant you， too。Next up， Parreto's principle。

 This principle states that in most cases， roughly 80% of the consequences derive from 20% of the causes and was originally applied to economics。

 But it turns out it applies nearly universally。I'm sure you have noticed that when you're writing a program。

 the general functionality， all the big parts are easy。

 you get about 80% done with a program fairly quickly and then spend the majority of the total time on the last 20% where you're debugging tricky issues and fine tune the functionality。

So 80% of your time is spent on 20% of the functionality and vice versa。

This rule of thumb can be surprisingly useful in estimating software development time and estimating how customers will use available disk space。

 but network filters will catch or prevent what traffic and so on and so on。

The 8020 rule can even be applied recursively， and you can again estimate what resources you need to spend on the vital few and what on the inevitable long tail。

Then， there is carp。Wait， what， That's not even a carb。 That's a sturgeon。All right， Sturgeon's law。

This is an adage named of thetheodo Sturgeon， the science fiction writer who famously equipped that 90% of everything is carp。

 crap，90% of everything is crap。He said this after it was noted that 90 per cent of science fiction literature is crut。

 but he observed that's only because 90 per cent of everything is crut。That is。

 most everything is not outstanding。 system administrators will quickly find out that this is painfully accurate as you go through software。

 both open source and provided by commercial vendors。It's not actually as nihistic as it sounds。

 but a useful reminder to help you set expectations。Similarly。

 we're all rather familiar with Nrfephy's law， right。Anything that can go wrong will go wrong。

 or more precisely， anything that can happen will。Like sturgeon's law， it's not quite so pessimistic。

 but good to keep in mind， especially when it comes to software。 And in that field。

 even more so when were talking about software systems at internet scale。

 we can't excuse not preparing for something by saying， well。

 what are the odds of that happening or who would ever enter that into this field here。

If it can happen， it will。 Hardware drives will fail。

 A user will enter an invalid number into a field， and that a connection will drop and you doubly redundant power supplies will both fade at the same time。

 eventually。Our job then is to prepare for these eventualities to anticipate the possible and build robust systems to function under those circumstances。

Finally， as we're talking about possible things happening and then logically of impossible things not happening。

 we end up in the realm of philosophy to help us troubleshoot our systems。

 causality for every effect， there must be a cause。 Things don't just happen。

 Systems don't just break。 There's a reason for why your software exploded for why the load balances are shifted traffic away from a healthy origin Vi for why your database is currently locked And for why you're out on traffic footage at in again。

Sometimes the causes for these effects are hard to find， but they're there。

The various rules and laws I just mentioned will hopefully help you cut out the explanations and guide you in finding the true cause。

All it takes is perseverance and dedication to finding the cause of the problem。Okay。

 so those were just some of every Suman's favorite laws。

 you'll find that we will reference them throughout the semester。

 and I bet you will years from now and your jobs run into situations where you will remember them。

And， of course， there are many more similar laws and observations， and we will， without a doubt。

 sprinkle some of them in each week。 But for to day， I think we've had enough。

So let's take a look at what happens next。One last topic for this week's introduction is Uniix's history。

 as we will be using Uniix systems exclusively in its class。

 and since system administration is in so many ways tightly coupled with Uniix systems and their development and evolution。

 it is important to understand the history of this operating system。For this。

 you should watch the video segment I recorded last semester for my other class。

 C 631 advanced programming in the UniX environment linked here。

That video covers all the critical aspects of Uni's history and explain some of the core features。

Although targeted towards programmers， Uni system administrators will be able to benefit as well and translate the lessons。

Throughout the semester you will see us going back to some aspects of this video。

 so please do not consider this an optional part， but a mandatory video in the series。After that。

 I'll explain the various homework assignments as well as how we set up good for using in this class。

 but that pretty much concludes week1。 congratulations。In the next week。

 we'll be talking about storage models and disks。 so please make sure to read through the reading materials posted on the course website and to submit the course questionnaire prior to a second interactive class。

The Quez website also includes a number of ungraded excs for each class and I strongly recommend that you go through those as you prepare for the next video lecture。

In addition， here are a few ways for you to review the topics we've covered in this week。

Try to find out a bit about how certain companies manage their infrastructure。

 You should find that many companies have public blogs where they op post a fair bit about the infrastructure or software products they use。

 This can be quite interesting and give you a good idea of what scalability challenges they may face。

Trying to find out what schools exist that grant a degree in system administration and what their curriculum looks like。

 correlate。To what we'll be covering in this class。Finally。

 as we're getting ready for some practical work in the UniX environment。

 maybe take a look at how you currently use the system。 What tools do you use most commonly。

 how do they fare when analyze for their complexity and interfaces。Well。

 I think all that should keep you busy for a while。Remember。

 it's up to you what you get out of this class。 and the more effort you put in to complete these exercises。

 even though they are not graded， the more you will hopefully learn。With that in mind。

 until next time。 and thanks for watching。

![](img/25108901f7f292dd10f0b8ee8e4e5261_9.png)

Js。