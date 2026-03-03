# 哈维穆德学院《数字设计和计算机架构RISC版｜Digital Design and Computer Architecture： RISC-V Edition》 - P115：Chapter 7 19.Multithreading & Multiprocessors.zh_en - GPT中英字幕课程资源 - BV1JC1MY1E7F

![](img/ac5f2635bc8ea2d232137f68fa124463_0.png)

Hello， in this video， we'll talk about multi threading and multipros。So。A thread is a program。

 it's a part of a program that you might want to execute simultaneously。So on a typical computer。

 you have many threads going， let's say you're running a word processor。

There may be a thread to look for key presses while you're typing and pose those to show up in the screen。

Simultaneously， there might be a background thread that is checking for spelling or grammar。

And simultaneously， there might be a thread that's printing a document while not preventing you from continuing to type。

So that's in a single application， you then have several applications running at once while you're typing on the word processor。

 you might have a video playing in the background and you might be downloading movie or some music。

So all of those threads， the user would like them to appear to execute simultaneously。

 and if we have enough hardware， we could actually make them execute simultaneously。

With multi processors here， we could put many processors known as cores onto a single chip or many chips in a box。

So we mentioned that thread process is a program running on computer and an application may be compressed。

嗯。Okay， and then application。A process may be composed of multiple threats。

So in a conventional single core processor， only one thread runs at a time。And when a thread stalls。

嗯。Let say a thread goes to access main memory， and it's going to take 100 cycles because we missed the cache。

Then the thread could stall and the architectural state of that thread could be stored away。

And new architectural state of another thread could be loaded into the registered file and program counter so that the new thread could start running。

This is called context switching。And if you contact switch often enough， it appears to the user。

 like all threads are running simultaneously， even though they're actually just switching back and forth very quickly。

With multi threading， we can have multiple copies of the architectural state。

 so we could say have multiple copies of the register file and multiple copies of the program counter。

And we could have multiple threads that are live or active at one time。When one thread stalls。

 another one can begin executing immediately。And in fact。

 if one thread can't keep all the execution units busy。

 we might issue instructions from another thread at the same time。

 just to keep the execution hardware fully occupied。

So multiing threading doesn't increase the instruction level parallelism of a single thread。

 but it does increase the throughput of the system。And intel， caused this hyperth。

So multiple processors are another technique。Where we have many processors at core with a method of communication between them。

And some examples of multiprocessors are homogeneous， heterogeneous， or clusters。

So in a homogeneous multiprocessor， you have many identical cores that typically share a common main memory。

And can talk to each other by reading and writing that memory。In a heterogeneous multiprocessor。

 so homogeneous is common in your computer。You may have a Quadcore laptop that has four identical core。

Hedtergeneous computing。We have multiple different kinds， of course。So for example。

 in your cell phone， you may have a Quadcore CPU for running applications。

 and you may also have a digital signal processor that's used for processing stuff coming in on the radios and you might have a graphics processor doing video acceleration and then you might have a little processor that's turning on and off power to all these other ones。

 That would be an example of heterogeneous multiprocess。Another type is clusters where。

Each core or group of core， has its own memory system。

And you communicate between clusters over the network， say over Ethernet。

So communication between clusters is slower than communication within a cluster。

So that's given us a survey of modern techniques in advanced computer architecture。

And I hope that you found this very interesting and have a deep appreciation of what's under the hood in your processor。

 and some of you may go on and build your own。

![](img/ac5f2635bc8ea2d232137f68fa124463_2.png)