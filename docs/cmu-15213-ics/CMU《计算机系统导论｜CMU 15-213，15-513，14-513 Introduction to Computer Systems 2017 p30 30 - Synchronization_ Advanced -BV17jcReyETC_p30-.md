# CMU《计算机系统导论｜CMU 15-213，15-513，14-513 Introduction to Computer Systems 2017 p30 30 - Synchronization_ Advanced -BV17jcReyETC_p30-

たち。

![](img/a630629c8629ff7d004f5e0896d826c6_1.png)

![](img/a630629c8629ff7d004f5e0896d826c6_2.png)

![](img/a630629c8629ff7d004f5e0896d826c6_3.png)

Welcome to probably what would be the lowest attendance class for the term。嗯。

And I think you'll find the material and that's pretty useful for proxy labb。

 so hopefully other people will watch it。The recording。嗯。So last time we introduced synchronization。

 the use of primitives in particular semaphos to control the sequencing of events between multiple threads as a way to get some structure so they don't all just race ahead and do bad things and what we'll do today is just continue that discussion with a little bit more sophisticated use of semaphores and other applications。

So。You recall then that this idea of a semaphore， which was introduced by a Dutch computer scientist named Edsgar Dyictra many years ago。

 is that you have a special variable called a semapho that's guaranteed to always be greater than or equal to zero and there's two operations on it。

 one that's called P and the other is called V or sometimes it's called weight and signal。

 so P means I want to。Io。Wait until this variable is not in zero and then decrement it。

And V just means increment the variable， but a key part of this is。That first of all。

 there is this atimity guarantee that everything in the square brackets there is done without any other thread being able to jump in and do anything。

 So when the P operation exits that while loop。It's absolutely guaranteed that S will still be zero S will be non zero。

 excuse me。And similarly， the increment you saw before。

 it's possible to have a single increment operation get thrown off by other increments going on。

 this one's guaranteed to work。The other thing is that that code that's shown here for P。

Is what's known as busy。嗯。Busy waiting code。So work。I to。



![](img/a630629c8629ff7d004f5e0896d826c6_5.png)

No。Fs with these settings events。

![](img/a630629c8629ff7d004f5e0896d826c6_7.png)

![](img/a630629c8629ff7d004f5e0896d826c6_8.png)

Sorry， I am。Clean nuts here。あ返し。So that code in that while loop is what's called busy waiting。

Or anytime that you have code that well actually it isn't because it has that call to wait。

 but anytime there's a loop like that it implies that the thing's just sitting there doing nothing useful。

 in fact with a real semaphore these are implemented as part of the scheduler and what will happen is if a thread's running it tries to execute a P and the semaphore is zero then the scheduler just yank that thread off the core and schedule something else in its place and then when the signal comes along it can check and say。

 oh what other threads are waiting for the semaphore and it will choose one of them and let it proceed。

So it has a cost， but it's reasonably efficient。And so we showed before the idea of using this in the most elementary form is for mutual exclusion that we want to prevent often what's called a critical section。

 some region of code that we don't want multiple threads executing at once。

 and often there's some shared data structure like we're manipulating a queue a list or something like that where we want to make sure that all the updating of it is done without any other threads coming in and messing things up。

And we showed that in the simplest form is just trying to increment a counter， which you recall。

 involves reading something from memory， incrementing it within a register。

 and then storing that back out， we want that whole sequence to occur what's calledatomically without interruption by another threat。

And so this is the idea of a mutex， and what we'll do today is show other uses of semaphos。

 so the same basic primitive but used in other ways。嗯。And one of the ways。Is to well。

 we'll show it in two day ways。 One is what's known as a producer consumer。

 where we have some code that generates a value and some other code that consumes that value。

 and we want to coordinate their actions so that the。

Consumer waits until the producer is producing something。

And so that's typically often looks something like the code here that there's some shared buffer or data structure that the producer will generate values for。

 and then it will let the consumer。Proceed and make use of those and so as example would be。

