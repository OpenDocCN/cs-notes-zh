# Quantum Leaps《现代嵌入式系统编程Modern Embedded Systems Programming》中英字幕 p12 -12-#11 Standard integers (stdint.h) and mixing integer types.zh_en -BV1fRt2efEms_p12-

🎼Welcome to the embeddedd System programming course。 My name is Miro Haock， and in this lesson。

 I'll talk about the fixed width integer types， SD and dot H。🎼AndDNs。

 mixing data types in expressions and a little about the floating point data types。

🎼For those of you who watched this video in preparation for a job interview in embedded programming。

 this lesson will provide answers to some tricky questions。As usual。

 let's get started with making a copy of the previous lesson 10 project and renaming it to lesson 11。

 If you are just joining the course， you can download the previous projects from statemachine do com s Quickstart。



![](img/c0dc14fa5359e2b45a3932d3d95b95b2_1.png)

Get inside the new lesson 11 directory and double click on the workspace file to open the Iea tool set。

 If you don't have the IR tool set， go back to lesson 0。



![](img/c0dc14fa5359e2b45a3932d3d95b95b2_3.png)

So far in this course， you have been only using the C built in integer types such as endt or unsigned。

The problem with these built in types is that the C standard does not actually prescribe their size。

For example， in or unign can be 32 bit wide on a 32 bit machine such as arm。

 but they can be only 16 bit wide on a 16 bit or 8 bit machines such as MSP 430 or AVR。

Beyond in and unsigned， the sea language offers also short and unsigned short。

 long and unsigned long， as well as car and unsigned car built in data types。But here again。

 the C standard prescribes only that the size of short must not be bigger than int。

 and int must not be bigger than long。The plain car data type is typically1 byte。

 but it can be either signed or unsigned， depending on the compiler options。

All these ambiguities are actually intentional in the original C standard to give the compiler vendors more flexibility。

 but in embedded work， it is often imperative to know exactly the size。

 Sness and dynamic range of your variables so that your code runs the same way。

 regardless of the target processor。This is obviously not a new problem。

 and solutions have been around for decades。 The approach generally taken is to define a new data type for each fixed with integer you plan to use in your programs。

 For example， the popular microco real time operating system uses the type de statements to define the fixed with integer types as follows。

Each type de statement defines a new type， and as most definitions in C should be read backwards。

For example， the new type CPU underscore N 30 to U is defined as the unsigned end built in type。

Once you type the venue type name， you can use it in the same way as a built in type to define your own variables such as X。

 Y and Z defined here。Of course， in a real project。

 you would put all these type of statements in a header file with the dot H extension and then include this headerophil in all your dot C files。

However， please note that such a handmade terophile cannot be universal for two reasons。 First。

 it uses some made up names， which aren't standardized in the same sense as the building types are。

And second， the definitions are correct only for a specific processor and a specific compiler。

 For example， the type CPU underscore n 30 to U is defined in terms of the int type。

 which can have different size on different processors。

It sure would have been nice if the authors of the C standard had defined some standard names and made compiler vendors responsible for providing the appropriate type defs in a standard library header file。

Interestingly， this is exactly what finally happened in the C99 ISO standard。

 which provides the standard header file SDDN do H for an embedded programmer， the SDDN。

 H header file is one of the most valuable features of the C99 standard。

The IAR compiler supports the C99 standard if you select it in the project options。

You can actually look inside the SDDN doh H file because it is inside the IR tool set on your disk。

As you can see， the file uses type devs to define the following fixed with integer types。

 int 8 underscore Sc T for sine 8 bit integer， U int 8 underscore Sc T for unsed 8 bit integer。

Int 16 underscore T for sine 16 bit integer and U int 16 underscore T for unsed 16 bit integer。

 and finally int 32 underscore T for Sine 32 bit integer and U int 32 underscore T for unsed 32 bit integer。

The file defines more types， but these six are the most important。

 The value of the SDD and header file is in standardizing the type names and the fact that it is now the responsibility of the compile vendor to provide the right definitions for your CPU。

 The compilers do it frequently by means of macros。

 such as this underscore underscore n 32 underscore T underscore type underscore underscore。

 which in turn are defined in terms of the built in types。Obviously， with the ISO standard in place。

 inventing your own integer type names is counterproductive。

Even if your compiler is not C99 compliant， you should provide the SDDin。

h header file with the standard names。For example， the Microsoft Visual C++ compiler is not C99 compliant。

 so if you wish to use it for developing embedded code on the PC。

 you can still do it by providing your own SDD and do H header file。

So now let's use the standard fixed with inteigent types to take a bit closer look at how the arm cortex and processor will handle them。

Here I define a few variables of each fixed width type。

 whereas I name the variables so that the type is reflected in the name。

The unsigned variables start with U， and signed variables start with S。First。

 let's check that the fixed width integers have really the expected size。

The C language provides the size of operator that returns the size in bytes either of a variable such as U8 a。

Or the data type， such as U in 16 T。Or you int 32 underscore tea。

Let's build the code by pressing F 7 to make sure that the compiler likes it so far。

While you can run the code on the launchpad board， I will today use the simulator so that anybody without the board can follow along as well。

