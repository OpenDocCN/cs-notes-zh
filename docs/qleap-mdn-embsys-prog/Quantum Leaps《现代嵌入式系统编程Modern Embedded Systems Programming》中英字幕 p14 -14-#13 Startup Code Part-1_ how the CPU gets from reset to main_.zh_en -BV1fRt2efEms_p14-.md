# Quantum Leaps《现代嵌入式系统编程Modern Embedded Systems Programming》中英字幕 p14 -14-#13 Startup Code Part-1_ how the CPU gets from reset to main_.zh_en -BV1fRt2efEms_p14-

Welcome to the Modern embeddedded System Program course。

🎼My name is Miro Samock and in this lesson I'll talk about the startup code that is the code that runs even before the main function。

🎼Today you'll learn about the standard startup code that gets linked with your application from the IAR library。

🎼You will see how the startup code initializes the various data sections and you will see these sections in the Lier MA file。

🎼Finally， you'll go back all the way to the beginning of the reset sequence where you will encounter the vector table。

As usual， let's get started with making a copy of the previous lessonsson 12 project and renaming it to lesson 13。

 If you are just joining the course， you can download the previous projects from statemachine。

com/ Quickstar。Get inside the new lessons 13 directory and double click on the workspace file to open the IR tool set。



![](img/b9db09f19babb50f82324bf20e4e2597_1.png)

If you don't have the IR tool set， go back to lesson 0。 The latest version published by IER is 710。

 which I am using in this lesson。So far in this course。

 you have been always starting your debugging with the main function Today。

 you will explore the world before main。To do this。

 open the project optionstion dialog box and in the debugger section and check the Run to main option。

Also， make sure that the T iced St la debu driver is selected because for this lesson。

 you will need to use the real launchpa board as opposed to the simulator。While you are here。

 make sure that the Use Flash loaders option is selected。Finally， in the general options。

 revert from the cortex M0 experiment to the TM4 C device actually used on your Tiva C Lapadboard。

 Please note that this device uses the hardware floating point unit， FVPV4。



![](img/b9db09f19babb50f82324bf20e4e2597_3.png)

When you download your code to the board now， you can see that indeed you are not starting with main。

Instead， the first label in the code you hit is underscore underscore IAR program start。

 please also note that most registers are initialized to0， except the stack pointer SP。

 which seems to be initialized to a reasonable value inside the RA。



![](img/b9db09f19babb50f82324bf20e4e2597_5.png)

You will need to understand how that happened later in the lesson。 But for now。

 let's just quickly step through the code to get a sense what is going on。

The first interesting instruction you should recognize is BL branch with link。

Which is a function call。Here， the function being called is underscore underscore IR in it VFP。

 which initializes the hardware floating point unit FPU。

 I don't want to go into the details of the FPU here。

 but let me only say that FPU needs to be initialized early in case any code downstream such as main wants to use it。

The second interesting function call is to a question mark main。

 This is an illegal name for a C function， but I just want to remind you that we are here in the strange world before the C language。

 so the C rules for naming functions don't apply。This is an Ie R specific start up code。

 and they have chosen to call it questioned Mark Ma。 Let's step inside this time。

So here you have another function called to underscore underscore low level in it。

 This function is intended to perform a customized initialization of your hardware that either must occur very early on or can speed up the start process。

 For example， if you plan to increase the CPU clock speed。

 it's better to do it sooner so that the rest of the startup code will execute faster。

If you don't define your own underscore low level in it， as you certainly don't at this point。

 an empty library version is used。As you can see by the test of the R0 register。

 low level in it returns a value which determines whether to go straight to calling main or to perform a data initialization。

The library version returns a non0 value， so the function underscore underscore IR data in it3 is called。

I skip over this function right now because at this point。

 your program does not have all the interesting data sections yet。

 I will step through the data initialization in the next debug session after you modify the code such that all data sections will be present。

Here， I just want to finish this run by showing you that finally。

 the start code ends up calling the main function。Okay。

 so let's modify the code such that it has all the data sections。 But first。

 I need to clarify the term data section for you。Well。

 perhaps the best way to explain it is to simply show you the various program sections。For this。

 you need to enable generation of the so called map file by the linker。

Please open the project options dialog box， go to the linker section and the list tab here。

 please check the generaterate Lier mapp file option。Rebuilt the code by pressing of 7。

So let's take a look at the generated linker map file。

You can find it conveniently in the output folder of your project。At first glance。

 you might think that the Lier map file is a cryptic， illegible machine level gibberish。

 and it certainly is， but for an embedded programmer。

 it is also a real treasure trove of invaluable information。

 and I highly recommend that you not only generate a map file for all your projects。

 but also that youll learn how to read and use the information。For example。

 you should always know how big your program is in terms of code space in ro and data space in ro and RamM to find out you scroll to the module summary section。

Here you have all this information broken down by type of data such as Read only code。

 read only data and Readrite data。As well as object module such as De O and main dot O。

At the bottom you'll find the totals which are currently 470 bytes of read only code。

 18 bytes of read only data， and thousand60 bytes of read writeite data。

