# mycodeschool【中英⚡数据结构｜Data Structures】 p27 p26 Data structures： Binary Search Tree -BV1ckrLYREn2_p27-

In our previous lesson we talked about binary trees in general now in this lesson we are going to talk about binary search tree。

 a special kind of binary tree， which is an efficient structure to organize data for quick search as well as quick update but before I start talking about binary search trees I want you to think of a problem。



![](img/bb7151e6bd3062ace2030a53bb8a53a8_1.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_2.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_3.png)

What data structure will you use to store a modifiable collection？



![](img/bb7151e6bd3062ace2030a53bb8a53a8_5.png)

So let's say you have a collection and it can be a collection of any data type。

 records in the collection can be of any type。

![](img/bb7151e6bd3062ace2030a53bb8a53a8_7.png)

Now you want to store this collection in computer's memory in some structure。

 and then you want to be able to quickly search for a record in the collection and you also want to be able to modify the collection。



![](img/bb7151e6bd3062ace2030a53bb8a53a8_9.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_10.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_11.png)

You want to be able to insert an element in the collection or remove an element from the collection。



![](img/bb7151e6bd3062ace2030a53bb8a53a8_13.png)

So what data structure will you use？Well， you can use an array or a linked list。



![](img/bb7151e6bd3062ace2030a53bb8a53a8_15.png)

These are two well known data structures in which we can store a collection now what will be the running time of these operations search insertion or removal if we will use an array or a linked list let's first talk about arrays and for sake of simplicity let's say we want to store integers to store a modifiable list or collection of integers we can create a large enough array and we can store the records in some part of the array we can keep the end of the list marked in this array that I'm showing here we have integers from zero tilll 3 we have records from zero tilll 3 and rest of the array is available space。



![](img/bb7151e6bd3062ace2030a53bb8a53a8_17.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_18.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_19.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_20.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_21.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_22.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_23.png)

Now to search some X in the collection。We will have to scan the array from index 0 till end and in worst case we may have to look at all the elements in the list。



![](img/bb7151e6bd3062ace2030a53bb8a53a8_25.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_26.png)

If n is the number of elements in the list， time taken will be proportional to n。

 or in other words we can say that time complexity of this operation will be bigu of n。



![](img/bb7151e6bd3062ace2030a53bb8a53a8_28.png)

Okay， now what will be the cost of insertion， let's say we want to insert number 5 in this list。

 so if there is some available space。

![](img/bb7151e6bd3062ace2030a53bb8a53a8_30.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_31.png)

All these cells in yellow are available， we can add one more cell by incrementing this marker end and we can fill in the integer to be added。



![](img/bb7151e6bd3062ace2030a53bb8a53a8_33.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_34.png)

The time taken for this operation will be constant running time will not depend upon number of elements in the collection so we can say that time complexity will be big go of1。



![](img/bb7151e6bd3062ace2030a53bb8a53a8_36.png)

Okay， now what about removal， let's say we want to remove one from the collection。

 what we'll have to do is we will have to shift all records to the right of one。😊。



![](img/bb7151e6bd3062ace2030a53bb8a53a8_38.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_39.png)

By one position to the left and then we can decrement n the cost of removal in worst case once again will be big go of n in worst case。

 we will have to shift n minus1 elements。Here the cost of insertion will be be go of one if the array will have some available space。

 so the array has to be large enough。

![](img/bb7151e6bd3062ace2030a53bb8a53a8_41.png)

If the array gets filled， what we can do is we can create a new larger array。



![](img/bb7151e6bd3062ace2030a53bb8a53a8_43.png)

Typically we create an array twice the size of the filled up array so we can create a new large array and then we can copy the content of the field up array into this new large array the copy operation will cost us big O of n we have discussed this idea of dynamic array quite a bit in our previous lessons so insertion will be big o of1 if array is not filled up and it will be big o of n if array is filled up。



![](img/bb7151e6bd3062ace2030a53bb8a53a8_45.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_46.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_47.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_48.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_49.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_50.png)

For now， let's just assume that the array will always be large enough。

Let's now discuss the cost of these operations if we will use a linked list。



![](img/bb7151e6bd3062ace2030a53bb8a53a8_52.png)

If we would use a linked list， I have drawn a linked list of integers here。

 data type can be anything， the cost of search operation once again will be big O of n where n is number of records in the collection or number of nodes in the linked list to search in worst case we will have to traverse the whole list。

 we will have to look at all the nodes， the cost of insertion in a linked list is big O of1 at head。



![](img/bb7151e6bd3062ace2030a53bb8a53a8_54.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_55.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_56.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_57.png)

