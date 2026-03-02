# 斯坦福大学《算法（分治／排序／搜索／随机算法、图搜索／最短路径／数据结构、贪心算法／最小生成树／动态规划、最短路径／NP）｜Algorithms》中英字幕 - P140：12_01_04_重加权技术.zh_en - GPT中英字幕课程资源 - BV1Rx4y1U7sZ

![](img/7e3e5c5742f3e123dbba7d6f6a20744a_0.png)

Let's now proceed to the final algorithm for the all pair shortest path problem that we're going to discuss。

 It's called Johnson's algorithm and the algorithm shows something pretty amazing。

 It shows that even in graph with negative edge links。

 the all pair's shortest path problem can effectively be reduced to just n ins of Dykester's algorithm。

 Even though Dkester's algorithm for correctness needs nonneative edge links。

 So this video will discuss the key idea behind Johnson's algorithm will then proceed to the algorithm itself。

 and this idea is a way of using vertex weights to reweight shortest path links。😊。

When we began our discussion of the all pair shortest path problem。

 we observed that the problem reduces to n ins of a suitable subroutine for the single source version of the problem。

 simply by iterating over all n choices for the source vertex。

The running time you get from this reduction is evidently n times the running time of the single source subroutine。

And the running time of the subrtine is going to depend on whether your graph has non- negative edge links or not。

 if you're in the lucky case where the graph has non- negative edge links。

 you get to use Dster's algorithm， which runs blazingly fast， almost linear time M。

 the number of edges times log N。 if you're dealing with a graph with general edge links。

 then the running time was not so good。 It would be n times the bellman Ford running time。

 which itself is Mn。At the end of the day， you get a running time of N M log n for the non negative edges case or n squared M for the general edge length case。

And now that we know about the Flod Warshall algorithm， which runs in BigO of N cubes time。

 there aren't a whole lot of reasons to care about this solution in general E links that runs Belman Fort N times。

 except perhaps the fundamentally distributed nature of that computation。

Johnson's algorithm remarkably shows that the same running time we get here for the non negative edge length case。

 n times M times log n， we can get equally well for graphs that have general edge lengths。

Specifically， Johnson's algorithm shows that the all pair shortest path problem in graph with General E length reduces to one invocation of the Belman Ford algorithm。

 followed by N ins of Dexster's algorithm。As we know。

 the Belman Ford algorithm runs in biggo of M times n time。

 and Ins to Dxter's algorithm is going to be n times M times log n。Putting it together。

 we see that the nins of Dykstra dominate just barely。

 so the overall running time will achieve is Big O of Nm log n exactly the same running time we were getting for the non negative edge length case。

So this should probably sound a little too good to be true。

 How on earth can we reduce the shortest path problem with general edge links to the special case where all the edge length are non negative。

 Indeed， this is a trick that we actually thought some about in part 1 for those of you who are alumni of that course。

 Suppose you have the single source shortest path problem。

 And you've got a graph with some negative edge links。 A very natural instinct is to say， well。

 come on。 that can't be that big a deal。 let's just shift the edge length so they become nonnegative and then compute shortest paths。

 So if you have some graph where the most negative edge length is -5。

 Why not just add 5 to the length of every single edge。 Now you have a new graph。 nonneg edge links。

 and you just run dister's algorithm， big deal。So this quiz asks you to think about this edge shifting trick in general。

 supposeuppose you have a graph and there's a particular source S and destination T you're looking at。

 and suppose you add some constant number， capital M to the length of every single edge of the graph under what conditions will that preserve the shortest path between S and T。

All right， so the correct answer is C。Of the listed conditions。

 the only one that guarantees that adding a constant M to every edge length preserves the shortest path between a pair of vertices。

 S and T is that all of the path between that pair of vertices have the same number of edges。

 Maybe the easiest way to see this is just with a simple example。

So consider this simple pink network where there's an S T and there's two paths between them。

 one with two hops， each of cost 1， one with one hop of cost 3。 Now， evidently， in this graph。

 the shortest path is the one that goes through the vertex V that has length 2。

 The other one has length 3。 Now， suppose we add a fixed constant。

 let's say the constant2 to every one of these edges。In that case， the two edges on top。

 their links increased to three， the edge on the bottom its length increases to five。

 and you'll see that after we've shifted all the edge lengths。

 we've actually changed what the shortest path is。 It used to be the two hop path on top Now it's the oneh path path on bottom that has length5 the2 hop path on top now has length6。

So this shows that the answers A， B and D are all incorrect。 Y is C correct。 Well。

 suppose it was the case that between the vertex S and T。

 every single path in the graph had exactly the same number of edges， say every path had 12 edges。

 Well， then when you add a constant to every edges length， every path between S and T。

 their length goes up by exactly the same amount， it goes up by 12 times M。

 if each of the path have 12 edges in it。 So if every single path between S and T goes up by exactly the same amount。

 Well， then the shortest path remains exactly the same。

 the ranking of the lengths of the various path is exactly the same because we've added exactly the same number to all of them。

So the broader point here is that if we want to find a transformation of the length of a graph that reduces the general edge length case to the non negative edge length case。

 we need to aspire toward transformations that preserve what shortest paths are。

 and this transformation is not it。There's no reason for you to expect that there'd be any useful transformations of this form。

 any shortest path preserving transformations that are non-trivial。

 but such transformations do exist， that's the reweighting technique which we'll start exploring in the next quiz。

So in this quiz， we're again going to think about one of our usual directed graphs。

 every edge has a length and the links can be arbitrary real numbers。

Here is the twist for each vertex V there's going to be a number piece of V associated with that vertex。

 don't worry about where these piece of V's come from。 We'll discuss that later。

 Just think of it as any old number could be 7 could be minus5， whatever， just one number per vertex。

