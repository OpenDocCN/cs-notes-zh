# uPenn《GPU编程和框架｜CIS 5650 GPU Programming and Architecture Fall 2024》中英（Claude-3.5 p19 2024-10-21 - CIS5650 GPU Programming Fall 2024 Lecture 12.zh_en -BV1sRtresE67_p19-

Yes。Before we jump in。Before we jump into the slide itself。

 I just wanted to go over the schedule a little bit so of course we are here October 21s。

 we are almost in November can you believe it？So today I will cover a small part of advanced Qa。

 I don't think it should take us too long， but Wednesday is essentially where we kick off final project season。

So， you know， start thinking about them， please ask those of you。

 your friends who who haven't attended class today， please ask them to make it on Wednesday because。

Like if you think all of the effort you've put into the class。The final project is 40% of your grain。

Suggestion in in putting that into perspective， please ask all your friends to come and attend on Wednesday。

Next week we'll have two backback lectures from Liam。

 Liam is a PhD student here at Penn who's done fantastic and this would be his fourth consecutive twopart guest lecture on machine learning and KUudDa and it inspires a lot of final projects so those of you who are。

Interested in dabbling into machine learning as part of final projects， again。

 these are going to be some two fantastic guest lectures。To attend。And then。

For the way we do final projects we'll do a page so that you present your ideas and stuff more details to follow on that on Wednesday。

 but during the final projects on November 18th we'll have our final gas structure。

 Gabe Deganni who's GPU software director at Samsung advanced Research Center in Texas and we had Ha and a few other。

Previous students TA or not T in turn with Gabe he's fantastic brings a lot of good knowledge from the industry into the classroom he'll be coming on November 18th and then it's like a home stretch to final projects once we start final projects we don't do any lectures we want to give you the time to focus on your projects itself。



![](img/0a975b25d69dd197a357dfb7db2b40e1_1.png)

The other thing I'll add， I've added percentage grades for projects four and five。

 so you can see that here， any questions。

![](img/0a975b25d69dd197a357dfb7db2b40e1_3.png)

![](img/0a975b25d69dd197a357dfb7db2b40e1_4.png)

Oh， all right。Let's dive in， then。

![](img/0a975b25d69dd197a357dfb7db2b40e1_6.png)

Okay。唉。

![](img/0a975b25d69dd197a357dfb7db2b40e1_8.png)

So today we are going to cover a few more topics so last class we covered streams and other things today we will cover a few more topics。

 atomic functions， whatt functions two very powerful ones， dynamic parallelism。

 which is an interesting concept if applied correctly in then independent threadcheduling in cooperative groups kind of。

In a way through everything I've taught to you so far about threadscheduling out of the door。

 but again it's these advanced concepts so you may not apply them all the time。

 so let's cover them as they come。All right。So first of atomic functions。😊。

Just like in every parallel programming paradigm， there are going to be times where you need to do atomic operations where you lock something and make sure that nothing is either reading or writing from that as you're operating on that memory。

Right so if you take an example like this and put it in a device kernel。

 what do you think happens here？What do you think the value of this might be？Yeah， Nick。

Anything between。Yeah， anything between one and8 your spot on there it depends on how。嗯。

How exact the timing of updating that variable is going to be if all threads。

at the very same clock cycle， try to update it， they will read zero and they will add it to one and then all of them have a race conflict to write to one。

If all of them do it one after the other， then they will do it to eight。😊，Basically。

The line of code you've written is undefined and the result is undefined right you haven't described what your intent is there very clearly to the program。

😊，So， this is not clear now if you intend for that each thread adds increments the value of count。

Then in that case， that's why you need to use atomics。So this is an example of atomic a。

 which is a bit in function in Kuda。Which essentially takes this variable and for each thread。

Adds one， which is an incr to count。 And this is done by an atomic way。 Now。

 what do you think happens。嗯。When you use a line like this in a coa kernel。

Like what's the implications of it？Yep， like any thread that wants to act on account has to wait for that one day。

So it could kind exactly， it's not just eight threads。

 but depending on how many threads you have in the block。

 it will entirely become serial so you can see how much it could impact performance if you use it in the wrong ways。

Okay。So。Diving a little bit into atomics。I want to like while this is a bit in function in Kuda。

 I think it's interesting to explore。😊，How you would implement something like this。

 because are there a bunch of built in functions in Qa。

But they're not everything you may want a different type of atomic function。

 there's a different type of atomic operation that you may want to do so in that spirit。

Let's look at how we would implement an atomic ad。If we were given an atomic。

Competence in operation like this， so if this function wasn't written。

 how would we implement it and it looks something like this。Where。

We would create our own new function called device end。

In then atomic add and we would take a pointer to the address and the value to increment it by generally clear on the function definition。

 but let me know if you have。If you have a question。We would。The return value here is the old value。

 so we want to store the new value in address and return the old value okay。

So we will create a variable for the old value call old and then we will have some form of a lock here。

😊，We are making up that word， there's different ways of doing it。

 but let's say there's a lock API and it locks the address。If that block is successful。

 it will go in and implement， execute these two instructions where it throws the value of address into old。

😊，And then increments the value of address by value。

And then returns the old value right if it's not successful。😊。

It will it's kind of like a two while loop then。So， as long as lock is false。

 it will iterate until lock is true once lock is true it will execute and then return。

Does that make sense？Any questions on this？Okay， so you can use this as something you you can use。

In with different atomic functions to build more complex atomics that you may want to write in your k kernels。

