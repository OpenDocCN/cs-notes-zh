# CMU《高级数据库系统｜CMU Advanced Database Systems (15-721 Spring 2024)》中英字幕（豆包翻译） p10 -10-S2024 #09 - Parallel Hash Join Algorithms .zh_en -BV1HZ421N7WZ_p10-

🎼Carnegie Mellon University's advanced database systems course is filmed in front of a live studio audience。

😊。

![](img/98e2fba6076922a1427cab8660166d56_1.png)

🎼。🎼あでち。🎼Okay。So a lot to cover hash joins， we probably could have done this in two lectures。

 but'll try to cram through as much as we can where we picked off last class was we showed how to take a query plan。

 identify what data it's going to access， break that data up into smaller units called morels。

 it's one approach we looked at and then have them pull from some kind of global queue and we said that the pullbasedase approach was going be superior than a pushbased approach for scheduling and that morsels is in by itself the techniques of like the low low implementation of it made different one to the next but the idea that I'm going to break up large chunks of data into smaller parts that's not unique to the morsel's idea that's an old idea in parallel systems or parallel data systems。



![](img/98e2fba6076922a1427cab8660166d56_3.png)

So， and as I said at the end， that the little bit ran out of time， basically。

All the papers we discussed last class were all about single node database systems。

 but when you go distributed， it's more or less the same thing is now you may need to account for network latency in between nodes rather than just assume everythings in the same box and whether or not you want to have your schedule plan individual tasks or course in each single node where they use sort of hierarchical approach or say here's the bunch of tasks I want to run。

 send that to a node and the decides how to divide up different workers there's different approaches there's pros and con to both of them。

 but we were're not going to really cover those。The one thing that we ran out of class ran of time I briefly discussed because this is going to come up when we start talking about real world implementations of systems is the notion between dynamic scaling and work steal way to allow the system to sort of rebalance itself and improve performance rather than getting stuck behind stragglers and these are not mutual exclusive。

 like snowflake is listening to both these， snowflake will do both of these some systems will do if it's a cloud based system you can do the dynamic scaling because you have additional resources。

 if you're stuck to a single notebook box， the way the hyper was， you cannot。

so dynamics scalinging basically says that you recognize that before before a query starts running that I maybe have more tasks than I have workers for。

 And I know that can make things slower for me。 So therefore。

 maybe I want to temporarily include some additional resources to scale out horizontally add more workers to allow that process that query So that runs more quickly。

 And so we'll see this in snowflake， They'll have something called flexible compute where they basically have this。

😊，Side cluster available to all customers for additional workers and that you can occasionally borrow some without paying extra and make your queries written run a little bit faster。

😡，Again， we can't do that， it's hard to do that on Prem because you have the provision hardware ahead of time。

 but in the cloud， everything's elastic that makes it easier。And then work dealing again。

 we covered last time， basically says you allow a worker to take work from another peer。

And then whether or not you want to have that the worker that's stealing the steeler。

 whether they should go move data from the CLE， the worker they're stealing from。

 get the data from them or go back to the distributed storage， S3 or whatever。

 again depends on the implementation。 snowfl is going to always go back to the remote storage because they don't want to slow down the worker that is that's the strraggr。

 but in case the hyper we saw that it'll go get it directly from the worker's CPU In that case because everything was in memory。

Again， these are just additional design decisions we can account for when we build a larger system。

Al right， so today I want to focus on joins， right， because joins are the most important， one or D。

 if not。One of the most or the most important operator we would have in a relational database system。

 And we're really going to be focused on how we do this in parallel。 And again。

 we're going to focus on a single node system because we're going to assume that something else above us has already moved the data to where we needed to be And again。

 that's not interesting。 That just says， okay， this needs the data to go here and then something。

 something moves that。But we really care about is when we get all the data on a single node。

 assuming that everything fits in memory。How can we run as fast as possible？Right。So again。

 we'll talk about the background of what the different sort of parallel join algorithms or high performance join algorithms look like for the less。

30，40 50 years then we'll talk about the basic building blocks to do a parallel hash join。

 then we'll talk about different hash functions， the hashing schemes and the high level overview of of the evaluation for the paper you guys read which I understand the paper was a bit inscrutable for some of you because there's some background material you maybe not have I'll try to ask questions I'll try to cover that as we go along。

All right， so parallel algorithms， again， the basic idea is that we want to be able to take two relations to join together across multiple workers at the same time to speed things up。

In the Android class， we didn't discuss threads or workers when we did joins。 we just said。

 here's the join algorithm， and then we computed the complexity of it based on the number of pages we had to read and write from disk。

Get as I said， if we assume now everything resides in memory and now we have additional cores because this is 721。

 not 445，625， we have all these additional resources for us。

 how can we get this to run as fast as possible？So again。

 where we focused on binary joins or just taking two relations。

 next class we'll talk about multiway joins or three way joins， three or more。

 and the idea is that can you join multiple tables exactly at the same time？

And we'll see an algorithm to do that。 Most of times， though for most queries。

 you want to do a binary join， that's going to be faster than the multiway join。

 plus it's for graph workloads， the multiway join will be better。

So the two main approaches that we're going to care about are hash joint and Smer's join。

 I'm not teaching Sortmer's join this year just because most systems aren't going to implement it and 9 times out of 10 or 99 times out of 100。

 you're going to want the hash join。That's always to me faster。

 if the things already sorted in the way you want on the join key， then yeah。

 you could do sortmers join and the paper you've read about talk about some ways to speed that up using SIdy and other things。

 but for now， I don't think it's necessary to know that。

 I'd rather focus on how can we do has join faster。

We're also not going to talk about nesta loop joins because this is almost always the worst thing to possibly do in。

 in an overlap system。 You would only do this if you know， like the table has like 10 tus。

And so again， hash only is almost always going to be preferable to everything else。

So and so the goal of today is again how to max my parallelism。

 and part of that is going to be being aware of what the CPU wants from us。

 being aware of what the threads are reading and writing to to avoid synchronization costs。

 and understanding the penalties of reading data that's in a different human region or maybe that's unallineigned。

😡，So it didn't always used to be that hash join was considered to be superior to everything else。

 this is sort of a classic debate in databases where it's gone back and forth between whether sorting as faster for joins versus hashing and back in the 1970s in the first database systems that were running on very。

 very primitive early computers。😡，You know， the the the handle tables that were larger than memory。

 the grace hash join or had had a spill joins to disk wasn't invented yet。 so。

 but they had an external merge sort algorithm。 So they said， okay， well。

 if I need to join two tables that are really big， bigger the amount of memory I have again。

 think of like megabytes not， you know， not terabytes of memory。 or kilobytes in some cases。

That they had a way to then be able to do external a merge sort so that they could write this sort of data out the disk。

 bring them in as partitions or chunks， and then do the merge pass to join them。In the 1980s。

 the hardware got better and then there was this project out of Japan called the Grace database machine。

 and so they invented the Grace hash join， which is a precursor to the partition join we're talking about today and they had the ability then to be able to spill the buckets to disk recursively to bring things up to smaller chunks that could fit in memory。

There was another movement called database Machines， which the Grace Project was part of。

 and that was like specialized hardware that had custom silicon just to do hash joints。

So they had ways of speed up hash joints back in the day。

In the 1990s Ernoli paper came out from Gerts Gry， the guy that invented a volcano。

 the volcano model， iterator model， the guy that invented the exchange operator。

 the guy that invented cascades， we'll cover later on。

 he had a paper that basically said these two algorithms were equivalent given the hardware that was available at the time。

But since the 2000， since the turn of the century， hashing has been shown to be preferable so the question is always now is it better to partition or not。

 and in the paper you guys read I think they show partitioning is going to be faster。

 there's another paper from other Germans from the hyper Germanmans of the Umra Germans that said yes。

 partitioning is faster， but it's really hard to get it right so most of the times to better off not partitioning。

Sorry， the partitioning is faster， but you're better off not partitioning because it can cover it's good enough for most things。

Right。So this is what we're going to focus on in today。 We're going to ignore certain's join。

 and we're really going to discuss the partition versus not partition approaches in the modern variance of these things。

For Sertmerge join the paper that they I think the M Sermerge join paper that they cite the paper you guys read。

 that's from Intel actually I'll start their from Intel and Oracle from the 2009 that basically said hey。

 SertMge will be better than hash joined， if you have Cindy registers that 512 bits because again。

 this is 2009 before AVX 512 came along but now if the AVX 512 is around and hashing I think is still considered preferable。

