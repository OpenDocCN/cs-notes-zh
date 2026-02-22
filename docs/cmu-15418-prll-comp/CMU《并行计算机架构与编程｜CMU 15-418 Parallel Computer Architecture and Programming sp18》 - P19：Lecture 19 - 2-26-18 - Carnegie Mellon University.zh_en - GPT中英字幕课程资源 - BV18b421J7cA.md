# CMU《并行计算机架构与编程｜CMU 15-418 Parallel Computer Architecture and Programming sp18》 - P19：Lecture 19 - 2-26-18 - Carnegie Mellon University.zh_en - GPT中英字幕课程资源 - BV18b421J7cA

で子。我先打开。Okay。So let's move on with more material。 Of course， I know you have an exam coming up。

On Wednesday and as stated in some posts， the exam only come up cover up through last Wednesday's lecture。

 so。Today's lecture will not be on the exam， but it might show up on a later exam。啊。

The topic today is we looked already at the issue of consistency in dealing with cash protocols。

 but we actually didn't look at the whole picture。And so the larger picture is what's called memory consistency。

And。嗯。It， it goes back to this question of if， if two programs are reading and writing to memory and they somehow are。

 the shared memory in there， what they should， what should they be able to observe about the reads and writes and。

 and having some consistent order among them。And so there's sort of an intuition that says， well。

 just， you want to grab the value that was mostly recently used to each memory location whenever you do a read。

 But that's not really a feasible definition。When you look across the memory hierarchy and you think about the fact that some operations can be performed in。

In a。A co cycle or less。 And some might take a few hundred cock cycles。

 So even the notion of time across a large system is not that tightly。

Scripted and it would be impractical to say that every right here must immediately be observable by a read in some other location。

嗯。嗯。So， again， you want to have a more relaxed model。 And it's a trade off。

 You can have one would be just total chaos。 to say， whatever。This processor reads this one write。

 might see it might not。嗯。But it would become horrendously difficult for software developers to design to vet standards。

 so。Almost every system provides some type of consistency model。

 but not maybe as clean and nice as as you as software developers might like。

 because in an effort to allow more performance， they've got come up with various relaxed consistency models。

 And that's what we'll talking about today。So let's think about what we mean by sort of some type of consistency model。

 So look at this program here。That the thread 0 is writing。V。

 all the even values to a shared variable X。 And thread1 is writing all the odd values。To。

 to a shared value X。 And then thread 2 is just。Repeatedly sampling what is x？And the question is。

 what values could ABC or some sequence observe。Of x。So。And which would be illegal combinations。

So what about 4，8， and then 1， Does that seem okay to people。So why does that seem okay。Yes。

But the two even numbers。Yes。So， you've already figured out the key idea that as long as the even numbers are in order and the odd numbers are in order。

Then pretty much any interle of those two is vin because we're not assuming anything about the relative performance of。

 of threads 0 and1， just that each of them is maintaining this consistency。

And so that kind of gives away the story。 So 9，12，3。Oop。

 there's a problem there that you can't have a three after a9。7，1931。 Well， that's fine。

 They're all odd and they're all in in order。So what comes out to that is that。For any given threads。

 rights， any observer， external observer must be able to see them。

In the order in which they were written in the program。And across threads。

There have to be some valid interleaving of the threads。呃。The sequential orders of those。

So that's sort of the classic idea ofency。 What we'll find is that's actually too strict a rule to get good performance。

 and we'll find various ways to， to even relax that。 But let's start with that。Idea and sort of。

hypoypothetical model that this is based on is imagine we had a。A memory that could only。

 it's a totally global memory。 There's no caches anywhere。

 and it sort of can each step do one operation。But it can choose across the threads are sort of all competing to have permission to do their one operation。

 And so this little。Dial thing is imagine it's， it's on each step。

 picking one of those memory operations to perform and then doing it to completion。 So。

 and so what you'd get out of that is this single port to memory would be sort of a serializer that fortss。

All the。All the across the threads to maintain some interweaving of each of the threads worth of rights。

 And we're assuming that each of the threads does its operation。In the program order。

So the only sort of flexibility we have is we're not trying to make any assumptions about the relative to performance of the different threads。

 We're just relying， requiring that they each are individually consistent。

So last time we looked at some of these consistency issues。

 but we're only looking at them with respect to a single cache line or or in general。

 all rights to a single shared variable。 Like the previous example was a shared value X。So， we。

We can all the work we are doing on these coherence protocols。

 We're guaranteeing that at least all the reads and write of。

 of some given lines worth of data in memory was always handled in some con sequentially consistent way。

