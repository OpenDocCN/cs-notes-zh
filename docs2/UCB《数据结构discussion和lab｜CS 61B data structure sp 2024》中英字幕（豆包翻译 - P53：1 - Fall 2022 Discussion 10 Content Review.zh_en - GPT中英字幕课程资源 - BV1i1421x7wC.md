# UCB《数据结构discussion和lab｜CS 61B data structure sp 2024》中英字幕（豆包翻译 - P53：1 - Fall 2022 Discussion 10 Content Review.zh_en - GPT中英字幕课程资源 - BV1i1421x7wC

Okay， hi everyone， this is C61 B discussion 10， and in this video I'll be going over some content review for shortest paths and minimum spanning trees。



![](img/799e6efd5d8d2d119b1f8b515153ebb9_1.png)

So for this week we have a project two workday in lab so you don't have a lab assignment you're just going to work on project two and if you need help you can show up to lab and we'll help you out and then project2 A is do Friday 1028 so that's the upcoming Friday and。

The Min semester survey is due Tuesday at 1025， please make sure you fill that out。



![](img/799e6efd5d8d2d119b1f8b515153ebb9_3.png)

Okay， so for the content review， the first thing we're going to talk about is Dxter's algorithm now Dxter's algorithm is a pathfin algorithm and the problem that we're trying to solve there is basically like if I have some source where text a。

 this is my source。And I want to find the shortest path from the source to every other vertex in my graph so every other node in my graph right now for this example my edge weights are just one because basically my cost of traversing over an edge is just going to be like one edge at a time right so like if I go from a to B I know I'm traversing exactly one edge if I want to go from a to E。

 I know like the shortest path would be traversing two edges as opposed to this alternate path which is going to go through Cf D B and then E right so the idea here is if I want to go from a to E。

 we want to find the path that's the shortest so basically jump from a to B and then from B to B because that's the only like short path in this graph from A to E right？

Now we learned that if we just use a breath first search。

 that's basically going to visit vertices from a， which is my source vertex in order of the number of edges I have to take to get to that node。

 so if I do like a breath or search starting from A。Right， so if I do like Bfs starting。仲诶。

Now I will first visit a because a is zero edges away from itself and then I'll visit one of B or C based on my tie breaking condition because they're both one edge away and then I can visit one of F and E right because there are both two edges away from a now here I know that basically in the order I visit the vertices that's going to be my shortest path based on the number of edges I take right so that's only valuable when there are no edge weights and my only cost is basically taking an edge in the first place so BFS would solve this problem in this scenario but what if my edges were weighted right so that's what we're going to see in the next slide。



![](img/799e6efd5d8d2d119b1f8b515153ebb9_5.png)

What if my graph actually looked like this where I have this new cost associated with taking particular edges so sometimes I like taking an edge let's say from going from a to C as opposed to like going from a to B using this edge like using a cost of seven is worse than using a cost of one right so now here it's a little different in that now my cost for taking the same edges from a to E is going to be7 plus2 basically the sum of all the edges that I have to take and here I'll get a cost of nine。

Vers says if I take this path， I'll get one plus two plus one plus one plus two。

 which is going to be about seven， right？Now， if I use。

An algorithm that takes care of these edge weights， then my shortest paths will change right。

 this will be my new shortest path from A to E， right。

So now that's the idea behind using like a pathfintting algorithm and basically one of our algorithms is known as diyke stresss。

 right？

![](img/799e6efd5d8d2d119b1f8b515153ebb9_7.png)

So what diyster does。Is。It finds the shortest path from one node to every other node in the graph。

 basically what our problem is。And we use a priority queue that sources vertices based on their distance from the root node and there's this algorithm here。

 if you notice on the screen we have like a bunch of steps but what I'm going to do is I'm just going to demo it and then you can read it over the steps on your own time to make sense of this。



![](img/799e6efd5d8d2d119b1f8b515153ebb9_9.png)

![](img/799e6efd5d8d2d119b1f8b515153ebb9_10.png)

O。Now what happens in the first step of di straws is obviously we need a source node right we want to be able to tell where we're starting from。

 so let's say for this example。This is my source node。系。

