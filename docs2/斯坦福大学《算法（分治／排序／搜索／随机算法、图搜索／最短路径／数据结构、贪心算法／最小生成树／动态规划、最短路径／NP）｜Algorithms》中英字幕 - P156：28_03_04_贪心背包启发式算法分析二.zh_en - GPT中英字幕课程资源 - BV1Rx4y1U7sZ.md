# 斯坦福大学《算法（分治／排序／搜索／随机算法、图搜索／最短路径／数据结构、贪心算法／最小生成树／动态规划、最短路径／NP）｜Algorithms》中英字幕 - P156：28_03_04_贪心背包启发式算法分析二.zh_en - GPT中英字幕课程资源 - BV1Rx4y1U7sZ

Here's the analysis Step one of our algorithms sorts the items in non-increasing order of value per size Step2 of our greedy heuristic picks the maximal prefix of items who fit into thenapsack let's say that maximal prefix comprises the first K items。

 the K+ first item is the first one that does not fit in the Napsack given the previous selections。

So here's the cool part。 remember we added this step 3 to our greedy algorithm so that it considered two different candidate solutions and picked the better of them。

 The first candidate solution was just the outcome of step 2。

 so therefore we can definitely say that the output of our three step greedy algorithm is at least as good as the total value of these first K items chosen in step 2。



![](img/b8248459159a62ff3c92e84b343d85a8_1.png)

The second candidate considered in step 3 of our greedy algorithm is the maximum value item all by itself。

 So one such item all by itself that would be considered by our greedy algorithm was this K plus first item。

 the item on which we got stuck in step 2。 So therefore。

 whatever the value of our output of our three step greedy algorithm is。

 it's definitely at least the value of item K plus1 in isolation。



![](img/b8248459159a62ff3c92e84b343d85a8_3.png)

So let's add these two inequalities together on the left hand side， what do we get。

 we get double the value of our three step greedy algorithm on the right hand side。

 we get the first K items and also the item K plus1 that is we get the total value of the first K plus1 items。



![](img/b8248459159a62ff3c92e84b343d85a8_5.png)

So now we're in a position to connect this inequality to the fractional greedy solution。

 So remember what is the greedy fractional solution Well it packs the first K items and then the item in which it gets stuck。

 namely item K plus1， it fills up the knapsack fully with a suitable fraction of item K plus1 and the value that the algorithm gets is prorated according to the fraction that it fits in。

 Well what we have here on the right hand side in green is even better then the greedy fractional solution。

 This is the first K plus1 items，100% of them。 the greedy fractional solution has the first K items。

100% and some fraction of item K plus1。 So the value of the fractional greedy solution is even worse than the right hand side here。

And the whole point of our thought experiment was to argue that the greedy fractionracal solution is even better than optimal。

 that has value at least as much as every feasiblenapsack solution。

Divide both sides by two and you'll see we've proved the theorem。

 the output of the three step greedy algorithm is guaranteed to be at least 50% that of an optimal solution。



![](img/b8248459159a62ff3c92e84b343d85a8_7.png)

That's cool。 We have a non trivial worst case performance guarantee for our simple and blazingly fast。

 three step greedy heuristic for thenapsack problem。

 But maybe you were hoping to do a little bit better than within 50% of an optimal solution。

 Maybe in the back of your mind， you were really rooting for something more like 90% or even better。

😊，There's a few roads we can take that might lead to better performance guarantees。

 The best case scenario is if we could just sharpen our analysis of this greedy heuristic。 That is。

 don't change the algorithm， don't make any new assumptions just have a better proof and maybe the 50% will improve to some other number。

 That would be the best case。 The second thing we could do is if we really loved this algorithm。

 For example， it being so fast。 we could try to identify additional assumptions on instances that allow us to prove better performance guarantees than this 50% guarantee。

 which holds for all instances。

![](img/b8248459159a62ff3c92e84b343d85a8_9.png)

![](img/b8248459159a62ff3c92e84b343d85a8_10.png)

The third thing we can try and do is just come up with a better algorithm that in fact has better performance guarantees so what I want to show you on this slide is that the first case。

 the best case scenario of just sharpen the analysis of this greedy algorithm is not feasible the analysis cannot be sharpened that 50% can be realized for certain instances then we'll tackle the other two approaches and we will in fact get better performance guarantees either under extra assumptions about the instances or alternatively using a more sophisticated algorithm。



![](img/b8248459159a62ff3c92e84b343d85a8_12.png)

![](img/b8248459159a62ff3c92e84b343d85a8_13.png)

So here is an example that shows that the really are NApsack instances on which this three step greedy algorithm might obtain nearly 50% of the value of an optimal solution。



![](img/b8248459159a62ff3c92e84b343d85a8_15.png)

![](img/b8248459159a62ff3c92e84b343d85a8_16.png)

In this example， we're going to set the Napsack capacity capital W to be 1000。

 There's going to be three items。 itemem 1 will have a value of 502 and a size of 501。

 The second and third items are going to be identical。 Both are going to have value 500。

 Both are going to have size 500。

