# hhp3《xv6 操作系统内核｜The xv6 Kernel 2022》中英字幕 p30 -30-xv6 Kernel-30_ The File System.zh_en -BV11CkSBsEtN_p30-

![](img/b3e27aa15dd4ba17d772f8eb1ee0b980_0.png)

This video is part of a video course on the XV6 operating system kernelel。

There's a lot of code involved with the file system。

 and I've broken it up into a number of different videos so far I've already talked about the buffer cache system and the disk logging system。

In future videos， I'll talk about the code， but in this video I'm going to focus on how the file system is represented on disk。

 So in this video， I'll talk about the disc organization and layout for directories and files。

Previously when I talked about the logging system， I showed this schematic image of the disk where each one of these squares is a block on disk。

 and we had some stuff， including the log area， as well as a main block area。

Let's simplify that picture and just look at the disk block area。

 so we just have a sequential set of disk blocks on the disk and the code that we've looked at already provides a number of functions that we can use to access these blocks and here I'm showing what it would look like in the code to access the blocks on the disk。

In particular， we have the function B read， which can be used to read a block in from the disk。

 and we provide a block number and it allocates a buffer from the cache and reads the disk block into memory and returns a buffer pointer。

 a pointer to that buffer in memory。 and then we have the log right function where we provide a pointer to a buffer and it will write that buffer data back out onto the disk。

We can read or update the data in that buffer anytime after we call Bread。

 and we can call logrite multiple times so we may write it and then modify it some more and write it again。

When we're done with that particular buffer， we need to call this function B release and。

Between the B read， call and the release， the buffer will be locked。

 which enforces the fact that we have exclusive use of that buffer。

 Only this thread can access that particular buffer。Now。

 a collection of rights are included in a transaction。

 the call to begin up signals where the transaction begins， and at the end of the transaction。

 we should invoke this function in op。There can be a number of calls to log write within the transaction。

 either to the same buffer or to different buffers。 And those are all grouped together。

 And the logging system will enforce the fact that either all of the rights within the transaction are performed or none of them are。

 So it's an all or nothing situation。A file system contains a single tree of directories。

 as well as a bunch of files that are located in those directories。

 and all of these are on one single device like a disk or a USB drive。

The dctories are organized as a tree。 That is， There are no cycles， and it's not a dag。

 A dag is a directeded， acyclic graph。So here's an example of a file system。

 and I've shown the directories in red and the files that are not directories in green。

 And you can see that if you just look at the red， it is a tree。 In other words。

 every director directory has a single parent， except for the root。

The other files that are not directories are shown in green。

 and in some cases you can see that some of these files have multiple parents。And， of course。

 you remember that we refer to files by their path names。 The file itself does not have a name。

 Instead， we refer to it or access it based on its path name。 So， for example。

 this file here could be referred to as slash A slash A slash K。

 Or we could also refer to the same file using another path name。Every directory is itself a file。

 and so we have several different types of files， both directories and regular files in X36。

 we also have a file type called device。 In fact， there's only one device that is located in the directory tree。

 and that is the console， but in general， we could have other devices as well。

 Those are the only three types of files that X36 implements。 but。

Unic systems and Linux systems implement other types as well。

Pssicix is the standard for Uniix and Linux systems， and it specifies other kinds of files。

 So we typically see devices。 We have two different kinds of devices。 actually。

 we have a character device and a block device。 We also have symbolic links。

 which are sometimes called soft links。 We have named pipes and sockets。

 but none of those are available in X V6。 And as I said， files don't have names。

 We use path names to refer to an individual file。I want to take a moment to talk about the difference between hard links and symbolic links。

 Symbolic links are sometimes called soft links。 Just to be clear。

 X V 6 and every Unix and Linux system implements hard links。

 but X V 6 does not implement symbolic links。So a regular file can have multiple hard links pointing to it。

 that is multiple parents。 And in my example here， this file has multiple hard links that refer to it。

 In other words， this file can be located as an entry in both this directory and this directory here。