Cool now when we start at diextras another like initial condition that we have is like the source node is zero distance away from itself right so that's what we're going initialize it as and by default every other node in this entire graph is going to be at infinite distance away from the source right because we haven't really explored anything we're not really looking at the entire graph in the first place we're just going to initialize everything the infinity and then slowly as the executor algorithm will be updating these distances okay。

Cool。So now I'm going to maintain a priority queue of nodes right now my priority queue is going to be sorted by the distance from the source node to the node that I currently have in the queue right by default a is at distance zero so I'll put it at the front and then every other node B C。

 D E and F。These are all at infinity。So my priority Q is going to put them underneath a right if it's a min heap based on the distance。

 then a is going to be the root node， right？So the idea behind using this priority queue is we visit the nodes in order of this of their distance from the sourcepart right now all we need to do is basically。



![](img/799e6efd5d8d2d119b1f8b515153ebb9_12.png)

The first step is pop the node from the top of the queue。

which is going to be the current node so i'm going to do exactly that I'm going to pop the node from the top of the queue which is this right here and basically this is the node that I'm going to visit right now my priority queue is left with the other nodes and these are all still infinity。



![](img/799e6efd5d8d2d119b1f8b515153ebb9_14.png)

![](img/799e6efd5d8d2d119b1f8b515153ebb9_15.png)

But right now I'm going to explore things starting from A， right？So when I pop the node。

 basically that means that I have visited a and I know the shortest path to a right the moment we pop something off the queue in this algorithm。

 we know the shortest path to that node okay？Cool， and now we know that is at a distance of zero。

Once we pop this node， we're going to look at the neighbors of this node that we just popped off right now A has two neighbors B and C right B is at a distance of7 from a and C is at a distance of one from a right。



![](img/799e6efd5d8d2d119b1f8b515153ebb9_17.png)

So now that I know that B， if we take this edge from a is going to be at a distance of 7。

 we know that7 is less than the current distancer that I have stored。

 which means that I can change this to be 7。If I basically want to go from a to B and I just traverse this edge。

 I'm going to take a cost of seven overall， which was less than my initial cost of B。

 which was infinity so I update this to be seven。Okay。Cool。

 I do this I do the exact same things for C basically sees out infinity right now。

 but I know that if I take this edge， it'll be at a distance of one， so I'm going to do that as well。

Okay。Great so now my priority queue will sort itself because I updated my distances so now B will be at a distance of seven C will be at a distance of one which means C would come somewhere here in the queue I'm just like ordering them an increasing distance of course it's actually a min heat but i'm not going to draw the entire structure out the idea is like you care about the next minimum so i'm just going to put that at the very front of the queue right？

And these are all of infinity。

![](img/799e6efd5d8d2d119b1f8b515153ebb9_19.png)

Okay， so now。The next node that I'll be visiting is going to be the next minimum in the prior8 Q。

 right， which I see is C， right， I just popped that note off again。



![](img/799e6efd5d8d2d119b1f8b515153ebb9_21.png)

So I take that out。Now that I've popped it off， I know that this edge。

Will be required in my priority view right I first I initially explored C to be visited through a so I go to a which is my starting note I traverse this edge to get to C and now that I've popped it off I know that C C has the shortest distance from a that that I've now found right the moment you pop something off of the Q you have the shortest path to that node okay。

So C is also going to get highlighted。And this edge is officially added to my priority queue because I explored Z from A。

 right？Okay。Now， I look at C's neighbors the same way I looked at A's neighbors before。

 C has only one neighbor。 F， right， F is currently at a distance of infinity。

 But if I want to go from a to F， right？ I know that C is at a distance of one。

Now if C is at a distance of one and this edge has a weight of two。

 F must be at a distance of three right at least if I go to F via C right， so if I go to f via C。

 I'll get a distance of three， which is definitely less than infinity。

 which means that I can update my distance here。And。

My priority queue will also sort itself right so now f becomes3 and I'll put that at the very beginning of the Q because that's the next minimum and D and E are still infinity right so that they did not change because I only explore onen at a time。

