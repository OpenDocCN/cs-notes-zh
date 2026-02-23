# hhp3《xv6 操作系统内核｜The xv6 Kernel 2022》中英字幕 p31 -31-xv6 Kernel-31_ Inodes.zh_en -BV11CkSBsEtN_p31-

![](img/d4bb997f8b5f85a7b57b01018fb882d7_0.png)

This video is part of a series on the X V6 operating system kernel。 In this video。

 I'll be talking about i nodes。 I'll talk about how they are represented and how they are stored in an array on the desk。

 And I'll be talking about how they are represented in memory。

 We have a cache in memory of the eye nodes that we're currently using。😊。

I'll go over some definitions from the files FS。 H and file。 H， and then I'll look at the code in FS。

c。There are a lot of functions， 25 functions in this file， and in this video。

 I will just do an overview of these functions。 I will actually walk through the code of these functions in the next video。

Okay， let's get started。Previously I presented this picture。

 which is a schematic showing the layout of the disc。In this picture。

 each one of these small squares represents a disc block。And we see the area where the log is kept。

 That's here。 We see the area where the iode array is kept， and that's here。 We also have a bit map。

 which is kept here。 and we have the data block area。

 The data block area contains the blocks that store the data of the regular files and the directories。

In the bitmap there's a single bit for each one of these blocks。

 and that bit tells whether the block is free or in use。

The blocks from zero all the way up to here are considered to be in use。 So within the bit map。

 the bits corresponding to these blocks will be a one to indicate that those blocks are in use。

Whenever we want to get a free block to add to a directory or file。

 we will look in the bitmap and it will only find a free block somewhere in this area。Okay。

 next what I want to do is take a closer look at what's going on with the iNots。

 so here I am showing the disc again， here's the log， here's the bitmap， here' are the data blocks。

This area is where the iode array is kept and it starts at some particular block number and that's。

Value is in the super blocklock。 So there's a field in the super block structure called Iode start that allows us to find where this array begins。

 This array contains a number of structures。 Each element in the array is an iode structure。

 And I'll talk about those in a second。They are packed。Together as tightly as possible。

 I'm indicating that we can get four of these structures per block。

 and here's a block right here and here's a block， and each one of these is a block containing four iode structures with a little bit of wasted space at the end。

There will be wasted space if we cannot get an even number of inos packed into a block。

 and in reality these iods are not quite that big so we can actually get more than just four。

 but here I'm showing you that they are packed together like this with some unused space。

Now let's take a look at one particular iode and see what that structure looks like。

 So I covered this before， but let me remind you that it has a type field that tells whether it's a regular file。

 a directory or a device。 If it's device， it's got a major number and a minor number。And in any case。

 regardless of what kind of file it is， we have in link。

 which is the number of hard links that point to it。

 So if this particular file is in say let's say four directories， then the in link will be four。

 This tells how many directories point to this particular file。If it is a regular file。

Or a directory， then it will have a size， the device files。

 would ignore the size and this array down here。And finally， for regular files and directories。

 we have to have the actual data。And so we have an array here of block numbers。

 each block number can be thought of as a pointer to a block up in this data area here。

And that array has a fixed size， which happens to be 12。 So we have 12 blocks here from 0 to 11。

And beyond that， if the file grows beyond a size of 12 blocks。

 what we do is we use an indirect block， so the next pointer。

 okay the 13th pointer points to another block on disk somewhere in here。

 and that block is filled with block numbers or pointers to other blocks。

And since the block number is 4 bytes and the block size is 1024。

 we can pack in 256 pointers into the indirect block。

 So with the 256 blocks that are pointed to by the indirect block and these 12 blocks that imposes the maximum size on any file It's rather limited in XV6 here it's given by these two constants。

 the number of direct pointers is 12 and the number of pointers we can squeeze into a an indirect block is 256。

And production Unix and Linux systems， we have other ways of accommodating bigger files。 For example。

 we might have a pointer that points to a double indirect block。

 So each these pointers points to an indirect block points to the block itself。

 We can also have triple indirect。 And with that， we have a potential maximum file size that's absolutely huge。

But XV6 just has this single block of indirection， and that's good enough for us。

So we don't actually store the iode number。 That's implicit。 So this is the iode for。File number six。

