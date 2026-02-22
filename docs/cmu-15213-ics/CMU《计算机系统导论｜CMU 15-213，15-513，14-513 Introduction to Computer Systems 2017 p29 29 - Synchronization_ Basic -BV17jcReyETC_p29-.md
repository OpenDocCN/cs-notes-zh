# CMU《计算机系统导论｜CMU 15-213，15-513，14-513 Introduction to Computer Systems 2017 p29 29 - Synchronization_ Basic -BV17jcReyETC_p29-

下很完全。ざま。恥かしい。

![](img/47b3b23d1b80b0185e1fe30c7f4bb4e2_1.png)

![](img/47b3b23d1b80b0185e1fe30c7f4bb4e2_2.png)

はは。Okay。I'mWhen I first got here， this room was nearly empty and I thought are people still writing their meic code。

 so glad to see that。At least if you are that you took the time out to come to a lecture。So。

Last time we started talking about multi threading。

 which is what I said is I think this is one of the。Places where this course really goes into some。

Really key ideas that will be very useful to you in many different respects。

And last time we just talked about the basic principle of threadreing。

 but all we were able to do is create code that did weird stuff and didn't usually work right。

 and that's because when you have concurrenrtency you have to have some kind of synchronization。

 some way of coordinating the actions of these independent executions。

And that's what we'll start on today。So just to remember。

 last time we talked the sort of basic idea of multi threading。Why is that？

Normally we think of a process as just one single execution context。

 one single sequence of program execution。And that we thought of concurrency as something that happens between processes。

 but the idea of threading is that you sort of take the normal view of the state of a process。

 which is namely the things that are stored in the virtual memory system on the right and all the other stuff on the left virtual memory has the execution stack for the process has any code that's being executed。

 global data。And the heat。And then over on the left。

 the pink stuff is what's normally held within the CPU， the actual registers。

 including the data registers， but also stack pointer condition codes program counter and then this green stuff what we call the kernel context that's actually in the virtual memory。

 but in a part of memory the application programs aren't allowed to access。

 and it's the stuff the operating system is maintaining on behalf of the this particular process。

 So it include the。The page tables， the various information about open files and things like that。

And then through a little bit of what I call the magic of PowerPoint animation。

 we consider rearrange this all。To be a little bit different organization and think about the stuff on the left。

Is what really controls the process itself， the state of the。Low level execution process。

 so the registers and the stack and the stuff on the right are sort of things that are shareable。

And now the trick is with multi threading， what we'll do is say， okay。We can have a couple of those。

Effectly， an arbitrary number of those what we'll call threads。

 and so each thread is like its own little bit of execution。

 it has its own set of registers and its own stack。

And it can execute so you can have multiple literally threads of control running within a single process。

 and so you get concurrency within a process， not just between processes。

As you would in a traditional view。And it's critical this idea that each one has its own stack so that it can be calling functions。

Haveve its own set of local variables and so forth so that they can run somewhat independently。

 but they're sharing a vast amount of stuff they're sharing， for example， the code itself。

 as well as the global data， including both the statically allocated data。

As well as the stuff that's been allocated via Mal and other。The dynamically allocated data。毕。

And so this is。Interesting in a couple of ways， we saw last time the value of having concurrency to handle things like external events so we could have one server managing connections from multiple。

Clients， but also nowadays with multithreaded with multicore processors。

 it's possible now to write a program if we're clever and try hard enough that one program will become a process but it will have multiple threads each of which is running on a separate core and therefore is able to get some of the parallelism out of the system and that will be discussed a little bit in the lecture one week from today。

But now that it's sort of an interesting question is what does sharing mean in a threaded program。

 what data are shared between these different execution contexts？

And there's a sort of simplistic view as well， gee。

 the things on the right hand side of this picture。The stuff。Basically in the heap。And the。

Statically allocated data。That's clearly shareable between the different threads of control。

 but just because it could be shared doesn't mean it is threat。

And the other thing to keep in mind is even though we show these stacks as being sort of associated with their individual threads。

 they reside in virtual memory。And so it's not so simple as you can't just point to some part。

