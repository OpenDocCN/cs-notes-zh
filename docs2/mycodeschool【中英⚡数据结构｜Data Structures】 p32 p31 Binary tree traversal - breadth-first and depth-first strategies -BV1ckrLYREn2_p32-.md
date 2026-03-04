# mycodeschool【中英⚡数据结构｜Data Structures】 p32 p31 Binary tree traversal - breadth-first and depth-first strategies -BV1ckrLYREn2_p32-

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_0.png)

In this lesson， we are going to talk about binary tree traversal。When we are working with trees。

 we may often want to visit all the nodes in the tree。



![](img/724d2fd46ae09dbe6c5bac8aa71d2854_2.png)

Now tree is not a linear data structure like array or linked list。



![](img/724d2fd46ae09dbe6c5bac8aa71d2854_4.png)

In a linear data structure， there would be a logical start and a logical end。

 so we can start with a pointer at one of the ends and keep moving it towards the other end。



![](img/724d2fd46ae09dbe6c5bac8aa71d2854_6.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_7.png)

For a linear data structure like linked list， for each node or element we would have only one next element。

 but tree is not a linear data structure I have drawn a binary tree here。

 data type is character this time fill in these characters in the nodes now for a tree at any time if we are pointing to a particular node then we can have more than one possible directions we can have more than one possible next nodes。



![](img/724d2fd46ae09dbe6c5bac8aa71d2854_9.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_10.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_11.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_12.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_13.png)

In this binary tree， for example， if we will start with the pointer at root node。

 then we have two possible directions from F we can either go left to D or we can go right to J and of course if we will go in one direction。



![](img/724d2fd46ae09dbe6c5bac8aa71d2854_15.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_16.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_17.png)

Then we will somehow have to come back and go into the other direction later。



![](img/724d2fd46ae09dbe6c5bac8aa71d2854_19.png)

So tree traversal is not so straightforward and what we are going to discuss in this lesson is algorithms for tree traversal tree traversal can formally be defined as the process of visiting each node in the tree exactly once in some order and by visiting a node we mean reading or processing data in the node for us in this lesson visit will mean printing the data in the node based on the order in which nodes are visited tree traversal algorithms can broadly be classified into two categories we can either go breadth first or we can go depth first。



![](img/724d2fd46ae09dbe6c5bac8aa71d2854_21.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_22.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_23.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_24.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_25.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_26.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_27.png)

Breakfast traversal and depth first traversal are general techniques to traverse or search a graph graphra is a data structure and we have not talked about graph so far in this series we will discuss graph in later lessons for now just know that tree is only a special kind of craft and in this lesson we are going to discuss breakfast and depth first traversal in context of trees in a tree in breakfast approach we would visit all the node at same depth or level before visiting the node at next level。



![](img/724d2fd46ae09dbe6c5bac8aa71d2854_29.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_30.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_31.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_32.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_33.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_34.png)

In this binary tree that I'm showing here this node with value F which is the root node is at level 0。

 I'm writing L0 here for level 0 depth of a node is defined as number of edges in path from root to that node a root node would have depth 0 these two nodes D and J are at depth1 so we can say that these nodes are at level 1 now these four nodes are at level 2 these three nodes are at level 3。



![](img/724d2fd46ae09dbe6c5bac8aa71d2854_36.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_37.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_38.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_39.png)

And finally， this node with value H is at level 4。

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_41.png)

So what we can do in breakfast approaches。

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_43.png)

That we can start at level0， we would have only one node at level0 the root node so we can visit the root node。

 I'll write the value in the node as I'm visiting it now level0 is done now I can go to level1 and visit the nodes from left to right so after f we would visit T and then we would visit J。



![](img/724d2fd46ae09dbe6c5bac8aa71d2854_45.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_46.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_47.png)

And now we are done with level1 so we can go to level 2。 we will go like B， then E then。



![](img/724d2fd46ae09dbe6c5bac8aa71d2854_49.png)

G and then K， and now we can go to level 3。

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_51.png)

