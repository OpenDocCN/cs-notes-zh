# 斯坦福大学《网络优化算法｜A Second Course in Algorithms for network optimization》中英字幕 p19 -19-Lecture 19_ Beating Brute-Force Search). -BV14CAUeUEPj_p19-

O。So。The point of today's lecture is doing better than brute force search for NP hard problems。

 So just to remind you we've been talking about NP hard problems for a couple of weeks。

 but we've been focusing on approximation algorithms where you insist on polynomial time and therefore you have to relax correctness so we're looking at approximate correctness always being close to the optimal solution So this time we're actually going to insist on full correctness we're asked for algorithms that are always correct now for an NP hard problem you don't expect it to run in polynomial time so you'd like it to run as fast as possible and at the very least you'd like to run faster than brute force search and again the first time you sort of learnmp completeness often you're sort of taught to think ofmp completeness is meaning you can't beat brute force search but reality is a little more nuanced so actually there's a lot of problems where there are exponential time that are algorithms which are significantly faster than brute force search and then in this lecture will revisit three old friends and see that concretely so the vertex cover problem and then the traveling sales。

problemblem and finally three set okay？So that's the point of the lecture。

 you can often beat Bote for Search and you sort of already know a lot of the ideas necessary to do so。

So we talked a lot about vertex cover on Thursday we're going to talk about it again now。

 it's actually going to be a special case we're going to look at of where there's no weights so in other words the cost of every vertex is one So remember in general the vertex cover problem I give you an undirected graph non-neegative costs on vertices you want to minco vertex cover so here you just want a minimum cardinality vertex cover we're going a vertex cover as a subset of the vertices that includes at least one endpoint from each edge of the graph so the same problem as on Thursday except all costs equal to one。

And actually we're going to look at even。More of a special case。

hi is rather than computing the minimum size of a vertex cover， I'm going to give you a target K。

 and add I just want you to figure out is there or is there not a vertex cover of size of most K。Now。

 in general， this isn't really that much simpler a problem if you could solve this problem。

 you could just run through all values of K and see what's the sort of smallest one for which you can find a vertex cover。

 So here the special case is we're going to be thinking of K as small。Okay。

So if you kind of like having some concrete numbers in your mind。

 think of k as say like between 10 and 20 and the graph as maybe hundreds of nodes or thousands of nodes。

 we want to know if it has sort of like a really nice small vertex cover okay。

And so for this problem， we're going to do better than brute force search。All right。

 so what's the line in the sand？So how long does it take to do brute force search？

So the most naive brute force search to check is a vertex cover of size k。Or less。

Like as a function of n and K， what's it going to be roughly？And choose K， that's right。Right。

 so given given a alleged vertex cover， it's easy to verify it。

 whether or not it is a vertex cover or not。 So the obvious thing to do is try all possibilities for a size K or less vertex cover Okay。

 so brute force is going to be。You know， proportional to n choose k。

 the number of subsets of size k of the vertices， which in the small K case， you know。

 is basically n raised to the K。Okay， end the Cape power。Now strictly speaking for any constant K。

 this is a polynomial time algorithm but if you think about actually running this。

 I mean you can't run this algorithm unless K is super small。

 like two or three or something like that， okay so even K equal 10， forget it。

 you could never run this algorithm。Okay。So we want to do better than this。

And so just you know a comment about context， so this idea of know having an algorithm for an NPR problem that runs fast when some parameter is small。

 like the optimal solution， what you're seeing here is just a glimpse of a much broader field called parameterized algorithms and parameterized complexity there's a whole course on that topics。

 CS226 taught here at Stanford usually by my colleague Ryan Williams so you can see a lot more examples like this in CS226 so we're just going to have this one example so I can sort of you can get a taste for it。

 but know that there's kind of a very vibrant research field around these kind of parameterized running time bounds it's been actually quite quite lively over the last 10 years or so。

Okay。So if by beating brute force search， what do we expect， what would we like to do？

So what we'd like the dependence on n， the graph size to be polynomial no matter what K is。Okay。

 so some polynomial on N。Now， we're not expecting a polynomial time algorithm for all k that would imp p equals NP P。

 so there's going to be some dependence on k and maybe the dependence on K is going to be not so good。

 like exponential。But better than n to the K would be a running time bound where the terms involving n and the terms involving K are different are separated from each other so in particular。

 K does not appear in the exponent of n is what we'd like。And again。

 because because we don't expect really sub exponentialent time algorithms for vertex cover。

 we think we expect F to be at least exponential in K， although hopefully not worse than that。

Or even。You know， MP hardness does not preclude。A runningun time with a form polynomial in the graph size plus some presumably exponential function of the size of the set that we're looking for。

All right。Okay。And so running times， so algorithms of this type。

Our problems of this type are called fixed parameter tractable。Or FPT。Okay。

So that's a buzzword you can always look the fixed parameter detractable algorithms。

So for the vertex cover problem， okay， so it turns out there's some problems which seems to admit algorithms of this form。

 some problems and parameters where you get algorithms of this form and somewhere you don't for vertex cover I'm going to show you next that we do get a running time of this form you of this better one okay pulling normally on n even you know essentially linear n。

Plus， an exponential function of K。 And again， this doesn't contradict P equal N P or anything like that。

 because when in general in the vertex cover problem。

 the optimal size of a vertex cover might be big， it might be like n over 2。

 And so then if F is exponential in K， we're not getting a sub exponential time algorithm for general vertex cover。

 We're just doing much better when we're checking for small vertex covers okay。

So questions about the setup？Okay。So。Here's going to be the algorithm。

 this again we're giving an undirected graph， all costs or unit。

 we want to see if there's a small vertex cover or not。

So the first thing we're going to do is we're to look at the degrees of all of the vertices。

And any vertex。With degree at least k plus1。We're just going to put in our vertex cover so far。Okay。

So again， we're looking for， say a vertex cover of size 10。Any vertex with degree 11 or more。

 we just sort of right up front put that in the set S。And that's without us a generality。

 Do you see why？We're checking for a vertex cover so if we want to know if there's a vertex cover that only has 10 vertices。

And we don't pick some vertex with degree 11， well then to cover all of those 11 incident edges。

 we have to pick all of their other endpoints， but that would be 11 vertices and the vertex cover and we don't have the budget for that。

