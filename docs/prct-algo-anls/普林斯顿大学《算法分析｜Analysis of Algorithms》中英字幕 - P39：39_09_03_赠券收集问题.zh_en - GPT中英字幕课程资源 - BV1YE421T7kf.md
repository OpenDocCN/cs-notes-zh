# 普林斯顿大学《算法分析｜Analysis of Algorithms》中英字幕 - P39：39_09_03_赠券收集问题.zh_en - GPT中英字幕课程资源 - BV1YE421T7kf

![](img/50fe9ef5e8215585048f0f792dd94564_0.png)

Similar problems call the coupon collector problem。

So and this the same setup and the question is how many people， this is in a much bigger group。

 how many people would you have to ask before you found every day of the year？Well。

 you have to ask at least 365 and if you're lucky everybody had a different birthday， you'd be fine。

 but generally you'd have to go much more， so that corresponds to again throwing balls into urns。

And again， randomly， and then the question is how many do you have to throw in before every ur has at least one ball in it？

MOh。So呃。This one nine finally finds its way in so generally it'd be much more than the number of urns。

 the question is how long until each urn has at least one ball in it。Yeah。And this comes from。

 I don't know what the rage is lately， say baseball cards or magic cards or。

Charlie and the chocolate factory cards， how many of the different ones you have to collect before you get every possible coupon that's the same problem there's M different types and when you get one it's random。

 how many you have to get before you get them all。And there's actually plenty of practical applications where we want to know the answer of this problem as well。

I have a 20 sided die this is again just another illustration you keep rolling the die and every time you get a new value you check off the value and so how many times you're going to have to roll the die so because of the birthday problem after not too many rolls you get a repeat so not new and then after a while you start to get plenty of repeats but the question is how many times you have to roll it until you get all possible values so in this case now we're still looking for just two more possibilities finally we get the four then after 37 rolls we have all possibilities for a 20 sided die。

So in general， if given an in， how many times you have to roll you get all different M values。

 that's the coupon collector problem。Now with classical probability。

 this problem is actually not too difficult， and so I'll give the classical analysis。

 actually the analytic combinatorics is more complicated than this。

 but it's still worth doing because the classical analysis just gives the average and if you want to study variances of the problem or other properties of the distribution you're going to need the structure that we get from analytic combinatorics。

But anyway here's the classical analysis so first thing is the probability that you need more than J roles to get the K+ first coupon is k over m to the J that's a probability that the first J rolls are all the same from the same K values。

So again， just adding those up in the same way， the expected number of roles to get the k plus first coupon is just something that。

 which is1 over 1 minus k over m， which is the same as m over m minus k。

So that's for the K+ first coupon， that's the expected number of roles to get the K+ first coupon。

 and so the expected number of rolls to get all the coupons is just summing that because that's an expectation and we can sum expectations。

So some of that of m over m minus k came from 0 to M， that's just M times the harmonic numbers。

 change m to M minus k， and you get the harmonic numbers， which is asymptotic to m natural log M。

So the number， if you have M different values， the number of roles you have to do to get all of them is on average m times natural log of m。

And again， there's lots of motivation for studying this in more detail， although。

Because of there's many extensions that we want to study。

 so I'll show you how this happens with analytic combinatorics。

 although really the motivation for this is much more interesting when we look at variations later on。

So start out the same way as we did for the birthday problem。

 coupon collector sequence is an M word that has no empty set。

 or it's a string that uses all the letters in the alphabet。

So how many coupon collector sequences are there， so for example， for Ams 26。

 that's 1 uses all the letters of the alphabet， well known one。IfM equals 5， there's an example。

 so no empty sets。So again， we set it up the same way as we did before。

With using exponential generating functions， treated as a labeled set。

 so what is a coupon collector sequence？It's a we have M different letters。

 so it's a sequence of M different letters， and now our sets are have to be non empty。

 so it just has to be set of size greater than zero。

 and that immediately gives us a EGF equation that it's e to the z minus1 to the M。

