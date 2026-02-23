# hhp3《xv6 操作系统内核｜The xv6 Kernel 2022》中英字幕 p37 -37-xv6 Kernel-37_ File-Related System Calls-Part 2.zh_en -BV11CkSBsEtN_p37-

![](img/ba5129da12b5a28c0a39a91ca41a962c_0.png)

This video is part of a series on the XV6 operating System kernelel。

There are a number of functions that implement the file related system calls。

 and these are coming out of the file cis file dot C。 There are quite a few functions。

 And in the previous video， that is part 1， I covered some of them。 And in this video。

 I will continue。 And in particular， I will be covering the following system calls。Open。Make note。

 Make directory。And pipe。The exact system call is a bit complicated。

 and I will handle that in a subsequent video。Okay， let's continue with these functions。

Now let's look at the create function。This function is used to create a file and add it to some directory in the file system。

It's past a type code that indicates what kind of file we want to create， either a directory file。

 a regular file or a device file。If we are creating a device file。

 we need the major and the minor numbers， so these will be something for other kinds of files for director files and regular files。

 these will be passed in as zero and not used。We're given the path name here as an argument。

 and that tells not only what directory we're adding it to， but the name as well。 So， for example。

 with this file name， we can see that we're adding a file called X X X to some directory in this example。

 user bin。On success， we will return a pointer to the newly created file or more precisely to an iode for the newly created file and that in will be locked as well。

If there's a problem， we'll return， null。Create is called from exactly three places。

 It's called from the open system call。 It's called from the make node system call。

 and it's called from make directory。And for the make node system call。

 it's for adding a device file， and so type will be device for make directory。

 we're creating a directory。 So type will be directory。 and finally。

 the open system call has the option to open a file and create it if it doesn't exist。

 So when called from open the type will be file。So。We're past in this path。

 And the first thing we do is call name I parent to parse this path name。

So it will identify the final thing in the path name and store it in this variable name。

 so this local variable name will contain x Xx。And then the prefix of the path name will be a directory。

 and that directory will be opened and the reference cap will for that iodeode will be increment。

 and DP will be set to a pointer to the iode。If everything's okay， then we'll keep going。

 But if we had a problem。Then this will return null and will immediately return null。

So we're going to be modifying this directory。 We begin by locking it。

The next thing we do is we look up Xxx in this directory to see if it's already there。Okay。

 if it's already there， this will return an a pointer to the i note for that file， and will' set I。

 and it will be something that's non zero。 So we do this code if the file already exists。

And if this thing returns， no， then we don't have a file， so we'll go on here to create the file。

But it might be okay for us to have the file， in particular。If we are called from open。

Then it would be the case that we've had the flag to create the file if it doesn't exist。

And if that's the case， we might have an existing regular file。

 Okay so we check the type field of the file that does exist。 And if it's a regular file， well。

 that's okay， it already exists， we'll go with that。 Or if it's a device file， that too is okay。

 so we'll go with that。 And in that case， we'll return I。

But if we were called to make a device file or make a directory。

 then this is going to be false and we'll return no。 But if we return， if we find that it's okay。

 we will return IP first we have to lock it before we check the type field and then we will return with it locked and。

before we return， we will unlock the directory okay and we'll return either way here。

 And so if it's not okay， that is if we're called from the make node system call or the make directory system call。

 and we've already got something。 then we need to return null。

 So we're going to both unlock the directory and unlock the file that already exists and just return null。

Okay， so we've got the directory file locked at this point and we've determined that the file doesn't exist。

 So at this point we call Ialc。Ialec will create， will allocate an Iode and will increment the reference count and will set its type to whatever were passed in here。

And so now we've got the iode in existence and assuming that that works successfully and doesn't return。

 no， we keep on going。Now we lock the file that we've just created because we're going to access some fields。

First of all， we're going to set its hardlink count to one。

 and we're going to sell in the major and minor numbers。

 which will be important if it happens to be a device file that we just created。

Then we're going to see whether the thing that we're creating is a directory file。

 if we have just created a directory file， we need to add entries into the directory for the dot and dot dot files。

So that's what we're going to do down here。 But remember that the hardlink count in a directory situation will include the hard link from a child to its parent。

 so here we are increasing the count of hard links to the directory that contains X X X。

And that's what happens here。 And that's why we do that。

 And then since we've modified the directory that we're adding to， we update that。

