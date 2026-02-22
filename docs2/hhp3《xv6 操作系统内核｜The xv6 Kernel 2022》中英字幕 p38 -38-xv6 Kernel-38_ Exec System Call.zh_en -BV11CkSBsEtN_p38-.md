# hhp3《xv6 操作系统内核｜The xv6 Kernel 2022》中英字幕 p38 -38-xv6 Kernel-38_ Exec System Call.zh_en -BV11CkSBsEtN_p38-

![](img/ffde5795273a39d332abc0f1b1621670_0.png)

This video is part of a series on the XV6 operating System kernelel and is in fact。

 the last video in that series。In this video， I'm going to describe how the Exec system call works。

 This is essentially a culmination of all you've learned so far。 It's a pretty long video。

 but I think you'll see that it's really quite interesting what happens in the Ex system call。

I will go over the E file format， at least in vague outline。

 and then I will cover the cis exact function and the exact function from file cis file dot C and Ex dot C。

 Okay， let's get started。In order to understand the exact system call。

 we need to understand how the executable file is laid out。

The executable file will be in the elself file format。😡。

There are a number of different file formats that are used on different systems。

 The Eth format is used in the UniX world。In the Apple world， we have a file format called Mo O。

 And for Windows， we have the portable， executable file format。 These are all sort of the same。

 but the details differ for each one。The L file will begin with a fixed format file header。

 and that tells where the other parts of the file are located。

The header is followed by an array of program headers。 Each program header is exactly the same。

 They have the same size， and so on。And that will be followed by a number of segments。

The actual code that's to be loaded into memory will be located in these segments。

 and these segments can have different sizes， as you can see here。

Each segment will be pointed to by exactly one program header。

 and that will contain information about where in the executable file the segment is located。

The segments can be followed by some other stuff， for example。

 we can have something called the section headers。In the case of relocatable files。

 this would contain information about how to relocate the machine code that's in the segments。

 We could also have some information about debugging and so on。

 I won't be looking at this section header stuff at all。

Now let's take a look at the file header here。And I'm showing it in more detail here。

There are a number of fields， and let's go through some of these。The first is the magic number。

 and this should contain exactly these four bytes。These can be checked to make sure we're dealing with an L file。

 If there's a mismatch here， then clearly this file is not an e format file。Of course。

 if the magic number correct， the file can still contain errors。

 either due to bugs or perhaps malicious code。The next field here indicates whether this is a 32 bit file or whether the data in this file is 64 bits。

And the next field indicates whether the data will be in little Indian format or big Indian format。

I'm not sure any exact sizes of these fields here。And I'm not sure in the offset within the file header。

 These will actually change。 They are different versions of the else file。

 depending on whether it's 32 B or 64 B。But let's just move on。

The executable code could be for one kind of a processor or for another kind of processor。

 And this field called machine indicates whether it's for for example。

 the X 86 architecture or the X 86，64 architecture。 There's also a code for the risk 5 architecture。

 So we would expect this field to contain Hex F 3。The executable code might be intended to run on a different kind of operating systems。

 So this field called O。Application binary interface contains a code to indicate which operating system that this file is meant to be run on。

There's not actually a code for the X 86， but we don't even look at this field anyway。 So that's。

 that's okay。The L file format is normally used for executable files。

 and it's also used for relocatable files。When the compiler runs。

 it will compile the source code and produce an object file。 That is a dot O file。

 And that file will be a relocatable file。 And in the Uni world。

 the relocatable file will also be an L file format file。

 So this indicates whether we've got a relocatable file or an executable file。The relocatable files。

 the object files， will be processed by the linkr， which will then produce a file in the executable format。

The L file format is also used for other things， for example， for core files。

When a program crashes or has some kind of an error。

 sometimes we want to capture the contents of main memory for the purposes of debugging。In that case。

 we can create what's called a core file and that core file can also be stored using the else file format。