Something like a video application where the producer is the camera。

And the consumer is the image processing software。 So you want to the camera you want to。啊。

Well actually it's not perfect because typically a camera will just generate frames at some fixed straight。

 but imagine a more asynchronous version of that。You want the consumer to wait until there's a frame to process。

 so there has to be a signal from the producer to consumer that there's a frame available。

 the other direction can also hold that you want the producer to wait until the consumer has completed its operation before filling up the buffer with a new value。

And that's the style that we'll look at is where we have we want to coordinate in both directions。

 we don't want either the consumer or the producer to get ahead。

And so the way we'll do this is to use two different semaphos for each。One to represent。

Is this buffer filled or not and the other is it empty or not？And。

So the state obviously and this is just a one place buffer so we the semaphore will either be zero or one。

 so when the buffer is really empty， then the full semaphore will be zero。

 the empty will be one and vice versa when the buffer is filled。So this is what the code looks like。

 this is just getting it started。And。So we want to。嗯。

Initnitiallyize it so the buffer starts out empty， so we'll set the semapho initially the empty one is one and the full one is zero。

And then we'll fire off some threads， one for a producer and one for a consumer thread。

And then the main thread will just wait until those are completed。And meanwhile， the producer。呃。Well。

And it's an interesting pattern here。 You'll see that the producer will use the P operation。

To wait until the buffer is is empty， so it will wait until。This value empty is set to one。

 and then it will be allowed to proceed， and then it will fill the buffer。

 and then it will signal the full， meaning it will say， okay， now there's something in the buffer。

 and then the。嗯。Consumer does the inverse that it waits until it's full and then signals that it's empty。

 So you see， whereas before with the mutex， there was a。The same muttex， we are first。

Calling P on it and then V so we are waiting here we've got this sort of first of all。

 there's two of them and they're alternating back and forth and which one is。Where。

One of the threads is peeing one and ving the other and then vice versa。

 so it's an interesting pattern。If you looked at this code more carefully。

 you'd realize that you don't for just a single producer and consumer。

 you don't really need anything this fancy， in fact， it would work。

With you could implement it with just a single semapho。

 but this code actually generalizes also to the case where you can have any number of producers and any number of consumers and their。

So in effect， the producers are all competing with each other of who gets to stuff something in this buffer。

 and then the consumers are all competing against each other of who gets to yank it out。

 but the code will work even with that extension without any changes from what's shown there。

This empty semipho will。Guard basically formed the competition between the producers。

And the consumers will compete with each other for this full semaphore。

And then this can be generalized to a end place buffer。

 so the previous one was just a one place buffer。And。So there's all this code for it。

 but the idea is actually just the same， the main difference is now our semaphore where before it was either zero or1 will vary between zero and n and so the semaphore will serve not only as the semaphoes will not only serve as the sort of gateway。

 but they'll also keep track of how many elements are in the buffer。And so the code for this。

 and I believe it's in the book as well， and all this code by the way， is on the class webage。

 uses what's called a circular buffer。So a circular buffer is a handy way if you want to use an array to implement either a FiIFO or a stack。

a buffer that can support PIFO ordering that you just as normal use the array to hold the elements。

 but when you start inserting， when you start removing。

 you start taking them out say from the left side and then the filling can then wrap around and start filling back in so at any given time。

 the valid buffer positions。Will be as shown here in some blue。With these blue squares that。嗯。

Let's see， it's shown here with a funny numbering because it turns out to be useful here。

So let's just look at the term front。Refers to the index， the next element to remove。

 and rear is the index of the most recently inserted element。So front here is the value。I that great。

It doesn't seem consistent with the picture， does it？Oh， remove minus1 mod then， yes， thank you。So。

 read the whole sentence。So in particular， front here， if I subtract one from it。嗯。

I'm still in trouble， right？So I don't think the。Description is consistent with this picture。

 but the general idea you'll see is that。And I don't remember why I think I drew this。

