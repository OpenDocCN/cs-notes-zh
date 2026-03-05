# 伊利诺伊大学【中英⚡算法｜CS473 Fall 2022 Algorithms】 p19 P19 18 maxflow application -BV1RdBTBrEdx_p19-

![](img/af2f8f17394d92e1db52fcaf4302c194_0.png)

。

![](img/af2f8f17394d92e1db52fcaf4302c194_2.png)

呢常な先。这个。Yeah just skip。定。Okay， let's。Go ahead and get started thanks for。Walking through the rain。嗯。

One fairly important bit of logistics。So， next Monday。Is midter two？

I apologize for having to schedule the midterm。On Halloween。There will be candy。At the midterm。And。

Um。I will give one point of extra credit。Or。Sufficiently interesting costumes。嗯。

So midterm two is going to cover the material that we've seen in class since midterm one。

 so specifically homeworks four， five， six， and seven。Unless the stuff that we're going to see today。

 even though you haven't seated on the homework yet， because it's a lot easier to ask。

Accessible exam questions about the material we're going to see today than it is to ask about stuff that you saw on homework7。

So even though you're not going to have an opportunity to practice with this beforehand。

I think and history suggests that this is going to be accessible enough。That this will not be。

An unfair exam question。Thursday， there's no lecture。

 I'll do exactly what I did the Thursday before midterm one， which is a walkthrough fake exam。And so。

Thursday。There's a review session。嗯。Just like midterm one， if you need to take conflict exam。

 there'll be an opportunity to take a conflict exam on。Tuesday， November 1st。

 unless that for some reason doesn't work out。But there is a form that came up on the webp page about an hour ago to fill out to register for the conflict exam。

🎼可。Later than Friday so that I know how many people need to take the conflict exam so it can reserve enough rooms。

If for some reason you need any kind of accommodations。

 please make sure that I have any letters from Dres if you've already given me those letters from midterm one。

 I still have them， but sometimes things change in particular。

 if you need extra time or distraction free environment。

 you may want to take the test at the accommodation center。

 you should reserve that quickly because they tend to fill up。Umh you're also welcome to just take。

The conflict exam if you need extra time instead of scheduling an attack。For midterm one。

 there was a small enough number of people taking the conflict that I think it would be reasonable to do that for Dr students as well。

嗯。And oh， right。Oh。See。I mean both in the literal sense that。

There will be no problem number three on the exam， but there will be no problem like problem three。

mThat where。The most common answer is brute force。Yeah。U。ok。

Any questions other questions about the midterm otherwise the structure will be the same you can bring in a cheat sheet there will be four questions。

mNumbered。I don't know， one， five， seven and 12， you can bring in a one page cheat sheet handwritten both sides or to one single sided。

You'll have two hours。It's in the same room that midterm one was in。

I will provide a formula sheet on the back of the answer booklet with all of the like weird inequalities and a few other formulas on it。

 I would still recommend writing those onto your own sheet sheet just to get them into your fingers。

But if you don't， I will give you those as reference in the exam itself。So。Okay。So what I。

Want to talk about today and what I'll continue talking about。😡，After the midterm。

Is applications of maximum flows and minimum cuts today just maximum flows？

And so a lot of the stuff we're doing so far has been very。Abstract。Is very general， you have this。

Big network of stuff and we want to push flows through it and want to separate into the cuts the things we've been doing in the homework are very much about sort of the structure of the space of flows and how things behave when the network changes I want to try to bring this a little bit back down to Earth。

And show you ways to use maximum flows。😡，And to use flow decompositions to solve。Other。

Problems where you only need to think about those things， those other algorithms as black boxes。So。

Simpplest one。Is the so called disjoint path problem。So let's say I have a directed graph。嗯。

Another special node called S and another special node called T。嗯。

Not necessarily a dag S is not necessarily a source， T is not necessarily a sink。Um。

And I want to find。The largest number of paths that I can from S to T。

 where every edge in the graph appears in at most one path。Okay， so。嗯。Given a directed graph。

Two vertices。S andT， I want to find。The maximum number of。Addds。From S to T that don't share。嗯。

I just。So for example， I might find this path from us to tee。And this path from us to T。

 or maybe make this a little bit more interesting。These two paths are edge disjoin they both go through that vertex in the middle。

That's okay， we're allowed to go through the same vertex more than once。

But just never go through the same edge more the ones。Now I can draw lots of stories about this。

 Google wants to wander around town with their street view cars and for the sake of avoiding redundancy。

 they want to make sure that they get as many cars out on the roads as possible。

 starting at the warehouse on the west side of town has a big S on the building and they drive through town until they get to the big warehouse on the east side of town there's a big T on the building。

 but they want to make sure that any stretch of road in town。

 only one Google car drives down that so they don't get pictures they don't need。

How many Google cars can they send out？嗯。But this is really what the question is asking is how many。

