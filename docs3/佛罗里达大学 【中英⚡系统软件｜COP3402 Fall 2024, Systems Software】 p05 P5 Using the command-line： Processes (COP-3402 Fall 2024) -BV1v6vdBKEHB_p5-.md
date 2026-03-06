# 佛罗里达大学 【中英⚡系统软件｜COP3402 Fall 2024, Systems Software】 p05 P5 Using the command-line： Processes (COP-3402 Fall 2024) -BV1v6vdBKEHB_p5-

Okay， so welcome back to System softwareftware。Last time we went over some of the fundamentals of navigating the file system on the command line。

 we went over the file system itself， hopefully everybody more or less understands the nature of a hierarchical file system。

 we read the UniX， original UniX paper that described their version of the hierarchical file system。

 we did some exercises， learning about paths， how to refer to files on the file system。

 so relative versus absolute paths， what are absolute paths。

They're always from the root and the root， how do you denote the root in the Uni world forward slash。

 so if the path starts with forward slash， you know it's an absolute path。Relative paths。

 what are they relative to？The working directory， so this is another UniX design decision every running program has a working directory that the kernel the operate existence actually maintains。

And this helps with that interactivity and the command prompt as we saw and navigate the command prompt。

 you can type what to learn what your current working directory is。PWD print Work directory。

So every running process has a current working directory associated with it。

 and that's what relative paths are relative to。So this time I'm going give a little background on the theory of processes。

 we talked about the file abstraction before， which you also read about in the UniX paper and we're going to talk about the process abstraction。

 another one of these fundamental operating system abstractions that the kernelel provides to you and we'll go over we won't go into how it's implemented。

 but we'll go over enough for you to kind of get the idea and then you'll read about it in the Uni finishing up the rest of the UniX paper they'll talk about their design of process abstraction。

And then I'll do some more command line illustration to show you how to work with processes on the command line using the kind of UniX philosophy。

うん。Okay， but first， let's go over the homework from。Last time。

So the homework from last time was to make sure you can get into Eustace so is everyone able to who can get into EustA？

Who cannot get any this is anyone' still waiting okay， good， so everyone can to use this。

 you get all ask to H。Did anyone have issues with downloading files， untring files。

 any questions on that？So you'll have to you'll be able to。

 or I don't think you' need to download files， but you'll have to clone or use other web resources so I want to make sure that you can access it yeah。

みだ。Oh， so sorry， TA is the UniX style archive tool。An archiving utility， so it's called tar。

It might come from TE Archive， I'm actually not sure， oh yeah， stands for tapepe Archivver。

So it's just the utility for making these archives。

 which are just like zip files like sets of files compressed into one format， one file。

 it's called a tar， also called a tar ball。For some reason to actually say that in here。

And so to like with unzip to unpackage or unarchive these， the lingo is untar。

Or at least that's what I'm using。Yeah， they don't actually use that term， but yeah。

 when I say ontR just mean unzip or unpackage， the tar ball and a tar ball is a file archive like a zip file。

In the UniX world， this is the kind of UniX world version of zip actually predate zip。

 and it's not compressed by default。Okay， so。Who felt like they got the whole homework。

 they actually got it done。Pretty good who is still anybody have questions or is struggling on some of the。

Or want admit it that they。Having having issues with it。All right。

 so let's go over it quickly anyway for those who。

![](img/4102035c7abe5cd6125719f03dfbf1dd_1.png)

Might have questions。

![](img/4102035c7abe5cd6125719f03dfbf1dd_3.png)

いや。Oh， so I put a quick documentation of this in the slides， X means extract as opposed to。

Create V means verbose， so it'll show more information and F is the for file F。

After F you put the name of the file that you want to operate on so that's if you're interested in and I can't remember if I talk about this later。

 but as I mentioned it before， there's a utility called Man， which stands for Man。

If you put N and then the name of one of these commands， it'll give you documentation。Of these。

 I mean it's pretty lengthy， it's more for reference。

 but you can see here that it'll define each of these arguments or options that you can pass to。

The tool， yeah。Oh， so this is。I think I had this in the slides and I went over this very quickly。

The man page is， I think the same tool as less， so we talked about less。嗯。Less is a。

Utility that allows you to kind of interactively browse a。The text of a file。

And it has commands that are similar to Vm which if you pick ViIm or you go over the tutorial for it。

 you'll learn the commands for it， you can use the arrow keys and page up and page down the way to search through it is with forward slash all these commands are very very acidoteer。

 you kind of just need muscle memory to relearn these over and over。

 but if you do forward slash and then type start and type a string to match and hit enter。

Less or the man page。Will highlight。Those matches and you can use n to sheet all the matches shift n to go backwards and search So these are all super like。

They're very lengthy sets of command line instructions for these and you can learn these over time。

Pick a couple of simple tests like let me just search and then just let me like try that a few times and then when you forget it like I do the next 10 times just Google it again I just all right how do I use search and then eventually you gradually remember the small number of commands you need to do what you want to do but that's how I learned it I basically just Google it when I forget how to do something and then I do that 10 or 20 times and eventually I remember it for a couple months that I forget again。

Okay， so let's go over this homework real quick， let's do a couple examples of these。

So here's the original tree， also I improved the instructions a little bit based on some feedback。

 I added some， I made this so you wouldn't get， so if you got lost in your directory tree。

 all these commands would still work but there are minor changes。

But this is what if type the if you look at the homework tree。When you unzip it， oh。

 I haven't actually untar it yet。We look at the tree。

This is what it looks like originally and this is the new tree that I did some file operations in order to get this modified version of the tree I don't know if anyone tried this but you could just like recreate this whole tree from scratch that's actually one solution did anybody try that that anybody just do okay so one clever person decided to so that's not the minimal number of instructions right but that is one way to do it this great whole tree that's like the the。

delete delete you remove everything。Yeah， I mean， yeah， I didn't show the remove。

 it's a little dangerous to remove entire trees， so I didn't show you to do it。

 but the RM command can be used to recursively delete a subdirectory so if you try to delete。

