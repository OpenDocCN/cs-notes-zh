# CMU《计算机系统导论｜CMU 15-213，15-513，14-513 Introduction to Computer Systems 2017 p31 31 - Thread-Level Parallelism -BV17jcReyETC_p31-

Yeah、ま。We'll have a。Nice Thanksgiving。How many people ate a lot of food。商品。Everybody are。

How many people have worked the entire weekend？Yeah。

 that's the problem of having a holiday in middle semester。All right。

 hopefully at least's got one day breather before us。Focus right back in on it。

Today we're going to talk about thread level apparels。In particular， we're going to remind you。

About perilous Union Harbor， very briefly。And then we're going to talk about consistency models for。

The memory systems， or there are multiple threads。And finally。

 we're going to talk about programming using multiple threads on a single application to try to get performance improvements。

And we'll use some very simple examples to show you some of the issues。Okay。

 so here's a picture of so there's a， highlighted dye。Here。

 the cartoon of that looks like this on the left， every core has its own set of registers。Yeah。啊。です。

the same。I can voice again，all right。This wasn't a 25 minute Windows update。All right。

 so each core has its own L1 data cache， L1 instruction cache， cash for instructions， and L2。

 and so forth， and they all share a last level cash。嗯呃7。And then there's main memory as well。可以。

We've also talked a little bit about what the out of or order processor structure looks like。

So here the notion is instead of executing the instructions one at a time。

 which would completely serialize things and you completely observe all the delays in certain instructions if you had slower instructions for special ones。

Instead， you have a instruction cash。That those instructions get decoded and then they get put in an operations queue。

Okay。And this Q is fed into these function units as they become available。

 so in this particular case we have two energyger units， a floating point and a load storage unit。

The load store unit has access to the data cache。Okay。

And so the overall performance is approved because potentially you can get all these function units operating in parallel。

 so maybe get a factor four there。But also just the fact that if one thing is stalled。

 like suppose this you're installeded on a cash M。You can be doing work。嗯。

On instructions that you normally think of as happening after the cashmis。and of course。

 that only is possible because the hardware has to track all these dependencies。

And decide when two instructions in your serial sequence of code can indeed be take effect out of order and when they can okay。

So hyper threading is a particular form of。Of parallelism。Typically， on say， an Intel processor。

 you have just two way hyper3i， which is what's shown here。And here what you have is basically two。

Copies of this instruction control mechanism。So for A， you have its PC program counter。

 you have its Operation queue and its register。Okay， and similarly for B。So。You know。

Given what I said before about， you know， you've got all these functional units that you could keep busy and so forth。

 why add the complication of。Hyperthreading on top of that。

Why do we have hyperthetic processes at all， anybody know？

It's like an example of when you might benefit from a hypothe cost。呃，我。

You get to use the L1 and the L2。Two course。No， they actually share the L1 and L2。Yes。

This is one of the processes。said it can't be affecting。Exactly exactlyly， so suppose for instance。

 this guy is waiting on IO or you know takes a page fault。

 some operation that's going to take a very long time。

 there's just not enough things that in that one instruction stream that can be sort of pushed ahead and kept keeping things busy while you're waiting for that and so you swap in a second。

Okay以。And the hardware designers have discovered that at least for most workloads。

That there's diminishing returns， so basically two is a good amount， three is not that helpful for。

 it's not that helpful and so forth， because you have to call you have to duplicate all the state。

And so two is kind of the sweet spot for the last 15 years or so。喂。Good。你かし证了。Okay。

 so our shark machines are hyper threaded， they have two way hyper threading。Okay。

 they have eight cores each。They're fairly old machines at this point you can get。

Machines with many more cores in that， you can get machines with。You know， 72 cores， for instance。

 those tend to be more for servers than for uses clients， find devices。嗯。So as mentioned。

 what we're to talk about today is in the context of a single program trying to get improved speed up by using multiple cores。

 so it's sort of truly parallel processing within a single program。Okay， and。

What we're going to talk about today is that there are things you can do when you write your program to make this work better to actually achieve some of the possible speed ups you might be able to get。

 I mean， ideally， for instance， on your shark machines because you have eight cores and each have two way hyperthing。

Theoretically， at least you might be able to get a speed up of 16x over a single threat execution。

by executing 16 threads at once， and if they're all able to keep busy， that's theoretically possible。

 although because of various overheads， you never exactly achieve that benefit。Okay。

 but you can get close with things that are。What's called highly parallel。

 not a lot of coordination between the task。Okay， so given that we have these different threads and they're all accessing the same main memory at the same。

 they're all within the same address space。There's a notion of memory consistency。

So if I have multiple threads in the reach updating memory。Okay， and they're each reading memory。

Then you know if there was no coordination going on， there would be a jumble mess。

 right you wouldn't know what to expect when you read something that someone else。

You read something someone else has written and so forth。

And so to create some structure over this mess that people can reason about when they write programs。

 there's notions of memory consistency levels。It's sort of abstract model of how the hardware handle cancurrent access。

