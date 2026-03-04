# 普林斯顿大学《算法分析｜Analysis of Algorithms》中英字幕 - P16：16_04_02_展开式运算.zh_en - GPT中英字幕课程资源 - BV1YE421T7kf

![](img/fae1dfcc51d354d11bc554d32d2a8ecb_0.png)

Okay， next we'll take a look at the basic techniques that we use for manipulating asymptotic expansions to derive accurate and concise estimates of the quantities that we're trying to study。

So our goal is to develop an expansion on the standard scale for any expression that might arise in the analysis。

 and these are just examples of the kinds of expressions that might show up。

 some of them are artificial but some of them actually turn up in our analysis。

 so we saw too and choose in when studying the Catalan numbers。

And the problem with some of these like2N choose in， it might be hard to compute that。

 so imagine a 17th century mathematician trying to compute that for n equals  a000。

 that's a lot of multiplications or imagining imagine a computer programr today given them the Java computing that it's simple to define。

 but if you use the basic definition for n equals a million million factorials。

 pretty big numbers so you have to deal with it in some way。On the other hand。

 using asymptotic expansions， we're going to get all of these in a kind of coherent form where we can be confident that we can work with them。

So there's a lot of different techniques that we use and each one of them is relatively simple。

 but it's still worthwhile calling out examples of each so and we'll look at each one of these simplification。

 substitution， factoring， multiplication， division and composition。

 and it's they seem really simple to call out but on the other hand when faced with dealing with one of these functions。

 you really want to think in terms of there is an easy way to do this， one of these basic ways。

Just have to figure out which one it is。 And there also the X blog trick is an important one or technique。

 And I'll show that in a minute。So again， the whole idea is that a lot of times we have not just these quantities。

 but maybe they combine in some way， so like what's the value of one over four to the N2 and choose in。

 that's an expression that arises that's of importance in the analysis of algorithms。

 and if you ask a programmer to try to compute that for n equals 10 to the6 it's going to be a challenge and we'll actually see that it's relatively simple to express this in terms of standard functions via asymptotics and all of these functions and all of the functions that arise we we can do that。

So let's take a look at the various techniques， so the first thing is that an asymptotic series is only as good as its big O term。

So that means there's no point in carrying around smaller terms。

 if you have something that's encompassed by the big O just drop it。

 it's only going to make the calculation more complicated and it's not helpful in any way。

 so we don't write log n plus gamma plus o of1 where gamma is a constant because the O of1 says the error is bounded by some constant and so that constant might as well be gamma or whatever it's better to say that write down this expression as log n plus o of1 it's more compact。

So the other idea we already talked about was substitution where you can just change variables in a known expansion。

 so the Taylor series for log of 1 plus x is x minus x square of 2 plus x square of 3 and so forth and if we just plug in a different value for x。

 we plug in1 over n， then we get the expansion， so that's one that technique that we already used。

Facting a very common thing to do is to estimate what the leading term is then factor that out and expand the rest。

 so look at this function1 over n squared plus n。 and we think to ourselves what's this going to be close to when n is large like n is a million it's going to be close to one over n squared。

 so we might as well factor out the one over n squared and then in this case what we're left with is one over1 plus1 over n and that's a geometric series and we have asymptotic expansion for a geometric series so expand it since' one plus one over n it's one minus1 over n plus over one over n squared so and we could take that to more terms if we wanted to but that's an asymptotic expansion of that if we use that expansion it says that for n equals a million that value is going to be very close to one over n squared。

The relative error that we would make would be one over a million in that case。

 which is probably small enough for our purposes。You distribute that。

 so it's 1 over n squared minus1 over in Q plus big over over n the fourth。

That's a asymptotic series in the standard scale for one over n squared plus n， very easy to obtain。

Mulipplication， so multiplication is just algebra but also employing simplification when we have smaller terms we throw them out。

 so let's look at the square of the harmonic numbers。So we did estimate of the harmonic numbers。

 we talked about the asymptotic series for the harmonic numbers is given by approximation with a sum and I talk briefly about that。

 and we'll talk more about that kind of asymptotics later。

 so the harmonic number is approximated by log n plus gamma plus big O 1 over n。

