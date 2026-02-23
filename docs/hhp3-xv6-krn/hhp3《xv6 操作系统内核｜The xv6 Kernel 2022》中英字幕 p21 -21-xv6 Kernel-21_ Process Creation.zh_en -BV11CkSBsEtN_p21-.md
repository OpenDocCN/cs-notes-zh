# hhp3《xv6 操作系统内核｜The xv6 Kernel 2022》中英字幕 p21 -21-xv6 Kernel-21_ Process Creation.zh_en -BV11CkSBsEtN_p21-

![](img/440051606a3a7334cc1247c1d0cc40db_0.png)

This video is part of a series on the XB6 operating System kernel。In this video。

 I'm going to talk about processes and in particular。

 the data structure that is used to represent a process。

 I'll talk about how the array of proC structures is initialized and how we set up the data for the initial first process。

 This stuff comes from the file proc do C， which also contains a bunch of other stuff。

 So in addition to this material that I'll be talking about。

 it also contains the code for the scheduler for yield and so on。

As well as the code for the sleep and wake up functions。

 I've covered these things in previous videos。 The file also contains code for functions like fork and weight and kill。

 And I'll cover those in a future video。😊，So let's begin with the file itself and。

I want to start with these two fields。 There's a process I D counter that's initialized to one。

 and there's a spin lock called P I D lock。 So right off the bat。

 we can take a look at this function， Aloc P I D。 So whenever we need a new process I D。

 we can call this function。 And it's pretty straightforward。 It returns the new process I D。

 And in order to access to read and update the next P I D。Global variable。

 We need to acquire the lock first。 So this acquires the lock。

 and then it reads the current value into a local variable and increments the global variable and then releases the lock。

 So this is pretty straightforward use of acquire and release。Okay， now that that's out of the way。

 we can go into the first function that I want to cover， which is proc and net。 Before I do that。

 let me。Remind you of the structures that are relevant for this video。

We've got an array of proc structures。 So here I show one of them， and we have 64 of them in total。

 one for each process。 And remember that they have a spin lock and some fields such as the state。

 whether it's running or runnable or so on。Channel， if it's sleeping。

 bullying for whether the process has been killed and some other things。 we've also got a。

Pointer to the area in virtual memory where the stack is located。 So I'll come to that in a second。

 The size of the address space。 that is the break point for where the top of the heap is for this particular process。

 pointer the page table a pointer to the trap frame。

 a context for saving it and a few other things such as the name field。

 So I'm not going to go over that just now， but I do want to talk about this function proc knit。

 which initializes the proc array。 And this is called once by core0 only during the initialization of the kernel。

 and it initializes that lock for the process I that we just saw。

 and it also initializes another lock called weight。PID， sorry， weight lock。

 And then it goes through this proc array。 Okay， so it's going through the proc array。

 And for each one of them， it initializes the spin lock， Okay， so。Goes through。Yops。

It goes through this array， and for each one， it initializes the spin lock。

And it also initializes this k stack。 Okay， so at this point。

 I'll talk about what the virtual address space looks like for the kernel。

 Remember that the kernel virtual address space， like all addresser spaces will have the trammppoline page mapped into the uppermost page。

 And then it has a series of guard pages and stack pages。So for each of the 64 processes。

 there is one。Page and the virtual ladderer space for the stack that will be used when that process is running in kernel mode。

So at this point here。In the proconate function， we are。Determining the virtual address。

 this is a preproces macro function， given a number between 0 and 63。

 it determines the virtual address for that stack page。

 and it simply saves it in the K stack field of this proc structure。

 So here's the proc structure again。 Here's the k stack field。 And it just saves the virtual address。

 And I added this dashed line to indicate this is a virtual address。As opposed to these links here。

 the page table points to physical address somewhere in physical memory。

 as well as the trap frame pointer， which points to the actual physical address of the trap frame。

Trap frame， of course， will be mapped into the second highest page of the virtual address space。

 but this point right here is to the actual physical page that was returned from K Ac。

 and we'll see that happening in a second。There are a couple other functions in this that I've already mentioned。

 but I'll just review them。CPU ID returns the number of the core that's currently executing this function by just returning the value of the TP register。

The MyC uses that current core number and returns a pointer to the CPU struct。Okay。

 so here is the array of CPU structures。 And here I'm showing one。 there are up to8 cores。

 That's a fixed constant。 And each one of them has a CPU structure。 And so were。

Returning a pointer to the one for the current core。And finally， we have the my proc routine。

 which gets the。Poiner to the current CPU struck and then follows the proc field to get a pointer to the。

