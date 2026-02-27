# UIUC《算法与计算模型｜UIUC CSECE 374 - Algorithms and Models of Computation 2023》中英字幕 p20 20231026-Oct 26_ Dijkstra and Bellman-Ford.zh_en -BV1Mh7RzaEL2_p20-

![](img/adff696eb8d597a68cf19f681c72c3fb_0.png)

。Thank。

![](img/adff696eb8d597a68cf19f681c72c3fb_2.png)

系 you话生。不是。Yeah。

![](img/adff696eb8d597a68cf19f681c72c3fb_4.png)

啊，嗯拜。o好。

![](img/adff696eb8d597a68cf19f681c72c3fb_6.png)

And。系。Okay， let's。Let's go ahead and get started， thank you all for coming。啊。

Enjoy the last day of non winter， I guess。Or like the last week of non winter。

 it's supposed to get down below freezing。Early next week。So dress up warm for Halloween。嗯。

One thing just I don't have any any detailed announcements。

 just one thing I do need to leave immediately after class。

 so the usual crowd of people that come up and ask me questions， I'm going to have to say no。

 I'm going to do my best to end the lecture a couple of minutes early so that there's at least a time for a couple of quick things。

 but but I can't hang out for the half hour that I usually do。😡，嗯。All right。So。

Last time we started talking about。Computing shortest paths。And。There is this。

Generic strategy that all shortest path algorithms follow。Um， which is to look for edges。That are。

Tense。So at every vertex， I'm going to maintain a distance value in this case。

 it's five and I'm going to in。Um。Maintain a predecessor。

 which is meant to be the second to last vertex on the shortest path from the start vertex to that particular vertex。

Okay so if I've got some start vertex down here and there's some path leading up。To you。Actually。

 let me make this a little bit clear because that looks like an ass。Let's call that three。

Whatever the previous vertex here is I call that。Let's call that T since it's the letter before you。

嗯。So maybe the edge has length two and the edge from S to t has length1。

 so I have some path leading from S up to that vertex U that has length three and the second to last vertex on that path。

Is T， that's the predecessor of that versex。And similarly over here at this other vertex V。

 I've got V dot disk。Is 15 and I don't know， V dot pred is some other vertex W that I haven't drawn in the picture。

嗯。But the thing that you'll notice about。😡，Those particular distances and the weights of the edges is that they signal immediately that 15 cannot be the length of the shortest path from S to V。

 because I can see a shorter path in front of me， namely I can take the shortest path from S to U which only has length three。

 and then I can add on to that the edge directly from u to V， which has way four。

 and this would give me a path with total length seven。Okay， so we say that U to V is tense。If。Um。

You don't just。Plus。The weight of this edge from U to V is less than v dot list。

That's the picture that you're seeing up there。And then we relax。Uvie。By setting V dot list。Equal to。

The length of the shorter path。And setting V dot predecessor equal to U。

 so I'll move this seven just changing this to seven and I'll change this predecessor to U so now this becomes part of the shorter path up to that point。

Hey， so the generic strategy is。Yeah， sorry， go ahead again。U， that should have been three。

I fixed one of them and didn't fix the other one， sorry。对。So at the beginning of time I say。

 what do I know about the distances， well the distance from S2 itself is zero。

 so so I'll initialize s dot disk to zero， anything else I know nothing。

 so I'll set v dot disk to infinity for all V that isn't S。😡，Um。

 nobody has a predecessor yet because I haven't discovered any non trivial paths。

And then I wander around the graph looking for tense edges， if I find a tense edge， I relax it。

 if I find a tense edge I relax it， if I find a tense edge I relax it。

 someone and someone until eventually there are no more tense edges and at that point。

 the predecessor pointers define a shortest path tree so if I follow the predecessor pointers from any vertex I'll eventually lead back along the shortest path back to S or really along the reverse of the shortest path from S to that original node。

嗯。So this gives us a way of constructing shortest path trees。

And there are a few different variants of this generic strategy that work best in different circumstances。

So one is that if I have unweighted graphs。Meaning every edge has equal weight。

 which I might as well take to be one， so the length of a path is just the number of edges in that path。

😡，In this case， the right strategy is to use breadth for search and this runs in linear time。

Another special case is your weights could be anything you want。

 but if your input graph is a directed acyclt graph。😡。

Then I can walk through the graph in topological order， relaxing edges as I encounter them。

 and I'm guaranteed not to make anything tense behind me。

So this is morally or it can be written as depth for search again。

 this runs in time linear in the complexity of the graph。But most graphs are not daAgs。

And most interesting applications of shortest paths， the edges have weights。

And so these two special cases are important to keep in mind when they do show up。

But they're not the most common the most common version， the most common version。is。That you have。

An arbitrary graph is not necessarily a dag。And the weights on the edges represent。

Some notion of length or distance or duration， like how long does it take to drive from here to Washington DC。

 well I can model the map of the US by having nodes for every city。

 town and exit on the interstate system and I can use edges to represent roads connecting those places。

