# 【计算机体系结构】普林斯顿—中英字幕 p53 52_02_basic-cache-optimizations -BV1ii421D7WR_p53-

![](img/5f3cfac831e8689ff711b1a0a21ead05_0.png)

Okay， welcome to today's E 475。OopsSo today we are going to be moving to a little bit different topic。

 we're going back to one of the topics we talked about at the beginning of class in lecture  three。

 we're going to be talking about caches。And we're actually spending two lectures on caches because they're really important to performance。

In the we'll say in 90s， 80s and 90s， a lot a lot of。

Computer architecture papers and Lala effort were spent trying to use more and more transistors。

 which Moore's law was giving the computer architect and applying them to build either bigger caches。

Fcier caches， more said associative caches。Harder， we'll say ways to think about cache is all for higher performance。

🤧。And we'll be continuing to videotape today's lectures and put them online for everybody。

 And so let's， let's start off and look at what we're doing today。

So we're just off with a little bit of review from。Lecture 3。

 we're going to talk about the three Cs of caches。So。Capacity。Conflict and compulsory misses。

We'll be talking about the basic cache optimizations we had talked about in lecture 3。

 which are mostly kind of make your cash bigger， make your cash more highly associative。

Somehow to reduce these three Cs。 And then we're gonna start talking about much more advanced。Cash。

Organizations and optimizations we can make。So， let's， let's。Briefly talk about it。

 It's sort of a hodgepodge。And this is kind of just the nature of the beast。

 There's lots of little things that sort of add up to make either the cache more effective or integrate the cache into your pipeline more。

 more efficient。And this is only the beginning。 We will have about five or six more topics next time。

 Let's start off looking at what we're going to be talking about today。

 So we're gonna look at how to build， how to pipeline of cache right。

 So one of the things we haven't really thought about when were working on our labs is we do it right to the cache and just sort of magically get stored there But if you actually are trying to build the real cache。

 you have to look at the tag data。And then you have to write the data。

Because you don't want to be writing something into the cache if it's， let's say。

 a different piece of data is in that same location。 So you need to check the tag first。

And we'll talk about some ways to optimize that。We'll talk about a right buffer。

A right buffer is a extra data structure we can put。After our first level of cash。

 which can hold victims。 So a victim is a line or a cash block that is being evicted from the cache。

And if you are going to， let's say。Replace something in the cache。

 You need some place to put the old data and， or the data that was， let's say。

 dirty in the cache from before。And the slow way to do this So things we sort of looked at up to this point is you take that line and you wait for it to go get rid into either memory or the next level of cache。

But if you want to go faster， you can think about trying to store it some way。

 place in some side structure。 And we'll say right to the next level cache or write to the main memory in the background。

We'll talk about multilevel caches。So， multileveal cache is。Meaning you have a level 1， a level 2。

 level 3， maybe a level 4 cache， then main memory。 and why this can improve performance。

We'll talk about victim caches。Victim caches is this idea that can basically increase the associivity of a cash by putting a。

Low associative cash or maybe a direct map cache next to a cache with very high associivity。

 So maybe like a fully associative cache。 And then you use them together to basically implement a pseudo higher associivity cash。

We're going talk today about prefeing， both hardware and software。

 So prefeing is the act of either a piece of hardware or software trying to get data that you need early into your cache。

We'll talk about how to increase the bandwidth your ti your cache。 So up to this point。

 we've looked at doing one memory operation per cycle。Well。

 we built machines that can execute two operations per cycle。 And on your exam。

 you had a machine which could execute three operations per cycle。

 Wouldn't it be great to be able to do three memory operations per cycle versus just three A U operations。

😊，So how do we， how do we go about doing that， Well， we can put multiple ports on this structure。

 but that's not particularly great for performance from， from a clock perspective。

 because it makes the structure very large。So you can start to think about banking。

 which we'll talk about today， is a mechanism to increase the bandwidth。

And then we're going to talk about a bunch of different compiler optimizations or software optimizations that the compiler can do to restructure code to have better cache performance。

So this is just what we're talking about today。Next lecture， we're going continue on this。

 And the main topic of next lecture， as far as the advanced cash optimizations are concerned。

 is we're going be talking about how to build caches， which can。Deal with out of order memory。

Or can deal with the ability to have。Loads and stores which hit in the cache or loads in stores which miss in the cache。

And then you can continue on past that point。So in our sequential machine， up to this point。

 weve all even in our out of order machines we were talking about， when you took a cash miss。

 you basically had to stop the machine。Because you had to wait for the day to come back because you didn't know if the next instruction was going need that data or the next。

 maybe the next load would need that data or something like that。嗯。

So if you want to try to go out of order， you can start thinking about that。

 And that's what the bulk of next lecture will be about is how do you go out of order in your memory system or what this is largely sometimes called is a non blocking cache。

And I should point out that a non blocking cache is actually not just for out of order processors。

This is sometimes good for in order processors。 So if you have an in order processor。

 the instruction sequence is going in order， but you don't want to， let's say。

 wait when you take a cache miss。You could actually have the memory system be out of order with the pipeline be in order。

That's actually a pretty common thing for people to do。Okay， so here。

 here let's go look at our review。We have processor。And in our basic machine。

 we go out to main memory when we want to get data。Main memory is big， it holds everything。

But it can be slow。So we put a cache in front of that。

 which keeps a subset of all the data in the main memory。And it has a faster time。

 and can take something， for instance， like this example here where you go to go access memory。

 and you have to wait for the memory to come back and it can shrink this time。

If we look at the sort of， you know， average memory access。

 it's your hit time plus your miss time times your。Or your miss rate times your miss penalty。

This is just review。Okay， so going back to the three C's。Here， we have a。4 block cash。

So it's a twoA site associative cache。And was look at。What are the major types of。

