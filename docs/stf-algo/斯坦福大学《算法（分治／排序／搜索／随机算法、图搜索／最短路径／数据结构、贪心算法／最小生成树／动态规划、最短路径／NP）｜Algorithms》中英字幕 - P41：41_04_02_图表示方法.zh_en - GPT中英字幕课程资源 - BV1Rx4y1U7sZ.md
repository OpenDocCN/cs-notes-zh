# 斯坦福大学《算法（分治／排序／搜索／随机算法、图搜索／最短路径／数据结构、贪心算法／最小生成树／动态规划、最短路径／NP）｜Algorithms》中英字幕 - P41：41_04_02_图表示方法.zh_en - GPT中英字幕课程资源 - BV1Rx4y1U7sZ

Okay， so this video is not about any particular graph problem。

 not about any particular graph algorithm， just sort of the preliminaries we need to discuss algorithms on graphs。

 How do we measure their size， how do we represent them and so on。 Remember what a graph is。

 it really has two ingredients。 First of all， there's the set of objects we're talking about。

 those might be called vertices synonymously we might call them nodes。

 we represent pairwise relationships using edges， these can be either undirected。

 in which case they're ordered pairs or an edge can be directed from one to another。

 in that case they're ordered pairs and we have a directed graph Now， when we talk about。

 say the size of a graph or the running time of an algorithm that operates on a graph。

 We need to think about what we mean by input size In particular。

 for a graph is's really two different parameters that control how big it is Unlike an array for arrays we just had a single number of the length for graphs。

 we have the number of vertices。 and we have the number of edges。

 Usually we'll use the notation N for the number of vertices M for the number of edges。

 So the next quiz asks you to think about how the number of edges M。

Can depend on the number of vertices N。 So in particular。

 I want you to think for this quiz about an undirected graph。 it has n vertices。

 There's no parallel edges so for a given pair of vertices there's either zero or one edge between them Moreoverover。

 let's assume that the graph is unconnected so I don't want you to think about graphs that have zero edges Now I haven't defined what a graph is what it means for a graph to be connected formally yet。

 but I hope you get the idea it means it's in one piece you can't break it into two parts that have no edges crossing between them。

 So for such a graph， no parallel edges in one piece n vertices。

 think about what is the minimum number of edges， it could possibly have。

And what is the maximum number of edges as a function of n that I could possibly have？

Al right so the correct option is the first one。 The fewest number of edges that a connected undirected graph can have is n -1 and the maximum number of edges that an undirected graph with no parallel edges can have is n times n-1 over two better known as n choose 2。

 So why does it need at least n-1 edges if it's going to be in one piece。 Well。

 think about adding the edges one at a time at each of the edges of the graph。

 Now initially you just have a graph with zero edges。

 the graph has n different pieces and isolated vertices and there's no edges at all。 Now。

 each time you add one edge。 what you do is you take two of the existing pieces at best and fuse them into one。

 So the maximum decrease you can have and the number of different pieces of a graph is it can decrease by one each time you add an edge。

 So from a starting point of n different pieces， you got to get down to one piece。

 So that requires the addition of n-1 edges。 you can also convince yourself of this by drawing a few pictures and noticing the trees achieve this bound exactly。

 So for example， here is4。text tree that has three edges so this is a case where M is indeed n minus1 Now for the upper bound why can't you have more than n choose 2 Well it's clear that the largest number of edges you can have is for the complete graph or every single pair of edges has one between them again there's no parallel arcs and edges are unordered so there's at most n choose2 possibilities of where to put an edge so again if n equals 4 here would be an example with a maximum possible number six edges。



![](img/193f3ccf2d279fe2c53bd117c6d88d65_1.png)

So now that I've got you thinking about how the number of edges can vary with the number of vertices。

 let me talk about the distinction between sparse and dense graphs。

 it's important to distinguish between these two concepts because some data structures and algorithms are better suited for sparse graphs。

 other data structures and algorithms are better suited for dense graphs。So to make this precise。

 let me just。Put down this very common notation。

![](img/193f3ccf2d279fe2c53bd117c6d88d65_3.png)

N is the number of vertices of the graph under discussion。 M is the number of edges。

