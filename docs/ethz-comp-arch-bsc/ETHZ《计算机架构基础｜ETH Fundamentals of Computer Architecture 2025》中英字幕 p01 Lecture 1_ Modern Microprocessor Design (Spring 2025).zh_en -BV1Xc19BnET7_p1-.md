# ETHZ《计算机架构基础｜ETH Fundamentals of Computer Architecture 2025》中英字幕 p01 Lecture 1_ Modern Microprocessor Design (Spring 2025).zh_en -BV1Xc19BnET7_p1-

![](img/c38e05d34c60e66bef8947f7d5549fb8_0.png)

そそで。さけ。啊，不了。是的。嗯啊。So不是 I。With the。Is it good， okay。啊睡一觉。So that's also working。yes多。No no。道。Yes。啊。

我想瞓享件思。No， you're not sharing it。Sure to go back。十数は。阿宝咧。这个すね嗯。一播啱洲盒子。で。Okay。又出显示。哦。Is it online？

Okay， it's all good clicker。Looks like it's working。H。Usually it doesn't work。Okay。应该个。把。今と。Oh。啊。

咁大 school。Thats like cool。Yes。We still have three minutes， so I'm waiting。

You guys can talk don't worry。We're supposed to start at 1415， right， Okay。

I hope you already mail about this didn right it so how is this is this course like a requirement for the odd course I'll discuss that like sure you can you can bump up the email if I don't discuss。

Or if you still have questions。Yeah'。Yes。即食。感も感や人。Look。不错了。不者说。This is a function。OhYeah。し？有不时候风兵去。

Business decision。This。对。最しま。你啊我发。こしな。就我都の。大这个。figure over 30 years。你。と天。Yes。Yeah， it's a bit tiy。

 let's see。这个确。不。では。There's not。我都食吧。对这。这。嗯。🎼，🎼No。Okay。

 I think we can get started we come to our cozy room。fundamentals of computer architecture。

 I hope you're here for this。😊，There are more people registered， but maybe they're watching online。

 which is okay， actually， as we mentioned it over email。

So today we have a lot of material to cover but let's see how far we can go this is a new course we're offering i'm going to place it with perspective of other courses that we're offering and other course at EthH soon。

 but before I'd like to introduce，😊，Myself and the teaching team， et cea。HowBefore I start。

 how many people here are EE students， EE students， how are UC？How many people are？See yes。

How many people don't belong to any of those categories。😊，You're in different departments。

Which is perfectly fine as long as you were taken the computer engineering course。Okay。Okay。

 so let me start so I'm a professor at ETH Zuric in the EE department， I'm also affiliated with CS。

 I've been here for about nine years before that I was at Carnegie Mellon at both EC and CS before that I started the Computer architecture Research group at Microsoft Research which is quite interesting and some of that experience influenced how we actually covered this course of course or other courses too I do research in computer architecture as at CO down here and I worked at Google。

 we amware Microsoft as I said Intel AmD and I spent a sabbaticttic at Stanford recently。

And before all of that， well， my up doinguring all of that also sometimes I got my PhD in computer engineering from UT Austin a while back。

And I think before that I was kind of in your shoes。

 a bachelor student in computer engineering and psychology at University of Michigan。

 so that's kind of a summary of my academic career。

 let's say you can find more information about me online and you can email me anytime。😊。

My email tends to be very， very crowded， so if you don't get a response which some of you have experienced。

 don't despair， feel free to send again or talk to me during course。

So I do research and teaching and computer architecture， which is the focus of this course。

 computing systems， hardware security， bioinformatics， genome analysis。

 and these are some research areas which some of which we will cover in this course but we will not go into everything clearly because it's a limited timeframe my coin instructor is sitting in the back over here Muhammad Sader Saro Sadati he's a senior research and lecturer in my group。

 he is leading this course also and he got his degrees at Sheriff University of Technology which is the。

One of the top institutions in Iran。And you can talk to him and email him at any time he has。

Research and teaching interests that are quite varied and do you want to add anything Muhammed okay he'll be giving some of the lectures and there will be some other lectures also that might be happening depending on the material and travel schedules etc ceter from some of safari students etc cetera we might have some we might have some actually guest lectures to let's see。

😊，Any questions， does it all sound good so far？Okay。

This is the research group that organizes this course， you may see some of them here。

 but not today because we wanted to keep the seats available for people， yeah it's a co room。😊。

I I'm not sweating yet let's see once I start sweating it's going to be time to change the room maybe you can learn more about our research online I'm going to go through these relatively quickly as I said we do research in the areas that I mentioned then we have a lot of material online talking about our research and I'm proud of the students that we have in the group and also that I've graduated you can find more about them if you're interested。

😊，There are a bunch of interviews if you want to learn more about future of computing from my perspective。

 you'll see some of it today and later but there's more okay there' is a lot of material we put out that I'm not going to talk about right now as I said we do research and enabling fundamentally better computers and today computing is very interesting because we have a lot of heterogeneity a lot of different types of devices that can process data there used to be a time and I was doing my bachelor's for example or even PhD CPUUs were the dominant type of compute engines today that's no longer the case in fact one could argue that GPs are not as important although I would challenge that as we will see therere clearly GPUs GPUs were just starting while I was a bachelor's student and while I was doing my PhD they weren't popular yet today GPUs are a fundamental part of the computing landscape because of machine learning and other workloads that actually are happy with GPUs let's say so we're going to cover see both CPUs and GPUs today we're going to start with。

Some basics that you hopefully have I'm going to ask you questions related to that also。

 but also there are other accelerators people are actually developing accelerators that are quite interesting which we will cover some of them some of the principles of there some of them are single instruction multiple data accelerators。

 some of them are systolic array based accelerators so there's a lot of heterogeneity and there's also very specialized processing that's happening for machine learning。

 vision， media processing， compression， decompress etc ceter。

 so it's a quite exciting time to study computer architecture I think because there's this proliferation of types of computation types of computing is that are happening。

😊，And there's also a lot of innovation on the memory side as well。

 traditionally processing and memory have been kind of decoupled from each other and there's a dichotomy between processing and memory。

 but people are trying to push more processing to the memory side to the storage side so that we can reduce the impact of data movement on performance and energy and this already happening in industry well actually have some lectures related to that in the later part of the course。

Okay， we do research in these areas so I'm quite excited about it as you can see I kind of went longer than expected。

 but you're going to see this kind of slide later on。😊，Okay。

 so these are some of the research topics that we look at which some of which you will see in this course。

 but this is not a we'll see a lot of basics in this course， as you will see。

 we look a lot into robust， safe， reliable and secure architectures。

 energy efficiency is very important because energy efficiency in today's world is really performance if you make a computer more efficient。

 consume less energy you can use more computers。That's one example right or you can parallelze the program better across more computers and we're looking a lot of the memorycentric architectures low latency architectures。

 predictable architectures are important I'm giving you a lot of keywords but。

A lot of these have a lot of depth inite clearly and clearly I cannot cover everything in one slide。

 but think of this as the breadth of research that's going on in computer architecture also there's very interesting direction that's happening today which is using machine learning techniques or AI techniques to design better architectures。

😊，Either to ease the design of the architectures or to make the architectures much more capable than what a human can do and we're going to maybe see some of these later on。

😡，And of course， there is the flip side of it， which is really designing architectures for better machine learning。

 better AI， better genomics， medicine and health。Okay。

So this is the transformation arch we're going to talk a little bit more about that this course is kind of situated here which is the hardware software interface ISA Inions to architecture。

 people are hopefully familiar with ISA right okay that's great computer engineering covers that today we're going to cover mostly what computer engineering covered maybe in a different way but today is going to be kind of basics hopefully you for you but feel free to ask questions because I will probably covered in a different way and micro architectureitecture in this course we're going to cover a lot of micro architectureitect。

 but we're going to talk a lot about software hardware interface also but we're also going to take at some point a much larger view which is in my opinion where things are going both in research and industry which is really co-designing across the stack so if you want to really achieve the highest efficiency and performance and robustness and security。

 you're really want to optimize across the stack as opposed to optimizing individual pieces。😊。

And this is already happening， for example if people are designing machine learning systems right。

 they're really optimizing the algorithm and hardware together。

 we'll talk about that in systolic arrays， for example， when we go to that。😊。

And also the larger scale systems like that people are also thinking about devices designing devices that can do better machine learning these could be for example。

 devices that can do analog computation or matrix vector multiplication in the analog domain when we talk about processing in memory we'll also talk about that so that's very interesting I think today。

😡，Okay， so I already said a lot of this， think I think if you want to achieve the highest efficiency performance and robustness。

 we probably need to take the expanded view of computer architecture and co designign across the hierarchy and specialize as much as possible within the design goals that you have。

😊，Is this interesting？Okay， great。Yeah， I mean we're going to see some examples of this。

 but will we will as I said， there are a lot of basics that we will cover in this course。

 that's why it's called fundamentalals of computer architecture。

 but I'm going to inject some of the examples of the later on today for example。

 if hopefully we' get to it we'll talk about data dependence handling in processors and when you do data dependence handling you can do the data dependence handling in software or hardware if the compiler does a data dependence handling it has to know the underlying microarchitecture of the processor so they can decide which instruction comes after which instruction。

So that's an example of cross layer design at a limited perspective。

 which is compiler microarchitecture co design。You can also do purely in hardware。

 which we will see in later lectures out of order execution， for example。

 it does data depends handling detection， et cetera， purely in hardware。And that's another approach。

 that's a more micro architectitectural approach。😡。

But people have proposed many different ways of doing this across the stack and which is quite exciting also。

 but we may not be able to cover all of the ways just to keep that just you keep that in mind。😡，Okay。

 so I'm quite a believer in teaching and research being two sides of the same coin so I actually inject a lot of research topics and ideas into even the most fundamental courses。

 so don't be surprised by that because in the end I think these two things drive each other if you do research you discover something and you educate the community and at some point it becomes teaching。

