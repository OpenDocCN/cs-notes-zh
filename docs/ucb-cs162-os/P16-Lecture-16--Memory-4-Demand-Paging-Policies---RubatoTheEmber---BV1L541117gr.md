# P16：Lecture 16： Memory 4 Demand Paging Policies - RubatoTheEmber - BV1L541117gr

 Okay， let's get started。

![](img/b17bfb079039a891e4b53e4d5e7fbc52_1.png)

 So this is our fourth lecture on memory and we're going to look at demand paging and paging。

 policies。 Okay， so remember from 61C that we can compute the average memory access time。

 So if we look at what the time is going to be to access， say we have a processor with。

 an L1 cache and DRAM， we want to figure out what's the average that it's going to take。

 us to access any given memory location。 Probably， probably。

 holistically that will be the hit rate for finding it in that L1。

 cache times the hit time plus the miss rate times the miss time。

 Now since the hit rate is 1 minus the miss rate， we can just simply reduce that down to。

 the average memory access time being our hit time in the L1 plus the miss rate for our。

 L1 times the miss penalty for the L1。 Now if you think about it。

 we're not just looking at the time to go from one cache to， memory。

 but there could potentially be multiple caches in our hierarchy。 So for example。

 if we don't find it in memory but it's out on disk or we don't find it in。

 our L1 but it's in our L2 cache， then that miss penalty for the L1 becomes our average。

 memory access time for the L2。 So that looks just like this。

 So it just becomes our miss penalty for the L2， our average memory access time rather for， the L2。

 So we can just take each one of our layers of the hierarchy and just compute the average。

 memory access time as the time if we hit at that layer or the average memory access time。

 if we have to go to the layer below， which could include the layer below that， which could。

 include the layer below that and so on and so on。

![](img/b17bfb079039a891e4b53e4d5e7fbc52_3.png)

 So ultimately， this is all about trying to make everything look like we're accessing it， on chip。

 on die at those speeds， even though that's incredibly expensive memory and we。

 have an incredibly limited amount of that memory， we want to make it look as if we have。

 as much memory as we have at our slowest technology and our least expensive per byte。

 But notice again here the difference in access time， right？

 We can access stuff in the chip in the speed of sub nanosecond to nanoseconds。

 Going to main memory is it jumped to 100 nanoseconds going all the way out to hard drives is 10。

 million nanoseconds。 So that's the challenge for us today is we want to look at access times。

 make it look， like main memory access times， 100 nanosecond。

 but we're going to implement it using storage， that has speeds that are 10 million nanoseconds in latency。



![](img/b17bfb079039a891e4b53e4d5e7fbc52_5.png)

 Okay， so remember in the ideal case， we have an instruction fetch or an instruction that。

 loads or stores from memory that generates a virtual address， provide that to the MMU。

 it either finds it in the TLB or if it's not in the TLB， it'll walk through the memory structures。

 the page table entries and it'll find the page table entry for the physical page that， we need。

 return that， combine that with the offset and we get the data we're looking for。

 That's the ideal case， but today we're going to talk about the other case which is we go。

 to make the reference， we look in the page table and we find the entries invalid。

 That causes a page fault that causes a exception or trap into the operating system， terminates。

 the running instruction and runs the page fault handler。

 Page fault handler looks at the operating system books maybe at the page table entries。

 and figures out that that page is actually out on disk， it schedules that page to be loaded。

 into memory， once it's loaded into memory it updates the page table entry， invalidates， the TLB。

 puts the thread back on the ready queue and eventually gets scheduled， we retry。

 the instruction and it'll run to completion。 Okay。

 so we can think of demand paging as treating main memory as a cache for our slower。

 SSDs or hard drives。 So if we say it's a cache then we have to ask all of the questions that we'd ask of any。

 cache which is what's the block size， so what's the unit of transfer from the cache to the。

 backing thing behind the cache and vice versa。 In this case it's going to be a page。

 so you know four kilobytes。 We can also ask what's the organization？

 Last time we looked at direct maps that associate fully associate。

 Well in this case it would make most sense to have this be fully associate， right， because。

 every page in main memory is equivalent。 You can put any page in any place。

 The virtual to physical page mapping allows any placement。 So it's fully associate。

 Now how do we locate a page？ Well first we look in the TLB。

 if we miss in the TLB the memory management unit traverses。

 the page tables and segment map and whatever to find that mapping from virtual page number。

 to physical page frame。 Now what's our page replacement policy？

 So when we have to evict the page from memory which page do we pick to evict？

 Well there's lots of policies we could implement。 We could implement LRU。

 We could implement random or something else， right。 It's going to require a lot more explanation。

 We're going to actually spend a lot of time thinking about the policy。 Why？ Because if we miss。

 if we replace the wrong page and then we access that virtual page right。

 after that then you know 10 million nanoseconds to go and do that access instead of 100 nanoseconds。

 Yeah， question。 Yeah so why do we want a fully associate organization？

 So in this case right every physical page is identical。 So we can place a。

 because of the page table allows us to map any virtual page number to。

 any physical page number we can place a page anywhere in physical memory。

 Right now we'll see later on that we'll sometimes treat physical memory differently。

 Different chunks in different regions differently。 But in general it's fully associate。 We have no。

 there's no limitation in the hardware that says you can't put this virtual page at。

 a given physical page as long as it's not used for IO or other purposes。

 We'll impose some policies on how we use physical memory but there's no strictly you know limitations。

 in the hardware saying you can't map some virtual address to some physical address。

 So that gives us perfect flexibility because again we're going to get into a moment in。

 a moment we'll talk about like misses and if we limited where we could put a page then。

 potentially we could have conflict misses。 Right？ Okay now。 What happens on a miss right？

 We're going to go to the lower level whatever is backing memory to fill that page and retrieve。

 that page。 So a disk in this case。 Now what happens on a right？

 Do we want it to be right through or would we want it to be right back？

 So if we think about it right if we made it right through then like if we're writing lots。

 of stuff on the stack or we're you know writing characters in a string we're going to be doing。

 lots of rights directly to the disk。 That's going to be really slow so of course we're going to want to do right back。

 But if we do right back now we need to keep track of the fact that a page in memory could。

 have dirty data that is it's different what's in memory from what's on the backing store。

 for that page。 So we can't just simply reallocate that page to someone else when we do an eviction。

 Okay。 So all of this is because we want to provide this illusion of infinite memory。

 So we say to a process you have a 32 bit virtual address space for gigabytes worth of virtual。

 memory and then we use the hardware the TLB and the page table to map that to what might。

 be a much smaller physical memory。 So we say you have four gigabytes but we might actually only have 512 megabytes on our machine。

 And so we use the disk which let's say is 500 gigabytes as backing store。

 So some of that virtual address space lives in memory and some of that virtual address。

 space lives out on disk。 Right。 The disk is much much larger than physical memory。

 So we can use it as backing store for our virtual for our virtual addresses。

 The other reason why we want to think about this is because we don't just have one program。

 running we have many programs running。 Each of which we're saying here's four gigabytes of virtual address space。

 So the fraction of each program that's in memory could be much much smaller than its。

 virtual address space and the rest of it will live out here on disk。

 Now we want multiple programs running for concurrency。

 It's one program waiting for its pages to come in for memory or it's waiting on IO or。

 it's waiting on the user。 We want to run other stuff on our processor and we can do that。

 So the principle here is one of transparent level of indirection。 Right from the point of view。

 semantically of the program。 It's virtual address space。

 It can touch or access any of the bytes in it。 Right。 That are defined that are that are mapped。

 But it doesn't know physically where that data lives。

 That data could physically live in physical memory or it could live out on the disk or。

 it could live on another machine。 Rather than paging to a local disk。

 we could actually page across the network to a disk， or a server on the other side of the planet。

 That's from a semantic and a correctness standpoint。 Now from performance standpoint。

 you could actually time memory references and see when， you're page faulting。

 when something's not in memory and then you'd see a difference。 But from a correctness standpoint。

 from a semantic standpoint， it doesn't know the difference。

 between a page that's in memory and a page that's not in memory。



