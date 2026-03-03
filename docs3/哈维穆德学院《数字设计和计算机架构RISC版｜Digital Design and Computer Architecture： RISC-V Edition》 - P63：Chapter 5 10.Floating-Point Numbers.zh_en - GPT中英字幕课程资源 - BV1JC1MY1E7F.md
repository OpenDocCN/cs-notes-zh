# 哈维穆德学院《数字设计和计算机架构RISC版｜Digital Design and Computer Architecture： RISC-V Edition》 - P63：Chapter 5 10.Floating-Point Numbers.zh_en - GPT中英字幕课程资源 - BV1JC1MY1E7F

![](img/cf0ac62c93497bbcbb6b3d141be8e7e7_0.png)

So instead of fixed point numbers， we can use floating point numbers where the binary point floats to the right of the most significant one。

And this is similar to decimal scientific notation， so for example， some number 243。

We have our decimal point here and in scientific notation， we're going to float。

That decimal point to the right of the most significant digit。And this would become。Instead of 2。243。

Times 10 to the 0， right， This 10 to the0。 we usually don't write。

 but we float that binary point or decimal point in this case， to the left。 and we get 2。43。

And then we increase that。That power， by the number of。Of places that we move the decimal point to。

 so 2。43 times 10 to the two。And so here's another example， 273， that would be 2。

73 times 10 to the two so that's decimal scientific notation and we're going to do a similar thing with our binary floating point numbers so in general we're going to have the sign either positive or negative。

😊，The mantisa。And times the base raised to the exponent。

So M is the mentia B the base and E the exponent， so for example。Here。Misa M was 2。73。

 the base is 10。And the exponent value is 2。And so in our floating point numbers。

 our base is always going to be base too， so we don't encode that， but we do encode。The rest。

 exponent value， the mantisa and the sign。So point point numbers are like scientific notation。

 and when compared to fixed point numbers that we just talked about。

 they allow us greater dynamic range， so smallest to largest so we can get larger numbers or smaller numbers and we trade off precision for that。

 So arithmetic is harder because now we have to we have all these different fields。

 mantis has to be aligned before adding them because maybe ones you know the second power on ones to the fifth power and now we have to make those manties aligned before we add them and this costs both performance and power So it slows down that it takes a long time and it costs power。

😊，So。😊，Fix point numbers， on the other hand， they're harder for the programmer。

 We have a smaller dynamic range， and we really have to watch out for overflow。So in general。

 floating point is preferred for general purpose computing where programming time is most important the programmer's time。

And fixedixpoint is preferred for signal processing performance。

 and this is where hardware costs matter most， for example， machine learning。

 typically like smartphones in handheld systems where。Where cost and power are really important。so。😊。

We're going to encode these different fields in different bits of our format。

 so floating point numbers are 32 bit numbers that include a sign。Themana。And the exponent。

 So like that decimal example we had or some decimal example，2。43 times 10 to the two。

And maybe it's negative， we're going to encode the sign。The exponent。And。Themana at 2。43。

And we pick fields to encode these in so the sign bit is one bit and then we have eight bits for exponent and 23 bits for the mentis that will' modify this format slightly as we go along here。

😊，Let's take an example of representing some value， in this case。

 228 and use this 32 bit floating point representation。

We're actually going to show three different versions as we build up to the final version。

 which is called the IEE 754 floatinglo Point standard。So our first step in writing this number， 228。

Base 10 in floating point representation is to convert it to binary and we'll use our usual method of 228。

1，2，4，8， 16，32 64， 128， it's kind of a one in the 128 place。And then we're going to get。100。One，2，4。

8， 163264 is going to have a one in it。Get 36。So 32 has a one in it。And then we get a four。

A one in the fourth place。And so that's our first step and you know we could write this times two the zero。

 we don't usually write times one。But we will， in this case。So first thing is to convert。

The decimal number to binary。And now that we've done that。 So we kind of imply this。

 We usually don't write it， but imply that times 2 to the zero power。

 And now we're going to float that binary point。It's here， we're going to float it to the left。

Until it reaches the right of the most significant one。 So we have 1，2，3，4，5，6，7 places。

 we're going float it to the right of that most significant。1。

And we floated it to the left seven places， so we increase our exponent by seven。So that's step two。

So now we have everything we need， we have our sign， well it's implied， it's positive。

We have Ar mentia。Here's Ara。And we have our exponent。7even。

And so we're just going to put those into our fields， so our sign， we' need zero。

For positive and one for negative。So zero is our sign， our exponent is seven。 we put that in 8 bits。

 so 1，2，3，4。5，6。7，8。And so we have eight bits， the8 bit representation of seven are exponent。

 and then we just put our mantea into the remaining 23 bits。 so we have one，1， one。0，0，1。

 So here's our mansa， 1，1，1，0，0，1， and then we just fill the rest。With zeros。

And so that's our first kind of attempt at representing our this floating point number using floating point representation。

Okay， so common error is to try to go directly from 228 to scientific notation。

And you don't want to do that because then you get 228 and people do this 2。28 times 10 to the two。

 and then they're like， oh， how do I get 10 to the two to a power2 and。It's a mess， right。

 it doesn't work。 so don't don't you know， try to skip those flip one into those steps。Okay， so。

One thing we might notice on that first representation is that well， we by definition。

 we floated that binary point to the right of the most significant one。

So this is always going to be a one。And so we don't need to encode it。

RightThat's called the implicit leading one because。By definition。

 we floated that binary point to the right of the most significant one。When we do operations on it。

 we need to put it back in。Right now now it is the most significant one so it's important for us to use it。

 but in our encoding we don't have to include it so instead of encoding the entire mantia。😊。

