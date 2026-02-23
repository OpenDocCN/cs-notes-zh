# hhp3《xv6 操作系统内核｜The xv6 Kernel 2022》中英字幕 p34 -34-xv6 Kernel-34_ Pipes.zh_en -BV11CkSBsEtN_p34-

![](img/48680c89d95a119025e2ade46aab8df0_0.png)

Welcome to another video in a series on the X V6 operating system kernelel。😊，In this video。

 I'll be talking about pipes， and I'll do a code walk through of the file， pipe dot C。

Remember that in Uniix， a pipe is a little bit like a file。 You can write data to it。

 and you can read data from it。 However， a file is kept on disk while a pipe is entirely within memory。

So here we have a process， let's call it W writing data to the pipe。

 and some other process R can be reading data from that pipe。

The data is kept in some buffer inside the kernelel's memory。 and that buffer has a limited size。

 So if process W writes too many bys， the colonel will need to suspend it until the buffer is no longer full。

 And likewise， if process R tries to read bys， but there are no bys yet sitting in the buffer。

 then the kernelel will need to suspend process R until process W writes some bys into the pipe。

For every open pipe， the kernel will allocate and use exactly one structure of type pipe。

 which I'm showing here。So this structure has a spin lock。

 and that spin lock protects all the remaining fields in the structure。It has a buffer。

 and that buffer is 512 by。 In our case， the actual size is determined by a constant。

 which is defined to be 512。And it has two indexes， read and write。

 which tell where in the buffer we are。 and a couple of Boolean flags called Read open and R open。

 which I will discuss a bit later。Now with ins， the kernel maintains a cache of inots。

 some of which are free and unused， and whenever we want to allocate a new inode。

 we search through that array and find an unused inode and then we allocate it and use that one。

With pipes， things are done a little bit differently。 Instead。

 we don't have a cache or an array of unused pipe structures。

And whenever we need a new pipe structure， the colonel will call Kalc and allocate an entire page。

 And then when it's done with that structure， it will return that page to the free pool。

Remember that our pages in X36 are 4 k bys in length。

 so the structure itself will occupy just a little bit more than half a K。

The remaining through almost3 and a half k of the page will simply be unused and wasted。

For a production operating system， you might want to think about a slightly different organization。

 particularly if you think that we are going to have a lot of pipes， but for XV6。

 we're not going to have so many pipes， and this is quite practical。

Now next I want to talk about the code here and show that the code corresponds to this exactly here we have the spin lock。

 here's the definition for the structure pipe coming from file pipe。C， and we have the spin lock。

 we have the buffer of size pipe size， we have the two indexes and we have the two Boolean flags here。

How are these indexes used， Well， the in read tells where in the buffer the next bite to be fetched for the reader is。

 And the inright index tells where in the buffer。 we should put the next bite that is written to the pipe。

And so here in red， I'm showing that this buffer contains several bites。

 and we will add to the buffer at this point， and we will retrieve from the buffer at this point。

 advancing the pointers。This buffer is a circular buffer。 So before we access the buffer。

 we are going to take the value modo 512。 So we have a wraparound situation。

 Here's another situation where we have 1，2，3，4，5，6，7 8，9 bys in the buffer。

 and they wrap around here。 You can think of the buffer as an infinite sequence of bys。

 So inread and inrite can be advanced well beyond 512。 In other words。

 we can write thousands and thousands of bytes into the buffer。

 As long as we keep up with the reading and never have more than 512 bytes in the buffer。

 So these two situations are equivalent views of the same situation。

An empty buffer situation will look like this whenever the Re index catches up to the right index。

 we have an empty buffer。 Okay， the next character or the next byte that we're going to write into the buffer will go into this position。

 and in retails where to read it。 And we haven't written that bite yet。When the buffer is full。

 we have a full 512 bys in the buffer， so the right pointer will exceed the read index by exactly 512。

And we can think of it this way， or we can think of it this way。Now， in the past。

 I wrote some code like this and I stored， I performed the modular operator before storing the indexes。

 so these indexes would only range from 0 to 511， and that's really not a very good way to do things because it makes the empty situation identical or appear to be identical to the full situation。

 So it would require some other data， when reading the XV6 code。

 I realized that this is really a much better way of doing things。

 So we allow inread and inrite to exceed 512 perhaps by quite a lot。

 and we only take the modular operator before accessing the data in the buffer。

 and this is a superior way of doing things that I learned by reading the XV6 code。

 And that points out that you really can learn new tricks by looking at the way someone else does something that is by reading other code。

