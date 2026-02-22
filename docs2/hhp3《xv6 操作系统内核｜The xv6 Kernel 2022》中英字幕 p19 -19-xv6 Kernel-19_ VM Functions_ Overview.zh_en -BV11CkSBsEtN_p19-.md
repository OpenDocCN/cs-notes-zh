# hhp3《xv6 操作系统内核｜The xv6 Kernel 2022》中英字幕 p19 -19-xv6 Kernel-19_ VM Functions_ Overview.zh_en -BV11CkSBsEtN_p19-

![](img/ed0cd04ab9d644451879f3eefb9dc818_0.png)

This video is part of the series on the X V6 operating system kernelel。 In this video。

 I'm going to go over a number of helper functions for virtual memory management。😊。

These come from the file VM dot C， and they're used to manipulate the page table structures。

They are fairly straightforward and can be understood in isolation。 For example。

 they don't do any locking or sleeping。However， there's quite a bit of material。

 and I'm going to break it into two videos。 in this video I'll do a general overview of the functions。

 and in the next video， I'll do a walkthrough of the actual code。

So let's begin with remembering what page tables look like。A page table is represented as a tree。

 And in the case of X V 6， they are three level trees。

 and we can refer to the root node as the root page。 And all the pages that comprise the page table。

 we can call index pages。 at the bottom level， the index pages point to data pages。

 So let's look in more detail at what these look like。 And here we see a picture of the page table。

 one branch in the tree。 and。Here's the root node， and we have a number of page table entries each pointing to the next level and at the lowest level。

 we have the data pages。So remember that a virtual address looks like this。

 We can use the field in the upper part of the address to index into the pages，1，2， and 3。

 and the all set is used to index into the data page itself。The page table entries。Have this format。

 Naly， they contain a pointer that's page aligned， and this is used to go down one level in the tree。

They also have a number of bits， the read， write， and execute bits。

 as well as a valid bit and a bit to indicate whether the page is accessible in user mode。

These bits are valid in the last page table entry， the one at the lowest level here。

In the upper index pages， at these two levels， only the valid bit matters and the other bits are zero。

Okay， now let's go through the various functions and we'll start with the walk function。

Walk is past a page table or more precisely a pointer to the root node of a page table and a virtual address。

 and it will walk the tree and it will return the address of the page table entry that points to the data page。

In other words， it's going to be past a pointer to the route。

 and it's going to walk down the tree and return a pointer to the page table entry that points to the data page。

If there are missing index pages in the page table， then we have the option to create them。

 this third parameter aLEC， is indicating whether we should create index pages if they are needed。

If there's any problem， for example， we can't allocate a page。

 this function will return the null pointer。The next function to look at is map pages。

 and it's used to add page table entries to a page table。 So it's past a page table and。

A virtual address， and that tells where the pages are going to be added in the virtual address space。

It has also passed a physical address， which points to a number of pages。

 so size gives the number of pages that are being pointed to。

 and this function will add a mapping or multiple mappings in this case。

 three mappings to the page table。so that these virtual pages are mapped to these physical pages。

The mappings will be given the permissions that are given by the last argument。 read， write。

 executable， accessible in user mode。If there's a problem， this function will return minus1。

 otherwise zero。It's oftentimes the case with the X V6 kernel functions that if there's a problem。

 the function will return -1。 and if everything's okay， it will return0。For the kernel。

 there is exactly one page table， and all cores will share that page table。

And when we create that page table， we use this function， K BM map， kernelon virtual memory map。

 And it's basically the same as map pages， except that we do not expect errors when we're creating the kernel's page table。

 So this function just adds a call to panic in case map pages returns a -1 error code。And as I said。

 it's used to build the kernels page table。So the function KV Ma is the one that calls KV mapap to create and initialize the kernel's page table。

It adds all of physical memory to the page table with a direct mapping。

 and it adds all the memory map Io devices to the page table again with a direct mapping。

And it creates a mapping for the trampoline page。 The trammppoling page exists somewhere in the physical memory。

 But in addition， there's a second mapping for that from the highest page in the virtual idero space to that physical page。

And finally， it calls prop map stacks。Here's a picture of the virtual address space for the kernel and at the top。

 we see the trampoline page， and we also see one page for each process。

And these pages are mapped into some virtual sorry， some physical pages that are obtained from K Aec。

Each process will need a page for its stack。To be used when that process is executing in kernel mode。

 And so we allocate 64 pages， and we add those mappings to the page table for the kernel。

Recall that we've got this preprocessor macro function called Ktack。

 which is passed a number between0 and 63 and returns a pointer to returns the address of the corresponding kernel Page table page。

The function K V Annet will call K V make KVM make to create the page table for the kernel。

 and it will assign it to some global variable kernel page table。

This function is called during initialization by Co zero to create the page table for the kernel。

And then subsequently， each and every core will call in it heartt。

 which will use that page table and write the page table address into the SATP register。

 This is the control and status register。And when the SATP register is set to point to a page table。

 that effectively turns on paging for that core。Next， we have the walk address。Function。

 which is used to take a virtual virtual address and convert it into a physical address。

