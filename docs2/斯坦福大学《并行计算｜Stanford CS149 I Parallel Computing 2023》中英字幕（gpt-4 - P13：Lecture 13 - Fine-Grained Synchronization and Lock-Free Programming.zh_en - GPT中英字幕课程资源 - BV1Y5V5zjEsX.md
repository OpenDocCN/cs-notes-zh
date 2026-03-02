# 斯坦福大学《并行计算｜Stanford CS149 I Parallel Computing 2023》中英字幕（gpt-4 - P13：Lecture 13 - Fine-Grained Synchronization and Lock-Free Programming.zh_en - GPT中英字幕课程资源 - BV1Y5V5zjEsX

![](img/4bf6548ae8b81faaf2fb5bfc2a084805_0.png)

So this is a good lecture to make sure you're sitting by someone you like to talk to。😊。



![](img/4bf6548ae8b81faaf2fb5bfc2a084805_2.png)

Because you know whenever locks get involved， there could be some heads get started exploding a little bit and thinking about all of the cases。

 so we're going to work through some of those examples a little bit but to get started let's just make sure we're all on the same page with a few terms and those terms are deadlock livelock and starvation so I just want to go through those because these are all issues that can occur when you have synchronization problems in your program so I want to make sure I get some examples of these we're clear on the terminology and then we'll use that terminology later in the lecture。

😊，So deadlock， and it's a term that I've heard people， you know。

 those of you in the audience have said earlier in class。

 so it might be intuitive what it might mean， Here's an example that I drew up。

 This is an intersection。😊，And， you know， I've got four cars on the intersection。

 And my claim is that none of the cars can make progress。So do you agree with the claim？

And so if cars are not allowed to back up。😊，What does every car need in order to make progress？😡。

It needs it kind of needs the road in front of it to be clear right like so this yellow car needs the road in front of it to be clear。

 but that part of the road is not clear because it is held or it's occupied by the green car so why doesn't the yellow car just wait for the green car to get out of the way？

Well， the green car can't make progress because it depends on a resource。

 a part of the road that's held by the next yellow car and so on and so on。

 So notice what the conditions are here for， for this form of deadlock。 You。

 everybody needs to have a resource that they can't get and。

You can't and then the idea is that you don't relinquish that resource until you get everything that you need to make progress。

 So in this case， the yellow car is kind of holding onto or occupying this territory。

 but it needs this territory。 and it's not going to let go of this until it finishes its job。

And then finally， the problem is that we have a circular set of dependencies。

 I can't go because I'm waiting on you， you can't go because you're waiting on someone else。

 they can't go because they're waiting on me。And so these are。

 you need all of these conditions to hold in order for there to be deadlock。 So， for example。

 here's a photo that I took。嗯。Of a deadlock situation in real life。

Which is very similar to the cartoon that I here's a bus and the bus made a little bit wider turn than it should have or you could argue that this car probably ignored a little something on the road that says please don't pass this line because buses need to turn here and all of a sudden the bus can't make progress because that car is there the car can't make progress because the bus is there and why is it the case actually that we get deadlock。

 we need ability we need to be in a situation where we can't relinquish resources。

So relinquishing the resource here would be what？Would be backing up right and you can't see it from my photo but neither of these folks can back up because everybody's kind of filled in behind them and so ultimately I mean it certainly isn't actual deadlock because otherwise if it was real deadlock。

 the road would still look like this So eventually people start backing up。

 but you know you have effective deadlock here are a few more examples of deadlock。😊。

For our more nature loving folks。And so make sure you can convince yourself why these are deadlock。

Nobody is willing to relinquish a resource because they don't trust the other party。

And since that's the case， no progress is being made。😊，Yeah。Now， of course。

 the reason why I'm telling you all of this is this can obviously happen in computing systems。

 like a simple example might be， imagine we had thread A and thread B。😊。

And thread A pulls data out of some work queue。And puts results in some output work queue。

And threadhread B supposed to pull data out of this work queue and put the data back in the one at the top。

😊，So you might be in the case with thread A says， well。

 I'm not going to pull any new work because I have nowhere to put my output。

So thread A doesn't drain its input。And it's waiting on B。

 but B can't make any progress because there's nowhere for B to put its output。

That's an example and the example of Delock that we hit earlier in class is when we were talking about message passing。

 remember I said， oh， there's this subtle bug in our original message passing code。😊。

Where we said everybody was going to send and wait for their message to be received。

 and then they would turn around and receive。And so that was an example of deadlock as well。

 everybody was blocked on essentially the same call。And as I alluded to earlier。

 you need these four conditions for deadlock to actually occur。

 we need to have resources that can only be held by one party at a time， that's the mutual exclusion。

 like only one car can exist in this part of the road or only one thread has data in its input this input queue is exclusively for this thread。

You have to have a situation where you can't back up。😡。

So once you kind of start this process and you acquire you know like the road。

 the part of the road that you're in， we're assuming that you can't back up or relinquish those resources to free things for other people。

 The only way you can free up resources is to keep going and complete things， complete jobs。

Last is you know no three and two and three are kind of similar in that there's no preemption。

 like if you actually could take the threat off the processor and relinquish the resources。

 that's kind of basically relinquishing resources， and then the most important one is this fourth one。

 which is the circular set of dependencies。I'm waiting on you while you're waiting on me。

And because if there wasn't a circular set of dependencies。😊，What would happen here。

 how would this resolve itself？Imagine that there are only three cars in the intersection。

 and not four。There are only three cars someone would make progress right。

 and as soon as they finish their task getting through the intersection。

 they would relinquish resources for someone else and then someone else can go and so on and so on。😊。

Okay， so that's deadlock in Dlock nobody is making progress。Like nobody's doing anything。

 no progress is getting made。That's a little bit different than the situation of livelock。

So in Livelock， that's a situation where you're constantly doing things。😊。

But no real progress is being made。So for example， imagine that we have these cars in this intersection and they did have the ability to back up。

😊，And so every car saw that they had sort of reached this sort of impasse where nobody can make progress and imagine everybody backs up。

And then everybody's like， oh， the intersection is free， I'm going to go。😊。

Then they back up and so on and so on So this is a situation of live locks it's called live lock because everybody's making progress like there's not you see operations happening left and right if you had like system logs you'd be like yes。

 that's happening but then you'd be like but nothing real is happening。😊。

So this is another problem that we can get into what's the most common day to day example of LiveBlock？

😊，That you run into。맞者。I thought I heard a mama。What happens all the time when you kind of walk up to a door？