Okay。So if there's a vertex covered with size of most k。

 it must include all vertices with degree at least k plus 1。Okay。

It's sort of a pre processingcess step。Oh。So two more preprocessing steps。

We've argued that we have no choice but they take all the vertices in S。

And that means we now don't have to worry about covering any of the edges incident to vertices and S。

 they're going to be covered because we pick all of S。So to get the residual vertex cover problem。

We just delete the vertices S that we've already chosen from the graph。allong， of course。

 with all of their incident edges， so all the edges that we delete， we've already covered。

 all of the edges that are left in G prime， we haven't covered。

So the residual problem is to supplement the vertices in S by a vertex cover of G prime。Okay。

That's where we are。All right， so the third step just says well。You know。

 G prime probably know after we've deleted all of S， there might be some isolated nodes。

 vertices with degrees0 Okay so there's no reason to pick those right that just means that all of the edges incident to that vertex are already covered by vertices in S。

 Okay， so there's literally no reason to pick this isolated vertex。

 It's totally redundant with our previous commitments in the set S。

So just like with all loss of generality， we take S。

 given that we're taking S without loss of generality。

 we can remove all isolated nodes from G prime called the result G double prime。Okay。

So now we see how big GW prime is。it add more than k squared edges。Then we assert。

That there is no vertex cover of size at most k。And you see why that's true？

So what's the degree of every vertex that's left in GW prime？Well。

 we removed all the ones with degree at least K plus ones。

 everybody left in G double prime has degree K or less。

 The degree of a vertex is exactly how many edges it covers when you pick it。

 assuming no redundancies with other people。 So each vertex in GW prime can only cover K edges。

 you're only allowed to pick K of them， given the budget on your vertex cover size。

 So the better be a most k squared edges otherwise， there is no hope。Yeah。Okay， so so far so good。

So now we get to kind of like of the real problem， which is G double prime。

 So we have part of our vertex cover S。 We need to pick the rest of the vertices from G double prime so that we cover all the edges in GW prime。

Which is just the vertex cover problem， but it's the vertex cover problem。😊，In a much smaller graph。

So how we're going to solve it， we're going to solve it by brute force search in the smaller graph。

And at the end of the day， we return yes。If and only if。C double prime。As a vertex cover。

Of size and most。K minus S， okay， and we implement five just by brute force search。

 literally enumerating over all subsets of the vertices of GW prime of this size and checking if it's a vertex cover or not。

Okay。So that's the whole algorithm。Okay。So I've already sort of talked through the correctness。

So I'm not really going to write anything more down formally。

 but so just to review the first claim was that any。

 if there does exist a vertex cover of size of most k， it has to include all the vertices and S。

 so without loss we can restrict attention to that。Those edges are already covered。

 so without loss we can delete all the edges and into S。

Isolated vertices don't cover any edges or without loss。

 we can delete the isolated vertices from GW prime。We're correct if we actually halt in step 4 again。

 because with that many edges and such small degrees。

 there's no way you could have a small vertex cover。 And then finally， you know。

The vertex covers of size of most k of the original graph are precisely s plus any vertex cover of size of most k minus size of s in the reduced graph G to prime。

 and we solve that by brute force search， so that's clearly correct。So any questions about that。

 I wasn't planning on really saying more about correctness。Okay。All right。

 so what about the running time？So the running time follows from this claim。If we reach step five。

 and of course we may not。I guess one sort of edge case I didn't really mention。

 So it's possible this is negative。 Okay， If S had k plus one or more vertices。

 but then it's sort of clearly a no， right， So you need all the high degree vertices。

 If there's more than K high degree vertices， then clearly there no vertex cover of size of most K。

 Okay so if this is negative， then just think of this as being an automatic no。All right。

 so in step five。The size of G double prime。Is all of K squared？Okay first you're saying。

 wait wait this is obvious， it's like by definition， but what do I mean by size。

 so definitely the number of edges in G double prime is the most k squared。

 that's because otherwise we halt and moreover， remember GW prime has no isolated vertices。

So that actually means with only k squared edges， it can have at most two k squared vertices， okay。

 the sparse as it could be is just a perfect matching on the nodes。Okay。

 so the size of the graph is k squared， which means brute force search is just going to be2 to the k squared。

 2 to the O of k squared， we pick all subsets potentially of G double prime。So the final runtime。

Straightfor， implement。In O of M。Plus o of2 to the， let me do it this way，2 to the o of k squared。

And this is of the promised form so polynomial time plus a function that depends only on k。

 the polynomial that depends on the input size is as good as it could be， it's linear time。

 we knew that F was going to be exponential realistically otherwise we'd have a sub exponential time algorithm for vertex cover so the best exponential you you might want an exponential that's like2 to the K or even 1。

5 to the K so here we're getting2 to the o of k squared so you'd like that to be better。

 but still just exponential function。And K。A nice homework problem。

 so I didn't ask it to all of you this quarter， but a nice homework problem is to use some of the linear programming techniques that we were discussing last lecture。

 and you can actually get this down to O of K so that's sort of a really best case scenario and parameterized algorithms。

 right so you get linear time in terms of the graph and just a single exponential function in terms of the parameter。

And so this is actually a particular type of FPT algorithm。

 so this grab GW prime that we constructed。And fixed parameter tractable language is called the kernel。

And the point is， is that you can take a vertex cover problem。

On an arbitrary graph as big as you want， and you can reduce it to the same problem on an instant size。

 which depends only on the parameters。 Okay， so in this case。

 we reduce it to the verless cover problem。On a graph with only O of k squared vertices and there is and so you again get a kernel which is linear size in this homeworkr problem。

 and so that gives you the two0 of k。 you only wind up doing brute4 search on a graph with a linear and K number of vertices。

So this is one way of beating brute force search。 Okay， And again， you know。

 I just want to emphasize end to decay K， which was brute force search。 I mean。

 that's really unrealistic for any problem instance you could imagine。

