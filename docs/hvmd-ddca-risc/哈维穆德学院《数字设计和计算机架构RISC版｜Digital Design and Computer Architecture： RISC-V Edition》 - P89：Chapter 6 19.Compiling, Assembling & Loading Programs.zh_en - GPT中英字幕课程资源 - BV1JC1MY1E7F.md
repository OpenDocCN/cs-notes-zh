# 哈维穆德学院《数字设计和计算机架构RISC版｜Digital Design and Computer Architecture： RISC-V Edition》 - P89：Chapter 6 19.Compiling, Assembling & Loading Programs.zh_en - GPT中英字幕课程资源 - BV1JC1MY1E7F

Hello， in this video we'll look at how to compile， assemble and load a program。



![](img/89802b5829e83d45e5d07d10ede06c31_1.png)

So one of the great innovations of digital computers is this notion of a stored program。

So you could imagine a system that was hardwired to do something， for example。

 a calculator that had circuitry that looked for buttons being pressed。

 and then in response to that piped the data into an arithmetic logic unit that did the operation and then some more hardware that displayed something on a screen。

 and that calculator is just a calculator and it can never be anything else。

But with a stored program。The program itself is a set of instructions stored in memory。

And if you want your hardware to do something different。

 then instead of having to rewire the whole system， you could just reprogram the processor。

Put new program into the memory。So in our processor。

 we have 32 bit instructions and data that are stored in memory。

 and the only difference between two different applications running on a processor is that sequence of instructions。

So when we're executing a program， the processor fetches the instructions from memory in the appropriate sequence and the processor does the specified operation for each instruction。

So imagine we had a simple assembly languages program。

Assisting of the sequence of instructions with this machine code。They add。

Is located the beginning of the program。Subtract。Is at the next address， then add I。

 the next address and load word next。 So is I just have to think about the proper order。

 When we read an assembly language program， the first instruction is at the top。

 the last instructions at the bottom。 When we put it into memory。

 the lowest memory address at the bottom and the highest address at the top。The program counter。

Keeps track of what instruction we're currently executing。 So when we begin this program。

 theer program counter is 8，3，0， pointing at the ad。

So one of the key figures in early computing was Ellan Turing。

 he was a British mathematician and computer scientist and a founder of theoretical Comp science。

He was very important during World War II as one of the people who cracked the enigma code that allowed the allies to read German codes。

And he also invented the notion of a Tring machine。

 which is a mathematical model of computation that tells us about what kinds of things are computable。

He also designed the automatic computing engine， which was one of the first stored program computers。

In 1952， he was prosecuted for being a homosexual， he was hounded in his professional life and lost a security clearance and he lost his ability to contribute to a lot of the key technology that was happening at the time。

 Two years later， he died of cyanide poisoning， and it still debated among historians。

 whether that was suicide or an accident。But the Turing Award is named in his honor。

 it's the highest honor in computing like the Nobel Prize of Computer Science。

So if we want to run and compile a program。We start with our high level code。

 say written in C or a similar language， and we put it into a compiler。

 The compiler emits assembly code。Then the assembly con code can go through an assembler and we get out machine language code called an object file。

We need to combine that object file for our code with other object files from libraries。

 for instance。Or other parts of the program written by someone else。

And then a linker puts all these different object files together and creates the executable。

And then the loader loads that executable into memory。

 putting the F language instructions in the right place in memory。

So here's another of key people in early computing， Grace Hopper。

She received her PhD in mathematics from Yale University and was the first person to develop a compiler。

She developed the cobalt programming language， so prior to this。

 all programs were written in assembly language or directly in machine language and translated by hand。

 and she built this compiler that went from a higher level language to the assembly language。

Edmiral Hopper was also a highly decorated naval officer。

And had major accomplishments in World War II。So now let's take a look at what's stored in memory。

The instructions for our program need to be stored in memory。

 they're also known as the text of the program。And data needs to be stored in memory。

We've already looked at the stack， which is used for holding some things。

 but theres also a section of memory used to store global or static variables that are allocated before the program begins。

 and there's another portion of memory used for holding dynamically allocated。

