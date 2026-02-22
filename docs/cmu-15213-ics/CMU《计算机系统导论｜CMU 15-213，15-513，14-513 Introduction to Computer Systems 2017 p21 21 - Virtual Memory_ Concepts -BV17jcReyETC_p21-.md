# CMU《计算机系统导论｜CMU 15-213，15-513，14-513 Introduction to Computer Systems 2017 p21 21 - Virtual Memory_ Concepts -BV17jcReyETC_p21-

十み。没。呢件事情我哋。我跟你说。

![](img/f18e487d6080f4d188a6ed046a577bb0_1.png)

Okay， let's move on。Hope you're all moving along on your。Lb。That you got through the midterms， okay。

For those of you who have senior midterm scores， we'll post a note on Piazza。

 but we did a very simple computation。Took all your WM scores up through cash cloud。

And those totaled to 24 possible points， we took your midterm， that was 20 points。

And we added those together， so it's a number 44 is a maximum。

 and then we just normalized that to arrange between0 and 100 and just did the usual cutoff so 90 plus an A a is a B and so forth。

And reported them so midterm grades are not part of your transcript or your official record。

 they're just a tool to help you and maybe your advisors might see them as well to get a sort of heads up how you're doing so we don't get too stressed about how we assign these grades we just give you a sort of general view。

嗯。So today we get to talk about something that we've been promising all term。Which is virtual memory。

 you'll remember Beck when we were talking about machine code and we talk about all the ways you can compute addresses。

But those addresses are。Always this mysterious thing。

 theres 64 bit quantity of with a lot of F in it typically if it's up on the stack and we said just wait。

 we'll talk more about how that really works later well today is when we start talking about virtual memory。

 which is the sort of the observation，You know that we've said at any given time a computer can be running many processes。

Easily 50 or more processes， if you include all the various demons that are monitoring network traffic and supporting printers and doing various things in the background for you。

As well as the programs you have that you're running the application programs and so forth。

we've seen that each of these has an image that it has a totally independent range of addresses over some range of very large range of values。

 and somehow each of these processes thinks it has some range of addresses and yet they're all sharing the actual memory of the computer and managing not to trip all over each other and mess each other up。

 and that's the idea behind virtual memory。Giving you the illusion， the virtual。

That somehow you've got access to a lot more memory than is actually on your computer and somehow your memory is independent of the memory of the other processes that are running。

So that's the virtual part of it。And。So we'll talk about this both today。

 today is more of the sort of conceptual ideas， and then the next lecture is more concrete with how this is actually supported in。

Weix and some details of the process here some things。嗯。

And the interesting thing about it is virtual memory is actually loaded with a whole bunch of issues。

 and it's a huge topic on its own and it sort of goes across multiple levels of a system because there's actually hardware support for virtual memory built into the processors。

And so the hardware were designed， but a big part of it is managed by the operating system。

And so it's interesting， usually in a。Class， they're usually they're talking hardware or they're talking software。

 And when they try to talk virtual memory， they kind of have to omit half the story。 in this class。

 we sort of talk about everything， although we don't go into a lot of detail。

 but we get to really talk about this sort of integration of the hardware and software to support virtual memory。

 but virtual memory is also one of these ideas that has。

Had layered on top of it all kinds of different capabilities that it supports。

 so one is it's sort of a cache， you can think of it， uses the memory。

 I'll just call the DRAM because that's the technology you have and a typical computer my phone has two gigabytes of DRAM and some of your CPU。

 your laptops have up to 16 or 32 gigabytes and a big supercomputer might have hundreds of gigabytes or even a terabyte of DRAM。

So you can think of it though， even though that's a lot of memory， several gigabytes or more。

 it's not as much as your virtual address space as you know。

 the addresses in on these systems are 48 bits and two to the 48 is about 256。Terabytes。

So it's a lot of memory that you can potentially reference。Conceptually， of course。

Very few applications could really make it that much use of。

 but you can think of it that they basically virtual memory is a way of creating a cache out of the DRAM that's caching。

The actual data of your program， which might be stored on a disk， for example。

The other is it's a way， as we've seen of creating a management scheme where we can。

Have multiple independent processes， each of which has its own virtual address space and the third is it provides protection so for example。

 in your process that you're running are stored up in the address space above the stack。

 all kinds of kernel data structures that if you tried to access them you'd get a protection violation segmentation fault or something like that because there's for example。

 potentially cryptographic information up there and various things that you shouldn't be able to read and certainly a lot of data structures you shouldn't be able to write。

And so those are managed for you by the operating system kernelel。

 but so they're in your address space， but you can't access them。Okay。

So talk about we'll sort of pick apart virtual memory as serving all these multiple roles and how it supports so。

