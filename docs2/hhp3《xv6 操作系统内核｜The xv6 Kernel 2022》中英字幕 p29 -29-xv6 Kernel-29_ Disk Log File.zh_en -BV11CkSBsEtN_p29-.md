# hhp3《xv6 操作系统内核｜The xv6 Kernel 2022》中英字幕 p29 -29-xv6 Kernel-29_ Disk Log File.zh_en -BV11CkSBsEtN_p29-

![](img/46c888c8ad76322da5c207a052a57417_0.png)

Welcome to another video in a video playlist describing the X V6 operating system kernelel。

In this video， I'm going to describe the disk log file system。

 and I'll be covering the code in the file， log C。This code is pretty complicated。

 so I'm going to start with a motivating example。The problem is that we may have complex data structures。

 and crashes can occur。And updates require several different operations in order to perform the entire update consistently。

So， for example， here I have a singly linked list。 Okay， it's linked like this。

 And I'd like to swap the order of these two nodes。 And so I need to update1，2。

 three pointers in order to do this particular update。

 So I need three different rights to make the change。

 And if a crash occurs in the middle of this operation。

Then the data structure can be left in what we call an inconsistent state。 In other words。

 the link list is all messed up。 And while this example is probably in memory and the whole thing just goes away at the time of the crash。

 what we're really getting at here is a problem with the file system。In that case。

 the data structure is kept on disk， and that data structure is used to represent files and directories。

 as well as IOs and free maps and so on。In my example。

 each update was a modification of a single pointer， but with our file system。

 each right will be a right of a single of an entire block to the disk。

And a particular update may involve several blocks。 In other words。

 it may require several blocks to be written to the disk。And a crash of the system。

 either a hardware crash or a software crash， must not be allowed to。Mess up the file system。

 We need to keep the file system in a consistent state。So in this particular example。

 if we are going to swap these two elements， we either need to do none of the changes in which case the update hasn't occurred。

 or we need to do all of the changes in which case the update has occurred。

Let's look at a more realistic example from the file system。

 Let's assume we want to increase the size of some file。

 We will have to allocate and remove a block from some pool of free blocks。

 and then we'll have to add that block to the file that we are growing。

 And each one of these will involve an update to the data structure。

 So we assume that we have to have at least two disk rights。Now。

 assume that the computer crashes and that one of these rights has completed。

 but the other one has not completed。 So we might have a data structure that is corrupted in an inconsistent state。

So how are we going to guard against this？ Well， we might try removing from the free pool first。

Before we add the block to the file， that the crash occurs after the first right。

 then we've got one block that has been removed from the pre pool， but not added to any file。

 So essentially we've lost a block。 It's become unaccounted for。 So that's not going to work。

 So maybe we can reverse the order and add the block to the file first。

 that is perform the right that will update the file data structure。

And then update the free pool data structure to indicate that we've allocated one of the blocks。

 But then if the crash occurs after the first write， then we've got a different problem。

 We've now got a block that's still in the free pool yet has already been added to a file。

 and that's a disaster as well。 One block is both in a file and in the free pool。

So neither of these two approaches works。This problem is more general， you know。

 imagine a bank computer a system that's involved with bank accounts and money。

And imagine that the operation of the transaction。Is to remove， say。

 a million dollars from one account and put it into a second account。

And this operation is going to involve two different updates。

 One removes the million dollars from one account， and the other update adds the million dollars to the second account well。

You can't tolerate a crash。 I mean， if you do them in one order， you may have lost a million dollars。

 and if you do them in the other order， you may have fabricated a million dollars out of thin air。

 And neither of those solutions is is acceptable。 So this problem of transactions and is a general problem。

 And we're going to see how it's handled here in the X V6 operating system。

With an operation involving two rights， our goal is that either both rights are completed and the disc is updated。

 or if a crash happens。Neither of the rights is actually performed。 So it's either all or nothing。

 We don't have a situation where one right is done to the desk， but the other right is not done。

More generally， we can talk about transactions and we will group several updates。 and in this case。

 we're talking about disk rights。And we will group several disk rights into a single transaction。

 And either the transaction occurs， and the disk is updated。

 or the transaction does not occur before the crash， and none of the rights occur。 All or nothing。

