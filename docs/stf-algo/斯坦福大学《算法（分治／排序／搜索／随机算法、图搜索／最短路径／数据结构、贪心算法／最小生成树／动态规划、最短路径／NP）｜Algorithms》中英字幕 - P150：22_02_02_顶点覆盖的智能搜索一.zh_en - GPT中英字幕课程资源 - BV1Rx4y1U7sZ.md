# 斯坦福大学《算法（分治／排序／搜索／随机算法、图搜索／最短路径／数据结构、贪心算法／最小生成树／动态规划、最短路径／NP）｜Algorithms》中英字幕 - P150：22_02_02_顶点覆盖的智能搜索一.zh_en - GPT中英字幕课程资源 - BV1Rx4y1U7sZ

The goal of this video is to develop an exact algorithm for solving the vertex cover problem。

 the algorithm will run an exponential time in the worst case in general instances。

 but is nevertheless qualitatively better than naive brute force search。



![](img/6e0fbafd4ff673490956dcd399e5e531_1.png)

One consequence of this smarter search algorithm is that the vertex cover problem is computationally tractable in this special case where you're looking for a small optimal solution that uses it most a logarithmic number of vertices。

Let me remind you quickly of the vertex cover problem。 The input is simply an undirected graph G。

A vertex cover of a graph is a subset of vertices that includes at least one endpoint of each edge of the graph。

The goal on the vertex cover problem is to compute the smallest size of a vertex cover。

Let's consider a variant on this problem where we're additionally given a target value K K here is going to be a positive integer。

 and we want to know whether or not there is a vertex cover with size K or smaller。Now， as stated。

 I haven't really made the problem any easier。 If you could solve this version of the problem where you're given a target K。

 you could also solve the original one where you want to know the smallest value of any vertex cover。

 namely， just run this subroutine for all possible values of K from one up to N。

 and the smallest value of K for which you can find a vertex cover is then the answer to the original optimization version of the problem。

 Rather to make the problem easier， I want to think about the special case where K is small。

So for now I'm going to be deliberately vague about what I mean by small。

 we'll fill in those details in due time。Now why might you be interested in the vertex cover problem when K is small Well we talked。

 for example one thing you might be modeling is hiring a team。

 each vertex corresponds to a potential team member， someone capable of performing various tasks。

 a vertex cover means you hire a team that is capable of handling any task that might be thrown your way where the edges of the graph correspond to tasks and the endpoints correspond to the two people capable of performing the task and you can imagine maybe you're only interested in forming a team if it has reasonable size so you have a budget for how many people you could hire and then you're only interested in solving the vertex cover problem when there's a good solution。

 a small cardinality vertex cover， otherwise you just punt and you're not willing to take on the project。

You could also imagine maybe you have some domain expertise that suggests that your graphs do have small vertex covers。

 recallca a star is just a vertex cover of size 1。 So if you know that your graph is star like in some sense。

 you might expect that there's an optimal solution that has few vertices。

Is it useful algorithmically to focus on the case of K small， Well， yeah， sure。

 If you're looking for a small optimal solution， then brute force search isn't as bad as usual。

 If you want to know whether or not there's a vertex cover comprising only k vertices。

 you can just check every subset of K vertices。The number of subsets of k vertices。

 assuming that there are n to start with would be n choose K， and for small K。

 that's going to be like theta of n to the K。So in principle。

 this naive brute for search runs in polynomial time as long as K is constant。

 as long as K is big O of1。 But practically speaking， I mean。

 you can't really imagine running this naive brute force search algorithm unless K was super small。

 You know， say K equal3， maybe K equal to 4， depending on the size of your graph。In any case。

 this naive search is limited to very small values of K， and it's then natural to ask。

 as we always do， can we do better， Is there a smarter type of search。So the answer is yes。

 there is a smarter way to go about this search that's going to allow us to solve the problem for qualitatively larger values of K。

The search algorithm is going to be driven by a lemma。

 which is similar in spirit to the kind of reasoning we did about optimal solutions in our dynamic programming algorithms。

 I think it would be a little misleading to call it an optimal substructure lemma。

 So let me just call it a substructure lemma。So consider some input。

 so our the job of our algorithm is to check whether some undirected graph G has a vertex cover of size K or not。

 consider also some edge， let's say between U and V of this graph。

