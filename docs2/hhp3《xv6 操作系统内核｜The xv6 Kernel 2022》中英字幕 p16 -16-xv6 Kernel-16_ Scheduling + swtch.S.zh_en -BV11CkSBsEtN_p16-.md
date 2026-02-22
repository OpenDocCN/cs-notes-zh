# hhp3《xv6 操作系统内核｜The xv6 Kernel 2022》中英字幕 p16 -16-xv6 Kernel-16_ Scheduling + swtch.S.zh_en -BV11CkSBsEtN_p16-

![](img/ca78db1d69132c768c7c9fff1fbe774a_0.png)

This video is part of a series on the XV6 operating System kernelnal。

Scheduling is probably the most interesting part of the kernelel， In my opinion。 And in this video。

 I'm going to take a look at it。 I will look at these three functions。I'll pronounce this one scared。

 So I'll look at functions， yield， scared and scheduler。And I'll also look at some helper functions。

 I'll look at CPU Id， My CPU had my Proc。And I will go over the assembly code that's in the switch dot S file。

So let's begin with these helper functions since they're pretty straightforward and easy to get out of the way first。

The CPU Id function。We'll simply return the value in the TP register。

That register will always contain the number of the coreps that we're currently executing on。

Since we could have interrupts and things could change at any moment。

 we really need to be called with interrupts disabled to make sure that the value is not out of date the minute we return it。

The My CPUU function。Will get the identifier for the number for the current core。

 and then it will look up the CPU structure in the array。

 So remember this picture we had showing that there's one CPU struck for each of the eight cores。

 And so all we're doing here is returning a pointer to the structure that describes the data for this particular core。

And the my proc function will go to that structure will get that structure。 So it'll call my CPU。

 and it will go to the proc field and follow it and return that。

 So the CPU structure will contain a pointer to the currently executing procedure。

 sorry process and willll return a pointer to the proc structure。

It could very well be null if we are not executing any process at the moment， but we return that。Now。

 my CPU has to be called with interrupts disabled， and my proc is called from all over the place。

 So one thing we do is call push off to disable interrupts here。That will also increment the counter。

 then we call poppa to restore the interrupts， to decrement the counter。

 and if it goes back to zero to restore the interrupt status to whatever it was before。Okay。

 now let's take a look at this roadmap that we showed earlier。And this shows everything that happens。

Between the trap and the Srat instruction。User code is being executed and we get a trap and we see what's going on。

 And then the case of a timer interrupt。We will call the yield function。

 So I'm going to be focusing on the yield function。 I kind of hinted at some stuff here。

 but I will now show this area here in more detail。After yield returns。

 we go back to the user mode function and continue executing。

One thing I will notice that when the trap occurs， interrupts are disabled and along this path。

 where we call yield， interrupts remain disabled。 and so interrupts are disabled for the yield function。

So looking at that area more closely， we see that the trap happens。

And we have a lot of stuff going on。 and we determine that it's not a system call and not a device that needs to interrupt handling。

 And we end up calling the yield function。 And so this is what happens。 And ultimately。

 we return from yield and basically do some other stuff and execute the S and go back to the user mode code。

You。Calls ski。 So here I'm kind of indicating that yield will call skid。

 Not much happens in yield and skid。 Just a few statements are executed， really。

 And we call a function switch。So。This is the processor thread。

 So we are executing a user mode for the a particular process P。

 and then we are executing here in kernel mode for process P。 And at this point。

 when the switch occurs， we switch from process P to the scheduler thread。

 and then we execute the scheduler thread。The schedule or thread may do some other stuff。

 It may invoke some other it may do time slices for other processes。

 but eventually it will come back and the call a switch here will return and well continue executing in the SCd function and then the yield function and then we do some restoring of the user state and return。

So let's take a look at what happens here in the yield and scared functions before we call switch。

We are going to examine and modify the state of this process P while we are running。

 the state is running。 It is it's running， but we're going to change it to runnable。

 which means it's no longer running and waiting for another time slice。

 So we acquire the lock on process P itself and change its state to runable。

And we also save this field， interrupts enabled。Of the CPU structure。Okay。

 let me just review the CPU structure， not only do we have the pointer to the proc that we're executing。

 but we have two fields that are used by push off and pop off。

In off is a counter and interrupts enabled is the previous status。

 and then we also have this context area where we will save registers。So we're going to save that。

 And then later， we will restore that field。And release the lock on P and return to the user mode code。

 So after we call switch， some other stuff happens and switch ultimately will return。

 And I'm indicating it right here。 And then we come back and finish the execution of this skid function and。

The execution， the yield function and so on。 Now， what happens in the scheduler threat。Well。

 once we resume executing the scheduler thread， we will change the CPU's proc field to knowll because we're no longer executing this particular process and we'll release that lock。

