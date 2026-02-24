# UCB《嵌入式系统｜EECS 149  249a Introduction to Embedded Systems fall 2014》中英字幕 - P16：-16-Lecture 17 - Operating Systems, Microkernels, and Scheduling.zh_en - GPT中英字幕课程资源 - BV1rBgDzRE2s

Okay， let's go ahead and get started， so we are here。At multitasking。

 which is what most of you are doing while you're reading email well。

There's someone up here lecturing。And one of the key things I'm going to focus on today is some of the pitfalls of multitasking。

嗯。Not from a human cognitive perspective， which there are major pitfalls from a human cognitive perspective。

We're going to look at it from a more technical perspective。

 it turns out multitasking doesn't work all that well for computers either。

In addition to not working very well for humans。So a reminder that your project charter is due today。

 that means your teams should be formed and you should have some idea of what you're doing and you should turn that in。

 I think the deadline is midnight tonight， is that the way it was set up？Yeah。Okay。

 reminder that next week you have a problem set due on Tuesday。

 it's a shorter problem set than usual， so it's been slightly more rapid fire now and we will release the solutions to that problem set hopefully promptly at midnight on Tuesday so that you have a chance to look them over。

In preparation for the midterm。Which will happen on Thursday in this room。And。

I have posted on B courses a sample midterm， it just happens to be the midterm we gave last year。

I think I should tell you that I think it was a relatively difficult midterm or will aim for something perhaps not quite as difficult as that one。

 but you know sometimes it's a little hard to。Caallibrate these things。

One particular thing is there's a question on that midterm about cashs。

 I don't think we're going to ask a question about cashs this time， there's a lot of material。

To cover as it is， and that's a relatively complex topic。

So we're probably and I think also the grad students in the class have done more problems on it than the undergrads which。

So we're probably not going to ask anything about cashs on the midterm。嗯。For the midterm。

You will be allowed to bring in one eight and a half by 11 inch sheet of notes。

 you can use both sides。 One of the goals there is that actually。

Constructing those notes is a good way to study。Another really good way to study， by the way。

 is to think up midterm questions。And if you think up a good one。

 email it to me and maybe we'll use it。Okay。But it is a very good way to study， okay？

I have handouts for today because I'm going to be talking about a snippet of software that。

It's almost meaningless to try to get the whole thing on a slide。

 and so I'd like you to have a copy in front of you。嗯。So hopefully there's enough copies circulating。

嗯。Are there any questions for me？Yes。Yes， so the question is。

 were the problems that were not assigned from the book a good place to get practice。

 and I would say yes definitely， in fact， most of the problems in the book were previously midterm problems in this course？

嗯。That's it's difficult to come up with good questions。You know， keep track of them。Yes， question。

So basically all of the chapters that are covered by the homework through homework five。Are in scope。

 okay， the specific list of chapter numbers I posted on a B courses announcement。Well。

 it's in the announcement， but yeah， no， it's the problems on which you've done exercises。

 the chapters on which you've done exercises are the ones that are in scope。ok。

And so today's lecture will be the last lecture that is within scope for the midterm， okay。

 on Thursday we move on to the next chapter and you won't have done a problem set。

On that content before the midterm， so that'll be covered by the second midterm。Yes， question。

It the question was whether there will be anything from the labs on the midterm。嗯。

Possibly only in the sense that you know the labs kind of inform some of the content。

 so there might be， you know， we might give you a state machine that is representative of something in the lab。

ok。On the projects， by the way， we hope that all of the teams can find at least one of the five lab slots during the week to meet regularly with a GSI okay so each project will have one of the three GSIs assigned as your primary mentor。

And we expect you to meet weekly。Okay， and so the ideal times are going to be during the lab times。

 And so we're hoping that's going to work out and also。On the week of no 18th。

We used to do this in lecture where we would devote one lecture time to have all the projects come up。

you know， tell everybody what they're doing in their project， and it's very valuable， I think。

 for you guys to hear what the other people are doing。

But the class has gotten too big to do that now in lecture。

 so we're going to do it in the lab slots and I encourage you to come and。

hear what your colleagues are doing for their projects as well， okay if you can。

 obviously for most people coming to all five of the lab slots during that week and listening through all those presentations is probably more time than you have。

But you might want to come to some of them to hear what some of your colleagues are doing， okay？

And so each team will get 15 minutes to present where they're at， what their goal is。

 what's blocking them， what progress they've made， et cetera， okay。

So plan on that as a pretty major milestone for the。Projects。Any other questions for me？Yes。

The HKN exam archive is out of date。Oh。呃。Yeah， I think with the possible exception of last year's midterm。

 which I've already posted as a sample midterm， I think all of the previous midterms have been converted into exercises in the textbook。

So。Yeah， that's true。 Okay， I'll look through the archive and see what might be useful。

 I also don't want to flood everyone with， you know。Too much stuff。

but I'll look through the previous ones and see if there's good examples to post。

In addition to the one I've already posted， but the one I've already posted can keep you busy for a while。

 it's not a trivial one，I'm sorry， it was the previous midterm， the scope， it was yes， it was。

 in fact， everything that was on the sample midterm that I posted。Is within scope this year。

 except that， as I've said， even though we are covering chapter 9 on memory systems。

 we're not going to ask a question about caches。So。ok。Anything else？All right。

 we'll go back to multitasking。Some of you are already back to Modaytasking。



![](img/467984062720b82aeb1779d40c995c8a_1.png)

系。All right。Concurrency。Andcurrency is。Logically operating at the same time。

 whether it's physically operating at the same time。Is a separate issue。Okay。

 we call that parallelism。If it's physically operating at the same time。

 but logically operating at the same time， just is a。You know， conceptual thing。嗯。

At the lowest level， we've already talked about concurrency in the form of interrupts。

