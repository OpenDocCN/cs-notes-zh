# hhp3《xv6 操作系统内核｜The xv6 Kernel 2022》中英字幕 p04 -04-xv6 Kernel-4_ Spinlocks.zh_en -BV11CkSBsEtN_p4-

![](img/8896ea6bdf0be38fd30126c199553dba_0.png)

This video is part of a series on the XV6 operating System kernel。In this video。

 I'm going to describe spinlocks and tell you how they're implemented in the X36 kernel。First。

 let's start off with remembering what spinlocks are。The idea is that。

The spinlock is represented with a single word and Ive called that word locked here。

And that word has one of two values。 It's either 0 or one。If it's zero， that means the lock is free。

 or sometimes we say it's unlocked or it has been released。And if the value is one。

 then the lock is said to be held or acquired or locked。

These are the common values that are typically used， and XV6 does that as well。Okay， so。

Here is the structure that XV6 uses for a spin lock。There are two other fields here， name and CPU。

 which you can see are just used for debugging。 So here's what a spin lock looks like。

 In addition to the key field that tells the state of the lock。

 we have a pointer to a string which could be used for debugging。And we have this field called CPU。

 which points to some other structure。Every core has a a structure associated with it called a CPU structure。

 And this field contains a pointer to the。Structure for the CPU that's currently holding the lock。

Okay， so the important functions on a spin lock or any lock， really， are acquire and release。

 In addition， we have a function that is to be called when the lock is first created that initial lies as the lock。

 Basically， it's past the name that we associate with the lock。 Once the name is set。

 it does not change。 We've also got a function that's used for arrow checking to determine whether the current core is holding the lock。

 Each of these functions is past a pointer to one of these spin lockstructs。

 So it's past a pointer like this pointer here。Okay， to acquire the lock。

 typically what we do is we just set， we want to set the field to one。But before we do that。

 we need to check to make sure that it's not currently being held。

 So our first pass at coding the acquire function might look like this。

 Check to see whether the lock is free and if it is free， then set it to one。 And if it's not free。

 then loop back and keep trying。 So these are spin locks。 they spin。

 It's a tight loop that keeps checking until it finds that the field is 0， it sets it to one。

 And then at that point， the lock is acquired。Well， of course。

 this has a problem if there are other threads that are executing concurrently。 in the case of x 6。

 we've got multiple cores。 So this one particular field in memory may be accessed simultaneously by other cores。

 or perhaps if there's thread switching going on within the single core。

 perhaps some other thread within the same core is trying to access the same memory location。

And we could have two threads simultaneously check this field。

And just happened to find that they are both。That that if the lock is unlocked and then simultaneously both set the lock to one。

 And， and so that's going to cause a problem because they both now think they are holding the lock。

 So we have to find another way to do it。 This code will not work。And for that。

 the Ri5 architecture has an instruction called AMO swap， Atomic memory operation swap。

And this single instruction will do two things。 It will copy a value into a word of memory。

 And at the same time， it will retrieve the previous value of that word。

 and it will do it without interruption。 So it will not allow any other threads or any other instructions。

 whether from this core or another core to do anything between the retrieval of the value and the setting of the value。

So here's how we're going to use that atomic memory swap operation to correct the problem that this code has。

We're going to execute the atomic swap operation， which I'm indicating schematically here。

 we're going to write a one into the location， and we're also going to retrieve the old value。

 the previous value。If the previous value was 0， then we're done， we have acquired the lock。

 But if the previous value was not 0。 Well， it must have been one because there are no other options。

 Then somebody else was previously holding the lock。 So we have to loop back and try again。

 So then we spin until finally， we find that the previous value was 0。

 and we then have acquired the lock。 The release operation is pretty straightforward。

 We just copy the unlocked。Value of 0 into the word。This doesn't。

 it's hard to imagine how copying value into a single location of memory could be anything but atomic。

 so in some systems this is implemented as just a single memory store operation。Okay。

 now let's look at the code for。The acquire operation。First of all。

 we can take care of the init operation。 This is code that's coming from the spinlock do C file。

To initialize a spin lock were passed a pointer to the structure and the name。 we set the name field。

 and it never changes after that。We also set the CPU field to null because the lock is not held。

 and we set its initial value to 0。Here is the code for the acquire function。 And here right here。

 we see the while loop that does exactly what I described previously。

