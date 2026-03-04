# 普林斯顿大学《算法分析｜Analysis of Algorithms》中英字幕 - P31：31_07_05_BGF与分布.zh_en - GPT中英字幕课程资源 - BV1YE421T7kf

![](img/f01364b6799008ba2600412484c33a98_0.png)

So now I want to finish up this lecture by giving an indication of how these kinds of problems can be solved with analytic combinatorics and the symbolic method。

Essentially those derivations in a sense were a little bit the hard way and there's an easier way。

 now we'll develop this fully in part two， but it's worthwhile to take a look at a typical derivation using analytic combatorics because it's actually not that much more difficult。

And actually， the idea is to use bivariate generating functions。

 That's really the way to analyze combinatorial parameters。So the idea is for a combinatoryial class。

 we have not just a size function， but we also have an associated parameter that has a cost。

And we want to analyze the cost associated with a size。

 we're looking for the average number of cycles in all permutations of size n and so forth。

So the way that we do that， say for unlabeled objects。

 is to just take another variable U and define the bivari generating function Z and U where z is for size and U is for cost。

 so for every object we take z to the size of that object and U to the cost of that object。

So that's what we work with for labeled classes， we divide by the size factorial。

 but it's the same idea， so that's the form we're going to work with for permutations。

Now the idea that those constructions that we gave are going to work just as well to give us formulas that these bivariate generating functions have to satisfy。

 and not only that， the bivariate generating function really does carry full information about the association between size and cost。

 and again it's pretty much as easy to compute as the CGF and we'll look at those computations next。

And not only that， using this approach with analytic combinatorics。

 it's often the case that we can get full distribution or the asymptotics of the full distribution by knowing and generate a formula that the bivariate generating function has to satisfy。

So it's extension of the symbolic method beyond just counting to also take into account costs of parameters in combinatorial structures。

So what are the basic calculations so we start with a bivariate generating function and this is exponential for label classes like permutations because that's all the examples I've done so far today。

So if you want to go back to the way that maybe you're used to thinking of things and we had in our tables actually。

 the number of elements of size n with parameter value k， then the。

have the fundamental identity which just extends what we did for singlevari generating functions。

 if you're summing in all combinatorial objects， you can gather them together by size and by cost and then the number with size n and cost k。

 that's the coefficient of Z to the integral in factorial u to the K。

Because every one of those objects will contribute one to the sum， you gather them together。

 you have ANK objects that have that sum。And so that identity is implicit when we're trying to understand the combinators of it。

 we work with the representation where we have a term in the sum for every object。

 but when we want to do some counting， we use the elementary identity to get us the results that we need。

 so for example，As I just said， the number of objects of size n with value k we can get from the byvari generating function。

 It's the coefficient is E to the n coefficient U the K divided a multi by n factorial for label。

So but what's interesting is what's the average value of a parameter for a permutation。

 it's the coefficient of Z to the n in the partial derivative of the binaryvari generated function with respect to U evaluated U equals1。

It seems like maybe kind of a strange operation to perform， but that calculation is really simple。

 so if you take the partial of AZU with respect to U， you get K u to the K minus1。

So now if you evaluate that at u equals1， then the u to the k minus-1 goes away。

 And if now if you look at that sum， what's the coefficient of Z to V N in that。

 it's sum of K A and K。 And then again， the trick the divide by n factorial。 So it's the sum of k。

 the probability that it's k over。Some of k， the probability of that is k。

 which is exactly the average。So， just。Knowing that one little really trivial calculation means that we can go ahead and。

Use our constructions to tell us about the bivariate generating function and just do that one to differentiate with respect to U and evaluate at U equals 1。

So this is the construction that we did earlier on， say for average number of cycles。

 and this is the same slide as above， so I won't spend too much time talking about it so we apply our construction and then simplify the sum to get down to the harmonic numbers。

So let's do it with bivariate generating functions。So bivaria generate function。

 it's z to the size over size bacterial u to the cost。So now， our same construction。Which has for。

For cycles for every permutation we construct a bunch of other ones and P of those have the same number of cycles and one of them has one more cycle。

 so that's what this equation says of those permutations a size P plus1。

One of them has one more cycles， that's u to the cycles of p plus1。

 and P of them have the same number of cycles， that's P U to the cycles of P。

 so rearranging the terms in the sum， according to this construction implies that identity on the bivariate generating function。

And that one is not so difficult to。Simplify， so Z and the people plus one over peoples one factorial。

 that means we should differentiate with respect to Z。 and if we do that。

 then we get two simple sums that we can easily simplify the first one is just Z b Z of U and I mean sorry U B Z of U and the second one has is like the derivative with an extra factor of Z and you can check that。

 that's a very simple calculation。And now we can solve for derivative respect to Z。

 and we have B sub Z of z of u equals U over1 minus Z B of Z of U。

And that's a differential equation in Z。That we can just solve。 And it's1 over1 minus z to the U。

And it's a little shocking at first that there should be such a simple solution。

 But once you think of you as a constant and just work with the Z，s not。

 it's not so amazing a calculation。And that's an explicit formula for the bivariate generating function and what do we want from that formula。

 what we want is the average value of our parameter。

 how do we get the average value of that parameter for any bivariate generating function all we do is differentiate with respect to U and evaluate at u equals 1。

Differentiate with that with respect to you， evaluate at U equals 1， you get1 over1 minus C log。

 whatever over1 minus C。That and the coefficient of Z to theN in that is your average。

 which is the harmonic numbers。So the same kind of construction leads us to our result。

