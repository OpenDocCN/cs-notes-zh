# UCB《Linux系统管理实践课程｜UCB Linux System Administration Decal 2025》中英字幕（deepseek - P4：Lecture 4.zh_en - GPT中英字幕课程资源 - BV1wj59zGEMq

![](img/8d5c27104de75e31cff3b03677f048ef_0.png)

Okay， welcome to。Linux System Administration decal lecture 4。

Today we're going to be talking about processes and services。So just a quick introduction。

 if you weren't here last week， my name is Oliver， I'm one of the site managers of the OF。

I do I've been doing a lot of work on like my infrastructure our desktops。

 so one of the things you might have noticed is that we have a bunch of new desktops。

So those old county boys have been replaced with the。等你 were。Seaker looking one。

So that's one thing I've been mentioned recently。跟住系。I guess I。

I just like do a lot of OCF stuff so feel free to talk to me about things that have been happening in the OCF or if you want to get involved after lecture I'm glad to talk about that。



![](img/8d5c27104de75e31cff3b03677f048ef_2.png)

Okay， some quick Administria， vitamin three and lab three were due last week。

 but we do accept late labs， I think。I think we officially accept up to two late labs。

 fill out the late lab form if you need to， if you have extenuating circumstances and you need more than two late labs。

 just come talk to us， I'm sure we can figure something out。嗯。Lab four。

 which is on the content of this lecture。What be due this week？And yeah。

 use your resources as always， this is like the same slide that was up last week， though。啊。Again。

 I want to emphasize Google。com。You can find a lot of things yourself。

 I think so come talk to us feel free to talk to us like don't don't be afraid of。Ferness， okay。Okay。

 so today we're talking about processes。😊，In its systems。System D， O and services。

 I don't know why I skipped that one。Okay。So just a quick disclaimer before lecture。😊。

This lecture is mostly about like or this week is mostly about like system D and we want you to get familiar with like managing services and that's like a lot of the lab will be playing around with system D and like。

😡，Typing a bunch of commands and stuff this lecture。Is a little more。Like。

Toward like the like theoretical like。ceIt provides some more background on why we have like how processes work and why we have like in systems。

Just so， you know， like。Really like what you're like really what you're playing around with and how this。

Fits into like。嗯。How your computer works， yeah。Okay。So。嗯。Yeah， so in operating system。

 that's like what we're talking about right like Linux， which is like the kernel。

 but we have like all of the stuff around Linux and distributions like we talked about。😊，Last week。

 the goal is to like make an operating system right so what is the what are the goals of an operating system？

😡，So if you've taken CS162， these next three points will look very familiar to you but。Broadly。

 there's three goals so the first one is to be like a referee right we have a computer。

 we have many shared resources and we have like you know， you have one CPU。

You have like a certain amount of limited memory。But we want to be able to run like all sorts of stuff on here。

 right， so we want to manage access to our shared resources and we want to make sure that you know。

If I have like one workload。That's running like if I have two programs running that they can't like they don't mess with each other in like weird ways。

So that's like it isolates and protects workloads from each other。That's the referee portion。

The second。Broad goal is to be an illusionist。Right， again， you have like many， many processes。

 many programs running on the same computer。But。To each program。

 we want the program to feel like it has the whole machine， right？😡，啊。And。Basically， in other words。

 like providing abstractions of physical resources。So that way like。When you。

 if you write a program for an operating system， right。

 you know that no matter like what else is running on the system。😡，嗯。Your program will like behave。

You know the same way， so I guess that's like not entirely true I guess like。The idea。

 you don't want like unrelated things that you didn't want to mess with your program to like mess with your program。

And also we provide glue， which is like common interfaces to do。😡。

Useful things so this is mostly IO things that's like the file system the networking。

Window management， all of this， this is like these are APIs that the operating system provides that programs can hook into in order to。

To beautiful。And so how do we accomplish these goals， right？There's like there's many different。

 you know， there's like many different small things that all come together to accomplish these goals。

 but broadly the like most important step is like the process abstraction。So。嗯。😊，Yeah so。

What is the process abstraction？Basically as saying when we run user code。

 which is code that's like not a part of the kernel itself。

 user code must run in something called a process。😡。

And the process has like certain properties that is are enforced by the。

By the kernels so the process has like some there's some restrictions on the execution environment。

 right so。You know。At the end of the day， like whether it's user code or kernel code。

 it's all just like instructions being fed to the CPU right but CPUs have like they'll build things called like privilege levels in。

That the kernel can set so when the kernel like jumps to your user program it'll like set the privilege level on the CPU such that the user program can't execute like the dangerous CPU instructions that。

😡，Only the kernel wants to be able to to execute right so that's。

So another restriction is like it can only access what it owns， right？For example。

We'll get we'll get into memory on the next bullet point。

 but also like if I have one process open a couple files those open files are like local to that process only so another process can't。

😡，Like access the same open files it might be able to open the same file。😡，In its own process， but。

That's like。Like it guarantees that if you open a file。嗯。Well， like， yeah。Okay。要是件事啊。Basically。

 like other programs can't mess with。You know， what position is your？

Like cursor on in that file and et cetera， stuff like that。🤧嗯。One， okay， so on the second point。

 the illusionist point， one way of guaranteeing this is we do something called virtual memory。

So every process will get its own virtual address space that starts at where memory addresses will。

