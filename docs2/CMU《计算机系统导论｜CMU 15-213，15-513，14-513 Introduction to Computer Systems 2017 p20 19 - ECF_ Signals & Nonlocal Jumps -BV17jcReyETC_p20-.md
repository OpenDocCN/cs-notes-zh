# CMU《计算机系统导论｜CMU 15-213，15-513，14-513 Introduction to Computer Systems 2017 p20 19 - ECF_ Signals & Nonlocal Jumps -BV17jcReyETC_p20-

我来。はい。

![](img/4e269ed3f846ba40c9b38218551b0ec9_1.png)

O啊。和标玩。Getting ready for the exam， but as every this course just kind of marches right along。

 so we'll do two lectures this week just with new material。I have to finish up。

 I didn't get through all the material from last Thursday though。

 so let me finish that up and then move into today's material。

So you recall last time we started talking about the idea of processes。

 the idea of one computer can execute multiple independent jobs。

 or running programs known as processes by switching between them and generally doing so at a rate that so fast that you as the user don't really observe the changes。

 the difference。And then we mentioned the sort of。From a programming perspective。

 the way you create processes， new processes is bias。Called to fork。

 And fork is a very odd function in that you call it once， but it returns twice。

 It returns once to the original executing process， which is called the parent。

But it also then spawns a new process with a complete replica of all the state。

 including the program， whatever data has been created， even the state of the stack at that point。

And that's called the childd。And so and then when the function returns。

 it's re either into the parent or into the child and the way you can just determine which is which is what the return value of four was。

 it's zero for the child， it's the process idea of the child for the parent。So。

The end of life of a process is that it terminates and it actually goes through a two step process that it first terminates and then it is reed and so the term of there's a term called a zombie。

Of a process that is terminated， meaning it stopped its execution， but it still exists。

In the eyes of the operating system， and it has to be， it's still consuming resources。

 there's various tables。Seets of files and so forth that the operating system maintains for all processes。

That are either including the zombie processes that until they are reaped。

 that's when the operating system is basically reclaiming the space form。啊。

And so normally this is done。When you wait for a process。Or， or when a。A parent exits。啊，我啊。

When you wait for a process and we saw there's both weight and weight pin as function calls that you can do so the parent can just wait until tell it。

Child completes and when it。Part of the executing weight is the operating system will reach that child。

So that's sort of normal when you do spawning a bunch of processes and then they all come back and you wait for them。

 then this zombie business isn't really an issue。But it's a problem and we'll see examples of it today that if the parent doesn't wait for a child to finish and instead it just returns。

Well， when the parent actually exits itself。the parent itself terminates。

Then it basically passes the responsibility of reaping to the initial process and it will do it for you。

But the problem is for a parent that runs forever or for a long term， such as a server。

 a web server or any service that you set up。 And it's a program that has no definite stopping point。

 If along the way， it's been spawning children。And those children have been finishing。

If they haven't been reaped， then they all become zombies。And that can over time。OfDa， weeks， months。

 however， along the server runs， it can actually basically cog up the whole system。

One of the reasons you'll notice that the shark machines reboot every 24 hours。

Is because a lot of students do this in the next coming lab， the Shell lab。

 they create these zombies that are floating around and so basically by rebooting the system once a day。

 we kind of flush out all that stuff。So it's sort of a very drastic way to deal with this issue。

So here's an example of some code that。You see it calls fork and within the child。

 the child just exits。But the parent。I doesn't really do anything， the parent just runs forever。

So not a very exciting program， but it demonstrates this idea that the parent hasn't done anything about its terminating children。

And if you run this program and by the way， I'm going to give up trying to do demos of programs。

 it seems like it's just。Too many quicks on a screen and takes too much time but I recommend all the code for this is on the website or reachable via the website。

 all compiled， ready to go on a shark machine or you can copy them yourself and compile them yourself and so I recommend you sort of play with this just to convince yourself that this is really what I say is true。

But what this example program does then when it starts is it fire up。The process， it calls fork。

The child terminates or it says it terminates。And the parent runs。

But now if I and you'll see that this。Invocation here of Forks。That I'm showing here。

 I put an ampersand at the end of the command line and that says do the command， execute the command。

 do it in the background， so return back to the shell and just got this program run and this will be a very important concept we'll talk about today。

And what you do then if you run PS， which just is process status。

 it lists all the processes for you right now and there's various command line arguments to it。

 but this is the basic version of it， it lists all the executing processes。

 all the processes that you have。And you'll see that。It shows two that are labeled as forks。

 and you'll notice the process Is that 6639 is whenever you run a background。The shell， the。

Interface， you have the command line interface that you have to the system will print the idea of the process that was just created。

And you'll also see that the program said own， by the way， the child has process ID。6640。

 and you'll see that that here we see two processes， 6639。

 which is the parent and 6640 which is the child and here the notation that it's defunct is an indication this is a zombie process。

 it's terminated， but its resources haven't been reclaimed yet， has not yet been re。Now。

 if we kill this process， this case， we do it explicitly with a command where you say you just say kill。

 and then you give a process ID。hen it will terminate the parent and in doing so that the zombie child sort of is then inherited by the main initial process of the system and it will do the repay。

So by killing the parent， it also knocked out the zombie child。

