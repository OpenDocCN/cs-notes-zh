# 加州大学伯克利分校【中英⚡虚拟机与托管运行时｜CS294-113 Fall 2015, VMs and Managed runtime】 p11 P12 b -BV1qBqPBYEy1_p11-

he'll be Skyping in from Germany， Call is the lead implementer of the Pipe system。嗯。

And he'll be talking about tracing and meta tracing as an implementation technique。

 kind know at this point。Am。You've kind of reached the state of the art of what's done in production in what we've covered with the exception of concurrency。

 We haven't talked about any concurrent techniques， but that aside。

 production systems use mostly the sort of stuff we've covered future weeks now will be mostly talking about techniques which are in labs in research and development that are been experimented on。

So pie pie metaraccing is one of those techniques。 We'll be talking about some of the partial evaluation stuff going on oracle。

嗯。I'll give you a flavour of where the field might be headed。Okay。

 so today I want to talk a little bit about an alternative。

Gbage collection approach called inexact or conservative garbage collection。

So as you've probably encountered already。Implementing a garbage collector can be difficult。

 There's an awful lot of detail that you have to get exactly right using the approaches we've described so far。

 So you have to find every single place。That you've stored in reference to a live object。

 especially if you're having a moving collector。If you miss out one of those things。

 the pointer doesn't get updated when the object gets relocated and bad things happen。 you know。

 the next G C after that or some other time in the future。

 and debugging is a difficult kind of thing。嗯。If you， if you're building a compiler。

 as you guys are right now， you have to track all the locations that the compiler uses as as well as the。

 the source of the VM。 So you have to build into your compiler tracking。

Information to identify where which registers things might be in if garbage collection points or stack slots。

And， you know， maybe you want to reuse some existing compiler that doesn't have that capability。

 What are you going to do。Also， perhaps you want to pass， you know， you're implementing a language。

 You want to pass references to foreign code， and you have no way to track what the foreign codes gonna do with a reference。

 So one approach is， you know， a kind of guessing。It's called conservative collection。

What you do is you scan memory looking at the contents of words without really knowing what's in those words。

 And if you see something that looks like a reference to an object， you assume it is。

And you assume that that object that it looks like it's pointing to must therefore be alive。

 And that's called conservative scanning。 But you basically， when you see a value。

 you conservatively assume it could be a heap reference。 So typically， it's a word。

 you're looking at words。 And if the word contains something that looks like an address within the range of the heap。

 Then you assume it is' an address within the range of the heap and the thing that it's referring to is alive。

 and there。In a conservative system， because you have no control over。

 say what the compiler or the foreign code is doing with the pointers。

 you might assume also that the references that appear to fall in the middle of an object are going to keep the object alive。

 So here's a little sketch。 We have a bunch of objects。In the heap and a stack。

 And you see these values scattered through the stack。

 There may be similar things in library areas of the code， whoops。Go back one。And what。

 what you're gonna to do in a conservative system is just walk through all the memory that you think might intended reference。

 And if you see something that looks like a reference， you just assume it is。

And that's conservative scanning。So in practice， you tend to do a mixture of the two because doing some amount of exact scanning is usually not too difficult。

When you implement the heap and you implement your own objects， you should。

 without too much difficulty to be able to figure out where the references are in there。

 It's much more difficult to track things on the stack or in foreign code。So often the。

 the two approaches are mixed。 But in any particular word。

 then you're going to make a decision that's either conservative or exact。 If it's exact。

 then you know exactly what's in that word。 And if it's conservative， you're just gonna make a guess。

Now there are a number of pitfalls to this approach。

One is that anytime you find a reference conservatively to an object。

That means you can't move that object， so。Wai。Exactly， it could be an int， right。

 It could be some random value that's got nothing to do with that object and you can't go around writing。

 rewriting the data in someone's program。 So so those objects。

 So whenever you make that decision the object that is being referred to has has to reside now that address it's pinned by that reference even though even though it might not be a reference。

 So if you try and build a collector or a compactor that also has to deal with some objects being immovable。

 that complicates the implementation of those considerably and may also negatively impact the performance because now probably in a loop of whatever' is doing the compaction of the relocation。

 you're going to have to do some kind of an exception test and say， oh it this guy pinned。

 or do I work around them you kind of building in a fragmentation mechanism into your system。So。

