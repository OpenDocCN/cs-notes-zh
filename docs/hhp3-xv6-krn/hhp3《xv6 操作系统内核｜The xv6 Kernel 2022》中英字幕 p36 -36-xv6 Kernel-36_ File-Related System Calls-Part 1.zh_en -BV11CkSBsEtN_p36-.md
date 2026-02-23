# hhp3《xv6 操作系统内核｜The xv6 Kernel 2022》中英字幕 p36 -36-xv6 Kernel-36_ File-Related System Calls-Part 1.zh_en -BV11CkSBsEtN_p36-

![](img/c536ab88c370b7fe9dcd7e1f69c96bc9_0.png)

This video is part of a series on the XB6 operating System kernelel。In this and the next video。

 I'll be going over the code and the functions that handle the file related system calls。

These functions are coming from Ss fileile dot C， and I will also cover file， read and file write。

 which come from file dot C。There's quite a bit of code here。

 so I'm breaking it into two different videos。 This is part 1。 And in this video。

 I'll be covering the following system calls。Read， write， close， link。

 unlink S stat change directory and dupe。 In part 2， I will cover the open system call。 make node。

 make directory and pipe。The Ex system call is a little bit complicated。

 so I'll be covering that in a subsequent video。Okay， let's get started。

So let's take a look at the Read and the write system call。 Each of these takes three arguments。

 and the user mode code will begin by placing these arguments into registers A 0， A1， A2， and so on。

It will also place that code number in register A 7。

 and that code number is used by the kernel to determine which system call is wanted。

Then the user mode code will execute the system call instruction in risk 5。

 that instruction is named E call。 And at that point， the kernelel will get control。

 and it will begin by saving the user register someplace。

Then it will look at the value in A7 and determine which system call is involved。

And if it's a read system call， the kernel will then invoke the sis read function。

 There's one of these cis functions for every system call。

The ciss reed will begin by locating the arguments and grabbing them from wherever they were stored initially。

So we have these functions， Ar Gy， Arant and a address。 and each is passed an argument。

 The first argument tells which argument we're interested in。 So a 0， a 1 and a2。

 These things aren't done in order， really。 So this is the first argument。

 the second argument and the third third argument。The arant function will go to register a2 in this case。

 grab a 32 B value and store it。 Well， here's the address of where to store it。

 and that's a local variable in number of bytes。The AG address function will go to register where Reg A1 is stored and grab a 64 bit value and store it in local variable P。

And finally， this RFD will obtain the value that was in a0 at the time of the system call。

And interpret it as a file descriptor。 It will check to make sure it's a legal file descriptor and return -1 if there's a problem。

 and then it will get a pointer to the file structure and it will store that pointer in F。

It can also obtain the file descriptor number itself， but that's not needed。

 so this address here is just null。If there's a problem with the arguments， we return -1。

 but otherwise， we're going to call this function file read to actually do the work。

 passing at a pointer to the file structure， as well as the virtual address and the number of bytes and file read will return the number of bytes transferred or -1。

 if there's a problem。So before I look at file read， I want to just look at the。Ss right function。

 which is exactly identical， right， It gets the arguments。Here。

Except it calls file write instead of file read。Okay， so let's take a look at file read。

The function file read is coming from。F that。And as I said。

 it's past a pointer to the file structure， as well as the virtual address and the number of bytes。

So it checks that file structure and looks at the readable flag to make sure that this。

File descriptor describes a file that is actually readable。 and if not， there's a problem。

 It returns -1。And that would then get returned to the user mode code。Otherwise。

 it looks at the type if it's a pipe， device or iNot。If it's a pipe。

 it's going to call the pipe read function， which I covered in an earlier video。

 And it's past a pointer to the pipe structure。And it will perform the read and store the bytes in this virtual address and return the number of bytes successfully read from the pipe。

 or possibly minus1。And then that will get returned。If the file structure is a device。

 then we look at the major number in the file structure。 That's the device number。

 and we make sure it's legal。 And we also look into this device switch array。

 we use it as an index into that array。 And remember that that array contains structure that has two fields。

 Both of those 0。2 functions。 So we're going to be using the read function。 So we look at that field。

 make sure it's not null here。If there are any problems， we return -1， but otherwise。

 we use the major number as an index into the array， get the read value。

 which is a pointer to some function， and then we invoke that function。

 So that will be the console read operation。 We path it a virtual address and a one to indicate that this is a virtual and not physical address as well with a number of bytes。

