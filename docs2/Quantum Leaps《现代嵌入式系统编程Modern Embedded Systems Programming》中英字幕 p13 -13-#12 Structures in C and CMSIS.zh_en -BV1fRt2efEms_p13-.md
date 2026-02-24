# Quantum Leaps《现代嵌入式系统编程Modern Embedded Systems Programming》中英字幕 p13 -13-#12 Structures in C and CMSIS.zh_en -BV1fRt2efEms_p13-

Welcome to the moderndern embeddeded Systems programming course。

🎼My name is Miro Samak and in this lesson I'll talk about the C structures。

🎼I will also introduce you to the Cortex microcrocontroller softwareware interfaceface standard CMC。

 which uses structures to access hardware in cortex M microcontrollers。As usual。

 let's get started with making a copy of the previous lesson 11 project and renaming it to lesson 12。

If you are just joining the course， you can download the previous projects from statemachine。

com s Quickstart。

![](img/a0e1129cf061dccf634236ef521d183d_1.png)

Get inside the new lesson 12 directory and double click on the workspace file to open the Ir tool set。

 If you don't have the Ir tool set， go back to lesson 0。The latest version published by IeaR is 7，10。

 which I am using in this lesson。So far in this course。

 you have been only using the so called scalar data types such as the built in integers or the exact with integer types introduced in the last lesson 11。

In lesson 7， you also learned about arrays， which is a way to group together variables of the same type。

 For example， array A contains 32 identical U in 32 T integers。

Structures are another mechanism in C to group together variables， possibly of different types。

The benefit of structures is that they permit a group of related variables to be treated as a unit instead of as separate entities。

In invalid systems， structures also permit you to access hardware in an elegant and intuitive way。

 I will explore this aspect later in this lesson。But first。

 let me explain the syntax and give you a few examples of structures in C。



![](img/a0e1129cf061dccf634236ef521d183d_3.png)

For this， I will create a few structures for an embedded graphic LCD display。

The basic object is a point which groups together an x coordinate and a Y coordinate。



![](img/a0e1129cf061dccf634236ef521d183d_5.png)

The keywordstruct introduces a structured declaration。

An optional name called the structure tag may follow the wordstruct。

 as does the tag point in this example。The variables enlisted between the braces in the structure are called members。

 So here x。And why are members obstruct point。On a horizontally elongated LCD display。

 X might need a bigger dynamic range than y。 So let's make x U in 16 T and y only you int 8 T。

A structured declaration can be immediately followed by a list of variables。 For example。

 you can define variables， P A and P B， both being points。Actually。

 if you define variables immediately after the structure。

 you might omit the structured tag altogether。I press F7 to quickly show you that the compiler accepts this form just fine。

However， more common is to define a structure followed by an empty list of variables。

 This is then the only situation in C where the closing brace must be immediately followed by a semicolon。

A structure declaration that is not followed by a list of variables reserves no storage。

 but if the structure is tagged， you can use it later to declare variables as follows。Nonetheless。

 this way of using structure types is still a little cumbersome because you must always repeat thestruct keyword in front of the structure tag。

 This is also not how it is in C+ plus where you don't need to repeat the keyword tract or class in front all of class names。

But by now， you should know the solution in the previous lesson。

 you learned about the type de directive， which you can use to define the point type as follows。

Now you can define variables P1 and P2 of type point without the keywordstruct in front。

An interesting wrinkle here is that， as you can see。

 the compiler accepted the same name point for both thestruct tag and the type of name。

 This is because tag names in C occupy a different name，space than type dev names。

 variable names or function names。Interestingly， also you can place the type dev even before thestruct declaration。

 and the compiler still likes it。Finally， there is a way to remove the repetition of the point name altogether by using the untagged Str declaration inside the type de。

In this last case， the compiler obviously no longer recognizes their Str point type。

 but it still likes the type defft point type。In summary。

 my preference is to use the last type F form without thestruct tag。 Actually。

 this is also recommended by the latest safety C standard called Mira C 2012。

 where the advisory rule 2。4 recommends that the project should not contain unused tag declarations。

