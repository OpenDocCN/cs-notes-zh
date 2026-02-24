# Quantum Leaps《现代嵌入式系统编程Modern Embedded Systems Programming》中英字幕 p28 -28-#27 RTOS Part-6_ Synchronization and communication.zh_en -BV1fRt2efEms_p28-

![](img/d1a29066a685ed4051b59e7708f0d42b_0.png)

Welcome to the modernern embeddedd System programming course。 My name is Miroamic。

 and in the sixth lesson on Arts， Ill talk about the arts mechanisms for synchronization and communication among concurrent threads。

 such mechanisms are the most complex elements of any arts and are generally really tricky to develop by yourself For that reason today。

 I will replace the toy Miros Arts with a professional great QXK arts included in the QPC framework。

 parts of which you have been using since lesson 21。😊。

You will see the process of porting your existing application to a different arts。

 and once this is done， you will learn about semaphos and see how they work in practice。As usual。

 let's get started by making a copy of the previous lessonson 26 directory and renaming it to lesson 27。

Get inside the new lessonsson 27 directory and double click on the microvision Project lesson to open it。

🎼To remind you quickly what happened so far， in the last lesson you implemented Preemptive priority based scheduler and you learned about the rate monotonic scheduling technique。

 which allows you to assign priorities to threats such that they all can meet their hard real time deadlines。

🎼The。But your blinky threads still aren't very realistic in that they run completely independently of each other。

 You can compare this situation to trains running on completely independent circular tracks。

 analogous to the endless wild one loops of your threads。



![](img/d1a29066a685ed4051b59e7708f0d42b_2.png)

In real life， neither threats nor trains run completely independently。

 but rather their tracks cross in various ways， which require synchronization and communication to provide timely service and to avoid collisions。



![](img/d1a29066a685ed4051b59e7708f0d42b_4.png)

Trains have solved this problem with a railroad semaphore， which can be either open or closed。

 if the semaphore is closed， any approaching train must stop and wait until the semapho opens。

 If the semaphore is already open， any approaching train can simply pass through。

The concept of a samaphore has been adapt for softwareware already in the 1960s by the Dutch computer scientist atk Dextra。

 Dextra invented a software Semaphore for a time sharing system he was designing at the time。

 The semaphore has been later extended to the priority based schedulers and real time operating systems。

 arttois which went mainstream in the early 1980s。Today you will see how a softwarewe semaphore works and how to use it for thread signaling。

 but at this point you are really reaching the limits of your homegrown Miro arttos because it turns out that implementing semaphos as well as all the other interthread communication mechanisms is really complex and tricky to get right。

So today， instead of implementing some of from scratch in the toy Miro Arts。

 I will show you how to move on to a professional grade QXK Arttos included in the QPC framework。

 parts of which you have been using since lesson 21。

 I use QPC in this course because it supports many different programming paradigms。

 the conventional priority based preemptive arts being just one of them of interest for today's lesson。

In the future lessons， you will learn about other more modern paradigms that QPC also supports。

 such as object oriented programming， event driven programming， state machines。

 and component based programming with active objects。

The process of moving an application from one artist to another is called porting an application。

 and it's a valuable exercise in its own right。 Porting an application is like replacing the foundation from under a house with minimal disturbance to the house itself。

So to start porting， let's remove the Mis files from the project。🎼And rename the group to QPC。うん。어。

Also to make sure that none of the Miros stuff is being used。

 let's go to the current lessons 27 project on disc and delete the files Miros。h and Mis。c。Next。

 you need to add the QPC source code to the QPC group。

 but first let's make sure that you have QPC installed on your machine。

 you should have it in the QPC folder at the same level as the folders for the lessons。

If you don't have QPC yet， please go back to lessons 21。

 where I showed you how to get QPC from the companion webpage to this video course， statemachine。

com/quistart。🎼。🎼Once you make sure that you have QPC installed。In the microvision IDE。

You right click on the QPC group and choose add existing files to QPC group popop up menu。From there。

 you go one level up and go into QPC source。QF subdirectory。

You need to select all the files in the QF subdirecty， which contain the code for state machines。

 event driven programming and component based programming， I will explain them in the future lessons。

