# hhp3《xv6 操作系统内核｜The xv6 Kernel 2022》中英字幕 p33 -33-xv6 Kernel-33_ fs.c Part-2.zh_en -BV11CkSBsEtN_p33-

![](img/0c1a668e6ba52a6bdf58861be50a0635_0.png)

This video is part of a series on the XB6 operating system kernelel。In an earlier video。

 I described the iode system and talked about the general organization of the file。 F S do C。

 I talked about the data structures， and I gave an overview of all of the functions in that file。

In the previous video to this video， I started walking through the code of the functions that are in F S dot C。

 And in this video， I will finish walking through those functions。

 Let me just put on the screen for a visual reference。

 What functions were covered in the previous video。 So we covered all these functions。😊。

And here are some more that we covered。I will start with B map in this video。

 But in the previous video， I covered eye trunk and stat I。 After I talk about B map。

 I will go ahead and talk about the remaining functions starting with read eye and so on。

And as I said， we are working toward the name。I function。

 and I will end by talking about the name I function。

 which is the function that has passed a pointer to a string that contains a path and will find that file on the disk and read an eye note into the in memoryory cache and return a pointer to that。

So let's get started。From time to time， we want to read data from or write data to a file。

 and we need to know where on disk that data is stored。

 so which block number on disk do we need to read or write to get the data。

And that's the function of this B map function。 It's past a file or more precisely a point to some I note describing the file。

 as well as the block number relative to the beginning of the file。

 So let's say we want to write some bytes in。 Well， let's say the seventh block in the file。

 We need to convert that seventh block number into the actual block number on disk。

 Re the disc block address of the inth block in the file。

And if that block has not been allocated to the file。

 then this function will allocate and 0 a new block。So looking at the picture here。

 what we are going to do， let's say we want to get the seventh block we'll need to go to the cache in let me use this picture over here because it's got the indirect block and if it's in one of the first 12 blocks。

 we just need to access the in and get the block number。

And find out where on disk that block is stored， if it's greater than 12 here， if it's 12 or greater。

 we need to access the indirect block and get the block number from the indirect array。

So that's what we are doing here。First， we're asking whether the block number that we're looking for is less than。

 well，12。 That is， if it's 0 through 11。 In that case， we can use one of the direct pointers。

 So we are going to look into the i note and the array and get the element from that array and save it and then return it。

 Okay， if that。Aray contains a zero pointer。 Then that block hasn't been allocated。

 So we need to call B ac。We will allocate or find a free block and set it to all zeros and return the block number on disk。

 which we will then store into the array so that it will be there in the future and in either case we return the block number。

However， if the block that we're looking for is 12 or greater。

 then we are going to need to follow this pointer and look in the indirect block。 So， for example。

 if we're looking for block number。14。 Well， this is 12，1314。 It's this one。

 We need to take the block number 14 and subtract off these first 12 to get an index into this array。

 That is we need the index of 2。 So that's what's happening in this line here。

 We're subtracting off 12 from the block number。 And now we've got an index that's between 0 and 255。

 Or at least we hope it is， the first thing we do is checked to make sure that our index is not larger than 255。

 And if it is， well， we've tried to access a block that is beyond the maximum file size。

 that should have been checked by whoever calls this function。 And if not， we issue a panic。

So then we need to load the indirect block， and。We then go to the array。

 and this is the last element of the array， and ask whether it's 0 or not。 If it is 0。

 then we need to allocate the block of indirect pointers。

 So here we allocate that indirect block and set it all to zeros and we save the block number of the indirect block in the array。

 So we're allocating this block here and saving a pointer in this element here。And that happens here。

 and we， in either case， we get to the address of the indirect block。

 and here we are reading the indirect block。Into some buffer and setting a to point to where that data is in that buffer。

 So that's the beginning of this array。 And then we're using our value here to index into that array。

 and we are saving the element。 So that's the block number that we're interested in。 And if it's no。

 then that block hasn't been allocated So we have to call Balc again。

 to allocate a block and set it to zero。 and we will store the block address of the freshly allocated block into the array。

 And we need to update the indirect block if we have modified it。

 So that's where we have a log right here。 But otherwise， we don't need to update the indirect block。

 we just use the address that we retrieved and return that。

 So here we are releasing the indirect block or more precisely releasing the buffer that contains the block of indirect pointers。