Okay。Now again， I'll do the same thing where I pop the next node that has the minimum distance from the source。

 so I pop f off right because that's the next minimum and。

I can just literally take it out and highlight it。Now I know that when I explored F at the very end。

 this distance of three came to be known through this edge via C。

 so I'll have to include this edge in my distr solution。Right。Okay。

 so now again I do the exact same thing where I look at F's neighbors right now F has only one neighbor again。

 which is D and D is at a distance of infinity， but if I look at F's distance from the source three right？

And I look at the edge here between F and D。 I know that D。If I if I go to D from a via F。

 we'll be at a distance of whoops。It'll be at a distance of three plus one right because the distance to f is three and D is just one cost away from F right now that's four。

Which is definitely less than infinity， so I'll update this distance as well。

So this is going to be my new distance， which is four and my priority queue will again sort itself out。

Right by sorting itself， I just mean like the minimum will pop up at the very beginning and we don't care about the rest of them right we can just represent them in any order for now as long as we have as long as we are able to keep track of the next minimum。



![](img/799e6efd5d8d2d119b1f8b515153ebb9_23.png)

Okay。So now I know that D is the next minimum and I've explored all of F's neighbors。

 so I'm done with all three of these nodes， the next thing to pop from the Q will be D because that's the next minimum。

 so I will literally remove it from the Q。And I will highlight it。Right。

Now I looked at D from F at the very end right where I found like oh D was out of this of4 and not infinity。

 so this edge is very important to me and I will highlight that in my di stress solution as well。O。

Cool， now D has one more neighborler， right， which is B。 Now I notice that if I got to D from a。

 right， I'll be using a cost of four。 And if I just traverse this one more edge。



![](img/799e6efd5d8d2d119b1f8b515153ebb9_25.png)

From D to B， I'll just add one more to my cost， which will give me a cost of5 whoops。Now。

 if it gives me a cost of five， I know that that's less than seven。

 which means B now has an updated cost。Of fire。So I'll update that and initially I'd explore D from A via this edge。

 but now if I end up including B later on， I'll be using this edge right because that's the last node that Id D from explored B from and it give me a new minimum value for the distance。

Right， so I will update this here as well。And。Now my priority queue will look something like this right now the pre for B used to be a。

But now it's going to be D。Right。So this is the previous node that it will come from that basically tells us which edge to include when we pop something off of the queue。



![](img/799e6efd5d8d2d119b1f8b515153ebb9_27.png)

Okay。So the next thing to pop off the Q is of course， going to be B again， right。

 because that's the next minimum， so if I pop it off。系得。And I noticed that， okay。

 B was at a distance of five， the previous node to visit from B was D。

 this edge will be includedd and B itself can be highlighted now once I pop something off again。

 that means I found its shortest path from the source， right？



![](img/799e6efd5d8d2d119b1f8b515153ebb9_29.png)

![](img/799e6efd5d8d2d119b1f8b515153ebb9_30.png)

B has one neighbor which is E right and if I take this edge from B to E I'll be traversing a total of5 plus2 which is seven and that's less than E's current distance which was infinity right so now basically I will update this distance。

To be seven。And my priority queue will also。Update E to be at a distance of 7 from a。

Through B right so that's the previous node that I'll visit before E I'll just keep track of it so I know which add to include there's only one edge in this case。

 but sometimes there are multiple edges and we want to keep track of like which node was the closest right Okay again the last node to remove from the Q is just going to be E itself。



![](img/799e6efd5d8d2d119b1f8b515153ebb9_32.png)

So I'll just remove it like that。Highlight this。The S that I have to include is going to be。E and B。

 right， because I know that E's previous pointer was a B， so I will just highlight this here。

And this is going to be my dietary resolution。

![](img/799e6efd5d8d2d119b1f8b515153ebb9_34.png)

， this is basically telling me。If I ask no stretch he。

