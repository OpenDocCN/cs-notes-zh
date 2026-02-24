# Quantum Leaps《现代嵌入式系统编程Modern Embedded Systems Programming》中英字幕 p16 -16-#15 Startup Code Part-3_ exception handlers, interrupt handlers.zh_en -BV1fRt2efEms_p16-

🎼Welcome to the modernern Emd System programming course。 My name is Mirosak， and in this lesson。

 I'll finish the subject of the startup code。🎼Today。

 you will learn how to properly initialize the vector table with the correct stack pointer and all interrupts available in your O Tva C microcrocontroller。

🎼You will also see how to write and test the exception handlers so that they actually do what they are supposed to。

As usual， let's get started with making a copy of the previous lessons 14 project and renaming it to lesson 15。

 If you are just joining the course， you can download the previous projects from statemachine do com squiickstart。



![](img/e4f515acb92e86143a4edc429fcee6e2_1.png)

![](img/e4f515acb92e86143a4edc429fcee6e2_2.png)

Get inside the new lesson 15 directory and double click on the workspace file to open the IR toolet。

 If you don't have the IR tool set， go back to lesson 0。



![](img/e4f515acb92e86143a4edc429fcee6e2_4.png)

To quickly summarize what happened so far at the end of the last lesson。

 you have added a new file named Startup underscore T M4 C do C to your project in which you have defined the vector table as a constant array of integers。

 The focus of the previous lesson was to make sure that this new vector table from start underscore T M 4 C was linked instead of the generic one from the IR library。

And that it was located in the section dot in fact at address 0。

But the new vector table was not initialized properly yet。

So the first order of business today will be to provide the right initialization。

To remind you quickly how the vector table should look like。

 let me open the relevant section in the TM4 C data sheet。

Please remember that most pictures showing memory layouts in data sheets are drawn with low addresses at the bottom and high at the top。

 which is upside down compared to how you initialize variables in C or how you view them in the debugger。

So with this in mind， you can see that the very first value in the vector table should be the initial value of the stack pointer at address 0。

And the next is the address of the reset handler， at address 4。So going back to your startup file。

 the first task will be to initialize the stack pointer correctly。

 The challenge here is not to break the compatibility with the standard IR Lier script editor， where。

 as you might remember from the last lesson， you can set the C stack size。

To get an idea how to initialize the stack pointer in a way that's compatible with the IR tool set。

 lets step back and load the workspace from lesson 13。

 which still used the default startup code from the I library。



![](img/e4f515acb92e86143a4edc429fcee6e2_6.png)

![](img/e4f515acb92e86143a4edc429fcee6e2_7.png)

![](img/e4f515acb92e86143a4edc429fcee6e2_8.png)

When you loaded all the code to the launchpa board and looked at address 0 in this assembly。

 you can see that the first entry of the vector table is C stack dollar dollar limit。

This is an interesting observation because it indicates that the simple C stack de limit is known to the linker。

So let's reload the most recent workspace and try to use the symbol C stack limit to initialize the stack pointer。



![](img/e4f515acb92e86143a4edc429fcee6e2_10.png)

But before hacking the code， let's read some IER Help。

 click on Help Contents menu and choose the IER C Laguage Exs section。When you read it。

 you will find out that the IR linker generates symbols。

 section name dollar dollar base and section name dollar dollar limit for every section defined in the program。

 The linker places the symbols at addresses corresponding to the base and limit of the section respectively。

The way it works for the C stack section is shown in the following picture。

 The linker creates symbols C stack dollar dollar bay at the beginning of the C stack and C stack dollar dollar limit at the end of the C stack section in memory。

Please note that on the arm processor， the stack grows from high rem to low rem。

 so the initial stack pointer needs to be set to the address of C stack dollar dollar limit。

So finally， back to the code， let's just try to initialize the stack pointer entry in the vector table to the address of the C stack dollar dollar limit symbol。

When you compile a code by pressing F7， you get the compiler error that the symbol C stackag dollar dollar limit is undefined。

This error should actually make sense because the section symbols are created by the linker after the compilation。

 so the C compiler upstream the built process does not know about them。

So you need to somehow inform the compiler about the existing CSt dollar dollar limit symbol。In C。

 you do this by a declaration of the symbol as a variable。So far in this video course。

 you have only used variable declarations that were definitions at the same time， like so。

But this won't do in this case because a variable definition introduces a new variable。

 which will cover the symbol defined by the linker。Instead。

 all you want is to simply introduce the symbol to the compiler without creating it and allocating storage for it。

In C， this can be achieved by means of a variable declaration that is not a definition。

 C provides the special keyword external， which you place in front of the variable definition。

