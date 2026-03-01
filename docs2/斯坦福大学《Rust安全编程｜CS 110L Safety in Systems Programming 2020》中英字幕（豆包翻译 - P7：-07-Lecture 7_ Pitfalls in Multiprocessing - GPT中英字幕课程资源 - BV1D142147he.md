# 斯坦福大学《Rust安全编程｜CS 110L Safety in Systems Programming 2020》中英字幕（豆包翻译 - P7：-07-Lecture 7_ Pitfalls in Multiprocessing - GPT中英字幕课程资源 - BV1D142147he

Alrighty， welcome everyone to week four this week， we're gonna to be talking about multiprocessing and yeah。

 you've almost made it halfway through the quarter， which is really impressive。

 I don't know about you， but I feel like the quarter just started and at the same time has been going on forever。

 So congratulations on making it so far and I think you should be really proud of all the progress that you've made just to give you a sense of perspective。

 So we've now hit the point where we feel like you know enough rest that you may not consider yourselves rest programmers。

 I certainly don't consider myself a rest programmer but you now know enough rust to be productive。

 you know enough to start building things。 and that's what we're gonna to start doing So starting from this week we're gonna talk about more of 110 material。

 and how that relates to safety and robustness and we're going kick that off with multiprocessing。

 but we hope we're doing well wherever you。😊。

![](img/08ca3b2028c0e8e1fa74094ae5154e65_1.png)

UmAnd staying healthy and staying sane and getting outside and congratulations on making it this far。

😊。

![](img/08ca3b2028c0e8e1fa74094ae5154e65_3.png)

So some logistics for this class， the exercises that we released last week will be due on Wednesday。

 please let us know if you need help if you feel confused I know some people don't feel super comfortable with traits and like trait boundaries and stuff like that a question can just be like you know what I don't really understand this material can you point me to some extra resources or like can you talk it over with me and we would be totally happy to jump on a zoom call or to help you over Slack we really don't want this to take a lot of time so if you get stuck。

Don't spend too much time on it， reach out and we'd love to help you。Also。

 this is just a general reminder you can substitute any week's exercises for if you want to write a blog post about your experience with rest。

 something you like， something you don't like， whatever you want， it can be literally anything。

 and so if that's interesting to you， just wanted to remind you that that's an option。

The first project is going to be coming out later this week。

 probably on Thursday or Friday and that will be implementing a mini debugger that'll be due two weeks from whenever it comes out。

 you'll be able to work with a partner and if you have suggestions for partner matching or for finding people let me know I'm thinking of just like sending a message in Slack and then people can respond to it saying I'm looking for somebody。

 but if you have better suggestions let us know。There won't be any exercise this week just the survey because of the project。

Okay， so today we're going to talk about why you shouldn't use what we've been telling you to use in 110。

It'll be a little controversial。 I'm going to try to make some arguments as to why I think this is the case。

 And then on Thursday， we're going to try to do a case study of how Google Chrome uses multi processingces。

 I think Google Chrome is one of the most sophisticated。Systems out there right now。

 Google Chrome is actually kind of an operating system in some sense。

 and so we'll take a look at how it uses processes for performance and for safety and security。



![](img/08ca3b2028c0e8e1fa74094ae5154e65_5.png)

So to kick this off， let's talk about fork and I'm going to try to make the argument that you shouldn't call fork in your code despite us telling you to call fork in 110 So why do we have fork can anybody throw some reasons for why fork is useful？



![](img/08ca3b2028c0e8e1fa74094ae5154e65_7.png)

Like why do we want to call it in our code？Feel free to unmute yourself。 why is。Okay。

 so this is a Google Chrome question， I'll answer this on Slack after or if Imen you want to take a stab at it。