What this looks like in X V6 involves these functions， begin op， B read， log writeite， and end op。

 and the begin op function will be called first， and that will start what we call a transaction。

 And then the end op will end the transaction and between these two， we will have a number of rights。

 we will also have some reads as well， but it's the rights that we're sort of focusing on。

 and when the end op function is called。 Then the transaction is complete。

 and it signals to the system where the transaction is。

 and it will either all happen or not happen at all。Now， let's take a look at this example。

 I've got two transactions。 Here's one， and here's the other。

 and they're being executed in two separate threads concurrently。

So each begins with a begin operation and ends with an end operation。And there are a number of reads。

And write in the transaction。 And so I'm showing in this transaction， we are reading block number 1。

0，3 and writing it back to the disk。 And then here we're reading block 10，8 and writing 10，8。

And in this transaction， we are reading block 103， but were not writing it。

 And then we're reading 10，6 and writing 10，6。 So whatever we write into block 106 could be dependent on 1。

03。 And I'm showing by the positioning here that this read occurs after this right。

 So here with this read， we must be getting the version of the block that was written by this right operation here。

 However， we can't actually write this。Block to the disk until after the end operation。

 So we have to keep it in a buffer and delay the actual right to the disk。 while at the same time。

 delivering to this read operation， the data that was written here。

 So we have to get the new version。 And the other thing is， when this transaction ends。

 we can't just simply write block 10，6 to the disk because it's dependent on 103 as well。

 So we can't actually perform the disk update until we're ready to perform this end operation。

 We've got to wait。 We can't write block 106 and we we are also writing block 103 and 10，8。

 So in a sense， these things are all linked together。

 and have to be either committed together or not committed。

So what we're going to do for the right operation is。Keep the block in the buffer cache。

 In other words， we're not going to write it to the disk immediately。

 We're just going to keep it in memory。And that solves this problem here， for the read。

 we will use the version of the block that is in the buffer cache if there is a block sitting there。

 and otherwise we will read the data from the disk。Okay， at the end operation。

 we will not perform the rights until all of the transactions are ended。 Okay。

 here we have two separate transactions。 And at this one， we're not going to do anything， really。

 It's only at this point here where we will be doing the rights。ok。

We also have a requirement that we want to avoid the exhaustion of the free buffers and log records。

 okay so we can't start operations， can't start transactions if we don't have enough memory or resources to complete the transaction。

We also don't want to delay writing forever， that would be starvation if we， for example。

 have a sequence of transactions that are trying to be started。

 we have a bunch of transactions and there's always one in progress。

 it might be the situation where we never have a situation where we can actually do the commit。Okay。

 so we can't allow that， so we will have to delay some begin operations if we have inadequate resources or if starvation is a possibility。

And finally， we have this idea of a commit， and at the time of the commit。

 that is when we perform all of the right operations that we've accumulated so far。

So here at this end， we won't actually do the commit。Okay， this transaction is over。

 but it's not yet committed。 It's only at this point here when all transactions are completed。

 that we can perform the commit operation。Here I am showing in schematic form the disk。

 Each one of these little squares represents a block on the disk。

 and the disc is nothing more than a sequential set of blocks。

 starting with block 0 and going up to some maximum。We'll be talking about the log。

 which consists of a header and some log blocks， and we won't be too concerned with the first two blocks。

 The first block is the boot record or the master boot record。

 and the second block is the super block。The super block contains a number of fixed parameters。

 Its read only。 And at start up time， the colonel will read in the super block。

 And this super block contains parameters such as where the log is located， how big the log is。

 where the main block area begins， and how many blocks there are on the disk。By the way。

 XV6 talks about a disk， but file systems can be stored on not only rotating disks。

 but solid state storage devices as well， and the organization doesn't really matter。

 I mean it's similar for solid state as it is for disks。

 the solid state device is broken up into a number of blocks and so on。

 but we'll just stay focused on the disk here，Log consists of a header and a small fixed sized area。

 which contains a number of log blocks。 In our case， it happens to be 30。

And that's followed by the main block area。 The main block area is where the file system is stored。

 and the file system contains all kinds of stuff。 the directories， the files， the i notess。

The log system is not going to be concerned at all with the organization of the file system。

 So from our point of view， in this video， the main block area is just a large collection of blocks。

 We don't really know how it's organized。The header block。

Is read in at startup time into memory and stored in a structure。

 So here's the structure that's kept in memory。 And from time to time。

 this structure will be written back to the header block on disk。The header contains a counter in。

 which tells how many of these log blocks are in use。 And for every one of these log blocks。

 there's an entry in an array。 So this number in tells how many of the array elements are in use。 So。

 for example， at any one point in time， we might have， say， three log blocks in use。

 and the remaining are yet to be used。 So in that case， in would be three。

 and the first three elements here would contain information about which block is stored in these positions on the disk。