And we will then need to read it into memory where we can work on it。 And for that。

 we have a cache of i nodes that are stored in memory。 So there's an array。

 or I should say a variable called I table as a structure， and it contains two fields。

 a lock and an array called iode。And that array contains a number of structures that look like this。

 and it's fixed to have a size of 50。 so we have up to 50 i nodes out of the 200 that we can be actively working on。

 So if we are working on a file that is it's open and we're accessing it。

What the kernel will do is it will read the structure from the disk into one of these cached structures。

The cache Iode contains all the fields that are in the inode on disk。

 type major minor in link size in the address array。

Tight major minor in link size and the address array。

 as well as some additional fields for one thing we need the I number， as well as the device number。

In X V 6， we only have one device that can contain file systems， but in other Unix systems。

 we will have several devices that are currently being used。 So in order to identify the file。

 we need not only the device number， but the I number。诶。

And the i numbers are unique on each file system that if we have several file systems， the I numbers。

 we can have some confusion because I number 6， just as it's I number  six doesn't say which file system that's in。

 so it could be either this file system or some other file system。

 So that's why we have the device number here。The reference count is the number of pointers to this structure。

 or you can think of it as the number of threads that are currently using this cached in。

Within this cache of 50 iNots， the reference number will tell which ones are free and which ones are in use。

 if the reference number is zero， then it's free and it can be used to cache a different iode。

 but if it's in use， the reference number will be something greater than zero。

The structure also contains a lock。 Oh， I've labeled these wrong。 The lock field is a sleep lock。

 and the valid field is a flag。And the sleep lock protects this。

 So whenever the kernelel wants to read or update any of other field in the iode。

 it must be holding the sleep lock called lock。At some point。

 the particular element in the cache is allocated to some iode and the i numbers filled in along with the device and the reference count。

But the data may not be read in immediately， so the valid flag tells whether the data has been read in from disk or not。

 and if it's zero， then we need to go ahead and read in from disk if we're going to look at it。

The fields up here， the device number， I i node number and reference count are protected by a spin lock in this i table structure。

 and that spin lock protects all of these。 So when' we allocate an element from the cache to be used for a particular i node。

We will need to first grab the spin lock and then set the I number and the device。

 as well as incrementing the reference count to one。

There's another variable called device switchitch， and that's an array it happens to be containing1 elements as given by this constant number of devices。

Each element in the array is a structure， and I've shown one of them enlarged here。

And for each device， there is an element in this array and what does the array contain Well it contains pointers to functions。

 So for example， element number one is the console whenever we do a reader write to the serial output。

 we need to access this device and so for the console device we use these two particular functions to perform the read and the write for other devices。

 we might have different functions。 So these are essentially the device drivers that are specific to device number one。

So for the console device， the read function takes a destination address。

 this is a buffer and kernel memory where well it's a buffer where we're going to be storing the characters that we read。

 here we have a by count that's how many characters we want to read and here we have a flag the first argument is either zero or one to indicate whether this destination address is a physical address and kernel address space or whether it's a virtual address in some user's virtual address。

And it returns the number of bytes that we have successfully read。Likewise。

 there's a console write function， it takes the address of where the characters are and how many bytes there are that we want to write out to the console。

 as well as a flag to tell whether this address is in the kernel space or the user's virtual address space and it returns the number of bytes written。

In X6 this array is not really used very much， in fact。

 the only element that has anything in it is device number one and so that's the console device。

 It's a bit confusing because the file system is also on device number one。

 but that's just the way it is， so we're only using this device array for the console but here you get the idea that for different kinds of devices we could have different routines to be used for them so the major number would be used to index into this device to tell us which functions to use and the minor number would probably be passed to the driver to indicate which device to send it to。

Now let's take a look at the file fs。h。In the real world。

 there are several kinds of file systems that are in common use， and here's some examples， EXD4。

 the file system used by Min， XFS are some common ones。

 we might call the file system format used by X36， X36， FS。

A real operating system is going to need to be able to handle several different file system formats。

X36 could only handle one， and the definitions that are related to the on disk file system formatting are contained in this file F S dot H。

So let's go through and see what it's got。First of all。

 we need to be able to locate the root directory， and that is iode number one。

The block size for the blocks on this disc is 1024。

The second block that is block numbers one is the super block。

 it's a block that's read in at startup and it contains a number of values and these values never changed and this block has never updated。

 This just basically tells us where the log and the Bimap and the Iodeode array are on the disk。

