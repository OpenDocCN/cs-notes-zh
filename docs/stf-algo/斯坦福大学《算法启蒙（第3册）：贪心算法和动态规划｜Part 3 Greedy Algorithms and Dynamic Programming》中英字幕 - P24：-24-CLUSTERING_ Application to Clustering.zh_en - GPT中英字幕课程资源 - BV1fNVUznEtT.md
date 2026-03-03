# 斯坦福大学《算法启蒙（第3册）：贪心算法和动态规划｜Part 3 Greedy Algorithms and Dynamic Programming》中英字幕 - P24：-24-CLUSTERING_ Application to Clustering.zh_en - GPT中英字幕课程资源 - BV1fNVUznEtT

So by now we've spent quite a bit of time talking about the minimum cost spanning tree problem。

 There's a number of motivations why we do that。 The first iss just a uniquely great problem for the study of greedy algorithms。

 You can propose a bunch of different greedy algorithms and quite unusually it' all of them seem to work。

 So you get correct greedy algorithms， but it's quite subtle what's driving their correctness。

 You also get a lot of practice arguing about graphs and arguing about exchange arguments and so on。

 The second reason it's been worthwhile spending time on these algorithms it's given us to more practice with data structures and how to use them to speed up algorithms。

 namely heaps to speed up Pris algorithm， the union find data structure to speed up Crusco's algorithm。

 The third reason that we're talking about them is they have applications in their own rights。

 That's the subject of this video in the next， and we're going to focus on applications to clustering problems。



![](img/c3ef7322def33864bfe80dac727397a9_1.png)

So let' me begin by just talking about the goal of clustering informally。

 and then I'll let you pin me down to a precise objective function on the next slide。



![](img/c3ef7322def33864bfe80dac727397a9_3.png)

So in a clustering problem， the input is endpoints that we think of as being embedded in space。

 and it's actually quite rare that in the underlying problem that we care about is it actually intrinsically geometric。

 is it actually intrinsically points in space， usually we're representing something we care about。

 maybe it's web pages， maybe it's images， maybe it's a database， as points in space。

And given a bunch of objects， we want to cluster them into， in some sense， coherent groups。

For those of you coming from a machine learning background。

 you'll often hear this problem referred to as unsupervised learning， meaning the data is unlabeled。

 we're looking for just patterns and data when the data is not annotated。

This obviously is a fairly wishy WasU description of a problem。

 so let's be a little bit more precise。We're going to assume that part of the input is what we're going to call a similarity measure。

 meaning for any two objects， we're going to have a function giving us a number indicating how similar or really rather how dissimilar they are to each other。

In keeping with the geometric metaphor， we're going to refer to this function as a distance function。



![](img/c3ef7322def33864bfe80dac727397a9_5.png)

One thing that's cool is we don't need to impose many assumptions on this distance function。

 the one thing we're going to assume is that it's symmetric。

 meaning the distance from P to Q is the same as the distance from Q to P。

So what are some examples Well， if you want to really go with a geometric metaphor。

 if you're representing these points as in a space RM for some dimension M。

 you can just use the Euclidean distance or if you prefer some other norm like say L1 or L infinity。

In many application domains， there are widely accepted similarity or distance measures。

 one example would be for sequences， as we discussed in an introductory lecture。

 the penalty of the best alignment between two genome fragments。

So now that we have this distance function， what would it mean to have coherent groups， well。

 things which have small distance from each other， which are similar。

 they should generally be in the same group and things that are very dissimilar that have large distance between them。

 you would expect to mostly be in different groups。So how can we evaluate how good a clustering is。

 how well it's doing with the job of putting nearby points together and dissimilar points in different groups。

 Well， to be honest， there's many ways of approaching formalizing that problem The approach we're going to take is an optimizationbased approach。

 we're going to posit an objective function on clusterings and then seek out the clustering that optimizes that objective function。

 I want to warn you that's not the only way to approach the problem。

 there are other interesting approaches but optimization is a natural one。 Furthermore。

 just like in our scheduling application， there's more than one objective function that people study and that is wellmot。

 So one very popular objective function would be say the K means objective。

 which I encourage you to look up and read more about for this lecture。

 I'm just going to adopt one specific objective function， it's natural enough。

 but it's by no means the only one or even the primary one。

 but it'll serve the purpose of studying a natural greedy algorithm related to minimum spanning tree algorithms。

 which is optimal in a precise sense。So let me develop the terminology needed to state the objective function and the optimization problem precisely。



![](img/c3ef7322def33864bfe80dac727397a9_7.png)

One issue that always comes up in clustering problems is how many clusters are you going to use。

 so to keep things simple in this video， we're going to assume that part of the input K indicates how many clusters you're supposed to use。

 so we're going to assume that you know ai how many clusters you want。

So in some application domains this is a totally reasonable assumption you might know。

 for example that you want exactly two clusters the K equals2 in some domains you may have good domain knowledge from past experience that you know how many clusters you expect to need that's fall fine and good Also you in practice if you don't really know what K is supposed to be you can go ahead and run the algorithm we're going to talk about for a bunch of different values of K and then use some metric or just eyeball it to figure out which is the best solution。