Why the strange numbering scheme？But the idea of it is to。At any given time。

 then there'll be some range of valid entries， but because of this wraparound property。

 it can wrap around over the ends of the array。And the code is right。

 it's just something about the description isn't quite right here。And so here's the code。And again。

 this has nothing to do with semaphos， this is or synchronization。

 this is just a data structure and some code， so at some level let's just believe it's correct。

And it is in the directory and at work， so I assume it's correct。

 so the idea is that we're doing some mod computation。

 incrementing both the rear when we insert and the front when we remove。

And so what we'll do actually is use three semaphos。

 one is a mutual exclusion that lets us make calls to these。

Qe routines and not have to worry about the fact that here we're doing an increment and then we're making use of that value and if in the meantime some other code jumped in and said increment this value as well we have this nasty race condition condition so we're going to all these things will be called we'll excuse I assume there's some sort of mutex there that keeps them from。

Executing simultaneously。And that's pretty typical that you throw a mutex。

 you have one any kind of data structure where there's this sort of moment of inconsistency of the data structure。

 you just put a muttex around that to keep other threads from trying to make use of these partially updated information。

And then we'll actually have two sephos， just like before we had full and empty now。

There'll be counter， so slots will count how many empty slots there are available slots。

And items will count how many full swas there are in the buffer。So。And this is。

The code it initializes， and here's the ones that really count for inserting then。Again。

 we'll use the。We'll wait until theres some at least one slot available， remember of slots。

If it's a non zero， then it will be allowed to proceed。And then so now we're allowed to go。

 and so we'll grab the mutual exclusion， we'll do the appropriate update on the buffer。

 and then we will release the mutual exclusion， and then we'll signal that there's an item available。

So a question for you， what if I swap the order of these two calls to the P operation？Yes。给他的。

You walked me about further。But then there's not an available slot。え解すめ。Exactly， thank you。

 That's a perfect description。 So you'd have a potential for deadlock that imagine。I grab the muttex。

 That means nobody can touch this buffer now。But there's no slots available。

 so I hang up waiting and then meanwhile there's a producer somewhere that wants to put something in that buffer。

 but it also it has to grab this muttex and it can't because it isn't available so a very critical point to make on this is the order of operations in threaded code is extremely important and unned sequential code where you have a lot of flexibility to change things。

 obviously not total flexibility， but in threaded code it's aligned by line。

 you have to stare at it and examine it and convince you it's okay and particularly the acquisition of locks or any of these synchronization operations。

But this is a pretty standard pattern， then we wait until we're allowed to proceed。

 proceeding involves grabbing a mutex。Updating some data structures， releasing the Mutex。

 and then saying， okay， I'm done。And the the remove is just sort of the inverse of it that this time I'll wait for at least one item to be available and again I'll grab the muttex。

 update the data structure， release the muttex and then signal that there's。

There's at least one thought available。So you can see that this is really just a small generalization from the single place buffer to give you an end place buffer。

Like I said， there's code in the directory you can try it out I won't try and do demonstrations so now let me move so that's actually a pretty common one and you'll find that useful in a lot of places another one that's sort of a generalization of this idea is sometimes called the reader's writers's problem actually readers' writers is more of a generalization of a muttex。

So imagine there's some database， let's use an example where maintaining the set of available seats on an airplane。

 just one airplane。They're all economy class， we don't have to worry about that。

But you also have a lot of people who might want to be looking and sort of scouting around and seeing what seats are available for points。

 and we'll assume that the people looking around and just checking things out。

Aren't really too fussy about the exact number， they just want a general idea。

So you could just put a pure muttex around this， but it would mean that all these people who are looking。

Would。谢 of。Only one could be looking at a time， and that's sort of a waste because they're just looking。

 they're not actually changing anything and so。It would be perfectly acceptable to have multiple lookers at the same time。

Without because they're not going to change any of the values of this data structure。

