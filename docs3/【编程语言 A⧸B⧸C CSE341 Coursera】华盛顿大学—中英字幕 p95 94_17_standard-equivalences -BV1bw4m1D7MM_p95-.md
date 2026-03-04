# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p95 94_17_standard-equivalences -BV1bw4m1D7MM_p95-

In this segment I'm going to share with you some well-known equivalences between functions。

 things that programming languages people have studied very carefully and understand well。

 when two functions are equivalent and what you have to be careful of to make sure you're following all the assumptions carefully so we'll just go through a few of these examples the first one is actually by definition we've seen a bunch of examples of syntactic sugar and if something is syntactic sugar it's always equivalent with the thing that is syntactic sugar4 that's really kind of the definition of syntactic sugar。

 so for example we saw that E1 and also E2 is sugar for if E1 then E2 else false so if you saw a function like you have here on the left takes an x and computes x and G of x for some G that's presumably in the environment you could always replace that with if x then G of x else false。

 which is not good style but a language implementation might do that so that it only has to implement if then。



![](img/48830623c420b152d6825c1dc3c815a8_1.png)

And not have to also implement and also by duplicating a bunch of code。 And， you know。

 you can go the other way。 if you see something like on the right。

 it would be good style to replace it with the thing on the left。

The thing to be careful about here is evaluation order and also is only sugar。

 if you evaluate the arguments x first， then g of x only if x is false。

 so the code on the left is not equivalent with this version you see here because the version on the right always calls G while the version on the left only calls G if x is false。

So that's our first example， it is really by definition。



![](img/48830623c420b152d6825c1dc3c815a8_3.png)

Here's another example。 This is the first of three that are sort of well understood by programming language people。

 and we work hard when designing our languages to make sure that they hold by treating variables properly and so on。

 And that is that you should be able to rename the variables in your function without causing problems。

 So I code on the left here takes in x returns x plus y plus X。 So2 x plus 14。

 The code on the right is exactly like the code on the left except it called the function parameters Z instead of calling it X。

 So it's z plus y plus Z。 And we really want these to be equivalent because we shouldn't have a language where the call E can have its parameter name change like you're cleaning up somebody's code and you say。

 oh， that's not a very good variable name Here is a better one and have suddenly callers be able to tell that you made that change。

 So you really want in your language that this equivalentence holds。😊，That said。

 sometimes people get a little sloppy and think that this means you can rename parameters to anything and have it always work。

Here are two subtle mistakes where you actually cannot do this。First。

 suppose we took the code on the left。 it's the same that we had up above。

 And instead of replacing x with Z， we replaced X with y。Well， if you just do that naively。

 you end up with F taking in y returning y plus y plus y。That's not the same function。

The function F on the right multiplies its argument by3。

 The function on the left returns twice its argument plus 14。

 The mistake here is if you rename your parameter to something that you were already using in the function body to refer to some outer thing。

 you're introducing shadowing that was not there before and your function is not equivalent。

There's a related subtlety that comes up where maybe y is not something already in the environment。

 but instead it's a locally defined variable。 So here the function on the left。

Defins a local variable Y for three returns x plus Y。

 So we know that this function just returns its argument plus 3。

The code on the right always returns six。That's not the same thing。 Even though again。

 all I did was replace every x with y。 Now this X I had here in x plus y is now referring to the shadowing of y。

 the three instead of the parameter。 So you have to be careful with this stuff and not reuse variables you are already using for some other purpose。



![](img/48830623c420b152d6825c1dc3c815a8_5.png)

Let's do another one。It turns out that you should always be able to choose whether or not to use a helper function without callers being able to tell so here I have some code on the left that just I think returns three times its argument plus 14。

The code on the right also always returns three times its argument plus 14。

 but it does it by using this helper function F so the code on the right calls F as a helper function。

 the code on the left does not use F， it shouldn't matter if I move out some of the function body and into a properly used helper function。

So that is all fine， you just have to be careful that when you do this。

 all the variables still refer to what they did before。So in this slightly different example。

 the code on the left is actually returning three times its argument plus7 because of this shadowed Y。

And the code on the right is using a helper function F。

 and this helper function F is the exact same code as it was up above。

But now it doesn't mean the same thing because Fs Y and G's Y are not the same y。

And so if I replace what was z plus y plus z with F of z。I end up using 14 where I should use 7。

 and you can check this by typing into the Reel that the function G on the left and the function G on the right are simply not the same。



![](img/48830623c420b152d6825c1dc3c815a8_7.png)

The last one I want to talk about， we actually have talked about plenty of times。

 and this is unnecessary function wrapping。So on the left here。

 function G takes in a y and returns f with y， and as I've emphasized a few times now。

 a simpler way to define G is to just say v G equals F。

They're both functions that take in one argument and return whatever the body of F returns。

 in this case， doubling the argument。The care here， the subtlety is you have to be a little careful。

 it's fine here where the function we're calling is just a variable。

But if instead we have an expression that we evaluate to get a function。

 then whether we're using function wrapping or not can can affect how many times we execute things。

 And if you have side effects like printing or mutable references， that can make a difference。

 So let me show you two things that are not equivalent on the left here。😊，Allright， I have F。

 which just doubles its argument。 H， a zero argument function takes in unit that when you call it。

 prints out high and then returns the function F。So this function G of y， every time you call G。

 it calls H， which prints high， then takes the result and calls Y with it。 So function G。

 every time you call it prints high and then doubles its argument。

The code on the right defines G the other way by just saying v G equals h applied to unit。

What that will do is we will one time call H， which will print height。Then return F。

 And so Val G is bound F G and F for the same function。

 So the code on the right will print I once before you ever call G and will never print I again。

Let me say that again。 the code on the right will print high once and never call and never print again。

They both double argument the code on the left does not print at all until you call G。

 but then print every time you call G， so if H might have side effects like this。

 it makes a difference， they're not the same。Okay， one more that I just kind of like because it helps explain let expressions and functions。

 We've also mentioned this once before， but it's good to repeat it now that we're talking about equivalence。



![](img/48830623c420b152d6825c1dc3c815a8_9.png)

I claim that the code on the left and the code on the right will always do the same thing。

 here's why。The code on the left evaluates as follows， evaluate E1 to a value。

Extend the environment so that x maps to that value evaluate E2， and that's your answer。

What about the code on the right？Well， this is already a value on the left。

 so evaluate E1 to a value。Then evaluate A2 in the environment where x is bound to the result of e1。

 and that's our entire answer。The left and the right do the exact same sequence of steps。

 They both evaluate E1， then evaluate E2 in the same extended environment。

 and then return the result of E2。 So there's no way they can't be equivalent。

And you really can think of these as being the same expression as if one were syntactic sugar for the other。

Now in ML， there's a type system difference， which is that the code on the left can give ex apolymorphic type。

 the code on the right will never give ex apolymorphic type。

 so there are programs where the version on the left type checks and the version on the right doesn't。

 but that's a detail of ML's type system for any expressions that do both type check。

 they are equivalent and will always produce the same result。So overall I'm now showing you。

 I think five examples of general situations where two things are equivalent and some of the subtleties where you have to think about shadowing or side effects and similar ideas。

 and if you understand these subtle distinctions， then you should understand the role of variables and the meaning of functions at a very fundamental level。

 these things are not ML specific， these are things that should be true whenever you're programming with variables and functions。



![](img/48830623c420b152d6825c1dc3c815a8_11.png)