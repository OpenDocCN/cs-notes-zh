# CoreDumped【中英⚡图解操作系统原理｜Operating Systems Theory】 p11 P11 Why Can't Programs Access Each Other's Memory？ -BV19h48zoEeB_p11-

This video was sponsored by Brilliant If I were to ask you what the most important part of a computer is right after the CPU。

 the answer would most likely be memory。We've previously talked about circuits that can hold a binary value。

 either using transistors or capacitors to create a memory cell that can store a1 or a0。

We learned that physically speaking， memory is essentially a giant grid of these tiny cells。

 where each cell can be accessed using a binary value called an address。

This term address originates from hardware design。Since each memory cell has a unique position in this matrix。

 a binary address， combined with additional circuitry can be used to pinpoint the exact cell we want to read from or write to。

With a single bit of information， we can represent basic values like true or false。Day or night。

Black or white。But that's it， only data with two possible states。To represent more complex data。

 we need more bits。That's why computers don't associate an address with just one bit。

 but with several。In computer science， this unit is traditionally called a word。

 but the more common term you'll hear is a bitete。A byte typically consists of8 bits。

 and that's a lot more useful because8 bits allows to represent values with up to 256 different states。

 accessible with a single memory address。The good news is that。

 as I explained in my videos about building memory from transistors， we， the developers。

 don't have to think of memory as a grid of circuits。From our perspective。

 memory behaves like a massive array of bytes， each with its own unique address。

Memory is central to the operation of a modern computer system。

 because main memory and the registers built into each CPU core are the only general purpose storage that the CPU can access directly。



![](img/694ff6e31e42f32bdc4e6409f49f0d95_1.png)

![](img/694ff6e31e42f32bdc4e6409f49f0d95_2.png)

There are machine instructions like load and store that take memory addresses as arguments to make the CPU read from specific memory locations。

 or write to a specific memory location。

![](img/694ff6e31e42f32bdc4e6409f49f0d95_4.png)

![](img/694ff6e31e42f32bdc4e6409f49f0d95_5.png)

But there are no instructions that take disk addresses。Therefore。

 any instruction being executed and any data it operates on must reside in one of these direct access storage devices。

If the data isn't already in memory， it must be moved there before the CPU can use it。For example。

 even a trivial operation like incrementing a counter involves multiple memory operations。

Each instruction requires a memory read because the CPU must fetch it from memory before it can execute it。

The load instruction tells the CPU to read a value from a specific memory address。

 that's another memory read operation。And the store instruction tells the CPU to write a value to a specific memory location。

 which is a memory right operation。Okay， but up to this point。

 I haven't said anything you haven't already heard in previous videos。

 so what's the point of today's episode？Well， once again。

 concurrency makes things a lot more complicated。Hi friends。

 my name is George and this is Core Dumped。Before starting， consider giving this video a like。

 it helps others discover my content， which， by the way is free。As we've discussed before。

 running multiple programs simultaneously on the same system introduces several challenges。

When programs run concurrently， they must share the CPU。

 so scheduling algorithms are used to ensure fair access to computing time。

But concurrency doesn't just affect CPU time， it also affects memory。

Programs typically reside on disk， but as we mentioned earlier。

 there are no machine instructions that use disk addresses。



![](img/694ff6e31e42f32bdc4e6409f49f0d95_7.png)

So when we launch a program， it must be loaded into memory so the CPU can fetch and execute its instructions and data。

 becoming a process。

![](img/694ff6e31e42f32bdc4e6409f49f0d95_9.png)

![](img/694ff6e31e42f32bdc4e6409f49f0d95_10.png)

Each process also needs memory for variables， temporary values， and other kind of data。

The total memory allocated to a process is known as its address space。

Here's the rule we want to establish by default， a process should never be able to access the address space of another process。



![](img/694ff6e31e42f32bdc4e6409f49f0d95_12.png)

![](img/694ff6e31e42f32bdc4e6409f49f0d95_13.png)

But why？Well， let me give you an example。Imagine two processes running concurrently。

 the first one displays a payment form that allows a user to send money to someone else。

As the user fills out the form， their input is stored in a buffer somewhere in that process's address space。

