# 斯坦福大学《算法（分治／排序／搜索／随机算法、图搜索／最短路径／数据结构、贪心算法／最小生成树／动态规划、最短路径／NP）｜Algorithms》中英字幕 - P51：07_01_10_计算强连通分量-算法.zh_en - GPT中英字幕课程资源 - BV1Rx4y1U7sZ

Having mastered computing the connected components of an undirected graph in linear time。

 let's now turn our attention to directed graphs， which also arise in all kinds of different applications。

 Now， the good news is is we'll be able to get just a blazingly fast primitive for computing connectivity information for directed graphs。

 The bad news if you want to call it that is we'll have to think a little bit harder。

 so it won't be as obvious how to do it。 but by the end of this lecture you will know linear time algorithm with very good constant。

 really just based on depth first search for computing all of the pieces of a directed graph。

 In fact， it's not even so obvious how to define pieces。

 how to define connected components in a directed graph。

 certainly not as obvious as it was with undirected graphs。So to see what I mean。

 let's consider the following four node directed graph。So on the one hand， this graph is。

 in some sense， in one piece。 if this was an actual physical object made say of a bunch of strings connected to each other and we picked it up with our hands。

 it wouldn't fall apart into two pieces it would hang together in one piece。 On the other hand。

 when you think about moving around this network， it's not connected in the sense that we might think about you cannot get from point A to any other point B。

 for example， if you start at the rightmost node in this graph。

 certainly there's no directed path that will get you to the leftmost node。

 So what's typically studied and most useful for directed graphs is which called strong connectivity and the graph is strongly connected if you can get from any one point to any other point and vice versa and the stronglyline connected components。

 then informally are the maximal portions of this graph。

 the maximal regions which are internally strongly connected。

 So the maximal regions from within which you can get from any one point A to any other point B along a directed graph。

For the record， let me go ahead and give you a formal definition。

 although this intuition is perfectly valid， just regions where you can get from anywhere to anywhere else。

So we say that the strongly connected components of directed Graph or the SCC is for short。

And as in the underdu case， we're going to give a somewhat slick definition rather than talking about maximal region satisfying some property。

 we're going to talk about the equience classes of a particular equivalence relation。

 but really it means the same thing， this is just sort of the more mathematically mature way of writing it down。

So the equivalence relation we're going to use on nodes of the graph and we'll say that U。

 a node is related to a node V， if you can get from U to V via directed path and also from V to U in some other directed path。

I'm not going to bore you with the verification that this is an equivalence relation。

 that's something you can work out in the privacy of your own home。

So remember what it means is being equivalence relation。

 it's reflexive that is everybody's related to itself。

 but of course there is a path from every node to itself。

 it also means that it's symmetric so if U is related to V and V is related to U well again by definition we're saying that the paths are mutually the verses are mutually reachable from each other so that's clearly symmetric by definition and then it has to be transitive and the way you prove it transitive is you just paste paths together and it just works the way you'd expect it to。

So let's illustrate this concretely with a somewhat more complicated directed graph。



![](img/ddf73c63104abbe99b0c13fd26f90641_1.png)

So here's a directed graph and I claim that it has exactly four strongly and connected components。

Theres a triangle on the left。

![](img/ddf73c63104abbe99b0c13fd26f90641_3.png)

A triangle on the right。It has this single node in top。

 and then it has this directed for cyclee with a diagonal at the bottom。

So what I hope is pretty clear is that each of these circled regions is indeed strongly connected that is if you start from one node in one of these circled regions you can have a directed path to any other node so that's true because on a directed cycle you can get from any one starting point to any other place and all of these have directed cycles and then there's the one strong component that just has the one node which is obviously strongly connected what I also claim is true is that all of these regions are maximal subject to being strongly connected。

 that's why the strong components that's whether the equivalence classes of this equivalence relation we just defined so if you take any two pairs of nodes which line two different circles。

 you either won't have a path from the first one to the second one or you won't have a directed path from the second one back to the first one In fact the structure of the strong components in this black graph exactly mirrors the directed acyclic graph that we started with in red so in the same way in the red for node graph you can't move from right to left here in this bigger graph you can't move from any of the circled secs to the right to any the circled SECs to the left。

