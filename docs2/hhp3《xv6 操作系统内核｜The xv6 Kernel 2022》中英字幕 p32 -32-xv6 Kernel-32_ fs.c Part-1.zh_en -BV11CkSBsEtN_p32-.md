# hhp3《xv6 操作系统内核｜The xv6 Kernel 2022》中英字幕 p32 -32-xv6 Kernel-32_ fs.c Part-1.zh_en -BV11CkSBsEtN_p32-

![](img/f494b40042117d97dc83af82abaa6a30_0.png)

This video is part of a series on the XV6 operating system kernelel。😊，In this video。

 I will cover the functions and walk through the code in the file， FS do C。

There are a large number of functions， and I've broken this into two separate videos。

 each is about 45 minutes long。 And this is the first video in that series。In the previous video。

 I introduced the data structures and gave a summary outline of the functions。

 and in this video I'll go over the code in the functions。

 But here let me just review this list These are the functions that I will be covering in this video and I just will present this material here on the screen so you can have a reference as to what is covered in this video。

 These functions are all covered。Bmap I will cover in part 2。However， in this video。

 I will cover eye trunk and stat I， and then the other functions。

 read eye and so on will be covered in the next video。And in the next video， we will end up。

Talking about the main function， name I， which is sort of what we're working toward。

 it's past a pointer to a path name string， and it figures out which file on the disk that is and returns a pointer to a9ode representing that file。

Okay， let's get going。Let's start with the functions that are involved with initialization。

 So here's the main function。 This is from file main dot C。 And recall that it attests the core。

 and all of these functions are executed on core0。 That is they're executed only once。

 and these functions are executed by the other cores。 And after all of this， we start scheduling。😊。

Right here， we see B in it， which initializes the data that's associated with the buffers。

 And then we call I anit。Remember that the iode cache consists of an array happens to have 50 structures in it。

 and the structures are i nodes， and there is one spin lock that protects the entire array。

 and each structure has its own sleep block called lock。So here is the code for I Anneette。

And you see， we're initializing the one lock that's associated with the eye table。

 And then we're going through the entire array right here and initializing each of the sleep locks。

These structures also have a reference count。 and if this is zero。

 that indicates that this element is unused and available for use in the future。

 and the reference field is initialized to zero by default。Great， going back to Maine。

We see a call to file in it this， I haven't talked about this yet。

 but essentially this initializes a lock as well。And we do submit initialization related to the device。

And then we create the init process。 So here we create the first user process。 And at some point。

 we will start scheduling。 Okay， and one of the cores will pick up this process and we'll begin the very first time slice。

 We can't do any diso until we are actually running in a user process because the diso stuff needs to sleep。

 So let's take a look at what happens when Enit is first executed。 Well。

 remember that forkret from the file proc dot C。😊，Will be called to schedule the first time slice。

And it contains this code here that asks whether this is the first time it's ever been called， right。

 There's this local variable。 there's a static variable。 It's initialized to true。

 And so the first time this function is called by any process， It will execute this code here。

 and then set first to 0。 And what does that do， Well， it calls F S a net。

 So let's take a look at F S and net。Now we're running inside of a process， and here is FSNE。



![](img/f494b40042117d97dc83af82abaa6a30_2.png)

Oh shows read S B2。 The first thing it does is it calls read S B。

 which will read in the super block from the desk。So here we see a call to B read。

 and this will be the first read we do and sets BPp to point to the buffer， and then it moves data。

From the buffer and how much does it move， Well， the size of this super block structure。

 and it moves it into this super block structure。 we're passing at the address of that super blocklock structure。

 and then we release that buffer。 So after this point here。

 we have the super block variables stored in that super block structure。

 and we can access things like the magic field。 So we immediately check it to make sure that the device contains a file system of the type that we are expecting that the file system has been properly initialized and so on。

And then， we call a knit。Log， and I discussed the logging system in a previous video。

 But this is where that gets called。 So after this， we can create transactions。 That is。

 we can call begin op and end op and log， write。Next， let's take a look at the function B Alc。

 Every time we create or grow a regular file or a disk file。

 we need to find an unused block on the desk and zero it out and then add up to the file。

 So B Al is called to allocate and 0 out a disk block and it will return the number of the block that it found。

 So basically， it's going to search through the bitm for an unused block。

 Remember that our bitm here can， in general， consists of several blocks。😊，Okay。

 with only a tiny disk with 100 blocks in it， it'll only have one block。 But in general。

 this code will search a number of blocks。 Okay， so this code can accommodate a much larger disk， so。