On top of this， you will need the specific Arts kernel。

 which is the QX preemptive blocking Arts in this case， to select it。

 go to the QXK folder and select all the files。And finally。

 you will need the specific port of QXK to the arm cortex and processor and the arm Kyle microvision tool chain you are using for this。

 you go up to the ports directory and down to Ar dash CM。

And inside there to QXK subdirecty for your specific QXK kernel。Inside the kernel directory。

 you see subdirecties for all supported tool chains such as Ar Kyle， armm with Clang。

 Go and IER toolchains。As you can see， the port directory is a bit complex。

 but this is typical for most professional artes， which have imported to many CPU types and tool chains。

On the flip side， if you wish to use a different CPU or toolchain， most likely you will find it here。

So for today， you need to go inside the arm directory for the arm Kyle toolet you are using and select the QXkport。

c file。The next step is to adapt your application to the new QPC Art。

 which is like adjusting a house to the new foundation for that。

 you can use the compiler to show you exactly what needs to be adjusted。🎼First。

 you obviously need to replace the nonexistent Mis。h header file with QPC。h。🎼你出。🎼う。🎼出出。🎼と。🎼不想说出。

The next problem is that the compiler cannot find the QF port。

h Hader file This header file is included from QPC。h。

 and it needs to be taken from the same port directory from which you took QXkport。c。

You provide this information to the compiler by adding the ports directory to the compiler include search path as follows。

When you build the code now， you still have errors but notice that all the files comprising the QPC source code compile correctly。

The remaining errors are getting more interesting because they are caused by the mismatch between the previous Mis Arts application programming interface。

 API， and the new QXK Arts API。The first such mismatch is the name of the thread control block。

 O S thread。This data type still exists in QXk， but it is called QX thread instead。

 so let's replace OS thread with QX thread and rebuildil。🎼The next mismatch is the OS delay function。

This function also exists in QXK， but it is called Q S thread。Underscore。Delay。🎼Again。

 let's replace the name and rebuild。🎼The。Now， the compiler does not recognize the OS in function。

The equivalent in QXK is QF in it， but QXK no longer needs the extra task space for the idle task because it reuses the main Ct for that purpose。

This more clever design means that the idle stack space can be recovered。

🎼The next problem is the thread start functionality。

 which is implemented slightly differently in QXK。For reasons that will become clearer when I talk about emulating object oriented programming in C in one of the future lessons。

A thread can be started only after the QX thread object has been initialized。

This initialization is accomplished by a special function called the constructor。In this constructor。

 the Q X object is associated with the thread function。

 and also with the specific system clock rate here represented as0。

A QX K thread is started by means of the QX thread start macro。 notice the all capital letters。

The reason for using a macro at this point will also be explain in the lesson about object relatediented programming in C。

 but for now it is important only that QX thread start takes more parameters。

The first two parameters are as before the thread object and the thread priority。

The next two parameters are the message Q buffer and size。

 The By1 thread does not use a Q at this point， but Q X threads in general can have dedicated cus。

The next two parameters are the stack buffer and size， as before。And finally。

 the last parameter is a pointer argument passed to the thread。

 It will also be ignored at this point。When you build now。

 the compiler complains about the incompatibility of the thread function pointer passed into the QX thread Conor。

This is because in QXK and thread function has slightly different signature。

It takes one parameter called me by convention， which allows you to access the associated thread object inside the thread function。

Of course， you need to adjust all your thread function signatures the same way。

Now the compiler finally likes the initialization and starting of your first Blinky1 thread。

 so you simply need to repeat these adjustments for all the remaining threads。🎼，🎼そ。

The last warning in Ma is that the OS run function is not recognized。

 The equivalent function in QXK is QF run。Please note that QFran also never actually returns back to Maine。

The build diagnostics now change from compilation to linking errors about functions called from BP。c。

 so let's go there and adjust it for QXK as well。The first modification needs to be done inside the Stic interrupt handler here。

 the undefined call to the scheduler needs to be replaced with the QXK macro QXK IR exit。

 which also performs preemptive scheduling inside the critical section。Additionally。

 Q XK provides a matching QX K IR entry macro to be called upon the entry to the IR before any other QXK API call。

