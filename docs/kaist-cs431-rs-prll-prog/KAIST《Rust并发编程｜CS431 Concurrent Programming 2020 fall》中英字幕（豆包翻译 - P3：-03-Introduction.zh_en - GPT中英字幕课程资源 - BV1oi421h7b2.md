# KAIST《Rust并发编程｜CS431 Concurrent Programming 2020 fall》中英字幕（豆包翻译 - P3：-03-Introduction.zh_en - GPT中英字幕课程资源 - BV1oi421h7b2

Okay， let's start studying concurency。

![](img/f48eab41c44cf80c8514de8e49e9215a_1.png)

First things first， let's look at some logistics。 So here is the homeage。

 Gith dot com slash k dash C P slash this。And you， I。

 I think that you should read this poetry very carefully。 It contains a read me。

 and it contains a lot of information。 you should know to finish dis course。

All the announcements and questions should be in the issue Checker。

 so please watch the repository so that all the new announcements and questions will be automatically delivered to your email account。

There will be no official office hours and we require you to ask questions in the tracker first。

 so you go to the repory and then see what's going on there and if you have any questions please create a new issue。

And also for each session we require you to submit a quiz answers so that we can be quite sure that you actually saw the video。

 so I'm going to ask a few questions on the videos that is corresponding to each session and you're going to submit the answers to this site Xjikac。

 KR so your account has been already created and please go to the repitory and read me and the announcements。

Also， I want you to sign the honor code， which is pretty standard among the School of Computing。

 it is basically mandating you to stick to the integrity role of the academia。

 so it is fairly standard， so please read it and please assign the honor code and in this URL。Okay。

 so basically I want you to read the homepage carefully and do some things for our attendance in our code。

And next， I'm going to explain a little bit about grading。And for this course。

 homework will be very important and it will constitute about 60% of the entire credits。

 So if you miss homework， so you will not get a good grade。 so please do the homework on time。

And furthermore， we will have midterm and final exams。

 but due to the CoVID-19 situation where I Im still not sure whether we are going to actually take midterm or final exams。

 so the grading scheme may change a little bit depending on the CoVID 19 situations。Also。

 I'm going to look at some attendance results， so for each session I said that you should go to decide site and submit the quiz answers and if you attended most of the courses or you answered most of the quizzes for each session。

 then you're good， but if you miss a lot of quizzes， then itll be a problem。

 so Im I' not still decided whether how to。Apply this attendance integrating。

 but please please watch the videos and go to this site and submit the quiz answers as much as possible。

Okay， here are some logistics and if you have any questions。

 go to the home page and read the read me carefully and if you still have more questions。

 please ask questions in the issue checker。And let me start with the the introduction and the concurrency。



![](img/f48eab41c44cf80c8514de8e49e9215a_3.png)

So it is one of the famous scene in in this 21st century。Pau match with Alphago and Iad all。

 and it is starting is probably the beginning of the first session。

 So he's going to allay the stone and here。And as if all of you know， I forgot one，4 by one。

 It is a one sided。Win over the Grandmaster Iadel。 So everyone was shot。Everyone。

 most of the people are thought that is it all win。Because AI is soed at the time。

 and people thought that Iadel is a really great great grandmothermaster of Pau。

 and he cannot be beatated。And I also thought that Iad all will win because I know that AI will do something good。

 but I still。Thought that Ipago would not be that good。But。

As contrary to what most of the people thought， Ali Pago actually won。For buy one。

So so I was quite shocked， so。In 2016， I was a graduate student and I watched all the matches in the laboratory and realized that。

 oh。A new word or no new era has come。 AI is really something。

 It will do something very impressive to the human history and beating Li at all is one of the sign of that。

 And actually we are going to do very interesting things out of AI。As it turns out。

 AI applications are widespread nowadays and it is actually very good in some cases， and。

 for example， the recent GP3 model really understand the languages very quite well and it can be used to models。

 some applications that should understand the languages， so on and on and on。Most of the。I mean。

 there are a lot of AI applications that is popping up these days， and they change our lives。

And behind the scenes of this match between Alphago and Iadel。There was some machines。A big。

 big machines that is consisting of a lot of computing units。

 So you can see that a lot of parents are repeating here， right。

 So the same rack is the copy and pasted on and on and on。And inside this slack。

 also the same unit is copy and pasted on and on and on。

 and they are connected with an networking solutions， basically。

