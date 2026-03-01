# 斯坦福大学《Rust安全编程｜CS 110L Safety in Systems Programming 2020》中英字幕（豆包翻译 - P8：-08-Lecture 8_ Pitfalls in Signal Handling, Google Chrome case study - GPT中英字幕课程资源 - BV1D142147he

Welcome to Thursday of week 4， we're almost at the halfway point of the quarter。

 just some quick notes about the project， so we'll be releasing the mini GDPB project tomorrow。

 We'll have you implement a very simple version of GDP that actually has most of the most of the functionality that you might use from GDP setting break points and stepping through code so it'll be a really fun project You're also welcome。

 We want to remind you that you can propose your own project and you can work on anything you like。



![](img/14cbbbe339881052b6207b5da6debf13_1.png)

So some potential ideas， somebody a couple weeks ago asked if there was any tooling that helps you understand what the rust compiler is doing specifically。

 is there any tooling that helps you see when the compiler drops a value and the answer is no there is no such tooling right now。

 but there could be if you wanted to implement something like that and we would be happy to give you some pointers。

If you are interested in a particular area， feel free to implement something in rust that has more to do with that area。

 for example， if you've taken CS148 and you're interested in computer graphics。

 maybe you could implement a ray tracer and then in the later part of this quarter when we start talking about multithreading you can make your ray tracer really really fast you could pick a command line tool like GrEP and try to beat its performance there's a rust based program called RipGEP which is GrP but much much faster and that could be a fun challenge。

If you're interested in databases， you could try implementing a simple database。

 anything you can think of， just like send us a message， ask， does this sound reasonable。

 do you think I could do this in a little over two weeks and we'd be happy to give you some feedback or point you in the right direction？

Any questions about the project before I move on？Cool。嗯。All right， so quick overview of today。

 we're going to pick up where we left off last week talking about signal。

 and then we are going to do a short case study of how Google Chrome uses processes。

 And I think this will be really exciting。 It's a very， very interesting project with。😊。

Many different constraints and many different goals。

 and so we'll talk about how they use multiprocesing to support those goals。



![](img/14cbbbe339881052b6207b5da6debf13_3.png)

So first we left off talking about don't call signal。

 which feels a little controversial because we just spent a long time in CS110 and you're about to spend a long time on the projects struggling with like signal handling and concurrency issues and how to deal with all of this。

 why am I telling you not to call signal Well it turns out if you look at the man page the man page says don't call signal It says the behavior varies across Uni versions and it varies across different versions of Linux don't use signal and it says see portability below if you look at this portability section It says the only portable use of signal it to either ignore signal or restore the default handler So signal is fine for this but if you want to set a signal handler do not call signal there's a different function called Sig action。



![](img/14cbbbe339881052b6207b5da6debf13_5.png)

Which you should call。 And it's talking about this like mess of semantics。

 explicit control of semantics。 What are semantics。 So in this。Context。

 semantics is referring to what happens like the details of signal handling。 For example。

 say you get a sick child and that starts your sick child handler。

 And then while you're in the middle of the handler， you get another sick child。

Do you restart the handler or invoke the handler again right away？

Or do you block SIig childild until the handler finishes running and then run it again That's an example of signal handling semantics that is actually unspecified by signal but Sig action has a bunch of options that allow you to specify something like this the reason we don't talk about SIig action in lecture is because if you look at its interface because you have to specify all these options it's really ugly for whiteboarding but we use Sig action on the assignment for starter code you'll see there's a function called like install a signal handler which called Sig action and if you ever use signal in your own CC+ plus projects you should be aware that you should not be calling signal。

This is actually a really interesting man page， it talks a lot about the historical legacies that led to this portability mess。

 so if you want to it's a pretty interesting read。All right。

 so last time I gave four code examples that were either safe or unsafe。

 Let's go through them quickly， and I'd like to hear what you all think。

 So what did you guys think about this， Sa or unsafe。😊，Yeah。Yeah， this looks pretty simple， right。

 there's not a whole lot going on here， it loops forever and then whenever it receives control C。

 it just exits So yeah， I would call this one safe。