The next undefined call to our stick needs to be replaced with a macro。Qf。Underscore tick。

 underscore x。Which services the timeouts at the specific clock tick rate here specified at0。

 It is the same clock tick rate as the one you set in the thread constructors。

The next category of undefined symbols originate from the QXK kernel。

 which means that these are callbe functions defined in QXK but not implemented there。

 the first of these callbe functions is QF on cleanup。

 which is only provided for the situation when an application exits。

Deeply embedded applications like your blinky never really exit。

 so this c function can be defined as empty。On the other hand。

 the undefined symbol QF on startup must be defined as the replacement for OS on startup。Here。

 the most important difference is that you cannot set cystic interrupt priority to0 because this highest interrupt priority in arm cortex M is never disabled in QXK。

At this point， I need to digress and explain the concept of interrupt latency and the more advanced interrupt disabling policy used in QPC compared to the simplistic murals arts。

As I explained already in lesson 17 about the interrupt， the interrupt requests are asynchronous。

 meaning that in general they are not correlated with the execution of the code。

I also explained that the CPU can recognize and interrupt only at the instruction boundaries。

 after which the CPU still needs to perform interrupt entry All this obviously takes some time。

This time delay from the interrupt request to the first instruction of the interrupt service routine。

 ISR， is called the interrupt latency。But this picture still does not show all the delays contributing to the inter latency。

As I explained in lesson 20 about race conditions and lesson 23 about Arts。

 and Arts needs to occasionally disable interrupts to prevent race conditions around its own variables。

 These critical sections of code shown here as black boxes obviously also contribute to the interrupt latency。

So at the end of the day and as usual for real time performance。

 the most interesting and important measure is the worst case， maximum interrupt latency。

 which consists of the longest critical section plus the interrupt entry time。

But such maximum interrupt latency might be just too long for certain ISRrs。

If these ISRrs do not make any ArtOS API calls， they don't run the risk of interfering with the Arts。

 so they really don't need to be penalized by the critical sections of the Arts。

This leads to the concept of kernel interrupts which are never disabled by the kernel。

 but also can never interact with the kernel。 The interrupt latency of such kernel interrupts is sometimes promoted as0 zero interrupt latency。

 which does not mean that such interrupts are handled instantaneously。 This is impossible。

 It only means that the presence of the arts has zero impact on the interrupt latency。In contrast。

 kernel A interrupts can call ArtTOS API， but in exchange they have longer maximum interrupt latency。

Of course， all this discussion is relevant only for processors that can disable interrupt selectively so that some of the interrupts can remain enabled while others are disabled。

As it turns out， the arm cortex M3 M4 and M7 CPUs， but not the cortex M0 or M0 plus。

Allow you to disable interrupt selectively。Specifically。

 instead of globally disabling all interrupts with the pre mask register。

 Cortex M3 and higher provide also the base pre register。

 which allows you to mask interrupt selectively only up to the specified interrupt priority level。

This means that interrupts above the level set in the base pre register are never disabled。



![](img/d1a29066a685ed4051b59e7708f0d42b_6.png)

![](img/d1a29066a685ed4051b59e7708f0d42b_7.png)

The QPC port to Ar cortex M3 and higher CPUs employs this more selective interrupt disab method。

As described in the application note， setting arm cortex M interruptdirect priorities in QP。

The QP port provides a constant Q F Aware ISR Simis pre。

 which separates kernel A interrupts from kernel unware interrupts。

Here is how the two interact groups look for enviC with three bits of interact priority。🎼。

🎼And here for envi with four bits of interrupt priority。So now， coming finally back to your code。

 you can see that leaving the cyst priority at zero would make it to a kernel unaware interrupt。

This would be incorrect， sinceistic， apparently calls QPC APIs。Therefore。

 cystsistic must be a kernel aware interrupt with priority QF Aware ISR Syesis3， or a bigger number。

 which would correspond to the lower interrupt priority in cortex M。Please now。

 that I also adjust a comment to explain the situation。

