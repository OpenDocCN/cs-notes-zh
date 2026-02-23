# ETHZ《计算机架构基础｜ETH Fundamentals of Computer Architecture 2025》中英字幕 p11 Lecture 10_ Virtual Memory (Spring 2025).zh_en -BV1Xc19BnET7_p11-

![](img/6f52fa76af7cc3905b36b97461096cae_0.png)

到是道。什行。审到。You们。I it fun？That's like face。Thepresent ofYeah， I don't know why my， my throat is。

I don't I don't have skin so。Yeah。

![](img/6f52fa76af7cc3905b36b97461096cae_2.png)

ちはにかか。Yes now。

![](img/6f52fa76af7cc3905b36b97461096cae_4.png)

So。So。嗯。是现在。暂说么。Okay。是难看。Okay。好事。あ。对。我。Was a best teenager？你や the Georgia。嗯。W。Yeah，出まし。あ。装。对这个一s那个。

我你在车上个。あす。Sa。好。我，所把自。No sure。W。Yeah。想死么。不。I。Yes。这。Some。可以。哦。Yeah。Yeah。你手机。哦行。I。🎼Oh。🎼，Yeah。Thank you。

 everyone。Thanks for coming。Will excuse my voice a bit my elders are killing me。Yeah。🤢。

So I'm Cr Sans today we're going to talk about virtual memory。

 so how many of you have heard before about it？All of you right from the informatic or something like that。

 where you implemented something in the kernel right， you remember correctly。

That's nice I'm Consants， I'm a fifth year PhD student I received my bachelor's and master's from the NUA in Athens。

And I'm working heavily on hardware and operating system code design with a focus on virtual memory and memory management。

And lately on hardware software design with the focus on programability intelligence interfaces。

And lately， we're also exploring some security primitives for emerging and futuristic systems。

So one of the。Tey review type of papers that you can take a look at is this one written by owner。

 it's called intelligentlig Architectures for intelligentligent computinging systemss。

I suggest reading it， it shows how you can design systems in data centric。

 data driven data aware monitor， and it does a very good job in giving a very broad perspective in the topic。

These are the readings， I will describe some of them later， but I suggest taking a look at them。

 they will give you a good background in the topic and make you a lot more capable of understanding what's going on across different concepts。

So virtual memory。So that's how the programmer perceives right now the memory。

 so when you write a program you write it in a way that you interface with memory with loads and stores when you start the memory。

 you store data inside the memory when you load from the memory you simply retrieve data from the memory。

And in an ideal world， we would like a memory that can be accessed at zero latency so we simply go to memory for free。

 we retrieve our data where we go and write to memory for free and we do not need to wait。

Infinite capacity and this would be very， very important if we had infinite capacity memory。

 then we would be running our LLMs in our mobile systems， not in the cloud basically。😊，And zero cost。

 we want to obate for free。And infinite bandwidth， we're going to affect as much as possible with zero cost。

But。Nice。But the programmer sees visual memory in modern systems and they can assume that the memory is infinite。

 so when you write your C programs you don't care about the physical memory that lies at the back of your system。

So the reality， though， is that the physical memory is much。

 much smaller than what you assume when you write your C programs or your Python programs。

The system internally， somehow magically， it maps the virtual memory addresses to physical memory。

And it does that so that it can help the programmer avoid the concept of physical memory so that you can write your programs in a much easier manner。

So the program error in this concept does not need to know anything about the physical memory。

 and you might have a very small memory which appears as a huge one when the program is writing its program。

However， as we will discuss， this introduces many complexities to the system and the microarchitecture。

 and it causes lots of overheadheads， which I will show you later。So the question is。

 why do we need virtual memory？Bal memory brings many benefits in the table。First。

 the programmer does not need to deal with physical addresses。

Its process has its own virtual address。So it has a virtual address space which is very， very large。

 for example， when you write a C program you do not need even to care about the virtual ladder space。

 you simply call a library， a malllo， for example， you take your virtual address region and you don't care about what happens on the backing store which is a physical memory。

The mapping of the virtual physical address is independent of the programmer we don't need to care about this。

😊，And this enables coding data to be located anywhere in physical memory。

This way we could move around data inside the physical memory for other purposes。

 and you do not care about it as a programme or you do not care about how data are being moved inside the physical memory。

Second。We can achieve isolation and separation of code and date of different processes in physical memory。

If I decouple the concept of the programmer allocating data in the physical memory。

 then I have a system that can basically make sure that two different processes。

 two different programmers， two different programs can map their data different locations in the physical memory。

 so you do not need to basically care about how data have been isolated from another program running in the system。

This offers protection and isolation。And third。Code and data sharing between multiple processes。

If you have two processes， you have two programmers which want to share their data。Then basically。

 you can achieve this transparently by making sure that their visual addresses map to the same physical page。

 physical data basically， and this can be done transparently that two programmers do not need to synchronize with each other and say。

 okay， we're going to put our data in the same physical page。

This is a system with a physical memory only doesn't have a pixel memory and this was used in the very whisper computers。

 many early personal computers also use this and many other embedding systems and in this scenario the CPU the CPU generates load and storage distractions which operate directly physical memory and as I will show you this creates many problems。

😊，The problem is that the physical memory of the limited size。

 so you might have let's say a memory that its only some megabytes large and the question is what if you need more than that？

The question is then， okay， should the programmer be concerned whether the physical memory is small or large。

 so will I tailor my program to what the physical memory characteristics are？

Also like if I cannot fit my data inside the memory。

 should I also care about writing routines that transfer the data from the storage to the memory and then I will handle them mapping inside the memory now that that's very hard in the life of the programme becomes very hard。

By this。So we have multiple programs that also may need the physical memory。

 may need access to the physical memory， and then you have a system where each programmer specifies their own physical addresses。

😊，And you need to make sure somehow that first you can fit all the data inside the physical memory and the programmers might not have some sort of synchronization with each other。

 second， if I write a program that explicitly wants to perturb some data of another process。

 then I break the isolation guarantees。Also， if I have an ISA that has a much larger address space compared to the physical memory size。

 then I would need to basically use different ISAs for different memories。

 which would again create lots of legacy problems in the systems。

 we would need to have the same version of the program for many different systems。

So these are the difficult basically of direct physical addressing first。

 the programmer would need to manage the memory on their own。😊。

Which is very inconveient and difficult。And it's very difficult when you have more and more processes running in the system。

So it's very hard to also support code and data allocationation。

 so if I want to move data around I need to make sure that I inform the rest of the process that I move data around。

Third， I need to run multiple processes concurrently。

 and how can I make sure that one process is not touching the data of another process？

And last it's very hard to support data and code sharing across processes。

 we need to explicitly synchronize processes to talk with each other and agree on the physical location that they're going to use C data。

And the question is right now， okay， this model of physical memory using only the physical memory and there is no virtual memory it doesn't work well and we need to find out though how does virtual memory work well。

😊，And the idea of virtual memory is to give its program。

 the lose of a large address space while having a much smaller physical memory。😊。

This way the programmer does not need to worry about managing the physical memory。

 basically there is a system that somehow magically manages the mapping between virtual and physical memory。

In this context， the programmer can see an infinite amount of physical memory when you write your again。

 your C programs or your Python programs， you allocate a race and you don't care about the size of them until probably looks tell you out of memory。

 I don't have more memory to give you。So the hardware in this context in modern in most modern systems。

 the hardware in the software cooperatively automatically manage the physical memory space to provide the illusion of a very large memory and this is maintained independent for its process。

 so this is not global in the system， its process has the illusion that memory is very large。However。

 to achieve this， we need some sort of indirect and mapping of addresses between visual addresses so we're using visual addresses in our program。

And we need we cannot access right now memory with the virtual addresses。

 we need to access them with the physical addresses。

So the virtual address is the X86 systems in older systems which was called a linear address and with this linear address we could not access directly the memory。

 we needed to find the corresponding physical address。

 the virtual address so that we are able to access directly the physical memory and this called the real address the X86 systems。

So when你。Another translational mechanism， which can translate virtual addresses to physical addresses。

 and it's a mechanism that involves hardware and software components at the same time。

This is an example， so we have two applications， application a application2 a B， one and two。

 they are running in the same system and in this context they have their own virtual address space。

 virtual ladder space number one virtual address space number two and the physical address space which is backed by the physical memory is much larger than the virtual address space for now of these two applications。

So we split both the virtual ladder space is and the physical ladder space in chunks which we call pages。

 for example most modern systems especially in Linux is using  four kilobyte pages， for example。

 your Apple systems are using 16 kilobyte pages as a bases， the base page size。

And then what do we do？Whenever we want to access memory from application one to be able to access memory。

 we need to map these virtual pages。To the physical address space， to the physical memory。

 so we know that whenever we access this data， this virtual address。

 we will be accessing this physical location。😊，And we do this for all the processes in the system。

We basically establish this way that filter from to physical address mapping， however。

 as you can understand。Being able to discover the virtual to physical other mapping requires some in direction basically it's some sort of pointer chasing。

 we need to basically take the virtual pointer and find out the location in the physical memory。😊。