So that's what I mean that from a programmer's perspective。

 this is only an issue of the parent were something like a server where it wasn't going to run where it could run for an indefinite amount of time and could create a bunch of children that don't get reaped。

Just to show you an example of a sort of similar idea is here's one where the child has an infinite loop。

And the parent exits immediately。So it's sort of the flip of the two from before。And you'll see that。

I actually。Don't have to put the ampers sand on this one because the parent is going to return immediately。

 exits immediately back to the shell。But if I do a PS。

 I'll see that there's still a forks process and it has a process ID 6676， which is the child。

So the point is that this child is going to keep running。And it's not a zombie， it's an active。

Program doing just spinning in a loop， doing nothing useful， but it's still executing。

And that will run again， potentially forever unless somebody kills it。

And the way to do that again would be， for example， to use explicit killil command to the show。

So you see that the idea of a zombie only happens when a child。Exitts。

 but is not reaped by its parent。If the child runs forever， then even if the parent exits， it will。

That child will continue right。So。I don't know if we really talked about the weight function。

 I guess。But the。I of a function weight， which I guess we've mentioned sort of tangentially a couple times now。

 is for a parent to basically hang up and wait until one of its children has completed。

One of its children is terminated and so this form of it will wait if it's forked。20 children。

 than any one of those will cause it to return from this function。

So wait's the first example we've seen of basically what you've seen in other places where basically the program is just going to hang up or hang there and wait until something happens。

And the way that's actually implemented is it's by this。Sis call mechanism that。That。

When the it calls weight。The program will just basically willingly suspend itself until the operating system don't do anything with me until something interesting happens。

And then when later the child completes that will and the operating system is dealing with the fact that child is called its exit process exit function。

 then it will recognize， oh， there is somebody waiting for this and it will return back to the program that the parent that's waiting。

So in the meantime， it could do various so you can call weight and。

The operating system could go off and run any number of different processes before it returns。

And you can get various information， the status information about the child in this。

And so this shows an example of a program that。Explicitly weight。

The parent explicitly waits for its child to exit before it continues。

And you can see that we use this graph representation to show this idea of these edges become constraints that the parent program will not continue past this point until the child is completed。

And so this is， again， one way you can see that it controls the concurrency。

 the kind of possible executions this program could have。That it's impossible for the program to。

Print by。Here。Without having previously printed HC， the hello from the child。

Wight will only continue past this point once the child is executed。In general。

As this example would demonstrate that the waiting when you say wait it doesn't presuppose any particular order in which processes will complete so they can happen in any order and so this example shows and this is actually。

No this。This code is okay。We'll look at similar but buggy code later that when you wait。

 this example shows a firing up n different。processes where I think and it's actually five in the program。

It will fire five different children than parent will。

 and then it will wait for them in a loop one after the other。

 but the point is they don't all have to return in the order they were created。On the other hand。

 there's another version of weight called weight Pi where you can actually specify which process ID you're waiting for and by that way you can force it to。

Follow this in a very specific order。There's not a whole lot of applications for that。

 but it's an available possibility。So that's the sort of key ideas behind。

The idea of forking waiting and now there's another interesting function called which goes under the various name of exec there's different versions of this this is the most general it's the way that a new process once a process has been created it's told to execute a specific program so exec is sort of like a high level way of saying execute this program。

Using these command line arguments。So it's given the file name。Technically。

 the path name of a file that contains executable code。And it's given just like you've seen。

For the main function， it's given the list of arguments that this program is supposed to execute on。

 and then it's also given a third list。Basically array of the values of the current set of environment variables for this process。

And you've seen examples of environment variables， for example， the one path。

 uppercase path determines the order in which the operating system chooses。

How to find a program if you just type in the name of a program。

And there's a bunch of other environment variables out there。

 so the point is that every process as it begins can access and determine what is its information about the operating environments that's encoded in these variables。

So in general， file name is the name of a program and that can either be a binary executable file or it can be some type of script if you've ever looked at the beginning of a script。

 say in shell script or Python or pearl or any of those languages that support scripting。

 you'll see it begins with a pound sign， exclamation mark and then the。Path name。

 the location of the interpreter like Python Perl。Bash or whatever scripting interpreter exists for that。

And so again， that can。That's how you can sort of set up a script and have it executable。

By telling what interpreter to use for。And then you know about the idea of ArgV as being an array of strings。

 and by convention it's supposed to be set up with the first string being the name of the file。

And then the list of environments is similar to the ArgVist， it's a list of。Except that it has the。

 it's actually a list of， it's like a keyword value pairs。

I'll show you this with some concrete examples。But the interesting thing about Exec V is exec is it's another one of these functions that has a strange calling that normally it gets called once and it never returns。

Because the idea of it is I've created a process。By fork。 and it's now a copy of。The parent。

What I really want it to do is execute some completely unrelated program and terminate。

 And so what happens is at the top level you call exec。

And that will load up and begin execution of this new program。And then if everything's going fine。

 it will never return back to this point again。It will just exit what it calls its exit。

The only time it returns is， for example， if the file name is not a valid program。

 it will return with an error code。So this is a picture sort of illustrates the。How的。

This information is all stored。In memory so that。The list。Of arguments。

Is encoded as a nu terminated list of。Strings。And the list of。啊， actually。

