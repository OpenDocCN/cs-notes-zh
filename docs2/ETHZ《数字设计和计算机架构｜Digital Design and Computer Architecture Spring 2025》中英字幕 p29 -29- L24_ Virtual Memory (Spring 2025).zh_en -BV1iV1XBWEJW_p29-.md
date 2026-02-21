# ETHZ《数字设计和计算机架构｜Digital Design and Computer Architecture Spring 2025》中英字幕 p29 -29- L24_ Virtual Memory (Spring 2025).zh_en -BV1iV1XBWEJW_p29-

![](img/3f2e9102bfa7b0f61ff39fe2bc1852f1_0.png)

Okay。因为我怎么觉得。视频。分个边。飞如。哎，这里要做。つ。没结算。是这个。But it also depends on your schedule。 You might want to。

So we have a few and then I have from three。5 and44。

The basic owner wants you to finish so what if I want to five minutes after four。

 is this possible or impossibleable but what's the flexibility you can them that。This。再见。😊，他是你这是这问题。

一个業会。这一的关系。好。ですぐ。这个。さ次で。差。你钱。你个这个是。那个。Okay。🎼So hello everyone before we can start with the lecture of today。

 I like to make an announcement， I think you have already received our survey to review the course digital design computer architecture this has been started I guess yesterday if I'm not mistaken basically we'd like to encourage you all to attend to this survey and provide constructive feedback Professor Muhu and I we are very very much open to receive all your feedback and basically improve the course for future editions of so please make sure you attend it I think the survey will be stay open until June 2 but would be good if you can do it as soon as possible such that you don't forget it。

So with that I will stop and then Constantius will take over， thank you。Hi， everyone。

Thanks for joining today， so I'm going to deliver the lecture on my favorite topic。

 which is virtual memory。Okay， so I am a fifth year PhD student working in Safari research group。

I did my bachelor's and master's at the National Technical University of Athens， I come from Greece。

 and my research interests lie in hardware and OS codesign with a focus on virtual memory and memory management。

 also hardware software codes with a focus on programability in intelligent interfaces。

 and I'm currently also working on security primitives for emerging and futuristic systems。

I would encourage you to read this blueprint from written from Honor。

 on intelligent architectures for intelligent computing systems。

 where Hoor tries to give an understanding of how we should design fundamentally better architectures。

At whose core they should be data centric， data driven and dataware， and as I will explain today。

 being data centric data driven and dataware requires a very strong virtual memory subsystem so that we can support these functionalities。

I would recommend these readings for you that you can understand and dive deeper into the topic。

 these are from the book， and this is also from two three publications from our group。

 which can do a very you can read a very concise background on the topic。

So let's dive into virtual memory so as you have seen right now in the course we have a memory and the programmer。

 so how things work is the following when you write your Python code。

 let's say you want to load from me some stuff， store to meism stuff。

 and this is your interface that right now you're using to program。😊。

Ideally we would like a zero axis time latency which means we go to the memory for free。

 we return for the memory for free， we take our data for free Second we want a memory with infinite capacity imagine what would happen if right now you had a1 terabyte memory in your MacBook pros and you could run let's say the Lama or the open AI stuff in your locally on your device instead of waiting for the network and the congestion of the network third zero cost we don't want to pay anything for our for our main memory and fourth infinite bandwidth which with infinite bandwidth we want to basically support multiple access in parallel to the main memory。

😊，So what is the abstractions we're going to talk today about， so the programmer。

 when you write the program， you do not see the physical memory， you only see virtual memory。

This way you can assume that the memory is infinite when you write in your Python code that you want to allocate a dictionary。

 you want to allocate a NI array， then that doesn't mean that you see the actual physical address that you access in the system。

 you don't actually， you see a virtual address， which is an abstraction。

Why does this happen because in reality， the physical memory might be much smaller than what you assume when you write your program。

 you don't want to care about what is the physical memory in your system。So， the system。

Tries to hide this information from you using both software and hardware。

 and comparatively it tries to map virtual memory addresses to physical memory。

So you as a programmer do not need to do anything， the system automatically manages the physical memory transparently from the programmer。

 so the programmer does not need to know the size of the physical memory or manage it so youre going have a small physical memory which appears to be very huge from the programmer's point of you and you make the life easier imagine what would happen if you would need to rewrite your program for every different physical device that is lies in your system then you would not basically you would lose the portability argument。

 you would not port your program from your laptop to your desktop to your cloud environment。However。

Adding this support in the systems makes the system a lot more complex。

 both in terms of the software stack stack， stack and as well as the low level stack。

 the hardware stack。😊，This is a classic example of the programmer microarchitecture tradeoff。

 so we have flowed in this concept of virtual memory。

 the burden down to the system to the system organizer and the architect and we take remove the burden from the programmer so that we increase productivity on the programmer' side。

😊，The question is why do we need virtual memory and there are many benefits of automatically managing memory so programmer does not need to deal with physical addresses first it process when you write a process it has its own physical address virtual address space and it has an independent mapping from virtual to physical addresses so when you write your program。

Your NI array， let's say in Python or your CR which you allocate using a Ma。

 then this is represented using virtual addresses， which is an abstraction so somehow its process needs to keep track of the virtual addresses that correspond to this array and how they map to the actual physical device where you store your data and this enables first code and data to be located anywhere in the physical memory。

And given this， if we can relocate and flexiblylocate our data。

 imagine if you would write your program and you would only place the data in a specific physical location。

 then you would not be able to relocate the data from one to another。Second。

 we can isolate and separate code and data of different process in physical memory。

 imagine if you want to search your computer with a friend of yours and you both want to write your programs。

 then you need a consensus about who is going to use the physical resources。

 however with virtual memory you don't need this consensus the system does it for you。Third。

Code and data sharing between multiple processes again， you goop coding with your friend。

 you write to programs， and then you can you do not need to basically agree upon the physical locations you're going to share the system can do it transparently for you using virtual addresses and we can share basically code and data this way。

This is an example of a system， a very old system。 This was used in most st supercomputers in nearlyly P computers and many other meic systems where we would have a CPU and on the。

Back end we have a memory physical memory device and the CPU loads and uses loads and store instructions that generate physical memory addresses。

 we don't have the concept of visual memory in this scenario and let's see。😊。

What are the downsides of this approach？So first， physical memory is of limited size。

So what happens if my program needs more memory than the size of the physical memory， so for example。

 should the programmer be concerned about the size of the code and the data。

 whether it fits in the memory， where should I place in the memory？Should I， for example。

 care about should the programmer care about whether the data is fed from the disk。

 whether it's fed from the memory， should the programmer care about fetching it from the disk to the memory or back and forth？

😡，Next， multiple programs may need the physical memory。

So if multiple programs need the physical memory and they are concurrently running in the system right so should the programmer make sure that all the processes can fit in the physical memory。

 what if I write a code that simply allocates the whole memory does not leave space for anyone else。

😊，So should also the programmer ensure that two processes do not and intentionally or incorrectly use the same physical portion。

 if you would decide on where to place your data in the physical memory。

 you would again need a consensus with all the other programmers that write programs in that computer about where to place your data so that you don't overwrite each other or that you don't read the data of each other。

 which creates both security problems， synchronization problems。Also we。

 as you have seen in the course we're using instruction set architectures which have an address space which is much larger than the physical memory size。

 so for example we use a 64 bit address space with a bio thederability that can cover up to 16 extraabytes of data。

😊，So what if you do not have enough physical memory to cover up the 64 bit address space？

So the difficulties of the direct physical addressing are the following so we have a programmer with needs to manage the physical memory space again we repeat it's inconvenient and difficult so we have it's more difficult even when we have multiple parts in the system because they need to coordinate with each other。

😊，It's also very hard to support code and data relocation why。

 because addresses are directly specified in the program。

 we cannot change the location of these addresses once you write your program。

It's also difficult to support multiple processes running concurrently， why。

 because we cannot guarantee protection and isolation between the multiple processes。

 we cannot guarantee that two， three， four entities that write programs in one single computer have the consensus that have have agreed that they're going to use different parts of the physical memory for their programs。