If memory access restrictions are not enforced， the second process or any other process could simply execute a small piece of code using load and store instructions to read that payment data from the first process's address space。

 copy it into its own address space， and send it over the network to a malicious actor。

That would be a serious problem， especially considering how casually we install apps without knowing who developed them。

And since the operating system itself also relies on memory to manage the system。

 unprotected memory access is something no modern OS can afford to overlook。

And it's not just reading that's dangerous； if a process could access another process's address space。

 it could also write to it。A malicious process could alter a buffer to change the payment amount or the recipient。

 without the user ever knowing。Worse yet， without memory protection。

 one process could even modify another process's code， or even the code of the operating system。

 injecting malicious executable code to make it do virtually anything。

The address space of a process is sacred； a process should never be able to read from or write to the memory of another。

As with most things in computer science， there are multiple ways to enforce this rule。

 but doing it entirely in software is not one of them。As mentioned earlier。

 memory operations happen constantly while a process is running。

If the operating system had to manually check for illegal memory access for each process that is currently using the CPU。

 it would need to run extra code on every single memory operation the user process performs。

That's not a trivial task， since instructions need to be fetched from memory。

 for every instruction the user process executes， the operating system might have to run several more just to validate the memory access。

 introducing a massive performance overhead， so hardware support is needed。

Now I know circuitry usually scares developers， especially if you're trying to make sense of it just from textbooks。



![](img/694ff6e31e42f32bdc4e6409f49f0d95_15.png)

That's why we focus on breaking things down visually here and why Brilliant is such a great companion for this kind of learning。

If you're someone who loves learning new things and building real skills。

 but feels like endlessly scrolling through PDFs isn't the way to do it， then brilliant is for you。

Brilliant is a learning platform built around active problem solving。

Every lesson is designed to let you play with ideas。

 using a first principles approach that helps you understand concepts from the ground up。



![](img/694ff6e31e42f32bdc4e6409f49f0d95_17.png)

You'll stay motivated with a perfect blend of engaging challenges， daily streaks。

 and competitive features that actually make learning feel rewarding。



![](img/694ff6e31e42f32bdc4e6409f49f0d95_19.png)

All content on Briiant is crafted by an award winning team of teachers。

 researchers and professionals from Stanford， MIT， Caltech， Microsoft， Google， and more。



![](img/694ff6e31e42f32bdc4e6409f49f0d95_21.png)

![](img/694ff6e31e42f32bdc4e6409f49f0d95_22.png)

The best part is brilliant is available right on your phone， so instead of passively scrolling PDFs。

 you can learn a little every day wherever you are。

Courses like thinking in code and programming with variables help you develop the mindset of a programmer by teaching you to break down complex problems into logical。

 manageable parts， and also help you develop an intuition for computer logic as you learn to design and debug real programs。

To try everything brilliant has to offer for free for a full 30 days and get 20% off in your annual subscription。

 visit brilliant。org/coredumped or scan the QR code on screen。

 or click on the link in the description below。

![](img/694ff6e31e42f32bdc4e6409f49f0d95_24.png)

And now back to the video。You might think we need to modify the memory itself， but actually。

 memory remains untouched in this design。While a process runs。

 the memory unit sees only a stream of memory addresses coming from the CPU through this set of parallel wires called the address bus。

The main memory does not know how those addresses are generated or what they are for。

So handling this process directly in memory is not the best way。



![](img/694ff6e31e42f32bdc4e6409f49f0d95_26.png)

Now I don't want to draw a million wires， so I'll use the simpler architecture I usually show here in the channel。

There's little to no use for general purpose components in this context。



![](img/694ff6e31e42f32bdc4e6409f49f0d95_28.png)

We'll use two special registers to enforce memory boundaries。

The base register points to the smallest legal physical memory address of the process。

The limit register defines the size of the addressable range for that process。With these registers。

 we can check whether any address a process tries to access falls within its own address space。

In code terms， we're checking whether， the address is greater than or equal to the base。

And lower than the sum of the base， plus the limit。

It's the same logic the OS would follow if the check were done in software。

 but here we're translating it into hardware。Note that the sum of the base and limit gives the upper bound of the address space。

 but this bound is exclusive。Which is why we check that the address is less than not equal to the upper bound。



![](img/694ff6e31e42f32bdc4e6409f49f0d95_30.png)