Every directory， on the other hand， has exactly one parent， except， of course， the root node。

 So each directory can only have one hard link pointing to it。

 That is the directory tree has to be a tree， Where if we include the other files。

 we have a directed acyclic graph。So in XB6， we have regular files， directories， and devices。

Symbolic link is another kind of file， and that's not included in X6， but it is a type of file。

 So what's going on with a symbolic link。 Well， we have a file。 Okay。

 but the file doesn't contain data， it contains another path name And when encountered。

 the kernel will automatically use that path name to locate what we can call the target file。

 So for example， this file here might be a symbolic link。 it doesn't contain any data directly。

 but instead， what it contains here is a path name。 So if we refer to this file。 Okay。

 with a path name C H。 What the kernel will do is it will go down see that it's a symbolic file。

 a symbolic link， and it will then use that second path name， which might refer to。

 let's say this file over here。And then instead of accessing the data here。

 when you do a read or write， for example， you'll be reading and writing data from this file here。

Now a path name is with hard length is either valid or invalid， okay， if we say C G。

 we get to this file， if was a CB， there is no B entry in this directory， so that's a bad path name。

We have another situation with symbolic links。 a symbolic link can become broken。 Okay。

 so we might have a perfectly valid path name to get down here。

 but the path name here might indicate a file that doesn't exist。 It might be a bad path name。

With hard links， the files must be on the same file system or within the same file system as the directory that points to them。

 So everything。Is in or on one device with the hard links。

One advantage of symbolic links is that the pathogen name can point to a file that's on another device in another file system。

And we can run into problems if we try to trace down or locate and follow a symbolic path name that is located on a file system that's not even available。

 So that's another thing that can go wrong with symbolic links。Next。

 I want to define the terms i number and I note。As you know。

 user mode programs refer to files with path names。

 but the path names aren't necessarily unique and they can change。Instead。

 the kernel uses a number to identify and work with files， and that's called the I number。

It's a small integer， and it's assigned to the file when that file is created and throughout the life of the file。

 its I number will never change。After the file is deleted。

 the I number is no longer needed and can be recycled or reused for a new file。

 and that also happens。And it's also the case that the root directory has a fixed and known eye number。

 and that number is one， this is a mistake。The I number of the root is one so that the kernel can locate the root directory。

And files are numbered from one， not from 0。The I number of 0 is reserved to indicate an unused directory entry。

Associated with every file are a number of attributes。The most important one is the I number。

 which is used to uniquely identify each file。The type tells which kind of file we're dealing with in X6。

 we can have a directory file， a regular file or a device in other Unix and Linux systems。

 we have other types as well。Directories and regular files contain data。

 and so if we have a directory or a regular file， we need to know how much data we have and so we have the size in bytes of the data。

We also need to keep track of how many hard linkss point to this file。 Okay。

 that's the number of parents in the tree。 For example， this file has two hard links pointing to it。

If there were no hard links pointing to it， then there is no path name by which we could refer to a file。

 and so we can think of the number of hard links as a reference count when the number of pointers to an object goes to0 in an object orance system the object space is reclaimed by the garbage collector。

 Well a similar thing is going on with the X36 kernel when the number of hard links goes to0。

 the kernel will automatically delete the file。In the case of directories and regular files。

 there is additional data， and so we need to know where on disk that data is stored。

 so we basically have a list of the block numbers that contain the file's data。In other systems。

 not in X36， but in other Uni Linux systems， we have additional information。

 including the timestamp of when the file was created and when it was last modified and so on。

 we also have information about who owns the file and some bits that indicate the permissions to tell how other users can access this file。

The attributes are kept on disk in a small， thick size structure called the Iode。Okay。

 the iode is kept on disk。 It's not kept in any file。

 but these are kept in a separate area of the disk。 So somewhere on the disk。

 there is essentially an array indexed by eye number of these iode structures。

Whenever a file is then used by the kernel， the kernel needs to read in the iode structure from disk and keep it in memory。

 So the kernel maintains a cache of i notess in memory。

So let's take a look at how the iode structure on disk is defined。

 So here we have a structure that shows the on disk iode。We don't see the eye number。 As I said。

 these things are kept in an array that's indexed by the eye number。 So the eye number is implicit。

