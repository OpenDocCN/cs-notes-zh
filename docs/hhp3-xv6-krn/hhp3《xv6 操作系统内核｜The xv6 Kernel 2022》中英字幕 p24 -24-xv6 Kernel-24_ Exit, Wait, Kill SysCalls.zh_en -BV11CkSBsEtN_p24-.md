# hhp3《xv6 操作系统内核｜The xv6 Kernel 2022》中英字幕 p24 -24-xv6 Kernel-24_ Exit, Wait, Kill SysCalls.zh_en -BV11CkSBsEtN_p24-

![](img/2533fe612f7ae6b7164b9fd4e47dfe9f_0.png)

This video is part of a series on the X V6 operating system kernel。😊，In this video。

 I will talk about the exit， weight and kill system calls。

I will also describe the reparent function and review。

 sleep and wake up as they relate to these system calls。

Let's begin by reviewing the exit system call。As I am sure you remember， there is no return。

 Exit is used to terminate a process。And we provide the exit status as a value to the exit。

 And that is returned to some other process。On Uniix and Linux。

 the exit status is an a bit positive number。And on X36， it's a 32 bit integer。

 but that's not really relevant。On Unix and Linux， the upper bits are used to communicate additional information to the other process。

 such as what signals cause the process to terminate and so on。But in X 6。

 there are no signals so we can just use 32 bits。But in both Uni Linux and X V6。

0 is used to indicate that the process terminated with success。

 whatever that might mean for the process， and any other positive value is used to indicate that there was an error in the process。

So what happens with exit。 Well， if there's a parent waiting for a child to terminate。

 then that parent is first awakened， and then the exit status is somehow copied from here to the parent code。

 And the parent then will be responsible for cleaning up the process。After a process terminates。

 it stops executing instructions， we need to free up its data structures， and in particular。

 we need to return its proc struct to an unused state。

 but we can't do that in the child process itself because it's no longer executing instructions。

 So it's the responsibility of the parent to perform that cleanup operation。

But if there is no parent waiting， then the terminating process must freeze and wait。

So at that point， it will become what we say is a zombie。 In other words， it stopped living。

 It stopped executing instructions， but it's not yet fully dead。

 Its data structures are still persisting because we need some place to store the exit status。

At some point in the future， its parent will finally issue a call to the weight system call。

 and at that point， the operation can be completed。Now。

 there could be a problem if a process exits without waiting for any of its children。

And what happens then， Well， all of the children of an term of a terminated process are moved。 Okay。

 we say they are re parented and they're moved to the init process。

 So they're no longer children of the process that's terminating。 but instead。

 they become children of this init process。Well what does an it do， Well。

 it does some initialization， And then it goes into an infinite loop waiting for children to exit。

 And so whenever one of these， I guess we can call them adopted children issues an exit system call。

 and it will then collect that exit status， and that will allow the zombies to finish dying and it will allow some process to clean up after a process has died。

Now let's look at the weight system call。Weight， which is available both in XV6 and all Uni and Linux systems。

Is past the address of some location， and it returns the process I D of some child that has exited。

Okay， if there are no children of the parent， then it returns -1， but assuming there are children。

 then it will wait for one to terminate if waiting is required。

 and it will grab the exit status from that child and store it。

 So the argument here as a pointer to some place to store that exit status。

Uix and Linux systems have an additional system call that's not available in X V6 called weight PID that gives you more control。

 For example， you can wait for a specific process to terminate and also you can avoid sleeping。

 so there's a parameter that allows you to return immediately if there are no zombie children waiting。

Okay， so how does weight work。 What does it do， Well， first。

 it looks for a child which has already exited。 In other words， it looks for a zombie child。

 And if it finds one， it grabs the exit status from that child。

 And then it cleans up after that child。And in particular， it gets rid of the proc structure。

 calls free proc， which changes it back to an unused proc， so it can be recycled， and then of course。

 it returns the process I of the terminated child。But if there are no zombie children， Okay。

 then the weight system call will need to sleep。 So it calls the sleep function。

 And when some child finally terminates within the exit system calls for for that child。

 the wake up function will be invoked。 and this will wake the parent back up。

 and the parent will then loop back up and look for the zombie child。

If the parent is awoken for some other reason， then there won't be a zombie child and it would just go back to sleep。

Remember that the sleep in the wake up functions communicate with this channel。

 which is an uninterpreted value that the sleep in the wake up don't really look at。

But it's used to coordinate。 So which processes should wake up call awaken。 Well。

 that's determined by whichever channel is passed to the wake up call。 And for this application。

 we use the address or the parent's proc structure as the code or the number， if you will。

 that is passed to the sleep。 So this wake up will only wake up processes， the parent process。

 it won't wake up any other processes。Okay， next let's see how this looks in code。

Whenever the exit system call is invoked， the colonel will go into this function cis exit。