Structure that represents the procedure that's currently executing。 Okay， each CPU struck。

Each CPUusstruct has a proc field that points to a proc structure。Each core at any one point in time。

 is either executing。The scheduler code， or it's executing one of the processes。

 If it's executing a process， then this pointer is valid， It points to a prostruct。

If the CPU is executing the scheduler code， then this will be null。O， so those functions are。

Pretty straightforward。 Next， let's take a look at proc dump。 I think proc dump is simple。 Basically。

 this is for debugging。 And it's just going to go through the proc array and printed out。

 print out information。 So it's past nothing and it returns nothing。 And what does it do。 Well。

 as I said， it's a for loop that goes through the entire array of all 64 proc structures here。

And if that。Strt is unused okay， in other words， if the state here is unused。

 then we just don't print out anything。So we continue and repeat the loop body。 Otherwise。

 we look up the state in the array that we have here。 We have a little array that maps the。

Constance unused sleeping runnable， running and zombie into short strings。

 And so we grabbed the string here called state。 we're here。

 we're just checking to make sure it's a valid valid number。 Otherwise we use that。

 And then we print a single line。 So this is gonna to print a line for the process with the process Id It's current state and the name。

 Okay， the name field is a fixed length field。 and we can store a short name。 in that field。

 And so here we we print the name。 Okay， so that's pretty straightforward。 That's proc dump。Now。

 we're going to get into。Lily Alec。functionction， so。Let's look at what this function does。 Okay。

 first of all， it's past nothing。 when we need a procedure， when we need a prostruct。To。

Create a new process。 We call Alec proc。 and it's going to find one and initialize it and return a pointer to it。

 Okay， look in the process table for an unused proc。 If found。

 initialize it and return with a lock held。 Okay， And if there's a problem， it returns No。

 So here's what it's going to do。 This is an outline of what it does what the code does。

 It first searches for an unused proc structure。Then it calls Kalc to allocate a trap frame page。

For that process。Then it creates a new page table， adding mappings for the trampoline page。

 which of course is shared by all virtual ladderer spaces and a mapping for the trap frame page that just got allocated。

And then it sets up the context， or maybe I should say it initializes the context in preparation for the first time slice of this process。

 recall that in the proC structure。 We have this context area and this is the register save area。

 so we do some initialization there。And。The adder space that got created， you know。

 we created a page table here， but we didn't put anything in it。 So there's no code or data yet。

Alc proc， this ac proc function is not responsible for that， but it'll be added later。

 And if there are any problems， this function has to undo everything。

 returnturn all allocated pages back to the free pool by calling K free。 And then it returns no。Okay。

 so let's take a look at the code here。Here we are looking for a proc structure that has a status or state of unused。

 So we're just。Looping in this for loop through the entire array of all 64 elements。 And for each。

 we acquire the lock。 If it's unused， then we have found something。

 Another go to here to this label down here。 But if it's in use。

 then we release the lock and keep looking。 Okay， And if we can't find anything， we return our null。

Okay， let's say we find something。 Well， that's good。 So here we fill in the process。 I D。

 Each process will get a new identifier。 You're telling what happens when this variable rolls over。

 we don't worry about that sort of thing in X V 6， because it's not gonna to ever happen in our lifetime。

 And we set the state to used。 So that's so what of the states that we can have in the。

I just remember that the used state is not listed here。Okay， well， in any case。

 it goes into this state of being used。And will。The color of this will be responsible for making it running or sorry。

 runnable at some future time。Okay， so then we allocate the trap frame page。

 So here we're calling K Allc。 And if anything goes wrong。Well。

 we're going to release the lock and return null。 And we're also going to call this free proc function。

 I'm going to cover that one next， but basically it just it's called anytime there's a problem。

 We see it being called down here as well。 It's basically going to make the proc structure unused again and zero out all the fields so that it could be recycled。

Okay， so now we create the page table， so here we call proc page table。

 and I'll cover that in a moment here， but that's going to create the page table。

 and add a couple mappings but if that's all okay。 then we keep going。

 but otherwise we call this free proc to undo what we've done。

 release the lock and return null just as we did up here。Alec Proc is called in two places。

 One is user it to create the first process， the knit process。

 and the other place is the fork function， which is used for the fork system call and。In any case。

 what's going to happen after the process is created is it's going to be scheduled to be run。

 So we need to kind of set things up for that。 So remember that in the proc。Structure。

 we have the save area for the registers。 This would be the registers that the kernel。

 the process is going to use when it starts running。 And， of course。

 it will start running when it gets scheduled in kernel mode。

 So you've got the registers that will be used or restored， I should say。

 and the R and S P registers， the return address and the stack pointer。Okay。

 so this is a new process。 it's not getting rescheduled， it's getting scheduled for the first time。

 so we need to have a return address and a stack pointer for its initial scheduling so we set the context。

 Well， first of all we clear out all the registers。

 So MIMSet just writes a zero to all of the registers in the register save area。

 and then we initialize the RA register to point to this fork RE function。

