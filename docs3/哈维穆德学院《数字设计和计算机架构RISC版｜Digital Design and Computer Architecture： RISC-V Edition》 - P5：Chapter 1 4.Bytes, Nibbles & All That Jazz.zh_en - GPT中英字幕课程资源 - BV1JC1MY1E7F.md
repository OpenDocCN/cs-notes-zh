# 哈维穆德学院《数字设计和计算机架构RISC版｜Digital Design and Computer Architecture： RISC-V Edition》 - P5：Chapter 1 4.Bytes, Nibbles & All That Jazz.zh_en - GPT中英字幕课程资源 - BV1JC1MY1E7F

![](img/e55b9edd26630590b012dc410a02652b_0.png)

Next in our conversation about number systems， we're going to talk about fights， nibbles。

 and all that jazz。

![](img/e55b9edd26630590b012dc410a02652b_2.png)

First we'll talk about bits， we've seen these in our binary numbers and the there's two bits in particular that we want to pay attention to the most significant bit。

 this is the bit in our binary number that represents the largest power of two and the least significant bit is the bit which represents the smallest。

Smallest the power of two。Btes and nibbles， bytes are eight bits and a way of grouping binary numbers again。

 so when we represent these as hexadecimal numbers。

 each bitete is going to be represented by two hexadecimal numbers since each hexadecimal number represents four bits and a nibble is just a less common term but is one that is used to represent four bits。

 which conveniently then can be represented as a single hexadecimal digits。

Similar to the way we talked about most significant bits and least significant bits。

 bytes also have a designation in terms of the most significant byte。

 this would be the bitete that represents the most significant part of the value and the least significant byte is going to represent the smallest chunk of the value that we're talking about。

It's also helpful to have a general sense of powers of two and what their values are in the decimal base 10。

So if we look at these two to the tenth0th power is equal to1 kilo，2 to the 20 is1 mega。

 2 to the 30 is1 giga and so on and so forth， and you can see on the left hand side the values of the powers of  two and on the right hand side the powers of 10 that those are approximately equal to so in two to the 10。

1 kilo is 10 to the third。2 to the 2，1 megas approximately 10 to the6，2 to the 30，1 giga。

 approximately 10 to the ninth， and so this will be helpful as you're talking about the size of binary numbers and you'll notice that these are commonly used。

 you've probably seen these when you're looking at file sizes on your computer that a certain file is a certain number of megabytes or gigabytes or also when you're doing a speed test on your internet connection to see how many bits。

 how fast your connection is in megabits per second。

 hopefully no longer in kilobits per second and this gives you kind of a way to estimate approximately how big those numbers are in terms of their decimal equivalent。

So if we just want to kind of get a little bit of practice with this again those values are worth committing to memory you'll use them quite a lot and they'll come in handy and you don't want to always have to look up that table so if we see the value of this 2 to the 24 you might say well how on earth am I going estimate what that value is but if you know those ones from the previous slide it's actually not too bad so here first what we can do is we can take two to the 24 and we can split this into pieces that we recognize so first we can say2 to the 24 is equivalent to2 to the fourth power times two to the 20th power。

We know two to the fourth is equal to 16。And we know from the previous slide that2 to the 20 is approximately equal to。

 so we should change this value to approximately 10 to the6。

 and so this is going to be approximately equal to 16 times 10 to the 6 or 16 million。Similarly。

 if we wanted to know how large of the value we can represent with a 32 bit integer。

 we're going to do the same thing， so we know a 32 bit integer number can represent a value as big as 2 to the 32nd power。

Using a similar strategy is what we did above， we can split this into two square times。

Two to the 30th power。Which is approximately equal to two squared is4 times2 to the 30 we know from our previous slide is approximately 10 to the nine。

And so this is going to be approximately four。辩务人。So again， knowing these values。

It allows you to very quickly estimate and get a sense of how big a certain number is。

 and this is always really useful as a rule of thumb when you're trying to figure things out。



![](img/e55b9edd26630590b012dc410a02652b_4.png)