# hhp3《xv6 操作系统内核｜The xv6 Kernel 2022》中英字幕 p09 -09-xv6 Kernel-9_ RiscV Trap Processing.zh_en -BV11CkSBsEtN_p9-

![](img/bef91684c29e5c6ec5a990daeb948ba1_0.png)

This video is part of a series on the XV6 operating System kernel。In this video。

 I'm going to talk about the risk5 architecture， and I'm going to focus on the status register and how traps are handled by the hardware。

So recall that we use this terminology， there are two kinds of traps。

There are exceptions and there are interrupts。A system call is a type of exception。

 and any kind of a program error is an exception as well。

The system call instruction in risk five is E call。And。

Program errors can include things like illegal instructions or alignment errors and so on。

We also have devices that can interrupt。The interrupt can occur when we're executing in user mode or supervisor mode。

And regardless of what mode we're in， when it happens， we begin executing some handler code。

 running in supervisor mode。So STVc is a control and status register。

It contains a pointer to the handler code。 In particular。

 it contains the address of the first instruction of some code that will handle whatever trap has occurred。

There are two pieces of code in X E6 that handle traps。

 Colonel Vck handles traps that occur while executing in supervisor mode。

And userve handles traps that occur when running user mode code。So let's begin with the status word。

 and I'm going to focus on the status word that code the running in supervisor mode would see the S status word。

The X36 kernel runs almost entirely in supervisor mode。

 so this is our status word that were concerned with。

Things are a little bit more complicated than I'm going to go into。

 but I'm only going to focus on three bits。 And I think that's all you need to understand the X V 6 kernelel。

There's a bit that controls whether interrupts are enabled or not， so that's called SI。

e for interrupts enabled。When an interrupt occurs， we need to save the value of this bit。

 and it saved in another bit in the status word called S P I。e。 previous interruption enabled to bit。

We also need to remember what mode we were executing in when the trap occurred。

Could be we were executing in user mode or it could be that this was an exception that occurred in supervisor mode。

The trap can occur as a result of an exception， or an interrupt。Obviously， if it's an interrupt。

 then the previous value was enabled。 otherwise， we wouldn't be handling it。

But it might be that we have an exception that's occurring while interrupts are disabled。

 So in any case， we need to save the previous value of this fit。

So that when we return from the interrupted code， we can restore the bit to whatever it was before。

One technique in kernels is to temporarily change the interrupt enabled bit to disable all interrupts。

And that can prevent other threads from interfering with one particular critical section。However。

 XV6 is a multi corere operating system， so it doesn't have any impact on what the other cores are doing。

They may be changing memory simultaneously。 So we have locks to handle those situations。 However。

 interrupt disabling does occur in the kernel。Okay， what happens when a trap occurs？Well。

 the first question to ask is whether interrupts are enabled or disabled。

 If interrupts are disabled and the trap will remain pending。 That is。

 it will not be immediately processed by the hardware。

 and the handler code will not run until at some later time， the kernelel re enableables interrupts。

 And then at that point， the trap crossing will occur。Now， if it's an exception。

 it's going to be handled immediately， regardless of whether interrupts are disabled or not。

But in any case， when the trap is handled， the hardware will do this。 It will do these things。

 and then it will resume executing。 So the previous instruction is completed。

 and then the hardware will save a copy of the program counter in。

A control and status register called S EPC。Then it will branch to the first instruction of the handler code。

By copying the value in STVAC to the program counter。

Then it will save in the S cause register information about what exactly happened。

 What caused the trap handler to be invoked。And it may save additional information in a CSR called STVal。

There are several causes that we will be concerned with in the XV6 kernel。If it's a system call。

 the cause will be 8。If there's an interrupt from an external device， will be 9。

If there's a software interrupt， and I'll discuss those in a second。

 that they are related to timer interrupts。Then it will be a one。

Anything else is a program exception and some sort of an error in the code。

The hardware will immediately save the previous mode。

 whether we were executing in user mode or supervisor mode when the exception or interrupt occurred。

That will be saved in this bit here of the status word。

 and we will also save the previous value of the interrupts enabled bit in S P， I。e。Finally。

 we will disable interrupts and change the mode to supervisor if it was not already supervisor。

 At that point， the hardware phase of the trap processing is done。

 and we begin executing the first instruction of the handler code。

