# 普林斯顿大学《算法分析｜Analysis of Algorithms》中英字幕 - P6：06_02_02_裂项法.zh_en - GPT中英字幕课程资源 - BV1YE421T7kf

![](img/c6adae5224f0c2d4847c84fc8152ce69_0.png)

Okay， now we're going to talk about telescoping a recurrence。

 That's a basic technique for solving recurrences。 So let's get into general techniques for solving a recurrence。

So this type of recurrence is called a linear first order recurrence， so that means that there's。

The coefficients are constant， and there's only one term on the right hand side。

 So this is a very simple recurrence。 And what I want to show with this example is that recurrences like this always telescope to a simple sum。

So what we do is take the same equation for n -1 and apply it。

 so apply the same equation for n -1 and we did this in the middle of the quickword example before。

 so if A equals an minus1 plus n， then an minus-1 equals n 2 plus n -1。And the thing is。

 we can do the same thing。 do it just do it again。 A N minus2 has got to equal A minus3 plus n minus2。

And the idea is to keep doing that。 it's called telescoping until we get down to a0。

 So when we have a0 here， then we're left with a1， or we just throw out a1 every time we throw out a thing that's equal to the ones on the left。

 So that's a proof that a sub n is equal to a0 plus sum from1 goes from k to n of K。

So that's a solution to the recurrence。 Well， maybe it's not that helpful of recurrence because we have to know how to evaluate the sum。

In this case， the value of the sum is half n plus 1 times n， but in general。

 we might have a more complicated bit of mathematics to do。However， you evaluate the sum。

 it's easy to check that it's a solution to the recurrence。

 n plus 1 times n over 2 is equal to n times n minus1 over 2 plus n。

 we put in 2 n over2 and just add in the minus1 becomes a plus1。

So that's a quick solution and what it says is that if we have a first order linear recurrence。

 we can that's equivalent to being able to evaluate a sum。

Now the challenge is how we're going to evaluate sums and there's some elementary discrete sums that turn up that we have to be able to do and many of these are familiar so anyway we'll catalog on and in the book there's discussion of how we know these things to be true but many of these are familiar so that's the standard sum of a geometric series sum k goes from0 less than n of x to the k is 1 minus x to the n over 1 minus x and similarly arithmetic series that's the one that we just did that's another way to write that value now we use less than so less than equal so it's n times n minus1 over2 and that's the binomial coefficient and choose to。

And that's actually can be generalized to do a sum- this is the case m equals0。

 and if we generalize that to any value of M， that's the sum of a binomial on the upper coefficient is m plus1 choose M plus1。

The binomial theorem is like summing on the lower index of binommial coefficient。

 and then you can that's what x plus y to the n is equal to， so that's another sum that comes up。

Here's one that turned up for Quick sortt， that's the harmonic numbers。

 the sum of 1 over k from k goes from 1 to n is defined to be the harmonic number H of n。

 and that's a discrete sum that comes up very often in the analysis of algorithms。

And then there's more complicated ones that involve more complicated sum sumans。

 so this one's called the Vdermon convolution when you have two binomial coefficients。

 n choose k and M choose t minus k summed on the lower， if you sum those。

 you just add a across and get n plus M choose T。So those are examples of elementary discrete sums。

And maybe people are familiar with these from some math course or another。

 and we talk about some of them in the book， but really if you want to learn about how to do discrete sums。

 see canuth Vole1 or the canuth Gr Poassic book that's referenced in the text。So from this point on。

 I'm going to kind of assume at least these and maybe some others that can be easily derived from elementary analysis。

Okay， so， but still， that is not a very rich class of recurrences that we talked about how to solving with the。

The linear first order recurrence because the coefficient of AN minus1 was1。

So first example where gives us a richer class of recurrences is when this coefficient is not one。

 so here's a simple example。A sub n equals 2 a sub n minus1 plus 2 to the n。 again， with a0 equals 0。

 we always have to specify everything that should be for n greater than 0 with a0 equals 0。

So that doesn't immediately telescope， we could apply the same equation for AN minus1。

 but then we have to take care of the two and we get to complicated nested parentheses to avoid that in this case。

 what we do is just divide by two to the n。If we divide every term in this equation by 2 to the n。

 then the2 to the n becomes a1， and then we do get an equation that telescopes because the first term on the right hand side is the same as the first term on the left hand side。

 except with n replaced by n minus1。So now we can go ahead and telescope this thing and in this case every time we go down one throws out a 1。

 and so we get down to a0 after n times， so that's a proof by telescoping that a sub n over 2 to the n is equal to n。

And then just multiply by 2 to the n， and that's a proof that a spend equals n2 to the n。

So that's a solution by using a summation factor to turn a linear first order recurrence into one that telescopes。

And then again， you can check by if you don't believe the solution in should always do this。

 even if you do believe it is check that it works so if we put n2 to the n and2 n minus12 to the n minus1 plus 2 to the n。

 then do the math， that's 2 times 2 the n minus1 that's n2 to the n。

 and then we have a minus 2 the n plus 2 to the n so that checks。