![](img/b17bfb079039a891e4b53e4d5e7fbc52_7.png)

 So that's valuable。 Okay。 We've seen this picture a bunch of times an Intel page table entry。

 The things we want to take away for today are three sets of bits。

 The present bit which is like the valid bit tells us this entry refers to a page in physical。

 memory。 The access bit which tells us whether we've recently accessed that page， I'll give a formal。

 definition of that in just a moment。 And then the dirty bit which tells us whether the page reflects what's out on disk。

 So is it clean or is it dirty？ Have we written to it and so changed its contents relative to what might be stored out on disk？

 Okay。 So some of the mechanisms。 So the page table entry is what lets us do demand page because it gives us this transparent。

 layer of indirection。 We look at the bits in the page table entry and they tell us where to find the page。

 So if it's valid， it tells us the pages in memory and the page table entry has the physical。

 page frame number for that virtual page number。 If it's not valid。

 it means the page is not in memory。 Okay。 So if it uses the page table entry or other operating system。

 bookkeeping structures to， find that page。 Now if you reference an invalid page table entry。

 then that's going to cause the memory， management unit to trap to the operating system。

 It's called the page fault。 And what will the operating system do？

 Well assuming the page is valid and it's sitting out on disk， it's going to want to pull it。

 into memory。 But we might have to find an old page to replace。 Right？

 Because if our memory is all in use， physical memory is all in use， we want to bring a new， page in。

 somebody has to get evicted。 And we're going to pick an old page。 Right？

 Because if we haven't referenced that page in a long time or use that page in a long time。

 then you know， we're not likely to use it again。 Well。

 we're going to go through a long detail what we mean by old and all of that。

 But for now we're just going to pick some page to replace。 All right。 If that old page is dirty。

 we're doing right back。 So we have to write it back to the disk so that now the disk is consistent with that page。

 We're then going to change the page table entry and any cached heal bees for that page。

 to be invalid。 Because it's not in memory anymore。 It's out on the disk。

 Then we get to load the new page into memory from the disk。

 We need to update its page table entry and validate any TLB entries， which previously。

 said it was invalid。 We're going to flush those TLB entries。

 And now we can put the thread back on the running queue and then the ready queue rather。

 And then eventually it will run。 Right？ So we'll continue that thread from the faulting instruction。

 It'll restart the instruction。 And the instruction now will succeed。 All of those steps。

 that's a cache。 Yeah。 For the new or the old？ For the new entry。

 the reason why we have the question is why do we invalidate the TLB， entry for the new entry？

 Because that TLB entry， when we ran through the memory management unit， it said， oh， this。

 page is invalid。 Here's the TLB entry I found。 We put that in the TLB。

 So now we have to invalidate that because we'll reload the TLB with the correct valid a page。

 table entry when we restart the instruction。 That's an important little subtle step。

 So that was a really good question because it's easy to miss that。

 Everything is getting cached out of the memory management unit even when we find that a particular。

 entry is invalid。 Yeah。 Question？ Same question。 Okay。 All right。 So now， as I just said。

 the TLB for that new page， it's going to get loaded as soon as。

 that faulting instruction restarts because it's going to not exist。

 The memory management unit will walk the tables， find the page table entry， and we'll put that。

 into the TLB。 Yes。 So that's another good question。

 We're about to dive into that in just the D and just in gory detail in just a moment。

 But the question is， how does the operating system figure out where this page is out on， disk？

 All right。 So， all that thought， we'll come back to that in just a moment。

 But that's going to be one of the challenges is we're going to need some bookkeeping information。

 and to store it somewhere like maybe in the page table entry of where to find that particular， page。

 Yeah。 Question？ Yeah。 So the question is， how do we invalidate any cache TLB？

 So we just go through the TLB and tell the TLB， you know， this mapping for this virtual page。

 number and this application specific ID is invalid。 And then they TLB will flush it。

 So we're just flushing that specific entry if it's cached in the TLB。 Okay。 Now， this takes time。

 This could take a lot of time。 Again， tens of millions of nanoseconds。

 So while that process is occurring， the process is sitting out， the thread is sitting on a。

 weight queue for that page and the operating system just schedules other threads to run。

 So this is again a reason why I want to have a lot of threads available is because there。

 might be multiple threads that are waiting for pages to come in from the disk。 Okay。

 So lots of things that we can do once we have page faults and demand paging。

 And this is a lot of this is operating specific。 Some operating systems will implement things different ways or support functions or not。

 But sort of the broadest set is we can use it for things like extending the stack， run。

 off the end of the stack， and automatically operating system just extends your virtual。

 address space with an additional page for the stack。 Same thing with the heap。

 run off of the end of that。 It just gives you another page。 We went over last time。

 copy on write when we do forking。 We just simply copy the address spaces。

 the page tables for the parent and child so they're， identical。

 And then we mark everything read only。 When we page fault on the right we check the books to see actually this is a writeable page。

 And so then we copy the page and update the page table entries in both the parent and the， child。

 Exexx， exec。 So when we call the Syscall for executing a new executable， exec。

 we create a new virtual， address space。 We don't actually have to load everything in on demand。

 We can just simply load in the parts of the binary that are actually being referenced， on demand。

 So this is really nice。 If I've got PowerPoint and I don't know。

 it's like a 2 gigabyte program nowadays， I don't， tie up 2 gigabytes of my physical RAM just for the code。

 The only code that's actually going to get loaded in is that code that I'm actually using。

 as I use it。 So this means it starts right away and it's memory， physical memory footprint is going。

 to be much smaller than its total virtual address space footprint。 Another example would be。

 we'll see this later on in the semester， I want to memory map。

 a file into memory and now I can just do reads and writes and I can access that file。

 So that's a technique we use for， for example， the code segment of a program。

 We just memory map it into memory and then run off of that。 Okay。

 So loading and executable into memory。 So this is a classic thing that we're going to do。

 We have some XC or executable out on disk in the file system and it contains our code。

 and our static initialized data and then relocation tables， a bunch of symbols for debugging and。

 other sorts of stuff。 So the operating system is going to load this into memory。

 initialize the registers， initialize the stack pointer and then it's going to call the C runtime in it。

 CRT0， the， start procedure or function。 So if we think about it， right。

 any pages that we're utilizing in our virtual address。

 space are going to be backed by pages on disk， blocks on disk。 Right？

 So you can think of on the disk， we've got our， there we go， we've got our stack， our， heap。

 our data， our code pages。 So all of the virtual address space that's in use for every page in use in memory。

 we， have a blocker page on disk that's backing it。 Right？ Now。

 we can swap these pages back and forth on demand as needed。 We do this for every single process。

 So here we have our page table and it's mapping our kernel， our stack， our heap， our data。

 to various physical pages。 Right？ Now for all of， so for all the other pages。

 the ones that aren't mapped， we have to keep， track in the operating system of where those pages are。

 They're going to be out on disk。 Right？ So here they are。

 here are the pointers out to all of the pages that are not in memory。 Right？

 So there was the question， how do we do that mapping from a given block or a given page。

 a virtual page number to a location on the disk？ Well。

 typically we have some kind of backing store out on the disk。 Right？ And in older operating systems。

 we had a special partition， which was our paging partition。

 And it was managed by the operating system。 And so it was one contiguous region。

 And so it went from like zero to n。 And so there would be a function that would given a process ID and a page number would。

 return you the block within that partition。 Now， modern operating systems。

 it's just simply a paging file。 It reuses the existing file system mechanisms。

 And there are many reasons why we can do that。 That way it can grow to scale with the size of processes。

 It doesn't have to be predefined when you create the disk partitions。 And so instead。

 it'll be some kind of logical index into that file that'll tell you where， define a given block。

 Now， depending on your page table entries， their sizes and structures， some operating。

 systems just simply store that logical offset in the page table entries。

 You just look in the page table entry and it gives you that actual pointer to this location。

 In others， there'll be some bookkeeping data structure， which when you call this find block。

 function， we'll return back the associated disk block。 Right？ Okay。 Let's see， what else？

 Something like the code segment。 Code segment， as I mentioned。

 we can just memory map that directly into the virtual address， space。 Right？

 So what that would look like is here， when we need to， instead of mapping stuff for the。

 code to some location on the disk， like here in our swap file， instead， we could just map。

 it back to our executable。 This is， again， what most modern operating systems do。

 And when you're doing the project or you're doing the homework， you've probably run into， this。

 You're debugging your homework and you're running your program and you realize， "Ah， I have a bug。"。

 So you go into your IDE， make a change to the source and you compile it and the compilation。

 fails because it says the executable is not writeable。 The executable is locked。

 And when you launch a program， the executable is locked because we're using it as backing。

 store for virtual memory。 Right？ And so it's actually got reference counting on it because you could have multiple people。

 who are running off of the same executable and you can't change that executable until。

 all of those running copies stop running and you release all those locks。 And so that， yeah。

 that's the second part。 You could share it with multiple instances that are running。 Right？ Okay。

 So， again， we have our page table， which is mapping in both directions。

 It's mapping to pages that are stored in memory。 It's also mapping to pages that are stored out on disk。

 But we can have multiple programs running the same executable。

 So here we've got a second one that's running the same executable。 And so if we look。

 it'll have separate stack heap and data， but it'll actually have the。

 same code that it's paging off of。 And again， this could be the actual executable that we're paging off of to save disk space。

 Right？ So when， and of course it's got pages that are in memory also。

 So now when we go to make a memory reference， right， we may find that that memory reference。

 is not present。 So we're going to page fault。 And when we page fault。

 we'll switch from what's the active process and each page table。

 to the other process while we schedule the read of that page to occur。 All right。

 So we're getting concurrency running now。 Eventually that page gets pulled into memory。

 Page table entries get updated。 And now we can switch back to that being the active process。

 Eventually it'll get scheduled and it will run。 All right。 Questions？ Yes。 Yeah。 So the question is。

 does each page and memory have a copy on disk？ The answer again is sort of。

 So for kernel stack heap and data， yes。 For things like code。

 it's going to be a many processes sharing the same physical page on， disk。

 And same physical page in memory also。 Yeah。 [INAUDIBLE]， Yeah。 [INAUDIBLE]， Yeah。 [INAUDIBLE]。

 Yeah。 So there are some-- the question is inclusive versus exclusive for caches。

 And do we have memory regions？ Absolutely。 There are some-- the question is inclusive versus exclusive for caches。

 And do we have memory regions that you don't cache？ Absolutely。

 There are memory regions that we don't cache。 Like for example。

 if you have a GPU and it's memory mapped into the virtual address space。

 that would be uncasurable memory。 Because all the writes are going directly to say the frame buffer。

 Similarly， you can have that with network adapters or disk adapters。 Yeah。

 If you can kind of think of it， that's the cool thing。 Again， with the page table entries。

 If you go back and look at the page table entry， in fact， you'll see that there's a mark for。

 whether something's cacheable or not cacheable。 Oh。 OK。

 So there was a question I missed about S break。 Yeah。 So if you look at break and S break。

 you'll see it changes the size of the data segment。 And for m-map。

 you'll see how you can use m-map to map a file into a address space。

 And then you can map that file into multiple address spaces and actually do sharing through， it。 OK。

 So kind of summarizing everything that we put together in terms of how we handle main。

 memory access， we have an instruction here like load some location in memory。

 When we go to walk through the page tables， we find that the page table entry is marked， as invalid。

 That causes us to trap into the operating system， run our page fault handler。

 It locates the page on backing store， schedules the page to be loaded into memory in a free， frame。

 Creating a free frame might require evicting someone else。 If that page is dirty。

 then we have to write that page back to the backing store。 Eventually it gets loaded。

 We update the page table and validate the TLB and then we restart the instruction when。

 that thread gets scheduled again。 All right。 That's page fault all on one slide。 All right。

 Lots of questions。 So the question is， so the code section isn't actually loaded into memory。 Yes。

 code segment is loaded into memory。 It's just backed by the executable on disk and we load from that executable on demand。

 rather than loading all of the code into memory when you start running a program。

 Although we'll see， there's a little caveats and there are optimizations that we can do。

 that we'll talk about at the very end of the lecture。 Okay。

 So a bunch of questions that we have to answer。 Like I just said， we need a free frame。

 When a page fault occurs， if memory is all full。 So where do we get the free frame from？ Well。

 operating systems typically will have a free list。

 So they'll have some process like a reaper process or other process that looks for frames。

 to evict evicts those frames。 If they're dirty， then it schedules them to be written out。

 It zeros them and then puts them on the free list。 That way the operating system when it goes to。

 you know， pull a frame in always has some， free location that I can put it。 And again。

 we'll talk about some ways that we can manage that free list at the very end， of the lecture。

 Now how do we organize the choice of what frame we're going to evict？ Well。

 that really gets to our replacement policy。 Another question we can ask is around how many page frames do we give each process？

 Is it a one over N？ Is it proportional to the virtual address space size？ Is it priority based？

 You know， we can also ask questions about utilization and fairness。

 And we can even extend that all the way down to thinking about things like the disk bandwidth。

 Right？ How much disk bandwidth does a given process get to use？

 So these are all questions that operating systems will look at in terms of how they allocate。

 physical memory to individual processes。 The question is。

 so we would never perform a read and a write to the disk at the same， time。

 So you're either reading or you're writing the disk。

 The disk executes commands on behalf of the processor。

 So the processor can give a queue of commands that are reads and writes to the disk。

 And the disk will do those reads and writes in the order it's given them。

 Or as we'll see later on in the semester， there's all sorts of optimizations we can do。

 in scheduling the disk。 Every resource in a computer can be scheduled and managed。

 And we're going to want to do that for efficiency and performance。 Okay。

 So if we think about what a program is doing when it's using its virtual address space。

 So it creates， we create a process。 It's got a virtual address space。

 Is it using all of that virtual address space at the same time？ Well。

 if we look over a window of time， what we're going to find is the following。 Right？

 So here we have time on the x-axis and we have our addresses on the y-axis。

 And what we'll see is that the program moves through a set of working sets。

 So at any given delta of time， we're going to see a set of accesses coming from that， process。

 Instruction fetches， loads and stores。 You can see it's not accessing all of its address space at any given time。

 So what that tells us when we're thinking about it is that working set represents the。

 pages of the application in its virtual address space that we want to make sure are。

 physically resident in the processor， in the physical memory。

 The other way to think about it is if these pages， for example， at this given time， if。

 these two sets of pages are not in physical memory， we're going to take page faults to。

 bring them into physical memory。 That's one thing to consider。

 Another thing to consider is that the working set changes over time。 It's not a static thing。 Right？

 In different phases of time， we've got different regions that are active。 Question is。

 what's the difference between a frame and a page？ They're the same thing。

 We'll use frame and page interchangeably。 Usually。

 we reference like a virtual page and a physical page frame of memory， but page。

 and frame are the same concept。 Okay。 Now， if we look at the size of our cache， in this case。

 the size of our physical memory， we look at our hit rate。 As we increase our cache size。

 the cache behavior we'd like is to see that more memory。

 means more of our working set fits into memory。 Right？ And so the key thing is also， remember。

 we're transitioning from one working set to another。

 So the working set sizes are also going to be changing in size。

 Now what happens again if our working set doesn't fit in memory？ If it doesn't fit in memory。

 we end up page faulting。 And it's the difference between having memory access times of 100 nanoseconds and memory access。

 times that are tens of millions of nanoseconds。 So when we think about physical memory being allocated to our processes。

 we want to think， about that in the context of what's the working set size of our processes。

 Now why might things not fit or why might we have misses that occur？ Well。

 some of them are going to be capacity related。 So if we don't allocate enough physical memory for the working set size。

 we're going to， encounter capacity misses。 But there's also going to be conflict misses and compulsory misses。

 Conflict because we replace the wrong pages and that also kind of gets into replacement， policies。

 Conflict misses should really be zero if we're fully associative and there's no biases in。

 replacing pages。 And then compulsory misses are when we first start running or when we just swap something。

 back in。 So this is applicable thinking about this kind of model to memory caches and pages。

 But it's really applicable to any kind of caching strategy。

 We have a limited size cache and we have to look at the access patterns of that cache。

 relative to the size of that cache。 And we'll come back to that in our next slide。 Okay。

 so another model to think about for locality is a Ziffian distribution。

 So in a Ziffian distribution， the likelihood of accessing some item of rank R， so here's。

 our ranks here， is going to be one over R to the A or alpha。

 And so the thing is it might be very rare to access something of low rank。

 There's so many things of low rank that this really makes it a heavy tail distribution。

 So one of the places where people see Ziffian distributions is in web accesses。

 So if we were to go to the Berkeley border route and look at what's the top website that。

 people are going to？ It's probably， I don't know， Cal Central。 If we look at the next one。

 maybe it's www。berkeley。edu。 And so there's going to be tons of accesses every day， every hour。

 every minute to those。 So caching those websites would give us huge value。

 Then maybe we get down to number 20 and it's， I don't know， www。sfgate。com。 But it keeps going。

 You might be the only person on campus that accesses www。xyz。com。 And so if we think about it。

 there's a large value to， substantial value to caching the， top view。 All right。

 because we're going to absorb a tremendous number of references to that top， view。

 But at the same time， there are going to be hundreds of thousands or millions of references。

 to this tail。 So even if we put an enormous cache on the border， we're still going to have a high。

 miss rate。 And that was one of the challenges people ran into when they started trying to develop。

 web caches is that， yeah， there are those popular sites and we can absorb all the traffic。

 to those popular sites in our caches。 But because people have diverse things that they want to look at on the web。

 that long， tail is going to mean we're not going to have as high a hit rate as we'd like to have。

 Yeah。 Yeah。 So the thing， the question is why the lower rank has lower hit rate。 So think about it。

 right？ If you're the only person on campus who's accessing www。xyz。com out of our campus population。

 daytime， population of like 50，000， that's going to be a small number of references。

 Yet if every student is going on Cal Central to check their classes， that's going to represent。

 a large overall number of references。 And so the value of caching those will be high。 Oh。

 the question is low rank， less popular or more popular？ It's less popular。 Right。

 So when we get all the way out to rank 49， there's not a lot of people that are accessing， 49。

 but they are accessing it。 So we can't， the thing is we can't cache everything。 Right。

 And in ideal world， we would just cache the entire internet at the border， but we can't。 Right。

 So we have to pick what's our cache size going to be， and what we'll find is we'll capture。

 a lot of these high rank， low rank， the rank one items， rank two， three， four， but we won't。

 be able to cache rank 5，000。 Okay。 Any other questions？ Yeah。 Ah。

 so if we look at capturing like every， if we were able to cache those pages， the more， pages we can。

 we can cache the low， these， you know， high rank ones， the more we would。

 capture what people are trying to browse， but we need a， you know， a， you know， petabyte。

 size cache to try and capture that。 Yeah。 Exactly。 The hit rate is capturing if we cap。

 cache everything of that rank and below。 So we just have to keep going further and further。

 you know， to get to action， you can， see we're still not at one。 You get to one， you know。

 we're going to be caching， you know， rank one million， one， you， know， in order to capture it。

 And that's just going to be expensive。 Right。 If memory was no， you know， disk space was no issue。

 then we could have an arbitrarily， sized， large size cache， but because we have to set a limit。

 you know， we have to look at， a trade off。 And so we， if we end up over here， right， we're， we're。

 we're getting an 80% hit rate， but， that means 20% of our stuff is still missing。

 Any other questions？ Okay。 So let's， it says， are there operating systems that have access to multiple caches。

 but use， different methods for each one？ Absolutely。 So every cache we have， you know。

 we ask those questions， like for example， replacement， policy and， you know， for TLB。

 we say random is often good enough because we can employ。

 what we implemented in hardware for demand paging。 We're going to do it in software。

 And so we're probably going to implement something more sophisticated and predictable， than。

 than random。 And the question is if we have too many caches， would it not be worth it？ Yeah。

 So there's always a trade off， right？ Every time we look in a cache。

 there's a cost associated with that。 And so that's why we don't have 20 level caches on processors。

 We typically have like three levels of caching。 The L3 is typically shared across multiple cores。

 There's always trade offs in terms of， you know， the value of chip real estate versus。

 the performance benefit that you get versus the performance hit that you， the latency。

 hit that you get of having to go through yet another cache。 Okay。

 So we can compute our average access time for main memory。 So let's look at that。 So if our。

 so our effective access time is going to be our hit time plus our miss rate， times our miss penalty。

 So as an example， let's say our memory access time is 200 nanoseconds and our average paid。

 fault time is eight milliseconds。 We'll say our probability of a miss is P。

 So one minus P is our probability of a hit and， we can compute our effective access time as follows。

 All right。 So it'll be 200 nanoseconds plus P times eight million nanoseconds。

 So if one out of a thousand accesses causes a page fault， that seems like a relatively。

 small number。 A thousand accesses run at full speed and one access runs expensive。 Well。

 it actually yields an 8。2 microsecond average memory access time。

 So we've now slowed our machine down by a factor of 40。 So it looks like our machine just stopped。

 Right。 So a different way to think about it is what if I wanted to bound the slowdown？

 I wanted to say I'm willing to slow down my machine by 10% for demand paging。 So what would I need？

 Well， I'd need to have a page fault rate of about one in 400，000。 All right。

 So this is why it's going to be really important to come up with a replacement algorithm。

 That's really good because if we picked the wrong page and evicted and then go to reference。

 that page， well， now we've made our machine run at the speed of our disk。 Okay。 So question is。

 why do we miss？ Well， we don't have enough space or not enough space。

 We haven't referenced it before compulsory。 We'll get to space and just more compulsory。

 We haven't referenced the page before。 So that's going to cause us to miss。 We could do prefetching。

 but that's super controversial。 So prefetching says， hey， if I've referenced this page， well。

 I know I do sequential access， so I'm likely to reference the other pages after it。

 So I'm going to pull those pages in when I reference that first page。

 The risk is what if I don't reference those other pages？ Well， to pull those pages in。

 I evicted other pages from memory and I use disk bandwidth。

 to pull those pages in and then I don't reference them and I've kicked other pages out so I。

 could actually drive my miss rate up。 So that's why prefetching is always controversial。

 And we have to predict which pages to actually prefetch。 So capacity。

 That was the one I meant to say。 Not enough memory。

 So we have to kick something out of the cache and that's going to cause us to have to pull。

 it back in later when we reference it。 So somehow we have to increase the available memory。

 So this is one of the things。 My friends， they're like， oh， you're in computers。

 can you help me with my windows？ It runs slow。 I'm like， I don't do that kind of computer stuff。

 But I say， how much memory do you have？ And then people say， oh， I have eight gigabytes。

 I go out and buy 32 gigabytes。 Not very expensive。 It'll make your machine run much faster。 Right？

 Because again， think about it。 If we're taking a fault every thousand references。

 it's a slowdown of 40， factor of 40。 So extra memory。

 you avoid capacity misses and you run it closer to that 10% overhead。 All right。

 So increase the amount of DRAM or adjust the amount of memory that we allocate to a process。

 If it's not getting enough memory for its working set， then it's just going to be page， faulting。

 not making for progress。 And so we either give it more memory or we're just going to say， all right。

 you run slow， and it's not very useful。 And you're taking up memory that can be used by other processes。

 So this conflict misses。 Technically， we shouldn't have conflict misses unless we had something broken in how we select。

 empty pages or something like that。 And that kind of really gets into policy misses。

 So where we replace the wrong page and that causes us to then fault and have to pull that。

 page right back into memory。 So solution invests more time and software cycles in a better replacement policy。

 Okay。 So some administrative stuff。 We have a midterm coming up on Thursday。

 It's going to cover everything including this lecture。

 And there was a review session yesterday and the slides and video for that are available。

 on the course website。 Questions？ Yes。 [inaudible]， Absolutely。 So the question is whether。

 you know， the idea here is investing more in the software。

 associated with the replacement policy to get a better replacement policy is worth it。

 And the answer is absolutely。 You can improve the hit rate。

 You're going to make your programs run dramatically faster。 Right。

 And so a better replacement policy or like I said， you know， going out and adding more。

 physical memory。 So you reduce capacity misses。 Those are all going to yield lower mis rates and yield much better performance。

 And this all is true because there's that huge difference。 Right。 If we think about like， you know。

 TOB， we can access the TOB in fractions of a nanosecond。

 versus going out to main memory is a hundred times slower or more。 Right。 A hundred nanoseconds。

 The difference between RAM at a hundred to 200 nanoseconds versus 10 million nanoseconds。

 is so large that it really makes sense for us to invest in a good replacement policy。

 Because with the TOB， we thought， well， we'll just we'll do it in hardware。

 Because it's a significant cost， but it's not as significant a cost differential。 Okay。

 Page replacement policies。 Again， reason why we care about replacement policy is because it's important for any cash。

 I just talked about， you know， how we we made that decision with TLBs that TLBs are typically。

 hardware managed。 MIPS was an exception where they do a software TOB。 But with pages。

 it's really important because this huge difference between the access times。

 to main memory and the access time of disk。 So we don't want to throw out something important。 Okay。

 So first policy， FIFA， first in， first out， sounds pretty simple。 It is pretty simple。

 So we throw out the oldest page。 The page we first pulled in from disk is the page where first going to kick out to。

 disk。 All right。 You could argue it's fair。 Every page gets to live in memory for， you know。

 sort of roughly the same amount of time。 But the disadvantage is if we have an old page that's frequently used。

 like it's some， critical code set， you know， piece of code that's used across multiple processes and。

 we kick it out of memory， next thing we do is going to be to pull it right back into memory。

 So that's a downside with FIFA。 Random。 Random is easy to implement。

 So you don't random number generator， pick a page， you're an evicted， right？

 But if you think about it， that worked well in the TOB where there was a high cost， a factor。

 of 100 to go out the disk。 But here again， 100 nanoseconds。

 200 nanoseconds versus 10 million nanoseconds。 So we picked the wrong page and evicted。

 It's going to be really bad for performance if we're looking at， you know， soft real time。

 or interactive systems。 So unpredictability is not something we want when it comes to paging。

 So looking at it the other way， what's the best we could do？ If we had to pick some page to evict。

 which page would do sort of the least damage to， evict the page？ Well， it's going to be the page。

 not the page that we're going to reference next， not the， page we're going to reference after that。

 not the page we're going to reference after， that。

 but the page we're going to reference farthest in the future。 Right？

 That's provably optimal going to be the best that you can do when you're limited in the。

 amount of memory that you have。 And so that's going to be our min algorithm。

 We can't implement it because we don't know the future。 If we knew the future， you know。

 we'd all be in Dogecoin or something like that。 And so we're going to instead think about programs as being consistent and if they haven't。

 accessed something for a long time， they're not likely to suddenly turn around and access， it。

 So we're going to use the past as a predictor of the future。 And that gets us to LRU。 So with LRU。

 we look backwards to the thing that was least recently used。

 And that's the page that we're going to evict。 And hopefully that's going to reflect something like min。

 It's going to be a good approximation of min。 Now how would we implement LRU？ Well。

 one way would be to just use a list。 So when we reference a page。

 we place it at the head and the tail is the least recently， used page。 So when we need a free page。

 we just pull it off the tail and give it to a process。 But think about this for a moment。 Right？

 What is use me？ Use means instruction fetch。 Use means memory load。 Use means memory store。

 So on every instruction fetch， every load， every store， we would have to update this list。

 That's not really very efficient。 All right。 That'd be incredible number of software cycles for every single memory reference。

 And yes， you know， it would allow us to pick the oldest page to replace， but it would come。

 at a severe penalty from a performance standpoint。 So we're going to approximate LRU， which again。

 remember， is going to be how we're going， to approximate min。

 So we start with the gold standard of min。 We approximate it with LRU。

 And then we're going to approximate LRU with a bunch of different approaches。 Okay。

 So let's look at what this would look like。 So we'll use FIFO as our strawman to start。

 We're going to assume we have three physical page frames and a virtual address space that。

 has four pages。 And we're going to have the following reference stream， A， B， C， A， B， D， A， D， B。

 C， B。 OK， so here's what this is going to look like。 Three physical frames here。

 And let's look at what our references do。 So first A， what's going to happen？ Reference A。

 We're going to page fault， right？ It's a compulsory page fault。 It's not in physical memory。

 so we have to page fault and bring it in。 So we'll bring in A。 Where's it going to go？ Well。

 we're just going to pick one at random。 We'll pick one。 OK。 Next reference for B。

 Where's it going to go？ Well， again， it's a compulsory miss。

 So we'll put it in the next available free frame， which is two。 Next is going to be C。 Again。

 compulsory miss。 We'll replace or bring it in to free frame three。 Right？ Now we reference A。

 That's in memory。 That's a hit。 Runs it full speed。 Reference B。 That's in memory。 That's a hit。

 Full speed。 And oh， now we reference D。 So that's going to fault。

 What was our first page-- we don't have any pages on our free list。 What was our first page in？ A。

 the page one。 So we're going to replace A with D。 And then our next reference-- oh。 It's for A。

 All right。 So what's our oldest first in frame now？ Going to be frame two B。 So we'll replace B。 OK。

 And our next reference is for D。 That's a hit。 That's great。 Our next reference is for B。

 It's not in memory。 That's a fault。 So who are we going to replace？ We'll replace three， C。

 And then we're going to reference C， which we just kicked out。 So now our oldest is going to be D。

 We'll replace D。 And now we reference B， which is a hit。 So we ended up with seven faults。

 And one of our faults was really bad。 Because when we referenced D， we replaced A。

 And then immediately referenced A。 And similarly， we replaced B。 And then-- no。 OK。

 Let's look at what the best choice would be at every given， moment， given our trace。

 So that'll be min。 So A comes in。 Nothing we can do about it。 Compulsory， same with B。 Same with C。

 Two hits。 OK。 Now D comes in。 Which should we replace？ So now we're going to look forward from D。

 And we'll see， well， we're next going to reference A。 So we don't want to replace A。

 Then we're going to reference B。 So we don't want to replace B。 And C is the furthest out。 So yes。

 it will be C that we replace。 Now A is a hit。 B is a hit。 B is a hit。 Oh。 Now C。

 So now who do we replace？ We're going to replace A or D。 So we'll replace A。

 And then B will be a hit。 So min ends up being five faults。 When we go to replace a frame for D。

 we look as far as we can into the future， to see what's the furthest out reference。

 Now it just happens that LRU does the same thing。 But that's not guaranteed。 In fact。

 if you think about it， we， could come up with a pathological example of where LRU is。

 going to do poorly。 So here， consider the reference stream ABCD， ABCD， ABCD。

 Same setup for virtual addresses。 Every physical page frames。

 And LRU and FIFO are actually going to do the same thing。 OK， so A is going to be a miss。

 B is going to be a miss。 C is going to be a miss。 Now D comes in with LRU。

 which frame is least recently used？ A， right？ Because frame one， so we replace A。

 And then we reference A。 Now， which frame was least recently used？ B， frame two， so we replace B。

 And now we reference B。 Which frame was least recently used？ C。 And so you can see we're basically。

 going to fault on every single reference。 So this is a little bit of a contrived example。

 of N plus 1 as our working set size。 And we only have N frames available。

 But it demonstrates that if you have fewer physical frames， available than your working set size。

 you're going to be taking a lot of page faults， and running at disk speed instead of running at memory speed。

 So let's look at instead what would be a better--， and again， this gets to a like。

 why replacing policies。

