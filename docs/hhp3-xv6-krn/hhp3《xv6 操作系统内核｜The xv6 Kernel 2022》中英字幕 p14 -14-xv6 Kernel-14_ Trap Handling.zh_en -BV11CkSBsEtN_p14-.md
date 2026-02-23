# hhp3《xv6 操作系统内核｜The xv6 Kernel 2022》中英字幕 p14 -14-xv6 Kernel-14_ Trap Handling.zh_en -BV11CkSBsEtN_p14-

![](img/8e30442a4939663ca60bdd9d5d14968e_0.png)

This video is part of a series on the X V 6 operating system kernelel。😊，In this image。

 we're executing in the user code。 We get a trap and we execute something in the kernel。

 and then we execute a system return instruction and go back to user mode。 In this video。

 I'm gonna talk about what happens when we're in kernel mode。

I'll talk about the data structures in particular， and I'll do a code walkthrough of the Proc do H file。

So let's begin with this thing that I call the roadmap。

 and it shows everything that happens between the trap and the SR instruction。

And let's go through this more carefully here。The trap could be caused as a result of an asynchronous interrupt。

Either the timer is requiring attention or an IO device is requiring attention。

Or it could be a synchronous exception due to a system called by the user mode code or some sort of a program error。

The hardware will do several things。 It will disable interrupts。 It will switch to supervisor mode。

 It will save the program counter in SPC。It will save some information about what exactly caused the trap in this S cause register。

 and it will load the PC with the address of。The user back。Function， there is a。

Control and status register called S T V。 And that contains the address of the。

Code that's supposed to handle any kind of a trap。 And so that's how we branch to this assembly code。

That is located in the trampoline page。 So this trampoline page， recall。

 is mapped into all address spaces， both the user address space and the kernelel's address space。

 And it does the initial saving of the user's state。So what does it do in particular， Well。

 it saves all the general purpose registers and the program counter in the trap frame。

 Each process has its own unique trap frame， but they're mapped into the second highest page in the user's address space。

 This code is executed in the user's address space。

 So then we get ready to start executing kernel code， and every thread needs its own stack。

 So we have to initialize the stack pointer register。And we also initialized the TP register。

 which contains the core number。These two registers will have other values in the user code and we can't trust what values they might have had。

 so we need to load those， but we don't really need to load anything else。

We then load the SATP control and status register with the pointer to the kernelels page table。

 so that will switch us effectively into the kernelel's virtual address space。And at that point。

 we then jump into this function called user trap。 and this is C code。And what does it do， Well。

 it's got a this statement， and it figures out what exactly is going on。 But first。

 it stores a pointer to the another trap vector in S TVc。Previously。

 STV contained a pointer to this function here。 but if a trap occurs while we're executing in kernel mode。

 we want to handle it a different way。 So we update SV here。And then we look at the cause register。

 the S cause register， and determine whether it was some sort of a program exception if there's an error。

 we print a message and call a function exit， which will terminate this process altogether。

If a device needs handling， well， we call this device interrupt function here to take care of that。

There's a boolean called killed that's associated with each process。 And if it gets set。

 we need to terminate that process。 So if for some reason， this process has been killed。

 somebody else wanted this process to die。 Well， they would have set that boolean true。

 And at this point， we check it。 And if it's the case that this process should die after handling the device interrupt。

 we then call exit。 But probably we just continue down here。If the timer interrupted。

 then it's time to have the end of this time slice and give some other processes a chance to run。

 So we check the killed thing。 And if so， we just exit。 But otherwise， we call yield。Yield will。

Eventually return。 But what it will do is it will cause the execution or allow the execution of other processes。

 It will invoke the scheduler and some other processes， which I've hinted at here， will execute。

 But eventually， we'll get another time slice and return to yield and then yield will return。

 and then we'll continue and go back into the user mode process。

If the cause of the interrupt was or cause of the trap was system call。

 then we enable the interrupts。 Okay， so we， this thread itself may be interrupted。 For example。

 there could be a device requiring attention while we're dealing with this system call。

Interrupts are enabled。 and so that might actually occur。 We might go off and do some other stuff。

But in any case， we handle the system call and then we come back and at that point。

 somebody has asked for us this process to guide and we call exit， but otherwise we continue。

 And finally， whatever the case is， we call a C function， user trap rep or user trap return。

 and it will begin the process of returning to the user mode code。

It will disable interrupts in case they got enabled here。

 and it will set ST T back to point to userbe。 So now this is in preparation for the next trap。

 so we need to have it point to userbe。Finally then we need to save into our trap frame values for the stack pointer。

 and we need to save the core number that we're executing on。 Remember we we loaded these here。 Well。

 here we're setting them up and getting them ready to go for when the next trap occurs。