I'm also showing here the buffer cash。 Remember that the buffer cash is a circularly linked list。

 a doubly linked list with a header buffer and a number of buffers。

I'm also showing individual blocks in the main block area。 These are from the previous example。

 I'm going to try to work through it and show how this thing gets updated。 like blocks 10，3。

106 and 108 contains some data initially。Here is the example that we're going to be walking through。

 Every transaction begins with a begin operation and ends with end and can contain reads and writes。

So let's take a look at what all these operations do， read， write， begin， and end。

The read operation is really just B read， which we discussed in the previous video。

What we'll do is we'll search the buffer cache to see whether the block that we want is in memory。

 And if so， we'll just use that。 Otherwise， we'll allocate a buffer from the buffer cache and read in the data from the disk。

The right operation is something new， and it's implemented with a function called log， right。

The first thing it will do is it will pin the buffer that we're trying to write。

 Remember that we only do a right after we've read a particular block。

 So we have a buffer and we want to write the buffer out。 So we won't actually write it at this time。

 Instead， we'll just do something we call pinning it。

 which basically sets a flag to indicate that that buffer should not be freed。

And then we will find the next available slot in the log。 Okay。

 if there are three elements in the log， then in will be 3， and we increment to 4。

 and we are able to use the next entry in the array。

So we add an entry to the array and increment the counter。But first。

 it's possible that the block that we're writing has already been written and therefore is already located in the log。

 So we search the log。 And if we find it， we just reuse that log slot， and we do not increment N。

Every transaction must begin with this operation， and it's actually done in the function called begin op。

If there is another thread in the middle of a commit operation。

 then the begin operation will just wait。 Okay， we'll go to sleep and wait until that commit is done。

 and then it will proceed。It will also check how many slots are available in the log if we don't have enough resources to continue this to complete the biggest possible transaction。

 then there could be a problem， so the begin ratio will just sleep and once other things have finished。

 it will be a reawakened。Finally， when everything's O， it will increment a counter。

 and that counter just tells us how many transactions are currently in progress。

The end operation function end op begins by decrement in this counter。If it goes to zero。

 that means this is the last transaction， and we can go ahead and do the commit。

But if there are other transactions currently in progress， then the counter will not go to 0。

 so this end will just return immediately without doing anything further。

The commit operation will then perform all the rights to the disk。

 You will actually do writing of the blocks to the disk。In the right operation。

 there is no actual right to the disk。 Okay， we just save everything in memory。

And then we will empty the log。 And finally， since this transaction is committed and we've released the log blocks。

 we can then wake up any sleeping operations that are stuck on begin。

I want to mention one thing by saving the rights until the commit operation， we are bunching them up。

 so it's very typical for a program to write sequential bytes to a particular disc block and we don't want to do a write to the disk for each time a program writes a single byte。

 instead we just use the same buffer in memory and they get saved up and then at the time of the commit。

 we do a right that writes the entire block。Okay， now I'm going to walk through this example here and I'm going to execute it by updating the desk on this piece of paper here。

To make it more interesting， I'm going to change this from block 108 to block 106。

And we begin with the read of block 103。Well， we start by searching the beak。

 the buffer cache for that block。 We find out it's not there。

 So we perform a disc read and allocate a buffer and read block 103 into that buffer。

 So I'll put an next right there。Next， we write that same block。

 so we will allocate an element in the log of change this n to one。

 and this first element will set to 10，3。This particular block will go into the log right here。

 but we don't write it just yet。The next thing is a read of block 106。 So again。

 the B read function will search the buffer cache。 find it's not there。

 grab a free buffer and read in block 106 to this point。Okay， we'll put it right there。

I forgot to mention that with this right here， we'll also pin this buffer。

 so I'll indicate that a buffer is pinned by putting a little check mark underneath it。Okay。

 now that next transaction begins by reading 103， and that call to B read will search the buffer cache。

 find that we already have it。 So a disc read will not be necessary。

 It'll return a pointer to this buffer right here。And the next thing we do is read block 106。

 And again， we have it in the buffer cache。 so we return a pointer to this buffer here。

And then we do a write of 106。 at that point， we will search to see whether 106 is already in the log。

 We find out it's not。 So we allocate another element in the log， and so we increment in to 2。

 and we write 106 here。Okay， and we also pin that buffer。And finally， we end。 well。

 I haven't shown the incrmenting or the decrementing of the counters。

 but this is not the last transaction。 So we really don't do anything。

