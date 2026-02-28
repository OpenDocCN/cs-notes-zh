# 加州大学尔湾分校《Go语言编程｜Programming with Google Go》中英字幕 - P61：5_模块3 2 1 第2版.zh_en - GPT中英字幕课程资源 - BV1ggpcevEJf

![](img/ecc189bdf4a727958701cd304373b376_0.png)

Module3 threads and go， topic 2。1， basic synchronization。

So synchronization is when multiple threads agree on the timing of an event。

 okay so you have these global events， synchronization means you synchronize on these global events whose execution is viewed by all threads at the same time。

 so they can agree on the timing of this particular event。



![](img/ecc189bdf4a727958701cd304373b376_2.png)

Now， why this is interesting is because in threads using threads and go routines or basically threads。

 So when you're using go routines， they typically one go routine doesn't know anything about the timing of its neighboring of a fellow go routines。

 So if a go routine is executing some code， it knows what line of code it's at。

 it doesn't have any idea where what line of code the other go routines are at and it doesn't care because for the most part。

 because they are largely independent， not completely and we'll get to that， but largely independent。

 So normally these go routines don't have any understanding of of the timing going on in the other go routines。

 But synchronization basically breaks that。 Synchronization says， look。

 we're gonna make some kind of a global event that every thread sees or every go routine sees at the same time。

And these are important to restrict ordering restrict some of the different interleavings that are possible so let me give you got this small example here where where ordering relative ordering between two different go routines or two different threads in this case are it's actually very important and so it's important for them to synchronize on certain events so just to explain this picture I got this on the left I got a left column and a right column got two little tables right on the left column on the right column left column is one simple thread and it doesn't do much it two instructions。

 x equals1 x equals x plus one very simple and then on the right it just that thread just does one thing print X。

Now， what I'm showing here in these two different tables， one the top one on the bottom。

 I'm showing two different possible interleavings of the instructions。

And there are other interleavings， but I'm just showing two。So in the top one。

 the print X happens after the first instruction on in the left thread。

 but before the second instruction， so if you print x at that point。

 x is going to equal 1 where if you look at the bottom you got this time in this interleaving。

 the print X happens after the second instruction on the left thread。

 so at that point x is going to equal 2。So what I'm showing you here is basically a race condition where the output。

 the print， what's printed， is going to depend on the interleaving of the instructions okay？

And the interleaving remember is not deterministic。 It is determined or when I say non deterministic。

 In reality， it is not nondeterministic。 there is a go runtime schedule。

 There is an operating system scheduler， and they are deterministic programs。

 but from our point of view， it is non deterministic because we don't understand their algorithms。

 we don't know if weird things like interrupts are happening and things like this that can alter the scheduling。

 So from our point of view， the scheduling is non deterterministic。 So we don't know as a program。

 we can't tell which one of these two interleavings。 itll it'll execute。

 And remember every time it might run a different inter leaving one time might run the top。

 one time it might on the bottom and so on。😊，Now let's say so we have to understand in order to understand what the correct operation of this little program is。

 we have to know what the intention of the programr was。

 so let's assume that you want to do the print you want the print occur after the update of x after the x equals x plus1。

 so that means the bottom interlaving is okay， but the top one is bad。

So but remember that since we have no control over their relative ordering that's all up to the scheduler。

 we can't control which one of those two happens。 Well。

 synchronization allows us to control that okay synchronization。

 we're going to use synchronization to make it so that the top interleaving is impossible right and in order to do it。

 we need some kind of a global event some sort of event and there are lots of different forms of this which we'll get into in later later modules but。

We need some sort of a global event that both of these threads see happening at the same moment。

 and then we can have condition execution。 We can say， one of them can say， look。

 if this event happens， then I execute else， I wait， something like that。

 So let's show that right here。 So here's my simple synchronization example。

 I got those same two tasks。 the task one on the left。 It just does the x equals  one x x plus1。

 test2 on the right。It does the printex， but notice I'd got this global event now。

 So I didn't specify what the global event is。 We'll get to that later。 But in task 1。

 after doing x equals1 and x equals x plus1， it executes this global event。 Okay， whatever it is。

 So that event is seen by all task or all threads， including task number two。And in Testament two。

 it says if global event has happened， then print X So what happens here is that that print X in task2 can't happen until the global event has happened in task one。

