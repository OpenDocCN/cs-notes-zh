# 斯坦福大学《算法启蒙（第3册）：贪心算法和动态规划｜Part 3 Greedy Algorithms and Dynamic Programming》中英字幕 - P47：-47-ALL-PAIRS SHORTEST PATHS_ The Floyd Warshall Algorithm.zh_en - GPT中英字幕课程资源 - BV1fNVUznEtT

So now let's compile the optimal substructure we just identified in all pair shortest pass into a dynamic programming algorithm。

 and this will be the Floyd Warsshall algorithm。 Let me begin with a quiz and ask you to sort out the base cases。



![](img/51339d65e5bb5ab30430154cb431211b_1.png)

So remember our sub problemsblem actually have three indices。 The first index is the origin I。

 the second index is the destination J， and then there's our budget K。

 which controls which of the vertices we' permitted to use as internal nodes in a shortest path in this subproble。

 So because of these three indices we're going to be using a three dimensionmenal array A。

So the plan of course， is to solve systematically all of these subproblems where the subprom corresponding to a choice of IJ and K is just the length of a shortest path starting at I ending at J and using intermediate nodes only labeled1 through K。

And what's cool about these definitions is it's clear which are the bigger sub problemss and which are the sub smaller subproble that's controlled completely by the index K。

 So the smallest set of subpros， the ones that we have to think through the base case is when K equals0。

 so the quiz asks you how should we fill in AI J0 for all of the various choices of the origin I in the destination J？

And as usual， if there are no feasible solutions， if no paths from I J J make use only of internal nodes 1 through K。

 then we define this to be plus infinity。So the correct answer is she。So if I and J are the same。

 then there is a path that starts at I in ends A J， the empty path， it does。

 in fact have no internal nodes at all， and it has length 0。Similarly。

 if I and J are directly connected and we look only at paths that have no internal nodes whatsoever。

 well then we're stuck with the cost of whatever the direct edge from I to J is。

 so we just fill it in with CJ。 On the other hand， if I is not equal to J and I and J are not directly connected。

 then every path from I to J has at least one internal node。

 so there are no path from I to J without any internal nodes， in that case， by definition。

 we assign a value of plus infinity。So having figured out the base cases it's now a simple matter to write out the fullblown Fyd Warhall algorithm in the past I've been writing down a recurrence as an intermediate step。

 I think I'm going skip that step here， we have so much practice with it。

 I think we can just jump straight to the code and in the code we will solve the problem systematically from the smaller values of K to the bigger values of K and each time we solve a subproblem we're just going to do brute force search amongst the two possibilities that we identified in the optimal substructure lemma。

So we have our three dimensional array A and it's three dimensional because we have three indices for our subproms。

 we got to know what the origin is， we got to know what the destination J is。

 and we got to know how big a prefix K of vertices we have to work with for internal nodes in our paths。

The base case is when cake was0。 So we just fill that in in a pre processingces step。

 according to the quiz we just solved。And now we have our triple 4 loop，1，4 loop。

 for each of the indices。 Now， as always， it's important we solve the smallest sub problems First。

 the subprom size is controlled by K， So we better put K as the outermost4 loop。

 The order of I and J is irrelevant， but K better go first。

So to compute the value of a given subproblem A I JK。

 we just take the better That is the minimum of the two candidates identified in our optimal substructure lemma。

 The first candidate furnished by case1 is just to inherit the solution computed in the last iteration of the outer for loop that is IJK -1。

So the second candidate is provided by the second case of the optimal substructure lelemma。

 this is where in the optimal solution to the current subproblem we actually do use node K internally on the shortest path in that case we know what it has to look like。

 we have to just be taking the optimal solution from the last iteration of the outer for loop from I to K and concatetnating that that is adding to it the length of a shortest path computed last iteration of the outer for loop from K to J。