😡，And I can define the weight of an edge to be the time it takes to drive from one end of the road to the other。

Then asking， how long does it take to drive from here to Washington。

 DC is asking what is the shortest path from the node representing SF？

To the node representing the White House。And in this weighted graph。

USo the most intuitive thing is weights represent distances or they're sometimes referred to as lengths。

but there are other circumstances where the weight of an edge might represent the amount of money that you have to pay。

 but the amount of gasoline that you have to buy or the amount of some other substance that normally only comes in nonneg amounts。

Like I don't know， parrots。U。If I drive from here to Washington DC。

 certain roads have swarms of parrots on them and I'm going to get them all over my windshield。

 I want to drive to Washington DC accumulating the least amount of parrot corpses， how do I do that。

 I model it as a graph or the weight of an edges that how many parrots I'm likely to kill in that road？

In this circumstance， the algorithm that you already know。

I'm going to talk about it a little bit more detail anyway， is Dyke Str algorithm。

There is the pseudocode up on the screen already。And in the most。

Straightfor implementation of Dyexter's algorithm， the running time is slightly bigger than linear really I should probably be writing this as V plus E。

😡，Logly。But when I'm。Writing down these running times。

I'm kind of making a judgment call and saying you know what， without loss of generality。

 let me assume that the graph is connected， let me assume that S actually has can reach every other vertex in the graph。

Because otherwise。It isn't really the vertices and edges。

 it's really only the reachable vertices and edges that I care about。But if a graph is connected。

 if there really is a spanning tree， then I know the number of vertices is at least the number of edges plus one。

 because that's the relationship between vertices and edges in the spanning tree itself。

So as long as I'm dealing with a connected graph， the V gets swallowed up in big notation into the E。

 so I just write it more simply as the e log V。😡，Okay， so here I'm。Assuming。The graph is connected。

And you're afraid to make this assumption in your homeworks and exams and so on as well。

 which also means that BFS and DFS， I could have just written that down is big O E。嗯。Okay。

So Dkesster's algorithm is the one that you want to use when the edges are unweighted。

 but there are circumstances where the edges can have negative weights， for example。

If the weight of an edge corresponds， say to a certain amount of money that I might earn by going from this point to that point。

 minus the cost of gas and transportation diamond and whatnot， hotels， for some edges。

 that money might be positive， if I drive along this edge， I'll make a profit for other edges。

 that cost might be negative if I drive along this edge， I take a loss。In that case。

 I might be more interested in。啊啊。Well， if I guess if I'm a masochist。

 I'm trying to find the route from here to Washington， DC that loses me the most amount of money。

 so the total profit I win is as small as possible， so maybe I should reverse profit and loss here。

Um， but u u there there are things where you have a resource that can come in both positive and negative flavors like money。

Then it makes sense sometimes to ask about shortest paths and then you can run Dykster's algorithm。

 it will work。It just won't be necessarily efficient。😡。

But there's a different algorithm that is guaranteed。

To always be efficient and this really works for arbitrary graphs with arbitrary weights。

And this is the so called Belllm and Ford algorithm， which runs in time v times E。Not v plus E。

 but the product the number of vertices and the number of  edges。Now。

 one quick comment about these running times， when we're dealing with graph algorithms。

 we generally want to analyze things in terms of two different parameters。

 the number of vertices and the number of edges。It's true that you can say in the worst case。

 E is v squared。BFS， DFS both run in v squared time in the worst case， unquote unquote， Dyketra。

 the way I've written it here， that running time is v squared log V in the worst case。

 and Belman Ford is v cubed in the worst case。The reason why I teased the dependence on V& E apart。

iss that I want to understand the behavior， how the behavior varies depending on how sparse the graph is。

 if the graph is a tree with just a few extra edges。

 then E is only roughly proportional to V and this is the structure you see， for example。

 in real world road networks。Real road networks or real circuit diagrams that you find inside your iPhone。

Those are not going to have a quadratic number of edges。

They're only going to have a near linear number of edges。

And so if we get something that depends on E as opposed to really， really actually。

 and no matter how many edges you have， depending on v squared。

 the algorithm that depends on E is going to be more efficient in practice。So we always。

 I'm always writing these running times in terms of these two different parameters。

It's fairly common to see these denoted n and M， so n is the number of vertices。

 and M is the number of edges。😡，But I find in needs to be a little bit more mnemonic and so I encourage people to do this。

Okay。So this is the summary。If you just want to use shortest path algorithms as black boxes。There is。

 this is what you write on your cheat sheet。Um， but what I want to spend the next 45 minutes or so doing is walking through the last two algorithms in some detail。

 explaining why they were。And exactly what the relationship with negative edges is in particular walking through Belman Ford。

To call back to what we were doing two weeks ago。W Bellllman Ford。

 at least one way of thinking about it， is a dynamic programming algorithm。

And so now we're going to be starting to do dynamic programming over graphs。😡。

And not just playing around with you know traversal algorithms in their various forms。

 you can also think of Belmon Ford as a traversal algorithm， but it's a little bit less natural。嗯。