Is that clear to everyone？And these are the major four issues when it comes to thedirect。

 this pointer chasing and the mapping so first is when do we map virtual addresses to physical addresses this is important。

Because different systems simply this in a different way。

 the most common right now that's happening in Linux， for example。

 is that the moment you first touch a virtual address。

 that's when data is allocated at the physical memory an example is the following if I give if I write a program that allocates let's say 10 gigabytes of an array which is 10 gigabytes large。

 but I do not touch， I do not write to any of these 10 gigabytes。

Then this will leave only in the visual address space。

 I will never map it to the physical memory I will not consume these 10 gigabytes from my physical resources。

 which is very important to understand。Only when I start touching and writing to this array and I'm using it in my program。

 I will be allocating the memory in the physical space。Second， what is the mapping regularularity？😊。

Do I allocate and split in chunks of bytes， kilobytes， megabytes， gigabbytes。

 do I have multiple grarangularities， again， modern systems use multiple grarangularities。

 not by default， but there are some specific modules in the kernel that enable that。

 we use both four kilobytes2 megabytes1 gigte mappings。Third。

 where and how to store the physical virtual the physical mapping so we need some sort of data structure which you will probably know iss a page table。

 I will talk about it later。That stores this information。

 this mapping basically this pointer changing， I go and look at the page table， this data structure。

 and I find out。Based on the virtual address， the corresponding physical address。

Plus what to do when the physical other space is full so when my memory is full I said I want to give to the programme the illusion of a very large memory。

 a very infr memory， so when when the physical other space is full I need to be able still to run my program and to do this I need to send some pages back to the disk and I consider the disc right now part of the physical other space。

But how do I choose which pages I sent back to the disc or which pages I bring from the disk is a very big research direction。

So some definitions， we have the virtual address space divided into pages and the physical address space divided into frames。

 I never understood why there is a difference between these two。

 I think everything should be called pages。And the virtual page is mapped to a physical frame if the page is in the physical memory or in the disk。

 so in virtual memory there is a chance that our virtual page is not mapped to the physical memory。

 but it's mapped somewhere in the disk。😊，If you have seen in your system， for example。

 the swap space， when you want to enable swap space in Linux。

Then some of your virtual pages might be mapped to the swapwa space and not inside the physical memory。

😡，So if an accessed virtual page is not in memory， but on the disk。

 somehow our subsystem needs to fetch the data from the disk。

 put it in a physical frame in the memory and adjust the mapping and this is called in the systems demand paging。

 so when your data resides in the swap， you cannot directly access it from the swap。

What things to happen is that somehow magically you fetch it from the swap in the memory。

 and then you are able to access it from your program and read the actual data。😊，🤧And page table。

 as I said before， is a table that stores the mapping of virtual pages to physical frames。😊。

So in other words， you can think of the physical memory as a cache for pages which are stored in the disk this is not always the case but it's mostly correct as a correct statement so we basically treat the physical memory as a fully associative cache where what does a fully asciative mean I can place a virtual a virtual page anywhere in the physical memory so basically as you have seen the concept of full associative caches I can place any cast line with a tag to to every possible location which might be free in the cache it's a similar concept here I can place a virtual page anywhere in the physical memory as long as there are three pages。

And there are similar caching issues which are also。

 which also exist and we covered earlier in the lectures。

So like placement where where and how to find the page in the cache which is the memory what page are you removed to make room in the cache which is the memory again like large in the management do I use large pages small pages do I use only one page size and the right policy do I always write back to the disc needed or do I simply write to memory and just let it go。

This is a good analogy that you can think of， for example。

 the cache is which use the concept of a cast block in memory， we use a visual memory。

 which is the concept of a page。😊，In the cast， we use the concept of a block size， in the memory。

 we use the concept of a page size。And you can think of more analogies like that。

So this is how things would look like a process has its own virtual addresses。And some of the data。

 some of the visual pages would map to the hard drive。

 while some other pages would map to the physical memory directly。😊，In modern systems。

 we want most accesses to heat in the physical memory because if they do not heat in the physical memory。

 then I need to wait to fetch data from the disk which is very， very， very slow and expensive。😊。

In example， we have a system with a 2 gigabyte let' say memory， a virtual memory。

 which means that the 31te for its process and the physical memory size is only 128 megabytes not reaching up to the 2 gigabytes。

 so we have a paid size of 4 kilobytes to the power of 12 which means I need 12 bits for the offset。

😊，27 beats for the physical address and 31 beats for the virtual address。😊，How is this organized。

 so why is the page offset 12 bits because I do not care about translating the offset inside my 4 kilobyte。

 I do not even translate this and you translate only the rest。😡。

And in terms of virtual pages I divide by the page size。

 which means I have only two to the power of 19 pages in the system。

 virtual pages in the for process and inside my system I only have the power of 15 pages so at the end of the day what do I need to do I need to take these 19 bits and somehow translate them to these 15 bits and this process is very as we also is very costly translating these 19 bits to these 15 bits in the physical other space。

These 12 bits need will remain the same， we do not need to translate them because it's the granangularity at which I organize my memory。

So the page table in the system has an entry for its virtual well page。

And its per table entry has a valid bit。To show whether the page is located in the physical memory or not。

 for example， if the validity bit is not set， this means that our data reside in the disk so we go fetch the P we look at the page table。

 you can think of the page table as a dictionary basically we will go look at the page table we find out that the validity bit is zero which means our data is not in the physical memory and it's in the disk so we must fetch it from the disk。

And the physical page number， so if the validity the validity is set。😡。

Then we simply read the physical Bs number and we find out the location of our data in the physical memory。

😊，There are many other bits related to replacement policies that can modified permission access bits。

 which are relevant to performing optimizations， which I will discuss later。

This is an example of a page table and as you can see there are four entries in our page table right now which correspond to different virtual pages as I will show you so for example this one corresponds to the third virtual page for the process this one corresponds to the fourth one。

😊，So an example here we take the virtual address， the virtual address is this one you can see there the virtual page number is0 x2 basically and the offset we don't care about as I said we don't need to translate the offset at all so we take the virtual page number and we need to somehow access the page table to retrieve the physical page number and how do we do this first imagine the page table as a data structure which is in your systems right now allocate by the kernel so when the kernel allocates it it allocates as an array let's say and we need to find the location the starting location of the array which is this let's say that we start from the location zero here。

😊，So this location called we call it the page stable based register in modern systems。

 it's called the CR3 Reg， for example， in XA664 systems。😊。

So we take the visual page number and we index our page table。😡，So we take the xx 0 x0002。

 and when we reach this， we need to probe this entry， which contains the 7 FFF。So in this scenario。

the7 FFF is one part of the physical address， it's the physical page number。

 and after we retrieve the physical page number， we simply concatenate the page offset which does not need to be translated。

😊，So if we want to find out a different address， the0 x 5 F20。

 we also need to again find the page table lender that corresponds to the VPN and look up this specific paid table entry。

🤧。In this scenario the VPN is5， that's the visual page number。

 we find out that say this specific visual page corresponds to the first physical page and we simply again concatetnate the offset。

So this is a more tricky scenario right now， we want to find the physical address of the visual address 73 e0。

😊，Which is number seven and when we look up this specific entry in the page table。

 we find out that the validity is zero。Which means that the data does not reside in the physical memory。

And based on what we described before， this means that the data resides in the disk。

So we need to find out go and search for the data in the disk。And in this context。😊。

The general algorithm is that especially in 64 bit systems。

 we take the virtual page number which is 52 bits， this is in a very inration systems。

 we probe the page table， we retrieve a 28 bit number。

 we concatenate it and we get back the physical address。😊，And the question is。

 if we have 64 bit virtual addresses。And 40 bit physical addresses。

 how large would it be the the table， Does anyone have an answer？😊。

Like how many entries would I need inside the page table？

So that to support this sort of system that translates 64 bit， bit addresses to 40 bit。

 physical addresses。Don't do them math its many， basically。That's the answer。

 so you would need to the part of 52 entries。Multipliied by four bytes。

 let's say four bytes is the size of the pointer。And in this context。

 we lead2 to the power of 54 bytes in the system， just to start the page table。

 which is impossible we cannot allocate in our memory to the power of 54 bytes because probably we don't have such a large memory。

And this would be just for one process， like if another process uses another 64 bit virtual address virtual address space。

 then I would again need to another two to the power of 54。Large page table。So。

Imagine right now that there's no way our process uses all these 64 bit virtual other space。

 but there's no way this is the case， cannot use sensor large other space and we're wasting so much memory that for the page table。

So the challenge number one with a page stable is that it's very large。

We need to somehow find a way to allocate some part of it in the physical memory。

And the way is using multileve hierarchical page tables。

 so we want to keep some part of the page table inside the memory and allocate whatever is needed on the fly without reserving a priori。

 the whole page table。So the idea is to organize the page table in a hierarchical manner such that only some parts of the page table have to be allocated in the physical memory。

 and we do not spend， let's say to the part of 54 large data structure tooring our physical memory and simply have this dictionary point to us to the physical locations of our data。

