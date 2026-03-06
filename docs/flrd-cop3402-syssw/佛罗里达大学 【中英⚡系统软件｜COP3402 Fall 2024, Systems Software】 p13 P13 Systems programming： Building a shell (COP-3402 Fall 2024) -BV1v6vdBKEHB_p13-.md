# 佛罗里达大学 【中英⚡系统软件｜COP3402 Fall 2024, Systems Software】 p13 P13 Systems programming： Building a shell (COP-3402 Fall 2024) -BV1v6vdBKEHB_p13-

And welcome back to System softwareftware。So we are at the end of our system programming。

 systems programming section of the course。bitit of a crash course and systems program and I know it's probably unfamiliar for probably most of you have not done systems programming。

 but hopefully as you've done the mys project， which is。Do this Thursday。

We've got a little bit of a feel for how this system call stuff works。So yeah。

 reminder that this is due on Thursday， I'm starting to get more questions on Ed STEM about it。

So does anyone have any like quick？Questions besides， you know。

 if you have specific advice for your program， come to office hours this week， otherwise yeah。什么意思？

Library。The witch？For what？What it what does it do like the？Oh， oh， oh， oh， yeah， yeah， yeah。 Yeah。

 You can use the string。So I think I have a comment here。Yeah。

 so I assume you know how to do you malik and string andcatein and stuff。What's that？The project。

 so you look here under submitting a project。There's very specific instructions about using Git to submit the project。

Oh， I think he said email it， sorry， you have to mail something。不抽不到。

I can't remember for this project， I don't think so。

 I'm sort of assuming you know how to do C programming， you could use MalC。

I'm trying to remember if I did， you may not have to。

You may be able to use automatic local variables to do that。

 but I'm just assuming you know how to use Ma。The code for what？Well。

 I gave you example code in this using files。For how to use the various system calls。

 so if you look at this project， these are the system calls you'll need to use。

In order to finish this project。So if you're not using all of these。

 you're missing something or you're using some other library that is not directly calling these system calls or library calls。

I gave examples on using。All of these system calls in the。Using files， lecture notes in the lecture。

 you can watch the lecture again。And the subsequent lecture， I even went over a little bit more。

And theres example code here。 So for instance， using P， here's an example。

 Here's an example of using open read and close。 Here's an example of using the De and the De directory entry system calls here is using stat。

And so my expectation is that you'll be able to write your own Cpro man。

 cobble together the algorithm。For myLs， for printing out these five pieces of information per file and looping over the directory。

But to help you do that， I've given you examples to show you how to use these system calls。

So you do it from scratch。But you have examples to show how to use the system call。

So I try to employ this and I'll show this today when I go over the next project。

 which is more complicated， but try to use this kind of what I talked about the tortoise and the hair。

 try to use this。This。Approach where you don't write code right away。

 instead you write out your algorithm， the kind of granular steps。

 the coarse grain steps of your algorithm。And then take each piece at one at a time。

 so don't try to write this whole program at once instead， all right， how do I do this number one。

 how do I get the names of each so for instance where do the names of the files come from。

 which system call？Does anyone know which system called to get the names of files from？The second？

Right， yeah， read De so if you look at the using files lecture I go over。

This code here for printing out all the files and file names in a directory。

 so you have an example of using these system calls。And so for number one。

 you want to start with pseudocode or start with comments to say， all right。

 I need to loop over all the files in the directory， I need to print out the name。

And so then when you go to implement it， look at the reference material。

 look at what I gave in lectures， look at the lecture notes， look at the page。

 and then start planning what you need to do。And only when you have a good sense of what calls to make。

 then start writing code and then start testing it， don't move on yet， start testing the code。

 make sure it does what you expect。And then go on to the next。Next one。

 so what system called do you need to find the number of hard legss？Statt says it right there。

 so in the notes， there's an example of using the stat system call。

So this isn't the exact code you need in the exact arrangement。

 but it gives an example of how to use it。And so you can incorporate that into your code。

Does that answer your question？Are right other kind of general questions on myLS？Yes。

as long as this self- checkck works， you're free to break up your program， however you like。

 you can certainly do a single file and one make file that has a single target to build your program。

 but this is the beauty of using version control and build automation is that you can architect or implement the code however you like。

 as long as I can clone it and build it。I and anyone else can use your code。

 and this is true in general of open source software the reason that you can just。Go to GitHub。

 download and build。more or less is because of this automation。

 and so that's why I have you do that automation so that you can architect things however you feel comfortable。

You can name things， however you like as long as we can run the code like this。This name of the code。

 we can build it and we can clone it。And this， you know。

 if you go into professional software development， this is the exact workflow that basically everyone uses。

 whether it's closed source or open source， this is the workflow this is the fundamental。

All right have questions we know and failed？You won't know， yeah。

 you won't know until you get graded。Yeah， so I think just come to office hours if you aren't sure we'll come to office hours and I' go over it。

 otherwise I don't know， I think it'd be unfair to give out the private test case afterwards because。

The people who submitted early didn't get that advantage， but we can go over it in class。

 they'll be similar to the public ones。Which will be released？But if you're testing on your own。

 when I' talked about in the first day of class， if you're testing on your own and following these directions。

 then you should be fine， the test case shouldn't have any kind of tricks in them。

 I'm not going to test like detailed error cases and things like this。

But as long as you're following these directions and if there's a misunderstanding the directions or I'm unclear then of course。

 you're not going to be penalized， I won't penalize you for that。

Some people asked about why their binary file was not being printed out， so why is it that， yeah。

 why is that the case that anyone figure out？Why you might have gotten weird stuff， yeah。あです。Yeah。

 this is， this is， so some people were getting non ASI characters。So here in the instructions。

 I say any non principle or non ASI characters。So non ASCI characters are those outside the ASCI range。