All right， so any questions about sort of the high level overview before I start talking about Dykester in more detail？

Okay。Yes。On exams， we need to know about the。Specific steps in universal。The algorithms。Okay。

 so the question was on exams， do I need to know how Dyktra is implemented， no？

On exams Jo need to know the techniques that would in principle allow me to derive Dketra from scratch。

 yes。So you need to know what tenses and relaxes， you need to know what a priority cue is。

Yeah you need to understand maybe at an intuitive level that Dykesstrude does this wavefront thing。

You need to understand the process by which I will derive Belman Ford because it's the dynamic programming process。

But do you need to know that the right way to say this is do you need to memorize the algorithms， no。

 of course not， should you be able to derive the algorithms on the fly given about three hours， yeah。

😡，Okay。😊，This goes for every algorithm in this class， by the way。嗯。Nothing。

 nothing really here should require that much memorization， but if you understand the principles。

 you should be able to reeriveve most most of the algorithms you've seen in the class。

 linear time selection maybe not。Looking for a local minimum in two D， maybe not。呃。

but at least the most of the other ones I've shown in class， yeah。

If you understand the basic idea working out the details you should be able to do。Okay。

 so here's Dyktra Dyktra can be seen as a kind of best for search。😡，So I have here a data structure。

 which I'm calling here a priority queue， so a priority queue maintains a collection of objects in this case of vertices。

 each with a priority。And satisfies it supports a few basic operations， so I can insert。

An object X with a given priority， I can extract。The object with the smallest priority and I can reach into the。

I can reach into the data structure and say， I know that object X is in there。😡。

Make its priority smaller by setting it to this new value。

I don't know why this is called decreased key instead of decreased priority。

 but that's sort of what we're stuck with， I think。嗯有。嗯。In Dyktra's original algorithm。

The way the priority at Q was implemented was with an array indexed by vertices that held the priorities when you wanted to insert something。

 you just wrote the priority down in the right spot in the array， when you wanted to decrease key。

 you just wrote the priority down in the right spot in the array。

 when you wanted to do an extract bin。😡，He did a linear time scan of the array。

 found the minimum thing and drew an X through it， so you wouldn't the next time you looked。

 you wouldn't find it again。We know of better。More efficient data structures now。

 so the traditional one is a binary heap。Each of these operations is going to take log of the number of objects in the heap。

 but since the objects in the heap are vertices， that means the running time of each of these operations is order log V。

😡，嗯。So at the beginning of time， I'm going to do what I do with every version of whatever for search。

 I take my source for text X and I put it into my priority queue。😡。

Uing and the priority that I use is the estimated distance for each of ver text。😡。

So when I initialize things， the estimated distance from S to S is zero。Because that's in fact。

 the correct distance， so I insert S with a priority of zero。

Then as long as the priority queue has something in it。

I'll extract the vertex whose priority is smallest。

So the invariant I'm going to maintain here is that the priority of any vertex v is equal to its distance value。

So I'm pulling a vertex out of the priority queue whose estimated distance is as small as possible。😡。

I look at all of its outgoing edges。And if any of those edges are tense。

I know the distance value at the opposite end of those edges is wrong， so I relax。

 if I find a tense edge， I relax it and I take the head of that。😡。

Edge and put it into the priority queue with its new distance。 Now。

 if it's already in the priority queue， that means I do a decrease key。

 if it's not already in the priority queue， that means I'm doing a fresh insert。😡。

That's the algorithm。哎。嗯。And here's an example of the algorithm running on a graph that has non negative。

Edge weights。So S here is the vertex down at the bottom。嗯。At the beginning of time。

S where the priority of zero is the only thing in the priority queue。

 I pull S out of the priority queue。And。And so I pull S out of the prioror to queue and I relax its two outgoing edges because they're tenses。

0 plus four is less than infinity，0 plus three is less than infinity， so I relax these two edges。

 changing this distance value to four， this distance value to three。And setting the predecessors。

 those are the blue arrows。And that's the end of what I do with S。

 the next minimum priority vertex is the one labeled three， I pull it out。😡，This edge going this way。

 I look at it， but I noticed that it's not tense， so I don't do anything。😡。

But this edge going up is tense， so I put this top right vertex into the priority queue。

Now the vertex labeled four has the minimum priority， so I pull this four out。

 I notice this edge going up into the left is tense，4 plus zero is less than infinity。

 but this vertex going up into the right is also tense。

4 plus 5 is less than 15 so here I'm doing a decrease key to change this 15 to a9。😡。

But I did a fresh insert to get this infinity into the priority queue。

Then I pull the four out of the priority queue， this edge leading to the top is tense and the edge leading to the bottom left vertex is tense and at this point once I've built this tree。

 there's still three things in the priority queue， but as I pull them out none of those edges leading out of those vertexas are tenses。

 so at this point that blue thing is the shortest path tree。Rooted to us。嗯。So。

