# mycodeschool【中英⚡数据结构｜Data Structures】 p36 p35 Delete a node from Binary Search Tree -BV1ckrLYREn2_p36-

In this lesson， we are going to write code to delete a note from binary search tree。

In most data structures deletion is tricky in case of binary search trees 2。

 it's not so straightforward， so lets foresee what all complications we may have while trying to delete a note from binary Search tree。



![](img/312882b4ee745f9691f56cca19c9b10a_1.png)

![](img/312882b4ee745f9691f56cca19c9b10a_2.png)

I have drawn a binary search tree of integers here。

 as we know in a binary search tree for each node value of all nodes in its left subte is lesser and value of all nodes in its right subre is greaterter。

For example， in this tree， if I'll pick this node with value 5。

 then we have3 and 1 in its left sub3 which are lesser， and we have7 and9 in its right sub3。

 which are greater。And you can pick any other node in the tree and this property will be true else the tree is not a BST Now when we need to delete a node。

 this property must be conserved。Let's try to delete some notes from this example tree and see if we can rearrange thingss and conserve this property of binary search tree or not。

What if I want to delete this node with Val 19 to delete a node from tree， we need to do two things。

We need to remove the reference of the node from its parent。

 so the node is detached from the tree here we will cut this link。

 we will set right childil off this node with value 17 as null。

 and the second thing that we need to do is reclaim the memory allocate it to the node being deleted that is。

Wipe off the node object from memory。This particular node with value 19 that we are trying to delete here is a leaf node。

 it has no children， and even if we take this guy out by simply cutting this link that is removing its reference from its patent and then wiping it off from memory there is no problem。

 property of binary search tree that for each node value of node than left should be lesser and value of node in right should be greater is conserved。

So deleting a leaf node a node with no children is really easy in this tree these four nodes with values 1。

913 and 19 leaf nodes。

![](img/312882b4ee745f9691f56cca19c9b10a_4.png)

![](img/312882b4ee745f9691f56cca19c9b10a_5.png)

To delete any of these， we just need to cut the link and wipe off the node。

 that is clear it from memory。But what if we want to delete a null leaf node。

 what if in this example we want to delete this node with value 15？



![](img/312882b4ee745f9691f56cca19c9b10a_7.png)

I can't just cut this link because if Ill cut this link we will detach not just the node with value 15 but this complete subree we have two more nodes in this subre we could have had a lot more we need to make sure that all other nodes except the node with value 15 that's being deleted remain in the tree so what do we do now this particular node that we are trying to delete here has two children or two subtes I'll come back to Kof node with two children later because this is not so easy to crack what I want to discuss first is the case when the node being deleted would have only one child。



![](img/312882b4ee745f9691f56cca19c9b10a_9.png)

![](img/312882b4ee745f9691f56cca19c9b10a_10.png)

![](img/312882b4ee745f9691f56cca19c9b10a_11.png)

![](img/312882b4ee745f9691f56cca19c9b10a_12.png)

If the node being deleted would have only one child like in this example this node with value 7。

 this guy has only one child， this guy has a right child but does not have a left child for such a node what we can do is we can link its parent to this only child so the child and everything below the child we could have some more nodes below nine as well will remain attached to the tree and only the node being deleted will be detached。



![](img/312882b4ee745f9691f56cca19c9b10a_14.png)

Now， we are not losing any other node than the node with value 7。 This is my tree after the deletion。



![](img/312882b4ee745f9691f56cca19c9b10a_16.png)

Is there still a binary search tree， yes it is only the right subree of node width value 5 has changed。



![](img/312882b4ee745f9691f56cca19c9b10a_18.png)

Earlier we had 7 and9 in write sub 3 of5 and now we have nine， which is fine。

What if we were having some more nodes below9？Here in this tree I can have a node in left of9 and the value in this node has to be lesser than 12。

 greater than 5， greater than 7 and lesser than9 we are left with only one choice we can only have eight here。



![](img/312882b4ee745f9691f56cca19c9b10a_20.png)

In right， we can have something lesser than 12 and greater than 5，7 and 9。

 all in all between 9 and 12。

![](img/312882b4ee745f9691f56cca19c9b10a_22.png)

Okay， so if the original tree was this much after deletion， this is how my tree will look like。Okay。

 so are we good now is the tree in right ObT， well， yes， it is。