What about this one So this one counts the number of sick child signals received and somebody at the end of last class mentioned that you should probably have a while loop inside of your handler if you want to so if you're using this handler for the purpose of calling weight PiID on all your child processes you should have a while weight PiID returns more than zero here so that you get all of the child processes because as I mentioned you can have two S child signals that are sent at the same time and if the parent receives them at the same time。

 it will only invoke the handler once so if you're calling weight PD in in your handler up here you may need to call it multiple times so that you get all the child processes that generated the signals coming in at the same time that's not the purpose of this example。

This example is just intended to count the number of sick childil signals that come in。

 and at the end you can compare it to the number of processes and almost always you'll see that the second number printed is less than the first one。

 There are fewer sick childil signals received than there are processes that exited so there's no correctness issue here。

 I'm wondering is there a safety issue here， is this code safe。What usually causes race conditions？

That's exactly right， data races are generally caused by having some shared resource that is getting used in multiple places at the same time。

So this is our shared resource， it's the only shared resource， it's the only global here。

Where is SG childild count getting used？It's getting used by the printf and one other place。

Also the handler， so there are two places here where it's getting used。

 is it possible for these two places to use the variable at the same time？Yeah。

 it is not possible for this to happen at the same time because of this way PD here。

 this way PID is going to wait for all of the children to exit。

And you get sick child when the children exit。 so you can get wait or I'm sorry。

 you can get sick child signals up until this point， like just after this while loop。

 after this point。You've already called W PI on all the child processes。

 all the child processes have terminated， all the SG child signals have come in。

 there won't be anymore more after this point。 So by the time you get to this printf。

You will no longer have this handler running and so。

There are two places that use this variable but they're separated by time。

 they don't use it at the same time， and so this example is actually okay as long as we're using SIGA action to specify that the handler can't be running multiple times。

 like the handler can't get interrupted by itself， which is usually the case and when we talk about signal semantics in CS110。

 these are usually the semantics that we use。Okay， how about this one？

This one we are trying to count the number of running processes。

 so in this loop we fork a bunch of processes and increment a counter and then we decrement that counter inside of the six child handler and at the end we print the number of running processes。

Safe or unsafe。Anyone want to take a guess？OkaySo we're incrmenting and decrementing in two different places。

 and you say that feels weird to you， why is that？Yeah。Okay， well。

 so this sleep one call in here kind of。Trew things off but in theory you could have so it's not so much that you have an increment in a decrement in different places。

 it's the fact that in theory they could happen at the same time。

 so you could decrement here at the same time that you increment here Let's just say because I have the sleep one call in here。

 let's say that we have a reasonable operating system scheduler that is not going to schedule this line one second later like there's not going to be a one second delay in running this for loop。

 So let's say that it's impossible for this increment and this decrement to happen at the same time。

Does that help？Does that fix our safety issue？Okay。

 so we could have a potential deadlock scenario where if we check that running processes is greater than zero。

 but then a sick child comes in right after this while loop。

 so right in between these two lines after we have checked that it's greater than zero but before the pause and that ends up decrementing running processes to zero。

 then we shouldn't pause， we don't want to pause because we've like all of the child processes have exited but we've already committed to running the code inside of the while loop so the next thing we do is pause and then we end up deadlocking indefinitely that is definitely a safety issue。

Is that the only safety issue？There's something really simple here。In the same place。Yeah， it。

Go ahead。This may not be obvious because this is just a simple integer。

But it's really not considered safe to。Be looking at to be reading this value。

While it's possible for it to be modified。And it is possible so reading this value and comparing it to zero happens in multiple assembly instructions。

 and it's possible that in the middle of that，That this handler gets changed and I'm sorry that this handler gets called and the value gets changed and if here it's not that big of a deal because it's just a simple integer and on x86。

 this will be fine。But formally this behavior is undefined。

 if we were to run this on a different architecture， we're not really sure what might happen。

 and if this were more than just a simple int， if this were like a list of running processes。

 for example， and then that list gets modified while we're trying to look at that list。

 the list could get reallocated while we're trying to look at that list and now we may be looking at invalid memory and so you definitely don't want to be reading a value at the same time that it's possible for that value to be changed。

And so all of the places in this function main where we're using running processes。

 we would need to make sure that the handler doesn't run by using Sigproc mask to block Sig childild。

And then here， when we're using this pause， we'd have to use six to spend instead as talked about in 110 so that you avoid thatlock。

 the potential deadlock where the signal comes in right after you check your condition。

 but before you go to sleep。Does this make sense to everyone， thumbs up， thumbs down？So。