One more build shows that the compiler accepts all the changes。

 but the linker still complains about the undefined OSs on iddle symbol。

 This col function from the Miros Artus is called QXk on iddle in QXK and has exactly the same semantic。

 so nothing except the name needs to change。🎼The code finally builds with zero errors and zero warnings。

 so I am sure that you are curious if this whole thing still works。🎼嗯。

After you load the program into debugger， the interesting question is how to best verify that your artist's application works。

Well， I typically focus on the threads。🎼Yeah。🎼Yeah。Interrupt。🎼う。🎼And the id callback。

🎼When you run the program， the first breakpoint hit is inside the Blinky1 thread。

 this seems reasonable since By1 is your highest priority thread。

The next breakpoint hit is inside the cysttic handler。

 which confirms that the interrupts are serviced。Another interesting aspect to watch is how the interrupt returns here in the disassembly view。

 you can see that the interrupt returns via the P to PC instruction。

 which returns to a BSB function called from the Blinky1 thread。Next。

 you hit the break point in Blinky2 thread， which proves that this low priority thread also starts executing。

🎼But the question now is how to look into the QXK art' variables since the mirrors art's variables are no longer valid。

 so you should delete them from the view。To find out which variables to watch in QXK。

 open the QPC source code， include directory QXk。h header file。

 where at the top you can find the structure defining the global attributes of the QXK kernel。

 copypy the QXK ATR variable name to the clipboard and paste it into the watch1 window When you expand the structure。

 you can see that the current data member points to the blinky2 thread， which makes perfect sense。

Finally， you reach your last break point inside the idle callback here you can verify that the red LED on your launchpaboard is turned on。

And off。When you exited thebuggger and let the application run free。

 you can see some activity of the LEDs， but to verify that nothing really changed compared to Miros Arts。

 I will use the logic analyzer view。 So here is the same setup as in the previous lesson 26。

 the top trays labeled ISR， shows the activity of cyststic。

 which fires every millisecond and toggles the test pin。



![](img/d1a29066a685ed4051b59e7708f0d42b_9.png)

![](img/d1a29066a685ed4051b59e7708f0d42b_10.png)

The trace below labeled T1 shows the activity of the By1 thread， which runs for about 1。

2 milliseconds and toggles the green LED。 As you can see。

 By1 always meets it a deadline of two time ticks。The trace below labeled T2 corresponds to Blinky2。

 which toggles the blue LED。 This thread also meets the deadline of 54 time ticks。And finally。

 the bottom trace labeled Ide corresponds to the idle thread that toggles the red LED in the Qxk on iddle callback。

 It runs only when no other thread or ISR are active。In summary。

 the QXK Arts executes your application and behaves exactly as the last version of the murals Art in the previous lesson。

So now that you have verified your port to QXK， let's see what kind of problems these artist will allow you to solve。

For example， up till now the Blinky2 thread has been based on the blocking De function。

But suppose that you would like to base the blinking of the blue LED on the button press instead。

 specifically， the blue LED should start toggling only after you press the SW1 switch on your launchpa board。

In the train analogy， this problem would be solved by applying a railroad semaphore。

 Such a semaphore would be initially in the closed state。

 so any approaching train would need to wait。Pressing the button would signal the semaphore。

 which would release the train from waiting and let it continue around the track。

The QXK Arts kernel supports such a semimapho concept in software。In particular。

 to add a semaphore for signaling of switch SW1， first you need to define a semapho object。

 which I will name SW1 Se of the type QX semaphore。To find out what QXma4 is。

 you can open the online documentation。Starting from the companion web page to this video course。

 use the top menu Product QPC framework。You can start typing QXEma into the search box and click on QXEma4。

As you can see， QX saphore is a kernel object that consists of the QX samapho structure plus functions starting with the QX samapho underscore prefix that operate on this structure。

The most important element of a semapho is the count data member。

 which is an up down counter that keeps track of the number of times the semapho has been signaled and waiteded on。

The semaphore stores also the maximum count value， as well as the weight set that remembers which threads are waiting on the semaphore。

