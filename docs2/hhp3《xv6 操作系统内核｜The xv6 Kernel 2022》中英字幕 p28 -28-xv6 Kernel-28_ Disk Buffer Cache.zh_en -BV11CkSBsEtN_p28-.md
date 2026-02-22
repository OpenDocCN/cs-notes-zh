# hhp3《xv6 操作系统内核｜The xv6 Kernel 2022》中英字幕 p28 -28-xv6 Kernel-28_ Disk Buffer Cache.zh_en -BV11CkSBsEtN_p28-

![](img/a3c1f69fad30553f4540596461cfbedd_0.png)

In this and the next couple of videos， I'll be describing how the UniX file system is implemented。

 and I'll talk about the system calls like open， close， read， and writeite。

This video is part of a playlist on the X V6 operating system kernel。

 X V6 is a simplified version of Unix。There's a lot of complexity here。

 and in a complex software system， we can start by describing the low level functions first and then gradually work our way up to the higher level functions。

In another approach， we can start with the high level functions and describe those first。

 followed by successive levels of greater detail。 I will go with the first approach and talk about the low level functions first。

In this video， I'll be talking about the disk system and how we interface to the disk。

 and I'll talk about the buffer caching system。I'll cover the code in files Buff。

h and buffer Iio or BIO。c。So let's begin by talking about the desk。

Whenever we transfer data to or from main memory， it's in units of bytes or words。

With a disk were transferring units in terms of a larger than called a block。

The block is a fixed size chunk of bys。 In the case of X V 6， our block size is 1024。

 and that's fixed by this constant B size。 Other systems like units use a different block size。

 but in X V 6。Or in any， any operating system， the block size is always fixed。Now。

 the disk is viewed as nothing more than a numbered sequence of blocks。

 So the blocks are numbered from 0，1，2 on up to some maximum。The second block。

 that is the block numbered one is special， And it contains something called the super block。

 The super block is fixed and doesn't change， and it contains a number of parameters。

 One of the parameters contained in the super block is the size or the number of blocks on the disk。

And so we can read that and know how many blocks are being available on this disk for the file system to be stored in。

The disk actually may read or write bytes in another unit called the sector。

 So block and sector are sometimes used synonymously， but they really are different things。

 General speaking， the sector size is a bit smaller than the block。A typical example is that in UniX。

 the block size is 4K，4096。Well， individual discs may have a smaller sector size。

One particular model of disk might have a sector size of 512。

 while some other kind of disk might have a different sector size。

But by having the operating system work in terms of blocks。

 we can ignore the different sector sizes of the individual models of disk drive。

Whenever the colonel wants to read or write from the disk， it reads or writes an entire block。

 and that will cause the reading or writing of a number of sectors by the device drivers。

 For example， if the sector size of one particular disk drive is 512。

 Then every time the colonel does a reader or write， it will transfer 4096 bytes。

 and that will cause the reading or the writing of well 8 sectors。On a disk。

 which is a rotational device， we have a number of different delays。

 We may have to move the head at the readr head in or out to other tracks。

 And we may also have to wait for the disk to rotate so that the indicated data。

 the desired sector is underneath the readwr head。By grouping sectors into a block。

 we can make sure that whatever we read， most of the sectors are read sequentially。

 We have to do a seat to the proper track and proper spot on the track。To read the first sector。

 but the remaining seven sectors will be read sequentially， which improves performance quite a bit。

Of course， there's a penalty。 in many cases， the last block in a file will only be partially filled。

 and the minimum file size will be the block size 4096， so we could have some wasted space。

 but we do have an increase in performance。Now， the device that is implemented by Kimu is the vert Iio disk device。

Remember that X36 will be emulated by something called the chu emulator。

 and the chu em emulator will interface to a vert I O disk。

This vert IO stuff is an attempt to standardize the interface between device drivers and actual hardware。

 and there are a number of different interfaces is Vert IO disk and USB and UR and some other stuff that are not used by the XV6 system。

But。Kma will provide an interface to something called the Vert I O disk。

 I won't go over it in this video， but the thing we need to be concerned about is that the disk driver provides one function that can be used for the read and the write operations。

