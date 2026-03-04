# CoreDumped【中英⚡图解操作系统原理｜Operating Systems Theory】 p05 P5 Why Are Threads Needed On Single Core Processors -BV19h48zoEeB_p5-

This video was sponsored by Brilliant。Threads， a subject in computer science that many people are afraid of。

 and no wonder it seems complicated。

![](img/040690c5232d0f1c5705435c7838abc0_1.png)

Okay， no， I'm just kidding today we'll explore the fundamentals of threads and how they leverage concurrency to optimize computer resource utilization。



![](img/040690c5232d0f1c5705435c7838abc0_3.png)

Hi friends， my name is George， and this is Core Dumped。As long as you get these four concepts。

 threads are surprisingly easy to understand。The premise is simple， in multiproces systems。

 if we have one CPU and multiple running processes。

 the operating system makes those processes share the CPU by alternating access between them。

This happens very fast， so fast in fact that the user is under the illusion that all processes are running simultaneously。

This technique is known as concurrency and along with another technique called CPUU scheduling。

 it is responsible for the smooth multitasking experience we enjoy on our computers。

But multitasking is only the well known purpose of concurrency and CPU scheduling；

 there's another less obvious purpose， maximizing the use of computer resources。

We'll dive deeper into this in my video about CPU scheduling For now what we need to know is that while a process is often defined as a program in execution。

 it doesn't necessarily mean the process is always using the CPU。

 even if the CPU is allocated to that process。For example。

 a process might be waiting for an IO resource。In that scenario。

 allocating the CPU to that process would be inefficient because it can't execute instructions until the requested IO resource is ready。

So instead， it makes sense to allocate the CPU to a different process。

 one that's ready to execute instructions。This is the second reason why concurrency is so important。

 it's not just about running multiple programs at once。

 it's also about filling those little gaps when a process can't use the CPU by assigning it to another process that can。

Up until now in this series， we've treated processes as the fundamental unit of execution。

 so we've assumed there's nothing more basic than a process for scheduling purposes。

 so we can't employ concurrency for executable entities within the same process。

If this sounds confusing， what I'm trying to say is that tasks within the same program。

 like two functions， for example， cannot run asynchronously under the traditional process approach。

This makes sense if you've watched my video on processes。

 remember each process has one program counter that points to the instruction where it is interrupted when the CPU is allocated to other process。

 but we cannot alternate the CPU between two functions that are part of the same process because with a single program counter we can't keep track where both are interrupted one of the functions must wait for the other to finish executing。

But why would we need concurrency inside a process in the first place。

 I mean if we wanted two pieces of code to run concurrently and cooperate。

 couldn't we just put that code in separate processes and use interprocess communication to coordinate their actions？

Well， yes。But using IPC isn't always intuitive， sometimes different pieces of code that contribute to a main goal are so correlated that putting them in different processes just feels wrong。

There are many situations where concurrency within a process is incredibly useful。

Think about a server that receives requests on Port 3000。

 where its sole purpose is to return a profile image associated with each client。

When a client sends a request， the server accepts it。

 processes it by searching and reading the image from disk， and once the image is loaded into memory。

 responds by sending the image back to the client。Because images are stored as files on disk。

 a very costly IO operation is required to find the image and load it in memory。As a result。

 processing a request can take significantly longer than simply accepting or responding to it。

These steps are executed sequentially and obviously take only a few milliseconds。

 so for a single client it works just fine， but with multiple clients， complications arise。

If five requests arrive at approximately the same time。

 the server will accept the first one quickly but then spend significant time processing it；

 the second request will only be handled once the first is completed and so on。

This creates a bottleneck with later requests waiting a long time to be attended to。Now。

 with five requests， the bottleneck is not that much of a problem， but imagine a thousand requests。

And here we can see the real problem。Notice the gray gaps in the timeline。

 these represent periods where the CPU sits idle， doing nothing This is wasted computational time。

 time that could have been used to accept and begin processing other clients requests。

When one task is unable to execute because another task is running。

 despite the two being independent， we call it a blocking effect。For a long time。

 the solution to this problem was as follows。There's a main process that listens for requests。

 which we'll call the listener process。Every time a client sends a request。

 instead of handling it directly， the listener process creates a whole new process to attend to that specific client。

This way， if another client sends a request， it won't wait until the previous request is completely handled because the process that listens and accepts the requests runs concurrently with the one serving the previous client。

In other words， this method allows taking advantage of concurrency to use the CPU as much as possible。

