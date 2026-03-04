# 【计算机体系结构】普林斯顿—中英字幕 p65 64_04_page-based-memory-systems -BV1ii421D7WR_p65-

![](img/3f403a887ba87946fe952a5a59e63fa8_0.png)

Well。Computer architects came up with something fun here and came up with this notion of paging。😊，So。

 instead of having。Variable size。Programs。And have variable size segments or data segments。Instead。

 what you can do is you can take all of your memory and you can chunk it up。

Into different fixed size。Regions。So for lack of anything better。

 let's say you have all of memory and you chunk it up into 4 k regions。And we call it a。Page。

So what is， what is this really。Turn into well。Let's say we have the address space。Of a user here。

And it thinks memory goes 0，1，2，3。Over here， we have physical memory。And what you can end up with is。

A table， which will map。These different addresses in different locations， possibly out of order。

Over there。 And it's a chunk at a time。 So if you go to access， let's say， address 0 to 4 kB， -1。

You are accessing here。 if you go to excess 4 kilobyte to 8 kilobytes minus-1， you're accessing here。

But this is a virtual address space。Once we go through the translation， if we go to access。

 they'll say address。4182。Rishshing it mapped up over to here into physical memory。

And just to introduce some nomenclature here。If you take a processor generated address or a virtual address。

 if we go to look at what is actually inside there。There's a page number。Which is this number here。

Which is which page to go look at。And then there's an offset。

 which is the low order bits of the address。And the offset says。

Where inside of this physical page to go find the exact bite we're looking for。

And it's pretty common for these page sizes to be in the sort of few kilobytes sort of range。

 If you go look at something。I don't know。 we'll take X 86， for example。

 X 86 default page size is4 kilobys。But it also has a2 MB option and like a1 GB option。

 Some architectures， like Mips actually has quite a few。Page size options。

 So I think you can go anywhere from 4 kB。By maybe powers of two all the way up to， I think。

 maybe 4 MBbys。So you can have different page sizes。 But right now。

 let's just abstract that and just say。There's a fixed size of some small number of kilobytes。

 Actually， the first original machines actually had these even be smaller。

 They had them be maybe about 512 B。But as memory got bigger。

Page sizes could get bigger and we'll talk about why you might want to have bigger page sizes。

But really， what happens here， this page table allows us to take a contiguous memory。

A set of memory addresses and map them into a non conuous space。Now。

 this can really get away from having fragmentation。Because all of a sudden。

The worst we can be the most amount of memory we can be wasting is a size of a page。

So let's say you have one byte on this page here。And we call that as used。😡，Well。

 your worst thing you're using is4 kilobytes here if you have a 4 kilobyte page。

Page in this page some other process can use。Because we have a very flexible reming system。

 It's it's a complete mathematical map。So that's looking at if you have one program。

We can extend this pretty easily to having。Multiple programs at the same time。

 where each program has a different page table。So if you have a processor which is excluding multiple programs。

 let's say it's time multiplexing these programs。In physical memory， you can actually。

Intermingle all the different pages of the different programs and do memory allocation where you try to pack the memory as tight as possible or reuse the memory as much as possible。

And these really flexible page tables here will allow the remapping to be arbitrary。

So you don't have these， at you don't have an external fragmentation problem。

You may still have what's called internal fragmentation。

 where you're just not using the pages very effectively。嗯。So this is interesting up here。

This figure here， we have。OS pages。So what， whats， what are O S pages。 Well。

 the US itself needs its own code and its own data。And many times in a paging system。

 the O itself may not use a page table to go access memory。Because it needs to go， let's say。

 start up another program。 So it needs to be able to touch these bytes here and go。

 you know kill a program or load some data from a particular application。So many times， the O S。Is。

 to larger extent， held to a higher standard here。 And the O S can actually go and touch all physical memory and not have to go through a mapping layer。

Okay， so here we have private address spaces per user。So something we have not addressed yet is。

Where do we store this stuff？And how big are these page tables？Well。They can get pretty big。

If you want to basically have a program that can address。4 GB of Ram。You're going to need。

A page for each  four kilo of those  four GB。That's a lot of pages。