You know， start at like zero and end at like two to the power of like。Whatever。他。And。To the program。

 the program basically thinks it has like， I guess， like infinite memory， right？😡，嗯。And。

Like one of the key things about the virtual address space is that。😡。

Every process has its own virtual address space， so if you have like one memory address。

In one process。Another process might have something at that other at the same memory address， right。

 but because。😡，Even though these have the same memory address。嗯Because。

They like are in different processes， they will refer to like。

Different memory so like the operating system will like the kernelel will。

Do some things to pretend that each process has its own like infinite virtual address space。😡。

And lastly， like the glue are the IO APIs that we talked about such as files， such as sockets。😊，Many。

 many other things， right？And。Basically， each running program has its own process。😡，So that way。

 running programs can't really like interfere with each other。Does that make sense。

Yeah question yeah so is what your referring is user code like compartmentalized within within the journal I mean i'm just curious like what sorts what isolates code that's running inside of the current as opposed to code that's that's running outside and what are there。

How are they able to communicate？The code executed within the current。

It has to make contact with whatever referral processes。Yeah， that's a good question。

 So the the question for those on Zoom is about。I guess like。What is like the distinction between。

 what exactly is the distinction between like user code and kernel code？😡，And if like user code。

 you know， is restricted and it can only do things within its own like address space。

 how does user code interact with like peripherals and stuff like that， right？😡，嗯。So。呃。Yeah， so one。

Like one key thing to。To realize is that。From the point of like the CPU code is just like code。

 right， it's just like a stream of instructions。😡，嗯。

The thing that differentiates like kernel code from user code is like。

I guess that's like that's a distinction that is made like by the kernel itself， right？嗯。

Because the kernel is。Like when you boot a computer that like starts the kernel， right？And。

Like that initial code。嗯。Like because the kernel is the first thing that started when you boot a system。

😡，But that has like。Control over like what other like all of the other code that gets executed。

 right so。😡，呃。You'll see this。m like especially when we talk about like in it systems later right so when the kernel first boots up there like is no user code like everything is kernel code。

And the ability to run user programs on the computer is like a feature specifically programmed into the kernel so the kernel has a way。

😡，To。To make。Processes。And。嗯。😊，Basically because like。嗯。Yeah， I guess like the the only way to。

Control。Anything else is to use the process API there's no way to like run any other code besides。😡。

啊。The kernel code and like using processes right that's like a thing that's programmed。

 that's just how the kernel works。 so that ensures that like user code always gets executed in process。

嗯。What actually is user code？User code is like。Anything that's not in the kernel itself， right。

 so if I run like。Even like my like login screen。It's probably running in like user space and not like kernel space。

😡，The kernel only contains like the minimal amount of code that's necessary to like ensure that all of these processes can exist at the same time and like works。

And like switch between them and stuff like that。Sorry that was a little conut。

 does that answer your question or that I something？I don't know。

 I don't want to ask you to explain what the girl does on this slide。Yeah。

 it seems like it's like processing the request in order to。yeah， well， basically the whole。

 I mean actually like a one way to think about it like the whole reason the kernel exists is to manage these like user processes。

😡，Right。If user processes didn't really exist， it would be hard to have a very useful computer。嗯。

Because like user programs is how we tell the computer like what to do。O。

Just like a brief aside on threading。So。In addition to so like when we talk about multiple processes。

 it might be like。😡，This might sound。Like this might sound like a way to you know execute a bunch of code in parallel。

 right， which it is but。😡，I guess， like。We also have other tools for parallel execution besides processes right so many operating systems。

😡，Pretty much all modern operating systems will have some sort of way to make threads。

 which are sort of。😡，嗯。Different like lines of execution in the same process。So in one process。

 I might have one thread that's like on this part of the code and I might have another thread that's on another part of the code and like most modern operating systems provide。

Abstractions where。I can。From my point of view， it looks like all the threads are executing at the same time。

😡，So。Yeah， so threads。Really threads encapsulate like concurrency right like the whole purpose of threads is for concurrency。

 whereas processes are primarily for isolation and like being able to execute a bunch of processes in parallel is like sort of a side effect of。

😡，That。And like one consequence is that communication between processes is a lot harder than communication between threads a yes question yeah Id like creating some like code before or like I'm like automating stuff and like I' like achieve it by like making a bunch of like different like multi processes or whatever yeah like is there like anything bad about that。

You know， is there like like right like computer crash yeah。

 so the question was about likeum so the person who asked the question said they have like written。

Some code that created a bunch of processes and asked is there anything bad about creating a bunch of processes？

So no， so creating a bunch of processes isn't like a bad thing。As long as you like do it correctly。

 which like we'll talk about some。Pitfalls later。嗯。

Like the purpose of them existing is for you to like spawn more。I guess。As an alternative to threads。

 like maybe like another question is like is it better to use threads or to use processes？

This is like a pretty complicated question， and it depends a lot on the specifics of what you're like programming it's like one example is like in Python。

嗯。In Python， like a Python process can also have multiple threads。😡，阿不。

Because of restriction because of like limitations of the Python runtime。😡。

You don't get as much like parallelization with threads versus creating an entirely new Python process that's like one reason you might want to use processes instead sub threads。

I guess we're going to talk about creating processes in a moment。Oh。Okay。So yeah。

 TLDR a process of a single instance of a program。And they're isolated from each other。