It's sort of you can think of it as the contract， the API。

 the contract between software and hardware。If the software writes assuming that this is the memory consistency model。

 the hardware is guaranteed to support that。Okay， so what are some of the things that could go wrong。

 Supp that we had not。Cashs that weren't kept at all， what's called coherent。

 whether it's of kept in sync okay this may happen for instance。

 if these are not like a cache on one of the shark machines， but maybe scratch memory on a GPU。Okay。

 where there's no coherence， so what can happen there is that if main memory starts off with a equals 1 and B equals 100。

 and then thread one has these instructions to execute and thread two has these instructions to execute。

Then one possible thing that could happen is that this instruction happen first。

 and so this thread pulls into his cache， the cache line that contains the value A。

And updates the value of a to 2。so from this perspective， this cash a is still two。I's not two。

And then B can come along and do the same thing for B instead of 200。Now。Over here。

Thread two now wants to print a。Okay， well， it doesn't， if these aren't kept。

 if there's no coordination between caches， it has no idea。That a has been updated over here。

So it just goes and readily grabs what's really a scalele value， an old value。

From main memory and brings that into his cache， and so when it goes to print A， it will print one。

And likewise， thread one can do the same thing， it doesn't know anything about if there's no coordination between these caches。

 it doesn't know anything about the fact that B has been updated that this value is stale。

 and so it reads in the old value and prints that out。Okay。Any questions on that， yes？Using the read。

If you。呃。Well， notice that these are two different。

So you have the separate thing going on on A and B， so if you had A and you。

Grab if this thread grabbed a lock before it updated it。Then yes。

 this thread would actually not be able to pull this into cache because it would be locked out until this thread was done okay now the trick though。

 is that when this thread unlocked it， it's going to have to before it does that make sure it gets pushed back out to memory。

So that when this guy is able to get the lock， it actually gets the fresh guy not the still guy。对。

Okay and at some later point in the scenario we've been going through here。

 it's true that these are right back Ca， so at some later point this A2 will get pushed out to memory and this B20 will get pushed out to memory。

 but there was nothing that made it pushed out in time to make these print statements make sense。

Okay， so。So one of the first things that you might want out of a memory consistent model is that from the standpoint of a thread。

 its operations appear to happen in order。Okay， so that's whats mean these thread consistent constraints that the right of A should somehow take effect before the read of B。

 and similarly here the right of B should take effect before the read of A。Okay。嗯。

So sequential consistency is the most。嗯。Popular。Convenient model for memory consistency because it has a very simple way of reason about as a programmer。

The way reason about it is that memory behaves as if only one operation occurred at a time。

Even though there's a lot of parallelism for correctness， only one operation period of time。

 and that has to be an order that's consistent with the order of operations of each threat， right。

 consistent with these things here。Okay。But otherwise。

 given that thread ones have to be in order and thread twos have to be in order。

 the shuffling of the deck can be any which way。There's no restrictions on how this can be shuffled。

So what this shows here for this exact same program is all the possible combinations of things that can happen。

 right？So， because of the。So have these four。Operations。Because of the thread consistency ordering。

The ones that have to take effect first is the first ones that each threatened。Okay。

 one of the other， one of those， so we have those two cases there。

 let's suppose that the right of A was the first one to take effect。that means that next。

 still the right of B can go。And the read of B can go， but still not the read of A。

 because it's blocked by the right of B。 Okay， in this memory consistent model。

 not in the real hardware， but in the memory consistent model。

So that means though there's only two choices， the next thing can happen is either it's read to B or the right of B。

So if it's the read to B， well， then you're basically done because thread ones done is two operations。

 the only thing that can happen the rest of the way is thread two gets his two operations done。Okay。

So if that's what happens， if this is the order。In which conceptually things happen。

 what gets printed？你接写分之就。行。Okay， do you see why。Because when this guy did the read a beat。

It was read this by here。The right hasn't occurred yet。When this guy did the read of A over here。

 this right of A had already occurred。That's where I get the two。Okay， what about the next one？

Write A， write B， read B， read A。Any ideas there？Any else。对。Do you see why？As both rights were done。

 so you're going to get before any of the reading， so you're going to get the two guys written。

and so forth， you can do that same， test yourself in the same all the different combinations。

So then the question is what combinations weren't possible under sequential assistance？

What's something that could not be printed？Des 101， Okay， why not because right a。

Or right B is going to happen first。Before。Read a or read B that's right you can't get an order。

You can't get to sort of both these reads without。Or at least one you know these reads without touching at least one right。

 so before before the first read occurs， at least one of the rights have to occurred。

 and therefore you can't get the old values for both both things and that's why you don't see here。

Any combination where that's what plays out。Any questions so far， yes。それ点おいか。ぐらいです。

So the memory consistency model is sort of the contract， the promise from the hardware。

 that there will be some restrictions on what the state of memory can be。Okay，And in particular。

 so you're right in the sense that there's our first example。This one here。

 basically any combination is possible because there was no coordination in the memory。

 there was no memory consistency， so they could behave independently， they could print out whatever。

 in fact here， they did print out that illegal value in cost consistency。All bets are off。

