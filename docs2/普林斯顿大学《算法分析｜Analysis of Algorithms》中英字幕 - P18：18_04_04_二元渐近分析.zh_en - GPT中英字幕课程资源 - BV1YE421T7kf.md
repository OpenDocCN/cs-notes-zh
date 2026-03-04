# 普林斯顿大学《算法分析｜Analysis of Algorithms》中英字幕 - P18：18_04_04_二元渐近分析.zh_en - GPT中英字幕课程资源 - BV1YE421T7kf

![](img/f4c6cb20630b42b0beb99f85de425f7a_0.png)

Next， we're going to talk about an intricate extension of the asymptotic techniques that we're looking at where there's two variables involved。

 and these arise frequently in the analysis of algorithms。So。

A lot of times in the study of algorithms， we have two variables that we're working with。

 one is the size of the problem and the other is the cost。

 so we're going to wind up with intricate expressions that are involve those two variables and they might very independently so we have some definite challenges。

The problem is， as I indicated， when talking about doing sums is that the relative values of the variables might matter。

 and that makes it even more challenging to deal with sums over the whole range of relative values。

And you'll see what this means when I get to some applications， fortunately。

 as was the case with the harmonic numbers and sterling numbers where there's a couple of fundamental functions that arise over and over again that take most of the work。

 similar is true of functions of two variables there's a couple of fundamental functions that arise and we'll look at the asymptotics of those。

 and they are the ones that arise most often and if it's not that function。

 it's a function that's similar that we can model the analysis on the analysis that have developed been developed classically for these functions。

So first example is the binomial distribution again。

That so K might be related to the cost and might be related to the problem size。

 How are we going to compute values like that for。How are were going to make computations if we wind up with an expression like that？

ItTs out that。As I just explained for the Cat n numbers， if k is0。

 that's close to1 over squared to pi n， that's two inches in。But if K is large。

 that's exponentially small， it's a very， very tiny quantity。

So we're going to have to come up with an analysis that tells us both those things。

Another example is called the Ranesian Q distribution， it's actually kind of similar。

Binomial coefficient is n factorial over n minus k factorial K factorial。

 this one's n factorial over n minus k factorial n to the K。

 and that actually arises in the analysis of several classical algorithms。And that one。

 if k equals0 is just n factorial and n factorial， it's1 but if k is close to n。

 that one is exponentially small， n to the n is way smaller than n factorial。

So those are the types of functions and the types of challenges that we face with analyzing functions of two variables。

Now to get an idea of what goes on， we use plots like this where we draw one line for each value of k。

 and then we scale。You can't in a graph， you can't have a variable n。

 so we make that a variable n by scaling the actual values by a factor of 2 n。

So the binomial coefficients， so for k equals2， it's one quarter， one half。

 one quarter then or just forgetting about the。The exponential scaling factor that's 1，2，1。

 and this is 1，3，3，1，1，4，6，4，1， so you can see Pascal's triangle in these plots and what happens as many people are familiar is that as an increases this discrete two variable distribution converges to the normal distribution and to a curve that we can describe with a simple mathematical function and we're going to see the math to get us to the place that this picture shows us we ought to be able to have a simple description of this distribution and we do。

This is what ramanusian Q distribution looks like again the same type of plot for different factors of k。

 we draw a curve so K goes from0 to n when k is small。

 it's very close to1 when k gets close to n over2 it becomes extremely small and then there's a curve that describes its growth。

 so for large n we ought to be able to use some function that defines that curve for any value of k and that's what we're after with bivari asymptotics。

Now let's take a look first at the Ramanuian Q distribution， the calculations a little bit simpler。

 it's an extension of the calculation that we did for the Catalan numbers。

 it's just that now we're carrying on this variable K。So first step is use the X log technique。