Strings meaning pointers to。Each of these is really a pointer to an array of characters。

 it's not the characters themselves。And same with the environment as a nu terminated list of environment values。

 each of which is a string giving the name of the environment variable and its value。And then， the。啊。

And what it will do is then。Excus me。So this is an example of calling。Setting up a call to exec。

And what I want it to do is call the LS operation。On some with some command line arguments。So LS。

 as you know， is a command within the shell that you can use to list files， LS， RM， MV， all those。

There's actually for every one of those。Command， so it's actually an executable file that implements that command。

 and it's generally in the directory， slash bin， slash， whatever the name of that command is。

So by saying I want to execute the program that's stored in slash bin slash LS。

That's just the way of saying I want to。Called the LS Command。So what you do is you'd set up a。

I said， if you wanted to do this call'd。You'd set up an array of four pointers。

 the first which points to the this name slash bin slash ElS the next。

To and then to the command wide arguments。 And then the final one is a null pointer。In some way。

 there's already an existing set of environment。Values that's maintained by the operating system。

 you don't have to create that yourself。And then you'd call the execec using these various。Arguments。

And if it returns， it's actually a sign that something went wrong。But normally it doesn't return。

So that and we'll come back to that now， so that was the sort of tail end of the lecture from last time。

 let me move forward with the material for this time。



![](img/4e269ed3f846ba40c9b38218551b0ec9_3.png)

Any questions up to now。哎。

![](img/4e269ed3f846ba40c9b38218551b0ec9_5.png)

![](img/4e269ed3f846ba40c9b38218551b0ec9_6.png)

Yeah我朋没到。

![](img/4e269ed3f846ba40c9b38218551b0ec9_8.png)

。So like， what's one of the。哦。So the question was， why is in this example here is doing this test is the P equal to zero？

Because and we'll show this is sort of a little snippet in a bigger context that we'll see shortly。

But what's happened is the parent has once。The parent for some reason wants to run a new program。

Which Norway wouldn't be to just list files， but。It basically wants to fire up something and do something with that information。

And so the parent calls fork。 and now that it's got two processes。

 one of which is the original parent， and another is its exact clone as the child。

 And so I really want the child to do this， execute this new program。 The parent。

 if it were to call exact would sort of。Call exec and never return and so it sort of moves its flow of control。

This will make more sense。Just shortly when I sell why a context where you call exec。

So this is the example from before。So。And remember we're starting now the non material for today。

 so it looks like there's sort of this introductory part so last time we talked about this idea of exceptional control flow。

And we talked about this sort of idea of at some very high level how these ideas of processes are maintained by the operating system。

And what we'll look at today is what are called signals。

 which are ways that you as a programmer can sort of create and handle some of these exceptional events。

 So it's like a software interface to this mechanism that process that's used to control the。

Execution of processes by the operating system。And then there's a whole other section non local jumps。

 which theres slides at the very end of this。啊。Lecture that we won't have time to get into and they're covered in the book。

 but they're a little bit less sort of central to the discussion so we won't try and talk about them。

 but there's some pretty good uses of these non local jumps I think I mentioned mentioned at to last time it's a little。

If you programmed in Python， Java， even C++， all those have some kind of exception handling mechanism where you can try something and if something goes wrong or there's an unusual event。

 you can say handle it this way， come back to this point and handle it。

That's not really built into C， but there's a system library with these functions called set jump and Long jump。

That allow you to get a sort of very primitive version of exception here。So。

As we said at the beginning on exceptional control flow， that theres some exceptions are synchronous。

 meaning that they're part of the executing program and some that are asynchronous。

 meaning that they're caused by the external activities in the system。And signals are。

A way for users to handle some of these asynchronous events。

So the way we're going to talk about it is with the idea of a shell。

 so I mentioned the shell is sort of the command line interpreter that you have when you're logged into a machine using a command line interface。

And。A shell is really itself a program that will fire up new processes every time it's given some command line to execute。

 and it will manage those processes in various ways。So when you log in。

 then you're given a shell and every time you ask it to do something， it will create a child。

And to execute that code and potentially that child will create more processes so you get this whole tree of processes going and if the system has multiple users logged into it。

 it will have each of them will be running their own shell and each of those shells in turn will have its children。

So。The whole system of processes then sort of has this tree like structure because some of these shells can correspond to different users。

 or if you log in twice to a machine like through two different SSH connections， you yourself。

 of course， sort of have the appearance of two different users as well。

And then there's some other processes that run in the background in a system that are known as demons and demons are just ones that sort of sit there quietly handling things in the background for you。

 so for example， HTTBD is a web server if your system is running hosting a web page。

 the other there's ones that even for your laptops and things are managing network connections。

 for example on your behalf。So that's the idea that this idea of for Can children naturally gives you this tree like hierarchy of processes。

So Ash shell is， as I mentioned， sort of a command line interpreter。

 but it's also just a program and it implements its actions by executing other programs。

The original shell was just called SH。Ones that were sort of。

Made a little bit more fancy seashell and T seahell， and then one called Dash。

 which is the one that's sort of the default when you're running Linux and you've probably heard this。

Some people get very emotional about which shell are you using in things？

