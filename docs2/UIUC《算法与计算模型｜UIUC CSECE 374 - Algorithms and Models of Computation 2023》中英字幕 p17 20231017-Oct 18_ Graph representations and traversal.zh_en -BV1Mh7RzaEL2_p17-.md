# UIUC《算法与计算模型｜UIUC CSECE 374 - Algorithms and Models of Computation 2023》中英字幕 p17 20231017-Oct 18_ Graph representations and traversal.zh_en -BV1Mh7RzaEL2_p17-

![](img/2f2f63a7a1502966720114f25f1d624a_0.png)

![](img/2f2f63a7a1502966720114f25f1d624a_1.png)

Yeah。Did hear's somebody refer to the recursion bird？version fair yeah。Whatever works， right know？嗯好。

Okay。Yeahは。Okay， let's let's go ahead and get started I don't have any。Any？

Administrative things to announce。We are slowly working our way through the more than 100 regrade requests that we got for the midterm。

 it's going to take us some time to get through those， but I've asked。Each TA to like try to do。

 you know， five to10 a day。If everybody works like that in parallel。

 we'll get down to only the ones I have to look at and unfortunately I can't work in parallel。

So again， if there's secondary regard requests， that may take me some time。

The next homework is out it's due at the usual time。

 and the next GPS is out it's due at the usual time。Soum。

We're now starting the second half of the algorithms part of the course。

We're not going to be talking about recursion as such for a while。

But we are going to be talking about one of the most useful。

Mathematical abstractions in the design of algorithms。

And as a preliminary example of this data structure。

 I want to point you to this thing that I have on the screen。

 this is called the Poiger table or the Poiger map。This is an 18th century。

Reproduction of a 14th century scroll。hi was drawn based on a fifth century description of a second century revision of a first century map of the Roman Rhos system commissioned by Augustus Caesar。

So what you're seeing here。Is a small portion of a map of the Roman road system。

Those red lines with the little jaggedty things in them， those are roads。

 this thing that looks down here like something weird。You know， blobby shape like a dragon's head。

That's the bottom of Italy， that's the heel of the boot at the top and the toe of the boot at the bottom。

 so this is not a geographic map。It's not geographically accurate at all。The map itself。

Is is about this big。By you， slightly longer than the length of the room。

This is just one panel out of the middle that shows the bottom of the boot。

But what you see on the roads here is。That there are our cities。

There's Trento over there in the arch of the boot。And then you can see the roads。

With little notches in them， each of those notches is a trading post or an inn or a small town not worthy of like drawing little buildings on。

And if you look very closely。You'll see that in addition to the names。😡，Of the towns。

 it's really hard to see with this you know， I'm zooming way in on on a JpeG here。

 which is always a mistake， but written next to it， maybe you can see。啊啊。Ear。

There's something that looks like Xxx V IiI。Those are distances。So what you have here is a graph。

Whose vertices represent locations in the Roman road network， which by the way。

 span something like 500，000 kilometers total， this map actually goes all the way to the east coast of China。

Although the entire continent of Asia fits on one panel about this big。

m because there weren't that many roads， u you've got vertices for every interesting location on the road network。

 you've got edges that represent segments of of road between those interesting locations。

Most of the vertices have degree too， because there's just a road that goes through it and that's it。

But the edges actually have whites on them。Which represent the number of miles between the two towns at the either end of the road。

Yes。Part the road that。Because I need some visual representation to show there is a town here。

This is not a geometrically faithful representation of the road network。This is a graph。

 this is an abstract representation of the road network with just enough geographic information on it to be mnemonic。

If you've ever been to a real city and ridden the subway network。You'll see the subway network。

ing that's what this is， this is a the shape of the network。

 the connectivity of the network is correct， but the actual locations of the objects don't bear any relationship to real distances or angles or anything。

 hence the bottom of the boot of Italy， which actually goes down more or less like south。

 south east pointing directly to the right， even though north is up。

It's also the fact that there's very little of actual Europe between， you know。

 the north of Italy and， well， there's some Alps。And like the Baltic Sea or no， the Arctic。

 basically。so this is an abstract。Representation or graphical representation of a graph now actual Roman travelers。

 it's unclear historically whether actual Roman travelers would carry a map like this。

What they would carry。I was called an itinerary is for the road that they were traveling on。

 they would have a list of the stops and the distances between those stops。

So rather than carrying around a drawing of the graph。

 Roman travelers would carry around a data structure for the graph。

But which they could if they wanted to plan you know， a road trip from， say Carthage to Jerusalem。

 they could run in principle ditras algorithm using the data structure given to them on these itineraries。

U。There's no historical record of anyone running Dykester's algorithm。

 there wouldn't be in part because the Roman alphabet didn't have either the letter J or the letter K。

m， but probably that algorithm， I'm reasonably confident that that algorithm was used by by somebody。

Before Ditra came up with it。Now this is not the only historical example of graphs。

 and it's not even the only historical example of graphs that comes from the Roman Empire。

 so the Romans were really not very good at developing new math and science， but they were very。

 very good at two things。😡，Because they had a standing army that they were very good at。

 that meant that they were good at engineering and they were good at bureaucracy。

