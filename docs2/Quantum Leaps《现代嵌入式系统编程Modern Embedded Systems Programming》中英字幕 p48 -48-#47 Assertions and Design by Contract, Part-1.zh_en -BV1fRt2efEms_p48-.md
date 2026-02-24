# Quantum Leaps《现代嵌入式系统编程Modern Embedded Systems Programming》中英字幕 p48 -48-#47 Assertions and Design by Contract, Part-1.zh_en -BV1fRt2efEms_p48-

![](img/aff84b6f9eabd27c1b2e6965bdd84ce9_0.png)

，Welcome to the modernern embedded systems programming course。 My name is Miro Samak。

 and in this lesson， you'll learn about software assertions。 and more formally。

 the design by contract methodology in the context of embedded programming。

🎼This is part one of the two parts series on this subject。

The technique you are going to learn today is the single most valuable and effective strategy for delivering high quality code。

In my programming career， assertions and design by contract helped me more than any other programming technique。

 even more than my favorite state machines。Unfortunately。

 assertions seem to be the most important non practice in a valid software。

An alarming number of embedded developers haven't heard about assertions at all。Know about them。

 but still don't use them or use them incorrectly。So today， in part1。

 my goal is to explain what assertions and design by contract are and even more important what they are not。

And the proper use of assertions。In part 2， you'll see how to apply assertions and DBC in embedded C or C++ and other practical aspects of assertions in embedded systems。

So what are software assertions。Asertionions are boolean expressions that allow a program to check itself as it runs。

When an assertion evaluates to true， a program is operating as expected。 Conversely。

 an assertion evaluating to false indicates an error。

 and it makes no sense for the program to continue。

The C standard provides a simple assert facility to use these standard assertions。

 You need to include the asserted H standard header file。

 You then specify a Boolean assertion expression as the argument of the assert macro。For example。

 here you see a function in div that performs an integer division of x by y。

But the division is not defined for0 divisrs。 So you assert that y is not 0。

 You then print the x and y parameters and then return x divided by y。Of course。

 you can have more than one such assertion in a given file。

 So here you have another function to calculate integer log base 2。

 You've encountered such a function in the lessons about the arts。

 where it was used in the scheduler to quickly find the highest priority task ready to run。

 But anyway， a logarithm is not defined for a zero argument。 So you assert that x is not0。Moreover。

 the function here is implemented with a lookup table。

 So you additionally assert that you don't index beyond the end of the table。So now in main。

 you just call the div and log functions with various parameters and print the results。

The last two calls intentionally violate the assertions so that you can see what happens。



![](img/aff84b6f9eabd27c1b2e6965bdd84ce9_2.png)

Now， I will demonstrate how to build and run that simple program on a desktop computer from the command prompt using the Gcc compiler。

 The code will be provided in the lessonson 47 underscore Scdes directory。If you work on Windows。

 as I do here， you might not have the GCC compiler。

But one way of getting it is to download the QP bundle for Windows。

 which among others contains a Mk W GCC toolult。

![](img/aff84b6f9eabd27c1b2e6965bdd84ce9_4.png)

![](img/aff84b6f9eabd27c1b2e6965bdd84ce9_5.png)

You build the assert program with Gcc as follows When you run the assert executable。

 you can see that the program continues until an assertion fails。

 whereas the printout tells you the assertion expression and the line of code where the failure occurred。

In a regular run， the output produced by the program and the error message from the failing assertion are combined。

 but when you redirect the output into the SDD out and SDD error streams。

 you can see that the failing assertion sends the error message to the SDD error stream。

 whereas the normal output from the program goes to the SDD out stream。



![](img/aff84b6f9eabd27c1b2e6965bdd84ce9_7.png)

![](img/aff84b6f9eabd27c1b2e6965bdd84ce9_8.png)

Finally， you can see that the failing assertion apparently aborts the program because the final end output is not produced。

This is consistently with the premise that continuing after a failing assertion makes no sense。

The last feature of the standard assertions I'd like to demonstrate is the ability to disable assertions by defining the antibu macro。

 For example， in a command line option to the compiler。

This causes the assertion macros to expand to nothing。

 So assertions generate no code and no overhead。When you run the executable this time。

 you indeed no longer see assertion messages。Interestingly。

 now the program prints a logarithm of 0 as-1， so it survives the first error previously causing an assertion failure。

But the program does not survive the vision by 0 and silently aborts。

 You guess the programme was aborted only because the final printout end is still missing。

So this is all there is to the standard assert facility。 It is remarkably simple， but unfortunately。

 not directly applicable to embedded systems because they typically don't have the SDD Earth stream for assertion messages and cannot aboard the same way as desktop systems。

Later in this lesson， you will see an implementation that is much more appropriate for embedded systems。

But before that， I'd like to discuss the proper use of assertions。

To use assertions properly and effectively， you must clearly distinguish between programmed errors and exceptional conditions。



![](img/aff84b6f9eabd27c1b2e6965bdd84ce9_10.png)