It's got， let's look at the structure of this thing。 It's got two nested four loops。 Okay。

 and the first one will go through the blocks。 And for each block in the bit map。

 it will read that block。 And then the next loop will go through all the bits in the block。

 looking for one that is free。 Okay， so here， this outer loop has an index variable of B。

 And it's being incremented by the number of bits in a block。 Well therere 1024 Bs with 8 B each。

 So it's B goes from 0。 and then 8 K and then 16 K and so on。 Okay， so each one of these will。

Be a block。 And the first thing it does is it reads that block in from the device， okay。

Dis function B block is past a block number， as well as a pointer to the super block。

 and it will figure out which block on disk contains that bit。 So we read the first block。

 and then the second block using the bit at the beginning of the block as the index here。

This inner loop runs through the bits within that block。 So it goes from 0 up to 81918191。

 So it that's this loop index here。 It's incrent by one。 However。

 so the actual bit that we're looking at is this number plus the index within the within the block。

 and that's B plus B。 And of course we also stop if we hit the size of the disk。

 if we search through all of the bits in the bit map up to。 well， in this case。

 we have only 1000 blocks。 So if we search up to this point without finding anything。

 then we immediately aort and that causes us to panic and say that we're out of blocks that the disk is full。

 There are no free blocks。So once we have a bit number within the block。 That's B I。

 we need to figure out which bit within the word or within the byte， I should say。

 So we are using mod 8 to figure out which bit within the byte and divide by8 to figure out which by within the block。

 So here we create a mask， all0 is except for 1，1 B in the appropriate position。

 And so that's our mask。 and it's a byte， although it's declared as a 32 bit value。

 we are only concerned about the 8 bits in it。 And then we here we are looking at one individual byte and ending it with the mask to look at one particular bit。

 And if that is 0， then this indicates it's a free block。 Okay。

0 is used to indicate free and the one bit is used to indicate in use。 So if we find a free block。

 then the first thing we do is we set the bit。 So here we're。

Taking the same word and we're oing it with a mask to set that one bit to a one。

And then we are writing the block back。 We've changed this one block in the bitmap。

 so we need to write it back to the disc。And we do that here。 And then we release that block。

 And finally， we zero that block， so。嗯。Here， we are。Using B plus B。

 that's the actual block number that we found that is free。

 So we're passing this block number to the B0 function。 And then we return the block number here。

 And I just want to say that after we've searched this entire block and not found any free bits then we release that block and we move on to the next block in the bitmap。

 So this B0 function is right here。 It's only called from the B ac where I just showed you。

 And so you can more or less forget about it after this。

 but what it does is it is past the block number。 And it reads that block。

 getting a buffer pointer to the buffer that contains that data。 And here we are updating the data。

 And in fact， we're using this function MIet to move a bunch of zeros。 How many zeros。 Well。

 the block size is 1024。 So we're moving that many0 bytes into this data area。

And then we're writing that block back to the disk。And finally， we're releasing that buffer。 Now。

 so these functions here are calling be read， log write and B release。 Okay。

 so that means they must be within a transaction。 So we'll see that all of the functions in this file here。

 are。😊，Supposed to be in a transaction。 They will call， be read and log， write and。

We assume that all of this is happening within some transaction。

 So this code outside of the file FS dot C will begin the transaction and then call these functions or some of these functions and then ultimately call the end op function to terminate the transaction。

As a professor， I can't help but insert a little commentary at this point。