Now， again， if your data is already sorted on the joint key， then yeah。

 that's always me faster than hash join。But you know most of times it's not。

 especially you in the lake House or the data lake environment we're talking about where someone just writing out random parquet falls and it's your job to join them together so things almost never going to be sorted on the joint key。

There're never going to be partition in the joint key either。So that was 2009。

 hashing was faster but if you had ABX 512， you could get better。

 and then there was a paper from Wisconsin actually from Jugnesh and his student that basically showed how the early work that's shown the tradeoffs between the partitioning hashin versus the nonpartitioning hashin and in their approach I think they said that the partitioning one was actually was better。

Then the hyper guyss came out in a paper the next year in 2012 said， well。

 it turns out Sermer's joined if you do it our way is even faster than hash joined from the Wisconsin people and without requiring AVX512 just using the heart of the view at the time with hyper。

 they could do Somers driven faster。But then they came back a year later， and said。

 ignoregnore what we said， in this paper， you really want to use hashing。

 and here's the way we did it and look how much faster it is。

Then another paper around the same time in 2013 from other Germans or I guess Swiss Germans that they said here's additional optimization you can do。

 and here's how to make the Reddx hash join， which we'll cover today go faster。

Then Me of paper you guys read from different Germans at Salin。

 they basically said everybody everybody is showing these different numbers and these different results。

 and it's really hard to compare an Apple have Apple to Apple comparison between the different approaches because they're measuring different things。

 or different implications， running on different hardware， different workloads， different everything。

 And the idea was to have a single paper look at all of them。Right。But again， this is going to be a。

This is going to be a test bed system， so they are going to materialize the tuples as if it was a real engine。

 but not going to have the it's not a complete system like hyper or Uper it's going to be。😡。

And then lastly， the the most recent paper， sort of in the space that sort of matters。

 which I did have you guys read from the theumbbra guys， which again。

 the same Germans as the hyper Germanmans。 And they basically said redx has is faster in a larger system and a full system like  Ura。

 But the challenge is going be when to know when you actually want to use it because there's these different design different。

Different aspects of the workload and the data and the hardware that you have to account for when you want to decide how to use Ra has join correctly。

Right。And most of the systems， as far as they know， the real systems that are there today。

 they're not going to implement the radx asterin versus the partition has join。

 but the nonpartition hasjoin， they're not going to implement usually don't implement different hash table implementations。

 Clickhouse is the exception。 we'll cover that in a second。

And so everyone sort picks one and it's good enough。

And in the paper you guys read from the Sin Germans， they basically said， hashory' is important。

 but it's not the most， you know， it's not where you're spending all your time in queries。

And so you're probably better off optimizing other things， which we。

 we've been saying throughout the semester that there's not like one。

The current state of the research and of database systems is that。

There's not one thing you could point to like this is the biggest problem。 We' got to fix this。

 It's a combination of a bunch of things。 So， yes， if you have a really crappy joint algorithm。

 then yeah， that's gonna be a dominating cost of your， of your system。

 But once you start implementing the basic optimization that we'll talk about today， you know。

 separate from the partition versus non partition one like。

You're not going to she off a large number of more cycles or more time and queries trying to make your has run even faster。

I had my one student Prashant， a previous Ph student who's now Databricks working on photon。

 he spent about a half a year looking at some of these earlier works。

 I met money from these guys and these guys trying to make their has joints faster and we were going we were literally counting cycles per tub he got it down from like 12 cycles per tub to like 11 cycles per tub。

And like in the end， it doesn't matter， and we never publish anything about it。Anyway， so anyway。

 we'll cover the different approaches as we go along， but。

The important thing to cover it now is discusses。How we want to design our algorithm and what is the overarching theme of how we want to make decisions about certain tradeoffs of our implementation？

😡，And this is going to come down to whether implementation is going to be considered harbor conscious or car oblivious。

And I know what these terms mean， I think the paper covered it。What does it mean harbor oblivious？

What do the believe mean？You don't know。 Yeah， So meaning like the album doesn't know doesn't care about what the。

What the cache sizes， the number of threads are， what the TLB sizes。

 right it's just like sort of here's a standard algorithm and you try to do the best you can being without tuning civic things to the actual hardware。

Harvard consciousscious is the opposite it' saying like， okay。

 I'm going to try to look at all the low level information specifications about the hardware that I'm running on。

 like the cache sizes， like the newmer regions and so forth。

 and then have my algorithm make decisions of how to divide things up and move things around based on that。

Right， there's trade off to each of these。 obviously that in if I'm Harvard Oblivious。

 then I write it once。And that's good enough for everywhere however conscious means that I had to have specific optimizations that may not work anymore as hardware evolves over time。

Or if I go somehow something in Xons or X 86 is completely different than something in arm。

 then my algorithms will will not scale the other ISA or other architecture。All right so within this。

 we want have sort of two goals of how we want to implement our algorithms。 First of that。

 we obviously want to minimize synchronization this means that since since we're talking about a parallel joint algorithm。

 we have to have multiple threads or multiple workers running at the same time and we want to reduce the amount of communication we have between those threads so that one thread can continue working and not get blocked on another thread filling up some buffer or hasht。

Right。So again again we want our threads we're were going to run full three sorry a full speed。

 So it doesn't mean that we want to make our implementation lock free or latch free。

 it just means that we can be careful about when we actually go acquire latches so that it's not everyone trying to cloboer each other all the time。

The second goal is to minimize the cost of going accessing memory。

 and this means that we want the data that any threads is going to be operating on or working on to be local to it。

 ideally in its caches。If not in know L1 L2， then L3， L3 shared across different cores。

 least in Zons within a single socket， or if I can't have things in my last level cache。

 I want to have it in my local memory。Because I want to avoid having to go over。

Over the interconnect across different numer regions。

And so the way we'll design our algorithms is very similar to how we design algorithms in the intraclass where we said whenever we bring something in from disk。

 a patient from disk into memory， we want to do as much work as we can on that piece of data before we throw it away because we don't want to go fetch the disk again。

Or it's the same thing we saw with Hy where they wanted to do as much work as they can for a single tuple sitting in a CPU register。

 going up the pipeline before they went back and got another tuple because again。

 the cost of going something into memory from CPU cache into to register was relatively expensive。

RightSo this this idea is shouldn't be foreign to us。All right。

 so let'ss focus how we want to do this。So。😊，WhatWhat's going to make our query go slow when you go cashm？

😡，Well， if we just fill our cache with a bunch of crap， a bunch of stuff， a bunch of data， then yeah。

 we're not going to have any space to store new things。But another challenge is going to be。

 we have to actually consider the TLB。On the actual CPU， because now if we have。

 if we're trying to have our thread address a bunch of different you know cache lines across memory。

 then。If I'm just polluting my cache with all these random cache lines and now when I do another lookup for some other know another cache line。

 not only is it not going to be my CPU cache because I got the CPU evicted and put it out to memory。

 but it's also the entry is not going be my TLB。 So I'm I actually gonna to pay two cash misses。

I had to do one single lookup。So I want to be careful about how I'm bringing in。

Bring in my data and make sure again， I reuse as much as I can before I move on to the next thing。

 Basically， I want to avoid doing complete random access， even though it's memory。

 and we said we could do random access。We want to still be careful about what we're accessing to avoid that issue again。

s just like in a display system in the inter class。

 just now we're at you know the even smaller scale。But it's still going to matter a lot。

RightSo I've already started to say that this， we want to avoid random access we want to try to scan as much as possible。

 and then when we do have random access， we want to have things be local possible and that way we're just hitting our local cache over and over again。

So there's going to be this tradeoff we'll see when we talk about the Rax join where theres going to be the amount of instructions we would have to execute to do something versus the amount of memory we may consume and the amount of cycles we consume again。

 the idea of this partitioning step is that if I preprocess my data on both the build side and the probe side of the join and put it in these nice little chunks that will only be accessed by a single thread or single worker。

Then they're not going to go over the interconn to go get random things， and they can just。

