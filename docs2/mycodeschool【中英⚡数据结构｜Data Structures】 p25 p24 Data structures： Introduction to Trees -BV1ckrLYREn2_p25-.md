# mycodeschool【中英⚡数据结构｜Data Structures】 p25 p24 Data structures： Introduction to Trees -BV1ckrLYREn2_p25-

Hello everyone in this lesson we'll introduce you to an interesting data structure that has got its application in a wide number of scenarios in computer science and this data structure is3 so far in this series we have talked about what we can call linear data structures or a linked list stack and queue all of these are linear data structures all of these are basically collections of different kinds in which data is arranged in a sequential manner in all these structures that Im showing here we have a logical start and a logical end and then an element in any of these collections can have a next element and a previous element so all in all we have linear or sequential arrangement。



![](img/35e661907458cf80b7e61d688134b8ff_1.png)

![](img/35e661907458cf80b7e61d688134b8ff_2.png)

![](img/35e661907458cf80b7e61d688134b8ff_3.png)

![](img/35e661907458cf80b7e61d688134b8ff_4.png)

![](img/35e661907458cf80b7e61d688134b8ff_5.png)

![](img/35e661907458cf80b7e61d688134b8ff_6.png)

![](img/35e661907458cf80b7e61d688134b8ff_7.png)

![](img/35e661907458cf80b7e61d688134b8ff_8.png)

![](img/35e661907458cf80b7e61d688134b8ff_9.png)

Now， as we understand， these data structures are ways to store and organize data in computers。



![](img/35e661907458cf80b7e61d688134b8ff_11.png)

For different kinds of data we use different kinds of data structure。

 our choice of data structure depends upon a number of factors。



![](img/35e661907458cf80b7e61d688134b8ff_13.png)

![](img/35e661907458cf80b7e61d688134b8ff_14.png)

First of all its about what needs to be stored a certain data structure can be best fit for a particular kind of data then we may care for the cost of operations quite often we want to minimize the cost of most frequently performed operations for example let's say we have a simple list and we are searching for an element in the list most of the time then we may want to store the list or collection as an array in sorted order so we can perform something like binary search really fast another factor can be memory consumption sometimes we may want to minimize the memory usage and finally we may also choose a data structure for ease of implementation although this may not be the best strategy。



![](img/35e661907458cf80b7e61d688134b8ff_16.png)

![](img/35e661907458cf80b7e61d688134b8ff_17.png)

![](img/35e661907458cf80b7e61d688134b8ff_18.png)

![](img/35e661907458cf80b7e61d688134b8ff_19.png)

![](img/35e661907458cf80b7e61d688134b8ff_20.png)

![](img/35e661907458cf80b7e61d688134b8ff_21.png)

![](img/35e661907458cf80b7e61d688134b8ff_22.png)

![](img/35e661907458cf80b7e61d688134b8ff_23.png)

![](img/35e661907458cf80b7e61d688134b8ff_24.png)

Threee is one data structure that's quite often used to represent hierarchical data for example let's say we want to show employees in an organization and their positions in organizational hierarchy then we can show it something like this let's say this is organizational hierarchy of some company in this company John is CEO and John has two direct reports Steve and Rama then Steve has three direct reports Steve is manager of Lee Bob and Ella。



![](img/35e661907458cf80b7e61d688134b8ff_26.png)

![](img/35e661907458cf80b7e61d688134b8ff_27.png)

![](img/35e661907458cf80b7e61d688134b8ff_28.png)

![](img/35e661907458cf80b7e61d688134b8ff_29.png)

![](img/35e661907458cf80b7e61d688134b8ff_30.png)

They may be having some designation。

![](img/35e661907458cf80b7e61d688134b8ff_32.png)

Rma also has two direct reports， then Bob has two direct reports and then Tom has one direct report this particular logical structure that I have drawn here is a tree well you have to at look at this structure upside down and then it will resemble a real tree the root here is at top and we are branching out in downward direction。



![](img/35e661907458cf80b7e61d688134b8ff_34.png)

![](img/35e661907458cf80b7e61d688134b8ff_35.png)

![](img/35e661907458cf80b7e61d688134b8ff_36.png)

Logical representation of tree data structure is always like this root at top and branching out in downward direction okay so tree is an efficient way of storing and organizing data that is naturally hierarchical。

 but this is not the only application of tree in computer science。



