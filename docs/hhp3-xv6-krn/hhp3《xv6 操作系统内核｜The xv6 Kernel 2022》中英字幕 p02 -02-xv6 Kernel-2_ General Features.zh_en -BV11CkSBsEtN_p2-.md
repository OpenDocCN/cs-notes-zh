# hhp3《xv6 操作系统内核｜The xv6 Kernel 2022》中英字幕 p02 -02-xv6 Kernel-2_ General Features.zh_en -BV11CkSBsEtN_p2-

![](img/b2b4b866a1ec574fac361a59d6118487_0.png)

Hi， welcome to another video in a series on the XB6 operatinging System kernelel。

XV6 is an educational kernel， and in this video I am going to talk about some general features of the kernel。

It's meant to run on a shared memory multi processor。 In other words。

 it's meant to run on a system with multiple cores。

 but which all share a single range of main memory。In this video and in the code。

 I'm going to be using the terms。CPU， core and heart synonymously。 So in the in the code。

 sometimes you see CPU， sometimes you see heart。 and I tend to say core。

 but they all mean a hardware processor capable of executing a single thread of control。

This term heartRT， which stands for hardware thread。

 is something that I first encountered when reading the Ri5 documentation。

The idea is normally a core will execute a single hardware thread。

 but for some high performance cores， you might have say two hardware threads， for example。

 with the Intel hyperthreading architectures， you might have two threads running on a single core。

 the idea is that these two threads are being interwoven。

 the instructions are being executed concurrently or possibly interwoven in such a way as to share some of the processing hardware。

The idea is， to， increase the performance per transistor。So this term heart appears。

 but for our purposes we're going to be running it on a system with multiple cores and so these terms are all synonymous。

 there's just a single hardware thread per core。Okay， main memory is shared。

 sometimes we call it RAM in a real operating system。

 the issues regarding the caching of main memory， L1。

 L2 and so on are important and the kernel needs to sort of work around the caching schemes and caching system in order to improve performance。

In this kernel， all concerns about caching are completely ignored。The main memory is 128 megabytes。

 and this is just hardwired into the kernel's code， it's fixed with a pound sign defined。

A typical real world operating system kernel is going to look at the amount of memory that's available on the machine when it starts up and it's going to configure itself to use all the physical memory。

But with XV6， it's just hardwired in with 128 mebytes。

The XV6 system can handle a couple of different devices。

 The UART is the device that handles serial communication。

This stands for Universal Asynchronous Re transmit unit in the old days it was a separate chip。

 but now it's integrated on the processor chip along with the cores and so on。

This is the device that provides a communication channel for printing and reading input from a keyboard。

 typically。If you program with the Arduino， you're probably going to be familiar with this。

 essentially can send a by stream in one direction and receive a by stream coming back in the other direction。

The XV6 system。Has one disk drive， and that will be emulated， of course。

 with the file on your host laptop， but there's a disk device。There are also timer interrupts。

The UA and the disk are shared between all the cores， but each core has its own timer interrupt。

 so these are local to the core。ThePros in the real world contain something called a p or platform level interrupt controller。

And what this does is a separate chip or separate circuit that deals with interrupts coming in from all the different devices that might be on a system。

 and it's figuring out which core should be interrupted。

 which core should be told about the interrupt and allowed to handle the interrupt and deal with it the emulator will emulate the platform level interrupt controller。

 and there's also a core local interrupt controller。

 which is also part of the emulation and there is one of these core local interrupt controllers for each core。

 so the operating system has to deal with these things as well。Memory management is pretty simple。

 memory physical memory is divided into pages and the page size is fixed with a pound sign defined at four kilobytes。

Memory is allocated， at least for the kernel。From a free list， there's a free list of unused pages。

 and it's a simple linked list and whenever the kernel needs more memory。

 it allocates the page from the free list。And when that page is no longer needed。

 it is returned by adding it to the front of the free list， very basic memory allocation scheme。