So notice that our code does indeed pass the sanity check you should always use when we evaluate a subproblem。

 we already have the solutions to all of the relevant subproble available for constant time lookup。

 That's because all of them were computed in the last iteration of the outer for loop。

 There's also not a whole lot to say about the correctness or the running time correctness it's the usual story。

 the only non-trial work is in the optimal substructure lemma that identifies the only possible two candidates for the optimal solution to a subproblem or systematically solving all of them taking the better of the two only possible candidates。

 As far as the running time。 Well， how many subproblems are there pretty easy to see each of our three four loops takes on n different values。

 So that's in cubed subprom overall， pretty clear that we only do a constant amount of work per subproblem that's gives us the cubic running time。

So let me wrap up the discussion of Floyd Warshaaw algorithm with a couple odds and ends。

 answers to two frequently asked questions。So question number one， which frankly。

 I kind of hope you're wondering about is， well， what's up with input graphs that do have a negative cost cycle。

 Let's recap what we've done。 We stated and proved the optimal substructure lemma only for input graphs that do not have a negative cost cycle。

 Our correctness argument for the Floyd Warshall algorithm relied on the correctness of the recurrence。

 which in turn relies on the correctness of the optimal substructure lemma。

 So if you feed in some arbitrary graph to the Floyd Warshall algorithm。

 It might have a negative cost cycle， it might not。

 while the algorithm is just going to process its N cube iterations and fill in this three dimensional array either way。

 So you're left at the end of the day with this 3D array filled with numbers。

 And if it just so happened， there was no negative cost cycle in the input graph。

 then you know that the final batch of numbers when K equals in are， in fact。

 the correct shortest past distances。 But how do you know if the input graph had a negative cycle or not。

 how do you know whether you can trust this last batch of numbers when K equals in。

Well there's actually a very slick answer to this question。

 which is all you need to do is scan the diagonal of the numbers computed in the final round。

 if the input graph does have a negative cost cycle， then for at least one vertex I。

 you will see a negative number in the entry A of I comma I comma n。

So let's assume for the moment that this fact is true that negative cost cycles will show up in the diagonal in the final round of entries。

 Then I hope it's clear how you can use the Floyd Warsshaw algorithm to solve the general version of the all pairs shortest pass problem whereby the general version I mean you're given an input graph。

 it may or may not have a negative cost cycle and you have to do one of two things。

 either you correctly deduce that the input graph has a negative cost cycle。

 then you're off the hook or you compute correct shortest path between all pairs of vertices So the way you use that using Floyd Warsshaw。

 you just take the input graph， you just run the algorithm， the N cube iterations。

 you scan the diagonal， you scan AIIN for all values of I if you see a negative number。

 you say I'm off the hook， there's a negative cost cycle， sorry and if the diagonal is all zeros。

 then you return the final batch of AIjNs as the correct shortest path distances。

I'm not going to prove this formally。 I'll leave that for you to do in the privacy of your own home。

 but let me just suggest some intuition about why you would expect this to be true。

So suppose the input graph does indeed have a negative cost cycle。

 Pick some arbitrary vertex on that cycle。 let's say vertex X Def vertex Y to be the highest label of some other vertex on the cycle。

 Now， think about the following point in the Fyd Warshaaw algorithm and a triple4 loop。

 Think about when the outereration， the value of K is equal to Y。

 So for the first time the vertex Y is eligible to be on internal nodes of shortest paths。

And think about in the inner four loops when both I and J are equal to X。 So what is the recurrence。

 what is the formula in the Four Warsaw argument going to say。

 it's going to fill in this particular subproblem value。

 That is capital A of x comma x comma Y with the minimum of two things。 So first of all。

 capital A of x comma x comma y minus1 who knows what that is but the second candidate。

 this is the interesting one， one candidate to fill in this entry will be capital A of x comma y comma y minus1 plus capital A of y comma x comma y minus1。

 That is one of the candidates for the entry in this diagonal capital A of x comma x comma y will be the length of a shortest path from x to y whose's all internal nodes are less than y plus the length of a shortest path from y back to x whose internal nodes are all less than y Well two candidates for such paths are the two hs of this cycle Y we chose to be the largest indexed node anywhere on the cycle。