The Catholic Church inherited their bureaucracy。This is an example from a 15th century document describing the Catholic Church's constiguinity laws who can marry whom。

 who can inherit from whom which word themselves inherited from Roman civil law back from the beginning。

 so what you're seeing over here on the left， this is an example of a complicated familial relationship。

The things， you know。True housewives of。A。You know， Rome。Throughru housewives of Vatican City。

 so the risk that Titus marries Theobro and has a son named Gaius。

 and then who dies and the mom remarries someone else and then has another child and then that mom original mom dies and dad remarries and has yet another child。

And now you're asking， oh， it is it like？If this person has a son and that person has a daughter。

 can know if these people get married， what's the actual relationship between those。

 if are they allowed to legally marry， if one of them dies is the other one allowed to inherit？

The I'm not entirely sure what the graph on the right is。

 but it involves a subset of the same people， possibly using a different set of relationships。

But the idea is that there were kind of you know complicated laws about which two people could marry。

Wwhich had to do with the distance between you and your prospective spouse from your least common ancestor in the genealogical table。

 but confused by things like actually if my brother and your sister got married。

 that actually makes us closer for purposes of whether we can marry。Or if my dad adopted your sister。

That makes us closer for purposes of making these decisions。嗯。At one time。

 the Catholic Church changed the rule for who could marry from， I believe it was the。

It's something like this， I'm not going to get the details exactly right。

 but it was something like the maximum of the distances from you to your least common ancestor had to be at least two。

So you can't marry your second cousin， but you can marry anyone further out to the sum of your distances to your least common ancestor had to be at least seven。

This is why when you go to European castles with old noble families。

 they have the entire family tree on the wall。Because nobles would visit each other and go into the genealogy room to figure out were whether my son was less than seven steps away from your daughter。

This arguably was one of the things that led to， know， you， nobility keeping track very。

 very carefully of genealogies， which is itself dealing with data structures for trees and if you go out far enough directed acyclic graphs。

😡，So questions about graphs have been around for， at least in Europe。

For basically as long as there's been Europe。U， yeah， there was this guy named Euler。

 who did something about bridges in the 1700s， it was much later。可了。嗯。

So yeah we're normally talking about， whent we talk about graphs。

 normally we draw a picture that looks something like this， we have circles or some other shape。

That represent。The vertices。And we have edges。That are normally drawn as straight liness or curves connecting those things。

But it's important to remember that this is just a picture。The actual。ATing that we're playing with。

Is well， we have a set of vertices。Which we normally would call V， this is any。Finite。

And for technical reasons， non empty set。So it could be， for example， the set of people in this room。

 the set of letters in the Latin alphabet， the set of words in the Oxford English Dictionary。

 the set of letters in the phrase the Oxford English Dictionary。Oh。And then we have。E。

 the set of edges。These are pairs。Of。Vertices。So for example。

 I could define a graph where the vertices are us people in the room。

And two people are connected by an edge， they form a pair if and only if they share a letter somewhere in their name。

Or I could define a graph where the vertices are the letters of the Latin alphabet。

And the edges connect to letters if there's a person in this room that has both of their letters somewhere in their name。

Or I could just say the vertices are the numbers from the national numbers from  zero to 55。

 and there's an edge between two numbers if their difference is prime。

So it's just things and pairs of things。This is another drawing down here on the bottom left。

 that's another drawing of exactly the same graph。😡，8ight。And yes。

 that thing that I've drawn up there that has 13 vertices， that is one graph。

That one graph happens to be disconnected， it happens to have two components。

 but that's still one graph， yes。But in the setup of arrows。

 the pair is always going to look like starting something。Well， okay。

 so I should clarify here that there are two types of edges。If I have an undirected graph。😡。

Then edges are sets of two vertices。There's no to and from it's just these two that's the example that I have here。

 C and D are connected by an edge， so there is an edge so I would normally just write by putting the letters down next to each other。

Without referencing their order。Okay， or there are also directed graphs。

 I'm mostly going to be talking about undirected graphs today， but in a directed graph。

 these are ordered pairs。Which I would normally write。Using this sort of mnemonic arrow notation。

 there's an edge from you to V。😡，So draw that with an arrow。Yeah。

So right out the set of every every edge so。With the set in。Yes， so for example， graph。

 this example graph that I have on the screen， the set of edges contains the E AB and the E AE and the E BC and the E C。

So the set E is formally a set of sets of size two whose elements are vertices。到。

So it's important not to confuse a graph from a drawing of a graph。😡，All right。

 so the the drawing up above that's much nicer the edges don't cross， this is sometimes。

What's known as a。Pner。Drawing。嗯。It just means none of the edges cross。

 not every graph has a planar drawing。The bottom drawing underneath it is a non planar drawing of exactly the same graph。

Um。But even this notion of vertices are little circles and edges are curves between those circles。

 even though， yes， that is exactly the notation that Roman legal scholars used。Or Catholic church。

Legal scholars used in the 14th century， it's not the only。

Way that graphs can be represented so here in the middle of the screen I have two more graphical representations of the same graph these are what are sometimes are usually referred to as intersection graphs。