I don't pay much attention there。But you'll see in the book and we'll cover a little bit of glimpse of the code and actually you're going to write your own shell starting Friday morning early if you get the assignment downloading fast。

 so your next coming assignment is pretty related to this。

And it will partly help you better understand all this business about signals and processes and stuff。

And also better understand what the operating system is really doing when you ask it to do things。So。

As I mentioned， this simple shell is available as a program。Online linked to this。

The web page for this lecture。And it's really simple。

 It doesn't do a lot of the nice stuff shells do。 So basically， you just start it。

Just like any other program， but now you'll see the single right arrows are the prompts being given by this shell that's executing as sort of a subprocess of your login shell。

And you can give it the name of a program， it doesn't understand the sort of short version of arguments。

 you have to give the full path name of the file that implements each of the standard functions。

 but if you say， for example， s bin/PS we'll execute the PS command。And I can do a little。

 it handles a little bit of job control， for example。

 running some jobs in the background and others in the foreground。

 so I can tell it to sweep for 10 seconds。And if。In the background。

 and then if I within 10 seconds say， tell me the processes running。

You'll see that it will list sleep as one of the currently active processesthe。

The only built in command it understands。He's quit。Otherwise， you have to give these。Basically。

 it treats everything you type as the name of a file and some arguments that you're passing to。

So I'm going to just show little pieces of the code for this to highlight some of the most important features。

 but like I said， this is not that much code and you're going to want to go and look at it and you're certainly going to want to understand it for your upcoming assignment。

But the basic idea is it's just in an infinite loop， well， a loop that potentially loops forever。

 where it prints prompt to the command line。Then it waits until you type something in and it reads that in with FGS。

And then it checks to say if it received an end to file， then you want to exit。

 otherwise you want to evaluate this command line。And once it's done evaluating that command line。

 it will jump around and do the next， so it's a standard interpreter that you read something。

 you do something with it。And so let me just go through pieces of this。

 so the interesting function is this one called Eve， and let me just step through parts of it。啊。

So there is some parsing that takes this。Command vine。

 and it breaks it into these separate fields to form the ArgV。

An AV will be an array of characters that will basically be formed by breaking up the command line。

 and the simplest way to do that basically is to replace all the spaces with nulls。

 and now you have all these command line， the command line is now broken into a series of separate strings and I just have to create pointers to the starting places of those strings。

So I won't show the code for that， but you can imagine it's pretty easy to do。

If it determines that this line is empty， it just ignores it。And then it checks。

 is this a built in command， and as I mentioned， the only one that's supported is quit。

And this function， which I'm not going to show because it's not very interesting。

 if it determines it's quit， it just exits the shell。Otherwise。

What it's going to do and this is where life gets interesting and it relates to the question you were asking before。

 is now you'll see that what it wants to do is create a new process， its's child。

 and the the purpose of that process is to execute the file that this command line is telling it to。

So it'll call fork。And just like what we said before it， we'll call Exec VE on this set of arguments。

We're using arg v of zero as the name of the file to execute。

And the environment is a global variable that。En codedes the environment variable information。

That you can anyone can us that。Go不非个。If it returns。

 it's a sign that somehow this was not a valid command and so it prints it。

The air handling here is rather primitive， it just says。Oh。

 that's an error and it just exits the whole shell， which normally is not a good idea。

you're starting to write programs now that do more than just some little thing and so if there's an error。

 what really you should do is probably go back to the command line。But， it doesn't。

But this is an example of exact V E， if it returns。

 it's a that something wrong because normally this would never return。So this turn it completes。

 you see how the shell program my interpreter。Created a copy of it Sopha Fork。

And that copy now sort of takes on the role of executing this particular command。

And then that's all it does， it exits out。But now we have this choice of is this going to be a foreground or a background process。

 so a foreground is the default but a background if you put an ampersand at the end of the command line and you're saying I want to execute this command。

 but I don't want to wait until it's done， I want you the shell to come back and be able to do more commands。

So it says if it's a foreground process， meaning it's supposed to weight。

 you'll see that it does a weight pit。On the process ID that have just created the forked process。

And。Presumably that will have an error， so this is the way that now the shell is going to wait for as long as it takes for the child to complete and then return back。

But if it's not， if it's a background process， then you'll see that it just prints out information about the process it created。

Like I showed you in a previous example， and then it returns back from a vow。

 And by returning back now it tells the。This main command loop。AnIner to so okay。

 now execute retrieve the next command to the shell and execute。

So that's how it's kind of interesting， how simple it is。

 the idea of how you maintain a background process versus a foreground process。

So that kind of gives you the very rough idea of what a shell is supposed to do。

There's a problem though， there's a problem with this code。That has to do with zombies。🤧咳。

And for foreground jobs it does fine because it will you call weightP， and when weightP。

 the part of what weightP does is the child terminates and weightP make sure that child gets reaped so it's no longer a zombie。

The problem is if it was a background process。The shell just。

Marchches on and doesn't pay any attention to it， so even when the background process completes。

 it will never get reaped and a shell is an example of a program that in principle can run indefinitely。

 and so if it keeps happening over and over again， it can accumulate this whole bunch of zombies。

So how we handle that well， as you could imagine， there's some mechanisms for handling these kind of events that。

As well as a number of other possible outcomes using a mechanism called signals， so as I said。

 signals are the way that your software， your user programs can sort of generate and。