Edge destroy pads can I pack into this graph？So how would I solve this problem？Yeah。Right。

 so that's exactly right。So the algorithm。Is。Asign。Papacity one。2。Every edge。Compute。Maxflow。

AndSpecifically， you know， just。Because sometimes the， the。I'll often just say maximum flow when S&T。

 you're clear from context， but let me just be careful here。Computer maximum ST flow。

 the value of the flow， now I claim is the number of disjoin paths。😡，And so。Why does this work？Well。

 if I signed a command。😡，To every edge。And other things， this implies that。Well。

 all the capacities are integers。So there is an integer maximum flow。And in fact。

 that's the flow that Ford Ferson would compute is a flow that has integer values。

 those integer values must all be between zero and one。

 so they must be either every edge must either have zero units of flow going through it or one unit of flow going through it。

The edges that have one unit of flow are the edges that。😡，Comprise the paths， constitute， yeah。

 make up the paths。U。So in particular， if I look at how many pads leave us。😡。

That's going to be equal to the number of edges that carry flow out of S。

 each of those edges carry one unit of flow。The pads are edges disjoin because well。

 if two paths went through the same edge， that would look like two units of flow。😡，U。So。

This is actually enough if all I want is the number of edge disjo paths。😡。

Actually want the pads themselves。Then I'll use the facilityffity composition。

To decompose this thing into the individual paths。嗯。His first step。We can use the off the shelf。嗯。

Ford focus on algorithm。And let's think about like what the running time of that would be。

So remember with no other specification。The most we can say about Ford Fkerson when the capacities are integers。

😡，Is every iteration I need time linear in the number of edges to find an augmenting path。

And the number of iterations is at most the value of the maximum flow。😡。

How big can the value of the maximum flow be in this case？Just。Well， okay。

 so one crude upper bound is the number of edges because each edge can be used at most once。

 but I can do slightly better than that。Out degree of S。Or if I want to be crudely。Okay。

 the min of out degree S and in degreeeg T。But I just， I want to do this。

 say this in terms of our normal graph parameters V& E。😡，The out degreegre of S is at most the。

The vertices on the other ends of those outgoing edges are distinct。So there're at most V of them。

 so I'd need order VE time now I could also get order VE time using this magic algorithm by James Orland from 2012。

😡，U but。Nobody's got time for that。😡，So it's perfectly okay on an exam to say Or's algorithm。

 order VE， move on。😡，In fact， I could。You know， if I really wanted to be。You know。

E to the one plus epsilon。And at this point， we know that you're just using it as a black box， no。

 no extra credit for using the faster algorithm that。😡，Just because it's six months young。

So off the shelf focusing is probably what you would actually implement。😡。

That already gives you order at eachtime。And the other reason why you know doing the faster max flow doesn't help you is that。

 well， I have to compute this flow decomposition and that also takes order of VE time。😡。

And that's tight。嗯。For as a black box for computing the floating composition now in this particular case。

U。You could probably devise a more efficient algorithm for decomposing this flow that would only run in order E time。

😡，Because you're tracing through you know walking through the flow， tracing out edges。

 as soon as you use an edge， you know you're never going to need it anymore。

 so maybe if you do it carefully， you could decompose the flow in order E time。

 but at this point you're doing there's a lot of details to check。😡。

And something like this say shows up on an exam， you're better off going to the next problem。Okay。

 so in the end。😊，this is。Order V time。At least using the the shelf tools。Question。有。Yeah。

So so one one way to think about the decomposition algorithm is I'll add an edge from t back to S with the flow value equal to the value of S star the number of pads now I have a circulation in this bigger graph。

I decompose the circulation into cycles， but every one of those cycles is going to include that back edge when I remove that I'm left with a path。

I can also phrase the algorithm differently。😡，Um， which is start at S。

 wander around until you either run into a place you've been before or until you get to tea。

If you see a place you've been before， throw that away。

 that's a cycle and it's not contributing to the flow， if you get to T， you've found a path arrayay。

 go back to Senttra start again。Either way， it's going to take this much time。Okay， so。你 kind of。为什么？

好。I。What do you do if the graph is undirected？Same problem。I now I give you an undirected graph。😡。

And I give you a vertex S and a vertex T， and now I want the maximum number of disjoint paths between S and T。

行。I'm not sure I understood what you mean。It direction。Right。

 so so the thing to remember if you think about。Adjacency matrices。Okay。

 the jaency matrix of a directed graph。Has a1 in row I column J if there is an edge from vertex I to vertex J。

An JCZ matrix for an undirected graph。Is symmetric if there's a one at row I column J。

 there is also a one at row J column I。😡，So I can take that symmetric adjacency matrix and just say。

h now it's a directedy graph。😡，Okay， so what that does is it replaces。Every。诶。Directed edge。

With a pair of undirected edges。Which now to solve the edges joint path problem。

 I'm going to give each of these directed edges capacity one。😡，And then run board focus and so on。