And then the other thread continues， and it tries to write block 10，6。 So again。

 what it will do is it will search the log。 And this time， it finds that it is there。

 So it doesn't really have to do anything。 in is not incrementent。And this is。

 this thing is already pinned。 So it really doesn't do anything。Okay， and finally。

 we come to the end operation here。 And at that point， we find it's the last transaction。

 And now we're ready to commit。 So next， let's take a look at what happens in the commit。

The commit has two phases。 In the first， it's going to move the updated versions of the blocks into the log area on the desk。

 And then in the second， it's going to write to the main block area of the desk。

 So the commit operation will begin by going through the array in the log header。And for each block。

 okay， in our case， there are only two blocks， blocklock 103 and 106。

 We will copy that block from the cache to the log area on the disk。Okay， and then at that point。

 after they've all been copied， we will write the header to the disk So I can indicate the first。

 we're going through this loop here。 We've got two elements in it。 and we're going write the。

New version of this block and that block。 Maybe I should put a prime here to indicate that it's been updated。

 So we write X prime here。 and we write Y prime there。 Okay， and then finally。

 we write the header back to this block on disk。 So at that point， we are committing。 Okay。

 if a crash occurs before this right of the header to the disk。

 then it will be as if none of those transactions ever happened when we boot back up and do the recovery。

 On the other hand， if the crash happens after this write。

 then these transactions will be carried out and they will succeed。Okay。

 so now after the header has been updated on the disk。

 we're going to go through the array and we're going to write the block to the main block area。

 So we're going to go through the header array here again there are two elements。

 and we're going to write x prime and y prime back to the disk。 So at that point。

 we actually write it to the main area here。 So I'm going to update it by indicating a prime here and a prime there。

 So now the main block area has the updated versions of both X and y。

And then we update the counter to zero and write the header to disk。

So I suppose I could show that here as well。 We change that to 0。 So these are effectively。

Esed or not important anymore。 And then we write that block back here。

The data is still here in the log， but of course it's no longer needed。Okay。

 what happens if we have a crash and then we reboot？Well。The system begins by reading the log header。

 It doesn't know whether the previous session ended with a crash or not。

 So regardless of whether there was a crash in the past or not， whenever we boot the system。

 we begin by reading in the log header。If the counter is 0， then we do nothing。

 Any in progress transaction， if there was one that was lost because of a crash。

 will just be ignored。 So that transaction or that commit will not happen。

 and all the transactions that are involved in it will be essentially lost。 On the other hand。

 if it is non zero， then we have managed to。Do this。

 We have managed to write a header to the disk at this point。

 So we need to replay the log and make sure that everything got written to the main block area。

 And that's what we do here。 We go through the array and for each element in it。

 we write from the log area back to the main block area。 So I've already， let's go back here。

 and say that we have a crash。 Okay， so the count is still 2， and we still have 103 and 106。

 in this header。 So we read in the header。 and we find out that it is not 0。 So at that point。

 we need to replay the log。 So we'll go through and for each one of these。

 we'll read in this block here and write it to the appropriate place in the main block area。

And then once we've done that。We can set into0 and write the header back out to disk with the0。

The commit operation is done in several different functions。 I'll just mention them， commit。

Right log， there's a right head， and then there's an install trans or install transaction。

The stuff that happens on the reboot。 Well， we initially execute this knit log function that will initialize the variables of the log。

And that's called from FS andt file System and， that's called in the En process as one of the first things it does the first time it has a time slice。

And it will invoke recover from log， install trans， and it also calls read head and write head。Okay。

 I think we're ready to take a look at the code next。The file log at C begins with a comment。

 and then it gets into the data definitions。This structure called log header is what I showed right here with n plus the array。

 So here we see a field in， and we see the array。 Lo's eyes is a fixed。

 constant parameter It tells how big to make the log。

All of the variables associated with the logging are contained in this structure called log。

 And there's exactly one instance of this structure also called log。

And we see a number of different things。 We see a spin lock that protects these two fields outstanding and committing。

 And then we see start and size， which tell where on the disk the log will occur。

These are constants and they don't change。And we see a field called device。

 typicallyyp we'll have several devices and each will have a separate log in XV6。

 we only have one device， so yet we still have this field here。呃，你。

Outstanding field is a counter every time we do a begin operation that counters increment。

 and every time we do an end operation that counters decremented， and if it's zero， we do a commit。

