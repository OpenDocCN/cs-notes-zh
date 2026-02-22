# hhp3《xv6 操作系统内核｜The xv6 Kernel 2022》中英字幕 p20 -20-xv6 Kernel-20_ VM Functions_ Code Walkthru.zh_en -BV11CkSBsEtN_p20-

![](img/5e964734889d7046269d2bd5a76227f8_0.png)

This video is part of a series on the XV6 operating System kernelel。In this video。

 I'm going to talk about the virtual memory helper functions that are found in the file， VM。 C。

In the previous video， I looked at the same file， and I did an overview talking about each function individually and describing what it did。

 In this video， I'm going to look at the functions again a second time。 But this time。

 I'm going to actually do a code walk through and see how they achieve their functionality。

You can watch both videos if you want the greatest understanding of this material。

 or if you've already watched the previous video， then it's quite reasonable to consider skipping this video。

 This video is quite long， over an hour long。 So you may want to just skip this video。

 But for greater understanding， watch them both。 Or if you have not yet watch the overview function。

 Then you might want to just watch this function。 This video alone。

 And that's also reasonable and acceptable。😊，Okay， let's get going。



![](img/5e964734889d7046269d2bd5a76227f8_2.png)

Okay， let's take a look at the walk function。 It's past a pointer to the root of the page table tree。

 a virtual address， and a Boolean called Alc。And it walks the tree and returns the address of the page table entry。

So here is a picture of a page table， and our page table consists of three levels of index pages and the data page we're past a pointer to the root of this tree。

 and we're going to walk this edge here to this index page。

 And then we're going walk this edge to this index page。 And finally。

 we're going return a pointer to the page table entry in the level 0 index page。

 We do not follow this pointer down here and don't do anything with a data page。

If in the course of walking that tree， either the index page at this level or the index page at this level is missing。

 We have the option to allocate them and fill them in。

 So that's what the last parameter alloc is all about。 And if it's true。 and we need to。

 then we will allocate and initialized index pages in the tree。So here is the code for this function。

And we see that we are past a pointer to the root of the page table， the virtual address。

 and this Boolean ac。First， we check to make sure that the virtual address is not exceeding the maximum mallowable number。

 and if so， we print a error message。Okay， so this is organized as a loop here。 for loop。

 And you can see that level starts at2 and it's decremented。 And so it only iterates twice。

 The first time level will be equal to2。 and the second time level will be equal to one。

 and then it exits the loop and does this last thing。

 So what the loop is going do it starts with page table pointing to one of these index nodes。

 and the loop body will go down， grab this pointer and chase it down here and at the end of the loop at the beginning of the iteration the next iteration。

 page table will point to this node。Okay， so in the first iteration。

 it moves page table from here to here and in the second iteration it moves it from from here to here。

 and then finally we go down and we get a pointer to this page table entry。Okay。

 so let's take a look at that in a little bit more detail。We have another variable called PT TE。

 So you can see the first thing we do is we extract the index field。 Now。

 remember that a virtual address looks like this。 Okay， it has three fields。For the level 2。

 level1 and level 0 index， as well as the 12 bit offset。And we。Extract。

 we start by extracting the level 2 index here。 and then we。Index into the page table。

 And we use that to index in here and get this pointer。 And that's what we do here。

 P TE now points to this， this page table entry。 And then here。

 what we do is we look at the page table entry。 We fetch that page table entry and get a pointer to the next one。

 So that's what's going on here。 We fetch。The the page table entry。

 And that gives us a pointer to the next one。 And we set page table to that。 Then we iterate。 Okay。

 let's look at that in a little bit more detail。 So here we see。

A call to this macro function called P X。 And what does P X do。 Well。

 here's another picture of the virtual address with the 9 bit fields。

 And P X is passed this virtual address plus a level number 2，0 or1。

 And it extracts those 9 bits and moves them down here。 So it returns the number between0 and 5，11。

 which we can use to index into the index page。 So P X， first we extract the field for level 2。

 And we use that as an index to index into this page。

 and that gives us a pointer to this page table entry here。And we fetch it。

 and then we use the page table entry。 We fetch the page table entry itself right here and call this function P TE to PA。

 And I have a picture of that。Right。Here。Here's PT TE to physical address。

 And the page table entry consists of 44 bits， which is the pointer plus 10。Bits， the valid bit。

 read， write， execute and accessible in user mode。 So it's got 1010 bits here。

 of which a few of them are unused。 It extracts this 44 bits。

 shift it a little bit and adds in zeros here to give you a physical address。

 So PT T E to physical address。 There's another function。

 which will come to in a second called physical address to PT TE。

 which basically takes the physical address and creates a page table entry。

 But here we are taking the page table entry。 And turning it into an address and setting page table to point to it。

 So in the first iteration， we go down here and we fetch this， this， this P T E。 This is the PT TE。

 and we build the pointer。 And now page table points to the next one。 and then。😊，We check it here。

 before we do that， we check the page table entry and we check the valid debt。Okay。

 so that's what's going on here。 If the valid bit is set。

 then we can go ahead and access it and use it as a pointer。 If it's not set。

 then we've got a problem。 We may have this page table entry may not be valid。

 and we may have to allocate this。Index page right here。

 So when we fetch the page table entry right here， we check it。 And if the valid bit is one。

 then we can go ahead and get the pointer to the next index page。 But if it's not one。

 then we may have to allocate。 So we first check our allocate。Parameter here。 And if it is false。

 then it's this not all will be true。 And we immediately abort by returning a k null。

But if it is true， we keep going and here we see the call to K AllLEC， so we are。

 let's assume that we on the first iteration of the loop had a problem。

 so that means this was not a page table entry， so we're allocating the index。

 the level one index page with this K Allc。and诶。So we do that。

 and we now have a pointer to the next one。 So we set page table to point to the level 1 index page that we just allocated。

 If we had a problem and it returns null， then again。

 we return and abort here by returning 0 immediately。 But if the KL worked。

 then we initialized the new index page to all zeros。The cult a meset here will。

