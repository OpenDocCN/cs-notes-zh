# CoreDumped【中英⚡图解操作系统原理｜Operating Systems Theory】 p09 P9 The Fancy Algorithms That Make Your Computer Feel Smoother -BV19h48zoEeB_p9-

This video was sponsored by Brilliant。There's something oddly satisfying about watching CPU usage spike to 100% during a benchmark test。

But one thing that always caught my attention when I was younger was that even though the CPU is completely maxed out。

 the system doesn't become unusable。

![](img/f1004676cd3d62ab172b559ff3443b86_1.png)

This is mainly because general purpose operating systems prioritize response time。

 ensuring that interactive applications stay smooth， even under heavy load。



![](img/f1004676cd3d62ab172b559ff3443b86_3.png)

![](img/f1004676cd3d62ab172b559ff3443b86_4.png)

Today we're going to talk about the CPU scheduler， one of the most important components of any operating system。

Hi friends， my name is George and this is Core Dumped。Before starting。

 please consider giving a like to this video if you enjoyed it or learned something。



![](img/f1004676cd3d62ab172b559ff3443b86_6.png)

This episode is longer than usual and it was hard to edit， but it is full of information。

 so here's the content table in case you need to jump to a specific topic。

CPU scheduling is a technique used by operating systems to determine which task or process gets to use the CPU at a given time based on specific criteria。

 one important criterion is response time， as mentioned in the introduction。

 however depending on the system， other criteria might also be important， such as CPUU utilization。

 throughput， turnaround time， and waiting time， we will explore these concepts throughout the video。

 we are going to start by building a very simple scheduler。

By far the simplest CPU scheduling algorithm is the first come first serve scheduling algorithm with this scheme the CPU is allocated to the first process that requested it。

To begin with， we must be clear about what it means to allocate the CPU to a process。

When a program is executed， it becomes a process and the operating system reserves a memory block for it。



![](img/f1004676cd3d62ab172b559ff3443b86_8.png)

Within this block， there's a memory segment called the text section。

 which contains the executable code for the program。



![](img/f1004676cd3d62ab172b559ff3443b86_10.png)

Each process has its own dedicated text section。From our computer architecture from Scratch Cose。

 we know that the CPU contains a special register called the address Reg。

 also known as the program counter。This register points to the next instruction to be executed When we say the CPU is allocated to a process。

 it means that this register is pointing to the text section of that process。

 enabling the CPU to execute instructions from it。When the CPU is reallocated to another process。

 the operating system modifies the address register。

 so it points to the executable code of the new process。

This involves a more complex operation called a context switch。

 which we've covered with more details in previous episodes。

Another important concept to understand is that processes aren't concrete entities。

 like objects or instances of structures in the traditional computer science sense。



![](img/f1004676cd3d62ab172b559ff3443b86_12.png)

Instead， processes are contexts in which the computer operates to manage these processes。

 the operating system uses a special structure called the process control block or PCB。



![](img/f1004676cd3d62ab172b559ff3443b86_14.png)

Thisstruct is not the process itself， but rather a representation of it。

 containing all the necessary information about the process such as its state， program counter。

 registers， and other management data。

![](img/f1004676cd3d62ab172b559ff3443b86_16.png)

Every time a process is created， the operating system generates a process control block to keep track of that new process。

The implementation of the first come first serve policy is easily managed with a FiIFO queue。

Which makes sense here because it operates on the principle that the first element added to the Q is the first one to be removed。

But we cannot directly push processes into this queue because processes are abstract contexts and cannot be treated as discrete elements of any data structure instead what the operating system does is push the process control block of each process into the queue。

Throughout this video I'll represent PCBs as boxes， and you'll often， if not almost always。

 hear me refer to them as processes， but remember that what enters the queue isn't actually a process。

 but it's process control block。In first come first serve， when a process is created。

 its process control block is pushed onto the tail of the queue， when the CPU is free。

 it is allocated to the process at the head of the queue。Sounds simple， right？Well not quite。

 there's a lot we're overlooking。For starters， we are assuming that a process can only get the CPU once the previous process has completed its execution。

This causes a lot of problems。First， not all processes terminate；

 many applications such as servers or background services are designed to run indefinitely。

If we allocate the CPU to a process that never ends。

 all subsequent processes would be indefinitely waiting in the queue。And second。

 if we assume that a process can only get the CPU once the previous process finishes its execution。

 we ignore an important fact， programs and execution don't use the CPU continuously。

