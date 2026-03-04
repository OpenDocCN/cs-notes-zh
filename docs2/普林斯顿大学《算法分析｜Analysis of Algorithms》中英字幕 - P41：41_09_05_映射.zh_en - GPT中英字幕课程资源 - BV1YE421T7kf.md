# 普林斯顿大学《算法分析｜Analysis of Algorithms》中英字幕 - P41：41_09_05_映射.zh_en - GPT中英字幕课程资源 - BV1YE421T7kf

![](img/81a83ffa2651c76624f786f2e9fff7f9_0.png)

Okay， now we'll talk about mappings， which is a combinatorial structure that is related to many of the things that we studied and it really is an appropriate topic on which to close it's kind of a poster child for analytic combinators。

So what is the mapping， mapping is an inward of length n。

 so that is we've got n characters and every one of the characters can be anything from one to n。

So obviously there's in to the N， different nwards of LiIn or mappings。That seems simple enough。

 but actually there's lots of interesting instruction hidden under this。

Because the idea is that every mapping corresponds to a digraph。So that is you have。For。

Every position in the word， you make a node， so there's 37 positions and where we have 37 nodes。

 and for every node you just draw an arrow from the node to its value。

Since there's n different possible values， there's n different possible places to point so every node as out degree1 there's only one place every node can point2 that's its position in the mapping so 30 points to 18 29 points to 23 and so forth。

 but some nodes could be pointed to a lot that's the like 33 is pointed to by 4 14。

19 and 28 that appears  four times in the mapping so the sequence of numbers kind of masks this interesting combinatorial structure。

And so once you see this structure， then there's all kinds of。

 it breaks up into things that are kind of like trees。

 well they are trees that eventually go to a cycle， so it's a cycle of trees。

 but there's independent components too， so natural questions that come up is。

 well what's the probability of the thing is connected。Or。If it's not connected。

 what's the average number of connected components？

Or how many of the nodes are on cycles and how many of them are on trees。

 all these types of questions turn out to be of great interest for important applications。

But just as mathematical curiosity， it's quite a fascinating structure to get out of a simple idea like an n word。

A function from a set of integers onto itself。So in order to address those kinds of questions we'll start with something simpler called Cayleley trees。

 so a caley tree is labeled rooted， unordered tree， so labeled means all the nodes are labeled。

 rooted means that there's one distinguished root。And unordered means we don't consider the order if there's two children of a root。

 we don't consider the order of the two children to be significant。So there's nine different。

Kayley trees of three nodes。So these six are all different because of the labels and these three are all different because of the labels。

 one， two or three could be at the root， but it doesn't matter what order the subtes of the root are。

 those are called caley trees。Now， rather than。Write out all the possibilities of the short form to do this is to just write the unlabeled trees and then write all the n wordss that give those same trees。

 so for example， 112， so that's this first tree here， one points to one。

 two points to one so that's one1 and then three points to two and so forth。111， that's  one， two。

 and  three， all 。21。So that's the n word， and that's the tree structure that comes out of it for all those cases。

So that's Caylee trees。So。Now the answer is the number of cae trees。

 you might have guessed that there's a power going on， it turns out to be n to the n minus1。

 but that's not at all an elementary result， we're going to use a technique called LaGrange inversion eventually to get to this result。

That's described on the next slide。Lagrzianversion is a classic method for computing a functional inverse。

 and it's a very important indeed deep theorem， I'm not going to go into all the ramifications because we use it in in quite a straightforward way。

So for example， if I have a function f of u equals z like f of u equals u over 1 minus u。

 then the inverse of that is the function u equals G of z。

 so if I take set z equal to u over1 minus u and solve for u I get u equals z over 1 plus z。

 so that's the inverse and so Lagr'sversion is a classical method for computing this and we'll see how it applies for us。

So this is the LaGrange inversion theorem that。It in our situation will be a transfer theorem to get us from a generating function to coefficients for problems where we're counting trees。

So what it says is that if you have a generating function。And it says G of Z。

 and it satisfies this equation z equals f of G of z， so's like we want to compute the inverse。

 when mean G of z， we want to know it F。So f of 0 has to be0 and f prime of 0 has to be non0。

 then G of n equals1 over n coefficient of u to the n minus1， u over f of u to the n。

In the function U over F of U to the end。And again。

 we're just going to look at applications of this theorem， so just for our example。

If f of u is u over1 minus u。Then G sub n， so u over1 minus u， so u over f of u to the n。

 so u over f of u， the U cancel is just 1 minus u to the n。

