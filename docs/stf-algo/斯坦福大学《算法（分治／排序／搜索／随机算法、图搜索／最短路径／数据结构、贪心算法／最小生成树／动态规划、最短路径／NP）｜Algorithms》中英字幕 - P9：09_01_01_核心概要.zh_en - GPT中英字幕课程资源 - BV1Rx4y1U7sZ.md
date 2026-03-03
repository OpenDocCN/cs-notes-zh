# 斯坦福大学《算法（分治／排序／搜索／随机算法、图搜索／最短路径／数据结构、贪心算法／最小生成树／动态规划、最短路径／NP）｜Algorithms》中英字幕 - P9：09_01_01_核心概要.zh_en - GPT中英字幕课程资源 - BV1Rx4y1U7sZ

![](img/604ae55f2971eebb83307bc68cd388be_0.png)

In this sequence of lectures， we're going to learn asymptotic analysis。

 This is the language by which every serious computer programmer and computer scientist discusses the high levelvel performance of computer algorithms。

 As such， its a totally crucial topic。 In this video。

 the plan is to segue between the high levelvel discussion you've already seen in the course introduction。

 and the mathematical formalism， which we're going to start developing in the next video。

 before getting into that mathematical formalism。 however。

 I want to make sure that the topic is well motivated that you have solid intuition for what it's trying to accomplish。

 and also that you've seen a couple simple intuitive examples。 Let's get started。

Asymptotic analysis provides basic vocabulary for discussing the design and analysis of algorithms。

 and while it is a mathematical concept， it is by no means math for math's sake。

 you will very frequently hear serious programmers saying that such and such code runs an O of N time or such and such other code runs an O of n squared time it's important you know what programmers mean when they make statements like that。

The reason this vocabulary is so ubiquitous is that it identifies a sweet spot for discussing the high levelvel performance of algorithms What I mean by that is it is on the one hand。

 coarse enough to suppress all of the details that you want to ignore。

 details that depend on the choice of architecture， the choice of programming language。

 the choice of compiler， and so on。

![](img/604ae55f2971eebb83307bc68cd388be_2.png)

![](img/604ae55f2971eebb83307bc68cd388be_3.png)

![](img/604ae55f2971eebb83307bc68cd388be_4.png)

On the other hand， it's sharp enough to be useful in particular。

 to make predictive comparisons between different high level algorithmic approaches to solving a common problem。

 This is going to be especially true for large inputs。 And remember， as we discussed， in some sense。

 large inputs are the interesting ones。 Those are the ones for which we need algorithmic ingenuity。

 For example， asymptotic analysis will allow us to differentiate between better and worse approaches to sorting。

 better and worse approaches to multiplying two integers and so on。



![](img/604ae55f2971eebb83307bc68cd388be_6.png)

Now， most serious programmers， if you ask them， what's the deal with asymptotic analysis anyways。

 they'll tell you reasonably that the main point is to suppress both leading constant factors and lower order terms。



![](img/604ae55f2971eebb83307bc68cd388be_8.png)

Now， as we'll see， there's more asymptotic analysis than just to these seven words here。

 but long term10 years from now， if you only remember seven words about asymptotic analysis。

 I'll be reasonably happy if these are the seven words that you remember。



![](img/604ae55f2971eebb83307bc68cd388be_10.png)

![](img/604ae55f2971eebb83307bc68cd388be_11.png)

So how do we justify adopting a formalism， which essentially， by definition。

 suppresses constant factors in lower order terms， where lower order terms， basically， by definition。

 become increasingly irrelevant as you focus on large inputs， which。

 as we've argued are the interesting inputs， the ones where algorithmic ingenuity is important。

 As far as constant factors， these are going to be highly dependent on the details of the environment。

 The compiler， the language and so on。 So if we want to ignore those details。

 it makes sense to have a formalism， which doesn't focus onduly on leading constant factors。



![](img/604ae55f2971eebb83307bc68cd388be_13.png)

Here's an example。 remember when we analyzed the merge sort algorithm。

 we gave an upper bound on its running time that was 6 times n log n plus 6 n。

 or n was the input length。 the number of numbers in the input array。

 So the lower order term here is the 6 n that's growing more slowly than n log n。

 So we just dropped that and then the leading constant factor is the6。 So we suppress that as well。

 after those two suppressions were left with a much simpler expression n log n。