😊，🤧。So this is an example again。In this example， we have。

Two levels in the page table we have the first level and the second level。

 so the second level is not allocated immediately to the physical memory。😊，So for sure。

 the first level is allocated immediately to the physical memory， it's already allocated。

 but when we start the process， we need to allocate this part of the page table in the physical memory。

😊，So whenever we want to perform address translation。We basically。

We basically take the pay stable number， the pay stable number gives us。😡，An index。

 a key inside the first level page table。😊，And we find out in this scenario that in the first level page table。

 there is a valid entry。😊，If there is a valid entry。

 then for sure we will find a second level page table which will contain basically the correct translation。

 so the content of the。Of the first level of the page table will act as a pointer to the second level of the page table so you can think of it as a linked list where each one of these entries have a pointer to the second level but what is the cuts here that if an entry here does not have a validity bit set。

 then I do not need to allocate the next level of the page table in this scenario for one through three entries for example which are set to zero I do not need to allocate the second level of the page table because their validity zero there is no way I will find them in memory so I do not need to allocate them。

Unless some process， unless some data at some point needs to access this part of the page table。

Is that clear to everyone？Yes， and this is an example of how36 architectures do it I will give an example later as well so I can skip this。

Yes， this is how the X86 handled the small page， which is the 4 kilobyte page translation where you simply read the CR3 registers and you go through two levels in the page table to retrieve your physical page number。

😊，This is the difference here that they do it also with different page sizes。

 but that's not really important right now。This is how modern X8664 systems do it。

So we do not have only two levels in the pay table， we have four levels。

So first the first thing that we do is that we take the virtual address and we split into chunks of nine bits。

😊，So the CR 3 register points to the first level， so if we use as offset the first bits。😊。

We can access internally。The key to the first level of the page table and this。😊。

This level in the page table is always allocated， there is no way that for a process this specific part isn't allocated because the CR3 pointer would not be valid if this frame was't allocated。

After we access this frame， we。😡，A pointer here the same way as link list work and using this pointer and the next nine bits we are able to access the second level the second level。

 the third level and the fourth level would not need to exist and unless I touch the data I basically access data I need to access the data so imagine that each's one of these entries these are 512 entries they cover a very large amount of virtual memory。

So our process will use only a small subset of these entries in the first frame。I access the data。

 the pointer again in the second level， I access my third level， again I use the key here。

 the key as a pointer to the next level， and then I concatetnate it with the next nine bits。😊。

So I perform this itly this sort of pointer chasing this， it's like a three search。😡。

And I figured out at the end。My page sta entry which the page sta entry contains the physical frame number。

 so you can think of it as a pure pointer chasing three sets。

 we're need to go through different levels inside the linked list inside the weird tree hierarchically to find the leaves which give me back the physical frame number。

To perform this sort of sets， and let's say which it's a process we call paid walk。

We need to perform four memory access in this scenario， one for the first level。

 one for the second level， for the third level， for the fourth level。So during the page stable walk。

 looking up the page table in X86 system might result in four sequential pointer changing based memory accesses。

 which we will show later it' a very expensive process。So we saw this。

 we were able to allocate the page table hierarchically， so we avoided the memory overhead。

And the second and most important challenge is that， okay。

 so right now we need to perform four axises， let's say。

 for our page stable work to retrieve back the physical location。

 and then we need to perform one more access to access the data from the physical memory。😊。

And this is very expensive， imagine if your computer would need to do four memory aes additionally。

Twes access it does to the physical memory， this would be very， very slow。

 it would basically be four times worse in performance。But there are ways to speed up this process。

 we do not need to walk the page table every time we want to translate our virtual addresses to physical addresses。

😡，So how do we perform other translation？To to support digital memory we need both hardware and software support。

 so the page table as I said before it's in the memory and it is the job of the software which in our case is the operating system to populate the page table this way we decide what to replace in physical memory。

Change the page table register on a context switch。

 So imagine you want to run a different process in the next context switch。

 then I need to change the contents of the。Paid table register of the CR3 register so that I can point to the page table of the new process。

We also need to handle paint faults and ensure correct mapping， I will talk about paintfalls soon。

So how does the CPU discover the width of the physical mapping。

 this is what the hardware does is that what has been delegated to the hardware as an operation。😊。

So the other translation。So we have the page size again， specified by the ISA。

 let's say we have  four kilobyte，8 kilobyte，2 gigabyte pages。

And there is a page table which contains an entry for its virtual page。

 let's call this a page stable entry the page stable entry is basically the leaf in the page stable of in actually the 664 system only the last level。

😊，So that's how other translation is performed in modern systems our core is sending virtual addresses。

To the memory hierarcharch， the memory hierarchy contains the page table。😊。

So once we perform all the lookups in the page table， we retrieve the page stable entry。

And the question is whether we could speed up this process， because again。

 if we want to perform so many accesses to the page table。

 then this would cost us a lot in terms of performance。First， let's define what's a paidtable entry。

 a page table， basically you can think of it as a tag store。

 addition analogy to the cache the hardware cache for the physical memory data store。

 so it's a mapping between virtual memory and physical memory and the PT the paidtable entry is the final entry is basically is the tag store entry for a virtual page in the memory it needs a validity bit it needs tag bits same way as normal hardware caches work。

😊，And the question is， okay。I understand all this but。

Who decides where I will map a virtual page inside the physical memory？So imagine again。

 we have an application here that is using this virtual ladder space。😊。

And it's the first time it tries to touch this specific virtual page。

 tries to perform a right to this virtual page。And this is the physical memory that our system is using。

So from the virtual address space， we need to somehow in some way map this virtual address。

 this virtual page to the physical me。😊，And this process is called a fault。

 so we need to handle a fault to map visual addresses to physical addresses and it happens on runtime as you're running your programs and you access your perform a right。

 then you would basically trigger a fault in the system and as I will describe now the operating system would come over。

 it would stop the process the operating system comes over and handle the memorial location so it can map from the visual address space to the physical address space。

So while this is happening， our application is stall。

 so application is waiting for the mapping to be established before being able to access the virtual address。

So the operating system while the application is installed。

 is trying to find free space in the physical memo。This is a single scenario。

 we simply did a malllo that we don't fetch anything from the disk。

And we write for the first time in our data and when we write。

 we need to somehow find a free location， the physical memory to store our data。

 we do not have something backed up by the disk。This is a very easy， let's say。

 to handle fault by the operating system， but there is also the major fault。In the major fault。

 we find out that okay， I needed to load the file。😊，So the virtual addresses I got from my F open。

 let's say。Mepped to map to a baching store， the baching store is basically a file and I need to read a file。

 how do I read files， I fetch it from the disk and once I fetch it from the disk then I need to find free space in the physical memory to place some chunk of this file and then I am able to read the data from the physical memory because I cannot read it directly from the disk I cannot read my file directly from the disk。

After the operating system handles this fault and establishes a virtual to physical mapping。

 it needs to update it or store it somewhere， it needs to store the information that okay。

 I took this virtual page and I mapped it to a physical page， it needs to remember this somehow。

And how does it do this， it goes to the main memory and updates the data structure which stores the mapping。

 which is the page table， so once we find free space for our data。

 then we simply update them virtual to physical mapping by updating the page table。

So if your page is not in the physical memory it's in the disk， this is a catch of the major fault。

 which is the most complicated scenario。😊，The page save length3 indicates that the virtual page is not in the memory。

 so when we access this page， we trigger an exception in the system。😊，And the US exception1 is in。

And it needs to move data from the disk inside the memory。

 other process in the system can still execute， so our process is the only one stall waiting for the device to finish its job。

😊，So before the fault， we had two virtual pages which were mapping in the disc。

 so they were mapping to data inside the disc after the fold is finished。😡，This page。V page。

Is right now not mapped to the disk， it's mapped to the memory。

 so data was brought inside the memory and right now we change the mapping。

 it doesn't point to the disk it points to the memory。😡，This is how modern systems do this。😡。

So the processor signal sound， which we call VIO controller。

 V IO controller basically starts reading blocks from the disk and is starting storing these blocks in some memory address that the OS finds available。

So。This process。Does not seem to involve the caches in the procedure。

 Does anyone know why it doesn't need to involve the cache or why。

Do we not need to involve the cast in the pressure？Like， what would happen if。

I would need the processor to handle this operation for me。Right now。

 what happens is that I simply invoke the Io controller and the Io controller decides source the source location of the data。

 which is somewhere in the disk。And the destination location of data。

 which is somewhere in the memory in some free location。

 and it simply transfers the data through a DMA through a direct memory access。😊。

What would happen if I would need to do this path， basically I would need to fetch the data from the disk placed the cachees。