There are no objects in the operating system in XV6。

 there are several different structures and of course they're pointers。

 but with an object ored programming language typically you would be allocating variable-sd objects none of that's going on in a real worldorld kernel。

 there are other aspects for there are other techniques for allocating memory to accommodate variable- sized chunks of memory。

 but that doesn't happen in XV6， there's no mallik， for example。

The virtual address spaces are handled with page tables， the page tables are three levels。

 I've shown diagrammatically a three level page table down at the bottom we have the data pages。

There's one table per process， and in addition， there's one page table for the kernel itself。

 which maps all of the physical memory。 That table for the kernel is shared by all the cores。

The pagetable hardware can accommodate marking the data pages as either readable， writeable。

 executable。And U stands for user mode access and V stands for valid。

 so a page may or may not be ridriable， it may may or may not be executable。

 it not may or may not be valid。It can also be marked。You or not you。

 and that determines whether the page can be accessed when the processor is running in user mode。

Well， I just used the word processor here and probably I should have said core。

 so sometimes I guess I use the word processor synonymously with CPU and core。It shows my age。

 perhaps some pages。May be restricted so that they can only be accessed when the core is running in kernel mode and other pages can be accessed by user mode code。

The scheduler for XV6 is quite simple。 It's a basically a round robin scheduler。

Each process is given a time slice， and then it goes back。 It becomes。

Dorant sitting on the ready queuee， the size of all time slices are fixed。

 It happens to be fixed at 1 million cycles。All the cores share a single ready cue。

 sometimes a Redicquee is called a ready list or a run list or a run queuee。

 I'll use all those terms probably。But in any case， there's only one of these things。呃。Now。

The cores share the single ready queue。 And so when a core is ready to run a process。

 it will select a process， the next runnable process from the ready queue。

 and it will give it a time slice on that core。 and then it will。

Return it to the ridiculee after the time slice ends。And。

So this ridiculee is actually an array and what's happening is each core for scheduling is going through that array linearly。

 when it gets to the bottom of the array goes back up to the top and what it's doing is it's searching for a process。

That is runnable， that is it's ready to go， and it's ready for its next time slice。

And when it finds one， it gives it a time slice， and then after the time slice ends。

 it returns it to the Rediculee as a runnable process and moves on to the next。Process。

 and so it just keeps going through。 each core keeps going through that array repeatedly。

And so I said this is a round Robbin scheduler， it's not quite round roin because what can happen is a particular process might be given a time slice。

 say on core number one。And then after the time flies is completes。

 the core will put it back on the ready queue and then move on to find another runnable process。

But immediately or very soon after， some other core， perhaps core number four。

Might be searching through the array and it might happen to come to that same process P and so it will give it a time slice and then put it back on the ridiculee when the time slice ends so what happens is this single process P might be given a time slice on core number one and then immediately after given another time slice on core number four and so normally with round Robin。

After process P is given a time slice， it needs to wait until all other runnable processes have a chance to run。

 but with XV6 and the multiple cores， it's sort of round robin within each core。

 so it's not quite a proper round robin scheduling。

 but it's simple and it's probably just about as effective， equally efficient。

The boot sequence is pretty basic。The emulator， which will be。

imulating the Ri5 processor and running our kernel basically skips all the boot sequence altogether what it's going to do is it's going to load the kernel from some executable file on your host laptop and it's going to put it into the memory or I should say the fixed physical memory sorry the emulated physical memory of the risk processor it's emulating and it's going to put that kernel code at a fixed location。

 in fact this is the actual location that it uses。There's no support in X6 for booting a boot loader or a master boot record or bio or anything like that。

Actually six uses a couple of techniques for locking and concurrency control。Spin locks are used。

And there are two functions， sleep and wake up。With spinlocks， you have two functions。

 they're called a acquire and release。And there's a single word in memory。

 that word is zero if the lock is free or unheld， and it is one。

 if the lock is busy or is locked is being held by some process。

