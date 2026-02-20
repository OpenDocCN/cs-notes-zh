# CMU《计算机系统导论｜CMU 15-213，15-513，14-513 Introduction to Computer Systems 2017 p23 23 - Dynamic Memory Allocation_ Basic -BV17jcReyETC_p23-

![](img/c2e143fe7ae0362a28e73100943f2297_0.png)

Okay， why don't we going to get started？So since we' were having class at Halloween night。

Try to wear the orange shirt I could find。And we have a little bit of funra。In today's lecture。

I don't see how any costs to doing。Oh there we go， all right。这し？Okay。

 so today we're going to talk about dynamic memory allocation。

It's going to be the first of two lectures that I think you'll find very helpful when you start the MA La。

 which is the next lab coming out。So dynamic memory allocation is the way that from a program application level program。

 you acquire virtual memory at runtime。And this is typically done for data structures for which you don't know the size until one。

And the memory is where's getting this memory foam， it's getting this memory from the heat。

 So if you remember this picture。That we've shown many times in this class in various forms of it。

This is the entire virtual dress space， and we have the read only segments and the readr segments and so forth。

And here's the heap， right， it starts from here， it runs up。Okay。

 and it's eliminated by this pointer。System pointer with the RK pointer。

And just to keep things in perspective， right up here is the kernel memory okay that's outside of the purview of user code。

 and here's the stack you've had so much fun with。In this course and the S point。

 so the S is growing this direction， there's also space for memory map shared libraries that grow up。

 but here's the heap here。 and that's what we're talking about memory it gets allocated。

In the space right here。And of course these aren't drawn to scale。

 right I mean that typically know these read only and readwrite segments are tiny and the stack is generally not all that big and the heat can be huge depending on what you're doing in your program。

Okay， so inside this he， the dynamic memory allocator maintains a collection of blocks that can be a variable size。

And each of these blocks at any point in time are either allocated or free。

And so in this class since we're dealing with seeing， we're going to talk about explicit allocators。

 which means that under the user's program control。

 you both allocate memory and you free memory when you're done okay so for instance Maic and free and C。

But that can be contrasted with language such as Java， which the user doesn't do the delocation。

 so they do the allocation in the program by saying new， for instance。

 you know invoking a constructor but there's no freeing in such programs there's a garbage collector that runs behind the scenes and tries to coalesce the useful data and create。

Free data， unused memory that it can then free up for later use。

So it's all done before you in those cases。But in this class， we're going to end in your。

Maic assignment， we're going to focus on explicitquis accuracyculars。Okay。

 so probably most familiar with Malik comes to the standard library。

 it takes a size and returns a pointer。If all goes well。

 that's pointer to a memory block that's available to the program。

That's at least of the requested size。And by。There's certain alignment conventions on the X 8664。

 the blocks， the pointer points to something that's 16 by aligned。Okay。A special case。

 if you happen to put the size of zero， this is going to return null。

 it's perfectly okay in that case， but the other time it's going to return null is if there's some problem if it is's unable to allocate the requested block of memory。

So it's a good idea in your programs if you call MalC to see what the return is。

 and if it's null and you didn't set size equals zero， so it's kind of a surprise to you。

 then you're going to have to deal with that in your sort of air handling code of your program。

It also sets this air number to this special value by the UniX Convention。

But typically people don't pay attention to that and then the flip side is of course you have the free function you give it a pointer。

Notice you don't give it a size， right， you just give it a pointer。And it basically says。

 I'm done with that piece of memory。And for correctness。

 that point and better point to something that was either mall or reality。

And Riot is maybe something you haven't used very much， if at all。

 that's if you've maled the region and now you decide you want a larger region or maybe a smaller region and so you call relic with the same pointer as before。

One that you may be familiar with is Calic。Which is like Malick， except。Well。

One nice thing is that it initializes the allocated block cell zeros。

You have to the argument has to be expressed in sort of bites， you have to give it。

The product of the size of the thing and the number of things。

There's also this SPI function that moves that point I told you about the BK pointer。

 and it's used internally。Basically， the system try to will allocate you some amount of he space to start with。

 and then we'll try to keep all your allocations within that space and only if it's forced to will try to grow the he fruit。

Okay， using this comm。So that's usually invisible to you unless you especially decide to use it。

So here's a simple example， right we've malleted something here， right this particular size。

 and again we check for the null， if it's null， then we know we have this air okay and we're going to exit。

Otherwise， since we called mallict， it was initialized force and in this program not we didn't want them to be all zeros。

 so we initialized each P to I。Okay and so now our array P is all initialized and ready to go。Well。

 we free it， okay， so not clear why this program made any sense， but presumably in a normal program。

 you would actually do something with P before you decided to free it。Okay。

 so when we talk about dynamic memory allocations in this class。

 we're going to make the following assumptions， we're going to assume that memory is word addressed。

 so we're not going to worry about you know。😔，You knowfeing bites。

 just keep things simple that the words are integer size so if it's a。

Whatever the size the energy is， that's the word， so we're not going to pay too much attention to that。

 and the allocations are double word aligned as they would be in the X8664。

