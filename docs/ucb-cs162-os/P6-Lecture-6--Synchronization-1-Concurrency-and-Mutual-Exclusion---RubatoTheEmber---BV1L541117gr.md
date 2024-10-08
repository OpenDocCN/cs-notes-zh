# P6：Lecture 6： Synchronization 1 Concurrency and Mutual Exclusion - RubatoTheEmber - BV1L541117gr

 Okay everybody， welcome back。

![](img/92632d7d853797ca01f9a2ab7bcecff1_1.png)

 Let's see， is that loud enough？ Can you hear me？ All right。

 Welcome back to the second in person lecture。 This is going to be a habit， I hope。 So this is good。

 You know， last time we were talking about some basic ideas in concurrency and we were starting to really talk about how threads can be implemented and so we're going to tackle that today and hopefully by the end of the day。

 you'll not only have a better idea how we get threads implemented but you might。

 actually have a better idea about why we want threads in the first place so， So。

 let's see what's going on here and will my slides actually go forward。 Okay。

 just if you remember last time， first of all， just to remind you。

 we were talking about setting up sockets for communication。

 And the key thing there was that you'd set up a server socket to listen on a particular IP address and port。

 The client would make a request a connection of that IP address and port by telling its own IP address and port。

 And， and then a connection would be made and a brand new socket gets created for every new connection and every new connection is unique。

 Five to pull of source address destination address source port number destination port number and protocol。

 And there has to be a unique port for every connection and typically that happens because the client randomly selects one from a range。

 Okay。 All right。 And then well known ports are things like 80 or 443 or 25。

 They're typically things from zero to 103。 So， good。 Questions。 Now， of course。

 we showed you this basic web browser。 And this one was one that's using processes so this listen gets executed once and that's sort of putting the ear out。



![](img/92632d7d853797ca01f9a2ab7bcecff1_3.png)

 And from that point on in a loop， we accept the next connection this is blocking until there's somebody to accept。

 We fork a new process。 This sort of child code talks to the connection。

 And notice that we close the server socket since we're not using it。

 And but we got a copy of it because of fork。 And then when we're done we close our own。

 The parent meanwhile closes its the connection sockets since the child is going to handle that。

 And then it we're not going to wait in version three of the protocol we just go back and we accept another one。

 And we can keep going。 And that will make sure that there can be as many parallel connections as people who want them。

 All right。 Questions。

![](img/92632d7d853797ca01f9a2ab7bcecff1_5.png)

 All right。 Good。 So， now we're going to get into today's topic。

 So we started by talking about each process is described by a process control block。 And， you know。

 this is a chunk of every inside the kernel。 It's not accessible at user level。

 And among other things， it's got the state。 To restore that process。

 If there's only one thread that state could actually be embedded inside the process control blocks of the program counter registers。

 etc。 As we'll see later in the lecture， if you have a process with more than one thread。

 then typically you've got a linked list of these thread control blocks。

 That describe each thread that's running。 There's a scheduler that we're going to spend a lot more time on during our scheduling discussions in a few weeks。

 And then after the midterm that decides which process gets the CPU at which time。

 And then the other thing to keep in mind is that a scheduler can also hand out non CPU resources like access to the network or access to disk I。

 So we're going to pursue this multiplexing thing a lot more today。 And so if you remember。

 this is also a picture from last time that if we have two processes and they only have a single thread for now。

 Process zero process one process zero runs for a little while。

 And at some point we get an interrupt， we switch into the operating system where we save out all the process zero state。

 reload process one state， and then go back to user level to run process one。

 And then it runs for a little while and then we get another interrupt come back into the kernel save process one store process zero and continue。

 And so we go back and forth。 And then an effective this is that we've got two processes and they look like they're running at the same time。

 Okay。 Now we had some good kind of discussion in Piazza about well， if you only have one CPU。

 why do you want to do this， because you're just， you know。

 you can never have things running at the same time。 You know。

 process zero is running when process one isn't invites versus so why bother with this。

 Are there good reasons for that。 What do you think。 Yeah。 So the best。

 that's a great first thing to think about is if this process is running and it blocks on IO。

 because it's waiting for the disk。 This one can run。

 So just by making sure that we have multiple processes there。

 then we have the potential that we can have concurrency going where we're actually letting we're overlapping IO and computing。

 Now， what we're going to get even further as we go into this process in the term。

 is you're going to see that this idea of concurrency isn't just the simple one of overlapping IO and computation it's also going to allow us to assign a thread。

 To do something very simple like pull in all the input from the keyboard and do something with it and we can totally let it do its thing。

 Well， we go off and we draw aliens on the screen or whatever our game might be doing。

 And those two things can be separated from each other， and we'll run perfectly well。

 even if there's one CPU。 Okay， so one CPU is not a good reason for avoiding multiple processes or multiple threats。

 Okay。 Everybody good with me so far。 And by the way， until about 2002 one CPU was the norm。

 and then we started getting multi for so multi core is a fairly recent thing in the grand scheme of things。

 Although perhaps all of your life was multi core。 So the other things that are kind of interesting which we're not going to do too much with today we'll get a little is these crossover points where we go kind of from user to kernel and vice versa。

 I'm going to show you that pretty explicitly with respect to stacks。

 but I think next time I'm actually going to show you in Pintos or a real operating system。

 What is that transition really look like， and we'll actually show you more details on that。