😡，So on the left。We have。呃。The vertices are segments。Bine segments。

And two vertices define an edge if the corresponding pair of segments intersects。😡。

So things and pairs of things， and in this case， the things are line segments and the pairs of things are intersecting line segments as opposed to further up。

 the things are circles and the pairs of things are pairs of circles connected by a line。😡。

And you can walk through and you know step by step and say， well。

 every vertex in that representation is also present in the other one。

 every pair of vertices that defines an edge in one representation also defines an edge in the other one。

 so it's the same graph。😡，It's just represented differently over here on the right again。

 I have the same graph， but now represented as the intersection graph of a collection of circles。😡。

So again， the vertices are circles the way they are when you draw out you know DFAs and stuff like that。

 but now instead of connecting to circles by a line segment， I just let the circles overlap。

Not every graph can be represented in these ways。But some of them can and this might be the representation that you're given so。

It's useful to remember that this is a graph， this pairwise relationship between these objects defines a graph。

We've also seen graphs already in other recent contexts。

The graph that I have here labeled on top or I have a portion of it labeled on top。

 this is the dependency graph。For the Fibonacci recurrence。

So the vertices are labeled by non negative integers and there's an edge from vertex I to vertex J if the value of the I Fibonacci number depends directly on the value of the J Fibonacci number。

😡，Said differently， this is kind of what you get when you take the recursion tree for computing the enphibonacci number。

 and instead of memorizing so you get rid of things when you repeat them。

 you just take the common some problems and merge them together。😡。

This is what the dynamic programming algorithm for Fibonoology numbers traverses。

 it starts over here on the left and it walks backwards through the graph to the right。😡，Similarly。

 this is。This other graph is the dependency graph for the edit distance recurrence。

The value that we want is probably edit of E and comma N down here in the lower right corner。

 every time I make a recursive call， I'm considering a subprom that is either the first argument is shorter by one or the second argument is shorter by one or both arguments are shorter by one。

 so I get this weird looking grid graph and then in the dynamic programming algorithm the values get filled in starting at the upper left corner and working their way backwards through the graph to lower the lower right corner。

😡，These two are examples of directed graphs。But more interestingly。

Therere examples of directed acyclic graphs， meaning there are no directed cycles。

 there is a thing that might look like a cycle here， for example。

 that's not a cycle because the edges are not all oriented consistently around that。

So a directed cycle means all of the edges point forward around the cycle in the same consistent direction。

We're going to talk more about directedlycycl graphs on Thursday。

 most of the examples I'm going to talk about today are I'm going to consider just undirected graphs for now。

Here's another example of a graph。That's the Tower of Hanoi。four disks。

Every vertex in the graph corresponds to a configuration of the four discs on the three pegs。

 I've marked two of those configurations so you can actually see what they look like and every edge corresponds to a move and just to be helpful。

 I've colored both the disks and the edges you see for example。

 the green disk is the smallest one and the green edges in the graph corresponds to moving the smallest disk。

This little green triangle， it reflects the fact that at any time with the Tower of Noi。

 I can take the smallest disk and freely move it around between all three pegs。

But depending on where the smallest disk is， I generally only have like one move that involves some disk that isn't the smallest disk。

And so those are the red edges for the second smallest disk。

 the blue edges for the third smallest disk， and these occasional gray edges for the largest disk。

And the goal for the Ta ofoid problem is to get from one configuration up in a corner where all the disks are on one peg to another configuration in a different corner where all of the disks are on a different peg and the standard recursive algorithm for solving the ta ofnooid problem does this。

诶。😊，So graphs show up in configurations of puzzles where the state of the puzzle is a node and the transitions between those states are edges for the tower of Hanoi it just so happens that transitions are always reversible anytime you make a move it's legal to undo that move。

 so the edges in the Hanoi graph are。😡，Undirected， but this goes more generally for other kinds of systems that have states and transitions like DFAs。

 a DFA is a graph， it has vertices they're called states， it has edges they're called transitions。😡。

You have to be a little bit， you know， you have to be careful。

Not to define the definition take the definition of graph to be too restrict so that you can allow。

 for example， self loops so you can have an edge from a vertex V2 itself。

That's okay and in this case the edges have labels associated with them that represent what symbol I need to read in order to make this transition。

But and a few other declarationations like a start state here and an accepting state there。

 but fundamentally。DFAs are graphs。And the way that I want one of the most fruitful ways of thinking about where graphs come from is exactly this notion of state and transition。

What solving some problem？I could imagine playing with the universe and keeping track of only the information that actually matters。

Then at any given time as I'm manipulating the universe。

 the description of only the information that actually matters is my state。

And when I change my state， that is a transition that's going to be defined the vertices and edges of the system that I'm playing with。

U。This is really exactly the same intuition that I' hope that you have started to develop adult dynamic programming。

When you're developing this recursive problem， the way that you describe the shape of a recursive subprom in the pursuit of a dynamic programming algorithm is as I'm chopping up this string into smaller words。

 what information do I actually care about what do I need to remember in order to describe what I have left to do that's my description of my subproblem。

 but it's also kind of you can think of it as a state？And when you make recursive calls。

