# 哈维穆德学院《数字设计和计算机架构RISC版｜Digital Design and Computer Architecture： RISC-V Edition》 - P26：Chapter 2 14.Decoders.zh_en - GPT中英字幕课程资源 - BV1JC1MY1E7F

Hello， the topic of this video is combinational building blocks and in particular decoders。



![](img/ce09b5a049f30e601ca71b5e744b28b4_1.png)

So decoders are another handy combinational circuit。

They are a block with n inputs and two to the n outputs。

That assert exactly one of those outputs high at any given time。So。😔。

We choose one of the two to the n possibilities。For example， a2 to 4 decoder has two inputs。

 Let's call them a 0 and A1。 These are often called addresses because we use this with a memory。

And we have four outputs， we'll call them Y0，3 y3。Could write the 0，3，3 and binary。So， if。A。Is0，0。

Then we want to assert output 0。If a is 01， we want output 1， if a is 10， we want output2。

 and if a is 1，1， we want output 3。So we're just choosing one of those four outputs based on the two bits of address。

Here's an implementation。This is just a bunch of hand gates。Where。

The output is true based on the and of the variables and their complements。

So y0 is true on a1 bar and a0 bar。Why 3 is true。If a1。And a 0 actually。

We can use decoders to compute all the mean terms of a function and then use some or gates to compute outputs。

 So this is another way of doing logic。So let's say we had a function of two variables， A and B。

Such as this function， y equals A and B。Or a bar， B bar。And remember。

 this is the same as exclusive nor a exclusive， nor B。So we could feed A And B into our decoder。

 Get out for minter。This row will be asserted if A And B are both true， this。

 if A And B are both false and so on。And then we could or together。

 We want our output to be true when A And B are both true， Po， when A and B are both false。So。

Here we。Have built logic with a decoder。

![](img/ce09b5a049f30e601ca71b5e744b28b4_3.png)