This is quite standard notation， please get used to it and use it yourself if you reverse these。

 you will confuse a lot of people who have familiarity with graph algorithms and data structures。Now。

 one thing we learned from the previous quiz is the following。So in most applications。

 not all applications， but most applications。M is at least linear in n。

 remember in the qui or saw is at least n minus1 if you wanted the graph to be connected。

 and it's also big O of n squared。This is under the assumption that there's no parallel arcs。

 Now there are cases where we want to allow parallel arcs， in fact。

 we'll do that in the contraction algorithm for the Min cut problem。

 there are cases where we want to allow the number of edges to drop so low that the graph breaks in the multiple pieces。

 for example， when we talk about connected components。

 but more often than not we're thinking about a connected graph with no parallel edges。

 and then we can pin down the number of edges M to be somewhere between linear in the number of nodes。

 linear and n and quadratic in it。Now I'm not going to give you a super formal definition of what a sparse or a dense graph is。

 and people are a little loose with this terminology in practice。

 but basically sparse means you're closer to the lower bound， closer to linear。

 dense means you're closer to the upper bound， closer to quadratic。

Now I know this leaves ambiguity when the number of edges is something you like n to the three/hals。

 usually in that case you'd think of it as a dense graph。

 so usually anything which is more than n times some logarithmic terms you'd think of about as a dense graph。

 but again， people are a little bit sloppy with this when they talk about graphs。Next。

 I want to discuss two representations of graphs， and we're mostly going to be using the second one in this course。

 but this first one， the adjacency matrix I do want to mention just briefly just on this slide。

 This is a supernatural idea where you represent the edges in a graph using a matrix。



![](img/193f3ccf2d279fe2c53bd117c6d88d65_5.png)

Let me describe it first for undirected graphs。So the matrix is going to be denoted by capital A and it's a square n by n matrix where n is the number of vertices of the graph。

 and the semantics are the Ijath entry of the matrix is1。

 if and only if there's an edge between the vertices， I and J in the graph。

 I'm assuming here that the vertices are named 1，2，3，4， etc ce， all the way up to n。

It's easy to add bells and whistles to the adjacency matrix to accommodate parallel edges to accommodate edge weights。

 which is accommodate directed edges。If you wanted to have parallel arcs。

 you could just have AIJ to know the number of arcs that are between I and J。

If edges have different weights， you can just have AI J be the weights of the I J edge。

And for the directed graph you can use plus ones and minus ones。

 So if the arc is directed from I to J you'd set AI J to be plus1。

 if the arc is directed from J to I you'd set AI J to minus-1。

 There are many metrics by which you can evaluate a data structure or a representation to important ones I want to discuss here。

 first of all the number of resources it requires and in this context。

 that's the amount of space that the data structure needs。

 The second thing is what are the operations that the data structure supports So let's just begin with the space requirements。

 what are they for the adjacency matrix。

![](img/193f3ccf2d279fe2c53bd117c6d88d65_7.png)

Alright， so the answer， at least with the sort of straightforward way of storing a matrix is n squared。

 and this is independent of the number of edges。 So you could try to beat this down for sparse graphs using sparse matrix tricks。

 but for the basic idea of just actually representing an n by n matrix， you got n squared entries。

 you got to store one bit in each whether the edges there or not。

 so that's going to give you n squared space。 the constants are of course。

 very small because you're just storing one bit per entry， but nonetheless。

 this is quadratic in the number of vertices。 Now that's going to be fine if you have a dense graph。

 if the number of edges is as high as n squared， then you're not really wasting anything in this representation。

 but in a sparse graph if M is much closer to linear， then this is a super wasteful representation。



![](img/193f3ccf2d279fe2c53bd117c6d88d65_9.png)

Let's talk about the adjacency list representation。

 this is the dominant one we'll be using in this class， this has several ingredients。So first。

 you keep track of both the vertices and the edges as independent entities。

 so you're going to have an array or a list of each。

And then we want these two arrays to cross reference each other in the obvious way。

 so given a vertex you want to know which edges it's involved in。

 given an edge you want to know what its endpoints are。So let's say first， most simply。

 each edge is going to have two pointers， one for each of the two end pointss， and a directed graph。

 of course， it would keep track of which one is the head and which one is the tail。

Now each vertex is going to point to all of the edges of which it's a member Now in an undered graph。

 it's clear what I mean by that in a directed graph you can do it in a couple ways。

 generally you'd have a vertex key track of all of the edges for which it is the tail that is all of the edges which you can follow one hop out from the edge if you wanted to you can also have a second array more expensive storage where the vertex also keeps track of the edges pointing to it。

 the edges for which it's the head。So let me ask you the same question I did with an adjacency matrix。

 what is the space require of an adjacency list as a function of the number of edges M and the number of vertices n of the graph？



![](img/193f3ccf2d279fe2c53bd117c6d88d65_11.png)