Variables that you might request with a malloc。So our next question is how big is memory？

And on our 32 B processor addresses are 32 bits long。

 so we have at most two to the 32 bytes of memory or 4 gigabytes。

And those addresses go from zero to F FffFF。So one of the only mistakes that you can't recover from in a computer architecture is not having a big enough address space。

And four gigabytes was big enough for a long time。But。

Modern computers and even mobile devices generally have more than that much memory and have needed to go to a larger address space。

 which has driven a lot of the advancing into 64 bit microprocessors。pastst decade。

Each system has a memory map that shows where different parts of memory are used for different purposes。

So the memory map can be a function of the overall system and the operating system。

 it's not necessarily defined by the processor itself。

But here's an example of a memory map that we might use on a risk five processor。The bottom。

32 kilobytes are used as an exception handler。 so let's say on reset。

 the program counter is set to address 0。And in address0， maybe there's a roM。

That tells us what to do and the first thing is to fetch some instructions out of a boot flash and load them into memory and then jump to those instructions。

Then we might have the text segment。Going up to。Big address here。

 This would be up to about 256 kiloomegaby。Memory。Then we'd have a global data segment。

That has enough room for our global variables that may be fairly small because there's deterministic number of global variables in our program。

And then we have space for dynamic data。We have a heap that starts at the top of the global data and grows up when you call something like malloc and request some memory that gets put on the heap。

We also have a stack that starts the top and grows down as we do function calls and have the store variables on the stack。

 the stack may grow down。If the heap and the stack ever collide。

 we've run out of memory and we've got a problem。🎼Then the upper half of memory might be reserved for the operating system and。

🎼啊，音两。So here's an example of a program。Let's say， we had。A program。

Let's say we have some global variables。She。Wい？And then we had a function。Funt that takes two inputs。

 and it does some stuff， possibly recursively。 And then we have a main function。

That sets our global variables f to2， G to 3， calls function with those variables。

 puts the result back in y， and then returns。Here's an example of translating the funt program to assembly language and then machine language。

 so funt。Needed to save some things on the stack。 So move the stack pointer down。

 store a return address and some local variables。And。Did some things。

Including possibly a recursive call to itself。And then returns。

We'll also notice that this program used some pseudo instructions， the move instruction。

Here was equivalent to an add eye， and the return。Construction was equivalent to jump register to RA。

Each of these instructions has a corresponding set of machine code。

 and all that machine code is stored at various addresses。 You notice that each line is。4our bys。

Then the main function is also stored here， each instructions is also four bytes。

And so we can begin by allocating space on the stack to store some variables。

We also need to load some values into F and G。F and G are global variables。

 and so their access relative to the global pointer。

 which is the base address of the global variables。

So we could load a of2 into a4 used for temporary purposes。St that into memory。

 and that would be our F equals 2。So we get our values of F and G。

Put them in a1 and A0 and then do a jump in link to our function。And when we come back。

We put our return result in Y， which is also relative to the global pointer and we clean up our stack。

And again， all of these turn into some machine code。So when you run this through the tool chain。

 one of the intermediate results is called a symbol table。

And it says the text segment begins at 1074。嗯。That was someplace where programs and variables。To go。

And in particular， funct and maine start at 10，14，4 and 10，180。That's this 10，14，4。And 1，0，1，8，0。

The data segment。Begins at 115 e0。And the global variables here are at 11，A，38，3，4， and 3，0。

And each of。FG and Y are four bys long。Fununkt is hexvesimal 3 c bytes long。

 and the main function is hexvesimal 3，4 bytes long。So。

Now we can see how all this gets put into memory。The tech segment here began at 10144。And we have。

This is。Funt。And this is mainine。When we begin running the program。

 the program counter is set to the beginning of Maine， and we start executing code。

The global pointer is up here。And Y G and F are in that global segment。

The stack pointer set at the top of memory and grows down as we put things on it。

 and in this program， there was no dynamically allocated memory， so nothing to grow upward。



![](img/89802b5829e83d45e5d07d10ede06c31_3.png)