This would create problems basically with sharing physical memory。

 and it's also very hard to share data and code because again。

 we need some synchronization between the entities that use the same computer need to agree on which data and which code they're going to share。

So the question right is， okay， we agree that using the physical addresses directly is a problem。

 does anyone have any question on that？No， okay。 So let's see right now how to solve this problem。

 which is how does visual memory work。So the idea here is that we give its program。

 they illusion you of a very large outer space， even though we have a very small physical memory。

This way， the programmer does not need to worry about managing the physical memory。In this scenario。

 the programmer assumes that they have an infinite amount of physical memory。😊。

And underneath the hardware and the system， the operating system。

 coly automatically manage the physical memory space to provide the illusion that it's maintained for its independent process。

😊，But。We need some sort of indirection and why do we need that because when the program generates an address in this scenario。

 when you write your programs and you generate an address。

 you basically express your data structures with using virtual addresses。

But we cannot use right now the virtual address to access the actual physical device because we do not know the physical location of the data based on this virtual address。

This visual address is called linearar address in the XA6 systems， the other systems。😊。

And we a mechanism， which we call other translation that maps the virtual addresses that you use in your programs to physical addresses that correspond to the addresses that lie inside the physical biting storage。

 This is called the real address in X86。 So we have another translation mechanism responsible for dealing with a problem of virtual to physical mappings。

😊，Together in hardware and software， the programmer does not need care about how this is happening。

 how this translation is happening。Let's see an example。

 so we have spun two applications in the system and these two applications have a different virtual other space。

 applicationplication one uses virtual other space one an application to use virtual other space2。😊。

And we have the physical address space and the physical outdoor space imagine it as the physical memory。

 so the first thing the system does is that it splits up the virtual address space and the physical address space into discrete chunks which are called pages So when we want to do a mapping we will do it between pages we will not do it with arbitrarily size segments。

😊，In this example， Up one uses two pages。And up2 also uses two pages。In this example， again。

 up one maps these two pages on the second and the third physical location in the memory。

 wide application two maps it in the fourth and the sixth。😊。

This is what we call a virtual to physical address mapping。

 the process of establishing a mapping from the virtual address space of an application down to the physical memory。

 but to be able to discover this virtual to physical address mapping we need some sort of indirection。

 we cannot directly access the physical memory from the virtual address。

 we need someone to translate for us。😊，So these are the key four issues when it comes to this detection and mapping first。

 when do we map visual addresses to a physical address？Second， what is the mapping grarangularity。

 what is the spa size， like do we split our virtual other space in four kilobytes，8 kilobytes。

 how do we make this decision？😊，Third， where and how do we store the virtual to physical mappings again。

 we need some sort of information about where the virtual address。Maps in the physical other space。

 so how are we going to find out where is this mapping and how do we find out where to find this mapping？

And fourth。What if we fill up the memory， even though the virtual ladder space is much larger。

 we mapped our data inside the whole physical memory and we somehow need to deal with this problem。

So in modern systems， when do we want to map a virtual address with a physical address。

 in most modern systems we do this when it's first referenced by the program。

 so once the programmer goes and performs and write a right operation that I want to write to this virtual address。

 the system underneath tries to prepare the physical location for us so that we can store our data。

What is the mapping in granularity in most modern systems we're using multiple granularities in your MacBooks。

 for example， you're using a  16 kilobyte pages in Botu and Linux。

 they're using  four kilobyte pages， they're also using2 megabyte pages。😊。

Where and how do we store the virtual physical mappings， we have OS system structures。

I will discuss this later they're called the page table。

 which stores the virtual to physical mapping， we can think of it as a dictionary basically where you go with your virtual address and you get back the physical address。

😊，And what do we do when we have a full memory， we need to evict some sort of pages right。

 and we need to evict some sort of pages to bring the ones that we want to use at that point in time。

So let's go to the concept of virtual pages and physical frames。

 so the virtual address space is divide into pages and the physical address space is divided into frames。

 I never understand why there is a distinction I' been doing this too but that's how you can find in the literature I call them pages all of them。

😊，The virtual page can be mapped with physical frame if the page is inside the memory or a location in the disc。

😊，So if we access a virtual page that does not reside inside the memory， but is on a disk。

 then we need to bring the physical frame from the disk inside the physical memory and adjust the mapping and this is called demand paging。

 this is called demand paging because we're fetching the data inside the physical memory。

 only when they're accessed， we do not when you create an RA in C with 1 million elements。

 your system underneath does not reserve1 million elements for you。

 only when you do the rights when you start writing and initializing this data structure。

 you start allocating physical memory in your system。

And where do we find these mappings in a data structure called the page table。

 which is actually you can think of it as a dictionary。

 the page table is imagined as a dictionary that stores the mapping between virtual pages to physical frames。

😊，In other words， other words， what you have seen is the course。

 the concept of casting and physical memory， you can think of it as a cast of pages which are stored in the disk。

In fact， basically it's a fully associative cast in modern systems because we can map a virtual page。

😊，Anywhere in any free physical page in the main memorial。

 and there are similar casting issues which we have covered there real like。

How do we place a page in the cars， What page can we remove？To make room in the cast。

 what is the going large of the amount that's been like a cast block。

 how large should be the cast block and what's the right policy do we write directly to the memory do we write directly to the disk。

 how do we handle these and you can find this analogy in this table。Again。

 this is the virtual to physical mapping so on the left you have some visual addresses right and as you can see some of these address virtual addresses map to the physical memory and physical addresses。

😊，However， in this scenario， the some virtual addresses do not just map to the physical memory because for example it was full and they map also to the hard drive but we need to guarantee the system that most of the accesses hit in the physical memory。

😊，Let's take an example of a virtual memory size of two to the power of 31ytes， which is2 gigabytes。

 a physical memory size which is much， much much smaller than the virtual memory size which is to the part of 27 bytes and a page size which is 4 kilobytes which means that for inside each page we store to the power of 12 bytes so what is the organization here so how many bits do we need for the virtual address 31 we need 31 because it's a log of two to the power of 31。

😊，What's the physical address size we only have two to the part of 27 bytes so we do not need all the 31 bytes for the physical address we only need 27 bits and what is the page offset 12 bits and we need the page offset to find the location of the data inside the page basically if we have a 4 kilobyte page using 12 bits we can express where our data is inside these 4 kilobytes。

So how many virtual pages do we have we have two to the power of 19 pages why because we divide the virtual address size。

 the number of virtual pages， the size of the virtual address space divided by the number the size of the physical page which two to the part of 12 which means that we need to do the power of 19 page virtual pages in the system in the case of the physical address space we have two to the power of 27 divided by due to the power of 12 as you can see here and we have two to the power of 15 pages in the system so we need to map the 19 bits for the pages in the virtual address space to 15 bits in the physical address space so you can see here that our job is the following。

😊，So we have 19 bits in the virtual address space and these 19 bits represent the virtual page number and we need to always translate these 19 bits to some bits in the physical address space to 15 bits in the physical address space as you can see the page offset remains the same why because the page offset only tells us where is our data inside the page we do not need translate the page offset we do not translate that the graangular with the page offset is that clear to everyone。

😊，Okay， nice。And the question is， how do we do this translation？

So we use a data structure called the page table and the page table has an entry for its virtual page and its page table entry has a validity bit and the validity bit tells us oh。

 this virtual page that you're trying to translate is located in the physical memory it's not。😊。

In the disk。 So using the validity bit， we know that indeed our data is inside the physical memory。

We also get the physical page number。So when we probe the page table and we look it up。

 we need to retrieve back where the virtual phase is located in the physical memory。

And then typically the page table has some additional bits per entry to know the permissions we have for the page。

 some replacement policies， which one to evict or not。😊，This is an example of the page table。

 you can see that they are in this scenario four entries， which are valid。😊。

And let's see how we would translate in this scenario so we have the address 0 x0002。

 so the first thing we do is we take this VPN， this is the virtual page number which we need to translate and we look up the page table at the corresponding entry in this scenario its entry number two so we start from the beginning of the page table and we we can access the third element which is0 x FFFF。

