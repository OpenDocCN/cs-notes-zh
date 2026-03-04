# 普林斯顿大学《算法分析｜Analysis of Algorithms》中英字幕 - P22：22_05_05_视角与展望.zh_en - GPT中英字幕课程资源 - BV1YE421T7kf

![](img/70f5872fbaf68f5df56325a07ef3e23b_0.png)

Just want to finish up by talking a little bit， giving some perspective on the things that we've talked about so far today。

So the idea is that we have a calculus that is going to be very effective for quantitative study of all kinds of large combinatorial structures。

 always going through the same kind of process where we have a construction that translates to a generating function that translates to coefficient asymptotics。

 actually with complex asymptotics， we don't even have to solve explicitly for the generating function often merely the form of the equation is going to give a generating function that is going to give a transfer theorem that gives us the coefficient asymptotics immediately。

And just think about what we've talked about in the last four lectures versus this lecture。

 to count binary trees， so we had a whole slide to go from recurrence to generating function involving a convolution。

 and then expanding that generating function involved some kind of intricate calculations using binomial coefficients that you might remember。

 and that got us to the exact form of the Catalan numbers。

And then we had to do the asmptotics using Sterling approximation that also involved a significant amount of calculation。

AndYou may remember the first time you saw each one of these the amount of intricate calculation that seemed to be involved。

 although there's straightforward from step to step。

 there's a lot of steps with analytic combinatorics we don't do those calculations anymore。

 we simply create the combinatorial construction get to the generating function equation and then get the transfer theorem to get the asymptotic result that we're interested in and these are normally very accurate and certainly accurate enough for practical applications。

啊。So for derangements， in that case， we we don't even know didn't even do the example of the calculations so complicated。

 but we can get immediately to the coefficient asymptotics。

And this is a good example of something that is characteristic of analytic combinatorques because we had a basic construction a permutations a set of cycles that we modified to work with to get this answer that's very common。

 we start with some fundamental constructs that are，The basic things that we want to study。

 they're either elementary or they're trivial or they confirm our intuition， and we understand them。

 but we try to understand them from the standpoint of analytic combinatorics。

But then we can have compound constructs where we have a set of cycles or a sequence of sets and so forth。

 and again those are only the constructions that I've presented there's many。

 many other constructions available in those things there's lots of possibilities they'll tell us something about the structure like a permutation as a set of cycles and actually lots of classic combinatorics can be dealt with in this way。

 and then there's variations like generalizing derangements for adding in other parameter the possibilities immediately become almost unlimited and not only that when we get to a generating function equation。

 we often have a universal law that will give us the asymptotics there'd be no way to go in and get the exact result and then do asymptotics from the exact result in principle。

You could do that because what underlies analytic combinatorics is a bunch of very simple techniques。

 but why would you if your goal is the asymptotic result so that's a very standard paradigm and also combinatorial parameters can be handled and we'll see lots of examples of that so that is we're not just counting things we counting properties of things but we talked about in the generating function lecture about the concept of cud costs where rather than computing averages by using probabilities what we do is we count up the total cost among all structures and then divide and it's reducing finding an average for number expected in a random object to two counting problems so to find the leaves。

In binary3 we count trees using the standard process to get to the estimate of the cattlealan numbers。

 but it turns out that the symbolic method works for bivariate generating functions so the same construction will give a explicit equation for the total cost so that's the leaves in all trees you just keep track of the leaves in another variable and the same construction follows through and then differentiate evaluate at one to get the leaves in all trees the way that we did before we're going to get again an explicit and then we have the immediate transfer for that one too。

So we don't have to go into the detail。 we have these two asymptotic results。

 and then we just divide， and that's how we get to n over four。And again。

 we can do this without all the detail that we presented before。

So this is a slide that I started up with that maybe makes a little more sense now that we've gone through a number of examples。

In analytic combinatorics we begin with combinatorial constructions。

 we use symbolic transfer theorems to get generating functions。

 they're the central object of study because we transfer to them from combinatorial constructions and we extract coefficients from them using analytic transfer theorems。

And so in principle， we can do this to any precision on the standard scale。

 and we can handle variations as well。So now for the rest of the course we're going to be looking at many applications of analytic combinatorics for first we'll do trees and then we'll do permutations which actually can be represented as certain kind of labeled trees and we'll talk about bit strings and associated data structures in mappings which are fascinating structures and these all have applications to the analysis of algorithms so that's what we'll be doing for the rest of the course。

So that's a perspective on what we've been doing， I just want to finish with some exercises that you might do to cement your understanding of this material。

 so exercise 5。1 is how many Bi stringings of LiedIn have no occurrence of  three zeros。

And that's a fine exercise to try out these techniques on。Or for trees and this is just again。

 to go through the steps of。Analytic combatorics for problems similar to the ones that we did。

 so this is binary trees where the size is the total number of nodes， internal and external。

So there's no even number always an odd number of total number notes and so get an expression for that。

Permutations， what about when the cycles are all of odds length that's an easy one， tree parameters。

 so the red nodes here have both children internal and the blue ones have one internal and one external so what's the average number of red nodes and blue nodes we already did the average number of leaves is in over four so those similar problem。

So for the next lecture， if you write of solutions to those exercises and read the analytic combinatorics chapter in the text。

 you'll have a good feeling for the basis for the analysis of algorithms that we're going to begin starting in the next lecture。



![](img/70f5872fbaf68f5df56325a07ef3e23b_2.png)

![](img/70f5872fbaf68f5df56325a07ef3e23b_3.png)