Iitialize the new level  one index page to all zeros。

 So that means all the valid bits for all the page table entries in this would be0。

And then we build the page table entry， we build this page table entry here。And store it。 Okay。

 remember， it was not valid before。 and it contained no pointer。

 But now what we're going going to do is we're going to take the pointer to the new page。

 we just allocated。 That's page table。 And we're going to convert it physical address to page table entry。

 So that's。我。That's this page here showing that we have a physical address and physical address to page tableable entry will convert it to a page tableable entry by shifting it and setting all these bits to zero。

But we don't want them all to be0。 We want the valid bit to be set。

 So here we are oring in the valid bit。 and we store that。 Okay， we store it right here。 Okay。

 and now we have page table pointing to this new index page and we' we've fixed the pointer there。

 So then we iterate。 And we may have to allocate another page。 if we allocated this one。

 then obviously the next one will also need to be allocated。 But in any case。

 we iterate and in the second iteration， we index down here。

 follow the pointer and in the loop with a pointer to the level 0 index page。

 So when we end the loop， we've got a pointer to the。Level 0 index page。

 And now what we do is we extract with our P X function， the level 0 field。

 So here's a level 0 field。 We extract those 9 bits。 And that gives us the index into， okay。

 here's a level 0 page。 We， we use that。Last field to index in there。

 And that gives us a pointer to the page table entry。 And that's what's going on right here。

 and we return the address of that page table entry。We just looked at the function walk。

 which is used to walk the in the page table and allocate index pages as necessary and find a pointer to the page table entry in the level zero index page。

Now we're going to look at the function map pages， which is used to fill in and create this page table entry。

So map pages is past a pointer to the root of the page table， a virtual address。

 the size and physical address， as well as a collection of permissions。And the virtual address。

 along with the size， will determine how many virtual pages are to be added to the virtual address space。

And we assume that PA points to a physical address where there are the same number of blocks of physical memory pre allocatelocated and to be used。

 so what this function will do is it will add page table entries so that each one of these virtual pages。

 points to the corresponding physical page in memory。

 and each page will have its permission set identically， according to this last parameter。

 which can set the pages to readable， writeriable， executable or accessible in user mode。Okay。

 so here is the function for map pages。I want to start out by saying creates Pageal entries for the virtual address is starting at the virtual address that refer to the physical address as starting at PA。

It says V A might not be page aligned。 It turns out the way that map pages is used in X6。

Its such that VA is always exactly page aligned。Size is in bytes。

 and it returns0 on success minus1 if there's a problem。Okay。

 so here we have the arguments pointed to the page table， a virtual address， size and bytes。

 physical address， and the permissions that these pages should have。

We start by making sure that size is not zero， so quick error message there。As I said。

The virtual address will always be page aligned。 So this call to page round down will not actually do anything。

 It will just copy the8 into the local variable A。 And a will then increment through the virtual pages。

 one by one and P A will increment through the physical pages  one by one。

 So here's the loop executes once for each page。 And we see at the bottom of it。

 It's incrementing a by page size and physical address also by page size。Before we start the loop。

 we compute the address of the last page。 So we take the virtual address plus size -1。

 So that's the last byte in the range of virtual memory。 And by rounding it down。

 we determine which page that last byte is on。 So here we check to see whether the page that we just added was the last page。

 And if so we terminate the loop and then return0。So what do we do for each one of these virtual addresses？

We call walk to walk the page table， allocating any index pages as necessary。

 So we see that the ac parameter to walk is set to true。

And if there's a problem and that returns null， then we immediately return -1。 But otherwise。

 we get a pointer to the page table entry。 P T E here is a pointer to the page table entry。

 That page table entry had better not be valid。 So here what we're doing is we're testing the valid bit。

And if that is set to true， then we call panic and there's the problem。But otherwise。

 we call this function PA to PT TE。 and that's a macro preprocessor function。

 And that takes the physical address and it builds the page table entry。

 So here is a picture of the physical address。 and if it's a page line address， which P will be。

 then the offset will be all zeros。AtPA physical address to page table entry will ignore these bits anyway。

 But what it'll do is it'll extract the 44 bits here， Shi them， and it'll set these bits to 0。

 So these are the readr executable valid and the user bit。 And those are all set to 0。 by P to PT TE。

 And then we or in。There we go。 And then we or in the permissions that we are supposed to have。

 That is from the last parameter perm here， as well as setting the valid bit。 and then we store。

This newly built page table entry in the level 0 index page where it's supposed to go。

 And then we just repeat that for each one of the virtual pages and finally exit and return 0。Next。

 we're going to look at the functions that build the kernels page table， and they call map pages。

 but they use this little wrapper function， KVM map。 All it does is called map pages。

 And you can see that the parameters are the same。 the page table， the virtual address。

 the physical address， the size， okay， they're not in the same order and the permissions。

 And if there is a problem with map pages。 This thing immediately invokes panic。Next。

 let's take a look at the function KVM make， which is going to create and initialize the kernelel's page table。

It will call KBM map to do the work。 And that's the little wrapper function that we just looked at that does nothing more than call map pages。

This function will create direct mappings for the physical memory， the I devices。

 and it will also map the trampoline page， and it will create mappings for pages for the stacks for each of the different processes。

 I'll talk more about that in a second。 But basically， if you remember this picture here。

 It's going to create the mappings that are described here。 This is physical main memory here。

 And this is the kernelel's virtual address space。 We see the I devices here。

 we see the kernel's code and data。 And we see the physical Ram here。 And those are direct map。

 And we see some other stuff。 So let's get into the code here。 So here is the code for Kvm make。

 It's going to。😊，rick。😔，Create the page table。 So here it allocates the top most index page。

 the level 2 index page。 and with MImet， it zeros it out， so it has no entries。

 and it it that local variable kernelonel's page table。

 and that will be used in all the calls to KVM map。

 and ultimately going through the final bit of this function。 It will return a pointer to that。