I think I showed this。Plus。So if you go St man， askky it'll show you all the codes for each letter of the alphabet。

 the nonprintable characters are the characters that aren't associated with the symbol instead there。

 like the new line character， tab， space。These are non printal characters。Yeah。There may be。Okay。

 yeah， you can use you can use C type， I just check the range when I wrote it， but yeah。

 are there are functions that are like， what is it like is alpha？Yes， C type。

 yeah there are some helper functions new free use that's what you're asking about C type right I think you're asking about like string electric kind yeah。

 you can use this stuff if you if it helps you。あ。Yeah， so it's like his printp。

But you can literally just check the range。All right， so that's my Ls。If you haven't started this。

 please work on it because they're debugging this kind of system call stuff is very is a little intricate。

 it's tricky to do even though the algorithm may be pretty straightforward so make sure you're working on this soon you know have there is a generously policy。

 but make sure you submit something。By Thursday， otherwise， we don't accept reubmissions。

Just to make sure you're actually like starting on the products。Okay， so that's my L。 All right。

 so let's get back into system calls。 So last time we left off with。Types。And if you recall。

Also first of all， what is a pipe， what's a pipe in the kind of UniX kernel world？Yeah。Yeah。

 that's exactly right， so that's what it allows for and the way it works is you ask the kernel to give you a new pipe。

And it's a pair of file descripts， it's kind of like a special file where the kernel will take any data you write into the pipe to the right end of the pipe。

And store it for you or buffer it for you in the technical jargon of the kernel。

And with the other file descript or the read end。Any process that reads that file will get the data that was written to it。

And by having this mechanism， you can communicate between processes， processes are isolated。

 processes think that they're the only program running on the machine because the kernel provides this。

This idealization or virtualization of memory and the processor。

And I also went over how this same concept is used for network programming。

So when you're connecting your browser or your app。

 whatever it's doing to some server and getting some picture or whatever。

 these are literally two processes， two UniX style processes most likely。

 depending on what device from pretty much all devices and most servers， these are Uni style devices。

 these are Uni style processes。That are reading and writing files， special files。

 and that file is a socket， which is like a pipe that works over different computers。

 different machines。So how do we create a pipe？In the UniX world。Okay， so in Bsh。

 you use the pipe symbol。What's the system call that's used to ask the kernel to create a pipe？Yeah。

Pippe， it's the pipe system call， yeah。So。The pipe system call gives you two file descriptors you pass it。

 so in C， outputs are not always through the return value， you can have outputs through。

The parameters as well。So you pass it a pointer to an array。

And the pipe command will populate that array with two function descriptors or sorry。

 two file descriptors， those are the in and out of the pipe。

And so the idea is if you have two running processes already。And you've created a pipe。

You can redirect。One of the running processes standard out to the right end of the pipe。

 and you can redirect the standard in of the other process to the read end of the pipe。

Does that concept make sense， questions on that？Okay， so let's go over how。

How we're going to set this up in our。Our implementation of a shell program。So just as a reminder。

 we're going to。あ。The project that starting today， although those up I already kind of introduced it to you。

 you're going to be writing a command line shell processor where you'll。Implement。

Let me show an example of a pipe here。You'll implement。

A command line processor that will be able to run， for instance。

 three processes at once and pipe the input， redirect the input and output of those processes to each other。

 so you'll actually implement。Kind of mini version of Dsh， a mini version of a shell。

And to actually implement this， you'll do all the forking and exactecing and piping to set all this up now in principle it it's pretty pretty simple to kind of put in a diagram。

 but you know using the low level system calls you'll have to kind of carefully do error management and set everything up properly yeah。

Ah， so the pipe system called doesn't know。The pipe system call doesn't actually know。

 so let me go over the kind of what I call the if you have a bash process。

 the process that's kind of controlling this whole。This whole procedure。

So this is a little review from last time。U。So the way what Bash will do is it creates the pipe。

 but the pipe is just two file descriptors， there's nothing about。

 it's just and those file descriptors are open in which process。

 which process are so if Bash creates the pipe， which process。Has the open filescript？いや。And yeah。

 so yeah it's the parent process， whoever calls pipe。

 so if Bsh is the parent process and you haven't created any other processes。

 when you create new open files or file descriptors。

 those belong to the process that called them so just like when you open a file。Your program。

 your program as a running process has those open files。In its。Process descriptor table。

 let's fine file the descriptor。So you'll create this pipe。And then。

And then in order to set up the two processes， you need how do you create processes in Uni。

 the UniX world？Fork。And does that- so if I fork a new process。

 am I running a different program at that point？No， why？Exactly。

 all Fork does is literally duplicate all of the metadata about your process， including memory。

 its memory layout， whatever is in memory， which is includes to the running program。

So how do we change the running program of an existing process？Exact， right， that's what Exec does。

 so together Fork can Exec create a new running program。From a parent process。

So if you have this bash process or this master process， the parent process。Create a pipe。

And now your parent process has these two new files that you can read and write to。

But in order to redirect。Data between two other processes， we need to create those processes。

 so we create one process that we'll use for so say we're doing piping LS to WC word count。

We'll fork a new process。And then we'll redirect it standard out to the pipe。

And then run exec to get the LS program running。After we do that。

 we are kind of set up the WC program， we' going to fork a new process。

Replaces it standard in with the read end of the pipe。And then run Zec to。

Actually start running the WC program。

![](img/08df0a55bd33077204f949b8691ab886_1.png)

So let me diagram what this looks like。

![](img/08df0a55bd33077204f949b8691ab886_3.png)

