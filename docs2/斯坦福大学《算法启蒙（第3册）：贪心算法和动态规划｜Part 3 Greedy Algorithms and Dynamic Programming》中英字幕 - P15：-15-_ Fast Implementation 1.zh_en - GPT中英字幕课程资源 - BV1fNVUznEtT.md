# 斯坦福大学《算法启蒙（第3册）：贪心算法和动态规划｜Part 3 Greedy Algorithms and Dynamic Programming》中英字幕 - P15：-15-_ Fast Implementation 1.zh_en - GPT中英字幕课程资源 - BV1fNVUznEtT

![](img/431a4f78be2a6163a1b07703b62c4b86_0.png)

So at this point， we understand Prims algorithm and we also know why it's correct。

 That is why it always computes the minimum cost spantry of a graph。 So in this video。

 we're going to turn to implementation issues and running time analysis。

 We'll begin by just analyzing the straightforward implementation of Prims algorithm that's already reasonable It's polynomial running time but not especially close to linear。

 Then we'll see how a suitable deployment of heaps very much in the way that we did for Dexter's algorithm leads to a blazingly fast near linear running time。

So let's briefly review the pseudocode for Pris algorithm。

 recall that Prim grows a tree one edge at a time spanning one new vertex in each iteration。

 so it maintains two sets， capital X a set of vertices that have span so far and capital T these are the edges we've committed to thus far they start out by just being some arbitrary vertex little S and the empty set and in each iteration of this main wild loop we add one new edge to the tree and whatever new vertex that edge spans we add that to capital X the algorithm terminates when we're spanning all of the vertices and as we've seen it halts not just with a spanning tree but with a minimum cost spanning tree so suppose we just literally implemented this algorithm as is what would be the running time。

Well， the initialization step takes only constant time， so let's ignore that。

 so then we just have this one loop， so let's just ask how many iterations does the loop take and how much time is needed to execute each iteration。

Well， the number of luiterations is going to be exactly n minus1。

 so where n is the number of vertices， x starts out with one vertex it terminates when it has all n vertices。

How much work do we need to implement each iteration Well essentially what each iteration is doing is a brute force search through the edges。

 it's looking for the edges that have one endpoint inside X and one end point outside and amongst those it just remembers the cheapest and it's easy to see that you can implement each iteration in O of M time or M is the number of edges。

For example， you can just with each vertex associate a Boolean variable that keeps track of whether or not it's in the set capital X that way。

 when you see an edge， you know whether it's crossing the frontier or not in constant time。

 So putting it together O of N iterations with O of M work for each gives us a running time of O of M times n。

So this running time is already nothing to sneeze at as we discussed graphs can have an exponential number of spanning trees。

 so this algorithm is doing far less work than examining each of these spanning trees。

 It's homing in in polynomial time to the minimum cost one So that's pretty cool。

 but remember the mantra of any algorithm designer worth their salts confronted with a solution you should always ask。

 but can we do better and can we do better than running time O of M times n we can as we'll see in the rest of this video。



![](img/431a4f78be2a6163a1b07703b62c4b86_2.png)

The big idea for speeding a Pris algorithm is exactly the big idea we used in part one to speed up Dyter's algorithm。

 namely we're going to deploy a suitable data structure so what data structure seems like it might be a good idea for making Pri run faster Well what's happening in the main workhorse while loop of Pris algorithm over and over again we keep needing to do a minimum computation amongst all edges crossing the frontier we need to find the cheapest one so the question we should ask ourselves is what kind of data structure would facilitate would speed up repeated minimum computations and if you recall from part one we have a data structure where that's exactly what it's ra on detra is the heap the meaning of life for a heap is to speed up repeated minimum computations just like in Pris algorithm。



![](img/431a4f78be2a6163a1b07703b62c4b86_4.png)

![](img/431a4f78be2a6163a1b07703b62c4b86_5.png)

So let me just remind you briefly， what are the operations exported by a He data structure and what is the running time？

So first recall that a heap contains a bunch of objects and each of those objects should have some key value from some totally ordered set like a number。

 like for example， an edge cost， so what can you do with a heap。

 well the salient operations for our purposes today are first of all。

 you can insert new stuff into the heap with their whatever their key value is you can extract the object with the minimum key value and you can also delete stuff from the middle of the heap and all of these can be done in logarithmic time。

 logarithmic and the number of objects stored by the heap。