And then we are going to add entries for dot and dot dot。 So we call directory link。

First for dot providing the I number of the file that we've just created and then for dot dot providing the I number for the directory itself。

 and if something goes wrong there， then we panic， but otherwise we keep going。Now， at this point。

 we need to add X X X to the directory itself。 So here we're calling directory link yet again。

 passing it a pointer or to the iode for the directory that we're adding X X X2 as well as the name X X X and the I number of the file that we just created。

 So presumably that will return。Something。 And if there is a problem。

 then it will return negative one。 and we can panic。 But otherwise， we're pretty much done。

 We still got the directory itself locked。 So we need to unlock it， and we also incremented the。

Reference count when we call name my parent。 So we need to undo that as well with a put。

 So we do that here。 and then we return a pointer to the newly created vial。

 and it will be locked at this point。Now let's look at the make directory system call。

 It's past a path name and it's just going to create a directory file。

So here is the code for cis make directory。 And basically。

 it's just going to call create which we looked at。 So it's pretty straightforward。

 We begin by putting everything in a transaction。 So we have a begin up and an end do。

And if there's a problem， we'll return  -1， Otherwise we willll return 0 to indicate that everything's okay。

We begin by looking at the first argument。And it is the path name。

 So we're going to call argument string to copy from the user's virtual address space into this local variable path。

The path name， and then we're going to call create providing it that path name。

 and the type code will indicate that we want to create a directory file and we pass in the major and minor numbers as zero。

And if that works， it will set I P to be a pointer to the iodeode for the newly created directory file。

If there's a problem， it will return null and we immediately in the transaction or return -1。

 But if it succeeded， well， we don't really need to do anything more。 So we have locked this i note。

 So we need to unlock it and then decrement the reference count for the i note。

 And so we do that here in our transaction and then return0。

Now let's take a look at the make node system call。 It's very similar。

 It's past a path name and will create a file， but it will create a device file with the given major and minor numbers returning zero if everything's okay and minus-1 otherwise。

So here is the code for make node and it's really quite similar we have a transaction and if everything's okay。

 we return zero， otherwise we return minus1。 We have three arguments。

 The first one is the path name so we call argument string to grab that。And put that string。

 Mo it from the user's virtual outer space into this local variable path。

And then we get the next argument and move that into the local variable major。

 and then we call argument a int to get the last argument as a number。

 an integer and move it into the minor variable Now that we've got those we can just call create and provide it the path and this time the type is device and we provide it the given major and minor numbers。

 and again， if there's a problem， it will return null， in which case we terminate our transaction。

 return minus1， but if everything' is okay， it will return a pointer to the iode for the newly created file。

And that file is locked， so we need to unlock it and decrease the reference count and in the transaction and return zero for success。

We are now in a position to look at the code for the open system call。 Remember that in Ex。

 Open is passed。 a path name that's the name of the file to be opened。

 as well as an integer that's called the flags value。

 And that value has some bits defined in it that tell what to do in certain situations。

And the system call returns the file descriptor。 That's the small endger that we'll be using in system calls like read。

 write， close， and so on。Now this flags value has this definition here for XV6 in real UniX。

 this is a little bit more complicated so you can look at the documentation for that if you're concerned about what's going on in production operating systems。

 but here's what XV6 does， it has the flag word defined with several bits if this bit is one then the file should be opened right only。

So right only is that bit。If this bit is one， then the file should be open for reading and writing。

And that's this bit。 And if this bit is set， we should create the file if it doesn't exist。

 And if this bit is set， we should truncate the file to size 0， if it exists。And finally。

 we have this read only， which is no bits set at all。Okay。

 now let's try to walk through the code for the Ss open function。

 which implements the open system call。 It will be returning the file descriptor integer。

It begins by looking at its arguments。The function calls arg string to move the path name。

 which is the first argument to the variable path here。

 which is a local variable from the user's virtual address space。

 And then it calls Arg endt for the second argument。

 And it stores the flag integer in this local variable called O mode or open mode。

If there's anything wrong， we immediately return minus1。Otherwise， we start a transaction。

 we're going to possibly be creating a file， so we will be modifying the disk。

 so we need to have a transaction going。Now， the next thing we have is an is statement。

 We look at the create bit in the flags value。 And if that is set， we do this， we call create。