And each process has its own memory， threads， et cetera。😊，And。

TheOS provides a lot of interfaces for processes to do IO。And I guess。Iio is like writing a disk。

 communicating a network， also communicating with other processes is also like a form of IO。Okay。😊。

Oh yeah， Colonel code doesn't run that。IO is like input and output。It's like kind of。

It seems like a very simple term， but it's like more overloaded than。Then you might think。

Basically like any time。Anytime like the user code。

Needs to like ask the colon to do something is like pretty much anytime。

That happens that's IO so like again， like reading from the file system。That's like。You know。

 that makes a lot of sense input and outputs like file system input output， but also like network。

Like spawning other processes， I don't know， maybe that's maybe that's not I own。啊。O。呃。

What about kernel code， So we touched upon this already so the kernel itself doesn't run in a process。

 so the kernel is like the thing that manages all the process。No。Okay。

 so now we've talked about this like sort of abstract processes thing。



![](img/8d5c27104de75e31cff3b03677f048ef_4.png)

But where do we actually get processes， like what creates processes， right？The answer is processes。



![](img/8d5c27104de75e31cff3b03677f048ef_6.png)

It turns out like the only way or I guess not necessarily the only way， but。

The main way that processes get created is from what's called like the four join model。嗯。

In Linux atally， so it's like other models of like how to spawn processes， but in Linux。

How processes get created is there's a special call that。One process can do called fork。

 and that basically just like creates a copy of the current process。

So it'll create a copy of the process， it'll be like running the same code， it'll have like。

Like if you did like if you stored some some data into a variable。😡，Before the fork， then like。

After the fourth， both copies。Both processes will still have that variable。嗯。But after the fork。

These two processes will continue their execution independently。So that's like kind of weird。

I don't know why it turned out like this。But。It's like， yeah。I don't know。

 I there's like some story that。I don't understand well enough to like talk about here。

 but some somehow or another we ended up with this like pork bottle right how do we actually get the spawn like the child process to do something。

😡，We can call this thing called exec and exec just like changes what program the current process is running so it just restarts your process running a different executable right？

😡，So。嗯。Yeah， so like a very common model is to fork and then in the parent process you like continue doing whatever you were doing before and in the child process you run you immediately run exec。

And then change to something else。嗯， yeah。啊。And then after the fork so。

The join part of the for joint pattern is that when the child exits。

 there's a way for like the parent process to see what the child process did。😡。

And like retrieve like what's called like the exit code， right？Oh。

But like the specifics of this for exact model， you don't really need to worry about the important consequence。

 Oh yeah， here's the。Here's the man page for Fork。And you can see like there's something so the child will。

Like most of the things stay the same between the parent and the child process。

 except like the child gets its own process ID。And the child gets its parent process ID set to the parent's process ID。

 right？😡，So the important consequence of this is that processes form basically a tree right so if I have like。

😡，Right。Like with this like parent child relationship right so if I have like a shell open。

So let's say add ba， right which is your normal like terminal command line。

 it's what you type commands in。And if I type the way thatsh actually works is if I type like。Hat。

And then a file。Bash will figure out what executable I'm referring to by cat and then it's going to fork an then Ex cat。

😡，2。So bash will spawn a child process cat and then。Like after cat is returned， so after cat is done。

 then bash will be notified and and then bash will like see that cat finish and like give you another place to type of command。

 right？So whenever you type， like whenever you spawn， like whenever you run cat or Vm or PS。

 those get spawned as like children of ba。And bash itself is also a child of something， right？😡。



![](img/8d5c27104de75e31cff3b03677f048ef_8.png)

But what is like Basha Childo， right？Oh。

![](img/8d5c27104de75e31cff3b03677f048ef_10.png)

Hey I'm sorry， clearly I do not know the order of my slides very well。

 but we will just roll with it okay。

![](img/8d5c27104de75e31cff3b03677f048ef_12.png)

Okay， so。Okay， so here's an example of a simple program that runs。Ok。

So we can see this is like some C code， you don't really need to understand like exactly how。

Exactly what like printf is but。嗯。This is just like a program that first runs fork and then it like prints out He low and then the process ID。

Yeah， if we run this code， how many head loads get printed？So。Okay， yeah， so the answer is to right。

 so when we fork it'll create a child process。😊，And it'll like the parent process is still there and both the child process and the parent process will print hello hello。

 but they will print like different PIDs。So。Here's our original process， let's say SPID 2000。

 when we run Fork。嗯。It'll fork。So the left one is actually just the original process。

 this is like the child process。Oh sorry， this is the parent process and then the process we have on the right is the child process and both of these will print hello。

Okay。So now we have this code it has three fors。This is like a little trick here。

I I don't want to figure out like。How many homos get printed？嗯。Okay。It is not 28。Someone else， okay。

 I think I heard earlier， somewhere， nine， not9。Yeah， it's eight。So。

At the start we have one process after the first fork。

 we're going to have two processes right we have the parent process and the child process。😡，🤧う。😊。

And then when we get to the second fork， the parent process will fork again。😊，Right， so you have。

The pair。Process， and then。The new， so。Yeah， so the parent process will workk again into like itself and another child process and then the child process right since it's a clone of the original process。

 it'll also get to the second fourth so the child process will work into the child process and the child child process。