Now， you can see that we are modifying the i note here。 Okay。

 we could be modifying the array directly either here or here。 And so if we are modifying it。

 we need to update the i note on disk。 So that's the responsibility of a color of Bmap。

 So let's keep that in mind。At some point we're going to want to transfer bytes from the file to memory。

 and that's the purpose of the readI function。 so it's going to read data from the file that's described by the iodeode pointed to by IP。

We're going to get the data from this offset within the file and we're going to transfer in bytes。

 We're going to move those into memory and the address that we're going to move them to is given by the destination argument here。

 that could either be a virtual address or a physical address and that's determined by this argument here。

 If this argument is a one， then the destination address is an address in the virtual address space of the currently executing process。

If this is zero， then destination is a physical address in the kernel address space。

We begin with a couple of checks。 First， if the offset is beyond the end of the file。

 then we return 0。 By the way， this function returns the number of bytes successfully transferred。

This test here is written in an odd way。 if you subtract offset from both sides。

 you see that it's really just checking to see whether the number of bys that we want to transfer is less than 0。

 and if it is， again， we return 0。Offset may be within the file。

 but the extent of the amount of data that we're transferring may go beyond the end of the file。

 And if that's the case， then we need to reduce in so that we only transfer as many bytes as the file has。

 So here we compute the number of bytes between the offset and the end of the file。

 and that is our new in。So the invitetes that we want to transfer can be spread over several blocks in the file。

 and we need to read each block individually and get the bytes out of that block。

 and well so we'll call be read a number of times。 and for each one we' transfer using this either copy out function。

So this loop will transfer a number of bytes each time and then it will finally terminate and return the total number of bytes transferred。

 so we start total at zero and we end when we transfer in bytes and then we return the number of bytes that we've transferred。

So the first thing we need to do is figure out for this particular chunk for the next chunk。

 where it is in the file and where it is on the disk。

 So the current offset from which we're getting data is given by offset and as we go through we advance offset and will advance the destination pointer。

As we do each chunk， we'll compute the number of bytes we're going to transfer here。

 That's M and increment the。Sour the offset within the file。

 as well as the destination pointer and the number of bytes transferred。

So we take the offset where we're at right now and figure out what block it's in。

 So we compute the block number that contains offset right here and call Bmap。

 Bm will map this block number， which is relative to the beginning of the file into a block number on the disk。

 and then we call B read to read that into a buffer， which is pointed to by this buffer pointer here。

Now we figure out how many bytes we want to transfer in the next step。

 and so we don't want to go over the end of this block。

 we don't want to go past the end of this block。 So that's what we do here。

 We take the offset and see how much is left in this particular block with this expression here。

And we don't want to transfer bytes beyond what we're supposed to transfer。

 so we look at how many bytes we' transferred so far and subtract that from M and that's how many bytes we have left to transfer total。

 and we take the minimum of those two， and that will be the number of bytes we're going to transfer。

So then we call either copy out。 and we covered that earlier。 But basically。

 it's past a source address here。A number of bys to copy and a destination address。

 and then a flag to tell whether those。Bites will be copied into a user's virtual address space or into the kernel space into physical memory。

 so that's just the parameter that we had up here。OkayAnd we are copying M bytes and where we copying them from Well。

 we're copying here's the the data is in the buffer and we look at the offset and we figure out where that is so we offset into the buffer's data and that's where we begin copying our M bytes and destination is where we copy them two and if anything goes wrong。

 this function will return a minus1 and we immediately aboard that could be if the destination address is not actually in the user's virtual address space it's not an allocated page for example。

 that could cause a problem and if that's the case then we immediately release the buffer and return a minus1 and break out of here。