But we will only be looking at executable files。The program header offset and program header number indicate where in the file we can find the array of program headers。

 so the offset says where in the file this array begins。 That's this location here。

 and the number indicates how many program headers we can expect to find in the L file。And finally。

 we have the entry point。This contains the address at which execution should begin。

This might be the first byte of the main function， but typically there will also be some prologue code in the executable file。

The prologue code will be the code that actually calls the main function。 And so in that case。

 the entry point would be the address of the first byte of the prologue code。

So after the colonel loads the executable into memory， it will then jump to the entry point。

 and execution will then begin。In the H36 system， we ignore a lot of these fields， and in fact。

 we will only be looking at the magic number。The entry point and the program header offset a number to find the program headers。

 The other fields will be completely ignored。So now let's take a look at the program headers。

 So we have in this example， four of them。 and each one of these things has a fixed format。

 And here I'm showing the program header structure。It has a number of fields， and as I said。

 it's a thick size。The first field is the， is the type field。

 and there are a number of different types， but we will only be concerned with loadable segments that's indicated by a code number of one。

The flags field indicates whether this segment should be marked as executable。

 writeriable or readable。 So these particular bits in this flags word indicates whether the segment。

 when it's loaded into memory， should be marked as executable and or writeriable and or readable。

The offset field tells where in the L file we can find the data。

 So this points to this segment and the file size field indicates how much data is in that segment that is how big the segment is。

The data in this segment will then be moved into main memory by the colonel when the executable file is loaded。

So the virtual address field tells where and memory to place this。

There's also a physical address field in most Uni systems， we are dealing with virtual memory。

 so certainly in X6， we are only concerned with the virtual address。

 so that's where in the virtual address space we're going to load or move this data segment。

The physical address will be ignored in XV6。As I said。

 the file size tells how many bytes are in the file for the segment。

The memory size tells how many bytes in the virtual memory address space are to be occupied by this segment。

The memory size can actually be larger than the file size。 It cannot be smaller。

 but it can be equal to or larger than the file size。If it is larger。

 then we are the kernel is supposed to fill in the remaining bytes with zeros。

So if we actually have zero bytes in the file， we can use the program header to indicate a region of memory。

 region of virtual addresserspace that should be entirely filled with zeros。 so in that case。

 the file size would be zero and the entire segment in the virtual memory would be zero filled。

Finally， we have an alignment field that's actually ignored。 In fact。

 we assume that the segment will be loaded into an address that is page aligned。But in other systems。

 we might have different alignment requirements for the segments。In X6。

 all of our segments will be aligned beginning on a page boundary。

The file else dot H contains a number of definitions that are related to the file format。

 So let's take a look at that。 We begin with a structure that defines the layout of the file header in the file。

 And so here we see a number of fields that I showed。 there's a loose correspondence here。

 We see the magic number， we skip over a bunch of stuff。 Here we have the type field。

 the machine field。 Here's the skip some stuff。 we have the entry。 the program header offset。

 and down here we have the program header count。 We have some additional stuff for the section headers and some other things that we will ignore。

 As I said before， we only are concerned with the magic field。

 the entry field and the program header offset and number。We have a constant up here。

 which is the magic number， I showed it here， but we're giving it in little Indian format。

 so we have 7F，4，5，4 C， and 4，6， okay given right here。And then we have the program header。 Okay。

 so let me。Show the program header。 I described it here， and the correspondence is straightforward。

 We have the type， the flags， the offset， the virtual address， the physical address。

 which we don't use。The file size and the memory size。 and finally， the alignment value。

 which we also ignore。We have some other constants in the program header， we have a type field。

 and here is the code number for an executable segment， a program loadable executable segment。

