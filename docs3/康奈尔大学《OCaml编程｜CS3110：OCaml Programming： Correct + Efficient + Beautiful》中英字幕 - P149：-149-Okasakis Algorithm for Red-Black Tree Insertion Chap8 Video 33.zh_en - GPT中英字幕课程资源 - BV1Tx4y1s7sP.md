# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P149：-149-Okasakis Algorithm for Red-Black Tree Insertion Chap8 Video 33.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

To start implementing insert for red black trees， we can use the same code that we used for insert into binary search trees。

So if we are starting off with an empty tree， which is a leaf。

 and we want to insert an element into that X。What will create a new node with X stored at that node and with empty subtes。

But since this is a red black tree， we now have to pick a color for this new node。So the question is。

 what color can we safely pick。

![](img/e1faa0cbdd5397363a5814abed84a1f8_1.png)

Let's think about this tree as an example。Suppose we were to insert four into this tree。Well。

 by the BST invariant， there's only one place we could put it and that's to the left of five。



![](img/e1faa0cbdd5397363a5814abed84a1f8_3.png)

But if we colored it red。

![](img/e1faa0cbdd5397363a5814abed84a1f8_5.png)

That would violate the local invariant。So it's not safe to always color new nodes red。



![](img/e1faa0cbdd5397363a5814abed84a1f8_7.png)

What if we call it black？Oof， that violates the global invariant。

 because before we had one black node along each path。 now。

 some paths have one and some paths have two。 So black is also not safe as a color to always pick for new nodes。



![](img/e1faa0cbdd5397363a5814abed84a1f8_9.png)

![](img/e1faa0cbdd5397363a5814abed84a1f8_10.png)

![](img/e1faa0cbdd5397363a5814abed84a1f8_11.png)

What to do about that。Okasaki came up with an algorithm for this in 1998 for functional red black trees。

 That's particularly elegant。

![](img/e1faa0cbdd5397363a5814abed84a1f8_13.png)

![](img/e1faa0cbdd5397363a5814abed84a1f8_14.png)

I want to caution you before I show you this algorithm。That if you look at online simulators。

 you might find， in fact， much of the time will find that they implement different algorithms than Okasakis。

 so don't trust what you might find on other websites。😡。



![](img/e1faa0cbdd5397363a5814abed84a1f8_16.png)

![](img/e1faa0cbdd5397363a5814abed84a1f8_17.png)

![](img/e1faa0cbdd5397363a5814abed84a1f8_18.png)

In Okasaki's algorithm， the choice of what color to make a new node is based on the following principle。



![](img/e1faa0cbdd5397363a5814abed84a1f8_20.png)

We will always maintain the BST and global invariance。



![](img/e1faa0cbdd5397363a5814abed84a1f8_22.png)

But we're willing to sacrifice the local invariant， at least temporarily。



![](img/e1faa0cbdd5397363a5814abed84a1f8_24.png)

So we'll go ahead and make the new node read， always。

 even though that might cause a local invariant violation。

Then we will recurse our way back up the tree after in putting in that new node and making it red。

And on the way back up， we'll keep looking at the two nodes immediately below the current node。😡。

If we detect a violation where we have two reds in a row， we will rotate the nodes around。

To cause the local invariant to hold again。And while we're at it， balance the tree。

So that it has a little bit better of a shape。

![](img/e1faa0cbdd5397363a5814abed84a1f8_26.png)