So we'll have pictures like this， we have a each of these little boxes is a word。

That's a words worth of thing so and we color code with green， the ones that are allocated。

 so this is and allocation of four words。And here's an allocation of two words and so forth。

 here's an allocation of six words。And the ones that aren't colored are still free。

 so we have a free block of two words。It's shown there。

And you can see that the allocations are all properly aligned， right， they have to be aligned thes。

Two by boundaries， sorry。スらつく。Okay。So let's continue with an example。

 so here we have it starts off all free and now we get this first call Malic for four times the size of it so just to keep the notation small。

 we're going to define this SIZ to be size of in。And so we see it just takes the first four。

And the next one just takes the next five。And so then the question is where does this next one start？

Do we just go ahead and take。Right these next six。I heard to know， why not？It's not properly aligned。

 right？So we have to go to the alignment boundary so it starts here。Okay。

 and we have a little bit of wasted space here。Okay， so now if we go to free P2。

 that means you want to free this that lavender。And so it looks like that。

And now if we do a malic of size two， then for instance， we can put it there。Okay。

But we had some choices， right， maybe we could have put it here， might have been a better fit。

But in this example， we put it here。any questions so far yes。We'll talk about that that's coming up。

 Yes， good question。Okay， so here are the， you know， if you're writing a dynamic memory allocator。

 as you may just happen to find yourself doing in a few days from now。

Here are the constraints you have to know about all right and also within real running systems that you have no control over the malls and freeze that your request that you receive as an allocateator。

 the program can do whatever it wants。Although if they give you try to freeze something that hasn't been malic。

 that's a， so you can assume that the freeze are two things that have been malked。呃。

So because you have no request no control of the sequence。

 you can't control the number of size of the allocated blocks。嗯。

The programmer doesn't want to be kept waiting for you to say， okay， here。

 can I have this block of memory and you say， can you wait a few minutes I want to see what other requests come in no you have to respond to them right away。

😔，Okay。So you can't reorder or buffer request， that's in contrast to other things in system。

 right I mean if you think about。あ。You know， say writing out to a disk。

Typically no one's waiting for you to write after that disk and so you can actually reorder requests if we talked about how the disc work and so if you're spinning past the place on the disc and it muzz well writing even if it's out of order。

这是。But here we don't have that luxury。嗯。Of course， we allocate only from free memory。

 we must have satisfy their library requirements。We can manipulate and modify only free memory。

And we can't move an allocated block once they're mounted。Okay， so why is that。

 why can't we remove an allocative block？Yes， it like。し秒。Exactly。Exactly。O。啊。

Poin in C you may have done all sorts of things about that now and the other thing is that the program has to be able to free this thing right and so it's got a pointer。

And it needs to be able to。To free it， and if you moved it， you。

 then it wouldn't know where to free it。Okay。对。Okay。

 so there a couple key performance goal of these systems is throughput。

 and that is that if you're given some sort of sequence，You know how fast can you plate them。

 number completed requests for unit time。Okay， and what， so for instance。

 if you had you're able to do 5，000 malic calls and 5000 free calls in 10 seconds。

 that's you know 10，000 operations and 10 seconds， so that's a throughput of 1000 operations per second。

All right。So because of this measure throughput， you want to have。

Routines inside your allocator that are fast， you don't want to be doing things that are very complicated and slow。

And the other goal is this peak memory utilization utilizationization。

And we'll get to that in a second here。嗯。I should kind of strike you as a weird goal。

P memory utilization， we don't use one。Reduce the amount of memory。It is like， oh。

 can we maximize that？It's sort of strange， but you'll see。Okay， basically。

 the trick is it's peak memory utilizations relative to where the break point currently is at。

So the way to calculate that is that if you think of every mallic。Of of。You know， of size P。

 we'll call that the payload， it has a payload of P bytes。All right。

And then at any point in time in the sequence of requests of Alex and freezeze。

 we can talk about the aggregate payload， which is just basically the sum of all the things that are still allocated。

Okay so I've had a series of requests， some thingss been freed， I don't count those。

 but the ones that are still allocated， I just sum up their payloads， okay。

 and that's going to be this and after K requests， I'm going to call that piece of K。

And then I also have this current heap size， and that's based on where this BK pointer currently sits。

Okay， and typically。In most systems that only increases。

 they tend to take away heat memory once they've given it to you。

 and so we could think about that as monotonically nondecreing。

 you're giving some amount of heat and it could stay in one place for a while and then it grows and stay in another place and so forth。

 but the sort of the maximum heat size。That you have seen thus far is the current heatap size， okay。

 another way of seeing it。So with that in mind， then we could talk about what we really mean by this peakat memory utilization。

 and that is if we look at the current amount of heat we have。

 which again we said is the maxim we've ever had since this sequence started。

And we compare that to this running aggregate payload。

 which can grow and shrink as things are allocated， ded， so we take the max。

That's why they hit peak memization， but take the max of all this PI and divide it by each of。Okay。

 and that's going to be your peak memorization after K plus one request。Okay。