On the other hand， we'll assume that writers， you want to keep those mutual exclusive so that there can only be one writer at any given time and will also enforce the stricter requirement that。

In fact， that while somebody's reading， they're not going to get something change out under them。

 they'll get a consistent picture of the whole system。

 so we want to say at any given time there's at most one writer。啊。And no readers。

 either that or there's no writers and an arbitrary number of readers。

And so this is actually a pretty common。 in fact， it will be a useful idea for the cash that you're supposed to implement as part of your proxy server。

So for example， we could have the version at the top where there's a single writer and that writer will then lock out everyone else。

Or the other case where we can have several readers， and they can all exist simultaneously。

 but then there can't be any writers。So there's been various published solutions to this and in fact。

 there was this whole sequences a long time ago of people publishing solutions to this problem with claiming that their version was Correct or better than the previously published solutions。

 and it was this long Cha of eventss， essentially in letters to the editor in this publication called Communications at the ACM。

So we'll just show a couple versions of these one is sometimes called the first version。

And what it says is that。呃。That I'll maintain then a pool of readers and as more readers come along。

 if basically the system won be theyre in reading mode or writing mode and in reading mode。

 as new readers come along， I'll just add them to the collection。And then if a writer comes along。

 the writer will have to wait until all the readers have left。And so there's zero readers。

 and then a writer will be allowed to go。So you can see there's a problem potential for sometimes fairness or starvation we said it。

 that you could imagine that there's a reader there for a while。And a writer comes along。

The first reader waves are the first reader is still there， and a second reader comes in。

 even after this right request has happened。And the first reader waves and then a third reader comes and the second reader waves and so forth that as long as there's some reader in the system。

 they can kind of indefinitely stall any writing。And then there's another version of it that's sort of the counterpart to that。

 I'm only going to allow a single writer， but basically if a new writer has arrived。

 then I'll hand the walk to that thread rather than allowing some waiting readers to go in so that's sometimes called the second。

 and then obviously there should be a third way which is somehow to make sure neither of these bad cases happen。

 but we'll look at the first code， the first code is by far the simplest。

So this is the one that favors the readers and you'll see that it's pretty simple there's two sephos one is。

A mutual exclusion one。And the other is a lock that is required。呃。

For either a single writer or for a pool of readers。And so we'll call it W。

 even that's not a perfect name。 And you'll see that let's look at the writer code first。

 It's very simple。 It just has to。Grab this right lock， do the writing and then release it。

 so the right lock for the writer is just a pure mutual exclusion and it doesn't even have to use this mutex variable you'll see。

On the other hand， the reader is。Going to use the mutual exclusion。

 So the mutex is more to block out other readers while those various values are being updated rather than to block out the writer So the。

Let I get rid of this。No。Reader then will grab the muttex and increment the count。

And here's a really interesting part of the code。Let's if this works。 No， no，'m sorry。It'll say。

 if I'm the first reader in because I've just incremented read count from zero。

 then on behalf of all readers。On me and all future readers， I'm going to grab this right lock。

 so I'll prevent any writer from getting in。And then it will then release some mutts。

 and that will allow more readers to come in， but writers will be blocked out because this variable W is being held sort of on behalf of all readers。

 even when this reader completes，You'll see that it will when the reader completes。

 if in the meantime， other readers have come in。Then it won't release the value W W only gets released by basically the last reader to exit will sort of close the door behind it。

 will release the right lock。So it's a very simple code。

 but you can see how it has this potential for this starvation。 So let me just show you an example。

 imagine。We have a sequence of events where first there's a reader and another reader and then a writer and a third reader。

 and so what will happen is the first reader will just slide right in and start reading and meanwhile I' have grabbed this right walk。

And the second reader will be able to jump right in too。

But now the writer will get stuck with the right lock。And now， even if。The first readerer waves。呃。

As long as there's at least one reader in the system。

 thenll the collection of readers will hold this walk indefinitely， so it will。Bk out that writer。

