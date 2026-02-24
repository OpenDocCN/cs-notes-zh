# Quantum Leaps《现代嵌入式系统编程Modern Embedded Systems Programming》中英字幕 p26 -26-#25 RTOS Part-4_ Efficient blocking of threads.zh_en -BV1fRt2efEms_p26-

![](img/c7020f795e8a5b3d5ff5e77d2f6baa0f_0.png)

Welcome to the moderndern embeddedded Systems programming course。

My name is Mirosec and in this fourth lesson on Realtime operating system， Arts。

 I'll show you how to replace the horribly inefficient polling for events with efficient blocking of threads。

 specifically in this lesson you will add a blocking delay function to the Miros Arts and you will learn about some far reaching implications of thread blocking on the Arts design。

🎼The。As usual， let's get started by making a copy of the previous lesson 24 directory and renaming it to lesson 25。

Get inside the new Lesson 25 directory and double click on the Microvission Project lesson to open it。

To remind you quickly what happened so far， in the last lesson you brought the Miros artist to the stage where it can run fully autonomously。

 performing simple roundroing scheduling of your threads。However。

 the threads still use a primitive polling inside the BSP delay function。

 The brain that' polling inside BSP delay is horribly inefficient Waste of the CPU cycles that could be put to a better use somewhere else。

But how could you eliminate this waste？ Well， you have now a new tool in your toolbox。

 which is the context switch With this tool， you could approach a delay function completely differently。



![](img/c7020f795e8a5b3d5ff5e77d2f6baa0f_2.png)

Instead of starting a brain deadad polling loop at the beginning of the delay。

 you could switch the context away from the thread and then switch the context back to it at the end of the delay。

 In between those two context switches， the thread will be very efficiently blocked。

 consuming no CPU cycles at all from the perspective of the thread。

 the blocking delay will be no different whatsoever from the polling delay。 Either way。

 the thread will simply call a delay function which will not return until the delay eappsses。



![](img/c7020f795e8a5b3d5ff5e77d2f6baa0f_4.png)

![](img/c7020f795e8a5b3d5ff5e77d2f6baa0f_5.png)

![](img/c7020f795e8a5b3d5ff5e77d2f6baa0f_6.png)

But from the perspective of a system as a whole， this would make all the difference because now the CPU cycles between the two context switches will be available to other threads that actually have something to do。



![](img/c7020f795e8a5b3d5ff5e77d2f6baa0f_8.png)

From the description so far， it should be clear that such a blocking delay implementation must become a part of the Arts because you need the scheduler and the context switch as part of the Arts then the blocking De operation will be called the OS De function。



![](img/c7020f795e8a5b3d5ff5e77d2f6baa0f_10.png)

At this point， I'd like to call your attention to an interesting and important trend。

 which is migration of functionality such as delay in this case。

 from the application to the system level software， where it can be handled much more efficiently。

 You will encounter this trend repeatedly as you learn about more advanced software techniques that I'll cover in the future lessons。

But before jumping into the implementation of the OSD function。

 you need to realize one important property of a blocked thread to see this better。

 you need to use a timing diagram with all context switches that are happening。

 but which I have omitted for simplicity so far。

![](img/c7020f795e8a5b3d5ff5e77d2f6baa0f_12.png)

![](img/c7020f795e8a5b3d5ff5e77d2f6baa0f_13.png)

![](img/c7020f795e8a5b3d5ff5e77d2f6baa0f_14.png)

As you can see， a thread running a polling PSP delay function participates in the round robin scheduling。

 meaning that sometimes the thread is scheduled in and sometimes it is scheduled out。In contrast。

 a thread that is in the blocked state should never be scheduled in。 It simply is not ready to run。

 This means that your art's threads have a new property which tells the scheduler whether a thread is ready or not ready to run。



![](img/c7020f795e8a5b3d5ff5e77d2f6baa0f_16.png)

![](img/c7020f795e8a5b3d5ff5e77d2f6baa0f_17.png)