And it's just capless one because we started at zero。Okay。

 so you can see why that's actually a good number to have high right you don't have you want to have make good use of the heat。

 the system wants to make good use of the heat that's been allocated for the process。不这你关清上来。Yes。我's。

Not。え中？So yeah， so what contributes to waste utilization， we'll talk about that a second。

 but it's mostly， yeah， it's mostly padding。It's the overhead for whatever data structures you're using。

As we'll see what happens is that we do the bookkeeping also on the heap itself。

That enables us to find things and so forth。And then。Just fragmentation。Okay。

 which we'll get to to second。Yes。P of I referred to。P话 cake is at the sum。

 so we've used K in two different ways here， so we think of those。I afraid to doing it。

So generically， this is B safe request RI。You have an aggregate payload PI。

 and then that's the PI here。Okay， so yeah， we should have used a different letter。We use camp there。

Good。Okay， support memory utilization is caused by two types of fragmentation， internal and external。

Okay， let's talk about internal first。All right， so you know， we've set aside this block。

For the user。And somewhere in that block is the payload。Which is the stuff you can actually use。

But as we'll see， there could be some wasted space before the block and we'll touch on that in a minute and wasted space after the block for things like gutpadding。

你可以。啊。But there's other things like was mentioned before about how much do we search for a really good fit for the block size requested。

If we don't search for very well and so we decide to， you know。

 we find like we' talking about something called first fit。

 which is you just march along and the first time you find available free space that's bigger than what you've requested so the thing fits。

 then you go ahead and satisfy it， you go ahead and use that space all right。

 but that could create you know a lot of sort of extra。Beyond just alignment value。Okay。

But the good news about trying to calculate how much internal fragmentation you have。

 it's just a it's it's a function of the request so far。 right You can， if you've run。

 if you've run up to a certain step， you can look and do that calculation。😊。

And figure out exactly how much internal fragmentation has shown so forth。All right。

 so let's talk about the other type of fragmentation， we should call external fragmentational。

And remember our example from before， you know， we've allocated this four， we' allocated this five。

 we allocated this six， it needed to be a line， we freed the two， okay。

 and so this is kind of the state of our memory。And now a Malik one in seven words comes along。可。

And so from an allocator's perspective， this is like a ynk smoke， right？That basically。Yeah。

 there really， there really is。啊。Right。As it says at the top there actually。

 there is enough aggregate memory right there's that six free things over there and the two there。

 So we had room for seven if we had made some different decisions before。Okay。

 but based on this is we made up till now and the fact we can't actually move the allocated stuff。

 you know， Kim。Ces or anything or kind of stuff。And the amount of external fragmentation you to end up with is a lot harder to figure out。

呃。You know because it's sort of predictive， we have to know what's coming right I mean。

 the reason this and this were external fragmentation after this first step only arose because you had something come in that didn't fit all right I mean if we had if the next request have been six and the next request of it two。

 thered been no external fragmentation and would would happen so it depends on what happens in the future。

はい。Any questions on that？Okay， so I've glossed over a bunch of issues that you have to deal with if you're going to write one of these things。

All right。You know， the free command， as I mentioned， just gives you a pointer， it doesn't say free。

 something that starts here and runs this law。Okay， so from your allocation perspective。

 all you're given is this pointer， is it' free， this amount is free what this pointed to。Well。

 in order to know the extent of which to free， right because maybe you have right。

 so I give you if I say free this guy here。All right， well。

 I've got allocated stuff all the way to here。But I need to know as an allocator that， oh。

 I just mean to free up to here， this stuff still stays。Okay。So we have to talk about that。

How do I keep track of his three blockss？They're scattered as we've seen throughout our heap。

 and I want to be able to find them the clean and so forth。嗯。

There's this issue if I happen to choose a smaller block。If I choose a bigger block than what I need。

 how do I handle this extra space because it's still space， so maybe I can use it later， right？😔。

Then the earlier question， how do I pick which to use？There's multiple choices。And。

Yeah how do we reinsert free blocks， so if we freeze something。

 can we coalesce it with other things that are nearby that also be free？Okay。

 so we're going to deal with those one at a time。So the first question is knowing how much to freedom。

 I'm just given this pointer。How much do I free？All right， and the trick here， as is shown here。

 is that we're going to。So， so this is。This is the payload， the block that I've given the programmer。

 and here's the point I return。Okay， so from the program's perspective， nothing's changed。

From my allocator's perspective， I've stolen this block right here。This board right here。

From the previous sort of this free stuff， so in this case， the dark is the gray is the free。Com。

Sorry， sorry， I've stolen this guy here。The greatest still the elegant I saw in this guy here。

 which wasn't being used。To put in length field， okay and so what this is saying is that this block size is my payload plus the space for this guy。

 which is five。哎。And then if I later to free that， then both this length field and this allocated thing are now available again all right so you can see that I'm back to this exact same stage as before。

诶。Okay， so。Any question算的。Okay good， so that tells me exactly how much to free when I get this money' these points。

Okay， so now about the question of keeping track of these free blocks。All right。

 there's a number of different methods in this class。

 we're going to focus on what's called the implicit list method。And basically， what that is is that。