But there's a bigger picture that we didn't even talk about it always。 Well。

 what about operations on， on different， completely distinct memory locations。

 Do they have any constraints among them。And what you'll find is if they don't。

 then you're gonna to have a really hard time writing programs。

 So there there even has to be some consistency across those。

 And that's a bigger picture we'll look at today。 the memory consistency model。And again， physically。

 in cash systems， it's。Handled at the， the scale of， of cache lines or blocks， but。

In sort of the principle， we want to think of these is just shared variables and not worry too much about the data type involved。

And so our intuition is， again， that there's this。This single port to memory。

 And so it doesn't matter whether reads the write or to a single location or to multiple locations。

We'd still have this sequential consistency model that it would。

But you'll see that this doesn't really， in practice because of the way hardware operates。

 the execution model these processors， They don't necessarily follow the exact program order in doing their reads and writes。

 And that can。Can mess things up with respect to the memory consistency。And so。

If your your mental model of a program is often that。You know， if you think of just running。

 a single program on a single processor， your mental model is that you do each。

Instruction in sequence。 And that defines the program。 But as we've discussed before。In reality。

 modern processors don't do everything in the exact order of the program。 They try to extract。

Innal parallelism out of your program and do out of order execution。

 including potentially out of order execution of， of memory operations。

So that's fine that there's a lot of hardware built into the processor to。

 to maintain the illusion of sequential execution， even when they're extracting parallelism。

But that hardware doesn't work across threads。 There can be distinct memory operations going on。

 not exactly in the same order。 even on a single processor。

 the actual read and write accesses might not follow the。What youd what you'd see from the program。

So let's see how that。What impact that can have？So we saw before that you think of it in。And。

Logically， that theres in a program。 there's first， if you had a write and then a read。

 one would follow the other。But， in fact， what happens is the。

Hardware will try to figure out ways it can start the read of。

 of B if it's independent of A before the right of A has completed。And it's totally possible。

 in fact， for the read of B to complete before the right of a is。

And so one of the techniques it's used。Is in a processor design is to build what's called a write buffer。

 So what happens is the processor just， when it says store this data to memory。

 it just sticks it in a queue that and then the hardware and including the cache logic and all that。

 is responsible for then eventually pushing those out into the memory system。

 but the processor can consider that right to be completed as soon as it sticks it in the buffer。

And then somewhat independently， it can be reading other locations。 And I say somewhat independently。

 as was mentioned before or has been mentioned before。

 There's actually a sort of a connection here that。Any read。

 it will sort of take a peek in the right buffer to see if there is a right。

 app pendingending right to that same memory location。 And if so， it will pull the。

 the value out of the buffer instead of actually reading from the cache。

 So there is a little bit of logic in there to make sure that。The read writes are consistent。

So for example， if this were a write to A and a read to A， it would。

 instead of reading from the cache， it would just pull the data right out of the right buffer。But。

The point is that you can have a queue of of rights here。

 stores that haven't even hit the memory system at all。 There's sort of no way the， the larger。

 all the snooping buses and all that stuff have any idea that there's pending rights to particular locations。

 question。Is this like。Another。卡多。No， rightic buffer is not a cash。It's a buffer。 It's sort of。啊。

The processor is just saying， I want to do the following updates。

 You memory system figure out how to do it。It you could think of it as a。

It's a bit of a cache in that it's。An a cache， though。

 is if you think about it is really just a redundant collection of， of recently， you know。

 the latest memory values。 This is more like a work cubit saying。Do this work for me。Okay。

Other questions？The main observation is this exists， and if you think about what it means。

 I can have reads。That like， if this read to B， if this right to A were taking a while。

 it were queued up here。I could have this read start and complete before the right actually ever is。

 is visible to the rest of the memory system。So you can see how very quickly。

The reads and writes that would be seen by the memory。System here might not be in program order。

And so in general， what happened。 And this is a technique used。To， to reduce the， the impact of。

 of misses or other long memory operations， question So。Processor looks。

Does it also look in the right upper？to make a right。Nope， it doesn't have to it。

 Just will queue it up in this。So if it can queue up several rights to the same location。In general。

 sometimes it will， you know， you can imagine more exotic logic that tries to do that。

Especially if it's multi。Multiple。Locations within the same cash block。

It might try to merge those together， but I don't。 It doesn't have to。

 And that's sort of beyond the scope of the discussion here。

We'll just assume that it just cues them and does them。In some order。

But not necessarily in the the PIO order here， because， again。

 we could have a right hit or a right miss。 and we want the。

We don't want to hold up all the rights because one of them happened to miss。So in general。

 this is used to hide the latency of expensive of cash misses and other things that slow down the memory。

