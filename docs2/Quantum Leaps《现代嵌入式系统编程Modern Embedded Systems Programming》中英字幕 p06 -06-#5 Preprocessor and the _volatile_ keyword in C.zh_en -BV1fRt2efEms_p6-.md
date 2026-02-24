# Quantum Leaps《现代嵌入式系统编程Modern Embedded Systems Programming》中英字幕 p06 -06-#5 Preprocessor and the _volatile_ keyword in C.zh_en -BV1fRt2efEms_p6-

🎼Welcome to the embeddedd System programming course。

 My name is Miro Samak and in this lesson I'll show you how to improve the Blakekey program by using the C preproor and the volatile keyword。

As usual， let's start with making a copy of the previous lesson 4 project and renaming it to lesson 5。

 If you are just joining the course， you can download the previous projects from statemachine do com s Quickstar。

Get inside the new lesson 5 directory and double click on the workspace file to open the IR tool set。

 If you don't have the IR tool set， go back to lesson 0。



![](img/e5d7aefc1e37657708bbb36255d251a6_1.png)

![](img/e5d7aefc1e37657708bbb36255d251a6_2.png)

So this is the program you created in lesson 4。 It works in that it manages to blink the red LED on the Stlaris launch pad board。

 but it is certainly not very readable because it is full of cryptic numbers。

 and there are no comments to explain what's going on。To improve the readability of the code。

 it would be very nice to use names for the registers instead of the cryptic numbers。😊。

One way you can achieve it is by means of the C preprocessor。

 which lets you define any piece of code as a macro。For example。

 let's define the macro for the first register you' write to。 Start the new line with a pound sign。

 followed by the word define， followed by the name of the macro。

 The data sheet calls the register run mode cloudgating control register for GI O。

 So let's name the macro R C G C， GI O。After the name。

 you'll simply paste the piece of code this macro is going to replace。Once the macro is defined。

 you can use it instead of the original piece of code。

Press F 7 to check if the compiler accepts the code so far。

The C preprocessor is called that way because it is conceptually a separate first step of simple text substitution before the real compilation。

 The preprocessor removes all lines starting with a pound sign。

 so that the compiler does not see them at all。 For example， you can define the macro to be anything。

 But as long as it is not used in the code， It doesn't matter， and the code still compiles。Also。

 the preprocessor replaces only the macros that are actually used in the code。

 So the compiler sees only the replacement sequences of characters and never the macro names themselves。

This means that the macro does not need to be any complete element of the C language。 For example。

 the macro fo is just a piece of the pointer cast expression。

 But as long as the text substituted for the macro makes sense in the specific context。

 the compiler will happily accept it， because really， the compiler cannot tell the difference。

The corollary of all this is that you need to be careful how you define your macros so that their meaning will not change unexpectedly。

 depending on the context in which they are substituted。 For example， to avoid surprises。

 it is always a good idea to enclose the macro like R C GC。

 G P I O in parentheses so that it always means dereencing of a pointer in any context。

 it might be used。It is also possible to define macros using other macros。 For example。

 if you define the macro GPIO F underscore base as it is specified in the data sheet。

 you can use it in the definitions of the other macros。

Such as GPIOF underscore DIR for the pen Direct register。With the offset。Hex 4，0。

0 from the base address。GPI O F underscore D E N for digital enable with the offset Hex 5。

1 C from the base address。And GI O F underscore data where the offset hacks 3 F from the base address。

Finally， it is always highly recommended to add comments to your code。

 Commonments are only for the benefit of humans who read your code and are completely ignored by the compiler。

 The C 99 standard supports two types of comments。 The traditional C command delimed by slash star and terminated by star slash。

 such as this one。And C plus plus styled comments starting with slash slash and terminated by the end of line。

 such as these ones。Comments are allowed everywhere where you could legally place a space。 And。

 in fact， all command are replaced with a single space before the compilation。

Both types of comments can also be used in the macro definitions。

So now it will be interesting to see if this code still blinks the LED to actually see this。

 I am going to use this solarlarious Lapad board。 But if you don't have the board。

 configure the debugger for a simulator and follow along。😊，Great， the LED blink as before。

 So all your changes seem to work。Let's examine in some detail how the compiler translated the GO underscore Disc code data macro and whether or not it introduced any overheads。

 After all， you might be concerned that now the CPU needs to add the base address to the offsetet at runtime。

 But when you step through the code， you can immediately see that the LDR dot N instruction loads directly the full address Hax 4。