Now that I have these lengths。Associated with each allocated block and I could do lengths associated with each unallocated block。

 analated segment of memory， and then you know I could just follow them so I start here。

And it says four， so I jumped to here， I know that's the start of the next thing， it says six。

 search from 1 two，3， four，56 to here， and so forth。Okay。

So now I'm able to get to the start or in particular the length field of all the blocks。

 whether allocated or free。Okay。啊。So the only twist that I need now from what I talked about before once I've added these length fields as I talked about before。

I that when I get to one of these length fields， I need to know whether I'm dealing with a region that's allocated or not。

 okay I need to know the difference between this guy who's allocated and this guy who's not。Okay。

 so we'll talk about that。In the rest of the lecture。

 but before we do I want to mention give you the big picture。

 which is that there are other ways of doing free list besides implicit free list。And in fact。

 in the first part of your MAcl， you're going to start off by doing an explicit list。

 so explicit list avoids a lot of the complications by just actually having a pointer okay。

 so if I have a free。AB here。All right， it has a length field as I mentioned。

 and then it also has right here， a pointer that skips over。

All the allocated ones and gets you directly to the next free one right here。Okay。

So that's nice because you don't spend a lot of time sort of bouncing through。

You know the ones that are already allocated right you can imagine as this space gets more and will through it up。

 you might spend a lot of time in this top method hopping through ones that you've already allocated where this one jumps immediately the next free thing and the only issue is is it big enough or not for what you're trying to allocate。

Okay， but what's the drawback of this comparative look？Greatrick yeah if you allocate。

A piece of memory that's free。 then you have to go to the previous。Free memory。Yeah down。

Adjust the point there to be the next free piece of memory right Yeah yeah so so you know that's that's。

RightSo for instance， you allocate this piece here， then you need this pointer。The point here， right？

Okay， and you notice in this structure， I didn't give you any back corner。Okay。

 to go backwards so so basically that means as you're marching along。

 you're going to have to keep track of not just where you are。

 but the one before so that you can do the you have this。This pointer available。To change okay。

 and the other thing is that you just need you need space with these pointers。And。Space。

 right and these。Yeah。that could be like 64 bits。Another method that you we'll cover in the next lecture as well that you're going to want to consider as well for your MAL is having different classes。

Of freeance based on songs。Okay， so maybe you have like a free list for all the blocks that are。

 you know， a size for。the available space is size four and maybe you have ones of all the ones that are size 8 or 16 or whatever。

 so some different combinations and you have separate freeless so therefore you don't waste your time hopping through ones that clearly aren't going you the right size。

The extremists would be if you had sort of you know。

You kept all the availableil of blocks sorted by size。

say in a balanced tree that allowed you to search so you'd come in with your key would be the size you're interested in and you'd search through this balanced tree using that length as a key and then you'd find one that was the tighttest fit。

 for instance， to what you're doing so that would get you without the。

Say overheads of segregated freeless that would get you the sort of the tightest fit。

To what you were looking for， but then there's all the overheads here。Search trees and so forth。Okay。

 but today again， we're just focused on nothing。Good。So I mentioned that in addition to size。

 the thing about the implicit free list。Is that and let me just remind you again， right。

 So we've got implicit free list。 we've got these these length fields that we use implicitly。

 and we said we need to tag as either allocated or free。So what we're into。

Po this tag of allocated or free。We don't want to have to store this information in its own word。Any。

Cubricks， yes。呃，这这挖。The lengths of these things are all unsigned。

 they're already using that bit potentially for。But drawing， the right track is go into the。

然后那是 bit惨的。So what's at the other end of the big time？Yeah， the least snipping be。

 and so why is that available because of alignment right， so basically the。

When the blocks are aligned， then some order address bits are always zero。

And so you treat them as being zero and you use the fact that they're zero to squirre away a bit。

 say， zero for free and one for allocated in that space okay。All right， so what that means is that。

You don't， you know this this。This word that used for the size is good enough because you just used this last bit。

嗯。But when you read the size inside your allocator， you want to mask out this bit。

 you want to basically view it as always set to zero， and if you're interested in what the bit is。

 then you want to sort of mask only this bit， but you want to just retrieve that bit。Okay。

 and we'll see examples of that in a second。你 question始来。Because things are aligned， right？这三没给。

The okay， so this。嗯。Yeah， size so for instance， the size is is。Yeah， I say the confusion， okay。

 so in this lecture， you know we've sort of set everything in the word sizes and all the linkss are in word sizes and things like that。

 right？But。I， it's two more。Yeah， the the the。Yeah， that that okay， that's that's yeah。

 answer your own question。 So so basically what happens here is that even if you wanted a。嗯。哎，对。

All these all these length。All these size fields， sorry。Our。You know， there the。

They're one less than the alignment boundary， right so alignment boundaries here， here and here。O。So。

 the。So you know that and these sizes include the pattern where they jump you to the next length here。

😔，So you know that these things are always。You know， as you said， a multiple of two。Okay。

 so that last bit will be zero， good。てうかはい。Okay， so in this diagram。

 what we've done here is we've labeled them as sizeizing words and allocated。