And if it's not set， then we call name I。Create will be past the path name。

 and it will try to open the file if it already exists。And if it doesn't exist。

 it will create it and it will create it as a regular file。If it creates it or opens it successfully。

 then it will set I to 02 an iode representing that file。

 and it will not only increment the reference count to that iode， but it will also lock that iode。

 So I'm drawing two lines here。If there's a problem， though， it will return null。

 and we immediately in the transaction and return -1。Otherwise， if the crate bit is not set。

 then the file had better exist。 So we called name I and provided the path name。

And it will find that file and allocate an iode in memory and return a pointer to that iode with the reference count incremented。

 So that's why I draw one line here。If there's any problem that like the file doesn't exist。

 then it will return nu， and we in the transaction will return minus1。Next， we lock that iNot。

 so in either case， we've got the file locked。If the file already existed。

 then we check to see if it's a directory file。 We are allowed to open directory files。

 but only in read only mode。 So here we're checking to make sure that the flags bit is the flags word is all zeros。

 That is the write only or the readr flag flags are not set。

 we're not trying to create it and it's we're not truncating it。

 So we're only allowed to open it in read only mode。And if anything's wrong there。

 we immediately unlock it。And we decrement the reference count in the transaction and return minus1。

If the file was opened and it was a device type， oh that's okay。

 we do a quick check to make sure that the major number is in the legal range here。

And if there's a problem there， we would unlock it。

 decrease the reference count in the transaction and return minus1。Now we're going to。

 we've got an INot either for。A directory or regular file or a device file。

 And what we need to do is find a slot in the open file array for the pro structure for this process。

 And we need to fill in that value with a pointer to a file structure。

 So we need to allocate a file structure as well。 And said it's I P pointer to point to this iode。

 whether it's a directory file， a regular file， or in this case， a device file。

 So that's what we're doing here， we call file ac。To create the file structure。 And we said。

 F to point to that file structure。And then we call FD ac。

 and Falc will look through the array and find an empty slot and set that to point to the file structure and increase the reference count for the file structure。

 so if there is any problem with either of these that is we can't allocate the file structure and it returns null。

 or there were no available slots in the open file array。

 then we will get rid of the file structure if we allocated it by calling file close。

And in either case， we unlock the iode and de the reference count in the transaction and return minus1。

Okay， but assuming everything's okay， we continue。If the type of the iodeode that we've just opened is device。

 then we've got sort of this situation down here where the iode points to a device what we need to do is set the type of the file structure that we've allocated to device and copy the major number to the file structure。

 so that's what we're doing here we are setting the type to device and copying the major number from the iodeode to the file structure。

Otherwise， we've got a directory file or a regular file。

 and so in that case we need to set the type of the file structure to iode and we need to initialize the offset to zero。

 and that's what we do。Right here， we set the type to iode， and we initialized the offset to 0。

Finally， we need to fill in the I P pointer in the file structure to point to the iode。

 whether it's a directory or regular file or whether it's a device file， we need to set the I。

Fielel to point to the Iode structure。And we do that here。

Then we need to set the readable and writeriable flags in the file structure。So。

Here we are looking to see whether we have right only。 We make sure that that bit is 0。 if it's 0。

 then。Either we have a read only file or a read writeite file。 And in that case。

 in either of those cases， the readable flag should be set to true。 So that's what we're doing here。

And then we look at the right only bit。If it's set or if the readr bit is set。

 then we are allowed to write to this file so we can set the writeriable flag to true。And finally。

 we look at the truncate bit。 If the truncate bit is set in the flag's value and we are looking at a regular file。

 then we can call I trunccate， and that will truncate the size of the file to0 and release any space that's occupying。

Now， at this point we've got the file， the IP， the i note locked。

 and we've got the reference count increment， so we need to unlock the in。

 but we will keep the reference count increment okay and return the file descriptor。

We keep the reference count increment because we now have a pointer。

 We store a pointer to the file structure in the i note， and we store a pointer to the。Sorry。

 we stored a pointer to the file structure in this open file array。

And we stored a pointer to the iode in the IP field。 So we do have a pointer to the in。

 so we need to keep the i nodes reference count。Incremented to indicate this pointer has been added to the i note。

And so I believe that ends the code for the open system file， for the open。

So I believe that ends the code for the open system call。Next。

 let's take a look at the pipe system call。In Uni systems， including X V 6。

 the pipe system call is passed a pointer to an array， and that array has two elements。