So that has restricted away some of the possible inter leavings Now the print X has to wait until after x equals x plus1。

 right you can see that x equals x plus1 has to happen first before the global event and print X has to happen after the global event。

 and so the ordering is restricted。So this is an example of synchronization。Now。

 we need this synchronization in an example like this because because of our intent。

 we needed this printex to happen at a certain time relative to the printex in the task too。

 it has to happen after certain instructions in ask one and there examples like that actually we'll come up with more of these examples in a later module。

 but there's many examples like that where certain events have to happen in a certain order。

 Now notice that this is。The opposite of concurrency， right？ So concurrency。

 sort of the beauty of concurrency and parallelism is that the interleaving is arbitrary In fact。

 it's parallel， things can run at exactly the same time。

 But even it's not parallel is just concurrent， the ordering is arbitrary。

 We don't care about the ordering。 and that gives us a lot of advantages。

 allows us to speed up the execution of the code like with concurrency。 if thread is ever waiting。

 blocked waiting， then since the order doesn't matter。

 the scheduler can just move in another thread in the meantime。

 while the first one's waiting So we get a lot of optimization。

 a lot of speed improvement because we're not restricting when we don't restrict the scheduling。

 But by doing this by using synchronization， we are restricting the schedulecheduling So understand that every time we use synchronization。

 we are reducing the efficiency。 reducing the amount of possible concurrency。

 So we're reducing the options for the scheduler So the scheduler won't be able to use the hardware as well as effectively。

 So there might be times when nothing can execute because we're waiting。😊。

These synchronization events so thats so in general。

 synchronization you know it's bad because it reduces your performance and your efficiency in general。

 but it is necessary for cases like this where you have to restrict the ordering certain things have to happen in certain orders there are a lot of tasks with that the case and will bring up more examples like that。

 So synchronization is necessary necessary evil and I also mention that it is complicated to use it can be although go Goling makes makes it pretty easy it has pretty straightforward constructs so it's easier to use in than it than it might be saying in P threads or something like that but anyway just this is an example of synchronization it is bad but necessary。

Thank you。Module 3， threads and go， topic 2。2 weight groups。

So weight groups are a particular type of synchronization that are common。

 so we're going to start talking right now we'll talk a little bit about the sync package sync package you have to import that。

 but sync package it includes weight groups weight groups are useful for synchronization we're going to cover other parts of the sync package later but right now let's use weight groups just to deal with the problem that we were dealing with earlier about the main ending early before the go routine that the main started gets to finish。

So。So the package has a lot of different synchronization functions built into it synchronization methods。

 but syncnc dot weight group， what that does is it forces a go routine to wait for other go routines so a weight group is a basically a group of you can think of it as a group of go routines that your go routine is waiting on and your go routine will not continue until all those ones that are in the all the go routines in the weight group until they've all finished。

😊，So this is what we need for for the example that we had before。

 remember that print a message and then I had the new go routine print message and the new go routine message never got printed because the main go routine executed and completed before the new go routine had a chance to execute and then that force the new go go routine to exit and it never got to finish so what we want to do is make this main go routine wait until the new go routine that is created until that finishes until that exits。

 then the main go routine can continue and in that way。

 we make sure that this new go routine has a chance to actually execute before the main go routine completes So that's what we want。

 we want to have a go routine， in this case， our main go routine。

 we want to wait on another go routine。 Now weight group is a general function。

 general set of methods general object with a method that Elija set our methods associated with it。😊。

You can wait on a lot of different go routines if you want to。

 so you can have one go routine waiting on 10 different go routines and wait till they all complete in our example。

 we're only going to wait on one， but understand this is generalizable so you can wait on as many as you want。

So this sync dot weight group object， it contains an internal counter often called a counting semopho。

 but just think of it as a counter， starts off at zero， okay。

You increment the counter for each go routine you want to wait for。

 so if there are three go routine you want to wait for， you increment the counter three times。

 so make it three。Then you decrement the counter when each go routine completes so if if the counter is up to three you're waiting for three every time a go routine completes。

 it goes down from three to two， two to1，1 to0 Now the waiting go routine is waiting for these three。

 it can't continue until the counter is down to zero。

 which means that all the different all the different go routines have all completed that's the idea。

Of how the S W group。Object works。 and it's got a set of methods associated with it that allow this to happen。

 So let's take a look at at something like what it does。 So in this case。



![](img/ecc189bdf4a727958701cd304373b376_4.png)

I'm I'm trying to depict two things on the left the left sort of column there label their main thread that blew up vertical set lines。

 that's the main thread。 and then the right is this F thread。

 which is the new go routine that the main go routine has created Okay so I'm just showing a little bit of the code execution。

 Actually first let me let me go down to the bottom and name these methods that are associated with weight group。

 So we understand what they do。 So there's an a method， a done method and a weight method。