Handle sort of events。Between exceptional events between processes。

So let's talk about signals and signals is actually this is what I'm showing you with the shell example is one use of signals。

 but there's multiple others as well。So a signal， and it's a little bit funky some of the details of signals。

 meaning if I were designing an ideal mechanism for communicating between processes。

 I don't think I would have come up with this one。But it's what it is。

 it's a standard that was created for eunuchs years ago， and it still exists today。

So a signal is actually something that one process requests。To deliver a signal to another process。

 but it's all managed by the operating system。 And there's different types of signals。

 There's a small range of integers that identify possible signal types。And the only thing that。

The receiving process knows is that it got a signal of a certain ID， doesn't know where it came from。

 there's no extra information with it。And so as I mentioned。

 there's sort of a range of 30 different signals and you can find that list in various places。

 including the book。The ones that are sort of the most。啊。The ones we'll talk about today。

Is called Sig int， meaning Sig interrupt。 And that's what happens if you're running a program and you hit control C。

You're basically towing the program。した。Don't， you know， stop forever， terminate。And so。

That's the way that's implemented as a mechanism is actually that the。When you hit control C。

 the shell is going to deliver。Is asking to deliver a s int signal to the running process？

Then there's another one called Sig kill， which is when you saw me using the kill command on the command line。

 that's sending the S kill signal， which is up。Sort of more powerful than an interrupt。

You've also seen ones like segment violation and some of those are illegal instructions。

 Those are all signals as well。And then there's one called Sig childil。

 which is sent when the child sends that signal to its parent when the child terminates and we're going to use that as a way of handling these zombie children in the shell。

The other thing you'll see is that for each signal type， there is some default action。

 meaning if there's no other overriding information。How a process will handle it。

 and you'll see that a lot of them， what it will do is just terminate the process。好。The， the sick。

Child signal actually is its default is to just be ignored。

 the parent won't react at all if it hasn't set up some special way of handling this signal。

So there's。Different options of。Default options， terminating， ignoring or suspending。

 meaning like when you hit control Z。You're stopping the executing program。

 but in a way that it can resume it later， as opposed to control C where you're stopping it forever。

So just some terminology， we say that the kernel is actually the one that does the work of signals。

And it delivers the signal to a destination by basically setting a bit in some field that says。

 you have a signal of this type。啊。And so signals can happen in various ways。

 one is if there's some system event。啊。Or one process has basically asked the。The another the。

Operating system to deliver a signal and there's this very misleading function and actually command called kill。

Which normally， if you say kill， it means send a s int。

But you can actually use kill to send any signal type to any process。

So just to sort of show this idea， it gets pretty involved here with some notation and conventions here。

But if a process wants to。A wants to send some type of signal to C。This is actually done。

 the operating system does it。So the process A says，S a signal of this type to process C。

It by using the function called kill， and now C has basically a little set ofbuoyan flags。

That you can see the idea of there being 30 different signals。

It has a bit vector corresponding to an int 32 bit word。

That is set to one if there's a signal of that type pending for this process and zero if there isn't。

So the idea of sending a signal， what happens is the operating system just sets the one bit field for that particular signal number for this particular process。

Meanwhile， C can maintain a mask， a similar mask that lists which signals it's willing to accept。

Or conversely which ones are blocked， so if this flag is set to one。

 it means even if a signal of this type arrives， I'm not going to pay attention to it。But if it does。

 if this is set to zero and that signal is set， then eventually the operating system will。Well。

Ca that signal to be delivered which will basically mean wake up this process and have a handle this signal。

This will make a little more sense as we kind of wade into this more。And this model， by the way。

 of thinking it as one bit flags， turns out to be important。Because if say process A and B。

 send the same signal to C。Before it gets handled by C， it won't cu them up， it won't say。

 oh you've got two signals pending， it just says you have a signal pending。

 so that's one of the weird things that has implications from a programming perspective of signal。

But eventually， then imagine this signal got set for C。And then process C now。Responds to that。

And when it responds， something's going to happen。And as I mentioned。

One of the possibilities is it will' ignore it。So even though that signal was delivered。

 nothing happens， another will be to just terminate this process。

 and a third is to execute a signal handler， which is a special piece of code that you as a programmer can set up so that it will handle particular types of signals for this process。

And this is where it gets interesting that you as a programmer， can write signal handlers that tell。

The operating system， how to handle different types of signals that might be arriving into your program。

So the idea of it is。The process is running along， doing whatever it's doing。

And the operating system。For one reason or another just decides， well。

 I'm going to tell it to run its signal hand and so it will jump over。

And start executing the program that or the code that's provided in this handler。

 and the handler might exit the whole program， but if it doesn't， if it just does a normal return。

 it will go back and resume execution of the original program。

So the interesting thing about signal handlers， though， I it still considered the same process。

That was executing before。So I'll get into that in a minute。So as I mentioned。

 this idea of at any given time， there can be some number of signals that are pending for a process meaning it's been delivered but not yet received。

 and so those are the ones for which this little bit fields are set。And as I mentioned before。

 it's important to realize that。They're just going to one bit field so if。

There's multiple signals that get sent before they can be handled， they don't queue up。

