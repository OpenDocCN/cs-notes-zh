# 【计算机体系结构】普林斯顿—中英字幕 p61 60_04_non-blocking-caches -BV1ii421D7WR_p61-

![](img/996af61a922788380c18ce85f2e3699a_0.png)

Okay， now we， now we get to move on to。The meat of today。

 we're going to talk about non blocking caches。Also known as out of order memory systems。

 also known as lock of free caches。 So I think the first paper that actually published on this called a lockup free cache。

 Lots of people call these things non blocking caches today。

 And if you think about it from a memory perspective， it's an out of order memory system。

What does non blocking cash allow you do？ Well， it enables。

You to have subsequent memory operations occurring from the main processor pipeline， even when。

You have a miss that was earlier in your instruction sequence。So in all pipelines。

 we've looked up to this point， you take even our out of water pipelines。

We were talking about them as basically saying， when you take a cash miss。

 you just sort of stop the pipe。Because we couldn't deal with having memory coming out of order。

 even to our out of order processor pipelines。 We didn't have enough bits to track all that。 Well。

 now we're going to talk about structures that allow us to track out of order memory。So。

Two major things this allows you to do。 It allows you to have a cash hit。Under a miss。

And it allows you to have a miss under miss。So what do mean by misunder miss。 Well。

 what I mean by misunder miss is you do access， like， say， a load to some address。

 It takes a cash miss。And then you load a secondary， but you keep executing your program。

And you another load。 and that takes a cache miss also。 And you're able to process both these things。

 If you have a non blocking cache， which allows you to have mis under miss。

One of the big points I want to get across today is that this is not only for out of order processors。

We talked a lot about out of order processors， believeve it or not you can actually hook up a non blocking cache to an in order processor or even a VIW in order processor。

Now， how do you go about doing that？Two， two major ways that you can do that。

 One is when you take the cachem， you mark the variable or you mark the register as not being there。

So when you go to actually read the data you block。

 So we'll show an example of that in a few slides up from now。But really。

 what I was trying to get across here is you can have in order processors without of order memory systems。

 you can have out of order processors without of order memory systems。Both these things are possible。

Okay， so challenge list。A couple of big challenges here。There we go。A couple of big challenges。

If you have multiple out of order。Mrs。Well， the memory system is going to return data sort of out of order。

You have to deal with this somehow。It's possible you might end up in a different memory bank。

 and the data comes back in different orders that you sent it out in。

 And this gets hard to deal with。 You， you sent out a cachem for X， Y and Z， and they come back in Z。

 Y and X order or something like that。 And you need to make sure you're delivering the right data to the right location。

 the cache and the right data to the right instruction。

So we're gonna need some big associative table to go figure this out。🤧嗯。Second problem。

 major challenge here is lots of times you were going to have a load and a store。

To the address that you want to take。A load and store missed to later。So what do I mean by that？

 Well， it's pretty common that you are going to be doing loads。Sequentialally through memory。

And if the first load in the cache line misses。The second load is also going to miss。

 but they're on the same cache line。You don't want to send。

Two of those out to the memory system at the same time， because you might confuse the memory system。

Worse， let's say if you have a load to one address and a store to another address。

But theyre both within the same cache line。 The load might go out to memory。

 start getting the new memory。 You do the store。 The store goes out to memory。

 and you actually store in the main memory somehow。

 But you bring in the original load data and they sort of pass in the in transit or something like that。

 the load data passes the store data。 And all of a sudden。

 you're gonna have the wrong data in your cache。 You don't have the updated data。

 And the reason that that ends up happening is because that store。

Didn't have any place to merge into。 It couldn't actually go deposit this data into the cache。

 for instance。Okay， so how do we go about handling this？ But before we do that， let's。

 let's look at a timeline here。Time。Goes from left to right on this graph。At the top here。

 we have a blocking cache， the blocking cache。You're happily running in the CPU。 You do a load。

 we'll say。Or store。It doesnn't really matter in these systems。

 and you take a cash miss in the most basic blocking cache， you're going to wait。

And wait for the cache line to get filled in。And then you can return the data and they can keep running the CPU。

There's no overlap happening here。But we want to go fast。 We want to go faster。

If we have a non blocking cache， we can take a hit under a miss。

So what that means is we're running along。We take a cash miss。This goes out to main memory。

But we don't stop the CPU from Mexican。So let's say it is a load。For Reg five。Well。

 as long as no one looks at Reg 5。Does the processor care that we took a cashmist to register 5？

Probably not。 Now， there might be some complexities around if that load to register 5。

Takes a trap or something like that， or takes an interrupt。Then it might care。

But let's say it doesn'ts for， one of the reasons that this is actually usually safe to do is that you've already done。