Finally， if it's an iode， then we will use the read I function， which I've also covered。

That's past a pointer to the in， as well as a address and a flag which indicates that this happens to be a virtual address。

As well as where in the file， we want to begin the reading。 And so we go to the file。 Sorry。

 we go to the Ie。Sorry， we go to the file structure。

And we get the current offset and the number of bytes。 If anything goes wrong， we return a -1。

 But otherwise， if we return the number of bytes red。 And if we read any bytes， this was positive。

 then we need to increment the offset that's stored in the file structure。 and we do that here。Now。

 Ridi expects the。I know to be locked， So we need to lock it first and then unlock it after we're done with it。

If it's anything else， then we panic。But in any case。

 we return are the number of bytes that we've read。

Now I want to take a look at the file right function。It's used for the right system call。

 and this function is very similar to the file read function that we just looked at。

It's passed a pointer to a file structure as well as the virtual address and the number of bytes。

Begins by checking the file structure to make sure that this file can be written to and returns -1 if there's a problem。

 And then it looks at the type to determine whether this file is a pipe， a device or。

A directory or regular file。And if it's a pipe， it calls pipe right。Previous。

 we called pipe read here， and that will return the number of bytes transferred or minus-1 if there's a problem。

 And then at the bottom of this s state， but we return that value。

If it's a device similarly to file read， we check the major number to make sure it's legal。

 We look into this device switch array using that as an index。

 and that gives us a structure that has these two fields， read and write。

 We make sure the right field is not null。 And if everything's okay。

 Then we're going to use that value。 Okay， so we index into the array and get the right field。

 That's a pointer to a function。 We're going to call that function。

 So we're passing it an address an indication that that's a virtual address and the number of bytes。

 And again， returns the number of bytes transferred。And we return that。Now， in the third case。

 it's an FIode for the file type， which means it's a directory file or regular file。

We might have a very large right， and these rights are going to have to go into transactions。

Previously， the read did not go into a transaction because if it's interrupted by a system crash。

 for example， it's no， no problem。 The disk is still consistent。

 But here we are doing a right operation。 So we need to include all of the writing in a transaction。

 So we'll see a begin up and an end do down here。That transaction is limited。

 It must be limited to a certain number of blocks。 We can't write too much。 Otherwise。

 we might fill up the log file and that could cause problems。

 So we need to break the right into a series of chunks。

And the first thing we do is we compute this size， the maximum size of any chunk。

 So that computation happens here。So let's just read this。

 write a few blocks out of time to avoid exceeding the maximum log transaction size。

 and we're going to be writing the in， possibly writing an indirect block and the actual blocks that are involved and the right the blocks。

 the series of bytes that we're writing may extend over a block boundary。

 So we're going to add to for that as well。 And I'm not quite 100% comfortable with this computation here。

 but it is what it is。 And don't want to bo down on that。

 I do want to say this really the comment says this really belongs lower down since right eye might be writing to a device like the console。

 but that's not really what right eye does right eye only writes to files on the disk。

So we compute the maximum chunk size。 and in this while loop here。Okay。

 what we're going to do is break the entire。是。Sequence of bytes that we need to write into a number of chunks。

 So n is the number of bytes to be written。 and n one will be the size of this particular chunk。

 And I will be the number of bytes that we've written so far。 So we're starting I out at 0。

 and we just keep looping until we have written a full n bytes。

And here we see how many bytes we have left to right。 So we compute n one。

 but we don't want to write any more than maximum number of bytes。 So we。Cut in one off at max。

 if it exceeds maximum。And then we're going to write that chunk。That will go into a transaction。

 So here's the begin up and the end up。 And we begin by locking the eye note here and then unlocking it here。

 And then we call right eye to perform this particular chunk， to write this particular chunk。

 Here's the eye note that we're writing it， too。 Here's the virtual address where we are getting it。

 And here's the one to indicate that that's a virtual address。

And here is the offset within the file that we are writing to and the number of bytes that this particular write。