And as I mentioned before， it's possible to block certain signals as well。So and in general。

 then the kernel for each process is maintaining these two bit fields。

 one is the set of pending signals and the other is the set of block signal。啊。And then。

So how are signals sent， it's actually possible to send a signal to pre。

Specific process or to a whole collection of processes。

And the idea of a collection of processes is that every process is part of a process group。

And typically， when you're running as a user logged into a shell。

 your shell and every process that spawns is part of a single process group。And so， there's。

For every processor there's an associated process ID PI， and a process group ID， the PGI。

Which is usually the process group ID is the。The PI， the process ID for the sort of highest。

A note in this tree for this process group。And you can basically you can change the process group of your program with a function called SEPGID。

嗯。So if you say。呃。TheThe kill command， as I said， the default。

 when you give a kill command is you give a。You just say kill and you give a process ID。

But the more sort of exotic version of kill is if you give a negative number as the first argument。

 then that's actually the signal number， the signal type。

So you remember from the table before that signal type nine is a SG kill。Right。

So you can say basically deliver a signal type。9ine。To something。 And if similar。

 if I give a negative number for the process this negative number here。

 I'm saying deliver this signal to every process in the entire group，2，4，8，1，7。So in this case。

 I set it up so in this example and you can look at the code。

 it had two processes in a group and the group ID was 24817， so by saying kill minus9 minus24817。

 it will kill both of these processes here so this example showing a couple things。

 one is you can specifically identify what signal you want to deliver。

And you can deliver it to either a single process or to a group of processes。And so in general。

 as you know， if you try control C， it will terminate whatever your're。

The program is running in the foreground。And the way it happens is it the。

You're have the colonel send the Sin signal to every job that is in the foreground process group。

Including its children， possibly in other words。And there's a similar if you do control Z。

 that's called the SIig stop。And you can test this out if you run this， it'll set up。Some。

A process group with two running processes。If you type control Z and you say， what's the status？

You'll see that and you use argument W， which as it give a little more information。

And it will tell you these two processes are stopped。And now if I。嗯。嗯。Okay， so I did forks。

 I typed control Z that put these in the I stopped these processes。

And now if I say foreground and I type control C， then it will terminate those two processes。

So the point being the control C terminates not just the process that's directly running。

 but if it's fun children， those will be terminated as well。Okay， so as I mentioned this kill。

 so now kill is more than just the ability to kill other programs。

 it's actually a way to deliver signals of any type。By the way。

 if you tried to kill some of your friends program， you'll find it won't work。

You can try to deliver that signal， but the operating system might not like you。

So here's an example of some code that fires off a bunch of children or all of which just go into an infinite loop。

And what I'll do then is I will kill them， meaning I'll call the kill function on their process ID。啊。

Where the type of signal I'm sending is S hint。And then I can。

Go through another loop that will then wait for those all to。And。

What it will find is since these have already been killed。That they'll all come back saying， oh。

 it was already terminated abnormal。So general， with weight。

 there's various ways you can look at the status information and determine something about the nature of that child and how it terminated。

嗯。So signals are。It's important to recognize that signals are a way to。

Handle we've talked about this idea of the kernel， and so the kernel part of the is the operating systems code that is used to manage processes。

But when the kernel runs， it's not considered a process of its own。

 instead what happens is as one process causes something that would cause the kernel to fire up。

 for example， it makes a cis call or gets interrupted by some external event。

 then the program will shift into kernel mode， which means that it has various privileges to access data structures and do things that you as a normal user can't do。

But at some point， if it's going to do a context switch， what it will do is transition。

 it will store away whatever state it needs about process Q。And load up from somewhere in its memory。

 information about process P。And then when it's got that all loaded。

 then it will begin executing the user code。 So that's the normal context switch is going between process Q and process P。

好。So this is the point also at which it's going to handle any appending signals。

So now what it's going to do is look at process P as it。Begins to get ready to fire it up。

 and it's going to say， hey， are there any pending signals for a process P？

And it will do that by looking at this sort of combination。

 are there any signals that are pending that are not blocked？And then for each of those。

So if none of those， there are no pending signals， then it will just begin executing the regular code for process Q。

But if there are some pending signals。Unblock pending signals。

 what it will do is start to process each of those in priority order。

 starting from the lowest number to the highest。And it will deliver。

 it will force that process to receive those signals。And if there。

If there's no signal handler for that particular one。

 then it will do whatever the default action is for that signal。But if there is a signal handler。

 then it will invoke that signal handler。So this is the way。That。Ting to。It's a nice picture。

So see here。Well， we're going to come to a nice picture。But the point being that。When it executes。

Process P， when it resumes execution of process P， it might。It will if there's any pending signals。

 unblocked signals， it will do those first before it executes the normal user code。

And that's how signals are implemented。In a very simplistic way。

 so the idea being that your program's running long perfectly happy doing over what it does。

 and one of these signals sort of appears to magically come out of from outer space that the operating system is taking control of your program and either doing a default action for that signal。

 which possibly means terminating the program。Or it's invoking a signal hand lawyer that's sitting there is some code that's within your program that you've put in there。

And then as those signal handlers return。And nothing else happens。

 eventually it'll come back to your regular coat。So there's a function called signal that you use to say。

 I've got some code called the handler， and I want you to use it to handle this particular signal number。

 which you give us an argument。And。There's sort of predefined constants for the corresponding to the possible default actions you can do。