I want to make sure that I have time for the rest of the slides， so I'll answer that in slackla。

 but essentially six supen。嗯。Yeah， I'll answer it in Slack because it's a really good question and it's important but。

Yeah， yeah， that'd be great。Any other like major questions about what's going on here？Okay。

 here is my favorite example of the whole quarter， is this safe or unsafe？

And I kind of just gave it away by drawing so much attention to it。

So if you're looking at this coming from CS110， you should say this is safe like Ryan。

 this is one of the simplest examples you've shown。

 this is the second simplest example of these four。

 All you're doing is you're like so this is silly because when you do a control C it just prints he he not exiting instead of actually exiting but like。

😊，Theres it doesn't look like there's anything wrong here。 You're just printing right， This is。

 this is so simple。 What could go wrong。 And I say this is actually no not safe。 And you're like。

 what how is this possibly not safe。 And， and I would argue that anything could happen here。

 We have no idea it could crash， it could deadlock。 And to demonstrate that for you。

 I wrote a an extended version of this。 So instead of just printing one small string。

 It prints a very long string。 So I repeated the string hellello world 1 thousand times。

 But all I'm doing is inside of this wild true loop。

 I'm just printing hello world1 thousand times over and over and over again。

 Like that's all that's going on here。 And then at the same time。😊。

I spawn a child process and the child process just in a wild true loop。

 repeatedly sends SIG user one to the parent。 What does a SIG user one handler do Well I installed this signal handler that just does print F hello world。

So that's all that's going on here。Really， really， really simple。

 it's the exact same thing that we're doing here。

![](img/14cbbbe339881052b6207b5da6debf13_7.png)

And if you run this program， you're welcome to run it。It deadlocks。And you're like， what？

Or if you run it， sometimes you end up getting a sigaboard。And it crashes。And you're like， what？

 And then even weirder some occasionally， this， this has only happened to me a couple of times。

 But you run it。 And before it even gets a chance to print anything。

You get illegal hardware instruction。And this is the exact same code that I just showed you on the slide and you're like。

 whoa， Ryan， back to truck up， like what's going on here？



![](img/14cbbbe339881052b6207b5da6debf13_9.png)

It turns out that you cannot call printf from a signal handler that is absolutely not a safe thing to do and to understand why。

 first of all printntf is a horribly written function It's some of the worst code that I've ever read in my entire life。

 this things almost 2000 lines along but somewhere in the middle of those 2000 lines。

 there's this call to a system call called F lock and what Flock does is it locks an open file so it sets a bit inside of the open file table entry saying hey。

 please don't write to this file right now and the reason is because if you have multiple processes on a system that are printing at the same time you don't want their output to get jumbled together and so we use this locking technique so when you want to print you lock standard out and then you write to it and while you're writing no other process able to print to standard out。

 no other process able to write to standard out so that the output doesn't get jumbled together and then when it's done printing the standard out。

 it unlocks the file descriptor and other processes are well。Wee to right。

Apparently there's some other stuff going on in here too， it calls MalC。

 Malik does something similar， but because of this use of global state and this use of locking。

 this ends up causing a lot of problems and in general you should not call functions that use global state there's a list of safe functions here。

 it's long but it's not that long， there's a whole lot of functions in C that you commonly use that are not included here and most functions in C++ which depend on dynamic memory allocation。

 for example， if you're using a string or a vector you definitely cannot call those from a signal handler。

嗯。And to explain what's happening here why this locking is so problematic。

 let's say that you're in the middle of printing something really long inside of main and so you get past line 1311 and you've acquired this lock on the file you set the bit that says this file is locked。

 please don't print the standard out right now and then just after that the signal arrives and you go to the signal handler and now you start running printf inside of the signal handler well what this printf do。

 it runs this exact same code so it gets to line 1311 and it tries to call F lock but the bit is already set the lock is already acquired and so printf is like oh some other process really it's the same process but it thinks some other process is printing the standard out right now I need to wait for that process to exit。

But of course， it's not some other process that's writing to printf。

 it is our process it just so happens that we interrupted it in the middle of writing to printf。

 and so you end up waiting indefinitely for this other process to finish printing， causing deadlock。

Does this make sense how this is happening？So what should we do about this。

Print app seems like such a basic thing， if we can't even print。

 then how are we supposed to handle signal handling？

If there's not much we can do in a signal handler， then that really limits our capabilities。So。

