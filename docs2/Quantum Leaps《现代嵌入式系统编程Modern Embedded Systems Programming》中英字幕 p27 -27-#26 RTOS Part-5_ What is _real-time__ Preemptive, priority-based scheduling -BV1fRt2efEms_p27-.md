# Quantum Leaps《现代嵌入式系统编程Modern Embedded Systems Programming》中英字幕 p27 -27-#26 RTOS Part-5_ What is _real-time__ Preemptive, priority-based scheduling -BV1fRt2efEms_p27-

![](img/06e8225d257bcb36b85766d3b4d75a33_0.png)

Welcome to the moderndern Emded System Program course。

 My name is Mirosak and in this fifth lesson on Artos。

 I'll finally address the real time aspect of the real time operating system name。

Specifically in this lesson， you will augment the Miros Art with a preemptive priority based scheduler。

 which can be mathematically proven to meet real time deadlines under certain conditions。🎼As usual。

 let's get started by making a copy of the previous lesson 25 directory and renaming it to lesson 26。

🎼う。🎼う。Get inside the new lessons 26 directory and double click on the microvision project lesson to open it。

To remind you quickly what happened so far in the last lesson。

 you added efficient blocking delay to the Miral's artist。 However。

 the artist is not yet worthy of its name because the round robin scheduler is not really real time yet。

 So let's start to day with introducing the concept of real time。Until now， in all your code。

 any computation that was performed was considered equally useful。

 and you cared only whether the computation was correct。

 but not whether it was performed within a given time。

 real time adds the timeliness requirement to the computations。Specifically。

 a computation that is performed too late or too early for that matter is considered less useful or even harmful as an outright run computation。



![](img/06e8225d257bcb36b85766d3b4d75a33_2.png)

Here is a graphical representation of the real time usefulness of a computation as a function of time。



![](img/06e8225d257bcb36b85766d3b4d75a33_4.png)

In the so called hard real time systems， a computation is useful from the triggering event up to the deadline。

 After the deadline， the usefulness of the computation becomes negative infinity。

 which means that the computation is worse than useless for that， its usefulness would be merely0。

 A missed deadline represents a system failure。 For example， deploying an airbag too late。

 is not just useless。 It is disastrous。But there are also soft real time systems where timeliness is also important。

 but the deadline is not as firm。 For example， a text message is expected to be delivered somewhat timely。

 say within 20 seconds， but it is still useful much longer。

 although its usefulness diminishes with time in the following discussion。

 I will focus on hard real time systems。From the historical perspective。

 mainstream use of computers in hard realtime systems started in the 1960s and 70s。 For example。

 the Apollo program used two identical real time computers。

 one in the command module and another in the lunar module。

 Here is a picture of Margaret Hamilton who led much of this effort with the stack of code listings showing how much real time software was created during the 1960s and early 70s。

Already in these early days， people realize that most real time systems operate in a periodic fashion。

 meaning that the triggering events and the deadlines repeat with a certain period。For example。

 lending a spacecraft on the lunar surface required fine corrections to the rocket thrusters that the onboard computer had to perform every few milliseconds。

 Similarlyly， industrial processes require periodic control ranging from milliseconds to tens of seconds。

Electronic control of combustion engines requires periodic control synchronized with the revolutions of the engine and so on。

To better understand how the real time concepts apply to periodic threads。

 let's perform a few experiments with your current version of the Mirals Artis。Specifically。

 you can increase the system clock tick rate to1 thousand times per second。

 That is one clock tick per millisecond。Next， you can modify your By1 and By2 threads so that they actually put some computational load on your CPU。

 because right now they only turn the LED on and off， which takes a microsecond。

 after which the thread blocks and relinquishes the CPU。

In order to simulate a more realistic CPU loading， you can turn the LED on and off not once。

 but a few thousand times in a for loop。 This particular fall loop will take about 1。

2 milliseconds to execute， which is intentionally slightly longer than your system clock tick After the for loop。

 they blink you one thread delays for one clock tick which will block until the very next cystic interrupt。

 This means that the body of the while1 loop will repeat with a period of2 milliseconds。



![](img/06e8225d257bcb36b85766d3b4d75a33_6.png)

![](img/06e8225d257bcb36b85766d3b4d75a33_7.png)

At this point， let me introduce a few symbols commonly used in the literature to characterize a periodic real time thread like your blinky one。

The time of computation of thread1 is denoted C1 and is equal to 1。2 milliseconds。