OfThe program and say， oh yeah。 that's shared。 No， this is private。

 You have to actually look at the code in detail across the whole， the whole， the whole program。

So what we'll say is a variable is shared or some。Going beyond a variable more explicitly。

 some region of memory。I shared if multiple threads have some reference to that。

And so what does that mean， well let's look in detail。So like I said。

 you can think of this model as each of the threads has its own private state。But the reality。

 and that's sort of the conceptual model that we mostly think of。But the reality is that。

These stacks of the individual threads reside in the virtual address space and there's no protection。

Among threads of which ones can access which parts of this address space。

 it's all mapped into the general。User accessible address space and a pointer， as you know。

 is just an address。 It's an address that you can store， you can store it in a register。

 you can store it in some other part of memory， but a pointer is just an address。

 and so any thread can hold a pointer to any other part of the memory。

So it's entirely possible then to have pointers that are going all over the place。

 so as this picture shows it might be that one thread has a pointer to some variable that's part of a local variable for some other thread。

So that's。Again。Because that stack is in memory。 There's nothing to prevent it。 It's possible for。

One thread to have a pointer。To the。That's stored in one of its local variables。

 that's pointing to some other local variable in one of the other thread stack。

It's possible for and quite common， in fact， for some data that's held in a。

In one stack to point to some of the global data， and it's possible even to have a global data structure that has a reference to some local variable and some threat。

I mean， there's nothing that prevents this from happening。 it may or may not be a good idea。

But but the it's inherently possible， so these sharing possibilities are all totally。

Totally supported by the machine。 There's nothing to prevent it。

And that can give you some sort of peculiar。Behavior and。

Remember that there's sort of a general principle in programming that even if you can do something。

 that doesn't necessarily mean it's a good idea。I'll show you some examples here and don't ever say。

 well， we saw this in class， so this must be okay code。No。

 we'll be showing you some very arcane code that purpose is just trying to illustrate a point not being a good idea。

So with that in mind， let's look at this program， which is。Really quite a。

Quite an artificial example。But the point is here this code will be the code for our main program。

 and we'll just refer to that as the main thread， but remember one of the features of threads is that they're all kind of considered equals among each other that there's no inherent hierarchy in threading like there was in processes。

Anyways， you'll notice it within this。Main program is a global variable called PTR。

 but it doesn't actually have any storage allocated to it， it's just a pointer。

A pointer to a care star。And within Maine， then this message is a local variable。

That references two different constant strings， so it's an array， and you'll see in this code here。

That it assigns messages to PTR。嗯。Remember， that's not a copy of this array。

 it's just a copy of the pointer。The which is really the address of this array called messages and like I said。

 this address since it's part of the local state of this。AThread will be on the stack。

For this threat。And then we'll fire up some threads and I want to。Explain a little bit here。

And then waiter will'll see that each thread program then is referencing the global rape PTR using an ID。

So first of all， I wanted to point out that there's。A trick in here， which。People do。

 I don't know if it's considered bad form or not， but it's a reality。Which is。

 remember last time we talked about if you want to properly pass an argument to a thread。

 you need to mount a little space。Store the thing there and then have the thread， extract the value。

 and then free it。that's true。But the quick and dirty thing is to just say， you know。

 I'm allowed to pass an 8 by worth of information to a threat。 It's supposed to be a pointer。

 But what if I just sort of take my long。And just。Cast it to a pointer。You know。

 a fake pointer and pass it to the thread and the thread knows I'm doing this too。

 and it will just cast that back to a long。So it works。Is it a good idea， I don't know， people do it。

And you'll notice it's one of the nasty things， though， that if you're on a。

You should match the size of the pointer to the size of the data that you're passing。

 so you should pass longs this way， but not ins。If you do， it'll give you some， it'll squawk。

The compile well that you're casting to a different data size。

So it's just sort of a dirty trick people play， I don't know。I'm sure it violates various standards。

 but you'll see it。So anyways， that's what this business here， this void Star eye。嗯。Okay。啊。

And like I said， you can see that both messages and the thread are referencing this global variable code pointer。