You know this however you know you're not going to be able to solve large instances。

 it's an NPR problems here it's not surprising， but really at least it does sort of push the tractability region you know quite a bit further past brute force search's to two to the K is really much。

 much， much better than end to the K if you think of n as being even 100 it's a big， big。

 big difference。So various NP hard problems and various parameters。

 some of them have algorithms like this， some of them seem not to so there's also sort of a subpart of complexity theory where they prove analogs of NP completeness for fixed parameter tractability so you show things like if so for example。

 Cique and independence that is one example which is thought to not have a fixed parameter tractable algorithm so you have these things known as W1 hardness and W2 hardness。

 analogous to NP hardness such that know if you had an FBT algorithm。

 it would cause some other collapses which are thought to be unlikely so again I'm not going to talk about any of this。

 but just know that there's kind of a sort of rich literature out there which you can see more about in CSs2266。

Okay。Any questions about that？So that's the first of the three。Problems wanted to talk about。O。

All right。So next we're going to visit the traveling salesman problem。And actually。

 Im going to give you an algorithm which even works in the non metric case。Okay。

So remember the traveling salesman problem is the input is a complete graph undirected。

 every edge has a non negative cost， your responsibility is to find a minimum cost TSP tour。

 what's a TP tour， it's a simple cycle which visits every vertex exactly once。And in general。

 for the general version of the problem， what we saw was that it was NP hard to even approximate it to any factor alpha so we talked about TSP。

 what did we do， we looked at the metric special case。

 so we assumed that the edges satisfied the triangle inequality。

 and then we were able to give good approximation algorithms。

 we had the MST heuristic a two approximation we have Christtoidei's algorithm which was the threehals approximation。

Okay， so here we're even dealing with a non metric case。

 we're not going to assume that the edge cost satisfied the triangle inequality and we're going to solve it optimally。

Now of course， it's going to be an exponential time， but again。

 it'll be faster than brute force search。So if you have in vertices。

What kind of running time are you going to get from brutefor search for traveling salesman problem It's like two to the end。

In factorial， right， So pretty much the feasible solutions are all orderings in which to visit the vertices。

 And that's going to be a factorial number。 And in factorial is a lot bigger than two of the N。Okay。

 and factorial is more like end to the end。 It's not quite that bad， but it's close。

 We'll talk more about that a little later。So end factorial is brute force。

And what I'm going to show you next is I'm going to show you dynamic programming algorithm。

Which has running time and squared times2 then。Okay。So within factorial， you know。

 if you're on your laptop， you could probably handle input sizes within equal to 12， maybe to 13。

You know，And with this， you know， you're still not going to be able to go that big。

 but you're going to be able to get into the 20s， with this algorithm。

 so we're going to extends the tractability frontier for this sort of very hard problem。

One drawback to the dynamic programming algorithm is that it also uses exponential space。

I guess oh two of the end space is enough。And。Brote force search of course does not right brute force search is easy to implement polynomial even near linear space and it's actually an open question。

 whether for the TSP problem or even for the special case of the Hamiltonian cycle problem。

 whether or not there exists in algorithm with running time of the form two to the end or even four to the n or even 10 to the end。

 some constant to the end， and simultaneously running in polynomial space。That would be nice。

 we don't know if one exists。Interesting open question。Okay。So that's the plan。

And again sort of the two takeaways from this you know of this exercise So first of all it's another examples where it's a famous NPR problem and actually brute force search is not what you're stuck with。

 you can do better， but also you know it's going to be a dynamic programming algorithms So in principle it's a little more complicated than the ones you do in CS161 but in principle you could teach this in 161 so it's again an example where all this sort of tools in your algorithmic toolbox that you've been developing it just useful everywhere it doesn't matter if you're doing exact algorithms there polynomial faster exponential time algorithms。

 approximation algorithms or whatever。Good。So。Should I want to do this？I want to do a new board。

And I'm sure all of you know last problem set do tonight at midnight。

 there is no exercise set number 10， okay， so the final just exercise sets one through nine。Okay。

So algorithm。Okay。For notational purposes， let's call the vertices of the instance one up to n。

It's a dynamic programming algorithm， so there's going to be an array that corresponding to a bunch of subprom that we're going to populate systematically。

So it's going to be a two dimensional array because as you'll see。

 our subproblem are indexed by two different things， okay？Now， as you know。

 sort of in dynamic programming， once you've figured out the right collection of sub problemsble to study where so you can solve the bigger sub problemsble quickly given the solutions to the smaller sub problems。

 you're pretty much done so usually like you're struggling with a dynamic programming solution and then finally it all clicks when you figure out the right set of sub problemsblem So I'm just going to cut to the chase and sort of tell you what are the right sub problemsblem that give you this algorithm。

All right，Semantics have a subprom。So again， there are two indices。On the one hand。

 you have a subset of V。And then on the other hand， you have a vertex。And in fact， a vertex of S。

Okay。So a sub problemblem is indexed by a subset of vertices， S plus a vertex J。

And what we want to populate this array entry with。Is the length of the min cost？Half。

So at the end of the day， we want a tour， but we're going to build up paths。

Linkked to the Minco path。Such that it visits every vertex of S exactly once。

 and it doesn't visit anyone else。So， visits each。K and S。Exactly once。It's going to start at vertex。

1。Okay， so all paths begin at vertex1。And then Jay indicates。The final vertex on this Minco path。

Okay。Ends add J。Now， for this to make sense， it better be the case that vertex1 belongs to the set S。

 and it better be the case that vertex J。Belongs to S， okay？

So S is the vertices that you visited so far。You're keeping track of the start point， vertex 1。

 you're keeping track of the endpoint vertex J， but you're allowing optimization over whatever order you want to visit the rest of the vertices of SN。

Okay， so that you're sort of not keeping track of。 That's what the subprom is supposed to do。

 So among all ways， you can visit precisely the vertices S of S in some order， starting from one。

 ending a J。 What is the minimum cost such path。So the definition of that subprom clear？Okay。

Now for someprom to sort of work out， you need a few different things going on， oh， I should say。

You know so most of the dynamic programming algorithms that you've seen are probably polynomial time algorithms this is an NPBR problem so we're not expecting it to be polynomial and so therefore we're maybe not surprised to notice that the number of subproble is exponential in n right so if you think about S there are two to the n different possibilities for the subset S sub vertices but again two to the ends much less than n factorial and we were expecting exponential。

It'The number of subpro。Is theta of n times 2 to the n， n for all choices of J。