So it says that g sub n equals1 over n coefficient of u to the n minus1 in 1 minus u to the n and just from the benomomeial theorem that's exactly minus1 to the n minus1 so that says that G is sum of minus1 to the N z to the n which is the over1 plus the which is what we got from algebra you can't always get it from algebra is the point you have to use the liangversion theorem。

So from an analytic counter ofatorque context， we're going to apply this as a transfer theorem and you'll see examples of this and we'll talk more about it in the context of complex plane in part2。

Actually， we use a more general formulation of it where。You can。

 for any function H of the generating function， you can get the coefficient of Z to the end in that。

 and it just includes an extra factor， H prime of U H of U U is the basic theorem。

So that's the LaGang and version theorem， and that's the technique that we're going to use to analyze mappings。

So now let's just before let's look at how it works for binary trees。So for binary trees。

 we have the standard construction and the OGF equation。

 so with LaGrange inversion we can extract coefficients immediately from that equation because it has the form z equals function。

So if we use f of u equals u minus u squared for Lagangian version。

 so we want to find the coefficient of z to the n and t of z， and f that minus that squared。

 so it use f of u is over u minus u squared， so we want to find u over f of u is1 over1 minus u。

 so coefficient z the n and t of z is according to the theorem1 over n coefficient u to the n minus1 and1 over1 minus u to the n。

 and that is easily shown to be the catalan numbers。

So that's an example of the application of LaGrange version。So now let's look at Kaylee trees。

So what we want is the class of labeled， rooted ordered trees， so in a word that just has one root。

And it's labeled and I'm sorry， unordered trees， we don't care about the orders。

So with the symbolic method， we just used the construction that says a tree is a root connected to a set of trees。

 the order doesn't matter so we use set。So that immediately translate to the EGF equation。

 these are labeled objects， so we use EGS， it's C of z equals z E to the C of Z。

 that's called the caley functions， one that enumerates caley trees。So in other words， Z equals。

C of z over E to the C of Z， so that's using Lagrrange inversion with F of U equals u over e to the U。

So coefficient of z to the n and c of z by the lagrangeversion of theorem， we look at u over f of u。

 which is just e to the u， u over u over e to u to the n。

 so it's the coefficient of u to the n minus1， whatever n times the coefficient u n minus1 and e to the U N。

Which is n to the n minus1 over n factorial。So the number of cae trees is n to the n minus1。

 and that checks with our small values。So that's a LaGangrangeian version to enumerate caylee trees。

Now that's just trees now we can work up to look at more complicated structures like connected components in mappings。

 remember mappings are cycles of trees so this isnt all the mappings。

 these are the ones that are just a single connected component。

 so these are all the possible things that can happen， all the possible structures。

 connected structures that you can get with three words with three mappings， so。So for example。

 we saw 111， that's or 222， so that's when they all point to the same thing。

But you can get a structure like this where。Two of them point to each other and so forth。

 so these words， so one points to two， say this is one， one points to two， two points to one。

 or this would be one。1 points to two， two points to one and three points to one that corresponds to that word。

 so these are all the ways to label and get that structure and those are connected so how many different ways are there to get cycles of caylee trees that's what a connected component is and that turns out to be into the end time screw a pi over2 in。

And the analysis of that is， again， straightforward using the symbolic method in Lagangianversion。

So this is a typical cycle of trees and clearly the construction we're going to use is cycle components。

 a cycle of trees， and then from the symbolic method， just log of1 over1 minus。

And that is immediately available for Lagangian version again we've got f of U equals u over e to the U and now our function is because that's what the Caley function does and then our extra function in the Berman form is H of U is log of 1 over1 minus U。

So that's going to immediately give that so h prime of U is 1 over 1 minus U。

 and then we still have the e to the UN that's U of Ref to the end。

 so our number of connected components is1 over encode efficient UvM minus1 in that formula。

And so just doing the convolution， it's end the k minus1 over k factorial。

And change n to n minus k and our coefficient is n factorial times that and that's our familiar ramanugen function which leads to that enumeration result。

 that's the number of connected components in mapping so the probability the component is connected is divide that by n to the n square root square root of 2 n。

Connected components and mappings comes directly from symbolic method coupled with lagGrange andversion。

And then mappings how many mappings are there， so that's going to cover all possibilities and again what's a mapping mapping is a set of cycles of Caylee trees。

 so it's going to be E to the log of 1 over1 minus CZ which is just 1 over1 minus C。

And that one we can get with the extended laggian version with our h function equals 1 over 1 minus u if you do the math。

 h prime u is 1 over 1 minus u squared， so it's coefficient of u the n minus 11 over n and1 over1 minus u squared e to the UN they do that convolution and this time the sums collapse just works out n minus k from over1 minus u squared and the k minus1 over k factorial from e to the UN。

 and then we just get two sums and they all cancel except for the last term n to the n over n factorial。

