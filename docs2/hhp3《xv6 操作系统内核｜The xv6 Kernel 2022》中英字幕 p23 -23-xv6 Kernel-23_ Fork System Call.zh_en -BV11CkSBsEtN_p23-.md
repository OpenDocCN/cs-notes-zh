# hhp3《xv6 操作系统内核｜The xv6 Kernel 2022》中英字幕 p23 -23-xv6 Kernel-23_ Fork System Call.zh_en -BV11CkSBsEtN_p23-

![](img/7313ad67b6e1648a3c0ad9214a8750dd_0.png)

This video is part of a series on the XV6 operating System kernel。In this video。

 I'll describe how the fork system call works。Whenever a process wants to create another process。

 it uses the fork system call， and this is the only way that processes are created with the exception of the creation of the initial process。

The process that does the creating is said to be the parent process， and it creates a child process。

The trial process is a clone of the parent process and almost exactly identical to the parent process。

When the parent makes the fork system call， the kernelel becomes active and then at some point。

 the fork system call returns。 and when it returns， both processes now exist。

 and so in both processes， there will be a return from the system call。

 One major difference is that the fork system call returns the child's process I D While the fork system call returns0 in the child process。

The code in the both processes， the parent and the child will typically take a look at the return value。

 and that code can then determine whether it is running in the child or the parent process and can then take actions differently。

 depending on whether it needs to behave as a child or a parent。If there is any difficulty。

 such as we run out of memory and we can't allocate the pages for the child。

 the Fork system call will return-1 in the parent。So what's involved in creating the child process？

 Well， we do several things， and then we return the process I D of the child。

The first thing we do is call the acproc function。This will search for an unused pro structure and grab it and begin the initialization process。

It starts by assigning a new process I D to that proc structure。

It also creates an empty address space and adds mappings for the trampoline and trap frame pages。

Then after Alec Prac returns， we need to copy the virtual address space。

 So every data page from the parent process is copied and added to the child's virtual address space。

The permissions on each data page in the child will be set to be exactly the same as the permissions on the corresponding page in the parent' virtual outer space。

And then we initialize and set few of the fields in the pro structure。

The size field is the number of bytes in the virtual address space。

 That is since the virtual address space starts at 0。

 That's just the same as the break address at the top of the heap。 So that's copied。Next。

 we copy the trap frame。When the system call was made in the parent process。

 all the registers of the user process were saved， as well as the program counter。

And those were saved in the trap frame。 And by copying the trap frame。

 it means that the child process when it's scheduled again and runs in user mode。

 will have exactly the same values in all of its registers。

 and it will begin executing at the same spot， namely directly after the E call instruction that did the fork system call。

 And then we modify register a 0 to set it to 0 so that the child process will see a return value of 0。

Each process has a name and we copy the name field so the child process will be given the same name as the parent process。

Each process has a number of open files。We copy all of the file descriptors for open files in the parent process。

 into the child process so that any file that was open in the parent process will then be open in the child process。

We also copy the current working directory so the child will be in the same working directory。

And we then set the parent pointer in the in the child's pro structure to point to the parent's proc structure。

 This is the other difference between the child process and the parent process。

They each have a different location in the parent child hierarchy of processes。And finally。

 we set the state to runable。 And at that point， we're done creating the trial process。

 It's runable and it will be scheduled when it's given a chance。 So at this point。

 the system call is able to just simply return the process I D of the child that has been created。

Let's a look at that in code。So。Here is the fork process in the fileproc dot C。

The system call initially invokes Ssfork。 Ssfork simply calls fork， and whatever fork returns。

 Ssfork will return。So we begin by getting a pointer to the parents proc structure。

 And then we call the ac proc function。If there are any problems。

 then we return minus1 and we're done， but otherwise we say a pointer NP P is new process， I guess。

 so we have a pointer to that process。Alec Prac will also acquire the lock on the newly created prock structure。

