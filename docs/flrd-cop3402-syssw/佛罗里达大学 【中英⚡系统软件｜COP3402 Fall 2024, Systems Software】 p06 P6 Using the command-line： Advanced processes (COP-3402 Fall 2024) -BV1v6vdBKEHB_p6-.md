# 佛罗里达大学 【中英⚡系统软件｜COP3402 Fall 2024, Systems Software】 p06 P6 Using the command-line： Advanced processes (COP-3402 Fall 2024) -BV1v6vdBKEHB_p6-

Welcome back to System Software。So last time we went over basics of processes。

 the kind of basic theory of the process abstraction， what it was for。嗯。

And how we can use some of the standards around UniX processes like standard input and output。

In order to help us be more efficient on the command line when we're running processes。

Today we're going to look at some more sophisticated process management techniques on the command line。



![](img/78dabf4952918fdeadad30d6bd224684_1.png)

So just to review where we are， we went over processes last time。

 and this time we'll go over advanced processes。Okay。

 so recall last time that a process is an abstraction or a virtualization or an idealization of the CPU and RAM。

The operating system provides each program with the illusion that it has exclusive access to。

The processor and Ram。 And so the kernel will provide its own address space and will。

Maintain the illusion that the process is the only process running on the machine。But in actuality。

 there are multiple processes running。And it's useful to be able to have processes communicate with each other。



![](img/78dabf4952918fdeadad30d6bd224684_3.png)

So to see how UniX designed was designed around this， this philosophy of process communication。

 this is the some of the philosophy summarized in an old AT&T article， the link is。In the notes。

 if you want to take a look at it。 And I've highlighted two of the。

Point pieces of the philosophy here， one is to make each program do one thing well。That way。

 instead of having to， whenever you have a new programming task going down and programming and see a new program。

You'll have a set of programs that are already there for you to help you do the job， for instance。

 like CAAT or less or text editors， or the programs that we looked at during navigation to help us navigate and modify the file system。

The second one is more subtle and we'll see how that works at the universe philosophy。

 but the second one is to expect the output of every program to become the input to another as yet unknown program。

And so this is kind of a subtle point in the UniX philosophy， but if you look at the tools。

 the kind of standard tools that come with a UniX installation。

 these tools tend to do one simple thing and have a pretty well definedfin output and input there's a lot of text processing that goes on I've showed a couple of these when in the past couple of classes。

 but let me show an example of a couple of。

![](img/78dabf4952918fdeadad30d6bd224684_5.png)

Tools that you'll find in most UniX installation so one is a program called Find which which sounds like it's a program to help you search。

 but really what it does is it just lists all the files in a file tree you might be wondering well how' is that useful。

Well， when paired with the second tool grip。Which searches for text and the input。

You can see that if we could combine these two programs somehow。

 we'd have a tool for searching for files in our file system。

 and so rather than us having to write some custom script or custom program to find files in a file system。

 we can actually use these two programs together。So， let me。

Show an example of each of these programs here。So here I'm going to start listing。 well。

 let me go into， let's say。The homework three examples， if I type find。

 find is just going to list all of the programs。呃。In the the tree。So I could save。These results。

Sorry， list of files， I could save these results to a file using the redirection that we talked about last time。

And you can see now this text file list of files now has。The same output that F gave。

Because we can redirect the standard out of find。With this arrow， we can save its output。

And so then we can use Gr here， let's Gr for say ACL， we can use Gr。嗯。To look at the。

Take this list of files as input， so here we're using the redirection of standard in。

To the GrP program。In order to have GrP read in the list of these files and the syntax of Gr with the usage of GrP is to。

Give the program name and then its first argument is a string pattern to match。So when I run。

 when I gr for ACL。On the input of list of files。It highlights for me the line of text that matches ACL。

I can similarly match for， say， FS。And it'll give me all the lines from the input that have FS in it now Gr has lots and lots of options。

 but for our purposes here we're just going to use this for。

