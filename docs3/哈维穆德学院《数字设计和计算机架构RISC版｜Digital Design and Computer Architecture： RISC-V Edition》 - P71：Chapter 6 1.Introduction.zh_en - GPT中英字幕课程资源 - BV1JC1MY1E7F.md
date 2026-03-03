# 哈维穆德学院《数字设计和计算机架构RISC版｜Digital Design and Computer Architecture： RISC-V Edition》 - P71：Chapter 6 1.Introduction.zh_en - GPT中英字幕课程资源 - BV1JC1MY1E7F

Hello and welcome to the sixth exciting installment of digital design and Comp architectureect。



![](img/ac33e1e3f6630c207df1c17affce0d80_1.png)

In this chapter we'll be talking about architecture。



![](img/ac33e1e3f6630c207df1c17affce0d80_3.png)

So architecture is the programmer's view of a computer。

 it's the set of instructions and memory that a programmer needs to know that defines the computer if you build two different computers with the same architecture。

 they could have entirely different implementations but still run the same program。

We'll also be looking at the level above a little bit。

 looking at software and operating systems that run on an architecture。

I willll start by focusing on assembly language programming。

 which is the native language of the machine。And how to get into translating programs from a language like C into assembly language。

Then we'll go into machine language， the ones and zeros that actually run on the hardware。

We'll talk about dressing modes， we'll talk about the process of compiling assembling and loading program and various odds in its。

So previously， we've been working at the low levels of abstraction。 we started with devices。

 worked our way up to digital circuits and logic， and now we're jumping up to the opposite end architecture。

 the programmer's view of the computer。And then in Chapter 7。

 we'll work our way back down to micro architectureure to meet in the middle and look at how to build hardware that actually implements an architecture。

So the instructions and assembly language are the commands in the computer's language。

And they come in two formats。 Assembly language is a human readable format of these instructions。

And machine language is a bunch of ones and zeros。 That's computer readable。

There are many different architectures in the world。

 and this book is focusing on the Rik five architecture。

A risk5 architecture was developed by researchers at Berkeley， starting in 2010。

 it's the first widely accepted open source computer architecture。

 so it can be used freely by anybody it can be enhanced。

And it's gaining a lot of traction in industry right now。 It's a hot thing。

 So we're focused on that one in this class。But once you've learned one architecture。

 it's really easy to learn all the others。Some of the originators of computer architecture。

 Christie Soovvic from Berkeley， was a pioneer on developing Risk5。

And is presently chairman of the Board of the Risk5 Foundation and co foundunder of SI5。

 which is a company that is commercializing Risk5。His colleague， David Patterson。

 is a longtime computer architect at Berkeley， who co inventedvented the reduced instruction set computer notion back in the 1980s。

And was also a founding member of the Rik 50。David Patterson was a co recipient of the Turing Award for pioneering the quantitative approach to design and evaluation of computer architectures。

And his colleague John Henessey from Stanford， was also co recipient of the award and co author of classic textbook titled Computer Architecture。

So prior to Heness and Patterson， computer architectures were often evaluated based on how elegant they were。

For instance， an architecture that might be able to run pastcal or Lisp programs directly。

And Heness and Patterson made the bold statement back around 1990 that computer architectures should be evaluated based on how fast they can run your program。

That led to the notion of reduced instruction set computers。

 where instead of having the largest set or most flexible instructions。

 they simplified to a minimal set of instructions that were capable of running whatever program。

 and because it was simplified， they could be built with really fast， efficient hardware。

And could run at much higher frequencies and deliver much higher performance。

So risk computers in the 1980s。Revolutionized the field of computer architecture and Henessan Patterson's book。

嗯。It's been in classic， it's gone through many additions。

They also wrote a textbook titled Computer Orization and Design that presents the micro architecture in a way very similar to this book that's inspired this book。

So Henness and Patterson articulated four main principles for design。

First is that simplicity favors regularity。So keeping things simple and。

Having as few special cases as possible is good。The second one is make the common case fast。

 look at what your architecture spends most of its time doing and make those cases really fast。

Number three is that smaller is faster， if you can build an architecture with fewer instructions。

 fewer registers， then it will be able to run those faster。But finally， number 4。

 good design demands good compromises。 So instead of sticking religiously to the first three principles。

 occasionally， you do have to make compromises for the sake of efficiency。



![](img/ac33e1e3f6630c207df1c17affce0d80_5.png)