Scan through sequentially on these buffers and not communicate with anybody else。 So yes。

 I'm doing more work， but in the end I'll have fewer cycles。Because there won't be， again。

 traffic on the hardware。Al right， so as I already said。

 the hash join is most important operator we're going to have in our database system again we'll see at the end that it's not always going to be the dominant cause。

 but nevertheless， this is what most people want to do in an O lab system。

 lots of joins So we want to make this go fast as possible and ideally again， we want to have our。

All the cores running at full capacity， 100 utilization how we're doing our join and minimize all the stalls of getting things from DMRA and putting into our CPU caches。

So at a high level hash join it has three steps where the first step is optional。So the first step。

 as I already said， is the partition phase where you could decide that I want to take the tuples that are coming up into my joint operator on the build side and the probe side or the inner and the outer relation。

嗯。And I'm going to break them up into these shards or partitions on the hash key that or sorry on hashing the joint key that's being used in the joint operator and I'll divide them up into different chunks and then the threads could then on the build side。

 you could then build the hashable at each worker using these joint subsets and then on the probe side。

 same thing different workers will do probing to the hashable on the digital subsets。

Then on the build side is I said we're gonna actually build the hash table。 So is this。

 we're gonna assume we have a single hash table， single logical hash table。 In some cases。

 you can have multiple physical ones that are that are still in front of a single interface。

 We'll cover that in a second。 But it's a single hash table。

 And that that prevents me from having any false negatives where I do a probe where something should exist。

 But because it's in a different hash or different location that I end up incorrectly missing it。😊。

again and that's the pro。 So again， you do a lookup if you find a match。

 talk about how to find a match in a second， then you take the tuple from the outer relation。

 the tuple from the interlelation， matchsh the two together。

 and then shove that up the pipeline as the output。Right。

So the Son paper you guys read that from these Germans。

 they correctly make a big deal that this materialization cost this last step here actually does matter a lot。

And a lot of the earlier papers dont didn't actually do any of this。RightAnd they said， you know。

 just how fast can you do the build and probe the partition。

 And the reason why this matters is because this is like a me copy to take。

 you're taking two pieces of data， mash them again and producing the output。

 And that's additional pressure on the CPU cache， which if you're not doing it may give you incorrect readings or the wrong perception about the speed of certain operations for the other parts。

 So you always want to do this because that's what a real system would have to do anyway。

They didn't cover the paper from the Columbiaia guys on the Cindy stuff。

 but like when they were showing how to do like vectorized hash joints or hashpups and so forth。

 they literally I found a match really throw it away because they were trying to keep everything in L3 cash。

 Otherwise Cindy didn't make a difference So this is showing in a full system you'd have to do this And again they're including that in the calculation。

And we'll discuss the pros and cons of early in late materialization later on。All right。

 so let's go through of these three phases again， we'll spend a lot of time on the partition phase because think there was some confusion on that in paper and I think。

😊，It's good to see how these systems actually could do it， even though if you end up building resist。

 you may actually not want to do this purchasing stuff。

 but it's good to understand what's actually going on because some of the tradeoffs and design decisions they're going to make for how they're going to implement this are useful for other parts of the system。

 like being aware of cash flow accounting and so forth。All right， so the partition phase。

 youre can to take the input relations on the outer and the inner and you're going to put them into partition buffers based on the join key。

And the idea is that you're going to take these buffers。

 these partitions are going to redistribute them across the different cores。

 and then when you now go into the build phase of the probe phase。

 the workers will be assigned those partitions and they only have to communicate。

 only have to read data within those partitions。 and now you're just doing a sequential scan in that buffer。

And the goal of this is that。Especially in a newer architecture that the extra instructions are going to spend to do this extra partitioning step where we will overcome the。

the extra cost of the instructions， running the instructions is to do the prediction step and therefore getting better locality of the data at each thread。

That's going to be faster than blindly just having every thread， reading different parts of memory。

So in some cases the data will actually already be partitioned for you， this is rare。

 if the data is already partitioned on the join key， then you don't have to do this extra step。

 you literally can say， okay， take the first1 thousand00 tuupples， you go here。

 next00upples go there。Right。But again， that doesn't always happen。And so， again， this。

 this idea comes from the greatest hash showing。 We saw it in the intro class but that was like spilling the buckets on disk。

 Let's see how we do it in memory。Alright， so there's two high level approaches to doing this。

 the non blocking and the blocking approach and the non blocking approach。

 the idea is that we're going to。Does have the threads？

Access to the data at the same time and populate。A single hash table without really。

Without doing any extra sophisticated things to split things up。

 where lit is letting them right out to these buffers， and any threat can write to any buffer。

 and therefore we have to use latches to synchronize。

 make sure that they don't clo each other or cause problems in our data structure。Right。

And in the blocking approach of the radIS approach。

 this is we're going to scan potentially scan the correlation multiple times。

 but then we're going to be clever about how we actually write data into these partitions based on the Radx to avoid having to do any synchronization across the different threads。

So this is the one that's more sophisticated。😊，But again。

 it requires bit more preprocess before doing the one at the top。

AndThere's actually two variations along at the top， so we'll cover both of them。So the， again。

 the non blocking partition is like， we're to collect any thread。

 So all the testss are going to run at the same time just generate。Generate our partitions。

The question is going to be， do we have the threads right to。A single global shared partitions。

 which we had to protect using latches， or do we have them right to private partitions。

Thinking of like almost like thread local storage。And that way， there's no synchronization。

 but then now I've got to do another pass at the end to put them， have one thread。

 put them into the shared partitions global partition。 Yes， in， how would you even have private。

Because in order to have private partitions， you would need like a raix to actually partition them based on or your question is for non blocking。

 how do you actually even do this without rate partitioning？呃。Next slide literally like。

Everyone like I say I have 10 partitions。Every core is going to have 10 mini partitions。

And then something at the end just puts them all together。

Rad partitioning is trying to be clever for having one buffer space。

 but I know what offset I want to write into。let's go through the example if we can come back。

All right， so here's our data table， say we do the really simple thing of like this in the very beginning splitting up in row groups or morsels and say this column be is what our joint key is。

 so we're going to hash this join key。And then sorry， when it has this joint key。

 and then that's going to determine which which my end partitions I want to write into。

 So literally think of this every single core is just writing to any other any partition at once and think of these are just linked lists of buffers。

😡，Al like a change hashheable。And so to prevent the threads from overriding each other called corrupting the data structure。

 I got to take latches on the buckets whenever I write into it because I don't know whether another threads writing at the same time。

Right。But at the end， when I， when I'm done， you know， when I'm done the。

I'm done populating these different partitions， I don't need to do any cleanup or consolidation because now Co one could take this one。

 core2 could take this partition， everything's all cleaning divide up。

 but I pay this penalty of coordinating using synchronization to make sure that threats don't kill each other when the writing to the partitions the population stop。

So this this is the share partitions， the private partitions is where now every core itself has this has n partitions for which is the total number that I'm going to have at the very end So say I want 10 partitions that I'm going hand off the 10 cores within each core now this first step here I'm gonna to have 10 mini partitions and now each core can write into these things without anybody clobbering them so I don't need to take any latches because I know everything single threaded and it'll be super fast but now the downside is I want to consolidate like for partition1 across my different cores。

 I want to put them into a single partition one。So I have to do another pass where you could have each core sort of one car be in charge of taking the data across the many partitions and putting it together into a global one。

Right。So what's the downside it is？I mean， yeah in the last stage， yes。啊。So in this case here。

 when I'm doing this initial pass I have say in this core here， I have this chunk of data。

 it's in my know it's in my L3 cache， I don't need to go across any numer region to go access anything else because I don't care about anything I don't care about this data here and likewise when I write it out。

 assuming the partitions fit my L3 cache， then I'm just writing to my local CPU cache。😡。

But now when I went to do this consolidation step， this core is in some other numer region and it's got to go touch all the partition ones across all the other cores。

 which may be in a different numer region。And then I got to write this back now into my Nuummer region。

So that's expensive。Right。So this this is actually a good example also too of the pros and cons between like late materialization and early materialization。

If I'm doing late materialization， then the data I'm then actually moving around here could just be like the join key and the tuupL ID could be kind of small。

 but if I'm doing early materialization， and I have like 20 columns。

 then this partitioning step here is moving potentially 20 columns around。

Plus going across newer region， which is always going to be bad。 but it doesn'ts better。

As basically it doesn't require a lock， so it is potentially better。Depends， right。

 like if I have multiple newer regions。Then maybe this is bad。嗯。

