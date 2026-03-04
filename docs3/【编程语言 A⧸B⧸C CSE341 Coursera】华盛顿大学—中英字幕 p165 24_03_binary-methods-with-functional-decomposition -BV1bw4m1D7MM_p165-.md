# 【编程语言 A⧸B⧸C CSE341 Coursera】华盛顿大学—中英字幕 p165 24_03_binary-methods-with-functional-decomposition -BV1bw4m1D7MM_p165-

So far our story for how to implement this twodisional grid of operations invari has been simpler than it sometimes is and in this segment I want to show you a very interesting complication that arises and that is when you have an operation that is defined over multiple arguments of the kind of data you're defining I'll show you an example in just a second and what we'll see in this segment is that functional decomposition handles this pretty well and an object oriented programming style well either have to abandon OOP or do something much more sophisticated and I'll show both of those in the next segment。

So to show the issue， let's extend our language with two more kinds of data。

 strings and rational numbers， but much more interestingly let's extend the addition operation to work over any pair of them。

 So if you add an int and an int or an inration or rational or an int it's mathematics。

 if you have a string and a string it string concatenation。

 and if it's a string in some kind of number， then we convert the number to a string and then concatenate that is just the definition of our language。

Now， if we want to do it this way， we now have another two-dimensal grid。

 It's different than the one we were talking about before， which is to implement addition。

 there are now nine cases。 it's a binary operation。

 there's a left opera end and a right opera end and you need to figure you need code for every combination of int string and rational int string and rational so in our eval function we're going to recursively evaluate the two subexpressions。

 We now have three kinds of values in our language， numbers。

 strings and rationals and addition works on all combinations of values So we call addition a binary method or binary operation because it takes two things of the where int string and rational or the possible kinds of things in general you could take any number but two is already complicated enough。



![](img/d918d163015cf3ce240e7a3ef440a789_1.png)

So from here， I'm really just going to show you this code and see how we do this in a functional program。

So here's my data type definition and you'll see compared to what we had before I've added string and rational Now we know that when we add string and rational。

 we have to go in change all of our old operations。 So I've already done that。

 let me show you that quickly before moving on to the main point。 So here's the eval operation。

 Strs are values， So you just return the expression itself。 rationals are values。

 So you just return the expression itself。 Here's the two string operation。 a string。

 let's just return the underlying string。 A rational has a numerator and a denominator and let's convert it to a string with this code here。

For it has zero， neither a string is never a zero， so we return false for a rational return zero if the numerator is0 and for no negative constants。

 remember this was this preprocessing where we got rid of all negative constants for a string we can just return the expression itself。

 it has no negative constants and for rationals I went ahead and removed any negatives in the numerator or the denominator by adding appropriate negation arguments。

 but that's really not the focus of this segment。So the focus of this segment is addition。

So up here in eval， let's look at this ad case， because as always。

 I want to recursively evaluate E1 and recursively evaluate E2。

 But now I do not want add to raise an exception。 if the results are not ints。 That's what malt does。

 look at malt。 right， Recursively evaluate。 if they're both ints。

 then build a new ant by multiplying the underlying numbers， otherwise raise an exception。

 But for add， we decided that any combination of int rational or string。

 which is the only thing that eval ever returns。 It always returns one of those three， is possible。

 And now we want to add those two things together。So I have made this a helper function just to separate it out and make clearer that we are going to use a function to define this green grid。



![](img/d918d163015cf3ce240e7a3ef440a789_3.png)

![](img/d918d163015cf3ce240e7a3ef440a789_4.png)

But you could have done it just as a nested case expression。



![](img/d918d163015cf3ce240e7a3ef440a789_6.png)

So add values up here。😡，Takes in two things， each of which might be an inter string or irrational and adds them together。

So the most natural thing to do is to pattern match on the pair so we can lay out the nine cases in string rational cross in string rational。

9 positions in our grid and just say what to do in each of them。

 It's a great use of nested pattern matching。 The type checker doesn't know that these v's couldn't be some nonvalue kind of expression。

 So I do have this10th case that raises an exception if either v1 or V2 is not some combination of in string or rational。

 Now we just break into cases。 If I have an int I and an int j， then I return int I plus j。

 that's the case we had even in the previous segment。 if I have an int in a string。

 then create a new string out of concatenating converting I to a string and S。

 And you just continue down an int in a rational， let's just make the rational。

 which is i times k plus J over K not reducing this or anything like we've done before。

 but it is a correct rational value for adding if I have a string in an int。

 then go ahead and do the appropriate concatenation。 If I have two strings through the。



![](img/d918d163015cf3ce240e7a3ef440a789_8.png)

Recatenation by the string and a rational， then do convert the rational to a string in a certain way。

And then concatenate us on the front。 Here's the interesting I want1， I want to emphasize。

 If you have a rational and an int， I could have absolutely just written here。

 Let me just paste it down， actually。This code right and it would have worked just fine。

 assuming that I didn't have wild card patterns over here。 But you know， when you're pasting code。

 there's often a better way。 I could have had a helper function for this。

 But the thing to notice about adding a rational in it。

 So you get the same result as if you add an in irrational the same one。

 It's a commutative operation to use the math word。 And what I did here。

 which is I would argue reasonable style is to say I've already covered this case in the opposite order。

 So let's just recursively call add values with V2 and V1。

 It's quite common when you have a binary operation to have lots of commutative cases。

 And I find this a convenient way to reduce the amount of code duplication or the number of cases you have to explicitly handle。

 It turns out that in this function， add values， this is the only case where I'm able to do this。

 But in other things， even things you might see on your homework。

 there are more situations where this works。And just to finish up。

 if you have a rational in a string， it's a lot like concatenating a string and irration。

 but the order matters， so you can't just treat it as commutative with this previous one。

 so for a rational in a string we do this concatenation and finally two rationals A over B and C over D。

 this is the basic arithmetic that produces the result of adding them。

So this code is functional decomposition of nine cases。

 this is our implementation of this green grid。I find this very natural。

 I find it far less awkward and cumbersome than the OOP decomposition of this same grid that we'll see in the next segment。