Where gamma is orless constant 0。577 so to compute the square of the harmmonic numbers we have to square those so that's two terms with three two factors with three terms each so we're going to wind up with six factors when we add all that together so log n times each one of those log n square plus gamma log n lets big O log n over n inside big O we usually don't specify the base of the log rhythm since it only differs by a constant so it doesn't matter that it's natural log so we just write log because means it's not specified as some constant。

Then the next row is gamma times each one， gamma log n plus gamma squared plus P O of1 over n。

 and the next term is o of1 over n times all of them， o of1 over n log n。

Over n gamma times over and over n is over and over n and over and over n times over and over in。

s over and over n squared。So that gives us nine terms but we can throw a lot of them out because well first of all。

 all the big O terms you just pick the largest one。

 so big O of over n squared is much smaller than log n over n so it can be subsumed in that same with o of 1 over n。

 so all the big O terms and there's five of them get subsumed in that o of log n over n。

There's the gamma squared and then gamma log n appears twice。

 so that's an asymptotic series in the standard scale for the square of the harmonic numbers。

Now just taking a look at this series， it's important to note that there's a difference between the first couple of terms and the big O that we lost。

 so log n squared， so n is a million log n is going to be some small integer。

 so log n squared and two log n is they're not that far apart so it seems like we're going to need those and then gamma squared is a constant but log n is a small integer it's only a slight improvement in precision to carry on those terms and so we're probably going to want those terms。

But when we get it divided by n， that's when we have a huge improvement in precision。

Now you can't always tell ahead of time how far you have to go to get this big improvement。

 but in real problems usually happens after three or four terms and that's what happened here if you look at the tables of these quantities for n equals 100。

So 1000，10000 and 100，000 you can see so HN squared is the quantity that we're trying to estimate and then if you just tried to estimate it with log n squared you can see you still be off by fair amount 10% for even 100。

000 if you add the two gamma log n you come much closer and add the gamma squared actually we're accurate to three decimal places because the next term。

 the one that we're missing is going to differ it's going to be bounded by a constant times log n over n and for 100000 that's going to be out in the fourth or fifth decimal place assuming the constant small which normally we assume in these asymptotic series because they are but we can check as in this case that that's an accurate approximation so usually we'll try to。

it out long enough until we get this big improvement in precision。All right。

 division that's like multiplication， so let's look at this example。

 HN equals an natural log HN over a natural log of n plus1 so what we'll do for that is we'll expand the numerator and the denominator both and then we'll use the geometric series to expand the denominator that'll give us a multiplication problem so let's look at how that works。

So。H of N。Is。Log n plus gamma plus01 over R， that's the approximation that we've been using for each event N。

Natural log of n plus1 factor out a log n， and it becomes natural log of n plus natural log of 1 plus 1 over n natural log of 1 plus1 over n is big of 1 over n just from Taylor。

So now we have the ratio of two asymptotic series and what we'll do is factor out the log n as before。

So let's divide both numerated denominator by log n。

And so the numerator becomes one plus game over log n plus1 over n， it's over1 over n log n。

 so we're simplifying that。And then the denominator comes1 plus O of1 over n。

 We could make a one over n log n we're making it a little bit bigger。And again。

 that's just to simplify the formulas， if we did not get a sufficiently accurate estimate。

 we could go back and try to correct that。And now one plus o of1 over n。

 if you expand as a geometric series， it just becomes one plus1 over1 plus o of1 over n is1 plus o of 1 over n just as a geometric series。

 and again， if there are more terms you could carry more terms out there。

So now we have a multi problem and if we multiply that out。

 that's a proof that the asymptotic expansion of HN over log of n plus 1 to within o of 1 over n is 1 plus gamma over log n。