So it's not going be important for us today to know how heaps are implemented what they look like under the hood。

 we're just going to be clients of them。 we're just going make use of these operations and the fact that they're running logarithmic time。

 But know just for those of you who are curious and or want to have your memory jog under the hood heaps are implemented logically as complete binary tree。

 they're actually laid out in an array， but you sort of think of them conceptually as being in a complete binary tree and they satisfy what's called the heap property and the he property is to make sure that you know where the object with the minimum key value is So the actual definition is every parent should have a key value which is less than that of its children So as you go up the tree。

 the key value can only drop and that means you know where the minimums got to be it's got to be at the root of this tree or the front of the array So that's great。

 that's how you locate the minimum so quickly in a heap Now what do you do when you want to extract the minimum So you rip off the root of this tree and now you have to rearrange the tree to restore the he property。

Swaamp the last leaf up to where the root was you bubble down as needed to restore the heat property how do you insert you put the new object as the new last leaf and you bubble it up as needed to restore the heat property to delete from the middle of a heap you just sort of rip it out and then bubble things up or down as necessary to restore the heat property again that's not supposed to if you're hearing this for the first time I know this is too fast this is just to jog your memory for those of you who already learned this in part one of the course for more details you can go review the appropriate videos there。

So now that I've reminded you about the salient properties of heaps。

 let's return to the question of how do we deploy them cleverly to speedup Prims algorithm。

So our intuition is that because we're doing repeated minimum computations in Pris algorithm each time in this wild loop to compute the cheapest edge crossing your frontier that's sort of in the wheelhouse of heaps。

 so how should we use heaps well the first idea which is a pretty good idea is to use the heap to store edges because our minimum computation should result in us choosing an edge so when we extract min from a heap we want it to hand us an edge on a silver platter so it would seem this would be your first thought that the heap should store edges and that the key value that you use should just be the edge cost because you want to find the cheapest edge。

So this is already a quite good idea using heaps in this manner will already definitely speed up Prims algorithm relative to the naive implementation and in fact。

 and I'll leave this as an exercise for you to work out using heaps in this way results in an implementation that runs in time big O of M log N What I'm going to show you instead is not that implementation but an even cleverer implementation of using heaps we're not going to see a benefit in the asymptotic running time。

 this more sophisticated version will also give us m log n running time。

 but it would give you better constants and it is the version you would want to implement in practice。

So the one slightly tricky point in this exercise is remember in Pris algorithm。

 you don't just want the cheapest edge overall in each iteration。

 you want the cheapest edge which crosses the current cut that has one endpoint in each of x and V minus x。

 and when you use heaps in this way， it might hand you on a silver platter and edge which is cheap。

 but isn't necessarily crossing the frontier so you need some extra checks to ensure that you're always finding the minimum edge and that edge crosses the frontier between x and V minus x。

So I'll leave it to you to work out the details of this implementation and the privacy of your own home what I want to spend our time together on instead is the somewhat more sophisticated。

 more practical way to use heaps and for those of you who remember our fast implementation of Dixtra。

 this will be very familiar to you， it'll be the same kinds of ideas that we used for Dtra and the key point is instead of using the heap to store edges we're going to use it to store vertices。

So in a bit more detail， our plan is going to be to maintain two invaris。

The first invariant is going to describe what the he contains。

 the second invariant is going to be what the key values of those heap objects are。

 so as I said we're now going to be storing vertices in the heap not edges， which vertices。

 exactly the vertices that we don't yet span， the vertices of v minus x。

The motivation here is that rather than getting on a silver platter。

 the edge in which to add next to the tree， we're going to get from the heap on a silver platter。

 the vertex that we're next going to add to capital X。

So the second invariant tells us what the key values of these vertices and v minus x are supposed to be。

 and we're going to define them to be the cheapest cost of an edge incident to this vertex that crosses the current frontier。

So I think a picture will make this definition clear。

So consider some snapshot of Pris algorithm at some iteration。

 We have our vertices X that we're already spanning。

 We have our vertices V minus x that we're not spanning。

 And remember the elements of the heat by Mar 1 are exact a vertices on the right hand side。

 the vertices of V minus x。 So we're trying to define the key value for some vertex in the heat。

 So some vertex v， which is on the right side， which is not in X。