Why fork？That's exactly right， so if you want to invoke some other functionality on the system。

 if you want to run some other binary and you want to continue running， then you need to fork。

 are there any other reasons why we might call fork？Exactly。

 if you only have one process in one thread， you can't get much concurrency。

 I mean you can install signal handlers， but besides that you can't do much concurrently and so fork allows you to execute multiple functions or multiple pieces of code at the same time。

 exactly。So get concurrent execution and invoke external functionality。

 like run a different executable。I'm going to try to argue that the first reason is not a good reason。

 so let's start with that。You want to run multiple things at the same time。

 say you want to run another function concurrently or or you have some like block of code that you want to run at the same time。

 How how could we mess this up So I'm going to。

![](img/08ca3b2028c0e8e1fa74094ae5154e65_9.png)

![](img/08ca3b2028c0e8e1fa74094ae5154e65_10.png)

Open up an editor。And everyone could see this， yes。It's main。Okay。

 so we want to run something at the same time。 We say PID T equals fork and what do we。

What do we do from here， what are some ways that we could screw this up？We would say something like。

 if， oh， I need a P ID here。 If P ID is 0， then。Do some stuff concurrently。啊。

Continue with parent process。How can this go wrong？Yeah， so that's one thing that could go wrong。For。

Got to reap。Child， So if you forget to call weight PID， why is that bad？一。You're exactly right。

 Does anyone know why that's bad？Exactly， it's a resource leak。

When you fork you're kind of allocating memory， it's not in your virtual address base。

 it's in the kernels memory， but you are allocating memory and you need to call weight PID in order to free that memory。

 otherwise the kernel is going to keep that process data structure around and if you are running this for a very long time you're going to accumulate a lot of zombie processes and eventually you can actually run out of processes your system will stop working because you can't fork processes anymore because you don't have any more available processes so yes。

 that's one issue that could happen here。What else could go wrong？We could have raised conditions。

 let's consider the simple case where we aren't using signals and remember that when you fork it creates a separate copy of the virtual address base。

You don't really have the processes writing to each other's memory。

 so race conditions are less of a problem。嗯。So let's simplify things and set race conditions aside。

What if we want to start two child processes that do two different things concurrently so we could do something like this。

If P D 2 equals 0。Other stuff。Right。Yeah， this fork here is going to produce two child processes or it's going to produce one child processes。

 you're going to have your two processes， your parent and your child。

 and then both of those are going to do this next fork。

So now you're going to have four processes instead of the three that you wanted。

 because your first child ended up creating a grandchild。 So that's not good。

 So you have to be really careful with your ordering here。

 And this is a very common mistake that we see in assignment 3。 You have to be careful。

Where you put things， because where you put things really， really， really matters。

 you can swap two lines in code like this and it will do something completely different。

So you need to be careful of that。What else？I didn't really fill out this code here。

 what if I start writing things like print F， hello from Child one？And how would I do that？Yeah。

 so we need to be really careful here that。When we're done with the child。

 we return because if we don't， then what happens， the child is going to continue outside of this if statement and it's going to execute the rest of this code。

Okay， so we have to make sure that we return。Here。And now let's say that some other developer comes into this code base and is adding some more stuff and stuff starts to get unwielly。

 so what do they do， they refactor the code， And so how do you write a function in C int funk。

That might fail so that it can return an error code and then you decompose。This code。

And does anyone see where I'm going with this？What's wrong with this picture？Yeah。

 we're not stopping the child anymore。Because we expected this return zero to terminate the process like we did stuff inside of the child process。

 Now we're done。 we want the child process to go away， so we return， and then the child goes away。

But not really， because it just returns back to Maine and it starts executing the rest of this code that was intended for the parent。

And that's not good。 So you say， okay， well， I'm not going to return。 I'm going to。

Exit would be the sure way to make a child go away， but what if you did this instead， let's say exec。

 VP， some stuff， and then I do throw could not find excutable。What could go wrong here？

Say this is C++。So this is not no longer an int。Yes， exactly。 if you put this。

 so you write that and you're like， okay， this looks fine。 there's nothing wrong with this。

 And that's actually true。 If if exact Vp were to fail you would throw this and the child process would terminate because there's no handler。

 Okay， so that actually works fine。 and then two years later。

 some other developer on your team comes and and is modifying the way that this error handling works and they add a。

