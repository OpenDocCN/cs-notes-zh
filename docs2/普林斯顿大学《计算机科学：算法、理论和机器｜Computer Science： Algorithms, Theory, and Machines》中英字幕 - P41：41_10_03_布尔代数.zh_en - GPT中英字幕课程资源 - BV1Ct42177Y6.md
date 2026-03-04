# 普林斯顿大学《计算机科学：算法、理论和机器｜Computer Science： Algorithms, Theory, and Machines》中英字幕 - P41：41_10_03_布尔代数.zh_en - GPT中英字幕课程资源 - BV1Ct42177Y6

![](img/5d42c68cd3c4afa36eb2b2aeac3cf0ad_0.png)

To help us， we're going to use a little bit of math。

 mathematical formalism called Boolean algebra that's going to help us understand the behavior of our circuits。

Bolean algebra was developed by George Bull in the 1840s to study logic problems。

I was interested in working with a formal system that could help understand statements that are true or false。

 So we wanted to have the idea of variables that represent true or false。

 and we're going to interpret them as one or0， of course。

 And then there's basic operations that are involved in such statements like and or a not。

 And those are very familiar with us。And ever since it was developed。

 Boolean algebra has been widely used in mathematics logic and computer science for many， many。

 many applications， In fact， it's so widely used that there's several different notations in common use。

 so we've already seen Java notation for a Boolean variables and we have the idea of a boolean variable in Java。

In mathematical logic， they use a different location notation involving V's and upside down Vs。

 and in circuit design we use yet another one that we're going to use in this lecture where the and operation is like multiply with Boolean variables in the orR operation is like some and we say not we say x prime。

 so that's the one notation that we're going to use in this lecture。

And then within this algebraic system that we can prove and manipulate these things as algebraic formulas。

 just bearing in mind the simpler rules that we have for boolean variables and boolean formulas。

 then you have for traditional algebra that were the variables are numbers， and so for example。

 this is de Morgangan's laws which we we're going to prove in just a minute。Now。

 the relevance to circuits is that this is really going to be the basis for us to build up circuits that are a little bit more than switches that we can understand what they're doing。

And of course， there standard bo cartoon is that well he had to express everything in terms of yes and no。

 and while we've seen plenty of examples of that earlier in this course。

So one thing that is an important part of the Boolean algebra formalism is the idea of a function。

 so what's a function， a function is the thing that takes arguments and that has a value and for Boolean functions we can use something called a truth table to systematically describe or define a boolean function。

And what we do is we keep one row for each possible set of argument of the values of the arguments。

 and then each one of those rows is going to give the function value for the specified arguments。

So if you have n inputs， each of the variables can take one of two values。

 so there's going to have to be2 to the n rows。So， for example， for not， there's just one input。

 so there's two rows。 If x is0， x prime is 1， if x is1， x prime is 0。And again。

 we've seen these functions before in other applications for and it's the X Y， which is x and y is1。

 if they're both one， otherwise it's zero， and or is zero， if they're both zero， otherwise it's1。

So those tables， which take two。Those are functions that take two arguments。

 We're giving all possible values of the arguments。

 either they're both 0 or x is 0 y is 1 or x is 1 y0， or they're both 1。

 And then on the right side of the line is the definition of what the function is for that row of the arguments。

 So it's giving us a complete definition of the function。

Here's another one called nor or not or that one is one if they're both zero。Otherwise， it's 0。

And Xor， which we saw back in our cryptography example， it's zero， if they're the same， it's one。

 if they're different。So this is a completely a well-specified way to define Boolean functions。

 and it's interesting to one of the big applications of truth tables is they're giving us they're working with every possibility so with truth tables。

 we can establish identities in Boolean logic just by writing down one row for each possibility and then checking what happens with each of the possibilities and with truth tables。

 we're sure that we've checked everything。 So for example here's the proofs of D Morgan's laws using truth tables。

 so if we have X and y that's again all possibility of x and Y and that's x and y so if we take the nod of that that's x and y。

 not x and Y then1110 is the value that's the value of that function definition of that function。

So all possibilities of x and Y。Now if we， on the other hand。

 if we take not x and not y and we look at the or of those。

 then that's going to be0 if they're both01 other y。

 so there's all possibilities that gives us the value of the function not x or not y。

 and now you see that those columns are the same， their' full specifications of the function。

 so that's a proof of de Morgan's law of not x and y is equal to not x or not y。

 and similarly we can do for the complementary version of it that says not x or y is equal to not x and not y。