One other way to visualize this property graphically is through a state diagram。

 I will introduce state diagrams more formally in the future lessons about state machines。

 but today I just want to show you a diagram depicting the life cycle of a thread。

When a thread is first created， meaning that you allocated the OSs thread object and the stack for it。

 it becomes dormant shown here as a rounded corner rectangle。 In this state。

 it cannot do anything until you have called the Os thread start function on it。 After that call。

 a thread looks exactly as though it was preempted by an interrupt。

 So it transitions to the stage of its life cycle shown as preempted。Finally。

 when the thread is scheduled for running， it transitions to the running state。 After a while。

 the thread gets scheduled out and another thread gets scheduled in at which point the original thread becomes preempted again。

Please note that in the single CPU system， exactly one thread can be in the running state at a time。

 which is shown here as a circle with number one in it。But now。

 a running thread can call the O S delay function at which time it becomes blocked。

 meaning not ready to run。 Now， let's think for a minute about the transition out of the blocked state。

 which must happen at the end of the delay。 This needs to be managed centrally for all threads by the arts。

 obviously， because a blocked thread cannot do anything。 and in particular， cannot unblock itself。

This central auto service will need to be activated periodically。

 typically from the system clock tick interrupt， and therefore will be called O S T。

 Upon every activation， O St needs to update all delays of the individual threads and needs to unblock the threads whose delays have elapsed。

An interesting observation now is that if a thread is not ready in the blocked state。

 it must be ready in the preempted and running states。

 This can be shown graphically by means of the ready superstate encompass encompassasing those two states。

 and indeed， while in the ready superstate， which means either in preempted or running。

 the thread is ready and willing to run， except sometimes it needs to be preempted to share the CPU with the other threads that are also ready and willing to run。

😊，The not ready to run property of the new blocked state in the thread life cycle has also another interesting consequence。

 and that is that the system of blocking threads is incomplete and necessarily requires one special thread that is always ready to run and cannot block。

To see this， consider a system with two threads like your Blinky1 and Blinky2。

As long as both of them are in the ready superstate， the scheduler can run one or the other。

When one of the threads goes to the blocked state， the scheduler can still run the other thread。

 But what if both threads become blocked at the same time。

 the CPU still must be running exactly one thread at a time， but none of the existing ones are ready。

The solution is to add another special thread， which the scheduler can run when no other threads are ready。

 This situation in the system is called the idle condition， and therefore。

 the special thread is called the idle thread。 This idle thread is not allowed to block。

 so its life cycle does not have the blocked state。So as you can see。

 thread blocking has surprisingly many consequences。

 all of which you need to carefully consider in your implementation。Going back to code then。

 let's start with creating the idle thread。 At first。

 the idle thread will be created exactly as any other thread。

 And only later you will add protections against it ever going into the blocked state。

So let's just go to main dotC and copy the boilerplate code for one of your blinky threads after pasting it into mirrorrals。

c， rename By 1 to idle thread。🎼う。The thread routine for the iddle thread will still have the endless super loop structure。

 but it will simply invoke a callbe function OS on IdL。

 where the application level code will be able to perform some processing。Just like any other thread。

 the idle thread needs to be started。 The most convenient place for this is O S in it。

Now the interesting part is how to supply the stack for the idle thread One option is to prelocate it in the artus。

 but at this level you don't know how much stack would be used by the OS Ile callback。Therefore。

 it is better to simply defer the idle stack allocation to the application。

 just as it is done in the OS start function。う。Oh。So now you need to update the OS in its signature in the Mis。

h header file， where you also need to add the OS on iddle Calt prototype。

When you try to build a project now， you get errors as the artist's API has changed。

To fix the problems， you need to add the stack for the idle thread to the OS in it call in main do C。

🎼う。🎼う。🎼，And you also need to define the OSs on iddle callback in BSP。c。 At first。

 let's just make the idle callback do nothing so that the project links correctly。

Moving on to implementing the centralized thread delay management。

 you need to augment the OS thread object by adding a private timeout counter to each thread these timeout counters will work as follows。