So the basic idea is pretty simple that in a sort of very。

 very primitive computer and you can hardly even find these uses what's known as physical addressing。

 meaning when there's an address generated by your program。

 it really is exactly an index into the physical memory， the actual DRAM that you're using。

 and this might be true of like a little microcontroller that's controlling your toaster or something or microwave oven。

 but even nowadays like a car has multiple computers on it。

 but most of them are actually fullfledged 64 bit computers and my cell phone has and your cell phones probably too。

 have pretty sophisticated processors， they all use virtual addressing。

But just imagine a very simple processor that when it says this is the address。

 that's really the address。The idea of a virtual address is that there's a translation process there's an indirect relation between what the virtual address is and what the physical address is。

And。As I mentioned it serves a lot of roles， it's a very strong idea。

So let's just do some terminology， we'll assume that in all cases our addresses are just a range of integer values and that we're referencing bytes。

That's not true on every machine， but it's good enough for today。

And so we'll say that there's n different capital n different virtual addresses。And capital M。

 different physical addresses， where typically N is bigger and often much bigger than L。

So I mentioned， for example，2 to the 48th。As value of M N and two to the well。

 32 gigabytes would be5 plus 30，35 bits of address， so two to the 35th， for example， for a 32 bit。

32 gigabyte memory。So the idea then is to。We'll keep track of those numbers and talk about that relation。

So as I mentioned， the first part of it is this idea of using the DRAM as a cache so that at any given time。

 you actually only have some subset of the actual。A range of memory that you might want to access resident within the processor。

So the idea of it then is that theres we， we logically divide our memory up into pages。And。

We'll say that the page is some number of blocks， a bytes， typically a power of two。

 so a typical number would be 4K bytes， 4096 bytes makes up one page's worth of memory。

4096 being2 to the 12 and so at any time， then we'll say that theres some subset of the virtual address range of pages that are resident in the physical memory。

And the other ones might not exist at all， or they might be stored on a disk。

So we'll talk about then there being virtual pages。

 which is how your address space is divided up into these box of 4096 bytes each or whatever the page size is。

 and then there's some range of physical pages， some subset which are some subset of your virtual memory pages。

And so this one shows that， imagine then that as this picture shows some of these pages might not exist at all。

 some might be stored on physical memory， and then these gray ones were saying they're uncached。

 meaning they're actually sitting on your disk。So the sort of realities of the underlying technology make a huge have a huge impact on what kind of how we organize this system and how we implement it。

 So you've already learned a little about caches。啊。The， the cash in the hardware system。

 which is a way of speeding up the access to the D ram。So when we normally talk about caches。

 we're talking about a way of making the actual memory references faster by having a subset of your blocks stored in a special hardware memory called the SRAM or staticRAM that has faster access than the DRAM。

 the larger amount that when people talk about I have a 32 gigabytes of memory。

 they mean how much DRAM。So the sort of range is。Like one or maybe at most two orders of magnitude speed up you get between DRAM and SsRA。

that by contrast， the relative speed of accessing data off of a disk is many thousands of times slower than reading it from memory。

 so especially if you think about a disk。The underlying the sort of traditional mechanical disc。

You have these platters that are spinning， and they typically spin at around 7，200 RPMs。

 which sounds pretty fast。It would be if it were a car engine。

 but if you think about that for any given position on that disk for it to sort of make the rounds。

 let's see， 7200 RPMs is like 120 rounds per second。So it takes close to a millisecond。

For that particular bit on the。Disk to actually get under the head where it could be red。 Also。

 the head is on a movable armor has to position。 So the point is。

Whatever you think about the technology， the mechanical disk has access times on the order that are measured in milliseconds。

 whereas DRA time。Numbers are measured in nanoseconds。

 so many orders of magnitude speed difference between them。

The other property of discs is that it takes a while to get to the first。Bit of a read access。

 but then you can read a whole block as fast as that data sort of rotates underneath the particular head。

 so it's a case that the first bit takes several milliseconds to get。

 but then from there you can be reading at a pretty good qui as far as reading again。

So it means that。All of this means that the design of a virtual memory system。

 even if we think of it as a sort of a cache is way different from the hardware cache that we've looked at earlier。

So in particular， we want pretty large walks。So a typical number， as I mentioned。

 is like four kilobytes as opposed to， say， 64 bytes in a hardware cache。

And that's partly the property of this disk technology that it takes a while to get that first bite。

 but then the successive bites come pretty quickly at a pretty good rate。

 so we want to sort of take advantage of that。Block reading capability。And。呃。

The other is that we're willing to pay a pretty high cost for a fairly sophisticated mapping algorithm if it can reduce thepen or mis rate so we know in caches。

The actual structure is pretty simple， most of you have a set associative cache where it does a mapping where there can be。

Maybe four different places that any block could go on a virtual memory system where actually let it be fully associative。

 meaning any page can go anywhere。And we'll use software to implement the sort of mapping algorithms because in the time we have to。

Do a block transfer， like I said， if it's measured in milliseconds， the operating system can run。

