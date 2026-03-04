# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p122 24_22_optional-variables-macros-and-hygiene -BV1bw4m1D7MM_p122-

In this segment I want to continue looking at how macros interact with the treatment of variables in our programming language。

 it turns out the semantics of macros is different than the naive sort of macro expansion I've shown you so far。

 that's a good thing， it's better in situations where variables may shadow things that are in a macro and that better semantics goes by the name of hygienic macros。

 that's what I'm going to show you here。

![](img/4c6affbc865f571d64ba57b6e7447a6d_1.png)

So to do this， I'm going to use a very simple example， which is a macro that doubles its argument。

 So I want to emphasize first its this poor style。 If you need something that doubles its argument。

 use one of these two functions you see at the top of the slide they're both perfectly good。

 and they are equivalent to each other and no client can tell how you've implemented it。

 you're just doubling and that's wonderful。 but for the sake of a short example that will fit on a slide here are two macro versions where the first macro replaces double of some expression X with plus Xx。

 the second one replaces double of some expression X with star2 X。Now。

 these two macros are not equivalent to each other。We saw this sort of thing in the previous segment。

 if I use the first macro with this argument， something that prints high and then returns 42。

I do get the result 84， but I also print out high twice because I replace double of this thing with plus of this thing and this thing。

 and so each of them will print， whereas the second version will only do the printing once because the replacement only uses this expression onces。

 so they're not equivalent and we want to study that sort of thing in the segment and even more subtle things。



![](img/4c6affbc865f571d64ba57b6e7447a6d_3.png)

So if you wanted to do something like the first one。

 you wanted to implement doubling as adding twice， and you wanted to use a macro。

And you didn't want it to print twice， then you should do something like this third version。

What you should do is say， well， when I have double of some expression。

 let's expand that to a let expression。 Let's introduce a local variable Y to hold X。

 So x is some expression。 maybe it prints。But then y will just be the result of that expression。

 because that's how let expressions work。And then we'll add Y and Y。

 And this is these Y's are just looking up a variable that holds the result of a previous computation。

 So now this macro seems to work much more like the version that star 2 x because it only prints one。

Fine。The general technique here is to use a let expression to make sure that your macro arguments are evaluated exactly once。

 Now， that's not always what you want。The My delay macro we did earlier。

 we didn't necessarily want to evaluate it once。 We wanted to put it inside a thk。Other times。

 you may want to have some of your macro arguments purposely be evaluated multiple times。

 because that's the entire purpose of the macro。 The next segment。

 I'll show you something with a for loop where there actually is some expression。

 We want to evaluate some number of times。 and then you shouldn't do this let expression either。

 But the technique is to use a let expression to control the number of times。 something is evaluated。

Another thing you might think about is the order that your arguments are evaluated。

 So here's an example here on the bottom。That does something that you might not want。

 So this defines a macro。 Take E1 from E2。 So this is a subtraction， but in the opposite order。

 it says the result should be the result of evaluating E1 and E2 and then subtracting from E2。

 the amount E1 maybe this is more logical ordering of the arguments to you。

 But the way this is being macro expansion， we end up with minus E2 E1 and that's right for producing the right answer。

 but if the order of evaluating your subexpressions matters this will evaluate E2 before E1 because we do the expansion。

 the result of the expansion is a function call and in racket function arguments are evaluated in order from left to right。

 that might the user of your macro who does not know that this is the macro expansion。

 they just read the documentation of use this macro to take E1 from E2 might be very surprised when things are evaluated in the opposite order that they wrote them down and you can。

Once again， fix this， not shown here with a let expression to evaluate E and then E。

 And then they use those results in the subtraction。Okay。

 so I'm recommending for issues like you see on this slide， putting local variables in your macros。



![](img/4c6affbc865f571d64ba57b6e7447a6d_5.png)