For example， from the rightmost nodes， there are no directed paths to the leftmost nodes。

So that's a recap of the definition of the strongly Ktic components I've motivated in a separate video some reasons why you might care about computing strongly connected components in particular on extremely large graphs which motivates the need for blazingly fast subroutines so four free primitives that will let you compute connectivity information so you'd love to be able to just know the pieces of a directed graph maybe you don't even know why they're going to be useful but you just compute them because why not it's a for- free primitive so that's what I'm gonna to give you in this lecture。

So the algorithm we're going to present is based on depth first search and that's going to be the main reason why it's going to be so blazingly fast is because depth first search is blazingly fast。

 Now you might be wondering what on earth does graph search have to do with computing components They don't seem obviously related。

 So let's return to the same directed graph that I showed you on the previous slide。



![](img/ddf73c63104abbe99b0c13fd26f90641_5.png)

And to see why something like depth first search might conceivably have some use for computing strong components。

 suppose we call depth first search starting from this red node as a starting point。

What would it explore。 So remember what the guarantee of something like depth for search or breathth for search for that matter is you find everything that's findable。

 but naturally nothing else。 So what is findable from this red note， whereby findable。

 I means you can reach it from a directed path emanating from this red note。 Well。

 there's not much you can do。 So from here， you can explore this arc and you can explore this arc。

And then you can go backward。And so if you do DFS or BFS from this node。

 you're going to find precisely the nodes in this triangle。

 although the other arcs involved go the wrong direction and they won't be traversed by say a depth of a search call。

 So why is that interesting， What's interesting is that if we invoke DFS from this red node or any of the three nodes from this triangle。

 then it's going to discover precisely this strongly kinetic component precisely the three nodes in this circled SCC So that seems really cool。

 It seems like maybe we just do a DFS and boom， we get an Se So maybe if we can do that over and over again。

 we'll get all the SCCs。So that's a good initial intuition， but something can go wrong。

 Suppose that instead of initiating DFS from one of these three nodes on the triangle。

 we say initiate it from this bottommost node in green。

So remember what is the guarantee of a graph search subroutine like DFS。

 it'll find everything findable， but of course， nothing more。

 So what's findable from this green node well naturally everything in its own SCC。

RightSo the four nodes here， it'll certainly find those four nodes。 On the other hand。

 if we start from this green node， since there are arcs that go from this bottommost SCC to the rightmost SCC。

 not only will this DFS call find the four nodes in the green node's strong component。

 but it'll also traverse these blue arcs and discover the three nodes in the red triangle。

 So if we call DFs from this green node， we'll capture all seven of these。

So the point is if we call DFS， it looks like we're going to get a union of possibly multiple SCCs。

 in fact， in the worst case， if we invoke DFS from the leftmost node。

 whats it going to discover is's going to discover the entire graph。

And that didn't give us any insight into the strong component structure at all So what's the takeaway point is the takeaway point is if you call DFS from just the right place。

You'll actually uncover an Se。 If you call it from the wrong place。

 it will give you no information at all。 So the magic of the algorithm that we're going to discuss next is we'll show how in a super slick pre processingces step。

 which。😊，Ironically is itself a call the depth first search。

 We can in linear time compute exactly where we want to start the subsequent depth first searches from so that each indication gets us exactly one strongly connectedtic component and nothing more。



![](img/ddf73c63104abbe99b0c13fd26f90641_7.png)

So the algorithm that I'm going to show you is due to Kaazeraju。

And it will show the following theorem。That the Australian ktic components of a directed graph can be computed in linear time。

 and as we'll see the constants are also very small。

 it's really just going to be two passes of depth first search。

And again let'm going to remind you that for many problems it's natural to assume that the number of edges is at least the number of nodes。

 because you're only interested in cases where the graph is connected。

 of course when you're computing connected components。

 that's one of the most natural cases where you might have a super sparse broken up graph。

 so we're not going to assume M is at least n so that's why linear time is going to be M plus n because that's the size of the input。

And we don't know either N could be bigger than n or N could be bigger than N， we have no idea。

Kazerraju's algorithm is shocking in its simplicity。 It has three steps。

 Let me tell you what they are。First， very mysteriously。

 we're going to reverse all of the arcs of the given graph。