Add method increments the counter Okay， so remember I said there's this counter and you increment it once for everything that you want to for every go routine that you want to wait for。

 So add does that so you can say add pass an argument three， it'll add three to the counter。

Now done decrements the counter， okay so done is what's executed at the end of each go routine。

 each one of these go routines that the main go routine is waiting on。

 they need to execute a done at the end to decrement that counter back down。

And then once all of them have decmented the counter down to0。

 then the weight will continue so the weight is called inside the main and what will happen is that weight will block until the counter is equal to zero So if the counters equal to1 or anything greater than zero。

 that means that some of these go routines that you're waiting on are still executing which means you have to wait So it'll just block until that counter eventually gets down to zero because finally all the go routines have executed the done and then you once it gets down to0。

 the weight will the main will continue， itll go past the weight。

 the weight will complete and you can continue。So if we look at the picture now。

 I'm just showing us sort of a sketch trying to highlight the important parts of the of the routine of the main thread。

 for instance， and the food thread。 So in the main。First line up there， I'm saying I'm creating a WG。

 a variable called WG， and it's a weight group。And then first thing I do with it。

 you see highlight in red， I say weightgroupwd。ad1 because I know that I want my main thread to wait for one go routine。

 so I add one。Then I create the go routine go F， and I pass it。

 in this case I pass it the weight group now it needs the weight group because remember that the F thread。

 the new thread that I'm creating。It's got a call done on that weight group。

 right to signify that it is complete。So okay， but let's stick with the main thread for a second。

 So the main thread it creates the Fo， the new thread goF and then it calls weight。

 So it says Wg dot weight。 Now at that point itll is going to block on that line until this foo thread that we're waiting on actually completes Now then go to the right。

 the F thread。It is created。 You can see when go gofu is called， it creates a new thread。

 So you see that red vertical line right that's the new the F thread。

 So the F thread does whatever it's supposed to do。 I don't know what code it has。

 and it doesn't really matter。 So at the end， whenever it's done。

 it calls WG do done and that will decrement the weight group。

 the counter inside the weight group So now like in this example。

 I added one to the counter So the counter is equal to1。

 I added that in the main and the F thread once it's done， it decrements it by calling down。

 So at that point when it calls down the counter and the weight group should be equal to0 and then the weight。

 the Wg weight function call that was called inside the main thread that will continue that will complete。

 and the main thread can continue with whatever code it has to execute after that weight。😊。

So this is an example of how weight groups use in this case， we're only waiting on one thread。

 this food thread， one go routine， but we could wait on any number if we wanted to just by adding if we wanted to wait on 10。

 we'd add 10 and then each one now remember as a program you got to make sure to use these methods correctly so。

You got to put the Wg do ad in your main or in your go routine before you want to wait。

 and it has to be incremented to the value of which is the number of go routines you want to wait for。

 You've also got to make sure that each one of these new threads that you're waiting on that they all call done the done method on this weight group at the end when they are finished and they got to wait till they're finished it can't do it earlier。

 it's got to be so a lot of times people use a defer to make sure that it happens at the end。

 and then you've got to make sure as a programmer that in your main or in your whatever the waitinging go routine is like in this case is a main。

 but whatever the waiting go routine is， you call Wg do weight if you don't call weight。

 then none of this will there won't be any weighting going on。

 So you've got it's up to the programmer to inject the a the done and the weight at the right place to make this whole mechanism work。

So here's a little example of。Slightly modified example of that print problem that I had。

 the print assignment where I wanted the the simple version。

 I just had the main create create the the fo。 iss actually， you can see it here。

 If you look at the main function in the middle of it， its says go Fo right。

 So it creates a new go routine that executes Fo。😊，But I've added some code。

 so after that it's supposed to print main routine and the F is supposed to print new routine。

So I've added a few things like if I look at Fo Fo it prints a new routine。

 but I add this line says wg dot done right so it has to call done。

 That was the thing that I had to add。 So I add that also in the main things that I've added are I define the weight group varwg Syout weight group。

 then I save Wg do add one right so before I create the the go routine。

 I add one to the weight group。Because I know there's gonna to be the new one go routine that I'm waiting for。

 then I create the go routine with that gofo and then I call WG wait after that so that my main will actually wait on the go routine to complete and only after that F go routine has completed will it continue on and print main routine So in this way my main won't just end early and cause the Fo go routine to never complete right now the main has to it won't print it won't exit and won't print main routine until after the F go routine has already complete and done its job and print new routine。

Thank you。