There's a small。Stly here。Which is that when I was presenting Ford Fkerson and when I was presenting。

The the flow decomposition and all those things I made a simplifying assumption that I never have edges like this。

Okay， so there are two ways to work around this one。

That was a simplifying assumption to make the presentation easier。

 it's not actually a requirement in the algorithm， it requires a little bit more bookkeeping to understand what happens in the residual graph when you already have backward edges。

😡，So if I send one unit of flow through this edge going to the right in the residual graph。

 the forward edge will have capacity zero and the backward edge will have capacity two。😡。

Instead of two backward edges with capacity one。But the other possibility。Is that I can just。

Decompose each of these edges into a path of length too。😡，Okay， so there might be other other。

I just hanging off here。Wops。😔，But now I've introduced these two new edges or two new vertices to subdivide the directed edges。

😡，Um， those vertices have exactly one in neighbor and one out neighbor。

I've doubled the number of edges I've roughly。At least doubled the number of vertices and now I can run forward forward focusing on that subdivided graph the running time is still going to be order V it's just that。

😡，啊。Well， V has gone up， so you have to do the analysis more carefully。Um。On an exam。

You would say I'm going to stop here， I'm going to run forward focus and I'm going to do the path decomposition。

It'll be fine。Um，In particular， it's possible that Ford Fguson will compute a flow that uses both of those edges。

😡，But in that case， you could maybe do a sanity check and if you ever see flow going across both of those edges。

 just remove that little cycle from the flow and that won't change anything。In terms of the paths。

Okay。So a little bit more bookkeeping， but not too bad。Um。Alright。Okay。

So now suppose I want to impose a stricter condition on the pads instead of the pads not sharing any edges。

I want to further make sure that paths don't share any vertices now these are all paths from S to T。

 so they're all going to go through S and they're all going to go through T。😡。

So when I say vertex disjoint， I mean all of the interior vertices， aside from the endpoints。

 have to be distinct。😡，So。These pads would not qualify as vertex disjoint。

 but if I took the blue path and I rerouted it down like that。😡。

Then the red and green pads would be considered vertex disjoin。

I'm going to erase this because it's going to be hard to see。When it's printed or。Exported。嗯。

So more generally what I want to think about is。Can I modify。

 suppose I want to modify the statement of the maximum flow problem？

So that I have capacities not only on the edges， but also on the vertices。Okay， so what I want is。

Vertex capacities。In addition to。嗯。The usual edge capacities。Okay， so what this means is。

We order to be feasible。The usuallyual will happen。Eddge capacity constraints。But now， in addition。

I have a new constraint， which says。That for every vertex v， the amount of flow going into V。

Is at most the capacity of that vertex？By conservation。

 this is also going to be the amount of flow going out of V。😡，Right， so。啊。

But I'll just write it in terms of incoming flow right so again。

 the usual physical metaphor that you've got pipes full of water。

There's only so much water I can push through each pipe before it explodes。😡，U。

And then at the junctions， I also have a constraint that if I try to have too much water going into this junction。

😡，The junction itself is going to explode。Okay。So。嗯。Just to give a sort of concrete example here。

Suppose I have here is a vertex with capacity three。These are all capacities。Okay。嗯。

Then the largest amount of flow that I could push through this whole system is three， so for example。

Push one unit know to flow inwards along each of these edges。

 push one out this way and push two out that way， so the numbers in red are the flow values。

There's three units in and three units out。That vertex is saturated。

 I cannot increase the flow through any of those edits。Okay。嗯。Now。什么意思？With a new graph problem。

 there's always two strategies。One of which looks more attractive。😡。

To a lot of people than the other。Great。😊，second strategy is we can change the algorithm。

The other strategy is we can change the graph。So。嗯。

I could start to think a little bit about how I would modify Ford Fkerson to deal with vertex capacities。

 I could say， okay， let me imagine that I'm going to define something called the residual graph again。

😡，Where at every edge and at every vertex I'm going to record how much more flow I can push along that edge or push into that vertex before things start to blow up so in my in my supposed residual graph So here I would have an edge going back with capacity one here Id have an edge going back with capacity one here I'd have edges going both forward and back with capacity one。

Here out with capacity two in with capacity one， out with capacity three， in with capacity two。

 and because I've used up all the residual capacity at this vertex。

I'm going to give that a residual capacity of zero。😡，Now does anybody see a problem with this？

Why is this bad？是。So you could still have overflow your capacity。嗯。Um。

 I think you're starting to get in the right direction， but let me see if somebody else has an idea。

So。What you want the residual capacity， the residual graph to represent is how can I change the flow？

😡，In a way that preserves its feasibility。So when I only had capacities on the Edwards。

I might decide， you know what， I'm going to send one more unit of flow in along this edge and。嗯。

We send one more unit of float in along this edge and out along that edge。

And if I just look at the residual capacities of the edges。

 do a capacity of one pour in the residual capacity of one going out， everything's great。

