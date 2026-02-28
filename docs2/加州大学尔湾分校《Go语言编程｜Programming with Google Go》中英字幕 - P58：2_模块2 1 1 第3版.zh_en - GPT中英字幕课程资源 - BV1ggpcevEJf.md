# 加州大学尔湾分校《Go语言编程｜Programming with Google Go》中英字幕 - P58：2_模块2 1 1 第3版.zh_en - GPT中英字幕课程资源 - BV1ggpcevEJf

![](img/f46a704bf138b7ec5e14e40406f0de30_0.png)

Module2， concurrency basics， topic 1。1 processes。So we're going to start talking about what a process is a lot of concurrent execution。

 a lot of these ideas came from operating systems okay and the job of an operating system is really to give concurrency。

 we'll talk about this to give sort of to allow programs to run concurrently so for instance。

 take the machine that I'm staring at right here， this's run this PowerPoint presentation it is running PowerPoint on it right。

But the same time it's doing other things in the background and the operating system is allowing them all to be running concurrently at the same time okay so concurrency issues。

 a lot of concurrency starts with this idea of processes and then we'll talk about threads and how they're related to processes and then we'll get to go and how it implements those things。

So a process is basically an instance of a running program。

There are things that every process has this unique to it， a big chunkunk of memory。

 So if you've got multiple processes running on a machine， every process has its own memory。

 it's a virtual virtual address base and we're not going to talk about virtual memory。

 but it has an address base Okay it has addresses zero to two gig。 this process owns them， right。

It has code， right， Every process is gonna to have its own code。 It's gonna to have its own stack。

 stacks a region of memory that handles function calls。 mostly Heap。

 which is another region of memory where you do memory allocation， stuff like that。 Sha libraries。

 actually shared libraries are shared。 So sometimes those are， in fact。

 usually those are shared between processes。 So shared libraries are actually not unique to a process。

 They're shared by definition。 So they are shared by processes。

 But each process is gonna to have its own stack， its own code， its own virtual address base。

 a bunch of other things。😊，Also， a process is going to have registers unique to it。

Registers in case you don't know， basically， they just store values inside the machine。

 They're like tiny little super fastt memories。 They just store one value， One word。

 say a program counter， right program counter。 it's the register that tells you what instruction you're executing right now。

 or really the next instruction Whats the next one you're gonna execute data registers。

 the stack pointer。 That's another register that tells you where you are on the stack stuff like that。

 So every process has this unique It was typically called context， a bunch of memory。

 a bunch of register values that are unique to the process。

 And they're all needed to executing the program correctly。

 So every process ist executing a running program。Now， an operating system does a lot of things。

 but what essentially an operating system is is something that allows multiple processes to execute concurrently。



![](img/f46a704bf138b7ec5e14e40406f0de30_2.png)

And there's a lot of complexity behind that because they have to execute at the concurrently without bumping into each other。

 Okay so one process might say， look， I have addresses 0 to 2 gig。

 The next process thinks it has the same set of addresses。

 The next process thinks it has the same set of addresses。

 And so they have to be able to access addresses。 Maybe they all accessing address 1000。

 but they're not accessing the same address 1000。 The operating system has to make sure， oh。

 this guy's 1000 is different than this guy's 100 so that they don't interfere with each other。

 So another thing the operating system has to do is make sure these processes get fair use of the processor。

 meaningan this is concurrency， right， These processes are not actually executing in parallel。

 or that's our assumption right now anyway， so。Since they're concurrently executing this process a process might get the CPU for a certain amount of time and then the next process should get its turn。

 so processes are switched quickly。 So like 20 milliseconds that's typical number I think that's a standard number and default number in Linux where a process gets to use the the process of CPU core for 20 milliseconds。

 then the operating system says okay next guy's turn and you can change that number of course。

 but what happens is it's just moving them in and out so quickly that tour uses perspective it looks like they're all running at the same time So that's the main job of an operating system and this task just to give it a name it's called scheduling。

Deciding which process runs at which time that's called the scheduling task and and operating systems do that。

 The user has the impression of parallelism， even if it's not parallel。

 And although operating systems can apply parallelism。

 it can map the operating system can map something to a different core， but generally。

 certainly right now， we're talking about single core operating system。

 and the operating system needs to give fair access to resources。 So when I say resources。

 I mean things in in the system other than the processor itself。 So there's a processor itself。

 you know maybe you give this guy 020 millisecond slice that 20 millisecond slides。

 But also other things like memory， this one gets to use this region of memory。

 This one gets to use that region of memory。 Io devices， you get to use the screen now。

 now you get your turn to using the screen so on。 So the operating system is basically managing a pile of processes and making sure they don't interfere each with each other and they get fair use of the resources so they can all complete in a timely manner。