Does anyone have ideas for what we should do， how we can handle signals？

What are some creative thoughts？Take a guess。We still want to be able to print in response to a signal。

It's just that we catch't print inside the signal handler。Modify something in the process。嗯哼。😊，Okay。

 really good idea。 So instead of doing the work in the handler。

 we we intercept the signal in the handler and then we do the actual work in the main process How do we。

😊，Have that communication there。 How do we go from catching it in the handler to doing the work in the main process。

How do we indicate to the main process that it should now print Hihi not exiting？Yeah。

 you could have like a global variable that is like signigt received， and then inside your handler。

 you could set the variable and then inside of your main process you can check did that variable get set if it got set。

 then we know we received Signant and you can handle it。

If you're doing anything complex or you want to handle the multiple signals it becomes really messy。

 you need to have multiple variables set， you have to deal with unsetting the variable so what happens if somebody presses control C twice。

 you have to make sure that your code is capable of intercepting those as two separate control Cs。

 like once you in your main code， you do something in response to the control C。

 you have to reset that variable to zero and make sure that it's able to be set again so on and so forth。

There's an even more clever trick that somebody invented in the early 90s called the Se pipepe trick。

And this is a really ridiculous hack， but it works， and it's used almost everywhere now。

 What you do is you create a pipe， normally pipes are used for interprocessed communication。

 but in our case we're just going to use it for communication within our own process。

 So we create a pipe and then when we're awaiting signal So in your main function in your main code。

😊，You just continually read from the pipe， so the reads this call， if called on a pipe。

 it's going to pause， it'll sleep until something is written to the pipe。

 so it'll essentially wait for something to be written to the pipe when you try to read from it。

 and then in the signal handler when you get a signal write a single byte to the pipe。

So then I'll wake up your main code and then your main code will say，  oh。

 I got something out of the pipe， I must have gotten a signal。And if you want。

 you can write different bytes for different signals to indicate that different things happened。

 but by doing this， it's simpler than setting a single variable。

Because the semantics of like receiving multiple signals is also handled， if you write two bytes。

 then you can just read two bytes out of the pipe and you can see， oh， I got two bytes out。

 that means that two signals were received。Ugly hack。 if you're thinking this is ridiculous， I agree。

 but this is actually how signals are are typically handled。 and there is a new Linux lab。

 It's not new， but it was introduced after Posics that added support for this hack。😊。

And so what you can do is first you block the signals that you want to receive so that。

They're not handled by the default signal handlers。

And then you create this signal FD thing and what signal FD， it's basically just a pipe。

 so it returns you back a file descriptor。And then in an infinite loop。

 you just read from that file descriptor and you're reading into this buffer。

 but this buffer is a special buffer， it's thestruct signal FD SIG info。

That reads specially formatted data out of the pipe that tells you which signal you got。

So instead of just checking to see if the byte that you got was a particular number。

 you can check if the field of this struct matches a particular signal and you can handle it appropriately。

 you can say， oh， I got sant， I got se quit， so on and so forth。

 it just formalizes this self pipepe hack。And we're not going to ask you to use this。

 so don't feel like you need to understand it fully。

 but I do want you to remember that if you are doing any complex signal handling in the future。

 this is a trick in your bag of tricks that you can reach for。

And I'll talk about how this relates to rest in a moment as well。So this。

Should strike you as weird because before in your main function。

 you could have a loop that is doing something useful， like you could be computing some values。

 you could be prompting you could be prompting input from the user。

 but usually inside of your main body of code， you want to have the flexibility to be able to do something useful while having the capability to handle a signal asynchronously if you need to so like in your main body of code。

 you can be doing something productive and if a Sant comes in or a Sig childild then you can just take a pause from what you're doing。

 go handle the signal and do something in response to that and then come back and resume your productive work。

But it seems like with the selfpipe trick and with like setting a flag or something。

 it seems like that kind of removes that potential for concurrency right inside of your main code。

 you can either be doing work， which means that you're not going to be reading from the pipe。

Or you could be reading from the pipe to wait for a signal。

But you can't do both at the same time because those two things both involve using the CPU for something and you can't do both at the same time。

 All， Does this make sense to people， thumbs up， thumbs down。So this should seem frustrating。Because。

Signal handling gave us a tool， and this feels like it's taking that tool away。