So this function， which is called vert Iio disk Read， write， can either perform a read or a write。

 And which of those it does， is determined by the second argument。

And the first argument is a pointer to a buffer。The buffer is an example or an instance of a buff structure。

and。One of these buffers will contain enough space for the block， in our case， 1024 bys。

 as well as the particular number of the block that we want to read or write。

It contains some other stuff as well。Now， with the vert I Odes and the X 6 system。

 there is no error reporting。This function does not return anything。 and if any errors should occur。

 then they would be maped and taken care of in these in this function。 For example。

 if there's a read failure， a check some failure or something。

 the sector or entire block would be read reread until we finally can get the data。In the emulator。

 of course， the disk is emulated with a file on the host system。

 so there's probably not really going to be any errors anyway， but in any case。

 this function has no error reporting。The function may sleep。 For example。

 if we want to read a buffer， this function will start the read operation going。

 and then it will go to sleep。Somewhere else， there is a trap handler。

 so when the operation is complete， the disc will cause a trap and the handler for the disk will become active。

 and among other things it will wake up this function。At that point。

 the process that had invoked the read or or the write operation will be reawakened and will return。

So in almost all cases， this function will sleep。Another thing that's important to remember or to know is that。

This function will not reorder the operations。It will do them in exactly the order in which this function was called。

 and we'll see later that that's important when it comes to atomic transactions。 but for now。

 just remember that it does the operations in the order in which the function is involved。Now。

 this buffer that's pointed to here is an instance of a structure called Buff。And。

These structures are used as a cache for blocks on the desk。

There are a fixed number of buffers that are pre allocated at kernelel start up time。

 and that's controlled by this constant in bumpuff。 Turns out we have exactly 30 buffers。

That can contain data and each one has enough space for exactly one block of data， in our case。

 of course， it's 1024 bytes。In addition， we have the block number for which this particular block of data is a cache。

 So which block on the disk is held in the buffer。And there's some other variables。

 some other fields that are used for synchronization。 we'll get to those in a second。

The buffers can either be free or in use。 So we have a free list of buffers and buffers that are not free are in use。

In this diagram， I'm showing how the buffers are organized。

 They are organized in a circular linked list。Circular linked lists are also called doubly linked lists。

 So here we have individual buffer structures， and one is special， and that is the head of the list。

It will not contain any other data， it's just used for its next and previous pointers。

 so I've indicated that with an x。Then we have the buffers in the cache。

 we have 30 buffers in the cash， I'm only shown four here for simplicity。

These are organized from most recently used to least recently used。

 so we can locate the most recently used by following the head pointer or sorry。

 the next pointer of the head， and we can locate the least recently used by following the previous pointer in the head。

With a circular linked list， we can easily remove an element， for example。

 we can remove this element and move it to the front of a list if it is now to be the most recently used element。

So let's take a look at the detail of what's in these buffers， and I'm showing that here。

We see the next pointer and the previous pointer。Here we have a reference count。

If the reference count as 0， it means this buffer is not currently in use， and it can be recycled。

 if you will， or used for something else。But if it's greater than zero。

 then we can't use it for anything else。 The block number shows which block is represented in the data portion down here we have space for the entire block of 1024 bytes and block number here is the number of which block is being stored here。

The device number is right here in XV6， we just have a single disk device。

 so we don't really see much change in that， it's more or less constantsonant of one。

 but in a more complex Uni system it wouldn't be the case。We also have a ballot field。

 and that indicates whether the data field contains the data from the disk or whether it contains garbage。

 whether it doesn't contain that and if it doesn't contain it， well。

 of course we need to read it in from the disk if we want to use that data。

We also have a field called disk， which is used entirely within the disk driver。 In other words。

 it's only used in the vert I O disk rewrite function。

 so we don't really need to think too much about it。

 but basically tells whether a disk operation is currently in progress or not。

And we have a sleep block， which will protect the data as well as the valid bit and the disc bit。