A million or more clock cycles worth of computation and it can spend some of that time figuring out you know fairly carefully where it would be the optimum place to place this page it will also probably go and do some other process in the meantime question。

The。Does it consider what to admit？As well as。What do you mean what to admit？

Does it admit everything？To to the D。Is it possible to like。Yeah。

 kind of asked to move it to the DM before you're going to access it。

 you can't go direct from disk very well。就这样。嗯。But and you know。

 there's a lot of intricacies in the design we will get here。

 but just sort of you have to shift your thinking if you've gotten used to the hardware of hardware caches and cache oil。

You have to kind of shift your thinking that virtual memory is。It hass the same ideas。

 but because of where you are in the technology space。It's a way different engineering design。

 it's like the difference between designing you know a jet versus a car， you just kind of。

 they both move。They both have engines， but they're very different parts of a design space。

And the other fact is that it's always a right back that because the cost of evicting something。Or。

The cost of a writing is very high One thing I should mention。

 I keep talking about magnetic discs and as you know。

 increasingly those are disappearing from even your laptops mostly have solid state drives。

 as well as my phone has doesn't have a spinning disc in it， the old iPods if you remember。The。

These would be antiques for you actually at good old disc drive syndrome them， they're pretty cute。

But。The the really old iPads。really really有。So now it's all based on what's called flash memory and flash memory is not DRAM and it's not SRAM it's a third type of memory that's based on a way of storing a charge in a。

You know sort of。嗯。Essentialsent great capacitor。That can hold charge and it's designed to hold it for a very long time。

So flash memory is very different from disks and that it doesn't have mechanical spinning and a lot of what I said isn't really true。

 but it is the case with flash memory that its access time is slower than DRAM and especially its right times are much longer than its read times。

So anyways。The transition from。Mechanical discs too。To flash memory change some of the parameters。

 but still the same general。System support， hardware support and software support is used for what they call solid state drives as compared to magnetic drives。

So the idea of keeping track of this mapping between virtual pages and physical pages then is handled by what's called a page table。

And a page table is just a set of entries for each of the。

Pages that are potentially referenced by your program， so for every virtual page。

We'll get into this in a little some nuances， but think of it initially as there is a page table entry somewhere that the operating system maintains and has access to。

And what that will have is it will have various little one bit flags。

 the simplest just being the valid versus invalid， and then if it's a valid page， meaning it。

Is represented in physical memory then it will have a。A。The the number of the physical page。So。

So think of it as just a table where each page table entry then has some information about that page。

 including， is it resident in the physical memory and if so， where？And for all the other ones。

 it will have some reference for where on the disc。We'll just assume disc still。Is the actual page？

Store。And for pages that are invalid， we'll just have an null pointer there。So at any given time。

 then what happens if？We reference some word。We'll get。A hint， if that a word is located。

 what that means is that the。Processor will or the memory management unit will look up the。What page？

A virtual memory does this represent。 Look at the corresponding page table。

 And if that page is located in memory， that's called a hip。And if it's not in memory。

 then it's called a page fault。And what that will do is trigger an exception。

 just like we've seen talking over the past week or so。

 the idea of exceptional events that will trigger an exception that meaning it will interrupt the running program and invoke the operating system。

And then what the operating system does is it will assuming the physical memory is fully occupied。

 it will pick some page to be evicted。In this case， this final page here， VP4。

And it will write that back to the disc。And then it will。呃。

Move the correct page in and then it will return back to the original program and reexecute that same instruction as before。

 so we told you with ECF that you might sometimes have an exception where the return is back to a new instruction。

But this is a case where it'll go back to the original instruction， which caused default before。

 but now that will go through because the page that's needed is located another。

So this is sometimes called demand paging， just like what we talked about is demand caching。

 meaning that。When we talked about caches， the idea is that。

The operating system doesn't try and predict in advance what the access pattern is going to be like。

 it just waits and when it's asked to reference a page that doesn't have， it will bring it in。

And it will tuggle along and then if there's so it only reacts and brings in pages in response to the particular demands being made。

And in general， if we want to allocate new space for the memory。Then we don't actually have to。

 like if you， for example， if you're calling。When you're first starting up a program， for example。

 and there's all these the code and the data that's part of your address space。

It doesn't actually when that program first gets loaded。

 it doesn't actually bring that into the physical memory， it just that code。

 the binary file is actually sitting on disk。And it will just create pointers to those locations on disk where your code is stored and the initial values of any data。

And then when the program first executes， what will happen is it'll create a whole series of page faults。

That then bring your program and the initial data into memory and it starts executing so this mechanism once you have it gets to be a very useful thing for hando。

 a lot of the kind low level activities that a program has to do。And so the reason this works is。

 again， just like caches， it works because of locality that you tend to access only relatively small regions of memory at any given time in your program。

And so there's a term they use that was developed。Referred to as the working set principle。

 meaning that。There's sort of some subset of your total memory。