So it was set total of minus1 and then would turn out。But if the copy is okay， then we just continue。

 we release the buffer that we allocated here and then iterate and do the next chunk。

 we just copied M bytes so we add M to the total bytes we've copied so far as well as from the source address within the file that is the offset and the destination address where the bytes are being copied too。

Now， one thing I want to point out is we're calling BMap here， and as I mentioned earlier。

 BMap can modify the i nodes in memory。If the data is not allocated in the file， it will allocate it。

 so it may allocate new blocks and add them to the file， and that will modify the iode。

 And it is the responsibility of the color of Bmap to write that modified iode back to the disk And that doesn't happen here。

 And I think that is a bona fide bug in this code。 But you know。

 maybe maybe there's something I don't see。Yes， there definitely is something that I didn't see at first。

 After looking at this code， I've come to believe that it's just fine， as it is。In UniX。

 we have the F C system call， and if this is a file here。

 you can use F C to seek to a certain point beyond the current end of the file。

 and then you can do a right。The posic specification says that the bytes in between here that were never actually written will be initialized or assumed to be0 so that if later you go back and you do a read in this region here。

 the read system call should return the0 bytes that were supposed to be there。

I made the assumption that XV6 works the same way and that you could have these gaps like this。

 but in fact， that's not the case。In X V 6， there is no F C system call。

 So it's impossible to do something like this。 You cannot start writing beyond the end of the file。

 In fact， with X V 6， writing will always start at position 0。

 I suppose that if you don't want to start writing at position 0。

 you will have to do a bunch of reads to get to whichever position you'd like to start writing at。So。

 with X6。The blocks in the file are always allocated。 So let's assume that we have a file。

 and it goes from this point up to some size。 And so here's the file in blue。

 And what this means is that all the blocks。 and each one of these is supposed to be a block。

 will be allocated。 and the last block might not be fully used。

 but all the blocks in here will be allocated and none of the blocks beyond this point will be allocated。

 So that means that the read eye system call when it calls B map will only be reading blocks that are already in the file。

 And that means there will never be an update to the i note。

 So there's no reason or no necessity to call the I update function。Like there is in right。

 as we will see in a second。This points out that a lot of times we make assumptions about the code that we are either reading or writing。

 and these assumptions are often below the level of consciousness。

 We have these assumptions in the back of our mind， but they may not be clearly articulated。

If we want to prove in a mathematically strict way that the code is correct。

 then we may be required to make all of our assumptions explicit and write them down。Doing that。

 proving a program is correct and making all these assumptions explicit is an excellent way to find bugs。

 but with the X36 operating system kernel， we are not going to go into that level of analysis。Okay。

 so let's move on to the right eye function。

![](img/0c1a668e6ba52a6bdf58861be50a0635_2.png)

To write data to a file， we have the right eye function。

 so we will write data to the file that's described by this in and the color must hold a lock on that iode。

The data is coming from。Memory at the location given by this argument source。

 and that can either be a virtual address in the address space of the currently running process。

 or it can be a physical address in kernel space， as determined by this argument here。

We are placing the data in the file at the location given by this offset here and we'll be copying in bytes this function will return the number of bytes successfully written and it might be less than the requested in if there's an error of some kind。

So it's very similar， the code is very similar to the read eye function。

 we start off by asking whether the offset is beyond the end of the file and if so we return minus1 in this case。

And we also ask whether the number of bytes to be transferred is less than zero， and again。

 that's considered to be an error。So we return minus1 and we also ask whether we will be。

Going beyond the maximum file size。 So Max file is the maximum number of blocks in a file times the block size。

 And if offset plus n is greater than that， then we've got to return an error indication。

