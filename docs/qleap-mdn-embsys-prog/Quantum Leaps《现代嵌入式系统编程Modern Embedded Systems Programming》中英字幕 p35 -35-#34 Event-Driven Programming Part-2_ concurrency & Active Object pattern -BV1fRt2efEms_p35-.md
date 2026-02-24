# Quantum Leaps《现代嵌入式系统编程Modern Embedded Systems Programming》中英字幕 p35 -35-#34 Event-Driven Programming Part-2_ concurrency & Active Object pattern -BV1fRt2efEms_p35-

![](img/9e790b7b69d472d058cf1fd0da2e1785_0.png)

Welcome to the modernern Emded System programming course。 My name is Miro Samak。

 and today Ill continue with event driven programming。 But this time。

 as it applies to real time embedded systems。In the last lesson 33。

 you'll learn the main concepts related to event driven programming。

 but they were all in the context of desktop windows。Also。

 the whole explanation as to why events should drive the application was entirely based on graphical user interface。

 Gui， and it might not be clear to you how any of this applies to real time embedded systems。

So I'd like to begin today's lesson by going back to the sequential programming with a superloop and a real time operating system。

 Arts， that you learned in the segment of 8 lessons 21 through 28。

 because this is the most familiar and still dominating style of programming real time embedded systems。

From that starting point， you will see how to gradually apply evanvan concepts and what kind of problems they will help you to solve。

For today， I've prepared an example project very similar to what you've used back in lesson 25 about the Arts。

 except that today's code is based on micro Cs2 so that you get expose to this popular arts as well。

Silicon Labs has recently released micro OS 2 on Gitthub under the Permissive Apache 2 open source license。

The project for today's lesson is available for download as a zip file from the companion webp page to this video course at statemachine dot com slash Quickstar for today。

 you will also need to download Q PC dot zip。After downloading。

 you need to unzip both archives into the same directory like this。

The slightly modified micro C2 code is included in the Q PCC third party folder。



![](img/9e790b7b69d472d058cf1fd0da2e1785_2.png)

![](img/9e790b7b69d472d058cf1fd0da2e1785_3.png)

When you build and run this example。It just blinks the green LED on the Tva C launchpa board。

 But this time， you can speed up the blinking by pressing the S W1 button。Additionally。

 to visualize what's going on with the button， the blue LED is turned on when the button is depressed and is turned off when the button is released。

The main blinky thread in today's code。Is almost the same as in lesson 25。

 except it uses the micro C O S time DL Y API to block and wait in line for the specific time delay。

The time delay used is coming from the shared blink time variable， which， as the name suggests。

 is shared between the blinky and button threads to avoid any concurrency hazards around the shared variable。

 It is protected by a mutual exclusion mechanism， which happens to be the priority ceiling mutics of microcoOS 2。

The main button thread also has the usual structure of the endless wide one superlo。 Here。

 the thread weights on the semapho object that is signaled when the button is pressed。

When this happens， the button thread turns the blue LED on and updates the shared blink time variable to speed up the blinking of the green LED in the blinky thread。

 Again， you see here the use of the microceosms to protect the access to the shared variable。

After this， the button thread weights again on the sama object。

 signal when the button is released I after that， the blue LED is turned off。Small as it is。

 this program demonstrates the general principles by which artist's applications are designed。

The main characteristic of the design is that threads synchronize their execution with various events by means of blocking and waiting in line for a chosen event to occur。

But a blocked thread is unresponsive to any other events， not explicitly waited for。Consequently。

 the main workaround for adding new events is to create more threads。

 because multiple threads can wait for multiple events in parallel。

But this ever growing number of threads quickly becomes very expensive and unmanageable。

But even more importantly， the new threads likely need to access the same data。

 peripherals or other resources as the already existing threads。

And this leads to sharing of resources among threads such as the shared blink time variable。

Now you recall that context switching in an artus is closely related to interrupt processing。

 and in fact， an Arts just hijacks the interrupt processing hardware already available in the CPU to do its magic。

But that means that threats inherit all the problems of interrupts。

 including race conditions around any shared resources overlooked or unhindered race conditions can lead directly to system failure。

So now you need to identify and prevent all race conditions。