The handler code will do a lot of things。 Who knows what exactly We'll see that with the colonel。

 But at some point in the future， we'll be ready to return to the interrupted code For that。

 we will use the risk construction called S Ret。For return from supervisor mode。

What this will do is restore the interrupts enabled bit from the saved copy。

Return to whatever mode we were in previously and restore the program counter to whatever we whatever it was before。

 and then we will resume executing the code that was interrupted。

Now that's what happens in supervisor mode and most of the kernel runs in supervisor mode。

 but there's a little bit of the kernel that runs in machine mode。

And so now I'm going to talk about trap processing in machine mode。 It's essentially the same idea。

There's another register called M status， actually it might be a mirror copy of the same register。

 so there might be it might actually be implemented as one register。

 but for all intents and purposes， you can think of it as a separate register。

And like the S status register， it has bids for。Disabling or enabling interrupts。

And for saving the previous value of the interrupts enabled bit。 And finally。

 it has a field for saving the previous mode level。We could have been interrupted in user mode。

 supervisor mode， or machine mode。So we have two bits to save that。

If we're executing in machine mode， then we will not be having any interrupt to supervisor mode。

 so interrupts and traps only go upward， so there is no。

 we need two bits for machine mode interrupts， but for supervisor mode interrupts we only need one bit because we could not be coming from machine mode to supervisor mode。

The only interrupt that we deal with at machine mode level is the timer interrupt。

And we have a mechanism for delegating all other traps。

 all other interrupts and exceptions to be handled at supervisor mode。For some reason。

 we cannot delegate the timer interrupt。 So we're going to see that it gets sort of mutated into something called a software interrupt。

So interrupts are always enabled at the machine mode level。 So whenever a trap， sorry。

 whenever a timer interrupt occurs， it will be handled。Whenever any。Trap of any other kind happens。

 It will be automatically delegated to supervisor mode and whether or not it is handled immediately or whether it becomes pending。

 will be determined by whether interrupts are enabled or disabled at the supervisor mode level。

When a timer interrupt occurs。A machine mode handler will run。

 and that code will create or or force or synthesize something called a software interrupt。

And that will interrupt supervisor mode code。And the handler at machine mode。Will continue running。

 and it will re interrupts and return to the interrupted code。

If the interrupted code was supervisor code， it will return to supervisor mode。

 if the interrupted code was user program， it will return to that。

If interrupts are enabled at supervisor level， then。

An interrupt will occur immediately at that level。 Otherwise。

 if the colonel has momentarily disabled interrupts at supervisor mode level。

 then the interrupt will remain pending until the colonel is ready to deal with it。

The trap processing at machine mode level happens pretty much the same way。

 It's exactly the same idea。 As I said， the only cause of interrupts are timer interrupts。

Every other sort of interrupt is delegated at the hardware level immediately to supervisor mode。

 and so we don't do this processing for anything， but timer interrupts。Like the STVc。Register。

 there's also an empty Vc register， which contains the address of the machine mode trap handler。

In X six， that code is a function called timer V， and that will handle the timer interrupts。

The hardware will take the following actions after completing the previous instruction。

 it will save the program counter in a register called M EPC。

It will load the program counter with MT TVc， which will force a jump to the handler。

The M cause and M T vow registers are ignored。 It's a timer interrupt。

 and there's no further information about it that we're interested in。

The hardware will save the previous mode， whether we were executing in user mode。

 supervisor mode or machine mode， and we'll save that in these two bits。

And then it will save the previous value of interrupts enabled。In this bit。

 and it will then disable interrupts。And switch to machine mode。We'll then execute the timer V code。

And what will it do， Well， it will synthesize or cause and interrupt at the supervisor level。

 So it's going to do something that will create an interrupt at that level。

 that interrupt is not a timer interrupt， but it's a so called software interrupt。And then。This code。

 which is fairly short， will execute an instruction called M returnturn。 return for machine mode。

And it will restore the interrupts enabled bits。It will restore the mode to whatever it was previously。

 and it will restore the program counter， thereby returning to the code that was interrupted。

What's going to happen after that， Well， we've raised this software interrupt。

And what happens will depend on whether interrupts are enabled or disabled at the supervisor mode level。

If the interrupts are disabled， then the software interrupt will become pending and it will just have to wait until the kernel is ready to enable interrupts。

If interrupts are enabled， then the trap will occur at supervisor level immediately。