😊，An exception handler so they wrap this in a try and then they have a catch and I forget how catches work in in C plus plus what the exact syntax is it's something like。

😊，Probably。You catch some error of some type and then use a like printf or if this is C++ then you do C out。

Oh， no， NL， right， and if you catch that in some way and then you continue on with the rest of your business。

 now you have a child process that is running code that was intended for the parent。

So that's not good。And at this point， you might be thinking like， okay， Ryan， well。

 all these kind of seem like。Avooidable， simple problems。Um， and that's。That's a fair argument。

 right， I kind of made up some of these situations。

I think the real danger here is when you have multiple programmers working on a project because you might have written this code and you're confident that it's safe。

 but there are a lot of subtleties to it and it's very easy to break and if some other programmer comes along that may be less familiar with things and they change things。

 they may violate your implicit assumptions。And break the code in very interesting ways。

The one that I think is the most egregious。I if you were to do something like this inside of your child process。

 we want to call ZecVP and for whatever reason we decide we want to use the heap for the AGV array so we do something like Con。

Car double star args equals Malik size。Of car star times。Args or something like that。

 and then we do exec BPP Args。Arcs of。Zero parts。And this looks pretty harmless。 right？ I mean， we。

 we can do some error handling here， like print F。Oh。And then exit one right。

 this doesn't look so bad。 Does anyone know when this might cause a problem？

That's a really good question。 We're allocating this memory and we don't free it anywhere。

 It turns out that。Sttylistically we definitely should free it and velgrind would complain。

 but because we're either doing ExecVP or exit and both of these destroy the process。

 I mean ExecVP doesn't destroy the process but it throws out all of your memory it effectively gets freed here so yeah I really probably should have done free args here but。

呃。Yeah， so let's add that what else is wrong here。That's a good question。

So exactly people will actually follow whatever pointer you give and it will extract the data that it needs before it wipes out the memory。

 so you can pass it a heat pointer and that will be okay。 The problem is actually right here。

And this may be very surprising， but Malik is not。Maalik is threads safe and we haven't talked too much about threads in CS110 yet。

 I know it was just introduced yesterday and we'll talk about it a little bit more on Thursday or around Wednesday。

 but。Threads are another way to have concurrent execution on a system。 And unlike multi processing。

 where your processes are separate， they have。Separate virtual address spaces when you have threads。

 you have multiple threads of execution inside one virtual address space， they share memory。

And because they share memory and Malick allocates memory， Malik has to be very careful。

 such that if two threads try to allocate memory at the same time。You avoid race conditions。

Think about how when you have a signal handler that could modify variable at the same time as the rest of your code。

 you have to be careful to avoid race conditions， MELC has similar ways they're called locks of ensuring that two threads allocating memory at the exact same time don't corrupt some shared data structure from the memory allocator。

The problem is when you fork what happens to your threads？It turns out that if you call fork。

 only the thread that called fork。Will survive。 All other threads disappear。

But they don't get a chance to clean up or to finish up。

So if you call fork in your main thread and you just so happened to have another thread that was in the middle of allocating memory。

That other thread may have the heap in some like inconsistent state。

 it may be in the middle of like think back to 107 when you are implementing the he allocator and you sometimes have to do these pretty advanced things like taking a chunk of memory and like merging it with another chunk or maybe taking a chunk of memory and splitting it into two allocations。

Mac in the other thread may be in the middle of modifying all these data structures now you just forked and so the other thread disappeared。

 it never had a chance to clean up， there's only one thread now in the child process after this fork。

 and then it tries to go in MalC， but the Malic data structures may have been corrupted。

And so you can't malloc in。In a child process when you have multiple threads involved and you're like。

 okay， Ryan， well I don't have multiple threads， I look at this program and I am certain that there are no other threads running and so this should not be an issue for me。

And to that I would say， okay， you might be sure that your thread doesn't use multiple threads。

 I'm sorry， you might be sure that your code doesn't use multiple threads。

 but are you sure that the libraries that you call don't use multiple threads？