And so what we do is we look at the edges incident on this vertex V that go back to the left hand side。

 so edges incident to V that are crossing the frontier， and there may be， of course。

 be many such edges。And the invariant we want to maintain is that the key value for this vertex v is the cheapest of all the incident edges crossing the frontier。

 or in this picture， the key should be equal to2。There is the niggling issue of how do you define the key if there are no incident edges at all that are crossing the frontier。

 so maybe you have a vertex W which is buried deep inside of v minus x and actually none of the incident edges go back to the left blob at all so in that case we just define the key to be plus infinity。



![](img/431a4f78be2a6163a1b07703b62c4b86_7.png)

So given this high levelvel approach to implementing Pris algorithm using heaps。

 we now have a few things to think through。 So first of all。

 we have to think about how to initialize the heap so that these invaris are satisfied at the beginning of Pris algorithm。

 Second of all， we have to check that if these invariants are satisfied。

 then we can faithfully simulate each iteration of the wild loop and Pris algorithm。

 hopefully very quickly And then third， we have to think about how do we make sure these invariants are maintained throughout the course of Pris algorithm。

 So let's do those in turn。 So the first thing is how do we set up the heap at the beginning of Pris algorithm and a preprocessing step so that both of these invariants are satisfied。

 Well， at the beginning X consists just of this single arbitrary star vertex S V minus x contains the other n minus1 vertices。

 The key value of a vertex other than s at the beginning of Pris algorithm is just the cheapest edge between that vertex and S if there is one or plus infinity otherwise。

 So the thing to think through and make sure you believe this is that。First of all。

 with a single scan through the edges。 So an O of M time。

 we can compute the key value for each vertex that needs to go in the heap。

 And then we just have to insert those n -1 vertices into the heap。

 So that's going to cost us O of M time for an edge scan。And then en log N for the inserts。In fact。

 for those of you that really know heEaps very well， you might know about a HePA Fi operation。

 which allows you to do a batch of n inserts in O of N time because you can do this even faster in linear time。

 but we're not going to need that in this lecture。And also。

 I claim that this expression M plus n log n is bounded above by the expression M log n。

 at least an asymptotic notation。 To see that， remember two things。 First of all。

 we're assuming that the input graph is connected。 Otherwise there's no spanning trees and it's not interesting to talk about minimum spanning trees。

 Second of all， in any connected graph。 The number of edges M is at least n minus-1。

 So asymptically M is always at least as big as n and it can be bigger。

 So you can always replace an n by an M and get a valid upper or bound。

 So that's what we're doing here。The second issue we need to think through is how do we faithfully simulate each iteration of the wild loop and Pris algorithm given that these two invaris hold？

So this issue is going to work out beautifully really by construction。

 we set up our heap and we set up our definition of keys so that extracting men from the heap and iteration is a faithful simulation of the brute force search in the naive implementation of Prims algorithmm。

So specifically assuming that these two invaris hold when we invoke extract min from this heap。

 what it provides to us on a silver platter is the next vertex not yet in X。

 the next vertex that we should add to x in this iteration and moreover the cheapest edge incident to that vertex crossing the frontier is the one that we should be adding to the set T in this iteration and the way to think about this fact is to think of us is essentially simulating the brute force search to the naval implementation using a two round knockout tournament So in the straightforward implementation of prim。

 the way we think of it is we just do a scan through all the edges crossing the frontier and we remember the winner。

 we remember the smallest cost of the all here with a heap we're doing it in two steps So first of all for each vertex on the righthand side of the cut for each vertex in V minus x it locally remembers what is its best candidate So what is the cheapest edge incident on that vertex crossing the frontier。

 So that's kind of round one So for an。To be chosen as the winner at the very least。

 it better be a local winner it better be the cheapest edge crossing the cut that ends at this particular vertex on the right hand side of the cut。

 So that's just in the definition of the key of each vertex it encodes the value of the winner local to that vertex and then this extract min is invoking the second round of this two round elimination tournament it's saying well amongst all the proposals from the first round amongst all the crossing edges that are locally minimum。

 given its endpoint， which of them is the cheapest overall and that's going to be the cheapest edge crossing this cut the result of this extract min computation。