The largest contributor to the readWite data is the 1024 bytes generated by the linker for the stack。

However， for now， the most interesting part of the map file is placement summary。

 which lists all the program sections。For the linker。

 a program section is simply a continuoustiguous chunk of memory that has a symbolic name。

 For example， the area between addresses 0 and Hex 40 is named dot In fact section。

 The following sections are all named dot text and are for the code。Finally。

 the dot RO data section is for read only data。All of these sections are in the wrong address range。

Below that， you find several dotPSS sections which hold uninitialized data that need to be set to zero during the system startup。

And finally， at the very bottom， you find the C stack section which holds the stack and is left uninitialized during the startup。

If you wonder about the names such as dot text or dot BSS for code and uninitialized data respectively。

 these are all historical names coming from some ancient assembly language。 For example。

 BS S used to mean blocks started by symbol or some such。

 which today has a completely different meaning。But anyway。

 the point is that your program doesn't have the initialized data section yet。

 that is a data section that requires a specific initialization to hard coded values during the startup。

So in the next step of this lesson， you will add some data initialization and then check again how this will change your map file。

In the previous lessons of this course， you have already seen that it is possible to give an initial value to a variable in its definition。

 The syn is to follow the variable name by an equal sign and an expression followed by a semicolon。

For example， sine 16 bit integer x is initialized to negative 1。

 while unsine 32 bit integer y is initialized to a binary of pound defineded constants， lead。

 red and lead green。You can also initialize more complex variables such as whole arrays。

 in which case you need to enclose the initial values ins and separate by commas。 For example。

 here is an initialization of a signed 16 bit array S QR of four elements。

When you provide an array initializer， you might omit the size and the C compiler will infer the size from the initializer。

Also， the initializer might have fewer elements than the specified array size。

 in which case the missing elements will be initialized to 0。However。

 the initializer cannot have more elements than the array size。

 and you get the compilation error when you try。Initialization of structures is similar to initialization of arrays。

 Again， you enclose the initial values of the members in braces and separate them by commas。

 For example， here is an initialization of the P1 point structure。

For a structure of structures such as window， you simply nest the initializers of member structures。

 For instance， here is an initialization of the window instance W that contains two point instances。

Now， going back to the map file， perhaps you have noticed that it has changed。First。

 a new initializer byte section has been added in the wrongm address range。Second。

 two new dot data sections have been created in the Ram address range at the same time as two dot BSS sections have disappeared。

And third， the combined size of the two new dot data sections is hex C bytes。

 which is exactly the same as the size of the new initializer bytes section in RAM。Shown graphically。

 the fact of your adding some initialization of variables caused the following changes。

The linker has inserted a new dot data section in RAM for the initialized data。And at the same time。

 the linker has created a matching initializer by its section in real of exactly the same size as the dot data sections。

The implication for the startup code is that it needs to copy the initializer byte section from RAM to the dot data section in RAM。

Please note that the start code does not initialize the data in the way you have specified it in the code。

 so it does not copy two bytes here and four bytes there to individual variables。Instead。

 the linker has specifically reordered the variables so that all initialized data can be initialized in a single block copy from initializer by its section to the dot data sections。

So let's have another look at the startup code now that you have both initialized data in the dot data section and the uninitialized data in the dot BSS section。

First， I set the memory view to the Ram region and I fill the memory with hex FFs so that you can clearly see when the bytes are changed to0 or some other values。

Next， quickly step through the startup code until you reach the IAR data in its3 call This time you will step into this function to see how it initializes the data。

This label indicates that the first step is to0 initialize the data。

This SR instruction is the core of the data clearing algorithm。

 The instruction stores the value of R3 to the address in R2。As you can see。

 R3 is 0 and R2 is exactly the address of the first dot BSS section in RamM。

As you can see in the memory view， the SDR instruction writes zeros to a4b word at the beginning of the first dot BSS section in RAM。

But I'd also like to take this opportunity to explain a new addressing mode used in this SDR instruction。

Please note the pound4 constant after the square bracket。

 This offset caused incrementing the base register R 2 by 4 bys， as you can see in the register view。

You should not confuse this addressing mode with an SR instruction that has a constant inside the bracket。

 as that one is for adding offset to the base temporarily before storing the data。

The new addressing mode with incrementing the base is specifically suitable for tight loops。

So as you step through the code， you can see how the code loops around the SDR instruction。

 and each pass clears the next word in the BSS section。After clearing dot BSS。

 the startup code proceeds to copying the data into the dot data section。

The actual copying is done by the LDR SDR instruction pair that use the addressing mode I've just explained for the dot BSS section。

The R2 base register of the LDR instruction points to the source of the data。

 which is the beginning of the initialr bytes section in RAM。

 The R3 base register of the SDR instruction points to the target of the data。

 which is the beginning of the dot data section in RAM。As you can see， again。

 the code loops around and initializes the whole data section。Eventually。

 the startup completes and the main function is called。In summary。

 what you have just seen is the standard compliance startup code provided in the IER library by the time main is called the C standard requires all initialized variables to have their initial values and all uninitialized variables to be set to0。