So the correct answer to this question is the third option theta of M plus n。

 which we're going to think of as linear space in the size of the graph。

 So this quiz is a little tricky， so to explain the answer。

 Let me return to the slide with the ingredients of adjacency lists。

 and let's compute the space for each of these four ingredients separately。

 Most of them are straightforward。 For example， consider the first ingredient。

 this is just an array or a list of the n vertices。

 and we just need constant space per vertex to keep track of its existence。

 So this is going to be theta of n linear in the number of vertices。 Similarlyly， for the M edges。

 we just need linear space in the number of edges to remember their existence。



![](img/193f3ccf2d279fe2c53bd117c6d88d65_13.png)

So that's gonna to be theta of M。 Now each edge has to keep track of both of its npoint。

 So that's two pointers， but two is a constant for each of the m edges。

 we have a constant space to keep track of n points So that's going to give us another theta of M constant per edge Now this fourth case。

 you might be feeling kind of nervous because a vertex in principle could have edges involving all n minus one of vertices。

 So the number of pointers at a single vertex could be theta of n。

 Also you could have you know you do have n vertices。

 so that could be theta of n squared and certainly in something like a complete graph。

 you really would have that much。 but the pointers in sparse graphs n squared is way overkill to the space needed by this fourth set of pointers。

 actually if you think about it for each pointer in the fourth category。

 a vertex pointing to a given edge there is a pointer in the third category pointing in the opposite direction from that edge back to that vertex So this。

A one to one correspondence between pointers in the third category and pointers in the fourth category。

 since the third category has space theta of M， so does all of the pointers in the fourth category。

So adding up over the four ingredients， we have one theta of n and three theta of Ms。

 so that's going to give us overall a theta of M plus n。

 If you prefer another way you could think about this would be theta of the max of M and N。

These are the same up to a constant factor。Now， as we discussed in a previous slide。

 often M is going to be bigger than n， but I wanted to do a generic analysis here。

 which applies even if the graph is not connected， even if it is in multiple pieces。

 so the space of the agencyency list is within a constant factor the same as the number of ingredients in the graph。

 the number of vertices plus the number of edges， so in that sense that's exactly what you want。

Now being confronted with these two graph representations that I've shown you。

 I'm sure you're asking， well， which one should you remember， which one should you use？



![](img/193f3ccf2d279fe2c53bd117c6d88d65_15.png)

And the answer as it so often is， is it depends， it depends on two things。

 it depends on the density of your graph， it depends on how n compares to n。

 and it also depends on what kind of operations that you support， want to support。Now。

 given what we're covering in this class and also the motivating applications I have in mind。

 I can give you basically a clean answer to this question for the purposes of these five weeks。

Which is we're going to be focusing on adjacency lists。

The reason we're going focus on adjacency lists in this class is both is for both of these reasons。

 both because of the operations we want and both because of the graph density and motivating applications。

 So first of all， most of the graph primitives not all but most will be dealing with graph search and adjacency lists are perfect for doing graph search you get to a node you follow an outgoing arc you go to another node you follow an outgoing arc and so on and so adjacency lists are the perfect thing to do graph search adjacency matrices are definitely good for a certain kinds of graph operations but they're not things we're really going to be covering in this class。

 So that's reason one reason two is a lot of the motivations for graph primitives these days comes from massive massive networks I mentioned earlier how the web can be fruitfully thought of as a directed graph where the vertices are individual web pages and directed arcs correspond the hyperlinks going from the page with the hyperlink pointing to the one that the hyperlink goes to Now it's hard to get an exact measurement of the web graph but a conservative lower。

Bund on the number of vertices is something like 10 billion。 So that's 10 to the 10。

 Now that's pushing the limits of what computers can do， but it's within the limits。

 So if you work hard， you can actually operate on graphs with 10 to the 10 nodes。

 Now supposed to use in adjacency matrix representation。 So if n is 10 to the 10。

 then n squared is going to be like 10 to the 20。 and now we're getting close to the estimated number of atoms in the known universe。

 So that is clearly not feasible now and it's not going to be feasible ever。

 So the adjacency matrix representation is totally out for huge sparse graphs like the web graph adjacency lists。

 well， the degree on average in the web is thought to be something like 10。

 So the number of edges is only going be something like 10 to the 11 and then the adjacency list representation will be proportional to that。

 And again， that's really pushing what we can do with current technology。

 but it is within the limits。 So using that representation。

 we can do nontrivial computations on graph。Even at the scale of the web graph。

