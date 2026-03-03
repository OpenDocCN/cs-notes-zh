# 哈维穆德学院《数字设计和计算机架构RISC版｜Digital Design and Computer Architecture： RISC-V Edition》 - P124：Chapter 8 9.Virtual Memory Introduction.zh_en - GPT中英字幕课程资源 - BV1JC1MY1E7F

![](img/96a39e15c3e88ae8e4d83e97ce0bc9b0_0.png)

Now let's talk about the next level or the lowest level in the memory hierarchy。

 which is virtual memory， which is kept on the hard disk or hard drive。

So virtual memory gives the illusion of a bigger memory and main memory acts as a cache。

For the hard drive。So here's a picture of the memory hierarch again。

 and now we're talking about the hard drive， which is we also refer to as virtual memory。It is slow。

 but very large and inexpensive。

![](img/96a39e15c3e88ae8e4d83e97ce0bc9b0_2.png)

So here's a picture of a hard disk drive， which。Probably none of you use now。

 but hard disk strives used to have these magnetic disks with a read right head that would take milliseconds to move around right kind of in our in mechanical time frames。

And then there's solid state drive shown here， which is mostly what people use today in their systems。



![](img/96a39e15c3e88ae8e4d83e97ce0bc9b0_4.png)

So programs use virtual addresses， there's an entire virtual address space stored on a hard drive。

A subset of that address space of that data is held in DRA or main memory。

The CPUU translates virtual addresses into physical addresses， in other words， DRAM addresses。

Data no in the DM is fetched then from the hard drive。

In addition to allowing us to effectively expand the amount of memory we can access。

Virtual memory also offers memory protection， so each program has its own virtual to physical mapping。

 and two programs can use the same virtual address for different data。

 for different physical addresses。So programs don't need to be aware of others running the virtual memory system takes care of that。

One program or virus can't correct memory being used by another program。

So there are some analogies between caches and virtual memory。

 So cache has a block size right the number of words that we access in a single cache line or cash block。

In virtual memory， we call this a page， it's the amount of memory that's pulled from virtual memory from the hard drive into physical memory or DRAM at a given time。

And so the block offset in a cache， we have what's called a page offset so that tells us which word within that page we're actually accessing。

In cache as we call it a miss in virtual memory， we call it a page fault。

And in cache we have a tag in virtual memoryory， we call that the virtual page number。So again。

 physical memory or main memory acts as a cache for virtual memory。

So page size is the amount of memory transferred from the hard diskk or hard drive to the to memory at once to DRAM。

Address translation determines the physical address from the virtual address。

A processor generates virtual addresses。I'll talk a bit specifically about what those are。

And a page table is a lookup table used to do that translation from virtual to physical addresses。

So here's a picture of what this might look like。 we have virtual addresses on the left and some of them。

 the ones in blue， these pages in blue are。And the are just on the hard drive or the hard desk。

That some of them。Some of those pages。Are in physical memory， I was called main memory。

A physical memory called me memory。And we can access them。

From the processor and particularly to pull into the cache。

So most access is hit in main memory and physical memory， but programs have a capacity。

Or the large par of virtual memory systems， so it seems like a lot of memory and fast。

 but really it's because of using this hierarchy between virtual memory。

Memory that's stored on the hard drive and physical memory memory that's stored on in DRAM in the main memory。



![](img/96a39e15c3e88ae8e4d83e97ce0bc9b0_6.png)