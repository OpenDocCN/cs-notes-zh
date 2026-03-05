# 伊利诺伊大学【中英⚡计算机科学基础｜Accelerated Computer Science Fundamentals Specialization】 p17 P17 01_4-1-堆简介 -BV1KnLCzXEcQ_p17-

![](img/1f5f18c403024744fbcc50d8c3ad0afa_0.png)

![](img/1f5f18c403024744fbcc50d8c3ad0afa_1.png)

This week， we're going to talk about an entirely new algorithm that's going to combine some best properties of different algorithms。

The best way to introduce this algorithm is to just think about a whole bunch of data。

 a whole bunch of numbers that we might want to insert into our algorithm。 This magical algorithm。

 this magical data structure is going to accept numbers or any other type of data that's comparable。

😊，Let's look at an example。 So here we may have the number 3， the number negative 17， the number 42。

Hi， maybe E。Maybe the number negative 10， maybe even the number negative pi。 These are all numbers。

 We could think of any type of data as long as it's comparable。In this data structure。

 we don't want to maintain a total ordering。 We don't want a sorted piece of data because we know that sorted data takes a really long time to maintain。

😡，Instead， the only operation we want to care about in this。😡。

Is we want a data structure that can remove the minimum value and do so quite efficiently。

 So if I do a remove operation on this data structure right here， I can simply say。

 remove and it's going to remove negative 17。And then if I do remove again。

 it's going to remove negative 10， but I remove again， it's going to remove negative pi。

Notice that every single time to remove operations not having any parameters。

 it's simply going to take the minimum value found in the entire data structure and remove it and return it back to the user。

😡，We want to optimize for this to build ourselves something called a priority queue where every single value can have a priority。

 and we can remove based on the value that has the highest or lowest priority to understand exactly why we going to build this。

 We can look at some of the classic data structures we already talked about。 Here's four of them。

 We have right here an unsorted array and an unsorted list。

And we can see that these lists have great insertion times。But terrible remove men timess。

We have to sort to search through the entire element。

 the entire list to actually get at where elements the smallest element。 On the other hand。

 assorted array， an assorted list has the ability to insert into that list。

In a very slow manner to maintain that sort order。 But then we can always remove the front under element。

 the smallest element in O of one time。So unfortunately， both of these have an O of in operation。

 which in operation we'd love to avoid using。Instead。

 we're going to try and build a data structure that we can do both operations in lesson than oement time。

To that， we're going to think about using something like a tree。

A tree can be maintained just like our binary search tree that we've talked about earlier。

 in the sense that there's always a left child and always a right child。

Though the ordering of this tree is not going to be the strictness of a binary search tree。

 because remember in a binary search tree， we have a detailed explanation of exactly why what we need on each side。

 and we find that that structure is going to lead to some performanceance decreases that we're not going to find acceptable。

😡，Instead， we can go ahead and build out a new data structure by using the idea of a tree and stick in one property on it。

Specifically， we're going to call this new type of tree a heap。

And the heap's going to have a few properties。 The first property is a binary tree T is a minimum heap。

 If either the tree is empty， so either we have a tree that has no nodes or we have a tree that has both a right and a left child such that both the left and the right child nodes are larger than the root node。

So all we care about in a heap is everything underneath our current node。

 all of our descendants must be larger in our。😡，We don't care anything about our siblings or anything that happens in another part of the tree。

 The only property about the heap that matters is everything that's a descendant from a node has to be larger in a mini heap or a smaller in a max heap than the node itself。

So what that means is that if we look at this he right here that everything on the left hand side is greater than4。

 We don't care anything about the right hand side when we're just looking at the left hand side。

 Likewise， everything on the right hand side is going to be greater than four as well。

Not caring about anything on the left hand side。And this， of course， applies recursively。

 So everything on the left child of five is going to use greater than five。

 not caring about anything else in the tree itself。

 All we care is this local property that the parent is going to be smaller than all of its descendants。

 This property， we're going actually represent using a clever data structure。

Because we ideally love the performance of an unsorted array。

 Some of those0 of one great guarantees for lookup。😊，That we don't have necessarily on。

 that we absolutely don't have on a binary search tree。

So what we'll do is we'll always ensure a heap is a complete tree。😡，Remember。

 a complete tree is going to be a perfect tree with every node filled in up until the last level。

 And in that last level， we're going to have all of the nodes pushed to the left。

Notice this complete tree right here。 Once we have a complete tree。

We can go ahead and map that tree entirely to a data structure that we're very comfortable with。

When we have this tree in memory。Work are going to store it as an array。😡，So specifically。

 let's look at this mapping。😡，When we have this tree。

 we're actually going to represent this tree in memory as an array。So if we look at this example。

 we see that here four。Is going to be the root of the tree。

 And it's going to be the first element in the array。

5 and 6 will be the next two elements in the array。

Then the four children of those elements are going to be the next four elements。

 And notice from the color degradation， we have 5 and 6 are both greater than4。

All of these nodes are going to be larger than their parent nodes。

What I'm going to do is I'm going to actually not think like a computer scientist for a second。

 And I'm going to start indexing the structure from the value1。

 And just so I don't even confuse myself。 I'm going to go ahead and put a zeroth index into this。

 And I'll just mark with an x to node。 I'm not going to use it。 So here's index 0，1，2，3，4，5，6，7。

So given any random node。 So let's look at this node 9， it has an index of 5。

 If we know the nodes index， let's look at where its parent is。 The parent of the element 9。

Is going to be the value five。So the value 5 is here at index 2。 How do we get from 5 to 2， Well。

 that looks like integer division。 So 5 divided by 2 using integer division is 2。

Let's look at the other child， 15 is the other child， 15 is index 4，4 divided every2 is also two。

So inside of our array， we can always navigate to our parent， not by having a parent pointer。

 but we know our parent。Is equal to our index。Divided by2。Likewise。

 we can navigate to our children the exact same process by inverting this equation。

 We know our left child， given a parent。Is going to be equal to I times 2。So looking at the value 20。

 for example， we know that 20 doesn't have a left child because seven times two is gen and jump to 14。

Look in the value 6， above 20，6 is left child is 7， so 6，3 times 2 is6。

 so left child can be gotten by multiplying our current index by 2。

 our right child is going to be gotten by multiplying our current index by 2 and then adding one。



![](img/1f5f18c403024744fbcc50d8c3ad0afa_3.png)

So what we have here is the entire memory representation or he is going to it in be entirely an array。

😡，All we're going have in memory is array。 We're not gonna have the tree structure and memory at all。

 But when we're actually we're actually doing the analysis。

 we'll draw it as a tree because it's going be way easier to think about things in a tree。

 Notice that we have the exact same tree structure we've had before。

 This is just like the binary trees you've learned about earlier。

 But now we're gonna shrink this binary tree into an array。😡。

We're going to have special properties on this array so that we can always go to our parent and child quickly。

And we know that these operations all have simple mathematical formulas that allow us to compute them extremely quickly。

 because everything's a power of two， we'll see that computers actually do this even faster than we can imagine。

So this is a setup for heap In the next video， I'm going to talk about how we can actually insert data in the heap and maintain this heap as we're building our priority Q data structure。

 So I'll see then。

![](img/1f5f18c403024744fbcc50d8c3ad0afa_5.png)