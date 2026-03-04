# mycodeschool【中英⚡数据结构｜Data Structures】 p37 p36 Inorder Successor in a binary search tree -BV1ckrLYREn2_p37-

In this lesson we are going to solve another interesting problem on binary search  tree and the problem is given a node in a binary search tree。

 we need to find its in order successor that is the node that would come immediately after the given node in in order traversal of the binary search  tree。



![](img/6a9b92df06a5a2551f62473daa3ab9cb_1.png)

As we know in in order Traverse cell alpha a binary tree， we first visit the left subree。

 then the root and then the right subtre， left and right subrees are visited recursively in same manner。

 so for each node we first visit its left subre， then the node itself and then its right subree。

 we have already discussed in order Traver cell in detail in a previous lesson in this series you can check the description of this video for a link to it。



![](img/6a9b92df06a5a2551f62473daa3ab9cb_3.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_4.png)

In order， implementation will basically be a recursive function。

 something like what I'm showing in right here。There are two recursive calls in this function。

 one to visit the left subree and another to visit the right subre。



![](img/6a9b92df06a5a2551f62473daa3ab9cb_6.png)

Time complexity of in order traveral is pick O of n where n is number of nodes in the tree。

 we visit each node exactly once， so time taken is proportional to number of nodes in the tree。



![](img/6a9b92df06a5a2551f62473daa3ab9cb_8.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_9.png)

I have drawn a binary search tree of integers here。

 binary search tree as we know is a binary tree in which for each node value of nodes in left is lesser and value of nodes in right is greaterta。



![](img/6a9b92df06a5a2551f62473daa3ab9cb_11.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_12.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_13.png)

Let's quickly see what will be the inor traveral for this Pity search tree we'll start at root of the tree now for any node we first need to visit all nodes in its left and then only we can visit that node so we will have to go left basically we will make a recursive call to go to left child of this node for this guy once again we have something in left。



![](img/6a9b92df06a5a2551f62473daa3ab9cb_15.png)

So we will make another recursive call and go to its left child。

Now we are at this node with value 8 and we will have to go left one more time and now for this node with value 6 which is a leaf node。

 we have nothing in left so we can simply say that its left subree is done and hence we can visit this guy visiting for me is reading the data in that node Ill write the data here and now for this node there's nothing in right as well so。



![](img/6a9b92df06a5a2551f62473daa3ab9cb_17.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_18.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_19.png)

We can simply say that its right is also done。And now we are completely done for this guy。

So recursive call corresponding to this node will finish and we will go back to call corresponding to its spirit。



![](img/6a9b92df06a5a2551f62473daa3ab9cb_21.png)

If we will come back to a node from its left child。

 then it will be unvisited because we can't visit a node until it left is turn。

 so when we are coming back to 88 is unvisited so we can simply visit this node that is read the data in this node。



![](img/6a9b92df06a5a2551f62473daa3ab9cb_23.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_24.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_25.png)

When I'll visit a node， I'll paint it in yellow and now there is nothing in right of this node so we can simply say that right is done。



![](img/6a9b92df06a5a2551f62473daa3ab9cb_27.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_28.png)

Now we are done with this node， so call corresponding to this node will finish and we will go back。

To its parent once again we are coming back to the parent from left。

 so the parent that is this node with value 10 is unvisited。

 if we would come back to a node from right then it would already be visited so I' am visiting 10 and now we can go to right of 10。

So far we have visited three nodes， we first visited node with value 6。

 and then we visited node with value 8， so 8 is successor of 6 and then 10 is successor of8。Now。

 let's see what will be the successor of 10 for nodes with values 6 and 8。

 there was nothing in right。 So we were unwinding and going to the parent， but for a node。

 if there would be something in right， that is， if there would be a right subre。

 then its successor would definitely be in its right subre， because after visiting that node。

 we will go right。 Now， at this stage， we are at this node with value 12。

For this guy we will first go left and now we are at node with value 11 which is a leaf node。

 there is nothing in left so we can simply say that left is done and we can print the data。



![](img/6a9b92df06a5a2551f62473daa3ab9cb_30.png)

