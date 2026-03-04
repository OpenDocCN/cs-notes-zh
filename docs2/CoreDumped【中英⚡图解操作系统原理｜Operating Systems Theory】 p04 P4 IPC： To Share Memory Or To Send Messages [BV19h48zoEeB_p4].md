# CoreDumped【中英⚡图解操作系统原理｜Operating Systems Theory】 p04 P4 IPC： To Share Memory Or To Send Messages [BV19h48zoEeB_p4]

This video was sponsored by Jet Brains。What I'm showing here looks like an image。

 but it's actually a program， I'm using two processes to render a fractal。

The part implemented in rust performs the mathematical calculations to determine the color of each pixel in the fractal。

 it adds this data to an array， and once all pixel calculations are complete， it triggers an event。

 sending the array as a message in TypeScr， I listen for that event， receive the data。

 and then pass it to a function that draws the pixels on an HTML canvas。



![](img/980afc941bd994dd1dd19367c37acc02_1.png)

Applications like this one built in a modular way are possible thanks to interprocessed communications。



![](img/980afc941bd994dd1dd19367c37acc02_3.png)

Today we will talk about how processes， which are isolated by default。

 can interact with other processes by exchanging information。Hi friends， my name is George。

 and this is Core Ded。In a previous episode， we learned that when a program is loaded into memory to begin execution。

 it receives a new name， a process。But a process is more than just executable code loaded into memory。

 it also includes a CPU state， the memory region allocated to the process， a list of open files。

 and other resources such as IO devices。Thus， a process is not just a program。

 it's the entire context in which the program operates。This isolation， however。

 introduces a significant drawback， as there are many scenarios in which a process needs to cooperate with others；

 if processes were entirely isolated， there would be no way for them to collaborate。

So processes can be classified based on whether they cooperate with other processes。

 a process can be either independent or cooperating。

Two processes that share data between them are clearly cooperating processes。

 but there are additional reasons for enabling process cooperation。For example。

 computationalutal speedup in systems that support parallelism。

 complex tasks can be divided into smaller ones that can be executed simultaneously。

 reducing the total time required to complete the larger task。

Or modularity constructing a system in a modular way allows for the division of system functions into separate processes。

But notice that in both cases， processes need a way to coordinate their activities to function correctly。

Cooperating processes require a mechanism for interprocess communication that enables them to exchange data。

 sending and receiving information between each other。

There are two fundamental models of interprocessed communication。Shared memory and message passing。

We will discuss how both inter processcess communication mechanisms work along with examples from modern operating systems。

Let's start with shared memory， as the name suggests。

 this mechanism allows processes to share a memory space directly。Remember。

 when multiple processes are running on a system， the operating system allocates a separate block of memory for each one；

 this is known as the process's address space。

![](img/980afc941bd994dd1dd19367c37acc02_5.png)

Through a mechanism called privilegevi instructions， the operating system enforces isolation。

 preventing processes from accessing each other's memory。

If a process attempts to read or write to another process's address space。

 the operating system will immediately interrupt and terminate that process。

 enforcing the isolation policy to ensure data safety。

So to allow two or more processes to share a memory area。

 the operating system requires them to agree to remove this restriction。

Typically a shared memory region is created using system calls and resides in the address space of the process that created it。

Any process wishing to communicate through this region must attach it to its own address space also through system calls。

Once the shared memory region is established， both processes can communicate by writing to and reading from this shared area。

Here's an important detail； once the operating system grants the shared memory region。

 it no longer manages what the processes do with it。



![](img/980afc941bd994dd1dd19367c37acc02_7.png)

What I mean is that the way the data is structured and the specific locations within the shared region where that data is written are entirely determined by the processes。

 not the operating system。For example， consider a producer consumer model where one process。

 the producer generates data， and the other， the consumer reads it。

Suppose the shared region contains an array where the producer writes8 bit signed numbers。

If the consumer reads these as unsigned 8 bit numbers， it will interpret the exact same bits。

 but with a different meaning。Similarly， if the consumer expects a different data type。

 like an unsigned 32 bit integer or reads from the wrong address， misinterpretations will occur。

As you can see， there's a lot that can go wrong here。

 the consumer must know precisely how the data is structured and where it's being written。

 failing to follow these conventions could lead to failures in one or both processes， or worse。

 undefined behavior。The processes are also responsible for ensuring they don't write to the same location at the same time；

 otherwise they could encounter race conditions， an issue we will cover in a future episode on thread synchronization。

