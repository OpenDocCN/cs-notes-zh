# 普林斯顿大学《计算机科学：算法、理论和机器｜Computer Science： Algorithms, Theory, and Machines》中英字幕 - P3：03_02_05_插入排序.zh_en - GPT中英字幕课程资源 - BV1Ct42177Y6

![](img/1416af2f1d96677388c7d338e2fde860_0.png)

In order for binary search to be effective， we need to be able to sort the items in the white list。

 so let's begin by looking at a method for getting that done。Sorting is a very fundamental problem。

 how do we rearrange n items to put them in ascending order？In our example。

 we have these names in the white list in an array and what we want to do is rearrange them within the array so they appear in sorted order。

 that's what we need for binding research to be effective。

Sorting is a very fundamental problem with lots of applications， not just binary research。

 it's used in statistics or databases， data compression， bioinformatics， computer graphics。

 scientific computing， the number of applications of sorting is too numerous to list。In fact。

 it's been estimated that a substantial fraction of all cycles spent on all computers is devoted to sorting even today to set up for all these different types of applications。

Let's begin with the pop quiz on sorting this is something to think about it might be a job interview question。

 in fact， we've got a famous example of that next。Now， senator。

You're here at Google and I like to think of the presidency as a job interview。

Now it's hard to get a job as president， and you're going through the rigs now。

 it's also hard to get a job at Google。We have questions and we ask our candidates questions。

 and this one is from Larry Schmer。What。You guys think I'm kiddings right here。

What is the most efficient way to sort a million32 bitbit integers？Well。I'm sorry maybe no， no， no。

 no， no， I I think the bubble sort would be the wrong way to go。Come on， who told him this， okay？

I didn't see computer science we've got our spies in there。Well。W。

 let's ask a different interview question。So that was in just before the 2008 election and Senator Obama。

 I guess did fine with that interview question， people still use this interview question today。

So we're going to look at the first sorting method that we're going to look at is called insertion sort。

And here's how it works， so what we do is we consider each of the items in turn。

We bubbled them up through the array into their proper position， it's called insertion sort。

 we go down through the array， each item gets exchanged with the larger ones above it to get to its proper position you think of it as lighter than them and it bubbles up so。

Everything above the current item in this case， Carol is already in order and then once we complete this bubbling up process。

 then we've got it for the current item as well and everything below is untouched。This method。

 there's Carol going into position so this method is not exactly bubble sort。

 we don't teach bubble sort anymore because it's even slower than this method and we're going to look at better methods for sure just in this lecture but if you get the idea so let's take a look at insertion sort so here's a trace of what happened when we consider Alice Wendy moves down to make room for Alice same with Dave and Walter。

Carloos comes， Dave Walter and Wendy moved down to make room for Carlos， then Carol。

 when Aaron bubbles up and so forth。At every point we've got the part of the array that the elements that we've already considered are in order and the other parts not touched。

 so now Bob comes in that bubbles up almost all the way to the beginning again。

 think of the new key as lighter than the ones that are bigger than it bubbles up to its right level。

So that's a trace and the last one is Victor goes up just a couple of positions。

 so that's a trace of bubble sort in operation。So let's look at the Java implementation of insertion sort。

So we go through for i from 1 to n and then we're going to look at the ones that are less than I moving lower in indices so we start at J equals I as long as j is not zero。

 we decrement it and what do we do we compare the one with one lower index with our current one。

 and if it's bigger then we exchange them， where in exchange is our method for exchanging AJ minus1 AJ in the array。

If we get to the point where our current element is bigger than the one with the one index lower。

 then we're done， it's found its position。That's insertion sort， there's the exchange method。

 that's one of the earliest little computing techniques that we learn。

And so now here's the test client， which is just read all the strings on standard input and put them in an array。

 sort it using this method， and then print it out。So if we use that for our array of 16 elements。

 then it'll put them in sorted order， that's insertion sort。

Sple sorting method that is going to do this job。Now， again。We want to do empirical tests。

 we could also do a mathematical model but let's do the empirical tests again as before。

 we're going to take an array of lengthIn and 10 character strings。

 so that's using our generator and if we do 20，000， it takes a second and 40，000， it takes 4 seconds。

And we keep going eventually it's getting pretty slow for 320。

000 and our ratio is going towards four， takes four hours to sort a million names which is actually pretty fast computers today are pretty fast but four hours is a long time and again our hypothesis is going to be that the order of growth is about n squared and that confirms this and you think about the way the bubbling works for every one of the n elements it moves about halfway through the array on average so that's for each n elements。

 it moves about n over two positions so it's going to be close to n over four positions is going to be about n squared。

It's not going to scale。And if your company grows to do 10 million。

 it's going to take 10 days and Alice knows that sounds like a bad idea。

 so we need a better sorting method than insertion sort。

And that brings up just the idea of Moore's law， and I want to talk more carefully about algorithms that scale。

 so it's been true ever since the 70s that since we first had integrated circuits。

 the founder of Intel， Gordon Moore， postulated this idea that about every two years you're going to double the number of transistors in an integrated circuit。

So that means that we're going to get twice as much memory every two years because our memories are implemented in integrated circuits and our processor speed is going to double every two years those are really important implications and so one thing that I've noticed like during my career is that what that means is that if you buy a new computer and you write a program that touches every word in the computer。

 whatever it does it's going to take a few seconds and one of the first computers I use just had tens of thousands words of memory you could do10 thousands instructions per second and I'll talk about this type of computer later on it's going to take a few seconds to access every word in that computer then we got to millions in tens of millions and nowaday you have billions of words of memory but you can also execute billions of instructions per second so to get to every word in the computer is going to be a couple of seconds it doesn't matter。

What kind of computer it is roughly so what does that mean in terms of programs that we run on computers。

 that's the idea of scalability。So what you need is an algorithm that running time doubles when the problem size doubles。

The idea is when you get a new computer you can fit a problem that's twice as big so your algorithm better be able to manage that at least at scale so for example if the order growth is N problem size doubles then the running time doubles N log n also pretty close but n squared it doesn't happen we already saw according to our doubling test if the running time is quadratic than when the problem size double the running time goes up by a factor of four and even worse for N Q。

So the thing is， if you're solving the problem you're solving now and you get a faster computer。

 then you can do it in half the time， but at least if you take on a bigger problem。

 you can solve it in the same time it took you before to solve a smaller problem and that's really progress。

If you have an algorithm that scales。If you have a quadratic algorithm or worse。

 an algorithm that doesn't scale， then you can still solve the problems you're solving now in half the time your computer's twice is fast after all。

 but if you take on a bigger problem because you have more memory。

 it's going to take you twice as long to solve it and that immediately leads to frustration。

And so we got you have to have algorithms that scale if you want to keep pace with Moore's law。

 and that comes up in application after application in sortings the first example。

 so what we're looking for is a sorting algorithm that scales that runs in time proportional to n log N。

 not quadratic time like insertion sort。

![](img/1416af2f1d96677388c7d338e2fde860_2.png)

![](img/1416af2f1d96677388c7d338e2fde860_3.png)