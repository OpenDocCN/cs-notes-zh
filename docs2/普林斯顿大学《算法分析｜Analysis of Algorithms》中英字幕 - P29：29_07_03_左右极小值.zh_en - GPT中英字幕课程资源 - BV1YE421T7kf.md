# 普林斯顿大学《算法分析｜Analysis of Algorithms》中英字幕 - P29：29_07_03_左右极小值.zh_en - GPT中英字幕课程资源 - BV1YE421T7kf

![](img/260c8d9f9206a72ac1329fdf59b3fe1f_0.png)

So next we're going to look at properties of permutations and as our main example we're going to talk about what's called left to right minima in permutations。

 so this is a parameter of permutation， so I want to talk some about the general approach that we use for analyzing parameters and we talked about it last time for trees。

So we talked about leaves in random binary trees last time。

 so we're going to use the accumulated cost approach because we can use the symbolic method in a very straightforward manner so recall that we're going to define generating functions for the counting sequence and for the accumulated cost。

And then we're going to have a construction and the construction will give an equation。

 a generating function equation for the accumulated generating function。

And then we're going to either solve to get an explicit formula or find another way to extract coefficients to get the counting sequence and the accumulated cost。

 and then we divide the accumulated cost by the counting sequence in order to get the expected value。

And we did that for leaves and binary trees last time。

 and that's the general approach that we typically use in analytic combinatorques to analyze parameters Now for permutations。

 there's a small trick。 and there's also a small trick for strings we'll see next time。

And so first thing is we're going to use exponential generating function for the accumulated cost。

 and it's exponential in the size， so we're going to consider the generating functions of the form b of z equals to sum over all permutations。

Whatever the cost of the parameter that we're analyzing times z to the size of the permutation over the size factorial。

And that's again， if you group them by their size， that's Z to Bn over n factorial times the cost。

 So exponential cumulative generating function。Now。

What we'll do is treat that as an O GF to get the expected value out directly。 It's， it's a little。

 so B sub n is the total accumulated cost。 That's the total cost for Udions of size n。

 B sub n over n factorial is the average。So this works because an n factorial is both the normalizing factor and it's the counting sequence。

 so really this is shorthand for n factorial times coefficient z the amia is the total accumulated cost。

 and factorial is also the counting sequence， so if we just extract the coefficient of z to the N。

 we get the average for permutations。So that's what we're going to do is we're going to work with an exponential accumulated generating function。

 but then when it's time to extract coefficients， we'll just extract coefficient as z to the n and immediately get the average value of the parameter。

So the application is an elementary method known as selection sort。

 and it takes quadratic time for randomly order permutations。

 but it's the method of choice in some situations， for example。

 when records are large and you can read about that in the algorithms book。

In this a very simple algorithm that goes through from left to right。

 the first thing it does is find the minimum element in the permutation。

 exchanges that with the first then it finds the minimum in what remains and exchanges that with the second and so forth so first question is how many times there's a variable that keeps track of the current minimum in this code and the question is how many times is that variable updated assuming that all the keys are distinct。

So in this example， we start out thinking that s is the minimum owes less。 so we update it。

R and T are bigger， but I is less， so we update it again G E and finally A is the fifth update。

 so for this permutation， min is updated five times in the first pass。

This quantity is called the number of left or right minima in the permutation。

So that's what we want to analyze first。Now， so that's our question。

 how many left to right minima are there in a random permutation？Now， from a practical standpoint。

 this question is maybe less important than some of the others we talk about because。

This cost is not significant compared to the number it compares。 still。

 it's a fundamental property of permutations that we want to study。 So a left or right minima。

 we call an L RM in a permutation。 It's a parameter of permutation。

 and it's an element that's smaller than any item to its left。So if a permutation begins with one。

 like the ones on the top in these examples。It's only got one left， right minimum the one。

If it begins with two， it's got exactly two， the two and the one if it begins with three。

 it might have two or it might have three and so forth。

 permutation and reverse order of size n has n left or right mini。

 each new one is a minimum and so these tables in our standard form show for each permutation the number of left to right minimum off to the side。