Because it's very common for libraries to depend on multi-threading to speed things up。

 to do things in the background， to run things concurrently， so on and so forth。

 and if you want to do this， if you want to allocate memory inside of a child process。

 you have to be 100% certain。That there are no other threads running on your system at the time that you call fork。

It's kind of a hard guarantee to make if you're doing anything complex。

 If you're using any libraries， you have to make sure that they're not using threads。

And so I argue that this is actually probably the biggest reason that you should not use fork to execute additional functionality So in this example like。

We could have just used a stack based array for this。

 but if we go back to what we originally saying we like call some other function to run it concurrently where like we're trying to run a piece of our program at the same time。

I mean， dynamic memory allocation is very common if you want to use a string in C++ or a vector N C++ that all uses heat memory。

And so this is a really big limitation。 And this is why I would argue that if you want to。



![](img/08ca3b2028c0e8e1fa74094ae5154e65_12.png)

Run two parts of your program concurrently， you should make them separate binaries。

You should start with your main program and then fork off a child process and call ZVP on your other binary。

 because that way when you do that ExVP， you throw away any potentially inconsistent state if MalC is corrupted that's okay because we're throwing out virtual memory and then you install a new virtual memory with your new binary and now you have two pieces of a program that are running concurrently at the same time。

Does this make sense to people？And I can also revisit this example when you feel more comfortable with multi threading because I think。

That context may be important to understand why it's such a severe issue to mix fork with threads。

But that is probably the biggest reason why you should not use Fork to run another component of your program at the same time。

You should just put it in a separate separate executable and you can share the code base if you want to。

 like compilers will allow you to include some library files in both binaries。

 but create a separate binary and exact that binary。And do it that way instead。Thumbs ups down。

Does everyone follow at this point？That's a really great point。啊。

Why should we be forking at all when threading seems like it might make life easier？

I'm going to talk about this on Thursday because this is the reason that Google Chrome uses so many processes。

 like you will see Google Chrome has made such a huge effort and a gigantic investment in building out a multiprocess architecture。

 it is way harder to implement a multiprocess browser than it is to implement a multithreaded browser for those of you who have started assignment3 and have gotten a farm。

 I know it was just released， so you probably haven't gotten to this part of the assignment yet。

 but there's a part of the assignment where you have to use multiple processes to factor numbers concurrently and you'll find it's really challenging。

You'll probably spend， that is probably the hardest part of assignment 3， Simon 3 has four parts。

 and that's probably the hardest one。And you're just sending numbers。

To different processes like you have a master process。

 it sends a number to a different process saying， hey， please factor this number。

 And then that process prints it out。 It's like one of the simplest things you could do。

 and it's really hard and really complicated。 So imagine building a browser where processes have to exchange much。

 much more complicated information。 It's really hard。 And yet it's the right thing to do。

 So I'll talk Thursday about that about why it is still important to use multiprocessing over multithing in some cases。

😊，Okay， so yeah， so better to exactly the P and invoke some other binary。So let's cross that out。

 we'll say if we want to be safe， we should not use fork to get concurrent execution。

 we should only use fork to invoke some functionality on the system to run some other binary。And。

Okay， so how do you， this is called starting a subproces， you fork and then you ex。

 you fork off another process and then in that process you call Exec VP to run some other binary concurrently。

And you'll find if you read a lot of C code that that does multiproces。

 almost every fork is followed by an exec， it's like fork and then exec fork and then exec this previous pattern that I was talking about for running concurrent。

Or running other parts of your codeb at the same time is thankfully not so common。So why did they？

Why did they design it like this， like why do they have a fork cis call， an exec Sys call。

 why didn't they just create a single cis call that does both？Does anyone have any guesses？

That's a good point。 There are a lot of different variants of exec that do slightly different things。

 so。That's true， but then they could just， if there are like 10 variants of exec。

 then they could have just had 10 variants of fork exec。But you're on the right track。

 It has something to do with。With flexibility。Assignment 3 in 110。Yeah。Yeah， exactly。

 something you do with file descriptors， maybe you want to rewire the file descriptor table。

 or maybe you want to change some environment variables or in assignment3 in farm。