![](img/35e661907458cf80b7e61d688134b8ff_38.png)

![](img/35e661907458cf80b7e61d688134b8ff_39.png)

![](img/35e661907458cf80b7e61d688134b8ff_40.png)

![](img/35e661907458cf80b7e61d688134b8ff_41.png)

We will talk about other applications and some of the implementation details like how we can create such a logical structure in computers memory later first I want to define tree as a logical model。



![](img/35e661907458cf80b7e61d688134b8ff_43.png)

![](img/35e661907458cf80b7e61d688134b8ff_44.png)

![](img/35e661907458cf80b7e61d688134b8ff_45.png)

Te data structure can be defined as a collection of entities called nodes。



![](img/35e661907458cf80b7e61d688134b8ff_47.png)

Linked together to simulate a hierarchy tree is a nonlinear data structure。

 its a hierarchical structure， the topmost node in the tree is called root of the tree。

Each node will contain some data and this can be data of any type in the tree that I'm showing in right here data is name of employee and designation so we can have。



![](img/35e661907458cf80b7e61d688134b8ff_49.png)

![](img/35e661907458cf80b7e61d688134b8ff_50.png)

![](img/35e661907458cf80b7e61d688134b8ff_51.png)

An object with two string fields， one to store name and another to store designation。Okay。

 so each node will contain some data and may contain link or reference to some other nodes that can be called its children。



![](img/35e661907458cf80b7e61d688134b8ff_53.png)

![](img/35e661907458cf80b7e61d688134b8ff_54.png)

Now I'm introducing you to some vocabulary that we use for three data structure。

 What I'm going to do here is I'm going to number these nodes in the left trace so I can refer to these nodes using these numbers。



![](img/35e661907458cf80b7e61d688134b8ff_56.png)

![](img/35e661907458cf80b7e61d688134b8ff_57.png)

I'm numbering these nodes only for my convenience it's not to show any order。 Okay， coming back。

 as I had said， each node will have some data。 We can fill in some data in these circles。



![](img/35e661907458cf80b7e61d688134b8ff_59.png)

![](img/35e661907458cf80b7e61d688134b8ff_60.png)

![](img/35e661907458cf80b7e61d688134b8ff_61.png)

It can be data of any type， it can be an integer or a character or a string。

 or we can simply assume that there is some data filled inside these nodes and we are not showing it。



![](img/35e661907458cf80b7e61d688134b8ff_63.png)

![](img/35e661907458cf80b7e61d688134b8ff_64.png)

Okay， as we were discussing， a node may have link or reference to some other nodes that will be called its children。



![](img/35e661907458cf80b7e61d688134b8ff_66.png)

Each arrow in this structure here is a link okay now as you can see the root node which is numbered 1 by me and once again this number is not indicative of any order I could have called the root node node number 10 also so root node has linked to these two nodes number 2 and 3 so2 and  three will be called children of one。



![](img/35e661907458cf80b7e61d688134b8ff_68.png)

![](img/35e661907458cf80b7e61d688134b8ff_69.png)

![](img/35e661907458cf80b7e61d688134b8ff_70.png)

And node1 will be called parent of nodes 2 and 3。

![](img/35e661907458cf80b7e61d688134b8ff_72.png)

I'll write down all these terms that I am talking about， we mentioned root， children and parent。

In the3 a parent one is parent of2 and3，2 is child of one， and now four， five and6 are children of2。

 so node 2 is child of node1， but parent of node 4，5 and 6。



![](img/35e661907458cf80b7e61d688134b8ff_74.png)

![](img/35e661907458cf80b7e61d688134b8ff_75.png)

Children of same parent are called sibling。

![](img/35e661907458cf80b7e61d688134b8ff_77.png)

I'm showing siblings in same color here。

![](img/35e661907458cf80b7e61d688134b8ff_79.png)

Two and three are siblings， then four， five and six are sibling， then seven， eight are sibling。

 and finally nine and 10 are sibling。

![](img/35e661907458cf80b7e61d688134b8ff_81.png)

I hope you are clear with these terms now that utmost node in the tree is called root root would be the only node without a parent and then if a node has a direct link to some other node。

 then we have a parent child relationship between the nodes。



![](img/35e661907458cf80b7e61d688134b8ff_83.png)

![](img/35e661907458cf80b7e61d688134b8ff_84.png)

![](img/35e661907458cf80b7e61d688134b8ff_85.png)