Meaning everybody knows about it。😡，Then essentially if you teach all of these concepts research becomes much better also so okay。

 so our courses I'm going to get to you can access this course as well as other courses online。

 I think there are links in all of these slides。Let's talk about some logistics。

 any questions so far？

![](img/c38e05d34c60e66bef8947f7d5549fb8_2.png)

Okay， great。So basically we will try to study how something like this works as much as we can building upon your previous knowledge on computer engineering hopefully will'll cover essentially compute parts。

 memory parts as well as storage parts so I'd like to take a broad view of this lecture but this does also mean that we cannot go into a whole lot of depth in everything and if you want to go to depth you should probably take the next course which is the advanced it's called computer architecture but it's a more advanced master's level computer architecture course or do a research in the area。

😊。

![](img/c38e05d34c60e66bef8947f7d5549fb8_4.png)

Let me put this course in perspective so why are we offering a new course it's actually a lot of work on us to do more teaching but I think this is kind of filling a gap so we have this digital design and computer architecture course which is offered every spring it's a bachelor's first yearear course but it's mostly for computer science students it's required it's a required course for computer science students。

It's a course that's broader than FoOCA， which is discourse， I would say it's more credits also。

 but there will be some overlapping topics。😡，In fact， there' will be quite substantial lower lab。

 but FOA will also go into a little bit more research topics than DDCA does。

We offer computer architecture every fall， this is master level master's level as I said。

 usually a mix of CS and EC students take it， this is more advanced topics than FoOCA so if you take FOCA and if you take computer architecture that's okay。

 I think。😊，Or if you take DDCA， if you've taken DDCA， probably none of you have taken DDCA here。

 right？Yeah， if you're taking DDCA， I wouldn't recommend taking FoOA this course。

 I would recommend taking computer architecture after that。😊，We also offer an orthogonal course。

 which is a seminar course in computer architecture it's offered every fall and spring currently。

 this is mostly bachelor students but sometimes masters and even PhD students take it again it's a mix of CSNEC。

And this is also good to take after DDCA or FOCA or even computer engineering， actually。

Okay so what's missing here I guess well there's also computer engineering which is offered by Kave Rozavi every spring this a actuallylor second year course EC students and's a prerequisite I hope everyone has taken it okay that's good you enjoyed it I hope otherwise you probably wouldn't be here that's my guess but this covers some OS and basic computer architecture concepts so basically what was missing is a course for I call it EC but it's really EE I guess I'm used to the CMU terminology electrical and computer engineering but electrical engineering is also fine essentially what was missing was some course that kind of bridges the gap between computer engineering and computer architecture。

😊，A master's level course， and this focusA is really bridging that gap from my perspective。

Basically we will cover computer architecture concepts if people have taken DDCA。

 I don't think there's any need to take forA there with a substantial overlap。

 so we'll have subset of DDCA plus some advanced topics as I said and we'll have hands on labs。

Does that sound good does it answer all the questions related to this topic yes， please。

I'm in the monsters， and I don't have toco or anything else。 And I can in。For my master。Okay。

 maybe this is a special case we can discuss over the break yes， as a master's student。

 I think you should be able to have some flexibility， but again。

 this is every individual case is different。😊，O。Any other questions？Okay， good。So what is our goal。

 essentially it's similar to a lot of our courses， we'll cover a lot of basics。

 we'll cover a lot of principles， I actually think about principal design a lot and we'll cover some precedents like what people have done in the past。

😊，Again， there's a lot of words over here you can listen to me instead of reading the slides。

 etc cetera， you can always read the slides later， basically my goal is to build an understanding of how a modern computer system works underneath again building on computer engineering。

😡，Look at hardware software interfaces of modern computing platforms like GPUs， CPUs。

 systolic arrays， processing in memory， etc。And give you the ability or the tools to evaluate trade offs and different designs and ideas。

And we're going to have labs to implement and simulate various components。

There are going to be simulation based labs， mostly we'll try to have some handson FPGs but let's see if we can scale up the infrastructure to that level and hopefully through that you'll learn to systematically debug increasing the complex systems。

And people do simulation before they design things actually in industry。

 if you go and design every idea that you have， then you'll be in trouble because you'll never be able to explore。

😊，Okay and hopefully all of this will enable you to design things better， evaluate tradeoffs better。

 but also develop novel and out of the box designs because in the end those are the things that advance the state of the art and that's what people are trying to do I think my deeps example is one example that I like because those guys went and really understood how to optimize things in hardware。

😊，Even though a lot of the concepts they used were known concepts， let's say。Okay。

So hopefully by the end of taking this course， you'll be able to do better than deep seek。Oh。

Okay so these are the course components lectures you're here readings。

 we're going to assign readings we'll have optional homeworks I'll talk a little bit about labs and exam because there labs is important I think exam is test of understanding or one sort of test of understanding I'm not a huge fan of exams in the end but。

😊，The bachelor's level will have Tt。And there are some extra credit assignments also。

My advice is don't focus too much on the exam since it's an optional course hopefully you're not focusing too much on the exam。

 but I understand the focus also just focus on learning and scholarship but understanding。😊。

basically。Yeah， I already said this I would suggest reinforcing problem solving skills with homeworks do not worry about the exam while listening to the lectures。

 I think it's good to。😊，Understand things here and to study for the exam。

 you can actually do the homeworks， maybe go over the concepts and the lectures， et。

Does that make sense？Yeah。Okay， and we will release a lot of material to help you with the exam at some point。

 it's not going to happen right now。😊，I think the exam is in August or sorry， sometimes yes。

It's also another unfortunate thing you'll have the classes will end and you'll have two months of break。

Anyway。Okay， that we cannot change so I think my summary。

 this is the way I view things in general also focusing on learning on scholarship is good where learning is for life exams only once。

😊，You'll forget about the exam 20 years down the road， but maybe you will not forget。

 but forget about how a systolic area works and may inspire you to do something completely different。

 right？😊，Okay。So that's what I mean by over here， I think most importantly perhaps trade off analysis and critical thinking and decision making is very important for me if you can get those。

 that's great because the concepts may also disappear。😊，from your memory。

 but the ability to do trade off analysis， upsides， downsides， critical thinking， about concepts。

 hopefully those are things that will not disappear that easily。Okay。

 and also we have a lot of flexibility， I think， that we provide to students like you don't have to attend the classes here。

 you can be online， so choose what works for you， you don't have to be here， but if you're here。

 maybe you get a different kind of。Discussion。It's harder which is harder to get on Zoom， I believe。

Any questions？Yes是。You mentioned that there's like a bonus grade complete actually credit signs。

 Is that the oral exam that we saw on the。系死。like I mentioned like 30 or5% oralOh， okay， is it oral？

I don't remember oral but we should check if it's there， but the exam is going to be written。

 but then extra credits is going to be totally different so maybe for example we'll assign a paper to review and we'd like to get your critical analysis of it and you may get one point let's say for the entire course I'd like to make this course a learning experience for you as opposed to an experience where you focus on the exam。

Okay。Okay， why study computer architecture， so what is computer architecture probably you've seen this before in computer engineering。

 is it correct？😊，Or something like this at least this is my way of seeing computer architecture it's really the science and art of designing。

 selecting and interconnecting hardware components and designing the hardware software interface to create a computing system that meets functional performance energy consumption cost and other specific goals this is the limited definition and i'll keep it at this but if you broaden it you can actually add the software stack and programming language etc ceter but that's quite broad。

😊，Have you seen this before okay that's good yeah and I called both science and art as you can see well you can add engineering also of course these are engineering and science are debatable in some cases。

 but art is also here because you really need to make some design decisions without knowing a lot of things you cannot model everything in the world right for example。

 this thing is quite successful not necessarily because they predicted what kind of workloads were there they had their judgment called also。

😊，Okay。So why computer architecture， we'd like to enable better systems。

 our systems are unfortunately still not good as we will take a critical analysis of it。

 we' going to make them faster， cheaper， smaller， more reliable。😊。

By exploiting advanced and changes in underlying circuits as well as looking at workloads。

 we'd like to enable new applications in a much better way and clearly we're seeing that a lot these days right selfdiv cars personalized genomics is an area that I quite interested in like lifelike 3D visualization。

😊，It's becoming much better right now but 20 years ago it was very different machine learning large language models et ceter。

 enabling better solutions to problems is also important again I will not read or discuss everything in the slide but you can go over these slides this is overview and I think understanding why computers work the way we do is really also important。

😊，Because all of these are interesting for sure and they advance。

 but sometimes if you don't understand how computers work。

 you may not be able to optimize even existing systems， right？

And that's why I'll bring back the deepsek example。

 these guys are actually really figured out how to they really understood why computers work the way they do and they really optimize things better。

Okay， today is a very exciting time， I already talked about this so I'll go through this relatively quickly。

 but basically there are many different potential systems possible and there are many different types of computing and memory and stored units that are out there today the domain of computing is very heterogeneous。

😡，Which was not the case， again， 25 years ago， 20 years ago， etc cetera。

And there are many difficult problems that happen because of this as well as that lead to this。

 clearly data intensive applications， power constraints。

 the reason we have accelerators are very specializeds power constraints mainly complexity of design。

 that's why we have heterogeneity as opposed to having a single processor that's extremely complex difficulties in technology scaling。

 we will see some of these memory Balnick， that's going to be important to look at reliability problems。

 program B， security and privacy issues。😊，These are all different aspects also of computer architecture。

 as you can see， probably I've forgotten something too。😊。

Okay and there's no clear definitive answers to these problems， which enables innovation essentially。

 if you actually have a good idea， good solution that solves a problem in the space。

 you can actually have your potential niche market and maybe that market will grow。😡。

That's kind of what happened with GPs， right， there was a very niche market for graphics。

 but over time。Its parallel processinging power was useful for different applications that could actually take advantage of it。