Okay， next let's get into talking about how this pipe structure is used。

We'll begin by assuming that we've got a process called P。

Every process is represented by a proc structure， and this object right here is used to represent process P。

Process can have a number of files open at any one time。

The user code refers to the individual files using a file descriptor。

 The file descript is a small number，0，1，2， and so on。

 and is used as an index into this array by the kernel。 So within the pro structure。

 we've got this O file array。 and it contains pointers to file objects。 So for every open file。

 there is a pointer in this array。 and it points to this file object。And of course。

 the user process doesn't get to use pointers in the kernel space。 Instead。

 it passes in a file descriptor。 So for example， if it wants to read from file number two。

 it passes in a two and the kernel will then follow it to this file structure。Here。

 it looks like we've got all the file descriptors in use。

 but if some of the files are closed and these entries are unused。

 then there would be a null stored in that particular entry。The file object starts with a type field。

 and I'm going to be talking about pipe。 So the type for this example is pipe。 but in most cases。

 the file structure is going to point to an i note。 So in any case。

 the file structures contain a pointer， and that pointer will point to some object。

 It could be a pipe or it could be an i note。Normally it would be an iode for a regular file or a directory。

There are also a couple of flags， the readable flag and the writeriable flag within the file structure to tell whether the file can be read or written。

 or perhaps both。In the case of a pipe， we have two file structures， Okay。

 we have one for the read end and one for the right end。 and so the file structure for the read end。

 well， it would have a type of FB pipe and the readable flag would be true。

 but it would not be writeriable and for the right end of the file of the pipe。

 we would have a file structure again with type FD pipe and it would be marked rightriable but not readable。

And so we can have two pointers， or we will have two pointers pointing to the pipe and two file structures。

 one for each end of the pipe。Now， these file structures contain a reference count， too。

 I didn't show it here， but the file structure can be pointed to by a number of different processes。

 right， This one particular file could be opened by lots of different processes And so we have a number of different pointers here。

 and the reference count keeps track of those。 And when it goes to zero。

 we can reclaim the space used by the file structure and add it back to the free pool。

The pipe structures， on the other hand， will have exactly two pointers pointing to them。

 So in the pipe structure， we have these two fields that I showed earlier。

The read open and the right open flag。 And so。The read open flag will will be true if and only if there is a file object pointing to this pipe structure。

 And likewise， the right open flag will be true。 if and only if there' is a file for the right end。

 pointing to this pipe structure。 And when both the read open and the right open are false。

 we can say there's no pointer pointing to this pipe object。 And then it can be returned。

 in that case， we would go ahead and free the entire page that it sits on by calling the K free function。

Okay， so what I want to do is assume that this process P has called the pipe system call to create the pipe and to allocate two file objects and set up these pointers。

 so after the pipe system call， this is the situation we have。

The the system call will find some empty slots in the file descriptor array。

 and it will use those and it will return those numbers in this case。

2 and4 to the user mode process so it can refer to either the read end or the right end。

Now let's assume that this process forks a couple of children。

One child will be a reader process and the other child will be a writer process。

So whenever we fork a process， we make a full copy of this array。

Okay so we copy all of the open files。 so if a file was open in the parent。

 it will be open in the child。 and so initially both pointer2 and pointer4 here will be set to point to these two file objects。

 but we're going to assume that the reader process immediately closes the right end。

 so we decrement the count to this the reference count for this object and set this pointer to zeros because that pointer no longer exists。

And process P is also going to fork the right process。

 and again the entire O file array will be copied and the reference counts increased for all the file objects。

And then we're going to assume that process W will immediately close the read end。

 So we'll end up following this pointer， decrementing the reference count and then setting that to null。

 So now we have this situation。 By the way， my indexes don't quite line up here。

 but I think you get the idea。So at this point， we have this situation where。

Process R points to a file object for the read end of the pipe。

 and process W points to a file object for the right end of the pipe。

 The parent process still has these pointers， and perhaps it will go ahead and close them or not。

 But I don't know。 But in any case， at this point。Process W can send data to process R by issuing a system call a right system call on the file for file descriptor4。

 while the reader can read data from the pipe by issuing a read system call using file descriptor 2。