What you're doing is saying， well， if I'm thinking about how to resolve this sub problemblem。

 I need to resolve that one， so I need to change my attention from this state into that state。

So it's a transition。U。At least in the form of like what is the current stack frame if you want to think of it as an actual recursive algorithm？

嗯。So a lot of the。Design things that we're going to be doing， it's important to think about。

What is the information that I need to maintain about the problem that I'm solving and what are pairwise connections between different possibilities for that information。

 yes。Can every recursive algorithm be shown as a graph。

 well ultimately you can describe the execution of any recursive algorithm as a recursion tree and trees are graphs。

Dyna8 programming works because different vertices in that graph represent the same information。

 and so I could fold those two vertices together and I get this much more compact representation。

Which hopefully only has polynomial size， this representation， by the way。

 is your memorization data structure。嗯。Okay。So。I want to start。By。Thinking about。Okay。

 so there's lots of sort of abstract ways that we can think about graphs。

 but ultimately when we're writing code， we need to nail down。U。A data structure。

That we're going to use to store our graphs。So there are。

Two maybe three standard ways of representing graphs。

Let's say there are two that are really useful and a third that's there because it's sort of obvious。

 but usually end up converting into one of the other two。嗯。What are the big two？

How do I represent a graph in memory？Yeah。An adjacency matrix， okay， so don't look at screening。

This is an adjac matrix。So。What I have on the left is that graphical representation of that that。

Romanman legal graph， what I have over here on the right is a matrix of zeros and ones。

Every row corresponds to a vertex。Every column corresponds to a vertex。

And the value of a particular cell in this。Mattrix。

 this value in row G column I represents an edge between vertex G and vertex I， whereas， for example。

 this zero in ro k column B represents the absence。Of。Let's say row L column B。

 that represents an absence of an edge between vertex B and vertex L。For an undirected graph。

 the adjacency matrix is symmetric。So everything above the main diagonal reflects everything below the main diagonal。

Pairs are unordered。U，There are zeros down in the diagonal because you can't have a set of two vertices where the two vertices are equal。

You sometimes may need to relax that。Um butum。There is this representation now one of the things that's really nice about this representation is that I can tell in constant time whether an edge is present in the graph or not。

 I just look it up in the array。Yeah。This was a directed graph。

Would throw a column the representative as K。Okay， so this is a good question if if this is a directed graph。

 then say these two。These two green dots。One in row L column B and one in row B column L。

 those represent the possibilities for two different edges， same endpoints。

 but in different directions and the question is if I'm in row B column L is B the tail of the edge or the head of the edge。

Whatever， decide。Flip a coin， it doesn't matter， I think it may be because we typically use the row index as the first argument when we're accessing an array。

 it may be slightly more natural for the row index to be the tail of the directed edge and the column index to represent the head。

 but this is really an arbitrary decision。Thank。So if I want to know here， so this is an adjacency。

Matrix。So I can decide。Is a。Given a pair of vertices， do they define an edge？

That I can answer in Constantine。Just by looking things up。If I want to say lists of neighbors。

Of a vertex。So a neighbor vertex is something that V is connected to by an edge。

So a has vertex A here， has two neighbors， B and E。This I really need order V time。

 I can sort of scan through the corresponding row of the adJc matrix in linear time and whenever I see a one that's a neighbor and whenever I see a zero that isn't。

So if I notice that F here has four neighbors has corresponded the four ones in row F。

But I have to scan the entire row in order to figure this out。Okay。

What is the other standard representation for graphs？Yeah。Yeah， and adency lifts。Okay， so。嗯。

This is a bit of a weird。Name。Because an adjacency list is not a list。It's an array of lists。

But it's still called an adjacency list。This is consistent with there's something called the red herring principle mathematics。

 which is a red herring is not necessarily red and it's not necessarily a fish， much less a herring。

Okay， so just because the name says adjacency list doesn't mean it's a list。

it's an array of lists and so you have an array least intuitively indexed by the vertices。

And each vertex keeps a。List in some form， typically just a singlely linked list of all of the vertices that it is adjacent to。

So again， if I look here at。Vertex F。I can list off the four neighbors of F by just walking down that list。

The order that the neighbors appear in the adjacency list for vertex doesn't really matter。

 you might want to put things in a particular order for some particular application。

 but the definition of an adjacency list doesn't care about whether any particular order。

 so that's why these aren't all listed in alphabetical order， for example，😡。

The nice thing about adjacent to list。Is I can list all neighbors。

Of a vertex v in time proportional to the number of neighbors of V。

 which is what's usually called the degree of V。And this could be significantly smaller than the number of vertices。

So if you' in an algorithm that is frequently askeds to like loop over all the neighbors of this vertex。

I really would prefer to be using an adjacency list data structure to an adjacency matrix data structure。

On the other hand， if I want to check。Yes。UV is an edge in E。So I want to know。

 is there an edge between vertex B and vertex L？Well。

I'm basically forced to traverse at least one of these two lists。

the list at B and looking for L and the list at L looking for B。

 and so instead of taking constant time。The right way looks say this is it's going to take time。