So。As this example shows。We can't。Start the second operation until we've completed the first because of the data dependency。

But we could do the other two operations without waiting because they， they don't rely at all on。

On the， the values generated by the first two instructions。And so， as I mentioned。

 the result of this is the actual completion of。The memory operations can aren't necessarily handled in the same order as they appear in the program。

And even if you have branches， it's possible for the。Processor to use speculative execution。

 So it can get guess， for example， that。This comparison is going to be true and goes ahead and and starts performing the。

Work in the conditional， the conditional work。And you say， oh， wait。

 this could be tricky if this were a store operation and I did it speculatively。

 I could really mess things up Like I set some global flag to true。

 and there's other processors that are in a spin lock waiting for that。You have to。

 that could really mess things up。 So what they'll do is they'll stick it in the store buffer。

 but not let it go yet until the branch prediction logic has been confirmed。

 whether that was a correct one or not。 So the actual stores。

 things that update global state can't be done speculatively。 All you can do is change registers。

And other things that you can back up if， if you got it wrong。But it is possible。 and。

 and systems will do reads speculatively。嗯。And even if then that red value is never actually used。

that's one of the sources of the timing problems in this way to set attacks I'd heard about。

That you can force。By branchch mis predictiondiction， you can。Essentially， probe and。

 and learn information about memory locations。So again。

 the conditional just adds to the cases where the program order is not necessarily the memory operations don't proceed exactly the way they'd appear in the program。

So。I got these slides have all these cute animations。嗯。That， the point being that。

What will happen is in， in a sort of simplistic way that the instructions themselves are issued。

In the order of the program。嗯。Well they're， they're decoded and put into some type of reorder buffer that's internal to the processor。

 And then the processor will attempt to issue， meaning begin the execution of any instruction that's。

Enabled that， the data for it is available， but it will。

 so it can potentially issue them out of order。And then at the end， it will。呃。It will。Complete them。

 It will retire them in program order， making sure that any speculative branches were correctly handled and things like that。

 But the point being that these again， these memory operations can sort of hit the the memory system out of program order。

So here's an interesting analogy that I hadn't heard before， but I thought it's cute。

 is think of these。In structure these memory operations， almost like。

Things bouncing around inside of a， a skinny balloon。That they can move up and down。

A relative to each other out of program order。 And the only real control we have。

To make this to prevent this is to sort of put a twist in the balloon。

 to wall off essentially a fence or some type of a global synchronization that says。

 I have to complete all these memory operations before I begin this next set。

 So if you think of this balloon， it's like we can put a kink in it that says。

 we'll complete everything up through this point before we begin anything else。

 But otherwise the system can be sort of moving loads and stores past each other effectively in these strange ways。

And， and again， this especially even the the， the basic right buffer already sort of introduces this possibility。

And as I mentioned， it will read in the and that pulling things out of the right buffer， you can see。

 well。Really make it confusing for any kind of global memory ordering。So what does this mean， Well。

 imagine we had。A flag that we're using to synchronize data accesses。

 So processor 1 is updating value A， And then it's setting this flag to true。 And meanwhile。

 a processor 2 is doing a busy wait on that flag。And as soon as it's enabled。

 it will then think it can safely read A。 So that looks like a pretty classic。

Way of doing synchronization across two programs。But imagine now that we have this system where。

The relative orders of reads and writes。From coming from a single program are not necessarily in the same as the program ordered。

And this can happen again， due to the presence of right buffers。

 Or it can also happen if you think about these cash cohernce protocols where。

There's multiple steps between when a read and when it completes and same with a right。

So imagine that we had。This processor that has a copy of， of ready， It's spinning on it。

 and it sees it。 It' 0。 And then the processor that's updating a has its current value of。

 of one of 0。 Excus me。 And so it sets it to one。And it sort of sends off as a zigzagging line is sort of a a sequence of transactions that will eventually globally set the value of a to be  one。

But imagine the the the same operation type of operation that it does to set a to1。

 It also sets ready to one。 But for one reason or another， it goes through much quicker。

 Then this processor on the right might read and see that this ready signal is there。

Even though it doesn't have a。And then when it goes to read the value of A。

 it might not see the updated value of that。And。The。

 the presence of caches makes us even more likely。 So imagine that。嗯。Let's see。哦。I think this。

 I'm trying to think of。So， and this is actually， a more involved example， where there's a。没写。

A chain of dependencies。 So the one on the left is setting a to1。

 The one in the middle is waiting until a becomes 1 and then setting B to 0。

And then the one on the right is waiting till B becomes one， and then looking at a。