Totally not clear why that would be an interesting thing to do yet。

Then we're going to do our first pass， our first depth first search。

 and we're going to do it on the reverse graph。Now the naive way to implement this would be youd literally construct a new copy of the input graph with all of the arcs in the reverse direction and then just run depth for search on it。

 Of course the sort of obvious optimization would be to just run DFS on the original graph but going across arcs backward。

 So I'll let you think through the details of how you do that but that just works you run DFS and instead of going forward along edges you go backward along edges that simulates depth for search on the reverse graph Now I've written here DFS loop and that just means the usual trick where to make sure that you see all of the nodes of the graph。

 even if it's disconnected you have an outer loop where you just try each starting point separately if you haven't already seen it。

 then you run DFs from that given node I'll be more detailed on the next slide。

And the third step is just your in depth first search again， but this time on the original graph。Now。

 at this point， you should be thinking that I'm totally crazy right so what are we trying to do we're trying to compute these strongly connectedinetic components。

 We're trying to actually compute real objects， these maximal strongly connected regions and all I'm doing is searching the graph and I do it once forward。

 I do it once backward I mean I'm not doesn't really seem like I'm computing anything。

 So here's the catch and it's a very minor catch So we're going need to do a little bit of bookkeeping。

 it's gonna to be very low overhead so we'll still have a blazingly fast algorithm So but with a little bit of bookkeeping here's what's going to happen The second depth first search which searches the graph will in its search process。

 discover the strongly kinetic components one at a time in a very natural way and thatll be really obvious when we do an example which we'll do in just a second。

 Now for the second depth first search to work in this magical way where it just discovers the connectedinetic components one at a time it's really important that it executes the depth for searches in a particular order that it goes through the nodes of the graph in a particular order and that is exactly the job of the first path。



![](img/ddf73c63104abbe99b0c13fd26f90641_9.png)

The depth first search on the reverse graph is going to compute an ordering of the nodes。

 which when the second depth first search goes through them in that order。

 it will just discover the SECs one at a time in linear time。

So let me say a little bit more about the form of the bookkeeping。

 and then I'll show you how that bookkeeping is kept in as we do depth first search。

So we're going to have a notion of a finishing time of a vertex and that's going to be computed in the first pass when we do depth research on the reverse graph。

And we're going to make use of this data in the second pass。

 so rather than just going through the nodes of the graph in an arbitrary order。

 like we usually do when we sort of have a loop to depth first or breath for search。

 we're going to make sure that we go through the vertices in decreasing order of these finishing times。

Now that's to the question of in what sense does this second depth first search discover and report the strongline kinetic components that it finds。

 so we're going to label each node in the second pass with what we call a leader and the idea is that the nodes in the same strongline kinetic component will be labeled with exactly the same leader node and again all of this will be much more clear once we do a concrete example。

 but I want to have it down for the record right now。So that's the algorithm at a high level。

 It's really just two passes of DFS with some bookkeeping， but this is underspecified。

 you really shouldn't understand how to implement the algorithm just yet， So what do I owe you。

 I owe you exactly what I mean by DFS loop although this you've seen more or less in the past is just a loop over all the vertices of the graph and then if you haven't seen something yet you DFS from that starting point I need to tell you what finishing times are and how they get computed。

 they're just going to be integers one to N， which is basically when depth first search gets finished with one of the nodes and then I need to tell you how you compute these leaders So let me tell you all three of those things on the next slide。

So the workhorse for Caserrajus Str kinetic components algorithm is this DFS loop subroutine。

 and it takes as input a graph， okay so it does not take as input a starting node。

 it's going to loop over possible starting nodes。Now， for the bookkeeping to compute finishing nodes。

 we're going to keep track of a global variable that I'll call T。Which we initialized to zero。

The point of T is to count how many nodes we've totally finished exploring at this point。

So this is the variable we use to compute those finishing times in the first pass。

 that magical ordering that I was talking about。 Now we're also going to have a second global variable to compute these things I was calling leaders。

 and these are only relevant for the second pass。So what S is going to keep track of is the most recent vertex from which a DFS was initiated。