Now here is where we allocate the buffers， so we have a structure called Bc with three fields。

 The first field is a spin lock called lock， and the second field is called head。

 and that contains an entire buffer structure which I've shown here。

So when we refer to the head structure， we can just refer to it as bcash。head。

We can also refer to the lock as Bc do lock okay， and then the third field is an array。 In our case。

 we have 30 elements in this array， and these are the buffers。We do not access this array directly。

 instead we go through the pointers here from the head element。

The array is there to allocate the buffers and its only accessed during initialization when we build the initial circular linked list。

So all 30 buffers are always on this list， although from time to time。

 we will remove one and insert it at a different location。The spinlock is protecting the。

Linkked less， essentially， Okay， it's protecting the fields。

 Next previous Ref count da and block number。 So every time we want to allocate a buffer or release a buffer。

 we will need to acquire the spin lock， which we can refer to as。Bcash dot lock。

So now let's take a look at the file Buff。 H， which contains nothing more than the definition of the Buff structure。

 and I'll try to line these up here， I showedd the fields in an order that makes sense to me。

 but you can see it's the same set of fields， so we see that next and the previous fields pointing to other buff structures。

We see the reference count， we see the device number。

 we see the block number here we see the sleep lock and the valid flag and the disc flag。

 and then here we see the。Block of data， the 1024 byte area， it will contain the block。

Now let's talk about the file bufferio。c， and we'll start with the definition of this structure called BCash。

 and I showed that right here。So you can see it's exactly the same we have the spin lock。

We have the array of， in our case 30 buffers shown right here。

 and then we have the head buffer structure， and these are not pointers。

 but these structures are just included directly。I want to also just read the comment that occurs at the top of this file because I think it's useful。

The buffer cache is a linked list of bus structures holding the cached copies of disk block contents。

Caashching the disc blocks in memory will reduce the number of disk reads and also provides a synchronization point for blocks that are used by multiple processes。

And here's the important point， the interface。In order to get a buffer for a particular disc block。

We should call the function， B， read。And after changing the data in that buffer。

 we can call Bright to write it back out to disk。And we can continue to use it。

 But when we're done using the data in that buffer， when we're done using the buffer itself。

 we should call this function B release。And then we should not use the buffer after we release it。

And only one process at a time can use a buffer， and so we need to remember not to hold them for longer than necessary。

Okay， let's then move on to the initialization function。So let's look at this function B in it。

 which is called during kernel startup。It initializes the。Ber cash lock。 That's the spin lock。

And then it creates a linked list of the buffers， that is it establishes this circular linked list。

It starts by creating an empty linked list where the head points。

 the previous pointer and the next pointer， both point to the head itself。

 And then it goes through the array。 So here we're going through the buff array from the zero element all the way up to the 29th element one by one。

 And for each one of them， we are initializing the sleep block in that。Buffer structure。 Okay。

 and we're also adding it to the linked list。 So I can just show this really quickly by。

Simulating it or doing the instructions one by one。

 So we've got a link list here that points to some， here's the head。 And we've got some list so far。

 We've got a new structure。 B that we want to add。 So we're going to make the next pointer。

 point to the head dot next。 Head dot next is this one。 So we make our next pointer。Po。Here。

 like that。And then the next thing we do is we make our next pointer point to the head。 Sorry。

 whoops， we make our previous pointer point to the head。 So here we are doing that。 Okay。

 and then in the next step， we make the thing that the head is point to next。

 which is this element here。 We make its previous pointer point to B。 Okay。

 so I'll do that by rerouting this pointer like that。

And then we make the heads next pointer point to B。 so we route that。To here。 So at that point。

 we've added this into the linked list。By the way， there are several fields in the bus structure that are used。

 but not initialized。 the reference count， the device number and the block number。

 it turns out are initialized implicitly to zero， and we will rely on that initialization。

Now let's take a look at the B read function。 This is coming out of the buffer Iio。 C file。

This will return a locked buffer with the contents of the indicated disc block in that buffer。Okay。

 it's going to search the cache。 And if we find that we already have a buffer containing that disk block。

 then we'll return that。 Otherwise， we're going to allocate a new buffer and read in the data from the disk into the block before returning。