So this gets into the Harvard believe versus Harvard consciousness。

In order to decide whether I want to do this or not。

 then I had to go look like maybe like run micro benchmarkchs or something to figure out when the system boots up like what the hardware capable of and that even then that might not work out when actually run it in the real time because the data is heavily skewed。

 then one set of partitions might be super big versus another one。Yes。

the with just the global partition， not local partition。

Even then you might have to access memory across。Correct， so the statement as in this one here。

 actually， this one， you， you definitely would。Right his statement is in this one here。

 are the cores potentially going to have their access data that's across newmer regions。 Yes。

 when it writes into these partitions， these partitions are not going to fit in healthy cash and they can be in in different newmer regionsitioning。

His statement is local partitioning definitely better？Meaning like the private versus shared。Again。

 it depends。Yes。For the。How exactly are the？The local participants getting join。

 they just like literally pin。It question is， in this last step here， how am I generating？

How is this thing getting generated， you learn sequential scanning through memory and just appending it yeah。

I mean。Yeah， there's no additional processing you'd want to do， it literally just copying。Yes。

To have each of the cores。😔，There are local conditions other。And then right out to multiple。

Your statement is， would't it be better to have each core have their local partitions in their cash？

Which they do， yes。Like this thing here， again， so I say at 10 partitions。

 this core is going to have 10 mini partitions。😡，And that's all going to be ideal in the Se3 cache。

This last app here， wouldn't it be better for this to be whereition are getting flushed out？

And the last step I have to consolidate， so like this core is to responsible for partition1。

 so it goes to partition one for the mini partitions that each core has to copy the data and put it into the final buffers。

And assuming that。Because because you want to write memory that's local to you。

 So partition one is going end up being in， CPU ones， you know， caches or local memory。

Is there any intention when we try it？The question is there any contention when you trying to join them together。

 contention from what， though。Becauseuse you know， CPU 1 is the only one reading mini partition 1。

 right， So there's no coordination。 There's no synchronization needed。So it's last week。Yes。

 the number of always go to the number。The question is the number of partitions is always equal to the number of cores？

The question is， how do you determine the number petitions you want？No。

 it depends on the s of the data， right？So simplicity， you could just say yes， the number of cores。

But then。What happens when the。Again， say this data like super heavily skewed and。You know。

 there's a billion keys in partition one and like 1000 keys and all the other ones。

 we're now got to partition this one again。Right？So you end up with more partitions than in course。

 Yes is this last step being done using C This question is， is this last step being done with Cindy。

 it's just mem copying。So I don't see anyone really help。To join to the globe。

Why can why can not we like。His question is， why do we have to do this last step。

 Why can't when I build a hashable， just jump， you know， know with it because then。

But now when you're doing the the well first two things。

 this is you're doing this both on the bill side and the probe side， right？

 So now if you have a thread scanning through。To do the build or do the probe。

 now you're kind of doing the jumping again。I guess I had to highlight it the same， I guess。

But it's like you're staging things so that when then you then do the build of the probe。

 there's fewer stalls as you scan along。So you stall because of the remote memory access during the partition phase。

 but then you don't have any stalls in the builder probe side。

If we have a larger number of partitions， hence fewer， like less number of contention for the law。

Maybe if we just let one of the cores handle all of those mini partitions and push it to the global partitions rather than having one core handle。

One set of mini partners。His David is instead of having every core be responsible for like some subset of the mini partitions and consolidateating them。

 would you just have one core do that so each takes care of one partition and right simply partitioning so we sort of go back to the gold partitioning model except that because if we have a large number of partitions there would be less contention。

he's basically saying if you go back here。This is PowerPots I can only show so many。

 you just had a ton of partitions。Then the likelihood that any two thread would be writing to the same thing at the same time and then you end up yes。

 getting a significant advantage。I debate whether I push back whether it's significant。

 but yes if you。If you increase n significantly， then the likelihood again。

 that the two threads try to contend on the same latch would go down， yes。

And the downside of that would be。Was that。Yeah。It depends on how big you'reocating these buckets could be underutilized and you're wasting memory。

 right？Okay。So， let's go through the ra partitioning。Again， the idea is the same。

 but the goal is that we only materialize results once。

 whereas the other only had to materialize it twice。😡。

At least in that effort for the private partitions。Unless you have the recursive partitioning。

 what that's like。We have to do for any of them。So whenever CB say。

 I do a reddx hash join or something that's called a reddx join， it's going to be this approach here。

So the idea is that we're going to scan through the input relation multiple times。

And in the first time， we're just going to gather information about what the data looks like。

And then use that to determine where we want to write data out to our output buffers when it's time to actually then do the partitioning。

So in the first step， do the first pass， we can compute this histogram。

 which is be the number of tuples that are going to exist with some radix。

 which I'll explain to that is in a second。Right， and then we compute the prefix sum。

 which is a running running summation of the。Of from this histogram。

 and that's going to determine where each partition is going to start within our output buffer。

And then we scan now or again， and then we have them write out the data into these buffers based on this partition key。

This are just text。 So I'll go through an example。 but we got to go through。

 understand what the rate X could look like and what the PP sum does。

 And then that'll tell us how we do this last step here， okay。

rightSo the radx is literally just like a digit within a number。

 so you take the hash of the key you're trying to join on and say the hash ends up being 19 and so the radx would just be the one position。

 what is the number like 9。Right。And so you can do this through bit shifting a multiplication。

 and then that can allow you to extract out I just want this one number， right？All right。

 so what do we do with this？Well， then we can use this now and get the other one too as well。

We can then use this to maintain a histogram that says， for every value within every radix value。

 what's the number of entries that we see？And we end up sort of with a sort of list like this。

 that says， okay， for zero， there's two entries for one， there' there's three entries and for two。

 there's one entries。 And so the idea here is that we're going to use the redx to determine which partition number you're going to go into。

And then we're going to use this histogram to the prex sum which is the next slide to say， okay。

 but where within that this giant buffer of my partition data。

 where does that prefix start or where does that radix start？

So the prefix sum is just taking again it's a rolling in summation。

 So say it is our input one through6。 So the prefix sum and the first position is just one because you start with0。

 so one plus 0 equals1。 But then now you're gonna to take whatever the number was the sum of the previous edition。

 Take the next number in my input sequence。 Add those two together。 and that's the next value I get。

So one plus two equals3。And I keep doing this down the line， and then now within my input sequence。

 I'm going to have repeat the prefix on。Right。Again。

 this is we're going to do this after we compute the radx histogram。

 send this all now to our threads， and now they're going to know， okay。

 well at this position in my pre sum， it corresponds to this radx。

 and therefore I know what offset they're right into。

Think of these to memory offsets into our partition buffer。Right。

And the reason why we're going to do this is that we don't to synchronize， so we do this first pass。

😊，Compute this prefix sum for all the radixes。 We hand that out to all the threads。

 And then now when they do the partitioning， they don't need to synchronize at all。

 the way we did with the latches from before。So I don't know if there's a way to compute this efficiently preome with SMD。

There's a paper from Gu Block who's here in the computer science department from like it's like 19994。

95。 And he was envisioning， hey， look， here's how to do vectorized prefix some if you had if you had Sdy instructions to do it。

 which at the time they didn't， which again， I said all think exist。

 but just curious how awesome some guy is he's been thinking about this problem for like 30 years。

 question yes。Sure I understand how。Next slide， so the question is。

 I don't see how the prex loan is going to help us。

 we're going to use this prefix sum to tell us what the offset is when we write into a raX next slide。

All right， so say this is our input data， and we've already hash it， right。

 so these values here is the hash values。So in the first pass of the algorithm。

WeWe're going to split it up like we did before like in morsel， let say we just have two CPUs here。

And then we're to take the first position and the first rax of each hash value。

 and we're going to use that to determine where we want to write the data that corresponds to this record。

So to do this， we compute the prefix sum for this input sequence， right？😊，Going like going like this。

 And then now that's going to be able to tell us， okay， for partition 0。 You know， we want to write2。

 two slots， right， So say theory， we have。We have four values， sorry， two values，0，1，1，0。

 so there's two unique values， so we know that for part zero， according to the first ra x。

 there's two elements in here。So we know that when we write into this giant output buffer。

 we can write at the first position。For partition1， there's two more elements， but it's  two。

 0 plus 2。 So now we want to start writing at the third position in our giant output buffer。Right。