So you need to store this somewhere。So the naive approach is you just have specialized register files in your processor。

That hold the entire page table。Unfortunately， that ends up being。Well， for a。

4 GB space with 4 k pages ends up being something like with with， I think， a 32 B page table entry。

 We end up something like 4 MB。And if we have 100 processes running， that's 400 MB。

 they we to store somewhere。嗯。Well。It means we probably don't want to keep it in registers or our register files in our main processor。

Now。Conveniently。As we have more and more RAM。This allows us to have more and more processes to run。

It allows us to use more memory because we have more Ramminar machine。 But also， we have。

More places to store page tables if we want to put them in RA。Okay。

Maybe we want to put our page tables in Ram， because。As RamM goes bigger。

 we might need more page tables， but we have some place to go put it。 And it's always the case。That。

Well， if we design this correctly， if our page table entries are designed correctly。

 that the size of a page table to represent a certain amount of RA is going to be less than the amount of RA that you have to store in it。

Sos some fixed overhead。 So let's take， for example， a page table entry。

 which is takes 4 B to represent 4 kB。Of memory。That's 1，000 to one compression。

So as you get more Ram， you're guaranteed to always have some place to put it because your Ram size will grow 1000 x faster than your page page size。

Okay， challenges of storing this in RAM。If we want to go。Access a page。

When we go to access a page here， we have to index this table。So every load we do。

Before was just a single load， but now we're going have to do a load to go read the page table and load from the actual physical memory location。

Well， we just doubled our number of memory references。That we have。And' that's kind of a bummer。

What do we， what do we do about this。Well， before before we talk about that。

 let's talk about where to store the page table。And the size。

 and there was probably some techniques to speed up the axis。So here。

 let's take a look at where where to store。A page two。

If we have our linear page tables of what we've been talking about to this point。

You can actually just go store them in RA， and they'll map down to different points down here。

And this， this works decently well。Unfortunately， these still have to be contiguous themselves。

So we might get fragmentation problems in the page tables themselves。Or。

Different page tables fighting with each other for memory。 They're hard to move。

So we would like to think about some way to go solve this。

We'll hold off for a second on how to solve that， but this just something to think about。

Kind of unpleasant here to think that。Your page tables themselves cause fragmentation。So。

I just want to sort of recap and show the mechanics of this of what's， what's in our page table。

So in our page table， what we're going to store。Is we're going to have， well， first of all。

 we're gonna have a。Instead of having a base bound register。

 like we have in the basin bound architectures， we're gonna have a base that points to the base of the virtual。

points to the base of the page table。And then。We're gonna have some structure in Ram There structure in the page table here。

And what does the structure look like， well， there's probably a valid bit。There's。

A physical page number。Which points to someplace over here。And maybe there's some status bits， also。

We'll talk about those more in a minute。You probably want some status registers there。

Could track some information like how often a page is being used。Which pages are used。

 Maybe some statistics。 Maybe you want to know whether you can read the page or write the page。Now。

This last note here is。Is sort of the key to time multiplexing a processor between different processes。

As different programs execute。And you time slice or preemptively multitask between different operating systems or just different applications on one operating system。

 What you're going to do is you're actually going to change this base register。To something else。

And effectively what this does is this completely changes your entire map of memory as you're executing。

And this is pretty， pretty fancy。 if you think about， you can just one， one right to one register。

 and all of a sudden， all of memory looks different。And the protection is totally different for the。

 the application。 Now， you might be thinking to yourself。If I'm running the operating system。

And I changed this register。All of a sudden and the changes the entire map of memory。

 How do I not crash the operating system instantaneously because all of a sudden。

The operating systems code has got re to some other location。Well。

Theres some magic behind behind the scenes here。 This is what I was saying is that there's a couple different approaches to this that the basic approach。

 the operating system will not use paged memory for its own purposes。😊。

It just uses physical memory for everything。 and there's a special bit that says you're in operating system mode and what you're doing basically doesn't have to abide by the paging system。

That's one approach。 Another approach is you'll have entries in the page table here that are all the same in every process。

And it always maps the operating system in at a certain location。 So you can change this Willy nily。

 But all the things you go to change it to will have the operating system mapped to the exact same location。