And somebody else is like you go， you go， you go。 that was like the most common social live walk that definitely happens or where you're walking and both of you walk to the same direction and then you both walk the other direction to let somebody go by。

 These are all examples of real life live。😊，Okay， so we have livelock and yeah。

 so Livelock is a state where we are actually doing stuff， but nothing is all that interesting。😊。

And then last there's the condition of starvation and so here's another road example。

 imagine that there was a yield sign here， so the yellow cars on the horizontal road had a yield sign and had to yield to traffic on the main vertical road。

😊，So if this is a busy time in the day。And the green cars are just a steady stream of green cars。

 they're going to make progress。We're going to get a lot of stuff done。

 but certain operations such as yellow cars going are going to get completely starved out because if they have to yield to the green cars and the green cars never have a hole in the traffic。

 you're just going to be sitting there all the time。

For those of you that are going over to the beach very often。

 it's like trying to get on 101 or sorry get on Highway1 on a weekend I mean you're stuck in half from bay and you're trying to turn on to Highway1 and you can just never get on the road so it may look like you are like if you're debugging this thing to you it might look like oh shoot。

 maybe I have deadlock because I'm not seeing any yellow cars do anything。But you're actually。

 we are completing useful transactions。 We are letting the green cards go。 Okay。

 so those are just three things to keep in mind throughout the lecture。 Deadlock， livelock。

 starvation， all things that we can we can kind of mess up。😊，All right。

 so before I start talking about lockCs， I think this is be a good time to review this diagram that Konley put out in front of you last Thursday。

 I think yeah last Thursday so that was the first time we talked about about cash coherence and so before we get into thinking about how locks are implemented。

 I want to make sure because you've only seen this once technically and this is like the first you're doing homeworks on this now that people have a little bit of an idea about what's going on here。

 so first of all， if you had to describe the purpose of cash coherence。

Why did we talk about that last week at all？What's the problem that cash coherent solves？这是。喂。

You will。Oh， okay， well， yeah， okay。 So it solves the problem of we want caches。

 and if you have multiple caches。😊，They are copies of data。

And whenever you have copies of data and you have rights。😊。

You've got a real problem and you've got to keep those copies up to date。

That's the problem that cash coherence largely solves good。お。

I guess if you had to maybe building on that， if we had to say。

 what is the general strategy that these cash coherence protocols that Kume talked about？You know。

 if you had to give like a high level， like， what are they all what。

 What's the main idea of them or what are some of the key principles， Like。

 what does this diagram even mean， Yeah， like multiple。so one version of this is saying if。

You make copies of something and you write to it。 You have a problem keeping those copies sort of in sync。

Don't allow there to be copies if you're writing to something。😡。

So then the first name of the game is the minute you write to something。

 all other copies are going to have to disappear so that there's not a problem where you cannot access data that might be sta。

And how did that get insured？In other words， like what is this diagram actually？

I guess it's like you don too。We fall three eggss， all the one to go。我们过。Okay， so it' good。

 and so I'll repeat that in a second for people remote。

 But the first idea that I want you to think about is that this cache coherency diagram is it's a policy。

 It's a rules of the game that all the caches have to be agreeding to。😊，So this is the state machine。

 this is the logic that every cache executes individually on their own。

To ensure that coherence is met and one of the biggest parts of coherence is to make sure that when one person is writing to the data。

 nobody else is and nobody else has data， so the way I want you to think about this is and K gave you one of these examples before is I want you to think about a sequence of memory operations performed by different processors or different caches。

And then I want you to think about what would I do if I'm cash zero？😡，In this situation。

And what would I do if I'm cash1 in this situation？So just to start。

 let's just say that the first cache loads a variable or loads an address。

And what that cache does is talk to me about it， like what does that cache do。

 what does this text on the slide actually mean， there's like issue bus read， loan。

 light X and S state reserve bus read， what does that mean？We have two caches。

 and let's just say I'm cache 0。And I wanted to read from this address， so what do I have to do？

Cl here is doing is it's broadcasting the fact that it is reading like this particular memory address to all the other caches so that if the other caches also have that line inside them。

 then they can kind like call the protocol and transition accordingly。是。Good so just keep in mind。

 the name of the game is that all of these caches are working together。

And whenever the state of my cash changes。I have to tell all the other caches about it。

Because they're making decisions based on knowledge of what I'm doing。So in this case。

 if I load address X， I have to shout out to all the other caches that say， hey， by the way。

I'm about to have a copy of this， which basically is saying， if you ever get around or writing to it。

 you got to let me know。So that's me cache zero shouting out I'm loading line X。

 and now what allows me to load it into the S state？It's still consistent。

It's still consistent with memory， yes， yes， so basically， first of all。

 I'm loading it essentially with a permissions to say I promise I'm only going to read from it。Right。

And that means that other caches know what。If I'm only going to read from it。

can also read from it exactly， so so that's what I did and notice that Ca1 did nothing at that point。

Why is that？Yeah， like like I yelled out， hey， I've got the wine containing X and the other cash is sitting over here saying it's not in my cash I can carry less。

 right exactly。Okay， and so then I loaded， yeah， I loaded to it again， I read the value again。

 and what happens。Absolutely nothing。 Why does absolutely nothing happen？Yeah。

 why do I not have to tell anybody about this， It's a hit， my cache state did not change。

 They already know what my cache state is， exactly， right？

So now let's say I want to write to the thing。What do I have to do？I have to yell out。

 but I'm about to write to it。And what does everybody else have to do？😊，然。Yeah， and now in this case。

 the other folks don't care because they don't have it， right， So in this case。嗯。Does't do anything。

And now if I want to write to it again， again， same thing， if I write to， oh， and this is OK。

 so now the other processor wants to write to it。😊，Whats the other process a good deal？

So it's going to shout out， hey， I need to write， and what do I do？

So first of all I can't keep my copy and in this case since I have written to the value。

 I better put the most recent value back out of memory so going I'm going to put the data back out of memory so the other processor gets the latest value and then I got a drop because of why don't I just keep it in shared state？

😊，Because it's going to be stale， because the other person that's going to write to it， exactly。😊。

So now if another load by the other party doesn't matter to me because I'm like。

 I don't have the value if I want to bring it back and read it。I'm going to say， hey。

 I want to read this value now， the other processor is going to flush it out to memory and then what are they going to do about their cache？

😊，They could， they could keep it in shared because they're like， well。

 I can't write to it anymore because there are coffees around。😊。