So let's。See here we've created the top level index page and zeroed it out。

 and then we start calling KBM map to add the mappings。 The first one is for the serial device。

 the universal asynchronous Ruce transmit unit， and it direct map。 So the virtual address is here。

 The physical address is there， and it's only one page in size。

 So page size is just the 4K page size， and it will be marked readable and ridriable。

 These are the permissions。And so that creates this mapping。This mapping here。

And then in the next line， we create the mapping for the disk device， again。

 one page readable and writeable， and so that's the disk page here。

 a single page over in physical the physical address space。

 And then next we have the platform level interrupt controller and it's mapped direct。

 it sizes a little bit larger。's in fact， four megabytes， its direct map into its addresses again。

 readable and writeriable Now let's take a look at the kernel the kernel has been loaded into physical memory and the address at which is's loaded is called kernel base and there's another address called Etext。

 which is where the data begins。 and so first of all。

 we create a mapping for the code portion which is readable and executable but not writeriable。

And that goes from kernel base to this address here， Etext， so that's what's going on here。

 the virtual address and the physical address are one and the same it's a direct mapping and the size is Ett minus the kernel base。

 and again it's readable and executable。Then the remainder of physical memory from here on up to the top of physical memory。

 Phiz top will be mapped， readable and writeable， and that will include the kernelel's data as well as the remaining memory can be used for which will be used by the K ALc and K free routines。

So。Here we're mapping that we're giving the virtual address as E textext。

 the physical address is the same， and the size is from the top of memory down to Etext。

And it treatable andriable。Next， we're mapping the trampoline page。 and this is not direct map。

 Instead， the virtual address will be trampoline， which is the address of the highest page in the virtual address space。

 So it's this， this address。Right here。And it will be mapped to the physical address of where the trampoline code is。

 And it's a single page， readable and executable。Okay， next， going to the next page。

 we see the last little bit of this function。 we call proc map stacks。 Now。

 let me go back to this page here， or this diagram shows over here。

That this is the virtual address space of the kernels address space， and we see in the topmost page。

 the trampoline page。And then we have a number of pages， one for each of these 64 processes。

 And these will hold the stacks for each one of the processes。They are each a page in length。

 and they're each separated by a single guard page。We have a preprocessor function called Ktack。

And it's passed the number 0 through 63， and it will return the address。

That is the virtual address of this page。 So， for example， if we call it with two。

 it would return this address。 this virtual address right here。 we call it with one。

 it will return this address here。 So it tells us where these pages go in the virtual address space。

 So now we're ready to。 So we in this function。 We call Proc map stacks。 up until now。

 all this code has been coming from Vm dot C。 But prop， sorry。

 Proc map stacks is in the file Proc dot C。 So here it is。 Okay。

 so it's past a pointer to the kernelel's page table。 I's not going to return anything。

 It's just going to update that page table。So it's going to iterate the number of processes happens to be 64 and we've got this proc array with a pointer。

 which is a number of pro structures。 And we're basically just going to allocate to iterate through that array。

 So that's what's going on with this loop here。 We're it iterating through each of the 64 pro structures。

 And for each one of them， we're going to allocate a page okay， in physical memory。

 that is we're going to allocate a page in the Kalc region somewhere， a physical page for the stack。

But then we're going to map it somewhere up here here we see that same picture with a trammppoline page and the stack pages separated by guard pages。

 Okay， so we're going to grab a physical page okay from the free memory so up here somewhere。

And then we're going to create a mapping from that to there。 Now， these arrows here。

 I don't like these arrows because they're pointing someplace else。

 They actually should be pointing into the free memory region here。Okay。

 so here we are allocating for each， for each process。A page。 And then if there's a problem。

 we panic， but if not， we。This this actually computes the number here It's kind of a funny way C works。

 but we're computing the number 0 to 63 and we're calling K stackack to get the address that is the virtual address where we want to map it。

 and then we call KVM map giving it the virtual address that we just computed。

 as well as the physical address of the page itself。

 it's one page in length and it will be readable and writeriable。Okay， that wraps it up for KBM make。

Next， let's take a look at two short functions， KVM and it and KVM and it heart。

 I just go straight to the code on these。KBM and is called once by core 0 during initialization。

 So it's only called by one core， and it calls KBM make to create the kernel's page table and saves a pointer to it in this global variable kernel page table。

Then when as part of the initialization process， each core will call cavium and it heart。

 and what that will do is it will set the control of status register called SATP。

 So this is writing to that SATP register。 The address of the kernelonel's page table that will effectively turn on paging and install the page table。

 if you will。Make SATP is just a little thing that mangled this pointer a little bit into the format that the Ri five processor requires。

 and we also see fence instruction to make sure that anything that we do that we should do before changes control status Reg is actually done before that and anything that must be done after that is actually done after that。

Next， let's look at this walk address function。It's past a page table。

 and it uses that to map a virtual address into a physical address。

 The virtual address must be valid and it must have user permission set。

This virtual address has to be a page aligned address and it returns the address of the physical page where that's located in memory and if there is any problem it returns zero。

 so now let's look at the code for walk address here and you see we have an error check if the virtual address is too large。

 we just return zero。Then we call the walk function with the virtual address to get a pointer to the page table entry。

 we do not allocate index pages if they don't exist。If it returns something valid， then okay。

 we proceed， but if it returns no， we immediately return zero。

Then we check the valid bit to make sure that it is set。 if it's not set。

 we return 0 and we check the bit to see if it's accessible。 if that page is accessible in user mode。

 and if that is not set。 again， we return 0。 And finally。

 we call this little PT TE to physical address function。

 we retrieve the page table entry here and extract the。

Pointer to the physical page and return the physical address。

The function UVM create is used to create and return an empty virtual address space。

 so it creates a page table with only the root that is the level2 index page。So here's the code。

