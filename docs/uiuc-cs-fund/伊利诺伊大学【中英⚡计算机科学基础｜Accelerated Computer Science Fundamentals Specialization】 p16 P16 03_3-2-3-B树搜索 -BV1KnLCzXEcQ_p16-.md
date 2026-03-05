# 伊利诺伊大学【中英⚡计算机科学基础｜Accelerated Computer Science Fundamentals Specialization】 p16 P16 03_3-2-3-B树搜索 -BV1KnLCzXEcQ_p16-

![](img/37632c065d09153833e2dbac8010f8e2_0.png)

![](img/37632c065d09153833e2dbac8010f8e2_1.png)

At this point， we have a deep understanding of exactly what it means to have a bee tree。

Now let's do a little bit of analysis on what's happening。

Here I have a simple Be tree that's of order 3。 And here we know that when we search for a node in this B tree。

 we're going to be comparing at each level one particular set of nodes。

 and we're going to need to do as many comparisons as is the height of this tree。

Given that many comparisons， we can look at the code to actually go about doing this and the analysis of how long it's going to take from a runtime perspective。

Let's look at some code。Here in this slide， I have some code that you have provided as part of the GitHub code for this course。

Here we can see that there's some interesting bits about this program。

 The first bit is we will function on whether or not this key exists in our B tree。

We've taken in a B tree node as well as a key， and this is a recursive definition。

The first thing you'll note is we're going to search through the actual node itself using a linear search to check the point where we have。

Keys equal to we find that we're past the key that has the value we're looking for。

 Once we know that we're past that key， we know exactly know what child to move into。

You'll see the next line move into that child。And unless we find an exact match。And then after that。

We ask if it's a leaf node if it's a leaf node， we didn't find it。

 otherwise we move into the next child by using this fetch child operation。

 The fetch child operation is going to go out to the internet or go out to cloud or go out to the disk or go out anywhere to find that next child。

 and that's going to be the really， really slow operation。

There's two interesting things about this code。 The first is up here at the top of this code。

 you'll notice that the search we're doing is actually a linear search。😡，Even though our data sorted。

 we could do a binary search here。 it would be totally fine to do that。

 but instead we're just doing a linear search because the time comparison it takes to run this O ofN algorithm here。

😡，Doesn't actually matter because the time it's going to take to actually do the work is going to be significantly greater when we need to fetch a note。

😡，Because the fetching of a node is such an important part of this algorithm。

 we want to actually understand how long does it take and how many fetches are going to be required。

The height of the B tree is going to determine the number of Cs that's needed in order to access all of our data。

 So we know that the number of seeks possible to access the data is going to be determined by the maximum height of the tree。

 We know the height of the structure decreases by a factor based on the order of the tree。

 So the height of our structure is always going to be log based M of n because that every single point we're decreasing by a factor of M So if this is log based 100。

 every time we're decreasing by a factor of 100。Therefore。

 we know the number of seeks that's required is going to log base M of N seeks。

And this number of Cs is going to be extremely low because many bee trees are going to run in order of 1000 or more。

 So if we consider a bee tree of order 101， we're going to see that that tree is going to take a number and break it up by however many commas are in that number。

 So if you have 3 trillion pieces of data， you've got five different commas in that number。

 which means you're only going to have to do five seeks to look through all 3 trillion pieces of data。

 This is absolutely amazing。 given how much data you can store and in the small amount of disks you need to do。

 in comparison， if you have that much data in an AVl tree， you'd have to do over 306s。😊。



![](img/37632c065d09153833e2dbac8010f8e2_3.png)

So a B tree is an optimized algorithm to optimize around the idea of doing as minimal disk seeks as possible when all of our data can't fit in main memory。

 It's a little bit of a hybrid between a classical tree and a pure disk algorithm。

 So we have the best of both worlds by combining two different algorithms we know。😡。

So we'll do a little bit more about B trees as we look at more algorithms that involve seeking on disks。

 but largely we want to make sure that you have an idea of exactly a one algorithm that works really well under conditions that we don't normally account for under big O notations。

Next time， we'll talk more about how to develop other algorithms that build upon two different ideas。

So， I'll see then。🎼，🎼。