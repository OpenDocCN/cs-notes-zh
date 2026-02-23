# hhp3《xv6 操作系统内核｜The xv6 Kernel 2022》中英字幕 p26 -26-xv6 Kernel-26_ Traps in Kernel Mode.zh_en -BV11CkSBsEtN_p26-

![](img/d49418e9f485df471723166e2a072a07_0.png)

This video is part of a series on the X V6 operating system kernel。 In this video。

 I'll talk about what happens when a trap occurs while we're executing in kernel mode。😊。

Colonnal mode is sometimes also called supervisor mode。

I'll look at the assembly code in the file Colonel V dot S。

 and I will look at the code in the file trap dot C， and in particular。

 kernelel Tra and device interrupt。So let's review this picture that I've shown earlier。

 where we have code executing a user mode and then a trap occurs and we go down here and ultimately execute an SRAD and return to user mode。

When the trap occurs， we will take an immediate jump。 The hardware will take a jump to userva。

There's a special register called STVc， and as part of the hardware processing。

 the value in that register will be moved into the program counter。

This register will contain the address of the first instruction of Usebe。

 so this just does a jump to UseV。Urbe is assembly code。

 it immediately saves all the registers and basically just jumps to the function user trap。

 which then looks at the situation and determines whether we have a program exception。

 a device or timer interrupt， or it's a system call。Ultimately， we come down to user trap Ret。

 which then invokes user Ret and does the SRt instruction。 First。

 they will say the registers and get everything restored and then go back to executing a user mode。

At this point， when the trap occurs， interrupts are disabled。

 So if a device interrupts anywhere along this pathway until interrupts are reenabled。

 that interrupt will remain pending and will not be dealt with until the moment that the interrupts are reenabled。

And you see that interrupts are enabled along the pathway that deals with a system call。

 so while the process is executing the code that implements the system call。

 a lot of things can happen， but interrupts are enabled。

 so it may be that we get and interrupt and if we do。

 then we will go off and deal with the interrupt by executing the device handler and then we will come back to this process and complete the system call and then finally come down here to user trap read。

The first thing we do in user trapre is disly interrupts。

 And so the next thing we do is we restore this register S T back to point to userback so that when we are executing a user mode。

 the next trap will go to userbe as it should。So we also see that interrupts remain disabled along the device path。

 So all the device handlers will execute with interrupts disabled。

We also see that interrupts are disabled along the time or interrupt pathway。

 so we will more or less complete this yield and then go straight back here。 Now， what will yield do。

 yield may switch to another process。 And what happens in that process。 Well， we don't know。

 But most likely interrupts will be enabled at some point。 So an interrupt may occur。

 But when we come back from the yield， things will be just as they were when we left。

 and in particular， the interrupts will be disabled。 And and we immediately。Disable them again。

If device。Interrupts during this phase right here， it will remain pending。

 That interrupt will not be executed， but it will be it will be pending。

 And the minute we enable interrupts right here， it will occur。If we don't take that pathway。

 then we don't enable interrupts until we go back to the user mode code。

 So if the device interrupt occurs anywhere else， in particular， if it happens down here。

 then that interrupt will remain pending until we return to user mode code。

 and then the first thing that the user mode code will do is have another interrupt and deal with the device。

I went over the function user trap in an earlier video in this series。

 but I wanted to show that right at the beginning of this function。

 we are writing to the control and status register called ST TVc， and we are storing in it。

 the address of the first instruction of the assembly code called Colonel Vk。 Okay。

 so that's what I showed right here in the diagram that we're setting STVc。

And I also want to look at what happens at。The bottom here。

 when we restore S TV after we dis the interrupts。 So in user trap rep， which is。Right here。

 this is user trap red。The first thing we do is turn interrupts off and then again。

 we write into the STVc and we're writing the address of the user V。

 so there's where we are restoring it。When we get a trap while executing in user mode。

 the first thing we do is save all of the registers in the processes trap frame。