The artist actually supports it by providing an assortment of mutual exclusion mechanisms such as Mut。

 But ironically， these mechanisms often lead to even more blocking。

 which brings a whole slew of secondary implications。

All this immensely complicates any timing analysis and can lead to missed real time deadlines。

 which can ultimately lead to the system failure。For these and other reasons。

 the experienced software developers learn to be very wary of blocking， and instead。

 they apply a set of best practices that drastically reduce the blocking in their software。

One of the most succinct formulations of these best practices I found comes from the C plus plus and concurrency expert。

 Eb Sautter。

![](img/9e790b7b69d472d058cf1fd0da2e1785_5.png)

Specifically， his article， prefer using active objects instead of naked threads。

 contains the following three best practices。One， keep data isolated。

 private to a thread where possible。This really means that threads should avoid sharing of data or resources with other threads。

 which eliminates the shared state concurrency note in the perils of blocking diagram。

Without sharing， there is no need for mutual exclusion。

 and a big part of the vicious cycle is eliminated。Of course， avoid sharing is easy to say。

 but how are then the threats supposed to communicate and synchronize。Well。

 this is addressed in the best practice number 2。 Comic among threads via asynchronous messages。

This best practice packs two important concepts， Me or events and asynchronous communication。

 These are exactly the event driven concepts you've learned in the past lesson 33。

Event objects also called messages are packaged data specifically designed for communication。

 They carry the information about what happened。 For example。

 a timeout occurred or button was pressed。 Additionally。

 event objects can carry event parameters that pertain to the event， For example。

 an ethernet packet derived event can carry the whole ethernet data packet as its event parameter。

You will see some examples of events in a minute。Asynchronous communication means that senders of events only post the events to their recipients。

 but they don't wait in line， meaning they don't block until the event is processed。

 So the best practice number2 is designed to eliminate the synchronization by blocking node from the perils of blocking diagram。

And finally， the best practice number 3， organizeise your threads work around the message pump references directly the event driven concept of event loop。

 also called message pump， which you learned in the last lesson 33。

This best practice goes directly after the blocking node in the diagram。

Please note that the blocking note cannot be eliminated completely。

 at least not with a traditional arts， because as you remember。

 every artto thread must necessarily block somewhere in its super loop。

But the best practice number 3 prescribes the only allowed structure of the superlo as the message pump。

 which restricts the blocking to only one specific place in the loop。Of course。

 all these best practices combined establish a design pattern。

 which is known as the active object pattern。The pattern is valuable because it provides a layer on top of the naked threads。

 which otherwise lets you do anything， including troublesome things。In this pattern。

 active objects like any other objects， have private data。

 but each active object also has a private thread and a private event queue。



![](img/9e790b7b69d472d058cf1fd0da2e1785_7.png)

The only way to interact with an active object is by posting events to its event queue。

The posting is asynchronous， meaning that the event is only placed in the queue。

 but there is no waiting until the event is processed。

The event processing happens in the event loop running in the private thread of the active object。

 The processing might involve sending secondary events to other active objects， or even to self。

In a sense， active objects are the most stringent form of object oriented programming because the asynchronous communication enables active objects to be truly encapsulated。

 In contrast， that traditional OopPN capsulation， as provided by C plus plus C sharp or Java does not really encapsulate anything in terms of concurrency。

Any operation on an object runs in the colors thread。

 and the object's private data are subject to the same race conditions as global data not encapsulated at all。

To become thread safe， operations need to be explicitly protected by a mutual exclusion mechanism。

 such as a muttics or a monitor。 But this leads to additional blocking and requires special attention from the programmer。

In contrast， all private data of enactive objects are truly encapsulated for concurrency without any mutual exclusion mechanism because they can be only accessed from the active objects's own thread。

 Not that this encapsulation for concurrency is not a programming language feature。

 so it is no more difficult to achieve it in C++ as in C。

 but it requires a programming discipline to avoid sharing resources。

 known as they share nothing principle。However， the event based communication helps immensely because instead of sharing a resource。

 a dedicated active objects can become the manager or broker of that resource。

 and the rest of the system can access the resource only via events posted to these broker active objects。

The active object pattern is valuable because it naturally implements and automatically enforces the best practices of concurrent programming。