Pal to the minimum of degree U and degree V。The way that I actually achieve the minimum is that I alternately take one step in use' list and one step in V list and if I get through either list I hit a null pointer then I know I've completely traversed that list that I didn't find the other vertex I know it's not going to be there。

 there's no edge。哎对。嗯。So if I'm dealing with algorithms that need to decide， hey。

 is this edge in the graph or not， then really， I'd probably prefer to be down here in adjacency matrix on。

But it turns out that it's actually relatively rare for graph algorithms to ask the question。

 is this edge in the graph？And relatively common for graph algorithms to ask。

Loop over all the neighbors of this vertex。And so for at least for the graph algorithms that we're going to see in this class。

 it is always going to be more efficient provided the graph doesn't have very many edges to use an adjacency list instead of an adjacency matrix。

 the other reason why I'm not going to use an adjacency list instead of an adjacency matrix。😡。

Is the amount of space？That an adjacency list data structure uses is proportional to the number of vertices for the top level array plus the number of edges。

Every edge is represented by two different records in the adjacency list data structure。

 so the edge between E and F is represented as a record once in E's adcency list and represented the second time in F's adjacency list。

😡，And if you're really doing this， you probably want pointers back and forth between those two records。

Whereas no matter how many edges。You have in an adjacency matrix。U。

You always are using a quadratic amount of space in the number of vertices。

So even if the number of edges is very， very small。Adjacency matrices。

Don't care about how sparse the graph is， they're just going to give you v squared space。Now。

This is kind of a subtle point here because so far we've always been thinking about algorithms in terms of their worst case running time。

 and we've analyzed them typically in terms of one parameter， which is almost always called n。

But now we're going to be wandering into a landscape where we actually want to pay attention to the rh times of algorithms and how they vary in terms of both the number of vertices and the number of edges。

And so when the graph is sparse， meaning the number of edges is significantly less than n squared。

 we get faster algorithms this way and running times reflect that speed up。

So any graph that has a planar drawing， for example。

 turns out that the number of edges is at most three times the number of vertices。

So if I have an algorithm that runs in something like v plus E time that I know in these kinds of really sparse graphs。

 that's just linear in V。But if I need to use an adjacency matrix。That's quadratic invy。

Which is slower。So I'm going to pose an interesting question。Why would I ever？Want to use。

Adjustency matrix。Ever。😡，Given that like， oh yeah， this operation is fast。

 but I'm never going to do that。What's the point of thinking about adjacency matrices？Yeah。

Can you speak up， I'm sorry。Okay， so this is one reason why you might want to use an adjac matrix is it's a matrix。

It's not just a two dimensional array。And so you can do linear algebra things with it。

One of those linear algebra things you can do is called page rank。

Page ranknk is literally the most the eigenvector of not this matrix。

 but another closely related matrix called the Laplaceian， where you add stuff along the diagonals。

 but the idea is you do an eigenvalue decomposition of this matrix and you take the largest eigenvalue。

 look at the corresponding eigenvector， now the matrix that when Google setup had one row in one column for every web page。

😡，and had a one or a zero or possibly higher numbers representing numbers of links from this web page to that one。

 and what it was looking for was tightly interconnected pieces of this graph。

 that turns out to be reflected in the algebraic structure of this matrix now if you don't know what an eigenvalue or an eigenvector is yet。

You'll see that in Ma 257， you'll see that in CAS 357。

357 is all about the singular value being composition， it's all about the eigenvalues。嗯。

But that's actually a really important reason why you would want to use at least intuitively an adjacency matrix but。

But。But when the matrix is sparse。Actual software for computing these algebraic things don't use this data structure。

 they use the other one。That thing up there called an adjacency list is also known as a sparse matrix data structure。

So yeah， intuitively thinking about a matrix is actually really useful。

 but if you actually come down to the implementation。No， you're back to using AJCC lists again。So。

Any other ideas， why would I want to use an adjacency matrix。

 why I want to think about adjacency matrices？Yeah。

So there are more complicated structures called hypergraphs。

 where edges consist of large sets of size larger than two。

There are also sparse representations for those hypergraphs。

It's instead of like three dimensional matrices。We're not going to get into that yeah， our hypers。

TheIn of edges use faces， No， they're called edges。This edge has three vertices。

 that edge has five vertices， sometimes they're called hyper edges。

 you're thinking of something else which iss dear to my heart， sial complexes， but no。

 that's something else。U would I， why I want to think about advocency matrices？Okay。

 so this is a good point， suppose I need to modify my graph。😡，This does happen quite a bit。

 I need to remove delete an edge or I need to insert an edge。

 if I have an adjacency matrix I just reach into the array。

 changes zero or under vice versa if I need to play with an adjacency list。

 I have linked lists there， so deleting something from a linked list needs finding it in the linked list and doing the pointer magic。

😡，Insting something into a linked list， if I really want to do it right have to make sure that i'm not putting an extra copy in there。

 so I again insertions and deletions take time proportional to the degree。But。😡。

Why did I use linked lists there？Because that's what Canuth told me to use。

The only reason why there are two reasons why we used actual linked lists in adjacency list， one。

 that's what every textbook tells you to use。So that's what we do。

 we don't think we just follow what the guy up front， what tenure tells us to do。