Then the total accumulated cost is just summing those numbers or the。For three elements。

Cumulated costs， there's two， the cost1，3， the cost 2 and one the cost three。

 that's a total of 11 divide that by n factorial， the average number of left or right minima in a random permutation of size 3 is 1。

833， and similarly for size 4， it's 2。083 and so forth。

How many left to right minima in a random permutation of size n。 So that's our question And again。

 as usual it's very worthwhile to fully compute small values。

 both to get an appreciation for the intricacies of the problem and also to have precise values to check against when we complete the analysis so that's what this table is。

So what we're going to do is use a combinatorial construction to help us derive directly a relationship that the。

Accumulated generating function has to satisfy。And that's the figuring out which construction to use is the art of analytic combinatorics for these kinds of problems。

So for left right minima we're going to use a star product construction where we say a permutation is a permutation star with an element and that gives us a permutation one bigger it has to be renumbered in all consistent ways。

 and that just corresponds to giving the last element the numbers from one through n plus1。

 and then renumbering the other elements in the permutation accordingly。

So now if you look at the original permutation， in this case has three left to right minima。

 all the permutations that we got from the star product have the same number of left to right minima with the exception of the first one has an extra one。

 which is the one at the end。So that construction in that observation。

Tells us if we know the number of left or right mini in the original permutation。

 we know the number of left or right minima in all the permutations that we constructed。And that's。

There's P plus one of them， and every one of them has the same number of left right mini as P did。

So those copies and then there's one extra one， the one that ends in one。

 so that's a combinatorial construction for permutations and then we're going to use that to derive a formula that the generating function。

 the cumulative generating function has to satisfy。P plus1 L room a P plus one。

So to compute the average number of left right minimum randomum permutation。

 we define the accumulated generating function， which is the sum for every permutation of its number of left right minima times z to the size over size factorial。

 and again that if you group the permutations by their size that gives the accumulated cost。

 the exponential generating function for the accumulated cost。Which we don be in。

So now if we apply the construction， every permutation gives us P plus1 permutations。A。

So in the number of left or right minima in those permutations is size of p plus1 L of P plus 1 size of the permutations that we construct is z the p plus1。

 so that applying that construction media applies that equation on the generating function。

And that's an easy equation to simplify。So the first term。

The size of p plus1 LRM of P and that size of p plus1 cancels with the size of p plus1 factorial below the z the size p plus1。

 so that gives us the first sum LRM of P z p plus1 over p factorial， and then the second term。

 the plus1 just throws out a second term with z to p+1 over p+1 factorial。So that's a simplification。

 Now， both of those， we can evaluate the first one。

 if you look up at the first equation is just Z B of Z。And the second one。

 if you group by size of the permutation， just gives z to the K plus1 over k factorial。

Ced a cap plus1 over K1 because there's k factorial permutations。呃。Of size K。

 and that'll cancel with a K plus1 factorial， just leaving a K plus1。

 in that generating function is just log of1 over 1 minus E。So now just solving for B of Z。

 we get b of z equals 1 over1 minus z， log of1 over1 minus C。

And remember that's the ordinary generating function for the harmonic numbers。

 and remember our trick for permutations， if we get just to extract the coefficient of z to the n in that。

Then we get the B to the n over n factorial， which is our average number of left right minima。

 and it's just the harmonic numbers。So a direct derivation of average number of left left or right minima using combinatorial construction。

And it's a good idea to check those against the actual values that we observed at the beginning。

 In sure enough， those were the harmonic numbers。It's also possible to get the generating function equation through analytic commonatorques and I'll talk about that in a minute。

 but it's worthwhile to think in terms of these direct counting equations too and we'll worry about the analytic commonatorques and parameters a little bit mostly in the second part of the course it's worthwhile to get a little bit of experience working with it in this form。

 to really have a feeling for the power and generality of the method。

So that's left or right Mina now a similar question。In terms of parameters on permutations。

 suppose we want to know the number of cycles in a random permutation is size in。And again。

 if we look at this table， the number of cycles in each one of the permutations is written to the left。