We have not talked about pipelining and multi core because。

We're not talking about architecture in this class in part because it's very well covered by other courses here。

But。Interrupts are a concurrency mechanism that is。

Universally used for IO in processors okay but it's a very low level mechanism。

 so today we're going to talk about kind of the next level up from that。

 which is the concurrency model that's typically provided to you by an operating system or a micro kernelnel。

Okay， so micro kernelnal， that term is just a term that's used for something that。

doesnn't quite rise to the level of being an operating system， so for example。

 it might not have a file system。Okay， you're used to doing a lot of software。you might think， well。

 can you actually do anything without a file system， Well， actually you can， I mean。

 a file system is just a way of organizing bits in memory。嗯。

And it's a construct overlaid on top of a raw architecture by an operating system。

So a micro kernelnel will have some subset of the capabilities of an operating system。

And is typically designed to be very small， consume very little power。

 occupying a small memory footprint， et cetera。One of the most common uses of a micro kernelnel is to provide a concurrency model on top of the raw interrupt level mechanisms。

Okay， so that's what we're going to focus on today is how you can provide a concurrency model above the level of abstraction of interrupts。

Now， just to give you a glimpse into what we're going to do in the future， well， today。

 one of the things we're going to look at is that one the pitfalls of multitasking。At this level。

And then later on， we're going to talk about concurrency models that have stronger formal properties than the multitasking models that are used at this level。

so they're meant to address some of the pitfalls that arise。Okay。So。What do we need concurrency for？

嗯。Reacting to external events。Right， that's。嗯。You basically have two choices。

To react to external events， you can just wait for them。This is a polling mechanism。

 so you decide at a certain point you're going to listen for external events。

And then you stop the world and you just listen for external events but。

That polling mechanism can be very inefficient because you're idle during the time that you're listening for events。

And you're not doing anything useful， so that's a non concurrent model it is， by the way。Used today。

Even particularly in safety critical systems， precisely because of the pitfalls in multitasking that I'm going to talk about today。

it's really very difficult to make multitasking systems reliable and safe。Okay， so for example。

 in in the safety critical software that controls the。

That is the aircraft control system interpreting pilot commands。

 controlling the aorons and the rudder and the flaps。That software typically。Doesn't use interrupts。

 doesn't use threads， has no operating system constructs involved。ok。

Precisely because it's difficult to make that software safe。So。

You can react to external events without concurrency， but it's extremely inefficient to do so。

Exception handling you really can't， that is a concurrency mechanism kind of intrinsically exceptions occur almost by definition out of the blue right。

 and if you're going to react to them， you're going to have to interrupt whatever you're doing to react to them。

嗯。A third purpose for concurrency is simply creating the illusion of simultaneously running different programs。

So those of you who are reading email are doing that。

 You're creating the illusion of actually doing two things at once。

 but actually you're only doing one and not very well。Right。嗯。Exploiting parallelism in the hardware。

 for example， making use of multico machines。Dealing with real time constraints。

 almost by definition in software， if you're dealing with timing constraints。

 you're doing multitasking。Because what do we mean by timing constraints， Well。

 software intrinsically has no temporal semantics the way we construct software today。

And so timing comes from the concurrency mechanisms that we use。Okay。

 so we'll talk a little bit about that in more detail。All right。Thread scheduling。

So this is going to be a big part of our focus today。

 so for our purposes today assume a single processor， single issue instruction。

 so you're executing one instruction at a time logically。 sequence of instructions。

 but you can still do concurrency。The way you do concurrency is you switch context。

 so you execute a sequence of instructions from one thread。

 then you suspend that thread and you start executing a sequence of instructions from a different thread and you suspend that thread and maybe you go back to the first thread so that interleaving between threads。

Is going to be a big part of the focus today。And predicting and controlling the thread scheduling with today's mechanisms is an extremely difficult thing to do。

Okay。So。If you're doing this at the micro kernelnal level。

 so you're implementing threads without an operating system， so there's no Linux。

 so this is the sort of the barest minimum。Multiitasking mechanism。

But it doesn't rise to an operating system level， it doesn't have a file system。

 it just does threads， okay？嗯。So you can deploy such systems and it's commonly done in embedded systems where you'll just put a thread library on bare iron。

 and it'll handle your multitasking。And the multi threading is achieved with interrupts。

 it is in the operating system as well， but we're not going to look very closely at operating system design。

 that's the subject of another course。ok。嗯。So generic operating systems provide thread libraries。

 and we're going to leverage one of those P threads， okay。

But they provide no fixed guarantees about when threads will execute and you might be。

You might fall victim to a marketing ploy， okay？And believe the statement。Real time operating system。

呃。I'll state categorically here there is no such thing。ok。

Real time operating systems are really ordinary operating systems。

That just pays some attention to thread scheduling。ok。So in generic Linux， for example。

 you can set the priority of a thread， but it'll typically be ignored。ok。

So the priority doesn't matter。But in our tos， the priority will be respected generally。

 so when you have two tasks that are available to execute， two threads available to execute。

 the thread scheduler will always resume the one that has higher priority over the one that has lower priority。

Okay。嗯。That's a very weak。Control of timing。Okay， very weak。

If you want to specify in an arttos that something should occur periodically， how do you do it？

Does anybodybody know？Yeah。Yeah， you could use an external timer。

 so what you do is you set up a periodic interrupt。ok。That periodic interrupt will。

Evoke an interrupt service routine。If you have configured this thing to execute a particular thread。

Periodically， then that interrupt service routine will not just simply return from interrupt。Okay。

 because if it returns from interrupt， it simply returns to whatever thread was already executing。

So the way that an operating system handles a context switch is it messes with the stack。Okay。

 before it returns from interruptt。So it'll change the return address to be。嗯。