When we are setting this node with value9 as rightchild of the node with value 5 we are basically setting this particular subre as right subree of the node with value5 now this subree is already in right of five so value of all nodes in this subre is already greater than five and the subtree itself of course is a binary search tree any subree in a binary search tree will also be a binary search tree so even after diletion even after the rearrangement property of the tree that for each node nodes in left should be lesser and nodes in right should be greaterter in value is conserved so this is what we need to do to delete a node with just one child or a node with just one subre connect its parent to its only child and then wipe it off from memory there are only two nodes in this tree that have only one child let's try to delete this other one with value 3。



![](img/312882b4ee745f9691f56cca19c9b10a_24.png)

![](img/312882b4ee745f9691f56cca19c9b10a_25.png)

![](img/312882b4ee745f9691f56cca19c9b10a_26.png)

All we need to do here is set one as left child of five。



![](img/312882b4ee745f9691f56cca19c9b10a_28.png)

Once again， if there were some mode nodes below one， then also there was no issue。



![](img/312882b4ee745f9691f56cca19c9b10a_30.png)

Okay so now we are good for two cases we are good for leaf nodes and we are good for node switch just one child and now we should think about the third case what if a node has two children what should we do in this case let's come back to this node with value 15 that we were trying to delete earlier with two children we can't do something like connect parent to one of the children while trying to delete 15 if we will connect 12 to 13 if we will make 13 the right child of 12 then we will include 13 and anything below 13 that is we will include the left sub3 of。



![](img/312882b4ee745f9691f56cca19c9b10a_32.png)

![](img/312882b4ee745f9691f56cca19c9b10a_33.png)

15， but we will lose the right subre of 15 that is 17 and anything below 17。 Similarlyly。

 if we will make 17 the right child， then we will lose the left subre of 15 that is 13 and anything below 13。

Actually this case is tricky and before I talk about a possible solution I want to insert some more nodes here。

 I want to have some more nodes in subtes of 13 and 17。

 The reason I'm inserting some more nodes here is because I want to discuss a generic case and that's why I want these two subtes to have more than one node okay coming back when I'm trying to delete this node my intent basically is to remove this value 15 from the tree my delete function will have signature something like this it will take pointer or reference to the root node and value to be deleted as argument so here Im deleting this particular node because I want to remove 15 from the tree。



![](img/312882b4ee745f9691f56cca19c9b10a_35.png)

![](img/312882b4ee745f9691f56cca19c9b10a_36.png)

![](img/312882b4ee745f9691f56cca19c9b10a_37.png)

What I'm going to do now is something with which I can reduce case 3 to either case1 or case2。

I'll wipe off 15 from this node and I'll fill in some other value in this node of course I can't fill in any random value what I'll do is I'll look for the minimum in right subre of this node and I'll fill in that value here minimum in right subre of this node is 17 so I have filled 17 here。



![](img/312882b4ee745f9691f56cca19c9b10a_39.png)

![](img/312882b4ee745f9691f56cca19c9b10a_40.png)

We now have two nodes with value 17 but notice that this node has only one child we can delete this node because we know how to delete a node with one child and once this node is deleteted my tree will be good the final arrangement will be a valid arrangement for my BSD but why minimum in right subre why not value in any other leaf node or any other node with one child well we also need to conserve this property that for each node nodes in left should have lesser value and nodes in right should have greater value for this node if I'm bringing in the minimum from its right sub tree then because I'm bringing in something from its right subre it will be greater than the previous value 17 is greater than 15 so all the elements in left of course will be lesser。



![](img/312882b4ee745f9691f56cca19c9b10a_42.png)

![](img/312882b4ee745f9691f56cca19c9b10a_43.png)

![](img/312882b4ee745f9691f56cca19c9b10a_44.png)

![](img/312882b4ee745f9691f56cca19c9b10a_45.png)

![](img/312882b4ee745f9691f56cca19c9b10a_46.png)

![](img/312882b4ee745f9691f56cca19c9b10a_47.png)

And because it's the minimum in write sub 3， all the elements in right of the sky would either be greater or equal。

 we have a duplicate that will be equal once the duplicate is removed everything else will be fine。



![](img/312882b4ee745f9691f56cca19c9b10a_49.png)

![](img/312882b4ee745f9691f56cca19c9b10a_50.png)

In a tree or subre if a node has minimum value， it won't have a left child because if there is a left child。

 there is something lesser and this is another property that we are exploiting give this some thought in a tree or subree node with minimum value will not have a left child there may or may not be a right child if we would have a right child like here we have a right child so here we are reducing case3 to case 2 if there was no child we would have reduced case3 to case1。