😡，Then from the gas and we need to write it back to to as。And then one。

 so I would cause pollution in the caches because I would need to fetch a very large block from the disk every time I wanted to handle a file back mapping while I would not need to use the data for any other reason so basically it would cause data movement the basic reasons that cause high data movement I would need to fetch data from the disk somehow write in my caches and then from the cache is right back to the memory which is a long path so we sort circuit disk and the short circuit is through the DMA basically。

So when this whole process finishes and the the DMA。

 you can think of it as a separate controller or a separate processor。

 this separate processor is simply responsible for one task。

Coping data from the disk inside the memory。And you can think of it even as a multiple processor because it has many threads that try to do these operations for multiple pluses at the same time。

 so when this thing finishes for our operating system handler。

 it signals the completion and then you can resume the operation in the process。

So the question right now is， okay， I find out my data is in the disk。The physical memory is full。

 this means that I check the list of three physical pages in the Linux， let's say。

 and I find out that it's empty， I don't have any free physical pages。😊。

The question is which physical frame should I replace so I need to take one frame from the memory and send it back to the disk because I cannot afford。

😡，Any free location in the memory。The question is is through LLU feasible。

 so if let's say I have a replacement policy which implements through administration we used eviction policy？

😊，And I have。40gbyte memory with 4 kilobyte pages， How many？Possible Lord theings。My。

I might have and how much data would I need to store to be able to find the trial here。

 the tool industry initially used。So let's say that I need to keep track in my main memory。

 which pages， which page is the least recently used。😡，To be able to achieve this。

 I need to store some metadata， sometimes stamps will say。

And how are the like in terms of timestamps， how many possibilities do I have。

 how many orderings the timestamps？Does anyone have any idea。

Its table the size of corporate the device device。O， so let's the month。So four gigabytes。

 it took the power of 32。What name。And。This I divide with the power of 12。

 which means I have to the power of 20 pages。So and you're saying how much metadata do I need？こござ。

But one bitit is not enough to support here because I cannot show exactly which one is the least recently used。

 right？So I need to express somehow that this one， one of the pages is the least recently used。

That's that's the one approach， yes， but this is not true IU。

 this is some something that tries to approximateU。

I'm talking about a scenario where you have a ground truth， like， you know exactly what's happening。

So imagine that the possibilities I will have is that。I would have。

To the power of 20 different possibilities， right？For sure， and。If I have one specific time stump。

 then I could order this。By to the part of 19 times。Because。Then if I keep one big constant。

 then I would need to change all the other 19 ones。And then if I keep this constant。

To the power of 18 possibilities。So at the end of the day， I would I may have。

This amount of possibilities where n is the number of pages I have in the system。

And if I want to encode this in bes。Then I would need。Which I guess， is very high because。

I think the approximation of this is。And。Look to end。

Which means that if I have to the part of 20 pages， I need to store the part of 20。😡。

Bs just to start a timetamps for a trial review and this is very expensive if I cannot afford it。

So as you said， we cannot afford this， so we need something different like a clock algorithm。

 which is what you said basically。The clock algorithm though that doesn't take into account frequency。

😊，There's another algorithm called the arc algorithm which takes into a con frequency in additional to the clock。

 so let's see how clock works though。So we keep a circular list of the physical frames in memory。

 the ones that are being used， not the ones that are free。

So we keep a pointer to the last examined frame in the list， so for example。

 this is the last examined frame in the list。When a page is accessed， we set the R bit in the PTE。

 so inside the page table， when a page is getting accessed， we set a bit and we're saying okay。

 this specific page has been accessed and then it will inform the OS about it so the OS comes to this page for example and sets the Rbit to one。

😊，Arbit2R means that it has been recently used， that's why it's R so when when we need to replace a frame we do something very。

 very， very simple we start teaching the clock。And once we find a bit which is not set。

 this means that this specific page has not been recently used。😡，And we assume in this scenario。

 for example， that this zero here has not been used and we need to evict this one。

So once we after we tick and we switch the pointer of the clock。

 then we would reset also the bits so that when the next time they have been used we will set them up and make sure that we keep the most recently used behavior of the algorithm。

 does anyone have any questions on this。We can go into detail， but it's。

 I guess very obsolete because the systems are not using exactly this at this point。

The reason they're not using it is because。This specific algorithm does not have the concept of hotness coldness of data。

 so it does not take into account how many times a page has been accessed。

 It only takes into account some temporal window that okay in some specific window we have access this page so you cannot evict it That's the only thing it knows It does not know historical information about what happened in terms of page access to this specific physical frames。

So in terms of cast versus page replacement， you can think again of the analog problems。

Pidage replacement similar to the gas replacement， the page table， the tag store。

 the difference is the following though。When we want to access the physical memory versus the cast。

 we have different requirements， the cast can be accessed at the order of nanoseconds。

The memory can be accessed the order of hundreds of nanoseconds。Second。

 the number of blocks in a class is much smaller compared to the number of pages in the memory。😡。

Also， if I want to run a more。😡，Let's say sophisticated algorithm and I wanted to run them。😊。

reinforcement learning， a supervised learning， a littleM that tells me which pages to evict。

 which is a very relevant research direction also。Then there is a chance that in the operating system。

 I could afford。The latency of the model predicting which page they will need to evict。

Because I need to fetch data from my disk， right， so I can overlap the latency of predicting what to evict with the latency of fetching from your disk。

But in the case is if I want to place an LLM or even a simple forward layer， a fit forward layer。

 then I cannot really afford it because the latency of accessing the cast is very comparable to the latency of。

 let's say， even accessing a two layer neural network。😊。

So this toler amount of time to find the replacement。😡。

It's very important to design more and more more intelligent policies on how to evict or fetch data prets data from the disk。

Should we do a break？Okay， let's take 10 minutes， yeah。咁是。Yeah yeah， for sure yes。

 if the programme was trying to access something else。啊，对。This can also be a major page fault yes。

 I'm touch here about the scenario this the system really is also as a major page fault。

 but imagine it as a branch where。The pa system treats it initially as a major paid fund。

You try to touch' something that you don't have access to， let's say。

But if you do not have access to this， it's a segmentation fault， let's say the car says， no。

 we don't have access to it， I cannot do anything， which means it's aful。

And the other con the other scenario is that you have access to it and I need to share it for you。

 so I need yes， yes。We had of this already in our computer archive computer engineering Yeah。

 I quick week， Yeah yeah。I will go into more recent this type of lecture a bit in a bit。Yeah。Okay。さな。

This。Yeah， sure。 So wanted to ask about the pitch table。 Yeah。

 So why do you need to have necessarily one to one happening between in and physical。

 Is it very nice to assume that the frames are beside you each other in physical memory like。Yes。

 it's common。 Yes， and there is a whole research direction with that。

 this is called a continuity based mapping。 So instead of not just the offset yes， that's a。

 that's called offset based translation。 So what they。Do。Its the following leg so as you said， right。

 you have virtual pages。Which are contiguous。IfVOS somehow manages to give you the corresponding physical pages to be contiguous。

Then as you said， you can create this mapping。And have an option。Oh， once you know。

The index of the virtual pages， you can easily。Calculate using the offset。

 the index of the physical page。 and this is a legit technique。

 which the transaction will be extremely cheap because you can just Yes， exactly。

 The problem is that you cannot easily find in the system contiguous memory。

 the problem is that even though your virtual memory is usually contiguous when you allocate an array。

 let's say the physical memory。 you don't have guarantees that will be contiguous。

 The is trying to optimize it to be contiguous， but you don't have such guarantees。

 I know at the end of the day wouldn't be still cheaper because you don't store as much Like imagine if you store for each physical memory address one offset because there is no it's a tradeoff still the same as you it's comp。

 but it's a trade off。 and I will explain why。If let's say we need to store a thousand offset， Okay。

 think of the following。I have a thousand0 offsets。And I have a virtual page number。

And these1 thousand offset， basically。不。Okay， so we talked about how we can allocate physical memory and store the plate table to basically keep track with a virtual to physical mapping。

 but virtual memory plays a secondary role in modern system， which is that of memory protection。

I'm going to go quickly through that， so we have multiple programs which run concurrently in the system。

And each process has its own paid table。And its process can use its entire virtual larger space without worrying about what other programs are doing in the system。

 so a process can only access the physical base， which are mapped in its page table and cannot overrite the page table of another process。

So this provides protection and isolation between processes。

It enables access control mechanisms per page。So you can see an example here。

 we have its process which uses its own virtual lot space。🤧And in this context， we have these two。

Viual other spaces with two virtual addressP2 and VP1 which point to the same physical page number seven in this context the physical page number seven is a read only library code so we have two applications with load Tensorflow let's say two passing and processes and Tensorflow is a read only library called library code we cannot write on the public。

 but somehow we need to show how the page table and the visual memory can help us avoid the sort of rights to the physical page number seven which is the Tensorflow which is our library which we cannot write。

😊，And this is done via access control the access protection control and we have page level access control so the not every process is allowed to access every page we need some sort of privilege to change this。

Pmissions and being able to access system pages。And we may not also able to execute instructions in some pages if you have seen this sort of stack overflow attacks where I can port execution program inside nice stack and make it execute and this is basically a very modern and powerful attack。