The address of an instruction for a thread that was previously suspended。ok。Puts that on the stack。

 then executes return from interrupt。 And to that thread， it just looks as if， who， you know。

 I just keep executing。 It never ses the fact that it was。That it was， in fact paused。O。

So a real time operating system is really just a way of giving you at the software level control over this low level interrupt mechanism。

嗯。Actually， before I put this up， does anyone know the difference between a process and a thread？Yes。

A process may have multiple threads， so that's one distinction， yes。Right。Right。

 that's actually the most important property really， is that a process。嗯。

Is essentially assigned its own memory。It doesn't share memory with other processes。

 typicallyy the way that's done is that you virtualize this and you give the process the illusion that it has all of the memory on the machine available。

ok。嗯。And。It is。Then not able to access the memory of another process and any attempt to do so。

Will result in a segmentation fault， which will abort the process typically in an operating system。

Okay。嗯。So。Yeah， so processes carve out sections of memory。

 threads do not threads are a more primitive concept， and they're just。

Sequences of executions of instructions and multiple threads within a process can share the same memory。

When you put a thread library on a bare iron processor in a。Micro kernelnal。

Every thread has full access to all the memory of the machine。

 and typically there's no memory protection at all， so you don't get segmentation faults。

You can read and write anything。In memory。Okay。All right， so let's focus on Poss threads。

 which are called P threads。Actually。An interesting anecdote here。In the late 80s and early 90s。

 every year there was a major announcement by all the computer vending companies that they were going to unify the UniX operating system。

And because it was extremely frustrating to people who were developing software that there were so many different variants of UniX out there and that they were mutually incompatible and that if you wrote programs for UniX machines。

 you had to port them individually to all of the different targets。

Typically they had incompatible thread libraries too， so the porting was absolutely nontri。嗯。And。

Every year for several years。All the companies would get together， agree that they should unify this。

 make a big announcement。And then fail to unify it。And a year later， they would all get together。

 agree that they should unify it， make a big announcement， and then fail to unify it。

And that kept going until Lina Stvals released Linux and basically put them all out of business。嗯。

We do have different variants of Linux， but they're actually much more homogeneous than the variants of UniX that were out there before。

 and all of them support P threads。As does OSX， which is a variant of Uniix， by the way。

As does windows， okay， so Posss is probably about as close as we have to a universal operating system。

Okay， so learning to use it can be pretty useful。Because it'll run on almost anything。

An alternative is to use Java， which is。Has the notion of threads built into the programming language。

 That's quite unusual。 Most languages don't have that notion built in。

 And for reasons that I'll go over today， I believe this will ultimately be viewed as a huge mistake。

It shouldn't have been done。But。We'll get to that。Okay， so how does B threads work？Well。

Here's a little snippet of code。Okay， that illustrates what happens in a program that creates threads。

 so you've got your main。ok。And this P thread create function is the key function here。

 the first key function， okay？And it takes a number of arguments。

 The first one is an address of a place to store the thread ID。Okay。

 and the thread ID is some data structure， you don't need to care what the data structure is， right。

 supposeupp you do care， you want to know how much memory is that thread ID taking up。

How would you find out？Sorry。Size of。嗯。What is size of？Okay， so you could。Yeah。

 if you have so assuming you have the appropriate library for an implementation of size of。

 you could invoke size of。Yeah， there's a more direct way， though。Yeah。

These are very experimental approaches， but there's a much more direct way， yeah。Just read that file。

Yeah。It'll tell you。What this thing is。Okay。I mean。You can demystify see programs always。

 right the C language is ultimately a very， very small language。Is not much there。Right。

If you go into the header files and go into the libraries， you can demystify everything。

and figure out exactly what the thread ID is okay， but here we're going to pretend we don't care。

 so it has a data type P thread underscore T， the underscore T is a convention using to remind you that this is a type。

ok。嗯。Then。What does this mean， where and memory will exit status be stored？

Is a good preparation for the midterm。Yes。Yeah， it'll be stored on the stack， right。

 and it'll be stored very early on the stack as soon as the main program begins executing。

There will be。You know， depending on what the size of your address space is。

 say it's a 32 bit address， then this is exit status is a 32 bit pointer。

 so there will be eight bytes on the stack set aside to store exit status。ok。

And the data type is declared to be a pointer to nothing。

Which is the conventional way in sea of completely bypassing the type system。ok。

You can have pointers to nothing， and then you can use them for whatever you want。

This is not a strongly typed language， it's really it allows， it gives you a lot of rope。

 you have complete control of the machine。嗯。Okay， so then this value variable will be an integer also stored on the stack。

 we can initialize that to something。And when we create the thread。

 we pass the address of the value to the P thread create function。And then that。

Address will be dereferenced and passed。Or I guess actually， that address will be used directly。

As the argument here， notice that the argument to your thread function is also a pointer to nothing。

In this case， what it's going to actually get is a pointer to an integer。That is on the stack。

All right。So your thread function will be invoked with a pointer to an integer and that integer is stored on the stack。

So。You also pass as an argument to this B thread create。A reference to a function。

You can do that in see。Okay。A function is a data type。

 and you can pass a reference to a function as an argument。 this is also a pointer。

 it happens to be a pointer to program memory instead of to data memory。

 but it's a reference to a function。This argument we don't care about。

 and here we give it an address for the thread ID， so what's going to happen is that this procedure when it gets invoked。

We'll create a thread which will sometime begin executing this function。We don't know when。

It might begin executing it immediately， it might begin executing it even before P thread create returns。

ok。Or P thread C might return and you might execute several more instructions before that thread begins executing。

You have no control over that at this level。So it's just going to start that procedure。

 this procedure up here is going to start executing sometime in the future after you call P thread create。

ok。Now， what happens if I were to just have nothing more in Maine？What would the program do？Sorry。

Yeah， it would create the thread， but do you think this thread would execute？

