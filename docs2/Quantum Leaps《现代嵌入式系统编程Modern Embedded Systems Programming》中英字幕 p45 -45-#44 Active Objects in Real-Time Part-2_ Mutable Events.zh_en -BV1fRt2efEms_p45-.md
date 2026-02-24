# Quantum Leaps《现代嵌入式系统编程Modern Embedded Systems Programming》中英字幕 p45 -45-#44 Active Objects in Real-Time Part-2_ Mutable Events.zh_en -BV1fRt2efEms_p45-

![](img/fe6be2304fdad82c9973cde8432cfb5a_0.png)

。Yeah。Hello and welcome to the modern embedded systems programming course。 My name is Miro Samak。

 and in this lesson， I continue this subject of active objects for real time。😊，Specifically today。

 you'll see how the use of asynchronous mutable events makes active objects even more suitable for hard dwell time than traditional programming with a real time operating system。

 Arts。As usual， let's get started by copying the previous lesson 43 directory to lesson 44。

Get inside the new lessonsson 44 directory and double click on the project lesson to open it in the microvision IdeE。



![](img/fe6be2304fdad82c9973cde8432cfb5a_2.png)

To remind you quickly what happened in the last lesson 43。

 you saw that active objects do not have to monopolize the CPU for the whole duration of their run to completion event processing。

Indeed， under a preemptive priority based scheduler。

 active objects with their stick machines can freely preempt each other。

 And so they meet all the requirements for the rate monotonic scheduling R M S or rate monotonic analysis。

 R M May method， which you learn back in lesson 26。

But the example in the last lesson was a bit simplistic in that it didn't include any interactions。

Neither among the original art's threads， nor among the active objects。

 After you've translated the threads to active objects。So today。

 you will make the example much more realistic by adding interactions among active objects to see how that impacts their real time behavior。

Specifically， supposed that now， after each button press。

 you want your blinky two thread to change the blinking pattern of your blinky one thread。

The first implementation Ill show you will be based on a naive sharing of global variables between the By 1 and By2 active objects。

Such sharing is precisely something that I've been trying to convince you to avoid at any cost。

But perhaps the best way to learn a rule like that is to see the consequences of breaking the rule。

So let's exactly break the no sharing rule as follows。

Let's replace the current hard coded the blinking pattern of the blinking one thread with global variables so that the pattern can be later changed。

The global variable G TX will hold the number of clock ticks for the time event。

It will be initialized with the current value of clock ticks。

The global variable G Eer will hold the number of iterations inside the B1 event handler。

It will also be initialized with a current number of iterations。But actually。

 the time event cannot be armed for periodic timeouts only once at the beginning。

 because it won't change the timeout as the global variable G takes changes。 So instead。

 let's arm the time event for one shot timeout and then arm it again after each timeout。

Now comes the sharing of the global variables in the By too。Here after each button press event。

 you want to change the global variables， G T and G Eter to some new values。

 which will in turn change the blinking pattern in a blinky one。

Such change can be accomplished in many ways， but one simple solution is to store the values in two static and constant arrays for Ts and iterations respectively。

And then to set the global variables from the arrays indexed by a private sequence counter。

To make sure that a different set of values is used each time the sequence counter needs to be implemented and wrapped around at the end of the sequence。

 Finally， of course， you need to add the sequence counter to the By2 class and you need to initialize the counter in the topmost initial transition。

All right， let's run this code in your Tiva C launchpaboard。At the first button press。

 you can see that the blinking pattern of By1 changes from fast to slow。At the next press。

 the parent changes back from slow to fast。So the code appears to be working just fine。

But I hope that by now， you can see that there is a race condition in this code。 If you don't see it。

 please rewatch lesson 20 about race conditions。But yes。

 if the button press would come just after changing G T， but before changing G Eer。

 the blinky one active object would see an inconsistent pair of values。 The new G T。

 but the old G Eer。Now， this race condition exists in a very narrow time window。

 so most likely it will escape casual testing in the lab。

But rest assured that if you shape your code in thousands of devices to thousands of customers。

 some of them will inadvertently trigger the race condition。One way or another。

 it's much better to face the problem right now during the development than to wait for the customers to find it。

So let's increase the chance of the race condition by adding some workload between setting G text and the G E。

For example， you can borrow one third of the workload from the loop below like that。

Such delay between setting variables might seem completely unnatural at first。

 but it actually can easily happen in practice。 For example。

 if the values were delivered by a serial interface。

Ceral transmission of the four Bs of G Eter would take about as much as your loop。

I want to stress it once more that the loop is not creating the problem because the race condition exists even without any loop。

 It merely makes it easier to find。But anyway， I am sure you are curious to see how a that works on your Tva C board。

Well， now， the timing of Blinky 1 is completely different。 Just after some activity in Blinkky 2。

 Blinkki 1 starts running constantly taking the whole CPU。 All right。

 I reset the board and try again。Essentially， the same thing。Now， I try without resetting the board。

So what's going on。 Well， when you zoom in， you can see that the blinky one occasionally pauses。

 which happens with two overlapping periods。Thous0 microseconds。And about 1285 microseconds。