So here is the pipe allocate function， and what it's going to do is allocate the pipe structure and these two file objects and return pointers to the two file objects that were allocated。

So it has to return two pointers。 So that's done as follows。

 The first argument as zero is a pointer to a pointer， and that's for the read end。

And the second argument is another pointer to a pointer for the right end。

 and you can think of it this way if you're not familiar with this pointer to a pointer stuff。

F0 points to an area where we will store a pointer to the read end file object and F1 points to an area where we will store the pointer to the other file object that we allocate and this function will return0 if everything's okay and minus1 if there's a problem。

So we start by initializing these two variables to0 so that they don't point to anything。

 and then we call fileile Ac to allocate the read end and save that in this variable here and we call file ALoc again and save the pointer to this object in this location here and if there was a problem with either of these and we get null back then we're going to go to this bad label down below where we clean up。

And the next thing we do is we call K to allocate a page in memory。

 And if there's a problem with that， again， we get a null back and we go to bad。 Now。

 if we go to badd， let's take a look at the bad label down here。 We basically need to clean up。

 So we check to see whether we've allocated either these file objects。

 And if we've allocated the read end。 Well， we call file closed to get rid of it。

 And if we've allocated the right end。 we call file closed to get rid of it。

 We have this code here that checks P I。 That's the pointer to the page that we've allocated。

But if you look at this code， I don't think you can ever actually call K free here because P is set to 0 here。

 And if we go to bad here， P will be 0， and it won't get executed。 And likewise。

 the only way we can take this jump is if K Alc returned。 No， in which case P I will be 0。

 So I think this test is actually。Superfluous and cannot actually be used。 but in any case。

 moving on。first， the next thing we do is we allocate the pipe structure。

 So remember that we have a number of fields in the pipe structure that we need to initialize。

 We need to initialize the spin lock， as well as the two indexes into the buffer area。

 and these two flags。 And we're doing that right here。 Here we are initializing the two indexes。

 Here we are initializing the two flags。 And here we are initializing the lock associated with this pipe。

Then we need to initialize the two file objects。 So for the read end， we set its type 2 F pipe。

 and we make it readable， but not writeriable。 And we set its pointer to point to the pipe object that we just。

Allocated， then we allocate， then we initialize the right end。 So we set the type to F D pipe。

 and we set it to writeable， but not readable。 And again。

 we set its pointer to point to the pipe object。 And finally， we return 0 because everything's okay。

Here is the pipe read function in addition to the pipe allocate function， there's also a read。

 a write and a closed function， so we only have those four functions to deal with。

The pipe read functions passed a pointer to one of these pipe objects。

 as well as an address and a bite count。This address is a virtual address。

 and the bike count tells us how many bytes we want to get out of the pipe at most and place into the user's virtual address space。

This function will return the number of bytes that we actually read。

 and this could be 0 if the pipe has been closed down。And if there's a problem。

 it might return minus1。Okay， since we're going to be accessing the counters。

 the in read and the in right counters， we need to first acquire the spin lock that protects this pipe structure。

 so we acquire that lock right here。And then in this loop here。

 we are going to be checking to see whether the pipe is empty， right。

 We have two situations that we need to watch for。 One is whether the pipe is empty and the other is whether the pipe is full。

 If the pipe is empty， then the reader will have to go to sleep and wait for a rider。

 And if the pipe is full， then a rid would have to go to sleep and wait for a reader to take some of the bites out of the pipe。

So here we're checking to see whether these two things are equal and if the two indexes are the same。

 we have a situation like this where we have an empty pipe。So if we still have a writer， okay。

 then we will go to sleep and wait for that writer to put something in。If we don't have a rider。

 then we've got a problem。 There's no point in going to sleep。 If the right open is false。

 it means there is no file object that is pointing to this pipe。

 And so no bites will ever be written， and we will never be awakened from any sleep。 We would do。

 So we better not go to sleep。 Instead， we'll just return 0 down here。

So let's say that the pipe is empty and we do have a rider， then we will go to sleep。Okay。

 so the sleep is needs a channel and the channel number that we're using。

 that is the code or identifier that we're using to the sleep function。

Is what is the address of the read index。 So we're passing at the address of the read。