Sttract tag names are almost never needed。 The notable exception being the so called self referential structures。

 such as nodes of linked lists or trees。But this is an advanced way of using structures。

 which goes beyond the scope of this course for the time being。

So now that you know all the different forms of declaring structure types。

 it's time to find out what you can actually do with them。Well。

 the first thing you can do is to get access to the individualstruct members。As usual in C。

 this is achieved by the special member access operator， which is a dot。For example。

 here you will obtain the size of the structure point and assign it to P1。 X member。Of course。

 you can also use the dot operator inside an expression here， for example。

 you calculate P1 dot x member minus uns 3 and assign it to P1。t Y member。At this point。

 you need to know that the dot operator has a very high precedence。

 which is higher than any arithmetic operators， such as minus。

 This is why you typically don't need to use parentheses around the access to strict members。

So now it's finally time to step down to the machine code and see how your point structure actually looks in memory and what's its real size because it's not3 by。

2 bys for x and1 by for y， as you might expect。For this part of the lesson。

 I am going to use the simulator， but you can also run the code on your launchpad board。

I clean up the watch1 view and prepare it to watch the P1 structure variable。

And I also set up the memory view to show the memory around the address of P1。

As you can see in both views， P1 starts with all zeros。When you step through the code。

 you can see that the compiler treats P1。x as any other half word variable and uses the already familiar SDRH instruction to store a value in it。

But the compiler evidently thinks that the size of the points track is 4 bytes， not3。

In the evaluation of the expression， you can see again that P1y is treated as a by size variable because the result of the expression is stored with the STB instruction。

Looking in the memory view， you can now recognize the point structure as the4 bys at address Hex 2 followed by all zeros。

 The P1 dot x member with value 4 is at the beginning of the structure。

 and P1 dot Y member with value 1 is immediately after it。Interestingly。

 the compiler has petdted the structure by one byte after the P1 dot Y member。

To investigate the structure layout and padding， let's reverse the order of members and run again。

As you can see， the order of members has also been reversed in memory because P1。

 y is now at a lower address than P1 x。Looking in the memory view now。

 you can see that indeed the P10 while member at the beginning of the structure is followed by one unused byte before the P1 dot x member so that the total structure size is 4 bytes。

Compared to the previous run， this change of order should convince you that the compiler will honor the order of structure members exactly as you type them in the structureture declaration。

However， the compiler can and sometimes will insert extra padding bys into your structure。

The second interesting observation is that evidently。

 the compiler for arm cortex M preferred to waste 1 bite of memory rather than place the P1 dot x half word member at an odd address。

 The obvious question is why。To investigate this last question。

 it would be interesting to somehow force the compiler not to waste the bid between the Y and X members。

This is not possible in the standard C， but most embedded compilers provide some non standard extension to pack the structure members tightly without any padding。

The IAR compiler provides photos this an extended keyword underscore underscore pack。

 which you can place in front of thestruct keyword。 So let's do this right now and see what happens。

Also， to avoid value 0 in P1 dot y， which will happen when the size of thestruct will indeed be 3。

 let's change it to something else。The first interesting thing to notice in the watch view is that this time around。

 the P1 dot X member is allocated at an odd memory address。In the disassembly window。

 notice that the code is still very efficient。 In particular。

 the assignment to P do X is still handled by the SRH instruction。

 even though P do X is at the odd address。So what's the big deal， The CPU handle the pe structure。

 just fine。To see a real difference， let's change the CPU， open the project options dialog box。

 go to General options and select the cortex M0 core instead of cortex M4 f。Next。

 go to the debugger section and select the T I stilllars interface and make sure that the use flash loaders option is checked。

Yep， that's right。 I really intend to run the code not just in the simulator， but on real hardware。

 In fact， I will run it on the Tva C launchpad board， even though it has the cortex M4 F processor。

 not cortex M0。This way， I hope to convince you that cortex M processors are truly binary compatible。

 specifically from the chart of cortex M machine instructions。

 you can see that cortex M4 recognizes all instructions for cortex M3。

 which recognizes all instructions for cortex M0 M1。

