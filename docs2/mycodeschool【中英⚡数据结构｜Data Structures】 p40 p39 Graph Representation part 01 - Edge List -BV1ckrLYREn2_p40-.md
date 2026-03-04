# mycodeschool【中英⚡数据结构｜Data Structures】 p40 p39 Graph Representation part 01 - Edge List -BV1ckrLYREn2_p40-

Hello everyone in our previous lessons we introduced you to graphras and we also looked at and talked about some of the properties of graphra。

 but so far we have not discussed how we can implement graphra。

 how we can create a logical structure like graphra in computers memory。

So let us try to discuss this a graph as we know， contains a set of vertices and a set of edges。

 and this is how we define graph in pure mathematical terms。

 a graph G is defined as an ordered pair of a set V of vertices and a set E of edges。

Now to create and store a graph in computers memory。

 the simplest thing that we probably can do is that we can create two lists。

 one to store all the vertices and another to store all the ages for a list we can use an array of appropriate size or we can use an implementation of a dynamic list。

 In fact we can use a dynamic list available to us in language libraries。

Something like vector in C plus plus or a raillist in Javava。Now， a vertex is identified by its name。

 so the first list， the list of vertices， would simply be a list of names or strings。

I just filled in names of all the vertices for this example graph here。Now。

 what should we fill in this edge list here？An edge is identified by its two endpoints。

So what we can do is we can create an edge as an object with two fields。

We can define edge as a structure or class with two fields。

 one to store the start vertex and another to store the end vertex。Edge list would basically be。

An array or list of this type struck edge。In these two definitions of edge that I have written here in the first one。

 I have used character pointers。Because in C， we typically use character pointers to store or refer to strings。

 we could use character array also in C++ or Java where we can create classes。

We have string available to us as a data type。So we can use tas so we can use any of these for the feeds。

 we can use character pointer or character array or string data type if it's available。

Depends on how you want to design your implementation。Now。

 let's fill this edge list here for this example graph。 Each row now here has two boxes。

 Let's say the first one is to。Store the start vertex and the second one is to store the end vertex。

 The graph that we have here is an undirected graph。

 So any vertex can be called start vertex and any vertex can be called end vertex。

Order of the word disease is not important here。We have nine edges here， one between A and B。

 another between A and C， another between A and D， and then we have B。

 E and B F instead of having B F as an entry， we could also have FB。But we just need one of them。

 and then we have C G， DH。EH。And F H。Actually， there is one more。 We also have GH。

 We have 10 edges in total here and not9 now。Once again， because this is an undirected graph。

 if we are saying that there is an edge from F to H。

 we are also saying that there is an edge from H to F。

There is no need to have another entry as H F we will unnecessarily be using extra memory。

If this was a directed graph， F H and H F would have meant two different connections。

 which is the start vertex and which is the end vertex would have mattered。

Maybe in case of undirected graphs， we should name the fields as first vertex and second vertex and in case of directed graphs。

 we should name the fields as start vertex and end vertex。

Now our graph here could also be a weighted graph。 We could have some cost or weight associated with the edges。

 as we know in an unweighted graph cost of all the connections is equal， but in a weighted graph。

 different connections would have different weight or different cost Now in this example graph here I have associated some weights to these edges Now how do you think we should store this data the weight of edges。

Well， if the graph is weighted， we can have one more field in the edge object to store the weight。



![](img/3d38bebd7b1eaf61ff9750f799856fc4_1.png)

Now an entry in my edge list has three fields， one to store the start vertex。

 one to store the end vertex and one more to store the weight。

So this is one possible way of storing a graph， we can simply create two lists。

 one to store the vertices and another to store the edges。

But this is not very efficient for any possible way of storing and organizing data。

 we must also see its cost。And when we say cost， we mean two things。Time cost of various operations。

And。The memory usage。Typically， we measure the rate of growth of time taken with size of input or data。

 what we also call time complexity。And we measure the rate of growth of memory consumed with size of input or data。

 what we also call space complexity。 time and space complexities are most commonly expressed in terms of what we call big O notation for this lesson。

 I am assuming that you already know about time and space complexity analysis and big O notation。

If you want to revise some of these concepts， then you can check the description of this video for link to some lessons。

We always want to minimize the time cost of most frequently performed operations。

 and we always want to make sure that we do not consume unreasonably high memory。Okay。

 so let's now analyze this particular structure that we are trying to use to store our graph。

Let's first discuss the memory usage。For the first list， the verortex list。

 least number of rows needed， or consumed would be equal to number of verortices。

Now each row here in this vertex list is a name or string。And string can be of any length right now。

 all strings have just one character because I simply named the node， ABC and so on。

But we could have names with multiple characters。 and because strings can be of different length。

 all rows may not be consuming the same amount of memory。