And you can see that the first one。Can launch setting A to B 1。嗯。嗯。And that will。

And and quickly triggered the middle one to say that， O， A is1。 But launching the update of a。呃。

Quer through what might go more scway。And。Then the B gets one is set by the middle one。

 and that goes to the second one。 but it still hasn't gotten the update of A。

 So if it attempts to read A， it'll still get a still value。

And the general point being of this example is。It's not even just a simple right here。 read there。

 It can be a sequence of writes and reads where due to the varying delays incurred and because of caching and。

 and other reasons， they。Even once it。Involvelving chain of dependencies going further back can still not get the correct value。

So。we， we've been talking about this idea， that sort of classical model of sequential consistency。

And the thing that it requires is based on the assumption that the access of each for each processor is in program order。

 But what we've already seen is that that's not even true for a modern processor because of write buffers and other other reasons。

嗯。And so as we saw with this example。啊。We， we'll sort of simplify it down。 We'll take away the。

The spinning on ready。 And just assume what possible values could processor  one read。

And what we'll see is that it should not be possible for。嗯。

For so we're looking at what possible values are there for X and Y。

 And so if we just do these in sequence， we'll set a to1， ready to1。

X will get one and y will get one。 So1，1 is certainly possible。 But the main claim is。

There's one combination that should not be possible， and that's one comma 0。

 So it shouldn't be possible for x to be set to one and H be set。To 0， which is its initial value。

 because that would mean that were not。 the reads being seen here are not respecting the program order of the rights being performed over here。

So呃。So this is going back to the sort of classic notions of。Sequential consistency。

 And the main point being that。ARe hardware， as we've seen。W。Without if there's no other steps taken。

 can very well perform create this inconsistent value。

And this is a similar example from a commonly used protocol for doing mutual exclusion。

Where you sort of， it's known that there's only two。

Processes that are attempting to implement mutual exclusion。

And so they can each have a flag that they've signaled each other whether they want this access。

And you can see that they have a similar sort of crisscross pattern that there's a write on one side and a read。

On the other。 And， but to two different locations。 And so it's possible to。嗯。Look at the values。

 then of x and y。And again， what， what should happen is you can't get the value of 0，0。

 It's not possible to。For。Both processor 0 and processor1 to get the initial values。Of these two。

 because one or both of them has to have have done a right to。B啊。To the other side。Right。

 this is pretty standard。So again， the case zero，0 should not be possible here。So how could we。

 you can imagine， see， if， if I can't assume any kind of sequential consistency。

 how am I gonna even write mutual exclusion， How will I even implement the most basic synchronization primitives。

If。If I have no guarantees at all about this consistency。Well。

 one way would be if we forced the each processor to only have one outstanding memory operation at a time。

 either a load or a store， then。We could。 We could。

 And then we had one of these cash protocols that took care of the。Acceses to a single location。

Then we'd be good， because。Each basically， it would force each processor to perform its memory operations in。

 in its program order。嗯。And， and we could， we don't even have to be quite that draconian about it。

 We can for say itll wait。For， for a memory operation in， it。

 it views the previous one as having completed。And what does it mean to complete means it has to have hit some part of the memory system where it's guaranteed to then be carried through。

So it's not good enough to stick it in a right buffer。

 It has to have sort of gotten engaged in the whole cash protocol and begun invalidating what our lines are necessary to make that happen。

 So it's often called the point of commitment where this right operation is really going to happen。

So you can think of it as a read is done once some value is。

 is determined where that what the writer of that value will be。

 whether it's coming from memory or from some of their cache。

Then that's enough call operation completed。And so way to write is completed as soon as the it's been determined。

That this right is going to be carried through into the。好。So it doesn't mean that， that the right。

The read doesn't have to have actually gotten its value back。

 and the right doesn't have to have actually updated， say， main memory or even any particular cache。

 It just has to have hit far enough into the protocol that we're sure this will， will take place。

 We've， we've sort of serialized its ordering。嗯。And so that's sometimes。

A way of implementing the classic sequential consistency， even in， in these multiproces systems。

But weve seen that that's actually a pretty harsh rule。

 It means it we'll have to really penalize our performance with respect to things like right。So。

 but we'll say that for any possible。A processor operation。Will maintain the。呃。

Will constrain each memory operation to follow the previous one in a， in a serial fashion。

So you can think of it as going back to this balloon analogy。

 It's like putting a little twist in the balloon。Between each of these memory operations， again。

 there could be some other stuff going on that involves just registers or something local。

 but we we put a twist that says before you can begin another read operation。

 you have to have completed or gotten the current one far enough along that it's guaranteed to complete。