Note that a declaration still needs to specify the type of the variable， such as end here。

 but in this particular case， the type does not matter。

 as you are only interested in the address of the variable。When you try to compile now。

 you see that the symbol is recognized， but the compiler now complains that a pointer to int can't be used to initialize entity of type end。

 which is the type of the vector table。 The simple solution is to apply an explicit cast to int。

After which the compiler is happy and also the program links correctly。

 meaning that the linker could also successfully resolve the Ctag dollar dollar limit symbol。

Im sure you are curious whether your stack pointer initialization really worked。

 so let's load the code into the launchpa board。Well。

 as you can see that this assembly view shows C stack dollar dollar limit at Ad 0 as expected。

 and the value in the S register is hex 20，0，0，0410， which looks like a top of stack。Indeed。

 when you inspect the Lier MA file， you can see that the linker created simple C stack Do dollar limit is allocated at the address Hex 2000410。

 which is exactly what you saw in the SP register。To prove beyond any doubt that you have not broken the compatibility with the Liscript editor。

 let's change the stack size through the IDdeE。As you close the dialog box。

 the stack size changes in the link script as well。Now。

 rebuild the project and verify that the address of Ctag dollar dollar limit has increased to hex20。

0，0，0，428。Finally， load the code again to the Lapad board and check that the new value in the SP register is exactly Hex 20000428。

Okay， you are done with the stack now。 So let's move on to initialization of the exception and interrupt handlers that follow in the vector table。

 According to the Tva C data sheet。 The first handler to initialize is reset。

Which is located immediately after the stack。The meaning of the reset handler is that it is the initial value copied to the PC register when the microcontroller comes out of reset。

 So this is the address in Ram， where the arm cortex M processor starts executing code。

Just like with a stack pointer， let's first look at the default initialization of the reset handler from the standard IER library。

So here is the disassembly view of the standard vector table， which you use back in lesson 13。

As you can see， the reset handler was set to underscore underscore IR program Start。

 which is the startup code you learn about in lesson 13。

This startup code provided everything you needed， so let's reuse it in your custom vector table as well。

But how can you obtain an address of a function such as IR program start in C？I mean， so far。

 you've only learned how to call functions， but you have never had a need to access the address of a function before。

It turns out that C allows you to take an address of a function。

 just like it allows you to take an address of a variable。For example。

 you can take an address of IER program start and use it to initialize your vector table like this。

Again， similarly as with the C stack limit symbol， you need to declare the symbol IER program start as a function by providing its prototype。

When you attempt to compile the code now， you get an error that the funny looking type， void。

 star in parentheses， void can't be used to initialize an int。This is， again。

 similar to what happened with a C stack limit symbol。

 Except now the pointer type is more complex because it is appointed to a function that takes void arguments and returns a void rather than a simple pointer to an int。

I don't want to go into details how you can declare such pointers to functions as independent variables because it is not needed to understand the code at hand。

I will leave pointers to functions for another lesson。For now to get rid of the error。

 I will apply an explicit cast to int just as I did with the sea stack limit。By the way。

 an address of a function can be obtained in C， even when you don't use the empersent in front of the function name。

This is allowed because a function name not followed by parentheses can't be misconstrued as a call to the function。

As you can see， the code without the impperscent compiles just fine。

 but I personally don't like this style and would not recommend it。Unfortunately。

 a lot of code out there， including vector tables from various silicon vendors， don't use emperss。

 So you definitely need to know about such possibility。

I simply consider the notation with Ampersand superiori because it is very clear that you mean an address of a function。

Needless to say， I will use ampersersonons in the rest of the vector table。But before moving on。

 I am sure you are curious whether the reset handleer initialization actually worked。

So when you load the code to your board， you can see that the program is stopped at IR program Start at address Hex1B8。

 which is the value in the PC。Also in the vector table at address 0。

 you can see both C stack limit and IAR program start。Finally， when you run the code。The LED blinks。

 so the code still works。Okay， let's now move on to the other entries that follow reset in the vector table。

 specifically I mean here entries with negative IRQ numbers such as NmiI， hard fault。

 memory management fault， Ba fault， usage faultult， S V， call， pens V and cysttic。

These entries in the vector table are common to all arm cortex and processors and are forhanding exceptions。

For example， in lesson 10， you encountered a stack overflow。

 When the S P register dropped below the start of Ram。

 the processor entered the hard fault exception， which you could see in the debugger。

You can read more about the exceptions and which errors they handle later in the data sheet。

 intersection， fault handling。Please note that the standard exceptions are arranged in the vector table not contiguously。

 but rather， there are gaps in the table marked as reserved。

 This is very important because you need to preserve this exact layout in your custom vector table。