And then we'll do some other stuff。 And eventually， we will choose to run P again In the interim。

 we may get some other processes time slices， but eventually we'll come around and。

This core or perhaps some other cor will choose to give P a time slice。 And at that point。

 we will acquire the lock on P again。And change its state to running。

And we will then set the proc field for the current CPU。 Remember。

 it could be a different core that we're executing on。 We'll set the current。

CPu strucks Prock field to point to the process that we are now starting， which is P。

 And then we'll use switch to go back into the scaredd function and then the yield function。Okay。

 switch is where the interesting stuff happens， so I want to talk about that next。诶。

In the CPU structure， we have a register save area where we can save registers RA，SP。

 and the S registers， and also in the PRC structure we have a register save area where we can save those same registers。

When we。Switch from the。Process P。Will save the current registers of process P and the proC structure in that register save area and will load the registers for from the CPU field。

 from the CPUstructs。Register save area。And when we go back from the scheduler thread to the thread of process P。

 we will save the schedulers registers in。The CPUstruct for that particular core。

 and we will load the registers from processcess Ps register save area。Okay。

 next let's take a look at。Switch。Switch is written in the simply code。

And we see here that it's past two pointers。Both pointers are pointers to the context。

 So essentially， we're passing a pointer to this context ti。

And that contact there in the proc structure。In the risk five system。

 whenever a call is made to a function， we will or the I should say the instruction that does the call will save the current program counter in the return address register。

 the R A register， and it will jump to the first instruction of of the function that we want to call the return instruction。

 and there's one right here。 will take the value that's within the R A register and move it into the PC。

 thereby going back to the caller。If a function doesn't call any other functions。

 then we can leave the return address in that register and we don't need to save it on the stack and in this particular function。

 we see nothing is pushed or popped onto the stack， so that's what's happening here。

In the risk 5 calling conventions， we assume that any function can update and use and modify and overwrite the a registers and the T registers。

 So anybody who calls switch。Will not be able to make any assumptions about the values of the S。

 I sorry， the A and the T registers after it returns。 So that's why we don't bother saving them。

 But what do we do， We save all the other registers， We save the R and the stack pointer。

 and we save all the S registers， and where do we save them。Well， the first parameter。

 the pointer to the old context where we save the state of the previously executing thread。Is in a0。

ThePoiner to the context for the thread we're going to be executing next is in the context pointed to by the new argument。

 which is in a1。 So a 0 is where we save everything。 Here we see a store double word。

 and we store registers， R A， S P， and the S registers。The GP register is not used in the XV6 kernel。

 so we don't bother with that。The TP register contains the number of the core we're currently executing on。

 and that won't change。 we are executing on a certain core when we do this saving and we are still executing on that core。

 so we don't change the TP register。So after we save the state of the previously executing thread。

 within load。The state of the next thread using the pointer to the new context。

 And we load those exact same registers。So here we're saving the return address from the function that called us。

And here， we're loading the return address from some earlier thing we saved。

 And so this return will not return directly Instead， it will return to something else。

 So that's it's kind of kind of weird。 So in this picture here that I showed。Here。

 we're calling switch。And here we're returning from switch。

 But this call that we are executing here to switch doesn't return immediately to the same thread。

It returns to some other thread。 Likewise， this call here returns over to this thread。Okay。

 so that's switch。Now， let's take a look at。The yieldL function and see how and walks through that code。

Deield， give up the CPU for one scheduling round。 So the primary thing it does is it calls scaredd。

Okay， but before it does that does it gets a pointer to the current process。

 We're executing a process P gets a pointer to the the proc。 And then it acquires the lock。

 Remember that the proc structure has a lock field that protects things like the state。

 We're going to be changing the state from running to runable。 So that's what we do。

 We acquire the lock。And then we change the state to runnable。 Then we call scaredd。And we go away。

 And maybe quite a while later， after some other processes have had time slices。 Ultimately。

 the scheduler function will call， switch again and will return back to this。Thread。

 so at some point， Sd will return。And at that point， we released the lock that we acquired here。

Yield is called in exactly two places。 It's called from user trap and kernel trap。

 So whenever a trap occurs when we're running a user mode， we execute user trap。

 And if we've had a timer interrupt， we will call yield。 And likewise。

 we're executing in supervisor mode， we have a function called kernel trap。

 And if the timer has gone off。 we will call yield。 But in any case。

 we will be calling it from a trap handler， interrupts will be disabled， and at that time。

 no locks will be held。Now， here we do an acquire and then a release。 As you remember。

 the acquire is a spin lock， and what it will do is it will disable interrupts。

And then it will remember whether they were enabled previously or not， well。They are not。

 So it will save that status in this interrupts enabled previously field will always be false。

 And since no locks are held， it will increment the counter for the locks， the in off counter。

 And it will increment it from 0。 And so it will be one。 So at this point， when we call SCd。