If a task takes two minutes to execute， it doesn't mean it kept the CPU busy for the entire two minutes。

During execution， there are often periods where the program is waiting for something else。

To illustrate this， let's break it down with an example program。



![](img/f1004676cd3d62ab172b559ff3443b86_18.png)

After a quick message from Brilliant。As developers。

 one of our main goals should be to improve our problem solving abilities。With Brilliant。

 you gain access to dozens of interactive courses designed by experts。

 enabling you to learn by doing rather than just reading。

 their first principles approach helps you build a deep understanding from the ground up。

Each lesson is packed with hands-on problem solving activities that allow you to engage with concepts。

 a method proven to be six times more effective than simply watching lecture videos Brilliant is also available on your phone。

 making it easy to build real knowledge in just a few minutes a day。

 unlike mindlessly scrolling through PDFs， their latest courses including applied Python。

 creative coding and thinking and code are perfect for building foundational skills and learning real-world applications。

Helping you to develop the mindset to think like a programmer and begin creating complex programs to build games and apps。

 you can try for free 30 days of brilliant premium and get a 20% discount on your annual subscription by scanning the code on the screen。

 or by visiting brilliant。org/coreDed， also linked in the description below。



![](img/f1004676cd3d62ab172b559ff3443b86_20.png)

And now， back to the video。This program opens two text files， one containing text。

 and the other empty。

![](img/f1004676cd3d62ab172b559ff3443b86_22.png)

Its purpose is to copy the content from one file to the other， but to avoid using a lot of memory。

 it copies data in chunks， let's say eight bytes at a time。



![](img/f1004676cd3d62ab172b559ff3443b86_24.png)

We're particularly interested in the part of the program where the copying happens if we were to observe the instructions being executed by the computer。

 it had look like this。Now it might initially seem like these instructions are executed like this。

But if we were to represent it more accurately， it would look quite different。

 something more like this。Reading from and writing to files requires the program to invoke the operating system。

 as file manipulation involves interacting with hardware， in this case， the disk。In other words。

 reading and writing involve IO operations The real problem here is that IO operations are usually costly in terms of performance。

 they can take a lot to complete。These instructions right here simply cannot be executed immediately after the previous one。

 not until the IO operation managed by the system call is completed。

 which entirely depends on the IO hardware capabilities， not the CPU。As a result。

 the program doesn't use the CPU continuously， if we were to map CPU usage of a program over time。

 we would see gaps where the CPU remains idle， waiting for IO operations to finish before continuing execution。

These gaps are not the exception， but the norm。At least in systems based on the von Neuman architecture。

 which represents over 99% of modern computers， In fact。

 this behavior is so common that it has been continuously studied for decades。

Those lapses when a program is using the CPU are called CPUU bursts。

 while those time lapses when the program is waiting for an IO operation to complete are calledIO bursts。

Every process execution begins with a CPU burst that is followed by an IO burst。

 which is followed by another CPU burst， then another IO burst， and so on。

Eventually the final CPUU burst ends with a system request to terminate execution。

As I mentioned earlier， this behavior has been studied for decades。

 as the success of CPUU scheduling largely depends on it。

The durations of CPU bursts have been extensively measured。

 and while they vary between processes and systems。

 they tend to follow a predictable distribution that looks like this。

This next part is very important。Before continuing。

 take a moment to pause the video and analyze what this chart represents。

The chart shows that most processes have a large number of short CPU bursts and only a small number of long CPU bursts。

This is a critical observation for designing CPU scheduling algorithms because it highlights that processes often spend significant time waiting for IO operations。

If a scheduling algorithm doesn't account for this behavior， a lot of CPU time will be wasted。

So when a process enters an IO burst， ideally， the CPU should be allocated to a different process。

 one that isn't also waiting for IO operations。One of the main goals of CPU scheduling is to keep the CPU as busy as possible。

 allowing processes to run as fast as they can while sharing the CPU。

Notice that a process's CPU burst never starts immediately after the previous one ends。

There is always a small additional process in between， which I've represented in gray。

 I'll come back to this in a moment。 What's important to understand right now is that a scheduling algorithm must take this into account Instead of allocating the CPU to a process until it fully terminates。

 the scheduler should allocate it only until the process's current CPU burst ends。

Achieving this behavior， of course， makes the implementation of our scheduler a little more complex because now we need to consider that processes can be in different states。