So to keep the code simple， I'm just going to do all of the bookkeeping in DFS loop but really DFS loop gets called twicew once on the reverse graph once in the forward graph。

 and we only need to compute these finishing times in the first pass on the reverse graph and we only need to compute these leaders on the second pass for the forward graph。

 but let's just keep them both in there just for kick。

Now we're going to need to loop through the vertices and so the question is in what order are we going to loop through the vertices and that's going to happen differently in the two different passes。

 but let me just use some common notation， let's just assume in the subrtine that the nodes are somehow labeled from one to end。

In our first depth first search， it's going to be labeled totally arbitrary。

 So these are basically just the names of the node or their position in the node array。

 whatever used to it in some arbitrary order。 Now， the second time we run DFS loop。

 as indicated on the previous slide， we're going to use the finishing times as the labeling。

 And as we'll see， the finishing times are indeed numbers between one and in。

So now what we do is we just iterate through the nodes and decreasing order。

And if we haven't already seen node I， then we initiate a DFS from it。

 so as usual we're going to be maintaining a local Boolean to keep track of whether we've already seen a node yet in one of the DFS passes。

Now， remember， the global variable S is responsible for keeping track of the most recent node from which depth first search had been initiated。

 so if Is not explored and we initiate a depth first search from it， we better reset S。

 then we do the usual DFS NG starting from the source node I。 So for completeness。

 let me just remind you what the depth first search sub team looks like。

 So now we're given a graph and a starting node。

![](img/ddf73c63104abbe99b0c13fd26f90641_11.png)

So the first time we see a node。We mark it as explored。

And just a side note that once a node is marked explored。

 it's explored for this entire invocation of DFS loop。

 so even if this DFS from a given node I finishes and then the outer for loop marches on and encounters I again。

 it's still going to be marked as explored。Now one of our book Keep me Jo is to keep track of from which vertex do the DFS that Disc I get called？

So when I is first encountered， we remember that S was the node from which this DFS originated。

And that， by definition， is the leader of I。And then we do what we always do with depth for research。

 we immediately look at the aps going out of eye and we try to recursively DFS on any of those。

 although of course we don't bother to do it if we've already seen those nodes。

Now once this for loop has completed， once we've examined every outgoing arc from I and for each nodeJ。

 either we already saw it in the past or we've recursively exploreed from J and have returned at that point we call ourselves done with node I there's no more outgoing arc to explore we think of it being finished。

 remember T is the global variable that's keeping track of how many nodes we're done with so we increment T because now we're done with I and we also remember that I was the teeth。



![](img/ddf73c63104abbe99b0c13fd26f90641_13.png)

Vertex with which we finished。That is， we set eyess finishing time to Dt。

 because depth for a search is guaranteed to visit every node exactly once and that therefore finish with every node exactly once。

 theres global counter T。 Well， when the first node is finished。

 it will be value 1 than when the next node gets finished， it'll have value 2。

 then'll have value 3 and so on。 when the final node gets finished with， it'll have value n。

 So the finishing times of the nodes are going to be exactly to integers from one to N。

 Let's make this much more concrete by going through a careful example。In fact。

 I think it'll be better for everybody if you yourself traced through part of this algorithm on a concrete example。

 so let me draw a nine known graph for you。So to be clear。

 let's assume that we've already executed step one of the algorithm is we've already reversed the graph so that is this blue graph that I've drawn on the slide。

 this is the reversal we've already reversed the arcs Moreover the nodes are labeled in some arbitrary way from one to9 just assume these are how they show up in the node array for example。

 and remember in the DFS loop routine are' supposed to process the nodes from top to bottom from n down to one。



![](img/ddf73c63104abbe99b0c13fd26f90641_15.png)

So my question for you then is in the second step of the algorithm when we run DFS loop and we process the nodes from the highest name9 in order down to the lowest name one。

 what are the finishing times that we're going to compute as we run DFS loop Now it is true that you can get different finishing times depending on the different choices that DFS loop has to make about which outgoing arc to explore next but I've given you four options for what the finishing times of the nodes 1。

2，3 all the way up to9 respectively might be and only one of these four could conceivably be an output of the finishing times of DFS loop on this graph so which one is it。

All right， so the answer is the fourth option。That is the only one of these four sets of finishing times that you might see。