A director that's not empty， the remove plan will not let you。

Same with remove DIR once let you remove a non empty2 director。

 but you can force it to do it and you can look that up on your own command。Allm。But， you could。

If you've ever seen online the people who troll unfamiliar users will say you know type this sequence of commands and it deletes your entire like file tree。

 that mean thing to do， that's the command and that' command I'm talking about。

 you can easily recursively delete all of your files so be careful with RM。

I think there's an interactive mode to make sure that you don't， is that maybe that's a move？

There's an interactive mode to like make sure you don't delete stuff without prompting。

 so you could use it safely like that dash I。呃。Anyway。

 so yeah that's the out of the outside the box way of doing it it's funny that somebody actually thought to do that that's good。

 but the sort of minimal way is to make small changes to this tree so that it matches the new tree so let's take a couple examples if we went over EXT2 in class。

U。Let's look at。Net ethernet。 So what's the difference between。Net。

 ethernet in the previous tree and in the new tree。Yeah。ItDoesn't have any subdirectors。

 there's no files of it， yeah。Okay， so one。Solution is to move ethernet to sound。呃。

So I gave no constraints on what files were the same or not the same or whether they were even directors or files。

 so you could certainly avoid recreating sound by moving another file。

 what are other ways to make net match net here。Delete ethernet， Yeah。

 you can delete ethernet that doesn't have to be combined with， but you could。

 you know to make a smaller number of operations， but yeah， that's that's。

That's what we can do to make the net subte match the new net subte。So what， what command。

 So here I'm in the。I'm in the homework three directory。

 what commands would I enter in order to make that happen to let's try deleting the Ethernet yeah。

So we could use RMDR， let's avoid using RMDR， let's do it without without， let's just do RM， yeah。

两个人。Oh， so yeah。So RMD R recursively deletes， so if you have an entire subte。Of。Fileles like。

 well all right， let me just show， let me just show working， so RMDR will take this entire tree。

This entire homework three tree。And normally when you just type RM。

 it'll say it's not I'm not going to remove a directory RM is meant by itself is removing files if I say remove recursively。

What the manual says。Is that it removes directories and their contents recursively。

 so it'll just blow away or at least remove from the directory entries。Every directory。

Starting from the path that you give it。So if I do like RM Dsha root。

 what's it purportedly going to do？Delete everything now you don't have permissions to delete route and I would very much annoy assistance if I somehow had permission to do that and did that would。

That would be very bad， but so I can't delete this tree now。But let me yeah。

 let's just delete all three， so RMDR recursive delete， the homework3 folder。

 and since I can't delete I can't remove the directory without removing all its entries it will recursively enter and actually I didn't have time to get this。

 but I wanted to ask。You guys for an algorithm from deleting an entire tree。

 and it's really just a tree traversal， you just traverse。It's like a post orderor tree traerssal。

 you just traverse the tree to the leaves， delete the leaf。

Then delete the parent because the parent is now a leaf once you delete all of the leaves。

 the parent of the leaves are now leaves and just recursively traverse that tree deleting all of the files and directories in a bottom up fashion。

 I mean that's haven't looked at the algorithm， but I'm pretty sure that's what it does。Yeah。

 it would take O ofN for the number of files， that's right， that traversal。

I think it's just removals really quickly， or I mean， I don't know what the。

I don't know what the upperex does under the hood， I don't know if it actually goes in and it bothers to delete all these files。

 I think it does， because the otherwise these files will still exist。Yeah， I don't know。

 I'm pretty sure it does recursively do it， I think it's just very fast to do removals because it's not deleting the data。

 it's just deleting all of the。Enries， the directory entries。

 it doesn't actually delete the files data if you remember when we talked about how files are implemented very briefly。

These are just the file name is just an entry that points to a directory entry that points to the data。

And so when you delete a file， you're just deleting that entry， not the data。

 you're effectively deleting the pointer to the data and not the entry itself。Basically， yeah。

 no problem so I suspect that's white so fast， I haven't looked at the remove command source。

 we could， it's open source。But I suspect it is doing this recursive traversal。

 So now if I try to look at the。Homework 33， it's gone， the entire everything is gone。

 so this is why using RM。DR is a little dangerous， especially when combining it with wildcard like star。

 I don't even want to type it because I might just blow away all my stuff， but yeah。

 that's what RN D R does。Questions other questions on on that。

So that's one way we could have done it。 I me restore this tree here。

 What's another way without using slightly dangerous commands to get rid ofthernet ethernet， yeah。

Okay， remove directory and remove directory off， if we type Re directory ethernet。Well。

 there is no directory Ethernet， that's because we're in the homework three folder。

 the homework three folder contains net。But the Ethernet file is under the net subdirectory。

 so as your colleague just pointed out， we would have to remove net slash。Ethernet。

 and what kind of path is this？Relative path and relative to what？Relative to net。Whats second？

Homework three， it's homework three， our working directory， print Work directory is homework three。

 so this path， so ethernet is relative to net， but this path net slash ethernet is relative to the current working directory。

 which is homework three。Other questions on this operation yeah？Absolutely。

 so let me do this way first and show you the new tree， so now net no longer has ethernet。

I'll restore this tree。So I just I untard the file again so Ether and is back。

 so you could certainly instead of using a relative path to go to a different director show delete a file in a different directory。

 you could just change the working directory to that。Subdirectory net。And now I' in。

Homework 3 slashnet， the only child here is Ethernet， and I could just remove。

Ethernet from this new working directory。Could certainly do that。So change directory is things。

 in my opinion makes things a little more confusing because you have to keep track of where you are。

 I like using paths because。I can stay in one spot and not disorient myself on the file system。