So let's start debugging in the simulator。Open the Watch1 view and type the names of the variables that you want to watch。

At this point， some variables that you have defined are not available because they are not yet used anywhere in the code。

 and the compiler has eliminated them。When you step through the code。

 you can see that the reported size of U8A is 1 byte。The size of U in 16 T type is2 bytes。

And the size of U in 32 T type is 4 bys， as expected。

I'd also like to point your attention to the addresses of your variables because their order in memory is different than the order in which you have defined them in the code。

The compiler allocated the 4 Bte variable U 32 E at a lower address than the 2 byte variable U16 c。

And left the one by variable。 you ate8 at the end。The point to remember here is that the compiler can and will change the order of your definitions。

 so you should never assume that the order will be preserved。Next。

 let's initialize the variables to hex constants， but in such a way that you can distinguish each byte。

 For example， the first byte of U 16 c is hex c1， and the second is hex C2。Also。

 let's use some assignment statements to see how the CPU reads the value of one variable and writes it to another variable。

Before you start debugging， please prepare the memory view to show the robots as they are naturally ordered in memory。

For this， you need to set the address of beginning of Ram。And select the one times units view。

Now take a look at the disassembly view as your single step for the code。

Notice that the processor uses the LDRB instruction to load the byte white variable U8A into R1 and the SDRB instruction to store R1 into the1 byte variable U8B。

Similarly， the instruction LDRH is used to load U16 B into R1 and SDRH to store it into U16 D。

And finally， the instruction LDR is used to load U16 E into R1， and SDR to store it into U 32 F。

The interesting point to remember here is that the arm processor has special instructions。

 LDRB and STRB to read and write bytes， LDRH and STRH to read and write half words and plain LDR and STR to read and write whole words into memory。

Now， let's take a closer look in the memory view。 The interesting thing here is that the order of bytes in the multibyte variables such as U 32 E is reversed compared to the order of these bytes in the register R 1。

This is because arm is a so called little Indian machine。Or strictly speaking。

 the arm Corps has configurable Indianness， but virtually all silicon vendors。

 such as Texas instruments， choose the little Indian configuration。

Little Indian means that lower order bys from a register are placed at lower addresses than higher order bys。

For example， the least significant byte E4 from the R1 register has been stored by the last SDR instruction at a lower address than the E3。

 E2 and E1 bytes。I don't have a big Indian machine to show you the difference。

 but I can manually change the order of bys to big Indian in the memory so that you can see how it would look like on a big Indian processor。

An example of such a big Indian processor is power PC used in the Mac computers before they switched to x86。

Once you start using their various integer data types。

 you will inevitably encounter situations when you will have to mix them in expressions and assignments。

 This will require conversions from one type to another。

 And the good news is that the C language does it automatically through implicit conversions。😊。

The bad news is that the rules for the implicit conversions are rather complicated。

 counter intuitivetuitive and often lead to developer confusion。

I can't possibly cover all the nuances of type conversions in C。

 but I will explain a couple of the most important principles。

I'd like you to remember that this is perhaps the most tricky part of the sea language and often leads to subtle bugs。

In the first example， I want to illustrate that C always automatically promotes any smallerest size integers to the built in int or unsigned int type before performing any computations。

Consider the following expression。When you run this example。You can see that the result is 70000。

 which obviously is 40000 plus 30000。 Nothing surprising here。

But this is because you have executed this code on an arm processor， which is a 32 B machine。

In order to see a problem， youll need to execute the code on a machine where the standard end data type is only 16 bit wide。

 such as MSP 430。In fact， I have here the MSP E XP 430 G2 Lapa board。

 which is quite similar to the Tva launchpa， except it has the MSP 430 microcontroller instead of the arm cortex M。

I have also prepared a blinky program version for the MSP430 launchpa that I would like to demonstrate first。

 since MSP 430 is entirely different than the arm I am using here a version of the IAR toolt for MSP 430。

In fact， I have the I R tool set for arm still open on my screen in the background。

So let me show you how the blinky code executes on the MSP430 launch pad。

Before I let the program run free， I first step through the code to demonstrate that the LED on the MSP430 board is turned on and off from the code。

Okay， so now I will just copy and paste the example code from the IAR for arm to IAR for MSP for30。

I need to type again the names of the variables into the watch1 view。And finally。

 I can step through the code and see how the expression is evaluated。Whoops， as you can see。

 the result is 4000464 instead of the expected 70000。 Now。

 I don't think that you' have expected this， did you。To understand what has just happened。

 you need to go back to my original statement， I said that C always automatically promotes any smaller size integers to the built in type int or unsigned int before performing any computations。

On the 32 B arm machine， the promotion was to 32 B because this is the size of int on the arm。

However， on MSP 430， there was no real promotion because the type end is only 16 B wide on MSP 430。

 So the computation happened in 16 B， which overflow。 So the result 4，4，6。

4 that you saw is just a truncated value to 16 B。Please check this with your calculator。

The most tricky aspect of this example is that the result of the computation is eventually assigned to a 32 bit white number。

 which has enough dynamic range to represent 70，000。

