# 普林斯顿大学《算法分析｜Analysis of Algorithms》中英字幕 - P21：21_05_03_系数渐近分析.zh_en - GPT中英字幕课程资源 - BV1YE421T7kf

![](img/7d526d3d95a63fce676e6292d319f5d8_0.png)

Next， we'll look at coefficient asymptotics， how do we get estimates of the coefficients of the generating functions that are so easily obtained through the symbolic method。

Fortunately， it's the case that we often can immediately get the coefficient asymptotics through general transfer analytic transfer theorems。

 and we've already seen some examples of transfer theorems that work for a lot of cases， for example。

 Taylor's theorem is a transfer theorem。If you have a generating function F of z。

 and you know it's derivatives， then coefficient of z to the n in f of z is the ns derivative evaluated at zero over n factorial。

And offer lots of functions。 That's how we extract coefficients。

 That's how we get started with generating functions。We saw another example with rational functions。

 and we talked about that in Geneing functions lecture and also the asymptotics lecture。

This is a special case just for simplicity on this slide。If F of Z and G of Z are polynomials。

 then the coefficient is z to the n and the ratio of F of z to G to z depends on the largest root of the denominator。

And if one over beta is that， then this expression。H。Gives the， it should be asymptotic of the。

C is z to the n and the ratio of those two beta times f of 1 over beta divided by g prime of beta beta to the n。

 the growth is like beta to the n， and that's the constant if that root has multiplicity one and we have a better form。

A more complicated formula that depends on the multiplicity if it's got higher multiplicity so those are two examples of transfer theorems and we use those。

 the one I want to talk about today next is what's called a radius of convergence transfer theorem and that covers the problems that we've talked about today in many others but actually most of the transfer theorems that we use in real life are based on complex asymptotics and we'll talk about those in a lot of detail in part two。

 but the radius of convergence one works for a lot of things and that helps give a coherent treatment of analytic combinatorics at this level。

So here's the theorem。The idea of this theorem is that the function。

1 over 1 minus z seems to arise a lot in the combinatorial constructions that we develop。

 so this is one minus z to alpha power where alpha is not necessarily an integer。

 the only restriction is it can't be a zero or a negative integer。And it so gives us， in some sense。

 it generalizes the ratio that I did before where G ofZ was a polynomial。

 now it's 1 minus z raised to alpha power。Coff of Z to the n and f is z over 1 minus z to the alpha is asymptotic to F evaluated at1 times n plus alpha minus1 choose n。

And that's asymptotic to F evaluated at one。N to the alpha -1 over gamma of alpha。

 Gamma of alpha is a constant I'll talk about in a second。

And I'm not going to go through the proof now because most people are just going to want to apply this theorem and not approve it。

 but it's not that difficult proof， really it's a convolution that involves the generalized version of the binomial theorem and also since the thing converges the sum of the first and coefficients converge exponentially to f of1 that's quick description of the proof for the first part and then the second part is standard asymptototics just using the definition of the generalized binomial coefficient and this function。

 the gamma function if you don't know what the gamma function is here's just a real quick summary it's a way to generalize the factorial function and plays an important role in analytic combinatorics and the analysis of algorithms because it arises in transfer theorems just like this one。

So for real Z， if you define this function， gam of z equals integral from0 infinity。

 t to the z minus1， E to the minus t dt。Turns out that function has the properties that we would want in generalizing the factorial。

 for example， gamma of alpha plus1 equals alpha times gamma of alpha。

 just like n factorial equals n n times n minus1 factorial。So and then if you work it out。

 gamma of1 equals 1， so gamma of n plus1 is exactly equal to n factorial。

 so for integers it matches the factorial。But it always satisfies this property for any alpha and gamma 1 equals 1。

 and then one that comes up really a lot for us is gamma of1 half if you want to compute gamma of1 half so it takes z equals1 half in there and then you get something like the normal and you compute it to be the square root of pi。

