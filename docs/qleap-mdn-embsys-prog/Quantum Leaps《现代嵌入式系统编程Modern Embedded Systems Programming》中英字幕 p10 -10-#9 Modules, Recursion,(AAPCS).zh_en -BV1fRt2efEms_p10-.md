# Quantum Leaps《现代嵌入式系统编程Modern Embedded Systems Programming》中英字幕 p10 -10-#9 Modules, Recursion,(AAPCS).zh_en -BV1fRt2efEms_p10-

🎼Welcome to the Emded Systems programming course。 My name is Miro Samak。🎼And in this lesson。

 I'll continue the subject of functions in C。🎼Today you'll learn how functions allow you to split your program into separate files。

 you'll write your first recursive function， and you'll learn about the Ar procedure call standard。

 APCS。As usual， let's start with making a copy of the previous lesson 8 project and renaming it to lesson 9。

If you are just joining the course， you can download the previous project from statemachine。

com s Quickstar。

![](img/36f8abe794e3e05f0eccbf5591f90375_1.png)

Get inside the new lesson 9 directory and double click on the workspace file to open the IAR tool set。

 If you don't have the IR tool set， go back to lesson 0。



![](img/36f8abe794e3e05f0eccbf5591f90375_3.png)

Let me very quickly remind you what happened so far。 In the last lesson。

 you have created a function delay to busy wait for the specified number of loop iterations。

Here is the declaration of the delay function， also known as the prototype。

And here is the definition of the delay function， which contains the actual code。

The delay function is then called in two places in your main program。

The fact that the single function can be called multiple times instead of repeating the same code verbatim was。

 in fact， your main motivation for using functions in the first place。

But functionss allow you to achieve even a greater feedat。

 Functions enable you to split the program into multiple files。

 rather than having to keep all the code in the main file。

 which for any non tri program will quickly become like a kitchen sink。😊。

So the first thing I want you to do today is to move the delay function into its own file。 First。

 create a new file by clicking the new document tool button。 Next。

 cut and paste the delay function into the new file。And finally。

 save the file as delay dot C into your current project directory。At this point。

 the file exists on the disk， but it is not yet part of the project。

You need to add the file to the project by right clicking on the project and choosing the add and add the do C pop up menu。

When you compile your project at this stage by pressing F7。

 you get an error that the delay function has been defined without a prototype。

You can easily make this error go away by copying the prototype from main dot C to delay dot C。

But this is a very lousy fix， because now the repeated prototypes can very easily become different。

 If you change one and forget about the other。This is just one example of violating the dry principle。

 Do not repeat yourself， which I hope you remember from the last lesson。

The right solution is to place the prototype itself in a separate file。

 which you could then include in all files that call the delay function， as before。

 create new document and cut and paste the delay function prototype into it。

Save the file as delayed do age header file。Now you can include a delayed H header file in the main dot C and in De thatt C instead of repeating the prototype code。

The final touch you can add to the delayed do H headerophil is the protection against multiple inclusion。

 Such automatic protection is useful because headerophiles can include other headerophiles。

 which can easily lead to a situation when a header file can be included more than once。In fact。

 most header files provided in various libraries such as the LM4 F do H header file contain this sort of protection against multiple inclusion。

This is achieved by means of the C preprocessor as follows at the top of the file。

 you have the pound， if not defined preprocessor directive， followed by the mangled name of the file。

There are many conventions of mangling the name here。 for example。

 you see two underscores preended and appended to the capitalized file name。

The idea here is that this macro is not defined initially。

 so that preproces will go beyond the pound if and F directive the first time。However。

 the next line defines this macro so that it is defined from now on。 Therefore。

 should the header file be included again， the preprocessor will not go past the if not defined directive。

 and the body of the file will be skipped up to the matching and if directive。

So now let's apply this technique to your delayed do H header file。

Copy and paste the top two lines and change the mangled file name。

Don't forget to provide the matching pound and if directive at the end。In quick summary。

 you've just learned about one of the most powerful features of the C programming language。

 which is the ability to build programs from separately compiled source files。This ability。

 which is enabled by the use of functions， is critically important because having a complete program in just one file is both impractical and inconvenient。

The way a program is organized into files can help you understand the overall structure and enable the compiler to enforce that structure。

Such modularization is also beneficial for speeding the compilation process。

 because only the changed files need to be recompild。Now。

 let's move on to explore some other properties of functions， such as the ability to return a value。

As an example， consider a function to calculate the factorial of an integer argument N。

Let's design this function top down that this， starting with a prototype and the use case。

 The function name is fact。And it takes one unsigned argument， N。

The factorial function returns an unsed value equal to1 times 2 times 3 all the way up to n。

With a prototype in place， you can write the code that uses the factorial function even before you actually define it。

 an unsigned volatile variable X will be used to store the values returned by the factorial function。

 The variable is volatile to prevent the compiler from optimizing it away。

 So now here is how you call a function that returns a value。

 You can simply assign the return value to a variable。😊，At this point。

 you should also think about the allowed range of the function arguments。 Mamatically。

 the lowest value for which factorial is defined is 0。Actually， strictly speaking。

 the argument type should be an unsigned0。A function returning a value can also be used inside an expression。

 rather than being immediately assigned to a variable。Finally。

 you can also just call the function without doing anything with the return value。

This would make sense only if your function has some meaningful side effects。However。

 to make clear that you don't care about the return value。

 I recommend explicitly casting their return value to void。

When you try to build your program at this stage， you get an error。

 but note that this is not a compiler error。 This error is generated by the linker。

 which is the next step of building your program where all the compilation units are linked together。

When you scroll up， you can see that the linking stage failed because the function fact has not been found。

Obviously， you have not defined this function yet。 so this reason is clear。

