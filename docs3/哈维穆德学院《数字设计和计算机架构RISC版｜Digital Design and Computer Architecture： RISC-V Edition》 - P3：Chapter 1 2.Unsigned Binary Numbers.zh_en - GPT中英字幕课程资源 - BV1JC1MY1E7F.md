# 哈维穆德学院《数字设计和计算机架构RISC版｜Digital Design and Computer Architecture： RISC-V Edition》 - P3：Chapter 1 2.Unsigned Binary Numbers.zh_en - GPT中英字幕课程资源 - BV1JC1MY1E7F

Hello and welcome to the next exciting installment of digital design。😊。

The topic of this video is number systems， in particular， binary numbers。



![](img/dc2aae91d8e319341ad8a128fac56262_1.png)

So we're all accustomed to working with decimal numbers or base 10。

These are numbers where each column has 10 times the weight of the previous。So for example。

 consider the number 5，3，7，4。We'll put a subscript 10 after it to indicate that this is in base 10 or decimal。

The columns are the one's column， the tens column， the hundreds column and the thousands column。

 each column has 10 times the weight of previous。So this number is 5 in the thousandss column。

3 in the hundreds column，7 in the tens column and 4 in the ones column or 5374。In binary。

 we only have two possibilities， zero or one。So each column has twice the weight of the previous column。

Now we have a one's column， a choose column， a fours column and an eighths column。So the number 1，1。

0，1 in binary subscript 2 to remind us that it's binary。Is one。8ight。Plus1。the fourth column。Plus，0。

In the twos column。Plus， one。In the one call。Which is 8 plus 4 plus1。13。In thatment。

As you could guess， we use powers of two quite a bit in binary， and it's handy to memorize these。

 You'll use them so much。 So remember， anything to the0 power is just one。2 to the one power is 2。

2 to the two power is  two times 2， which is 4，2 to the third power is  two times 2 times 2。

 which is 8，1632，64，1，28。256，5，12， 10，24，2048。4，96。81，92，16，3，84 and 32，7，68。

Let's talk about converting numbers between binary and decimal。 So， for example。

 if we had the number 1，1， sorry，1，0，0，1，1。This is the ones column， twos， fors。8s and6。

So this is 16 plus 2 plus1。Which is 19 in decimal。We can also go the other way。

 converting from decimal to binary。 So let's say we had the number 47 in decimal。

We could start with the largest。A power of two that's smaller than our number。So that would be 32。

Then our columns would be 16，8。4，2， pen1。We need a one in the 32s column。So 47。

 takeaway 32 gives us 15。15 is less than 16， so we don't need any 16s。8 is less than 15。So we need 1。

8。Evenaving 7。4 is less than7。So we need a four。Leaving3。3 is less。2 is less than 3。So we need a two。

And that leaves one， so we need a one。So this is 32 plus 8 plus 4 plus 2 plus 1 equals 47。

 or we could readwrite it more compactly，1，0，1，1，1，1。By the。

So there are two general methods of converting from decimal to binary。

 One is the method that we just tried finding the largest power of two that fits。

 subtracting it off and repeating。Another method that's more suitable for computers often is to repeatedly divide by 2 and the remainder going in the next most significant。

So let's suppose we wanted to convert 53 to binary。Again， we have the 32，16，8。4，2， and 1。嗯。

32 is less than 53。We need one of those。Leaving 21。We need a 16。Leaving five。

So we don't need any eights。We need a four。Leaving one。 So we don't need any twos。

 and now we need a one。So 1，1，0，1，0，1。Alternatively。

 we'll divide by two and the remainder going in the most significant in the next most significant。So。

53。Divided by2。Is 26 remainder 1。So that one goes in the bottom bit。26， divided by 2。

Is 13 remainder 0。So we get a zero。13 divided by 2。I 6 remainder 1。So we need a 1，6 divided by 2。

Its three remainder 0， so we get a0。3 divided by 2。Is one remainder one。And one divided by 2。

Is 0 remainder 1。So again， we get 11，0，1，0，1。Both will work。

 I tend to use method 1 as a human that's more natural to me。Finally。

 let's think about the range of numbers that we could represent in binary。And for starters。

 let's think about this in decimal。 So suppose we had an indigit decimal number。

There are 10 to the n different numbers。In the range of 0。To10 to the end。-1。So example。

 three digit decimal number。Has 1000 different possibilities。From 0 to 999。

If we have an binary number。By analogy， there are2 to the n possible numbers in the range of 0 to 2 to the n。

So for example， a3 bit binary number。There are eight possibilities。From 0，0，0 to 1，1，1。

 or in decimal。 that's from 0 to 7。

![](img/dc2aae91d8e319341ad8a128fac56262_3.png)