Why did this happen？So here's this algorithm for doing this。So your shell will be called。My shell。

 so that'll be the parent process of everything that runs。So who runs the myha process。

 who forks that process？Yeah， who's the parent of Michel shell？What's that？Wow， you a process？

Are you a running program， I mean maybe metaphorically， yeah。Exactly yeah bash。

 well so yeah if you're running it from Bsh which you will be for doing this test but exactly right。

 so you run Bash and then when you run a program Bash is the parent of that program that you run so up here somewhere is the Bsh process and when you tell Bash to run my SH it forks and execs my SH for you。

Because remember， you can't create a new process without。Forking from an existing process。

And where does the initial parent process come from or where does it get created？What's there。Well。

 that's the standard output but the initial process。And， yeah。

 it's in it process by convention that might be implemented in different ways。

 but when the system bootss。The boot process creates a new process for you that starts with one program that you give。

 the colonel will say this is my initial program and then from there that's the ultimate ancestor of all processes。

Okay， so we have our my SH program running。And so looking at this algorithm。

 the first thing we do is we call pipe。To create。A new。Pair。

OfFile descriptors for the read ended right end of the pipe。

And which process do those file descriptors belong to？W in， who's the parent？M H， yeah。

 the myH now has two new files that I can read and write to。Then we want to set up。The fork。

 the process for。Running。My are LS。And is this LS yet， is this the LS program yet？No。

 it's just a copy of mySH。便告诉。F creates a new process by duplicating the existing process。

 so now technically we have another process that's also running mySH at this point。

So how did we do something different to make sure you know， if you're running the same program。

 it should be running the same program， how do we write a program that does something different in the child from the parent yeah？

And what do we put in the switch statement， what do we test？Exactly， yeah。

 so the return value of fork is the only difference between these suproes and that's what the kernel S suffer is so at this point we're just running a duplicate of my SH。

And so we'll check that we're in the child。And so does this process have？

The pipe file descriptors are not。Ah，It duplicates everything， yeah yeah。Yeah， duplicates everything。

 including all open files。😡，So this also has access to the pipe。Filescriptors。

Because it duplicates everything in the process， including its open files。And that's the trick。

 that's why we can do this redirection。Before we start running LS， yeah。Well。

 so file descriptors reflect open files， not the contents of the file。

 so for instance if I had opened like hello。c， you wouldn't expect me creating a new process to make a new copy of that file。

 right？It's just creating a new file descriptor that points to the open file。

See the difference so that's the open file versus the file itself kind of like the process versus the program。

 so file descriptors are open files。And when you copy them or when you make a new process。

 you're not duplicating the files， you're just making a new pointer to the open file and the open file is again。

 another table in the kernel that it manages。So this is just a pointer effectively a pointer to the new to the file。

 and this pipe file is， it's not on disk because files don't have to be backed by storage。

 files and abstraction。It's managed by the kernel， so in memory in the kernel somewhere there's a buffer to store。

😔，The contents of this pipe。Okay， so this copy of MySH has access to the pipe yet。えとしたもい。Well。

 we will still be in the parent because the parent process is also still running。ただわれびたさ。Oh， well。

 there will be an error code， so can that's why you do do error checking， so fork fails。

Then you check the return value of four if it's negative one， it's an error。

Then it's the you're in the parent， then it's the so this is guaranteed by the this is the kernel's guarantee so if just at if you look at the return value for fork。

Child process is zero， nonzero is the process idea of the child and failure is negative one。

 so all possible cases， at least that the kernel defined。

 so it should never return less than negative one for instance as long as you trust the kernel is written correctly。

Okay， so we've got our new process， it has access to all the open files including the pipe and so what we do in order to make sure that LS will go to the pipe instead of whatever standard out is so at this point if I've。

Forked from Bash originally， what is standard out as long as I don't do anything else when running it。

 what is standard in and standard out for my S H？😔，Yeah。The terminal， why， why is the terminal？Oh。

 because bash。Bashs standard out and standard in were the terminal。

And so what happens to- so standard in and standard out those are open files。

 what happens to open files when you fork， or what happens yeah。

 what happens to the open files when you fork？They get duplicated。

 so if bash is standard in and standard out were the terminal when it forked your program。

It will inherit that standard in and standard out， so it's not that standard in and standard out are always the terminal。

 it's that they're always duplicated from the parent。

That's why it's standard in standard out of the same， that's why when you run a program in Dh。

 it'll print to the terminal。Without doing any redirection。Okay， good。

So what is standard out and standard in for this copy of my SH？😔，Terminal。

 why duplicated everything of mySH and why did my SH have the terminal？Because of Duke Ed from bash。

 good， yeah okay。Yes， that's right， so that's a good question so if you call bash with redirection like you redirect to a file。

What BAS does is actually what we're going to see right now， it uses du in order to overwrite。

The standard IO of my SH before executinging it。And so actually。

 if you can wrap your head around how this pipe process works。

 you'll understand how redirection works at the kernel level as Bash does it。

 because when you redirect to a file， it's kind of a simpler version of pipeping。

You're just piping to an open file instead of to a pipe file， which will get read by another process。

 so that's exactly right， so bash has standard IO as the terminal。But in its implementation。

 when it sees that you've given this little arrow， it will use Do， it'll open a new file。

 and it will use Do。To redirect the standard out of my FH。Before exacting it。

So let's actually see how that works。Here we can see how this redirection works。嗯。

In this in your MySH program， so we have forK here standard out and standard in are duplicates of mySH。

 so however you've run mySH in the first place， that will be the standard in standard out。All right。

 so does everyone remember how to redirect or change？Standard in and standout。