Which will just call exit to do the work。This function exit will never return。

 so we won't get to this point。There's a single argument。

 so we invoke arg and to retrieve a register a0 from the users' registers and place that in a local variable n。

 That value was then passed to the exit function。So here's the exit function。

 and all of these functions， exit， kill， weight， repairpar are in the file proc dot C。

So exitod is past the status value。 And what does it do。

Remember that the global variable in it proc points to the proc structure for the initial process。

 and here we're just making sure that that initial process is not trying to exit。

I haven't talked about the file system yet， but you can see here that we're closing the open files for this process。

We go through the open file array okay and for each one that's open。

 we are closing it and clearing it out。 We're also closing out the current working directory with this code here。

Now let's get to the good stuff。In the rest of this function。

 we can notice that there are no if statements or loops， so it goes straight through。

 And among other things， we can see that the state of the process is turned into a zombie state。

So all terminating processes will become a zombie， and the parent will ultimately clean up and take care of returning the pro structure to the unused status so it can be recycled。

We also save the status。 That's the argument right here in a field in the pro structure called X exit state or X state。

And whenever we access these fields， we need to be holding the lock on the proC structure。

 so we've acquired it before that point。Before this， we see that we're invoking re parent。

 So if this process has any children， they have to be moved。 They have to be orphaned， if you will。

 and adopted by the initial process。 So that happens in the re parent function。

And then we might have a parent that is waiting for us。

 Maybe there's a parent sleeping and maybe not。 But if there is one sleeping， we need to wake it up。

 Okay， so here we are calling wake up。 And as the channel。

 we're passing a pointer to our parent propc structure。So before we access the parent field。

 we need to be holding this lock called weight lock， and so we've acquired it here。

The reparent function will also be accessing the parent field。

 and the reparent function requires us to already be holding weight lock when it's called。

 So we acquire the weight lock here and then call reparent and wake up the parent process。

 The parent process might get awon at this point。 But the first thing it does we'll see is acquire the weight lock or try to acquire the weight lock。

 So it won't really make any progress until after we release the weight lock。

 So we don't release it until after we've become a zombie so that the parent process when it does wake up。

 We'll find us being a zombie。 Find this process as having a state of zombie and the status will already have been set。

And so finally， we jump into SCd and Sd is the scheduler， and we set our status to zombie first。

 and the scheduler will never schedule anything unless it's runable。

 So this process will never be scheduled again。 So we'll never execute this last instruction here。

In SCd， we are required to be holding the lock on the process and no other locks。

 So that acquire is done right here and satisfies the requirement for SCd。Okay， next。

 let's take a look at the reparent function。And。We see that the color must hold weight lock。

And all it's going to do is past a pointer to the process that is exiting。Okay。

 that we can call that the parent process。 and it runs through the proc array looking for children。

 So basically it for every potential child， it looks at its parent pointer and asks whether that points to pe。

 And if so， we've got a child。 And so we modify its parent pointer to point to the proc structure for the initial process。

 So that's where the reparenting occurs， And then since we've added a new child to the knit proc to the initial process。

 we need to wake that process up in case it's sleeping because it will be in a tight loop waiting on children to terminate so that it can get rid of them。

 So we issue the wake up call for the knit process。 in case it's sleeping。

 And that's all re parentent does。Next， let's take a look at the weight system call。

 The colonel invokes cis weight， which will then call Wait to do the work。

The weight system call has a single argument。 So here we invoke a adder to fetch the value of the user register a 0。

 and we place it in a local variable previously in cis exit， which is right here， we called Arg int。

 The only difference is that Arg int retrieves 32 B。 and Arg adder retrieves 64 B value。

And that is the virtual address into which we will store the exit status。

Wight will return the process ID of the child that is terminated。

 and then we return that to the user mode code。

![](img/2533fe612f7ae6b7164b9fd4e47dfe9f_2.png)

So here's the code for weight and let's start by looking at the general structure。

 we see that it's past the virtual address into which we store the exit code。

We've got an infinite loop here。 Okay， an infinite loop。

 and it initializes that local variable have kids to zero。

 and then it looks through all of the children for one that's a zombie， Okay。

 and if it finds a zombie， it does this stuff。 And so here's where it looks through all the children。

 and if it finds no children after it finds no zombie children， then it asks。

 have we found any children at all。 Okay， if ever we find a child， we said have kids to one here。

 But if we get down here and we find that we have no children， then we immediately return -1。

This function at the beginning， acquires。Weight lock because it's going to be looking at the parent pointers。

 And so we release weight lock before returning that -1。Also。

 if ever any other nasty processes have set our killed flag。

 then this process needs to terminate itself。And so if killed has been set， again。

 we release the lock and we return -1。The kernel code that invoked this was originally called from userV。

 and as we return through cis weight to Cis call to the userV function before we return to user mode code will check the killed flag。

 and if it has been set。 we will exit then。 and so we will never actually return a minus1 to the process that invoked the weight system call。

 the weight system called simply will not return at all。Okay， so if we have not found a zombie。

 but we do have children， then we sleep。 So here we are sleeping on the channel。 And for the channel。

 we're using the。Address of the pro structure of this very process。 Okay。

 that was obtained right up here at the very beginning。 We grab our own。