Plus over1 over n and again， there's a big improvement in precision when we get to the1 over n term。

 so this is going to be a very accurate estimate of that more complicated quantity as n increases。

Composition， so this is similar， so we're just going to substitute an expansion and figure out what to do so if you had to compute E to the H of n you plug in the expansion for H of n and see what you get what you get is E to the log n plus gamma plus big o of1 over n E to the log n that's n E to the gamma is e to the gamma that's a constant and then what's left is E to the big o of 1 over n and then that one you expand with Taylor。

 although it's a little more work to actually prove that but you can from now on use that lemma E to the O1 over n is 1 plus o of1 over n and then thatll and you can expand it a couple of terms if you need to and that gives the simplification that。

E to the HN is N E to the gamma to within1 over n。Or ending to the gamma plus o of one。And again。

 N E to the gamma that grows within of1 is a constant， so there's a big change in precision。

 so that's going to be a very accurate approximation for large n。

Each time that we do an asymptotic expansion， we go down to where we can usually try to go。

 where we can get a big improvement in precision like this and gives us a simple expression in terms of familiar functions for this thing where otherwise its growth might not be so obvious to see。

And again， you can see for n equals a million， this is accurate to within one。Absolute one。

 which is a fine， small relative error。Okay， X log trick。

 so this is a way to bring us in a position where we can apply the composition in more complicated scenarios and all we'll do is write F of x as E to the log of F of x and we can expand log of F of x and we can expand E to that series as we did before。

 and here's a fine example1 minus1 over n to the n。And when you see a thing like that。

 you have to think how would you compute that for that large values of n。

 ask a programmer to compute that for n equals a million， maybe not necessarily so easy to do。

 it's going to at least take time proportional to n and there might be precision problems。

 or as with factorial there might be problems in needing to carry too many digits。Well， actually。

 the way people compute things like that is use the exp trick。

 so that is we write that as E to the log of 1 minus1 over n to the n。

And so the log of1 over1 minus to the n， we can bring the n down。

 It's n times the log of 1 minus1 over n。And so now if we expand log of 1 minus1 over n， again。

 using the Tayloror series， we get minus1 over n plus big of 1 over n squared。

 and then do the algebra， that's e to the minus1 plus big of1 over n。

And again e to the o of1 over n is1 plus o of1 over n， so that's1 over e。

 it says that that function1 minus1 over n to the n is going to be very close to1 over e and again that's the big improvement in precision we always look for and again we can check that for n equals a million that's accurate to six decimal places because the big O says that the error is going to be out there around the 6 decimal place so again when we're trying to understand what the value of the quantity is if we know that it's 1 over e which is this constant 0。

367879 that's very precise and concise information as opposed to that exact expression which maybe it's hard to know what it is and when we start combining these kinds of formulas which we do all the time。

We're going to want to work with the precise and concise expressions。

So that's the X log technique and we actually use that one quite a bit。

So thinking about these various techniques， here's just a couple more examples that you might want to try doing to make sure that you understand the kinds of techniques that we're using。

So log of n over n minus2 to within1 over n squared and hn squared。

 what's that constant times the one over n term because we only got it to log n over n。

And that's just to illustrate that if desired we can go to more asymptotic accuracy。

 maybe we need to do that because we've got a function where we're multiplying that thing by n squared。

 and so we need more accuracy， just for example。So for log n minus2， what we do is factor out the n。

 so that's the leading term， and then we have log 1 minus2 over n and then just expand the rest and so it's minus2 over n plus big over of1 over n squared。

呃。So that's the solution to that one and this one is just carrying out the asymptotic approximations to one more term which is one over n squared term and then that gives the coefficient of log n over n is one and again these types of things as with any kind of mathematics they require a little bit of practice but the techniques are so simple it's not difficult to learn how to do these kinds of expansions。

 so that's a quick introduction to manipulating asymptotic expansions。



![](img/fae1dfcc51d354d11bc554d32d2a8ecb_2.png)

![](img/fae1dfcc51d354d11bc554d32d2a8ecb_3.png)