So that's the dash syntax for it， so the system call to do it， yeah， back there。否则。Dop。

 doop or doop2 see somebody asked about do two last night I went over had to read the manual again。

 they're all very similar， it's just that dope。Dop with nothing will so it it's dope is the was the original system call I guess do two is the two parameter version。

 du three is the three parameter version， that's why I think it's called do2 do3pe one will just。

Use whatever new file descriptor is available， so file descriptors are just from zero。

 literally a table， a base zero table of open files。Standard in out and air。

Are the first three file descriptors of every process， zero1 and two。So if you want to use Doop。

 you would first and you want to redirect standard IO。

 you would close one of those file descriptors thereby freeing it for a new open file and Doop will just take whatever file descript you have and just copy it to whatever open file descript you have Doop too will do the closing for you。

 it will overwrite。Its an easier way to do and and I think unless it doesn't have raised conditions either。

 but an easier way to。Override or redirect an existing open file。对。So it's， yeah。で。

So actually to a new file descriptor is the target that you want to close and modify。So it's it's。

Yeah， it's kind of confused I'll go through the actual code of this。

 but it's kind of confusing depending on what you think is old and new。

 so old is like the one you have open already and new is the file descriptor that you want to copy into。

So you'll see when I get into the code， but O will be the pipe。

File descriptor and new will be standard IO， standard in or standard out。But I'll show the code。

 I'll show the code，三ビジか。ItIt's。So at just point， so the process just has a list of open files that that you've called open so whenever you call open。

 the kernel will it maintains a table of all the files you have open。

 open will add a new entry to that table and it'll have。

What kind of file it is it'll have where in the file you are so if there's on disk。

 you can seek the different positions， it'll actually keep track of the current position so you can use like read because read read is not ienpotent I guess is the word every time you call read it actually moves the pointer into the file to a different location。

 but it's just a list of open files and information about what those open files are。

 and other internal kernel stuff like caching and things like this。Okay。

 so before we get the actual code， let's see how do works kind of conceptually。So right now。

My standard out， I think it file scriptor zero， is the terminal。And so when we call do。

 what we're going to do is we're going to take。We're going to call dupe。On the。Right end。Of the pipe。

And we're going to。Overr。The stand the current standard out。Of this process， this myH process。

So what that's going to do is going to take this。Zero file descriptor and instead of。

Pointing to the terminal。It's going to redirect。Or overwrite that file descriptor with whatever file descriptor give or。

 overwrite it with the in the right end of the pipe。😡，It makes sense。So this is what Duke does， will。

Take this。Standard IL file descriptor。And it will。Change this。They read。Whatever green。

It'll overwrite that file descriptor with the new file descriptor。That way。デパ？The pipe。

 the right end of the pipe， that's what you'll get from the pipe system called。This。Oh yeah， sorry。

 so I've overloaded the meaning of these arrows， let me make this a little less。Overloaded。

So forget about thosearrow， that arrow were like inputs to the du function， let me。Let me do this。

In a more kind ofman semantically coherent way， so let me say。

So this arrow means open file scriptor0 or standard， let me just call this standard out。

 it doesn't matter the number of it。So right now， standard out is pointing to the terminal。

When I call dupe。When I call Duke， what it does is it redirects， it changes the standard out。Into。

Whatever file inscript that we get it， so now standard out。Is。

Pointing to the pipe is the pipe open file descriptor， so this is what dupe。This is what Duke does。

 it changes the open file descriptor to be whatever you gave it。Well。

 so what standard out is is just。The first open file。

 so standard IO is just the zero1 and two file descriptors。So whenever a process is created。

The system。Pre allocates。The first three open files of every process。

 that's the standard that's what standard IO is， it's just a convention that says whenever you make a process。

 allocate for me the first three open files。By default， it's whatever the parent process wants。

Because。Exactly。Because batchsh calls fork， it inherits。

 the process inherits whatever those three open files were。Exactly， exactly。

 and that's what you're going to be doing in this， you're actually going to be implementing what D effectively does。

 you're going to be doing your own fork。Going to inherit standard I。

Redirect it and redirect it is just changing which file the standard I don' know is pointing at。

That's effectively all it is， yeah。Yeah， yeah， yeah， it would be too， it would be too， you're right。

Okay， so that's redirecting。This copy of mySH to the input of the pipe。Yes， yeah。

 if I fork from here， yeah， you just have another copy of my SH， it's standard out would also be。

The pipe， because all the open file descriptors are duplicated， a good question。对。requires。

W followed the fear period。So if you have to bedirect。Yeah。いう状在。AhI'll show it way after the code。

 you call pipepe and pipe will give you file descriptors。

And you just save those file descriptors and use those in Dope to overwrite standard out。

But I'll say that I want to get to the code， all right， so now we've got a due process。

It standard out has been redirected to the pipe。So now if to run we're not actually running the LS program。

 we've just set up the process， the kind of metadata of the process。😔，How do we now run？LS。

In this process。Exact， yeah， exactly。So what exec does？Is it？Overrs。The current processes。呃。

Running program。With a new one， so this is what。Execec will do and I we talked I asked you about variations of exec。

Kind of like a very miative detail， I'll just I'll give you an example of which one to use for the project。

We've got LS running。With its standard out being redirected to the right end of the pipe。

So how do we complete this do we get？I said it， but I didn't write it down。

 but we're trying to implement LS pipe to WC， what is WC？改变哎，不用。OhYeah。Oh yeah。

 word count WC all right so how do we now？How do we do the WC part， let's have you guys walk through。

 yeah， I think your hands is up for us yeah。Okay， so let's fork my cell again。

And so what program is running in this process？My essay， it's good。Okay， let me ask someone else。

 what can we do next？十十九。Good， so what's the standard in right now of my shell？Great， yeah。

 exactly so standard in is now。The terminal。Okay， good， so we use Duke 2 just like we did before。