So extracting coefficients， getting the coefficient of in factorial times of coefficient is z to the M and we get this complicated equation for the count sequence。

 for the number of coupon collector sequences。Now this isn't so helpful but if you go ahead and extract the coefficient as z to the n。

 you get an alternating sum， and so not necessarily so helpful。

 I mean it's asymptototic to m to the n， it's like m to the n。

 and then a smaller number to the n so asymptotically it's m to the n。

 and so all that means is if you have a long string。

 almost if you have a random string of n objects where n's bigger than m。

 almost all of them are going to use all the letters， if n is significantly bigger than M。And so。

That's not helpful what we want is what we need to do is exactly evaluate this。

So the probability that a random mor of LinkedIn is collector sequence is that。

 what I just showed and this is a little bit complicated to evaluate because of the alternating sum feature of it and again the probability that the last one is greater than n is one minus that。

 the average is the sum of those probabilities， and so that's not too difficult to simplify a little bit but it's still got this alternating characteristic and well if you have studied canoe eventually you can get the solution MHM。

 but it really is still kind of a magic solution。So this is possible to get to the end。

 but this is not， say a recommended way to get to the end for this problem。

When we look later on at generalizations and asymptotic methods in the second part of the course。

 we'll kind of see why this happens， but for the elementary derivation， this one doesn't work。

There is a way to do it with OGFs that pretty much mirrors the classical derivation。

 so if we define a WMK to be the class of M words that have K different letters with the last letter appearing only once so in this case there's three different letters and the last one appears only once。

 so then and have an OGF for those and then we can actually make a probability generating function just by evaluating that at Z over M。

And so then if you differentiate that probability generating function and evaluated z equals1。

 you get the mean wait time for k coupons， so that's pretty simple generating function manipulations and so what we'll do in the next slide is use a combinatorial construction again。

 an equation for the generating function and then perform this operation to give us a solution。

So here's the construction， so if we have M words with K different letters。

 the last letter appearing only once。So either it's。

The last letter is one of the letters that's already used， or it's a new letter。

 and that's what leads to that construction。And then that construction immediately translates to this generating function equation。

 which I won't read out。And then evaluate at C over M to get the probability generating function。

Differententiate and evaluate at one， then we get a recurrence relation for the thing that we're looking at。

 the wait time for K coupons and that leads us to the same sum that we got in the elementary derivation。

 which is going to lead to again， the end result。So definitely the classical derivation is the best way to get the average。

 but the structure here can be used to solve more complicated problems and our answer in practice is if you know how many different baseball cards there are multiply by the log of that that's how many you're going to have to look for to get every possible coupon so for  20 sided die it's about 60 or an application is maybe testing pages in a memory。

 you do it by having a program randomly access the pages maybe you want to be sure that the test hits every page then you can figure out you can take if M is a million then it's going to take you about a million times natural log of a million which is about 14。

5 million steps to test every page， that's an example of an application。In the real world。

It's a well known phenomenon that has lots of applications and that's the combininators of the coupon collector problem there is a combinatorial concept called a Sion that that does really need analytic combinators to study so what we call a coupon collector sequence is it's an M word with no empty set。

So that's called an Murgion， but there's a more general thing which is just a word that is an Murgion for some M and that appears in lots of applications so that is either it uses just one letter or it uses two letters but without leaving any out or it uses three letters without leaving any out and this is a combinatorial object that's well definedfined and easily handled with the symbolic method。

 so this is what we did for m serions， it's a sequence of non empty sets e to z minus1 to the M and we could asymptototics for that for subjections it's not a sequence of size M it's a sequence of any length so that gives one over one minus e to z minus1。



![](img/50fe9ef5e8215585048f0f792dd94564_2.png)

A set of non empty sets is e is z minus1， a sequence is1 over1 minus。

 so that's1 over 2 minus E to the z。And so how many suggestionsions are there of length n asymptotically。

 well we'll see that this is best handled with complex asymptotics。

 but it's in factorial over too long2 to the n plus1。

 so that's a classical example in combinatorics that's related to the coupon collector problem and we'll see this coming up in more detailed studies in part two。

So that's the coupon collector problem， and next we'll go on to applications in computer science。



![](img/50fe9ef5e8215585048f0f792dd94564_4.png)