Will be if everything's okay， it returns the number of bytes written。 And if that's greater than 0。

 we need to increment the offset。And then。We see whether we've got a problem。

 If we didn't write all in one bys， then the R， the the number that we did write will be。

Less and so we are done。 We need to break out of this loop。 Something went wrong。

 And so we break out of the loop。 Otherwise， we increment I and keep going。

 And then we determine whether we wrote all of the bytes。 Did we write all in bytes。 If so。

 we return that number。 Otherwise， we return to -1。Next， let's take a look at the closed system call。

 which is past a file descriptor。So here's the Ss function for the closed system call。

 and it begins by obtaining its argument。Arg FD is used to get the argument in a register A0。

 which is the first argument， and that's expected to be a file descriptor。

 and it will store the file descriptor integer itself in local variable FD and a pointer to the file structure in F。

If everything's okay， then it will go into the pro structure and go into the O file array and null out the entry that's indicated by F D。

 And then we'll call file close to do the work。 I discussed file close in a previous video。

 But let's take a look at what's going on here， so。Here's a process。

 and here's the pro structure for that process。 So the first thing this close will do is go to the particular entry and it will change it to null。

 and then it will call file close and file close will decrement the reference count。

And if the reference count goes to zero， then it will look at the IP and the pipe pointers。

 if it points to an iode， then it will go into that iode， decrement the reference count。

 and if that goes to zero， then it will close out the iode。If it contains a pipe pointer。

 then it will follow that， and it will look to see whether this is the last pointer。

 If the other pointer has been shut down already， then it will free the pipe structure。

But if the reference count doesn't go all the way down to zero。

 then fileflows will not do anything else。ok。😊，Now， let's take a look at the Dope system call。

 It's past the file descriptor of a file that's already open。

 and it will allocate a new file descriptor for this file and return that new file descriptor or -1。

 if there are no more slots left。So before we look at the Sis do function， let's look at F D Ac。

If the ac has passed a pointer to a file structure， that's the file that's already open。

 and it goes to the pro structure。 And then in this loop。

 it runs through the O file array from 0 to the end。

 looking for an entry that is currently not in use。 and if it finds one。

 then it will store a pointer to this file structure in that entry。 and return the file descriptor。

 that is the number， the small integer that indicates which entry was used。

 And if there are no more slots than it returns -1。

 So looking at the picture we see that it's going to goes through the array until it finds a null。

 and then it's going to store a pointer to some file structure and return whichever index it stored it into。

Now we can look at Sisduop。It's past a single argument， and R FD goes and gets the first argument。

 and that should be a file descriptor to an open file。

 So it returns or saves into F a corner to the file structure。 And if that's okay。

 then it calls F ac。 And that will find an empty slot in the array and return the index of that empty slot。

 as well as filling it in。 And at this point， we call file dope。

File do was covered in an earlier video， but essentially what it's going to do。

 it's past a pointer to a file structure， and it will lock that structure。

 increment the reference count， and then unlock it in return。 And then finally。

 Sisdu will return the file descriptor that was allocated。Now。

 one thing about Unix that's very important and that is that the user has this idea that these follows scriptures are allocated in some order and 0。

1，0 is used for standard in， one for standard out， two for standard error。

 and we rely on the fact that dupe will fill in the first empty slot in this ordered array here。

 and that's used by the shell program that is relied on by the shell program。Next。

 let's look at the StAT function。 It's past， the file descriptor of an open file and a virtual address。

 and it save some information about that file at that address in the user's address space。

I already covered the cis。St function， but I'll just quickly review it here， takes two arguments。

It uses R FD to get a pointer to the file structure for the open file。

 and it obtains the virtual address here as the second argument。

 and then it calls the file stat function， which will copy information about this particular file to the virtual address given here。

Next， let's take a look at the change directory system call。

Every process has this idea of a current working directory。

 and from time to time we can use the system call to change that directory。It's past a string。

 which is a path name that describes a file which better exist and better be a directory。 and if so。

 it will change the current working directory to that file。

So in this picture I showed the O file array， I did not show the current working directory field。

 but it's there， and it points not to a file structure， but directly to an Iodeode structure。

