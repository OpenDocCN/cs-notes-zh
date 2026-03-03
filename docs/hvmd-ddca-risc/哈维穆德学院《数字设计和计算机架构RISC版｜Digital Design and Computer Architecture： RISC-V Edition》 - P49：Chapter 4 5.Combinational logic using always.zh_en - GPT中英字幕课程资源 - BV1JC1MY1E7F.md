# 哈维穆德学院《数字设计和计算机架构RISC版｜Digital Design and Computer Architecture： RISC-V Edition》 - P49：Chapter 4 5.Combinational logic using always.zh_en - GPT中英字幕课程资源 - BV1JC1MY1E7F

So now let's talk about how to use an always block to describe combinational logic。



![](img/a556e5eae02a4d978b32965a13140d88_1.png)

So there are certain statements that have to be inside of an always statement or an always block if else statements。

And case statements and a second kind of case statement called a case Z that includes don't cares。

So let's take a look at those。So here is a combinational logic block。

But it's using this always statement。Instead of always underscore FF。

 we use always underscore comm to indicate that this should be combinational logic。

And so here we have our inputs and outputs there。Four bit buses and our outputs are also four bit buses and we could always underscore comm begin notice there's no assign y1 equals A and B。

 it's just y1 equals A and B。And so forth。For all of the other outputs， y2 through y5。

And you'll notice that this is almost exactly the same as our prior module that we had。

 but instead of using the always block。We just use assign statements， so assign。Y1 equals blah， blah。

 blah， all of those are assigned sign statements a s y2 equals assign y3 equals and so forth。

And so in this case， it would be better to actually use assign statements because it's fewer lines of code and there's no need to use the always block。

But this to show you。How you could。Yous can always block and always underscore comm。

Statement to indicate that you are producing combinational logic inside the Always block。

So here we have a seven segment display decoder， which is a combinational circuit that is described using an always block。

 so always underscore comm， and then we have this case statement within our combinational our always block and so remember case statements have to be inside of an always block。

And so we'll notice this is a seven segment display coder， so remember our segments。

Are numbered like this， A， B， C， D， E， F。And G is the middle bar。And so for displaying the value0。

 so if data is0， and we're going to get A， BC， D， E。

 and F lit up and G will be zero will not be lit up that。The segment in the middle。Likewise。

 if we have a one， well， we just want the B and C segments to be lit up。

So here we have B and C being lit up and so forth。And so this is a base 10 seven segment display decoder。

 so displays  zero through nine if it gets any other number like 10 through 15。

Then or in other words， A through F， then it just doesn't light up any of the segments。

Makes them zero。And this statement， this default statement is required。

Because for combinational logic， we need to know deterministically what the output should be for every possible input combination。

 so we need to specify。The output value for every possible input combination in order for it to be combinational。

And using a case statement is similar to a truth table， so if we had data。

 here was our data input three to zero， and we have our segments。Or seven segments。

6ix to0 as the output。So when data is all zeros。So this row here。

 data is all zero is going our segments to be 111，1110。If on the next line we have。Data of 0，0，0，1。

Now we want our segments to be。0，1，1，0，0，0，0， and so forth。

So instead of going from our truth table to equations and then specifying the equations。

 you can actually go directly from the truth table to。Are HDL using a case statement。

 remember case statements have to be inside of an always block。So don't forget。

This default statement， if you don't include that， the synthesizer will say， oh。

 I'm not sure what to do in that case， so I'll put a latchin and keep what you had before。

And so it actually may simulate correctly， but then when you go to build it in hardware。

 nothing works and you wonder why， so make sure you always include a default statement in your case statements。

And。And here we have another example of a case statement。 but this is called a case Z。

 So this is the priority circuit that we've talked about in in prior videos。

 And so we have these question marks， these question marks。Right there。

 those question marks are don't cares。So it means that we don't care what the other inputs are。

 so here we have our input A and when a sub3 that most significant bit of a is high。

 it says I don't care what the other bits are because when that's true。

 I'm going to give priority to that most significant requester or a sub three。Will cause Y of 32 be1。

Likewise， if ACI 3 didn't request it。But AC sub2， that AC sub 2 input did request or was high and doesn't matter what a sub 1 and zero are。

 those are don't cares， that question mark means don't care。And then a sub 2 gets it by same y sub2。

Is， is one。And so forth。And again， this case C statement， so in a caseC statement。

 we can include these don't cares on the inputs。And the default make sure to include is just like in the case statement。

 make sure to include the default， for example， in this case。

 if we didn't the combination of a being00，0，0。Would not be covered。



![](img/a556e5eae02a4d978b32965a13140d88_3.png)