Looking for a simple string in a text file。Okay， so that's what these two programs do。

 and we can use them together in a kind of clunky way by saving the output。

But because the UniX philosophy has a standard input and output for every program and that's part of the reason for having that standard input and output is to satisfy that philosophy of assuming that the output of a program is going to be used by some other program so you can set up these chains of tools。

There is actually support in the operating system and in the shell for stringing together multiple commands。

And feeding their output of one command to the next command。

So let me show this find example again without having to make a new file。 So before I just ran Find。

 and then I ran Grep， say ACL。What I can do instead of having to save an output file like this。

I can use a pipe to say instead of redirecting the output to a file。

Redirect the output to the input of another program in this case we're going to redirect the output of find into the input of GrE。

And so this command here。We'll do the exact same thing as we'll have the exact same output。

As these two commands where we saved。we saved the output to find and then we read that output into GEP and used it to search for a string。

Instead， we can have the operating system manage this intermediate file for us。

And because these programs have standard input and standard output。

It's straightforward for the shell to feed， to redirect and feed the output of one program to the input of another program。

And we'll actually， when we write our command line shell。

 we'll actually implement this feature in our own simplified command line shell。Al right。

 so let me show another example of using a pipe here， I'm going to use CA， which， if you remember。

 prints out the text， writes the text of a file to standard it out or writes the bites of a file standard out。

So here I'm going to use CAt， which writes out all the text of standardIio。h。And I'm going to grip。

For。The word head。So here we can see the word head appears on two lines in the input。

Can grab for other things， like include。So by combining printing of an entire text file。

 which seems kind of like， well why would you need。

 seems almost trivial to print out just the text of a text file when piped。To other commands。

 we can combine these。In nontrivial ways to quickly create a very complicated program from small pieces。

 kind of like Legos or building blocks， putting components together in this standardized way through standard IO to build up larger applications that may be useful to you。

So if you've ever thought you need to do some quick task and thought， well。

 let me write a Python script or let me write some script to do it。

If you learn the suite of these common tools that are available on Mu system and understand the philosophy。

Of using small well definedfined programs and chaining together with their inputs and outputs。

 then you can build up useful tools so for instance。

 if I want to count how often an include happens or the word include appears and a header file。

 I can run CA to print out the text of that file use GP to filter out only the lines that have included in it。

 and there's another command called WC word count which will count the number of characters。

 lines and words and a file so Da I'll just count the number of lines the actual tool is not that useful。

 but I just want to illustrate for you that you can combine these tools to get some sophisticated programming test done with very little programming effort。

So here I've counted the number of lines that have included on it in this standardIo。h file。Okay。

 so how do pipes work under the hood， so take an operating system class you may go into actually implementing how these work。

U。But you can think of- well， so let me illustrate how this works at the OS level first。

So what the operating system does is when Bsh asks to create a pipe。

The operating system actually has built in support for creating pipes。So the kernel。Will produce。

This pipe。Object。And so when you run， find and say it's output。Is。Now。

 let's say it's user Then we just run find on。 let's say we run find on the route。

This is the output of find。And Gr。Let's say we want to Gr for any instances of been。

In order to feed the output of find into the input of pipe， the kernel creates special files。

You might call these virtual files。And so this is where the file abstraction comes in handy because a file does not necessarily have to be data on disk。

The file abstraction is just something that can be read， have its bytes read and written。

 and so the kernel can just fabricate a device storing it wherever it likes。

 it'll likely store it in RA in this case， but the backing of the storage doesn't matter because the shell just needs to know that it has a file that it can write to。

And so the kernel creates two files， one to be written to and one to read from。

 and the kernel will manage all of the communication between these these two kind of virtual files。

So when the。Shell writes or redirects the output of find or whatever the first command was when it redirects that。

Output into the pipe。inputput file。The kernelel will automatically feed。

The output into another file and the shell can redirect the output of that file into the standard in of GEP。

And so that it can。Give the output that we。Expect from combining these two tools。

So how this actually works under the hood is more the subject of an operating system class。嗯。