So ultimately， you're minimizing where actually lock happens。Okay， so like we said before。😊。

In a function like this where you're doing this kind of a doai loop to get the lock。

It becomes completely serialized， you may have all the threads。

 each thread tries to acquire the lock， but only one thread can get a lock at any given time once a thread gets a lock it executes。

Once done otherwise all the threads will loop around it。Okay， again， remember for this code。

 if you were to implement something like this。😊，嗯。The threads still have to execute even if they are not doing anything threads and warp execute together right so that is still going to happen that's why this diagram kind of has the arrow down from unlock backup not just from lock backup okay。

This thread has to execute in lockstep with the warp。嗯。Okay。third， okay。So。

There might be a different way of doing this。Which is to not use。Loocks。

And that's done using something like this here。We call this function our atomic compare and swap。

Which is also built in Kudaf Atomic。If we were given an atomic compare swap and guaranteed that it didn't do a lock。

How would we then implement an atomic ad without using a made up block function， right？

So here's an example of that。Just atomic cash， atomic compare and swap， what it does is。

You take an address。You compare it to a value。If the value is true。It returns。

It stores a new value and returns the old one， right？m sorryrry。Click the wrong thing。

 it's kind of like this。This comment here， old equals compare if true。Return value or return old。

Like set the value and then return old， so it it's comparing if true， swap the value。

So let's take this example and let's say we have this API and address starts with one。

In the first line， once that executes， what happens is address is compared to one。

Is that true or is it address one， that's what we are comparing。Yes， address is one。So。

 we are going to put two in address and return the old value。Okay。

So we address now equals 2 and returns one。What do you think happens in the next line？

This is not one。Address is not one so。So。走合飞啲ます。Right， and what value gets returned？Yeah。

Always old is returned so in this case the compare has failed because  one not equals 2 right so we dont do a swap。

😊，And return the value from address， okay， what happens in the next slide？Youhan。Exactly。

 address goes to three because address value is2。😮，So the compare is true。

 swap the values and return the old one。So that's kind of what we do。So by doing this， Comp swap。

Give you。A way to do。Atomics without actually locking。😡，Right。

 it allows you to compare if the value is exactly the same。

 you then it gives you like this in to actually do something。😊，Otherwise。

 you just continue on as usual， so you avoid the lock。So now if we come back。

 how would we do an atomic ad if we were given atomic asthma？Yeah。Let's stopping another thread from。

Something thing。Like well， one I just from carrying another。Yeah， so the idea here is。

If because you're。Because you can compare the value to something unique for that thread。

The each thread can have a unique compare。So it's like the swap part is what you can customize in a way。

The compare can be unique to each thread。Basically what we're trying to change from the locked mechanism。

Is how it will cause divergence。Whereas if we use something like this。

 all the threads will continue executing along the same time step。

 but not actually change the value of address。So if if you were。

 let's say we had a warp of 32 threads right， let's say a block of 32 threads。

 we can give each address。Compare it to thread IDX， for example。If that's equal。

 then we will change the value。Something something of that sort can be used to create more convergence of threads rather than divergence of thread with a made up block。

Okay， so if we were given atomic cast， how would we implement an atomic ad so now this is again building blocks that I was trying to explain before。

So that would look something like this， so our atomic ad function definition remains the same。

We will store old。😡，As the value in address and then also create an assumed variable。

And then we do a do while loop。What we want to do here is do。Store。Assumed as old， okay。

 this will make sense in a bit and then do a compare and swap on the address。

Assumed value and then value plus assumed because we are adding right so this value is what is value or what is in address plus the new value。

So the result we know if we are able to successfully do an atomic has。😊。

We know the result in address should look like that。Okay， that's clear， right？Now。

 the reason this works address and isd is because in compare swap we are。

Checking if the value in address is the same as value in assumedd。Right。

If multiple threads were trying to change this。😮，It would fail。So if this specific thread。

Compared address and resume and got the same value。Then it can do the compare swap and then exit。

Otherwise， if it failed at atomic gas， then assumed an all would be the same。😮，Sorry。

 not be the same and then you have to do it over again。新だ。Is't it still essentially cere？In a way。

 yes。What we are trying to do is make the best of a bad situation。 I'll put it that way。

 You're never going to get true parallelism。For an atomic you have to have at least one small atomic operation in there what we are trying to do is minimize the amount of divergence it's causing so yes it will still be very serial。

 we just don't have the overhead of creating locks and unlocking and stuff like that。So。

I guess going back to something like。Our core fundamentals in Kuda， we are saying computer is free。

 memory is expensive， try to minimize how much memory we are using that's kind of a concept you can think of as well。

嗯。So I covered that。😔，Cward that。All right， any any more questions on on how we've kind of built up a building block of atomics here？

Okay， so so saying they built in atomic functions here。

 there's a bunch here so you can see atomic ad atomic cache are both built in。

 so you don't actually have to go reimplement these。

 but if you are building something more complex and you wanted atomics for that。

 then you can use all of these atomics to actually do those kind of operations。嗯。So。

You can have different levels of atomics as well。😊，If there's no suffix。

 then it works on the device scope。Atomic system works on the system scope so it does an atomic operation on CPU and GPU and then if you have a block suff then you can do a block level atomic as well these are all fairly new its you can read the programming guide for how to use these more again。

These are worst case scenario right you ideally don't want to use any atomics。

 but if you really have to use them then you can do this can anybody think of an example where atomics would be useful。

Maybe not the best case scenario， but where can we potentially use them in an algorithm we've seen in the class？