And its big O of n at tail we can choose to insert at head to keep the cost low。

 so running time of insertion we can say is big O of 1 or in other words we will take constant time。



![](img/bb7151e6bd3062ace2030a53bb8a53a8_59.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_60.png)

Removal once again will be we go off in， we will first have to traverse the linked list and search the record and in worst case we may have to look at all the nodes。



![](img/bb7151e6bd3062ace2030a53bb8a53a8_62.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_63.png)

Okay， so this is the cost of operations if we are going to use array or linked list insertion definitely is fast。

 but how good is big O of n for an operational like search？



![](img/bb7151e6bd3062ace2030a53bb8a53a8_65.png)

What do you think？

![](img/bb7151e6bd3062ace2030a53bb8a53a8_67.png)

If we are searching for a record X， then in the worst case。

 we will have to compare this record x with all the end records in the collection。



![](img/bb7151e6bd3062ace2030a53bb8a53a8_69.png)

Let's say our machine can perform a million comparisons in one second。

 so we can say that machine can perform 10 to the par 6 comparisons in one second。

 so cost of one comparison will be 10 to the par minus6 second。



![](img/bb7151e6bd3062ace2030a53bb8a53a8_71.png)

Machines in today's world deal with really large data it's very much possible for real world data to have100 million or billion records a lot of countries in this world have population more than 100 million two countries have more than a billion people living in them if we will have data about all the people living in a country then it can easily be 100 million records okay so if we are saying that the cost of one comparison is10 to the minus6 second if n will be 100 million。



![](img/bb7151e6bd3062ace2030a53bb8a53a8_73.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_74.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_75.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_76.png)

Time taken will be 100 seconds。

![](img/bb7151e6bd3062ace2030a53bb8a53a8_78.png)

H0undd seconds for a search is not reasonable， and search may be a frequently performed operation。

Can we do something better， can we do better than we go of n Well in an array we can perform binary search if its sorted。



![](img/bb7151e6bd3062ace2030a53bb8a53a8_80.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_81.png)

And the running time of binary search is big O off log in which is the best running time to have I have drawn this array of integers here records in the array are sorted here the data type is integer for some other data type or some complex data type we should be able to sort the collection based on some property or some key of the records we should be able to compare the keys of records and the comparison logic will be different for different data types for a collection of strings for example we may want to have the records sorted in dictionary or lexxiographical order so we will compare and see which string will come first in dictionary order now this is the requirement that we have for binary search the data structure should be an array and the records must be sorted。



![](img/bb7151e6bd3062ace2030a53bb8a53a8_83.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_84.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_85.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_86.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_87.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_88.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_89.png)

Okay so the cost of search operation can be minimized if we will use a sorted array。

 but in insertion or removal we will have to make sure that the array is sorted afterwards in this array if I want to insert number 5 at this stage。

 I cant simply put5 at index 6。

![](img/bb7151e6bd3062ace2030a53bb8a53a8_91.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_92.png)

What I'll have to do is I'll first have to find the position at which I can insert5 in the sorted list。

 we can find the position in order of log n time using binary search。

 we can perform binary search to find the first integer greater than 5 in the list so we can find the position quickly in this case its index2 but then we will have to shift all the records starting this position。



![](img/bb7151e6bd3062ace2030a53bb8a53a8_94.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_95.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_96.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_97.png)

One position to the right。

![](img/bb7151e6bd3062ace2030a53bb8a53a8_99.png)

And now I can insert5。So even though we can find the position at which a records should be inserted quickly in big O of log n。

 this shifting inverse case will cost us by go of n。

 so the running time overall for an insertion will be big o of n and similarly the cost of removal will also be big go of n we will have to shift some records okay so when we are using sorted array cost of search operation is minimized in binary search for n records we will have at max log n to the base2 comparisons so if we can compare if we can perform million comparisons in a second then for n equal 2 to the par 31 which is greater than 2 billion we are going to take only 31 microseconds。



![](img/bb7151e6bd3062ace2030a53bb8a53a8_101.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_102.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_103.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_104.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_105.png)

Log of 2 to the part 31 to base 2 will be 31。Okay we are fine with search now we will be good for any practical value of n but what about insertion and removal there are still big O of n can we do something better here well if we will use this data structure called binary search tree I'm writing it in short BST for binary search tree then the cost of all these three operations can be big o off log n in average case the cost of all the operations will be big o of n in worst case but we can avoid the worst case by making sure that the tree is always balanced we have talked about balanced binary tree in our previous lesson binary search tree is only a special kind of binary tree to make sure that the cost of these operations is always big o of log n we should keep the binary search tree balanced we'll talk about this in detail later let's first see what a binary search tree is and how cost of these operations is minimized when we use a。



