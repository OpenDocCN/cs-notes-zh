# KAIST《Rust并发编程｜CS431 Concurrent Programming 2020 fall》中英字幕（豆包翻译 - P4：-04-Lock-Based Concurrency, an Introduction to.zh_en - GPT中英字幕课程资源 - BV1oi421h7b2

So today， we are going to start studying concurrency first from luck based concurrency。

So the part name， which is search for Sa API and its meaning will become clear in the course of doing this slide。

Okay， so let's start with lock based currency。

![](img/6252942acfb28dc263dfdab8f91ba3b0_1.png)

But as a context， I'd like to introduce a shared memory concurrency as a concept before going into lock based concurrency because it the context of all the concurrency well learn in this course。

 so we assume that there are multiple stress in our program and the multiple stress are sharing the same memory at the same time。

 So for example， they are third one，2，3 and blah blah and N and they are all sharing the memory。

So you can see that it is a little simplified view from the existing physical CPUs because they are caches or they are stores and all the kinds of complex things inside the actual implementations of the CPUs and memories and the system。

 but for the purpose of this class for now， let's assume that we only have threats and they are sharing memory and no other details will be evident at this moment。



![](img/6252942acfb28dc263dfdab8f91ba3b0_3.png)

![](img/6252942acfb28dc263dfdab8f91ba3b0_4.png)

But later， maybe cashsius and other kinds of。Optims。

 they play a key role in understanding concurrency， so we will learn them later。 But for now。

 let's focus on thrust and memory。

![](img/6252942acfb28dc263dfdab8f91ba3b0_6.png)

So this is the model of concurrency we are going to use。

 which is shared memory concurrly because multiple stresss are sharing the same memory at the same time。



![](img/6252942acfb28dc263dfdab8f91ba3b0_8.png)

So here a thread is basically an agent that is executing its own program， for example。

 usually it is a program with a program counter and program encounter is constantly increased and the current instruction is executed in this thread。



![](img/6252942acfb28dc263dfdab8f91ba3b0_10.png)

The thread has a local storage that is usually called to register or register file。

 and it is updating the registers on its own， and from time to time it is accessing the shared memory that is located in the stack or a hip in the usual domainmenclature from architectures and operating systems。

And yeah， it is requesting a read and write to the shared memory。

 and it will get responses from the shared memory and。In the course of doing so。

 it is executing on its own， and maybe it will execute to some IEO so that the fact of this thread can be visible to the outside world。

 so this is basically a threat。So if we already took courses on operating systems。

 you may well know all these concepts， but I am reiterating these concepts here because I want to focus on some aspects of those ideas here the idea I want to stress for strategy is that it is an agent。

It is agent that is accessing the shared memory or shared resources。On the other hand。

 shared memory is a resource， it is a shared storage resource of data and data is written to this memory in read from this memory。

 so as a result it is a resource and it is shared among multiple stress I want to spread that aspect of this shared memory。

Okay， this is the context for lock based concurrency and lock rate concurrency we will learn later but。

But maybe it will not be dealt with in this class， but there are other kinds of concurrencies as well。

 So this picture only captures the concurrency inside CPUs and memory。

 but there are shared memory concurrency or other kinds of concurrency among CPUs not only CPUs and memories。

 but also accelerators like GPus and FGs， or even the emerging class of persistent memories。

 like Intel obtain these memories or arms upcoming persistent memories。

 or even we can think of concurrency among multiple computers。

 basically if multiple computers are attached to a single network and they are sharing some resources like databases or some some caches。

 then you can think of it as a concurrent system and you can analyze those distributed nodes in distributed systems as a concurrent objects。



![](img/6252942acfb28dc263dfdab8f91ba3b0_12.png)

![](img/6252942acfb28dc263dfdab8f91ba3b0_13.png)

But for now， let's focus on just memories and stresss。 So this is the context for our study for now。



![](img/6252942acfb28dc263dfdab8f91ba3b0_15.png)

Okay， now let me introduce now luck based a short American currency。

 So the luck base means that at any moment a single memory location is accessed by only a single agent。