You may also have the problem of unreclaimed garbage because when you find one of these values。

 it's going to refer to an object and keep the object alive。

 even though it might actually not be a reference， it might be some random piece of data that just happens to look like a reference。

So the claim is that conservative scanning is safe in that it doesn't premature or reclaim objects。

 but because it might be fooled by something looking like a pointer。

Then it might keep things alive longer than than they should be。

 If that object then is connected to many others， then the， you know。

 the amount of garbage that goes unreclaimed is potentially unbounded。 It's。

 it's all the question of probabilities and whether you got lucky on or unlucky。

This gets worse as the heap occupies a larger and larger fraction of the address base。

 So if you imagine if you've got something that's taking a few kilobys， you know。

100 kiloby of heap in a 32 B system is a tiny fraction of the address base and very few random inages are going to point into that exact area。

 But if your heap is 2 gig in a 4 gig address base。

 then there's like a random one in2 chance that any arbitrary bit value is going to point into that heap。

So it， it doesn't。 it's， you know， it's a big risk if you're gonna do that on a system that has。

High occupancy in the address base。 Obviously， if she switched to a 64 B system。

 then the probability is tilt in the other direction。um。

You may also have the problem that the things that look like references are not within your control。

 So when you're implementing an exact system， a typical trick is when something gets deated。

 it either moves out of a boundary that you're scanning or you explicitly overrite it with things that make it look like there're in no pointers Well you can't do that in a conservative system because。

 for example， if the compiler takes a value and spills it off to the stack， even though it's dead。

 it might still look like a pointer to an object in a dead stack lock。

 but you don't know it's dead because yout you haven't built the mechanism that tracks tracks these things。

 So there's a number of potential ways that you can get unreclaimed garbage。

Despite the claim of safety， there is all， there are also ways in which you can get premature or reclamation。

 So the typical implementation of a conservative system will rely on the fact it will only look at word values word aligned。

 So if you do something to hide a pointer or disguise it in such a way that it doesn't look like a pointer。

Then the GC system will be fooled。 So， for example， if you're doing tagging or shifting， well。

 then the tagging， particularly a shifted representation with a tag bit。Requiring shifting。

 then that's gonna to cause a problem because it's not gonna look like a， like a pointer to a。

 to a conservative collector。If you store references in an unaligned manner that therere on arbitrary bite boundaries。

 that can also cause problems。If you do any creative tricks with address arithmetic。

 do you guys know about the。The trick of having bidirectional pointer links by X oring the pointers from opposite。

 Yeah， so I see some nodding。 So if you have， if you store， you know， functions of pointers。

 then unless the garbage collectors been told to understand those functions and invert them。

 then it's gonna to get fooled by that trick too。 Or if you you store things in places that the garbage collector is not gonna look。

 So you write pointers to a file and then assume you can read them in back again later or you do compression tricks。

 then then the conservative collector。Is gonna be fooled。 And that's， you know。

 when you're linking to third party code， how do you。

 how do you guarantee that none of that stuff is happening。

 It's really hard to know whether any of that stuff is happening。The。

 the one that scares me the most， though， about。About conservative collection。 I that。

Compilr optimizations can do this。 And you really have no control or very limited scope for discovering what's going on。

 So here's a little concocted example。 Imagine we have a loop that's doing an object copy。

 We've written in our virtual machines。 So we've written something that involves maybe macros on the destination and the source。

Now， it's a perfectly legitimate optimization for the compiler to change those what looked like pointers into offsets。

Are a best off some common bass。 And now， if you interrupt this loop and you look for pointers。

In the registers， you don't see anything that looks like source or desk here。

 or pointing to source or desk。 The only pointer here。Is to the base of the heap。

 and the rest are just indexes。And so if you're gonna to do conservative collection。

 you have to somehow get some inner peace that this is not going to happen。

 You either have to know what the compiler is going to do。 Opimisation wise， or you。

 you try and write some tests that expose this and test every time you update the compiler or you pray or it's not a happy place to be in my。