How many steps do I have to or how much cost will it be to go from a to D right now if I want to go from a to D I already have a path based on the edges right and I know the exact distance to D as well so that's how dis works right we keep track of a priority queue we pop nodes off based on their distance from the source and if we then explore their neighbors and the neighbors have a new updated distance that that's smaller than what it used to be we'll update that distance as well right so that's the idea。



![](img/799e6efd5d8d2d119b1f8b515153ebb9_36.png)

Okay， all of this is written in these steps here， feel free to read them on your own time and execute this entire algorithm。

 and I'm sure you'll get the same answer as well。Okay。

A star is basically a variant or like something to add on on top of ditras in an effort to kind of try to make distrs converge a little early on the difference between a star and dixtres here is that a star will find the shortest path from one note to another specific note in the graph so this is key right。



![](img/799e6efd5d8d2d119b1f8b515153ebb9_38.png)

![](img/799e6efd5d8d2d119b1f8b515153ebb9_39.png)

Dextras was finding the shortest distance to every other node in the graph。

 but a star is finding it through a specific node right now this gives us an added advantage because we only have to worry about one node right one source node and one goldm right now in a star we use this thing called a heuristic which is basically like a guess value。



![](img/799e6efd5d8d2d119b1f8b515153ebb9_41.png)

For a vertex is distance from the goal okay so if I have like a heuristic value of one here we'll put that in bracket we can also give you a table that represents the heuristic basically this one represents that our guess value。



![](img/799e6efd5d8d2d119b1f8b515153ebb9_43.png)

![](img/799e6efd5d8d2d119b1f8b515153ebb9_44.png)

Of the distance to the goal which is E in this case from B is going to be one right now you'll be like oh wait no we just take a we just take this one edge two that's a weight of two and then that's actually the value but the idea here is that you don't know all the edge weights at the same time in a really big graph right so you basically try to use some guess values in order to encourage ditras if you run ditras based on the heuristic to be able to converge faster sometimes it may not even like converge to the correct solution but if our heuristic is a good heuristic if we guess well we might we might arrive at an answer a little quicker。

Right so here six here means that our guess for the distance to e from a is going to be six right and then four here means that the distance to E from C is going to be four and so on。

 right？Now， this is executed in the exact same way as distrs。



![](img/799e6efd5d8d2d119b1f8b515153ebb9_46.png)

The only difference is that this distance。We'll get some of the distance up to the node that we're currently visiting and our guess from how far away the goal node is right so if I initially see like hole。



![](img/799e6efd5d8d2d119b1f8b515153ebb9_48.png)

I am at a right initially I'll know like a is at a distance of zero because we start from a right so a is at a distance from zero from a。

Now if I explore A's edges， right， instead of initially saying， oh。

B is at a distance of zero plus seven right that was like what I did here where like initially I looked at this edge from a and I was like okay。

 you know B， if we if we take this edge to B from a we'll have a distance of setting。



![](img/799e6efd5d8d2d119b1f8b515153ebb9_50.png)

![](img/799e6efd5d8d2d119b1f8b515153ebb9_51.png)

Here we'll basically add our heuristic value on top of the distance that we had in distr right so here my distance would be something like this node this edge wait plus the heuristic value this is going to be my new distance right in a way I'm trying to basically discourage my algorithm to go to B from a right because it's already taking a very heavy edge right and then I'm also adding a new edge rate。



![](img/799e6efd5d8d2d119b1f8b515153ebb9_53.png)

![](img/799e6efd5d8d2d119b1f8b515153ebb9_54.png)

Perciia in this case is basically going to be one plus four as my new distance， right？



![](img/799e6efd5d8d2d119b1f8b515153ebb9_56.png)

And that's what I'll sort off of right initiallynitially I was just short sorting off of to the exact distances like B happened to be five here。

 but now we'll sort based on the exact distance plus the heuristic value but everything else is executed the same way as I just did in the previous example so I'm not going to go too deep into how this is executed we'll see a question and discussion anyway so I'll go over it then but the idea is that you'll add a heuristic value on top of the distance that you've explored so far right the heuristic is supposed to make a star kind of。



![](img/799e6efd5d8d2d119b1f8b515153ebb9_58.png)