But when we impose this sequential consistency abstraction。

 then there's some promise by hardware that。And mechanisms in place to ensure this that that won't happen。

Okay， so it makes sense。 I I asking that so。I just think third side to go before。对个收。

Be that I feel like I think good to。Always takes a。From the43。那他是这个。

So is this is like P threads create， so you're creating two threads within the same。Address space。

Okay， and so。They actually。They。They're sharing the same memory， okay。

 it's not the case of like an entire process for。Where it's a separate memory with， I mean。

 it behaves like a separate memory with copy and right and things like that。Yeah， sorry。

 I should made that clearly。Okay， good。嗯。All right， so this is the。Yeah before。

 this is a not sequence because it C。Because that's not possible。

Under of the rules is question consistent。Okay。SoBut that was because there was no codation between the caches。

But another thing that can happen is even if the caches themselves are coordinated。

Because of the out of order execution at the processor。

 things can sort of get reversed by the time that the loads and stores even occur。

 the memory system even observes it。So here's an example where what happens is that。You know。

 threadhread2 has this pool， this queuee of instructions。

 this pool of instructions it's trying to execute。And it includes both these two instructions。Okay。

 and it goes to， you know， the has the different function units。

And it so happens that this one is the one that happens first。Okay， so therefore。

 you print one because that's the current value of a。代ベ。And then similarly on this side。

 you could have this one go first。可以。And then。Later these rights to A and right to B occur。Okay。

So it's。Although we use the example of cashs not talking to each other。

The problem of supporting sequential consistency is one that involves more than just caches talking to each other。

 right， It involves the process realizing。The out of order executionrs throughout the process are realizing it can't swap these around。

If it wants to maintain sequential consistency。Okay。All right now。

So the dirty secret is that while everybody。Programrss and software and things like that want to have a bunch of consistency。

It's。There's a heavy performance penalty to bepaid， typically。

In order to have a machine a process that supports。是关系的事实。So instead。

 what you get on Intel processors and others。But those of one say sun， Oracle。

Are memory consistency models that are weaker than sric consistency。ok。And。

Operations such as defense operations。That allow you to。Yes。

Enforce an ordering between two instructions。So the notion is that the processor actually。

 because of its out of order execution。Would could give you this。And that's bad。

That's not we expected， so what you have to do is you have to put in between these two。On both sides。

One of these a particular type of fence operation， S fence， and that will tell the hardware。

 the out order execution that the order of these two things actually matters and therefore I better do this one first before I do this one and I better do this one first before I do。

Okay。So in a perfect world， the hardware would just provide sequential consistency。

It would be fast and you wouldn't have to add these silly fence operations in there。

But unfortunately， that's not the world we live in because people didn't want to give up performance。

that would be required to give up in order to get that perfect world in terms of modeling。

 and so instead we have this imperfect world where we have to put in fence operations if we want to ensure particular things order。

All right。So。But there are ways in which the processor does help， okay。

 so the processor does not allow for noncoherence in caches。Okay。

And there's a number of ways which is done， this was historically the first was known as Snoopy Caching。

Snoopy caches has nothing to do with Charlie Brown and peanuts has to do with the fact that the。

That you there's this bus， remember there's a shared bus that connects the memory system to caches。

And you have the cash controllers snoop， pay attention to what's on the bus。

 even when things that they don't request are going by。All right， so how does that work here？

So what we have is a tag。You're familiar with certain kinds of tags in your CA slab。

 right this is one in particular for shared memory settings。

An exclusive tag means a that you've gotten permission to write that you have a writeriable copy of that cash line in your cache。

So。The first thing that happens when threadhread one tries is right is that it first grabs the cache line in the exclusive mode。

And then it does the right。可以。And similarly for thread two。

Gras cache line that contains B in exclusive mode， it does the right。Now。

 when you go to do one of these reads in order to do the print。What happens is that the request。嗯。

The request goes out。Sa for a。So over here， the quest goes out for A。All right， there we go。

And what happens is that you。You put their request here on the bus， say， I'd like to read A。

This cast controller snooping on that bus and says，" oh， I have the latest copy Bay。Here。

 let me supply it for you to supply the value from the cash。

And then because this is no longer the exclusive。Copy of this cache， you change the state to share。

Okay。So this guy now has a shared copy and this guy also has a shared copy。Okay。

 so you set the tag to share。And notice that we did that based on snooping off this bus here。

And in particular， we knew this guy replied， we knew。Not to use this value here。

 that this was a stale value in memory and that the place to get the latest value of a was the cache line。

And this generalizes any number of caches and threads you could have 32 of these and similar things to happen when it's exclusive mode。

 there could be only one copy in one cache， when a shared mode。

 there can be as many copies as you like。And similarly， in order to print B。

 you first put the request for B on the bus， this cache controller who sees that says， oh。

 I have the latest copy of B， I'm going to change it from exclusive to shared and pass it to you and now it's shared in both places。

Yes。So when thread2 decides to look for。Why does it go to？し大ぞ。啊。So here you're right。

 it would first look at its own cache and it would be amiss。 A is not here。