So by that time， we'll after the second fourth， we'll have four。Processes。So every time you run fork。

 the number of processes gets multiplied by two。2 to the1，2 to 2，2 to the three。

 and 2 to the three is 8。 So it's going to print。Oh yeah， like whoever made this slide。

Actually compiled the Senate front， Senate Prince died。Okay。Has anyone seen this code before？Yeah。

 definitely like right for computer code。Yeah， so this code will crash your computer and how does it crash your computer well so it turns out that like this so this is a line of bash。

😊，It turns out that like colon is like a valid name for something in bash。

 so this actually what it's doing is it's defining a function called bomb。That。

Does bomb and then pipes itself into another bomb and then the an just means right in background。😡。

But the important part is that。When bomb runs， it'll spawn to more bomb instances right and the way bash bonds these is by forking processes right so it'll fork a process for。

Bom and then bomb again， so the number of processes is going to increase exponentially and。

You will like。Well， for one， it's going to like keep doing。

Every process is just going to keep spawning more and more processes。

So it'll like keep your CPU busy doing basically nothing。And eventually， also at some point。

 you'll run out of process ID numbers。O。Yeah， so just here's an example of making the child do something。

So this is like some code， we call fork and it turns out that a fork will return zero。😊，If。嗯。

It's the it。So。Fork like creates a copy of the process right。

 so inside fork it creates a copy of the process， but。After the fork。It will return。

A different value in the parent process and the child process and that's how we can tell which one it is。

So it'll return like zero in the child process and it will return sorry， yeah it will turn zero。

 work will return zero in the child process and it will return the the PID of the child process in the parent process。

So for example。This is just like a simple of statement saying。if fork。

So it checks whether we're in the parent process or in the child process and in the child process。

 it'll execute bash。By calling exec。Okay。But like again， you don't like this is not like a CS class。

 you don't need to understand how exactly this code works。This is just like。

An example of the fourth exec model。Okay。差不懂。floor or floor process floor。

So the so we did that as functions or。Yeah， so the question is like。

 is this a stack overflow or like？I'll process over flow like something else so this is like。嗯。😊。

This looks like a programming language， right？I guess one thing if you're if you've taken like CS classes before like done some programming。

 one thing you might know is that if you like have a recursive function that。

Never stopped like withcur says infinitely， you'll run into what's called a stack overflow。Ot。

That's actually not what's going to happen here。The reason it's like a stack overflow in most programming languages is has to do with like how。

Those programming languages like do function calls。But in bash， when you do。

When you do like this function code。嗯。Its the with the pipe it like actually it spawns new processes so like this is。

In this example， the function calls are implemented by 14。😡。

So I don't think you'll actually ever get a stack overflow because like each new process。

Will have like its own like new like stack and heap and whatever。嗯。But you will like。

Freuce your computer by having like a billion processes that do that are just like busy spawning new processes。

Yeah。And you might write out of。Process ID numbers。

 but I don't I think like your computer will freeze before you run out of process ID number。Okay。

 so let's do some exploration of process trees。

![](img/8d5c27104de75e31cff3b03677f048ef_14.png)

Just so you can see。Oh， what it looks to like a real host。Okay， so I'm going to SSation to supernova。

And。😊，So one useful command is called HT。And each top is just this like。

It's like a terminal program that。Shows us all the processes， right， Okay， so if I type H top。

 I can see all the processes that are running on the system。

So I can see there's like there's SSHD running， right， that's like。嗯。

If you recall like SH is like a way to just get。Get a shell inside a remote machine。

So something has to be running on the remote machine in order to enable that。We have， like。

I don't know WPA Supplic does like wifi things， I don't know why that's running。But if we press H5。

 sorry， if we press F5。We can actually see the process tree。Yes， over here so we can see。

There is an instance of Z is Z SH， So Z SH just just like it's a it's another shell。

 it's very similar to bash。😊，But it just has some more features and I use it。

You can replace that with bash in your head。So we can see that the H top process is a child of the。😡。

The bash process and the batchsh process is a child of this SSHD process。And。😊，This SSHD process。

 which is specific to my current session， because has my username in it is a child of like the big global SSHD process right so you can probably imagine that。

What is happening is that when SSHD， which is。The thing that powers SSH。But when I run。

 when I run SSH。Itll。Fork off its own little process for this my SSH session。

 And then when I'm done with my SSH session， it'll。Theyll like。That child process will exit。

 but like the parent process will stay there and continue listening for more connection attempts。

Does this make sense？Any questions？Okay， so feel free to run H top on your。

Deal VMs or I guess you can run it on supernova。And just like poke around So like the way you get this tree is F5。

 but you can also like。It also shows like how much CPU all the processes are using and stuff like that。

 so that might be interesting。

![](img/8d5c27104de75e31cff3b03677f048ef_16.png)

Okay。So okay， so we talked a lot about processes and this cycle like for thing。

 right we learned that processes are just like instances of running program。And。

The way to create processes is。嗯。They get created by other processes， right？So。

If processes are created by processes。Isn't this like a chicken and egg problem right like what's like what's the what's the first process。

 right？😡，So， and how is that created？So it turns out that the first process is a very important process and that's。

嗯。That's like。Your lab is like relevant to。To the first process。

 so the first process is called the in process and。

We like we talked a lot about like what the kernel does and how like。Processes。

Are only created by other processes， but that's actually like a lie so。

There's one thing that the kernelel does。UmWith user processes and that's it like creates。