Okay， as I said computing landscape is very different from 10 to 20 years ago。

 both application and technology demand new architectures and every component and its interface as well as entire system designs are being reexamined today I've shown you this picture before。

😊。

![](img/c38e05d34c60e66bef8947f7d5549fb8_6.png)

This an example system in your pocket， for example。

 it looks very different from a system 20 years ago。

Inside this or there are a lot of accelerators and this is actually not a single chip it's a chipt right there is a high bandwidth with interconnect between these two chips。

 let's say。😊。

![](img/c38e05d34c60e66bef8947f7d5549fb8_8.png)

Okay， I think that is an example of system that takes advantage of that expanded view actually。

 there's a lot of cost the stack optimization that happens over here。

 which we may get into some time。😊，呃。Before I get into it。

 I think there are a lot of opportunity so we saw this picture of problems and electrons at the bottom right。

 you can think of it at the top and the bottom， I think there is a lot of opportunity at the bottom today。

 meaning we need to examine new technologies， new materials to make computing much more efficient。

Quantum computing is one example， but it's not the only example I think I think we really want to look at new materials that are much more efficient going into the future and this is actually there's this famous saying there's plenty of room at the bottom。

 which is from Richard Feynman who was a famous American physicist and he basically imagined that you could directly manipulate individual atoms to do things for you。

😊，And again I will not go into a our detail over here you can read more about it。

 but one of the things that you could do this way is much denser computer circuitry and you actually imagine swallowing the doctor which is actually designing robots nanoscale robots that can actually do things in your body so I think this is actually good to think the reason I'm talking about this is a lot of things that we take granted today are actually enabled by。

😊，These is very， very low level。What is called the bottom right advances in electronics and devices。

 essentially， so it's good to think about that。😊，And of course。

 all of those are enabled by exploiting them in a micro architectureitecture or architecture that can be programmeammble at the top。

 so the top is also important。😡，Butottom is not the only thing if you just come up with some fancy device at the bottom and if you don't connect it to the top your device is useless essentially right and this is I think a challenge a huge challenge that people are having with quantum today there are a lot of challenges in quantum。

😊，A lot of them are technology challenges， like how do you make it cost efficient， et cea。

 but one of the huge challenges is how do you really exploit it at the algorithms and is the exploitation that you do at a very general purpose level with a lot of algorithms。

呃。Going to be successful， meaning is it going to be better than existing systems？

So top is extremely important also and there is another paper that talks about top。

 especially with the lower level not scaling very well innovations and algorithms。

 architectures and software are going to be more important so as I said I think these folks actually argue what I just said I think in the end we should really consider both there's plenty of room both at the top and the bottom。

😊，But much more so when you communicate well between and optimize across the top and the bottom and the end。

😡，And you will see some examples of this today and later。

 so that's why we take this expanded view that I mentioned multiple times now。Any questions？Okay。

 so let me talk about coursing for a little bit more。

 but we're not going to spend a lot of time over here I've already introduced。😡，诶。Instructors。

 I should introduce the head assistant over here， Constantina。

 he's also a senior lecturer in our group。And she's going to be coordinating the course as well。

If you want to add anything， Cononssantina Consantta received our PhD from NTUA。

 I guess a top school in Greece。And then we have a bunch of assistants and guest lecturers who are actually part of our group research。

 both researchers as well as PhD students。I don't know who's here， let me see。Constantinos escaped。

He was the person who set up all of this， but he escaped， I see Susanna and Jun in the back。

And that's all because we told people not to come so that you can have seats over here。

 they might be online， okay。😊，So if you need help there's Moodle。

 you can always email us but Moodle is preferred for especially technical questions。

 but if you have some individual question related to your course attendance， etc ceter。

 or how you're doing in the course you should email us we have off so please come to them you probably have seen the website your website there's a lot of information that we will add over here and we will send email as well。

😊，I don't want to go over this， I think， but maybe what I will say over here is definitely attend the lab sessions because info about each lab and its evaluation will be provided in the lab sessions。

We intend to have four labs， let's see， and labs will start on March 6th， tentatively。

 anything else you want to add over here。Okay， good。Final exam。

 so it's a written exam we will talk more about that later on。

 but as I said optional homeworks could be useful to study for this。😊。

I think this is a simple way of the great evaluation， but again， as I said， don't focus on the great。

😊，Focus on learning。Okay。不。Okay， now I'm done with the introductory material， any questions？

Otherwise I'm going to jump into some things that you probably have seen and I'll ask you questions of it also so I like this code from hemming I don't know why this yeah the purpose of computing is to gain insight this is heming and it's cat the people know about heming。

😊，Havingming codes？Yeah， some people know how some people don't know we're having distance。Okay。

 maybe I'll talk about that later， I want to cover the basics right now。

 but remind you to talk about hammm distance later， but Taming actually came up with coding theory。

 at least a lot of it and the codes that he developed are used in air collecting codes and modern machines。

😊，We'll talk about timing distance later I think， but basically his view was really computers were viewed as computational devices。

 but he really viewed computers as doing computation to solve problems and that's actually think a good view of computing and in the end you have a problem and you want to solve it by orchestrating electrons right at least in today's technologies。

😊，嗯。So how do you do that if I had a way of talking to electrons and told electrons electrons solve my problem that would be nice right maybe that'll happen at some point if machine learning actually advances to that stage I have my doubt but the reason we have this levels of transformations we cannot bridge this gap and to bridge this gap we express our problem with an algorithm。

Again， I will not go through the details of what an algorithm is。

 hopefully you studied that at some point。Have you。Okay， good。

 but I provide it for your benefit over here， at least our definition。

 and then you implement the algorithm in a programming language。

rite it in a program and then that gets executed partly using system software mechanisms。

 virtual machine operating system memory management。

 and then both the program as well as operating system execute on top of the hardware software interface。

 they basically have instructions that are specified using an instructions to architecture。

 which is really the contract between software and hardware。😊。

It's really what the programmer assumes hardware will satisfy so that's the definition of instruction at architecture you've probably seen that before that's good and then that instruction that architecture gets implemented using some micro architectureure as we will see soon。

😊，And micro architectureiture gets implemented using logic gates， digital logic circuits。

 these are building blocks micro architecture， for example， gates。😡。

And then those logic gates get implemented using devices like transistors， etter。

 and transistors operate based on principles of physics， which is what moves electrons。

 so that completes the picture over here。So in this course we're going to talk a lot about over here。

 we may go into logic a little bit today。😊，Probably you've seen the difference between ISA and Arcm architecture。

I think of well ISA is really the interface interface between what the programmer assumes。

 what the hardware will provide， and I think there's a nice analogy over here with cars。😡。

Cars have very similar interfaces right gas pedal for example。

 well self drivingiving car is a little bit different maybe in the future you will not have this interface either a different interface will change so the ISA is changing as you can see but it changes very slowly you still have these cars and the gas pedal is really the interface for acceleration but internally。

😊，呃。At the micro architecture level there may be many ways of implementing that acceleration right you could implement it using mechanical parts complete。

 you could implement it using an electronic complete the electronics part potentially I don't know how to do that yet。

 but you could implement it using different ways essentially and that's really the internals of the engine and what happens after you press the accelerating level and that's very different in many different costs。

So that's the difference between IA and my architecture from my perspective and the user。😡。

The driver of the car doesn't need to know anything about the underneath。😡，Do you agree。

When you drive。But sometimes it could be helpful right you may decide to press the button like 50% if you knew actually how efficient your engine would be if you press the button at different levels。

 let's say。So actually knowing the underneath could potentially enable you to optimize the system better。

😊，This is my poor man's explanation of how you can optimize across the stack。😊。

By knowing what's going on underneath。Okay。So implementation。

 micro architectureit can be different various as long as that's satisfy the specification。

 for example， you can have an a instruction。😊，It's the same in the ISA but then adder implementation can be different across different micro architectures it could be ripple carry。

 carry look ahead bit serial etc ceter， so I'm going to refer a lot to Harris and Harris book which we will recommend you can find it on our website have you studied adders。

😊，No， not somewhat in computer engineering。Or something else。Oh， dig you take， okay。Two years ago。

 okay， so you remember any of these ripple cherry cher， look ahead。😊。

E okay yeah that's okay I mean you don't need to really know this for this course I'm not going ask your chair look at it or et cetera clear that there's actually a computer athmetic field that is actually quite exciting and it's actually really important today especially because of efficiency of machine learning because a lot of machine learning is really about computer ametic in the end how you implement matrix vector multiplication。

😊，But these are very there are many different ways of including adders where the tradeoff is latency cost。

 area， overhead， bandwidth， et ceter， we're not going to go into that if you're interested you can look more in this Harris and errorss so similarly X86 ISA has many implementations right for X86 is the ISA that's kind of dominant today although it's changing I think over time at least in general purpose computers there are many。

 many implementations by especially intel AMMD。😊，And micro architecture usually changes faster than ISA。

There are few ISAs like X86 arms， spark， MIps， Al risk， five， et ce。And their GPU I is also。

It changes but many micro architectureitectures because micro architectureure is easier to change right it doesn't when you make a change in the micro architectureecture the program doesn't need to change so there's a huge software stack gets built on the ISA。

😡，But you can change the micro architectureit to speed up programs without changing any of that software stack。

😡，Next that's serious and that's we see a similar example over here right this gas pedal has not changed for many decades。

😊，But underneath， there has been a lot of innovation in engines。Okay。

So my correct architecture is the implementation of the ISA under specific design constraints and goals。

 you can also think of it as anything done in hardware without exposure to software。😊。

This is a kind of way of thinking about it so pipeing you covered pipelining you know about pipeing okay。

 so today we're going to go up to pipeing hopefully in order we're out of order instruction execution have you covered out of order。

😊，In detail， so that's what we're going to start with。

 especially next next week in the second course， hopefully if we cover the basic materials。

 but if you' told them to tell me that you know everything about pipelining maybe we'll start out of order without covering the basics。

