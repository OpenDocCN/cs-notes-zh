# 哈维穆德学院《数字设计和计算机架构RISC版｜Digital Design and Computer Architecture： RISC-V Edition》 - P74：Chapter 6 4.Memory Instructions.zh_en - GPT中英字幕课程资源 - BV1JC1MY1E7F

![](img/86e21f03202dc17c5142cbbce4d0eee2_0.png)

Hello， in this video， we'll talk about opera and stored in memory。

So most interesting programs have too much data to fit in only 32 registers and will store the additional data kept in memory。

The memory is much larger， but it can be slow。For example。

 a embedded system may have kilobytes or megabytes of memory。And a laptop or a PC or。

A mobile device will have gigabytes of memory。So we'll keep the most common variables in registers。

 and then we'll store the less commonly used ones in the larger but store slower memory。First。

 we'll discuss word addressable memory in which we。Keep each memory location holding one word。

 then we'll adapt to bitete addressable memory， which most microprocessors， including risk five。

 are really bite addressable and will explore the difference。So in word addressable memory。

 each 32 B word of data is stored in unique address。 So word address 0 could have this word A，B C， D。

 E F 7，8。W address1 might have this data value， F2， F1， AC，0，7。嗯。

Regular instructions can't use memory directly as an opera end。 for instance。

 add and subtract only work on registers， not on memory。 So instead。

 we need a new type of instruction called a load。That reads data from memory into a register。

So the load word instruction。We'll read a value from a memory location and place it into a register。

An example of that would be load word T1 gets five parentheses S0。

And the first argument is the destination registered to put the result in。

And the second part is an offset relative to a base register。So in this case。

 the offset is5 relative to the base register of S0。And the answer will go into T1。So for example。

 let's say we have want to read a word from memory address 1 into to register S3。

We can write load word S 3 gets one parentheses 0。 The base address register is 0。

 which just test us the value 0。 We add an offset of one that gives us memory address 1。

We look at that address and we see stored in memory。Is F2 F1AC07。

 we read that out and we put it into S3。Similarly， theres a store word。Instruction。

That takes a value from a register and puts it into memory。So for example。

 if we wanted to store the value from Reg T4 into memory address 3。

We could take a base address of zero。Add an offset of three and store tea 4 into that。Supposing T4。

Contain the value。Feed cab。Then after we run the instruction。Memory location。Well。3， we'll have。

Feed cabin。Now， in reality， most computers use Bte addressable memory。

 so each data byte has its own unique address。And。We introduce load instructions that can access a byte as well as just a word。

So a word in our processor is 32 bits。So that's4 byte s。

 So each word address is a multiple of four bytes。And so word zero is still at address zero。

 but word one is really at address4， not one。Worard  two at8， word3， at C。

 word 4 at 10 and exit S mode。And within each of those words， there are four byte addresses。

For the bites within the word。So if we want to read about addressable memory。

The address of the memory word Ne needs to be multiplied by four。

So if we're interested in the second word， that's address 8 in memory。

If we're interested in the  tenth0th word， that's address 40 in memory， or in hexademal 40 is 0 x28。

So it's important to remember risk five is bite addressed， not word addressed。



![](img/86e21f03202dc17c5142cbbce4d0eee2_2.png)

Let's do an example。 Suppose we wanted to read the second word again。

 Now it's little word S3 gets 8 parentheses 0。 This is the correct code on risk 5。

And we would read the value at word to address 8 and put it into S 3。Similarly。

 if we want to write an address。We could do a store word。T7。Into address 0 x10 parentheses 0。

0 x10 is word hex10 address hex 10， which is the fourth word in memory。And we would put in。

The value from T7。