# 普林斯顿大学《计算机科学：算法、理论和机器｜Computer Science： Algorithms, Theory, and Machines》中英字幕 - P31：31_08_02_概述_2.zh_en - GPT中英字幕课程资源 - BV1Ct42177Y6

![](img/c6dca36bcf624375d0b2e0f50735f859_0.png)

And now for something completely different， we're going to fulfill the last part of the promise that we made at the beginning of this course that we wanted to demystify for you what goes on inside the machine。

So to begin， we're going to describe an imaginary machine that's very similar to the computer that you use every day。

To begin， we'll start with a basic overview of the properties of the machine。

This is an imaginary machine that we created for this course， it's very similar to ancient computers。

 that's a picture of a PDP8 machine from the 1970s。

 but also surprisingly it's also quite similar to today's smartphone processors and countless other devices that have been designed and built over the past 50 years。

In fact， it's really rather incredible that from a bird's eye view。

 the design of these machines is all virtually the same and you'll see that as we get into the topic。

So why do we want to study the machine like this？ Well。

 our main thing is to prepare to learn about computer architecture。

 We're going to be talking about how your computer's processor works and we're going to try to develop an understanding of that。

What are the basic components of your computer's processor and how do they interact？

To look at these things， we need to learn about machine language programming。

 the lower level language that your computer uses to get its job done。

 and you'll learn about how Java programs relate to your computer and the relationship between the code that we've been writing and the actual code that your machine runs。

 it really is the key to understanding references in Java。

 which is one of the most important concepts in Java programming。

There's also just the intellectual challenge of attacking a new programming regime。

 actually machine language programming is fun and many of you will get to experience that。

 and it's still the case that it's necessary in some modern applications to go down to the low level for performance and still today people working in multimedia computer games or embedded devices and scientific computing are writing machine language programs in order to get good performance。

But our main idea is through these next four lectures。

 we want you to learn the fundamental abstractions that have informed processor designed for decades and are likely to for decades to come。

All right， so to get started， we need to work with the idea that everything in our Tory machine and in your real machine is encoded as a sequence of bits。

So we need a language to communicate with the machine really。

 and the reason that everything's encoded in bits is that in the physical world it's easy to represent two states on or off and we'll see that directly when we start working with this machine。

Usually bits are organized in contiguous sequences in our machine it's 16 bit sequences in your machine maybe it's 64。

 but the idea is the same so the idea is the information is encoded as bits but we represent them in the machine and we interact with the machine using switches and lights and the switches are either up or down on or off the lights or either lit or not lit on or off and so we're representing the information with this physical these physical artifacts that we use to communicate with the machine we tell the machine what we want by turning a switch on or off the machine tells us what it has by turning on the light or not。

Now， communicating in binary is definitely inefficient。 So we always use a more convenient notation。

 and we're going to use exodademal notation to communicate with the machine。

And that's just a base 16 number， it takes a tiny bit of study。

 but it's really very simple to convert to and from hexadeademal notation in binary notation what we do is in a base 16 number we have to have 16 different digits rather than the 10 digits that are familiar from decimal notation and we call those last five digits we just use A B。

 C， D， E and F。So to convert a binary number less than 16 to hexodadeciimmal。

 I've just used this table and the first few are familiar from converting a binary to decimmal。

 but then the next ones we represent 10 with A， 11 with B， 12 with C， 13 with D。

 14 with D and 15 with F。And in a very short time， you'll get used to this table and you can do the math。

 but the fact is that if you have a binary number， say this 16 bit sequence。

 we can convert that one to and from hex just by doing one digit at a time。

So we look at the first four bits。 those are 0，0，1， we look it up in the table。 it's1。

 Then we do the next four bits。 that's 1，0，0，0。 look it up in the table。 That's8。 the next four，1，1。

10， that's E and the last or 7 and conversely if we have that hex number 18 E7。

 we know that each one of those hex digits corresponds to fourit4 bits。

 we just look up in the table and find the bits。But absolutely everybody knows this table after just a short amount of time working with the hexodadecimal notation。

That's the way we're going to communicate with the machine you wouldn't want to be trying to remember a long binary number but it's not so hard to remember a hex number that has represents the same number of binary digits and there's much more detail about Hex and binary on the book site and in the book if you want to study it more detail okay so what is this toy machine made up of what's inside so we're going to talk next about the basic components of the machine it's got a memory it can remember things and work with them that's where the data and the code is held and we'll be looking at that in detail。

It's got something called registers， those are kind of like your variables in Java programs and you'll understand better after we look at the circuit that implements the machine why we need registers。

 but they're there。Then there's the arithmetic and logic unit。

 that's the calculator that actually does things like add numbers or compute the end of bits and so forth。

And then there's two special components called the program counter in the instruction Reg。

 that are abstractions that make everything go。Let's look at these in detail。So for memory。

 what that does is holds all the data and all the instructions that we're going to work with in our programs。

 you're of course aware that your computer's got a memory， you pay more for more memory and so forth。

Of。For toy， we have just 256 words of memory and 16 bits in each word we're going to talk about a machine that's quite a bit smaller than your computer。

 but the basic principles are easy to extend to get to the size of your computer and we'll talk about that a little bit later。

 what we want to have is a machine that is powerful enough to really actually do many。

 many of the things that you've already done with Java programs。

 but also simple enough that we're going to be able to look at the design of a complete circuit for that machine。

