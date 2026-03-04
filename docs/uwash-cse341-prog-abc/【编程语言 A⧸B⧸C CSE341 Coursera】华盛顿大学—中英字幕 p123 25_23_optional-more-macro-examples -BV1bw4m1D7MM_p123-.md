# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p123 25_23_optional-more-macro-examples -BV1bw4m1D7MM_p123-

I want to wrap up our study of macros by just showing you some more sophisticated examples that expose some new features and are just a little longer and put together some things we've seen。

 so we'll do three examples， one will be a sort of for loop。

 I've put it in blue because this is most similar to a homework problem I like to assign the purpose of this is to show a macro that takes multiple arguments。

 some of which we want to re-evaluate and some of which we don't。



![](img/90b9a8d569dde3a2ec454e3cded20c1b_1.png)

Then I'll show you a special version of let we define that can let you take a few different possibilities with fewer parentheses and that'll show how you can have a macro with multiple cases。

 then I'll show you another macro that not just has multiple cases， but is even defined recursively。

 so it'll be a recursive macro that ends up calling itself。

 and that will be a full reimplementation of let star just in terms of let。

 It's a fairly standard example for this sort of material。



![](img/90b9a8d569dde3a2ec454e3cded20c1b_3.png)

Okay， so here is this first four example and these things are sometimes a little hard to read。

 so how about first I just show you how it's used， I could say something like 472 11 do print high。



![](img/90b9a8d569dde3a2ec454e3cded20c1b_5.png)

And it will print five times because 11-7 is5。 Of course， I could have defined， you know。

 I can have arbitrary expressions in those positions。 Supp I have a function F that prints。

 let me do the begin， prints A， and then returns X。And then I have another function G that prints。B。

 and then returns x。 and how about one more function H。That prints C and returns x。

And now what's kind of interesting to me is if I say4 F of7。2， G of y。Do H sorry， A G of 11。

Do H of 9。And it prints a once。B once and C  five times。

 This is probably what a user of your for loop would want。

 It would like to see these things evaluate in this order。 And to get this right。

 we need to be a little careful in how we define our macro。 So here we have our four。

It clearly has two extra syntactic rules to undo。 those are not expressions。

 So we wrote those when we have something like four low， too high do body。

 we want to have this expansion。

![](img/90b9a8d569dde3a2ec454e3cded20c1b_7.png)

![](img/90b9a8d569dde3a2ec454e3cded20c1b_8.png)

So we use our idea of the let expression to evaluate first low， then high in that order。

 we will put the results in L& H so that we do not evaluate low and high again。

But then we do want to evaluate body one time for high minus low for every number between high and low。

 And so here I've just defined a little recursive helper function loop to do that and you'll notice you can follow the logic yourself。

 but right here I paste in， if you will body， And so that will be there in the body of the lambda。

 So every time this lambda gets called body will execute and it's inside a recursive loop here where it gets called the right number of times。

 So that's a nice example of controlling the order things are evaluated and how many times they're evaluated。

 let me show you one other example of it， by the way， which is if I flip it around。

 So the beginning is larger than the end。😊。

![](img/90b9a8d569dde3a2ec454e3cded20c1b_10.png)

![](img/90b9a8d569dde3a2ec454e3cded20c1b_11.png)

![](img/90b9a8d569dde3a2ec454e3cded20c1b_12.png)

Then it never prints C at all， which is also the behavior that I would want。So， that's good。Alright。

 let's do another example。 Here is a version called let2。 This is kind of interesting。

 Let me again start by showing you how it works。 I could say let2。

 and I can define up to two variables。 So when I use let， I need these extra parentheses， Y2。

 and then a body like plus X， Y。

![](img/90b9a8d569dde3a2ec454e3cded20c1b_14.png)

![](img/90b9a8d569dde3a2ec454e3cded20c1b_15.png)

![](img/90b9a8d569dde3a2ec454e3cded20c1b_16.png)

But let2 takes out these parentheses。 And I just write it like that。 But I have to call it Let 2。

 There we go。 And that does the right thing。 It produces3。 It also allows two few things。



![](img/90b9a8d569dde3a2ec454e3cded20c1b_18.png)

![](img/90b9a8d569dde3a2ec454e3cded20c1b_19.png)

So， that。Does the right thing。 except then you can't use the variable you deleted and it even allows zero things and then you could have a constant in here like two and2。

 Okay so that's the idea。 Let's see how this one works。

 The key thing I'm introducing here is that you can have multiple cases in your macro。

 So I'm defining let2， no extra syntax rules。 The first case is if you see let to。

 then parenthesis parenthesis than body just replace that with body。



