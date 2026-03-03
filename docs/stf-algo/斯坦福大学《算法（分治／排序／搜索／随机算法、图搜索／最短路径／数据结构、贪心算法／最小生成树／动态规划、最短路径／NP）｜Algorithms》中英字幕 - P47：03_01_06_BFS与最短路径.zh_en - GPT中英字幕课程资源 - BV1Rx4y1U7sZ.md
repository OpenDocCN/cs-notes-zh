# 斯坦福大学《算法（分治／排序／搜索／随机算法、图搜索／最短路径／数据结构、贪心算法／最小生成树／动态规划、最短路径／NP）｜Algorithms》中英字幕 - P47：03_01_06_BFS与最短路径.zh_en - GPT中英字幕课程资源 - BV1Rx4y1U7sZ

![](img/66d550c132ef29f84514ad35a8b9d4a0_0.png)

And let's begin with the idea of shortest paths， so again I'll give you the movie graph I give you Kevin Bacon as a starting point。

 what's the fewest number of hops， the fewest number of edges on a path that leads to say John Ham。

So some notation， I'm going to use DIST of V。To denote the shortest path distance。

 so with respect to a starting node S， the fewest number of hops are the fewest number of edges on a path that starts at S and goes to V。

And again， you can define this in the same way for undirected graphs or directed graphs in a directed graph you always want to traverse arcs in the forward direction in the correct direction。

And to do this， we just have to add a very small amount of extra code to the BFS code that I showed you earlier。

 it's just going to be very small constant overhead and basically it just keeps track of what layer each node belongs to and the layers are exactly tracking shortest path distances away from the starting point S。

So what's the extra code well first in the initialization step？

You set your preliminary estimate of the distance， the number。

 the shortest path distance from S to a vertex v， as well， if V equals S。

 you know you can get from S to S on a path of length0， the empty path。And if it's any other vertex。

 all bets are off， you have no idea if there's a path to V at all。

 so let's just initially put plus infinity for all vertices other than the starting point。

This is something we will， of course， revise once we actually discover a path to a vertex V。

And the only other rest of your code you have to add is。When you're considering。

 so when you take a vertex off of the front of the Q and then you iterate through its edges and you're considering one of those edges VW。

 so here V would be the vertex that you just removed from the front of the Q。And as usual。

 if the other end of the edge W has already been dealt with， then you know you just throw it out。

 that would be redundant work to look at it again。 but if this is the first time you're seeing the vertex W。

Then in addition to what we did previously， in addition to marking it as explored and putting it the Q at the back。

 we also compute its distance， and its distance is just going to be one more than the distance of the vertex V responsible for W's addition to the Q responsible for first discovering this vertex W。

So returning to our running example of breath first search。 let's see what happens。 So again。

 remember the way this worked is we start out with from the vertex S and we set the distance you know in our initialization equal to0。

 we don't know what the distance is of anything else。

 So then how did breath first search work So the initial step we put S in the Q。

 we go to the main while loop and then the queue's not empty。 we extract S from the Q。

 we look at its neighbors， those neighbors are A and B。 we handle them in some order。

 let's again think of that we first handle the edge between S and A。

 So then what do we do we say we haven't seen a yet So we mark a as explored。

 we put a in the Q at the front。 and now we have this extra step。

 It's the first time we're seeing A So we want to compute its distance and we compute its distance as one more than the vertex responsible for discovering A。

And so in this case， S was the vertex whose exploration unveiled the existence of the vertex A to us。

 S's distance is0。 So we said a's distance to1 and that's tantamount to being a member of the I layer。

 So what happens in the next iteration of the while loop。 So now the Q contains sorry。

 the next iteration of the for loop， excuse me。 So after we've handled the edge S comma A。

 We're still dealing with S's edges。 Now we handle the edge S comma B。

 We put this is the first time we've seen B。 we put B at the end of the Q。 We market as explored。

 and then we also execute this new step。 We said b's distance to one more than the vertex responsible for discovering it。

 that would again be the vertex S S led to B's discovery。

 And so we said b's distance to be one more than S is distance also known as one。

And that corresponds to being the other node in layer 1。Now， having handled all of S's adjacent arcs。

 we go back to the while loop， we ask if the Q is empty， Certainly not。

 it contains two vers first A then B。 we extract the first vertex because it's PIO。

 that would be the vertex A。 Now we look at A's incident edges。 there's S comma A which we ignore。

 there's a comma C。 This is the first time we've seen C。 So as before we mark C as explored。

 we add C to the end of the Q。 and now again we have this additional line。

 we set C's distance to be one more than the vertex responsible for its discovery In this case it's a that first discovered C。

 So we're going set C's distance to be one more than A's distance also known as2。

So then having handled A， we move on to the next vertex in the Q， which in this case is B， again。

 we can forget about the edge between S and B， we've already seen S。

 we can forget about the edge between B and C， we've already seen C。

 but D is now discovered for the first time via B， it gets marked as explored it goes to the end of the Q。

 and its distance is set equal to one more than B's distance， which is 2。So then we deal with C。

 again it has four arcs， four edges， three of them are irrelevant。

 the one to E is not irrelevant because this is the first time we've seen E。

 so E's distance is computed as one more than C because C was the one who first found E。

 and so E gets a distance of three。And then the rest of the algorithmgon proceeds as before。

 and you will notice that the labelings， the shortest path labels are exactly the layers as promised。

 I hope you find it very easy to believe at this point that that claim is true in general。

 that the distance computed by breadth for a search for an arbitrary vertex V that's reachable from S that's going to be equal to I if and only if V is in the Ih layer as we've been defining it previously。



![](img/66d550c132ef29f84514ad35a8b9d4a0_2.png)

And what does it really mean to be in the I layer， it means that the shortest path distance between V and S has eye hops eye edges。

So I don't want to spend time giving a super rigorous proof of this claim。

 but let me just sort of give you know the gist， the basic idea and I encourage you to produce a formal proof at home if that's something that interests you so one way to do it is you can do it by induction on the layer I and so what you want to prove is that all of the nodes that belong to a given layer I do indeed the best for search does indeed compute the distance of I for them so what does it mean to be a node in layer I well first of all you can't have been seen in either any of the previous layers you weren't a member of layer0 through I minus-1 and furthermore a neighbor of somebody who's in layer I minus1 you're seen for the first time once all of the layer I minus-1 nodes are processed so the inductive hypothesis tells you that distances were correctly computed for everybody from the from the lower layers in particular whoever this node V was from layer I minus-1 who is responsible for discovering you in layer I it has a distance computed as I minus-1 yours is assigned to be one more than its namely I so that pushes through the inductive。

Deep everything on layer I indeed gets the correct label of a shortest path distance of I away from S。

So before we wrap up with this application I do want to emphasize it is only breath first search that gives us this guarantee of shortest paths so we had a wide family of graph search strategies all of which find everything findable breathth first search is one of those but this is the special additional property that bread first search has you get shortest path distances from it so in particular depth first search does not in general compute shortest path distances this is really a special property of breath first search by contrast in this next application which is going to be computing the connected components of an underre graph this is not really fundamental to breath first search for example you could use depth first search in here instead and that would work just as well。