To redirect。So to redirect in this case， standard in。The arrow here means like。Well。

 maybe make you It go this direction。So my arrow semantics are very loose， okay。

 I don't have like a rigorous semantics in my arrows but。When you use Dukepe 2 here。

 you're redirecting the standard in to the read end of the pipe。Yeah。Yeah， it does， it does。

 and in fact， when you so good practice is actually to close that read and right end。

Because you don't need it， you could get away of not doing it。

 but if you beat the Linux program or Facebook。It's cleaner。

 you close the end of the pipe you don't need in that process yet。So remember。

 programs don't get forked， processes get forked， so this isn't like the text of the program。

 this is a running program。And that gets forked， does that make sense？

Or you asked me something out it。Oh oh， so okay， that's a good question， so when I did this fork。

We had the MI H20 program and then the child version of LS H。

I forked from the parent the original well yeah from the original parent process you'll see when I get into the code how this looks it's more straightforward than you might think you just check if you're in the parent and and then go to forRC the other program but hopefully it'll be clear when we look at the code but yeah that's that's a good question okay so we've redirected we forked we forked my SH again we've redirected instead the standard in。

To be the。Read into the pipe。So now what's the last step？To get this whole pipe set up。

SomeSomeone different， oh yeah， yeah， yeah， good。Exactly we exactec。The WC program。So exec will。

TheExec will overwrite this program to now run WC， so a little messy， but now we set up。

The whole pipe， and because Zec just immediately starts running the program。

LS will already have started running， most likely， at this point。

 depending on how a scheduler is working， and already have started populating this buffer。

And then the last thing to do， which we'll see in code is in the parent so the parent is still running here。

So the last thing to do so you don't certainly have to wait， I think if you don't wait。

 it'll kill the pro and so these may not actually finish。But especially in Dash。

Without giving other information and without giving other stuff on the command line。

 know having background processes and stuff。What Bash does by default is it waits for all of the processes to finish running。

 it doesn't allow you to enter more command until all the processes have finish running。

And the system call for that is called wait， wait will just wait for any child process to finish。

It'll block， the program won't continue until one of the child processes finishes。

You wait after you've set up after you do fork Ex and pipe for both。

And then once all of this is set up， then you call weight， you actually call weight twice。

 you call weight all the child children that you have weight is a system call， it can have errors。

 I've given up dealing with weight is kind of kind of annoying so I've given you a little piece of code that'll just。

 kind of。Carelessly， just wait for every process in a loop。Yeah。W我就 wait for。性の？

I think that's probably right， I don't know， well it's not a so I don't think it's a signal。

 but it just the kernel will just block。It was a stop execution of the program until an event happens so under the hood it may be implemented with some messaging or signaling。

 but from the programmer's point of view， it's not asynchronous。

 it's not an asynchronous signal instead just like reading a file if you're waiting for the file to be loaded from this。

 et cetera， the rest of your program is not going execute until that kernel call。

 that system call returns， so wait works the same way， it's called block it， it blocks。It waits。

 the kernel will not let your program continue until that weight function returns。

 just like any function。呃，有科。嗯。Well， the pipe will still exist。

I am very unclear about parent childild like healing pro。

 you can definitely kill a parent and have proheies still run I think of a parent。

It existed without waiting and may kill its children， I can't remember， does anyone know？

But you can certainly like write like a shell script that invokes processes， killed a parent。

 and they'll still run。呃。Yeah I think these are called like zombie processes or something where the parents has died and nothing is there to wait for it and the child I think it's a little problem with the kernel like cleaning things up because the parent is supposed to be the one to wait。

 but I think you can， I'm pretty sure I've finished sure I've done this where you can have the parent process killed and still have the。

But I'm really unclear on how the parentchild and the zombie stuff works in the kernel that's an area where I haven't looked to enough。

 but in my personal experience， yeah， you can I've had problems where the child process does not die。

Kill it， yeah。I said， does answer a question？ますが。It moves the child to admit，Thanks。Yeah。

 I mean you could， yeah， you could。Yeah。You technical like that。But I wouldn't for the program。

 I would just like make make crap。I mean，s so it's just open files， so any process that。Was for。

Has access to the pipe， and the parent still has access to the pipe。

So if you close a file in one process， but that file still open in another process。😔。

The process can't read or write from it， that you close it in， but the other process can。

Because it's not the file itself， it's effectively a pointer to a table that represents state of the open file。

😔，So yeah， all of these process unless you close。The file closed the file， the filescriptor。

They'll all technically have access。To all both ends of the pipe。Yeah。

 so if multiple proxies have the same open file descriptor in the UniX world。

 they can all write to it。And it's kind of up to the。Colonnal to order that。

 depending on how the process is scheduled to be run， you can end up with situations where like say。

 two programs are writing hellello world。It may interleave hellello world， it might be HH， EL。

 oh you， it might be interleaved so there's no。否则。Well， that's where the tools of threading。

 the critical sections。I mean， like。啊。Managing multiple processes at the same time， like locking。

And these techniques for' managing synchronization that's work that's where synchronization tools come in for sure so the kernel does not provide kind of have any specific synchronization when you have multiple files。

 it's arbitrary depending on which process gets scheduled so there are additional tools I think there's a couple of classes here Multiproing it's very own specific and difficult area in doing synchronization it's a hard thing to do UniX doesn't provide it for you by default。

 but you can there are other there are tools for doing。Synchronization。But yeah。

 no other good questions。Yeah it just kind of punts on synchronization of the current。

 which just says， well， anyone can write to it whenever they are the running process。Okay， so that's。