嗯。But this is is kind of not a great idea in terms of performance。 And， in fact。

 here's results from a paper。Fair old paper that show taking some benchmarks， some sort of standard。

Parallel benchmarks， one of which is the L U that。We've shown before， and it shows how the。

 how the time spent by the memory system。嗯。We split over， over across the whole。

Ex of a program and you see the。Where it's actually doing useful memory operations。

The black is synchronization traffic。The red is where it's stalled， waiting to read。

And the green is where it's stalled， waiting to write。And so what you see is that the。啊。

Performance is that you're really spending a lot of time held up waiting to complete reads and writes due to this。

Time spent by the synchronization。By this put enforcing this order。So。One possibility then。

 is to sort of relax which ones we。We assume， can。呃。Can avoid this need for， for pure sequencing。

And the simplest one is called total store ordering。 So that what it means is that。We're allowed to。

Basically， started right。start a read， even though we haven't completed a previous write。

 And if you think， this is what somebody who builds store buffers for a living wants to have， right。

Because it lets you stick a right result in a store buffer。And begin the next operation。

 say it's a read。Without having to worry about waiting till it flushes out of the store buffer。

Whereas these other ones aren't quite so scary。呃。You could enforce an ordering of reads。

 You don't have a buffer there， and you could enforce the rule that you have to finish a read before you begin a write。

Meaning that you。嗯。Don't put things in the store buffer until you've completed a previous read operation。

And some， the right can go by right if you just use a Q， a 50 Q for the store b。

So that's sort of you can imagine a hardware designer saying， oh。

 I could give you this without too much challenge to me And in fact。

 that's basically what Intel provides。 You can look it up as this reference。

 but they'll talk about the rules and it's more complicated than this。

And others have come up with even more relaxed models。 And so what's called a partial store ordering。

Is basically， there's no constraint after right happens。 You could have。

 So what this allows on the right hand side is that the store buffer doesn't have to be a fiIO。

 It could be any kind of you can complete rights in any order that you you want。And so the same。

Performance measurements on looking at a sequential consistency versus total store ordering。

 you could see for these benchmarks that。You greatly reduce the amount of time spent stalling for rights because you've been able to dump the rights into buffers and forget about them。

ForFor these benchmarks。 So you can see that the time spent waiting for rights has reduced quite a bit using this total store ordering rule。

But now let's think about it。 that， that's sort of the， the hardware perspective of， oh， wow。

 I can make you some nice hardware if you'll give me this rule。 But what does it imply for the。

The people that are trying to actually implement software that will do this sort of common operations。

And。So first of all， the observation is。Actually， we don't care what order a lot of stuff takes place in。

So for example， if this program updates two values， A and B， we don't really。Care。

 whether A is updated before B or B is updated before A， that really doesn't matter at all。

And similarly， down here。We really don't care what order these two reads take place in if they're reading。

If they're reading different memory locations。 So putting some really strict policy in place for every single read and write。

Could be very inefficient performance and really completely unnecessary in terms of what programmers really need。

What counts， though， is。I want to be able to say that if I unlock a lock。

So if this process is updating some global data and then releasing unlock Lock。

And then some other processes acquiring that lock。You want， in the meantime。

 any operation that has been complete， any rights that have been completed by process 1。To have。啊。

Taken place so that when I do these reads， I will see these values written。

 So that that's the main point is this observation that what really counts is making sure before you unlock something that the rights have taken place and making sure when you acquire a lock that all the pending。

啊。That you'll get the values that are consistent with。

And so what this shows is if I can just sort of put a hypothetical barrier of sort of synchronization at this point in the program。

 in the two programs。Then， I will。Then it really doesn't matter what other ordering that。

The execution。And so what we'll say is that。嗯。What counts then is if I have a。A memory location。

That I'm writing in some ways and reading in another。

ThatThere's potentially a dependency between those。

And I want to have a an ordering if theres one of these is sort of global values that is。

Then I want to carry from， from one place to another。 I want to make sure that。

That that the relation between this right and this right maintain program order。

And this read and this read maintain program order。And that there is a dependence order。

Across these two threads of this single value。But remember this。呃。あの。This， this is the。

 the read of a single value， which we， we maintain with our。 So what really comes。

We guarantee that these two program order dependency are。And if you think about it in。

 in certain more general terms。What so one way to think about it is then a typical program will involve sort of accessing some data and then some type of synchronization operation。

 either acquiring a lock or releasing a lock and then some kind of reads and writes and some kind of synchronization。

And so。Let's see if we can't take advantage and we don't really care within。

Between these synchronization operations， the relative ordering of reads and writes。