Questions about how this execution works。Yeah。So essentially very right。

 but essentially was that just kind of pull the thing of the smallest priority out of。That's right。

 so you pull the node， so all of the nodes that are shaded in pink。

 those are the ones that are in the priority queue at any one of these stages。

 the one circled in red is the one with minimum priority， that's the one I pull out of my heap。😡。

And then I look at all the outgoing edges from that node， try to relax them， if I succeed。

 then I put the vertices at the other end into the priority queue。

So one thing that you'll notice here， if I just write down， you know， what's the distance？

Associated with the vertex that I'm pulling out at every stage。Those numbers never go down。

I'm discovering。One way to say this is because all of the edges have non negative weights。

The distance values of anything that's in the priority queue must be greater than or equal to the distances of things that I've already dealt with。

 I've already pulled out of the priority queue and relaxed。😡。

mThat's because whenever I pull anything out。I I pull a vertex out， if it relaxes any outgoing edges。

 the priorities is that the other vertices have to be at least as big as the one I pulled out。😡。

So there's never an opportunity to pull something out of the priority queue。

And then put a smaller distance back into the para。So the distances are always increasing。😡。

In terms of what the priority Q sees is the priority that you're extracting。

So the priority queue thinks distances。Only。Increase。On the other hand。

 if I look at any individual node。Its distance label can only go down because I only change it because some incoming edge is tense。

And the way that I change it is by changing the value from a higher value that's obviously wrong to a lower value that might be right。

So any distance value at a particular vertex？😡，Is only decreasing。So at each node。Distance。Only。

Decreases。And what these two observations imply？Is that a single node can be pulled out of the priority queue at most once。

If vertex v were ever pulled out of the priority queue more than once。

 its priority must be higher the second time than it was the first time。

 but that's impossible because its priority is its distance label and distance label that vertex can only go down。

 can't ever go up。😡，Okay， so。Um。Each。Vertex。Is extracted。UAt most。Once。

But every time I execute that while loop， I'm extracting a vertex from the priority kid。

So the total number of iterations。All right， so this line here happens at most v times。哎。That。

That I can't call extracttonin more than v times again。

 I'm working here under the assumption that all the edge lengths are non negatives。😡，嗯。

That means that this line is executed。For each vertex， that line is executed。😡。

At most once for each edge leaving that vertex。Another way of saying that is each edge is relaxed at most once。

😡，So this edge， this call to relax happens at most e times。😡，Which means。

This stuff happens at most E times。And so I've got V extract mins， which take log v time each。

And I've got it most E decreased keyser inserts， which take log v time each。😡，Plus。

 I've got V inserts at the beginning。😡，So altogether together。

 I'm going to have order V plus E priority Q operations。

And that leads me to my final running time of， again， assuming the graphics connected order e log V。

嗯。So the。Everybody follow。What just happened？If all of the edges have non negative weights。

Then intuitively， I'm discovering vertices in increasing distance order from the source。

The first time I pull a vertex out， that distance label is correct。😡。

And those distance labels are only going up， so I'm sort of getting this expanding waveleth。Yes。

在我们产品外。It'sOkay， so let's walk through this。These two observations again。

U whenever I put anything into a priority queue， it's put there because I relaxed some edge from U to V。

😡，Because edge weights are positive， the distance label at V has to be at least the distance label at U。

Because it's actually the distance label you plus with the length of that edge。

So whenever I can take something smaller out of a priority queue， I might put bigger things in。

But I'll never put something smaller in than I just took out。

So everything that I put in has to be larger than the last minimum thing I took out。

I took out a five， maybe I can put it in a seven then a nine and a 12， but I can't put in a four。

So this means the minimum value in the priority queue is always going up。

Okay that's what I mean by the distances only increased。

 so I really should say minimum distance only increases。So actually let me go ahead and say that。

 you know， minimum distance only increases。On the other hand。

 the distance labeled at any particular vertex can only change by getting smaller。

So the priority Q sees things going up， the verticeses see things going down。

 so the same vertex can't be the smallest thing in the priority Q twice。

Because the priority co logic would say the second time the distance is bigger and the relaxation logic would say the second time the vertex distance was smaller。

It's a contradiction。Make sense。Somehow just。But。嗯你个知道。好。But somewhere that you haven' a lot。Okay。

 so the same logic here actually implies each edge will be relaxed at most once。

When it tailovertex is pulled out of the priority queue。

But each distance label could change multiple times。I mean。

 I had an example here where the distance label at that top right vertex started as infinity。

 and then I relaxed one edge， it went down to 15 and I relaxed another edge it went down to nine。

So distance labels can change more than once。But they're in flux they come out until that vertex comes out of the priority cube。

 and then they're fixed and they're correct。Yes。I'm sorry， could you say that again？Okay。So。

The main while loop iterates once for at most once for every vertex， so the variable U。😡。

Takes on at most V different values。系。Now in the inner loop。

 what I'm doing is I'm exploring all the edges leaving you。Each at most once， if I fix you。

 then I'm exploring each of those edges at most once。

 I'm never going to see you again in the outer loop。😡。