So now let's take a look at the。function sits change directory that does this system call。First。

 it gets the argument。 The argument is a pointer to a string in the user's virtual address space。

 and the arg string function will retrieve that string from the user' space。

0ero indicates that it's the first argument that we're interested in。 There is only one argument。

 Pa is a local variable here， and we're going to move the string up to the nullbyte into this array here。

And we'll stop at the maximum length if we reach that。

So the second thing we do is we invoke this name I function。We covered that earlier。

 but basically it's passed a string， which is a path thing。

 and it will open that file and allocate an iode and return a pointer to that iode。

 So I P is a pointer to an in。And if that's successful， then we keep going。

 But if there's either a problem with the string or a problem finding that file。

 then we will immediately return -1。You can see that I've drawn a line between this begin up and this end up and also between this lock and unlock。

 sometimes when we have a complex series of nested loops or if statements。

 using lines like this can help match the braces。 and so here I'm doing it to make to show how these things are matched up and to make sure they are。

 in fact， matched。So。The name I function will increment the reference count for the I node。Okay。

 so that was done in the I get function。 And that's part of name I。 So if this thing is successful。

 then the reference count for the I note is incremented and we need to ultimately do an I put。

 such as this down here to match that。 But if there is a problem， then it won't be incremented。

 So then when we get ready to return here， we're going to jump out。

 and we can see that we're crossing this single line here。 So we need to take care of that。

 So there's the end out that matches with that begin op。But assuming everything's okay。

 then we need to check that file and make sure that it is a directory file。

Before we look at any field in that i node， we need to lock the i node。

 So here we're locking it and checking the type field to make sure that it's okay。

 And if it's not okay， then， well， we have done the get。Within the name I function。

 And we've done the lock。 And we've also got the begin op sort of open。

 So we need to undo all of that。 So we unlock， put and in the op and return to -1。

But assuming that it is a directory， then everything's okay。

And we're going to proceed and return zero here。Now we've got an existing current working directory and that field will point to an iode for some other directory。

 and we have incremented the reference count for that iode to keep it from being deleted。

 and so we are done with that。 Now we no longer are going to point to it。

 So we need to do the put function for that。 So here we're sort of releasing our pointer。

And this one， we've incremented the pointer。 So in some sense。

 we've incremented one pointer and decremented the other reference count。

We've incremented one reference count and decremented the other reference count。In some ways。

 these are sort of matched， but in any case， we are now done with our transaction。

 and the final thing we do is store a pointer to the i note in the current working directory。

Field of the prox structure。 and then we return zero。Next， let's take a look at the link system call。

 It's past pointers to two strings。The first is the path name of an existing file。

 and what this function is going to do is it's going to add an entry into a directory so that the new path name will be valid and will refer to the same file。

If everything's okay， it will return 0 and it will return -1 if there are any problems。

So here is the sslink function。And it begins by dealing with the arguments。We have two arrays here。

 new and old， in which we store these path name strings。

 We need to copy them from the user's virtual address space into these arrays first。

 And we do that with the call to the arg string function。 So here。

 we're calling it for the first argument。 And here for the second argument。

 And we copy the first path name into the old array up to the null byte or up to max path characters。

 And here we are copying the second argument string into the new array up to the null byte with no more than max path bytes copied。

 If there's any problem here， we immediately return -1。

Now we're going to be updating the file system， so we need to put this into a transaction。

This begin op is where the transaction begins。 and down here is the matching end op。

 and we return 0 to indicate that everything's okay。

So you can see that I'm using this line system where I match I get with I put I lock with I unlock。

 and I begin with， sorry， begin up with end out。The next thing we do is we take the old path name and we invoke this name I function that I talked about earlier。

This is going to go out to the file system and locate this file。

And then it's going to allocate an iode structure in the iode cache， and if successful。

 it will return a pointer to that iode structure and increment the reference count。

But if there's a problem， it will return -1。 So we're inside this begin up。 we meet。

 we need to immediately end the transaction and return -1。But if it is successful。

 then we will have increment of the reference counts for that I node， which is what I get does。

 And so that's why this line is here。The next thing we are going to do is check the type of the old file of the existing file to make sure that it's not a directory。

