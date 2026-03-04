# 【计算机体系结构】普林斯顿—中英字幕 p68 67_02_address-translation-review -BV1ii421D7WR_p68-

![](img/ee5f6966206d2795504414289bbe2a5f_0.png)

Okay， so we'll get started。 looks like we have a quorum today。

So we're gonna be continuing wrapping up what we were talking about last time。

 which was about address translation and virtual memory。

So we have like about two or three slides left over。

And mostly what we were trying to talk about was how。Address translation and virtual memory。

Influences the design of caches。Well let's， let's go back and。

Briefly recap here what we were talking about last time just to put it back in everyone's memory。

So we were talking about memory management and different ways to do memory management。

 And we had talked and， and some of these orthogonal concepts and functions that memory management is trying to do。

Mainly， we're trying to translate addresses so that we can move around data and remap data。

We were talking about protection， which would allow us to run multiple different operating systems or multiple different applications at the same time on one chip。

And we also started to talk about virtual memory。 But this is kind of where we were left off last time。

 We were talking about， we talked about paging。And we briefly touched on demand paging。

 So I want continue on that today and then look at some the implications of the design issues。

Of virtual memory and the ability to have。Lots of different address spaces intermixed at the same time with different mappings and how that inter mixes with having lots of memory or very large amounts of memory。

 even though your system may have a very small amount of memory。

 So it's a very large amount of virtual memory as the name implies。

So if you go look at a modern day virtual memory system。

 So if you're going to run Linux on your desktop these days。Your desktop， let's say。

 has a few gigabytes of Ram， has some small number。Probably one，2，3，4， maybe even six。

 if you have a really good desktop of gigabytes of RAM。And。

One of the things you may want to do is run applications that use more RA than that。

And we have this big storage device plugged into our computer， which has lots and lots of storage。

 namely our disk。Now， the disc is not the only place you can actually try to swap memory out over。

You can actually use other things。 So people have built virtual memory systems that swap memory across the network。

 for instance， to another computer。This is actually found to be fast in the original network of workstation days。

 So this is a project at Berkeley where they had lots of computers。

 lots of old sun computers on a network， and they would they were actually able to swap memory across the network to the neighboring computer and use the neighboring computer's ra effectively to make the Ram size bigger of the machine that they were using or effectively swap out。

 Now， one of the key things to making all this work is having this notion of demand paging。

And demand paging basically is around this idea that the operating system only maps a page when it absolutely has to。

And the operating system can also decide to kick things out and put that memory。 let's say on disk。

 If the memory is clean。 What I mean by clean is it's not dirty relative to the process。

 So the process or to not go write any data It's that memory。

 And there's exact same blocks on the disk When it goes to kick it off。

 It doesn't have to go save that dirty data and can just market it as saying， oh。

 it's on the disk already over there。 So don't， don't worry about this。

If you go to an operating systems class， you're actually going to implement a demand paging scheme。

 I know they do that here at the Vson's operating systems class。 So you can。

Try out some different algorithms and how to pull data in and not out because there's different management algorithms you can use to do。

 to do this demand and paging。But if we went back and looked at sort of how address translation works from the hardware level。

 because that's what we're focusing on in this course。

You take an address and you run it through a translation lookaide buffer。If you have a hit。

 this is the everything's going Well case。 you have a hit。

 So the address is in your translation look aside buffer for cash of the page table。

You also probably check some protection bits。 so to see if you can do a read or write。

 or if the process that is reading or writing the data is in the correct address space。 So。

 for instance， you don't want to have an application trying to read or write the address space of the operating system or something like that。

 if， if it's permitted。The translation comes out of the T，O B。 Everything is good。

 and you just go access the data。If not， you're to end up here in this protection fault case。

 This protection fault case is going to be in the operating system and the operating system will probably try to kill the process or have some sort of segmentation fault。

Alternatively， if you're up here in the TOB lookup and you take a miss in the T O B。

Lots of interesting things can start to happen now at this point。 If you have a hardware page walker。

 So what that means is a little finding state machine， which will walk through the page table。

 walk all the way to end the page table， find the mapping and install it into the T O B。

This and this is all done in hardware。Hence， it's speckled。

If you are on architecture or something like MIps or alpha。Or Terra， that's all done in software。

So this page walker and updating the T O B is actually done in software。

 So we'll have some software going and walking it and doing bunch of memory references and you have a little piece of software there。

 And then there's some hybrid approaches。 So， for instance， even a MIPS。

 there's some special hardware that helps the software walk the page table faster。

If the memory that you're trying to go get at is not in the page table already。

 then you sort of fall over here in the operating system line。 you take it interrupt。

Into the operating system。The operating system then has to go look through all of its structures and see。

 oh， is that data on the disk somewhere。 I it Are you just accessing some piece of memory that doesn't actually exist。

 If that's the case， then you're actually going to be sort of going over this segmentation fault or bus error world also because you're basically going to be try to do a memory reference to some piece of memory。

 which isn't there。But if， let's say it's on discor it's in the。

Swaap memory or the backing page cache on the disc。

You're basically going have the O S fill in everything， fill in the T， O B and just return。

 And life is， life is all good。 and you continue on。So。

Now that we have decided that we want something like virtual memory。

 and we've decided that we want to have translation look aside buffers。

 let's look at how this influences the design of our hardware pipelines。

So here we have address translation， shoehorned into a five stage pipeline here。

And some of you may notice。Here and here， we just added to the delay of these stages。

 We just sort of shoehorned it in。 We didn't add an extra stage。 We just sort of put it in there。

And it's serial。Is the naive approach to go do this？Well， that has some， has some。

Serious latency consideration。 So if your instruction memory is on your critical path of your processor and all of a sudden。

 you put something else in serial fit， your processor gets slower。

 Or if your data catches on your critical path to your processor and you add something in thats。

 that's going to also slow down your processor。So we want to look at techniques where we can actually move those two structures off the critical path。

Alternatively， we can start to think about having something where we could pipeline the T。

 O B in the cache and have one stage for T， O B lookup and one stage for the cache。

It gets a little hard。 And that mainly over here in the data data side of the world。

 it gets a little hard because that's going to increase your access time to your data memory。

 So when you do a load， it's just going to push out that load an extra cycle if you put another pipe stage in there。



![](img/ee5f6966206d2795504414289bbe2a5f_2.png)

And in the instruction side， this could also hurt your branches。

 So if you add an extra cycle out on if you put a pipeline stage， something like here。

 then your PC plus 4 loop gets a little bit harder。 not from a timing perspective。

 it probably doesn't get harder。 but from a if you have a branch。Perspective。

 and you take a branch and you're going to add an extra cycle to your branch， mispredict latency。

And also， it gets a little bit weird here that you can't access your instruction memory effectively in one cycle。

 Having said that it's usually easier to take the instruction。TOB off the critical path， because。

You don't really change the high order bits of your instruction that often。

You really only change that。 You only cross page boundaries when you do like a far jump。

 or if you happen to fall through off the end of a page。 And both those are relatively rare cases。

 So people have found it's pretty easy to sort of take that off the the critical translation path。

So we're mostly going to focus on the data side of the world here。



![](img/ee5f6966206d2795504414289bbe2a5f_4.png)