The in off field will be one， and interrupts will be disabled。Okay。

 so now let's take a look at what happens in SCd。So。We are grabbing a pointer to the Myproc field。

 and we are asking doing some error checking here。We make sure that we are holding the lock。 Okay。

 well， we acquire it right here。Skege can be called S can be called from some other places as well。

 but let's just focus on this call from yield。So we make sure that we're holding the lock。

 we make sure that in off is one。And we make sure that the state is。Not running。

And then we also make sure that interrupts are disabled so。

If the interrupts are enabled this would return true and we would print a error message。

So now we're going to save the value of I N T E and A interrupts enabled。 So in this particular case。

 when we're calling it from yield， it will always be false。 So we're going to save that state。

 But if we call schedule scared from somethingplace else， it might be true。 So in any case。

 we save the previous value of I N T E and A interrupts enabled。And we save it in a local variable。

 And then we restore it later after the call to switch from that same location。

Is this local variable kept in a register or is it kept on on the stack。

 We don't know exactly what the compiler will do， but it doesn't really matter。

 All we know is that the state of this thread will be entirely saved。

 and whether this local variable is on the stack or in a register doesn't really matter。The point is。

That。Is saved in this in some data that this thread。Has， and it will be restored。

 So then we restore the value of it， and then we return and release the lock。

Now let's take a look at the scheduler function and see what it looks like。



![](img/ca78db1d69132c768c7c9fff1fbe774a_2.png)

So it's pretty short it just goes from here， down to here， and it contains an infinite loop。Okay。

 throughout this function， C is set to the。嗯。Poiner to the CPU structure for this particular core。

Each core will execute its a single thread for the schedule function。

 and this function will you know， be executed on one core。 Of course。

 it'll be executed on the other course simultaneously。

 But let's just focus on this one particular core。 So we get a pointer to the CPU struct that describes this core。

And then we've got an infinite loop here。 and inside of that we've got another loop。

 so let's look at this loop first。What is this doing， Well。

 it's going through this proc array 1 by one。 Okay， so it's， here's our array。We have 64 processes。

 and it's going through each one of them one by one and looking at the proc structures。

 And we see that's going here。 And for each one。It asks whether it's runnable or not。 And if so。

 it calls switch。 So we acquire the lock for that process。 right。

 We're going to be looking at the state variable and changing the state variable。

 So we need to hold the lock while we're doing that。 So we acquire the lock。

On this particular process。 And if it is runable， we do this。 If it's not runable。

 we release the lock and move on， look at the next one。 And when we've gone through them all。

 we then repeat the outer loop and start from the beginning beginning again。

If the process is runable， then we're going to change its state to running。 Okay， we've selected it。

 We're also going to store in the CPUstruct a pointer to the relevant pro structure so that we know which process we're running。

And then we're going to call switch。 And here we see the call to switch。

 We're providing it a pointer to。The context。4。The current core and a pointer to the context for the new process that we're going to be executing。

 So we're passing switch。For the old。Argument， a pointer to the area in which to save the registers for the scheduler thread。

And in the new argument， we're passing it a pointer to the context area for the proc structure。

 And that's where to load the registers for the process that we're about to start executing。

So we call switch and then after switch comes back。

 we're no longer executing that process so finally。We set the prock field to null。

And so let me just show how that's working here。We saw all of this going on。诶。

Let me look at it this way here。 So here I'm showing it from the user's point of view。

 We have a trap。 We go into switch。The scheduler executes， gives some others some time slices。

 and eventually we come back， execute the S and back in the user。The user's code。

 but now let's look at it from the scheduler's point of view， we are choosing some process P to run。

 acquiring the lock on P and changing its state to running。And we are also updating the proc field。

 And then we're switching into that process。 And then at some point later。

 that process will give up the CPU。 Okay， timer， if nothing else。

 a timer interrupt will happen and cause a trap。 or it may be something else。 But in any case。

 a timer interrupt causes a trap and we come back into yield And then。

We call switch again only when we call switch in yield。

 we will provide the context in the reverse order。So just let me go in there。We call yield。

 we call SCd。 and insteadd calls。Switch， and this time， the old is the processes context。

 So that's where we're going to say the registers from the processes。Registers。

 we're going to say the processes state and we're going to load。

The registers for the scheduler thread。 So we're going to go to the My CPUstruct and use its context。

So。So then switch comes back so。We set proc to P and invoke switch。 Then some something goes on。

 Eventually， we get the time and interruptrup yield happens。 and we have switch。

 And then we're back in the scheduler thread。 So we then finish off our loop by setting the proc field to null and we release the lock on P。

So we see exactly that going on here， we call switch。We come back。 We said proed null。

 and then we release the。Lock for P。 And then we iterate。 Now， one thing I。

