# 普林斯顿大学《算法分析｜Analysis of Algorithms》中英字幕 - P37：37_09_01_词.zh_en - GPT中英字幕课程资源 - BV1YE421T7kf

![](img/baa51a642bf311de4f2d53b067244d5c_0.png)

Today we're going to talk about words and mappings。

 this is an appropriate area in which to finish our study because it ties together many of the things that we've talked about before。

Again， this is the last of the second half of the class and what we're talking about today mostly labeled objects so we'll be working exponential generating functions and again。

 as I've been saying each week there's many more examples in the book than we're able to do in lecture but we'll consider some techniques from analytic combinatorics in applications to the analysis of algorithms。

So to start out， I'm going to talk about what we mean by what is a word in a combinatorial sense。

And to do that， let's just review a few of the related combinatorial objects that we've looked at。

 so for example we looked at again how many binary strings within bits it seems we talk about this almost every lecture。

So a string is a sequence of zero bits and1 bits and with the symbolic method using ordinary generating functions。

 we show that it's2 to theN。Now that can extend to how many strings drawn from an M character alphabet。

Then in that case， it's a sequence of one of the M characters， which is 1 over 1 minus Mz。

 so again that gives us M to the n， is the number of strings drawn from air alpha with that as end characters。

So how's that related to words， well we'll get there。

 let's look at a labeled objects now and let's say how many sets labeled sets are there of size n？

So there's exactly one labeled set of size2， the one that's got two objects in it。

 and actually if any size n， there's only one labeled set。

This is just a little bit of review of what we mean by labeled objects。

we don't consider the order significant， so there's only one set and we label all the objects。

Now if you want to take ordered pairs of labeled sets of n objects then what do you get well for two objects you can have a one and then a two or two and then a one or you can have an empty set in two objects or two objects in an empty set in this case the ordering of the sets is a significant and then the labeled objects can fall in sets in these different ways。

 and so there's eight different ordered pairs of labeled sets of n objects and then you can see the answer is two to the n。

And that's the same as the number of bit strings and we'll see how that relationship comes through in just a minute。

So what about instead of pairs， what if we have a sequence of M sets。

 how many sequences of length M of labeled sets of n objects are there。

 and we use the word earn to talk about a set， it's a thing that can hold labeled objects。

So thinking of it that way， a classical way to think of it is as balls and urns。

 so really what we're talking about is the number of different ways to throw in balls into two urns。

So if there's one ball it can go，' two urns， one ball it can go into either one of them。

 there's two balls， it can either both can go in the first or both can go in the second or they can go in the two orders。

 the labels on the balls are significant， but not the order of the labels within the urn。

 we put them in the order they went in but that order is not significant and again there's eight ways to throw three balls into two urns。

So that's a balls and urns way of looking at really the same combinatorial structure。So again。

 two to the end。So。Now let's look at how we get at these counting results from the symbolic method and this is just a review of what we talked about in lecture5。

 if we have combinatorial classes of labeled objects then we have these basic operations that we can perform on the classes。

 that disjoint copies or taking ordered pairs relabeling in all ways and then the corresponding operations on the exponential generating function give us a symbolic transfer from the construction right to the generating function。

And for labeled objects， we extend that to sequences of length K or sequences of any length。

 giving those transformations on the generating function or for sets where we divide by K factorial。

 so a set of objects from a class， the generating function for that is E to the generating function of the class。

And also cycles so these are the basic operations that we use for labeled objects and so these are the ones that we're going to use now to look at balls and urns problems or wordss。

So combinatorially we're going to define a word to be a sequence of m urns that have n objects and it's the number of ways to throw n balls into MEns it's a number it's a configuration of throwing n balls into mEns。

 so we're going to know how many different words there are than we use generating functions。

 it's parameterized by M so that's the number of urns in the sequence。

So the generating function is the sum of all possible。Ojects。

 that's configurations the way the ball could fall Z to the object size over W factorial。

 and then as usual that collects it together to get us the number of ways that we could get n balls into MEns。

So and again we have all these different ways of looking at it。

 so this is nine balls into five urns and maybe this is one way it could come out。

 that corresponds to a sequence of five subsets of nine things。

 or we could just write out the subsets， those are all different ways of representing the same combinatorial object。

But in terms of the symbolic method to find out this generating function or how many different ways there' how to do this。

 it's simple， it's a sequence of length M set of objects， and it's nothing more than that。

 so that means immediately the generating function equation is E to the Z to the m power or E to the Mz。

 and so our number of different configurations is n factorial times the coefficient of z to the n in that。

 which is just m to the n。Now that m to the n again。

 that's the same as the number of strings from an alphabet of like M within n characters in it。

 and indeed there's a one to one correspondence between words and strings。

 so a string as we talked about last time a sequence of n characters drawn from an M character alphabet。

 and since for each of the n characters in the string， there's M different possibilities。

 there's M to the n different strings。A word is a sequence of labeled sets with a total of n objects。

 and there's m to the n words。So what's the correspondence well the correspondence is quite simple what we do is we take a look at。

The second set， for example， corresponds to the positions in the string where the second character happens that's as simple as that there's no three so the third set is empty the one is in position7 so the first set has seven in it and the fives or positions five。

6 and9 in a four is are position  two and4 so it's just a one to one correspondence where the word tells us the position in the string where the character happens that is for。

In the word， if you look at the K set for every I in the word， the Ithe character in the string is K。

 or vice versa， if you look at the string， if the Ithe character in the string is K。

 then you put I into the case set in the word。So the word is just the indices where the letter appears in the string。

 that's the correspondence。So it's very familiar we worked with strings before and now we're going to be working with words and we have this one to one correspondence so this is just another way looking at it for binary strings so looking at the eight binary strings as words first one says that all three characters are zeros and there's no ones and the last one says there's no zeros and all three characters are one and so forth so what's the difference there's no difference it's only the point of view last lecture when we're looking at strings we were concerned about the sequence of characters and about the relationships between one and the next in the sequence looking for patterns in the string and so forth。

This time we're interested in applications where the sets of indices are important。

 where it matters how many zeros there are， how many ones there are， and so forth。

 but really it's the same object。And strings， we're using OGFs to enumerate words。

 we're going to use EGFs， so that's a difference in point of view and a difference in technique that we use to analyze variations。

So again， here's just a summary for strings which we considered last time。

 consider them as unlabeled objects we used OGF to enumerate them a typical string is just a sequence of characters。

 so the OGF is 1 over1 minus Mz if there's M characters， those m to the an。



![](img/baa51a642bf311de4f2d53b067244d5c_2.png)

For words， we consider them as labeled objects and use an EGF and we had all these different representations and now when we're doing sequence we're doing star product where we relabel in all possible ways and our number of different words is E to the MZ。

 but we get the same result out。So we're going to be focusing on the balls and hers kind of representation in this lecture。

Now that's a brief introduction to what is a word combinatorialily。



![](img/baa51a642bf311de4f2d53b067244d5c_4.png)