All the memory checks and you've done， you sort of pass the commit point at that point of the processor because you're already pretty late in the processor pipe by the time you know you get a cache miss。

 so it's not too harmful。But then you keep executing here and you take， you access your cache again。

 you do a different load， and you get a hit。That's great。 you just keep executing。

And it's only when you go to use the data do you stall。And effectively， we've we've overlapped。

Computation with our missed penaltyal。And this， this is， this is pretty nice。

Now something else we can do is we can do misses under misses。So a misunder miss。

 we're executing along here。 We take cache misss。 and we send out something out to the main memory system to go get the data。

But we don't stop executing， we keep executing， we take another miss。

we said that out' to the main memory system。At some point。

 maybe we actually go to look at the data or possibly。

Maybe we don't actually look at the data until here。 And the CPU just keeps executing the whole time。

 It overlaps multiple memory aes with。Computation。So this can be really powerful。

And you could do this， as I said， with in order processor。

One thing I do want to say is usually you have a limited number。Of outstanding memory aes。

Some small integer。It be like。Four or8， this dimension returns as you add more and more。

But usually you， this isn't sort of。Thousands of outstanding memory aes。

So let's look at the structure here。There's a couple different names for this thing。

 It depends what school of computer architecture design you come from。

 If you are from the Alpha or the Digital equipmentp Corporation design philosophy。

 you're going to call this thing a misad file。If you come from the Intel school of things。

 you're going to call it a misstead handling register。

 Mi status handling register actually predates Intel and。Goes back to， I believe， control data Corp。

There's a paper from Control Data Corp on M statuss handling Regs back in the like。

So out of the late 60s， early 70s。But let's look， inside of this thing and sort of understand what's what's going on here。

Youre can have some small number of mis statusus handling registers， probably in a register file。

And you have a valid bit。And you're going to have a block address。Now。

 this block address is not the address of load to the store。It's the address of loaded store。

 Its the address of the cash line。That aligns that load in the store， because。

What we're gonna to use this structure for is we're going use this to check subsequent memory aes or subsequent misses against previous ones that have been going on。

 And we may， may have multiple sort of in flight here。 and we don't actually need the address of the。

 the load or the store。 We need the address of the entire line。

Because we didn't check the entire line。Because that's what's in play。We' have a bit here。

That says whether it's issued or not。Now， why， why we have that is just because you took a miss doesn't mean it's actually out of the memory system or going to the memory system yet。

 So you sort of fill this in。And it sits around there until you have some time to go talk to the main memory。

 and hopefully。That happens quickly。 Some architectures that you may not even need this because you might just stall until it actually goes out to main memory。

But once it's issued， you tick that bit。 and what this。

 what this allows you to do is it allows you to have multiple misses which are not issued。

 So if you have a miss under a miss under a miss， and they happen really quickly。

 you can fill this table quickly and not actually have to wait for it to stream out the main memory。

 All the requests not to main memory yet。So that's half of it。

And then we have a bunch of load store entries。And with these load store entries。

 they also have a valid， and they have a pointer back to one of these entries here。

So this just is a number which says sort of which entry you're in in the mis statusus handling register file。

嗯。And this is for individual loads or stores that are occurring。

 So what allows allows it to happen is let's say you have a load miss to address 0。

 and you have a load miss to address。诶。I don't know。10。And these both are in the same cache line。

You can fill in this table with two entries。And they'll actually both point back to the same M statusis handling register location。

They'll have different offsets。And in the destination field。

 you'll fill in which register on the processor they're destined for。

So what we're going to do is we're going to use these tables such that when。A load comes back。

 or excuse me， when a cache line comes back from main memory。

 we'll be able to check in these two tables and do two things。 One。

 we'll be able to fill it into our cache somewhere。And two。

 we'll be able to return the data to the correct destinations。

And we'll be able to find which piece of data we need， given the offset in the cache line。That's。

 that's a mouthful to say。 So this is a little bit of a complicated data structure here to actually work out。

 Now， I wanted to point out where the associivity。Associative matcheshe versus。嗯。Indexed。

Matches happen in these tables。So one of the things that you might notice is that。This block address。

 we're going to have to check every subsequent miss。Against this block address。

So we're going take the higher order bits of the address。 Check it against this。

 And it checks that we don't add a new entry here。 instead。

 we just merge it into a currently pending one。 But we do have to add a new load store entry for that。

Which points back over here。🤧When。A memory transaction comes back from main memory。

 We're going to look back in this table and say， oh， here's the one that I， I had issued。

 I need to clear it out of the table。And given the number of the location that I'm clearing out a table。

 I'm going to sociably check that against all of the load store entries and wake up the ones that match。