yeah parallel reductions is a fantastic example because if you remember parallel reductions the reduction in the block is all parallel super optimized right but to do reductions across block we were launching either nested reductions or copying it the CPU now if you were to say。

😊，Hey， I want to do atomic reduction for all the block results。

 then you can do that using a single thread and it would work so that's definitely an example of using atomics。

Okay。嗯。The other question is if you have。Threads from different blocks。

Can you think of a way how atomics can help？Work together。Nick。Yeah。

 you can have like some kind of global variable that you on Yeah， exactly you could。Don't do this。

 Cardinalson。Don't run atomics on global memory， okay， bad idea。😡，As much as possible。

 run it on registers or on shared memory。嗯。There's nothing stopping you from running atomics on global memory。

 you could potentially have your entire kernel all the threads and blocks you launch the entire grid of millions of threads running atomic on a single variable entirely possible nothing's stopping you you're just turning your program into a completely serial one so don't do it but in the right case for the right reason you could use atomics on global memory to actually communicate information between different blocks to do that。

😊，So use atomics theory， I think we discussed it， this so that it's not clear what I was saying about the first line。

Different blocks in collaborate。That's effectively like I sync threads across blocks。

Right if you if you have blocks and you put an atomic on it。

 all the blocks are going to wait until that gets done now there is a resource。

Limitation that you may have to consider， but effectively you could do that。Okay。

 so in conclusion for atomics， they allow you to create much more sophisticated algorithms。

 you want to use the atomic functions as building blocks for more complex operations if you wish。

 but they also foresee utilizationization so use them as sparingly as possible。Okay。

Questions on atomics before we continue。All right。All right。

 let's go into war functions which are really， really powerful and very。

 very cool and well take some getting used to。😊，All right。

Fundamental question from our first class our first two classes。

What are the ways in which information is shared between a block？嗯。Everybody forget？

Shared memory and。Blooming river， two waysiz。Shared memory and global memory right that's how threads know what memory exists。

嗯。But there's really one more。Which is called what level functions， and these are essentially。

Ways to share registers between threads。嗯。Actually， I should correct myself。

They're sharing the information within registers rather than the registers I。

 the registers are connected to the core， they're sharing the information within those registers without using shared memory。

So the first one of these type of functions。It's called what Vo。

Share what is happening is each thread in a warp， not a block， each thread in a warp。😡。

We'll do a broadcast and reduce operation。But that what we mean is。

All the threads will give their value into a pool。😮。

And that each thread will collect the result and process it， okay。嗯。

So there are three types of functions here， any， all and ball okay and notice how they all return inch。

 which will make。Sense it a bit。All。😮，Checks and all of these do some predicate。

 a predicate here and pretty much in all of Kuda when you see the word predicate。

 it means a condition。Okay， it's checking for true or falses。At all。

Basically by what it means is if all the predicates are true， return  one， otherwise return zero。😮。

For any， it' is the opposite if any of the conditions are true， return true， otherwise return false。

For ball， this is where it gets interesting。😊，Ballot is。So this。This is true or false， right。

 it's a predicate， it's true or false， even though it says in， it's true or false。

This is unsigned in。Okay， here we are doing a reduced operation。Here there's a very cool function。

Because what it does is how many threads in a world？😊，そて。32。How many bits in an un signedigned in？

WhatHow many bids do you need to store or true or false one so what this does is it getss you the result of every predicate stored as a true or false in your assignmentign？

😊，So lets look at that in a bit， so I've kind of explained the all basically if all predicates are true。

 it will return true so now。What is the result of something like this？The first line。

 let's take that as an example。What will be the result of the first line？should be of。False。

 how many of you say false？Okay， most of you， yeah， in most cases it will be false。😊，嗯。

II can't really think of a scenario where there's a crazy configuration we launch where all the TD IDxs are one so the first line will be false what about the second line？

And。Depends on the word， so tell me which words will be true， which forms will be false。啊。

The first two wars will， will be false。The rest of the world would be true。

Yeah yeah pretty much so if you have if you have a 1D block and let's say you launched 256 threads。

The first two wars up to thread 63 would be false。But all the others would be true。

The reason I want to show you these two examples is。😊，This thread id extra x equals 1。😮。

Could be a different line of code as well， and it can almost be customized。😊，To each thread in a way。

 because like thread ID extradex is a value specific to that thread so each thread is giving its own value into the predicate。

 you could use any variable here here you don't have to use a built in variable so you can you can you have an element of customization。

😊，Okay。Let's do any， what about this？What do you think is the result of the first one？

True for the first warp and false for the rest， okay， anybody have a differing opinion？Noello。Okay。

 here's my differing opinion， what if it's a 2D block that is 32 by 32？

Then every every warp will have at least one thread ID x dot x equals 1 because thread ID xtrot y will change。

😡，Right so you have to think about the configuration there。What about the second line？Nick， again。

 assuming no trap that we're absolutely one。Fair qualification be Yeah。

 pretty much for that reason yeah if you have a 2D block。

 then that's going to differ based on your launch configuration。😊，Okay。Any questions on any or all？

Okay。Just ballot。So remember how I said that itll take a condition and then store the result this kind of what happens。

Let's assume we in the first warp。Forth be， thread IDx equals 1。This first bit will be set to 1。

 all the others will be set to 0。If you had something like the thread IDx dotx mod2。

 then you're setting every alternate element to001。Right？This can be extremely powerful。

