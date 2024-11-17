# P7：Lecture 7： Synchronization 2 Concurrency (Con't), Lock Implementation, Atom - RubatoTheEmber - BV1L541117gr

 Okay。 Welcome everybody to CS162。

![](img/53a0bbd96bce73194524f58499453c5d_1.png)

 Real lifestyle， which is always kind of nice。 Today we're going to pick up where we left off and start really pushing on implementation。 of threads。 And then we're going to move into some of the consequences of threads when we start。 worrying about synchronization。 So， if you remember from last time we had this example。 which always stymies people the， first time they hear it or see it。

 So let's briefly remember the idea is we have two threads S and T。 The fact that there's。 two threads running the same code should not be mysterious to you。 We could either， you know。 the code is on disk。 We could either have two separate processes or we could have two threads within a process。 both of which are starting that code。 So that's not mysterious。

 And remember every thread has its own stack。 So when thread S runs we've got A calls B。 B goes into loop with while it calls yield。 That takes us into the kernel which calls run new thread which calls switch。 So run new thread is really a proxy for our scheduler right now。 It's going to make a decision about which thread。 And we're going to have a whole couple。

 several lectures on scheduling。 Okay， because that decision of which next thread。 lots of interesting possibilities。 Okay， if you can think of it。 it's probably been done by somebody。 But back to this， run new thread picks a new thread to run。 Hence its name。 Then it calls switch and switch does what？ Well it swaps the registers in thread S。

 saves them to the TCB and loads the registers from， T。 one of those registers happens to be a stack pointer。 So the fact that switch switched S for T means poof。 Suddenly we're in T stack。 That's why there's this arrow here。 And then we kind of go backwards up the stack。 Okay。

 now this is an imperfect animation that I gave you there but you get the idea that。 just as soon as the stack pointer switch suddenly we're in this switch over here。 And so when we return from switch we end up returning to run new thread which returns。 back to yield which returns to while。 The while loop calls yield， yields goes into run new thread。

 thread calls switch。 We'll say there's only two threads in the world， switch calls。 switches out thread T for， thread S and the whole thing happens again。 Okay。 and I want to pause here because I know there is already some discussion on Piazza。 as though what does this mean？ So go ahead， ask me， what does this mean question？

 Presumably something to do with this slide。 What does this mean that the daffodils are blooming？ No。 nothing like that but yes。 Good syntax too by the way， what did you mean？ I like that。 Okay。 go ahead。 Okay， good question。 The question is when I said， when I gave this example。 what did I say we went back up the， stack？ Okay， good。 So let's answer that。

 Let's go back to this point。 So you understand the idea that each time we call a new procedure we get a new stack frame。 and that's going to be where local variables are stored， that's where the return address， is stored。 And so if we only had one thread， yes， what would happen is A would call B， B would call， yield。 yield would call a new thread， we would switch， which would do nothing and then we return。

 from switch， which would actually erase that switch stack， then we would return run from。 new thread which would erase that one and then we would return to yield which would erase。 that one and we backed it back in the while loop and then we'd do it all over again。 Okay。 So if you get what I just said there， the way to think about this whole thing is the moment。

 we swap S and T， S is like in the Twilight Zone frozen。 And as soon as we swap back。 S just picks up with that return just like I said because， of the way we did this。 We made it clean enough that as soon as we swap back to S， it's really just like this。 where we return and go back up the stack。 Okay。 Anybody else？ Yes。 So no。

 run new thread does not restart from A。 So remember the reason， excuse me， the。 constraints of this example were that S and T have been running for a long time。 So T at the point here where we switched to T， T was running before。 And so its stack is already like that。 So we're returning to switch not to A。

 So we return to switch and we return our way back。 up and come back down again and return our way back up。 Okay。 This is probably the hardest slide that I'll cover in this class。 So it's kind of， kind of。 and I'm going to show you a really funny quote in just a little， bit about understanding this。

 Go ahead。 Right。 So when it's， when we take S all the way down to switch， the question was。 and then go， somewhere else， does a suspended thread always look exactly like this？ Yes。 Well。 except， I mean， it has to be running this code， which， you know， I don't think any of。 you are going to run that code because it's boring， but you get the idea， it'll always。

 have switch at the very bottom of the stack。 Good。 Okay。 Okay。 Do I dare move on？ Yes。 When。 when the kernel calls switch here， all it's doing is it's swapping switch swaps the。 registers and then you return from switch， but when you return， you've already swapped。 to the different stack。 So when you， as soon as you call switch here and then you start returning。

 you're actually， in a different thread and you return back up that stack。 So you haven't changed code any， you're running the same switch code。 It's just here in a different stack at that point。 Spooky。 Okay。 Yes。 It's not going to the switch code。 It's the same switch code。

 but it's done as it's changed the stack。 So when the same switch code hits return。 it does something else than it was going to do， if it stayed on S。 Yes。 Ah。 why don't you hold that question for a moment。 That's a good question。 How do we know where T is？

 Okay。 So let me give you guys give me permission to go on the next slide here。 So let's。 let's just go for a little bit here。 The other thing I wanted to recall is exactly what we just did with yield works fine with。 timer interrupts as well。 So the timer interrupts an involuntary yanking of you from user mode into kernel mode。 but， notice that run new thread and switch are down at the bottom。

 And so really at this point it'll switch to TRS or whatever else is ready。 Okay。 And the other thing we talked last time， which I didn't put back here is how do you start。 a thread from scratch？ You got to set up the stack so that when switch goes to it。 it thinks it's going to a switch， it's a thing that's running， but when it goes to it and returns。

 it actually starts with， red running。 Okay。 So it's a simple paradigm across a whole bunch of things。 Okay。 So the question is also in the， in the chat here， but even if thread T's not run， will we。 still switch back to S given that we will start thread T first？ Yes。 So if we were in a situation where T hasn't run yet and we did this， what had really happened。

 is that's the one instance where switching to it will start from A and run the way through。 because we've set it up as a stub and then it'll look like this from that point on。 Okay。 I'm going to， I'm going to move forward here。 So on this is basically the idea of how we get the scheduler control so that we run。 run new thread regularly enough to swap things and make a decision about what to do。 Okay。

 And that's for a whole nother lecture。 Okay。 Now， I wanted to give you a little grounding here in actual reality。 So if you were to look inside Pintos， there are， there's an x86 processor code there for。 handling x86。 And really this idea of there's a kernel stack that gets swapped in as soon as you go。 into kernel mode， all of that stuff is supported directly by the x86 registers。 So for instance。

 there's a TSS that's been set up for exceptions and for the processor， level zero。 which is a kernel， you put a stack in there so that as soon as you go into， the kernel。 that's the stack that gets swapped in。 Okay。 And you'll see that code if you start looking at things like TSS dot C and inter stub dot。 tap S。 Okay。 And so once we get into the kernel， what do we do？

 We've swapped or we've saved the user's stack and program counter。 We've put in the kernel stack and， and a program counter。 And so really this craziness here going from blue to red is really using in our case in。 Pintos the features of x86 that automatically switch the stacks for us when we make that transition。

 because SIS calls a type of exception。 It's like an interrupt， just like whatever。 So we have to have preset that up in the kernel so that that switch will happen。 Okay。 And。 and then when you return out of the kernel and back， that same part of the hardware in。 x86 will restore the user's program counter and stack。

 So that's why I go to the trouble or the non trouble of just making this look like really。 we're just doing a function call into the kernel。 Okay。 So the user stack is growing but when we went from blue to red it was a different stack。 But once you've got that set up， you don't have to think about that。

 You're just procedure calling into the kernel and you're doing stuff and then you return。 back out of the kernel。 That little transition is handled by x86 hardware for you guys and a lot of other processors。 It's more software related but I want you to get to where you're just thinking like your。 procedure calling into the kernel and back。 Okay。 So for instance， here's an example。

 here we're running the code and we've got our， the user。 is happily running and remember every user thread is actually got a corresponding kernel。 thread and it's sitting here waiting。 Okay。 And what happens there is when there's an interrupt。 so notice that we have the CS， CIP， that's the code pointer or the instruction pointer and then we have a stack pointer。

 And as soon as we go across that， notice that what happened was the hardware switched us。 to the hardware's stack which is down here and the hardware's instruction pointer which。 has to do with whatever exception we did。 Okay。 And then at that point。 the original user's program counter and stack are actually pushed， onto the kernel stack。 Okay。

 So see what， see what we did there。 So here， here's the user's program counter and stack。 And as soon as we make this call into the kernel， those two registers are pushed on。 the stack automatically by the hardware。 And now we're set up with a program counter and a stack pointer from。 for the kernel。 And now we just keep procedure calling in the kernel。

 I had a lot of people ask on Piazza something like， why does the kernel need a stack？ Well。 for the same reason the user needs a stack。 Okay。 So you see it's got to have some place to put return values and local variables。 Okay。 So， and now there's also a page table base register which is going to be the same in。 this simple instance。 But the fact that we're in the kernel means that the page table。

 we'll talk about this， in several lectures later。 But you can mark certain entries as only available to the kernel。 And so just by going into kernel mode， suddenly the kernel space is available to the kernel。 Okay。 Again， that's a hardware feature。 All right。 And now we can run。 Okay。 This kernel is busy doing something interesting。 Maybe it's a read system call or something。 Okay。

 And then we're getting ready to resume。 And so at that point。 what we're going to have to do is undo what we did over here。 which is we got to restore the program counter and stack。 Okay。 And that'll be done by this interrupt return。 And now we're back running off of the user stack。

 Question， yes。 Yes。 Now， what's the notion of atomic atomic means uninterruptible。 And we'll talk about that in a moment。 So saying it does it atomically doesn't mean that it's all in one cycle necessarily。 but， it means it's not interruptible。 Okay。 But it turns out that there are a lot of things much simpler than x86 that don't have that。 level of sophistication。 And you don't， there's， there's a small set of things you actually need to do atomically。

 and the rest of them you could do in software。 Okay。 But I think this is an easy way to think about this for now until you get comfortable with。 these ideas。 Okay。 There's another question。 Yeah。 Good。 How does the hardware know the address of the kernel stack？

 The answer is if you look in these things， there's called a TSS trap segment register that。 actually you put that you store the kernel stack in it so that when the hardware does。 do that transition， it knows where to get it from。 And you'll be able to look at the C code to see that how that sets up。 Good question。 Okay。

 So the kernel stack is preset when you're boot up。 Not quite。 What happens is the kernel stack needs to be preset when you switch to a new thread group。 Remember。 every user threads got a kernel stack。 And so when the scheduler switches。 it's going to have to change that out。 Okay。 But essentially you're doing that in advance before you return back to user mode。

 Yes。 Which I think is where you're going with that。 Go ahead。 Right here。 Now。 you were so it's not got its own registers。 It's got its own register values。 Okay。 So， you know。 it's got its own processor。 And when we do this transition。 what happened here was the hardware put in the program counter， and stack pointer for the kernel。

 And then it also saves the users stuff on that kernel stack。 Okay。 Now。 not all hardware does that for you。 X86 does it that way。 Okay。 And that means that now we're just running away lower in the stack。 Remember how I had red stuff that went down further？

 And it was when we return enough that we get back to this point where we do an iret。 And there we restore from here off of the stack， we restore the registers back to run。 Now the only registers that are affected by this are the ones that absolutely get trashed。 when you go into the kernel， namely the program counter and the stack pointer。

 It's going to be up to the kernel to save and restore everything else。 Okay。 So you have to do that correctly。 Good。 Anybody else？ Okay。 Go ahead。 So the page stable base register is shared between the kernel and the user because you。 can mark entries as only being available to the kernel。 Okay。 Now。

 at the risk of confusing everything here， I'm going to point out that there was some。 pretty crazy things that happened in 2017 where there was something called meltdown where。 they figured out how to yank things out of the kernel even though they weren't supposed， to。 We'll talk about it later in the term， but the net effect was that the number of things。

 of the kernels that's in the user base table or user page table has to be very small。 And so today when you switch， you're going to have to actually switch to a different page。 table in general， but it used to be like this up until 2017。 We'll talk much more about that。 Okay。 And I didn't want to go down that path yet。 I did want to show you this。

 So here's a case where we're scheduling and we're going to do a context switch。 Notice how there was an interrupt， but you only know that because I said there was one。 And we're at the same point here。 It looks almost identical to the way it was when we did a system call into the kernel。 But what's different is we're going to now schedule somebody new。 And at that point。

 we're scheduling by swapping in a new user thread， kernel stack pair， user， stack， kernel stack。 That's why things are green。 And notice the page table base registers is definitely different because this is potentially。 a different process。 And then now we just do the return and now look。 we're running green instead of blue。 There we just scheduled。 Okay。

 I'm going to let you ponder that for a moment。 I'm going to show you this in a that was kind of a time based thing。 This is more spatial。 So Pintos， the version that you start with only has one thread per process。 We actually let you change that a little bit later in the term。 But what does that mean？

 That means that kind of in a process， we've got the user mode here， which is below and。 below kernel modes above， so in user mode， there's code data heap stack for the user。 And then above is a kernel stack。 But in Pintos， that kernel stack is actually a whole page in size 4k and there's a chunk。 at the bottom of that page that is the TCB。 Okay。 So they actually put that on the bottom of the page and there's a spot to save the stack。

 pointer and that points to the top of the page。 So is this。 are we going to use the kernel stack to compute Fibonacci？ Why or why not？

 Anybody know why I'm asking？ Go ahead。 There you go。 This is an extremely limited stack size。 But the kernel screws up and does anything too recursive， it'll overwrite the TCB and it'll， be bad。 Okay。 Don't do that。 Okay。 Dr。 it hurts when I overwrite my stack。 Don't do that。 Okay。 So what I wanted to show you here is， for instance， if we're in a user thread and the。

 kernel thread is not functional， but the kernel thread， a kernel threads really a stack。 that's paired up with the user thread， then we look like this where the instruction pointer。 which is the PC and the stack pointer are pointing into the user's space and we've loaded up。 the kernel stack pointer in that special register to point at where it's going to be swapped， in。

 So now we're happily computing Fibonacci here。 And if we make a system call。 the hardware has enough information here to now swap in， the new kernel stack。 which will be here and go ahead and save stuff。 Okay。 Now， here's a different thing to look at。 So notice this has got a kernel thread or kernel stack paired with the user thread or， user's stack。

 No， we've got some things over here with no user component。 There were a lot of questions on Piazza。 Well， does the kernel have threads that just do their own thing？ Yes。 So here's an example of threads that never go back to user mode or never had a user mode。 They run only in the kernel doing， you know， maintenance like stuff， flushing out blocks， the disk。

 et cetera。 So the nice thing about this is the way we've set this up。 the kernel portion of these looks， identical regardless of whether it was a user thread or not。 And so the scheduler can schedule between these threads， all the ones that have different。 user code associated with them and kernel code。 It's all the same。 Okay。 What is it？ Well。

 let's look。 Here we go。 We're running inside the kernel。 Okay。 On a kernel thread。 And here in that case， the program counter and the stack pointer are pointing inside the。 kernel and we never return back to where we're pointing at user space。 Yes。 I see。 Well。 can you see that？ Let's see。 Oh， I guess that， oh， my pointer isn't showing up on the screen。

 I apologize。 So what I'm referring to here is I'll have to figure out how to do that。 But let's see。 Is this laser pointer work？ Let's check this。 Let's try this。 Ooh， there we go。 How's that？

 That's a lot bigger than invisible。 So okay。 So what I'm talking about here。 thank you for pointing that out， is in this case， notice。 that this is the user's stack and we're running over here and the hardware has the kernel stack。 set up so that when we make a system call in， we will use that stack。 But in this case。

 we're already running with this stack and notice how the stack pointer。 is pointing inside that stack and of course the instruction pointer is pointing in the。 kernel code somewhere。 That's an instance of just running something that's going to stay in the kernel。 And so now as long as we have a way to switch between the different kernel threads with。

 the scheduler， then we'll automatically give CPU time to both the user's threads and the。 kernel threads and now the scheduler can do whatever it wants。 Okay， which gets us back to policy。 So this is why people call the second half of a user thread a kernel thread。 I'm a little bit conflicted as to whether I like that terminology。 From this slide。

 it makes perfect sense but oftentimes it's confusing people。 So the other thing is just， you know。 every user's stack has a kernel stack。 Okay。 Now we can go further with this。 Here's an example of that original thread that just took a system call and notice in， this instance。 what's happening is， I don't know if you noticed， let's see， here， there。

 was really nothing where at the top of the stack， when we get here， we've actually pushed。 the user's registers on that kernel stack and now we're busy running into kernels。 That would be the example of a system call to do a read。 We're now running on that stack。 And then when we return back， we returned across that boundary， we're back at the user， level。 Okay。

 Now， what does Pintos look like？ Let's see if I can turn this off now without too much challenge。 Let's see， what if I just， oh， turned it off。 Let's see， okay， no。 Good。 All right， here。 now experts。 So here， let's look briefly at Pintos interrupt processing。 So here we have the hardware vector， which when a hardware interrupt， such as the timer。

 which is OX20， that's 32， happens， it goes to a vector set up by the kernel that says。 run these instructions。 And those instructions could be unique to the vector， but in fact。 in Pintos， what happens， is they just push which interrupt it was on the stack and then they call common code。 which saves all the rest of the registers。 Remember how I said you have to save all the users' registers。

 but the kernel only saves， two of them。 So that's the code that saves them all， set up the computer。 the kernel environment， calls， the interrupt handler itself， okay。 and that's going to run something to do with the timer。 So here we have a situation where we're going to go user to kernel with an interrupt vector。

 Here's the interrupt vector。 It points the parts in the code。 And when we get that interrupt。 we actually transfer here， and again， I got to show you， this laser pointer。 So here again。 after the interrupt， now we've got stack pointer and thread running in there。 and we could go ahead and schedule and switch to a different stack if we wanted to， just。

 like with a system call， we could schedule and go to a different stack。 So going in there and interrupt， going in with a syst call， whatever， it all looks the。 same at the kernel level， and that's why it's easy to schedule。 Okay。 So I don't want to go too much longer on this because we'll run your brains。

 We'll start turning into mush， but I did want to point out that once we get to this point。 we call the interrupt handler， and that interrupt handler then goes ahead and does another dispatch。 inside a pintos of， well， what do I actually do with the timer？ And that point。 the timer calls tick and then thread tick， which potentially does nothing， in return。

 The timer can go off some number of times and the codes keeps going。 Okay。 or thread tick could yield call thread yield， in which case we're going to schedule。 And in that case， we just switch to another thread by swapping out the instruction pointer。 and the stack pointer。 And now when we return back up the path。

 we're now running on this other thread。 So there was s and t。 Okay。 Now。 I'm going to let you guys play with that a little bit more on your own， but I wanted。 you to see this is kind of like the spatial version of all this。 Okay。 Oh， in the back。 Yeah。 go ahead。 So the kernel， there is only one TCB。 That's this kind of off colored tan thing。

 And so that TCB， when you're going to switch to some other kernel thread or some other thread。 that's when you save stuff in that TCB。 And so for the kernel that's running in the kernel thread。 it just saves it here。 If we're in a user thread and we go into the kernel and then we're going to switch to some。 other user thread， we also just save our registers into that TCB and then we swap over。

 So there's one place。 Good。 Good question。 Yes。 So the kernel does not share the same。 So the kernel has access to a whole bunch more stuff than the user does。 So yeah。 so address space is the set of all addresses and their mappings。 Okay。 So from that standpoint。 I would say the user's address space is augmented by the kernel's。

 address space when you go into the kernel。 So the kernel's address space has more stuff in it。 Same number of addresses。 But most of them in the user case are not available。 but when you go into the kernel， they're now available。 So one thing you could think of that is address space prime or it's a little， when you go into。

 the kernel， it's a much bigger set of active addresses。 As I just mentioned。 they can be sharing the same page table， but that page table， most。 of it is turned off when you're in the user mode。 Because it's because there is only one kernel。 Remember， that's our new mantra。 There is only one kernel。

 And the kernel space that's mapped when you're in the kernel is the same for everybody。 They have all access to everything。 It's just when you go into user space。 you have a much more restricted access to things， and it's a smaller subset。 Okay。 Good。 So we're not tied up on a dress basis。 All right。 This I wanted to give you before we close。 Okay。

 Dennis Ritchie， one of the founders of Unix wrote the following comment in scheduler code。 just like what runs we just said。 It says， if the new process paused because it was swapped out。 set the stack level to， the last cell to save you of u_ss。 AVE。 This means that the return。 which is executed immediately after the call to our ARETU actually， returns from the last routine。

 which did the save u。 You are not expected to understand this。 That's my favorite quote in any kernel or anywhere。 Okay。 So， however。 I expect you to understand what we just talked about。 But if you're finding it challenging。 just keep in mind what Dennis Ritchie wrote inside， Unix。 Okay。 So just give that。

 give yourself a little bit of a break there。 Question。 So， okay。 So， okay。 They do get saved in the TCB。 When I go into the kernel， see， you see this here。 this saves all the registers once we， get kind of into the kernel。 But the registers we need to save immediately are really the， let's go back to where I want。

 to go back to here。 The registers we need to save immediately on getting into here are the users PC and stack。 pointer and so on。 And they get pushed on the stack。 That's why this guy now has two kind of has entries on there。 That's where the user's stuff is pushed。 So， when you call into the kernel and you push the user's stuff on the kernel stack and。

 then you just keep going。 Also to the kernel stack。 Everything's pushed to the kernel stack。 By the kernel does the， everything but the program counter and the stack pointer。 All gets pushed。 Best way to think about red and blue and red stacks is it's just the procedure call and。 we clean up the mess between kernel and user but it's all just procedure calling its way。

 through and coming back。 Okay。 Good。 Yes， one go ahead。 I mean， where did this guy come from？

 Actually， let me just go to the last。 Oops。 And then we do want to move on a little bit so we have other things to talk about today。 But if you look here。 This is set by the kernel in kernel space and the hardware knows where to look。 Okay。 All right。 Okay。 Let's， let's move on。 So， if you're finding it challenging， that's okay。 It is challenging， but we're going to make sure you understand it because I， I believe you。

 all can understand that。 Okay。 I believe in you。 So today we want to now talk about。 so we've got mechanism for switching between threads。 Woo hoo。 Mechanism。 The problem is if you go ahead and use that and you do it unwisely， that concurrency can。 kill you from a functionality and correctness standpoint。 Okay。

 And so we're going to have to start understanding why it's a problem and what to do about it。 All right。 You guys ready？ This， by the way， is my favorite Sunday cartoon from Dilbert way back in the day。 And it's sort of a， a point at which the boss asks everybody around the table。 So tell me about your project。 And one guy， the first guy says， my project， the whole new paradigm。

 And then there's all this， well， what's a paradigm mean？ And， oh， you know， paradigm， paradigm。 you know， as in my project， the whole new paradigm。 And then the rest of the frames are， yeah。 mine's a new paradigm too。 And so is mine。 It's so is mine。 So， all right。 So we're going to teach you a new paradigm today。 Okay。 So if you remember。

 we kind of gave you this slide where we talked about how the scheduler。 can give you lots of different schedules。 Okay。 If we have A， B and C threads， then。 and we happen to have a bunch of cores and it's， possible they're actually running in parallel。 That's what that first thing looks like。 That's multiprocessing。

 The other option is a scheduler is going to be switching between them。 And we just spent a lot of time talking about how that switch could work mechanistically， right？

 How you save registers here and do that。 But the key thing to get from here is the fact that the scheduler could run A for a little。 bit than B， then C and it could run A for longer and then B or it could run A to completion。 You don't know what the scheduler is going to do。 So any code you write that's multi-threaded better work no matter what the scheduler does。 Okay。 This is by the way， Kubi's malicious scheduler rule number one， assume the scheduler will。

 find the bug in your code and exploit it in the worst possible way and it will have to。 be at 335 in the morning。 Okay。 I have other versions of that rule which are a little bit less restrictive on to what。 time it is， but you get the idea。 So keep this slide in mind。 anytime you're designing parallel threaded code， you've got。

 to realize that it better work no matter what the scheduling is。 Okay。 So let's go to a particularly simple example。 Here's a bank server。 These funny symbols I've got here represent ATM machines。 Okay。 You can give me a little bit of benefit of it out there。

 We've got some mainframes at the central bank。 And the idea is that lots of people can be withdrawing money and you know there's all。 these requests to go to the central bank and back。 Okay。 So there's lots of parallelism possibilities。 Now suppose you want to build the server and so what you might have something like this。 there's a big loop while true。 You receive a request information in the process the request。 Okay。

 And so what does process request mean？ Well depending on if the op is a deposit。 it does the deposit function， otherwise that， it up。 And the deposit function does something like well get the account from the ID and then。 take the account balance and add some amount to it and then store the result back into， the account。

 And first of all， you could clearly code like this。 I guess。 Okay。 And I've left out all the details about you know， what does it mean to be storing money。 and you know， how do you interact with the fed and all of those things， but we'll assume。 that those are not relevant。 What's wrong with this code？ One at a time。

 We got a lot of pissed off customers， right？ Because only one of them gets to get money at a time。 And so how do we speed this up？ Well we want to have more than one request going on at once。 Now I want to point out something here。 I've got these red may use disk IO things here。 And if you notice， these are things that could take arbitrarily long because it's got。

 to go to a mechanical device。 And so if we wanted to speed things up and we only had one CPU。 it might be that we want， to make sure that whatever we do， we don't have users held up by disk IO。 Okay。 So when one user hits disk IO， the other one can make some progress and vice versa。 Okay。 And so we could do this。 We could build an event driven thing。 Suppose we only have one CPU。

 We want to overlap IO。 And we have no threads。 And so what could we do？ Well。 we could build the bank server like this， still while true。 We get the next event。 But now an event is a part of something。 So a deposit has multiple events。 We look at deposit here。 We might have the get account event， the increment， the balance event， the store account， event。

 whatever。 A bunch of sub pieces。 And at minimum， we need to make sure that we have a separate piece for kind of each slow。 thing。 Right。 So that while you're waiting for a slow thing to happen。 somebody else can be partially working， their way through the deposit。 Okay。 And this is called event driven。 And so it might look like this。 Great。 Get the next event。

 If the event is a brand new request， then you start things。 Otherwise if the event is an account available event， you continue it。 And if it's a stored event。 you finish it。 And each of these things do part of a whole deposit process。 Okay。 And this is a very common thing for graphical programming。

 So if any of you ever program games or whatever， you're going to build event loops like this。 where the event is wait for the next mouse click or wait for things to be drawn， whatever。 Okay。 And the complication here is the only way we get performance out of this is if we're very。 careful to always identify every slow piece so that when there's a slow piece， what happens。

 like this， where the way when we start the request， that's going to fetch something from， disk。 And so what we want to be able to do is have that start on request， start fetching， and。 then the event that comes back from that when it's finally back from the disk will be an。 account available event。 Okay。 And we can go through this and we can build it this way。

 But if we miss one of these blocking steps， then things will still block and the whole。 system will grind to a halt。 But with careful analysis， you could do this。 Okay。 This is challenging for very complicated code， because if you notice what I've got here with。 the deposit， this is like really simple。 But imagine something complicated。

 You got to split it in lots of little pieces。 This is probably not going to be your preferred way of programming complicated code。 Unless you're a really crazy game constructor and you want to make it fast， you might do。 it that way。 Okay。 So let's do it using threads。 Okay。 One thread for request。 So now you've got 20 people standing at ATMs。 Each one gets a thread。 Okay。

 And this is why threads are useful。 So the request proceeds to completion blocking is required。 So here we've got each thread does the get account， add to the balance store account。 Okay。 And now if that thread blocks or goes to sleep， somebody else will take over。 Okay。 So now without a lot of work， we've just decided to assign a thread to each user and it just， works。

 Okay。 Except that does it work。 No， unfortunately it doesn't。 So for instance。 what does it actually happen here when we get the account update the balance， and so on？ Well。 just look at this middle step。 How do we add the amount to the account while we grab the account balance into a register。 we add the amount to the register， we store the amount back。

 And if somebody else happens to be accessing that same account at the same time and the。 threads get interleaved， now I'll have it goes loose。 Okay。 And let me give you an example here。 which is you're going to put 10 bucks into your account。 Your parents are putting 500 bucks。 Except your $10 thing here。 Overwrites the $500 your parents put into your account and by the time you're done your account。

 balance doesn't have $510 in it。 It's got 10。 Okay。 Now I don't know about you guys。 but this is probably bad。 Okay。 That's a lot of lattes that you lost out on。 Everybody with me on this？ So the problem here is there are these things that need to be atomic。 which is that the， combination of load add store can't be interruptible。

 It's got to be treated as an atomic section。 And that's the fundamental problem here is that we don't have our atomic sections figured。 out properly and we don't even have a way to express an atomic section yet。 So and if you remember。 Cooby's scheduler， malicious scheduler rule， the scheduler will。 find the best schedule of two threads to lose you 500 bucks。 Okay。

 That scheduler will do it and it'll do it at 335。 Right。 That's what I said。 So what are we going to do？ The problem is at the lowest level。 So the time threads are working on separate data。 The scheduling doesn't matter。 So here。 if thread A says x equal one and thread B says y equals two。 Doesn't matter what order they're in。

 right？ Here， suppose y is 12 and now we have A and B interleaving。 What's x when you're done？ Well。 let's see。 If thread A runs the completion first， then x will be 13， right？ X equal one plus one。 Or if thread A and B are interleaved， then perhaps we get y equal two in which case x。 ends up at three or y equals four in which case x ends up at five。

 So the possibilities of what happens when these two threads are interleaved are completely。 non-deterministic and depending on that malicious scheduler。 Okay， which will get you。 Okay。 The one thing that we want you to be paranoid about in this class， nothing else。 Just the scheduler。 Okay。 Now， what happens here？ So， today says x equal one， thread B says x equal two。 Well。

 here you know in most real machines that either x is one or x equals two。 Now。 you could imagine some sort of weird serial processor where the bits are interleaved。 and you got the zero one from the one guy and the one zero from the other and they get。 interleaved and you get three。 Okay， but I'm here to put your mind at rest。

 That probably isn't going to happen。 Okay， because most processors， loads and stores are atomic。 which means the actual load or， store either entirely completes or not。 Okay。 So。 we need to understand the concurrent program。 We need to know what the underlying indivisible operations are。 And so we need this idea of an atomic operation， which is an operation that always runs the。

 completion or not at all。 It's indivisible， can't be stopped in the middle and can't be modified by somebody else。 in the middle and therefore can become a fundamental building block。 And on most machines。 memory references and assignments are atomic so that weird case， of three doesn't happen。 Now it turns out that there are a lot of non atomic instructions and 32 bit processors。

 with double floating points that's 64 bits。 Those are not always atomic。 But don't worry about that for now。 Okay。 If we've got atomic loads and stores。 the question might be can we even make something， like that banking example work at all？ Okay。 because it clearly didn't work the way I started it out。 Right？ It was broken。 So。

 here's another example。 So， you have two threads A and B and they're competing with each other。 One of them sets i to zero counts up and says A wins。 The other one sets i equals zero counts down and says B wins。 So， what happens？

 These are two threads in the same process。 What happens？ Well， I don't know。 So memory loads and stores are atomic， but incrementing and decrementing is not。 So who wins？ Well。 it could be either or neither。 They're guaranteed that somebody wins no because if they're interleaved in the wrong。 way， they keep erasing each other。 Okay， and they never get to winning。 Okay。

 And what if they both have their same CPU running at the same speed？

 Is it guaranteed to go on forever？ No。 There's going to be non-determinism because of caches and all that other stuff and so。 even if they're running at the same speed， it probably will be that one finishes。 Okay。 So again。 this malicious scheduler hits the fan here， right？ So， here you go。 The interloop looks like this。 Thread A does a load。 Thread B does a load。 Thread A adds。 Thread B subtracts。 Thread A stores。

 Thread B stores over it。 You know， when you do this and we're off， A gets up to an early start。 B says better go fast and tries really hard。 A goes ahead and writes a one。 B goes ahead and writes a minus one and A says， huh？ Okay。 Could this happen on a uniprocessor with the kind of scheduling we did at the beginning。

 of the lecture？ Probably not because the quantum we're talking about for switching。 Does anybody remember what a good number for how frequently you switch might be？

 So we don't want more than 10% of the time wasted， but how much time between switches？

 Everybody remember I gave you a couple of numbers。 Was that？ So 100 milliseconds is a good number。 Okay。 10 or 100 milliseconds。 Yeah。 So going forward trying to fix this。 our definition might be well synchronization is using atomic。 operations to ensure cooperation between threads。 And for now loads and stores are atomic。

 Mutual exclusion says ensuring that only one thread does a particular thing at once。 And a critical section is a piece of code that only one thread can execute at a time。 Okay。 And you get a critical section because of mutual exclusion。 Okay。 And so we need some way to have mutual exclusion。 And I want to give you an idea。

 The idea is a lock。 Okay， which I'm sure you got in 61C probably or B maybe。 But now we're going to learn a lot about locks。 Okay。 And a lock prevents somebody from doing something。 And so the idea is you're going to do a lock before entering a critical section。

 And then you're going to do an unlock afterwards。 And the trick here is if somebody already has it locked and you try to lock it。 you're， going to be forced to wait until they unlock it。 Then you get to go forward。 And so the essential idea to get out of today's lecture is that synchronization problems are。 all fixed by waiting。 If you make sure that people wait or threads wait in the right time。

 then you can fix problems。 Okay。 So locks will need to be initialized。 Okay。 So there's ways of initializing by constructing a lock or a lock init。 And typically acquiring。 you say acquire and you give a pointer to the lock or release， and you give a pointer to the lock。 So there can be many locks in a program。 Okay。 So let's look to fix the banking problem。

 Notice what I did here is I put in acquire and a release around that critical section。 This is the critical section。 It's the piece that we don't want to have broken into because that's will screw everything。 up。 Okay。 So if we have that lock acquire and release。 what we see here is basically that if we have， acquire and release around our critical section。

 notice what happens。 Thread ABC， they all show up， but only one of them gets the lock。 Okay。 So for instance， a may acquire and all the rest of them are forced to wait。 And so now a does its thing。 And after it exits， now be gets to go。 And after it exits。 now see gets to go。 Okay。 Everybody with me？ And there we've just fixed the banking problem。

 but only if we make sure that we use the same， lock across all the deposit。 withdraw all of the things where we have to make sure there's， only one thread in there at once。 which is messing with the state of the bank。 Okay。 I'm going to pause for a second。 Okay。 Okay。 So if you're interested in p threads， we mentioned p threads packages well back， they have locks。

 called mutexes。 Okay。 So most languages give you a way to do some sort of locking。 but we're going to explore， what that really means in a moment because really。 if I just did loads and stores so far， I haven't shown you anything about how to make a lot。 Okay。 But usually if I've got multi threaded code and I'm writing multi threaded code， the first。

 thing I do is I find out what are my synchronization operations of which locks are one。 All right。 Part of the process。 Okay。 So， so correctness requirements basically are that threaded programs must work for that。 malicious scheduler。 So all inner leavings of thread instruction sequences and cooperating threads are using。 the same data by almost definition because they're cooperating。

 And so therefore it's non deterministic。 And it's going to be very hard to debug unless you do really careful design of your code。 to start with。 Okay。 So if not a design aversion， run it a bunch of times declare it's fine and go home。 you're， guaranteed that the malicious scheduler is going to get you。 Okay。 So part of what we're going to do over the next several couple of lectures is we're going。

 to try to understand what's involved in properly building code that works under all sorts of。 thread scheduling。 Okay。 So an example is the there are 25。 which actually has reading from last time。 I didn't put it up。 but this was a machine that did radiation therapy for people with， cancer。

 And there was a software control of the electron acceleration and the electron beam production。 to get x-rays as well。 And software control of the dosage。 And so the idea is you put the patient on a table。 And if you wanted to give them certain x-ray therapy， you'd send electrons at a target。

 which would produce the x-rays and you'd do it for so long to give them the right dose。 And you know， this is an important kind of way of treating cancer。 The problem was there were concurrency bugs in this machine。 And it killed a bunch of patients。 Okay。 And what was really bad about the concurrency bugs were there are a bunch of race conditions。

 where somebody hadn't properly thought this through。 And it was very poor software design。 And here's the quote that's most crazy。 There's a report up there on the reading from last time that you can look at。 Quote， "They determined that the data entry speed during editing was the key factor in。 producing the error condition。 If the prescription data was edited at a fast pace。

 the overdose occurred。"， Let me translate that for you。 You've got a really good operator。 They know things well。 They're typing things in too quickly。 That was when you ended up killing people。 Okay。 Now hopefully none of you will be in that position。 But I will point out that concurrency is really something you got a design for correctness。

 from the beginning。 Okay。 So that's the whole point。 Now I'm running a little bit behind what I normally do here， but we have a midterm week。 from Thursday。 I'm sure you're all excited。 No class that day。 Okay。 I'll try to have some extra office hours during class period in my office if people。

 want to come by。 We'll give you a lot more details about that。 But it's all the topics up to that day。 All right。 Excuse me。 Up to the Tuesday before。 but not a heavy emphasis on that Tuesday lecture。 Okay。 Project one。 design documents due next Friday。 So you know that。 And that means design reviews are coming up。

 And we will have the TAs will be scheduling you to come in and give a design review on。 what your plans are for the project。 Think of the design document as a high level discussion of what you plan to do。 Don't do it first and then dump all the code into your design document。 All right。 The point here is a discussion of your design。 Okay。 And if you need to have some code。

 put in pseudo code。 Okay。 That's the kind of code I put in class where it's not a huge amount of syntax。 It's given the general idea。 Okay。 Because you want them to help you。 You're going to under make them understand what you're planning to do。 And then they can have some suggestions for that。 Okay。

 And you and make sure you have a good testing methodology。 How are you going to test it to make sure it works？

 And the other thing I just want to mention and we did a bunch of this the first couple， of lectures。 In these projects， do your own work in your group。 Don't be tempted to collaborate。 Don't have a big project writing party。 Okay。 That's a bad idea。 You can have a project writing party within your group。 Okay。

 And four people is about the right amount for， you know， a nice two slices of pizza and whatever。 else。 But don't， uh， don't be sharing things back and forth because our tools that we use to check。 for that will flag you。 And we really don't want that。 Okay。 Now， project one， project two。 project three， they're all looking inside Pintos。 So you're hopefully you started looking at the code。

 Okay。 And some of the things I showed you today， if you go back to my slides， you can see some。 some different files that are referenced there。 If you want to sort of see some of those details。 Okay。 All right。 Questions。 Okay。 Yes。 You know， you can start coding a little bit。 but I would go through the design review before， you get to， uh。

 enamored with a particular approach。 Okay。 But， but you know what， I would。 I would push as far as you can so you have a very good idea， what you're going to do。 Okay。 Just。 I would say don't go that last step of writing it all up， but I would keep working。 hard on figuring out what you're doing。 And if you write some preliminary code。

 just so you understand what it's going to look， like， that's probably a good thing to do。 Getting ahead in this class is never a liability。 Let me say that again。 getting ahead in this class is never a liability。 Always a good idea。 All right。 So。 I want to motivate an example here to start understanding block construction。

 So we call this too much milk。 Okay。 And the good thing about OS is is analogies between real life and the operating system。 uh， are all over the place。 And sometimes this helps。 Okay。 But you got to assume when you're coming up with an analogy that computers are much， super。 super than people。 I hope especially you guys here at Berkeley。 Um， and so we got to be careful。

 So here's the problem。 You live in a house with somebody and you have a rule about milk。 If you use it up， get some more。 Okay。 And so what happens is person A gets back from section at three o'clock looks in the。 fridge， you're out of milk。 So we've already violated something。 but they're going to go get something， right？ So they leave for the store and they're arriving at the store at three 10。

 But meanwhile， the next partner looks in the fridge， you're out of milk。 They start leaving for the store， they go in the other direction to a different store， right？ Um。 person A buys the milk， they arrive home， they put the milk away。 The， uh， goes to the store。 buys milk， you arrive home。 And now we've got altogether now too much milk。 Okay。

 So how do we fix this problem？ Right？ So could we put a lock to use？

 Now we don't have to build a lock yet， but all synchronization involves waiting， right？

 That was what you learned today。 So example is you fix the milk problem。 you put a big padlock on the fridge when you're， going to the store and you take the key with you and you get home and now your。 uh， your， roommate is just pissed。 Okay。 Because they really only want an orange juice or ice cream or something。 Okay。 So maybe we need to do something other than that。 Okay。

 So let's see if we can be a little more sophisticated。 So first of all。 what are the correctness properties here？ So one is we got to be very careful about correctness of concurrent programs since it's。 a non deterministic issue。 Okay。 And so the impulse is to code first， ask questions later。 Don't do that。 Think first code。 Then ask question。 Okay。 No。 So instead think first。

 then code and always write your behavior down that you're expecting。 especially with synchronization problems。 Okay， there you are。 your instincts as a EECS or an LNSCS person are to write first ask， questions later。 You got to resist。 Understand first。 Okay。 So what are the correctness properties？

 So never more than one person buys somebody buys if needed。 Those are two very important constraints。 Okay。 And the first attempt is we're going to restrict ourselves to use only atomic load in store。 and that means we're going to use notes。 So here's the idea。 You use a note to avoid buying too much milk。 So you leave a note before buying like a lock and then when you're done。

 you remove， the note and you don't buy if there's a note。 Okay。 Seems reasonable。 The problem is we're talking about computers not people here。 So notice our code。 which we want to try to get a critical section out of might be like， this。 If no milk， okay。 If no note， leave a note， buy milk， remove note。 Okay。 So what happens？ Anybody see？ Yeah。 Uh huh。

 Good。 Now， it's， notice the problem here， right？ So thread A says， if no milk and thread B says。 if no milk， thread B says， if no note， thread， A says， no note， leave note， goes to buy milk。 And the other one does the same thing。 So an interleaving there is actually going to give you too much milk again。 right？ But notice that this is too much milk， but only occasionally too much milk because we're。

 basically， you have to hit spot on that interleaving or everything will work properly。 So this is like worse， right？ Because this happens intermittently and the scheduler will pick up that 335 in the morning。 problem， right？ Okay。 So the result is still too much milk， but only occasionally。 Okay。 So everybody with me on that？ That doesn't work。 Okay。 So， uh。

 so the solution basically makes the problem worse since it fails intermittently， and you know。 you do not want that。 And by the way， there are lots of bugs， not exactly like this。 but intermittent failure， bugs in the early days of Unix。 And it was recommended that you had to reboot every now and then because there were some。

 weird bugs in the kernel。 Okay。 And there are some operating systems that we won't name that have that same property。 So actually， I heard the other day that Tesla is now recommending with their big screen to。 reboot it regularly because it gets blocked up。 So anyway， I don't know。 I don't know if I like that where that's going。 So the clearly the notes not blocking enough。

 So let's try to fix this by placing the note first。 So you leave the note and then you say if no milk， if no milk， so what's wrong with this？

 There's a note there。 Okay。 Well， with a human probably nothing bad， but with a computer。 no one ever buys milk。 Okay。 So let's try something different。 Let's label the notes。 So A leaves note A and B leads note B。 Okay。 And so A says leave note A if no note B if no milk by milk remove note A and vice versa。 Okay。 Does this work？ Why not？ Okay。 And then what？

 So they both leave the note and they don't buy milk。 All right。 So it's possible for neither thread to buy milk。 So it's context switch at exactly the wrong time。 Remember that malicious scheduler？ Okay。 This is the this is extremely unlikely that this would happen。 but this is where there， was a lot of possible bugs like this。 Okay。 Very unlikely。

 but hard to debug because you have to somehow get it to occur in exactly the。 right way to find the bug。 Okay。 This is this is not sleeping for days kind of bugging debugging。 Right。 This is the I'm not getting milk。 You're getting milk。 Okay。 And this kind of a lock up is often called starvation， which kind of works here， right？

 Because there's no milk。 So， so let's try another option。 I'm going to call this number three。 So here， thread A leaves the note and then says， well， there's a note for B。 Don't do anything spinning。 And then if there's no milk， buy milk。 remove note and be leaves its note。 And it says， if there's no note A， then if there's no milk。

 buy milk， remove note。 So first thing to notice is these two threads are different。 Everybody catch that？ Does this work？ Who thought they'd find milk was so complicated？

 How many people think this works？ How many people think it doesn't work？

 How many people have absolutely no idea？ Okay， at least you're honest。 So turns out it does work。 It's both can guarantee that it's either it's safe to buy or somebody else will buy。 Okay。 And it's okay to quit。 So if you notice， think about this。 It doesn't matter。 Suppose they both leave the note at the same time， then what A is going to do is A is going。

 to spin waiting for B to remove the note and now B can happily look at to see if there's， no note A。 then it'll go ahead and buy the milk。 But if it finds out there was a note A。 it's not going to do anything。 Why is that okay？ Well， because A will then check for no milk。 Okay。 so this， you know， at X if no note B is safe for A to buy， otherwise wait， so。

 find out what's going to happen。 If A， Y if there's no note A， safe for B to buy。 otherwise A is either buying or waiting， for B to quit。 Wow。 Okay。 And so you can kind of see here。 you know， leave note A happens before if no note A， then， we sit here and spin waiting。 And then eventually when we remove the note， we go ahead and do this and that works。 Okay。

 Case number two is that we leave note B and we execute the if no note A before we leave， note A。 And so what happens here is he's going to leave potentially leaves note A， sees note。 B is set so they're going to wait a little bit。 And at that point。 this guy is going to go all the way through and buy milk。 This one's still spinning。

 So by the time we get here， there's milk。 Okay。 Now， wow， it works。 I can guarantee you that if you had to write code like this all the time， you would never。 get it right。 I would never get it right。 And can anybody answer this question？

 What if I had a third thread？ What if I have C？ Say again， it paint or paint？ Uh huh， paint。 Yes。 Paint exists。 So it turns out that this generalizes Dan threads。 You can look up this paper。 but this seems bad， right？ I mean， it works， but it just doesn't seem desirable。 So what did we learn just now？ If we only have loads and stores， yes， we can synchronize。 Okay。

 In fact， this is the critical section we're synchronizing。 All that other stuff on the outside is to make sure that only one thread ever says if。 no milk by milk。 So we actually came up with locking scenario here to give us a critical section in solution。 number three works， but it's terribly unsatisfactory and it's really complex。 Okay。

 And A's code is different from B's code。 And worse， as you'll learn。 is that A actually spins waiting for B。 So it's possible that B goes to the store。 goes to the library， goes and gets dinner。 And then comes home to put the milk in there and meanwhile A has been spinning the whole。 time。 Okay。 That's bad。 And so if you come up with a synchronization solution where cycles are just being wasted。

 it's not good。 Okay。 And we'll actually knock points off if you have an explicit busy wait that can last for。 a long period of time。 So I will tell you for a fact。 this is not going to be a recommended solution。 Okay。 Got to be a better way。 And so the better way is going to be we need something other than loads or stores。

 We're going to need some hardware to help us。 Okay。 And too much solution number four is really we want this acquire。 Lock release lock。 And if somebody else already acquired the lock， you go to sleep on a weight cue so that you're。 not using any cycles。 That's a desirable solution。 Okay。

 The roommate who's waiting for B gets to go up and take a nap and they'll get woken up。 when B comes back。 Okay。 That would be not busy waiting。 Okay。 And somehow these things that fire and release have to be atomic operations。 If two threads are waiting for the lock and both set it free， only one gets to grab it。

 So if you remember that example I showed you with the bank， there were three threads， they。 all kind of waited at the entry。 And what one of them got in first and then when he exited。 only one of the two remaining， ones got to go through。 So it has to be atomic。 Otherwise it's not a good lock。 Okay。 And then here's our problem。 Okay。

 And this works for a sorority now。 Okay。 So many people as you want or fraternity。 it doesn't matter。 You can have a choir if no milk by milk release and it'll just work for 20 threads or 100。 threads。 Okay。 So that's where we're going with this。 We want the code to be the same。 Okay。 And so where are we going？ We're talking about load in store for synchronization。

 We're going to start moving into some other types of hardware operations other than load， or store。 We get a little bit before we leave today。 And everything is going to be kind of painful down at this level if we only have operations。 but it's going to get a lot better if we can disable interrupts， et cetera。 But ultimately。 we're going to build locks and semaphores and monitors and so on out， of those lower primitives。

 And so by the time we get to semaphores and monitors， things are going to be much easier。 to build correct code easily。 Okay。 And then we're going to build shared programs and all that。 Okay。 Now， how do you implement a lock？ So remember a lock prevents somebody from doing something。 You lock before entering the critical section。 You unlock after you wait if locked。

 And we're going to say to avoid busy waiting that you should sleep if you can't get the， lock。 So now I kept， I keep using this term sleep and I just want to make sure it's clear what， I mean。 Sleep means your thread is unloaded， the TCB's got its registers and it's sitting on some。 queue somewhere。 That's a sleeping thread。 Everybody with me？

 So what we want is our lock to work such that if multiple threads try to acquire， only one。 gets through and the rest of them are put on a wait queue， usually associated with the， lock。 Okay。 Question。 Yes。 So so far， all we've given you the ability to do here is that they will go to sleep。 So if multiple threads enter the acquire phase， only one of them goes through， the rest of。

 them are put asleep on a wait queue。 Okay。 And for now。 also assume that that wait queue is associated explicitly with that lock。 Okay。 So there'll be as many wait queues as there are lots。 Okay。 Good。 question。 Yeah。 。 (silence)。

![](img/53a0bbd96bce73194524f58499453c5d_3.png)