In the same way in all of our dynamic programming， optimal substructure lemas。

 we thought about taking the original instance and reducing it by one in some sense。

 removing an item， removing a vertex， removing a position of the alignment， and so on。

 we're going to be thinking about this graph G， but with one fewer vertex。

 actually two different graphs of that form， One that we get by theleting U。

 That's one endpoint of the edge that we chose。 And in addition to you all of the edges incident to it。

 And we'll also look at the graph that we get by theleting V。

 the other endpoint of the edge and all of its incident edges。

I'll use the notation GU for the graph we get by deleting U and G sub V for the graph we get by deleting V。

The lemma asserts that we can reduce the question that we care about。

 namely does or does not G have a vertex cover of size K。

 two analogous questions on the smaller graphs G and GV。

 specifically G does have a vertex cover of size K。

 if and only if at least one of GU or GV has a vertex cover of size K minus1。

So the proof is not too hard， I'll be able to squeeze it in on this slide。

 and then once we know the substructurelemma is true。

 I'll show you how that leads to a smarter search algorithm for vertex cover。

So this is an if and only if statement， so we have to have two different parts of the proof assuming the left prove the right。

 assuming the right proof of the left， let's start by assuming the right hand side。

 let's assume that G or GV or both does in fact have a vertex cover of size K minus-1。

 Let's show that then G must have a vertex cover of size K as well。



![](img/6e0fbafd4ff673490956dcd399e5e531_3.png)

It doesn't matter which of G U or G V has the good vertex cover。 Let's just say G U。

So let's think for a second about which edges of the original input graph G survive into the smaller graph G U。

 For the purpose of this proof， there's basically two types of edges in the world。

 There's ones where one of the endpoints is U that is edges incident to U。

 And then there's edges where neither endpoint is the vertex U。

 So the edges in the graph G U are precisely those where neither of the two endpoints is U。

 So let's call those edges E subu。 Those are edges not incident to U。 the edges in G subu。

 and then we'll call the edges incident to U that got deleted F subu。

So let's call this set of K -1 vertices That's a vertex cover in G sub。 Let's call it capital S。

 What does it mean to be a vertex cover， It means you include at least one endpoint of every edge。

 So S by virtue of being a vertex cover for G sub。 It means for every edge of E sub。

 that is every edge of the original graph。 Neither of whose endpoints is U。

 S contains at least one of the endpoints。 So if we think about capital S in the original graph capital G。

 the only edges that it's missing。 are those of F sub are those where one of the two endpoints was the vertex U。

 Well， that means if we just take capital S， and we throw in the vertex U。

 we get a bona fide vertex cover of the original graph capital G。

 S takes care of all of the edges of E sub u by definition。

 and then U single handededly takes care of all of the edges in F sub because all of those edges are incident to U。

So that's why if we assume the right hand side， we can conclude the left。 If either G or G V。

 let's say G has a small vertex cover size of K -1。

 all we need to do is augmented by the missing vertex U and boom。

 we get a vertex cover of the desired size K back in the original graph G。

 So what about the other direction of the substructure lemma。

 Now now we assume that the original graph G does， in fact， have a vertex cover of size only K。

 and we show that has to be reflected one of these two subgraphs。

 Either G or Gv must itself have a small vertex cover， size only K -1。

Let's let capital S denote this small vertex cover of the original graph G， so S has K vertices。

 and every edge has at least one of its endpoints represented among this set。In particular。

 the E U V that we singled out at the beginning， one of its endpoints， either U or V maybe both。

 but certainly one of them has to be in the set capital S。 Let's say U is in S。

So let's think about the pink picture from the other direction of the proof。

 Let's think about exactly the same decomposition of the original edge set capital E into two sets。

Now， this set S。 remember， it's a vertex cover of the original graph G。

 So S contains at least one endpoint of every edge。 But now U， which is one of the vertices in S。

 Sure， it is an endpoint of every edge of F subbu， Every edge incident to U。

 but U is not an endpoint of any of the edges in E subbu。

So what that means is the other K -1 vertices of S have to be responsible for containing endpoints of all of the edges that survive into G sub。

 The vertex U takes care of edges In to it。 S with U removed those K -1 vertices included an endpoint from all of the other edges。

 All of the edges in E sub。So that completes the proof of the forward direction and therefore of the substructure lemma。