Every process begins in the new state， a new process is a program that has just been launched。

 but its executable file is still being loaded into memory。

Once the program is fully loaded and all necessary resources are allocated。

 the process enters the ready state， meaning it is prepared to execute but is waiting for CPU time。

When the CPU is assigned to a process， it enters the running state。At some point。

 the process will likely make a system call， such as an IO request。

 which voluntarily returns control of the CPU to the operating system。

Keep in mind that an IO call is not only made to request some resource like manipulating a file or allocating memory。

 but to simply wait for some event to happen， such as an user keystroke or an incoming network request。

In both cases， the process moves to the waiting state until the event happens。

 or the IO operation is completed； once the request is fulfilled， the process becomes ready again。

 waiting for the scheduler to allocate CPU time。Notice that even when the IO operation is completed。

 the process does not immediately resume execution。

This happens because while the process was waiting。

 the CPU has most likely been allocated to another process。

 so even though it is now ready to continue running， it must wait for its turn。

For most of their lifetime， processes cycle between these three states， ready， running， and waiting。

Some processes， such as web servers， are designed never to terminate and remain in this cycle indefinitely。

 but for most user programs， the process eventually enters the terminated state。

These names are arbitrary and they vary across operating systems。

 the states that they represent are found on all systems， however。

Certain operating systems also more finely delineate process states。For example。

 a terminated process may not be really terminated； after making a system call to exit。

 the operating system must free all allocated resources， including memory。

Some operating systems make a clear distinction between a process that has been fully terminated and one that is still in the process of termination。

This state model explains why Qs are the fundamental data structure used in CPU scheduling。

Even though there is a specific waiting state， processes in other states。

 except the running state are also waiting。Given that hundreds of processes may be waiting at any moment。

 using cues to manage their execution order is both logical and efficient。

It is important to realize that only one process can be running on a processor core at any given time。

This means that while a queue makes sense for waiting processes。

 it does not apply to the running process。When studying CPU scheduling algorithms。

 it is necessary to be aware of another component of the operating system， the dispatcher。

When a running process enters an IO waiting state and the CPU becomes available。

 the dispatcher steps in with one single purpose， allocate the CPU to the process at the head of the ready queue。

In other words， perform the context switch。Although the running process is not stored in any queue。

 a reference to its process control block is always maintained。

 this allows the dispatcher to save the CPU state into the PCB when an interruption occurs This saved state enables the process to resume execution later the dispatcher then places the PCB into the waitinging queue。

Next， after handling the interrupted process， the dispatcher retrieves the PCB of the next process from the head of the Read queue。

 identifies it as the new running process， restores its previous CPUU state。

 including registers and the program counter。And reallocs the CPU。

 allowing the process to resume execution from where it was interrupted。If the processor supports it。

 the dispatcher is also responsible for switching to user mode before handing control to the process。

In other words， the Schr determines which process should use the CPU next by managing the Ready queuee according to a specific scheduling policy。

 while the dispatcher is responsible for the execution of the decision made by the Schr。

These additional CPU bursts caused by the dispatcher are inevitable。

 since the CPU itself is required to execute the context switch。

This delay is known as dispatch latency， the time it takes for the dispatcher to stop one process and start another。

Because the dispatcher is invoked during every context switch， it must be as fast as possible。

For this reason， the dispatcher is one of the most highly optimized components of an operating system。

 since it is implicit， the dispatch latency is usually not illustrated between processes。By the way。

 this is a variant of something known as a Gt chart。

 a bar chart that illustrates a specific schedule， showing the start and finish times of each participating process。

In first come first served scheduling， this policy is implemented using a FiIFO queue as the Ready queue。

As soon as a process makes an IO request， the CPU is immediately allocated to the process at the head of the queue。

Notice that the name first come first served can be somewhat ambiguous because the scheduler is not actually managing entire processes。

 but rather their next CPU burst。A more precise name would be first CPU Bur come first served。

That said， since many books and resources continue to refer to it as first come first served。

 we'll stick with that convention。And with that， we have the simplest CPUU scheduling algorithm。

But while it does take CPU utilization into account。

 that doesn't mean it's effective at optimizing it。To understand why。

 let's go back to our CPUU burst frequency graph。Notice that while very large CPU bursts are rare。

 their probability is never zero。The most common processes。

 those with a high number of short CPU bursts， are known as IObound processes。

These processes depend heavily on IO operations， meaning their performance would improve if the IO subsystem were faster。

