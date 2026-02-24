# Quantum Leaps《现代嵌入式系统编程Modern Embedded Systems Programming》中英字幕 p44 -44-#43 Active Objects in Real-Time Part-1_ Run-to-Completion and RMS_RMA -BV1fRt2efEms_p44-

![](img/549526906f94beed2e991e33d563ad0e_0.png)

。Hello and welcome to the modern embedded systems programming course。 My name is Miro Samock。

 and in this lesson， I'd like to go back to event driven programming and active objects in particular。

😊，🎼You' have been using event driven active objects since lesson 34。

 but perhaps it's not quite clear to you what advantages they provide in real time programming。

 So this lesson ties together the concepts of event driven programming， active objects。

 state machines and real time operating system， artists。

I talked about all these concepts in this video course before。In fact。

 let's go back today to the project for lesson 27 about the Art。

Comppy the lesson 27 directory and rename it to lesson 43。

Get inside the new lesson  for3 directory and click on the project lesson to open it in the microvision IDE。

To remind you quickly what happened back in lesson 27。

 you experimented with a preemptive priority based artist kernel called QXK。

 which is part of the QPC framework。This artist was currently managed two traditional threads。

 Blinky 1 and blinklinky 2。 threadread Blinky 3 was not started and not used。

 so let's just clean it up。To understand what the threads were doing。

 let's just build and load the code to the TVC Lachpad board and then watch how it works using a logic analyzer。

The logicized the trace labeled the By1 corresponds to the blinky1 thread。

 while the trace labeled idle corresponds to the idle thread of the QX K kernel。When you zoom in。

 you can see that both threads rapidly toggle the LED lines。

 green LED in case of blinky 1 and red LED in case of the idle thread。Blinky one runs for about。

1200 microconds， after which it delays its execution till the next clock tick。

 The result is that the blinky one runs periodically every 2 milliseconds。

The idle thread of the Qx K Cor round when no other threads are running。Now。

 there is also the blinklinky2 thread started with a lower priority than blinklinky1。However。

 blinklinky2 waits on the semaphore， which is signaled when the switch S W 1 is pressed。

So let's set the trigger in a logic analyzer on the falling edge of the SW1 trace。

 because the switch is active low。Now， when you start the trace。

 you don't see anything until the SW1 switch is pressed。By the way。

 I received quite a few inquiries about the inexpensive logic analyzers。 So today。

 I am using a very cheap logic analyzer that you can get for about $10 on Amazon dot com and perhaps other online retailers。



![](img/549526906f94beed2e991e33d563ad0e_2.png)

This logic Ana works with the open source Po view software that I'm using in this video。



![](img/549526906f94beed2e991e33d563ad0e_4.png)

I've put some resources about the toolll in the video description below。

But going back to your real time project， it has been specifically designed to showcase the principles of rate monoonic scheduling RMS。

 also known as rate monoonic analysis， RM A that I have introduced back in lesson 26。

You can see here are Ms in action。 The blinky one thread with the highest rate runs at the highest priority。

 And because of this， it always meets its hard real time deadline of 2 milliseconds。

 Even if other threads are ready to run， like By 2 and the idle thread。Now。

 these were traditional blocking threads managed by a traditional preemptive priority based artuous colonel。

The main question for today is connective objects also do this。 In other words。

 can objects be compatible with the RMA RMS method to deliver provably hard real time behavior。Well。

 the purpose of this lesson is to find it out， as well as to explore other properties of active objects related to concurrency and real time deadlines。

The first step is to convert the blinky one and blinky two threads to active objects。

You've seen such a conversion before in the second half of lesson 34。 So I'll go over this quickly。

I will do the coding still manually today， although I will use the Q M modeling tool for illustration。

 the Q M model will be included in the project download for this lesson。

 so you will be able to try automatic cogen， if you like。So starting with blinky one。

 you need to create the blinky one active object class that inherits the aactive base class from the QPC active object framework。

In sea， you' do this by declaring the blinky one struck with the first member super of type Qactive。

Blinkky one active object will need a time event to replace the blocking time delay from the corresponding blinklinky one thread。

The blinky one class needs a constructor function。As well as a very simple state machine consisting of the top most initial pseudostate and just one state active。

The constructor must initialize the superclass Q active。And also。

 the time event to associate it with the active object me and with the timeout signal。

The topmost initial pseudostate arms the time event to fire in two clock ticks。

 and then periodically， every two clock ticks with system clock ticks occurring every millisecond。

 This will make blinklinky one periodic with the period of 2 milliseconds。

That topmost initial transition goes to the state active。

