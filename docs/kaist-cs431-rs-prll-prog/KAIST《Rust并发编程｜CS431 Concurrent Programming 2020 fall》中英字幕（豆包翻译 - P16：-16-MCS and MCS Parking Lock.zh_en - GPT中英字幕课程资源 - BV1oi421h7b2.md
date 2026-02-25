# KAIST《Rust并发编程｜CS431 Concurrent Programming 2020 fall》中英字幕（豆包翻译 - P16：-16-MCS and MCS Parking Lock.zh_en - GPT中英字幕课程资源 - BV1oi421h7b2

So in this video we are going to continue to study locks。

 so in the previous videos we studied spin lock， ticking lock and CH locks。

And today we are going to study what is called MCS lock and MCS parking lock。

So MC log is a variation of CH log in that， so it is the same， it is a linked list。

 but it is trying to take into account what is called numa nonun memory access。In CH log。

 one of the problems regarding performance is that the nose allocated in the in a thread is delocated by the next threat。

So if the log turns from a to B， then the node is allocated by a， and then it is still located by B。

So it is a little bit problematic in terms of performance because the memory allocator works better if an allocation is always stilld by the same threat。

 So MC S log is trying to do that。 All the allocations are stilld by the same threat， but。Yuben。Yeah。

 that is basically the。Motivation of this。M C S lock。So in this video。

 we are going to study the key ideas of。The those two。M C， S and MC S parking lot。So。

 M parking log is that。If it didn't acquire a lot， then instead of doing a spin loop。

 then it is just sleeping。So， the threat doesn't。Doesn't consume the CPU times more。

 It is just sleeping instead of looping and looping again。

 So because it is problematic for performance and energy consumption。 So instead。

 it is just going to。Sleep and operating systems will give turn to。Other。Other。啊。

Other thrusts that is basically the。Motivation of this all the MCs parking lot。

So now we are going to go to the。Go to the code。 So we are going to see the emphasis log。



![](img/c601eb537c652afd698b09f60225460d_1.png)

So。The node is almost the same with the CH log， it has a variable that is indicating whether the log is acquired or not。

And next is the pointer to next pointer。 basically， so the same， it is the linked of the nose。

 and each node is created by a thread that is trying to acquire a log。Also， we have a token here。

 token is just a pointer。 pointer to the node。And MC's log is always containing the tail。

 so it is a linked list and the log is containing the tail， so here is a figure at the beginning。



![](img/c601eb537c652afd698b09f60225460d_3.png)

The beginning。The tail pointer is pointing to the no value。So， it is the beginning。



![](img/c601eb537c652afd698b09f60225460d_5.png)

And let's see what happens。What happens if the。Mces log authority is trying to acquire the MC log。

 So it it is。No， at the beginning。And in the log function。If a thread is trying to quiet a lot。

It just note。And the note is that。The value is log。 value。 Theduct value is  true。

So let's create a node here。

![](img/c601eb537c652afd698b09f60225460d_7.png)

A is trying to log。听你 steel。A no pointer。And it creates a note。 No， this。

The locked value is true and its next pointer is no。So it is created here。



![](img/c601eb537c652afd698b09f60225460d_9.png)

Here the log value is true and next pointer is false。And then it is trying to swap the tail pointer。

Tail becomes ned， and pre becomes the previous tail。



![](img/c601eb537c652afd698b09f60225460d_11.png)

So okay， let's see what happens here。So know this looking like this。And after succeeding a swapb。

The node is pointed to by the tail pointer。 Luxe tail pointer。And then my。

 my pres are the previous tail， which is no。

![](img/c601eb537c652afd698b09f60225460d_13.png)

Okay， so far so good。And let's see what happens here。Oh， if previous value is nu， then oh。

 I succeeded in acquiring the lock because no one is there， no one is waiting for the lock。

 and I am the first who sought to take a pointer which was no， so I acquired the lock。

So that's the reason why it just returned。And when it returns， it returns the node that I created。