![](img/92632d7d853797ca01f9a2ab7bcecff1_7.png)

 And then the last thing was what's the process look like it starts when we generate a new one with fork。

 it gets put on the ready queue which really means that it's runable。

 And then we can basically go back and forth between things that are on the ready queue and the thing that's running so right now in this next several lectures assume there's only one CPU or core。

 So there can only be one thing in the running circle， all the rest of them are on the ready queue。

 Okay， and it's going to be up to the scheduler to pick the next one off the ready queue put it on the run queue and then they switch back and forth。

 Okay， and so you can have many things on the ready queue， but only one thing running。 All right。

 How many people have actually looked at the task manager or done a PSA UX or looked at whatever to see what's running right you look there's many。

 many things right hundreds。 And so those are all mostly sleeping somewhere。 So。

 and they're not all running because if all those hundreds were running you'd be in trouble。

 And so notice that every now and then something that's running needs to do I oh and then it gets put on a weight queue。

 And the most of the things that are in the task manager are waiting。

 And then when the date when the I oh comes back then we're back on the ready queue and we can get some more cycles and then eventually we exit。

 And we go into a terminated state until we can give our exit code to our parent or grandparent and then we are done。

 Okay。 Now， the thing to keep in mind here is this notion that we can have a process is a container address space with one or more threads in it。

 This on the left， the single threaded process is kind of what we used to call a traditional process or a heavy weight process。

 And today， most operating support system support the thing on the on the right。

 which is basically many threads in one process。 Okay。

 and each one of those threads of course has its own register and stack storage。

 because well it's a full thread of execution， it needs to know where it's executing from it needs to know what it's stack pointer is it needs to know what the registers are。

 And so we have to have space for that for each of the threads。

 On the other hand the threads are in the same address space so they're sharing all the same code the same data the same files。

 Okay。 Good。 Now that's all kind of repeating for last time so I'm going to pause here and see if we have any other questions before we go forward down。

 Yeah。 So， in the concept of a child， the parent with threads so threads are typically a little more flat。

 Okay， so the threads are kind of in the process。 There。

 there are occasionally some operating systems that give you a little bit more detail with that but for now let's think of it as a flat thing inside the process。

 Okay。 So， of course， we've got this view as well which is sort of shared state for the threads or the heap and the global variables in the code。

 and the per thread state is， as I mentioned stack and registers and metadata and etc。 Okay。 Now。

 So let's say， so the core of concurrency， the core of the operating system is this。 Okay。

 what we've got here is looping， where we run a thread。 We choose the next thread， we save the state。

 we load the state and we loop。 Okay， and we do this over and over again。

 And as I kind of joked at the very end of lecture last time， there's the operating system。

 you got it all let's take our final next week we're done。 Okay。 This is an infinite loop。 Okay。 Now。

 You could argue this is all the operating system does。 Okay， and I， you know。

 I was able to summarize it for you in these few lines。 Now， can somebody tell me， you know。

 should we ever exit this loop and why would we ever exit this loop。 Shutting down the system。 Good。

 Where else， why else。 An exception like a big one。 Blue screen， the blue screen of death， right。

 That's another example。 Now， the other thing that's a little more subtle here is you might think。

 why I'm busy running， I might actually exit the run to go off and do some。

 I owe or some interrupt handling and then come back。 Okay。

 so that's another way of thinking of getting out of the loop。 So yes。

 it's nice to think that the OS is just this but we perhaps we should have a few more details。

 What do you think。 Sounds like a good idea。 Let's。

 let's hold off the final for forever and I'll not have a final so。

 So let's talk about this running of the thread here right so let's consider the first portion。

 And what does that mean so we got to load the state of the thread into registers of the physical CPU so the thread。

 when it's not running is sitting in memory。 So it's a thread control block。 It， you know。

 where it left off because you've got its PC， you know what the stack pointer was and so on。

 But in order to actually run it you got to load it back into the CPU。 And。

 and then load the virtual memory space if we're changing processes， and then you jump to the PC。

 And now you're running。 So， what is a couple of things here also that the fact that we have to load up the virtual memory space for a thread。

 If we're， if we're changing processes means we must be running this loop that I showed you in at kernel mode in order to be able to actually modify the threads。

 But then when we go to run we're going to jump back to user mode so there's some transitions going on here right that was the red to green you saw in a previous slide。

 So how do we make sure， for instance， that this dispatcher loop here will only run the thread for a little while。

 and then get control back to choose the next thread and run the next thread。 So that's a。

 an important question。 I mean， how do we do that。 Anybody。 Time are interrupt， right。 Now。

 how many of you have ever gone to like a computer museum。 I don't know。

 maybe your parents room you found Macintosh from， you know， the 80s or something。

 Did you know that it didn't used to be the case that operating systems were that hardened。

 And so you'd load up a bunch of things and they'd be on the screen。 And what you'd see is。

 well that's great until one of them crash and then the whole system crash so one frozen application would actually freeze the whole system and that's。

 it's a precisely explained here。 And by the fact that it would run a thread that would go into an infinite loop and would never exit back into the operating system and so there was no way to take control。

 Okay。 So that timer， which we'll talk a lot about today is something we've got to be careful with。

 Okay， we've got to somehow make sure it happens properly so that we don't lock up because of a bug。

 So， so one of the ways， however， is that we're not going to rely on the timer let's talk about how that Macintosh might have worked。

 And that's what we call an internal event where the process is running for a while。

 And then what it says is yield。 And that says okay fine operating system what somebody else run。

 So those early operating systems relied on this notion of yielding。

 And so it was a process whereby an application that's running would periodically say okay let somebody else run okay let somebody else run。

 And so whether it ran properly and multiplex properly dependent crucially on did you put enough yields in there。

 And did you ever hit a yield。 Okay， and those are what we call internal events。

 External events is this example of the timer interrupt。 Okay。

 so let's talk about the internal ones for a moment。 In addition to explicitly yielding。

 you might actually try to do IO like I'm about to read a file。 And in that case。

 you're giving control back to the operating system and the operating system may make a decision to reschedule somebody else at that time。

 Okay， one reason for that of course is that I always a long running process takes a long time。

 You might as well let somebody else go。 The other is well。

 they've decided to break up what's going on here so I'm going to take that opportunity to switch in somebody else。

 Okay。 So， let's say good rule of thumb。 I think I gave you this lecture to ago for how many instructions you lose to access a physical spinning disk。

 Anybody remember。 Million so millions of good number。 Okay， plus or minus a few orders of magnitude。

 We'll talk a little bit like an astronomer here but， we'll talk about it in instructions。

 So that's important to black and I'll and let somebody else run。

 So another example might be if this given applications running。

 and it's going to wait on a signal from another thread。

 It's going to go into the operating system and say， well， I'm。

 I can't do anything right now let somebody else run while I wait。

 And then yield of course is the thing I just mentioned。 So if you look here。

 Here is how we could make a version of compute pie that might actually play well with others。 Right。

 So in an infinite loop we compute the next digit， then we yield compute the next digit yield and as long as we keep doing that。

 then we know that the other applications in the system could keep running。

 even on an old Mac and touch。 And then， somebody see the flaw in this particular。 Statement。 Huh。

 No you're computing the next digit so you'll yield。 Yeah。 Yeah， each digit if you。

 if you ever I had a， I was a person who liked to come up with ways of computing pie and my got mute so I had many algorithms I looked at。

 And the problem is that if you compute each next digit takes longer and longer and longer and longer to get。

 And so this would work well for a while but then eventually you know you'd be taking days before you yield it so this is probably not a particularly good example。

 But for now we're going to use this to understand more about what goes on with the stacks。

 Let me tell you why I mean the stack so if we've got two applications running。

 and they're switching between each other。 They both have a stack。

 Somehow those stacks have to be coordinated and cleaned up because we're loading and unloading things on the processor so let's see if we can peer into that process just a little bit。

 So here we go。 So we're computing pie for a little bit and then we execute yield so what's the cyan color here is going to be user level。

 And it， this is something that the user code execute so the user code is executing the next digit of pie。

 And yield is going to yield into the operating system with a system call。 Okay， now。

 why is it a system call。 That's why yield needs to be a system call。 Yes。 Yeah。 For now。

 we're assuming that to go to another thread we actually have to go into the kernel so why do we know about calling the kernel in terms of the stack。

 but has to happen with the stack when we call the kernel。 What was that。 Well。

 the state needs to be saved and what about the stack。

 Do we trust the user to have a good stack pointer when they enter the kernel。

 Pretty much any question I say do we trust the user your answer。 Oh， right。 Okay。

 So what we have to do is one of the first things that happens on that transition is when we enter the kernel we're going to change to a kernel stack。

 which is not necessarily contiguous with the original user stack。 So there's a user stack。

 There's a kernel stack。 Those two are married together right now in terms of a process。

 a user level process is always going to have both a user stack space and a kernel stack。

 And we can treat it kind of like they're together。

 because what happens is this transition from user mode to kernel mode。

 comes with a process of switching the stacks to a well defined kernel stack that we know is good because we're inside the OS and we've vetted it and it's good。

 Okay。 And we're going to basically put。 We're going to put the user state will store on the kernel stack here so that's why it says kernel yield。

 So this system call system， this system call is really like a procedure call that crosses into the kernel。

 saves the state for return。 So that when we return from here will return back to user level。

 But what that really means is we're going to have to set things up and doing a return from trap that's going to then restore the user stack。

 Okay， but we're going to be able to think of it like we had user called into the kernel。

 and then it's going to run new thread。 And then it's going to call switch。 Okay。

 and we're going to have to talk about what switch is in a moment。

 But so all we're doing is we computed a digit of pie。

 we executed the yield system call that took us into the kernel we switched the stack。

 We execute run new thread。 Here's run new thread run new threads a procedure。 What does it do。 Well。

 it picks a new thread。 Kind of good given that it's called run new thread right。

 And then it does this switch magic。 And the switch magic basically takes the current thread and the new thread and it switches them in the sense that it saves the current thread out to its thread control block and loads from the new threads control block into the hardware。

 and registers。 And then we might do a little housekeeping like keeping track of how long the previous task was running and so on so we can get statistics later。

 Okay。 And so how does that switch actually happen。 Well。

 you got to save anything that the new thread may trash program counter register stack pointer and then maintain isolation for each thread。

 And then we don't overlap each other。 And we have to make sure we do that cleanly。 Okay。

 So I want to pause here just to make sure I've thrown a bunch of terms that you。

 And I've thrown this sort of stack picture which we're going to use a bunch of times in the next hour so I want to see does this all make sense everybody。

 Ask your question now。 Yeah。 And that's every process and in fact。

 for now every thread is going to have its own kernel stack。

 So it's not like there's one kernel stack。 There's a kernel stack per user thread。 Good question。

 And that's why we can explicitly think of them as matched up。 It's not hard。

 It's like when I switch to a new thread I'm going to get a new kernel stack as well。 Yes。

 So you're wondering where the TCB is stored。 So the TCB is stored inside the process control block right each process as a set of threads。

 Okay， so that's one answer。 And the different answer which you're going to find when we get to so that's the high level answer when you get to penthouse and you look inside you're going to find that a kernel stack is allocated with a unique page of memory for K。

 And a little bit of that page is TCB and the rest of it is kernel stack and those are always allocated together for cleanliness。

 Okay。 So for now just think of the TCB as in a separate place in memory and it's linked together for the process control block。

 Good。 Other questions。 So， chat here， can we inject code into a running process。

 Talking about how the JIT compilation mechanism works。

 So the answer is if you're in that process and you're a thread in that process then potentially you can inject code。

 And it may be to that a little bit later， another another time。

 but usually the code block is explicitly read only unless we're allowing JIT。 So that's a。

 Any other questions about this。 Yes。 So the user。 So this is。 So there's two ways to look at this。

 The question was how is this kernel thread and user thread related to each other， right。

 One answer could be， it's really only one thread because there's only you're either running at user level or kernel level never at the same time。

 Okay， so the one answer is they're not two separate threads they're really one thread。 Okay。

 Now there is a lot of terminology that even I will use because it's pretty standard talking about when we're running down here in the red portion we're running the kernel thread associated with the user thread。

 That's confusing。 But for now just think about every user half is attached to our kernel half and you're running in one or the other。

 Keep it at that way for now and we'll get more sophisticated at other times but I think certainly for the next couple of weeks that's the easiest way to think okay。

 Good question。 All right， should we move on。 So is everybody get what I mean when we go down here right we showed you this last time but compute pie is running and then it calls yield。

 And then it call which goes into the kernel calls kernel yield and then calls run new thread and then call switch。

 Okay， and it's somehow we're going to have to turn this into switching to the next process。

 And so what are the stacks really look like here and so I'm going to forget pie for a moment let's look at something simpler。

 And if you look here's an example where we have a procedure。

 A that calls be and then procedure be says while true yield and it just yields in a loop over and over again so this is the ultimate do nothing just yield all the time。

 Okay。 And so， suppose you got two threads s and T what do they look like well here's thread s。

 And so， so this is a first and a calls be which is that while loop。

 be calls yield yield goes into the kernel and switches。 Okay。

 Now what are we switching to well this was thread s thread s and T I running we got to get to T。

 So here's the magic。 Saves out all of the registers of thread s into the thread control block and loads registers from T from it's control block back into the hardware。

 One of those registers is the stack pointer。 So when we switch stack pointers。

 we're outside of this figure and we're suddenly inside this one。

 Because we switched the stack pointer。 Okay， and because we switched the stack pointer。

 We're still in switch but we're in switch。 We're in the stack frame from switch for the last time thread T switched。

 And so when we return from switch。 We're going to return to run new thread which will return back to user mode。

 which will return from yield which will go to the the wild loop which then we'll call yield。

 which then will call red run new thread which then will call switch。

 which then will switch the stack pointer and now we're back to the other way and we're going to go back and forth and back and forth。

 And now we have two things that are doing nothing but boy they're multiplexing well。 Okay。

 Now I'm going to pause here because this this either is obvious or drives people nuts。

 I found both cases。 So if you're one of the it's driving me nuts， ask your question。 It's fine。

 Good。 Good。 I like that question。 So the question is this this only makes sense if bread tea has already been running。

 Right。 But if Freddie hasn't already been running， this doesn't make sense。 Okay。 Yes。 That's true。

 So he has to be already ready。 What we're going to do in a few slides is we're going to show you how to set up a brand new tea in a way that will still work with this pattern and it'll look like it's already been running。

 But when we switch to it， it'll actually start itself up and look like this。 Okay。

 so what I would suggest you guys is for a moment。 Don't worry about how did we get here。

 Just worry about what we're doing while we're here and we'll talk about how to start this up in a moment。

 but that's a great observation。 Okay， so you only understand that this works。

 If thread tea was already running and they're already executed switch。 Okay， good。 Another question。

 Yeah， in the back。 Nope， we got to switch all of the。

 we got to switch all of the registers because we're going from one thread running to another thread running and it's a virtualization。

 where the threads got essentially， you know， all of the user level registers。 Okay。

 and so we're going to switch them all and in fact I'm going to show you assembly code for a version of switch in a second。

 Good。 Yes， go ahead。 Well， this case， the stacks are going to stay the same size。

 because notice that once we look at this code here right this code said be executes while which executes yield。

 And then sometime later later we're going to return from yield and go back and call yield again。

 So the fact that we've returned from yield means that we've actually returned across this boundary。

 which is shrinking the stack。 So we call call call call call call all the way down。

 and then eventually， even with switch and then we're going to return return return and back up。

 and then we're going to call down and so this particular example。

 which is doing nothing useful except being an example。 The stack grows down grows up， you know。

 grows down shrinks growth shrinks growth shrinks over and over again and the net effect is there they don't get any bigger than this。

 Okay， good question。 Yes。 Ah， well， so the question is why are thread T and executing the same code。

 So， think of this as a great example， where the program on disk。

 or the application is like a proto process and when you loaded into memory now it's a process and it's running。

 you can do that lots of time so there's no reason that we couldn't have compiled this program started on disk and then started S and T as two instances of it。

 Okay。 All right。 Other questions。 Okay， so this is kind of magic right。 Let's look at。

 So this is often called context switch。 So we're saving。

 We're switching to threads so we're switching the current thread and the new thread。

 And so what does that mean it means the TCB for the current thread。 We。

 we unload the physical registers and store them back， including this stack pointer。

 and maybe the return PC so this is like a risk five version of this。

 And then we load back all the registers from the new thread。 And then we execute return。

 And what is returned to return says， well， I'm going to return from this switch function call。

 but I'm returning based on the stack and registers I just loaded and so I'm returning back the way T would have done it back when T was running。

 Okay， and that's why this looks like this。 Okay， you know we got。

 we run down down down down and then we switch over to T。

 and then we return return return return return， but now we're on T stack and then we go down down down down down switch return return return return return return return return on S is stack and back and forth。

 And so part of the reason this is so weird is we've actually changed the stack pointer。

 And so we kind of changed the locality of execution to this other thread。 And believe me。

 if this is a good thing to ponder at parties and whatever you can be a great。

 great hit at the party to like can I tell you something really weird that I learned class today。

 but I found it sometimes just sleeping on this will help a little。 Any other questions。 Yes。

 one more go for it。 Is this code executing different address spaces that's what you're asking。

 So the answer is in this simple example we're not changing any of the address space so think of this is two threads in the same address space。