Our questions， other questions on this？All right， so maybe deceptively simple exercise。

 you know you have to kind of do a little puzzle solving， figure out the right operation。

 keep track of your working directory， just remember always type PWDLS so you don't get lost in your file system you kind of have to have a mental model of where you are on the tree when you're working in the command line and PWD and LS will keep you up to date so you don't have to make any assumptions about where you are。

All right， so that's navigating the file system， hopefully those you haven't seen the command line are a little bit more comfortable。

I hope with you through the command line， and when we go into the projects， I'll give you。

 at least in the beginning projects， very specific instructions for moving around the file system。

And then hopefully over a couple of months you'll be much more comfortable with the command line。

 you can kind of make your own workflows and work however you prefer。

 there's no real one way to navigate the file system there's many ways to achieve the same goal and so once you get comfortable。

 I hope you'll get comfortable a couple months so when you do the later projects。

 you'll no issue using the command line。All right， other questions on navigating file system？

All right， so that was the。File abstraction， so we learned very quick briefly the kind of theory behind the file abstraction。

 what is a file？In this Uniix world， the file abstraction， what is a file？Data。

 so that's what backs it。But abstractions are really defined by what you can do with them。

 how you can operate on them， so how is a lock defined， a lock is defined because you can lock it。

 unlock it， doesn't matter how it's implemented， it might be metal， it might be steel。

 it might be wood， kind of a woodlock。But it's really the operation。

 so what operations unify files yeah？How do you store information with the file？

You write bites to it。You read and write to。If you read and write bytes to something。

 you could model that with a file in the UniX world。

So I'm sure I think you've all done C programming where you have to open a file， like FO。

 read and write。So that read and write， those read and write operations。These are。

systemstem calls that the kernel provides you to read and write files。

 but the file itself does not have to be backed by it doesn't even have to be backed by some physical data。

 it could be something in memory， it could be a socket。

 it could be a thermometer that you hook up to your machine and in the UniX world you could treat that as a file and read well not write to a thermometer but you could read from the thermometer。

 read bytes from it。And using this exact same interface that you use for writing and writing files on disk。

 you can read and write。Really， any kind of hardware you like as long as you can。

Implement what reading and writing means for that， so a thermometer might be continuously sending temperature data。

And you could open it as a file called the read operation and every time you get the read operation it gives you like two bytes of a temperature or something like that。

So that's the file abstraction， that's why it's an abstraction because it's an interface that's independent of how it's actually implemented behind the scenes。

 and if you've taken object orient programming or will take it。

 you'll see that this notion of abstraction kind of pervades programming。

 with object oriented programming it's one way to define new abstractions for yourself in a programming language。

 but in the kernel world the abstractions are defined by the kernel by the operating system and then it exposes a library of commands at API for operating on its abstractions。

Okay， so that's the file abstraction that we learned about and most of the time you're going to be dealing with files on disk and file hierarchies。

 but good to understand that abstraction is the operations you can do on some object and the file abstraction is just you can read and write。

I dear。So today we're going to learn about another。Fundamental operating system。

 abstraction called a process。So has anyone learned about processes before？A little。

 what did you learn about it？No， no， no okay， so you learned some implementation details of processes like how you can。

Make memory accesses faster for processes and probably virtualization that they talk about virtualized memory。

 perhaps。So you might learn about that in operating systems and you'll learn more about that。

 I'm going to give you kind of just the broad strokes of processes。

But a process is sort of deceptively， just like files。

 a very deceptively simple definition of what a process is in the operating system world。

A process is just a running program。I mean， who cares， I mean， you have a program， it can run。

 why do you need some fancy abstraction for this？So first of all， what is a program？😡。

You guys have all written programs， what is it，W how can you define what a program is？Yeah。

Sure code like machine code。So you might have。For instance。Actually， I think I have。

Diagram I can show for this。So this is a really good。

 free and open operating system textbook that you might use if you take an operating system class。

And it defines it the same way a process。It's just a running program。So it's easy to say that。

 but it's a little more subtle when you look at the hardware point of view。

So typically when we have a program， we persist at the disk， you know， when you run。

 you save the hellello world and you compile it， now you've got a Hello world program。

That machine code， you store it as a sequence of bytes on disk。And at that point it's not running。

 the machine is not running， it's just stored on disk。

And to have something running on the machine means that the processor is executing its instructions。

So it's a subtle distinction， but there's the program itself。

 which is just a sequence of instructions， and then there's a running program。

 there's a machine that's actually executing sequences of instructions。

And in order for that to happen， which I probably learned a little bit in computer organization。

 in order for the machine to start executing a stored program machine。

The code somehow has to get into memory。And then the CPU has to go to the first instruction of that program and start executing it。

And because of the whole fetch， execute loop that modern processors have。

The CPU will automatically fetch its next instruction and go through each line。

 not necessarily in order sequentially， but go through each sequence of instructions in that program as you've coded it to do。

That makes sense， questions on that。It's almost too basic to even say。

 but when we think of a process， a process is not the program on disk or some sequence of instructions。

 but it's the program that is currently executing。On the machine。And so at any one time。

 there are lots and lots of programs on your machine because they're stored on disk。

But not all of them will be running at the same time， and depending on your machine。

 you may only have one program running at any one time for most people's machines。

 that's more or less the case you probably have one processor。Okay， so that's a process。嗯。

What does it matter， why do we need to make such a big deal about a process and why do we even need？

An operating system。To manage this for us， why can't we just write a program？

Write some code that loads it into memory and just run the program。So on your machine， for instance。

 why do you need to care about a special product， why don't you just run a program in your machine。

 right？Right， exactly， you have multiple programs that you probably want to run。

 at least for our modern day computing devices， we have lots and lots of programs that we want to run at the same time。

 but most of us have like one processor， maybe it has eight cores。

 but you're probably running more than eight。Programs at one time， yeah。Right， so I mean。

 the point is what if the process crashes？Well， if you're just running run program on your machine。

 your whole machine just stops。😡，So that is actually another function of having this process abstraction of having the operating system manage it。

 is that if there are failures in the program， then the operating system there is to recover for you。

 to terminate the program， give you the dreaded sank fault， but your machine still runs。

 hopefully even if you're one of your programs enter some failing state。So yeah， one of the。