And here we have the codes for the bits here in the flags word。

 or we have the executable writeriable and readable bits。

 and those are just given with these constants here。So here is the exact system called。

 It's past two arguments。 The first is a pointer to a path name that describes the executable file that we like to load and execute。

 And the second argument is a pointer to an array， and these are the arguments that will be passed to the executable file。

 This array contains pointers to strings that are null terminated， and it ends with an entry。

 that is a null pointer and。These are in the virtual address space。In Uniix systems。

 there are several other variants of the exact system call， but XV6 has just this one。

 and this is the main one that gives you the idea of what's going on。

 So when this system call happens， the kernel will go into this cis exactec function。

 This is coming out of the file。 cis file do C。 And what it needs to do is get these strings。

 this argument stuff from the virtual addresser space of the process that invoke the exact system call。

 and then it will call the function exec to actually do the work。

 So let's step through the cis exactec function。The first thing it's going to do is copy the path argument。

 And we saw the argument string function earlier。And it's going to copy that into a local variable called path。

The second thing it's going to do is get the second argument。 This is an a0。 This is an a1。

 and it's going to copy the address of the array。 That's a virtual address into this local variable U R。

 So at this point， I can just draw this line here to indicate that that gets stored。

The next thing it's going to do。 Well， we've got this R V array， and it's fixed size。

 It can accommodate up to 32 elements。 Actually， that would be 31 arguments because the last argument has to be followed with a null pointer。

 And that's given by this max Arg constant。 So the next thing we do here is we set all entries in that array to 0。

 So here， I'm showing the array。 So let me just draw it like that。

 And we're setting all the elements to null。 Okay， later， we'll go ahead and change them。

Then we have a loop here， which is going to walk through all of the arguments。

 So it starts at I0 and just increments。Okay， and the first thing we do is check to make sure we haven't gotten more arguments than we can accommodate。

 So we have to have room for， we have room for up to 31 arguments。 plus the final nu。

 So here we're checking to see whether we have gone past the last element。 And if so。

 we go to this label bad。 Okay， I'll come to that in just a second。 But basically。

 we're gonna return -1。 at the label bad。Next， what we do is we go into the virtual address space Okay。

 and we fetch the value that is stored at some particular location and what location are we interested in。

 Well， we're interested in the。Address of the users array plus I times the size of the entries。 Okay。

 so this is the user's array。 And we add I。 And so we go in and we get a pointer。 Okay。

 to one of these strings。 And then we store it in a local variable called U A。 Okay。

 so U R is a local variable here。Let me just illustrate this for one of the examples。

 Let's assume we've gone through a couple of times， and now we're on I equals2 here。

 So we've already filled in a couple of elements。 but on the iteration of the s where I is now two we fetch this pointer and store it in U Arg Okay。

 so we go to the this element here and we fetch that。 So now U A points to this string。 that's。Sorry。

 you are points to this string here， the second element。If there's a problem， then we go to bad。

 but then we check to see whether we got something。 Okay， if we got the last element here。

 if we got a null， then we are done， we need to store a null in the R V array， and we do that。

 and then we break out of the loop。Otherwise， what we're going to do is copy the string。

 Remember that these strings are in the virtual address space。

 and we need to move them into kernelel's memory somewhere。

 So the A V array is a local memory for this particular function。

 And what we're going to do is allocate a page for each and every string。So for this string。

 we're going to allocate an entire page and copy it。 So here we're， here's the page we allocate。

 and we're going to copy all the characters up to the terminating null into this page。

So that's what's going on here。 We allocate the page。 Okay， And if we failed with the allocation。

 then we go to this bad label。 But otherwise， we call fetch string。

And fetching is past the virtual address。Okay， and it's past the place where we're going to copy it to。

 Okay， that's the pointer to the page。Okay， up here， after we allocated the page， we saved it。

 So I forgot to draw that line。 So let's go ahead and save the pointer。To this page。

 this newly allocated page。 And then we call fetch string。

 which will copy up to a full page worth of bytes into the。

Page that we just allocated in kernel space。 This particular function will copy the final null by。

 and it will return -1 if there wasn't enough room to copy the entire string plus the null bitete。

 And if there's a problem with that， we go to bad。Okay， so now we can take a look at bad。

 bad is just going to loop through this array， loop through the R V array。

 And for every element that is not null， we will just call K free to get rid of these pages。

 return them to the free pool， and then we'll return -1。