2 to the n for all choices of S。Okay， so one thing that better be true about the sub problemsblem is that if we solve all the sub problemsm。

 we should have solved the original problem， I the Minco TSB tour okay？But in fact。

 the cost of the Minco TSV tour is easy to read off from the solutions of the biggest subpro where s is equal to all of the vertices。

 when s is equal to all of the vertices this just says what's the cheapest， sorry。

 the cheapest path from 1 to J visiting every vertex exactly once。

 I guess it's a Hamiltonian path from1 to J。Now， of course。

 given such a path it's easy to complete it to a tour。

 you just insert that last edge between vertex 1 and vertex J。Now， on the optimal TSP tour。

 we don't really know whicht J is the one that precedes one vertex1 on the optimal tour。

 but there's only n possibilities so we can just check them all。と。

So this is basically brute force search over the n minus1 possibilities for the vertex preceding one on the optimal TSP tour。

One of these we'll guess correctly。And what we're going to do。

 so the observation is just that if you think about the optimal TSP tour， you know of course。

 it has to be an optimal path from1 to its last vertex J， whatever J is okay。

And that's what we have computed。And then we also have to take into account the cost of the final edge。

 CJ1。So everyone okay on that？So if we can solve all of the sub problems， then in linear time。

 we can figure out the cost of the TSB tour and as usual with dynamic programming。

 if you want not just the value of the optimal solution， the optimal solution itself。

 all of the usual tricks will work for that like backtracking tricks， for example。

So questions about that？Al right， so if we can solve the sub problems， then we're done。

 So then really， you know， the final ingredient that we need is we need a way to systematically solve larger subproblem from smaller subproblem。

 so that is we need a recurrence telling us the ways in which larger subproblem solutions can be composed from optimal solutions to smaller subprom。

 right that's the name of the game and dynamic programming。And again。

 the way I'm presenting this in lecture is kind of the opposite of how one actually does this oneself。

 so normally when you're trying to devise a dynamic programming algorithm。

 the first thing you figure out is the recurrence and you sort of figure out how optimal solutions are composed from optimal solutions to smaller subpro from that you back out of recurrence。

Then once you have the recurrence， you can zoom out and say， well， then reverse engineer the subprom。

For ease of presentation， I'm doing it in this order。Okay。

 so I'm not going to talk about the base cases when s is just a single1。

 those are sort of easy to handle， so suppose you have a sub problemm with at least two vertices in S。

So again， remember what we want to compute here， we want to compute a path。

 it visits every vertex of S exactly once it starts at1 it ends a J。

We don't know what that looks like。But。We do know that there has to be some vertex K that precedes J。

And then the path from one decay better be optimal， otherwise you could substitute a different。

 better path between 1 and K visiting the vertices outside of s minus J and get a better path from S to J。

 visiting all vertices of S。So basically what we're going to do here。

 so just like in the final output， we in effect， guessed what was the final vertex visited before vertex 1 and take the best of all possibilities for the recurrence。

 we're just going to guess the penultimate vertex of the best path from one to J visiting S。

 there's only a linear number of possibilities。 We're going to check them all， take the best。Okay。

 so what are the possibilities for the penultimate vertex。

 the second to last vertex on the optimal path？Well， it should belong to the set S。

Maybe you want to think of， let me ignore the case where。

Where s equals 2 and then then I'm going to say here is correct so one should be part of s if s equals 2。

 then actually if you think about it， the previous vertex is1。

 so think of that as another base case if you want and k should not be sorry。

K not equal to1 to what a myth， right？And then K， of course， should not equal to J。Okay。So again。

 what's the point， the optimal solution by definition that's the best path from 1 to j visiting everybody in S。

 so what are the candidates for the vertex right before J。

 assuming we're visiting at least three vertices， any of the vertices of S other than the two endpoint of the path。

1 and J okay？Oh I guess I should say what this is。All right， so what's the sub problem？Well。

 you're looking at the subpath that's not visiting J， so you're going to visit one fewer vertex。

 you're not going to visit J。And we're guessing that K was the penultid vertex of this path。

 so the end point of the subpath。And then just like here。

 we have to account for the cost of the final hop。So getting from k to J。Okay。

So any questions about that？I wasn't planning on formally doing a correctness proof。

 it's just by induction。 So really the question is， do you believe the recurrence？

Do you believe that it's really true that this left hand side。

 the cheapest path from one to J visiting S really is the minimum overall possible guesses for the prompt vertex K of the cheapest path from1 to K visiting everybody in S other than J plus that last top from k to J？

Yeah。Okay。Good。Right， so I guess I should say， what order do you solve the sub problemsm。

 Well from smallest to largest。 So how do you measure the size of these sub problemsblem。

 or you just look at the cardinality of the set S。 Okay。

 so the first thing you do is you handle the base cases。

 you handle all the cases where S has only a single vertex。

 then you handle the cases where S has two vertices， then three vertices and then four vertices。

 Notice if you do that， all of the things you need on the right hand side of the recurrence have been previously computed when you considered smaller sets。

 So they're available for constant time lookup in your 2D array。

How much time does it take to solve a sub problemm， Well each of these lookups is constant time。

 it's previously computed and you're searching over a most linear number of vertices and S。

So linear time per subproblem。Remember the n times 2 to the NS sub problems。

So n squared two to the end time。Overall， as promised。K。So any questions about that？

So that's an example where we' beat brute4 Search for an NP hard problem without making really any compromises other than。

 I guess the space blow up。We didn't look at a special case。

 we didn't look at a parameterized version， like with vertex cover， we simply had a faster。

 if still exponential time algorithm。Okay。And our final example is going to be another example of that type。

 or it's an NP hard problem， we're just going to solve it in general。

 faster than you might have expected if you thought all you could do is brute force search。

So questions before。The final example for today。Okay。So our last example is going to be threeAT。

 the canonical MP complete problem。So remember how this works， so there are n Boolean variables。

 you're going to be looking for a truth assignment， your assignment， you're able to true or false。

There are clauses， each clause is a disjunction that is an ore of three literals， literals。

 either a variable or a negation。Of a variable。 So a clause just asks for。

One of the literals to be satisfied by the truth assignment and in the threeat problem you look at the conjunction of the clauses。

 so you want every single clause to be satisfied by the same truth assignment Last lecture。

 we studied the optimization version Max3at where the goal was to just satisfy as many clauses as you can here we're just going to look at the more standard decision version that you learned in 154。

 we just want to know yes or no， is there a satisfying truth assignment or not。So。