The period of thread1 is dened T1 and is equal to 2 milliseconds。And finally。

 the processor of utilization of Tread1 is denoted U1 and is the ratio between the time of computation and the period。

 This is the percentage of the time the CPU spends executing T1 and is 60% in this case。

Similarly to Blinky1， you can modify Blinky2 thread to simulate a CPU load that runs three times longer than Blinky1。

 that is for about 3。6 milliseconds。After the for loop。

 the blinky to thread will delay for 50 milliseconds so that its total period will be about 54 milliseconds。

In the diagram， the computation time of blinky2， C2 will be 3。6 milliseconds。In its period。

 T2 will be 54 milliseconds。 The CPU utilization of By2 U2 will be 6。6%。

One last thing before building the code is to comment out the wait for interrupt instruction in the OS on Ile callback。

This will prevent the CPU from stopping and will allow you to see the toggling of the red LED from the idle thread in the logic analyzer view。

The code builds correctly so let's load it into your Tiva C launchpaboard and see how it runs using a logic analyzer。

The top trays labeled ISR corresponds to the cystic handler， and it repeats every1 millisecond。

 This is your fast thousand times per second system clock tick。

The traces immediately below labeled T1， corresponds to blinklinky 1。

 and most of the time it runs for about 1。2 milliseconds。It repeats every 2 milliseconds。

The trace below labeled T2 corresponds to By 2。 This thread runs for about 3 to 4 milliseconds。

 not counting the gaps。🎼T2 repeats every。55 milliseconds。Finally。

 the button trace labeled idealde corresponds to the idle thread。

 and it runs only when no other thread or ISR is running。

But the most interesting part of the logic analyzer view is the time when Blinky 1 and Blinky2 are both unblocked and ready to run at the same time。

When you zoom in， you can see that Blinky 1 starts running but is scheduled out on the next clock tick at which point Blinky 2 is scheduled to run Blinkki 2 also runs only for one tick and only then Blinky 1 is scheduled in again to finish the processing。

 after which it blocks， so Blinky2 runs for the rest of the time slice。On the subsequent clock tick。

 Blinky1 becomes ready to run again， but notice that this is the third tick from the previous activation。

 which means that Blinky1 misses its 2 millisecond deadline by one tick。

This happens because the current scheduler inside the mineralrals Arts is still round robbing。

 This scheduler was designed for time sharing systems。

 where the most important goal was to share the CPU fairly among all threads。 Therefore。

 the scheduler takes the CPU away from the By1 after it exhausts its time slices。

 but this is not what you want in the hard real time system。 For example。

 suppose that the By1 represents an important thread that controls lunar module's descendcent on the moon's surface。

 It has to run every 2 milliseconds。 and missing even one of these deadlines can cause a catastrophic system failure。

 In that case， you don't care about the fairness of CPU assignment。

 You care about meeting your 2 millisecond hard real time deadline。For this。

 you will need a different scheduler which somehow knows about the importance of the threads so that it can execute a more important thread before executing a less important thread。

Today， you will implement the simplest version of such a real time scheduler called priority based Preemptive scheduler with static priorities。

 This means that each thread will be assigned the unique priority number when it is started。

 and this priority will not change thereafter the job of the scheduler will be to always run the highest priority thread that is ready to run。

Let's see in a timing diagram how your blinky threads would execute under such a priority based scheduler and how the timing would differ from the current round Robbin scheduler。

As long as the thread T1 remains the only one ready to run because T2 is blocked inside the OS De function。

 the execution is identical under both schedulers。But as soon as T2 becomes ready to run。

 the round Robbin scheduler suspends T1 and schedules T2 Alread at this point。

 T1 loses its chance to meet the2 millisecond deadline。In contrast。

 the priority based scheduler also sees that T2 is becoming ready to run。

 but T1 has a higher priority， so the scheduler chooses T1 to run。 Therefore。

 T1 continues and easily meets its2 millisecond deadline。

The T2 thread is scheduled only after T1 voluntarily blocks in the OSs delay function。

 but as soon as T1 is unblocked again， the scheduler immediately switches back to T1 because it has higher priority than T 2。

 The situation repeats as long as T2 eventually blocks as well。But interestingly。

 notice that even though T2 is significantly delayed by constant interruptions from T1。

 it too eventually completes and blocks way before its deadline of 54 milliseconds。

 This means that the priority based scheduler executes T1 and T2 in such a way that they both meet their hard drill time deadlines。

So now let's actually implement the priority based scheduler in the Miros Arts。