![](img/b17bfb079039a891e4b53e4d5e7fbc52_9.png)

 are important， what would min do？ So now the reference for B comes in。 Which frame do we replace？

 Looking into the future， we want to replace C。 Now when the reference A and B will run out of memory。

 and now the reference for C comes in。 Which frame do we want to replace？ It's going to be B。

 Because we're， going to do D， then A， then B。 So we replace B。 Now D and A run out of memory。

 And now we get the reference for B。 And so if we look into the future， we can replace A。

 So we can see much fewer faults。 That's why replacing policy is important。



![](img/b17bfb079039a891e4b53e4d5e7fbc52_11.png)

 OK， now a desirable property we want to have， is you add more memory， you spend more money。

 and you get better performance。 In that you have--。

 as you increase the number of physical frames that， are available。

 you watch your number of page faults drop。 All right， now there's always going。

 to be some floor because there are compulsory misses and so on。

 But does every replacement policy have that property？ Throw more memory at it。

 and it performs better。 Intuitively， it seems like the answer should be， yes。 I have more memory。

 so I should be reducing capacity misses。 But you can have policy misses。 And so for some algorithms。

 we have what's called， balates anomaly， where actually adding memory。

 doesn't decrease the fault rate。 So for LRU and MIN， it's guaranteed。 You give them more memory。

 you will get better hit rates。 But for FIFO， it's not always the case。 And this is the anomaly。

 So consider this following page reference key。 Three frames， and the reference string here， ABCDE--。

 so five in our virtual address space--， mapped into three。 So how many faults do we have here？ Nine。

 If I now add an additional frame， how many faults do I have？ Ten。 So I added memory。

 and my number of faults went up。 So here's the thing。

 Look at the contents of memory with three frames， the contents of memory with four frames。

 Completely different。 And that's the anomaly here。 With FIFO， the contents of memory。

 can be completely different， which， means the hit rate might actually be lower。 With LRU and MIN。

 the contents of memory with X pages， is going to be a subset of the contents of memory at X plus 1。

 This is a little confusing。 It's a little counterintuitive。

 But it's a side effect of how FIFO treats memory。