Always， my token is the node that I created。that is the。That is the thing。



![](img/c601eb537c652afd698b09f60225460d_15.png)

Okay， so so far so good。And。Mitocon is node。So far， so good。And suppose that。

A third A is still executing it itself。And now。A。Let's， let's say it is no day。Now， B is trying to。

Aquired a lot。When a is holding the lock。Okay， so the tail was node A。

 and let's see what happens if another thread is trying to acquire the lock here。



![](img/c601eb537c652afd698b09f60225460d_17.png)

![](img/c601eb537c652afd698b09f60225460d_18.png)

And it also create a node here。Not B。 It should be true and no。And now， as before。

 it swaps the value of tail。And。The prime becomes node A， and the tail becomes node B。

By swapping the value of the tail， the old value is assigned to Pro and the new value node B is assigned to tail。



![](img/c601eb537c652afd698b09f60225460d_20.png)

So first so good and now。It goes to a different branch。 The private is no longer or no。

N nano probe means that the log is held currently held by another threat in in this case。

 it is the threat A。Now。What it does is that。The it looks at the Pra pointer。Kay。Oh。

 you the there is a previous node， So I am assigning the pre pointer next pointer to me。



![](img/c601eb537c652afd698b09f60225460d_22.png)

Okay， so that is the thing。 So， okay， and now。Note a becomes。True， and would be。

So this is because we are assigning the node A's and X pointer as node B。



![](img/c601eb537c652afd698b09f60225460d_24.png)

In this line。And we're looping。Until the nose lock per is becoming false。

 So we set the next pointer here。So what did the this stand？

It hopes that the previous thread is going to unlock me。By reading my own note here。

 So we said that though As next pointer is not B。

![](img/c601eb537c652afd698b09f60225460d_26.png)

And when a calls a enough， then it is going to。嗯。Going to assign node bes a locked variable as a false。

So。Basically， is this what is what's。What's going on in this log implementation？

And let's see what happens if this a unlock function is called。Okay， so that's the good。

And let's assume that B is still working。 B is spinning here。 It is not finished here。

 It is trying to。

![](img/c601eb537c652afd698b09f60225460d_28.png)

Luck the function by looking at the。Looking at the。啊。Its own luck variableable。At the same time。

 conly， Note B is unlocking itself。So it first read the its next pointer。In if。It is。Not no。

 Then we are going to just assign the next pointer。 Next knows locked value as false。And then。

 it is going to。It is going to drop its own self。So。So， if， so。If we see this next pointer as now。

 then it is going to。

![](img/c601eb537c652afd698b09f60225460d_30.png)

A drive its own self， so。So in， and at this point。It read it's， itss note here。And。

No be becomes false and no。

![](img/c601eb537c652afd698b09f60225460d_32.png)

That that is by assigning。I mean。Here， see this store assigns false to node values。

 node Bs locked variable。

![](img/c601eb537c652afd698b09f60225460d_34.png)

And now， they locate。Note a。But before that， load the other node A and load B becomes false now。



![](img/c601eb537c652afd698b09f60225460d_36.png)

Okay， so fast so good。And。

![](img/c601eb537c652afd698b09f60225460d_38.png)

Yeah， and it is the end of the unlock function。 So a unlocks itself by。

By writing a value to this false variable。And now reason to B lock function。

 So B s function should return only after a unlock finishes。

So that is actually guaranteed by this implementation because node B's locked variable becomes false。

 and only after that B's lock function can break the loop。😊，And let's see the implementation here。



![](img/c601eb537c652afd698b09f60225460d_40.png)

Let's see the implementation here。 So here it is looping until its log variable becomes true。



![](img/c601eb537c652afd698b09f60225460d_42.png)

A false。And only after a un， it can break。And。Return after AM long。Finishes。Yeah， so basically。

 that is what's going on in this implementation。Okay。

 and now let's see what happens if B unlocks itself。

 So if there is a stress C that is also trying to acquire the law， almost the same thing happen。

 B A C is trying to acquire the law by waiting for B B to。Assign the my my locked variable to2。