That's another approach that people use， And there's something that kind of in between those。

Just to flip back here， one thing I did want to point out is it's important。

That an application is not able to modify its own page table or modify other applications' page tables。

😡，And hence， you know， this。Application here tries to go access something。

 It looks up in the page table and that says， oh， that's down there。

 It's important that this does not like overlap with someone else's page table。 All of a sudden。

 you'd allow an application to be able to change its own memory mapping。

 that would be quite dangerous。O， so so far， we've talked about， oh， actually。

 before weve bought this。Let's talk about the exact mechanics of this。So you have a virtual address。

Has this。Virtual page number and offset。This is actually index into this table。It's the basic index。

 It's， it's one huge table。It just indexes into here and gets out some bits and those bits get basically replaced or to take a virtual dress into a physical address。

 We're going to take the virtual address。 We're gonna take the virtual page number。

 and we're gonna remove that。We're going use that to index into here。

 And then what comes out of here is going to be used to be the new high order bits of this address。

 And we're to call that the， the physical address。One last note about this。

 we talk about here a disk page number。We're going we talk about this more at the end of today's lecture。

But it's possible。That you might want to use this location here to say。

The bits for that page are not here right now。 They may be on disk。

We we're going to talk that more advanced。 This is the virtual memory subsystem。But a lot of times。

 a convenient place to locate that information is in the page table itself。Okay。

 so let's crank through some map very quickly here。This page table is。😡，Relatively large。

 So let's take example here， a 32 B address space。It has。4 kilobyte pages and each page table entry。

 PTE。Is four bytes？So there's  two to the 20 page table entries。 Each of those is 4 by big。

 This is a megaby times 4。 end up with 4 MBby。Okay。

 so that's four megabytes for this table per user process。And this assumes that we only have。

 let's say。Four gigs worth of address spaces address space， four gig address spaces。嗯。

That's not too horrible。If you have 10 processes running。That is pretty bad。

And if you go type top on your system and you go look to see how many processes are running。

 you probably have a few hundred running。So if we use this linear page table notion and you get 10 processes running。

 all of a sudden you'd be using 4 gigabys of memory。

 which is your entire address space on a 32bit machine just for the page tables and have no place to put actual data。

So I'll give you guys a hint here that people typically don't use linear page tables。

Because it's not very storage effective。Now， what are some approaches to make it more storage effective？

You can go to larger pages。So instead of having four kilobyte pages， we have one megabyte pages。

So that would， that would take。The number of page table entries and dramatically shrink it。

And they would also directly shrink the linear page table size。

So downside is you start to have some more internal fragmentation。

 So if you use 1 B onto a new page and the whole rest of the page is empty。

 you'll be wasting a megaby-1 versus 4 kB，-1。 So you have a higher amount of internal fragmentation。

Another challenge is that on a page fault， you're going have to pull in a lot more data。

Instead of pulling off of disk， will say。4 k。 of memory you might pull a megaby。 and just bigger。

 bigger numbers to deal with。 And， and this could be painful。So let's。

 let's think about actually the。let's move from a。Old computer to a more modern computer。

So more modern computer， we have much larger address spaces。

 We want to access larger amounts of memory。So， my laptop has six gigabys of RAM。Well。

 6 gigabytes a Ram， that's bigger than 2 to the 32。We can address that in a 32 B machine。 And。

 in fact， my， my laptop is a 64 B machine。So。Let's， let's crank through the math now。

For instead of having a 32bit machine， having a 64 bit machine。Well。

If we have relatively large pages， let's go for our megabyte page。And， well。

 megabyte page is going to give us 2 to the 44。Page table entries。

And these page table entries themselves are probably bigger because the output of them has to be。

 let's say 64 B instead of 32 B， because the。Page address is larger now。Well， all of a sudden。

One process。Page table is 35 tertes。Well， my laptop is a 64b machine。

 but I don't have 35  TB of ra in my computer。Doesn't just won't physically fit in my laptops。

 can't can't lift up 35 TB in today's。Today's technologies。That's a bummer。