in that process during Bo。And that's like the only user process that the kernel will respond。嗯。Yeah。

 so。Because this one process is the only thing that the kernel。

They will only use a program that the kernel is going to spawn。

 this in process needs to be responsible for managing all of the other processes in the system。

 right？😡，嗯。Okay， so this is like some this is some more like technical details。

 but like one of the ways that it's in charge of managing processes is。

So when we have when we have this like fork and join model right。

 parent processes create child processes， right but。😡。

What happens if the parent process exits before the child process， right？

If that happens and the child processes is parent gets set to the knit process right so that's like one responsibility of the knit process。

 it's to。啊。Basically， adopt all of the orphaned children。

And that's actually like really important because there's this things called。嗯。

Well I don't want to like get into like all the details again， but。嗯。When you like spot on a process。

 you have to eventually like wait on the process。嗯。And if you don't wait on the process so。Okay。

 so when you。Okay， sorry let me back up for a moment。If we go back to the fork and join model。

 so on the bottom left there's this thing called weight right and as I mentioned before。

 weight is the way for like a parent process to get the exit status of a child process right。

So if a child process exits with status code zero， which means like it。Usually that by convention。

 that means it like。Executed successfully with no errors or whether the child process exit with like an error code like one or one。

 two， three or whatever it chooses。The way for the parent process to figure out。

 to learn what that exit code was is to call weight on the child process。😡。

So in order to like enable this operation， which is like a very critical like communication between processes。

The colonel has to。The kernel must like keep track of all processes， exit codes somewhere in like。

Somewhere in memory， right。So it。You can imagine if you have like a very long running parent process that keeps forking child processes and the parent process never waits on all of these child processes。

We might have some like resourcely， right， because the kernel will have to keep track of。You know。

 if the parents spa like  a thousand processes， the kernel will have to keep track of the exit codes and metadata of all thousand processes。

😡，Indefinitely， right， because it doesn't know whether the parent process is ever going to wait from them。

So。呃。Yeah， so those child processes are called like zombie processes because they don't exist anymore they' like exit。

 but the metadata is still being saved in the kernel memory somewhere right so like another one of in its responsibilities is that。

When。呃。I swear there was like a slide on this， wait is it this slide？Oh yeah。

 so in it we'll wait on all processes。If a parent process exits。

 so if a process exits and it had like  a thousand0 children that never got waited on in it we wait on all of those just to make sure there's no like resource link。

 right？😡，嗯。Yeah， so like if if again， if the parent never exits。

 we can still have like resource leaks with zombie processes。

 which can cause all sorts of like fun problems。They're like used to be a slide of like。

Just like bug report。But。It wasn't very informative but so I took it up so I don't know why we've talked about right now。

 but okay。Well， basically turns out there's like a bunch of things you need to do in order to make sure like processes behave correctly and we don't have resource leaks。

 and that's like one important responsibility of the in system。😡，Yeah question to the waitYeah。

 so the question is。Like why doesn't the in process just wait on all children immediately。

 is that what your question is？Right， yeah， no， so that is the case， right， so if you have。

A parent process and a child process， and then the parent process dies。

Then in it we'll like take ownership of the child process and it will immediately like wait on the child process yeah so that's that's exactly how that works。

But if a zombie process， parent process is still alive， then it can't do anything about it。Right。

Until that parent process。Because you can only wait on processes that are your children。Okay。

So like another response like another core responsibility of the in system is to like。You know。

Start critical services to enable you to access the computer， right？嗯。So。

Like we talk about lot of processes， it turns out that you know SSH。

 the thing that powers SSH or like the login screen that gets displayed on your computer。

 these are also all like these also run on user processes right so。😡，The very first process。

 which is the in process， needs to， you know， that has a responsibility of like starting all of these critical processes that we need。

嗯。So like。Here's just like an example of。嗯。This is like a very typical。Text login process。

So the in process， so okay， this is like how computers work before we have like Ra user interfaces and most servers still like do this。

So the in process will start something called Getty。😡。

And Getty will like look for all of the displays that are connected to your computer。

And then on every one of the displays， Getty forks into login。😡。

And then login is like another program that's responsible for displaying this like login prompt。

 right？嗯。And then after you log in， the login program will fork into like a shell。

 which is like bash。And then from bash。We can run our programs and we run our programs I also like this all relies on this like process working lot。

And these days we like with Gal user interfaces and stuff。

 even though these exact programs are different。

![](img/8d5c27104de75e31cff3b03677f048ef_18.png)

It's still like the same like it's still the same idea right so this is like instead of Getty。

 we have something called a display manager， which is like。



![](img/8d5c27104de75e31cff3b03677f048ef_20.png)

It presents a graphical login screen， so if you're sitting in front of an OCF computer right now。

 that's like what you're looking at is the display manager well unless you logged in and then you're not。

嗯。Oh。So I like， I wrote display manager and the GDM。

 but that's like GDM is an example of a display manager So I like I messed up the sidess here。Come。

After you log into the display manager， the display manager will start a graphical session again by forking。

😊，And。This is like what example is like gnome or like。Kitty， plasma or like sway。

 I don't know if like。People any people use like Linux on their laptops or stuff like that。

 but these are just like examples of like graphical sessions that that we can start。

So that's like sort of the equivalent of the shell。In。Goyland。

 it's just like we can launch other programs from there。Yeah， and then speaking of other programs。

 just like all other programs are like forked from。G know more like。