The loop here is roughly the same， as we saw in Re I。

 we're going to break the transfer into a number of chunks of size M。

And so we start with the total number of bytes transferred so far， that's zero。

 and we'll stop when we've transferred all in bytes and we'll ultimately return this total number。

And we compute the number of bytes we're going to transfer as M and in each generation of the loop we'll be adding M to the offset in the file that we're writing to as well as the source address where we're getting the bytes from and we'll increment the total number of bytes that we've written so far by M。

 and again， this is exactly the same as in ReadI， when you take the current offset in the file。

 figure out what block its in， called Bmap to determine the block number on disk and then call BRead to get that block into a buffer pointed to by BPP。

Then we compute M here we are limiting in if we are going past the total number of bytes we need to write。

 then we stop there and so n minus total is the number of bytes left to right so we don't want to write any more bytes than that and we also don't want to go beyond the end of this block so here we compute how many bytes are left。

From offset in this particular block。 And then we use the either copy in function， which will copy。

From this location and memory source， which is either in virtual ladder space or kernel ladder space。

 as given by this parameter here。And we'll copy in bytes sorry M bytes and where will we be copying them too Well。

 we've read in the buffer that contains the range of bytes that we are going to be writing to。

 and so here we compute where that is。 So here's the data in the buffer and here's the offset within that data and that's where we're moving data to。

 and after we copy the data from memory to the buffer。

 we need to write this buffer back to memory sorry back to the file。

 So here we invoke the log right function to do that。 and then we release the buffer。

If the either copy in function has a problem， it will return minus1 and we then release the buffer and break。

Now we need to update the size field， so here we are。Updating the size attribute of this file。

If the offset that we're at now， after we in this loop exceeds the current size of the file。

 and we need to grow the file， or at least make a note that the file has already grown。

 BMap will be the function that actually adds records or adds blocks to the file。So。

Rightrite the iode back to the disk， even if the size didn't change because the loop above might have called Bmap。

 or it did call Bmap。 and that Bm might have added a new block to the file and therefore modified the array of block pointers。

 So we do call I update here and finally， we return the total number of bytes。Transferred。Next。

 let's take a look at the directory look up function。

 It's passive directory or more precisely a pointer to a cached copy of the iode for that directory file and a pointer to a string。

And it looks that name up in the directory。 And if it defines it。

 it allocates a cached version of the iode for that file and returns a pointer to that。

It also has the capability of returning the offset within the directory at which it found this name。

 and that could be useful if， for example， we want to delete an entry from a directory。

So let me remind you what the directories look like。

We have this directory entry structure that's 16 B in length。It has two fields。

The Ium field is only two bys， and it has the I number of the file。

 And then we have 14 by for the name of the file。 If the name is shorter than 14 Bs。

 it will be followed by a null by。 And a directory is just a file that contains an array of these。

So here's an example directory， some of the entries will have an I number of zero and those are essentially unused entries in the directory。

 so this directory seems to have three files in it and so we have the file name if it's shorter than 14 characters it is followed by a null byte and if it is 14 characters then there is no null byte。

 but in any case theres the i number that's associated with these names for the ones that are zero we don't really care about what characters we have for the name。

Okay， so。What do we do in this function？First of all， we check the file that were passed。

 the directory to make sure that its type is， in fact。

 a directory and if not there's a serious problem。Then we're going to go through the file。

 So offset will start at 0， and it will be incremented by the size of these directory entries。

 So we have this local variable called D E directory entry。 and that's a 16 B value。

 And so we're going to increment the offset in units of 16。 So here， here， here。

And we're going to end when we get to the end of this file， the size of the directory file itself。

And for each iteration of the loop， what we're going to do is we're going to call the readdi function。

 So we're going to read from this directory file okay and where we're going to read。

 we're going to read from this offset and we're going to read， well it's 16。

 the directory entry is 16。 we're going to read 16 bytes and we're going to place those bytes in this DE variable here。