The SRt instruction will rely on the SPC register， so we retrieve the saved program counter and we put it into the SPC register。

 and then we jump into some assembly code and this assembly code is located in the trampoline page。

 It's called user rept and this will complete the process and execute the SRAt instruction。

It will now that we're executing in the trampoline page。

 we are in that top page that lives in every user address， every address space。

 And so we can switch from the kernelel's address space to the user's address space。

 And we do that by loading the SATP register with a pointer to the。😊，Userss page table。

And then finally， we restore the users' registers， and we also set a couple of bits in the status register。

 The Sret instruction will use the status register， and we set bits to tell the Sret instruction。

 we want to go into user mode， we want to the previous privilege level。 will be user mode。

 So we will be returning the user mode。 and the previous interrupts enabled flag。 we set to enabled。

 So this will be copied into the current interrupts enabled flag。 So when we execute the Sret。

Interrupts will then become enabled and we will be in user mode。

You runningning with the users registers and the user's page table and so on。Okay。

 so let's now take a look at some of the data structures that are involved。 First of all。

 let's take a look at this trap frame。While we're executing in user mode。

There's a control and status register called S scratch， and it will point to this trap frame。

 and that will be useful。This contains the place where we will save the user mode registers。

 so up here when we save the registers in the PC and the track frame， that's going to happen。

And that information will be saved here。 the 31 general purpose registers will be saved here。

 remembering that the 32nd register that is register 0 is always hardwired to zero。

 so we only have to save 31 of them。And the program counter， the previous program counter。

 will be saved here。 So that's the state of the user mode thread。

And then we load up the state for the kernelel thread。

 So we have a pointer to the kernelels page table。 That's nice and handy to have。

 and that's right there。We have a pointer to the stack that this particular process will be using。

 and then we have the address of user trap that's that actually not really part of the state of the supervisor thread。

 but we have that in this trap frame as well。 And finally we have the heart IDd or the core number if you will。

 which we will need to load into the TP register when the trap occurs。

 So that's what's going on on the trap frame。We have some other crucial and important data structures。

We have a data structure called CPU。 There is an array called CPUs， and there are eight of these。

 one per core， and each one of these elements in this array is a structure。

 and that structure contains these fields。If a user mode process is running on that core。

 then well have a pointer to the proC structure that describes it。Okay。

 if nothing is running on that CPU， or I should say if the schedule or thread is running。

 this proc field will be zero or no。 And I talked earlier about interrupts and how we can sort of stack them。

 we remember whether initially they were enabled or not。 And then if we want to disable them。

 that we remember the initial value。 and increment a counter。 And then when we back off。

 we can decrement the counter and ultimately return to the original state of the interrupts enabled bit。

And， finally。We have another register save area， called context。Now。

 one thing I didn't really make clear was that。When we're executing a process。

 we're executing either user mode or in kernel mode。But we may switch， and I don't show this here。

 but we may switch over to the supervisor thread。Okay， and we leave that process behind。

 So we're really in all of this what that we're talking about here， we are executing as part of。

A process， okay， but in here， perhaps in here or in in the yield。

 we will maybe go into another processs time slice。

 So we will have other context switches that are different。

 A context switch occurring here is different than a context switch occurring here。

 And so if we leave this process and go into the scheduler thread。

 we will need to save the registers。 And so that's what this register save area is all about here。

 So。Then。let me point out we don't need to save all the registers。

 we only need to save some of the registers， and we'll talk about that later。If。

We are executing if this core is executing a process of thread。

 then we'll have a pointer to a structure that describes that process。

And it's got a number of fields。 So let me go through these quickly。 We've got a lock field。

 We have the current state of the process。 It could be unused， used， it could be sleeping。

 it could be runnable， which means it's ready to ghost and it could be scheduled。

 but it's just waiting for time slice， it could be actually running or after the process terminates we call exit。

 it becomes a zombie for a little while before the structure is then recycled and becomes unused。

If we are waiting on some lock， if this thread is sleeping。If it has the status of sleeping。

 then this channel describes exactly what it is we're waiting on。

Here's that killed bullolean that I mentioned。After the process terminates， it has an exit status。

 and that's what this field is。And every process has an I D number。

 That's sequentially given I D number。 This lock protects these fields。 So let me zoom in a bit。

 this lock。The spin lock will protect these fields。 In other words。

 if any of these fields are going to be modified or accessed， we need to grab the spin lock。

We also have a pointer to our parents， so this is a pointer to one of these other proc structures。

There are up to 64 processes， well there are 64 processes， some of them may be unused。

 but we can have up to 64 processes running and runable at once。

 and for each one of them there is a structure and this is the structure。

 and so this I'm showing just the structure for one process。

 and parent points to whichever structure is the parent process represents the parent process for this parent。

For this process。There is a stack for the kernel aspect of this process。

 So when we are executing here， Okay， when we're executing here。

 we need to have a stack for the kernel to use。Each of the 64 processes needs a separate stack。

 So that's given here by this， this， there's a point for that stack here。