So there's never going to be another opportunity to relax those edges。so an edge UVV is relaxed。

 the only time it can be relaxed is when you is the minimum thing I pull out of the priority queue and then even then only if the edge happens to be tense at that moment。

😡，哎。Now。That also means in the case when edge weights are non negative。This line never happens。

I'm never going to reinsert anything into the priority queue。

So I don't need to test whether it's already in the priority queue， I know it is。

And so I can simplify the algorithm somewhere。嗯。By just removing that if then else clause and just replacing it with a decreased key。

Here I wrote Vv。Ds， that's just a clever way of observing that s。

Ds is zero and anything elseD is infinity， sot write I didn't have to write that out explicitly that was set by SSP。

😡，And this is the version of Dyktra that you'll see in most textbooks。

The assumption is that you only run Dykstro when all edges are non negative。

And that's a reasonable first approximation to the truth。

But the actual truth is a little bit more subtle， yeah。So the question is。

 does this happen with multiple components， shortest path problems。

 we don't need to deal with multiple components？😡，The shortest path from S to another vertex that S can't reach is infinity because there is no path。

Okay。嗯。So this is great if you know all your edge weights are non negative。

 here's the algorithm and I already argue that it's correct， I already argued that it's efficient。

 so great， what happens when there are negative edges？😡。

And you might have to in the original version of Dyixtra I showed you。

 you might have to put something back in， so here's an example of that behavior。So again。

 the same visual standard here， the vertices that are shaded in pink。

 those are the things that are in the priority queue， the ones circled in red。

 that is the one that has the minimum distance label， that's the one I'm going to extract next。

 the blue edges indicate predecessors。😡，So I start。

With putting S in with zero and everybody else is in or with infinity， I pull S out。

 I relax these edges now three is the minimum， I relax these edges， now four is the minimum。U。

I relax this outgoing edge， but that's the only one now you know five is the minimum。

 but there aren't any edges coming out of it， so I don't need to do anything。

Now sevens is the minimum， so I relax here。Um and。In particular。

 I relax this edge going from seven over to five， seven minus three is smaller than five， so I relax。

Which means right off the bat。IveI've put this edge in。

 taken it out and put it back into the priority queue。

The simplified version of Dytra's algorithm would simply fail at this point。

 you would get numbers at every vertex， but they would not be the actual shortest path distances and the predecessor would not give you the actual shortest paths。

But by putting it back into the priority queue， you're giving the Ford's generic relaxation strategy a chance to say。

 oh oh wait maybe there's more tense stuff， let me go and fix it again and again I pull four out and there's no outgoing edges then I pull that vertex at the top。

😡，That's labeled eight， oh8 minus five is less than four， so here I relaxed this thing again。😡。

And put it back in again and now it's the minimum again and then I pull nine out because thiss the only thing in the priority queue and nine minus seven is less than three so I pull it out again。

And it even happens that when I when I。Pull that nine out again。

 I also relaxed this edge going up here to seven， which I previously took out and that sets off a chain reaction through the top part of the graph。

 which means that actually I'm going to pull this vertex out again and again。So altogether。

 I think I process this upper left vertex in this example graph six times。Is that right？Yeah。

 instead to five the to four， then to three then two the one the zero， yeah， six times。

And several other vertices are handled more than once， several edges are relaxed more than once。

Sometimes an edge is tense， even if it's a predecessor edge。

But eventually eventually everything settles down to the correct shortest path tree。Provided。

 there are no negative cycles。If there's a negative cycle in the graph。

 then this generic relaxation strategy will just run forever。

 some edge on that negative cycle will always be tense。😡，You'll just get it into an infinite loop。

There are ways of detecting that infinite loop and sort of generically。

 I'll talk about it more when we're talking about Belman Ford， but the right thing to do。

 at least initially you just say， let's assume there are no negative cycles because if there are I'm completely screwed anyway。

系。But if there are no negative cycles。That her works。And。Now in the worst case。Right。

worstors case running time for Dyktra。Turns out to be exponential in the number of vertices。

But it also turns out as if I only have a constant number of negative edges。Then provably。

 each vertex only gets pulled out of the priority queue a constant number of times。😡。

And so my running time is only V log E。Yeah， that oh， sorry。

Sometimes I could swear this is my right hand。E love thee。Yeah。

So is it possible to have negative shoulder paths。Yes， it is。

It is possible to have shortest paths whose total length is negative。That was also true for daAgs。

 by the way。If you have a dag， all the edges might be negatives。And in fact。

 the worst case for Dyextra is a dag where all the edges are negative。

So Dykesster's algorithm for that weird special worst case runs in exponential time。

 but we have this other algorithm for Dgs that runs in linear time。Yes。Okay。

 so so this is actually a very good question， the question is if I wanted to find the shortest path。

 couldn't I say find the edge with minimum weight？And add it and then find the next edge with the next smallest weight and add it。

 find the next edge with the next smallest weight and add it as long as it doesn't like create any weird cycles。

 what you're describing is an algorithm for building the minimum spanning tree of an undirected graph。

The minimum spanning tree you're trying to minimize the global weight of all of the edges in the tree that you're building。

