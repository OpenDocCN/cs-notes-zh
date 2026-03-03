# 哈维穆德学院《数字设计和计算机架构RISC版｜Digital Design and Computer Architecture： RISC-V Edition》 - P59：Chapter 5 6.Subtractors & Comparators.zh_en - GPT中英字幕课程资源 - BV1JC1MY1E7F

![](img/2970270cf10b0961bb42ae0db182ef39_0.png)

So let's talk about subtractors and comparators。 Subtractors are， well， similar to adders。

 form the function A minus B。 And really， that's a。Plus， a negative B， can think of it that way。

And so how do we take a twos complement number and negate it while we flip the sign。

 we take the twos complement。 And so this minus B is really。Invert B and add one。So， we had a。Plus。

 the inversion of B plus 1， which is。Minus B。So here's our symbol， looks like an adder。

 we just replace the addition sign with a subtraction sign。And well， how do we implement it。

 use this as our guide。 We already know how to design an adder。Several types of adders。

Put a in one end。Invert B。But we still have to。Add one。 Well， our carry in。

Give us a place where we can add one。we can tie that or carry in and put high。And now。

We have a plus the universeverse of B plus 1。To produce the result。

Now let's think about comparing numbers， so one common comparison is equality。

 we want to check if two numbers are equal and here's the symbol for it we put in this case。

 a four bit equality comparator checking if A is equal to B。So we can think about， well。

 how do we do that， how do we perform that？There are actually multiple ways。 when common way is。

 well， how do how do we tell if2 B are equal， We put them through and。X， norgate。

Also called the equality gate。Right， we have a。And B。And if you remember the Xno function。

Looks like this。It's true。When the bits are equal or when an even number of bits。

Of input bids is true。And we can see that， yeah， that that this output is true when the bits are the same。

 So A and B are both0 or A and B are both both one。 And so that's how we can do it for  one B。

How can we do it for multiple bits well？Right just。Include more of these。 Now we have a bit wise。

Signal to tell us whether they're。Equal or not？And we say， okay， well， all of those have to be equal。

So we add that together and then we get already。Equality comparator。And obviously。

 we can extend this to multiple bits。Or additional bits as well。

We may also want to perform sign comparison。In this case， we're going to test for a less than B。

So how do we do that， Actually， we show the circuit here。 Let's think about it。 Well。

 if a is less than B， let's just do some examples A And B， A is less than B。 Let's do 5 and 7。

 for example， if we subtract that， we get。in-2， if we get a negative number。

 let's suppose a is not less than B， like A and 3。Let me get a positive number。

 Let's suppose they're exactly equal。 So5。inus5。We get positive number again， right。

 both these are positive numbers。Let's do another example two minus3。It -1。 So we get negative。

A negative answer when a is less than B。 And so we know that if a is less than B after we subtract then that sign bit。

 the n minus one bit is going to be。One， because the result going to be negative。

So we put A and B into a subtractor， and then we take that。Most significant bid， the sign bid。

And you know， take that off of the bus。 And that gives us a less than B。

That would be careful of overflow。And this。And in this comparator。



![](img/2970270cf10b0961bb42ae0db182ef39_2.png)