So in this example， when the programmer wanted you translate， it would take the 0 x x xx2。

Then you would look up the page table and you would be you would get back the 0 x7 FFF。

 which means that after the page table entry is done。

 then I can form my physical address using the page offset which remains the same and the corresponding physical address。

😊，However， how do I know where my page table starts so how do I find the physical address basically of this element there is a concept in almost all the page tables and all the data structures in the system which is called the base right so in this example the page tables allocate to a contiguous structure in the physical memory and we always know when we want to translate the beginning location of the page table that's how we can form the corresponding location here which is the third entry and find out the pointer which we need to load which would contain this the0 x7 FF。

😊，Next example， we have the address，0 x 5 F 20。 And in this example。是。How do we do this？

We first form and find the page offset and the virtual page number， how do we do this。

 we shift by 12 because this are the number of bits for the page offset and then we take the rest of the bits。

 which is the 0，0，05。Which entry do we need to look up in this scenario because we have the fifth virtual page number。

 we need to take a look at the6 entry，0，1，2，3，4，5。😊。

The sixth entry of the page table and in this scenario again。

 we find that the physical page that the fifth visual page corresponds to。

 it's the first physical page in the physical memory。😊，And next example， a more complicated one。

We form again the virtual page number which is seven and the page offset which the three is0 and in this example we need to access which entry the eighth entry in the page table so we access the eighth entry and what do we find out we found out a zero does anyone know what is a zero in this scenario based on what we discussed so we don't find the validity bit our data is not in the main memory then where is it。

😊，Yeah。there he was doing the physical memory to been delivered。That's one。That's correct。

 but that's not what I want to hear as an answer。 It might be the virtual memory and not being initialized。

But usually what happens if you want to load the file， which has not been brought？

In the physical memory， where would the data be？Anyone。So the data would be at disk。So。

 the data would been the disk。Because the data is not in a physical memory。

 We already have a file with the data， and we figured out in this context from the page table that our virtual address has not been mapped anywhere in the physical memory。

 So we will fetch it first from the disk。And the question is the following。

 Let's say we have a 64 B virtual address space and a 40 B physical address space。

 And the question is， how large should the page table be。So if you have a 40 bit。

Physical other space。How large should the page table be， Does anyone have any idea？Like， how can you。

 you need to somehow support？Translation for each one of the virtual addresses that can be stored in a 64 bit virtual address space。

Then how large would the page table be in this scenario if we store it as a contiguous array？

Let's say that the page table stores4 kilobyte pages。Does anyone have any idea？

So you would need to address every single you need to look up every single virtual page number。

And in this example， if you have two to the power of 52 entries for for the virtual address。

 why do you have put to the power of 52 because you have 64 bit for the visual address。

 minus the 12 bits for the offset which do not need to be translated。

 so you would need to translate to the power of 52 entries and each pointer。

 its physical pointer for the physical frame would be four bytes so you would need in this context put to the power of 54 bytes for the page table。

And this is just for one process， if another process using another virtual other space。

With need a paid table， you would need to store another to the power of 54 bytes。

Do you think this is feasible， Like imagine if we would need to store in the physical memory2 to the power of 54 bytes for its process。

 I guess no system would be able to run。Today。So the challenge number one is that the page table is very large。

 or at least part of it needs to be allocated in the physical memory and the solution that people have come up to solve this problem is a multilevel hierarchical page table。

😊，So let's see how multilevel page tables work， so we need to organize a page table in a hierarchical manner such that only some parts of the page table need to be allocated in the physical memory so that we don't need to store the entire two to the part of 54。

 let's say， page table in the physical memory。😊，So how does that work we have in this example two page tables。

 we have the first level page table as you can see here and the second level page table so the first level page table which is much much smaller。

 we start in the physical memory always we allocate it and what do we do then we split our virtual address into two distinct numbers。

 the page table number and the page table offset。😊，To access the first level of the page table。

 we're using only nine bits which correspond to the page table number。

 These nine bits mean that we can access 512 different entries into the first level page table。

So the key idea here is the following， if an entry at the first level of the page table is not allocated。

 then we do not need to store the corresponding entry in the second level of page table。

You can see this example here， So we have in the first level of the page table。

 we have two valid entries， the second one and the last one。 So what does that mean essentially。

We are storing only two entries in the first level of the page table for all the intermediate zeros。

 we do not need to store a pointer to the next level of the page table because this has not been touched yet。

 It has not been allocated。 So what do we gain from this that we would store the second level of the page table only for the entries。

 which are valid in the first page table。 So if our process is using just this entry to map the data to this entry to map the data to the physical address space。

 then we would store only one frame in the from the second level inside the physical memory。

 we would not need to store all the entries that correspond to the first level of the page table。

Is that clear to everyone？Yes。😊，Do want to ask something？或者。

And that's how modern systems employ the page table。

 they basically have multiple levels so that each level can basically act like a tree and as you can see here。

😊，They split the virtual address into four chunks of9 beats。

And you have a CR3 registerer which is used in the XAD 664 systems in your Intel processors and the CR3 register points。

To the beginning of the first frame， so once it points to the beginning of the first frame。

 you're using the first nine bits to find the offset inside the first frame。

If we have a valid bit in the first frame， then only we store the second frame。

 which basically we use the second nine bits to find the offset inside the second frame。

From the second frame， we find a pointer to the third frame， only if they are allocate。

And we do this itatively four times until we find the last frame。

 which is called the leaf of the page table， you can think of it as a three as a three data structure if you have seen linked lists。

 for example。😊，And after we reach the final level of the page table。

 that's where we retrieve the physical page number in this scenario again。

 for all the entries inside all of these frames which are not valid and are not initialized yet。

 we do not need to store pointers to the next levels so there are no next levels basically so we would store only the frames that correspond to the virtual addressess that we're using。

 if we do not use a large portion of the virtual other space。

 then the page table becomes smaller and smaller and smaller。😊。

So as you can see how many accesses we would need， how many memory access do we need to access the page table in these systems。

 we need four memory accesses， one for its level， given that the physical virtual to physical mapping exists。

 so in this example you show that we need four sequential memory accesses to retrieve the physical address。

 the physical address during the page stable work in ED664 systems。

So we tried to solve this challenge that the page table is large and we figured out that the multileve hierarchical page tables are a good solution towards that。

😊，Second and very important。When we perform an instruction fetch in the system or a loader store。

 then we need two memory accesses。Write down your systems， when you do when you access。

 let's say the location of an array， let's say a of I。

The system does not only perform one memory axis。 It performs two memory axis or more。

 Does anyone know why it performs more than one。Like how why would you perform a second memory axis。

 even though the only thing you want to act is A of I？We're accessing a virtual memory address right。

You look up into the patient where the wheel that exactlyactly so your system somehow needs to perform a second memory access to figure out the contents of the page table to figure out where it would go to the physical memory insert search for your data so you want one others for the others one memory access for the other translation or more in the modern systems and you have one access to the data within the physical address once you retrieve the physical address from the page table。

 then you can access your caches and your physical memory。So we want two memory axises。

 which as you can understand， if for every single virtual memory axis I'm doing。

 and you do a second one， I'm going to basically degrade performance by almost 100%。😊，Yeah。

And if I have the multilel page tables， which have， let's say some sort of pointer changing。

 I jump from level to level to figure out the final level。

 then I would take to perform more than one memory axis is to find them。

Unless we're more clever and we try to speed up the translation process somehow。

And we everything boils down to how we perform the other translation in modern systems。

So to support visual memory and the other translation process。

 we require support from both the hardware and the operating system。

 so the page table is installed inside the memory and it is the job of the software of the operating system to populate the page table and decide what to replace in the physical memory。

We talked about the page table register before， the page table register。

 given that the page table is a per process structure。😡。

And needs to change every time we run a different process in the system。

 we cannot use the same base and pointer to the page table。S。

 we need to handle pages and ensure the correct mapping， I'm going to talk about pages in a bit。😊。

So the next question is， how does the CPU when it's running。

 discover this virtual to physical mapping， how is it accessing the page table？😊。