So before what happened is it went to the main memory and got the stale value。Now is Snoopy caching。

 which is a way of coordinating the caches and keeping them consistent。

When this request for A goes out on the bus， this guy doesn't reply， this guy does。

And let's say you get the most recent value。So thread2 has no idea where a is。

 He doesn't know if it's in main memory。 He doesn't know if it's in some other cache。

 somewhere else in the system， doesn't matter because because of the Supreme protocol。

 all the cash controllers are watching what their requests are。 And so when a request for a。

goeses out on the bus， then anybody who has A can respond。

 in particular this guy has to respond because he has the exclusive copy of A。有 question， yes。

In what kind of situation with the value？They memory that is written。Will it be。所以。The value of babe。

 but at the same time， it doesn't supply。是。呃。So， if。

So it's always safe for the cache to respond right because any cache has a more value at least as fresh as what's in main memory。

Okay， because these are right back caches。Now， the case where memory supplies the value is。

 I if this was evicted。Right，So no cash has the value that you supply from memory。

But then the only difference seems to be that you don't。Really get the value from make memory。所以我是我。

Why do we have to have that？Because it was important that we got two and not one。

We wanted the recent value not the sta one。And when last another point point is when the last copy of this a。

I gets evicted， then you have to write back to update the memory to P2。

so that you don't lose the track of the real body。All right， good。Okay。

 so to ensure sequential consistency， we need both the proper cash memory behavior and also intra threatread ordering constraints。

Sometimes by inserting the fence operations。O。So for thread level parallelism。

 we're going to do a simple example。你飞。In this example， we want to sum the numbers。

Between 0 and n minus1。And we're going to do that by partitioning the numbers into K ranges。

Of this many values each。And then each of how many threads we have。

 say K threads will process one range。And then there' going to be doesn't divide evenly necessarily。

 so there's going to be some leftover at the end of this range。

And we're just going to accumulate that serially because it's not going to be。Not much if N is large。

And the first thing we're going to try is method one。

 which is that all the threads update a single global variable， okay， the running sum。

And we're going to have three ways of doing that， one is without seization。

 one is we're going to use our P37pho， and one we're going to use our P3 muttex。

 which is a7pho where the values are just zero。Okay。嗯。So again， single global variable。Here it is。

 Global sum。Here's our sepho a mut text when you use one of the other。

The number of elements that are some bytes thread is stored there。嗯。Thread IDs are stored。

And identifying each threat。Okay， so the number of elements were thread。 As we said。

 it was just the total number of elements divided by the number of threads and the automatic gets round it down。

 Things started 0。We're going to create all the threats one at a time。

So we let the eye thread know that it's the IDI。And then we passed that as an argument。

And the threads go off and run and then mentioned when all things are done， we have this join。

 we place the result。In a local variable， and then we finish up。

 so we say that if each thread did elements times number of threads，Then I sorry。

 number I with times number threads is how many that they did？Got done in all。

 so we start there and we finish off the rest of the list one at a time and because again。

 we're just adding up the actual numbers themselves， it's just a summing of E。

So it's n minus2 n minus1 done。All right。So here's what each the threats。对。嗯。So they compute。

So we've got this whole range of numbers right from zero to M is1。And we're just we're chunking it。

 right？So you just compute where you start， so you start at my D times number of elements of thread。

 so the first one starts at zero， the second one starts at a number of elements of thread and so forth。

嗯。Pms。The thread。And so forth。 And then you end at。That many elements later， right。

 so that's your range。And so you're just going to loop between the start and the end one at a time and accumulate to this。

Global variable。That's with no seization。Okay以。So how does that perform Well。

 with here's the number of threads we run it on starting with one。Okay， well on a single thread。

 this thing took two and a half seconds， roughly。We ran n equals to the 30th。

And it got better for a while up until around。I maybe eight threads or so。

 maybe slightly better after that。But this and the best speed overall was 2。86。Okay。

But it got the wrong answer。Why is that？You不要s。the same raised commission。Right。

 basically what's happening here right is you're reading， you know。

 even though it's a single instruction here， you're reading Global sum。

 you're adding I and you're writing back out Global sum。And in the between。

 if somebody else reads it and does the same thing， then you miss entire values。All right。

 so let's try putting a semopho around this。Okay， so at least this becomes atomic。Basically。

 no one else can when I'm adding I to the Global Sum。

 no one else is updating global sum at the same time。Alternatively， we can use the mute text。

Just the binary version of the74。And when we do that。

 we see that- so this was the one where the races。It's now sort of almost hug zero relative to the others。

Time lap seconds here， we see that the semaphore is horrendous and the muttex is also really bad。

Okay。We went from two and a half seconds to around 10 minutes。So that's clear not what we want to do。

Okay。So why the poor performance？Well， there's a lot of overheads in these both Mutexs and semaphores and you put them inside this tight loop。

You know， things get slow out， okay。So。Separate accumulation， it's a natural thing to try。

We're going to show you three methods of that， accumulating contiguous array elements。