😊，Now， this is a picture of the task manager。 So if you have a Windows machine you hit control alt delete and you'll get you get a little prompt the middle of the screen。

 it'll give you a bunch of options， you can select task manager。

 This is the task manager at the time when I made this slide Now task manager。

 what the task manager does is it shows you all the running processes。

 Now and you can see there are many running processes。 So I can't even read it from here。

 but there are a lot of processes。 And so typically like like if I were to look at the task manager for for the machine I'm looking at right now。

 this running the PowerPoint slides。 It's got PowerPoint。

 that would be one of its processes that's running。

 but there would be sort of 30 other processes running， doing other background things。

 maybe reading email， maybe serving a maybes a web server on it。 all kinds of background think。

 some security thing checking for a task all that stuff could would be going on at the same time。

 Now when I say at the same time， it's all concurrent execution。

 and maybe there's only one foreground test like this machine right here。😊。

I'm looking at it's got PowerPoint running on it， that's the foreground task， right。

 that's the foreground process。But in the background。

 it's got a bunch of other things that get their turn and they do their thing at the same time。

So you can always see the processes running just by looking at the task manager on a Windows machine anyway。

 Now say you you can see this on any machine， Mac OS Linux Mac OS just for your information it's basically a Linux So you can look at that if you wanted to see that go to the command line type P it lists all the processes running or do a PS L you can see them all and you would see similar information to this although in a less easily readable format。

 you would see the same information。 but this is the idea that an operating system is allowing all these different processes to execute at the same time or virtually at the same time concurrently。

Thank you。Module 2， concurrency basics， topic 1。2 scheduling。

So we're talking about how an operating system allows these processes to all execute concurrently。

 virtually at the same time， giving the illusion of parallel execution to a user。

So what happens is the main task of an operating system is scheduling。

 so you might have many processes that are running like in this case。

 I have three processes that I want to run Pro  one，2， and three。

 and this little chart that I'm showing is execution over time。

 so time is increasing time is increasing down。And these little vertical bars， they're colored。

 And each one's aligned with a process。 And they're just showing how how basically the operating system is making sure that one process gets a turn。

 or process run for ones first。 Then it gives process to a turn。 Then it gives process 3 a turn。

 Then it goes back， maybe goes back to one again， so on。 Now。

 these scheduling decisions There are many different scheduling algorithms。 ways of doing scheduling。

 like， for instance， what we're showing here is basically what's called round robin。

 So you give each one a fair amount of time。 Like in this case， I'm just going 1，2，3，1，2，3，1，2。

3 over and over。 everybody gets the same slice over time。 sort of a fair way to distribute。

 This is not necessarily how scheduling is done。 Like， for instance。

 you'll get maybe you have a higher priority process。 Some processes are more important than others。

 right， for instance。😊，Some processes， maybe they're interacting with the human。

 So they need to be prioritized better than something in the background。 Okay so in that case。

 the scheduling algorithm built in the operating system might consider that and say， well。

 you higher priority。 I will let you have more time than I let this other task run or something like that。

 or I will let you maybe process ones higher priority。 So it gets to it occurs。

 It gets be scheduled more frequently than process two or three， something like that。

 There are many different scheduling algorithms。 And you get a lot of this。

 especially with embedded systems where。You get certain tasks and an embedded system。

Or an IoT device that are critical like if you take like a car， okay， let's take a car。

 car's got many processors actually and lots of things running。

Say it's got a processor that's processor doing antilock braking So you hit the brake and the car's got the pals。

 the brake pads have to come down on the wheel and break it。 Antilock breaking。

 that would be considered a high priority process。 Okay now， on the other hand。

 maybe you got a stereo running。 that is a low priority processor。

 So what the processor should do if they were both running on the same processor。

 which they typically are not。 But if they were。 then you would say that that antilock breaking thing。

 that's got to have higher priority。 So even if you're in the middle of playing some stereo music。

 that task would have to be stopped。 So the operating system will say， okay， I'm putting you aside。

 somebody just hit the brakes， we've got to go to the high priority task。 the antilock breaking。So。😊。