So the objective function we're going to look at is defined in terms of separated pairs of points。

 that is points that are assigned to distinct clusters。Now。

 you know if you have more than one cluster inevitably there's going to be some separated pairs of points。

 some points are going to be in one group， other points are going to be in a different group。

 so separated points are inevitable and the most alarming separated points are the ones that are the most similar。

 the ones that have the smallest distance。 If points are separated， we want them to be far apart。

 So we're particularly concerned with nearby points that are separated。

 so that's going to be our objective function value called the spacing of a clustering。

 It's the distance between the closest together pair of separated points。

Now what do we want from the spacing of a clustering。

 well we want all of the separated points to be as far apart as possible because we want the spacing to be big。

 the bigger， the better。So that naturally motivates the formal problem statement you're given as input。

 the distance measure， you're told the distance between each pair of points。

 you're also told the desired number of clusters amongst all ways of clustering the points into K clusters fine the clustering which makes the spacing as big as possible。

So let's develop a greedy algorithm that seeks to make the spacing as big as possible。

 and to facilitate the discussion I'll use an example point set with just six black points up here in the upper right part of this slide。

Now the good idea behind this greedy algorithm is to not worry about the constraints that at the end of the day we can only output k different clusters。

 we're actually going to be infeasible， we'll have too many clusters throughout the algorithm。

 only at the conclusion of the algorithm will we be down to K clusters which will be our final and feasible solution。

 so that frees us up to initialize the procedure where the degenerate solution where each point is in its own cluster。

So in our example point set we have these six pink isolated clusters in general you're going to have n clusters and we've got to get down to K Now let's remember what the spacing objective is in the spacing objective you go over all of the separated pairs of points So for this degenerated solution and it's all pairs of points and you look at the most alarming separated pair that is those that are the closest to each other so the spacing is the distance between the closest pair of separated points。

Now in a greedy algorithm， you want to increase your objective function as much as possible。

 but actually things are pretty cut and dried in this scenario。

 Suppose I give you a clustering and you want to make the spacing bigger。

The only way you can do that is by taking the currently closest pair of separated points and making them not separated anymore that is putting them in the same cluster。

 so it's in some sense obvious what you want to do to make the objective function go up at all。

 you' got to look at the pair of points that is defining the objective。

 the closest pair of separated points， and you have to fuse them。

 you have to fuse their cluster so that they're no longer separated。In this example。

 it looks to me like the closest pair of points， which of course are separated is this pair in the upper right。

 so if we want to make the spacing bigger， then we fuse them into a common cluster。

So we started with six clusters now we're down to five。

 so now we reevaluate the spacing again of this new clustering。

 we ask what is the closest pair of separated points so that would seem to me to be this pair in the bottom right。

And again， the only way we can increase the spacing by merging clusterings is to merge these two isolated clusters into one。

Now we do it again， we say which pair of points determines the current spacing。

 which the currently separated pair pointss that are nearest to each other。

 that to me would look like this pair that's on the rightmost part of the picture。

The only way to merge two clusters and make the spacing actually go up is to merge the clusters containing the pairs of points determining the current spacing so in this case。

 two different clusters with two points each would collapse into a single cluster with four points。

 Let's assume that we wanted three clusters clusters anyways。

 which is where we are so at this point the greedy algorithms going to halt。

So let me now spell out the pseudo code of the greedy algorithm more generally。

 but it's exactly what you'd expect given the discussion so far。Al right。

 so I'd like you to stare at this pseudocode for 10 seconds or however long you need and try to relate this to an algorithm that we've seen in the course。

 in particular an algorithm that we've seen quite recently。

 I hope it reminds you strongly of an algorithm we've already covered。Specifically。

 I hope you see a strong resemblance between this greedy algorithm and Crescle's algorithm for computing a minimum cost spanning tree。



![](img/c3ef7322def33864bfe80dac727397a9_9.png)

Indeed， we can think of this greedy clustering algorithm as being exactly the same as Crreescoll's minimum cost spanning tree algorithm。

 except aborted early， stopped when there's K components remaining that is before the final K minus1 edge editions。

So just to make sure the correspondence is clear， what is the graph， what are the edges。

 what are the edge costs， well the objects in the clustering problem that is the points those correspond to vertices in a graph。

The other part of the input of the clustering problem are distances which are given for every pair of points。

 so those play the role that edge costs were playing in the minimum span tree problem。

Since we have a distance or an edge cost for every single pair of points。

 we can think of the edge set in the clustering problem as being the complete graph because we have an edge cost or a distance for every single pair。

So this type of a glamorative clustering has a name。

 this idea of fusing components one at a time using MST like criterion。

 it's called single link clustering。So singleling clustering is a good idea。

 if you work at all with clustering problems or unsupervised learning problems。

 it definitely should be a tool in your toolbox， we're going to justify its existence in one particular way in the next video when we show that it does indeed maximize the spacing over all possible K clusterings。

But even if you don't care about the spacing objective function per se。

 you want to be familiar with single and clustering。 It has many other nice properties as well。

