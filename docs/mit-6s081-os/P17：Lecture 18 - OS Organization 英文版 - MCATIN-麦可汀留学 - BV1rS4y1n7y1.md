# 【操作系统工程】精译【MIT 公开课 MIT6.S081】 - P17：Lecture 18 - OS Organization 英文版 - MCATIN-麦可汀留学 - BV1rS4y1n7y1

 All right。 You guys hear me。 Yes。 Excellent。 Thank you。 All right。 Today， I want to talk。



![](img/07b446657b79f559ab9740b95aa8b25e_1.png)

 about， talk mostly about micro kernels， but first a little bit of context to sort of， how this lane。

 why people explored micro kernels in the first place。 This， people got the micro。

 kernels by trying to think about a little more broadly about what kernels should actually， do。

 Like we， you know， with XV6， it sort of does the things that UNIX does and we kind。

 of take that set of abstractions and system calls and sort of facilities inside the kernel。

 is kind of， for granted is the target of what we're trying to design。 But it's totally worth。

 wondering， gosh， what should a kernel do in the first place？ Maybe， maybe it's the particular。

 kind of stuff that XV6 or Linux does is not really the best answer or maybe this。 And of， course。

 you know， we're on somewhat treacherous ground here because now we're， you know， we're。

 what kernels are is kind of a development platform for programmers。 As we know， programmers。

 different people have like very different sort of subjective preferences about what kind。

 of infrastructure they like to program on。 So we can't necessarily expect a single best， answer。

 But we can expect to maybe learn something and maybe make some progress by trying to think。

 about what answers might be。 So first of all， let me try to kind of crystallize what the。

 traditional approach is to what kind of kernel interfaces we ought to be using。 And Linux。

 and UNIX and XV6 are all examples of what I personally call the traditional design approach。

 But another word for it that kind of summarizes what this approach is ended up like is monolithic。

 And what that means is that the kernel is a single big program that does all kinds of。

 things all within the same program。 And indeed， this really reflects the way people thought。

 about what kernels ought to be doing。 A real hallmark of kernels like Linux is that they， have。

 they provide powerful abstractions。 You know， they choose things like file systems。

 and which is really a complicated item。 And they present file systems and files and directories。

 and file descriptors as their interface rather than， for example， presenting disk hardware。

 as their interface to applications。 And using presenting powerful abstractions instead of。

 very low level abstractions has some big advantages。 So these monolithic kernels often。

 have big abstractions like file， the file system。 One advantage of big abstractions is。

 that they're often portable of files and directories。 You can implement files and directories on。

 all kinds of storage。 And you can use files and directories that have to have to worry。

 about what brand of disk drive it's running on or maybe it's an SSD instead of a hard。

 drive or maybe it's a network file system。 It all has the same interface because the file。

 system interface is pretty high level， pretty abstract。 So an advantage of this is that。

 it's a way to get portability。 You can write an application and have it run on all kinds。

 of different hardware without having to modify the application。 Another example of this is， that。

 you know， Unix， Linux provides an address space abstraction rather than providing something。

 that's like rather than providing direct access to the MMU hardware。 And that's useful to。

 get portability and to sort of hide complexity from applications。 So another big advantage。

 here are these powerful abstractions that they tend to hide complexity from applications。

 So for example， the file descriptor interface that xv6 provides， it's a very simple interface。

 but just read and write on file descriptors can get much simpler。 But behind it is some。

 very complicated code for actually reading and writing the disk， the file system on disk。

 And so that's a nice for programmers， but it makes for a big complex kernel。 These big。

 abstractions also help the kernel manage and share resources。 We sort of delegated to。

 the kernel things like memory management， the kernel keeps track of what memory is free。

 We similarly， the kernel keeps track of what parts of the disk are free and what parts。

 the disk are in current use。 So programs don't get to think about it。 And that， again， it。

 simplifies programs。 It also helps with robustness and security even because it programs were。

 allowed to decide what parts of the disk are free or not， then maybe one program could。

 use part of the disk that's already being used by another program。 So the fact that the。

 kernel is in charge of resource management helps with sharing and helps with security， but again。

 it's a force that sort of causes the kernel to be big。 So anyway， so having。

 the kernel be in charge of all these sort of juicy abstractions that even if they have。

 simple interfaces， have a lot of complexity inside， have led kernels to be big and complex， items。

 And another aspect of this monolithic design approach is that because it's all one， program。

 all the different kernel systems， it's like the file system and the memory allocator。

 and the scheduler and the virtual memory system， they're all part of one big integrated program。

 It means that they can peer into each other's data structures。 And so that's just tended。

 to make it much easier to implement facilities that are sort of parts of more than one or。

 what you might think of as more than one kind of module or subsystem。 So for example。

 a system called like exec。 exec has his fingers deeply into the file system because it's reading。

 binary images off the disk in order to load them into memory。 It's also has his fingers。

 into the memory allocation and virtual memory paging system because it needs to set up the。

 address space of the new process。 But it's really easy。 There's no problem with doing that in。

 xv6 or Linux because both of all the file system is right there in the same kernel program。

 and the virtual memory system is all survey there as part of the same program。 And if somehow。

 there was a rigid split between the file system and the virtual memory system， it'd be much。

 harder to implement something like exec that has sort of fingers in both of these pies。

 But in a monolithic system， just one big program， it's not easier。 Another thing that makes。

 implementing software inside a monolithic kernel like xv6 or Linux easy is that all the code。

 runs with full hardware privilege。 It's all of xv6 runs in supervisor mode， for example。

 which means there's no limits， there's no irritating or you can't read or write that。

 memory here because you don't have enough privilege。 All the kernel code runs with your。

 maximum privilege。 And you know， the same is true with operating system like Linux。

 So this design strategy is very convenient for kernel developers and it's made it easy。

 to build these big abstractions which are convenient for application developers。 However。

 there's also a certain amount to criticize with the monolithic， the traditional monolithic。

 approach。 And this is starting to be part of the motivation for looking at other architectures。

 like micro kernels。 So you might ask why not monolithic kernels？ So one is just that they're。

 big and complex。 So anything that's Linux is depending on how you count Linux is somewhere。

 between many hundreds of thousands and a few million lines of code。 And people really do。

 take advantage of the fact that one part of Linux can sort of look at the data of another。

 and that makes the programming easier。 But it also makes there be a lot of sort of interconnections。

 and interrelationships between code。 And so it can be a bit challenging sometimes to look。

 at Linux kernel code and figure out what it's up to。 And anytime you get big programs。

 especially ones that are complex structure， you get bugs。 And operating system kernels。

 are no exceptions。 And over the years， they've had all kinds of bugs， including bugs that。

 are exploitable for security。 So this is sort of a troubling set of relationships。 If you。

 allow a big model of the kernel， you almost certainly can't avoid bugs and exploitable。

 security problems。 And that's a real， I mean， that really is a problem。 Another reason why。

 people are maybe not entirely happy with monolithic kernels is that they tend to just grow with。

 all desirable features over time。 And so， you know， Linux is used for all kinds of different。

 things from telephone handsets to desktop workstations and laptops to tablets to servers。

 on the internet to routers。 And that's caused Linux is fantastic that Linux can support。

 all those things。 But it has caused it to be very general。 It has support in there for， many。

 many different things。 And any one application like me running my web servers unlikely to， need。

 for example， Linux is very sophisticated sound card support。 So there's just a huge。

 amount of stuff that's there for to allow Linux to be general purpose， which is good。

 But there's a worry that general purpose is going to tend to mean slow that， you know。

 maybe good for all kinds of different things， but maybe not optimum for anything in particular。

 So it's very hard to， you know， when you're trying to make something run really fast， it's。

 great to have it just only do one or two things。 So you can focus on optimizing a single code， path。

 But if your software needs to do any one of a thousand different things， it's much。

 harder to have focused optimization。 So this is， Linux is not necessarily slow， but it's， you know。

 you might wonder if it's really as fast as it could possibly be for any given， situation。

 And so if you think about， I mean， all you just think， if you think about almost。

 anything in Linux or XB6， you know， you may wonder whether it really needs to do everything。

 it does。 So for example， if you write a single byte over a pipe from one process to another， boy。

 there's a lot of instructions that get executed even in XB6， which is a simple kernel， right？

 There's buffering， you know， there's locking， there's could be a sleep and a wake。

 up during a pipe read and write， there's maybe a schedulering， they call to the scheduler or。

 a context switch。 That's a lot of stuff that's maybe not necessarily the absolute minimum。

 that would be required to move a byte from one process to another。 Another potential problem。

 with these big kernels is that they， because they're so big and they sort of intentionally。

 bite off some very sophisticated abstractions， they tend to have a lot of design decisions。

 kind of baked into the kernel。 So， you know， in ways that you can't， even if you disagree。

 with them， you can't really， you know， tough luck， like applications just have to have to。

 live with it。 So， you know， as opposed to you mentioned some fantasy world， maybe the applications。

 could make a lot more of the decisions。 So， you know， some examples of things where you。

 may be bummed out by the way the API is designed。 For example， in Unix， you can wait for a process。

 of your own children， you know， if you fork， you can then wait for your children， but you。

 can't wait for some other process。 And， you know， maybe you want to wait for a grandchild。

 or an unrelated process， but that's just not an option。 It's just not the way things work。

 even if it would be convenient for you。 Maybe you want to change the way another process。

 is address spaces set up， you know， maybe call and map on behalf of another process that。

 you're controlling。 But again， it's just not an option。 You can， and map change your own。

 address space， but not change other processes address space。 Maybe you're a database and， you know。

 you have B-tree indexes on the disk。 And you may know a lot about it the fastest。

 way to lay out a B-tree on a disk。 But if you're reading and writing files with the file system。

 the file system has no idea that you're actually writing a B-tree or how a B-tree ought to be。

 laid out on a disk for fastest access。 And so if you're a database， you're going to be。

 kind of bummed， you know， maybe you're happy that you have this file system at your disposal。

 but it doesn't really do what you want it to do。 And that's the sense in which design decisions。

 are often baked into big kernels。 And finally， a specific sort of issue that sort of came。

 up in a big way in the 1990s probably， it's the notion of extensibility that it might be。

 desirable for programs to be able to change the kernel on the fly， like to be able to。

 download new code in the kernel or change the way it operates or something in order to do。

 things like have databases be able to control the layout of data on the disk。 And at least。

 in decades past monolithic kernels tended not to have any particular features that helped。

 with this kind of extensibility， or just stuck with whatever the kernel did。 Okay。

 so these were sort of problems in the back of people's minds that led them to think。

 about other kinds of other ways of designing other architectures for operating systems。

 And there were another number of the number of ideas some quite radically different that。

 people pursued。 We're going to talk about one of them， a particularly popular one today。

 and that's the idea of micro kernels。 Micro kernels， although many of the ideas go back。

 to the beginning of computer history， they became a sort of hot research topic starting。

 in maybe the mid to late 1980s。 And the big idea， so a microkernel， this word by the way。

 refers to a sort of general approach or concept。 It doesn't refer to any specific artifact。

 There were many people who designed and built operating systems that followed the general。

 plan for micro kernels， but you know， each of these projects ended up designing an operating。

 system that was maybe quite different from the others。 So the key idea was the tiny kernel。

 that supported just IPC or inter-process communication and some sort of notion of threads or tasks。

 So you have a kernel that provides you a notion of sort of process-like abstraction and a。

 way for processes to communicate with each other with this inter-process communication。

 and nothing else。 And everything else you might want to do， like have a file system。

 you'd implement as a process， as a task， as a user level code， not in the kernel at all。

 So a picture for that might be now we're going to use mu for microkernel。 We've got the microkernel。

 down here and we've got user space processes up here and we might have all the kind of。

 usual processes run。 Maybe we're going to run vi， my favorite text editor， my compiler。

 my Windows system。 But also up here as user level processes， we're going to have the file。

 system just as a server process in user space。 Maybe we're going to have a disk driver。

 That knows how to talk to my disk hardware。 Maybe we'll have a network stack that knows。

 how to talk TCP to my network interface card。 Maybe we'll have a user level process that's。

 in charge of doing fancy paging tricks like memory mapped files or maybe implements copy。

 on write fork or something。 And when my text editor needs to read a file， it needs to talk。

 to the file system。 And so it's going to send a message via IPC in our process communication。

 to the file system server， which has all the file system code in。 It knows about files。

 and directories and the file system server code may need to talk to the disk。 So it might。

 send another sort of disk reader right to the other IPC to the disk driver， which somehow。

 talks to the disk hardware。 The disk driver may return a disk block to the file server。 Maybe。

 the file server finally returns the data you asked for again by inter-process communication。

 messages back to my text editor。 But the critical thing to notice here is that the only stuff。

 going down here in the kernel is support for these processes or tasks or threads or whatever。

 they might be and support for the inter-process communication message passing and nothing else。

 There's no file system down here。 There's no device drivers necessarily down here in， the kernel。

 There's no network stack。 All that stuff is up here is more or less ordinary， user level processes。

 And so it leads you to a very small kernel with relatively little， code optimized。

 You can optimize IPC and there's not much else going on。 And so this is the。

 kind of picture we're going to talk about for the rest of the lecture。 And just to give。

 you a taste of kind of where this ended up， there are actually still micro kernels in。

 use today and indeed the L4 microkernel which is the topic of today's paper。 Turns out to， be used。

 there's many instances， many， many instances of L4 running because it's used。

 in a lot of cell phones in the little microcontrollers that control the cell phone radios。 And it's。

 also apparently used in recent iPhones as the operating system that runs on the special。

 dedicated on-clade processor in the iPhone that hides the secret cryptographic keys。 So。

 there's a bunch of embedded where these micro kernels have won out is in little embedded。

 specialized computer systems。 Not laptops but computer sort of dedicated to single specialized。

 tasks where you may not need the complexity of Linux but you do need some operating system。

 The other thing that's the other sort of final result from micro kernels is that the idea。

 of user level services with other programs talking to them with IPC that also has made。

 its way into a lot of operations like Mac OS which I'm running right now to talk to you。

 You know it's sort of as well as being a kind of ordinary monolithic kernel。 It also has。

 good support for user level services and IPC between Unix processes to talk to these services。

 So that idea also was a successful idea and widely adopted。 Okay so this is the basic。

 architecture that I'm going to go on and sort of talk about some ways and reasons why this。

 might be attractive but first or the only just kind of high level questions about what it。

 is I mean by microkernel。 Okay so what is it that people are hoping for when they started。

 building microkernel。 So one big motivation although you wouldn't necessarily see it written。

 down much is just a sense of aesthetics right。 I think just a lot of people feel that huge。

 complicated single programs like Linux kernel are just not very elegant that surely we can。

 build something that's much more much much smaller， much more focused design isn't such。

 a huge grab bag of random different features。 So I think there was a strong sort of aesthetic。

 feeling that surely we can do better than big kernels。 But other sort of more specific。

 things that you might be able to quantify are something a kernel that's small might be， more secure。

 A few lines of code you have probably a few bugs you have less chance of。

 somebody to be able to exploit one of those bugs to break security。 And in the extreme。

 of that you could imagine an operating system that's actually provably correct where somebody。

 can sit down and write a proof that the operating system has no bugs or does exactly what it's。

 supposed to do and nothing else。 And indeed there is a at least one verified proved correct。

 proved secure operating system named SEL4 which is one of the many descendants of the。

 L4 microkernel that it is paper。 But you really you know people know how to verify sort of。

 small the medium size programs but they don't know how to verify huge programs unless the。

 fact that microkernel are small is sort of a critical ingredient and be able to prove。

 they're correct。 Another reason why you might like small is that a small amount of code。

 is often a lot easier to optimize than a huge program。 Another reason why small might result。

 in fast is that you don't have to pay for a lot of features that you don't use。 If your。

 microkernel does hardly anything then you're not paying for a lot of features you're not， using。

 Another reason for small is that a small kernel probably bakes in far fewer design。

 decisions forces fewer design decisions on application writers。 And so it leaves them。

 more maybe it leaves them more flexible flexibility to make their own design decisions。 So by。

 the way these are all these are not necessary consequences of the microkernel approach。 These。

 are things that people hoped for and tried to achieve by using microkernel。 Another set。

 of reasons why microkernel seems attractive has to do with the fact that a lot of the。

 code was at user level。 That is a lot of features and functions that we sort of have grown used。

 to being inside the kernel or actually user level services。 So they hope that by sort of。

 breaking the kernel apart and running the different parts like user level services like。

 a file service file service server that might cause the code to be more modular might sort。

 of encourage the operating system designers to split up all these functions into many separate。

 services and that might be a good thing。 User level code is also possibly easier to modify。

 if stuff is at user level it's usually easier to tweak it or replace it or modify it then。

 doing the same stuff in the kernel so it's easier to customize。 Putting the operating systems。

 at user level also might make them more robust。 If the kernel， something goes wrong with the。

 kernel usually you have to panic and reboot because you can't necessarily trust what's。

 in the kernel anymore if it's had some bug that maybe causes it to overwrite a random part。

 of its data。 Whereas if you have a bunch of user level services and one of the malfunctions。

 and devised by zero or de-references， a wild pointer， maybe only that one server will crash。

 and leaving the rest of the operating system intact and maybe you can restart it just that。

 one server。 So maybe user level moving OS functionality to use the process it might lead。

 to more robustness。 This is probably particularly evident for drivers。 Most bugs in the kernel。

 are actually hardware device drivers if we can manage to move the device drivers out。

 of the kernel then we might have many fewer bugs and crashes in the kernel。 And to find。

 out what advantage the people were thinking about back then is that you could emulate or。

 run multiple operating system personalities on top of a microkernel。 So even though the。

 microkernel does hardly anything for you directly you might be able to run a Unix server or something。

 on top of it。 Maybe more than one on the same machine。 And of course that's what today's。

 papers about is running a Unix running Linux as a service on a microkernel。 So these are。

 all the set of things that people were hoping to be able to get some traction on by looking。

 into microkernel science。 Of course there's some sort of puzzles you have to think through。

 some challenges。 One challenge if you want to design your own microkernel is actually。

 figuring out you want the API you want the microkernel system call interface to be as。

 simple as possible because the whole point was to keep it small。 What is the actual smallest。

 set of useful system calls you can get away with？ What does it look like？ That's not particularly。

 clear。 So we're looking at the minimum system call API。 You need this minimum system call。

 API it's great if it's simple but you actually have to be able to build some pretty sophisticated。

 features out of your minimum system call API because even if the kernel doesn't do much。

 you know in the end you got to be able to run programs you got to maybe you're trying。

 to run Unix on top of a microkernel you got to be able to do things like fork and mmap。

 So as part of the system call interface simple low level system call interface it has to。

 be powerful enough to support all the stuff people need to do like exec and fork and heck。

 maybe even copy on right fork or memory mapping on disk files but all in a kernel that has。

 no idea about files or a file system right it needs to support exec but with a kernel。

 that knows nothing about files。 We need the rest of the operating system somehow you know。

 sure the microkernel may be very simple but you know now we're sort of requiring the development。

 of some set of user level servers that implement the rest of the operating system。 So we need。

 to that has to get done at least and may require some just solving design puzzles。 And finally。

 the you know this arrangement requires a lot of chit chat over inner processor communication。

 over IPC so there's going to be great pressure to make the you know you see very fast so we're。

 going to wonder whether IPC can be made fast enough to keep microkernel competitive。 All。

 right and just in general actually the not just IPC speed but in general there's a lot of。

 reason to believe that monolithic kernels derived some performance out of the fact that。

 they're integrated that the file system code can talk to the virtual memory code and memory。

 allocation code and it's all sort of one big happy giant program and if you require all。

 those things to be split out into separate servers or maybe split between a kernel and user。

 level there may be fewer opportunities for optimization by way of integration than that。

 may or may not end up hurting performance。 All right so these are sort of cross cutting。

 hoped for wins and sort of challenges that all the many microkernel projects faced。 Because。

 of today's paper I'm gonna tell you a bunch of bad L4 specifically which is the microkernel。

 the authors of today's paper developed and used。 L4 is not certainly not the earliest microkernel。

 ever made but it's one of the sort of early micro kernels that came out of all the work。

 in this starting in the 1980s and it's fairly representative as far as how it works。 There's。

 been it's a bit of a moving target it was a subject of intense development and evolution。

 for many years and it's still going strong。 If you look at a public apedia you'll see that。

 there's maybe 15 or 20 different variants of L4 that have kind of come and gone and some。

 are still here starting I think in the late 1980s and I know what I'm gonna try to explain。

 to you is my understanding of how L4 worked at about the time that today's paper came out。

 All right so just at a high level the L4 was certainly micro in the sense that it was。

 actually is a small kernel it has only seven system calls some of them are a little bit。

 complex but still it only has seven system calls whereas today's Linux the last time I。

 counted had in the mid 300s and even XV6 which is an extremely simple kernel even XV6 has。

 21 system calls so L4 is only seven so by that metric it's simple it's also not very big I。

 think as of the time this paper was written is at about 13，000 lines of code just not too。

 much XV6 is smaller than that I think XV6 is maybe six or seven thousand lines of code。

 in the kernel but still XV6 is very simple as kernels go and L4 not much more complex than。

 that and this is you know a tenth or a twentieth or a thirtieth as big as Linux is this is。

 pretty small it had only a few basic abstractions it had a notion of what they called tasks or。

 address spaces and these more or less correspond to what we would call a process in Unix it's。

 a bunch of memories mapped starting at zero and and you're able to execute in here just。

 like in a process one difference from XV6 is that there can be multiple threads per task。

 and L4 was in charge of scheduling the multiple threads of execution within each task and part。

 of the reason for this is just that it's very convenient to have threads as a programming。

 structuring program structuring tool and it was also I don't know if they actually supported。

 multi core or multi processor machines at the time the paper was written but they may well。

 have and threads are of course just what you need to be able to harness multiple cores you。

 know executing in the same program so whether there were threads supported by L4 kernel so。

 L4 supported tasks it knew about tasks and knew about threads and it also knew about address。

 spaces in the sense that you could you could ask tell L4 look here's you know how I want。

 pages mapped in my address space and the other main thing that L4 knew about is in a process。

 communication so those every thread had an identifier and one thread could say look I。

 want to send a message just invites to another thread and here's this identifier please send。

 a message to that other thread so these are really the only tasks threads address spaces。

 and IPC were really the only abstractions the system calls I don't know if I can be able。

 to list them all but the system calls were there was a thread thread create system call。

 which also you gave it a address space ID and a test to create a new thread and if the。

 address space or task didn't already exist it would create a new task for you sort of。

 a combined thread and task creation there's send and receive various flavors of send and。

 receive IPC system calls there's a way to map pages into your or other address spaces。

 so you could ask the L4 to change the way your address space was set up the way your。

 page table maps were set up but you could also ask L4 if you had the right permissions to。

 go and change the way another tasks address space was set up so this was actually done。

 through the IPC would spend through the IPC interface you would send a kind of special。

 IPC message that the current knew about to the target thread and the kernel would modify。

 the target threads address space and this is if you're creating a new thread this is actually。

 new threads are created with no memory at all so if you want to create a thread you first。

 call the thread create system called to create the new thread and a task and address space。

 now you send it you make one of these magic IPCs to send it some of your own memory the。

 map some of your own memory that you've prepared with instructions or data to map that memory。

 into the new into the new task address space and then you send a special start IPC to this。

 new task with the program counter and the stack pointer you want it to start executing。

 with and it will start executing and that memory you've set up at the program counter。

 the US to start at there's a way not through system calls in fact I don't know how it worked。

 but privilege tasks could map device hardware you know device control registers into their。

 own address spaces so L4 didn't really know much about devices like disks or network interface。

 cards but user level software could get directly at you use a little bit of the implemented。

 device drivers that user level could get directly at device hardware there was a way。

 to you could tell L4 to turn and interrupt any interrupt from any device L4 didn't really。

 know which device it just turned a given interrupt into an IPC message so a device driver task。

 could not just read and write the device harder but also tell L4 well anytime that device interrupts。

 please send me an IPC message to notify me at the interrupt and finally one task could。

 tell the kernel to give it notifications of another task page faults so if this task page。

 faults L4 would turn that into a IPC message and send it to another designated pager task。

 send the notification the page fault to a designated pager task so every task had an。

 associated pager task that handled its page faults and that's the way you know you get。

 hooks into the page faults in order to implement things like copy on write for or lazy allocation。

 and that's it for the kernel there's nothing else in L4 there's no file system L4 didn't itself。

 have support for things like fork or exec didn't have any communication beyond this very simple IPC。

 like did not pipe did not device drivers no networking support nothing everything else if you wanted it。

 you need to supply as usual level services， okay so one thing that L4 does supply is switching among threads L4 would actually do the scheduling。

 and context which is in order to multiplex a single CPU among multiple threads and the way it did it。

 you would find completely unsurprising L4 basically had saved registers for every task for every thread。

 when it executed a thread the execute would you know would jump into user's base and switch page。

 tables to that thread and that thread would execute for a while in user's base then maybe the timer。

 interrupt would go off and that was actually the device L4 knew about a timer in or it might go off。

 after a while interrupt into L4 L4 would save this task user registers in a per task。

 an array of like tasks or thread structures would save this threads registers away。

 now pick a new task to run in a loop much like the scheduling loop in xv6 restore。

 this task registers out from its previously saved registers switch page tables and then。

 jump into this task and execute it for a while until the timer interrupt went off or until this。

 task either yielded I think there's also probably a yield system call or something like it。

 a task could yield the CPU or a task could wait to receive an iPC in that case。

 L4 would jump back into L4 and L4 would save its registers switch to a new task and run that task。

 so that thread switching part of L4 is very， be very familiar。

 the I mentioned this before but I just I want to because it comes up I want to。

 write here this notion of a pager the repeat if a process is a page fault。

 traps into the kernel and the kernel turns that page fault into an iPC message to a designated pager。

 task and tells it the address you know that tells it tells this pager task。

 which thread faulted and the address it faulted on and then the pager task if it wants to say implement。

 lazy allocation maybe this thread wrote read or write some memory that wasn't allocated yet but it。

 think but it's asked to be lazily allocated its pager task would then be in charge of。

 allocating some memory from L4 sending one of these special iPCs that caused。

 that caused the memory to be mapped into this task and then sending an iPC to resume execution。

 inside this thread so there was this notion of pager task to implement all this all the stuff that。

 xv6 or linux implements in page fault handlers like you could implement copy on right fork with。

 this if you liked or memory mapped files all using one of these pager tasks so they were。

 sort of powerful user level way to play tricks with driven by page faults。

 and so this is an example you know one of many examples in which a microkernel like L4 might。

 have been quite a bit more flexible for user programs than a conventional kernel like if you。

 just if you think linux ought to do some extra thing like maybe you know some you know if linux。

 didn't already have copy on right fork and you wanted to have copy on right fork you know you。

 really can't implement that in linux without modifying the kernel there's no way to write portable。

 code portable user level code for linux that could implement something like copy on right fork。

 because i'm not that's not quite true but it would be very difficult whereas in L4 it's relatively。

 straightforward L4 is like completely set up for you to be able to write user level code that gets。

 the page faults that are required to drive copy on right fork all in user space without having to。

 mess with the kernel okay so any questions so far about how L4 works。

 oh sorry can you just clarify the difference between our thread and a task。

 um yes a a task corresponds to a it's like a process it in xv6 it has a bunch of memory and an。

 address space and you can execute user code in it xv6 if you have a process in xv6 it can only。

 there can only be one thread of control on a single you know executing inside a process in xv6。

 but in modern operating systems and in L4 in a single process in a single address space you could。

 have multiple if you have multiple cores you can have multiple cores executing in a single task。

 because each you know typically always each set up with its own stack inside that tasks address。

 space and so if you that means you can for example write a single program that can get parallel speed。

 up improve performance from multi core hardware by running one thread on having multiple threads。

 each running on a different core thereby getting more work done okay so thank you yes。

 okay um so as you can see this is a design that relies heavily on。

 ipc because you're going to want to talk to your file server a file server is going to want to talk。

 to the device driver server you know you're going to have ipc messages flying back and forth。

 for every system call for every page fault for every device interrupt the ipc system just has to be。

 fast however and now we're starting to sort of talk about a serious potential defect in the micro。

 kernel story um so first let me show you um a straightforward but very slow design。

 for ipc patterned off of Unix pipes and i'm bringing this up because some early micro kernels。

 worked in sort of a similar way to what i'm about to show you which turned out to be slow。

 but okay so um let's suppose you have uh you know you have two processes we got p1 um p1 wants。

 to send a message to p2 so how should that actually work well one possibility is to have。

 a send system call and you give send system call the id of the thread you want to send the message to。

 and um a pointer to the message to the bytes maybe that you actually want to send to that process。

 so this is system calls you're going to jump into the kernel um you know maybe we design this patterned。

 after uh pipes and xv6 and so you can imagine there being a buffer of messages waiting you know maybe。

 p2 is doing something else right now if it's a server it's serving somebody else's request so。

 it's not ready to handle your request um you can imagine maybe a buffer of waiting messages。

 in the kernel like a pipe buffer and when you call send it um appends your message to this buffer。

 waiting for p2 to receive it now in fact almost always um in these systems you really just。

 wanted to send a message you almost always wanted to get a response to you wanted an RPC or remote。

 procedure call operation so in fact p1 would probably follow this immediately by a receive to try to get。

 the response back um but in general let's just imagine we're doing a one-way ipc for the moment so。

 send would append your message uh to the in kernel buffer um we would have to copy the message bytes。

 from user space into this buffer um and then return and process one can do something else like。

 maybe prepare to receive the response um after a while p2 um is going to want to receive the next。

 message it's going to make the receive system call um and that's going to return the id of the sender。

 and copy the message into p2's memory so it's going to take the front message off the queue copy。

 and the p2's memory and then return um so um， this is called uh yep there's some words for this whose opposites you'll see and。

 you saw on today's paper this is called an asynchronous scheme。

 because p1 sends a message without having to wait for anything it just depends just to this queue and。

 returns um and it's called a buffered system because the kernel uh copies these messages into the buffer。

 into its internal buffer on a send and then later and when the receive happens it copies the message out。

 of the buffer to the target so this is asynchronous and buffered um if you're doing a full request response。

 here then p1's going to call send sends going to return p1 is then immediately let's assume we're。

 going to assume that there's really sort of two sets of buffers one for each direction p1's。

 immediately going to call receive um receives going to wait going to need to wait for something to appear。

 in the reply buffer so it's going to have to yield the cpu it's going to have to do something i call。

 sleep in xv60 yield the cpu um and on a in a single cpu system it may be only at this point。

 that p1 gives up the cpu and now p2 can run and indeed the hardware in this arrow is almost always。

 single core um certainly this paper uh is running on single core hardware so p1's gonna it's going to。

 be p1 executing and p1 not executing until p1 finally gives up the cpu and receive waiting for a message。

 to appear here and only then will p2 be scheduled maybe it'll call receive the cpu copy the message。

 and then p2 will make its call the send um to append its reply um and then the send system call。

 return to p2 and at some point presumably p2 will give up the cpu maybe the timer will go off and p1。

 will resume execution in the kernel see that there's a message there and return it back to user space。

 and so that means that in this design this slow design um there's in order to have a request。

 and a response um uh there's four system calls two sends and two receives and you know。

 eight user kernel crossings each one of it's just like reasonably expensive um there's a need to。

 sleep this receive has to sleep waiting for data to appear um and there's a full call to the scheduler。

 loop and a context switch from p1 to p2 in order to make this and you know each of these kernel。

 crossings and context switchings is potentially expensive because um you know every time you。

 cross the kernel user boundaries switch page tables um and that uh is it has a near certainty of um。

 disturbing the cpu caches like changing the page table probably flushes the uh the tlb the virtual。

 memory lookup cache which is going to slow things down um so um this is a pretty slow way to go。

 it involves a lot of kernel crossings message copying of messages between user and kernel。

 maybe allocation of buffers etc but it turns out that for the for this stylized case in which you're。

 sending a request and you want to get a response back um you can strip this down to a considerably。

 simpler design um in fact this is the way all forward and this was laid out in a famous paper。

 called improving iPC by kernel design published a few years before today's paper。

 so it does a couple things differently for one thing um it's synchronous that is um。

 there's none of this there's no uh dropping something off and returning and waiting。

 letting the other guy then letting the other process pick up the data when it feels like it instead。

 send waits for receive and receive waits for send so um if i'm process one and i want to send and i。

 call send um it it doesn't copy my message into a buffer it actually um p1 will now immediately if。

 if p1 send in the in the l4 kernel waits for p2 to call receive and if p2 is already in the kernel。

 waiting in a call to receive well p2 is either already in the kernel um waiting in a call to receive。

 or uh p1 send wait for it waits for p2's next call to receive when both have arrived here when p1 is。

 in the kernel and it's called the send and p2 is in the kernel and it's called to receive。

 only then does anything happen um and um one reason this is fast is that if p2 is already。

 in receive then p1 when it's executing send in the kernel can just without a context switch or a。

 general purpose scheduling can just jump back into user space into p2 as if it was returning from。

 this receive right and that's a much faster path through the kernel um then you know saving。

 registers giving up the cpu calling the scheduler um and finding a new process to run instead p1。

 send knows that there's a waiting receive um and just sort of immediately jumps into p2 as if it。

 was returning from receive um the scheme that they developed is also unbuffered。

 and it can do that partially because it's synchronous um when both the send and the receive are in the。

 kernel um the message can be you know send sending some message the kernel can directly copy the。

 message from user space to user space without having to first copy it into the kernel and then。

 back out of the kernel because because since you know both sides wait for the other system called。

 that would happen that means that they've waited for both pointers to be known receive specifies where。

 it wants the message to be deposited so at this point we know both addresses then。

 kurtl can just do the copy directly instead of through the kernel um for and um if the message is。

 super small like maybe only a few dozen bytes then uh it can be passed in registers without any copy at。

 all um but you might call zero copy remember the send only proceeds if if p2 is already in receive。

 and it the send basically jumps directly to p2 well this code path through the kernel takes care to。

 not disturb a bunch of the registers um and that means that p1 can put its system call if it's if。

 the message is short it can put the message in certain designated registers the kernel guarantees。

 to preserve those registers on its way up to p2 and that means that when the kernel returns from the。

 receive system call but as a result of send the contents of those designated registers hold the。

 message and therefore never had to be copied at all from memory to memory never had to be moved at。

 all they're just sitting right in the registers where they can be accessed very quickly um。

 and this you know of course this only works for small messages um for very large messages。

 l4 could carry a page mapping in an ipc message so for for huge messages。

 you know like the result of reading a block from a file or something。

 you could just send the page and it'll be mapped into the target's address space again without any。

 copy and so this is done through page mapping give away the page or access to a copy to。

 access permission to share the page and so small messages are fast uh huge messages are pretty fast。

 you know you still have to adjust the page table to target but that's much faster than copying um。

 and a final trick that elf were played was noticing that um if you're doing an rpc with a request and。

 response there's a very stylized pairs of um uh system calls and you may as well combine。

 system calls send and receive system calls in order to reduce kernel crossing so um for the。

 special case of rpc which is almost always what people are doing when they're using ipc there was。

 a call system call and a call was basically a combined send plus receive。

 you know but without the return to user space and then reentry into kernel space that a pair of system。

 calls take um and on the server side there was a um a single call that would send the reply um。

 from one system call and then wait for uh the request message from anyone for the next system call。

 and this was basically a send of one response but wait to receive the next request and this again。

 cut in half the number of kernel crossings um and it turned out that uh the sum of all of these。

 optimizations you know for the kind of short rpc's which uh are you know one typical workload all this。

 led to a 20x speed up this is what their paper reported 20x speed up over their previous system。

 which was presumably a little bit more like what i showed in the previous design um and so this。

 was an impressive um this paper came out a few years before the by the some of the same authors。

 but a few years before the people were reading and this caused people to um view micro kernels a。

 little bit more favorably that the ipc could actually be made quite fast any questions about。

 these ipc tricks that l4 plays yeah i i think i missed this but um when is a process uh sending。

 their or like receiving messages like when is it using that system call okay actually so for rpc's。

 for request response in fact the in fact the processes use this pair of of system calls rather。

 than send and receive um so yeah call you really give it two arguments a message you want to send。

 and a place to put the response and inside the kernel it just combines these two i mean you could。

 view this as a bit of a hack but um because ipc is so frequent it's worth a little bit of hacory in order。

 to make it be fast and in the diagram um up there in the box where um you have p2 sending that or like。

 running the receive system call what like what prompted p2 to。

 okay it in in my rpc world uh we got we have clients， and they're sending requests to servers。

 and the server is going to do something and reply so since p2 is a server we imagine that p2 is。

 sitting in a while loop in which it in which it's going to receive the next message from any client。

 do a little bit of work to process it you know look up some data in a database or something and。

 then send or apply then go back to the top of the loop and wait again so to a first approximation。

 we expect p2 to spend all its time uh waiting for the next message from anyone that's request from。

 anyone and i and this design really um it does kind of rely on p2 always at when it's at rest。

 basically sitting in the kernel in a receive system call waiting for the next request so that the。

 next request can directly basically return from that system call right that's the fast path that's。

 super efficient in this design cool thank you， so i just to fill up on that that means that um you said that it goes from p1 and like returns to p2。

 so like to come back you would need to send a response so that's right we expect p2 to。

 um send a response and and that sending of the response actually follows basically the same。

 code path in reverse so that when p2 sends a response um that that effectively causes p1 to return from。

 the i mean p1 is actually making this call system call so the delivery of p2's response。

 causes the call the return from this from this system call back into p1。

 okay i see thank you you know this is a little bit different from the usual setup where you think of。

 you know you jump into the kernel in a system call and you execute that system call and it returns。

 sort of all working on the half of p1 which is the way pipe read and write work here you know p1 is。

 entering the kernel you know it's p1 entering the kernel you know and then but the return goes to p2's。

 so it's kind of odd but um very fast， okay um so this was a big big sort of contribution to people taking micro kernels。

 people's willingness to take micro kernels seriously as potentially a replacement for。

 monolithic kernels however you know that you still have to still leave open the question even if rpc's。

 fast like where do you get the rest of the operating system right you know this kernel only has like。

 a few percent of all the stuff like file systems and network stacks and we expect to be in a full。

 operating system what do we do about the rest um and this question is usually being asked in the。

 context of some university research project with relatively limited resources um we need to get。

 all those user level services from some way um now actually there are specialized applications for。

 which that's not too much of a problem if we're you know running uh you know some sort of device。

 you know controller maybe the you know ignition control system for your car that is you know only。

 running a few thousand lines of code anyway maybe doesn't need a file system um then we can get away。

 with like very little stuff at user level and micro kernels you know totally make sense for that kind。

 of application um but the people you know in these projects really they had ambitions that oh gosh。

 we're going to totally replace existing operating systems and they hoped that they could build。

 something that people would want to run on their on their workstations and run on their servers and。

 everywhere and just replace big monolithic kernels all together and but for that you know you need a。

 real you need all the stuff that an operating system does um one possibility the most maybe sort of。

 philosophically consistent possibility would be to you know reimplement everything you need but in a。

 sort of microkernel way is lots and lots of different user level processes um but that's just。

 actually people you know there were projects that did that but it's a vast amount of work um and。

 more specifically people really want to run you know in order for me to use a laptop it just has。

 to run emax right and it has to run my favorite c compiler otherwise i'm just definitely not going。

 to switch to your operating system um and what that meant is that micro kernels in order for。

 to gain any kind of adoption they had to be able to support existing applications um they had to be。

 able to be compatible provide a identical at least at the system called at the higher level service。

 API level they had to be totally compatible with some existing operating system like UNIX like Linux。

 in order for anybody to be willing to switch um so they these projects faced a more specific。

 problem of how they were going to get uh how are they going to attain compatibility with you know。

 existing applications written for Linux or maybe windows or something but um for this project it。

 was Linux um and rather than write their own totally new set of usual level servers that。

 mimic Linux um they decided to take the far easier path and many projects did this of simply。

 directly running an existing um monolithic kernel as on top of their microkernel instead of。

 re-implementing some new thing and so that's that's exactly what today's paper is about um it has uh。