The OSs delay function will start with loading the timeode counter with the number of clock ticks。

 subsequently every clock tick will call the OS tick function。

 which will decrement all nonzero timeode counters When any of these down counters reaches0。

 the corresponding thread will be unblocked and scheduled。As you can see。

 having a separate timeout counter in each thread will allow the delays to run in parallel and independently from each other。

Of course， OST will run all the time， but all time out counters that are already zero will be simply left alone。

The next new attribute of a thread is a Boolean flag。

 which will be true when the thread is ready and false when it is not ready to run。

Putting such a flag in each thread object would be a logical thing to do。

 but it turns out that it is not optimal for the efficiency of the code。Instead。

 it turns out that it is more efficient to group the ready to run flags together in a 32 bit bitM OS ready set This OS ready set bitm will work together with the OS thread array as follows。

🎼Yeah。Each individual bit in the OS ready bit mask corresponds to a thread in the OS thread array with the idle thread skipped because it is always ready to run。

The idle thread is always at the index 0 because it has been started from OSs in it。

 which ensures that it is the very first thread in the OSs thread array， therefore。

 skipping the index 0 means that the bits of OSs ready set are simply shifted by one with respect to indexes into the OSs thread array。

For example， a threaded index1 corresponds to bit 0， threaded index 2 to bit1。

 a threaded index n corresponds to bit n minus-1， and finally the last thread at index 32 corresponds to the last bit number 31 in the OS ready set bit mask。

The various values of the O S ready set bitmask correspond to the following situations， bit 0。

1 and n-1 set mean that threads 1，2 and n are ready to run。

Only bit 1 set represents thread2 ready to run， and finally。

 all bits at0 represent the idle condition of the system。

 This situation can be checked in the code very efficiently by simply comparing OS ready set to0 in a single instruction。

The other benefits of grouping the ready to run flags together in one bitm will become clear in the next lesson where you will implement priority based scheduling。

 In that case， the bit numbers in OS ready set will represent thread priorities。But for now。

 you are still working with round robin scheduling where there is no notion of thread priority。



![](img/c7020f795e8a5b3d5ff5e77d2f6baa0f_19.png)

Going back to code， let's now modify the scheduler so that it will avoid scheduling threads that are not ready to run。



![](img/c7020f795e8a5b3d5ff5e77d2f6baa0f_21.png)

First， you quickly check for the idle condition by comparing OS ready set to0。

 in which case you set OScur IDX to the index of the iddle thread， that is to0。

 as you will see later， this will be the most frequent path through the code。Otherwise。

 if OS readyy set is do0， you have some ready to run threads。

 but now you cannot simply choose the next thread index because the thread might not be ready to run。

Instead， you need to keep going in round robin fashion until you find a non idle thread that is ready to run。

As shown in this diagram， to check if thread N is ready to run。

 you need to synthesize a bit mask that has only n minus1 bit set。

 and you need to bidwise end it with O ready set。 If the result is0。

 you need to keep going because it means that the bit is not set so the corresponding thread is not ready to run。

Also， you need to be careful to exclude the idL thread from the round roing scheduling by skipping the index0。

So here is the final algorithm。 You advance the Os curve Idx in a round drop in fashion。

 but you skip the idle thread by wrapping around to1 instead of 0。

 You keep going as long as the O ready set indicates that the thread is not ready to run。

Now you are finally in position to tackle the most interesting new service of your Arts。

 which is the blocking OS De function。🎼The signature of the function will be identical as the polling PSP delay。

🎼う。🎼Inside of this delay， you need to disable interrupts。

And store the tick count in the current threads timeout counter。

Next you need to make the thread not ready to run by clearing the corresponding bit in the OS ready set bitm。

 and finally you need to call the scheduler to immediately switch the context away from this thread so that it can become blocked。

As you remember from the previous lessons， OS SCD is designed to be called with interrupts disabledable and the context which happens right after the interrupts are reenabled。