The directories must be organized in a tree， so we can't add additional links to a directory。

 And that's why we're checking here。If it is a directory， then we're going to abort。

 But before we check the type field， we need to lock that eye note。 So we lock it here， check it。

 if there's a problem， immediately unlock it。 and then call I put to undo the increment of the reference count。

 So we decrement the reference count。 and then we end the transaction。

 So we're essentially breaking out， going through all three of these lines here。

And then we return -1。But assuming that it's not a directory， then things are looking good。

 So we need to increment the in length field in the iode。

 That's the number of hard links that point to this file。 And since we just updated the iode。

 we need to write that back to the disk。 So here we're calling I update。

 And then we unlock this iode。This one't actually get written to the disk， of course。

 until we end the transaction down here。 but for now we're done with it。

 So we update the disk and unlock this i note。Next， we need to process the new path name。

 So here's an example， new path name。 It consists of a directory followed by a name at the very end。

 And we talked about name I parent before。 but it's past this path name。

 What it's going to do is locate this directory and allocate an eye note for it and return the iode。

 or return a pointer to the iode as D P。 And so it's incremented the reference count for the iode that describes the directory。

And it's also going to isolate the final name in this path name。

 And it's going to store it in this variable here。 Na is an array here that's limited to， well。

 director sizes 14 B。 So it will store the final item in this path name into this name variable。

If there's a problem like this string is all messed up and empty or this directory doesn't exist。

 then this thing will return -1， and we will jump out and go to a label calledBd。

If there is a problem， we will not increment the reference count for。This D P， I know。

 So that's why I'm skipping this line here。 But we still have the。

I did reference count for the old file and the begin up sort of pending。

 So that's why they're I'm crossing two lines here。 Now， let's look at this bad label right now。

 whoops。Here it is。And so I'm showing the two lines here。

That we have to cross to come into this label。And we need to decrement the number of hard links。

 We previously incremented it on the assumption that everything was going to work out。

 but we've got a problem now， So we need to decrement the in link field。 And in order to do that。

 we need to hold a lock on that i node。 So here we lock the i node and here we decrement it and here we update it。

On disk。 And then at this point， we unlock it， and we also decrement the reference count for this existing file。

 And finally， we in the transaction and return -1。But assuming that we did not take that jump and everything's still looking good。

We now need to modify this directory to add this name。 So we're going to lock the directory D P。

 And then we are going to check to make sure that this directory is located on the same device that the existing file is located on。

Remember that hard links cannot cross from one file system to another。

 They have to be on the same device。 And so that's this check right here。 And if theres a problem。

 we're going to go to bad。But if that's okay， then we call the directory link function。

 which I discussed before。 It's past a pointer to an iode which describes a directory like D P here。

 and it's passed a name， array， as well as an iode number， an eye number。

And so this will add a new entry to this directory。 Okay， And if everything's okay， it will return 0。

 Otherwise， it will return -1。 If anything went wrong with that， then we need to go to bad。 Okay。

 we will need we。Willll need to deal with the lock that we have on D P。

 as well as the fact that we've incremented the reference count for this Iode。

 So we unlock and put here。 and then we go to bad。 And so we still have these two things to do。

 We need to do the matching I put and end op， which we saw happens in bad。

 We do the put here and the end op。Okay， but if that didn't happen and the directory link returned 0。

 then everything was okay。 Well， we're done。 Now we can unlock。The directory。

And here we incremented the reference count for that in， so we do the corresponding put。And then， we。

Do the corresponding put for the old file and in this transaction。 and finally， we return0。Next。

 let's look at the unlinked system call。 It's past a pointer to a string， which is a path name。

 and it will remove a hard link to that file。Return  zero if everything' is okay and minus1 if there's a problem。

Before looking at the code of cis Unlink， let's look at the code for。Is directory empty。

 It's a little helper function， and it's going to be passed the eye note for a directory。

 and it's going to go through that directory and ask whether it contains anything。So you see。

 it loops through this directory in units of。Well， D E is is a directory entry。

 And remember that a directory entry contains a 14 B file name and a 2 Bte Iode number。

 So the size of this thing is 16。 So it's going to increment in units of 16。

 but it's not starting at 0。 Instead， we're going to skip the entry for dot and dot dot。

Every directory must contain these two。 So instead of starting at and going0。16。32，48 and so on。

 We're going to start at 32 and increment in units of 16。 So that's what's going on here。