![](img/92632d7d853797ca01f9a2ab7bcecff1_9.png)

 Okay， because if you look at， you know this switch here doesn't change the any of the translation page tables anything。

 One more yeah。 How does thread access thread T structure。

 So the answer is we went into the kernel and the kernel has access to everything。

 And so those TCB's are distorted kernel space and so it chooses one chooses the other。

 So there's no there's no security violation here。 Yes， there's only one kernel。

 one kernel to rule them all。 Okay， these are little rings。 Yes。 There's only one kernel。 One kernel。



![](img/92632d7d853797ca01f9a2ab7bcecff1_11.png)

 There's only one kernel， but so the kernel is the code that's running at system level。

 So only one kernel， we go into the kernel， we come out of the kernel， we go into the kernel。

 we come out of the kernel。 One kernel to rule them all。 Only one kernel。

 So both T and S have the same kernel。 Now， T and S have different kernel stacks。

 but it's one kernel so so in fact look， see this code here。

 this is a sub routine running it kernel mode。 And it's accessing， you know。

 S is TCB and then T is TCB。 So， keep in mind that what is the kernel doing the kernel is the thing that is producing this virtual machine view that the threads are running it。

 So it's turning what was only one CPU into something that looks like it's got a bunch of CPUs but it's one kernel。

 many threads。 Good。 Okay。 So。 So， there's only one kernel， multiple kernel stacks and or threads。

 Okay， because the kernel stack is really defined by some chunks of memory so it's not hard to have lots of them。

 Okay， so should I go on。 We good。 Okay。 So what if you make a miss see this is a fairly simple routine。

 What if you screw it up。 What happens like you forget a register。 Yes。 Leak data。 Perhaps yes。

 But it's even worse than that。 So leaking data kind of somebody is a privacy violation that's bad。

 but it's worse than leaking data yes。 So， you know， it's not going to be overloading in what sense。

 So anybody want to else want to take a stab at what happens if you don't correctly switch。 But。

 Well， the system crashes yes or worse。 It's subtly screws everything up and you don't know what's going on。

 Okay， because those registers。 How many people have looked at the output of a compiler。 So。

 you know， it's a very simple thing。 You should take a look sometimes。

 There's a lot of register optimization。 The way registers are used is very complicated。

 And if we forget to save and restore one register。

 and maybe the thing runs perfectly well for a while。

 but it's going to start failing in some very subtle ways。 Because the whole notion of a thread。

 It's own CPU registers that are going to be good every time it's running and when you put something in a register。

 It's there the next time you look。 But if we screw up the switch routine it's perfectly possible that tea put something in a register then we switched over to s。

 s screwed it up when we came back to look for that thing it wasn't there properly。

 And now we got maybe a crash。 We'd be lucky with a crash maybe we've got something worse which is a corrupted computation。