The last touch in the always delay implementation is to forbid calling it from the idle thread because it should never go to the block state。

 You can accomplish this by adding an assertion that the current thread is not the idle thread at index 0。

 This specific assertion type is called precondition because it introduces a specific requirement that must be met before calling the service to make this intent clear。

 the Q assert H header file provides a specific macro named Q requirement。

 which works exactly like Q assert， except its name conveys the intent much more precisely。

To quickly summarize the status so far， you have implemented the idle thread。

 and you have added the blocked state to the thread's lifecycl。

 You have also just implemented the transition to the blocked state。

 This transition is unique in that it is the only one in the thread's lifecycle that is taken voluntarily by the running thread itself。

 All other transitions are forced on the thread without necessarily its corporation or consent。



![](img/c7020f795e8a5b3d5ff5e77d2f6baa0f_23.png)

This includes the last transition you still need to implement。

 which is the OST service that would take a thread out of the blocked state。



![](img/c7020f795e8a5b3d5ff5e77d2f6baa0f_25.png)

![](img/c7020f795e8a5b3d5ff5e77d2f6baa0f_26.png)

The implementation of OSt needs to loop over all threads， except the idle thread obviously。

 and decrement all non0ro time old counters， the threads corresponding to counters that just become zero need to be unblocked。



![](img/c7020f795e8a5b3d5ff5e77d2f6baa0f_28.png)

![](img/c7020f795e8a5b3d5ff5e77d2f6baa0f_29.png)

The code of Ot will therefore consist of a four loop over all threads。

 starting with index 1 to skip the idle thread inside the loop。

 you first need to check the timeout counter of the corresponding thread， and if it is not0。

 you need to decrement it。If the counter is becoming0。

 you need to make the thread ready to run by setting the corresponding bit in the OS readyy set a bitm。

Please note that this implementation assumes that OST will be called from a single interrupt service routine such as Sic handler。

 In that case， you don't need to disable interrupts inside OST because an ISR cannot be preempted by a thread。

 so any unexpected changing of the timeout counters which can happen only in OS delay is not possible。

Also， it is not necessary to call OS SC from OST because the scheduler is called at the end of Sstic handler anyway to schedule any unblocked threads。

The implementation of the blocking delay is almost ready now。

 but you still need to make some final adjustments First， any restart thread。

 except the idle thread needs to be explicitly made ready to run by setting the corresponding bit in the OS ready bitm。

This corresponds to the transition into the ready superstate in the thread's life cyclee。🎼。Second。

 you should increment the Miro's artist's version number to lesson 25， both in themrals。c。

And in Miros dot H。And third， in Miros。h， you need to add the prototypes for the newly added services OS delay。

And holistic。🎼And finally， you need to actually use the new OS De and OS T instead of the previous paing BSP De and BSP counter。

🎼こに？🎼，🎼う。🎼う。🎼The code builds cleanly。 so now I understand that you are quite keen to see how it works。

Let's then open the debugger。And at first， run the code free。W do you know。

 the code appears to be blinking all Ls exactly as before。

But now it really works quite differently when you break into the code。

 you find it in the OS iddle calledback。Indeed， when you set a break in the scheduler。🎼Yeah。🎼う。

You can see that the OS ready set bitm。🎼Yeah。Is zero。So the scheduler picks the idle thread。

All this means that most of the time all threads are blocked。

 so the system spends most of its time in the idle condition。Only occasionally。

 a thread gets unblocked and scheduled to run。🎼う。🎼The。🎼你出我。All right， as you can see。

 the idL thread has become quite important because the CPU spends most of its time there。

 so let's study it a bit more specifically， let's put some code into the OS on IdL callback。

I'll use the technique from the previous lesson to toggle a pin up and down from the OS on iddL callback so that this activity could be observed with a logic analyzer。

As I am running out of pins， I will reuse the red LED from the blinklinky3 thread。

To avoid any conflicts around the red LED， I will simply comment out starting of the By 3 thread in main。

 C so that this thread will stay in the dormant state。

When I build and load the coat to the board now， the blue and green LED blink as before。

 but the red LED only glows at a low intensity。