The type field tells what kind of file this is， and we have several constants to indicate whether it's a directory。

 a regular file or a device。 we also use the type code to indicate whether the iode is free。

 So some of the iodes on disk in this iode array are in use and have a type of directory file or device。

 but others are free and unused and available for future files， and we use a type of0 for those。

If the file is a device， then we also have the major and minor numbers being valid。

And what are the major and minor numbers， This is essentially the device number。

 So the device number is a 32 B number， and it's broken up into 2，16 B fields。

 the major and the minor number。The major number is an identifier to tell what kind of device it is。

 and the mine number tells which device among several it is。 For example。

 if we have three hewlett Packard printers， the major number would indicate that this is a hewlett Packard printer。

 and that will be used to indicate what kind of what routines we should use to access the printer。

 The mine number would tell whether this is printer number1，2 or 3 or whatever。

Then we have the number of hard links。And then we have the size and bytes。

 if it is a directory or a regular file。 And finally， if it is。

 we have the blocks on disk where those where that data will be kept。

 So this is an array of block numbers here。Previously， when I talked about disk logging。

 I presented this schematic diagram for what the disc looks like。

 And I just had the main block area here。 But now I want to present another view of the disc that is more accurate and more detailed。

Let's go through this thing。The boot record is a block that is neither read nor modified by the colonel。

 Its used just during the boot and start up process in order to load the kernel into memory。

The super block contains a number of parameters。 It is read by the kernelel， but not modified。

 Among other things， it tells where the other items on the disc are located。Then we have the log。

 which I talked about elsewhere and won't go into any more detail on here。

Then we have an area where the iode structures are stored。

 we have the bitmap and we have the data blocks。Remember that each iNot is stored in a fixed size structure and these are packed into an array and this array is kept in these blocks。

A small number of i nodes will fit into each block。 So depending on how many i nodes we have。

 including both the ones that are in use and the ones that are free。

 we have a number of blocks that are allocated to。Do to the storage of i notess。

And then we have a bit map。 The bit map is contains one bit for every block on the disk。

 And that bit indicates whether that block is in use or free。 It's really useful。For the data blocks。

 Okay we consider all of these blocks up to this point here to be in use。

 so the bitmap will indicate that all of these blocks up to this point are in use。

 and all of these blocks here are either in use or free indicated by a bit in this bitmap Okay so there's one bit for all of the blocks in this particular file system we only have 1000 blocks。

 So this bitmap would only be as big as required to contain 1000 bits。

That'll all fit into one block of course， but I've shown three blocks here for illustrative purposes。

And the bid is either one to indicate the block is in use or zero to indicate that it's free。

And finally， we have the data blocks， this is where the files and directories are actually stored。

Now let's look at the superb。The super block is essentially a block that contains this structure here。

 and the structure has a number of fields。 Okay， so let's see what's stored in this block on desk。

First of all， we have a magic number。 This is just a constant and the operating system when it reads in the super block。

 will check this number to make sure it has the right value。 And if it doesn't。

 that might indicate that， while this is not the kind of file system we expect or something is dreadfully wrong。

 This disc doesn't contain a file system at all or something else is really the matter。

The size field， in our example， will be 100。It tells how many blocks are available on the desk。Okay。

 the。Number of data blocks is 959 in our case。 So we have that many blocks here， and we have。

200 i notess， so how many blocks is that， well， the kernel will compute that and figure that out。

But in any case， we have enough。Space to store 200 i notess。

 And that means that this file system can accommodate up to 200 files。

 We cannot have more than 200 files。In log is the number of blocks that are allocated to the log。

 and then we have an indication of where that starts， it starts at block number two。

 and then where the iode start， block number 32， and then where the bitm starts， block number 38。

The size of the bitmap will be determined by the number of blocks。 and as I said， with 100 blocks。

 we can actually fit the bitmap into a single block， but I've shown three here。

 even though that wouldn't be the case。So this super blocklock is read in。