Yeah sort of may or may not， it kind of depends on what your micro kernelnel does when mainine exits。

Right。If it does execute， you're in trouble because。

You will have popped all of this stuff off the stack。Right？And consequently。

 your procedure may be looking at arguments that are no longer there on the stack or have been overwritten by other stuff。

It''s up to- I'm going to talk a little bit about how the thread scheduling decisions get made。

 right， but an implementation of P threads is free to do whatever it wants。Sometime in the future。

 it will begin executing this threat， this procedure。ok。嗯。Okay。

 so to prevent Maine from executing from exiting prematurely， by the way， you know。

 when I ask a question like this， what happens when Maine exits？

That's a hard question to answer because the fact is if you've got a microprocessor and the clock is active。

It will execute instructions。Whatever the program counter is pointing to。

It'll fetch instructions from that location and execute them。Whether you're in Maine or not。

If you're clocking it， it's executing。Okay。So it kind of depends on what your compiler does。

 how it works with the boot loader， you know， maybe when it exits main， it goes to an idol。Lop。

Or something。But you don't know for sure what's going to happen。Okay。

 it's an operating system that terminates。When you exit Maine。

An operating system will destroy a process， what does it mean to destroy a process？Well。

 the machine process is a logical construct。The machine doesn't。Vanish poof into thin air。

 the machine keeps executing instructions。Right。So exiting Maine does not stop a machine from executing instructions。

It's an important thing to realize in embedded systems。Okay。So。Here we call P red join。

to which we pass a thread ID and a reference a pointer to an exit status。

 a place to point to store the return value from this procedure。Okay。

 this procedure is going to return a pointer to nothing。

And that pointer to nothing is going to get stored。In this exit status variable on the stack。

You should be careful when you return a pointer to nothing。

That it not be on the stack that belongs to this procedure because if it is。

Then the memory in which that thing is stored will have been delocated by the time you can read it。

Hopefully all of that is clear if any of what I just said isn't clear。

 you really need to go back and study chapter9 before the midterm。Okay。Okay。

 so P thread join is a blocking procedure， it'll actually suspend the thread that is executing Ma。

Until this procedure returns。If this procedure never returns， then P thread join will never return。

That's not necessarily a problem， by the way， you know， in the classical theory of computing。

 all programs that fail to terminate are equivalent， they're all defective。But in embedded systems。

 it's often the reverse， all programs that terminate are defective。

And the ones that fail to terminate are exactly the ones we want。Right。

So you have to be a little careful with how you treat termination in the context of embedded systems。

O。So create the thread may or may not start running。You can pass in arguments。啊。

You can return values from your thread function。And you can block until your threads conclude。Okay。

Any questions about this？All right， what's wrong with this program？I have a question。For you。Yes。

I'm returning a pointer to a variable on the stack。ok。

That variable is then used after the P red join。Which means that you've popped up the stack。

That the stack no longer is assured of having whatever value it had， 42。Okay。

 that value may have gotten overwritten。 what could cause it to be overwritten between。

This invocation of P thread join。And its use here。Yes。Well。Anything that uses the stack。

 And by the way， printf is going to use the stack。So the mere calling a printf is going to obliterate 42。

 It's going to overwrite that data value with all the maybe the return address。

Of printf right or something。So it's pretty much assured of not being there by the time you try to use it in the printf。

So this is why， I mean， you need to know where stuff is in memory and when it remains active in the stack。

Okay， I think I， oh， one thing。When does a thread get？Suspended， okay。

 so let's go back to this pattern here。So P thread create is going to return。And when it returns。

This may or may not have begun executing。Now logically。Everything。

At this dot dot dot location is executing concurrently with everything at this dot dot dot。

But in a single processor with a single issue instruction stream。

 that's not actually what's happening。They're executing one at a time， and they're taking turns。But。

When and how？Right。And one of the biggest problems with threads is that you don't know。Okay。

So a thread can be suspended between any two atomic operations。 what's an atomic operation？Yes。

Can't be interrupted， yeah， that's one property， yes。Happens in one cycle， yeah。

 that's not necessarily true， actually。Processors have multi cyclee atomic instructions。

It can't be interleaved with other operations。 Yeah， so how do you know if you have a C program。

How do you know what in that program is going to execute atomically？Yes。You could disable interrupts。

 yeah， that would be one way to regulate things， you have to do a little bit more than that because。

The thread scheduler sometimes gets invoked whenever you make any operating system call so if you。

Happ to access memory that is on disk。You might。Suspend a thread and start executing a new thread。

 even though interrupts are disabled。You also might， if you have a cash miss。

Sometimes the thread scheduler will kick in and do a context which even if interrupts are disabled。

 yes。Yeah， so you could do that， look at the output of the compiler， look at the assembly code。

 but after they have to go even further， you have to actually look at the manual for the processor that you're using to determine which of those assembly instructions are atomic。

They're not all atomic， so the arm instruction set， for example， has a bulk memory move instruction。

Executs in multiple cycles and can be interrupted。But it's a single assembly language instruction。

So the short story is。You don't know。Basically， you have no idea。

So a thread can be suspended between any two atomic instructions。

 and you have no idea what an atomic instruction is。So that's not such a nice situation， right？

There are certain instructions that are actually explicitly guaranteed to be atomic that you used to implement。

For example， mutual exclusion protocols， which I'll talk about in a minute。

Because you have to make some assumptions about atimomicity in order to do multitasking at all。Okay。

I think I said the rest。All right。So you can model threads using asynchronous composition of state machines。

In fact， it's a pretty natural application of asynchronous composition of state machines if you have a state machine describing a progression of a program。

Then another one describing a progression of another thread。Then。

Asynchronous composition of these is a pretty reasonable choice。

 right what that means is when the overall machine reacts。