Main problems with computing devices that operating systems help overcome。

Is that you have many programs that you might want to run at the same time。

 and there are lots and lots of ways to solve this problem。We're going to look at one way today。

 but how can we solve this， let's say you have one machine。

 one processor and you want to run 10 programs， how can you run those 10 programs？

You can have them take turns。 Okay， you can have take。 So who's gonna。

 who's going do the turn taking。 Are you going sit there and stop the machine and load a new one。

Okay， so you could have some program that helps them take turns， what else could you do？

You going have more CPUs， but let's say I give you。

N plus one programs or ends a number of processors。

 what are you going to do when you have not enough CPUs for programs？Yeah， yeah。Okay。

 so you could ask the user to order them somehow， and then what were you going to say？Scheduling。

 but how do you schedule them？So who does this， who does this work of scheduling？

So who does他 mean yeah， go ahead ahead。Well the operating system that you run a program to do it sure。

 yeah， so one simple way that I didn't hear what's kind of funny is you could just like run them one at a time。

I didn't say it once， it just said you have like 10 programs to run in one CPU。Sorry。

 maybe that was a gotcha question， but you could just run them one at a time。

 it's called batch processing， it's what lots of machines did yeah。We switch really rapidly yeah。

 so that I think we have a couple of people already sort of foreshadowing what modern operations is of yeah。

这个就说。Multithratic and these are all the same， actually relatively the same solution。

The way I'm going to talk about and what Munichs and other modern what are called time sharing systems do is they。

They make the CPU or make the programs take turns。And so that you have the feeling of programs running at the same time。

 they take turns really， really fast。😡，So you can imagine。

You have 10 programs to run and you let each one take an hour and then switch and for high performance machines like high performance computing machines where they have processes that take hours and hours and hours。

 this may be one strategy where they do batch processing or they have very long time detas for switching on our modern mobile devices and desktops they're using the what UniX and other systems of the time pioneered of time sharinghar where they not only switch between applications。

 they switch between them really really fast to the point where。For at least some of the time。

 you have the illusion that the programs are running。Simultaneously now。

 I'm sure you've had programs hang where that's not making progress and you've had not had this feeling that they're running at the same time and that's partially because that program is really slow or not responsive but time sharing is the technique where you have many。

 many programs you want to run and what the operating system does as many of you pointed out is they make the profit the programs take turns。

On。The CPU and they do it so fast， like many， many times a second。

or once every like few milliseconds or 500 milliseconds switch between these applications。

 and because modern PCs are so fast， you get this illusion of sultaneous execution。

 you can also have multiple CPUs as one year，Collgues pointed out well you can't actually have multiple programs executing at the same time。

 but those are finite。Yes， yeah， that does mean the programs are running slower。So strictly speaking。

 yeah， they will， in some cases always have to run slur because they're sharing times。And in fact。

 they may even run slower than if you would run them back to back because of the extra time taking to switch between them because it takes extra computation time to switch between。

Processes of， I'll show you why that is。Briefly， but yes it will can make all the programs run slower now not necessarily there are a bunch of tricks that if you take O or an architecture class you'll learn about where if one program is waiting for input or waiting to write to disk or write to the screen。

 that time is wasted anyway， they're not using the CPUU and so another the operating system can schedule a different process to run during that。

Natural pause in the program。For certain workloads， you can minimize the amount of slowness。

Process gets， but if you're doing long running computation， yeah， there's not what you can do。2，2。

Make that it。Even as fast as running programs back to。Okay。

 so time sharing is the technique where you slice up the time that each program has to run on the CPU。

And the。The trick， the abstraction part of this， the abstract so there's many ways you could do this。

 you could write programs that are aware of the operating system and actually tell the operating system。

 hey， I'm done for a little while， schedule someone else。But。

The way time sharing works is it uses the process abstraction and the process abstraction。Gives each。

Program the illusion that it actually has exclusive access to the memory and the CPU。

So let me try to diagram this。呃。Briefly。So this is our physical hardware， this is the CPU and the RA。

And as I kind of hint it out in the first place。The kernel is the lowest layer of software that mediates your program's access to the hardware。

And excuse。And it provides this kind of idealized or virtualized view of the hardware。

 so when you write programs you don't have access to actually touch directly hardware。

 the operative system mediates that access to the hardware。And so with the process。

 what it does is it。呃。え。In a sense， copies。For each running process on the。that you've executed。

 so you have one only one， if you only have one processor there's two here。

 but if you only have one processor on your machine， then each running program。

Is given a virtual bubble。Where the program believes that it is exclusively running on the processor and that it has exclusive access to the entire RAM space。

To your entire ramp。And so this is where the process of abstraction becomes a lot more meaningful at the operating system level because for the running program。

You， as the programmer， can write hellello world。Without worrying about all the other programs that are running on your machine。

 you can just pretend that you're going to be loaded into memory and exclusive access to memory。

 that you're going to get exclusive access to the processor and your entire program will be run。

And so the process abstraction defines what the process has access to and how it gets mediated with hardware。

 and it's the operating system down here。At the kernel layer that looks at these two running processes and schedules them to actually run。

On the machine， yeah。This is very similar to how virtual machines work， yeah。

 you can think of a kernel as a virtualization layer。

Now virtual machines historically were emulators。Where instead of giving。

Access to the physical hardware so modern operating system processes。

 your program will be running on physical hardware。

 like your instructions will be loaded into the CPU。With traditional virtualization or emulation。

 like emulating game consoles， for instance， the hardware you're running the virtualizer on is not necessarily the same as the hardware you're virtualizing。

