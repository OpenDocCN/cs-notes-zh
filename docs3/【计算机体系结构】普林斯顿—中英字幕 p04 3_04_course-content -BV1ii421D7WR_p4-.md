# 【计算机体系结构】普林斯顿—中英字幕 p04 3_04_course-content -BV1ii421D7WR_p4-

![](img/328f35d7fcd079f43ef3dedef10d6be1_0.png)

So course structure， there's going to be recommended readings。

There's going to be in video or in lecture questions that will pop up。

There's going to be several problem sets during the term。

 And these are going to be very useful for review for exam preparation。

 So I'll give you guys a hint right now that if you do the problem sets and actually master the problem sets。

 the exams are going to be relatively easy after that。

We'll probably use pure valuation for grading the problem sets because a lot of them are more open ended problems。

And we're going to have a midterm and a final exam。



![](img/328f35d7fcd079f43ef3dedef10d6be1_2.png)

One， one other thing I wanted to point out is collaboration in this class is encouraged。

 but I want everyone to。Make their own problem sets and midterms and final exams。 So， you know。

 you can discuss the overall generalities of the ideas and the concepts going on。

 But I don't want people discussing the actual。Exam questions in particular。 So， for instance。

 you can discuss the concept if you have some caching question and you want to understand how caches really work。

 You know， discuss the concepts and collaborate on that。

 But don't discuss and collaborate on the actual problem itself on the respective problem sets。

 Minterms and final exams。Okay， so let's talk about the content of this course。

 so we give a very high level motivation， and now we're going to talk about what's inside of this course。

 and I'm going to start off by contrasting it with what you should have already learned。

So in a computer organization class， something like E E 4，75 at Princeton。

 you're going to have learned how to build a basic processor。 So something like we see here。

This was this is actually the risk one processor from Berkeley。

It depending on who you ask either the risk one or the the first MIps chip was sort of the。

 the first academic。Risk， the IBM 801 probably used a lot of those ideas。

 but didn't call it risk before then。🤧But。You know， you， you learned how to design stuff。

 which had about 50000 transistors。 So this entire design here。

 this is a two stage pipeline processor。But things that you should have learned is。Basic cash ideas。

Piplining。So how do you pipeline a processor a little bit about memory systems。

And you should also know sort of how logic works or digital logic works。And then。In this class。

To contrast， instead of learning how to build a very simplistic processor。

We're going to learn how to build。Cutting edge， modern day microprocessors。That's right。

 We're gonna to learn how to build things like this。 Or at least design things like this。

 So this is a core I 7 from Intel。 We， I guess this is original core I 7。

 We're now in the third generation of core I 7s standing in 2012 now。😊，So this is， this is pretty。

 pretty recent。 And to give you an idea to contrast in that previous picture。

 which was 50000 transistors。This design is about 700 million transistors。

So the complexity has gone up here a lot， and。That other processor or the processor that you learned about in your computer organization class。

this little tiny box up here。And have performance。That's sort of equivalent to the size of the little tiny box relative to these these this big processors。

 So we're going learn how to， instead of just building little tiny processors or toy processors。

 we're gonna learn about how to build。Big processors and high performance processors。

So before I go down this list， I want to talk briefly about the course content of E 4。

75 and the two main techniques to make processors go fast。So how do we go about making processors？

Go go fast because people like their computing systems to run， run fast。 Well。

 one is to exploit parallel parallelism。So we're gonna to figure out how to exploit lots of concurrent transistors or concurrent perilism in your program。

 And as you add。More transistors and more perism。 Hopefully。

 it'll make your computing system go faster。 So and there's different techniques on how to go after perism。

 And they're not all explicit perism。 So a lot of them are implicit perilism。 So， for instance。

 instruction level perism is a completely implicit concept。

 The programmer doesn't have to do anything。And then the other main technique we can think about is just to do less work。

So if you're trying to do something and you look at， let's say。

 an assembly line of someone building cars， Well， you can either pipeline and try to get pipeline parallels them in your assembly system。

 or you can try to have multiple people building different cars at the same time。

 So that's all falls into the pering category。 Well。

 something else you can do if you want to make a car faster。

 is you just take out steps or you take out components。 So you do less work。

And one way to do less work is to have fancier software systems so we can have better compilers。

And runtime systems。 And a lot of times， they can remove work。

 So this is like the optimization pass in your compiler。

 If you turn on dash03 or the optimization for GCC。

 it's going to try to remove instructions from your program。

 which are either redundant or not doing any useful work。Another great example of this。

 which people don't really think about as doing less work， but it actually is。

 is something like a cash。In your microprocessor。 So in your cache。

 it puts memory closer to the processor than main memory。Well。

 this is equivalent to if you had a assembly system or a。Production line of cars。 And let's say。

 for every part you had to get， you would to walk down the street three blocks away。

 get the part and bring it close。Well， that's that's pretty slow。

 It's doing a lot of work for each part that you need to go fetch。 But in a cache。

 you can actually put the data very close。 And by doing that or put the parts very close to the similar sorts of ideas here in car assembly is you can put a bin。

 if you will， of all of the parts you need to build the car。 and then just grab out that bin。

 And you're gonna to do less work。 do less walking。 similar sorts of things of caches。

 So these are the the two primary techniques that we're going to apply。

 So now let's dive into the actual technical content。

 of what we're gonna to learn in computer architecture and this computer architecture class。

And we'll categorize them as either doing less work or perilism。So the first。

The the first thing we're going start off in this class talking about is we're going to talk about instruction level perilism。

So we're going to look at superscalear processors， which can execute multiple instructions at the same time。

And it's done implicitly from sequential code。 And we're also going to study very long instruction word processors or what's called V I W processors。

We're going to hint a little bit about pipeline perilism and look at how to build long。

 longish pipeline processors。We'll talk about advanced memory and cache systems。

 So this has no perilism in the word here in the title here。

 So what this is going to be is this is going to be looking at doing less work。

 And we're going to look at how you build memory systems that either bring the data closer or have higher bandwidth and and a lot of the implementation issues in building these advanced memory systems。

Then as the term goes on， we're going to be talking about data level perism。

 So this is more explicit levels of perism。 So these are things like vector computers and graphics processor units or general purpose graphics。

 processor units， G， GPPUs。And at the end of the course， we're going to talk about。Explicit。

 threaded perism。And be talking about multi threading。 How do you build multi processorces systems。

 So this is multiple chip multi processor systems。Multi core and many core systems。

 and how do you interconnect all these different processors？

Roughly the first third of the course is going to be talking about instruction level perism。

There's going to be sort of a middle third， which is going to talk about caches and a little bit about data level perism。

 And then the last third is going to talk about more threaded levels of perilism。

 But that's a very coarse cut of this class。

![](img/328f35d7fcd079f43ef3dedef10d6be1_4.png)

![](img/328f35d7fcd079f43ef3dedef10d6be1_5.png)