I said you're gonna to be factoring a lot of numbers and doing a lot of computational intensive things。

 Maybe you want to pin a process to a particular CPU core so that if you have multiple CPUs。

 you can run things at the same time with the processes not migrating across cores and destroying your cache and this is so Windows actually doesn't have a fork cisca Windows has this single cis call which is a fork and an exec and this is what it looks like it takes a crap load of arguments and a lot of these arguments are actually strucks So not only does it take a lot of arguments but it takes arguments that have arguments and it's extremely complicated because they attempted to do this。

All of this in onces call， they say you can spawn a child process and have it run a binary and you can configure it however you want。

And they were like， great。 and we're like。Not great。 Why。

 because this is really ugly and it's not very fun to invoke。 and there's quite a lot going on here。

And by contrast， fork and exec take almost no arguments。 They're extremely simple。

 and you can do anything you want with them。 You can do more with fork and exec than you can with this because if you want to do something that is not specified by these arguments。

 you're out of luck， but with fork and exec you can fork a child process and then you can use any cis call to customize the child process and then you can call exec and a lot of those properties get inherited。

 the file descriptor table gets inherited， the signal mask gets inherited if you want to block signals inside of the child process。

 you can do that by blocking signals before exec。 the CPU core binding gets inherited what else I think I had a list here。

 you can change environment variables， you can make the child process take control of the terminal。

 you can enable debugging on the child process， you can do anything you want with just these two cis calls it's a beautiful design very simple。

 very powerful， but simple does not mean。EasyAnd because it's so powerful， its very easy to mess up。

 right， Malik and free are very simple， too。 They're extremely simple。

 You just allocate some memory and then you free some memory。 can't get simpler than that。

 And by contrast， I would argue that rust is actually really， really complicated。

 And I think by this point， most of you would would probably agree。😊。

But just because something is simple doesn't mean that it's easy to use and because it's so powerful。

You need to be careful not to shoot yourself in the foot。So what can we do here？In my opinion。

 the best approach is to let forking the exec VP or let fork and Exec be let's not try to change the cis calls because that is at a very low level of abstraction。

 this is how we talk to the operating system and sometimes we really do need that flexibility so the cis calls are there if you need them but for the common case let's define a higher level of abstraction so that we don't shoot ourselves in the foot by writing crappy fork and Exec code which I just showed you like three different variants of。

So in assignment three， you actually do this， you implement a subprocess function。And in a slide。

 I'll show you what this looks like in rust， rust has a struct called command。

 which basically just lets you create a subproces， Python has a subprocess module。

 any language that you look at is going to have an abstraction like this and many times these abstractions will allow you to define what's called a preex function。

So the the abstraction will give you a lot of options like you can change how standard and standard out and standard error are wired。

 You can change environment variables。 You can change the current working directory inside of the child process。

 you can like customize a lot of these things。 But sometimes you know what。

 like I was talking about with Windows。 Sometimes you want to customize something that is not defined by this interface。

 you need to go outside of the box。 And most of these libraries。

Allow you to specify a pre Ex function， which gets called after fork but before Exec。

So because of this preexec function， there's really no reason to call fork or ex because if you need to do something that is not defined by this abstraction。

 you could just do it inside of the preexec function and this is something that will have you do in the project coming out later this week for the debugger because the rust abstraction doesn't allow you to enable debugging in the child process you have to make a cis call that is Linux specific。

 so that's why they don't include that in the general command。Stt。

 but they let you specify a pre exact function and in that function we can make the ciss calls to enable thebugging。

Okay， so let's talk about very briefly how this works。The syntax is pretty straightforward。

 so this is straight out of the starter code for the week three exercises。

 so you say I want to run this binary and I want to pass these arguments there's a way to pass multiple arguments one by one if you want to look at the command documentation it's excellent and this is how you construct a command。

A command being a sub processcess。So。Doing this first bullet points code doesn't actually run anything。

 it just tells Rust， hey， I want to create a subpro。