All the other vertices other than x and y have only smaller indices so there are permissible internal nodes at the previous iteration so if you take the sum of these two pass that's just the cycle length which by assumption is negative so at this point in the th Warshall algorithm if not earlier when the outer four loop k is equal to y and when we're looking from x back to X itself at that point will' get a negative number and because these numbers only go down in future iterations of the outer four loop that negative number will persist to the end of the algorithm that's why to check for negative cycle just scan the diagonal of the final batch of numbers that tells you whether or not there was one in the input graph。

So the second frequently asked question concerns reconstruction。

 Suppose after you run Floyd Warsshaw， you actually want to know the actual sequence of edges that's the shortest path from some your favorite origin I and your favorite destination J。



![](img/51339d65e5bb5ab30430154cb431211b_3.png)

So like in the Belman Ford reconstructionion solution。

 we're going to have to store a little bit of extra information。

 a constant amount of information per subproble Now in the Belman Ford algorithm。

 we only had one subproblem per choice of destination。

 the source was fixed and for each choice of destination。

 we remembered the penultimate vertex on a shortest path to that destination。 So for Floyd Warshaw。

 the number of subproblems is indexed by origins and destinations。

 And so for each choice of an origin and destination。

 we're again going to remember some other vertex on a shortest path。

 but the vertex we remember might not be the second to last one it might not be the last hop rather what we're going to remember is the highest index vertex on a shortest path from I to J。

So I'm gonna call this additional information a twodiional array capital B。

 This is indexed just by the choice of the origin and the choice of the destination。 And again。

 the semantics is we want the Ij entry of this array to be the max label of any internal node on a shortest Ij path。

 So two things we have to understand。 So first of all。

 how do we compute all of these Bj values on the forward path of the forward War algorithm without affecting its running time。

 Secondly， if we successfully compute all of these Bjs on the forward path。

 how do we reconstruct shortest paths by going backward through the filled in table。

 So this is all analogous to Belmand Ford and Belelmand Ford， we showed that on the forward paths。

 you could maintain the predecessor pointers， it wasn't a big deal。

 just when you fill in when you recompute shortest paths and a given round of subproblem。

 if you compute some new shortest path value， i。e。 you don't just inherit that solution from the previous round。

 you just figure out which vertex was responsible for it and you remember that as your predecessor。

 And then given the predecessor pointers are correctly computed。

 you just trace back pointers to reconstruct shortest paths。 So here， how do you compute them on the。

Forward direction。Well， remember in the recurrence that we used to fill in the threedial array A。

 there's two possibilities， either you just inherit the solution from the previous iteration。

 that's kind of the boring case and the interesting case is when you actually use the newly available vertex K in a shortest path from I to J。

 So whenever you use that second case of the recurrence to reset the value in the three dimensionmensal array A at that point you reset the corresponding Bj value to the current value of K。

 so that is just in the forward path of forward Warsaw。

 you always remember the last vertex responsible for changing your shortest path distance between I andJ。

So now let's suppose you've coded up this extension of the forward paths of Floyd Wasll correctly so that at the end of your triple4 loop。

 you have accurate computations of all of these Bj values。 That is for any origin and destination。

 you have a little birdie。 the twodial array B that will just tell you in constant time what is the max labelbeled vertex internal on a shortest IJ path。

 Well， maybe you really want to know your favorite source is 23。

 your favorite destination is 17 and you want to reconstruct a shortest path from your oracles。

 your're filled in tables。 So you look into the entry 23 comma 17 into the B array this little birdie this filled in table tells you the max labelbeled vertex on a shortest path between 23 and 17。

 Maybe it tells you it's the vertex 43 So it promises you that the shortest path comprises 23 on one end 17 on the other end a bunch of stuff in the middle。

 the largest of which is 43。 Well then you're like。

 okay cool let me just I know where the shortest path has to be It's the shortest path from 23 to 43 plus the shortest path from 43 to 17 and you just reconstruct those two shortest paths recursive。

In exactly the same way this has got to terminate because at the end of the day。

 the shortest path is going to have it most and vertices and you're figuring out one of those vertices every time you do a recursive call。