The1000 microsecond period is caused by the cystic interrupt。

 preempting the blinky one active object。But the 1285 microsecond period is caused by the original blinky1 workload of 1500 iterations corresponding to the previous value of G Eter。

But this time， when Blinky1 finishes its run to completion step。

 the time of event is already waiting in its event queue because it was armed just for one clock tick corresponding to the new value of G ticks。

This situation causes total low cap of the under the target， which becomes completely unresponsive。

 This is a classic example of denial of service。But all this shouldn't sounded new to you because the issues related to resource sharing among art's threads have been discussed back in lesson 28。

The only new aspect here is that all this applies equally to active objects as well。Well。

 if this is the case， then the traditional solutions based on mutual exclusion should apply also。

 So let's just apply one such mechanism。In traditional threads。

 the mutual mechanism of choice is the mutics introduced in lesson than 28。

But muttics is a blocking mechanism， so it cannot be used in the non blocking active objects。

 But in the same lesson 28， you also learned about selective schedule locking。

 which is a non blocking mutual exclusion mechanism。 and therefore。

 you can apply it inside active objects。So here， around the code that modifies the global variables。

 you can just copy the QXK schedule a lock from lesson 28。Typically。

 you need to adjust the priority ceiling。 But here it just so happens that the ceiling of 5 is right because the highest priority blinky1 active object accessing the shared global variables has also priority 5。

Allright， let's test this version。As you can see， the software now works much better in that blinky one no longer overloads the CPU。

And also， the blinky one pattern changes at each button press。

 So definitely the mutual exclusion works。 But now something strange is going on with the timing of blinky one during the transient from one linking pattern to another。

Specifically， the period of the transient sometimes takes over 3 milliseconds。

 which exceeds the blinky one deadline of 2 milliseconds。

A hiccup like that might be unacceptable in a hard real time system。

But this is a consequence of the bounded priority inversion， always present with mutual exclusion。

 The whole time that the low priority blinky2 spends holding the priority ceiling lock prevents the high priority blinklinky1 from running and should really be counted towards Blinky1 CPU utilization。

Whereas CPU utilization is the critical concept in the rate monotonic scheduling method。

During the bounded priority inversion， the CPU utilization is increased。

 so the system is temporarily above the RMS S sulability bound， and therefore。

 the deadline is missed。So in short summary， you just saw some consequences of sharing resources among active objects and why you should avoid it。

 Shaing without mutual exclusion is simply wrong。 Shaing with mutual exclusion can screw up real time performance。

So even though this traditional approach， known as shared state concurrency。

 is still dominating the me programming， using events for interactions allows you to avoid the sharing and eliminates the whole need for mutual exclusion。

So now let's take a look at the event driven alternative with a focus on today's subject of real time performance。

The first thing you will need is a special event that will carry the information about the blinking pattern in its event parameters。

In the introduction to Evenor and programming， I mentioned that events can have such parameters。

 but today is the first time you will actually see how to do this。

So you need to create a new event class。 Let's call it the blink parent Evity that will inherit Q EvT and add to it the two parameters with the same meaning as your global variables。

Next， in By2， upon button press， you want to create such an event。

 set the parameters to the desired value and post it to By 1。

It turns out that you've already done something similar with immutable events such as button press in your BSP do C。

Well， then let's try as the first attempt to do essentially the same here as well。

So you allocate the static event of the type blink pattern EvT。

 but now it cannot be con because you will want to change its parameters。

This also means that you cannot use a one type initializer because you need to modify the parameters every time。

But still， you should not forget that every event needs a signal。 Let's call it blink parent Sig。

And added to the enumation of all signals in B SP dot H。Next。

 you can get rid of the mutual exclusion protection and replace setting the global variable with setting the tick event parameter。

You can leave the for loop with the emulated workload。

 and then you again replace the global with the Eer parameter。Finally。

 you post the static event to the blinky one active object。Here。

 I'd like to emphasize that this is not the final recommended way of generating mutable events。

 and you'll see that it can actually be wrong。However。

 I see similar attempts made by developers new to event driven programming。

 so I showed this step for instructional reasons to later explain why it's not good in general。

But let's leave it for now and continue to blinky one where you still need to receive the generated event。

For that， you add the case for the blink parent signal。Inside。

 you can access the event parameters by explicitly downcasting the received generic event E of type Q EvT to the subclass blink pattern EvT like this。

You can use the text parameter immediately to arm the time event to time out after the received number of ticks and subsequently every number of received ticks。

You can revert to this periodic time out because now you have this explicit change event。Previously。

 without this event， you had to use a one shot timeout because you had to be ready for a change in the global variables at every time out。

You should also not forget to earn the time event for a periodic operation in the initial transition。

Regarding the number of iterations， you need to have it available in all subsequent timeout events。

 so you need to store it in the class attribute。You change the value of this attribute in their blink parent event。

 whereas you access the event parameter the same way as before。Of course。

 now you need to add this attribute to the class。And you need to initialize it in the initial transition。

Well， this should be it for now。 So let's try to compile the code。Okay。

 the C compiler doesn't perform upcasting automatically， so you need to do it explicitly。