But what Ready makes by very generating functions， the method of choice is that we can actually get rid of this sort of construction stuff and Ready use this symbolic method。

 and again， we'll talk about many examples of this later on。 but I want to show it for this one。

So the idea is to just carry the cost along with the combinatorial constructions and the transfer theorems and everything else follow right through。

For bivari。And without much difficulty at all， so the symbolic method will take us right to where we need to get。

 so this says permutation is a set of cycles of z and the variable U marks the number of cycles and that's it so that immediately leads to the through transfer theorem which is the same cycle is log over1 minus z and set is E to the power。

Immediately leads to E to the U log of one over minus C。So simple combinatorial construction。

 immediate transfer to BGF equation， and there we are no sums at all， and what do we want。

 we want to differentiate with respect to U， evaluate U equals what。And in this form。

 it's the same function。 It's one over 1 minus Z to the U just written an X log form。

 It's obvious that the。Derivative with respect to U is going to bring out a factor of log 1 minus z and then leave this term evaluate u1 is just1 over 1 minus z。

 so immediate from the transfer theorem to there and then derivative evaluated that u equals 1 which immediately gives the harmonic numbers。

So derivations of this simplicity replacing the ones we've been doing is really persuasive evidence or persuasive bottom line that BGFs and the symbolic method are the method of choice in analyzing parameters and we're going to see many examples of that in part two。

啊。Yeah， so here's say， another example。 So you wanted to know the average number of cycles of size 1 that we did in exercise with 2 and R and so forth。

 So here's that derivation using symbolic method。So a number of cycles of size R。 Well。

 it's a set of cycles that are not of size R plus cycles that are of P R marked with the cost variable U。

 Now， that's it。And so by transfer theorem， that immediately gives logger 1 minus z minus with the1 for R subtracted off and then added back on。

 marked with U。So immediate from the transfer theorem to that BGF equation。

 and then what's the value we're interested in， we want to differentiate with respect to U evaluated at U equals1。

And that。Is immediate difference with respect to U brings up to the z to the R over R。

 evaluate u equals 1， just makes it e log1 over1 minus e。

 and that's the generating function for the average number of cycles in what's the coefficient of z to the n in that it's 1 over R as long as n's bigger or equal to R。

So the working with the constructions in the way we did earlier is at the level of detail that analytic combatorics can free us from and again。

 we'll see many more examples of working with parameters that allow us to use the symbolic method for。

Bvarirate generating functions in this way。呃。嗯。So that'll be mostly in part two。

And just to quickly finish up without going into much detail， this parameter。

 the number of permutations with size n with K cycles has got a long history and lots of applications that we don't have the time to talk about in detail so and it's written。

 it's called Sterling numbers of the first kind and it's usually written nowadays in square brackets like that。

So for permutations of size 3。There's。Two of them that have one cycle。

 three of them that have two cycles， and one of them that has three cycles。 and for four goes 6，11，6。

 and1， and so forth。So。What we just did was show that the。

If we just define the BGF for sterling numbers of the first time。

 we just showed that it's one over1 minus e to the u。

And you can use that form to develop all kinds of interesting identities for the sterling number。

 for example， the distribution of for a given n， the number of cycles of size n is the coefficient of Z to the n over n factorial。

 which if you use Taylor's theorem to expand this， you get u times u plus 1。

 U plus n minus1 and so forth。So if you take that polynomial as a polynomial in U。

 the coefficients that polynomial give you the sterling numbers of the second time。

And you can also come up with a way to compute them and get a recursive formula like the basic formula for binomial coefficients and so forth and we'll come back to some more details about this in part two。

 I just wanted to point out that this kind of structure and more detail has been studied a great deal。

In effect， here's a distribution with the。With rescaling by N。 and actually one of the。Results。

In analytic combinatorics， we study try to learn about limiting distributions in situations like this。

 and actually can show that this distribution is normal in certain ranges。

So that's the use of bivariate generating functions in introduction of an easier way to deal with analysis of parameters in permutations。

So I just want to finish up with by pointing out a couple of exercises that people could do to test their understanding of the material that we've talked about so forth。

So far。 So the first one is to study arrangements。 So an arrangement of n elements is a sequence formed by a subset of the elements so。

that's a permutation。 use element， each element once and only once with the arrangement。

 you could use some of them more often。And so the problem is to prove to study arrangements and to get some kind of combinatorial interpretation。

And this next one tests two different concepts that we brought up。

 and that's inversions and involutions。 so find the average number of inversions in involution。

And there's no real reason to do that other than to test out mathematics。

And then this third problem gets at， what does the cycle length distribution look like？

So it actually turns out to be asymptotic to the Poisson distribution and from the generating functions you can show that and it's an interesting problem to work through。

So for our next lecture， read the。Chapter 7 in the text。 again， it's kind of encyclopedic。

 So you might find yourself skipping through analysis of certain parameters。

 but some of them have interesting applications。I think it's always a good idea to run some experiments to validate the mathematical results that we've developed and it's easy to generate random permutation。

 so why not do it to just check that， say the average number of cycles or the average number of one cycles in a random permutation agree with the results predicted by our analysis。

And even for distribution for that exercise when we're doing the distribution of cycle length takes cycle more computer cycles to study cycles。

 but it's worthwhile to run experiments to validate these things always。And again。

 it is used worthwhile to practice writing up solutions to exercises like this。



![](img/f01364b6799008ba2600412484c33a98_2.png)

So that's permutations。

![](img/f01364b6799008ba2600412484c33a98_4.png)