This is like a set of nesting dolls where any bigger doll can hold all the smaller ones inside。

After the code is programmed into the launchpad board。

 quickly check that P1x is still at the odd address。And set up the memory view。

When I start stepping through the code， notice that the code for the simple assignment of P1 do x is bigger than before to help you see the difference I put the previous disassembly for cortex m4 f side by side。

As you can see， the same C source code compiled for Cortex M0 consists of two STB instructions。

 plus a logical shift right instruction， whereas Cortex M4 achieved the same effect with just one STRH instruction。

Interestingly， this is not because cortex M0 does not have the SDRH instruction， In fact it does。

 but it can't use it at this point because the SDRH instruction in cortex M0 is less powerful than in cortex M4 and cannot access a half word allocated at an odd address。

So here， for the first time， you see that alignment of the data in memory matters to the processor。

As an emmedted programmer， you absolutely need to know about it because otherwise you will never understand why the compiler inserts padding into your structures。

The compiler prefers to keep the data aligned instead of wasting the CPU cycles to access misaligned data。

You can also see here that packed structures might not be as efficient to access as the regular unpacked structures。

In other words， you need to use packed structures judiciously only when you absolutely need to avoid padding。

To conclude the experiment of running cortex M0 code on cortex M4 CPU。

 I just run the program so that you can see that the launchpad board keeps blinking the LED as before。

 so it happily executes the M0 code。So now I would like to show you a few more things that you can do with structures。

First， you can make more complex structures， including structures that contain other structures。

For example， a track window might contain two points for top left and bottom right corners of the window。

Structures can also contain arrays。 For example， a structured triangle might contain an array of three corners。

 each one being a point。 So you can see here that you can have arrays of structures。

The variables of structure types are sometimes called instances。 So here W is an instance of window。

 and T is an instance of trianglestruct。Now， regarding accessing members of such complex structures。

 here are examples of accessing nested members of the window and triangle structures。

Please note how the IAR editor helps you by displaying all possible members of a given structure。

But assignment is not limited just to the basic scalar types。 You might also assign whole structures。

 For example， you can assign the whole P1 structure to the P2 structure or the whole complex window structure to another window structure。

However， I hope you realize that more complex structures can occupy considerable memory。

 so an innocently looking assignment of structures can mean copying a sizable chunk of memory from one variable to another。

Therefore， instead of copying entire structures from one place in memory to another。

 it is often more efficient to use pointers to structures。As you perhaps remember from lesson 3。

 a pointer type is created by simply adding a star after the type name。

 This is exactly how you make pointers to structure types as well。 For example。

 P P is appointed to the point type while W P is appointed to the window type。

To initialize a pointer， you can take an address of a variable with the address of operator。

 For example， you can set P P to point to the P1 point or W P to point to the W2 window。

The next question is how to access the members of a structure using a pointer。

The C language provides two ways。 First， as you learn in lesson 3。

 you can apply the star operator in front of a pointer to obtain the object pointed to by the pointer。

So if P is a pointer to point， star P is the point type。From there。

 you can access any member using the dot operator。Note that the parentheses around star PP are necessary because the presence of the dot operator is very high。

 even higher than the star operator。In a similar way。

 you can dereference the W P pointer to set the top left member。 noticeice that here again。

 you can see an assignment of whole structures because both top left member and star P are points。

But pointers to structures are so frequently used in C that the language offers an alternative operator arrow as a quicker way to access a structure member via a pointer。

 So the following two assignments are equivalent to the previous versions。

Let's now take a look in the debugger to see how these more complex structures are accessed。

 You can keep the cortex M0 core， but remove the packed extended keyword from the point structure to avoid muddying the picture with accessing misaligned data。



![](img/a0e1129cf061dccf634236ef521d183d_7.png)