But just think of pipe as two special or virtual files that the kernel creates one。

File that you write to and one file that you read from。And through this pipe。

 we can communicate between processes。Okay， so let's show some more。Examples of。Piping command。

 so there's another useful tool called X Arcs。So， X As will take。Each line from standard input。

And turn it into arguments for a given command。So for instance， this example here。

 it'll take all of the output find， which recall， it just lists all the files in a sub。

Take the output of this。And XAs will use each line from the output of find。

And it will pass it as arguments to the file command。

So I can use a little trick to show you what will get executed by。By by XARC。

 so it will take whatever program you gave to XARC's file here。

 and it'll pass each line of find as arguments to that program。

 So you can see here find gives you this list。Fileles here and XAs will turn a inlist from the input。

 however it's generated into arguments for the program you'd like to run。

So if I run a find pipe that's output to。X As and have X As call file。 Re what the file command does。

 The file command。Will tell you what type of file。哎呀。We'll tell you what type of file you。Go？So if I。

Pippe the output of fine to X A's file。 This will run file on every file in。The output of find。

So I could do this for say。Hello。Programmed to give something， more interesting here。Okay。

 so that's how you can。T there's a special program called XARC that will turn standard input into arguments for a given command。

And so I can use just these set of tools to build some pretty sophisticated text processing tools。

So let's say I want to look for。All dot H files in the include directory。

Probably almost exclusively dot H files here， but not entirely there are some non dot H files。

 there are also directories， which I may not want to include。And so I want to filter out。

Only those files that contain。Dt H。 so don't worry so much about the syntax of gripp。

 but this will give me all of the files that end with dot H。

And I can use XAs to print out the beginning of every file。

 so head will print out the beginning of every file。

 but the point here is I can pass all of the output from this filter find。

Into another command in this case， head。So here we see the first three lines of every program。

So I actually use this in my research work， so I work on some build system analysis。

And I can do some pretty sophisticated。It's a very simple。

 straightforward but sophisticated analysis of some of the code。

 so just to show a quick example of this。I want to find all files in this is the Linux source tree。

 so this is all the Linux source code。I can find all files that have the name cake andfiig。

And in these files。Our。Definitions of。Our definitions of configuration options。

 this config crash reserve。For instance。And so I can use XAs to G and ask repP to look inside of each of these files。

 each each of the files that matches K confiIg as found by find。

Look inside of each one and find all cases， all lines from those files that match this pattern that start with the config keyword。

And str together a few other。呃。Stringing it together a few other。So。Fan like hacking here。

 stringing together a few。Other commands here。So for instance， I can。

Just get use cut to split the lines of code。And then to handle any duplicates， I can sort。

The list find only the unique ones with unique。And。Take off。The confit keyword。

And count them with WC。 so this will tell me all of the unique configuration options that appear in the Linux kernel build system。

So anyway， I just want to show a more sophisticated case of combining together a whole string。

Of tools to answer some questions that might be hard to write a new fresh program for。Okay。

 so anyway， so there's there's a variant of pipe。Where you can pass。Both the standard。

 So pipe will only pass the standard out by default。 But you can。 there's a shorthand for。

Passing both the standard error and the standard out。So， for instance。

 if I were to use pipe here and look for。Some text。呃。

This text is being printed out to standard error， so I still want to be able to match that text。

And I can use pipe。Ampersand， in order to。Pass the text to grab。

So if I wanted to look for something that wasn't there without piping the standard air。

I would still see the standard error。Okay， so that's pipe and some of the other more sophisticated things you can do with pipe。

Let's turn to managing processes on the command line。

So one of the something that I think lot a lot of people sort of know already is that you can kill a long running program so if I run find on the entire。



![](img/78dabf4952918fdeadad30d6bd224684_7.png)

![](img/78dabf4952918fdeadad30d6bd224684_8.png)

File system。It's probably going to take a very long time to run if I want to kill it。

 I can type control C。And it will kill the job。Or at least it will ask the job to stop。

