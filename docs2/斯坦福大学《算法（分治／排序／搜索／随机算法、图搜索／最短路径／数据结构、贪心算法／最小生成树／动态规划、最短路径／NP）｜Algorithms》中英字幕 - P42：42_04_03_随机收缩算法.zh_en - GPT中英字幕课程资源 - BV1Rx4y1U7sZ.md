# 斯坦福大学《算法（分治／排序／搜索／随机算法、图搜索／最短路径／数据结构、贪心算法／最小生成树／动态规划、最短路径／NP）｜Algorithms》中英字幕 - P42：42_04_03_随机收缩算法.zh_en - GPT中英字幕课程资源 - BV1Rx4y1U7sZ

So now I get to tell you about the very cool randomized contraction algorithm for computing the minimum cut of a graph let's just recall what the minimum cut problem is given as input and undirected graph and parallel edges are allowed and in fact they will arise naturally throughout the course of the algorithm that is for given pair of vertices we allow multiple edges to have that pair as endpoints Now I do sort of assume you've watched the other video on how graphs are actually represented although that's not going to play a major role in the description of this particular algorithm and again the goal is to compute the cut so a cut is a partition of the graph vertices into two groups A and B the number of edges crossing the cut is simply those that have one endpoint on each side and amongst all of the exponentially possible cuts。

 we want to identify one that has the fewest number of crossing edges or a min cut。



![](img/f183f01336855d22e8538dd56d80c603_1.png)

So here's the random contraction algorithm， so this algorithm was devised by David Carter back when he was an early PhD student here at Stanford and this was in the early 90s。

 so like I said， quote unquote only about 20 years ago。

And the basic idea is to use random sampling now we've known forever ever since Quicksort that random sampling could be a good idea in certain contexts in particular when doing story and searching。

 and one of the things that was such a breakthrough about Cargo's contraction algorithm is it showed that random sampling could be extremely effective for fundamental graph problems。

So here's how it works。 We're just going to have one main loop。

Each iteration of this while loop is going to decrease the number of vertices in the graph by one。

 and we're going to terminate when we get down to just two vertices remaining Now。

 in a given iteration， here's the random sampling amongst all of the edges that remain in the graph to this point。

 we're going to choose one of those edges uniformly at random， each edge is equally likely。

Once you've chosen an edge， that's when we do the contraction。

 so we take the two endpoints of the edge， call them the vertex U and the vertex V and we fuse them into a single vertex that represents both of them。

This may become more clear when I go through a couple examples on the next couple of slides。

This merging may creates parallel edges， even if you didn't have them before。

 that's okay we're going to leave the parallel edges and it may create a self loop edge where now both of the endpoints is the same and self loops are stupid。

 so we're just going to delete them as they arise。Each iteration decreases the number of vertices that remain。

 we start with n vertices， we end up with two， so after n minus two iterations。

 that's when we stop and at that point we return the cuts represented by those two final vertices。



![](img/f183f01336855d22e8538dd56d80c603_3.png)

You might well be wondering what I mean by the cut represented by the final two vertices。

 but I think that will become clear in the examples which I'll proceed to now。

So suppose the input graph is the following four node five edge graph。

There's a square plus one diagonal。So how would the contraction algorithm work on this graph well of course it's a randomized algorithm so it could work in different ways and so we're going to look at two different trajectories in the first iteration each of these five edges is equally likely just chosen for contraction with 20% probability for concreteness。

 let's say that the algorithm happens to choose this edge to contract。To fuse the two endpoints。

After the fusion， these two vertices on the left have become one。

Whereas the two vertices on the right are still hanging around like they always were。

So the edge between the two original vertices is unchanged。

The contracted edge between the two ver disease on the left has gotten sucked up。 so that's gone。

 And so what remains are these two edges here。The edge on top， and the diagonal。

And those are now parallel edges。Between the fuse node and the upper right node。

 And then I also shouldn't forget the bottom edge。Which is。

Edge from the lower right node to the super node。So that's what we mean by taking a pair of vertices and contracting them。

 the edge that was previously connected to them vanishes。

 and then all the other edges just get pulled into the fusion。