But assuming that we go through all the strings and finally exit when we hit the null pointer。

 we will then call the exact function passing it the local variable path。Okay， that's here。

 And the R V array， the pointer to that array。And we call exec， exec， ideally， will not return。

 It will result in the executable file being loaded the previous process。

Will have its memory returned and that we will never come back here。 But if there's any problem。

 this function will return to -1， and then we can return -1 to the user process that invoked the exact system call。

 But before we do that， again， we need to go through this array。

 and free all of the elements that have been allocated。Next。

 let's take a look at the exact function from the file， Ex dot C。

This function will complete the work of the exact system call。 It's past a string。

 which is the path name of the executable file and a pointer to an array。

 That array contains pointers to strings， And those are the arguments to pass to the new executable program。

It will return -1 if there is a problem， but if everything goes okay。

 then it will begin executing the new program in the new virtual address space。

So it begins by starting a transaction。And calling the name， I function。

Name I is passed the path name of a file， and it will go out make sure that that file exists and load an iode for that file into memory and return a pointer to that iode。

If anything goes wrong， then the transaction will be ended and we'll just return -1。

 But if everything's okay， then the i note will have its reference count incremented。

 And I've shown that with this line here。And then the next thing we do is we lock that iode。

After that， we begin by reading in the header from the L file。

 so we've got this local variable here called L， which will contain an header structure。

 and we read in from offset0， this structure and we place it into this local variable and this flag indicates that that variable within kernel space and this is the iode pointer and if there's anything wrong。

 we will jump to this bad label， which I'll discuss in a moment。But if everything's okay。

 we next checked the magic number for the else file and the magic number is this constant of 7 F，4，5。

4， C，4，6。 And assuming it's okay that we keep on going。

 And the next thing we do is we call proc page table。😊，Now， this code is executing within a process。

 and that process has a virtual address space。 and if anything goes wrong。

 we will have to return -1 and return to executing the code that's in that virtual address space。

 But if things go okay， then we're going to create a new virtual address space。

 and load the executable program into that virtual address space。

 So here we're creating the second or the new virtual address space and this local variable page table will point to the newly created page table。

This function here needs to have a pointer to the current proc structure。

Because it needs to add a trap frame to the top of this virtual address space。

 and it needs to know which physical page to use for that particular page in the virtual address space。

 If there is any problem in allocating this page table， then again， we will jump to this bad label。

 But otherwise we keep going。 So let's continue here。And the next thing we see is a for loop。

 And what this for loop is going to do is go through the program headers。

 Remember that the L file contains an array of program headers。

 So that's what this loop is going to go through。Here we see offset。

 and that's the offset of the first program header。

 and we are incrementing by the size of the program headers here。We've also got this index I。

 which is being incremented， and that allows us to stop after we've done each of the program headers。

We call read I here to read in the first or the next program header into this local variable， P H。

So going back to the top of the exact function， we see the local variable pH here。

 which is big enough to hold a structure for the program header。

And this is the in and this address here is in kernel memory。 This is the offset。

 the current offset for the program header。 And if there's any problem， we go to the bad label。

Then we check the type field of the program header。

The type field had better be a one to indicate that it is a loadable segment。

There might be some other kinds of segments， although I don't know what other kind of segment we might find in an executable file。

 But if we find something besides that， we would just continue and repeat this loop。 That is。

 we would skip anything that is not a loadable segment。 But if it is a loadable segment。

 we continue here。 And the next thing we check is mim size。

 And we make sure that it is not less than file size。Okay， remember that in the。File。

 we have a segment， and the size of that segment is file size。

 and we're going to initialize a chunk of memory in the virtual address space。

 And the size of that chunk is mi size。 And it better be at least as large as file size。

 So it ought to be able to contain all of these， these bytes here。

 So we're checking that to make sure that we don't have a problem there。😊，Next。

 we're adding V adder plus mim size and checking it。 And what's going on there。 Well。

 remember that V adder and mim size are unsigned integers and just to refresh your memory。

 whenever we have unsigned integers， and we add them， there is a possibility of overflow。

