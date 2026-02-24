# Quantum Leaps《现代嵌入式系统编程Modern Embedded Systems Programming》中英字幕 p09 -09-#8 Functions in C and the call stack.zh_en -BV1fRt2efEms_p9-

🎼Welcome to the embeddedd Systems programming course My name is Miro Sammock and in this lesson I'll introduce you to the C functions and the stack。

🎼I can't possibly cover all the important aspects of working with functions in just one lesson。

 So today I will mainly focus on explaining how the C tag enables calling functions that call other functions and so on。

If you only ever bother to learn about one aspect of the low level behavior of C or C++？

🎼Then the C stack is most likely to be this one thing because it is the key to understanding functions。

 interrupts， context switch， and the arts。As usual。

 let's start with making a copy of the previous lesson 7 project and renaming it to lesson 8。

 If you are just joining the course， you can download the previous projects from statemachine dot com s Quickstar。



![](img/08b58329ef41fe09e1d234398721d733_1.png)

Get inside the new lesson 8 directory and double click on their workspace file to open the IAR toolt。

 If you don't have the IAR toolet go back to lesson 0 while I do some cleanup。

 let me quickly remind you what this program does。

![](img/08b58329ef41fe09e1d234398721d733_3.png)

It starts with setting up the registers inside the LM4F microcrocontroller to control the LEDs attached to the GPAO lines。

Next， it lights up the blue LED， and then it enters an endless loop in which it lights up the red LED。

Waits in a delay loop。Extinguishes the red LED。Wait again in another delay loop。

And loop back to the beginning。When you look at the program at this stage。

 I hope you agree that the repetition of the delay loop is rather ugly。 In fact。

 it goes against the dry principle， which stands for do not repeat yourself。 In other words。

 in programming， you should strive to eliminate repetitions so that parts of the coded are supposed to be the same。

Can't get out of sync。Today， you are going to learn one of the main techniques of avoiding repetitions。

 which is to turn a piece of code into a function and then call this function as many times as needed。

Instead of repeating the same code， verbatim。A function in C， also known as a procedure。

 subrout or subprogram in other programming languages。

 is a reusable piece of code that can be executed from many different points in a program。

In order to turn a piece of code into a function， you need to give it a name， a list of arguments。

 and a return type。So to start simple， our delay function will have the name delay will take no arguments and will return no value。

 These three elements， the return type， the name and the list of arguments are called together the signature of the function。

The function code goes between the opening and closing races that follow the signature。

Once your function is defined， you can very easily call it as many times as you like。

The syntax for calling a function is the function name， followed by arguments in parentheses。

The parentheses are necessary， even if the function takes no arguments。

Calling a function means changing the flow of control to jump to the beginning of the function code。

 executing that code and returning to the next instruction just after the call。

Let's check if this code comps by pressing F 7。I am sure you are eager to run this code on a real board。

 but before you do this， please change the project options as follows。

Set the optimization to low because at high level of optimization。

 The compiler is so smart that it will eliminate a function called overhead by essentially reversing what you have done so far。

 This is called inlining a function。 And obviously， you don't want that to happen at this point。Also。

Whenever you work with functions， I strongly recommend checking the option require prototypes。

When you try to compile this time by pressing F7， you get an error that the function delay has no prototype。

 A function prototype is the signature of the function followed by a semicolon instead of the code block。

The compiler must see a prototype of each function， before the definition。By the way。

 your function delay takes no arguments at this point In the older standards of the C language。

 you might code it by simply an empty argument list rather than avoid argument list。

 So let's try to do this right now。As you can see， the code no longer compiles。

 This is because for backwards compatibility， the empty argument list means that the arguments are not specified and could be anything with the required prototypes option。

 The compiler is much stricter and does not recognize such a weekly specified prototype。Okay。

 so finally， you are ready to run the code on the Slarries board。

The first line of business is to check if your program still blinks the LED as before。And so。

 it does。When you stop the code， you find the program inside the delay function。

 This is to be expected because your program spends 99。999% of the time executing the delay loop。

The next interesting thing to check is to find out how your processor actually calls the delay function。

 So let's set a break point and run the program。As you can see。

 the call to your delay function boils down to just one instruction called the BL from the earlier lesson 2 about the flow of control。

 you might remember that the branch instruction simply changes the value of the program counter PC。

The BL instruction has， however， an additional important side effect。

 and that is to save the address of the next instruction into the R14 register。

 which is also called the link register LR。This way。

 the the LR register remembers the place in the code to return to after the function completes。

So let's remember that the next instruction following the BL is at address Hex 9 c。By the way。

 please note that the BL instruction itself is4 bytes long。

 while most other instructions are only two bytes long。

So you can see that the instruction set of the arm cortex and processor， which is called Tamp 2。

 consists of mostly two byte instructions and occasionally a4 byte instruction。

When you a single step over the BL instruction， you can see that indeed the program counter jumped to the beginning of your delay function while the ELR changed to Hx 9c。

Or wait a minute it actually change to hex 9 D。 This is， of course。

 very strange because all T2 instructions must be aligned at an even address and value hex 9 D is odd。

I will explain this oddity in a minute when we see how the function returns， but before that。

 let me point out a few interesting things about the function code。

The function starts with adjusting the S P register。

 S P stands for stack pointer and is an alias for the R 13 register。

The S is the hardware implementation of the C call stack mechanism。

 And so it is the most important register to learn about in this lesson。

