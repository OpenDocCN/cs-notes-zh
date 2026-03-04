# 普林斯顿大学《算法分析｜Analysis of Algorithms》中英字幕 - P35：35_08_04_字典树参数.zh_en - GPT中英字幕课程资源 - BV1YE421T7kf

![](img/8019f388c21c4760b457ca8a90858736_0.png)

So the analysis of tri parameters is one of the most challenging in the analysis of algorithms and quite interesting to contemplate so that's what we're going to look at next。

So again it's the basis of understanding performance in lots of large scale important applications that are part of our infrastructure right now。

 so one of the big questions is how much space does a try take well it's the number of total number of external nodes and then if you have the number of strings you're representing you can figure out the number of extra nodes that's the number of void nodes is really the extra space that you're using。

What about the expected search cost well like with BSTs。

 that's the external path length that's the distance from the route to all the external nodes。

 the average distance， so external path length， average external path length this try is 3。92。

 that's the search cost。Now you notice that even if half your nodes are void。

 that's only going to add half to this extra cost， that's part of the reason that tries are effective。

 you can have plenty of void nodes， and it's not going to affect the search cost all that much。

And then a leader election that's the length of the rightmost path as I talked about before it turns out we can analyze all of these I'm going to talk about external pathling and the others will be exercises。

And again the easiest model， the usual model is to think of the try as built from inserting n infinite random bit strings。

 eventually they're going to differ and that's where they differ。

 that's where you're going to get a nonvo node that might represent an infinite tail but we don't care the bit strings distinguish themselves eventually the try represents them according to distinguishing them on the leading bits。

 and from an analysis standpoint it makes for reasonable model。Because we can assume at every time。

 every node that we randomly go to the left or to the right。

And this model fits real data perfectly well when it's been studied。So the starting point。

 if you think back to the analysis that we did for binary search trees is very similar。

 it's just that so that is we have a try of size n there's k on the left and n minus k in the right for some value of k the difference is that two differences。

 one is what's the probability that there's k nodes on the left which in the case of binary search trees was just1 over n and the other difference is that。

You might have no nodes on the left and in nodes on the right。

So that's a technical thing that definitely comes directly from the definition of tries。

 but it makes the recurrence just a tiny bit trickier。So that's the recurrence down at the bottom。

 what's the probability that when you have in strings n random strings。

 what's the probability that k of them start with a zero bit iss just one over 2 to the n times n choose k so then the external path length of a try as you look at the root that adds n to the external path length because there's n nodes down below it and then one over 2 to the n so it's a probability that this k on the left which is n choose k over 2 to the n and then external path length c sub k external path length n minus k with the appropriate starting conditions and again it's just a little tricky to realize that there's a cN on the right hand side when k equals 0。

So for BST， the probability that there K on the left is1 over n。

 we looked at random Catalan trees where thats the probabilitybil is K on the left is a Catalan number and we had the Catalan distribution and for triess。

 it's a binomial distribution。So that's the recurrence and we can use that to calculate small values or the distribution。

 but that's the one that we want to solve。And again。

 just to by correspondence to the distributions that we looked at for random cattlean trees and for binary search trees。

 for binary search trees， the distributions totally flat equally likely for any node to be at the root for cattlean trees。

 remember we found that they were very likely to have one side or the other have only a small number of nodes and so the distribution was very skewed and very skinny trees。

 for AVL trees we're trying to make them more balanced and the distribution shows this amazing pattern that we haven characterized analyticallytically and for triess。

 the probability that's a roots k as binomial and that's really characteristic that we're looking for that's going to tell us that these things are going to be pretty well balanced because that tends to and over2 is the most likely thing。

Within square of n of n over two is where the divisions are mostly going to be。

 which means that it's going to be pretty well balanced。But let's look at that analytically now。

I'm not going to cover every detail in great detail。

 but I think you'll see how we go from one step to the other and you can check details。

Offline so this is the basic recurrence we're going to use exponential generating function for this and the reason is the n choose k allows us to if you divide by this equation by n factorial then you have c of n over n factorial on the left and then sum that on all n you get c of z use fus in the the exponential generating function and then the n choose k part of it is it's a convolution of c K over k factorial and1 over k factorial and without very much calculation at all you can verify this formula c of z equal this is by dividing by n factorial summing multiplying by z to the n and suming both sides pretty quickly comes down to this formula and you can also actually get this directly through the symbolic。

With an appropriate operation having to do with the way trees defined。

So very simple formula on the generating function， it's a convolution of E to the z over 2 and c of z over 2。

That's the generating function equation now it's not can't be characterized as the simplest of generating function equations that we're going to be able to solve explicitly because we have that Z over two in the argument。

But one way to deal with it is to just iterate。So if we applied the same equation for c of z over 2。

 just plug in the same equation， then the z e to the z becomes z over 2 e to the z over 2 minus z becomes minus z over 2 and then 2004 c to the z over 4 we can iterate and then the argument gets smaller and smaller and simplify so just's just collecting terms。

 but we're still have an equation that we can iterate。In in another step。

 you can see the pattern is that。what we're going to wind up with is z times the e to the z in every case。

 and then we have the declining z over 2， z3 z over 4，7， z over 8， and so forth。

 so we get a sum of terms the forms z times e to the z minus E to the half Z to z7，8 z and so forth。

So it's not yet to prove that this thing really goes away as you go to infinity。

 but anyway that's the iteration that we get， an explicit formula for the generating function for the average external path that gives us the average external path length in a try。