So this is two words and unallocated four words and allocated and so forth。Okay。

And we're showing the double word aligned boundaries。嗯。And then as a result of that。

 there's always because we have to have room for the header for the first guy。

There's always going to be this first unused word， that's all right。

And they also have this notion of what's called an end block， which is at the end of this list。

And it turns out that the most convenient convention for that block is to say it's a size zero and its' all。

Okay。And it's kind of arbitrary to call that thing all because it's not really allocated。

 but it turns out that when we look at coalescing later， you don't want to coalesce past this thing。

By assuming by setting this to one。Things are you won't try to coalesce with it， right。

 you'll stop and that's good because you don't want it。know。

 coalesce is something that's really not there and it's off the end。All right。

 so that oughtll become clear later when we talk about coalescing。

 but I just wanted to highlight that because it looks a little strange on the slide to call that thing allocate。

嗯。Okay， what about the question of finding a free block？は。

So first fit says you search from the beginning and you choose the first one that fits okay and so here's the simple little code for that right so you you you do from the start。

嗯。Right，Youre right here。Start。嗯。And while it's not past the end。Okay， again。

 the N would be delimd by the end block。But in your code。

 you probably have these as some absolute starting in any addresses。Okay。

 what am I going to do if I'm not past the end， then。What I want to do。

I take what that pointer points to。And I end with one。What does that do？Yep。

 just extracts that bit okay， so if that bit is one。This is no good event， okay？But if it been zero。

 that's free， all right， so then I go to check to see if it fits， right？And so。If， if the the length。

Field is if it's less than equal to。呃。To the length I'm searching for， then it's too small。

 and so I continue this well， okay？ByGo to the next block。So notice I have to do。

 in order to jump to the next one， I have to take that size field。And I have to end it with minus2。

To get rid of that， the zero out， the allocated bit。so that gets you the real size。And then add that。

你清理。Okay。2。全一款是什的。So the only thing that certain little subtle is why this is less than or equal to。

Because you think if it's equal， that means there's enough room， but the length field， if you call。

like this is a length field of four and it includess the length for this guy here right because he says hop 4。

1，234。So there's really， if the length field is four sorry， the size field is four here。

 there's only space for three。Okay， so that's the only reason that code says less than equal to as opposed to maybe more intuitive lesson than。

Okay， so the good news is that we first fit。It's you know you're done as soon as you find something that fits。

But the bad news is that you know sort of。It may not be a very good fit。

 and things tend to splinter at the beginning of the list because the little things sort of clogged things up。

So in order to get around this fact that all that sort of。

Cluutter is occurring at the beginning of the list， there's this thing called next fit。

 which is the same as first fit， but instead of always resetting when you want to find a place or something at the beginning。

 it just continues where you last left off。😔，Okay。And this is really good， for instance。

 if the thing that you want to。Findine is at least as large or equally as large as the thing you just look for right because you know。

 if you just search search search search search search search search search and you weren't able to find and this was the first place you could find a space that was big enough。

 then there's no reason to go search search search or search or search or search again。

 if there hasn't many feess in meantime because you're going to fail if that new thing you want is the same size or larger。

So the next bit says， oh， we'll start here。And look forward because I know everything behind this place。

Spot didn't work out。嗯。Yeah， so often faster because it avoids reskinning unhehelpful blocks。

But some research suggest that fragmentation is actually worse。All right。

So the other extreme is best fit where you， in some sense。

 go through all the possible choices and find the one that has the fewest fights left over。

Fits with the fierce spice leftover。All right， so this has the advantage that you're actively working to avoid fragmentation。

And so it usually improves memory utilization。But it's typically slower because you're not just stopping the first time you find something that works。

 You're like search search search search search you can you find something that。

You know that's the best you can hope for。And maybe， for instance。

 at the best you could hope for it doesn't exist。If everything is bigger than what you want。

 by too much， you have to go all over the end before you discover that and say， oh okay。

 I guess there really was nothing that was the exact size of one or the exact size plus one。

 so now I' just wasted my time running into the whole thing。All right， yes。

 so whenever you mallet a type like an int， you also have to mall an extra word that keeps track of the size of the。

这才。So yeah， behind the scenes， unknowns to the programmer， you're also counting for that length feel。

 but that extra feel doesn't affect the ca rate because like in the catting questions。

 we didn't have to know about that extra word。Actually being there。嗯。

Because like if your end is like four。For were。And then like you have an extra word。

 so it's actually secretly five words。That doesn't like the it happen。Okay겠。So， yeah。

 so so you need this to be。Like for instance， you needed this to be， is these good questions？

You need this to be double word aligned， right， okay？So。

So this allocation here was actually an allocation for。2。Okay。

 the thing that was requested was size two。All right， so in that case， we did pad by one。Okay。

 but notice size and size three would have worked。We wouldn't have to do。I mean。

 the quote unquote padding would have been this guy here。Right。