So maybe you're emulating an NAES Nintendo from decades ago。

 but you' were emulating it on an X86 architecture， so in that case the software。

 there's a software definition of the machine that is executing。

 pretending to be the hardware executing the operations。

 but in this case and actually modern virtualization as well have techniques for making sure that the programs actually run on the bare metal。

 so it is very， very related。Virtization in fact， modern operating systems have support to make virtualization faster so that they work much closer to this where the virtualized programs are just getting time to run on the bare metal。

So yeah， very related， you can think of the kernel as providing hardware virtualization in a sense。

 but it does it in a way that's much more efficient than just straight up emulation software friendly。

Okay， other questions about this？So each one of these bubbles。Is a process。

And we'll actually see some commands for how we create processes and look at processes on the operating system。

But at its most fundamental level， the kernel provides an API for you to create a new process。嗯。

And to replace that process's memory with whatever program you want， there are actually two commands。

 fork and exec， which we'll look at in a couple of weeks。And so yeah。

 Colel provides this API for creating and managing processes on your machine。

 and the beauty of a process is that it makes each program believe that it's running exclusively on the hardware and without having to know anything else is the programmer。

 the operating system will schedule use of the actual hardware for each running process。

So because of this， we can have hundreds， thousands of running processes on a machine that has a single CPUU and you as a programmer don't have to do anything special to take advantage of that all you have to do is know how to call the kernel and tell it to create new processes for you。

Questions on this， questions on the process abstraction。So what's a process？A running program。

 that's all it is， and the reason that we have this abstraction is for scheduling and providing this illusion。

 this virtualization of the hardware。うう。

![](img/4102035c7abe5cd6125719f03dfbf1dd_5.png)

Okay， so to see a little bit about how this actually happens。



![](img/4102035c7abe5cd6125719f03dfbf1dd_7.png)

At the hardware level， let me show you the same。呃。So this is this book has like a。

AHmade kernelel to illustrate some of the ideas。And the processes the way the kernel manages swapping between different processes。

Is actually pretty straightforward， the CPU， if you member a computer organization and logic。

 how much state does the CPU have？So we have RAM， but we have the CPU， the CPU has some state。

 has some information that it holds onto to， what are those call？Registers it has registers。

 and that's really where almost the entirety of its state lives now there's complexity with caches and RAM。

But。Fundamentally， the processor state is just in its registers。

And so what the operating system does is。so actually the way schedulers work is every X number of milliseconds。

 the kernel will take over， start running and when the kernel takes over that stops whatever process is running and it literally copies。

The values of the registers at that time， so the process， your program stops running。

The operating system copies all of the state of the CPU。

storetors it in memory somewhere and then restores the state from a different process or starts a new process。

And then it starts running， that process stops。The operating system takes over。

 records the state of that CPU， puts it into memory， and then restores。

Your old process that was frozen。And it just does this over and over and over， many， many。

 many times a second， freezing and restoring the state of your process。

And that's really all it needs to do in order to resume what your program is doing at the CPU level。

That kind of makes sense， yeah。ううん。So threads there are several ways to implement threads。

 but you can certainly use processes or something called kernel threads。

 which are effectively processes。That works the exact same way。

So you can implement threads using kernel processes， they sometimes call them lightweight processes。

You're managing them within the same program so you don't need all the same information for a different process。

Effectively here， these are。Same idea as threats， it's how you can implement concurrency on the same。

🤧Excus。AndThen there's other information that processes have associated with them like open files where they have RAM。

 so the RAM is divided up in a different way it's virtualization。

 which you'll learn about of take operating systems。

 and when we talk about processes and standard IO， there are also files associated with each running process。

 but in order to achieve this time sharing trick。All you really need to do is copy。Save and restore。

CPU state。The CPU won't know any difference。Except for saycaing。

 which actually can lead to security vulnerabilities， but in the theoretical model of a CPU。

 all of its state is in its registers。Quions on processes and how this magic of processes work yet。

Yeah， 100% so what your fellow colleague is asking is if you're swapping all the time and so you probably own a computer organization that the CPU is caching RAM accesses and instruction and data accesses and so can the cache go stale every time you swap it absolutely yeah so there are。

So this is outside my expertise， but there are designs that will help ameliorate this。

 there's algorithms for when you evict stuff from the cache。

 there's a separate cache for virtualization that helps keep the translation faster。

 there's all sorts of tricks at the architecture level and at the OS level to make sure that you have like better cache performance and people actually like spend a lot of time optimizing kernels hardware designs to make sure that when you're running a browser in your email that you'll run as fast as possible that you'll avoid slow RAM accesses。

 so sure yeah there are lots of techniques for doing this in computer science outside my expertise。

 I don't research these。But yes， that is a problem。

 caching can also just have a larger cache tos one solution to deal with it。All right。

 so that's the process abstraction。Let's take a look at how in the UniX world。

 we create new processes。So there's a。Those my slides。

So there are two instructions that are used to create processes in the UniX world。

The first one is called fork。And perhaps counterintuitively， Fork doesn't actually create a new。

New running program， it just copies your process in its entirety， including the program。

 so when you run Fork， you actually have two copies of the exact same running program。

Wch seems a little counterintuitive if you want to run a new program。So the instruction。

 there's another instruction called execec。which overwrites your running program with a new running program with a new program machine code and so you can run these separately。

 you could run exec by itself， you could write a program like Hello World that then executes LS。

And you can just call exec and say， okay， operating system。I don't after this point after exec。

 I want you to take this other machine code from disk and I want you to overwrite my memory and start executing that code。

 that's what exec does， so it doesn't actually create a new process。

 Fork will create a new process and in the Uni world these are decomposed into two separate steps。

So yeah， Fork will yeah， the two programs will continue running when you have Fork。

And the common idiom is that in one of the new programs you calling Zec to replace it。

 so that way your old program is still running and then your new program is also running in a new process。

So we'll actually write this when we get we' actually got to implement our own toy shell。

 and we'll actually use Fork and Exec to run programs the weight bashed us。

So kind of like I put up the cell division here， it's kind of like cell division where you make a copy。

Of an existing process。And interestingly， this is actually the only way。