On the other hand， if there is no such a threat that is waiting for。The threat too。



![](img/c601eb537c652afd698b09f60225460d_44.png)

I'll take the turn。Then the peaks unlock function works like this。 So unlock function here。

Is reading the node this is node B in for from the point of view view of the threat B。

Then it reads the next pointer。And it is no because there is no such a thread that assign the my variable。

 so。

![](img/c601eb537c652afd698b09f60225460d_46.png)

Tale was not B。And next is no。

![](img/c601eb537c652afd698b09f60225460d_48.png)

So， it goes to this。Oh， there's no thread that is waiting to take turn。

So that's the reason why we just reset the tail pointer by a comparison swap。So let's resetit a tale。

 So if there's no next pointer。Then。I know that The tale is still me。

So I'm trying to compare and swapb the tape pointer from myself， the node to the no pointer。

Which means that there is no threat that is waiting for the threat the law。

So it is effectively unlocking myself because。Originally， I was there。

 but I no longer hold a lock after comparing swapping this tail pointer that effectively releases myself。

From the lock。And if it is successful， we are going to drop my node。😊。



![](img/c601eb537c652afd698b09f60225460d_50.png)

And at this point of time。At this point of time， tail becomes。No pointer。And the locate note B。

And it is the end of the block node a， the third Bs， a turn。



![](img/c601eb537c652afd698b09f60225460d_52.png)

So， this is。h， what's going on here？But if at the same time， at this point of time。

 if another thread， see。

![](img/c601eb537c652afd698b09f60225460d_54.png)

Its trying to acquire a lock here。Then there is a contention between this another thread cease log and threadBs on log function。



![](img/c601eb537c652afd698b09f60225460d_56.png)

So depending on the order of the RNW instructions here。

It may be possible that this online function may succeed this cost or may not succeed this costs。

If we succeed this， then this unlock unlock is happening before and it just return。

 it just drop itself and return effectively the unlocking itself。 But if it fails。

 it means that a con thread are succeeded in。

![](img/c601eb537c652afd698b09f60225460d_58.png)

Acquiring the luck。And at this point of time。And what happens then it is loop again it is looping again from the beginning。

 Oh， I I fail to unlock this my lock because the tail pointer has changed。

 so I need to do it again from the beginning。Loading the next pointer and it may be changed because Cs log function may assign the node bes next variable。



![](img/c601eb537c652afd698b09f60225460d_60.png)

And after that， I need to go to here install store in the false value and then return。So basically。

 basically， this was done in this unlock function in the case of contention。



![](img/c601eb537c652afd698b09f60225460d_62.png)

Okay， so this is basically what on the execution log of the the MCS law。😊。



![](img/c601eb537c652afd698b09f60225460d_64.png)

And what is different from CH log is that。All the nose that is created in this La function here。

The node is created here in this boxing。So this is allocated in the hip。

And it is returned as a token。And later， in unlock function。It is still located in the same strand。

Recall that in the CH log， a node that is allocated by a previous thread is still allocated by the next thread。

 so it is attributable to the performance because memory allocators are usually assuming the assuming。

😊，The， the， the allocations are located in the same thread。 So otherwise， it is still safe。

 but you are going to pay some performance costs。But in this implementation。

A node is allocated and ded in the same thread and it is better for performance than C logs。



![](img/c601eb537c652afd698b09f60225460d_66.png)

But instead， the implementation is a little bit more complicated。

 so it needs to check the next pointer and swap the tail pointer， etc。



![](img/c601eb537c652afd698b09f60225460d_68.png)

![](img/c601eb537c652afd698b09f60225460d_69.png)

So you need to understand what's going on here。In order to。

And you need to pay more attention than the sales law。



![](img/c601eb537c652afd698b09f60225460d_71.png)

Okay， so first second good。

![](img/c601eb537c652afd698b09f60225460d_73.png)