My opinion， you know， and basically， you， you know。

 how do you know that this is going to happen or not going to happen。

 So I makes me feel very uncomfortable。Now， despite that。

 conservative collection is still widely used the most well known。

Coor using in this style is known as the B Collector。Available as open source as URL here。

 it's been used in many language implementations because it's easy。 you just link it in。

 you call malloc as if it were calling Mal as if you were calling the real malloc， but in fact。

 you're calling the reimpleation in malloc that's in this collector and you don't have to call free because the collector takes care of the frame。

U。In fact， the very first。JD K，10 and1 dot1 used a very similar collector to do collection of the Java heap。

But this program。Shows that that maybe is not such a good thing。 So in this programme。

 we have a recursive function， slow sum。That allocates a big array， this thing up here。

And then immediately throws away the reference。 It doesn't keep the reference。 So we call new。

 We ask for the hash code of this thing， but we don't keep a reference to the array。

 So it's clear by trivial inspection that the only live data here。

 the maximum live data here is one array。Unfortunately， however。In the early JDK。

 hash code returned the integer representation of the address of the object。

And so when you stored the int hash code， you kept the object alive。

 And so in this particular function。As the recursive stack builds up。

Each stack frame has a copy of the hash code of the array that was allocated in that frame。

 And they're all kept alive by the in the conservative collector。

 So you could run this with some typical numbers， you know， in like a megabyte on an exact JDK。

 but on a conservatively collected one， you know， hundreds of megabytes。

 it would still run out of memory。So I， I think。I personally am completely uncomfortable with this approach。

 And my advice is， don't do it。 I I just can't。Get to the point where I think that this is correct enough to be really usable。

In， in practice， and it reminds me of a certain。Quote。No sound。Probably gonna blast your ears out。

Now， it's turned all the way up。 It's Arthur Dent from the hitchhiker's guide to the galaxy saying this must be some other use of the word safe with which I'm not previously familiar。

Okay。So， that's。My take on conservative collection。

The other thing I wanted to talk about is metrics and how you compare collectors and how you measure them。

U。There are a number of different things you can measure in a collector。

I've listed the important ones here。So throughput or overhead is a sense of how efficient the compel collector is at doing its job in terms of raw。

Time taken to reclaim stuff。Ftprint is a measure of how much extra space you need other than the live data for the collector to。

Compute effectively。Pause times of the interruptions。In computation that the collector induces。

 and then there's energy。Let's go through these。 Not there is no single figure a merit， so。

There's just no straightforward way by which you can say This one is better than that one under all circumstances。

 You have to compare across all of these and maybe some others， too。So。Thput an overhead。嗯。So。

Assume we have a fixed mutator workload。How much of the wall clock time in your running application can you attribute to the collector。

Well， if you have a simple， you know， kind of old style thing。

 a serial implementation of a batch collector， something like Mark sweepep that， you know。

 you run without collection and then you do collection and then you run without collection。 Well。

 then it's easy to calculate this right， the red parts the times where the the G C runs the green parts of the times where the mutator is running。

 you wrap the red parts with some timer code， you add up all the times and you do the arithmetic straightforward enough。

And that gives you a measure of。Of overhead。Now， if you want to measure a throughput。

 one way of doing that is to say， okay， how much space did we reclaim over all of those runs divideiv that by the time it took to reclaim that space。

 that gives us a reclamation rate and that gives us a way of comparing how effective the G C is a reclamation and it's worth noting that if your programme loan runs long enough。

 you know， if it's doing many， many GCs， then the allocation and the reclamation。

 they converge towards the same thing。 So you can use allocation as a proxy for that under a long running in a longrun program。

Unfortunately， for anything more complicated than that， it gets really difficult。

 So imagine you have reference counting。How do you measure the overhead of a reference counter But you can't。

 you know， put timers around every increment and decrement because you'll add so much time from the time measurement。

 you'll get the wrong answer。 If you have a reader or a right barrier， Same thing， you know。

 there are only a handful of instructions。 You can't put timers around those。

 So one possibility is to compare it with the system with no garbage collector and see how much is slower it gets。

 But as you've probably seen， the problem there is the system with no garbage collector won't run for very long before it runs out of memory。