This algorithm is pretty straightforward and easy to understand， and for our purposes of XV6。

 it's adequate， but I have some questions about efficiency。For one thing。

 it's searching every bit in the block one by one。 so this inner loop is executing 8 k times and for its execution。

 it's building this mask and then doing a little bit of computation。Now， when we allocate a block。

 we need to search through all the bits until we find a bit that is 0。

 And so we might have a bunch of blocks that are in use。

 So we go through a bunch of bits that are one。1 approach would be to look at entire words at a time rather than individual bits at a time。

 So the idea is that we would have a loop that would loop through all the words in the block。

 and it would look at each word and ask， is this word equal to a word with all one bits。And if it is。

 then it doesn't contain any0 bits。 So there are no free blocks represented by that word。

 so we can move on to the next word。 So it searches word by word instead of bit by bit。

 And then when we finally find a word that is not all ones， it must contain a0 bit。 So at that point。

 we search the word and find out which block is actually free。But still， there's a problem。

 This is doing a linear search。 If the disk is almost entirely full。

 we have to search through the entire bitmap。 and for large devices， that could be time consuming。

 So we don't really like to do linear searches in the first place。

 I want to just mention another approach to managing free lists。

 So the idea is that we keep a linked list of pointers。

 And so each one of these structures represents a block on disk。 Okay。

 and each block contains 256 words， shall we say the first word points to the next block in the linked list。

 And the remaining words in the block， point to free blocks。 so in order to get a free block。

 we go to this linked list。 and maybe these have been allocated。

 but here' is the first block so we can allocate that one。

And that's pretty quick because we just keep a pointer。 It's a stack。 Basically。

 when we return blocks to the free pool， we push onto this stack。 And then when we allocate blocks。

 we pop off of this stack。 And then when we get to the end。 Okay， after we allocate this block。

 the next allocate， well， we just allocate this block itself， the entire block。

 And now this block becomes the head of the list。 And we begin with our stack pointer here。

 And when we want to allocate a block， we allocate this one and then this one， and then this one。

These blocks will be kept on disk。 And you you can see that the these are each one of these requires a block。

 but we have a bunch of free blocks anyway。 So it's not really a cost to store this link list on disk as we consume。

Blocks as blocks are allocated， we consume the blocks that are used for the linked list as well。

 And we would also like to keep one or two of these blocks in memory to make this process faster。

 So we can keep allocating here。 we can allocate this block and then we can allocate this block and we can keep going。

 But at some point， we have to read in the next block from disk and likewise。

 when we're returning blocks， we can fill up this block。 and after this block is completely full。

 well， we need to write this one back to disk。 and we just have returning a block so we actually have a place to write it。

 So we have a slightly complicated algorithm。 but it's going be much more efficient because returning a block we'll normally involve just writing a number into this and advancing the stack pointer and allocating a block will be just grabbing the next element on this and decrementing。

Or increasing the stock pointer。The one aspect of the free block being kept as a bid map is from time to time。

 you want to allocate a number of blocks， and you want them to be close together on the disk。

 For example， when we allocate the blocks for a file。

 we would like all those blocks to be close together because if one is read。

 it's quite likely that the others will be needed as well。

This approach here doesn't really deal with that。 whereas with a bitmap。

 if you're trying to allocate， let's say 10 blocks altogether。

 then you can search the bitmap for a place where you find 100 bits。

 that is 10 free blocks altogether。 And so there， you know， we can go down a rabbit hole here。

 But I just want to point out that this code is simple and easy to understand and adequate for the X V 6 teaching kernel。

 But in reality， things are going to get quite a bit more complicated。

So now let's turn to looking at the corresponding free routine。From time to time， files are deleted。

 or their size is reduced， and we need to return the blocks in the file to the free pool。

 And for that， we have the B free function。When we allocate a block from the free pool。

 we have to search the bitmap to find an unused block。 But when we free a block。

 we just need to find the corresponding bit in the bitmap and change it。

So Beery has passed the block number。And it calls B block with that block number to determine which block in the bitmap will contain the corresponding bit for that block。

And then we read that block from the bitmap area into a buffer。

 and here we compute the bit within that block。 So this is bits per block。

 and we use the mod operator to figure out a number between 0 and 81，9，1 within that block。

Then we use the mod and the divide operator to figure out which bit within a byte and which by within the block。

 So here we are making a mask， all zeros except for a single one bit in the corresponding position using the modD operator and here we are figuring out which byte within the data block will contain that bit。

 and we're looking at that。 So we're ending it with the mask to determine the value of the bit。

