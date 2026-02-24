# Quantum Leaps《现代嵌入式系统编程Modern Embedded Systems Programming》中英字幕 p25 -25-#24 RTOS Part-3_ Automating the scheduling with round-robin policy.zh_en -BV1fRt2efEms_p25-

![](img/8f868de052174a5c30ceec5903a7f7b0_0.png)

Welcome to the modernern embeddedded System programming course。

 My name is Mirosak and in this third lesson on Realtime operating system Arttos。

 Ill show you how to automate the scheduling process specifically in this lesson you will implement the simple round robin scheduler that runs threads in a circular order along the way。

 you will add several improvements to the Miros Arts and you will see how fast it runs。As usual。

 let's get started by making a copy of the previous lesson 23 directory and renaming it to lesson 24。

Cut inside the new lessons 24 directory and double click on the microcrovision project lesson to open it。

To remind you quickly what happened so far， in the last lesson you started building a minimal real time operating system。

 abbreviated to mirrors。At this point， the Omiroos arttos can represent threads， can start threads。

 and can switch context from one thread to another。

But the scheduling of the next thread to run inside the OS SC function is still manual Today you will automate this as well so that mirrors will be able to actually run your threads at full speed。

For the specific situation of just two threads， Blinky 1 and Blinky2。

 you can simply hard code the thread scheduling with an if statement as follows if the current thread is Blinky 1。

 then set OS next to the address of Blinky 2。 Otherwise set it to the address of By 1。

 When you try to compile it fails because the Blinky 1 and Blinky 2 identifiers are not known to the compiler。

You can fix it by providing external declarations。Of course。

 typically you place such declarations in a header file。

 but at this point you just want to test the general idea of automatic scheduling。

The code builds correctly so let's just load and run it on your launchpad board。As you can see。

 both the green LED from the Blinky1 thread and the blue LED from the Blinky2 thread keep blinking simultaneously and independently from each other。

 so at least you know how their results should look like and that automatic scheduling is workable。

Now let's try to actually design it so that you don't hardcode the specific threads in the scheduler please note that at this point you don't want to change the behavior of the code。

 it already behaves according to your requirements instead you want to improve the internal design which is called refactoring。

Now there are of course many ways to do such refactoring。

 the central element is how you choose to organize the threads that are started in the OS thread start function。

Some arttoes out there organize the threads into a linked list。

 which is then traversed by the scheduler。But in view of the future direction for the Miros Arts。

 I suggest a simple brute force solution which is to store the thread pointers in a preallocated array。

 OS thread。Once the array is populated by the consecutive calls to OS thread start。

 the scheduler will then select the next thread to run in a circular fashion。

So the first thing you need is the OS thread array， which will be sized for 32 plus1 threads。

The maximum number of threads will become more clear in the future lessons。

 but for now just remember that the Miros arts can handle up to 32 threads。

The arts also needs to remember how many threads have been started so far。

 which it will keep in the variable O S thread nu。And finally。

 the scheduler needs to remember the current index into the OS thread array。

 which it will increment and wrap around in the circular fashion。

So now every time a new thread is started in OS thread Start。

 the me pointeder to the thread is stored in the OS thread array。

 and the OS thread nu counter is incremented for the next thread。At this point。

 you are making an implicit assumption that you are not overflowing the threat array。

Such assumptions should be enforced somehow。 The typical way is to check the index and return an error code to the color when it overflows。

But then the color can simply ignore the problem。A better way for such situations is to use assertions The C language provides a standard assert facility which evaluates the expression and when it turns out to be false。

 the assert macro prints a message to the screen and exits the application neither of these actions makes sense in a deeply embedded programming where you have no screen to print to and you cannot really exit either。

So instead， I use here an em embedded System friendly the assertion Q assert that simply checks the expression。

 and if it turns out to be false， it calls the special callbe function， Q on As。

You have this function already defining the BSsp。c file because the startup code is already using assertions。

This function can and should be carefully customized to your specific project。

 This is your last line of defense after the code already failed。 When this happens。

 you should try to do damage control and log or somehow output the location of the assertion。

 which is provided in the module and log parameters。 After this。

 you typically should reset the system to avoid the denial of service failure。

 I hope to talk more about assertions and the philosophy called design by contract in the future lessons。