So the number of mappings is n to the end as we expected from the trivial argument。

So sure there's a trivial argument that tells us the number of mappings。

 but this analysis gives the entire structure that we can use for analyzing all sorts of properties。

 and we'll go into the details later on， just for example。

 and interesting property of these functions of something called a row length。

So the row length of a function， so if we started a given point and just apply the function。

 say you have a function like x squared plus 1 mod 99， so three goes to 10。

 10 100 plus 11101 mod 99 is 2 and that square that and go away that's5 and so forth you eventually get to a point where you hit a cycle。

 so that's called the row length the number of times that you iterate the function until it finally repeats。

呃嗯。Now so in a mapping， wherever you start you're always going to wind up in a cycle。

 so there's a row length associated with each point in the mapping and this is a mapping where we have a formula to tell us what it is。

 but random mapping you still have the same thing。WellOne thing to think about is what about an algorithm to compute the rolling it's kind of a fun problem you could say well I'll just use a symbol table I keep track of all the values I've computed and then that way I'll know when I get a repeated value but in practice you can't do that because we talk about in real applications we're doing this for huge numbers like  hundred digit numbers and there's no way you can have enough memory to keep all the possible values so what do you do well there's a famous method due to Floyd which is a tortoise and hair algorithm where you keep two variables one that iterates the function just once and the other one that iterates it twice so so for example so A and B start at the same place at time t equals zero and we iterate A by one and B by two and iterate a by1 and B by two。

And。So B is going to go around the cycle and eventually they catch up and it's not difficult to see that eventually they're always going to catch up and when they do actually the row length of starting at that point is between T and 2T if T's the number of times that you had to go to get them to match。

So that's an interesting， and that doesn't use any extra memory。

 it's just comparing those two variables。So computing the row length。So with mappings， again。

 starting at every point， you've got a row length and that's a parameter that's interesting to study in this other like tail length like。



![](img/81a83ffa2651c76624f786f2e9fff7f9_2.png)

That is how long until you hit the cycle and again， number of components， number of trees。

 and so forth。Now using the same method of construction and using bivariate exponential generating functions。

 it turns out that I'll just give an example， so like number of components is mapping is a set of cycles of trees but we mark the cycles and that'll tell us the number of components。

 this one for each cycle。So immediately we get the EGF equation， 1 over1 minus Ez to the U。

 and then we can work with that equation to answer questions like what's the average number of components？

Or if you're doing a number of trees， then it's a set of cycles of trees and then you just mark the trees and then you get this other function。

So and we'll talk about this analysis in more detail in part two。

 but for now I just want to motivate the study of mappings and it works out to be actually without that much work that we can get all these properties of mapping。

 so for example， the expected row length and a random mapping is about squared of pi N over two。

And so why is all this relevant， Well， here's an actual application where it matters。

 this is a famous method for factoring an integer， a huge integer。

And so what it's called Pollard's method and what it does is iterates a random quadratic function to find a cycle。

 so it's pretty much like the function that I just talked about we take F of x equals x squared plus C until finding a cycle and we do it like with Floyd's algorithm where we take two variables and iterate at once for one of the variables iterate it twice for the other and we use a random value of C and a random starting point and and keep going until this particular condition is satisfied having to do with the GCD and when it's done you get a factor out it's quite an amazing algorithm so this is just an example that is doing the same thing as Floyd's algorithm done and when the GCD of these things is not one then you found a factor。

So you know why does it work， well， it's actually not too difficult to see how it works if you know number theory。

 although it's definitely magic if you don't， that's not really the point of why I want to bring it up now。

 the question is how many iterations does Po's algorithm take？And well。

 one thing that seems reasonable to do is to assume that this function is not a random mapping。

 but since you're taking a random C and a random starting point。

 maybe it's got the same kind of characteristics as a random mapping and it's conjectured actually that the random quadratic function of this type is asymptotically equivalent to a random mapping。

 and in a random mapping， the row length is squared to pi n over2。So you can factor a number。

 you can factor a number n in square root of n cycles， which is。

A lot faster than trying every factor and Pollard actually used this method to factor huge integers a while ago。

 and it's typical of the kind of thing that people are trying to do in cryptography nowadays is study properties of these kinds of functions。

 andnalytic combinatorics and properties of mapping plays a role in this kind of research。

So I wanted to end with a real application like that and end with mappings。

 they are quite fascinating combinatorial structures。



![](img/81a83ffa2651c76624f786f2e9fff7f9_4.png)