One you might be less familiar with is that a control Z will pause a job。嗯。



![](img/78dabf4952918fdeadad30d6bd224684_10.png)

So let me hear the action show that。So you can see the job being paused。



![](img/78dabf4952918fdeadad30d6bd224684_12.png)

So here we get。A line from the shell that tells us that this command has been stopped so。

It's not still running， but the process still exists， so if we type PS。

To see the running processes in our current terminal session， you can see that the find program。

It's still a process， but it's been paused。So。So if we want to resume a job that we've suspended。

 we can use FG for foreground to continue running the job， so once I do FG。

 this fine command which is currently paused or suspended， will continue running。



![](img/78dabf4952918fdeadad30d6bd224684_14.png)

And I can use control Z to suspend it again。So foregrounded background is really a conceit of the shell。

 the operating system doesn't really distinguish between foregrounded background。

 it's really about whether the interactive shell can interact with the process。

 so foreground process， I can hit control C， I can hit control C， I can interact with it。

 I can see its input and output。If I use make a background process instead。

 then I won't be able to interact。With that， with that process。 So let me。

Let me show what I mean with the background process。



![](img/78dabf4952918fdeadad30d6bd224684_16.png)

So instead of FG if I type BG for background to put this process in the background。

Fd is running again， but I can't hit control C and kill it。



![](img/78dabf4952918fdeadad30d6bd224684_18.png)

none of the signals that the shell is sending。We'll go to。



![](img/78dabf4952918fdeadad30d6bd224684_20.png)

This process。Control C won't work。 Control Z won't work。



![](img/78dabf4952918fdeadad30d6bd224684_22.png)

So what I can do is I can take this process and type FG。



![](img/78dabf4952918fdeadad30d6bd224684_24.png)

It actually finished running so I can take this process。



![](img/78dabf4952918fdeadad30d6bd224684_26.png)

Put it into the background。诶。In order to make it so I can interact with it again from the terminal。

 I can type FG。 You can't see it because the text is being moved so quickly up the screen。



![](img/78dabf4952918fdeadad30d6bd224684_28.png)

![](img/78dabf4952918fdeadad30d6bd224684_29.png)

I can but I now have typed FG to put it in the foreground and now I can use control Z to suspend this or control C to suspend this process。

So that's really the only distinction between foregrounded background and you can control whether a process that you've suspended goes into the foregrounded background with FG and BG。

 these built in commands and bash。All right， so let me bring this into the foreground。And kill it。

So this is just describing what I just described to you。Yeah。

 showing you that I can kill it by bringing me into the foreground。 All right， so let's let's。

Let's show this Ampersand sign。 So ampersand， if you put Ampersand at the end of a program。

Our end of a command。It will immediately put it into the background， so for instance。

 if I grant fine slash。And use Ampersand as the suffix of this。



![](img/78dabf4952918fdeadad30d6bd224684_31.png)

I can'tm hitting control C now I can't kill it because it's the I told the shell to immediately run this process and put it into the background。

But I can still use FG to bring it into the foreground。

 so I just typed FG even though the text was moved off the screen。



![](img/78dabf4952918fdeadad30d6bd224684_33.png)

And I'll type controlrl C to stop it。And you can see here。

 I've stopped it by bringing it back into the foreground。So one thing to notice here is that the。

 even though I've put it into the background， the standard output is still flooding my screen。

With the standard output。Standard in is also being taken from the input。

 just no signals from control Z or control Z will be received from the shell。



![](img/78dabf4952918fdeadad30d6bd224684_35.png)

So we can actually have multiple processes that we manage at the same time。

So here I'm going to redirect。The output of find into Devbnell， so I don't see it on the screen。U。

So I've used Ampersand to put the process into the background。

 You can see here the shell has told me the the process I D， and I can confirm that。 Oh， actually。

 it's running so quickly that I can't see it。 but you can see here this is a find program running。

In the background。So。Without having to write to the shell。

 find and listing the entire file tree so quick that it ends pretty quickly。But I could run multiple。