![](img/312882b4ee745f9691f56cca19c9b10a_52.png)

![](img/312882b4ee745f9691f56cca19c9b10a_53.png)

Okay so let's get rid of the duplicate， I'll build a link like this and after deletion this is what my tree will look like。

 so this is what we need to do in case3 we need to find the minimum in right sub3 of the targeted node then copy or fill in this value and finally we need to delete the duplicate or the node with minimum value from right sub tree。



![](img/312882b4ee745f9691f56cca19c9b10a_55.png)

![](img/312882b4ee745f9691f56cca19c9b10a_56.png)

![](img/312882b4ee745f9691f56cca19c9b10a_57.png)

There was another possible approach here and I must talk about it instead of going for minimum in right。

 we could also go for maximum in left sub3， maximum in left sub3 would of course be greater than or equal to all the values in left。

😊。

![](img/312882b4ee745f9691f56cca19c9b10a_59.png)

![](img/312882b4ee745f9691f56cca19c9b10a_60.png)

![](img/312882b4ee745f9691f56cca19c9b10a_61.png)

Maximum in left sub3 of node with value 15 is 14 I'm copying 14 here now all the nodes in left are lesser than or equal to 14 and because we are picking something from left sub3 it will still be lesser than the value being deleted 14 is less than 15 so all the nodes in this right sub3 will still be tter and if we are picking maximum in a3 or sub3 then that node will not have a right child because if we have something in right we have something greater so the value can't be maximum the node may have a left child in this case node with value 14 doesn't have a left child。

So we are basically reducing case3 to case1。I'll simply get rid of this node。

So we are looking good even after deletion in case3。

 we can apply any of these methods and this is all in logic part。

 let's now write code for this logic。

![](img/312882b4ee745f9691f56cca19c9b10a_63.png)

![](img/312882b4ee745f9691f56cca19c9b10a_64.png)

I'll write C++ and we will use recursion if you're not very comfortable applying recursion on trees。

 then make sure you watch earlier lessons in this series。

 you can find link to them in description of this video。



![](img/312882b4ee745f9691f56cca19c9b10a_66.png)

In my code here I have defined node as a structure with three fields we have one field to store data and we have two fields that are pointers to node to store addresses of left and right children and I want to write a function named delete that should take pointer to root node and the data to be deleted as argument and this function should return pointer to root node because the root may change after deletion what we are passing to delete function is only a local copy of root's address if the address is changing we need to return it back to delete a given value or data we first need to find it in the tree and once we find the node containing that data we can try to delete it remember the only identity of tree that we pass to functions is address of the root node and to perform any action on the tree we need to start at root so let's first search for the node with this data。



![](img/312882b4ee745f9691f56cca19c9b10a_68.png)

![](img/312882b4ee745f9691f56cca19c9b10a_69.png)

![](img/312882b4ee745f9691f56cca19c9b10a_70.png)

![](img/312882b4ee745f9691f56cca19c9b10a_71.png)

First I'll cover a corner case， if root is null that is if the tree is empty we can simply return。

 I can say return root or return null here， they will mean the same because root is null else if the data that we are looking for is less than the data in root then it is in the left sub3。

The problem can be reduced to deleting the data from left sub3。

 we need to go and find the data in left sub 3 so we can make a recursive call to delete function passing address of the left child and the data。

To be deleted now the root of the left subre that is the left child of this current node may change after deletion。

 but the good thing is delete function will return address of the modified root of the left sub3 so we can set the return as left child of the current node。

Now， if。Data。That we are trying to delete is greater than the data and root。

 we need to go and delete the data from right sub3。

And if the data is neither greater nor lesser that is if it's equal。

 then we can try deleting the node containing that data Now let's handle the three cases one by one if there is no child we can simply delete that node what I'll do here is I'll first wipe off the node from memory and this is how I'll do it what we have in root right now is a address of the node to be deleted Im using delete operator here that's used to delocate memory of an object in heap in C you would use free function now root is a dangling pointer because the object in heap is deleted but root still has its address。



![](img/312882b4ee745f9691f56cca19c9b10a_73.png)

![](img/312882b4ee745f9691f56cca19c9b10a_74.png)

So we can set root as null。And now we can return root。

 reference of this node in its parent will not be fixed here。



![](img/312882b4ee745f9691f56cca19c9b10a_76.png)

Once this recursive call finishes， then somewhere in these two statements in any of these two statements。