In factorial remin k factorial n the K is E to the log of n factorial minus log of M minus k factorial minus log of n to the K。

 which is k log n。So that's the first step now how we're going to expand each one of those well the first two is are just handled with Sterling so we use Sterling's approximation to log n factorial and just plug that in in both of these cases。

 so that says log n factorial is n plus1 half log n minus n plus log squared root to2 pi plus0 of1 over n。

Now the difference is， so that's what we'll use for the first term， for the next term。

 we have that value of k that we have to worry about。Now we're going to have O of 1 over n minus k。

 which we can cover with O of 1 over n。So that's plugging in Sterling's formula for the first two terms。

 and then there's the minus K log n term still left there from the n to the K。So again。

 we've got a bunch of terms， three terms for the log n factorial。

 three terms for the log n minus k factorial， and then the minus k log n。

 and we've got to do algebra to deal with those terms。

 but again there's some cancellations that are going to help us out， log square root to2 pi cancels。

 the minus n plus n cancels there's。Lg of n minus k is log of n plus log of 1 minus k over n。

 so we get some cancellations there。So if we collect all those terms with all the cancellations。

 that's what we're left with E to the minus n minus k plus12 log of1 minus k over n。

 you might want to check the math on that but it's all a simple algebra that leaves us with that and the only technique used is log of n minus k equals log n plus log of 1 minus k over n and we're down to just a few terms。

So。Now we have to expand the log of 1 minus k over n。

And that's minus k over n minus k squared over 2 n squared plus O of k cubed over n cubed so now we're carrying both variables in the big O term which can be a little tricky we're trying to make this work for as many values of K as we can but different values of K particularly when K is proportional to n are going to give us different asymptotic accuracy and that's one of the challenges with byvari asymptotics but we'll carry it in this form and see where we go so just plugging in that formula and doing the math is so there's a minus k over n we're multiplying by n and again you can go ahead and do the math not too much survives there's k squared over 2 n minus K squared over n so that's minus k squared over 2 n the k's cancel so all。

get is e to the minus k squared over 2 n in the end and then what's left over are the two error terms and those error terms are just doing the math if you multiply n times a of k cubed over O of k cubed over n cubed get K cubed over n squared and if you multiply k times。

That's sorry， and then what's left is the O of K over in。So those are valid formulas。

 but the interpretation of the formula is going to depend on the value of k。

 and it tells us a lot for small k， for relatively small k。

 it says it's going to be close to e to the minus k squared over 2 it and that's the curve that we see。

So if we just analyze sort of different values， if this。

 in fact if k is like n to the two fifths say which is pretty good sized value then K over n is going to be one over n the threefi K cubed over n square is one over n to the four fifths so that's the error term seems like we're shaving into tiny distinctions。

 but the main point is one over n positive power that's going to be a a big distinction when k is square root of n they're about the same Now when k gets bigger then this term starts to starts to pick up but we can work with those different ranges and really the main point of this derivation is to show that for most of the curve remember the plot show it up to square root of n it's got a fine curve and read the description of that。

curveurve， and we have it。 It's E to the minus k squared over n。

Which is a simple function to work with as opposed to the original description involving factorials。

A similar situation works for the binomial distribution， and again。

 this is just an exercise using Sterling's formula。

 carrying through all the error terms and making sure that you get the cancellations。

And it's definitely worthwhile to close the book， turn off the computer and try to do this derivation just as an exercise in algebra perhaps because you can see when you do that how the cancellations happen and simplify the calculation and everybody who works in this sort of field knows that if you do a long calculation like this and you miss a term you're going to get something very exciting at the end that maybe is not relevant or wrong。

 simply by missing a term， because you're E to a power and you accidentally forget to cancel out an end term。

 you got E to the end which probably is not there at all just as an example。

 so we'll do the calculations， I'm not going to explain。Return on these calculations。

 but because they're actually very similar to the ones that we just did。You apply Sterling's formula。

 and so that gives three lines each with four terms， one for each of the main terms。And again。

 initially we can just use o of1 over n for the whole range where we start to have to carry terms that involve o of k over n is when we expand log n minus k to be log of n plus log of 1 minus k over n and log of n plus k to be log of n plus log of1 plus k over n。

 that k over ns are one in those asymptotic series are the ones that give us some complication。