Here's the magic number that's related to this field。I know it's contained 12 direct pointers。 Okay。

 that's this number here。 And the indirect block will contain。

A number of pointers given by this constant here， we take the block's size and divide it by the size of a block number。

And that's the 256 number I referred to earlier。The files have a maximum size determined by the number of direct pointers plus the number of indirect pointers。

 so that's 12 plus 256， and given that the block size00 is 1024 bytes that imposes a maximum size on every block。

The iode， as it's kept on disk， has this structure here， the type， the major and minor numbers。

 the number of hard lengths， the size and bytes， and this array with 12 direct pointers and one indirect。

Block， which is pointed to by the 13th element in this array。Mis go to the next page， which is here。

This constant here is the number of i nodes we can squeeze into one block here I indicated it was four and maybe the block size is evenly divisible by the size of the iode structure or maybe it's not in which case we have a little bit of extra space。

 but in any case it's not really four， it's given by this i nodes per block value here that is determined by the size of the block and the size of the iode structure。

Okay which block on disk will contain a particular iodeode so this function。

 this macro preprocessor function i blocklock is past an iodeode number and pointer to the super blocklock。

 which is a structure in memory that has things like where the iode array starts In my example I started it at 32 and so we just do a little bit of division here by the iodes per block and add 32。

The bidmap will contain a number of bits in each block。

 and the number of bits in each block is just 1，024 bytes times 8 bits per byte。So。

 given a particular。Bit number or block number where which block in the bitmap will contain that bit Okay。

 so B is the block number and this B block will compute be divided by the number of bits per block and where the bitmap starts。

你。Directory contains a bunch of files， and each file can have up to 14 characters in its name。

 And so that's directory size here。 And the directories will contain a number of these directory entries。

 which has each one of these structures has。And an iode number and 14 characters。

 so it can accommodate a file name， size up to 14。Okay。

 now I also want to take a look in of this file file do H。

 which contains a number of different things， but in particular， it contains the in memory i note。

So remember that our cache is made up of 50， it turns out to be 50 of these iode structures。and。

We have the fields that I talked about in this picture here。Here is the structure。

 as I showed it before， device I node number and the reference count。

 So device I know I node number and the reference count。 and then we have a sleep block。

 and here's the sleep block called lock。 and this sleep lock protects everything below that。 Okay。

 so we have the tight major minor in like the number of hard length size and the pointers。

It also protects the valid field， I didn't really draw this quite correctly。

 but the sleep block corrects the valid flag as well。And then I mentioned the device switch。

Aray and that's given right here。 these are the structures and each one is a structure that contains two pointers。

 a read and a write field。 So that's was shown in this picture here。

 This structure here contains two fields called read and write and each of these is a pointer to a function。

 okay， the function takes three arguments。

![](img/d4bb997f8b5f85a7b57b01018fb882d7_2.png)

And returns on integer value。And the array itself is declared elsewhere。Okay。

 that's it for oh oh wait， we also have this console。

 which is the number in the array of the console device。

There are a couple of other definitions that I wanted to cover， and these are coming out of the file。

 Fs。c， not。h。Here is the superblock variable SB， where the superblock is read into at startup time。

Then we have a macro function called minimum， which is defined pretty much as you would expect it to be。

 Remember that as a kernel programmer， you have to define everything you're going to use。

 You can't rely on library functions that you would normally rely on as a regular programmer。

There's something else that I wanted to mention and that's the eye table structure here is the picture of it that I used。

 this is where we have the cache of inots。And it has a spin lock。

And it has this array of iode structures that we will use as our cache。

And I also wanted to mention something from the file。File。 C。

 and that is this array I discussed previously called device Switch， which has 10， as it turns out。

 elements。I won't talk about the rest of this stuff right now， but I'll cover this in a later video。

There are a lot of functions in Fs。c， in fact， there are about 25 functions。

The code in some of these functions is pretty complicated。 and before I get into the code itself。

 I I want to just introduce these functions by name and talk a little bit about each one of them。

The first three functions are concerned with initialization。

I in it is for initializing the cache of inots。File system in it is past the device number and it initializes things and among other things。

 it calls readSB， which will read in the superblock from the disk and store it in this super blocklock structure。

The function B0 is past a block number， and it will go out to disk and write all zeros to that block。