And it will initialize the virtual address space。 And in this step。

 we invoke UM copy to copy all of the data pages from the parent into the child's virtual address space。

 So these are pointers to the page tables。 And that's the size of the address space。

 which indicates the number of pages that need to be copied。 If there are any problems。

 Then we free this。Proc structure， this zeros out all the fields and returns everything to the free memory pool。

 And then we release the lock on that structure and return -1。But assuming everything's good。

 we keep going here， we make a copy of the size field。And here we copy the trap frame。

 So this is where we are copying all of the registers that were valid in user mode。

 as well as the program counter from the parent to the child so the child can resume executing at exactly the same place。

And here we modify a0 to clear it to0 so that the return value will be0。In this code here。

 we are running through the open files of the parent and for each file that is open。

 we make a duplicate of that and add it to the child here。

And here we are making a duplicate of the current working directory and copying that so the child will have the same current working directory。

Here we are copying the parent's name into the name field of the child。

And here we grab the process idea of the child， and we're going to be returning it right down here。

Then we see that we are updating the parent pointer of the child to point to the parent's pro structure。

 Whenever the parent pointer is accessed， either read or modified。

 we must be holding a lock called weight lock。 So we acquire that lock here and then release it here。

And finally， we set the state of this。Process to runable and release the lock that was acquired up in Alec Prac。

And then return at that point， the child process has been created and will get scheduled whenever the scheduler gets around to it。

We also see something else going on here。 We see。During this code right here。

 we first release the lock on the child and then reacquire it。

 and we also notice that we don't just return the PID field here。

 we copy it to a variable and then return that。This is because we need to acquire this field while we are holding a lock on the process。

 It's possible that。You know， the minute we release that lock this。Proc structure will get scheduled。

 It will run。 It will exit， and another fort call will grab this process。

 and a new P ID will be assigned。 High unlikely that all this sequence of events could occur。

 But in an operating system， we have to assume that anything that can occur will occur。

 And so if we just simply grab the Pid field from the proc structure after releasing the lock。

 We could， in fact， get the wrong number。 So that's why we grab the process Id while we're still holding the lock。

 But still， we haven't figured out why we are releasing this lock and then reacquiring it。

 So for that， I want to go back and remind you about deadlock。 So here's a simple deadlock situation。

 we have two processes and we have two locks。And I'm going to show that lock A is currently held by process one with a solid arrow。

And I'm going to show that Lock B is currently held by process， too， with a solid arrow。Now。

 let's assume that process one wants to acquire lock B。 That is， it has called the acquire function。

 and it's trying to obtain a lock on。The lock Bay， which is。Impossible， because it's held by process。

 too。So the acquire function will be spinning here。 Meanwhile， process 2 is one in lock A。

 So it calls a， and it is spinning tied up in the acquire function waiting on lock A。

 This is a deadlock。 Deadlock in general occurs。 whenever we have a cycle。

 in one of these graphs that involves processes and locks。 here， I'm showing a very simple cycle。

 but we can have more complex cycles。 But this gives the idea of what deadlock is。

 There's a cyclic weight situation。 Pro one can't proceed because it can't get lock B。

 process 2 can't proceed because it can't get lock A。 And so they're both frozen。 Now。

 in our situation。 We I haven't yet talked about the code and exit and wake up。

 But we do have this situation。The weight lock is concerned whenever we are basically looking at the parent child hierarchy and when a process exits。

 we need to notify its parent。 So the weight lock will be acquired in the exit function。

 and we also have a function wake up and wake up goes through all of the potential parent processes and goes through all processes。

 in fact， and grabs all of the locks on those processes。

 So we have this situation where at any at some point in this， these two functions。

 we might have a situation where the weight lock is held and we are trying to acquire the lock on a particular process。

