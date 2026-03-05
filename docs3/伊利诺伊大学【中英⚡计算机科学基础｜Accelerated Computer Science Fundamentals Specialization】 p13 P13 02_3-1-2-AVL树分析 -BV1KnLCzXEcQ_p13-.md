# 伊利诺伊大学【中英⚡计算机科学基础｜Accelerated Computer Science Fundamentals Specialization】 p13 P13 02_3-1-2-AVL树分析 -BV1KnLCzXEcQ_p13-

![](img/c8d4b259dc8db275bf6dcff63b0b74f2_0.png)

![](img/c8d4b259dc8db275bf6dcff63b0b74f2_1.png)

Balanced binary search trees are kept in balance through tree rotations when we do an insert and remove。

 We call these trees A VL trees named after two computer scientists， Adson Velsick and Landis。

 an A VL tree is just like a binary search tree。 Everything you know about a binary search tree still holds true。

 that includes finding， inserting， removing and everything else。

 We only do two things differently in an A VL tree。 That is。

 we do some extra work on inserting remove to ensure that we keep the trees in balance。😊。

And to keep the balance factor to be able to be computed easily。

 we're going to store the height of every single node in the tree。

 We'll see how this works through examples。 So let's go ahead and look at an insert。

Suppose we want to insert the node 14 into our binary search tree or an AviL tree。

 just like the insertion algorithm we talked about previously， we're going to start the route。

 compareare 14 to 18 and find that we need to move left。Looking at 5，14， we need to move right，10。

 we need to move right again，12， We need to move right again。

 And here we can insert 14 as a new leaf node right atly in this path。

 We do this insertion through a recursion algorithm so we can always check each thing as we move back up the tree。

So let's actually look at a stepwise process for doing this。

The first step is to insert that proper place。 We know that the insertion happened by taking this path right here and inserting here at 14。

As we move back up the tree， we're going to check at every single place for an imbalance rotate if necessary。

 and update the height。 So here， the height of 12 is now going to be equal to  one since we have one node below it。

 Moving up to 10。 We see the height of this element is going to be 2 because we have two nodes below it。

But what happened here？We have an imbalance right here。 We have one side of the tree， the right side。

 having a height difference of more than one， specifically a height difference of 2。

 So we know that this tree is at a balance right here。 So we need to go ahead and repair that。

 We do that through a simple rotation。 We're going have 12 moved up。

 So 12 is going to be the top node。10 is going to come from the left。

14 is going to come from the right。 and we have a repaired binary search tree。 The height of 12 is 1。

 The height of 10 is 0。 The height of 14 is 0。And now we can move up to5。

 check if five's height is still3， it is， and then check it 18 height is still 4。

So by doing an insertion and moving back up the chain。

 we saw we only need to do a rotation somewhere along the path we took to do the insertion。

 We found we had to do one rotation this time， but we were able to insert 14 and ensure that the AVL tree was a balanced binary search tree by the time we gave it back to the user。



![](img/c8d4b259dc8db275bf6dcff63b0b74f2_3.png)

The code to ensure the balance was added to the binary search tree code you saw last lecture。

 And now we have this extra helper function called insure balance in our A VL tree。

 This ensure balance function is going to help us by ensuring that if our balance has a value of negative to。

 we know that we need to either do a right rotation or a left right rotation。 If our balance is too。

 we know that we need to either do a left rotation or a right left rotation。

 we determine that by looking at the balance of the next node。

 So here we see the height of the curve left。 right and the cur left left。

 this is exactly what we saw in the diagrams that we looked at previously。

 So everything you saw in the last video and this video came together in this function to ensure that if our tree is ever at a balance that we do the prop rotation based on table we discussed last time to get the tree back in balance。

 taking a look at the rest of this， we need an update height function that simply updates the height and a rotate left function to do the actual rotation。

 And that's it。 The only other place we need。😊，To do actual work is in remove。

 So let's look at the possibility of removing 5 from our original binary search tree。



![](img/c8d4b259dc8db275bf6dcff63b0b74f2_5.png)