0 is used to indicate free。 And if it's already0， we've got a problem。 So we panic。 but otherwise。

 we set the same by by ending it with the knot of the masks。 right。

 So we turn all the0 bits into one。 And so that preserves them。

 But the bit that we're interested in here turns into a0。 and by ending it， we clear it。

 So this sets the or I should say， clears the bit that we're interested in to 0。

 And then we write that buffer back to disk and release the buffer。Next。

 I want to talk about the I get and the I put functions。

 as well as the I lock and I unlock functions。Whenever we want to access an existing file。

 we'll call I get and Ilock。 And then when we're done with it， we'll call unlock and I put。

So I get is past an in number， as well as the device in which we want to find this file。

 and it returns a pointer to that iode in the cache。

 So it will look in the cache to see if we already have that in open， if you will。 And if we do。

 we'll use that one。 Otherwise， it will allocate a new entry in the cache and devote it to storing that particular in。

 but in any case， it will increment the reference count to indicate that that structure in the cache is used for that particular in。

It won't read in the eye note from disk， and it won't lock the eye note to do that。 we call I lock。

 which will lock the node。 And then if it has not yet been read in from the desk。

 it will go ahead and read it in。So then when we're done using this particular in。

 we call unlock and it will unlock the node and we can call i put Okay i put will decrement the reference count。

 So if it was already there， when we call I get， we incremented the reference count。

 And then when we're done with it。 we call I put and it decrements the reference count。

 and it checks to see whether we have no more hard links to it。 And if so it it gets rid of the file。

 But otherwise， the file will stay in the cache。 if it decremented the reference count to0。

 then that node in the or that structure in the cache is now available for reuse。

 But if there are other users of the iode in the cache， then the reference count will not yet be0。

 and it will persist for the other users。 So let's first take a look at the get function。

 which is here， I get。Finally， I note with the number I numb on this particular device and return the in memory copy。

 Okay， but it will not lock that， and it will not necessarily read it in from disk， okay， so。

In order to access the iode cache， we need to lock the i table lock。

 And then we have a loop that's going to search the。Cched i nodes。 So here we start with 0。

 and we go all the way up through all 50 of them。 And we look at each one of them。

 So what we're doing here。Is in this picture， we're acquiring this spin lock。

 And then we're going through all 50 of these structures。 And we're looking for one that。

Matches the device and I number。Okay， so we're looking for one that in this loop。

We are looking for one。Whose device matches， the device we're on and whose I number matches。

 And we're looking for something that is not free。 So if it's the reference count is greater than 0。

 then we've got one。 and we increment the reference count。

 and we release the lock and return a pointer to that I note。 Okay， but we might not find one。

 So as we go through all 50 of these structures， we look for one that has a reference count of 0。

 And if so we save a pointer to that one in this variable empty。 And here。

 we're checking to see whether we've already found one。 And we only save the first one。And then。

We exit this loop if we haven't found one， and we are recycling or allocating a new entry in the cache for this particular i note。

Okay， so we make sure we have enough， we actually found one。

 otherwise we've run out of inots in our cache and that's cause for panic。But if we find one。

 then we are pointing to it。 And then we set its device and I number to indicate that it's in use。

 and we said it's reference count also to indicate it's in use。 So now we have allocated it。

And we said it's valid to zero。 Now， previously， I said that the valid field was protected by the sleep lock of the structure itself。

 So this sleep lock called lock here protects everything below it， including the valid field。

So is this cool that we're modifying the valid without holding the sleep block on this？Well。

 we are the only process that is accessing this eye note。 Okay。

 because the reference count is one here， we just set it to one， and we are holding the I table lock。

 So no other process could conceivably get a pointer to this particular cache because the reference count is protected by the lock。

 So setting ballot to 0 here is safe。Okay， next， let's look at the lock function。

 the I lock function。So it's past a pointer to one of these cached iode structures。

And it is making sure that the reference count is really one or greater。 And if not， it panics。 Okay。

 now we are going to modify the fields of it。 So we need to begin by acquiring the sleep block。

 and this will。Lock it。 And once we've gotten the sleep block。We check the valid bit。

 If the valid flag indicates that we have not yet read the data in from disk。

 then we need to do that。 So here we call B read。And we're reading from the device and the call to eye block。

 which I should have bolded here， is called to compute which block on the disk。

 this i number the iode is kept in。 and then we read that block。

 And here what we're doing is we're moving everything from the iode structure in that block into the。