That you're you're kind of actively using at any given time and as long as that。

No larger than the physical memory of your computer， then virtual memory will work。

If you have an application where it's making references all over the place to a huge range of addresses。

Then virtual memory will just fail totally you'll often see this on older machines when there were these disk drives。

 you hear the disk going。Or on really older machines， the disc was this thing like this。

 And that thing would just start to shake because it was trying to。

The pages were basically the memory system was thrash。Grabbbing a page off a disc， bringing it in。

 making a few changes， need another page， evict that one。

 bring it in and the time this the program performance just totally takes some nose dive because you're going from。

Access times measured in nanoseconds to access times measured in millisecond。

And so that's sort of a reality that you can only virtual memory is only works as long as。

The sort of reality of the system。Can be it。Make you of the actual physical memory。So。

That in the idea of caching， let's go on and talk about memory management。

And this is where I said that you have many processes running。

 each of which has its own virtual address space， but somehow they manage to。

Get along and this is this idea that once we have this idea of indirect mapping between virtual addresses and physical。

 then we can have it where different processes have different mappings。

And so and you can even have sharing potentially， as this example shows VP2 in both of these cases represents。

A shared page in the memory and this is one trick， for example。

 if you have a shared library like of code instead of having100 copies of that same code to support 100 processes。

 they can all be reading from that same part of the memory by sharing this page so that's a good thing and you remember with fork。

That Fort conceptually creates a clone of a process。

So that now from thereafter the two are running kind of side by side， but with separate copies， well。

 the mechanism we' go into that a little more， doesn't require actually making an exact copy of the full memory。

 What it does is that it just creates a shared region。

These two processes are basically sharing their pages。

But they also make sure that if one of them goes to and that does it right。

At that point it will basically create the copy so that the two have independent。嗯。Update。

Because you remember they both got copies， but thereafter they were like isolated from each other。

 so the operating system does that by sort of this trick of saying， well。

 as long as you're not doing any rights， you don't have to know that you're sharing。

And as soon as the right occurs， I'm going to just clone that copy and now we'll have two different really true copies。

 so it's a pretty clever trick。And for example， that's an easy way then to get sharing of the code libraries。

And so the idea then， as soon as you have this indirect mapping。

 it's a fairly straightforward idea to have this independent processes that have some shared pages but mostly unshared pages。

And as I mentioned， it also simplifies how linking is done。呃。That linking and loading。

 linking remember is how the all the pieces of code get assembled into executable file and the good news is。

That executable file can just use its range of virtual addresses and not have to worry about。

Are two different processes going to share the same memory region？And loading， as I mentioned。

 once you have this mechanism that can just bring in memory off the disk and make it become part of the memory that's used by process。

Then。嗯。That's sort of the underlying mechanism of how exactec。Fires up a job， the loader。

 it just creates a pointer to the dispositions of the code。

 and then those all are brought into memory by page faults。Question。呃是他的。是就是什。

And in the virtual address space， that's what actually called。Yeah。

 we're going to talk in just a minute about when I talk about address translation。

 we'll go into more what page tables are why and how they're stored and what their format is。今日平さ。No。

 a page table you can think of as just an index for mapping， for this virtual page。

 where is the physical page？Okay， it's just a table and the idea of pages though。

 is that we've partitioned the memory space into these blocks of so many bytes。

 and so we don't have to have for every byte， where is it stored。

 we just have for this range of bytes。Where they store。Good。😊。

So here's actually a little bit more about page tables。

That we can add various little flags to the page table entry that give information about what privileges are allowed for this particular page。

So in this case， we say is it。Does it have。Access for the supervisor， in other words， the kernel。嗯。

DoesIs it able to do reads or writes or can we execute the code here？看。

So imagine that just as part of the page table entry。

 we can store these little flags that indicate what this range of addresses you're allowed to do。

 and we talked earlier you remember with the attack lab that back in the battle days on an Intel processor just stored a read and a write bit for each page and there was no way to separately indicate whether that should be executable or not。

And so since your stack had to be both readable and writeable， it became executable。

 and that's what left people put on the stack code。

By code injection attacks and then have an execute like you did in with your C targets。But the。

Nowadays， part of X8664， actually， is had another flag for each page that says。

 is this executable or not， and so the stack is marked on X？

So there's various flags that you could imagine having， but the point being that。

This whole mechanism gives you a way to control what types of access are permitted to which parts of the memory。

I' also mention， by the way， the way we made your C targets so you could attack them was we actually allocated a separate chunk of memory and then sort of diverted the stack over to this other chunk。

And that chunk was allocated in a way that let it be executable。嗯。Okay。

 so that's the idea and we'll talk more about that， but let's go ahead with a quiz。よせし。わ。嗯。你 know。

I think that was more in conceptual， I don't think it's real， it meant supervisor Colonel Mo。