This is something that throws many developers off。But I hope that this example will help you remember that the precision in which the computation is performed does not depend on the left hand side of the assignment。

So knowing this， how would you fix the problem。Well。

 you need to enforce promotion to 32 B precision of at least one of the operas。That way。

 the other implicit conversion rule of the C language will apply。

 which is that the computation is performed at the largest precision of the involved opera。

Specifically， if one of the opera is 32 B wide， the other will be promoted to 32 B and the whole computation will be performed at 32 B。

So the solution is to explicitly cast one or both of the operas to you in under Sce as follows。

As I step through the code on the MSP 430 launch padd。

 please watch the values of the opera and the result U 32 E。

 I specifically single step through the disassembly to show you the additional work。

 the 16 B MSP 430 CPU needs to do to promote both arguments to 32 B。 in particular。

 note the familiar partial value 4，4，6，4， which is subsequently extended to 32 B。In the end。

 the final result is 70000 as expected。So this final version is the truly portable code。

 You should copy and paste it into the I for arm because the version left there is not portable。

 Of course， on a 32 B machine， the explicit cut to you in 32 T will not cost any additional CPU cycles。

Just to confirm， I run the code and verify。That the disassembly is the identical as before。And that。

 the result。Is 70000。In the next example， I would like to show you problems that can arise with changing the sinedness of an arithmetic operation。

 Consider the following expression。Here I mixed signed 10 with unsigned U16 C。

The expected result of this computation is 10 minus 100 equals negative 90。

 which is stored in the signed as 32 variable。When you run this code on arm。The result is， indeed。

 negative 90。However， when you copy this code to MSP430。And run it on the MSP430 launch padd。

You get a different result。The value in S 32 in this case， is 6，5，4，4，6。

The implicit conversion rule that applies in this case is that when you mix assigned signed and unsigned opera。

 both are promoted to unsigned int， and the result is unsigned in。Subsequently。

 the result is converted to Sine 32 bit because this is the type of the S 32 variable on the left hand side of the assignment。

When this expression is evaluated on the 32 B arm， the unsigned end value is 32 B wide。

 So it fills completely the S 32 variable， and the value is reinterpreted in the two complement representation as negative。

If you don't remember the two complement representation of negative numbers。

 please go back to lesson 1。However， when the same expression is evaluated on the 16 bit MSP430。

 the unsigned end is only 16 bit wide and fills up only the lower half of the S 32 variable。

Because the value is unsed， it is not s extended to 32 B and is interpreted as a big positive number。

The best way to avoid such non portable code is to avoid mixing signed and unsigned。 Instead。

 you should explicitly cast the unsigned variable to a signed type。Note also that in this case。

 the problem was not within insufficient number of bits。

 so you can cast to the signed in 16 T type because it is sufficient。

When you run the correct code on MSP430， you can see that the value in S 32 is sign extended。

 so it is negative 90 as expected。The problem of mixing signed and unsigned integers arises often in comparisons。

 Consider the following if statement。When you compile this code。

 youll get a warning that you have a pointless integer comparison。When you think about it。

 it seems to make sense because the smallest value an unsed number can hold is 0。

 which is always bigger than negative one。But wait a minute。

 the warning says that the that the comparison is always false。Which is exactly the opposite。

 what you would think。But this is apparently exactly what the compiler thinks。

 because you cannot even set a break point in the F branch， only in the else branch。Indeed。

 when you run the code， you hit the breakpoint in the else branch。So how can that be。Well。

 this makes sense only when you recall that in the mixed signed unsigned expressions。

 the C standard promotes the signedine up to unsigned in。

The negative one value promoted to unsed int is Hx F， F， F， F， F， F， F。

 which is the largest value a 32 B unsed integer can hold。 That's why the comparison is always false。

Again， you can fix the problem by an explicit cast from unsigned to signed。

The last frequent confusion I'd like to discuss is with binary operations on small integers。

 Consider the following comparison。You compare here bitwise one complement of a byte with 0。

 Something like this could come up。 For example， when your byte represents a checkum over some data and you want to make sure that the checkum adds up。

At first glance， with value F F in U8 A， the comparison should be true because one's complement simply inverts all the bits。

But， in fact， the comparison will always be false， although the compiler does not report a warning in this case。

However， you cannot even set a break point inside the if or even on the if itself。

 because the compiler has eliminated the whole thing。

The compiler knows that the comparison will never be true because the byte U8 a will be promoted to in。

 so the most significant bytes will be 0。 When once complement is taken。

 the most significant bytes will be all ones， so the result can never be 0。

The remedy in this case is to specifically revert the promotion to int by casting the inverted value back to a bite。

🎼This concludes this lesson about the standard fixed with integers。

 ininess and mixing types in expressions。🎼I haven't covered the floating point types。

 so I have to leave this subject for another time。🎼In the next lesson。

 I will talk about C structures and the cortex microcontroller software interface standard， CMC。

🎼If you like this channel， please subscribe to stay tuned。 You can also visit statemachine。

com/quiickstart for the class notes and project file downloads。



![](img/c0dc14fa5359e2b45a3932d3d95b95b2_5.png)