So the idea is I need to store the access control information on a page basis in the process page table。

 and we need to enforce this access control as the same time as translation so when I figure out the virtual of the physical mapping。

 that's where I will find out whether I have access to this page or not。

So the virtual memory system serves， as we discussed two functions。

 one is the other translation for the illusion of the very large address space and the access control。

😊，This also could be decoupd， it doesn't mean that the only way to store this sort of metadata。

 the access bits can be done through a virtual memory， it can be done in other ways as well。

So how does it work with virtual memory， though， we extend the page table entries with permission bits。

😡，So we check this bits on its access and during a page fault which comes here。

 so if I check during a page fault that these access bits are not set for my page table。

 then I simply go to a segmentation fault otherwise I go and proceed with the allocation。

So if we violate these axis bits， then we generate an exception。😊，In this example。

 the physical page6 process I tries to access the physical page number six and it cannot write it and does why can't it not write it because process J is the only one who can write it if both of them could write it then we could have synchronization problems。

😊，These are the privilege level next 86 we have something called protection rings。

 so we have applications which are level3 right now when you run your applications at level3。

 some operating system services which are not used mostly in the kernel and we have level zero which is the operating system code so when the operating system runs in zero this means that it has almost all permissions in all physical pages。

😊，Yeah this is not very important so we have two levels of the page we have these are the two last levels of the page table in XA6 systems and as you can see the last from the end the PDE pay directory it stores some additional bits here which encode these access protection bits。

😊，And these are the flags basically so a part of it contains the address in the physical memory another part of it contains the flags basically in this scenario the PD doesn't store directly the address to the physical memory。

 it stores the pointer。😊，To the P， to the last level of the paid table。

So it startss the pointer to the last level of the page table and it has some access bits。😊。

The last level of the page table， the PTE it stores the address of the  four kilobyte page frame。

 the last frame in the page table and again some axis bits the difference between these two axis bits is the granularity that they have been stored this is stored of the 4 kilobyte level this is stored at the2 megabyte level these flags can capture two megabyte large regions and not specifically4 kilobyte large regions。

😊，I will show you the example so here if I would let's say this is the page director entry right and if I wanted to make the user。

Perform a readr operation。And the page table entry says that the user can perform and readdirectite operation。

 then it would result in a readrite because both the PD and the last level page table entries agree that in this specific page。

 the user can have readwrite。😊，But。In this in the PD for the second entry。

 let's say we have read only access permissions， so at the 2 megabyte granularity。

 I'm saying you can only read these2 megabytes。Segment。However。

 the page stable entry says I have readrite operations。

 which means I can readrite to this four kilobyte entry。😊，However。

 the PD overrites the 4 kilobyte a permission and enforces a read only behavior。😊。

It's a hierarchical protection scheme if I associate access control bits to the higher level frame。

 the2 megabyte frame， then everything that maps to it， the2gate。

 the whole2 megabyte region would not be able to being accessed because these are overwritten overrite the four kilolobyte ones。

😊，So let's say that your hardware is unreliable。😡，And someone could flip adiac protection bits in the page table。

And this way， if you flip the access protection bit so that you can， for example。

 take access in terms of supervisor level access， you can read， write， execute anything you want。

How do you do this by flipping the access control bit from the user to the supervisor so your page frame was saying。

 okay， this is a user space page and you switch this bid， you flip this bit and you're like， okay。

 this is the supervisor page。So first， can this happen。

 do you know any way that this can happen that I can flip a bit？Somewhere， yes。Yes。

 one way is Rohammer， so if I could find the location。

Of the data inside the memory and flip the bits of the page table。Then I could do two things。

 either I would change the access control bits number one， which means that I take over the system。

Using general level privileges。This is not a STM attack， though， because I become the supervisor。

Or second， any other idea， one is changinging the a control bit。What's another way？嗯。啊。嗯。这是。

virtualirtual green。Yes， exactly so another way。I that I change a physical frame number and I can map a virtual page anywhere I want in the physical address space。

 this might not give me escalation privileges， but it gives me possibility to read right to every potential physical location which could be a huge security problem。

😊，Some other issues in visual memory。Again， how large is a Pe table， how do we store and access it。

 we discussed a lot about this。😊，How can we speed up other translation and access control check。

 this is what we will focus on this section of the lecture and when do we do other translation in relation to the CA access。

 that's not very important and I will probably skip it。There are many more issues。

 how what happens in a context suite， how can you handle multiple memory sizes I will give you an overview of this。

First high large is a page table， I think we discussed a lot about this。

I don't want to go again through that。So I will focus on the second part here。

 how can we speed that other translation in the access control check？

So how fast is the other translation， how can we make it fast？

We need to use a data structure at the hardware level that castes pagetable entries。

And reduces the number of memory aes to look up the page table。

So I do not want to look up the page table a lot， I want to somehow fetch the page table entries that I need so that I figure out quickly the physical location of the data and the access control bits。

So if you remember the figure before， there is a memory man that's been used that intervenes right now between the page table and the core so when the core ships the visual address。

😊，It ships it to the memory management unit， the memory management unit imagine it as a pure hardware component。

😡，That is responsible for performing other translation as quickly as possible。

It does this by fetching the page table。😊，And then storing it somehow so that we don't need to probe and look up the page s every time we perform a memory axis。

😡，And then many management many units。Is one per core。

 its core has its own memory management unit because remember that its process running requires a different page table。

 so it could not mix up page tables in different memory management units。

It has3 key components first， the translation look aside buffers。

 the translation look aside buffer im there's some sort of cast。😊。

That CAS recently used Vi physical translations， I give you the visual page number。

 you give them back quickly the physical page number I do not need to walk any page table。😊，Second。

 the page table classes， if you remember we had hierarchical page tables。

 we had four levels of paid stable。So the paid table classes gives me access。

 quick access to the point I chasing。So that I can skip walks in the page table I directly find the pointers to the next levels。

😡，And the third is a hardware page table worker， let's say that I don't find anything here。

 I mentioned the TLBs， I do not have anything in the page table Os I somehow need to look up the page table in hardware so imagine that this is an FSM that accesses the different levels of the page table to fetchs and work the page table and the end of the day fetchs the require a page stable entry I will go in detail into this。

😊，So this is an example memory management unit that is in modern Intel processors。

 so you have two TLBs， one for instructions and one for data。😊，And then if you're missing those。

 then you have an L2 unified TLB that serves translations for both instructions and data。

If you miss also an L2 unified TlB you go and probe the hardware page stable walker。

 the hardware page stable walker simply starts generating the addresses for the page table if it finds any address in the page stable or casess it means that it can quickly do the point of changing without going and touching to the memory hierarch and fetching entry yeah it's inside the CPUU imagine it。

😊，I'll give you a broad perspective。So in your CPU， maybe you talked about it。

 there's something called a load store unit。Its not for cute， sorry。Okay。

 so here when you perform loads， you basically。It's a feefall， let's say。

 and here you have a Q and you have an element， let's say let's go it a1。

This A1 cannot be directly sent to the CA because this has a virtual address。

So what you need to do is you send day one first。To the MMMU。

TheM mu contains what we discussed like it contains it's these structures were exactly。And。

You send the request using the Vi address。To the Ca， to the L1 Ca， L1 D。即。

But you cannot access the cash until the MMU。😡，Send you the physical address。

They're trying to overlap a bit the latency here of accessing minimum during the CA I was also later。

 it's not that possible。But yes， the cast axis cannot be performed unless theM sends you the physical address。

To see if it's stored in the cash flow。No， but like this will give you yeah， yeah yeah yes。

 it will give you the physical address then you will check is it in the cast or not or not yes you continue down the hierarchy you might face。

😊，But in the meantime， before you generate the physical address。

You might already access the memory hierarchy to fetch the bytable enters。

So it's not a single axis eventually in some cases。

And the translational look as I buffered the idea is to cast the page stable entries in a hardware structure in the processor。

 speed up translation， so it tries to cast basically the most recently used page stable entries and this way we reduce the number of memory access required for most instruction fetchs to only one TLB axis so we need to do one TLB access for most entries and then at the same time fetchs the TLB entry supply to the L1D and perform memory access even if。

How does this work， you can imagine it's the same analogy as cachees in this scenario we use as index the lower bits of the virtual page number as taggged the unused bits of the visual page number plus the press ID。

 does anyone know why we need the press ID。Like why can I not use directly as a tag。

 the unused bit as a visual page number？There might be saying similar name tag across the different tables for each process yes。

 but okay， but I'm running my process right now。Let's say that I am running my process and I there's no chance that I will place something that it be。

 which is not coming from my process。Think of a context with， though。

Let's say that I switch the context and I fetch another。Process in this scenario。

 if the VPNs were the same， I would have an analyzinging problem。

This is related only to context switches， this is not related to the current execution model。