And we end when we get to the size of the directory。 And for each of these offsets。

 we're going to read from the directory。 So we're providing the pointer to the i note for the directory。

 And we are going to move from this offset in the file。16 bys。

 And we're going to place them into this local variable， D E。And this is a variable in kernel space。

 And this flag here indicates that it is a physical address and not an address in virtual memory。

And we should return the number of bytes that we've asked for。 So we're reading 16 bytes。

 and we should return 16。 And if that's not the case， and something is the matter and we panic。

But otherwise， we look into the directory entry that we just read here and ask， is the I number 0。

 unused entries will have an I number of 0。 And if it's not 0。

 then there is something in the directory beside the dot and dot dot entries。 So we return false。

 Is directory empty。 Well， it's false。 That's not true。 If we find something。

 But if we go all the way through。And find nothing。 We return true。Here is the Ss unlink function。

 It's kind of long。 You can see that we begin a transaction here and we go down here and continuing on to the next page。

 we ultimately in the transaction and return zero if everything's okay。

We've also got a bad label where we return minus1。So。Let's begin with the argument。

 We're past a pointer to a string， which is the path name。

 And we call arg string to copy from the user's virtual address space into a local variable path。

 So that's what happens here。 And if there's any problem with that， we immediately return -1。

 And then we begin the transaction， we need to be running a transaction。

 because we're going to be updating the disk。 when we remove the file from a directory。

Then we begin by calling name I parent。Name I parent， which I covered earlier。

 has passed a path name， such as this right here。 And it's going to identify the final component in the path name。

 X X X X， the file name that we're removing， and then it's going to identify the directory that it's located in。

 and it's going to return D P， the directory pointer。

 which is a pointer to an iode structure for this directory。If it's in this form。

 then it will return a pointer to the root directory， and in this form。

 itll return a pointer to the current working directory。

 So now D P points to an iode for the directory， and the name field is a local variable here。

 and we are copying。The final component in this path name into this name array here。

If something goes wrong， then it will return DP equal to null。

 and we immediately end this transaction and return minus1。 but assuming that this directory exists。

 then we can go ahead and lock it。The next thing we do is we check to see whether we're trying to remove the dot or dot dot entry。

 These cannot be removed from a directory with this function。

 So we do a compare to see whether name happens to be dot or dot dot。 And if either of these is true。

 then we go to bad。 So we've started a transaction。

 We've done the I get function to increment the reference count for the iode。

 and we've locked the iode。 So let's go to bad and see what happens there。So here's bad。

We are going to unlock the directory。Do an output， which will decrement the reference count。

 And then we're going to end the transaction and return -1。So assuming that it's not dot or dot dot。

 we can proceed。 And now we're going to call directory lookup。

 Directory lookup is passed a pointer to of the I node for some directory， such as here and a name。

And we're going to look this name up in the directory。 And if we find it。

 we're going to allocate an iode for that file and return a pointer to that iode。

We're also going to store the offset into this directory file of where that directory entry occurred。

 So we have a local variable offset， and we're going to save the offset within the directory file of this entry for this particular name。

If there's a problem and we couldn't find the name in the directory， then we will go to bad okay。

 we will not increment the reference count for IP， but still we have to unlock the directory and decrement the reference count for the directory and in the transaction。

 So that's what happens there。But assuming that the name is in the directory。

 we have incremented the reference count for this i note。 Now we need to lock it。

 We're going to be modifying its end link。 First of all， we're going to be looking at its end link。

 So we need to lock it before that。We do a quick check to make sure that the end length。

Is at least one。 I mean， we can't。 we would have some kind of a consistency error otherwise。

 And so we panic if it's zero or smaller。Then we look at the type of the file that we're removing。

If we are removing a file， you know， X X， X X， and that is actually a directory itself。

 then it better be empty。 We could only remove it if it's an empty file， an empty directory。

 So here we're calling the is directory empty function。 So if it is a directory and it is not empty。

 then we've got a problem。 So at this point we've locked IP an increment of the reference count。

 So we need to unlock and put the IP。 and then we can go to bad to take care of the other stuff。Okay。

 so that's assuming that error hasn't happened。 We don't have any more error conditions。

 and we can keep on going。 So we have a local variable D E， which is a directory entry， right，16 bys。

