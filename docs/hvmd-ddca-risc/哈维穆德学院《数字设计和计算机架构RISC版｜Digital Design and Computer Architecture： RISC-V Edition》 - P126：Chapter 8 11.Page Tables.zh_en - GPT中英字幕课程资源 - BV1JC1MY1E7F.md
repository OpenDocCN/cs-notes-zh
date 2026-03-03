# 哈维穆德学院《数字设计和计算机架构RISC版｜Digital Design and Computer Architecture： RISC-V Edition》 - P126：Chapter 8 11.Page Tables.zh_en - GPT中英字幕课程资源 - BV1JC1MY1E7F

![](img/b5a6e674f8cf9566804e7856630d4a2b_0.png)

So in order to perform this translation of virtual addresses to physical addresses。

 we use what's called a page table。😊，And a page table has an entry for each virtual page。

 so the number of entries is the number of virtual page numbers。

Each entry in that page table has a valid bit。And the physical page number where the page is located。

If it's invalid， it means it's not。It's not mapped to physical memory or main memory。

So here's a page table example， here's our page table right here。And so。In this case， we have。

 you know。2。Virtual page number 19 bits here， so our number of entries in our page table is it's not shown up to all of them obviously is two to the 19 entries。

Its that page table。And so we use our virtual page number to index into that into that page table。

 So in this case， were address2，4，7 C， virtual address 2，4，7 C， which is produced by our。

By our processor。We look at the page offset we're not translating so we're just looking at the virtual page number which are those upper 19 bits and this is two so we look at entry2 and entry2 is valid it says yep。

 this is mapped to physical memory or main memory。And we find the physical page number or that translation that we just used in that prior slide。

And so we read that from this memory。We look at the valid bit。 say if it's valid if it's a hit， yet。

 it is actually in。Physical memory。 and we use that。Physical page number。And then， append。Or。

Page offset to give us the physical address。So given this page table。

 what is the physical address of virtual address hex 5 F20？

Try it on your own and then we'll do it together。So。😊，啲。Page offset is again。

 the lower 12 B because our page size is 2 to the 12 B。And so here's our page off that。

 we don't translate that again。All we're translating is。而。Virtual page number。

So we look at this table， we look at entry。five。Because it's virtual page number five。It is valid。

That means that page is mapped to main memory to physical memory。And the translation。

 the physical page number is hex1。And so now that's our physical page number。

And we append that with our page offset。To get。The physical address。So this is our physical address。

Compation of。Virtual address， X 5， F2，0。Here's a second example。

 what's the physical address of virtual address Hec 73 E4。So again， we just look at the upper bits。

These lower 12 bits are the page offset。 so we don't look at those。12l bits。

 because those will stay the same， this is basically which word within that page we're looking for。

We use the virtual page number， the upper 19 bits。So you look at page or entry7 in the page table。

 and we see that it's invalid。So that means that this page is not mapped to physical memory。

So the system would need to then pull that page or choose the page in physical memory。

Where to write where I would like to write this virtual page。So this is a miss in the system。From。

In the main memory system。So the term we use for pulling this page into physical memory is called paging。

Or sometimes called swapping。 when it has to swap out another page。

It's really large and it's usually located in physical memory because it's so large。

 so a load or store required not just one memory access， but two memory accesses。

 one to read the page table to do the translation from virtual to physical memory and one to actually access the data once it gets the physical memory address。

😊，So this cuts memory performance in half。

![](img/b5a6e674f8cf9566804e7856630d4a2b_2.png)

Unlesst we get a little bit clever。