So that's gonna limit you。 But there is this trick。 it， it was easy。

 It was more applicable in the olden days with them。More predictable micro architectures。

 But the idea is， if you have some low overhead operations， such as card table marking。

 that's idotent。You just do it twice and you measure the time of the run doing it once and the time when it does it twice。

 And that gives you the idea a good estimate as to how much the cost of something like car sample marking is。

Yes。Yeah， so that's the problem is that， you know， a modern micro architecture makes a whole bunch of things。

Ha， you know， right， you， you， you don't get the same cost the second time round。 So even that trick。

Often is not going to give you the right answer。 So you have to know what the micro architectureure is like。

U。To understand， but if you're on a very simple， like an embedded process。

 it might be a reasonable technique。So in practice， what happens is people go to a。

A less satisfactory stick， which is you implement two different garbage collectors。

 and you just measure the ball clock time of the entire system with them both。 And， you know。

 the one that takes less time is， has less overhead。

 You don't have any sense of where the zero point is。

 And so you don't know kind of where you how how optimal you're getting。

 But it does give you a way of doing comparisons。 You have to be a little bit careful in that if you're measuring on a parallel system if。

 if， you know， you have to give them the same amount of resources cos or whatever。 to give a。

To give a fair metric， because you can in most garbage collectors。

 if you can offload some of the work into a parallel thread and decrease the wall clock time there。

 even though it might be a， you know， a large extra fraction in terms of resources。

 that's usually a good trade off。When it compares to comparing systems for footprint。

 it's rather different in that the footprint is， you know， it's not a dependent variable。

 It's a variable you get to control。 You see how much memory the system is being given and you run it within a chunk an allocation and see how well it does。

So the only way of measuring， the only way of determining how the the system response to fraud is multiple runs with different allocations。

So， you。Use whatever tools on own your system to， to limit the amount of heat or either virtual or physical that you're running。

 in， and then， you know， you can't make it smaller than the amount of live dataca it won't run。

And so a common reporting metric to normalize things is to say the heap size was。You know 1。3 x。

 the size of the maximum live data set because， you know 1。0 is your absolute lower bound。

 What is it above that， Is it twice， iss it one and a half， Is it more than that。

 That's the usual way that gets reported And the throughput obviously is going to vary with footprint。

 So if you run a Mark sweep collector in a system that has a heap that's just a tiny bit bigger than the lay amount of live data。

 It's going to be collecting an awful lot。 You know， you know， allocate an object you'll collect。

'll allocate an object you'll collect the throughput will be terrible。

Whereas in a reference counted system， the throughputs almost flat。um。

Indi independently of how much extra memory you give it， so。You have to。

 you have to do a whole bunch of measurements as you vary the， the footprint。

If you get to the point where you increase it beyond the size of the physical memory and you give it more virtual memory than you have physical memory。

 usually with any kind of garbage collection， that's a disasterca there's no locality and。

 and the system will fall off a cliff。 So I've driven drawn a kind of a sketch。

Of what one of these graphs might look like。 You know， we're， we're varying the heap size from 1。

1 times the live data size to what to 10 times。And let's say this is a Mark sweep system。

 It's gonna perform really badly with a very small amount of memory'cause there'll be a ton of garbage collections。

 And then it'll rise to some， some peak， which is close to。You know what。

 what the system would run like without a garbage collector in infinite memory。

 probably not quite that close， but something like that。 And then as you increase the memory further。

 you know， there's a cliff that you fall off due to paging。 And before that。

 you might fall off a lesser cliff as you exhaust the。

 the T LB spread in the collector and you youre spending a lot of time in。In T L Bs， you'。

 you'll get an interesting curve anywhere， nonetheless。So what about Paul's times？嗯。

A batch collector， such as Markwe， will have really excellent throughput when it's tuned at the right size and you give it enough heap。

 But the price is， you get these really long pauses that are proportional to the size of the heap。