And what a choir will do is just basically in a tight loop， wait for that word to become zero。

 unlocked， and then when it finds that it's unlocked， it will set it to one。

And release just simply sets the word back to zero。呃。Sleep and wake up， well。

 when a particular thread executes the sleep function。

 it will end its time slice and it will be placed back on the reiculee with a status of runnable。

 sorry with a status of not runnable and it will then sleep until it's been until it is woken up。

So when a process executes the sleep function， that process will no longer be runnable。

 it will go into a blocked or sleep state， and it will not be scheduled。Later。

 some other process will execute the wake up function and wake up one or more processes or zero or more processes。

 and if our process happens to get woken up， then it will be changed back from a status of sleeping or blocked to runable and then it will get time slices after that。

There's also a third technique that is sometimes used。

 and that is the selective disabling of interrupts。So each core has a status control word。

 and there is a bit in that control word that can be either said or cleared。

 which either enables and allows interrupts or disables and prevents interrupts。

By disabling interrupts， a thread running on one core can prevent being interrupted when a timer interrupt goes off or when an IO device calls for an interrupt。

 So we can use this technique on one core to prevent being interrupted by another thread on that same core。

 However， X V6 is a multicore system and disabling interrupts on one core has no impact on other cores。

 So a thread on another core can be modifying memory simultaneously。XV6 has a number of fixed limits。

 these are declared with pound sign defines， for example the number of processes is just a fixed number。

 as I said， the reiculee is stored in an array and that array is allocated with a fixed size。

 the number of files open the maximum number of files that can be open simultaneously as a fixed number and so on。

The kernel tends to use arrays and not linked lists so much。

 and so in several situations we are running through these arrays with a linear search。For example。

 there's a function to kill a process and it's past the process ID。

 and what it does is it does a linear search of the array of processes。Actually。

 this Read queuee here is not a separate data structure。

 there's a single array of processes and some of them are marked runnable and some of them are not runnable and so when we want to find a process that's runnable。

 we basically just go through the process array looking for one that has a status of runnable。

And likewise， when we want to kill a process， we just run through the array looking for one that has a matching process ID。

Okay now let me talk about the user address space， so this is the virtual address space that a user mode program sees and here I'm showing the address starting at location zero going up to the maximum virtual address。

The kernel will allocate this address space in units of pages each。

One of these is a 4K page and so when the Ex system call is used。

 the kernel will go out to the file system and find the executable file。

 which is in Elf format and it will allocate several pages， an integral number of pages here。

 and it will read in the data and the code into this region of memory。

Those pages will then be marked， read， write， and executable by the colonel。

You also have a page allocated for the stack。We see here that the stack only gets one page。

4 kilobytes of memory， and so XV6 is somewhat limited in this aspect， a process that wants to grow。

 its stack beyond this will not be able to and so XV6 cannot support that。

 and when a process tries to grow its stack beyond that， it will simply be aborted。

 the process will be terminated。And the way the kernel does that is kind of clever。

 it allocates what is called a guard page right here， this guard page is not readable， not writeable。

 in fact it's not accessible in user mode， so if the user mode code tries to access this page of its virtual ladderer space。

 it will immediately cause an exception and the process will be thrown out and terminated。The he。

Starts after the stack and grows in units of pages。This is called the break。

 if you program in Linux or Uni you may be familiar with this concept as the user mode code allocates things on its heap。

 this boundary here will be moved up the kernel will be invoked to。

Alllocate more pages and the break point will be moved up and will consume some of the unused space these pages will be marked read and write。

I should say that in a typical Linux or a Uni system。

 the stack is usually put out in high memory and it grows down and it's capable of growing and memory is only filled up when these two when the heap and the stack run into each other。

That's not done with XV6。 we have just a single stack page down here。However。

 we have something interesting going on。 We have two pages up at the very top of the virtual memory space。

 virtual memory happens to be 256 gigabytes， so this unus space here is actually huge。

 and the heap may not take up very much of that and certainly it's not going to take it all up because we only have 128 megabytes of physical memory and we're not going to be able to accommodate anything larger than that。

 any virtual address space that exceeds 128 mebytes。