![](img/92632d7d853797ca01f9a2ab7bcecff1_13.png)

 And then we're going to get to the switch。 So switch is important。 Okay。 And。

 and what's interesting about this so you can think of this is the most important thing inside the kernel that you got to get right is you got to get switch working properly。

 And can you come up with an exhaustive test of the switch routine to make sure you never forgot anything。

 So it would just be badly exponential and you'd never figured that out so you got to stare at it very carefully and then you get your friend to stare at it and then you get your friends friend to stare at it。

 And fortunately we don't ask you to， to write switch too much in this class because that would probably trigger our illegal cheating if you did too much of that but。

 And so the point is switch is important and you got to be careful with it。 Okay。

 And there's a cautionary tale that I always like to tell which is kind of fun so there was this kernel。

 Topaz。 And this is back in the days where one instruction made a huge difference because you can imagine that the switch overheads important。

 And so somebody was clever and managed to save one instruction in the switch routine。

 And they documented it they wrote a whole block of comments that said that as long as the kernel isn't bigger than a megabyte in size this is fine。

 Okay， and then several years later people forgot。 And they didn't read the comments。

 And so they just added a couple of things and the kernel got big enough that it was no longer a megabyte in size and then all of a sudden weird stuff started happening。

 Can you imagine so your kernels working fine you had a little bit and all of a sudden it's totally crashed。

 Okay， so you got to be really careful with the switch routine。 Okay。 By the way， how many bits。

 where are they dealing with where one megabyte mattered。 Quick。 Good。 You should know these things。

 This is good。 You know， again， this could be a party trick right。 I know my powers of two。 Okay。 So。

 I'm going to give you a lot of really good social recommendations here in this class。

 You listen to me， it'll be great。 So， project one is in full swing was it was put out yesterday。

 You should be doing it。 Okay。 And part of the first assignments with with project one is going to be a design document。

 There are some。 There are some basic sketches for what a designs document should look like that we're going to give you out。

 But， you know， think about the design document is something you would give to your boss or something which is explaining。

 What's your high level concept if there's going to be code it should be pseudo code。

 And not dumping 50 lines of C code。 Here's my here's what we're planning to do because the whole point is here's what we're planning to do right but we wrote 50 lines of C code。

 So， you know， think of the design doc is a high level description of what you're doing。 Okay。

 now the paradox here of course is what if you need code for the design document so pseudo code。

 Try to describe it in a way that your TAs can get it easily。 Okay。

 You have a permanent discussion session now since we did our group assignments。 And so。

 So we should be attending your permanent to discussion session Friday。 Okay。

 that'll be your first time。 There we want to have you come so your TAs can get to know you。

 If you're sick， don't come。 And that's also true of lecture here。

 We have ways around if you're sick。 Okay。 So， for one thing。

 there's a way to make up a loss discussion session， which you can find out。

 I think we have that on piazza。 We're also going to have rotating section leaders are going to record sessions so that there'll always be a recording of the discussion session for that week that we have for archival purposes and so you can study with it and stuff too so。

 Okay。 Mid term one is two weeks from today。 Okay， and it's seven to nine。

 We need you to fill out the the conflict quickly so we can figure out what to do with conflicts。

 We are that's two tomorrow so it's up on the。 It's up on the schedule。 Okay。

 And the topics are pretty much everything up to the day of the midterm。 The previous lecture。

 There might be a couple of things in there。 They won't be heavily tested but。 Okay。

 So Anthony points out that perhaps we're actually going to ask you to do a little bit of switch for。

 Point point units in project one so you'll get a little bit of a flavor on that。 Any questions。

 So we're， we're diving right in we're we're starting the class how many people have actually started the project like loaded it and looked at it。

 So for those of you that are on the on the net there everybody raised their hand。

 They're really on top of it so you guys ought to be too。 All right。

 So are we switching contacts in these previous examples well I called it a context which。

 Earlier we sort of said a context which was between processes so when you say a context which。

 You need to be clear what your context switching from okay so if you stay within the same address space and switch threads between each other。

 That's the example I previously gave you。 Okay， and that's much cheaper than switching the address basis in fact here's some numbers that are kind of give you a little bit of a flavor so from Linux。

 For instance， they contact switch every 10 to 100 milliseconds switching between processes is about three or four microseconds where switching between threads in a process is 100 nanoseconds it's faster。

 Okay。 Why is that well thread you to switch and registers。

 You actually have to switch the address context you have to flush。

 And so I wanted to give a little terminology here just so we kind of are on the same page here but if you notice we're talking about this。

 where we have one user thread per kernel thread now this is that possibly confusing terminology which I wanted to make sure everybody got。

 really one user stack per kernel stack。 Okay。 The reason they call this a kernel thread is this is a home for this this bottom half of this user thread to run when it's in the kernel。

 But there's several other options so here's an example where we can have a bunch of threads that are multiplex that user level and one kernel thread underneath。

 So the original Java was like that where you'd start a bunch of threads and there's only one kernel instance underneath。

 and the library multiplex the registers totally at user level。

 And as long as it properly executes yield， then you can have the equivalent of the kernel scheduler running totally at user level much cheaper than anything because you don't even have to go into the kernel。

 Okay。 Can anybody see what the downside of this model might be over this one。 Well remember we're。

 we're threads inside a process right now so you know at worst a bad thing is a bug not a security violation right。

 Anybody else have any idea what might be。 Yes。 So really。

 now remember we're assuming the kernel is okay so or the code's good so it's not that this one of these others let you screw it up but the point here is。

 if any one of these user threads goes to sleep in the kernel and I owe them they're all put the sleep because there's only one。

 kernel thread。 So you can think of the kernel half is a point to go to sleep on aisle。 Okay。

 And then last but not least you can have many threads and many kernel threads and you can multiplex them。

 We're really talking about this particularly simple model， which by the way。

 because of Linux has become fairly inexpensive。 And so the default threading model in Linux is basically this one on the left。

 Good。 So， let's go。 Let's push now with our stacks since we're all comfortable with them。

 So what happens when you don't execute yield but you're busy executing IO。

 So you're in a copy file routine。 You， you do a read。

 And that reads got to go into the kernel so a system call goes into the kernel。 Right。

 It gets the kernel stack executes kernel read actually showed you that code a few lectures ago。

 Okay， which does some stuff to set up the disk， let's say。

 gets it ready to go but now we need to switch to a different thread because I always a million instructions worth of time right。

 So here we call run new thread and switch。 And so this routine yielded implicitly by calling read。

 and then that read did its thing but then did a switch， and now we'll run something else。 Okay。

 the stack looks exactly like that example we gave earlier。 Okay。

 And it's similar for thread communication like signals and joins and networking all of this is kind of similar。

 And notice， now we can say it doesn't matter what caused you to switch。 Is it a yield， is it IO。

 It just works and switch will take you and gets another guy running， right。

 What about external events。 Okay， so what happens if a thread never does any IO never waits never yields while we said that that was a bug with the early versions of the Macintosh actually of Microsoft Windows too。

 And so， you know， we got a problem because what if compute pie never calls yield never calls prints anything out。

 We need a way for the dispatcher to get control and this is the external events。

 So the simplest idea is we set a timer off that's generating an interrupt and that interrupts causes us to enter the kernel and that point lets us do a schedule and switch。

 Okay。 But in principle what I'm going to show you here for timer work fine for any interrupt so packet coming off the network could take control back。

 Okay， and here you just have to make sure the external events happen frequently enough and then you can make sure that you're properly switching。