Like this。 So partition zero at CP0 can write at the first position。

 partition0 CP1 can then write at this one and so forth。Right。So again。

 they don't need to coordinate how to do this， they know they're writing into a memory location and a partition buffer that nobody else is going to be writing into。

 so we can just rip through it and run as fast as possible。

And then we just scan through the data and then we just write it out like that。Now maybe the case。

 again， if we have， this is horribly in balance where one partition is huge。

 we can just recursively just do this again by looking at the next raposition and just doing another round。

 and that'll subdivide it even further。Right。That is your question。Okay。Okay， so。And， a。

The vanillaelle implementation or a naive implementation of these different approaches is going to be super slow because。

呃。We're reading， writing random locations in memory。

 and we're polluting our CPU cache as we go along， so in the paper you guys read there are some optimizations you can do to prove this。

The first is going to be using what I call the software right command buffers or the right buffers。

 And the idea here is that。Instead of me just writing out to， you know， as I'm scanning along。

 like writing data here and writing data there as as I'm scanning through on the petitioning step。

 I'll write to like almost like the private buffer I before。 but it much smaller。

 I'll write a little bit to that private buffer。 And when that buffer gets filled。

 then I write to that remote location。 And again， going back to the slide here。 since I know that。

At this step here， I know that nobody else has been writing to the range that I'm supposed to right into。

There won't be any issues if I delay a little bit and then write things out in a batch。Right。

And that'll help things out。Obviously being ni aware from all this is going to matter a lot too。

 but the other trick we can do use is called streaming rights or non-temporal streaming rights。

 and this is these are special instructions on the CPU that allows right to a memory location without having the CPU put it into our CPU caches first。

It's like you're basically bypassing the CPU cache I want to write to memory location X Y， Z。

 don't put in my CPU cache， but the CPU normally would because once I read it in and then overwrite it。

 you just write it almost like direct memory access， write it to the memory。 Yes the last point。

 it says without a separate right phase at the end。

 but there is a separate right phase right English could buffering everything。

Writing in the software right combined。 But like， we don't like。

the private buffers is like you wrote to the private buffer。

 then you wrote to the global buffers right with the greatest partition， I don't need to do that。

 right I do one pass here， and then I know exactly where the data needs to go and it's one right into that。

So there's no extra extra step now to put it as a global buffer。So anyway。

 so there's special instructions， I know Cindy can do this。

 you can take things out of the Cindy register and get it right into memory。

 but I think you can get regular CP register as well can do this。

And so the combination of these things is how you're going to get this actually to work well on modern harbor。

Al， so now so we partitioned now we have a bunch of data or the option partition。

 We could have a bunch of data in these nice little partitions that are assigned to different cores。

 or we could just be operating directly on the the input data itself on the build phase。

 But the idea is that we're going to take all the data that's coming the outer relation。

 case case are， we're going。Asse we we have to have as input。

 the input data has to have the keys the columns we want to join on。We're going to hash them。

And then sort it and so we're got a hash table。 And then when that's done。

 then we switch over the probe phase。 right So now we need to discuss how we're going to organize our hash table in this build phase to run as fast as possible。

So when someone says they have a hasht， they really mean they have two things。

They're gonna to have a hash function something that takes takes an arbitrary bytes of some value and map it to a integer value in a smaller domain。

 typically 32 or 64 bits and then then we're going store this in some kind of data structure which will cover few more slides but then within that data structure we need a way to handle collisions because the hash function isn't always going to guarantee that the hash value for two unique tuoles is going to be unique So we need to figure out what do we do we have two guys try to go to the same location。

Right。So again， we're not a algorithms class。 we're not gonna go too much detail about like。

 what hash function you want to use or what the actual。

The complexity of the hash tables are we' going to。

For the hash functions that we're typically going to use something off the shelf。

 Most systems do some right the room， we talk about in a second， but。

You take something off the shell， but it's the hash。

 what we probably we want to spend most of our time make sure we get that right。

 because we want that to be as fast as possible。So if the hash function。

 there's this trade off between a speed and low collision。

 So the fastest hash function you can have is literally just return one， meaning。

 no matter what key I give you， you always get back one。Becauseuse what is that。

 does's copying from one register to another register。

 or in some case that the CPU can just inline it， right。

 But it' is gonna be terrible for collision because， no matter what key I give you。

 it's going to be at the same location。On the other end of the spectrum， you have perfect hashing。

 which is a way to guarantee that for any possible hash key or any possible key。

 I get get a new hash value。So。A a true perfect hash function。

Only exists in the literature in theoretical papers。

 Jgnash and his Ph student in Wisconsin are working on sort practical implementation of this。

 which we won't cover， but again， it's not truly perfect because you have to handle the corner cases。

 but for most of the keys， it's good enough。But most systems aren are going to do what J Nesh is doing in his perfect hatch function。

 they're going to use something off the shelfho。So to figure out what hash function you want to use。

 again， we don't want to implement things ourselves， there's this。

There's this Github repo for this thing called SM M Hasher。

 And it's basically in the same way that I'm obsessed about databases。

 this guy's obsessed about hash functions。 So he has this benchmark he runs for every possible hash function that exists。

 And he keeps track of the collision rate and the throughput and the performance of them。😊。

And you I think the。Like the Facebook XX hash and the Murmur hash。

 those ones usually rank pretty high。With that。it's like a know op， yeah， Sarah says。Noは。

So so here's a smattering of the ones that probably you'd want to consider for your database system。

 So one of the easiest and fastest ones to use is one of the oldest ones。

 the CRC from the 1970s and the reason why we would consider this in a database system today is because there's actually CPU instructions to do this very efficiently And so some systems like Clickhouse will use in Hy。

 I think use CRC for CRC 32 for integers。Because again。

 it's going to be solem instructions and it's good enough， the collision rate is good enough。

Remember hash is through the the。One this is one of the first sort of modern hash functions that started the new era in 2008。

 and actually I think this was invented by the guy that runs the SMM Haher website。

 Sur was just some general some random dude put this thing on Gitthub but put on the internet and people just started using it and things up the mermur hash3 and in one of the papers they talk about how you can use memur hash2。

 you can use that and actually in CMD to do the vectorized lookups in a hash table。😊。

And so over the years has gotten better， Google then forked Murmurhash and created city hash then they had a followup called Farm hash。

 which does better collision， I think for longer strings。

 and then Facebook has this thing called XX hash， which is up to like version 3。

 and that one again for the performance and collision rate for XX has is pretty good。

So probably member hash， excess hash， and the combination of CRC32 is probably what you would want to use。

Yes， sounds like for any given algorithm， you might be able to engineer data that。

Probably when you say do say on average or workload Yes。

 the question is like if I say could you come up to generate cases that make one hash function be terrible。

 yes。And so with this thing， basically try to throw everything at it and figure out what works the best and doesn't work the best。

 And then like what's the right trend between like collision rate versus performance。Again。

 perfect hackron will have zero collisions， but it's going to be super slow。You need a hash function。

 You need a hash table for your hash table。啊。Like I said， in CRC 32。It's going to be related fast。

 but it may have a higher o collision rate。Again， it's hard to decide and mean people just pick one。

 or they'll pick a hash function for ins and a separate hash function for strings。

All right so now with our our hash function we talk about what the hashing scheme can be so some of these I think we covered the intro class。

 but I want to over them quickly again， and then I think the two ones I want to sort of focus on Robin Ho Hahing and hopcott hashing。

😊，Because the。I think the paper talks about linear probing。

 but there's a previous paper from the same Germans from the paper you guys read that says Robin Hohashing usually works out。

And then what the ober guys are going to use in their paper。

But then I think it's still up for debate whether which one's actually better because people try Wehead in H。

 and turns out it actually doesn't always work as well。

All right so chain hashing this is what most people think about when they have a hash table or a hashing scheme and this is what you get I think for SDL。

 the Center T library's unordered map is this， the Java hash map is this and the idea is that you're going to maintain a list of buckets and these buckets are going to pointers to a linked list and then whenever I have a collision。

 I follow along my chain to find the next free slot to store something。

And the length of each chain within a given bucket can vary depending on the number of entries in it。