So you can see that this code will work， but it does have this not very desirable property。

Does that make sense to people？Yes， isn't that what you want for all the readers who finished reading？

Yeah， but you don't necessarily want。You know， imagine this is a。Like a store。

 this is what it's like if you've ever。呃。I've beenen at an airport where they had one counter and the people with priority status always get to jump the line。

Right。😊，It's the same field， right that I could have been waiting here for an hour。

 but as long as at least one person keeps showing up at this priority line before the one who's at the counter is completed。

 I'm going to get aced out in deffintly。So it's that analogy that's not fair， you'd say， right？

Does that make sense？Okay， so the second version just。

Fps this along and basically with a little bit more complicated code gives a benefit to the writers。

It's a。And here's how it works well， there's two things we're going to have to do one is actually it's a little subtle。

 but we're going to need two mu texts， one for the readers and one for the writers。Well。

 before I remember， the muttex was only for the readers。

 so now we're going to introduce a writer's mutex。But more significantly。

 we're going to introduce a second。Smapho that is guarding the readers。

And so you'll see that now the。For a reader to get。This is the read code。For the reader to get in。

 it will have to have this readlock。Which as you can imagine， will be collected by the。

Guarded by the writers and everything else about the code is the same except the the mut textex is I'm differentiating the read mut textex and the write mut textex。

 but it's the same idea now the first reader in will get to block any writers。嗯。But。

Here's what will happen that's。A little bit interesting。

 Now you'll see the code is actually much more symmetric that。On the writer side。

IfIf I'm the first writer。嗯。Then I'm going to basically grab this readwalk。

And block out any future readers from coming in。To the system。

 and I'll only release that when all the writers are done。In the meantime。

 you'll see it still guarantees this property that。Only one writer can actually。

Be in its critical section at a time， and it can only be there when there's no readers。But。

As long as sort the set of writers keeps accumulating。

 it can block out any new readers from entering the system。It's a。

It's hard to say this code would be any better in practice than the first one。

 and it's a little bit more complicated and it's a little bit more subtle the way it has these sort of。

Doling parts to it between readers and writers that there's a symmetry。

 but it's still preserving this general properties we want。嗯。So。

There's actually another way to do it。 You can think about what you really want is essentially a fiIO Q that would say。

We just keep adding new customers to the end of this line。And then as those customers come。

 if it's a writer， then that thread will have soul access to it。

 but if now there's a sequence of readers， we'll just let them all jump in at the same time and go ahead。

 but now as more readers or writers come along， they don't。

The more readers coming along would be added if if there's no if there's nothing else in the queue。

 but if one writer comes along， then it will basically hold its spot and any future writers will have to wait until that right is done so that would be a fair system meaning that assuming that the initial cu is the customers get cud in some order properly。

 then things will be guaranteed to happen in some。Vable system。

So there's actually code for that if you look at the class director， I didn't present。

 actually I just got it running this morning that I think is pretty cute。For。嗯。

That basically builds a 50q using the same style code that you did for Web0 of a linked twist with a tail pointer。

 and basically for each entry in the queue represents one thread that's waiting。

And has built into it then a semaphohor that's only used once。

The semaphore is initially assuming the thing shows up and there's。Has to be added to the Q。

 The semaphore gets set to 0。And the thread that's assigned to that position in the queue then blocks。

And then there's other code when you release。Either a reader or a writer releases it。It's lock。

 it'll then run through the queue and add to the list any waiting either a single waiting writer or any number of waiting readers。

 so I think it's a pretty nice code， it seems to work a little bit tricky。

 but I won't try and present it here。But you can see that that's really what you want to do and so anytime you start really worrying about systems and worrying about these fairness conditions。

You have to kind of come up with some principle about how can I guarantee that this system won't block out some class of users forever。

Make sense。Okay， so now。We'll just go through a few other aspects of。Of concurrency。