So could we just not go to page systems with。64 bit address spaces or larger address spaces。Well， no。

 the world's not that。Unforgiving， we do have some， some saving grace here。

 We can think about going to different arrangements of our page tables。

 And the other nice thing is we go to more space dense arrangement of our page tables or。😊。

We can go to the notion that our page tables。Don't always have every single page being used。So。

 for instance， in this linear page table here， I have some。Slash locations。

And what this means is this is some location in memory， which doesn't have anything mapped there。

So if this is not mapped。Why do we want to store or use the storage for that space？

 So we can actually go with a sparse representation of our page tables that only have the portions of the page table that we actually need。

And it's possible that if you， that if every single page in your page table is filled out。

 you may not be able to get away with a sparse representation， and you might need all 35 TB。

To map one process， this is one process。 if you have 10 processes， multiply this by 1000。嗯。Well。

 the saving grace there is。By definition， if you're going to have one process， which is going to map。

Two to the 64。Locations of memory。That means you have two to the 64 locations of memory。

 probably in your address space somewhere。 And that's a much larger number or in your physical machine。

 rather， that's a much larger number than 35 TB。So， this compression。

Of the page table entry always being smaller than the page itself allows you to always store the page table entry into the memory that you have。

 because it always grows。To be able to fit inside of the amount of physical memory you have。

So how do we go about doing this well？One representation that we can think about。

Is having a hierarchical page table。So instead of having one big table。That is linear。

We have a table that we index into， which tells us where to go look for more data。

 And then we look in that table to look for even more data。

So here we actually show a two level page table。And what's interesting。Is。If we have an address here。

We index into here。We can actually rule out huge portions of the address space very quickly by just leaving this particular entry in the。

Higher levels of the page table empty。And then as we go drill down a little bit farther。

 we can also have empty entries。So with this， if you go look at our virtual address here。

 we're actually going to use different portions of the virtual address to index into other other structures and we can build。

 we can take this sparsity into account。Another cool trick we can do is we can actually reuse if you have a hierarchical page table like this。

😊，You can actually reuse。Sort of middle level page table。Entries between different processes。

 if they're mapping the same space。 So， for instance， if they're mapping the same。Instructions。

 you can actually just reuse。All these page table entries between two processes and have multiple pointers coming into here。

One thing that this does not change is you still have。One page table base pointer。Per。

Process or per user。You don't need to have bases over here because the bases of the second level come out of the first level。

 So it's a tree。And here， this is just a two level。

 but there are plenty of architectures that have more than two levels of page tables。

 So if you go try to build a two level page table， which is relatively unspare。On something like。

A64 B machine。 It still becomes very large。 So as you have more and more dress space。

Your address space， by definition， has to be less sparse if you have a sort of fixed amount of memory in it。

 so。What people will do is they'll actually go to maybe three levels or four levels of page tables。

Now， some downsides of this is we just took something that was。We took a load。

 which took one memory reference。And we had to added extra memory reference to go look up on our page table。

 which was in memory to go find the actual address to the physical address。 And all of a sudden。

 we turned it into。😊，3 memory references， one to do the actual load。

 one to look in here and ones to look into here。So every level of page table that we add could potentially add another load。

EhThat's， that's not very pleasant。But before we get to that and ways to fix that。

 let's look at how this gets laid out into memory。So， before。

We had all of the page tables sort of up here， and they had to deal with fragmentation between the different page tables。

But now， because we have a multi level page table， we can allocate it out of our physical memory dresses。

 sort of in an ad hoc manner。And one of the cute little tricks that most operating systems do。

And most systems do， is they make the。Size。Of one of these levels of tables。

To be the exact size to fit in a page。Cause then you can locate it easily inside of a page。

And you can allocate it like a normal userland page and just sort of mix and match it somewhere into the different locations and intermix it。

So that's pretty convenient。 This solves our external fragmentation problem for our page tables themselves。

And we can use sparsity in our address space。To use less space for our actual page table。

 So page table itself is smaller。 down downside is we might to do multiple memory references to be able to resolve a page table address。



![](img/3f403a887ba87946fe952a5a59e63fa8_2.png)

![](img/3f403a887ba87946fe952a5a59e63fa8_3.png)