The good news is that calculating this upper bound is as simple as adding the contents of the base and limit registers using a binary adder。

 which we covered in a previous episode。Remember， we want to validate the address being passed on every single memory operation。

 and since every address passes through the address bus， we can intercept the address right there。

Now that we have all the values we need， we can move on to the comparisons。

To compare the address with the boundaries， we'll use binary comparators。

 which is the most straightforward method。If you're new to this channel。

 don't let this circuit intimidate you， it's just a combination of logic gates arranged to produce a specific result based on its inputs。

In this case， the comparator receives two binary numbers， A and B， and produces three outputs。

Only one of these outputs is active at a time， depending on the inputs。

One output activates if a equals B， another if A is less than B， and another if A is greater than B。

We'll abstract this logic into a simple component called a binary comparator。

We'll use one comparator to check whether the address is greater than or equal to the base。

 and another to check whether it's less than the upper bound。But remember。

 both conditions must be true for the address to be valid。

 so we'll combine the outputs using an and gate。And that's it The wire at the end of our circuit will only be active if the address pass to memory falls within the address space defined by the base and limit registers。

But how can a single wire prevent illegal memory access？Let's quickly recall how memory works。

Sending an address through the address bus doesn't trigger a memory operation on its own。

To actually perform a memory operation， we must specify whether we want to read from or write to that address；

 this is done by activating either the Read Enable or write En signal。When ReadEnable is active。

 memory places the contents of the address onto the database。When WEn is active。

 memoryory overwrites the contents at the specified address using the data provided on the data bus。

So the simplest way to block illegal memory access is to use the output of our address validator circuit to gate the read and write signals。

That way， if an instruction attempts to access an address outside the process's address space。

 the hardware will block the read or write signal from reaching the memory module。In other words。

 memory will only receive the Read or write enable signal if the address is within the bounds of the current process's address space。

Another good idea is to add a few extra logic gates to detect when a process attempts to access an illegal address。

That way， the circuitry not only blocks the memory operation。

 but also triggers a hardware signal to the CPU that immediately interrupts the running process and invokes the operating system。

 which then handles the violation， most likely by terminating the process。



![](img/694ff6e31e42f32bdc4e6409f49f0d95_32.png)

On UniX like systems， when this signal is caught by the operating system。

 it terminates the process and displays the error message， segmentation fault。

 meaning the process tried to access memory it wasn't allowed to。



![](img/694ff6e31e42f32bdc4e6409f49f0d95_34.png)

Now， something that should be very clear at this point is that the operating system doesn't need to execute any additional instructions to make this circuitry work。

Because of the way everything is wired， the circuit automatically intercepts any memory operation。

 regardless of its purpose and immediately performs the validation。As I'll show in a moment。

 the only responsibility of the operating system is to set the correct values in the base and limit registers before dispatching the CPU to the user process。

All this circuitry is of course embedded inside the CPU。

Just keep in mind that for any of this to work as expected， the CPU must support operational modes。

These memory management registers， like the base and limit Regs。

 must be implemented as privileged registers， which can only be modified by the operating system。

This becomes another responsibility of the operating system during a context switch。



![](img/694ff6e31e42f32bdc4e6409f49f0d95_36.png)

When the CPUU is reassigned from one process to another。

 the OS not only captures the state of the interrupted process and restores the state for the new process。

 but also updates the memory bounds， the base and limit registers to match the address space of the incoming process。

Once everything is properly set up， the OS switches the CPU into user mode。

 allowing the user process to run。But in this mode， the CPU cannot modify the privileged registers。

So the process is limited to using only the memory that the operating system has explicitly allocated to it。

And that's the basic idea behind how the operating system， with support from the hardware。

 prevents user processes from accessing each other's memory。



![](img/694ff6e31e42f32bdc4e6409f49f0d95_38.png)

We're not done with memory just yet， so far we've implemented protection for processes running concurrently。

 but what happens when multiple processes are running and there's no more memory available for new ones。

That's a topic for a future episode where we'll explore paging。

 a memory management technique that allows a computer to use more memory than is physically available。

So make sure to subscribe， you won't want to miss it。See you in the next one。



![](img/694ff6e31e42f32bdc4e6409f49f0d95_40.png)