![](img/799e6efd5d8d2d119b1f8b515153ebb9_59.png)

![](img/799e6efd5d8d2d119b1f8b515153ebb9_60.png)

Think of a faster way to approach the gold Knight right so it's kind of trying to encourage a star to converge faster than ditrus。



![](img/799e6efd5d8d2d119b1f8b515153ebb9_62.png)

Okay。Cool and as a very important note here， the heuristic may not always be very good and might lead us down a path that is in the shortest right so it does not have to be good maybe if I put C to have a C to have a heuristic of like 10 million if my heuristic was really bad。

Right then it may not be visiting C at all right like if if there were other edges and stuff as well。

 but the idea again is like。You just try to give it a guest value to be able to get to the goal note faster。



![](img/799e6efd5d8d2d119b1f8b515153ebb9_64.png)

Okay。Cool。Coming to minimum spanning trees。So a minimum spanning tree is basically a set of edges that connect all the nodes in the graph while minimizing the total edge rate what does this mean so if I have this graph right here we see a bunch of nodes and a bunch of edges in this entire thing right now my problem here is I want to basically have a tree of all of these nodes。



![](img/799e6efd5d8d2d119b1f8b515153ebb9_66.png)

But if I sum up all the edge weights in that tree， that should be the minimum edge weight possible right now we're given the solution here。

 if I want to include all nodes from a through F in this entire graph。

These are the edges that will minimize。My spanning tree right and it does form a tree right there should not be any cycles in the final solution if we add all of these up i'll get one plus two plus one plus one plus one which is a total edge weight of six right any other edge and I would have had a large sum of edge weights right。

So that's the problem we're trying to solve， connect all of these nodes。

 but as we include the edges that connect them， we want to keep the total sum of those edge weights at the minimum value possible。



![](img/799e6efd5d8d2d119b1f8b515153ebb9_68.png)

Okay。Cool now there may be multiple MSTs in a graph MST is just minimum spanning treat and there are two main algorithms for MSTs in this class prams and crustcos that I'll go over very soon。

This both of these algorithms are based on the cut property。

 so the idea is if we cut across any edges and separate the graph into two groups。

 the minimum edge that falls along the cut will be in some NSD as an example of what that means it's kind of confusing and wording but basically if I have any cut that I want to create let's say this cut right here。



![](img/799e6efd5d8d2d119b1f8b515153ebb9_70.png)

This cut is basically dividing my graph into。Two different sets of otices。

 one is including A B and C， the other is including D E and F， right？

If I investigate the edges that I included in this cut， which is basically this edge， this edge。

 this edge and this edge and this edge， right， basically the edges that I had to include to be able to separate these nodes into two separate sets。

 I see that this node。Wwhich has the minimum edge rate of one right will have to be included in my minimum spanning tree so that's what the cut property is right if I take any cut across any graph right any cut is basically a set of edges that separates the graph into two different sets of nodes。

The minimum edge weight。Edge have to has to be included in our overall minimum span entry。

 so that's what the property is based on， right。

![](img/799e6efd5d8d2d119b1f8b515153ebb9_72.png)

That's the idea。Okay， coming to Pris， so how do we execute Pris。

 basically we started any source node。

![](img/799e6efd5d8d2d119b1f8b515153ebb9_74.png)

Right and we add the source node to the set of visited nodes in the MST right so let's say that I start from a so this is my source node okay same as what I did in Dtro I started from a。

Right。Okay， and now I want to add a to the set of visited nodes in the NSnesty basically i'm just going to highlight it and i'm going to keep going until there are no unvisited node so basically until all of these nodes are highlighted I have to keep executing the following two steps。

The first step I execute is I want to add the lightest weight that leads to a node that is unvisited。

And I'll add that new note to the set of visited notes。ok。Now。

 put simply basically what happens is like。I'll look at the current minimum spanning tree my current minimum spanning tree is just a right that's the only node that I've added so far because by definition the source ver text has to be included in the spanning tree now from the spanning tree I'll have to look at all of the edges that go to node that have not been visited right so my minimum spanning tree is just a right now and these are the four edges that go from the a which is the entire MST so far to other visited node to other unvisited notes that are not in this tree right？