That means when your processor does something。Arbitrarily pick one of the two machines and have it react。

ok。Now in practice。嗯。An operating system will not do fine grain interleaving。

So it won't execute one atomic instruction from this thread。

 then one atomic instruction from this one， then one from this one。

 because the cost of doing that would be enormous。 It actually costs a lot to do the context switching。

So。The context switching compared to the execution of the program is relatively rare。

This is actually a problem because there's an awful lot of program bugs that manifest only if context switches occur in unfortunate places。

But。When you're testing a program， what are the odds it's going to show up in that unfortunate place？

Pretty small right， unless it's you're giving a demo for a sponsor or something like that。

 in which case Murphy's law will help you and maybe you'll see the bug right but。

Bugs can lurk in programs for years。Okay， without showing up in any kind of testing or in deployment。

And then。You never know what's going to happen when they show up。Some of you may remember。

 there was quite a bit of press over the last couple of years about Toyota's unintended acceleration debacle。

Right。And NASA commissioned a study of their software。

And I actually got invited to serve on that commission that was going to look at the software。

 but I had to decline because Toyota had been a sponsor of my research。

 so I had a potential appearance of a conflict of interest。

And but the report is really quite interesting and it really slams。

The software design approaches at Toyota and their design methodology。嗯。

The typical program is a bunch of threads。All executing concurrently and accessing unguarded shared variables。

So the typical pattern is sensor data。Temperature sensor， for example。Will be read by， say。

 an interrupt service routine driven by a timer interrupt。

And that interrupt service routine will write the temperature to a global variable。

That is then accessed asynchronously by all the threats。ok。So a control engineer says， yeah， that's。

 that's the way you want to do it， right， because you want your threads to always see the most recent。

Sensor data。But the problem is you have no control over the interleaving here， right。

 So you could be looking at recent data from one sensor and stale data from another and treating them as if they were simultaneous。

But they're not simultaneous。Right。So what are the artifacts that can arise from that？Well。

 you don't know， actually。And this NASA study showed that there were， in fact。

 possible executions of these programs that would lead to unintended acceleration。

They were extremely unlikely to occur in practice。But when you've got a million vehicles on the road。

 extremely unlikely to occur， may not be good enough。Right。

They have no proof that these are the things that occurred。

 but the fact is that you can't test these programs to ensure through testing that these scenarios will not occur。

Okay， so let's consider a concrete scenario here and try to solve it。

So suppose that we're designing an aircraft。And this is an aircraft engine being mounted on a plane。

Okay。You can see the hoists here。And there's hundreds of sensors on this engine。

And those sensors are doing all kinds of health and diagnostic measurements on this engine。

Now it used to be in a sort of old fashioned design for airplanes。

 every one of those sensors would have a pair of wires routing it to a rack mounted computer in the cockpit。

Whi would then aggregate all that sensor information and use it。

But that design has a lot of problems， right， one of them is it turns out that you actually increase the weight of an aircraft considerably by putting that much wire on it。

Okay， so it decreases the fuel efficiency of the plane。

So the more modern design is what people call integrated modular avionics where you distribute microprocessors throughout the airplane and you put them on buses。

The buses that are used today in aircraft。Conformed to a standard called Anc AINC。

 which is a time triggered bus， so it does time slotted reservations。For transmission of data。

 so it's very different from an ethernet bus which is a best effort kind of bus that can allow for collisions and when you do a collision。

 you back off and you retry okay so these ank buses you don't get collisions。

 you reserve time slots on the bus。And the sensors and their microprocessors will simply publish their sensor data periodically on this bus。

ok。And then。So you've got a bunch of sensor data coming at you over the bus。

 so proper software engineering practice suggests a design pattern which is called the Observ pattern in this gang of four book where you have a process that runs on a computer in the cockpit that is simply subscribing to these streams of sensor data monitoring the health of the engine and reporting the health of the engine to the pilot。

ok。These are concurrent threads now because you've got。You know。

 processes running on the microprocessors in the engine， reading sensor data， putting them on a bus。

 you got a process running in the cockpit that's monitoring those and updating the display。

 and by the way， you have a lot of other processes also updating the display。

So the displays in the cockpit are a shared resource。

 and they're used for multiple purposes by different tasks on the plane。Okay。

 so you'll have multiple tasks updating the displays， Okay。

 so visualize that scenario and lets let's try to solve a very specific problem， which is。

The pilot should be alerted if the engine is on fire。Okay， assumeoom you've got temperature sensors。

 oxygen sensors， things like that that can tell you。Engine's on fire， youve got to flame out。

 you've got to do so。ok。So the observer pattern from the Gang of four book。

 this is called the Gang of four book， Gamma Helm Johnson and Biddis。ok。嗯。

And it codifies a whole bunch of。Commonly used design patterns，Interestinglyly enough。

 these guys were sort of the first to actually write this down。

People were doing these kinds of design patterns for decades。嗯。You know。

 giving the design patterns names。It turns out， was a really useful contribution。

So they define the observer pattern， which is a one to many dependency between a subject object and any number of observer objects。

So that when the subject object changes state， all of its observer objects are notified and updated automatically。

O。So you could have an observer object in the cockpit。That's。Observing the subject。

 which is the temperature of the engine。Okay。So let's write some multi threadreaded software to do this。

So here's the C program， hopefully you got the handout that I spread around。

 are there any leftover handouts somewhere？Did anybody knock that one？There's some back there。

So those of you who came in late。And those of you who were too busy multitasking and it went by you don't have one。

嗯。Okay， so you have a complete program in front of you。 Okay， a very small one。 And again。

 I apologize for the smallness of the example。But。The real examples are millions of lines of code。嗯。

But it's nonetheless enough to really illustrate the pitfalls。And outline。 so we have a variable。

 let's assume it's a global variable。嗯。AToyota style design， okay。

