# P18：Lecture 18： General I O (Con't), Storage Devices, Performance - RubatoTheEmber - BV1L541117gr

 So， welcome back everybody。

![](img/23e79b6fcc118f0e2bb88e747e8fef69_1.png)

 So we're going to pick up where we were last time talking about devices and general I/O。 And if you remember from last time， let me just see if I've got it advancing here。 We were talking about how the processor is able to talk to the device。 And we sort of started with this idea， which is the CPU has a bus， which we might call。

 the memory bus。 And I guess that's allowed for everybody there。 Is that better？

 Not quite so booming。 So， and that CPU memory bus needs to be short and probably wide to be fast because the memory。 is in the critical path of everything。 So in order to actually put I/O devices in the system。 we talked about having adapters， that talk via the processor memory bus， roughly speaking。 to controllers。 And the controllers are the interface to the device itself。

 And I'm going to show you in a moment how a modern processor kind of ties all this together。 But let's talk about this abstractly for a moment。 So the CPU is going to do operations that are going to go through the bus adapters to this。 controller。 And the controller will give responses back。

 So you can imagine that because this is on the memory bus， we can do reads and writes to。 that controller and it'll act just like memory except it's going to be accessing the device。 And of course， the other thing that's going to be important is for the device to be able。 to interrupt the processor。 So this is， we're starting now to show you all the other interrupts other than the timer。

 interrupt， which was kind of the only one we really talked about most of the term。 And so the CPU interacts with a controller to summarize here。 The controller。 if you look inside of it， typical controllers have a set of control registers。 which I'm showing here on the left， and then potentially big chunks of actual addressable， memory。

 And those registers are control registers and status registers。 You can find out kind of what's happening with the device by reading from them。 And you can often control the device by writing to them。 Okay。 And we'll talk about how you can do those reading and writing in a moment。

 And then this big chunk of memory is potentially， you know， it could be， for instance， the display。 pixels。 It could be any number of things having to do with that device。 If this were the network device， it could be incoming packets。 Okay。 And so just like we have physical DRAM， these controllers are going to be interacting over。

 an interface。 It's going to look pretty much like memory under most cases。 So however。 there are two main ways of talking to devices。 And this is kind of where we stopped off last time。 So one is a port map。io。 And I'm going to show you what that means in a second。 And the other is memory map。io。 So port map。io is special。io instructions。

 Processors like Intel x86 compatible processors have these port map。io instructions。 And when you use one of those IO instructions， you can use it to directly address the control。 registers of that device。 And what I'm showing here just for the sake of argument is I'm showing you port 32 or。 OX 20 is where the beginning of these registers are。 And so if I did an in from port 20。

 I might read this register。 And if I did an in from port or an out to port 21。 I might write this register。 Okay。 Those are special instructions just for IO。 Now that is pretty much on only specialized processors like while the x86 is hard to call。 it specialized because it's pretty much everywhere。

 But a general mechanism that appears on all processors is this idea of memory map。io。 And what's different about memory map。io is just by doing loads and stores to addresses。 that are outside of where the physical DRAM is， they can be parts of the memory space。 Okay。 And I'll show you what this looks like in a moment。

 But by reading and writing some high address in the physical space， you could actually be。 controlling a network or controlling the device。 Okay。 Question。 Yes。 So this is so the idea of a bus is it's a way of connecting multiple things together。 And this is just abstract here in a moment。 Okay。 But the idea is the CPU is doing essentially let's say loads and stores to physical memory。

 after they've been translated by the MMU。 And so those loads and stores could either go to regular DRAM and we want that to be quick。 Or it doesn't have to be quite as quick。 We can go out to the IO devices because it's the same interface to the processor。

 It's a load in store to some physical address。 Okay。 So conceptually at least it's the same bus。 All right。 And for all the problems I told you last time about buses that they tend to slow things down。 and so on。 I'll show you that in reality what happens is this is really a point to point thing that。 you could call it a bus but it's really a communication network。 We'll get to that in a sec。 Okay。

 Good question though。 Any other questions？ So I want to talk about this IO port map。