Jobs in the background。And the jobs command will list all of the currently running processes and their state。



![](img/78dabf4952918fdeadad30d6bd224684_37.png)

So if I have multiple background processes， I can use the jobs command you know now find exit already。

 but I can use the jobs command to selectively bring whatever job I'd like to the foreground so they're numbered here。

 these jobs are numbered here， I can bring the rep command to the foreground here。

And continue interacting with it。You can see that this commands being run because we can tell because when I put in a line that had hello in it。

 it matched。So I've still got that cat program running， could bring it to the foreground and kill it。

So it turns out that control C might think of control C as killing a process， but in actuality。

 it's really just asking the process to terminate these processes。

 these programs can be written to actually ignore。This， this command。

But you can really kill the process， so even running and k on a process is just asking it to be killed。

But we can really kill it。By using kill dash9， so this will。

Send an uninterrupttable signal to the process too。啊， kill。The process。

 so actually it already exited， so let me show show that in a faster way。

So send this in the background and then。Kill the so money sign excation point is just the last commands PID so I'll use that too。

Kill， kill the。The process， the process in an uninterruptted way。Okay。

 so all this is say is that you don't have to remember all this or how to use all this。

 but one kind of quick and dirty way to do development quickly on a remote command line where you know it may not be obvious how to run multiple pro by using foregrounding and backgrounding。

We can have a very quick and dirty。Development workflow using job control。

So let's say I go in to edit my。I program here and let's say I've got a bug。So I write this program。

 I've got a bug。Instead of quitting your editor， you can use controlr Z to suspend your editor。

You can see jobs to confirm and PS to confirm that indeed my editors still running。

And I can go to run my compiler of the command line， see that I've got an error。

 so instead of going back in。Typing everything out。To go back and edit my program。

 I can just use FG to immediately resume my editor， go back， fix any bug。Save it。

 suspend without quitting。And I have a very quick and dirty development workflow here using the job control that we have available in Bsh。

So there are better workflows， which I'll show you when we get to editing。

But this is really good for like quick scripting tasks， for instance。

 which something that I also use frequently when especially using remote systems。Okay。

 so let's show a more sophisticated job management solution for remote systems these are called terminal multiplexers there are local ones。

 there are remote ones I'm going to show you one tool that will you can use on a remote system used as has it installed already。

And yeah so let's take a look at it。 So Biobbu is a wrapper for managing terminal multiplexs Ter multiplexs just a way to have multiple terminal sessions from a single login so let so first let's let's initialize Biobu this is something you'll that you should run when you。

First， go into Eustace， run this be open control a command and hit two for emax mode。

This is just an historical thing。 So the terminal multipctors traditionally use control A to enter commands。

 but that conflicts with Emax and bash。 So we're going tell it to go into Emax mode to actually use to not capture this。

 this command。 So don't worry about this too much the details of this。 just for some initialization。

Okay， but let me show you what Bobu does for us。I'm going to type Bobu。

And you'll see that it looks like I've almost kind of relogged in。 I have a new dash session here。

 I'm still in the same login session。 I haven't relogged in again。 And then I've got this。

Status bar at the bottom with all sorts of information and you can configure this if you like their instructions and。

In。The notes， if you want to configure this。So I can。Use the shell just as normal。

 but if I'd like to do some other work。sayy I'm editing in one window， building in another。

 or I need to do some system administration and I don't want to interrupt my current show。Hitting F2。

Will give me a new。Bash session。You can see at the bottom here。That。I've got a little indicator。

That will tell me which。Terminal session， I'm in。So I can switch between these sessions with。

 So that was F 2 with F 3 and F 4。 I can move back and forth。 F 3 goes left。 F 4 goes right。

 I can move back and forth and switch between these sessions。 So here I'm in。Scrreeen 1。If I hit F3。

 it will move me back to Sc  zero。 there's little highlighting and an asterisk for to tell you which which screen you're in so here。

Let'm going show you that。These sessions are ongoing。 I haven't exited any batchsh sessions。

 and I can make lots of these can make one，2。Compile。And run。And use the。

