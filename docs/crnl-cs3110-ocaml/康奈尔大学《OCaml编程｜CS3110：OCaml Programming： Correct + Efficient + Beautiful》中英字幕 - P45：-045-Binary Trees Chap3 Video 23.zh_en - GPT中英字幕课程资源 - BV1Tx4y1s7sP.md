# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P45：-045-Binary Trees Chap3 Video 23.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

As another example of variants in Ochemel， let's take a look at binary trees。

Bineinary trees are of course very similar to singly linked lists in that a singly linked list has nodes where every element has a single successor。

In a binary tree， there are nodes， each of which can have two successors for the two subchildren I've put code here for both Alpha myist and Alpha tree so we can compare it as we go along。



![](img/46fb2972c57f0e51a2042e9b391e2b33_1.png)

An alpha myel list was either nil or cons。An alpha tree is either leaf or node。

 so leaf represents an empty tree that contains nothing。

Noode represents a node of the tree that contains a value of type alpha。

 as well as another alpha tree and another alpha tree。

So it's really just up to renaming all of the identifiers in it， the same definition as alpha mylist。

 but with this final little piece tacked on of a second child of the node。

 whereas the list only had a single child of the node。Okay， so to create a value of such a type。

 here's a treat T。

![](img/46fb2972c57f0e51a2042e9b391e2b33_3.png)

Here's a picture of the tree we are creating， it has two at the root with one is the left child and three is the right subchild。

Each of the nodes one and three themselves have two leaves as subchildren。

Often we won't even bother to draw the leaves when we draw pictures of trees like this because they're uninteresting。

 they don't contain any data， there's really nothing to be done with them so we'll typically leave them out What if you wanted to take the size of a tree which is to say the number of nodes in it。



![](img/46fb2972c57f0e51a2042e9b391e2b33_5.png)

Well， the code would look a lot like the code that you would write for getting the size of a list。

So in the case that either one is empty， so for the leaf constructor or for the nail constructor。

 we'd return zero。But for the non emptyty case， which for lists would be cons。

 for trees would be node。I think we're going to return one plus the result of the recursive call on the children。

And in the case of a list， there's one child， in the case of three， there are two children。

What if you wanted to sum up all the elements of a list or a tree， well。

 for a list you'd return the head plus the sum of the tail if the list is not empty for a tree。

 you would return the value at the node plus the result of the recursive call on each of the subchildren。

So once again， it's really pretty much the same code。

Binary trees are really not that hard to implement in Oaml。

 and that's one of the brilliant things about functional program。



![](img/46fb2972c57f0e51a2042e9b391e2b33_7.png)