# WilliamFiset【中英⚡数据结构｜Data structures】 p50 P50 AVL tree removals -BV1M2JXzhEdp_p50-

Welcome back In this video。 we're going to look at how to remove elements from an AviL tree。

 And what you'll discover is that removing elements from an A VL tree is almost identical to removing elements from a regular binary search tree。

 So for the majority of this video， we're going to actually be looking at how to remove elements from a binary search tree。

 And at the very end， augment that algorithm for aviL trees specifically。 So let's get started。😊。



![](img/b39aa4e82de10f853118516361e345e2_1.png)

So just for review， I want to look at how to remove nodes。In a binaryer search tree in detail。

 so we can generally break it up into two steps， finding and replacing。In the find phase。

 you find the element you want to remove from the tree if it exists and then replace it with a successor node。

The successor note is necessary for us to maintain the binary search tree invariant。



![](img/b39aa4e82de10f853118516361e345e2_3.png)

More details on the fine phase。 This is when we're searching for the element in the tree to see if it exists。

 And basically， four things can happen。 First is we hit a null note， in which case。

 we know that the value we're looking for doesn't exist。Our comparator returns the value of 0。

 meaning we found the node we want to remove。 The comparator value is less than 0。

 So the value we're looking for if it exists， is going to be found in the left sub tree or the comparator value is greater than 0。

 in which case， the value if it exists is in the right sub tree。

 So let's do an example of finding nodes in a binary search tree。 supposeupp were。



![](img/b39aa4e82de10f853118516361e345e2_5.png)