And the reason why there are a lot of redundancies or a lot of duplications of this the resources is that we in order to be is at all the alphaphago need to do a lot of parallel searches。

 basically and for parallel searches， we these parallel machines will be very， very efficient。

 we just distribute the search job across this a lot of machines， a lot of the same machines。

 basically， and itlig in the。The outcome much， about 100 times faster。

 if you have 100 units of computation。So the version the aphago version that beat it Iadl was also a massively parallel machine and four years later now the machine behind Alphago which is a TPU or tensor processing unit。

 it is becoming more and more parallel and more and more dense these days。

 so behind the scene of the era of AI， it is also the era of a parallel machines。

Paralyism everywhere。Okay， so now now is the era of parallelism。So as I said。

 we need more and more competitions in order to prepare for the era of AI and Io T， etctera， et cea。

So the trend is that computers are becoming more and more parallel here parallel means a lot of things。

 so we have parallel resources basically， and these resources can be CPUUs， memories。

 IO resources or TUs GPUs or neuralprocess units or NPUs or other FGAs or other kinds of resources。

 all those kinds of resources are parallel， and theyre parallelly deployed。

So the reason why we need more parallelism in response to the more computation needs is basically two。

The first reason is popping up about at 2005， which is the end of what is called Denor scaling。

So basically， what is meant by Den art scaling is that we cannot increase the number of transistors for a fixed area of core。

AndW whichch means that we cannot， we cannot。Increase the number of transistors for a single computing unit in in。

In a fixed area。 So the reason is that the power consumption is constantly going up in Ar so we cannot simply simply put more transistence inside the same core。

 basically computing units。 and that is the reason why this end of the scaling is。I mean。

 we are fighting with the end of the scaling with introducing multi core systems。

So we are basically introducing more and more cores basically， so at the beginning。

 there were two cores instead of designing 5 gigahHtz CPUUs。

 we developed dualco systems and then four core systems a core systems and nowadays in 2020。

 even there are 16 core CPUUs in desktop CPUs。And furthermore there there are even 64 core CPUs of server grade CPUs。

 and as far as I know， a CPUus with 118 cores is being designed and it will be delivered to the customers next year。

So a lot of cores， a lot of denities are growing up。In response to the end of the art scaling。

 you cannot just increase the gigahertz of the course。

 You need to put more cores in order to utilize the number of transistors。Okay。

 so about 15 years we have been so happy， so even though there are scaling ended。

 we can benefit from multi core systems and it is basically a pair resources of the course and we were good。

And these days， we are facing a little different difficulties， which is the end of more slow。

So it is basically saying that we cannot just increase the number of transistors for a fixed area。

So you I mean， the silicons or CPU or something like some semiconductors。

Are designed in a wafer that is basically round。round materials that is consisting of the silicon basically。

 and we are going to just draw some picture of the circuits to get CPUs and theM controllers and other semiconductors。

So one of the main trend in this silicon industry is that we can constantly increase the number of transistors that can be put in us a given amount of area。

So that's the reason why we by for example， about two or three years later。

 we can get higher performance CPU with almost the same price。

 that reason that the reason is that we can just increase the number of transistors constantly。But。

We are facing almost the end of this most law。So even though the lithography is becoming finer and finer。

 we cannot guarantee for， we cannot say for sure that the trend will continue in the future。 So the。

Number of transistors that can be put into a fixed area are not no， no more increasing。

 like a rocket。 It is increasing。But at a very， very slow pace。So in order to deal with this problem。

 one of the main strategies is introducing what is called accelerators。

 which are specialized and extremely parallel hardware so CPUs are very general purposes so it can do almost everything every computation we want to do but accelerators are different。

 they do small subset of operations but with a very higher efficiency。

 so it is specialized to specific workloads， but but。Thanks to that。

 it can be extremely parallel and extremely efficient hardwareddle there。

So GPUs are accelerators and it is the most important types of accelerators。

 first it was for graphics， obviously it is GPU graphics processing units。

 but these days GPUs are also specialized for AI applications and vision applications and other kinds of even data analysis。

 applications， etc。And TPUs that was behind the scene of this Alphago was also a famous accelerator。

 and a lot of startups are trying to develop accelerators that is called NPUs on neural processingcess units that are more specialized to AI applications。

So these two trends， let's see these two trends， so the first trends。

 the end of the scalinging forces us to think about multicho systems。AndBa， app perciious。