I discussed that at length in an earlier video in this series。

When we get a trap while running in kernel mode， we do things a bit differently。

 We don't have any fixed place to store them。 Instead， we save the registers on the kernelels stack。

 Okay， so now let's take a look at the code in kernelel Vck dot S。

 And it is the first code that is executed after a trap in kernel mode。😊。

We make it known to the asmbler that the label kernelel Vec and the function kernel trap。

 which we will be calling， are externally known labels。So the first thing we do is we。

Subtract 256 from the stack pointer。 This is an ad immediate。

 and we subtract 256 and from the stack pointer， and that allocates bytes on the stack。

 Then we say each of the general purpose registers， R A， S P， G P， T，P， and so on。 Now。

 we don't have to save the0 register， the one that contains 0 at all times。

 So we actually we only need 248 bys。 But nonetheless， this code pushes 256 by。

Then we call the kernel trap function， and that will go off and execute the device handler。

If it was a timer interrupt， it will do a yield。 And at some point。

 the yield will come back and eventually will return from kernelel trap。

 and then we will restore the registers。 So previously， we saw an S D， which was a store double word。

 Here's a load double word。 So we're loading all of the register registers back into the registers。

 And you see all the way down here。 And then we pop。The 256 bys off the stack by adding。

 and then we do an S rep to return to the executing code that was interrupted with the trap。

One thing you will notice is that we do not restore the T P register。

 Remember that the T P register is used to hold the number of the core that we're executing on。

The trap could have been caused by a timer interrupt， in which case we will be executing a yield。

Yield will go off and make this process。Runable instead of running。

 and it will then sit on the ready queuee for a while。 And ultimately。

 some core will select this process to run， and then it will be rescheduled。

 and the yield will return。 However， it may not return on the same core。

 The T P is supposed to hold the number of the core we're executing on。

 and that will be set appropriately by the scheduler。 I mean， so when we come back to it。

 we'll have T P register for that core。 So we don't want to overwrite that with the core number that we were executing on at the time the trap occurred。

 because we may resume this process on a different core。 I think that's kind of cool。Okay。

 so the code in Colonel Vck has just saved all the general purpose registers and invoked Colonel Trarap。

 which is shown here。The first thing the kernelT function does is save the value in several of the control and status registers。

The programme counter， the status register and the cause register are fetched and saved here。

We will need the program counter in the status in order to return to the interrupted process。

The cause register will contain a number that tells exactly what caused the trap。

So the first thing we do after that is do some sanity checking。

 we make sure that we were really executing in kernel mode when we were interrupted by looking at the status register and looking at the previous privilege mode field and making sure that it is supervisor or kernel mode。

Then we make sure that interrupts are in fact， disabled and assuming everything is good there。

 We then call this function device interrupt。 and device interrupt will look at the cause register and determine whether it's the the U art or the disk that is causing the interrupt。

 And if so， it will execute the appropriate handler routine for that device and return one。

 If it is a timer interrupt， it won't do anything， but it will return a2。

 And if it's anything else that will return a0， that is a problem。

 So here we are saving the value returns， and if it returns 0。

 we print out the cause register and we also print out the program counter and the value of the S T Val register at the time of the interrupt。

 it should have highlighted boldface these function calls。 But in any case that we then panic。Now。

 if it was a time to interrupt， then it will have returned two。 So we call the yield function。

Yield will go away。 It will invoke the scheduler and our process will be changed from running to runnable。

 And then at some later time。We will get a chance to run again， and。

We will change back from runnable to running。 And this might actually even occur on a different core。

 And so we might resume executing on some other core。So before we return。

 we need to restore the value of this register for the program counter and the status。

 These will be used as part of the SRt。Process， the S red instruction will copy the value of S EPC into the program counter and the copy S status into the status register。

 So we need to have those set up before we return to。Colonel Vk。Now。

 the other thing I want to discuss is why do we do this test here。 If we had a time interrupt。

 we're also making before we call yield， we're making sure that the state is running。

 So here we are asking what is the current process and if it's not known and then we follow that to the state and make sure it's running And so you might ask。

 well， how could we have been interrupted from any process that wasn't running。