So when we do this and do the algebra the bunch of things cancel。

 the2N cancels with the twoNs and so forth and so these are the terms that survive and again that's pretty much straightforward algebra with the additional proviso that we're doing that expansion log in my equal was log n plus log1 myre the terms of all in the log n。

 most of them go， and so we're left with that。And then these two terms are kind of similar。

 one's got a minus k， one's got a plus k in just rearranging terms in terms of k times this difference of log1 minus k over log one plus k run and n plus12 times the sum。

 those two that sum and that difference that's one of the first exercises that we did and those things collapsed down to just one asymptotic term so。

The sum of them is asymptotic to minus k squared over n squared。

 and the difference of them is asymptotic to minus2 over n with again， big O terms involving KQ。

So substituting that in gives us。E to the 2 n log 2 minus natural log square root of pi N。

 that's the only part of pi that's left over from all the math。

Minus k squared over n plus the big O term。And then just undoing the X log technique。

 E to the 2 n log 2， that's4 to the n。E to the minus log squared of pi n。

 that's1 over square root of pi n， and then what's left is E to the minus k squared over n。So。

1 over 4 n2 inches choose n minus k is e to the minus k squared of red over squared of pi n。

 and that's the normal approximation to the binomial distribution and that's accurate for a broad range of values of k。

 it's only for this approximation it's only when k gets a bigger than n of the three4 that the approximation doesn't work and again remembering from the curves when k is that big we can use independent means to prove that the terms are very。

 very small。So there's certainly a lot of math on this slide， on the other hand。

 the bottom line is a fundamental classical result in mathematics and techniques use what makes it complicated is really just elementary algebra。

 so it's an exercises in doing elementary algebra well。

 and it's interesting these kinds of calculations still nowadays most people do them by hand because it's difficult to have automatic calculations carry through on the bivariate to the extent that would like say。

So lots of people still do these kinds of calculations by hand。

And there's plenty of other examples in the book， and so I'm not going to go through all those examples again。

 these functions arise very often and we can go back to a table like this to get the approximations that we need later on when we encounter these functions in applications。

So again， different arguments， depending on different ranges of k， in most cases， will have a。嗯。

An approximation that's true no matter what the value of k is。

 and then other times we'll have a more refined approximation that will give us a little more accuracy for near the center so that's the end result for the normal distribution then there's a so-called Poisson distribution which I haven't talked about very much but which falls to the very same kinds of techniques and I'll talk about it when we come to it in the context of applications and again look at the derivation in the book you can just deal with that by using the X blog trick a lot of things cancel and the end result is a famous result that for。

Into that inches k times that binomial for a probability that's got a small chance of occurring this lambda a K E minus lambda K factorial and we'll talk about applications of that later on right now just in terms of the math。

 she should appreciate that the very same technique that we did on one slide will give this kind of these kinds of approximations。

In the Q distribution that I talked about e to the minus k squared over n to within one over squared of n uniform or more accurately near the center。

 those are the kinds of bivariate approximations that we can develop and they're extremely important in not just analysis of algorithms。

 but in many applications， it's far easier to work with the standard mathematical functions like e to the minus k squared over n。

 than it is to work with the factorial representations which are exact but carry a lot of information that make calculations difficult。

So most of the time， we'll be coming back to this table and picking out these kinds of approximations when these sorts of functions arise in the analysis of algorithms。

 and we have similar functions that arise will go back to the derivations and see that they can be handled with the same basic method really the X log technique plus application as Sterling's formula is what gives all these kinds of results。

So the next challenge that we're going to have now is， though。

 what do we have when we have a sum that involves one of these functions？

