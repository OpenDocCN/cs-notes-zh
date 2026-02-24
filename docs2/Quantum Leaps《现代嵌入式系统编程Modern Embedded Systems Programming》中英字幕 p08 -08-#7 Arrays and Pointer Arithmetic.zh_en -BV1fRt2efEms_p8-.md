# Quantum Leaps《现代嵌入式系统编程Modern Embedded Systems Programming》中英字幕 p08 -08-#7 Arrays and Pointer Arithmetic.zh_en -BV1fRt2efEms_p8-

🎼Welcome to the embeddedd System programming course My name is Miro Samak and in this lesson I'll introduce you to array and basic pointer arithmetic in C。

🎼You will learn how to apply these concepts to take advantage of the more advanced features of the Solaris GPIO data registers。

🎼Which I hope will answer some questions asked in the comments to this video course posted on YouTube。

As usual， let's start with making a copy of the previous lessonson 6 project and renaming it to lesson 7。

 If you are just joining the course， you can download the previous projects from statemachine。

 com s Quickstart。

![](img/cbdea4eda6a95b50bf3b5520eb1d065e_1.png)

Get inside the new lesson 7 directory and double click on the workspace file to open the Ir tool set。

 If you don't have the Ir tool set， go back to lesson 0。



![](img/cbdea4eda6a95b50bf3b5520eb1d065e_3.png)

So this is the program you created in lesson 6。 Let's clean it up a bit and step into the debugger。

As you can see， this program uses read modify write sequence to change the value of individual bits of the GIO register without disturbing the other bits。

 For example， to set bit1， controlling the red LED。

 the program first reads the current value of the GIOF data register with the LDR instruction Next。

 it uses the bitwise or to set the bit1。 and finally。

 it writes the modified value back with the SDR instruction。

The read modify right sequence is necessary because all the GIO bits are co located in a single byte with a single address。

But imagine that each bit could be accessed separately through its own unique address， or better yet。

 every possible combination of GPIO bits would have its own unique address。

Then a single atomic right operation to this particular address would change the selected bits without disturbing any other GPIO bits。

In this lesson， I will show you how the stellarlarious GPIO hardware allows you to do exactly this so that you can replace the typical read modify right sequence with a single anatomic right operation。

But before I explain how to do this， I think it is interesting to understand why bother。 After all。

 the read modify right sequence is fast enough for most cases。Well。

 it turns out that it is not so much about the speed in this case。

 but rather to give you the ability to manipulate the individual GPI orbitbits truly independently from any part of your code。

 including from interrupts。Now， I realize that I haven't talked about the interrupts yet。

 and I promise I will， because it is a fascinating subject， especially in embedded systems。

But just for now， let me only say that interrupts are a hardware supported mechanism for a processor to abruptly change the flow of control in your program。

When an interrupt occurs， a special hardware in the processor changes the value of the program counter register so that the processor suddenly starts executing a different piece of code called the interruptt service routine or ISR。

 which is typically quite short。When the ISR ends， the processor resumes the execution of the original code as though nothing happened。

The interesting case is when the IR changes some GIO bits。

If the interrupt happens to come in the middle of the read modify right cycle after the main code reads the GPIO register。

 but before it writes the modified value back， any changes to the GPIO bits made in the interrupt service routine will get lost。

This is because the main code will still use the previous value of the GPIO register before the interrupt happened。

This is the inherent problem with a read modify right sequence。

So that's the main reason why the designers of the Slaris GIO hardware devised a way to avoid the read modify right sequence and replace it with the single anatomic right operation。

Here is how it works。 The GI O beds are connected to the CPU with a bunch of wires called a bus。

 Each bed is connected to both a dedicated data line and a dedicated address line as well。

 The bed can be changed only when the connected address line is one。 Otherwise。

 the bed is unaffected， regardless of the value of the attached data line。For example。

 to isolate the three GPIO bits connected to the LEDs。

 you need to write to the address ending with 00，0，0，1110，00 binary。

Please note that the two lowest order address lines。

 a0 and a1 are not used because the hardware requires all addresses to be divisible by4。

The data you write， determine the state of the pins。 For example， you can light up the red LED。

 extinguish the blue LED and light up the green LED all in a single right operation。

 I hope it is becoming clear that this hardware design requires many registers with unique addresses because not only each GI O bit has its own address for this。

 you would need only8 registers。Each combination of bits has its own address in this scheme to cover all possible bit combinations of 8 GI O bits。

 the Stlars GO provides 2，56，32 B data registers。 starting with the address Hex 4，0，0，2，5，0，0，0。

So far in the previous lessons， you have been using only the last of these registers called GIO port F data R corresponding to the offset。

 all ones0，0 binary， which is 3 F Hx。 This register obviously didn't isolate any bits and enabled all8 GIO bits to be changed with data lines。



![](img/cbdea4eda6a95b50bf3b5520eb1d065e_5.png)

In this lesson， we will use the other registers。So now the question is how to access all those GPIO registers in C。

One way is to hard code the address directly with the brute force approach youll learn in lesson 3。

 for example， to isolate only the bit1 corresponding to the red LED。

 you could manually compute the address。By starting with a base address from the data sheet and adding to it the LED red bit left shifted by2 to skip the two unused address bits。