The weightet data member is similar to the readyis set Pimk introduced in the Mirals artist。

 except in QXK， it can hold up to 64 priority levels。Before a semapho can be used。

 it needs to be initialized with the QX semapho init function， as shown in the usage example。

 a good place to perform the initialization is the top of the main function。 In fact。

 let's just copy the usage example。And paste it。Into your main function。QX sum in it。

Takes the pointer to the seapho you wish to initialize。As well as the initial sign of account。

And the maximum semaphore count。Most often for signaling you would set the maximum count to one。

 meaning that the semapho count would be allowed to take only two values0。

 meaning that the semapho is not signaled and one， meaning that it is signaled。

 such a semapho is called the binary semapho。Also， initially your SW1 samapho is not signaled。

 so you set the initial count to0。Once the semapho is initialized。

 you can use it to synchronize your thread； you do this with the QX semapho weight function。Again。

 let's just copy the usage example。And paste into your blinky2 thread function。🎼，🎼The。

The weight function takes the point to your semapho object and also allows you to specify a timeout for how long you wish to wait on the semapho。

If you are willing to wait indefinitely， you use the special timeout value， QX thread， no timeout。🎼う。

Also now that you have the sapho as the blocking mechanism。

 you don't need the blocking delay anymore， so you can delete it。At this point。

 you are done with the waiting part of the problem and you can check whether the code compiles。

But you still need to implement the signaling of the semapho when the SW1 button is pressed。

 Let's start with taking a look at how this SW1 button is connected to your TVC microcontroller。

For this， you can go to the companion web page to this course。

And click on the Tva Launchpad Use manual。🎼In the table of contents。

 scroll down to the schematics section。🎼Where on the second page。You can find the SW1 switch。

And trace its connection to the Pf4 pinIN， which stands for PN4 in the GPIOF group。

With this information， you can now go to the board support package BSP。c。

 which is the logical place for any code specific to the board。

You define here the button as W1 pin as bit4， similar as you did for the LEDs。Notice， however。

 that pin 4 in the GIOF group is already used as the test pin。

 that the handle toggles for the logic analyzer view。This is obviously a conflict。

 so let's just remove all uses of the test bin from the code。Instead。

 let's configure the button SW1 pin similarly as you did for the LEDs。

The pin direction should be input。🎼。🎼Yeah。🎼住。And the pin should be configured as digital。🎼出去。

Additionally， since this is an input pin， it needs to be configured with the pull up register enabled。

Pull up register enabled means。The pin will be normally at the high level while pressing of the SW1 switch will bring it down to the low level。

The final part of the GPA Open configuration is setting it up to generate interrupts to the CPU here I simply copy and paste the code and let you read the comments and possibly also consult a TVA data sheet。

The only thing that I'd like to note is that to sense the pressing of the SW1 button。

 the MC needs to detect the falling edge in the voltage supplied to the pin。

 Now you are finally ready to write the GPIO interrupt handler for the Sw1 switch。

 This would be your first IR unrelated to the clockctic because so far youve been only reusing the cysttic interrupt introduced already back in lesson 16。

But actually， let's begin with copying and pasting cystick as your starting point。

The first thing you need to change is the name， which you can look up in the startup code inside the Inter factor table。

Inside the ISR body， you'll leave the QXKISSR entry and QXKISSR exit macros because this will definitely be a kernel aware interrupt。

But you need to delete the QS T call and replace it with the signaling on the semaphore。However。

 before you can signal the se， you need to make sure that the interrupt is coming from the specific SW1 pin。

 because this ISR will also fire for other pins of GIOF if they are configured to trigger this interrupt。

Also after detecting the source of the interrupt， the GPIO peripheral needs to be explicitly cleared in software so that it is ready for the next interrupt。

So finally， inside the if statement， you can signal the semapho by means of the QX semapho signal function。

The only parameter you need to supply here is the pointer to the sehor object。

But you are not quite done with this interrupt yet， as I explained earlier， forsistic。

 the very important step for any kernel aware interrupt is to explicitly set its priority to be below the kernel aware level。

🎼You configure the interrupt priority in the QF on startup callback。🎼。

🎼The GIOF priority can be the same as。🎼う。🎼，🎼The。Or perhaps one level lower。

 which means bigger priority number in cortex M。And one last step for the GPIO interrupt is to explicitly enable it in the NVIC as follows。