So we obtain the physical address from a virtual address using the other translation。

 and we do this at the granularity of the page size。😊，The paid size。

spec by the instruction set architecture basically it's a contract hardware and software have agreed how they're going to split both the physical pages。

 the physical address space and the virtual address spaces in  four kilobyte times。😊，Okay。

So the page table contains an entry for its virtual page。 This is called the。

 we will call it the page stable entry for simplicity and in a。😊，In a PTA。

 we basically started translation and some other memmal protection bits。

So how does that translation happen， we have a core right now you're using let's say your arm course in your CPUUs in your laptops and the core tries to access a memial location using the virtual address。

 you're using A of I， let's say and it goes to the me hierarchy and first and the first thing it needs to do is it needs to load the page table and find the paid stable entry。

 the page stable entry is let's say the leaf the final entry from the page table that contains the translation。

So for every virtual address it's doing， if for every virtual address is' accessing。

 it would need to go to the memial hierarchy to find the translation and the question is how can we speed up this process that degrades performance a lot？

First， let's see some definitions， you can think of the page table as a tag store for the physical memory。

So it's a mapping between the virtual physical memory。

 and we define PT as a tag store entry for a virtual page in memory。😊。

So we need a validity bit we discussed this before we need some tag bits， the physical frame number。

 and we need support， we need bits for support for replacement and a dirty bit to support right backcaching。

😊，I will discuss this later。So the big question also。

 before we jump into the translation is like who would establish a mapping。

 who would update the page table， who would give us the location of our data in the free physical memory。

Again， we have an application here with a virtual address space。And this is the physical memorial。

 you can think of it as a arm in your systems， right？😊。

So when the data is being touched from the visual other space。

 which means that the programmer needs to perform a right to this piece of data。

We had to find out and somehow establish the location that this data would be stored in the physical memoryial。

So we need to map essentially the visual addresses to the physical addresses and this process of mapping them is called the fault in the systems。

 so visual addresses are not mapped to the physical memory in this example。

 so someone needs to take over which is the operating system that would handle the memorial location and place the addresses from the visual address space to the physical memory。

😊，How does that happen？One of this happens in your system， also in your system nowadays。

 So the application gets stall。And the operating system takes over and says， okay。

 I have this virtual address and I need to place the data that correspond to this virtual address somewhere in the physical memory。

 so my job is to first find free space in the physical memory of where to put my data。

 this is the simplest scenario that your colleague also said before， which is called the minor fault。

😊，The minor faults happen usually when I allocate memory for a very big array。

It's not backed up by anyphi I simply used as a my program just allocates a large array as an intermediate data structure data has not been mapped yet to the physical has not been allocated yet in the physical memory and somehow we need to handle the only thing we need to handle is fighting the free space in the physical memory that's the only thing the first thing to do This is a good scenario because this is very fast。

😊，What's the bad scenario the bad scenario is that our data is backed by a file so we want to write a program that reads a file when we do this and the data has not been brought to the memory we need to first fetch it from the disk and once we fetch it from the disk we also need to search for free space in the physical memory so that we can place the data that we fetch from the disk inside the physical memory and establish them up in this the major fault and as you can see in your systems when you have lots of major faults。

 it will be much， much much more expensive。If you have enabled， for example， swapwab space。

 swap space is something that many of your laptop support right now。

 if you enable the swapwab space in your laptops， which can extend basically the physical memory by using part of the disk。

Then your system will become much slower if it's using part of the swab space and fetch data from the swab space in the physical memory。

Okay， we handle the fault， the operating system handle the fault and then what does it need to do。

 it needs to store and update or update the virtual to physical address mapping in the page table。

 which is stored in a physical memory so once we find a very physical location for our data。

 we go to the page table update the corresponding entry and we know where our data lies right now so we can establish we establish the virtual to physical mapping。

😊，So if a page is not in the physical memory， but it's in the disk。

 the pages stable entry will indicate that the virtual page is not in the memory。

 as we discussed before the validity， the debate would be 0。😊。

And the access to these page would trigger the paid for exception。

The exception you can think of it as an interrupt， so the operating system would figure out that the CPU raise an exception and it would raise a special program that tries to move data from the disk into the memory。

😊，Other processes while this happening can continue executing。

 but the process that needs to break the data from the disk in the memory needs to stop executing。

And theOS also can make decisions while this is happening about where to place the data。

 So before the fault in this scenario。We had these two pages which were stored in the disk。

And after the fault was resolved because we wanted to access this page in our example。

 the operating system brought this page inside the memory and it established， as you can see。

 we had two mappings in the physical memory before and after the page fault is done。

 we have three mappings inside the free physical memory。How does this happen？

So the moment you receive a major paid fault， the processor signals a component which we call the IO controller that starts reading some block from the disk because our data is backed is file backed。

 which means it stored inside the disk， and we need to start fetching the corresponding block that we requested from the disk。

So。When the Io controller figures out that this is the case。

 it tries to perform a disk to memory read， and a disk to memory read is happening in modern systems using a direct memory axis。

So imagine this as some sort of module， the DMA engine which exists in the systems。

That simply has one objective。Transparently from what the core is doing the core might be executing a program transparently you tell the DMA engine that okay start fetching the data from the disk and place it somewhere in the physical memory the core is not involved at all and the processor is not at all is is not involved at all in this process Does anyone have any idea why we would do it this way。

 why we would not simply fetch the data from the disk inside the processor inside the caches and then the processor would then store our data in the physical memory so why would do we need the DMA and don't we just let the processor do the job of fetching from the disk and then writing back to memory。

Does anyone any idea。那个是要。山。Yes。Yes， that's one。 Now that's true， yes。😊。

And maybe because especially this is a long process。必须。Doing on a separate bus and can push。

That's one。 Yes。 So what would happen if I would start fetching。

 that's true both of the answers are correct。 What would happen if I start fetching data from the disk inside the caches。

Like what would I cause as a problem？Like how expensive is that？

So if I would need to fetch data from the disk inside the cast inside the processor。

 the first problem I would cause is I would need to pay a very high price in connectivity and like I would need to transfer the data over a bus。

Which is very expensive from the SSD or the Sa drive inside the processor second。

For every transfer I would do， I would need to have data from my classes。

Fets the corresponding SSD data， the disk data， and then start writing them back to the main memory。

 which is much slower than simply copying them from the disk directly inside the physical memory。😊。

So that's why we're using a DMA engine in modern systems。

Once the MA engine finishes its job and copies the data from the disk to the memory。

Then the controller signals completion and the OS can resume the suspended process。

And there are many page replacement algorithms。😊，Which we can use to find out which spades are you going to replace inside the physical memory。

Modern systemss， you can think of they using some approximation of the least region they used。Policy。

And they're also using the clock algorithm。 I will talk about the clock after the break。

So let's have a 15 minute break。And we can talk about how the OS replaces pages。Yeah。So want to， no。

 I don't pop yes yes。对呀。好，谢谢。你关。い。你。要。Okay。啊。2。Okay。我呢已经。对。我。啊。嗯。哦。啊。对对。对。干。没啥法。对。Yeah。Yeah。

This is where I made a copy of my。嗯，好。不行电是嗯。And this didn't get it right because。

What is with the problem if we have the virtual memory。

 which is bigger than the physical memory and isn't it possible that you have like two virtual memories and they're met with the same physical memory or yeah。

 that's that's possible Yeah So the basic problems the point like right if if I have a very big。

For somehow， I need to。There's some data when you write your program right that need to be into the this some data which will be in the main number so basically I need to find a way that when you write your program I will aspire and do this for you so you don't need to care about where you place your data in the physical manner this is the more important would's say。

How functional the fact that I have stacked this from the program and program there's what need to know about。

So I automatically manage basically how data will be placed in physical memory or in the disk without you caring about it。

 Okay， this is the most fundamental part rather than the infinite memory part。

 The infinite memory you can remove it it sounds very important。

 This is how people perceive this in the older。 But the most important is that I automatically manage where your data will be placed without you caring about。

 Okay so this is the main problem I not that the infinite memory is not a thing Okay。

 this makes sense。 Yeah agree I don't like in general but this is how people think I't。