You need to cast the synthesized address to a pointer。And。Dear reference at the pointer。

Remembering that this address isolates just a single bit。

 It matters only what you write to this particular bit。

 and it is irrelevant what you write to the other bits。For the sake of demonstration。

 let's write one to the LED red bit and 0 to all the other bits。

Let's check if this called compiles by pressing of 7。Now it is。

 of course interesting to test this on the launchpad board。As you can see。

The read modify right sequence is simplified to just the SDR instruction to the address in R 2。

 which is the GPIO base address plus the offset 8。 When you step through the code。

 you see that the red LED lights up and the other LEDs stay unchanged。

 proving that the code does exactly what you wanted。So the code works， but it is not very elegant。

 You can improve it significantly by applying the concept of an array。

An array is a group of variables of the same type occupying consecutive memory locations。

 such as the group of 256 identical GIO data registers。In C。

 you can declare an array by adding the number of elements in square brackets to a variable。

 For example， this is an array of two counters， each being a volatile integer。

You can even initialize the whole array at once by using the array initializer like this。

Now you can use the array elements as normal variables by referring to the elements by their numbers。

The number in the brackets is called the array index。

 and the first element of an array in C is always 0。 The second element is one， and so on。

Let's compile by Pre F 7 to see if the compiler accepts the syntax。

Aasency are closely related to pointers。The C compiler treats an array as a pointer。

 which points to the beginning of an array。To get the pointer to an element with index I。

 you simply need to add I to the array pointer。So instead of counter of one。

 you can write counter plus one dereenced as a pointer。 This is an example of a simple pointer。

 arithmetic。The correspondence between arrays and pointers goes both ways because every pointer can also be viewed as an array。

 For example， the standard L M4 F header file defines the pointer GIO port F data bits R。

This pointer can be used to access all to 56 GPIO data registers as an array。So for instance。

 to access only the LED red bit， you can index into GI output port F data bits like this。

Which is exactly equivalent to using the following pointer arithmetic。

Let's step into the debugger to see how these three options compare。As you can see。

 all three implementation options write to the same address stored in the R4 register。

So this little experiment shows that， indeed， all three alternatives are equivalent and generate the exact same machine code。

 going back to the source code。 Let me point out the very important difference between address arithmetic and pointer arithmetic。

In the first case， you put form address arithmetic first。

 and only then you cast the raw address to the unsigned log pointer。In this case。

 you had to left shift the LED red value by 2 Bs to take into account the size of the GO register。

 which is 4 B wide。 In the second case， you use pointer arithmetic because GPO port F data bits R is a pointer to unsign long in pointer arithmetic。

 you don't need to scale the offset by the size of the element because this is done automatically for you。

 This must be so because of the equivalence between pointer arithmetic and array indexing。

Of all these three options， I think that array indexing looks the cleanest。

 so I'm going to leave this one and comment out the others。Now。

 let's use the array indexing technique to clear the red LED。As you remember from the wiring diagram。

 this requires writing 0 to the LED red bit position。Finally。

 I use the array indexing consistently for setting the blue LED bit in the beginning。

So this is the final program that uses the fasted interrupt Sa technique for manipulating the GPIO bits。

 Let's test this program on the Lapad board。First， let's run full speed and watch the LEDs。

As you can see。The program works as before。When you break into the code。

You can see that clearing the red LED bit takes only one SR instruction to the GPIO address in R0。

So your program is about as good as it gets， except that， as it turns out。

 the stellarlars LM4 F microcontroller can do even better。As you can find out in the data sheet。

 the microcontroller has not one but two peripheral buses。Advanced peripheral bus。

 A P B and advanced high performance bus， A H B。The GIO ports are connected to both。

The A P bus is the default， and this is what you've been using so far。

 But the A P B is older and slower than A HB。 And so it is kept only for backwards compatibility。

So in the remaining minute or so of this lesson， I will show you how to switch to the faster and better A HB。



![](img/cbdea4eda6a95b50bf3b5520eb1d065e_7.png)

First， you need to find in the data sheet how to switch GPIO from the default APB to HHB。

In the system control section， you'll find the GI O H P C TL register， which does exactly this。

 Youll note that port F is controlled by bit number 5。Next。

 you go to the L M4F header file and look for the GIO H PCtl register。



![](img/cbdea4eda6a95b50bf3b5520eb1d065e_9.png)

You copy the register name and set bit 5 in it。Finally。

 you need to change all GPIO addresses from the APB address range。

 which is called APB Aperture in the data sheet to the AHB aperture。

You search again the LM4 F header file for GPIO port F。

 and you find a set of registers with all with the AHP suffix。

So you need to add this suffix to all the GPIO port F registers in your program。

Let's test this final version on the Lapad board。🎼This concludes this lesson about arrays and pointer arithmetic in C。

 Now you are an expert in Stellais GPIO， so congratulations。🎼In the next lesson。

 Ill talk about C functions。If you like this channel， please subscribe to stay tuned。

You can also visit statemachine。com/quiicksstart for the class notes and project file downloads。

