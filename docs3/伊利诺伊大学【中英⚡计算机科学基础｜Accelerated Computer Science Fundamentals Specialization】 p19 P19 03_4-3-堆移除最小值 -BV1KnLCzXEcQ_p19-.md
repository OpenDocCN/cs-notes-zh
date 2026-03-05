# 伊利诺伊大学【中英⚡计算机科学基础｜Accelerated Computer Science Fundamentals Specialization】 p19 P19 03_4-3-堆移除最小值 -BV1KnLCzXEcQ_p19-

![](img/c191c219e9ebbbc2b3e00e2ea5c88ebe_0.png)

![](img/c191c219e9ebbbc2b3e00e2ea5c88ebe_1.png)

At this point， you know what it means to be a minimum heap and you know how to insert an element into the heap。

 Let's go ahead and remove an element from the heap。To do so。

 we are always going to be removing the minimum element。

 There is no operation on the heap that we can do except for removing that minimum most element。

So to do so， we're going to go have to figure out an algorithm。To take the top element of the tree。

 the root of the tree itself， and actually maintain the heat property， even after removing the tree。

 So let's look at an example of removing a couple of nodes。

So here's the tree we had in the previous video before we did any insert Now I want to remove minimum on our root node。

 so removing minimum is going to take four out of the tree to do that I'm going to go ahead and use a clever approach of actually just swapping the very last element in our tree with four to ensure that we don't mess up the tree structure itself。

 so as remove min I'm going to take four out and I'm going to put that very last element 11 into this tree。

So doing that means that we have a complete tree still， we haven't ruined our tree structure。

 we've just ruined the order。😡，In the previous example， we did a heap offi up to do insert here。

 we're gonna heapify down to do a remove minimum。 So looking at our root node。

 we need to compare with the child and take the smallest of the two children and swap the smallest child with the node above it。

 So here 11 and 5 needs to get swapped so that 5 becomes a new root and 11 becomes a left child。

Here we can then compare against to the next level， 11 versus 9。Nine is smaller。

 we need to bring nine up。And bring 11 down。Here 11 is smaller than both 14 and 12。

 therefore 11 has found its proper spot， and we've maintained the heat property。

Let's do one more example here on this slide， to understand understand exactly how this works。😡。

So going through a second example， we're going to remove min again。😡。

Removing men a second time means that we're going to remove the element 5。

 so5 gets removed and 12 becomes our new root node。We removed 12 entirely from the tree。

What this means is here。We're going to be updating the ray every single point of the view the way。

 but I'm here just updating the tree to make it simpler。 looking at 12。

 we're going compare our two children nodes here，6 is going to be the smallest element。

 so 6 becomes the root，12 becomes the right child。 Again comparing the two children of 12。

 We have7 verse of 20，7 is a smaller element。 We swap 7 and 12， bringing7 down here and 12 here。

So again， we've maintained the heat property by doing a series of。Heap ofify down operations。

 it's going to ensure that after we finish doing our remove。

 that we ensure that the tree is a complete tree and that every single level has nodes。

Whose the smallest element is the root node， and larger elements are always below that root node。

The next thing we can look at is how do we actually run this。 What's the actual code。

Here looking at the code， we see the code's really simple for you move in。

 the first key operation here is we're going to swap with our last element。

The second key operation we're going to do is we're going to heap a P down。

 so this is what restores the he property。And like heappafi up。

 we have a huber function that's going to do this， heap of fi down again always starts with the root node。

 so we know exactly how to begin the call the heappa fi down。😡，Looking the heappafi down。

 we'll go ahead and start this at element1， the root of the tree。 we're gonna heappaify down。

 check if it's a leaf node， if it is not a leaf node。

 we know that we need to compare against to children。

 we're going to compare whether or not the item at our current index is going to be the item at the minimum trials index。

 So we want to check whether or not。Our current item is larger than the item of this current smaller。

 if it is， then we can go ahead and need to call our hepaphy down recursively after doing the swap operation on line 6。

So the very last thing we're going to do is we're going to he a fight down again on an index。

 so this will be the Min childil index。Which says that we are going to heap aify down by swapping the element with the minimum of our two children and doing that swap。

 we're going to ensure that the he property is maintained because the smallest element among the two children is now placed on top。

 so we know after the swap that among the subtree that includes our root node and our two children that the root node is the smallest。

 then we need to recursively continue down the path that we did the swap in。😡。

After doing this recursive operation， we know by the time we reach a leaf node that we found the proper spot to restore the heat property of this tree。

So through two really clever algorithms。😡，Inserting using heap of P up and removing minimum by using heap of P down。

 we're able to maintain a minimum heap through a series of simple tree operations that allows us an extremely efficient structure to maintain an order。

😊，Inside an array without having a totally ordered array。

 This is going to be a really useful property。 And we're going to start building properties on top of heaps in the next lecture。

 So I'll see there。

![](img/c191c219e9ebbbc2b3e00e2ea5c88ebe_3.png)