The first thing is to bump up the version number and add the thread priority to the thread control block into to the OS thread start function。

 the priority number will be a small integer in the range from0 to the number of supported threads。

 which is 32 in the Miros arts， so it will comfortably fit in a UN A type。

🎼In the artist's implementation。You also need to bump up the version number。

And add the priority parameter to the OS thread start function。Here。

 you also need to redesign the use of the O thread array。

As you perhaps recall from the last lesson 25， the OS thread array holds pointers to all thread objects that have been started in the round rubbing scheduler。

 the array was filled consecutively from index 0， which was reserved for the idle thread up to the index OS thread nu。



![](img/06e8225d257bcb36b85766d3b4d75a33_9.png)

![](img/06e8225d257bcb36b85766d3b4d75a33_10.png)

For the priority based scheduler， the difference will be that the indexes into the OS thread array will be the thread priorities。

 and that these priorities don't need to be consecutive。

 meaning that there could be gaps in the OS thread array， for example。

 the picture shows the idle thread at priority0， Blinky2 at priority 2。

 Blinky1 at priority 5 and thread N at priority N。

![](img/06e8225d257bcb36b85766d3b4d75a33_12.png)

This means that you replace the OS T nuum index with the priority number passed as the function parameter。



![](img/06e8225d257bcb36b85766d3b4d75a33_14.png)

Also， you need to save the user specified priority into the threat control block。However。

 to avoid overbooking of the OS thread array， you must now make sure that not only the priority level is in range。

 but also that it is not already used， meaning that OS thread at the priority index is still a0 pointer。

You can move this assertion to the top of the function and make it into a precondition that you code with the Q required macro introduced in the last lesson。

Precondition means that it must be satisfied by the color of the function。

 not by the function itself。 For example， it is the job of the application programmer to assign a unique priority to each thread。

Now， let's think for a minute about the use of the OS ready set pitmk。

For the priority based scheduling， the most interesting information will be to find the highest priority thread that is ready to run based on the current value of the bitmask。

At this point， you need to decide about your preferred priority numbering scheme。

For historical reasons， many artes you might encounter such as nucleus， Tx， microcoOS。

 Ambos and others use the inverse priority numbering scheme where priority0 corresponds to the highest priority thread and higher priority numbers corresponds to lower priority threads。

 needless to say， the inverse priority numbering scheme leads to constant confusion when talking about higher and lower thread priorities。

But it is of course possible to use a simple direct priority numbering scheme where priority0 corresponds to the idle thread and higher priority numbers corresponds to threads of higher priority。

 the Miros Arts will use this simple direct priority numbering convention。

The basic principle of finding the priority number of the highest priority thread that is ready to run will be to count the leading zeros in the OS ready set bit mask up to the first one bit and subtracting it from the total number of bits。

 which is 32。For example， if the blinky2 thread is the only one ready to run。

 the OSs ready set bitm would have all zero bits except bit number1。 In this case。

 the count of leading zeros is 30， which can be converted to the priority number by subtracting it from the total number of bits of 32。

 If the blinking one thread with priority5 is ready to run the OSs ready set bitm will have 27 leading zeros up to the first one bit。

 which converts to the priority number of 5 by subtracting it from the total number of bits of 32 in the general case of a thread with priority n being ready to run the count of leading zeros will be 32 minus n so that the priority number works out again as 32 minus the count of leading zeros in the OS ready set bitm。

The formula works even for the idle condition of the system where all 32 bits in the OS ready set bitmask are 0 which results in a priority of 0。

 that is the priority of the idle thread。Mathematically。

 the formula 32 minus Cz of x that finds the most significant1 bit in the number x is the integer approximation of the log base 2 function。

 and that's why I will code it as the log 2 macro in the Miros do C implementation file。Of course。

 the algorithm is only as fast as the count leading zeros operation。

 but it turns out that your arm cortex M4 processor supports it in hardware as the CLZ instruction。

You can actually find this instruction in the data sheet of your TVC microcontroller。

To take advantage of the CLZ instruction you can search the compiler help for CLZ As you can see。

 this particular compiler support it through the intrinsic function underscore underscore CLZ。

With the very efficient log to operation， you can now implement the priority based scheduler。

 as before when the scheduler detects the idle condition of the system。

 it needs to choose the idle thread。 But now you no longer use the OS curve IDX variable。

 So you just directly set OS next to OS thread of 0， which is the idle thread。Otherwise。

 if some threads are ready to run， you use the log 2 macro with the OS ready set argument to find the highest priority thread that is ready to run。

 please note that the log 2 macro is guaranteed to produce a number between 0 and 32 inclusive。

 so it can be used directly as an index into the OS thread array without rain checking the index。