Or it's the address of function。So let's show a simple example that you might have encountered in the bombwe。

So if you tried it in the bomb lab to hit control C。

 you might have seen this kind of creepy thing come out。That it said。You know。

 printed this threatening message from Dr。 El。But then if you were patient， it would actually exit。

And so that was implemented as a signal handr， and this by the way。

 will show why this is not really a totally legitimate code。But let's set that aside very briefly。So。

 but this is sort of a version of what the program did。

 it so what happened then is you type control C。But I'd already。

 before beginning your the part of the program you saw， I'd installed a signal hand for Sig int。

Which is this function。So when you type control C， the operating system delivered the Sig int signal to this program。

 but rather than the normal thing which just terminates the code， it invokeked this handler。

And the handware then printed out this message， used sleep to sort of pause for two seconds。

And but then eventually it called exit， and so it exited your program。

 which is what you wanted to do。So that's an example。 And by the way。

 you can look at the code for the。Several of the labs we've done and we've got signal handlers sitting all over the place。

 handling when it came back said， oh， you caused segmentation fault or oh。

 you did something wrong or oh， this code took too long to execute。

 those were all implemented as signal handlers。So oh this is the slide I wanted to show。

An important thing to recognize is we talked before about this idea of concurrency。

 meaning that you're interleaving the execution of multiple functions。

But the main point is that the handler is considered part of the same process。

 it's not a separate process to handle a signal。And so it has access to all the same global variables and stuff that the main program does。

And so， what's happening is。The it's a similar idea to a。A context switch。

 So here's an example where a switches to B。 And now， as B comes back to a。

It sees that there's an unbed pending signal and it executes the handler code for it。

 and when the handler returns， it returns back to the kernel and potentially then it will just resume back the original program。

So it's possible for signals to interrupt。So one signal can interrupt another handr。

So it will get this sort of nested thing， but it's important to recognize that。Once a signal happens。

It either returns or it calls exit to the program， there's not much it can do as far as changing the control flow。

And possibly this is why the idea of blocking is is maybe this handler didn't want any other signals to get be able to interrupt it so this handler can to block signals and in fact what happens is every time a signal gets invoke a handler it automatically blocks that particular signal type so you can't get a sort of。

Unbounded loop of。Of hand raised being called， the same hand raised being called。

And there's a kind of clunky way that you can set up these and specify which signals are blocked。

 there's a instead of having you specifically。Changing these bit vectors， there's an API for。Oh。

Where you can create an empty set。Of blocking of blocks， meaning don't block any signals。

 you can block all signals by sealing that set or you can add specific signal numbers to the set。

 or you can delete specific signal numbers from the set。

So these are all functions with various ampersands and arguments and stuff like that that you can use。

But the idea of it is you can create and manipulate these sets of blocks。So here's an example。

OfI want to block Sig int。So I'll first create an empty， so I have to declare two SG set teas。

 which are whatever data structure it uses to。Represent these。

And you don't need to know the details of how they're represented。

 but you can say create an empty mask， a mask where nothing is blocked， and then just add to it。

 the signal for signigint， the bit for signin。And then there's a function called。Sig proc mask。

 meaning change the signal proc mask for the set of box signals。

And the idea is you pass in a pointer to the。New set of signals。

And you can also pass in a pointer that will then be set to previous the existing set of box signals。

And so right now I'm running this code will just be blocking only Sig int。And if at some later point。

 I want to unblock that ci， what I'll do is I will say， okay。

 return back to whatever signals were blocked before。

Resume back to what they are and that's typical of what you do that you want to sort of write your code that assumes that there's potentially some set of signals being blocked。

 I want to change that behavior， but then when I'm done I want to resume back to the way things were before。

So。Writing signal hand wordss has a lot of caveats to it。

And some of the worst issues have to do with that there's。And so here's some guidelines。

Thought that you'll have to follow。嗯。One is you want signal handler need to be very simple if they try to do too much。

 they should be sort of they're designed to be just a very short piece of code to handle whatever that signal is and move on。

 They shouldn't be long lived， they shouldn't。Tverses through some big data structure or anything like that。

The other is that there's some only a very limited set of functions that you're allowed to call in a signal hand。

 and it has to do with some very awkward interactions between the support for threading and signals so threading is a way we'll talk later in the term that you can also create concurrent activities within within a single process。

 Signs are a way to communicate between processes and create concurrent events and that have some really bad interactions for some functions。

We'll talk more later in the term about what those bad interactions are。

 But the bottom line is a lot of functions that you'd like to call， including printf。

Or in Sprintf are not considered safe ones， so that code I showed you before is actually not good。

The other is that there is a global variable called ErRno。

 which is the ID that's used to pass some information if an error occurs in a system call。

 and you're supposed to basically save that when you start the signal handler and restore it back because remember any global variable that the signal handler accesses and changes will be permanently modified when the signal handler returns。

You have to worry about blocking signals if there's。

Potential for causing sort of race conditions or bad behavior between multiple signal handlers。

And in general， if you use global variables， you should declare them as being volatile。

 volatile is just a way to tell the compiler that this， when I give this global variable。

 I want it to really be in my program， don't try to optimize it away。