So does the operating system have access to it？Somebody made that slide up。

That's not really on any real pages because the supervisor in the standard process has access to everything。

The colon。Actually， no， that's not true Intel now they have a reach and a memory you can set up that's private。

It's called an unquited， secure unqua that even the colonel can't ask。Okay。

 so I think we have most people have made progress on this， let's just go through the questions。ですてね。

So most people got the first problem correct， and this is。

If there is a problem on the previous quiz that we didn't have time to get to and this is a。

Sly changed version of that。So this one sort of tests some of these ideas about signals and the idea that proper signal hand if you if there's multiple possible copies of signals coming through it has to have a loop in it The ways we've shown that before was always using SG childil and this is just a variant on it there's a couple signals called a SG user signals that basically have no fixed definition from the operating system perspective and you the program writer can use them to for whatever you want So this is the same idea though that instead of a SIig child hand I had a hand for SIG user and then this。

Whoops， a little formatting problem。This main program would fork off five children。

 each of which would send this signal to the parent， the main program， and the next。

And then this program， then the main program would。Just wait until all five children had。

Been completed， you see that this loop is every time a child is being reaped here， it will。

Increment that counter。And then at the end， it asks， how many times has this handler been called？So。

And the correct answer is you can see is between one and five。

 and you can see that pretty easily has been called at least once because that's the only way that this child gets incremented。

 children counter gets incremented。But it could be as small as once。

 because it might be that the first time this handw gets called， all five children have terminated。

All five children have terminated and can be reaped and so the minimum number is one。

And that's the correct answer。So the main idea of this is to again， remember that。

Children that signals don't queue up， they're just a one bit flag for each signal type。

 and so you have to write a loop like this。The next one is a variant of these nasty file problems that always show up on exams。

It's an amazing thing。And so the。And again， most people got the correct answer and what you basically have to do on these is on with a pencil and paper。

 just work through what's going on。So the idea is that we open up two copies of the same file。

And you remember those two will have independent position indicators as they read through。

 so typically if you just open two copies and read in any order， the two。

 each of them would just see the copies the values A BC D E as they did successive reads。

 but because of this dupe2， it means that first we read from the first file descript and gotten an A。

 but this dupe2 then turned F1 into a copy of FD2， and so now when we're reading from both FD1 and F2。

 it's as if we're reading from the original FD2 so we'd get an A the first time in a B the second。

And then， finally， this。We've only very briefly talked about virtual memory。

Most of this stuff is true。As we said， it's like serves as a cache where you use the。嗯。

The DRAM is a cache for your virtual address space。It's a way to。

Provide protection between processes and within processes so that they can't do anything harmful or restricts your ability to do harmful things。

It allows sharing of code。But Malik， and you're going to really know Malik really well in a few weeks。

 I can promise you that。But。MC is an interesting program because it doesn't require any synchronization。

 it's really just a function that runs within your own process。

And allocates and manages the he memory for your particular program。

 but there's absolutely no synchronization between the various mals that might be executing at a given time because each of them is managing memory within a separate or isolated address space。

So。I think most people got that。嗯。

![](img/f18e487d6080f4d188a6ed046a577bb0_3.png)

So let's move on。

![](img/f18e487d6080f4d188a6ed046a577bb0_5.png)

Okay， so I promised to talk more about address translation。

The idea of you already learned this idea of caching。

 the idea of looking at different bits within an address to figure out and interpreting to look up into tables and to create offsets。

 that it's the exact same idea with virtual memory。That there's a mapping between。

A given virtual address and its physical address counterpart。Or potentially a。

It will say phi or null value if that address is not located in the physical limit。

And then that will cause a page fall。So just in terms of。

Some of the we've already introduced these numbers， NM and P。

 n being the number of bits in a virtual address， M being the number of bits in a physical address。

 and P being the number of bits。The for which the page size is two to the。So as I mentioned。

 4096 is a very typical number。Might be bigger， might be smaller。

 but that would be 12 P little P would be 12 in that case。

And so what we'll do is we'll break out the address。

 and I'll show you this in a minute between the lower。P bits or 12 bits in our example。

 are called the offset within a page and the upper。

 whatever is left up is then called the virtual page number。

Just like we saw with caching that we looked for， what's the offset within a block？

And then what's the tag？Same ideas。And same way we can talk about the physical pages having an offset。

 and then you're picking a particular。Offset is the position of this within the page and the physical page number being the。

Where it's located in physical memory。So in general， then the address translation goes like this。

 that we take a virtual address and we split off the lower P bits of it。And that's called the offset。

 and so that offset becomes。Exactly the same that we use in the physical dress right because we're assuming that we're going to load all these pages on multiple of the page size boundaries and so now we can just use the same lower order bits to index into the physical memory that we do for the virtual memory。

And so really the translation that goes on is then the translating from a virtual page number to a physical page number。