So let's look now at these different types of variables and whether they're shared or shareable or not。

 so we'll say that a global variable is one that's defined outside of any function in this example。

 say PTR。And you know that that it ends up in the region of memory that's allocated for that。

And in general， then if you look at the。No matter how many threads there are for each global variable。

 there'll be exactly one copy of those。Similarly from local variables are ones that are declared within a function。

 but don't have the attribute static associated with them。

And there each thread will have its own local copy。

That's why they're called local of a local variable。

And so potentially there'll be as many instances of that variable as there are threads if they're all running the same code。

And then there's this slightly funky one that。actually is。Kind of like everything。

 There's always a weird case。 And C， I don't know if we've really covered this much。

 but it's possible to declare a。Local variable to be static。

And what that means is it's shared across all instances of this function。

And what we talked about it briefly in linking， that it means that it's really sort of like a global variable except that only the function that it's declared in can access it。

And so one curious thing is now when there's multi threading and you have multiple。

In multiple instances to this function running simultaneously。

 they'll actually all be sharing that single variable。

 so it's sort of like a it really is like effectively from execution perspective。

 like a global variable。So given all that we can see in this code。

 we can sort of break down all the different variables in here and figure out。

Which ones is there a single unique copy or are there？Several copies。So in particular。

 we see PTR as a global variable。嗯。Within mainine it has I and T ID and MSGS。

 those are all local variables and well we'll give them the name in this illustration will'll say I do M meaning the。

Variable I in the code for the main threat。And similarly， within the threads。

 which we'll call the peer threads， even though at some level， they're all peers。

 but Maine is sort of。First among equals。So we'll call these other threads， the peer threads。

And my ID while being local， they'll be on their own stacks。So there'll be two of those。

 one for each of the two different peer threats。Just to kind of add to the fund here。

 we introduce this variable CT count that's declared as static。

 so that will actually be shared across all the threats。We don't really do anything。

 we increment it in this program。Oh， and we printed out the value， so we do kind of use it， but。

It's more to illustrate a point than doing anything useful。

So we can kind of break this down and make a table then we can say these three threads。

And we have these various different variables， are they referenced by which threads， so for example。

 PTR or global variable we saw is of course， truly global。

 meaning it's used all three of these execution threads run it。What about CT？Yeah。No。Good， and right。

 and the point is it's sort of like I said， it's like this。Effectively。

 from an execution perspective， treated like a global variable。What about I？じ。Right， thank you。MSsGS。

No， it's getting interesting， yes。Yeah， so even though the variable is declared and local to。嗯。Main。

The fact that it's。Reference via this PTR。know it's just a copy of the pointer to this array。

 so it's effectively used a reference by all three threads。

 and so this is an example of there being a pointer making use of the fact that pointers are pointers and you can point to things in the stacks of other threads。

What about my ID？什么意见？语文。So this one is a local variable。

 each instance of it is local to a particular thread。That it's declared it。

Even though we're we're using it to pass an argument from the main thread， but it's local variable。

 It gets created and only used and never shared outside of that。questionestion。没了。这CCMT the maybe。下一。

いうことです。Well， but there's a difference between it could。那我。

It could be reference versus it is reference reference， I mean， it's either read or written。I mean。

 it really is。It couldn't actually be because。At least you'd have to create a pointer to it artificially to do it because it exists in the main。

Data for the program。But because it's declared within a specific function。

 it can only be referenced within calls to that function。

Static is it's a feature people use sometimes if they have like an initializer that they want to create。

 but it's not a very common trick in C。That's not the more important thing， the more important thing。

The share。Stack variables across threads。Yes。exit is that attached the two threads？Pre， you know。

 this is weird code to have put that Pe exit only exits。That particular threat。ですね？Yes。

 which is name。So this is a sort of strange way to。I would not like code。一。Actually。😊。

I don't know what it would do。m in terms of the threat， because as I've said。

 heat thread exit usually only， if you call the normal exit。From any thread。

 it will the whole program will exit all the threads will stop。

You call Pe threat exit or normally await。Exits from that particular。对。If Maine returns。

