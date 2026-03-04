# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P51：-051-Filter Chap4 Video 6.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

As a third example of the abstraction principle and of higher order functions。

Let's consider the task of keeping some list elements but dropping others。

 maybe you want all of the even elements from a list or maybe you want all of the odd elements from a list that's not a map because you're not keeping every element like a map would force you to。

That's not strictly a fold because you're not combining the elements together。

 you just want some but not others， so this is a different computational task。First。

 let's write functions that just directly do what we want。How about evens and odds？

And you'll notice I got so bored writing odds there that I just copied and paste of code。

 that's a good sign I should be abstracting out some common piece of functionality。Let's do that。

What we're trying to do here really is to filter out some elements of the list。

Let's call this filter。And spoilers， that is going to be the name of this function in the standard library。

Here's where we need to decide whether to keep the head element of the list。

So let's have filter taken in。A predicate。P that tells us yes or no whether to keep that element of the list。

 technically it's going to return a bo。And there you go， that's filter。

 we can reimplement evens and odds in turns of it。Actually。

 it might be a good idea just to introduce a separate function for even etO。And now we have a nice。

 simple one line easy to read implementation of eventss and odds using our higher order filter function。

Filter itself is not tail recursive。You can see that because there's extra work still to do here。

Before returning after the recursive call。We have the cons H on to the result of that。

If you wanted a tail recursive version of filter， you could build that too。

Let's try building it together。The process for building a tail recursive version of a function。

Generally works as follows first， add an accumulator argument to the function。

 that's where the result is going to be， as the name suggests。

 accumulated so that extra work isn't needed after recursive calls。

So I'll go ahead and add in an accumulator here。Second， when we get down to the base case。

 that's where we'll return the accumulator。Of course。

 we've lost the notion now that we start off with the empty list。

 so let's actually make this a helper function， I'll call it filter Oux。

Let's get that right in both places here。And filter itself。

Will be the result of filter a on the same predicate with the initial accumulator of empty on the same list。

Okay， so now the type of filter is what we're expecting to be。

 it's going to be the same as the type of filter as we wrote before because it takes in the same arguments。

 a predicate and a list， and we use this helper function to do the tailworkers of part of it。

All right， we still need to fix this piece of it though。Let's work on that。

So clearly filter O is not taking in the right arguments anymore。

 and we haven't made it tail recursive here yet either。

The L case is going to be easy to pass the accumulator to。

And we capacity pass the accumulator here as well。But we've still got this cons going on here and we definitely don't want it there。

So how can we take care of that？what's common in both the then and the else branches here is that there's a call to filter Ox PT。

On the accumulator。And if we wanted to put things into the accumulator， when would we do it？Well。

 for filter， we do it when the head element actually does。Pass the predicate。

So I could wrap this with an if expression。Now just what I'm doing is basically moving the if expression into the argument where the accumulator is。

If P holds of H， then put H in front of the accumulator。

 otherwise don't put H in front of the accumulator。

Now I think I have my arguments in slightly the wrong order at this point。

Because the recursive call on the tail of the list needs to go out there。

And this becomes the new aant。At this point I really don't need the begin and end anymore。

 I don't have a nested match or if expression。And I'm almost done。In fact。

 it might be instructive for us to run this code at this point and see the one thing that's still broken with it。



![](img/1c60d48b9e246978c48f3923147f5d97_1.png)

So our last implementation of filter is the tail recursive one。

What happens if we try to filter all the even elements out of one， two， three， four？We got four， two。

 we got the Es。But they're in reverse order。 What happened is as we discovered each even element and put it on the front of the accumulator。

 we were processing the list left to right。 so first we found two， then we found four。

But by coning them onto the accumulator， first we put two on it， then we put four on it。

 so we ended up with four in front of two。The solution to that is to reverse the accumulator。

 which is what we can do with the reverse function from the L library right there。

So this is a second time where we've talked about tail recursion and reverse has come up last time we talked about you might need to reverse a list on input before running it through a full function。

 here's kind of the opposite case after you do a computation that you've made tail recursive you might need to reverse the list as a result to make it what you expect。

Again， doesn't increase the asymptototic complexity in terms of time that's required for the function。

 it does improve the asymptotic complexity of space because they can use constant stack space instead of linear in the length of the list。



![](img/1c60d48b9e246978c48f3923147f5d97_3.png)