This magic sync lock test and set is going to be turned into some assembly code。

 and the comment here is indicating that the AMO swap。Instruction is going to be happening。

 and it talks about some registers。 But essentially。

 we're passing at a pointer to the word that we want to update。And we're passing it the new value。

 which is one。 and this function is going to return the old value。

 and we're checking to see whether it is 0 or not。And if it was not 0。

 then we repeat this while loop。 And if it was 0， then we've acquired the lock and we're done。Now。

 there are a couple of other things I want to mention about this function。 First。

 once we acquire the lock， we are storing。Into the CPU field。

Every core has a structure associated with it。 So there are， in fact，8 cores。

 So there are 8 structures， and this function here will retrieve a pointer or return a pointer to the structure for the core that's currently executing。

 So we're just saving that here。Up here， we are checking to see whether before we acquire the lock。

 whether we already， whether it's already。Being held by us。

 So we'll see the holding function in just a second。 And if it is。

 then something's drastically the matter。 So we cause an error message。

Then we've got this synchronized thing going on here。

So tell the sea compiler in the processor not to move loads or stores past this point to ensure that the critical section's memory references happen strictly after the lock is acquired。

 This is a instruction。So we want to prevent the compiler for doing from doing optimizations。

 It might， in fact， reorder things， and that is not acceptable。

 though anything that's supposed to be done after we acquire this lock after this while it completes must be done after that。

 So that's what this synchronized does， It forces。The compiler to omit code and the processor to execute that code in such a way that everything that is supposed to happen before this point is completed and everything that is supposed to happen after this point is not started until after this point。

We see one other thing here that's kind of unusual。 And that is push off。

 The commentt says dis interrupts to avoid deadlock。 holy smoke， What's that， I mean。

 isnn't this a lock situation here， Why what Where are interrupts involved at all。

I'll come back to that in a minute， so I'm going to just leave you in suspense。But first。

 let's take a look at the release operation。We do a quick check to make sure that we are， in fact。

 holding this lock。And if not， we print an error message。

 and then we're going to be releasing it down here。

 And so we might as well go ahead and set the CPU field to know at this point。And。

Here we are copying the zero into this field。 They're using an A M O swap instruction to do it with this sync lock release。

 But like I said， it's hard to imagine how a normal stored of memory could be anything less than atomic。

And we've got。Pop off。 Well， we've got the synchronize here up here。

 which makes sure that anything that's supposed to happen before we release the lock actually finishes。

And that anything that's and only after we finish that， do we actually set the locked field to0。

 So pop off is a partner， a duall of push off。 And so what it does is it enables interrupts。

 And I'll come back to that in a second。 But first。

 let's look at this holding function just to complete this code。

This just checks to see whether the current core that's executing this is holding the lock。Okay， it。

Looks at the value of the field， and if it's one and the CPU is the same as this core。

 then it returns true and otherwise it returns false。

A spinlock should never be held for a long period of time。

Imagine a situation where one core is holding a lock and another core wants to acquire that lock。

 Well， the acquire function is going to be spinning in a tight loop。

 waiting for the lock to become free。 So as a general rule of thumb。

 you should always plan to release the lock soon after it's acquired。 in particular。

 we don't want the thread that's holding the lock to go to sleep or to get time sliced。

There are other techniques for locking in X V6， we have the sleep and the wake up function。

 and these can be used in situations where the lock needs to be held for a long period of time。

Locks are used to protect shared data。Actually， the X V6 documentation has some interesting wisdom。

 They point out that locks really protect。Constraints， and I think that's a nice way to put it。

 But other， in any case， we usually or almost always see this particular pattern here。

 We acquire the lock， Then we access the shared data， and then we release the lock。啲。

Code here is often called a critical section。 In other words， it's critical。

 It can only be executed by one thread at a time。 So therefore， this code is protected by a lock。

Let's look at a quick example。 And I'm going to imagine input。

 character input that's coming from somewhere and going to someplace else。

 So perhaps we have a keyboard。 and every time the user types on the keyboard。

An interrupt handler wakes up and adds a character to a shared buffer。

 So the buffer is the shared memory item， and it's going to be a 5，0 Q。 So the data goes in one end。

 And there's some other thread that is reading from the buffer。When it needs a character。

 it just needs to access this shared data structure， which we will need to protect。

 And in this example， we will protect it with a spin lock。

 So here's the code that we might see in the handler。 It acquires the spin lock。

Adds a character to the buffer and then releases the lock。

 the thread that wants to get input is going to acquire the lock so it can access the shared buffer。

 remove a character and release the lock。I'm not going to be concerned with what happens if the buffer is completely full or completely empty。