![](img/92632d7d853797ca01f9a2ab7bcecff1_15.png)

 So if you remember by the way， I showed you this picture so I'm not going to go into a detail but interrupts again。

 come from the outside their external， including a timer。

 They generate a physical signal that causes the CPU to jump to an interrupt vector。 Okay。

 And you'll be able to actually look at that code now that you've downloaded the process。

 The start the first project。

![](img/92632d7d853797ca01f9a2ab7bcecff1_17.png)

 Okay。 So， here's an example of what happens during a network interrupt。 So， to remind you。

 we didn't talk about this explicitly but here I'm executing along。 Okay。

 this is kind of like risk five assembly just for the sake of argument。 And the interrupt comes on。

 So what happens is that internal interrupt actually tells the processor stop executing。 So。

 it's a pipeline flush to get rid of the partially executed instructions。

 It saves the program counters and disables interrupts goes into kernel mode， kernel mode runs。

 And then it does the work of say transferring the network packet from hardware to kernel buffers。

 If you had a process that was running that web server code we showed you last time。

 And it executed a read from network， it's could be that it gets wick looking up at this point and it gets taken off of a weight cue and put back on the ready cue in this green。

 So， for everything we go back， and the user process keeps going。

 So the idea behind interrupt is it's a temporary interruption of what's running to go do something else and then come back。

 And the way that we can use this to help us switch is when we're in this green portion doing the interrupt handler portion of our timer。

 At that point， we can go ahead and do the switch and start somebody else running。

 And so here's an example， where I'm busy doing something， whatever it is。

 the timer interrupt happens。 So I've called， you could think of an interrupt as calling into the kernel。

 but it's a forced call that the user doesn't do anything with the interrupt forces you from user mode into the kernel。

 Okay， and what does that forcing do well it puts a kernel stack there。 Okay。

 and now that kernel stack， we run the interrupt code part of which will eventually call run new thread and switch。

 and now we can switch somebody else in， and we've just shown you how a timer interrupt can make sure that we keep switching regularly。

 Thanks。 And here's an example， you know our timer interrupt might do some periodic housekeeping and do other things and then call run new thread。

 All right， questions。 All right， yes。 So this is a good question so explain the red is what you're asking here so what happens when an interrupt happens。

 The first thing that goes on back in this picture here you can see is that the interrupt disabled bit。