These pages up here are marked not accessible in user mode， so user code cannot access these pages。

 user mode cannot read them or write them or execute any code from them。

These are used during trap and exception processing。So the trampoline page contains code。

 so it's executable。And when an exception or interrupt occurs。

 we're going to be executing code in the trampoline page。 We'll discuss that later。

The trap frame is readable and writeable， and that is where the。

Registers will be saved when a trap that is when an exception or an interrupt occurs， the registers。

 the entire state of this user process will be saved and it will be saved in the trap frame。

By code in the trampoline page。There is。Each virtual outerspace has its own trap frame page。

 so they're all mapped to the same location。But there are different physical memory pages。

 so each process has its own。Trap frame。 The trampoline page is shared by all。Processes。

 so the exact same page of physical memory is mapped into the same spot in all of the virtual address spaces。

One thing I was going to mention was that。I said that the kernel doesn't have a very sophisticated memory allocation system。

 it just has pages and they are kept in a free list。

 and so all allocations are in units of one page or 4 4096 bytes，4 k bytes。However。

 we accommodate heaps for the user mode programs， so a user mode program is free to implement Maloc with and allocate things on the heAP。

 in fact it's free to implement whatever complex garbage collection algorithm it wants to。

 but it just has this memory that can be grown here to allocate its memory to accommodate its memory needs。

So I mentioned that this not you here means that the guard page is not valid when it's accessed in user mode。

 likewise the trampoline and trap frame pages are not。Accessible in user mode。

C programmers will be familiar with the main function， which takes a couple of arguments。

 Arg C and R V。And these point to the arguments that are passed into the program when it begins executing。

You may also be familiar with something called A E for environment。

 but that is not accommodated with XV6 that doesn't X V6 doesn't。Use any environment variables。

 just Arg C and Argv。 And how does that happen Well， when an exact system call is made。

 the code in the kernel will set up the virtual address space here and among other things。

 it will allocate a page for the stack and it will push onto the stack， The arguments。

 we'll get into the details of exactly what's pushed later。

 but basically it's going to push all the arguments onto the stack and then set the stack pointer to be something。

Besides right here， it will allocate these things on the stack。

 essentially pushing them onto the stack and moving them into the registers。

 so when the first instruction of the user program is executed。

 it will already find several things on the stack， it will find its the arguments on the stack。

Now I mentioned that we could only have 256。Gabytes of virtual address space。

 I want to mention that the。Risk5 architecture， it's a pretty complex architecture and there's several different options for page tables。

 there are three options called SV32， SV39 SV48。The version of the architecture being used for X V 6 is the S V 39。

Version。The first one is a two level page table scheme。

 the second one is a three level page table scheme and SV48 is a four level page table scheme。

 so XV6 uses SV39 architecture which provides for our three level page tables。Okay。

And with that particular scheme， virtual addresses are 39 bits。Well。

 39 deaths happens to be2 to the 39 happens to be 512 gigabytes。

 so with this scheme we could actually access 512 gigabytes。

Two to the 39 expressed in hex is this number here。

 and so you can see that expressed down here here are 39 bits。

And the first bit beyond that would be in here right here，8 is 1000。And then zero is0，0，0，0。

 and so on。So。呃。It turns out that X V6 only uses 38 bits。 It does not use the full 39 bits。

 It's 1 B shy。And so 2 to the 38 is actually 256 GB， And that number is 4，0，0，0，0，0，0，00。

 That is equated to our maximum number。 So this our address range is from 0 to。3 F。That's3 is 11。

 and then F，1，1，1，1， so 3 f。1，1，1，1，1，1， and then F F， F， F F， F， F， and then F， F， F， F。

 So our maximum address is this。 And so maximum。Virtual address here is actually。

The address of the byte， just beyond our virtual address。Okay， that's it for this video。

 I'll see you on the next one。