# hhp3《xv6 操作系统内核｜The xv6 Kernel 2022》中英字幕 p07 -07-xv6 Kernel-7_ RiscV Architecture.zh_en -BV11CkSBsEtN_p7-

![](img/8809b2b6b49ce7388f780f5b258de901_0.png)

This video is part of a series on the X6 operating System kernelel。

In this and the next couple of videos， I'll be talking about the risk 5 processor architecture。

I'll be going into it in enough detail so that you can understand the X E6 Colel。

 but I won't be going into great detail。I won't assume that you have any prior knowledge about the Ri 5 architecture。

But I'm not going to go into it in enough depth for you to become an assembly language programmer。

Let's start with the registers。The Rik five instruction set architecture has 32 general purpose registers。

And a program counter， all of which are 64 beds。So let me go through these registers here are the register names and we start with the first one。

 which is hardwired to be zero， so we won't need to save it when we do contexts。

 which is between processes。r a is the return address。

The risk 5 uses kind of a clever system for function calls and returns。When a call is made。

 the return address is saved in this register rather than being pushed on the stack。

And then the return instruction simply copies of the value from the return address register back into the PC。

So for many functions， we don't need to access main memory at all。SP is the stack pointer。

 the stack grows downward。TP is the so calledled thread pointer。In the X6 kernel。

 it will contain the core number， which is the heart I D， the hardware thread。 So thread here。

 I guess， might stand for a hardware thread。GP is a global pointer。

 It's used by the compiler and will be set and not changed。 Basically。

 it just is used to make accessing global and shared variables。Quick and efficient。

Then we have the a registers， which are used to pass arguments to functions。

A0 is used for a return value if the function returns something。

The a registers and these T registers can be used freely within a function to。

Do whatever the function needs to do。In addition， we have 12 so called callee saved registers。

The caller will assume that any function it calls will not modify these。

 So if a function wants to use any of these registers。

 then that function must save them before using them。

 So typically they would be pushed onto the stack， and that function must restore these registers before returning。

So this is the entire state， these 31 registers here and the program counter。

This is the entire state of a user mode thread。User code has no access to the status register。

 so the status register is invisible in user mode code。At each context switch。

 that is when we are ending one processs time slice and about to begin the time slice of another process。

The colonel will need to save the state of the previous thread。Okay。

 the previous process registers will be saved somewhere by the colonel。

 And then before the next time slice begins。The colonel will need to load the registers to constitute the state of the next process。

At any time， the risk processor is in one of three modes。There's machine mode， M。

Their supervisor mode。S， and there's user mode， U。So each core has its own set of registers and each core is running in exactly one mode at any one time。

Machine mode is the highest and most powerful mode with the greatest privileges。

 And after the core starts up or is reset， it will go into machine mode。

In the XV6 kernel machine mode is not used very much。

There is some code that is executing in machine mode on startup that does some initialization stuff。

The other thing that。We need machine mode for is for dealing with timer interrupts。

Timer interrupts require the handler to run in machine mode。

 So there is a little bit of code that will run in machine mode。

That code immediately converts the interrupt into and interrupt to the supervisor mode code。

And then it basically returns quickly。 So this handler。Is short and quick。

 And just basically converting the interrupt， the timer interrupt into an interrupt to code running and supervisor mode。

So supervisor mode is where all the action happens， all the kernel code runs in this mode。Of course。

 some instructions are privileged and they cannot be executed in user mode。

 So privilege instructions can only be executed in machine and supervisor mode。And finally。

 of course， we have user mode。 All user code runs in this mode。 In fact。

 we can say that if code runs in supervisor mode， it is kernel code and vice versa。 Likewise。

 any and all code that runs in user mode is user code It part of a user application。

So privilege instructions are of course not allowed in user mode。

 and if a user program tries to do something that's privileged。

 it will cause a trap and the kernel will abort that process。Okay。

 now let's move on to supervisor mode and machine mode will not be going over the individual instructions of the risk five processor。

 Of course we have the usual instructions。Add and move and load data from memory and store data to memory and test and branch and so on。

 But I won't be going over those。In addition to the general purpose registers。

 there are a number of control and status registers， CSRs。In fact。

 the architecture accommodates up to 4K of these registers。 That's a lot of registers。

 There's a lot of complexity here。 And I'm going to sort of present a simplified model。 Hopefully。

 everything I say is correct and true， but I'm going to leave out some details that I think are not necessary for understanding the X6 kernel。

I'm only going to discuss 19 of these CSRs。We have a couple of privilege instructions。

 we have three privilege instructions that are important。We have one to read a CSR。 Okay。

 so this example will take the value in a CS register。

 which happens to be called S status and move it into the a0 register。We have a right instruction。

Takes the value in some register and moves it into some control and status register。 In this example。

 we're writing into the S status register。And finally， we have a swap instruction。

So here you see register A 0。 It happens to be the same。 So this is going to simultaneously。