B ac is used when we need to allocate a block， for example， when we're growing a file。

 and so it will search the bitmap to find a block that is currently free。

 and it will change the bitmap to indicate that it's now in use and return the number of that block。

To free the block after were done with it， we can call B free， which is past a block number。

 and it will change the bit in the bit map to indicate that the block is now free。

The IalLc function is used when we're creating a new file and we say which device we want to create it on and the type of the new file。

 this could be a regular file， a directory or a device file。

And it returns a pointer to the iode that is to a structure in the iode cache。

What it will do is it will read the disk to locate an unused iode in the iode array。

 And so at that point， it determines what the I number of the new file will be。

 Remember that the I nodes in this array will have a type value of 0 to indicate that they're free。

 And so this function will set the type。On the disk to indicate that that eye node is now used。

And then it will call I get and return a pointer to the in。And so what does I get do， Well。

 at this point， we've got the I number of the new file， and we allocate a。

Structure in the iode cache。 Okay， if we already have a structure for that particular I number。

 then we go ahead and use that one。 But in either case。

 we increment the reference count to indicate that this particular iode in the cache is in use。

 We will not actually read in the iode data from the disk。

Remember there's a valid flag in the iode structure。

 and so that may remain zero to indicate that there's no valid data and each iode in the cache has a lock associated with it。

 and I get will not set the lock。Okay， if we want to set the lock， we can call eyeL。

 which is past a pointer to the eye node and it will set the sleep lock in the eye node。Furthermore。

 if the data in that node is has not yet been read in from disk。

 then the valid flag will be false or zero。 and this function will also read in the data from the Iode structure on disk and store it in the cache version。

And there is an I unlock function， which will simply unlock the ionode。Next。

 we look at the I update function， and this is past a pointer to an iode in the In cache。

 and after we've made changes to the in， we need to write that iode back to disk。

 and that's what this function will do。From time to time， we need to increment the reference count。

 and so we can call I dope to increment that reference count。

Remember that the reference count is protected by the lock for the entire cache。

 the i table dot lock field， so it'll have to set that in order to increment the reference count。

And the I put function is past pointer to an in， and it will decrement the reference count。Now。

 if this particular thread is the last thread that's using that iode in the cache。

 then the reference count will have gone to zero。 And at that point， we can also ask。

 or this function will also ask whether there are any hard links to this file and if in link of0。

 it means there are no references to this file from any directory。 So at that point。

 this file is not accessible。 There is no path name which can get to it。

 So this file needs to be released and freed。 the space associated with it has to be freed。

 So what it will do in that case is lock the inode。

 trunnccate the file to a link of0 which will free all the data blocks and then it will call this I update function here to write the modified iodeode back to disk。

And at that point， the。The file is freed。The function I unlock put is just calling I unlock。

 followed by I put。And then we have this BMap function。It's past a pointer to an in。

 so we've got some file that we're concerned about and we've got the in cached in the in cache。

And we are trying to get some data out of the file or perhaps write data into the file。

 So we figure out which block in the file with the first bite of the file being in block 0 of that file。

 So we have the block number relative to the beginning of the file。

 And we need to translate it to a block on the disk。 And that's what Bmap does。

 So it will consult the。The array of block pointers of direct block pointers。

 And if it is a block beyond the 12th block， it will look at the block of indirect。

 and it will find a pointer to locate the block。On the desk。

 so it will figure out the block number on the desk。

If that block is not actually allocated in the file， okay it's not in the file。

 then this function will also allocate a free block and add it to the file。

 and it will also update the in by adding it to either the array of direct pointers or the block of indirect pointers。

Next， let's look at the function I trunccate， which is past a point or to an iode。

 which is in the iodeode cache， and it will truncate this file to size0。

 it will free all the data blocks in this file and it will free the indirect block to if there is one and set the size attribute to zero and call I update to update the iodeode on the disk this is called among other places from the i put function。

 remember with iP we basically call this when we're done with the particular file and it will decrement the reference count。

 and if there are no hard links to it， then it will truncate the file to length0。

It calls I update as well as I truncate。 And you might think， well， gee。

 that is a duplication of effort。 It's writing to the disk twice。 But remember。

 we're using the disk logging system and。So there will only actually be one right to the desk。