If we are in the middle of committing， the committing flag will be set to true。

 and it will cause other begin operations to wait。And finally。

 we have an instance of the log header structure itself。Right here。Okay。

 now let's take a look at the ant log function。 This is called on kernel startup。In particular。

 is's called from this function FS and it， which itself is called from forcrret。

 the first time that Forcrt returns。We're going to be accessing the disk possibly if we do some recovery and that might involve sleeping。

 so we need to be running in a user process， so that's why we are doing this from within for Gr。

The first thing we do is initialize the spin lock called block。

 and then we initialize the fixed fields， the start， size， and device fields。

We are past the device number of which we are initializing。

 as well as a pointer to the super blocklock。Previous， the super block has been read in。

 and here we just pick up values from the super block to initialize the start and size fields。

 and we initialize the device field。And then finally， we call recover from log。

This will read the header block in。 And if n is non zero， it will do the recovery stuff。Okay。

 let's take a look at the begin operation function。

 This is called at the beginning of every transaction。

 This is called at the start of every file system system call。 Well。

 every file system system call is a single transaction。 So that's why it says that。Essentially。

 what it does is it increments this outstanding counter to indicate that yet another transaction is in progress。

This counter is protected by a spin lock。 And here we acquire that spin lock。

 And after we do the increment， we release the spin lock and we return。 We break out of this s。

 and then return。But before we can increment the counter， we need to perform a couple of checks。

First， we check to see whether some other thread is in the middle of committing。 and if so。

 we go to sleep。The first argument to the sleep function is the channel， and we use as a channel。

 the address of the log structure itself。 And， of course。

 the second argument is the spin lock that will be temporarily released while we are asleep and reacquired once we are reawakened。

So if nobody's committing， then we make a check to make sure that there is enough space in the log for the blocks that will be involved in this transaction。

 So we look at the current value of n and we have this parameter max op blocks。

 which happens to be 10。 and that's the maximum number of blocks that any transaction is allowed to update。

 So we look at how many transactions are currently in progress plus this current transaction that we're trying to start and we figure that they might all use the maximum number and we're asking whether that would exceed the size of the log。

 And if so， again， we go to sleep and we use the address of the log structure as the channel。

And after somebody commits， after some other thread commits， will get reawakened。

 And if both those are okay。 In other words， if both those tests are false。

 then we can go ahead and increment the outstanding counter in return。After we wake up。

 we will basically meet to check and make sure that both these conditions are true。

 just because we've been reawakened， we don't know exactly what's true and what's not true。

 So once we wake up from either these two sleeps， this while loop will repeat and we won't be incrementing the outstanding unless we pass this test and this test while holding the lock。

 And if we pass both of these， then we can go ahead and increment the outstanding counter and release the lock and return。

Now let's take a look at this function， logrightite， which is past a pointer to a buffer。

In the comment here， we have an example。We would first call B read with a block number to read in the data from the disk。

 and that gives us a pointer to a buffer。 Then we modify the data in that buffer。 And after that。

 we call this function log right to write it out to the disk。 It doesn't actually do the right。

 but it schedules it。 We might do some more modification and call logright again， But ultimately。

 we need to release this buffer， and we call be release。

 So the caller has modified the data in the buffer and is done。

 We record the block number in the log， and we also pin this buffer。

 We do that by increasing the reference count for this buffer。 We saw that in the previous video。

 And then the commit operation later， we'll actually perform the right to the disk。

So here's the code。 We're going to be modifying the log， so we need to acquire the spin lock。

 and we acquire that here。 and then before we return， we release the spin lock。

We do a couple of checks first。 We make sure that we have enough room in the log。

 We've already checked that with the begin operation。

 but we do another check right here to make sure that we have enough room in the log。

And we also make sure that we are in the middle of some transaction。

The begin operation will have increment this counter and we make sure that it's not zero。

So everything's okay， then we scan through the array looking to see whether we've got。

An entry in the array that happens to match this particular block number。 So from 0 to in -1， we ask。

 is the array， Does the array contain an entry that has the block that we are currently looking at。

 And if so， we set I to that。 Otherwise， we set I to n。 That is we exit when I becomes equal to n。

 That's the next available entry。Then we update the array， Okay， if I comes if we didn't find it。

 then I is equal to n。 so we update the next available entry by storing the block number。

 if we already found it， then we just overwrite it so that doesn't really do anything。