The handler is called when someone types a character on the keyboard and interrupt handlers。

Begin with the trap processing， which will disable interrupts。 And then they'll do some stuff。

 Basically， this stuff here in the case of our example。

 And then they will return to the interrupted code with the。S rep instruction。

 which will re enableable interrupts。 So we might imagine a thread T that's running like this。

An interrupt happens as a result of a key being pressed。 The handler runs。

 And then when it's done adding the character to the buffer， it returns to the interrupted thread。

 whatever it was and continues。Well， so you can imagine this situation。

If T happens to be this thread here that acquires a lock。And then at just the wrong moment。

 the interrupt comes in from the keyboard， and the handler is invoked。

 And the first thing the handler does is try to acquire that lock， well。

It will wait until the lock is released。 But unfortunately。

 the thread that is holding the lock is waiting for the handler to complete。

 So we've got a deadlock situation。In operating systems， we need to remember that if anything。

 if any combination of events， can possibly theoretically happen。

It's best to assume that it will happen no matter how unlikely or how rarely you think the event is。

Our first approach to solving the problem of deadlock is to disable interrupts in the acquire function and then to re enableable them in the release function。

So we don't have a situation like this if T acquires a lock。

 it will disable interrupts so it cannot have a situation where some other thread on that same core is trying to acquire the lock。

This also has an additional benefit。We don't want to hold spin locks for very long。

 So by disabling interrupts， we are preventing time slicing from happening while the lock is held。

 and we are preventing interrupt processing from occurring。Basically。

 we're allowing the core to focus on the thread that is holding the lock and to complete its critical section without interruption quickly and then release the lock。

But now we have another problem。 What if interrupters are already disabled。For example。

 in our handler code， we have interrupts disabled， and for a number of reasons。

 we don't want to re enableable interrupts prematurely before we get to the system return instruction。

We might also have several spin locks that we need to acquire。

 And so we have perhaps three acquire functions being called in a row。 And for each one of those。

 we'll have three release functions。 But the first release will disable， sorry。

 we'll re enableable interrupts。 and that might not be quite what we want。 So essentially。

 we want this release to return the interrupt status to whatever it was before the acquire happened。

 and we want to accommodate nested calls。 that is we want to accommodate several acquire function calls。

Followed by several release function calls。 And our solution to this problem is simple。

 We're going to use a counter， and that counter happens to be called in off。

And it's specific to a core。This variable will be held in the CPU structure。

 Each core has its own CPU structure， and each one will contain its own counter。

 So the acquire function will increment the counter and then disably interrupts。

Perhaps they were already disabled， but they will be after they acquire for sure。

And what's release going to do， Well， release is going to decrement the count and to handle the nested case。

 If it goes back to 0， then it's time to consider re enablingabling them。 More precisely。

 we need to ask whether they were previously enabled before the first。Call to acquire。

 So if the count is zero and they were previously enabled， then we will re enableable them。

That previously enabled status is kept in a variable called interrupt enable and Ena， I guess。

 And so we all， we will remember the previous interrupt status before the first call to acquire in this variable。

 which is a part of the CPU structure。Okay， now we can take a look at the code for push off and pop off。

Remember that in the acquire function shown here。The first thing we did was。

Call push off to disable interrupts to avoid deadlock。 So now we know what that means。

 And in the release， we also end up calling pop off。Here's through code for release。

 And right before we return， we re enableable interrupts if appropriate。

 So let's take a look at push off and pop off。Push off is called by a choir。

 We immediately turn interrupts off。 We disable interrupts。 Well， first。

 we find out what the previous status of the interrupts was。 That's called old。

And then here we're accessing the CPU structure and。If this is the first call to acquire。

 that is if the counter already is previously zero， then we're going to save the old status。

But in any case， we're going to increment the counter。Pop off is， as you'd expect， pretty similar。

 We are accessing the counter and the。And。Enable variable here。

 So we start by getting a pointer to the CPU structure。

And then we decrement the counter at this point here。

 And if it went to 0 and interrupts were previously enabled。

 then we turned them back on at this point。We also have some error checking here if for some reason we call pop off and interrupter are already enabled。

 somethings drastically the matter， so we print an error message。

And we also make sure that the counter is not zero or smaller。

 That would also be some sort of an error condition。Okay， that's it for spinlocks。

 See you in the next video。

![](img/8896ea6bdf0be38fd30126c199553dba_2.png)