But I wanted to point out that this type of error is not detectable by the compiler。

 because the compiler cannot know in which valid definition of this function might reside。

 So let's define the fact function。Copy the prototype and provide the braces for the body of the function。

Before writing the actual code， you might want to brush up on your math by writing the mathematical definition of factorial in a comment。

 In fact， there are two definitions， iterative and recursive for this exercise。

 you will use the recursive definition in which the factorial of 0 is one。

 and the factorial of n is n。Times the factorial of n -1。For all ends， greater than 0。

Translating this into C you get。If n equals unsine 0。Return the value， unsed1。Otherwise。Return n。

Times factorial of n -1。So as you can see， a function produces the result by means of the return statements。

 which are followed by numerical expressions。When you build now。

 both the compilation and linking succeed。 So congratulations。

 You've just written your first recursive function that calls itself。😊，All right。

 so now it's finally the time to see how it really works。

I run the code on the TI board to show that it works on real hardware。

 but you might just as well use the simulator。Before stepping into the code。

 adjust the memory view to see the top of the stack。Which， as you recall from the last lesson。

 is stored in the stack pointer S P register。To help you keep track of the stack content in the memory view。

 I will use an arrow pointing to the current top of the stack。Stepping into the code。

 you can see that the call to your factorial function consists of two instructions。 First。

 the argument value is moved to r 0。And then the function is called with the branch and link B L instruction In the factorial function。

 The first thing that the code does is to push the registers R 4 and the L R link register to the stack。

By now， you should understand why the LR has to be saved。

 and this is because factorial is not a leaf function。

 so it must preserve the L R cloered by the B L instruction when it calls itself。

The very next instruction should give you a clue why saving the R 4 register is also necessary。

 As you perhaps remember， from the last lesson， the first argument of the function is passed in the R 0 register。

But inside factorial， r 0 is reused to return the value。

 and also as the argument to the nested factorial call。 So the compiler moves r 0 to R 4。

Here you can see that the function moves the return value1 in this case， into the R0 register。

The last instruction of the function is very interesting because it kills two birds with one stone。

 As you know， by now， any attack operation executed in the beginning of a function must be exactly reversed before the function returns。

So here the function pops the two registers， which it pushed initially。

 but the content of the original L R is popped directly into the program counter PC。

 which causes the return。Please notice that the value on the stack that was popped into PC is actually an odd number Hx 49。

 whereas the return address the PC has become is an even number Hx 48。

I explained why the least significant bit of the address is handled specially in the B X instruction。

 which was used to return from a leaf function， such as delay。

Here you can see that the P to PC instruction is also a special case and behaves like the BX instruction。

Finally， here you see again that the function returns the value in r 0。

 which is then stored on the top of the stack where the x variable lives。

In the next call to factorial， you see that factorial calls itself。

The most important observation here is that the next call to factorial happens before the previous call returns and pops the registers from the stack。

 So it nets on top of the stack allocated by the first call。

Here you can see that after the recursive call returns。

 the value return in r0 is multiplied by the original value of the argument n stored in R 4。

The result is， again stored in r 0 to be returned from the function。Back in the main function。

 you can see how the expression is evaluated， whereas the factorial value is taken from r0。

The last call to factorial of 5 shows six levels of recursive calls。As I quickly step for the code。

 please watch the stack building up with a clearly distinguishable pattern of the decrementing arguments N and return addresses。

At this point， the recursive calling stops。 and now all these nested calls will return one at a time。

 again， as I step through this return sequence， please watch how this causes the stack to unwind。

After the factorial function eventually returns all the way to main。

 you can see that the result it produced in r0 is hex 78， which is 120 decimal。

 which is indeed the factorial of5。The last subject I'd like to touch upon in this lesson is the function calling convention。

From the discussion so far， I hope you have noticed that there must be some agreement between the color of a function and the function being called。

For example， both sides must have an understanding that the return address will be provided to the function in the LR register。

Also， both parties must agree that the first argument will be passed in r0 and that the return value will be returned in r0 as well。

Of course， there are many more such little agreements that all form a whole formal contract called the arm application Procedal standard。

 A A PC S。The whole formal document is quite complex。

 and you can find it online by searching for AAPCS。

Here I would only like to mention how the AAPCS assigns their responsibilities for the arm registers。

 because this will be very useful when you will learn about handlinglink Inter on the arm processor。

So the registers R0 through R3 and R12 are used for passing arguments and returning values and can be cloed by a function。

On the other hand， the function must preserve the8 registers R4 through R 11。

This doesn't mean that the function cannot use R 4 through R 11， but if it does。

 the function code must save them on the stack and restore before returning。For example。

 please recall that your factorial function uses the R4， but it saved it on the stack。

This convention allows the color of the function to use the preserved registers for values that must survive a function call。

Again， recall that the value of the argument N was stored in R 4 exactly to survive the recursive call to factorial。

 because it was needed in the final multiplication。Speaking of the factorial computation。

 the recursive implementation that I've used in this lesson was just for convenient demonstration of a deep call sequence so that you can watch the stack grow and shrink。

But in fact， any such deep call sequences should be avoided in embedded programming exactly because they use a lot of precious ramp for the stack。

A much better implementation of factorial would be the iterative version or perhaps better yet。

 a lookup table。🎼This concludes this lesson about modules， functions that return values。

 recursive functions， and the arm applications procal standard。🎼However。

 we are still not done with functions。🎼In the next lesson。

 you will learn more about function arguments， including pointer arguments。

 and you will learn about scope and local stack based variables。



![](img/36f8abe794e3e05f0eccbf5591f90375_5.png)

🎼Finally， you will see what can happen when you overflow this stack。If you like this channel。

 please subscribe to stay tuned。🎼You can also visit statemachine。

com/quistart for the class notess and the project file downloads。

