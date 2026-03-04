# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p119 21_19_macros-the-key-points -BV1bw4m1D7MM_p119-

We're now going to move on to a different but slightly related topic which is macros。

 the way this is going to work is in this segment I just want to give you the high levelvel ideas of what a macro is so that in the next section when we use that idea for a few things you're familiar with the idea。

 do not need it for this section's homework unless you attempt to do the challenge problem so the way this is going to work is that after this segment I will go into the details of racks macro system some of the general pitfalls of macros using this in racket is actually a great idea because rack's macro system avoids a lot of the pitfalls and weaknesses of other macro systems。

 particularly the more well-known macros of CNC plus plus so I've decided to make all the segments after this one optional because macros are a bit of a standalone topic and we're not really going to build on them very much in the course。

 so it's sort of up to you and this is an opportunity to say。



![](img/74ab5fc30d748754b814547616928dcb_1.png)

Time and focus on other topics that fit more into the other core material in the class。



![](img/74ab5fc30d748754b814547616928dcb_3.png)

You do need to know a few things， so let's go through that。And let's start with just what is a macro。

So when you define a macro， it describes how to transform some new syntax into different syntax in the source language。

I'd basically like to think of a macro definition as adding more syntactic sugar to the language。

And if we let programmers define their own macros， then they get to extend the syntax of the language by introducing new syntactic sugar。

For example， maybe we could have something that lets you add the and also keyword to rack it in some way。

 and that that would turn into the conditional that we know and also an ML is syntactic sugar for。

A macro system is just a language you give programmers for defining macros。

And then what happens is after someone has defined a macro， then someone can use that macro。

 just like you define a function and then you use it when a macro is used， that macro is expanded。

 you take the syntax at the use and you transform it into the de sugaruged version。

 according to the rules in the macro definition。And the key thing about the way macro systems work is that expansion happens before anything else we've talked about in this class。

You take the program， the programmer wrote down， you go through and you expand all the macro uses first before you type check if you're in a aesthetically typed language。

 before you evaluate anything。 So you do macro expansion in function bodies。

 you do it in conditional branches。 it really is a prepass before you do anything else。

 and that's the idea of macros。

![](img/74ab5fc30d748754b814547616928dcb_5.png)

So in racket， just to get a little more specific so we can actually see some examples。

 if someone defines a macro M， then M just becomes a new special form。

 so after that macro definition， someone can use it by writing M and then whatever other arguments that macro needs and then due to macro expansion that will get replaced as though it's syntactic sugar。

So here's a few examples that the later optional sections will learn how to define。

 here I just want to show how you might use them。So first。

 suppose someone didn't like rackets if because。You know， they。

 they didn't understand which one was the then and this is the else。

 They could define their own macro where you write myif， then some expression。

 then other keywords then in L with E2 and E3。 So E1， E2 and E3 are expressions。

 my if then and L are all part of the syntax， and macro expression would expand that to if E1， E2 E3。

Okay， that seems somewhat useful， not too exciting。 Here's one that's also maybe not too exciting。

 You could write a macro comment out that took two pieces of syntax， two arbitrary expressions。

 And in the expansion got rid of E1。 So the idea is that we want to comment out E1。

 But we need to put something in its place。 And so that will be E2。😊，So it doesn't。

 because this is done before anything else we do， that E1 will never be evaluated。😡。

And as a final example to relate back to something we did earlier in the section。

 we could define a macro for creating promises， something of my delay that would take an expression and by putting it under a lambda in the macro expansion。

 it will make sure it does not get evaluated。 and that's something that you simply can't do if you try to define my delay as a function。

 So let's see how we might do this， I've already clicked run where I have definitions of all these things。



![](img/74ab5fc30d748754b814547616928dcb_7.png)

And I really did define them。 So， for example， I could define。 I could use the Myif macro。

 This is not something in racket。 I defined a macro that let me do this。 And， you know。

7 actually comes out to 7。And you even get an error message if you screw something up like write else in both places。

 it says bad syntax， the definition of the macro doesn't allow you to put an else in that position。

Let me show you the comment out macro if I did something like comment out， how about car of null。

 we know car of null will raise an error as soon as you try to do it。

 but because macro expansion replaces this entire thing with false。I get no error。And I just get。

False。know just to be clear， if I had actually tried to do car of null。I would get an error。

And finally， let's look at my delay a little bit。 So let's say P of my delay begin。Print high。

 And then how about we multiply 3 and 4。So if my delay were a function。

 we know that this argument to it would get evaluated right away and it would print high ones。

 That's how functions work。 But our My delay macro picks up this syntax and puts it under a lambda。

 makes a thk out of it， and so there's no printing。Now we also have our old Myfor function。

 My force is just a function it's right here。 it works exactly like we learned in an earlier segment。

 and that we can now still use on the result of my delay because that did return a promise and now we see it print out and also return the result 12 and because of how promises work and how myfor is implemented we know that that expression is only evaluated once that we did a set M Kter bang to change the result so if we force that same promise again。

 we get the 12 but we don't see printing。

![](img/74ab5fc30d748754b814547616928dcb_9.png)

![](img/74ab5fc30d748754b814547616928dcb_10.png)

So those are example uses of macros you can learn how to define in the upcoming segments。



![](img/74ab5fc30d748754b814547616928dcb_12.png)

And basically， it's like we added new keywords to our language。



![](img/74ab5fc30d748754b814547616928dcb_14.png)

I should mention that macros have a bad reputation generally in computer science and software development and frankly they often deserve it macros are often overused or they're often used in positions where functions make a lot more sense stylistically in terms of what you're trying to do and I actually do want to leave you with the message of when in doubt if you're not sure a macro is useful。

 probably you shouldn't define one and probably you shouldn't use one but if you like that version of my delay where you just got to write E and the user didn't have to write Lambda parenthesis parenthesis E。

 well then you really need a macro because no function in the world can have an argument that it does not evaluate。

So since macros can be used well， I hope that the optional segments are coming up can help people understand why macros are difficult to use well and give some guidance on doing so。



![](img/74ab5fc30d748754b814547616928dcb_16.png)

And so the optional stuff ahead is that we're going to talk about how macro systemss need some basic semantics of how they deal with parentheses and variables and things like that。

 We'll learn how to define macros， like the ones we just used in this segment。

 We'll learn that when you're defining a macro， you have to be extra careful about。

Which expressions evaluate where and how many times。

 and then we'll see the key thing that racket does better than most macro systems。

 which is that it actually has a reasonable semantics when macros define local variables or use variables that are in scope where the macro is defined。

 This is something that most languages just do what I would say wrong。

 but in some sense they're just a different semantics and they work differently。

 and I'll show you why rackcet semantics is a superior one in almost all circumstances。



![](img/74ab5fc30d748754b814547616928dcb_18.png)