That is visit this node， So in order successor of 10 is 11。

 Now for node with value 11 there is nothing in right， so we will go back to its parent。

And now we can visit this guy so after 11 we have 12， there is nothing in right of 12。

 so call for this guy will finish and we will go to its parent now we are coming back to 10 again but this time from right so this guy is already visited。

So we need not do anything we can simply go to its spell and now we are at this node with value 15。

 we are coming from left this guy is unvisited so we can visit it。



![](img/6a9b92df06a5a2551f62473daa3ab9cb_32.png)

And now we can go to its right。

![](img/6a9b92df06a5a2551f62473daa3ab9cb_34.png)

We will go on like this。Successor of 15 would be 16。And after 16， we will print 17。😔。



![](img/6a9b92df06a5a2551f62473daa3ab9cb_36.png)

Then after 17， we will print 20。😔，Then 25 and the last element would be 27。



![](img/6a9b92df06a5a2551f62473daa3ab9cb_38.png)

So this is in auto traveral of this binary search tree notice that we have printed the integers in sorted order when we perform in order traversealon a binary search tree then elements are visited in sorted order Now the problem that we want to solve is given a value in the tree we want to find its in order successor in a binary search tree it would be the next higher value in the tree but what's the big deal here can't we just perform in auto traversal and while performing the traver cell figure out the successor well we can do so。



![](img/6a9b92df06a5a2551f62473daa3ab9cb_40.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_41.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_42.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_43.png)

But it will be expensive。 running time of in order is big O of n， and we may want to do better。



![](img/6a9b92df06a5a2551f62473daa3ab9cb_45.png)

Finding next and previous element in some data could be a frequently performed operation and good thing about binary search tree is that frequently performed operations like insertion deletion and search happen in big O of edge where edge is height of the tree so it would be good if we are able to find successor and predecessor in big O of edge we always try to keep a tree balanced to minimize its height height of a balanced binary tree is log n the base2 and big O of log n running time for any operation is almost the best running time that we can have。



![](img/6a9b92df06a5a2551f62473daa3ab9cb_47.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_48.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_49.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_50.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_51.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_52.png)

So can we find another successor in big O of edge？

![](img/6a9b92df06a5a2551f62473daa3ab9cb_54.png)

I have re example tree here。Lets see what we can do in various cases What node would we visit after this node with value 10 can we deduce this logically Well if you remember the simulation of inau traveral that we had done earlier then if we have already visited this node then we are done with its left subree and we have read the data in this node and we need to go right now in the right subre。



![](img/6a9b92df06a5a2551f62473daa3ab9cb_56.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_57.png)

We will have to go left as long as it's possible to go and if we can't go left anymore like here there is nothing in left of this node with value 11。

 then this is the node that I am visiting next so for a node if there is a right sub tree then in order successor would be the leftmost node in its right sub tree in ObD it would be the node with minimum value in its right sub tree。

I would say this is case 1。In this case all we need to do is we need to go as left as possible in right sub3 in Ob。

 it will also mean finding the minimum in right sub 3 leftmost node will also be the minimum in the sub3。

Now this is one case our node here had a right sub3 what would be the successor if there would be no right sub 3 what node would we visit after this node with value 8 this guy does not have a right sub3 if we have already visited this guy then we have visited its left and this node itself and there is nothing in right so we can say that right is also visited but we have not found the successor yet。



![](img/6a9b92df06a5a2551f62473daa3ab9cb_59.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_60.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_61.png)

Now where do we go from here？Well， if you remember the simulation that we had done earlier。



![](img/6a9b92df06a5a2551f62473daa3ab9cb_63.png)

We need to go to the parent of this node and if we are going to the parent from left。

 which is the case here， then the parent would be unvisited for this node with value 10。

 we just finished it slaps up 3 and we are coming back so now we can visit this node so this is my successor。



![](img/6a9b92df06a5a2551f62473daa3ab9cb_65.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_66.png)

Let's now pick another node with node Right subre what would be in order successor of this node with value 12 what node would we visit next now here once again we do not have a right subre for this node so we must go back to its parent and see if its unvisited but if we are going to the parent from right if the node that we just visited is a right childild which is the case here then the parent would already be visited because we are coming back after visiting its right sub3 this node must have been visited before going right so what should we do？