Setting up a pipe， this is effectively what baash does when you set up a pipe。

And this also tells you how redirection happens instead of redirecting to a pipe you just redirect to。

 you open a file， you got a new file descriptor， you use Dupe2 to redirect the standard out or the standard in to or from that file。

 so it works the same way， the same system called。Yeah。

The reason is because we wanted to execute a different program。

So as soon as we went to call Zec on LS， that would blow away the MySH program。

 so the MySH program is what is calling Pipe and du。And exec。

But as soon as you call exec on a process。Any other code after that exact call does not get executedd。

Because the processes program。The memory where the set of instructions is stored gets overwritten by the new program that you've exact。

Yeah。他。That's exactly right yeah， so exactec doesn't do anything with processes all it does is replace it's the text segment of its memory where where the program texts the sort the binary machine code is stored so everything else about the process yeah。

 it's open file descriptors。Yeah， it's parent process， all that stuff stays the same。

 you've just kind of swapped out， you know you've kind of like made an imposter。

 you've swapped out just the kind of brains of the process， but everything else about the process。

Stays the same that's what， yeah， that's exactly why exactly right， that's why the redirection works。

And so the standard IO is more than just， well， it's the first three open filescriptors。

 it's a philosophy of writing UniX tools。When the developers of LS and WC and all these Uni tools wrote them。

 they wrote them to use standard in and standard out and standard error。

Specifically because you can do redirection。So if you know that every program is going to have。

 it's always going to use zero，1 and two for in out and error。😔。

And that enables this redirection to be possible。And you just like on the bahell， you can always。

 well at least for most for these standard tools， you can be sure that the information you want is probably going to be in standard out。

And then you can pipe it to other processes or save it。All right， so that's piping。

 let's look at how to actually implement。This pipe。Okay。

 so let's try using the kind of tortoise method or what's probably called the stepwise refined method。

 which I pointed this out early in the class。I'll kind of show this in action， yeah。Yeah。No。

 so if you look at the program description， no arguments for the project description。So， that's。

So this is the usage of it， you just call the program no arguments。

There are some tricks with actually you could you can actually pipe stuff to my SH because it's just using standard in。

 but well， that's kind of just follow the directions on doing that。Okay， so let's。

Let's see if I can quickly show this kind of stepwise refinement or the method I'm trying to instill in you or trying to get you to use before you write any code。

Write some， you don't have to write like a formal pseudocode algorithm， these pseudocode algorithm。

 these algorithms are actually pretty simple， it's just using the tools。

 the system called tools and it's hard。So let's， let me start with just。嗯。

Copying this kind of overall algorithm。So then we want to fork the process for WC。And same thing。

 the place that he sees standard in this time。With。The pipe。Run WC with the new standard in。発セ。Okay。

 where should start， where should we start implementingtic？Okay， that's a good place to start okay。

 so create a pipe。嗯。How do we figure out how to create a pipe， where can you look？Okay。

 so assuming you know how to use pipepe already， you could go look at my example code。

You could look at the man page， so I gave example code four pipes， so look at my notes。

 you can like use that， I wouldn't necessarily cut and paste it， I would look at it so let's just。

Show what that might look like if you're doing this kind of from。know， almost zero knowledge。

 at least about the specifics of doing this。So look at the notes it's in here， but here you can see。

 here's the call to pipe。We need an array and if you don't know what these mean。

 then look in the main page。But I can， you know， basically just copy。

Hand copy this code to set up the pipe for myself。So。

So I'm just looking the reference for the includes that you need for all this， okay。

 so I set up a pipe。I've done this。First step here of setting up the pipe。All right。

 so I guess let's， yeah， yeah， good ahead yeah。嗯。Actually， yeah， you probably could。

 I think it would have。Pretty much the same effect， I don't know if it'd actually be different but。

Yeah。I think you probably could do that。呃。Okay， so。For forking。

Oh this is actually the this is the program I'm writing， so we probably shouldn't look at this。

 this is too easy。呃。Let we go to process creation。All right。

 so the next thing we need to do is fork a process for LS， but remember。

We're going to do some redirection first before we fork。Okay， so。

How do we fork and how do we fork and make sure that we know the difference between the child and the parent process？

Yeah， we can use this switch statement。Or an if statement。So notice it's a single legal sign。

 that's a gotcha in C programming。So there was an error with fork here。Probably don't need a break。

 but。Okay， so now。In the child process， so before you go， you know like。

Copying whatever this is doing。 Keep in mind that this is a different program。

 It's it's not going to be doing the same thing that you necessarily want to do。

 but you can at least take the structure of fork now。 So now we've got the。嗯。

System call for the system call set up for fork Okay。

 so what do we want to do in the child process at this point？Right， so I'm going to just。

Copy my pseudocode in here to keep track of it， and in the parent process， what do we need to do？

Continue， continue forking and stuff， so I'm going to you know。Just。

Let this continue past the switch statement。So you can certainly put all your code here in default。

 but I'm going to use the C style of keeping the nesting pretty flat。So after this default happens。

 I'm intentionally going to leave this blank， know， intentionally left empty。So here。

I'm still in the parent process here。But in K zero， I'm in the child。Okay。

 so what you want to do first， should we continue with the parent process or work on the child process？

Okay， so let's look at the parallel processes there's two things we need to do。

 we need to redirect standard out。And we need to run with the new。run the new。Program。

So let's run the new program first because I think。

I think that's something hopefully everybody has seen this。

 so's I wanted to show here that you don't necessarily have to write this code。😔。