So toys just got 256 different words， it's got 16 bits in each word and the memory is connected to registers。

 generally we take stuff out of memory， put it in registers。

 operate in the arithmetic logic unit with the registers and then put it back in memory and we'll look at that in detail。

What we need to do is address the words， so each word's got a name and just we just use hexadeadecimal for the addresses。

So we number them from 00 to FF FF is the hex number 255 The hex number 100 is 16 squared or 256 one less than that is FF is 255 and again when you think about binary arithmetic it's pretty easy to learn about hex arithmetic and anyway this is quite simple layout of the memory the first column has all the first all the words whose addresses start with zero hex digit there's 16 columns one for each hex digit next one is one next one is2 and so forth and all you have to do is bear in mind that it's not decimal it's hexadecimal so that after9 is a after a is B and so forth and after0 f is 10 so we number the words from00 to FF and really we're going to think and hexadeadecimal for the next four lectures for sure and just use array notes。

So to refer to the contents of memory， we say M of2 a so the M means memory and 2 a is the address2 a and what words in theres CO24 Again。

 CO24。 That's four hex digits，4 bits per digit。 That's 16 bits。

 Every memory word we can specify which word it is with8 bits。 there's 255 of them。

2 hex digits and we can specify the contents with four hex digits or 16 bits。 That's the memory。

 and it's important to remember that a table of 256 words。

 which we can fit you can fit in just a page really only we're going to show four out of the 16 one quarter of the memory right here。

 but if you know all 256 words， you know the contents of memory Now your memory might contain a billion64 bit words。

 So there's a lot more to it but usually you're only using a small。Part of a time anyway。Okay。

 the next thing is the arithmettic logic unit。 That's toy's computational engine。

And the way to think about arithmetic logic unit or ALU is that it's a calculator。

 it's not a computer， it's the hardware that implements the operations that we perform on data。

 like adding things and doing an and and so forth。And in a couple of lectures we're going to look at precisely how it does that and what kind of circuit we can build that actually implements the operations。

 but for now it's not any different than an advocus or a slide rule or a calculator。

 that's the way to think of the ALU， it's the thing that calculates。

 takes two numbers as input perform some operation on them and gives the result as output。

 that's the ALU， an important part of the computer but just one part。Then there's the registers。

 the registers are 16 words， they're like the memory but there's only 16 of them so we can number them from 0 to F and we'll use the names R0 through RFf for the registers in their words so there's 16 bits so we need four hex digits to specify each register and again you think of those as like variables。

 there's this scratch space that we use for calculations and for moving things in and out of memory and very soon you'll see how the registers relate to the memory and to the ALU they're connected to both。

By convention in toy， we make register zero， always zero。

 and that's just to simplify code and we're going to do plenty of toy code in the next couple of lectures。

And we also often keep 0001 in Reg1 although that's not an absolute convention and all of these things are just illustrating the types of things that are found in real computers and we're going to be very specific about them because we need to be very specific in order to write code and also to build a circuit that implements this kind of thing so you might think well what do we need really registers for well we'll talk about a little more later but the basic reason is that there's too many different memory names or addresses to be able to always be specifying things in memory when you have a huge memory you need a lot of bits to specify word and memory and that's lot and that's wasteful often why not just always connect the memory locations just to one another what do you need the registers for anyway and again in this case there's just too many different connections and you'll have a better feeling for this。

After you've seen the circuit， but just want to just briefly indicate why we need something like registers and all computers have registers。

So again， it's important to remember， a table of 16 words completely specifies the content of the registers。

Okay， so there's the memory in the registers in the ALU。

 the last two things are the program counter and the instruction register。As we're going to see next。

 the way that toy operates is by executing a sequence of instructions。

These are the critical abstractions that make this happen are the program counter。

 which we call the PC。And that's the memory address of the next instruction to be executed。

And the instruction register， which is the actual instruction being executed。So these abstractions。

 when we think about them when we're writing toy programs。

 and we actually physically realize them when we build a circuit to implement the tory machine。

And the basic idea of the machine is very simple， it's based on a fetch， increment execute cycle。

 so what happens is fetchch gets an instruction from memory into the instruction register。

 which instruction， the one that's referenced by the PC。

And then increment most often just increments the PC by one to reference the next instruction in the memory and then execute。

 does whatever the instruction specifies， it might be moving data to or from memory it might be changing the PC or might be performing calculations as specified by the particular instruction in the instruction register and we'll see detailed examples of this in just a moment。

 but the basic idea is that all the machine needs to do is fetch increment execute。

 fetch increment execute specifically what it does is encoded in the instructions and again。

 all computers operate in this way。Finally， that's really that's it。

 that's what the machine is and the fundamental concept that you want to be sure that you get at this point is that the contents of the memory the registers in the PC they for one thing is they provide a record of what a program is done if a program changed things。

 then it's going to be reflected in the state of these things。

 some memory word will have the sum of two numbers or whatever else。

But the other more important thing is that it completely determines what the machine will do next。

 The machine is deterministic。 What's going to happen next is the PC。

 the instruction is going to be fetch from where the PC points to。 PC is going to increment。

 The instruction is going to be executed and so forth。

 The state of the machine completely determines what it'll do。 That's a deterministic machine。

The IR and the ALU are there， they hold kind of intermediate states of computation。

 so we don't worry about them in terms of the state of the machine。



![](img/c6dca36bcf624375d0b2e0f50735f859_2.png)

So now what we're going to look at next is what kind of data we hold inside the memory and what kind of instructions or operations we perform on that data。



![](img/c6dca36bcf624375d0b2e0f50735f859_4.png)