From disk at start by this function， read S B。 And then it never changes。

 And so here I have the structure that contains these。

 And you see this is exactly what we saw before。 We have the magic number。

 We have the size in blocks， the number of i nodes， this number of blocks in the log。

 where the log starts， where the iode。Blocks start and where the bitmap blocks start。

 And so that's read in at startup time。In my example file system。

 I showed the edges as being labeled， and that is important because it emphasizes path names。

But that might not be the way you think of directories。Here， I'm showing in the ages labeled。

 but you might think of it as a directory containing a bunch of names and those names each refer to a directory or file somehow。

Well， directories are stored in files， so for every directory there is a file and that file contains a number of blocks and the directory information is stored in those blocks。

Here's what we have in X V 6。 In X V6， a directory is represented as an array。

 and each array entry has both a name and a reference to the file。

 The name has space for up to 14 characters， and the reference to the file is an I number。

The original Uni system had this 14 character limit for file names in XV6。

 we can have up to 14 characters for the file name， and if it's shorter。

 we would terminate the file name with a null character。When we want to look up a file。

 we have to go through this array。Lineally， and that's a bit time consuming in modern Unix and Linux systems。

 we have a different organization for directories that will accommodate longer file names。

 And as you know， some directories contain hundreds of files。

 So we have different data structures that allow for faster look ups。 But essentially。

 it's still the same idea。 You have a name。 And for each name， you have an eye number。

So that pretty much completes the information about how the file system is stored on disk。



![](img/b3e27aa15dd4ba17d772f8eb1ee0b980_2.png)

So next， let's take a look at the MKFS。Function or program。

 which can be used to create or build a file system from scratch。MK。

 F S or make file system is a standalone C program。 It's not part of the X V6 kernel。

 and it's not a user mode program that runs under the X V6 kernel。 Instead。

 it's a separate C program。 It's compiled on your host computer。

 and it runs on that computer just as the chu emulator runs on that host computer。

When you run the make file， it compiles the XV6 kernel and it compiles all of the user mode programs and it also compiles this Mfs program and runs this program as well and what does this make file system program do Well it's going to create the disk image file the disk image file is named Fs do image and this is a file on the host computer and it will be used by chu to emulate the disk So all of the contents of the disk are kept in this file system image file and whenever a reader write command is issued to the disk chu will actually go to this file on the host system to get or put data。

So our disk in XV6 is initialized to have 1000 blocks and each block is 1，024 bytes。

 so that means there is 1000 K bytes in this file， one by in the file for every byte on the emulated disk。

Make fileile system will initialize the disk。 Okay， will create the entire file system。

 It will create the directory tree and it will put a number of files into the directory tree so that when the kernel begins that is at start time the kernel will find the file system already exists so。

What does it do well。Make fileile system will write the super block to the file。

 or that is to the image file actually， it doesn't write anything for the boot record because that's not really needed。

And it will also initialize all the i nodes。 It will initialize the bitmap area of the emulated disk。

 It will create a directory structure and initialize some directories and for each of the user files that is the user mode executables like CA Echo the initial program and the shell and so on。

 it will create a file and add that to the directory of the file system so that when make file system is done。

 this image file will contain an entire complete file system ready to go so that the kernel can boot up and find the file system。

Real Unix and Linux System also have a similar program called makeF System。

And these will initially is not an image file， but a device。

 and they will write whatever is necessary to initialize the organization for the file structure on that device the file system organization that we've talked about for XV6 is fairly simplified and these make fileile system programs for other systems will create file systems with very different and more complex file systems。

 but so these are complicated programs to create the initial file system on a device。

 but in any case， the make fileile system program that we are looking at here in XV6 we'll make use of some parameters will go to the file parameter。

 H and get things like the file system size as the number of blocks to create in the file system as well as the number of blocks to add to the log。

And we also have a number of predefined parameters or macros and constants。 for example。

 the number of bits per block。That we can store for the bitmap or the number of i notess that we can pack into a block in the i note array that will be represented on disk。

 These constants are needed by the。Make fileystem。c program to create the image file。Okay。

 that wraps it up， I'll see you in the next video。