From the historical perspective， the active object design pattern combines the arts。

 object oriented programming and Evanvanrvan programming。 I will call these trends modern。

 as in the title of this whole modern embedded systems programming video course。This is。

 in contrast the still dominating traditional approach based on a traditional artist and shared state concurrency that dates back to the early 1980s when artes went mainstream。

All right， this was a lot of dry theory， so now let's actually see how active objects could be implemented on top of a traditional art。

Starting from the previous sequentially coded example with microCOOS2。

 let's now add the active object services。Because the active object layer will be based on microcos。

 let's call it microca A O。The minimal implementation of MiCAO will consist of the Micy underscoreco AO。

 H Her file and the Microcy_ AO。C source file， which I prepared in advance and will quickly review with you today。

The her file。Includes the microcis art and adds to it the event facilities。

The event signal will be just a small integer， which will hold enumerated signals representing various interesting occurrences in your application。

There will be a couple of reserved signals， such as the in signal that will be dispatched to each active object right before entering the event loop。

The user signal will be the first signal available to the users。Next。

 you need to define the event structure。 It needs to contain the signal。

 but it also needs to be extensible to fit arbitrary event parameters。

 This would be accomplished by the object oriented concept of inheritance。

 as you learned in lesson 30。But just to give you an example use case。

 a hypothetical ethernet event could inherit the event based structure and could add the ethernet packet as the parameter。

Next， you need to define the facilities for active objects。

You start with the forward declaration of the active objectstruct。

 followed by the definition of the dispatch handler pointer to function。

This will be a virtual operation in the active object class。

 as you learned in lesson 32 about polymorphism in C。Next， you can define the active objectstruct。

 which as you recall needs to have a private thread and a private event queue。For microcius  too。

 the threat can be represented by its unique priority。

The event queue will be represented by the microcy 2 O S event pointer。

 The name O event here is a bit of a misnomer because it means here operating system object to deliver the event instances you just defined above。

In case of microseos 2， this operating system object will be a message queue。

 which is somewhat of an overkill because it can be potentially written to and read from by multiple threads。

In contrast， an event cu of an active object can be much simpler because it needs to be read from a single thread only。

But the message queue is the closest approximation of what you need。

 even though it's a bit more expensive than strictly necessary。Finally。

 the activestruct contains the pointer to its dispatch virtual operation that will be provided in the subclasses。

This is the implementation option of polymorphism you saw in lesson 32。

 where you embed the whole virtual table directly in the class with just one virtual function dispatch。

 this implementation makes the most sense。The specific subclasses of the active base class will also add their private data through inheritance in the same way as subclasses of event at event parameters。

These will be the strictly encapsulated private active object data accessible only from the private threat of the active object。

 Youll see examples of it， in a minute。The active class will have a few public operations。

 starting with a construct， which in C is just a regular function that you need to call explicitly。

Then the active start operation will start the internal thread of the active object。And finally。

 the active post operation will asynchronously post events to the active object event queue。

Now let's quickly review the implementation of these services in the Micy underscore Ao。cC file。

Let's begin with active start operation。First， the function creates the internal microCOOS2 message queue and asserts that the queue was created correctly。

But the most important is how the function creates the internal microces to task for the active object。

Interestingly， you can see that every active object thread is based on the same event function defined earlier in the file。

This is a drastic departure from the traditional way of creating artist threads where each thread runs its own custom thread function defined in the application level code outside the artist。

In contrast， here all active object threads run exactly the same event loop function defined inside the active object module and even made static to hide it completely in this module。

This means that the control over the thread function resides in the active object module rather than the application。

 Now， I hope you remember from lesson 33 that such inversion of control is one of the main characteristics of event driven programming。

But while all active objects run the exact same event loop function。

 each such function operates on a different active object instance me。

 which is passed as the P data argument to the OS task create X microcy2 API。

So now inside the active event loop implementation。

 which must conform to the microCO2 task function signature。

 the P data void pointer parameter is immediately cast back to active and assigned to the me pointer to give it access to the active object instance this function works on。

The rest of the active object event loop code is quite similar to the Windows Goi code that you have seen in the last lesson 33。

So let's pull up that code for reference。For example， the initialization of the application。

 which in Windows GuI happens in the call to create window。

 sends the WM create message to the window pro。In your embedded code。

 this is accomplished by directly calling the dispatch virtual function via a pointer to function to which you pass the initial event carrying the reserved in it signal。