And that will often make it unsuitable for， for interactive use or other things that areertency sensitive。

 So a simple way to compare things for that is just to measure the， you know。

 the maximum pause time of the average pauses time。

 But the problem with that is it doesn't account for clustering。

 So if you imagine a situation like this where you're running in the system。

 And you've got pauses of a certain duration Well spread out。

That's going to feel really different from a system where you move those pauses together。

 And technically， you're making progress a tiny amount in these gaps。

So you can't necessarily count this as a pause。 But in reality， from the perception externally。

 is that that's a pause， one longer pause。And so， we need。We need a way to。

We need a where to account for that。 And so we， there's a better pause metric， which is。

Introduced early 2000s called minimum mutator utilization。And the idea there is， we take。

A time window。 And we slide it across this picture。

 And we look at what the worst case utilization is in that time window。

 and then we report the the fraction of the time in that window that was used in the that was spent in the mutator。

 So let's do an example。 let's。We have these， this trace with some pauses。

 if we use a time window of 03 of a second or less。 Well， the longest pause we've got is 0。

3 of a second。 So if the window sits right on top of this， our utilization is 0。

 because we're spending all of our time in G C。 So at that point we're at 0。 And any time。

 any window smaller than that will be at 0。 once we get above 0， however。We can。 we can actually get。

Non zero utilization。 So if we take a half second window and slide it across， then at this point。

 we're spending 02 out of 。5。In the， in the mutator。 So that should be  point4。Yeah。

And then as the window goes up， we get kind of a linear growth。 So with one second， we get。

7 of that spent。 But eventually， we'll get a window which spans two pauses。And then we get。

A decrease。In the utilisation。 So a one and a half second window will span these two G C pauses。

 And the the worst case is we spent a second out of the second and a half in the mutator。 So that's。

A two third utilization。 And as the window goes up， eventually it reaches the entire program。

And then the report the MM U for the entire program。

Is the fraction of time that was spent in the mutator versus in a pause。

 So that's a fairly straightforward calculation。 If we do the same thing again for our clustered scenario where I've moved the G C pauses together。

 you see there's a clear variation。 These are the old numbers。

 These are the ones for the clustered numbers。 And you can see the numbers are all significantly worse。

So the typical thing。You would do with that。 So there's the， you know。

 half second window over that G C pause gives us only a hundredth of a second of。

Utilization of 200ths。啊。And so on。So if you plot the actual utilization times。

 the minimum utilization times versus the window size。

 you end up with a graph like this that rises monotonically。 But in the MM M U plot。

 we divide each of them by the size of the window itself。And so you end up with a graph like this。

 which， you know， goes between 0 and one。In terms of the minimum muttaator utilisation。

 and it can have these depths because the util time stays constant。 But as the window gets bigger。

 the fraction of uilisation goes down。So。A couple of years after that。

 there was a proposal for a slightly different definition。Called the bounded mutator utilization。

 The idea there is that we report the minimum for a particular window or any window larger。

 So that kind of crops off the weird， weird little monoonic， non monotonic peaks。And this is。

 this is a pretty good metric。 And you can see that's a a decent visualisation of what's going on in those two cases。

 You know， the， the， the blue case has much better utilisation than the green case。

You also get a couple of useful points on this。 So where they intercept on the X axis occurs。

 That's how our longest pause。And the intercept on the Y axis gives us the ratio of mutator time over total time。

 So sort of the non pause。Computation in our system。 And obviously。

 this doesn't have to be just G C pauses。 You comp can apply to any of the kind of pause。

 If you compiler， for example， pauses， execution， you can include those in the pause column calculations。

 too and and come up with some reasonable metric。 Now。

 the only problem with this is in many systems which have mostly low pauses occasionally。

 there's a very long pause， like a full G C。And then the MM M U is skewed entirely by。

 by that occasional long pause。 So it's still occasionally worthwhile plotting pause time distribution。

 So the number of pauses of a certain duration against the duration。 And。

 and this is a stolen from a paper， typical kind of graph you'll see there's a few outliers。

 Longish pauses。Probably from field G Cs。 And then the bulk of them are much shorter。

 And it also reports the， you know， the 95th and the 90th percentile and stuff like that to give you a good feel for。