And that's what the page table entry has to hold is it has to hold a copy of the。

Identity of the physical page and it has to at the very least have a one bit flag saying。

 is this a valid pager？Somewhere， there has to be something。Where it can keep track of。

Where is the actual page table and that will be a register that we really haven't talked about。

 but is in other words， there's some hardware register that。

That contains identifies where in memory is the page table because one of the interesting things is。

The page table sit in the same physical memory as the。As the data。

 the rest of your program information。So somehow you have to know how to get to the page table。

So the idea then is。The overall scheme， if you work the whole thing out is first of CPUU。

 the program you're running wants to access Read orwrite some location in memory。

 so it gives a virtual address and then the memory management unit。We'll turn that into a。

An address of。Of。Of a particular entry in the page table。

 so PTEA is the address of the particular page table entry。That would hold this。

 And that's done exactly by。If you look at this， you can think of the virtual address。嗯。

Conceptually is there's one page table entry for each。Virtual page number。

 so if a page table entry is say eight bytes。Then what you'll do is index。

 it's as if you index into an array。Using your virtual page name number as the index into this array to get to the page table number。

 so that's what we met when I said。PTEA is just where how do we locate this particular page table entry。

 it will be somewhere we' assuming it's going to be in physical memory。

And then we'll read through the memory and potentially it's stored in the cache。

 the actual page table entry。And then that page table entry will give us what the physical address of this memory location is。

 and then we'll give that back to the memory system。

And that will give us our actual data that we wanted。 So that's all the steps to a read。

 And you'll notice that in this scenario， it takes two full memory accesses。

 even in the best case here， where everything's a hit。

So first find the page table entry and then actually to locate within that page。

 the data that we're trying to read。So that's kind of scary if you think about。

Performance of a program， if every single memory access actually requires two memory accesses。

 that doesn't sound very promising。And it's even worse if there's a fall。That， and default can be。

With in our example。We're assuming the page table is in memory。

But it might be the actual page you're looking for isn it and so that will raise an exception and then that will require the operating system to bring in that page somehow for memory and access it so when you have a page fault。

That it has to actually typically write a whole page out to disk。呃。Bring a new page in from disk。啊。

Return to the original process， restart that faulting instruction， and then it goes through。

The same scenario for a hit。So。Overall then， this sounds like a fairly costway process。So obviously。

 there's some tricks involved。And this slide just shows that。Typically。The actual cache。

 the hardware cache， is the one that's really between the CPU and the memory system。And the the。

So a lot of these reads and writes will actually occur in the L1 cache or one of the caches。

But conceptually， just one thing to think about is。

Cashching from a program perspective is completely invisible。

 it just happens it's all handled in hardware， whereas virtual memory is this combination of some hardware support and a lot of operating systems。

So this would not really work in real life if every memory access then required， in the best case。

 two memory accesses。So。What the solution is to create yet another。What's called a buffer。

 but it's actually a cache， it's essentially a cache of page table entries。It's usually called a TLB。

 meaning a translation loaide buffer。呃。So it's a translation buffered。

But it's exactly it is in fact a hardware cache of。Of。Of the page table entries。

 so it's a mapping from virtual page numbers to physical page numbers。So in other words。

 what it does is it contains the complete page table entries for some subset of the actual pages you have available。

哎。So now we can add to our mix， then when we want to do look at the TLB。

It's treated just like a cache， like the hardware cache that you've already seen。

 and so we can split the virtual page number。Into an index。

And a tag and use the same ideas you had for set Associative captions。So in other words。

 we'll say our virtual address then in this case will have this lower Pbytes bits will be the virtual page offset。

 but then the virtual page number， some subset of those will be an index that's used to index and select the proper set from a cache。

And then your page table entry， if it's cached in this TLB， will reside somewhere in that set。

 just like we saw for the caching of data。And so what happens now with the TOB is。

That we avoid that extra memory reference that what will happen is we'll issue a virtual address。

that memory unit will use the virtual page number to index the TLV and that will come back with the page table entry that we want。

And then from that page table entry， we can generate a physical address and go off to the main memory for our memory reference。

So you see that assuming a TOP is a hit， then we'll。

We'll be able to avoid that sort of double cost of every memory access。

And so that's pretty important。It doesn't take a huge TOB to basically make this work really well。

 and so any kind of machine that supports virtual memory will have some kind of TOV in。

If there's a TB miss， it will go through that double。Access process。

 but it will store the resulting page table entry in the TOB。And。And get back to the。Processory。

 so that can all be done。Totally in hardware。As long as the actual page is resident。

ATLB myth can be handled totally in hardware without slowing down the program。Very much。Okay。

 so that's sort of the basic idea， now life is less simple than that。Imagine， for example。

We had an X86， I said it's a  four kilobyte page。But it's 48。Bits of address。And so。

If we work out how many page table， how big would the page table be for that program？