UVM create returns a pointer to a page table。 It's only used to create virtual address spaces for user processes。

 So that's why it's called UVM create。 And you can see it allocates a page here and that will be the level 2 index page。

 the root page if there's a problem， it returns null。

 otherwise it calls meet to initialize all the page table entries in the root index page to0 and returns a pointer to that page。

The UVM and function is used to create the virtual addresserspace for the first process。

So the first process will contain code that comes from anITcode。 S， it's assembly code。

 but basically it's a very short program that does an exact system call and invokes another program and gets things rolling。

This assembly language program is assembled separately， and we extract all the bytes。

 there are actually 52 bytes。 And in hex， they are specified directly in the kernel code in this array of bytes called an ni code。

 So what this function is going to do is allocate a single page。

And it's going to then copy these bytes into that page。So it takes a parameter， source and size。

 which points to these bytes and the sizes the 52， the number of them。And a page table。

 and it will allocate one page。 map it into virtual address 0 with read， write。

 executable and user mode permissions。 and that then that program has then been loaded into the first page of the virtual address space。

 So here let's take a look at the code for UM ait。We see it's past a pointer to a page table and a pointer to the bytes。

 the 52 bys along along with their size。 And what does it do。

 makes sure that they're going to fit into a single page here and if not， it panics。

 and then it allocates a page of physical memory by calling Kalc。

And it sets all of that page to zeros。And then it maps that page。 So here is the pointer。

 the physical address of the page that we just allocated here。

 and its size is zero is page size here， and we're mapping it into virtual address0 with the call to map pages。

And we're passing it the permissions of write， read， executable and accessible in user mode。

 And finally， we are moving。😊，This number， these 52 bys from wherever they are this array。

 this ni code array。 we're moving them into the page that we just allocated。

 So here we're moving them from source to that page。By the way。

 the virtual ladder space for the initial process is quite different from the virtual ladder spaces for all the other processes。

 We sort of cheat a little bit。 recall that a virtual ladder space normally looks like this with the stack down here and code and the heap and and so on。

 Well， with the initial process。 We just have a single page allocated at location0 in the virtual ladder space。

 So we only have one page。 and we load into that page， the code for the initial process。

 that's those 52 B from theit code do S assembly code。😊，And we also use that same page for the stack。

 Of course， every process will need a stack。 and we will position the stack pointer at the very top of that page。

 So the stack doesn't have any more than one page to grow downward。 Of course。

 it really will't need that。 But in any case， that's how we set up this initial processes virtual address space。

It's got a single page， marked readright， executable and accessible in user mode。

 and the vast majority of that space is just unallocated。 Of course。

 every virtual address space for a user process will need a trampoline on a trap frame page。

Now let's take a look at UVM AlLEC， which is used to grow a virtual address space。

Here's a picture of a virtual addresserospace。 and as the process executes。

 it may want to enlarge its he area。 We have this point called the break point。 More precisely。

 it's the address of the first byte beyond the heap。 So since the virtual aerospace starts at 0。

 The brake is actually nothing more than the size of bytes that we've allocated。

And what this function is going to do is going to allow us to grow the size of the virtual address space。

 So we're going to go from some old size to some larger new size。啲。

Breakpoint need not be page aligned。 And so here I'm showing an old size that happens to fall in the middle of a page。

 and we might want to grow it。 The user might want to grow it to some new location， to some new size。

 It's also not page aligned。So what we're going to have to do is we're going to have to increase this old size to the next page boundary。

 and then we're going to say， is it less than the new size Nope。

 So we're going to have to allocate this page here， this page right here。

And then as it's increment to the next page boundary。 And we're going to say， is that。

 we exceeded new yet。 No， we haven't。 So we're going to have to allocate this page。

 And so we're going allocate two pages here。 The new size will still be set to here。

 but we will go ahead and allocate two pages。 So that's what U VM Al does。

 Festa pointer to a page table， the old size。 that is what it was before and the new size。

 And it returns the new size。The pages are added to the virtual address space。

 it called KL to get new physical pages and it zeros those out。

 And it call called map pages to add them to the。Page table， the new pages will be marked as read。

 write， executable and have user permission set。 And as I said。

 the old and the new need not be page aligned。 If there are any problems。

 it will basically undo everything it did。 So it will call K free to D allocatecate what it what it's allocated and it will also use U VM Daloc。

 which I will talk about。In a second， but it will return 0 if it fails to actually enlarge the address space and instead leaves it just the way it is。

 So let's take a look at the code for UM Alec here。 We're past a pointer to the page table。

 the old size and the new size。 and we're going to return the new size。

First thing we do is we do a check to make sure that we are trying to grow the address space。

 and if we are not trying to grow it， we just return the old size。

Then we round the old size up to the next page boundary。 So that's what I talked about here。

 roundunding it up to the next page boundary。 So page round up。

And then we're going to walk through the pages。 In my example， I did this page and this page。

 so I did two pages。 So a is going to start out at old size。

 and we're going to increase it by page size until it exceeds new size。

And so that's what's going on with the loop here。 So each iteration of the loop will allocate one new page and add it to the virtual address space。

So the first thing we do for each page is we allocate a page of physical memory by calling Kalc。

 And if there are problems， if Kalc has no more memory。

 it will return null and we will and have an error situation。 So I'll describe UVM the ac later。

 but basically it undoes everything。 and this is the new size here。

 So we revert to wherever the old size was。So this is the current size for the callta UVMD aus the current size and this is the new size。

 And so what we've done is we've managed to get as far as a here and we then retract everything or undo everything and return zero。

 But if KLc succeeds then Mm will not be null， and so we've got a page so we zero it out by calling MIMSet you know we don't want any data from some previous page which was in some other processes virtual address space perhaps to we don't want the data on that page to become visible to the new process because that would mean data leakage and it would be a security violation。

 So we zero out that page and then we add an entry to the page table for that virtual address So a is the virtual address here that we're adding so。