And the second trend forces us to think of parallel resources of heterogeneous resources。

 not only CPs， but also GPSUs， NPs and TUs， and even SSDs， FPGs， etcter， etc。

So we are having abundance of parallel and heterogeneous resources these days。

 and in the future the trend will continue。More and more parallelism will be introduced。

 More and more heterogeneity will be introduced to achieve higher performance to meet the human demands for more and more computations。

Now， the question is that， okay， now we have power resources。That's very good。

 We have parallelel machines， perroll CPUUs， pay Rams， parallelel SSDs， Very good。

 But the question is how to coordinate those parallel resources that is coexisting in order to achieve higher performance。

We need to somehow coordinate those power resources to collaborate rather than compete to achieve a single or unified goal of computing that is what is expected from our human demands。

 for example， we want to compute AI graph using power resources。

 and they need to somehow coordinate in order to achieve that goal。



![](img/f48eab41c44cf80c8514de8e49e9215a_5.png)

How to do that。So usually it is， I mean， it is widely largelyly known that it is a little bit difficult。

 it is a little bit difficult to achieve high performance other power computing。In theory。

 paracomputing should work like this。 So there are parallel dogs。 Basically。

 there are many dogs here， and they are eating the eating the， the。What is this adding the。

Biscuits at the same time。 In theory， there are， they are working in parallelil。



![](img/f48eab41c44cf80c8514de8e49e9215a_7.png)

But however， usually it is。Like this， I mean， they are competing for the same resources。

And the three dogs here are competing for the same resources。

 and this resource is even not utilized at all， and they are doing well， but problems， I mean。

 performance problems occur when some resources are contended or some resources are not utilized at all。

 blah， blah。So in theory， we want this， but most of the time we cannot achieve this。

 we can achieve only the kind of chaos out of parallel resources。So let me explain。HowWhy。

 why this happens and how to synchronize those power resources safely and efficiently。Okay。

 so let me introduce concurrency here， so parallelism is basically defined as multiple resources。

 if there are many resources， we can say that out there is a parallelism between these two resources or these many resources。

And concurrency is about shared me states， and it is important。

 it is defined as shared mineral states or shared me resources， basically。So for example， CP。

 GPS memory， they are all shared among multiple processes。

And a server is shared among multiple processes or multiple virtual machines。

 database is shared with multiple connections， even their centers is shared among multiple users。

 basically。And all these resources are meable。 Obviously， CPU is meable。

 They can change their registered values constantly， and databases can be changed constantly。

 etctera， etc。So parallelism and concuracy is defined this way。

 multiple resources and shared real resources。The problem is that share renewable resources is the key to utilizing multiple resources。

So you can think that parallelism without concurrency is not that interesting， for example。

 if resources are shared， but it is immutable， then the resources are constants and there is no difficult things that arises or theres no interesting things can arise。

They are all constant。 They are They are defined at the beginning， and it cannot be changed。

 So it is not that interesting in terms of the computations， basically。On the other hand。

 exclusive me resources are sequential and there is no parallelism that is involved with this exclusive or resources。

 we cannot share this resources so there is no way to no way to increase the performance using these resources because it is specifically owned by a single agent so it cannot be using parallel。

So in order to achieve high performance via parallelism， we really need to deal with concurrency。

 deal with shared mirrores， how to safely and efficiently use this concurrent shared mirror resources is the key to achieving high performance of out of parallelism。

Okay， and so we've so far we discussed that concurency is fundamentally about shared meable resources。

And there is a trivial way to deal with accuracy。 So here stage are known to be difficult and they are known to be all the sources of all the difficulty in the programming。

But there is a trivial way to deal with concurrency。

 so it is basically at any moment don't share any resources so that means that at any moment if we can say that at any moment a resource is owned by or used by only a single agent。

 then we can say that even though resource can be shared。

 but at any moment the resource is exclusively owned by an agent。

 so there is no difficulty arising from the concurrency。

It is nominally parallel because many agents can access this resource。

 but it is temporarily aar because at any moment it is exclusively or owned by a single agent without a pay emphasis。

It is obviously safe because there is no difficulty or no problems arising from these shared mirror accesses。

 but usually it is inefficient because at any moment a research cannot be shared at all it can be I mean it can be time multipleed。

 but it cannot be used at the same time so that's the reason why it can be inefficient。