Can you accumulate a space to rating elements and accumulate it registers？Okay， so again。

 we have this。Part of sum。And we have this parameter called spacing。All right， so as before。

 we divide the number of elements evenly by the number of threads。嗯。We go ahead and。

Set the partial sum， which is now on a perth thread basis。To be zero。 So when space single goes1。

 this is just you know p sum of0， p sum1 p sum of two， p sum of three and so forth。

 kind of what you'd expect。But we'll see in a minute why having spacing their helps。

We have P thread create as before join result， we have sort of add up the。嗯。The partial sums。

 so each of the threads has computed a local partial sum of the stuff in its elements。

 and we just want to serially run through those and add them all up。

 and that just gets us through the ones that divide evenly。

 we still have the same serial loop at the end for the leftovers for things when they don't divide evenly。

Okay， so what is the East threats code looks like again， a cap pizzaza start at an end。

And then has the notion of index that， again， with spacings1 is kind of what you were expecting before。

And it just goes through and it runs through this list and adds up， does all the sums。

 but it does it on a。You know， on something where it's。Own index。

 so it's accumulating in a part of La Pison array that no other thread ID。

 no other thread is also computing it。Okay。So when you do that。

 so here's the one we showed with a race。Okay， that was the Sierra Global counter and got the incorrect answer。

If spacing is one。We get this green curve， so we actually have some improvement by doing the partial sum plus we have the correct answer。

 always good to get the correct answer。And then if we set spacing to something other than one。

 which we'll talk about in a minute， we get even better results。Okay。

So in terms of the spacing is one case， we get a 5 x speed up。And the based apart speed up。

 we could get up to 13x。Okay， so significant。difference。系。So before I get to that。

 I want to ask about。Newute Texas。So why didn't I need a mut text for this？Yes。

In what sense in the sense that？No't worry it。一れで言いつけて。Space to work in。That's right。的医や力。Yep， yep。

 there's no data race at all here， right， they're all operating on separate accumulators。

 separate parts of the piece of array。Okay。So。So we had this notion that when we had spacing。

 it was one， we got the screen curve， when we have spacing。Greater than one。嗯。

Ter value greater than one， we got a better curve。So the question is why？Yes。push togetherでき。届れたな。对。

Thats， I mean， you're on the right track， you not saying the right word yet。それで。

For which one is maintaining。The updates fashion at。あって。老板。But I mean。

 they're two separate accumulators， why do they get placed in the same cache？ちキャ。

Because it's placed in the same cache line， right， that was the work of was line。

So here's a picture that looks like that right that。If you have the eight byte accumulation。That。嗯。

教育。Sorry， this is the P summary， okay， so here's the different zero7815。

But if within the same cache line， you could fit eight of these。Sums。可以。Then all these eight。Will。

You know， want to all update the same cash lines the cash line will。One， like zero。

Thread ID zero will grab the cache line in exclusiveusive mode and do an update and then thread ID。

 another one maybe seven will say， well， I need to update that cache line too。

 so it will grab that invalid the other cache line。

 grab exclusive a copy of that and so forth then go back and forth back and forth back and forth。

Okay。And you can do experiments where you see just how much ping ping happens in this case。

It does result in a lot of overt。Okay。So yeah， threats sharing and common cash block will keep fighting each other for access to the block。

Okay。So that's called fault sharing。So ideally though， of course。

 is that you want to have one of these accumulators per cash line。The cash block。

So if zero gets here， then the next counter you'd want to put here。

And the way we do that is through the spacing parameter， so if spacing parameter is set to be eight。

Then if you look at the back of the code， everything sort of jumps eight apart。

And then every cumative counter gets its own cash flow。对。And then you can see that from here。

This is showing that again， the。Spaccing use one curve。The as you space things further in part。

 you get fewer and fewer things competing for the same cash lines。

But it's only when you get to the eight case that you get you can it's kind of hidden under this other curve。

 but you get the curve that runs here。Can you get the best performanceers？

If you were to make spacecing even bigger than eight， like 16。

It's no better the 16 curve is right on top of the a curve。

So no benefit increasing spacing beyond eight。But eight bike values in a 64 bike cash line。

 you can get eight of them in there。And so if you jump space by eight， you jump over。Any questions。

Yeah，こ so。The spacing doesn't change anything regarding like cash fits and misses。

 it's just about using more。Becauseご。They can't like two threads can't access the same line at the same time。

Yeah， so we think of that as。As。So in cash lectures， when we just had a single thread。

 we talked about coldnesses and cones and capacim misses。

There's also a type of miss in this shared environment that's called a coherence miss。Okay。

 so these are misses when they are fighting with each other to access the block。

 they are suffering a miss right so the first one brings it into his cash。

And it gets evicted from the other guy's cash so it's over here so when this guy wants to read it it's a miss and it's got to get it and brings it over here and the meantime it validates this one because this is the exclusive copy and so then this guy suffers a miss so he actually is cumating tons and tons of misses。

Does this economists called a coherence myth because it's part of the coherent Cacoherence protocol。

