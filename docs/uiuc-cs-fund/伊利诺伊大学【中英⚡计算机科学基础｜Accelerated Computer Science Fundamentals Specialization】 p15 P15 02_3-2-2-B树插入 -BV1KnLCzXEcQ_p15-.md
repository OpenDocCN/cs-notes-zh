# 伊利诺伊大学【中英⚡计算机科学基础｜Accelerated Computer Science Fundamentals Specialization】 p15 P15 02_3-2-2-B树插入 -BV1KnLCzXEcQ_p15-

。

![](img/d54b6c38f85151075042497d341d73df_1.png)

![](img/d54b6c38f85151075042497d341d73df_2.png)

A Bree of order M is a data structure that we introduced earlier that's going to optimize an algorithm for having a minimum number of disk seeks or network seeks to get at our data。

A B tree of order M is specifically a tree that contains nodes of order M。

Each node can contain no more than M -1 keys。There can be a pointer on the left and right of each key of the node。

 potentially resulting in M children， because there are M total pointers coming off of that node。

And we talk about the data structure as being a B tree of order M。Inside of a B tree。

 we're gonna to start with just having a single node that has a number of keys inside of it。

 Let's imagine we have a B tree of order 5。Having a B tree of order 5 means that we're going to go ahead and insert elements into this tree。

 So for example， the element 14， 1942， 47 and 81。Inserting 14， we simply can put 14 into this key。

 19 can go in here。We'll stick 47 and next， and then 81。Given a B tree of order 5。

 we know that when we reach this point， we can't stick any more data in our root key node。 Instead。

 we need to go ahead and when we insert this value。

 create a new node that's going to contain this value。 Let's see how this works。 Looking at node 42。

 We need to stick 42 right here in the middle。But we can't do that because that's going to exceed the capacity of this node。

Instead， how we do an insertion in B tree is we need to throw up the value 42。

 to ensure that we have a new node。 Think about entering 42 here。 We can then take the middle value。

 make 42 a new node。 Everything to the left of 42， which is 14 and 19 can go on the left node。

 Everything to the right。 The numbers 47 and 81 can go on the right hand side。

 Now we have a B tree that contains five values。 There are two keys in the left child node。

2 keys in the right child node， and the root node contains one key with the value 42。

The recursive idea of B trees also holds。 Let's look at this B tree right here。

 That's a B tree of order 3。 Here， every single node is full， and we have multiple layers。

Suppose now we want to insert the number 30。 inserting 30。

 We can go ahead and do a find in our B tree。 What this means is we're going to go ahead and say 30 is between 23 and 42。

 So we're going to advance this middle node。And now， between 25 and 31。

 we'd place 30 to make this a node with three keys。But since the node has too many keys。

 we need to go ahead and throw up the middle value。

 Here we see the middle value 30 is going to be brought up to the parent node。

 The parent node is now going to have the values 23。

30 and 42 with pointers that point down to negative 3，8 is the left node here。

 just 25 is to the left of 30 to the right of 30 is 31。

 then 42 has the same right child of 43 and 55。Since this root node is now full。

 we need to again throw up the middle value。Here， we can do this by bringing 30 to the top。

 The left of 30 is 23。 The right of 30 is 42。 And you can see the keys otherwise stay the same。

23 still has connected， and 42 still has two children connected to it。 Here。

 we've seen the recursive nature of going down a bee tree to find the insertion point of a value And then only if the node is full。

 splitting that node in half and throwing up the middle value to the parent node till we find a node that hasn't been filled to capacity。

 So we have this understanding of exactly how this algorithm works。

And now we can look at properties inside of the Bea tree itself。

Looking at the properties of the B tree itself。 we can determine four things that are going to be true。

 The first thing is that we know that every B tree is going to have keys that are ordered within a given node。

 remember that the keys being ordered， means that they are in sorted order。

 which is a different meaning of the word when we say a B tree is of order M。

 In addition to having ordered keys。 Every node has no more than m minus one keys。

 but we're going to look at internal nodes as well。 So every node internal to a tree。

 which means that every node that is not a leaf node， is going to have two properties。

 That is that there is going to be one more child in key for every single internal node。

 The idea being here that you have pointers on the left side and the right side of our array and pointers between every single element。

 So we have one more pointer than the number of keys in the node。

 That means it contains one to M minus one piece of data Since our array has a data on both the left and the right side。

 So one piece of data is going to have two children， a left child in a right。

M one piece of data going to have M children。 We know that the root nodes are always going to have somewhere between2 to M children。

 And finally， every non root node is going to be bound by having somewhere between the ceiling of the order M divided by 2。

 So somewhere between ceiling of M over 2。And M children。

So every node inside of our B tree is going to be at least half full。

This makes sense because we're only splitting nodes as soon as they become full。

 So the result of a split node is going to be two nodes that are exactly half full。

 So we know the bounds in these nodes are always going to be M over 2 and M。

 The last thing to mention are all the leaves in a B tree are always going to be on the same level。

 The way we construct this tree means that we're never going to have leaves that are on different levels。

 So B tree is always going to have the same height， no matter which path you take down the Be tree。

Here's an example bee tree。 we can talk about different factors of this tree。 Here。

 I haven't labeled exactly what the order of this bee tree is。 Instead。

 we want to do some analysis to figure out what the order of this tree is。Looking at this tree。

 we can see that there are some interior nodes that have just two keys and therefore three children。

We can see that there is a leaf node that has four keys。Because this leaf node has four keys。

 we know that the order of the Be tree must be at least5， Given that we have three children here。

 we know M must be at least three。 And since we know the internal nodes is between M over 2 and M children。

 we know that M over 2 is at most 3。 So M is at most 6 We know the order has to be bound somewhere between 3 and 6。

Given these two criteria， the order must be greater than an equal to 5 from our first criteria and from our second criteria。

 that the order must be between 3 and 6。 So the only condition that satisfies both these criteria is that the order of this B tree must be either 5 or 6。

Given that these are the two possibilities。And given the fact that bee trees is generally are splitting node。

 So it's nice to have odd values， this bee tree was created as an order 5 B tree。

 And you should be able to look at any bee tree and reason something like this。😊。



![](img/d54b6c38f85151075042497d341d73df_4.png)

So what we've seen is we've seen a broad instruction of how to find a node in a be tree。

 as well as how to insert that node to create a larger and larger bee tree。

 You saw the recursive nature of this， where we find a spot to insert。

 And then once we found the insertion point of the be tree。

 we're going to recursively run this algorithm so that we keep throwing nodes up higher and higher in the tree。

😊，Next， we'll dive into some analysis of the B tree。

 as well as some properties of exactly how much you need to search to find any given node。

 I'll see then。🎼。

![](img/d54b6c38f85151075042497d341d73df_6.png)