But I'll keep it around because if I want to read from it。

 I don't want to actually take that cash miss and so I'll let this。

 you know you know we won't go into the rest of this。

 but these are the things that you definitely need to be able to walk through and step through in your head。

 You did one last week I think there's one on the homework assignment and stuff like that Okay so with that in mind。

Now let's think about implementing a walk。And I'm going to give you because you're used to。

to using a bunch of locks， but we haven't actually talked about the underlying details very much。

 So what I'm going to do is I'm going to give you an instruction that's not a load or a store。

 but actually a little bit of both。 It's a load compare store。😊。

So imagine that you have a machine instruction and just to keep it simple。

 I'm going to call it test and set but in practice these types of machine instructions are very different。

 they might be compare exchange or load links store conditional。

 but imagine you have this instruction called test and set which takes the value or reads a value from memory at a designated address。

 and if the memory's address is zero， it sets it to one。😊，It's all it does it。

 loads it and sets it to one。Okay。Now let's think about how I might use this to implement a law。

So here's my simple assembly code for implementing a lock， here's unlock。Let's start with unlock。

 actually。😊，So imagine you had a variable that was one if someone had a lock。😊，And0， otherwise。

If you're the thread that has the lock， how might you unlock？都话。Its right zero。Makes sense， okay。And。

Here。What is the lock procedure， the lock procedure is try and execute one of these testing sets。

 which says if。And it's storing the value of loaded from memory here into this register。

 so I'm going to read the value from memory and if it's zero。😊，嗯。

I'm going to set it to one all in one step。 This is one instruction， one atomic instruction。

And if the value， I read from memory is0。😊，What can I conclude？I have the lock。

If the value that I read for memory is one， what can I conclude， I don't have the lock。

 and I actually amm going to branch if nonzero back up and try again。So it's basically， I'm saying。

 while the value in memory is not as one， keep trying this test and set thing。

 If you ever see it to be0 by the time you you're checking to see， oh。

 was I the person that set it to one， if you're the person that set it to one， you have the lock。

And then the minute you unlock， presumably， some other thread can come in。

And now succeed with one of their test sets。 Now， like if for example。

 if you were running on an Intel chip， you wouldn't have test and set。

 you might have something like Comp exchange， which is a little bit more elaborate form of things and offline。

 I think it'd be kind of fun to study this to say， basically， hey。

 can you confirm that essentially this is a lock with compare and compare exchange which basically is using some X86 flags registers and things like that doing basically the same thing。

😊，Okay。Okay， now here's why I spent some time talking about or reminding you about coherence。

 Imagine that we have three processors or three threads and they're all trying to get this locked。😊。

So remember what they're doing is they're saying while Test and set fails。

 keep trying and as soon as test and set succeeds， I know I have the lock so I can do my critical section kind of thing so let's think about what happens。

😊，Processor  zero， let's just say that processor0 is the processor that first tries to get the log。

That test and set I'd like you to think about as a right。

 at least from the coherence protocol perspective， it's a right because it's modifying the variable。

So since it's the right， processor0 or processor1 in this case is going to try to execute its test。😊。

That test and set is going to cause an invalidation。Because that's a right operation。

 even if it fails， it's a right because it's an atomic operation that may right。Okay。

So at this point， if that test succeeds， I think you would agree with me that processor1 is holding the log。

Okay。So let's think about what happens at the same time， so processor2， at some point in the future。

 tries to obtain the lock。And what is processoror 2 going to do to try and get the lock？

It's going to execute that test and set instruction。What's going to happen to the cash line？

Processor one and three will have to invalidate。😡，And the cache line containing the lock variable is going to move over。

To a processor two。Okay so keep in mind what's just happened。😡。

A lock is just a variable that has a value。That variable is just in the address space， it's cached。

And so even though processor one has the lock。Processor 2 has a valid cache line containing the variable that the lock is。

 So having the lock。And having the cash line are two different things。

So there's nothing stopping from process or three from coming in and trying to get the lock at this point。

 right？So that cache line is actually just going to bounce over there to processor three。

And then all these tests and sets by processor 2 and 3 are failing， right？

Because they can't get the lock， which means the cache line is just doing this。Does it make sense？

Now， what happens when processor one wants to unlock the lock？It's got to issue a bus readx。

 it's got to invalid everybody else。 It gets the line in exclusive mode。

It does the right to set it to zero。And then one of those tests and sets on one of the other processors。

 Let's just say processor 2 succeeds。 And now processoror 2 has the walk。

So think about what's going on here is I'm a core， I have a lock。

 I'm in my critical section trying to do this thing so I can release the lock。😊，AndFirst of all。

 there's all this bus traffic flooring around between all the other processors as they spin。😊。

And second of all， actually， I have to take a cash miss to get out of the walk。Which kind of stinks。

 too。Because that's time that other folks are not doing what they need to do。

Why is the test second law。Well， the test instead is an atomic instruction。

So there's a couple ways I could answer that question。

 one is the instruction may or may not update the line。

But you need to have right access if it's going to go through。

So there's no way you could implement it as an atomic。

Or I guess if you implemented it as a let me give a bus transaction to read the value and then another bus transaction to sort of upgrade or get right permission。

 you're issuing two bus transactions， so by definition it's not atomic。😊。

And at X86 there's actually a lock prefix on a number of instructions and that lock prefix basically kind of does that。

 it says sure under the hood this will be implemented as multiple transactions。

 but they've got like a lock flag on them meaning that we're not going to allow any transactions in between to the same thing or something like that so you can just effectively think about it as atomic independent of what the。

😊，Implementation is going to be。So I already alluded to this。

 but I want you to be absolutely clear here that on the previous slide。

 what is the duration of time that the thread running on P1 had the lock？😊，It was the entire slide。

What was the duration of time where P1's cache contained a valid copy of the line containing the lock variable was only for a second at the time of lock and for a split second at the time of unlock。

It's kind of interesting， right？And so like a simple lock like this has some properties that if we added more and more threads。

😊，More and more processors are trying to actually grab this line。

It might take an increasing amount of time for the core with the lock to actually be able to grab it in the right state again。

🤢，And you actually see that in this graph where this graph is just kind of like the cost per lock unlock。

😊，Which is actually going up as a function of the number of processors in the system。

Because basically like in order for me to get the cash line in the right of state， I'm fighting。

 I'm contending with increasingly large number of processors。

 it might take me longer to get that exclusive access and might take me longer to literally unlock the lock。

 and so every unlock unlocked period actually starts getting big and gets higher。Okay。