So this is the value that's going to get updated by the sensor。

And we would like to make sure that we can create listeners that will be notified。

 observers that will be notified whenever this value changes。Okay。So。In order to be notified。

 you need to provide a notified procedure。Okay， so the way that you set this up。

Is you call an ad listener。Procedure。And you specify as an argument。

 the procedure that you would like to have called whenever this value changes。ok。

So a listener puts you on the list of listeners。update地。Is a procedure that will update this value？

ok。And one of the things that update should do， in addition to updating the value。

 is notify all the listeners that are currently on the list of listeners。Okay。

So your interrupt service routine for your sensor will call update。With a new temperature reading。

There will be a list of listeners available。And your update procedure will then。Call the update。

 we'll call the notify procedure for each of those listeners to notify each listener that the value has changed。

Okay， very straightforward pattern。All right。Diving into a little more detail。

 if you look closely at the C code。The list of listeners is a linked list。In this case。

 so it can grow without bound。Presumably in an embedded system。

 you don't want it to grow without bound。So you have to worry about that。

 but you don't want to necessarily specify ahead of time how big your list of listeners is。

So we define a structure which is an element in the list。

 which simply contains a pointer to the notify procedure。

And a pointer to the next element in the list。That's a typical linked list structure。

So then this is a complete definition of a linked list of listeners。

You have a pointer to the head of the list。Which is initialized to null when the head is null。

The list is empty。 if the head is not null， it's pointing to one of these elements which has a pointer to a procedure and a pointer to the next element。

 if it's the last element in the list， the pointer to the next element will be no。Okay。

So everybody clear on， I mean， hopefully this is all old hat， you all know how to write linked lists。

O。Okay， here's a procedure to add a listener to the list。If the list is empty。You just。

Alloccate memory to store an element of the list。Okay， and you set the head to point to that。

You set the heads listener， the elements listener pointer to point to this notify procedure。

You say there's no more elements in the list。And you set the tail equal to the head。ok。

If the list is not empty。Then you take the tail。And you make its next point or no longer point no longer be null。

you point to newly allocated memory。For a new element in the list。And then you set the tail。Of。诶。

You set the pointer to the tail of the list to the new element。Okay。

And then you update that new element。Clear enough。Okay， so the update procedure。Given a new value。

Just sets this global variable to equal that new value。

And iterates through the list of listeners invoking the。The notify procedure。Okay。

 so this is a C construct， right element？Elements， listener field。Is a pointer to a procedure。

So you can invoke that procedure and pass it and argument new value。So this is a procedure call。Okay。

And then we just iterate through the list， calling each of the procedures。All right。

You could model this update procedure using a state machine。Okay。Like this。

When you're not in the update procedure， we're in the idle state。

 when the update procedure gets called， we transition to line 31， setting some values。

 then we're going to circulate through this list of states， which is the notify。Sequence。

 iterating through the list， and when I'm done iterating through the list， I return to IL。Okay。就。

Suppose forget about the distributed nature of this。

 okay let's assume that this is all running on a single processor。Which is actually。

 in some ways the better situation， that's more difficult when it's running on multiple processors。

Okay， but assuming it's running on a single processor。Is the code as written？嗯。Thread safe。

Will it work if there are multiple threads？Each of which can call add listener and update。

What could go wrong？Yeah。Yeah， if so two procedures try to call， I mean。

 two threads try to call the same function at the same time， okay。

 let's look at one of these procedures。This one， for example。ok。So one of the threads。

Calls a listener。And the threat is the list of listeners is empty。So it。

Just before it starts executing this instruction， however， the timer interrupt kicks in。

And another thread gets scheduled。And that thread。Calls add listener。And discovers， oh yeah。

 the list is empty。And it adds its element to the list。And then。

That thread eventually gets suspended and the original threat gets resumed and the original thread is now at this location。

Thinking that the list is empty。And it'll simply overwrite the previous listener's request。

To be notified。Okay， and the thread that previously called adolescent listener will never be notified of any temperature changes。

Because the original thread will have overwritten its data。Will that show up in testing？Probably not。

Okay， almost certainly not， in fact。嗯。But sometime in the field。

 it might just be that that red light in the cockpit。

 the thread that controls whether it's on or off。Never gets its notified procedure onto the list of procedures to be notified。

So this program is not threads safe。ok。So。Let's try to make it threads safe。Okay。

 so P threads gives us a mechanism for doing that。Which is to acquire mutual exclusion locks。

So in particular。I can create a mutex lock， which is a type P thread underscore muttex。

's just a data structure， again， if you're curious about what this data structure actually is。

Just go read the header file， it'll tell you。ok。But anyway。

 there's some data structure there that is the lock。

And there's a procedure that you can call in P threads， called P thread_ Mutex_ lock。

 and you pass it a reference to the lock。And what this does。

Is this guarantees that no other thread once this procedure returned？

No other thread can acquire this lock until this thread unlocks it。Okay， so if any other thread。

 a second thread tries to call a listener。And I've already acquired the lock that second thread will not return。

 this procedure will not return until the first thread has executed this procedure。Okay。Yes。

Is it possible for both to request the lock at the same time？

If we have a single issue instruction set on a single processor， then no。Right。But。

If you have a multi core machine or you have a multi issue instruction set， then。Yeah。

 but what do you mean by at the same time？This is where in order to implement P threadread Mutex lock。

You actually have to dive into the architecture that you're implementing it on。

 and you have to find an instruction typically called a test and set instruction。

Which guarantees atity that you can test a variable and change its value without an interrupt occurring between testing it and changing its value。

Nothing can block you Once you've tested it， you will succeed in changing its value。Right。

That's an atomic test in set， and you have to have an atomic test in set in order to be able to implement this muex。

Okay， but you can see now why this is provided as an operating system。