And we can go ahead and compute the accumulated costs。

 and probably you already recognize that it's the same number and so now we're going to look at why it's the same number。

 so to analyze the average number of cycles in a random permutation。

 we'll use this same basic approach。We'll look at a construction creates that constructs permutations given one permutation construct of size n。

 construct n plus1 of P n plus 1 and use that construction to rearrange the terms of the sum of generating function to imply a relationship that that generating function has to hold。

 so for cycles， what we're going to do is if we have a permutation that's a set of cycles。

 we're going to insert and it's a size n， we're going to insert n plus 1 into every position in every cycle including the null cycle。

So first thing is put seven in the null cycle so that creates a new cycle of size one。

And then put seven in every position in the one cycle。

 there's only one place that makes a two cycle with two and seven in it。And then in the two cycle。

 there's two places to put it， 376 or 367， and in the three cycle there's three places to put it。

 either 4715，4175 or 4517。So that permutation of Psi 6， we construct seven permutations of Psi 7。

And so now the question is how many cycles are there in all of these permutations and so if the number of cycles in the original perm is cycles of P。

 then how many are there in all of these well they all have the same number of cycles except the case where we added a new cycle by adding to the null cycle。

 so there's p plus one copies of the original perm。

 all of the same number of cycles and then there's one extra for that extra singleton cycle。

So immediately now you can see that's exactly the same relationship that we had for left to right minimum。

 and so what that means is the derivation is going to be exactly the same。So instead of LRM。

 I wrote cycles， but it's the very same derivation。

 we apply the construction and use that to essentially reorder the terms in the sum。

 let's say the generating function also has to equal that。Expression。

 then it simplifies in exactly the same way to get down to the harmonic numbers。

 average number of cycles in a random permutation of size n is H sub。Now。

 when we have the same generating function again， often in combatorques and when we see that what we like to do is find a correspondence。

 between one to one corresponds between the number of LRM and the number of cycles so it's a reasonable question is there a one to one correspondence and this is a famous one and the answer is yes。

 so what you can do if you have a set of cycles， you can build a permutation corresponding to that set of cycles。

 a unique permutation corresponding that set of cycles by looking at the smallest element in each cycle and call that the leader of the cycle。

 so the first one， the four is the leader， the second one， the one is the leader。

 the single cycle is only one the third one， the 14 is the leader and the last one。

 the two is the leader so we identify the leader。Of each cycle。

And then what we'll do is write down the cycles in decreasing order of the leaderer。

 So we pick the largest leader and then write down its cycle just by following the cycle。

 So in this case， the largest one is 14。That's where we write 14，16。

The next largest leader is just the five。The next one is that first one， which the leader is for。

 so we write down 4， 10， 6， 15。And then the big one at the end， we write down 2，128311，13。

 and then the one containing the  one， 17，9。Now we don't write down we didn't demark the cycles in any way。

 but that's a permutation。And so I said it was unique。

 And that means we can use a corresponding process to get。

The set of cycles corresponding to any permutation。

 what's the set of cycles corresponding to this permutation？So we're given the permutation。

 What we do is identify。The left or right minima， those are the leaders。 Remember。

 we picked the leader as the smallest in the cycle。

And then we wrote them down in decreasing order of the leaders。 So between each leader。

 say between four and two， everybody on the same cycle as four is bigger。

And so as soon as we get to somebody that's smaller than four， that's the lit of the next cycle。

 so that's how we break up the permutation into cycles and that immediately shows that the number of left or right minima is equal to the number of cycles because this correspondence is one to one and works for any permutation。

So that's a famous correspondence between left or right， minima and cycles。



![](img/260c8d9f9206a72ac1329fdf59b3fe1f_2.png)

That。So now we can write down the cycles just by finding the LRM and then simply writing these cycles out as before。

So that's a couple examples of parameters and parametersmutations left or right minimum in number of cycles。



![](img/260c8d9f9206a72ac1329fdf59b3fe1f_4.png)