😊，So that's going to be important because all modern microprocessors are out of order execution processors。

 pipeing provides throughput， out of order instruction execution makes it much better。😊。

Me we access scheduling policy， speculative execution， probably you' in speculative execution。😊，Yes。

 no。Okay， branch prediction， for example， have you seen different techniques for branch prediction touch on。

 Okay， so we're going to go into more okay， that's great。😊，Okay， in 30 minutes。

 we're going to go longer in that so you don't know about perceptron based branch prediction。

 for example， Okay good that's a good test， superscalear execution。😊。

Basically fetching multiple instructions per cycle is a simple concept， clock gating。

 these are actually all examples of micro architecture。😊，Normally these are not exposed to software。

 that's why I am calling them micro architecture， but you could expose pipelineing software also you could imagine an ISA that says。

 oh these are the my pipeline stages。😡，And the software can schedule things on the pipeline stages。

 it'll be an ISA that doesn't give a lot of freedom implement of implementation to the lower level hardware designer。

So placing the ISA is important， but we're not going to cover a lot of that in this course if you're interested in that DDCA is the place。

😊，Cashching， prefetching， voltage jump frequency scaling， error correction。

 I put question marks over here because that really depends on whether the cache prefeter。

 et ceter are exposed to the IA exposed to the programmer so the key test is really is something exposed to the programmer does the programmer need to know about it when they're writing programs。

😊，And this could be any programmer。Okay， let's play a fungi。Property of ISA or my architecture。

 upcode of an ad instruction。😡，What do you guys say？Ia。I okay I say I say people are correct。

 I'll go through this relatively quickly because this is very basic I think type of data used in the ALU。

😊，i a。No， my architecture， okay， I kind of fooled you there， yes。

 number of general purpose registers。😊，Yes， go ahead， you can blurt it out， no problem， I I say yes。

 number of cycles to execute the multiply instruction。Birt it out。Michacro， yes， I'll go with micro。

Although it depends on the execution model， as we will see， we'll cover， for example， viaIW。

 very long instruction word architectures。😊，Have you heard about those？No okay。

 good now we'll see that in later execution， this a paradigm of designing computers where people said。

 okay， we're going to expose the latencies of each instruction to the compiler so that the compile can actually extract parallelism and schedule everything static。

😊，This way， hardware is simpler and much more efficient。Compilr is complex。

 but hopefully it does a good job。Okay， number of port of the register file。😡。

How many things can you read from the register file concur？Mi girl， good。

Whether or not the machine employs pipeline instruction execution。Pipe planninging risk。

Oh usually micro usually micro yes exactly， except for maybe real IW， yes。

That's good program counselor。Yes， okay， good， okay， good， I think we're at a good place yet。😊。

All right。So now that we know what an ISA is how do we implement it and you've seen some of the implementations。

 but there are many， many opportunities for implementation here， but in other words。

 how do we design hardware that obeys the hardware software interface？😡，In other words。

 how does a machine process instructions， what does processing an instruction mean？😡。

And for now I will assume the One Neman model， but we will break that later you heard about the One Neman model okay good so it's going to be a little bit of review。

 but basically one Neman model has two properties okay maybe you can tell me what those two properties are。

😊，Two major properties， yes， okay， that's good， I mean that's part of the I wouldn't call them as major。

 but yes。you only have one type between the processing unit even in the。Okay。

 yes stored program execution yes， I think maybe you guys are getting to the same thing there's stored program computer there's one more thing that's actually going to cause a lot of trouble to us that's why we're going to do out of order execution。

Inent。There sub multiifiable codes。No。not necessarily。But that causes problems also。

That could be in a one normal mile， you could actually say South modifyifying code is not allowed。😊。

Sequential execution。Basically。Maybe you mentioned that I don't know。

 maybe you were going to start it， but basically every instruction is executed sequentially in the one normal model。

 no instruction can be started before the previous one can be completed。😊。

That's the strict definition。But in the micro architecture you can violate that as long as you report to the software that everything is in order Okay so we're going to see that basic that's what out of order execution is all about okay so basically we have architectural or program of visible state before an instruction is processed and then we process the instruction and then we get architectural state prime。

Wwhichch is what happens after the instruction process and ISA specifies how to transform AS to AS prime you can think of an ISA as a finite machine actually if you think about it。

 where the inputs are instructions。Okay， crosssing an instruction means， as I said。

 I think transforming AS to AS prime according to the IAC specification of the instruction。😡，Okay。

 these are the two major things in a one million model。

 although there are other things that you mentioned also basically stored program sequential instruction process。

😊，And yes， the annoying models is usually associated with this picture。

 which is decoupling the processinging unit and memory。😊。

So that's true and but then there's other parts also actually output input controlling etc and again in DDCA we cover this in a lot more detail。

 but I'm not going to do that right now you've probably seen some version of it in computer engineering so what is programmer visible state this is architectural state that's visible to software essentially programmer sees all of these and can modify it memory is an example it's array of storage location by an address registers。

😊，It could be general purpose versus a special purpose。

 and there's a program counter that you guys all got correct。

And instructions and programs specify how to transform the values。😡。

In this architectural state to the next values， essentially。Makes sense。

So architectural state is program visible， but then there is also micro architectural state that's not programme visible。

😡，Okay， so we're going to add more and more of that as we go along。Okay。

 process instructions I said this already， I say specifies what AS prime should be given an instruction and AS architectural state。

 my architecture implements how AS is transformed to AS prime。So as I already said。

 I say it can be viewed as an abstract finite state machine where states is program Re state next state logic is instruction execution specification。

 hopefully these are things that you're kind of familiar with at least if you have a finite state machine。

 you have states。😊，And you have a way of going from one state to another state and next state logic determines how you transform from one state to another state。

 essentially， and that next state logic is combinational and the fact that you're moving between different states is sequential essentially。

Okay， from an IA point of view， basically， there are no intermediate states between AS and AS prime。

😡，That's what the programmer assumes， essentially during instruction execution。

One state transition per instruction。Where micro architecture is a different mindset， essentially。

 there are many choices of implementation over here。

We can now programr invisible state to optimize the speed of instruction execution。

 we can have multiple state transitions per instruction。😡，For example， one choice is actually。

Implement things exactly as ISA specifies them。😡，Bad idea， as we will see。

 this is single cycle machines you may have heard of that have you covered that in computer engineering？

Okay， maybe you called it something else I don't know yes it we like a architecture and then we split it into like five look at cycle one stage like just doing one clock cycle Okay Okay。

 exactly yes， so it's essentially the same thing doing one clock cycle in one。😊，At Mongo。

 I'm going to put cover in a different way。So maybe you wouldn't call it exactly single cycle machines。

 but this is a choice one， which is a bad idea as we will see using a principled framework we're going to evaluate it the other choice is what's called multicycle architectures which may be one of those dividing it but there are different ways of dividing a pipelineing is also dividing it you basically go through multiple cycles take multiple clock cycles to transform as architectural state to architectural state prime and for this you need my architectural state。

Transitions。And while youre doing that， you make you should not change the architectural state so that the programmer doesn't get confused right because these are the things that you're doing to execute the instruction and the graularrity of visibility for the programmer should be the instruction。

 right， not my architecture。😡，Okay， so let's go through this relatively quickly I'll。

Sorry I'll eat into the break a little bit but then hopefully we'll start to again so essentially I don't want to break it in a nuts so let's say nice place。

😊，A very basic instruction processing engine。😊，Essentially is designed to such that each instruction takes a single clock cycle。

 takes it。Meaning there is only combination logic used to implement instruction execution。

 there are no intermediate programr invisible state updates。

 and then you update the architectural state， which is essentially registers and memory。😡，Okay。

 so this is basically what we're going to do process instruction in one clock cycle so that you transform as to AS prime。

And single cycle machine looks like the sector。😡，You have sequential logic。

 which is the architectural state， which stores your architectural state。

 and that architectural state is fed into some combinational logic that implements your ISA。

 essentially every instruction specification， and then you produce ASP。😊，Now。

 the question is what is the clock cycle time determined by？Over here。

That is determined by the critical path delay over here right probably you' have done some of this in the past plus。

 of course， the delay of the sequential logic。And then I can also ask the next question。

 which what is the critical path， meaning longest delay path or in this combination logic determined by？

😡，And that is really determined by。The longest instruction to execute。So this sounds bad maybe right。

 meaning longest instruction to execute maybe may take really long because instructions are very different。

 a matrix multiplication can mean an instruction。😡。

And memory access can be an instruction then you may get a cache miss， et cetera。

 right it could be hundreds of like nanoseconds or so or more。😊。

So that's a single cycle machine each instruction takes a single clock cycle all state updates are made at the end of an instruction execution the biggest disadvantage is the slowest instruction determines cycle time。

 which means that you get a very long clock cycle time that's why people have a lot multicycle machines which are much more reasonable。

😊，This is I don't think this is realistic at all， but it's good to study it to see bad ideas here instruction processing is broken into multiple cycles。

 clock cycles or stages state updates can be made during an instruction execution but these are micro architectitectural state updates architectural state update is made at the end of an instruction execution when you really are going to finish the instruction you update the architectural state。

😊，The big advantage is now the slowest stage determines your cycle time。

 so it gives you freedom to optimize。😡，Here， for example， the worst case determines your common case。

😡，Basically everything is worst case， based on worst case here you can optimize for the common case if you're executing matrix multiplications all the time。

 optimize for that right make that really fast in your clock cycle as well as number of cycles to take that and forget about the square root instruction that you have in your ISA because someone decided that was a good idea to put over there。

😡，Because that's going to take forever and no one is using it。But be careful with that of course。

 no one's using it is always a difficult thing to discuss right there may be someone in the world using it。

😊，Okay， so both single cycle and multicycle machines literally follow the one N Neman model at the micro architect level。

 it's good to think about that also。😊，One moment model says sequential instruction execution。

 so I'm specifically talking about the sequential instruction execution part。😊。

