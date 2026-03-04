# 普林斯顿大学《算法分析｜Analysis of Algorithms》中英字幕 - P8：08_02_04_归并排序.zh_en - GPT中英字幕课程资源 - BV1YE421T7kf

![](img/6ffb5d577c8c33106d39eb5e5dd1d631_0.png)

So as a non trivialvial and actually very important example。

 let's take a look at the analysis of merge sort， which is the prototype for the study of divide and conquer algorithms。

So as a warm up， I want to talk first about binary search。

 which is everybody's first divide and conquer algorithm。

And that's where we have assortded array and we look to see if a particular values in the array by looking at the middle。

 the value we're looking for is less than the item at the middle go left if it's greater go right and in either case divide the size of the array about N2。

 that's the code for binary search and you can find it in the algorithms book on the algorithms book site and its behavior is described by that recurrence。

 the number of compares in the worst case to find to discover that an item missing from an array of size n is going to be the size of the subarray that you look in it's going to be four of n over two so that you take n over two and it's the biggest integer less than that if it an array of size is of odd size then that'll be exact equations of even size you go down one and so just check that。

Yourourself that that is the number compares in the worst case。

 and so now we have this mathematical model and that's what we want to study。Now。

 usually we're trying to get an approximate solution or just an idea about how many compares are taken and the easy case for binary search is if the file size is exactly a power of two。

 then divides in half， then the。Part of the array that you look in is also a power of 2 so it becomes a recurrence that telescope so we'll take a sub n equals b of 2 to the n if we start with the power of 2 and then we just have a simple recurrence that telescopes that's just the substuting B of2 to the n and then that recurrence is the one that we looked at just telescopes to a sub n equals n each time you throw it a1 for n times and that means that that little n is log based2 of big n by definition。

So the number compares taken by binary search in the worst case is log basease2 of big n when n is a power of two。

And again， I can check that just by plugging into the recurrence log based two event。So now。

 but what about the general case when N is not necessarily a power of two well。

 it turns out to be an easy way to study that case and that's to develop a correspondence with binary numbers。

So let's define B sub n to be the number of bits in the binary representation of n。

So this example n is 107 and it's got seven bits in its binary representation。

 so you can check pretty easily that what you can do is just remove the rightmost bit if you remove the rightmost bit you get flu of n over 2。

And you removed one bit so that what that means is the number of bits in the binary representation of n is the number of bits of binary representation of flu N over2 plus the one bit。

 that's the same recurrence as binary search。Maybe it's a little bit easier to think about counting the number of bits in the binary representation of N than it is thinking about the binary search algorithm and so that's an easy model and then it's pretty straightforward to prove that number that number。

 the number of bits in the binary representation of n is the floor of the log based2 of n plus1。

And it's worthwhile this table and these formulas are here for you to check that math for yourself。

 to be sure that you understand how that might be the case。

 it's actually a pretty simple calculation just that the leading digit of log basedase2 of n changes at the powers of two。

 and if you just ignore the rest of it then you get floor of log basedase2 of n and then we're adding one to that and this math and that table is for you to check and prove to yourself that this is true。

So we had an algorithm， binary search， and we had an idea。

 a number of bits in the binary representation of the numbers。

 and these two are matched up through the recurrence。

And that's a warm up because now we're going to do the same thing for merge sort。

So merge sort everybody learns and I talked about it in the earlier lecture， divide the two array。

 their array into two halves， sort the two halves and then merge to put them back together。

 for simplicity will assume that the merge implementation always uses n compares and then if you do that you get this recurrence for the number it compares for the sort。

And this kind of recurrence is more complicated than the ones that we've looked at because of the appearance of the floor and ceiling functions over in the right hand side。

They're not immediately easy to deal with， and they result in some interesting effects if we're trying to come up with the formula for the answer。

 what's the value of C？We can go ahead and do our computation。

 but let's first talk about the easy case， which we already did。

 it's the same as for binary research， that is if n is the power of 2。

 then the floors and ceilings go away， floor of n over 2 ceiling of n over 2 are both equal to n over 2。

 or so if you do the same kind of thing where a sub n equals C sub n。C sub 2 to the n。

 we get this recurrence here， and that's one of the first ones we solved with a telescoping sum。

 the summation factor is 2 to the n divide by 2 to the n， and then we get the result n2 to the n。

 in terms of the original， it means that c sub cap n equals n log cap n when n is sub power 2。

But what if N is not a power of two？So that's the next question to address。

 So like there's a natural question that arises， so for quick sort。

We did the number of compares and got a very precise analysis that we could check against the performance of the algorithm。

 and it was asymptotically equal to 2 and natural log n minus this constant times n。

So one natural question is， we want to get a more accurate。

Estimate then n log n for merge sort is the number it compares for merge sort proportional to n log n plus alpha n for some constant alpha。

 and then we want to find out what alpha is in order to get the job done。

And the answer to that is no， actually， there's no constant。And that's important to， first of all。

 it invalidates a hypothesis like that。 And it's going to get in their way of us trying to。

Aly approximate the performance of merge sort and it's a prototype of what can happen in many many computer algorithms that have this same kind of characteristic so how do I know that well heres a demonstration of what goes on and this is reading why I wanted to spend the time at the beginning to motivate you to go ahead and do plots this is simply using the same structure that we use for Fibonacci and quicksort to go ahead and compute values of the merge sort recurrence？