Write from or copy the value from M scratchch to a 0 and copy from this register here。

 which is also a0 into the CS SR。This is done atically。

So either both of these copies happen or neither of them happen。Well。

 I don't think there's any way that they would not happen。

 They both happened simultaneously without any inner leaving of other instructions。Okay。

 so here are the 19 registers， and I'll just mention that some of them are used and accessible only in machine mode。

And other， others， the ones that start with S are accessible in both machine and supervisor mode。

One register contains the core number。Another is the status register。 We have the trap vector。

 which is basically the address of the handler that will be invoked when a trap occurs。

When a trap occurs， the previous program counter will be saved in the EPC exception previous。

The exceptionception program counter。Register also。

 the cause of the trap will be saved in an S cause register。

 And if there's any additional information， there's an S T vow register。

 which might be updated as well。There's also an M cause register， but we don't care about that one。

There's a work register that can be used by our。Trap handlers。SATP is fairly important。

 It will contain a pointer to the page table， so AP is address translation pointer。

And then there are a number of registers that allow us to。Enable interrupt selectively。

 both in machine mode and in supervisor mode。We can also find out which registers are sorry。

 which interrupts are pending at any one point。And we'll see that later。Finally。😊。

Exceptions and interrupts can be delegated from machine mode to supervisor mode。

 I'll talk about that later。And then we've got something called physical memory protection。

 And we'll talk about that。So before I get going any further， I want to discuss some terminology。

We have exceptions and interrupts， and these are both kinds of traps。 So trap is a more general。Term。

 and we talk about having a trap handler to either handle an exception or to handle an interrupt。

Exceptions are synchronous， which means they are caused by some instruction。 you know。

 some instruction is executed， and that instruction has an exception。The system call instruction。

Happens to be named E call in Ri 5。 And that would cause an exception。Also。

 any instruction that causes some kind of an error。Will cause an exception。

 This could be an illegal instruction or an alignment error or some kind of page fault or memory access。

 something like that。Interrupts， on the other hand， are asynchronous。

 They come from someplace besides the current instruction。

So one example of that is the timer interrupt。Another example is when a device interrupts。

 So we have two two devices。 We have the。Asynchronous Re transmit unit。

 which is the serial communication。Device， and we have the disk， and those can interrupt at any time。

The timer interrupt will only interrupt code running in machine mode。

 or I should say the handler has to run in machine mode。 It can happen at any time， of course。

 but the handler happens to run in machine mode。 and we'll talk about how that's dealt with。Later。

Finally， we have something called a software interrupt。When a timer interrupt occurs。

 the handler is running in machine mode。 it needs to notify the supervisor。Code。

 it needs to notify the kernel。 So it causes what's known as a software interrupt at the supervisor level。

So a software interrupt will be caused by code running in machine mode whenever a timer interrupt occurs。

 And then that software interrupt will be handled by。Code that runs in supervisor mode。That is。

 the colonel has a。Interrupt handler for the software interrupt that will do what it needs to do for a timer interrupt。

Finally， in this video， let me talk about two registers。

 three registers that are fairly easy to discuss。

![](img/8809b2b6b49ce7388f780f5b258de901_2.png)

The heart is synonymous in these videos， at least with the core or the processor number。

 So this register M heart， I D contains the core number。

 Each core has its own separate set of registers。And。The heart I D register is hard wirered。

 It cannot be modified， and it can be queried to find out what core the code is running on。

The kernelel will immediately move this value into the T P register during start。

 and it will never change。 At that point， it will stay constant。 So there's a function CPU I D。

 which is used all over the place。 and all it does is return the value that's in this T P register。

Now， I say TP never changes。 It never changes in the kernel。 However。

 all registers are accessible in user mode code， and the user code could easily overwrite TP with some other value。

Whenever the kernel goes from kernel code into user code， it first saves all the kernel's registers。

 including T P。 Then the user code has a time slice and runs until something happens。

 Some kind of trap occurs。 And at that point， the kernel becomes active。

 And the first thing it will do is restore its own registers， including T P。

 So T P never changes within the kernel。We've also got these two registers。

 There's a system for physical memory protection。It is not used in the actually6 kernel。

But we need to deal with it anyway since it's there， basically。

 it's going to be able to limit access to physical memory for any code running in supervisor or user mode。

 so machine mode can basically partition memory into areas and keep the code that's in those areas out of you know keep it from interfering with other code。

The intended usage for this system is to support， secure bootstrapping and。Hypervisor code。

 Hyvisor is some。Code like an operating system where each of the user threads。

 the users are host O Ss。 So the idea with a hypervisor is it's going to use this physical memory protection scheme to isolate the memory of one operating systems use from another operating system。

In our case， with X3 6， this is loaded during start while we're running in machine mode。

 and basically， it marks all of physical main memory as fully accessible。 Read， write and execute。

 And then these registers are not changed after that。😊，Okay， in the next video。

 I'm going to talk about the status registers and page tables， so I'll see you in the next video。