If I is equal to n， then that means we did not find it。

 and we're adding a new entry at the element at the end of the array， so we need to increment n。

 and we also invoke buffer pin on this particular buffer to make sure that we will not reuse this buffer for some other block until after it's been written to the disk。

And then again， we release the spin lock in return。Here's the function end operation。

 it's called at the end of each file system system call that is it's called at the end of every transaction。

 and if this is the last transaction and there are no other outstanding transactions。

 then it will perform the commit operation。So we have this counter outstanding。

 which tells how many transactions are currently in progress， and we are decrementing it right here。

 This counter and the committing flag are both protected by the lock。

 So we acquire the spin lock here， and then we will release it down here。

If the outstanding counter goes to 0 after we decrement it。

 then we need to go ahead and do the commit。 Okay， but we better not already be doing a commit because this transaction was in progress up until this point。

 So we do a little error check here to make sure we aren't committing already。

 But if the outstanding counter is decrement it to 0。 Then we set this do commit flag。 right。

 That's a local variable here。 do commit。 And we check it down here。 And if it's true。

 we'll execute this code。And we also set the committing flag so that we know so that other threads will know that we are committing。

However， if we did not go to 0， then it means there are other transactions still running。

 and there may also be transactions that are waiting for enough log space to begin。

 so there could be threads that are in the begin operation that are sleeping。

 So we do a wake up here to wake up any sleeping begin operations。

We check to make sure that there's enough reserve log space based on how many transactions are in action。

 And since we are now finished with this transaction。

 it means that we no longer have to reserve additional log space。

 and it may be that there's enough log space for one of these transactions to begin。

 So that's why we're calling wakeake up here。And then， we release the lock。Now。

 if we need to do a commit， then we are going to call this commit function。

 which I'll talk about in just one second。 and then we're going to clear the committing flag after it completes。

 We have to reacquire the lock and then release it。In order to modify this flag。 And again。

 we also call the wake up function to wake up any begin operations that happen to be sleeping。Okay。

 here is the commit function。 It's called from exactly one place。

 and it first checked the counter in。 Now， presumably there were some rights in this transaction。

 and it will be greater than zero。 But if it happens to be the case that there were no calls to the write log。

 the log write function， then this would be zero and we don't need to do anything。

So here we're going to call the right log function。Previous， I talked about the log right function。

 it's a little bit confusing， but the right log function， which is right here。

 is only called from this one place。That will write all the blocks from the buffer cash to the log area on the disk。

And then we call this function right head， which will copy the header structure to the disk block where it's in the log file on the disk。

 and that performs the commit after this completes。

 then this transaction or all of these transactions are committed and even if we crash directly after that。

 the log will be replayed and we will do the rights to the disk。

 if we crash before this right head completes， then it will be as if no transactions have occurred。

Then we call install transaction， and that will run through the log。

 and it will write each block to the actual location in the main block area of the disk。

And then we set in to 0 in the in memory， copy of the log header structure。

 and then write that log header structure back to the disk。

 And that essentially sits in on the disk back to 0。 And at that point， the commit is done。 But now。

 let's look at this right log function。 And as I said， it's called only from here in commit。

What it's going to do is go through the array in the header。 Okay。

 so we're going to go through this array here from 0 on up to in -1。 And for each one of those。

 we are going to。Write it to the log area of the desk。 Okay， so we're going to。Right。

From the buffer cash。 Okay， so， for example，1，03 is the first one we look at。 We're going。

 we've got that。 It's pinned。 Okay， so it will be in the cache。

 and we're going to write it to this location here。 And that's what's going on here。

 So the first call。 well， let's look at this call。From， that's the from location。 And we are。

Looking at the log。 Okay， here's the array and tail is our index。

 And we will find it in the cache because it was pinned。 Okay。

 And so this just gives us a pointer to the buffer。Okay， it doesn't actually read from the disk。

This read function right here is needed because we are going to do a write Every call to be write needs to be preceded by a B read to get the buffer。

 so here we are asking using the index tail here for the block number in the log area。

 so that will give us the block number in this case，01，2，3 for this particular block。

 and we will read it in although that's not really。I suppose could be optimized in some other kernel。

And then we're going to be writing it here。 So before we write it， we move all of the data from the。

Buffffer that came out of the cache。 Okay， to this new buffer that we just got。 Okay。

 and so we move an entire block into the two buffer， and then we write it to the log area。

 And then we release both buffer， both the cache buffer and the cache。

 and we created a new buffer in the cache for this particular writing operation。

 and we release that as well。So to review the commit function， we are going to write the log。

 That is we are going to take every block that is indicated by the array。 In this case。

 we have two of them。 and then we're going to copy that data， two blocks on the desk in the log area。

