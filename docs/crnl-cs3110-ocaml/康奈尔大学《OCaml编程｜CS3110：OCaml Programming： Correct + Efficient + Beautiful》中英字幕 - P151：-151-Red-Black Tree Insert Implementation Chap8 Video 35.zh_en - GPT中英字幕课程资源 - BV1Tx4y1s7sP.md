# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P151：-151-Red-Black Tree Insert Implementation Chap8 Video 35.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

Let's look now at the code that implements the red black tree。

You can see the balance operation here first， which is just the same as the code that I showed you earlier on slides。

This function is constant time， It's not recursive。

 It doesn't do anything other than pattern match against the first two levels in a tree to see whether the red nodes might be。

 and then rotate around and construct a new tree as a result。Below that。

 we have the insert O function。Insert O is my auxiliary helper function for insertion。

It's basically the same code as insert on a binary search tree。😡，If we're inserting into a leaf。

 it just creates a new tree that has two leafs as the subtrees。

 the new element X as the value at the node， and then it colors that node red。

 which is exactly what Okasaki's algorithm says to do， always color that new node red。

 even though it might violate the local invariant。Then insert， as the insert operation for BST did。

 looks to see whether the element being inserted， x is less than or greater than the value at the node V。

😡，And it recurs itself down on the left or right sub correspondingly， keeping the color intact。

The only real change is the insertion of calls to balance in order to balance the result of each of those recursive calls on the way up and restore the local invariant。

Finally， insert。Really just uses insert ox as a helper。

The first thing it does is to match against the return value of insert ox to see if it gave back a leaf now that should be impossible。

 it is impossible， I'm only doing the fail with here in order to get an exhaustive pattern match。



![](img/a4553e8289ac3e6e25ef083055157d05_1.png)

Really， the interesting work that insertt has to do is to color the root black。😡。

And so that's what the final pattern matching branch does here， no matter what insert O returned。

 insert is going to recolor it to be black to finish off the out。



![](img/a4553e8289ac3e6e25ef083055157d05_3.png)

So insert itself is going to be logarithmic time because it calls insert ox。

 and it's guaranteed to be logarithmic by that lemma and theorem we looked at before about the size and pathlings of red black trees。

😡。