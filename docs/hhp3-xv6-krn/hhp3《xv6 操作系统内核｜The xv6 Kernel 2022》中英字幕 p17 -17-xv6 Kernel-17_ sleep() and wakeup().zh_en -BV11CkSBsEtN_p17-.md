# hhp3《xv6 操作系统内核｜The xv6 Kernel 2022》中英字幕 p17 -17-xv6 Kernel-17_ sleep() and wakeup().zh_en -BV11CkSBsEtN_p17-

![](img/517c35e4232493292bb1b5f3bd171b7f_0.png)

This video is part of the series on the XV6 operating System Colel。In this video。

 I'm going to talk about the sleep and wake up functions。I will use as an example。

 the system called sleep， which is dealt with in this function here。

Any process can call sleep to put itself to sleep， and that will end the current times slice and change its status from running or runnable to a status of sleeping。

 And the process will then remain sleeping until some other process calls wake up。

So we have this problem though， of exactly which processes to wake up when some process calls wake up。

So when we go to sleep， we need to provide some kind of information about when we want to be woken up。

And then wake up should not wake up every single sleeping process。

 but it should only wake up a certain subset of those processes。 And the question is。

 how do we identify which processes to wake up。And with XV6， we have something called a channel。

The channel is just a simple number。 It could be anything， really。

 It's uninterpreted by the sleep and the wake up functions。And for example。

 it might be the number 37。 so a process could sleep on the number 37。

 And then when wake up is called， it's past a channel that is some number。If it's waking up on 37。

 it will wake up that process， But if wake up is called with some other number， like 54。

 it will only wake up the processes that are sleeping on 54。 So that's how the channel works。

There are other approaches used in different systems。 Sometimes you provide a list of threads here。

 so you sleep on a particular set or list of threads。

 and then wake up is applied to a particular list of sleeping threads and it will wake up everything on that list。

Some systems also have condition variables， and a condition variable is really fundamentally nothing more than a list of sleeping threads。

嗯。But this is how X 6 works。The channel is a field， and it's just kept in the proc structure。

 So every process has a field that will store the number that it's sleeping on if its status is sleeping。

 And then the way wake up works is it goes through all the processes。 In other words。

 it iterates through the entire proc array， and it will wake up any process that is sleeping with the matching channel number。

So next let's show how。These functions are used， so I'm going to look at a typical usage。So in code。

 we would like to check conditions and only proceed if the condition is true。 Otherwise。

 we want to wait for that condition to become true。 And so here's the typical pattern we see。

In this while loop， we are checking to see whether the condition is true。 and if it's not yet true。

 then we call sleep， and we're going to wait until the condition is updated。

 It may be that some process will， some other process will update variables and those variables are somehow involved with that condition。

 The other process may not really know what condition we're waiting on。

 but we just basically wake up。 the other process will wake up any process that's waiting on those variables that are involved in that condition。

 So it may wake up。 a little too many processes。 It may wake up several processes that are waiting for some changes in the shared data。

 It may be that the condition is true or not true。 It may be that one of them will grab the condition and find that it's true while others will find that it's false and go back to sleep。

 So we have to recheck the condition upon waking up。However。

 there's a problem with this particular pattern here。And that is， where're。

Concerned about what would happen if the condition might become true sometime between being checked and the sleep being executed。

We've got other processes running both on this core and other course。

 and it could be that our time life ends right here， and other processes run。

 and they may make the condition true。 and furthermore， they may issue wake up and it。

We would miss it because we haven't yet executed our sleep。

 So we don't want to miss any wake ups after checking this condition。

It could really be bad if there are no further wake ups。

 in which case we go to sleep and never wake up。So here's an example from the code that we will look at in a second。

The sleep system call is handled in in this function。 And here's an outline of what the code does。

 First of all， it grabs the argument to the system call， which is how long we want to sleep。

 And that's measured in a unit called ticks。 Every time the timer interrupt goes off。

 it's said to be at tick。And there's some global variable that is shared amongst all cores。

 and it contains the current。Tick count。 That's the the time。 that represents the current time。

 It's updated by core 0 whenever core 0 gets a timer interrupt。 So it's a global shared data。

