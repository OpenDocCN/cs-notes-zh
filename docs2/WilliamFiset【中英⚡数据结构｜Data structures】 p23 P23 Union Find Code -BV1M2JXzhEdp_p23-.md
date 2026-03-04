# WilliamFiset【中英⚡数据结构｜Data structures】 p23 P23 Union Find Code -BV1M2JXzhEdp_p23-

Let's have a look at some of the union find source code。



![](img/aff2462e4e608aa0bd390f533cf3e2ed_1.png)

So。Here's a link to the source code。 You can find it on my Github repository at Github。

 co/willmphysa/da structures。 I also have a bunch of other data structures from past videos and before we dive into the code。

 make sure you watch the other videos pertaining to the Union find。

 as I will be making some references to them。

![](img/aff2462e4e608aa0bd390f533cf3e2ed_3.png)

Okay， let's dig in。Here we are inside the code， and。



![](img/aff2462e4e608aa0bd390f533cf3e2ed_5.png)

I have a class called Union Find and so have few instance variables， so let's go over them。



![](img/aff2462e4e608aa0bd390f533cf3e2ed_7.png)

![](img/aff2462e4e608aa0bd390f533cf3e2ed_8.png)

The first size is just how many elements we have in our union find。



![](img/aff2462e4e608aa0bd390f533cf3e2ed_10.png)

Then I have these two arrays， one called ID， and one called size。



![](img/aff2462e4e608aa0bd390f533cf3e2ed_12.png)

So the interest， well， the more interesting one is ID and ID D at I is that array I talked about。

 which at index I points to the parent node of I。And if I D at I is equal to I。

 then we know that I is a root node。So we're essentially keeping track of all these like tree like structures right inside in the array。

 which is practical。And also， because we create a bijection between our elements and some numbers。

 this is how we're able to access them through this idea array。



![](img/aff2462e4e608aa0bd390f533cf3e2ed_14.png)

And just for convenience， I track the number of components that sometimes。



![](img/aff2462e4e608aa0bd390f533cf3e2ed_16.png)