I'll look at that in just one second， and we initialize the S P register to point to the stack page。

 So remember that。Each process has a page in virtual memory， and。For example。

 process 2 has this page at this address in virtual memory， and stacks grow downward。

 So we want to initialize the stack pointer to point to the top of this so that it can begin to grow downward from this zone。

 So we initialize the stack pointer。 So when this process is scheduled。

 That is when it has its first time slice， it will begin executing at the address given here for Gr with a stack。

What we're going to do after we call Alec Proc is basically fill in the code and the data。

 and we also need to release the lock。 remember that we have acquired a lock up here。

 we need to release the lock。 And then this thread can go on and do whatever it wants to do。

 But at some point， the scheduler will select this process。 and it will acquire the lock。

 and it will for that process， and it will schedule it。

 and then it will load the registers from the context， and that will include the return address。

 And so this process will begin every process， including the in process will begin by executing the fork REt function。

 So here's the forkret function。And we can see what it does。It。Well， remember。

 when we first get scheduled， we are holding the process lock。 So we have to release that lock。

 and we have nothing more to do except the return from the trap。 Well， we haven't really had a trap。

 but we begin by returning from the trap。 In the case of a fork， we have had the trap。

 In the case of the initial process， we are going to fake the trap。 but in any case。

 we do a trap return here。 this other the other stuff in fork grt。

You can see that you've got a global variable first or a static variable。

 I should say that's initialized or true， so this will be done one time。

 the first time that any process is scheduled， it will execute this code。

 then set first to false and it says the file system initialization must be run in the context of a regular process。

Because it's called sleep。And thus it cannot be run from the main function。

 so that's what's going on here when we are just about to schedule the initial process。

 we will see that first is one and we will invoke this file system。

 a knit function and take care of that before we do the user trap rat to the first bite of the initial process。

Okay， next， let's take a look at。诶。Free pro。So if anything goes wrong and we'll call free proc。

 And when we're done with a process， we'll also call free pro。 So what's it gonna do， Well。

 it's past a pointer to the procedure that， you know， we're。Abandoning。

And it looks at the trap frame pointer。It looks at the trap frame pointer oops， here we go。

 and it asks if it's not null， then it points to something， so return that to the free pool so。

That happens here。And says the trap frame to no， and then it looks at the page table pointer。 Okay。

 it looks at this pointer here to the page table， and it needs to basically destroy that page table。

 And so we'll discuss page table and proc page table。And Proc free page table in a second here。

 But basically it's going call Proc free page table to undo that page table and return everything to the free pool。

And then it zeros out some of the remaining fields。You know， it this is not strictly necessary。

 but it does all of this。 setss a null in the name field and so on。 But in most important。

 it sets the state to unused。 So at this point， this。Process。Is the pro structure is unused。Okay。

 so in。呃，alc。Proc， so returning to the function Alc proc， we found a proc structure。

And set up the trap frame。And then we call proc page table。 Okay， to create an empty user page table。

 So now let's look at proc page table。So。Create a huge， a user page table for a given process。

 So it's past a pointer to the pro structure。And it's going to set up the page table and return a pointer to that page table and as we saw in Alec Prac。

 it'll just store that in the page table field。Okay， so。What does it do， Well。

 we've covered UM create to create an empty page table。 Okay。

 so that just sort of creates the user page table。 And if there's any problem， we return 0。 Next。

 we map。We create a mapping for the trampoline page。 Okay， so the trampoline address。

 This is the address of the highest page in the virtual outer space。 It's one page in length。

 and we map it to the trampoline page。 This is the page in the colonel's code area。

 marking it read and executable。 And so we've discussed map pages。

 So that adds a mapping to the page table for the trampoline page。

And if there is a problem with that， then we free the page table that we've created and just return。

 Okay， next， we map the trap frame to the page， the second highest page and。诶。

We call map pages again the trap frame address is the second highest page again。

 it's one page in length。 and where is that page Well。

 we've allocated page by calling Kalc earlier and set trap frame to point to the physical page in physical memory and so that's what we're using right here。

 the trap frame and we're making it readable and writeriable and if there is any problem well we unmpped the trampoline page and then again free the page table under trend0。