If I need a contact switch， I cannot have sta entries with the same virtual page numbers in my TLBs。

 that's why I need to store the Pro ID because I will compare the pro ID and see， oh。

 is this coming from my pro ID or another ID？But the TLB is small。

 it cannot hold all the page table entries and some translation requests will inevitably miss in the TLB。

So we must access the memory to find the required page table entry。

 this is called watching the page table。This has large performance panels which I will discuss later and better TLB management and prefeing can reduce the TLB misses the question is who handles the TLB misses？

Like who walks the paid table， that was a research question。In earlier years in the 19。

 let's say 90s， people were doing differently the page table compared to how they're doing it now。😊。

The big question is， do I work in hardware software？

The first approach is what is happening right now in the systems， which is hardware managed。

The hardware does the page table work， which means I have a ship picture here and the。

There is an FSM in my core， it simply sends requests to the memory hierarchy。

 fetching all one by one the page stable levels。😊，And this is done transparently the system software。

 I could have many of these working at the same time if five requests miss in the TLBs at the same time because I have parallels in my core。

 then I could be able to walk five not five page steps I could walk for five different misses in the TLBs。

When this is done transparent to system software， I don't need to wait for any sort of software to satisfy the t be missed for me。

The second approach is a software managed approach， so instead of having an FSM here。😡。

I raise an exception。I basically。Inform the operating system that okay， look。

 I have a missing in the DLB and somehow you need to find for me the final page table entry and I cannot walk the page table so you need to do everything in the software。

Can anyone think what are the problems with this what are the let's say advantages of this first what would be the advantage of having an exception here and letting the OS decide？

How it would access as the page table。Examply， it doesn't have to go one by one if could probably you know。

 figure out some smart way to jump across exactly， which offers what？Like， yes， essentially。

 it's this。What you describe though， it's some sort of flexibility。

 like I could do whatever I want with a page table， could organize it with three levels， two levels。

 one level， it's whatever I want。If I fix the hardware to do the work。

 then I need to have four levels， I cannot change anything。

 cannot do any formalization with respect to that。But if I let the Os decide how to work。

 then the OS can basically。Do the paid stable work without caring。😡。

About what the hardware assumes about the page table。

 hardware doesn't need to assume anything about the page table， because at the end of the day。

 it will receive the paid stable entry from the operating system。

So the advantages of the harder Man still be though are superior I think to the sovereign managed still be miss。

 so if we have a harder managed still be miss， then we don't have an exception and the exception is something very。

 very expensive because when we have an exception we need to invoke the whole operating system stuck to handle the tailB miss。

The second key thing is that when we launch an exception， we need to stop the whole process。

 the whole process waits for one specific TLBs to be resolved。However。We don't have flexibility。

 we cannot decide the paid stable structure because we have a specific worker in our ISA basically it's part of the ISA have a worker that walks the fourleve paid table for example。

 X64 systems if the OS decides that this doesn't work anymore and we need a different type of worker it also fabricate a different CPU for this type of paid table。

 which is not very nice because we need to pay thousands of dollars and fabricate new CPUs for every optimization that the operating system does。

In the case of the software managed TLB， the can define a placetable organization。

 and we could also have more sophisticated TLB replacement policies because theOS would take over it would replace data to the TLB in whichever way it wanted。

However， we need to generate an exception an exception and if we want to generate exceptions。

 we may have very high performance overhead， we need to fl the pipeline hand exception。

 we need to bring instructions from the operating system to be executed and in general we underutilized resources just for a single TLB miss。

😊，In this specific M we have as discussed before two L1 and TLB。

 we have an L1 deta LB an L1 instruction TLB。😊，In the L1 data TLB。

 it doesn't have only for one page size， plus three page sizes， 4 kilobyte。

2 megabyte and 1 gigabyte pages， so it has essentially three L1 data TLBs。

 one for 4 kilobyte pages which is much larger， y is much larger because with 4 kilobyte we can cover less in terms of memory。

😊，A smaller one with2 MBgaytes and a much smaller one with  one gigtes imagine though that this oneab the four entry。

 one gigte one it can cover up to 4 gig， so if I could map I could use pages which are one gigab。😊。

Only with four entries I could cover 40 Gabytes of memory while the 4 kilobyte 1 doesn't cover as maths as even this theomicgayte multiplied by 32 entries。

Of course， these have different latencies， for example， right。

 because if I would make this this is full elastic。

 which means it has a bit higher latency compared to having many entries， for example。😊。

So this visual all the physical mappings that I discovered that we discovered during the page stable work process are inserted in the corresponding TLB after a TLB miss and during a translation request all three TLBs are looked up in the parallel how does this happen？

😊，We assume different indices and page offsets for the page offset of 4 kilobytes。

 we will use the tag that corresponds after the 12 the 12 bits for the offset。

For the index of two megabytes， I will use only this part that corresponds after the offset of  two megabytes for the one gigabte I will use a different offset as well。

So we probe we look up these3 TLBs in parallel to find out if our page is mapped by a 4 kilobyte physical page。

 two megabyte physical page or one gigbyte physical page。

 it cannot map to all of them at the same time， these are exclusive so if something maps to 4 kilobyte pages。

 you won't find it anywhere else。😊，So the TLB axis becomes a races。

 whichever one of these fetchs is the data， first it will basically give you back a translation。😊。

The toify TLB works a bit differently though。😡，In this scenario， we have two separate TB structures。

😡，One for four kilobyte and two megayte translations at the same time。

 and one for one gigabyte pages。So the key thing here is that we have 1 L2 TLB。😡。

With two page sizes at the same time， we can start two different page sizes。And the question is。

How can using a single hardware structure？Have both page sizes because before I could assume simply different offsets and access them in parallel right。

 the question is how can I insert in the same TLB different tags basically？

Does anyone have any idea of how you can do this？And you just indicate in the beginning， okay。

 this is going to be a four kilowatt page and then I yeah but but if you do this。

 then you need to access so your tag， the formation of the tag forming the tag depends on the page size if the page size is4 kilobytes。

 which is an assumptionion because you do not know this yet， you form a specific tag。

If your page size is 21 to the part of 21 which2 megabytes， your tag changes。

 so you have two different tags that you need to check。

So the way this works is by simply performing two accesses to the L2 TLB。So first。

 you assume the page size is 4 kilobytes。😡，And this way you calculate the index bits and you access the L2 TLB。

 assuming this is the correct page size。😊，If everything matches and the tag matches。

 for sure it's a hit。😊，Because you're tax months， so the paid size should be 4 kilobytes。

If the tag does not match， then you need to go to step  two。😡。

And you assume that the page size is  two megabytes。

 you recalculate the index you recalculate the tag and you access L to tLB again one time one more time。

 so if the tag matches then means it's a two megabyte page if your tag does not matches in L to tlLB miss and you didn't find the data there so the general algorithm is that if you have n page sizes you recalculate the index based on the different page sizes so that you can find out basically sequentially which is the correct page size your L to tlB。

This is called asciivity in time， it's called pseudosociivity basically where I do not have associivity inside the cast block。

 let's say but I simply change my index and search in different indices for the same cast block。😊。

How does this work？😮，We have the1th and the 14th beat to index the 4 kilobyte page in this scenario because we have four sets。

😊，So we find out we set first in the set number zero because its numbers are zero。

 and we find out that data is not there， like the tags do not match for set zero。

Then we change the index because we use the 21 bits， the 2 megabytes offset。

And in this scenario the 22nd and 23rd bit indicate the index into the L2 TlB and the second index we're going to look at is the set one is the one that corresponds to set1 and you might find it for example in set one in this scenario and if you don't find it using this inices then this means that the data is not in the L2 TLB。

Whether the pros， it a simple and practical implementation， but we have a verying L TlB latnt。😊。

If you find your data using the first offset， which means assuming the 4 kilobyte page。😡。

You find it very quickly because you do only one axis with the L2 TLB。😡，However。

 if always your data is mapped to two megabyte pages。

 then you need to do one access to missing the 4lobyte frame。😡，For the firstlobyte offset。

 and then you need to perform a second axis so that you can find the2 megabyte index。Also。

 you also have a slower identification of L2 BB miss if you always missing your relative willB。

 you always need to perform。😊，Two sequential axises to B to TlB。😊。

And one optimization is to perform parallel lookup。

 you basically calculate both indices and both tags at the same time。

 you look up both for both page size， what's the problem with this requires more hardware because I need two indices。

 two row decoders for example， at the same time to be activated and tell me whether the tag matches or not。

😊，Second is page size prediction and there is some work on people who are trying to by people who are trying to optimize for the order at which you access the TLB by predicting the page size。

 so if you know that by 9 99% of the cases，Your data is mapped from 2 megabyte physical pages。

 then it makes sense to start the LttLB lookup process by assuming a 2 megabyte page size another assuming a4 kilobyte page size because you know in most of times you're going to hit using a 2 megabyte page size。

Then we have the hardware replaced stable worker， let's say we missed right now the TLB。😡。

