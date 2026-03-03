# 哈维穆德学院《数字设计和计算机架构RISC版｜Digital Design and Computer Architecture： RISC-V Edition》 - P88：Chapter 6 18.Decoding Instructions & Addressing Modes.zh_en - GPT中英字幕课程资源 - BV1JC1MY1E7F

Hello， in this video we'll look at how to read machine language instructions and how operas are addressed。



![](img/cee3632c735e7bc5d8da7163942a7b0d_1.png)

So here's a summary of some of the instructions we've looked at so far in。

Assembly language and machine language。So each of the instructions has its assembly language mnemonic。

And it has a corresponding op code。So the R type instructions add Subtract。

 and or all have an op code of 51。And they're distinguished by means of the funct 3 and the funt 7 bits。

So， for instance， atom and subtract are identical in have funct 3 as well。

 but differ in their funt 7。And an ore happened to have different encodings for Ft 3。

Add I is an I type instruction with an op code of 19。

The branches are B type instructions with an op code of 99 and a funcked field to distinguish between them。

Load Word has an op code of seven。And a fet three of two。

Storeward has an up code of 35 and a f3 of two。Jump and link。Has an op code of 111 its J type。

 jump and link register is 103。Load up intermediate is 55。 that's seeing type。Jump and link register。

 interestingly， is actually an i type instruction。Because it only has a 12 bit offset and it takes a destination register。

So if you want to interpret some machine language code。

 the best place to start is going to convert the hex decimmal number in binary and look at the op and function three fields to tell you what type of instruction is and how to parse the rest of it。

And then extract the fields based on the type of instruction。

So suppose we met these two machine language instructions in a dark alley。For this instruction。

The bottom bits are 51。That tells us。That were an art type instruction。

And we need to look at Ft 3 and Ft 7。So Ft 3 is up here， that's a zero。

So now we know with funk 3 of zero， it's either add or subtract。And finally。

 we have to look at the upper bits。0，1，0，0，0，0，0，0。That is。32 which subtract。

So this instruction is a subjecttract。If we encounter this instruction。

We look at the bottom bits and the op code is 19。So 19 looks like an eye type instruction such as add eye。

So again， we look for the F three field at zero。And sure enough。With a funct 3 of0， it is an addey。

Once we have figured out what format of instruction is。

 we can unpack the rest of the bits into those fields。So our first example here。

 we said was subtract instruction， it's R type， and these are the R type fields。So。4our。Is 0100。

 or 1 is 0001。F。Is all ones。E is 11，10。Eight is10，0，0。3，0，0，1，1。B，10，11。And 3，0011。

 So we've unpacked this hexadeadecimal number into the 32 bits of binary。

We'd already looked at the opt Ft 3 and Ft7， so we know it's a subtract。

 and the other fields will tell us our source and destination registers。

So the destination register is x7， which we could look up in the table is register T2。

And the source registers are X29 X31。Which are T 4 and T6。Similarly。

 this instruction we had figured out based on Op and funk 3 is an ad immediate。

And we can unpack the rest of the bits like this。 We see the immediate。

Is a negative number because of the leading one， its negative 38 as a two complement number。

RRS1 is9 and RD is7。So that's an addd。T 2。Gets。嗯。S 1。Plus， negative 38。

So another part of understanding the machine and assembly language is the addressing modes。

 how do we address the opera in an instruction？And some of the choices。Were discussed here。

Our tech instructions use only register addressing modes， so they take two sources in a destination。

Immediate。I type instructions， take one source， one destination register。

 and an immediate for the I type the immediate the 12 bit signed value。

Our basin address is used in loads and stores。And。The address in memory that we want to access is computed by taking a base address from a register and then adding an immediate。

Here's another case for a store where the base address is in T1。

We add 25 to it to get an address of t1 minus 25。Finally， there's PC relative addressing。

This is used for branches and jump and link。And the。Yeah。PC relative。

 we have to compute how far it is to our destination compared to where we are right now。

So let's say we have a branch not equal to L1。The branch not equal happens to be at address EB0 in memory。

And label L1 is a 354。So。The distance of the branch is EB0 minus 354 backwards。So it's at。

B 5 C backward in hexodadecimal or 2908 backwards。 So immediate should be negative 29，08。And。

Here's how we represent。Negative 2908 has a 13 but twos complement number。And again， remember。

 the least significant bit is always zero and is omted from the encoding。

So we have our Op codes branch。Funt field for one for branch equal。

And the source registers were S8 and S9。Whichever registers 24 and 25。And our branch。The。

Bottom four bits，0010。Wint here。The next bits。10 through5。Are these。Then bid 11。

Is here and bit 12 is here。And so that concludes addressing modes and how to interpret machine language instructions。



![](img/cee3632c735e7bc5d8da7163942a7b0d_3.png)