![](img/23e79b6fcc118f0e2bb88e747e8fef69_3.png)

 I owe here just for a second。 You can't really see this too well because it's very small but port map。 I always been around forever。 It was in the original 80 86 processors。 And if you look here I have in be here I've out be instructions and those are things that。 are going to send data out。 You can look at the slides online if you like later。

 And that out be instruction typically has a port just for speakers。 So if you went to a I don't know the computer history museum and you looked up IBM PC。 What you'd find is there are ports that have been defined since the beginning of the IBM。 PC's that are for speakers and for interrupts and for all of those ports are for interrupt。

 configuration。 And so those if you say an out to the standard speaker port you might actually cause the speaker。 to do something okay。 And so in fact this out be quote unquote instruction here's a here's a C prototype for。 that's using the assembly syntax and so that assembly syntax actually turns this C call。 into an actual one instruction operation of out to the speaker。

 And of course a similar idea for in where basically you have what port you're interested。 in and what it returns is a byte okay。 And so in be an out be are actually one instruction ways of talking to a device and the way you。 say which device it is or which register in the device is you actually use a port number。 and those port numbers started out as eight bits and they kind of went to 16 bits and。

 then there's a bit of an extended version that's 32 bits but they're typically defined。 specifically for the architecture all right。 Now I'm going to move on from those because that's very specific to certain architectures。 More interesting is this idea of memory mapping okay and so here I'm going to give you the。 example of a display controller and what I'm showing you here is the physical memory space。

 of a machine not the virtual memory space remember we've been talking about virtual memory。 the last several weeks and midterm two and everything where you map the users virtual。 addresses to physical DRAM addresses right those physical DRAM addresses are in some。 physical space and that's what I'm showing you here。

 So the things that are pink might actually be DRAM okay but the things that are light。 blue here cyan are going to be parts of that display controller that if I read and write。 from those physical addresses I could actually impact the controller。 So for instance and so what's happening is the registers for controlling the controller。

 might get mapped to these certain addresses。 So if I in my page table for the kernel mapped some kernel addresses to 7F000 then if I read。 and wrote from that address I could actually get the status of the display controller just。 by reading and writing from that physical address okay and these physical addresses obviously。 if you have 12 display controllers you don't want them all to use the same addresses because。

 that would be called a conflict okay。 And fortunately all of this stuff auto configures these days if you take the PCI buses or the。 PCI Express follow-ons when you turn the machine on and it's booting up it makes sure that the。 addresses don't overlap properly and they give away for the device driver to figure out。 what the addresses are okay。 If on the other hand you were using an old school PC and you put some cards in you'd actually。

 have to set little physical jumpers to make sure the addresses didn't overlap okay and。 you could very easily plug in cards and the machine would be just toast because there was。 overlapping addresses and it didn't work okay but let's assume this is all auto configuring。 So now once I've got this display I could for instance simply write to addresses here。

 say 80000F00 and I might actually get display memory。 So I don't know if any of you have ever been into writing video games and we're trying。 to make it really fast but if you get access to the display hardware you could actually。 write bits into the display memory and it would show up as dots on the screen of certain。

 colors okay。 So that's a direct interface to that memory which then is in the controller and ends up。 impacting the display okay。 But it might be for instance that writing to the command register causes the onboard controller。 to do something so you might actually have some memory in the memory map space that you。 have a queue of commands of triangles that you want to draw for some game and then by。

 writing to the register you say command which might be like go then it would go ahead and。 use its onboard hardware to render something for you okay。 And of course since this is physical addresses here we can protect it all with virtual memory。 so the kernel can make sure that only it is mapping these addresses okay。

 And so the user programs can't or even more interesting than that is you could give a。 particular process the ability to control this one device by mapping its virtual address。 space to these physical addresses alright。 Questions yeah。 Say that again。 Ah you're worried about the cache。 Now careful this is actually writing to whatever registers are in the actual hardware so that's。

 what memory mapped that's good question so memory mapped IO literally means when I read。 and write a certain physical address it goes directly to the to the hardware。 I thought you were asking a different question which was also a good question so I'm going。 to answer it which was we've been talking about caches right and so if there's a cache。

 in between the processor and the memory controller or excuse me and the display controller it。 seems like you got a different problem which is what I thought you were asking which is。 you write and it goes into the cache but it's not in the hardware okay and so the cache。 kind of gets in the way。 That's kind of what you asked in a different way right。

 So what if you go back and look at the PTE that I showed you last time reminded you again。 what you'll see is there's actually a couple of bits that say uncache and so in that mapping。 you can say okay let the reads and writes always go directly through to the hardware。 never cache them okay and that's what you would do this with these devices good question， yes。

 It isn't that's good question is the real memory being shadowed no what's actually happening。 here is the real memory is in a different part of the address space。 So in this situation you're never going to have as much DRAM as you do addresses okay。 Well if it's only 32 bits we all know that these days 32 bits is 4 gigabytes and so a。

 32 bit physical processor 4 gigabytes isn't a big deal anymore so however but most processors。 are like 64 bits and there's lots of space for the IO space okay yes。 Yeah so what you would do let's suppose just to make this interesting that I'm going to。 give a process your process ability to write this controller what the kernel would do is。

 it would map certain parts of your virtual addresses to these physical addresses and。 then it would also mark the PTEs that are doing that mapping is uncache and then all。 your program all your process has to do is just read and write from those addresses and。 voila it shows up on the screen。 So it's literally like loads and stores that's why it's called memory mapped IO。

 By the way and final answer to the shadowing if you don't have enough physical address space。 then there are ways to shadow out some of the DRAM but these IO addresses are hugely。 are in a huge part of the space yeah so the physical addresses I'm showing on here when。 you read and write to those addresses physically it goes into that device not the DRAM yes。

 Now the reason I didn't quite answer it the way you asked is are those addresses in the。 device not the DRAM well the addresses are just in the address space the question of when。 you read and write those addresses what happens well the way we've set this up is reading and。 writing to those addresses go to this hardware not to DRAM。

 Because because the hardware gets set up because the hardware knows based on the address where。

![](img/23e79b6fcc118f0e2bb88e747e8fef69_5.png)

 things get routed so that's the network bus routes it to the right place。

![](img/23e79b6fcc118f0e2bb88e747e8fef69_7.png)

 Okay good now we have so the question is so does drivers tell the program where the command。 status etc are located that's a good question because we talked about auto configuration。

![](img/23e79b6fcc118f0e2bb88e747e8fef69_9.png)

 oops we get our picture back up so when it boots these the addresses are assigned this。 also happens with USB which you're all very familiar with right you plug your little devices。 in there's an auto configuration process at boot time that figures out what are all the。 things that are controllable are and it assigns addresses to them in a non-overlapping way。

 and there is a way for the device driver to be queried by the operating system to find。 out where things ended up。 Okay hopefully that answered that question there's another one over here yeah。 Who does the redirection the hardware this is purely a hardware thing。



![](img/23e79b6fcc118f0e2bb88e747e8fef69_11.png)

 Yes so the accesses go through the MMU their mark is on cash but it figures out how to map。 your virtual address to physical addresses so they go through the MMU and then they go。 over the physical memory bus to get to the actual device。 Now I'm giving you the common way that this works there are lots of exceptions that we。

 could say you know you could bypass the MMU for certain parts of the address space that's。 another option here too but but for now I think it's easiest for you to think about it。 being translated through the MMU。 Good other questions。 So memory map dio is by far the most common way that people access IO devices because it's。

 a simple question of redirecting based on an address where things go。 Okay and then the then the kernel or whatever just has to read and write from addresses so。

![](img/23e79b6fcc118f0e2bb88e747e8fef69_13.png)

 you use the same loads and stores but their mark is uncashed。

![](img/23e79b6fcc118f0e2bb88e747e8fef69_15.png)

 Okay so now let's keep going on the IO so here's a chip okay this is an old one now this。 is from 2015 but if you open up I encourage everybody to very carefully though open up。 some hardware some time take a look inside okay don't hold a cup of coffee my very first。 computer I ever purchased I was so proud of it I was a freshman yep and I had a cup of。

 coffee and I missed and I spilled it all over my keyboard and I immediately trashed my brand。 new keyboard so don't do this with coffee。

![](img/23e79b6fcc118f0e2bb88e747e8fef69_17.png)

 But if you look inside so here is the Skylake Intel processors okay and this is a four core。 version Skylake goes up to 28 cores but what's interesting in here is these four cores do。 out of order execution they do memory protection extensions they do SGX which is enclaves you。 can get basically a six micro ops per cycle GPU for graphics it's got memory and fast IO。

 there's a large shared level three cache on chip in the ring and then each core so all。 the core is share pieces of level three that are kind of in these blue pieces and the yellow。 pieces and then there's actually level one and two as well there's integrated IO inside。 here so this is what kind of makes it relevant to today's lecture so if you look here these。

 IMC this integrated memory controller can connect multiple DRAM so that's where the DRAMs。 go and then there's a bunch of interfaces like here to the the platform chip controller which。 I'll show you in a moment and there's direct media interface okay so all of that stuff。 is in just the processor chip and this network what you see here in red there's that's an。

 actual ring network and so when the cores are doing reads and writes to physical addresses。 they get routed over that ring network to the right thing so they either get routed。 to DRAM or they get routed to IO okay so and so the question here also is where the way。 we're describing devices mean that memory for the devices on the device and regular memory。

 is separate that's true and so the addresses are just different so the addresses get routed。 some of the high bits get routed to device or not depending on what they are okay so when。 you are looking at your laptop next time appreciate all the stuff that's just in that。