But it is also possible to have processes that exhibit a high number of long CPU bursts。

Unlike IO bound processes， these processes do not benefit significantly from a faster IO subsystem。

 but instead they depend on faster CPU speeds。And for that reason。

 these are called CPUU bound processes。The problem with CPU bounded processes and the first come first serve scheduling algorithm is that they can generate a negative effect on CPU utilization。

Imagine we have one CPU bound process and some IO bound processes。

For convenience I'm going to use the same color for the IObound processes。

The CPU Bo process will get and hold the CPU for a relatively long time。During this time。

 all the other processes will finish their IO and will move into the Ready queue。

 waiting for the CPU。While the processes wait in the ready queue。

 the IO devices are idle Eventually the CPU Bo process finishes its CPU burst and moves to an IO device。

 all the IO bound processes which have short CPU bursts execute quickly and move back to the IOQs。

At this point there's no process to dispatch and the CPU sits idle。

 the CPU bound process will then move back to the ready queue and be allocated the CPU。Again。

 all the IO processes end up waiting in the ready queue until the CPU bound process is done。

See the problem here？There is a convoy effect， as all the other processes wait for the one big process to get off the CPU。

This effect results in lower CPU and device utilization than might be possible if the shorter processes were allowed to go first。

Yes， the shorter job first scheduling algorithm exists and is the next one we are going to learn。

Shortest job first assigns the CPU to the process with the shortest next CPU burst。

If two processes have the same burst length， first come， first served is used as a tiebreaker。Again。

 note that a more precise name would be shortest next CPU burst first scheduling。

 since it prioritizes the next CPU burst rather than the total process length。

Most people in books refer to it as shortest job first， so once again let's stick to that convention。

This algorithm can be implemented using a priority queue。

 where priority is determined by the length of the next CPU burst of the waiting processes。

This allows those short CPU burst processes to overtake those CPU hungry processes。

 reducing the convoy effect。This algorithm is also provably optimal。

 in that it gives the minimum average waiting time for a given set of processes。

Imagine we have four processes that arrive almost simultaneously。

 the first process next CPU burst takes two minutes to complete。

 while the others only take a few milliseconds each。In first come first serve。

 if those shorter CPU bursts arrive just after the long CPU burst。

 they would experience significant delays because they'd have to wait for the longer to finish。

On the other hand， if processes with short CPU burst are allowed to go first。

 their waiting times would be minimal， and the process with the longer CPUU burst would barely be affected。

 it would simply start a few milliseconds later， which would make little difference to it。

Moving a short process before a long one decreases the waiting time of the short process。

 more than it increases the waiting time of the long process；Consequently。

 the average waiting time decreases。Minimizing the average waiting time in a system is crucial because it represents the time that processes are ready to run。

 but cannot execute as they wait for their turn to use the CPU。

There are important considerations to keep in mind whenever a scheduler relies on priority cues。

 as we'll explore later。But there's one major issue specifically tied to shortest jobs first。

 it is impossible to implement perfectly。Because unless we could see the future。

 there is no way to know the exact length of a process's next CPU burst。

You might think that we could use the program counter to determine where the next system call occurs and how long the process will use the CPU before its next IO burst。

 however， this approach is unreliable because between the current instruction and the next system call。

 there can be loops or function calls that alter execution time。

The program's execution path may depend on external inputs， like the user input。

 making prediction even harder， for example， this function takes a user input。

 convert it to uppercase， and then print it the amount of iterations depends on the length of the user input。

Since we cannot know the exact next CPU burst， the best we can do is estimate it based on past CPU bursts。

 with the assumption that the next CPU burst will likely be similar in length to previous ones。

To approximate this value， we compute an estimate using an exponential average of previously measured CPU bursts。

I know this isn't rocket science， but if you're not into math， I'll break it down。First。

 it's important to understand that each process's CPU burst prediction depends only on its own history；

 other processes do not affect its prediction。Each process's CPU bursts form a sequence of observed durations over time。

N is the most recent CPU burst。N1 is the previous CPU burst。N minus2 is the one before that。

 and so on。N+1 is the next CPU burst， the one we want to predict。In the formula。

 that means tau subN is the predicted burst time for the process in the most recent iteration。

 while T subN is the actual burst time that was observed。

So TO subN+1 is the estimated CPU burst durationeration for the next iteration。

Since TaO subN represents the previous prediction， we can expand the formula recursively。

Since tau sub n minus1 is the prediction before that， we can expand it again。