Great， other questions。If you have few friends。It was called ballot。Like given region。

The UC Malik is padded out， and I think that has to do with。That's a danger。

Usually a good implementation Malik will avoid that by padding。Yeah。So this newtaes， I do the third。

So， if you。The second。That same piece of memory。离开啊。あせ？s see you click sign。つせ。对，行行。我 end up getting。

暂すね。Now， if a cash has a shared version of it， it can。It should respond as well。

that also just give the share version？YeahGood。Okay。

 and the third version we're going to look at is registered accumulationulation。

 so here instead of having them bother to write to shared memory at all。

 they accumulate in a local variable which the compile was takening to register。

And so all the suming gets done without worrying about memory at all。

 and then only at the end do you write out the partial sum into shared memory so that the main thread can then。

Go through and add all those up。And you get better performance still， right， you get this green line。

Okay， so Red was the best from the previous。Graphs， and now we get green。

So the total speed up is seven and a half， it's basically 2 x faster than the fastest。

Remembermory accumulation。Version， which is this red cur。嗯。

One of the things that this says beware the speed up metric。

ICan't remember if we've talked on this about this before but。

Sort of a lazy practice would be to say， I run my parallel code。On one thread。

And I see where that lands。And then I measure the performance。

Approv it from there and call that my speed up so if this is like the fastest thing here。Then。

I call out my speed up。But if it turns out that running the whole darn thing sequentially。

 it would be a lot faster than what you started at， that's really an unfair comparison。

So a much better comparison is to look at the fastest you version of the code you can write sequentially and wherever that hits on this time chart。

Right and then see how much you can speed up over that and what often happens is that it takes。

 you know maybe maybe the one thread parallel version， the two thread parallel version。

 the three pet parallel version， fourth thread parallel version。

All of them are slower in this serial version because of overheads of what you have to do to get them correct in parallel context。

 and it's only when you get it to maybe eight threads or 16 threads or whatever that you start to see some benefit of parallelism。

给一块始上来。Okay， so。Shared memory sharing memory can be expensive。

 we want to pay attention to true sharing， which is when they're both accessing the same actual fights。

Pay attention to fault sharing， it's in the same cash line。But different fights。

Use registers whenever possible。Use your local cash， try to cash hit whenever possible。You know。

 things that divide out evenly deal with the leftovers。

And when exam reform is compared to the best possible sequentialquest limitation。

 not just how much fast your own code runs relative to your own parallel code runs relative to itself。

Okay questions so far。All right，qui。I see how people did。

No only got 100% which made me believe I got something wrong to answer to you。All right。Okay。

 so we have these two threads， we have sequential consistency。没。And。Okay。

 so what orderings are possiblele， so initially zero and two？So。Okay。

 so is it possible to get zero and two？Yes， if this thread。

 these are the first two things that execute， you get zero into two。

It's if possible it gets zero and three。If this executes。First。Then these two and then that one。

You get zero and three。Is it possible to get one and two？嗯。So if this goes first。

And then they get you one。ピ。Okay， and is it possible that' maybe whether we seek it， okay？One two。

And I said， sorry。Okay， good， see that's why no one was getting right， I messed up the question。

 I meant to reverse these two。Make it more interesting，There was meant to be quite。

I was having all sort of trouble with the formatting and this。 it looks nice now。

 but it took me like， and I kept having retyped this。 I think one of the times I retyped it。

 I swapped the order when I was a tenant。 It was intended to be that similar to the example we showed in class。

That if you print it。If these were too reversed， if you printed b equals 3。

Then you knew that a equals 1 already so you can also print a equals  zero。So。

But the way I wrote that problem up they're all possible， so the problem is silly。But anyway。

 you get the idea okay， that there's certain combinations of things that。

Aren't possible when you insist upon sequential consistency。All right， good。SeeHow do I get this。没诉人。

All right， so how are we doing on this？Okay， so this the trick here was that we wanted true sharing。

Okay。And so in order to avoid true sharing， all you needed was。嗯。Was that each thread had its own。

Part of the partial array， right， So spacing was one suffice。

To stop them from sort of trampling on top of each other。So that's why the answer here is one。

And all right， people got this one good， so for fault sharing。

 in order to get them to be in separate cache lines。

 you need to have spacing Vc over T and the only tricky part was asking you whether to round up or round down。

 you need to round up because you need to make sure you're sort of fresh past into the next cache line。

So you need to to。To take this basically the ceiling of sea overt。Yes，なウジる。ロし。So。どち必し。

When that be to。If I round up， that means I'm space them far apart that they're not sharing cash needs。

And therefore， there's no fault here。All right， other questions in the quiz。

New something was suspicious when no one's getting 100%。



![](img/a9c12b94727e58b1fb7d762996df4039_1.png)

Good。

![](img/a9c12b94727e58b1fb7d762996df4039_3.png)

Okay， so let's take the rest of the class and look at a more substantial example sorting。

It turnss out there's lots of ways to sort lots of proposed methods for sorting on efficientlyly on parallel machines。