Back to code。You initialize the standard exceptions in exactly the same way as the is exception。

 but you pay attention to all the reserved slots， which are typically initialized to 0。

As far as the prototypes of the exception handles are concerned。

 you don't need to declare them yourself because they are all provided for you in the T4C's Hereophile。

The names of exceptions and interrupt handlers are not arbitrary， but rather。

 they are all part of the CMCs standard。Using standard names is important when you want to use this startup code together with other components such as real time operating systems or other third party software。

Okay， so include the TM4 C CMC Her file in your startup code。Now。

 unlike the IAR program Start reset handler， which was taken from the standard IAR library。

 you actually need to write the code for the other exception handlers such as Heart fault handler。

The standard way to code an exception handler is to use an endless loop that ties up the CPU when the corresponding exception。

 such as heart faultt， is taken。This is convenient for debugging because when you break into such code。

 youll find it spinning inside the endless loop。Unfortunately。

 most people leave such code in the final product。 I am sure you have experienced devices that seemed to freeze and could not be used。

 not even turned off until the battery has been pulled out and inserted back in。

This is a classic example of denial of service due to incorrectly coded exception handlers。

So instead of an endless loop， I typically call a function named Ast failed that provides a common handler for all sorts of errors。

 including assertions that they hope to talk about in the future lessons。

I use aer failed because it is also used in many code libraries for arm。

 and it is already prototyped in the TM4CCC's header file。

Please note that a failed is only suitable for situations when you encounter an unrecoverable error and you don't want to continue。

In that case， the purpose of a search failed is to perform some damage control and most commonly。

 to reset the machine。The other purpose of assert failed is to report the error location and to record it in an error log。

 if possible。For this purpose， the function takes two arguments。

 appointed to a constant file name string and the line number at which the call occurred within the file inside the heart fault handler。

 The function is called with a fault name。And the underscore underscore line underscore underscore symbol。

 which is the standard pre processorcesor macro that results to the line number in which it appears。

 You can code all other fault handleers the same way。However。

 the vector table contains also exceptions that are not faults such as SVC handler。

 the Baman handler， pandas V handler and cysttic handler。Instead of treating them as false。

 what you ideally want is to provide an option for these handlers to be defined somewhere else in your program。

 but only if needed。If not used， you would like to provide a default implementation。

 which will indicate a fault of using an undefined handler。

It might seem like you can't have a cake and eat it too。

 but the IR compiler provides a very convenient way of providing the so called weak alias for a function。

For example， here are the weak aliases for the non fault exception handlers from your vector table。

The weak alias means that if a symbol remains undefined till the end of the linking process。

 the provided alias will be used。For instance， if SVC handler is not used。

 it will be replaced with unused handler。However， if the symbol is defined in the project。

 the weak alias is ignored， and the linker does not report multiply defined symbols。Of course。

 the alias itself must be defined。 So here is the definition of the unused handler。And finally。

 you also need the prototype of the unused headr at the top of the file。When you try to build now。

 you can see that the startup T4 C actually compiles cleanly。

 but the linker reports that AserRT fail is undefined。

This is to be expected because you obviously need to add that function to your project。

 But the question is in which file。I propose that you create a new file for the so called board support package。

That you save it as BP。c。And you add it to the project。As the file is specific to award word。

 it needs to include the T4 CMC's header file。You will put here the board specific stuff like your error and assertion handling policy。

You will also put here your specific interrupt handlers。

 so the file will come in really handy in the future。

Regarding the definition of the assert failed function。

 any damage control will really depend on your project。

 so you need to revisit this function after you carefully design your error recovery strategy。

In the end， however， you will typically need to reset the system for which the CMC standard provides a useful function called NviIC system reset。

As you can see， the project build succeeds with no errors and no warnings。As usual。

 after every incremental step， you need to check how the code performs on the target。

As you can see in the disassembly view， the vector table at address0 matches the initialization in your startup TM4c。

Specifically， the fault handlers。And the reserved vectors。

Match exactly the non fault handlers all show as de baggmon handler in the disassembly because they are all alias to the same address unused handler。

 And the I R Dbugger displaypls all of them using the first name in the alphabetical order。

 which happens to be de baggmon。And finally， you want to， of course。

 to run the code to see if the LED still blinks。 And so it does。

The next interesting test is to check the aliasing。

 You can do this by providing your own implementation of one of the non fault handlers。 For example。

 cystic handler， which you expect to be used instead of the alias。The code builts cleanly。