SoThat means that in shared memory， multiple stress are not accessing the same location at the same time in lock based concurrency。

 that this is basically at the meaning of these lock based things。Okay。

 it corresponds to the easy concurrency I introduced in the previous lecture， and this is。

 as I said in the previous lecture， the main benefit of this is simplicity。

So we basically kill all the concurrency， all the interesting concurrency that they shared mutable accesses to the same resource。

So as a result， it is simple， only one agent is accessing the resource， theres no actual concurrency。

 simple。However， the disadvantage of this approach is that it is possibly and quite often inefficient for our purposes because we kill all the concurrency and only one agent can access a single resource as a result。

 we cannot parallel execute multiple agent or multiple stress at the same time。

 so it is the process con of this lack based concurrency。

But anyway we start with this lock based concurrency。

 it is simple and we are going to look into lockfr concurrency later after we master the concept of this lock based concurrency。

The major mechanism to achieve or to program， this lock based con is unsurprisingly loss。

And lock is an object for which only one stress hold a lock。 So lock is basically。An object。

 just like in the object in front of the door， only one agent can hold a lock。

If it is held by an agent and another one is trying to get it。

 you should wait for the order to finish using the lock。

And it is effectively removing all the concurrency。 So here's an example here。

 let's say that this is two threads and this bar double bar is meaning a thread separation。

And there are left threads， and there are right stresss。

And let's assume that these big letters are short memory locations from now on。

 and these small letters will be on registers， agent local or thread local registers。

So this program is basically reading from X and adding it to one and then assigning the new value to the X again。

At the same time， the right strategy is doing the same thing。

 it is reading from x and then adding1 and then storing it to x again。And also as a convention。

 let's assume that all the short memory locations are zero at the beginning of the execution。

And you may guess that， or you may argue that at the end of the day。

 x should be  two because it is incremented in the left thread and it is incremented also in the right thread by one。

 so as a result， x should be incremented by two times and it should be  two。However。

 this reasoning is broken and it actually doesn't happen。 I mean。

 it it actually doesn't hold in the real systems because unfortunate interlaving of the threat executions may produce。

 for example， S equals one。Let's see why。So suppose that these stress are executed in an interlived manner。

 that means that they are executing one instructions at a time and turn。

 they nonistically take turns and execute their own instructions。



![](img/6252942acfb28dc263dfdab8f91ba3b0_17.png)

![](img/6252942acfb28dc263dfdab8f91ba3b0_18.png)

And suppose in an execution， this left thread is executing the first instruction that is reading zero from r x and signing0 to r1。

And then let's assume that the R threat takes turn and it is reading zero again from this axis。

And now the lecture takes turn and assigning 1 to X。And then the right threat takes1。

 and maybe me it is the case that X is assign sign1 again。So X is red as 0 in two stress。

 and it is assigned one in two stress in boost rests。In this。

 in this particular scheduling of instruction executions。And if it is the case。

 it may be the case that x is not two， but one at the end of the execution。

So this anomaly or this unfortunate nondetanism arises from the fact that this X。

 which is a shared memory location， is actually access in a shared mutable way because they are accessing the location at the same time and they are actually modifying the content。

 so it is a shared mutable accesses to the same resource， and it causes the problem。

 it is beyond the reach of our thinking or our imagination of how this program should work。

So in order to remedy this， we need to protect the excesses to the X。In order to do so。

 the easiest way to do so is inserting a lot。So let's say that L is a shared lock that is shared among the two stresss and L has two interfaces。

 two methods， basically the first one is acquire that is acquiring a log when it is not held and the other API is released so if you hold a lock and then you release this lock。

 then you are no longer holding the lock。Okay， now in the presence of this protection。

 acquire and release， this the unfortunate inter living does not happen。

Because let's say that the left thread execute the first instruction here and acquire the law。

 and then it can read and write to the location X。But if this thread is acquiring a log and it holds the log。

 the right stress cannot enter into this line because it should wait for the left thread to release the log。

 it just waits for it to be released at this the first line。

 the acquire function is not exiting until it successfully acquires the log。And as a result。

 it should be the case that all the access to the X by the left thread should happen before all the access to the X in the rest。

And as a result， our imagination or our intention actually holds。

