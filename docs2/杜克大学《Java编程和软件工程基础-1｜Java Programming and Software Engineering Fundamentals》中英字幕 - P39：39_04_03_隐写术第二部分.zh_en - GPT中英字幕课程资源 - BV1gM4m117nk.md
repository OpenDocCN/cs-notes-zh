# 杜克大学《Java编程和软件工程基础-1｜Java Programming and Software Engineering Fundamentals》中英字幕 - P39：39_04_03_隐写术第二部分.zh_en - GPT中英字幕课程资源 - BV1gM4m117nk

![](img/2c9b16fe0c82e3caa9e66cda0609acc1_0.png)

Now that you have the basic idea of steganography， it's time to learn a bit about binary so you can do the math on the numeric values of pixels。

 Let's start with a refresher on base 10 numbers。 the normal decimal system you use every day。

In a base 10 number， the digits are in the one's place， the1's place， the hundreds place and so on。

 This means that a number like 8237 is 7 times 1 plus three times 10 plus。

Two times 100 plus eight times1000。The same principles apply in binary。

 but the places are powers of two instead of powers of 10。

Computers do this because they fundamentally work with electric circuits and transistors。

 which are easiest to implement with two voltage levels。

So computers work naturally in a number system where you have only two values， ones， and zeros。

So the binary number， 10，1，1，1 is1 times 1 plus。One times2 plus。

One times 4 plus0 times 8 plus1 times 16， which if you wrote in decimal， would be 23。The red。

 green and blue components of pixels range from 0 to 255 because they are stored with 8 binary digits called bits。

 Note that the B in bit comes from binary and the it in bit comes from digit with 8 digits or 8 bits。

 a number can range from。0，0，0，0。0，0，0，0。Which is the decimal number 0 to 1，1，1，1。1，1，1，1。

 which is decimal 255。 These8 bits are in the one's place， the two's place。

 and so on up through the 128 place。 If you were to add up all of these place values。

 you would get 255。Now that you know that each color is an8 bit binary number。

 let's revisit the stganography problem。 You want to hide the8 bit number on the left。1011。0，0，1。

0 in the number on the right，0，1，1，1，0，1，0，1。As before you'll hide the most significant digits in this case。

 you use the four digits from each number， since that's half of the total digits。

The resulting number would be this8 bit binary number where we've colored the bits based on which of the two original numbers they came from。

The most significant bits from the number you want to hide。

 shown in blue are now hidden as the least significant bits of the color that will be displayed。

That's how you do it conceptually， but how do you pull these numbers apart？

And then put them back together using mathematical operations that you can write down in code。

Let's again revisit the problem in the more familiar context of decimal numbers。

 working similar problems in more familiar contexts can be a great strategy in general。

 whenever you're approaching problems that have unfamiliar concepts。

The first question we might ask is how do you extract or get 82 the blue digits out of 8，274。

 the number on the left where the 82 is underlined in blue？You could take 8274 and divide by 100。

That would give you 82。74， and then throw away the 074。

 The mathematical operation called taking the floor of a number。

 which means rounding it down to the whole number less than or equal to it。In JavaScript。

 you would do this with Ma dot floor 8274 divided by 100， and that would give you 82。

The same principle works to get the most significant two digits of 3，568。

Math do floor of 3568 divided by 100 is 35。In fact。

 you can get rid of the least significant digits of any base 10 number by dividing by the appropriate power of 10 and discarding the fractional part。

Now that you have 82 and 35， you want to put them together to get 3582。

 which you can do simply by multiplying 35 by 100 and adding 82， in fact。

This strategy works to combine any two digit numbers into a four digit number。

If you wanted to combine numbers with more or fewer digits。

 you would multiply by a different power of 10。Now let's go back to the numbers represented in binary。

 you can apply the same principle， but now you'll need to use powers of  two instead of powers of 10。

And since we want to work with four digits at a time， we'll use two to the fourth， which is 16。

So if you took math dot floor of 1011-0010 divided by 16， you would get 1011。

Note that there's nothing really special about binary math， binary numbers are still just numbers。

 in fact， this really is 178 divided by 16， which is equal to 11。

We just wrote the numbers down in binary rather than decimal。Similarly。

 to get the most significant four bits of the other number。

 you can divide by 16 and take math up floor of the result。In this case， you're taking 117。

 dividing by 16 to get7。Now you can combine the two different four bit numbers into one8 bit number with the same principle we saw before with base 10。

 but this time， instead of multiplying by 100， you multiply by 16 and then add。

That's the math required to hide one image in another。

But what about the math to extract the hidden image？

How do you get the least significant four digits out of the number on the right。

 shown in blue to make them into the most significant four digits of the number on the left？

Let's again go back to the more familiar based 10 scenario when you take 3，5，82 and divide by 100。

You get 35 with a remainder of 82， that 82。The remainder when you divide is exactly what you want。

So how do you ask JavaScript to give you the remainder that's left over when you use a vision？

You'll use the percent sign operator shown here。3582% sign 100 is 82。

The percent sign operator is called modD， short for modulus。

 the formal mathematical name for the remainder when you divide。

So we' would actually read this statement as 3582， mod 100 is 82。Once you have these two digits。

 you can just multiply by 100 to get the number you want。

 making them the two most significant digits of the resulting four digit number。

The same principle will work for binary digits， but again。

 you use powers of two instead of powers of 10。Since you want four digits。

 you would use two to the fourth， which is 16。Instead of 100。

Taking a number mod 16 gives you the four least significant or right most bits， the binary digits。

 in this case， 1011。If you take that number and multiply by 16。

 you end up with these bits as the foremost most significant bits of an eight bit number。

You see that the leftmost or most significant bits are now 1011。

That's exactly the math you need to extract a hidden image。

So now you've seen how numbers are represented in binary and how you can extract the digits you want from numbers in base 10。

Or in base two， using either division or mod。You've seen how you can combine these digits back together in either base。

 using multiplication and addition。And you've seen that you can use Math dot floor to discard the fractional parts after you've divided。

We've summarized these ideas on this slide。Remember， think about numbers in base 10。

But do the math in base two by using powers of two instead of powers of 10。Enjoy your programming。