And then with tau sub n 2， and so on。What this shows is that this term retains the process's past history。

 as a result， we don't need to store an entire list of possibly thousands of CPU burst durations。

 we only need to keep the most recent prediction。And what about this parameter alpha？Well。

 if alpha equals zero， the most recent CPU burst is completely ignored。

 and the prediction relies only on past history。If Al equals 1。

 the prediction is based only on the most recent CPU burst， ignoring all past history。Thus。

 Al controls the relative weight of the recent and the past history in our prediction。

A common choice is alpha equals12， which gives equal weight to recent and past history。

And notice that this doesn't mean all observed CPU bursts in the history are equally weighted。

By expanding the formula， we can see that each CPU burst duration is multiplied by alpha times 1 minus alpha raised to a power。

Since alpha is between 0 and 1， the term 1 minus alpha decreases exponentially。

 meaning older CPU bursts have less influence on the prediction。

This makes sense because older execution patterns are less relevant when predicting future CPU bursts Additionally。

 when a process is first created， there is no historical data。In this case。

 the initial prediction is typically set to a constant value defined by the operating system or based on the system wide average。

 for example， using a starting value of 100 milliseconds results in a predicted next CPU burst of around 72 milliseconds。

 which as you can see， is closer to recent CPU bursts than the oldest ones。



![](img/f1004676cd3d62ab172b559ff3443b86_26.png)

Here's a chart comparing the predicted versus observed CPU bursts over a longer period of time。

While not perfect， this approach provides a decent approximation。



![](img/f1004676cd3d62ab172b559ff3443b86_28.png)

But there's an important decision the dispatcher must make that we haven't discussed yet。

Imagine Pro A enters the Read queuee with a specific next CPU burst and is eventually allowed to run；

 then an instant later， process B enters the Read queuee， but Pro A is still running。The question is。

 if the remaining CPU burst of process A is longer than the next CPU burst of process B。

 should process A be interrupted to give priority to process B？

This decision depends on the scheduler if a scheduler allows running processes to be interrupted。

 we are dealing with a preemptive scheduling algorithm where the operating system can preempt currently executing processes。

In contrast， a non-preemptive scheduler will never preempt a running process。

 even if a process with a shorter CPU burst arrives in the Ready queue。

 it will have to wait until the running process completes its CPU burst and releases the CPU。

This is not a trivial decision， as the execution order of processes can change。

 depending on whether the shortest job first algorithm is preemptive or non preemptive。

And now that we understand preemption， let's discuss why it is the default choice in modern systems。

Consider a non preemptive system where a process with an extremely long neck CPU burst reaches the head of the ready queuee and is selected。

Since the system is non preemptive， there is no way to interrupt this process until it voluntarily releases the CPU。

But what if it never does？Infinite loops are not uncommon in computer science；

 if no system call is used inside the loop， the process will never return control of the CPU to the OS。

This is problematic in general purpose systems， where concurrency is a key feature。Remember。

 concurrency is a technique that allows the CPU to alternate execution between processes very quickly。

 creating the illusion that all processes are running simultaneously， however。

 in non-preemptive systems， if a CPUbound process holds the CPU indefinitely or even for long periods。

 all other processes freeze from the user's perspective。

 this is a major issue because non-preemptive systems rely on processes to behave correctly and return control in a reasonable amount of time。

Malware could exploit this by intentionally avoiding system calls to monopolize CPU time。

Whenever a scheduling policy causes a process to wait indefinitely in the Read queue。

 this is called starvation， because the process is starving for CPU time。

Even CPU bound processes can suffer from starvation for example， in shortest job first。

 a process with a long estimated CPU burst may be forced to stay in the queue indefinitely if many shorter CPU bursts continue arriving。

 the only way for this process to get CPU time is if no other process is in the ready queue。

In real world systems， this is unlikely， since hundreds of processes compete for CPU time。

In terms of concurrency， that would look something like this。Thus。

 starvation is not just about process burst length。

 but rather a consequence of the scheduling policy itself。

While shortest job first is efficient in terms of CPU utilization and waiting time。

 a general purpose operating system requires other scheduling criteria as well。

A great example of preemptive scheduling is the round Robbin algorithm。

The roundund Robbin scheduling algorithm is similar to first come first serve scheduling；

 a FiIFO queue is used as a ready queue but preemption is added to enable the system to switch between processes。

A small unit of time called a time quantum or time slice is defined here in this animation I'm using a time quantum of 100 milliseconds。