You know innovate enough but I wouldn't focus on the part that memory is infinite that's that's not important that kind yeah the important part is that you have a very large visual space that's fine and no matter what you do there I would transparently and without the program of carry。

ItH the location of data either in the， either in the disk or in the physical memory and the page table。

😊，It's like that you encoded your virtual address in like the normal address right Yeah。

 so I the page table is very simple second addiction I know the name the person I will define where they live by So I give the virtual address and based on the virtual address。

 I get the occasion that they live by whether they live in the this or in the memory is mine specific is on the program on the most level page shaable。

We are like iterating over the four page tables right and then if you are writing memory。

 do we start in the first one or do we iterate the last one and then start and so imagine this as the following so the first page table describes a very large location of regular data might be okay the second level of the page table。

Perhaps a bit smaller location where your data might be。there a bit smaller in the last one。

 the  four kilobyte location， so if your program let's say uses one gigabyte of data。

 probably what will happen is the following you use only one entry for the small for the first place they you would use only one entry for the second。

 only one entry for the third and many entry for the last。This means that for the immediate lines。

 you would not need to store extra entries for the paid stamp， you would one for this specific。

Which reduces a total size of if you want to learn more about it。

 there is a consequence which I don't want to deeper that。Paraics remains。Perfect。

 perfect extreme means that。The root of my train， like when I want to describe names and let's say I want to describe names。

Like name is Muhammad。 Okay the way I would look this up is I would quote it as M O。

 And then after M O there are multiple names that can。I right M o come MO。

Only me or something like that so you can think of it as encoding a searching for a smaller part of the virtual address the beginning Okay then I search for a bigger part of the virtual address a bigger part of the virtual address until I have the whole virtual address and find the final number Okay。

 that's make that makes a lot of sense take you。嗯。啊。啊。我可。What is LR。It's the least recently used。

 which means that I want to select a page， which has not which the least recently use。

 I did not use it all in the last say time window。It's used a lot classeses in many replacement forms when we want to figure out which data to replace inside the physical memory。

 where the system right now is using some approximation of this of the least recent used。Okay。But。Oh。

对呀。Yeah。什么意思？不让孩。啊。Yeah。大30号。哦。嗯。Yeah。啊。肯定是块。嗯。嗯。嗯是。没。Oh。得十个。对。嗯。🎼我次和你起。我。超级己。So。Yes。

So let's continue where we left it。So we fetch our data from the disk。

 We want to place it inside the physical memory。 and right now we figure out that the physical memory is full。

😊，So we do not know where to place our data。And we need to make room for the data。I it fine。

 and we need to make room for the data that we need to place inside the physical memory and we need to make a decision which data to evict from the physical memory。

 remove it from the physical memory and place it back in the disk。😊。

So modern systems using approximation of the least recently used policy。

 we try to evict the data rather has been the least recently used ones。

But one of these approximations is called the clock algorithm， which I'm going to discuss quickly。嗯。

So the clock algorithm works in the following way， so we keep a circular list of the physical frame or the physical frames in the in the memory。

 so as you can see for its physical frame we keep one bit so for its page in the physical memory we keep one bit。

😊，And what we do is the following， we keep a pointer to the last examined frame in the list。

 so for example we wanted to evict this one right or with our pointer points to this one and we figure out that we access this one or we access this physical page and when we access this physical page we set the bit。

😊，To R， R means that it has been recently accessed， and we encode this information as a bit。

If it has been recently accessed， the bit will be one in the physical page。😊。

So when we want to replace a frame， the first thing we do is that we start the clock。

 the clock starts and goes rightwise， and whenever we meet a bit，Whenever we see a bit。

 a physical frame where the bit is set to zero， this means that it's not recently used。

 that's our assumption， right？So as we move the clock， all the set bits will become zero。

 which means that we set their property， we reset the property。

 we assume they have not been recently used because the clock went by them。

 and the moment we see a physical frame， which has not been used which means that the bit is zero。

 then we select this bit as the eviction candidate。

And what we do is that we also set the hand pointer to the next frame in the list。

 So once we evict something， we move the hand pointer to the next one。😊。

Can someone tell me which property？This algorithm is missing fundamentally and would not work well in the systems。

 like if I just use one bit to show to figure out whether my data is recently or not recently used。

 what am I missing out basically？Like how would I figure out if my data have been very important to be kept in the physical memory？

In the history of like， my program running。This would be impossible to store using this algorithm because it cannot capture information about the history and how many times I have accessed this page in the memory it would only capture。

A partial history， very recent history of what happened with a page in the main memory。

 that's why modern systems use a lot more intelligent and sophisticated algorithms to do the page replacement。

So you can think the the analogous problem when it comes to caches。

 so the physical memory you can think it as a cache for the disk so we it's managed by the system software via the virtual memory subsystem and the page replacement is similar to the cast replacement so the page table is the tag store and the difference is that what is the key difference is that the speed of access to the cast and the physical memory is different。

 we can access the cache in one，2， three， four nanoseconds we can access the main memory in 100 nanoseconds。

😊，Second， the number of blocks， the CA has， let's say the L1 cast has a 32， 64 kilobyte size。

 which means it has a lot less blocks compared to the physical memory， which stores let's say2，4。

 16 gigabytes of data。We also have a tolerable amount of time to find the replacement candidates。

Ftting the data from the disk can happen in microseconds。

 Feing data from the cask can happen in nanoseconds。

 so we don't have the same slack in the same time to make the eviction decision in these two scenarios if I fetchs my data from the disk and it takes let's say one two micro microseconds。

 then I have time to make an intelligent decision of which data would evict from my physical memory。

The second and biggest property that virtual memory has been used in the last 20。

 30 years is memory protection。So we have multiple programs and processes which run concurrently。

 right， and its process has its own paid table。Its process also can use its entire visual address space without worrying about where other programs are。

 because the paid table would isolate fundamentally these two processes by storing different physical locations from the data to different processes。

So a process can only access the physical pages mapped in its page table， it cannot。

 for example of right， the memory locations or the memory of another process because it does not have access to the page table of another process。

😊，This provides protection and isolation between processes and enables access controls mechanisms per page。

 so we could figure out like given a page table， we can figure out whether we have permissions over a specific page。

😊，In this example we have two different virtual address spaces。

 it's one of the processes using two virtual pages and you can figure out the following information here。

 VP1 and VP2 VP1 maps to PPP2 VP2 maps to PPP7， VP1 maps to VP7。

 what does that mean that we have two processes whose virtual pages mapped to the same physical page？

😊，For example， I ran a process that use Tensorflow。 They both use the same library。

 which is Tensorflow， and they map the same code to the same physical pages that contain the code。

We need to enforce some sort of permissions and priorities when it comes to this specific physical page because we do not want one application to go and change the code of TensorFlow so we need to make and register this specific physical page as I read only library code if the virtual ladder space for process2 is malicious and wants to hack the system。

 it cannot go and basically change right now PP7 and change the contents of Tensorflow or and library so that it can hack the virtual other space of process one。

So the access in the production control happens we have virtual memory。

 so virtual memory does not only map virtual addresses， the physical addresses。

 it also keeps track of the protection mechanisms for its virtual page。😊。

So we have page level access control， so not every process is allowed to access every page。

 so we need some sort of care level support to access the system pages。

 we may not be able to execute instructions in sub pages。

 for example we might make we might avoid attacks like stack overflow if you know about it where we overflow the stack with some instructions and the attacker executes instructions if we would somehow not enable the attacker to execute specific pages。

 execute code from the specific pages then we would avoid such attacks。

And the idea is to store the access control information in a page basis in the process page table。

 so we want to enforce the access control at the same time as translation。

 the moment we find out the location of our data inside the physical memory。

 that's the moment we will figure out whether we have permissions to access this page in the physical memory。

You can see this example again we have we extend basically the paid stable entries with permission bits and we check bits on its axis and doing a paid fault and if we violate these permissions。

 then we generate。😊，We generate an exception， for example， in process I。

 we have VP0 which we can read so we can read from this virtual page， we can only read data。

 but we cannot write data so in PPP6 in this page we can only read from it and we cannot write to it why is this the case because。

