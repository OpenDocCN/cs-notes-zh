# 哈维穆德学院《数字设计和计算机架构RISC版｜Digital Design and Computer Architecture： RISC-V Edition》 - P73：Chapter 6 3.Operands.zh_en - GPT中英字幕课程资源 - BV1JC1MY1E7F

Hello， in this video， we'll talk about the operas used by instructions and in particular。

 focus on register opera。

![](img/22b26cab295a29ed224327c56e162dd8_1.png)

So recall from our example of add A+ BP。A equals B plus C。That A， B and C are ups。

And there were two sources in a destination。They have to be stored physically somewhere in the computer。

And three choices of where we can keep our brands。Are in registers in memory or as constants？

Registers are where we have a small set of information usually stored in footflps or a registered file。

That can be accessed very quickly。Memory is usually built with SRM or DRAM。

 and it has a larger capacity， but also a longer access time。

Then constantss are also known as immediates。 They are physically in the instruction itself。

So they're hardwired into the instruction。Let's focus on our registers。 Risk 5 has 32 registers。

 each 32 Bs wide。These registers are much faster than accessing memory。

And riskk 5 is known as a 32 B architecture because it operates on 32 B data。

There is an extension to riskk 5， a 64 bit version of the architecture in which the registers are 64 bits wide。

 and when you load data from memory you get 64 bit chunks。This leads us to design principle 3。

 that smaller is faster。 Risk 5 only has a small number of registers，32 of them。

And computer architects pick that size of the register file very carefully。

 the clock period of the system could be limited by many different things。

 could be limited by the ALU speed， it could be limited by time to fetch an instruction or access data memory。

 or it could be limited by the register file。And we choose a small enough register file that its not the limiting factor in the computer。

 so it doesn't prevent us from building fast computers。

The 32 registers in Ri5 are known as x0 through x31。And they can be called by these x's。

 but they're more commonly called by other names that have some convention to the programmer。

Register zero。Is named zero or also x0， and it's hardwired to the constant value0。

That value zero shows up in computer programs so often that it's helpful to have a register that's just hardwired to always have zero。

That leaves us 31 other registers to do interesting things with data。In principle。

 you could store any information in any register， but programmers have agreed on a convention。

In which they use certain registers for certain purposes。

 and that makes it easier for two different programmers to write different functions that can talk to each other easily。

So x1 is known as the return address。And it's used to store the address that you should return to after a function call。

X2。Is called the stack pointer。And its address in memory with a top of the stack。

Which is used for holding variables， as we do function calls。 And we'll come back to that later on。

There's a global pointer and a thread pointer， we won't talk about too much in this chapter。

But the remainder of the registers are divided into three groups。S， T and A for saved registers。

 temporary registers and arguments。The S registers。Arrged。By the programmer to store variables。

 So there's S 0， S1 and S 2 through S 11 total of 12 registers stored in x 8。

 x 9 and X 18 through 27。These are variables that need to hold their value when you return from a function call。

The temporary Regs。T 0 through T 2 and T 3 through T 6。Are used for holding temporary results。

 for instance， when we did that a equals B plus C minus D。

 we needed a temporary register to hold an intermediate result。

And then the A registers are arguments。 these are used for values passed to a function and values returned from a function call。

So as a programmer， you can use either name。The x's or things like RA M0。

 by using the name is clearer to the reader。So let's rewrite our previous instructions using these real registers。

 so we had add a equals b plus C or as b plus C， and now let's say we wanted to keep the variable A in register S0。

 B and S1 and C and S2， then we would rewrite our program as add S0 gets S1 plus S2。

The pound symbol in assembly language program indicates a single line comment。

 and it's a good idea to have comments in your code to indicate what registers are being used for what variables to make it easier for your reader。

InAnother example， let's introduce a constant。Add a equals B plus 6。

We introduce a new instruction at I stands for add Immediate， and it takes a destination， a source。

 and a constant or immediate。So here again， we have a and S 0， B and S1。

 So we'll add S 0 gets S1 plus 6。

![](img/22b26cab295a29ed224327c56e162dd8_3.png)