![](img/07b446657b79f559ab9740b95aa8b25e_3.png)

 indeed you know l4 microkernel down at the bottom um。

 but also as like a pretty big server they run a pretty full Linux kernel as a user level process。

 um and so they may sound a little surprising the kernels not to use a level process right the。

 kernels the kernel you think of it as running on the hardware but in fact you know the Linux kernel。

 as as you can see from running xv6 and qmu which is running in user space after all。

 a kernel is just a program and so with some modifications it can be made to run um at user level。

 and so they had to modify Linux and they took a lot of the low level stuff in Linux for example。

 the code in Linux that expects to be able to directly modify page tables or read and write。

 processor registers um there was some low level stuff they had to modify so some parts of Linux。

 they had to change um in order to convert them to basically make system calls or send iPC messages。

 through l4 instead of directly get at hardware but for the most part they were able to directly run。

 without change almost all of Linux so that means they got as part of Linux you know a file system。

 and a network support and all kinds of device drivers and um who knows what that comes with Linux。

 without having to write their own version of this um now um in fact the way this was set up was that。

 Linux the Linux kernel ran as one l4 task and but each Linux process ran as a separate l4 task so。

 when you log into this Linux and you ask it to run a shell for you a terminal window or something。

 it's going to fire up an l4 task that's going to run that Linux program at user level um so there。

 were one task for Linux and one task for each Linux process that you fire up um under Linux and。

 Linux instead of directly you know modifying the page table that the vi that the vi process uses。

 Linux is going to ask l send the right iPCs to l4 to cause l4 to change vi's page table。

 any questions about the about the basic scheme here。

 um another thing to uh another thing that was changed many small things were changed but。

 a specific thing of interest is that when vi wants to make a system call so。

 if vi doesn't know it's running on l4 um we're the in this scheme it's it's really all these programs。

 just think of themselves as running on Linux when vi wants to make a system call um you know l4 does not。

 support it's not making an l4 system call it's making a Linux system call so vi system calls like。

 fork there's a little library basically that was linked into these um uh Linux processes that would。

 turn calls to things like fork or exec or pipe or read or write into iPC messages um that it would。

 send uh to the Linux task um and wait for the response to the Linux task and then return as if。

 the system called returned um so so these little libraries would turn system calls into uh。

 iPC messages to Linux and with that meant is that if the Linux kernel task isn't doing anything。

 isn't doing anything else it's sitting in our call to receive waiting for the next system call。

 request iPC from any one of these processes um and that led to work uh that leads to a。

 significant difference between how this Linux works and how ordinary Linux works um in ordinary。

 Linux just like xv6 there's a basically a kernel thread that corresponds to every。

 user level process and when a program makes a system call it uh the kernel runs a thread on。

 behalf of that system call um and when in ordinary Linux when Linux switches between kernel threads。

 that basically implies a switch from one process to another um so there's kind of one-to-one correspondence。

 between um what what kernel thread Linux kernel is running and what process is gonna run when。

 Linux is done here that connection is broken they were indeed um in this Linux server a kernel thread。

 corresponding to each i'm sorry let me start again the Linux kernel server was running in a。

 single l4 thread so there was only a single um sort of thread of control executing in the。

 Linux at a time however just as an xv6 um this one thread of control would switch you know using a。

 technique very much like uh xv6's context switch could switch between um a kernel thread corresponding。

 to each user process however uh which of these the these kernel threads were implemented purely。

 within Linux and nothing to do with l4 threads so only one l4 thread here um but which user process。

 was running was determined by l4 so in this setup uh Linux might be serving a request from。

 executing the kernel thread for vi serving a vi system call at the same time that l4 is。

 causing this shelter run in user space which is very unlike uh what happens in xv6 or Linux where。

 there's a direct correspondence between the sort of active kernel thread and the。

 corresponding uh use a level thread here l4 is off running whatever it feels like um and these。

 threads in the Linux kernel are really much more private and are just about Linux being able to。

 concurrently execute system calls in different stages of execution where maybe one process is。

 waiting for the disk in its thread um Linux can run a different processes kernel thread to serve。

 that process in system call um so um you might wonder uh why the this design didn't directly use l4。

 threads uh to implement the various different um uh kernel threads inside Linux why you know。

 why did Linux implement its own sort of internal threads package instead of using l4 threads and。

 the answer was that in those days um a they didn't have access to multi-core hardware they。

 were using single core hardware so there would no performance advantage um to be able to execute。

 multiple threads in the kernel at the same time because there was only one core um so a second。

 thread couldn't be executing only one thread could execute at the time due to the hardware um and。

 the other maybe even more powerful reason is that in those days the version of Linux they were using。

 did not did not have the support that's required to have multiple threads multiple cores executing。

 inside the kernel at the same time they were using a uniprocessor Linux is that old enough Linux。

 that expected only one core in the kernel at a time um it didn't have things like the spin locks that。

 xv6 has that would allow it to correctly execute multiple cores inside the kernel so there would。

 have been no performance advantage um in having multiple l4 threads active inside the kernel um but。

 it would have required adding in you know for no performance when adding in all the spin locks and。

 other stuff is required to support concurrency so they didn't do it a drawback of this arrangement。

 is that um in ordinary Linux in native Linux like you would run directly on your laptop。

 Linux has a lot of sophisticated scheduling machinery that can do things like impose priorities on。

 different processes or ensure various kinds of fairness um and that works fine because in a。

 on your laptop because Linux is in control of what process is running on each core but in this set。

 of Linux is not controlling that at all and Linux has no control over what what process is running。

 because it's l4 that does this scheduling not Linux now these processes are scheduled by l4 so。

 they kind of lost the ability to have Linux be in charge of a schedule thing um you know that's a。

 bit of a defect of this the although um i'm sure leader versions of l4 had some way for。

 Linux or something like it to be able to tell the l4 scheduler or look please。

 give this process higher priority or whatever um so it's a bit awkward， all right um。

 so so they went to all this work um to get this going and um you should ask yourself you know what。

 is the what's the takeaway lesson from from this paper about micro kernels um now one thing this。

 so for us you know this paper has a lot of interesting tidbits about how micro kernels work。

 and about how Linux works and how you know you set up how you can design a system like this which。

 may be interesting but um in the larger world you know people want to want to draw some lessons。

 they need to be able to present some lessons in this paper um the paper is not really answering。

 the question are micro kernels a good idea that's not really what's going on here um the paper what。

 the paper is is part of a argument about whether micro kernels have enough performance to um。

 to be worth using and the reason is that in in uh maybe sort of five years or five or 10 years before。

 this paper came out um there was a famous set of measurements on one of the predecessor micro。

 kernels an earlier micro kernel called mock basically running in very much this uh configuration。

 but a different you know totally different design internally but kind of the same architecture um。

 this um the name of this earlier micro kernel project is mock there was measurements on mock。

 that showed that mock was dramatically slower than just ordinary Unix um when it was run in this。

 configuration and you know there are a lot of reasons for that having to do with the iPC system。

 not being as optimized as you might hope they're being just sort of more context switches and。

 you know we use our kernel crossings and cache misses and whatever you know there's a whole lot。

 of reasons why mock uh was slow but many people saw those benchmarks results showing that mock was。

 much slower than native operating systems and decided that micro kernels were just uh hopeless。

 hopelessly inefficient were unlikely ever to be fast enough to be competitive and you know we should。

 just all use monolithic kernels today's paper is like an answer basically um to that argument it's。

 sort of the rebuttal to that argument and the point of this paper is to show that you can build。

 this architecture and if you pay enough attention to optimizing performance you can get um competitive。

 performance with native operating systems which is just directly running Unix and therefore。

 you can't dismiss micro kernels simply on the basis of performance you may not want them for。

 other reasons but you can't use performance as the reason to reject them um part of the a huge part。

 of the ingredient in um making that argument is that they made the iPC much faster with the。

 techniques that I outlined a few minutes ago and you can see this I think in um in a very simple。

 benchmark in table two if you have a copy of the paper with you um table two has measurements of。

 just native Linux running in the ordinary way on hardware um and on native Linux they show that uh。

 you know on their hardware and their version of Linux that um a single simple system called。

 get PID took 1。7 microseconds um and they also show that the um sort of equivalent thing in their。

 in L4 setup where you have to send an iPC request and get an iPC response just for this get process。

 ID system call that that um that took four microseconds under L4 Linux which is to say twice as long。

 but there's sort of twice as much work going on because you're doing two sets of user kernel crossings。

 instead of just a single simple system call that is they could claim that they had paired the expense。

 of these iPC based system calls down to basically the minimum that is twice the cost of a system。

 call in native Linux and therefore they were doing roughly as good as as you could possibly expect。

 now of course that's still their system calls are still half as fast as native Linux。

 um and you know it's not clear unless you did some measurements whether system calls taking twice。

 or simple system calls taking twice as long as a disaster or not a problem and in order to show that。

 and you know it might be a disaster if you do a lot of system calls or it might be not a problem if。

 you do relatively few system calls or there's a lot of work per system call because。

 maybe your system calls are more complicated than get PID um and the answer to that in the paper。

 is the figure 8 benchmark using this benchmark called AIM which is just a more it's a benchmark。

 that does all kinds of different system calls it reads and writes files and creates processes。

 or does all the things with the kernel that processes do and they basically showed and figure 8 that。

 they're set up running a much more full application that does you know much more than just get PID。

 runs only a few percent slower than native Linux and that therefore hopefully you could expect that。

 whatever it is you wanted to run on a computer would run almost as fast under L4 plus Linux as。

 it does under a straight operating system under native operating system therefore you know they were。

 basically to a first approximation as fast um as just running straight Linux and therefore you。

 should take them seriously um okay so that was an impressive result by the way this is like。

 like somewhat unexpected and um cool just fast forwarding 20 years um where this ended up as I。

 mentioned before people actually use L4 in a bunch of embedded situations particularly it's used a lot。

 there's many instances of L4 running in in smartphones um hidden from view but nevertheless。

 you know all running various kinds of custom software not not running you know they don't have to have。

 compatibility with Unix in these situations micro kernels in other more general situations like work。

 stations or servers never really caught on and it's not because there's necessarily anything wrong。

 with that design it's just they would have to in order to display some existing software your new。

 thing has to be you know like better so people will be motivated to switch and these micro kernels。

 were perfectly good not certainly elegant um but it was hard to put for people to put their finger。

 on why it was so much better that they should like go to the trouble of switching from Linux or whatever。

 they were running uh this and so it never really caught on not necessarily for good reasons but。

 because they weren't like dramatically better on the other hand many ideas from this architecture。

 had a lasting impact um the the uh people had to work out so much more interesting and flexible。

 ways of using virtual memory in order to support operating systems on their micro kernels um and。

 those more sophisticated interfaces made their way through things like mmap um into mainstream。

 operating systems like Linux um this idea of running an operating system kind of on top。

 as a as a you know server on top of a lower level operating system is extremely popular today in。

 the form of uh virtual machine monitors which use all over the place in sort of cloud hosting。

 services um the desire for extensibility you could modify a user level service the way that played out。

 in things like Linux was loadable kernel modules which allow you to。

 load you know modify the way the Linux kernel works on the fly um and of course the sort of。

 client server good support for this client server architecture also made its way into kernels like。

 mack OS which has good iPC and good client server and that's all I have to say for this lecture um。

 happy to stick around for questions thank you， oh I wanted to ask so the paper we're talking about virtual um about page tables at I think 4。