Any node in the tree that does not have a child is called leaf node。



![](img/35e661907458cf80b7e61d688134b8ff_87.png)

All these nodes。Marked in black here。

![](img/35e661907458cf80b7e61d688134b8ff_89.png)

A leaves。So leaf is one more term。

![](img/35e661907458cf80b7e61d688134b8ff_91.png)

All other node with at least one child can be called internal notess。



![](img/35e661907458cf80b7e61d688134b8ff_93.png)

And we can have some more relationships like parent of parent can be called grained parent。

 so one is grandparent of four and 4 is grandchild of one in general if we can go from node A to B walking through the links。



![](img/35e661907458cf80b7e61d688134b8ff_95.png)

![](img/35e661907458cf80b7e61d688134b8ff_96.png)

![](img/35e661907458cf80b7e61d688134b8ff_97.png)

And remember， these links are not bidirectional。

![](img/35e661907458cf80b7e61d688134b8ff_99.png)

We have a link from one to2 so we can go from one to2， but we cannot go from2 to1。



![](img/35e661907458cf80b7e61d688134b8ff_101.png)

When we are walking the tree， we can walk in only one direction okay so if we can go from node A to node B。

 then a can be called ancestor of B and B can be called descendant of a。



![](img/35e661907458cf80b7e61d688134b8ff_103.png)

![](img/35e661907458cf80b7e61d688134b8ff_104.png)

![](img/35e661907458cf80b7e61d688134b8ff_105.png)

Let's pick up this node number 10，1， 2 and 5 are all ancestors of 10。

 and 10 is a descendant of all of these nodes。

![](img/35e661907458cf80b7e61d688134b8ff_107.png)

![](img/35e661907458cf80b7e61d688134b8ff_108.png)

We can walk from any of these nodes to 10 okay， let me now ask you some questions to make sure you understand things what are the common ancestors of4 and9？



![](img/35e661907458cf80b7e61d688134b8ff_110.png)

![](img/35e661907458cf80b7e61d688134b8ff_111.png)

Ancestors of four are one and2 and ancestors of nine are one， two， and five。

 so common ancestors will be one and2。

![](img/35e661907458cf80b7e61d688134b8ff_113.png)

Okay， next question， are six and seven siblings？Sibling must have same parent。

 six and seven do not have same parent， they have same grandparent。



![](img/35e661907458cf80b7e61d688134b8ff_115.png)

One is grand parent of both node not having same parent but having same grand parent can be called cousins。

 so six and7 are cousins and these relationships are really interesting we can also say that node number 3 is uncle of node number 6 because。



![](img/35e661907458cf80b7e61d688134b8ff_117.png)

![](img/35e661907458cf80b7e61d688134b8ff_118.png)

Because it's sibling of two， which is father of six。



![](img/35e661907458cf80b7e61d688134b8ff_120.png)

Or I should say parent of6。

![](img/35e661907458cf80b7e61d688134b8ff_122.png)

So we have quite symptoms in vocabulary of three。

![](img/35e661907458cf80b7e61d688134b8ff_124.png)

Okay， now I'll talk about some properties of three。Three can be called a recursive data structure。

We can define tree recursively as a structure that consists of a distinguished node called root。😊。



![](img/35e661907458cf80b7e61d688134b8ff_126.png)

![](img/35e661907458cf80b7e61d688134b8ff_127.png)

And some subtes and the arrangement is such that root of the tree contains link to roots of all the subtes。

T1， T2 and T3 in this figure are subtes。In the tree that I have drawn in left here we have two subtrees for root node。

 I am showing the root node in red， the left subre in brown and the right subre in yellow。

 we can further split the left subre and look at it like node number two is root of this subre。



![](img/35e661907458cf80b7e61d688134b8ff_129.png)

![](img/35e661907458cf80b7e61d688134b8ff_130.png)

![](img/35e661907458cf80b7e61d688134b8ff_131.png)

![](img/35e661907458cf80b7e61d688134b8ff_132.png)

And this particular tree with node number two as root has three subt。

 Im showing the three subtes in three different colors。

 recursion basically is reducing something in a self similar manner。

 This recursive property of tree will be used everywhere in all implementation and users of tree。



![](img/35e661907458cf80b7e61d688134b8ff_134.png)

![](img/35e661907458cf80b7e61d688134b8ff_135.png)

![](img/35e661907458cf80b7e61d688134b8ff_136.png)

