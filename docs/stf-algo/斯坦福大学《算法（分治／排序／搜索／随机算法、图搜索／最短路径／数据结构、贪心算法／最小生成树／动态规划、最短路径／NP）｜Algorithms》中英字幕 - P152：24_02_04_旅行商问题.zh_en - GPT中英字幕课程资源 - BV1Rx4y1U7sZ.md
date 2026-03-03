# 斯坦福大学《算法（分治／排序／搜索／随机算法、图搜索／最短路径／数据结构、贪心算法／最小生成树／动态规划、最短路径／NP）｜Algorithms》中英字幕 - P152：24_02_04_旅行商问题.zh_en - GPT中英字幕课程资源 - BV1Rx4y1U7sZ

In this video， in the next， we're going to revisit the famous traveling salesman problem。

 When we first talked about T SP， it was bad news。 The context was MP completeness。

 We discussed Edmd's conjecture that it widely believed there's no known polynomial time algorithm for solving the T SP problem。

 But let's talk about some good news。 The fact that you can do better than naive brute for search。

 In fact， it's going to be another neat application of the dynamic programming algorithm design paradigm。

😊，So let me remind you briefly about the traveling salesman problem， the input， very simple。

 just a complete undirected graph， and each of the N chooseose2 edges has a non negative cost。



![](img/2d494bf671d6421d2b7952524662e091_1.png)

![](img/2d494bf671d6421d2b7952524662e091_2.png)

The responsibility of the algorithm is to figure out the minimum cost way of visiting each vertex exactly once。

 that is you're supposed to output a tour， a permutation on the vertices that minimizes the sum of the corresponding n edges。



![](img/2d494bf671d6421d2b7952524662e091_4.png)

For example， in this four vertex pink network， the minimum cost tour has overall cost 13。You could。

 of course， solve the problem using brute force search。

 The running time of brute force search would be roughly n factorial。

This would allow you to solve problems with， say， 12，13， maybe 14 vertices。



![](img/2d494bf671d6421d2b7952524662e091_6.png)

In this video， and the next， we'll develop a dynamic programming algorithm that solves the T SP problem。

 Now， of course， T SP is NP P complete。 We have to respect that。

 We're not expecting a polynomial time algorithm， but this dynamic programming algorithm will one quite a bit faster than bootte for search。

 The running time will be big O of n squared times 2 to the end。2 to the n is， of course。

 exponential， but is' quite a bit better than n factorial。 N factorial is more ballpark N to the N。

 Okay， if you look up Sterling's approximation， you'll see it's really n over a constant raised to the n。

 But still， that's much， much bigger than a constant2 raised to the N to make it more concrete。

 You could run this dynamic programming algorithm for values of N。 probably pushing 30 or so。

So I realize these are still pretty absurdly small problem sizes compared to the size of the arrays that we can sort compared to the size of the graphs on which we compute strongly connected components or shortest paths。

 but that's how it goes or then be complete problems。

 you have to work pretty hard even to solve modest size problems。

So at least this dynamic programming algorithm proves the point that even for NP completele problems。

 there are opportunities to improve over Rote force search and the programmer toolbox I've already equipped you with is sufficient to make some of those improvements。

😡，For the traveling salesman problem in particular。

 it's been a benchmark problem for the development of tools and optimization and people have worked very hard to solve very large instances of the traveling salesman problem。

 even with tens of thousands of cities， even sometimes over 100000 cities。

 but I mean this often represents years of work as I said earlier there's some really nice sort popular accounts of the traveling salesman problem books out there check it out if you want to know more about the state of the ark for solving large TSP instances。

So I said we're going to pursue a dynamic programming approach to the TSP。

 so that means we should be looking for optimal substructure a way in which an optimal solution must necessarily be composed of an optimal solution to a smaller subproblem extended in some easy way to the original problem so what could that look like for TSP。



![](img/2d494bf671d6421d2b7952524662e091_8.png)

![](img/2d494bf671d6421d2b7952524662e091_9.png)

So of all the problems that we've tackled using dynamic programming。

 I think the one which seems the most like TSP is single source shortest paths。

 so think about a tour not as a cycle exactly， but as a path from some vertex。

 let's say vertex number one， looping all the way back to itself with of course。

 the constraint that it should visit each other vertex exactly once on route。

We want to minimize the overall cost of this path from one back to itself。

 so that sounds a lot like wanting to minimize the length of a path from some source to some destination。

And I'm sure you'll recall that our dynamic programming algorithm for the single source shortest path problem was the Belman Ford algorithm。



![](img/2d494bf671d6421d2b7952524662e091_11.png)

![](img/2d494bf671d6421d2b7952524662e091_12.png)

So what then did the subproblem look like in the Belman Ford algorithm Well。

 the cool idea there was to measure subproblem size using an edge budget。

 So a canonical subprom in Belman Ford was to compute the length of a shortest path from the given source vertex to some destination vertex V that has I edges or less。

 So by analogy， we could think here about subproble where we want the shortest path from the starting node vertex number one to some other vertex J that uses at most I edges。



