# 哈维穆德学院《数字设计和计算机架构RISC版｜Digital Design and Computer Architecture： RISC-V Edition》 - P99：Chapter 7 6.Single-Cycle Processor Performance.zh_en - GPT中英字幕课程资源 - BV1JC1MY1E7F

Hello， in this video， well analyze the performance of the single cycle processing。



![](img/c2c1081eb52b9584db6d7395527734ec_1.png)

So now that we've built a single cycle processor， let's see how fast it can run a program。

Recall that the program execution time depends on the number of instructions in the program。

The average number of cycles it takes to run each instruction。And the number of seconds in the cycle。

In other words， it's the number of instructions temp the CPI times the cycle time。

So we need to figure out the cycle time of our processor。

And there's sometimes more than one possible cycle time we'll have to actually look at the elements to figure out which one is the limiter。

So I've labeled two possible cycle times in blue and gray on this figure。

We're looking for the longest path， so the hardest thing。

And the load word instruction seemed like the hardest thing because it uses the most different parts of the system。

Use the register file to ALU the data memory， and then writing back to the register file。

 as well as fetching your instruction。So the cycle starts when the program counter comes out of the PC register。

We go into the instruction memory， and we've got to wait to read out the instruction。

Then we fork and we have a couple different paths。let's start with the blue path。

Where we are accessing the register file， so we provide some bits from the instruction to the register file。

 and we wait to read out the data。Then that goes in as source A to。咩A you。We read out。That source。

And。That value goes to the ALU， we do a computation。We provide the result to the data memory。

Read out。The answer that we're loading。That goes into the result multiplex， sir。We bring it around。

And need to write the value back into the register file so the WD3 terminal holding result needs to set up before the end of the clock cycle。

Another possible critical path。Is one involving the immediate。So for the immediate。

 once we have the instruction， that goes into the controller and we need to compute IMM source to say what type of immediate is。

Bring that value down into the immediate。Extender。And based on that， we get out our immediate。嗯。

Take some time to choose that second source。And the source Bms。And then goes into the AU。

 and then the rest of the path is the same， we still need to redate it from the memory。

 go through the result mugs。Back。To the register file。So whichever those two is longer。

 may be the cycle of there。So。H的。Critical path of the single cycle processor。

Is the time through the program counter？Plus， the time to access the instruction memory。Plus。

 the longer of the two of either reading from the register file or decoding the instruction Xy。

Deign extending and going through the source Bm。Then we have the time for the ALU。

 the time for loading from the data memory， time for the result multiplexer。

 and the time to set up the register file。So。嗯，Limiting paths are usually the memory。

 the ALU and the registered file， those tend to be the hardest things to do。

So if we assume that the registered file read。Longer than the other path。Then our critical path。

Is all of this stuff。Or in other words， the time from the program counter。Two memories。

 the instruction and data。Leeting the register file， going through the ALU， the result marks。

 and then setting up to write the register。Here's a table of component delays。Assuming these delays。

We have。40 picoconds for the program counter。Two times 200 pico seconds for the instruction memory。

And data memory。We have。40。100 peac secondsds。To read the registered file。120 for the ALU。30。

For the result multiplexer。And 60 to set back up at the register file array and adding all these up。

400，506，26，60。6。97，50。750 picoconds。So now suppose we're running a program that has 100 billion instruction sent。

That's。10 to the level1th instructions。Times single cycle processor， so by definition。

 there's one cycle per instruction。Times the cycle time the 750 times 10 to the minus 12。

And that is 75 seconds。So our single cycle processor takes 75 seconds to run our program。



![](img/c2c1081eb52b9584db6d7395527734ec_3.png)