A C stack is simply an area of Ram that can grow or shrink from one end only the end is called the top of the stack。

 and this S P register contains this top address。You can very easily see the stack in memory by pointing your memory view to the address stored in the S P for viewing this stack。

 it is best to adjust the memory view to show only one column。In the arm processor。

 the stack grows towards the lower addresses， which is up in the memory view and shrinks towards high addresses。

 which is down in the memory view。In other processors。

 the stack might grow in the opposite direction。A good metaphor for the sea stack is a stack of dishes。

 You can only add or remove the dishes from the top of the stack。

So now you understand that subtracting4 from the S P grows this stack by this amount and creates space for the local variable counter at the top of this stack。

Subsequently， this variable is cleared and incremented a million times。Now。

 let's set a break point at the end of the function to see how it returns。

The first thing the compiler needed to do before returning was to exactly reverse any operations on the stack that were performed at the entry to the function。

In this case， the stack is shrunk by4 bys to free the space initially allocated by the counter variable。

As you can see at the current top of the stack， the last value of counter is Hex F 42，4，0。

 which is 1 million in decimal， which is the number of iterations of your delay loop。

The next instruction is the actual return from your function。

 The return is accomplished by the branch instruction， B， X， which stands for branch and exchange。

This instruction sets the program counter to the value in the specified register。

 which is L R in this case。 However， not all bits in L R are transferred to the PC。Specifically。

 the least significant bit in the PC is always set to 0。

 which makes sense because a return address must be even。So instead of being used for addressing。

 the least significant bit in LR is interpreted as the instruction set Exchange bit。

If this bed is one， the processor switches to the thumb instruction set。 If this bit is 0。

 it switches to the arm instruction set。Problem is that arm cortex M supports only the T2 instruction set and cannot really switch to arm。

 So in cortex M， this behavior of the Bx instruction is just a historical legacy。

So let's execute the BX instruction and see where it goes。Indeed， we end up at address Hex 9 c。

 which is exactly the next instruction after the call to your delay function。Finally。

 just to see what happens， let's run again to the end of the delay function。And set。

The least significant bit of L R to 0。 This should exchange the core state to arm。

 but arm is not supported on cortex M cores。Well， as you can see， you end up in a ba fault exception。

 I will talk about exceptions in an upcoming lesson about interrupts。 But for now。

 I thought it would be interesting to see how a processor handles an impossible condition。

The machine ends up in an exception handler， which is like a function that you can redefine for your specific project。

To get out of the exception handler， you need to reset the machine。

As the reset brings you back to the beginning of mainine。

 it is a good opportunity to examine a function that calls other functions。😊，By now。

 I hope you noticed that main is also a function， just like your delay function。

Before you called delay from main， mainine was a so called leaf function， like a leaf on a tree。

Because it did not call any other functions。When you added the call to delay。

 Maine stopped being a leaf function and had to do something special to preserve its own return address。

As you recall， the return address is kept in the LR register。

 but this register is clubbbed with a new return address by the BL instruction。

So any function that executes BL must somehow save the previous value of L R so that it can return to the right place。

The question is， of course， where is the best place to save the link register。

I hope you see from the code that this place is the stack。

The push operation saves the specified list of registers on the stack and automatically and automatically decrements the stack pointer to grow the stack。

Let's verify this by executing the push instruction。To summarize。

 you found out that this stack is used for two purposes。 First。

 it holds the local variables of the functions called。 And second， it stores the return addresses。

Finally， in this lesson， I'd like to show you what the function arguments are for and how to use them。

Function arguments allow you to specify initial values of the local variables at the point of the function is called。

 whereas each call can be made with different set of values of the arguments。For example。

 you might want the delay function to execute a different number of iterations at every invocation。

To achieve it， you can specify an integer argument iter。

 which will be used as the iteration limit inside the function。Once a function takes some arguments。

 its every invocation must provide the initial value for all those arguments。

 So if you try to compile the program right now， the compiler will report errors for the two calls to the delay function。

 because they no longer match the prototype。 This is the beauty of using prototypes。

 because the compiler can now warn you whenever you forget to provide the right number and type of arguments for every function call。

Okay， so let's provide the arguments For the first call， I use 1 million iterations。

But for the second call， I only use 500000 so that the red LED will be twice as long on as it will be off。



![](img/08b58329ef41fe09e1d234398721d733_5.png)

Let's run this code on the launchpad board。First， remove all the break points and run freely for a while to watch the LED。

Indeed， the red color appears to be about twice as long on as it is off。Next。

 set breakpoints at the calls to the De function to see how the parameter is passed to the function。

As you can see， the BL instruction is now preceded by loading a constant value into r0。

For the second call to delay， this constant is hex 7， a 1，2，0， which is 500000 decimal。

 For the first call， the value loaded into r 0 is the familiar hex F。4，2，4，0。

 which is 1 million in decimal。So as you can see in both cases。

 the argument eat is passed in the R0 register。Lets now step into the delay function to see how it uses the E argument。

 Indeed， as you can see， the argument iter is located in r 0。

 and the variable counter is at the top of the stack because its address is the same as the value of the S P register。

🎼This concludes this first lesson about functions and the calls stack。

🎼Functions are critically important because when you design them properly。

 you can ignore how a job is done and you can focus only on what is being done instead。

 which is a lot simpler。🎼But we are not done with functions yet in the next lesson。

 I will talk more about this stack and function calling other functions。

 including functions calling themselves recursively。

🎼You will also learn more about function arguments as well as the nonvo return types。🎼Finally。

 at the low level， I hope to get to presenting the Ar Proal standard。If you like this channel。

 please subscribe to stay tuned。You can also visit statemachine。

com/quistart for the class notes and project file downloads。