And the resulting modified flow is feasible， I now have instead of 111 on the left。

The modified flow would have02，1 coming in from the left。

 and so the amount of flow going into that vertex is still three。

But over here in the residual graph land， I pushed one more unit of flow through the vertex。😡，I。😡。

Should change the zero to a minus1。But if I pushed one more to flow， say along this red path。

going this way， so I changed that one down at the bottom to is0 and this two over year to a1 now I've actually reduced the amount of flow going into the vertex。

 but over here in residual graph land， it just looks like I pushed a unit of flow through the vertex。

😡，So there's not enough information in this thing that looks like a residual graph。😡，Beel。

Whether I'm allowed to push another unit of flow。😡，Through the vertex。

 sometimes it doesn't affect anything at all， sometimes it would overflow the vertex。

 sometimes it would actually create extra space in the vertex。😡，So the whole idea。Of residual graphs。

That doesn't work。When you have residual capacities。So no。Changing the algorithm。Not a good idea。😡。

Right。So instead。I want to change the graph。都是分。Iご。喂我。呃，对么经。开始三关。That's exactly right。

 so the idea is that I know how to deal with the situation when the edges have capacity now I have this other object that has capacity。

If I could only turn that other object into an edge。😡，Then I'd know what to do。

So that is exactly what I'm going to do I going to replace a single edge with a single vertex with capacity three with an edge。

😡，That has capacity three。All of the edges coming into the vertex are now going to be routed to the the inside of that vertex gadget。

 all of the edges coming out will be routed to come out of the outside of that gadget。

 so this little thing that I've circled in yellow here。😡，This is a gadget。

 this is exactly the same kind of thing that we do when we're dealing with NP hardness proofs。

 if you remember that from the end of 374， we muck with the input until it ceases to be an instance of problem X and turns into an instance of problem Y。

😡，8。if I students say one unit of flow here out of one， one out of two， one out of one。

Um one out of three， two out of five， what goes through that intermediate edge。

Is three units a flow out of three？And now I can build my residual graph。

And it will just have an edge。Inside inside the gadget。That represents。

I can send three more units of flow backwards through that gadget。So again this blue path。

I can augment along this， that looks like I'm augmenting here。

Notice that doesn't go through this intermediate edge that I added and so it does the right thing。

 it says I didn't push any more flow through the vertex。😡，mSimilarly。

 if I try to push one more unit of flow along this red path。Again， that will do the right thing。

 I'm pushing one unit of flow along this backwards residual edge inside the vertex gadget。😡。

That reflects reducing the amount of flow through the vertex by one。Okay， so in general。

 I'm going into replace。One vertex with capacity C with an edge with capacity C rerouting。They are。

Iner edges to one side and the outward edges to the other。And from this point on。

 I'm just dealing with floats。In the standard sense that we saw at the beginning of last week。

This transformation can be done in time proportional to the number of vertices plus the number of edges。

 it's just brute force grind out your reassigned pointers。😡，UUh。

 once I build a flow through this modified thing， I can turn it into a flow in the original graph just by copying over the flow values on the edges。

😡，I can decompose the flow through this modified graph into paths and cycles and pull them back to paths and cycles in the original graph。

😡，All of this is just bookkeeping， it's just you know writing things down the right way。

 so the translation between these two different views of the network。😡。

Is sort of linear time equivalent。Yeah。So in particular。If I want to compute。😡，嗯。Vertex。This joint。

Thats。And graph。I do exactly the same thing that I did before only now because I want the vertexes。

 the vertices to be destroyedjoin， I assign a capacity of one。😡，To every vertex。

And then I compute maximum flow and then I decompose that into paths and what that actually looks like in the end。

Is。I split every vertex into two vertices， one in and one out。😡。

I assign a capacity of one to all of the edges inside the gadgets。😡。

And you can decide whether you like one option or the other better if you want。

 you can also assign a capacity of one to all of the original edges that are between gadgets。😡。

Because after all， each path is only going to go through one edge or sorry。

 each edge is only going to have one path go through it。

But you could also assign a capacity of infinity。😡。

To all of the edges that aren't inside gadgets because it won't matter。

If two pads never share a vertex， then they also immediately can't share an edge。Right。

So in the reduction。😡，these edges would all have capacity one inside the gadgets and between gadgets。

 I would have capacity infinity。In particular， all of the edges leaving S now are rerouted to come out of S out。

😡，All of the edges going into T are rerouted to go into T in。😡，And so in this modified graph。

 I'm looking for the largest number of edges justjoin pads from S out to T in。😡，So in the end。Again。

This is order V time。表。ExWhy you need in the result， Why can't believe S exactly。

I might have edges going into S。I'm going to get them out of the way。It's better I mean， in general。

 I want the algorithm to be as simple as possible because I'm trying to explain it in 20 minutes on an exam。

 so just say do this to all vertices。😡，If you say， do I really need to do this to asents。

 you're thinking too much。Just move on。It's true that you don't really need to do the modifications on the terminals。

