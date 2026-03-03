# 哈维穆德学院《数字设计和计算机架构RISC版｜Digital Design and Computer Architecture： RISC-V Edition》 - P56：Chapter 5 3.Ripple-Carry Adders.zh_en - GPT中英字幕课程资源 - BV1JC1MY1E7F

![](img/c937f88317660a99861968153b9e6201_0.png)

So let's talk about the first kind of carry propate adder， the ripple carry adder。 So this adder。

 we're going to， you know， put our 1 bit adders here。

 and we could potentially use just a half adder on our zeroth bit。 we're going to add。

Those zero bits。A sub zero and B sub zero and produce。Or some bit or some zero sub zero bit。

There's our adder there or in this case， a one half adder， and we have our carryout。Here。

 this is c sub 0。 the carry out a column is 0。So if we had our example from before 1011，0111。

And we added those together。 Here's a sub 0。Here's B sub 0。And our sum S of0 would be  zero。And our。

Carry out of column 0 would be。In this case， one。Okay， so we want to feed that into the。

 as if you can see from our addition here， this is the carry in of column1， remember column zero。

 column 1， column two， and column three。😊，And so we feed that into now into。Colum 1。

This is the carry in input。Have this now， full outer。A sub one and B sub one。

 now we're going to add these。Now these next bits， A sub one and B sub one。

And add that to our our carry in here。That came in from column， the carry out of column 0。

And we produce。Our sun bit。Sss sub one。For the。First column， right。

 the zeroth column Now the first column and will produce a carry out。

C sub1 or right we're either a one or0 on the carryout in this case。

 one plus one plus one is three so if we get one and our carry out of that column。Home1。

Is one in this case？And it's going to get carried in。To。The next column， column 2。Okay， so same。

 you know， right same pattern here。A sub 2 and B sub two。 we're going to add those。

 We're going to add that to。The carry out from column one， which is the carry in。Column 2， I call0。

 column 1， column 2。I'm going to produce some bit two and the carry out。I call them to。And so forth。

 right， we could make a 32 bit ater or a 64 bit ater or whatever bit ater in the same way。

 But we can see the slow path。Is where this carry ripples through。Our adders until the n minus1。But。

So that path is pretty slow， but you know， pretty simple， we use you know， full ladders。Or you。

 possibly a half hourer on that right most or least significant bit。And so here we have it。

 it drawn with， in this case is a 32 bit ripple carry adder。P carry out her。

And so we can ask ourselves well， what is the delay of this， well， you know。

 we get this pretty quickly right， a sub zero B B sub zero and potentially carry in。

 we'll see why we might want to keep that as a full ladderer and have that as a carry in。😊。

allow it to have a carry in coming into it on that least significant bit in the zero column。Well。

 that's not the slow path， though， right， That's not the critical path。

 If we put our numbers in A and B and are waiting for the result， Well， the slowest path is through。

Right， through the carry。Through the carry chain。And so if we're thinking about this for well。

 for 32 Bs， while we have one full ladderer delay， right。

 the delay to take these inputs and produce that carry out output。And then， that comes in。

Another full ladder delay to produce the carry。For the next column， C U sub one and so forth。

 So the delay for this is。In this particular case， 32 by out， 32 full adder delays。

We've designed a fill out up you know the previous slides and so we could figure out what that delay is。

From our gates， from our individual gate delays。And generally， for an ended adder。

 it's n times the full adder delay。Because that carry has to ripple through each of those flats。

And so。This is pretty slow and this is one of the disadvantages of the ripple carrietter。

But it's pretty simple， too。 So if we're looking for something that's cheap and speed isn't an issue。

 not a bad option。One thing I also want to mention here is that。We write， you know。

 unlike other circuits， we're actually writing it with the flow going from right to left， right。

 we typically have our gates with our flow going left to right。 In this case。

 the flow is going right to left and we do that because we want to keep our digits。With our。

 you know， least， how we write it， our least significant bid is here。

Our LSB is here and our most significant bit is on the left as we expect with our numbers right if we have some number like the example we have。

 we put our MSB on the left and our LSB released least significant bit on the right。

And so we draw our adders flowing from right to left。So again， the delay of our ripary adder is。

 well， n times the full adder delay where TFA is the delay of a one adder。



![](img/c937f88317660a99861968153b9e6201_2.png)