Those of you that have perhaps done a lot of programming with CN C plus plus macros might be really upset that I'm doing that because in those languages。

 it's usually very unwise to put local variables inside of your macros。

 and if you ever need to do it to go end up using variable names that probably no one else would possibly use anywhere like underscore。

 underscore strange underscore name 34。So for all of you。

 let me explain why people in impoverished macro systems end up doing this and how racket has a semantics that makes this unnecessary。

 you can use local variables in your macros and everything works out fine。So here's an example。

 Here's yet another version of double that's very silly for the purpose of demonstration。

 So what this does is it takes in some expression X。And then it does are multiply 2 and x。

 So that was the easy version。 but then it also multiplies by y where y is some local variable that holds one。

So it seems clear that this will do the right thing， will double its argument。

 just has this unnecessary argument why。But now here's a very strange use of the macro。

It's not strange to the user makes perfect sense that I might have some local variable Y that's 7。

 and then use the double macro with Y。So if I'm the user of the double macro。

 I'd expect this to return 14， the fact that there's some other y up in the macro definition should be an implementation detail。

But under the naive semantics， I've been kind of assuming throughout this section。

 that would not be what happens。If you take this double Y and you replace it。

 as the rules up here would suggest， you would end up with let y be 1 in star2 y y。

All I did was take the body of the macro， but wherever there was an X。

 I put the actual argument to the macro， which is y。This is a problem。

 If you evaluate this entire result， which is what you would get from that naive macro expansion。

 you will not get 14。You'll get2。Somehow， the Y here at the macro use got captured。

 got put underneath the Y in the macro definition。This is the sort of thing that can happen in C or C plus plus。

 This is not what happens in racket。 Raet gets this right。

 If you have this use exactly as you see on the slide， when you run this， you will actually get 14。

 This is part of what it means for your macros to be hygienic。 They're clean。 They keep separate。

 the local variables in the macro from any local variables it might be in scope where you're using the macro。

 The way racket does this is it just changes the names of variables in macro definitions as necessary。

 and we're not going to go into the details of how it does it。

 just rest assured that you get 14 in racket。 you do not get the naive expansion。

So it turns out that's one of the problems that can come up。

 there's a second one where you also get the wrong answer and that racket also fixes。

 so let me now show you that one。

![](img/4c6affbc865f571d64ba57b6e7447a6d_7.png)

Here I have this perfectly reasonable macro， there's nothing wrong with this macro except that you should define a function。

 and it just takes double of selling expression X and produces star2 x。

But what if we use that somewhere where the function star and star is just a function I could have shown you an example of a function namedF instead of star。

 What if we use this macro somewhere where star referred to something else because the built-in standard library star was shadowed。

Here's such a use right here。If I call the double macro with 42 in an environment where multiplication has been shadowed by addition。

😡，Then the naive expansion would be star 2042 in a situation where star has actually been rebound to plus。

 and I would get 44 instead of 84。And again， rackcet does the right thing。If you have variables。

 like star。In a macro definition that are defined outside the macro definition。

 you look them up in the environment where the macro was defined。

 not in the environment where the macro was used。 This is our old friend， lexical scopepe。

And it applies to macro definitions in racket the same way it applies to function definitions。

Then this is again something that most macrosystems， including the preprocessor for CNC++。

 simply do not do， this is sometimes abused this sort of dynamic scoping in those languages as a feature instead of a bug。

 but I would say that experience suggests that the vast majority of the time。

 you would rather have racks lexical scope and hygienic semantics than what you get in these other systems。



![](img/4c6affbc865f571d64ba57b6e7447a6d_9.png)

Okay so a hygienic macro system basically gets these two issues correct。

 the way it does it is for the first issue， when you have a macro definition。

 it secretly replaces all the local variables with other local variables and uses them consistently so that they can't interfere with anything that might be used in the use of the macro and for the second issue it basically uses lexical scope for macros the same way it does for functions。

This is not what you get by naive expansion。 So it's actually quite a bit harder to implement rack's module system than you would naively think。

 but the racket designers and implementers were able to do that and were able to enjoy the benefits。

 I would just remark in passing these hygienic rules are not always what you want。

 They're just what you want the vast majority of the time。

 So there's much more two racks module system， you could read about in the racket reference if youre implement interested and they even have specific ways to indicate specific places where you don't want these hygienic rules and they'll give you a different semantics when that's what you ask for。



![](img/4c6affbc865f571d64ba57b6e7447a6d_11.png)