So it really simple looks like this right， say I have my bucket pointers and here's my buckets right so I want to put keyA in。

 I hash it， it takes me to one of these bucket pointers and then I jump to the first location of my chain for this bucket and I find a first free slot and I store A no surprise there saying thing B。

 first bucket's empty stores it right away in cases C。

 now I have a collision because it once to go where A is but I just do a sequential scan within my bucket until I find the first free slot and I store it。

Kays that D，D wants to go in this bucket as well， but now since I'm only showing two entries per bucket。

 so it's obviously small， but now since this thing is full。

 I have to extend my chain out to it further like that， right？

This also should be pretty understandable。O， sorry。So the one trick that the hyper guys do。

 which I don't think is discussed in this paper。 but they mentioned it in the morsels paper or the。

You either the morsel's paper or the compilation paper？

So they recognize that this array of pointers here。😡，Since in X 86。

 even though when you say give me a pointer， it's 64 bits in memory。

 the harbor actually only looks at 48 bits。And so they say， hey。

 let's go take those extra 16 bits that aren't being used by the hardware。

 and let's stash something in there。 So they put a 16 B balloon filter。Inside in the pointer。

 the hardware ignores it， but they know to interpret that first 16 bits as a balloon filter so that they'll use that to check to see whether the key even look for could even exist in my hash table or in my chain。

Right。And it's clever because it's like this thing， I got to read this thing anyway。

 It's gonna to be in you know， L1 cache in my last level cache。

 So let me go put as much information as I can to potentially avoid scanning along a chain and find nothing。

So now when I do a look at get G， I check the bloomlo filter first if it's not in there that I know I don't need to follow the chain。

So the next approach is do open dressing and hashing。

 This one is probably more common than the chain hashing， especially where joints。

 The idea here is that I just have this giant。You know slot table slots and when I do a look up。

 I hash something， I modify by the number of slots I have。

 I land in some location in this giant table or giant array。

 and if the slot is empty then I put my thing in there or if the slot is full then I keep scanning sequentially to I find a free slot and then I can put my entry in there。

Or if I end up wrapping around， come back to where I started that。

 then I know I'm in an infinite loop， and I have to stop and resize。And we we。

And then when you want to do a deletion or when you do a lookup， same thing。

 you jump to that location， look to see whether the thing you want is there and keep scanning maybe you find it。

So that approach will be linear scanning。 And this is what most you would think of again。

 when you think of open address hash table， there is variations called quadratic probing。

 And the basic idea are instead of scanning sequentially， you just use a quadratic equation。

 to jump to。Expanly larger。Os， why would you ever want to do quadratic his question is。

 why would you ever do quadratic because it avoids clustering。

Becauseuse they different keys won't always be jumping to the same bunch of locations。

 But the downside is now you're doing much， you know， more random access and you may be， you know。

 but， again， there's no free launches pros to cons with these purchase。

Those systems are going to do linear scanning。Again， this is just a rehashing of the intro class。

 same thing I take take I'm going to put A in， I hash it， I'll come to this first slot， it's empty。

 I can put my thing in there， saying name with B。With C， since it hashees this slot。

 but A's in there， so I just scan down to the next one and I find a free slot and I put it in there。

D， same thing goes here， E starts wants go where A is。

 so I keep scanning down until I find the free slot， then I can put E and F goes here at the bottom。

And in this case here， if I say I try to put something that hashes to。

You know I put in one mar keye and this gets full， now I push sure I put another one in。

 then it's going to loop around and I have to keep track where I started to avoid breaking out。

 right。So the。The obviously downside of linear probing is that or an open dressing scheme is that I'm。

Potentially getting very far away from you know if my my hashtag gets full。

 I'm gonna put a key in pretty far away from where it actually wants to be。

 So now when I go do a lookup， I may have to scan a bunch of entries that aren't the thing I want and you know in the worst case scenario。

 I could almost wrap around the very beginning to find what I'm looking for right。😡。

So the way the way to avoid this， you know， having this infinite loop is you just try to double make your hasht would double the size of the number of keys you're going to put into it。

 And again， we know the number of keys we're going to put into it because。You。

 we know the number of tools are coming up。IAnd we， we could allocate things ahead of time。

 If we get it wrong， then we have to， you know， we have to resize。

 So you always sort of a good approximation is is to。To doubleub and Ricks I expect to have。

And on the resize， you just double it again。So。Theres this observation in the 80s， that。

Recognize this this obvious problem with with the linear probing schemeche or open address。

 And they came with an idea that try to， to， to limit the number of， of。

 look lookups I have to do when I'm starting to read the hash table again on the in a。In a hash join。

 we have these clue clearly two phases where I'm going to build it， I'm going to then probe it。

 and I want the smaller relation to be always on the build side because I want my hasht to be as small as possible。

And so the idea is that what if I spend a little more extra instructions on the build side to reorganize my hash table so that when I do my probes。

 the length of the distance I have to go look potentially to find the thing I'm looking for is potentially reduced。

So the two approaches that do this are the Robin Hood Hahing and the Hbsco Hahing。

 and the Robin Ho Hahing came out in the '80s， Hpsco Hahing came out in the 2000s。

And the idea here is that。Rather than when I just like it's an open dressing hash table。

 but as I'm trying to find my slot， instead of just trying to say， what's the first free one。

 go put my thing in there， I actually look at the entries that are in the place where I want to be and I can decide whether to go steal their slot。

And the goal is that the idea is that the you want to。

Minimize the average distance that any key is from where it should be by swapping keys that are farther away from where they want to be versus keys that are closer。

It's like stealing from the rich to give to the poor， hence the name Robin Hood Hasing， right？So the。

The the more recent research from from the slin Germans for papers you guys read。

 they talk about how Robin Hahing is actually the better approach better than linear hashing。

The hyper guyss or the Umber guys in their latest paper in 2021， they also use Robin Hood Hahing。

 citing the slin paper about why you'd want to do this。But every so often。

 you see various database companies try out Robin Hood Haing。

 and it actually doesn't pan out in the real world。So I'm not trying to pick on these guys Ques TBB。

 but this is the most recent one that I found。So they had a blog article came out in November last year that says。

 hey look we swapped out our hash map with a new studio joins with this new fast map implementation。

 they're in Java， but we could ignore that for now and at the very bottom of this they're they're all happy have this nice hash table it's better than the chain hash table in。

😊，In in Java because now they're using open addressing or linear probing。

 but then there's just a little blur at the bottom here that says someone on Redit told him hey。

 you should try Robin Ho hashing right and he talks oh yeah。

 the early numbers actually look pretty good we think we want to do this right But then if you follow the pull request link here from November you go to the very bottom where now in January he says well it turns out Robin Ho hashing made things worse so they end up turning it off reversing it right。

A few years ago， we had the influx D people show up and they were all boasting how they were using Robin and Hahing。

 Dave Anderson was in the audience。 He asked them why you're doing this and they said， oh。

 we saw someone in Hacker who said to use it so they used it but then it turns out I think it made things slower too right So to me I think this is still an open question I don't know what's the best one to use at this point but it's good to understand what Robin Ho and Hoscotch actually doing。



![](img/98e2fba6076922a1427cab8660166d56_5.png)

Okay， so again the basic idea is that。It's just like linear probing。

 when I want to store something in， I'm going to store it。

 know the first location that's free in in my slot array。

 But then in addition to storing the key or the hash key。

 which we'll talk about in a second and the payer of the value。

 I'm also going to store the number of jumps I am from where I should have been when I hash directly into it。

 So in this case here， when we hash a and put it in， there wasn't any else in the slot。

 So's positioned or its distance is 0。So now I want to be same thing distance is zero。

 so I want to put C in。C wants to go where A as so it can't。

 but now I compare from where C once the distance C is from where it wants to go from where A is from it where it should be。

 in this case here， they're both zero， so C is not going to steal a slot and it goes down the next one。

 but now that I store that it's one hop away from where it wants to be。😡。

So now when D wants to go where C is。😡，At the very beginning， Ds。

 the number of hops it is from where it wants to be is 0， and that's less than D or R C， which is1。

 So D cannot steal from C。 So we leave C alone。 and then D is going right here。

 And then its hop is one。Now I going to start E。Same thing in the very beginning。 E A is0 hops away。

 E is0 hops away at this step。 leave alone。 Now we get down here。 C is one hop away。

 E is one hop away。 Leave that one alone。 But now we get here。

 D is one hop away because it wanted to go where C was。

 But now E is two hops away because it wanted to go where a is。 So this case here。

 E is allowed to steal from D shoot them in the head， take a slot。

 And then D pops out and we got to put it back down into the next slot。

 And we would run that same protocol。 If there was something else here。

 we would decide whether we want to steal that slot or not。Right。And then F， again。

 same thing goes like this。Yes， sos can be really his question is answer be really， really slow， yes。

