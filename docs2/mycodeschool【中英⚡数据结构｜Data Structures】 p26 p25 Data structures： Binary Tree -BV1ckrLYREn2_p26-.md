# mycodeschool【中英⚡数据结构｜Data Structures】 p26 p25 Data structures： Binary Tree -BV1ckrLYREn2_p26-

In our previous lesson we introduced you to tree data structure。

 we discussed tree as a logical model and talked briefly about some of the applications of tree now in this lesson we will talk a little bit more about binary trees as we have seen in our previous lesson binary tree is a tree with this property that each node in the tree can have at most two children we will first talk about some general properties of binary tree and then we can discuss some special kind of binary trees like binary search tree which is a really efficient structure for storing ordered data。



![](img/d8e59d9e754f114b089d265fc34aaea8_1.png)

![](img/d8e59d9e754f114b089d265fc34aaea8_2.png)

![](img/d8e59d9e754f114b089d265fc34aaea8_3.png)

![](img/d8e59d9e754f114b089d265fc34aaea8_4.png)

![](img/d8e59d9e754f114b089d265fc34aaea8_5.png)

![](img/d8e59d9e754f114b089d265fc34aaea8_6.png)

In a binary tree as we were saying each node can have at most two children industry that I've drawn here。

 nodes have either zero or two children， we could have a node with just one child。

 I have added one more node here and now we have a node with just one child。



![](img/d8e59d9e754f114b089d265fc34aaea8_8.png)

![](img/d8e59d9e754f114b089d265fc34aaea8_9.png)

![](img/d8e59d9e754f114b089d265fc34aaea8_10.png)

Because each node in a binary tree can have at most two children。

 we call one of the children left child and another right child。



![](img/d8e59d9e754f114b089d265fc34aaea8_12.png)

For the root node， this particular node。Is left child？And this one。Is rightchild。



![](img/d8e59d9e754f114b089d265fc34aaea8_14.png)

A node may have both left and right child and these four nodes have both left and right child or a node can have either off left and right child；

 this one has got a left child but has not got a right child。I'll add one more node here。

Now this node has a right child but does not have a left child in a program we would set the reference or pointer to left child as null。

 so we can say that for this node left child is null。

 and similarly for this node we can say that the right child is null。

 for all the other node that do not have children that are leaf node a node with zero child is called leaf node for all these node we can say that both left and right child are null。



![](img/d8e59d9e754f114b089d265fc34aaea8_16.png)

![](img/d8e59d9e754f114b089d265fc34aaea8_17.png)

![](img/d8e59d9e754f114b089d265fc34aaea8_18.png)

![](img/d8e59d9e754f114b089d265fc34aaea8_19.png)

![](img/d8e59d9e754f114b089d265fc34aaea8_20.png)

![](img/d8e59d9e754f114b089d265fc34aaea8_21.png)

Based on properties we classify binary trees into different types。

 I'll draw some more binary trees here if a tree has just one node， then also it's a binary tree。

This structure is also a binary tree。This is also a binary tree；

 remember the only condition is that a node cannot have more than two children。



![](img/d8e59d9e754f114b089d265fc34aaea8_23.png)

![](img/d8e59d9e754f114b089d265fc34aaea8_24.png)

A binary tree is called strict binary tree or proper binary tree if each node can have。

Either two or zero children this tree that I'm showing here is not a strict binary tree because we have two nodeds that have one child。

 I'll get rid of two nodeds and now this is a strict binary tree。



![](img/d8e59d9e754f114b089d265fc34aaea8_26.png)

We call a binary tree complete binary tree if all levels except possibly the last level are completely filled and all nodes are as far left as possible。

 all levels except possibly the last level will anyway be filled so the nodes at the last level if it is not filled completely must be as far left as possible right now this tree is not a complete binary tree。



![](img/d8e59d9e754f114b089d265fc34aaea8_28.png)

![](img/d8e59d9e754f114b089d265fc34aaea8_29.png)

Not it's that same depth。Can be called node at same level root node in a tree has stepped 0 depth of a node is defined as length of path from root to that node in this figure let's say node at depth0 or node at level 0。

I can simply say L0 for level 0 Now these two nodes are at level 1， these four nodes are at level 2。



![](img/d8e59d9e754f114b089d265fc34aaea8_31.png)

And finally， these two。

![](img/d8e59d9e754f114b089d265fc34aaea8_33.png)

Nors are at level 3 the maximum depth of any node in the tree is3 maximum depth of a tree is also equal to height of the tree。



![](img/d8e59d9e754f114b089d265fc34aaea8_35.png)

If we will go numbering all the levels in the tree like L0 L1 L2 and so on。

 then the maximum number of nodes that we can have at some level I will be equal to2 to the par I。

At level0， we can have one node，2 to the power0 is 1。