Cched version pointed to by I。 So we are getting a pointer to the iode in the block。

 So here we're accessing the data of the block， and we're figuring out exactly where in that block。

 This particular i note is stored。 This is i nodes per block。 So we're figuring out that。

 So back in this picture， we're just basically computing where in the block。 we need to read from。

And that's the pointer for the source， and then we're copying the type major minor in link size field。

 as well as the address right here， okay so here we're copying the address field from DIP to the cache copy and finally we're releasing the buffer that we use to read in the iodeode from disk and setting the valid flag to true and we're also making sure that the type that we just read in is not zero we shouldn't be reading in a iode that's not allocated。

Okay， so unlocklock is pretty straightforward， the I unlock functions past a pointer to one of these cache i noteses。

And it just releases the sleep lock。 Okay， it does a little checking here to make sure that we have a pointer and we're actually holding the sleep lock and the reference count can't be 0。

 We better be referring to it。 And so then we release the sleep lock。 So next。

 let's take a look at the eye could function。Okay， remember what the I function is going to do。

 it's going to decrement the reference count。 and if that reference count is now zero。

 that means no other processes are using the cached copy and the number of hard links to this file is0。

 then we're going to eliminate the file。 we're going to truncate it to link0 that it's type to0 and update everything on the desk and finally unlock the iode with a reference count of0 that the cache structure will now be free to be reused for some other in。

So let's take a look at the I put function。 When a process is done with a file。

 it's done with the cached copy of the in and we need to allow other processes to use the memory and the cache for other iNots。

 So let me read this。 what we're going to do is drop a reference to an inmemory cached copy of an in。

 if that was the last reference。 then the cached space， the space in the cache can be recycled。

 And furthermore， if that was the last hard link to the file。 then this in is not reachable。

 and so we need to free both the in and all of its data and its block of indirect as well if it has one。

So as is true of all the functions in this FS do C file， this function must be inside a transaction。

 Okay， so I's past a pointer to the cache copy of the i note and it's going to acquire a lock on the cache because we're going to be modifying the reference count。

 So the way this is actually organized is a bit different than I showed in my out in my handwritten stuff。

 we have the if statement first followed by the decrement of the reference count。

 and then we release the lock on the cache。The reason we won a decrement at last is because if it turns out we're going to be deleting this file。

 we want to maintain a reference count of one， so here we're looking to see whether we have a reference count of one that is we are the last process that is accessing this cache copy of the iNot and if that's the case and the number of hard links is zero。

Then we can go ahead and delete the file Okay so we will be truncating it to length0 and setting its type to0 in in order to modify the type。

 we need to be holding this iodes sleep block。 So here we acquire the sleep block。

 And here we release the sleep block。 And then we call i trunk which will look at this iode and it will look at all the data blocks it points to either directly or indirectly。

 and it will eliminate all of those， or I should say it will return those to the free pool and update the bitmap and so on。

 and then we set its type to0， So that makes it an unused in previously its type was either regular file directory or device And by setting its type to0。

 we indicate that it is free， but this is the inmemory cache version。

 So here we write that to the disk。 So at this point， we are updating。

D and now that I know that's stored on the disc will also have a type code of0。

 and we then we set the valid bit to zero so。Now。Here we are releasing the lock for the cash and then reacquiring it right here。

 We need to be holdingen the lock for the cash before we access the reference count。

 so we need to reacquire it if we release it。 Why do we release it。Well， as far as I can tell。

 there's not a deadlock concern。 We're not releasing it for that reason。 And I think we could。

 it would be legal or valid or correct to just hold on to this lock。 know， after all。

 we've acquire this log and this lock。 and we're not acquiring any more locks。

 We can release this log here or not， but there's no problem with holding on to it。

 as far as I can tell。 But it's if we do release it， we need to reacquire it， Of course。

 but it's just a question of politeness。 Okay， we're going to be calling I trunk。

 and that's going to be doing some disk rights or more precisely。

 it's going to be calling log rightite and Bread。 which will need to allocate buffers and modify the log and so on。

 could end the update。 It's the same thing。 We're going to be calling log rightite to update the log file。

 All of this stuff could take a little while。 The cache of inots。I's somewhat of a bottleneck。