And potentially you need to also declare them to be of typey sIig atomic T。

 which has to do with how the program is allowed to actually modify these values。啊。

And so this's actually really a nuisance when you write signal hand。

 there's a lot of stuff you want to do that you can't do。So in the book。

 they give a very small library of output functions to sort of replace printdf that can print a string along or some error message。

And so the proper way to。Imple this。Signal at hand where I showed you for the bomb is to use these special versions of print routines that don't call print of。

And also， it turns out you're not supposed to call the regular exit function you're supposed to call one called Tsp exit。

Don't ask me why I don't know that one。好吗。Okay。Now。

 here's another annoying feature about signals that's demonstrated by this example。

 So the idea of this example。Is I've got a loop that's going to fork off N children。

And the child is just going to。Sweep for a second and then exit。 So not much goes on， but you see。

 this is a way to。Potentially create zombies。And so the idea of this is I'm going to use a signal hand。

As these children exit， they will send Sig child signals to their parent and the parent's going to receive those and know that。

 okay， I can reap this， I can make sure this child gets reaped by calling wait。啊。

And so the general idea of it is that there's this signal handler that's associated with the signal Sig childild。

And each time it。Gets invoked。 It will wait for a process that presumably。And it will in the process。

 then it will decrement this global counter。And then my main program will just sit there apparently in an infinite loop。

 but what's really happening is as this parent sits in this infinite loop。

This child will be invoked for as many children as exit。

And eventually that count will go to zero and I'll be done。So that looks like it should work。

But there's a problem with it。And the problem is this business that signals don't queue up。

So if this， if multiple children exit。And deliver their sick child to the parent。

Before that signal handw gets fired up。This hand is only going to wait for one of them and reap one of them。

 and the rest of them won't。And what will happen is this program will potentially hang forever。

Because this count will never go to zero。 it only goes to zero once。Per call of the child handlewear。

 but that child handlewear might。Be getting called because there's been multiple children of accidents。

 So it's this problem of。Not queuing of just a single one。

And so the cracked way to handle it is to write a loop within the child handler。

That calls weight over and over again until it gets a。Yeah， a value less than or equal to 0。

 which is the way that。Odating system basically tells the hand， hey， there's no children。

That need to be reaped at this point， so give it up。

And so you'll see that potentially this child handler might just reap one child or it might reap the whole set of them or any combination of those。

And do that。And so this is an example then of how that handler could be used in my shell。

 so going back to the original example， remember that the idea of it I had the shell。

 but it could create background processes and background that the background processes didn't have any way of getting reaped and so this handler here is an example of some code that handles that problem and it's the same idea that we've just seen it weight pi if you give it a minus1。

 it's the same as weight for anything。But it's being a little bit more careful's using。

Because there's some other data structure around there。That's。

That the shell is using to maintain the set of jobs。

 and it wants to remove this process ID from that set of jobs。

And wants to make sure that some other signal coming in doesn't mess up that data structure。

 So by blocking all signals while I'm doing this delete job。

 it's a way to make sure that no other signal handware is going to get fired up that potentially。啊。

Does anything with the same data structures that are here。

So the idea in signal handlers is he's blocking his way to prevent。啊。

Other signal hand raiseds from getting caught。So this example just keeps going on。And so this is。

 you know， I could talk for three lectures on this。

 but you can see you're going to have to read the book on this。

And I would apologize for that and but you will read the book about this because this is going to be your upcoming layout。

 so you'll really get to know this。This is an interesting example of the same general idea of a shell。

 but it's got a kind of subtle。啊。And it's doing the same idea of creating a。

Wanting to start a bunch of children。Each of which is going to run some program。And。It will。And exec。

 this is sort of， remember exec will not return normally so the children just disappear off after they've done this。

 but now the parent you see it will block all signals and add to the list of processes this particular process。

So the idea is I forked off a child， I executed some other program。

And then I made sure that I added this program to the list of。

Of jobs that I'm actively monitoring and then later that handler that we showed before。Well。

When that process completes， then we'll delete this job， and you see I'm using this。

 I'm blocking signals as a way to make sure that I'm not trying to add and delete a job at the same time。

But there's a problem with this program。And the problem is that the。

It sort of assumes that the parent is able to add this job， block and unblock the signals before the。

The child executes and completes。 But remember， as I've talked about before。

 there's no guarantee which goes first， the parent or of the child。 So potentially。

 the child could run through this。Execute this program， finish。And do all that before。

I've had a chance to even add it as to my list of jobs。

So the basic idea is the correct way to handle this is to block SG child。Before you call fork。

And then block all of them， add the job， and then go back and unblock everything。

So and then within the child it has to unblock some of these two。

 so this use of blocking as a way to control what kind of events can happen is subtle and pretty tricky and pretty important。

Okay。I have run out of time。But you'll find some pretty interesting quiz pro。On Canva。

 and we will pick this up next time。

![](img/4e269ed3f846ba40c9b38218551b0ec9_10.png)

![](img/4e269ed3f846ba40c9b38218551b0ec9_11.png)

没有。やて。

![](img/4e269ed3f846ba40c9b38218551b0ec9_13.png)

。是关。

![](img/4e269ed3f846ba40c9b38218551b0ec9_15.png)

不可。我写话者借我。