Field within the pipe structure that is currently empty。

 and that will be the channel that the rider will wake up on。

 It will issue a wake up call using this channel to wake up this process。When we call sleep。

 we need to be holding a spin lock， and we are holding the spin lock。

 and that will be momentarily released。 But then when we are reawakned。

 it will be reacquired and we'll loop back and again check to see whether the pipe is empty。

 It could be that some other process is another reader and grab with those bites and the pipe is still empty。

 So we make these checks again。 And assuming that there are bites in the pipe。

 Then we can proceed down here。Before we go to sleep。

 we also check to see whether this process has been killed by some other process。

 So we're grabbing a pointer to our proc structure， and we're checking the killed field here。

 And if that's been set to true， then we need to know terminate after the system call that's involved with this pipe reading。

 And so we immediately release the lock and return -1 to indicate that something is wrong。Okay。

 so assuming that's not the case。 We go to sleep。 Eventually we wake up and we find that the either the file is no longer empty or there is no rider anymore。

 in which case， we need to go ahead and return something。

So what we're going to do is we're going to loop through each byte we need to find up to n bytes。

 and we're going to ultimately return the number of bytes that we have transferred and we're going to transfer each one byte at a time。

So we check here to see whether the pipe is empty。 we could get to this situation after looping through this a couple of times in which case we've emptied the pipe。

 or it could be that on the first iteration， we got into here because there's no rider and so the pipe is empty and furthermore。

 there's no rider， So in that case we need to return zero immediately。

 but normally we would get at least a couple of bytes， so I will not be zero。

So if the pipe has something in it， then what we're going to do here is we're going to go to the buffer area in the pipe structure using inread as the index。

 And remember it's a circular pipe， and so we need to do mod， the pipe size， which happens to be 512。

And then we use that as an index to grab a byte of data， advancing the index。

And we save the byte in C， H。 And then we're going to transfer that one character to the virtual address space。

 So that's the copy out function right here。 It's past a pointer to the page table that describes the user's virtual address space。

 As well as where we want a place that byte。 So this is the virtual address。

 that was was our argument here。 offset by how many bytes we've read。

 and we are passing a pointer to these byte that we just retrieved， as well as a bike count of one。

 And if that works okay， then we loop back， but otherwise we break out of this loop。

 and we've had we're done。 In any case， we have。Red bytes。 Well。

 maybe we haven't actually retrieved any bys an increment of the in read。

 it can't hurt to wake up a process， but in any case。

 we must be sure to wake up any rid because we have probably removed some bys from the pipe and so the pipe is no longer empty。

 So we use the address of the right index for the rid。 So while this。

 while readers will sleep on the read index and wake up on the right index。

 writers will sleep on the right index and wake up on the read index。Well。

 after waking up any waiting， waking up all waiting riders。

 we will release the spinlock and return the number of bytes that we have。

Moved into the user's virtual address space L at this line。Okay， next。

 let's move on to the right function。Here is the pipe write function， like the pipe read function。

 It's past a pointer to the pipe structure， as well as an address and a byte count。

 The address is a virtual address in the user's address space。

 and N is the number of bytes to transfer from that virtual address space to the pipe。

It returns the number of bites that have been moved into the pipe。In the case of pipe readed。

 the number returned maybe be less than the desired number。

 The pipe read function will try to read at least one thing。

 but will return after getting at least one by if there is nothing else waiting in the pipe。

On the other hand， piperight will try to write all n bytes and will normally return in。

 If there is some sort of an error， it may return -1。 And if there's a problem with the page table。

 it might return a value less than n， but normally it will return all in bys。

 So the structure of this function is a loop。 And each iteration of the loop。

 will try to move exactly one by， and that happens right here。 and we increment I。

 So I starts out as the count。 I is the count of bys that we have moved。

 and it will keep being incremented。 And ultimately， when we exit this loop， I will be equal to n。

 and we will return n。 the number of bytes moved。It may be that we execute exit prematurely if there's a problem with a page table and we return a smaller in。

 smaller value than in。So let's take a look at this。First of all。

 we check in the body of the loop to see whether we have any readers。

 if the read open flag of the pipe structure is false， then there are no readers。

 so we immediately return -1。Likewise， if we have been killed。

Then the killed field of this process will have been set。

 and we need to abort immediately and return -1。 But in either case。

 we release the spin lock first before returning。So assuming everything's good。

 we next need to check to see whether the pipe is full。 And here we have that check。