ok。Now， what about the converse， the free。Proc free page table， well。We've discussed。

These functions in the videos on the virtual memory functions。

 so we basically remove the mapping for the trampoline page without freeing the data page itself。

And we remove the mapping for the trap frame page without freeing the trap frame page itself。

 And then we call U VM free to completely obliterate the page table to return all the data pages to the free pool and to return all the index pages to the page to the free pool。

 So where we call。Where we call this。Is in。Free proc。 So here's our function， free pro and。

You see we're already freeing the trap frame page here。

 so that's why we don't ask for it to be freed at this point right here。

Because we've already freed it and we call a free page table here and set page table to null。

 so this is where we use PRC free page table。Okay， now let's talk about the。



![](img/440051606a3a7334cc1247c1d0cc40db_2.png)

This function here， which is user in。User init is called to set up the first user process。

 So let's walk through the code。 It's not too long。

 So the first thing it does is it calls Alc proc to find a proc structure and sort of set it up。

 So now we've got a pointer to the proC structure。 And this is called the init proc。

 So we're going to save a pointer to that。Next， we're going to allocate a single page and copy in the code for the initial。

诶。Process， so here we are calling UM Anit， which weve discussed earlier。

 but it's past a pointer to the page table。 Okay， so Al Proc would have set up this page table。

 but not filled in any code or data。And UVM and it has passed a pointer to some bytes and the number of bytes the count。

 And what is that， Well， this is a ni code right here。 Okay， this is this array。

 and it contains the bytes。 And I think they counted out 52 of these things you can check me on that。

 Let's8 times 6，484 9，542，52 bytes。 So here we are going to oops going to copy in those 52 bytes into page 0 of the。

Virtual address space that is being pointed to by this page table。

We're also going to set up the size field。 That's one of the fields in the proc structure right here this tells how big the。

The virtual addresser space is from zero to the break point and here we just have a single page so that's not very much okay。

 prepare for the very first return from the kernel to the user here's the trap frame。

The EPC was where we saved。The program counter。When a trap occurs in a running user process。

 we save the program counter and we save it here and we save all the registers as well。 okay。

 we save all the general purpose registers， including the stock pointer okay and so when we get ready to return to the user's process。

 we return to executing at this program counter here， after wereoring all the registers。

So what we're doing here。Is we are setting the program counter to 0。

 So for the for this process and only for this process， we'll start executing it。

 Lo 0 for all other processes， when they first begin executing。Well。

 they were created as a result of a fork construction。

 and they will begin executing directly after the the fork call to the fork system call。

 And so we don't need to do that for the other processes。 But for the first process。

 the in it process， we said it's program counter to 0。 And we also set it's stack pointer to。

The page size。 Okay， we're gonna remember that the initial process will have exactly one page。

 which will contain both the code and the stack。 So by setting S to the page size。

 we are setting it to the top of that initial page。 And so hopefully。

 the initial process won't grow it stack very much。 In fact， it won't grow it at all。

 But we do set it up anyway。 And then finally， we copy into the name field。Of the pro structure。

 so here's the pro structure again， and we have this name field down here。

It's a fixed number of bytes， a small number of bytes。We are copying in these characters。

Safe string copy is something that will copy a string from one place to another place。

 and it won't overrun the target area。 So we're passing in the maximum number of characters to copy with this size of parameter here。

 So that way we don't over accidentally overrun this array here。

And we've got a couple of other fields， the current working directory down here。

Of the pro structure is initialized to point to this， this slash。 So that's what that is。

 And then finally， we set the state。Wops， set the state to runable and release the lock。

 Remember Ra proc returns with the lock set。 And so now we've allocated a function。 sorry。

 allocated a proc structure and。Change its initialized its page table and everything。

 got it all ready to go。 We set it state to runable。 and we're done with it。

 We can ignore it from here on out。 this thread that's running this can ignore it。

 And so we just release the lock。 And the scheduler will then find this process when it's looking for something to run。

 And it will see that it's runable。 and it will just schedule it。

 and the initial code will then start executing。 And， of course， what it does is not much。

 just looking up to this code here。 Here's the code。 Of course。

 you can't read this because it's the machine code for the risk5 processor。 And in any case。

 what it does is calls。performforms a system call for the exact system call passing it a string of slash in。

 and that's all it does。 and we are basically getting this code。 This is the UniX commandoc。

 Basically we'reocto dumping it and putting it into a file and then copying it into here。

So there you have it。 And Ill cover the rest of this file， the proc dot C file in a future video。

