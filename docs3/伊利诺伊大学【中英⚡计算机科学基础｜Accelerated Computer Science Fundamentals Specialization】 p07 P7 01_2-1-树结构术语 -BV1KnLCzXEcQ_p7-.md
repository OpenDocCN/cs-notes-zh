# 伊利诺伊大学【中英⚡计算机科学基础｜Accelerated Computer Science Fundamentals Specialization】 p07 P7 01_2-1-树结构术语 -BV1KnLCzXEcQ_p7-

![](img/315a36f67544b2ed9cd1ebeb88e958f3_0.png)

![](img/315a36f67544b2ed9cd1ebeb88e958f3_1.png)

Up until now， we have discussed purely linear or flat data structures Today。

 we're going to discuss a new series of data structures that provides us the ability to have complicated data and relationships such as a parent。

 child and sibling relationships。This data structure is called a tree。

Let's dive into what this means。This is one of my favorite trees in the world。

 And this tree maps all of the Mario games that were created in the entire Nintendo franchise。😊。

Untiltel 10 years ago， as part of this tree， you can see that there' is an original game that included Mario。

 That was Donkey Kong。And from there， there's a ton of different games that run the entire lineage of Mario Game going only to Mario Galaxy。

 And there's been probably hundreds of games since then。 So seeing this Mario family line。

 we see it starts with a single node。😊，And really， these are kind of precursors to the actual first Mario game。

And the first true Mariiogan he is really here。 And we can really consider this the root of the tree。

From there， we can see that the root of the tree has several branches。 My personal favorite。

Is Super Mario Brothers RPG， Great classic if you've ever played it。

 But let's actually talk about trees， not in terms of a specific tree。

 but terminology that can apply to every tree possible。 And in fact。

 this video is just going to talk about the terminology so that after this point we can be very clear when we're describing this data structure。

Every single elementary a tree， we're going to call a node。

 and we're going to always denote a node with a circle。So you'll say see here's a tree。

And in this tree， we have a number of nodes。Nodes are always connected to another node by an edge。

In a tree， an edge will always be directed and will always be directing the edge away from a root。

In computer science， we often say that we grow trees backwards because it will represent a tree with the root on the top。

Compared to a normal tree， then will grow out。By going down， instead of going up。

But you can really think of a original tree， just turn it upside down。

So a tree must always contain a single root node， and the root node must have no incoming edges。

So the topmost node of the tree， as we draw it， has nothing coming into it。

 All it has is nodes going out of it。 And every tree must contain a single root。

 So there's only one node that has no incoming edges， and that node must be the root。

Notes that have no outgoing edges are called leaf nodes。These are at the base of our tree， and these。

Just like a normal tree， which going to column leaves。

 And these leaf nodes can be found at any level。 But the only requirement is they have no outgoing edges in our trees。

Our node will store our data。So here in this tree， we've stored the first 10 or so letters the alphabet。

 In this tree， the nodes contain the data。Edges， on the other hand， are often never labeled。

And they contain no data。In fact， we'll identify the edges just in the names of the nodes that they connect。

 For example， this edge from Kta M。We'll just call this KM。Because this is the edge。

 It starts from K and goes to M， and it connects the node K and the node M。

So we will very rarely ever name an edge， and our edges will never contain data。

All of the data that we're going to store in this data structure will always be in the nodes。

Every node， except for the root node， will have something we refer to the parent node。

 This works just like a family tree。 One level up from you in the tree is going to be your parent。

For example， the parent of B is a since B has an incoming edge from a。The parent of K is D。

Looking at the incoming edge again， Pernol is also D。On the flip side。

 a node's children are the node that have that node as a parent。

So it's possible for a node to have anywhere from zero children to an infinite number of children。

 While every node， but the root has just a single parent。So notice that note A right here。

Noday has three children。Nodes C， a leaf node has no children。

 So leaf nodes have no children because they have no outbound edges。

And M right here has just a single child。So we see a no that has three child。

 A no that has three children。 A no that has one child。And a node that has。6 children。

So these type of relationships on the tree work just like an ancestral tree。

And all of the ancestry terms that you're used to really do apply to the trees， siblings。

A sibling of a node is something that's on the same level and share is a parent。

 So B And D are siblings。An ancestor。Works just like a normal family tree。

 A grandchild or a grandparent works just like a family tree。 You can have multiple grandchildren。

 just like you could have in a family。But because our nodes don't actually marry。

 you only have a single grandparrot。Finally， we wanted to find exactly what it means to be a tree。

In a tree， three conditions have to be true。The tree must have a root。

The tree must have directed edges， and the tree must not contain a cycle。

 So what this means is if I were to have a edge from M to D。Suddenly。

 we can travel from D to K to M back to D in this big loop。If we ever have a loop。

 we're no longer a tree。So long as all of our edges travel down a level deeper。

 So as all of our edges are down。Then we can never have a loop， because to have a loop。

 we have to move an edge up。 So as long as all of our nodes face down。

 we can easily check any sort of diagram and say， okay， yep， all of the node's edges face down。

 Therefore， we must have a tree。We say this tree is a rooted， directed， acyclic structure。

And we'll explain what this means more as we talk about general trees or graphs later in this class。

So the big things take away is trees are formed with nodes and edges。Trees must be directed。

 rooted and acyclic。And the relationship between nodes and a trees follows a classical ancestry pattern。

 It's got parents。 It's got children。 It's got grandchildren。 It's got a grandparent。

It has ancestors， and it has descendants。 All of the terms that you' are accustomed to from your own family。

 we're going to use here in computer science。So now they have your tree terminology。

 let's dive in and look at particular types of trees that are particularly useful as a data structure。

I'll see you there。

![](img/315a36f67544b2ed9cd1ebeb88e958f3_3.png)