The act should be two at the end of the day always， because love prevents such unfortunate in。

And luck is such such a useful construct that allow us to do such a reasoning only since only one agent is accessing a single resource at the same time。

 we no longer need to reason about unfortunate inter livings and the nondeterminisms that is arising from these inter livings。

Okay， so far so good。And as I said， it has two APIs and additionally it has one more API， try a。

 and as I said， acquire blockss until acquiring the lock。

 just wait for other threads to release the lock。And try acquire returns whether a luck is acquired and it may return false when another thread already held a lock and it immediately returns false。

 oh， I try to acquire the lock， but I failed because other threads has acquired it so I am I I didn't acquire the lock or it may return true。

 that means that I successfully acquire the lock。The third API is release that is releasing the log that I have already acquired previously。

So these are the lowle API of this lockx and this is the most important API of all concurrencies LG is the most important object in all concurrent programming and this API is the most important APIs of this lockx。

Okay， so first second good， if you use this API well。

 then it is guaranteed that there is no longer shared mutable accesses to the resources and we may be we may be。

It may be easy to reason about concurrent programs。But there is a pitfall。

 the pitfall is that this API is really extremely error pro。

 it is really really easy to misuse its API so that the system can hang or the system can be broken。

 the environment can be broken， for example， if you don't write release here。

 then the system will hang。Because this thread cannot occur the threat the long。On the other end。

 if you forget to insert a acquire here， then the invariant x equals 2 may not hold at the end of the execution。

 so you need to somehow very intelligently insert those API invocations and only if you successfully inserted those very well。

 the system will work as you intended。But it is extremely error prone for two reasons。

 The first reason is that it is from this API， it is， it is somewhat coincidental， or it is somewhat。

啊，这么。Ly to protect X using L。 I mean， there is no explicits relation in the code between L and X。We。

 the programmer， just know that， oh， X is protected by L， and as a result。

 we can safely use the X in this code。But there's no such an explicit marking of the relationship between L and X。

 and as a result， it may be the case that we are acquiring a Rolock。

That is not meant to be protecting the ax。Or we may use a different resources that is not intended to be protected by this log L。

If that happens， the all the environments are broken and this unfortunate results may pop up。

Even though you悠落。The second challenge is that the second reason why the API is entrepreneur is you need to match。

 acquire and release very well， you should not forget about releasing the lock。

 you should not forget about acquiring the lock at the same time and you should release the lock you you have already acquired if you are releasing different lock than it is problematic。

Okay， for these reasons， it is this APIs is in my opinion， really error pro。

I know that a lot of programs like Les are implemented this way and very well。

 Linux code is very well maintained， but it is still very prone and is for begins and it' for those who。

Are working on large code base， large codeor base usually have bug when the program is retain this way。

Because no one is understanding the entire codeb and the environmentvari becomes extremely complicated and if API is at a low level。

 we cannot somehow statically guarantee that the program the entire program is well written。

And these challenges， this API problem is particularly more problematic for concurrent programming。

And the region is then。The programmer needs to be concerned with the API all the time and it is costing high cost and it is especially so for concurrent programming because concurrent programs usually have much more complex invariant than the sequential programs and as a result the programmer needs to take into account these complex invariance all the time and it is causing very high cognitive load load to the programmers。

And still， even though programmers are very much concerned with these bugs。

 usually there will be remaining bugs in large systems。

 so I saw concurrent programs of a millions or 10 millions of lines of code and they usually have a lot of bugs because no one is understanding the entire environment and this bug is difficult to test as well because usually such a bug such a hidden bug that pops up once every。

 for example， billion times or billion times so testing coverage it is difficult to achieve high test coverage for those kind of concurrent programs。

And that's the reason why this Airpro API is more problematic for content programs。Okay。

 that's the reason why we want to use high level API for those locks because we want easy to use an O API API so if。

An API， a log API is always safe， and it is boproof than it is much easier for programmers because programmers don't need to worry about safety no longer。

If a program is compiled using this high level API， then it is okay。

 The compiler guarantees that this log will work， as I intended。And this is a great benefit。