Right，Because what are we doing， We're copying。Furthermore of all。

 we're doing a bunch of branch misredictions。Because we got to do then else is to figure out whether we want to steal or not。

SoBut again， now when I do lookups。know， if I'm looking for if I'm looking for E， for example。Well。

 it could have been here， but I'm gonna get it here。 I'm gonna one fewer hop doing the lookup。

 So again is is the trade off always the right thing to do to pay higher costs in the right side to make the read side go faster or the build Cy to the probe side。

 same thing with partitioning。 It's a bunch of a bunch of actual work I'm doing before I even do the two steps that I join。

 But ideally I'm setting things up to make things faster when I run later。Yes。自分がもかばも。

More subsequent。😔，M user。But otherwise， you might get a false false。This question is。

 do you if there still look more values otherwise you get a false negative。

 why would you get a false negative， you because you don't know it's definitely at the position you expected。

Actually ended up at。So， so I look， if I'm looking for F maybe go back。

 say Id look for what was it E wanted to be here， right。Or say say I'm looking for D。

 So D would start here。 it doesn't matter。 So I say it starts here。

 I'm gonna scan through until I find D or I find empty slot。

 If I find empty slot that I know doest exist。 or I don't have a false negative。To go to。

But I would have to do that with Leer probing anyway， without Robin Ohas。Yes。So the total jump。

 the dis of that jump。The question is what sorry？I mean， the。The total of the job。Oh，Sorry。

 listening thing。The summation across all entries should be the same。As linear probing。I think yes。

Yes so like overall， there should be like that。Yeah， he's pointing out and he's correct。

Even though I'm rebalancing things so that I try to minimize the jumps。

the distance between one position for where it should have been。

 it's the same as if I didn't do this shuffling thing。

 but like depending on what keys I'm trying to look up。I may， you know。

 if if I'm highly swed on on the looking up the same key and over again and that key is closer than what it should have been then I might。

 I might be in a better position。 but you can't algorithmically prove that because it depends on the data。

 That's what I'm saying you don't want key is it you can't algorithmally prove it。

The goal is in practice that this works out for certain distributions of data。

Would you be able to prevent？Long scans。Don't exist。This question is。

 would you be able to prevent long scans from data that does exist by putting a blueprint in front of this。

 we'll see this in the second of joins， yes。Right。We the vote was everywhere， right。All right。

 so again， this one is。This one can swap forever， right。

 like like it doesn't try to bound the you know how far thing is actually going to be。

 The modern variation called hots Scotting hashing is is an extension of this。 But the idea is that。

We can still move things around like in Rob Ho， Ha。

 but we only move things around if it can be in the same neighborhood。

There's a way to artificially restrict how far we can move something away from where it should have been。

RightAnd then if we can't find something in our neighborhood that we know doesn't exist。Likewise。

 if we try to reshuffle things and there isn't room in the neighborhood where something needs to go。

 then we say our hash table was too big and we have to stop what we're doing and resize it。Right。

So the goal is again， to have the cost of accessing a neighborhood be the same as finding a key because if we size our neighborhoods to be within cache lines and things are nicely aligned。

 then it doesn't matter whether we're looking for a key in the last position in the neighborhood or the first key position in the neighborhood。

 since we brought out everything in our CPU caches anyway， it's the same。So for this one。

 for simplicity， we're say our neighborhood size is three。So you would say for the first three slots。

 that's the neighborhood one， next three slots to neighborhood two and so forth and they're overlapping in the case of last neighborhood six again that's the last two positions and then it wraps around we you know a seven would be here as well right？

So now when I want to do a lookup or insert A。A hashees this position here。

 So that goes in neighborhood  three。 So we can say a can go anywhere inside neighborhood3。

 So because the table is empty， we'll put it in the first position。Same thing for B。

 wants to go over neighborhood one is that neighborhood is empty。It goes in the first position。

So now we take C and then once to go this neighborhood it and it gets just like linear probing where the first position is full。

 I scan down until I find the next free slot， and that's why I store that。That's fine。

So now I going to start D， same thing。 D wants to go over C is。 that's the name of4。

 So in this case here， it just scan through and it goes here。So now we put E。

So E wants to go in the same neighborhood where A is in。 So when we scan through， we'd say， okay。

 this neighborhood is full。So what we got to do is figure out what we can take out of the neighborhood where it wants to be。

Put it into another neighborhood。 and that way we can put D into I put E into neighborhood three。

So you'd have to basically go look and keep track of okay for A C and D。

 which ones are not in neighborhood 3。 So A and C both hashed to this location。

 So there' neighborhood3， but sorry A and A and D both hash to this position。

 So they're a neighborhood 3， but C hash to this position。 So it's neighborhood 4。

 So there's in neighborhood4， there's a free slot。 So I'm allowed to move。Is that right， No， yeah。

 That should be D。 Yeah， D is allowed to move down by one。

And then now I can go ahead and put E in this neighborhood here。

This seems really complicated compared to the first the statement is this seems very complicated to to Robhood and linearar probing。

 yes， absolutely yes， but it take longer longer to actually Sure absolutely yes。

So they since you're building that actually， we're always paying the cost of building would be faster。

But it's only limited by a certain amount of simplicity is better in this case here on a modern CPU。

 nobody does this。And I'll show one graph at the end and I think Robin Hood beats this。

In the clickhouse， measurements， yes。anything out of it。His question is。

 what happens you came to anything in the neighborhood， you have to say Mashhe is full。

 even though obviously you have free slots and litter probing that would not be an issue for this scheme it is you stop what you're doing。

 resize and double the size the has and repopulate it。😡，Then you get to questions of like， okay。

 well。You know。If I'm doing late materialization， then repopulating hashaable maybe isn't not big of a deal。

 But if I have the full tu。 I' got to put back in the Ha shape， then that's expensive。

 But in the case of Ques EB， they store separate heap of the actual data just the values are just offsets。

 which we haven't covered what this actually is。 And so that way you can resize it without having to copy any of the tus themselves。

's pros。第一个。Sa is is the worst version extend hashing this？

This would be that fast than understand hashing， but。Cause， like。The idea is like say， okay。

 I know I I' gonna have a million tuples。 I'm going to pick hashpe I can hold 2 million slots。

 and hopefully I don't have collisions there。All right， super short in time。

And they quickly bring up cuckoo hashing， sometimes called double hashing。Basically。

 the idea is that instead of one hash function， we can have multiple hash functions to figure out where things go。

Right， so I want to put a in。 So I'll have two different hash functions。 Basically。

 it's the same hash algorithm， like murmur or or X X hash。

 which is with different seeds to make sure that it has a different distribution of values。

 So I'm gonna hash both of them。find it for the first free slot。In this case here。

 the both empty because the table's empty。 So I'll flip a coin and maybe pick the first ones。

 first one。 So I'll put a there。Next T comes along， B， it hashes to these two free slots。

 or two slots here， one of them's occupied， one of them's empty， I always choose the empty one。

 and I put B in there。C comes along Now C was the hash where B went and the hash where A went。

 So both are occupied。 I got to pick one to kill them and take their slot。 right。

 It's like Robin Ho hashing， but instead of moving it down， I'm going literally pull it out。

So say we're going to go to kill the first guy。 B。 So C takes its slot。 B comes out。

 now we've got to hash it again。 since we know that when we put it in the first time。

 we use the second hash function， when we come back the next time we use the first hash function。

 But now when we go to insert it， it goes where A is so we got to go take it its slot。A comes out。

 we hash it again with the second hash function， and now we find a free entry。Right。Yes。

 but thes are bound his question is if lookup's bounded by two， yes。

 so you have01 lookups by doing this ahead of time， yes。We get a loop of hashes。

His question is just like there's like a linear probing， all the other hashing。

 seems I can get I can get stuck in infant loop where。

Saage something was here and I pull that out and it hashes back to something else。

 and I have to keep track of where I went into to avoid infinite loops。