![](img/23e79b6fcc118f0e2bb88e747e8fef69_19.png)

 one chip okay and now if we expand out a little bit what we see here is in yellow is that chip。 I just gave you but below that is the typical platform controller hub and there's this DMI。 which is a high speed digital media interface that is a bus that goes for everything from。 the cores to a certain part of the physical address space which represents slightly slower。

 speed IO devices it goes over DMI and then there's a separate chip that now basically。 gives you a bunch of USB things it gives you a LAN port for ethernet you get PCI express。 which is very fast you get SATA for disks etc okay and there's even this low pin count。 interface here LPC goes to things like BIOS and stuff okay so all of the lower speed things。

 are down here and what's connected directly to the chip well memory see the DDR4 okay and。 display memory which is typically fast so there was a question earlier you know well。 what does it mean to be attached to the memory bus what it means is that ring I showed you。 that's the memory bus and some things are connected directly on that ring other things。

 you route through a controller for DMI bus interface and that takes you to another chip。 for the lower bandwidth stuff okay and so this is a very standard architecture these days。 for Intel chips okay questions so the details are different depending on what the chips are。 so there's a follow on to Skylake which actually has 56 cores and so on but the basic idea here。

 is about the same so really the question another question is the memory for the device in the。 device hardware or the device controller yes it's wherever they decide to put it okay。 you're many people design things in many different ways okay so some of I think in that。 previous diagram I gave you guys some of the things that are blank don't have anything in。

 them okay so if you read and wrote to those addresses nothing would happen now let's talk。 about IO in this more detail so let's drill down so now when we think about IO I want。 you to all think that we're using like a memory mapped interface or a port interface to read。 and write the device's controller okay is everybody with me on that okay so now what do。

 you do if you say want to talk to storage okay so back to this you see this little SATA here。 that's that's an interface that typically goes to disk drive which is going to be a topic later。 in this lecture okay so now suppose we want to read and write from that we have a lot of。 options here so different devices have different granularities to them so we're going to talk。

 about spinning storage or disks in a moment they have a block size granularity or sector。 size granularity that might be 512 bytes at a time always on the other hand if you've got。 a serial line or you've got a mouse then what you typically you might get bytes out of that。 okay so the question of whether you've got a byte level interface or a block level interface。

 is important okay also are you going to access things sequentially or randomly so obviously。 if you have a storage media and you're going to put files on it and read files and write。 files you need to have random access of some sort so typical disks SSDs etc。 allow you to。 randomly select where you're reading from other things like a network port things come。

 in in the order they come in so there no I doesn't make any sense to read a network port。 randomly okay now what's going to be interesting for us is yes we need disks to be random access。 but it's going to be a lot more expensive to randomly go to a different track and start。 reading something that it is to stay on the same track and read something and so we're。

 going to want to take advantage of that when we start designing file systems and that's。 actually going to be next lecture at some point okay and then we also have a transfer。 mechanism so imagine we've got a disk and we reach out to the disk and we say I need。 this block read it for me and it reads it into its local controller memory but that's。

 not helpful to me because I want it to be in DRAM somewhere because I'm going to manipulate。 it as part of a file system so there's a big question of how does it get out of the controller。 and into memory okay and that's going to be done in multiple ways one is you could just。 build a loop read read read read and store seems like that's making the processor do。

 a lot of stuff that's called program。io or direct memory access or DMA so those are a。 couple options we've got okay so let's talk about this for a moment so again think back。 to what I told you about memory map。io so program。io is very simple you build a loop。 you know if it's a 4k block what happens is you say well read byte the first byte from。

 the source which is in the memory controller or excuse me is in the iocotroller and store。 it in memory and then loop increase the address grab the next byte store grab the next byte。 store it so the loop has 4k iterations to it right just to read a block of data out of。 the out of the controller and into memory okay now that's expensive maybe you can optimize。

 it by doing loads and stores that are 32 bits at a time instead of a byte but you're still。 tying up the processor okay so the pros of this is it's very simple hopefully it's very simple。 to to understand and it's really just the processor does a read from the controller and。 write to memory or does a read from memory and a write to the controller and it just does。

 this in a loop okay and that's really easy to do because we're using memory map。io okay。 now before I go on to the next option I want to pause here and say is that makes sense to。 everybody questions are we good on what program。io means it's。 i-o in your program okay every now and then something actually means what it says right。

 so let's talk about dma or direct memory access this is a case where instead of making the。 processor read out of the controller and store into memory what we're going to do is we're。 going to give the controller permission to just write memory on its own okay so what we're do is。 we we first tell the disk to read a block into its internal memory of the controller and then。

 we tell the controller to directly transfer that data from its memory to the DRAM and we。 do that all automatically and just get an interrupt when it's done okay and that's going to be a lot。 more efficient and I'm going to show you an example here so here's an example of how this might work。 so we have a CPU we have a disk controller down here and what we're going to do with the CPU is。

 we're going to start by getting we're going to have your program ask the device driver to transfer。 some data for you so then the next thing is that request is going to go over the bus there's the。 memory bus to the controller okay and that point the disk controller is going to initiate dma on。 its own so we're assuming that in the past we had already loaded off disk into the controller。

 but the CPU is saying hey controller go ahead and do some dma so the disk controller is going to talk。 to a dma engine to get things started and then the dma engine is going to let this go forward。 so that each byte comes out of the controller directly over the buses into memory and when it's。 done it'll give an interrupt saying I'm done and notice that the CPU didn't have to be involved in。

 that because we just said oh tell the dma controller start this transfer then the device transfers it。 all and then it says I'm done and meanwhile the CPU can go back to important tasks you know like。 computing the last digit of pi or something okay that's dma questions。 now notice in some sense the only way that dma can work is if we can treat this whole memory。

 situation like a bus so the d-ram's on that network the disk controllers on that network and we just。 allow the disk controller to be a to control the transfers and send directly from the controller over。 that bus to the memory okay that's why this works and most modern devices support dma directly and so。 if you were to look inside the you're to look inside the device driver for for discs typically they。

 know how to invoke dma and pause that to happen as part of the file system yeah question。 say that again is what lock， so which thread are we talking about okay good question so is the thread blocked so。