Because you can use it for some really cool things。

 you can any of you have ideas on what these can be used for？Look。

 you're doing like some kind of a noise function or whatever you're kind of do something。Poten yeah。

 what else Mike？Compaction yeah， what is more fundamental form of compaction？More fundamental， yes。

 reduction is you can do it with this， but what's one level below？You can use this。

To check if a thread is active or not。Remember in your path。

 twicea you did stream compaction and you were doing stream compaction so that you were exiting early。

 right？Now， let's see as you。You're doing stream compaction at the end of the pass。

 right end of the pass tracer pass， but what if？You'd come in a crazy scenario。

 which is maybe not all that crazy where all the threads in your warp。Have exited but one。

You're then executing a Syrian war， right？What you can do with something like this is ballot。😊。

Whi threads are active。Right。And then if you can count how many of these because it's bitwise。

You can count how many threads are active and you're like， hey。

 only one thread is active in the warp， I don't care about the result of this thread I'll just calculate it in next time it's Monte Carlo anyway it doesn't matter if one result changes here or there and then you can exit to improve performance。

😊，So ballot can be very powerful for things like that where you exit wars early based on sub heuristic that's interesting to you。

It can also be used for things like histograms again。

If you want to calculate how many threads are active across an entire block or entire grid。

 then you can also use ballot to get an assessment of histograms there。Okay。Questions on this。么。嗯。So。

 like I。Yeah。Yeah。So if you have like a 3D launch。嗯哼。😊，30。So it's always。

 it's always the threads in the war。Inmtigration。The warp is always 30 to consecutive threads。

Let's say you have a 16 by 16 block right what you'll have is。

Thread ID x 0 to 15 somewhere in the middle with thread ID x dot y equals 0。

Then you will get thread idx do x equals 0 with thread idx do y equals 1 and then so on from there。

 so the warp is always 30 to it is always implicitly linear。It's the concept。

 even blocks you can think of implicitly linears， the 2D is for human aspect。

 so if you had a 16 by 16 block then you would get1 be true here and one be true somewhere here where thread extra x equals1 for y equals1 as well。

Other questions？Okay。All right。So。W war essentially allows you to remove branch divergence in certain ways by collecting that information。

 note how none of these examples， any all or ballot actually used any sharedd memory。

 they didn't use any locks， they didn't use atomics。

 they're all operating in parallel getting you a result。So that's very powerful。

If there are inactive threads， like I was saying， if you want to count how many active threads there are ballot pits are set to zero and then any and all ignore active threads so they don't count in the computation Matt。

So this is不 going walk out。嗯哼，你快你两客。No it's operating completely on registers completely parallel。

 completely asynchronous yeah， so you don't have to run synchronous。

 that's why it gets you a lot of performance。Okay， so so yeah these these conditions are true if the threads are interactiveactive。

 so basically if you wanted to see how many active threads you end up on award award。

 all you have to do is ballot true。If you do ballot true。

Only the threads that are active will actually set the bit to1。

 the inactive threads won't set anything， so that's like a trick you can use here。嗯。The API changes。

 pretty much everything I've shown here is after Kuda 9， before Qa9。

 the API was slightly different but essentially the same。Okay， any questions on what what？Okay。

All right， let's look at what shuffle now shuffle is extremely powerful but also a bit confusing to understand。

😊，So in what port， what were we doing， we were taking the results。Of a predicate。And sharing it。

 we weren't actually sharing the value itself， right。

 We were sharing the accumulation of a certain result。Shuffle shares the actual value。

Of the reistries。And that's why it can be very powerful it's all single instruction like I'm saying a PTx is the assembly language for Ka it's single instruction。

 no synchronization works within an war， no shared memory and it's really really fast。😊，Okay。

 so let's look at this。

![](img/0a975b25d69dd197a357dfb7db2b40e1_10.png)

There are four types of shuffles。First is indexed， then you have up and down and then you have butterfly or XR。



![](img/0a975b25d69dd197a357dfb7db2b40e1_12.png)

嗯。There's some examples here。Let's dive into each one of them。In index。

 you're going to use the shuffle with no prefix or suffix。What you're going to give it is a variable。

😊，A source lane and a width for our exercises here we are going to ignore width you are always going to consider it to be more upsized。

 but you could give it a different width if you wanted to up to 32。What you're going to do is。

For the variable， you're going to say。Switch it based on the source La， get me the value of v。

In source Lane， okay？Remember， we don't use T index here。Where else did you see Laing。

 you saw lay in the debuckers and the profilers， right？Lane is a hardware concept。

 lane is tied to wars。Your lane value has to be between 0 and 31。Otherwise it will be invalid。

 so you're giving which lane of the warp you want to swap the value with。

And that's what you're going to get here。So let's take a look at this example。Essentially。

 this function boils down to this t equals y of source frame。If you have。

The original lane Is up in the Maroon。You v values in this peach color or gray color and then source lane that you should swap the tea with。

 this is kind of what you get。嗯。For thread 0 right or lane 0， the value of t becomes p。😡。

You're not changing the value of whatever wire is， you're getting a new variable。

 you're getting a new register。That register will source the value of P。

 you're literally getting the value of V from another register and soring it in your own register。😊。

Okay，s copyied by value， not copyied by reference， but you're copying the value into your own thread and so on。

So literally you can put any index and you get that here。Source lanene is。Is。

Independent for each thread， So all the threads can give the source same source name。

 they can give all different source names or any order。

It can be completely independent and still works in deterministic time。Any questions on this？

So like so lane doesn't。方。No， you don have you don't have to have 0 to 31。

 you can have all same all different ordered， unordered doesn't matter。