It will create the pipe， and it will return the file descriptors for the read and the right end in this array。

It will return 0 if everything's okay and -1。 if there's a problem。

 So let's look at what's going on here。 here， I'm showing a pro structure for some process。

 and it's got an open file array that has some elements already filled in。



![](img/ba5129da12b5a28c0a39a91ca41a962c_2.png)

And this system call will allocate a pipe structure。

 as well as two file structures shown here and here。

 And then it will fill in pointers from the open file array to these file structures。

So here we've created a pipe structure， and this is the read end。

 this file structure represents the read end， and the readable flag is set to true and the writeable flag is set to false。

And you can tell that this is the right end because the writeable flag is true。

 and the readable flag is set the false。 But both contain pointers to the pipe structure。

 and the reference count for both is one。 And then what the system call will do is it will search the open file array and find the first unused slot and make that point to the。

Read end， and it will find the next unused slot and make that point to the right end。

 And then it will save in this array。 The file descriptor for the read end。 Well， that was two。

 So we'll save two here。 and then it will save in the second slot of this array。

 The file descriptor used for the right end， which was 5。

This array is a fixed size array of two elements。 Each one is big enough to hold an integer。

 So the total size of this array is 8 bys， at least in xV6。Next。

 let's look at the code for Cis pipepe， which implements the pipe system call。

There's no activity on the disk， so we don't see any transactions in this particular function。

We're going to begin by calling Arg adder to get our first argument。

 That's the virtual address of this F D array。 So we are going to store that virtual address into this local variable F D array。

And if there's any problem， we return immediately。Next。

 we call pipe Allc and what pipealoc is going to do is allocate this pipe structure as well as these two file structures and set this thing up here。

And it will return pointers to the read end and the right end。

 That is the pointers to the file structures for the read end and the right end by setting these variables here。

 There's any problem that returns -1 and we return immediately。Now， we have got these two。

 these three structures allocated， and we're ready to fill in these pointers here。

So we're going to call F Allc to find a slot in the open file array and set it to point to the read file structure。

 and then we're going to call Falc again to find another slot in the open file array and fill it in to point to the file structure that represents the right end。

 and then we're going to save these two file descriptors in F0 and F1。Now。

 I have no idea why we're setting F D0 to minus-1 here because whatever happens。

 the first thing we do is call FDc and it's going to return something and modify Fd0。

 but in any case here， if anything goes wrong。 that is either these returns a negative one。

 then we've got a problem and we need to deal with it。 So if we've got a slot for the read end。

 but failed on on the right end， then Fd0 will be something greater than or equal to0。

 and so we need to eliminate that， we need to restore it to be no。

 So that's what we do here But in either case， we close both file structures。

 and remember that with the pipes when we close an end of the pipe。

 it will eliminate that file structure and if it's the last point or to that pipe structure， it will。

Free up the pipe structure itself。 So on the second call to file close。

 we close the last end of the pipe， and that will free the pipe structure as well。 Then we return -1。

But assuming that we were able to store these pointers into the open file array。

 we now have F D 0 being2 and F D 1 being5。So we need to store those into the FD array in the user space so。

This value right here is the virtual address of this FD array and page table indicates the virtual address space。

 So we're using copy out to copy from the kernel space， namely the value that's stored at F D0。

 and the size of F D0。 Well， that's an integer。 So that would be4 bytes。

 And so we're going to copy 4 bytes into the FD array at offset 0。 Okay。

 and then we're going to copy。The value of F1。Okay， and we're gonna copy again，4 bys。

 and we're gonna copy it 2。The virtual address space。

 And this time we're going to copy it into offsetet 4。

 That is the beginning of FD array plus the size of the first element。

 So the beginning of FD array plus the size of the first element will be the second the address of the second element in the array。

 So here we're storing the two and the5 the two file descriptors that is into this FD array in user space。

 And if there's anything wrong here， well， we need to return those file descriptors to null。

 so we store a0 in this element here and a0 in this element there。

And then we close the read file descriptor and the write file descriptor as before and return -1。

 But if these two copy outs worked fine， then we skip that and return 0 to indicate success。Okay。

 the final。File， the final system call that we haven't talked about is the exec。

 And that's pretty involved。 So I'm going do that in the next video。 That's all for this video。

 I'll see you in the next video。