In multi thread and multiple cores， we're going to look at variants of Quick sort。

 so let's remind you of how Quick sortt works serially。You have a set of values， you choose a pivot。

From that value， according to some rule of pivots。And you rearrange such that all the values。

L is the set of all values less than equal to the pivot。

 R is the set of values greater than equal to pivot。

 recursively sort L cursor or R and return the combinationnation。 So it looks like this。

 You start with x。You pick a pivot。🤧嗯。You divide things into all the things less than， you know。

 all the things in X that are less than this。啊，批。All the things that are greater than the P。

And now you pick a pivot for this site and repeat over here。

Until recurs and so forth until eventually that entire side gets sorted。

Then you pick a pivot through the right side。And you go until all those things are sorted。

And then the final result looks like that。行。So you can see why this has a feel for why it might be a nice thing to try to paralyze because once you've got this thing divided into the left side and the right side。

 there's no interaction anymore between those two sides so you might as well do those two halves in parallel。

Okay。And so that's what we will do。嗯。Okay， so first this is just the code。

 if the number of elements we're trying to sort is the most one， nothing to be done。

 if it's exactly two， then if they're out of order， you swap them。呃。Otherwise， you're going to to。

To partition it。And return am， which is sort of the position in this list of。

Of where the partition falls。So if M is one， that means you picked up very unlucky partition。

 everything in the。And that in the part of the array is bigger than M。

And so there was bigger than the pivot， and so there was nothing to be done。

But the normal cases is that M is bigger than one， and so you sort on that left half。

And then similarly， you check for the extreme where the item you think does a pivot happened to be the greatest item there was there was nothing to be done to the right of it。

 but the typical case， there is nothing to be done to the right of it。

 and you go ahead and do that serial。So recursly sort LRR if it has more than one element。O。

So let's look at the parallel version visually， right， we start as before。We do this。

 and the only difference now is that we pick both these pillars at the same time。喂。

And do those in perel。When we do， we in parallel， we get these pieces like this。

Now we have four pieces and we recurse on those in parallel and so forth。Until eventually all that。

Pallllel recursion stops and we produced the sort of version of these two halves。And then we're done。

可以。So if you look at the thread structure， each of these sorting tasks has some range of the array X。

And it's doing its thing inside there， going to run as a separate thread。Now when these。

 so it turns out， like I said， there's a lot of overhead in doing things in parallel， so well known。

For decades is that when you reach a certain problem size， a subprom size， that's sufficiently small。

 you might as well just do the serial code。OkayAnd so when we get subranges that are sufficiently small。

 we'll use our fast zero quickword to finish it up。可以。But if you have a piece that's large。

 you're going to partition the subrange。And spawn two tasks to deal with the left and right side。

Okay， so you have this task is to tasks。And this one takes the left and this one takes the right and open。

可以。So sort of the simplified top of a code。呃。Right， you just。There's a base and N。

There's a task queue， we have this helper routine that we're going to call。

So we set up the data structures called Cur so routine。

Keep joining threads until they're done and then free the data structures。

So what does this look like， the helper thread， what it does is that if the。

The number of elements is smaller in this threshold and the threshold we're going to use to switch to serial code。

 and we go ahead and sort serially。Otherwise， we're going to create this new task and ask it this sort。

Okay。So large partition spawn news sort count。Okay， the sort thread is going to。Again。

 call the partition routine that fix this M。And again。

And either side is greater than one in its size， it's going to call the helper routine。

To cursively sort that part as well。Okay， so you get the task parameters you form the partitioning step。

 you call acursive sort on each partition。All right， so how does it do？Okay。So。

Our parallel quick sort we're sorting。2 to 37 random values in this particular case。

And what we're plotting here is where our cutoff is。

 what fraction the input do we decide that now is the time you transition to serial sort？可以。

So if we one means。We do sererraleghal way， so that's way up here。Okay。And so forth。You know。

 as we go。Further along this curve， we basically somewhere in here。

 I guess reads a sweet spot somewhere in here， not clear exactly where the lowest spot is。

 but what that says is that when。呃。This， this much of the。If you have a sub problemm of this size。

 then you going to switch to the。To the serial thing okay。

 but you don't want to do that too soon because then the things start slowing up again right if you jump too soon you're doing serially。

 you've missed out as some potential speed update that you get from the parallel version。

And the best speed up to get in the end is 6。84。Even though you potentially could have。

 you know you're running eight cores， each of its hypothetics， you could potentially get。

So this is the potential the eight core。This is say if you just your straight line here。

 if you just got factor of eight speed up， you'd go there。

 there's two way hyperthe so you could get up to a factor 16 speed up， you get there。Okay。

 so what this is showing is that even with the best choice for。For when to switch the serial version。

 there's still some gap here。You're not getting the perfect linear your speed。Okay。Any idea is why？

Is there still any part？Of this code that's actually I guess you can't tell because I didn't really show you inside the box。

 Well， it turns out that one of the reasons this isn't doing perfect。

Speed up is that partition routine。Where you given a pivot。

 you scan through the elements and you accumulate all the ones that are less than over here and all the ones that are right than over here so you can hand off a less than equal pivot right then that was done serially in this code。