Okay， but are there popular programs that use shared memory？



![](img/980afc941bd994dd1dd19367c37acc02_9.png)

I'll share the answer after a quick message from Jetbrains。



![](img/980afc941bd994dd1dd19367c37acc02_11.png)

If you're a developer just learning， self educating， or working on personal projects。

 setting up your entire development environment might not be the most productive way to use your time you might need a full IDE loaded with all the tools you need right out of the box。



![](img/980afc941bd994dd1dd19367c37acc02_13.png)

![](img/980afc941bd994dd1dd19367c37acc02_14.png)

![](img/980afc941bd994dd1dd19367c37acc02_15.png)

That's where Jetbrain's products come in。With Rder and Webstormorm， you get just that。

 and I'm glad to tell you that you can now access the full versions of these IDEs for free for non commercial use。

Whether you're developing games， building web apps， or exploring the dotnet ecosystem。

 Rder offers all the tools you need， including full support for unity， Unreal， ASP。net， and more。



![](img/980afc941bd994dd1dd19367c37acc02_17.png)

![](img/980afc941bd994dd1dd19367c37acc02_18.png)

Webstormorm is the ideal IDE for modern JavaScript and TypeScrrit development。

 supporting frameworks like React， nodede JS， Angular， and so much more。



![](img/980afc941bd994dd1dd19367c37acc02_20.png)

This is perfect for those of you who want to grow， create， and stay productive。



![](img/980afc941bd994dd1dd19367c37acc02_22.png)

Both IDEs come loaded with features like code analysis， Safe refactoring， Project wide navigation。

 and version control， giving you everything you need to work efficiently and write great code。



![](img/980afc941bd994dd1dd19367c37acc02_24.png)

![](img/980afc941bd994dd1dd19367c37acc02_25.png)

Getting started is simple， just download writerer or webstorm， pick a free non commercial license。

 and you're all set。

![](img/980afc941bd994dd1dd19367c37acc02_27.png)

Head to the link in the description to start your development journey with jett Brains。

And now back to the video。You might have noticed that when using Chrome。

 multiple processes are created， even if you're only using a single tab。

Any chromroium based browser is a perfect example of a modular system。

 which relies on interprocess communication。As we know， dynamic web pages often contain JavaScript。

 which can sometimes come with bugs that could potentially crash the browser。To address this problem。

 Chromeium uses a shared memory approach， dividing tasks among three types of processes， browser。

 renderer， and plugin processes， the browser process manages the user interface and IO operations and is created only once when Chrome starts。



![](img/980afc941bd994dd1dd19367c37acc02_29.png)

Reendnderer processes handle web page content such as HTML， JavaScript。

 and images with a new renderer process for each open tab。

And plugin processes manage specific plugins like Flash， QuickTime or PDF readers。



![](img/980afc941bd994dd1dd19367c37acc02_31.png)

This isolation ensures that if one tab crashes， only its renderer process fails。

 leaving other tabs unaffected。Other examples of systems that use Sha memory are simulation software。

 game engines， databases management systems， and deep learning frameworks。

Now let's talk about the second approach， message passing。

Sharing memory isn't always the best way for processes to communicate。

 as it can be error prone and might place more responsibility on the programmers than they're comfortable with。

An alternative method is for the operating system to provide a mechanism that allows processes to communicate and synchronize their actions without sharing the same address space。

Address spaces can remain isolated and instead of writing to memory。

 processes can communicate by sending messages。Popular message passing mechanisms include pipes。

 sockets， and remote procedure calls， although the specific implementations of these mechanisms are beyond the scope of this video。

 the general concept is as follows。A message passing facility provides a set of basic operations。

For instance， suppose we have two processes， A and B。If Pro A wants to send messages to Pro B。

 it must invoke a system call to request that the operating system establish a link with Pro B This link serves as the logical pathway through which messages are sent。

And notice that I just said logical path。What is actually happening is that the operating systemss kernel creates a queue in its own address space。

 and this queue will serve as a mailbox where process A can send messages and process B can receive them。

The behavior of this cu can vary based on communication requirements； for instance。

 we may need asynchronous instead of synchronous communication or a buffered queue if we want to limit the number of messages the mailbox can hold。

For full duplex communication， a mailbox can be implemented with two cues。

 allowing both processes to send messages to each other simultaneously without conflict。

