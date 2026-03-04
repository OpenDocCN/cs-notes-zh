# 普林斯顿大学《算法分析｜Analysis of Algorithms》中英字幕 - P15：15_04_01_标准尺度.zh_en - GPT中英字幕课程资源 - BV1YE421T7kf

![](img/4ac66b12168d2c0dbe4381352cc77dfd_0.png)

Today we're going to talk about asymptotics， This is mathematics that was developed well before the advent of computers in the 18th and 19th centuries。

 but it's quite relevant to the analysis of algorithms and to analytic combinatorics。

We'll start off by talking about the standard asymptotic scale。

 so the goal is to develop concise and accurate expressions that give us good estimates of the quantities we're interested in studying。

As I mentioned in the first few lectures， the Big O notation is really。Not adequate for this。

 if you say big O of log n， it doesn't give you an accurate measure of the quantity。

 it's an upper bound and it's within a constant factor and there's no way to get a precise estimate of what the quantity is。

If we had take a definition like this， say H sub n for the harmonic numbers， that one's accurate。

 but it's not concise it's going to take time to compute the exact value that you want Now that's not too bad but still the spirit of what we're talking about is to try to get accurate and concise expressions like this one natural log n plus gamma plus big O of1 over n。

 So that one for large values of n will give a numerical result that's very close to the quantity that we're interested in studying and we'll see lots and lots of examples。

 but that's the basic goal we want concise and accurate estimates of the quantities we're interested in studying Now we won't go crazy with defining what concise means what I mean by it is I've got standard functions and I've got。

Consts that are maybe known and I want to be able to compute this value for large n it's as simple as that I want to write a program we use a calculator to compute the value and actually that kind of definition it's easy to understand the motivation for scientists in the 18th and 19th centuries who we're learning more about mathematical models of the world and coming up with functions that describe whatever they're interested in studying but they want to be able to do calculations in order to be able to compare their hypotheses with what goes on in the in the natural world and without asymptotics it would be hard to do so because without computers you definitely need to be able to compute your answer and that's always a good perspective to have in the back of our minds when we're thinking about asymptotics。

So this is just a reminder I talked about these notations earlier on。

 so the big big O notation for upper bound， if you say G of n equals big O of F of n。

 that means absolute value the ratio is bounded from above as n goes to infinity。

And we're going to use that notation for error terms， but not for our leading terms。

Also we use a little o notation which says that G of n is little o of f of n if their ratio tends to0 as n approaches infinity。

 so that's gns asymptotically smaller than F of n and again we use that for error terms。

 in fact often we use the so-called tilde notation which just says that G of n and f of n ratio approaches1 as n approaches infinity。

 that's the weakest nontrivial little o so we use those notations to come up with approximations。

 so if we say that G of n equals f of n plus big o of h of n。

 it means the error will be within at most a constant factor of H of n as n increases。

Little O means that we know the error will decrease as n increases and that's good that means that for larger end we get a better result until again is the weakest nontrivial。

 little low as n increases we expect a better result and that's the basic approximations that we're going to be trying to develop。

So now with that background， what we're looking at is developing a series of functions。

And if we have a series of functions， GK with GK plus1 equal little O of GK。

 so that's a decrease in asymptotically decreasing series of functions。

Then if we write FN as a linear combination of those as they decrease。

 we call that an asymptotic expansion of the function F， and since the functions decrease。

 the expansion is supposed to get more accurate as we add more and more terms。

Precisely it represents the collection of formula F of n is big O of G sub0。

 it's also c0 g0 plus big O of g sub1 and so forth and we can pick off of this list of formulas。

 the one that suits our purposes best in terms of getting an accurate estimate of the quantity we're looking at and this will become more clear when we look at specific examples so we're using big O notation but in the specific technical sense we want to be able to be ensured that we can get more accurate asymptotic estimates if needed。

So the standard scale， we use the functions GK， we use powers of n and log n and maybe log n and log log n in exponentials so those are the standard functions that we want to use and we'll see it's very easy to express many of the functions that arise in scientific studies in terms of the standard scale and it won't give it's not necessary to give a detailed definition of this so typically what happens is we only use a few terms。

 maybe two， three or four terms， a second or third or fourth equation from this when the unused terms are extremely small。

 that's when we stop because we have the big O estimate that says we're within constant that unused term and it's extremely small relatively that's when we stop。

So we use the Tilde notation if we don't want to bother carrying around the big O information and a lot of times that simplifies the calculations and there's no reason not to。

 we usually check our asymptotic estimates against the actual values to make sure that what we have is giving us the accuracy that we want。

And if we do mathematically want to specify information on the unused terms。

 we go ahead and do that using the big O notation or the little O notation。

But the main point is that the methods we use in principle should extend to any desired precision。

If we need more terms we can get them and that's a very big difference from the use of the big O notation in the theory of algorithms where it's both expressing an upper bound and capturing the concept of the worst case。

 this is more in the spirit of science in the origins are clear in the 18th and 19th centuries where people wanted to be able to calculate things and then compare those with the results of scientific experiments and that's what we want to do in the analysis of algorithms and that's why we embrace all of this classical mathematics。

So here's an example from that we looked at in the second lecture。

 so there' we came up against a theorem that was going to give us coefficient abstraction for this was for solving linear recurrences and eventually we found through the use of generating functions that the quantity that we're interested in is the coefficient of Z to the n in the ratio of two polynomials and so what we can do with asymptotics is take a pretty complicated theorem statement that I'll show in just a second and reduce it down to actually a pretty general result。

 the coefficient of z to the n in the two ratio of the two polynomials is asymptotic2 a constant times beta the n into the new minus1 where beta is the。