New processes are added to the tail of the Ready queuee。

The CPU Schr picks the first process from the Read queue。

 sets a timer to interrupt after one time quantum and dispatches the process。

 one of two things will then happen。The process may have a CPU burst of less than one time quantum In this case。

 the process itself will release the CPU voluntarily。

 The scheduler will then proceed to the next process in the Read queue If the CPU burst of the currently running process is longer than one time quantum。

 the timer will go off and will cause an interrupt to the operating system。

Forcing a context switch to be executed， and the process will be put at the tail of the ready queuee。

The dispatcher then selects the next process in the Ready queue。

This routine is applied consistently to every dispatched process。

 ensuring that no single process can hold onto to the CPU for long periods or indefinitely。

 which prevents other processes from being starved of CPU time。

Something very important to mention is that the timer is a physical device。

 usually embedded in the CPU circuitry， meaning preemptive scheduling can only be implemented if the hardware provides support for it。

 there's a very cool video about this on the channel， so if you want to learn more about the topic。

 go check it out。

![](img/f1004676cd3d62ab172b559ff3443b86_30.png)

![](img/f1004676cd3d62ab172b559ff3443b86_31.png)

![](img/f1004676cd3d62ab172b559ff3443b86_32.png)

Notice that when a process is preempted， it does not enter the waiting state since it did not request IO；

 instead， it goes directly into the ready state， waiting for its next time quantum。

If we need a scheduling policy that fairly distributes CPU time， round Robin is ideal；

 if there are n processes in the queue and the time quantum is Q。

 each process receive oneN of the CPU time in chunks of at most Q time units。

This ensures that once a process enters the Read queue。

 it will wait at most n minus1 Q time units before its next turn。

But while roundund Robin ensures fair CPU distribution， waiting time is not always optimal。

If the time quantum is too large， most processes will enter an IO burst before being preempted。

 causing round Robin to behave like first come first served。

At first it might seem like the obvious solution is to simply reduce the time quantum。

 but if the time quantum is too small， processes will be interrupted too frequently。

 causing a high number of contact switches。And remember。

 context switch time is pure overhead because the system does no useful work while switching。

As a result， processes will take longer to complete due to excessive interruptions。

The CPU will spend more time switching between processes than actually executing them。

And here we need to start talking about another scheduling criteria， the turnaround time。

 defined as the total time taken from a process's creation to its completion。Mathematically。

 it is the sum of the time spent waiting in the Ready queue。

 the time spent executing on the CPU and the time spent doing IO operations。

Another useful metric used as scheduling criteria is the throughput。

 defined as the number of processes that are completed per time unit。Again。

If the time quantum is smaller than the average context switch time， the CPU will be busy。

 but constantly switching between processes rather than executing them。

Maximizing CPU utilization is meaningless if the CPU is not doing useful work。

A well designed scheduling algorithm must balance CPU allocation and overhead to optimize both turnaround time and throughput。



![](img/f1004676cd3d62ab172b559ff3443b86_34.png)

The average turnaround time of a set of processes does not necessarily improve as the time quantum increases though。

 as you can see here， in general， the average turnaround time can be improved if most processes finish their next CPU burst in a single time quantum to ensure context switches happen only when necessary。



![](img/f1004676cd3d62ab172b559ff3443b86_36.png)

However， turnaround time is not always the best criterion for measuring scheduling efficacy；

 often a process can start producing output before completing execution， and as we stated earlier。

 some processes may even never terminate。Thus， another important metric is the response time。

 defined as the time from submission of a request to the first response produced。

This is not the total time needed to complete execution of a process。

 but rather how quickly it starts responding。Response time is critical because it directly affects that smooth feeling that users expect from interactive systems。

 especially when multitasking。

![](img/f1004676cd3d62ab172b559ff3443b86_38.png)

![](img/f1004676cd3d62ab172b559ff3443b86_39.png)

Round Robbin is one of the simplest ways to achieve concurrency；

 each process gets a fixed time quantum in a rotating fashion。

Once a process finishes its time quantum， the next process is allowed to run If this rotation happens fast enough。

 the system appears to be executing all processes simultaneously。

The only problem is that all computer processors have a speed limit as the number of concurrent processes increases。

 Round Robin struggles to maintain responsiveness； at some point the number of processes will be so high that each process will wait much longer before getting CPU time。

And the illusion of simultaneous execution breaks down as the average response time increases。

