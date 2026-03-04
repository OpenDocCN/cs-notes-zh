# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P148：-148-Red-Black Tree Implementation_ Rep Type, Empty, Mem Chap8 Video 32.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

Let's implement the set ADT with red black trees。We'll use a variant type to represent the colors red and black。

The representation type for our sets will be the binary trees that we've used before for binary search trees。

 but with one addition， we will use a color as part of the tuple as well as a left and right subte and the value stored at a node。

😡，For the abstraction function， the leaf represents the empty scent。

And a node represents the set containing the value sort of that node。

 as well as all of the elements of the sets represented by the left and right subtes。

 Notice that the color is irrelevant to the set itself。

 It has nothing to do with the elements that are part of the set。For the representation invariant。

 we use the BST invariant and the local and global invariants for red black trees。

The empty set is just the leaf constructor。And the MEm operation is virtually identical to the MEm operation we implemented for binary search trees。

😡，Literally， the only difference is in the pattern match where we put a wild card to indicate we're just ignoring the color。

 otherwise it's the same code。Insert， though， is going to be a little trickier。