Smallest modulus root of the polynomial in the denominator and new is its multiplicity。

 so this is just picking the leading term off of the more detailed theorem so in lecture2 I gave this detailed theorem that show that the coefficient of z to the n in that ratio there's a term corresponding to each zero of G of z and then according to its multiplicity and with asymptotics we can not worry about all the smaller terms in that sum and just pick out the largest one in a precise technical sense so for example if the roots are3 and 2 then it might be3 to the n and 3 to the n plus 2 to the n and you can see as n gets even to 11 they're pretty close。

And when n gets very high， they're going to get closer and closer。

 so usually the pole of smallest modulus really dominates。

 so no question 3 to the n plus 2 to the n is asymptotic2。

3 to the n you could forget about the2 to the n for large n。And。In fact。

 the convergence is exponentially fast as n gets large， even by one。

 it gets closer and closer to being accurate， the ratio gets closer and closer to one。

 so usually that pole of smallest modulus， the place where the denominator goes zero closest to the origin and that's the one that really matters。

 and I've emphasized this because this particular scenario turns out to be very important in a general context later on in analytic combinatorics。

Now there are situations depending on what these polynomials are where the poles are close together or the multiple poles very close to the one of smaller modulus and so in those kinds of cases we have to figure out how to extract the leading terms。

 but still it's very important to realize that we don't need to carry around the small ones。

 so sure if one of the roots is two and the other one is one half and the other one's one over 1。

9999， it's not going to be that close you'd be off by a factor of two if you try to throw that one away。

 but it's easy to figure that out and it's important to know that it's easy to throw away the small ones。

So here's how analysis would go for a recurrence， say like one of the early recurrences that we started out with a sub n equals 5 a minus1 minus6 n minus2 and a0 because a1 equals 12。

We only worry about the root of G that's smallest， so to solve the recurrence we make it valid for all n。

 then we multiply by z and sum on n to get a polynomial and that gives us for the generating function a ratio of two polynomials and what we're interested in is the coefficient of z to the n in that generating function。

 and now we can just plug and chug in the theorem， the smallest root of the denominator is onetd so it's going to be asymptotic to3 to the n。

 and then we go ahead and calculate the constant and if you plug in the values for the constant in that formula you just get one。

And if you want to apply the same thing to say the recurrence for the Fibonacci numbers， again。

 the same steps are going to work and in that case the constant will be1 over square root of 5 and it'll be a feet of the VN。

 the golden ratio of VN。The extra term in that case is fee hat。

 which is less than one and totally negligible。So with asymptotics。

 we get a relatively simple general theorem that gives us a precise and concise result for a big family of problems。

Okay， so back to the basics， where do we start out。

 where do we get the asymptotic expansions that we need to start out？Well。

 for a lot of the generating functions that arise， Taylor's theorem immediately gives us an answer。

 it's an expansion through power series and Taylor's theorem。

 they're infinite but since they converge you can stop at any point to give results like this in principle we can take as many terms as we want off the infinite series and then we have a asymptotic series in the standard scale。

 so again these are just immediate from Taylor's theorem where the term of Xant of re factorial is the derivative of the function。

So we looked at all of these when we talked about expanding generating functions。

 the difference now is with asymptotics， we're onlyni interested in taking a couple of terms for the purpose of being able to accurately compute values。

So those are standard examples now these are Taylorlor theorem goes for x goes to zero actually we're usually interested in coefficient and z the n as n increases so what will do is just substitute one over n in all of these formulas to get asymptotic expansions and these are maybe in more familiar terms if you want it to compute e to the1 over n say n equals a million this will tell you it's going to be pretty close to1 well it'll be one plus one over a million plus one over two times a million squared it's not going to be worth trying to compute that any more accurately than that this will give a very great accuracy just with a few terms。

Same log of 1 over1 plus1 over n for n n it equals a million and it's pretty close to 1 million。

 the next term you won't notice until 12 decimal places out and the next 118 decimal places out if you just want it to a few decimal places use one over a million。

 that's the whole idea of asymptotics。And binomial has， this is for K constant。

 will have a similar kind of character， now this gets more complicated if K grows within and that's be one of the things that we'll talk about later on。

And the one that we use really most often is geometric。

 so anyway that's the what you get when you plug in one over n in the straight geometric series。

 one over n what it says is that one over n minus1 is really close to one over n for a million again。

 the next term out wouldn't happen for 12 decimal places。

So those are the basic building blocks of the asymptotic expansions that we work with。

 so just as exercises， just using those simple formulas。

 then we can get relatively accurate approximations of say sums and differences of functions。

 just using those formulas and so it's worthwhile to take a look at these exercises and just as getting started a problem in asymptotics。

 we specify the function and then we specify how accurately we want to estimate it。

 and so so these two problems， it's definitely worthwhile， just working for a second on those。

And if you go ahead and just plug in from the formula from before the previous slide。

 log of1 plus1 over n is1 over n minus1 over 2 n squared plus big over1 over n cubed。

 and log of n 1 minus1 over n is a minus1 over n， and so the1 over n terms cancel。

 and then you got two1 over 2 n squared terms which makes it just minus1 over n squared。

 plus big over1 over n cubed。So right away you can see the log of 1 plus1 over n is a rather complicated function。

 but we can approximate it very accurately as just minus1 over n squared and that's going to be quite accurate in the practical ranges of interest if it's minus then what happens is the1 over n squared terms cancel out we just left with2 over n so that's just a simple。

 simple example of asymptotic expansions using the basic information that we get from Taylor's theorem。



![](img/4ac66b12168d2c0dbe4381352cc77dfd_2.png)

And then combining those results， really just using algebra and for lots and lots of functions that come up。

 we can apply techniques like this to develop accurate expansions， that's what we'll look at next。



![](img/4ac66b12168d2c0dbe4381352cc77dfd_4.png)