Now the recussion will roll back further and we need to go to parent of 10 and now we are going to 15 from left so this guy is unvisited so we can visit this node and this is my successor。



![](img/6a9b92df06a5a2551f62473daa3ab9cb_68.png)

If the node does not have right subre， we need to go to the nearest ancestor for which given node would be in its left subtree here for 12 we first went to 10。

 but 12 is in right subre of 10， so we went to the next ancestor 15 and 12 is in left of 15。

 so this is the nearest ancestor for which 12 is in left and hence this is my in order successor。



![](img/6a9b92df06a5a2551f62473daa3ab9cb_70.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_71.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_72.png)

This algorithm works fine， but there is an issue how do we go from a node to its parent。

 well we can design our tree such that node can have reference to its parent。



![](img/6a9b92df06a5a2551f62473daa3ab9cb_74.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_75.png)

So far in most lessons we have defined node as a structure with three fields， something like this。

 this is how we would define node in C or C++ we have one field to store data and we have two pointers to node to store reference or addresses of left and right children。



![](img/6a9b92df06a5a2551f62473daa3ab9cb_77.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_78.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_79.png)

Often it makes a lot of sense to have one more field to store the address of patent。

 we can design a tree like this and then we will not have problem forking the tree up using patent link。

 we can easily go to the ancestors。

![](img/6a9b92df06a5a2551f62473daa3ab9cb_81.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_82.png)

But what if there is no link to patent in this case what we can do is we can start at root and walk the tree from root to the given node in a BSD this is really easy for 12 we will start at root 12 is lesser than value in root。

 so we need to go left。

![](img/6a9b92df06a5a2551f62473daa3ab9cb_84.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_85.png)

And now we are at 10 now 12 is greater than 10， so we need to go right。And now we are at 12。

 if we will walk the tree from root to the given node。

 we will go through all the ancestors of the given node。



![](img/6a9b92df06a5a2551f62473daa3ab9cb_87.png)

In order successor would be the deepest node or deepest ancestor in this part for which given node would be in left sub3。

 12 has only two ancestors， we have 10 but 12 is in right of 10 and then we have 15 and 12 is in left of 15 so 15 is my successor now lets use this technique to find successor of 6。



![](img/6a9b92df06a5a2551f62473daa3ab9cb_89.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_90.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_91.png)

We will first walk down from root to this node，6 is in left for all the ancestors。

 but the best ancestor for which6 is in left is this node with value 8， so this is my successor。



![](img/6a9b92df06a5a2551f62473daa3ab9cb_93.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_94.png)

Remember we need to look at ancestors only if there is no right sub3 for six there is no right sub3。

 okay so the algorithmtum looks good， lets now write code for this。



![](img/6a9b92df06a5a2551f62473daa3ab9cb_96.png)

In my C++ code here， I'm going to write a function named Cats successor that will take a address of root node and address of another node for which we need to find the successor and this function will return address of the successor node。



![](img/6a9b92df06a5a2551f62473daa3ab9cb_98.png)

We could design this function differently instead of taking pointer to the node for which we want to find the successor as argument。

 we could just take the data as argument and for this data for this element we can find the successor node and return its address and that's why the return type here is。



![](img/6a9b92df06a5a2551f62473daa3ab9cb_100.png)

Struck node asterisk。Because we will be returning address in a pointer。



![](img/6a9b92df06a5a2551f62473daa3ab9cb_102.png)

Or what we can also do is we can return the element itself， the successor element itself。

 we can implement with any of these signatures。

![](img/6a9b92df06a5a2551f62473daa3ab9cb_104.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_105.png)

Let's implement this one， we will pass the data in current node and we will return back the address of the successor。



![](img/6a9b92df06a5a2551f62473daa3ab9cb_107.png)

Now， the first thing that we need to do is we need to search the node with this data。



![](img/6a9b92df06a5a2551f62473daa3ab9cb_109.png)

I'm going to make call to a function named find that will take address of the root node and the data and will return me pointer to the node with this data。



