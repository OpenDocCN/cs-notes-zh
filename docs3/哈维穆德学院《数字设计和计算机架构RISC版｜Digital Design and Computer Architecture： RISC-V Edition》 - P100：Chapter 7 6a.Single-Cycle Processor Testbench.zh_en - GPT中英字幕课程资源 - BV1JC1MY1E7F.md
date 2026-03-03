# 哈维穆德学院《数字设计和计算机架构RISC版｜Digital Design and Computer Architecture： RISC-V Edition》 - P100：Chapter 7 6a.Single-Cycle Processor Testbench.zh_en - GPT中英字幕课程资源 - BV1JC1MY1E7F

Hello， in this video， we'll take a look at a very log model for the single cycle。

Our risk five processor and also take a look at the test bench to prove that it's correct。

So here's the design of our overall system。We're going to have a risk processor comprising the data path and controller。

 just like we talked about。We also need the memories and let's pull these memories out of the data path because typically they're external to the processor core。

 so we'll have an instruction memory and a data memory。你啊。

Datapath will send the program counter to the instruction memory to say which instruction to fetch and it will get back the instruction from the RD port of the instruction memory。

 that instruction will go to both the data path and the controller。To access data memory。

The data path will take the ALU result signal， sended out as data address to the address port of the data memory。

We'll send the right data value to the right data port of the data memory。

 and it will get back the read data signal from the read datata port of the memory。

 and there'll be a right enable signal for the data memory called Memite。

 just like we already have from the controller。Controller will receive the instruction and based on that。

 produce a bunch of control signals， the data path will reply with the zero signal when the。

Answer zero。And the data path and controller， both data path anyway。

 receives a clock signal and a reset to initialize the program counter to the beginning and execute instructions one at a time。

Let's switch over now。2。

![](img/a2c40082567b1c9646ecdaf97be0c890_1.png)

第。嗯。Test benchch so this processor is going to run a program to tell us if it's correct and there are a couple strategies for testing processor。

 one is something systematic that applies a whole bunch of tests to check each kind of instruction individually。

Another is a more holistic but ad hoc testing methodology where we put in a program that exercises all the programs。

 all the instructions， and then we check the program produces the right answer in the end。

So for this simple processor， we're going to do this ad hoc technique of a program。

So let's walk through the program and see what should be happening。We start Maine。

We're going to add I x2 get x0 plus 5， remember x0 is to0 register。

 so this should put the value 5 into x2。And this instruction， let's say， begins at。Location。Z。

This should say locate for the value。71 in the address 84 when we're successful。All right。

 so I address zero instruction memory。Have our first add I， and X2 gets 5。Next instruction。

 next add I makes x3 get 12， and the next add I makes。X7 get x3 minus9， which should be three。

So this is testing addition of negative numbers。Then let's test the or instruction while or x4 gets x7 or x2。

X7 was3， x2。Was a five， so three or five in binary， three is zero011，5 is0101。

 so the answer should be 0111， which is7。Now let's test the and instruction。

 so and x5 gets x3 and x4。X3 was 12， x4 is 7。12 is 1100，7 is0111， or and those together， we get 010。

0， which is four in decimal。Next， let's do an addd。We add x5 gets x5 plus x4。

 x5 had been four from the end。X4 had been seven from the or， so when we add them together。

 we should get 11。Then we'll do a B E Q X5 x7 end。 So x5 was 11。 x7 was3， so they're not equal。

 so this branch should not be taken。 so we test that not taken branches work。

We continue and test a set lesson instruction。We'll see is x4 less than x3。So it is x3 less than x4。

X3 was 12， x4 was 7， so it' 12 less than 7， no， so the answer on set less than should be0 or false。

So now x4 is0。Next， we'll do a branch on equal。Is x4 equal to0？It is， so that should be taken。

 so we should skip over this add eye instruction。 This add eye would put a0 into x5 if it were executed。

 which would mess up the contents of x5。So now we're up here at address 28 in instruction memory。

 we do another set Le。Is three less than five， yes it is。 so set less than should produce a one。

 that's way we're testing both set less than producing a zero and a1。Then we do an addd。

 x7 gets x4 plus x5， x4 was the one from the set lesson， x5 was the 11 from up here。

 so when I add them together， x7 should be 12。Then subtract x7 gets x7 minus x2 that's 12 minus5 should be 7。

And will' store that value of x7 into location 68 parentheses x3。So， X3 contained。12。

68 plus 12 is 80。So we should store the value 7 into memory location 80。

We're testing that we can write to memory。Now let's test that we can read the value back。

So we'll load from address 80 relative to x0。That's also addressed 80 since x0 contains zero。

And we'll load that index2， so now x2 should have the seven。Let's test a jump and link instruction。

 so we'll jump to the end。That way we're seeing that we can step over this instruction that would be messing up X2。

Now let's do an add。嗯。The jump and link。Should put the return address。

Which was hexodadecial 40 or decimal 64。Should put that into the x3 register。

 so let's check that it's there by doing an ad x2 gets x2 plus x3。X 2 was 7。linknk value is 64th。

 so added together we get 71。And finally， let's store the 71 into memory location 84。

So at the end of the program， we should see a write。

 memory right with a value 71 into the address of 84。

And if any of the instructions messed up along the way， if we had any bugs in the processor。

 then it would be unlikely that this would still come out correct and we'd get a wrong right。

So next we need to translate that risk5 program into machine language and that's kind of tedious process。

 it's best to do it with an assembler and here we get the 18 different machine language instructions corresponding to those 18 instructions of assembly language。



![](img/a2c40082567b1c9646ecdaf97be0c890_3.png)