An interesting twist here is related to the chosen active object interface。

 which posts only pointers to events， not the whole event objects by value like it was in Windows。

In general case of events that are modified outside a given active object。

 you must be very careful to avoid race conditions。

But events without parameters can be constant and allocated in Rome。

 Such immutable events can be shared freely because they don't pose any concurrency risks。

You will see a few more example of posting immutable events later in this lesson。

The following code implements the actual event loop the same way， really as the Windows Gui code。

At the top of the loop， you see the OSQ pan call that obtains the next event from the active objects event queue。

This is the only place in the loop where blocking is allowed when the queue is empty。Next。

 the received event is dispatched to the active object me by means of the virtual call via the me dispatch pointer to function。

The final touches of the implementations are the active object constructor。

 which simply sets the virtual operation dispatch。And finally。

 the asynchronous event posting to an active object boil down to posting the event to its private event queue。

So this is about it at this point。Now， let's try to use the active object layer instead of the naked microciioos2 arts。

For starters， let's convert just one of the traditional sequential threads to an active object。

 It turns out that the button thread is easier with the currently available active object services。

You can keep the original sequential code as a reference for now。

 but remember that most of it will be deleted after you are done。So first。

 you need to create a button active object class by inheriting the active base class as the first member super。

The button active object has no private data， so you don't add any other members to the。Next。

 you implement a button dispatch virtual function in which you process one event at a time。Typically。

 you call the function with the switch statement， which discriminates based on the event signal。

When you received the special reserved in its signal。

You establish the initial state of the blue LED as off。

When you receive the application specific button pressed signal。

 you perform all the actions that you did when button pressed Semapho was signaled。Finally。

 when you receive the application specific button released signal。

 you perform the actions that you did when the button released Semapho was signaled。

 So here you have just seen how to convert the sequential code to event drivenvin code。

The most important thing to remember is that in the event driven code。

 you never block to wait for events。 All waitinging is external to the dispatch function and happens at the top of the event loop。

The last function you need to define is the constructor of your new button active class here you have to call the base class constructor where you attach the specific button dispatch implementation to the virtual dispatch operation。

This completes the definition of your new button class so you can delete the sequential code。

 including the blocking sephos。But you need to keep the stack because it is still needed for the internal thread of the button active object。

A part of that， you also need to provide the memory buffer for the private event cu of the active object。

 the instance of the button active object and the global pointer to the active object so that other parts of the code such as the BSP can post events to it。

The last change in main that seen is to call the button constructor explicitly and to start the active object by calling the active start member function。

Regarding the BP board support package。You need to replace the blocking sehorce with a definition of the event signals。

And you need to declare the global pointer to the button active object。

Please note that the global pointer is of the type active， which is the superclass。

 rather than the specific button sub class。 This is intentional to completely encapsulate the private data that the subclass might have inside。

 The rest of the application simply does not know about any such data and can only interact with a button instance as a generic active object。

In the BSP implementation， BSP do C， you need to replace the signaling on the sehorce with posting events to the button active object。

 The button pressed and button released events have no changing parameters so you can use the immutable consed events in ro。

And this is finally all as far as the button active object is concerned。

 The compiler still points out a few details to fix。But eventually， the project builds cleanly。

Please note that the blinky functionality is still coded with a traditional sequential and blocking microcy OS2 thread。

All right。 I know you must be really curious to see how all this works。

 So let's just load it to the board and run it。 As you can see， the green LED blinks us before。

 but this is hardly surprising because this is still the old sequential code。😊。



![](img/9e790b7b69d472d058cf1fd0da2e1785_9.png)

But the button is the new event driven active object code。 As you can see。

 it also works exactly as before。So congratulations， you just implemented your first active object。

Very well。 So now I am sure you want to go with all your guns blazing and convert the sequential blinky thread to an active object as well。

Using the existing button active object as a template， you can just copy and paste the code。

And replace button with blinking。But now comes the most interesting part。

 which is the actual implementation of the blinky dispatch operation， whereasas you shall remember。

 you are not allowed to use any blocking calls。But here in lies a problem。

 button present button release were obvious events。But where is an event in the time delay。Well。

 every blocking calls always corresponds to an event， even though initially。

 you might not know how to call it。But time delays specifically， correspond to time events。