It's a different problem， so the answer ultimately is no。That won't give you the right answer。

 there are graphs where the minimum span tree looks very。

 very different from any single source shortage of path tree。So it's good intuition。

 but for a slightly different problem。Fact。What you're describing is normally referred to as Crosspo's algorithm。

Okay。In practice。Experimentally， the Dysters algorithm is actually proved to be faster for most real world instances would have reasonable negative edge weights so even there are other results that say if you have negative edge weights but they're not very negative Dtra can still be efficient things like that so the standard that you see in a lot of places that says oh my God something in there is negative immediately run Belmond Ford no。

It's not that clean。There are cases when Dman Ford is faster。But more often than not Dysters fine。

Yeah。So this e log V， when you've got a constant number of negative edges。

 there's a lemma that needs to be proved， which is if there are at most k negative edges。

 then each vertex is pulled out of the priority queue at most two to the k times。😡。

But if k is a constant， two to the K is a constant。So you go through the same analysis。

 but multiply it by a factor of constant。You get you get e lovevy。Okay。All right。

 but if I really do to want to care about you know worst case behavior under arbitrary conditions。

 particular if I see negative edges on an exam。The right algorithm to use is Bellman Ford。

Ford is the guy who came up with this generic relaxation strategy。

 Richard Bellman was the guy who invented dynamic programming。

He called it dynamic programming because he was working in a defense department think tank， Rand。

And it was run by a general who needed everything to be practical on point。

 none of this manmby Paby blue sky research thing， and dear God， nothing involving mathematics。

So programming doesn't mean writing code， it means basically filling out a table like a program for a。

 you know， a TV station has a program that says， what plan， you remember TV。

 don't you remember televisions that like certain shows are on at certain times is really weird。😡。

But you know， at 10 a I'm going to show， you know Renan stampampy reruns and at 1030。

 I'm going to do a bunch of commercials and at 101059。

 I'm going to show one minute of bugs bunny and so on that's the program for the TV station I'm filling out a table。

 it's planning。And he called it dynamic because you who can argue with dynamic？

It's not just programming， it's dynamic programming。😡，And so he got under the general's radar。

And so here's the algorithm。Remember， forgeged generic strategy is look for tense edges and relax them。

 so the simplest thing one can think of is just look at every edge if it's tense， relax it。Am I done？

No， okay， look at every edge if it's tense relax it， so literally just for loop over the edges。

And if the edge is tense， relax it。And do that over and over again until every edge is relaxed。

There's your algorithm。嗯。Now， there's a bit of a problem with trying to analyze this algorithm because it's really unclear how many times that while loop is going to run。

Okay， so。But I。It's also not necessarily great because if there happens to be a negative cycle in the algorithm。

 this is just going to go into an infinite loop。So I want to put a little bit of defensiveness into the algorithm and the way I'm going to do that。

Is I'm going to observe。That if the main loop。Execcuts more than v minus1 times。And does any work？

There must be a negative cycle。So I can prove that there's essentially a time limit that this algorithm says if it hasn't finished by this time limit。

 it's never going to finish。But this is not something that works in general。

 you can't just take any algorithm that might go into an infinite loop and figure out， oh。

 if this doesn't finish by next Thursday， it's never going to finish。

That's part of that's equivalent to the whole thing problem， but for this particular algorithm。

 we can show that。The real work happens only in the first v minus one iterations of that average loop。

And if any more edges are tense after that。Those1 edges are part of a negative cycle。

 and I could just get， o， negative cycle， forget it。嗯。And with a little bit more work。

 you can actually construct a negative cycle。系。But one thing to see right off the bat。

Is the running time of this algorithm？I've got two nested loops。

The outer loop iterates at most v times。And the inner loop iterates at most eat times。

And inside the inner loop， I'm doing constant amount of work is the edge tense， if so。

 relax it the end。So the running time in the algorithm is pretty clear。The question is。

 why is it correct？hy does this time limit work？And I think the best way of showing that。

Is by showing you how Belman derived。This algorithm as a dynamic programming algorithm。

So it's not the only way to think about the algorithm。

 the way Edward Moore did it who was the guy who invented Brett or sorry。

 who successfully published Brettford search first。Um，You can。

 you can set it up a as an extended version of Bret first search where if you relax an edge。

 you put its head vertex back into the queue。It turns out to be equivalent。Um。

But u let's let's start with the way Bellman said it。

This is the recurrence we used when we look computed shortest pads and Dgs。

So I'm going to define distance of V。To be the length。Of the shortest path。From。S to V。And well。

 I know where the shortest path starts。But the thing that I don't know and the thing that Dicstra and other Ford based algorithms try to figure out is what's the last edge in the shortest path。

 what's the predecessor of V？In that shortest path。