And if overflow occurs， then the answer will be incorrect and if overflow does not occur。

 then the answer will be correct。 And if the answer is correct， and there's no overflow。

 then the sum will be greater than or equal to A and will be greater than or equal to B。

 because these are0 or larger。 However， if and only if there is overflow。

 then a plus B will be less than a and less than B。

 So what we're doing here is checking to see whether we've got overflow。

 So that's what's going on here。Remember that the kernel can't trust the code that's running in a process。

 a user process， and it can't trust what's going on inside an executable file。

 So we need to make sure that we don't have overflow when we add these two things together down here。

 Otherwise， the kernel might be get get confused and we might have a problem。

 So that's why we're checking for overflow here。The address。

 where we're going to be loading the segment in virtual address space had better be a multiple of page size。

 That is， it had better be page aligned。 and we're checking that here。Then we call U VM Alc。

 U VM Alc is used to grow a virtual address space。 So here's the pointer to the page table for this new address space that we're creating。

 And here's the old size and here's the new size。 So we're providing a size here that it is at least large enough to contain the。

😊，Segment that we're going to be loading。 So this is the virtual address， right， plus the me size。

 So we're making sure it's at least。This big， okay， and this will return the new size。

 if everything is okay。 If there's a problem， it will return 0。

 So that's why we're using this local variable here， C Z 1。 we if there's a problem and it returns 0。

 okay， then we're going to jump to bad and bad will need the size variable， the old value。

 So that's why we're using a temporary here。 But if everything's okay。

 we then go ahead and update the size variable。Now， this X V6 code happens to be changing。

 and since I made the video where I discussed the UVVM aLEC function。

 the code has actually been modified， and now the UVVM aLEC function takes an additional parameter in the video where I cover this function I did not have this additional parameter。

 but now it has this additional parameter。The way I describe U VM Ac， it allocates the pages。

 and for each page， it will mark them as accessible in user mode， readable， Wriable and executable。

 However， that is changed。 And now the current version of U VM Ac will mark each page as。

Accessible in user mode and readable。 And it will take this additional argument。

 And this additional argument will tell whether to market as executable and or ridriable。

So this little helper function flags to perm is。Given right here， so let's take a quick look at that。

Remember that's in the program header。 We have a flags word。

 and that flags word contains some bits and。The first bit is the ecutable。

 and the second bit is writeriable。 Okay， so flagags2 perm is going to take such a word。

 and it's going to look at the writemost bit and the second bit， and if the executable bit is set。

 then it will build a permissions where the page table entry bit for executable is set。

And then it looks at the second bit。 and if that is set。

 it also will set the page table entry sriable bit， and then it will return that new permissions。

 and that can then be passed to the UM ac function。

 So that's what's happening with this last argument here。So。Let's at this point， take a look at bad。

 If anything goes wrong here， we jump to this bad label， which I have right here。

So here's the end of this function。We may have a transaction in progress。 So here's what happens。

 We first look at the page table。 and if we've managed to get far enough to allocate a page table。

 then we need to return all the pages that are involved back to the free pool。

 And so we call Proc free page table with this page table and the current size。

 And so that's why we had to use this CZ1 temporary variable because we we need size right here。

And this will free the page table and return everything to the free pool。Likewise。

 if we've got the i note for the executable file still open。

 then we need to call put and unlock and we need to in the transaction and then return -1。

We will see， okay， going back to this loop here after the loop ends， we unlock。

 we call the put and unlock an endop， but there are other places where we call bad like down here or we will be outside of this transaction。

 So that's why we check it that way。So after we allocate space in the virtual outer space that we're creating。