The key idea behind the reweighting technique is to use these n numbers。

1 weight per vertex piece of V， to use these n numbers to shift the edge length of the graph。

 I'm going to use C prime to denote these shifted or transformed edge length。

Here is the exact definition。 Consider an arbitrary edge E of this graph G。

 Let's say the edge goes from the tail U to the head V。

 The new length C prime of V is defined as the original length C E plus the weights of this edges tail。

 So plus P of U minus the weight associated with this edges head that is minus P of V。So for example。

 consider an edge from u to V that original length is 2。

 And let's say the weights associated with its tail and head are -4 and -3。

 Remember these vertex weights can be arbitrary numbers， positive or negative。 Well。

 then the shifted weight C prime is going to be by definition，2 plus-4-3。This， of course。

 is just equal to one。So that's the setup。 Here's the quiz question。

 I want you to think about some fixed path。 capital P， let's say it starts at a vertex S。

 and it ends at a vertex T。 Now， capital P may or may not be the shortest path。 I don't care。

 It's just any old path starting at S ending a T。 So suppose in the original network with the original edge lengths。

 C sub B， The total length of this path P was capital L。 What is its new length。

 L prime under these new edge lengths， C prime。So the correct answer is C。

Under the new edge lengths C prime， the path piece's length does not in general remain the same。

 but it shifts by a predictable amount， namely the difference between the node weights associated with S。

 the origin of the path and T， the destination of the path。This follows by a simple calculation。

The new length of the path P is， of course， just the sum over the modified edge length。

 the sum over the C primes of the edges in P。So now we just expand each term in terms of its definition。

 so remember the new edge length C prime of V is just the original length C plus the weight associated with the edges tail。

 U minus the weight associated with its head V。Now， consider a vertex other than S or T on this path。

 some internal vertex on the path。 So such a vertex is going to be the tail of exactly one edge of P。

 and it's going to be the head of exactly one edge of P。

 So its vertex weight is going to show up with a coefficient of plus1 once。

 and it will show up with a coefficient of -1 once。 Obviously， those two terms will cancel。

So the only vertex weights that matter when we evaluate the sum is the weight of the origin S and the weight of the destination T。

 the S only shows up once， and it shows up as a tail。

 So its vertex weight shows up with a plus one contribution。

 So that's where the piece of S term comes from。 symmetrically。

 the destination T only shows up once where the minus1 coefficient。

 So that's where the minus t comes from。So when the dust settles。

 all that we're left with is the sum of the original edge lengths that we're using the notation capital L for plus this shift term plus P of S minus P of T。

All right， so now that we've sloggged through the algebra。

 let me explain to you why we went through that exercise。

 what is the potential application of this reweighting technique？

So what did we just learn about the reweighting technique， Well。

 fix a graph and fix an origin vertex S and a destination vertex T。

 What we just learned is that when you reweight using these vertex weights。

 you shift every single st path by exactly the same amount。

 The length of every St path shortest or otherwise changes by exactly the quantity P of S minus piece of T。

So this is now starting to sound pretty cool because let's remember our first quiz。

 In our first quiz we explored what happens when you just add a fixed amount capital M to every edge of a graph。

 We notice that doesn't work in the sense that it can change the shortest path。

 Why can it change the shortest path while different paths have a different number of edges。

 So if you add some fixed amount to each edge， you change different paths by different amounts that can screw up the shortest path。

 If you're lucky and all of the paths between an S and a T have exactly the same number of edges。

 then you shift them all by exactly the same amount and you preserve the ordering of the paths。

 But what do we see here， we see that under no assumptions whatsoever about what the paths between S and T like。

 node reweighting Shis every single path from S to T by exactly the same quantity。

 the difference between P S and P。😊，Well， since reweighting changes the length of every path by exactly the same amount。

 That means it preserves the shortest path。 Whatever was the shortest path previously is still the shortest path after we've done reweighting。

So what？ Why is this interesting， Well， let's dream big。

 Suppose we could actually come up with vertex weights that transformed the problem into one that we don't know how to solve blazingly fast into one that we do know how to solve blazingly fast。

 That is， what if we can find vertex weights that change an arbitrary instance that in general has negative edge lengths into a shortest path problem where all of the edge lengths are now non negative。



![](img/7e3e5c5742f3e123dbba7d6f6a20744a_2.png)

So if such a transformation existed， I hope that its use would be clear。

 This would transform an instance of shortest paths where it seems like we're stuck with the Belman Ford algorithm because we start with negative edge links and it transforms it into an easier one where we can apply Dystra's shortest path algorithm。

Now， this best case scenario should sound like a free lunch to you。

 Why do we think we can do basically a trivial amount of work。

 just the simple shift of the edge length and transform a seemingly harder problem。

 Shortest paths with general edge length into an easier one。

 shortest paths with non negative edge length。 The catch， of course。

 is to figure out which vertex weights to use。 How do you know the magical edge weights that transform the general edge length into the non negative ones。

 Actually， more fundamentally， why do we even think that these vertex weights exist。

 maybe no matter how you pick the vertex weights， It's impossible to transform all of the edge length。

 so that they become non negative。 Well， it turns out as long as the graph has no negative cycle。

 which we know is essential to compute shortest paths。 If there's no negative cycle。

 they do always exist。 Mag choices of the vertex weights piece of V。

 that transforms all of the edge lengths to be nonneg。 Now， it's not trivial to compute them。

 you have to do some work， but it's not a prohibitive amount of work。 In fact， one in of the beman。

Agorithm will be sufficient Johnson's algorithm puts those ideas together。 that'll be the next video。