AC and I， and finally I can go to level 4。This kind of breakfast traveral in case of trees is called level order traversal and we will discuss how we can do this programmatically in some time。

 but this is the order in which we would visit the nodes we would go level by level from left to right in breakfast approach for any node we visit all its children before visiting any of its grandchildren。



![](img/724d2fd46ae09dbe6c5bac8aa71d2854_53.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_54.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_55.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_56.png)

In this tree first we are visiting F and then we are visiting D and then we are not going to any child of D like B or E along the depth。

 next we are going to J， but in depth first approach if we would go to a child we would complete the whole subre of the child before going to the next child。



![](img/724d2fd46ae09dbe6c5bac8aa71d2854_58.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_59.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_60.png)

In this ex tree here from F， the root node， if we are going left to D。

 then we should visit all the nodes in this left sub3。

 that is we should finish this left sub3 in its complete depth。

 or in other words we should finish all the grandchildren of F along this path before going to right child of F J。



![](img/724d2fd46ae09dbe6c5bac8aa71d2854_62.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_63.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_64.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_65.png)

And once again， when we will go to J， we will visit all the grandchildren along this path。

 so basically we will visit the complete right subre。



![](img/724d2fd46ae09dbe6c5bac8aa71d2854_67.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_68.png)

In depth first approach the relative order of visiting the left sub3 the right sub3 and the root node can be different；

 for example we can first visit the right sub3 and then the root and then the left sub3。



![](img/724d2fd46ae09dbe6c5bac8aa71d2854_70.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_71.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_72.png)

or we can do something like we can first visit the root and then the left subre and then the right subre so the relative order can be different but the core idea in depth first strategy is that visiting a child is visiting the complete subre in that path。



![](img/724d2fd46ae09dbe6c5bac8aa71d2854_74.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_75.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_76.png)

And remember visiting a node is reading， processing or printing the data in that node based on the relative order of left subt。

 right subre and root there are three popular depth first strategies One way is that we can first visit the root node。



![](img/724d2fd46ae09dbe6c5bac8aa71d2854_78.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_79.png)

Then the left subre。

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_81.png)

And then the right subtre， left and right subtes will be visited recursively in same manner。

 such a traveral is called preorder traveral。

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_83.png)

Another way is that we can first visit the left subre， then the root， and then the right subre。

Such a traversal is called in order traversal。And if root is visited after left and right subtreed then such a traveral is called post order traversal。



![](img/724d2fd46ae09dbe6c5bac8aa71d2854_85.png)

In total there are six possible permutations for left right and root but conventionally left subree is always visited before the right subree。

 so these are the three strategies that we use only the position of root is changing here if it's before left and right then it's preorder if its in between its in order and if its after left and right subrees then it post order there is an easy way to remember these three depth first algorithms。

 if we can denote visiting a node or reading the data in that node with letter D going to the left subree as L and going to the right subre as R。



![](img/724d2fd46ae09dbe6c5bac8aa71d2854_87.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_88.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_89.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_90.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_91.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_92.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_93.png)

So if we can say d for data L for left and R for right。

 then in preorder for each node we will go DLr， first we will read the data in that node then we will go left and once the left sub3 is done we will go right in in order traveral first we will finish the left sub3 then we will read the data in current node and then we will go right in post order for each node first we will go left once left sub3 is done we will go right and then we will read the data in current node。



![](img/724d2fd46ae09dbe6c5bac8aa71d2854_95.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_96.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_97.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_98.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_99.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_100.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_101.png)

So preorder is data left right in order is left data right and post order is left right and then data preorder in order and post order are really easy and intuitive to implement using recursion。

 but we will discuss implementation later， let's now see what will be the preorder in order and post order traver cell for this tree that haveron you。



![](img/724d2fd46ae09dbe6c5bac8aa71d2854_103.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_104.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_105.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_106.png)

Lets foresee what will be the preorder traveral for this binary tree we need to start at root node and for each node we first need to read the data or in other words visit that node in fact instead of DLR we could have said VLR here。

 V for visit we can use any of these assumptions v for visit or D for data I will go with DLR here。



![](img/724d2fd46ae09dbe6c5bac8aa71d2854_108.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_109.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_110.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_111.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_112.png)