😊，Process J is the only one who can read and write to it。

 so we do not want process I to write to it and create a synchronization problem， for example。

 of who write and when。There are multiple privilege levels in X sits which we encode using the access protection bits。

 I'm not going to go deep into this， the two most important ones in level 3 and level zero。

 either your patent system can do stuff or the user space can do stuff， our programs。😊。

And if we take a closer look at the page directory entry and the page stable entry。

 this is in 32 bit systems where we have a two level page table， we have the PDE。

 which is the first level and the PDE， which is the second level。😊。

We can see that using the first level， we can encode permissions for a larger number of memory pages。

Using the last level， we can encode permissions for a smaller number of pages。😊。

What does this give as a possibility， using a single entry in the first level of the page table。

 we can cover up the permissions for a larger number of pages。😊，For example。

 using the first level of the page table in 32 bit systems and using the access control bits there。

 we can encode the protection bits for 1024 pages in the page table and we don't need to do it for every 4 kilobyte page。

😊，However， the last level of the page table， which contains a translation from the 4 kilobyte virtual page so the 4 kilobyte physical page。

 it can protect only one page at a time because each entry protects one entry。😊，And as you can see。

 we can combine basically these two so that we can encode。

So we can create more complicated schemes when it comes to protection。

 we can encode some pages we can protect at the one megabyte granularity。

 let's say some other pages we can protect them at the4 kilobyte granularity and this way you can have a multi granular support for access protection。

So the question is right now the following。Your， let's say that somehow your hardware is unreliable and someone can flip the access protection bits。

So some hacker tried to hack in the system and their job is to basically perturb the A protection bits and they do this so that the user level program。

 so you're at the user level you can gain supervisor level access， basically you can be the external。

And the way you do this is you try to flip the access control bits from the user to the supervisor。

 which means that this virtual page doesnt belong anymore to the user space program。

 it belongs to the operating system， which is a much more privileged process。The question is。

 can this happen， does anyone know a way that this can happen。

 that they can flip bits inside the memory？Correct。Yes， Rohammer。

 I'm not sure if you have heard in the course about Rohammer， but if you remember Rohammer。

 it's a technique with which we can predictably induce errors in most D memory chips。

So we can predictably induce bit flips in commodity dim chips and this is the first example how a simple hardware failure mechanism can create a widespread system security vulnerability and this has been published in 2014 by a group of by a paper from our group and we saw how row hammer works so we open up a row。

 we activate a row in Dm and then we close the row， we open up again the row。

 we close again and what do we find out we found out that there are some bit flips in the neighboring rows so by hammering a single row activating and reactivating and reactivating and accessing again and again and again a single row in the system we can cause bit flips and perturbations in the neighboring rows。

😊，These are called the victim rows which suffer from this problem after accessing the Ham row。

 so if we repeatedly read the own enough times， we can induce errors which are called disturbance errors because they are caused by electrical disturbance。

And these errors can be induced in most of the real Dm chips you can buy today and the ones that in your system。

How does this work， we can have a simple program that induces many errors how by we try to avoid cast hits。

 we try to bypass the cachees and access the memory and the memory only so we flash the cast line from the cast the cast line X and well try to avoid row hits to x。

To avoid row hits to one and have two different rows， which we activate X and Y。

 we basically do the following。 We access row X。Then we access row Y。

 which activates two different rows， neighboring rows。

And then we flush the contents of x and y from the Caes。 So next time we access X and Y。

 they will not be in the Casis。 We will again go to the main memory and do the same thing。

What would happen in this scenario， the rows in between x and y would be the victim rose because they would be encapsulated by X and Y。

 and they would receive some electrical charge magically that changes their bits。

And you can see that we observed many errors in real systems。

This is a real reliability and security issue， and one can take over another wide secure system with this approach。

And this has been shown by Project Ze， where they tried to explode the Damrohaber bag to gain privilege access。

So the Google's original Rouhammer attack paper。Shows the following car exploit。

So the X86 page stable entries are dense en， so as we discussed before。

 they control the access to the physical memory and a bit in the Ps in the paid stable entries。

 physical page number can give a process the access to a different physical page。

So the aim of the exploit is to get access to the page table and give access to all the physical memory。

 so if we would basically flip some bits in the page table。

 we could simply fake the system assuming we are the hypervisor， we are the kernel。😊。

And we wanted to in this paper， they wanted to maximize the chances that the B fliplip is useful。

 and they did this， they did this by spraying the physical memory with paid stables。

Let me explain how this was done。This is the virtual observation space。 This is a physical memory。

 So the first thing they did was they simply used。😊，And mapping。

 they established the mapping between the virtual these virtual page and this virtual page。

 And this mapping was established using the page table。😊。

But they started creating more virtual pages。That would map to the same file。

 so basically they created from multiple different processes。

 they created different page stable entries that would all point to exactly the same file so we would have multiple process in the system。

 multiple page tables and the paid tables would all point to this specific file。😊。

And what they achieved is that they basically fed up the whole memory with page save entries that would point to the same file。

So what was the assumption that they have？If a bit in the right place in the pity flips。

 then the corresponding virtual address now points to a wrong physical page with readrite access。

 so if they somehow could flip a bit inside this page table。

 then they could get access to the whole system。And the chances are this wrong page contains a page table itself。

 So if you figure out a way to flip bits。Then there is a high chance。

That you will basically point to the page table。An attacker can also read and write page stables this way。

 basically you fill up the whole memory with page stables， you do your raw hammer。

 and then what you achieve is that you start perturbing the bits to the page table to make sure you point to the locations that you want。

😊，We're not going to how they exploited this， but that's the premise of the attack。

And let's see right now some more issues in virtual memory。

 so this was a very good example of how people combine one reliability problem and one existing abstraction in the system with virtual memory to take over the whole system。

So there three major issues in universal memory first is how large is the page table and how do we store it。

 how do we access it， second， how can we speed up the translation process in the access control check。

 and third， when do we do the translation in relation to the CA axis？😊。

And there are many more issues which we will not cover in detail。How large is a paid table。

 we basically answered this and the idea was multi level paid stables。

And in modern systems recall that we're using multileve page tables。

 they do not use as a single level， each one of these levels is used to store pointers for the next level。

 and if the pointers are not valid， we do not need to store the next level， basically。

So how do we access a page table with a page stable based register and if the VPN is out of bounds then the process did not allocate the virtual page which is an access control exception。

 if you see segmentation faults that's why they happened because you tried to access a virtual page that was not there in your page table and the OS figured out that you don't have access to this page。

So this is how X6 systems again use small pages， I will not go into details with respect to this。

And I was up to the second issue directly because we discussed about the page table。

So the big question is how can we speed up translational access control check and this is one of the main main main main research directions that the community has been focusing on for over more than the last 30 years。

How fast is the other translation， how can we make it fast？

So modern systems use a hardware structure that castes the paid stable entries and reduces the number of memory access to look at the paid table let me remind you the following if we would do one additional memory access per memory axis then we would have high performance degradation。

So researchers have introduced a component。That can basically store and give us very quickly the ritual to physical translation using the paid table blending without requiring going to the main memory。

Every time we want to read the page table。So how does the translation happen。

 the translation happens this way in modern systems。

 we have a core and the core ships the virtual address。

 it sends the virtual address to a component which we call the memory management unit。😊。

So you can think this component as part of the core somewhere near the core。

 it's a hardware component and is responsible for translating your addresses。

 the virtual address to the physical address， how does it do this。

 it tries to read the page table and store the most recently or some paid stable entries。😊。

So that you do not need to go to the memory hierarchy every time you request a virtual the physical of translation and you retrieve it quickly from the memory management unit。

So the memory management unit is responsible for resolving that translation requests。

 we have one of these per core if your system has a six arm core let's say you have six memory management units。

 ones for its core， and it typically has 3 key components。😊。

The most important component is the translation lookaocyte buffer。

 the translation lookaocyte buffer CAes recently used virtual to physical translations。

 in other words， it castes the most recently used by stable entries that contain the virtual to physical translation。