Ma is the virtual address first here。 And then on the next it here。

 And we call map pages to add that。 And the physical address is the address of the page we got from K。

 So that's the physical address。 Of course， it's 4K bys。

 And we pass in permissions to make this page readable， writeriable。

 executable and accessible and user mode。 And if everythings okay， then we go on to the next page。

 However， if theres a problem， then we free that page that we allocated here。 Okay。

 with call to K free。 and then we also decate all the other pages。 So again。

 we call U VM Dalc to undo everything we've done so far and return 0。When the loop finishes。

 everything's okay。 We return the new size that we were past。Before we look at the U VM D。 AlEC。

 let's look at U VM Un map。It's passed a pointer to a page table as well as a number of virtual address pages。

 so virtual address here is a page aligned address and we have the number of pages that need to be unmapped。

And for each page， it will locate its page table entry and clear the valid bit。In addition。

 there's another parameter， do free， and if that's true。

 then this function will call K free on each of the data pages and return them to the free data pool。

Okay， here's the code。Remove in pages of mapping starting from the virtual address V A。

 which must be page line， and the mappings must exist。And optionally free the physical memory。

 So here's a point of the page table， the virtual address， the number of pages and the Boolean。

And the first thing we do is make sure that V A is page aligned。 And if it's not， we call panic。

Then what we're going to do is we're going to iterate through all of the virtual pages。

 So we start with the virtual address V A， and we successfully increment it by 4K by the page size until we reach the limit。

 In other words， V A plus the number of pages times the page size。So for each virtual page。

 which has a virtual address， A， what are we going to do？ Well， we start by calling walk。

 and here's the pointer to the page table and the virtual address。 and we。

And walk will return a pointer to the page table entry。 PTE is a pointer to the page table entry。

If there's any problem with that， it'll return null。

 and we panic the pages that we are unmapping had better be mapped。

So the next thing we do is we retrieve the page table entry and we check the valid bit。

 And if it is0， then that page is not mapped。 That's a problem。 It had better be one。Next。

 we look at the page table entry and this function here， PTE flags will isolate the flag bits。

And the flag bits， know， the readable， writeriable， executable user mode， and valid bits。We are。

 we've checked to make sure that the valid bit is one。

 and here we're checking to make sure that something else is one。 besides it better not just be one。

 And this says the message is that it's not a leaf。 And so exactly what's going on there。 Well。

 let's look at this picture of the page table。 And here we have a page table entry pointing to another index page。

 And here we have a page table entry pointing to another index page。

 And here we have a page table entry pointing to a data page。In the case of these page table entries。

 they had better be valid if there is， in fact， a pointer and the other bits， the readable。

 writeriable， executable and user mode bits had better be0。Down here。

 if the page table entry is valid， then it had better point to a data page。

 and that data page needs to be at least readable or writeriable or executable and have the user mode bit possibly set。

 So the other bits besides the valid bit can't all be0。 So that's what we're checking for here。

 we are making sure that there's something， some bit besides just the valid bit that is set。And so。

What we're going to do with this page table entry is just set it to zero which will clear the valid bit among other things and so that's what we do here but before we do that we ask whether we are required to free the data page and if so we use this page tableable entry to physical address to extract the pointer to the actual page and memory here remember this picture this is the page table entry and we're using the PTE to physical address and it's going to ignore the bits and do a little shifting and replace the offset for zero to give us an address that we can use and the call to Kfr so here we are using that physical address that was so obtained and returning that page to the free pool。

Next I want to talk about UVM DalEC previously I talked about UVM Aloc and remember it's past an old size and a new size and it's essentially used when the user process needs to grow the virtual address space so it needs to increase the break point。

And so。UVM Ac adds pages to the virtual ladder of space。 And if anything goes wrong。

 it calls U VM thealc to remove pages。 so it has it can have a problem and returns 0。

UVM D Ac will not fail。 So it's past the old size and the new size。

 And so here's an example there where we are taking the virtual outer space and shrinking it。

 So in this particular example， we are removing two pages。

 Old size and new size need not be page aligned。And we will also call K free to get rid of the data pages。

 So when we call UVM Unmap， we'll pass it the do free parameter being true。

So the way it's going to work is it's going to take the old size and round it up to the next page boundary here and round new size up to the next page boundary here。

 and then it's going to subtract them to determine the number of pages that have to be freed。

So let's take a look at the code for UVM DalLEC。To pass the pointer of the page table。

 the old size and the new size。First， it checks to make sure that we are。Decreasing the。

Size of the space。 So if new size is less than old size。

 then we are shrinking the outer space and we can keep on going。 But otherwise。

 we're not asking to shrink the size。 So we just return the old size。And we don't shrink anything。

Next， I think the best way to understand this is to look at the computation of in pages。

So the number of pages， we round up the old size and we round up the new size。Okay。

 so we round these numbers up here， so we have a pointer here for old size and a pointer here。

 we find the difference。 that's the number of bytes and then divide by the page size to get the number of pages。

Here we are checking to make sure we get something。 If these happen to be equal。

 then we won't do this because that would be a zero here。

 So we make sure that we have a positive number of pages here。And then we call UM Unmap。 again。

 we round up the new size。 So we're going to be freeing these two pages。

 So we round new size up to this point。 and then we have the number of pages is2。

 So we pass it number of pages。 And this is the do free argument to UM unmap to free the data pages。

 And finally， we return the new size。Next， I want to talk about UVM free。

 This is used to basically get rid of a virtual address space。

 so here's a virtual address space it has some size which shows how many pages have been allocated down in this region and of course it has the trampoline and trap frame pages mapped in the upper two pages of the virtual address space。

What it's going to do is call UVM Unmap with the parameter of size。

 and that's going to unmap and free all of the pages that are here。

 So all of the data pages will be returned to the free pool and all of the page table entries that point to those data pages will be cleared out and made invalid。