A time event is an event that an active object can request to be posted to its event queue in some time in the future。

Such functionality does not yet exist in your micro active object layer， so you need to edit。First。

 you go to the microCO header file where you add a time event class。



![](img/9e790b7b69d472d058cf1fd0da2e1785_11.png)

Because time events are just specialized events， a time event class inherits event。 But in addition。

 a time event must remember the active object that requested the timeout。

 and a time event must also keep track of the time out。

 which will be a down counter decremented by every system clock tick， when the counter reaches 0。

 the time event will be posted to the active object and the time event will be considered disarmed。

 This also means that the time out value of 0 indicates at thisar time event that is not ticking。

Finally， often you might want the time event to be delivered periodically。

 This can be quite easily achieved by adding the interval member。

 This interval will be loaded to the time out down counter when it reaches 0。 That way。

 the time event will automatically arm itself and will keep ticking towards the next time out。😊。

The interval value of 0 will then naturally correspond to one shot time event that would be automatically disarmed after expiring only once。

The time event will have a few public operations， such as the constructor。

 as well as the arm and this arm operations。Finally。

 the class wide operation time event tick would be a static class operation without the me pointer for the specific instance。

 It will service all instances of the time event class， every system clock tick。Now。

 regarding the implementation of the time event operations in microcao。 C。

 I will use a very simple approach。To keep track of all time event instances in the system。

 I will simply use a static array of pointers sized for some maximum number of time events and the actual number of time events registered so far。

 I like to add the prefiix L underscore to indicate that these variables are local to the module。

Then in the time of constructor， you initialize the data members as usual。

But you also store the time event pointer in your local array。

 and you increment the actual number of time events registered in the system。

An important consideration here is to realize that the local variables can be implicitly shared among concurrent art threats。

 and also system clock interrupt through the interface of the time event operations。

 This means that there is a potential for race conditions around these variables。

 So you need to apply some mutual exclusion protection around them。

Here you can use the fast micro2 critical section mechanism because the axis is very short。

This is exactly the same mechanism that microcy 2 itself uses internally in its own source code to protect its internal variables。

This leads to an interesting observation that， in a sense。

 your active object layer is an event driven extension of a traditional artist。As such an extension。

 it poses similar challenges as other parts of the artist's code， for example。

 avoiding internal race conditions。But going back to the time of an arm operation。

 it simply sets the time out and interval members inside the critical section。Similarly。

 the time event disarm operation clears the timeout to 0， also in a critical section。Finally。

 the most interesting class time event tick operation goes over all the registered time event instances。

This function is intended to be called from the system clocktic interrupt。

 which can never be preempted by an art's thread。 Therefore， it does not need a critical section。

Each time event is first checked whether it is armed。 And if so。

 its time old counter is decremented and checked again if it just has reached 0。If so。

 the time event is posted to the active object， and the timeout counter is reloaded from the interval data member。

 This works for both periodic time events and one shot time events when the interval is 0。

The last modification you should not forget is to add the time Even tick call to the system clocktic microCO2 callback so that the registered time events are serviced。

All right。 So this was the extension of the active object layer。 Now。

 let's use it to implement your By AO。The blinky active object clearly needs a time event。

 so let's add one time event instance as its private data。As all private data members。

 the time event member needs to be initialized in the constructor where it becomes associated with the active object me super and gets the signal timeout defined BSP do H。

So now you have the event signal for your timeout， and you can write the case statement for it。

 As usual， you copy a portion of sequential code up to the blocking call。But here comes a problem。

 Should you turn the LED on or off。 I mean， in the sequential code， you had two blocking calls。

 one for LED on time and the other for LED off time。 But here in the event driven code。

 you have only one time out event。 and you need to know whether the LED was most recently on or off。

 This information needs to be stored in such a way that it would survive the calls and returns from the dispatch operation。

 This means that it definitely cannot live on the stack as an automatic variable。Instead。

 the ideal place for it is the private data in your active object class。

 where you add the is LED on Boolean flag。Assuming that the LED is initially off。

 you can set the flag accordingly in the constructor。Now， in the timeout case。

 you first check the flag and if it indicates that the LED is not on yet。

 you turn it on and remember this change in the flag。

 Then you arm the time event to expire in B T clock ticks。Otherwise。

 you turn the LED off and set the flag accordingly。 here。

 you arm the time you to expire in three times B T clock ticks。But this code has still a basic flaw。

 The time event is armed only in the timeout case， but this case executes only when timeout event occurs。

 So you need to somehow prime the pump so to speak so that the time event gets armed the first time。