So that's the first iteration of Cargo's algorithm or one possible execution。

 so now we proceed to the second iteration of the contraction algorithm and the same thing happens all over again。

 we pick an edge uniformly at random Now there's only four edges that remain。

 each of which is equally likely to be chosen so a 25% probability for concreteness let's say that in the second iteration we wind up choosing one of the two parallel edges。

 say this one here。So what happens Well now， instead of three vertices， we go down to two。

 we have the original bottom right vertex that hasn't participated in any contractions at all。

 So that's as it was。 And then we have the second vertex which actually represents diffusion of all of the other three vertices。

 So two of them were fused。 the leftmost vertices refuseded in iteration one and now the upper right vertex got fused in with them to create the super node representing three original vertices。

 So what happens to the four edges。 Well the contracted one disappears that just gets sucked into the super node and we never see it again。

 and then the other three go in where go where they're supposed to go。

 So there's the edge that used to be the rightmost edge that has no hash mark。

 there's the edge with two hash marks that goes between the same two nodes that it did before。

 just the super node is now and even bigger node representing three nodes。

 and then the edge which was parallel to the one that we contracted。

 The other one with a hash mark becomes a self loop。

And remember what the algorithm does is when self loops like this appear。

 they get deleted automatically。And now that we've done our n minus two iterations without just two nodes。

 we return the corresponding cut by corresponding cut。

 what I mean is one group of the cut is the vertices that got fused into each other and wound up corresponding to the super nodeode in this case。

 everything but the bottom right node and then the other group is the original nodes corresponding to the other super nodeode and the contracted graphs。

 which in this case is just the bottom right node by itself。

So they set A is going to be these three nodes here。which all got fused into each other。

 contracted into each other， and B is going to be this note over here。

 which never participated in any contractions at all。And what's cool is you'll notice this does。

 in fact， define a min cut。 There are two edges crossing this cut。This one。

 the rightmost one and the bottommost one。 and I'll leave it for you to check that there is no cut in this graph with fewer than two crossing edges。

 So this is， in fact。Im in cuts。Of course， this is a randomized algorithm and randomized algorithms can behave differently on different executions。

 so let's look at a second possible execution of the contraction algorithm on this exact same input。



![](img/f183f01336855d22e8538dd56d80c603_5.png)

Let's even suppose the first iteration goes about in exactly the same way。So in particular。

 this leftmost edge is going to get chosen in the first iteration。

But instead of choosing one of the two parallel edges。

 let's suppose that we'd choose the rightmost edge to contract in the second it， Toally possible。

25% chance that's going to happen。 Now what happens after the contraction。Well again。

 we're going to be left with two nodes， no surprise there。

The contracted node gets sucked into oblivion and vanishes， but the other three edges。

 the ones with the hash marks all stick around and become parallel edges between these two final nodes。

This again corresponds to a cut。A and B。Where a is the left two vertices and B is the right two vertices。

Now， this cut， you'll notice has three crossing edges。

And we've already seen that there is a cut with two crossing edges， therefore this is not a min cuts。

So what have we learned， we've learned that the contraction algorithm sometimes identifies a in cut and sometimes it does not。

 it depends on the random choices that it makes， depends on which edges it chooses to randomly contract。

So the obvious question is， you， is this a useful algorithm， so in particular。

 what is the probability that it gets the right answer？

We know it's bigger than zero and we know it's less than one。

 is it close to one or is it close to zero？So we find ourselves in a familiar position we have which seems like a quite sweet algorithm。

 this random contraction algorithm and we don't really know if it's good or not。

 we don't really know how often it works and we're gonna need to do a little bit of math to answer that question so in particular we'll need some conditional probability so for those of you who need a refresher you go to your favorite source or you can watch the probability review part two to get a refresher on conditional probability and independence once you have that in your mathematical toolbox will'll be able to totally nail this question get a very precise answer to exactly how frequently the contraction algorithm successfully computes the minimum cut。



![](img/f183f01336855d22e8538dd56d80c603_7.png)