What the distribution is like。So。I thinking of this earlier。

 but it might be interesting to explore this。On a graph。 So if we draw a。A graph of。啊啊。Heap size。

Versus。呃。Throughput。Throughput。And， you know， we label one as the throughput of the system with no garbage collector and infinite memory。

 So that's kind of the best we should be able to do as across there。Then。

And then here is the minimum size。 That's 1。0 in terms of live Max live death。

 usually you'd probably do this in a logarithmic way， too。5，10。

 let's say here is the point at which the system runs out of。Real memory。

 And then try and plot a curves on here that illustrate sort of typical garbage collectors。

 So let's start with an easy case。 What， what do you think the shape of the curve is gonna be for a reference counted implementation。

 You know， what's the throughput。 assume we've got a high speed， you know。

 a compiler that's generating good code and the rest of the system is well tuned， You know。

 and we can drop in any collector we like， If we drop in a simple reference counting system。

Any guesses as to what the shape of that curve is gonna look like as we increase the height heap size。

Where do we， Where do we start off。On the X axis between naught and1。Anyone got a feel for it？

Who thinks you spend half your time in reference counting in a， in a fast system。A quarter。

A quarter is about right。 I I would say for a reference counted implementation。

 you're probably going to start at that point。And it's going to be。More or less flat。Of course。

 at this point， when you reach paging， you know， the systems gonna drop and the reference counting implementation will drop with the rest of the。

Performance。What about Mark sweepep。What's the shape going to look like。Here。

 we're going to start really low。We got another color。We got a green。So in a marked sweep system。

 if you give it just the minimum amount of memory， the performance is terrible。

 The throughput's gonna be way down here。And it's going to rise。Pretty quickly， up to its peak。

And then sit there。 And the peak is going be pretty good in and a decent system。You know。

 it's itll perform slightly better， maybe。 And then eventually。

 it'll start dropping as TLB misses occur。 Then when it reaches the paging point。

 it's just gonna fall。Really sharply。 if， if the program without。

A garbage collector was like this ship。 but this is gonna be much worse。 I've seen。

 I've seen G C pauses go from a second to an hourwa by doubling the heaps size。So。

Cause you're basically， you know， disk speeds for most of the memory accesses。What about。

A semi space system。Any guesses。Where's this sharp edge gonna be。It's not。

 it's not going to be out here， right， because of the semi space， it's going to be halfway。Right。

 logarithmmic express， wherever P over2 is。Somewhere out here。It's going to fall off much sharper。

 but it probably has a little bit better performance due to the better allocator。Something like that。

And so on。You can underaw these out for a different collectors。 It I， it's interesting in that。

 I don't actually think anyone's ever trying to do this in a publication and compare them。

 But it's not trivial to switch garbage collectors in most implementation， so。Okay。So。

Wrapping up the state of the art is you've， you know。

 I've given you three metrics throughput footprint and pause time。

 It's pretty easy to make one of them look good by the cost of the others。

 There are a bunch of systems that do fairly well on two out of three。 for my money。

 doing well on all three is still a an an unolved problem。I didn't mention energy。

 and that's somewhat deliberate in that there's actually very little work being done on studying the energy of garbage collection。

 You can probably count the number of papers on the fingers at one hand。

 I found a couple of recent ones when I was looking around yesterday。 I put them in the bibliography。

 someone from。From Qlcomm doing studies on Android。

 running on phones and and changing the G C heuristics to prolonged battery life。

 that's a promising direction。 But no one's really looks at this from the point of view of a large scale system。

Okay， that's it for today。Next week， we'll have So I'll send you some reading on tracing compilation。

In advance， of call Friders。Talk， and then we'll。We'll hear about that。 And if we've got time， we'll。

 we'll cover some other material any。Questions， concerns。Jit going， okay。2 thumbs up over that。 cool。

 yeah。All right， thanks。