Because each threat can pass its own social lane。Any other questions？Okay， this will all build up。

 you'll start seeing where something like this can be used。Shuffle up。

Is kind of a right shift by a delta in this case we are not giving it a source lane we are giving it a delta right so if the delta were let's say5 in our example what we are essentially doing is v of its own lane。

Minus delta。So in this case， 0，1，2，3，41 change， there is no circular operation here。😊。

Lain 5 is the first one where the lane minus delta is valid， so its 0， so that gets the value of a。

And so on， so it's kind of like you're copying the value from the left lane into the right lane。

 so that's why right shift by delta。不是。Questions are up。Is there a reason it doesn't wrap？嗯。

That's how the docs said。I don't have a concrete reason why in hardware it can't do it。

 but according to the documentation， if the value is less than zero then it doesn't wrap around。Yes。

Other questions here？Okay， down predictably is shift left。Okay。

 here instead of doing minus we will do a plus and so basically the right set of lanes don't get a different value for t。

But for all the others， it kind of gets the fifth value after its own lane。

So same thing now in this in both up and down， you can see why warp size would make sense that if you wanted to change the size of the operation。

Then you can change the width to and width can only be1，2，46 1，2，4，8。

 16 or 30 do you cant have random values of width， but if you were to reduce the width。

 then you can see how you could create multiple circular loops within the war。Okay。

Questions on up or down。All right， let' us look at shuffle， butterfly or shuffle XR。

 and this will get a little bit confusing so feel free to ask questions。The way this works is。😊。

What you're going to do is。You're going to get。The variable T。

You're going to get an unsigned int on the lane mask， kind of like indexed。

But the difference here is the target lane where you are going to copy the value from。

Is going to be an XR operation， a bitwise XR operation on the lane ID of that thread。😊。

And whatever lane mask you put。Okay。And I'll show you a few examples。

 so the result will be bar of the target lane。😊，Okay， so let's take a look at an example。

So let's say we have this， okay？The values。Sure。Let's say I give it all lane mask one。

What happens here is。A， which has lane zero。If you do x or of0 with 1， you will get1， right？So。

 youll get。The value B in T。whereas b lane id is 1 mask is 1 x or will be 0， so you get a。Okay。

Similarly， C now you have two， which is 10 in bit。😊，If you x are with one， which is 01。

 youll get 3 so youll get the value from D and vice versa you'll get D and C。

 so this is kind of like swapping neighbors。Right if you do something like this。

 you're swapping neighbors。You could give anything you wanted in mask。

 I'm just making up this example of one to show you how it creates a neat pattern。

 you could give anything and it will create very very powerful patterns where you can swap values very fast because it's all registers and very very quickly。

Let's take a look at another example， so here's a few random values。

Let's say lay ID is six and you give it a mask too。The destination is X of this， which is 10。

 so you get 1，1，1， you get 0，0，0， you get0， so the destination becomes4。

So you get that value getting copied into lane 6， so T T。Of lane 6 equals v of4。Similarly。

 if you had lane 10 and Ma 3， you have 1010，0011。The destination becomes 111001 as an XO operation and then you get destination 9。

 similarly for this， you'll get six so it can create these powerful combinations that youre not exactly。

嗯。Doing as a loop or swap or anything， it can be pretty random。

 but using it in the right way will get you some powerful combinations there。So。

Where do you think this can be really useful， these kind of examples that I've shown？

We've covered something like this in class。嗯。In pattern reduction， Matt， how do you think that works？

Right end of right。そしたうん。Potentially。But which part of reductions that we covered where this would be most applicable？

Yeah， I guess like in the up sweepep step， like we we are only ever like operating on things that are like due to the power of some some K index or so we can just like use this to。

Compact there also one side。You're talking about scan in upwe yeah okay so okay I get what you're saying instead of doing right to left you're saying you can potentially do it the other way too I'm asking more like if you think of it from a court perspective。

Where can something like this be super powerful？All right， this will refresh your memory。

You remember this？Can anybody explain what might be going on here from memory。

 we kind of covered this in the performance lab。If you remember in the performance lab。

 we said for reductionuctions。We are going to create this。

We are going to remove branch divergence right， and we remove branch divergence from the entire block except the last warp。

Right well in the last warp you get this kind of divergence where half the thread stopped working and for that we created this war produce function which was adding on shared memory and doing this kind of operation which works。

 and we proved it works， but it's different its values like this。

And it was using shared memory now what faster than shared memory？Registers， okay。

 so how do we go from using shared memory to using registers to improve performance even more？



![](img/0a975b25d69dd197a357dfb7db2b40e1_14.png)

So here's a slide on this。What we were doing was something like this shared memory thread ID X。

 shared memory 32 times v I plus lane ID and more 30 so that's what this code was if you make it more general and then it did the sync threads。

If you do it using shuffle， it's like this operation here。No shared memory。And by doing X。

This lane ID formula， now you' are doing this x or the lane itself。

Right and this is a valid operation like I wont do it on a whiteboard。

 but this is a valid operation and literally gets you what you need to。😊，So now if you were to。

Do this。

![](img/0a975b25d69dd197a357dfb7db2b40e1_16.png)

Without sharing memberia S， which is kind of what we did here。

 we are doing this here in an unsafe way。

![](img/0a975b25d69dd197a357dfb7db2b40e1_18.png)

Right。So。What we get is。This kind of a performance improvement where you have shed memory。

 sharedd memory unsafe， which is what we did here again see。



![](img/0a975b25d69dd197a357dfb7db2b40e1_20.png)