And so essentially what we can observe is the distance is zero if the vertex in question is the source vertex。

 and otherwise I say， well， I don't know what the last edge in that path is。

 so I'll try all possibilities for the last edge in that path。Each one， I'll say， well。

 if I'm trying the EGUV， the candidate shortest path is the shortest path to you， plus that EGUV。

 here's the total length of that path， minimize over all choices of you。嗯。And for a DAG。

 this immediately leads to a dynamic programming algorithm， everything is great。

 it runs in linear time， we're all happy。But。If I have。And add a graph that looks like this。Then。

Distance at U or sorry distance at V depends on distance at U， which depends on distance at W。

 which depends on distance at V， which depends on distance at U， which depends on distance at W。😡。

This is still correct。As an equation。But it's no longer a recurrence because if I tried to turn this into a recursive algorithm。

In any graph that has a cycle， I'd get into an infinite recursive loop。So what Belelman said is。

If I want to turn this into。A recurrence， I need to have an additional parameter。

It always goes down when I recurse。That way I know when I'll get to the bottom。

When I get to the base cases， I can stop。And then I'll know that I don't get into any of these weird recursive loops。

And so what。Um。Belman decided。Was to take as the additional parameter。

The number of edges in the path。So I'm going to define distance less than or equal to i of V。

This is the length。Of the shortest。

![](img/adff696eb8d597a68cf19f681c72c3fb_8.png)

他。

![](img/adff696eb8d597a68cf19f681c72c3fb_10.png)

With。At most。Iye edges。From S to V。Okay。Notice the way I carefully indented things to emphasize this。

I don't mean the length of the shortest path if it happens to have less than eye edges， I mean。

 among all paths that have at most eye edges。I want the shortest one。

That isn't necessarily going to be the globally shortest path。All right。

 so a good example of this is let's consider。A graph that looks like this。Here's S， here's V。

Let me add。Sorry。诶。The shortest path from S to V in this graph with at most one edge has length 16 is that single edge going across the top。

The shortest path from S2V with at most two edges has length 14， this seven and then that seven。

The shortest path with at most three edges has length 12， five two two。

 the shortest path with at least with at most four edges is 11， it's either two， two， two。

5 or it's five， two， two，2。The shortest path from STV。Has link nine。sorryrry， two it's like 10。

 right？So as you increase I， you're allowing yourself to look at paths that are longer and longer in terms of the number of edges。

 but shorter and shorter in terms of the total length。嗯。So。

Belman came up with what economists refer to as a Bellman's equation and what we know is a recurrence。

嗯。AndSo he said， okay， if I is equal to zero， if I'm not allowed to use any edges at all。😡，Well。

 then my distance is either is zero because v is equal to S or its's infinity。

I can't get from S toV without using any edges because S and V are two different vertices。

 so there is no path from S toV， so I'll take infinity as a reasonable value for the minimum of the emptyP set。

😡，系。Otherwise， he said， okay， the shortest path with at most eye edges from S to V either uses eye edges or it doesn't。

If it doesn't use eye edges。Then the shortest path at most eye edges is equal to the shortest path with strictly less than eye edges。

If it does use eye edges， then I have a choice of what my last edge will be。😡。

And I try all possibilities for that last edge。But you'll notice again， every time I recursed。

This parameter bound the maximum number of edges that I'm allowed to use goes down。嗯。

So I've got here a two parameter recurrence。What sort of data structure might I use to memorize it？

Well， first， let me make sure that the recurrence itself kind of makes sense。Yes。Yes。

 UWV is a single edge， so that minimum， just like in the daAg recurrence at the top of the screen。

 what that's doing is saying over all possible edges，Leading into my vertex V。

Which one is the right one to choose， it's the last edge on the shortest path in DV。

With the most diers。Yeah， so I'm looking， what's the right predecessor for V？

WithWith that number of edges restriction。Okay， I've got a two parameter of recurrence。

 what do I memorize into？A 2 dD indexed by what？What are my two parameters。

 well one of them is a vertex。Okay， if I'm given a graph data structure as an explicit data structure。

 those vertices are going to be represented by integers from one to capital v。

 and so I can use that as an index into an array。And the other parameter is this I thing。

 that's going to be， again， an integer between one and V， oh， why is it going to be at most V？Why？

Do I the actual distance to V is actually equal to the distance at most capital v minus1 of V。

Why is that true？Yeah。You're getting close。But why using the word smallest here。

 what I'm actually interested in is。Why is v minus1 the largest do that I need to consider？

For the number of edges。Yes that's it exactly so if I have a if I try to use more than v minus one edges。

 let's say V is equal to five and I try to use more than four edges in a path。Well。

 the last edge has got to go somewhere that's been on the path before。Now I have a cycle。

But I know that shortest paths don't have cycles in them。Because。There's two possibilities。

 either the total length of this cycle is greater than equal to zero。

 in which case I can just throw it away。Or the total length of the cycle is negative and I'm screwed。

There are no shortest paths。Okay， so you know， this is because。Shortest pads。Have。

At most v minus one edges。嗯。So back to the question of memorization。

 if I don't have an explicit graph data structure， but say I'm doing this in some sort of pointer-based thing。

 or for example， my graph is made of internet hosts and my edges are made of connections between those internet hosts and I want to compute the shortest fastest way of getting a packet from my laptop here to my computer at home。

 which is a real thing。😡，I can't build an array with one column per computer。