![](img/312882b4ee745f9691f56cca19c9b10a_78.png)

In any of these two elsess， the link will be corrected。 I hope this is making sense。 Okay。

 now let's handle other cases。

![](img/312882b4ee745f9691f56cca19c9b10a_80.png)

![](img/312882b4ee745f9691f56cca19c9b10a_81.png)

If only the left child is null， then what I want to do is I first want to store the address of current node that I'm trying to delete in a temporary pointer to node。

And now I want to move the route。😔，This pointer named root to the right child。

So the right shell becomes the root of this sub3。And now we can delete。😊。

The node that is being pointed to by temp， we will use Dete operator and see we would be using free function。

And now we can return root。Similarly， if the right child is null。



![](img/312882b4ee745f9691f56cca19c9b10a_83.png)

I'll first store the address of current root in a temporary pointed node then I'll make the left child new root of the sub3。

 so we'll move to the left child and then I'll delete the previous root whose address I have in T and finally I'll return root actually we need to return root in all cases so I'll remove this return root statement from all all this if and I'll save。



![](img/312882b4ee745f9691f56cca19c9b10a_85.png)

![](img/312882b4ee745f9691f56cca19c9b10a_86.png)

![](img/312882b4ee745f9691f56cca19c9b10a_87.png)

![](img/312882b4ee745f9691f56cca19c9b10a_88.png)

And write one return route after everything let's talk about the third case now in case of two children。

 what we need to do is we need to search for minimum element in right sub3 of the node that we are trying to delete let's say this function find min will give me address of the node with minimum value in on tree or sub3 So I'm calling this function find min and I'm collecting the return in a pointer to node named temp。



![](img/312882b4ee745f9691f56cca19c9b10a_90.png)

![](img/312882b4ee745f9691f56cca19c9b10a_91.png)

Now I should set the data in current node that I'm trying to delete as this minimum value and now the problem is getting reduced to deleting this minimum value from the right subree of current node with this much code I think I'm done with delete function。



![](img/312882b4ee745f9691f56cca19c9b10a_93.png)

This looks good to me。

![](img/312882b4ee745f9691f56cca19c9b10a_95.png)

Let's quickly run this code on an example tree and see if this works or not。

 I have drawn a binary search tree here， let's say these values outside these nodes are addresses of the nodes now I want to delete number 15 from this tree so I'll make a call to delete function passing address of the root which is 200 and 15 the value to be deleted。



![](img/312882b4ee745f9691f56cca19c9b10a_97.png)

In delete function for this particular call， control will come to this line。

A recursive call will be made execution of this call delete 200 comma 15 will pause and it will resume only after this function below delete 350 comma 15 returns now for this call below we will go inside the third L in case 3 here we will find the node with minimum value in right which is 17 which is 400 the value is 17 address is 400 first we will set the data in node at 350 at 17 and now we are making a recursive call to delete 17 from write sub 3 of 350 we have only one node in write sub3 of 350 here we have case 1 in this call we will simply delete the node at 400。



![](img/312882b4ee745f9691f56cca19c9b10a_99.png)

![](img/312882b4ee745f9691f56cca19c9b10a_100.png)

![](img/312882b4ee745f9691f56cca19c9b10a_101.png)

![](img/312882b4ee745f9691f56cca19c9b10a_102.png)

And return null， remember route will be returned in all calls in the end。



![](img/312882b4ee745f9691f56cca19c9b10a_104.png)

Now delete 350 comma 15 will resume and in this resumed call we will set a address of right childil of Nod 350 as null。

 as you can see the link in parent is being corrected when the recursion is unfolding and the function call corresponding to the parent is resuming and now this guy can return and now in this call we will resume at this line。



![](img/312882b4ee745f9691f56cca19c9b10a_106.png)

![](img/312882b4ee745f9691f56cca19c9b10a_107.png)

![](img/312882b4ee745f9691f56cca19c9b10a_108.png)

![](img/312882b4ee745f9691f56cca19c9b10a_109.png)

So right child of node at 200 will be set as 350 it's already 350 but it will be written again and now this call can also finish so I hope you got some sense of how this recursion is working you can find link to all the source code and go to test the delete function in description of this video This is it for this lesson thanks for watching。



![](img/312882b4ee745f9691f56cca19c9b10a_111.png)

![](img/312882b4ee745f9691f56cca19c9b10a_112.png)

![](img/312882b4ee745f9691f56cca19c9b10a_113.png)