There are many different scheduling algorithms for operating systems to handle prioritization and meeting deadlines and all this and we won't go into it。

 but scheduling is the main task in operating system。Now。

 when the operating system moves from one process to another。

 when it starts a process running and then it stops it and starts another process running。

 that act of switching is called a context switch。

![](img/f46a704bf138b7ec5e14e40406f0de30_4.png)

So what we're showing here， little graph where time is increasing down。

 you got process A is one column on the left， process B is another column on the right。Now。

 when you got the vertical line， like at the beginning， process A is running。

Vert line under process A。 Then there's this blue area， this labeled context switch。

 And that's where it's switching from process A to process B。 That's the operating system。

 changing from process A to process B。 Then you can see process B runs at vertical line under process B。

 And then's another context switch from process B back to process A。 Again。

 that's the operating system。😊，So。😊，Basically what's happening here is that when you're running a process。

 when you want to stop it or like running process A， you want to start running process B。

 what you have to do is take the state， the current state of process A， and save it somewhere。😡。

So for later use right and then you have to bring in the state of process B， let process B run。

 and then later when process B is running you want to go back to A。

 you take that state of process A that you saved and you bring that back in so it can start from where it left off。

😡，Now when I said the state， that's called the context， okay， and the state。

 it includes all those things that are unique to a process。So it's virtual memory system。

 like which parts of memory it can access which you can， all this register values。

 the program counter of values， the stack point or all that stuff， it's code， right。

 all that stuff is unique to a process。 So we call that the state sort of memory and registers associated uniquely with the process。

When you move when you do a context switch， you take that context， all that state information。

 you save it to memory somewhere the one for the process that you're throwing out。

 And then for process B， if you bring that one in， you find its state on memory and bring it all back in。

 bring in its virtual address system and bring in its register values and all that so that process B can continue from where it left off And then when you go back to process A。

 you do a swap again。 process B state is context is saved to memory somewhere and then process A's state is brought in from memory back into the registers where it belongs and process A can continue where it left off。

 So this context switch is performed by the operating system so。

If we look at the the chart I show there， right there， there's a time where process A is running。

 then there's a context switch， then process B， then the context switch then process A。

 those two context switch times。 That's the operating system itself running。

 What's called the kernel。 The kernel of the operating system。

 So the main main code of the operating system。 Let's think of it like that。

 And the context switch is the kernel of the operating system running。 It's executing at that time。

 And typically what happens is。😊，You got a timer， so these processes all have timers when the program。

 when the operating system starts process a running， it sets a timer， maybe a10。

 maybe 20 millisecond timer。And when that timer goes off。

 process A is stopped and the operating system is executed， then it does the context switch。

 and then it starts process B， and it sets a timer again。 So when the timer runs out again。

 then it the operating system runs again， does the context switch and the process continues forever or the process this whole procedure continues forever or as long as the machine is powered on。

Thank you。Module 2， concurrency basics， topic 1。3， threads and go routines。

So we've talked about what a process is， now I want to define what a thread is。

So threads versus processes used to be that there were only processes。Now。

 this is way back back when you first create when Unix was first created， right。

 they just had prothe at first and they used to say， look。

 see one downside of prothe is it that the context switching time can be long because the context it requires context switch requires taking data。

 writing it to memory and then reading stuff from memory back into registers right so there's a lot of memory access and memory access can be slow So switching。

 doing a context switch between two processes that can be slow。😊，And， you know。

 you want the operating system to be fast， don't want to waste time doing that。

 So switches switching the switching process rather， often to speed it up。People said， look。

 let's make threads。 Now， they would call actually originally called lightweight processes。

 But what a thread is。It's like a process， but it has less context， okay。

 it shares some of the context with other threads in the process。

So one process can have multiple threads inside it and the threads share a decent amount of context。

 So if you look at the top picture， I show a process right and it's got these two blocks of things that are unique to the process。

 you know， it's virtual memory would page table that sort of thing file descriptors， you know。

 it's stack， Its program counter。 you know all these it's registers。

 those are all unique to a process。 Now notice how I separated them into two。

 I have those that little orange block and the green block right but all of those are unique to a process。