You draw as it's an impossible number， two the 39th is 512 gigabytes。Just to the page table。

Because you work out the numbers that basically out of this 48 bits。

12 of them will be the page table， the page offset， and so 36 of them will be for。

The virtual page number and each page takes eight bytes， so that's where this number comes in。

So what happens then and we'll show in the next lecture a more detailed look at the typical X86 processor。

But the idea is to actually use a multilevel page table。呃。And so the idea of this is that。嗯。

The the level two page tables will actually be the standard page table entries。

But the level one page tables will be basically a page table for pages。

And these will actually be stored in the virtual address space and only the level one page table will be in the physical address space。

 So in this two level scheme， we only have to have enough。Page table entries to hold。呃。

This first level page table， and then these all can be stored in virtual memory and brought in by the same idea as paging There was a question back there。

Yes。😊，What's that。😊，Oh， in this calculation， that was taking away the page table size。

 so remember the way one way to think about is of the 48 bits。36 of them will be。嗯。

The count of the number2 to the 36 will be the number of pages。

And each page requires eight bytes to represent。Two to the 48 times 2 the minus 12 is 2 to the 36。

Okay。But this is。It takes a while to get your head around this。 But imagine we're going to use。

Like imagine a case where you just had one。So a 4896 byte region of physical memory that holds the top level page table。

And then that's all references other page tables， but they don't have to be in physical memory。

 they can be brought in and out by the same paging mechanism that we bring to regular pages。

And so that gives you this ability then with a relatively small amount of。Of。Of。

Information to keep track of。All the range of pages in your program。Yes， oh。

 for your page table to be 512 gigabytes， would that mean that your hard drive would have to be like？

Really neat。Well， the other thing is the question is。So okay， what you're basically saying is， okay。

 great， so I get to store all these level two page tables on disk。Right。

 but your observation is correct。 with this number， we're still。嗯。

That's we've blown a lot of disk space， right， and I've really blown it on my phone where I have。

I think 64 gigabytes flash memory。So the main trick we're using is that real programs are never the full address space。

Right。We really don't have。We really can't run a 256 terabyte program on my cell phone。

 right it's just not going to work。So you really， a lot of these even level two tables don't exist if there's a huge region of memory that's unallocated。

 then you don't have to have page tables for that part of memory。Question why。

Vt items stay so big then why。Like that's just not possible。It smaller。pretendYeah， you know。

 it's an interesting thing that there's this whole history of people making their。Processors。

 assuming that， you know， nobody would ever want this much virtual memory。

 And so I'm going to restrict how big my addresses are。

 So the first computer I used for real was had a 12 bit。 So 4096。Words。

 they weren't bites of storage and。So there's this whole history of prostute that only allowed two to the 16th。

And then they became obsolete。 And then recently，2 to the 32nd has sort of just gone over the edge where people routinely want more。

 And so I think what they said is， heck， we're not going to get caught in this again。

 We're going to really jump to something huge。Anticipating that someday in the future。

 people might really want to have that size of program。And as I said。

 actually in the Pittsburgh Supercomputer Center， they have this machine that has over a terabyte of DRAM on it。

It's shared between a whole bunch of processors， but any in principle。

 any one of those processors can access any one of those positions。

 so there really are machines coming along today， they're very expensive。

 but there really are machines that exist today that where you're referencing terabytes worth of data。

 so we're not we're not at。256 terabytes， but we're getting that direction。

I'll tell you remember that even if you think about it right now。

 we're only the hardware is limited to 48 good addresses。说了。The actual。Poiner size is 64 bits。

 and so they're even anticipating some future in which you can have to the 64 bytes of memory addressable。

And that's what I remember。Yes。😊，What would the TLB look like in a scenario？あのペンチてます。嗯。Good question。

I think that the TlB stores。Entries for can store entries at any level and it has。Basically。

 one of the parts of the entry is saying， at what level of the page table is this particular？

That's a good question。So this is an example that this is just for simplicity。

 assuming eight kilobyte pages。And eight bytes per page table entry。

But this is the idea that we have。呃。Basically， these top level page table entries is now indexing into a range of。

 in this case， 1024 different page table entries， each of which is then giving some position for 8192 bytes worth of。

Of virtual memory。And so。嗯。And as I said that if theres some huge gap in the virtual memory system。

 then we don't need any level two page table entries to represent that。

So it's sort of the classic use of a tree。So actually， if you work out the numbers。

 two doesn't really do the trick。Even for the 48 case that it's actually ends up being， I think。

 three。 we'll look at it more。 but this same basic principle applies for any number of。

Levels that we basically were splitting the。Virtual address， page number into K different fields。

 each of which。Then gives you an offset in some type of a page table that either indexes into page table at the next lower level or next higher number here or directly into the page table for the。

Program data you're looking for。And in principle， then all of these。

Except usually the very top most level page table。Can be swapped in and out of memory。

 can be handled just like regular pages。 And one thing you'll notice。

