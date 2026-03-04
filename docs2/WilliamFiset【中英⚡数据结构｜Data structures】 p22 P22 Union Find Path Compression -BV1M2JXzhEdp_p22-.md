# WilliamFiset【中英⚡数据结构｜Data structures】 p22 P22 Union Find Path Compression -BV1M2JXzhEdp_p22-

Let's talk about path compression。Now， this operation is really what makes the Union find one of the most remarkable data structures。

 because it's how the union find gets to boast in its efficiency。 So let's dive right in。



![](img/2257e3c0601069df892e10f589d0e49f_1.png)

But before we get started， it's critical that you watch the last video so that you understand how the find and the union operation work。

Otherwise， you won't understand what's going on and what's up with path compression and how we're going to get that really nice。

 amortized constant time。

![](img/2257e3c0601069df892e10f589d0e49f_3.png)

Allright， suppose we have this hypothetical union find。

I say hypothetical because with path compression， I am almost certain it's impossible to achieve a data structure or a structure that looks like this。

Nonetheless， it's a good example。So now suppose we want to unify nodes E and L。Or just unify groups。

 orange and blue， but we have access to EL。 and that's what we're calling the unify operation on。

Well， we would have two pointers that start on E and L and what we would want to do is find the root node of E and find the root node of L and then get one of them to point to the other。

But with path compression， we do that， but we're also going to do something else。

 so let's start by finding the parent node of E， so E's parent is D then D' is is C。



![](img/2257e3c0601069df892e10f589d0e49f_5.png)