And then in the second step， we are going to write the header。

 So we copy this data structure here to this block here。Then we do the install transaction function。

 which will go ahead and perform the rights to the main block area。

Then we set in to 0 and write the header a second time。

So let's take a look at the right head function。Here it is。

 And essentially what it's going to do is write the in memory log header to the disk。

The comment says this is the true point at which the current transaction commits。 Well。

 that applies to the first use of right head here， but I don't think it really applies to the second use。

 but in any case， what it's going to do is get a buffer for the appropriate block on the disk， okay。

 loggged dot start。 That's this block number here， it would be 0，1，2。 It would be two。

And once we have a buffer pointed to by buff， we're going to copy the。

In and copy the array into that buffer。 And then we're going to write it and release the buffer。

So more precisely， we're calling B read to read in this disk block into a buffer。

 So it's going to actually read this into some buffer in the buffer cache。

 We don't really need to perform that read。 and perhaps some other kernels could optimize that away。

 But in any case， Then we get a pointer into the data of that buffer。 Okay， into the。

Block part of that buffer， and we treat that as a pointer to one of these log header structures。

 and then we're going to copy first we copy in from the in memoryory log header to this area in the buffer。

 and then we go through the array up to n minus-1 and copy from the log header structure here to the buffer that we have just allocated。

 and we write the buffer and release the buffer。Now let's take a look at this install transaction function。

It says copy committed blocks from the log to their home location。 So what it's going to do。

 it's going to go through the array， the header array here。

 And for each block in the log like this one right here。

 it will copy it to its home location in the main block area。

 and then it will do the next block and so on。This function is called in two places。

 It's called when the commit happens， and it's called at start up。 Okay。

 so if we are calling it during the commit operation from the commit function。

 recovering will be false。 If we're calling it on start up， recovering will be true。Okay。

 so here's what it's going to do。 We assume we've already read in the log header structure that iss in memory at this point。

And we go through the array from 0 to in -1 with the index tail。

 and we are going to read a block from the log。 Okay。

 so here we're using the start of the log plus the index plus one for the header block Okay so that's where we're computing the block number here。

 So the first one would be this block number here。And we are reading it in from the disc。

Into a buffer。 And then we are going to be writing to a location on disk。

 So we need to have a B read for that。 And that's what the second B read does。

 It is reading from the disk。 And where is it reading from。 Well we go to the log header。

 and we use tail as an index into the array。 Okay， so we use tail into as an index。

 and we find out the block number 103 in this case。

 And so we're going to get a buffer for this particular block。

And then we will move a block of data that in our case， it's 1024 bys。From the log block， Okay。

 L Buff to the buffer that's going to be written out， the Dbuff。Okay， and then we write the debu。

And if we are called from commit， then we know that this。Particular buffer。Okay， has been pinned。

 so we need to unpin it。Okay， if we are recovering after a crash， then it won't have been pinned。

 So we do not call the unpinned function。 But in either case， we release both these two buffers。Now。

 I should add that when we perform this first read here， we are reading from this here。

That may actually still be in the。Ber cash， okay， it's not this one right here because this one points to this block number。

Okay， this buffer points to this block number， but in order to write this。

 we had another buffer here in the buffer cache for this particular block。

 So it may be that this B read here doesn't actually do a disc read。嗯。Here， in this case。

 we have to call B read before we can call B right。 And so this will read in an entire block。Okay。

 so when we are preparing to write to this block here， we first called B read for 103。

 and that's what's happening here。Now let's take a look at what happens on startup。

The function and it log is called as part of the very first time slice。

 and it runs as part of a user mode process。It begins by initializing the spin log that protects our log variables and initializing several constants that won't change after this。

 And then it called this function， recover from log。 So what's recover from log going to do。

It's going to begin by reading the log header from disk and moving it to the in memory copy。

 And then it's going to check in。 if it's 0， then it indicates there's nothing in the log area。

 and we can proceed immediately。 But if it is greater than 0。As in this example， it's too。

 it indicates that the log area contains a transaction that hasn't been completely finished。

 So it will go through the array。 And for each element。

 it will read a block from the log area and write it to the appropriate location in the main block area。

 And so it will do that for each of the blocks and update the main block area。And finally。

 it will set into0 and then write the log header back to disk， thereby essentially clearing it。Now。

 it may be that the crash occurred in the middle of committing a transaction and some of these blocks have already been written to the main block area。

 but this recover from log will repeat that work。 It won't matter that we read this block and write it a second time to the main block area。