That sort of very standard is that the page size。Is always。The number of page table entries。嗯。

Is always that， in other words， this particular field will be the size of。嗯。

One page is worth of page table entries。So just imagine， 4096 is the case of X86。

And each page shape entry is eight bytes， so there's 512。

Page table entries in a page and so this will be nine bits worth of address we'll go into that next time。

 but that shows this idea of you you view the virtual address as basically a big representation of a path through a tree。

Where the branching factor of the tree is。嗯。Determined by the page itself。So。As a programmer。

 then you're mostly hidden from the realities of virtual memory as an application programmer。That。

 in fact， virtual memory does this nice job of hiding a lot of nastiness from you。

 that you have a view that you have as much。Your own private address space that can't be corrupted by other processes。

But then that puts a lot of weight onto the operating system and to some extent the hardware as well to manage all that virtual memory。

But it does a lot for you， so I went back nowadays only the sort of most primitive smallest processors use physical memory back in like the early days of the either the PC or the Apple Macintosh and certainly Apple Is you know back in the ancient days those didn't have virtual memory and so it was very common you could have a program where one program basically caused a whole system to lock up because it had a wild point of reference that screwed up the data for other programs so it's really been a nice thing。

You should appreciate that fact。Your programs are fairly isolated from each other through virtual memory and so all these are features of why even for fairly you know things like cell phones and most of the processors even in automobile。

 they really want to have virtual addressing just to kind of，Take care of all these features。

Other questions？第。There's such a level of abstraction。What's the point of to trying to write？走。

You're a town town。Tind of optimize cash is so like it's so hidden in all these levels of。 Yeah。

 actually， a really interesting question is why even bother trying to write cache friendly code if there's all these layers of page tables and stuff。

 the the whole scenario and all this paging and all these end levels of pages is。等等。

The hit rates are measured in like 99。99%。So all the extra cost of doing it is almost invisible for reasonable programs。

If you actually， you know those caches。You can really see it when you write programs that if you write cash friendly code。

 it really runs 10 times faster than bad cash code。No。

 for the transpo that you were doing was pretty much absurd， right that you were。

 especially the 64 by 64 case where you're kind of picking up this and putting it there and this and there。

So that sort of went over the top， but that basic idea in cache is and what we call cash and we code is a real thing。

because。Especially for programs that really are pounding on memory and they're doing something like reading through arrays and things。

 all those pages are just sitting there and all the TOB entries are hitting so all of this is working perfectly and it really is then bound by the time to stride through the arrays。

But that's a really important consideration that all this only works because the frequency at which these bad events happen is so small that。

It doesn't significantly harm the performance you approve。But that's a very important design point。

Yes。見つけおけ。The table is probably going to end up sitting in L1。While L1 is still nuts。

 the TLB basically ws you。啊。We'll see that the TL big happens。嗯。Actually。

 there's this clever trip that makes it possible to do the TlV access。And。

Start reading the cache at the same time。Because。I can。Usually if you look at the bits。

 the thing that selects the set you're accessing in the cache。

All those bits are within the page offset。And so that parts the same。

 whether it's physical or virtual。So it actually does the set access of the cache。At the same time。

 it's doing the TLB。And then only when the TOV then does its translation。

 does that tell what the tag within the？So the hardware can make it fast and also L1 SRAM。

Of L1 cache is still a little bit slower than the TLB is a very small memory。

 and so it runs really fast。Also， does X boxes get its own table。Yeah。

 so the page tables are independent through every process。The TlV is shared。

 so when you do a contact switch。You might have to flush out CoLB entries for one process and put them in for them。

And the caches usually are caches are almost always referenced by physical memory。

 so it means I can run a program， jump over doing this program and come back and as long as those pages haven't moved。

And those cash entries are still valid， I can still get a good cash before you。Good question， yes。

Pusels have this own。Yes， so the idea of registers。Let's answer this in two ways。

 The classic view of registers is that there's only one set。 And if I do a contact switch。

 what I have to do is copy that whole set of registers。Onto the staff。And then pull。

The saved registers for the other processor from the stack， into the in other words memory。

 from memory into the registers， and then I can do it。That's the classic few。 Now。

 most processes nowadays have what they call hyperthtic。And hyperthing。

Is actually where there's multiple copies of the registers so that the processor can jump between the。

The two processes almost instantaneous。And it will actually do that。

You saw in the code optimization that you have these pipeline functional units going on。

 it'll actually jump on an instruction by instruction basis between the hyperthreaded processes to let it fill up the pipeline with basically operations from different programs。

 but that's like we're often outer space here， so if what I said didn't make sense you just flush it out your memory but if you ever hear the term hyperthreading。

Other questions， iss a good question。Okay， very good， we'll see you next time。



![](img/f18e487d6080f4d188a6ed046a577bb0_7.png)