# 伊利诺伊大学【中英⚡计算机科学基础｜Accelerated Computer Science Fundamentals Specialization】 p42 P42 03_4-1-3-图论-深度优先搜索遍历 -BV1KnLCzXEcQ_p42-

![](img/4c30d1233cf58741650b44858e7c8d01_0.png)

![](img/4c30d1233cf58741650b44858e7c8d01_1.png)

In the previous videos， we've talked about the breadth first search traversal。

 and now we want to dive in and actually do a different type of traversal。

 a depth first search traversal。In a breadth first traversal。

 we identified all of our children nodes or our nearby incident nodes first。

 and then we visited their children or their instant nodes。 in a depth first search traversal。

 we want to go very， very deep， very quickly in a BFS。

 we use a Q structure to maintain our data structure here we're going to maintain our data structure using a stack structure。

And to make this really， really easy， we already know we call stack frames when we call C plus plus code。

 So we won't even worry about the structure itself。 Instead。

 we're just going to visit every single node as we see them as we move through our recursion。

 So this algorithm is going to be really， really quick to understand。

So let's go and start with Note A and go through this just like we did before。😡，Start with node A。

 I'm going to just start drawing a circle as I want to want to visit every single node around node A。

 So I'm going to start here。 and as soon as I cross an edge， have I seen this edge before。

 have I visited D no， So this is a discovery edge， and now I've moved from A to D。So now at D。

 let's do the exact same thing， let's start at D， let's start drawing my circle and oh。

 I found a new edge， it's discovering something new， so let's keep going down。

 let's keep doing our depth first traersal， we move to H again start in this circle from about the same spot and oh。

 H goes to G A we have a new newly discovered vertex here at G we're going to do the same thing and we're going to go ahead and start and oh。

 we got to J。Do a discovery here on J。 And now at J， the exact same thing。We're going to look at J。

 start looking at all the edges we might visit， and we find that we have an edge from J to K。

 we've discovered a new node and finally at K we can repeat this process for one last time。

And see at K， we start here。 And here we have an edge that no longer discovers something new at this edge from K to a。

 We already know about a。 A' has been discovered。 So we're not going to mark this as a new discovered edge。

 Instead， we want to mark the K edge as a back edge。

 It gets us somewhere further back in our process。 So just。Just like a cross edge inside of a BFS。

 a back edge is going to be an edge that's not a discovery edge in a DFS。

 So I'm going to label it with dots just as I did with the cross edges。So here adding dots。

We now know that's a back edge continuing on K。 We find that K to E is a discovery edge。

 We discover something new about E。 and now at E， let's continue on。And say， okay， E。

 have you found up， this is now a back edge because we've already seen the node D。

 so we don't want to do this as a new discovery edge。

We've completely finished an E visit all the edges， we go back to K， the completely finish。

 I's completely finished， and now here we're back at G。And in G， we need to continue our circle。

We find a new edge here， it's already been labeled。So at G now we see a new edge C。

 C is a discovery edge。C has a back edge to D， sorry already even discovered and a discovery edge to B。

Finally， F is discovered when we visit G and has a back edge to D。

So notice we did this entire algorithm without ever thinking about a cure stack data structure。

We have an implicit stack going on based on the calling stack in our recursive algorithm。

 but here we're able to build something up entirely by a really， really simple code。

 So you know that this has the same roots as a BFS algorithm。 You can see we did the same process。

 which is a different ordering of visiting nodes。 Let's see how this code differs。😊。

Here's a BFS code。 All I need to do is remove everything that has to do with a queue。

 and I'm going to have a perfectly great call stack。

So instead of going through and looking at elements related to a Q。I remove all the Q lines。

Change the cross edges to discovery edges。And make sure instead of inqueuing。

 I'm going to call a new version of my depth for search algorithm with a graph on my new node。

By making these changes all over， I can modify this code from a BFS algorithm to a DFS algorithm by simply removing a few lines of code related to the Q。

 calling DFS instead， and labeling it as a back edge instead。

So we now have the code that allows us to do a DFS traversal。😡，In。

The exact same way is a BFS traversal， but we visit our deep nodes extremely early in this process。

So in the previous time， we did an analysis of the actual code to understand how it worked。😡，Here。

 I want to do in a different form of analysis to see what the running time of the BFS algorithm and DFS algorithms are。

 and you'll see that this analysis works for both algorithms。

 and it's another way to compute the exact same running time。

We know the only operations that we're going to perform on a data structure like this is going to be operations that involve labeling our nodes。

 so every time we do any operation we're always going to do a labeling。

 so let's count how many labels that take place when we label all of our vertices and when we query them to find out when the next one is。

😡，So when we label a vertex， we know that every single vertex we initially have undiscovered。

 and then we label is discovered at some point in time。

 So we don't do a total of two times n labelings or O of n labels。We label every edge twice as well。

 So we do two times M labels in edges or O of M labels。 They're originally a undiscovered edge。

 and then theyre they're either a discovered edge or a back edge。Now。

 when we query our data structure， we know that we're going around every single node。

 so we know that we're going through every single vertex exactly once。

 so we visit every vertex exactly one time this On。When we look at a single vertex。

 we're going to visit every single one of those vertices。Edges。

So we know that potentially a vertex can have every single edge connected to it。

 but we have a mathematics who say it's actually the degree of V。For every single time。

 so we have degree of V for every single one of our vertices。

 we know we're going to visit every single one of our vertexes。

 so we know that this is the sum of all of degrees of v。

 the sum of all of degrees of v is equal to 2 m， which equal to O of M so what we have is O of n plus O of M plus O of M plus O of M so total running time is O of n plus M。

This is the exact same running time as doing a BFS traversal。

 so we can see by doing two different analysis， we have two different forms of doing a BFS and DFS traversal。

 those two different forms of traversal are going to both run an n plus M time and you'll notice thiss the optimal running time for running this。

Because we have to visit every single node exactly once。

 and we have to visit every single edge exactly once。

 So there's no way we can do fashion in plus M time。 So both the B。

FS and DFS traversal are optimal traversal running optimal running times for a graph。😊。

And they give us some really interesting bits about the substructure。

 like this spanning tree we talked about in BFS。Next。

 we want to dive into actually understanding how we can do even more interesting data structures and。

Figure out how we can find out structures like spanning trees and cycles within our graph。

 So we'll dive into those things in the next video。 We'll talk more about spanning trees。

 then see there。😊。

![](img/4c30d1233cf58741650b44858e7c8d01_3.png)