We're assuming that we're either operating on private， unshared data or if it's global data。

 it's data for which we have a lock。 and therefore we should have exclusive access。So really。

 it says that we can really focus on the synchronization operations。And also。

 the relation between the program operations。As they come either before or right after it synchronization up。

And， and this is just， you know， a practical statement。 In reality， of course。

 we're assuming it's a shared memory system。 And so。Even if， if。

It's perfectly possible for other threads to be examining and altering。啊。Me locations globally。

 and we don't have， we're not assuming that we're， we're you know， enforcing anything like that。

 We're just assuming that the program is written correctly。

to use some kind of correct synchronization so that if there's some global state。

 it won't modify it unless it has appropriate lock for it。

So an example of synchronization would be gra a lot。And， and let's say in the middle。

 we have a lock and， and we want to modify some global data structure。 So up to now。

 we've done some computing。 figure out what we want to do。We grab the log， we make the update。

 release the lock。And now any further operations。IShould be able to see that any update we've made to this global day。

And keep in mind， sometimes， too， it's a little bit trickier that usually there's a rule。

 if you want to modify a global data structure， you have to have right access to it。

 But sometimes we allow programs to read， have read only access to shared data。 So， for example。

 you know， if theres some。count。Then， in。Anyone who updates has to have a proper lock to do that or do it as an atomic operation。

 but will allow anyone to read it at any time。 So that's fairly common。

 So it's a little important to distinguish。That what assumptions we make about global operation。

 you know， global values， whether we're writing them or reading them， it's different。嗯。So again。

 we can think that in here where it's a purely private， we could do reads and writes in any order。

Even within this critical section。We might assume that。That we have。

 We're the only ones that are supposed to be modifying things。

 So we don't have to worry too much about the ordering of those。

And then but by once we release the log， then it means that all the updates that should have been performed in this critical section must really be done。

And so what we want out of this is given a properly written program。

 it will have the same consistency as youd get through the sequential consistency model。

Even if the hardware itself does not fully support sequential consistency。

 because what we'll do is we'll make sure our synchronization operations are implemented correctly and we'll have some more relaxed consistency。

 the actual hardware。And so this is sometimes called a weak ordering。

 something where we allow a weaker ordering than the sequential consistency。

 But we assume that's linked with a properly written program question。

This model why do we still need to worry about read， read？こいっぱい。Assume that between cigaretterons。嗯。

Let's see you said read， read。Oh on the the TSO and so forth。

 you mean like under this model you allowed to shle。Yeah， I think the problem， like you asked。

 what about read， read consistency？Its still， what gets trickier on the reads is， like I said。

 it's possible。Although， as you know， you have to be really careful with this that you'll have other observers of read only observers of shared data。

 And that's generally allowed in， in synchronized programs。

 So you have to go a little more more deeply into。What do you assume about the ordering that that would be done on。

Shared data for， for read access。It gets a little trickier。So， for example。

 Intel provides an operation called M fence。 And all it says is that。All the prior reads and writes。

Have to it basically puts a barrier in。 it says any reader right that was pending up to this point must have been。

AComp。And I won't start any new operations until after it's reached this fence。So logically。

 it's like putting a twist in the blue。 It's sort of saying it。 And again。

It's not the case that it means that。The the final right must have occurred。

 It just means it has gotten far enough along in the protocol to be able to guarantee that it's done。

And so that's an intel operation， by the way， arm processors， which I don't know very well。

Have a much more relaxed memory consistency model， and。

It's a known fact that trying to program to these things is much more difficult。

 but potentially they have the in the interest of greater performance out of that。

There's a lot of literature about this huge amount。嗯。So the。

 the one point about this evidence is it doesn't really。Have to wait until everything is done。

 What it does is basically it， it will stall the thread。And once it hits this M fence。

 it will basically stall it until its right buffer is empty。So that。

Any pending right from that has sort of gotten into the cash system far enough along that it's begun the whole protocol on that instead of just staying there invisible and local to this particular process。

And and so that's all it does is it's not actually synchronizing with any other processor。

 It's just internal to the processor itself， sort of holding up a thread until it's sure that the memory it's going to be accessing that those have gotten suitably performed。

And so what this effect is is again， think of this。ATwist in this balloon。

 it sets effectively a barrier that guarantees that。

Although these memory operations might get reordered and these might get reordered。

 there won't be any reordering across them。And so that's enough to kind of。

I giveive you some handle on memory consistency。So let's try it in practice。

 let's figure out where we need to put fences。In order to make this program behave reasonably。

Meaning that。い？The possibilities are that processor 0 is successful in updating A。