And we've talked about this idea of a race condition。This is one definition of a race。 in general。

 a race， any time there is a contention for some shared resource without any without any form of synchronization。

 The way they describe it here is that。If the program depends on the ordering of two events。

In a way that's completely unpredictable， then that's a race and some races aren't bad， I mean。

 if there's only one seat on the airline and there's two people contending for it。

 one's going to get that seat and the other one isn't。

 but that's just the way the world works and so that's a race but it's not a race that is an error。

But we've seen a lot of examples here of potential races where you could end up with a deadlock or something bad happening。

Like the count's not being updated properly。And we showed this with an illustration the first day。嗯。

So， there is。呃。This you'll recall this was the example of the race for the creation of threads and passing the argument to the thread。

Routine when it starts up。That we showed that the right way to do it in general is to mallic some data structure。

 pass that into the thread， and then the thread will yank values out of that data structure and then free it。

 I described it as a producer， consumer， meaning it sort of follows that pattern that the main routine is packaging this information up。

Passing it to the thread， and then the thread is extracting that information out and also doing the free recycling that resource。

嗯。So a deadlock is a case where。Where the program gets hung up becauses it can't proceed any further。

 it's waiting for some resource or synchronization operation that is never going to be available。

 so the condition it's waiting on is never going to be true。嗯。

And a very simple version of that is this code here that you'll see down here this count。Is。

Grabbing a muttex。Two mu tes and then releasing two mu tes。There's two of these threads。

And you'll see that one as ID0 and the other as ID1。

 and you'll see basically that they're trying to acquire these mu textexes in opposite order。

 So this gray code over here shows what's happening that the first thread I D0。

Tries to grab740 first and then se41 and meanwhile。

Id1 is trying to grab sema41 and then zero and this is a classic source of deadlock of acquiring the locks in the wrong order in an inconsistent order and so we can show that in this code here that thread0 is going to acquire S0 first and then S1 and meanwhile thread1 is going to acquire S1 and then S0 and you can see this notch here is the danger zone that it's possible for the program to get to this point。

And be unable to proceed。And so that's a classic。Reason for deadlock。

So it's entirely possible for some programs to avoid this， you know。

 they'll basically walk along and avoid that region。

 but it's also possible for some program to come in and get stuck。

And so this was the illustration we used in the first day sort of classic gridwalk is a case where each。

the vehicles are all kind of holding space that the other ones need， and so nobody can get out。え。

And in general， Delock almost always involves some cycle of dependencies that each one thread has a resource。

 the other needs， vice and so on， and there's this cycle of dependency that's very well illustrated by this illustration here。

It's picture。So in general， the rule is acquire locks in the same order across all threats。嗯。

And that will prevent what it will do in this picture is basically eliminate that notch it will say that I have to first acquire S0 and S1 S0 and S1 so I'll acquire and so there's no。

Possibility of the threads。One getting one lock and the other getting a different lock。Okay。

It's going to be a short class。嗯。There's another very important concept when you're using threaded code that's generally under the term threads safefe。

 is this code thread safe， meaning can it be safely used in a threaded environment？嗯。

Even though there's multiple concurrent threads that are making use of the same code。

And so there is a。In the book， the description of several different classes or categories of function of how threads become threaded code is not safe。

And we'll show examples of those， but the basic idea is there's some shared variables that are unprotected。

Very。Functions that have basically static local variables in them。That are。

Being used by multiple threads， there's ones that return a pointer to one of these static variables。

 or in general， it sort of applies a transitive weight that if one function calls a thread unsafe function。

 then it by definition is threat unsafe。 if it has no other synchronization in it。呃。

So example would be there's some shared variable， some global state that isn't properly using some type of semaphore muttex to guard against simultaneous update。

 and that was the example of these global counter that counting has to be done within the scope of a mutual exclusion。

Another example would be and unfortunately a lot of the standard library code that you use has this feature that there's some internal state to the system that。