The reason we call I update here a second time is because we are also setting the type field to zero。

 which I did not include in this， so let's add that there。

 and we need to set the type field to zero and then write that to the disk so that the on disc iode structure will have a type of zero which will indicate that this particular iodeode is free and can be recycled。

Okay， the next function is Stat I， and this is past a pointer to an in and to a structure called a stat structure and all it's going to do is copy data from the iode to someplace else。

Now we want to look at the read eye and write eye functions。

 These are used to actually move data into or out of a file。

 so read eye is called with a point or two an I know that's in the cache and a destination address of where to put the data in memory。

 as well as an offset。In the file of where to get the data and the number of bytes to transfer。

This destination address is either a physical address or it is a virtual address in some user's virtual address space。

 And that's determined by this flag 0。 if destination address is a physical address， one。

 if it's a virtual address， and it'll return the number of bys red。诶。

The right eye is just the other direction， and here we have the same arguments。

 the pointer to an Iode， the flag， the source from where we're getting the data and the number of bytes and where in the file we will be writing it to。

 and then it returns the number of bytes correctly written。

And then we have the function directory lookup。And this is past a pointer to an i node。 Okay。

 that's a directory file， or at least it should be a directory file and。A name okay。

 this is something that's 14 characters or viewer， and we also have an offset variable and well pass the address of that。

 So what it's going to do is it's look this name up in the file that's pointing to by this iode here and if we find this name in the directory then we're going to call I get which will add an iodeode for this file in the iodeode cache。

 it will not lock it okay。And it will then return the iode of the file that we just looked up。

In addition， we've got this offset variable and so。

This function will also save the offset in the directory of the directory entry for this particular file。

 so it will say the location of this directory entry within the directory array。

 the directory file in this variable offset。And if the style is not found， it will return zero。

The next function to look at is directory link， which is used to add an entry to a directory。

 so it's past a pointer to an Iode that represents the directory。

 as well as a pointer to a name and the I number， and it will add a name number pair to this file。

It will return 0 if everything would O and -1。 if there's a failure and the failure can happen if there is already an entry for that name in the directory。

And this function will do reads from the disk as necessary to check。 And after it adds the entry。

 it will write that back to the disk。By the way， all of these functions that we've talked about so far are reading from the desk。

 and many of them are writing as well with a log right operation。

These reads and the corresponding write and the releases， the B release function calls。

Are all part of transactions， but none of these functions include the transaction itself。 Remember。

 the transaction begins with a call to the begin op function and ends with a call to the end op function。

 None of these functions in F S dot C in the file， F S dot C。Contain calls to begin up or end up。

 but they are all used within code that is part of a transaction。The next function。

 skip element is not a function that accesses the disk。 It doesn't do any reading or writing。

 It's simply a string processing function。It's past a pointer to a path name string somewhere in memory。

 such as this string right here。 and so it's past a pointer to the first character。

 and it will parse it essentially， it will find where the first element is and it will store that in a variable called name。

 So it's past an address of some 14 byte area， and it will store whatever the first element in this path name is。

 And in this case， it's the character's USR in the name variable。

 and it will also advance the pointer to the next element in the path name and return a pointer to the next element。

 so it will return a pointer to this。 if the path name is empty。 and there are no more element。

 it will return0。Okay， finally， we have this name I function。

 and this is what we've sort of been working toward。 We're past a point or to a path name。

 and it's going to find that file on disk。Move the iode into the iode cache and return a pointer to the cached iode。

 So the iode will be cached， and the reference count of that iode will be incremented。

 It will not be locked。 And if the file doesn't exist。 If this path name is no good。

 then this function will return null or 0。There's also a variation of this that will do exactly the same thing。

 It's past a pointer to a path name and it returns a pointer to the iode in the cache。

 but it will stop one level earlier。 So basically， if it's past this path name here。

 it would return a pointer to you the director user slash bin。 Okay。

 and it will save cat in this name variable。 So it will stop one level earlier in the path name。

 save the last file name that is cat in this name variable and it will return the iode of the parent directory。

And both of these are quite similar， and all they do is call the function name X。

 which actually does the work of both the name I and the name I parent function。

 So name X is passed a point or path name and a flag to tell whether it's doing the name I function or the name I parent function and the name variable。

And does the work of both name I and Na I parent， and nameex is not called from anywhere else。Okay。

 that's it for this video。 In the next video， I will start looking at the code for these functions。

 See you there。