It will leave the trampoline and trap frame pages in physical memory。

 it will not attempt to return those to the free pool。

 of course we don't want to do that because they are in use and the trap frame page has to continue to exist for this process for each process and the trampoline page is of course shared by every virtual address space that we can't。

Free that page， either。Then it will call this function free walk。

 which will eliminate the entire page table。 So let's take a look at the code for UVM free。

Here we see it， we'll past a pointer to a page table as well as the size。

 and what we're going to do is call UVM Unmap， assuming there are more than zero bytes。

And we'll pass it to the virtual address of zero and take the size and divide it by the page size to get the number of pages。

 this is the do free parameter that we'll call K free for all of the data pages。

And then we call the free walk function。Next， let's talk about the free walk function。

 It will free all the pages in the page table。 or more precisely。

 it will go through the page table tree。 And for each index page。

 it will call K free to return it to the free pool。 It does not free the data pages。

 It assumes that all the data pages have been previously freed and all the entries。

 the page table entries that point to data pages have been removed。

So I wanted to mention for the UVM free。 this frees all the data pages and clears out the page table entries for all the pages below the size。

 It doesn't do anything for the two pages at the very top。

 These pages are not to be freed because they need to be used。And before we call you VM free。

 we will separately call UVM Unmap to remove the entries for the trampoline and the trap frame pages without actually freeing them。

 And so when we get ready to call free walk， we can assume that there are no data pages in the page table。

The way this thing works is recursively， It's passed initially a pointer to the root of the page table。

 and for that for each page it's called on， it goes through and looks at all of the children and calls itself recursively。

 Each recursive call will completely free。 The entire subt。

 And so it frees all of the children and then finally， it frees the top page。Okay。

 so now let's take a look at the code for free walk。It's past a pointer to an index page。

And it goes through that index page and initially it's past the pointer to the root。

 but in the recursive calls down here， it's past pointers to it's past a pointer to the child index page。

So it's got a loop。 It's going to iterate through and look at all 512 entries in the。Index page。

 So here it grabs the。Index the I page table entry and looks at it and calls itself recursively on that child。

And then finally， after it call itself recursively on all of its children， it frees that node itself。

Now， let me mention here that remember that in the index pages， in the upper pages here。

 we have the valid bit being set。 So in level1 and level2， the valid bit is set。

 but none of the other flag bits， the readable writeriable or executable are set， theyre all zero。

 whereas down here， we should， if we have the valid bit set， then we have a pointer to a data page。

 and it must be either readable， writeriable or executable or some combination。

So we're assuming that all the data pages have been freed and all of the page table entries for them have been set to0。

 so they'll have a zero valid bet。Okay， so you that's what's going on here， we。

Grab the next page table entry。 and then we look at it。 Is the valid fit set， Okay。

 if the valid bit is set， then we're assuming that we point down to another index page。

Okay so we check here to make sure that the readable writeriable and executable bits are0。

 so if it is valid and the bits are all zero。 then we've got a valid page table entry pointing down to a lower level so we need to chase that pointer and so here we call the page table entry to physical address which turns the 44 bits that shifts them and gives us a pointer to the child index page and then we call ourselves recursively on that child。

 and then finally we set that page table entry to zero。So。We have here a second check。

 We're asking whether we've got a page table entry that is non zero。 Well。

 we're looking at the valid bit。 if the valid bit is set。But one of these bits is not is one。

 then this won't have been true。 So we're saying that if we have a valid bit。

 but we've got readable writeriable or executable， then something's wrong。

 we should we might have that situation where we've got a valid bit and a pointer to a data page with readable writeriable or executable set。

 But we assume that we've removed all the data pages。 So we better not have that situation。

 So that's what's going on here。 are we've detected a pageable entry that points to a data page here。

The other thing I wanted to ask is I'm not sure it's really necessary that we zero out each page table entry。

 we're going to be calling Kfr on this page anyway。

 so there's not really any need to zero out the entries as we process them。

 but I don't think that hurts anything。Next， let's take a look at the function UVM copy This is used in the Fork system call。

Remember that when we have a fork， we need to take the virtual address space of the process that's doing the fork and make an exact copy of that virtual address space。

 And UVM copy is what we'll use to do that。 So in this diagram， I'm trying to show what's going on。

 Here's the existing virtual address space。 And it's got a bunch of stuff in it up to size。

 as well as a pointer to the trampoline page and to the trap frame page for this process。And。

UVM copy assumes that we've got a second address space that's already created and it assumes that it has the top two pages mapped into the trampoline page。

 which is shared by all virtual address spaces and the trap frame page is allocated and somewhere else。

 And so that is mapped into this virtual address space as well。 And what this function。

 UM copy is going to do is copy all pages up from0 up to size， Okay， into the new address space。

 So here I'm showing the new address space before this function。

 and here I'm showing it after the function。 So what it's going to do is it's going to make copies of all of these data pages。

 So here it's going to make a copy of the page。 And then it's going to add mappings for each one of those pages to the page table。

😊，And also， the permissions that will be in the new page table will be identical to the。

Permissions that were in the old page table。 And if anything goes wrong。

 it's going to sort of free up all the pages it allocates and return an error code。 Okay。

 it'll return -1 if there's a problem。So it's past the old page table， the new page table。

 and the size of the old page， old virtual ladderer space。Here's the code。

 So let's take a look at this。It's a past pointer to the old page table on the new page table as well as the size。

 and it returns zero if everything's okay or minus1 if there is an error。

So it's going to loop here through all of the pages from virtual address0 all the way up to size。

 and it's going to go in increments of pages， so it's going to increment by 4K here until it reaches or exceeds size。

And for each one of the virtual pages in the old space， it's going to obtain the page table entry。

 so it calls walk oh I forgot to bold it anyway， it calls walk on the old address space with the virtual address I and it gets a pointer to that and PTE in this case is a pointer and if there is any problem it just calls panic。

 the page table entry should exist and furthermore， it should be marked valid。

 so here we fetch the page table entry and check the valid bit to make sure that it is not zero and then we proceed to look at the page table entry and extract the address so this is page table entry to physical address so we extract the page number and turn it into the。