Decreasing the time quantum might seem like a solution； After all。

 it could make it look like processes regain CPU time more frequently。But as we've already discussed。

 reducing the time quantum too much leads to excessive context switches。

 which is just as problematic。To deal with this issue， there are three possible solutions。

Increase the processor speed， allowing context switches to happen faster。

 so we can use smaller time quantums without negatively affecting turnaround time。

Or use multiple processors， allowing processes to run in parallel and share the workload。However。

 both of these require hardware upgrades， which are not always feasible。

But the third solution can be achieved through software alone with a smarter CPU scheduler。

Think about the processes running on your computer。

 you might be playing a video game while streaming， with Outlook， a Gmail client， a file Expr。

 and other background apps all running simultaneously。

 so much stuff that round Robin causes your game to lag a bit。The question here is。

 do all these processes really need the same amount of CPU time， probably not？

If we assign higher priority to the right processes， we can increase their response time。

 making them feel smooth and responsive again from the user's perspective。Yes。

 it's true that background processes will get the CPU less often， but think about it。

 Does it really matter if your email notification is delayed by half a second。That said。

 not all background processes are trivial， some like operating system services are critical。

 the key point is this， if we can correctly identify which processes need higher priority。

 we can significantly improve overall system responsiveness without upgrading the CPU or adding more cores。

Priority scheduling is implemented using a priority queue。

 where each process is assigned an integer value representing its priority。In this example。

 I'm using 1 and zero to distinguish between high and low priority。

 but the actual range of priority values varies depending on the operating system。

Some systems may use a range from  zero to 255， others might go from  zero to 32，000。

 especially when a finer granularity of priority levels is needed。

Whether lower numbers represent higher or lower priority also depends on the system。

 in this animation， lower values indicate higher priority。

It's also common to combine multiple scheduling strategies； for example。

 priority scheduling can be combined with round Robbin to ensure fairness among processes with the same priority。

One inherent issue with priority scheduling is starvation in a heavily loaded system。

 a steady stream of higher priority processes can prevent a low priority process from ever getting the CPU。

If this sounds familiar， that's because the shortest job first algorithm is essentially a type of priority scheduling。

 where priority is based on the inverse of the predicted next CPU burst。Here's an interesting story。

The IBM 7094， a powerful mainframe computer used by NASA and the US Air Force for Scientific and military applications。

 was introduced in 1962 rumor has it that when they shut it down in 1973。

 they found a low priority process that had been submitted back in 1967 and had not yet been run。

A solution to the problem of indefinite blockage of low priority processes is aging。

Aging involves gradually increasing the priority of processes that wait in the system for a long time。

For example， if priorities range from 127， low to zero， high， we could periodically say every second。

 increase the priority of a waiting process by one。Eventually。

 even a process with an initial priority of 127 would have the highest priority in the system and would be executed。

With both priority and round robin scheduling， all processes may be placed in a single queue。

But depending on how the cues are managed， an ON search may be necessary to determine the highest priority process。

In practice， it is often easier to have separate cues for each distinct priority。

This is known as multilevel Q scheduling。And here there must be scheduling among the cues。

 One way is the one being shown on the screen right now。

 Each queue has absolute priority over lower priority cues。

 scheduling simply dispatches the process in the highest priority non empty queue。

But to avoid starving lower priority cues， we could schedule cues in another way。

We can rotate the ready cu in a round robin fashion。

 but dispatching a different amount of processes in a row depending on the priority of the queue。

To time slice among the cues。Multilevel queue scheduling is commonly used to partition processes into several separate cues based on the process type。

 making it better to schedule processes with multiple response time requirement。

It even allow us to use a different scheduling algorithm for each queue。

The foreground queue might be scheduled by a round Robbin algorithm， for example。

 while the background queue is scheduled by a first come first serve algorithm。

And that's basically what we expect from a general purpose CPU scheduler to give priority to interactive processes。

 but not to the point of starving lower priority ones。

There's just one more issue to address in a typical multilevel Q scheduling algorithm。

 processes are permanently assigned to a queue when they enter the system。

This has the advantage of low overhead， but it's also inflexible because processes don't behave the same way throughout their lifetime。

Take your email client for example。Most of the time it runs quietly in the background。

 occasionally checking for new messages。But the moment you bring it to the foreground。

 you expect it to be fast and responsive， menus， buttons， forms all need to react instantly。

 a process's CPU usage pattern and by extension， its response time requirements can change dynamically。



