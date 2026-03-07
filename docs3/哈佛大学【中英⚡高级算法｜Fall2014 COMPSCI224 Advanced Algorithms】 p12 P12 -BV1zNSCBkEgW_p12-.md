# 哈佛大学【中英⚡高级算法｜Fall2014 COMPSCI224 Advanced Algorithms】 p12 P12 -BV1zNSCBkEgW_p12-

![](img/887ea0428273090e07d7e3c5e861a259_0.png)

Okay， so I'll get started。I sent an email， but just in case someone didn't see it。

Next week we're having two guest lectures， one on Tuesday one on Thursday。

 the Thursday one will not be recorded。So if you want to see that lecture。

 you should be here in person。Okay so today I want to wrap up with approximation algorithms。

We're going to finish FP tasks。This is we're going to do it for NapsSack。2。

We're going to look at F Praes。I'm going to do this for DNF counting。And then three。

We're going to look at semi definite programming。And we'll look at max cut。And if we have time。

 we might look at one other。Application as well。Okay。So let's get started。

 so last time we saw with Napsack that there was a PT。a PAS just means for any fixed epsilon。

 you can get a one plus epsilon in approximation， or for an Napsack。

 it guess a one minus epsilon in approximation。And your running time is a polynomial and n if epsilon' is a constant。

But with an FP task。We want to say that your dependence on Epsilon is also。Polynomial， okay so。

So we want to。Polly。And one over up san。Depenence。Fornaps。And I think actually what we'll get is。

Today。We'll just see it's a very simple algorithm。 It'll get you n cubed over epsilon。

1 minus epsilon approximation。Okay。Do you have a scribe today？Yeah， okay。

I did some searching around to see what。The best known bound was for Napsack。呃。So。

It's possible to get。With a different algorithm。A running time of n times log one of Repsilon。

Plus winter uppson to the fourth。This is due to luer。And。79。

searched around a bit to see if there was anything after '79 where someone improved this。

 but I couldn't find things， maybe I just didn't search hard enough。嗯。So yeah。

 there you go for if you're want a final project， I'm just giving it。No。Yeah， okay。So。Good。

 so let me show you this algorithm。So this is an idea that。Time。It gets used a lot in FP ta。

 which is so the idea is rounding。So remember the setup。Okay， we have N items， we have anapsack。

 first of all， a Napssack。Of size W。Capital W。And then we have N items。With weights。W1 up to WN。

 and also values。V1 up to VN， remember， and the goal is to pack this knapsackack。Don't。

 don't overload it。 You can't put。More than W total weight in the Napsack and the items that you put in there you want。

 you're going to collect the sum of values of those items and you want to get as much value as possible。

So the basic idea is。Well， what do we know？We know that there is an algorithm with running time。AndV。

So we mentioned this last time this is via dynamic programming where here V is just the sum of the VI。

Unfortunately， this is not polynomial time。Because the running time depends on the sizes of the numbers。

 as opposed to logarithms of the numbers。 Okay， writing down a number V only takes log V bits。

 So the input。Is exponentially smaller than V potentially？So the trick is just to make these small。

Okay。To get a PT， what are we going to do？We're going to define new values。

We're going to set v prime。It's equal or VI prime。To be。N over epsilon times。VI over Vmax。

And let's make it let's floor it， so that it's an integer。Okay。And then。Run。

An O of N V prime algorithm。That's going to give us a set。

This is going to be an exact algorithm for the new values。好 right。

And that's going to give us a set of items， which is the optimal thing for this new set of values。

 and the claim is just if you use that set for the original problem with the original values。

 you'll get at least one minus epsilon times opt。Okay， so I'll justify that for you。

 but what's V prime here？Or any bound on V prime？Capital D prime。And it's got to rhpsilon， right。

 So this thing。This thing here， we have v prime is at most。N times the max over I of V prime。

And well， VI is at most V Macac certainly。 So this is at most1。 So this is that most n over epsilon。

 So this is at most n squared over epsilon。So this running time is at most what I said at Mo Epsilon。

 so that's all there's to。

![](img/887ea0428273090e07d7e3c5e861a259_2.png)

The basic idea is something fairly simple， so what's the basic idea？Okay。First of all， we know。

That opt prime by opt prime， I mean， opt the value of opt in the new problem。 Okay。

 after you change these values， opt prime is at least。V maxax prime。Right the maximum value。嗯。

The maximum value of the VI primes。And one of the items actually has。Value V max， right。

 So that item will have。At least and over epsilon value。Okay。

But how much value did we lose in any given solution。In this new rounded problem。Well。

For each item in a set， we rounded down its value after this multiplication， right。

 So by rounding down， we at most decreased its value by one。So I mean。

 the basic idea is I'll make this more formal。After rounding。I mean。

 if there was no rounding if we just multiplied by some scalealar on every single value。

 then opt doesn't change， Every set just has the same multiplicative factor times its old value。

But by this rounding， we potentially lose one from every value。So after rounding。Any set。

 let's call it S， a subset of the items。Loses。At most。S， which is at most n value。Right。

Which is at most？Epsilon Times Ops problem。Allright。Zeng。😔。

Let's just now make it's a little very slightly more formal， so claim。If D P。Un roundunded。Instance。

Returns。Some set。A。Okay， which is subset of n。Then。The value of a。