It will effectively what call global exit。But it's not returning here， it's calling P threat exit。

 So I believe what would happen is。That these threads if they were still there would potentially stay alive until they're done。

But that's a little bit obscure。This isn't really a very good code。

 we're not trying to illustrate that。Okay。It's an interesting question。Also， as you know。Actually。

 you're supposed to also say return a value for May it returns a hit。So not beautiful code。

 but it wasn't intended to be anyhow。So。The point being that。

This idea of sharing what we mean if the program is referenced。And we'll call it a variable。

 but some value in the program is shared if multiple threads reference at least one instance of it。

So we'd say PTR， CNNT， and MSGS are all shared I and my idea are not。嗯。So we said now that， okay。

 that tells us something， but what are we supposed to do about it？How can we understand that？

And so let's drop down at a kind of lower level and understand exactly how these curious interactions occur。

 So this is code that we showed last time。Where the。There's a global variable CT for count。

And we have two threads that are just。Of。Over and over。

 repeatedly just trying to increment that variable。And what we find。Is that when you run it， say。

 with an argument of 10，000。It should sum to 20，000。嗯。Because。There's two threads。But generally。

 it does not， it comes out something less。And so let's look a little at the code。 and by the way。

 one of the curious things is if you。Take away this volatile。Then it always returns 20，000。Or。

It returns the correct number， and we'll talk about that in a minute。

But let's just keep that volatile there and we'll get back to why that's sort of part of the whole picture。

So let's look at the assembly code for this。And what really counts here is the code that。

That is in this。Part of the loop that is incrementing the value of CT and what we said is you can think of it as as three different steps。

 one is a load meaning to read。From memory， the sc variable count and store it in a register。

 which in this code is in RDX。The other is then to increment register RDX。

So we'll just call that the update and the second is to store that register back to memory。

 so this is the critical part that it's sometimes called read modify write that you're reading out of memory。

 you're modifying that value and then you're storing it back so we'll use the initials L and S for those。

And then the rest of the code we'll call the head no tail that's not really so interesting。

So the observation is depending on how these threads step through these different pieces of this code will affect what happens to this global variable count。

So here's an example where first we're sort of interleaving that first。

Thread one goes through the load， update and store of count。 So count is initially zero。

 so now we read that into the register。 we increment it。And then we start back。

And then thread two is doing the same thing and itss copy of the register， so it's reading。

 incrementing。And writing it back。And so what will describe those and that gives us something that makes sense we've had two threads each do two increments。

 we increase count by two。So what we'll do is we'll call these little regions of these three instruction sequences a critical section。

 meaning that as long as they're executed without anything in between， then life is good。

But if we do one where we interleave these two critical sections for these two different threads。

 we can potentially get something that goes out of whack。 So here， for example。

We read zero out of count。And then later。We incremented it， and then later we went to write it back。

But。In the meantime， we've also read。In thread2， the value of count and it hasn't changed yet because this second this first update hasn't。

这。Been stored。 and so it just reads zero in and it goes and it increments it。And it stores that back。

But it stores back what it thought was the incremented count。

 not what the global variable count should be， and that's why you get these that the bad count is always less than the correct number。

 not more， because basically some of these increments are getting，嗯。

Failing to have the effect because the other thread is instead sort of overriding it using still data。

And so that's the source of it。So just to go back to my point。Anyone know what volatile means？I mean。

 not just。You know， this person this。Liquid seems very volatile， yes。Yeah， that's one version of。

 So D RamM is not is volatile， and SM is not involved。 No， I'm sorry。Flash memory is nonvol。 Yes。

 that's one version。 Volunat means a lot of stuff。 But in C， it has nothing to do with that。 And C。

 it means。When I say this is a variable， I mean， put it in memory and when I say update it。

 I mean really update it。As opposed to stick it in a register and do whatever you want。

So that's actually an interesting thing here， and you'll see and when people write threaded code。

 they throw volatiles all over the place。What would happen otherwise？

Is that the C optimizer has absolutely no concept of threats。It's sort of designed and all the。