An address of our own proc structure。 And then we sleep using that as the channel。 The child。

 any child that exits will then do a wake up using the address of its parent。

 That is that same address and wake us back up and then we'll repeat the infinite loop， the for loop。

 the outer loop。 and again， look for a zombie child。诶。We're passing as the second argument。

 the weight lock。 And remember that with sleep and wake up。

 they work in such a way that the lock that is passed should be held and it will be released。

 but it will be released。 and the process will be put to sleep。 as an atomic operation。

 So we won't miss any signals and the weight lock will be held until we are certainly all way asleep。

Okay， now let's assume that a child has exited。 And so this process is woken up from the sleep。

 The outer loop will be repeated。 and what happens。Well， we initialize half kids to 0 again。

 and we are going to search through the proc array for any children。

 So we go through the proc array and for each one。Call it N P。

 We check to see whether it is a child of ours。 In other words。

 does its parent pointer  point to this process。 And if so we found a child。

 So we'll set have kids to one and then check to see whether it is a zombie。

Anytime we access the state field， of course， we need to acquire the lock。

 So we acquire the lock on NP and then look at its state field。And if we found a zombie， well。

 this is the one we are going to take care of。 So we grab its process Id。

 and that's what we'll be returning down here。 And then we grab its exit status here。

 So here we're grabbing its exit status。If adder is no， we can。Skip the copy。 So we check for that。

 If we actually have been provided with a virtual address in which to store the exit state。

 then we will do the copy out。And so here we're using the function copy out。

 which copies from the kernelel's memory into the virtual address of some process。

 that is the parents process is the one we're copying into at the virtual address in this variable adder。

And so if there's any problem with that， we will release the two locks we're holding the lock on the child and the weight lock and return -1。

 but assuming the copy works okay。 Then we go ahead and clean up after the child process。

 The zombie child is now ready to be laid to rest。 we can say， so we take care of the final action。

 which is to free up the data structure that's associated with a child。 we call free proc to do that。

And then we release the lock on the child。 At this point。

 the child proc structure is now unused and can be recycled， And then we release the weight lock。

 which we're still holding and return。Next， let's take a look at the kill system call。 First。

 we get into the sis kill function， which we'll call kill to do the work。Kil takes a single argument。

 which is the process ID of the target process that we want to terminate。

We retrieve the value of user register a 0 by calling Arg and。

Place that in a local variable and pass that to kill。

Kll will return zero if everything's okay and minus-1。

 if we've been past a process I D that doesn't exist。Okay， so here is the code for kill。

 It's pretty straightforward where we've got a single loop here that will search for a matching process I D。

 So let's look at that in a little bit more detail。Here。

 we're going through the prock array 1 by one。 and for each proc。P， for each process， P。

 we are looking at its P I D field to see it is the one we are searching for。And if so。

 we are going to set its killed field to true。We are also going to look at stake field。Now。

 these three fields， P ID killed at state are among the fields in the proc structure。

 which are protected by the lock。 So if we are going to read them or modify them。

 then we need to first acquire the lock。 So here we are acquiring the lock on this proc structure。

 and then we are releasing the lock。 If we do the out statement， we release it here。

 and everything' is okay， we return0。 if we find and it doesn't match。 It's not the right process。

 then we release the lock and repeat the loop。 okay and if we go all the way through the loop without finding a matching process。

 we return -1。Okay， we set the killed flag here to true。 and then we check its state。

 If this process happens to be sleeping。 okay， it's not running or runnable。

 then it is waiting on something and we don't know what it's waiting on， but we don't really care。

 So we need to just wake that process。 So we can wake it by changing its state to runable。

 And now if it's sleeping， that means it was in the kernel thread for that process。

 And so whatever its gonna whatever system call it was in the middle of doing or wire it was sleeping。

 it's going to wake back up and finish that system call。 Okay， it might be you know。

 might end up returning an error or something because it just got woken up arbitrarily。

 but with any process with any system call， before we return to executing a user mode。

 we always check the killed flag。 So whatever this process was doing whatever system。

Call it was in the middle of executing。Yeah， it finished， but and maybe it didn't do the right thing。

 But nonetheless， before it returns， it will not return。

 It will see that its killed flag has been set and it will then call an exit。

 So that process will never return to user mode。 So here we wake it from sleeping。 Otherwise。

 it might just persist and stay sleeping forever。 if the condition never arises。

 We want to kill it immediately。 So that's what we do here。Okay， that's it for these system calls。

 I will see you in the next video。