In a top down fashion， you can work on different parts。 You can do the low hanging fruit first。

 And I I would say also make sure you test and run this。

 I'm not going to go through that now because I only have 20 minutes left。

 but make sure you're testing as you go along。 I mean， do sanity checks。 Actually。

 I should do some sanity checks。Myself。So you can see I already have an error here。

 so make sure you're testing and running， so I forgot the PID。呃。Variable。Actually。

 it's supposed to be。If you look at the code， it's supposed to be this。O。So I've made a new PID here。

Program compiles， you should also try running it。And yeah， yeah。因。Absolutely， use Bobo。

So I showed this in， I think the lecture on editors。Which right， I know I was。Hopefully you got that。

 but use the Biobu tool。And now I can have my。Program here。And F2 to create a new session so I can。

Compilile my program here。And you can switch back and forth。けな。Oh， in B yeah。

 I think you can do split。Let if remember how to do this。Yeah， there's a way to split in Bohu。

 I would just Google it for using Bo， there's a way to split them。But yeah， you can do that。

 you can't do that。O。So。Get out here。Yeah， you'd be able to do it or you could SSH twice as well。

 that could be another way to do it。

![](img/08df0a55bd33077204f949b8691ab886_5.png)

![](img/08df0a55bd33077204f949b8691ab886_6.png)

O。I don't need that。All right， so I'm going to go through this。

 so make sure you're compiling and testing as you go along。

 but I'm just going to for the sake of time it's going to go through and finish up this coding example。

All right， so here I'm going to use。Let me actually use this。Other。

System call that I encourage you to use for the project it's called Exec VP。Instead of Ex VE。

 which I showed in prior。Prior classes。So what's the difference between executive VP and V。

 this was homework， right， this was a homework question yeah。1。やった？先輩？你。全国安。So yeah， I mean。

 the kernelel， the loader， has built in a capability to run scripts。And so it will， so that is true。

 I mean， I think you read this right in the Linux programming interface。Yeah。

 so this is having to do with the fact that the colonel can run scripts。

And execute a script interpreter for you。But yeah， that is one behavior that it does。

 but I guess in terms of like the arguments that are passed and the difference between file and path name。

What are the differences let's go here？い酒？いさ。Yeah， that's right and so this is super like detailed。

 but basically what you get is you don't have to specify the full path name of the program。

Exact V VP theP part will search the path for you。嗯。And the E part。

Means you have to specify the environment。 Otherwise it gets duplicated from the parent。

 But basically， this exact VP is the， I think the easiest way for you guys to run。A child process。

 yeah。Yeah， yeah， yeah。这玩意儿。What's say again？I mentioned this briefly when we talked about the like the path and the environment。

 So this is a Unix philosophy thing， there's just a set of。Variables that are defined。

For the running process， they include things like the path for lookups， the shell。

 your home directory。嗯。So this is kind of a UniX system thing， this environment。

 and so that parameter you can use to update or change the environment variables。

 there are some actually security consequences to the environment but yeah。

 it stores kind of useful things for your interactive system like your path。Yeah。Right。

 if it's in the path in your environment， yeah， exactly。Exactly。So all right， so let's try to run。

Exactly P。So if you just look at the。嗯。Mandage， it says， give a file。And give this pointer to an RV。

List。So let's just let's assume we have it。This kind of programming style I actually encourage quite a bit。

 this kind of backwards programming， So this is the main thing what we want to do。

 we want to call Zec VP。We might even parameterize this and say this is the progue name。

And so this imposes a requirement on you to satisfy。These variables。

 but this is really the main thing you want to run。And so you can just write， you know，'s。

 nobody's saying you can't write this。It's something that doesn't build right away。

So it's kind of a break， it's going to complain about this， but the compiler will actually help you。

 The compiler will keep keep track of this for you。 So this is the main thing I want to run。

 you know， I want to make sure。I do air handling for exec is just run exit afterwards。

Air handling as needed and look at the past lectures on system calls for air handling for exec。

But so， we got a set Progue name， we got to set up New ARC。

So notice I'm not even bothering to code here。Writing the main meat of what I want to do。

 which is run exec。😡，And then my compiler is going to you know if I don't notice myself。

 ther is going to check for me that I haven't defined find these things。

 so instead of going to coding instead I just make a more fine-grained pseudocode for myself， I say。

 all right， well， this is imposing two tasks on me。

 so instead of trying to do all those tasks from scratch and not documenting it。

I actually write comments to say， all right， well I'm going to have to do these two things first。

And so that way I won't forget， It I won't get lost in all the things I have to do。 I've offloaded。

That work into comments， into documentation。And so this is why when you hear people say writing comments after code is really hard or have two lines of comments per line of code。

 what you really want to do is you want to have the comments as like pseudocode directing what your program is supposed to do。

 I mean there's many philophies you're doing this， but when you're trying to write from scratch。

 it's useful to use comments and other pseudocode or other organizational tools to keep track of what you need to do so you're not just coding blind。

 not just coding， trying to code from memory。You can， it's like offloading onto a stack。

What you need to do so you don't have to keep everything in memory all right。

 so how do we set up the program name it's a you know it's a string。So let make a string， right？

Run LS。And all right， so then we have this other task for ourselves to do here， New AV。

 this one's a little more complicated， just need to make a list of strengths。

 an array of strengths and look at my passcode for how to do that， you can also see here。

 how to do it。So I'm just going to make an empty list right now。O。So let's see if this program works。

So it doesn't like my pointer type， so I made a mistake here。This has to be a pointer to an array。

 not just a string。And already when I start running this， I'm already getting my LS process running。