We need to actually load the bytes or move the bytes from the file to the virtual address space。

 So we have this helper function load segment。 And that's what it does。

 So the file size field tilt how many bytes are in the file。😊，And。P H offset tells。Where in the file。

 those bytes begin。 So we're moving it， the bytes from the file。 and we're moving them to。

 Here's the pointer to the i note for the file。 And where are we moving them to in this new virtual adder space。

 Well， the V adder field tells where we're moving them2。 if anything goes wrong。

 this load segment function will return to -1 and we can exit to the bad label。 But if it succeeds。

 then we are done with this loop and we can go on to the next program header。

And after we've done all the program headers， we're done with the executable file。

 we can then put and unlock it and in the transaction。

 and we then clear out the Iodeode pointer so that in the bad label， we won't redo these two actions。

Okay， now let's take a look at this load segment function。Here is the load segment function。

 Its past page table， which is a pointer to the page table describing the virtual address space that is being created for this executable program。

 and it will load a program segment into that virtual address at location V A。

 and that V A address must be page aligned。 And furthermore。

 the pages in the virtual address space that are going to be written to must already be present in that virtual address space。

If there is any problem， it returns -1 and otherwise it returns 0。

 So in addition to a pointer to the page table describing the new virtual address space。

 it takes the address at which we will be loading the data。

I P points to the in for the executable file。 offsetet is the place in that file where we are going to get the bytes and size is the number of bytes that we're going to be moving into the virtual ladder space。

So this function contains a loop， and each。Iteration of this loop will move one page of data from the file into the virtual address space。

I will be the number of bites we've moved so far。 So we're just going to。

Loop in units of page size here until we've moved as many as size bys。

The first thing we do is we take a look at the virtual address space and we determine where we are going to move the next chunk of data。

 So we call walk address， and we pass it the virtual address plus I。

 that's the number we've already moved up to now。 and that will give us the physical address of the page in kernel memory where that page is mapped to。

 So once we have the physical address， we check to make sure that we really have something we have already called UM Aloc。

 So that page ought to be in the virtual address space。 And if it's not。

 we print an error message here。Then we look at how many bytes we have left to go。

 So I is the number that we've moved so far up till now。

 And if the remaining amount of bytes is less than one page worth of data。

 then we don't want to move a full page worth of data。 Instead。

 we compute the number of bytes to move as size minus I。 Otherwise。

 we're going to move a full page of data。And finally。

 we call read eye and read I is past the iode from the file， from which we are going to read。

 as well as the offset in that file。 So this is our offset parameter plus the number we moved already。

 And in is the number of bytes we're going to be moving on this particular move and P is the physical address。

 this flag indicates that that's a physical address and not a virtual address。

 If there's any problem， we return -1。 Otherwise we loop back and move the next。

Chunk of data from the file into the virtual address space。 And when we're done， we return 0。

So let's return to the exact function。 Here's the loop where we're going through all of the program headers。

 And for each one， we are loading a segment。 And after we're done with this loop。

 we're done with the executable file。 So we call unlock put， and then we in the transaction。

 and then we move down here。Here we are getting a pointer to the proc structure。

 We actually did that earlier in this function。 So this statement is unnecessary。

And then we're capturing the size of the existing virtual address space。

 And we will be using that later on。And then let's see what's going on with this。

 So here is a picture of the virtual address space。 When we created it， it had two frames。

 two pages at the very top of the virtual address space for the trampoline and trap frame。

And then we loaded a bunch of executable segments down here somewhere。 And apparently。

 in this example， we required four pages。 So we have a number of pages and size might not be page aligned at this point。

 So what we're going to do is round it up to the nearest page boundary。

 And then we're going to allocate two pages。 One for the guard page and one for the user stack page。

So that's what's going on next。Here we see that we are rounding size up to the next page boundary。

 And here we're calling U V M Alc。 And the old size is size at this point。

 And then we're adding two additional pages and growing the virtual address space by two pages。

And if there's a problem there， we go to bad， but otherwise we have enlarged the size of the virtual address space。