All the tricks it plays are basically under the assumption that you're running。

 you're the only thread that's going to access or execute this code or do this。

 it has no provisions built into it to support concurrency at all。So。What happens is。

This code compiles。Where CT is just held in a register。And。

Probably some clever C compilers even figure out， hey。

 I know it happens if I increment a value n times， I get the value n， so it just turns it into n。

 but even if it doesn't， it'll just stick in code to just increment a register over and over again。

So and then it will at the end， it will store it back in this global variable。

But it sort of has that built in optimization because it does this analysis here and goes。Hey。

 you know read if this is the only thread in the world。Than if I increment count。

If I were to write it and then read it back， I'd get the same time。

So the volatile is what you have to do as a programmer to。

When you're dealing with threaded code to sort of force the thing to say， no。

 I really want you to use sharing between different threads。You have to write that。Yes。らです。

20000 back for one。They'll come back。I think you could get either right in all the cases I tried。

 it always came back。20，000。And I think what happened is the scheduler， the thing happens like this。

 And the scheduler just said。This guy seems to be running pretty well which just got it go。

 and then it scheduled the other one。So in other words。

 it didn't try to inter the scheduling of those two because the code runs so fast。

But you could potentially， you could imagine， especially if you fired up a bunch of these threads。

And had this big multi corere processor that you'd get some。Something less than。

It would be a multiple of 10，000， but it would be not the full， it would be an interesting。

That's a good question。So that's just a little obscure point。

It is important that if you really need to be。And C。

 and the same goes if you're writing code that interfaces with external devices and things that you have to throw volatiles around。

To really tell explicitly tell the C compiler that don't just hold this in a registry。

 put this in a place of memory that it can be reliably updated。Oh， sorry， Ive jumped ahead myself。嗯。

Well。This was supposed to be something you figured out。

 but you see the trick that it's the same deal again that。嗯。The thread1。Took place and within that。嗯。

Thread2 took place。But you end up with the same idea that。They're both sort of。

They're not thread two isn't getting the version of count that thread one is supposed to have increment。

So in general， anytime these。嗯。The loads。And the stores get sort of interweaved on these。

 there's the potential for a problem。So there's a kind of cool visualization of this that's used in the book。

I can say these things because I didn't write this part of the book that lets you at least for two threads kind of understand in a pretty interesting way what's failing here and when when we fix it。

 Y that's a fix so imagine the progress of the two threads being on the X and the Y axes and as you saw each one goes through some initialization H。

 then the load， the update the store and then the tail or the final part and it's really the L un andS that's interesting。

And so at any point， the program is going to start down here and it's going to finish up there。

But potentially， it can kind of wander。Along any what you'd call Manhattan path from along these parts。

 right anywhere that's in general， going upward into the right。And so we'll call that a trajectory。

So if the trajectory sort of wanders around。嗯。Then we can see whether it some trajectories will be good and some will be bad。

 assuming good is that we want count to be increment by two。Is itAnd we'll refer to then。So anyways。

This was an example of a bad trajectory， in fact， because you see that we did the update here。

But we haven't stored it， and meanwhile we did the load here。

So this one will end up in a not incrementing count by two。So we consider。

I'll map out this little region in here that fits within that particular set that we'll call the unsafe region。

 meaning if a trajectory kind of veers into that pink area， then it will do something bad。

And so just as illustrations。If say thread2 sort of gets far enough along， gets its load and update。

And its store。So it avoids going into the region you'll see that now I've。

I've completed the updating of count by one。And now thread one can do its load。An update and store。

And then increment the count by another。One， and end up here that I've gotten the correct result。

So we'll call those safe trajectories。One it don't go into the unsafe region。But on the other hand。

 if we had one that crossed through this region， you can see it's not safe because it's again。

 like we saw。It's one we've already seen that we did the load and the update。

 but we haven't stored it yet， and meanwhile we do the load here。

 and so we're not getting the updated version of the count yet。

And so this one will only increment count by。By one。

 and so that's called an unsafe or incorrect trajectory。So anyways， this kind of trick。

You don't see this in most presentations， but it's really a very interesting way to kind of visualize what are good and bad execution sequences。