14 bys for the name and  two bys for the I number。 What we're going to do is set it all to 0。

 including the I number in particular。And so we've got the directory entry being set to 0。

 And now we're going to write that directory entry into the directory。

 So here's the right eye function。 We're passing it the iode of the directory file。

 And we are writing from this directory entry。 There's all zeros。 That's in kernel space。

 So this flag says it's kernel space and not a virtual address。And we are writing2 the offset。

 That's the offset we saved with the call to directory look up。 And we are writing， well。

 directory entries are 16 bytes。 So we're writing 16 bys。

 And this thing will return the number of bytes that we wrote。 it better be 16。 I mean。

 the directory entry is there。 we found it earlier。 and we've had the thing locked since then。

 So it better still be there。 So we panic if there' if it's not。

And then let me just skip this for a second。 Now we're done with the directory。

 we're going to unlock it and decrement the reference count。

 and then we're going to go to the in for the file itself and decrement the number of hard links to it。

That will involve an update to the disc。 so we need to do an eye update。

For this particular eye note here。And then finally。

 we can unlock this file and decrement the reference count。 and we're done。

 We can end the operation in the transaction and return 0。 But I skipped over this part。

And that I want to try to describe here。So。Let's imagine that we're trying to remove。

The bin entry from this directory。 So here's a directory slash user。 let's say。

 And it's got only a one file in it。 And that file is bin。

 And so we have a directory entry with 14 by plus 2 byte iode number。

 which points to some other file。 and that other file is a directory file。 Okay。

 it happens to be a directory。 and it's pointed to by I P。

 the iode for this file is pointed to by I P。So with directories。

 we have the dot and the dot dot going on， so。The dot entry always contains the node。

 the I number of the file itself。 Okay， so that's that's the dot entry。

And the dot dot contains the iode of the parent。 So this is a tree。

 We have only a single parent for directories。 so we can have a parent pointer。

 And that's the dot dot pointer。Now， the question is。

 how many links are there to this particular directory？ Well， of course。

 we have the one link that is for the directory in which it lives。 Okay。

 we don't count this pointer here， but we do count this pointer， So we got one directory。

 We could have， you know， other directories as well， in。This directory。

 but it looks like we just got this one bin。 And so we've got a back pointer from。Ben。

 and so that's the second hard link to this directory。 So in link will be two。

 If we had something besides Ben， we might have actually additional pointers from others， but。

What this is showing is that the number of hard linkss for a directory includes the the hard link from the parent in the directory tree。

 as well as one hard link from each of the children directories in the directory tree。

 So we've got to decrement。Okay， we're eliminating this file。

 so we're removing Ben from this directory。I already showed where we decrement the in link for I P。

 but we also have to decrement the in link for D P。So we decrement the inlink for IP here。

And we incr or we decrement the in link for DP here。 And here we update the directory。

 if if that's the case， we have to update this i note on disk as well。

 So we have to call I update here。So after we're done with all that。

 we have eliminated both this hard link and this hard link and adjusted this inlink pointer and this one because we've also eliminated that one。

And then we can return0 if everything worked out okay。

There's a subtle point that I wanted to mention about this code。

Whenever you're locking multiple things， it can be very critical what order you lock them in。

If you lock them in the wrong order， there might be a possibility of deadlock。

And I've drawn my lines to match the locks with the unlocks to make sure that everything we lock gets unlocked。



![](img/c536ab88c370b7fe9dcd7e1f69c96bc9_2.png)

But it doesn't really matter which order you unlock things in， General speaking。

 as long as you get around to unlocking everything that you've lo。

 So here I'm showing the unlocks reverse in order。 Okay， in the code that I showed before。

I wanted to。 I kind of messed up my lines。 We're locking D P here。 And then within that。

 we're locking I P。But and then at the bottom of this function， we are unlocking DP。

And then we're unlocking I。 So actually， we have this situation here and not this situation。

 So really， I suppose I ought to draw these lines crossing or something。

 But I did want to mention that。Okay， that's enough code to put in one video。 In the next video。

 I will continue going over the functions in cis file do C。 I will see you in part 2。