Misses you can have or the the only types of misses you can have。 You can have a compulsory miss。

So this just means that the first time any any portion of your program has gone to go access the data。

 There's no real way around this。Maybe you can prefetch。But， you know。

 you're not really going to magically be able to get the data in there early unless you have some sort of aggressive prefeting mechanism。

Capacity。So in this cache here， we have four blocks。If you're looping over， let's say。

5 cash blocks worth of data。You're basically not going to be will fit all the data in this cache。

Or a more common case， let's say you have a cache。 That's 8 kb cache。 That's your L1 cache。

 And you're trying to add two arrays where each array is 16 k。 Well， that needs 32 k of data。

 maybe even another 8 k data。 If you're not doing it in place for the result matrix。

And it's just not gonna f your cash。 So you have capacity problems。

 And things are just basically gonna to get continually kicked out of your cache。

Conflict means that you don't actually have。诶。You have enough space in your cache。But。

Too many different loads or stores you're trying to access alias to the same location in your cache。

 So let's say you're trying to loop over 3。Different cashwalks。

Or we're trying to access three different cash box， which all alls to one set in the cache。

And effectively， you can only fit two things， and you're trying to fit three things in， in two spots。

And this is kind of a pigeonhole principle here， comes， comes up and says， no。

 you just can't fit three things in。Two boxes。So we get conflicts。Okay， so still， still review here。

 Let's， let's take a look at。One way to reduce our hit time。Hit time is just。The， the fast case。

 that's actually you find the data in your cache。 This is the good case。 But for hit time。

One way to make it lower， this is actually in nanoseconds is just to have a smaller cache or a simpler cache。

So small， simple caches are in this drawing here。 We have time on the vertical axis。On the X axis。

 we have different cache sizes。And the 16 kb cache is faster than let's say the 256 kb cache。

 So if you make a smaller cache， you can go faster。

 And we see an example of this actually in the pentium 4。

 when we were talking about super pipelining。In the Pentium 4， they had a very small cache。

 And the real reason they did that is because they had such a high clock frequency that they couldn't put anything bigger and still fit it in one clock cycle。

You know， in a perfect world， your clock cycle was slower。

You can try to fit some bigger cache in there。So you can try to reduce the miss rate。

There's a couple different techniques on how to reduce the mis rate。 And this is。

 there's advanced techniques， which we'll be talking about later。

 But one of the basic ones is to change the block size。As you make the block size larger。

You're going to be pulling in more data。So you'll get spatial locality。 and hopefully。

You'll be pulling in data that you actually need。So the you know。

The positives of this is you're really gonna have less tag overhead。 if you have a larger。

Block size or cache line size。Because for the same amount of data， let's say you had a 64 B。

Line versus 128 byte line。You're going to have half as much tag。

Sort of cost or area dedicated to the tags。And， and usually as you go to larger block sizes。

 this is good for the farther out layers of your cache because you can basically burst more data in。

So if you look at something like a DDR2 memory or DDR 3 memories。

 this is the traditional D Ram technologies that we're using today。

They want to actually their block size。 their line size is very， very long。

 sort of thousands of bits。And if you have a longer block size。

 you can use all those bits and pull them all into your cash in one big chunk。

 and you can use wider buses。嗯。Downside。You can waste bandwidth if you have a very large block and you don't actually use all the data in the block。

 Let's say you use one B out of your。I don know，256 B cash。

You're just pulling in all this data and you're wasting a lot of off chip bandwidth for no real good reason。

And if you have fewer blocks。You're gonna have less locations to put data for a fixed size cache。

So you might actually increase your conflict rate。So this chart here， what we're trying to show。

 this is from your book。We're plotting the block size。🤢，Versus。The miss rate。

And you want the lowest miss rate possible。So if we start here with a 16 by。Block or 16 by cash size。

Cash line， as you increase it， the the mis rate actually goes down。But at some point。

 you end up wasting a lot of bandwidth。Because you don't have enough。 the， the program will say。

 does not have enough。Sppatial locality。 So you actually just end up pulling in more data than you need。

You also could potentially have more conflicts。 So it starts to go up。 So there's of a minimum here。

 Traditionally， people have thought about this is actually increasing block size usually increases your performance for most applications。

 But that's up to a limit。And the reason why people traditionally thought this is cache sizes used to be sort of smaller。

 or mean， cache block sizes or line sizes used to be smaller。

 And they sort of got start getting bigger。And then people really weren't looking way out here。

But now that we look at way out here， it does， It does get worse for some applications as you get farther out。

Okay， so another way， just the basic ways we can reduce miss rate is we just have a bigger cache。

This one's great。 bigger cash， lower miss rate。Youve got to pay area for this。And potentially。

 it takes longer to access this larger cache， as we had seen in the first。Graph that we showed today。

I'm not going to really talk about this， but。EPical rule thumb。Cash size is doubled。

 Your miss rate usually goes down by the square root of 2。 It's just empirical people found。

But good rule thumb to know。Same graph。Tells a different story。If you go to a higher associivity。

Your miss rate goes down。So if we have a direct mapped cache and we go to a two way set associative cache。

The mis rate goes down。 and the traditional sort of rule thumb about this is if you have a direct mapped cache of size N。

It has roughly the same mis rate as a。Two ways that associative cash。 That is half the size。

AndYou might say， wow， that's， that's pretty amazing。

 So can I just continually apply that over and over again， It doesn't quite work。

It also gets very hard to actually build very highly associative caches。Becauseuse your。

 your your tag check becomes pretty hard because you have to check against all different places in the cache。

 it could be in parallel。 and that becomes hard。

![](img/5f3cfac831e8689ff711b1a0a21ead05_2.png)

![](img/5f3cfac831e8689ff711b1a0a21ead05_3.png)