But what I can do is ask each computer to keep an array of all the things that it's that it can see so what i'm actually going to do is have。

A。You know， V dot disk。From one to the。You know，Or I could have distance。呃呃呃。

So either I could just have a one dimensional array stored at every vertex。😡。

Or I can have a two dimensional array。Whichever way you want to think of it is fine。

IThink Bellman was like， yeah， let's go with a two dimensional array。

If I write that out now as a dynamic programming algorithm。

It looks like this now this is a little bit more complicated than the version of the algorithm I showed you earlier。

😡，The version algorithm I showed you earlier just had a distance value associated。

 a one real number associated with every vertex here I've got a whole one dimensional array of things associated with every vertex。

😡，But one thing I want you to notice is。In the I iteration of this last for loop where I'm doing all the real work。

 I'm only ever referring to distances at level I minus1 and at I。

So I don't really need this whole two dimensional array， I only need the two rows。

I only need like a really come from more earlier a one dimensional array and so in fact I can。

'Do a little bit of surgery with the algorithm。Hey， so。Here's。Here's the algorithm。

Any just as is written in the box？I'm going to do。Some somewhat strange surgery and eventually turned this into the original algorithm。

ok。So in the for loop。I say for every vertex。Look at its outgoing edges if theyre tense relax。

And there's a bunch of bookkeeping around it。But I don't have to look at the edges in that particular order。

I could just like initialize the distance values at the vertices and then look at all of the edges in the graph in some arbitrary order and the logic would still work out all the edges that need to be relaxed or relaxed so I can take this for loop。

And I can pull it out one level of indentation。And I don't change the essential logic of the algorithm。

 I'm allowing some more freedom in the order that I look at the edges。

 but I'm going to do all the relaxations that I need to do I'm just maybe doing them in a different order。

Then the next thing to observe is what does this algorithm do at the beginning of the I iteration。

 it takes all the I minus one level distances and copies them into the if level of the distance array。

 and then it does a bunch of comparisons against the I minus one level distances。😡，But you know。

 I can actually save myself a little bit of time if I look actually at the if level distances。

Instead of the I minus one now this might mean I relax things a little bit more eagerly than the original algorithm。

 but I'm still within the realm of Ford's relaxation strategy。

 so that's fine if I relax more edges earlier that's not going to hurt me。😡。

The distances might go down a little bit faster， but that's only going to help。Now it turns out。

 wait， why am I doing that copying？Why am I bothering to copy all that stuff， I don't need it。

 so I don't need this business。And in fact， I don't need to keep a two dimensional array at all。

And now。This is。U。The original version of Belmon Ford that I showed you earlier。Okay。

 order VE time and everything works。Correctly， so then I can。Pll that up there。And yeah。

 I shouldn't have done that。Right you could tell。Okay。😊，So the punchline is。

The way to think about the way Belman Ford works is。In the first phase of Belman Ford。

 I find all shortest paths that only have one edge。In the second phase of Belman For。

 I find all shortest pads that have two edges， the third phase I find all shortest pads that have three edges and so on and so forth。

So after v minus one phases， I found all shortest paths with at most V minus one edges。

 but that's all shortest paths。In prairie learn， there's a question about， hey。

 how would you find the shortest path with it most K edges？

By running only key phases of this algorithm。Not by running Dyixtra or any modification of Dyextra because Dykstra doesn't keep track of how many edges are in the shortest path and if you try to modify Dyktra by keeping track of that information and short circuiting the logic。

 all you're going to do is break diyextra。😡，This is a general bit of advice。Don't modify ditra。

Modify your graphs so that Dkester works。Don't modify Dykes Str so that it works on your data。

It's in principle doable， but nobody ever does it right， especially on exams。So just don't。有。

Are you to。is it fine if you modify？The part of an algorithm where。

Were going to store different kind of data。That's generally okay if you're not changing the essential logic of the algorithm。

 but you're saying when this happens。Do something else。

 so you're not so much modifying the algorithm as you are amending it。

 putting something on top of it。That that's okay as long as you do it carefully。Yeah。Yeah。

I don't think of so okay。That's Stkester's algorithm。That puts things back in the priority queue。

 that's what Dkester's algorithm does。 If it just so happens that none of the edges are negative。

 then I can prove that nothing ever gets put into the priority queue twice。

And that allows me to simplify the algorithm。But it's really the same algorithm I'm just removing dead code。

And if it's a dag， I don't want to run Dexter anyway。

 I wanted to run the topological sort thing because that doesn't have that log overhead。Okay。

Are there any questions about？😡，How Belman Ford works， why it has this running time。

I'm sorry that I do have to run after class if I think I have time on Tuesday。

 I'll show you another way of looking at Belelman For。That。

Makes it look like I're doing something on a da。Okay， thanks everybody。

 have a good weekend or see you on Tuesday。

![](img/adff696eb8d597a68cf19f681c72c3fb_12.png)