Okay but the other one is for most algorithms， a linked list is actually good enough。😡。

I'm just going to be enumerating neighbors over and over again。

 then just something that I can iterate over， that's fine。

 but if I'm going to add vertices and delete vertices， instead of linked lists。

 I would use a different data structure that supports fast insertions and deletions。😡，Such as。

How do I maintain a set？That in a way that allows me to add things and delete things quickly and possibly enumerate them quickly。

So let said it， say Bder。A map otherwise known as a hatchh table。

So I could use as long as I use a sufficiently dense hash table。

 as long as I set it up with professionally developed hash function that somebody else gave me because writing my own hash function is a cardinal sin。

😡，But the same reason that like writing your own random number generator is a cardinal sin or。

You know， doing any lots of other things trying to do it yourself as Cardinalson。

 so if I have a good hash function with good collision resolution and it's nice and dense。

 then I can do dynamic table things。I can insert something into a hash table in constant time。

I can delete something from a hash table in constant amortize time。

Um or if I don't mind paying small penalties， I could use a binary search tree instead of this list。

 and then I have logged in overhead every time I want to do an insertion or a deletion or a membership check。

So I can still get some advantage from using the sparse data structure。

maybe not as much as I would like， because either I have to depend on weird assumptions I don't completely understand about hashing or I have to get some logarithmic overhead if I'm using binary search trees。

 but I can still take advantage of the sparsity to get something that's faster or uses less space and it's probably faster overall than using the adjacency matrix。

😡，So the one reason why。I think the most important reason， honestly。

 about why we want to think about adjacency matrices。

Is sometimes you're not given the graph in a data structure。

 you're given information that defines the graph。😡。

In a form that allows you to check in constant time whether an edge is present or not。

So if I give you a collection of circles。And ask。Is this connected？

What you can think of it as is it's a graph， the intersection graph of those circles。

 and I'm asking whether that graph is connected。And that's something I know how to do using whatever first search。

But as long as I have access to a graph， but I do have access to a graph。

If I want to know whether circles I and K overlap in constant time。

 I can do a small amount of math and I get the answer。

 that means I can pretend that I just looked it up in a table in constant time。

 one constant time computation versus another constant time computation for purposes of analysis are identical。

😡，So。This implicitly represented graph。Behaves like an adjacency matrix。

And I could spend the time converting it into an adjacency list。Or I could just say。

 I'll pretend there's really an adjacency matrix and I'll implement the lookup operation using this subroutine over here that takes constant time。

And so this allows me to run graph algorithms on implicitly represented graphs。

Without having to actually build an explicit data structure。

 but sometimes that implicit representation is going to look like an adjacency matrix and other times。

It's going to look like an adjacency list。For the Tower of Hanoi problem。

 I can enumerate the three legal moves from any configuration in constant time。😡。

But if I give you two sets of disks and ask can I connect from here to there。

 the fastest way to do that is to you know directly in one move。

 the fastest way to do that is to try to make moves in one configuration and see if it's equal to the other。

 so this this is kind of an implicit adjacency list data structure whereas the intersection graphs that I showed up here。

 these are implicit。😡，Adjacency matrix data structures。嗯。All right。

I think that's as much as I want to say about these two things most of the time I'm going to be assuming that。

呃。By default。If I'm given a graph， that means I'm given an adjacency list representation for that graph。

But you may encounter in homeworks。or exams or labs or something problems where the graph isn't given to you explicitly。

 but rather defined implicitly by some other given information and then you need to think a little bit。

About whether that implicit representation should be treated as more like an adjacency list or is more like an adjacency matrix。

Yeah， question。They like a third data Scure。Where theres a。The ver of your edges， and。

There's a third data structure called an edge list that's a list of all of the edges。

But in order to use it， you have to convert into one of these other two。

So you convert it to one of these other two？So I remember like， there is a。The data Dr where is？

Verstices vertices and edges separate， but they're bidirectional pointers between you store the vertices and edges separately。

 but they're bidirectional pointers in the sense that vertices are the ninjugers from one to n。

And edges are pairs of vertices from one to N。Maybe you have a point on your the first edge that so an edge list without any other organization is utterly useless。

 turn it into an adjacency list， an edge list that is properly organized is equivalent to an adjacency list data structure。

Okay。Oh this is another point I want to make about these data structures。

 occasionally I will want to associate other information with the vertices or edges of a graph。😡，嗯。

So。は。Within these representations that I have on the screen here。What are the vertices？

What is the representation of a vertex？In these。Dave structures。Sorry。No。

 those I put the labels on there。For convenience， so you could actually see that that's part of the drawing。

But the actual data structure wouldn't necessarily have those letters in there， so it would have。

 you know in particular in the adjacency list data structure。

 there's no reason for me to call the vertices A through M， they already have names。😡，What are they？

The array is how I get from a vert text to its list of neighbors。

What do I feed into the array to get information out？An index。

The vertices are the integers from 1 to v or0 to v minus one。The vertices are integers， remember。

 the set of vertices is any finite non empty set。And when I'm representing a graph in memory in a standard data structure。

 the standard representation for a vertex。Is an integer。There's vertex 5， so instead of a through M。

 I really should have called these vertices 1 through 13。😡。