And to see the answer to that， let's go back to look at the scheduler code。Here's the scheduler code。

 So remember that this will be executing a for loop here or it goes through all the proc structures in the pro right。

 looking for one that's runnable， looking for one that's runable。

 And if it finds when it changes it to running and switches into it。And it just keeps looking。

 And when it gets to the end of that array or if it doesn't find anything in the array。

 it will then loop back to this infinite loop。We turn interrupts on here。 Okay。

 I discussed that earlier why that's necessary。 But at this point， when interrupts are turned on。

 it may be that we will have a trap。 It could be that a device try to interrupt earlier。

 and that interrupt has been remain， remaining pending。 So the moment we turn interrupts on here。

 boom， we get a trap。 Okay， we're not actually in any process。 We're in the scheduler。 Okay。

 so no process will have a state of running。 In fact。

 the last thing we do before calling switch is change our， our state to runable or maybe sleeping。

 So we don't want to have。Yield function executed while we're in this scheduler。

 that would really mess things up。 So that's why we we do that here。

But notice that from this acquire on through the switch。Interrupts will be disabled。

 Remember that when we acquire spin lock， we disable interrupts until they are released till the spinlock is released。

 And likewise， in the code that calls switch that comes back， we will also acquire the lock。

 which will disable interrupts until this point。 So it's possible that interrupts will be reenabled at this point。

 and we might have that trap occurring here as well。Next。

 let's talk about the device interrupt function。 It begins by reading the S Ca register to see what exactly caused the trap。

This function will return two if it was a timer interrupt， one， if it was the U artt or the disk or0。

 if it was something else that it was unrecognized。So here we are looking at the S cause register。

 and if it's this value， then we've got an external interrupt。

The platform level interrupt controller makes its need to be taken care of known by causing an external interrupt。

 So if we have an external interrupt， it must be the p。

 So then we handle it here and otherwise we handle it here。We call this function click claim。

 which will return a code to indicate which device is demanding attention。

And then we check that number。 If it has this value， it must have been the U art。

 So we call the function here， which is the in candler for the UA device。If it had this value。

 then we call this function， which is the inner handler for the disk device。 And if it's0。

 we ignore it。 But if it's anything else， we print some sort of an error message。So。

Then we need to call p complete。 The p allows each device to raise at most one interrupt at a time tell the p the device is now allowed to interrupt again。

And we return the code of one。Otherwise， we check the S cause register and if it has this value。

 then we must have a software interrupt and remember that when we have a timer interrupt。

 the machine mode code gets that and it then simulates this software interrupt at supervisor level So that's what's happening here and then what are we going to do if it was a timer interrupt。

We are going to check whether we are running on core 0。 And if so。

 we call this function clock interrupt。 And I'll look at that in just a second。 But regardless。

 we acknowledge the software interrupt。By cly。Bit in the interrupt pending。Word in that register。

 So we read the register， clear the bit and write it back。 And then we return the code of 2。

 And if it was anything else， then we return 0。 So what did this clock interrupt function do， Well。

 all it does is。Increment， this global variable ticks。 That's essentially our clock。

 X 36 doesn't have any kind of a real time clock。 We're just counting the number of ticks on core 0。

 And so that global variable is protected by a spin lock called ticks lock。 So we acquire that。

 And then we increment it。 And if anybody has been waiting。

 if any other processes are waiting on a particular time coming to be。

 then we wake that process up or all of the processes up。And then we release the spin lock。Okay。

 that's it for Colonel V and what happens when a trap occurs in kernel mode？

I'll see you in the next video。

![](img/d49418e9f485df471723166e2a072a07_2.png)