Fms tells me that I have to select the minimum possible edge weight so which is one in this case right firms says that if you want to make a minimum spanning tree。

 look at all of the nodes that are stemming from the tree and choose the one that's of minimum weight okay。

So if I choose this one， I'll have to include it in my Spanish tree。

And I have to visit the next node， which is C。Now my tree is basically formed of two separate nodes a ansi。

 right， and it includes this one edge that connects antsy。Again。

 I'll do the exact same thing where I look at all of the edges that stem from this minimum span tree。

 the those edges are basically going to be this， this， this， and this， right？

All of the edges that are stemming from A andC。And now I want to select the next edge of minimum weight。

That has not been visited。O。😊，So the next edge of minimum weight is either this one or this one they're both of edge weight2 so I can either include AF or CFf right let's say that we break ties in alphabetical order so I'm going to include AF okay。

 we can also do CFf based on our tie breaking condition but in this case this for the sake of simplicity I'm just going to use AF。

Right。That would mean that I have to include this f to my minimum spanning tree and also include that edge that leads to F right now my minimum spanning tree is born of A。

 C and F。Right so this time I'll be looking at all the edges that go from this minimum spanning tree onto any unvisited note。

So those edges are going to be this one A B， A D D F。

 and I'm not going to look at Cf this time because both C and have been visited and we don't need to look at both those nodes at the same time right we want to include nodes that have not been visited yet so this time I have three possible edges。

The one with minimum weight is Df of edge weight 1 right。

 so I will just include that in my minimum spanning tree this time。Which one look like that， right？

The exact same process repeats itself。Basically， again。

 the minimum spanning tree is now made up of A， C， D， and F。

 and I look at edges that come out of these four nodes and go to some unvisited node。

Those nodes are going to be A B or like B& basically right， so that I'm going to have to include A B。

 B D。第二。And there are no other edges that lead to unvisited node from a visitor domain， right？

So now between A B， B D and DE， the minimum edge weight is basically either BD or D right they're both edge weight1。

 let's say again I break ties in alphabetical order， so I will just include BD instead of DE for now。

 right？That would mean that I include B and the edge that leads up to it from my current minimum span tree。

 right？Okay， this time my minimum spending tree is based on A B，C， D and F right。

 and now I have to again look at edges that come out of all of these nodes and go to some unvisited node。

The only edge that does that is basically this DE edge。B ES as well， right。

 they both stem out of my minimum spanning tree and go to E。

 which is the only unvisited node that's left。Of these two， the minimum is D because it has weight1。

 so I will include E and the edge D because that was the minimum edge between the two that I had to choose from。



![](img/799e6efd5d8d2d119b1f8b515153ebb9_76.png)

And now basically I'm done with my entire minimum span treat， if you look here。

 this is the exact thing。

![](img/799e6efd5d8d2d119b1f8b515153ebb9_78.png)

Tree as the one that we just saw。And primes gave us the correct answer right so again。

 the idea is that。

![](img/799e6efd5d8d2d119b1f8b515153ebb9_80.png)

This time， we're basically running dirus。But instead of worrying about the distance from the source node。

We're worrying about the distance from the entire tree right so instead of worrying about the distance of E from a。

 we worried about the distance of E from this entire tree that we have built up so far right and the minimum distance then was just one if we just added this edge from D to E right so that's why it's very similar to distrs so if you make a priority queue your sorting value or like your compare the value you compare is going to be the distance from the tree instead of instead of the distance from a particular source node right you only need the source node to start the algorithm but eventually like you'll keep adding new nodes to your entire tree and from those new nodes that your tree is formed of you will be exploring new edges that lead to unvisited node right and then including the ones that are of minimum weight among those nodes。

O。

![](img/799e6efd5d8d2d119b1f8b515153ebb9_82.png)

So that was Prince。Now let's look at the next algorithm， which is called the crustcle。



![](img/799e6efd5d8d2d119b1f8b515153ebb9_84.png)