![](img/23e79b6fcc118f0e2bb88e747e8fef69_21.png)



![](img/23e79b6fcc118f0e2bb88e747e8fef69_22.png)

 I think what you need to do is you need to bring on your lots of your concurrency hat okay your。 concurrency hat says that if there's uh if there are independent paths then dma can be happening。 independently of anything the cpu's doing that's the first thing to say and then the second thing to。 say is how do we program that we're going to remind you what a device driver consists of in a moment。

 but if a process or a thread says I need to do some IO and that starts the IO going what's going to。 really happen is what it's going to go to sleep on a sleep queue and another the scheduler will get。 involved and somebody else will start running and they'll run and then later the dma will finish。 it'll generate an interrupt which will now say the transfer is done let's wake that guy up again。

 put him back on the ready queue so this is all these are all things that you're now very familiar。 with from the last set electrics right so good now the question here is why can't the cpu。 so one question is what's the relationship between program IO and dma the relationship is program。 IO unfortunately requires the cpu to do a lot of work one one bite at a time or one word at a time。

 where dma is uh getting the cpu out of the loop literally so why can't the cpu access data directly。 from the disk controller memory or write it directly to the disk controller memory it can that's called。 program IO okay so what we're the problem with it doing that is it's time consuming and we'd like to。 free the processor up to do something else and that's why dma is such a useful thing all right。

 that makes sense to folks on chat now any other questions on this yeah。 no dma is another piece of hardware so what we see here is hardware in fact if you notice this。 little cpu is just up there that's the thing we've been talking about all all term so we're kind of。 pushing it out of our picture and we're talking about the IO subsystem so now we're really talking。

 about hardware down here yep so the cmu cmu the cpu is talking to the dma controller and the device。 and asking them to set things up and and the details here by the way are um vary a lot depending on。 what buses we're talking about so like in the uh usb bus which you're very familiar with um you。 typically you can ask the device to do dma in some of the earlier x86 architectures there was a dma。

 controller that you asked and it was like a processor doing reads from the memory from the device and。 stores into memory um so where this dma controller is varies but uh the idea is the same across all of。 them okay yeah， so the disc controller notifies as the cpu uh really the the dma portion notifies it with an interrupt。 that that would be um dma completion interrupt， uh huh so you're worried about uh cache coherence so the so this is getting pretty sophisticated so。

 what i will say is suppose we have two cores one of them read read an old version of the data out of。 memory and then the dma overwrote that old version and now the next time a cpu or core reads it'll。 get the new version and you're worried about that right is that the question so there are lots of。 ways to deal with that the simple way is uh that the um the operating system just make sure to flush。

 out all the caches before things are overwritten in dram okay but that's also expensive again so modern。 architectures typically uh while the dma is going on they're sending in validations up to the cpu and。 that's killing it's kicking things out of the cache automatically so it depends a lot on the。 architecture okay but the bottom line is you need to make sure that this the cache is flushed somehow。

 okay good wow i don't think i've ever gotten quite so many uh questions on this one slide that's。 awesome any other question yeah all right we got a record going here yeah。 so what would happen if we are using program dio instead of dma is just that the cpu would be stuck。 in a loop here and it would read the first word out of the controller and then it would store it。

 into memory and then it would read the second one and store it and so think of a loop in your code。 you know load store load store load store and the cpu can't be doing anything else while it's doing。 that whereas in the case of dma it's off doing something completely different and it gets a。 notification later okay all right so let's talk about that notification so the os needs to know。

 when for instance the i/o device is completed in operation so we ask the disc read this sector for。 me you want to find out later when it's happened well uh that's an interrupt potentially or you want。 to know when there's an error or you want to know when dma dma is done and so there's really two。 completely different ways of doing this one is an interrupt so we already talked about interrupt。

 controller i think almost the first lecture or the second lecture and one of the if you go back to。 those slides you'll see when i showed a picture of the interrupt controller there was like a disc。 drive having an interrupt come into the interrupt controller so just like timer interrupts which。 you're all very aware of now we can set up and have the device interrupt the cpu when the i/o。

 operation is done same idea is what what's been happening before so you're running a user program。 thread the disc says i'm done it generates an interrupt you'll you'll go into the kernel。 switch the stacks as you've done maybe you'll handle that disc interrupt like by waking up。 somebody who's waiting for the data by putting them back on the ready queue and then you'd return。

 from that interrupt back to the interrupted user thread and later the scheduler would schedule the。 one that you just woke up so all of the things that you're used to now thinking about with timer。 interrupts make sense here for device interrupts as well okay polling is a slightly different idea。 here so with interrupting you sell it give me an interrupt when you're done it gives you an。

 interrupt just like i said polling says instead every down then the kernel goes and checks all the。 devices and says hi are they done are they done are they done are they done and if they aren't then。 it goes back to what it was doing it's called polling okay now with polling what you typically。 do is you shut off the interrupt mechanism and then you're just looking in the interrupt controller to。

 see if the interrupt would have been flagged or not so that's an example of a poll okay can anybody。 tell me what the advantages and disadvantages might be of polling。 can do either one what's a disadvantage of polling yeah。 okay the thread is getting involved looking right okay so there's there's CPU time okay what else。

 are there any advantages you could think of or just disadvantage yeah。 yeah so this this uh the pro here is when you go to poll you're just looking at what you're doing one。 read from an i/o register checking it and getting back to what you're doing an interrupt actually。 goes into the kernel saves a bunch of registers gets the interrupt context going there's a lot of。

 overhead to take an interrupt and so if you can be in a situation where the kernel checks periodically。 uh that can be much lower overhead the problem is that if the interrupts are unpredictable then。 you're wasting a lot of time where you check and there's nothing there okay so polling versus。 interrupts are two sides of a coin actual devices combine both and i want to give you a really good。

 example where this is important so most servers these days have 10 or 110， 40， 100 gigabit ethernet。 interfaces on them okay in the cloud very fast if you put the network controller in a mode where。 every packet that comes in generates and interrupts you're spending a huge amount of time interrupting。 for every packet and it's happening at existing you know exorbitantly high rates and so what。

 typically happens is since packets come in bursts the first one generates an interrupt the operating。 system goes into the network part of the kernel grabs the packet out of the controller and then。 starts polling and pulling all the subsequent packets that are still there out of there before。 it disables or before it re-enables interrupts and goes back to what's going on so it's a good。

 combination of interrupts for unpredictable where the bursts start but then because there are bursts。 we do a bunch of polling to get the empty the network controller out and then we only end the。 interrupt service when we've emptied the controller and this was kind of the only way uh uh i would say。 five to ten years ago when you could even make a 10 gigabit interface sort of work because you had。

 because it was just coming in too fast for the processors right questions now remember this。