Both of these actually。😡，Don't bring in another instruction into the machine before the previous one is complete。

😡，We're going to violate that with pipeline， pipelining violates that actually micro architecturally。

 so you've probably seen that perspectives。Okay， let me quickly go through this and then before multicycle。

 I think I'm going to take a break。So you've seen the instruction processing cycle， probably。

 instructions are processed under the direction of a control unit。

Instruction cycle is sequence of steps to processinging instruction this is very different from a clock cycle clock cycle is related to how long is your clock cycle and the machine determined by a critical path the unfortunately called instruction processinging cycle also so fundamentally there are fetch decode evaluate address fetch Al brands executes store results steps you've seen this before。

😊，Okay， even pipeing for example， not all instructions require all six steps actually and this becomes an issue in pipeing also so this is what happens basically you fetch an instruction decod evaluate data as fetch up execute store the result。

 update the architectural state and you fetch an X instructions both single cycle and multicycl follow this model。

😊，So in a single cycle machine， all of those six phases that I showed you take a single machine clock cycle。

😊，In a multicycle machine， all six phase of the instruction pressing cycle that I showed you can take multiple machine clock cycles In fact。

 each phase can take multiple clock cycles so if you go back over here，😊，You can take I don't know。

10 cycles to fetch five cycles to decode et cetera。

 and you can optimize that in fact usually fetch opera from memory takes a very long time。😊。

So you really want to not wait for it and make your clock cycle dependent on it， right okay？Okay。

 I think this is actually a better place to take a break because。

I'm going to switch the data path versus control。So let's take a break。

I think let's be back at 15 pasts， sorry， a 10 minute break today。

And then we're going to cover hopefully what you've seen mostly。😊，But this is in a different way。

 probably， right？But feel free to ask questions。Yes。好东。嗯。Okay。好的。Yeah。あ。I have flash again。

 I don't know if they possible。Right now， of course， its only for corporate purposes for the。

We need to charge this or or no， this thing would be okay。Okay， okay， that's good， yeah。

And we also have another one so we can just change Okay， that's good。 I don't know。 I guess so， yes。

28的去。I， I didn't check the9 thing at the point。 Yes Okay， look yeah， that's good。对他都是。是。说。没丽。し。

I thought最。Or I send an email to。要这常。个是啊。他们把这个。Hello there。So。可以。

alicallyWhat do you think that process will be done with。Say three peace。Or this is better for me。

Yes。o。😊，All right。Is everything good online。 Can you check。 Okay， all good。All right。啊そ下。Yeah。Okay。

All right。Ohpe， maybe thiss not working anymore。We're still sharing it right online， okay。Okay。

 it's working now。Okay。So let's take a look at instruction pressing another way。

 which you have covered also probably data path versus control。

 essentially instructions transform data to data pride。

 architectural state to architectural state pride。And this transformation is done by functional units that operate on data。

😊，These units need to be told what to do to the data， right？😡，And as a result。

 an instruction pressing engine consists of two components and usually these are distinct components that are designed separately and then of course they interact with each other that are put together data path。

 for example， consists of hardware elements that deal with and transform data signals。😊，For example。

 functional units that operate on data， multiplication units， addition units， logic units。

 hardware structures that enable the flow of data into the functional units and registers。

 and there are many things wires， Maxs， decoders， triSt buffer， etc。

Have you seen all of these before？Maybe try to go for okay。

 definitely don't worry about it that's not that important， but this is one way of。😊。

Is putting signals onto a wire。Basically， you have an input signal and then you want to put it into a wire。

 some bus for example， and a trit buffer is put between the input signal and the wire and then there's an enable signal if you enable it this input signal gets connected to the wire。

Okay。There are different ways of implementing that and loading onto a bus。

 but yeah we cover this in the DDCA so if you're interested in all of these in DDCA。

 digital design and computer architecture has a digital design component that covers some of the essentially all of these things actually。

😊，And we over there we have FPG exercises， but you guys are don't need to take DTC I think so storage units that store data are also part of the data path like registers。

 memory units et cetera， and of course theirre associated circuitry to address them et。😊。

There's also a control logic and control logic consists of hardware elements that determine the control signals。

😡，In other words， signals that specify what the data path elements should do to the data。😡。

And when you designed or when you've seen a pipeline processor probably you've seen the different parts right there's a control unit and there's a data path yes okay that's good I'm going to show you a picture don't get scared this is from a book maybe you have not seen the exact picture but this is an example of a single cycle processor single cycle MIps processor MIpses an IA from Harris and Harris essentially the data path is the black parts and control unit is the blue parts and control unit takes the instruction as input and generates control signals。

Based on the instruction to control what the data path elements should do to the data that is read based on what's specified by the instruction Have you seen a picture like this。

 Okay， great maybe not the exact picture or did you see the exact picture。Not the exact one， Okay。

 very Oh very similar。 Yes， I yeah， a lot of the material is very similar。

 but essentially this's a single cycle processor in the sense that。😊，Everything is done in one cycle。

 you essentially you have the program counter， you fetch the program counter。

 you input it into the memory， you read the data from memory， which is the instruction。

 and then you decode the instruction， access the register file。

 you operate on the up and then produce the result and then if needed。

 you write data to the memory or you read data if it's a load instruction from memory and the write the result back if the instruction specifies it to the register file。

And you can see that there are no latches。Or registers to buffer anything。

 meaning everything is combinational logic。Until you latch the data back into memory and the program counter to the program counter。

 correct？This is the example of single cycle machines， so your clock cycle is very long。

And then you can do fun analysis which we're going to do a little bit。

 so okay I don't want to harp on too much， but every instruction takes one cycle takes executes cycle per instruction strictly one in a single cycle micro architectureit now how long each instruction takes is determined by how long the slowest instruction takes takes execute。

😊，Even though many instructions do not be that long to execute。I already said this。

 so I will not tarrppon again， but let's take a look at this critical path analysis。

So if you want to find out what is the slowest instruction process。

 you need to think about how long you actually spend on evaluating these different phases of each instruction so in this particular analysis we simplify it a little bit。

 you have five stages you don't have to have six stages etc because you can merge some of these things with each other again I'm going through this relatively quickly because you've probably seen something like this。

Now the question is， let's find the critical path there's a game we play in DTCA initial design and computer architecture。

 probably you've played a game like this before， critical path analysis， that's good。😊。

And to be able to do this， essentially you need to list all of the instructions in your ISA and list all of the steps to execute an instruction and figure out how long the maximum delay is for each instruction and this is what's done for a subset of instructions in the MIPS architecture there are some assumptions of course memory units take 200 piconds AL and address take 00 register files 50 other logic and wirelessly is magically zero which makes analysis easier of course but that's not true in real life clearly。

😊，Now you actually put together different instructions types， and then you figure out that。

Almost always the problems are load instructions whenever you access the memory。😊。

That actually goes through all of the steps and it takes in this particular case， 600 piconds。

Makes sense， this is spreadsheet analysis that you can do quick and dirty but the real analysis of course needs to be done with simulation tools and read the real real analysis really in the hardware in the end but first you simulate you basically design the processor and then figure out how long each instruction takess these are the data path and can units exercise by ALU instructions in the MIps architecture on this particular design and you can see that the critical path is over here and the total is 400 there's also program counter update that happens concurrently which is much faster as you can see and we assume some things。

😊，Again， in DDCA we've covered this in more detail， load actually takes exercises。

 essentially all of the units across this data path over here， so it takes 600。😊。

Updating the program counter is only 100 because store is a little bit shorter than load。

And taken branch is actually reasonably short， but you need to find the critical path basically based on the specification of the instruction as well as what is your micro architecture。

😊，Okay， so you've seen something like this before probably so I will not go into I will not tarpoint。

 so this looks not so good meaning youd assuming all of the these are correct you set your cycle time to be 6000conds。

😊，But。Maybe most of your instructions are need 400 becausecond， right？😡。

So you're really optimizing for the worst case and this worst case is actually much worse than what I showed over here in modern memory systems。

 memories are huge as a result accessing memory and it's also off chip。😊。

Accessing memory takes hundreds of nanoseconds in some cases so you don't want to clock cycle time that's hundreds of nanoseconds right Okay so basically this is a bad design in the end so let me introduce some architecture or micro architecture design principles I think there are many principles I can come up with of course。

 but these are three major principles if you want to optimize for performance。

When it's critical path design， bread and butter， common case design and balance design。

 third is balance design and single cycle micro architectureures violate all of these critical path design means find and decrease the maximum combinational logic delay as much as possible to maximize frequency we're talking about performance for energy you may actually come up with different principles which we will talk about later on。

😊，Basically， you break a path into multiple cycles if it takes too long and clearly a single cycle doesn't do any of that。

😊，Bread and butter coming case design is basically you design。

 spend time and resource on where it matters most， meaning what is the machine going to execute in the common case？

This is part the art， of course， right if the machine is going to execute 99% matrix vector multiply instructions from the register file optimizing。

😡，For something else that may not make sense a lot and that's the idea of oh okay。

 maybe we could go through accelerators right accelerators actually come from this common case design。

 what am I going to execute in my workload。And clearly in this case we're doing worst case design with single cycle because worst case really determines the common case well common case performance balance design is essentially you balance instruction data flow through hardware components。

 eliminate bottlenecks as much as possible， balance the hardware for the work essentially and this is also violated but I will not go into that in detail we'll see balance design later on。

😊，So these are the design principles， it's good to think about these when you're designing a high performance system。

 how am I actually satisfying them， how am I violating them， can I do better essentially？😊。

Sometimes balance design is very hard to satisfy， for example。

 today's machines are actually not so bad at these two， but they're terrible at the balance design。

And what I'm referring to over here is the balance between compute unit and memory。Essentially。

 a compute unit has a lot of performance， but accessing memory is done using a thin pipe。

 meaning a low bandwidth。Memory bus as a result there's a huge imbalance between compute and memory today and that's what we will foreshadow into thinking about like future like processinging in memory type of architectures why don't we put compute units inside the memory itself so that we don't go through a tin pipe。