And then the second for loop is just going through and scaling。

 it's trying to determine if there's this alpha value。 so just divide by。Subtract off the n log n。

 which is the leading term， and then it actually adds the n because to make the scale good and this is the plot that you get。

Absolutely not a constant。It's it's something that grows in a strange ascillatory factor and so computing the values and actually plotting the values。

 if you just plot the values without scaling like that。

 you might not notice this it's actually kind of small initially。

 but it's important because it means that you're not going be able to prove that there's a constant or find a value of a constant。

So plotting the values are very very helpful and if we want to characterize mathematically the performance of merge sort。

 whatever result that we have， whatever mathematical formula that we have is going to have to be able to do this。

This is a fundamental example， it's a relatively simple example that comes up over and over and over again。

 and really this kind of oscillation is something that is intrinsic in the analysis of algorithms because of the idea that we need to go down to the discrete and that means that we get stuck in this kind of oscillations all the time。

So， but I do want to talk about doing merge sort specifically in the general case because it's so important and there's a little trick involved to simplify it a little bit that again I'm not going to completely motivate but you'll see what I mean。

 so if we write down the same formula for n plus1 then we're going to have to do some math with floors and ceilings。

 so floor of n plus1 over two is the ceiling of n over two and ceiling of n plus1 over two is the floor of n over two plus1 that's just you can do a little math to convince yourself of that。

So that's what this table does。 and then once we have that。

 then we can subtract those two formulas and that gives us something but telescopes。

So little magic trickery based on the relationships between floor and ceiling with the plus ones。

 and that gives us a simpler formula to work with。So we'll just define that difference to be d sub n。

 and then that's going to be then the equation for dub n。But the that equation is a familiar one。

 that's the binary search equation。 It has a different initial value。

 So the solution is the sub n equals floor of log base n plus 2。

And then telescoping that one so that c sub n plus1 minus c sub n is equal to that and then so c sub n plus1 equals cN plus that so that immediately telescopes to give this sum and so now but what's interesting about that sum is that this thing here is the number of bits in the binary representation of k。

 so this is a proof that c sub n equals n minus1 plus the number of bits in the binary representation of all the numbers less than n。

And that's an interesting fact， here's a combinatorial way to prove the same thing。

So if S sub n is the number of bits in the binary representation of all the numbers less than n。

 then what we can do is just over on the left is all the numbers less than 15。呃。

And what we do is carve off the rightmost bit。If you carve off the rightmost bit。

 then taking every other number， you get S of flu of n over2。So it's just counting1，2。

3 up to floor of n over 2 and then the alternate bits are the ceiling of n over2。

 and then the right most bits are n minus1， so that's a combinatorial proof that the number of bits in the binary representation of all the numbers is less than n satisfies this recurrence that's the same recurrence that merge sort satisfies so that's a proof。

So a number of compares taken by merge sort is n minus1 plus number of bits in the binary representation of all the numbers less than n。

And when you think about it that number of bits in the binary representation of all the numbers less than n。

 that's going to have some kind of oscillation because when you come to powers of two。

 things are going to change， so this is just another way of looking at the number of bits in all the numbers less than n。

So in one dimension， you've got n in the width， you have floor log n plus1。

So the bits are all in a big end by floor of log n+1 box。

 but then what you can do is so that's pretty good thing but we don't have in the actual numbers we don't have those leading zeros。

 but the leading zeros have a very simple pattern， it's one plus2 plus4 plus8 and that's represented by that sum and that sum's just a geometric sum so it gives a solution。

Number of bits and all the numbers less than n without the leading zeros is you just take the square as if there's leading zeros and subtract off the leading zeros and that's an explicit solution to number compares taken by an merge sort。

 so it's that plus n minus1 and that's again we started with an algorithm。

And then we had an idea which is the binary representation of all the numbers。

 and we show that the number of compares taken by the algorithm is equal to the number of bits and binary representation。

 all the numbers less than n， and then we have an alternate way to count the number of bits。

 numbers less than n， and that gives us a complete solution。

So that's a fine formula for the number of compares in used by merge sort。

And that's a relatively simple formula that we can use to compute the value。

So that's just a summary of what we've done so far， but what about that oscillating turn？Well。

 there's another way to deal with the floor of log n。 if you write floor of log n。

 that's equal to log n itself， minus the fractional part， that's what the braces do。

If you substitute this formula into this solution for the number it compares by merge sort。

 you could split it off into three functions and that's again just algebra from this for the coefficient of n I'm sorry into two functions。

 the coefficient of n is one minus the。Fal part of log n。

 and then the other thing that you have is the2 minus log n and that those things are plotted。

 they look kind of antisymmetric but actually it doesn't cancel out what's left is that little oscillating function。

 and if you multiply that by n， you get the exact function that we plotted by four before。



![](img/6ffb5d577c8c33106d39eb5e5dd1d631_2.png)

So you can check this math and if this is also described in the book。

 but it's just an indication of the kind of challenges that we're going to face when trying to analyze algorithms where it looks like things are going fine。

 but we might be stuck with oscillation where things are just complicated because we're working on the one hand with wanting to work with familiar functions like log n。

 and on the other hand， needing to work with functions that are forced to be integer valued like the floor of log n or largest integer less than log n。

That's the analysis of merge sort。

![](img/6ffb5d577c8c33106d39eb5e5dd1d631_4.png)