![](img/23e79b6fcc118f0e2bb88e747e8fef69_24.png)

 we showed this picture early in the class okay so there's a system call interface which we've。 been doing a lot with and those system call interfaces come down to a set of high level。 operations like process management memory management etc we're going to start moving into things like。 file systems device controls of other sorts networking high level but this standard interface。

 everything is read right open right all of those standard calls happen up at this level。 underneath the covers we have to have a set of device drivers etc to handle these various。 systems okay and so these parts especially down the block device drivers and the iF drivers etc。 these are all specialized for particular hardware but they give standard interfaces up。

 so that most of the kernel that's not a device driver is the same that doesn't matter what type。 of device so most of the kernel file systems are exactly operating the same way regardless of the。 type of disk that's attached okay or most of the networking operates the same way despite different。 types of networking Wi-Fi ethernet etc and so that's what this device driver structure does down here。





![](img/23e79b6fcc118f0e2bb88e747e8fef69_26.png)

 okay and if you remember a device driver is that device specific code in the kernel。 that directly interacts with the device hardware supports a standard internal interface。 same kernel i/o system can interact easily with different device drivers and then we talked about。 the i-ocals which lets you control things so device drivers typically have the two pieces。

 the top half is the part that interacts interacts with the high level part of the operating system。 where the processes and so on are the bottom half is run as interrupt service routines and interacts。 with the device drivers okay and so remember this figure i actually showed you this。