![](img/2d494bf671d6421d2b7952524662e091_14.png)

So precisely， let's define sub problems as follows for a given choice I。

 This represents the number of edges that you're allowed to use a given destination J。

 Let's assume the vertices are just named from one to N。

 So I'll call a generic destination J and integer from1 to N。

 Let's denote capital L sub Ij as the shortest length of a path from the starting vertex1 to this destination J using a most I edges。

 So suppose we try to set up a dynamic programming algorithm using these subproble。 So do you think。

 can we use these to get a polynomial time algorithm for the T SP problem。



![](img/2d494bf671d6421d2b7952524662e091_16.png)

All right， so the correct answer is C。So this proposed collection of sub problemsblems does not yield a polynomial time algorithm。

 That is D is not the correct answer。 That would be surprising。

 right TSP is an NP completele problem。 So if this gave a polynomial time algorithm。

 we could all report directly to the Clay Institute for a million dollar cash prize。

 Now there's a lot of students in this class， but at least we need to get 20 bucks or so out of the deal。

 So that's not the case。 This is not going to yield a polynomial time algorithm。

 What's the problem Well， the problem is also not a。 It's not that there are too many subproblems。

 we only have O of n choices for I and O of n choices for J。

 So there's only a quadratic number of subproblem， just like in Belmand Ford。

 That's totally reasonable。 We also can correctly compute the value of larger subproblems from smaller ones。

 It's really exactly the same as what were doing in Belman Ford。

 The problem is that our semantics are incorrect。 by solving these subproblems。

 we don't actually get an optimal solution to the traveling salesman instance that we started with。

So what are we hoping is going to be the case Well。

 in our dynamic programming algorithms thus far after we solved all of the sub problems。

 the answer to the original question was just lying there waiting for us in the biggest subproble。

 So here the biggest sub problemm would correspond to I equaling n where youre allowed to use up to n edges in your path。

The issue with these sub problems is they only specify an upper bound eye on the number of edges you're allowed to use。

 that dude does not enforce that you have to use your full budget of eye edges。

 So that means when we look at these biggest subproblem， yeah。

 the shortest paths could use as much as n edges if they wanted， but in general， they won't。

 They'll use much fewer than N edges。 they'll skip tons of the vertices and that's not a traveling salesman。

 Travel salesman has to visit Every vertex once that is not enforced by these subproblem。

That problem doesn't seem so hard to fix。 Let's just insist in each subprom that instead of using most eye edges in the shortest path。

 it has to use exactly eye edges in the shortest path。

So while this set of sub problemsms is not quite as misguided as the previous one。

 the answer remains the same， the answer is still C。

Of course we still don't get a polynomial time algorithm， we're not planning to prove peak was NP。

 the number of subprobles hasn't changed， it's still quadratic。

 and if you think about it you can still efficiently solve for bigger subproms with a bigger edge budget given the solutions to of the smaller subprobles。

So what's the issue， the issue is that our semantics are still incorrect。

 just because you solve all of these sub problemsblem doesn't mean you can extract from it the cost of a minimum cost traveling salesman tour。

So the problem briefly is that we don't enforce the constraint that you can't visit a vertex more than once。

 What were we hoping would be true。 We were hoping that we look at the biggest subproble。

 So this is when I is equal to n and we're looking at paths that have exactly N edges。

 And when we take J， the destination to be one， the same as the origin。

 we were hoping that that shortest path with N edges from one back to itself would be a tour。

 and therefore， the minimum cost traveling salesman tour。 but that need not be the case。

 just because this path has n edges， and it starts at one and it ends at1， doesn't mean it's a tour。

 It might， for example， visit vertices 7 and 23 twice。 And as a result。

 it never visits vertices 14 or 29 at all。For this reason。

 the number computed by the largest subproblem when I equals n and when J equals 1， that can be much。

 much smaller than the true answer for the minimum cost traveling salesman tour。

A good algorithm designer is nothing if not tenacious。

 so let's just recognize the flaw in this proposal that we're not enforcing the fact that you can't have repeat visits to a vertex and let's just change the subproblems yet again to explicitly disallow repeated visits to a vertex。

So precisely， let's index the sub problems in exactly the same way as before。

 there going to be one for each budget I and once for each destination J for a given eye and a given J。

 the value of the sub problemblem is now defined as the length of a shortest path beginning at one。

 ending a J using exactly I edges with the additional constraint that no repeated vertices are allowed。

 The one exception being that if J is equal to one， then， of course。

 you're allowed to have one at the beginning and one at the end。

 But for the internal vertices in a shortest path， we do not allow repeats。

So what do you think does this refined collection of subprom allow us to get a polynomial time algorithm for the traveling salesman problem？