So how can we address this There's two ways that this is commonly addressed the first way is to use threads so what you do and I'll note that threads can still have concurrency problems。

 but when you use threads we have more tools to reason about and to control those concurrency problems and I'll give you a concrete example in a moment。

So when you're writing multi threadreaded code， you have tools available like locks， like semaphoes。

 like condition variables， if you're in 110 right now。

 we haven't talked about all of these tools yet， but you'll see them within the next week。

And if you are using signal handlers， you don't really have many tools available the only tool that you have when you're doing signal handling is to block a signal。

 you try to prevent this other asynchronous body of code from running。

 but you don't have tools to elegantly control two things running at the same time。

The other option for addressing this is to use a tool called nonblocking IO。

 which is also extremely common in something that you should know about。

 and this is something that we'll talk about in week eight。

So I promised that I would explain how this relates to rust and how signal handling is done in rust Sign handling is not built into the core rust language。

 I think the rest designers realize that signal handling is a messy business it's easy to shoot yourself in the foot Ru has a lot of problems on a tent that is trying to solve namely memory safety and they said let's defer this issue。

 we're not going to address it yet if people need signal handling will defer to external crates but we won't provide it as part of the core language So if you want to use signal handling you have to use rust libraries of which there are several。

So rust has something called a control C crate， it's a library that allows you to run a function whenever control C gets received。

 whenever second is received， seems like pretty reasonable functionality。How does this actually work。

 so first it creates a self pipe。Then it installs a signal handler that writes to the pipe when signigant is received。

And then it spawns a thread。And that thread is extremely simple， all it does is in an infinite loop。

 it tries to read a byte from the pipe， remember that waits it blocks if nothing is inside of the pipe。

 and then when it gets something out of the pipe， it just calls the signal handling function that you registered that you want it to be called。

Okay。So it's actually very simple and this crate is extremely easy to use and it has the benefit that rust already has very good controls。

 we'll talk about this a lot next week， but it already has very good controls to ensure that you don't have race conditions when you're using threads。

And so rest is like， okay， you know， you don't even need to understand threads to understand this because you already understand the borrow checking rules。

 and what do the borrow checking rules enforce that no two places in the code。

Can use a variable when at least one place is modifying it。

 And that's really what causes race conditions。 is somebody is modifying data while somebody else is trying to use it。

 And the rust Bchecker already prevents that。 So with this setup。You can't have concurrency problems。

 you can't have data races in your code。And you might be asking like， okay， well。

Like this is still concurrency， right？We have threads versus signal handlers。

 how is using threads different from using a signal handler。

 like it still seems like you're calling printf from two places at the same time。

 can't you still have problems？And to make this really concrete。

 let's explain what is wrong when you call signal printf from a signal handler。

 So you call printf from the main body of code， and it locks the file descriptor that is standard out。

And then the signal handler gets called， and this is in the middle of printf running。

 and the printf from the signal handler tries to lock that file descriptor。But it sees that。

That bit is already set to one， indicating that a process is in the middle of printing。

And so it waits and the signal handler can't continue until the main code says， okay。

 I'm done printing。But the main code can't finish printing because the signal handler is running。

And so that we get a classic deadlock here。This is different from printing from a thread because threads are scheduled differently。

 so the printf is called from the main thread and then the signal handling function gets called so it writes to the selfpipe that causes this other thread to wake up and that other thread now calls printf。

While this other thread， the signal handling thread， is like， oh。

 some processes already printing right now， I can't print。And it waits。So it gets blocked。

And because it's blocked， that means the operating system scheduler is free to schedule a different thread。

And so it schedules the main thread， it schedules print up from the main thread。

 which now goes and it finishes printing， and now the signal handling thread is free to do its print。

Does this make sense how this is different？And to make this more oh and if you're dealing like with memory allocation。

 I mentioned that this is a danger as well， it's the same deal here。

 they have protections built in there as well。 I could interject something quickly。

 I literally had the same issue with Malek like just last night I tried to mall something when interrupts were disabled and bad things happened and I realized that I shouldn't have done that。

Yeah， so don' don't mallic inside of a signal handler So to make this more clear。

 you still have concurrency problems in both threads and signal handlers and that's very important to recognize。

 but because the scheduling is totally different the results are often very different。

 So when threads you have multiple equal priority threads of execution that you constantly switch back and forth between on the processor。