Shell history to very quickly compile and rerun。And I can use F2 and F3 to switch between different batchsh sessions without having to change directory or kill a session。

 so if this' here I can go look at the include directory。And all the while。

 my other sessions are still。

![](img/78dabf4952918fdeadad30d6bd224684_39.png)

Active and running。All right， so normally。Well。Without any additional configuration。

The sessions should be retained across logins。And you can see it's retained in the same log。But。

This system has been configured。To kill。User processes on。Exit。So， yeah。

 you won't be able to use to be able to stage your sessions on Eustace。 And this。

 I think this gonna make sense because the assessment probably don't want like。

Thousands of users to leave processes running。So unfortunately， you can't use that feature of Bovo。

But。

![](img/78dabf4952918fdeadad30d6bd224684_41.png)

You can still use it and so you know firing this up。

Whatever you're going to do development is not so hard you just。Run Viovo。

 hit F2 to make new sessions， use F3 and F4 to move back before between them。

 or alternatively you can use alt left and right， at least on my terminal session， I can use that。

And you can always just quit a window with control D or exit just like you would a batch session。

Okay， so that's unfortunate， but let me go through the。

 so if you're on another remote machine that you control or that doesn't restrict offline processes or processes that you can run away or logged out then。

Then you can use that， but you can still use this to help you with running multiple proceed。

 having multiple terminal windows。Okay， so we learned a couple of things today。 We looked at pipes。

 We can。Chain together multiple programs to do。

![](img/78dabf4952918fdeadad30d6bd224684_43.png)

Larger。Tasks。So here I just found every file path that has。The word bin in it， so there's 32。

00 of them parallel。So that's pipes。You can manage processes， you the main things to look at here。Or。

The control Z for suspend， you can go back， drop into your shell。

 run whatever forgrounds you need to run。And Fg to resume。Then we also saw Bobu for managing。

Remote sessions， so it won't preserve it on Eustace， unfortunately。But you can still use it for。

At least having multiple。Windows open at the same time， Multi bash windows open at the same time。

And navigate between them。So here I can swap between my editor and my compiler。All right。

 so that's it for advanced processes and see you next time。



![](img/78dabf4952918fdeadad30d6bd224684_45.png)

The homework for next time is to go through a tutorial of one of these two editors。

So these are two very， very popular command line， only editors， well EmX has a Windows mode as well。

 but these are editors that you can use on use this solely on the command line。So I recommend emX。

 this is what I use， VIM is good to know because of its command set is commonly used in other applications。

 but EAC I think is a great great editor， Id strongly recommend it it's a little more intuitive to get started with although also a pretty。

Pretty esoteric tool。So for this until。The next class。Pick one of these， as I said。

 I recommend E or do both and go through their tutorials。So to go through their tutorials。

 these are accessible。On the command line。From uset this。 So for Emax， just cut and paste this。

Tutorial command。And this will open emax with the tutorial。

 and it'll have instructions in there to navigate the tutorial itself。 So it'll it'll tell you。

's read over the whole thing。 It'll tell you to。Use C V to go to the next screen full of information。

 etcter。

![](img/78dabf4952918fdeadad30d6bd224684_47.png)

And if you get lost or get stuck， you can use this quick command in order to leave， so controlr X。



![](img/78dabf4952918fdeadad30d6bd224684_49.png)

Ctrol C， we'll quit。Vim has a。Special command called Vm Tutor。Which will open up its。tutor。

 it's tutorial。And again， it has instructions for navigating for you。In here。

 its quick command is also a little esoteric， it's colon Q and then enter。To quit。So pick an editor。

 I recommend EmX。Pick an edit or go through both these shouldn't be more than around 30 minutes or so to go through these I don't think and then just answer a little survey on what editor you chose。

 why， etc ceter， that's yeah that's all you'll need to do for the next lecture。All right， thank you。

 have a good week。

![](img/78dabf4952918fdeadad30d6bd224684_51.png)