So now when I do a look up to his point， it's always going to be 01 because I just hash it twice。

And then I， I jumped to two locations， and I could figure out what 2 I want。

So Koo hashing is used in a couple systems and DB2 Blue uses this。

 and I think one or two others I can't remember， but I remember looking this up before and other systems were using this。

Yes a lot of these seem to be optimized for like read only workloads。

 like they sacrifice inserts a lot。Is that intentional or was it designed for something else rather than？

Daases。His David is， these seems like these are made for read only workloads。

They seem to be ignoring the hash build phase。And the cost of it。I。Right。

 but his image is like you're ignoring the hash build phase because most of the data structures like again's almost like you're using this a hash index。

 it's right once read many。 So yeah， the insert are more expensive。

 but I'm going to make my reads go faster that's essentially for databases， that''s a fair tradeoff。

All right， we're way， way， way， way， way behind on time。Hey， you know。

 we'll have to pick up what we left off and come back on。On Monday， unfortunately。

And let competing with the runs。Should we just thought it？It's popular okay。

cool if you got to go go So what's actually we're putting a hash table。

 kind unclear And the paper doesn't really say So the first thing we'm going to figure out is are we actually storing the tus themselves or certain pointers or offsets the tus And some cases in the case of QueDB in their system。

 they store the tus actually in a separate heap and just have offsets into them。

 So now when I resize I'm just moving around those offsets and not the actual data itself or if I'm having these buffers coming in if I maintain those input buffers then I just have offsets into those and I don't have to store the actual data。

 But now that means when I do certain lookups or I matchsh the tus together that are being joined。

 I got to dereence that pointer or follow along to figure out what the actual data is。😊。

If you have variable linked data， then you can't put that in a hash table with open addressing because every slot has to be the same length。

Next question is， are we what actually storing as sort of the key portion of the hash table？

Because again， because there'll be collisions， I actually need to compare the actual join keys from the input tuupple which is what's actually in the hash table。

 so I could just store the original tuple and that could be expensive but also because it's a variable of a length and you can't that's going to screw up your slots so sometimes you actually want to store the hash the hash you compute it when you inserted it along with the original join keys。

And so that you can do a quick comparison just based on the hash keys。

 rather than having to do expensive string comparison。

So differences systems do different things and this is a classic compute for storage if I only store the join keys and not the hash。

 then my data structure is going to be smaller， but now when I do comparisons。

 it may be more expensive potentially because I have to basically look at raw keys。All right。

 the probe side， there really isn't anything fancy we can do because it' literally just ripping through the input feature vector input vector and probing hashe one looking for matches。

But the one trick we can do is what he asked about is adding balloon filters And so this is the idea is that when we're building the hash table in addition to populating the hash table will also populate a bloom filter so I build a hash table。

 but I also build a balloon filter And then I pass that over to on the probe side So now when I do my probe。

 I first check the balloon filter there's no match then I know it's not gonna be in the hash table so I don't by look in the hash table because again the filters can have false positive。

 but not false negatives So I'll know that something could notex and it's way cheaper and way faster to look at the balloon filter rather than probing the hash table So this is sometimes called sideways information passing I think the technique there's a vectorized paper that talks about it there's a vertica paper from 10 years ago that talks about it a bunch of systems do this technique。

 The hyper guyss do this。 theumbber does it as wellumbbra again they'll have this bloom filter for this will also have a balloon filter within that as well to see whether you need to fall along the chain。

Alright， so quick benchmark。 So we're going to look at the paper you guys read and read the and then some。

 some。A paper from the hasht with the clickhouse guys use for strings。

 and again I'm going through this very very fast， but it's basically going to have the no partitioning basic scheme。

 but then it's going to have the different rax partitioning stuff we talked about that have a concise hash table from IBMDB2 blue。

The thing is like a packed array with like a bloom foot in front of it。 we can ignore that。

 no other system， No system other than DB2 Blues uses it。

So you're going have sort of like the the vanilla implementation like based on what's in the。

 I think the open source versions of these of these algorithms and the。

As it's described in the papers， and then they'll have their optimized versions that do a bunch of the techniques that we talked about。

So here's all the different variations of these and over here again。

 this is that sort merge that I talked about that came from the Intel Oracle paper right and so the region here which you can't really see this region over here it's gonna be optimized versions and then these are the symbols that they're using so they basically say that if you do radx partitioning for either a chain hashing linear probing or open address or really basic array like that's always gonna to be the fastest if your data is nicely fit in an array。

 you can get a little faster as well， but if you don't do any of these rated partitioning。

 no specialization because again， making sure you get all this correct for the actual hardware that you're running one is non-trivial。

This is actually going to be pretty， pretty good for most things。

 almost all things and requires less engineering overhead than than all these other ones。

 the a array literally like like。Yeah yeah， it's like， yeah， the indice is are a has to be use yes。

Right， okay。So then the next graph they show is this thing here that says， OK， well。

 how much time in a real query is actually being spent on the hash drawing？

And for all these different approaches， you can see that it's basically 10% or less or 30% or less being spent just doing the hash join and everything else is the rest of the query。

 like getting the data， reading the data in， doing any filtering， materializing the output。

 doing any other stuff up above in the query plan， this is TPCH query 19。So again。

 the hash only is super important， but it's not the high pole in the tent。

 The most important thing we should be optimizing for。But so for for this reason。

 that's why I think the， you know， this， this invitation here is going to be。

The no partitioning linear approach would be the easiest to implement and good enough for most things。

 right？All right， so let me one graph also too that wasn't into paper。

 this is from another paper from it's some random workshop or conference I'd ever heard of。

 but the Clickhouse guys basically took their implementation or they sent a PR and what this is the data structured Clickhouse uses for doing hash joins or hashing for hashts for strings。

And the basic idea of how it works is that it's a single logical hashable。

 but underneath the covers they have a four different variance of a hashable for the different strings of different sizes。

 so they'll have one that's like for strings that are 16 bytes， here's a hash table。

 here's one that's 17 to 32 and they have different optimizations for all of them。

So what I like those papers because they just ran everything on this one worklay doing joints and groupey。

 and you can see how their thing is the best。 So this art index is is the Reddix try from the Germans from hyper。

 really not for joins' replacement from a B plus tree， but they did it for that。

 but you see the chain hash table you can see the Hoscot hashing。

 the cuckoo hashing Robin Hood hashing F 14 tables from Facebook。

 the Swiss tables from the Swis guy left from Google thank you。 And then here lo and behold。

 here's our vanilla off the shelf Leer probing hash table and then their thing is squeaking out a little bit better because again this is physically for strings。

😊，Right。Yeah， unfortunately there's no clickhouse paper， they do a lot of crazy stuff。

Like I think so many different variations of hash tables and a bunch of different ways doing joins。

 but they don't their blog articles are pretty good and you sometimes go into the covers and understand what's actually going on Clickhouse a really fascinating systems。

😊，The guy told me that they haven't be able to be here they're actually working on now。

 so hopefully we can cover that next year because it's so simple。That's the whole point of it。

 simple is better。Right？Okay。Again， as I said this， partitioning is is faster， than no partitioning。

 but getting it right is challenging。 Again that this is not just me。

 the Germans and another say the same thing。 And most of them are going to pick one implementation and not try to be clever about it。

 Yes， quickly doing that last。地を？Would you think that people should adopt like a different？

His question is。Given these results， does it makes sense to have a specialized very well length string hash table。

Yes， if you can get random people to write it for you， sure。But if you're just starting off this。

 linearar prove。Okay all right， so again， next class we'll do worst case up'll join。

 we'll spend a little bit of time on do profiling with performance counters and then again reminder Wednesday next week will be the status update presentations for the projects okay。



![](img/98e2fba6076922a1427cab8660166d56_7.png)

got a bes to get the 40 young spot get a grip take a sip and you'll be picking up models ain't the pu because I more man I telling the 40 young got short cans。

St are six backs on the table and I'm able to see Santa I。

No short with the quilt you know what got them， I take off the cat but first' tap on the bottom。

 don about three in the freeze it so I can kill it， cat full with the bottle baby whoop don feeling。

 co they nice and says the pain off win you can't get down with the guy in wild。

Take back the pack of thugs， and go catch some now for trigger to the thugs。

 Billy Des affiliate developing weak Go， be a man kid kind of thank God。🎼。