Resource rather than a user level resource， because there's no way to write a portable program in C that does a mut text lock。

C is not a rich enough language to do that。You have to know something about the underlying architecture in order to implement this。

Okay， in Java， you don't need to make these explicit calls。

 although you can you can create what is called a synchronized block。

 or you can simply declare the procedure to be synchronized。

 in which case there's a mutex associated with it automatically。Okay。

 synchronized is a very bizarre word for that term。

 because synchronized usually means two things are synchronized if they happen at the same time。

In Java， synchronized means two things are not allowed to happen at the same time。Which is。

Very bizarre twist of the English language。Anyway， okay， so so if we acquire a lock。

 we can guard against two threads messing each other up as they're adding themselves to the listener list。

We also have the problem that there's a race condition between threads with the updates， right。

When you update the value， you're then going to iterate through the list of listeners to notify them。

Well， what if while you're iterating through the list of listeners， the list of listeners changes？ok。

In fact， it could change in a rather nasty way where this condition is never satisfied。

And your notification procedure goes into an infinite loop。Whi would be a real problem。So you can。

Put your update procedure， guard it as well。So problem solved， right？No。ok。Problem is not solved。

Because there's a very significant deadlock risk。Can anyone see how a deadlock can occur？Yes。Yes。

Yeah。So let me give you a couple of rules of thumb， one。

 if this is the only Mutex lock in the program。Then you're safe。Can't get deadline。ok。

But if there's another mutex lock somewhere， for example。

The process that's updating the cockpit screen。That's a shared resource。

 I need to acquire a lock to update it。So when is that going to happen， Well。

 that could happen when this procedure is called the notify procedure。

 That's a reasonable time to update the cockpit display。Suppose that the procedure that I call here。

Blocks trying to acquire a mutex。And the thread that holds that mutex。Decides to call adolescent。

It decides suddenly it wants to be notified when。This。呃。Variable changes， okay？

Then that thread will block because this thread holds the lock。

but this thread is blocked because the other thread holds the lock it's trying to acquire。

And the two threads freeze。And the only way to get out of that。Is at the reset。ok。

There's no way to resume executing those programs。Now， is that likely to occur？No。But it could。

Give you a little anecdote， we in my group， my research group。

 we've done quite a lot of software development and this was a picture taken during a code review。

 we used to do pretty intensive code reviews。And。We got a really good turnout whenever it was code that I had written because my students loved to find bugs in it。

And so this was a pretty good turnout for code review and we were reviewing some code that I had written。

And we were reviewing code that had actually been used for years。

And in every use of the Ptolemy system。This code was central。 It was being used all the time。 Okay。

 and it was being used in a multi threaded context， and it was being used on multi core machines。

And it had worked。Fe years without a problem， okay？But in the code review。

 the students identified that it was in fact not threadsSa， in fact。

 it was exactly the deadlock risk that I just showed you。So we said， oh， that's bad， let's fix it。

So it was written in Java， so we put in the synchronized keyword to the add change listener method。

Three days later， we had an email on the mailing list saying。

 it's a weird deadlock I've never seen before， and he sent us the stack traces。And sure enough。

Exactly the scenario I just described had bitten this guy in Germany and caused his program to deadlock。

Okay。All right， so how could we fix this？Well。Actually， before we get there， yeah。No， no。

 he updated to the fixed code。Okay， we implemented this fix。He updated to it。

And his program deadlinelock。It was working fine without the fix。Okay， be wary of software updates。嗯。

Okay， and it was exactly- I mean， it was incredibly difficult to find。

 but he gave us a complete stack trace and his example was simple enough。

 what we did was we actually printed out the source code for the various files that were involved and laid them out on a table and started drawing lines between them to figure out what were the possible interleavings that could have led to this stack trace。

And finally found it。ok。And this was actually how we fixed it。Okay。

So the way to fix it was to release the Muex lock in the update before iterating over the list of listeners。

Okay。But you can't iterate over the list of listeners without a mutex lock。

Because if the list can change out from under you， you're going to potentially go into an infinite loop or the list could get corrupted。

So what you do is you copy the list of listeners before you release the lock。

Then you iterate through the copy and do the notifications on the copy。Okay。This still doesn't work。

就。Find the floor。Yes。That's a potential problem， a listener could remove itself from the list and then get notified。

It could， if I don't know how you would get a segmentation fault from that。

 if you could conceivably if you had delocated。Memory， yeah， so that's a potential problem。

 but there's a much more serious problem。Yes。You get two updates to the value。What's your name？

Daniel。You almost got the really nasty problem， but you definitely got the scenario right， I mean。

 the scenario you described is there's two updates to the variable。And。

You're going to get a notification of a stale value followed by a notification of an updated value。

And maybe you wouldn't want the notification of the stale value。

But there's a worse problem in that scenario。Which is that you could get the notifications in the other order。

you could be notified of the updated value and then notified of the stale value。Okay。

So your sensor says。Engine's O。 engines on fire。And you're notified in reverse。Engines on fire。

 engine's okay。You maybe get a little flash on the screen。But engine OK is like lit up。Okay。

 but the engine's actually on fire。Yes。Yes， so let's go through it carefully， okay。

So you have two threads that are calling update。ok。嗯。

One of them will succeed in writing the value first。

 and the other one will write it second because the writing of the value is within a critical section。

 this is called a critical section。So there's a mutual exclusion lock。

 so there will be one will succeed first， then the other。So there's whichever one。

Does the update second gets to determine the persistent value of this variable？Okay。

But they release the lock before they do the notification。

Which means that the notifications on those two calls could occur in arbitrary order。ok。

Notice that the notifications are using this value。Not the value of the variable from there。嗯。

You know， global scope， although it's not clear that that would necessarily be safe either。

 but nevertheless， they're using the local value and so that could result in the notifications occurring out of order。