And we have a per hardware component again this perMMU that walks the multilevel page table to avoid expensive context switches and software handling it has two components the state machine that is designed to be aware of the architecture's page table structure and registers that keep track of the outstanding TLB misses this is how it looks like so imagine you could have for each one of these registers you could have one different state machine that walks the page table in parallel basically for each one of the TLB misses。

😊，Other is help quick that avoids the need for context switch on TLB miss and it overlaps the TLB misses with useful computation。

 it also supports concurrent TLB misses。😊，I will show you an example later。

The disadvantages has hardware and power hardware area and power on versions and second limits flexibility compared to having a software based by able work。

This is an example， the page stable of accesses the CR3 register that maintains information about the physical address of the route of the page stable of the first level。

😊，And then concatenate the contents of the CR3 with the first language。

 which of the visual address is the first step that you take， right？😊。

So the hardware page St looks allows overlapping TLB image with useful computation and I'm going to show you how so you have this load for VPN equals one and then you have the TLBM so normally in systems with software based TLB mishandling。

 you would contact Su， you would run the page St process in the OS and then you would continue with your next loads。

😊，And after you load B， which is VPn equals5， you have a D sheet， everything's fine。😊。

But in the case of the hardware page tableby work here， what happened the following。

 you again try to load the PN1， you have a TlB me。😡，And at the same time you can start your load B。

 why because here the page stable walk happens without the requirement for switching to the operating system。

 so in parallel I can satisfy load B which hits in the TLB and this way I save very critical cycles in my pipeline。

Is that clear to everyone？How this done？So the paid table walker just can do remote。Yeah， for sure。

 but this is not even a paid stable worker， this is not even a paid stable lock is a hit so it doesn't stop my pipeline essentially。

I can send more requests without。those the same timeThat's also true。 That's also true。 Yeah。

 this is whats happening here No， because this is a hit， right， This is not a miss。 hit Yeah， yeah。

 yeah， yeah， sure yeah。Yeah， it basically does not destroy the parallelism。

 which is destroyed here because here I cannot run anything else regarding the which has to do with a user space application。

And the pagework classes， which are simply stored translations from the nonle levels of the paid table。

 store some translations from the intermediate levels and the very low laency so who can have access to the initial levels of the paid table。

So the question， some questions which are。Key for low level designs。

 but I don't want to go deeper into them right now is do I do translation before or after or after accessing the L1 Ca which is related to what we discussed here so there are multiple ways to deal with that you could tag caches with visual addresses you could also tag cache with physical addresses and there are different。

Overheads a different sort of phenomena and problems that you deal when you make each one of these choices。

I don't want to go deep into these， we can discuss later or you can take a look on your own。

 mainly there are three different concepts。That's the simplest one in what most systems are using。

We have a TLB， which is no， this is not the one systems're using。

 this is the one systems we're using。The naive solution。

 I simply wait until it gives me the physical address and then I go to the cache。

 I supply the data to the translation of the cash。Another way is that I have a virtual cast。

 I access the cast using virtual addresses， and I only translate when I need to go to the main memory to the physical memory。

😊，And this is what's happening in the system right now。The TLB is done。

Is performed the LLB axis is performed in parallel with a gas axis。

 and I am able to access part of the cast， I can overlap some latency of the ca using the virtual address。

 but I'm still waiting for the physical one。😊，Which means that。I can for example。

 calculate the index in the cast using the visual address。

 but I cannot still know the physical address which means I don't know which word I'm going to load from the cast so I'm trying to overlap the latency of access in the TlB with the latency of access in the cast so if the memory is stored the cache otherwise if it's not the cache parallel already searchinging up in the rest of the yes。

And let's see right now how the virtual La system has evolved。😊。

Back in the years we had a software paid table worker we only had two TLBs one data class I mean we might have more than one data class but right now this is what's happening we have two TLBs we have the paid table cases paid table worker and this happens before we have we perform the L1D axis this is what。

Many of your phones have， for your phones， for example。

 have a very high number of TLBA entries compared to your desktop sheets probably have a very small number of a very low number of TLB entries and you can see the different design decisions here because。

The apple is using a 16 kilobyte large spa size by intel D and arm are using a 4 kilobyte base page size and these are all different。

This all pose different tradeoffs。And when it comes to virtual memory research。

 how much time do I have？😊，对没 you。This is the work we presented in As 2025 it's called Viwa enabling fast and accurate virtual memory research with an imitation based operating system simulation with aology。

 so I'm going to walk you through basically the virtual memory overhead first so we have GPUs CPUUs and network interface cards in the system right now which are all using virtual memory。

So as you understood from this lecture， virtual memory is a cornerstone of modern computing systems。

But it doesn't come for free， as we discussed。So virtualley causes very high performance overheads。

Because of two reasons which we discussed today， one is memorial allocation。

 so when the OS wakes up and says okay， I need to allocate data， then we pay a price for it。

When the processor needs to translate the addresses。

 we will also need to pay a price for the performance price for it。

So when it comes to memorial location overheads， we have this emerging workloads。

 functionality as services， sorted sort output， put large， language modeling inference。

 which are very short running and they also have a high spawning throughput。

So we spend a lot of time on the OS allocating memory。

Well we spend a lot less time in executing the workload。

 which means that we're spending more time in the OS。

 which cannot be amortized by the execution of the function。

So you can see in this plot in the Yx is the fraction of the total execution time that the physical memorial allocation takes across different short running workloads。

 and you can see that， for example， 32% of the execution time which was measured in a real system。😊。

You spend on physical nu locations， so these workloads。😊，From the 100% of their total execution time。

 they spend 32% of the execution time on allocating me。Second， we have a second class of workloads。

Sparse machine learning by informmatics workloads， graph analytics， databases。

 which have very large data sets， that are very long running and they also have a regular memory axis。

 they have lots of pointer chasing。And these workloads spend a lot of time for TlBes and page stable walks leading to high high address translation。

😊，whichch basically slows down fetching of the data。

 we need to wait for the other translation to be resolved because before we go and fetch data。

And in this plot， I demonstrate the fraction of horizontal execution time that other translation takes in many data intensive irregular workloads。

😊，And we show that on average， 26% of the execution time is spent another translation。

So putting everything together， we have these diverse workloads which have diverse overheads。

 some of them are facing overheads because of the minor paid faults in this scenario。

 we need to allocate memory for this workloads and some other workloads spend their execution time both in allocation and other translation。

And the virtual me overheads are expected to increase also as we transition to much larger physical other spaces。

😊，You might have seen in modern systems that are using unified memory between GPUs and CPUUs。

So we have a GP memory which has high bands within limited capacity， CPUU memory with high capacity。

 low cost per bit， and they're trying to cooperatively work together to run， for example， LaLLs。😊。

We have direct storage axis， we have high NSDs， and we have a bio addressable interface with which we can access them quickly。

😊，We also have memory segregation， we have a CL if you have seen devices that offer us the possibility to access remote memories connected somewhere in the system。

And researchers tried to save every day by proposing different techniques that design at the same time。

 the operating system and the hardware to reduce these operations。The first solution。

 software management still bes。So there are multiple works which's proposed using a software managed at CLB。

 and what do I mean by that？As I showed before， we had the L2 TlB， which is at the hardware level。

 and there are some words which its proposed at the MMMU using keeping the L2 TLB at the hardware level。

 but when we have a M，😡，We access a TLB， a much larger TLB， which is stored in software。

 you can think of it as a minipa table that stores the most recently accessed Ps。

But it requires continuous space in the physical memory。

 so we need to reserve space in the physical memory to store it， which sometimes it's not possible。

 so we need to basically prereserve space for its process for the software amount still big。

Another way as we discussed is leveraging visual address to physical address contient there are many works which as I discussed with your colleague。

 they try to demonstrate how we can allocate virtual addresses and physical addresses in a contiguous manner so that I can do offset- based translation I can simply using one offset。

 figure out where is my data in the physical memory， I would not need to access the page table。😊。

There's also another type of solutions that try to accelerate the memorial location。

 there are a bunch of works which are like okay， no we're not going to do the memorial location at the operating system level。

 I'm not going to have an exception I'm going to have a hardware unit there that does the hardware that does the memorial location for me so I do not need to stop and context switchs the operating system。

😊，There are also works that demonstrate how you can use alternative v mappings， for example。

 half space mappings and in this work we showed in microd 23 that you can have。

Both are restrictive and flexible mapping in the system at the same time， which means that。

You have two segments， a restrictive segment and a flexible segment in the system and your restrictive segment when you want to map pages to the restrictive segment。

 you take the virtual page number and you do something very simple。

 you has it so you has it and you find out directly the location in the physical memory。

In this scenario that has function says that okay， this virtual page number will always map them page the number four。

 so we break the fully associivity nature of the virtual memory。😊，This offers fast translation。

 but limited universal member functionality， is because I cannot place my page wherever I want。



![](img/6f52fa76af7cc3905b36b97461096cae_6.png)

But that's why I'm also employing in the system flexible mappings， which is what we discussed today。

 it's basically the classic conventional system where're using a page table to map wherever I want in the physical memory and this offers it basically supports my virtual memory features but as we discussed at the cost of higher latency other translation。