So in Re plus the pipe size。Which is 512。 If that equals the right index。

 then we've got a pipe full situation。 That is shown in this picture here where N rate plus 5。

12 is equal to N right。If we've got a pipe full situation， then we need to go to sleep。 but。

 and we will use as the channel to the sleep function。

 the address of the right index in the pipe structure。Okay， and readers will。

Wake up using that channel。 Remember that the here's a pipe read function。

 And remember that when we do a wake up， we wake up on the right index for the pipe that we want to wake up。

Before we go to sleep， though， it may be that we have some readers that are waiting。

 And so we need to wake up any sleeping readers。 It may be that this loop has looped through。

 We started， we might have started with an empty pipe。 And the readers were waiting to be awakened。

 and in maybe a very large number greater than 512。

 and we may have executed this loop enough times to fill up the pipe。

 in which case we need to go to sleep because the pipe is full， but we've got。

Readers that went to sleep when the pipe was empty。

 So we need to wake up any readers that are out there first before we go to sleep。Okay。

 assuming that the pipe is not full， then we can go ahead and move a byte to the pipe。

 So that's what's happening here。 We use the copy in function to copy bytes from a virtual address space as described by this page table here to some place。

 that's the local variable C H。 And where are we copying from， well。

 it's the virtual address plus the number of bytes already copied。And were moving one bite at a time。

And if anything goes wrong， then we abort the pipe right function with however many bytes we've successfully copied。

 we break out of this loop and return the number of bytes we've copied so far。

 But assuming everything' is okay。 Then we've got a by from the user's virtual addresser space。

 And in this next line， we move it into the buffer for this pipe。 So we are using the right index。

 and we are taking it modd 512， the pipe size。 and we're moving the by into that location in the in the buffer。

 And we are then incrementing the right index， as well as incrmining eye。 And then we loop back。Now。

 after we're done filling the pipe， there may have been some readers that were sleeping。

 And so we need to issue a wake up call。 And again。

 we're issuing the wake up call using as the channel， the address of the inread index。

 which is what any sleepers for this pipe will have gone to sleep on。And finally。

 we release the spin lock for this pipe and return the number of bytes that we have transferred。

Finally， let's look at the pipe close function。Remember that from time to time。

 a user process will call the closed system call， providing a file descriptor， for example。

 file descriptor number two， and what that means is the user wants to remove this pointer and eliminate this file from this process。

There is a reference count associated with each of these file objects。

 and if it does not go to0 when we eliminate this pointer， then we don't do anything。

 but eventually it will go to 0 when there are no more pointers to the file object。

 And at that point， we need to return the file object to the free pool and eliminate this pointer here。

 And so at that point， we will call the pipe closed function on this object here。So， whenever we。

Close the read end or close the right end。 We will call this pipe close function。

So let's take a look at it。It is past a pointer to the pipe structure and a flag to indicate whether we are closing the right end or the read end。

 And so that's this argument here。We begin by acquiring the lock for the pipe object。

 and then if we are closing the right end， then we will set the right open flag in the pipe structure to 0。

 Okay， again， that's this one right here to indicate that we have lost the pointer from the file object that's associated with the right end。



![](img/48680c89d95a119025e2ade46aab8df0_2.png)

Now， there could be readers or processes that are reading。

 and they are waiting because they found that the pipe was empty。

 And so they're just waiting for something to go into the pipe。 So we need to wake those up。

 Remember that a reader will be sleeping， if it finds that the pipe is empty。

 So going to the pipe read again， we see that if the pipe is empty， then we will be sleeping。

 But we also check to make sure that we do have a right， and if we eliminate the right end。

 if we close down the right end， we need to wake this sleeping reader back up and it will check。

 and then it will find that there is no right end open and it will go ahead and return  zero。

 So that's what's going on here， if we're closing the right end。

 we set the flag to0 to indicate that we do not have any right end and we wake up any waiting readers。

 On the other hand， if we're closing the read end。Then we set the read open flag to 0 and wake up any sleeping riders for the same reason。

Finally， if we have closed both the read end and the right end。 In other words。

 if now both these flags are 0， then we are done with a pipe object altogether。 So at that point。

 we release the lock and call Kafr to return the page that contained the pipe object back to the free pool of pages。

😊，If the， if there's still one of the ends open， then we will just release the spin lock for this pipe object and return。

 Okay， that's it for pipe dot C。 I will see you in the next video。