This leads to a potential inconsistency in a system， right， You could have two parts of a system。

Both of which think they know the state of the system。But they don't agree on what that state is。ok。

And that can lead to really seriously insidious bugs。And by the way， these are bugs that， you know。

 I mean， a deadlock when the bug may be rare。Right。So the occurrence may be rare。

 but you know when it's occurred。This one， you probably won't even know that it's occurred。Okay。

So how do you test for something like that？You can't， right？嗯。So people say， okay， all right， yeah。

 so this is hard。Get over it， you got to be Doug Leah to write multi threaded code。

 everyone else should not be allowed to。He's the one guy I would trust to write multithed code。嗯。

But actually， you know， humans are very good at reasoning about concurrency。

We do it all the time in the physical world。It's just that the model of concurrency and threads isn't。

Even remotely like the model of concurrency in the physical world。Okay。

 threads are sequential processes that share memory。 And from the perspective of any thread。

 the entire state of the universe can change between any two atomic actions。So it's kind of like。

 you know， if I think of this lecture as a thread。Theres there's nothing that keeps me from standing here。

In an instant， the lecture hall is empty， and I'm just lecturing to an empty。Set of chairs。

That may happen anyway。嗯。But you I mean， if it happens， I would see you all walking out the door。

But in a multi threaded context， you don't see that。

The state of your universe can change without you being able to observe any reason for it having changed。

ok。Humans have trouble reasoning about processes like that。

Because we have no experience with processes like that。

 Our brain did not evolve to reason about processes like that。ok。I mean。

 imagine if the physical world did this。 then， then perhaps we could really trust multith programs because our brains would have evolved very differently。

 and we would be able to reason about them。 But as it is。

 our brains can't reason about these kinds of processes。So， you know if you're using Mu Texasex。

You better be nervous， okay？Because even the smartest， most skilled。

 most experienced programmers will make mistakes with threads and mutual exclusion locks。

And my claim is that actually， nontrial software written with threads。

 semaphos and muttexes is incomprehensible to humans。

 I used to think it was just incomprehensible to me。

But now I'm convinced it's actually incomprehensible to humans。So and yet it is the most widely used。

Concurrency paradigm in software。Which is pretty scary。



![](img/467984062720b82aeb1779d40c995c8a_3.png)

So。Threads have a pretty weak foundation。Okay， like this piece of poor quality engineering。ok。嗯。

And if you have a weak foundation， it's really hard to build things on top of it， by the way。

 notice that this is being held up by threads。Com。I understand they've gotten rid of those now。

 actually， that they've managed to shore this up so that it doesn't need the cables anymore to ensure it doesn't fall over。



![](img/467984062720b82aeb1779d40c995c8a_5.png)

嗯。But。There's a very simple analysis of why this is a problem。Software。Actually has a very。

 very simple underlying formal model。And that formal model gets completely undermined by threads。

Okay， and the formal model is simply function application。

 so you can define an abstract model of computation for software as being something that operates on bits and particularly on finite sequences of bits。

Okay， so B star is the set of all finite sequences of bits。

And a computation is a function that takes a finite sequence of bits and produces a finite sequence of bits。

Okay， very simply。And you can compose computations by doing function composition。

So every line of a program。😡，Is a function like this？It takes the state of the machine。

 which is a finite sequence of bits and yields a new state of the machine when that line has executed。

Okay， so it's a function of this form， and a chain of two instructions is simply a function composition。

Right。So it's a very simple model， but this model doesn't admit to concurrency easily right start with the initial state of the machine。

 proceed through a sequence of state transformations， end up in a final state。

But if you have threads。Mounction composition doesn't work anymore。ok。

You have a state when you got suspended， but a new state when you resume。

And there's now no useful formal model for the behavior of this process。

So we've not only taken a beautifully simple， elegant， powerful， formal model and weakened it。

 We've utterly destroyed it。Okay， we've eliminated it altogether together。

Which is a pretty big gloss， so threads are， in fact wildly non deterministic。

 right they just their behavior can be all over the map。And as an engineering principle。

 what New Texas are is taking something that's wildly non deterterministic and trying to rein it in。

You're trying to constrain what the thread scheduler can do。As an engineering principle。

 that's not a very good way to do design。It's kind of like my one analogy that I use is if you want to design an internal combustion engine。

You could start with a big vat of iron and hydrocarbon molecules moving around at random。

And constrain their motion。Until you get an internal combustion engine。

But that's not the way you do it， right， you make parts， you assemble parts， and out of those parts。

 you get systems。Okay， and threads don't work that way。

 so the programmer's job is to prune away the nondeminism。And fortunately。

 people have invented techniques that help。So object oriented programming helps because it hides a lot of shared variables。

 so it limits access， limits visibility of your state of your system。Coding rules， so for example。

 if you always acquire locks in the same order。If all threads acquire a sequence of locks in the same order。

 it's a nontri proof， but you can prove that you can't get a deadlock。

There are libraries written by experts。So the threadSafe data structures in Java were written by Doug Leah。

 one of the few people on the planet I trust。To be able to write these programs。

There's higher level mechanisms like transactions in databases or design patterns that already have the where some smart people have figured out how to get the concurrency to work like mappRduce。

You can try to apply formal verification to these， so you come up with state machine models。

 there's some very nice work that's relatively recent。

That synthesizes constraints on the thread scheduler to guarantee that you won't get deadlinelock。

Beautiful work。You can use enhanced languages that have better concurrency constructs than threads。

But all of these things still fall under this principle of you've got something wildly non deterministic。

And your job is to constrain it。And I think that's flawed。

And we'll talk a bit about models of computation that have stronger。Properties。

 more reliable properties later on。That's it for today。



![](img/467984062720b82aeb1779d40c995c8a_7.png)