And this is exactly where you can take advantage of the innate event dispatched to every active object right before entering its event loop。

 here， you can explicitly turn the LED on， Sa the is LED on flag and arm the time event。

But this is just repeating what is happening in the timeout case when the flag is cleared。

 So your other option is just to intentionally fall through from in it to time out。

Now you still need to move the shared blink time stuff before the new blinky active object。

Remove the sequential code。And start the blinky ao instead of the sequential， By thread。Of course。

 now you want to see the codes to the works。And。Both blinky and button active objects work as expected。

Now， as the very last exercise in this lesson， I'd like you to take a critical look at the two active objects you have created。

 They came to be only because you had translated the sequential design from the conventional artist to active objects。

 But the real and only reason why you ended up with two active objects is that sequential superlos were not composable due to unresponsiveness。

😊，Making them composable again was the whole reason for existence for an arte at the expense of creating multiple threads。

But all this does not apply to ervin code， which remains responsive to all events。

 This means that ervan code is directly composable。Well， in that case。

 you should be able to merge blinking and button together into just one active object。

So let's actually do it right now， starting with renaming Blinky to By button。Next。

 you need to move any private data if present， from the button class to Blinky button。

And you need to move all events handled by the button to the Blinky button dispatch operation。

Any duplicate cases need to be merged， such as event handling in in it。But wait a second。 Now。

 the shared blink time is no longer really shared between threads。 Instead。

 the variable can become internal， fully encapsulated private data inside the blinky button active object。

As all other member variables， blink time needs to be initialized in the constructor。

And since there can be no race conditions around blink time anymore more。

 you can get rid of the metics protection。 This not only reduces the overhead。

 but eliminates any potential blocking in the event driven code。 Thus。

 the code has a more predictable timing and is better suited for hard drill time applications。

So you replace the shared blink time variable with me B time private attribute。

Clean up the temporary variables。And get rid of the muttics。

Now you can simply delete the button active object altogether。Note that by doing so。

 you free up significant Ram for the stack and the cube buffer。

Obviously now you no longer need to create or start the button active object。

You still need to make a few name changes to fix the syntax。And finally， as the compiler reminds you。

 you need to change the global AO button pointer to AO Blinky button。Of course。

 the very last thing to do is to verify that the final code still works as before。And。Indeed。

 it does。I hope that this exercise demonstrates the following two properties of active objects。First。

 an active object can hold much more functionality than a traditional blocking thread because you no longer need to create expensive threads just to make them responsive to events。

And second， the ability to combine functionality inside event of an active objects makes it much easier to avoid sharing of resources among them than the traditional blocking threads。



![](img/9e790b7b69d472d058cf1fd0da2e1785_13.png)

In summary， I realized that this lesson grew to be a little longer than usual。

 but really a lot happened to day。 You experienced nothing short of a paradigm shift from traditional sequential programming within arts concepts that essentially didn't change since the early 1980s to modern event driven active objects。

😔。

![](img/9e790b7b69d472d058cf1fd0da2e1785_15.png)

Not only this， you actually started to build your own active object framework called Ter microcaO。

 which is very different from in the art because it is based on inversion of control。

In your framework， you used a few services from a traditional art。

 such as threads and message queuees， but the traditional art does not provide much else needed in event driven programming。

 which you had to create yourself。At the same time。

 most mechanisms provided in a traditional art are of no use in programming。

 the event driven active objects。 Not only they are not helpful。

 they can be outright harmful because most of them are based on blocking。

 which is not allowed inside active objects。At the end of the day。

 even though a traditional artist can be used to implement an event driven framework。

 it is not the best fit。 I will hopefully get back to this， in the future lessons。

If you like this channel， please give this video a like and subscribe to stay tuned。

 You can also visit statemachine。com squiickstart for the class notess and project file downloads。



![](img/9e790b7b69d472d058cf1fd0da2e1785_17.png)