![](img/bb7151e6bd3062ace2030a53bb8a53a8_107.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_108.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_109.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_110.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_111.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_112.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_113.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_114.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_115.png)

And research tree。Binary search tree is a binary tree in which for each node value of all the nodes in left subtree is lesser and value of all the nodes in right subte is crreter。



![](img/bb7151e6bd3062ace2030a53bb8a53a8_117.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_118.png)

I have drawn binary tree as a recursive structure here。

 as we know in a binary tree each node can have at most two children。

 we can call one of the children left child if we will look at the tree as a recursive structure left child will be the root of left subre and similarly right child will be the root of right subre now for a binary tree to be called binary search tree value of all the nodes in left subree must be lesser。

 or we can say lesser or equal to handle duplicates。



![](img/bb7151e6bd3062ace2030a53bb8a53a8_120.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_121.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_122.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_123.png)

And the value of all the nodes in right sub3 must be greater。And this must be true for all the nodes。

 so in this recursive structure here both left and right subtes must also be binary search trees。



![](img/bb7151e6bd3062ace2030a53bb8a53a8_125.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_126.png)

I'll draw a binary search tree of integers Now I have drawn a binary search tree of integers here let's see whether this property that for each node value of all the nodes in left subree must be lesser or equal and value of all the nodes in right sub3 must be greaterter is true or not let's first look at the root node nodes in the left sub3 have values 108 and 12 so they are all lesser than 15 and in right subree we have 1720 and 25 they are all greater than 15 so we are good for the root node now let's look at this node with value 10 in left we have8 which is lesser。



![](img/bb7151e6bd3062ace2030a53bb8a53a8_128.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_129.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_130.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_131.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_132.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_133.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_134.png)

In right we have 12 which is greater， so we are good。

 we are good for this node2 having value 20 and we don't need to bother about leaf nodes because they do not have children。

 so this is a binary search tree。

![](img/bb7151e6bd3062ace2030a53bb8a53a8_136.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_137.png)

Now what if I change this value 12？16 now is there still a binary search tree well for node with value 10 we are good the node with value 16 is in its right。

 so not a problem but for the root node we have a node in left sub tree with higher value now so this tree is not a binary search  tree Ill revert back and make the value 12 again。



![](img/bb7151e6bd3062ace2030a53bb8a53a8_139.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_140.png)

Now as we were saying we can search insert or delete in a binary search tree in big O off log n time in average case。

 how is it really possible let's first talk about search if these integers that I have here in the tree were in a sorted array we could have performed binary search and what do we do in binary search let's say we want to search number 10 in this array。

 what we do in binary searches we first define the complete list as our search space。



![](img/bb7151e6bd3062ace2030a53bb8a53a8_142.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_143.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_144.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_145.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_146.png)

The number can exist only within the search space。 I'll mark search space using these two pointers start and end。

 Now we compare the number to be searched or the element to be searched with。



![](img/bb7151e6bd3062ace2030a53bb8a53a8_148.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_149.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_150.png)

Mid element of the search space or the median and if the record being searched if the element being searched is lesser we go searching in the left half else we go searching in the right half in case of equality we have found the element in this case 10 is lesser than 15 so we will go searching towards left our search space is reduced now to half once again we will compare to the mid element and bingo this time we have got a match。



![](img/bb7151e6bd3062ace2030a53bb8a53a8_152.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_153.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_154.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_155.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_156.png)

In binary search we start with n elements in search space and then if mid element is not the element that we are looking for。

 we reduce the search space to n by 2 and we go on reducing the search space2 half till we either find the record that we are looking for or we get to only one element in search space and be done in this whole reduction if we will go from n to n by 2 to n by4 to n by8 and so on。

 we will have log n to the base two steps。

![](img/bb7151e6bd3062ace2030a53bb8a53a8_158.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_159.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_160.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_161.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_162.png)

If we are taking k steps， then n upon 2 to the par k will be equal to 1。

 which will imply 2 to the par k will be equal to n and k will be equal to log n to the base 2。



![](img/bb7151e6bd3062ace2030a53bb8a53a8_164.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_165.png)

So this is why running time of binary search is big O of log n。



![](img/bb7151e6bd3062ace2030a53bb8a53a8_167.png)

