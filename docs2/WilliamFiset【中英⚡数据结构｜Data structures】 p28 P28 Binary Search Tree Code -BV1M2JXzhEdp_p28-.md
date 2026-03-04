# WilliamFiset【中英⚡数据结构｜Data structures】 p28 P28 Binary Search Tree Code -BV1M2JXzhEdp_p28-

Okay， finally time to look at some source code for a binary search tree。

 So the source code that I'm about to show you can be found at the following link。

 The link should also be in the description at the bottom of this video。

 Please like the repository so that other people can also find it more easily。 And now let's dive in。



![](img/f9fd627387fa47f51d0a72a1d67b11ba_1.png)

![](img/f9fd627387fa47f51d0a72a1d67b11ba_2.png)

Alright， here we are inside the source code for the binary search tree。

 This source code is written in Java。

![](img/f9fd627387fa47f51d0a72a1d67b11ba_4.png)

Okay， so first thing you will notice is I have a class representing a binary search tree and。



![](img/f9fd627387fa47f51d0a72a1d67b11ba_6.png)

It takes as a type。Anything that is comparable。

![](img/f9fd627387fa47f51d0a72a1d67b11ba_8.png)

We need things that are comparable， so we know how to insert them accordingly within the binary search tree。



![](img/f9fd627387fa47f51d0a72a1d67b11ba_10.png)

So to start us off， I have a few instance variables。



![](img/f9fd627387fa47f51d0a72a1d67b11ba_12.png)

Actually， only two， in fact， one to keep track of the number of nodes in the binary search tree and another one。

 which is the root of this binary search tree because this binary search tree is a rooted tree。



![](img/f9fd627387fa47f51d0a72a1d67b11ba_14.png)

![](img/f9fd627387fa47f51d0a72a1d67b11ba_15.png)

Next， I have a private note class。

![](img/f9fd627387fa47f51d0a72a1d67b11ba_17.png)

Which contains。

![](img/f9fd627387fa47f51d0a72a1d67b11ba_19.png)

A left node and a right node， as well as some data of type T。 and that type T comes from here。

 So it's some comparable type T。

![](img/f9fd627387fa47f51d0a72a1d67b11ba_21.png)

![](img/f9fd627387fa47f51d0a72a1d67b11ba_22.png)