At this point， it is also a good idea to assert that the OS next pointer is not0。

The final change is redesigning the OS T and OS delay services。

 This is necessary because both implementations currently assume that the OS T array is populated consecutively up to the OS Tread nuum level。

 which is no longer the case。In OST， instead of iterating over the whole OS thread array with potentially big gaps of unused priority levels。

 you can leverage the fast log to operation。Specifically。

 you can introduce a bitm of delayed threads， which is similar to the OS ready set。

 except it holds the delayed threads。While you are edit。

 you might also remove the no longer needed variables OS cur IX and OS Tread nu。

With the OS De set bitmask in place， the OST function will iterate only over the1 bits in the bitm instead of scanning other bits。

 but because you will need to remove the already processed bits from the bitmask。

 you need to use a temporary bitm working set。You loop as long as the working set has some bits set。

 meaning that some threads are delayed and need processing a this clocktic。

You first quickly obtain the number of the highest order 1 B in the working set using your fast log 2 macro。

 and you use it to index into the OS thread array。 You save the obtained pointer in the temporary variable T。

 You then assert that the T pointer is not0， meaning that the thread is in use。

 and you also assert that the timeout of this thread is not0 because it must be a delayed thread。

Next， you dec a timeout counter for this thread and if it becomes zero。

 you make the thread ready to run by setting the corresponding priority bit in the OS Ready set bitm。

At the same time， you'll remove the same bit from the OS delayed set bitMk because this thread is no longer delayed。

Finally， you always remove the same priority bit from the working set because it is now processed。

To avoid the apparent code duplication， you can introduce a temporary variable bit like this。🎼Yeah。

In the OS De function， you need to replace the OS core IDX variable with the priority number of the current thread。

In addition to removing the priority bit from the ready set。

 the function now also needs to add the same bit to the OS delay set because this thread is now becoming delayed。

🎼And finally， to avoid code duplication， you can introduce a temporary variable bit。

 just like in OST before。🎼不出。🎼从出。🎼我。🎼是说出的。The priority based schedule of implementation is ready now。

 so let's try to build the code。The project fails to compile because the signature of the OS thread start function has changed with a priority based scheduler。

 each thread you start needs a unique priority to run it。

To remain consistent with the previously used diagrams， let's assign priority 5 to blink you1。

And priority 2 to blinky2。As you can see， the priorities don't need to be consecutive。

 What really matters is that they are unique and that the priority of By 1 is higher than priority of By 2。

There is still one more compilation error。You need to add explicit priority0 when starting the idle thread。

🎼The code builds cleanly， so let's see how it works。うん。어。First。

 I am sure you are curious about the code generated by the logg2 macro。

So let's set a break point inside the OS St function where the macro is used。

As you can see that this assembly starts with loading addresses of the OS thread array and the OS readyy set bitM。

 and then the whole calculation of the highest priority thread ready to run is accomplished with just two instructions。

The CLZ instruction counts the number of leading zeros in the bitmask and stores it in R0 in just one CPU cycle。

Similarly， the RSB instruction reverse Subtract。Converted to the priority number in r 0。

 also in just one CPU cycle。 The resulting priority in this case turns out to be 5。

 which you should recognize as the priority of blinky1。Indeed。

 the OS next variable is set to the address of the By one thread。When you finally run the code free。

 you can watch some activity of the LEDs on the board。

But to really see how your new priority based schedule works， you need to use a logic analyzer。

As you can see， the Blinky1 thread runs now completely undisturbed even when Blinky 2 becomes ready to run。

Blinkky one always meets its deadline。🎼，🎼Yeah。🎼And so does By 2。

 even though By 2 is preempted by By1 several times。Finally， the idle thread runs as well。

 but only when none of the other threads or interrupts are active。

It's nice to notice that this analysis trace matches exactly the timeline of the priority based scheduler you've designed earlier and subsequently implemented in the Mirals arts。

 At this point I would like to notice the absolutely critical importance of blocking for the priority based scheduler。

 A high priority thread runs for as long as it wants and no thread of lower priority can run until the high priority thread blocks and voluntarily relinquishs the CPU without the blocking。

 no lower priority thread will ever run。 For example。

 Blinky2 and the idle thread run only when By1 blocks and similarly。

 the idle thread runs only when both Blinky1 and By2 are blocked。

This is very different from the round Robbin scheduler。

 which executed audioio blinklinky thread in succession， even when they didn't block at all。

 So now you know why I had to implement efficient thread blocking in the last lesson 25 before introducing real time priority based scheduling in this lesson。

