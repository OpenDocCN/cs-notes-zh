# 【计算机体系结构】普林斯顿—中英字幕 p106 105_05_introduction-to-directory-coherence -BV1ii421D7WR_p106-

So let's， let's。Think about our snoopy protocols that we've talked about are bus based protocols and the performance and the asymptotic performance requirements of them。

So what are the challenges of a snooping protocol。As we discussed before， is as you add more people。

Or more processors to the system。 You have more entities shouting on one shared medium。And。

You need to hear the shouting。You can't just forget some。

 some shout because you need to snoop that against your local cash。

So whenever another core takes a cash miss。You need to snoop that against your cache and make sure that you don't have a a copy of that that you'd have to invalidate。

 for instance， or reply back with some data or do some other invalid or coherence protocol adjustment。

So。What's， what's annoying about this is if you sort of look at the amount of bandwidth。

You require on your bus。 All cash misses need to go across that bus。Everyone needs to look at that。

 and everyone needs to have a port that has enough bandwidth to look at all those transactions on their cash。

So。If you got to look at this。Our bus， if we want to sort of keep up。

With the same amount of bandwidth of cash misses per core as we add more cores to the system is going grow order N。

 where N is the number of processors。Because， now， you can compute this because everyone， let's say。

 has the same number of same amount of cache misses going on。

 And you want to have the same cache miss rate and just multiply it by n。Forree each。

 each course and I have that。 Well， that may be fine when n is 8。But if n goes to 1000 or a million。

You're gonna have some serious problems here。 That's a very， very big bus。

 And it's not just straight bandwidth。 You also need to have effectively some way to arbitrate for that bus。

 and you need to。Have atomic transactions going across that bus。 So it may be hard to actually。

 even if you have a very high bandwidth bus， you may not have enough transaction cycles。

In order to operate in the bus。So， solution to this。

Is we start to look at something we're going to call directory cash coherence or directory protocols。

And the idea in a directory protocol the， the key idea here is that instead of broadcasting。

Your invalidations to every other core in the system or all cash misses to every other core in the system。

Instead， what you do is you go talk to a location that we're going to call a directory。

And this directory is going to keep track of which caches have that data。

And what's nice about this is now， if you take a cash miss， you can go ask the directory， well。

 who has all these different， who has this cache line。😊。

And if only one other core has the cache line， let's say readable。Itll。

 and you're trying to to take it into an exclusive access。 you're trying to right to it。

 You only need to invalidate one location instead of sending that data to all end processors in your system。

So we've cut down what was a broadcast system into a point to point system。

But the overhead that we have to keep now is we need to track in a directory。

All the locations that have。Or all the caches， which could have。A particular cache line in it。And。

 and we'll， we'll go through a much more complicated example of that。 But that's。

 that's the overall key idea。And this is going to turn what was a broadcast。Into a point to point。

Communication。And we can use point to point interconnects for this。

Another good point of scalability here is you can actually have。Different directories。

 So you don't have to have one big monolithic directory。 Instead。

 you can segment the address space somehow。And depending on the address that you have。

 you can go to a different directory。And by going to these different directories。

 you can actually increase the bandwidth to your directories。Okay。

 so let's see how this fits into like a block diagram here。 we have。CPUs。

are trying to communicate other CPUs via shared memory。And they go check their cache first。

If it's not in the cache。Before they would have to communicate across a bus。

 and everyone would have to look at that traffic。But instead， in our directory cash coherence。

They'll send a message。From their cash。To the directory controller associated with the address。

So they're going to send a message here to this directory controller。And then direct controller。

Is going to keep track for every single line in or the the basic directory controller here is going keep track for every single line in memory。

V。List of possible other caches， which could potentially。Have that piece of data。

 And we're gonna call that the sharer list。Or the share list。And this is。Right now。

 if you look at this might still be a uniform。Communication network。 So let's say in here。

 you have some Oomega network。 Everyone can talk to anyone else， and the latency through it is fixed。

So this is still a uniform memory access system。 We've not。We didn't have to go non uniform here。

 So no cache is necessarily closer or farther away to any other piece of memory in a system like this。

So this is kind of our naive directory cash coherence protocol。

 But what's still nice here is we don't have to broadcast。 We can across our。

's say our Oomega network or mesh network or something else in the inside here。

 We like to send from this cache directly to this controller。😊，If no other cache has it， let's say。

 readable or writeable or anything like that， it can just respond back with the memory。

 the the data from memory， If not， instead of invalidating and broadcasting and invalidate to all other cores。