![](img/0a975b25d69dd197a357dfb7db2b40e1_21.png)

嗯。See how we use volatile float SM。

![](img/0a975b25d69dd197a357dfb7db2b40e1_23.png)

That's what we have here， volatile creating unsafe。



![](img/0a975b25d69dd197a357dfb7db2b40e1_25.png)

But shuffle gives you a pretty decent performance improvement based on that and even from shared memory。

😊，You're using shared memory， you're not using shared memory。Again。

 when you think about block optimization and usage and all of that。

 not having shared memory is pretty powerful and you could increase how many blocks you are trying to fit in your occupancy。



![](img/0a975b25d69dd197a357dfb7db2b40e1_27.png)

So。To do something like that， basically you are removing the need for shared memory。

 everything is that registers。You're not using sync threads， you're not using volatile。

So this kind of operation using shuffle is always faster than shared memory in every way possible now this。

Example is essentially that last 1% last 2% of performance that you will extract。In a lot of cases。

 you may not need to go this far。😊，But when you really care about that last 1% of performance。

 you're going to use tools like this to get you that and think out of the box on how you can do this kind of an indexing。



![](img/0a975b25d69dd197a357dfb7db2b40e1_29.png)

So to show you how it's actually done in code， here's the example。Let's say a warp size is 16， right？

Are sum plus equal shuffle x or sum 16。What's going to happen here is。嗯。

16 is what one followed by three zeros， right？Or four zeros， four zeros。

What that means is all the threats to the left。😮，Will return will return themselves。Plus。😮，16teen。😡。

Because that bit where 16 is stored， the fifth bit will be zero for all the threads on the left。

And one for all the threads on the right。So that way you only add the threads on the left。

And so on will this will continue to do so so that way you can remove the shared memory operation and use the shuffle Xor so these are kind of the replacement lines for each of those shared memory operations here if we had space4 32 threads in our slide we would have had a 16 version but if you have 842 and1 you are done noing threads no shared memory。

So here's what the actual code looks like。If you were to implement。

 you can have a warp already some function and then in a for loop you can do the shuffle XR to do this。

There's a way to do it but shuffle down as well， which you could。

 but shuffle like aura is generally the preferred method here。啊。

You could also potentially do this for all wars， not just for the last warp。😊。

You can can do this throughout and then for。Maximum 32 wt per block， which is 1024 threads。

 then you have 32 additions and you write that to global memory。

So it's a really powerful way of expanding shuffle。So to do that in code。

This is the entire reduction operation for an entire block。You you get some shared memory。

 so 32 values to share the result of each warp with the block。

 so you have shared memory for that so you're reducing the amount of shared memory needed。

You compute a lane ID and a war ID right just like you have thread ID and block ID。

 you're computing lane ID and a war ID have typo there。嗯。

Then you do the s reduce function that we just saw。And if your lane is zero。

 then you put it in shared memory and have a sync threads for that。Now at this point。

 all the vers will be synchronized and then。All you have to do is for the first warp。

 you can run reduce。😊，On the shared memory by copying the shared memory into value。

So the shared memory basically serves only as a temporary storage where you're writing once and reading once。

 and then everything else is in the register operations。Any questions on this？No。Okay。

This kind of becomes the more simplified kernel where you have a device reduce kernel and then you're running this over and over again by doing a block reduce sum function here。

Okay。So in conclusion for shuffle， it's one of the most powerful tricks in the book。

 once you start knowing how to use it and start being creative with the algorithms。

 it can get you actually a lot of performance even over sharedd memory when used the right way like we saw with introductions。

😊，But reductions are not the only way to use it， you can use it for scan sort transpose。

 which we also saw in in a performance lab， you could potentially use shuffle for that because at that point。

Your shared memory within the block。What do we run into bank conflicts， right？

And the way we resolve that is by adding more shared memory。

But if you use shuffle and you swap values between registers， no sharedd memory。😊。

And then you can speed it up really fast because all you're doing is swapping one value at a time all in parallel。

 so you get really， really good performance numbers using that。Okay， so yeah。

 think about using these as you're doing more kuda， it can be really， really powerful。😊，All right。

 let's look at a few of our last concepts。Which will be a lot less。Things you'll see in the wild。

 but still equally useful depending on the algorithm you use。

So dynamic parallelism was introduced in KUuda 3 or not Kuda compute 3。5。And is a way to。

Have kernels。Launch other kernels again I told you this will throw some of the most fundamental things about kuda I've taught you out of the door and this is true about this。

One of the most basic things I've told you is kernels can be launched from the host and only from the host。

Not true in dynamic parallelism， kernels can be launched from other kernels that way you can create additional parallelism there。

So。You can create launch and synchronize kernels from other kernels you don't have to return to the host to do that what you get is like a parent child relationship where a parent has a launch configuration。

And if you launch the kernel， that becomes the child kernel and until the child kernel is done。

 the parent kernel will wait okay。It has an implicit synchronization guarantee。

 so diagrammatically it looks something like this where you have a grid of blocks and threads for kernel A。

And then if kernel one thread in kernel A launches a kernel B。

 that needs to execute and only when that gets executed， can it return execution back to a？Okay。

So it's like nesting essentially。嗯。What you want to do is track the dependencies that you have via streams and events like we saw in the last class。

And then the kernels and objects are visible to all the threads in the grid。

Remember that because you're not launching from the host。

 you can only pass variables to the new kernel that are already available to the parent kernel itself。

 you can't create new variables and stuff that you're passing， so that's very important。And。