On the other hand， what we really want to achieve is a scalable concurrency is it actually accessing resources at the same time。

 so for example， we want to design a jobb queue， a concurrent job queue supporting， for example。

 1 million operations for a second。So。In the real world。

 such systems are deployed in the name of for example， redies for a Rait MQ blah， blah。

 so this Rait MQ for example， is a job queue， and if a web server is wanting to request for a job to be done。

 it just throws the job to the job queue， and this job queue is constantly pulled by workers and a worker is getting a job out of this queue and executing the job。

And we have a lot of concretecurrent connections at the same time。

 such as J queue must be as fast and as fast as possible。

 That's the reason why we want the concurrent job queues us can support for example。

1 million operations per second。That is usually the， I mean。

 this is similar to the number of concurrent connections that can be handled by a single server in these days。

So for this scalable concurrency， multiple agents actually can access the same job queue at the same time。

 so in that sense， it is truly shared me resources。It is shared among， for example，1 million handles。

 and it is mutable because jobs can be added or removed from the queue。

And in order to support this kind of actually scalable concurency， though。

The problem is that it is usually difficult to reason about it is definitely efficient。

 as I said it can support many many operations per second。

 but usually this kind of scalable concurrency is a little bit difficult to reason about。

 especially for their safety and correctness， how to ensure the correctness of the queue。

 which means it actually acts like a queue。In the presence of shared meable accesses。

 so it is difficult usually。

![](img/f48eab41c44cf80c8514de8e49e9215a_9.png)

So let me explain why it is difficult， so the essence of this difficulty there is non determinism。

So concurrency is difficult because it introduces combinatorarily explosive and determinism。

So commercially explosive basically means lots of lots of lots of nondeminism。

 so we don't need to worry about this difficult words。

So the first source of Ndeminism is usually called interling。

So let's say that there is a two stresss。 This is x equals1 is a thread。

 and is x equals 2 is also a thread。 Let's assume that。

And the problem is that depending on the order of the execution of this press。

 the end memory is one or two， depending on the order of the execution。

If x equals 1 is executed before x equals 2， then the n memory should be x equals 2。

On the other hand， if x equals 2 is executed before this thread x equals 1。

 the n memory should be x equals 1。So these kind of possibilities are are I mean。

 this kind of the number of inter livings are basically。I mean。

 it corresponds to the factorial of the number of instructions， basically。

 that is combinatorarily explosive， basically。The second so which means that if there are a lot of threats or if there are a lot of instructions inside a single stress。

 then the number of possibilities of interlavingings are going very high。

 so in this example we only have two inter livingings。

 but if we have many threats and many instructions。

 it will easily go higher than billions and billions and zillllions of cases。

And the second sources of Ndeterminism is optimization by hardware and compiler。For example。

 let's still get this code。There are two thrusts， and let's assume that this A and B。

 which is in the small case letters are registers， and this X and Y。

 which are B case letters are shared memory locations。

And let's assume that accent y equals to0 at the beginning of the execution。And in the left， right。

The this thread is writing want to ask and then reading from y。On the other hand。

 on the right thread， I rise1 to y and then raise from x。And the question here is that。

 is it possible to observe a equals B equals0 in the model hardware？So surprisingly， it is okay。

 it is obable in actual hardware。Even though you can nily think that。Either。

X equals 1 or y equals 1 should be executed first， and if x equals 1 is executed first。

 then b should be 1。In other case， y equals 1 should be executed first。

 then this should be reading one。So you maynively think that。

But this reasoning is broken in the presence of optimizations。And in particular。

 if reoddering is happening in the left red or right thread。

 x equals because equal 0 can be possible。So let's say that hardware or compiler is smart enough to deduce that two instructions in the lecture are not dependent on each other。

So in May execute the second instruction first， reading from Y first。In the same reason。

 the compiler word hardware may be that these three instructions are independent with each other。

 so maybe the thread is executing the read from x first before writing 1 to y。So if it is the case。

 it can be the case that A and B are0 at the same time because they are reordered and they are executedd before the O rightss。

So this kind of optimization and this kind of additional nondeminism is happening。

 it's really happening in the hardware and it's really happening in the compilers。

 so we need to somehow deal with this and we need to somehow learn how to defeat this kind of andeminism。

So this is basically the topic of this course。 The entire course is devotedive to understanding concurr and understanding the nonism that is arising from concurrency。

 and furthermore， we want to tame。This non determinism to make sure that this nondeminism is actually beneficial for our purposes。



