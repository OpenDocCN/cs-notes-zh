# hhp3《xv6 操作系统内核｜The xv6 Kernel 2022》中英字幕 p08 -08-xv6 Kernel-8_ RiscV Page Tables.zh_en -BV11CkSBsEtN_p8-

![](img/f39da02346c55ba4763f6ae664a7a7cd_0.png)

This video is part of a series on the XV6 operating System Colel。In this video。

 I'm going to talk about address translation and describe the。

Page table architecture that's used in the risk 5 processor。

 at least as far as we need to know to understand the X 6 kernelel。

The register that we need to know about here is SATP。

The supervisor register for address translation pointer。It is a control and status register。

 and it will be set to point to the page table。Page tables are kept in main memory。

 and at any one time there is one page table that is in use。

 and that is the one that's pointed to by the SATP register。

Virtual letters translation in the risk 5 core is always turned on。

That is after initialization is complete。So initially， SATP is zero， and when it's zero。

 then there is no translation occurring。But。In the initialization phase。

 we will set SATP to point to the page table that we want to use。

It's always turned on when we're running in supervisor and user mode。

 it's not turned on in machine mode。There are several page tables。

 There is one page table for the kernel。 All cores will share that page table。

And it provides a one to one mapping， pretty much one to one。 There are a couple of exceptions。

But it will map all of physical memory so that the kernel code can access any location in memory without having to do any sort of。

Computation about the address。There are also a number of memory mapped I O devices。

 and the kernelels page table will map those directly。In addition to this one page table。

 there is also a single page table for every user mode process。Now with the risk  five。

 there are a number of options for how page tables are implemented。 These options are called SV32。

 SV 39， SV 48。One of them is a two level implementation scheme。

 Another is the three level architecture， and the SV 48 is the four level architecture。

SV32 is available for 32 bit processors。We are only concerned with the 64 B processor。

 and X V 6 will use the S V 39 scheme。 So the processor processor implements the S V 39 scheme。

 So we have three level page tables。 There's some other options that I won't go into。Every load。

 store or fetch to or from main memory will。Walk the page table table， at least conceptually。

 So we'll go through the page table to find the address translation to use。 That's conceptual。

Walking the page table would involve several memory accesses。

 and that's going to lead to incredible inefficiency。 So for performance reasons。

A real processor is going to have something called translation lecoide buffers。

These are registers that are in the core and generally they are transparent， or I should say。

 invisible to the programmers。And basically， what these registers will do is act as caches for recent page table entries。

The only thing we need to know about。As kernel programmers。

 is that whenever we change the page table， that is， whenever we update the SATP register。

 we need to somehow flush the cache。 We need to empty out all the T L Bs。For this。

 there is an instruction in the risk5 instruction set called S fence VMA。In the kernelel。

 there is a function with the name Sphnce， VMA that does really nothing more than just execute this instruction。

Okay， let's look at virtual addresses for the SV 39 scheme。A virtual address is 39 bits。

And that address can be divided into an offset。All pages will be 4 kilobyte in length。

 and since2 to the 12 is 4K， we need exactly 12 bits to offset into the page。

The remaining 27 Bs are divided into three fields， which will access the level 1 level， sorry。

 level 2， level 1 and level 0 of the page table。 The bits above this， are ignored。

And when we access the page table， we will get a page table entry。

And that page table entry will contain a number of bits that will control whether the access should be allowed or not。

 It can be marked。Read。In which case， reading is O， Wriable。 If we're writing to the page。

 we need to have this bit set and X for executable。

 There's also a U bit to indicate whether the page is accessible in user mode or only in supervisor mode。

And there's a final bit， V， which standss for valid to indicate whether this page table entry is valid or not。

There's some other bits here， but we don't care about those。 And finally。

 there is the physical page number。 And the address translation hardware will take the virtual address。

 use these indexes to look up the right entry and retrieve the page table entry。

 and then it will take the 44 B of the page number and the 12 bit of the offset and put them together。

😊，To form the physical address， which will be 56 Bs。 So with this scheme。

 we can support up to 2 to the 56。Bs of main physical memory。Okay。

 let's look at the page table itself。 Remember we have these three fields and each is nine bits。

So the page table looks like this。 Here's our SATP register。 It points to a tree。

Each node in the tree is a 4 kB page in main memory， and the tree has three levels。

And the leaf level at the leaf， we have the actual data pages。

 So all of these nodes and the leaves are 4 k Bte pages。

And each one of the interior nodes of the tree， that is each one of the three levels in the page table。

Will contain 512 entries。 Each entry is 64 bits。 and， of course，64 bits is 8 Bs and 8 times 512。

 This is 4096。 So we have room for 512 entries in each node。 And each entry is a page table entry。

 which will have some bits and a pointer to the next。Level node。 And so。The way it works is。

The hardware will look at the first nine bit field here and use that as as an index into this root node。

Recall that。Due to the 9 is 512。 So 9 Bs is exactly what we need。Of course，12 bits will allow us any。

ccAccs to any byte in the data page since2 to the 12th is 2096。So we use the first index here。

 the level  two index， the index here。We get a pointer。We use the next index。To index into that。

We use the and that gives us a pointer to the next page， we use that index to access into this page。

 and that gives us the final page table entry， which is shown here and which will be used to check the access of the data page and to build the physical address。

Okay， that's it for the page table scheme， see you in the next video。



![](img/f39da02346c55ba4763f6ae664a7a7cd_2.png)