Being computed by DFS loop on this blue graph so let's go ahead and trace through DFS loop and see how we might get this set of finishing times So remember in the main loop we start from the highest node9 and then we descend down the to the lowest node1 so we start by invoking DFS from the node9 so now from here there's only one outgoing arc we have to go so we mark9 as explored。

And then there's only one place we can go we can go to six so we mark six is explored Now there's two places we can go next we can either go to three or we could go to eight and you know in general DFS could do either one now to generate this fourth set of finishing times I'm going to need to assume that I go to three first okay so again what DFS does what we're assuming it does it starts at nine and it has to go to six it marks those as explored then it goes to three。

It does not go to8 first， It goes to3 first。 Now， from 3， there's only one outgoing arc。

 which goes to 9， but9， we've already marked as explored。 So it's not going to reexlore 9。

 It's going to skip that arc。 Since that that's three is only outgoing arc。

 then that four loop completes。 And so then three is the first node to finish。

 So when we finish with three。 we increment T is started at 0。 Now， it's one。

 And we set the finishing time of3。To be one。Just like we said it was in the example。

So now we go that now we backtrack to six， now we have another outgoing arc from 6 to explore。

 so now we go to8 from8， we have to go to2 from two， we have to go to 5 from five， we have to go to8。

8 we've already seen， so then we're going to be done with five because that was its only outgoing arc。

 so then when increment T now is two and the finishing time of five is going to be two。As promised。

So now we backtrack to two， there's no more outgoing marks from two。

 so two is going to be the third one that we finish as promised。Then we finish with8。

 So the finishing time for8 is going to be the fourth node to be done。As promised。

 now we backrack to six， we're done with six。That's the fifth node to be completed。As promised。

 and then finally we get all the way back to where we started at nine。And nine is the。

Six nodes to be completed。As promised。Now if we were computing those leaders。

 all of these nodes would get the lit9， but again， the leaders are only relevant for the second pass。

 so we're just going to ignore the leaders as we're doing this trace。

 we're just going keep track of the finishing times So now we're not done so all we did is we finished with the DFs that is invoked from the node 9 and we found six of the nodes total in that depth first search So now we return to the outer for loop and we decrement I so it started at 9。

 we're done with that now we go down to8， we say have we already seen 8， yes， H's already explored。

 so we skip it go we decrement I down to 7， we say have we already seen node 7 No we have not7 is not yet explored。

 so we invoke DFs now from node 7。7even has two outgoing arcs。 It can either go to4 or can go to 9。

 Let's say it checks the outgoing arc to 9 first。 Now，9， we already explored。

 granted that was in an earlier part of the four loop。

 but we remember that we're going to keep track of who got explored on previous iterations of the four loop。

 so we don't bother to reexpllore 9。 So we skip that。 So now from 7， we have to go to4 from4。

 we have to go to one from one， we have to go back to7。7's already been explored its way backtrack。

 Now we're done with we're done with one So one is the next one。 we're completed with。

And the finishing time of one is going to be seven。As promised， we backracked to four。

 there's no outgoing arcs from4 to explore， so that's going to be the eighth one to finish。

As promised， and then the last one to finish is Po node7， it is last。

So that would be an example of how the DFS loop subroutine computes finishing times on a reversed graph。

 So now let's work through the second pass on the forward version of the graph using the same example。

 Now， remember the point of the first pass is to compute a magical ordering and the magical ordering against these finishing times So we're going throw Now we're going to throw out the original node names and we're going to replace the node names in blue by the finishing times in red。

 we're also going to work with the original graph which means we have to reverse the arcs back to where they were originally So those are the two changes you're going see when I redraw this graph。

 First of all， all the arcs will reverse orientation。 second of all。

 all of the nodes will change names from the original ones to the finishing times that we just computed。

So here's our new graph with the nude node names and all of the arcs with their orientation reversed and now we run DFS again on this graph and again we're going to process the nodes in order from the highest label9 down to the lowest label one。

 Moreover we don't need to compute finishing times in the second pass we only need to do that in the first pass but the second pass we have to keep track of the leaders and remember the leader of a vertex is the vertex from which DFS was called that first discovered that node。

All right， so what's going to happen Well in the outer four loop again。

 we start with I equal to9 and we invoke DFS from the node9。

