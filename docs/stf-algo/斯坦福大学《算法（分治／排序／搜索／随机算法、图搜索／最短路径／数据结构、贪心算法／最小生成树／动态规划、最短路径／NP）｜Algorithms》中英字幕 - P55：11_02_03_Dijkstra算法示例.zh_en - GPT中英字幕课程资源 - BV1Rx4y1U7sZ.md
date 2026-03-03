# 斯坦福大学《算法（分治／排序／搜索／随机算法、图搜索／最短路径／数据结构、贪心算法／最小生成树／动态规划、最短路径／NP）｜Algorithms》中英字幕 - P55：11_02_03_Dijkstra算法示例.zh_en - GPT中英字幕课程资源 - BV1Rx4y1U7sZ

![](img/391554e2b8c54591a1bafd8e3e01427a_0.png)

So let's just see how it works in the same example we traced through earlier。

So we started out just by initializing things in the obvious way。

 so the shortest path distance from S to itself， we say zero and the shortest path from S to itself is just the empty path。

And initially x is going to be just the source vertex itself so now we enter the main while loop and so remember in the while loop we say well let's scan all of the edges whose tail is in the vertices we've already looked at whose tail is in X and whose head is outside of X Now in this first generation there are two such edges there's the edge S comma V and the edge S comma W so how do we know which of these two to choose well we evaluate Dykes versus greedy criterion and so remember what that is Dykes versus's greedy score for a given edge Vw that's crossing the frontier is just the previously computed shortest path distance for the tail of the arc plus the length of the arc itself so at this point Sv has a greedy score of0 plus1 which is one and the arc s comma W has a greedy score of0 plus4 which is4 so obviously sv is going to be the shorter of those two so we use the edge Sv。

This is playing the role of V star W star on the previous slide。

 and the algorithm then suggests that we should add V to our set X， so we suck in V。And our new X。

Consists of S and V。And it also tells us how to compute the shortest path distance and the shortest path from SV。

 namely。In the A array， we just write down what was the greedy。

 the diyketras greedy score for this particular edge， And that was 0 plus1 or1。

 It also tells us how to compute the shortest path for V。 Naly。

 we just inherit the shortest path to the tail of the arc。

 which in this case is the empty path from S to itself。 and then we tack on the end。

 We append the arc we used to get here at the arc S of V。

So now we go to the next iteration of the Y loop， with our new set capital X consisting of S and V。

 and now again， we want to look at all edges which are crossing the frontier edges that have tail in X and head outside X。

And now we see there's three such crossing edges。 There's S comma W， there's V comma W。

 and there's V comma T。 All of those have the tail in X and the head outside of X。

 So we need to compute diyser's greedy score for each of those three and then pick the minimum。

 So let's go from bottom to top。 So first of all， we can look at the a S comma V S comma W excuse me。

 and the greedy score here is the shortest path distance for the tail so that's 0 plus the length of the arc which is 4。

 So here we get a4 in this iteration。Then if we do this crossbar edge， this VW edge。

 the diykester greedity score is the a value or the shortest path distance value of the tail。

 and we compute that last iteration， the A of V value is one。

 we add to that the length of the arc which in this case is two， so this edge3。

 this edge V comma W has a score of three。Finally， there's the arc V comma T。

 and here we're going to add one， which is the shortest past distance of the tail of V arc plus the edge length which is six。

 so that has the worst score。So since the edge V comma W has the smallest score。

 that's the one that guides how we supplement X and how we compute the shortest path distances and the shortest path for the newly acquired vertex W。

 So the changes are first of all， we enlarge x。

![](img/391554e2b8c54591a1bafd8e3e01427a_2.png)

So x is now everything but T。And then how do we compute things for W， where the shortest path。

 So our entry in the ARA is just going to be Dyster's greedy score in the previous iteration。

 So that was one plus2。 So that's going to be equal to3。And then what is the shortest path。

 how do we fill up the array B， Well we inherit the shortest path to the tail of the arc。

 which in this case is the arc S comm V， and then we append the arc that we used to choose this new vertex W。

 so that's the arc of VW。 So the new path is just the SVW path。

So that's what we compute is the shortest path from S toW in this graph。

So now we proceed to the final iteration of Dsrus algorithm。

 we know what vertex we're going to bring into x it's going to be the vertex T that's the only one left。

 but we still have to compute by which edge we discover T and bring it into the set X。

 so we have to compute the greedy score for each of the two crossing arcs V commt T and W commt T and in this final iteration the score for the arc VT is unchanged。



![](img/391554e2b8c54591a1bafd8e3e01427a_4.png)

So this is still going to be the a value of its tail1 plus the length of the arc 6。

 so the score here is still7， and now for the first time W comeee is a crossing edge of the frontier。

 and when we compute its score， it's the a value of its tail W。

 which is3 plus the length of this arc， which is three so we get a greed score of 6。

So by Dyxter's greedy criterion， we pick the edge WT instead of the E VT。

 and of course that doesn't matter who gets brought into X。

 but it does matter how we compute the A and B values for T。

So in the final iteration we compute AT to be the Dyser greedy score of the edge that we picked which is the edge WT and the score was6。

 so we compute the shortest path distance from S to t to B6 and then what is the path itself where we inherit the shortest path to the tail of the arc that we used to discover T so that's the shortest path to W which we previously computed as being the path through V and then we append the edge we used to discover T so we append the edge WT so the shortest path from S to T。

 we're going to compute as the zigzag path S goes to v goes to T sorry goes to W goes to T。