![](img/23e79b6fcc118f0e2bb88e747e8fef69_28.png)

 suppose we're going to do a file read so we're going to request i/o so we start in the user program。 it does a system call for a read we check can we already handle the read okay and we're going to。 talk a lot about file systems in the next several lectures so the reason we might be able to do a。 read already is what well we already read part we already read a block in and we only requested a。

 few bytes so it could be that there are more bytes there and so this is a query potentially。 the file system is their data i can give back immediately the answer that's no then we're going。 to send that request through the file system down into the device driver to actually ask the device。 for stuff and at that point we get into the top half of the device driver where our request。

 for some bytes in a file get transmitted transform into a request for certain blocks on the disk。 and that's going to take time how long is it going to take。 take talk to a disk remember what was that number。 one million instructions worth at least right that's that's an important number to remember。

 very long so what do we do at the top half we take the thread that was asking or the process that。 was asking and we put it to sleep on a sleep queue and meanwhile we have started the device。 after we put that guy to sleep now somebody else can wake up and be running later the device is done。 okay so the the interrupt happens okay it gives an i/o completion interrupt at that point we received。

 the interrupt into the device driver the device driver says oh who was waiting for this we find them。 we take them off the wake queue put them back on the ready queue they wake up the kernel transfers。 data into the user's buffer and we continue okay so this interaction between the top half of the。 device driver which initiates operations and puts threads to sleep and the bottom half get。

 which gets woken up by completion interrupts and then wakes the threads up this is a pretty standard。 pattern okay questions so now you actually understand what it means to put something to sleep okay that。 was that was kind of a mystery at the beginning of the term so the goal of that i/o subsystem。 is to make sure that if you write code like this fd f open slash dev says something and you go in。

 a loop and you f prints to it and you close it it works no matter what the device is it works on a。 raw disk it works on a network socket it works on whatever and that's really the uniformity of unix。 remember everything is a file it's kind of that viewpoint we even had a slide like that at the。 beginning of the term and it's really because that device driver portion is exporting something。

 standard enough that the rest of the operating system can basically do the same thing to all。 devices okay and we're going to try to get a flavor in what's involved in actually controlling devices。 for the rest of the lecture and we can only scratch the surface but we want standard interfaces to。 devices so for instance the notion that block devices there's a lot of them okay disk drives。

 tape drives DVDs ROMs etc you always access a block at a time the commands are things like open。 read write seek we can do typically raw IO or file system access so we'll show you what a file。 system is like in the next lecture and but those open read write and seek is going to be the same。 no matter what we talk to okay character devices keyboards my serial ports those are things that。

 you access a byte at a time and there's a different set of system calls that you typically use so。 you all of them open but you instead of read writing seeking you typically do get input to these kind。 of devices okay and then network devices are traditionally treated separately from block and。 character devices and those are things that go through the socket interface okay now um how do we。

 deal with timing so up till now when you went open to file you do open and then you do read and you're。 mostly dealing with a blocking interface right you said read five bytes into this buffer and what。 happens is that read gets put to sleep until there's data to give you that's a blocking interface。 okay but there are two other options which i wanted to point out now because we can start talking。

 about them one is called a non-blocking interface and all that says is if i go to do a read and there's。 no data yet it immediately returns with an error saying there's no data yet okay and the reason i。 do that is so that i could go off and do something else and come back and pull it again okay and so。 typically you can turn things into a non-blocking version just by using either the iocte or the fdc。

 control interface on a file descriptor after you've opened it okay and so what we've done that's。 different here now is if i do a read with a blocking default interface i know it always comes back with。 at least some data unless the file is there's an error or the file's empty or the sockets closed。 whereas with non-blocking i can actually get back nothing right away but it tells me it gave me。

 nothing okay and i go back and look at it later another more interesting perhaps version of this。 is called asynchronous and so what happens in an asynchronous interface is i set up buffers in advance。 and i ask the ios system go read this for me and tell me about it later and then i go away and i。 can do something else so i immediately can go away and do something else later it tells me either via。

 an interrupt of some sort or i pull for it that that when it's done and then i can get the data back。 okay so so it's kind of like asynchronous is like a combination of these two blocking and。 non-blocking where i get to go to set up something for a complete access but i can immediately go away。 and do something else while it's completing for me yes so the difference is non-blocking。

 immediately returns with whatever it can give me and if there's nothing there it'll give me nothing。 so like a read on a socket if i read from a socket with a blocking interface i always get at least one。 byte if i read with a non-blocking set okay and you can set up there's a there's a flag that you can。 set to the file descriptor that says be non-blocking but happens there is it may return to me with zero。

 bytes even though things aren't closed yet so non-blocking disk i/o in principle yes but um disk。 a lot of file systems don't work well with non-blocking unfortunately asynchronous does so in the case of。 asynchronous what you're saying is here's the buffer here's what i want you to read go do it and。 then immediately you get to do something else okay because setting that read starting the read。

 is a is a system called it sets things up and then you can go off and find out about it later。 okay now by the way if you're interested in asynchronous i/o it's not something that。 we normally teach in 162 but you can go look up the Linux a。i。o interfaces and it's actually there's a， whole way to do this that that works well even with files okay now let's talk about uh we're。

 gonna talk about storage devices but let's take a bit of a break i didn't do that last time we'll。 break for like three minutes you guys stand up and stretch and then we'll come back and continue。 all right so uh let's pick up where we left off， uh let's see hello okay so there are a couple there are at least two different types of storage。 devices we'll talk about in this class magnetic disks and flash memory or SSDs so magnetic disks。

 i'll show you a picture in a moment but basically put storage on a bunch of rings on a bunch of。 platters magnetic storage it's rarely corrupted because there's very good uh story um very good error。 correction codes on them there's a really large capacity at low cost it's a block level random。 access okay and uh i'll show you what that means in a moment but it means you're always accessing at。

 least a sector which is 512 bytes or 4 4k um on more advanced drives it's very slow at random access。 but it's much faster with sequential access as you can imagine flash memory is storied it's also a。 very reliable storage it's an intermediate cost relative to disk but it's become very prevalent so。 pretty much if you buy a laptop these days you probably have an SSD or flash memory device inside。

 of it not spinning storage i don't think i purchased a laptop with a spinning disk in it in years okay um。 good performance for reads it's a little worse for writes uh but it also has some weird。 weird problems with it like you have to erase a bunch of blocks at a time you can't just overwrite。 something and it also wears out so let's start with disks so um i asked you earlier if you've opened up。

 a laptop or computer before probably yes have you opened up a disk drive probably no。 i don't know if anybody here has done that that's a much rare thing to do but if you were to look。 inside what you'd see is a bunch of platters which are these round uh magnetic double-sided disks。 on top of each other and a very sophisticated head which has kind of one read right head for。

 every surface and it moves like this as a unit so you have a bunch of disks platters inside here。 and the head kind of goes in and out okay and it simultaneously has a head on the top and the。 bottom of every platter i put this in here by the way these are very cool they're they're old now。 but um what was fun about this is these were the form factor for a flash memory that would fit in。

 cameras i had a camera i used these in but they were actually micro drive so the little tiny disk。 drives that would fit in uh into your camera okay and they were they were um a gigabyte at the time。 which was hugely bigger than anything you could get with flash memory so it's kind of cool but um i。 wanted to give you some specs disk drives really became kind of popular with the IBM personal。

 computer in terms of for users in 1986 and a 30 megabyte hard disk was about 500 bucks and that。 was like a big deal okay and it had like 30 or 40 milliseconds seek time and maybe a megabyte。 per second transfer time okay so let's see where we're going now with these okay so let's talk for a。 moment about what's on a disk so these spinning platters we have a head on the top and the bottom。

 if you were to take any ring okay that's typically called a track okay and if you take all the rings。 that are directly on top of each other for all of the disks in a stack that's called a cylinder okay。 makes sense right looks like a can okay and each uh we can only read and write a sector at a time so。 it's a chunk of bytes at a time okay it's called a sector okay and so what happens is the head。

 moves to the track you want and then you rotate until you get to the sector you want then you read your。 data okay so it's got three things it's got seek rotational and then reading or writing okay now。 the question might be why do we uh why can't we read or write a single byte at a time the answer is。 the overhead would be too high for all of that moving and stuff and in fact the sector has a。

 bunch of error correction code so it's if it's a 512 byte sector there's more data together as a。 unit so that you make sure all the bytes are readable okay or writeable now the disk tracks。 can be a micron or so wide micrometer uh and wavelength of light that you see typically 0。5 microns。 the human eye can see 50 so these are pretty small okay um and typically there's a guard region。

 between each track to help make sure that one track reading and writing doesn't interfere with。 the other one question yes， so this is a great question so you're asking what happens with the size of a sector as you。 start at the beginning in side versus outside in the old days where i'm saying really old days before。 my time what happened was the disk was a constant speed and you moved the the heads to where you。

 wanted to go and then it was a uh amount of time of rotation to find the sector so really it would。 be like there's a bunch of pie shapes so the sectors would get bigger on the outside than the inside okay。 unfortunately why why do you not want to do that well that means if you optimize the magnetic media。 for a certain density of bits you're kind of wasting it on the outside to fit things on the inside。

 so what actually happens today is there are more sectors on the outside than in the inside。 okay and so there are more the sectors are all the same size but there are more of them as you go out。 okay so um so that's great that was a good question right so the track length actually。 varies across the disk more sectors per track on the outside and basic geometry as it's spinning。

 the the sector bits go by the head faster on the outside than the inside so if you store your data。 on the outside tracks you can actually read and write it faster than you can on the inside tracks。 yes， uh not there are some you mean between the rings。 oh I see it's uh sure but there's so many of these sectors it's a small it's a small change。

 okay so um the other interesting thing to note is as the disk got bigger and bigger which meant we。 got more and more density of bits per square inch there is so much data on disks that take。 an 18 terabyte disk in order to read all the data off and or write it on there takes a long time and。 so google about 10 years ago 15 years ago started doing the following they buy these commodity disks。

 but they're so big they'd put people's archival storage on the inside and the storage they're。 mostly using were on the outside and so they would do fast reads and writes to things on the outside。 but things that weren't going to be accessed very often they put on the inside and so that was kind。 of an interesting optimization okay so google did that um another interesting thing we can do。





![](img/23e79b6fcc118f0e2bb88e747e8fef69_30.png)

 which gives us more density is called shingled magnetic recording where we actually here's the。 normal thing where every track has a little space between it that was what we were talking about。 here we can write a track and the right the next one slightly over it okay and the way we the reason。 we can then recover the bits is really good uh digital signal processing that can figure out kind。

 of based on what track your hour what the data is and the reason it's wide is because the uh right。 head can only you know it's got magnetic leakage on every side on either side so by doing smr we。 can make things much denser however as you can imagine when you write one track you're going to。 overwrite some stuff from another one so what typically happens is if you're going to do smr。

 you need to write a bunch of tracks in a region of the disk at a time so it's more used for archival。 storage than active storage okay and it's kind of not great for active file systems where you're。

![](img/23e79b6fcc118f0e2bb88e747e8fef69_32.png)

 overriding things a lot of times but it's much denser now if we were to look at a disk what we'd。 see is cylinders um again are all the tracks under the head at a given point on the surface。 the seek time is how long it takes to get the heads in the rotational latency is the time for you to。 rotate to where you need to go the transfer time is transferring a block of data off the bits or。

 off the disk okay and so we could actually come up with a disk latency for an access equation。 which is some amount of queuing time we'll do a little queuing theory next time。 plus the time to go through that controller remember what the controller is and then。 seek plus rotation plus transfer okay so here's some typical numbers of modern disks okay so。