And we make sure that we got 16 bytes and if we didn't， well， something's really wrong， so we panic。

If the I number of this directory entry is 0， then we skip and go to the next one with a continue。

 Otherwise， we compare the name that were passed。 Okay， this string here。

 with the name in the directory entry and see whether they are equal。 So at this point。

 let me look at this name compare。 Okay， that's a little function here that is passed two strings and uses a string in compare to compare up to 14 characters。

 well， it will compares up to the first null byte and in any case， no more than 14 bytes。

And so if the name is equal， then we have found it， okay， the two names are equal。

 then we have the entry that we're looking for。 and so we grab the I number that's associated with it。

Also， if this P off。Argument is non null and we store the current offset of this directory entry。

In the variable that's pointed to here。And once we've gotten the I number for this entry。

 we then call IG。Recall that I get will allocate an iode in the cache of i nodes and it will initialize it with the appropriate device and I number。

 and from then on we can lock it if we want to， but at least we've got the pointer to we've got a pointer to the iode cache in memory。

If this loop goes all the way through and ultimately reaches the size of the directory file and still hasn't found a match。

 then we return zero to indicate that we haven't found anything。

So next we have the directory link function， which is used to add an entry to a directory。

It's past D P， which is appointed to the eye note for the directory。

 as well as the name and I number to be added to the directory。

It will return 0 if everything's okay and -1， if there's a problem。

The first thing it does is it calls directory lookup to determine whether this name is already in the directory。

If it finds something， then it will set IP2 point to the iodeode for that file。

 it will call I get to do that with indirectory lookup。If that's the case， then well。

 that's a problem， we need to return -1， but we are not interested in the file that we've already found。

 so we call I put to undo the I get， if you will。Then we look for an empty directory entry。

 so we're going to look through the directory file。

 starting with offset0 and incrementing by the size of these directory entries and we're going to stop when we get to the size of the file after we've looked at them all。

And for each offset。We will call readdi to get from the directory file， 16 bytes。

 and we'll transfer it from the current offset within the file to this D variable。

 this directory entry variable here is a local variable of 16 bytes， and that's in physical memory。

 not virtual letterer space。 So that's the flag 0 here for that。

And if for some reason we're unable to transfer the data， unable to transfer a full 16 bytes。

 then there's something dreadfully the matter， and we panic。But otherwise。

 we then check the directory entries I number to determine whether it's free。 if it's0。

 then we found a spot in the directory that we can use and we break with that offset。

 Otherwise we go all the way up to the end of the file and offset will be equal to the size of the file。

 because the size of the directories is a multiple of 16。 And in either case。

 we are now ready to create the directory entry and write it to the file。

 So here we are copying the name into the directory entry variable。

And we copy it up to 14 characters， and we copy the I number into the directory entry。

And then we write that directory ingue。 So we're writing it。Here's where we're writing。From。

 and this is an address in kernel space so the flag is 0。 and we're writing to the offset。

 This could be the offset of an entry that is unused or it could be an offset beyond the end of the file and it doesn't matter which this will grow the file if necessary。

 and so we write 16 bys that's the size of the directory entry。 if there's anything wrong。 we panic。

 but otherwise we're done and we return zero to indicate success。In order to open a file。

 we need to be able to deal with path names。The next function we want to look at is called skip element。

This is purely a string processing function and helps us parse a path name。

 It doesn't involve iodes at all。It's past a pointer to a string containing a path name。

 such as this one right here， and it will identify the first file name in that path and advance the pointer to this second file name。

 and it will return a pointer to the second file name。It will also save the first file name。

 So the second argument is a pointer to a 14 by area。

 Remember that file names can be at most 14 characters。

 and it will save the first component in that area。 If there is no file name in the path。

 then it will return no。Okay， so let's take a look at the code here。