Then at level1 we can have at max 2 nodes at level 2 we can have2 to the par2 nodes at max which is4。

 so in general at any level I we can have at max 2 to the par i nodes。



![](img/d8e59d9e754f114b089d265fc34aaea8_37.png)

![](img/d8e59d9e754f114b089d265fc34aaea8_38.png)

You should be able to see this very clearly because each node can have two children。

 so if we have x nodes at a level then each of these x nodes can have two children。

 so at next level we can have at most two x children here in the binary tree。

 we have four nodes at level 2 which is the maximum for level 2。



![](img/d8e59d9e754f114b089d265fc34aaea8_40.png)

![](img/d8e59d9e754f114b089d265fc34aaea8_41.png)

![](img/d8e59d9e754f114b089d265fc34aaea8_42.png)

Now， each of these nodes can possibly have two children。I'm just drawing the arrows here。

 so at level 3 we can have max2 times 4 that is eight nodes。



![](img/d8e59d9e754f114b089d265fc34aaea8_44.png)

Now for a complete binary tree， all the levels have to be completely filled。



![](img/d8e59d9e754f114b089d265fc34aaea8_46.png)

We can give exception to the last level or theest level， it doesnt have to be full。

 but the nodes have to be as left as possible。This particular tree that I'm showing here is not a complete binary tree because we have two vacant node positions in left here I'll do slight change in this structure now this is a complete binary tree we can have more node at level tree but there should not be a vacant position in left I have added one more node here and this still is a complete binary tree。



![](img/d8e59d9e754f114b089d265fc34aaea8_48.png)

![](img/d8e59d9e754f114b089d265fc34aaea8_49.png)

![](img/d8e59d9e754f114b089d265fc34aaea8_50.png)

If all the levels are completely filled such a binary tree can also be called perfect binary tree in a perfect binary tree all levels will be completely filled if h is the height of a perfect binary tree。

 remember height of a binary tree is length of longest part between root to any of the leaf nodes or I should say number of edges in longest part from root to any of the leaf nodes height of a binary tree will also be equal to max stepped。



![](img/d8e59d9e754f114b089d265fc34aaea8_52.png)

![](img/d8e59d9e754f114b089d265fc34aaea8_53.png)

![](img/d8e59d9e754f114b089d265fc34aaea8_54.png)

Here for this binary tree， height or max stepis3 maximum number of nodes in a tree with height edge will be equal to will have2 to the par0 node at level 02 to the par 1 node at level 1 and well go on summing for height edge will go till2 to the par edge at the best level we will have2 to the par edge nodes。



![](img/d8e59d9e754f114b089d265fc34aaea8_56.png)

![](img/d8e59d9e754f114b089d265fc34aaea8_57.png)

Now this will be equal to 2 to the power h plus 1。in-1。H plus 1 is number of levels here。

 we can also say2 to the par number of levels minus1。In this three number of levels is 4。

 we have L0 till L3， so number of nodes， maximum number of nodes will be。2 to the par 4 minus1。

 which is 15， so a perfect binary tree will have maximum number of nodes possible for a height because all levels will be completely filled。



![](img/d8e59d9e754f114b089d265fc34aaea8_59.png)

Well， I should say maximum number of nodes in a binary tree with height edge。

Okay I can ask you this also what will be height of a perfect binary tree with n nodes let's say n is number of nodes in perfect binary 3 to find out how height will have to solve this equation n equal 2 to the par h plus 1 minus1 because if height is edge number of nodes will be 2 to the power h plus 1 minus1 we can solve this equation and the result will be this remember n is number of nodes here I'll leave the maths for you to understand height will be equal to log n plus 1 to the base 2 minus1。



![](img/d8e59d9e754f114b089d265fc34aaea8_61.png)

![](img/d8e59d9e754f114b089d265fc34aaea8_62.png)

![](img/d8e59d9e754f114b089d265fc34aaea8_63.png)

In this perfect binary tree that Im showing here， number of nodes is 15， so n is 15。

 n plus 1 will be 16， so the h will be log 16 to the base2。inus1 log 16 to the base 2 will be 4。

 so the final value will be 4 minus1 equal 3。

![](img/d8e59d9e754f114b089d265fc34aaea8_65.png)

In general， for a complete binary tree。We can also calculate height as flow off log n to the base2。

 so we need to take integral part of log n to the base2 perfect binary tree is also a complete binary tree here n is 15 log of 15 to base 2 is。

3。906891 if well take the integral part then this will be 3 Ill not go into proof of how height of complete binary 3 will be log n to the base2 we will try to see that later。



![](img/d8e59d9e754f114b089d265fc34aaea8_67.png)

![](img/d8e59d9e754f114b089d265fc34aaea8_68.png)

![](img/d8e59d9e754f114b089d265fc34aaea8_69.png)