But going back to the Miro's implementation to use the embedded System's friendly assertions。

 you need to include the QAsert。h header file。This file is located in QPC include directory。

 so you need to make sure that this directory is in your include search path。

Speaking of the QPC directory， please make sure that you download and unzipqPC from thestatemachine。

com/quistart webage。🎼The。Back to the implementation， to use assertions in a given file。

 you also need to define the name string for the file。

 would you do by placing the macro Q define this file at the top。Finally。

 instead of introducing the symbolic name for the number of elements in the array。

 such as Mac thread here， you can use the QD macro defined in the QSer H header file。

 which provides the array dimension without the need to introduce any additional symbolic names。

With this preparation in the OS thread start function， you can get to the most interesting part。

 which is the actual scheduling inside the OS S function。

Here you need to increment the index of the currently running thread。

 which you store in the OS curve IDX variable and wrap it around to0 when the index reaches the number of threads。

You finish the round dropping in scheduling by setting the OS next pointer to the thread at OS Cur IDX Index。

That all there is to it， you can now build and run the code。

The advantage of this design is that you no longer need to hard code the threads from the application because the Miros Arts registers every newly started thread and automatically included in the round roing scheduling。

In fact， to see how easy it is to add a new thread to the system let's create another blinky type thread。

 the new Blinky 3 thread will blink the red LED and will use a bit different delays for on and off timeouts to produce some interesting color patterns when combined with the other two blinky threads。

🎼う。As you can see， the addition of a new thread is confined to the main file and does not require changing any of the existing threads or the artists code。

This property of threads is called composability please note that threads became composable only after adding the arts。

 because without it you could not easily combine them to run seemingly simultaneously and independently from each other。

Okay， so now let's talk about the next aspect of the minerals arts that needs improvement。

 and that is the initialization timeline and specifically the configuring and enabling of interrupts。

Currently， the code starts and enables interrupts already in the PSP in function。🎼う。

This is too early。Because if an interrupt were to fire before you reach the end of main。

 such an interrupt might trigger a context switch which takes the control away from main and never really returns。

This means that some important initialization code might not get executed and some of your threads might not get started。

The correct timeline of Art's initialization is for the system to configure and start interrupt only after all threads have been started。

 this means that the right place to do this is at the end of main。

Here is also the place where you have the ugly while1 loop。

 so let's replace it with the new Arts API O run。As the name suggests。

 the OS run function is where you will transfer control to the artist and ask it to please run your threads At this point you are done with all initialization and you are ready to receive interrupts。

The implementation of OSR will begin with calling the OS on Start callback function。

Callbeck means here that the function will not be defined in the art itself。

 but rather you will need to define it in the application。

 the OS on Start function is where you will configure and enable interrupts。Next。

 the OSR function will call the scheduler to run the first thread。

This call will be identical as in your cystistic handler。

But this time you will call the scheduler outside the interrupt context。

I hope you remember from the previous lessons on Arts that the context switch can only happen immediately after an interrupt because the whole stack layout assumes that the thread is switched as a return from an exception。

But this is okay here because the scheduler is not performing the context switch directly。

 but instead it triggers the pensV exception which then correctly returns to the next thread to run the penV exception will run immediately after the interrupts are reenabled so the control will really never return back to OS run and consequently any code after that should never execute。

If this is so， then you can use an assertion that always fails； you could code it as Q insert0。

But the QS3。h head file provides a more descriptive assertion for such occasions called Q error。

🎼Yeah。To finish off， you still need to declare the prototypes of the new Arts APIs in the Mis。

h header file。When you try to build now， you fail because the OS on startup Calb function is missing。

This is a very good reminder that you still need to define this application specific function in your BP。

c file。To get the body of the OS on startup function。

 you simply cut and paste the portion of the BSP unit that deals with configuring and enabling interrupts。

The last instruction to enable interrupts is redundant because the OS run function disables and re enableables interrupts anyway。

う。This time the code compiles and links without errors or warnings。

 let's quickly step through the main parts of the code in the depacker。🎼う。

Place a breakpoint in OS run and watch how it disables interrupts and calls the scheduler。