And so now getting back to bad count， what we'll see is that。This is a shared variable count。

Across the main thread and all the other threads。This code， by the way， I was looking at it， going。

 oh， no， we said， don't do this。 So remember， last time we said。

Don't just create a pointer to a local variable and pass it。To a thread routine， right。But this one。

 it's okay， why is it okay？Do guessい。Yeah， but if you remember the last time。We did that。

 we still got problem， it's actually a simpler reason than that。

Yeah don't not any entrieseries is the same for all。But this is normally。嗯。

I would not be happy if one of you submitted code that did this。And more important。

 the Ts would not be。Because they're the one in signing style for。嗯。But anyways。We're not trying to。

Enforce good practice here in these examples。But the point is it has exactly this problem that we saw。

 that it has this potential and nothing preventing it from hitting these bad trajecties。Okay。

 so now you get to try this as a quiz。

![](img/47b3b23d1b80b0185e1fe30c7f4bb4e2_4.png)

Yeah。

![](img/47b3b23d1b80b0185e1fe30c7f4bb4e2_6.png)

No， this code doesn't do this is still the bad code We'll fix it after you're done with a quiz。



![](img/47b3b23d1b80b0185e1fe30c7f4bb4e2_8.png)

![](img/47b3b23d1b80b0185e1fe30c7f4bb4e2_9.png)

![](img/47b3b23d1b80b0185e1fe30c7f4bb4e2_10.png)

What that。It's still locked。Oh， it always starts at 220。Sorry about that， thanks for telling me。

Let's see if I can fix that。いち。Try now。一ありです。这る。It's still 220。Okay。哼。不真。Think this will do it。对没有。

Thank you。How's that。I'm really proud of this， I made it up for you yesterday。Yes。Okay。

 let's take a look at this code then together。 So this was an instance of。Basically。

 how can I come up with the most obscure code possible？And I think I did a pretty good job。

So it's vaguely like the idea that was shown before， except a little bit funier。

And the main point of which is。Oops。Does it work。I'll just point to it。This part here where it's。

Thatからこう。Assigning to a global variable pointers， which are long stars。呃。

The reference to the local variable， My Id。 So effectively， we've created。From the main。

Global memory。Pointers back to the stacks of the two threads， the two peer threats。And so now later。

 when the main thread。Prints out star pointers of I。It's。

Remember as an array in global memory that are pointing back to the two threads。

But they're to local variables in the stacks， those two threads， so the main is referencing them。

The two threads aren't really talking to each other。

 but that a main and each thread is effectively sharing this variable。My idea between them。

And so that's the main trick。So one is， I think， true。2。Its fault。嗯。Well。

 one is true because it's pointers， right， it's obviously a global variable， two is faults。

 they're the peers aren't sharing with each other。好。But they are sharing with the main one。

 so three is true。There is a race condition passing the value I to the pure threads。

 This goes back to that hack I showed you before that you see pretty common way that。

This isn't like the one we talked about last time。We're not passing M percent I， we're passing I。

So we're taking in numbers。It happens to be eight bys and we're kind of jamming it and saying， oh。

 it's a pointer。And then the thread is saying it's not a pointer， it's a long and it just grabs it。

 so good way you can think of。We're using a fake pointer to pass an argument。And then finally。

 so there's not a race condition there， but you'll see that。

I wanted to do this before we've actually talked about how to synchronize。

 so there's no synchronization here， so I use sleep。

As this very crude way to kind of control the ordering of events here。So， you see that。

Assume that all three threads get fired up and they'll be basically a contention of which one goes first。

 but within a few milliseconds at the worst， all three threads are going to be running。

And so if I sweep for two here， that gives enough time for this variable to stay alive， myi。

 the thread will still be alive when about halfway through it execution， the main will will。

Complete its sweep and be able to reference these。 So basically， both of these sweeps are important。

 and it's sort of important that one sweep is longer than the other。

And this is really a terrible way to program， don't ever do this， don't ever say this is a good idea。

 but it just。It's in this case， pretty reliable， the difference between one or two seconds versus sort of execution times of typical thread activities is。

