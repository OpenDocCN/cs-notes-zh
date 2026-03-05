# 伊利诺伊大学【中英⚡计算机科学基础｜Accelerated Computer Science Fundamentals Specialization】 p30 P30 03_2-1-2-不相交集合的简单实现 -BV1KnLCzXEcQ_p30-

![](img/ce26fd8b29132ee37d833d2a69a7932b_0.png)

![](img/ce26fd8b29132ee37d833d2a69a7932b_1.png)

Let's think about how we might actually create an implementation。Of the disjoint sets algorithm。

In doing so， I'm going to create the most simple algorithm that I can think of。

 and we'll look at how well this performs and what kind of problems that we have in this implementation so we can go ahead and build a more complex implementation that solves the exact same problem。

 motivated by the example we see right now。So what I'm going to do is I'm going to store all of the elements inside of my set into an array。

😡，So let's look at an example here I have the element 01，4，2，7，3，5 and 6。

Luckily this is the numbers between 0 and 7 and these are nice indices into an array If we don't already have this nice index relationship。

 we can put a hash table in front of this。Using our hash algorithm that we learned about a few weeks ago。

To create an index that can be indexed in a your array。So given these elements。

 I can simply say at every single index into my array array。

 the value in the array is the set identity for that particular group。

 so zero is in the group that has a set identity0。The element1 is in the group that has a set identity0。

 the element2 is in the group that has set identity2。

 the element 3 is over here in the group that has a set identity of  three。

The element4 is in the group that has a set identity of zero。

The element5 is in the group that has a set identity of three。

Element6 also in the group with the set identity of three， and finally。

 element 7 is the element which is in the set with the identity of two。

So notice the value in every single array is the exact identity of our structure itself。

So that means to find the identity of a given element， so to find the identity of element 4。

Then we can simply look at index 4 in the array and find out what the set identity is for that。😡。

So looking at element four， we know that the set identity for find a four。Is going to be zero。

This is incredibly fast。 We're just looking up into an array。

 We know that the running time of this is O of one time。

 This is an incredible running time for being able to find an array。😊。

But let's think about what happens when we need to union two things together。

 S I want to union the element four and two together。

Union4 and2 means that the entirety of the left set and the middle set must be union to one same set What that means is two and7 needs their set identities updated。

To be zero。Unfortunately， in our current implementation。

 we have no way to know what elements are in the element2。😡。

Or what elements are in the set identity that has a set identity of two？😡。

So two and7 are both in the same set， but no data structure here allows us to look up what all elements have a set identity to instead the absolute only way to do this is to go through array and say。

 hey index0， are you part of set identity2？😡，Nope， okay， index 1 are you part of it， no， index 2。

 you're part of it， Yes， okay， awesome， then we need to update your identity to zero。

Index 3 are you part of it， Nope， index 4， are you part of it， No， index 5， no，6， no。

 only here when we get 7， we find another element that's in our set here we update that to be zero to update the correct set identity and doing that means to find every single element that's in the set that we're unioning together using a disjoint set we have a find that runs an O of one time。

 a really great running time for find。But the actual running time for union means we have to traverse the entire array。

 it's an Ol running time， which is absolutely terrible。😡。

So what we hope to do is we hope to actually build something that's going to be。Nearly as efficient。

 fine， nearly that constant time running time， but also ensure that we have an efficient running time in the actual union operation。

So what we'll be aiming to do in the next lecture is to use the base ideas here and actually build on it to create a more efficient algorithm to build a disjoint set。

😡，In a runtime， much， much smaller than O of N， so I'll see you there。



![](img/ce26fd8b29132ee37d833d2a69a7932b_3.png)