In user space to create a new process。In the kernel world。So that kind of begs the question。

 how do you create？The first process。And so when you boot your machine。

 the first process is created during the boot process outside of your control， it's called a knit。

 used to be called a knit， I think nowadays system D is managing the。

A knit on a lot of distributions like abu2， but basically during the boot process。

 one of the things that happens during boot is the very first。You a root process is created。

And then any new processes that are created during the lifetime of your running machine are all forks of a knit or some child of a knit。

嗯女。So what you end up with is。A processed tree。So you can see trees show up a lot in computing。

You have this。A knit process。And when there's a lot of programs that get created during Bo after and it。

But new programs are created by forking。From an it。And eventually bash will be forked。

When you log in and when you start running your own programs like， for instance， you run PWD。

PWD will our bash will fork itself。🤧It will go fork itself to create a new process for you and execute the PWD program and then when PWD is done。

It will。trolWell， the input of your keyboard will return to Bsh。So that bash can。Fork。

Other commands like LS。And you end up with this。Process tree。

 which you can actually see on your own system with there's a couple different commands for running it。

 but PS。Is the program for inspecting running processes？And this little secret sauce here， AxJF。

We'll print the kernel tree。So here's the Enit process， it's actually a program called ait。

You can see it has process ID zero and is the very initial process。

And then all these other there's a little ASIR here to show you child nodes here。

 but all the other processes are some descendant from the inI process。I can even look for。마연。

Oh sorry， that was lab， can look for my own processes here， so here's my SSH session。😊。

Where the SSH process， SSH is another program， it's a process， and it's a child of something。

 probably of some SSH demon， it created it forked an SSH version of SSH for me。

This ultimately forked bash， and you can even see here， here is the PS program forked from Bsh。

And less because I also ran less to view the output of this。

So here's the process tree in the realel in your UniX machine。Questions on this。

 questions on the process tree， the style， you'll read about this tonight。

 so if your homework tonight is reading about this design yeah。That's a good question。

 wheres the question Mark oh here？Oh， this is the。This is the what do they call teletype。

 or used to call this is like the terminal， what terminal it's associated to or what terminal it's writing out to。

 so most of these processes are not associated with a terminal。

So the ones that are like logins from people， so you can see we can actually spy on the other users on the system so other people are logged into the system and they have different terminals。

 so in the old days there were physical terminals that were connected by wire to a machine now we have virtual terminals like over the internet yeah。

No， this is not homework， homework， homework will be reading about processes。Right。

 all have use this， all of use this， yeah， this is all of useless this so you can look at least look at the processes for all use so we can actually see。

 okay， yeah， let's not look at that。But you can see mine， at least。Yeah。

 so if I had other running processes here。As you'll see in the video that I recorded for next time。

 the advanced processes， Eustace does not allow you to keep processes running when you exit。

 which is a little unfortunate because there was a tool I'm showing you I'll show you next time in video that benefits from being able to be run after you exit but EustAace is configured to not to not permit that so all these people are logged in have a。

Maintaining a connection to the machine。Okay， so there's processes。

 there's the Uni philosophy of how processes are created。

 they're always created by forking an existing one。

 so that means you have to have an initial process， that's the init。

Program which you can actually see here， actually you can see threads here as well。

 so I think I don't really know how this is implemented。

 but I suspect this is the kernel functionality for doing P threads like kernel threats This is the inI program so there's literally a program I guess called ani。

That is the first okay， so system D nowadays on a2， so this is the admit program。Okay。

 questions on the kind of theory of processes。In the operating system world。Yeah。

They don't necessarily run from it， but they may run from a descendant of it。So that SSH demon。

Actually might be that actually might be run from a it。

 but my best shell is run from the SSHD process， which itself has。As an ancestor。

So just like in this tree here。Where my best shell， its parent is like SSH， the SSH demon。And yeah。

 so all the ancestors， the ultimate ancestor of all processes， isn't it？On the machine。Okay。

 so let's look at how we can actually work with processes。嗯。In bash。

One of the benefits of using a shell is that we can。

Have some pretty low level control over the operating system， including processes。

Oh sorry baash is our command line shell so Bash Bsh is the name of a program that implements a command line shell。

 so the command line it's another program actually it's another process that runs and there are other shells like Z Shell or TC shell。

 there are other implementations of command line shells。

 there are command line processing programs we'll actually write we'll write a simple version of a command line processor for one of our projects。

 but Dash is。The name of one of the implementations of a command line shell and it has its own syntax and its own scripting language。

嗯。And yeah， it's a popular one as someone I use yeah。あ面の？sell。

The shell is the program that you interact with。Yeah。

 the shell is just a program that you interact with that you type commands into。

 called a shell I think it's called a shell because it's a very lightweight program that allows you to operate over the kernel。

 I don't exactly I don't exactly know the history of it。有在。Oh， because it surrounds the kernel Well。

 the kernel itself has protections， hardware protections against it。Okay， yeah。

 I think that makes sense， so the shell wraps around the kernel。

 it's like a thin wrapper around the kernel that allows you to access a lot of the low level features of the kernel。

 like what I'll you today like process management。呃。Yeah， so that's all bahees， yeah， not a。

Not a bad question， bash is the name of a program that is one implementation of a kernelel operating system shell。

Okay， so。Let's go over using the shell。To manage processes。In the Uni world。

So I already kind of preview some of these， if you want to view all the processes that you've created。

In your bash session。You can think of these as the descendants of your bash session。

 more or less the PS command， which is kind of short for processes， we'll show you those processes。

If you want to view the pro on the whole system， you can use PSAUX。And so。

I'll show this trick next time， but you can use the less command in order to navigate through this whole list because it's a giant it's a giant file so you can scroll backwards too if your terminal allows it。

 but here's all the running processes on。This is EustAace。

 so these are all the processes running on Eustace。Don't think this is secret information。

 everyone has access to this if they can log in。A batchsh session is so when you log in to so the reason that。