And so the example that we'll do is the so called Ramanun Q function。

 and that's a critically important function in the analysis of algorithms。

So it's the ramanusian distribution summed over all values of k。

 and it's basically asking what's the area under the curve。

And the challenge is that we're going to need again。

 it's nearly one for small K and it's negligible for large K。

 so we're going to need to use different approximations in different parts of the range to get the answer This is a very typical situation so that's why we need by varied asymptotics to make sure that we can have good estimates in the whole range that we can use to estimate the sum。

The general method is referred to as the Laplace method if you have to approximate a sum and this is just a schematic representation of the situation what usually winds up being effective is that the tails are going to be small so we'll restrict the range to an area that has what counts and then find an approximation that works there and then what we can do is extend the range。

 so rather than the point is that that approximation usually is also going to be very small on the tails so we can just extend the range back out so we take out the original tails that we put in the approximation and we use both of them are exponentially small by comparison with the value of the whole sums。

ItDoes't matter which one that we use and then that gives us a way to get a concise approximation of the whole sum。

 that's called the Laplace method。And then usually one of the advantages of converting from representation involving factorials to a representation like e to the minus K squared over n is that we can use an integral for functions like that and then use that approximation to get the answer where integral with discrete doesn't do the job force us usually。

 so let's look at how this method works for the Q function。

And it's actually very straightforward so what we're going to do is just pick a value K0 and split into two parts for values less than K0 and values bigger than k0 remember for small k is where it's significant for large k it's going to be negligible。

And going from the approximations that we developed before， for example。

 if you take K0 to be like n to the two thirds， then the tail is going to be exponentially small。

 and I won't do the detail of that。And then for the tails exponentially small and not only that。

 we have a good approximation of the sum man for k less than k0 for all of those values。

 it's not far from e to the minus k squared over 2 n。

 that's the approximation that we just developed， It's very close to that actually。

So then we can now we can just， but that one also for large k is going to be exponentially small。

 so we might as well just extend the range back to be an infinite sum because the tails also exponentially small for that one and now that sum we can just approximate with an integral and if you do that you get squared of pi in over two。

So and again， that's the true value of doing asymptotic calculations。

 this function Q of n while it's a precise description of some mathematical quantity。

 that's going to be really difficult to compute but if you know that square to pi in over2。

 then that's something that you can work with， and we'll be coming back to applications that use this function later on。

That's an introduction to bivariate asymptotics now I want to finish up by giving a few exercises that you might do before the next lecture to test your understanding of asymptotics。

So the first one has to do with where I started with is how small is exponentially small and this is just trying for a couple of different values of alpha and beta comparing the values of alpha to the n and beta the n and really showing that alpha to the n the larger one is going to be really good approximation so here's another one an opportunity to go through those calculations that I did in the last section there's another ramanugen function actually there's three famous ones。

 but there's another one called the P function it's also the r function which is discussed in the book and that's this function sum over k n minus k to the K and minus k factorial over n factorial that one also is approximated by square root to pi n over 2 going through the steps that I did for the Q function。

For this function will be very instructive if you want to test your understanding of this material。U。

So are one thing that you might do just to get started is write a program that'll print logbase2 of N choose K and just use what we've talked about in this lecture to get that done。

 that's an interesting exercise。In read of solutions to the two exercises that I just gave and again。

 if you're not comfortable with using tech either on paper or with mathjas and HTML。

 that'll certainly provide some practice， or write it up by hand。

I don't write stuff up by hand anymore， but some people do。

And then read the chapter on asymptotics in the text for much more detail on all the information we've covered in the next lecture we'll put together all the things that we've talked about in the previous lectures and see how they fit together to form the basis of analytic combatorics that we can then go on to apply to the analysis of algorithms。



![](img/f4c6cb20630b42b0beb99f85de425f7a_2.png)

![](img/f4c6cb20630b42b0beb99f85de425f7a_3.png)