It could be that the cache holds the iodes for some very important and popular files。

 And so we'd like to release this spin lock as soon as we can。 I think that's why it's released here。

 But then， of course， it's reacquired。Now， then we have a question of why is valid being set to 0 here。

 We've already set type to 0， which indicates that the s node is unused。But if you look right here。

 there's a moment of vulnerability。 Okay， we've released the spin lock and we've released the sleep lock。

 So at this point right here， we're not holding any locks。And we haven't looked at ialoc yet。

 But what ialc is going to do is look on the disk and find an iode whose type is0。

 And so it might find this very iod， the i with the same number that we just wrote out here。

 and it might say， okay， I'm going to recycle that for some other file。And then what。

It will do is call I get to see if there's already a cached version in memory。Okay。

 and so there is a cached version in memory。 So we need to make sure that it doesn't get used。

 So that is。Why we need to set valid to0 right here。 Okay， the reference count is still one。

 So when we look for it in the cache in the cache， Ialc will find it or it might find it and try to reuse the cached version。

 Well， the cached version is not correct。 Ialc will have modified the type on the disk and it needs to read that back in so that the type in memory is also adjusted。

And we can't do that here because we don't know what the type is。

 So I think that's why we are setting valid to false right here。 So I hope that explains I put。

The other function we have down here is called I unlock put。

 and all it does is unlock an iode and call put。 So it's very common that after we've modified or used a file。

 we are ready to both unlock its iode and get rid of our reference to it。 We're all done with it。

 So this is a common idiom。Next， let's take a look at the Ialc function。

 This is called whenever we want to create a file and we pass it the device。

 it indicates where we want to create the file and the type， which will either be a regular file。

 a directory file or a device type。And what this will do is find an unused iNote on the device and market it allocated by setting its type field to whatever we were past here。

And then it will call I get here to return a cached copy of that iode。Okay。

 so let's go through the code here。 We are going to loop through all possible I numbers。

 We skip 0 because 0 is not a valid I number。 And so we go from one all the way up to our maximum number。

 In our example， we have 199 possible i node。 So we loop from  one to 199。And for each one of those。

 we need to read it from desk。 Okay， so we'll call B read。I block is past the eye number。

 and it will determine which block this Iode is stored on。 So the first one。

 number one will be stored on this block， which happens to be block 32。

 And so we'll use block 32 for several， and then we'll go to block 33 and so on。

So then we compute once B reader returns， it has a pointer to the buffer that we've read in。

 and we then figure out where in that buffer we can find this particular i note so。

Here's the pointer to the data of the buffer。 and we take the i number modulo， the inots per block。

 And that tells where in the buffer， we could find the on this data for this iode。

 And then we look at its type field。 And if that's0。 then we found one that's free。 if it's not0。

 then we release this buffer and loop back to the next i number and called B read again。 Now。

 most likely， when we call Bread the next time。 the block that we need is just sitting in the buffer cache。

 Okay， we just read it previously for the iode before this。

 and this new iode is probably on the same block。 So we don't actually do a disc read for most of them。

 So we just loop through the i notess in one block。

 eventually we hope to find one that has a type of0。 if we don't。And we get all the way up to 199。

 then we'll exit this loop and panic that we have are already allocated as many files as we possibly can。

 I think earlier I said we have a maximum of 200 files， but since we don't use zero。

 we have a maximum of 199 files。Okay， so let's say we find an iode with type equal to 0。

 Then what we're going to do here is zero out all the fields in the iode on disk。

 So we copy zeros into this buffer。 And here we're doing that。 This is the size of。

This is the size of the iode on disk。 And then we set the type field to whatever argument we were passed。

 and we write that buffer back to disk and release it。

 And now that we've got the iode updated on disk。 we call I get。

 and it I get will look through the cache and find an empty slot for this iode。

 And then it will fill in the device and i number， as well as setting the reference count to1。

 and it will return a pointer to this in memory cached version of the iode。

 the valid flag will still be 0， because we set it to0 earlier。

 And so unused entries in the cache we'll have a valid a flag being equal to 0 and。

And when we call lock， when we call IL， we will go ahead and read the data in。

From disk and copy it into this area。诶。😊，I， Aec is only called from the create system call， and。