Okay， so we're looking for coefficient of Z to the n in that。

So well n factorial times z to the n in that， and if you go ahead and expand the E to the z multiply by n factorial and get the coefficient of z to the n。

 then we have this difference 1 minus1 minus1 over 2 to the j d n minus1 so j。Again。

 that's a fairly simple formula， explicit formula for the average external path length in a tri。

 but still does have the infinite sum and we're going to have to work with it a little bit。

I'm working through this with elementary analysis just to make sure that people see。

TheWhat's underlies this solution because we get to a kind of surprising result and it's good to see what's underlying what the structure is。

 and so that's what we're going to do。To characterize this fully analytically requires complex analytic methods that we'll talk about in part two of the course。

So。What we're going to see is on the next slide， we're going to use the- if you use an x log approximation。

 this thing becomes like1 over 1 minus e to the minus n over 2j。

And that's not a difficult calculation using X blog and the next slide will show that that's pretty close to end log based2 of N。

So that's the external path length in a try。So this step is not difficult and didn't mean to skip through it so quickly。

 but it's not difficult at all to show that with Xpl。

But now what I'm interested in is looking at this sum sum on J greater equal to0。

1 minus e to the minus n over 2 to the J。How we're going to characterize that？

And that's a really interesting function to take a look at it。

What I'm going to try to do with this analysis is try to isolate the periodic terms that there's an oscillation in here and I want to try to isolate the part that oscillates。

 and so the way that's going to happen is we're going to take the function log based2 of n。

 and we're going to work with the integer part of log basedase 2 of n。

 and then the fluctuation is every time you come to an integer as you go from one integer to the next。

 there's fluctuation in the function as you're working with the real function log X。

 but you're only picking off the integer parts of it and let's so let's see how it works。

So all we're going to do is take that infinite sum and we're going to break it into two parts。

 the part where j is less than floor of log n in the part where it's greater greater or equal to flow of log n so that's just split the sum into two parts at that one point and the key thing to notice about this is when J gets bigger than log base2 of n then2 to the j is going to be bigger than n and so we're going to have minus n over something huge we're going to get number very close to1 it's going to go away so and when it's j is small like say j is2 or something we have e to the minus n which is tiny the sum is just1 so basically we're going to have log n terms theyre very close to1 and all the rest of them are going to be very close to0 with just a little bit left in the center so let's look at how that goes。

So。In this case we just split off the log n so we get floor of log n。

 and then we have the second one E to minus center over2 to the J。

 and that's just spliting the first sum into two parts。So and then this one is the same。

 so no change there。So now。What we're going to do is let this J go as far negative as it wants it doesn't matter because if that j goes as far negative this thing is exponentially small it doesn't matter and we're off by an exponentially small amount so and that's going to allow us to combine the two sums in that part so now this is change j to j plus log n in this sum and same way change j to j minus log n in that sum and so now we have some floor to the log ns coming in into the sums but then there's n over floor to the log n well that's like taking the functional log n subtracting off the integer part all this left is the fractional part。

So the end some of this thing is。What's floor of log n that's the integer biggest integer less than log n that's the function log n minus flow of log n as n increases this function fractional part of log n goes from zero to1 and back again。

 so it's a fractional part of log n， it's an oscillating function and then but these other functions also are just functions of the fractional part of log n。

And again， I skip through just a tiny bit of subtracting log n from floor log n。

 but you'll see that that works out so now I have these three parts that are all functions of the fractional part of log n that is they oscillate。

And so this is my external path length over N， so right here this is a proof that it's asymptotic to in log based2N because the other things are all zero to1。

But what's really interesting about this is we look at these functions。

 so this is the proof that I just went through， if you have that recurrence then that leads to this result。

AndBut let's look at it in just a little more detail these three terms。So the first one is again。

 the fractional part of log n， and so that's just a plot of the fractional part of log n。呃。

Now the second one is this sum of e to the minus2 fractional part of log n minus j。

 and that one also oscillates as an increases it oscillates and that's the approximate magnitude of it and then this is this third one that also oscillates so we have these three terms that oscillate that we're adding together to give us the difference between log n in our function。

And what's amazing is if you add these all together you get a smooth oscillating curve that's very tiny in magnitude 10 to the minus6 in magnitude。

 not something you would notice if you didn't do the math we're going to see in part two will look into a little bit how to do the math。

 but certainly it's quite a surprise to see these functions that are so difficult different in character adding up to this continuous function so this is a proof that seeing a rim minus log in is this strange oscillating function that you wouldn't see unless you look out to six decimal places and the question is is there a reason why a recurrence like that which seems such a natural natural recurrence involving our integer costs should have this strange periodic。

behavior and the answer is yes， we're going to see when we get to complex analytic techniques in the melon transform that there's a perfectly valid explanation for such periodicity and not only that it's bound to appear in the analysis of lots of algorithms that are based on properties of pit strings。

 light triess。So applying that result and taking a look at the distribution that we get with Tris。

 you can see that it's even more tightly bound towards a particular shape。

 basically divided the center， even than BSTs。And so just to quote the results that we get from this kind of analysis。

 the extra space is about 44% of the external nodes are avoid。

The expected search class is about in logwayase2 of N。

So that's the number of bits you have to examine and that's a very acceptable search cost and competitive and for leader election well。

 that'll be an exercise。That's a discussion of tri parameters。



![](img/8019f388c21c4760b457ca8a90858736_2.png)

![](img/8019f388c21c4760b457ca8a90858736_3.png)