And what's actually stored in the adjacency list in the neighbor part is the index of that neighbor。

So if I want to associate additional information with the vertices like I want to store a color for each vertex。

 or I want to store which component some integer that represents which component that vertex belongs to。

😡，What's the most natural way to store that information？

How do I associate values with the integers from one to v？Somebody give me a bad answer， please？

But Ray， I don't know， I wanted a bad answer。That was the correct answer。Okay。

 so if I want to associate other information with the vertices。The vertices are integers。

 so I have a standard data structure that allows me to associate data with small integers。

 it's called an array。Okay， now I'm generally going to to when I'm talking about things like I'll define in my algorithms something that。

You know， V dot color or V dot mark。Where I'm imagining in some abstract sense that I have a record for every vertex and I'm associating a field with that record。

 but really if I'm implementing this， I would probably really do it by having an array that looks like that。

Um。Similarly， if I want to associate data with the edges of a graph with an adjacency list data structure。

 then in every one of those records in the lists。I would put the data there in an initial field that corresponds to the edge。

Yeah。Oh。ticVertex the singular of vertices is vertex。

 there is no such word in English as verticie every time you say the word vertice the baby Jesus Christies and you owe me a dollar。

Btex， if you can't keep it straight， say no。Okay， now what was your question？

If I wanted to lead a vertex。He of her text extended。In this series， well。Very good。

If I wanted to delete a vertex， then what I would do is I would mark vertex 6 as dead。

 but I would not change the indices， I would just have some indices correspond to vertices that don't exist anymore。

😡，It's called tombstone name， it's the same way you delete something from ash table。

And then when too many things are dead， you clean up and rebuild data data structure。All right。So。

Let's start with looking at algorithms。The singular of indices is index。Again。Baby Jesus。

 you owe me a dollar。UmOkay， so this is depth for search。Okay， this is the most standard， you know。

 the first thing most people think of when they think about searching graphs。😡，Okay。

 so here's the recursive version of the algorithm。Hey。

 this is the one that probably you would actually want to implement。It says， okay。

 I'm going to walk into a graph， I'm walking into a maze。And when I reach a junction in the maze。

 I reach a node in my graph。I'm going to put a rock on the ground that says I've been here before。

If there is no mark， if there's no rock on the ground for that intersection。

 I put a rock on the ground since I've been here before， and then I recursively try every corridor。

Leading out of that junction。Searching the rest of the graph， but because I put the rock down。

When I come back to a vertex from a different direction， I'm not going to explore it again， I say。

 oh， I've already been here， I'm just going to pop back up the recursion stat。And so。This。

Dept first search algorithm。嗯。Is guaranteed to visit every vertex。That is in the same component。

That is reachable from whatever start vertex I start the search app。Okay。

 so I'll pick some node at the beginning and I'll say， do a depth search from here。

And depth search will explore the graph。Visiting every node that is reachable from that start vertex。

😡，Um， now。This is how you would find out， for example， how many nodes are reachable from this vertex。

 how large is the component for this vertex？or I want to find all of the things that are connected to this and treat that subgraph as something that I pass to a subroutine and then later I'm going to like find some of the vertex that wasn't marked and do that again for different components of my graph so this is this is a way of sort of systematically exploring the graph。

😡，It's very， very easy to implement as long as I have some way of associating bits called marks with the vertices。

And of course， like any recursive structure， I can implement it iteratively by making the stack explicit。

So when I walk。To when I say， okay， as long as my stack is empty。

I'm going to pop the vertex on the top of the stack off。

And as long as that vertex if that vertex is unmarked， then I'm going to mark。

And then I'm going to push each of the neighbors at that vertex onto the stack。Again。

 this is marking every vertex that is connected to whatever vertex I start with at the top level recursion。

嗯。There's another。Way of searching graphs that you've probably heard of and or used or at least searching trees that you've probably heard of or used。

It's not in depth for search。Brereadth for search。The difference between depth for search and breadth for search。

Is。That。Usually I prefer to call the extraction operator for Q's poll instead of P。

 most people will insist on NQ and DQ， but that's boring。

The opposite of pushing in the back is pulling from the front。And well， these are really examples of。

What I refer to more generically as whatever first search。Okay。😊。

Whatever research means I don't care about any special order that you're going to search the graph。

 I just want to make sure that I search the graph so I am going to use an anonymous data structure。😡。

That I will call a bag。And a bag has。呃。3。嗯。Operations。That it supports。I can。

Insert a vertex into the bag。I can reach into the bag and pull out over text。

I have no control over which vertex comes out of the bag。I just get a vertex。

And I can ask whether the bag is empty。I can shake the bag， it's not making any noise， it's empty。

Okay， so it is like literally the bag of marbles。Data structure。Where the marbles are overseases。