While clever， this approach isn't perfect， remember。

 each process is like a self contained context with its own properties， including an address space。

 creating an entire process for every client might work for a few hundred clients。

 but when scaling to thousands， it becomes inefficient in terms of memory usage。Additionally。

 spawning a new process is not a trivial operation， it consumes processing time。

 so even though the goal is to utilize idle CPU gaps。

 a portion of that time is actually spent creating the new process itself。Moreover。

 if the server needs to handle some kind of global state。

 all child processes must be synchronized to keep track of it； this requires some form of IPC。

 complicating the implementation。Although processes are one of the most important concepts in computer science。

 they aren't perfect。Let's discuss the solution。After a quick message from Brilliant。



![](img/040690c5232d0f1c5705435c7838abc0_5.png)

There's one fact we all know about traditional studying。

 reading books might not always be the most effective method。

 but fortunately Brilliant is here to help With Brilliant。

 you have access to dozens of different courses designed by professionals and specifically crafted so you can interact with examples and improve your problem solving skills through small challenges。

Remember， one of the most important aspects of being a good developer is the ability to solve problems。

The best part is you don't have to spend hours because Brilliant is designed to help you learn a little every day through small lessons。

 even better， you can access it anywhere since Bri is available on your phone。

You can access all sorts of courses， from math and data science lessons to programming oriented courses like thinking and code and how large language models work。



![](img/040690c5232d0f1c5705435c7838abc0_7.png)

You can try everything Brit has to offer for free for a full 30 days and get 20% off in your annual subscription by accessing brilliant。

org/codumped， or by using the link in the description below。



![](img/040690c5232d0f1c5705435c7838abc0_9.png)

![](img/040690c5232d0f1c5705435c7838abc0_10.png)

And now back to the video， since the concept of a process is very useful， we can't just discard it。

 but we can modify it slightly to allow concurrency within the executable code of a single process。

Remember， in general terms， a process comprises an ID， a program counter， a register set。

 an address space， and other resources such as open files and IO devices。As I explained earlier。

 the main limitation is that a single program counter doesn't allow the process control block。

 the structure the OS uses to represent processes， to keep track of more than one task at a time。



![](img/040690c5232d0f1c5705435c7838abc0_12.png)

The solution is to stop associating the program counter directly with the process。

 and instead assign a program counter to each interexecutable entity that we want to run concurrently within the process。

These inner entities are what we call threads。By no longer limiting each process to a single program counter。

 we can now create a new thread whenever we need code within the same process to run concurrently。



![](img/040690c5232d0f1c5705435c7838abc0_14.png)

This solves the blocking problem without creating new processes；

 if one of the threads needs an IO resource， such as loading the contents of a file into an array。

 the other threads can continue executing without being blocked。



![](img/040690c5232d0f1c5705435c7838abc0_16.png)

While threads share the entire address space of the process they belong to。

 they cannot share a CPU state， because threads are going to be interrupted to allocate the CPU to other threads。

 we need to capture the state of each thread so that when the CPU is reallocated。

 its state can be restored。Therefore， if each thread has its own program counter。

 it also must have its own register set， flags， accumulators， etc， essentially its own CPU state。



![](img/040690c5232d0f1c5705435c7838abc0_18.png)

And note that this includes a separate stack pointer。Remember。

 the stack is a fast and efficient way to organize and access local variables in memory。

If two functions in the same process run concurrently and share the same stack。

 they could easily overwrite each other's data。

![](img/040690c5232d0f1c5705435c7838abc0_20.png)

Hence， each thread must have its own stack。And something that I want to make sure is very clear is that the fact that each thread has its own stack doesn't mean that they cannot read from or write to each other's。

This makes perfect sense if we consider the address space as a property of the process。

 not the threads， since the stacks are located within that shared address space。

 nothing prevents a thread from accessing another thread stack。

Whether if you should do it or not is a completely different discussion， but generally。

 unless you really know what you're doing， it's best to avoid accessing other thread stacks directly。

If threads within the same process need to communicate by sharing memory。

 the heap is more appropriate for that， since by its nature。

 the data stored in the heap is not organized in a predictable way anyway。But even with the heap。

 caution is still required， if one thread is reading from a block of memory while another is writing to it。

 the results can be disastrous。Synchronizing concurrent tasks is so critical that mechanisms for doing so are implemented directly in hardware I'll cover this in a future episode。

 so make sure to subscribe。

![](img/040690c5232d0f1c5705435c7838abc0_22.png)