When you try to build the code， the compiler complains that the SW1 S object is undefined。Well。

Indeed， the Semahor object is defined only in main that C。

 And so BSP that sea does not know about it。You can easily fix it by placing the declaration of the Semapho object into BP。

h headerophil， which is included in both main。c and BP。c。However， when you build the code again。

 the compiler still complains， but this time about the QX semimapho type being gun defined。

This type is defined in the QPC。 H h file so you can fix this problem by making sure that BSP。

h is included after QPC。 H。While you are edit， you can also remove the SDDN dot H head file because it also is already included from QPC do H。

One more build， and。Heluja， the code finally builds with zero errors and0 warnings。

I'm not sure about you， but I'm really curious how the code will work。

🎼So let's load the code into the board and open the debugger to perform the basic sanity checks。

To do this， I set breakpoint at the most important junctures。

 that is at Semapho weight inside Blinky 2 and Semapho signal inside the GIO ISR。

 When I run the code， the first breakpoint hit is at the Semapho weight。

 This makes sense because the blinky2 thread should be blocked on the semapho。

To verify that the thread is indeed blocked， I move the break point to the first instruction after the semapho weight。

 When I continue now， the program runs without hitting any break points。 This makes sense again。

 because the semapho has blocked the thread so the break point past the weight call cannot be reached。

 Now， I press the S W1 button and。As you can see， the code hits the breakpoint at some signal inside the GIO ISR。

 This is excellent because it means that the GIO interrupt has been configured correctly。

When you continue from signaling the semapho， you immediately hit the breakpoint inside Blinky2。

 This means that the semapho weight has been unblocked and the code past it started to run when you run the program from here。

Again， no breakpoint is hit。Until SW1 is pressed again。

At which point the break point at samapho signal is hit。 When you continue again。

 you immediately hit the break point past samapho weight。 This proves that indeed。

 the execution of the blinky2 thread is synchronized with signaling the semapho。

 and by this mechanism to the pressing of the S W1 button。Okay。

 so let's run the code free and leave the debugger to inspect the timing of this code in more detail using the logic analyzer。

When you open the logic analyzer with the identical setup as before。

 at first you don't see any activity。But let's change the trigger to auto。And now， as you can see。

 the green LED is toggled from your blinky one thread as before。

 and so is the red LED toggled from the idle callback。On the other hand， the ISR pin is not toggling。

 but rather is stuck high， and also the blue LED is not active at all。

 but this is exactly what you changed。 In particular。

 the previous trigger was set up to use the rising edge of pin 4。

 which was toggled from the cysttic interrupt。 Now the pin is used for the SW1 switch， which。

 as you can see， is normally high and should go low only when you press the switch。Therefore。

 let's adjust the trigger to the following edge of P4。

 which as you recall is also the trigger for your GPIOF interrupt。

So let's run with these adjustments while repeatedly pressing the SW1 button。

As you go through the collected traces， you can see that most of the time pressing of the button caused the ISR to go low and the blue LED started to toggle for about 8。

5 milliseconds gave what take a few milliseconds for preemption。

When the button press came while the blinky one thread was not running。

 the By2 thread started to toggle the blue LED immediately。However。

 when the button press happened while Blinky 1 was running。

 the Blinky2 thread had to wait until By1 voluntarily blocked。

This is because QXK is a preemptive priority based kernel。

 fully compliant with rate monoonic scheduling RMS。

 and so it always executed the higher priority Blinky1 thread as long as it wanted to run before executing the lower priority By2 thread。

For today's lesson， which is about understanding samaphoes。

 I'd like you to remember that unblocking a samaphore that is waiting inside the lower priority thread might be delayed by all higher priority threads。

Now， when I was pressing the SW1 switch and collecting the traces。

 you might have noticed some anomalies。For example。In race 12。

 you can see that the blinky two thread is running twice as long as usual。

 I am sure that you want to know why。Well， when you zoom in。

 you can see that the following of the ISR line is not clean， but rather shows some strange spikes。