So in cross goals。I personally like this a little more because it's really simple to execute the idea is that you basically sort all of the edges by weight right I'm not going to sort then I'm just going to look at the minimum edge weight so the next minimum and basically i'm going to treat that as sorting but if you were to sort it in an actual example we know that AC is of edge weight1 so AC would go at the very top then we know that BD is of edge weight1 so BD would go at the top and then basically in that order will'll be going through all of the all of the edges right？



![](img/799e6efd5d8d2d119b1f8b515153ebb9_86.png)

![](img/799e6efd5d8d2d119b1f8b515153ebb9_87.png)

So you saw it all of the edges by weight， and then while there are still nodes that are not covered by the MST。

 so while not all of the nodes have been visited。You add the lightest edge that doesn't create a loop。

And then you add that new node to the set of nodes in the entire amnesty。Okay。

So what does this mean so basically we're。'm going to sort all of the edges by weight and let's say that I select the most minimum value right so if I want to look at the minimum value for any edge I see that okay I have AC。



![](img/799e6efd5d8d2d119b1f8b515153ebb9_89.png)

BD， D F and D E these are the four edges right now that I have that are all of weight one and that's the minimum weight right I can select any one of these initially。

For tie waking conditionss， lets just go go in alphabetical order and include this edge from A to C。

没有。If I include this edge right here， actually I'm going to do it in a different color。

I'm basically including both A and C in my minimum spanning tree。

RightBecause this edge visits both of those notes。Okay。So now。

Now that I'm done here with including this edge， I want to look at the next minimum edge that doesn't create a cycle now still I have three remaining edges。

 BD， D E and DF that are all of weight one right among these let's say I break ties again in alphabetical order which would help me include this BD edge。

So that's the next minimum S that I can include in my minimum spanning tree。Right。

Then the next minimum edge that I can see is either D or DF。Both are of edge weight1。

 again breaking ties by alphabetical order， I will include D。

And now the next minimum edge is going to be Df that's the only edge left that's weight one and that's the minimum so I just have to include Df as well right again none of my edges so far have created any cycles in the trees that I've been building。

No cycle so far， so we're good。Okay， the next minimum value I see in my entire graph is going to be two。

Now the edges that include two are going to be BE。AF and Cf。Now if I look at BeE。

 can I include this edge？If I include be E， I will basically have a cycle。Between B， E and D。

Now because this edge makes a cycle， I am not going to include it。

 so this will not be included because it makes a cycle。Right。

Then the next edge that I can look at is AF AF does not does not make a cycle。

 so I am good to include that and。I can also include CF because even if I include this。

 I won't have a cycle in any of the trees that I've built so far， but for tiebreak sakes again。

 I will just include AF。Okay。So that's basically what we're trying to do now the next minimum edge weight is basically going to be either B but we include weve concluded that it doesn't happen we can include it and C they're both again of edge weight2 now be is not included for the same reasons creates a cycle Cf also will create a cycle between A C and F if I include C。

so it don't include yeah。嗯。And now basically I'm done with my entire。

 I'll go with them for pressco because I've included all of my edges。

All of my nodes and the edges that covered those nodes。

 and again I got the exact same solution as Pris or as the one that we gave you initially， right？



![](img/799e6efd5d8d2d119b1f8b515153ebb9_91.png)

![](img/799e6efd5d8d2d119b1f8b515153ebb9_92.png)

All of those all the same edge have been covered now as a note here。

 sometimes crescos and Pris will give you separate answers。

 but if you execute those algorithms correctly both of those answers should be correct sometimes you have like multiple edges with the same weights as we saw and sometimes your tie breakingking conditions might differ so the overall tree the overall minimum spanning tree that you end up with does not need to be the exact same in all algorithms but it should still be the minimum tree the total sum of the edge weights should still be the same in both cases。



![](img/799e6efd5d8d2d119b1f8b515153ebb9_94.png)

![](img/799e6efd5d8d2d119b1f8b515153ebb9_95.png)

Cool， so that was all for content review。

![](img/799e6efd5d8d2d119b1f8b515153ebb9_97.png)