![](img/90b9a8d569dde3a2ec454e3cded20c1b_21.png)

That's not the end of my macro。 The second case says if you have let to one thing， another thing。

 and then a body， replace that with a let that has one binding。

 So basically just put in some extra parentheses。 Everything will work。 And the third case。

 which is right here。Is if you have four things in parentheses and then a body。

 then do this nested let where you have let var 1， v1， then let var 2 v2， and then body。

 Of course I didn't have to do this in this nested way。 You can expand it however you want。

 but this does the right semantics and nobody will be able to tell。



![](img/90b9a8d569dde3a2ec454e3cded20c1b_23.png)

So that's how it works。 What about if you use it incorrectly， This is actually kind of interesting。

 Let's say I give it too many arguments， something that it has no case for X and Y。

 I don't even have to use Z。 This just simply does not match any of the three cases。



![](img/90b9a8d569dde3a2ec454e3cded20c1b_25.png)

![](img/90b9a8d569dde3a2ec454e3cded20c1b_26.png)

Then I get an error message。 It says let to bad syndax。 It says it doesn't match the macro。

 It's a bad syntax。 And similarly， if I had three things instead of four。



![](img/90b9a8d569dde3a2ec454e3cded20c1b_28.png)

![](img/90b9a8d569dde3a2ec454e3cded20c1b_29.png)

I would get the same error message。Now， here's the final one I want to show you。

 This is actually kind of interesting。 Suppose I write this。That actually does match the macro。

 It matches this third case。 This third case has let to followed by four expressions， which I have3。

 x 4 and Y， followed by a body。

![](img/90b9a8d569dde3a2ec454e3cded20c1b_31.png)

But after I do the expansion， I'm going to get a lead expression that it's not syntactically well formed because I'm going to have a number for var 1 and a number for varr 2。

So what happens？

![](img/90b9a8d569dde3a2ec454e3cded20c1b_33.png)

I get a syntax error message， but it's a different message。

 It's actually telling me this is a bad let。Right and the problem is this three where I was expecting an identifier so there is always a problem when you use macros。

 depending on how you define them， you can end up having error messages reported to your user in terms of the expansion instead of in terms of the macro and that is just a difficult thing about using macros racket has some support for improving error messages。

 but I'm going to leave that subject there where we have it。Let me show you one final example。

 This was this recursive macro。 Suppose racket did not have let star。 It just didn't have it。

 It had let， but it didn't have let star。 and you really wanted a let star。

 You could define your own because racket supports recursive macros。

 So I'm defining a macro here called my let star。 I'm just gonna have two cases。 Here's one case。

 Here's the other。The first case is if you have my let star， then the empty list of bindings。

 and then a body， just like we did we let two replace that with just the body。Otherwise。

 we have some special syntax for doing this kind of recursive thing。



![](img/90b9a8d569dde3a2ec454e3cded20c1b_35.png)

Do am I let star？😡，With this pattern。

![](img/90b9a8d569dde3a2ec454e3cded20c1b_37.png)

This says you have a first parenthesis and then a var 0 and then a Val0。

 and then after this next one you have this special thing dot dot dot。

 this is actually a special thing in racket macros， this basically says well。

 you can have one or more of the previous things and we can refer to those altogether and then a body。

And so that is the pattern we're matching。 And then the way the macro expands is into this。

 So it's a let with var 0， Val 0。 And then that lets body。



![](img/90b9a8d569dde3a2ec454e3cded20c1b_39.png)

![](img/90b9a8d569dde3a2ec454e3cded20c1b_40.png)

Is this recursive call to my let star where I pass the my let star。

 the syntax that is all the other bindings， including this dot dot dot， and then the body。

I just wanted to show you that I don't claim that from that you'd be able to write your own recursive macros。

 you should probably consult the reference to see how to do it。

 but I wanted to show it was possible and it even begs the question of well what if you wrote an infinite loop in your macro expansion Well that would be a bug and before the program ever started running it would try to generate an infinitely large program and that would eventually crash before anything ever ran when you write programs you can have bugs sometimes bugs can do unfortunate things when you have a powerful feature like a recursive macro you need to use it appropriately and we've seen how thanks to having a recursive macro you can do something as fancy as lets star even if the underlying language did not give it to you。



![](img/90b9a8d569dde3a2ec454e3cded20c1b_42.png)

And that， with that last bit of faniness concludes our study of Ra's macro system。



![](img/90b9a8d569dde3a2ec454e3cded20c1b_44.png)