😡，It doesn't hurt。Okay。😊，All right。So that's one。Nice family of examples。Now。

 let me see if we're paying attention， suppose I want。A set of paths that's as large as possible。

With the following constraints。At most two of the paths can go through any edge。

And most three of the pads can go through any vertex。😡，What would I do？26。Yeah。😊，It's the other half。

Most two paths through most two paths through any edge so。

It set the capacities of every edge to be two。So now you can either think of that as。

Assign the edges capacity2 and the vertices capacity 3。

 run the vertex disjoint path algorithm from there， or you could say， well。

 do this translation from vertices to edges。😡，And then give every intra gadget edge capacity three and every inter gadget edge capacity two now run for focus on and do floating composition again。

 the running time is still going to be V times3。😡，Okay。😊，So more generally。

Find the maximum number of pads。Where at most a。Through。Each edge。And at most B。Through each。Vertex。

And as long as A and B are constants， this is going to be the Eton。Again。

 just by doing the reduction writing in the capacities in the right place and running off the shelf ford Volkerson and off the shelf pathy composition yeah back to the undirected graph yeah。

M米。Not satisfied but it feels like then you can have pass where one goes through and one way everyone one goes through the same the other way okay so this is a very good point so if we go back to the undirected case for edge disjoint。

I decomposed every undirected edge into two directed edges that are in opposite directions now I run Ford Flkkerson。

And the objection is， wait a minute in the flow that Foson computes。

 it's possible that one in of flow will go across the edge from left to right。

And one unit of flow will also go across the edge in the opposite direction from right to left。

And so。As undirected paths， these are no longer as disjoint。喂。😡。

If I have flow going through both of those edges， I can just erase the flow going through both of those edges。

 I've removed a little cycle from my flow。😡，I've not changed the value of my flow。And therefore。

 I have not changed the number of paths that make up my flow。😡，So if， in fact。

 Ford Fguerson does give you these little cycles， you could just erase them。😡。

It will have no effect on the value of the flow in the end。

 it will have no effect on the number of paths you get at the end。

 it does have an interesting effect on the structure of the paths。😡，Because。

What you' don't expect is soll just draw an example like this。

Instead of having one path going through like that。And another path going through like that。

After you erase the flow through that little cycle， you now have one path going like this。

And the other path going like that。嗯。Okay， that's fine。That answer your question， okay。All right。呃不。

So let me switch to a different。嗯。A different application。This is a bipartite graph。

Lipartite means literally having two parts。There's the part on the left and the part on the right。

So vertices in the same part。don't have edges between them。

 every edge connects a vertex in one part and a vertex in the other part。

Let me warn you a little bit about language here。这。Doug West。

 who's an amazing graph theory researcher who's on the faculty here at Illinois for three decades before he recently retired。

 is like you， the world's authority on graph theory or one of them。Um， he's u。

He's been working on a book。😡，For 30 years， no， he's not Donald Canth in disguise。

 the art of combinatorics is currently about this thick。Like like。Stacked up paper that thick。

And he keeps in the printouts when he prints it out。

 he always prints two logical pages per side of piece of paper so it。It's a big book。U。

But he noticed that in the literature。People were using different words。To refer to。

What are there two of in a bipartite graph？😡，So one way that you can think about bipartheite is it's possible to color some of the vertices red and some of the vertices blue so that every edge has one red endpoint and one blue endpoint。

😡，So this has to do with how many colors do you need to color the graph。

 and so apartheid is the same as two colorable。😡，And so some people were referring to the sides of bipartite graph as color classes。

嗯。After doing a poll。Doug finally settled on the official term。Heartite set。

Which makes the baby Jesus weep。嗯。Art。The word is part， bipartheid having two parts。

There's the left part and the right part。😡，Okay， but I I will point out if you read Wikipedia。

 probably says something about apartheid sets。What is apartheid set， it's a set that's part like。😡。

Yeah， I don't know， the etymology doesn't make sense。

 but I insist that it's perfectly acceptable to call this。You know。

The two things parts and in particular， whenever you partition a set。

That means you've subdividideed into disjoint subgraph or subsets that cover the whole thing。

 the union is the whole set， the intersection of any two is empty。😡。

Those component sets of your partition are parts。😡，诶 not。Cartite sets or something。Anyway。Um。

 I will die on this hill。嗯。So I've got a bipartite graph。

 Now I've chosen a subset of the edges in red。The subset is called a matching。

 a matching is a subset of edges so that each vertex touches at most one of them。😡。

So it doesn't necessarily mean every vertex touches an edge so this vertex here。

Is't connected to any of the red edges， that's fine， these are unmatched vertices。But in general。

 you know。The no two edges in the matching share and endpoint。😡，All right。

 and so the question now is。Given a bipartid graph。Find。A。Maximum。Matching。Which means。