![](img/b17bfb079039a891e4b53e4d5e7fbc52_13.png)

 OK。 Approximations。 So yeah。

![](img/b17bfb079039a891e4b53e4d5e7fbc52_15.png)

 [INAUDIBLE]， Yes。 The question is MIN guaranteed to be the most optimum policy。 Yes。

 because MIN can look in the future。 So MIN knows exactly what's the least impactful frame。

 to replace。 The most impactful is to replace the frame。

 that you're going to reference immediately following。 So MIN looks as far into the future。

 and tries to delay that page fault to be as far in the future， as possible。

 And it's doing that on every page replacement。

![](img/b17bfb079039a891e4b53e4d5e7fbc52_17.png)

 OK。 So we can implement MIN。 We can't implement LRU。

 So we're going to implement an approximation to LRU。

 We're going to look at a couple of different ways， of doing that approximation。

 So the first is an algorithm called the clock algorithm。

 So we're going to take all our physical pages in memory， and conceptually。

 we're going to arrange them in a circle。 And then we're going to have a clock arm that's。

 going to go around all those pages and do the following。

 Our goal here is we need to find a page to replace。

 We're not going to try and replace the absolute oldest， referenced page。

 We're just going to try and replace an old page， a page， we haven't referenced in a while。

 And that's the trade-off。 So rather than trying to implement an exact LRU。

 we're going to implement something that just picks an old， referenced page and kicks it out。

 So some of the details。 We're going to have a hardware use bit or access bit。

 And if that bit is set--， or that rather that bit gets set every time we reference a page。

 So if we do an instruction fetch， a load or a store to a page。

 the hardware will automatically set that use bit for us， that access bit for us。

 Now that could be set in the TOB。 If it's set in the TOB， then when we evict an entry from the， TOB。

 we need to copy that use bit back to the page table， entry that that TOB is caching。

 On a page fault， what happens？ We advance the clock arm。 If the use bit is set， what does it mean？

 It means the page was recently accessed。 We clear the use bit and advance the hand。 If it's not set。

 if it's 0， it means that page hasn't been， accessed in a while， and that could be a candidate for。

 replacement。 So we could pick that page to replace。 OK， a little bit more detail。

 As this hand is going around， are we eventually going to find， a replacement candidate？ Yes。

 Even if every page in memory is recently accessed， that hand， will just set it to 0， set it to 0。

 set it to 0， and advance， all the way around until it comes back around and finds a。

 page that's marked to 0。 And that becomes our replacement candidate。

 So that effectively becomes FIFO at that point。 Now。

 what does it mean if the hand is moving very slowly？ And is that kind of like good or bad？ Well。

 it means that there are not many page faults。 So that's probably good。

 It could also mean that we're finding pages very quickly when， we do have a page fault。

 That's also good。 Now， what if the hand's moving really quickly？ Well。

 it means that either there are lots of page faults or。

 it's taking us a long time to find a free page， like all the， pages are in use。

 So we have to go all the way around on every single， access to find a valid page to replace。

 So the way you can think of the clock algorithm is we're。

 partitioning our pages into young pages that are， referenced a lot and old pages that aren't referenced as much。

 But if we're just looking at two sets， why not have more， than two sets？

 Then we could start to think about the granularity of， the page。

 And then we could start to think about the， number of pages that are written in the， form of a page。

 And then we could start to think about the number of pages， that are written in the form of a page。

 And then we could start to think about the number of pages， that are written in the form of a page。

 And then we could start to think about the number of pages， that are written in the form of a page。

 And then we could start to think about the number of pages， on a page fault。

 operating system checks the use bit。 If the use bit is one， we clear the bit， we clear the， counter。

 If the use bit is zero， we're going to increment the， counter。 And if the counter equals n。

 it's a candidate for， replacement。 Question？ OK。 So what this means is for any given page。

 a hand has to go， by n times before we're going to select it for， replacement。

 So it gives it n chances to get accessed。 If it doesn't get accessed in those n chances， we pick。

 that page to replace。 So big question now is we just looked at n chance where we。

 just look directly。 What do we set n to be？ Well， if we set n to be really large。

 then it's going to be a， good approximation for LRU。 If we set it to 1，024。

 that's saying we're dividing these， granularities of how old that page is into really fine。

 granularities。 It's not perfect LRU， but it's going to be a really close， approximation of LRU。

 But if you think about it， though， that's not going to be， very efficient， right？

 The hand might have to go around 1，024 times before we， actually find a page to replace。

 So if we pick a smaller n， it's going to be much more， efficient。

 but we're not going to have as true a reality， around what's LRU。

 It's going to be more of a coarse-grain approximation。

 So we find something that balances finding pages， quickly and efficiently with picking the right pages to。

 a bit。 OK。 So yes。 Yes， so the question is if we're looking at n chance， does。

 it mean it's going to take n sweeps every time we want to， find a page？ Not necessarily， right？

 Because we could have already have gone by a number of， times in the past。

 And so as we advance the hand， we might find a page where， advancing the counter hits n。

 So the first page fault--， yeah， potentially could require n to go around and find it。

 if all pages have been recently accessed。 OK。 So all of this。

 we didn't consider what happens if the， page we picked to replace has been modified。 So remember。

 we're doing writeback caching， so that means， we may have done a bunch of writes。

 What's on the backing store doesn't match what's in memory。 So we actually have to--。

 it's going to take extra overhead because now we have， to schedule that page to be written out。

 That takes tens of millions of nanoseconds to write that page。

 out before we can spend the tens of millions of nanoseconds， to bring the page in。

 So maybe what we do is we give dirty pages an extra chance。

 So we don't consider them for replacement when we first， realize， hey。

 maybe we should replace this page that hasn't， been used in a long time。 So a common approach is。

 say， for clean pages， we use n， equal to 1。 And then for dirty pages， we use n equal to 2。

 And when we hit n equals to 1， when we realize the page is， dirty， we schedule it to be written out。

 So then hopefully by the time the hand comes all the way back， around， that's now a clean page。

 And we can just evict it and replace it with the page， that we want to pull it。 All right？