So we have this MII。e bit。That enables interrupts。At machine mode。 And we have this S I。e。 bit。

 which enables or disables interrupts at supervisor mode level。 And these are global enabling bits。

 There's also， so the interrupts can be all interrupts can be enabled or disabled by changing these bits in the status registers。

We also have a facility for doing more selective control in the risk architecture。

 it's not really needed， but I want to cover it because we have these registers and they are touched during initialization。

So the MIIe for machine mode interrupts enabled。Is a register。

It's rather confusing because there is a bit called MII。e。 in the status word。

But this is a separate register。 Likewise， there's a bit called S Ie in the status register， S I。

e is here， and we have a register called S I。e as well， but these are separate things。

For the selective control， we have a bunch of different bits going on here。

 but we're only interested in this one bit。This stands for machine mode， timer， interrupt enabled。

 and we will set it to one during the initialization phase。 This happens in the start function。

 which is executed in machine mode。We also have a way to selectively enable and disable。

 interrupts at the supervisor mode level。That's taken care of in this S I。e。 register。

And the bits that we're interested in are these three bits。

 We have one to enable or disable device interrupts that is interrupts from hardware devices。

 We have one to interrupt。 sorry to enable or disable software interrupts。

And we have something for timer interrupts， but I'm not sure why that's not usable here。

 We can't seem to delegate timer interrupts down here。 so， but this bit is。

 I just want to mention it anyway。And so what we'll do in the initialization is to set all these bits to one。

We also have a register called SIP for interrupts pending。This has the same format。

 So when a device is interrupting， the bit will be changed to one when theres an interrupt pending。

 and if there are no interrupts， it will be 0。 So we have the ability to force an interrupt to become pending or to happen by setting this bit to one。

 And that's what the timer Vec code， which is executing a machine mode will do。

 It will set this bit here to one。In the SIP。Register。

 thereby forcing the software interrupt to occur。So。I'm saying that here。

 the timer interrupt handler， which is running in machine mode， will set the SS SIe bit to1。

 and that will force a software interrupt to happen at the kernel level。In supervisor mode。

So now we have the ability to delegate。Trapps， a trap being either an interrupt or an exception。

So all traps in the risk architecture will go to machine mode handlers。

 but there's also facility to sort of bypass the machine mode handler and go straight to a handler that's executing at supervisor mode。

Level， and that's what we do。X v6 delegates all traps to supervisor mode。

 so normally it would be handled by a handler running in machine mode。

 but we're going to delegate things to supervisor mode。And there are two registers。

 M E delegation and M I delegation， which are used to delegate exceptions and interrupts。So。

X 36 will set these bits in these two registers to delegate traps so that when and an interrupter an exception occurs。

 it will be immediately handled。In supervisor mode by the kernel code。For some reason。

 the timer interrupts can't be delegated。 So as I said。

 it's handled a bit differently by doing this software interrupt thing。So these two registers， M。

 Deg and M I， Deleg， are initialized during start in which it happens in the start function。

 which executes in machine mode。They are set to one， and they never change。When a trap occurs。

Because these interrupts and exceptions are delegated。 Nothing happens in machine mode， instead。

It immediately becomes a supervisor level， interrupt or exception。

So let me just point out these registers。 So here is the register for delegating exceptions。

 And on the next slide， we have delegating interrupts。

And we have a bunch of different kinds of exceptions that might occur。

 We have page faults for stores and loads and instruction fetches。 We have environmental calls。

 the system call， we have different access faults， we have faults related to misalignment。

 if an instruction is illegal and attempt to execute an illegal instruction。

 we would have an exception for that and so on。 So there is an instruction that is executed to set the M De register。

And basically， we're just setting all the bits to one。This is not exactly legal assembly code。

 but I think it gives you the idea。 It writes into the。Control and status register called M E Deleg。

 a value of all ones。For delegating the interrupts。

 we have a register called MI delegation and it contains some bits and we have the ability to delegate device interrupts。

 we have the ability to delegate timer interrupts， which apparently we can't happen for some reason we don't have that ability。

 but in any case they're set to one。 and for software interrupts。 we could delegate those as well。

 The initialization is very simple。 it basically just sets all these bits to one So we have this going on。

 Okay that's it for this video， Sue in the next one。



![](img/bef91684c29e5c6ec5a990daeb948ba1_2.png)