The scheduler increments the OS Cur IDX index， checks for the wraparound and sets OS next to the address of Blinky2 threadread。

The next interesting breakpoint is inside Pice V handler。

 where you can see how it returns to the next thread。Which is blinky2 in this case。Finally。

 when you remove the breakpoint， you can watch the LEDs of all three colors blink as the three blinky threads run simultaneously。

As the Miros art finally runs truly autonomously， I thought that in the last couple of minutes of this lesson。

 you might be interested to find out how fast it is。For these measurements。

 I will use a mixed signal ocilloscope with a logic analyzer connected to the following pins of the TVC launchpad board。

The red LED， the blue LED， the green LED， a couple of ground pins。

 and Ill also use the Pf4 as the test pin。The first view shows the signals D1 through D4。

 which correspond to Pf1 through Pf4， and the line colors match the colors of the attached LEDs。

As you can see the signals change as the LEDs blink。

 but the changes are so slow that it's difficult to measure the context which time。

What you need is a much faster ongoing activity on each pin， such as to the pin up pin down。

 but without delays in between。🎼This is simple enough to achieve by simply commenting out the BSP delay function calls in the thread handlers。

But you would also need a trigger to know when the context switch occurs for this。

 you will need yet another test pin like the Pf4， which is still unused。

To provide the trigger for context switch， you can use a cystic handler to drive the test pin up。

🎼Hand down。Since the test pin is an output pin， you need to configure it as such in the BSP in function。

When you load this code to the board you get a very different picture。

 the LEDs all glow with varying intensity as they switch far too fast for the human eye to see the individual flashes of light。

In the logic analyzer， you can see the pins rapidly toggling up and down。

 but you can also clearly see that the activities are mutually exclusive。

 meaning that only one pin at theine keeps switching while others stay the same either up or down you can also see that the switching of activities occurs only when the line D4 corresponding to your test pin is activated。

 so let's set the trigger to the rising edge of D4。

Now the context which is always centered on the screen。

 and we can conveniently zoom in to see the details。So let's perform a couple of measurements first。

 let's measure the time between the last activity of the thread and the trigger。

 which is the beginning of the cystic interrupt。To see the measured value。

 I need to activate the analog view。And the value turns out to be around 400 nanoseconds。

To convert this value into the CPU clock ticks， you need to multiply the delay by the clock frequency。

 The basic rule of thumb is that every megahertz in clock frequency corresponds to one clock tick per microsecond。

Your TVVC launchpad runs at 50 megahertz， so you have 50 clock ticks per microsecond。

You multiply this by 400 nanoseconds， which converts to 0。4 microseconds。

 and the result is 20 clock cycles。Similarly， you can measure the time spent inside thesistic handler。

Which turns out to be about 1。6 microseconds。This corresponds to 80 clock cycles。And finally。

 perhaps the most interesting measurement is the context switching time after the cysttic exits。

 but before the next thread starts toggling a pin， this time turns out to be about 1。5 microseconds。

 which represents 75 clock cycles。The overall time between suspending one thread and resuming another is about 3。

5 microseconds。🎼う。Which represents 175 clock cycles。

This last measurement could be used to estimate the overhead of your arts。

 which is the ratio of the CPU time spent inside the arts for things like scheduling and context switching to the total CPU time this ratio is 3。

5 microseconds multiplied by 100 ticks per second and divided by 1 million microseconds in a second this turns out to be only 0。

00035 which is not even 110th of a percent。Even if you increase the system clockptic to 1000 times per second。

 that is to 1 kilohertz， the artist's overhead would still be only 0。3%。So as you can see。

 the overhead of the arts is quite small。😊，This concludes this lesson on round Robbin scheduling the Miros arts is getting better。

 but there are still huge opportunities for improvement the main such opportunity is to do something about the horrible waste of CPU cycles inside the DSP delay function。

With a context with magic under your control， you could use it to switch the context away from a delayed thread and switch it back only when the delay has elapsed。

 such efficient weighting is called blocking and it will be the subject of the next lesson on Arts。

If you like this channel， please subscribe to stay tuned you can also visit statemachine。

com/quiickstart for the class notes and project file downloads。



![](img/8f868de052174a5c30ceec5903a7f7b0_2.png)