![](img/c7020f795e8a5b3d5ff5e77d2f6baa0f_31.png)

Now let's connect logic analysis signals D1 through D4 to pins Pf1 through Pf4 respectively。



![](img/c7020f795e8a5b3d5ff5e77d2f6baa0f_33.png)

As you can see in the logical a view， the signal D1 corresponding to the red LED keeps toggling rapidly。

 which means that the O on idle callback is constantly called The signals for the green and blue LEDs change very slowly in comparison。

 The signal D4， which is switched in the cystic ISR is used here as the trigger。 Most of the time。

 the cystic ISR takes about 3 microseconds， but occasionally it gets significantly longer。

 to investigate this behavior。 Let's look through the accumulated traces。Indeed。

 here is an instance where cysttic gets longer。Interestinglyly， at the same time。

 the greenery changes from low to high and the idle thread activity gets delayed by over 5 microseconds。

 The explanation is quite simple。 Most of the time， cysttic simply updates the timeout counters。

 but does not switch the context from the idle thread。

 You can see this directly from the idle thread activity before and after the cysttic。

Only occasionally， a thread other than idol gets unblocked and scheduled。 after the cyststic。

 the unblocked thread runs and does its stin。Such as toggling the LED in this case。 After this。

 the thread calls O S delay and voluntarily relinquishs the CPU。

 which switches back to the idle thread。 Now， regarding the actual timing。

 the longest cysttic takes about 4。5 microseconds， which is three times longer than before blocking was introduced。

 This increased overhead is caused by more complex OS stick and Oque implementations。

On the other hand， the context which time remains about the same below 2 microseconds。

 The thread blocking noise delay， which involves marking the thread as not ready and scheduling another thread takes about 3。

8 microseconds。Finally， the longest time spent outside the idle thread is only about 10 microseconds。

 in most of the cases， this time is even shorter。With all this。

 I hope to have convinced you that indeed the CPU spends almost all of its time in the iddle thread。

 except for a few microseconds here and there to execute all other threads。

But the id thread still basically wastes all the CPU cycles it gets。 So the question is。

 what can you do about it。Well， the best thing you can do is to put the CPU and its peripherals to a low power sleep mode。

 Indeed， you will never achieve a truly low power design with the CPU and peripherals running at full speed。

 So for battery operated applications， you have to use sleep modes。

The full discussion of the subject of low power design goes far beyond the scope of this lesson。

 but the most important takeaway for you today is that the idle thread and specifically the OS on idle callback is the ideal central place in the code to put the CPU and peripherals to a low power sleep mode To this end the armcortex MCU provides a special instruction called WFI wait for interrupt that shuts down the CPU clock until an interrupt occurs。

You can put it in your O on idle callback using underscore underscore Wfi CC's function and see what happens When you load this code to the board。

 you can see that the green and blue LED blink exactly as before。

 but the red LED seems not active at all。 The situation becomes clearer in the logic analyzer where you can see that the red LED actually toggles。

 but very infrequently。 In fact， it toggles exactly once after each interrupt。

This is because now the CPU gets stopped inside each call to OS on iddle and is only woken up by the next cyststic interrupt。

This concludes this lesson about efficient thread blocking and its profound implications。

At this point， your Miros Arts implements a round roing time sharing scheduler with blocking。

 which corresponds to the state of the art of computer systems in the early 1960s。



![](img/c7020f795e8a5b3d5ff5e77d2f6baa0f_35.png)

There the Comput Center at MI， which serves more than 40 New England colleges and universities。

Here is an introduction of the time sharing system at MIT in the year 1963 In addition to the routine work which takes place here。

Experimentation is underway to develop a new technique of computer usage called time sharing。

At consoles like this one， located in laboratories and offices throughout New England。

 hundreds of people will one day be able to use tomorrow's computer simultaneously。

🎼In the next lesson， you'll bring the Mirals Art into the 1970s by implementing the preemptive priority based scheduling。

If you like this channel， please subscribe to stay tuned。 you can also visit statemachine。

com/quiickstart for the class notess and project file downloads。