And we did an example like this also in our cryptography application。

 it's a fine way to establish truths of identities for bullolean functions。By the way。

 these function that is， thats the nor function on the right。

 that's one effects somewhere both 0 and0 otherwise。

 and we'll see that one come up again when we look at circuits。Now。

 it's interesting to think about how many different boolean functions are there of two variables。

Well， there's four bits in the truth table column and they can each have either value zero or1。

 so that's two to the fourth， there's 16 different possibilities。

And actually we can just enumerate all boolean functions of two variables。So that's x and y。

 and then we just start out all0， 0，01，0010， and we've looked at some of these actually all have names。

And the last one is called one。So we have zero and 1， and we have a hand an X or or or and so forth。

 so 16 different possibilities。But that's interesting but let's think about three variables Well for three variables there's eight different possibilities of the three different variables。

 so then there's eight bits to define the Boolean function so that means there's two to the8 different boolean functions of three variables which is 256 so we're not going to look at all of those but there's some that are interesting so for example and is a multiway n and that just generalizes our definition of n it's going to be0 if any of the inputs are zero it's one if all the inputs are one。

And or again， generalizes it's one if any input is1， it's0， if all inputs are 0。

 nor is the knot of the or， and that's one if they're all zero，0 otherwise。

And there's lots of different boolean functions of three variables。

 So here's one called the majority function。 So that one is one if and only if more inputs are1 than0。

 so that is if a majority the arguments are one in the case of three that would be there have to be two of them are1 or all three are1 and those are the four1s in the column labeled majority01。

1 there's21s y and z101， there's two1s， x and z1，1，0。

 x and y are 1 and 111 they're all one those are the rows for which the majority function is1 and that's the definition of a boolean function that's useful as we'll see。

And here's another one odd parody， so that one's one。

 if and only if an odd number of the inputs are one。

 so either exactly one of them is one or all three is one， another differentbuo function。

And actually all of these general lies to any number of inputs and if we start thinking about more variables though it's interesting to contemplate if you have n variables you have two to the n different possibilities for the values of the variables so that means there's two to the n rows and to define the function you can give 0 or1 for every row so the total number of boolean functions of n variables is 2 to the 2 to the nth power and that's a function that grows very quickly so 16 for2 to 56 for3 already for four there's 65000 for5 there's2 to the 32nd which is4 billion and for6 already we're getting to very huge number of boolean functions。

So there's a lot of boolean functions out there and we'll never ever even encounter almost all of them。

It's a little bit of a sobering thought that we'll get back to。Okay， so。

 but one thing that's important in basic outgrowth of Bo's study is that every boolean function can be represented with only a few operations。

 we're gonna there's a number of ways to prove this。

 We're going to talk about the sum of products representation。

So the idea is to form an n term for each one in the Boolean function and then or all the terms together Now with a truth table proof。

 we can show how this works。 So the majority function we want to write down an algebraic expression that just uses and or not to express the majority function。

 So the way we're going to do it is we're going to take a look at the function。

 and for every one in the function， we're going to create an n term that's one only for that for that values for that set of values of the variables So the term x prime yz is going to be one only if x is one sorry x is0 and y and z or1 then x prime is1 and then x prime Yz is1。

 Any other value of the variables， that term x prime yz is going to be0。Similarly。

 if we look at the next one in the majority function， then we're going to develop a term x y prime z。

 again that function is one， only for the values x equals1 y equals 0。

 z equals 1 otherwise it's  zero， so we have another column corresponding to that one in the majority function。

 and then there's two more and the last one is x Y z， which is one。

 if and only if all three of them are 1。So now we have four functions that each have just one1 in them and what we can do is just or them all together。

 so oring them all together just brings those ones back and now our column is equivalent to exactly the same in every position as the majority function。

 so that's a proof that the majority function is equal to x prime Yz plus xy prime z plus xyz prime plus X。

 Yz。This idea is obviously going to work for any Boolean function。

 so there's the concept that set of operations is universal if every Boolean function can be expressed using just those operations and what this amounts to is a proof that and or not is universal。



![](img/5d42c68cd3c4afa36eb2b2aeac3cf0ad_2.png)

So with regard to circuits， it means that we can implement any boolean function as long as we can implement and or not。

 but we're getting ahead a little we'll talk about that in just a minute。



![](img/5d42c68cd3c4afa36eb2b2aeac3cf0ad_4.png)