Aimum number of edges。Kow to share。A projects。是。Yes。Hi。对。Right。保月。没有。啊，好。嗯。吓。😮，要审。The气啊。Okay。

 that's very， very close。So the the basic graph structure is exactly right。

 so I'm going to have edges I'm going to create I'm going to add a source。

And I'm going to have edges from the source to every node in the left part。I'm going to add target。

And I'm going to add edges from every node on the right part to the target。😡，The interior。Edges。

 I'm all going to orient from left to right。😡，Now， what am I looking for in this graph？not。

Vertex disjoin pads。Right， so that there's the there's the there's the reduction from the the。嗯。呃。

Further up。So move that up so we can actually see it on the same screen。嗯。

So I added a source on the left。I had a target on the right。

 I directed all the edges from left to right， and now I want vertex disjoint pads from left to right。

😡，Because the I want vertex disjoint because I want to make sure that no two edges in the middle land at the same vertex are come from the same vertex now in this particular case。

 vertex disjoin and edge disjoin are the same。😡，Because every vertex on the left has in degree 1。😡。

So if I multiple pads going I have multiple paths going through this vertex on the left。

 if and only if I have multiple paths going through this edge coming from the source。😡，Likewise。

 I have multiple pads going through the vertex on the right。

 if and only if I have multiple pads going through the edge from that vertex T。😡。

So once I've built this graph。At this point， I can say everybody gets capacity one， so I actually。

 I think you were right。You said capacity one on the left and right edges。

And capacity infinity in the middle， yes， that was exactly right， I'm sorry。

So if you do infinity on both sides and one in the middle。嗯。Then it's you'll actually and。

You might actually end up pushing more flow through the graph。😡，So if I added， for example， this。

That's not one。How would I do this？是。Yeah， it might actually still work。

What I would worry about is that you would do， you add another path like this。But if you can do that。

 then they'll。Yeah， so if the sides are infinity and the inside is one。

 then I could add one more path of flow through this network。Yeah。Okay， so in general。

 what this means is I'm going to set all of these to have capacity one。

 all of those to have capacity one and well you know one or infinity or。Squared of 17。

 anything larger than one will be fine for the things in the middle。It a stupid question。

 Can this somehow be connected with the members。Can this be connected to min cuts？

So the answer is yes。嗯。Now I'm not going to be able to improvise the details。

 so forgive me I'll just say what the connection is without explaining why。

A minimum cut in this graph。So let's see。Might look something like this。Sorry。

 let's see if I can do this。Well， let's just say a minimum cut that looks something like that。

 it's going to have some some vertices on the left on the S side。

 some vertices of S on the right side， some vertices of T on the left and right side。

So the thing that this actually corresponds to in the original bipartite graph is a vertex cover。

It's a subset of the vertices such that every edge touches at least one of the chosen vertices。😡。

And so there's something called Hall's theorem that says the size of the largest matching in a bipartite graph。

Is equal to the size of the smallest vertex cover in a bipartite graph。

Hall proved this about 20 years before Foren Ferson， but it's an avatar of the Max women cut theorem。

mNext week。We will see another example of doing cuts in this kind of thing。

 but I'm just not prepared to talk about it right away。Yeah， so actually。

The capacities to the infinity like suggested and then we find vortex destroyjo parts that might still worry。

Oh right， so another way we could imagine doing this is assign capacity infinity to all of the edges。

And capacity one to every vertex。What this will end up doing。Well。

 subdivide the vertices into little edges， so that'll add a little gadget here。

That only has one edge into it and one edge out。And so it really doesn't substantially change the graph that you're giving as you're doubling the number of additional edges it's still correct it still gives you the right asttic running time。

 it's a little more complicated than necessary。Okay。So。Add source。As。

Edges from S to everything on the left。Add a target C。Add edges。From everything on the right to T。

Direct all the interior edges from left to right， assign all the edges capacity one。

And then now Max flow。We get the the。One way I can imagine doing this is I compute maximum flow。

 I decompose the flow into pads， that gives me this picture over here on the right。

Where the pads are all outlined in red， but then I ignore everything that I added and I just look at the edges in the middle。

Another way of doing that is。Can compute an integer Maxflow。

Which is what For focusingon normally does。And then just look at which edges between the left and right parts have flow value one。

😡，Those are the edges that the matching and the ones that flow out you zero the ones that are not in the match。

So I don't need to bother with the。嗯。Mach。Okay。So we know how to do this in order of eaten time。

Again。嗯。But I think one thing that is。Sort of useful to think about。😡，Is。

I can imagine running Ford Fkson on this updated graph。I'm always maintaining an integer flow。

 now all my edges have capacity one， so that means my residual graph。

Has for every edge in this network， either that edge or its reverse。😡。

And the capacity of every edge of the residual graph is always exactly one。嗯。

So I can actually interpret the behavior。Of Ford Fson directly in terms of the bipartite graph。