So now you might say， oh， wow， it sounds like we could do a whole lecture on how to efficiently implement locks。

 which we're not gonna do。 but you could think about some of the properties you'd like to have in your lock。

 like you'd like it to be be fast。 know like low latency like when you call lock。

 you don't to wait for very long or you call unlock， you don't wait very long。

 you'd like your lock implementations to not basically Ds your system by generating a bunch of interconnect traffic while everybody's waiting。

 everybody's spinning。 You might like it to scale to large numbers of cores。

 You actually might like it to be fair。 There was nothing about that previous implementation here。😊。

That guaranteed that all the processors would ever get the lock， right。

 like maybe processor one processor two just keep getting it and there's nothing to ensure that processor3 actually would。

In this implementation。So， so implementing locks efficiently can actually become a pretty。

 pretty interesting thing。 So let me just give you a few small refinements。

 So here's a different lock that has the same test and set instruction。

 So now I'm just I'm writing in C code to make it a little bit clear。

 Test and set does the same thing， if the lock is， if it returns the value and memory。

 and if the value of memory is 0， It atomically sets it to one。 So this。😊，You know。

 sort of this if test and set is0， well that means I executed a test and set and the return value is0。

 so I now know the value in memory is what？😊，One， and I also know that I have the lock because it was zero when I started the test set。

 I know it's one when I ended it。And I know that I executed the test set when nobody else had the lock。

 which means I have the lock。So that's what this is if test and set returns zero return。

 which means I have the lock。But what's this thing doing， Why do I have like while while here？

This is correct， like there's not a bug in this code， this is correct code。

But can you kind of back engineer what I'm trying to accomplish？对。Yesestin staff。

 where can I to get the？so this called a test and set is a read exclusive or a request to write to the value。

 What is this while value of lock is zero doing？It's just saying， oh。

 just keep checking to see if it's zero， because if it's not zero。

 why should I even bother doing a test set？😡，So what's the implication of this。

 so what happens here is while the lock is taken by someone else。

 I am going to spin on reading to see if it's still locked， if it ever becomes unlocked。

 I'm going to try and jump in there and do my test set。If I fail。

 I'm going to go back to a waiting until until it's unlocked again。 Why might this be a better idea。

Yeah， there。So I'm turning a bunch of writes into a read or into a bunch of reads。

 So let's go back to my diagram。 Let's think about what happens。

Same thing as before P1 grabs the lock， teach P1 doesn't write a test and set to get the lock。😡。

All other processors are spinning on， is the value still zero？

If I'm reading over and over and over again， all the other processors are just holding that line in what state。

S state， yeah， the shared state， which means they're just taking a bunch of cash hits。

 So for the duration of the critical section， they're spinning they're doing work。

 but that work is not creating global traffic out to everybody else。

Processor  one still has to take a cache miss to get the line back in the what state。

To release the lock。Processor one definitely has to take a cash miss。

It's a cashmist to get exclusive access again。 That's where the right to set the value to zero occurs。

 And then everybody else， all of a sudden invalidates their line because they had to their next read back into the shared state finds that the value is0。

😊，And then they all jump in and try and actually do a right。

So you're going to get a flurry of if you have P processors， you're going to get p minus1 rights。

 or if you count this one， it's O of P rightss on every lock relief。😊，But during the Cri section。

 you get no rights。So thiss kind of nice， right， Like。

 it also helps in that while I'm in the critical section。

 I would love to have an uncontended bus because maybe I'm doing reads and writes to other variables。

 and I don't want to wait on an interconnect。 So everything calms down during the critical section at the end。

 there's this feeding frenzy where everybody says， oh， I think I can get it。😊。

And that's actually when you take P in P different write ins。

So we're pretty good that we really we like what we did here。

 right like we got rid of this like continuous flurry of traffic whenever we're in the critical section。

 I'm still doing it with one integer。😊，You know， my lock variable is just one integer。

 I haven't tried it all to make things fair。There's no guarantee that anybody's going to win and I slow things down just a little bit because now when the lock gets released。

 you have to do two things， you have to do a read and then a write or a read and then a test and set and not just a test and set。

 but I'm not too worried about that extra instruction of latency to be honest。

Just to give you one more design， here's a different thing that echoes how it might work if you go。

 if you're going to go get a sandwich or you go into the deli counter。

 like how does that work in real life， like you show up for the counter and how do you know when your turn is？

You take a ticket。And so the butcher or whoever's， the deli person or the sandwich maker is like。

 okay， when they finish a job， they increment the current pointer。😊。

And so that's what's going to happen here。 So now I have a lock that's not a single variable。

 but actually two integers where let's ignore wrap around for now just to keep it simple and I have an integer for now serving。

😊，Which is。The thread that has the lock is the thread that has the ticket matching now serving。🤢。

And then we have N's ticket， which is when a thread wants the lock。

 it walks up to the counter and says， can you give me a ticket a unique ticket ID。

 so let's look at Lock。It's。My ticket， my local ticket is going to be an atomic increment of next ticket。

 Its just like， give me the next available ticket。😊。

And then I spin while my ticket is not now serving。And that is largely a bunch of reads。

And now releasing the lock。When the lock is released。

 the thread with the lock just increments now serving。

 so it has to get exclusive access to now serving。And doest write， doest update。

But now look what happens for if you have a lot of waitinging threads。

 it's not like everybody tries to get the lock now， only one thread is going to try and write。

And actually it doesn't even need to write at all， it just needs to do a comparison。😊。

So now a locked release is actually only one right， this right。

And the thread that acquires the lot actually doesn't have to do right at all。

It only has to do it right when it， when it sort of enters the waiting queue。

So it's just another example of ways you can actually reduce contention and in this one actually this is fair。

😊，Because you get in line and the first person in line is you're going to be served in PIF order。

So it's pretty cool， you know I don't need an atomic operation to acquire the lock。

 I need an atomic operation to start waiting， but I don't need to acquire an atomic operation at the point where I get the lock。

So that's pretty cool， there's only one right per lock release。嗯。Now。

 what it did do is it required your hardware to provide something a little bit more sophisticated than Test and set。

The hardware had to provide an atomic integer operation， an atomic ad in this case。

 So now you're asking a little bit more of your hardware here。嗯。

So here's a list of a bunch of atomic operations that you might find on any platform these days。

 here are atomic operations that I took from the Kuda builtin library， Kuda standard Library。

 So if you're running anything on NviDIdia GPUs， you have all of these atomic operations at your disposal so like an atomic increment。

 which is what we have is it takes the value pointed to here at this address and increments it by this value。

