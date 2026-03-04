# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P152：-152-Red-Black Set Performance Chap8 Video 36.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

Let's review what we've learned about the efficiency of the red， black operations。

The mem operation runs in logarithmic time。 The worst case for it is when it has to walk down the longest path in the tree。

But because of the red black invariance， we've ensured that the length of that path is at most big O log in。

Likewise， for insert the worst cases walking down that longest path and then back up it recursively as we go。

 again， that's going to be big O login。While we're walking back up that path。

 we do rotations along the way， but each of those runs in constant time。

 so it doesn't increase the asymptotic complexity。

![](img/2958bd0d431780749f2fe50d3157ee73_1.png)

By using these more efficient red black tree operations， we get the performance that we wanted。

 both on the ascending workload and the random workload。

So this RB set implementation gets an insert and MEM performance that's totally comparable to the same performance for the random workload from BST sets。

😡，And it's about the same whether we do an ascending workload or a random workload for RB sets。

 There is a little bit of difference we're seeing here。

 and this is just experimental variation in the measurements。

 I only did three runs of this and took the media if we really wanted to get good information。

 we should do a lot of repetitions of this experiment and compute confidence intervals。

 but I hope this has been enough to convince you that by using a balanced binary tree implementation。

 we get the really good performance that we're looking for without the pathological case of some insertion orders causing our performance to completely tank。

😊。

![](img/2958bd0d431780749f2fe50d3157ee73_3.png)

![](img/2958bd0d431780749f2fe50d3157ee73_4.png)