0，0，2，5，3 Fc into r 0 without performing any additions。 In other words。

 the code is as efficient as before。 because the compiler folds any constants computable at compile time and avoids unnecessary computations at runtime。

 Finally， it is very interesting to see which single instruction actually turns the LED on。

 It turns out that this is the SDR instruction。 In other words， from the CPU point of view。

 talking to the outside world is fundamentally very simple。

 and boils down to writing a specific value into a specific address。O。

 so your program still works and is as efficient as before。

 but I don't want to leave you with the impression that you have to define macros for all the registers yourself。

 In fact， typically you don't need to because the microcontroller vendors such as Texas instruments in the case of the Sillaris board already provide the macros for you in a separate file which I have copied to the lesson 5 directory。

You can add this file to the project by right clicking on the project and choosing Ed Ed files menu option。

 The file name is L M 4 F 12，0 H5 Qr dot H， which corresponds exactly to the microcontroller type on your Stis Lapad board。

 The file extension dot H means that this is a header file specifically designed for inclusion into dot C files such as your main dot C。

When you open the header file， you can see that it contains a whole bunch of macros very similar to what you have defined yourself。

 However， the pointer costs used in the header file are significantly different。

 which requires some explanation。 Let me grab one macro from the header file and copy it to the main dot C file for comparison。

The first discrepancy is the pointer type。 The macros in main dot C use unsigned int。

 While the header file uses unsigned long。 I will discuss data types in a separate lesson。

 but for now， let me only say that on a 32 B machine like the arm processor。

 The int type is 32 B wide。 So is the long type。 So unsigned in an unsigned long are equivalent。

 So the real difference is the volatile qualifier。 It informs the compiler that the object pointed to by the pointer might change spontaneously。

 When you declare an object to be volatile， you are telling the compiler that the object might change。

 even though no statements in the program appear to change it。 For example。

2 Bs in the GIO F register on the launchpa board are connected to the user switches。

These bits can be changed when they user presses or releases the switches。

 which is obviously not caused by any program instruction。 Therefore， the GIOF register and in fact。

 most other IO registers are volatile。This is important because the compiler can optimize access to nonvolat objects by reading an object value into a CPU register。

 working with that register for a while。 And eventually writing the value in the register back to the object。

 The compiler is not permitted to do this sort of optimization with volatile objects。

 Every time the source program says to read from or write to a volatile object。

 the compiler has to do so。 So clearly， the volatile qualifier is useful for the I O registers such as GI of。

But it can also be very useful for normal variables to prevent optimizations that the compiler otherwise might do。

 For example， the counter variable is used only in the two delay loops。

 But if you look at these loops from the compiler's perspective。

 they make no contribution whatsoever to the computation。

Because the final value of the counter is either overwritten or discarded。In this this case。

 the compiler is permitted to optimize both delay loops away。

 You can actually see this quite easily by allowing a higher level of optimization as follows。

 click on the project options choose CC++ compiler section and click on the optimizations tab。

 select High optimization level and click O。Recompile and run the program on the launchpad board。

As you can see， the LED lights up and stays on all the time。When you single step with the code。

 you can see that the instructions for turning the LED on and off are still there。

 but the delay loops between them are gone。But now that you know about the volatile keyword。

 you know how to prevent the compiler from optimizing the delay loop away。

 You need to make the counter variable volatile。By the way。

 the volatile keyword can be placed either before the type。

 like in the macro from the header file or after the type。 I recommend placing it after the type。

Let's quickly test whether the volatile counter， indeed， fixed the problem。Yes， the LED blinks。

You can also see the delay loop when you single step with the code。

So now let's make use of the dot H header file by actually including it into the main program。Again。

 you use the preprocessor for this。To include the file。

 you start a new line with a pound sign followed by the word include。

 followed by the name of the file in double quotes。



![](img/e5d7aefc1e37657708bbb36255d251a6_4.png)

Let's put the header file side by side with the main program to replace all the macros you've defined so far with the macros from the header file。



![](img/e5d7aefc1e37657708bbb36255d251a6_6.png)

The hair file provided by the microcontl vendor uses the register names from the data sheet。

 so you should have no trouble to recognize the interesting registers such as GI or F data。

GPI output port FDIR。And GI output FDEN。If you have any doubts about the correct name of the register。

 you can always check its address to make sure that this is what you want。

After replacing all the macros， you can remove your own definitions and recompile the code。

Let's test the code one last time。To check if the LED will still blink。

This concludes this lesson about the C pre process order and their volatile keyword。🎼From now on。

 you are able to write programs that will run correctly at any level of optimization。

 so congratulations。🎼In the next lesson you will learn how to use the bitwise or and end operators to blink other colors of the composite LED。

 and you will also learn about the more advanced features of the GPIO register。

If you like this channel， please subscribe to stay tuned。 You can also visit statemachine。

com/quistart for the class notes and the project file downloads。