In the micro architecture。Okay， so essentially single cycle micro architecture doesn't do too well we're going to compare multicycle to these principles also。

 yes please what is the difference between putting more memory into the CPU compared to putting compute into the memory that's a great question we can talk about when we come to it but essentially you can put more memory into the CPU where the logic is the question is how much memory can you put over there what we're limited by today is the technology。

😊，The denser memories require a fabrication process that's very different from how we fabricate CPUs。

 meaning logic today， if you want to have very dense huge memories， you need to。

Design logic for those huge memories， let's say。So basically there's a fabrication process dichotomy。

 unfortunately， people have not figured out how to make tense memories using the fabrication process CPUs。

Are fabricated with。That's a great question if you figure that out somehow。

Then maybe you get rid of the balnik。A lot of people tried it。

That doesn't mean that you should not try to。Okay。So always we're going to ask this question in this lecture and I think it's always good to ask this question to do better going into the future。

 the question can we do better and I think I've already given you the idea of how to do better multie micro architectures but let's examine it in a little bit more detail and then we're going to go into pipeline。

😊，So the goal， as we discussed in multicycle micro architectureures is to let each instruction to take close to only as much time as it really needs。

 I say close to because you cannot be perfect over here because we're going to add some overhead also。

 which is latching overhead sequencing overhead， etc。

So the idea is to determine clock cycle time independently of instruction processing time。😡。

Each instruction takes as many clock cycles as it needs to take。😡。

And there are multiple state transitions per instruction。

And the states followed by each instruction is different。Okay。

 let me go back over here because this idea the first part of the idea。

 even though it may not sound like an idea it's really part of the core idea。

 basically I don't say these are the instructions that I'm going to execute and this is my clock cycle I say。

😡，I'm going to have a high clock cycle and I'm going to design my machine so that I can achieve that clock cycle。

Now you can argue that that high life cycle is good or bad， you determine different ways。

 but you actually have freedom to decide your own clock cycle， say 100 gigahertz。

And you can design a machine to do that with multicycle， you cannot do that with single cycle。😊。

So basically it looks pictorial like this， you start with an architectural state。

 you transform it to micro architectural state， process part of the instruction one clock cycle。

 store the results intermediate results somewhere， which is going to be our overhead。

 process part of the instruction in the next clock cycle。😊，And then process the next part， next part。

 next part， and these number of steps may depend actually they do depend on the type of instruction that you process and eventually you generate the architectural state prime at the end of the clock cycle。

Makes sense。Well at the end of a clock cycle at the end of the last clock cycle takes a good instruction there is not as single clock cycle as you can see over here an ad may take four clock cycles multiply can take 10 clock cycles and memory access can take as long as it needs to take because it may go to far away right today we actually have far memories also not just local memories but remote memories。

😊，Okay， especially in data centers， so this is actually one of the designs that is proposed by Morris Wilkes。

 who is essentially a leading computer architect one of the fathers of computer architecture。

 let's say。😊，Essentially， the realization is that you can implement the process instruction step as a finite sake machine。

😊，Actually， everything is a finite state machine， but now you actually implement the process instruction step as a finite state machine that sequences between states and eventually returns back to the fetch instruction state and I'm going to show you an example of this finite state machine a state is really defined by the control signals asserted in it in a given state you say okay these are the control signal that I assert these are the control signals that I assert and that is actually determining what the data path does。

😊，And that's the signature of the state。In fetch state， for example。

 I read from the program counter and latch it into the instruction register。

And that's fetch state well not to read from the program counter input it to the instruction memory。

 which could be a single memory at this point and then la into instruction register the control signal that enabled you to do that are asserted in that state that's a my fetch state。

 you can have fetch one， fetch two fetch three， fetch4， fetch5， five fetch states。

Control signals for the next state are determined the current state。

 so you overlap the computation in the data path computation in the current state with the control signal generation for the next state。

 this is a good design principle so that your control signal generation doesn't become the critical path。

😡，Earlier。In the picture， we looked at actually data path。

But control signals may become the critical path if you have a bad design， in general。

 control signals should not be your critical path。Okay I'm giving you a lot of thoughts over here and ideas。

 but hopefully you've seen some of this before， so this is an example of a multicycle micro architecture finite state machine。

😊，Ss it again from Harrison Harris。For example， this state is the fetch state。

 and it basically specified which control signals are asserted， which ones are not asserted， eta。

And then you decode the instruction。And the quote state has some signals。

And then based on what you decode it， based on the up code。

 you jump into different sequence of states。😡，For example， if it's a load word。

 you have a memory address generation state over here。

 and then based on whether it's a load word or store word。

 the next state is either memory read or memory write。😊，And then。

Once the memory write is done in a store war， you go back to fetch the next instruction with the next PC。

 which should have been incremented in one of these states over here。Okay。

 first load word you do right into the register， so now you can actually optimize your finite state machine such that。

Hopefully you minimize you achieve your clock cycle， right？

None of these things that are described here should not exceed。

 well at least to the combination of logic delay to implement them should not exceed your clock cycle。

Makes sense。Okay。So again， I'll go through this relatively quickly。

 but instruction processing cycle is divided into state a stage in the instruction processing cycle can take multiple states。

😊，Multiple clock cycles。A multie micro architecture sequenced from state to state to process an instruction and the behavior of the machine in a state is completely determined by control signals in that state。

 I'm harping on this because this is really important。

Which means that if multiple different instructions actually share the same behavior。

 they can use the same state and then you can branch out so you can actually optimize your finite state machine also。

And the behavior of the entire process is specified fully by a finite take machine。Okay， in a state。

 as we discussed control signals control two things。

 how the data pass process the data and how to generate the control signals for the next clock cycle。

😊，So this was our single cycle micro architectureecture。

We're going to keep most of it the same to do a multicycle micro architectureit。

 but we're going to optimize， so this is a multicycle micro architectureure。

 which probably you've seen also。😊，Correct， again， maybe not the exact same thing。

 but what we've added over here is we still have the control unit over here。

 so let's go back control unit is a little bit more complicated because we have intermediate。😊。

States meaning these registers over here that we added so that we can latch intermediate data before we didn't have any latches in between now we have latches so that we can optimize a clock cycle so the clock cycle is determined by this stage or the stage or the stage basically you need to follow how the data flows through the registers okay so if we've added a lot of registers as you can see and you've added some more control signals etc。

Okay， let me actually， these are extra register that are not needing a single cycle design。

Makes sense。So we have hardware overhead， we paid some cost。

 but we actually gained something if you paid attention to the previous slide which I don't expect you to because this is so small and far away。

 I can barely see it from here basically we saved some things we don't have that many ALUs as before we can actually get away with a single ALU we're frugal。

Why because in the previous design in the single cycle design。

 we needed to have as many ALUs as needed to execute an instruction in a single clock cycle。

 you cannot reuse the same ALU across different。😡，Stages of instruction you have to have。

 for example， if you're doing an ad， you need to have an adder。😡。

And then you need to update the program count that requires an adder also。

You cannot reuse them because you're doing everything in a single clock site。

 you need to have combinational logic to do everything that is possible in an instruction concurrently。

 but if you actually。Say， okay， I'm going to do part of an instruction in a clock cycle。😡。

You can get away with a single all。Which is nice you can actually be also consolidated instruction and data memory together also instead of having separate memories instruction and data we have。

The same memory over here again in a similar way。You can when you're fetching an instruction。

 you use the instruction part when you're loading data or storing data， you use the data ports。O。

Okay， so basically this is a summary in a single cycle micro architecture we have low clock frequency and high hardware cost。

 I've added that now in a multicycle micro architecture we have higher clock frequency simple instructions take only a few clock cycles and we can reuse expensive hardware across multiple cycles。

😊，That's also nice。Now the downside is we have hardware overhead for storing intermediate results as I've shown you。

 and we have sequential logic overhead paid many times for each instruction because you have to  la the data at the end of the clock cycle and that eats from your clock cycle。

 if you think about digital design there's useful work that you do in a clock cycle which is processing the data and there's the overhead which is sequencing you need to  latch the data and as you make your clock cycle smaller and smaller and smaller the useful work becomes a smaller fraction because the sequencing overhead it starts to dominate。

😊，So it becomes at some point if you actually make your clock cycle extreme maybe even less than one gate your sequencing overhead maybe higher so in the end as you pipeline deeper well I shouldn't' use the word pipeline as you make because we're not pipeline necessarily that's a higher level concept as you but this applies to pipelineing also which I'm going to say as you make your clock cycle smaller and smaller at some point it doesn't make sense to make your clock cycle smaller because you're paying a lot of overhead and your latency of crossing an instruction actually increases because your instruction goes through many。

Many clock cycles where most of the clock cycles spent sequencing。Right doing use work as， well。

 it's not useless work， but doing sequencing overhead so that you can store the data and latches。😊。

Okay， so multicycle requires the same design as steps as single cycle。

 you still do a data path and control logic， but you add these latches as we've seen。😊。

So one advantage of multicycle that we didn't discuss is flexibility and this is actually a huge advantage。

😊，Let's say here what we assumed actually something really bad over here。

Which is memory takes one clock cycle， right？But in modern systems memory takes maybe hundreds of clock cycles right so how do you fix that what if memory takes 500 cycles or what if memory takes an unknown amount of cycles。

 basically you have you have another signal， you add another loop over here says if the memory is ready。

 if your memory is not ready you stay in the cycle。😊，If the memory is ready。

 then you move to the next site next stage， next state in the machine。Does that make sense？

So there's a lot of flexibility and you can also add other instructions or write a program that actually goes through this fine United State Mach as a hardware designer。

 Mycrocode is an example of this， but we're not going to cover that。Any thoughts？Any questions？