😊，You can use locks to protect data， we haven't talked about locks in CS110 yet。

 but we will in a week。With signal handlers， the handler completely preemps all other code。

 So if you have anything running doesn't matter， drop what you're doing。

 jump to the signal handler and the signal handler is going to run until it finishes because of that you can't use locks you can't use any other synchronization primitives The only thing you can do is to disable signal handling In fact you should not do anything that causes blocking it is signal handler you should not call read in a signal handler you should not call weight PID with W noh in a signal handler you should not call sleep in a signal handler Why is this important Why should you avoid blocking inside of a signal handler。

Does anyone know？It's less about getting called multiple times。

I think there may have been an example in CS110 where they called W PID with without W noHang in the signal handler and what happened？

Yeah， kind of， because the signal handler hogs the CPU until it finishes。

It means that you can't run any of your other code。

 like if you have more code in your main function that was supposed to continue doing things。

Sigical handlers are supposed to be a quick interjection， you're doing something， something happens。

 quickly you jump over， you respond to it and then you jump back to what you were doing before。

But if you block inside of a signal handler that's not going to happen。

 you're going to jump to the signal handler and you're going to stay in the signal handler until that function exits。

And that's problematic because if you needed to get back to what you were doing。

 you're not going to because you're blocking， you're stuck in the signal handler。

And that's why you can't use locks because it causes deadlock， like we saw in printf。

 you're doing something that acquires lock， jump to the signal handler， try to acquire the lock。

 and you have deadlock。Because of this， and this is the most important bullet point on this entire slide。

Signal handlers play very poorly with library code。

 you can successfully write code that uses signal handling if you write all the code yourself。

But if you try to use libraries with your code， everything falls apart。

 and I consider printf to be a library， it's part of GlibBC。

Libraries don't know what signal handlers you have installed。

 and they don't know what your signal handlers do。So in your code， you have a global and you're like。

 okay， I'm touching this global here and I'm touching it in the signal handler when I'm touching it down here。

 I'm going to disable signal handling so that I don't have a race condition where it's accessed in two places at one time。

Libraries also use globals， but they don't know about your signal handlers。

And so they don't know that they're supposed to disable your signal handler in order to avoid a race condition。

 even if they did， it would be pretty bad if library is just started arbitrarily disabling your signal handlers because you would have arbitrary behavior that would be very hard to debug。

So libraries can't disable signal handling to protect themselves from concurrency problems。

And if you use libraries with signal handlers， you will end up dealing with issues like this in your signal handler you should only touch code that you can control or call library functions that have been marked explicitly as safe to call from signal handlers。

Because libraries don't know about your signal handlers and they don't know what bad things could happen if your signal handler gets called while in the middle of library code。

Does this make sense to people？

![](img/14cbbbe339881052b6207b5da6debf13_11.png)

Okay， so long story short。Try to avoid signal handling when you can if you're doing something very simple that is fine to do it inside of a signal handler。

 but anything complex should be moved outside of a signal handler and you can use that selfpipe trick to handle it or just you know real simple just use library and that's what you'll do in rest。

So I took way too much time talking about signal handling， but in the remaining 10 minutes。

 I'll talk about Google Chrome and you should be able to look through these slides on your own if this is something you're interested in and you want to see more material that we end up not getting to。



![](img/14cbbbe339881052b6207b5da6debf13_13.png)

So。Processes are fairly isolated， and I'll start by just talking about processes versus threads。

 processes are pretty isolated。 The only way that you can communicate is by sending data to each other using pipes or by throwing signals at each other。

 and signals don't really have much data like you just I sometimes call this like just throwing a fruit at a different process like you throw a strawberry at the other process Other process like oh I got a strawberry。

 I don't know where it came from， I don't know why I don't know what data is associated with it。

 signals don't carry any associated data It's just like， oh。

 well I got that kind of fruit and maybe they know what to do with a particular kind of fruit but there's no message that's getting passed besides the signal itself。

Threads are different。So threads are also multiple independent threads of execution similar to processes。

But they share memory and they share the file descriptor table and they also share some other resources as well。

 so they live inside of processes， they have their own stack for their own thread of execution and they have their own registers similarly to support their own thread of execution but they share memory besides that and really under the hood what's happening is。

You still have similarstructs to processes， but there are references saying that if you want to use memory in this thread。

 this is where you should look， you should use this processes's virtual address space。Okay， so。

With that in mind。What are some things that would be important when we're designing a browser？