![](img/f48eab41c44cf80c8514de8e49e9215a_11.png)

So there are basically two approaches to taing nondeminism。The， the first approach is about API。

 So we are going to enclose theism within a safe API。

So let's think of a lock or conditional variable or threads or other kinds of abstractions that is present in the operating systemss implementations and other kinds of systems programming。

For example， the lock， it has a very simple API。You can acquire a lock。

 You can release a lock and the so。 and there is no things like interlaving of instructions。

 interlaving of instruction is inside the implementation of the lockx。

 It is no longer of our interest。 what is needed to use a lock is the specifications of the lock。

 the specification of the lock is that if， I mean， two stress cannot acquire a lock at the same time。

 So only a lock is held by a single agent。 That is the specification of a lock。

Conditional variable has its own API and other kinds of concurrent objects。

 like concurrent data structures or concurrent garbage collectors。 They all have safe API。

 So one needs to know the safe API and how to use it safely instead of understanding all the implementation details of the the APIs。

 So this the。I mean， all the implementation details of the concurrent objects。

 that's basically one of the most important approaches to tameine nondeminism。

Once thedeomminism is enclosed within CP API， we can just forget about the implementations。

 We can use the concretecurren objects， using only the APIs。So。Let think of I another example。

 let think of a concurrent stack， that is a stack， but that is concurrent so that multiple structures can access the stack at the same time。

 So it is such a stack。So the Con stack API should hide to lowdeomminism， so for example。

 inside the implementation of the stack and it will consist a lot of instructions， a lot of。

 for example， x86 instructions and they can be reordered and they can be interlied。

But we no longer are interested in such low level andeomminism。 So because API will be。

 it will enclose the such low level things and。On the other end。

 we only want to know the high level nondeminisms that is exposed by the API。For example。

 if two stress are trying to push values to the same concurrent stack。

 then there will be interlaving of the operations， either a thread A is pushing a value first or a thread B is pushing a value first so but it is an intended parallelism。

 I mean intended nondeterminism， we want to enjoy the performance benefits that is allowed by the kind of nondeterminism so that's the reason why we usually want to expose expose a high level nondeterminism to the programmers。

Okay， that is basically first to the first approach to taming nondeminism。

And the second approach to taming Nterminism is about implementation。Okay。If we know safe API。

 we can just ignore the implementations。But someone needs to implement in order to satisfy the safe API。

And what should they do for actually implementing such concurrent objects？

And the key idea here or key approaches here is that we only use a well studies synchronous patterns instead of using arbitrary code。

 we just write down a very well established synchronous patterns。So， for example。

 locks are using what is called release power synchronization and some。What is called theQ。

 conteling De the data structures is using what is called fence synchronization。

So there are a few synchronization patterns that can be combined in order to achieve a necessary or desired coordination of the desired synchronization。

 and we are going to learn such synchronization patterns that will be necessary in the。

What is happy or what is fortunate about this is that we only need to know about two or three synchronian patterns。

 so that's all， we don't need to learn thousands of synchronian patterns because there are only a few synchronian patterns。

So in this course we are going to learn these two aspects。

 what is the safe API of existing concurion library， for example。

 locks and conditional variables and cond stacks and concurrend work selling queuees， bh blah， blah。

And also， we are going to learn the implementation of concurrent libraries。

 how to implement such locks。How to implement conditional variables。

 how to implement concurrent taxing， queuees， etc， or how to implement concurrent garbage collectors that is the main topic of this course basically。

Okay， so I said that we are going to study API implementation of concurrent libraries。

 and I observed that there are two layers of concurrency。

 basically one is easy and the other is difficult。One is the easy one is usually called lock based concurrency。

 which I called what trivia currency in the previous slide。

And that means that luck basically mandates that at a moment a resource should be owned by a single agent。

 so it removes all the parallelism for a single resources but it may be the case that we have multiple resources that is protected by their own locks and in that case multiple resources can be accessed at the same time。

It is the case that。Lock based concurr removes parallelism， but for some cases。

 it it may be sufficient for our performance target。

that's the reason why we are learning luck based easy concurrency。So we are going to learn scratch。

 loss conditional variables or other things that is relevant to lock based concurrency。