And that gives another way of looking at how the graph algorithm proceeds that you is enlightening to think about helpful to think about because it may give you more intuition about how For focuserson works。

 but it also gives more intuition if later in the semester after midterm two。

 we might want to do other more interesting things with matchings。😡。

So I want you to sort of think about the following and simple example。对，就是。啊。In that graph。Now。

 first， is that a maximum matching？No。This is a bigger one that just uses the horizontal edgeges。嗯。

But let's think a little bit about how I would imagine finding。

Discovering that this is not a maximum matching right so the way the reduction would work。

Is I have edges going like this。In my phone network。How did I get a dashed line？That's。

Rather incredible， I mean， there is an option to， you know draw that on purpose。

But somehow I managed to get it anyway。系。All right。So in my flow。

 I'm going to have one unit of flow going like this。

 and I'm going to have another unit of flow going like that。So in my residual graph。

 these edges are all going to be reversed。So in my。

 I'll draw these in red so that it's more clear that they're reversed。

And now what I would look for in Ford Fererson。Is a path from S to T in this residual graph。

So what does that path look like where there's only one edge out of Ss。

 there's only one edge out of that， there's only one edge out of that。嗯。Yeah。

 so I don't know at this point， maybe I'll just exag like this that that thing that I've outlined in blue。

 that's an augmenting path in my residual graph。And I'll push one unit of flow through all those edges that has the effect of reversing a each of those edges in the residual graph if it was forward before I pushed a unit of flow forward and made it backwards。

 it was backward before I pushed a unit of flow backwards and turns of forwards so this is an augmenting path。

Now， the way that shows up in my original。😡，Bypartite graph is as an alternating path。So I start。

 I look at the augmented path and just look out what goes on in the middle part here。😡。

I saw on the left。I follow an edge that's not in the matching to the right。😡。

Then I follow an edge that isn't the matching to the left。😡。

Then I follow an edge that's not in the matching to the right。

Then I follow an edge that is't the matching to the left。

And eventually I end with an edge going to the right that's not in the matching。😡。

And that's the end of my alternating path。And then the way I would update。

The matching is I would replace all of the red edges that were in the matching in the alternating path with all of the blue edges and the alternating path that we not matching。

😡，In other words， I find an alternating path and then I take its exclusive or with the matching。😡，系。

And so if I run this algorithm on the example。Right。I get something that looks like this。

 I sort of jumped into the middle because at the beginning the algorithm is kind of boring。

 so after the third iteration of my algorithm， I found three independent edges。😡。

Every time I do this alternating path thing， I'm increasing the size of my matching by one。Okay。

 so starting over here at the top left， I found these three up to the third iteration。

In the full iteration， I find this new alternating path。

And then I replace all of the red edges in this alternating path with the black edges。

 and that changes this matching with three edges to this matching as's four edges。😡，And again。

I find an alternating path。Starting on the left， right left， right。

 that changes the matching with four into a matching with five。

 then I find another alternating path I think this one has length seven。

 but when I do the exclusive or， I change that set of five edges into that edge of the collection of six edges。

On the right。And if I did things correctly， then at this point， that is， in fact， a maximum match。

Okay， so the I。It's like this。Excellent matching that's my biproduct graph G。

My set of edges is a fee。有。There is。And。Alternating paths。Let's call that path， well。

 let's say while there's an alternating path in G， is any alternating path。

And then M gets M exclusive orp。So。😡，I don't need to explicitly maintain。😡，residual graphs。

The only thing I need to remember when I'm looking for these alternating pads is to treat all matching edges as though they're oriented from right to left and treat all non matching edges as though they're directed from left to right。

😡，嗯。Um， so。Finding a path， finding an alternating path。Well， how would you actually implement that？

Yeah。I mean， one way to do it is to you know， run whatever first search from each node on the left and see if it marks any node on the right。

 but without an outgoing edge。😡，嗯。Honestly， the way I would do it is。

I would temporarily add a source。And the sink。But I don't really need to modify my general purpose graph data structure to do this。

 I could just write the algorithm in a way that pretends that there's a source over here and so if I were doing Bret first search for example。

 I'd just do a four loop over the edges the vertices on the right。😡。

And pretends that there's a target edge over there on the right。U。诶。

With the edges pointing in the right direction， so actually do need to be a little bit careful here。

 I would not have an edge going into Hill text on the left that is part of the matching。

And I would not have an edge coming out of any vertex on the right。That is part of the mansion。

So basically， I'm building the parts of the residual graph that aren't reversed。😡，But。😡。

Bake that into the data structure。Write it out explicitly， in the end， the algorithm。

 no matter how you implement， it's going to have the same running time。Um，W whichch is。

Finding any alternating path that's going to take time proportional to the。Well。

 let's be careful here because。Let's just say E plus V。

And then doing this is going to take time order V。And then the number of iterations。Is going to be。嗯。

Ororder V because every time you iterate， you're increasing the number of matched edges by one and you because each matched edge most one matched edge touches each vertex。

 the number of matched edges can never be more than the number of vertices。😡，Yeah。