Errors known otherwise as bugs are persistent defects due to design or implementation mistakes。

 For example， dividing by 0， overrunning an array index。

 dereencing a null pointer or using a peripheral before initializing it。

 when your software has a bug， typically， you cannot reasonably， un handle the situation。 Instead。

 you should focus on detecting， reporting and ultimately fixing the bug。Also。

 you typically cannot continue execution。 Instead， you must carefully devise a damage control strategy。

 This is where the assertions come in。In contrast to errors。

 exceptional conditions are specific circumstances that can legitimately arise during the system's lifetime。

 but are relatively rare and lie off the main execution path of your software。

Examples include incorrect user input。Transmission errors on inherently unreliable connections。

 such as wireless。Abnormal or degraded modes of operation， et cetera。In those cases。

 you should not use assertions。 Rather， you must carefully design and implement strategies that handle such exceptional conditions using a regular code。



![](img/aff84b6f9eabd27c1b2e6965bdd84ce9_12.png)

Attempting to un handle an error as an exceptional condition is just as bad as the other way around。

This programming style is known as defensive programming。

It aims to make the software more robust to errors by accepting a wider range of inputs or allowing an order of operations inconsistent with the program's state。

For example， a defensively programmed in function would not assert。

 but instead it would quote unquotehandle the zero divisor by returning some bogus value such as Hx F FFF。

Similarly， a defensively programmed in log 2 would quote unquote handle the below the range x by returning。

 say negative1， the above the range value by another made up value such as 9，9，9。

 and only otherwise the real value from the lookup table。

Another example would be the board support package functions for turning LEDs on and off on your O Tva C launchpad board。

Normally， these functions simply write to the GI registers。

 assuming that the GI openends have beenized。But coded defensively。

 these functions would check whether the GI was initialized and would silently perform the initialization if needed。



![](img/aff84b6f9eabd27c1b2e6965bdd84ce9_14.png)

Defensive programming is often advertised as a better coding style， but unfortunately。

 it hides bugs and frequently introduces new bugs due to the additional complexity。

Please also note that behaviors like reacting to incorrect user inputs or limping mode in a vehicle are always a result of intentional design and dedicated code。

Specifically， it is rather naive to expect that such behaviours could ever miraculously emerge from defensive programming。

Instead， it is far more likely that defensive programming will produce bogus incorrect results and undesirable behaviors。

But going back to assertions， a powerful methodology that takes assertions to the next level is designed by contract。

 DBC。Pioneered by Bertrand Mayor in the mid 1980s。A link to Btrand Mayor's article applying design by contract as in the video description。



![](img/aff84b6f9eabd27c1b2e6965bdd84ce9_16.png)

DBC views assertions as specifications of mutual obligations between software components。

 analogous to contracts between people。The central idea of this method is to inherently embed those contracts in the code as assertions and validate them automatically at runtime。

Designed by contract perspective helps you to truly understand software assertions。And that is。

 assertions are not an error handling mechanism。They neither handle nor prevent errors。

 just like contracts among people don't prevent fraud。For example。

 asserting that the divisor is not0 does not really prevent calling the int Dave function with0 divisrs。

Similarly， asserting that an array index is in range might give you a warm and fuzzy feeling that you have handled or prevented a bug when actually you haven't。

What really happened， however， is that you did establish a contract in which you spelled out that the parameter to your function and log2 must be in a certain range。

As long as assertions are enabled， the contract will be checked automatically and sure enough。

 the program will brutally abort if the contract fails。At first。

 you might think that this must be backward。 Cons not only do nothing to handle， let alone fix bugs。

 but they actually make things worse by turning every asserted condition， however benign。

 into a fatal error。However， police recall from the previous discussion that the first priority with dealing with errors is to detect them。

 not to hide them。

![](img/aff84b6f9eabd27c1b2e6965bdd84ce9_18.png)

To this end， a bug that causes a loud crash and identifies precisely which contract has been violated is much easier to find and fix than a subtle one that manifests itself intermittently with millions of machine instructions downstream from the spot where you could have easily detected it。

Also， as youll see in a minute， assertions can provide the last line of defense and an opportunity to perform corrective actions and damage control。

 In contrast， defensive programming surrenders to the bugs and does not offer such an opportunity。

Besides assertions as contracts， another insightful analogy is to think of assertions in software as corresponding to fuses in electrical circuits。



![](img/aff84b6f9eabd27c1b2e6965bdd84ce9_20.png)

Electrical engineers insert fuses in various places of their circuits to instill controlled damage。

 burning a fuse in case the circuit fails or is mishandled。

It is unimaginable to have any nontri circuit， such as a home wiring or electrical system of a car without many differently rated fuses。

Please note that the fuse can neither prevent nor fix a problem。

 So replacing a burnren fuse doesn't help until the root cause of the problem is removed。In fact。

 the terms bug and debugging originate from the actual bug found in the wiring。

 The problem was fixed only after removing the bug。

This concludes part one of the two parts series is about assertions and design by contract。



![](img/aff84b6f9eabd27c1b2e6965bdd84ce9_22.png)

In part 2， you will see how to apply assertions and DBC in embedded C or C++。

If you like this channel， please give this video a like and subscribe to stay tuned。

You can also visit statemachine dot com s video course for the class notes and project file downloads。

Finally， all the projects are also available on GitHub in a quantumntum Les Reository modern embedded programming course。

Thanks for watching。🎼う。🎼。

![](img/aff84b6f9eabd27c1b2e6965bdd84ce9_24.png)