And that will be seen by process  one， or process  one will zip through before process 0 has a chance to update a。

 So， but what we don't want is it for to。X to get set to1 and y to be set to 0。

So what if we put an M fence here， would that do us any good？What a。Yeah， we haven't done anything。

 so we're not going to stall。 We haven't had any real impact。Similarly， what about？Down here。

 what if we put a fence right there， Would that do us any good。It's the same argument。 By this point。

 it's too late。 We haven't actually。嗯。At this point' our program doesn't have any more operations to complete。

 so that wouldn't have any effect。So it would seem to indicate it might be a good idea to put a fence in there。

 is that people think that might be a good idea， yes。So that ensures。one。For。Ready use story。Yes。

 good。 So it would， it would guarantee that。

![](img/3f784d06efe71a31d76a58448c966439_1.png)

Basically， it forced these two to occur in program order， right， which is a good thing。And similarly。

 you can come up with same arguments over here。 It really isn't going to。

Do me any good to put a fence in here。Because I haven't done anything yet。

 So there's nothing to stall for。 And there's no point in putting a fence in there。

 because I'll just。I wasn't planninging to do any more memory operations。 So remember， a fence。

 whoops is。Jump on me， but you can see the punch wine anywhere。But here， similarly。

It's not ideal way to point。You could see that by putting a fence here。

 it again guarantees that these two reads occur in program order。



![](img/3f784d06efe71a31d76a58448c966439_3.png)

And so that comes up with this answer here。And if you think about it， what if I took away。

eitherither of these fences， could I get into trouble。So what if I took out this fence？

What could happen。Yeah， so now even though I'm forcing these reads to go in program order。

 But the fact they're going out of order here potentially means I'd still be messed up。

And vice versa， so you need both of these fences。To， to guarantee this will work。

But the point is that the fence is purely， it's not a global synchronization。

 It's not saying to everybody， hey， let's all agree that we should synchronize to this point。

 It's a local operation that just guarantees。Enforces program order。啊。Sort of for everything before。

 relative to everything after。And this can get even more exotic if you think about it。嗯。

So basically what。What you do with fences is and is similar to what we've just done is that you force。

You put a fence before you acquire a lock。To make sure that all the rights that this is performed have been completed。

And when you go to release a lock。You put a fence in there to make sure that all the updates here have taken place。

But that， that's actually a bit more conservative than you need。In the。If you think about it。

These are all private updates of some private data structure and so there's some rights there。

And these are all。Reads that should be private or local now。And。So what we really require is that。嗯。

And remember， we'll maintain program order。At least each of the， the， the。

 the programs that are running will think they're running in order。

 even if the memory operations go out of order because of the whole out of order execution model。

So what comes about-， and it takes a little while to think about this is you can sort of split this logically。

To and distinguish between a locker and you're acquiring a permission and release where you're releasing and giving permission to others。

 And so if each thread just maintains this。呃。These dependencies that before you。Unlock a lock。

Then all the rights that were done by this thread either。Before or after it got the walker completed。

And similarly， before you。呃。Aquiir lock。嗯。Before you do any reads， either。

Within this section or here， you make sure that you've acquired the necessary walk。

Then that that's actually enough。 So you can actually distinguish between。嗯。You know。

 what type of operation is being performed？ And so in particular。Withtel， besides M fence。

 they have operations， ones called L fence。Which is like an M fence。

 except it only is with respect to load operations。An S fence， which is like M fence。

 except it's only respect to store operations。And。So that， that gets even more nuanced。

 It practice what happens。 First of all， most of the stuff is usually built into library code。

 It's not something you， as a normal programmer， have to deal with。

So there's an instruction that Intel provides called exchange。 And we'll see some examples of that。

 It's like a ability to do an atomic swap。Of some data you're holding locally with some global value so that you can both update the global value and look at what the global value was before。

 So it does is sort of swap to memory location contents atomically and that operation is guaranteed to also provide a so that the。

Before a full fence， like it's equivalent to also doing an M fence as part of that operation。

So most of the time you'll just see code that uses exchange。

Rather than using these having to use these fence operations。But if you think about it here。

 we could。If we wanted to be trickier， we could use a store fence here。

 because all we're really requiring is that。These two rights occur in program order。And similarly。

 an elephant fence here， we just want to guarantee that these two reads occur in program order。

So it's interesting if you go back and look at sort of classic mutual exclusion protocols。

 like this is called Peterson's method。And it's a simple。

A way of doing synchronization between two processes。

 you're doing mutual exclusion protocol where you know there's only two processes that want to be mutually exclusive with one another。