A pointer to the page to the physical page， the physical data page。

And we also take the page table entry and extract the permissions， so this extracts the bits。

 the readable writeable executable user mode bits， and puts them in flags。

Now we're ready to copy the data page。 So the first thing we do is call K AEC to get a new data page。

 So for the first time we're looking at this data page down here and we call Kal to allocate a page here and we're going to copy the data Okay so if let me just zoom out here。

 if we have any problem here。We're going to do a go to to this label down here。

You don't see go tos in C programs very often， but you know here you have one。No comment about that。

 But in any case， we call Kalc。 And if everything's okay， then we copy。From the old page， right。

 we got the address of the old data page here or the data page from the old virtual address space。

 and we're going to copy it into the page that we just allocated with this Kalc here。

 and it's a 4K page size。And then we're gonna to add the mapping。

 So we have a pointer to the new page table and the virtual address， the page size is we've got。

 And we've got a pointer to the。The data page that we've just created， as well as the flags。

 So this tells us to add a mapping to the new virtual address space for this page。

And if there's no problem， we keep going。 But if there is a problem。

 we immediately free the page that we allocated with Kalc and we go to air again so。

Then we keep looping like this through all of the pages in the old address space。

 so we loop through all of these pages， copying each one of them and adding an entry to the page table。

And then finally， if we make it through all that without any problems， we return zero。

But if we have a problem， then we need to unmap everything and return -1。

 So this is the new address space and from。Virtual letter of  zero， that is from the beginning。

Through I， okay， I we need the I is incremented by page size here。 So it goes in units of pages。

 And so we divide by page size to determine the number of pages to unmap and we remove them from the virtual we remove them from the page table and。

The do free argument here indicates that we return them to the free pool by calling K free。

 So if anything goes wrong， we basically undo what we've done and return -1。Next。

 let's look at the UVM player function。It's past a virtual address。

 and it will mark the corresponding page in the page table as not accessible in user mode。

It's used in only one spot。 and that's for marking the guard page in a user address space as not accessible。

 So here's a picture of an address space。 We've got the code and data。

 we've got one page for the stack， the user stack。 and then we've got this one page called a guard page here。

 And so UVM clear is used to mark this particular page as not accessible in user mode。

 So if the user program tries to access this page then the X6 kernel will catch that error and throw that process out。

 And that would happen if the stack， which is growing downward from this point。 gets too big and。

Runs into the guard page。And so the code for UVM clear is。Pretty straightforward。

 you might say it's clear Here's a pointer of the page table and the virtual address。

 we walk the page table to find a pointer to the page table entry。 This is a pointer。

And if there's a problem， we immediately panic because we are only calling this on the guard page that should all already be there。

 and then we are updating the page table entry， So what we're doing is we're ending it with a word that has all ones except for where the Ubit is which has a zero there。

 so that's a way to clear this particular bit in the page table entry。Next。

 let's take a look at the copy in function。It's past a page table that describes a virtual address space and a virtual address within that space。

And it's passed as well， a destination location and a link。

 which is the number of bytes that needs to be copied。

So here in this picture is a virtual address space and the source virtual address is at the beginning of the red zone here。

 and the length is the number of bytes， and you can see in this example we are trying to grab a number of bytes and the overlap several pages。

And。When we actually look at where these bytes are in memory。

 there's a virtual there's a page table that maps each of these virtual pages into some physical page。

 So， for example， the first page is actually located right here。

And what we want to do is we want to copy these bytes。

 which are actually located in physical memory at you know here， here， here and here。

 and we want to copy them into some contiguous place in the colonel's address space。

 So that's the destination location。Okay， so we're going to copy bys from the user space to the kernel area and we'll return minus-1 if there's any kind of a problem。

 it may be that the user process gave us an invalid virtual address so。

Let's take a look at the code now， This is I think kind of tricky code to look at。

 so let's see if we can work through this。 here's the page table and here's the destination pointer。

 here's the LiIn bytes and the virtual address， the source virtual address from where it's coming from。

So first of all， we're going to copy in chunks and length is the number of bytes we have left to go。

 So while we have more bytes left to copy， we'll keep doing this loop。

 And so each iteration of the loop is going to copy a piece from one page。 So this piece。

 then this piece， then this piece， and then finally this piece。So we will be decrementing length。

 okay， we will determine how many bytes to copy， and then we will copy that and decrement length and we'll increment the destination pointer by the same amount。

So here you see the actual call to MIM move， which does the movement from destination and it moves in bytes。

 so I think we've taken care of destination and length and if we manage to copy all the pieces and exit this loop。

 we have no more bytes to copy， we decmented length all the way to zero then we return zero。

 if there's any problem we're going to return a minus1。

So the tricky part is the source and we have two variables here， the virtual address 0， B 0 and PA0。

Let's see how this works。 We're going to start by taking the source location。

 Let's go the source VA here。Sour virtual address。 And we're going to round it down to the nearest page boundary。

 So that gives us this virtual address。 And then we're going to call walk address on that to turn it into the physical page。

 So that gives us the pointer to the。Page， where it's kept in physical memory。

 We still don't know this address， but we know this address here。

And we want to copy this bit here first， that's the first thing we copy。

We check here to see whether we had any problem， for example。

 if that virtual address is not mapped or if not accessible in user mode。

 then we would have a problem here and we just return minus-1。So。Sour V minus V0。

 What that's doing is determining the offset。 source V is this。

 this address here and V 0 is this address。 So we're returning we're computing the offset here。

 So that's what's what's happening here and。Page size。Is the amount remaining。

 So that's the amount we have to copy， okay。So we've determined N the amount we have to copy。

 Now we check to make sure we haven't exceeded the length。 Okay。

 so in this case we haven't for the first chunk that we have to copy， but if we do。

 we shorten into the length so we don't want to copy more bytes than we are required to copy。