Now a stack is an implementation of a bag， a stack is when I insert it goes on top and when I remove one I remove the last one I insert it。

 Q is a version， an implementation of a bag， whenever I insert I inserted in the back and when I remove when I remove the one that was inserted furthest in the past。

 so in the front。But there are other versions of bags。

 like maybe I want some priority cu where I have priorities attached to the vertices and I'm for reasons that I don't care about now。

 I want to make sure that when I extract things I extract the vertex with lowest or highest priority。

Or maybe it's important for some reason I don't want to think about it now that when I reach into a bag and pull out one vertex。

 that vertex has chosen uniformly at random this out of the bag。对。None of that matters。

When I'm thinking about whatever for search。So whatever first search here gives me a way of systematically exploring the graph。

 but not in any particular order。😡，This is the algorithm that you want to call when you want to exploring graphph and you don't care about exploring it in any particular order。

 not depth for search， not breadth first search， whatever first search。

 let the person implementing it decide whether they want to do depth or breadth or something else。

 based on whatever criteria they want。😡，Don't make the decision for them wrap with。

This is an excellent question。If the graph is disconnected。

 you probably want to put some sort of wrapper function around it so that you actually visit every node in the graph and this is really useful。

 for example， if I want to count the number of components in the graph。

 what I can do is keep a separate counter and start by clearing all the marks and then for every vertex v in the graph in whatever order。

 what the vertices are represented by integers from one to v。

 so that for all vertices V is really just a standard for loop。😡，If the vertex is unmarked。

 then I say， oh， there's at least one component I haven't encountered yet， increment my counter。

 run whatever for search to mark everything in that component， and then continue the for loop。😡。

If during this for loop， I visit a vertex V that has already been marked。

 that means it was already allocated in some other component previously。

 and I don't need to search again， I don't need to implement my calendar。嗯。

There's a question about the running time of this algorithm。U。I will spoil the punchline。And say。

 if algorithm if the graph is represented using an adjacency list data structure。

This entire algorithm runs in time proportional to the number of vertices plus the number of edges。

And to give you a sense of why that's true。U。Let me just mark。四。

This line in the whatever first search algorithm and ask during the course of an entire whatever first search。

How many times is that line with the two stars on it executed？Okay， so this is the part where I say。

 okay， I take a vertex out of the bag。I see that it's unmarked。

 so I haven't visited this vertex before。😡，I look down each of its edges to my neighbors now because I've never visited this vertex before。

 I've never looked down these edges before either in that direction。😡，And for each of those edges。

 I'm putting the other endpoint into the back。😡，诶。😊，So that double startre line。Is executed。

Twice for every edge in this part of the graph。系。So let me just give an example here。S U V。

 let's suppose this is my graph。Okay。So I'm going to start， here's my bag over here。

I'll start by putting S into the bag。Then X isn't marked。So I market。I take S out of the bag。

 it isn't marked， I take the neighbors U and V and I pull them out of the bag and by doing that I went。

 I looked at these two edges in that direction， I looked from S down the edge to U and I looked from S down the edge to V and doing that I put UN and V into the bag。

Then I pop back up and say， oh， I need to take something out of the bag。So I take V out of the bag。

 I notice that it's not marked， so I mark it。😡，And then I need to put its neighbors into the bag。

So its neighbors are U and S。So now I've looked this way down the edge from V to S and this way down the edge from V to U。

Now I need to pull a vertex out of the bag。Yes。I pull S out of the bag。And well， S is already marked。

 so I don't do anything。Now I pull you out of the bag， let's say I pull this one， you is not marked。

So I mark it， and then I need to put its neighbors into the bag。

 so I'm looking at the neighbors S and V。And at this point， everything else is marked。

 so I pull U out of the bag and then I pull V out of the and pull S out of the bag and the algorithm is done。

So for every edge。In the graph。In the part of the graph that is traversed。I put。😡。

One endpoint puts the other endpoint into the bag， and then the second endpoint puts the first endpoint into the bag。

 and that's only the only thing that happens with each edge。So this line is executed。Order E times。

at most2 e times。So they are most two e times when I put things into the bag。Actually。

 I should say2 e plus one。So how many times is this line executed？

How many times do I take something out of the bag？Well。

 at most the number of times I put something into the bag。In fact。

 equal to the number of times I take something and put something into the bag。

 so this line is executed。Order E times。So if I look at various pieces of the algorithm。

This line is executed order v times。So there are the number of times I take something out of the bag is proportional to the number of edges。

 but most of the time the thing I pulled out out of the bag is already marked。

 and so I don't do anything else。But once for every vertex， I'm going to mark that vertex。

And launch the loop over its neighbors。But at this point， every line in the pseudocode。

Is that where I'm actually doing some work。I've written down how many times that line is executed。

I do the first line once。The main while loop executes order E times。

 so their order E times that I take something from the bag。

 their order E times the I check whether their vertex is unmarked。

Theyre only order of V times where I mark something。

 the order of v times when I launch the second inner for loop。

 and there are a total of order E times when I take something out of the bag。

So the overall running time here。Is。Proportal to the number of vertices plus the number of edges。

We are out of time。I'm happy to answer any other questions up front。

 thank you for your patience for going over the last couple of minutes。

And I'll see you all on Thursday。系。All right， letting you get somewhere。



![](img/2f2f63a7a1502966720114f25f1d624a_3.png)