It will follow the stream ordering semantics as well。

 so the same operations order of operations we learned last time will apply to dynamic parallelism too。

In terms of memory， your global and constant memory is shared with all kernels and that remains true here as well。

😊，Um。Me operations before the child， so any anything you may have done in the parent before the child kernel was launched will still be available to the child。

 so that remains true because within a kernel the operations are synchronous。嗯。

The child's memory operations are not visible to the parent Ie registers and stuff。

 global memory is visible once the child kernel is complete。Global memory will be visible。

 but registers and stuff won't be。Excuse me， you can use this this kind of flag here kuda stream tail launch to actually see it。

 but that's way more advanced than you need to。A child kernel will have distinct shared and local memory。

 it's not visible， not shared with the parent， it's completely independent。

 just like with every other kernel you've seen so far。So an example of something like this is oops。😊。

嗯。Cings coin。Okay。So you end up getting something like this。如是。

In a super simple dynamic parallel example where you have in host code。

 you're launching parent kernel with some configurationflration。In the parent kernel。

Your specific thread will launch a child kernel and that child kernel will operate。

 you'll want to sync threads after that just so that you're synchronized and then you can continue stuff later this is kind of not for this specific example but this is an example of how dynamic parallelism could work depending on the types of kernels and functions that you're launching。

嗯。Any questions on dynamic parallelism？Where do you think this could be useful？Recursion。

 yeah exactly。 So remember when we did reductions we also had the in in performance lab。

 we have the reductions recursive。😊，This could avoid that by not returning to the host。

 but like one thread will launch a new kernel to do the reduction， right？其些边搞。Yeah。

But I feel like they would be sort of overhead。said that shared memory。Right， right。

 you will have to copy shared memory into a global memory and then pass it to the child here。Yeah。

 it kind of defeats the purpose then because again。

 the thing you have to remember about shared memory at registers is that context and that context lives inside DSM。

But your child kernel can be launched anywhere， there's no guarantee of where the blocks will launch so you can't share that shared memory and again shared memories per block。

Which shared memory are you going to share if you're launching a new kernel。

 that becomes complicated too， so that's why you can only share global memory。嗯。So。So yeah。

 dynamic parallelism。alows for cleaner code， it enables recursive algorithm。

 it doesn't guarantee more concurry because you're still limited by the same hardware limits。

And you want to be careful about how to use data between parent and child colons and how much dynamic parallelism you create。

Now in practice I've actually never written a line of code that does dynamic parallelism。

 there are theoretical concepts that help like we discuss with recursive reduction。

 I think some of the AI and ML concepts are using recursive reductions a lot more so if that's of interesting you may want to explore that more。

All right， second last concept for today。Independent threatcheduling now again。

Throwing breaking down everything I've taught， right？I've said。

 there's no such thing as threadcheduling， there's only warpchedcheduling， well。

 this kind of breaks that paradigm。Where in the newer architectures。

 Vol which came out about five years ago， you can start the scheduler can actually more independently schedule threads in a war。

 so instead of having all the threads do the same thing simultaneously it can do more complex scheduling。

So。What it does is it allows for full concurrency of threads regardless of the warp。😊。

It allows for threats to diverge and reconverge as subwar granularity。

It doesn't mean that different threats can execute at the same time， different lines of code。

 but it means that there's more flexibility in that。So here's an example of it。😊。

You're familiar with the top lines of code， I've showed those many times， basically you diverge。

 you do AB， then you do X Y， and then you reconverge。

In the newer architectures and you don't really have to do anything， this automatically happens。

Where。It could even do statement wise diveer， so you can do a， then X， then B， then y。

 and then z and z， not how Z for both subvers， subwarb groups happen at different times。

 whereas in the old thing Z would have happened at the same time。

So this is a more powerful scheduler and allows you to take advantage of that by creating programs in a certain way。

😊，Where do you think something like this could be really useful？没。

I'll say like be does some kind of memory read than you like。Be like， oh， I'm just stalling on DNA。

Exactly， so so in those types of stalls are mismatched。😊。

Compute weights of one thread or a few threads doing some longrun computation with most stalls。

 this can be more powerful and help optimize that computation and cover that latency again GPU program is all about covering latency and this is another way you can do that。

So。嗯。ul have taught you about warp synchronity isn't completely valid after this it doesn't mean that you throw away those concepts those fundamental concepts remain but these are some new concepts you can also take on board if you want to synchronize your warp there's a new function called sync warp like sync threads you have sync warps and thatll synchronize the war so that it starts executing together once again。

All the whatt functions require that sync suffix now。

All of the wartport and war functions that I showed you have the sync suffix to tell you that they are going to be synchronous again you can do something like this when and try to do a shuffle operation when all the threads are executing different operations so that's why the sink operation the sync suffix indicates that all the threads will be synchronized and then this operation will execute。

You also get a new function to use， which is called active masks， so remember how I said。Baalot。

With ballot true you can get all the active threads well you no longer have to do that you can use active mask which essentially returns and uns signedigned in。

And tells you which bits are active， so instead of doing ball through。

 you're going to do active mask and it'll get you the same result。

Any questions on independent searchchedcheduling？来。なんです。Could also would。Right。Yeah。Yeah， definitely。

 the active mass code definitely sing。Any other questions？在这。All right， so the last topic。

Is cooperative groups。 and before I start this， I will tell you I don't。

I'm not anywhere close to an expert on this， this is probably one of the least explore topics of Kuda for me。