With the code working as expected， let's now focus on the most important decision you face when working with a priority based scheduler。

 and that is on how to assign priorities to your threads。

With just two threads like your Blinky 1 and Blinky 2， you have only two possibilities。

 Priity of Blinky 1 higher than Blinky2 and priority of Blinky 1 lower than By 2。 As you just saw。

 the first option meets both real time deadlines。On the other hand。

 it is easy to see that the second possibility of assigning lower priority to Blinky 1 than Blinky 2 leads to Blinky 1 missing its deadline as soon as Blinky 2 becomes ready to run。

So the role that emerges here is to assign higher priorities to threats with shorter periods。

 which means also shorter deadlines。It turns out that this rule has been discovered already in the 1970s。

 specifically in 1973， CL Liu and James W Layland published a seminal paper titled Schcheduling Algothms for Multiprogramming in Hard Real Time Enron。

 I provide a web link to this article in the video description。But basically。

 Lou and Leland described in this article that the simple static priority based scheduler that you've just implemented can be mathematically proven to meet all hard drill time deadlines for all threats under certain conditions。

The method was later generalized and called rate monoonic analysis。

 RMA or rate monoonic Schcheduling RMS， and has been very well explained in another articleRate monoonic analysis for Real Time System to which I also provide a web link in the video description。

I bring it up here because no discussion on the priority based scheduler can be complete without mentioning the RMA/ RMS method。



![](img/06e8225d257bcb36b85766d3b4d75a33_16.png)

The term rate monotonic RM derives from the method of assigning priorities to a set of threats as a monotonic function of the rate of a periodic thread。



![](img/06e8225d257bcb36b85766d3b4d75a33_18.png)

A function is called monotonic in mathematics when it preserves or reverses the order between two ordered sets。

 specifically RMA refers to priority assignment that maps increasing order of thread rates to increasing order of thread priorities。

 as such it is just a fancy name for the simple rule you have discovered yourself。

But there is of course more to RMA than this and the full discussion would be really out of scope for this short lesson for today let me just summarize the most important guidelines of the RM/ RMS method。

First， always assign threat priorities monotonically。

 meaning that threats with higher rates must run at higher priorities than threats with lower rates。

Second， you need to know the CPU utilization of each thread。

 which you calculate as the ratio between the measured execution time CN to the thread period TN。

And third， you need to calculate the total CPUU utilization as the sum of all individual CPUU utilization factors。

If this total utilization is below the theoretical bound。

 all threads in the set are guaranteed to meet their deadlines。

 This was already proven mathematically by Liu and Leland back in the 1973 paper。



![](img/06e8225d257bcb36b85766d3b4d75a33_20.png)

The utilization bound U of N depends on the number of threads N for the large number of threads。

 U of n approaches natural logarithm of 2， which is just under 0。7。 So in practice。

 if you stay below 70% of the CPU utilization， your set of threads will be schedulable。

 meaning that they will all meet threat deadlines。For example。

 the total CPUU utilization for your Blinky1 and Blinky2 threads is as follows。1。

2 millisecond over 2 millisecond for Blinky1 plus 3。6 milliseconds over 54 milliseconds for Blinky2。

 the total CPUU utilization is thus 0。66， which is below the theoretical bound。

Of course the basic R assumes periodic threads that execute in constant time。

 but the method can be extended to a pic threads with variable execution time in that case you need to consider the worst case that is the shortest time between the thread activations and the longest execution time。

Also， in practice， typically only a few highest priority threads have hard drill time deadlines。

 while other threads have only soft real time requirements；

 in that case you use R for the hard drill time threads and prioritize all soft real time threats lower。



![](img/06e8225d257bcb36b85766d3b4d75a33_22.png)

The beauty of preemptive priority based scheduling is that a high priority threat can always immediately preempt all lower priority threats。

 so a high priority threat is insensitive to changes in execution time or period of lower priority threats。

In other words， the preemptive priority based scheduler decouples threads in the time domain。

For all these reasons， the preemptive priority based scheduler became the norm and is supported in most real time operating systems to this day。



![](img/06e8225d257bcb36b85766d3b4d75a33_24.png)

This concludes this lesson on real time computing and the priority based scheduling。

In the next lesson you'll advance by another decade from the 1970s to the 1980s。

 when the commercial artes went mainstream and when inter threat synchronization and communication mechanisms have been added。

If you like this channel， please subscribe to stay tuned you can also visit statemachine。

com/quistart for the class notes and project file downloads。