That system call will immediately call IL， so it will read the data from the disk。 Okay。

 and it will copy it into the cached structure。And since the block is probably still sitting in the buffer。

 it won't involve a second read of the disc。Whenever we update the eyeode associated with any file。

 we need to write those changes back to the disk。 And that's the function of the I update function。

 So it's past a pointer to some cached iode， and it will write it to disk。

 So copy a modified in memory cache version of an iode back to the disk。

 It must be called after every change to a field in the iode that is stored on the disk。And。

The collar of this function had better be holding the sleep lock associated with this。 I knowed。

So we saw that this was called in the I put routine。 So here's the I put routine。

 Remember we if we're going to delete the file， we set its type to0 and then immediately write that to disk。

 So here's an example where we call I update。The code is pretty straightforward。

 first we invoke i blocklock， giving it the I number of this particular iode and it computes which block contains that iode。

 and then we read that block from disk into a buffer。

Then we compute where in that buffer we can find this particular i node。

 so we take the i number mod the i nodes per block and then add that as an offset to where the data is for that block。

And that gives us a pointer to into the buffer。 And so then we set the type， the major， the minor。

 the in link and the size， right， we set the type major minor in link and size。 And then we set the。

Address array。 so we copy it from the cached copy in the i table cache。 Okay。

 so we're copying it from this area here into the buffer。

 and then we'll write the buffer back to disk。 So that's what we're doing with these copies。

 and here we're copying the address array。 The size of this array is 13。

 That is the number of direct pointers plus one more。And then we write that buffer back to memory。

And。Release the buffer。From time to time， we need to truncate a file to link zero。

 that is we need to get rid of all of its data。One place we do this is in the I put function。

So here's the Iput function， and if we've determined that the number of hard links to this file is zero。

 we're going to go ahead and delete the file， so we call I trunk or I trunknk it here。

 and then we go ahead and set the type to0 and so on。

Another place that IT is called is in the open system call code。

 we have the option there of truncadating the file to length zero。

So let's take a look at what this file does。The collar must hold the sleep block on the cached version of the iode。

 So it's past a pointer to the iode。 It's cached， and it's going to go through that iode。

 and look at all the data blocks it points to。 So here's the picture。

 It's past a pointer to one of the cached copies。 and it's going to go through this array here。

 and let me use this array up here because it has the blocks。

 So we're going to go through the direct pointers。 And if they are non-ze。

 we're going to call be free to return this block to the free pool。

 And then we're going to go through the block of indirect pointers。So that's what's happening here。

 We go through the direct pointers。 all in our case， we have 12 of them and so it from 0 to 11。

 and we look at each entry in the array in this i note and if it is nonzero。

 then it has a pointer and so we need to call be free using that block number and what this will do is update the bitmap to change the bit for this block from one meaning in use to0。

 meaning free。 and then we zero out the element in the array。

 And so after we've done all the direct pointers， we need to ask whether there is a。

Block of indirect pointers。 So we ask whether this pointer here is0 or not。 And then if it is not0。

 we need to read this block and they can go through all of these pointers for each one of these and then free the block itself。

So that's what's happening here。Is the last element。 Okay， that's the 13th element。

 or we have 12 direct pointers。 So element number 12， which is the 13th element of the array。

 If it is non-zero， then we have an indirect block。

 So here we call B read to read that indirect block into some buffer and here we find where in that buffer the data is actually stored okay。

 and that we will consider it to be an array。 it's considered to be this array here。

 and we're going to index through it。 So in this loop here， we are indexing from0 up to well。

 in our case， we have we go from 0 to 255 and we look at each element in the array and ask if it's non-zero or not。

 And if there is a pointer there。 then we call be free providing that block number and that will free the block so。

We go through this array。One by one and three these blocks。And then finally。

 we release the buffer that contains the indirect block。 Okay， that's this buffer。

 And then we need to free that。Block itself。 So again。

 here is the address or the block number of the indirect block。

 And we just call be free with that block number to free the indirect block。

 and we set the final element of the array to 0。Then we set the size in the iode to0。

 and we update the cache version of the iodeode by copying it back to disk。Okay。

 we've also got this function here， Stat I， which is simply going to copy some information from a cached in to someplace else。

 okay， so we've got a stat structure and we assume that we are holding the lock on the cached in because we are reading the fields in that cached in and we're just copying them into this stat structure。

Okay， we've just covered about half of the functions in the file FS。c。

 and the remaining functions will be covered in the next video， so I'll see you there。