😊，Now， now that once you start having threads， you can say you can have multiple threads in one process。

 so you can see the green chunk， the green rectangle as a as a thread right so you can think of that first that process picture as just a process with one thread in it one green thread and with one code and each thread is associated with a piece of code that is executing。

 So so the stack is so since the stack is associated with the code executing。

 you got a stack and you got some registered data registers are unique to a thread。😊。

But in the bottom picture， what I'm showing is one process with three threads inside it。Now。

 each one of these threads does have unique context， right， The stack is unique for every thread。

 The code is unique for every thread。 The data registers are unique for every thread。

 So there is unique context between different threads。

 but they also share context like that stuff in orange。 the virtual memory system。 that's the same。

 right The file script is those are the same so。😊，You know， this is an exhaustive list。

 these pictures。 But the point， though， is that these threads， they have unique context。

 but it's much less different than unique context between two different processes。

 So when you do a context switch between two processes。

 that might take you a long time because there's a lot of context。 That's unique。

 But with two threads， when you go from one thread to the next in the same process。

 it's much faster because there's less context， less data that you have to write to memory and read back from memory when you do a context switch。

 So and now what happens in operating systems is that they instead of scheduling processes they schedule thread by thread So they say okay。

 this thread runs and that thread runs than that one where in the old days is it used to be processed by process now they've gone to this sort of thread levell granularity。

 It's the same problem。 but the level granularity is different。

 they do one thread at a time and they schedule accordingly。😊，Now， go routines。

 Now we're moving to go。 all that other stuff that I talked about。 It was sort of generic。

 independent of the particular language。 It was talking about operating systems in general。 Now。

 we're going to talk a little bit about go。 Go has what are called go routines。

 Go routines are basically a thread， but in go。Many go routines execute within a single operating system thread。

 So remember there was this hierarchy where I said。

 look there's a process and it's got many threads in it right that's from the operating system point of view。

 You can have many threads inside a process， maybe preciselyly as one thread。

 what you call a main thread， but it might have multiple threads。Now， what Go does is it says， look。

 it takes process with one thread in it， one main thread。

And you can have multiple go routines that are all executing in that same thread。

 So from the operating system point of view。All it does is schedule the main thread。

But then then within go， you can have multiple go routines that are all executing within that thread。

 all alternating within that thread。 So maybe go routine one executes then two then three all the while from the operating system point of view。

 nothing is changing。 It's got its main thread running。

 but inside of go go can start switching basically these go routines。

 which are like threads inside the main thread。So that process of doing the switching。

 determining which go routine is executing at what time， that scheduling process。

 that's done by what's called the go runtime scheduler。

The Go runtime schedule it does scheduling within an operating system thread。



![](img/f46a704bf138b7ec5e14e40406f0de30_6.png)

So you see how the scheduling task is sort of separated between the operating system and the go runtime scheduler。

 the operating system schedules which thread， which operating system thread runs at a time and then once the main thread is running。

 your go program is running within a main thread or an operating system thread once that's running the runtime scheduler can choose different go routines to execute at different times underneath that main thread。

Now， they also， the go runtime scheduler uses a logical processor， this logical processor。

Is mapped to a to a thread。 so typically， like default， you're gonna have one logical processor。

 mapped to a main thread。 And then the go routine is going to run on that logical processor。

 which means it's running in that main thread。 Now。

 notice that since all these go routines are basically running in one thread。 One main thread。

 There is not an opportunity for actual parallelism like this。 right， It's all concurrent。

 You're executing one go routine or the next or the next at a time。 But what you can do。

 and we'll touch on this later。 is you can as a programmer。 you can say， look。

 I don't want one logical processor。 I want two logical processor or three or4。

 And you would do this according to how many coreords you had， presumably。

 that would be sort of the obvious way。 You might say， look， I got four chds。

 I'm gonna to have four logical processor。 Then what'll happen is the go。The go runtime scheduler。

 it'll take these go routines and map them to different logical processors。

 Each logical processor can be mapped to a different operating system thread and the operating system can map those threads to different cores So you can sort of allow there is a way to change the settings so that you don't have just one logical processor。

 you have multiple assuming and if you had cores that would allow multiple cores。

 would that would allow you to exploit those cores during execution。

 Now still this task of hardware mapping， determining this go routine which core is it on that task is still not done by by the programmer。

 but the programmer can determine how many logical processors are going to be used and by default itll be one in which case has got to be concurrent behavior but you can increase that if you want to which would allow the go the go runtime and the operating system to do parallel scheduling if it wanted to。

Thank you。