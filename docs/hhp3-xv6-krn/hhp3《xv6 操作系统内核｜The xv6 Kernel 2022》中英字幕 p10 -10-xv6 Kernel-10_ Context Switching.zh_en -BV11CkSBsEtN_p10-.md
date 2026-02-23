# hhp3《xv6 操作系统内核｜The xv6 Kernel 2022》中英字幕 p10 -10-xv6 Kernel-10_ Context Switching.zh_en -BV11CkSBsEtN_p10-

![](img/f5d6a2940eff4f47bd307f796193ef7d_0.png)

This video is part of a series on the XB6 operating System kernelel。In this video。

 I will talk about context twitching。 I'll talk about how traps and system return instructions are used to implement time slices。

And I'll talk about how the system switches from one thread to another。

Let's start with this picture here， and I'm showing time flowing down the page。Here's a user thread。

 and this indicates instructions are being executed until at some point a trap occurs。

 and then we switch into the kernel and execute instructions in kernel mode。

User thread instructions are executed in user mode and anything executed in kernel mode is by definition part of the kernel。

The switch from user mode to kernel mode occurs as the result of a trap。 This can be an interrupt。

 such as from a device that is requesting attention。

 or it could be requested by the user thread itself。In the form of a system call。

 or perhaps the user thread has a program exception， some sort of an error。

 And that results in a trap as well。After the kernel executes and is ready to return to the user thread。

 the S REt or system return instruction is executed， and that takes us back into user mode。

This could be a device requesting attention。 So if it's an interrupt。

 the user thread will be unaware that this trap has occurred and every and the user thread will just be executing instructions and really have no clue that the trap and return happened。

At the point of the trap， all the registers of the user thread should be saved and will be saved。

And at the system return， those registers will be restored or reloaded， if you will。

 And so these are thread just pick picks up where it left off。

So the user thread experiences over time， a series of time slices。 It happened。 Here's one。

 and here's another and here's another。This trap could be the result of a timer interrupt。

 in which case the kernel will go off in this region and do something else with some other threads。

 but eventually we'll come back to user thread X。 So if the trap is a timer interrupt。

 we have the end of the time slice。 and at some later time。

 the kernel will decide to give the user thread， another time slice and then we'll return to the user thread。

So here's a different view of it。 And here I'm showing the schedulers thread in red on the left。

 and we've got several threads。 Okay， X is executing down here and thread Y is executing over here。

And from the point of view of thread X， you say it executes along。 It gets a trap。

 And then at some later time， a return happens， and it continues executing。 and then it traps。

 And then at some other point， a return happens， and it resumes。While the kernelel is active。

 it may choose to run a time slice for thread Y。 So the system return goes back to thread Y。

 and that executes until thread Y gets a trap。So one interesting thing to note in this picture。

 the trap is followed by the return sort of like a call is followed by a return。

So the user thread can imagine that it is calling the kernel， particularly with a system call。

 and that the kernel eventually returns to it。Here。

 it's sort of different because the return and trap are sort of reversed。

 So this trap is not followed immediately by return， but it's followed by some other stuff。

So from the scheduler's point of view， we go into thread X and begin its time slice with the system return instruction。

 and the time slice ends with a trap instruction。Now I want to look at a little bit what happens when the trap occurs。

 let's go back to this diagram， when the trap occurs， the kernel executes。

 and then there's their system return。This is this diagram is what I call the roadm， my roadmap。

 and it's pretty complicated， but basically we have user code executing。 it executes。

 and there's a trap。 And then down at the bottom， there's a return。 and then the user code resumes。

 So a lot of stuff is going on here。 and I'll come back to this in detail。 But among other things。

 the trap happens， could be as a result of a timer interrupt or a device interrupt。

 Those are both asynchronous in the sense that they happen from outside the user code。

 And the user code will be unaware that they've occurred。 or it could be a system call。

 the user code might have asked for something from the kernel。

Or it could be that the user code has some sort of an error condition。So we see。

 you know saving the registers and the program counter happens really early and then way down here at the bottom before we do the system return。

 we see restoring user registers and then the SRt instruction。And what goes on here。 Well。

 we have a big if state， but then we might have a device requesting attention。

 So here we have to run run the the handler for this particular device。

 Maybe the user code asks for a system call。 So we have to deal with that。

Maybe it was a timer interrupt， or maybe it was a program exception。

 But at least in these three cases， we all come down here and ultimately go back to the user code。你好。