So that's a solution to a recurrence with a constant first coefficient。 But now the challenge is。

 how do we find the summation factor。That turns out to be not too difficult。

 actually there's two different ways， but the main one that we're going to use is shown right here and it works even when the coefficient is not a constant but some sequence。

All we do is divide both sides by the product， xn， xn minus1， xn minus2 down to x1。

And if you look at the equation you can see on the left。

 you're going to have an over that product and over on the right。

 you're going to have an minus1 over that same product， but the Xn cancels。

 so it's the product going up to n minus-1。 So again your first term on the right is equal to your first term on the left but with n replaced by n -1。

So let's take an example of how that works， here's a more complicated recurrence where we've got a factor that's a sequence function of n that is multiplied by the An minus1 on the right。

So the factor， what we're supposed to do is just take the product of so this thing xn is n plus 1 over n 1 plus1 over n and then we do xn minus1。

 so the same thing with an n minus1， same thing with an n minus2， all the way down to1。

 which is2 times1。And if you look at this product in this case， everything cancels。

 the ends cancel and minus1 cancels all the way down to the twos canceled。

 so all thats left is the n plus1。So that says the summation factor is n plus 1。

 or to solve this recurrence， what we should do is divide both sides by n plus 1。

So if we divide both sides by n plus 1 in this case， then we have an over n plus 1 on the left。

 A minus1 over n on the right and2 over n plus1 as the term。Does that it on。

I presented this as magic in the Quick sort lecture。

 this is the same type of thing that we did for the Quick sort lecture was to take a simple recurrence and reduce it to one that telescopes by using a summation factor。

 and there's an easy formula for the summation factor。

 the cancellation maybe is magic but not that magic。So now that thing telescopes and that again。

 each time it throws out a2 over n plus 1， that's the sum of1 over k plus 1， k goes from 1 to n。

 multi by  two， so two， and then that's the harmonic numbers， and then just doing the algebra。

 that's a solution。So now we've got a method for solving any recurrence of that form。

 we do get to a sum in these examples， they've been familiar sums。

 but still that gives us a much broader class of recurrences that we know how to solve。

 still need to be able to evaluate the sums。All right。

 so just as an example and to check your understanding of this material。

 one thing you might do is take a moment to verify the solution for that example。

 so that's the recurrence and then what you want to do is plug in the solution given on the previous slide to see if it works。

It just involves a little bit of algebra that you may not be familiar with。

 but it's worthwhile to check your understanding of these definitions by doing that。

So one thing that is good to do even before trying to do the algebra is to just do small values。

So that you know the small values or as I mentioned you could write a program to compute them。

 but if I've got a recurrence I can do the first value like a sub1 it's got to be2 and a sub2 is got to be5 just by doing the really simple math there and so over here and solution that I'm supposed to have I can check a sub1 it's supposed to be4 H2 minus1 and H2 minus1 and H2 is one plus1 half minus1 is just1 half times4 is2 so I've got it and H3 minus1 that's1 plus1 half plus1 third subtract off to1 we've got one half plus1 third six times that is3 plus two is5 got it so once I've done that I have some confidence that I've got the solution and actually with only one thing here almost then almost that does result in a proof that you've got the solution if your first few values are right。

But to really have a proof what we want to do is plug in the supposed answer， AN minus1。

 which would be 2n H of n minus1 over on the left and do the computation see if you get AN and that's the little bit of algebra that's required to do that so have a solution that always verify it and the computation with harmonic numbers involves realizing that H of n plus1 equals H of n plus1 over n plus1。

 and that's where there's a little magic algebra in there to check that。All right。

 here's another exercise to test your understanding of the idea of solving a recurrence by multiplying by a summation factor and then telescoping。

So this looks like a quite similar example， and this is an exercise in the book。

 so you might take a moment to try to solve this problem。Well， if you've been。

Paying attention to the lecture so far， you know that you want to do a summation factor and the summation factor is somewhat similar to the one that I did for the quick sort like recurrence comes out to be one over n times n minus1 but actually in this case that's the hard way to solve this problem you forgot the other thing that I said we should do when faced with a recurrence and that's to do the initial values。

If you do the initial values on this， so a1 is 1， what's a2， well a2 a2 equals0。

 so cancels out the A1 thing plus 2， so 2a2 is 2， so a2 equals 1。Well。

 actually that is a proof if a2 equals1， then a3 is going to be equal to1 because just rename in to get that actually that's a proof that all the terms in this sequence are1 and if you try it with the summation factor you'll get to this same result。

 but with a lot more algebra， this thing is just another way of saying that a sub n equals1。



![](img/c6adae5224f0c2d4847c84fc8152ce69_2.png)

So that's an example， also you have to prove that， but again， that's easy。

 so that's an example or coverage of solving first order occurrences by telescoping。



![](img/c6adae5224f0c2d4847c84fc8152ce69_4.png)