But it's apparently very， very powerful because I think a lot of the computations and modern on Ka being written does use cooperative groups。

嗯。So。There we've seen different typess of synchronization so far。

 the scuda device synchronized which synchronizes everything CPU and GPU。

There synchtreads which synchronizes across a block。And there sync warp， which， as we just saw。

 synchronizes within a warp。Right。But there's nothing in between。

 There's nothing that's flexible and。You can control how it works， right？

Thread group are kind of that flexible option that Kuda is giving us now。Basically。

 what it does is you can use a group of threads that you define。That can cooperate together。Okay。

You can within a group， you can get implicit groups， I blocks are an implicit thread group。

You can break them into subgroups， you can create。Memory operations between them even across blocks。

That's what I'm trying to emphasize here is is not limited to within a block across blocks you can start sharing memory and create subgroups and then you can synchronize across blocks and stuff as well。

 so it adds a lot of flexibility。Now to do this， you have to use these header files and also this cooperative groups namespace objects。

So there are few implicit groups built in。Which。this thread block gets you the implicit cooperative group of that block。

 similarly grid will get you the implicit cooperative group of that grid。

What you can do from there is break them apart。😮，In many different ways， so if we look at an example。

😊，What we're going to do is if we have some shared memory for this kernel。

We are going to use the thread block。Or this thread block to get the implicit subgroup there？

And within G， what we will do is well use this new function called thread rank， thread rank。

It's kind of like thread IDX， but within a thread group。

And that's because you don't have to have sequential threads be part of a thread group。

 you can customize it as you want。But you need some form of identifying what is the index of that thread within the group and thats what thread rank gets you。

This will all be linear， you don't have 1D 2 d， 3D concepts， you'll just do it in a 1D way。

 and then you also get the sync function on the thread group that you can call to synchronize。嗯。

So covered that。😔，Okay， any questions so far on thread groups？No。Okay。

So we look at implicit groups which are like thread blocks and grids they get you implicit groups now let's look at explicit groups where you are defining something custom for yourself。

So， to do that。You're going to start with this thread block， which gives you the current block。

Then you are going to do something like this where you do thread block tile of 32 where you're doing 32 threads and then you can do a tile partition of 32 values and give it the block。

 so you're creating partitions of 32 threads to create subgroups。Similarly。

 you can do something like this where you are doing four and thread block as two template parameters and then you can pass it to tile partition as well and what that does is it gives you four partitions of the block。

Finally， you also have this Coesce threads option。which allows you to only work on the active threads。

 it's basically the active mask version that you have in the warp。

 but in the thread block tile group is here。Any questions on explicit groups？

Where you're creating them yourself。嗯，O。So to break up any group。

 you can use these operations your sub tile partition。

 you'll get a 1D subgroup with row major and tiles。

 label partitions you can do coalesce threads and then binary partitions where you can do it using a predicate。

 again predicate being a condition right， so you can pass a condition to binary partition to partition it in different ways。

 basically a true group and a false group。So just visually you could do all of these with that kind of partition。

 so you start with the full grid。You do tile partition， you get two groups。

 you can do synchronize and then you can do more tile partition and then you can do syncs within them so you can partition in a nested way down。

嗯。Group collectors are basically how you control operations for groups you can do synchronized like barrier weight sync and barrier arrive to control you can do memory transfers between them using Me copypy async and these are all kernel level functions not host functions and then you can do data manipulation like run some operations and you can also do execution control like in work one and work one broadcast now some of these you can read the programming guide to understand more I won't go in full detail but basically there's some conditions on what functions can work on all on which group types so definitely worth checking out。

There's also warp level collectives that we kind of already saw。

 but we can now pass threat groups into those。So you're not limited to using those warp level functions on only on warps。

 you can use them on site groups as well， so this is kind of the example for that。Finally。

In conclusion so cooperative groups get you two things。

 they get you modularity because you can control how the threads write code and how you break them apart and then it also allows scalability because now with much larger hardware you can control the threads and blocks in many different ways and synchronize them in many different ways without being limited to the sync threads and Kuda device synchronized kind of concepts which either give you too little or too less or too little or too much synchronization based on what you're trying to do so you kind of get this multi GPU across the entire device kind of synchronization if you want to。

So that's the end of cooperative groups， I'm happy to take any questions here。No know。Okay，So。

 so these are all advanced ka topics you know。There'll be theory。

 but if you're doing coDa projects for final projects， you will likely use some of these to advance。

 Mike。I like any way like you say， I don't know。Maybe some worth。GPU farms or something。

 iss there any like somehow simulate that。Something like that。So the way NVdia wants。

Programs to view multi GPU clusters is as if they were one big GPU， that's why they have NV link。

 that's why they have those high bandwidth memories connecting GPUs。

 especially on those big AI machines， you know， where you have to use big giant chips operating on them。

And that's why concepts like these cooperative groups help with that now because they are trying to design everything from a developer perspective to appear as one GPU。

 those same concepts can be applied to a single GPU as well it really depends on the algorithm and you may question to be like hey on one GPU this will add overhead。

 yeah absolutely will but if you're thinking of testing on your own GPU and then deploying on a much bigger GPU。

 these concepts will help with that。Any other questions？All right， so we learned class here。😊，again。

 as a reminder on Wednesday we'll cover final projects。

 so please please do come to trust and then for those of you who are coming tomorrow to Caium for the demoine light。

 I'll be sure to see you there。All right， thanks everyone。



![](img/0a975b25d69dd197a357dfb7db2b40e1_31.png)

O。Okay。