So let's take a look at recover from log， and here it is。It begins by calling Rehead。

 and then it calls install trans with the recovering argument set to one to indicate that we're being called as part of the start up and not as part of a commit。

 Then it sets into 0 and writes the log header structure back to disk。Let's take a look at Readhead。

 that's right here， and it's going to read the log header from disk into the in memoryory log header structure。

And so， it has a。Read here。 And it's providing the address or the block number， I should say。

 of the log header。 That's the start of the log， which is in our example is 2。

 So it reads from this block into some buffer。 And that is a pointer to the buffer。

And then we get a pointer to the data area in that buffer L H's pointer with C data is an array。

 So this expression here is just equivalent to the address of the first element of the array。

And so that's where we're going to be copying from。 And we're copying into the log header。

 the in memory copy of the log header。 So we first copy in from the buffer L H into the log header。

 and then we go through the array and copy each of the array elements from the buffer to the log header that's in memory。

If in0， we don't do any work。 So we only copy as many as is necessary。 And finally。

 we release this buffer。Now， we could consider just using a memory move function call to do this copying。

 And in that case， we would be copying from the buffer to the in memoryory log header area。

 and we're copying the entire structure。 That is we would copy the entire array。 But normally。

 the previous session will not have ended with a crash。 So in will normally be 0。

 So we really only need to copy in in most cases and can skip copying the array。Okay。

 so now let's take a look at in。Recover from log。 we read the header。

 and then we call install trans so we can take a look at that again。

 And we have this recovering argument that will be set to true if we are being called on startup。

And again， what it does is it reads from the log area on desk and it writes to， okay。

 here's the right the buff。 it writes to whatever address， the array tells us to write2。

 So here we're going into the log header and into the array。

 This is our tail is our index from 0 to n -1 in this array。

 and we are looking at the array to find the address。 Okay， so first， we would find 103。

 and that tells us we want to write to 103。 So we get a buffer for block number 103。

 and then we write to that block。 first， we move the entire data block 1024 bytes from the buffer that we just read in L buff。

 Okay， to the destination buffer。 and then we write Now the recovering here will be true on。

Startup so we will not need to unpin the buffer recall that these buffers in the buffer cache when we first read in the old value of block 103 into the buffer we pin it okay and so if we are in the middle of a commit。

 we need to do the unpin but on recovery， these blocks in the buffer are not pinned so we don't do the unpin and then finally we release both of these buffers so that they could be reused in some way。

Now。So I think we've looked at everything， but I wanted to make one comment。

 this knit log function called Recover from Lo。Recover from log is only called from that one place。

 and it consists of four lines， pretty short。And it calls readhead。

 Readhead is only called from this particular location。 And again， it is quite short。

 So we could consider doing some inlining。 We could take all of this code here and move it into the recover from log function and or we could take the recover from log function and move it directly into the in log function。

Recover from log is pretty short， and it's only four lines。 So I would prefer to in my。

 if I were writing this code， I would do the in lighting。

 I think that I might also consider inlining Readhead as well。

 The resulting function in it log would then be still well less than a page。

It's an aesthetic question and it kind of depends on how you feel about things。

 you could make the argument that recover from log is a separate enough function。

 separate enough operation， it's a discrete and different operation。

 so it makes sense to pull it out and put it in its own function and document it separately。

The argument that I would make is that every time you have a separate function introduced。

 it requires a little extra effort， a little extra mental effort， not much， but a little bit。

If you were to approach this code without having seen it before and are trying to read it and you encounter some function like this。

 you have to say， well， where is this thing called from， And oh it called this function here。

 where is that。 So you have a little bit of extra mental effort， not much but a little bit。

 you've got to go find where readhead is， So you got to shuffle through some pages or whatever and locate it。

 But more importantly， when you're looking at a function， you have to ask， where is it called from。

 So if I see recover from log， I it called， where is it called from。

 So that requires a little bit of a search， Okay， and then you might find out that it's only called from one place。

 readhead， it's not clear at all that it's called from only one place So you might spend some time trying to search for where else it is being used。

These are minor things， and again it's an aesthetic question。The code in log do C is fairly complex。

 and what it does is fairly complex。 but I think we've gone through all of this file。

 And so I can say thanks for watching。 I'll see you in the next video。



![](img/46c888c8ad76322da5c207a052a57417_2.png)