Let me go back to。My login here。So when you call SSH on your machine。

You're opening an internet connection to use this。And when Eustace receives that connection。

 after it does authentication， it starts running a program on your behalf， it runs the BH program。

And what the Bra program does is just reads your text that you type over the SSH connection over the Internet connection。

And so all that really happens， all SSH really does is that just when you connect。

 it just starts running a program for you。That program happens to sit and wait for your input。

And it weights over this virtual terminal and when you type。AsCI when you type on your keyboard。

 ASCI data goes to that BH program and that BH program interprets that instruction and then does whatever the program to do。

 whatever you ask。でよで。K of makes sense。Oh oh， so there's the only difference is whether they're basically。

Programs that you invoked during your bash session。Versus programs that were invoked by others。

On the machine。So it's just by default， the PS command。Will。

Only print the processes that you've invoked from your current batchsh session。

 think of it as like the descendants of your B session。

 whereas PSAUX will just start from we'll give you all processes in the entire machine。

That's all it is， it's just a convention， it's like when you type CD without arguments。

 there's some default behavior and the default behavior of PS is just to show the processes that you've invoked in this current SSA session。

We already looked at the processed tree， Ax JF， this will show the whole tree。Okay。

 so running programs， creating new processes in BH。

 we actually already saw this it's very straightforward， you just type the name of a program。

 Bash will go out， find the program， and it will fork an exec for you。

So that's why when we saw the tree here。You saw that PS。

 which I invoked from the command line is a child at Dash。

 so the DH program itself ran Fork and execec。And started and created that process for you on your behalf。

And the command line shell， this design know， this is designed by people。

 but the way they designed it was you just literally type the name of the program and it will go off and create the process for you。

 the running program。So that's all you need to do to run a program。

 you just type the name of some existing program。And pay better。

 and it'll go create that process for you。So we talked a little about command line arguments。

 this is just also the design of the shell， this information will be passed to the running program so if you've ever written into Maine。

Or in mainin int Arc AV and ArcC you brought that right and you probably wondered why why don' I have to do that the convention is is that the information from the shell command line。

 all this stuff after the command gets passed to your main method through ArcV。

That's where that information goes， and it's just a convention in the UniX world to use that information in order to control the behavior of your command line program。

Yeah。I mean I think it's just design the bash， like it's kind of an interplay between the design of the shell and the design of UniX programs。

 so the shell will break up the arguments for you ahead of time and pass a list of those arguments。

 it could certainly just pass you a big string right and just like make the program do it itself but it's just a design to pass in arguments。

And you can see these conventions here。There's a。A function called GetO。

 which helps with command line processing in the kind of UniX style。

Okay so how does the shell know where to get these programs。

 so LS is obviously not here in my current directory。So in the kind of UX world。

 there's a list of directories that the Shell looks at in order to look for programs。And again。

 this is just a convention that is used in the UniX world you want to see if you want Bsh to tell you where it found that program。

 you can type the W command。So which will give you the full absolute path of the program that it matches that it finds from this set of paths。

So that's why， and this is exactly why if you are trying if you compiled a C program yourself。

And you were hoping to run it with Ho， the past's going to be like。

 I don't know where that program is， the reason is because your current path is PWD path。

I not known to Bash as a place where programs live。But you can always give Bash a path。

 a relative or absolute path to a program。And run it that way。

 so that's why you have to type dot slash in the experiment， it's just a design。

So that programs that are run without a path。Are given in a well defined set of directories。

 and there's some kind of sensible security reasons for that I guess。That's just the UniX design。

Okay， so that's the path so I went over this already。

 so there are some commands so I type which CD there's no path here。

 why is that because actually CD is a built in command in the D program。

So Bsh will interpret your commands， there are some things that are built in like CD。

And so they don't have a program for them。🤧。Okay， so let's say I write a program named CD。

How would I run that program？That's like C D， Yeah， or whatever path to it。 It is exactly right。

 That's how you do it。 So CD is a built in that dash like reads。

 and it won't let you run a program called C， D。 Yeah， but you can always give the the path to it。

 yeah。So path is an environment variable。So another design of the shell is that there。

There's a set of persistent。Variable that Bsh maintains。And these are。

These range from a lot of things you can see here， it's like the name of the Shell program。

 the language you're using， your current working directory， and one of those is。

The path and the path。Defins the set of programs that Bash will look up。

 it's really just part of the Bsh design that these notion of environment variables and actually all Uni shells have this。

Yeah。No， it just holds data， it's just data that is used by various tools used by the shell by the shell environment。

 so for instance there's no like one use for these environment variables， it's just a data store。

 persistent data store for the shell that you can use for all sorts of things one thing that it uses it for is to store the。

The set of paths to programs， to set of path the system programs。

 and these are all like configurable。Okay， so let me。

All right let me get through standard IO in the UniX world。

 so another UniX convention addition to shell variables and the design of the shell is that every process in the UniX world is given three files every time a process is created so this is done by the system so there's some kind of enforced file IO file standard that are on every process that gets executed and these three files are standard in standard out and standard error so collectively these are called standard IO which is kind of tangentially related to the standardIo。

 H inC。So the question is why do this， why make every process？😡，Have three files。

 so I don't just let the programmer open it。So what do you think， like why bother doing this。

 why force every program to have it yet？都ぜた。Sure， if you leave it up to the programmer。

 then they might not do it。They may not yeah。Okay， so somebody who knows the Uni world already。

 I'll show this next time where you can， so one of the benefits of this is exploit this to。

Liked together， chained together multiple executions of programs piping their input and outputs together This is a more advanced thing that I'm going to show show next time。

But I think part of this is also that comes from this focus on the interactive shell。

 so whenever I invoke a program。嗯。The shell is always or the terminal is always there as input and output。

And so if the shell is always there as input and output and like your fellow student said。

 if the developer didn't bother dealing with standard IO。

 then where would the input and output from the shell go。

 you'd have to tell each programmer to do that instead the operating system provides standard IO and the C library with like print F so when you all wrote print F。