The state active has only one internal transition triggered by timeodeig。

 So here is the skeleton code， according to the optimal state machine implementation that I have introduced back in lesson than 39。

The action executed in the time of internal transition is the exact body of the original blink1 thread minus the blocking delay。

 of course。At this point， you can delete the original code for the Blinky one thread and move on to Blinky 2。

The By 2 active object has quite similar structure to blinky 1。So， I copy。Paste。

And replace Blinky 1 with Blinky 2 in the selected code。Brinkki，2 does not need the time event。

And also， it handles the button press event instead of timeout。



![](img/549526906f94beed2e991e33d563ad0e_6.png)

The action executed in the button present in to transition is the exact body of the original blinky2 thread。

 minus the blocking sema or， of course。Now， you can delete their blinky2 thread code。

But before deleting the By2 thread instance and the blinky to private stack。

 let's think for a minute what you need for the By2 active object as the replacement。Well。

 you need the blinky to instance。And you need an eventcu buffer。

The length of the queue must be adequate for the worst case scenario。

 but 10 events is typically a safe initial guess。On the other hand and most interestingly。

 you no longer need the private stack for the blinky to active object。

This is because the underlying QXK Art Kon takes advantage of the non blocking nature of active objects and executes them as so called basic threads。

Basic threads are run to completion activations as opposed to endless as loops for traditional blocking threads that are then called extended threads。

This allows all basic threads to use the same stack。

In a minute you will see in the logic analyse trace that these basic threads can still preempt each other。



![](img/549526906f94beed2e991e33d563ad0e_8.png)

Of course， you also need to create the event cube buffer and the instance for the Blinky one active object。

 but again， you don't need the private stack for it。

So the net result is that you save a lot of precious Ram because stacks are typically much bigger than event queuees。

Moving on， you can delete the blocking se for。And instead of the extended Blinky1 thread。

 you need to call the constructor of your Blinky one active object。Now。

 you need to tell the framework that you are starting an active object as opposed to an extended thread for this。

 you use the Qactive Start API。The signature of the parameters remains the same。

 so you leave the same priority， but you need to provide the eventcu buffer and its length。

 and you don't provide the stack。You apply analogous changes to start the Blinky2 active object。

So this would be all for main at C， but you still need to adjust a few things in the board support package。

 BP。For example， you still need to define the newly introduced event signals like button press S and timeout S。

For this， open BSP dot H and declare an enumeration for the signals。Remember that in QP。

 the signals cannot start with 0， but must be offset by Qusic constant。Also。

 instead of the semaphore， you will be posting events to your active objects。

 and for that you'll need global pointers to them。You still need to add the definitions and initializations of the global active object pointers in main dot C。

And also， you replace the signaling on the samaphore with posting an immutable button press event to the Blinky2 active object。

 just as you did it for the time bomb project in the previous lessons。This should finally be all。

 so let's try to build the code。Okay， the problem is the missing definition of the loop index that was dropped during copy and paste。

All right， the code builds cleanly， so let's load it to your TVC Lapad board and see how it works。

Well， it works exactly as before with the traditional threads。Specifically。

 pressing the button causes blinky2 to run as before。

 but Blinky  one keeps running completely undisturbed and meets its hard well time deadline every time。

This is because blinky one， having higher priority， freely preempts blinky， too。

So even though Blinky， too， does all its processing in run to completion steps。 still。

 it is preempted by blinky one multiple times。But this is entirely fine because Blinkki2 eventually completes its run to completion step before handling another button press event in the future。

This illustrates the most important point of this lesson。

 The run to completion execution semantics of active objects and state machines does not mean that the state machine needs to monopolize the CPU for the whole duration of the run to completion step。

Under a preemptive kernel， such as Q X K， random completion steps in active objects can and will be interleaved in time。

This is handled entirely by the underlying real time kernel。 So if the kernel is preemptive。

 Act objects can preempt each other and can meet hard real time deadlines。

 just as the traditional threads did。What that means that active objects with state machines。

 when combined with a preemptive priority based real time kernel。

 are as suitable for rate monotaonic scheduling R M as the traditional extended threads。Actually。

 active objects are even more suitable for hard drill time and for the RMS S method in particular。

 because they don't share resources and instead use asynchronous events。

But this is such a critically important aspect of active objects that it deserves its own lesson。

 and this is exactly what I will explain next time。If you like this channel。

 please give this video a like and subscribe to stay tuned。 You can also visit statemachine。

com/vide course for the class notes and project file downloads。🎼Finally。

 all the projects are also available on Gitthub in the Quantum Lis Repoitory modern embedded programming course。

Thanks for watching。

![](img/549526906f94beed2e991e33d563ad0e_10.png)