So that's a read， modify write， like read the value for memory， update its contents， write it。

 all in hardware guarantees that that's atomic with respect to all kuda threads。

And I'd like to call special attention to this atomic comparison swap， so CAS is Comp and swap。

So this is the logic of atomic compare and swap。 Now keep in mind that even though I'm writing it here as C code。

 this is an instruction， this is what the instruction does。

 so it's not like there are locks inside of this or something like that。

 so the hardware is providing some mechanism。Where this can be and what it does is it takes a pointer to an address。

 it takes a comparison value and a new value， and it says if the value in the address is the same as the comparison value。

😊，So the value out of memory， if it's equal to compare。Please write this new value in。

 otherwise leave it unchanged。😡，Okay。And I wrote it here in this syntax to kind of give you a sense that basically a right is essentially happening regardless of whether or not it's unchangedchange though。

 so I'm setting the value and address to either its previous value or this new updated value。😊。

So given this。What if I asked you to implement something like atomic min。

This is something that's a common question that I might ask on， on a homework assignment。

 I don't think I did this year。 Actually， this is a good one to study。

 So atomic compare and swap just says。Grab a value from memory。

 if it equals this value called compare， please update the value in memory to v else do nothing。

What if I said I don't want this， I want to something much more useful。

 like I want you to read a value from memory。 I want you to compute the min of this value and some other value。

 and I want you to write the new man back out to memory。😊，Yeah， you just do like。Old is greater。

Close。Close。What do I want to know in any atomic operation？

What I want to know is that no other thread。Has set the min lower。

So let's just say that the current value of men in memory is 100。And I'm coming in with 90。😡。

So if there was nothing else in the system， my answer should update the minimum to 90， right？

But what if after I read 100 from memory？But before I wrote 90 back out。

 some other thread had the value 80， and updated memory to have 80。And I come in and write 90。

I've messed things up。So I know that my operation can succeed if I can guarantee。😊。

That no one else has come in while I was trying to do this min operation。

And how do I know if nobody else has come in？I can， but we're not going to use any locks here。

I don't really care if nobody else has sort of come in， I only care if the Min has changed。

That's actually the only thing that matters to me， right So if I read the value from memory。😊。

Compare it with my men。And then go， oh， if my Min's lower， I'm going to write it。

I'm going to write my value， but I only want that to happen if the value in memory is the same。

That's what it was when I got this whole thing started。

And hasn't changed right That's exactly what compare and swap is going to do for me。

 So let's take a look at this。 Atomic min is I read the current value out in memory。

 I'm going to call that old。😊，Then I look to see， okay， is my value in this case， x。

 is it smaller than old？😊，I'm going to put that here。And then I'm going to say， okay。

I want to update the value in memory。😊，If nobody else has changed anything。😡。

So I'm going to do an atomic compare and swap on the memory address and I want to make sure that the address and memory is still old and if it is。

 please update it with you。And compare and swap always returns old。

 and so that's how you know if you succeeded。So compare and swap always returns the value in memory。

So if the value in memory equals old， I know now that the value， I've updated it to new。😊。

If the value in memory is not old。Try again。じゃあ。If you listening like this question up。

Yeah different。like already to this address is also being kept track of via the cash states， right？

If the cast state was invalid， then perhaps know。s a lot of it's a a great question okay so so let me answer in two ways。

 first of all， the game that we are playing right now is the only primitive you have access to is Compance swap so in that game you don't know anything about the state of the cache。

😊，But what you're saying is that if I had the cash line。And for some reason， I lost it。

Then some other operation has intervened。Now， to be honest， in the cache coherence protocol。

 that operation could have been a read。Which would not have modified this at all。

 But let's just say I knew it was a right。 Like， let's say。

 I invalidated my line instead of dropping it to the shared state or something like that。

If you had some way to get access to that， then you could provide me some alternative solutions and there is in your practice problems。

 the non requiredquid practice problems， there's an instruction。

 a pair of instructions called loadlink store conditional。

And that's kind of what those instructions do， load links says load of value from memory。

And at an address， store conditional says store a value to that address provided that it hasn't been touched by any other processor since the last load length。

Those two implementations can ride the coherence protocol really easily and in fact。

 theres a practice problem that I think I gave you which says imagine you has MSI coherence。

 how would you implement loan length store conditional？

So load links store conditional I believe even to this day are kind of the preferred primitives on arm Yeah Yeah I mean I'm not sure if they because they didn't have cash coherence before。

 so lately I mean now they probably leverage the cash coherence protocol to implement them。

 but before they probably just had some processor or state or something right where they。He。

 probably。Yeah。Co yeah because I remember reading the instruction manuals like a couple years ago is like you can have up to this many outstanding load length store conditionals or something like that。

 so on like some tiny processors there's probably still some table or something that's like yeah yep。

 exactly so what you're proposing is a very common operation on arm and so it's exposed to you via loadlink store conditional。

😊，Here's another great exercise， and I'm actually going to leave this one to you。

Which is given atomic cast， build a walk。And remember， how did we build a lock。

 we built a lock to say if the value in memory is zero， make it one。

And so it should be a pretty obvious thing last slide order to like1。And then拦。Okay。

 to can make me check what if it was like 18。じです。はい。Yeah， so imagine I'm trying to。

 I have the value 90 and you have the value 80。And the current min is 100。Okay。

So let's say I read 100 for memory。And I'm going， oh，90 is less than 100。

 I should probably write 90 Before I get around the writing 90， you come in。

You say 80 is less than 100， and you beat me to it。 You write 80。Now， imagine if you look at。

 that's weird。Now imagine that I go ahead and write my 90。We're incorrect。

 like like the code is broken now， So I need to know like I've read a value。

 I've done some comparisons or whatever。 And then when I do my right。

 I have to say I only want this right to occur if the value is still 100。

Because the value 90 that I'm writing in there is the correct answer provided that it started at 100。

But if you've come in and changed that value， in this case。

 my atomic cast is going to fail because the value in memory is not old， it's not 100。

 so whenomic cast returns to me， it returns to me 80， I go whoa 80 is not equal to 100。

 therefore my atomic cast must have failed。I need to try again。

 So I go load the value from memory again。 I now observe 80。 I compute a new min， and I go， oh。

 my 90 is bigger than your're 80， so it should just stay 80， and then I try again。

Then that it would go through and then it would see the update。 isn't this inefficient。

 so let's say you have the value 90 and the current value was 80。