But notice that a size four doesn't fit。If I did a sum allocation。Okay。So。So yeah。

 so I guess you're pointing out that technically when we ask these padding questions and exams and the padding question we had earlier。

 we're making some assumption that we're not losing。Any space。On the heat for these kinds of。

size fields and stuff like that， just because we hadn't covered that topic yet， you， but yeah。

 that's a really good question okay。嗯。Okay， so this no is splitting。All right。

 so I's suppose we're coming along， we're trying to find something to size four and remember that four actually only fits three。

 so this isn't big enough。Sorry， this isn't big enough， but we come here and we see a six and we say。

 okay I can hold up to things of size five， so certainly can hold this four。嗯。So。Yeah。

 that's a little confusing actually， so basically this can hold。嗯。We're recording here is these。是不一。

Okay。And then we're going to。Have this leftover space， right？In this leftover space。

 was we had six here before， and now we're allocating something of size either two plus padding or three。

 and we have this length the size field as well。And so we basically use up four out of the six。Okay。

 and so now what we do is we just figure out what the remaining part is and we subtract basically six minus4 and we get to。

And so that's what this code is doing。All right。This is going through。

 this is a routine within your allocator right that says I'm unalocating something that needs of length four。

 including the size field。And so you say， well， the new size is the。You know。

 it needs to be rounded up to even， so your is a way of rounding up to even if you remember your bit tricks from the。

From lab one， you're going to right shift in the left shift。

 that's a way of zeroing out the last bit。嗯。Then you're going to mask out the lower a bit。Okay。

 on the old size。Right， because。it could be a zero one there。And then we want to set the new length。

Which is we want to indicate this is now allocated so we put the or that new size with the one。Okay。

And then if new size was less than old size。Okay as opposed to equal to old size。

 then we know we have something left over all right and we just figure out what how much that is so we take the old size if there' six when it's the new size which was four and and we just have a fair to store that okay and we're going to store that well this is the P again this is not the P that we return to the user。

 this is the P and our sort of walking through the free list P this internally our allocateator。

And we say， well。The new P is going to be p plus the new size。Okay。So that'll be placed here。Okay。

 so whatever the P was， plus whatever the new size took up， places two。

 so we placed a two in that position here。关系上的。Okay。What about the opposite freedom block？Okay。

So one approach is that the only thing you do is you just clear that allocated bit， right？So if you。

Take the thing that's stored。呃。Sorry， you take the thing that's stored here。

This is really four slash one because it's allocated。

And you just want to convert that to four that0 and you do that through this manipulation that just zeros out the last bit。

Okay。So that's fine and good， that would be enough， but then what if you get now a malica size5？

Okay and the way you've set this up is you only see you know four。

 four and two and so forth right so this is again another one of our yanks moments。喂。And。You know。

 the allecator doesn't find it necessarily， right？So that's why we want to do something。

So we have a couple of choices， one is as we're marching along。We can。

 as we've created this free this space， instead of just sitting this bite。

 we can actually march along and look at this pointer。And say， oh， does this also have a zero？

This also has a zero in the allocated bit， then it's also not allocated so I can go ahead and。

And collapse this and return this to a six。Okay。And that's what this is showing here。

 that basically this is logically gone by just once you've done this zeroering out of the a a bit here。

 you find where it pointed to， which is here。And you say， well。

 if I just yank out the allocated bit and zero， which be unallocated。

Then I'm going to actually just jump over。谢 here。By 6，4 plus2， whatever's there。

and now that's largely gone and you're back to where you were before。All right， does that make sense？

Okay， and we see a problem with this。Yes。I think for the previous walk is going to be huge reverse。

Again。Exactly， exactly， so this was the case where the thing you were trying to coalesce with。

Was it hadn you， but suppose we had a reverse situation where two one this was the one that was allocated and this one was not。

And now my forward partnerer doesn't help me at all， I want to coalesce factors。Okay。Good。All right。

 so fortunate there's a solution for that， a number of solutions。

 the first one proposed by Donna Kth it's called Boundary tag。

And that is simply that in addition to storing the length。At the beginning。

 so it allows you to jump forward， you also store the length at the end and that allows you to jump back。

Okay。嗯。But of course the problem is that now you're storing the size in two different places， right。

 so that's wasting space。Okay， so it looks like this same thing we've got the size and the allocated bit here and the size and the allocated bit here。

All right， and that allows us to go backwards forwards and coalesce backwardss。Okay。

 so if we consider each of the four cases， we're trying to free this block here。

And the four cases are is surrounded by allocated stuff， the thing before it's allocated。

 but not the thing after it， the converse， the thing before it is free， but not the thing after it。

 and they're both free。Okay， so how would we handle all these cases， the first case？Its simple。

We first free this by setting these bits to zero。And then we look before and we see， oh。

 that's allocated， we look after we see that's allocated and we're done。Okay。

 that's the easiest case。The second case。嗯。We're trying to free this and the one after it is unallocated。

Okay， and has some size M2。Then what are we going to do。

 we free this by saying this is zero and this is zero， and then we look at this guy。