Might be either statically local to that function， or it's in the library file。

 But a classic example is a random number generator when you call the。Either random or random。

 the two different random number generators commonly used in UniX。Basically。

 they don't really generate random numbers， as you probably know， they're pseudoran。

 meaning that they create some computation that makes the next value look very unrelated to the previous value and in such a way that if you call it often enough。

 you'll sort of get a uniform distribution across all possible positions。

 but it's really computed in a totally deterministic way。

And what they rely on is value is sometimes called a seed that's used to。

Create each successive number and one of the actions every time Rand gets called。

 then the seed gets updated。As shown here， so you'll see that it's almost like a hash function that it's taking the seed and computing some value that looks totally unrelated to it。

 but in fact it's just a simple computation。The point being that this code here， first of all。

 there's a race condition that I can have multiple。

Functions trying to update this next value at the same time。嗯。

And the other is that it's generally not a great idea to have， kind of， well。

 depending on the context， often you want control over your random number generation so that it's repeatable。

 which sounds weird。嗯。But for a debugging purposes it's often handy to have random numbers that are predictable so you can run the same program twice and get the same results Other times that's exactly what you don't want。

 and so you have to set the seed based on process ID or time of day or something like that that will differentiate it。

 but in general it's a good idea to have the at least the option of controlling your random number generators so again since this is a single shared global variable that if a whole bunch of threads you're calling RA then they'll be getting different values。

 but the more serious thing is they'll potentially actually be returning the same value to different threads because this updating of this variable next is unpredictable。

So the correct way of handling that is to use a what's sometimes called a。

A thread say or what's called a reenttrant version of this function， reenttrant。

 meaning that the value it produces depends only on the parameters you pass it and not on some global state that might be changing。

And so in particular with Rand R， you're responsible for creating your own。

Seed and storing it somewhere in your own thread。And then the job of Rar is then to update that seed and return a newly generated number but。

But it's responsibility of the caller to maintain that state and make sure that it's not being shared。

And so you could see you can have multiple threads each one with its own copy of this next。

A variable that are all calling the same function， and they'll always get the same results within each thread。

So that's sometimes called reentry， this idea that it's independent of any global state。

And then there's a lot of library functions that are make use of static local variables。

 it's the same general idea of as a global variable， so for example， this is the problem with printf。

That there's built into printntf library， there's some state that is used to keep track of time zones。

Of all things。For the date conversion routines。And it's a big library with a bunch of stuff。

And that stuff relies on some shared global state that different routines are allowed to update potentially。

 and so to make printf and all the relateded functions。嗯。Thread safe， they slapped walks around it。

Which is a general technique， but we saw that that's what messes it up when you try and use it in a signal handler。

Because signal handlers can interfere in bad ways with blocks。So anyways， there's other functions。

I2A is a conversion routine from。Integer to a string where this string represents the internet address。

 the IP address。Represented by that integer， we'll talk about that or I guess you already did talk about that in。

Lecttureures before where so something like 128。2。 x。y， that's an IP address。

Is actually just represented as an int， but an I2A will put it in that dotted deimal form。

But it relies on a， and it returns a pointer then to the string that gets generated for it。嗯。

And that worked fine as long as it was only used in a single threaded environment。

 it would actually pass a point or two。Lolobally static variable。Assigned to that function。

 which you recall， we saw before， variables like that are actually stored in a manner similar to global variables。

 they're stored in the global data part of the program。

So but the problem is every call to I2A actually returns the exact same pointer。

 and if there's multiple threads calling it， they're basically in this race condition with each other and messing it up。

So。It was implemented that way years ago so that the programmers didn't have to specifically allocate a buffer with enough characters to represent down a decimal string。

But it says。Archaic now。In a multi threaded environment。And so。嗯。The sort of cheap way of doing that。

Is to wrap a muttex around it and then use， but now the user will have to pass a。嗯。

A pointer to some destination buffer， which is presumed to be big enough。