Why the word should even go Well I can make my program better。

 which says if the new min is not the same as the other one just bail Yes yeah yeah yeah yeah I could definitely make my program more efficient and that would be similar in spirit to like this test and test set lot right exactly yeah you could do that。

So the point here is if you have an atomic cast。You should be able to easily implement everything on this slide。

And moreover， you should be able to implement。Lock and unlock too right because lock and unlock are just like atomic。

 if it's zero， set it to one right and so the implementation of lock looks just like this。😊。

and if you want to be a little bit more clever， the implementation of the test and test and set lock from the floor looks a little bit like that。

😊，So on an exam or on future homeworks I will assume that you're familiar with Comp and swap now we'll always give you the definition。

 but it's very common exercise to say given compare and swap can you create an atomic primitive of some customized nature given that and we already talked actually about loadlink store conditional as another pair of atomic instruction so some systems give you atomic casts a lot of most systems actually give you load link store conditional and everything gets built up from that。

😊，So just a few other things， like for example， in some of your assignments。

 you've used atomic and C++， you might be wondering a little bit about what that means is just keep in mind that if you at least in modern C++。

 if you wrap a variable in atomic，The operations on that variable are assured to be atomic。

So one way to do that would be， let's say if we had i+ plus automatically increment I。

 the implementation of atomic increment could be lock I plus plus unlock I be valid。

 but you could believe that most implementations， say for certain operations on certain variable types。

 if there was an efficient hardware solution， it would in fact use it so if there was an atomic increment in the system i+ plus on an atomic type event would actually translate into an atomic increment instruction for more more expensive stuff。

 it might actually be implemented under the hood as a lock and actually any variable of type atomic。

 you can actually query is it lock free。😊，And it'll tell you a little bit about how it's implementing that atomic operation。

So it's kind kind of fun。 The other thing that it does and that we're not talking in too much about。

😊，Is。When you use these atomic variables or like locks。

 you have to be really careful about relaxed consistency。Like if you were implementing these things。

 imagine you have this lock implementation from right here。And your code called unlock。

 which is just write zero to this address， and let's say that there was an operation up above this which would have been in the critical section imagine if due to relaxed ordering。

Those operations got reordered， so another processor saw the unlock。

And then solve the right to a value in the critical section that would be very bad。

 your lock would essentially be useless， So I'm writing these implementations assuming we have a sequentially consistent memory system。

 a real implementation of lock。😊，On a relaxed memory system would actually have a memory fence here to make sure that everything that came after that walk or before that walk。

 for example， was not reordered with respect to other processors So I do want to point out that out。

 like you will encounter relaxed memory consistency。

 if youre in a job like a driver or a less lighter or your job is to implement synchronization primitives。

If you are just using synchronization primitives， you always assume that those primitives have properly inserted the memory fences to give you the strict ordering that you actually expect and I think that's about all I'm going to say really on this So one of the reasons why you use atomic int is not just have atomic operations but to make sure the compiler implements those fences around there so you do not get unexpected relaxed memory consistency issues。

😊，Okay， all right， so that was just like a half a lecture just on。It's kind of interesting。

Kind of interesting you see what happens and you call a lock or unlock and there's a lot of complexity there and if you get it wrong。

 like the speed of these locks can be very， very different。😊，이것。

And the cache coherence and memory consistency are front and center。

 actually in the different implementations， for sure。Yeah。佢问个话俾个充。Well。

 there's also a bunch of other ways to implement the lock that I didn't talk about that they almost certainly tell you in an operating system for。

 So all of my locks are what you would consider to be spin locks。

 The processor is still just spinning。 you know there's also the idea of actually sleep the threat。

literally sleep the thread and pull it off the execution context My understanding if you look at most lock implementations。

 the way well there's a difference between Mutexes and spin lock sometimes in these libraries so spin lock will do something like this。

 most sort of heavy weight locks will actually probably spin a few times to try and get the lock and if you can't get it after a few spins then it does the heavier weight systems calls to pull you off the processor。

I know P threads is implemented that way was it doesn't like if you try and get the lock。

 the first time if you fail to get the lock， it's not like they sleep you immediately， they're like。

 okay， maybe it'll be available in a split second， try a few times。And if you fail a couple times。

 then it'll take you off。Okay， so let's talk actually about using these things。

 which is equally complex but a completely different topic。

 so now I want you to assume that you have locks。😊，Okay。And here's a linked list。

So take a look at this and just confirm yourself， maybe even and there's going you a lot of code coming up。

ThatThis is in fact your run of the meal job interview link list which has insert and delete I'm not even handling the edge cases of inserting the front of the list just to keep the slide simple we have a node which has a value and a next pointer and this is insertion and deletion into a sorted linked list so your operation on insert will be create the new node and then walk forward into the list until you find the first node that is bigger than me。

😊，And I need to insert myself right before， yeah， so the current list item is current。And if。

If the current value is greater than the value that I'm trying to insert， then we quit and we move。

Yeah， yeah， yeah， we keep walking forward， and then we break。 And then if so。

 the new nodes next is the current。 the previous nodes next is me。 So in other words。

 I'm walking forward until I find a value in the list that's bigger than me。😊，Previous points at me。

 my next points at the note I just found。Okay。So what I want you to think about a little bit now。

 and this is maybe you know everybody's sitting around staring at me。

 this is where I'd like you to talk to yourself a little bit。

 I'd like you to tell me what could go wrong。If I run this in a multithreaded setting。

 there are no locks on the code right now， so think about what could happen if you're deleting two nodes at the same time。

 think about what could happen if you insert two nodes at the same time。

 just think about all the possibilities of what could happen here so I'll give everybody about 90 seconds or so to do that。

Like， is there a way you could lose nodes， is there a way you could lose the rest of the list？

Things like that。Go for了。And yeah， feel free to talk about with your neighbors， of course。All right。

 should we talk about a little bit？I see some people still puzzling over things。

 which actually is pretty， if you're not still puzzling over things。

 I'm impressed because even with suddenly as simple as a linked list， this can get kind of hard。

 So let let's go maybe look through some visual examples that might help everybody here。

 So let let's consider double insertion for now。 So let's say that I have this list 3，5，101118。😊。

And let's say that I want to attempt to insert six and seven。

 so Im want to kind of insert right next to each other in the list。😊，So what's going to happen。

 like what's the right answer for thread1？Well， thread one is going to walk forward。

 find this point in the list where the six should go， and if there were no other threads involved。

 previous should point to six and six should point to current。No problem at all。

We get something that looks a little bit。A little bit like this， patch it right in。可。