One thing I want to mention is that it ignores leading slashes。

 and if there are multiple slashes separating the file names。

 then it ignores that and treats them just as one。Okay。

 so here we're past a pointer to the path and a pointer to the 14 by area to say the first file name。

So it begins by skipping past， any leading slashes and ignoring them。

And then if there's nothing found， that is， if we're positioned at the no bite at the end of the string。

 then there is no file name in the pass。 So we just return。zero。Now。

 we're positioned at the beginning of the first filing， So we save a pointer to that。

 And in this while loop here， we advance our pointer。To whatever comes after that final name。

 So we search for the next slash or the next null character and stop when we hit something。

 either of those。And at that point， we know where the first file name begins and where in so we can compute its length。

Now we're going to move it into this name area。 Okay， that that's our second argument here。

 And we need to check to see whether it's greater than 14 if it's 14 or greater than 14。Bs in length。

 Then we don't need to worry about the null。 We just move it into the named field and directorizes this 14 constant。

If it is 13 or fewer characters， we need to add a nu character after the end of it。

 so here we do it that way。And finally， we advance the pointer to the next thing beyond the slashes。

 So if we ended pointing to a slash， then we advance to the second file name or the end of the string and return the pointer the results。

Next， I want to look at the name I function。 This is sort of the culmination of all the functions we've been looking at。

Name I is past a pointer to a path， and it locates that file on disk and returns a pointer to the iode for that file。

And if there's any problem such as the file is not found or the path name is no good。

 then it returns no。The actual work is done by this name X function。 There's another function。

 Na I parent， which is very similar to name I， except it stops one level earlier。

 And both the name I and name I parent call name X to do the work。

 So let's take a look at name I and name I parent here。Okay， we're going。

 so nameI calls name X and nameI parent calls name X。

 and the only difference is they pass a flag to say which is involved here。Now。

 name X requires a 14 B field， a 14 by memory area in which to save each file name in the path。

 And so in the case of name I parent， we're trying to extract that。 So it's passed in。

 but for name I， we have a local variable that's the 14 B field。

 and we're passing in the address of that variable。Okay， so let's take a look at name X。

It is past appointed to the path。 And then this flag Na my parent。 If this flag is 0。

 then we will return the Iode for the parent。Okay， and。Copy the final file name into the name area。

 Okay， otherwise， we will open that file directly。Okay。

 so this name X is only called from name I and name my parent。

So I think the way to look at this thing is to imagine we're calling it from name I first。

 and I'll look at the second case a bit later。 but so imagine that this flag is0 right。

 and we have a 14 byte area that we can use within this name X function。

So here we start by seeing whether the path begins with a slash。 If it does。

 then we we need to start with the root directory。Okay。

 so here we have the device on which the file system is kept and the iode number。

 which is one for the root directory。 And we just get a pointer to the iode for that here。

And let's say we've got just a slash and nothing else。 Then this， Okay。

 so here's a while loop that processes each element in the path name。

 But let's say that there's nothing。 Then we immediately exit the loop。

 And let's we're assuming that this flag is0。 So we skip this。

 and we would just return a pointer to the i note for the root， doesn't lock it。

 but it does add it to the cache。So this flag is called somewhat confusingly name I parent。

 and so the flag is called name I parent， and we're going to assume that that is false when we look at this code here。

Now， if it doesn't start with a slash， then we need to begin processing the path。

From the current working directory。 So the structure for this particular process that we're running in has a field called current working directory。

 And that is a pointer to an iode。 So that's the current working directory。 And we need to use that。

We haven't seen this i dope function before， but basically all this does is just increment the reference count for this iNot。

 In fact， let me just stop and show you the code for that。Here。

 here's the I do function past a point or two an i note， and it acquire the。