![](img/23e79b6fcc118f0e2bb88e747e8fef69_34.png)

 I have a seagate 18 terabyte disk from 2020 it's got nine platters that are double-sided they're。 three and a half inches wide the density is a terabit per square inch okay a terabit per square。 inch and the seek time is four to six milliseconds okay and uh if you look um you know most of the。 disks that you're likely to encounter are going to rotate at a 300 3 600 rpm to 7200 rpm but server。

 disks can get to 15 000 rpm that's revolution permitted or 20 000 rpm okay the controller time。 that's going to make it faster right if you rotate faster you can get to your stuff faster。 the transfer time is typically somewhere between 50 and 70 270 megabytes per second。 and it depends on where you're reading from it's faster on the outside than the inside。

 depends on your rotation speed all sorts of things these are all specs you could look up。 okay now I know you're always looking for wonderful things to do at parties you can go to seagate's。 website you can start looking at some of the disk specs I know that's a great party favor right。 and you can look and you can actually see these density numbers you can see the seek times and so。

 on they're actually on they're actually specced out okay and um so for instance we could come up with。

![](img/23e79b6fcc118f0e2bb88e747e8fef69_36.png)

 a performance example where ignoring queuing and controller time for now average seek time of。 five milliseconds we could say hey 70 200 rpm means that it takes we can do 60 000 milliseconds per minute。 for every uh divided by 70 200 revolutions per minute says that a full revolution is about eight。 milliseconds and how long does it take on average once we get to the right track to find the sector。

 we want if it's eight milliseconds for a whole rotation how long does it take to on average to。 find our sector yep four milliseconds right it's about half on average okay so and if it transfer。 rates 50 megabytes per second block size four kilobytes we can just work this out we can say hey。 it's four kilobytes divided by 15 50 megabytes per second transfer time can tell us that it takes about。

 zero point zero eight two milliseconds for one sector and then we can talk about if we want to。 read a block from a random part of the disk we have to seek rotate on average and transfer that gives us。 9。08 two milliseconds to get a block on the other hand and so it's about nine milliseconds to fetch。 or put data on the other hand if we read a block from a random place in the same cylinder what does。

 that mean it means we're not seeking we can remove that seek time and notice the difference here so。 we're getting about 451 kilobytes per second if we have to go back and forth on the disk versus if。 we don't and we leave it in the place and read we get about a megabyte per second so there's a huge。 difference on a disk between having to seek to a random place or not seek or having to move just a。

 little bit versus move a whole bunch and so what does that mean that means when we design file。 systems in the next few lectures and we're going to have disk drives we need to make sure that we。 try to seek as little as possible okay you know it may be that seek and you shall find is the right。 thing to do but seek and you'll slow is another way to go right so we want to seek as little as possible。

 so we're going to want locality on disk and that's going to be something our file systems are going。 to optimize for okay and if we read the next block on the same track it can be even faster okay so。 and that would be basically reading the next block says we don't even have to rotate so that's why。 this is so very fast so how does the seek mechanism work in hardware is a question what happens is。

 the heads actually have a piezoelectric actuator which is a type of material that when you put。 electricity on it it bends a little bit and so it's an actually a piezoelectric actuator。 so depending on how much electricity you put across it it moves more very precise because it's not moving。 very far so there's a lot of intelligence in that controller i showed you earlier so sectors。

 which is the minimum amount of data you can get have very sophisticated error correction codes。 there's something called sector sparing which we can remap so anyway so the controller does。 error correction it can remap sectors i thought i was getting this sector but it's a bad sector so。 it gives me a different one the controller can do that we can do what's called slip sparing。

 where we remap all the sectors if it's bad we'll talk about these later we can skew our tracks to。 get better performance so all of this stuff is in the controller and the file system talks to the。 controller which talks to the disk so some of that sophistication is a good thing because the。 operating system doesn't have to worry about it some of this sophistication is going to prevent。

 us from knowing exactly where things are on the disk which is going to make it harder for us to。 optimize so there's going to be some interesting questions here okay so here's current hard disk。

![](img/23e79b6fcc118f0e2bb88e747e8fef69_38.png)

 drive i mentioned this is the uh c gate xos x 18 from 2020 18 terabytes four milliseconds average。 seek time uh 7200 rpm etc it's about 562 bucks for that that's not too bad remember 500 bucks got us。 18 megabytes back in the ibm pc time right so this is a little different okay little different from 18。 okay megabytes this is terabytes um so i 30 megabytes sorry very different uh let's talk about another。





![](img/23e79b6fcc118f0e2bb88e747e8fef69_40.png)

 type which is ssd so back in 1995 we started putting these flash memories on cards and using them as。 an alternative to disks and by about 2009 the technology got good enough so that it could actually。 have multiple levels of bits in the same cell and i'll show you what that means in a moment。 and so that was kind of the beginning of really large ssd drives and here this guy you see here。

 the form factor is exactly the same as a spinning disk so you can put in the same interface you could。 put that sucker in your computer and it would interface in exactly the same way as a spinning。 disk except that there's flash memory inside okay so an ssd solid state disk is taking flash memory。 putting it in the form factor of a regular disk so that you can plug it in in replacement for a。





![](img/23e79b6fcc118f0e2bb88e747e8fef69_42.png)

 spinning disk okay um there's no moving parts no rotator seek okay so the seek and rotational。 delays are gone uh very low power light weight but if you write overwrite the same thing too many times。 uh it wears out so ssd's unlike disks actually wear out if you write them too much so that's a。 downside of ssd okay here's an architecture so typically it's called a nan flash uh there's a。

 bunch of blocks and it's laid out in a in the fashion of nan of a simos nan but we won't go in。 that for now but here's the host cpu it talks to its controller over the sata which is the same。 disk interface we had for spinning storage and then what's inside that disk ssd uh container。 is a buffer manager that cues a bunch of requests and a memory controller for the flash and what does。

 that do well the smallest size that you could read and write off of an ssd is typically like 4k at a time。 okay and so that's the transfer time you can transfer a 4k page at a time and so our latency is going to。 be queuing time plus controller time plus transfer time so notice there's no seek time there's no。 rotational latency okay um and uh the question here uh the previous thing was called a magnetic drive。

 where that come from while there's actual uh there's actual magnetic uh media on the disk surface that。