So that's going to be the current leader because that's where the current DFS got initiated Now from nine。

 there's only one choice， we have to go7 from7 there's only one choice we have to go to 8 from8。

 there's only one choice we have to go back to9 and then nine's already been seen so we backtrack。

 we go back to 8， we go back to  seven， we go back to nine and that's it。

So when we invoke DFS from node 9， the only things that we encounter are the node 7，8， and9。

And these are all going to be given the leader vertex9。

You will notice that this is indeed one of the strongly connected components of the graph。

 we just sort of found it with this invocation of DFS from the node 9。

So now we go back to the outer for loop and we say， okay， let's go to node 8。

 Have you already seen 8， Yes， What about 7。 Have you already seen 7， Yes， what about 6。

 Have you already seen 6， We have not， We have not yet discovered 6。 So we invoke DFs from node 6。

 We reset the global。Source vertex S to6。From 6， we can go to9 or we can go to1。

 So let's say we explore 9 first。 Well， we already saw 9 in the earlier iteration of the four loop。

 so we don't explore it again， so we don't discover9 now， so we backtracked to6。

 we go to1 from one we have to go to5 from 5， we have to go to 6。

 and then we start backtracking again。 So the only new nodes that we encounter when we invoke DFs from the node 6 are the vertices6。

1 and 5 and all of these will have a liter vertex of 6 because that's where we call DFs from when we first discovered these three nodes。

And you'll notice this is another SCC of this directed graph。

So we invoked DFS again now from a new node to new node 6， and what it discovered。

 the new nodes it discovered was exactly an ST of the graph， nothing more， nothing less。

So now we return to the outer four loop。 We go to node 5。 Have we've already seen 5。 Yes。

 we've already seen4。 No， we haven't seen four yet。 So now we invoke DFs from 4。 Again。

 we can try to explore 5， but we've seen that before。 We're not going to explore it again。 So from 4。

 then we have to go to 2 from two， we have to go to 3 from three， we have to go back to 4。

 And then after all the backtracking we're done。 So the final call to DFs will be from the node 4。

And that DFS will discover precisely， newly discover precisely the nodes two，3， and four。

 they will all have the leader vertex 4 because that was where this DFS was called from。It's true。

 We'll go back to the for loop and we'll check have we seen three yet。 Yes， have we seen two yet。

 Yes， have we seen one yet， Yes， and then the whole thing completes。

 And what we see is that using the finishing times computed from that first step first search pass somehow the strongly connected component of this graph just showed up and presented themselves to us one at a time on a silver platter。

 Every time we invoked Dfs， the nodes we discovered newly were precisely one of the SCCs。

 nothing more nothing less。 And that's really what's going on in this algorithm。

 it turns out this is true in general。 The first pass Dfs on the reverse graph computes finishing times。

 so that if you then process nodes， according to decrease ordering of finishing times in the second pass Each in to DFs will discover one new SCC and exactly one SCC。

 so they'll just present themselves to you one per DFS call in that second passes for loop。

This is of course merely an example， you should not just take a single example as proof that this algorithm always works。

 I will give you a general argument in the next video。

 but hopefully there's at least a plausibility arc。

 no longer does this threestep algorithm seem totally insane and maybe you could imagine perhaps it works at least there's some principles going on where you first compute the right ordering to process the nodes and then the second pass peels off SCCs one at a time like layers from an onion。

One thing that I hope is pretty clear is that this algorithm correct or not， is blazingly fast。

Pretty much all you do is to depth first searches and since depth first search as we've seen in the past runs in time linear in the size of the graph so does cause a Rajus to pass algorithm there are a couple subtleties and I encourage you to think about this and you'll be forced to think about this in the programming project for week four So for example。

 in the second pass how do you process the nodes in decreasing order of finishing time you don't want to sort the nodes by their finishing time because that would take n log n time So you need to make sure that you remember in the first pass that you sort of remember the nodes in a way that you can just do a linear scan through them in a second pass So there are some details but if your intuition is that this is really just double DFS properly implemented that's pretty much exactly right。

So having spelled out the full implementation argued that it's definitely a linear time algorithm and given at least a plausibility argument via an example that it might conceivably be correct。

 let's now turn to the general argument。

![](img/ddf73c63104abbe99b0c13fd26f90641_17.png)