![](img/6a9b92df06a5a2551f62473daa3ab9cb_111.png)

If this function returns min null， that is if the data is not found in the tree。

We can simply return null。

![](img/6a9b92df06a5a2551f62473daa3ab9cb_113.png)

Else， we have the address of the current node in this point or two node that we have named current。



![](img/6a9b92df06a5a2551f62473daa3ab9cb_115.png)

Now in a BSD， this search operation will cost a big O of edge where edge is height of the tree。



![](img/6a9b92df06a5a2551f62473daa3ab9cb_117.png)

Search in aBST is not very expensive。

![](img/6a9b92df06a5a2551f62473daa3ab9cb_119.png)

We could have avoided this search if we would have passed address of the current node instead of passing the data as the second argument。



![](img/6a9b92df06a5a2551f62473daa3ab9cb_121.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_122.png)

But let's go with this， let's now find the successor of this node， if this node has right sub3。

 that is if the right sub3 is not null， we need to go to the leftmost node in the right sub3。

 I have declared a temporary pointer to node here and initially I've set it to current do right and with this while loop I will go to the leftmost node。

While there is something in the left， keep going and finally when I'll come out of this loop。

 I'll have a address off leftmost node in the right sub 3 and I can return this address this particular node will also be the node with minimum value in right sub 3。



![](img/6a9b92df06a5a2551f62473daa3ab9cb_124.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_125.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_126.png)

I'll move this code in another function， I have written this function named Find min that will return node with minimum value in a3 or sub3 in get successor function I'll simply say return find min and I'll pass the address of right childil of current node so basically I'm passing the right sub3 here。



![](img/6a9b92df06a5a2551f62473daa3ab9cb_128.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_129.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_130.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_131.png)

Okay， now let's talk about case 2。If there is no red subre what we need to do is we need to walk the tree from root till current node and we need to find the deepest ancestor for which current node will be in its left subre。



![](img/6a9b92df06a5a2551f62473daa3ab9cb_133.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_134.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_135.png)

What I'm going to do here is I'm going to declare a pointer to node named successor。



![](img/6a9b92df06a5a2551f62473daa3ab9cb_137.png)

And initially， I'll set it as null。And I'll have another point at a node named ancestor and initially I'll said this as root。

 and with this while loop we will walk the tree till we have not reached the current node to walk the tree we will use the property of binary search tree that for each node value of nodes in left is lesser and value of nodes in right is crreta。

 if data in current node is less than the data in ancestor。

 then first of all this ancestor maybe my in order successor because the current node is in its left so what we can do is we can set this guy as successor。



![](img/6a9b92df06a5a2551f62473daa3ab9cb_139.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_140.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_141.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_142.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_143.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_144.png)

And we can go left while traversing if we will find a deeper node with this property that current node will be in its left sub3。

 then successor will be updated else if the current node lies in right we simply need to move right when we'll come out of this while loop successor will either be null or it will be the address of some node。

 not all nodes in the tree will have a successor。

![](img/6a9b92df06a5a2551f62473daa3ab9cb_146.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_147.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_148.png)

Note with maximum value will not have a successor after coming out of this while loop。

 we can return the successor。

![](img/6a9b92df06a5a2551f62473daa3ab9cb_150.png)

So this is my get successor function and I think this should work you can find link to complete source code in description of this video overall time complexity of this function will be big O of edge and this is what we wanted we wanted to find successor in Big O of edge here we are already performing the search in Big O of edge finding minimum we also take big O of edge。



![](img/6a9b92df06a5a2551f62473daa3ab9cb_152.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_153.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_154.png)

And walking the tree from root to a node in BST will also take big of et。



![](img/6a9b92df06a5a2551f62473daa3ab9cb_156.png)

So overall this is big O of et if you have understood this code this logic then it should be very easy for you writing function to find in order predecessor I encourage you to write it I'll stop here now in coming lessons we will solve some more interesting problems on binary trees and binary search trees thanks for watching。



![](img/6a9b92df06a5a2551f62473daa3ab9cb_158.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_159.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_160.png)

![](img/6a9b92df06a5a2551f62473daa3ab9cb_161.png)