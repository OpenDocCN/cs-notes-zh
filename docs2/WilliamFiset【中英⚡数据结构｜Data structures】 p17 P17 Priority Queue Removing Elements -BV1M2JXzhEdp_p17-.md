# WilliamFiset【中英⚡数据结构｜Data structures】 p17 P17 Priority Queue Removing Elements -BV1M2JXzhEdp_p17-

Welcome back today we're going to be looking at how to remove elements from a binary heap this is part 45 in the priority Q series。

 make sure you watch the last video so we understand the underlying structure of the binary heap。



![](img/967441ea4a7ecf02fba2f964cbb88b4f_1.png)

So let's get started。In general， with heaps， we always want to remove the root value because it's the node of interest。

 It's the one the highest priority because it's the smallest or the largest value。

When we remove the root， we call it polling。A special thing about removing the root is that we don't need to search for its index。

Because in an array， implementation， it has position or index zero。So when I say pull in red。

 we have the node we want to remove and in purple is the one we're going to swap it with。

So the node in purple is always going to be the one at the end of IRA， which we also have。It's index。

So we swap them。We get rid of the one， and now。Since 10 is at the top， well。

 we're not satisfying the heap invariant， so we need to make sure that the heap invariant is satisfied。

 So we need to do what's called bubbling down now instead of bubbling up。

So what we do is we look at10 children， five and one。

 and we select the smallest and we swap with the smallest。



![](img/967441ea4a7ecf02fba2f964cbb88b4f_3.png)