Step through the code to where the window structure is accessed and put the W variable in the watch window。

 Ma sure that all the members are expanded and visible。Now。

 single step through disassembly and note a few interesting things。 First。

 you should notice the SR H instruction， which means that it is available in cortex M0。

 but only when the point member X is aligned。Second。

 please note the square brackets after the SR H instruction。

 This means that the content of the R 0 register must be stored at the address in R1 plus the offset of2 bytes in this case。

This addressing mode with additional offset from a given base register is very convenient for accessing structures。

 In fact， it has probably been designed specifically for this purpose。

Because a structure for a compiler is nothing else but a bunch of offsets。

 one for each member from the beginning of the structure。Here again。

 you can see this addressing mode used in the SDB instruction to access the y member of the bottom right point in the Windows track。

As you can immediately see， this member has the offset of4 bytes from the beginning of the window structure。

Let's confirm these offsets by looking at the address of the W variable in the memory view。

So here is the whole structure。Here is the2 byte offset to the top left dot x member。

 and here is the4 byte offset to the bottom right dot Y member。



![](img/a0e1129cf061dccf634236ef521d183d_9.png)

So now I hope you are really getting ready for the idea of applying structures to access hardware registers in an embedded microcontroller such as the S control registers to enable or disable various peripherals or the GPIO registers through which you can turn the various color LEDs on and off on your launchpad board。

Please note that the way you have accessed the hardware registers so far was quite primitive and did not involve structures。

 You use the L M4 F header file， which defined the hardware registers of your LMF4 F microcontroller simply as pre processor macros。



![](img/a0e1129cf061dccf634236ef521d183d_11.png)

For example， the GPIO port FAHPDIR register was defined as the referencing of a pointer with the hard coded address of the register from the data sheet。

All other registers were defined in a similar way。In contrast。

 the idea now is to design a C structure in such a way that its data members would correspond to all the registers within a given hardware block。

 such as C control or GPIO。For that， you need to consult the data sheet here I have the data sheet of the specific TM4 microcontroller used on your Tva Lapad board。

 which is also identical to the L M4F microcrocontroller used on the slightly older L M4 F launchpad。

 This P D F is available either directly from Texas instrumentnstru or from the state machine dot com slash Quickstar webage accompanying this video course。

For example， in the description of the general purposepo input output block。

 you can find the section register map。

![](img/a0e1129cf061dccf634236ef521d183d_13.png)

![](img/a0e1129cf061dccf634236ef521d183d_14.png)

As you can see there， all registers within the GPIO block are specified as offsets from the base address of the block。

The register map provides thus a blueprint of the GPIO structure in C。

 because as you recall from the debug session a minute ago， a structure is just a bunch of offsets。

 one for each of its members。

![](img/a0e1129cf061dccf634236ef521d183d_16.png)

So given the data sheet， I hope you start to see how a C structure for the GPIO block can be written。

The good news is that you don't need to do it because it has already been done by the microcontroller vendor。

In fact， to your current project directory， I have copied the TM4 c underscore underscore score CMcs。

h header file， which contains definitions of structures for all hardware blocks found in your microcontroller。



![](img/a0e1129cf061dccf634236ef521d183d_18.png)

When you open that T M4C header file。And scroll down a bit。

 You can see that it contains type fft structure definitions。For example。

Here we can see the structure for the system controller ci control。And right below。

 you can see the structure for the GPIO。As a quick exercise。

 let's compare the structure definition in the TM4 C header file with a GIO register map in the data sheet。

As you can see， the first register in the data sheet is GPIO data but when you look closer。

 you can see that there is a big gap of 400 hes in the offsets to the next register in the map。

This is because GPIO data is not a single register， but rather a group of 2564 byte registers。

 which I discussed in detail in lesson 7。In the C structure。

 the group of 256 data registers is represented as an array of 255 data bits member plus the data structure member。

Again， please refer to lesson 7 to see why this last data register is special。

All the following registers in the GPIO map have a one to one correspondence to the members of the C structure in the header file。

I only wanted to point out the gap in the offsets after the GPIO alternateter function select Register。