And as you are at， you also need to add this arming of the time event before arming it again。Well。

 time for testing。 Up the code。And reset the board。As you can see。

 the first button press causes By1 to change from slow to fast。

And the second press causes it to change from fast to slow。

There are also no more hiccups in blinky one timing。

So everything seems to be working perfectly without mutual exclusion and without sharing。

Or is it really。Well， unfortunately， there is still sharing going on around the static B pattern event。

I mean， the static event object， B P E V TV， might not be completely global because it is hidden inside the blinky2 state handler function。

 but there is still only one such object in the system。

The static event is obviously constantly available to the blinklinky2 thread。

 which changes it from time to time。And it is also made available to the concurrently executing Blinky one active object via a pointer sent through the event queue。

This is， in contrast to the button press event， which is also shared between concurrently executing cyst interrupt and blinky2。

 But that event is immutable， can be declared constant， and it lives in Rome。

So the mutability of the button press event makes all the difference and requires completely different。

 much more complex approach。The good news is that the active object framework like Q P in this case。

 handles most of this complexity for you in a generic， thread， safe way。So to do this correctly。

 you'll need to let the framework allocate the mutable event dynamically via the macro Q new。

 This macro allocates an event of the given type and also sets the provided signal in the event。

 So you don't need to worry about that later。 The macro returns a pointer to the event。

 which you need to keep， but it does not need to be static。Now， you don't need to set the signal。

And you fill the event parametersers as before， remembering that now you have a pointer。Finally。

 you post the event as before。And that's all for creating and posting a mutable event。

The reception of the event in Blinky one does not need to change at all。 In particular。

 you don't need to worry about deleting the dynamically allocated event because the framework will handle this automatically for you。

The only thing that you still need to do is to initialize the part of the framework that deals with the dynamic events。

 specifically， you need to unlockcate the storage for the dynamic events。

 which are kept in deterministic fixed size event pools。

The QP framework can handle many such poles with different sizes。

 but here you need just one pole for holding events of type button press EvT。

Once you statically allocate the pull storage， you hand it over to the framework by calling Q F pull in it like this。

So this is finally the correct version of the event within code。

 free of sharing and mutual exclusion。Let's quickly test it to see how it performs。

 especially in real time。

![](img/fe6be2304fdad82c9973cde8432cfb5a_4.png)

Well。As you can see。It looks really good。All right。 so here is the summary of today's lesson。



![](img/fe6be2304fdad82c9973cde8432cfb5a_6.png)

Every real time application eventually needs mutable events。 But to day。

 you saw that such mutable events must be handled with great care。

 Real time frameworks like Q P provide support for deterministic and threadsafe allocation and exchange of mutable events。

 In fact， this is one of the most valuable services that the framework provides。

 The framework creates an abstraction that is often called zero copy event delivery。

 because from the application perspective， it looks like copying events， whereas under the hood。

 the framework performs a clever management of reference counted events and deterministic event pulls。

But as all nontrial abstractions， this one is also subject to the law of leaky abstractions。

 which states that all nontrial abstractions， to some degree， are leaky。

In case of the zero copy event delivery abstraction， this means that for it to work correctly。

 the application needs to obey certain ownership rules sumd in this lifecycle diagram of a dynamic event。

 At first， all dynamic events are owned by the framework。

 An event producer like Blinkki2 here can gain ownership of an event by calling Qnew。 At this point。

 a producer against the ownership rights with a permission to write to the event。

The event producer might keep changing the event as long as it needs。

 which might be over multiple run to completion steps。But eventually。

 the producer must transfer the ownership back to the framework。Typically。

 they produce a posts or publishes the event。As a special case。

 the producer might decide the event is not good， in which case the producer must call the garbage collector explicitly。

After any of these three operations， the producer loses ownership of the event and can no longer access it。

 For example， changing the event after posting it is not allowed。Also。

 posting or publishing the event again would be wrong because at this point。

 the application doesn't have ownership rights to the event anymore more。

The consumer active object gains ownership of the current event E when it receives the event。

This time， however， the active object gains merely a read only ownership of the event。

The consumer active object is also allowed to post or publish the event。

 and this happens without losing the ownership of the event。So for example。

 this event posting would be okay。And that publishing， in addition， would be fine， as well。

The ownership ends， however， at the end of the run to completion step。

 So if the current event has any information that is needed in the future RTC steps。

 this needs to be saved， typically in the internal attributes of the active object。

So these are the rules that you need to obey in exchange。

 the framework will safely and deterministically deliver your mutable events with hard dwell time performance。

 which is superior to the traditional shared state concurrency and mutual exclusion approach。

This concludes this lesson about active objects， mutable events and real time。In the next lesson。

 I plan to talk about software tracing， also known as logging。🎼If you like this channel。

 please give this video a like and subscribe to stay tuned。 You can also visit statemachine。

com/video course for the class notes and project file downloads。🎼Finally。

 all projects are also available on GitHub in the Quantum Les Repoitory Moern embeddedd programming course Thanks for watching。



![](img/fe6be2304fdad82c9973cde8432cfb5a_8.png)