So lets start at the root for each node we first need to read the data I'm writing F here the data that I just read and now I need to go left and finish the complete left sub3 and once all the nodes in the left sub3 are visited then only I can go to the right sub3 the problem here is actually getting reduced in a self-s or recursive manner now we need to focus on this left sub3 now we are at D root of this left sub3 of F once again for this node we will first read the data。



![](img/724d2fd46ae09dbe6c5bac8aa71d2854_114.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_115.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_116.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_117.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_118.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_119.png)

And now we can go left we will go towards E only when these three nodes A B and C will be done now we are focusing on this subt comprising of these three nodes now we are at B we can read the data and now we can go left to a there is nothing in left of a so we can say that for left。



![](img/724d2fd46ae09dbe6c5bac8aa71d2854_121.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_122.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_123.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_124.png)

For a left sub3 is done and there is nothing in right as well。

 so we can say right is also done now for B left subre is done so we can go right to C and left and right of C are null。



![](img/724d2fd46ae09dbe6c5bac8aa71d2854_126.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_127.png)

And now for D， left subre is done so we can go right。



![](img/724d2fd46ae09dbe6c5bac8aa71d2854_129.png)

Once again for E left and right and null and now at this stage for F complete left sub 3 is visited so we can go right now we need to go left of and there is nothing in left of G so we can go right。



![](img/724d2fd46ae09dbe6c5bac8aa71d2854_131.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_132.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_133.png)

And now we can go left off I。

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_135.png)

For edge there is nothing in left and right now at this stage left subre of I is done and right subre is null。



![](img/724d2fd46ae09dbe6c5bac8aa71d2854_137.png)

And now we can go back to J the left sub3 for J is done so we can go to its right sub3 Finally we have K here and we are done with all the nodes。



![](img/724d2fd46ae09dbe6c5bac8aa71d2854_139.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_140.png)

This is how we can perform a preorder traversal manually actual implementation would be a simple recursion and we will discuss it later。

 lets now see what will be the in order traversal for this binary tree。



![](img/724d2fd46ae09dbe6c5bac8aa71d2854_142.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_143.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_144.png)

In in order traveral， we will first finish visiting the left subree。

 then visit the current node and then go right once again we will start at the root and we will first go left。



![](img/724d2fd46ae09dbe6c5bac8aa71d2854_146.png)

Now we will first finish this sub3。

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_148.png)

Once again for D， we will first go left to B and from B。

 we will go to a now for a there is nothing in left so we can say that for this guy left subre is done so we can read the data。



![](img/724d2fd46ae09dbe6c5bac8aa71d2854_150.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_151.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_152.png)

And now we can go to its right， but there is nothing in right as well。

So this guy is done now for B left subre is done so we can read the data。



![](img/724d2fd46ae09dbe6c5bac8aa71d2854_154.png)

And now for B we can go right for C once again there is nothing in left so we can read the data and there is nothing in right as well now left of D is completely done so we can visit it。

 read the data here now we can go to its right to E for E once again left and right and null at this stage left sub3 of f is done so we can read on the data。



![](img/724d2fd46ae09dbe6c5bac8aa71d2854_156.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_157.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_158.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_159.png)

And now we can go to right of F if we will go on like this。

 this finally will be my in order traversal。

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_161.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_162.png)

This tree that I'm showing here is actually a binary search tree for each node the value of nodes in left is lesser and the value of nodes in right is crter so if we are printing in this order left subre and then the current node and then the right subre then we would get a sorted list in order revveral of a binary search tree would give you a sorted list okay now you should be able to figure out the post order reversal this is what we will get for post order reversal。



![](img/724d2fd46ae09dbe6c5bac8aa71d2854_164.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_165.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_166.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_167.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_168.png)

Ill leave it for you to see whether this is correct or not。 I'll stop here now。 In next lesson。

 we will discuss implementation of these three traverseal algorithm algorithms。 Thanks for watching。



![](img/724d2fd46ae09dbe6c5bac8aa71d2854_170.png)

![](img/724d2fd46ae09dbe6c5bac8aa71d2854_171.png)