And and then we'll just use stir copies， so we'll call I to a still this bad code。

 but since it's guarded by a mutex， there will only be one thread at a time doing it。

 and then it will copy that to the destination。You might also figured out， well。

 why didn't I just rewrite I2A in this version so that it just did the SPprintF directly to the destination？

That would be actually a better way， but this is just an illustration that in general。

 if you're stuck with some code that's not threads safe。

 you can sort of throw some muttexes in and make it thread safe。Make sense。

So this is a fix it's sometimes called lock and copy。And then in general， it's possible to have。

Thread safefe functions that are unsafe because they call other functions that are unsafe。

And so you might have to go pretty deep into the whole calling stack and libraries to sort of flush out all the unsafe code。

So I mentioned this idea of a reenttrant function， a reenttrant function is one that excesses no shared data。

 no shared variables when it's called by multiple threats。And that's sort of the ideal in that it's。

呃。Threadafe by design， rather than having to use lock and copy or some other trick like that to just take what's inherently a bad code and just try and improve it。

 So as this diagram illustrates all reentrant functions are threads safe。

 but it's possible to have a threadsafe function that's not reentrant。So in general。

 there's a lot of the sort of old time。嗯。Ununix library code that is not thread safe。

Because of some type of shared global variables or static variables and in some cases。

There's reenttrant versions， so we saw the idea of Rand。

The reenttrant version reend underscore R it used to be in this class we had students use get host by add and get host by name for their proxies。

 but nowadays we have this new kind of stuff that's reentrant so you don't have to worry about it but。

嗯。Like I said， these thread unsafe functions go back to a long time ago before threaded code existed and people just weren't thinking in terms of making it that way。

As I mentioned， all the standard most of the standard library code that you encounter like Malocan free are thread safefe and those who done by walkinging。

 you can imagine Nc， you've written a Malck package now and you have a pretty good sense that there's a lot of shared state。

 a lot of state in that。But。As long as you sort of lock each of those little sub functionss or put a lock up when you start Meloc and only release it when you're about to return from Meloc。

 you can make it thread safe and that's basically what they do。So anyways。

 threads are sort of a fact of life that you'll find now both for。

The way we're describing it here is mostly for functional reasons that you want to handle external events that。

嗯。Are unpredictable in their sequence， and so you have to use some mechanism that can handle it and threads have become the sort of standard way of doing that。

It's also， as will be discussed in the lecture next week on Tuesday that。

We've got these multi corere processors， wouldn't it be nice if we could actually apply multiple cores to solving a single problem？

And that's harder than you might think， but it's possible and it's a fairly important idea。

 so those of you someday take 418。We'll spend a lot of time on that， how to make programs run faster。

Generally， not just using raw P threads because that's pretty tedious but that。

Multi threading is an important way of getting code to run faster。But the problem is。

 there's just a lot of stuff that can go wrong， as we've already seen synchronization code is just really tricky stuff。

 The ordering in which you put statements is really critical。

 You have to think through all the time about， well。

 if I release this lock and somebody jumps in right here before I can do what I'm going to do next。

 I that a bad thing。 And it's actually hard to actually test all those scenarios as well。

 So you have to spend a lot of time staring at code thinking about it。

Using some of these basic principles like always require walks in the same order to to try and avoid problems。

There is a book if you're interested on Possics threads。

When you have the basic idea and you can get the basic ideas from the book as well。

 the man pages are okay， but the man pages are a very difficult way to learn something from first principless。

So this book is a little bit old， quite old。Still sort of the standard one people use。And also。

 you probably found threads in some form are available in most other languages。

Java has it sort of built in。 Python is fairly easy to fire threads and quite often use that way。

 So the idea of threads is not just a C idea。 It's actually across many different programming languages。

Okay， so I think that'll take care of things and I hope you' all have a good holiday。



![](img/a630629c8629ff7d004f5e0896d826c6_10.png)