Such a gap is represented in the C structure as the reserved one array member so that the following members align exactly at the offsets specified in the data sheet。

Finally， I am sure that you are wondering about the types used in the C structure。

I hope you recognize the U in 32 underscore T fixed with integer type。

 which means that all the registers are 32 bit wide。

 but the underscore underscore IO underscore underscore I and underscore underscore O identifiers surely look strange。

As it turns out， these are the preprocessor macros defined in the cortex microcontroller software interface standard。

 CMCs。Which the TM4C header file is part of。I will show you the actual definitions of these CMCs macros in a minute。

 but first just notice that the macros correspond to the third column in the data sheet。

Whereas I O stands for input output and corresponds to read write I， which stands for input。

 corresponds to read only and O， which stands for output， corresponds to write only。



![](img/a0e1129cf061dccf634236ef521d183d_20.png)

Going back to C Cs， you can see that the T M4 C headerphilee is not completely standalone。

 but rather it includes the core underscore the score C M4 dot H headerophille。

 This headerphile is part of the CCs industry standard。

 and I R distributed as an integral part of the toolet。

To see the core underscore underscore score CM4。 H header file。

 go to the installation directory of your IR toolt。Get into arm。Cms。Include。And opened the file。



![](img/a0e1129cf061dccf634236ef521d183d_22.png)

So here are the definitions of the macros underscore underscore I underscore underscore O and underscore underscore I O。

 These macros turn out to be defined as the volatile keyword， which I hope makes sense to you。

 It also means that the volatile qualifier can be used for individual structure members。

The underscore underscore I macro has additional quaifier cont。

 which means that such designated variable is constant and cannot be modified。

 I hope to cover the use of the Kst keyword and the concept of const correctness of programme in one of the future lessons。

To finish with the core and the Sc CM M4 header file。

 I only want to show you that it too contains structures that define hardware registers。Here。

 for example， is the structure for the nested vectored interrupt controller and Vic。

 which is part of every cortex M core， and therefore it makes sense to define it in the CCs core header file。

You will use the NviC in the future lessons about interrupts。With all this information。

 you can finally rewrite your code to use the CMC's compliant way of accessing hardware using structures。

The last piece of the puzzle you need to understand is how to make sure that the C control or GPIO structures are at the right base address。

This might seem like a big problem because so far， you have only created instances of point。

 window or triangle structures where the compiler controlled their placement in memory。

But this problem is not really new， and you have encountered it before， already in lesson 4。

The solution is to use pointers to structures initialized to the hard coded base address from the data sheet。

Indeed， this is exactly what's done in the TM4 c header file。At the end of the file。

 you can find the pound defined base addresses of various hardware blocks。And below that。

 you have a bunch of pound defined hard coded pointers to various structure types。 For example。

 the Cs control macro defines a pointer to the Cs control underscore type structure。

 which is hard coded to the Cs control base address。Similarly。

 the GPIO F high speed macro defines a pointer to the GPIO type structure。

 which is hard coded to the GPIO port F AHB base address。

The first step in replacing the way you access the hardware is to change the header file name to T M4 c underscore Scorsms dot H。

 You can also remove the LM4F header file from the project。Next。

 you replace every register access using the new form。For example。

 to replace the first register access， you take the Cis control pointer and append the member access operator。

At this point， the IAR editor will help you by displaying all the members of the structure。

You choose the appropriate register from the list to know for sure which one you might need to consult the data sheet and the is controlled underscore type structure definition。

You proceed in a similar way with all other registers。

The GIO port F data register is actually an array of 255 registers， as you saw a few minutes ago。

As you can see， the program compiles cleanly。

![](img/a0e1129cf061dccf634236ef521d183d_24.png)

One last thing left to do is to verify that the LED still blinks as before。And so， it does。

This concludes this lesson about the structures in C and the CMC standard。🎼In the next lesson。

 I will talk about pointers to functions， which you will need to understand the startup code and interrupt handlers。

🎼If you like this channel， please subscribe to stay tuned。 You can also visit statemachine。

com/quistart for the class notess and project file downloads。