You didn't bother saying where it should go， you just said， just print F。

And the reason that works is because the operating system gives you a standard output on every process and printf。

 you don't have to open a file， you don't have to， like you said。

 you don't have to remember where to put it or where to write that information yeah。Yeah。

 you includeH to standardH， it's actually standard， it's standard IO is what it stands for。

 yeah it looks like it does look like a dispelling a studio。

 but that includes the library functions for operating on。It's more than just standard IO。

 but it also operates on IO， file IO。Within C。But yeah。

 so that's I think a lot of the reason is that by having a default input and output。

 if you have an interactive shell， then you always have a place for information to be passed into the program and information to come out of the program。

So when you're running the shell， standard IO， so Echo is another program。

So Echo is a program that just takes whatever argument you put it on the command line and print it out to standard out。

 So where does it go when you're running in an interactive shell， it just goes to。

The interactive the terminal， the terminal session。

 the terminal session can read data and can write data。

But where does standard income from so CA is a program that writes out whatever its input is。

 whatever input you give it it'll write it out and so again without saying anything else the Bsh session already has input and output from the terminal and so it'll just redirect that input and output to whatever running program you've executed so cat will take whatever input you give it and write it out so I can write hellello world here and you can see it gets printed out by the cat command yeah。

Yeah， touch creates the file on disk。But cat will read from the standard input。

 which when I'm running Bsh is my terminal and it'll write to the standard out。

 which when I'm running Bsh is also my terminal。Yeah。That's a good question。

 so standard input and output is not defined ahead of time。So you can change so in other words。

 in the program， the programmer doesn't have to know where standard in and standard Out comes from。

 that's kind of the beauty of it is that the operating system just gives you standard input of standard output。

 depending on how you execute the program， you can change where standard in and standard out come from。

So when you're running dashash。The BH program will make your terminal session standard in and standard out。

Exactly， yeah， yeah， so when I run cat here or so G is a command that searches for a string。

 so if I write a bunch of text into the Grep command，And one of my lines is hello。

 you can see that the GP command will write to its output， whatever input matches。

 that it matches the argument that I gave it。Okay， so this seems almost a little like trivialvia like why。

 I mean， yeah， I have a terminal， I write to a program and I read from it。

The beauty of standard In and Standard Out is that because it's not programmer defined。

 it's operating system defined， you can from outside the program change and redirect where standard input and standard out go。

So I give this example with gripP so okay， so this is one of the cool tricks with the dashshed commandline is that I can write some extra suffixes to my commands to redirect standard output to different places in this case。

 I can redirect to a file。So here， normally when I type LS。

 it writes to stick my shell because standard out is now being redirected to my terminal。

 but I can redirect it to a new file so this is my LS out file。

 and you can see the terminal no longer shows the output。Instead。

 the output has been written to a new file， so you here's the new file here， LS out。

And the CAT program， if you remember， from a couple or last time。

 CA will print out a file to stand it out。There's the text of the LS command。That makes sense？

Sort of。So whatever output of command has。I can add this little arrow suffix。And a name of a file。

 and it'll create a new file and instead of printing the output of that program to the Bsh terminal。

It will create that file and add that text to the file。It creates a new file。

 this file called new fileile， let me give it a better name。So LS output。

It creates a new file called。LS output。You can see here I have a new file called LS outputput just created just now。

 1316。And the contents of this file， like if I type less。

Or whatever command you want to use to print it out， the contents of the file is the output of LS。

So it took whatever program you ran。Whatever output it generated is standard out。

 like the programmer LS probably wrote print app。Whatever output it had， or my Hello World program。

 for instance， writes is just printfHello World， I can redirect that output。To a file。

And that's without changing anything in my Hello World program， so when you wroteHello World。

 so this is hellello World。It just said printf。Print F prints to standard out and because you're printing to standard Out。

 my shell can change where that output goes， so in this case I redirected it to a file called out file for hellello and here's the text of that file。

Yeah。It's going to overwrite it， yeah， so you have to be a little careful when you use it so I could overwrite my out file for hello here。

And now my out for Hello has been overwritten with the output of LS。Yeah。Yes， you actually canapend。

 I didn't show that here， but in the slides， but if you do a double arrow。

 that's a very good question， very， very， very good very good thinking， if you have two arrows。

Then it will append， so I'll just append a whole bunch of times to my out file。

 and you can see here there's the old text from LS and Hello world multiple times for running that multiple times。

All right， so we can also redirect the input as well。So let me。Let me do an example with Gr。

So normally if I look at this user include。Standard IO file。

 it's got to print out this big long header file。And remember， GP will take your input。

And whenever it finds a line that matches， it will write it to standard out。So if I Gr for include。

 but redirect its inputs， so I'm not typing it on the command line instead I redirect its input from a file using an arrow D different direction。

 then what about what do you think I'm going to get as the output？I think I've lost people。

So when I run Gr C by itself， I have to type in。Stuff to pass a GP and GrP will match whatever lines I type in。

 so it matched include。If I instead pass in a file。Yeah。喂。Yeah， exactly。

 it'll print out all the lines that match the word include。

So instead of me having to type things to pass to G。I tell the bash shell to take this file。

 pass it as the input to grab。And then GE will run as it normally runs。

 and this is all without having to change the GP program。

 so just because GrEP works with standard in and standard out， like print F and scanf。

It will just take whatever input is given to it by the user， by the person who created the process。

Actually， yeah， you probably redirect it to a file and then ran diff or something。Yeah。

 so exactly right， so that's why it helps with development。Reect the。Yes。

 you can do both so I could redirect and say to a new file and save a new file called All Inlude。

And now the results of GrP will be in that all include file exactly right， Okay， so it is yeah， okay。

 so class over at this point， I think I've basically yeah， so I've covered everything。



![](img/4102035c7abe5cd6125719f03dfbf1dd_9.png)