All these maps will be really helpful when we will analyze cost of various operations on binary tree。



![](img/d8e59d9e754f114b089d265fc34aaea8_71.png)

Cost of a lot of operations on tree in terms of time depends upon the height of tree。

 for example in binary search tree which is a special kind of binary tree， the cost of searching。

 inserting or removing an element in terms of time is proportional to the height of tree so in such case we would want the height of the tree to be less height of a tree will be less if the tree will be dense if the tree will be close to a perfect binary tree or a complete binary tree。



![](img/d8e59d9e754f114b089d265fc34aaea8_73.png)

![](img/d8e59d9e754f114b089d265fc34aaea8_74.png)

![](img/d8e59d9e754f114b089d265fc34aaea8_75.png)

![](img/d8e59d9e754f114b089d265fc34aaea8_76.png)

![](img/d8e59d9e754f114b089d265fc34aaea8_77.png)

Minimum height of a tree with n nodes can be log n to the base2 when the tree will be a complete binary tree。



![](img/d8e59d9e754f114b089d265fc34aaea8_79.png)

If we will have an arrangement like this， then the tree will have maximum height with n nodes。

 minimum height possible is flow off or integral part of log into the base 2。

 and maximum height possible with n nodes is n minus1 when we will have a sparse tree like this which is as good as a linked list。



![](img/d8e59d9e754f114b089d265fc34aaea8_81.png)

![](img/d8e59d9e754f114b089d265fc34aaea8_82.png)

![](img/d8e59d9e754f114b089d265fc34aaea8_83.png)

Now think about this， if I'm saying that time taken for an operation is proportional to height of the tree。

 or in other words I can say that if time complexity of an operation is big o of edge where edge is height of the binary tree。

 then for a complete or perfect binary tree， my time complexity will be big o of log n to the base2。



![](img/d8e59d9e754f114b089d265fc34aaea8_85.png)

![](img/d8e59d9e754f114b089d265fc34aaea8_86.png)

![](img/d8e59d9e754f114b089d265fc34aaea8_87.png)

![](img/d8e59d9e754f114b089d265fc34aaea8_88.png)

And in worst case， for this past three my time complexity will be big go of n。

Order of log n is almost best running time possible for n as high as 2 to the par 00。

 log n to the base 2 is just 100。With order of n running time if n will be 2 to the power 00。

 we won't be able to finish our computation in ears even with most powerful machines ever made so here's the thing quite often we want to keep the height of a binary tree minimum possible or most commonly we say that we try to keep a binary tree balanced we call a binary tree balanced binary tree if for each node the difference between height of left and right sub tree is not more than some number k mostly k would be1 so we can say that for each node difference between height of left and right sub tree should not be more than one there is something that I want to talk about height of a tree we had defined height earlier as number of edges in longest path from root to a leaf height of a tree with just one node where the node itself will be a leaf node will be0 we can define an empty tree as a tree with no node。



![](img/d8e59d9e754f114b089d265fc34aaea8_90.png)

![](img/d8e59d9e754f114b089d265fc34aaea8_91.png)

![](img/d8e59d9e754f114b089d265fc34aaea8_92.png)

![](img/d8e59d9e754f114b089d265fc34aaea8_93.png)

![](img/d8e59d9e754f114b089d265fc34aaea8_94.png)

![](img/d8e59d9e754f114b089d265fc34aaea8_95.png)

![](img/d8e59d9e754f114b089d265fc34aaea8_96.png)

![](img/d8e59d9e754f114b089d265fc34aaea8_97.png)

![](img/d8e59d9e754f114b089d265fc34aaea8_98.png)

![](img/d8e59d9e754f114b089d265fc34aaea8_99.png)

And we can say that height of an empty  tree is minus1。



![](img/d8e59d9e754f114b089d265fc34aaea8_101.png)

So height of3 with just one node is0 and height of an empty3 is minus1 Qui often people calculate height as number of nodes in longest path from root to a leaf in this figure I have drawn one of the longest path from root to a leaf we have three edges in this path so the height is3 if we will count number of nodes in the path height will be four this looks very intuitive and I have seen this definition of height at a lot of places if we will count the nodes height of3 with just one node will be equal to1 and then we can say height of an empty tree will be0 but this is not the correct definition and we are not going to use this assumption we are going to say say that height of an empty3 is minus1 and height of3 with one node is0。



![](img/d8e59d9e754f114b089d265fc34aaea8_103.png)

![](img/d8e59d9e754f114b089d265fc34aaea8_104.png)

![](img/d8e59d9e754f114b089d265fc34aaea8_105.png)

![](img/d8e59d9e754f114b089d265fc34aaea8_106.png)

![](img/d8e59d9e754f114b089d265fc34aaea8_107.png)