And。Because of that。啊。The overall best speed up you could obtain was limited。

And the way we think about that is something that's known as Amollf's law。So。

If you have a problem where there's amount of tea， total sequential time required。And you say， oh。

 of that total， I'm actually able to speed up some fraction p of it between zero and1。Okay。

And of that amount of that work， I actually get a speed up factor of K。Okay， so if I， if I ran。

On eight cores and I got perfect speed up then K would be8 if I ran on eight cores。

 but I only got factor of six speed up， then K would be six。

Then the thing to observe is that the resulting performance is， well。

 on the part that you are able to speed up。Which is the fraction of the word p times t that is manable to speed up。

You get your nice factor K B， so it runs k times faster。

But there's still this remaining part where that ran Si。

This one minus p fraction of the total that ran serial。So the and this can be the bottleck。

 and Amdo's laws is this formula。So even if you could get infinite speed up。

 cake equal affinity on the part of the code that you could speed up。

Then all best it does is that drops at to zero and your time is still1 minus p times t。

which may not been what you were hoping for。So here's an example， suppose I say， okay。

I'm able to speed up 90% of my code， and not only that I can speed up by a factor of nine。😡。

So that seems like overall， I ought to be speeding up the whole thing by， I don't know。

 maybe 80% or something， you know， but no， because of Amda's law， yes， on that 90%。

You get a speed up of nine， but on that 10% you're stuck running。Serly slow so。

It takes one time unit to run the parallel part， one time unit to run the sequential part。

And so the end result is two， so you only sped it by a factor of5 you lost。Almost half your speed up。

Because of that 10% of things you couldn't speed up。And in fact。

 the maximum possible speed up in this case is。You know， is one。Okay。は。嗯。

So in terms of parallel a quickword。The partitioning at the top level， I picked that first pivot。

The code just ran through serial， so there was no speed up in that top partition。

Okay in the participants part， the second level I already got it split into two pieces， right。

 so they're on expectation， at least they're half the size。

Each and so I can get potentially 2 x speed up and similarly 4x speed up，8x and so forth。

 things go down on the case level I could get up to2 to the K minus1 x speed up。But you know。

 that top level is going to。Still kill， right。Okay。And so in order。

 if you really wanted to get better results or have this speed up for on larger machines and so forth。

 you're going to need to paralyze the partition step。Okay， and there are ways to do that。

That are both kind of like Quick sort， and like I said， there's other ways of sorting。嗯。

So one common way would be to just grab at random a whole bunch of pivots。Okay。

 and then sort those pivots。And then now there's c bucket boundaries。

For the rest of the rest of the era raise and then you just go through and you take each each core and take a chunk of those。

Of those other values and say， oh okay， this value falls between these two pivot points。

 I'll stick it there and so forth and so you just fill up all these buckets and then you're end up with a situation where you've got this array and all your little pivots。

That you've all now done in parallel。And then you just have to。

 and then all the things in this bucket fall between these two pivots。

 so you just have to recursse on these things。Okay。

 and sometimes these things are already small enough that you could just do something seriouslyly at that point。

O。I've forgotten to have this animation here， so this is paralyzing the partition step。那。

One way to do that is other so another way to do that which is more like quickword is you pick a single pivot。

 but you just have them each create their own little splits between these right so this thread。

Just splits up L4 and R4， and then you collapse them together。

 can together so that all the L's are first and then the R's are second。O。But on the shark machiness。

 at least and the size of problems that we were running。

 the parallel partitioning didn't really help much。

And so that's why we showed you the simpler results。Okay， but smarter algorithms。

 other other machine contexts， parallel partitioning or these other other styles of running。

 sorting and parallel can be very effective and you can get you know， speedups of。

Of 60 on these 72 core machines and stuff sort。So it's definitely doable to get。

Really nice speed up in a perous way。Okay， so lessons learned。

 we must have a parallelzization strategy。Things like， you know。

 find some independent work for the process to do， use to conquerer。

We saw that once we' put in semaphores or New Texas。In inner loops， that was extremely expensive。

 so we want to try to avoid those。We want to。Understand things like fault sharing and true sharing and races and things like that。

嗯。And part of that is you need to understand how the cache is laid out。

 which you guys know from doing all your cash lab stuff。AMD's law can be a killer。

 make sure that you think about how much。The overall code you're able to speed up before you get overly optimistic about how much。

Befit your parallel is going to get。嗯。But you know。

 this is the world we live in right with lots of core， and they can be。

 very useful for speeding up programs， and particularly you can get it's pretty easy to get modest levels of parallelism。

And you could test out multiple strategies。And just like。

 test out multiple strategies for yourmalicL and find out which ones actually achieve the best performance。

跟一关しだ。

![](img/a9c12b94727e58b1fb7d762996df4039_5.png)

Okay， so that's it。Next time we'll talk about the future of computing。



![](img/a9c12b94727e58b1fb7d762996df4039_7.png)

。

![](img/a9c12b94727e58b1fb7d762996df4039_9.png)