We encode just the fraction in the 23 bit filled。 So we encode。Just the fraction bits， so 1，1，0，01。

 and then the remaining， all the lesser significant bits are zeros。Okay。

 so that's our second kind of attempt at。😊，At representing floating point numbers。

Now the last change here is we're going to instead of just representing the exponent。

 we're going to represent a biased exponent， so we're going to add basically the middle of our range 127 to our exponent。

So right， we want to represent numbers that have a positive and a negative exponent so we can have two to the minus。

 you know，12 or we have two to the。Plus， 23， right？

2 the 23 or2 the minus-12 this exponent we want to allow to have negative and positive numbers so we could have chosen several options and we could have represented that as a two complement number right the exponent。

But instead we use a biased exponent it actually makes comparisons easier with floating point numbers。

😊，And so we're going to bias all of the numbers up by 127。And so instead of storing a seven。

 the exponent， we're going to store 127 plus 7。Which is 134。One in the 128s place。Plus 6。

And one way I like to do this and like 127 is zero and all ones， so 128。Is this。

So this is 127 is like 128。Plus，6。So 128 plus。6。It's going to be this。

So just an easy way to do that in your head or。Okay， so we have 128。Plus。Or6 here。And。

Now we put that biased exponent in the in the exponent field。 So instead of seven here we have。134。

 which is 127 plus plus 7。And this is our final IEE 754 32 bit floating point representation。

 we have our signed bit。Our biased exponent biased by 127 and our fraction bits。

 so all of the mantes accept the implicit leading one。And we can represent this in hexodademal。

 grab groups of four。And we get。For。re。s。4。😔，And then all zeros。

So we can represent that group of 32 bits in a hex decimal number。So let's do another example。

 let's suppose we want to represent 58。25 in floating point and niEE 754 floating point standard well 58。

25， so 58 is12481632 64 is too big so。We're going to put a one in the 32s place。58 minus 32。

We're going to get 26， so we have 16。Plus。10。16 plus8+2。Okay。

 so there's 58 where we're going to represent that magnitude。

 we already know the sine bits going to be one to indicate that it's negative。So at 58。

 we still need to do the 0。25， well 0。25 is a fourth。So here's half。Is 0， and。

Right2 to the minus ones place。And two， the minus to place or。A half and a fourth。Okay。

 so we have our number written， the magnitude of the number written in in binary。

 and now we're going to float。That exponent， remember this is implied times 2 to the zero。

 we're going to flow it to the left。So we get to the right of the most significant one， so one， two。

 three， four， five places。We're going to get 1。1101001 times two to the number of places we floated it to the left。

So，5。And so now we have our fraction bits。We're going to go put in here。We have one，1，0。1，0，0，1。

 remember we don't encode that one if we're ever going to do。Arithmetic manipulation with it。

 we want to definitely put that back in， but we don't need to encode it。So 11，0，10，01。

 and then all zeros。The remaining bits， and now we have this exponent of five。

 we have to bias it by 127。So it's 128， 127 plus5。Equals 128 plus 4。We have 128。Plus。4。Which is 132。

Okay， so now we put those bits in here， 10，0，0，010，0。And now we have our 32 bit。

IEE 754 representation of minus 58。25。And we can now also write this in hexadeadecimal。

 grab groups of four。So divisible by the 32 is divisible by by4， so we can start out either end。

And we're going to get a C。To。six。9ine， all the rows。So hex C269-0000。

So there are some floating point special cases and one of them is actually a pretty common case。

 so the case where we have。Zero， right， we often use zero in our in our calculations。

And actually zero doesn't have a one to float， there's no implicit leading one。

So we have to choose a special encoding for that and we choose the encoding right the value zero we're going to encode as all zeros and the exponent and all zeros in the fraction and turns out we have plus and minus zero so the sign bit could be1 or zero。

😊，And then we also have values like infinity， minus infinity， and not a number， for example。

 when you divide by zero， your result will be you'll get not a number。

And so we have these special special cases， which our hardware is going to have to， you know。

 when we build these floating point units， we're going to have to know deal with these special encodings as well。

 so another thing that makes it more hardware and the performance lower。😊，So for floating point。

 we have single precision and double precision， single precision is what we just talked about with 32 bit。

32bits of encoding， one sign bit， eight exponent bits and 23 fraction bits。And the bias is， you know。

 the middle of that。That range of 127。Double double precision uses 64 bits and you'll notice right we're not increasing the range a little bit right we're instead of eight exponent bits。

 we have 11 exponent bits， but the biggest。😊，ingThe biggest change is the number of fraction bits。

We're more than doubling the fraction bits so we're increasing the precision of the number。

 so if we're trying to re measure like the roundness of an electron or something we need very high precision so we're going to use double precision floating point numbers and the bias is in the middle of the range for the 11 excellentent bits now the bias 1023。

So floating point numbers， they can also overflow， a number could be too large to be represented。

 or it could actually also underflow where the number is too small to be represented。

And we also need to round so now we have a fixed amount of precision on our fractions or on our numbers。

Right in our in our fraction bits are 23 fraction bits， and so we can choose a roundy mode。

 we can round up down towards zero or toward nearest so here's an example。

 let's suppose we can only use three fraction bits。So three fraction bits here right now we have six。

 so rounding down， we're going to just basically take off。Those bits rounding up， we're going to。

Increase。That least significant bit to one rounding towards zero。

 while it's a positive number so rounding towards zero， it's the same as rounding down。

And then rounding to nearest， it turns out that。1。625 is closer to。1。578125， then 1。

5 is right the other option would be。Would be that so turns out that 1。

65 is closer to the number that we want to represent。 And so that's called the rounding to nearest。



![](img/cf0ac62c93497bbcbb6b3d141be8e7e7_2.png)