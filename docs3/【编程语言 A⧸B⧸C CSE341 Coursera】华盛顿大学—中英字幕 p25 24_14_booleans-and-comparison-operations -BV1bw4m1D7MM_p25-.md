# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p25 24_14_booleans-and-comparison-operations -BV1bw4m1D7MM_p25-

RightIn this segment， I just want to pick up a few odds and ends that we didn't do before in the interest of getting you ramped up but are useful things to know。

 And that's basically ways to combine Boolean expressions with and and or or negation。

 things like that and also how to compare numbers with comparison operations。

 I think I've only shown you equal and greater than so far。

 So let's start with the Boolean operations。 I actually showed you once because it came up for an algorithm we needed。

 the construct E1 and also E2。 So and also is just the seven letter keyword and the type checking rules are that E1 and E2 can be any expressions that have typepo and the evaluate rule is that we evaluate E1 if we get false。

 then the result of the entire thing is false and we never evaluate E2 Otherwise we evaluate E2 and then that's the result of the entire expression。

So this is exactly what in most programming languages these days is written with the ampersand ampersand operator。

 but M is an older language that shows a different and longer syntax。

 So you just have to write out and also when you want to do an and like this。 Similarlyly。

 we have or else where we evaluate E1。 if we get true。

 that's the result for the whole thing and we never evaluate E2 Otherwise we evaluate E2 and that's the result for the whole thing。

 And we have actually a function not an Ot that evaluates E1。 if you get true。

 the result is false and you get false。 the result is true。 So again。

 the syntax in most languages is different。 Ampersand ampersand a pipe pipe for or and the exclamation point for not。

 if you try those in M they're not going to work and and or and an or with amper amper and pipe pipe don't mean anything。

 So you'll get a syntax error。 The exclamation point actually means something totally different related to mutation which we might see at the very end。

 So you'll get a stranger error message。And then the last thing I wanted to point out is because and also and or else have this property that they don't always evaluate both subexpressions。

 they really are keywords and they're not functions， whereas not can just be a function。

 So let me show you that。 if I say something like true and also false。 I get false， that's fine。

 And if I said true and also true， then I get true， that's fine。 if I say not true， I get false。

 And if I say not false， I get true。 But if I just say and also。



![](img/e6d789f6d399e440448997f1057a64d7_1.png)

It's asking for more input。 It's like that doesn't make any sense。 That's not the right syntax。

 This is a syntax error because it says if you use and also。

 you have to put an expression on the left and an expression on the right， but if I just say not。

 it turns out that's not special syntax at all。 it just says， oh， well。

 that's a function that was already defined that takes a bull and returns a bull。

 and that works just fine for not because we always evaluate its expression。

 but we wouldn't want to find and also that way， because we know that。If we have a function。

 we evaluate all the arguments to it before we call the function。

 and since that's not the semantics for and also and or else， they're not functions。 All right。

 let me point out one other thing here going back to the slides， and that is that a language。

 a programming language， if it has， if then else expressions。

 it doesn't need and also or else or not。

![](img/e6d789f6d399e440448997f1057a64d7_3.png)

So it turns out， as you see here on the slide， if you were ever going to write E1 and also E2。

 you could just write if E1， then E2 else false because both versions have the exact same type checking rules in semantics。

 E1 and E2 both have to have typepo， we evaluate E1。 If we get false。

 that's the type result for the whole thing。 If we get true， then we get the result of evaluating E2。

Similarly， E1 or L E2 could just be written if E1 then true else E2 and not can be written if E1 then false else true。

 So from a how powerful is your language standpoint， all you need is if then else。

 But because we have and also or else and not， these longer versions with if than else are considered poor style。

 And that's because someone reading your code can tell much more easily， oh。

 this is and this is an and or this is an or， if you use the special syntax for it rather than these more verbose versions using the more general expression。

And as long as we're on the subject。Please make sure that you never， in any programming language。

 write the equivalent of if E then true else false。 Let's understand what this is saying。

 It says evaluate E to a result， which has to be a boolean， either true or false。

 If that is result is true， then our whole thing is true。 And if that result is false。

 then our whole thing is false。 That sounds very natural when your're programming。

 But you know a simpler expression that has the exact same semantics， E。

E is an expression that if you evaluate it and you get true， then the whole thing is true。

 And if you evaluate and get false， the whole thing is false。 So please just write E。

 not if E then true， else false。Okay， so those are the booleans。

 Let's just finish up with the comparison operators。 If you have two ints。

 You can see if they're equal equal。 we've done that。

 You can see if they're not equal with the second one。

 the less than greater than you might be used to in most programming languages exclamation point equals。

 It's just not M syntax。 you can think of this as less than or greater than if you like the other comparison operators are more familiar。

 greater than less than greater than or equal to less than or equal to just a couple weird things in Ml thanks to the type system。

 And that is that the last four for greater than and less than greater than an equal to less than or equal to can also be used for floating point numbers。

 which M calls things of type real， but you can't use it for an int and or real。

 So let's show you what I mean by that you can say3 greater than2， you get true。 you can ask if 3。

0 is greater and 2。0 that also gives you true。 notice that three has type int and 3。0 has type real。

 you can't do this。😊。

![](img/e6d789f6d399e440448997f1057a64d7_5.png)

You just get a type error。 Do you ever need to convert an int to a real。

 There's a library function that does that called real dot from int。 You could call it with two。

 you get back 2。0。 These purple messages are just the repel telling you that it loaded the library that has that functionality。

 and you're welcome to ignore that。 just one more complication now that I've mentioned realels。

 It turns out you cannot in M use equal or not equal on realels。 You can use them on lots of types。

 We'll talk about this in the future。 things called equality types。

 ints are just one example of an equality type。 but real is not an equality type。

 It's actually enforcing something that's good in any programming language。

 because floating point numbers are subject to roundoff errors。 It is rarely。

 rarely the right thing to do to actually take two floating point numbers and see if they're equal or not。

 You should always see if they're within some small epsilon， some small range of each other。



![](img/e6d789f6d399e440448997f1057a64d7_7.png)

![](img/e6d789f6d399e440448997f1057a64d7_8.png)