And let's turn to the MCs parking lot。And。The only difference is that its node is having a what is called str。

Just， you can think of it as ability to sleep。 So it is just an ability to slip instead of doing。

Nothing very special or nothing very fancy。 It is just a mechanism to sleep in the ro programming。

And it is almost almost same。 So the tail you it the， the log contains the tail pointer。

And when you create a node， you are going to。嗯。Remember your own thread。

 So your own thread is recorded in this note。So that's the only difference here。

And the implementation is almost the same。 you in the log function。

 you create a new node and swap the previous pointer。😊，And if it is okay， it is。えです。呃。

Checking if the previous node is no， then it just returns itself。

 that means that there is no thread that is that is currently holding this logs and you just acquired the log by swapping the tail pointer。

And similarly， you are setting the next pointer。And also。

You are trying to wait for your node locked variable to be true。Otherwise， you just sleep。

Here is it is the meaning of this is sleep。Indefinitely， until someone wakes me up。

You're parking yourself into a parking lot。And waiting for someone else to wake you up。

So you are parkinging here。And who unpars it or who wakes it up。

 it is the unlock function of the previous thread。 So in the previous thread， unlock function。😊，You。

You read the next pointer and if it's not no， then you you are going to store the locked variable of the next pointer as false so that in this while loopbe。

 it can wake up。I mean， it can break the loop。But also， you are unpar the threat。

You're on parking the thread so that it is， it is going to。Wake up from the parking。

So it is sleeping indefinitely。Without unparing， the threat is no longer given the turn。

In in order to avoid that， you need to unpark it so that。The OS will schedule this thread again。

And so that this thread can break this loop and return from the lock function here。

So that is basically NC is parking lot， the only difference is use of this park and onpar。And。

Please note that this on park happens after storing this value。

You may say that it is a little bit complicated because you may think that， oh。

 why don't you just unpark here？Instead of cloning the thread and then write this store variable here。

But。It may introduce the deadline law if you unpack here before unlock knocking， I mean。Before the。

Sttor in the false value to the store。 then it may be possible that you unpackuck here。And you。

You unpack here， basically。And loop again。And then read the locked variable again。

And it may be possible that it is still false。I mean， it is still true。

Because maybe this instruction is not executed yet。So， you park again。

So it may happen if you unpark again， so you need to store the variable before unparing this thread。

 so in this way you can avoid the deadlock。Also， I'd like to discuss a little bit about the orderings here。

So here， the tail pointer is。Change it using a relaxed ordering。The reason is that you are not。

Interested in synchronizing multiple threads using the tail pointer。

 the tail pointer's rule is just ordering log axis。

 who called the log function before another thread log function。

 so that is designed by this order of the swab in this tail pointer。The synchronization happens here。

😊，From here to。Here。So this is allocated by the， the。This is set by the previous thread。

 and this is read by the next thread。And there is a release across synchron addition。

 So all the information that is。啊。Amin。I mean， there are two， I mean。Let me explain it again。

 so there are ways of to release of question synchronizations from here to here。😊。

And then here to here。So when you， when you write the note here， you need to。You need to。Oh。

 you need to。Given an information about this node， you created this node。

 and this node will be accessed by the。the unlock thread。

So this information should be transferred to。This。But because the previous thread online function is accessing the next pointer。

So that's the reason why we have to do release acquire here。

The knowledge about the box node is transferred to this acquire so that this。Access can be safe。

This excess cannot be reordered across the allocation here， which may。Introduce。Use， I mean。

 use before allocation。On the other hand， there is release a question correlation from here to here。

😊，Which means that all the accesses that is done before this love function is transferred to the the next red love function。

 which guarantees that。😊，Oh， if a thread is holding a log。

 then it is accessing the latest value of the data。So that is granted by this release。

 acquire synchronization。And also， there is another release across synchronian。Here。Here， I mean。So。

😔，Okay。There are two。 I mean， let's write that。 So I explain again。

 there are two leaves least request correlations。 So here too。Here to here and here to here。Okay。

 that's the really syn correlationrons inside is MC S and access parking lot。Okay。

 so far second good。