And we see it's also zero， so we jump by M2 to get to the well M2 minus1。

 I guess to get to the end of this。And then we see what the end is， and we can write the new sides。

 which is the sum of these n in M2。And M2 and then。Keep that at zero。Okay。

 any questions on that case？All right and okay so now this case is the case where we had to you know we had to come with Bo Texas off so this is the first interesting case。

 but it's pretty simple right so basically we check here we see it's allocated so there's no reason to coes that way we check back here。

 we see it's unallocated we use this。Boundary attack。To jump in one。

And get here and that enables us to set。updatedate this to be the sum of those two sizes and of course it's unoped。

And finally， this case where neither of them are allocated。

 we just do both directions and we end up getting nN plus M1 plus M2 and unallocate。Okay可し上的。Yes。

So that's an option， right。嗯。You can can defer coalescing until later if you want。

 this has the advantage of。I mean， in some sense， when someone's gone to free something。

You've got potentially some time there。It's not on in the critical path， typically for anything。

And so it's good to do some work ahead of time， if you do it immediately then' you're not coalescing on the like if you didn't do this immediately。

 then the next time through you you'd be hopping like this and so you'd be doing these hops and that would slow up the actual allocation。

Okay。And。And then you have to it'd be more complicated you have to do this keep track as you're going and you're right。

 but after having march through this， you could then create it to make it look like this。

 but that's just delaying the allocation which is typically when there is something waiting the program is weighting so the more you can push。

Computation time to the free and less to the actual time allocation， the better。

 but fundamentally there's nothing wrong with deferring。Coal。All right， with that。No，没 start。Yes。

All right， of， do you want to use your reach a memory to store different types？

You should use a union。 This is a。Reminder that it will come in very useful in Maliclo。Okay。

 which is why we put question put this question here。嗯。Just to see how you're coming with。Sheah。

 well， I mean not' so good， all right。Yeah。Well， nice even distribution okay。嗯。

So who can tell me why this is an error in the first place？来兄点。Somebody doesn't use the answer。

How the red。That's right。Okay。So you cannot set the handler for sick kill to be ignored。Okay。

Now maybe a little more subtle of whether the compiler catches out， the runtime catches it。

 but it turns out that the compiler doesn't really have enough information to figure that out。

 and so this will get captured at runpi。So user code you can't block sick kill， you can't ignore it。

 you can't do anything with that Ch code template。呃哪里去看。All right。

 and the one thing whichs related to today's lecture。Good， did pretty well in that。Now。

 the answer is not showing up on here。嗯。I don't remember what it says， what was out anyway。

 once you got it right whatever it said。是这样的。Yeah， and so the boundary tags are neighboring you to go backwards and forward。

嗯。Minimize the internal fragmentation， it turns out that if you call internal fragmentation is sort of。

How much a big part of that is how much of your own data structures contribute to loss of available memory。

And because you have these tags on both the front and the end， it's actually not very good。

For in terms of internal fragmentation。So we can argue semantics over what it means to minimize。

 but it's not one of the better solutions for。There are internal fragmentation。



![](img/c2e143fe7ae0362a28e73100943f2297_2.png)

All right， and that's kind of。

![](img/c2e143fe7ae0362a28e73100943f2297_4.png)

All right， and so the first clue is sew on the slide here which。

Which blocks- so we have this both this header and footer sizes。But which blocks do we actually need。

 do we actually care about？Allocated ones are unallocable ones。

So it turns out that it only comes up when you do coalescent。All right， so we'll show you trick here。

All right， so。Okay， so boundary tag are needed only for the free blocks。

 okay because they're used basically to allow you to do coalescent you free something when you're free consecutive things。

系。So we mentioned that if sizes are even bound multiples of two， then we had one square bit。

When sizes are multiples of four or more， we have two sps。Okay。嗯。So let's assume that。And again。

 this would come back to the case of if size is actually accounted for in bytes。

 as opposed to in words as is in this lecture， then you would have。

Multipableles of four bytes clearly。For sizes once you didn't count for padding。

So we're going to use that extra bit。In kind of an interesting way。

 we're going to set to one if the previous bid is allocated and is zero for previous bid bid is free。

Okay， so we're going to get rid of this all together。

 and instead we're going to do some extra encoding in the head。Let's see how that works。O。

So we have those four cases， remember， the first case is that we're trying to free something where the thing before and the thing after are both allocated。

All right， so initially before we do any frame we see allocated。Alloc， allocateocd。Okay。

 this is our our teaching sheet， right， the current block all is the last bit。

The previous spec allocated is the bit before that。

And we use those two bits because the address bits are always zero due to alignment issues okay。

 so if we want the actual addresses and sizes and things， then we just zero those up。Okay。

So what do we see here， so we free this。Okay， so this is now unallocated。

And now we look at this bit here and this bit here was a one。

 so that means that the previous block was allocate， okay。

 and that's indeed what we show here because it's in green。😔。

And so we know we don't have to do any coescing backwards。All right， and so we leave that in one。

And then because of this n， we can jump to here。All right。

 and then we can look as before as to whether this is allocated or not， it turns out it is allocated。

And so we don't have to do any closing there， so this remains a one。