You're telling restss like I want to set up a set process。

 but I don't actually want to run it yet in order to run it。

You can call one of three different methods， and the first one is called output。

 So if you call output that is going to run this subproces and it's going to block。

 it's going to wait for that subprocess to finish。And when it finishes。

 it will return you everything that was written to standard Out and standard error。

So if you've used subprocess in Python before， this is similar to Python's check output。

 you're running something， you're waiting for it to finish and you're getting the output really convenient if if you just want to invoke some。

External binary， wait for it its finish and then come back and do something with its output。

There's another variant instead of calling dot output you can call dot status。

 so this will not rewire standard out or standard error to go to a pipe。

 standard in standard error will standard in standard out and standard error will be left bound to the terminal or to whatever it was bound to before in the parent but it will wait for the child process to finish running and it will return to you the exit status code。

So that's that status。And then the last variant is called dot spawn and dot spawn just kicks off a child process。

 it doesn't actually wait for it or anything like that， it just forks the child process。

 does the exec and then returns you a handle， which is a child struct。

It returns you a handle which you can use to wait in the future。So later down the road。

 you can call a child。 weight and that we'll call weight PID on the process。Any questions so far？

So this pre-ex function that I mentioned， you'll use this in the project all you really do is you create your command。

 you add the arguments or whatever， and then you do command。

preexec and you pass a function that you want to execute inside of the child and you'll notice this like unsafe bracket and you're like。

 whoa what's that that sounds pretty dangerous， we're going to talk about unsafe rust in the last week or maybe week9 of the quarter but basically this is a red flag to a programmer that you need to be really careful with what you're doing in here because again。

 why did I say to try to avoid using fork and exact V directly。

 you need to be really careful not to allocate memory in the presence of threads and you may not even know that you have threads。

And so you have to be very careful inside of this unsafe block to not do anything that allocates memory。

 it should be very， very， very simple function here。Dangerous， but it's there if you need the power。

So。How did we do I had this list of problems earlier that we might see from doing forkkin exec ourselves and we've knocked out the first three issues。

 you still need to be careful not to create zombie processes right I mentioned that the command dot spawn returns a child process and you still need to call weight on that child process if you wanted to you could implement a struct with a drop trait that calls weight so that as soon as it goes out of scope。

 you automatically reap the child process， the reason that they don't do this is because。呃。

I don't want to spend too much time on this。But I think the reason is because it it makes things confusing。

 you can have。Say that you on a child process and then you return from your function and your child process gets dropped。

 your program might hang there if your child process doesn't exit and it may be unclear to a programmer why it's hanging and so they want you to call droprop by yourself or they want you to call weight by yourself if that's confusing I'll explain it a little more in slack because I don't think it's super important here。



![](img/08ca3b2028c0e8e1fa74094ae5154e65_14.png)

So quickly， let's talk about pipes。

![](img/08ca3b2028c0e8e1fa74094ae5154e65_16.png)

What are some issues that you can think of with pipes？

Some issues maybe that you've seen in your own code with calling the Pi ciys call。Yeah。Yeah。

 not closing them forting to close them or closing the wrong file descriptors like maybe you intended to close the file descriptor。

 but you closed it too early and then you used it later on or maybe you just close a number。

 an invalid number， that's not good。That's probably the biggest problem。

 so here are some that I thought of， so leaked file descriptors means failing to close the file descriptors you forgot。

This I see this in office hours every single quarter on this CS110 assignment 3。

People will write code like this， so they're trying to do error checking on clothes and they write code like this。

 Does anyone know what is wrong here？This is the worst because we're not supposed to look at their code。

And we asked them what they did and they did everything exactly right。

And yet they have bizarre issues like their program doesn't accept input anymore or they're adding or here's what they say。

 they say my program deadlocked and I'm like what， theyre like it deadlocked on a close and I'm like。

It can't， that's not possible， and they're like， well。

 I put a print statement before and I put a print statement after and the print statement after never prints。

This closing parentheses is in the wrong spot， it should be here。