However， startup code from other vendors might not comply with the C standard。

 specifically you might encounter startup code that does not clear your uninitialized variables in the dot BSS section。

For example， the startup for Texas Instruments DSP routinely does not comply in this respect。

The point is that I highly recommend that you test your startup code by methods I've just shown you。

If you find out that your dotBSS sections are not cleared。

 you might need to explicitly initialize all previously uninitialized variables to0。

But this is not optimal because you essentially convert the dot BS sections to dot data sections。

 which require a matching initializer byte section in RAM。 In other words。

 you take space in RAM for a bunch of zeros。All right。

 so now that you have a fairly good overview of the standard C initialization sequence。

 it's time to go all the way to the beginning of the reset process。

This part of the startup sequence is processor specific。

 so what will follow will be specific to the arm cortex M processor on the Otiva launchunchpad board。

Let's start another debu session to answer two basic questions。First。

 you want to find out how the stack pointer S got its initial value， and second。

 how the program counter PC ended up at the function underscore underscore IR program start。

The clues to answer these two questions are at the address 0， which is the start of Rome。

When you look at this address in the disassembly window。

 you can see C stack limit at address 0 and underscore underscore IAR program Start at address Hex 4。

Please note that these are not machine instructions。 These are simply words in memory。

 The code instructions start later， with the main function。So here is the answer to your questions。

 The arm cortex and processor is hardwired， such that after reset。

 it copies the bits from address 0 to the S P register。

And all the bits accept the least significant bit from address Hax 4 to their PC。

The least significant bit of any value loaded to the PC must be one。

 because this bit indicates the thumb mode of the processor。

 which is the only one supported by cortex M。This explains why PC is hex 2，1，8。

 why the value at address Hex 4 is hex 2，1，9。 I talked about it already， in previous lessons。

But I'd like to point out something even more significant。

 What you have just discovered at address0 is the so called vector table。

The vector table is described in the data sheet of your microcontroller。

Where you can read what you already know， that it contains the reset value of the stack pointer and the start address of the PC。

But the vector table contains more than that。 It contains all the exception and interrupt vectors that your processor can handle。

 Of course， I need to explain what these are in the upcoming lessons。

 but I hope that you are excited about getting so close to the fascinating subject。😊。

The actual layout of the vector table is shown on the next page。

This picture is drawn in a traditional way that is with the address 0 at the bottom and high addresses at the top。

This happens to be upside down compared to the vector table in your disassembly view。

So let me flip the vector table layout and try to match it with the view in your debugger。

As you can see， the vector table from the data sheet now matches your view in the debugger quite nicely。

 All the exception vectors defined the data sheet are initialized to Ba fault handler。

 and the vectors marked as reserved are 0。However， the vector table from the data sheet is evidently much longer than the one in your disassembly view。

 specifically the vectors labeled IRQ 0， IRQ1， etc ce， are not present in the disassembly view。

This is because the vector table provided by the IR library is generic。

 It contains only the standard exception vectors that are defined at the beginning of the table and are common to all cortex and microcontrollers。

But the IAR table does not contain interrupt vectors that are specific to a given microcontroller。

 such as IRQ0， IRQ1， etc cea， so it cannot really handle any interrupts。For that。

 you need to replace the generic IR vector table with a specific one that will match exactly the layout defined in the data sheet of your specific microcontroller。

Before you leave this debug session though， let's examine the B fault handler code。

 which from the vector table should be at the address Hex 1 Db。

The actual location of this code is Hx1 D A， but by now。

 you should know why the address must be an odd number， why the actual code is at an even address。

So here you have also the answer why all exception vectors in the IAR vector table appear to be set to B fault handler。

Apparently， the IR startup code defines all exception handlers such as pass fault， debug monitor。

 hard fault， memory manager， and nonmsable interrupt。But they all point to the same piece of code。

Knowing only this common address that disassembler could not distinguish among the various exception handlers and chose to show only the ba fault handler because this one is the first in the alphabetical order。

Finally， the Ie R code associated with all these exception handles turns out to be a single branch instruction which jumps to itself。

This means that an occurrence of any of the exceptions ends up tying the CPU in a tight。

 endless loop。 This is good for debugging， because when you break into such code。

 you will find it looping inside an exception handler。However。

 such a primitive policy is unacceptable for a production code because the device will appear completely locked and unresponsive。

 This is known as denial of service。

![](img/b9db09f19babb50f82324bf20e4e2597_7.png)

🎼This concludes the lesson about the standard startup code In the next lesson you will learn how to replace the generic vector table with a real one that can handle all interrupts available in your microcontroller。

🎼You will also write the exception handlers that can be used in a production quality code。

🎼And finally， you will start building the board support package for your launchchpad board。

🎼All of this will set this stage for learning about interrupts。🎼If you like this channel。

 please subscribe to stay tuned。 You can also visit statemachine。

com/quistart for the class notes and project file downloads。

