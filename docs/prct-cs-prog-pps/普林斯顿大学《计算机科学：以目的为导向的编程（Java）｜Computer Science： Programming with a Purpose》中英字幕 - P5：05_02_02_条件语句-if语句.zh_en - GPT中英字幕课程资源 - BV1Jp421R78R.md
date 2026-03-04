# 普林斯顿大学《计算机科学：以目的为导向的编程（Java）｜Computer Science： Programming with a Purpose》中英字幕 - P5：05_02_02_条件语句-if语句.zh_en - GPT中英字幕课程资源 - BV1Jp421R78R

![](img/64fdd4119de330c71b3f087d4d9ea055_0.png)

Not that you know how to use basic data types and basic operations on those types。

 we're going to look today at conditionals and loops。

 which are going to provide a way to do computations that you couldn't contemplate doing without a computer。

First， we're going to talk about conditionals or the if statement。In general。

 we're talking about adding some more building blocks to your basic programming skills last time we talked about primitive data types and math and text I and assignment statements。

 that's pretty much what you get with a calculator with conditionals and loops really we go to infinity and beyond as you'll see。

All right， so the idea of conditionals and loops is that it has to do with control flow in the computer。

It's the sequence of statements that are actually executed in a program With conditionals and loops。

 we can choreograph the control flow。Before the previous lecture we had what's called a straight line control flow where we just execute one statement after the other。

 all our programs were of that form。With conditionals and loops。

 we can have a much more complicated control flow that enables us to do a much。

 much richer set of calculations， and this is the kind of thing that we're going to look at next。

So the simplest statement to talk about is called the if statement。

 and that's where we execute certain statements， depending on the values of certain variables。

 we evaluate an expression， and if it's true， we execute a statement。

 So here's a very simple example of an if statement。 if x less than0， x equals minus x。

This replaces x with the absolute value of x， it tests the boolean expression x less than0。

 and if it's true， then it sets x to minus x， and if it's false it leaves x alone。

 either way the result is that x has the absolute value of x。

You can also have an else option to execute some different statement if the Boolean expression is false。

 so for example， this if statement with the L option computes the maximum of x and y if x is greater than y。

 max equals x， that's the bigger one， else， if that condition is false。

 max equals y and y is the bigger one， computes the maximum of x and y。That's the if statement。

Here's an example of an if statement in a full program to simulate a coin flip。

All we do is generate a random double value using math。random， and if the result is less than a half。

 we print out heads， otherwise we print out tails。So each time we run this。

 we might get a different result， in this case， heads， heads， tails， heads。

very simple use of an if statement。So just here's another one。

 what does this program do Let's think about it。's well it's called two sorts。

 so that kind of tells the answer。 What it does is it reads two integers from the command line and then prints them out in numerical order。

 Let's look at each statement。A is read from the first command line argument， B from the second。

 then the if statement says if B is less than a， there's curly braces so that means you can put a bunch of statements inside an option for an if statement or an else alternative。

It can be a sequence of statements and this sequence of statements is one of the first ones we examined when we talked about the assignment statement that exchanges A and B。

 but A into T， B into A and T back into B， and then once that's done if B was less than a we exchange them now a is less than B。

 if A was less than B we didn't do anything in either case。

 A is less than B at the end and we print them out in numerical order。So after seeing that one。

 you might think for a while about how you would put three numbers， integers， A， B。

 and C in numerical order。So that whatever order they get typed in the command line。

 they come out in numerical order。And this is a little program with three if statements that achieve this goal。

 the first one does just but before it makes A smaller than B。The second one makes A smaller than C。

 and it's already smaller than B， so it's smaller than both of them。

And then the third one makes B smaller than C。 So A smaller than both of them， B smaller than C。

 Then they're going to come out in numerical order。 That's an example of the use of an if statement。

And again， any order that the organ get typed in， they come out in numerical order。

Here's an example of an if statement use in a real program and a very typical example and one of the reasons we want to talk about if statements are right away。

Our program that we wrote that computed that showed showed off the different operations on integers had the possibility of dividing by zero。

 and if division by zero happened， that program would crash。

It's much better for the programmer that's you to anticipate a condition that would make the program crash and check for it and do take some appropriate action and notify the user or whatever else in this case if B equals zero。

 we don't want to try to divide or compute the remainder so we replaced the statement that did the division or computed the remainder with an Efl if that。

Theno is going to be zero， we print out division by zero and don't do it。

 otherwise we go ahead and do it。

![](img/64fdd4119de330c71b3f087d4d9ea055_2.png)

That's a much more robust program， so this way we got before， if we do it with zero。

 we get division by zero and we maintain control of the computation。

It's a good programming practice to use conditionals to check for and avoid runtime errors。

 and that's a good example of it。So that's a quick introduction to the if statement。



![](img/64fdd4119de330c71b3f087d4d9ea055_4.png)

![](img/64fdd4119de330c71b3f087d4d9ea055_5.png)