KD plasma or whatever your desktop environment is。Right。

So this is like the last core responsibility of a it， which is to like manage our services。嗯。And。

 you know， people often think of services as like。Things that run in the background that are like not interactive right for example。

 you might have a service that like so like you might have a service that like serves web pages on your on your on your computer。

😡，That is like services often include these background non interactive processes。

 which are called demons。But。Services， they don't necessarily have to be not interact right like your display manager is a service and that's that's interactive。

😡，Your。嗯。Wow。Yeah， I mean， there's like lots of other examples of services that are interactive。

 but for some reason I can't think of anything off the top of my head。笨。对呀。

But most computer space run like hundreds of different services from like GetEty or SDDM as another display manager。

 or like SSHD to let you connect via SSH。For。HttPD serves web pages from your computer Post fix is like a mail and an email。

A email server so you can like you can run post fix and have people send email to your computer。

 which is like not how email works nowadays， but you can still。You can still do that。And。

Because these servers need to be always running for us to like。

Be able to use a computer like we need something to like keep track of everything so that's like last thing that and it does。

Okay， so。Any questions。 So this is like the end of like the。Broad general in systems。

Section and we're going to talk about system D， which is like a specific in system。

 do we have any questions before we move on？やぱしムデそまタスタ。Sir， can you say againOh yeah so yeah。

 so like as a user can you add your own like background services to the system and yeah like you can that's that's exactly what the lab is about is like also very dangerous us。

好。Because it like when the does like like no I mean。

I I like people cannot interrupt me anyway so that you must always start whatever user program they use in isn't that so。

I don't know from a security standpoint， it doesn't seem very Right， Yeah。

 so the for sorry for those on Zoom， the question is about like。

If like users can add arbitrary services that get started by the in system。

Is like are there security concerns about like running untrusted code and stuff like that， right？Um。

 the answer is like。So most of the time， so I guess like。If your system is configured properly。

Like usually you can only add services if you have like what's called root access。

 which is just like admin permissions on the machine。嗯。I guess that like。

It is possible to like misconfigure your system to allow any user to add。Services。

 which that that would be like a big security concern， but that's just， I think like if you。

If you've gone there， you've like really messed up。嗯。Like any same distribution by default。

 it'll be like。You have to have admin permissions to add services。So there is like。

 but there is like some。嗯。😊，Like on most distributions。

 you can also install packages and the packages can add services automatically。

And there is like some risk there of like a supply chain attack right like if a hostile maintainer adds like a malicious service into the package that like millions of people have installed。

😊，You know that might cause like a major security crisis。But。That more has to do with like。You know。

 trusting you're picking a trusted distribution like。

Having like security practices around like distributions， releasing like。嗯。You know。

 distributions like packaging things properly。Which goes back to tax management。

 so that's like I guess that's another reason why we want。

Trusted distributions to package everything instead of having developers directly like push services to everyone。

Yeah。Okay。Okay， so let's talk about system D this is like the final part of the lecture。

 but system D is like what your lab is mostly going to be about。😊，System D is an in system。

 it does like everything we talk about it， you know， it takes care of。You know。

 orphan processes and like zombie processes， you know it it manages your services， it'll like。Start。

Display manager and Getty and whatever if you tell it to。嗯。

It is the most common in its system used on like modern Linux systems。Nowadays， pretty much。

WellPretty much everything like。I guess not everything， but。

Like the vast majority of Linux systems run system D nowadays。

It this is like actually a pretty recent development I guess like 10 years ago this was like not the case so we used to have like a lot of different in systemss there' used to be like there's something called like ci5 in it and then there's something called like upstart and there's something called run it。

And like。You know， different。Like which in system you pick。

That would also be a property of like what distribution you're using right。

 So like some distributions might prefer to use this in system and some might prefer to use that in system。

But。Eventually， we sort of conversege on system D because。え。

Like having different in systems makes a lot of like。

Anknowing pointless differences between distributions， so having like one。Very well maintained。

In a system that all Linux distributions use is like。

It has like simplified a lot of packaging and simplified a lot of like how would we use like how you write software for Linux。

There's like some controversy around what system D does because system D is like this really big thing that does like a lot of things。

So I guess like the very last slide of the slide， you see it has like there's many different commands。

 There's login D， which like。Manaages login sessions。 There's network D， which does like。

It lets you like you can configure your network to D like Re D is like a DNS resolver。

 and it's like all of these things。😊，I guess like a lot of like very old tiny。

Linux people think that like。The Uni way is like have like。

Things that do like one thing and do it particularly well。 So I don't know。 if you search online。

 there's probably there's like some controversy around like system D， But I think that's like。

 I think it's like。It's stupid I think like。Everyone uses system D nowadays。

I don't think it's worth it to。You know， try to use another in system on your computer or something。

You could try maybe maybe it'll be fun， but I think。Yeah， system D is the good one。

 that that's that's， that's the best point。 Well， okay， whether or not system D is the good one。

 system D is the one that everyone uses。 So you should learn how use system D， okay。😊，Okay。

 so the way we use system D is we make these things called unit files and unit files are like a specification for。

For services right， so it contains things like how should the service startup up？How like。

Like what environment variables should the service have？You know， like if I start this service。

 does this service have dependencies on other services？If the service crashes。

 what should be the behavior and we like define all of these things through the systemD unit file。😡。