And the benefit of this is that it is very simple because we remove another parallelism。

 we no longer need to think about nondeterminism at all because there is no such nondeterminism。

 It is very simple。But because we removed a lot of nondeterminism。

 maybe it is the case that it has a very low scalability， so in maybe the case。

 if we require a luck for a lot a big resource， so if we protect a big resource with a luck。

 then it may be the case that a big resource can be assessed only at one at a time。

So that's the reason why we may proceed to the lock free concurrency or difficult concurrency。

 or during concurrency that is usually called by some authors in the research community。

And the La concurrency is not going to use logs basically。

 and instead it will allow concurrent axis at the same time。

 actually allowing concurrent axis to the same object at the same time。

So in order to tame the andeterminism that is arising from this African currency。

 we will learn theory and tools and practice of this African currency。

And the theory will be thematics and regional principles that is characterizing the nondeter museum。

 basically。And tools wheel based inronation patterns， the building blocks for La currency。As I said。

 there are only a few synroian patterns。 that is a good thing。

 So we need to only learn a few synroous patterns。And also。

 we will learn a the practice of luxury free concur。

 The API and implementation of actual luxury free objects like data structures like stacks and queuees and list。

 etctera etc。So we are going to learn such things。And furthermore。

 a little bit more about practices that we're going to learn a little bit about garbage collect。

 basically。

![](img/f48eab41c44cf80c8514de8e49e9215a_13.png)

Okay， so far is the introduction of what is going to be learned during this course that to summarize we are going to learn the API implementation of concurrent libraries and this concurrent libraries can be usually classified into two categories。

 easy1 and the difficult one， so we are going to deal with both of them we are going to deal with easy ones。

 API and implementation of the E ones and API implementation of the difficult ones at the same time。

Here are a few general advices for Kcare programming that can be applied to most of the situations when you're going to do KAR programs。

 so if this course is too long just memorize these things。

And the first advice is always start with a easy concurrency。

 always use lux and always protect your resources with lux when you are going to deal with shared material states at the beginning。

And only when it is a bottleck and only when the lux are introduce a lot of bottles here， you。

 you should go to the difficult concur。If easy concurrency is just enough。

 just use it because it is because。It is much simpler and easier to reason about。

There is a very famous wording by by Kauth， which is premature optimization is the rootable evil。

 So don't， don't optimize things prematurely。 Just start with easyconcurrency。

The second advice is about difficult concur， and it is actually not that difficult once you understand the theory。

😊，So if you understand the fundamentals and if you understand the theory。

 and applying it to the difficult concurrency is systematic。

 you don't need to worry about the magical things。So that's the reason why if you understand the theory。

 it is no longer a very much difficult。But the other side of the story is that I have to confess that understanding the theory may be a little bit difficult and it requires some discipline study。

 which is the aim of this courses。And the key here key of the difficult concurrency is taming the right amount of nondeomminism。

 you should not remove too much nonminism because it will introduce scalability problem。

 but at the same time you should not remove too less nondeminism because it will introduce correctness problems so in order to achieve scalability and correctness at the same time。

 you need to remove or tame the right amount of nondeminism。

 So thats the key criteria for this difficult concurrency。

The third aspect of this advice is that probably your code for your con code is not that big。

Because most of the things can be done in a sequential way。

 so concurrency is usually done for a very highlycur highly access code resources。

 and is usually small and it is usually simple。So there will be not so much to code。

 but you have to know that there is much to the buck。

So it is really easy to introduce about inside your code in concurrent programs。

 It is much more easier than sequential programs that that's the reason why debunkgging is most important。

啊。Activities in concurren programming。But fortunately。

 we have a lot of tools that support us in debugging， sanitizers， stress testers。

 assertions and line by line debuggings， etc cetera。 So you're going to。

Learn how to use those tools in debugging your currentcur programs。AndFurthermoremore。

 mathematical and PR thinking helps a lot in debugging such things because they mandates us to think about or pntically think about the safety of the programs。

In the mind of proving the correctness of a program， we need to deal with all the corner cases。

 and we need to think of all the corner cases in the course。

 So that's the reason why it will help us to debunk the code。

So so I imagine that it is dis courses for senior and most of you already do courses in PL。

 but it is not required for this course， but it is much easier for you to already take a appealL for taking this course。

Okay， this is pretty much end of this talk and this is pretty much the end of the first day。

 and I hope you will continue to register this course so that we will learn concurrency in the remaining of this semester。

And I hope this course will be very fun and also deep at the same time。

