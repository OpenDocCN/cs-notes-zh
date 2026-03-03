# 哈维穆德学院《数字设计和计算机架构RISC版｜Digital Design and Computer Architecture： RISC-V Edition》 - P64：Chapter 5 11.Floating-Point Addition.zh_en - GPT中英字幕课程资源 - BV1JC1MY1E7F

![](img/e0e34397040069a79324b52c7649e00d_0.png)

So how do we add floating point numbers， This is actually a lot harder process than adding to complement or unsigned binary numbers。

 So we actually have to extract the fields basically you know。😊，Put the number back together。

Pform the operation and then you know， break it back up into the field into its field。

 So here are the steps， extract the exponent in fraction bits， prepen the leading one。

 compareare the exponents if they're the same。 we don't do anything。

 but if they're different we we're going to shift the smaller mentia。😊。

To the right and then we're going to add the manticss。

 normalize the manta we could get something where we get a 10 dot 10 point， blah， blah， blah。

 so we have to shift it again and adjust the exponent and finally might have to round the result if we ended up with too many too many bits of precision and then assemble it back into the floating point format。

So let's show an example of this。So let's add the following floating point numbers。

So the first step is to extract the the fields， the exponent infraction bits， so we're going to have。

thre。F。See。Zero and then a bunch of zeros。And。For。0。5ve。0。And a bunch of zeros。

And we're going to break up into the field。 So we have our。Sign bit。There's a signed bit。We have our。

I have to be careful here because it goes across our he digits。We have our exponent。

 our biased exponent field。And then we have the rest， which is our fraction。Y。

And so the first number is， well， the sign， we're doing this for positive numbers。

They are a assigned bit of zero， so they're both positive exponent is。

For the top number is 127 and the bottom number is 128。And our fraction bits are。1。

For this top number，1 bunch of zeros， and this one is 0。101。Okay。

 so we've extracted our fraction and exponent bits and now we're going to prepen the leading one right it's implicit。

 but it's not unimportant right so we still need to it's in fact the most significant bit so we prepen that leading one to form the entire mentisa。

😊，And now we're going to compare the exponentence， so one of the numbers had exponent of 127。

 the other one of 128。😊，So we need to shift。If go go back to。Our numbers， we had 1。1。

Times2 to the 127。And 1。101 times 2。😔，Qu。😔，The 128。And so。

Well which one are we going to shift if you have to shift something。

 this is the smaller number right N1 this number we call this N1 and this one N2 N1 is smaller right it has a smaller exponent and so we're going to shift that to the right by one bit so that we can make their exponents equal。

And so we're going to shift N1 to the right。get point。😔，1，1。Times2。So the 128。This is N1。

 and we still have N2 here。And so now we're going to add those mantices。And we can in this case。

 it looks like we shifted it back down to or it took a way to the bias。

 but we don't necessarily have to， we could just leave that as 128。They're relatively the same。

And we're going to add these menisees so they have the same exponent we can add them and we're going to get。

1。1 plus0 is one，1 plus1 is0。 carry the one， we get1 plus0 plus1 is0， carry the one。

 and we get a one。And so get 10。011 times2 to the one， or if we just leave it as bias。hich we can。

Of 1，2 to the 128。 unless we want to actually know the number。

 if we're trying to like print out the number at that point。

 we need to take the bias off or we get some huge number when we were expecting something with the power of one。

Okay， so we added those manticsas and now we're going to normalize it。

 so we need to have our our binary point to the right of the most significant one and so I'm going to go ahead and leave this as 128。

128。系。Result it's not 128， but Ill believe that 128 and see what happens here。We have 128。

And we're going to float that binary point to the left。By one bit， we're going to get 1。0011 times 2。

To the now 129。Or unbiased two to the two。And we don't need to round the result。

 clearly this fraction fits more than fits in 23 bits。

And now we're going to assemble it back into the floating point format that we have we left it as biased the entire time。

 we already had that 129， if not we had 127 to our unbiased exponent。And again。129 is 128 plus one。

And we take out our fraction bits。Where we extract those fraction bits and put those into the fraction field。

 so our sign bit is0， our exponent is 129。And our fraction is 0011。And then a bunch of zeros。

And then we can write this in ofadeimal as well。We're going to get it。We're going to get four， hex 4。

0。9ine。8。0，0，0，0。And so addition， as we can see， floatingloing Point editionition actually took a lot more effort than unsigned binary or twose complement edition。



![](img/e0e34397040069a79324b52c7649e00d_2.png)