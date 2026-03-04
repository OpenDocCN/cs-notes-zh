# 普林斯顿大学《算法分析｜Analysis of Algorithms》中英字幕 - P17：17_04_03_有限和渐近分析.zh_en - GPT中英字幕课程资源 - BV1YE421T7kf

![](img/b2c7adfd8e5fc911b8ea10ac0484b74c_0.png)

Next we're going to take a look at techniques for dealing with coming up with asymptotic expansions when our quantities are expressed in terms of sums and we'll see lots and lots of need for applying these techniques a lot of times our final result is in the form of a sum and so what we need to maybe the terms at the end of the sum are much smaller than the terms at the beginning we have to use different techniques for different ranges of the sum so here's an easy example called bounding the tail。

So there's a famous problem where the end result is expressed in terms of this finite sum n factorial sum as k goes from 0 to n minus1 to the K over k factorial。

So to deal with that one， what we're going to do is write it as an infinite sum。

 so the infinite sum k greater than equal to0。inus1 to the K over k factorial。

 that's just1 over E e to the minus1。So that quantity that we're interested in is equal to n factorial over E minus this remainder term。

 and the remainder term is n factorial some K bigger than n minus 1 to the k over k。

K factorial so now what we can do is just see that this infinite sum we can bound it just absolutely。

 it's the first term is less than1 over n plus1， the next one is less than1 over n plus1 squared and like that which is just one over n。

So that's a proof that that infinite sum is just 1 over n。

 and that's just a proof that our original problem is n factorial over E to within big O of 1 over n and again n factorial grows so fast。

 that's an extremely accurate estimate of that sum。

So that happens a lot that tail is very small and we can bound the whole tail at once。

Another possibility is that actually the。Terms in the sum are rapidly increasing in that case it might be that the only term that matters is the last one。

 for example， sum on k of k factorial so if you just look at the last two terms of that sum those are n factorial plus n minus1 factorial all the rest of them are all less than one over n times n minus1 there's n minus1 of them so that gives it to within a big o of1 over n。

 so you have to have a feeling for how the sum grows where the big terms are and where the small terms are。

 but often the sums that arise the terms change in a way that we can take if we can find the most significant part of the answer and express that and then bound the rest of it to get our asymptotic expansion。

The other thing that we do quite often is approximate with an integral and as I mentioned。

 that's where our approximations for the harmonic numbers and。

The factorials or the sterling numbers come from， and we talked about those approximations and there's proofs of these simple things。

 but we'll talk about better approximations later on。

So those are three basic terms that we use for approximating fine at sums。

 but the main one is approximating with an integral。

Classic formula for approximating sums with integrals is known as Euler McLain summation。

And there's two versions of that theorem given in the book in a bit of discussion about where it comes from。

 most people are just going to be in the position of wanting to apply the theorem。

 so I have a finite sum say a K goes from one to n of F of K thats this theorem gives an asymptotic series for that sum。

 kind of like a tailor expansion that is expressed in terms of the derivative of the function。

And there's a couple of unique things about this series when it comes to applying it。

 so one thing is the error correction terms what do they like the first one is half f of n so that's at the end of the integral is a little bit left out say and then there's a constant that's dependent on the function。

 sometimes we have explicit expression for this constant sometimes we don't and actually the two cases we gave for harmonic numbers。

 we just name that thing gamma， we don't know how to express it in terms of other mathematical constants for factorials for sterling approximation of log of n factorial turns out that that constant is squared to two pi but that's something that has to be derived independently。

And then the next error terms， the first one is proportional to the first derivative of the function with coefficient 112 and then usually we stop there because the next one is proportional to the third derivative with a constant of one over 720 so it's way smaller。

 actually this series like some other asymptotic series doesn't necessarily converge。

 the terms can start to get bigger so we don't want to take too many but we can know that since it's an asymptotic series if we stop with a big O we can get an accurate result by stopping with just a few terms and usually for oral McLaron summation。

 we have the integral in just a few more terms。So there's a lot of details about that in the book。

 but in terms of applying it， just using this form is very useful for a lot of applications。

So classic example， f of k equals 1 over k integral of F of x dx from1 to n is log n。Yeah。

The F of n is1 over n， so that's a 1 over2 n， the constant is gamma， derivative is 1 over n squared。

 so that's that and then the next term third derivatives1 over and4。

 so that gives us the harmonic numbers from orch ins summation to within O to n to the one4。

 so for n equals a million you're not going to see deviation from that for 24 decimal places。

And the other classic example is Sterling's approximation。And again， now。Logue of in factorial。

That's the sum of k so FK is just k and so sorry fK is log K so it's the integral in computed out and again there's a big jump in precision right at the end where the last term big O of1 over n cubed so that's going to be a very good approximation in the ranges of interest and we can use that for other functions as well but these are the classics that arise again and again in the analysis of algorithms and they're so useful because they're so accurate。