![](img/e4f515acb92e86143a4edc429fcee6e2_12.png)

And when you look into this assembly， you see your cystic handler instead of the debgman handler alias。

Again， when you run the code， the LED still blinks。I am afraid that at this point。

 you might think that you have tested your new stuff and you can move on to adding all other interrupt vectors。

But not so fast， you have tested neither any of the fault handlers nor your assert fault function implementation。

 so let's try to exercise these parts of your code。But this seems easier said than done。 I mean。

 faults simply don't happen in your primitive Blinky programme。

 So you would have to wait for for something very unlikely。

 such as a cosmic gray hitting just the right part of the silicon。

The answer is that you need to make it happen at your will。 scientificifically。

 this is called fault injection。So here is what you could do。

Set a break point at the beginning of the delay function。And run the code。

When the break point is hit just before the stack push instruction。

 change the SB register to Hex 2 followed by all zeros， which is the start of your Ram。Now。

 very carefully， single step through the code。Whoops， as the S drops below the start of Ram。

 the program jumps to hard fault handler。So far， this is exactly what you would expect。

But wait a minute。 The first instruction of Hartft handler is another push to the stack。

 So when you step again， you don't move forward。 Even if you run the program at full speed and break into it。

 you find it at the beginning of Hartft handler。 Well， I really hope that you know why。Yes。

 you are right。 The push instruction at the beginning of hard fault causes another fault。

 which reenters hard fault。 This is obviously not good because your assert failed function is not even called。

Instead， you have an implicit， endless loop and denial of service。

 something that you precisely wanted to avoid。How do you fix it， Well。

 you obviously don't want to access the stack in your fault handlers or in insert failed because the stack might be corrupted。

As described in the IR help， IER provides a C language extension called underscore Sta class。

 which tells the compiler not to use the stack for a given function。

A function designated as Staless violates the coding convention such that it is impossible to return from it。

But remember that you don't want to return from your fault handlers or from assert failed anyway。

 Instead， all you want to do is to perform some damage control， record the error and reset。

With this change， let's build and run the code again。First， check that the LED is still blinking。

And then stop the program， as before， set the break point at the beginning of the delay function and run the code。

After the break print is hit， change the S registered to Hex 2 followed by all zeros。

 which is the start of your RAM。

![](img/e4f515acb92e86143a4edc429fcee6e2_14.png)

Now， very carefully single step through the code as the last time the stack overflow that you have just created caused the hard fault exception。

But this time around， there is no stack push instruction。

 and the code proceeds to calling the assert failed function。Finally。

 a third failed does not access the stock either。 So it also successfully calls the NviC system reset。

 which succeeds because you find yourself at I R program start。 That is your reset handler。All right。

 So your code works and no longer seems to suffer from the denial of service problem。Unfortunately。

 you can see that of the most startup code examples distributed by the various silicon vendors。

That startup code is perhaps sufficient for debugging， but is inadequate for deployment in products。

So while my goal here is to give you startup code that you can take all the way to production。

 I'd like to make a larger point as well。I want you to develop a habit of exercising all parts of your code。

 especially parts that are executed infrequently like your fault handlers。To test in frequent events。

 you don't need to wait until they occur naturally。 Instead。

 use the fault injection method to intentionally cause errors at will。And lastly。

 I hope you start to see the benefits of having a single common error handler like Asert failed。

 One obvious advantage is that a single breakpoint at this function will catch all false errors and assertions during debugging。

I'm running out of time for this lesson but perhaps in the future。

 I will show you how to hardcode a breakpoint in arm cortex M。For now。

 I highly recommend that you always set a regular break point in a failed。

But back to your custom vector table， it has all the standard exceptions。

 but you still need to add all the interrupt handles that your processor supports。

I'm talking here about the entries marked as IRQ interrupt request in the data sheet。

When you go a couple of pages up， you will see the complete list of these interrupts。

Please note that this list also contains some reserved entries。

 which you mustn't forget to preserve the exact layout of the table。

Adding the actual interrupt handlers to the vector table is tedious。

 but does not introduce any new trick that you should know about。

 So I simply copy the list that I prepared in advance。

Please note that all the prototypes are provided in the TM4 CCMCs headerophil。

The final touch is to alias all the interrupt handlers to the unused handler。Finally。

 one last system build shows that the code compiles and links cleanly。

This concludes this third and last lesson about the startup code。🎼In the next lesson。

 I will introduce interrupts。If you like this channel。

 please subscribe to stay tuned you can also visit statemachine。

com/quiickstart for the class notes and project file downloads。



![](img/e4f515acb92e86143a4edc429fcee6e2_16.png)