So this will use the page table。Walk it to find which page that virtual address is mapped into。

 and then it will translate the virtual address into a physical address。

The page on which this virtual address occurs must be marked valid。

 and it must have you permission set。 And if there's any problem， it dysfunction will return no or 0。

Since the no pages in virtual， any virtual address space are mapped to the very first page in the physical memory。

 no virtual address can have a physical address of 0。

 So it's safe to use0 as the result of this call。Next， let's look at the U VM create function。

 This is a function that will create an empty virtual ladderer space。 Essentially。

 it's just going to allocate one physical page and clear it out to 0 and return that as the root。😊。

Index page for the page table。U Vendna's user virtual memory。

 And we've also got user virtual memory and it， which is used to create the first user virtual outer space。

 This is a little bit special。😊，It's going to allocate a single page。

 map it into virtual address 0 and mark that page as readable， Wriable。

 executable and accessible in user mode。 And then it's going to fill it with some code。Okay。

 it's going to fill it with the code for this function and it code。

 or should say this process and it code。A ni code is represented in the kernel as an array of a bunch of bytes。

 The 52 bys spelled out in hex。 And what this function is going to do is it's simply going to copy that。

S of bytes， which is pointed to by source with a length of size into that first page。Now。

 what are these bytes， Well， they are instructions and where do they come from Originally they come from a file called inIcode do S。

 which is the very first user mode process that ever executes。And it's written in assembly code。

 but basically what it does is it called the exact system call passing it a file name。

 which is the name of the EnIT process。As well as the zero argument。

That should not ever return this init function。 this init file should exist。

 And so there should be no problem。 But if， for some reason， it does return。

 this code will call the exit system call， which itself should never return。

 but that is followed by a go to to this loop label And that is all assembled and the bytes then are extracted from the executable and placed in this array where they can be copied into this single page virtual address space。

The next function to look at is UM Aloc， which will add pages to an existing virtual address space。

It's past a corner to the existing address space and the size of the old virtual address space。

 as well as the size we'd like to bring it up to。So it calls K to allocate physical pages。

 and it calls map pages to add。Pig table entries to the page table。

The new pages will be marked readable， writeriable， executable and accessible in user mode。

And so here's an attempt to show this with pictures。 here's the old virtual address space。

 and we want to add as many pages as necessary to bring it up to new。



![](img/ed0cd04ab9d644451879f3eefb9dc818_2.png)

The old and the new pointers on the old and the new sizes need not be page aligned。

 and we will add as many pages as necessary to make sure that the virtual ider space is at least as big as the new size。

 and we will return the new size。If there are any problems。

This function will call K free and U VM the ac， which I'll discuss in a second to basically return all the pages to the free pool and restore the page table to what it was before。

 as well as returning a0 to indicate that it has failed。So here is an example use of it。

 Here's a user's virtual address space。 We've got the code and the data， the lowest address。

 We've got the stack page and a guard page to catch stack overflow。 And then0 or more heap pages。

 This is the so called break point。 That's how big the user thinks the address space is。 But。

 of course， we also have the trampoline page and the trap frame page up in high memory。

So when the user program wants to grow the heap， we will ultimately end up calling UM Alc。

 using this point as the old and enlarge the heap to whatever the user needs it to be。We've also got。

UVM Unmap， and this is going to go through each page and set its page table entry to0。

Which includes the valid bit。 And so it will， by definition。

 change this page table entry to an invalid entry。And so we have the pointer to the page table we want to modify and the virtual address。

 as well as the number of pages we'd like to remove from the virtual address space。

 And we also have a fourth argument， do free。 And this Boolean tells whether or not to free the data pages。

 So if it's true， then this function will also call k free to return the data pages that are being unmapped to the free pool。

Next， let's look at the function UVvM Dalc， which is very similar to the previous function。

The previous function I talked about UM Unmap worked in terms of the number of pages。

 whereas this one works in terms of the old size and the new size。

 and it's used to shrink back an address space。 And all it does really is called UM Unmap to remove the pages and to free the data pages。

 So it calls UM Unmap with the do free argument set to true。

The old size and the new size do not need to be page aligned as this particular example shows。

And also， the new size can be greater than the old size， in which case we don't do anything。

It's okay。Next， I want to talk about free walk， which is used to remove a page table to free up all the index pages that are involved in a page table。

It's past a pointer to the root of the page table tree。

 and it will walk the entire tree and free the index pages， but it will not free the data pages。

This is actually a recursive function， and it's past a pointer to any index node。

 And what it does is it calls itself on the children of that node to delete the subtes。

 and then it frees the root page， the top page。Now， in kernel coding。

 we need to be careful with recursive functions。The kernel doesn't have very large stack。

 and typically they are a fixed size and rather small stack。