This is the size of the virtual address space， and here's a pointer to the page table for the user's address space。

And then we have a pointer to our trap frame page。 Each process has a unique page in physical memory。

 And so this points to that page。 it will be mapped in。

 They will all be mapped into the second highest。Page in， in the address spaces。

 But this is a pointer to the physical page。 And then we have another one of these context things。

 So this is another save area。 So when we're switching back and forth between the the。Scheduller。

 thread， and the process we can use these two save areas。

And we have an array here for open files and the current working directory。

 we even have a space for the name of this process so we can give processes names。Okay。

 now that we've seen pictures of those。 let's go ahead and look at the definitions in this file proc do H。

So this is a context that was used both here。And here。And you can see it contains。The R。

 that's the return address register。 And that tells， you know， that's the the PC， if you will。

 where we go back to。And then the stack pointer， and then we only need to worry about the S registers。

 there are 12 S registers and we only need to worry about those。

 so we only need to have an area to save those。Next， let's look at the CPU structure。

 the CPU structure here， and we see that it contains a pointer to the process if it's running。

Or null， if not。 And we have an area for the context。The save area that I showed here。

 And then we have these two fields that are the depth of the push off every time we call push off it increments that that counter。

 And this remembers whether interrupts were enabled before the initial push off。

And then here we have our array of well we have eight CPUs。

 so it's an array of eight elements of these of these structures The next thing we want to look at is the。

Trap frame， So I'm not going to read through this information here。

 but here's what's going on in the trap frame。 We're going be accessing this in assembly code。

 So we actually care about these offsets。 The trap frame is a page。

 and this will be page aligned And these are the offsets given in comments here。

 of each of these fields。 You can see that each of these fields is a 64 bit number， right。

 And here are the fields that I mentioned。 Let me get my trap frame。Picture here。

 And so you can kind of we can go along。 We've got the SATP。The stack pointer， this trap。

 I did these in a slightly different order， the saved PC， and then the core number。And then we have。

 you can count them， we have all 31 registers here and。Okay。

 so we have all 31 registers there just in case you're curious。

 they're listed in sort of a strange order， for example we have some T's here， we have some S's here。

 we have some A's here， we have more S's and we have more T's down here。

That's the actual way they're organized in the risk5 processor。

 but we just care about we just access them by name and we don't really care which this is register x1。

 x2， x3， and so on。Next， let's take a look at the。Proc structure。 Okay， so that's。

This structure here。We're going to look at this structure here and it's shown whoops。

 let's see if I can z man there。The state down here is a proc state。 and as I said。

 here are the states unused。Used sleeping。Runable， running and zombie。

 So when the process is actually running on the core， it has a status of or a state， if you will。

 of running when it's ready to run。 And but unfortunately， there's not an available core for it。

 It's just sitting around waiting for a time slice。 it's runable。 If it has waited on something。

 It will go into a state of sleeping。And。If it's terminated。

 it will become a zombie until it can be recycled。 These structures are recycled。

 We only have 64 of them。 So we need to reuse them after that process is killed。 We need to。

Reuse that structure。 It remains in the zombie stage for a little while until the exit status。

 this exit state can be retrieved by the parent or whoever waits on it。

 and then at that point it but can be recycled and it becomes unused and then used as sort of intermediate between unused and something else。

So here we have the lock， that's very important， we need to lock the process。And in particular。

 we need to lock it whenever we're going to be using these fields。 Here's our state field。

Listed up above。Then we have this channel field。 It could be zero， but I mean。

 it's it's only relevant when we're asleep and it tells what we're sleeping on。

 We'll get into how that works later， but basically it's just an identifier and that identifies as different things that we might be waiting on。

And here's the boolean that indicates whether someone has asked for this process to be terminated。

 Here is an integer that is used to。Transfer and exit status from the process itself to whoever waits on it。

And then this is an integer that's just the process ID number。

Here is a pointer to another proc structure that is the parent' process。

Wight lock must be held when dealing with this field。And then we have some so called private fields。

 The lock does not need to be held when we are dealing with these。

 This is the address of the Colel stack。Here is the。

Size of the virtual of the virtual ider space here is a pointer to the page table that describes the virtual ider space with。

Here is a pointer to the。Data page that the trampoline is going to use。

 this will get mapped into the second highest page， but here's a pointer to that。

Here is the context area。 So when we switch this process， we'll we'll be using that。 And finally。

 an array that is used for open files。Number of files is the number of files that could be opened simultaneously and current working directory and then we have a field of 16 bytes for a process name that we can use。

Okay， I think that covers our road map。 And hopefully this image will help you understand what's going on in the next video。

 I plan to discuss the user back and user trap functions， as well as user trap rep and user rep。

 See you in the next video。

![](img/8e30442a4939663ca60bdd9d5d14968e_2.png)