A huge。A discrepancy。 And so this will pretty reliably do that。

 And if we took it out and you can try this on your own if you want。

 But like if you take this sweep out， what will typically happen is you'll get a segmentation fault because this thing is tries to reference。

Part of the stack of a thread that no longer exists。 and the。

That memory will get reset basically to be no longer allocated within the virtual memory space by that point。

 so its saying faults。Make sense， yes。哦，我觉得应该是。if you take out the。Sleep1。The problem。

 the risk that sleep one has， it could because if。It zips through this code too quickly before the two threads have been created。

Those stacks might not be set up yet。Right， and so it's there's a potential for it to basically the sweep is to make sure it's sort of。

Not too early and not too late。During the the lifetime of these threats， yeah。B延就会19。Re。2 and3。Well。

 that would be wrong， if that's true。S。That's why the scores were so off。Let's just try it out。

 I'll just do this here。It's actually harder than you might think to get the correct answer so。

 let's just go。It could be。怎样？Good。Yep， thank you， sorry about that。



![](img/47b3b23d1b80b0185e1fe30c7f4bb4e2_12.png)

Okay， so anyways， that was an exercise that sort of repeated the same ideas that were just covered now finally。

 we're able to say， okay， now you know you need synchronization， but how do you do it？



![](img/47b3b23d1b80b0185e1fe30c7f4bb4e2_14.png)

![](img/47b3b23d1b80b0185e1fe30c7f4bb4e2_15.png)

And so there's various ways to do it。 What we want to do is enforce what's referred to as mutual exclusion。

 We want to make sure that。Only one thread can be in its critical section at any time。

And we'll use the sort of classic approach that are known as semaphores。

 and these were are devised by a Dutch。computeruter scientists named Dyktra。

 if you ever learned Dyketra's algorithm for a shortest path， it's the same Dyktra。He was。

A person could be incredibly annoying or charming， depending on his mood， I've met him several times。

嗯。So the idea is to introduce what's called a semapho。

 which is think of it as a variable S that is guaranteed to be non negative。

 and we'll say we want to do we'll define two operations， one is called P。All right。

 sometimes called。Wt and what we'll do is we'll。We'll check whether this s is non zero。And if so。

 we'll be able to proceed while we'll decrement S and proceed， but if not。

 we'll just hang there and wait until it becomes non zero。And some way。

 there's a counterpart operation sometimes called signal that allows you to just increment that value F。

 and if there's some other thread that's waiting on that， then it will be allowed to proceed。

So just to restate that， and the main point is S is never negative。

So you can think of that as P is like this little bit of code。

 it just sits there and waits in a loop。Arbitrarily long， as long as s is zero and then once S。

S is non zero， it will jump out of the loop and increment S。And。

And the V operation simply increments us and in doing that。

 it might well one of the sepho one of the。Other threats to continue。

And one really important part of this as these little square brackets show is this is done atomically。

 so in particular you're guaranteed。That nobody else can sneak in here。

 if you tried to write this just using normal C code。You'll find it's you can't do it。

 you have to see special constructs， both in hardware and supported by the operating system to make this work。

That it's really important that nothing else can come in here。 and so you know。

 all of a sudden I think I can go， but somebody else jumps in ahead of me。

 So this is guaranteed to happen atomically that。Ex if there's multiple threads that are hanging there waiting for the semapho。

And it gets incremented exactly one of those threads is going to get through。

And these P and V are acronyms from Dutch。🤧嗯。Which I think would be Probernon and Ver Hogan。で際。

My limited Dutch tells me anything。So but that's all it is， the main idea of it。

And so these are supported in。The P Reds library as semaphores。And they don't call them P and S V。

 they call them weight and post。And so in the CSAPP。 c， cAPP。h block of code。

 there's rappers that use the traditional。P and V for onsemophorees。

 but they're just wraps around the P threads operation weight and post。

So let's see how we can fix this with semaphores。 And you see the key thing that we want to do is make sure that this count。