If there is no such a benefit， programmers should be concerned about the invari all the time。

 but if compiler guarantees this invariant， then you can forget about this。

 you can just forget about this and use high level API and automatically there will be notebook。

So in particular， we want a high level API that is automatically matching O release functions and also the high level API should relate a lock and the corresponding inter innerner resource explicitly。

For example， the relationship between L and X should be explicitly marked in the program。



![](img/6252942acfb28dc263dfdab8f91ba3b0_20.png)

And as a result， there is no confusion about which lock protects which data。Okay， as I said。

 this kind of high level API is。A low cost and it introduces less bug because all the bug will be automatically eradicated thanks to the hba API and the compiler。

Okay， and for logs， already there are many kinds of high level APIs。

 and the most prominent one is from C++ and its ability to do resource acquisition is initialization or RAII。

And the higher level idea of this API is the two things。 so in order to automatically matching。

 acquire and release invocations， we are introducing a RAII type which is a lockout and lock when you acquire a lock。

 then it returns a lockguard， instead of just return nothing。It returns a log guard。

 and when this log guard is deed， the corresponding log is automatically released。

So as far as this lock card is there and if it is not intentionally somehow。Forgotten about。

 then the lock corresponding lock that created the lock guard is automatically released。

And acquire and release function is automatically matched。

That is basically the intention of this lockguard。And if you don't understand what I'm saying。

 you probably want to search for this RAII or resource acquisition is initialization pattern。Okay。

 and the second thing， in order to relate the lock and a resource in a automatically， I mean。

 explicit way， we introduce a new type that is lock。Lock and tea。

 And this is basically a pair of a lock， and there are tea。

And it is explicitly marking that a lock is associated with the data of T。And as a result。

 we are no longer confused with which data is protecting with which resources。

So let me show you the example of this too。So here is API of the lockguard。

 which is in the standard C+ plus。So here， let's just think that view textex is a kind of law。

 so it is a lot。And。At the beginning of this function。This is called in main function。

 The main function is creating two threads， and each thread is executing the save increment function。

And it is then the main thread is then waiting for the T1 and T2 to be finished and later it is printing the value here。

And main threadread is launching a new thread that is executing Sa increment and inside Sa increment that is executed by each thread。

 it is acquiring a lock here by creating a lockguard。And this is the name of the lockguard log。

 and it is acquiring the lock from this metatax。And this is an RII type。

 and it it signifies that I am now holding the the the lock mutex here。 G I lock is acquired by me。

 and this is the proof that I acquired it。 Lockguard is a proof that I have acquired the GI Muex。

And after that， I am incrementing or accessing the GI， which is a shared resource。

 but it is okay because I acquired a lot of GI Muax。And now at the end of the day。

 I'm returning from this function。And this lock is destructed here at the end of end of the function。

And what is interesting here is that this when log is distracted。

 GiI Mu text is automatically released。So that is basically the idea behind RAII you initialize this resource on lock guard using an initializer and at the end of the day when it is disrupted you are automatically running some code in this case it is releasing the lock。

In this way， we cannot forget about releasing the lock because。

 because this lock guard is automatically releasing the lock。 We cannot forget。 we。

 we cannot force this to。First these two。And not to release a lot unless we are doing something strange here。



![](img/6252942acfb28dc263dfdab8f91ba3b0_22.png)

Okay， the second idea is relating a data and a log， and as I said。

 the benefit is that it is mandating， it is making explicit which data is protected by rich log。

And the type looks like this。 the log type is consisting of two data， which is a low rock。

 the log type of the delu that has acquired and release functions and the data type。

And if you acquire a log by calling this log function。

 then you are creating you are basically creating a lock card， but before that。

 you are acquiring a log。Because。Lock guard means that you acquired the log。

 So you need to actually acquire the log。And after that， you return the lockguard。

 that means that signifies the fact that you have acquired it。So firstly good。

And when you have a lock guard， then you can dereference the inner data。

Because it is proof there is a proof that you acquired a log。

 So you are legitimately allowed to access the inner data。

 That's the reason why we implement this operator。 So when when log guard is used。

 it can be automatically transformed into the reference or reference to the data inner data。

