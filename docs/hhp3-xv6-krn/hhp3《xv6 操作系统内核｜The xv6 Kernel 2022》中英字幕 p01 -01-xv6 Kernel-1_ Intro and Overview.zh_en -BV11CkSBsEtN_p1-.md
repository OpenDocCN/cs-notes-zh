# hhp3《xv6 操作系统内核｜The xv6 Kernel 2022》中英字幕 p01 -01-xv6 Kernel-1_ Intro and Overview.zh_en -BV11CkSBsEtN_p1-

![](img/c26a98cb8df21276baa3ae6daeace192_0.png)

This is the first in a series of videos on the XV6 operating System kernel。

This is a very short but very sweet Uni like operating system that's used for educational purposes。

 It was developed at MIT and used at other places as well。😊。

This is an operating system that's used by students， primarily in an operating system course。

And there are two implementations of this kernel。One for the X86 architecture and one for the Rik5 architecture。

In this series of videos， I'm going to be talking about the risk five version。

The risk five version that is used is a 64 bit processor and whether're using the X86 version or the risk five version。

You're probably going to be using it in an emulated fashion using an emulator like Kimu。

 most likely you don't have a spare computer sitting around。

 probably a spare risk five processor is even less likely。

 so instead you'll be running the operating system if you choose to run it。

 under an emulator but in any case it's meant to run on a bear machine。And in fact。

 it's a multi core operating system， so Kimu is capable of emulating multi core systems。As I said。

 it's short and very sweet， it's only about 6，000 lines of code。

 most of it is written in the C programming language with maybe about 300 lines in assembly language。

In this video series， what I'm going to do is do a walkthrough of more or less all of the code to give you an idea of what's going on with it。

The code is very simple and well written and clean code。

 and I've read a lot of C code and written a lot of C code。

 and I'm still learning new coding techniques， and I think this is an example that is worth studying。

In addition， of course， as an operating system kernel。

 it illustrates some of the basic concepts that you'd be learning in an operating systems course。

 so that's another good reason to study this code in detail。For this video series。

 I'm not going to assume that you have any knowledge of the risk five instruction set architecture。

 but I will assume that you have had some assembly language coding。

I intend to walk through the assembly language。Instructions line by line。

 so I will hold your hand there， so don't worry have you had an operating system class。

 maybe maybe you're in an operating system class right now that is using the XV6 system In any case I've taught a few operating system classes and I'll probably go over some of the concepts as we encounter them。

This is going to be a long series。 So buckle your seat belts， it's not for the faint of heart。

I'm assuming that you've got some brains， and furthermore。

 I'm assuming that you're interested in this particular system and can focus for the amount of time that it's going to be。

For this video series。 So let's look at some of the features。That the kernelel has。

It's got processes， these processes run in their own virtual address spaces。

 so there are page tables for a page table for each address space to support the virtual address spaces。

The operating system supports files， units like files， and the directory hierarchy。

 you can pipe data from one program to another program。Of course， there's a timer interrupt。

 so there is multitasking， the various processes are running in parallel with time slicing。

There are 21 system calls that are implemented in XV6， this is not a lot。

 the production UniX systems have more like 300 system calls， maybe 500 system calls。

 but this is enough to give you the core ideas of UniX。

There are a number of user programs that are supplied with this kernel。

 and these can illustrate the capabilities of this operating system。

The operating system can run a simple shell program。In fact。

 I made a video that talks about the Shell program in detail， you can look for that if you want。

 other common unX programs， CA， Echo， GrP， kill， which is used to terminate a process， LN。

 which is used to create a hard link from one file to another。And LS。

 which is used to list out the contents of a directory。You can create directories。

 you can remove files， and WC is for counting the words in a file， as well as the characters。

So all in all， I think that this can really be considered a true Uni system。

 although it's pretty short and simple。 There's a lot that's missing。 Okay， definitely。

All the complexity of a real operating system is not there。

 a real operating system like Linux may have as much as 100 times as much code。

 you know we're talking a million lines of the kernel and when you add the device drivers in。

 you can go up to many millions of lines of code。This is just too much for any human to study really。

 and if you want to find out how kernels work， this is really the operating system for you。

But there are some things that are missing from your typical Uni or Linux system。There。

Are no user IDs and no login sequence， no verification。

There are no protection bits associated with files， you know the read， write， execute protections。

 that's not here。The mount command is just not available， so you just have one file system。

In a real system， the virtual addressero spaces can be paged out to disk so that you can run more processes than will fit in physical main memory。

That's not present in XV6。There's no support for networks， no sockets or anything like that。In fact。

 there's no way for processes to communicate or synchronize amongst themselves。

There are two device drivers， but a real operating system。

 a real world operating system is going to have many more device drivers to support all kinds of different bits of hardware that you might find。

And lastly， there is only a limited amount of user code I listed the approximately 10。

Programs that are distributed with it， but a real。Usable Linux or Uni system is gonna have lots and lots of apps。

So let's go over some of the。

![](img/c26a98cb8df21276baa3ae6daeace192_2.png)

System calls that are present， I'll go over these in more detail later when we encounter them。

 but I just wanted to kind of list them out here so you could see what we've got。So fork。

These are familiar from any Unix or Linux system。 The parameters are slightly different in some cases。

 but the idea is there。In。Concept anyway。Fork is used to create a new process。

 weight is used to wait for a child process to terminate， exit is for terminating a process。

Pipe is for creating pipes， and then we've got open clothes。Read and write for dealing with files。

 we've got kill a terminate a process。We've got exec， which is past a file name and will'll。

Read in that file， presumably it's an executable file and we'll load it into memory。

 creating a new virtual ladderer space and execute it。We can make iNots， we can create links。

 hard links， and we can remove hard links and unlink files。

 thereby possibly removing them if it's the last link。We can get information about files。

 we can change directory， so we do have a notion of the current working directory。

Dpe is used for copying file descriptors。Then we can get a program ID sorry。

 the process ID for the current process。We can grow the heap， so that's this function here。

 this system call here， and we can put a process to sleep for a while and we can also see how long the kernel has been running So in the next video in this series I'll be going through the code in quite a bit more detail。

 but I just wanted to start with giving you an idea of what this operating system kernel has。

 and what its capabilities are so you can determine whether you want to make the commitment for watching these videos As I said。

 the series is not for the faint of heart， it's not for the amateurs。

 it's for people who really want to look at an operating system kernel in detail and understand a rather large but not too large body of code。

Okay， let's get started with the next video。

![](img/c26a98cb8df21276baa3ae6daeace192_4.png)