Now let's think about what thread2 would do， like thread2 would basically want to do the same thing。

5 should point to 7，7 should point to 10。Okay。Now， what's going to happen when？

Both of those are going on at the same time。I think you might at double。Well。

 let's say thread1 just says， okay，5 is going to point to6 and6 is going to point to 10。

And then if thread2 comes in later。Later。5 is going to point to seven。

And servant's going to point to what？10。And what just happened？We just lost an insert。

And as it goes in the other order that could happen too。

 so it kind of depends on which one we want to say wins。

 but assuming thread one updates previous next before thread2。

Then thread two is going to end up winning。So I just lost an insert。

Let let's say about another case how about one insert and one delete。

 so let's say thread2 is trying to delete 10， so thread2 is like oh okay， I want to get rid of 10。

 so5 needs to  point to 11。But。That's kind of interesting because five。

 according to thread1 is pointing to6。Which is pointing to 10。

 which is deleted and might no longer have a valid next pointer at all。

And now of this time I've lost the rest of my list。

So and then we could do some similar things with simultaneous deletes。

 you know simultaneous deletes you might get a double delete。

 you might actually delete memory that's already been deleted。

 so if I go back to this code and I said in the spirit of do the simplest possible thing to make this correct。

😊，What would you do？Yeah， the back。Can you tell me where you put the locks？Okay。

 so what you're going to do is're going to put one at the beginning of insert and want at the end of insert and then is that it？

One more to the beginning of delete and the end of delete。Why is everybody laughing？Is good。给我。

It works， see you sure。Are you sure it works？Look closer。

Even the simplest co grain locking is busted。ていうこと。Well， yeah， yeah。

 we're assuming it's the same walk。 Yeah， yeah， that works。 a little closer。I claim deadlock。😊，Now。

 of course， if you used one of these like unique locks and C++ that automatically unlocked when out of scope you define。

 but this is just like a little example of even something as simple as throw your locks globally around everything with multiple exit points from a function can kind of get you。

 okay。😊，So， you know， if I had to jump forward， you like if I had to be careful。

 it would look a little bit like this， exactly， it was the same spirit of your solution。😊，对。

So what's good and what's bad about this， what's good is clearly that it's correct now， what's bad？😊。

I the entire access to the data structure is serialized at this point。

 and that's going to be trouble why I even spawn these threads in the first place， right？😊，Good。

 okay， so that's， that's not， you know， May limit parallel application performance。 And well。

 if most of your performance was in the data structure， it's going to definitely limit your action。

 You may not care if most of your your。I don't know what's going on there。Okay。

 so what I'd like you to think about， you don't need to see the slides for this。

 I'll bring it back up in a second as soon as I is how would you do better？

So talk that over for a second。So clearly， different parts of this data structure can be edited at different times。

Okay， so just for the sake of making sure we get through everything。

I mean I am not surprised people are still puzzling over this。

 I should probably give you at least five minutes to try and figure something like this out。

 by the way on exam one year I decided to do this for a rotating binary search tree and it was hard。

😊，I promise I won't what's the gist of some of the stuff that you're coming up with so first of all。

 I think it should be clear that like I should be able to do some insertion or deletion here while another thread is working on another part of the list like the data structure should definitely afford that。

😊，What are you thinking about and how you might accomplish this？

I think probably like a lock on a per node basis so many who's had a lock play a drop okay so let's throw a lock in every node now so there's no total list lock anymore there's a lock per node that's okay so that's a reasonable start and now the question is is what's the order that you would take those locks to make sure that things were okay Like let me give you a starting example One example would be I'm going to take a lock on three。

And then I'm going to release the lock on three and put a lock on five。

And then I'm going to release the lock on five and put a lock on 10。That's one，1 example。

 Another one would be， I'm going to lock 3， and then I'm going lock 5。

 and then I'm going lock 10 holding all of these locks， and then I'm going to do my thing。

 and then I'm going to release the locks。 So like， how did you。

 did anybody start discussing like like a policy for how you might。

Maintain as much concurrency as you possibly could， but also still got to be correct。

So's like what about my simple example of let's take a lock on three， let's release it。

 and let's lock five， and then let's release it and let's lock 10。Yeah。Okay， so if I lock three。

If I release the lock on three and I don't have any locks。

That's the moment where I know nothing about the data structure anymore。

 right like that means that by the time I go to5 it might be gone。

So there can't be a situation where we have no locks。

 otherwise like that's definitely going to be trouble So if I'm holding the lock on three。

 what do I know？Nobody else has a lock on three。 So that's true。

 How can we use that information to have guarantees。

So if we lock three and then we lock five and three。

 well we certainly know that nobody has got locks on three or five。

And then we also know that nobody has locks on five and 10。That's helpful。

maybe you only need to like walk the nose before and out to at。

So there should be some notion of I only need to keep the locks on the blast radius in some sense。

 right， like I only need to keep the locks on things that，If someone else modified。

 it would cause me a problem。😡，And so the real question is how many walks is that here？😊。

So one way in this diagram， this gentleman on American Angel warrior。

 he's on the overhead bars and so this idea that if we ever lock and then unlock and then lock again。

😊，That is deadly， that's like basically what happens if he's never holding on to at least one bar？

Gavity takes over it's not going to work， but he's doing the thing where he's making sure he's holding on to at least one bar at a time and the question that we have now is like how many locks do we really need？

😊，So here's a scheme that embodies this hand over， hand locking idea where I'm inspired by what you're saying。

 I'm going to take the lock on three， and then I'm going to take the lock on five before。

I release that lock on three。And then what do I do， oh yeah， I'm deleting 11 here。

So I need to keep going， right， so I need to take that lock on 10， release it， take that lock on 11。

Okay。And at this point， these are my threadread Ze's previous pointer and current pointer in the linked list Traversal。

So should I release the lock on 10 and then delete 11？No， what's the motivation behind that？

So if I can I'm only deleting 11， so why do I care about 10？So I need to modify 10。

Right and so since I'm going to be modifying 10， what am I worried about？That next pointer of10。

 well really what am I worried about some other threat doing？Another thread could delete 10。

 what if another thread inserts after 10？Yeah， so to delete。

 I want to make sure I always have a lock on current。And previous。Okay。

And so let's say if thread1 comes in and wants to delete 10， why are we protected？

Because if the rule to delete is I have to have a lock on the thing to delete and the previous one。

 I know that nobody is deleting the previous one， why？Why can't T1 get in there？

Because I have the luck。😊，Okay， so why am I not worried about someone deleting 18？