Now if we'll use this binary search tree to store the integers search operation will be very similar let's say we want to search for number 12 What we'll do is we'll start at root and then we will compare the value to be searched to the integer to be searched with value of root if it's equal we are done with the search if it's lesser we know that we need to go to the left subree because in a binary search tree all the elements in left subree are lesser and all the elements in right subree are greaterter now we'll go and look at the left child of node with value 15 we know that number 12 that we are looking for can exist in this subree only and anything apart from this subree is discarded so we have reduced the search space to only these three nodes having value 108 and 12 now once again we will compare 12 with 10 we are not equal 12 is crter so we know that we。



![](img/bb7151e6bd3062ace2030a53bb8a53a8_169.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_170.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_171.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_172.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_173.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_174.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_175.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_176.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_177.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_178.png)

To go looking in right sub3 of this node with value 10 so now our search space is reduced to just one node。

 once again we will compare the value here at this node and we have a match。



![](img/bb7151e6bd3062ace2030a53bb8a53a8_180.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_181.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_182.png)

So searching an element in one research tree is basically this traversal in which at each step we will go either towards left or right and hence at each step we will discard one of the subtes if the tree is balanced we call a tree balanced if for all nodes the difference between the heights of left and right subtes is not greater than one so if the tree is balanced we will start with a search space of n node and when we will discard one of the subtrees we will discard n by two nodes so our search space will be reduced to n by2。



![](img/bb7151e6bd3062ace2030a53bb8a53a8_184.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_185.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_186.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_187.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_188.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_189.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_190.png)

And then in next step we will reduce the search space to n by 4。

 we will go on reducing like this till we find element or till our search space is reduced to only one node when we will be done。

So the search here is also a binary search and that's why the name binary search tree this tree that I'm showing here is balanced in fact this is a perfect binary tree but with same records we can have an unbalanced tree like this this tree has got the same integer values as we had in the previous structure and this is also a binary search tree but this is unbalanced this is as good as a linked list in this tree there is no right subree for any of the nodes search space will be reduced by only one at each step from n nodes in search space we will go to n minus1 nodes and then to n minus2 nodes all the way till one will be n steps。



![](img/bb7151e6bd3062ace2030a53bb8a53a8_192.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_193.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_194.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_195.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_196.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_197.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_198.png)

In binary search tree in average case， cost of search insertion or deltion is big O of log N and in worst case。

 this is the worst case arrangement that Im showing you running time will be big O of n。

 we always try to avoid the worst case by trying to keep the binary search tree balanced。



![](img/bb7151e6bd3062ace2030a53bb8a53a8_200.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_201.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_202.png)

With same records in the tree there can be multiple possible arrangements for these integers in this tree。

 another arrangement is this for all the nodes we have nothing to discard in left subtre in a search。

 This is another arrangement this is still balanced because for all the nodes the difference between the heights of left and right subrees is not greaterter than one。

 but this is the best arrangement when we have a perfect binary tree。



![](img/bb7151e6bd3062ace2030a53bb8a53a8_204.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_205.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_206.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_207.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_208.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_209.png)

At each step we will have exactly n by two nodes to discard okay now to insert some record in binary search tree we will first have to find the position at which we can insert and we can find the position in we go of log n time let's say we want to insert 19 in this tree What we will do is we will start at the root if the value to be inserted is lesser or equal if there is no child insert as left child or go left if the value is crter and there is no right child insert as right child or go right in this case 19 is crter so we will go right now we are at 20 19 is lesser and left subre is not empty we have a left child so we will go left now we are at 17 19 is greaterter than 17 so it should go in right of 17 there is no right child of 17 so we will create a node with value 19 and link it to this node with value 17 as right child because we are using point。



![](img/bb7151e6bd3062ace2030a53bb8a53a8_211.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_212.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_213.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_214.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_215.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_216.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_217.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_218.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_219.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_220.png)

Or references here just like linked list， no shifting is needed like an array。

 creating a link will take constant time， So overall insertion will also cost us like search。



![](img/bb7151e6bd3062ace2030a53bb8a53a8_222.png)

To delete also we will first have to search the node search once again will be big O of log n and deleting the node will only mean adjusting some links so removal also is going to be like search big O of log n in average case binary search tree gets unbalanced during insertion and deletion so often during insertion and deletion we restore the balancing there are ways to do it and we will talk about all of this in detail in later lessons in next lesson we will discuss implementation of binary search tree in detail this is it for this lesson thanks for watching。



![](img/bb7151e6bd3062ace2030a53bb8a53a8_224.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_225.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_226.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_227.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_228.png)

![](img/bb7151e6bd3062ace2030a53bb8a53a8_229.png)