I was going to have us discuss this， but for the sake of time。

 these are the ones that I came up with。 You want a browser to be fast。

You want it to not use too much memory， if it uses too much memory。

 your computer can end up slowing down， it won't work very well on low end machines。

 so on and so forth。You want it to be efficient with its CPU usage， if it uses a lot of CPU。

 especially on laptops， this will be really bad because it will deplete your battery。

You need to actually be able to build it， nobody cares if you have a great idea for a browser。

 if you can't actually implement it。😡，And lastly， it needs to be secure if you want a user to be able to browse to some shady。

 like MP3 torrenting website， some like knock off Spotify and also to be able to go to their bank account and to not have malicious code from one one website compromise。

Very important information from some other website。

So how does threads versus multiprocess play into this？Let's talk about speed。

M threadreading or multiproces， Anyone have a leaning for speed？Why is that？Exactly。Yeah， so oops。

 them going to the wrong， wrong way。 So when you switch between processes。

 you have to change the virtual address space that is being used。 and that's actually。

Somewhat expensive， you have to erase the processor's cache and then install some new virtual address mappings and it's not cheap to do that by contrast threads are using the same virtual address space so it is easier to switch between different threads of the same process than it is to switch between different processes。

😊，So for speed， I'd say they're probably pretty similar but slight advantage to multi threadreading。

 what about memory usage？Why is that？That's exactly right。 They're sharing memory。

There whereas if you create multiple processes， every process has to have its own memory。

 It's a little more nuanced than that， but that's the basic idea。 And indeed。

 if if you fork a bunch of processes as opposed to spawning a bunch of threads。

 you will use more memory for the processes。 What about CPU usage。Yes。

 so same reasons as the previous two， you don't have to copy as much data when you are creating the processes and also when you're switching between the processes。

 the contact switching is less expensive。So advantage multi threading。

 what about ease of development？Like being able to actually build the browser。

Huge advantage multithreading for anyone who started farm on assignment 3。

 you know this if you have this much difficulty just passing numbers between processes。

 imagine how difficult it is to build a browser that has to pass a lot of different kinds of information between processes。

Definitely advantage multithing， what about security and stability？That's exactly right。

And this is the one bullet point here where the advantage definitely goes to multiprocessing because and it's specifically because they don't share memory。

 if you have a bug in one of these threads of execution and you're using multithreading and that bug ends up corrupting memory somewhere。

 you've now corrupted memory for all of your threads。

But if you have a bug and you trash memory in one process in a multiprocessing scenario。

 you've only trashed the memory for that one process。

 you can't the operating system will prevent you from trashing the memory of a different process。

And because of that。That means that sure， you may have a bug that crashes one process。

 but at least all your other ones are still going。 You haven't put all your eggs in one basket。

And this is the sole reason， I think。That Chrome ended up deciding to build its multi processingces architecture。

 right， all browsers prior to 2006 were single process multi threaded applications for these four reasons。

 These are These give pretty obvious advantages， especially ease of development towards building a multi threaded browser。

 but Chrome said。You know what we feel that and I'll just show you the quote。 Oh man。

 is this was fun。 So I was gonna make the point that browsers are so complex they gave you storage APIs。

 you can have concurrency APIs。 you can communicate with hardware。

 You can plug in a MIi keyboard to a computer and access it through Google Chrome you can run assembly code。

 you can even run Windows 95。 and this was just too good not to show。

 So this is Windows 95 running inside of an emulator that was written in C and compiled to webassely。

 and you can literally like this works。 This is the original Windows 95 code。

 This is not somebody that created some some mock or some like fake version。

 This is actually the original disk image and this is ridiculous that you can do this and these things are extremely complex。

😊。

![](img/14cbbbe339881052b6207b5da6debf13_15.png)

![](img/14cbbbe339881052b6207b5da6debf13_16.png)

And because of that complexity， it makes it very difficult to implement correctly。

 And the Chrome designers said if I can get this to go to the next slide， which I can't。



![](img/14cbbbe339881052b6207b5da6debf13_18.png)

Why does it make me do this？

![](img/14cbbbe339881052b6207b5da6debf13_20.png)

They said it's nearly impossible to build a perfect browser that never crashes and never never hangs。

 We're always going to have vulnerabilities and all it takes is one browser plugin like one tab to bring down the entire browser and all tabs that are currently running。