But some of you might have already noticed that there's something odd here。

Since the mailbox resides in the operating system address space。

 processes shouldn't be able to access it。And yes， that is true。

 processes cannot directly read or write to mailboxes， thus。

 the operating system must provide system calls for at least two operations， send and receive。

When process A needs to send a message to Pro B， it uses a system call to instruct the operating system。

I need to place this message in the mailbox shared with Pro B， but I cannot access it directly。

 so please handle this for me。Because the mailbox exists in the kernelel's address space。

 the operating system can copy the message to the mailbox。Similarly。

 when Pro B wants to check for messages， it uses its corresponding system call to ask the operating system。

I cannot read the mailbox shared with Pro A directly。

 could you please check if there are any messages for me。

 if there's a message the operating system can return it as the return value of the function。

If you don't fully understand why system calls are necessary for this process。

 I highly recommend reviewing the previous videos in this series。

And this is the general idea behind message passing communications。

One of the first operating systems to introduce the idea of shared mailboxes was Match。

 an OS whose derivatives form the foundation of some modern systems， including iOS and Mac OS。



![](img/980afc941bd994dd1dd19367c37acc02_33.png)

![](img/980afc941bd994dd1dd19367c37acc02_34.png)

Match treated processes as tasks and had a very specific name for mailboxes， ports。

It's important to remember that messages are sent to ports， not directly to processes。



![](img/980afc941bd994dd1dd19367c37acc02_36.png)

This distinction matters because two processes can have more than one communication link。

 and not all ports are associated with exactly two processes；

 a process may keep an open port to receive messages from any other process。

This type of port is known as a listening port， and its purpose is to handle special messages called connection Res to establish new private communication links between processes。

Some of these concepts may have started to sound familiar。You see。

 message passing has a huge advantage， since it doesn't require two processes to share their address space。

 processes don't even need to be on the same machine to communicate。



![](img/980afc941bd994dd1dd19367c37acc02_38.png)

Of course this requires a more complex underlying implementation。

 such as networking capabilities to establish a connection between computers。

 this involves driver levell programming for components like network interface cards。



![](img/980afc941bd994dd1dd19367c37acc02_40.png)

But if implemented correctly at the operating system level。

 the process should be seamless for developers messages passing between processes on different machines will function the same way as it does between processes on the same machine。



![](img/980afc941bd994dd1dd19367c37acc02_42.png)

![](img/980afc941bd994dd1dd19367c37acc02_43.png)

![](img/980afc941bd994dd1dd19367c37acc02_44.png)

The client server architecture is typically implemented using the socket interface。

 which is an example of a message passing mechanism supported by nearly all mainstream operating systems today。

 it is usually illustrated this way， although I'm not sure I completely agree。

 as it suggests that the clients and server are machines。

 in reality they are simply processes running on those machines。

 and communication doesn't always require a network。



![](img/980afc941bd994dd1dd19367c37acc02_46.png)

The client and server processes can run on the same machine as we see when using local host to test projects。

Anyway， when a client sends a request to a server， the IP address identifies the machine hosting the server process。

 while the port represents the mailbox through which the server process receives requests。

Servers providing specific services like HTTP， FTP or SSH rely on the Socket interface。

 which makes me remind the guys from Codecrafters have a nice challenge- based course where you can learn how to use sockets to implement an HTTP server from scratch in the programming language of your choice I'll leave a link in the description in case you want to support me when subscribing。



![](img/980afc941bd994dd1dd19367c37acc02_48.png)

![](img/980afc941bd994dd1dd19367c37acc02_49.png)

![](img/980afc941bd994dd1dd19367c37acc02_50.png)

Unfortunately， message passing systems do have drawbacks。

 because ports reside in the kernelel's address space。

 processes must use system calls each time they want to send or receive messages；

 this can be quite costly in terms of performance。This limitation does not apply to the shared memory approach with shared memory。

 system calls are only necessary when creating the shared region and attaching processes to it once these steps are complete。

 processes can read from and write to the shared region as if it were part of their own address space without needing further system calls。

This results in communication that is extremely fast， essentially as fast as direct memory access。

And just to clarify， I'm not saying that message passing is slow， shared memory is simply faster。

In 99% of cases， message passing is more than sufficient。And if you learned something today。

 don't forget to like and subscribe， see you in the next one。



![](img/980afc941bd994dd1dd19367c37acc02_52.png)