So it is possible because we explicitly related log and data。

 That's the reason why we can dereference from this logguard into the data。Now。

 at the end of the day， after finishing the referencing the data。

 we can release the lock and by destructing this lock card in the deor of this lock card。

 we are releasing the lock here。So as a result， we are automatically releasing the law。So in summary。

 this API achieved the two goals at the same time， matching or client release the same time。

 and furthermore， it is explicitly relating our log and the data。

So first are good and it is quite a good API and it based API we can think of inside as the C++ programming language。

 but actually it is not 100% safe。It is Sa fish API。But still。

 there is a huge case for which we can break the system using this API。



![](img/6252942acfb28dc263dfdab8f91ba3b0_24.png)

Let's what's happening here。So let's see that there is a lot of type lag of integer。

And you acquire the lab here and get the guard here。

And suppose that you dereferenced the guard and get the pointer to the data。So it is okay。

 it is allowed in C++ because you acquire a guard and the guard can be converted into the pointer to the data。

Now suppose that there guard is dropped here or disrupted here and lock is automatically released。

But the problem is that the pointer data underscore PTR is still there。

 and we can still dereference the data pointer here。But if it is the case， it is very much unsafe。

 it breaks all the invariance that is provided by the loie。

Because it can access the inner data without help， without holding the lock。

 because the lock is already released here。So maybe it is the case that other threats has acquired a lot and accessing the same data at the same time。

Then the unfortunate inter may happen from there。 It is no longer as intended。So as I said。

 the root codezy here is that this pointer to data is leaked after the guard is disrupted and log is released。

So data PR is lit here after the guard is dropped and this' the root cause conversely we have to mandate that data pointer should not outli the lifetime of this life guard。

 I mean data guard。When their guard is draft and the lock is released。

 data pointer should no longer be used from now1。But it is using that。

 and the API actually allows that。You may think that it is a pedantic approach to argue the unsafe of this API。

 so you may say that this doesn't happen in the real world。But in my experience。

 it is actually happening。In real world， in production code。And it causes a lot of troubles。

The reason why it happens in the real world code is that the programmers are doing whatever they want if it is allowed。

If pointer， you can get a pointer out of this data， they do for later purposes。

But probably for a good will。 I I get the pointer here and use this pointer before the card is dropped。

But later， they forget about this invariant and they use the pointer after the card is dropped。

So it is really difficult to guarantee the API is used as intended if there are a lot of programmers working on a big。

 big code base。So if this kind of API is into my eyes， very much airpron。

 and it actually causes the trouble in the real world production code。

So the solution I'm proposing here is using the program language Ro type system based on ownership and lifetime。

So rust is specifically designed to avoid all such problems like this。

 so this is basically a lifetime problem， the lifetime of data pointer should not be longer than the lifetime of data guard and it should be somehow guaranteed in the type system。

That is basically the purpose of the Ro tax system。



![](img/6252942acfb28dc263dfdab8f91ba3b0_26.png)

Preventing the the lifetime problems of the libraries and the programs。 So in Ro type system。

 we can actually guarantee that。 So that's the reason why ro can solve such problems。

So that's also the reason why in this course we are going to use rust inside of the C++ that is most widely used in concurrent programming。

Because I believe that T system is very good API。 It provides very good API for learning and implementing concurrent libraries。

And by learning this， I believe that you can be better conquercurren programmer。

Even though you are going to use C++ in the future for cooking programming。

 learning Ru and learning concur with Ru will be very much helpful。



![](img/6252942acfb28dc263dfdab8f91ba3b0_28.png)

And here is safety implementation of log with a safe API。

 and the safety of this API is actually proven in a research paper。

And this API will be discussed in a later phase of this course。Okay， so this is the basically the。

Why this API is unsafe in C plus+， And I mention that this API can become safe in rust。

And before delving into the Sa API in RuS， we really need to discuss when study rust first。

So in the next video， we are going to study rust as a crash course and then going back。

 go back to the concurrency and continue to study the lock based concurrency and its core concept and its APIs。



![](img/6252942acfb28dc263dfdab8f91ba3b0_30.png)

![](img/6252942acfb28dc263dfdab8f91ba3b0_31.png)