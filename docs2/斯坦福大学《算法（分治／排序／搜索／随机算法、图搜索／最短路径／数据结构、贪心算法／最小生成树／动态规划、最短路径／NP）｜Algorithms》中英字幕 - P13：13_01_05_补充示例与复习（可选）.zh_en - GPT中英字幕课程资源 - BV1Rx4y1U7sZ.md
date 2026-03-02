# 斯坦福大学《算法（分治／排序／搜索／随机算法、图搜索／最短路径／数据结构、贪心算法／最小生成树／动态规划、最短路径／NP）｜Algorithms》中英字幕 - P13：13_01_05_补充示例与复习（可选）.zh_en - GPT中英字幕课程资源 - BV1Rx4y1U7sZ

This video is for those of you who want some additional practice with asymptotic notation。

 and we' to go through three additional optional examples。 Let's start with the first one。

So the point of this first example is to show how to formally prove that one function is big of another so the function that I want to work with。



![](img/de12ee7807ed05e25d0fae79dd3e3f82_1.png)

Is two raised to the n plus 10。Okay so it's the two to the n function that you're all familiar with。

 but're going to shift it by 10。And the claim is that this function is big O of2 to the n。

 So without the 10。 So how would one prove such a claim， Well。

 let's go back to the definition of what it means for one function to be big O of another。

 What we have to prove is we need to show that there exists two constants。

Such that for all sufficiently large n， meaning n bigger than and not。Our left hand side。

 so the function to the n plus 10 is bounded above by the constant multiple C times the function on the right hand side to the n。

Right， so for all sufficiently large N， the function is bounded above by a constant multiple of 2 to the n。

 So unlike the first basic example where I just pulled the two constants out of a hat。

 let's actually start the proof and see how you reverse engineer the suitable choice of these two constants。

So what a proof would look like， it would start with two to the n plus 10 on the left hand side and then there'd be a chain of inequalities terminating in the C times 2 to the n。

 so let's just go ahead and start such a proof and see what we might do。

So if we start with two to the n plus 10 on the left hand side， what would our first step look like。

 well this 10s really annoying so it makes sense to separate it out so you could write2 to the n plus 10 is the product of two terms。

 two to the 10 and then the two to the n， also known as just 1024。Times 2 to the n。

And now we're in looking in really good shape， so if you look at where we are so far and where we want to get to。

 it seems like we should be choosing our constant C to be 1，024。

So if we choose C to be 1024 and we don't have to be clever within not。

 we can just set that equal to one， then indeed star holds。So the desired inequality。

And remember to prove that one function is big over of another。

 all you got to do is come up with one pair of constants that' works。

 and we've just reverse engineered it， just choosing the constant C to be 1024 and not to be one works。

 so this proves that 2 to the n plus 10 is big O of 2 to the n。Next。

 let's turn to another non example of a function which is not big of another。

And so this will look superficially similar to the previous one。

 instead of taking adding 10 in the exponent of the function 2 to the end。

 I'm going to multiply by 10 in the exponent。And the claim is if you multiply by 10 in the exponent。

 then this is not the same asymptically as2 to the n。So once again。

 usually the way you prove that one thing is not big of another is by contradiction。

So we're going to assume the contrary that2 to the 10 n is in fact big O of 2 to the n。

 what would it mean if that were true， well by the definition of big O notation。

 that would mean they are constant C and and not so that for all large n2 to the 10 n is bounded above by c times 2 to the n。

So to complete the proof， what we have to do is go from this assumption and derive something which is obviously false。

 but that's easy to do just by canceling this two to the n term from both sides。

So if we divide both sides by2 to the n， which is a positive number since n is positive。

 what we find would be a logical consequence of our assumption would be that two rays to the9 n is bounded above by some fixed constant C for all n at least and knot。

But this inequality， of course， is certainly false， The right hand side is some fixed constant。

 independent of n， the left hand side is going to infinity as n grows large。

 so there's no way that the synality holds for arbitrarily large n。

So that concludes the proof by contradiction， this means our assumption was not the case。

 and indeed it is not the case that two of the tenon is big O of2 to the n。



![](img/de12ee7807ed05e25d0fae79dd3e3f82_3.png)

So our thirded final example is a little bit more complicated than the first two it'll give us some practice using theta notation recall that while big O is analogous to saying one function is less than or equal to another。

 theta notation is in the spirit of saying one function is equal asymptotically to another so here's going to be the formal claim we're going。



![](img/de12ee7807ed05e25d0fae79dd3e3f82_5.png)

For every pair of functions， f and G， both of these functions are defined on the positive integers。

 the claim is that it doesn't matter up to a constant factor whether we take the pointwise maximum of the two functions or whether we take the pointwise sum of the two functions。

 So let me make sure it's clear that you know what I mean by the pointwise maximum by max f and G so if we look at the two functions both functions of n maybe we have F being this green function here and we have G equal to this red function。

 then by the pointwise maximum max fg I just mean the upper envelope of these two functions。

 so that's going to be this blue function。So let's now turn to the proof of this claim that the pointwise maximum of two functions is theta of the sum of the two functions。

So let's recall what theta means formally， what it means is that the function on the left can be sandwichged between constant multiples of the function on the right。

 so we need to exhibit both the usual and not， but also two constants。

 a small one C1 and a big one C2， so that the pointwise maximum of f and G， whatever they may be。

 is wedged in between C1 and C2 times F of n plus G of n respectively。

So to see where these constant C1 and CN are going to come from。

 let's observe the following inequalities。So no matter what n is， any positive nte N。

We have the following， Supp we take of the larger of F of n and G n。

 and remember now we've fixed the value of n and it's just some integer， you know， like 23。

 and now F of n and G n are their just numbers， you know maybe they're 57 and 74 or whatever。

And if you take it the larger of F of n and G of n。

 that's certainly no more than the sum of F of n plus G of n。

Now I'm using in this inequality that F and G are positive。

 and that's something I've been assuming throughout the course so far here。

 I want to be explicit about it。 We're assuming that F andG cannot output negative numbers。

 whatever integer you feed in， you get out something positive。 Now。

 the functions we care about are things like the running time of algorithms。

 So there's really no reason for us to pollute our thinking with negative numbers。

 So we're just going to always be assuming in this class positive numbers。

 And I'm actually using it here， the right hand side is the sum of two things is bigger than just either one of the constituent sums。

 Secondly， if we double the larger。Of F of n and G of n。

Well then that's going to exceed the sum of f of n plus g of n because on the right hand side。

 we have a big number plus a small number and on the lefthand side。

 we have two copies of the big number。 so that's going to be something larger。

 Now it's going to be convenient， it's going to be more obvious what's going on if I divide both of these size by2 so that the maximum of f of n and g of n is at least half of f of n plus g of n。

 that is it's at least half of the average。 and now we're pretty much homefree。

 right So what does it say this says that for every possible n。

 the maximum is wedged between suitable multiples of the sum So one half f of n plus g of n is a lower bound on the maximum This is just the second inequality that we derived and by the first inequality that's bound and above by once times the sum and this holds no matter what n is any n at least one and this is exactly what it means to prove that one function is theta of another we've shown that for all n not just for visually large。

 but in fact for all n， the pointwise maximum of f and g。

Is wedged between suitable constant multiples of their sum and again， just to be explicit。

 the certifying choices of constants or NO equals one， the smaller constant is one half。



![](img/de12ee7807ed05e25d0fae79dd3e3f82_7.png)

The bigger constant equals one。And that completes the proof。

