# 哈维穆德学院《数字设计和计算机架构RISC版｜Digital Design and Computer Architecture： RISC-V Edition》 - P85：Chapter 6 15.Machine Language R-Type Instruction Formats.zh_en - GPT中英字幕课程资源 - BV1JC1MY1E7F

![](img/17d857f9679f2b193b914ab008d5ad8e_0.png)

Hello， in this video， we'll look at machine language。

So so far we've been focused on assembly language， which is a human readable version of the native language of our computers。

But really， computers are digital systems， and all they understand are zeros and ones。

 So every assembly language instructions is actually represented as a pattern of zeros and ones。

In risk 5， each instruction is 32 bits long。So each assembly language instruction has an equivalent machine language instruction that's a pattern of 32 ones and zeros。

The reason we make all the instructions the same size is that simplicity favors regularity。

 so by having our instructions be the same size as our data word。

 each instruction also takes up one word and they pack in nicely。In an ideal world。

 we could just have one format for all instructions。

 but we have seen that some instructions need two source registers and a destination。

 other instructions need fewer registers， but they need an immediate。

 and some of them want a long immediate， such as a 20 bit immediate。So as a compromise。

 risk5 defines four different instruction formats。And we'll look at those in this lecture in the next。

The art type instruction format is for instructions register type instructions with two source opera。

 two source registers and a destination register。The eye type。

Has one source register any immediate and a destination。

The S or B type are used for stores and branches， and the U and J type format are used for load up immediate and for jumps that need a 20 bit。

Immediate。So let's start by focusing on our type instructions。

 These are for instructions that take three register opera， two sources。

 Rs1 and Rs2 and a destination R D。The instruction also has to have some bits to say what the instruction is。

 and we're going to store those in three different fields。 One is called op。

 which is also known as the op code or operation code。And the others are funt 7 and funt 3。

 which are 7 and3 B fields telling us what type of instruction to do by having this many different bits。

 we can encode a lot of different instructions in the instruction set。

 including some that the designers haven't even conceived of yet。

So the format of an R type instruction is a 32 bit word。The bottom 7 Bs are the op code。

The next five bits are specifying the destination register since there are 32 destination registers。

 log base 2 of 32 is 5， so we need five bits to specify how which one。

Then up here we have source 1 and source 2， which are also five bit fields to specify one of 32 registers。

And then we have three bits and seven bits left over that we'll use as function fields to tell us more about what kind of operation we're doing。

So suppose we wanted to do an add instruction， add S2 gets S3 plus S4。

We need to look in a table with listing of all the op codes for different instructions。

 there's a table in appendix B of the textbook and happens that for an ad instruction Op is 51。

Funkt 3 is 0， and funed 7 is 0。We also need to know which registers are used。

 and back at the beginning of this chapter， we talked about a link between the register names and their numbers registerister S2 was number 18。

 S3 was 19 and S4 was 20。So the destination register is 18。 source 1 is 19。 source 2 is 20。

 You've got to be careful putting them in the right order。So those are the values in decimal。

 let's convert them to binary。51 in binary。Is 32 plus 16 mix 48 plus 2 mix 50 plus 1 mix 51。

Destination register of 18 is 1，0，0，10 binary。Funt 3 was 0。 Ft 7 was 0。RS1 was 19， and RS2 was 20。

 both in binary。So then if we take this big mess of bits and we chunk it into groups of four。

The first four bits are 0。The next four Bs。A one insmo。The next4 bits。R a4 in the exodademo。

Next four bits are9。Den。😔，8ight。Then， another 9。Then a three and a three。

So this 32 bit instruction is easier to express in hexademal because there aren't so many digits to rattle off。

 and we'd say the machine language instruction for add S2 S gets S 3 plus S4 is hexademal 01498933。

And tellll that to risk5 processor。 and it'll know exactly what you mean to do。Subtract is similar。

The upper end is 51。Just like add， funt 3 is 0， but we differentiate it from add because the funt 7 is 32 instead。

T0 happens to be registered5。T 1 is register 6， and T 2 is register 7。

So if we encoded that the same process， pack the zeros and ones in and turn it into hexadeal。4，0，7，3。

0，2， B，3。Let's look at a few more examples。 A shift left logical S7 gets T 0 shifted by S1。

S shift left logical also has an op code of 51， but the funded code is。1， instead。

And the registers S7 was register 23。T0 was registered5 and。S 1 was registered 9。

Exclusive or has an op code also a 51 and a fundt。Value of four。

ILooking in a table in appendix sp of the book to find this。And shift very arithmetic。

 immediatete happens to have an op code of 19 instead。A funked field of phi and a funct 7 of 32。

And again， these registers， we could look up what their encodings are。

Turn all that into binary and then into hexodadecimal。

 and we've got three machine language instructions。



![](img/17d857f9679f2b193b914ab008d5ad8e_2.png)