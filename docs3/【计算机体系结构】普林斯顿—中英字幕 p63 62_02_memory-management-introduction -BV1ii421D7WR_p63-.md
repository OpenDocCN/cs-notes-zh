# 【计算机体系结构】普林斯顿—中英字幕 p63 62_02_memory-management-introduction -BV1ii421D7WR_p63-

![](img/319c3d92cf81879c9b6b1f44744b2d9d_0.png)

Good afternoon，'s。Get started。So today we are going to be continuing our quest into computer architecture。

 and we're going to be talking about virtual memory and address translation。

Together with how you do virtual memory protection on top of that。嗯，实实是。

Crossover between architecture and operating systems topic。

 So your operating systems many times has to worry about how to manage memory。Also， many times。

 you have to worry about how to manage。Who connects this memory？

 You have to worry about how much memory different users could possibly have。

 But even in a un processor system， this becomes an important thing。

That a uni processor system and a uni。User system， not a multi program system and not a multius system。

 but just a single user system also has to worry about layout of memory and worrying about running different libraries。

 different portions of programs and how to lay that out effectively in memory。

So we're going to continue videotaping our lectures today to put online that you guys can go look at later。

 And so let's get off。 I started by talking about memory management。

And we're going to talk about a couple different schemes today， which。Orange。Very popular。

We're going to talk about some schemes that have some historical basis that are still important and important to understand and there's some vestiges in today's architectures。

 So for instance， one of the things we're going to be talking about today is called segmentation or base and bound registers。

 which still shows up in X 86 processors today， but is not very common as a memory protection system。

But it was designed as a memory protection system when it first got started。Then we're going to go。

 and at the end of today's lecture， we're going to talk about fancier virtual memory systems that are used in modern day computers。

How your operating system goes about managing memory with that。

 how it provides efficient use of memory and how it protects different accesses。

So we can broadly separate memory management into three really important。And orthogonal functions。

First of all， translation。So in translation， what we're doing is we're taking one address and we're turning into some other address。

 So we're able to remap addresses。Now， you might say， why do we want to do that？ Well， by doing that。

 we can have more flexible memory layouts and prevent things like fragmentation。 So fragmentation。

 we'll talk about that more later in today's lecture。

 But fragmentation basically is the problem that if you have lots of little pieces of data or code they get loaded。

 And then some of them complete or go away。 You're gonna end up of holes in your memory space。

 And it's very hard to reclaim that unless you try to compress or relay out the memory。

 And lots of programmingb models don't allow you to go recompress the memory。😊。

This is familiar if you've ever taken a。Basic。Data structuress course where you had to go deal with managing something like a heap。

In the heap， you have pretty common to， it's pretty common to allocate different sized objects on your heap。

 And then you free up those different sized objects。 And if you happen to free them in a bad order。

 you end up with little chunks of memory that are really hard to go use for something else。

 especially if you want to go allocate something very large。

 you might have enough memory in your system， but it's just not contiguous。

So what approach to this is to have things like garbage collectors。

 which is what Java and a lot of the managed programming languages do。

 But something like C or C plus plus does not have that notion of garbage collectors。

 So we're gonna look at that more。Not from a heap perspective， but from a。

Perspective of the entire memory system。So sort of one level out from a heap。

 So inter program fragmentation and inter program garbage collection。

The second important function of our memory management here is we want to restrict access or protect access to memory and allow only。

Users who are supposed to be able to touch a certain piece of memory。

 to be able to touch that certain piece of memory。 And this is important if， for instance。

 you have one system which has someone's bank records on it。And on that same system。

 someone else can log in。 They can tnet or SS S H into it or remotely log into it。

 And you don't want。One user to be able to go read some other users bank records that just happen to be laying in memory。

 So we need some way to protect that。And memory protection gets us there。

 It allows us to have different users using the same system。

 different processes using the same system。And we can restrict the access to different locations in memory。

 or protect。The access to different locations and memory。Finally， memory management。

 one of the important sort of。😊，Points of memory management is that you can actually think about having more memory than your machine has memory。

Now， you might say。Well， that doesn't make any sense。 No， it doesn't make any sense。But。

If you have a flexible enough hardware system， you can think about using other things to look like memory。

So for instance， if you have a hard drive in your computer， you can use that hard drive。

 which is very， very large。To effectively increase your memory size by taking。Data。

 which is laying in memory and put it onto the disk。And sometimestime later in the future。

 take it off the disk and put it back into memory and trick the user。

Into thinking that they have a larger memory space。 And this is virtual memory。

 So it allows us to have transparent extension of the memory space using something slower。 I mean。

 it could be could be disk。 It could be the older days。

 some drum that spins where you sort of store things on the drum。 You could even even， you know。

 nowadays， you can swap on flash。😊，And if you ever go look in Linux or something like that。

 this is called your swap partition。Sometimes called a backing store。

 a couple different names it goes by， but it's a virtual manage virtual memory storage location。