![](img/3d38bebd7b1eaf61ff9750f799856fc4_3.png)

Like here。Here I'm showing an intracities road network as a weighted graph。

Cities are my nodes and road distances are my weights。 Now， for this graph， as you can see。

 names are of different length。 So all rows in verex list are all rows in edge list。

Would not cost us same， more characters will cost us more bytes。

But we can safely assume that the names will not be too long we can safely assume that in almost all practical scenarios。

 average length of strings will be a really small value。

 if we assume it to be always lesser than some constant。

 then the total space consumed in this verortex list will be proportional to the number of rows consumed That is the number of vertic。



![](img/3d38bebd7b1eaf61ff9750f799856fc4_5.png)

Or in other words， we can say that space complexity here is big O of number of fortic。

This is how we write number of vertices with two vertical bars。

 what we basically mean here is number of elements in set V。Now， for the edge list once again。

We are storing strings in first two fields of the edge object。

 so once again each row here will not consume same amount of memory。

But if we are just storing the reference or pointer to a string like here in the first row instead of having values filled in these two fields。

We could have references or pointers to the names in the vertex list。

 if we will design things like this， each row will consume same memory。This。

 in fact is better because references in most cases would cost us a lot lesser than a copy of the name。

And as reference， we can have the actual address of the string。

 and that's what we are doing when we are saying that start vertex and end vertex can be。

Character pointers， or maybe a better design would be simply having the index of the name or string in vertex list。

Let's say a is at index 0 in the vertex list and B is that index 1 and C is at index 2。

And I'll go on like this。

![](img/3d38bebd7b1eaf61ff9750f799856fc4_7.png)

Now， for start vertex and end vertex。We can have two integer fields。

As you can see in both my definitions of edge， start vertex and end vertex are of type int now。

 and in each row of edge list first and second field are filled with integer values。

I have filled in appropriate values of indices。This definitely is a better design。

 And if you can see now， each row in edge list would cost us the same amount of memory。 So overall。

 space consumed in edge list would be proportional to number of edges， or in other words。

Space complexity here is big O of number of edges。 Okay， so this is analysis of our memory usage。

 overall， space complexity of this design。Would be big O of number of what is C plus number of edges。

 Is this memory usage unreasonably high。 Well， we cannot do a lot better than this if we want to store a graph in computers memory So we are all right in terms of memory usage Now。

 let's discuss time cost of operations。 What do you think can be most frequently performed operations while working with graph。

 One of the most frequently performed operations while working with graph would be finding all nodes adjacent to a given node。

 that is finding all nodes directly connected to a given node。

 What do you think would be time cost of finding all nodes directly connected to a given node。 Well。

 we will have to scan the whole edge list we will have to perform a linear search。

 we will have to go through all the entries in the list and see if the start or end node in the entry is our given node for a directed graph we would see if the start。

n in the entry is our given node or not and for an undirected graph we would see both the start as well as the end node running time would be proportional to number of edges or in other words time complexity of this operation would be big o of number of edges Okay now another frequently performed operation can be。

Finding if two given nodes are connected or not in this case also。

 we will have to perform a linear search on the edge list In worst case。

 we will have to look at all the entries in the edge list。

So worst case running time would be proportional to number of edges。

 so for this operation to time complexity is big O off number of edges。Now。

 let's try to see how good or bad this running time big O off number of edges is。

 If you remember this discussion from our previous lesson in a simple graph。

 in a graph with no self loop or multi edge， if number of what is see。



![](img/3d38bebd7b1eaf61ff9750f799856fc4_9.png)

That is the number of elements in set v is equal to n。Then maximum number of edges。

Would be n into n -1 if the graph is directed。Each node will be connected to every other node。 and。

 of course， minimum number of edges can be 0。 We can have a graph with no edge。

 Maximum number of edges would be n into n -1 by 2 if the graph is undirected。But all in all。

 if you can see， number of edges can go almost up to square of number of vertices。

 number of edges can be of the order of square of number of vertices。

Let's denote number of vertices here as small V。So number of edges can be of the order of v squared。

In a graph， typically any operation running in order of number of edges would be considered very costly。

We try to keep things in order of number of vertices。When we are comparing the two running times。

 this is very obvious。Big O of v is a lot better than big O of v squared。All in all。

 this verex list and edge list kind of representation is not very efficient in terms of time cost of operations。

We should think of some other efficient design。 We should think of something better。



![](img/3d38bebd7b1eaf61ff9750f799856fc4_11.png)

We will talk about another possible way of storing and representing graph in next lesson。

 this is it for this lesson， thanks for watching。

![](img/3d38bebd7b1eaf61ff9750f799856fc4_13.png)