So the overall running time here is。V squared plus EZ。

 and I can ignore the v squared part if I know that the input graph happens to be connected。😡，系。

Now this is one。嗯。Just a couple of final comments about this。

There are several different ways of thinking about the same algorithm here。😡。

I can think of finding this matching as looking for alternating pads and I can use the structure of the alternating pads to go。

 yeah， it's an EV time。Or I can think about this as reducing to a vertex disjoin path problem。

 which then reduces to an edge disjoint path problem， which then reduces to Ford focus on problem。

But in each of those cases， I'm reducing basically opening one black box and finding another black box inside it。

Um， and ultimately， you could say， oh， I remember Ford Fguson is just augmenting pad。

 so I'll do that。😡，Any of these ways of thinking about the algorithm is fine， it's all correct。

 it's all morally equivalent， but different ways of looking at the same algorithm expose different structure and provide different intuition。

😡，And this， I think is one of the most powerful things about this body of algorithms is that there are multiple ways of thinking of the same algorithm。

So you can approach things based on the intuition that fits。😡，Your own comfort levels。

 and it might be different from somebody else， but that's fine。Right。The downside of this is。

The the upside of this is you've got a lot of freedom to choose how you think about things the downside of this is you've got a lot of freedom to think how you choose to think about things and that freedom can be very uncomfortable if you're used to。

This has been apanning tree。And it's a minimum fanning tree and I'm going to think about it as a minimum fanning tree there's really kind of only one way to do that or this is diyktra there's a wavefront there's a priority queue that's the way it is。

Right， here。Because there are multiple ways of thinking about it。

 it can sometimes feel a bit slippery。😡，You're never really grasping onto any one way of doing it。嗯。

What I'd recommend is play with a couple of different ways， but commit。

At least for a few minutes at a time， I'm going to think about it this way。And if that works。

 stick with it。But if you find yourself getting confused or lost， say， okay。

 I got to put this problem down for 10 minutes and when you come back。

Think about it a different way and see if that intuition is more helpful。嗯。嗯。

The last thing that I want to say is just some historical notes about this。啊。This。

Nottion of alternating paths。😡，This was published by Bears in 1957 in。

What is usually thought of as the first graph theoryory textbook。

But he had come up with it in papers and talks before then。

 so it predates the alternating path thing predates Ford Volkerson again。But in。啊。

It's older than that。So call Gustav Jacobbe。Was one of the people that we have to blame for the modern theory of differential equations。

😡，Really， he was a cool guy。But in particular， if you have a system of differential equations and you want to know something about the structure。

 one of the problems that comes up。😡，Is the following， I have a matrix of numbers。Oh wait。

 we didn't have matrices in 1836。 I have a rectangular table of numbers。

I want to permute the rows and columns of that table。😡。

And maximize the sum the values along the main diagonal。诶。拜。千。😔，OhComute。Rs and columns。😔。

Let's so there's all positive。Along。But I don't。This is exactly the same as。

I'm given an end by N bipartite graph。😡，Where the edges represent non zero entries in this matrix or or the the。

Positive entries in the matrix are represented by edges。

And I want to know if there is a perfect matching。Meaning a matching of size n。

 every vertex is touching exactly one matching edge。And so Jacobbe writes out this algorithm。

Mind you， we didn't have algorithms in 1836。😡，He describes the algorithm in what might be。😡。

Might in modern terms be referred to as pseudocode， but we didn't have pseudocode in 1836。😡。

So it's actually written in narrative weight， not English， Latin。Sex was written in narrative Latin。

With examples。So he actually shows an example that looks the only thing that makes it not look like a page straight out of an algorithm's textbook is that there are no pictures of the graph。

😡，Next to it， but he actually shows here's the table and then you do this alternating thing going back between rows and columns to do some swaps。

😡，And then you get this new table and you do some alternating thing alternating between rows and columns and then you get this new table。

 and look I can't find an alternating thing in there anymore， I've got the final table。Um。

 it's really startling， even though it's written in Latin。Even though it talks about。

Square arrays of numbers。It's remarkably understandable and it's that algorithm。😡，Actually。

 it's even more general than that algorithm。U， so yeah， the stuff is is old。And for。啊。

As my son would say it， that makes brain go better。Guessing there was also no concept of run。No。

 there was no concept of a running time， and this is the amazing thing is that Jacobbe described a polynomial time algorithm for analyzing the degree of a set of different multivariable differential equations。

😡，Um， I don't know why this makes me happy， but it does。Because I'm a nerd that's why okay。

 we're done， thanks everybody， I'm happy to answer questions up front。

 if not hopefully I'll see some of you in office hours or in class on Thursday。

So earlier you said we don't have to compute the residual。

 but it looks like we're competing residual by having a graph going backwards。



![](img/af2f8f17394d92e1db52fcaf4302c194_4.png)