![](img/23e79b6fcc118f0e2bb88e747e8fef69_44.png)

 gets magnetized one or one way or another to put bits down so this uh let me just show you a little。 bit what's interesting here so writing data is a very complex thing and the reason is that you。 can never overwrite a page so once you've written a 4k page if you want to change it you actually。 have to find a different 4k page you can't overwrite the one you already did instead you collect all。

 the used 4k pages and you uh they had in blocks of 256 kilobytes and then you erase them all at once。 and now you have a bunch of 4k pages you can put back on the free list so the way an ssd works is。 there's actually an indirection layer inside that when you when the operating system says give me block。 x what actually happens is it goes through a translation table it says oh here's block x i'll。

 give it to you and then if you write block x it picks a new physical block maps it to your block x。 and then the old one gets put on a list for re-racer so all of that translation is happening under the。 covers it's called the flash translation layer you don't actually have to worry about it it does。 it for you automatically okay but what's interesting about that is because that layer is there now what。

 it can do is keep track of how often have you written these blocks because every time you erase and。 rewrite a block it gets a little more worn out and so what the flash translation layer does is it tries。 to spread all of your rights evenly across all of the possible blocks in the flash that's called wear。 leveling to make sure that they kind of wear out in the same way okay and so it after all of that's done。

 it gives you the same interface for reading and writing chunks as a hard disk drive 4k at a time。 but you can only override as i said you have to erase 256 kilobytes at a time all right。 and erasure is very slow so that's why you want to optimize and do 256k at a time all right questions。 i don't know how many of you seen inside of an ssd before so this is a very high level view but it's。

 there's lots of components， yeah go ahead， well because it takes a long time to erase a block and so what they do this is called a block in the。 4k things actually called a page very confusing but what happens is it takes a long time to erase a。 big block but now you got a bunch of 4k pages you put on an internal free list that can be used。 remember how we talked about the free list at the end of the uh couple last lecture i guess we talked。

 the beginning a lecture about the clock algorithm in a free list here since it takes a long time to。 erase a bunch of to erase a block we erase a bunch of things at once that's the way the architecture is。 and you put them on the free list and now you can get them quickly okay good question。 now um uh okay so this layer of indirection called the flash translation layer basically。

 allows you to freely locate data under the covers without the os knowing it so that's another thing。 going on and it's essentially copy on right so if you know what you're doing you could in fact。 undo rights in a flash if you had access to a flash translation layer because you're really doing。 copy on right um okay so so uh the flash translation layer there's no need to erase and rewrite the。

 entire 256k block when making small modifications um and it does wear leveling and etc okay and there's。 a garbage collector inside the ssd etc to figure out which pages are no longer in use to collect。 them together into physical big blocks and then erase them okay now here's some current ssd's so。 the seagate xos ssd of uh 15 terabytes that's from 2017 uh has a much higher sequential read uh time。

 860 megabytes per second 920 megabytes per second of rights this is my favorite here's the nip oh by。 the way that thing's about uh five thousand dollars on amazon so you know it's not quite 18 terabytes。 but it's about 10 times as expensive as the uh spinning storage i showed you earlier this is my。 favorite here is a three and a half inch drive 100 terabytes ssd okay uh 40 okay okay so you've been。

 40，000 dollars i don't know if you can buy this one on amazon i haven't looked in a while but um。 all right the interesting thing about this is even though ssd's wear out the spec on this is that it。 for five years you're allowed to write it as much as you want and it will not fail why can they。 guarantee that anybody want to guess why can they tell you even though ssd wears out you're welcome。

 to write it as fast as you like for five years and we guarantee it yes there's no way through the。 interface to overwrite enough of the on board flash to wear any of it out in five years that's exactly。 correct okay i want to do i want to end today with this so um the way that ssd works way that flash。 works is when you uh you have some transistors that are just like simos transistors i don't know if。

 you guys learned about those in in uh one of your early uh undergrad classes but what happens is。 you force some electrons onto an isolated plate and if the electrons are there it's a one and if。 they're not there it's a zero okay and that's the way flash works so when you shove some electrons。 on that little isolation plate it turns out you're increasing the energy of that transistor okay so。

 ones have high energy and zeros don't or vice versa it doesn't really matter what you call。 call what so here's a question how many of you guys have a kindle i know i do i these are kind of。 they're great devices could be sitting a sun and read it's awesome but if you take a kindle that。 was empty and then you fill it with books is it heavier how many people think it's heavier if you。

 fill it with books now many people think that's an absolutely ridiculous question okay a few of you。 so the answer is actually yes but not by much so flash works by trapping electrons so the。 array state is lower energy than the written state。 if you assume for instance this was an old school calculation the kindle has four gigabytes of flash。

 assume that when it's full half of all the bits are one right that's just probabilistic high energy。 states about 10 to the minus 15 joules higher than the lower energy states so if we use equals mc squared。 then a full kindle is about an at a gram heavier 10 to the minus 18 grams than an empty kindle。 now the best scale at the time that somebody did this calculation that you could get。

 it was about 10 to the minus nine grams so this is not that much heavier this is 10 10 to the minus 18。 grams so in fact you probably couldn't measure it on anything of course uh it's still in a music。 calculation this weight difference is overwhelmed by the battery discharge when it gets warm you add。 energy and so on so you know calling this heavier is maybe a bit of a stretch and of course where did。

 I get this information well there was an article in the New York Times back in 2011。 I got a call one time there was this column you guys can look it up there's this column where。 you know readers write in they say uh vicarious is a kindle heavier when it you know when it's full。 and they reached out to me and they said hey is a kindle heavier and so I went through and I。

 consulted with a bunch of my colleagues and so on to get these energy states and wrote a little yes。 it is heavier the funny part about this was that uh right after that was published there were a whole。 bunch of mimicking calculations this one at least is sort of sensical there are a bunch of。 nonsensical ones and you should look this up but including a guy who did a whole video about why。

 the internet all of the data on the internet was the weight of a strawberry。 anyway all right we got to end but let's conclude we talked about interrupts versus polling we talked。 about device drivers we talked about dma we gave you an idea what disk performance is like we're。 going to hit up that a lot more next time we talked about the complex interaction and performance。

 characteristics of various sorts and we started talking about uh what we're going to need to optimize。 when we build a file system so we'll hit that up next time and uh so bursts and highly utilization。 is going to give us queuing delays and we're actually going to do a little queuing theory in this class。 so stay tuned we'll see you on Tuesday have a great weekend don't forget project two is due on。

 Saturday project three starts on Sunday。

![](img/23e79b6fcc118f0e2bb88e747e8fef69_46.png)