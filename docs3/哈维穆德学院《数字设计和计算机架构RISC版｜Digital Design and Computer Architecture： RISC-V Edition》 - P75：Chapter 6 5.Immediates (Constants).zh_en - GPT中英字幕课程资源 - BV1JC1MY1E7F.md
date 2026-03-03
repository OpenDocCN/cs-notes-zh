# 哈维穆德学院《数字设计和计算机架构RISC版｜Digital Design and Computer Architecture： RISC-V Edition》 - P75：Chapter 6 5.Immediates (Constants).zh_en - GPT中英字幕课程资源 - BV1JC1MY1E7F

![](img/15031ee90ecc699a4d2bde4dae37f9a4_0.png)

Hello， in this video we'll talk about generating constants so so far we've looked at operaans stored in registers and operaan stored in memory now let's look at constant operas also known as Is because they're immediately available as part of the instruction。

So。Some instructions like AddI can take a 12 bit immediate as part of the instruction。

Let's say we had this program， A gets minus 372 and B gets。B equals a plus 6。

And we wanted to keep A and S 0 and B and S1。Then we could use the AddImedia command。

 addingmedia S0 gets0 plus negative 372。That will add 0 plus minus 372 and put the answer of minus 372 into a。

Then we could do another add immediate S1 gets s0 plus6 that does the B equals a plus 6。

Because our instructions are of finite length， we can only store medias of finite length。

And as we'll see later， in the Rik five instruction set， we can only store medias up to 12 bits slot。

However， those immediates are stored in twos complement form and their sign extended to 32 bits。

 so we can store both positive and negative numbers。In the range of minus。2048 up to positive 2047。

Suppose we needed a longer constant， something up to 32 bits。

Risk 5 has a special instruction for that situation。 It's called load upper immediate。

Lad upper immediate puts a 20 bit immediate into the upper 20 bits and zeros into the bottom 12 bits。

And we could follow that by an add eye to add the values to the lower bits。

So let's say we wanted in a equals to 32 bit constant FEDC， 8765 and hexsmal。And suppose a was in S0。

We could do a load upper or immediate。S0 gets F E D C 8。 That's the upper。20 bits。

And then we could do an add eye。S0 gets S 0 plus 765 that adds to 765 to the lower 12 bits。

 completing our 32 bit number。Load up or immediate only needs a single register and then an argument。

 an immediate， and that's why there's space in the instruction for a 20 bit immediate。

So even though we're saying simplicity favors regularity。

 this is a case where we're making good compromises to be able to handle 32 bitten instruction。

With a special 32 bit immediate with this special LUI instruction。

It's important to remember that a media is going to sign extent the 12 bit immediate。

So if the 12 bit immediate had a one in the most significant bit。That is going to get sign extended。

And create ones and all the other bits。嗯。And that effectively makes it look negative。

So if we want to do load a constant， that's 32 bits。Where。对。嗯。Most significant bit of the bottom 12。

 It's a bit 11。Is a one。We need to。Increment the upper bits of。The LUI by one。

So let's say we wanted to get FEDC，8 EA B。We could do an LuUI of FeEDC9 instead of8。And then， EA B。

Is negative 341。So we could add negative 341。Which is FffF F， FF EAB。Add it to the FEDC 9，0，0，0。

 and we get our desired FED C 8， EA B。So if you are trying to create a long constant like that。

 you got to be careful of this bit and handle it。

![](img/15031ee90ecc699a4d2bde4dae37f9a4_2.png)