![](img/b17bfb079039a891e4b53e4d5e7fbc52_19.png)

 OK。 So if we come back again-- yeah， question？

![](img/b17bfb079039a891e4b53e4d5e7fbc52_21.png)

 [INAUDIBLE]， Yes， the question is， what do I mean by n equal to 1 and n， equal to 2？

 So it's a question of when we consider it for replacement。 So if you remember here。

 if we hit the page and the use is 0， we increment the counter。 If it equals n。

 then we evict that page and replace it。 So what we're going to do is that when we're going around。

 if we hit a page that's 0， it's use bit of 0， we increment the counter。

 If the counter now equals 1 or greater， we replace it。 If it's clean。 If it's dirty。

 then we're going to assume n has to equal 2。 We're going to schedule it to be written out。

 By the time we come all the way back around， if it still hasn't been used， hopefully at that point。

 the counter will now be 1。 It'll get incremented， and we will now。

 be able to-- it'll also have been renounced， so now we can replace it。 OK。

 Coming back to our page table entries， what bits are we going to use here？

 We're going to use the present bit。 We're going to use the writable bit， the access bit。

 and the dirty bit。 So those are the bits that we're going to use。

 for all of the bookkeeping that we need to do to figure out， whether a page is valid。

 whether a page has been written， whether a page is writable， and whether the page has been used。

 All right。 So some of the variations of clock algorithm。 Do we really need a modified bit that's。

 implemented in hardware and tells us， whether things are dirty？ The answer is no。

 We could emulate that in software。 So we're going to need some extra books that keep track。

 of which pages are allowed to be written and which aren't。

 but we could simply mark all pages as read-only。 And then when they get accessed to write。

 check the books to see are we allowed to write it？ If we are， we mark that now in software。

 the page has been modified， and we mark the page table。

 and we can see how the page is written and how the page is， written and how the page is written。

 So we can see how the page is written。 So we can see how the page is written。

 So we can see how the page is written。 So we can see how the page is written。

 So we can see how the page is written。 So we can see how the page is written。

 So we can see how the page is written。 So we can see how the page is written。

 So we can see how the page is written。 So we can see how the page is written。

 So we can see how the page is written。 So whenever we write it back to disk。

 we clear in our software modified bit。 Similarly， we could ask， do we need a use bit in hardware？

 That's what gets set on every single memory reference。 Now， again， we can emulate it in software。

 So now we're going to keep a use bit in software， and a modified bit in software for each page。

 And we're going to use the page table infrastructure， to do both of those。

 So we'll mark all pages as invalid， even those that are actually in memory。 Now。

 when you reference one of those pages， what will happen？ Trapped to the operating system。 Again。

 the operating system is going to look in its double， books and see， oh， this page is actually valid。

 So all market is used。 If that was a write that occurred。

 I'll also mark it as dirty and set it as read write。

 If it was a read or instruction fetch that occurred， I'll mark it as read only。 All right？ Now。

 when the clock hand passes， I'll， set that software use bit back to zero。

 and mark the pages invalid in the page table entry。 Flush the TOB entry for it。 The modified bit。

 I don't touch， because the page is still， dirty and needs to be written back to disk。 Now。

 clock itself is just an approximation of LRU。 It's just one way that we could implement LRU。

 What are other ways that we could do it？ All， again， we're trying to do here， is identify old pages。

 not necessarily the oldest page， but just an old page。

 So another approach that became very popular for a while。

 is an approach called the second chance list。 And we still have variants of that today。

 So this was used in the VaxVMS architecture。 And the idea was we split memory into two regions。

 an active region of pages that are actively， being used， which we manage FIFO。

 and a second chance list， that we mark as LRU for pages that are considered inactive。

 So pages in the active list are marked read/write。 Pages in the second chance list are marked LRU。

 So active pages， we can reference those at full speed。 Accesses to the second chance list。

 those are going to trap into the kernel。 OK。 Now， when we have overflow from our active pages。

 we move that page onto the head of the second chance list。

 If we access a page that's on the second chance list， we're going to trap into the kernel。

 that tells us that this page we thought was inactive， actually is active。

 So we're going to move it to the head of the FIFO， for the active pages。 All right。 Now。

 page in from disk， it's active， so it's going to go to the head of the FIFO queue。

 here for our active。 And that's going to force us to evict a page out of memory。

 and we're just going to pick our LRU page。 So what does this give us？ Well， if we think about it。

 if we put all of our pages， onto the active list， it's just FIFO。

 If we put all of our pages onto our second chance list， it would be pure LRU。

 but it would be really expensive， because we trap on every memory reference。

 So we picked some intermediate， and that， gives us the advantage of fewer disk accesses。

 because we let pages live in memory longer。 We have a higher fidelity LRU implementation。

 even if they're unused。 But the trade-off here is we're going。

 to increase the number of traps that we have， into the operating system。

 So this is where we're trading off traps for hopefully。

 having a higher fidelity representation of LRU， as an approximation to min and reducing our overall misread。

 So the cool thing here is with page translation， it's really up to the operating system developer。

 to figure out what replacement policy do I want to implement。

 The hardware gives us the ability to implement anything we want。

 And if the hardware doesn't have that capability， we can emulate that capability in software。

 So a little side-factor of history， why did the VaxVMS have a software implemented。

 use bit and software implemented modified bit？ Because when the architect asked the operating system。

 developers， do you need a hardware supported use bit， and a hardware supported modified bit。

 they said no。 Why， who knows why。 But it turns out it wasn't the end of the world。

 because they were actually able to emulate them in software。

 And the VaxVMS line was a very successful line， of many computers。 OK。

 Another thing we have to think about is our free list。 Yeah。 Well， again， the question is。

 is it really expensive， to have to trap into the operating system， to implement the use bit？

 Absolutely。 If you had any choice otherwise， you would not want to have to do a trap on every use。

 But they were able to amortize it， because it's only the first reference to a page that's。

 going to cause the trap。 But still， it would have just been a lot easier。

 if you had a hardware implemented use bit， and hardware implemented modified bit。 OK。 So yeah。 Yeah。