![](img/b8248459159a62ff3c92e84b343d85a8_18.png)

![](img/b8248459159a62ff3c92e84b343d85a8_19.png)

So what is the greedy algorithm going to do， Well， in step 1。

 it sorts the items according to the value per size ratio。

 and you'll notice that the first item has a ratio slightly bigger than one。

 So it's going to be considered first before item 2 or 3。 In step 2 of the greedy algorithm。

 It packs item 1 in thenapsack。 That leaves only 499 units of residual capacity。

 not enough room for either item2 or item 3。 So step 2 of the greedy algorithm just outputs the first item by itself。

 Step 3 of the algorithm considers the max value item in isolation。 That， again， is item 1。

 For this reason， the greedy algorithm will output the solution。

 which is just item 1 for a value of 502。

![](img/b8248459159a62ff3c92e84b343d85a8_21.png)

![](img/b8248459159a62ff3c92e84b343d85a8_22.png)

And I'm sure you've noticed that there's a better solution。

 if yousch item1 and instead choose items two and three， they both fit in the Maps Act。

 they fill it fully for a combined value of 100， which is essentially twice as big as the value of the greedy solution。

So what does this example teach us， Well， it argues that if we want performance guarantees better than 50%。

 we have one of two options。 First， if we really want to keep analyzing our three step greedy algorithm。

 we're going to have to make extra assumptions about the instances in order to prove performance guarantees better than 50%。

 There are some instances out there where the performance is as bad as 50% of optimal。

 The second approach we can take is to look at better algorithms。

 which might have better guarantees on worse case instances。 So in the next slide。

 I'll show you a refined analysis of the three step greedy algorithm。

 conditions under which it performs much better than 50%。

 And a separate sequence of videos will develop a dynamic programmingbased heuristic。

 which is guaranteed to have much better performance on all instances。😊。



![](img/b8248459159a62ff3c92e84b343d85a8_24.png)

So there's a few different assumptions you can impose on Napsack instances that will enable you to prove better performance guarantees for greedity heuristics。

 let me just show you one that's both simple and also it's a condition that's met in many Napsack instances that arise in practice。

So let's focus on Napsack instances where no item is especially big compared to the Napsack capacity for concreteness。

 let's say that the size of every item is at most 10% of the Napsack capacity capital W。



![](img/b8248459159a62ff3c92e84b343d85a8_26.png)

As you'll see， there's nothing special about the number 10%。

 I'm just using that to keep the discussion concrete。



![](img/b8248459159a62ff3c92e84b343d85a8_28.png)

So I claim that without changing our algorithm at all。

 using exactly the same three step gry algorithm， actually we can even get away with the original two step gry algorithm。

 we can prove performance guarantees much better than 50% as long as the instant satisfies this property。

Why is this assumption useful， Well， let's think about step 2 of our greedy algorithm。

 So we've sorted the items in nonincreasing order of value per size or packing the items one at a time。

 Now， at some point， we get stuck。 there's some item K plus1。

 where if we tried to put in the Napssack， we would overflow the capacity。 Well， by assumption。

 this K plus1 item， its size is a most 10% of the original Napsack capacity。

 So if sticking in item K plus1 would cause it to overflow。

 That means there's less than 10% of the Napsack capacity currently available。

 That is the Napssack is currently 90% full or more with the items that we've already packed in so far。

So this is sounding pretty good， our greedy criterion ensures that whatever fraction of the k Napsack we wind up using。

 we're using in the most valuable possible way， and we've just noticed that this assumption on the instance implies that we use almost all of the Napsack。

To make this intuition precise， we compare the output of our greedy algorithm。

 even just after step 2 to our favorite hypothetical benchmark。

 namely the greedy fractional solution。 What's the difference between these two solutions， Well。

 they're almost the same， The only difference is that the greedy fractional solution gets to pack that last bit of annapssack。

 which we know is at most 10% with a suitable fraction of item K plus 1。

 So the value that we're missing in our solution is that final 10% at most of the greedy fractional solution。

Now， in the greedy fractional solution， the items are packed in decreasing order of bang per buck of value per size。

 So this last 10% of the greedy fractional solution is also the least important。

 It's making the least valuable use of capacity。 So this final at most 10% of the greedy fractional solution can account for at most 10% of its overall value。

 So whatever we're missing in our solution for our greedy algorithm。

 It's at most 10% of the overall value of the greedy fractional solution。

 That is we're getting at least 90% of the value of the greedy fractional solution。

And we know from our thought experiment that the greedy fractional solution is even better than optimal is at least as good as any feasible Napsack solution。

 therefore， the output of our grity algorithm， even if we don't use the third step is 90% as good as the value of an optimal solution。



![](img/b8248459159a62ff3c92e84b343d85a8_30.png)

All of this reasoning holds equally well with a number different than 10% so for example。

 if you only knew that every size was at most 20% of the knapsSack。

 then you'd get that the greedy solution would be at least 80% of optimal， on the other hand。

 if you knew that every item had size at most 1% of the Napsack capacity。

 then just the two step greedity algorithm would get you within 99%。