2， um and it was saying how I think it was kind of what we what do you mention before where you said that。

 there is a wrong way to do that I think maybe kind of similar to that but um if you do this this。

 thing that you explained in this um in in your picture now uh would it be I guess how how would the。

 page tables work in this case well are you uh you may be referring to section 4。3 the dual space。

 mistake oh yes sorry 4。3 oh no yeah that's a bit of a complicated story but the um uh let's see。

 but part of the background is the way that Linux worked in those days and indeed until recently。

 is that the when you're running at user level um the page table this active has both the processes。

 pages user level pages mapped in and all of the kernel mapped into that one page table。

 on the x86 anyway so when you made a system call and jumped into the kernel the kernel was。

 already mapped into the page table and therefore no page table switch was required so when you。

 make a system call it's not much more spent and much more cheaper because there was no page table。

 switch if you're calling xv6 you know the trampoline code switches page tables which。

 um is an expensive thing to do because it uh flushes the tlb cache of virtual to physical。

 mappings anyway so for efficiency Linux used to map kernel and user space in the same page table。

 and had fast system calls as a result um so they um for reasons that aren't very clear decided to。

 do this same thing to set up the mappings in the Unix server。

 well what they wanted was that when vi when a process sent a system call over here they wanted。

 to have the page table that was active while in the the next server while processing that system call。

 include all the virtual memory mappings mappings for the process that sent the system call。

 and that at least would make it simpler to look up virtual addresses passed as system call arguments。

 like past repeat the reason why this worked out poorly there were a bunch of reasons one is that。

 l4 which doesn't know anything about any of this stuff l4 just knows there's two processes and so。

 when you send an ipc from one process to another l4 just switches page tables it always just switches。

 page tables a sky to page the vi at a page table l4 associates a page table with Linux kernel just。

 always switches page tables so you couldn't even due to l4 due to the different way system calls。

 were implemented and the fact that l4 was involved there was no way to preserve the page table during。

 a system call that just wasn't possible because it over always switched page tables when it switched。

 from one process to another so they were never going to get the efficiency win of not having to switch。

 page tables when when sort of crossing from process from user to kernel but i think they。

 wanted the convenience of being able to directly use users applied virtual addresses but that meant。

 that the mappings they needed to be active depended on which process they were executing a system call。

 on behalf of so there couldn't be any one page table for Linux they would have you know the page。

 table Linux or one it's used depending on what process sent the system call rpc but l4 did not。

 know how to play that game l4 associated a single page table with each process with each task and so。

 in order and it would just switch to that page table so tough luck the Linux didn't have any way to。

 cause the page table to differ depending on who it sent the system call in order to deal with that。

 apparently they made a bunch of shared memory copies of the kernel one for each process and so。

 each of these shared memory copies of the kernel had exact had all of the kernel memory mapped into。

 it so they were all the same kernel data structures but each process had a dedicated。

 kernel task associated with it and therefore that basically allowed them to trick l4 into switching。

 to the appropriate page table that included that process plus the kernel you know depending on。

 which process synthesis and call it a press and you know i think that kind of worked but or i don't。

 know what they said they worked it was slow or something because there were a lot of tasks。

 anyway it's like a complicated story and i think it didn't work out very well for them。

 okay okay i see i think i think that explains oh well why this thing is harder to do than。

 what we do in xv6 okay yeah yeah this would be because there's not。

 yeah this picture in xv6 or even standard Linux is much simpler than this because。

 you're just jumping directly into the kernel and the kernel has control over direct control over。

 all the paging hardware which it doesn't have when it runs in i4 right okay i see thank you thank you。

 we're gonna ask um why um it seems like um some some tasks are more appropriate to be put。

 outside the kernel than others but this like the approach with micro kernels always seems to be。

 either everything or nothing or like either you have a monolithic kernel doing everything or。

 nothing just like i feel like paging and some other things could be very efficient inside the。

 kernel and then maybe like file systems that things that need to be swappable could be outside。

 and then even like you could maybe even have a kernel that has some functionality but you can opt。

 to not use it and provide your own is there any everything you say is absolutely well taken and。

 indeed there were a lot of microkernel or microkernel related projects um and many of them built。

 various kinds of hybrids um like there are actually a couple different versions of mock and some of them。

 were sort of hybrid kernels in which yeah there was this microkernel that knew about ipc but also。

 in the kernel was a complete Unix so for instance mock 2。5 was this hybrid within。

 but microkernel and Unix all sort of in the same kernel and you could make system calls either and。

 some stuff was built in the sort of microkernel way but some things really they were just used。

 the kernel that was in mock that was built into the mock kernel the Unix kernel that was built into。

 the mock kernel and modern you know mackOS also is built in a way that like the way you describe。

 you know mackOS has a or has a complete operating system with a file system and everything inside。

 it but it also has good support for ipc and sort of like threads all the stuff you would want to。

 build microkernel style services。 I think google's fuchsia i'm aware of also implement some of these。

 ideas now as well。 Oh yeah so anyway there you know there's no one way there were people who were。

 sort of hoping that a pure the very pure scheme could be made to work um but it was not the only。

 possible way forward。 All right thanks uh got around to my lecture but i'll see you guys。

 See you later。 Thank you。 You're welcome。 Oh i i didn't have a i have a just a remark i think it's。

 fascinating that it it's like five percent slower but it does so much more important。

 I was fascinated with that。 You mean that even though it's doing much more work it's only slightly。

 slower。 Yeah well they really sweat blood over the ipc performance。 And it's another thing to。

 remember of course is that if you start doing if you're doing significant amount of work per system。

 call like you know looking at files and directories or something then the cost of the system call or。

 the ipc itself starts to be less important。 So the combination of faster system calls plus real。

 programs do things other than making system calls。 I mean we're also like switch page tables and。

 oh yeah the others have。 Yeah although the paper i did not talk about it but the paper had some clever。

 tricks for avoiding the cost of switching page tables。 I don't know if you're a member or some。

 it's like on page six we're talking about supporting tag to bees or small spaces。

 They had some clever， ideas for not which page tables which I had not heard of before I read this paper。

 This is pretty cool。 Thank you so much。 Bye。 Bye bye。