好。And so again，1 half equals square root of pi is a value that that we want to know because we apply this thing with alpha equals1 half the square root of 1 minus e。

So that's a transfer theorem that works whenever we have a convolution of some function with1 minus e to the alpha。

 and that turns out not to come up a lot。And just a little more generally。

 if the radius of convergence is bigger than a rh and if a rh is not equal to0。

 so it's just applying this to0 over rh， plugging in zero over rh in this theorem。

 then we get slightly more general， do1 over1 minus0 over rh to the alpha。

 and that pulls out a rh to the n in the。In the asymptotics。

 so that's just an elementary calculation to see where that comes from。

So that coroller is the one that we'll really be interested in。

So that's the theorem if we have a generating function of that form。

 we know the anymptotics and that applies to the two major problems that we've talked about so far in this lecture。

For Catan numbers， so t of z equals1 over 2 is z 1 minus squared to 1 minus4 z。

 so there's a tiny complication because the first term has to cancel out but ignoring that what we're using is alpha equals1 half in this alpha equals minus1 half。

 so that's1 minus zero over a row and the minus1 half in the denominator that's square root and row equals a fourth so that' square root to 1 minus4 z。

And then F in this case is just the constant， just the half out front。

And so we wind up needing gamma of minus12， and then that's two times gamma of1 half just because gamma alpha plus 1 equal is alpha gamma of alpha。

 minus2 squared of pi， so you plug it all in and then maybe it's easiest to think about it by just multiply both sides by Z and then apply these exactly。

 it's not hard to finish the calculation to show that this transfer theorem immediately gives us the asymptotics of the Catalan numbers。

Hi。So one transfer theorem to get the generating function， another transfer theorem。

 the analytic one， to get the asymptotics of the coefficients。

And this same theorem works for the derangements problem。

 so during numbered generalized derangements， we had this complicated function。

 not so complicated with this transfer theorem now we have alpha equals 1。

 we have rh equals1 our function is just e to the minus E so all we need to do is evaluate f at1 that's e to the minus1 minus1 half up to1 over m that's h sub M that immediately gives the asymptotics E to the minus h sub M。

So two problems that the first one， a lot of calculation to get there， second one。

 we don't even know how to get there immediately through this analytic transfer theorem。

 we can get the result。This is just really just the beginning what part two is going to be devoted to is the idea of really universal laws that we can get from transfer theorems based on complex asymptotics and I'll just talk through one there's a lot of technical details just to give you some idea if you have a system of combinatorial constructions where you have a bunch of classes and they're all interacting and those operations indicated by Op0 up1 t those can be sequenced are some are product operations and you can create a whole linear system of combinatorial constructions so a very simple special cases the binary tree1 where you get t on one side and Z times t times t on the other side you can have a much more complicated thing a cycle of binary trees of sets of well not those but but linear。



![](img/7d526d3d95a63fce676e6292d319f5d8_2.png)

Of combinatorial classes， a whole system of combinatorial constructions。

 those immediately transfer to a system of generating function equations with the symbolic method。

Well that's good， but those generating function equations might be quite complicated and difficult to solve。

 but in fact there's a method called Groner basis elimination that reduces those all down to a single generating function equation and not only that there's a theorem called the Dmoto Eliwoods theorem that shows that there's an explicit solution to that equation that equation's got the square root and this is in the complex domain and there's a process called singularity analysis that immediately gives a simple asymptotic form。

So any combinatorial construction is asymptotic to a over 2 squareta pi in Q， B to the N。

 where A and B are constants that we can explicitly calculate from the construction。

It's an amazing universal law， and you can find in older mathematical literature hundreds of papers that come up with these kinds of results that this one process covers。

 and that's just why one example of universal laws that we see in analytic common toques there's many more。

So that's an introduction to coefficient asymptotics。



![](img/7d526d3d95a63fce676e6292d319f5d8_4.png)