And the only thing we have to change in this guy's header。Is the fact that now。

 from this perspective， its previous block is now uneleocate。

So it's gone from a one here and you still see that under Al myA。Chilty scratch。

It's gone from a one here to a zero because now a free distance is un allocateated。Okay。

So with just the。Actually， this shouldn't be here。也行。Just mistake on the slide， all right。

 good so from just the information of this extra bit。

 we knew there was we were able to handle this case and set this bit to maintain in view。All right。

 so what about our case two， wheres the one after the that's about unated？Okay。好还是 no问题。そrry。

I seeSo for the I'm getting myself confused use here， so for the ones that are free。

We are going to go ahead and maintain both the header and footer。Okay。

 it's just there ones that are allocated， we don't want to waste space in the available allocated stuff for the。

Okay。So this is the steady state that basically for something that's unallocated。

 you've got both a header and a footer。And in this case， the previous block。Is allocated。

 that's why it's a one and it's a one there。Now after we free this， what's going to happen？

So we'll use this n。To have to hear。Okay， and we'll see it's unallocated。All right。

 so that allows us to coalesce。With this bio is N plus2， and so it ends up looking like this。Okay。

And from the perspective this bigger block， its previous guy is allocate， okay。

 so that's why that red fit stays one。All right， so what about this case？

So the question mark here means we don't really care whether it' zero1 is not going to influence what's going to happen here。

So what's going to happen here is that you're going to free this。Okay。

 so that's going to set this one to a zero。And now you know it doesn't matter when you do the previous or the next first。

 but let's say we do the previous first， so we see this zero and we say oh。

 this is unallocated stuff， so what that means is that the footer is actually contains a length field so I can just hop just this one back here retrieve this M1。

And then I know that I can add n plus M1 to sort of the intermediate step。😔，This is gonna。

The intermediate step。Enandds up looking like the n plus M1。And the zero。And n plus M1 here。0。

And this one we haven't touched yet， and so from that step then。we have this end。

I guess I had to remember the end， so you have this n and we go here and now we see that this is allocated and so we're done。

😔，Okay。So it answer word like that。Okay， and the only thing I forgot to mention this thing we have to do is to make sure as we set that this。

Goes from one previous block allocate to a zero。And otherwise， it's because want yes。Here widely we。

Why do we have the question mark？一つの一。The block tied to it was free when we've already come ask them block。

That's true。That's true， good point。Okay， so in the final cases where they're both。嗯。Free。😊。

And so the hand picture looks like this， and basically we do。Kind of what we did before。

 let's say we so we first set we first go and ahead， we'll get to this guy， he says M2。

 so now we can go。To n plus M2， should we get to this guy。And。

And we see that the previous is unallocated。So we go back。So when we went forward。

 we looked at this bit， and we go back， we look at this bit， we see it's unallocated so we go here。

 we know that this。Is actually a。Go footer， and so now we can add M1。 and so the end result is。

Is this in this？Okay in the sun。Questions on any of those four cases。可以。Okay。

 so we've talked about that there's a number of decisions to make an allocator。

 one is the placement of policy， do you go for the first one that fits， the next fit。

 the best fit and so forth。Each of these policies has a trade off between lower throughput。Mean。

 it takes you longer to find what you want to hand over to the user。

 but possibly saves you on fragmentation。Which is a good thing。嗯。Interesting observation。

 one of the reasons that segregated freeless， remember。

 these are the ones we have different allocation classes for different sizes。

I is a somewhat popular thing to do is because it actually can approximate a bit。

Best fit placement policy without having to sort of do this what might be search。Okay， and again。

 in your Maic lab， particularly the second part of it。

 you're going to play around with a lot of different combinations of these things to try to optimize。

It won't just be one or the other， be this mix of different policies。

 so you're can to be able to think long and hard about what works。

We talked about splitting policies whenever we go ahead and decide to split a free block。

 how much internal fragmentation we willing tolerate when we do that。

And then we talked about coalescing policy， immediate coalescing。

 which was the what I was presenting， which is coalesce time a freeze call， as was in the question。

 you could also defer coalescing。to try to prove the performance of free。For instance。

 you can coesce as you scan the free list for Malec， so as you're going forward。

 you can do the coesing。Or you can class the amount of external fragmentation which is some threshold。

So there's different options there， but again， generally。

 I think Malck is more on the critical path than free。So you tend to want to do。All right。

 so to summarize this lecture， we talked about implicit list， implicit free list。

 the advantages that， believe it or not， I know it may have sounded complicated in the lecture。

 but conceptually， it's actually very simple。To do these implicit lists。

Joawback is that the allocation costs are linear time in the worst case because you're marching through this linear list。

The good news is that you're free and constant time， even with a coalescing。

Member usage depends on which placement of policy you decide to use。嗯。

Well they're not used in practice because of this first problem。

The reason we've spent a whole extra on them is because it're a good way to introduce the concepts of splitting and boundary tech coalescing and so forth that you actually end up using in all the different kinds of allators and you will need to understand for your amount。

Okay， happy Halloween。

![](img/c2e143fe7ae0362a28e73100943f2297_6.png)