😊，Second， it uses table classeses。As as you recall。

 we have multiple levels in the page table and its level acts as a pointer to the next level。

 so the page stable caches offer very fast access to the intermediate levels of a multilevel page table。

 we give it a pointer and gives us the pointer to the next level。😊。

There is also a hardware paid stable watcher that sequentially accesses the different levels of the page stable to fetch the required paid stable entry。

 so imagine there's a circuitry fixed in hardware that is able to go and traverse the paid table for us instead of doing it at the software level。

😊，This is an example memory management unit in Interky Lake processors where we have two TLBs at the first level。

2L1 TLBs， one that stores translations for instructions， one that stores translations for data。

 one L2 TLB much larger， which stores translations for both instructions and data and then if we miss in this TLB。

 then we need to perform the work， basically， if we do not find the virtual the physical translation inside any of the hardware structures which store the most recently ones。

 which is the TLBs， then we need to somehow go to the page table in the memory to figure out where is the data inside。

 where does the data reside in the physical memory。😊。

So the idea is to cast the paid stable entries in a hardware structure in the procedure to speed up translation。

 this is the translation look aside buffer， it's a very small cast which stores the recently used paid stable entries。

AndIt reduces the number of memory access required for most instruction fetches and load source to only want TLB access in most systems。

 based on my experience， at least 95% of the memory accesses you do or even more are filtered by the TLB。

 you do not need to go to the main memory to fetch the page table to find the location of your data in the physical memory。

How does that work It's a similar concept to caches we have the concept of indices tags data and status so we take the virtual page number。

 we use it we form the index， we go to the corresponding set in the TLB。😊。

And we find out if the tags matchs and if the tags matchs。

 then we figured out that the translation is there and if the translation is there。

 we form the physical address。But the T LB is small。

 and it cannot hold all the potential paid stable entries。

So some translation requests will inevitably miss in the TLB。 we cannot find everything in the TLB。

So we must access the memory at some point to find the required page stable entry。

 so this process in the hardware level is called watching the page table。

It has a large performance penalty I will discuss later。

 and we have better TB management and prefeing， which can reduce the TLB mees。

And the question is who handle the TLB misses hardware software。

 So this is a question that has been answered and we do it in a hardware based manner in modern systems。

 but in older systems we're not doing it this way so our first approach is hardware minus so whenever we missing the Ldo TLB we trigger a circuitry that simply does the pointer chasing of the page table for us it's switchluing up the page table for us。

Once this is completed we fetch the pagetable entry and insert it inside the TLB so if the TLB is full again we have the same principles。

 you need to evict an entry in place there our paid stable entry there this is done transparent with the system software so you work the page table completely hardware the programmer doesn't need to know any of these。

😊，The approach number two is a software managed approach， which was done in MIPS processors。

Whenever we have an L2 TlB miss， we would raise an exception， the program raise an exception。

 the processor stops。The operating system takes over and starts watching the page table。

 lacing the page table to figure out what is the virtual to physical mapping。

 so the operating system fetchs the page table entry and controls how you will insert it or not in the tailbysup system。

😊，The good part with the hardware managed at stillB is that you don't need exceptions on until be miss exceptions are very expensive。

 Hand the control over to the operating system is a very expensive process。 Second。

 you might have independent instructions but can execute at the same time。😊。

If the operating system would take over， then you cannot execute any other instructions from the same program。

 and third， you do not need to bring any extra instructions or data into the caches to fetch。

 for example the operating system code or the operating system data that they will handle the exception。

However。The paid stable organization in this scenario is fixed。

 There is no flexibility with respect with respect to the design of the page table once we fix the hardware to walk to access this type of page table with four levels。

 we cannot go and change this from the operating system side。

 The operating system needs to use a fourle page table， if it uses a twole page table。

 the system will break because hardware expects that the paid table is a fourle page table。

The second approach is software manner still be where the OS can define the paid stable organization。

 we have more sophisticated TLB replacement policies。😊，But we need to generate an exception。

 So we have a performance over here， because every time we have a L to TlB miss。

Then to find the translation， we would need to raise an exception。

 fetch the code of the operating system， fl the whole pipeline so that we can fetch the data and execution and instructions of the operating system。

 then the operating system would work the page table， okay。

 we have more flexibility can do whatever it wants。😊。

But we would basically degrade performance of applications which have lots of L2TLB misses and cannot sustain the throughput and the size of L2LB for translations。

When it comes with the L1 TLB， data TLB， modern systems use say different page sizes。

 4 kilobytes2 megabytes and 1 gigabyte page sizes， I will not go into deeper details of how this is done。

But imagine it as we do not know the page size a priori。

 we know it only after we perform the other translation。So。

We have virtual the physical mapping inserted in the corresponding TLB after a TLB miss and during a translation request all the3 TlBs are looked at in parallel So this is a complicated process which I don't have very much time to explain but we have three TLBs one that stores translations for 4 kilobyte pages one that stores translations for2 mete pages and one that stores translations for one GB pages So right now the modern Linux and the operating systems do not just use one page size they use three page sizes usually and we need to figure out given the virtual address what is our page size and the TLB these3 TLBs if we have a hit in the L11 GBte then we would know that our page size is1 gig if we would hit in the L12 mete then we would know that the page sizes 2 mete and it would hit in the L14 kilote then we would realize that there are page sizes 4 kilote that's why we do three parallel memory axis is to figure out to which tLB are we hitting so that we。

quickly find which are。Fade size。Second， we have the L2 unified TLB。

 the L2 unified TLB causess translations for both instructions and data。

 again it's private per individual core， and we have two separate L2 TLB structures for  four kilobyte2 megate pages and one gigabyte pages。

The question is， how can the L2 TLB support both 4 kilobyte and to make a byte paid sizes using a single structure？

There is not publicly enough map information， so I'm going to skip this part so that。

We make it more simple。But the most important part is what happens if we miss in the L2LB and if we miss in the L2tLB we have a hardware paid stable worker so you can imagine this as a per core hardware component that works the multilevel page table to avoid the expensive context switches so you can think of it same to the things you do in the lab you can think of it as an FSM basically that goes and reads a pointer in every cycle and once it figures out that it loaded not a pointer。

 but the actual page stable entry， then it will stop the FS FSM will stop and resolve its execution so the hardware paid stable worker consists of two components。

 the state machine， the FSM that is designed to be aware of the architecture's paid stable structure it needs to do four accesses。

😊，And registers to keep track of outstanding TLB misses because we might want to perform more than one TLB miss。

 handle more than one TLB miss at the same time。What is a good part。

 we avoid the need for context switch until TLB misses。

 we overlap overlap overlap the TLB misses with useful computation。

 and we can support concurrent TLB misses。😊，The disadvantage is we have hardware area and power over here because we have a new hardware that accesses the paid table。

 you have a new FSM， we have limited flexibility to convert the software paid stable work。

 which is what we discussed before。And here you can see。

An example of why doing this in hardware work compared to software is very important。

Let's say we had a software paid table work here， so we would load a which corresponds to VPN equals one。

And we have a till L tl bemmi， we have an L2 tlbi。So after the L2 TLBs。

 we would have a context switch and the context switch would give the control to the operating system。

 which would be responsible for running the TLB mis handler and giving us back the translation。😊。

After the TLB mis is handled and the OS gives the control back to the hardware。

 then we would perform the load for address B， which is VPN equals 5。

 and in this scenario it would be a TLB hit， everything nice。😊。

In the case of the hardware paid stable water， though。We would again load a。

 which would be a TB means， but in this scenario， we do not context switch to the operating system。

At the same time， because we do not contact switch， we can perform the load A in a pipeline manner。

 so in a pipeline manner we perform the O day with PPN equals 5 and at the same time we have a TiB sheet for load B。

And we have the paid stable work in the hardware level that services that he be miss for load A。

 So what did we gain， we saved these cycles and we saved these cycles because in this scenario we first overlapped the load B access and the translational process with the load A。

😊，And we also save time because we do not spend time in context switching and giving control to the operating system。