Also， because we are not completely discarding the concept of a process。

 address spaces of different processes are still isolated。

 so while sibling processes share memory by default。

 if threads from different processes want to share data， interprocess communication is needed。



![](img/040690c5232d0f1c5705435c7838abc0_24.png)

Replacing the traditional multi process approach with the multi threadreaded approach requires reimplementing the process control block。



![](img/040690c5232d0f1c5705435c7838abc0_26.png)

The most obvious path here would be use a second structure to represent threads。

While implementation details can vary by platform， the most common approach is the one used in the Linux kernel。

 where both processes and threads are represented by the same structure called task。



![](img/040690c5232d0f1c5705435c7838abc0_28.png)

If you ask me， I'd said this is a perfect example of good naming and programming。

 because it abstracts away the distinction between processes and threads。

 so instead of describing concurrency as alternating CPU access between processes， threads， or both。

 we can simply describe it as alternating tasks。This implementation is more intuitive if we want to use a single scheduler both for threads and processes。



![](img/040690c5232d0f1c5705435c7838abc0_30.png)

Regardless of the approach， doing this requires that every process has at least one thread called the main thread。

Whenever a new process is created， the operating system automatically creates this thread。

So even if a process doesn't rely on multi threadreading。

 the operating system can allocate the CPU to it by scheduling its main thread。

Whether a process starts with a fixed number of additional threads or can spawn threads dynamically。

 depends on the operating system's implementation。Most mainstream operating systems prefer the dynamic approach where each process starts as a single threaded process。

 and additional threads are created at runtime if needed。



![](img/040690c5232d0f1c5705435c7838abc0_32.png)

This of course， increases the complexity of the operating system's internal implementation。

 as it must provide system calls for dynamic thread creation。

 but it's the preferred method because in many cases it's impossible to know at compile time how many threads will be needed at runtime。

Okay， that's a lot of information before we discuss how all of this applies to our server example。

 there's one last thing we need to know。In many implementations。

 because the main thread identifies the process it belongs to。

 if other threads are spawned and the main thread terminates its execution。

 the execution of all the other threads will immediately terminate。

There are multiple ways to handle this problem， but that's a topic for another video。



![](img/040690c5232d0f1c5705435c7838abc0_34.png)

Back to our server example， with the multi threadreading approach。

 we can spawn a new thread for each incoming client。

 achieving a similar effect to the multi processces approach， but with far less memory consumption。

Additionally， there can be a performance improvement when using threads。

 because the system calls used to create threads are generally completed much faster than those used to create new processes。

The reasons for this should be obvious at this point。And that being said。

 we should now define what a thread is， but first， we'll define what a thread is not。



![](img/040690c5232d0f1c5705435c7838abc0_36.png)

A thread is not a function。 Any code that a thread executes is in the text section of the memory layout of the process。

 The thread doesn't contain code。 It points to the code through its program counter。

 This means multiple threads can point to the exact same executable code。

This is precisely what happens in our server example。

 since all the requests need to be handled in the same way。

 all the handler threads don't contain a function， but rather point to the same function in memory if you're wondering if threads accessing this memory area at the same time is dangerous。

 it's not because executable code and constants reside in the text and data sections。

 two regions that are never written to。

![](img/040690c5232d0f1c5705435c7838abc0_38.png)

All the information pertinent to a specific thread generated at runtime。

 resides either on the stack or the heap， so threads accessing the same executable code concurrently is perfectly safe。

Perhaps this last part helps you understand why in low level languages like C。

 spawning a thread requires us to pass a pointer to a function as a parameter。

This might seem confusing， but what we're actually doing is passing the memory address where the code that the thread will execute begins。

So please don't misinterpret my animations， threads are not asynchronous functions。

There are two ways we can define threads from the operating systems point of view。

 threads are what processes were in our previous episode， the most basic unit of execution。

From a developer's perspective， threads are a mechanism to tell the operating system that certain pieces of code inside our program can be executed concurrently。

Other interesting definition that I've heard of is threads can be seen as lightweight processes。

 easier and faster to create。And remember， everything I've said in this video applies even to systems that disposes of a single core processor。

And let's wrap things up for now。In the next episode。

 we'll discuss the additional purpose of threads in systems where the processor has multiple cores。

 the fundamentals of parallelism。If you learned something， please hit the like button， it is free。

 and that would help me a lot， see you in the next one。



![](img/040690c5232d0f1c5705435c7838abc0_40.png)