These are all familiar concepts。Yes， earlier， I didn't quite forget how we could use like reuse the same ALU when we have like multi cycles。

呃 so。For example。😡，You have a fetch state over here， it's fetching， it's using the ALU。

 there's only one ALU in this。😊，And then you have， let's see， whereas this execute stage。

 it's using the same value， right？呃。The reason you can use it is because you've latched the data from the fetch。

😡，In a single cycle， if you do that。Which data are you going to supply to the ALU？

Does that make sense you're incrementing PC to a PC plus4？Or you're doing some operation。

 your instruction requires both。😡，Add instruction， so you really need two ALU so that you can increment PC plus four while concurrently。

Maybe not concurrently because data has flown through the first ALU， you fetch the instruction。

 you decode it， et cetera， but you didn't really latch the result， right？

If you go back and input the same input the registers or input the register IDs or registers that you read into the same ALU。

 now you need to change the control signals， you could do that but that would change your PC now you wouldn't be executing the same instruction as that makes sense the reason is there's no latching the first in the single cycle machine。

😊，Thank you， Sure，Any other questions？Okay。So let' let's look at the benefits of multi design。

 so this is actually good for critical path design again using our framework， principled framework。

 you can keep reducing the critical path independently or the worst case pressing time of any instruction。

 this is great， it gives you flexibility。😊，You can optimize for the common case。

 you can optimize the number of states it takes to execute important instructions that make up much of the execution time。

 for example， you focus on that part of the finite state machine as opposed to some。😡。

Not so commonly executed part。And you're more balanced。

 there's no need to provide more capability or resources than really need it and this is what the previous discussion kind of points to right as opposed to having three values you may get away with one。

 depending on your instruction set of course。😡，Okay。

 I think I've discussed this an instruction that needs resource X multiple times does not require multiple Xs to be implemented。

 that's kind of a summary。Okay， I think I would said that。

 but there are the downsides we've seen also need store the results。

 there's hardware overhead register set up and hold overhead what I call sequencing overhead。

And we're going to talk about this downside to build up to pipelining， limited concurrency。

Only a small part of the machine is used at any point in time。😡，So for example， when you're fetching。

😡，Only the fetch part is used。But there's a lot of stuff that's part of your machine， right。

 ALU memory register file access， none of that is used because you're actually executing only a part of the instruction and this becomes worse and worse as you reduce the clock cycle time。

As you make your machine higher frequency。Now you can say this is okay。The hardware is useful。

 but then you're not utilizing your hardware in the best way possible。😡，Okay， before I go into it。

 have you seen the performance analysis equation， does this look familiar？😊，Basically。

 execution time of an entire program is a number of instructions times average cycles per instruction times clock cycle time。

😊，Yes no maybe you don't remember maybe not if you don't remember it probably not。

 this is also called some people called the iron law of computer architecture。

 but it applies to some general purpose systems actually it's a good way of thinking about execution time so execution time of a single instruction is really CPI cycles you take to execute the instruction time to clock cycle time this makes sense execution time of an entire program is。

😊，This summed over all of the instructions we execute in the program。😡。

You can also think about that as number of instructions times average cycles per instruction in your program times the clock cycle time now this gives you a way of thinking about how to optimize your system right if your goal is to maximize performance。

😊，You have three things to play with。Now， a number of instructions。😡。

You can play with it at the compiler level or the programmer level。

 you can write a different algorithm， different program ettera。

 we're going to assume that the number of instructions is the same。

If you want to actually fairly compare my architectures。

 you should either assume that or figure out the best number of instructions that provide the best overall performance for each architecture。

 which is not an easy thing to do。😡，So fair comparisons are actually very hard than architectures in general。

😊，But anyway， assume that number of instructions is the same。

 we can play with average CP and clock cycle time at the micro architectureitecture level。

Micro architecture usually cannot play with a number of instructions because that's specified by the program。

So a single cycle micro takes your performance says CPI is one clock cycle times long。

Whereas multicycle， CPI is different for each instruction。

 average CP is hopefully small and clock cycle time is short。😊，So you gain on both parts。

 essentially， yes， well sorry yout you don't gain on both parts， let me correct myself。

 your average CP is higher than one。😡，But clock cycle time is much better， hopefully。

You' see average seat guide c for each programming individually， yes exactly。

And when you evaluate a machine my architecture in terms of CPI。

 you can actually aggregate across many programs also， this is my every TI and this set of programs。

 this is my everyT and this set of programs and overall this is my every CPI。😊。

But clock cycle time doesn't change across programs。Yes。So。

Just just a bit branching out how would you what's good metric for comparing what's say memory load because this will obviously be。

Well， if your workload is memory intensive。😡，Your average CPI may go up significantly。

So you can still compare， this still applies。😊，Yeah， across different micro architectures。

 well across different architectures is different across different micro architectureits you you can do some comparisons right you run the same program。

 for example。😊，Acros different micro architectureitectures。

 and you can try to optimize CPI and clock cycle time。Anyway， we we'll get into memory more。😡。

But this doesn't take into context clearly energy， for example。

 or data movement overheads in terms of energy， but a lot of things get reflected on the average CP in the end so if we have a very memory intensive workload that waits for memory。

 average CP is very high。😊，Okay， so basically， I think my point here is in multicycle。

 we have two degrees of freedom to optimize independently。

 whereas in single cycle we have one degree of freedom， which is clock cycle time。

 but we don't have a lot of freedom in that degree of freedom either。

It's determined by with worst case。Okay， the question is always， can you do better？

And now we're going to get into pipeline。Essentially。

 the question is always asked what limitations do you see with the previous design in this case I've already given you limited con currency some hardware resources are idled during different phases of the instruction processing cycle in fact most of the machines。

😊，Can we use it for something else Fe logic is idle when instructions is being decoded。😡。

Or execute it， or at making MM access or writing the result back。

Most of the data path is idle when a memory access is happening。😡。

So can we use idle hardware to improve concurrency and the answer is yes。

 well why do we want to do that first of all， more concurrency is higher instruction throughput。

 meaning more work is completed in one cycle。😊，And the idea here is when an instruction is using some meaning。

 we can reduce the cycles per instruction。😊，Another way of thinking of it。

 we can improve instructions per cycle。But we'll get into these are two sides of the same point。

So basically， the idea is when an instruction is using some resources processinging phase。

 process other instructions on idle resources that are not needed by an instruction。For example。

 when instruction is being decod， fetch the next instructions。😡，When instruction is being executed。

 decodeotete the next instructions。😡，When instruction is accessing data memory。

 execute the next instruction。When instruction is writing its result into the register file access data might for the next instruction。

 so this is based on sequential execution doesn't have to be the next instruction。

 it could be any random instruction but that will make your life very complicated when you're updating the architectural state so next instruction is a good idea。

😊，Okay。So basically， you can have different instructions in different stages。

 so assume that we have these five stages。😊，What we can do is one instruction is writing its result。

 another instruction is。Executing the ALU and other instruction is accessing the register file and being decoded and another instruction is being fetched。

And now you need to change the control。😡，Logic to make sure that right control signals are generated for instruction in different stages。

So clearly we need to be more careful than this we cannot just。

Declare victory we need to actually redesign the entire thing to make sure it works。

 and we're going to look at that in a little bit。So I give you of the basic idea， systematically。

 we pipeline the execution of multiple instructions this is similar to assembly line crossing in factories。

😡，Basically， instructions go through an assembly line。

 every instruction goes through every stage in the pipeline。

I think we've already said this divide the instruction processing cycle into distinct stages of processinging and ensure there are enough hardware resources to process。

One instruction each stage and press a different instruction in each stage。

Instructions consecutive and program are processed in consecutive stages because of the sequential execution model that we assume。

And the benefit is this is increasing instruction processing throughput one over CPI。

 or maybe it another way it reduces cycle per instruction。

 it doesn't reduce the cycle per of an individual instruction。😡。

An individual instruction actually still goes through。The same cycles。

 except you're doing more instructions， so average CPI reduces， right？😡。

So it doesn't help the latency of any instruction， in fact it's going to hurt the latency if you pipeline more because of the hardware overhead。

 hardware register overhead sequencing overhead。😡，But it improves throughput of the overall instructions stream。

😡，Makes sense。Okay， so hopefully you know the idea so downsides it's good to start thinking about this because there could be many downsides also and we're going to cover the beauty is how do you handle the downsides can you have a better model etc ceter。

 so that's going to build up we're going to build up the auto order execution with this。😊。

But before we get ahead of ourselves let's take a look at pipeing a little bit more。

 so this was multicycle， you have assumed that you are doing four cycles per instruction。

 these are your stages。😊，And if you pipeline them nicely， you can actually finish four cycles。

 four instructions and four cycles。As you can see， right。

 because things are nicely pipeline over here。And at the steady state。

 it's called the steady state where your machine is full of instructions。

That's where you can see that you're executing four instructions concurrently except in different parts of the machine。

So this is nice now you have on average one instruction completed every one cycle here one instruction is complete every four cycle。

 so you improve CPI by 4X， so your performance may improve by 4X except。😡。

Maybe pipelining overhead will be worse over here for the reasons。

 so a clock cycle time may be lower over here， but if you can keep your clock cycle time the same。

 your performance may improve by4x。😡，That sounds great。

The problem is life is not always as beautiful。First of all。

 you may not be able to have a nice clock cycle time kept the same。

We're going to see that a little bit。You may not be able to fetch the next instruction。😡。

Because that requires you to know what's the next instruction address。

If you're doing sequentially that's good， but what if a branch happens。

 what if this instruction is a branch and you need to decide what is the next instruction。

 if it's a taken branch， if it's a not taken branch again you're fetching sequentially that's good。

 but what if it's a taken branch， you don't know that before you execute the instructions or you have pipeline bubbles etc。

 and what if instructions are dependent on each other。😊。



![](img/c38e05d34c60e66bef8947f7d5549fb8_10.png)