So here's a very simple unit file， you see has three sections， so there's unit。😊，Which contains。

 like， very basic。嗯。Information about the unit， like a description， a name。I guess not a name， but。

In the service section， you define actually like how the service itself like。

Like how to actually run the service， right， There's this line called X start。 And after the。

Except start defines like what command should systemD run？To start the service。

And you can see there's also restart equals always， which means like if the service crashes。

 you should always restart it， some other like common things are like restart a service only if it like。

Fails right if the service exits successfully with exit code zero。

 maybe you don't want to restart it。😡，嗯。We set a user to run the service。And the last section。

 which is install。Is about like。When this unit should be started， right？😡。

Systemy has like a lot of like different specifiers for dependencies。

 but the most common one is wanted by and wanted by means like when this thing is started。

Then you should start sorry when when the thing you specify and want to buy is started。

 then you should start whatever service this is so。😡，嗯。Like multidashus。 target is just。

One of the steps of the bru process。Basically， this service， the Hello World service。Is saying like。

It always wants to be started on boot， right？But like you could also imagine I could create a service that's like。

Well。Okay， for example， one of the things that we have at the OCF computer is we wrote this program to you know。

 automatically log you out if you've been inactive for like long enough。

And we don't want this service to always be running。

 we only want it to run when a user logs in right so that's like。😡。

It's a little more complicated than that， but like。

It would be like want to buy equals like plasma shell or something like that， right？

And if plasma shell is like the desktop environment。嗯。So on the next slide。

 we have like this is an example of a real service。

You can see I got this file by typing system CTL CA that's one of the system D。Commandline toolsol。

So this is。The service for Apache， which is a web server。

 So like Apache is what serves all of like the OCF websites on our web server。

Which is running on the machine called death。And。I guess we can like look at some of these lines of the file。

So there's like， who annotate。Can turn on the laser point， okay。So we have like the documentation。

 So in the unit section， we can also specify like。Some dependencies。Right。

 so we only want to start the web server after network is up。

That's like one way to tell System do to do that。嗯。

Down here we might have like so this is like one environment variable。

 which gets passed to our Apache program。So it looks like Apache does some special things if it was started by system D。

 which is like not uncommon nowadays。嗯。In the previous example， right。

 we had just an exitat Start command。😡，And。The way that if you want to stop this process。

 the way that system D would stop it is just by sending like a kill signal to。😡，The that process。

 But in this case， we can specify like。very like a custom stop command for this for service specifically。

If you want to do something like clean up before you stop， right？We also have like exactec reload。

 which is a way to like。嗯。If we like want to reload the configuration without restarting the whole service。

 system D has like a like a built in command for that that you can customize here。嗯。

There's some other things， so restart equals on aort so you'll notice this time it's not always。

 I don't actually know what on aort means， but like I guess we can search it up。



![](img/8d5c27104de75e31cff3b03677f048ef_22.png)

So if we man system D。 unit。System D that service， maybe。嗯。And we type， we start。All for it。Okay。

 so we can see on aort means like if it exited。😊，Due to。An unclean signal。Yeah。

 I don't know exactly why Apache says on a board， but it probably just has something to do with how they manage like the star install。

嗯。And again， we want this service to always be running。

 so we set one if5 equals multi user dot target and that will。



![](img/8d5c27104de75e31cff3b03677f048ef_24.png)

It'll like start the service as soon as we get to。The multi user stage of the boot process。

So are there any questions about this file specifically， anything interesting people see？Yep。

This within six executive desireative executed with vi and mind。Yeah， so exec reload is。

So we can see in this case， it's set to like slash user slash S bin slash Apache CT TL。

 So this is saying so。😊，嗯。So like reload is like。Basically like system D provides like a command line tool to reload like a configuration。

A services configuration without。Like restarting the service completely that you can customize。

 So this is saying， if someone runs that reload command on this service。

Then what system D should do is run this。😡，This executable with this argument so the thing on the right is something that comes with Apache so that path is so this this command this binary is installed when you presumably like when you installed the Apache package。

嗯。And。Yeah， so this comes from Apache， the exact reload is the thing that's built in this is something。

Does that answer your question？After I assume you was up。申。So iss it a fourth process within doing？

Okay， so what actually happens when you like run reload is that system D will。

Well system D will like fork itself and then run this， right？😡。

This is basically it's spawning like a separate process。

mFrom the process that the service is actually running under。嗯。

And I guess like Apache has like written these these commands in a way such that。

If you run a separate process with Apology CTL graceful。Um。

 it will like communicate with the existing process and tell the existing process to like reloads configuration or something like that。

Oh。And yeah， there are like ways to communicate between the processes。嗯。Yeah。

Anyone have questions about T es forking？Okay。嗯。Like type equals4 is like。So。

There's like system D has a couple like different service types and this like controls like。嗯。😊。

Some some some things about how system D manages your service， so for example。

 like how does system D know if your service has like is running right？So by default。

 which is like type equals simple， your service is running as soon as。😡，As soon as like the process。

Which is your exit at start。Gets。Started， so as long as that process is running。

 then system do will think through a services running， right？😡，嗯， but。

There's like that's not necessarily what you always want in this case Apology says types 14 and that's telling system D like oh。

 when you run exec start，😡，I'm going to fork。And only when I have forked should you consider the process running？