Instead， now。The directory can just say， oh， this core， this cache and this cache have copies。

 I need to send two messages，1 to this cache， one to that cache， and validate them。

Wait for the responses and then reply back with the data。So we can。

 we can decrease our bandwidth that we use in the common case， across our interconnection network。

So Im to show a slightly different picture here， which is very similar to the previous picture。

What you'll notice is that the。Memory and the directory now。Are connected to a individual CPU。

So why do we do this well。If you're building one of these scalable systems。

 some sort of like supercomputer。It might be a good property that as you add more CPU to the system。

 you also add more memory。And maybe more directory storage or some like that。

Another positive of a design like this is this CPU now is actually close to this memory bank。

And we can try to take advantage of that。So1，1 question comes up is。

 how can we take advantage of that Anyone' have any thoughts， Okay， so。Shared data。

We don't know where it's going to be accessed。 It could be accessed by all six CPUs and all six caches here。

But it's very common that your stack。For your program is going to be only access local。

 and the instruction number for your program is only going to be accessed local。

So you could potentially have performance benefits by putting。

The instruction and memory urge excuse me instruction and let's say stack and maybe even some portion of the heap close to this core。

Because then you can access that really quickly， but only shared data has to go across the interconnect。

And will。In fact， that has a fancy name。So systems where some data is close and some data is far away are called nonun memory access。

Or p Nuumma。And you might see this， actually， even in your desktop processors are actually。

Moving towardsneous systems。 there， some of them are are actually， you go look at some of the。

I believe it's the AM D chips today are already pneous systems even on。

 on a single die excuse me a single chip with multiple dies or something like that。 There。

 there will actually be two new nodes inside them sort of one for one memory controller。

 one from another memory controller。So。If you go into something like Linux， and you。

Go look in the proc directory。 you can actually see there's a subdirecty in there called Numa。

 and itll tell you the configuration of the different memory。

 And then the O S can take advantage of this。 So can put， for instance。

 the stack and the instruction memory for a particular program that's being used by particular core close to that core。

And then for me some other data can somehow choose some other， other choice now。I wanted to。

Make a important point here is that。Just because the latency to memory is different。Does not mean。

That your system is a。Diectctory based cash coherent P Nuumma system。So you can still have。

Non directory based systems， where some memory is close and some memory is far away。

So you can still have basically a bus or something like that。

 or maybe some other interconnection network in there。

 which is still a snooping protocol or effectively a snooping protocol。

 But some data is close and some data is far away。But if you were to see this in literature， usually。

 if people are talking about directory based cache coherent p nuuma systems， they'll call them C。

 C nuumma or cache coherent nuumma systems。And that's usually sort of means that this is a。

Cash coherent non uniform memory access， architecture and。Usually implies that's directory based。

 but there may be other protocols that people are using out there also。Okay。

 so I want to go back one slide here。 And I want to finish off talking about one topology。

 which is interesting。 And the difference between these two slides is went from a CPU here。To CPUs。

 So this is a multi core chip now。And where this gets interesting is you might to have a directory based cash coherence system connecting multiple chips。

 But then inside of a chip， you may have something like a bus based snooping protocol。

So you can actually mix and match these two things。And how we go about doing this is。If cash， if。

 if cores inside of this one。Chip， for instance， have to go get data from each other。

 They can just effectively snoop on each other。 But outside of that。

 your cache controller or maybe your L 3 cache for this particular chip is going to。

Respond to messages coming from other directories， like invalid requests and do something about it。

So there's basically transducer there between a directory based cash coherence protocol and a。

Bus based， Snoopy protocol。And this is pretty， pretty common these days。

 especially given that you have。Fair number of multi core systems showing up and being used in more of these。

Diirectctory based cash clear systems。 we'll talk about one of them at the end， actually the。SGI。

 U systems or U V 1000， which we'll talk about is a uses off the shelf， Intel parts。

Modern day sort of core I 7 parts mixed together with a p nuuma and directory based coherent system to connect all the chips together。

 So as a transducer from the external snoop bus protocol to the。Diirecty based coherence protocol。



![](img/8d54fecc93a9153d2c36b7147e8a5cf1_1.png)

![](img/8d54fecc93a9153d2c36b7147e8a5cf1_2.png)