One thing I want to talk about next is the。Fact that we could have things going on on a multi core system。

 So here I just showed the scheduler executing thread X and then thread Y and then thread X。

 That's for a single core system。In this picture， I am showing more or less the same thing。

 but for two cores。 So here you see the scheduler for one core in blue。Okay。

 and over here we have another core shown in red， and here we have some processes， X， Y， Z and W。

 and you can see the scheduler decides to give process Z a time slice at this point。

 And so it does a system return into process Z until process C finally has a trap and we go back to the scheduler for this core。

 and then maybe it selects some other cores and does some other stuff。Meanwhile。

 this core is executing along and perhaps at this point， it decides to give Pro Z a time slice。

 so at that point， it does a system return into process Z and process Z gets another time slice。

From the point of view of process Z， we see that it got a time slice on this core。

 and then it had to wait for a while， and then it got a time slice on the other core。

There could be additional cores as well。 So the time slices for any process can happen on any core。

 It's just a matter of well， more or less chance in the case of X36。So what happens at this trap。

 This is the trap where we go back into the kernel。 and at this point。

The registers for process Z will be saved at this context switch， all of Zs。State on the core。

 on the core is saved， namely its general purpose registers in its program counter。

And then at some later time， core， this red core over here decides to give Z a time slice。

 so it does another context switch into process Z。And it will， at that point。

 load registers into the core0 that will the the registers that process Z needs to execute。Now。

 at this point。When the state of Pro is saved， it will be saved into memory。

 So it's shared memory shared amongst all the cores。 And at this context which。

 that shared memory is accessed and the state is loaded from the shared memory back into the registers of a core。

That shared memory where we are storing the state of process Z is， of course。

 critical and needs to be protected with locks and will be protected with locks。

 So while that state is being saved at this context switch。

 a lock will be held and only after it's done is that lock released and treat up。

 And so that prevents core， this red core over here from trying to start the the time slice of process Z too soon。

 So only after the red core is able to acquire the lock。

 can it then begin to load process Z's registers and do the context switch into process Z。Now。

 I should they。Time is flowing down the page here。 We do a trap into the kernel。

 and then we do a return back from the point of view of the user thread。

Sometimes we see it drawn differently here in this diagram up here， time is flowing to the right。

 So we see the trap occurring from user mode into kernel mode。 And then at the system return。

 we have a context switch from kernel mode back into user mode。If it's a simple operation。

 then we sort of have this picture。 For example， if it's a device that's requesting service。

 the trap is an interrupt。We're able to handle the device and deal with the device without doing any further context switches。

 and then we go straight back into the interrupted user mode。Also， in the case of some system calls。

 it may be that we can service the system call without doing any further context switches and go straight back to the user mode code。

 And that's pretty efficient。 But in other situations。We can't。

 So here I've drawn a slightly more a different situation。

Here we are executing a along and user mode。

![](img/f5d6a2940eff4f47bd307f796193ef7d_2.png)

And we do our trap。 And now we're executing in， in the kernel。But it， in some sense。

 it's the same process。 Okay， it's not。 we're not really in the schedule thread yet。

 The scheduler thread is indicated in brown as a separate thread down here。 So here we're in the。

Thread， the kernel thread for this user process。And if we decide that we want to schedule another thread。

 then we will do a second context switch。So we will then go into this scheduler thread。

 select another another process and then go to that process is kernel thread。

 So each process has a user portion and a kernel portion。 I'm showing。1 thread in red here。 Okay。

 this is the user portion that executes in user mode。

 And this is the kernel portion that executes in kernel mode。 But it's all part of one。Thread。

 if you will。 And I'm also shown a second thread in blue here。

So the scheduler thread is a different thread。 and there's a context which。

From the process into the scheduler thread and then another context switch back。

And this is a little bit different than the ones that are going on here。

 When we switch from user mode into kernel mode， we need to save all of the general purpose registers in the program counter。

 We need to save everything。Okay， down here， when we're switching。To the scheduler thread。

 we're already in the kernel， and we can make some assumptions。

 We don't need to save quite all of the registers， and it's a little bit different。

This context switch and this context switch are both handled in an assembly language function called S WTC H or switch。

 I guess we can say。That's assembly code， it's called in these two functions。

 when the scheduler chooses which process to go to。

 it will that's done in this function called Schr and it will call switch to make that context switch。

There's another function， which I guess we can call S。S C， H E D。

 and that is invoked by the kernel portion of a process thread to go into the scheduler。 So it， too。

 will call this switch function。 So the switch function basically will save registers from one thread and load the registers for the next thread。

And as I said， it's written in the Simply code。Okay。

 that's it for context switching and the trap and system returns。

 We'll come back to the gigantic roadmap later in future videos。

