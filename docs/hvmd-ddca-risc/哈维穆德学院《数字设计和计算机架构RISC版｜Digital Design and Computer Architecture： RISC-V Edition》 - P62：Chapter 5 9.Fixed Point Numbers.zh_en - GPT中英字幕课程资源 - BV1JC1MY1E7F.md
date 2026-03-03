# 哈维穆德学院《数字设计和计算机架构RISC版｜Digital Design and Computer Architecture： RISC-V Edition》 - P62：Chapter 5 9.Fixed Point Numbers.zh_en - GPT中英字幕课程资源 - BV1JC1MY1E7F

![](img/32cc255a8057be2fe3ff3ba7e437b01b_0.png)

So we've talked about various number systems， unsigned binary numbers to represent positive numbers。

 numbers that are positive only。And weve talked about negative numbers。

 s magnitude and two complement numbers， what about fractions。

How do we represent fractions using bits？Let's talk about that now。

So the two most common notations for representing fractions are fixed point notation where the binary point is fixed and floating point notation where the binary point floats to the right of the most significant one so let's talk about both of those representations。

So fixed point numbers use a fixed number of bits for the integer and a fixed number of bits for the fraction。

 So in this example， we have four integer bits and four fraction bits so。Just like。

And where either unsigned binary。Would have the two to the zeros place。

 the two to the one's place to the two and two， the three's place。So the one，2，4， and8 place。

 And now we're going to have the bits for the fraction。So。To to the minus one's place in decimal。

 that would be right the。The value after after the binary point would be the10th。

 the minus ones place。10 to the minus twos place or the10 place， the hundredth place， et cetera。

 So similar。Pattern here， we're going to have for our base two numbers。

So we have two to the minus one's place， and then we have the two to the minus two's place。

 two to the minus threes place and two to the minus fours place。And so this is the。Onehal。One。

 fourth。1，8。And116th place。And so here we have in this case， so the binary point is implied， right。

 we have to decide how many bits are for integers and how many for fractions。

So it doesnt you know we don't encode that。But we'll put it in here just so it's easy for everyone to see。

But here we have the。well， we have a one in the。To the one's place。

The two place and and a one in the do the two place or the fourth place， so we have。4 plus a two。

 and then we have a one in the two to the minus ones place。So plus a half。Plus。A fourth。

And so we have 6。75。And again， the binary point is implied。

We have to agree on the number of integer infraction bits。

So unsigned fixed point formats are listed as U A do B where a is the number of integer bits and B is the number of fraction bits so an example 6。

75 when we had we represented it as U4。4， which is what we had before on the prior slide。

Has four integer bits。And four fraction bits。 Or we could write this as U 3。5。

It fits a knot or a use6 point。6。 2。And so common。Common formats are 8。

16 and 32 bit fixed point numbers， for example， U。8。8 often represents sensor data data， audio。

And pixels use 16。16 is used for higher precision signal processing。

Theigned fixed point formats are listed as Q A dot B。

 so signed tos complement number Q A do B would be 8 integer bits。

 including signed bit and B fraction bits。 So to negate a Q fixed point number。

 we invert the bits and add one to the least significant bit。

 and this is the least significant bit of the。Of the entire number， people。

 the common narrow is to put it to add it to the least significant bit of the fraction portion。

 And that wouldn't be correct。 So， for example， if we want to represent -6。75 and Q 4 do4。

We would write 6。75， which we did in one of the prior slides， invert the bits。And then add one。

So this is now the Q4。4 representation of minus 6。75。Q1。

15 also called just simply Q15 is common for signal processing and it ranges from one to minus1。

 so one。And then all zeros。All zeros would be would be minus one and then。

Very close to one would be zero。And all ones。And then remaining in 15 bits。So one thing about ametic。

 especially as we know about overflow， when we have a video or we have audio that we're listening to and overflow occurs where a number turns from you know some large positive number and all of a sudden it turns negative。

 we hear that right it's a crackle or know a dark pixels in video。

And so that's that's a problem right， would rather have it be approximate and still large than you flip over and overflowing and look like it's a negative number。

 And so often we'll use what's called saturating arithmetic where instead of overflowing。

 it just saturates to the highest value。 So for example， U 4。 412 plus 7。

5 instead of though here we have。😊，This number。And 7。57。Point5。And if we add these together。

We would get。Overflow here。And so the result we would get would get some large number。

 plus another number， and we end up with something smaller than both of them。

And so we got overflow here， and instead of that happening， it would just saturate。

To the largest value。

![](img/32cc255a8057be2fe3ff3ba7e437b01b_2.png)