Any questions？Okay。Then there is a component of the page table work you' is using which's called the pagego Cas and the pagego Ca is cast translations from non-les levels of the multilevel page table to accelerate page stable walk so we have these intermediate levels which with store pointers in the page table and you can imagine the pagego cache as very fast components that basically avoid these intermediate levels of the page table。

😊，So there are more more issues when it comes to translation， which is with respect to casting。

 I don't want to go there because this is a more advanced concept。

And I'm going to talk more about the evolution of the virtual memory system。

 So as you can see in the left。😊，Back in the days， not so far basically back but back in the day。

 so we did not have a very advanced other translation substem we had simply an L1 data TLB and L1 instruction TLB and then when we missed we had a software repeat paid table what we would raise an exception we would go back to the and this happened because of the following reason that as I discussed before there was no concept of data centric data where we were not using lots of data basically we did not design our systems based on the size of the data。

Right now we have a lot more components in the other translation subsystem why because there are many。

 many workloads which make use of a large data footprint and we need to cover it up with more TLBs。

 we need to cover it up with a paid stable worker， we do not need to contact switch every time we missing the TLBs。

As you can see these are two systems the14 processor from Apple which which is in the iPhone 12 pro。

 and this is the Intel AMDNR architectures and as you can see。😊。

There are fundamentally different properties in these two， for example。

 the A 14 is using an L2 DLB with three kilo entries。😊。

While in most Intel AMDNR process you can find L2 TLBs with app to let's say two kilo entries and as you can see the page size are also different app is using a 16 kilobyte page size base page size while Intel and AMDNR are using a4 kilobyte page size。

😊，And now let's talk about the visual memory overheads。

 which is also the main part of my research endeavors。😊。

So we recently published a work called Viwa which enabled how to enable fast and accurate virtual memory research with an imitation based writing system simulation methodologyology。

 I'm not going to go deeper into how we did this and how the simulator is formed。

 but I put this here so that I can show you the concept of virtual memory over here。😊。

So we have modern systems that use GPUs， CPUUs， network interface cards that all use virtual memory these days。

 so virtual memory is a cornerstone of most modern computing systems and the question is。

Does virtual memory come for free， No virtual memory causes high performance overheads because of two reasons。

 number one， memory allocation and number two address translation。😊。

So let's see first the memorial location overheads， so we have emerging workloads。

 as you may have heard， functions a ce workload， serverless computing， we have LLMs。

 we have sort input sort out with LLM inference models。😊，Wwhich are short running。

 they run in less than a second when you execute your query in Saippity it runs in less than a okay doesn't。

 but close to less than a second， it also has a very high spawning through because we want to execute many as many queries as possible the same time because the whole universe is using Saippyity or gemminized days。

What's the problem with this these applications are spending a lot of time on OS memorial allocation routines。

 you basically try to allocate， let's say the KVC or some data structures in your LMs or in your functions which takes time and the time it takes to allocate in the operating system。

 all this data is often more than the execution time of the workload itself。

 because the workload might run on a GPU or an accelerator while your OS memorial location would run on the CPU。

So we have time spent in the operating system， which cannot be amortized due to the short execution of the workload。

In this plot we demonstrate the fraction of the total execution time as a percentage of the physical memorial location。

 how much time do you spend in physical memorial location compared to total execution time across some workloads and as you can see here you can see Lama baggel and Mistral which are famous La inference workloads and as you can see we have an average of 32% of the total execution time spent on simply allocating memory we didn't run anything with the spectral program we simply allocated memory。

😊，And the second type of overheadat is the other translation overheadat。😡。

We have another set of workloads like sparse machine learning， we have graphraph neural networkss。

 we have bioinformatics workloads which has vast data footprints， we have graph analytics。

 we have databases that are long running， for example。

 we run our bioinformatics workload it runs for one and two days。😊。

And they also have irregular memory access because of the properties of their inputs。These workloads。

Cannot fit basically all these daytime and the translations inside the T L B。

 So we have lots of T B misses。 We have lots of trade stable works。

 which means we have a high latency other translation。

And this high late other translation basically stops us from fetching data quickly。

 basically in this plot， we demonstrate that other translation on average takes 26% of the total execution time in this very demanding irregular workloads。

😊，So we have。In a nutshell， two types of overheads， which are caused in diverse emerging workloads。

 we have both other translation and minor paidfalls。

 which basically is a memorial location in this workloads。

And the virtual memory overheads are expected to increase as we transition to much larger physical other spaces。

 so as we go into the future we have， for example， in modern systems we have CPU and CPU together working and they use a single memory which we call the unified memory。

 virtual memory scenario we have direct sort of axis if you have seen devices where we can directly access the storage without using a memory we also have memory desegregation right now from your computer there are systems which enable you to use not only the Dm available in your laptops but also the D available in the remote node somewhere else which increases your effective memory capacity basically。

😊，We integrated the simulator with five different simulators and we built tools that have many state of the art techniques and we validated it against high end server grade CPUUs and we demonstrate many use cases if anyone is interested。

 we can discuss and see how you can have your first research opportunity and you can find online and play with it。

 I have a documentation as well so we can get started。And in general， we have been focusing。

 I have been focusing a lot in the group in general on how to improve the virtual memory overheads here is a work we published in micro 223 two years ago on how we can leverage the cachees to store paytable entries and not just store them in the TLB subsystem but start them also as repurposing by repurposing the data caches in the system。

 we also published another work where we show that placing a virtual page anywhere in the physical memory is not very helpful and it would be good if we establish a more restrictive mapping so that we can do other translation faster and this is the more a bigger work where we show that doing that we need to completely think the virtual memory subsystem in order to alleviate its overheads。

In summary， virtual memory gives the illusion of infinite capacity。

 we have a subset of virtual pages which are located in physical memory and a page table maps。

 the virtual pages of the physical pages it acts as a dictionary and this process is called the address translation so we have a TLB and a memory management unit that tries to speed up these address translations at the core。

 we have the multilevel page tables which try to reduce the size of the page table。

 and if we try to use different page table for different programs we can provide memory protection without the programme needing to synchronize over the memory acts they're doing。

😊，There is a lot more virtual memory which we will not cover when it comes to virtual machines running programs and hypervisors。

 you can think of。Concepts like virtualized environments where we don't have simply one operating system。

 we have two have the guest operating systems and the host operating systems。

 so we do not need to translate just from host virtual to host physical。

 we need to translate from guest virtual from the guest operating system to host virtual to the host operating system and then from host virtual to host physical which makes the other translation process both a lot more complicated and a lot more expensive。

😊，So you have seen and you may have understood that virtual memory is one of the most successful examples of architectural support for programmers。

 it's one of the first endeavors of research where people tried to provide a much better abstraction to the programmer to make their life easier and it's one I think of the like least。

😊，One of the few basically hardware Eco design primitives that have been actually established in the process nowadays。

So going forward， there are many more problems with respect to how virtual memory would scale。

 like if we have very large physical memory sizes， I described this before with SSDs with unified virtual memory between GPU and CPUU。

We have hybrid physical memory systems， we might have a D， a non volatileat memory。

 we might have a SSD as well。😊，We might have many accelerators in the system。

 we had have neural processing units， CPUUs， GPUs working together and access the same physical memory。

 and might have visualized environments like hypervissors。

 jet microcarnels and other weird software structures。



![](img/3f2e9102bfa7b0f61ff39fe2bc1852f1_2.png)

You can find our lectures on YouTube， more lectures and virtual Me。

 this is an old lecture from CMU from Monor， and you can also find the Catat research discussions we did for these three works in our computer architecture course in the master's level。



![](img/3f2e9102bfa7b0f61ff39fe2bc1852f1_4.png)

And thanks a lot for your attention and I'm happy to answer any questions you have。Yeah。Oh。哎我们见。我下。啊。

我刚说的。不在那些我。没有。身咩长。诶请你个。我マ新要了。

![](img/3f2e9102bfa7b0f61ff39fe2bc1852f1_6.png)

そうで、すね。你诶我 many。Yeah。

![](img/3f2e9102bfa7b0f61ff39fe2bc1852f1_8.png)