And we're grabbing the time that we start the weight。 And then we， here's our condition。

 We're checking to see whether N ticks have gone by。 And if not。

 then we go to sleep and we sleep until this shared variable is incremented again。

 We also have a little check in here to see whether the process has been killed。 And if so。

 we have bored our waiting。 And that's beside the point。So。Ticks。Is a global shared variable。

 and it is protected， or we could say， guarded by a lock。If you want to look at or modify ticks。

 you need to first acquire ticks lock。And so we have these requirements that we've got to hold ticks lock while we're looking at ticks。

 So， for example， right here， when we check the condition。

And we don't certainly don't want to miss a wake up。

 But we've also got this other condition that we cannot hold locks while sleeping。

 Remember that spin locks must be released quickly。 and in particular。

 we cannot hold a spin lock while we're sleeping。 So we've got a bit of a problem here。

 And the solution is this。Our code is going to look like this。 We're going to。Acquire the lock。

 In this case， it's the ticks lock。 Whatever lock is required in order to check the condition must be acquired before we look at the condition。

 So we acquire the lock。And then we check the condition again。

 we go to sleep and then wake up and check it again。

 But the difference is that we are now passing a pointer to the lock that is being held。

To the sleep function。And what's the sleep function going to do， Well。

 it must release that lock before we go to sleep， but it's going to do that in an atomic way。

 So the lock will be released and we will go to sleep in such a way that we can be guaranteed。

That we won't miss any wakeups。 And then at some later point。

 the some other process will change our status from sleeping back to runnable and the scheduler will select us and will be changed to running。

 And at that point， this process will wake up。Still in the sleep function。

 and the sleep function will then reacquire this lock before returning。

 So once we loop back and we are holding the lock when we check the condition again。

 And we keep loop looping until finally， the condition is found to be true， in which case。

 we exit the loop。 And then we do something with our shared data。 And finally。

 we must release the lock。 So the acquire and the release are paired here。 And in a sense。

 they're also paired here。Okay， so now let's look at the function。Ss。

 sleep and see what that actually looks like in code。And here you see。

ACa to this function that will obtain our first argument and store it in this variable in。

And then were acquiring ticks lock。Here we're accessing the shared variable ticks and grabbing the starting time。

 which is a local variable。Here's the condition。That's being checked。

 And then here we see a call sleep。 And we're providing a pointer to the ticks lock。And finally。

 after the loop exits， we release the ticks lock and return。

We also see a check to see whether the killed flag has been set。 and if so。

 we immediately release the lock and return。 and the code that calls us will then notice that kill killed has been set and terminate the process。

 but that happens elsewhere。So what about the channel here？

We are using the address of the shared variable here as our channel。 So when we sleep。

 we sleep and we pass a the address of the ticks global variable。 And that's okay。's， it is a number。

Before we look at how sleep is implemented， let's review yield because they're really quite similar。

嗯。Both will stop the process from running and put it back on in a dormant state。

And so yield will change the state to runable。 Okay， But first， it acquires a lock on the process。

 So when we call scanned here， we have to be holding a lock on this process。

 S will release that lock。 And then when the process is scheduled again。 It will reacquire the lock。

 And then we come back here and release the lock and and keep going。 But that's what yield does。

 And sleep is， is really quite similar。 So here's the code for sleep。So。

We see the acquire of the lock。This acquires the processes lock。 And here we change its state。

 We don't change it to runable， we change it to sleeping。

 So when the scheduler encounters this process from now on。

 it will see that it is not runnable and it will ignore it。

 So it will remain sleeping until some other process changes it back to runnable。

 So we change our state to sleeping， we call skid here， and then when ski returns。

 we release the lock。And return。However， we see a couple other things going on。