And before we return， we will grab the sleep block for this buffer。

 and well also increment the reference count for that buffer。

A reference counter of 0 indicates that a particular buffer is free and available for reuse。

 But if the reference counter is greater than 0， then that buffer is in use。

This function is past the device number and block number。That we want to get。

 So the device number in X V 6 doesn't change。 It's always one。

 but the block number tells which block on the disk we want to read in。 So this function will first。

 call be get。Bigge will search the circular linked list of buffers to see whether we already have a cached copy of this particular block。

 And if so， it will return a pointer to that buffer。 But if we don't already have one。

 then Bigge will return a pointer to a newly allocated buffer。 In other words。

 itll find a free buffer with reference counter0 and return a pointer to that。In either case。

 it will increment the reference count and grab the lock。

 So now we have a buffer with a reference count incremented and the sleep lock set。

Then we look at the valid flag。 If we found an existing copy in the cache of the right block。

 then valid will be set to true。 But if we had to allocate a new buffer， then valid will be false。

 So we need to read in the value。 We need to read in the block from the disk。

 So here we call vert I O disk， readwrite。This parameter 0 indicates that we want to be doing a read。

 and we pass it a pointer to B， which will already have the device and block number filled in by the bege function。

And then we set the valid flag to one after that and return a pointer to the buffer。Okay。

 now let's take a look at the B get function。This is going to first。

 look through the buffer cache to see whether we already have a block with the right data in it。

 And if we do， and we're going to return a pointer to that buffer。 But if we don't。

 we're going to allocate a free buffer。 So in other case， in either case。

 we are going to return a pointer to a buffer， which will be locked and which will have its reference count increment。

So here we are past the device and the block number to indicate which block we need to read in。

 and we return a pointer to the buffer that we have read that data into or maybe not read。

 that might not be valid。So we acquire the lock。 Okay。

 we're going to be accessing this circular linked list here。

 we're showing the next and previous pointers and the reference count。

 and these are protected by the spin lock in B cash。

We're only going to be reading the next and previous pointers。

 but when fields are protected by a lock， we need to grab that lock and acquire it。

 even though we're only reading it。The reference count， we will be both reading and modifying。

So here we acquire the lock。 and you can see before we return， whether it's we release the lock。

 whether we return here， Okay， we release the lock， or if we return down here， we release the lock。

 If there's an error， we don't really worry too much about it。Okay， in the first loop。

 what we're doing is we're going through the circular list in the forward order so you can see we're following the next pointer。

We're starting with the first element in the list。 In other words。

 we look at the head element and follow its next pointer。

 and we keep going until we wrap around and get to the head again。

And what we're doing is we're asking， is this buffer a match， In other words。

 does its device and block number match the device and block number that we are searching for。

 And if so， we' found an existing copy of that buffer。

 And so we've got the data already in the cache。 We increment the reference count and of course。

 release the lock in Bc。 And then finally， we acquire the lock that's in this particular buffer and return the pointer to the buffer。

😊，Now， I should point out right here that I mentioned earlier that the device。

 block number and reference count fields are implicitly initialized to 0。

 and we don't actually do that explicitly when we initialize things at the very beginning and be a it。

 And this is why， because we are reading these things before they ever get initialized。😊。

So we are assuming there's zero to start with， and we never look for block number zero on device number zero。

Okay， if we search the list and we don't find a match。

 then we need to grab a buffer that's currently unused。 So we're going to look through the list for。

A buffer with reference count0。 Remember that a reference count of 0 means that it's free。However。

 we are going to use the list in the reverse order。 We're going to search using the previous field。

 So we're searching it in the reverse order。 We're starting with the head's previous pointer。

 and then we keep going until we wrap around and reach the head again。Okay。

 and if we find one with the reference count of zero and we're going to grab it， we're going to。

Change its device and block number to the device and block number that we're searching for。

 And since it may contain data from some other disk block。

 we will set it's valid to0 and we will essentially initialize its reference count to one。

 which is nothing more than actually incrementing it from 0 and finally release the lock on the Bc and then acquire the sleep block for the buffer itself before returning。