The next property that I want to talk about is in a tree with n nodes there will be exactly n minus1 links or edges each arrow in this figure can be called a link or an edge all nodes except the root node will have exactly one incoming edge if you can see I'll pick this node number two there is only one incoming link this is incoming link。



![](img/35e661907458cf80b7e61d688134b8ff_138.png)

![](img/35e661907458cf80b7e61d688134b8ff_139.png)

![](img/35e661907458cf80b7e61d688134b8ff_140.png)

![](img/35e661907458cf80b7e61d688134b8ff_141.png)

![](img/35e661907458cf80b7e61d688134b8ff_142.png)

And these three are outgoing links。There will be one link for each parent child relationship so in a valid tree if there are n nodes there will be exactly n minus1 edges。

 one incoming edge for each node except the root。

![](img/35e661907458cf80b7e61d688134b8ff_144.png)

![](img/35e661907458cf80b7e61d688134b8ff_145.png)

Okay now I want to talk about these two properties called depth and height。

 depth of some node x in a tree can be defined as length of the path from root to node x。

 each edge in the path will contribute one unit to the length。

 so we can also say a number of edges in part from root to x。



![](img/35e661907458cf80b7e61d688134b8ff_147.png)

![](img/35e661907458cf80b7e61d688134b8ff_148.png)

![](img/35e661907458cf80b7e61d688134b8ff_149.png)

![](img/35e661907458cf80b7e61d688134b8ff_150.png)

The depth of root node will be0。

![](img/35e661907458cf80b7e61d688134b8ff_152.png)

Let's pick some other node。For this node numbered 5， we have two edges in the path from root。



![](img/35e661907458cf80b7e61d688134b8ff_154.png)

So the depth of this node is 2。In this tree here， depth of nodes 2 and 3 is1， depth of nodes 456。

7 and 8 is 2， and the depth of nodes 19 and 11 is3。



![](img/35e661907458cf80b7e61d688134b8ff_156.png)

![](img/35e661907458cf80b7e61d688134b8ff_157.png)

Okay now height of a node entry can be defined as number of edges in longest path from that node to a leaf node。

 so height of some node x will be equal to number of edges in longest path from x to a leaf in this figure for node 3。



![](img/35e661907458cf80b7e61d688134b8ff_159.png)

![](img/35e661907458cf80b7e61d688134b8ff_160.png)

![](img/35e661907458cf80b7e61d688134b8ff_161.png)

The longest path from this node to any leaf is 2， so height of node 3 is 2 node 8 is also a leaf node。



![](img/35e661907458cf80b7e61d688134b8ff_163.png)

![](img/35e661907458cf80b7e61d688134b8ff_164.png)

I'll mark all the leaf nodes here， a leaf node is a node with zero child。



![](img/35e661907458cf80b7e61d688134b8ff_166.png)

The longest path from node 3 to any of the leaf nodes is 2。

 so the height of node 3 is 2 height of leaf nodes。



![](img/35e661907458cf80b7e61d688134b8ff_168.png)

Will be0。

![](img/35e661907458cf80b7e61d688134b8ff_170.png)

So， what will be the height of root node in the tree。

 we can reach all the leaves from root node number of edges in longest path is 3。

 so height of the root node here is 3。

![](img/35e661907458cf80b7e61d688134b8ff_172.png)

![](img/35e661907458cf80b7e61d688134b8ff_173.png)

We also define height of a tree， height of tree is defined as height of root node。

 height of this tree that I'm showing here is3 height and depth are different properties and height and depth of a node may or may not be same。

 we often confuse between the two。

![](img/35e661907458cf80b7e61d688134b8ff_175.png)

![](img/35e661907458cf80b7e61d688134b8ff_176.png)

![](img/35e661907458cf80b7e61d688134b8ff_177.png)

Based on properties， trees are classified into various categories。

 there are different kinds of trees that are used in different scenarios。

 simplest and most common kind of tree is a tree with this property that any node can have at most two children。



![](img/35e661907458cf80b7e61d688134b8ff_179.png)

![](img/35e661907458cf80b7e61d688134b8ff_180.png)

![](img/35e661907458cf80b7e61d688134b8ff_181.png)

In this figure node2 has three children， I'm getting rid of some node， and now this is a binary tree。



![](img/35e661907458cf80b7e61d688134b8ff_183.png)

