# 密歇根大学《给所有人的C语言编程课（了解C、用C编程、数据结构、创建对象）｜C Programming for Everybody》 p10 2_01_04_第2章类型运算符与表达式的历史背景-第2部分.zh_en -BV1v2421P7pt_p10-

![](img/2b9f2ec255bcf2a4705e926465854daa_0.png)

So another thing they talk about a lot and it has to do with as we start thinking about storage allocation on a bit by bit basis。

 we tend to need to know how to represent and print things out。

 not just in base 10 and it really has to do with the fact that base 8 and base 16 are better at printing out binary data。

 raw data， 10 is the number like where you know how many pizzas do you want。

 I want 16 pizzas or 22 pizzas， it's our natural the way we think way humans think。

So talk about to talk about bases， let's start by just reviewing what base 10 means there is。

 you know， the one's place in the ten's place。 And of course， later， there's hundreds and thousands。

 but。

![](img/2b9f2ec255bcf2a4705e926465854daa_2.png)

The the4 in 42 represents 4，1， so you can think of it as 4 times 10， which is 40。

 and then that one's place is two more。 So 42 is 40 plus 2， which is kind of redundant。

 We do that instinctively。So now let's take a look at base 8。So。42 in base 10 is 52 in base 8。

 And what base 8 is really doing is it means that the digits in the two places mean something different。

 meaning the 5 and 52 represents an 8。So there's five8s in this number that we're dealing with and two1s。

 and so  five times 8 is 40 and two times1 is 2。And so converting from 52 base 8 to 52 base 10。

 we get to 42。And we used base 8， and again， base8 lines up perfectly with base  two because three base two digits equals one base 8 digit。

And。I did a lot of base 8 in the early days of but base 16 is really the way we tend to do it now because it's a little more dense。

 The rightmost place is still the ones。 And the next place is the 16s。

 So the two in the 16's place represents two times 16 or 32。And then what's left over is 10。

 which we represent with an a and 10 plus 32 is 42。 Now， the problem is。

 is we only have digits 0 through 9。 So by convention。10 is a， 11 is B， 12 is C，13 is D。

14 is E and 15 is F。F is all the ones。 It's four ones。 I know that I just like four ones。

 so I can convert hex from hex to base2， like very， very quickly。

 and if I need to look at some a dump of some memory， I can dump it in Hex。

 and then I when I need to， I can convert it to base2。

So just converting back and forth between base 16 and base two is a bit of a trick。

And I don't really care if you do much of this。 you can grab this sample code and play with it。

 This is a conversion from base 10 a base number like 1，2，3，4 to base 8， and then base 16。

And the way this one does it is it converts the number in effect from left the rightmost number。

Up to low the low digit， up to the high digit。And so what you do is you use the modular function。

And so you take your number one， two， three， four， and you take it modo8。

And what's leftover's remainder is two。 So that's the far right number in the new one。

 And then you chop it off with integer division。You chop that off and see what's left and that's 154。

And you're accumulating the two in the converted number。 and then you take the modular of 154 modo 8。

 and you get2， and then you chop off the next8 with divide by integer divide by 4 and you get 19。

 So now you either bottom 2 digits or 2，2。 And then you do 19 modular 8 and you get 3。

 And that next digit from the right is a 3。 Then you divide by 8 integer divide by 8 to get what's left over。

 And that's below 8。 And so that the fourth digit from the right is a 2。 So 1，2，34 in base 8 is 2，3。

2，2。And you can do the exact same thing。 the difference is you got to look up the digits because。

🎼The base 16 needs the ABC， D E F。 And so I make a little string。 Now go we're talking Python here。

 And so we do we do repeatedly modo 16 integer divide by 16 modo 16 integer divide by 16。

 modular 16 integer divide by 16。 And so we take 1，2，3，4。 And when we convert it to base 16。

 It's kind of comes up from the bottom is 2 D4， which we read 4D2。

 So that's just an algorithm that converts these。 You tend to you tend to use this modo。

 And that's how we can convert from one base to another。 Now it's not critical in this class。

 We're not going to spend a lot of time converting bases。

 But we just need to be aware that because there was so much。



![](img/2b9f2ec255bcf2a4705e926465854daa_4.png)

🎼Awareness of how bits were stored， we tended to print a lot of stuff out in hexadeciimmal or in base 8。

 And so I just want you to know what those things are。 So if you look， for example。

 at the ASI chart that we've already seen， you see that it shows us that the letter A is 65 and in Hex it's 41 and in octal。

 it's 101 and in base 2 or binary， it's one in a bunch of zeros and a1。



![](img/2b9f2ec255bcf2a4705e926465854daa_6.png)

And so this this is just something that's making you know。

 in the old days you had to be just much more aware of the real bits inside the computer and Hex and base 8。

 Hex and Oal were better ways to sort of know what the bits were， you know， so there you go。🎼So。



![](img/2b9f2ec255bcf2a4705e926465854daa_8.png)

🎼Yeah。

![](img/2b9f2ec255bcf2a4705e926465854daa_10.png)

🎼Yeah。