法院。Okay， right， so when you write your bash interpreter。

 you'll have to take in a command from the user， figure out what they're running and use that。

 but I you know I recommend doing this。Step wise， doing one piece at a time， and so you can use。

 you know， this is why it's useful to use variables。Because while I'm coding this。

 I can just hard code something until I'm ready to change this to user specified string。嗯。Yeah。

 basically， so I have example code for showing you how to do this as well。But yeah。

 but do you see this style of coding where you break the problem down into the most fine grain。

 like if you're ever thinking， how do I do this， well okay write down steps first and then if you have to exact a program。

 then hopefully you know that you need some exact command。So you can freely write exec。

 you can freely just write it assuming that the parameters are already defined。

And then this task is done， so then that imposes more fine grain tasks on you to define to how to define these parameters。

 so don't try to do it all at once， break the problem down little by little in this style and so that way if you get this right。

You don't have have to think about this while you're getting a program name。And you know。

 you might say here。A comment to say， all right， we're replace with user input later。Yeah。

This end up in yeah， this ends up in the binary of your program。

 all these string literals end up in a kind of data space in your binary。That's right。Okay。

 so I've done this is the kind of stepwise way to do it。 Let me， let me show the。Actually。

 if it's take a time， let me just show the finished program so that because we only have like 9 minutes left Okay。

 but， but hopefully you get a little sense of this kind of stepwise refinement style of programming where you don't start with code。

 You start with comments。 You start with coargrained algorithm and then take a piece first。

 and break that down。 Don't code。 Yeah， break it down until you get to a piece that's like a single line of code or a single function or a single variable definition。

 And there's no rule that says。I have to write。This， before I write the function call。

 nobody's forcing you to do that and the compiler will check for you whether you've done that。

 whether you've done that。So this will hopefully help avoid the thashing code a lot test of something breaks。

 let me go back and look code a lot instead。I can test。This program， right now before I move on。

 which I did， I tested it， I had a little bug。So if you're coding here。

 if I was continued coding here。And I didn't bother to try to compile and run it。

 I would have been chasing this。This bug that I wrote。

 you know 10 lines before when I was thinking about something else。

 you're giving yourself cognitive load and programming。

And so great programming is not actually about being like super smart and keeping everything in your head。

 you can' for a substantially large program， it's about breaking the problem down， being organized。

 compartmentalizing things， using program extractions like functions。

 comments or tools like comments。To break the program down into easy parts that that are easier for yourself。

 That's the whole spirit of。You know if you're as clever as you can be when you write the code。

 how will you ever debug it， so write the code in the more simple minded way and then debugging will be a lot easier。

All right， let me show the final result here。So some of the variable names are a little different。

 but here's the pipe。And here is the first fork。So this is the whole first4QI use an if statements instead of a switch statement。

Here's the child， so the child code is a little bit more。

Involved here so let me let me go through it so there's our ex I use Ex VE in this version but the algorithm is the same。

 so there's the exact VE part。Here is what the pipe looks like。So there are。A few steps here。

One is closing the read end of the pipe。And then calling Dupe 2 to redirect。

And then finally to make things clean， I mean， it'll happen when you close the program。

 but also closing。The end of the pipe that we wrote to， yeah。Standard out， yeah， that's right。

 that's right， so there's really only three main things going on here。

Closing the read end of the pipe， which is kind of optional， your program will still work。

Calling dupe2。So that was if you look in our。In our file here， we've already called fork。

 this is the Duke2 part。Closing the right end of the pipe。Cleaer to do that。And then calling exec。

 so there's really only like three calls here。Close the read end of the pipe。

Duplicate the right end of the pipe to standard out。

Close the right end of the pipe because you're done。And calling exec。

You know that's why writing the algorithm is so much easier because you just have those four steps。

 I mean really two steps if you want to be like lazy about closing files。

 there's only only two steps here do and exec， and getting all the stuff around it right is not so much about doing top- down coding。

But it's about writing those first。Even if it's a comment writing that first。

And then setting up for yourself more finegrain tasks to do so once you've set up the exact call but okay。

 I need a program game， let me make that one task， let me off that in a task， all right。

 I need an argument， let me outload that task， don't try writing code。

 offload it into a comment same with Duke all right， I need to do Duke too。

I need the whatever the right end of the pipe is， you can even make a variable name called right end of the pipe。

And I need the standard out， you could make those variables。

 so you wouldn't even have to know ahead of time a priori which parameters to write， you could say。

 okay， I know I need the right end。Of the pipe， and I know I need the standard out file。

And you can write this code and you've already written the most important part of this part of the code。

And then that gives you two other tasks to set the right end of the pipe。

And to set the standard out file so that way you can break these tasks down without having the cognitive load of thinking about the whole holistic program and so at the right end of the pipe。

 you might say， all right， I know it's in pipe FD。So。

Let me make a new variable here for the right end of the pipe。I know it's pipeFD， but you know which？

Which one is it？And so at this point， because you've offloaded all the other tasks。From your mind。

 you can just focus on this one little task。And go out， look in the man page。Okay。

 the pipe zero is the read end， so I need pipe1， the right end， come back。Finish it， build。

 try to build it and test it well you know it's not going to build it's going to tell you that you have standard out missing。

 but if you made a mistake here， the compiler will help you a little bit。

And then work on the standard out。So you can just look at my example code for a lot of these parameters。

But I could have easily just written it this way instead of getting out this exact code in this exact way。

Questions on this， questions on this style of coding。Yeah。Yeah， you have several weeks from my SH。

Let me。So my S is yeah， 1022， my S I made this。Out pretty long because I thought， yeah。

 it might have some tricky news。So take a look at the rest of the notes。From today there's。There's。

Example code for processing the strings。Assume you know some string processing。

 you can use the string tote function I I've given you the code for doing this so you can use that for processing the input all right。

 all right everyone， so see you on Thursday， bye。

![](img/08df0a55bd33077204f949b8691ab886_8.png)