Bineary trees is most famous and throughout this series we will mostly be talking about binary trees the most common way of implementing tree is dynamically created nodes linked using pointers or references just the way we do for linked list。



![](img/35e661907458cf80b7e61d688134b8ff_185.png)

![](img/35e661907458cf80b7e61d688134b8ff_186.png)

We can look at the tree like this。😊，In the structure that I have drawn in right here。



![](img/35e661907458cf80b7e61d688134b8ff_188.png)

Notode has three fields one of the fields is to store data， let's say middle cell is to store data。

 the left cell is to store the address of the left child。



![](img/35e661907458cf80b7e61d688134b8ff_190.png)

And the right cell is to store address dress off right childil。

 because this is a binary tree we cannot have more than two children。



![](img/35e661907458cf80b7e61d688134b8ff_192.png)

![](img/35e661907458cf80b7e61d688134b8ff_193.png)

We can call one of the children left child and another right child。



![](img/35e661907458cf80b7e61d688134b8ff_195.png)

Programmatically in C or C++ we can define node as a structure like this we have three fields here。

 one to store data let's say data type is integer I have filled in some data in these nodes so in each node we have three fields we have an integer variable to store the data and then we have two pointers to node one to store the address of the left child that will be the root of the left subree and another to store the address of the right child we have kept only two pointers because because we can have at most two children in binary tree this particular definition of node can be used only for a binary tree for genetic trees that can have any number of children we use some other structure and I'll talk about it in later lessons in fact we will discuss implementation in detail in later lessons this is just to give you a brief idea of how things will be like in implementation。



![](img/35e661907458cf80b7e61d688134b8ff_197.png)

![](img/35e661907458cf80b7e61d688134b8ff_198.png)

![](img/35e661907458cf80b7e61d688134b8ff_199.png)

![](img/35e661907458cf80b7e61d688134b8ff_200.png)

![](img/35e661907458cf80b7e61d688134b8ff_201.png)

![](img/35e661907458cf80b7e61d688134b8ff_202.png)

![](img/35e661907458cf80b7e61d688134b8ff_203.png)

![](img/35e661907458cf80b7e61d688134b8ff_204.png)

![](img/35e661907458cf80b7e61d688134b8ff_205.png)

![](img/35e661907458cf80b7e61d688134b8ff_206.png)

Okay so this is cool， we understand what a tree data structure is。

 but in the beginning we had said that storing naturally hierarchical data is not the only application of tree。

 so let's quickly have a look at some of the applications of tree in computer science。



![](img/35e661907458cf80b7e61d688134b8ff_208.png)

![](img/35e661907458cf80b7e61d688134b8ff_209.png)

![](img/35e661907458cf80b7e61d688134b8ff_210.png)

First application of course is storing naturally hierarchical data， for example。

 the file system on your disk drive， the file and folder hierarchy is naturally hierarchical data。

 it is stored in the form of3。

![](img/35e661907458cf80b7e61d688134b8ff_212.png)

![](img/35e661907458cf80b7e61d688134b8ff_213.png)

![](img/35e661907458cf80b7e61d688134b8ff_214.png)

Next application is organizing data， organizing collections for quick search， insertion and deletion。

 for example， binary search tree that we'll be discussing a lot in next couple of lessons can give us order of log in time for searching an element in it。



![](img/35e661907458cf80b7e61d688134b8ff_216.png)

![](img/35e661907458cf80b7e61d688134b8ff_217.png)

![](img/35e661907458cf80b7e61d688134b8ff_218.png)

![](img/35e661907458cf80b7e61d688134b8ff_219.png)

A special kind of tree called Tri is used to store dictionary。

 it's really fast and efficient and is used for dynamic spell checking。



![](img/35e661907458cf80b7e61d688134b8ff_221.png)

![](img/35e661907458cf80b7e61d688134b8ff_222.png)

Three data structure is also used in network routing algorithms， and this list goes on。



![](img/35e661907458cf80b7e61d688134b8ff_224.png)

We'll talk about different kinds of trees and their applications in later lessons。

 I'll stop here now this is good for an introduction。



![](img/35e661907458cf80b7e61d688134b8ff_226.png)

![](img/35e661907458cf80b7e61d688134b8ff_227.png)

In next couple of lessons we'll talk about binary search tree and its implementation。

 this is it for this lesson， thanks for watching。

![](img/35e661907458cf80b7e61d688134b8ff_229.png)