What kind of running time is brute force for threeat？Within the decision variables。

Two to the n there's two to the in truth assignments， true or false for each of the n variables。

And so you just try them all， okay， you know， maybe times linear time to actually check if it's a satisfying assignment or not。

So that's what we're trying to beat， we're trying to beat two to the end。

 and we'll beat it actually by a pretty significant amount， which is kind of cool。

So we're going to talk about。An algorithm due to shing。Which， while not exactly new。

 at least is newer than a lot of the stuff we do in CS261， it's from 1999 originally。U。

Its a little context。So shown its algorithms for three set。 It's going to be a randomized algorithm。

 And it's an extension of a previous really neat algorithm by Popa Dimitri for the two set problem。

 Okay so what's two set。 Well same thing， except now we clause as only two literals instead of three。

Interesting fact， if you haven't seen it before， twoat can be solved in polynomial time。Okay。

 so checking whether or not there' is a satisfying assignment， Max2at is again NP heartt。

 but you just want to check if it's satisfiable or not too sat， polynomialton。

The classic way of proving that is to reduce it to computing strongly connected components of a suitable directed graph。

So that gives you a linear time solution to the twoat problem。

Ppa Dimitri proposed a quite different randomized algorithm and that that is also a polynomial time so it's only n squared。

 so it's not really the one you'd use in practice， it is conceptually very interesting and so Shain's algorithm will extend the twoat randomized algorithm which was polynomial time to threeatAT。

 of course it won't be polynomial time but it will be significantly better than brute force。

So how can you do that， so how can you figure out satisfiability without looking at everything。

 so here's how you do it。So it's going to be a randomized algorithm。

 so it's going to be a randomized experiment that will repeat a bunch of times capital T T will figure out what T is later。

 basically the running time is going to be basically proportional to T。All right， so what do you do。

 well first you try a random assignment。Okay， so there's two to the end truth assignments。

 you just pick one at random。 each variable equally likely to be true or false and independently。

Now you repeat the following。And talks。Or you know， needless to say。

 if you ever find a satisfying assignment， you just halt immediately and report yes， okay？

So as long as you have not yet found， right so if you pick randomly and this is satisfying boom。

 you're done but what if it's not a satisfying assignment？What do you do？Well。

 at least one of the clauses has to be not satisfied。Otherwise you would have stopped。

 so pick a violated clause arbitrarily。It violated clause CJ。

Now we're going to do so this clauses three variables。

We choose from those three variables uniformly at random， I we pick an arbitrary clause。

 but then within the clause， we pick one of the three variables involved uniformly at random from the three possibilities。

And we flip。The value of that variable。If it was previously false， we make it true。

 if it was previously true， we make it false。Choose a variable of CJ。Uniformly at random。

Pifft's value。And now you go back up to the repeat end times， okay？So again。

 you check if it's satisfying， if it's still not satisfying， there's some violated clause。

 it's going to be a different violated clause than last time。

 but you're again going to pick a random variable from the new clauses and flip it and you keep going。

Now， if you so there's sort of an outer loop of T random experiments。

 then there's sort of any iterations of this inner loop。And if after all of these n times t。

Interlopierations， you haven't found a satisfying assignment。

Then you very boldly declare that none exists。And that is the algorithm。Okay。

So it's really it's a random search algorithm。 you would say local search， but local search。

 you're actually like looking at objective function to improve each time and here you're not doing that。

 you're just flipping something a random Okay， so it's the form of random search。And that's it。

any questions about the algorithm？Okay。And let's start trying to understand it。

So I'm going to keep giving you better and better running times for this algorithm via sort of slightly more sophisticated analyses。

 I'll give you either two or three versions depending on the time。

So the first thing to notice is that， so randomized algorithms sometimes can make mistakes。

 so they have errors。Suppose you feed in an unsatisfiable formula to this algorithm。

 Will it ever mistakenly call it satisfiable。No， but it only says satisfiable when it actually has a satisfying assignment in its hands。

 So you're always correct when you say satisifiable。If we handed a satisfiable formula。

We're not of course， guaranteed with 100% probability that this will find one。Okay。

 so maybe it just goes into a silly you know infinite loop just alternating that seem between the same two bad random assignments。

 So by analysis， what are we trying to do， we're trying to understand what is the probability or the random coins are the ones flipped by the algorithm。

 what is the probability that when we feed this algorithm， a satisfiable instance。

 it actually finds one or the bad case， what's the probability it fails to find one when one exists okay。

So the correctness analysis， we're always going to be thinking about the satisfiable case。

 because obviously it gets the unsatisfiable ones， correct？All right。

 so consider a satisfiable instance。And you know if there's many satisfying assignments。

 pick one arbitrarily， call it a star so think of this as just an n vector of true false values。And。

Suppose we have any。Not satisfying assignment。Okay。Call it A so at any given time in our algorithm。

 we currently have some truth assignment， which is not satisfying the formula。

All rightSo here's a really simple observation。So for all clauses， not satisfied by A。Okay。

Of the three variables in that clause。A must differ from a star in its assignments of at least one of those three variables。

A star satisfies all the clauses， in particular this one。A does not。

 so they differ somewhere on these three variables。Okay。

 so its assignment to one of the three variables of the clause differs from what A star gives it。

So what that means is that when we take this clause and we flip the value of one of the variables。

 there's a one in three chance， at least that we pick a variable。Where a has a wrong。

 where a star has a right and a has a wrong， and by flipping it。

 we then make our assignment A closer by one variable to the satisfying assignment a star。

Now it could go the opposite direction， it could be that you pick a variable where actually ANA star are the same and you flip it and you make them different。

 so that would actually increase the distance between AA star by one。Okay。

 so you have at least a one and three chance of decreasing the distance by one。

 you have the most of two over three chance of increasing the distance by one。

Notice that the probability might be better than a third so it maybe be that A and a star differ on two or even all of the variables of the satisfying assignment。

 then you have a much better chance of bringing them together。

 but the worst case is that two of the variables in A are the same as a star and there's only one which is off。

 but you still have a one and three chance of guessing right and flipping it to agree with a star。

Okay。So probably at least a third。Flipping a variable。Decreases。The distance， and by distance。

 I just mean the number of variables that are assigned different values。So between A and A star。