![](img/92632d7d853797ca01f9a2ab7bcecff1_19.png)

 enables everything until the CPU can clean up the current interrupt and disable that one thing and get things ready to interrupt for other stuff and then it'll turn it back on again and go。

 So immediately disable everything then we'll get stuck in this loop where we're the hardware is just interrupting over and over again。

 whereas instead what happens is we enter， we turn them all off that's done in the hardware and then we disable that one interrupt and then we can turn them back on again。



![](img/92632d7d853797ca01f9a2ab7bcecff1_21.png)

 So， you can do it in different ways。 The question is shouldn't we reenable interrupts just at the very end。

 That always re enables them。 But you might want to re enable things that are higher priority that might be even more important than the one you're handling。

 Okay。 And we， we can talk more about this another time I don't want to get too distracted on this but you get the basic idea。

 And we can view that it's kind of raising priority of the interrupts will take will only take ones that are really high priority higher than the one I'm working on。

 Okay， good。 Any other questions about this。 So I think the key thing to get out of today's lecture is there's a wide variety of ways to get to switch。

 Okay， and if you design the way your stacks work in the kernel。

 then it's really easy to have external and internal events of a wide variety of types。

 Bring you back to the kernel scheduler so you can make sure that things keep running。

 And that's when you get to where you actually look at how that works inside the switch routines in the kernel。

 You'll see how that works。 Okay， and I think I either next time or the time after I haven't decided when exactly I'll actually show you even an explicit stack kind of arrangement for x86 and give you an idea how that works。

 Okay。 But so the idea is this way as long as we can get to this switch， we can change things out。

 Okay， any other questions， should I move on。 Now， let's get to the question that came up earlier。

 That S and T example was fine but that assumes that T has been running forever。

 And so let's talk about something that we could loosely call thread for。 Remember， I gave you the。

 the p threads API last time that's on a slide so there's p thread create and so on but let's just call it thread for for a moment。

 It's a user level procedure to create a new thread。

 The arguments to thread fork are in this case a pointer to the application routine you want to run so and arguments to it。

 And how much stack。 Now the reason this is different from fork is remember fork is giving us a brand new protection context and it's going to duplicate everything。

 We can't really pass pointers into somebody else's security context because that's kind of untrustable。

 And so that's why for just sort of says we're going to exactly execute where we were and give you a brand new security context。

 If we're inside of a threat process and we're making new threads。

 We can certainly give it a pointer to a routine so thread for just says well run this function in a new thread。

 Okay， here's the pointer。 Here's the arguments。 And then we'll do the size of the stack。 Okay。

 and so how do we build this。 Well， we'll do some sanity checking just to make sure that we don't screw anything up。

 We're going to enter kernel mode sanity check again。

 Just to make sure that the user isn't giving you total garbage here and then we'll allocate a new stack and TCB will initialize the TCB。

 Place it on the ready list is rightable and we're good to go。 But remember。

 we need to do this in a way that once we put it on the ready queue。

 even though it hasn't ever run before it looks like it ran before so that we can switch to it without changing any of what we just talked about。

 Okay， that's， that's going to be our goal。 So just like ST ST right。

 we want to be able to do that with T the first time T runs and in order to do that we have to fake out things a little bit so the stack looks just like it did as if he had been running for a long time。

 Okay， everybody with me on that。 And so how do we do that well。 We're。

 we got to get a new TCB because it's a brand new thread。

 We got to initialize some fields stack pointer in their pointing to a stack a PC return address。

 Pointing at something we might call thread route to argument registers。

 maybe for function and for the function pointer and the argument pointer。

 And what do we do with the stack。 Well， usually we don't have to do too much with the stack。

 we might at minimum， well， maximum， we might have to put like the return address on there。

 But otherwise there's no setup required。 But what we want to do is we want to fake this so that that stack。

 When we switch to it creates the thread。 You want to put it in a format so that switching to it。

 the system thinks it's been running forever， but what really happens is it just creates a thread right then in there。

 Okay， and the trick is， we're going to set it up。 What happens when you switch to thread T is what well you're going to return at that point。

 And so all we really have to do is set the return address in that new thread control block so that when we return we really instead of returning to something that was already there we just returned to the start of thread。

 and that's going to start everything。

![](img/92632d7d853797ca01f9a2ab7bcecff1_23.png)

 Okay， and so this is the way to think about it。 Here's another thread。

 This stub is a TCB that we've just crafted in a way that we can switch to it using the same switch code but when we go here it actually starts creating the thread。

 Right then in there。 Why can we possibly do that well。

 This the will switch to a new stack that new stack has got a return address on it。

 If we do return just like what happens when we switch to this one we go as if we were at the bottom here and we do a return as the first thing so we set it up so when we do a return it runs what we want。



![](img/92632d7d853797ca01f9a2ab7bcecff1_25.png)

 Okay， so you can think of it like this that we set up the new thread by setting up the registers in the TCB to have what the new stack pointer is to have a return that points at thread route and a few other things。

 And then when we switch to it it's going to do a return first thing and then the code is going to execute thread route whatever that is to set the thread up。

 Okay， the pause there for a sec。 Yes。 Can you say a little louder。

 Right so we're going to allocate the space for the new stack。

 So we allocate the stack will allocate a thread control block。

 But then we'll put a pointer to the top of the stack into the stack pointer in the TCB so that when we load that TCB we've got a new stack pointer pointing at the new stack。

 And the only other thing we need to do is set it up so that when we execute that one return at the very end of switch it returns by executing the beginning of the initialize routine for the thread。

 Good。 Again， this is one of these things that takes a little bit to stare at。 Okay。

 One more quick yeah go。 So thread route here I'll show you what thread route is。