Do say something that we say choose P I say here， choose P and then acquire the lock on P。 Well。

 in order to choose P， we have to find one that's runable and we can't look at the state without locking it first。

 So actually， we do things in a slightly different order。We acquire the lock。

 then we look at the state to see if we found one that's runable。But that's just I a minor detail。

The switch function is called in exactly two places。 It's called in the scaredd function。

To go into the scheduler function and it's called in the scheduler function to go back into some process。

Okay， so whenever it's called and scared， it is always switching from a process to the scheduler thread。

And when it's called in the schedule of thread。It's always going from the schedule thread into a process。

 So if we look at the code for SC。Here we see that switch is being called。

 and it's being passed a pointer to the old context where it saves the state of the previously running thread and a pointer to the new context。

So it will save the current registers in the context tour， the process that it is leaving。

 and it will load the registers from the context area for the CPU。 That is the scheduler thread。Okay。

 that's going in。This direction， Okay， in this direction， it's called from the scheduler function。

 Okay， I'm showing that right here。 Here's the scheduler function。 And we call switch here。

 and it's going from。The scheduler function or the scheduler thread to the process to some process that's now going to be running。

 So it will save the scheduler's registers in the context associated with the current CPU。

 the current core， and it will load the registers。For the process that's going to be executing next。

Another thing I want to mention is that we always have acquires and releases of locks being paired。

 So if we look in the yield function， for example， we see an acquire and a release。

So here's the yield function， and we see that this locked is being acquired here and released here。

And if we look in the scheduler function， we see a similar kind of thing going on。

 So here's a scheduler function。 And we're acquiring the lock。 And we're releasing it。

 And it would seem that this acquire and this release are paired out。

 but that's not really quite right。So here we have the lock being acquired in the yield function。

And it's a spinlock。 We shouldn't hold spinlocks for very long。

 And we see it being released very soon after， in the scheduler function。

And here we see the lock being acquired in the scheduler function。

 And then after just a few instructions being released in the yield function。 So they are paired up。

 but they're paired in sort of a funny way。For example。

 we might be acquiring this lock when running on one core and release it pretty soon after。

 and then later it may be that some other core decides to choose P and to run it。

 so it will acquire that lock and then begin that process running and then the yield function will release that lock。

 So in fact， the lock could be acquired on one core and released on another core。

Another thing I want to point out is that whenever we call the switch function and we switch from。

A process to the scheduler thread。 We will always have interrupts disabled。

 And we know that for sure， because well， here's the scared function where we call switch。

 And right before that， we check to make sure that interrupts are disabled。

So interrupts are always disabled when we come back into the Schr function。

So if we look at the scheduler function， we see that we are going。Here we call switch。

 but then at some point we come back Okay， so we return from switch from after executing a process's time slice。

And at that point。Or at this point here， interrupts will be disabled。And we release the lock。

 but that interrupt may remain disabled， and we look back。Now， if we go into another process， right。

 if we go into another process， we choose another runnable process and we switch into it。

Then we're going to do the switch。And we come back here。 Now。

 this yield was being executed as part of the user trap function and interrupts are disabled at the time the trap occurs。

 and they will remain disabled for the yield function。

 So this acquire here will remember the previous state of the interrupts。

 And this release will then not re enableable the interrupts at this point。 But。

We restore the state of the user registers and so on。

 and then we execute the SRA instruction and at that point interrupts will be enabled。

 and so they will become enabled when we go into the next process。

But it's possible that there won't be a next process。 I mean， it's。

 it's possible that all of the processes on the in the array are not。Runable。 So we。

 we might not be able to find one that's runable。 And what， what would we do。

 We would just if we go through the entire array and don't find anything that's runable。

 Then we come out of this， this for loop here and we go back to iterate this while loop here。

 And we see that we're turning interrupts on。So we could get into a situation where there are no runnable processes。

 It could be that we're waiting for that all the processes are sleeping or waiting on something。

 we could be waiting on user input， for example。 And so there may be no runable processes。

 and we could get into a situation then well， if they're disabled when we come out of this switch。

 and we don't re enableable them here。 then they stay disabled because we we're never finding a runable process。

 So that's what's going on here。 So you see this comment。

 avoid deadlock by ensuring the devices can interrupt。 So we do turn the interrupts on。

If we go through the entire array and which every time we go through the entire array once。

 we turn them on at least for a tiny amount of time。 But it's long enough for the。

Interrupt to occur and the trap to be handled。 and that will possibly wake up some other processes。

 So that's what's going on right here。Allright， this， this。Stuff with the process switching。

 I just find it the most interesting part of the kernel。

 and I hope you've enjoyed this video as much as I've enjoyed making it。😊，Alright。

 I will plan to continue making videos， although there may be a slight delay。

 Look forward to seeing you in the next video。😊。