Why don't I need the one in front of me？So if I have a lock on 11， nobody can be deleting 18。Okay。

So why am I not- now let's think about insert。If I have the lock on 11。

 how do I know that nobody's inserting？After 11。给掉了吧。Because I'm going to have a lock on 11。

 how do I know that nobody's inserting after 18？😊，I don't， but I don't care。

Because it will impact me。So this hand over hand， 1， two， one， two，1， two，1， two。

 always keeping a lock on previous and current is actually going to work out here， yes。

The way insert was set up， if you had， I don't know。

 threadt2 come in and start a preio effect one in this case， would it be simply blocked and like？

This operation was to insert after， but it started after these two operations it stuck that's correct。

 so that that's a night so this is not necessarily。Maximum concurrency， right。

 because I have a thread2 coming in and let's say this is like way down the list。

 or actually let's say it's a really long list and this is happening at the beginning。Thread2 T2。

 which is not on the slide， is not going to be able to get past these。😡，And get ahead。

 even if it's going to operate way over here on the list。

 and why do we have to make sure that it cannot pass things up？Because while it's traversing。

these T1 or T0 better not be deleting those nodes that it's traversing or inserting actually in places。

 right because we can lose the list with with inserts and stuff。 So， yes。

 like a linked list is a very sequential data structure in some ways。

 And unlike some other data structures， you don't have as much concurrency in it。😊，Now。

 if we had a guarantee that T 1 and T2， T0， we're not writing to this portion of the array。

Then we could think about it， like we could think about a different lock type that was like allowed multiple readers or something like that。

 but we have not discussed that here in this class today。😊。

All right so here's the handover hand locking solution for this program there's actually a few kind of tricky invaris in that like what I actually had to take a there's actually a lock on the list as well as a lock on the node。

The point being is remember our invariant is I need to lock on current and I need to lock on previous if you're deleting the first node you kind of you either need a dummy previous or you need like an extra lock somewhere else。

 so this code is correct， there's actually ways to make it slightly more performant where you more aggressively unlock things and I'll leave that to the class to sort out on the discussion board。

Okay， so this is a， you know， good， you know， just just different things that you might come up with。

 like incorrect。 you actually could end up deadlocking。

 It's hard to deadlock a little bit in a link list because it's kind of one directional。

 but and then there's like the cost。 Like now imagine like remember your cost of a link list was like just chasing a pointer。

 now you're taking a lock on every step。😊，That's going to slow things down big time， right？

So it may be the case that that big course lock might actually be better， like limit concurrency。

 but get done quick。So who knows you'd have to perform its profile if it turned out that taking a lock on every step to the list was too much。

 what are some ways that you might sort of what's a middle ground between a lock on everything and a lock on。

Every node。Yeah， you could like say I'm going to take a lock for every five or 10 nodes or something like that exactly so you can play on so on your own time。

 a very good exercise would be let's just go with a standard binary tree。😊。

And a binary search tree and out try and write the code yourself。In and delete on a binary tree。

No rotations or anything like that。Okay， so I want to hint at one more thing that is not going to be on your midterm。

 but we'll bring it back for the final a little bit is how to make concurrent data structures that are thread safe but don't use locks and you've already seen one example of it in class Atomic min。

 I think you said just use locks right and I was like。

 well no you can't use locks that compare swap implementation is an example of a primitive that is safe。

But does not use locks。 And the main idea was to say， I'm going to。Basically， speculatively。

Go forward with whatever operation I'm supposed to do。

 and at the last second I'm going to check to see if something's changed。And if something's changed。

 I'm going start all over again， right， And that's different from locks。 Lock say， I'm when I enter。

 nobody else can go。In this lock freeway of thinking， your idea is to say everybody goes。

 but everybody can check at the last second to see if things are safe。😊，And if things are safe。

 they do their right， if they don't， they sort of abort and try again。

That's the big idea of walk free。Okay， so and one of the reasons why people are so were lot free is。

😊，People talk about it， I think a little bit more than necessary。

 but like all of your concurrent collections in Java are Lockfr implementations， for example。

 and I want you to think about a case that in our class。

 most of the code you write is your application runs is the only thing running on the machine。

 you're using parallelism to run really fast。Imagine you're writing some big database or some web server and there's hundreds of thousands of threads or something like that。

 concurrent threading is being used to hide latency of network traffic or something like that。

 not necessarily parallelism imagine you take a lock as a thread。😊，And then you get swapped out。

By the OS， you get context switched out all of the runable threads are sitting there spinning or trying to get a lock。

And the thread that has the lock just got swapped out in its critical section。

Those are the types of examples that really motivated lock free data structures because just because you have the lock。

 if you are not doing anything， you know somebody else should be able to come in and do their thing right And so that's the difference between blocking and non- blocklocking everything that I've shown you in this lecture so far has been except for the atomic cast stuff has been blocking meaning that if you can't get the lock you just stop And now everything I'm going to talk about is you just run forward and hope for the best and that's what lock free algorithms are called。

 So let me give you just one simple example before we here's a queue。

 this is very much like a queuee that you would write at a Microsoft interview again this is like a big And so I'm implementing a queue as an array and as you push you increment head as you pop。

 you increment or as you push you increment tail as you pop you increment head。😊。

And imagine you're doing it with just two threads。The pusher thread is just incrementing the tail。

The poper thread is just incrementing the head。So you don't have two threads ever accessing the same variables。

 and this code is thread safe with two threads。And I'll stop there。

 I don't want to hold you any later， but in the slides what you'll find is you'll find- I give an example of how to do that with allocation with like a queue that's implemented as a linked list and I give you an example of a stack。

😊，So the idea of a lock free stack is you try and pop， you do all the stuff to pop。

 and again at the last second you check to see as anybody else popped and if nobody else has popped。

 which you can detect with compare and swap， you just go ahead。

And the nice thing is that if you're in the middle of a pop and you get swapped out。

Then all the other fededs come in and they just do their pops and when you get swapped back in and you complete your operation。

 you will detect that the world has changed and you just try again。

So these lock free data structures are designed for highly concurrent situations when there's a bunch of different threads and tasks on the same machine to try and get around some of the problems that can occur in a blocking situation where you have mutual exclusion。

😊，So I just want you to know a little bit about them。

 we're not going to talk about them too much more in the class until we get to the modern day version of all of this。

 which is transactional memory。😊，Okay， I'll let you all go， sorry for going a little bit over。



![](img/4bf6548ae8b81faaf2fb5bfc2a084805_4.png)