The terminology would then be to say that the running time of merge sort is big O of n log n。

 so in other words， when you say that an algorithm's running time is big O of some function。

 what you mean is that after you've dropped the lower order terms and suppressed the leading constant factor。

 you're left with the function F of n intuitively that is what bigO notation means。



![](img/604ae55f2971eebb83307bc68cd388be_15.png)

So to be clear， I am certainly not asserting that constant factors never matter when you're designing and analyzing algorithms rather。

 I'm just saying that when you think about highlevel algorithmic approaches when you might want to make a comparison between fundamentally different ways of solving a problem。

 asymptotic analysis is often the right tool for giving you guidance about which one is going to perform better。

 especially on reasonably large inputs， Now， once you've committed to a particular algorithmic solution to a problem。

 of course， you might want to then work harder to improve the leading constant factor。

 perhaps even to improve the lower order terms。😡，By all means。

 if the future of your startup depends on how efficiently you implement some particular set of lines of code。

 have added it， make it as fast as you can。In the rest of this video I want to go through four very simple examples in fact these examples are so simple。

 if you have any experience with big O notation， you're probably better off just skipping the rest of this video and moving on to the mathematical formalism that we begin in the next video。

 but if you've never seen it before， I hope these simple examples will get you oriented。

So let's begin with a very basic problem， searching an array for a given integer。



![](img/604ae55f2971eebb83307bc68cd388be_17.png)

Let's analyze the straightforward algorithm for this problem。

 where we just do a linear scan through the array， checking each entry to see if it is the desired inte or T。

That is the code just checks each array entry in turn， if it ever finds the imageteger T。

 it returns true， if it falls off the end of the array without finding it。

 it returns false So what do you think we haven't formally defined Big notation。

 but I've given you an intuitive description what would you say is the running time of this algorithm as a function of the length of the array capital A。



![](img/604ae55f2971eebb83307bc68cd388be_19.png)

![](img/604ae55f2971eebb83307bc68cd388be_20.png)

![](img/604ae55f2971eebb83307bc68cd388be_21.png)

So the answer I'm looking for is C， big O of n， or equivalently we would say that the running time of this algorithm is linear in the input length n。

Why is that true， Well， let's think about how many operations this piece of code is going to execute。

Actually， the lines of code executed is going to depend on the input。

 It depends on whether or not the target T is contained in the array A and if so。

 where in the array A it lies， But in the worst case。

 this code will do an unsuccessful search T will not be in the array and the code will scan through the entire array A and return false。

 the number of operations then is a constant， there's some initial setup。

 perhaps and maybe it's an operation to return this final boolean value。

 but outside of that constant， which will get suppressed in the big O notation。

 it does a constant number of operations per entry in the array。

 and you could argue about what the constant is if it's2，3，4 operations per entry in the array。

 But the point is whatever that constant is2，3 or4。

 it gets conveniently suppressed by the big O notation。 So as a result。

 the total number of operations will be linear in n and so the big O notation will just be O of n。

So that was the first example in the last three examples I want to look at different ways that we could have two loops。

 and in this example I want to think about one loop followed by another， so two loops in sequence。



![](img/604ae55f2971eebb83307bc68cd388be_23.png)

I want to study almost the same problem as the previous one where now we're just given two arrays。

 capital A and capital B。 let's say both of the same length N。

 and we want to know whether the target T is in either one of them。 Again。

 we'll look at the straightforward algorithm where we just search through A。

 and if we fail to find T and A， we search through B。 if we don't find T and D either。

 then we have to return false。

![](img/604ae55f2971eebb83307bc68cd388be_25.png)

So the question then is exactly the same as last time， given this new longer piece of code。

 what in big O notation is its running time？

![](img/604ae55f2971eebb83307bc68cd388be_27.png)

![](img/604ae55f2971eebb83307bc68cd388be_28.png)

Well， the question was the same。 And in this case， the answer was the same。 So this algorithm。

 just like the last one has running time big O of n。 If we actually count the number of operations。

 of course， it won't be exactly the same as last time。 it'll be roughly twice as many operations。

 as the previous piece of code。 That's because we have to search two different arrays each of linked n。

 So whatever work we did before， we now do it twice as many times。 Of course， that too。

 being a constant independent of the input length n is going to get suppressed once we passed bigO notation。

 So this， like the previous algorithm is a linear time algorithm， it has running time big O of n。

Let's look at a more interesting example of two loops。

 where rather than processing each loop in sequence， they're going to be nested in particular。

 let's look at the problem of searching whether two given input arrays each of linked n contain a common number。