Spin lock for the cash increments the reference count and then releases the lock。 Okay。

 so that's what Ioop is doing right here。And I get will increase the reference count for the route directory。

 So regardless of whether we do this or we do this， we've got an iode that's been added to the cache。

 and we've incremented the reference count for that。

 So that's what will be true when we return down here。Okay， so whether we start with a slash or not。

 we are ready to start looking at the path。 So we're going to call the skip element function that we just talked about。

To locate the first file name in the path and to advance the path pointer to the next element。

 So that's what happens here。Okay， if there is no next element， then we are done。 Okay。

 and we exit the loop。But otherwise， we need to look in the directory that we're pointed to at the beginning of this for the file that has this name。

 So here we are identifying the name and and， and saving it in this name variable。And at that point。

 the next thing we're going to do is called directory look up。 But before we do that。

 we need to lock that i note。 Okay， so we lock it here， and then we call directory look up。

Before we do that， we make sure that the file that we are thinking as a directory is in fact a directory so we check its tight and if it's not a directory。

 something is the matter and so we are going to abort and return a zero to indicate that we had problems but remember that we've got the the directory has been had its reference count increased and we've locked it so we need to undo both of those things so we unlock it and decrease the reference count and before we return。

Now I said， let's just take a look at the case where this flag， this name I parent flag is false。

 so let's skip that for now。And now we're ready to do the directory look up。

 so we've got the first or the I should say the next file name in the path in this string here。

 and this is our i note of the directory and so we're going to do a directory look up。

So remember that this is the offset into the directory。

 this is a pointer to a place where we can save the offset if we want to。

 we're going to pass in null because we don't care where in the directory this name is found。

 so we don't need that information we pass in a null rather than the address of a variable in which to store it。

So here is going to， this is going to return a pointer to the iode for this file。

 So that's what the next iode is。 And we'll see here we're going to advance to that。 Okay。

 so if everything goes well， then we return。A pointer to an I know。 But if there's a problem。

 we return null。 And again， we've got this。Directory that we're looking into locked。

 and we've increased its reference count。 So we need to undo those two things and return a no indication to indicate that there was a problem。

 Okay， we couldn't find the file。So if there's a problem with a path name and we can't find one of the files in the path name。

 we consider it an error and return null， but assuming everything's okay。

 then we're done with this directory， we now have the next thing in the path name could be the file that we're looking for。

 that is the thing at the end of the path name or it could be another directory。 In other words。

 we could be looking at the bin directory or we could be down here looking at the file that we want to get app。

 but in any case， we are going to advance to that to that so unlock the directory and then move to the next thing。

 the next file in the path and then we loop back up if that was it。

 okay if that was the last thing in the path， then this thing is going to return zero and we'll exit and we'll exit the loop。

Here and then return the pointer to the file that we found。 Otherwise， the while loop。

We'll continue and look at the next element in the path name。Okay。

 so now let's take a look at the name I parent function here we're passing in one。

 so in this case we just want to stop prematurely。So again， we start with something。

 let's say we start with the root directory。And we set I to point to the the next director or the next thing in the path。

 And let's say there's nothing else。 Okay， this returns 0。 Well， there is no second thing。

 and that's a problem。 So if this thing is true， which it will be for a name， I parent situation。

 then we've got a problem we need to return 0。 it was not at least one file name in the path。 So we。

Get we unlock the。Sorry， we haven't locked it because the the lock occurs in the loop， okay。

We do not have IP lock at this point， so we don't need to unlock it。

 we just need to decrement its reference count before we return。No。Okay， in the loop， what do we see。

 It's the same thing。 we're going through it and we get the next thing in the path Okay。

 we look in the directory that is pointed to by IP and identify the next file and if we are wanting to stop early and we've come to the end of the path right。

 we've advanced path to point to the thing after name and if there is nothing after name。

 then we can stop okay， we're done okay， we've identified the last thing in the file and IP at this point points to the directory so we unlock the directory and return。

Yet。Okay， I think that's it for all the functions in the file F S dot C。

 I will see you in the next video。