Oh， should you consider the service right？嗯。So that way like this is just so like maybe Apache will like fail to read some configuration files or get stuck in the startup process before it forks and if it does that for too long。

 maybe system D will like try to start it like shut it down and restart it again。It's just like。Yeah。

 this is， that's just。That's just like one of the different ways you can。Configure system dude。

So like it's like pretty flexible， okay？😡。

![](img/8d5c27104de75e31cff3b03677f048ef_26.png)

There's lots of units。If we go to supernova and we type system CTL。With no。With no arguments。

So actually I think the CTL stands for control in this case。

 so this is just like the command line utility that that system de provides。

 we can scroll through all of the unit files。😊，And we can see， like。

We can see everything else's running on here so we can see there's app armor do service there's。

You know。WhatWhat are the interesting things Okay， so there's like Chon dot service and Ch is like a thing that will like。

You can， you can make crown jobs。And。Which are like schedules for running different commands and like Crron has a service that will like look at the Cr jobs you've defined figure out like wait until it's time to run them and then like。

Run your commands again by4。What else there's， So cups is like a printing， a print server。嗯。😊，Yeah。

 when you press like when you press print on any of those， you have computers that like goes to cups。

啊。There's Docker， which lets you like run containers Docker。

 there will be lecture about Docker and in a couple weeks。So we can see there are some geties。

 this is probably like。嚟。Well like this server is like in the server group and it's like not connected to anything so but if we plug the monitor in。

 you might like see the geties on the screen。嗯。Theres。What's there。What's been good。What is what？

Fail to ban yes， fail to ban I believe is like this it like looks at your web requests。

 it looks like incoming web requests and if it detects something suspicious like a spammer or like a like a DDOS attack or something it'll like ban those Is。

😡，嗯。Yeah， it's just to like prevent people from abusing our service。嗯。Yeah。

 so like you will mostly be dealing with these services。

 but it turns out that there's like lots of other things that aren't services that system D manages。

So， like。We can have mounts。Right， so like。What amount is its like if I have a drive。

 I might want to like， if I have an external drive， I might want to mount the external drive。😡。

Like a file system on that drive somewhere on my file system。

And that's like very similar to the service right I want this to happen when my computer boots up and I want to make sure it like stays up so like system D also manages those。

😡，I don't know， you can run System CTL on your decalLVM and see what's up。There's some sockets。对呀。

my where' is my browser， oh it's gone。Hello。 how did that happen？



![](img/8d5c27104de75e31cff3b03677f048ef_28.png)

那可。嗯。And yeah， that's pretty much it before we wrap up I just want to like mention some of these commands that you'll be working with so there's like system CTL stop system CTL stop that's the start stop service。

There's a restart command， there's like the reload command that we were talking about earlier。

 and these are all like。I'm not sure if like。You can change what restart does。

But like most of these are like each service can specify how exactly they want these things to work。

嗯。Enable and disable set services to start on booth so right if we saw as we saw earlier in the unit file。

😡，Like the wanted buy thing。Sstem basically what system CTL enable does。

 it sets wanted by to multi user on target。😡，嗯。And system CTL disabledable will like。

Remove multius target from one device。So those are just like shortcuts to like start and stop them at boot。

啊。But。Yeah， oh， here are some more examples。

![](img/8d5c27104de75e31cff3b03677f048ef_30.png)

This slide is outdated， I'm going to delete it。And we'll put on another reading list later。But yeah。

 that's pretty much it for sorry about like the chaotic lecture， I hope。😊，Everyone like。Learn some。

 some things。If there are any final questions， I'll take them before we move on to like the lab portion。

That we zoom about if if the service is the same as the possible。Okay。

 so so this question on Zoom about， is the service the same as a process？Not really。

 they're like very like closely related， right？A service is like。

A service is like more of like an abstract thing， right A service is like we want something to be running。

So it is the case that yes， in more concrete terms， like if a service is running。

 it probably means it means that there is like a process running somewhere。😡，嗯。But like the。

It's not necessarily that like each service will correspond to like one to one with a process， right？

😡，嗯。Yeah， so a service is like a background process， yeah sure。Well。

A service might be a background process。That's like one of the things that can be a service。But。

I can also。You know， I can also like。Run a process。

 like open a terminal and run a process there and put it in like the background as they do other things。

 Is that a service not necessarily， right， So I guess。I guess like a service is only defined。

The definition is sort of like。嗯。😊，Up to like。It's specifically like a background process that we have told the unit system to care about。

Right。嗯。😊，And like that。It's like more， it's more closely， it's like。

It like depends highly on the unit knit system itself。啊。So I guess like。

System D services might work in like different ways from like。

Like upstart services or something like that。It's just like。Yeah。

 service is just like something we have told the in system to care about。 Basically。

 does Does that answer your question on Zoom。O。Any other questions？Okay。

 if there's no other questions， I'm gonna close the Zoom and end lecture here。 Feel free to like。😊。

If you're， if you're in the lab， feel free to like， come， poke me or loxeth or。Other OCF people like。

 oh， I guess Michael' is also here oh Michael's Boly。I guess Pomeorlaxes for help。If you need it。

If you want to chat about like。OCF or like processes or whatever feel free to and like if you're not in zoom sorry if you're not if you're on zoom feel free to like ask questions on Ed and whatever and we'll try to get to those as soon as we can。

Yeah， thanks for thanks for coming。