So we need to make sure that this thing doesn't recurse too deeply。In fact。

 the tree is only three levels deep， so we can be certain that it won't recurse very far。

 and we can be sure that the stack usage is bounded and we won't get into any trouble there。Next。

 let's look at the UVM free function， which will。Basically， free the virtual address space。

 And it's past a pointer to the page table and the current size of the virtual address space。

 So here I'm showing the user's virtual address space。And we see the code and the data。

 We see a stack page and a guard page to catch overflow and finally。

0 or more pages that are allocated to the heap。 And what this thing is going to do is free all the pages below size。

 and it's going to walk the page table and free all the index pages。

A user outerspace also has a trampoline page and a trap page。

The trap tripling page is shared by all virtual outer spaces。 so we don't want to free that。

 And the trap page is also pre allocatelocated。 There's one for each process。

 So that's not freed either。The next function is UVM copy。

Remember that when we have a fork system call， we need to copy the entire virtual address space of the process that invokes the fork。

 and we need to create a second address space for the child process。

 And UVM copy is going to take care of that for us。

 It will copy all pages up to size from the old address space and put them into a new address space。

 So it's past the pointer to the old page table and to the new page table， as well as the size。

So here is a picture of the old address space。 We've got the code， the data， the guard， the stack。

 the heat pages， as well as the trampoline and trap frame。

 And here is the new address space before we call this function。

 and it will already be set up with the topmost page pointing to the trampoline page。

 and it will have its own trap frame page。And what this will do is copy all of the data pages。

 So here I've indicated the data pages being copied and。

It will create mappings for each one of these。 The permissions that were valid here will be applied to the new page table。

 So these will have the same exact permissions。One thing I wanted to mention is that the guard page is actually mapped to a physical page in memory。

 It will be marked as not accessible in user mode。 So over here。

 it will also be marked as not accessible in user mode。But to keep things simple， we copy the page。

 even though this data page will never be accessed。So in order to do this， the function calls walk。

To walk the page table， K Allc to get new pages， new physical memory pages。

 memory move to copy the data and map pages to add mappings to the new page table。

If anything goes wrong， for example， if we run out of memory。

 then it basically undoes everything it calls Kfr and UVM Unmap to remove every entry from the page table and return all the pages。

Next， let's look at UM clear， and this is used only to mark the guard page as not accessible in user mode。

 That's the only place this is used。So it's past the pointer to the page table and the virtual address of the guard page。

 And it will mark that page by clearing the U bit in the page table entry。 And as I said。

 it's used for marking the stack。The Stas guard page in a user address space。From time to time。

 the kernel needs to move bytes into or out of the virtual address space of the user processes。

For example， when the system call open happens， it's past a pointer to the string that is the path name of the file name that we want to be opening。

 and that string is located in the user's virtual address space。The kernel needs to get it。

 The problem is that that string may cross multiple pages。 It may lie on more than one page。

 So in this example， I'm showing the block of bytes that we want to access in red。

 And you can see that this block of bytes spans four pages。Well that。

What it looks like in the virtual address space， it's all contiguous。

 at least the user sees it that way， but the actual physical pages and memory can be spread all over。

 And so this data is not contiguous in physical memory。

 And so the functions that we're going to look at， copy in and copy out basically are used to copy the data into a buffer in the kernel or from the buffer back in such a way that it will be contiguous in the virtual address space。

So let's start with copy in。 It's past a page table and the virtual address from which to get some bytes。

 as well as the number of bytes we want to obtain。And it passed a place like the address of this buffer here。

 where it wants to store the bys。 And what it will do is it will copy bys from the user's virtual address space to this kernel area pointed to by destination。

So it's going copy the individual pieces。 I mean， it would start by copying。Well。

 let's see memory goes up this way。 It starts by copying this piece。 and then。This piece。

 and then this piece。 and finally the the last piece copypy out of the reverse。

 it's used to move data from this buffer back into the virtual address space。

 It's past a page table and the virtual address where the data is supposed to be placed as well as a pointer to the source that is the buffer and the number of bytes。

If anything goes and it copies bytes from the kernel area back to the user's virtual address space。

If anything goes wrong， for example， the virtual address is not valid。

 then this function will return a minus1 if there's an error or zero， if it's all okay。

In the case of the open system call， we are looking for a string that will be null terminated。

 So we only want to copy bytes up to the null byte。

 And so there's a variation on copy N called copy N string。And it's similar。

 It's past a source virtual address and the destination that is the address of a buffer into which it's going to be placed。

 as well as the maximum number of bys to copy。 This is probably going to be the buffer length。

And so it will start copying， and it will go up to max length。

 but it will stop after it copies the null terminating byte at the end of the string。

If it goes all the way to the maximum length without encountering the terminating null byte。

 then it will stop copying and it will turn a minus1 to indicate that there was some sort of an error。

Okay， as I mentioned this， this is an overview of these functions。 And in the next video。

 I'll be walking through the code， and it's safe if you want to just skip that。

 if you feel like you understand these functions well enough， you can skip the next video。

 which walks through the code in detail and proceed with just this overview of what these functions do。

😊，Okay， that's it。 Thank you。 and see you in the next video or the one after that。