![](img/92632d7d853797ca01f9a2ab7bcecff1_27.png)

 Okay， here you go。 So it's something that takes a function pointer and some arguments。

 And it does some startup housekeeping like it sets up some zeros some counters and so on。

 It goes to user mode。 And then it calls the function pointer with the arguments。

 And then if that ever returns back it calls thread finish which shuts everything down。 Okay。

 so it's it's really pretty simple。 So startup housekeeping records start of time of thread so on。

 And so really if you were to look at the stack right after thread route starts running we have this little bit that's it user kernel mode。

 And then it calls the thread code kind of right here where we call the function pointer。 Okay。

 and so at that point we have a new stack frame which is for the beginning of the function we said we wanted。

 And from that point on it'll work fine because however we get to switch whether we yield or we get an interrupt whatever that's all now in process。

 So the only magic was really the very first time getting to where we kind of get to the beginning of this routine and executed and from that point on it just works exactly like everything I said earlier。

 And so in the case of thread T。 What happened originally was there was a thread route。

 It did a user mode switch it called that function a。

 And now it got this stack and now it starts running and eventually we get to a point where we enter the kernel on yield and switch and then we go over to whatever else to run。

 Okay。 So here's a question what is switching from user mode to kernel mode look like and vice versa。

 Is it a flag so it's a processor flag。 There's a， remember we talked about dual mode very first day and second day。

 There's something in the hardware that says your kernel motor user mode。

 And going from kernel mode to user mode easy， because there's no security violation the kernel one kernel kernel rule them all。

 Going from user mode to kernel mode that's where we have to be careful and we said that last time。

 No， a couple of times ago。 It's control。 So you can do it with a system call you can do it with an interrupt whatever but it's got to go through a vector to well define piece of code in the kernel before you go to kernel mode。

 Okay。 So that's that controlled entry。 Okay。 All right。 Questions。 Yes。

 So good questions you're talking about right here with the call。

 How does it know to put things into the thread stack instead of the kernel stack is that what you asked。

 So the good question so the way we know the reason this function call has the correct stack is we set up thread route so that when we switch to it the very first time it gets a pointer to the new stack。

 In the stack register that was how that's the， that's the whole magic behind this。

 Notice right here we set the new stack pointer into it into the TCB。 So that one switch loads it。



![](img/92632d7d853797ca01f9a2ab7bcecff1_29.png)

 Well， we have the new stack right then and there。 And so from that point on we're just executing normally and it uses the stack because it's got the stack。



![](img/92632d7d853797ca01f9a2ab7bcecff1_31.png)

 Okay。 Yes。 Yep。 Well， there's only so every thread has one stack。 Well。

 it has to it's got a kernel and a user stack but that there is a stack。

 There's no difference between execution stack and another stack there's the stack。 So， so the stack。

 So we're not actually storing the。 So we're the function here。

 We're not executing this code in the stack。 This code is in the code block we're executing this code using the stack。

 So this is representing all of the variables that are being stored。 Yeah。

 I'm sorry if this has been so that would have been a good question earlier if that's been confusing so when we say this。



![](img/92632d7d853797ca01f9a2ab7bcecff1_33.png)

 Every function call allocates a new stack frame。 And what this says is a did get a stack frame but there wasn't any data the store in there。

 So the only thing actually and there's going to be the return。 But。

 so this actually this isn't the functions we're calling and this is the actual stack frame and I'm showing you the traces we go through and back。

 Good。 Sorry。 I'm glad you asked that question。

![](img/92632d7d853797ca01f9a2ab7bcecff1_35.png)

 Yes。 So the question is， is it reasonable to assume that this top has a thread route of every thread looks like this。

 Yes， that would be true。 And then of course this is going to depend a lot on the operating system as to what it actually looks like but everything I say here is something that would go in every thread when it starts up。

 Good。 Okay， so let me talk a little bit about processes versus threads so we have one core。



![](img/92632d7d853797ca01f9a2ab7bcecff1_37.png)

 You can think of one core we're multiplexing back and forth。

 You could have many threads per process and now you can start to see how we can just have many things executing at the same time。

 And then we have two quotes， even though we only have one CPU because we just switch back and forth。

 Okay。 Now， multi core by that notion isn't that much more complicated。 Really。

 we just have a bunch of cores， each of which can be scheduled in the way we're talking about it so now you can have say in this case。

 four things actually in parallel。 And then a scheduler can choose to take one of them away from one thread and give a different thread and so the scheduler has multiple physical processes。

 processors to use。

![](img/92632d7d853797ca01f9a2ab7bcecff1_39.png)

 Okay。 And then of course we talked about simultaneous multi threading。 In that instance。

 now this diagram hopefully will make a little more sense in the middle here。

 we have a two core situation where we have two cores， each of them are super scalar。

 And so time goes down and so here we see three possible slots。

 only two of which are doing something useful on core one。 And then we have two slots。

 three slots only two of which are doing something useful on core to hyper threading we just mix those together so we fill up all the slots and do better hardware utilization。



![](img/92632d7d853797ca01f9a2ab7bcecff1_41.png)

 But from a model of today's standpoint。 You could think of this is actually being。

 even though we have four cores with two hyper threads per core you could think of this as eight total physical cores running simultaneously from the standpoint。

 right now。 And then we're talking about， there are some performance differences there but from the standpoint of this lecture。

 this is just like an eight core processor。 Okay。 And that swapping back and forth is something that you hopefully can generalize when you have more than one core or more than one hyper thread。

 something you can easily think about unloading， loading。

 and you do that on all the cores at different times and you can get scheduling， Okay。 So。

 so we can start thinking about some of our options here right so most operating systems have either one or many address spaces。

 most of them today have many。

![](img/92632d7d853797ca01f9a2ab7bcecff1_43.png)

 And they can have one thread for address space or many threads for address space so this gives us four kind of options right here in the middle in the one one category is the early Mac and Tasha's MS dots。

 where there was kind of one address space unprotected and one thread running at once。

 Pretty primitive。 We can have sort of one address space and many threads that's kind of where bed and operating systems that you might have on little devices might run。

 You can have sort of one thread for address space and many address spaces that's kind of traditional Unix where you only had one thread for process。

 And then modern things are all in this lower corner that where you can have many processes many threads for process。

 Okay。