These spikes are even better visible in the analog wave form of the same signal in the upper part of the plot。

 which I specifically provided for today by probing the P4 pin from the bottom of the board。Well。

 it turns out that this is a well known property of all mechanical switches。

 which sometimes momentarily bounce before establishing the permanent contact。

The problem is that for the fast CPU， these bounces look like multiple presses and releases of the switch instead of the expected single press or single release。

The subject of filtering out the noise created by mechanical switches is quite interesting。

 and you can read about it by searching the web for debouncing。

Let me only mention here that you should definitely not release any production quality software with the current implementation。

 and instead you should properly deouncece all your switches in software。 however。

 for this lesson I chose exactly to use the noisy signal because it provides more extreme stress test for your sepho and in doing so it will allow you to gain a deeper understanding of how a sepho works。

Specifically， in this particular situation， you see three falling edges in the ISR line。

 which means that the samapho was signaled three times from the GI O F interrupt。 However。

 the blinky2 thread went only two times around its while1 loop。 So let's find out why。

A good way of thinking about the semaphore is that it is a protocol of exchanging tokens according to the following rules。

The signal operation adds the token to the semaphore。

 but only up to the maximum configured count number。

The weight operation removes the token from a semaphore if any tokens are available or it blocks if no tokens are available。

So let's see how this works in this particular case。Before the switch was pressed。

 the semapho had no tokens， so the blinky2 thread blocked on the Semapho weight operation。

The first following edge caused the GPIOF interrupt to signal the sepho， which added one token。

This has immediately unblocked a Blinky2 thread， which still inside the weight operation took the token out of the semapho。

The next bounce caused the GPIO FISR to signal the semapho。

 which again added one token to the empty semapho。But this time。

 the blinklinky2 thread was already running and didn't yet execute the semapho weight operation to remove the token。

 so the token stayed in the semapho。The third bounce caused the GPIO F the ISR to signal the semapho again。

 but this time the semapho already had one token and could not accept another because it was configured as a binary semapho。

 with the capacity to hold at most one token。The blinky two thread kept running and looked back to the top of its wild1 loop and called the Semapho weight operation。

This time， the token was immediately available in the semapho。

 So the weight operation just removed the token， but didn't block。

 Blinky 2 continued through the loop the second time， Eventually。

 Blinkki2 looped back to the top of its while1 loop and called semapho weight operation for the third time。

This time， however， the samapho was empty and so blinky too blocked。

But this is only one way the scenario can play out。 It turns out that due to threat preemption。

 essentially， the same three bounces of the switch can lead to quite a different outcome of Blinky 2 going just once through its wild one loop instead of twice。

An example of such a scenario is trace number6。🎼う。Here。

 the switch bounced while it was released as opposed to being depressed。

 but still it produced three falling edges。 and consequently， the semapho was signaled three times。

But let's analyze this trace in detail。As in the previous case， initially the semapho had no tokens。

 so the blinky tooth blocked on the semapho weight operation。

 the first falling edge caused the GPIOF interrupt to signal the semapho， which added one token。

But this time， the By two thread could not run immediately because it could not preempt the higher priority By one。

 which happened to be running。 Therefore， the weight operation was not performed。

 and the token was not removed from the semaphore。The next following edge caused the GPIOS interrupt to signal the semapho。

 but this time the sepho already had one token and could not accept another。

The same exact thing happened by the third bounce of the switch as well。

The high priority Blinky1 thread kept running， but finally blocked on the delay operation。

 Only at this point， the preemptive Qx K kernel scheduled Blinky 2。

 which unblocked and removed the token from the semaphore。Finally。

 Blinkki2 looked back to the top of its wide1 loop and called the Sammapho weight operation。

 This time， the Sammapho was empty and so blinklinky2 blocked。

This concludes this lesson on Semaphoce as the first of the many inter threatreat synchronization mechanisms you need to learn。

In the next lesson， I'm going to talk about sharing of resources among threads and about the artist's mechanisms for guaranteeing the mutually exclusive access to such shared resources。

If you like this channel， please subscribe to stay tuned。 You can also visit statemachine。

com/quistart for the class notes and project file downloads。



![](img/d1a29066a685ed4051b59e7708f0d42b_12.png)