Maybe you actually need to stall the pipeline。Okay， so this is in a site。

 this is one of the first pipeline computers IBM stretch。😊，You can carry it in your pocket。

 as you can see。And the price is what everybody in this room can afford， I think。

I cannot afford that。

![](img/c38e05d34c60e66bef8947f7d5549fb8_12.png)

Okay。That's fun。So that shows that how technology scaling has been successful， right？

Okay so an ideal pipeline we would like to increase throughput with little increasing cost hardware cost in case of instruction processing so pipelineing can be applied to many concepts actually we talk about assembly line right actually that's how a lot of pipelines where people start thinking about analyzing pipelines and operations research for example there's a field that's dedicated to analyzing large scale production systems and pipelineing is a big component of operations research at least old type of operations research so if your pipeline should be efficient if you want your pipeline to be efficient ideally you should repeat identical operations。

😊，The same operations repeat on a large number of different inputs， for example。

 when you're doing laundry。😡，If you actually have a laundry， let's say， business。

 you get a lot of loads。And they all go through the same stage you do the identical operations on them。

 right， put you put them into a washer and then you put them into a dryer and then you fold them and then you give back to the customer。

There is no difference， hopefully there may be， I don't know， I mean I'm not in that business。

From my perspective， it's similar。But that's where the analogy end。

don't push it further okay and then you want to repeat the identity repeat independent operations so different loads are independent of each other in the laundry right so there's no depends between repeated operations and this makes your life easier because you could keep pushing things without thinking about oh this load actually should stop because my shirt needs to be processed first but there are dependences also over there as you can see。

😊，Okay， and then if you want to actually have a good clock cycle that's partitioned nicely across the stages。

 you need to have uniformly partitionable solver patients。

 basically such that processinging can be evenly divided into uniform latency clock cycles in this particular case。

That's true for pipe laundry also， because for example， when you're doing laundry。

 usually the dyer takes the longest。And that becomes a bottleneck right if your clock cycle is determined by the dryer then your throughput will be limited so if you're running a laundry business probably you pay more for the dryers and get more dryers for a given number of。

Wasers， right this is why dryers are expensive from my perspective because there's more demand on the dryers because they're slowering。

Okay， anyway， so automobile assembly line doing laundry are actually reasonably fitting examples。

 the question is what about instruction processinging cycle？😊。

Do we get all of these properties nice and unfortunately not。😡。

And that makes it things interesting and nice， so let's take a look at this ideal pipelineing so what we want to do this is like a single cycle machine right。

😊，You have some combination logic to execute instructions， T piseconds， ideally when you pipeline it。

😊，You would like your throughput to be doubled right if you have two stage pipeline unfortunately you have a sequencing overhead so that's not going to be possible if you pipeline it for three things。

 you need to basically decide how to pipeline also that's also essentially a design optimization problem ideally you would like throughput to increase linearly with number of pipeline stages。

😡，But unfortunately more realistic pipeline， you have a sequential logic delay and you pay that sequential logic delay multiple times just like in a multicycle processor in a realistic pipeline。

 so throughput K stage looks more like this over here t over k plus some sequencing delay。😊。

So this register delay reduces throughput。😊，And this picture still assumes that you can evenly divide the work nicely。

That may not be also possible， right？Because your boundaries of memory。

 your boundaries of registerries， your boundaries of ALUs may not really nicely divisible as T over K。

😡，So it's good to think about that。So a lot of digital design actually works on this sort of thing。

 how to optimize a pipeline for example， there's also cost。

I'm not going to talk about energy but cost energy is more complex if you look at non pipeline you have some number of gates。

 this is a single cycle again and then some register cost if you have a pipeline，😊，If you're lucky。

 if you nicely divide the gates across stages， your gate cost doesn't increase， that's not real。

 usually your gate cost increases and you multiply the register overhead by the number of stages。

Registers increase hardware cost extension again， this picture ignores resource and register application that's likely needed G overK and R over RK。

😊，Okay， I'm going through this route really quickly because probably you've seen things like this。

 right？😊，Have you designed things at that level， lower level or？Okay， some of you maybe。Okay。

 now let's take a look at I think weve already seen all of these processing cycles。

 so this was our single cycle micro architecture， this is another example of single cycle micro architecture again that looks like this what I've shown you。

😊，Some when you're designing a pipeline， you need to divide the single cycle microarchction to some stages and let's assume that this is the。

Division that you came up with you need to have some more things at it and you need to be careful about things that look like this right you actually are processing an instruction over here。

And this instruction is determining this the branch， for example， or the target of the branch。

 this instruction may change the program counter over here。

 so you need to be careful about these backward loops。

That come so that you actually do the right thing for the right instruction because different instructions are in earlier parts。

So assume that this is a partitioning that someone has done， there's always the question。

 is this the correct partition， assume that you want to design a five stage pipeline。😊。

Your throughput should improve by 5 x normally right。

 but if someone came out with this part you can say why didn't I have four stages or six stages。

 why not different boundaries？😡，It's always good to think about。

Let's take a look at the throughput of one of the pipelines， this is here， this is a multie oring。

I guess it's a multie design， but it doesn't matter one instruction is finished every 800 pickcoconds over here。

😊，No， this is a single cycle design assume that everything takes 800 piconds well in this case it doesn't matter because they're all same instructions where the assumption is the same here each instruction you get one instruction finishing every 200 piconds with the partitioning that we have seen。

😊，And the reason and the throughput improvement you get is 4 x as opposed 5 x。

 even though you have five each pipeline， right？😊，Why？Yes。

 our cycle is like 200 because that like it's it isn't like 800 divided by5 exactly yes。

 it's not 160， it's 200 because we couldn't somehow manage to divide it。Exactly， basically。

 we couldn't uniformly sub partition。The operations right， essentially。

 that's the last part that I discussed in an ideal pipeline。Okay。

 basically half of the clock cycle is wasted in two stages， another way of looking at it。

 there's some internal fragmentation that happens in the clock cycle。😡。

And usually things are than things could be worse than this。Okay， so you need pipeline registers。

 as I said， if you want to pipeline things to case stages。

 you need to add some pipeline registers so that you can store the intermediate results and that adds to the overhead as well。

So for example you need to store PC plus4 and you to propagate it until you actually may need to use it because it your instruction you're processing over here maybe a branch and you may need it for some reason etcter next PC actually you may need it over here you need to propagate some parts of the instruction register data elements that you fetch immediate etc so these register actually grow after you decode the instruction and then they try shrinking because you use some of the data in the stages that are later。

So they're not actually equal， this picture kind of shows that they're kind of equal。

 but they're not actually equal in terms of size。😊，Okay。

 you need to make sure no resource is used by more than one stage。😡。

All instruction classes must follow the same path and timing through the pipeline stage this actually leads to some other overheads so this load word is being decoded executed memory load word is nice because it actually utilize all of the pipeline stages that we have over here。

 but if you do an ad for example， it doesn't do anything in this memory stage。😡。

So not all instructions use all stages in the pipeline， and that leads to。😡。

Something that we don't normally think about but actually it has't a performance impact if you could actually do something else then you wouldn't waste that or you could do something more useful。

 it's much harder to do of course in a linear pipeline like this。Okay。

 this is the example of a pipeline control， essentially you have the same control unit as a single cycle processor。

 except your delay。😊，The use of the signals until。The appropriate point。

In the pipeline so you generate the control signals。

 you latch them and then you move them through the registers。

 some control signals are needed over here， so I have only two for example in this particular case and some other control signals are needed over here but you need to store the control signals that are needed in this stage as well as every other stage after that so your pipeline registers actually are quite large。

Okay， let me finish this and then we'll be done essentially this was our ideal pipeline。

 we want identical operations， independent operations uniformly subpartition operations。😊。

Unfortunately。We don't have an ideal pipeline and instruction processing unit。

We have different instructions， not all need the same stages。

 forcing different instructions to go through the same pyth stage leads to external fragmentation。😡。

Uniforms software patients， you have different pipeline stages that are not the same latency。

 you need to force each stage to be controlled by the same clock。

 meaning you're wasting part of the clock， some pipet are fast but still have to take the same clock cycles and that's internal fragmentation and finally we're going to start with this next time independent operations instructions are not independent of each other so you need to actually control the pipeline so that you detect and resolve inter instructionion dependencies so that you don't get the wrong results。

Okay， this leads to pipeline stalls。Okay， so that brings me to issues in pipeline Z that we're going to cover next week and then from there we'll build a pipeline processor and then an out of order execution process。

 does that sound good？😊，All right， cool， I'll see you next week。3。雨天。哦。So。我。questionSure。

 I think it was by 88 or something Okay， you mentioned with multis that you gain flexibility。 Yes。

 like memory is really large。 Yes， yes。 That's a finite state machine Yes did you mean by this flexibility。

So basically。You can easily add a control signal from memory。

And change your finite state machine easily so that you make a very local modification single cycle。

 if your memory takes longer， your clock cycle needs to increase whereas here your clock cycle doesn need to change this isolated stage will anyway be longer because the clock cycle not necessarily in this particular case。

 the clock cycle， you can keep exactly the same。 except the memory says， okay。

 I'm done at this point。 So you can stay in this stage as long as memory is not without changing your clock cycle。

 but thing don't go to the next stage I have to wait。 Yes， this weight increases my close cycle no。

 no no， it doesn't increase your clock cycle， It takes your program increase your how many cycle you take execute Basically。

 you're in this stage for more cycles now。But your clock cycle， yeah。

 exactly just repeats waiting in that stage essentially Yes yes and you mentioned that if you can if you do pipeline and no pipeline staging you can basically reuse resources like use but if you do pipeline Yes No。

 basically you go back yeah， that's a very good point we're going to get to that that increase your hardware costs so that's a nice thing in a multicycle design。

 but if you want to increase your through， but unfortunately you have to add back all of them。😊。

Can I ask if。

![](img/c38e05d34c60e66bef8947f7d5549fb8_14.png)