So here's a very fine example of applying the information that we've talked about so far in this lecture。

 so if we have Sterling's approximation， just take it to O of1 over N now what we want to do is use that to figure out how2N choose n grow so we want to get2N chooseN to within big O of1 over N。

So that's a straightforward exercise using the basic techniques that we've talked about with the algebraic manipulations on asymptotic series。

 let's look at how it goes。And it's worth doing a couple of exercises of this nature and there are plenty in the book because the number of terms that arise appear daunting。

 but you have the ability to whack them away with the big O and a lot of them cancel out。

So let's look at this， so two and choose n， so that's two n factorial over n factorial times n factorial。

So we have。Complicated terms are multiplied together。 we're going to use the X log technique。

 So that's equal to E to the log of 2 n factorial minus2 log n factorial。

 So change the multiplication division into sums of logs。Okay， so now those two functions。

 we can apply Sterling's approximation。So the next line is just plugging in on the first line is Sterling's approximation for log of 2 n factorial。

That's 2N， net log 2N。inus2 n。Plus log of squared of4 pi n plus over1 over n。

And the next line is subtracting off twice， again， the formula for stirring approximation。

 minus2 and log n。Minus n。Plus log squared to2 p M plus big of1 over in。So。That's。

That's the quantity。 So now we just have to do algebra。

 and you can see a lot of things are going to cancel out。

 So say the first term on the first line is2 n natural log at 2 n。

The first term on the second line is minus2 n natural log n。

 so that first one is log 2 n is log n plus log2。 all iss going to be left there is 2 n log2 then also look at the。

What happens to the terms involving square root of pi so log of squared root of 4 pi n minus twice log squared to 2 pi n。

 if you just multiply that out， there's a log 2 minus2 square root of log 2 square root then minus log of square root of n。

 so log 2 minus2 log square root of 2 that's0， so all this left is minus log of square root of pi n。

So those two terms go to that one simpler term。And the 2 n log 2 and that's all that's left。

 the2 n cancels with minus2 times minus n and so now that's2 n choose n equals E to the 2 n log 2 minus natural log of squared of pi n Now both of those terms have logs and it's e to that power so now we can undo the x log technique。

 the first term is 4 to the n and the second term is since it's minus1 over square root to pi n。

So that's an asymptotic expansion for2N chooseN。To within one over n and again， that's a big number。

 but if we needed to compute two inches n over four to the n。

 then we get a function like one over squared root to pi in and that's going to be what we're going to want to estimate the quantity that we're studying as a typical example。

So Sterling's approximation leads us to good approximations of binomial coefficients using the X log technique。

So there we go one over4 the end， two inches in， there one over square root of pi in。Okay。

 so here's an application in the real world of this kind of technique。So。The question is。

 for some kind of computational process， the data might be represented as a binary tree with an internal nodes。

 and the question is how do you represent that binary tree？

You can think about different ways to do it， but one thing that you can know is since there's one over input the number of trees is the Catalan numbers。

 you have to distinguish among all the trees， so you have to have at least log that many bits in your representation otherwise the number of things。

 the number of things that you can represent is less than two to that power and it's got to be at least that big if you use fewer bits then you can't possibly represent all the trees。

Now someone who didn't know asymptotics might respond to the programmer。

 that's how many bits you need， but how's the programmer going to compute that value for a million I have a tree with a million nodes it's not concise。

 it's not a value that's easy to compute well this is a well knownn function maybe but in general faced with functions like that that's not what we want but using the calculation that we just did。

 you can say that there's an extra factor of n2 n choose n it's4 to the n over square root of pi n cubed。

 and you take the log of that log base2 of that， that's2 n minus 1。

5 log n that's really close to2 n so need at least2 n minus so for a million。

You'd need 2 million minus 1。5 natural log base2 of a million which is about 20。

 so you need 2 million minus 30 bits at least。And that's an important practical fact to know actually there's a way to represent binary trees with two end bits。

 so that's within 30 of the best that you could do。

 and so people who are working with a problem of this sort could stop there。

 I know I need at least 2 million minus 30 and I can do it with 2 million I'm going to be happy with that。

And。

![](img/b2c7adfd8e5fc911b8ea10ac0484b74c_2.png)

This is not the time to go through this in detail， but the method of representing binary tree into in bits is to just do a priororic traversal of the tree and write down zero every time you hit an internal node and one when you hit an external node and that's a unique representation of the tree that you can get back if you look in the algorithm's fourth edition。

 there's a code for doing that representation。That's a fine example of why asymptotics are useful。

 takes the functions that we get from analysis， and it gives us a practical way to work with them。

So that's an introduction to asymptotics on finite sums。



![](img/b2c7adfd8e5fc911b8ea10ac0484b74c_4.png)