Here we're going to find five just as we've done before。😡，18， move left to find 5。

 and we found the node we need to remove。 Remember to remove a node。

 we need to find the in order predecessor of that node。

That means we have to find the node that comes just before that node。

Or the rightmost node in the left subre， The rightmost node in left subtre is going to be the element 4。

 So we go ahead and swap 5 with 4。And then we need to remove this node we just swapped。

 So we remove 5。 We'll notice that we now have， as we move up this tree from 5。

 we have to rotate 3 because three is now out of balance。 There's2。

 a height difference a 2 on the left than the right。 Roating this。

 We're going to see that it's an elbow。 So the first thing we're going to do is transform the elbow into a stick。

 And then we're going to raise the middle element of the stick。 so that we now have two。

1 and 3 hanging off the side of the four element。 Now we see that with these with a height of one here。

 and a height of one on the left hand side and a height of one on the right hand side。

 The middle element here has a height balance exactly right。 The height is actually shrink slightly。

So the height is now2 here。 We move a tree and we see the height of the root is 3。

 So just like before， the only nodes we have to update is the path we took to do the deletion。

When we remove an element or reinserr an element， we only need to modify nodes along the path to do so。



![](img/c8d4b259dc8db275bf6dcff63b0b74f2_7.png)

So the code to modify the remove is just gonna to be simply adding a extra function called Iop remove。

 that's going to go ahead and remove the Iop。 And it's going to find whether or not where the Iop is by looking at the rightmost pointer and left subre。

 And if we'd have found the IO， we're simply going to swap that element and then going to go ahead and call our remove function to remove it altogether。

 You have all this code provided for us and we'll take a look at it in a second。



![](img/c8d4b259dc8db275bf6dcff63b0b74f2_9.png)

So as a reflection on all of this， we know that an AVL tree is an implementation of a balanced binary search tree。

And an implementation of aviial tree starts with a binary search implementation and then just adds two things。

 We added the height of every single node to be stored with the node itself。

 And we maintain the balance factor of the tree after every insertion removed。

 By only doing those two things， we ensure that we have a balanced binary search tree。

 So before we go， let's take a look at the code。 And then we'll discuss exactly how this aviL tree runs in our next lecture。

 So let's look at some code。

![](img/c8d4b259dc8db275bf6dcff63b0b74f2_11.png)

Going to the AVL directory。I can check out what's in main。cppP。



![](img/c8d4b259dc8db275bf6dcff63b0b74f2_13.png)

You'll see inside main。 we create an A VL tree。 This A VL tree is going to be a dictionary where we have integers as the keys and strings as the values here。

 we insert a number of things in A VL tree， just like we did in binary our search tree。

 The key is going to be the integer number。The value will be the string itself。

 saying the integer number。 And we'll see out a bunch of things。

 The first thing we're going to do is we're going to find 51 using the code we have for our A VL tree。

 Then remove 11，51 and 19。As well as 6。 So 11 is going to be a simple remove where there's no children。

51 is going to be a somewhat simple remove where there's one child。 And then 196。

 those are going to contain two different children in our A VL tree to make them more complex moves to make sure that we handle the I O P situation exactly correctly。

 The very last thing we're going to find 51。 We expect you to have that to be an error because we just remove 51 earlier。

 Let's go ahead and run this and see what happens。 Run make to compile。



![](img/c8d4b259dc8db275bf6dcff63b0b74f2_15.png)

And then dot slash main。We see when we find 51， we indeed get the 51 value out。

 removing 11 or remove 11， removing 51， removes 51， removing 19， remove 19， removing 6。

 remove 6 here， when we find 51， We find that we have an uncutaught exception。 Henot found。

 This is exactly what we expect。 because since the first time we found 51， we've removed it。

 now 51 no longer exist。 So you have the source code for the A VL tree。

 You have all of this information， you can play around with doing amazing things to the A VL tree yourself。

 And I hope you'll spend some time doing that。😊。

![](img/c8d4b259dc8db275bf6dcff63b0b74f2_17.png)

So have fun and I'll see you next time。

![](img/c8d4b259dc8db275bf6dcff63b0b74f2_19.png)