![](img/b17bfb079039a891e4b53e4d5e7fbc52_23.png)

 So the reason why we have to trap， is because the second chance list is marked as invalid。

 So if we try to access anything on the second chance list， the page table entry is invalid， which。

 is going to cause us to trap into the operating system， so that we can then move it onto the active。

 And market is used and if necessary， market is modified。 [INAUDIBLE]， Yeah。 So the question is。

 if it's marked as invalid， how do we know that it's on the second chance list？

 So this is where the double books come into place。

 The operating system has to have a side set of books that， tell it， oh， these are the pages that。

 are on the second chance list and not just pages that， are maybe out on disk。 And again。

 we might be able to do some of that， in the page table entry， depending on what bits we have。 OK。



![](img/b17bfb079039a891e4b53e4d5e7fbc52_25.png)

 So I'm going to skip the free list， and we will go through our summary。 OK。 So replacement policy。

 So we looked at FIFO， which places pages on a queue， and replaces the one at the end of the queue。

 We looked at the page that we're going to reference， farthest in the future to replace。

 It's optimal， the best we can do。 We looked at LRU because we don't have the future。

 And we're going to use the past as a predictor of the future， assuming programs behave rationally。

 We looked at the clock algorithm as an approximation， to LRU。

 arranging the pages in a circular list， sweeping through with a clock hand。

 And if a page is not in use， picking that page， for potential replacement。

 We looked at finer granularities for treating young versus， old pages。

 The nth chance algorithm was an example of that。 Another example is having a second chance list。

 where we actually can implement LRU on a smaller set of pages。

 So we have pages that are truly treated as LRU， and then we have pages that are treated in a FIFO manner。

 We have our working set， which is the set of pages， that have been accessed recently。

 And we didn't get into thrashing。 We'll get into that after spring break。

 But thrashing is when we have too many different pages。

 So our working set sizes across all of our processes， is greater than our physical memory。

 So that's the case where we are continually taking capacity， misses and always going out to disk。

 All right， so good luck on the midterm。 Again， it's on Thursday in the evening。 [VIDEO PLAYBACK]。

 [END PLAYBACK]， [BLANK_AUDIO]。

![](img/b17bfb079039a891e4b53e4d5e7fbc52_27.png)