Moderate operating systems are robust because they have isolation。

 because they partition resources and isolate processes from each other。

 so if you have one application that crashes， it doesn't bring down the entire computer and we need something like that for the browser too。

On a different page， they gave a lot of reasons that should remind you of what we talked about in the very first lecture of this class。

They say that determined detectorers are always going to be able to find ways to hack a process to break out of a process。

 are there were a lot of exploitable bugs in the past and this is despite our best efforts we spent years of investment in in trying to teach people how to write better code fuzzing is an approach where you just throw malform to data repeatedly at an application to until you find things that make it crash vulnerability reward programs our bug bounty programs。

 we pay people to try to hack our browser and to try to find problems with it and despite this we still find so many issues and。

We're not even sure that we found all of them。 like these numbers are only the bugs that we know about。

 but we also know that there are a lot of bugs for sale on the black market。

And bugs are often exploitable。 We talked about this in the very first lecture how you have a one bite buffer overflow and it turns into an exploit。

 and we haven't talked about this in our class， but there are techniques for preventing the damage caused by buffer overflows and they don't always work。

So they basically said， you know what， we've thrown everything we know at this problem and we still have issues。

 we really need a better isolation model so that if we have bugs in one process。

 it doesn't affect other tabs that are running in the browser or the browser itself。As an aside。

Does anyone know where rust comes from？Ruth comes from Mozilla。Which makes Firefox。

And Firefox's approach has been， has been a bit different。 They said， you know what。

 instead of trying to isolate these issues with processes， Can we try to fix these issues。

 Chrome basically said we can't fix the issues。 We've tried really hard and we can't fix all of them。

 Mozilla said， let's try to create an approach where we create less issues。

 And they built rust for Firefox。 That is why Ru exists。

 because this is their attempt at trying to create a language where we。

 we can't introduce these issues。 Neither approach has been successful yet。 By the way。

 Chrome still has bugs。 Firefox， there are vulnerabilities and rust too， and you can。

 you can have issues there too。 It's fairly new。嗯。I'm going a little bit over time。

 but just very quickly， this is basically how Chrome uses processes。

 so there's one main browser process and it renders what is called the Chrome of the browser。

 It's the part that appears on the top like the tab controls and everything and it has multiple threads inside of it that manage the UI that make network requests so on and so forth。

And then every tab has a renderer process that renders the page inside of that tab。

And so if you go to some untrusted website that runs in one process。

 you go to your bank in a different tab that runs in a different process。

 there's this really good article that I linked here that has these fantastic illustrations but actually has a pretty decent technical overview as well of what's going on here。

And the core of it is that it uses these things called so it does this isolation。

 and then it uses pipes to manage communication between the processes。

So it sends messages through these pipes and Chrome doesn't use signals for handling events because signals don't carry enough data。

 say that somebody presses a key on the keyboard， you want to inform this render process that hey。

 somebody pressed a key on the keyboard but if you send a signal you won't be able to send any associated data like oh it was the letter A that was pressed on the keyboard and we talked about how signal handling has so many problems and so they just don't use signal handling at all。

 they send messages over these pipes saying oh hey， letter A was pressed on the keyboard oh hey。

 somebody pressed command W so on and so forth。And that's basically how this works。

 I've got a couple more slides in here that talk about some of the work that Chrome did in the last five years。

 like this was their model starting in 2006， but a lot has happened since then。 and in particular。

 there was this initiative called the site isolation project that took four years that in which they used more multiprocessing。

 They said， you know what， we already used multiprocessing， but it's not good enough。

 we need more isolation and it was a huge initiative that was very important。

 So if you want to read about it you can check out the slides。😊，Turns out that with this setup。

Vulnerabilities are still possible， they still happen。

 but they usually involves stringing together a lot of bugs because first of all you have to break out of this process。

 then you have to get into this process， then you have to get into some other process and attackers have to find ways to like wiggle out of this isolation setup so if you want to read about that there are some interesting links here and then this is just a small tidbit that's not very important but we talked about how not to call fork last class and our approach actually causes some problems with Chrome so you can check out this link to see how they handle forking if you're interested。

So apologies for going over， but that's all I have for today。

 if you have any questions about any of this， I think it's really interesting and I would love to talk about it on Slack。

😊，But yeah， thanks for coming and we'll see you on Tuesday。



![](img/14cbbbe339881052b6207b5da6debf13_22.png)