Now we have to compute where to copy from。 So we take the physical address。

 That is the address of the physical page where the memory is located， and then we add to it。

Source V minus V0。 That's this offset right here。 So we're taking this addressers here and adding this offset。

 and that gives us the location here。 So now we're ready to do the copy and we do the copy。And then。

Here we are incrementing source V。To。The next unit。 So V A 0 is here， and we're adding1 k to it。

 So now we are are appointed here。 Okay， we've copied this much。

 and we' are now pointed to this place， and we're ready to iterate the loop。

And I think that covers it， that is copy N。Next， let's look at copy out。

 we just look at copy in and copy out does the same thing in reverse。

So a copy in takes a string that possibly spread across several pages in the virtual address space and copies it to some contiguous locations in the kernel's address space and copy out does the exact reverse。

 It takes something in a buffer in the kernelel's address space and moves it into the virtual address space。

 spreading it across several pages as necessary。 so you see that it is passed a source location and a length and bytes and it copies that many bytes to the destination virtual address in the virtual address space。

Coies bytes from the kernel area to the user space， returning minus1 if there is any problem。

And we went over the code for copy in， and the code for copy out is really almost identical。

 So here's copy in。I just want to like compare these two line them up。

 You have the exact same number of lines we can see copy in and we've got the while lope and we've got the page rounddown and walk address and check to make sure PA0 is not zero and computation of in and adjustment for length and then the memory move and then updating the variables and then returning zero So in copy in we see destination here it's changed to source and here we see the source virtual address and here it's changed to destination virtual address and go when we go through this we see that that's really all that's happening source virtual address change to destination virtual address and then everythings the same here the computation of。

How big the chunk we want to copy is okay this is the offset and this is subtracting from the page size as a whole and that's just source virtual address has changed the destination virtual address and then in the move here we were copying it from the virtual address space to the destination。

And here we're copying it from the source from the colonel's address space and the destination is then this chunk of the virtual address space and again we see destination change the source here and source。

Virtual address， change the destination virtualr address。 So there's a nice symmetry there。

The last function I want to look at is copy in string。So to motivate it。

 imagine that you've got a system call such as open that provides a file name。

 That file name will be located in the user's virtual address space。

 and presumably it's a string with a variable number of characters terminated with a null character。

 and the kernel needs to get that file name。 and it wants to it'll need to copy that string into some buffer while the kernel will have a fixed size buffer。

 and we don't know exactly how many characters will be in that string before we hit the final null。

 we don't want to allow the kernel to overrun the buffer that would be disastrous。

 And so we need a slight variation on this copy in。

 So we want to have a version of copy in that will copy up until the null character。

 but won't overflow the buffer。 So。Copy in string is past a page table and the pointer to a pointer to the destination area。

 as well as the max length。 So how many bys we have in the buffer to copy to。

And the source from where in the virtual ladder space， the characters will be coming。

 And what it does is it's like copy in。 it copies bys from the user space to the kernel area。

 but it stops copying after the null character and if the null byte is not reached before we copy max length characters。

 It stops。 So it doesn't overrun the buffer。 and it also returns -1 in that case to let us know there was an error。

 So now let's look at the code。 And first， I want to look review。

 copy in because it's really quite similar。 So， we've got you know。

 this stuff here is pretty much the same。 It's the memory move where there's a difference。 Okay。

 so take a look at copy in string。Again， it's pointer page， pointer to the page table。

 the destination area， the source virtual address and the maximum number of characters to copy， so。

We've got a while loop here。 And instead of length， previously， we had length and the while loop。

Copiied until we had length characters copied。Here we have Max， here we have max。

 And so the while loop copies until we exceed max。 And so we will be decrementing。Max。

 as we go And as long as it's greater than0， we've still got more characters to copy。

 But we've also got a flag here called gott null。 Initially。

 we haven't seen the null bite at the end of the string。 So it's initialized to false。

 And the minute we do see the null by。 We'll set that flag to true。

 and that will cause this loop to terminate。And then if everything went well and we saw the null character。

 we returned zero， but if we didn't see it， we return minus1。诶。😊，So。

This part here is pretty similar to。

![](img/5e964734889d7046269d2bd5a76227f8_4.png)

Copy in string。 So let's just take a quick look at that。

 We are try to line these up a little bit better。We are copying。 we are rounding the source location。

 the source virtual address down to the nearest page。

 And we're figuring out what is the physical address of that page and in memory。

 And we're checking for an error here。 And then we're figuring out how many bytes to copy in that first chunk and possibly making sure that we don't overcopy here。

 But then we hit the mem move。 And that's replaced by a loop that copies individual characters。

 So in in copy in。We are copying from this location。Physical address plus the offset here。

 And so that's what we're doing here。 Phys address plus the offset。 And that's where we copy from。

 And so P is going to be our our pointer。 And instead of just copying in bys here into destination。

 what we're going to do is a while loop。 And we're going to copy。

 we're going to try to copy in bys in this while loop。 And we are。

Looking at the the characters are coming from the pointer P。

 So we see if we've got the null character。 And if so， we copy it to the destination。

 and we set our flag and we are done with this loop。But if。We don't have the null。

 Then we just copy the bike and then we decrement our counter in。 okay， and we also decrement max。

 which is the number of characters we have to go incrementing P and incrementing the destination pointer。

 So we're doing these。 by one here， Of course， we do the loop a bunch of times in times here。

 when we adjust the pointers， we do it all at once we did in iterations here。

 we copyied it in bytes So we can just adjust the the length in the destination by in all at once。

 So here we're adjusting the destination one by one and the length decrementing at one by one。

And but then we sort of continue the same way。 So here in copy in。

 we are figuring out the virtual address of the next chunk。 we need to copy。

 And we do that the same way here。 And so I think that finishes it。

 And that is all that we have for the file VM dot C。



![](img/5e964734889d7046269d2bd5a76227f8_6.png)