![](img/d8e59d9e754f114b089d265fc34aaea8_108.png)

![](img/d8e59d9e754f114b089d265fc34aaea8_109.png)

![](img/d8e59d9e754f114b089d265fc34aaea8_110.png)

The difference between height of left and right subrees of a node can be calculated as absolute value of height of left subre minus height of right subre。

 and in this calculation height of a subre can be minus1 also for this leaf node here in this figure both left and right subtrees are empty。

So both h left or height of left sub3 and h right or height of right sub3 will be minus1。

 but the difference overall will be 0 for all nodes in a perfect tree difference will be0 I have got rid of some nodes in this tree and now by the side of each node I have written the value of TIF this is still a balanced binary tree because the maximum diff for any node is1 let's get rid of some bold nodes in this tree and now this is not balanced because one of the nodes has Tff2。



![](img/d8e59d9e754f114b089d265fc34aaea8_112.png)

![](img/d8e59d9e754f114b089d265fc34aaea8_113.png)

![](img/d8e59d9e754f114b089d265fc34aaea8_114.png)

For this particular node， height of left subre is1 and height of right subre is minus1 because right subtre is empty。



![](img/d8e59d9e754f114b089d265fc34aaea8_116.png)

So the absolute value of difference is 2。We try to keep a tree balanced to make sure it tense and its height is minimized if height is minimized cost of various operations that depend upon height are minimized okay the next thing that I want to talk about very briefly is how we can store binary trees in memory。



![](img/d8e59d9e754f114b089d265fc34aaea8_118.png)

![](img/d8e59d9e754f114b089d265fc34aaea8_119.png)

![](img/d8e59d9e754f114b089d265fc34aaea8_120.png)

One of the ways that we had seen in our previous lesson。

 which is most commonly used is dynamically created nodes linked to each other using pointers or references for a binary tree of integers in CRC++ we can define a node like this。



![](img/d8e59d9e754f114b089d265fc34aaea8_122.png)

![](img/d8e59d9e754f114b089d265fc34aaea8_123.png)

![](img/d8e59d9e754f114b089d265fc34aaea8_124.png)

Data type is integer， so we have a field to store data， and we have two pointer variables。

 one to store address of left child and another to store address of right childil。



![](img/d8e59d9e754f114b089d265fc34aaea8_126.png)

![](img/d8e59d9e754f114b089d265fc34aaea8_127.png)

This of course， is the most common way， node dynamicically created at random locations in memory linked together through pointers。



![](img/d8e59d9e754f114b089d265fc34aaea8_129.png)

![](img/d8e59d9e754f114b089d265fc34aaea8_130.png)

But in some special cases we use arrays also arrays are typically used for complete binary trees。

 I have drawn a perfect binary tree here， let's say this is a tree of integers。

 what we can do is we can number these nodes from0 starting at root and going level by level from left to right so well go like01 to。



![](img/d8e59d9e754f114b089d265fc34aaea8_132.png)

3，4，5 and。6。Now I can create an array of seven integers and these numbers can be used as indices for these nodes。

 so at zeroth position I'll fill 2 at1 eighth position I'll fill 4 at width position will have one and I'll go on like this。



![](img/d8e59d9e754f114b089d265fc34aaea8_134.png)

![](img/d8e59d9e754f114b089d265fc34aaea8_135.png)

We have filled in all the data in the array but how will we store the information about the links。

 how will we know that the left child of root has value 4 and the right child of root has value 1 well in case of complete binary tree if we will number the nodes like this then for a node that index I。



![](img/d8e59d9e754f114b089d265fc34aaea8_137.png)

![](img/d8e59d9e754f114b089d265fc34aaea8_138.png)

The index of left child will be 2 i+ 1 and the index of right child will be 2 i+ 2 and remember this is true only for a complete binary tree for0 left child is 2 i plus 1 for I equals0 will be 1。



![](img/d8e59d9e754f114b089d265fc34aaea8_140.png)

![](img/d8e59d9e754f114b089d265fc34aaea8_141.png)

![](img/d8e59d9e754f114b089d265fc34aaea8_142.png)

And 2 i+ 2 will be 2 now for one left child is at index 3， right child is at index 4 for I equal 2。

 2 i+ 1 will be 5 and 2 i+ 2 will be 6。

![](img/d8e59d9e754f114b089d265fc34aaea8_144.png)

![](img/d8e59d9e754f114b089d265fc34aaea8_145.png)

We will discuss our implementation in detail when we will talk about a special kind of binary tree called HeEap or is that used to implement heaps。

 I'll stop here now in our next lesson we will talk about binary search tree which is also a special kind of binary tree that gives us a really efficient storing structure in which we can search something quickly as well as update it quickly。

 this is it for this lesson thanks for watching。

![](img/d8e59d9e754f114b089d265fc34aaea8_147.png)