![](img/604ae55f2971eebb83307bc68cd388be_30.png)

![](img/604ae55f2971eebb83307bc68cd388be_31.png)

The code that we're going to look at for solving this problem is the most straightforward one you can imagine where we just compare all possibilities。

 so for each index I into the array A， each index J into the array B。

 we just see if AI is the same number as BJ， if it is， we return true。

 if we exhaust all of the possibilities without ever finding equal elements。

 then we're safe in returning false。The question， of course， is in terms of biggo notation。

 asymptotic analysis as a function of the array length n what is the running time of this piece of code？



![](img/604ae55f2971eebb83307bc68cd388be_33.png)

So this time the answer has changed for this piece of code， the running time is not big O of n。

 but it is big O of n squared， so we might also call this a quadratic time algorithm because the running time is quadratic in the input length n So this is one of those kinds of algorithms where if you double the input length then the running time of the algorithm will go up by a factor of4 rather than by a factor of2 like in the previous two pieces of code So why is this。

 Why does it have quadratic running time big O of n squared。 Well again。

 there's some constant setup cost which gets suppressed in the big O notation again。

 for each fixed choice of an entry I into array A and an index j for array B for each fixed choice of I and J we only do a constant number of operations the particular constants are relevant because it gets suppressed in the big O notation What's difference is that there's a total of n squared iterations of this double four loop and the first example we only had n iterations of a single。

F loop in our second example， because one for loop completed before the second one began。

 we had only two n iterations overall here for each of the n iterations of the outer for loop。

 we do n iterations of the inner for loop so that gives us the n times n i。

e n squared total iterations so that's going to be the running time of this piece of code。

Let's wrap up with one final example， it will again be nested for loops。

 but this time we're going to be looking for duplicates in a single array A。

 rather than needing to compare two distinct arrays A and B。



![](img/604ae55f2971eebb83307bc68cd388be_35.png)

![](img/604ae55f2971eebb83307bc68cd388be_36.png)

![](img/604ae55f2971eebb83307bc68cd388be_37.png)

So here's the piece of code we're going to analyze for solving this problem for detecting whether or not the input array A has duplicate entries。

 There's only two small differences relative to the code that we went through on the previous slide when we had two different arrays the first the first change won't surprise you at all。

 which is instead of referencing the array B I change that B to an A so I'm just going to compare the I entry of a with the j entry of a the second change is a little bit more subtle。

 which is I changed the inner for loop so that the index J begins at I plus1 where I is the current value of the outer for loops index rather than starting at the index1 I could have had it started the index1 that would still be correct but it would be wasteful and you should think about y if we started the inner for loops index at1 then this code would actually compare each distinct pair of elements of a to each other twice which of course is silly you only need to compare two different elements of a to each other once to know whether they're equal or not。



![](img/604ae55f2971eebb83307bc68cd388be_39.png)

So this is the piece of code， the question is the same as it always is。

 what in terms of Big O notation and the input linked N is the running time of this piece of code？



![](img/604ae55f2971eebb83307bc68cd388be_41.png)

![](img/604ae55f2971eebb83307bc68cd388be_42.png)

So the answer to this question， same as the last one big O of n squared。

 That is this piece of code is also has quadratic running time。

 So what I hope was clear was that you know whatever the running time of this piece of code is it's proportional to the number of iterations of this double for loop like in all the examples we do constant work per iteration。

 we don't care about the constant it gets suppressed by the big O notation So all we got to do is figure out how many iterations there are of this double for loop。

My claim is that there's roughly n squared over two iterations of this double for loop。

 There's a couple ways to see that。 Inally， we discussed how the difference between this code and the previous one is that instead of counting something twice we're counting at once So that saves us a factor of two in the number of iterations。

 Of course， this one half factor gets suppressed by the big O notation anyways。

 So the big O running time doesn't change。 a different argument would just say。

 you know how many there's one iteration for every distinct choice of I andJ of indices between1 and n and a simple counting argument says that there's n choose 2 such choices of distinct I andJ or n choose 2 is the number n times n 1 over2。

 And again， suppressing lower order terms in the constant factor。

 we still get a quadratic dependence on the length of the input array A。

So that wraps up some of the sort of just simple basic examples， I hope this gets you oriented。

 you have a strong intuitive sense for what Big O notation is trying to accomplish and how it's defined mathematically。

 let's now move on to both the mathematical development and some more interesting algorithms。