![](img/c601eb537c652afd698b09f60225460d_75.png)

AndSo far， we studied the implementations of those two locks。

 and in this slide I would like to explain the trade offs of the log again。

So the key ideas of the locks was that the guaranteeing mutual exclusion by release acquireir and guaranteeing fairness by ordering and waiting with different locations。

 and there are two key ideas。And this is this， this mutual description by this acquire。

It applies to all the logs， spin log， tick log， C log， MCS log。

 they all are ordered by this release acquired synchronization。On the other hand。

 only tick lock and CHGCS locks are guaranteeing fairness by ordering and waiting with different locations。

It since CH locks are ordering the excesses with a tail pointer。

And after the lock orders are decided， they are waiting for with a new location for each node。

 for example。So， so they are ordering and waiting in different locations。 So by doing so。

 they can guarantee the， the fairness。Also， usually the the ordering location， for example。

 tail or next。 and it doesn't need to be release acquire because they are just ordering and all this synchronization happens at the at the。

At these locations， the waiting locations， though that's the reason why ordering locations can be relaxed。

 They there't need any ordering ordering。Okay， there is the。Things。

And recall that tickenla is trying to guarantee fairness by queuing。Compared to the spin lock。

And the concern is that it has a little bit slightly complicated API than the spinner。

 It returns a ticket。The， the， the number。CH log is improving scalability by using。

Using per critical section， spin location， that means that。In the TL log。

 all the threads are waiting for the same location。But on the other other hand， in Serla。

 you split the locations and。A thread is waiting for a single location。

 and a location is waited for by only a single threat。So by doing so， it can。

 it can significantly improve the the performance。And because there is much less contention on the cash。

It is a linked list of a spinning location， basically。But the con is that it has a space overhead。

You need to allocate node for each critical section。And further。

 MC S log is trying to improve upon C log by。Allowing that， by by guaranteeing that。

 I'll know these allocated andd at the same rate， always。But。

But the con is that it is a little bit more complicated， and furthermore。

 it has one additional comparison swap。😊，Which may be deterrenal to the performance， though。

Before using these logs， you， you usually need to benchmark so that using which lock works best for your scenario。

And finally， we learn MCS parking lot， which is a slight variation from this MCS law。😊。

And in this lock， when you fail to log a function lock this， this， this one， then you park。

And waiting for the previous ride on park myself。It will significantly reduce the energy consumption by by allowing the。

The strike to sleep when it doesn't acquire a lot。Okay， so first good。And。And yeah。

But the concern is that when you when you just park and you are going， the parking itself is。Coス。

It itself costs a little bit。So if there's a modestist contention。

 then you will sacrifice the performance a little bit。Because parking and unpar， I have a coast。

So there was a paper， a somewhat old paper on performance evaluations of these logs。

 so if you're interested， please go to this link and see what's going on there。

There are a few questions about the logs， so please enter try to answer these questions on yourself and。

And I already explain a few of them。 for example， why Str is cloneed instead of。parking。un嗯。

Without cloning。So please answer these questions on your own so that you can better understand these log implementations。

Also， there are many， many， many other other variations of the logs。 So please。

Look at these codes and these keywords and codes if you are interested。

 So log is one of the most important concurrent programming objectives。

 so it has a very broad literature and there are many log implementations and verifications。

 So please if you are interested please go look at those things。Okay， so in the next video。

 we are going to start studying。The concurrent data searchers。And。We in so far。

 we studied logs and the primitives of the concur programmings or the semantics。

 So they are all the backgrounds。 So from now on， we are going to study what is much more interesting。

 It is con data structures。So we are going to study。啊， the。

Implementation strategies and the key criteria for those data searchers。

 and at the end of this semester we are going to study how to reclaim memories。

 what is the memory allocator and the allocator for concurrent data searchers。



![](img/c601eb537c652afd698b09f60225460d_77.png)