Byu one。Otherwise。The distance increases by one。Okay。Summ we're okay with that？So what are we doing。

 we're trying to understand in what sense does this random search algorithm ever make progress？

So here' here's a sort of probabilistic progress at every step。 Okay。

 it's a little weird because it's not monotone right。

 it can go backward and actually the odds sea against us。

 right there's only a one in three chance that we make progress is's a two and three chance we go backward okay。

But that's where the exponential time is going to come from。

 It's exactly because of that unbalanced bias。So our progress measure is just going to be。

 you know what's the difference between our current assignment A and the assignment a star obviously if we ever have distance zero to a star。

 we're done， we found a satisfying assignment。Notice if there are many satisfying assignments。

We just picked one or a star arbitrarily， so the algorithm might stumble upon a different satisfying assignment。

 even though its distance is far from a star， that's only good for us。

 we're only going to basically give the algorithm credit when it actually hits a star or terminates early。

All right。So。Suppose the distance between A and a star is k， so k out of the n variables。

Are different。Well， each iteration。There's a one and three chance we bring them closer together by one。

And if that happens， k times in a row。And we're at A star。Okay。

K variables are different and we get lucky and we have k iterations in a row where we bring them closer together at the end of that a was a star we have a satisfying assignment。

Yeah。So of Aa star。Okay。Different K variables。Flipping variables of violated clauses。

Yields a satisfying assignment， either a star or something that hits earlier。Okay。Oops in。Incates。

At most。With probability at least one third to decay。So this is like the algorithm gets lucky。

 and it just makes a B line from the current truth assignment A to this reference satisfying assignment。

 a star。 And again， it might finish early。 That's fine。You may notice that okay， in the algorithm。

Where's the algorithm， Here's the algorithm。 So in the inner loop， we repeat n times。 Okay。

 so the biggest K could be is n。Okay so to handle all possible choices of k， we repeat n times。

 of course， you if k is something like n over2， for all we know the algorithm is actually not going to find something in the first n over2 interlo iterations。

 but then it gets lucky and finds one later。 we're not even going to count that。

 Okay so over and over again in this analysis， we're going to actually discard the probability of the algorithm succeeding in various ways。

 We're just going to lower bound the probability of a subset of the ways in which the algorithm can succeed。

So this is a way I can succeed if at any point it finds a random assignment that's k variables away from this reference assignment A star。

 it gives you a one in three raised to the K chance of finishing within K iterations。All right。

 so what is K。 So this is just this parameterized bound。 This is true， no matter what K is。

But what do we expect K to be if we just pick a random assignment？N over 2， and actually by symmetry。

 the probability that K is n over2 or less is exactly a half。Good for each variable。

 you have a 5050 chance of agreeing with a star with it， okay？

So if you look at one of our capital T trials and you look at a。

 a knot has distance n over two or less from a star with probability at least a half。Okay。

So one way this algorithm can succeed。So。Is。To first pick a random assignment。

 which agrees with the A star in at least half of the positions。

 and then to n over two iterations in a row， get lucky and make the right choice of the one and three variables to flip in the violated gloss。

So these are all the things that have to happen Okay so you have a starting assignment where k is n over two or better and then n over two times in a row。

 you make the correct choice of the one and three variables。So if this ever happens。Then。

The algorithm indeed finds a satisfying assignment。All right。

 so from this we can back out what capital T needs to be so the name of the game here is obviously if it's satisfiable。

 the more trials we do， the probability that we find an assignment only goes up So the question is how large do we have to take capital T so that the probability that we miss a satisfying assignment is quite small okay say inverse polynomial in n Now it's an NR problem and every iteration can be implemented in polynomial time。

 so we're expecting the number of iterations to be exponential the question is what exponential is it。

😊，All right。So what do we conclude？So if the formula is satisfiable。We succeed in tea。

Outer iterations。Okay so think of each of this like choosing an a knot and then doing n random flips。

 think of each of those as a trial， we have capital T trials。

 we argued that each trial succeeds with at least this probability。I guess for notation。

 let's call this P。Succeed。Except。With probability， well what has to happen okay？

So how could you never find a satisfying assignment in any of the capital T iterations。

 well this would have to not happen every single time？Okay。So if this is not happening。

 that's just the compliment events。And then this would have to happen t times in a row。

 and they're independent。 so we just take it to the T power。 Okay， Oh， I have P here。So let's Du P。

All right， so how should you think about this， well this is easiest to understand if you use the estimate again。

 remember1 minus p is always bounded above by e to the minus x。

 we've used that a couple times already this course。

So this failure probability is upper bounded by e raiseds to the minus p times t。Remember。

 we want our failure probability to be small， what's small， let's say inverse polynomial in n。

So we want to solve for the value of capital T so that this failure probability is inverse polynomial。

And that's easy to do， you just take t equal to1 over p to cancel that out。

And then you boosted by another logarithmic term。And this is nothing。

 this is not specific to this algorithms is just always true。

 so whenever you have a subroutine which has one sided error。

 so it sort of does something wrong only in a particular case， otherwise it's always correct。

 and you want to boost the correctness probability， this is the relevant derivation。All right。

 so right， So this is。One over end of the D for your favorite constant D picket however you like。

When tea。Equals d natural log of n over p。Okay。And if you plug in this value for capital T here。

 the P's cancel， you have e to the minus d natural log of n， also known as1 over end of the D。Okay。

 I thinks just by setting doever you want， you can get the failure probability to be。

As small inverse polynomial as you once。And so now we're done because we already know what P is for this algorithm。

So this is P。So we want to look at。We just want to plug that in for P here，So what is this。

 this is theta， so let me suppress all the constant factors。

 I'm going to ignore that one half I'm going to ignore this D。So what is this。

 so this is one third to the n over 2， so we flip that， we get three to the n over  two。

 also known as root 3 raised to the end。这。So root three raised to the end。I was natural log it。Okay。

So to summarize if we run this algorithm。With capital T equal to this。

 then we'll never make a mistake when it's unsatisfiable。 And if it's satisifiable。

 we'll make a mistake with only probabilities， say one over n cubed。So in that sense。

 it's solving the three set problem。 just makes a tiny bit of error sometimes in the satisfiable case。