![](img/6f52fa76af7cc3905b36b97461096cae_8.png)

Another way of dealing with the problem is refining the stable design。😡。

As you might have seen in your C courses or data structure courses。

 you could use a hash based page table， not a multile based page table， like a RAs based page table。

In this scenario， you might have a collision though。

 so you might go to the has base page table and you find out that okay the virtual page number does not match there。

 so I might need to jump to a different basically entry of the has table using pointer changing and then if I do not find my data there and I have another pointer here and I need to do a series of pointer changing operations to discover the mapping。

Some people have shown that this is beneficial in some cases that require only a few number of access to the plate table。

This is called chain， this technique is called chain。And this paper that proposed okay。

 we're not going to change what we're going to do is the following whenever we have a collision。

We're not going to change。The page table entry using linked lists we're going to simply look up the next entry after a collision so when we have a collision we go check up the next entry and you're like okay does the VPN mats here no okay we look up the next entry have a collision again okay then I needed to perform four axises in this scenario inside the same page stable without performing pointer chasing to figure out my translation。

😊，Another way would be to use elasticastic page tables which have been used a lot in databases and in this scenario to improve parallelism。

 I check up four， three， four， five page tables at the same time。

 has tables at the same time and if I have collisions in some of them I might find my data in one other one in another one that doesn't have a collision。

Why is this good because I can perform multiple memory access to different tables。

 which is much better than performing the sequential pointer changing to theeric space space table。

 for example。And the most relevant to you and to the systems you're using right now。

 it's the transparent huge pages right now systems use transparent huge pages。And how does this work。

 we use furlo bio and2omegabytes at the same time。And the system Linux tries to substitute the 4tabbyte pages with  two megabyte pages。

Based on two facts， do I have three to megabyte pages number one is the application going to benefit from it if I do this？

😡，And imagine there is a demon working somewhere in the kernel that tries to create two megabyte large pages for you。

 and this was introduced in 2011 by Andrea Aanelli， who is right now。

 I think a distinguished engineer in in。This is the physical an layout。

 the red ones are 4 kilobyte pages， but as you can see。

 transparently the OS uses also internally some2 megabyte pages and it doesn't need to inform the user about how the virtual pages are mapped to 4 kilobyte or 2 megabyte pages。

😊，The advantage is that if you use2mgabyyte pages transparently will reduce the size of the page table because its page stable and it can cover a much larger amount of memory。

😡，A single Tb entry can up a larger amount of memory。

The problem though is the internal fragmentation， we might reserve a 2 megabyte region。

 but the user does not use it， which means that we increase internal fragmentation。😊。

Also say if we want to move pages around to make space in the physical other space。

 then we need to pay a higher price in terms of latency spikes to move data around and this can take a lot of time and create。

😊，Performance overheadheads in different applications。

These are some resources I put here some the oldest book well the oldest。

 but like one of the most out to date books of the Linux channel which is very useful for courses or whatever you want。

 this is a new one this from a naracical engineer， this is very useful。

And this is one of the lectures that basically helped me understand how transparent speech pages work you cannot find lots of documentation for this。

 so this is a very good explanation by the creator of it please。😊。

We all have this arsenal then of techniques that can reduce virtual old memory overheads。

The problem is that we want to effectively evaluate all these techniques。

 which is very crucial for the domain。But they are challenging in the evaluation because as we discussed whistle memory spans across the stack there is a hardwareM view。

 there are different system components like the disk there is software level memory management somehow there is a very intensive interplay between these components an example the page stable size depends on the device allocation policy。

😊，If the OS can provide many large pages， their page table size remain small。😡。

If the OS channel cannot provide two megabyte pages because internal fragmentation is rising and applications don't benefit。

 then the page table size becomes larger because I only need to use 4 kilobyte pages。

So this I will skip because you have not been exposed yet to。Main memorial。Yes。

 but evaluating the interplay between these components is critical。

 especially when we want to assess kind of new virtual memory techniques。😊。

And researchers have architectural simulators at their disposal。We do in classes。

Aulation based and full system。There are many em based simulators which you have used probably like aulator or something in your lab。

 they offer high simulation speed， focus on microctorural features。

 limit support for experimentitives。And analytically estimate virtual memory overheads。

They basically try to use some mathematical functions to evaluate the virtual memory overhead。

 they do not have proper components like an MM hero or the page table in this scenario we demonstrate that assuming fixed cycles for these components and latencies does not work well because there's a highvari in the system when it comes to page stable latencies in this plot will demonstrate howvariabilities across different workloads。

It can rates from 33 cycles up to 12084 cycles， I can only set a start fixed value to assume the page table of latency。

And in this plot we demonstrate also the memorial location latency to design。

 so one I allocate both2 mebyte and 4 kilobyte pages and then wanted I allocate only 4 kilobyte pages and we demonstrate that handling the latency of handling the memorial location invo the West allocate pages for us exhibits very high variable。

 again， we cannot have a fixed way of dealing with these latencies。

Then we have another type of simulator， other type of simulators which can basically enable the execution of a full blown operating system on top of a hardware simulator。

😊，They have very low simulation speed and they're very hard to develop。

 though that's why we won't have them in your labs。😊，Yes。

 if you wanted to develop something with Gen5， it would take you three months。

 so that's not going to happen。So we tried to bridge basically this dichotomy simulators and our goal was to create a simulator which had higher sim speed and higher accuracy in estimating these virtual memory overlls and that's why we introduced it to also the simulation framework that you can enable basically evaluation of both the software and hardware components of the virtual memory subsystem。

😊，It used a lightweight user space kernel， written a high level programming language。

 you do not need to change the operating system in Linux C。

 so you can only choose the OS modules related to your desired research， the Pay St design。

 the memorial locator。And the job of the penguin is to try to imitate the full blown operating system as much as possible and as close as possible。

How does it do that it takes all the modules， we took all the modules saved the operating system。

 the full blown operating system， and we are related only the ones which were needed for our research。

 then we tried to replicate them in a high level programming language。

And we came up with this simulation based simulation methodologies that offers rapid development。

 high simulation speed and accurate evaluation。So I won't go into the details of how it works because I will go into details how it works in your lab。

Wwhich I'm going to explore， we're going to discuss the whole infrastructure。

 I'm going to give you basically a full blown tutorial on how to use it。😊。

It's not going to be the next lab， it's going to be the next after the next lab。

 I think it's going to be the fourth lab。诶。Yes， but it has many module read C plus plus you can find more details in the paper。

I don't want to go into these details。Yes， and in the paper。

 we demonstrate how you can use a simulator for different use cases。

We have five use case in the paper again I'm going to go through two of them in the tutorial that we're going to have together。

嗯。Probably your lab is going to be about one of these two。

 it's going to be about either evaluating different page table designs or evaluating different memorial allocation policies。

I'm not going to make it very hard， so because the simulation is hard these sort of simulators are hard to work with when you need to change both the hardware and the software。

嗯。嗯。Yes， it's open source， you can already download it if you want。

 you can find the slides and the slides the Gitthub link。

You can find those documentation have we have written some sort of documentation you can use to get started and getting to know how things work。

 running your first examples。This will be very useful like again for the lab。And in conclusion。

I love going go。As a summary， R memory gives the illusion of infinitefin capacity and we have the page table load maps。

 whistle pages to physical pages， the MMU and the TLB try to speed up the translation process and we have the multileve page tables to keep the page table size in check。

😊，We showed also how you can use these transparent pitch pages to play around with the page size transparently from the user and how you can use different page tables for different programs that provide different memory protection。

There are many things in visual memory like visualized environments， hypervisors， which cannot cover。

 for example， visualized environments， you have two levels of other translation because you translate from the guest toOS to the host to S to the physical memory。

😊，You can find these works which are very interesting which one work we did in East with published studies 20。

 it's about how we can rethink virtual memory and how we can change the whole other translation pipeline and allocation pipeline to perform more efficient other translation。

 one of work that we did in microcro123 that shows how we can use the entire Ca hierarchy to Ca TLB entries we don't just use the small TLBs in the MMU。

And as you have observed， like visual memory is one of the most successful examples。😊。

Of architectural support for programs， I think it's the first time。

 I think in the 1970s where people decided to co design hardware and software together to and this has remained since then so it's basically a fundamental part of computing systems。

And going forward， how does it scale， we will have much larger physical memories。

 we will have hybrid memory systems with DRM， SSDs， nonvolat memories。

 we have many accelerators in the system which are trying to add their physical memory。

 and we have virtualized systems especially in data centers which where people need protection they need to run their data in isolation。

You can find lectures on ritual memory。Yes， true。 I forgot this it's the last slide。

 so it's just there。It's a wrap of the lectures here on the virtualwood Memorial。

And if you want to do research on this， feel free to get in touch and let me know about it。Thanks。

这个带。Sorry for taking more of your time。

![](img/6f52fa76af7cc3905b36b97461096cae_10.png)