Nowadays。Most systems provide this with some sort of page based system， which we'll be talking about。

 But， these ideas are all orthogonal， and you can have different mechanisms to solve all of them in different ways。

 And we'll be talking about some of the historical aspects of that。Okay。

 so let's start off in the beginning。Well。In the beginning， we didn't have fancy memory management。

 Instead， we had addresses。You want to go access some piece of memory。 You come up with an address。

 and that directly indexes into our memory， and you get back the data。Well。That's okay。

 if you're running one program at a time。So if you go back and look at EdSAC。

 which is one of the original。Probably the second computer， I think， Can the first computer。

 first sort of modernish looking computer。It only had physical memory addresses。

So what this really meant is only one program can run at a time。And it had all of memory。

And the addresses that were used。Basically didn't move around because there was only one program running。

 and it owned everything。 And I O could directly touch memory。

 main processor could directly touch memory， and life was simple and okay。But。Unfortunately。

You couldn't really run multiple programs。 You couldn't protect multiple programs。

 You could definitely not take memory off of disk and put it into memory because you had no way to sort of remap things。

 So it did not fulfill those sort of three requirements that we were talking about。 We didn'。

 It didn't doing translation and didn't do any ability to protect and it didn't have any notion of virtual memory。

One thing that did happen is that users still。One until to write subroutines。

That were location independent。 So what I mean by that is。You read a subrtine。

 and this is back in the days when people were writing these subrines in machine code or assembly code。

And you still wanted to be able to write one subroutine and be able to use it and call it and use it in different portions of your programs。

So one of the tricks that people sort of thought about is how can you still have location independence even。

When you only have one physical address space so you can't remap things。

 there is no translation going on here。Well。In fact。

 you can actually use the linker or the loader to be able to go do this。So actually。

 a quick show of hands here， who knows what a loader is。Who knows what a linker is。Okay。

 so we got a little bit of coverage with Lier。Liinker。

What it does is it takes multiple different compilation。Objects or compilation units。

 So if you take a computer program that's made out of a bunch of little files。

 a bunch of different source files， you compile up each of those separately。And when you link it。

 you take them and you put them all together into one program， and you resolve all the addresses。

 all the jumps and the data aes across that one program。 So that's linking。 That's static linking。

Now， dynamic linking， you guys might have seen DL L， dynamic。Dna linkable， notable objects。

 So what happens with DL Ls is you'll actually do that linking step of resolving the addresses at runtime。

So you can actually do either， you can either do it dynamically or statically。And the loader。

Is the piece of code， which actually takes a binary off a disk and puts it into memory somewhere。

And typically， the loader will go and do a last level linking step at the end。

 So on a modern day Linux system， your linker， excuse me your loader。

 when you type up when you go to execute a program and you type don you run L S or something like that on your Linux system。

First thing it does， it goes and finds the L S bits on the disk。

And it takes that and copies it up into RA。Somewhere。

 so you can do this on this absolute dressing system。And then when it does。

 and it goes and figures out。All of the dynamic libraries that are needed。

And it goes and takes those off disk and puts them into Ram somewhere。

 And then it's going to the last step here is the original program had pointers。

To addresses that didn't actually exist yet， because it didn't know where the respective。

Loaded respective libraries were gonna be loaded。 So it has to patch the program up。

 It has to rewrite addresses to make sure that the newly loaded program points at the correct location。

 So that's a runtime linker doing its job。 The static linker can do that same sort of thing。

 but a compile time。 or excuse me at assembly time or linking time in your program。Okay， so's。

Absolutely dresses。And if you have the physical hardware for an absolute dress machine， it's simple。

It's kind of what we've been looking at at this point。You have your program counter。

 you stick it in your cash。It gets instruction cache， It gets an instruction out。

 You take your address。 If you're doing a memory access。

 you stick it into your data cache and it gets some data out。If you take misses。

 everything's a physical address， it goes to the memory controller， goes out to DRA。

Sees seems simple， it is。But like I said， it doesn't solve all the problems we want to solve。Okay。

 so now let's start talking about stuff that's a little bit more， more complex。

 If we actually want to do a dress translation。So address translation， actually。

 before we leave this， we're going to call。Addresses that touch main memory。Physical addresses。

And we're also going to talk about this notion of a virtual address。

A virtual dress is actually just an address that the main processor uses。

 which might be translated somehow into a address which is out in main memory。



![](img/319c3d92cf81879c9b6b1f44744b2d9d_2.png)

![](img/319c3d92cf81879c9b6b1f44744b2d9d_3.png)