![](img/92632d7d853797ca01f9a2ab7bcecff1_45.png)

 So， as we have about， we have about 10 minutes left today I want to。

 I didn't get a break in today I apologize， but you guys stay with me for 10 minutes。

 I want to do a few definitions here just to be on the same page so multi processing typically means multiple CPUs or cores going on at the same time。

 Okay。 And here I'm using CPU and core interchangeably。

 Multi programming is typically multiple jobs or processes really says there's more than one app running at the same time kind of。

 Okay。 And then multi threading is typically used as multiple threads per process。 Now。

 I did see on Piazza a question once well with hyper threading can each of the two hyper threads be in a different process and the answers。

 Yes。 Okay， so they really are like different course but for now when I say multi threading unless I'm saying。

 unless I specify assume I'm talking about multiple threads in a process。 Okay。

 and so what does it mean to run two threads concurrently。

 This says that the two threads look like they're running at the same time。

 So we've been talking about concurrent execution today。 One CPU multiple threads alternating。 Okay。

 And multi processing is really when here's three threads green magenta and blue。

 And basically they really are running at the same time because there's three cores。

 We really do have these things running at same time。 Multi programming is wider and includes。

 includes concurrency。 So here， we can have ABC。 And there may be only one CPU so these aren't actually running at the same time but they're alternating。

 And so a B and C have to be properly designed so that they'll work correctly。

 No matter what the interleaving so for instance notice that I give you two interleavings。

 one at the top where a runs until it's done be run so it's done see runs till it's done。

 Down here we alternate ABC ABC ABC come up with some other random way of doing that you should assume the scheduler could do that to you。

 Okay， so this is what I like to think of is assume adversarial scheduling。

 And then in our code we're going to assume that if you have a bug that could get screwed up by a particular ordering the scheduler will find it for you and it'll probably be like three in the morning。

 Okay。 Everybody with me on this。 So this at the bottom ought to be something to really motivate us moving forward the next couple of lectures because whenever we've got either multi processing where things are really running at same time or multi programming with concurrency。

 We need to design our applications so that they work properly no matter what ordering happens to come to pass。

 And that's going to be designed for correctness， not design test the bechievers out of it。

 And hope you find all the bugs right because that will be guaranteed to never work properly。 Okay。

 and you'll discover the problem at three in the morning。 Okay。

 or actually you're even worse your partner will discover one of your partners will discover it three in the morning and you'll be catching a nap。

 At the time， so， so correctness for systems with concurrent threads is interesting right so if a dispatcher scheduler can schedule the threads in any way。

 programs must work under all circumstances。 All circumstances， can you test for this。 No。 Now。

 there's some very cool work being done by folks in our faculty and other faculty trying to test whether something is mostly correct under concurrency。

 They can do it to a certain depth of inner of exchanges and so on。

 But you have to imagine that it's very hard to test all possible schedules to see whether any of them have books。

 Very hard。 Okay， and so really we want to design correctly for the at the beginning and that's going to be our goal。

 We're going to understand how to do synchronization。 It's a word you'll learn a lot about。

 In a way that the code is correct。 Now the one slight case where you don't have to worry so much about this is if the threads are really independent of each other they're not using the same data。

 You know there's no， there's no state shared with other threads。 The result can be deterministic。

 Okay， where the input state determines the result no matter what's going on because they're just running。

 Doesn't matter that these other two threads are computing E and pie simultaneously and doing some other complicated thing。

 This thread is unrelated anybody else it can run to completion。

 And you get a deterministic reproducible result。 And it doesn't matter the interleaving right because this thing runs for a while and then you switch up and it runs again。

 It doesn't matter what these other threads did because this is totally independent。 Awesome。 Okay。

 unfortunately， that doesn't happen too often。 Especially since you're all sharing the one operating system girl。

 That's a spot in the middle， but cooperating threads give you much more power。

 but they're also more problematic and why we have to be careful about how we design things。

 So the problem is if you have two threads and they're sharing data and they're scheduling concurrently。

 then。 And they're non deterministic problems it's not reproducible。

 We often call these highs and bugs。 Okay。 And they really are like the Heisenberg principle because these are the kind of bugs that if you got a bug。

 and you put print apps in to try to find it the print apps will make the bug go away。 Okay。

 so if you if you look at it， it's gone。 Okay， so highs and bugs are annoying and dangerous and we want to make sure that we have as few of them as we can by designing for correctness。

 Okay， have I gotten off my soapbox yet designed for correctness design for correctness。

 So interactions。 I just leave the print up and it's what came up on the chat here。

 And I'm not going to leave me people do that。 So， is any program truly independent。

 So every process shares the same file system OS resources network。

 You can imagine example buggy device driver causes thread a crash independent of thread B。

 but now be is done right。 And imagine an evil C compiler。

 which modifies files behind your back by inserting errors into the C program unless you insert the debugging code and then it compiles it perfectly。

 That you laugh。 There were actually a couple of famous hacks like that where it figured out whether you're trying to debug it and did the right thing when you weren't when you were debugging。

 But the thing to note is debugging statements can actually overrun your stack in some instances and so by inserting the debugging statements you can screw everything up。

 So this is going to be something to think about。 And non deterministic errors which are errors that are different every time you run it are very hard to find。

 You know memory layout of kernel and user might change each time you run it。

 or I oh my cause problems okay so these are going to be interesting to play with it。 Okay。

 you have now entered the domain of the twilight zone of non deterministic books。 Okay。

 those are not the bugs that you were looking for。 So why even allow cooperating threads so people cooperate。

 Computers help and enhance people's lives and you need to have interaction which is going to mean concurrency。

 because we're going to have people entering stuff on the one hand on a keypad plus we got to compute stuff plus we have other input。

 We're looking at a camera。 So we're going to be able to have concurrency。

 And so we're going to have to figure out how to do that。

 And so one advantage of cooperating threads is really you can share resources one computer。

 many users， one bank balance many atms etc。 You can get speed up so if you have multiple core and more threads。

 then you can actually get things go faster if it's parallel you've learned about that and 61 see I think indeed probably did some parallelism right。

 And there's actually a modularity advantage to splitting things up into different processes。

 for instance， so the compiler GCC actually calls the CPU processor and pipes it into two code phases and pipes it into an assembler and a loader。

 By splitting into separate programs it might be easier to debug。

 And then you just time together and that turns out to be a nice pipeline so there's a lot of advantages to parallelism if you can get it under control。

 You know， we're going to close with a couple of quick examples and then we're going to pick this up next time but if you remember the web server we were talking about where we have this non cooperating version of a web server。

 where we accept the connection。 And we get a new fork and go forward。 That can be kind of expensive。

 Because every connection has to load its own kind of file state and web cache and all that sort of stuff。

 Wouldn't it be nice to have the threads together。 Okay， and so this was the threaded version。

 where we accept the connection and fork a new thread looks the same but it has a bunch of advantages from a performance standpoint the threads are lower cost to create。

 And you can share state。 So they have two different people request the same thing。

 You have state that's cash and it can be a lot faster。

 And obviously you are all thinking about the security concepts， but let's hold that off for now。

 But if you remember， I mentioned this one big problem with a lot of threads for performance is now somebody can figure out how to exploit that and that's sort of the so called。

 effect， where they actually cause so many connections that you generate so many threads that you crash your operating system。

 Okay， and if you remember， I gave you this idea， which is bounding your concurrency by using something that's typically called a thread pool。

 All right， and the idea is see all these threads here。

 So the connections come in for the outside they're picked up by a master thread that does accept。

 It puts them on a queue， and then we have a bounded number of threads 20。

 And the idea is that we're only running 20 connections at a time and when a thread exits it grabs the next connection。

 And therefore we have a bounded pool of threads。 And you can kind of see the idea here is the master puts it accepts and puts on the queue。

 and the workers pull off the queue。 Okay， and that's a way to control threading。 So。

 with that we've run out of time I just want to say in conclusion， hold on， don't go away。

 Processes have the two parts they have the threads which we spent a lot of time talking about that's the concurrency piece。

 and the address base。 And the question piece。 Various textbooks talk about processes they often mean an original old style Unix process with one thread for process。

 We'll talk about multiple threads。 We started to talk about concurrent threads being very useful next time。

 We're going to dive into the question about what happens when you have threads that are sharing data。

 And that's not fail。 Okay， and that's going to be the problems that they're introduced so you guys have a great weekend。

 Get working on your project， because I know you all raised your hand when I asked who was。

 and we will go to your section tomorrow and we'll see you on Tuesday。 second。



![](img/92632d7d853797ca01f9a2ab7bcecff1_47.png)