![](img/f1004676cd3d62ab172b559ff3443b86_41.png)

![](img/f1004676cd3d62ab172b559ff3443b86_42.png)

![](img/f1004676cd3d62ab172b559ff3443b86_43.png)

The Multilevel feedback Q algorithm was designed to adapt to these dynamic changes in behavior。

Here's how it works Every process starts in the highest priority queue If a process completes its CPU burst within a singletime quantum。

 it can return to that queue after finishing its IO if a process needs more CPU time than allowed by the time quantum。

 it's moved down to a lower priority queue。Lower priority cus have larger time quantums。

 and processes that behave more like IObound tasks can be moved back up if they complete their CPU burst in less time than the quantum assigned to the higher priority queue。

Over time， processes that have short CPU bursts will tend to stay in higher priority cues；

 In contrast， CPU bound processes will gradually sink to lower priority cues。

This is how the system adjusts process priority based on behavior automatically。

Keep in mind that this is just one example of multilevel feedback Q scheduling；

 it comes in many variations， or as I like to say， all colors and flavors。



![](img/f1004676cd3d62ab172b559ff3443b86_45.png)

Not only can the scheduling algorithm apply to each queue differ。

 but also the criteria used to decide when a process should be promoted or demoted between cues。



![](img/f1004676cd3d62ab172b559ff3443b86_47.png)

For instance， instead of relying solely on the most recently observed CPU burst to adjust a process's priority。

 the system could use a prediction based on historical data。

 which might help avoiding unnecessary Q switches in response to isolated or unusual bursts。

 whether extremely short or unexpectedly long。If you've been paying attention， you might be thinking。

W， aren't we penalizing CPU bound processes just for needing more CPU。

 it seems we are now going against the original idea of prioritizing more important processes。

 aging indeed can prevent starvation， but still， once a process is recognized as CPU bound。

 it will eventually be demoted。What's the deal here？

While this is very hard to explain without a 40 minutes master class on processes analysis。

 the best I can do now is to highlight two important facts。

IObound and interactive processes are not necessarily the same thing。

 but both are characterized by very short CPU bursts。And second。

 modern processors are extremely fast if you open a task manager right now。

 you'll see hundreds of processes running， yet if you open a resource monitor。

 you'll notice that combined they use less than 10% of total CPU time。

These two facts reveal that most of the time higher priority cues are actually empty。

 so when a process sinks to the lowest priority cue。

 it's not as doomed as it sounds being dispatched without aging is actually more probable than we might think。

Think about when your system is under heavy load， for example。

 when rendering a video or running a benchmark。CPU usage hits 100%， but your desktop stays smooth。

 your music keeps playing， and your browser remains responsive。

That's because the scheduler prioritizes everyday interactive tasks。

 while less frequent CPU heavy processes get served with any CPU cycles left over from higher priority processes。

If we put multilevel Q and multileve feedback queues side by side。

 which one sounds more general purpose to you？Many operating systems used some variation of multilevel feedback Q in the past。

 but modern systems faced new challenges， these factors introduced additional complexity and more advanced scheduling strategies were developed to handle them。

In a future episode， we'll take a closer look at how modern operating systems handle CPU scheduling。

 we'll explore the scheduling policies of Linux， Windows and BSD。

 and how they manage all these modern variables。And that's it for now。

 an intuitive introduction to CPU scheduling。Before we wrap up， a few final clarifications。

Modern systems schedule threads， not processes This allows concurrency within a single application；

 for example， one thread handles the user interface， while another performs background computations。

With Multilevel feedback Q， the user interface of a CPU hungry process can remain smooth。

 since the thread that manages the UI can maintain high priority independently of the thread that performs the heavy computations。

The IOQ shown in this video is simplified we've shown it as a FiOQ for clarity In reality the IO subsystem is more complex processes that enter the IOQ may finish in a different order than they arrived。

 just like first come first served is inefficient for CPU scheduling it's also not ideal for IO devices for instance。

 a process needing to use a graphics card shouldn't have to wait behind another process that's currently using the disk。

 all of these details however concern to another component of the operating system。The IO scheduler。

Let's wrap things up for now， there are more exciting topics coming soon。

 like race conditions and thread synchronization， so make sure to subscribe you won't want to miss it。

If you enjoyed this video or learn something new， please hit the like button。

 it's free and it helps me out a lot， see you in the next one。



![](img/f1004676cd3d62ab172b559ff3443b86_49.png)