These pages pages will be marked as readable and accessible in user mode by the U VM AlEC。

 And this new argument to U VM AlEC in this case will mark the pages as ridriable as well。

 So we can go ahead and and mark these pages as。Accessible in user mode， readable and ridable。

 accessible in user mode， readable and ridable。The next thing we do here is call UVM clear and we're passing at the size pointer minus two pages。

 so at this point the size pointer has been incremented by two pages and decrementing two pages we're pointing at the guard page so we call UVM clear。

 which is going to mark this thing Its not accessible in user mode and if the user mode program tries to grow the stack and grows downward and grow it beyond one page。

 it will try to access this guard page and that will abort the user program。Next。

 we need to capture the pointer， the stack pointer。

 the stack is empty and it will be growing downward。

 and we also capture a variable called stack base， which will allow us to detect whether we are going to push。

Stuff on the stack and overflow it within this function。 So here we clear the user mode bit。

 And here we capture the stack pointer and the stack base pointer。

So continuing with the exact function， the next thing we're going to do is deal with the argument strings。

 So remember that the exact function is called with a pointer R V to an array。

 and that array contains pointers to strings。 and each string has been placed in a separate page in the kernel space。

So here's what we'd like to get to。 Okay， here is a picture of the stack。

 and we start with an empty stack， and the stack will grow downward in this direction。

And we want to push each one of the four argument strings onto the stack。

 and we want to push an array with pointers to those strings。

 And then we will pass to the main function of the new program， Both Rrg C， which will be4。

 in this case， as well as R G， which is a pointer to an array of pointers to the strings。

So let's walk through this code。We are going to count the number of arguments with the variable Rrg C starts at 0。

 and we are going to go through the Rrg V array。 And for each one of the strings。

 we're going to push that string onto the stack。So first of all。

 we make sure that we don't have too many arguments。 and if so， we go to this bad label。

Then we look at the string。And we figure out how long it is。

 And then we add one for the terminating null bitete， and。Then we subtract the stack pointer。

 and we also want the stack pointer to remain aligned on 16 B boundaries。

 So this line here will lower the stack pointer if necessary to the next 16 B boundary。

 And then we check to make sure that we haven't overflowed the stack by looking at the stack base value and go to bed if that's the case。

And then we are ready to copy from the string。 Okay。

 here is a pointer to the string in sitting in its page by itself。

 Here's the length of the string plus the null by。 and we're going to copy it to where the stack pointer now is。

And so here。In this diagram， these tick marks here show 16 byte boundaries。

And so we figure out how long the string is， and then we drop that down to the next 16 byte boundary。

 and we copy the string in there， possibly leaving some unused bytes after it。

Now we've got this other variable called USt。 that's a local variable in the exact function。

 and we want to save a pointer to the string that we just pushed onto the stack in that array。

 So that's what's going on here。I'm showing the U stack array here。Normally I in the past。

 I've shown arrays with the first elements at the top and then indexes increasing as we go down the page like this。

 But for this case， I want to show it in the reverse way。

 So this is the first element here to the first string。 I'm doing it this way。

 because I'm showing the stack growing downward with low addresses down here and higher addresses up higher on the page。

And so we add a pointer to this U stack array for the first string and for the other strings as well。

 So we go through this loop， repeating for each one of the arguments。

 saving a pushing it onto the stack。And then saving a pointer to it in this U stack array。

 And finally， when we're all done， we save a null pointer after the last pointer。

 So that's this null pointer here。Now， we need to push that U stack array onto the stack。

 So here we are calculating the size of it。 This is the number of elements。

 plus the terminating null， so。4 plus  one。Times the size of these pointers。

 And so we subtract that from the stack。 And then with this line， just like before。

 we round it down to the next 16 by boundary and check to make sure that we haven't overflowed the stack。

If everything's okay， then we can now copy the entire array。

 so the size of this array is just argy plus one for the null pointer， and we copy that to S。

 and here is where the array is located， so we copy it to the current value of the stack pointer and if there are problems with that。

 we jump too bad。So。That's what's happening here。 We have figured out how big this array is dropped down to the next 16 by boundary and then copied。

The elements up to， and including the first null bite。