Now， in fork， we are needing to grab the weight lock to modify the parent。The parent field。

 So we see that right here。 we are calling a choir to grab the weight lock。 Okay。

 now what if we were holding。A lock on some。Process， okay， then we would have the arrow going here。

 And that would be our deadlock situation。 And we can't allow that。

 So this is an explanation for why we must release the lock on the process before we attempt to acquire the lock called weight lock。

Next， let's take a look at what happens in the child process。 At some point。

 the scheduler will select the child process and will invoke switch。

Switch will load the registers from context。These are the registers that were。

Saaved previously in most cases， but in this case， they have been just initialized。

And then switch will do a return。 Well， register R A was loaded from context。

 and this return will effectively just jump to the instruction that's pointed to by R A。

When the fork system called created the child， it called Alcproc。 And among other things。

 that function initialized the context for this process。It zeroed out all the registers。

And its saved in RA the address of this function called forkret and it's saved in the S register。

 the stack pointer。 that is， in fact， the page that's pointed to by the K stack field and proc structure。

 And since stacks grow downward。 We save the pointer to the top of that page。

 So we have a fresh stack and a starting address in this function called forkcrret。

 which we'll look at it in just a second。 But before that， let's review what happens in a trap。

 So remember this picture， we're showing a trap and we save the registers in userva user trap figures out what's going on。

 let's say it's a timer interrupt and we call yield because I want to look at yield a little bit more。

 and yield does some stuff as we saw it called switch eventually。

 But ultimately yield returns and we come back and then user trap rept is invoked。

User REt is invoked。 and these restore the registers and set things back up and then return to the user mode with the Sret instruction。

 So let's look at this pathway in a different way。Let's assume we've got a timer interrupt。

 so we've got a trap that goes into userV and user Tra， saves the user mode registers。

And then calls the yield function。Well， what does yield do yield basically just calls？

Scared after acquiring a lock on the process。 Here， here is the code for yield to review it。

 So you see yield， it acquire the lock。 Well， in the case of yield， it changes the state to runable。

 in the case of a trial process， it's already runnable。 So keep that in mind。 But then it calls skid。

 And then after skid comes back， it releases the lock and then returns。 So we call skid here。

 And what is skid do。 Well， ski does some error checking。 here's the skid function。

 it does some error checking primarily。 and essentially just calls switch。 and then returns。

And so when switch returns， we are back in scared， scared returns。And then Yale becomes active。

 does its last statement， which is to unlock the process。 and then it returns to user trap Ret。

 which immediately called user trap Ret。And then that calls user rept。

 and then that that executes the S Ret instruction， which pushes back in user mode。

Switch does some things。 Basically， it unlocks the process and goes off and invokes a scheduler and may execute some other processes。

 But eventually it reacquires the lock。 And at that point， switch will load all the registers and。

Return to R。 Okay， and normally， that would be a return address in the SCd function。

 But in the case of a trial process， we've preloaded R with forkcr。 So when switch。Returns。

 it will be returning not to some address and scaredd， where it can finish this process here。

 but it will be essentially jumping to forkrat。What does Hkcrt do。Unlocks the lock on the process。

And called user trap rep。 So essentially it does this right here。

 It takes us into this point so we can complete the return process。诶。

User trap Ret will load the user registers。 Remember。

 we've saved a copy of the parents user registers。 We've also modified a0 to B 0。

 but this is how the user registers were saved and they will be loaded by user trap Re。

 and it will call user Re， and ultimately the Sre instruction will happen。

 and we will resume execution。After the call to fork or more precisely after the E call instruction。

 So just to complete this， let's take a look at forkres code。 Here is the for code for forkret。

 And you can see it does exactly what we said。 it is going to。Release the lock on the process， and。

Invoke user trap， RE。This code here is only executed the first time for the first time twice。

 and that would be for the init process when it gets going。

 and this just does a little initialization。 it'll set first to0。 And from then on。

 this code will never get executed。 so we can ignore that。

 It won't be involved for any child process。Okay， that's how the Fork system call works。

 I'll see you in the next video。