You're checking if the output of close is equal to negative  one。

 but instead this is checking if the file descriptor is equal to negative  one。

 which is going to give us back a Boolean， which is a  zero or 1， so we're closing zero or 1。

Most likely zero， so this ends up closing standard in。And that's not good。So。

So that's a problem that you need to be aware of Sometimes people will declare an array of ints and then they'll use like something from that FDS array before they actually call pipe。

So that's kind of a use before pipe and also a use before close in some sense a pipe is kind of like memory。

 right it's a resource and the same kinds of issues that we see with dealing with memory。

 we also see with pipes。So what is the solution？Add another layer of abstraction。Yeah。

That's a bad solution。But in this case， it's the right one。 when you have problems。

 don't throw more layers of abstraction at them。 but in this case， it actually makes a lot of sense。

 We can do something similar to what we did with memory。

 We can create a pipe object with a drop trait that closes the pipe。

 And then everywhere that we need to use a file descriptor or where we need to use a pipe。

 take one of these pipe objects don't take a random integer because then you'll avoid these kinds of issues where like you just pass a number and it happens to to work as a file descriptor。

 which is not good and you'll avoid issues with closing。 So I'm going。

Kip over the slide because I really want to get to signals and because you aren't going to need to use this for the foreseeable future。

 but if you wanted to write to a standard in pipe or create pipes in rest。

 this is how you would do it。

![](img/08ca3b2028c0e8e1fa74094ae5154e65_18.png)

And as a quick aside， you might be looking at this and thinking like， Ryan。

 why are we talking about this？You are telling us in CS110 to use fork and Ex VP and pipe and signal。

 and now all of a sudden you're like telling us not to do all these things， what's up with that？

To that， I would say I think it's really， really important for you to understand how this stuff is working under the hood when you use libraries。

 you need， especially in systems， especially in systems。

 you need to understand what those libraries are doing for you because in systems usually。

The interactions between code are so complex like I mentioned earlier。

 you can swap two lines of code looks in a， completely changes everything。

 Our autograder for CS110 is so broken I have to like apply a git patch during week three。

 every single quarter in order to make the autograder run for assignments3 and4 but that patch actually breaks the autograder for assignment 6 and so you have to unapply the patch every single quarter for assignment 6 in order to get it to work and it's because it has grown into this multiprocessing mess with a lot of interactions where you know what that patch does it just reorders two lines。

😊，And you can swap two lines， looks innocent， completely changes the characteristics of things。

 and so I think it's very important that you understand how this works and that you respect it enough to not use it if you don't need to because we've built up abstractions so that you don't shoot yourself in the foot。

 but if you need to implement those abstractions or debug a problem with those abstractions。

 you need to understand how they're working。So that's my my quick plug so with our remaining。

We'll probably take the whole rest of the time， I really wanted to do this in breakout groups and I think I still will because this will be a fun exercise so in the remaining time I'll put you all into breakout groups and if you go to the course website。

😊。

![](img/08ca3b2028c0e8e1fa74094ae5154e65_20.png)

![](img/08ca3b2028c0e8e1fa74094ae5154e65_21.png)

Go to the course website and in the lecture notes for today。

 I have four code examples that you signal。

![](img/08ca3b2028c0e8e1fa74094ae5154e65_23.png)

Oops。Cs 110 L。tanford U。嗯。So if my interent decides to work。

 check out the lecture notes for today's lecture and there are four code examples here。



![](img/08ca3b2028c0e8e1fa74094ae5154e65_25.png)

Some are safe， some are not。So in breakout groups for the remaining。6ix minutes。

 Go ahead and talk through whether you think these examples are safe。

 And then we won't have time today， but at the beginning of lecture on Thursday。

 I'll come back to this， and I'll explain。

![](img/08ca3b2028c0e8e1fa74094ae5154e65_27.png)

![](img/08ca3b2028c0e8e1fa74094ae5154e65_28.png)

Why the results are not what you might expect。

![](img/08ca3b2028c0e8e1fa74094ae5154e65_30.png)