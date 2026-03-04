# 康奈尔大学《OCaml编程｜CS3110：OCaml Programming： Correct + Efficient + Beautiful》中英字幕 - P144：-144-Binary Search Trees Chap8 Video 28.zh_en - GPT中英字幕课程资源 - BV1Tx4y1s7sP

Could we do better than linear your time for our set implementation。

If you think back to learning about linear search versus binary search with arrays。

 you might suspect the answer is yes， we can do better。Recall that with linear search。

 you end up needing to scan through an entire array， and that has linear running time。

 its big O of N where n is the length of the array。😡，But with binary search。

 you don't scan the whole array。 You repeatedly keep having the search space。 Now， of course。

 that requires an invariant to hold of the array。 It must be in sorted order。

But that reduces the running time of the search algorithm to big O of log N。

 We keep halfing and halfing and halfing the size of the air that we're looking through。

 That corresponds to the log operation。 There's a corresponding notion that you'll remember from earlier programming classes about binary search trees to make it more efficient to search for an element。

In a binary tree， of course， every node has two subrees。

But the binary search tree invariant or the BST invariant。

Says that if you're at a node containing you the value V。

 then all the values in the left subt treee have to be less than V and all the values in the right subt have to be greater than V。

We can use a binary search tree to implement a more efficient set。



![](img/27883f24dbebc85e6363aceb4e8b332d_1.png)

I've got us started here with a module BST set that implements the set interface。

For the representation type， I'm using the same tree type that we've come to know and love for a while now。

I either have leaves， which are empty or nodes， which contain a value as well as a left and a right sub。

The abstraction function here for a tree to represent a set is that leaf represents the empty set。

And if I have a node that contains the value V， as well as subtes， L and R。

That represents the set that contains V。Union together with all the elements of the sets the L represents and the R represents。

My representation invariant is simply the BST invariant。😡，For every node in the tree。

 all the values in the left subte have to be less than V and all the nodes in the right subree have to have values that are greater than V。

The empty set， then， is simply the empty tree， just a leaf。And I need to implement two operations。

 Mem and insert。Let's go ahead and implement MeM first。

I'm going to be guided in my implementation of it by the BST invari。😡。

So the easy case is if I'm looking at an empty tree。

 there's no way any element can be a member of that set， so I'll return false in that case。

If I do have a node in the tree， then I want to compare the value X that I'm looking for to the value V that's in that node。

😡，If x is less than v then I want to look in the left sub tree recursively。 If x is greater than v。

 I want to look in the right subt recursively。 Otherwise， x must be equal to V。

 So I've just found that element of the set， and I can return true。

 The algorithm for insert is almost the same as the algorithm for me。In both places。

 we need to use the BST invariant to figure out where in the tree a node should be。

It's just for them we look for it there and then return true or false depending on whether we found it with insert。

 once we get to the right place， we put the element there where it ought to be。😡。

So the code for insert is going to look almost the same as the code for mem。Let's pause here。

 we have an inexhausted pattern match right now that I want to explain what I just wrote。



![](img/27883f24dbebc85e6363aceb4e8b332d_3.png)

If we have an empty tree， then we go ahead and insert the new element X by creating a new node which has empty subtes。

😡。

![](img/27883f24dbebc85e6363aceb4e8b332d_5.png)

![](img/27883f24dbebc85e6363aceb4e8b332d_6.png)

If we have a non empty tree with a node in it， then we use the BST invariant to compare the element X that we're inserting to the value V already at the node。

If x is less than v， we recurse on the left subte to insert into it。

 if x is greater than v then we recurse on the right subte to insert into it。

 otherwise we're at exactly the place that element ought to be so we can just return the node that's already there because x must be equal to。

A couple comments on the implementation of this。 We already have node L VR as something we pattern matched against。

 And now we're creating a new node。

![](img/27883f24dbebc85e6363aceb4e8b332d_8.png)

We could optimize that just the tiniest bit by giving the node that we matched up here a name with this as pattern and then just saying return n here。

😡，That's a little nicer。Also， a common error here is to recurse on just the subte。

But to forget to actually reconstruct the rest of the tree around it。

So you could recurse here on the left subte and insert X into the appropriate place。

 but now you've totally forgotten about V， which is supposed to be in the set still。

 and all of the elements in the right subt are that we're supposed to be in the set。😡。

So it's easy to do， but don't forget to reconstruct that node with V and R。



![](img/27883f24dbebc85e6363aceb4e8b332d_10.png)