But on any given step， it may be that only one of them wants it。

 So what it's doing is basically alternating back and forth between the two， giving them priority。

 but saying， but even if you have priority， if you don't want it and the other one does。

 then I'll give the resource to that。 So you see that there's a shared。Basically。

3 bits of state to do it。 a flag for each one， whether it wants access。And a turn saying。

 whose turn it is？And basically， the protocol goes something like this that you。嗯。If you want the。

If you want it。But you'll say， but I'm going to give the other side its turn if it would like it。

And then be in a busy loop that says。As long as the other side wants it。And has the turn。

 then I'm just going to wait。And。And then once I get through that。

 I'll be able to do the critical section， and then I'll release it by setting my own want flag to false。

So you can see that this is a complete mess with。These relaxed consistency order， right。

 If we can't make any assumptions about the relative timings of the the rights。

To these three variables。Then this protocol is just not going to work。

 And so you can insert enough fences in there to make it work， but it's a lot of work。

So here's a simpler version making use of this exchange instruction， you say。嗯。

When you want the lock， you just say。If， if the。然后。I'll do it a busy loop， So I'll say。

Set the lock available flag to0。And tell me what the previous value of lock available was。

And if it were zero。Then I'll say， whoops， I'm not allowed to proceed。But if it were one。

 that meant the lock was available。 and I've just grabbed it。 And because it's an atomic exchange。

 it's not possible for the other process to jumped in the middle and seen and also tried to grab the lock。

So by making that an atomic operation， then that that's good enough。 And then。

Critical section is you just assign。A one to this value。 you can do it。 And normally。

 you just say assign lock available to one。 But by putting this as an exchange， remember。

 the exchange also implements a fence。And so it guarantees that it will preserve the ordering rules that we want for the system as well。

So that's the kind of thing that people usually use for code。好。

So my point here is that the exchange is only operating on a single value。But。

By putting having this fence， it means whatever updates were made in the critical section will be completed。

Before some other process is able to grab the lock。 right。

 So it's sort of serving the purpose of both synchronizing。

But also making putting these fence operations in to make sure that the。

 the memory has been updated appropriately。Yeah。ここすみねよ。The what。What's meaning。哦 channel嗯。Turn is。

Allowing。I actually nested up this。Tweed this code， and let me make sure I got it right。He， now is。

I'm not I'd have to double check this code to convince myself it's right。 But the idea of it is。

And you can look at in Wikipedia， if you look at Peterson's mutual exclusion algorithm。

 It's some variant of this， but not quite this。 The idea is to provide a fair protocol， so that。

You keep changing the priority。 whether， if both of them want it at the same time。

The idea is to make sure that you won't always give it to process through0 sort of strict alternation。

That's the idea of it。 whether this code actually achieves that， I'm not sure。

But the bigger picture with respect to the topic of the lecture is。

This protocol is you'd have to do a lot of work and put a lot of fences in to make sure that it really is。

gonna do what want to do。Sorry about that。And the， the point being that this exchange operation。

Which you can get as an GCC extension will give you access to this。

InInstruction also provides a fence behavior。 and so it sort of you don't need any extra fences inserted here。

So just to wrap up then the point being， if we， we could。

 in hardware enforce pure classic sequential consistency。

 but it would really penalize the memory system quite a bit。 And what we've seen is that。

A lot of operations on memory were perfectly fine。 A lot of them are just to private data structures。

 Or if they're to global data structures， we can assume that the program was written in a way that puts the necessary locking mechanism on it。

 So given all that。Why sort of make the hardware run slower so。

There's sort of a trade off that you can give more and more hardware performance。

But giving a weaker and weaker memory consistency model。 But at some point。

 it becomes so so hard to fathom that the software designers go crazy。

 And there's always that tension between the hardware people and the software people。

And we've seen that in in other places， too， that。The hardware people want to take away things。

 make it more relaxed。And then they can run it faster。 And the software people go， wait， no， sorry。

This is， I， you know， I can't begin to debug this software and make it run correctly if you don't give me something。

And so the good news， and of course， that you saw already， this will vary from an arm processor to。

Intel processor to other brands。 They'll have different models。

 different consistency models and rules。 And so usually。These are embedded in libraries。

 and it's part of the reason why it's usually best practice to。啊。To， you know。

 make use of a library rather than to try and cook up your own synchronization code because you just run the risk of。

Of it ran fine on all the intel processors I tried。 And then you try to map it to arm。

 And all of a sudden， boom。 The thing doesn't work right。

 So it just brings home that the importance of。Sort of being disciplined in your programming and make use of libraries for anything tricky like this。

Okay， that's all I got for today， then。

![](img/3f784d06efe71a31d76a58448c966439_5.png)