The first mill pointer into this area here in the stack。 So again。

 we may have some space after that array。Now， the stack pointer is pointing here。 and we。

 when we call the main program for the new program， we will end up passing it R C。

 That's the count of the arguments in a 0。 as well as a pointer to this array。

 And that will be in register a 1。Okay， so we just copied the uset array into the new virtual address space at location SP。

 if anything goes wrong， then we jump to our bad label。

 but otherwise nothing else can go wrong and we will proceed down to the return here。

 so we are committed at this point to executing the new program。S P。

 at this point will point to the Rrg V array that we've pushed onto the stack in the new virtual address space。

 and that needs to be saved in register A1 so that the new program will get it。

 A 0 and a1 will be the arguments to the function。 The first function that executes in the new program。

 So we need to save S P。 That is the pointer to the Rrg V array on the stack。In the trap frame。

For register A1。We have a field called name in the proc structure。

 And what this does right here is save the program name for debugging。

So the path name might look like this， and we run through the path name with variable S up to the null byte。

 and we increment through it。 And for each character， we ask， is it a slash， And if it is。

 then we're going to save a pointer to the character after the slash。 So， for example。

 when we hit this slash， we set last to point to this。Position here。

And after this last slash is encountered， we have a pointer to the final file name in the entire path name。

If there are no slashes， well， we initialized last to point to the beginning of the path name。

So now we will copy from last through the nullbte into this name field in the pro structure。

 and we use safe string copy to copy up to as many characters as there are in this field。

Now we are ready to switch out the old virtual address space and switch to the new virtual address space and make sure we start executing at the beginning of the new program。

So we have previously saved the size of the old virtual address space。

 and here we're saving a pointer to the old page table for the previous virtual address space。

 and here we are going to call Pro free page table with the pointer to the old page table and its size to free all of the pages that are associated with the previous address space。

And here we are going to switch over to the new virtual address space by replacing the page table with the new page table that we've just created。

 which has size。😊，Indicated right here。We will also update the program counter。

 We saved the executing program counter of the previous program in the trap frame at this location。

 but here we're going to overwride it with the entry address for the new program。Now， previously。

 we had gotten into the kernel with an environmental call instruction。

 so the program counter was pointed to the place where we should return from that。

 but the entry point of the new program is the beginning of some function。 So previously。

 we would be returning a0 as a return value for from the E call function。

 But now we are going to return a0 and a1 as well， and those will be arguments to the code presumably a function that begins executing at this location here。

We also need to update the stack pointer， so here is the stack pointer that we have computed for our new stack in the new virtual address space。

 and we are saving that in the track frame so that when we return to the program。

 it will have a new stack pointer as well as a new program counter。

 then we free the page tables the old page table and return。

 Now remember that this exact function was called from the cis exact function。

 and previously I told you that the exact function here would not return unless there was an error and if there was an error。

 it would free all those pages that we allocate it but I kind of li， it will return。

 even if there's no error so if it does return without an error。

 then it will return a value that is the Arg count。

 the Arg C value and that will then get returned to the program in register a0。

 but whether there's an error or。

![](img/ffde5795273a39d332abc0f1b1621670_2.png)

We will do this loop， which we call Kfr for each one of the pages that we allocated for temporary storage of the argument strings。

And at this point， we return， I'm not sure we should call it return。

 but we go back as if we are returning from an environment call and we resume executing in the users process at location EPC with the new stack pointer and the new page table。

The pro structure also contains some other fields。 for example， it contains the O file。

 which is the array of pointers to the open files， and it contains the field C， W D。

 which is the current working directory。 Those are not changed here。

 So the newly executing program will begin execution with all files that were open in the previous program。

 still being open in the new program and with the same current working directory。Okay。

 that wraps it up for this video， and that also wraps it up for the entire playlist。

 So if you have watched all the videos in this series， then kudos to you by all means。

 leave me a comment on this video。 So I will know that。 And well， thanks for watching。

 And I hope you've learned something about the kernelel。 and。😊，Thank you very much。😊。