So if this is entry number one。And there's multiple number ones in here。

 all the ones that are have number ones in here。 I need to。Return that data to the registers。Now。

 when I return the data to the register， I have to mark the register as being available again。

And the type here basically just says， you know， is it word， half word byte。

 And is it a load versus a story。One of the things I wanted to say is the destination。Here。

For loads is going to be the register identifier。Now this might be a physical Reggitry identifier versus a virtual regitry identifier or an architectural Reggitry identifier if you have a registry number。

So if you have out of order processor here， this might get more complicated。

 This is typically a physical register identifier， not a architectural registrtry identifier。

For stores。You also effectively need to track something in this table。

Because you need to merge the store with the background data。

 So this is going to basically add an entry in here。It's going to sound out to main memory。

 go get the background data。 And when that comes back。It's going to deposit that into our cash。

And we need to point at some other buffer。 This is very similar。 we had that future store buffer。

 You can have an array of those， for instance， and it'll tell you which one to go play the store against cash with。

 and you can merge the return data with the store data that we've stored locally。

So this is kind of fun。 We could have。Memory came back out of order。

 We have memory being issued out of order。Lots of， lots of fun， fun toys here。

 And one of the fun things we can do is we， we have an ability because this sosociative check here to check to make sure that the data coming back。

😊，Or you mean， subsequent requests hit or miss here and will merge。

 So we don't want to generate more memory traffic or cause strange things happening where you have responses coming back and new requests going off the same line。

 and you might lose some data in flight。I should point out this is only one implementation。

Lot of times what people do is in in this mis status handling register。

 there will actually be a tag field。Because main memory will not necessarily keep track of the entire address when you get a response back from main memory。

 instead， it'll just have a tag。So instead of checking against the block address。

 you might check against a smaller tag。嗯。That's one way that people sort of make this a little bit easier。

 Another way sometimes people will do this is the tag。

If you have a small number of cores might actually be which entry you are on this table so you don't have to do an associative check that sort of a optimization on this。

 you still need to do an associative check when future loads and stores that miss go out to memory you need you check in this table。

I think I， I think I walked through most of this already on Cash M。

 You could check the table for the match address， if found。You allocate。

A new entry that points to the misda handling register。 If not。

 you have to make both a load load store entry and a Mda handling register entry。

One thing I did want to point out here is if you run out of M sta handling registers or load store。

Entries。This is not the end of the world。 You could just stop the processor。 So if you have。

 let's say，8 of them and you run out of all8， you have 8 outstanding memory transactions。

 you just stop for a while。 It's gonna to come back at some point。

 You one of the loads or one of the main memory a he is going come back。

 So you can just stall for a little bit。Indeed to return。

You need to find the loading store that's waiting for it。 going back to what B said。

 it's very possible that a。The load in store that was waiting on it might have actually disappeared in that time period。

 at least for a load， because you might have a right after a right occurs。That's okay。

 You still want to fill it into your cache。At that point。And， of course。

 you can have multiple loads in stores。When the cache line is completely returned and you' finished checking against all the load in store entries。

 you want to decate both the load and store entries and the musttache handling register entries。Okay。

 so。A little bit of。Fun here with in order machines。

 So you can sort of see how this relatively logically fits into an out order pipeline。

 You sort to fit this into an in order pipeline。You can， it's not， not too hard。

 You can actually add a scoreboard。For each individual register。 And when I say scoreboard。

 you're not tracking where the data is coming from。 instead， there's a special bit saying。

This register is out to launch。 This register is out in the memory system。If you try to go access it。

 just wait。Or just stall。And then when the memory because it's a variable length sort of thing。

 so your scoreboard can't have， this will be ready in five cycles because you don't know it's out in the main memory system。

Unload miss here， you can mark， you mark the destination register as busy when it comes back。

 you mark it as available and you installs the processor。

But if no one actually went to go use that register in the meantime， while was out of main memory。

The main processor never stalls， and no one's ever the wiser。Okay。

 so I wanted tore almost out of time。 So I wanted to pick it up here for a second。

 So non blocking caches。They can。Effectively， increase the bandwidth to your lower levels of caches。

 your sort of L1s。The other thing they can do is they increase the bandwidth because they can merge misses to your cash。

Now， you probably would have actually gotten in it。Anyway， if you had a blocking cache。

 but the Mitache handling register basically allows you to have multiple cash misses merge into one transaction。

Your miss penalty is obviously lower because。Going back to this picture here。

 we've overlapped the missed penaltyalty of other useful work。



![](img/996af61a922788380c18ce85f2e3699a_2.png)

![](img/996af61a922788380c18ce85f2e3699a_3.png)