So the answer to this quiz is more subtle than the past couple。

 and the correct answer has switched from C to B。 It's still the case that there's a quadratic number of sub problems。

 It's still the case that we don't expect a polynomial time algorithm。

 but now that with this different definition of subproble， they do capture the TSP。 specifically。

 look at the biggest subproble。 Take I equal to N。 Take J equal to1。

 The responsibility of that subpro is to compute the shortest path from one to one that has exactly n edges and no vertices repeated internally。

 That is exactly the original problem that we started with。 That is exactly TSP。

The issue is that you cannot efficiently solve larger sub problems。

 problems with a larger edge budget， given the solutions to the smaller sub problems。

 the smaller sub problems are just not very useful for solving the bigger sub problems。

 and the reason is a little bit subtle。

![](img/2d494bf671d6421d2b7952524662e091_18.png)

Now the hope would be that like in all our previous dynamic programming algorithms。

 you can just formulate a recurrence which tells you how to fill in how to solve bigger subproms given solutions to smaller ones。

 and there's even a natural guess for these subproblem what you hope the recurrence might be。



![](img/2d494bf671d6421d2b7952524662e091_20.png)

Recurrences generally follow from a thought experiment about what optimal solutions have to look like。

 So you'd want to focus on a particular subpro， A given destination J and a given budget I in the number of edges。

 You'd say， well， let's think about an optimal solution。 So what is that。 That's a path。

 It starts at one。 It ends a J。 It has exactly I edges。 It has no repeated vertices。

 and amongst all such path， it has the minimum length。



![](img/2d494bf671d6421d2b7952524662e091_22.png)

![](img/2d494bf671d6421d2b7952524662e091_23.png)

![](img/2d494bf671d6421d2b7952524662e091_24.png)

And it's natural to proceed by analogy with Belman Ford and say， well。

 wouldn't it be cool if a little birderie tell me what the penultimate vertex K was on this shortest path from one to J。



![](img/2d494bf671d6421d2b7952524662e091_26.png)

![](img/2d494bf671d6421d2b7952524662e091_27.png)

So if I knew that the second to last vertex on a shortest path was k。

 well then surely the length of this path would be the length of an optimal path from 1 to k using exactly I minus1 edges and no repeated vertices with this final hop Kj concatenated at the end。



![](img/2d494bf671d6421d2b7952524662e091_29.png)

![](img/2d494bf671d6421d2b7952524662e091_30.png)

Now， of course， you don't know what the second to last vertex K is。

 but no big deal as usual in dynamic programming， we're just going to try all of the possibilities。



![](img/2d494bf671d6421d2b7952524662e091_32.png)

So we can encode this brute force search as a minimum。



![](img/2d494bf671d6421d2b7952524662e091_34.png)

Over the sensible choices for K， clearly K should not be equal to J。

 it should be some other vertex that precedes J， and ignoring some base cases。

 let's also preclude K from being1。 That's the starting vertex。And of course。

 pictorially what we have in mind is we have in mind taking some shortest path from1 to K。

 so we'd looked that up that would be previously computed in some smaller subproble and then concatenating to it a final hop that goes from K to J。



![](img/2d494bf671d6421d2b7952524662e091_36.png)

![](img/2d494bf671d6421d2b7952524662e091_37.png)

Well， hey， that sounds pretty good， right， Doesn't that kind of sound like maybe this is the key ingredient to a polynomial time algorithm for T SP。

So what's the problem， Well， the problem is that we've defined our subpro to disallow repeated visits to a vertex。

 So when we compute a subprom， we better make sure we're respecting that constraint that no repeated visits are allowed。

 And if we have in our mind， concatenating a shortest path from one to K with no repeats with this final hop K to J。

 Well this might result in a repeated visit to J。 In particular。

 for all we know the shortest path from1 to K that uses exactly I -1 edges and has no repeated vertices。

 that path might well go through J， in which case concatenating this final hop K J results in a cycle。

 a second visit to J。

![](img/2d494bf671d6421d2b7952524662e091_39.png)

![](img/2d494bf671d6421d2b7952524662e091_40.png)

So this bug means that the proposed recurrence is not correct。

 The recurrence is computing something which in general is less than the actual shortest path length from1 to J with exactly I edges with the no repeat visits constraint respected。

 That could be a bigger number than what's computed by this recurrence。

And I encourage you to think about， is there any way to fix this bug。 Could you propose a different。

 more complicated recurrence， which was still easy to evaluate。

 but was actually getting the sub problem value correct。 I don't think you're going to find one。

So the moral of the story is that this constraint in the traveling salesman problem that each vertex gets visited exactly once。

 that's a quite tricky constraint， and we're going to have to work quite hard to make sure it's satisfied。

The solution we're going to use is in some sense a logical next step from this recurrence here。

 we need to be able to know more information about subpro problems than just where they end。

 We actually need to know the identities of the vertices on the path used to travel from one to K。

 We need to know whether or not V is on that path。 So we're going to look at a much bigger set of subproble where we remember not just destinations。

 but also all of the intermediate stops。 That idea will translate to a dynamic programming algorithm。

 not a polynomial time1 needless to say the details are coming right up。