We see that we are passed a pointer to some spin lock， and here we are releasing that spin lock。

 so we acquire the lock to the process and the order here is critical。

 we acquire the lock to the process first and then we release the spin lock。

And so we're not holding the spinlock while we are sleeping。 But then after we come back。

We reacquire the spin lock and it doesn't really matter。 this order here is not critical。

 but so we release the lock first。 when in doubt we prefer to release locks as soon as possible before we do acquiring。

 So let's see the code。 we also have the channel that's passed。

 And here it's just a pointer to some address。 and we see that we're storing the channel in the field of the proC structure。

 And then after we are woken back up。 we clear that field。Just as a matter of tidying up。



![](img/517c35e4232493292bb1b5f3bd171b7f_2.png)

Next， let's take a look at the wake up function。The Wickup function is passed a channel。

 and it goes through all the processes and wakes up any and all that are sleeping on that channel。

It has a loop， and it goes through the proc array1 by one。 And for each process， it asks。

 is the state of that process sleeping and is the channel field of that process equal to the channel that we are using as an argument。

And if so， it changes the state to runnable so that the next time the scheduler encounters that process。

 it will be given a time slice。Now， the field state and channel and some others are protected by the lock on the process。

 which means we need to acquire the lock before we access those fields。

 and we see that acquire occurring here and a corresponding release right here。

We also see this test right here， which is asking， is the current process that we're looking at equal to the current process that's running this code itself？

The comment says that this function must be called without holding a lock on any process。

 and so if that's true， then this test is really superfluous。

We are looking at the state of the process and obviously， the current process。

 the one that is running， will have a state of running and not sleeping。

 So it would seem that this test is really unnecessary。

It may be that this is an artifact of the history of this code。

 or it may be that somewhere in the XV6 code that I'm not aware of。

 this function is actually called while holding a lock on the current process。 In any case。

 this test is here and it certainly doesn't hurt anything other than maybe taking a little bit of extra time。

Now， I want to go back to the pseudocode that we looked at for showing how sleep is used。

Remember that we are typically using sleep in a loop where we're looking for some condition and this condition is checked by looking at some shared variables and we acquire a lock before looking at the shared variables and we need to release the lock before we go to sleep before we actually begin the sleeping state because these are spin locks and we cannot allow them to be held while we are sleeping。

 we need to release them quickly without any delays like a sleeping process would have。

So we need to release the lock before we actually go to sleep。

 and that has to happen in the sleep function， and it does happen in the sleep function。

And we said that this has to be atomic， so I wanted to just comment on why it is atomic。

In other words， if the wake up comes along that matches our channel here。

 it will either execute before this group of instructions or after this group of of two instructions。

 it won't execute in the middle。 So we will either still be holding the lock， in which case。

 we can be certain that our condition is still false。 And so we don't need to be awakewoken。

 or it happens after here， in which case， we will be properly awakened and then reacquire the lock and go to check again。

 the condition。 So the way that works is， is that the。Within the sleep function。

Recall that we are acquiring a lock on the process before we're releasing the spin lock。 Okay。

 and likewise， notice that in the wake up function。

 we are acquiring a lock on the process before we consider possibly waking it up。

So it's that acquire that the spin lock， I'm sorry this lock on the process can only be held by one thread at a time。

 so either the wakeup gets there first and acquires a lock on the process。

 in which case the sleep code is still somewhere above this acquire and still holding the spin lock LK。

Or。The acquire in the sleep function gets there first and acquires the lock。

 in which case it releases the spin lock L K， but also sets the channel and the state fields before actually going to sleep。

 And so later。Well， this， this。Lock on the process will be immediately released once we get into the scaredd function。

 And at that point， wakeake up can then acquire the lock for that process and can be sure that it will be found to be sleeping and the channel to have been set。

 So then it will wake it up。 So that's how we guarantee the atity。

 atity of these two operations here。Okay， that's it for this video。 See you in the next video。