Route 3， that's like 1。73。 So this is already a nontrivi improvement over2 to the n。

So by doing random search， we really don't need to look at all of the assignments， you can do better。

So questions about that？Okay。So it's actually quite easy to。Make this bound even better。So first。

 let's keep the algorithm literally exactly the same and just prove a sort of better。

 meaning smaller bound on the capital T that we need to get a low error probability。

So the idea is we're going to try to do something smarter than this。 Okay。

 so previously what we said is like， well， you know。

 if you have a trial and the algorithm sort of screws up and picks a random assignment。

 which is more than an over two away from a star， let's just give up。

 Let's just like pretend like the success pro is zero。So let's be a little smarter about that。

 so we pick a random assignment， it has some distance K from a star。

 and then we're going to have some success probability， which is a function of k。Okay。So。

So to do this， we need to have an understanding of， okay。

 what's the probability of various values of k again。

 K will always be the distance between the initial assignment here and。

The reference assignment A star。So distance between a and a star equals k。So how would that happen。

 Well， so that means there's exactly K out of the n variables that you got wrong。Okay。

So there's n choose K choices for which are the K variables， you get wrong in your random assignment。

 and then you have a two to the minus n factor， basically up for every variable that you get right。

 you have to flip the coin actually has to come up right for variable you're getting wrong。

 you have to actually flip the coin and come up wrong。Okay。

So the distance between a0 and a star is k for any k between 0 and n with probability exactly n choose k。

2 to the minus n。Okay。So this is sort of like the same thing as saying， you know。

 like what's the probability that you get you flip a sequence of N coins。

 what's the probability that you get exactly K heads？And don't care about。Okay。So。Then。

So let's just have a smarter version of this thing where rather than just sort of conditioning on whether you're in over2 or less。

 let's actually parameterize it by K。So a trial succeeds。Now with probability， at least。Well。

 you look at all the possible choices of the initial distance between a knot and a star。

We agreed that the probability of a given distance k is n choose k times ss2 to the minus n。

And then in the case where a star and A differ in exactly k spots。

 then the chance that you get lucky and you just make a B line straight to a star。

Is one third to the K。看。Everyone cool with that？So in effect。

 what we're doing is we're conditioning on the distance between a knot and a star。Conditioned on K。

 this is a lower bound on our success probability， then when we remove the conditioning and take expectation over what the value of k actually is。

 then we get this term。Al right。So。I don't know how this looks to you， this maybe looks like a mess。

Like， how do we interpret this？But actually。We're pretty stoked to get this expression。

So let's pull out the part that doesn't depend on k。

So we just get sum over K and choose k times a1 third to the K。

Might start reminding you of like binomial expansions。Right。

So like a plus B raised to the end is like sum over blah， blah， blah， blah。So actually。

 with the binnoonic expansion， we can recognize this as exactly。One plus one third。To the end。Okay。

So again， think about expanding this。If you expand all of these products。

 how many times are you going get the term of the form1 third raised to the K， Well。

 that means you chose the one third exactly K times。You chose the one exactly n minus k times。

 and those n choose k different terms from which you could choose those K1 over threes。So again。

 this is just the bi noial expansion that you would have learned in 103。So it's pretty sneaky。

To recognize it here， but it works。Okay。So this is a fourth third to the n。

 this is a2 to the minus n。So what we have here is。What do we have， two thirds？To the end。Okay。

So this is our new P， our old P。Was one of a root  three raised to the n。

 Our new P is two thirds raised to the n。 So again。

 just sort of plugging in for what we have to set P to B in order to get our desired error probability。

So now we get a running time。呃。So succeed。With high probability。When t is equal to theta of 1。5。

To the end。Large in。Okay。I cool with that？Any questions？

This bound is like the slickest of all of them in a way。

 So I'm going to show you an even better bound。 but this three halfs to the end is maybe the one kind of worth remembering。

Is it so nice？Okay。So we can even do a little bit better than this。 Okay， Again。

 we're already kind of blowing away2 to the n。 It's pretty nice。1。5 to the n is definitely like。

 you can definitely solve bigger problem sizes than you can with two to the n。

 It's pretty noticeable。😊，But so let's do one more step。

 so I'm going to tweak the algorithm slightly。Instead of n here， I'm going to make this3 n。Okay。

What's the intuition， so what are we trying to do？Again， all along。

 we've been sort of analyzing the success probability of our algorithm by like throwing out so many different ways it could succeed。

 zooming in on just a subset of the ways it could succeed and even just lower bounding that probability。

And so notice we've actually only been counting a success in this special case where you literally move monotonically from your random initials assignment a not to a star。

 so if you' differ in K spots， you really have to flip you know K lucky coins in a row。

 otherwise we just don't count it at all。But obviously another way you could succeed is maybe。

 you know， okay， maybe once。You pick the wrong variable and you go backward。

 You increase the distance between your current assignment and a star。

 But then you make up for it by K plus one times。 you pick the right variable。 Okay。

 so that would still be a net movement of K agreement toward a star。 So again。

 you would have a satisfying assignment。So that's just what we're going to do。

 we're going to also count the ways where you know you make some mistakes。

 but you compensate by making a correspondingly larger number of correct decisions that turns out to give you a better bound okay。

All right。So how do we analyze this。 So in iteration now。Now succeeds。With probability。

So what we're going to do is we're going to take this exact same expression。Okay。

 so remember what this was， this was condition on k， the distance between a0 and a star。

 and this was a lower bound on the success probability。

 so we're just going to plug in a different lower bound on the success probability now okay。

And again， conditioned non K。So again， we have cake equal with zero to n。

And choose k2 to the minus n， that's the probability of the initial distance really is k。Okay。

 so now before we said we're only going to count it if you just make k correct decisions in a row。

So now we're only going to count it if in the first 3k decisions you make exactly 2k correct decisions and k incorrect decisions so again。

 don't forget what's sort of driving all of this， we're tracking the hamming distance。

 the number of different variables between a and a star， we pick a violated clause。

 at least one in three probability， they get closer by one where that most two and three probability。

 they get farther by one but one of those will happen okay they they'll get closer if you pick a variable where they make different assignments or they'll get farther。

 if you pick a variable where they were making the same assignment okay。