嗯。Is done atically， meaning that。Exactly one。We think of that as the critical section。

 we want to guard that so that only one thread at a time can be executing it。

And so what we'll do is we'll use a sort of special case of a semapho， semapho in general。

 that value S can be anything。Not negative， but in this case， the value would just be zero or1。

 it's sometimes called a mutex mutual exclusionion。And we'll use the P operation as a way of。

Acquiring a lock。A mutually exclusive lock， and the V operation is a way of releasing that lock question。

そしてビる。Well， yeah。That's actually a really good point we'll get back to it。

 but remember parallelism is not good if it gets you the wrong answer。So it might be fast。

 but if it gets you the wrong answer， that's not a very useful program， right？

So sometimes it's necessary to do this。呃。And so what we'll do is we'll introduce a。

A some that we'll call Mutex。And we have to give it an initialization。What its initial value is。

So it's initially one， one will mean that it's okay to grab it's like a lock， the lock is available。

 zero means no， the lock is not available。And we'll just surround the increment of count by a P and a V on this Muech。

And sure enough， it works。But as was just observed， it does slow down the program。So in particular。呃。

The running on a shark machine with a million iterations willll find that it。

Slows the code down by a factor at 37， so not just a little a lot。

 it's a very relatively very expensive activity。And that's important when you're trying to make programs that run fast。

 but again， sometimes you just have to do it anyhow。🤧嗯。

And so one way to think about it this is we can use this progress graph to represent that where now we've added。

In front of our mode update and store and afterwards， the P and the V operations。

And so what we'll find is， and then you can map out as this program executes what the value of the semaphore variable is。

And the point is that。That。That74 variable can never go negative。So well， this。Is not possible。

 you see what happened here is I already did the P。On the semaphore here in thread one。

And then I'm attempting to do a P on this one， but that won't be allowed because basically thread one has this lock now and thread2 cannot acquire it until thread one releases it。

 so it's not possible for the program to move in that direction of that time。And。If you draw it out。

 and so instead it will have to go to the right， that's the only thing that's allowed at this point because thread2 is waiting。

So it's just hanging there， waiting and only thread one is allowed to execute。

And thread one will be allowed to continue through。And do its V operation on that semaphore。

 and only then will threadread one be able to continue？

So one way to map it if you map what the values of S would have to be in order to hit each of these different points in the program。

 you'll see that this unsafe region is guarded by because it's all minus one。

 and that's not possible for Smapho to be， so we sort of created this forbidden region a zone around the unsafe region that keeps the code on track。

So it's a pretty interesting way to visualize what's going on。

I'll just make a aside that this isn't in the book and it's not the normal lecture。

 but I couldn't help but talk about it。This special case of a binary semaphore is so common。

That it's called something， it's called in P threadreads， it's supported explicitly as a mutex T。

The only operations allowed are unlock and unlock and 99。

9% of uses I can think of for a semaphore are ones where Mutex is really what you want。

 and so you might as well use the special case instead of this more general semapho。In particular。

 you'll find it。The code looks essentially the same。And it works the same。

But it runs around twice as fast。So it's still almost 18 times slower than the bad count code。

So it's not fast， but it's not as slow as the more general seimopho code。

So that's just an observation you'll be using semaphos in the final lab the course。

 and you might as well just use。Autee taxes when that's appropriate。Okay， so。

That actually is pretty much all for today just to summarize then that it's really important with threads to understand this idea of sharing and it's not simply a local versus global variables。

 it's basically is their pointer， it is that pointer being used to reference George either in the main memory。

 the main heap or whatever or else in the。The individual steps。And。

We use very synchronization constructs， which the simplest is the semaphore to sort of control the mutual exclusion。

 and next time what we'll do is we'll talk about some other uses or semaphore for other types of control that are commonly used in concurrent programs。

Okay， Matt will take care of us for today， then。

![](img/47b3b23d1b80b0185e1fe30c7f4bb4e2_17.png)

![](img/47b3b23d1b80b0185e1fe30c7f4bb4e2_18.png)

![](img/47b3b23d1b80b0185e1fe30c7f4bb4e2_19.png)

这是这思。