And then now indeed x's all of the vertices we've computed it for everything。

 This is our final output， the contents of the especially the a array is the final output shortest path distances from S to all of the four possible destinations and if you go back and compare this to the example you went through to the quiz you will see at least on this example indeed Dyketra's algorithm corrects the shortest path distances now I've said it before I'm going to said again someone shows you their algorithm works just on some example。

 especially a pretty simple fornote example， you should not jump to the conclusion that this algorithm always works sometimes algorithms work fine on small examples but break down once you go to more interesting complicated examples so I definitely owe you a proof that Dyketra's algorithm works not only in this network but in any network and actually it doesn't work in any network。

 it's only going to work in any network with nonnegative edge lengths so to help you appreciate that let's conclude this video with a non-ex showing what goes wrong in Dyketra's algorithm when you have networks with negative。

length。So before I actually give you a real non-example。

 let me just answer a preliminary question which you might have and would be a very good question if it's something that's occurred to you。

 the question would be well why is it why are these negative edge linkss such a big deal。

 why can't we just reduce shortest path computation with negative edge lengths to the problem of computing shortest paths with non-neative edge linkss right so why don't we just sort of clear things out。

 we just add a big number to all the edges that makes them all non- negative and now we just run Dx' algorithm and we're good to go。

So this is exactly the sort of question you should be looking to ask if as a computer scientist as a serious programmer。

 when confronted with a problem， you always want to look for ways to reduce it to simpler problems that you already know how to solve。

 and this is a very natural idea of how to reduce a seemingly harder short of path problem to when we already know how to solve using Dugtra algorithm。



![](img/391554e2b8c54591a1bafd8e3e01427a_6.png)

The only problem is it doesn't quite work。Why doesn't it work Well。

 if you let's say you have a graph and the most negative edge is minus10。

 so all the edge links are minus10 and above so then what you'd want to do is add 10 to every single edge in the network and that ensures that all the edge links are non negative run Dster's algorithm get your shortest path。



![](img/391554e2b8c54591a1bafd8e3e01427a_8.png)

The issue is that different paths between a common origin and destination have differing numbers of edges。

 so some might have five edges， some might have two edges。 Now。

 if you add 10 to every single edge in the graph， you're going to change path lengths by different amounts。

 If a path has five edges， it's going to go up by 50 when you add 10 to every edge。

 If a path has only two edges， it's only going to go up by 20 when you add 10 to every edge。

 So as soon as you start changing the path lengths of different path by different amounts。

 you might actually screw up which path is the shortest。

 the path which is shortest under the new edge lengths need not be the one thats shortest under the old edge lengths。

 So that's why this reduction doesn't work。To be concrete。

 let's look at this very simple three vertex graph with vertices S V and T and edge links as shown 1 minus5 and minus2。

Now what I hope is clear is that in this graph， the shortest path。

 the one with the minimum length is the two hop path， SVt that has length-4。

 the direct S Arc has length -2， which is bigger than-4。

 so the upper path is the shortest path Now suppose we tried to massage this by adding a constant to every edge so that all edge length were non negative we'd have to add five to every edge because that's the biggest negative number。

 the VT edge。So that would give us new edge length of six and zero and three。

And now the problem is we've changed which path is the shortest one。

 We added 10 to the top path and only five to the bottom path and as a result， they've reversed。

 So now the bottom path S is actually the shorter one。 So if you run diyer on this graph。

 it's going to come back with the path ST， even though that's not in fact。

 the shortest path in the original network， the one that we actually care about。

 so that's why you can't just naively reduce shortest paths with negative edge lengths to shortest paths with nonneative edge lengths。

Moreover， on this very same super simple3n graph， you know we can try running dikes for the shortest path algorithm it's perfectly well defined。

 it'll produce some output， but it's actually going to be wrong。

 it is not going to compute shortest path distances correctly in this graph， so let me show you why。



![](img/391554e2b8c54591a1bafd8e3e01427a_10.png)

Well， of course the initialization will work as it always does。

 so it's going to start by saying the shortest path distance from S to itself is zero via the empty path。

And then what's it going to do next， It's going to say， okay， well。

 we need to enlarge the set capital X by one vertex。

 And there are two crossing edges is the Xv edge and the S T edge。 And what's it going to do。

 It's going to use the dicester greedy score。 So the score of this upper edge is going to be one。

And the score of this bottom edge。Is going to be minus2。

Because remember you take the previously computed shortest path value of the tail that's zero in both cases and then you add the edge length。

 so the edge lengths are 1 and minus2 so the scores are 1 and minus2。

 which of these is smaller well evidently the ST arc has the smaller score minus2 so what is Ju's actually going to do it's going to say yes。

 let's go for this edgeST let's bring T into the set capital X T is now part of the Cond territory。

And of course， as soon as you bring a node into the set X into the Cond territory you have to commit or DyCsA's algorithm chooses to commit to its shortest path distance and its shortest path。

 what is the definition of its shortest path distance as computed by Dyixstra。

 where it's just its greedy score， so it's going to assign the vertex T。

 the shortest path distance of minus2 and the path is going to be just the ArcST。

But notice that this is in fact wrong the shortest path distance from ST T is not minus2 in this graph。

 there is another path namely the one that goes through V that has length4 less than minus2。

 so ditra computes incorrect shortest path distances on this trivial 3 node graph。

So to summarize the story so far， we've described Dexter's algorithm。

 I've showed you that it works in a very simple example that doesn't have negative edge lengths and I've showed you that it doesn't work in an even simpler example that does have negative edge linkss。

 so I've both given you some plausibility that it might work generally at least for non-negative edge links。

 but I've also tried to sow some seeds of doubt that it's not at all clear at this point if Dxter's algorithm is always correct or not even if you have non-negative edge length and certainly if it is always correct。

 there better be a foolproof argument for why you should be demanding an explanation of a claim that Dyters is correct in any kind of generality that's the subject of the next video。