So if you make k incorrect decisions， increasing the distance by K。

 but you make 2 k correct decisions， decreasing the distance by 2 k overall that gives you a net decrease of K。

 So again， either you find a satisfying assignment along the way or after you've made those K incorrect decisions and 2 K correct decisions。

 you've decreased the distance from a start to 0。 So that's definitely satisfying。Okay。So up there。

 we looked at the probability that you just make k correct decisions in a row。

 here we have 2 k correct and K incorrect。So what's the probability of that is again。

 accounting argument， so we're thinking about the first 3K decisions that the algorithm makes。

We're only going to think about the case where exactly k are incorrect and2 k are correct。So again。

 3K choose k。This is sort of the choice of the subset of decisions where you chose the wrong variable。

And now it should be the case that you know， in all the cases where you make choosing the wrong variable。

Indeed， you choose the wrong variable， and remember that's the probability two/3s at most。

And then for the other 2K choices were you supposed to be decreasing the distance？

You need to see a one third。2 K times。Okay。So this is just of your first 3 k decisions。

 this is just the probability that exactly k of them are wrong and 2 k are correct。All right。Good。So。

I don't know what you think of this， this probably now is really starting to look like a mess。

The good news is。This binomial coefficient we' be able to deal with with the same trick as before。

 But now we've got another binomial coefficient， which is sort of annoying。 okay But you know。

 whenever you have binomal coefficients and you kind of want to you know massage them in other things。

 you often want to expand them in terms of factorials and then you Sterling's approximation on the factorials。

 Let me just remind you quickly Sterling's approximation。 Again， this is one of those things。

 the only thing that's important for you to remember is that there is a really nice approximation of the factorial function。

 You can always look at up on Wikipedia。 just remember that it's something like this exists。

So it's called Sterling's approximation。And what is it。

 it says that n factorial is up to a constant factor equal to square root of n times n over e to the n。

Okay。So the fact it's often it's obviously a most end to the end because each of the products here is at most n。

 and of course it's going to be a little bit less because most of those numbers are less than n。

 And so this is how much less。 you divide n by E， but it's still raised to the end power times of root n。

The constant here is like root 2 pi， but it doesn't matter for us。All right。All right。

 so why did we introduce drillings approximation， we don't like this binal coefficient 3K， choose k。

So let's get a better handle on that。So 3K choose K， well what is that， that's 3k factorial。

Over 2 k factorial， K factorial。So using Sterling's approximation。Right up to constants。

 let's just say theta。We have a root 3k here， root 2K here， root k here。Up here we have a 3 k over E。

To the 3K down here， we have a 2K over E。To the 2 k times k over e to the K。Okay。Now。

 obviously I wouldn't have done this unless there were going to be some serious simplifications。So。

Okay， so equals。So this basically winds up being up to constant factors of one over root k。Okay。

So let's look over here， let's look at these things。Okay。Let's start say with the ease。

 or' always annoying ease's in the denominator。But how many one overes do we have in the top through the K？

How many， what power of one over do we have in the bottom， Well。

 we have a1 over to the 2 K and then also one over to the K。

 So that gives us one over to the 3 K on the bottom。So the eases go away。 Okay， And again， this is。

 you sort to get used to this once you've sort of done these kinds of calculations。 you know。

 it's annoying in the stirerlings。 But then it cancels out in the。Bomal coefficients。

 same thing for the Ks。 Okay， so ignore the three and the two。 ignore the coefficients。

 Just look at the K。We have a K to the 3 K on top。 We have both a k to the 2 K and a K to the K on the bottom。

 So those factors of K are going to cancel as well。What's left。

 the powers of three and the powers of  two Okay so we have a 3 to the 3K on top。

 we have a two to the 2K on bottom。Okay。So that's the simplification we get。

 So we're going to plug this in for the binomial coefficient。Okay。And actually， let's do it this way。

 right， So let's actually now just sort of throw in the two thirds to the K and the one third to the2 K。

Okay。So。Let's just write。Some constant C， that's what was in the theta。

 And now let's also take care of the other terms that depend on K。 So two thirds to the K。

One third to the 2K。So now they get even more cancellations， right？We have a three to the 3K here。

 we have a  three to the K there， a3 to the 2K there， so all the threes cancel out。

We have a two to the 2 K here， we have a two to the K here， so we're left with one over two to the K。

So c times1 over root k times 2 to the minus k。So that's our estimate for 3 k choose k times23 of the K times 1/3 to the。

Yeah。All right。So let me just sort of rewrite that and say， let's just go on， let's just do it here。

Don't need sterling anymore。That served its purpose。

So this is the most constant times sum over k equals 0 to the n。N choose K2 to the minus n。

 the same stuff we had before。 Now I'm plugging in our estimate for this。 So there's the constants。

 there's the one over root K， and then there's。I is right， Yeah， two to the minus k。Okay。

So this is our lower bound of the success probability。So let's start with a square root。 Okay。

 we want a lower bound。 So let's just assume that this is always its biggest value。 Okay。

 so let's just replace this by a one over a root n。Okay， so constants。Overroot in。

 that only gives us a smaller number， we're dividing by more。So now。Oh yeah。

 and let's take the two to the minus n out too。Okay， if that doesn't depend on k。

 so let's move that out front。And now we're just left with sum over k equals zero to the n and choose k times 2 to the minus k。

And now this we can recognize again as a binomal expansion just as before。

This is now one plus one half。To the end。Right。So again， think about deleting this stuff。

We pulled that stuff out， looking at this thing， if you expand one plus1 half raised to the end。

 this is exactly what you get binomial expansion。All right， so what do we have here？Theta， well。

 so this is a three/ halfs to the n。That's a two to the minus so that gives us three fourth to the n。

 So theta of root n， sorry， one of a root n。Three fourths to。So this is our new P。

we had a P at one point， which was one over root  three raised to the n。

 then we had a P which was two thirds to the n， now we have a P which is three quarters to the n。

 and I can remember our running time is basically the reciprocal of this。So now t equals theta。

4our thirds。To the N。Times root in， times login。Is enough。Okay。

So a brute forest search gets you two to the end。Random search gets you four thirds to the end。

 There are some minor improvements on this known， but I've actually gotten you pretty close to the state of the art for worst case running time bounds of exact algorithms for three set。

So any final questions？All right， see you Thursday for the last lecture。