If we can't find any free buffer， we've got a problem。

 we have pre allocated enough buffer so this should never happen。 but if it were to。

 we would have an error message here。Now， I just want to point out when you're maintaining a least recently used list。

 we can do it sort of a couple of ways， every time we use something。

 we can move it to the front of the list。Or every time we're done using it。

 we could move it to the rear of the list and。Actually。

 S uses the latter approach Every time we're done with a buffer。

 That is every time we release the buffer， we will remove it from wherever it is on the list。

 and we will move it to the tail of the list。 That's why we don't see any change in the position of the buffer on the list with this。

 But later， we'll see in the B release function that we move it to the tail of the list。Now。

 let's take a look at the B right function。 It's past a pointer to a buffer。

 and it will write the contents of the block in that buffer back to its location on the desk。

Every buffer that we write to the disk must first be acquired by a call to the B read function。

 So at this point， this buffer will have its device and block number fields set。

 as well as the 1024 bys of data in the block。And furthermore。

 the B read function will always return a buffer that is locked。

 So we check to make sure that we are actually holding the lock on this buffer and if not print an error message。

Then we call the vert I O disk readwr function with an argument of one here to perform the right operation。

 This will invoke the disk driver function that will write the block in that buffer back to disk。

 and it won't return until after that diskrite is complete at which time Bewright returns。Now。

 the way we use buffers is we first always call be read。

 and that will get the data from the disk into the buffer。 So at this point。

 the buffer will be locked and its device and block number will be set， and it will contain data。

 Then we can modify some or all of the bytes in that block and then invoke be right to write the modified block back to disk。

We can then modify some more bytes in that buffer and call Bright another time。

 and we can keep doing this because as you can see。

 the B right function doesn't release the buffer itself。So when we get ready to release the buffer。

 we call this function B release。And。Since that buffer will have been acquired with a call to be read。

 we had better be holding the lock on it。 Okay， so we first check to make sure we are， in fact。

 holding the sleep lock on that buffer。 And then we release that lock。

Then we decrement the reference count and check to see what it's gone to 0。Now。

 every time we access the reference count or the previous or next field， as we will do here。

 we need to be holding the B cash lock。 Remember that the B cash lock in my picture here。

Protectt these fields。 So we need to grab that lock first， and we do that。At this point here。

 and then subsequently， we will release the Bc lock here。At this point， after getting the lock。

 we decrement the reference count。If it's now 0， then this buffer is free。

 It's not in use by anybody。 It still contains the data from that particular block。

 and the device and block number fields are still accurate， along with the valid flag。

 So it might be that a future call to B read will be able to reuse it。But on the other hand。

 a future call to B read might actually need this buffer for a different block and will not use the existing data。

So if it's gone to  zero， then it's no longer in use。 and it's now the least recently used buffer。

 So with these statements here， we modify the next in previous fields of this。

Buffffer as well as the head buffer。 And I won't go over those in detail。 But basically。

 what we're doing is we're taking the buffer， delinking it from where it is。

 and then moving it to the end that is the least recently used end of this circular linked list。

I just want to comment here that the the comment that you see here move to the head of the most recently used list。

 I feel is completely wrong。 and I should say， move it to the tail of that list。So at this point。

 the buffers released and B released returns。Now there are two other functions that are of interest that we can cover right now。



![](img/a3c1f69fad30553f4540596461cfbedd_2.png)

The pin and unpin functions， which will pin a buffer or unpin the buffer by pinning it。

 All we're doing is we're incrementing the reference count and unpinning it is decrementing the reference count。

Whenever we have a buffer that we want to make sure doesn't get released prematurely。

 we can call this B pin function to increment the reference count。

 And then when we're done with that buffer， and we want to allow it to be released by others。

 then we can decrement the reference count。In order to modify the reference count。

 we must be holding the B cash lock。 So you can see we acquire and release it here。

 and we acquire and release it here as well。Okay， that's it for the buffer functions。

 And I will see you in the next video。

![](img/a3c1f69fad30553f4540596461cfbedd_4.png)